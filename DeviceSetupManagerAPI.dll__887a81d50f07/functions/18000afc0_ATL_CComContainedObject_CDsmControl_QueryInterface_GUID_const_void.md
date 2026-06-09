# ATL::CComContainedObject<CDsmControl>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000afc0`
- end: `0x18000afd9`
- name: `?QueryInterface@?$CComContainedObject@VCDsmControl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDsmControl>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000afc0  sub     rsp, 28h
0x18000afc4  mov     rcx, [rcx+8]
0x18000afc8  mov     rax, [rcx]
0x18000afcb  mov     rax, [rax]
0x18000afce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afd3  nop
0x18000afd4  add     rsp, 28h
0x18000afd8  retn
```
