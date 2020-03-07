# react datepicker

## [react-dates](https://github.com/airbnb/react-dates)

```jsx
import React from "react";
import "./styles.css";
import "react-dates/initialize";
import "react-dates/lib/css/_datepicker.css";
import {
  DateRangePicker,
  SingleDatePicker,
  DayPickerRangeController
} from "react-dates";
import moment from "moment";

export default class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      startDate: null,
      endDate: null,
      focusedInput: null
    };
  }
  render() {
    return (
      <div
        className="App"
        style={{
          display: "flex",
          flexDirection: "column",
          alignItems: "center"
        }}
      >
        <DateRangePicker
          startDate={this.state.startDate} // momentPropTypes.momentObj or null,
          startDateId="your_unique_start_date_id" // PropTypes.string.isRequired,
          endDate={this.state.endDate} // momentPropTypes.momentObj or null,
          endDateId="your_unique_end_date_id" // PropTypes.string.isRequired,
          onDatesChange={({ startDate, endDate }) =>
            this.setState({ startDate, endDate })
          } // PropTypes.func.isRequired,
          focusedInput={this.state.focusedInput} // PropTypes.oneOf([START_DATE, END_DATE]) or null,
          onFocusChange={focusedInput => this.setState({ focusedInput })} // PropTypes.func.isRequired,
        />
        <SingleDatePicker
          date={this.state.date} // momentPropTypes.momentObj or null
          onDateChange={date => this.setState({ date })} // PropTypes.func.isRequired
          focused={this.state.focused} // PropTypes.bool
          onFocusChange={({ focused }) => this.setState({ focused })} // PropTypes.func.isRequired
          id="your_unique_id" // PropTypes.string.isRequired,
        />
        <DayPickerRangeController
          startDate={this.state.startDate} // momentPropTypes.momentObj or null,
          endDate={this.state.endDate} // momentPropTypes.momentObj or null,
          onDatesChange={({ startDate, endDate }) =>
            this.setState({ startDate, endDate })
          } // PropTypes.func.isRequired,
          focusedInput={this.state.focusedInput} // PropTypes.oneOf([START_DATE, END_DATE]) or null,
          onFocusChange={focusedInput => this.setState({ focusedInput })} // PropTypes.func.isRequired,
          initialVisibleMonth={() => moment().add(2, "M")} // PropTypes.func or null,
        />
      </div>
    );
  }
}
```

[https://codesandbox.io/s/github/sangkukbae/react-dates](https://codesandbox.io/s/github/sangkukbae/react-dates)


## [react-infinite-calendar](https://github.com/clauderic/react-infinite-calendar)

```jsx
import React from "react";
import "./styles.css";
import InfiniteCalendar from "react-infinite-calendar";
import "react-infinite-calendar/styles.css"; // Make sure to import the default stylesheet

var today = new Date();
var lastWeek = new Date(
  today.getFullYear(),
  today.getMonth(),
  today.getDate() - 7
);

export default function App() {
  return (
    <div className="App">
      <h1>react-infinite-calendar</h1>
      <InfiniteCalendar
        width={400}
        height={600}
        selected={today}
        disabledDays={[0, 6]}
        minDate={lastWeek}
      />
    </div>
  );
}
```

[https://codesandbox.io/s/react-infinite-calendar-w067f](https://codesandbox.io/s/react-infinite-calendar-w067f)

## [react-datepicker](https://github.com/Hacker0x01/react-datepicker)

```jsx
import React, { useState } from "react";
import "./styles.css";
import DatePicker from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";

export default function App() {
  const [startDate, setStartDate] = useState(new Date());
  return (
    <div className="App">
      <h1>react-datepicker</h1>
      <DatePicker
        selected={startDate}
        onChange={date => setStartDate(date)}
        showTimeSelect
        timeFormat="HH:mm"
        timeIntervals={15}
        timeCaption="time"
        dateFormat="MMMM d, yyyy h:mm aa"
      />
    </div>
  );
}
```

[https://codesandbox.io/s/react-datepicker-3zpnx](https://codesandbox.io/s/react-datepicker-3zpnx)


:memo: **참고 자료**

* [https://airbnb.io/react-dates/?path=/story/daterangepicker-drp--default](https://airbnb.io/react-dates/?path=/story/daterangepicker-drp--default)
* [http://clauderic.github.io/react-infinite-calendar/#/basic-settings/basic-configuration?_k=nw7bg7](http://clauderic.github.io/react-infinite-calendar/#/basic-settings/basic-configuration?_k=nw7bg7)
* [https://reactdatepicker.com/](https://reactdatepicker.com/)
* [https://react-day-picker.js.org/](https://react-day-picker.js.org/) :heavy_check_mark:
* [https://react.rocks/tag/DatePicker](https://react.rocks/tag/DatePicker)


