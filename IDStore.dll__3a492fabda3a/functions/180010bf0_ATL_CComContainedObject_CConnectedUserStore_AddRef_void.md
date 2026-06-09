# ATL::CComContainedObject<CConnectedUserStore>::AddRef(void)

- ea: `0x180010bf0`
- end: `0x180010c0a`
- name: `?AddRef@?$CComContainedObject@VCConnectedUserStore@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010c10`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CConnectedUserStore>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180010bf0  sub     rsp, 28h
0x180010bf4  mov     rcx, [rcx+10h]
0x180010bf8  mov     rax, [rcx]
0x180010bfb  mov     rax, [rax+8]
0x180010bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c04  nop
0x180010c05  add     rsp, 28h
0x180010c09  retn
```
