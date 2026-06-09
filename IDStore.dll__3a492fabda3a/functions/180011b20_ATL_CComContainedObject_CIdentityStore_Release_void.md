# ATL::CComContainedObject<CIdentityStore>::Release(void)

- ea: `0x180011b20`
- end: `0x180011b3a`
- name: `?Release@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011b40`
- `0x180011b50`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityStore>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180011b20  sub     rsp, 28h
0x180011b24  mov     rcx, [rcx+18h]
0x180011b28  mov     rax, [rcx]
0x180011b2b  mov     rax, [rax+10h]
0x180011b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b34  nop
0x180011b35  add     rsp, 28h
0x180011b39  retn
```
