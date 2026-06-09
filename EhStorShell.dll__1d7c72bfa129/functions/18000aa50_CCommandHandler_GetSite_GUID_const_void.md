# CCommandHandler::GetSite(_GUID const &,void * *)

- ea: `0x18000aa50`
- end: `0x18000aa71`
- name: `?GetSite@CCommandHandler@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000aa50`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CCommandHandler::GetSite(CCommandHandler *this, const struct _GUID *a2, void **a3)
{
  __int64 (__fastcall ***v3)(_QWORD, const struct _GUID *); // rcx

  *a3 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *))*((_QWORD *)this + 6);
  if ( v3 )
    return (**v3)(v3, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000aa50  mov     qword ptr [r8], 0
0x18000aa57  mov     rcx, [rcx+30h]
0x18000aa5b  test    rcx, rcx
0x18000aa5e  jz      short loc_18000AA6B
0x18000aa60  mov     rax, [rcx]
0x18000aa63  mov     rax, [rax]
0x18000aa66  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa6b  mov     eax, 80004005h
0x18000aa70  retn
```
