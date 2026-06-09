# ATL::CComAggObject<COpusDecMFT>::QueryInterface(_GUID const &,void * *)

- ea: `0x180020e10`
- end: `0x180020e73`
- name: `?QueryInterface@?$CComAggObject@VCOpusDecMFT@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180020824`
- `0x180020e10`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<COpusDecMFT>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`COpusDecMFT::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180020e10  push    rbx
0x180020e12  sub     rsp, 20h
0x180020e16  xor     ebx, ebx
0x180020e18  test    r8, r8
0x180020e1b  jnz     short loc_180020E24
0x180020e1d  mov     eax, 80004003h
0x180020e22  jmp     short loc_180020E6D
0x180020e24  mov     [r8], rbx
0x180020e27  cmp     [rdx], ebx
0x180020e29  jnz     short loc_180020E53
0x180020e2b  cmp     [rdx+4], ebx
0x180020e2e  jnz     short loc_180020E53
0x180020e30  cmp     dword ptr [rdx+8], 0C0h
0x180020e37  jnz     short loc_180020E53
0x180020e39  cmp     dword ptr [rdx+0Ch], 46000000h
0x180020e40  jnz     short loc_180020E53
0x180020e42  mov     [r8], rcx
0x180020e45  mov     rax, [rcx]
0x180020e48  mov     rax, [rax+8]
0x180020e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e51  jmp     short loc_180020E6B
0x180020e53  mov     r9, r8; void **
0x180020e56  add     rcx, 18h; void *
0x180020e5a  mov     r8, rdx; struct _GUID *
0x180020e5d  lea     rdx, ?_entries@?1??_GetEntries@COpusDecMFT@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180020e64  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180020e69  mov     ebx, eax
0x180020e6b  mov     eax, ebx
0x180020e6d  add     rsp, 20h
0x180020e71  pop     rbx
0x180020e72  retn
```
