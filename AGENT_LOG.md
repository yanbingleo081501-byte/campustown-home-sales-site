# Agent log

Add a dated entry each time you work with your AI coding agent, with the newest entry at the bottom. Each entry records what you asked the agent, what it produced, and what you checked or changed. Paste your key prompts in exactly as you typed them. Include at least one time the agent got something wrong, and how you caught it.

Copy this outline for each entry:

```markdown
## 2026-11-19: Build the first home sales page

- **Asked:**

  > Read AGENTS.md and docs/data_description_sheet.md first. Replace the placeholder index.html with a simple webpage that shows the median home sale price by city using the provided dataset. Show the results in a bar chart and a table, and format the prices as whole-dollar amounts. Briefly explain how the medians were calculated.

- **Agent produced:** Codex replaced the placeholder with a bar chart and table showing median sale prices for 18 cities. It formatted prices as whole dollars and explained how the medians were calculated using sales of $1,000 or more.
- **Checked or changed:** I opened the downloaded `index.html` in Chrome. The page title and table headers appeared, but the chart and table rows were blank. I asked Codex to fix the display before merging.

## 2026-11-19: Fix the blank chart and table

- **Asked:**

  > I opened the downloaded index.html directly in Chrome. The title and table headers appear, but the chart and table rows are blank. Please make the 18 chart bars and 18 table rows render directly in index.html without relying on JavaScript at page load. Keep the existing design, whole-dollar prices, and the $1,000 cutoff explanation. Verify that the revised file displays all 18 cities when opened directly in a browser.

- **Agent produced:** Codex put the 18 chart bars and 18 table rows directly in the HTML so they could display without JavaScript running at page load.
- **Checked or changed:** I reviewed the updated preview and confirmed that the chart and table showed all 18 cities and that Pittsboro's median displayed as $876,986. I merged PR #1 into `main`. The public site was then checked in an incognito window.

## 2026-11-19: Review the design and update the price rule

- **Asked:** I used ChatGPT to change the page to a light blue color scheme and update the title to “What homes sold for in each city.” I then used Codex Cloud to review the draft and sent this prompt to update the price rule:

  > Update my existing draft PR #2:
  > https://github.com/yanbingleo081501-byte/campustown-home-sales-site/pull/2
  >
  > Read AGENTS.md and docs/data_description_sheet.md first. Use the original CSV to keep only sales of $10,000 or more. Recalculate each city’s median sale price and qualifying sales count, then update both the chart and table. Sort by median price from highest to lowest and display prices rounded to whole dollars.
  >
  > Above the chart, display the number of cities and the total number of qualifying sales. Calculate both from the filtered data. The expected result is 18 cities and 35,402 qualifying sales. If your results differ, check why and report the difference.
  >
  > Add this note above the chart:
  > “Price rule: Sales under $10,000 are excluded. The median for each city is calculated from the remaining sale prices.”
  >
  > Update the methods section to use the same $10,000 cutoff. Keep the light blue design, the current title, and the chart and table rendered directly in HTML. Push the changes to the current branch of PR #2 and leave it as a draft for me to review.

- **Agent produced:** Codex recalculated the city medians and sales counts from the CSV using the $10,000 cutoff. It updated the chart, table, and methods note and added a summary showing 18 cities and 35,402 qualifying sales.
- **Checked or changed:** I previewed the revised page and merged PR #2 into `main`. The merged `index.html` was checked for the new title, the $10,000 price rule, and the total of 35,402 qualifying sales.
```
