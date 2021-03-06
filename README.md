# ZingChart Distributed Weighted Average Module

This module calculates the distributed weighted average of your plots.

![dwa example](/assets/dwa-example-graph1.png)

### Usage
1. Include the module in your page after the zingchart library
2. Include the module reference in the zingchart.render({}) method.
<pre><code>zingchart.render({
		id : 'myChart',
		data : myConfig,
		height: 400,
		width: '100%',
		modules: "dwa" // Include the dwa module!
});
</code></pre>

### Docs

There are a couple attributes you can define in your chart configuration for the dwa module.

1. dwa (object) - This object can be defined in the root of the chart configuration. Within this object you can define two properties <b>visibleAtFirst</b> and <b>name</b>.
	* visibleAtFirst (boolean) - If true this attribute will show the dwa plot when the graph loads. This is the default.
	* name (string) - If defined, this name will appear in the legend. The default text is "Weighted Average".
    * color (string) - If defined this will set the color of your dwa plot. Otherwise it will default to the standard library color for that plot.
<pre><code>dwa:{
            // 'dwa' module is loaded in the render method below.
            visibleAtFirst:true, // Default is true
            name: "Distributed Weighted Average", // Optional Name
            color: '#000' // Optional Color
        },</code></pre>
2. weight (Number) - If defined, it must be defined within each individual series object. The default weight is 1, in which case the weighted average is an even distribution amongst plots.
<pre><code>series : [
        {
            values: [35,42,67,89,25,34,67,85],
            weight: 0.4 // optional weight
        },
        {
            values: [74,71,89,34,26,73,21,56],
            weight: 0.6 // optional weight
        }
   ]
</code></pre>

