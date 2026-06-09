# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::InternalGetRuntimeClassName(void)

- ea: `0x180005360`
- end: `0x180005368`
- name: `?InternalGetRuntimeClassName@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180005360`: `Windows.Internal.StateRepository.AppInfoFactoryBroker`

## pseudocode

```c
const unsigned __int16 *Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::InternalGetRuntimeClassName(
        void)
{
  return L"Windows.Internal.StateRepository.AppInfoFactoryBroker";
}

```

## disassembly

```asm
0x180005360  lea     rax, ?RuntimeClass_Windows_Internal_StateRepository_AppInfoFactoryBroker@@3QBGB; "Windows.Internal.StateRepository.AppInf"...
0x180005367  retn
```
