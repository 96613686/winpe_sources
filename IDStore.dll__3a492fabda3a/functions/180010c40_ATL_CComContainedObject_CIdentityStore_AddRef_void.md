# ATL::CComContainedObject<CIdentityStore>::AddRef(void)

- ea: `0x180010c40`
- end: `0x180010c5a`
- name: `?AddRef@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010c60`
- `0x180010c70`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityStore>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180010c40  sub     rsp, 28h
0x180010c44  mov     rcx, [rcx+18h]
0x180010c48  mov     rax, [rcx]
0x180010c4b  mov     rax, [rax+8]
0x180010c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c54  nop
0x180010c55  add     rsp, 28h
0x180010c59  retn
```
