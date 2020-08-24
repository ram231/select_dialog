# select_dialog Package

> Note: this package is just a fork to make barrierDismissable set to a boolean value.
> Please Read the simple example in the code below
Package designed to select an item from a list, with the option to filter and even search the items online.
<img src="https://github.com/davidsdearaujo/select_dialog/blob/master/screenshots/Screenshot_1.png?raw=true" width="49.5%" /> <img src="https://github.com/davidsdearaujo/select_dialog/blob/master/screenshots/Screenshot_2.png?raw=true" width="49.5%" />


## Steps to follow:

## 1. Add the forked package from github in your pubspec.yaml
```yaml
select_dialog:
  git:
    url:  https://github.com/ram231/select_dialog.git
```
## 2. import
```dart
import 'package:select_dialog/select_dialog.dart';
```

## 3. simple example
```dart
String ex1 = "No value selected";

SelectDialog.showModal<String>(
  context,
  label: "Simple Example",
  selectedValue: ex1,
  barrierDismissable: false, /// Prevents user to dismiss outside the dialog
  items: List.generate(50, (index) => "Item $index"),
  onChange: (String selected) {
    setState(() {
      ex1 = selected;
    });
  },
);
```


# Attention
To use a template as an item type, you need to implement **toString**, **equals** and **hashcode**, as shown below:

```dart
class UserModel {
  final String id;
  final DateTime createdAt;
  final String name;
  final String avatar;

  UserModel({this.id, this.createdAt, this.name, this.avatar});

  @override
  String toString() => name;

  @override
  operator ==(o) => o is UserModel && o.id == id;

  @override
  int get hashCode => id.hashCode^name.hashCode^createdAt.hashCode;

}
```


## Getting Started

This project is a starting point for a Dart
[package](https://flutter.dev/developing-packages/),
a library module containing code that can be shared easily across
multiple Flutter or Dart projects.

For help getting started with Flutter, view our 
[online documentation](https://flutter.dev/docs), which offers tutorials, 
samples, guidance on mobile development, and a full API reference.
