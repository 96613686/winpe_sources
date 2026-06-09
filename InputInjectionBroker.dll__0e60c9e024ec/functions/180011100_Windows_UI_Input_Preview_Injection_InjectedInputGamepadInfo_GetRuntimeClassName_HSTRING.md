# Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180011100`
- end: `0x18001111d`
- name: `?GetRuntimeClassName@InjectedInputGamepadInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180011116`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InjectedInputGamepadInfo", 0x3Bu, a2);
}

```

## disassembly

```asm
0x180011100  mov     qword ptr [rdx], 0
0x180011107  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InjectedInputGamepadInfo@@3QBGB; "Windows.UI.Input.Preview.Injection.Inje"...
0x18001110e  mov     r8, rdx
0x180011111  mov     edx, 3Bh ; ';'
0x180011116  jmp     cs:__imp_WindowsCreateString
```
