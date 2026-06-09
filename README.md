[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/qF8WcF0i)
# Week 1: Evidence Desk Patterns

## Student

**Name:** Bijay Shahi  
**Student ID:** 2412083

## Summary

This assignment focuses on solving common data structure problems using dictionaries, sets, and stacks.

The Evidence Counter function uses a dictionary to count how many times each evidence label appears.

The Repeat Suspect ID function uses a set to quickly detect the first duplicate ID.

The Evidence Tag Validator uses a stack to verify that brackets are balanced and correctly matched.

The Alias Directory function uses a dictionary as a lookup table to find a real name from a given alias.

The optional challenges introduce queue processing using `deque` and sorting techniques to find the largest time gap between events.

---

## Approach

### `count_evidence`

- Iterate through each evidence label.
- Store counts inside a dictionary.
- Increase the count whenever a label appears again.
- Return the completed dictionary.

### `first_repeated_id`

- Create a set to store IDs that have already been seen.
- Check each ID while looping through the list.
- Return the first ID that appears a second time.
- Return `None` if no duplicate exists.

### `valid_tags`

- Use a list as a stack.
- Push opening brackets onto the stack.
- Match closing brackets with the most recent opening bracket.
- Return `True` only when all brackets are balanced.

### `lookup_alias`

- Search for the alias in the dictionary.
- Return the matching real name.
- Return `None` if the alias is not found.

### `process_reports`

- Store reports inside a queue using `deque`.
- Process reports in first-in, first-out order.
- Return the processed list.

### `largest_time_gap`

- Sort the list of event times.
- Compare neighboring values.
- Track the largest difference found.
- Return the largest gap.

---

## Complexity

### `count_evidence`

- **Time:** `O(n)`
- **Space:** `O(n)`

**Why:** Each evidence label is processed once and stored in a dictionary.

### `first_repeated_id`

- **Time:** `O(n)`
- **Space:** `O(n)`

**Why:** Each ID is checked once and stored in a set for fast lookups.

### `valid_tags`

- **Time:** `O(n)`
- **Space:** `O(n)`

**Why:** Each character is processed once and unmatched opening brackets are stored in a stack.

### `lookup_alias`

- **Time:** `O(1)`
- **Space:** `O(1)`

**Why:** Dictionary lookups are constant time on average.

### `process_reports`

- **Time:** `O(n)`
- **Space:** `O(n)`

**Why:** Every report enters and leaves the queue exactly once.

### `largest_time_gap`

- **Time:** `O(n log n)`
- **Space:** `O(n)`

**Why:** The list must be sorted before scanning for the largest neighboring gap.

---

## Edge-Case Checklist

- [x] Empty list
- [x] One item
- [x] Repeated items
- [x] Different labels
- [x] No repeated IDs
- [x] First two IDs match
- [x] Empty string
- [x] Correctly nested tags
- [x] Mismatched tags
- [x] Closing tag before opening tag
- [x] Unclosed opening tag
- [x] Non-bracket characters
- [x] Known alias
- [x] Unknown alias
- [x] Empty dictionary

---

## Tests

Run all tests with:

```bash
pytest -q