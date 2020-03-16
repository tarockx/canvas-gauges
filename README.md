# HTML Canvas Gauges + mods

This is a fork of [HTML Canvas Gauges](https://github.com/Mikhus/canvas-gauges) with some additional functionalities

Original readme available [here](./README_ORIGINAL.md)

All credits for the HTML Canvas Gauge library go to the respective authors.

## Changelog

### v 1.0.0
- Initial release of modded version

## Features

This fork includes the following additional features

### Value box and Units label offset

The following new settings allow you to apply an offset to the position of the Value Box and Units label:

|Option|Description|Type|Default
|-|-|-|-|
|`valueBoxVerticalOffset`|Shifts the Value Box vertically|`Number`|`0`|
|`valueBoxHorizontalOffset`|Shifts the Value Box horizontally|`Number`|`0`|
|`unitsVerticalOffset`|Shifts the units label vertically|`Number`|`0`|
|`unitsHorizontalOffset`|Shifts the units label horizontally|`Number`|`0`|


### Individual ticks side in linear gauge

With this option you can control on which side (left/top, right/bottom or both) each individual tick and tick label in a linear gauge are drawn. This allows you to have some ticks on one side and some on the other, instead of having to chose the side for the entire tickbar.

This option only works if the `exactTicks` option is set to true, i.e.: when you're explicitly providing the gauge with an array of ticks, rather than having them auto-generated.

To use it, add to the gauge options the `majorTicksSides` object, which must be an array with the same length as the `majorTicks` array and, for each position, contains the behavior for the corresponding tick. The supported values are:
- `left` - only show the tick on the left side (or top side for horizontal gauges)
- `right` - only show the tick on the right side (or bottom side for horizontal gauges)
- `both` - show on both sides

NOTE: this option does not override the global `tickSide` option, which will still limit drawing on a single side if set to a value different from `both`.

Here is an example of use:
```JSON
{
    "exactTicks": true,
    "tickSide": "both",
    "majorTicks": [0, 10, 15, 100],
    "majorTicksSides": ["both", "left", "right", "both"]
    ...
}
```
the resoult would be something like this:

![](./assets/images/tick_sides.png)