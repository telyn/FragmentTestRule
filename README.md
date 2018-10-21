# Fragment Test Rule

Test `Fragment`s in isolation.

## Download

For use with AndroidX:

```gradle
androidTestImplementation 'com.21buttons:fragment-test-rule:2.0'
debugImplementation 'com.21buttons:fragment-test-rule-extras:2.0'
```

For use with the older Android Support:
```gradle
androidTestImplementation 'com.21buttons:fragment-test-rule:1.1.0'
debugImplementation 'com.21buttons:fragment-test-rule-extras:1.1.0'
```


## Usage

```java
@Rule
public FragmentTestRule<?, FragmentWithoutActivityDependency> fragmentTestRule =
    FragmentTestRule.create(FragmentWithoutActivityDependency.class);

@Test
public void clickButton() throws Exception {
  onView(withText(R.string.button)).perform(click());

  onView(withText(R.string.button_clicked)).check(matches(isDisplayed()));
}
```

You can check the sample code for more examples.
