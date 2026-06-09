# ATL::CComContainedObject<CMigrationPlugin>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800118b0`
- end: `0x1800118d2`
- name: `?QueryInterface@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800118e0`
- `0x1800118f0`
- `0x180011900`
- `0x180011910`
- `0x180011920`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMigrationPlugin>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 48))(*(_QWORD *)(a1 + 48));
}

```

## disassembly

```asm
0x1800118b0  sub     rsp, 38h
0x1800118b4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800118bd  mov     rcx, [rcx+30h]
0x1800118c1  mov     rax, [rcx]
0x1800118c4  mov     rax, [rax]
0x1800118c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118cc  nop
0x1800118cd  add     rsp, 38h
0x1800118d1  retn
```
