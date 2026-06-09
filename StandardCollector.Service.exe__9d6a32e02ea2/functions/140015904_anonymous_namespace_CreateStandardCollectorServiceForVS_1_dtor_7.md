# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$7

- ea: `0x140015904`
- end: `0x140015910`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001e4c`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x140015904  lea     rcx, [rdx+68h]
0x14001590b  jmp     ??1?$CComPtr@UIStandardCollectorAuthorizationService@@@ATL@@QEAA@XZ; ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(void)
```
