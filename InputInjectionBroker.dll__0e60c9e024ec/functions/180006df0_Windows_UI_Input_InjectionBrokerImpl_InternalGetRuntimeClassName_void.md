# Windows::UI::Input::InjectionBrokerImpl::InternalGetRuntimeClassName(void)

- ea: `0x180006df0`
- end: `0x180006df8`
- name: `?InternalGetRuntimeClassName@InjectionBrokerImpl@Input@UI@Windows@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180006df0`: `Windows.UI.Input.InjectionBroker`

## pseudocode

```c
const unsigned __int16 *Windows::UI::Input::InjectionBrokerImpl::InternalGetRuntimeClassName(void)
{
  return L"Windows.UI.Input.InjectionBroker";
}

```

## disassembly

```asm
0x180006df0  lea     rax, ?RuntimeClass_Windows_UI_Input_InjectionBroker@@3QBGB; "Windows.UI.Input.InjectionBroker"
0x180006df7  retn
```
