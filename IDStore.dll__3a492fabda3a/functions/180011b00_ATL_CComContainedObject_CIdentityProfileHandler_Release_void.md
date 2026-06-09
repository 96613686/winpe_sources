# ATL::CComContainedObject<CIdentityProfileHandler>::Release(void)

- ea: `0x180011b00`
- end: `0x180011b1a`
- name: `?Release@?$CComContainedObject@VCIdentityProfileHandler@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityProfileHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180011b00  sub     rsp, 28h
0x180011b04  mov     rcx, [rcx+8]
0x180011b08  mov     rax, [rcx]
0x180011b0b  mov     rax, [rax+10h]
0x180011b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b14  nop
0x180011b15  add     rsp, 28h
0x180011b19  retn
```
