# MCF Calendar Automation

Automatically downloads the MCF calendar ICS file every 6 hours and commits it to this repository.

## Overview

This repository contains a GitHub Actions workflow that:
- Downloads the calendar from: `https://calendar.google.com/calendar/ical/calendar%40mcfolsom.com/public/basic.ics`
- Runs automatically every 6 hours (at 0, 6, 12, 18 UTC)
- Commits changes to the repository when the calendar is updated

## Files

- `calendar.ics` - The downloaded calendar file
- `download.log` - Log of download timestamps
- `.github/workflows/download-calendar.yml` - GitHub Actions workflow configuration

## Setup

1. Push this repository to GitHub
2. The workflow will automatically start running on the schedule
3. You can manually trigger a download by going to Actions > Download Calendar > Run workflow

## How It Works

The GitHub Actions workflow runs on a schedule and:
1. Checks out the repository
2. Downloads the latest ICS file using `curl`
3. Commits and pushes changes if the calendar has been updated

## Schedule

The workflow runs at:
- 00:00 UTC (6am EST)
- 06:00 UTC (12pm EST)
- 12:00 UTC (6pm EST)
- 18:00 UTC (12am EST)

You can adjust the cron schedule in `.github/workflows/download-calendar.yml` if needed.
