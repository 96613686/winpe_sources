# ATL::CComContainedObject<CServiceProvider>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007690`
- end: `0x18000769f`
- name: `?QueryInterface@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800076b0`
- `0x1800076c0`
- `0x1800076d0`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 32))(*(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x180007690  mov     rcx, [rcx+20h]
0x180007694  mov     rax, [rcx]
0x180007697  mov     rax, [rax]
0x18000769a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
