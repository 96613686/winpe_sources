# [thunk]:ATL::CComContainedObject<CServiceProvider>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800076b0`
- end: `0x1800076b9`
- name: `?QueryInterface@?$CComContainedObject@VCServiceProvider@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007690`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CServiceProvider>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800076b0  sub     rcx, 8
0x1800076b4  jmp     ?QueryInterface@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CServiceProvider>::QueryInterface(_GUID const &,void * *)
```
