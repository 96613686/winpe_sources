# ATL::CComContainedObject<CTieringEngineTaskHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x140003b70`
- end: `0x140003b89`
- name: `?QueryInterface@?$CComContainedObject@VCTieringEngineTaskHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CTieringEngineTaskHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x140003b70  sub     rsp, 28h
0x140003b74  mov     rcx, [rcx+8]
0x140003b78  mov     rax, [rcx]
0x140003b7b  mov     rax, [rax]
0x140003b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b83  nop
0x140003b84  add     rsp, 28h
0x140003b88  retn
```
