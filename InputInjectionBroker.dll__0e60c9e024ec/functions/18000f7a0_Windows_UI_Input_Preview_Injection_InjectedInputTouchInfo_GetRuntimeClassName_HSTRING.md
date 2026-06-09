# Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000f7a0`
- end: `0x18000f7bd`
- name: `?GetRuntimeClassName@InjectedInputTouchInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f7b6`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InjectedInputTouchInfo", 0x39u, a2);
}

```

## disassembly

```asm
0x18000f7a0  mov     qword ptr [rdx], 0
0x18000f7a7  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InjectedInputTouchInfo@@3QBGB; "Windows.UI.Input.Preview.Injection.Inje"...
0x18000f7ae  mov     r8, rdx
0x18000f7b1  mov     edx, 39h ; '9'
0x18000f7b6  jmp     cs:__imp_WindowsCreateString
```
