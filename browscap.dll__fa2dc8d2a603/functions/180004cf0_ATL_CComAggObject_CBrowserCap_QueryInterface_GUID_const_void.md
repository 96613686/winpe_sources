# ATL::CComAggObject<CBrowserCap>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004cf0`
- end: `0x180004d53`
- name: `?QueryInterface@?$CComAggObject@VCBrowserCap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800044a8`
- `0x180004cf0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CBrowserCap>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CBrowserCap::_GetEntries'::`2'::_entries,
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
0x180004cf0  push    rbx
0x180004cf2  sub     rsp, 20h
0x180004cf6  xor     ebx, ebx
0x180004cf8  test    r8, r8
0x180004cfb  jnz     short loc_180004D04
0x180004cfd  mov     eax, 80004003h
0x180004d02  jmp     short loc_180004D4D
0x180004d04  mov     [r8], rbx
0x180004d07  cmp     [rdx], ebx
0x180004d09  jnz     short loc_180004D33
0x180004d0b  cmp     [rdx+4], ebx
0x180004d0e  jnz     short loc_180004D33
0x180004d10  cmp     dword ptr [rdx+8], 0C0h
0x180004d17  jnz     short loc_180004D33
0x180004d19  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004d20  jnz     short loc_180004D33
0x180004d22  mov     [r8], rcx
0x180004d25  mov     rax, [rcx]
0x180004d28  mov     rax, [rax+8]
0x180004d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d31  jmp     short loc_180004D4B
0x180004d33  mov     r9, r8; void **
0x180004d36  add     rcx, 18h; void *
0x180004d3a  mov     r8, rdx; struct _GUID *
0x180004d3d  lea     rdx, ?_entries@?1??_GetEntries@CBrowserCap@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004d44  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004d49  mov     ebx, eax
0x180004d4b  mov     eax, ebx
0x180004d4d  add     rsp, 20h
0x180004d51  pop     rbx
0x180004d52  retn
```
