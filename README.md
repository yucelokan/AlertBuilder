# AlertViewBuilder

![Swift](https://img.shields.io/badge/Swift-5.0-orange.svg)
![Swift](https://img.shields.io/badge/Swift-4.2-orange.svg)
![Swift](https://img.shields.io/badge/Swift-4.0-orange.svg)
![Platform](https://img.shields.io/badge/Platform-iOS-lightgrey.svg)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/yucelokan/AlertBuilder/blob/master/LICENSE)

AlertView is a structure used in situations such as displaying a message to the user or offering a choice. There are already a lot of libraries for that. What I'm trying to do with this library; Allows the developer to create AlertView with View without forcing to use a specific view. This library is not an AlertView library. This library is a builder for AlertView. Create and show on the screen a view with AlertViewBuilder . That's all. This view can be anything. (TextView, TextField, Label, Button, ImageView, TableView etc.)

| Custom 1 | Custom 3 |
|:---:|:---:|
| ![1.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/1.png) | ![4.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/4.png) |

| Custom 3 | Custom 4 |
|:---:|:---:|
| ![6.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/6.png) | ![7.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/7.png) |


| Custom 1 | Custom 3 | Custom 3 |
|:---:|:---:|:---:|
| ![2.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/2.png) | ![8.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/8.png) | ![9.png](https://github.com/yucelokan/AlertBuilder/blob/master/images/9.png) |

## Example

```swift
let alertViewBuilder = AlertViewBuilder() { (builder) in

    builder.addView(with: <ANY VIEW>, tag: 0, height: 50)

    builder.addView(with: AlertSubMessageView.init(messageText: "Message with image"), tag: 134, height: 40)

    builder.addButton(with: "Button 1", backgroundColor: .black, titleColor: .white, font: UIFont.systemFont(ofSize: 15), height: 40, action: {
        print("Button 1 clicked")
    })
    }.build()
```

```swift
let alertViewBuilder = AlertViewBuilder() { (builder) in

    let imageView = UIImageView.init(image: UIImage.init(named: "letter")?.withAlignmentRectInsets(UIEdgeInsets.init(top: -5, left: 5, bottom: -5, right: 5)))
    imageView.contentMode = .scaleAspectFit

    builder.addView(with: imageView, tag: 0, height: 50)
    
    builder.addView(with: AlertSubMessageView.init(messageText: "Message with image"), tag: 134, height: 40)

    builder.addButton(with: "Button 1", backgroundColor: .black, titleColor: .white, font: UIFont.systemFont(ofSize: 15), height: 40, action: {
        print("Button 1 clicked")
    })
    
    builder.addButton(with: "Button 2", backgroundColor: .orange, titleColor: .white, font: UIFont.systemFont(ofSize: 15), height: 40, action: {
        print("Button 2 clicked")
    })
    
    builder.addButton(with: "Button 3", backgroundColor: .white, titleColor: .black, font: UIFont.systemFont(ofSize: 15), height: 40, action: {
        print("Button 3 clicked")
    })
    
    builder.addButton(with: "Button 4", backgroundColor: .purple, titleColor: .white, font: UIFont.systemFont(ofSize: 15), height: 40, action: {
        print("Button 4 clicked")

    })
    }.build()
```

```swift
if let view = alertViewBuilder.getView(viewWithTag: 134) as? AlertSubMessageView{
    print(view.mLabelMessage.text ?? "")
}
```
## Install

```ruby
pod 'AlertViewBuilder' 
```
## License

AlertViewBuilder is available under the MIT license. See the LICENSE file for more info.
