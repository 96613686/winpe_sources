# Windows::UI::Input::InjectionBrokerImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800067c0`
- end: `0x1800067dd`
- name: `?GetRuntimeClassName@InjectionBrokerImpl@Input@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::UI::Input::InjectionBrokerImpl *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800067d6`

## string_xrefs

- `0x1800067c7`: `Windows.UI.Input.InjectionBroker`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Input::InjectionBrokerImpl::GetRuntimeClassName(
        Windows::UI::Input::InjectionBrokerImpl *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.UI.Input.InjectionBroker", 0x20u, a2);
}

```

## disassembly

```asm
0x1800067c0  mov     qword ptr [rdx], 0
0x1800067c7  lea     rcx, ?RuntimeClass_Windows_UI_Input_InjectionBroker@@3QBGB; "Windows.UI.Input.InjectionBroker"
0x1800067ce  mov     r8, rdx
0x1800067d1  mov     edx, 20h ; ' '
0x1800067d6  jmp     cs:__imp_WindowsCreateString
```
