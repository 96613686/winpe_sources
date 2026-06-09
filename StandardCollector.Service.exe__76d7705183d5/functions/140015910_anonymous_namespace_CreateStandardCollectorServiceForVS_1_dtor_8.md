# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$8

- ea: `0x140015910`
- end: `0x14001591c`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001e4c`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x140015910  lea     rcx, [rdx+70h]
0x140015917  jmp     ??1?$CComPtr@UIStandardCollectorAuthorizationService@@@ATL@@QEAA@XZ; ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(void)
```
