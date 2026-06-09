# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::InternalGetRuntimeClassNameStatic(void)

- ea: `0x180003dd0`
- end: `0x180003dd8`
- name: `?InternalGetRuntimeClassNameStatic@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180003dd0`: `WindowsInternal.ApplicationModel.Calls.IncomingCallToast`

## pseudocode

```c
const unsigned __int16 *WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::InternalGetRuntimeClassNameStatic(
        void)
{
  return L"WindowsInternal.ApplicationModel.Calls.IncomingCallToast";
}

```

## disassembly

```asm
0x180003dd0  lea     rax, ?RuntimeClass_WindowsInternal_ApplicationModel_Calls_IncomingCallToast@@3QBGB; "WindowsInternal.ApplicationModel.Calls."...
0x180003dd7  retn
```
