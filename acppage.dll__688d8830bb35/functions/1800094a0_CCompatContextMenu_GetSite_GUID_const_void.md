# CCompatContextMenu::GetSite(_GUID const &,void * *)

- ea: `0x1800094a0`
- end: `0x1800094c4`
- name: `?GetSite@CCompatContextMenu@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `36`
- prototype: `__int64 __fastcall(CCompatContextMenu *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800094a0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CCompatContextMenu::GetSite(CCompatContextMenu *this, const struct _GUID *a2, void **a3)
{
  __int64 (__fastcall ***v3)(_QWORD, const struct _GUID *); // rcx

  *a3 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *))*((_QWORD *)this + 74);
  if ( v3 )
    return (**v3)(v3, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800094a0  mov     qword ptr [r8], 0
0x1800094a7  mov     rcx, [rcx+250h]
0x1800094ae  test    rcx, rcx
0x1800094b1  jz      short loc_1800094BE
0x1800094b3  mov     rax, [rcx]
0x1800094b6  mov     rax, [rax]
0x1800094b9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800094be  mov     eax, 80004005h
0x1800094c3  retn
```
