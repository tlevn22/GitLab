# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose
answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)

 The SHA for this branch is 9b257.

2. What is the SHA for the last commit associated with line 9 of this file?

The SHA for line 9 of this file was b2ed3

3. What did line 12 of this file say in commit d1d83?

Line 12 said: 2. I should really finish writing this.

4. What changed between commit e474c and 82045?

Between e474c and 82045 changes were made to the function find_top_5 in movie_data.py. gross_sort was updated to turning it into an int, and top_five was updated to actually show 5 values. 


## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N

```
The function will change from top_5 to top_N in test 

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```

The quiz.md will change to answers.md in top_ten

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```
The first rebase will work correctly, changing top_5 to top_10. However, the second rebase has some changes between top_N and top_10 because there is a different commit that the first commit isn't aware of. Then, after editing the files where different changes and commits were made, then going back into git log, now both changes are shown in the log as test is aware of both things happening. 
