# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$6

- ea: `0x1400158f8`
- end: `0x140015904`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001e4c`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x1400158f8  lea     rcx, [rdx+60h]
0x1400158ff  jmp     ??1?$CComPtr@UIStandardCollectorAuthorizationService@@@ATL@@QEAA@XZ; ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(void)
```
