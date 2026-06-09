# ATL::CComAggObject<MetadataPackageSource>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011b40`
- end: `0x180011ba3`
- name: `?QueryInterface@?$CComAggObject@VMetadataPackageSource@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800119e8`
- `0x180011b40`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<MetadataPackageSource>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`MetadataPackageSource::_GetEntries'::`2'::_entries,
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
0x180011b40  push    rbx
0x180011b42  sub     rsp, 20h
0x180011b46  xor     ebx, ebx
0x180011b48  test    r8, r8
0x180011b4b  jnz     short loc_180011B54
0x180011b4d  mov     eax, 80004003h
0x180011b52  jmp     short loc_180011B9D
0x180011b54  mov     [r8], rbx
0x180011b57  cmp     [rdx], ebx
0x180011b59  jnz     short loc_180011B83
0x180011b5b  cmp     [rdx+4], ebx
0x180011b5e  jnz     short loc_180011B83
0x180011b60  cmp     dword ptr [rdx+8], 0C0h
0x180011b67  jnz     short loc_180011B83
0x180011b69  cmp     dword ptr [rdx+0Ch], 46000000h
0x180011b70  jnz     short loc_180011B83
0x180011b72  mov     [r8], rcx
0x180011b75  mov     rax, [rcx]
0x180011b78  mov     rax, [rax+8]
0x180011b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b81  jmp     short loc_180011B9B
0x180011b83  mov     r9, r8; void **
0x180011b86  add     rcx, 18h; void *
0x180011b8a  mov     r8, rdx; struct _GUID *
0x180011b8d  lea     rdx, ?_entries@?1??_GetEntries@MetadataPackageSource@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180011b94  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180011b99  mov     ebx, eax
0x180011b9b  mov     eax, ebx
0x180011b9d  add     rsp, 20h
0x180011ba1  pop     rbx
0x180011ba2  retn
```
