# __anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools_::_1_::dtor$0

- ea: `0x140015970`
- end: `0x14001597c`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001e4c`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140015970  lea     rcx, [rdx+30h]
0x140015977  jmp     ??1?$CComPtr@UIStandardCollectorAuthorizationService@@@ATL@@QEAA@XZ; ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(void)
```
