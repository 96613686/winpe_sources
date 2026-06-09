# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::InternalGetRuntimeClassNameStatic(void)

- ea: `0x180003de0`
- end: `0x180003de8`
- name: `?InternalGetRuntimeClassNameStatic@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## string_xrefs

- `0x180003de0`: `WindowsInternal.ApplicationModel.Calls.ServiceUiToast`

## pseudocode

```c
const unsigned __int16 *WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::InternalGetRuntimeClassNameStatic(
        void)
{
  return L"WindowsInternal.ApplicationModel.Calls.ServiceUiToast";
}

```

## disassembly

```asm
0x180003de0  lea     rax, ?RuntimeClass_WindowsInternal_ApplicationModel_Calls_ServiceUiToast@@3QBGB; "WindowsInternal.ApplicationModel.Calls."...
0x180003de7  retn
```
