---
title: dayClick
type: callback
---

Triggered when the user clicks on a day.

<div class='spec' markdown='1'>
function( *date*, *allDay*, *jsEvent*, *view* ) { }
</div>

`date` holds a Date object for the current day. If user has clicked on a slot in the agendaWeek or agendaDay views, `date` will also have its time set.

`allDay` will be set to `false` if the user has clicked on a slot in the agendaWeek or agendaDay views. Otherwise, it will be `true`.

`jsEvent` holds the native JavaScript event with low-level information such as click coordinates.

`view` is set to the current [View Object](view-object).

Within the callback function, `this` is set to the `<td>` of the clicked day.

Here is an example that demonstrates all of these variables:

```js
$('#calendar').fullCalendar({
  dayClick: function(date, allDay, jsEvent, view) {

    if (allDay) {
      alert('Clicked on the entire day: ' + date);
    }else{
      alert('Clicked on the slot: ' + date);
    }

    alert('Coordinates: ' + jsEvent.pageX + ',' + jsEvent.pageY);

    alert('Current view: ' + view.name);

    // change the day's background color just for fun
    $(this).css('background-color', 'red');

  }
});
```

<div class='version-info' markdown='1'>
The *allDay* parameter has only been available since version 1.4.
</div>
