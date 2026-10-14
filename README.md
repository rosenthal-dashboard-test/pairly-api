# pairly-api

Backend for **Pairly**, the app that matches university students into small study groups.

Maintainer: Daniel Ortiz (CTO)

## What it does

- Stores students, courses, and weekly free-time grids
- Runs the **matching service**, which builds groups of 3 to 5 students
- Sends session reminders to the mobile app ("Your study group meets in 30 minutes")

## Matching service v0.3

Groups are built from three signals:

1. **Shared courses** (same course section scores higher than same course)
2. **Overlapping free time** from the weekly grid
3. **Preferred study style**: quiet, discussion, or exam cram

In tests with the Westbrook University sample data, 87% of students were placed in a group within one minute.

## Roadmap to the beta launch (Nov 2)

- [ ] API response time under 1 second with 200+ students matching at once
- [ ] Fix oversized groups for students with only one course
- [ ] Migrate free-time data to the new format (Saturday, Oct 17, 11 PM - 1 AM ET)
- [ ] Smaller default group size for problem-set groups

## Running locally

```bash
cp .env.example .env
npm install
npm run dev
```

The API runs on http://localhost:4000.
