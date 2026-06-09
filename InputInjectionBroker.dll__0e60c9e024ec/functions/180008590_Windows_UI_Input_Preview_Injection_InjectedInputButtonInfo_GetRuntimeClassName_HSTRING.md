# Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180008590`
- end: `0x1800085ad`
- name: `?GetRuntimeClassName@InjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800085a6`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InjectedInputButtonInfo", 0x3Au, a2);
}

```

## disassembly

```asm
0x180008590  mov     qword ptr [rdx], 0
0x180008597  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InjectedInputButtonInfo@@3QBGB; "Windows.UI.Input.Preview.Injection.Inje"...
0x18000859e  mov     r8, rdx
0x1800085a1  mov     edx, 3Ah ; ':'
0x1800085a6  jmp     cs:__imp_WindowsCreateString
```
