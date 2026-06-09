# Windows::UI::Input::Preview::Injection::InputInjectorStatics::TryCreate(Windows::UI::Input::Preview::Injection::IInputInjector * *)

- ea: `0x180008b00`
- end: `0x180008b1b`
- name: `?TryCreate@InputInjectorStatics@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUIInputInjector@23456@@Z`
- size: `27`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjectorStatics *__hidden this, struct Windows::UI::Input::Preview::Injection::IInputInjector **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007c78`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjectorStatics::TryCreate(
        Windows::UI::Input::Preview::Injection::InputInjectorStatics *this,
        struct Windows::UI::Input::Preview::Injection::IInputInjector **a2)
{
  char v3; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  return Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Input::Preview::Injection::InputInjector,Windows::UI::Input::Preview::Injection::IInputInjector,bool>(
           a2,
           &v3);
}

```

## disassembly

```asm
0x180008b00  sub     rsp, 28h
0x180008b04  mov     rcx, rdx
0x180008b07  mov     [rsp+28h+arg_10], 0
0x180008b0c  lea     rdx, [rsp+28h+arg_10]
0x180008b11  call    ??$MakeAndInitialize@VInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector@23456@_N@Details@WRL@Microsoft@@YAJPEAPEAUIInputInjector@Injection@Preview@Input@UI@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Input::Preview::Injection::InputInjector,Windows::UI::Input::Preview::Injection::IInputInjector,bool>(Windows::UI::Input::Preview::Injection::IInputInjector * *,bool &&)
0x180008b16  add     rsp, 28h
0x180008b1a  retn
```
