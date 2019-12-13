# grafana-wizzy-dashboard
Simple Example of Grafana Dashboard (for wizzy import/export)

## alternative snippet to download dashboards (run from Console):
```javascript
(await fetch("/api/search?limit=1000").then(r => r.json())).map(r => r.uid).map(async (uid) => {
  const jsonData = (await fetch(`/api/dashboards/uid/${uid}`).then(r => r.json())).dashboard
  const a = document.createElement("a");
  a.href = URL.createObjectURL(new Blob([JSON.stringify(jsonData)], {type: 'application/json'}));
  a.download = `dashboard-${uid}.json`;
  a.click();
})
```
