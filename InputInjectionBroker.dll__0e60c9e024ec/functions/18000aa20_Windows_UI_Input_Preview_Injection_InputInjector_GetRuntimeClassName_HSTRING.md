# Windows::UI::Input::Preview::Injection::InputInjector::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000aa20`
- end: `0x18000aa3d`
- name: `?GetRuntimeClassName@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000aa50`
- `0x18000aa60`
- `0x18000aa70`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000aa36`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InputInjector::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InputInjector *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InputInjector", 0x30u, a2);
}

```

## disassembly

```asm
0x18000aa20  mov     qword ptr [rdx], 0
0x18000aa27  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InputInjector@@3QBGB; "Windows.UI.Input.Preview.Injection.Inpu"...
0x18000aa2e  mov     r8, rdx
0x18000aa31  mov     edx, 30h ; '0'
0x18000aa36  jmp     cs:__imp_WindowsCreateString
```
