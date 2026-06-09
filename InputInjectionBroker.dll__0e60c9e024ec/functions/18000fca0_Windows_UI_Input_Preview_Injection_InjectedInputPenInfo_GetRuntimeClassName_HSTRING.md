# Windows::UI::Input::Preview::Injection::InjectedInputPenInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000fca0`
- end: `0x18000fcbd`
- name: `?GetRuntimeClassName@InjectedInputPenInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputPenInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000fcb6`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InjectedInputPenInfo::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InjectedInputPenInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InjectedInputPenInfo", 0x37u, a2);
}

```

## disassembly

```asm
0x18000fca0  mov     qword ptr [rdx], 0
0x18000fca7  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InjectedInputPenInfo@@3QBGB; "Windows.UI.Input.Preview.Injection.Inje"...
0x18000fcae  mov     r8, rdx
0x18000fcb1  mov     edx, 37h ; '7'
0x18000fcb6  jmp     cs:__imp_WindowsCreateString
```
