# Description

Identifying Fair Value Gaps/Imbalances areas as trade entry

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1dd90ab0-37c9-44e6-998a-75e1d97974bd/212a561e-37e9-4be0-bfbc-f3a3ac490038/image.png)

# Indicator Code

[tradingview/indicator/fvg.tv at master · vholti/tradingview](https://github.com/vholti/tradingview/blob/master/indicator/fvg.tv)

**Notes:**

This indicator is developed from another indicator that available on TV called Fair Value Gap as code base.

I developed some additional features in this existing indicator, such as:

1. New metrics in the dashboards to count identified FVG, unfilled/unmitigated FVG, and filled/mitigated FVG in the specific market session (e.g. today’s, yesterday, 2 days ago, etc). With this feature you can analyze how FVG appears, filled/mitigated in change of direction case and unfilled/unmitigated in trend following case.
2. Session Time configuration (e.g. 09:30 to 15:00)
3. Day offset to configure which market session you want to identify the FVG
4. List of FVG and mitigated FVG

# Indicator Features

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1dd90ab0-37c9-44e6-998a-75e1d97974bd/18a0f661-c49e-4a15-8e64-fdc7ba0512e9/image.png)

## Threshold

Threshold percentage used to filter our FVG’s based on their height

## Auto Threshold

Use the cumulative mean of relative FVG heights as threshold

## Unmitigated Levels

Extend the mitigation level of the number of unmitigated FVG’s set by the user

## Mitigation Levels

Show the mitigation levels of mitigated FVG’s

## Timeframe

Timeframe of the price data used to detect FVG’s

## Dashboard

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1dd90ab0-37c9-44e6-998a-75e1d97974bd/f4a5f441-8663-40e0-af0e-3ce14b13a951/image.png)

The dashboard shows following metrics:

1. FVG metrics from all available bars in the chart:
    1. Total FVG count
    2. Unmitigated count and percentage
    3. Mitigated count and percentage
2. FVG metrics from market session that configured in Session Time and Day Offset configuration
    1. Total FVG count
    2. Unmitigated count and percentage
    3. Mitigated count and percentage

## Session Time

Specific session time to select specific FVG to show in session metrics in the dashboard

## Day Offset

Day offset from today’s date to select specific FVG to show in session metrics in the dashboard. For example today is Sunday and you want to see FVG metrics from last Friday (2 days ago). In this example you need to enter 2 as day offset.

## List of FVG and Mitigated FVG

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1dd90ab0-37c9-44e6-998a-75e1d97974bd/e7feccd2-c19e-4dbd-84e8-ddf3a298fd88/image.png)

The list of FVG is available in the indicator logs. Here is the intruction how to show the logs:

1. Select `Pine Editor`
2. Select the three dots beside `Publish indicator`
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1dd90ab0-37c9-44e6-998a-75e1d97974bd/a0378bd9-0dc2-4453-87d6-1505bc829eb9/image.png)
    
3. Select `Pine Logs...`
    
    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1dd90ab0-37c9-44e6-998a-75e1d97974bd/1a639f3a-e78b-48c1-84a0-028d18469456/image.png)
    

## Alerts

Several alerts are available for you to use:

1. Bullish FVG
2. Bearish FVG
3. Bullish FVG Mitigation
4. Bearish FVG Mitigation

# Strategy

## Entry

1. Check trend. If trend is `bullish` then expect to see `Bullish FVG`
2. Check `Order Block`. If there is `bullish breakout`, then it’s confirmed. If there is `OB` as `resistance`, then the entry after breakout has lower risk.

## Exit (alternative 1)

1. Stop Lost trail based on OB

## Exit (alternative 2)

In futures symbol ES I found this profit target is relatively easy to fill when the price is in a clear trend:

1. Fix Profit Target 17.5 points
2. Stop Lost 5 points. You can modify it to any RR you want to achieve.

# Next Development

1. Stretegy Backtest
2. Optimizing Exit