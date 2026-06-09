# ATL::CComContainedObject<CMigrationPlugin>::AddRef(void)

- ea: `0x18000d150`
- end: `0x18000d173`
- name: `?AddRef@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d180`
- `0x18000d190`
- `0x18000d1a0`
- `0x18000d1b0`
- `0x18000d1c0`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMigrationPlugin>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 8LL))(*(_QWORD *)(a1 + 48));
}

```

## disassembly

```asm
0x18000d150  sub     rsp, 38h
0x18000d154  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000d15d  mov     rcx, [rcx+30h]
0x18000d161  mov     rax, [rcx]
0x18000d164  mov     rax, [rax+8]
0x18000d168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d16d  nop
0x18000d16e  add     rsp, 38h
0x18000d172  retn
```
