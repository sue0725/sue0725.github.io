---

title: "스위프트로 아이폰 앱 만들기 - Chapter1. Hello World!"
date: 2021-07-21 19:28:43 -0400
categories: IosStudy

---

**Hello! Ios!**

# Hello World 앱 전체 소스

        import UIkit

        class ViewController: UIViewController {
            @IBOutlet var lblHello: UILabel!        // 출력 레이블 용 아웃렛 변수
            @IBOutlet var txtName: UITextField!     // 이름 입력용 아웃렛 변수
    

        override func viewDidload(){
            super.viewDidLoad()
        }

        @IBAction func btnSend(_ sender: UIButton) {
            // "Hello, " 라는 문자열과 txtName.text의 문자열을 결합하여 lblHello.txt에 넣음
            lblHello.text = "Hello, " + txtName.text!
        }
    }


_객체에 대한 속성을 지정할 때는 **아웃렛**, 객체에 이벤트를 넣고 싶을 때는 **액션**으로 연결한다._


---

## 아웃렛 변수를 추가하는 소스

    @IBOutlet var lblHello: UILable!


`@IBOutlet` : @IBOutlet으로 정의된 변수. IB는 Interface Builder의 약자로 @IB로 시작되는 변수나 함수는 인터페이스 빌더와 관련된 변수나 함수라는 것을 의미

`var lblHello:` : 변수를 선언할 때는 var 키워드를 사용

`UILabel!` : 선언하고자 하는 변수의 타입

`strong/weak` : storage라는 항목에서 strong과 weak 둘 중 선택할 수 있다.

    @IBOutlet var lblHello: UILabel!        // strong으로 선언
    @IBOutlet weak var lblHello: UILabel!   // weak로 선언

_strong과 weak는 메모리 회수 정책을 나타내는 키워드, 일반적으로 객체를 참조하기 위한 아웃렛 변수는 strong을 사용한다._

---

## 액션 함수를 추가하는 소스

    @IBAction func btnSend(_ sender: UIButton) {
        lblHello.text = "Hello, " + txtName.txt!
    }


`@IBAction` : 객체의 이벤트를 제어하기위해 사용하는 키워드 (버튼을 누르거나 피커가 선택되는 등...)

`func btnSend` : 함수를 선언할 때 func 키워드를 사용해서 선언 func 뒤에 액션 함수의 이름 btnSend를 입력하여 액션함수 선언

`(_ sender: UIButton)` : 액션 함수가 실행되도록 이벤트를 보내는 객체, 버튼 객체에서 이벤트가 발생했을 때 해당 액션 함수를 실행시킬 것이므로 UIButton 클래스 타입 선택

`lblHello.text` : 레이블 객체가 가지고 있는 속성 중 텍스트 내용을 의미하는 속성

`+` : 앞의 문자열과 뒤의 문자열을 합한다는 의미

`txtName.text!` : 텍스트필드 객체가 가지고 있는 속성 중 텍스트 내용을 의미하는 속성
