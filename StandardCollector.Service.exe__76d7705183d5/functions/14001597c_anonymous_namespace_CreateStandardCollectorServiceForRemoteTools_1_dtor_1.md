# __anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools_::_1_::dtor$1

- ea: `0x14001597c`
- end: `0x140015988`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001e4c`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x14001597c  lea     rcx, [rdx+38h]
0x140015983  jmp     ??1?$CComPtr@UIStandardCollectorAuthorizationService@@@ATL@@QEAA@XZ; ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(void)
```
