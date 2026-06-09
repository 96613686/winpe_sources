# ATL::CComContainedObject<CIdentityProfileHandler>::AddRef(void)

- ea: `0x180010c20`
- end: `0x180010c3a`
- name: `?AddRef@?$CComContainedObject@VCIdentityProfileHandler@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityProfileHandler>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180010c20  sub     rsp, 28h
0x180010c24  mov     rcx, [rcx+8]
0x180010c28  mov     rax, [rcx]
0x180010c2b  mov     rax, [rax+8]
0x180010c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c34  nop
0x180010c35  add     rsp, 28h
0x180010c39  retn
```
