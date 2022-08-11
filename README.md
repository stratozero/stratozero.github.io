# Get ready for code! 😎  

I only want to improve my written english, and do this by giving some useful advice to beginner java developers.

Just be patient with me and issue any problem [in the GitHub issue section](https://github.com/stratozero/stratozero.github.io/issues)

## Tips

Here you can find some code tips. Some are good examples to follow,
other are bad examples or worst

### Properties API

`java.util.Properties` do have a method `getProperty(key, defaultValue)` which evaluate a key and, of not found, return a default value, but this return value should heve been already calculated, even if it's not used.

To avoid this and cover this lack of implementation you can do this:

```java
final Properties properties = new Properties();
// populate properties
final String value = Objects.requireNotNullElseGet(
    properties.getProperty("eventuallyNonExistentProperty"),
    () -> "A calculated default value made with " + expensiveCalculation()
);
```

Which has a comprehensible semantic and do the tick very well
