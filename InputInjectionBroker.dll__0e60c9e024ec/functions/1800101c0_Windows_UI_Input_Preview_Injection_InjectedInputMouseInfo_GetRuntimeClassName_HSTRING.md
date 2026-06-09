# Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800101c0`
- end: `0x1800101dd`
- name: `?GetRuntimeClassName@InjectedInputMouseInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800101d6`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo::GetRuntimeClassName(
        Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.Preview.Injection.InjectedInputMouseInfo", 0x39u, a2);
}

```

## disassembly

```asm
0x1800101c0  mov     qword ptr [rdx], 0
0x1800101c7  lea     rcx, ?RuntimeClass_Windows_UI_Input_Preview_Injection_InjectedInputMouseInfo@@3QBGB; "Windows.UI.Input.Preview.Injection.Inje"...
0x1800101ce  mov     r8, rdx
0x1800101d1  mov     edx, 39h ; '9'
0x1800101d6  jmp     cs:__imp_WindowsCreateString
```
