# ATL::CComContainedObject<CMigrationPlugin>::Release(void)

- ea: `0x180011eb0`
- end: `0x180011ed3`
- name: `?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011ee0`
- `0x180011ef0`
- `0x180011f00`
- `0x180011f10`
- `0x180011f20`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMigrationPlugin>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 16LL))(*(_QWORD *)(a1 + 48));
}

```

## disassembly

```asm
0x180011eb0  sub     rsp, 38h
0x180011eb4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180011ebd  mov     rcx, [rcx+30h]
0x180011ec1  mov     rax, [rcx]
0x180011ec4  mov     rax, [rax+10h]
0x180011ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ecd  nop
0x180011ece  add     rsp, 38h
0x180011ed2  retn
```
