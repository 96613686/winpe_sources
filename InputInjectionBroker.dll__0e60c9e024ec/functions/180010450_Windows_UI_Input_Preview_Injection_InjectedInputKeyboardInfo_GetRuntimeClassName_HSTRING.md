# Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180010450`
- end: `0x18001046d`
- name: `?GetRuntimeClassName@InjectedInputKeyboardInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010466`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InjectedInputKeyboardInfo", 0x3Cu, a2);
}

```

## disassembly

```asm
0x180010450  mov     qword ptr [rdx], 0
0x180010457  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InjectedInputKeyboardInfo@@3QBGB; "Windows.UI.Input.Preview.Injection.Inje"...
0x18001045e  mov     r8, rdx
0x180010461  mov     edx, 3Ch ; '<'
0x180010466  jmp     cs:__imp_WindowsCreateString
```
