# ATL::CComAggObject<CDsmDevice>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c220`
- end: `0x18000c283`
- name: `?QueryInterface@?$CComAggObject@VCDsmDevice@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800098f0`
- `0x18000c220`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDsmDevice>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDsmDevice::_GetEntries'::`2'::_entries,
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
0x18000c220  push    rbx
0x18000c222  sub     rsp, 20h
0x18000c226  xor     ebx, ebx
0x18000c228  test    r8, r8
0x18000c22b  jnz     short loc_18000C234
0x18000c22d  mov     eax, 80004003h
0x18000c232  jmp     short loc_18000C27D
0x18000c234  mov     [r8], rbx
0x18000c237  cmp     [rdx], ebx
0x18000c239  jnz     short loc_18000C263
0x18000c23b  cmp     [rdx+4], ebx
0x18000c23e  jnz     short loc_18000C263
0x18000c240  cmp     dword ptr [rdx+8], 0C0h
0x18000c247  jnz     short loc_18000C263
0x18000c249  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000c250  jnz     short loc_18000C263
0x18000c252  mov     [r8], rcx
0x18000c255  mov     rax, [rcx]
0x18000c258  mov     rax, [rax+8]
0x18000c25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c261  jmp     short loc_18000C27B
0x18000c263  mov     r9, r8; void **
0x18000c266  add     rcx, 10h; void *
0x18000c26a  mov     r8, rdx; struct _GUID *
0x18000c26d  lea     rdx, ?_entries@?1??_GetEntries@CDsmDevice@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000c274  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000c279  mov     ebx, eax
0x18000c27b  mov     eax, ebx
0x18000c27d  add     rsp, 20h
0x18000c281  pop     rbx
0x18000c282  retn
```
