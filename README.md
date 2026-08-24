# Longest Substring Without Repeating Characters

A Python solution for **LeetCode #3 – Longest Substring Without Repeating Characters**.

## 📝 Problem

Given a string `s`, find the length of the longest substring that contains **no repeating characters**.

### Example

**Input:**

```text
s = "abcabcbb"
```

**Output:**

```text
3
```

**Explanation:**

The longest substring without repeating characters is `"abc"`, which has a length of `3`.

---

## 💡 Approach

This solution uses the **Sliding Window** technique along with a Python `set`.

1. Use two pointers, `left` and `right`, to create a sliding window.
2. Store the characters currently inside the window in a `set`.
3. Move `right` through the string.
4. If a duplicate character is found, move `left` forward and remove characters until the duplicate is removed.
5. Keep track of the maximum window length.

---

## 💻 Solution

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        chars = set()
        left = 0
        max_length = 0

        for right in range(len(s)):
            while s[right] in chars:
                chars.remove(s[left])
                left += 1

            chars.add(s[right])

            max_length = max(max_length, right - left + 1)

        return max_length
```

## ⏱️ Complexity

* **Time Complexity:** `O(n)`
* **Space Complexity:** `O(n)`

## 🛠️ Technology

* **Language:** Python 3
* **Platform:** LeetCode
* **Concept:** Sliding Window
* **Data Structure:** Set

## 🎯 What I Learned

* Working with strings in Python
* Using sets to detect duplicates
* Understanding the Sliding Window technique
* Using two pointers
* Improving algorithm efficiency

## 📌 Problem

**LeetCode #3:** Longest Substring Without Repeating Characters

Difficulty: **Medium**

---

⭐ This repository is part of my ongoing **LeetCode problem-solving journey**.
