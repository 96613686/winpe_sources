# ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004520`
- end: `0x180004583`
- name: `?QueryInterface@?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800043c4`
- `0x180004520`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::QueryInterface(
        char *a1,
        __int64 a2,
        char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`HtmlDocForParsingSiteUnmarshaller::_GetEntries'::`2'::_entries,
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
0x180004520  push    rbx
0x180004522  sub     rsp, 20h
0x180004526  xor     ebx, ebx
0x180004528  test    r8, r8
0x18000452b  jnz     short loc_180004534
0x18000452d  mov     eax, 80004003h
0x180004532  jmp     short loc_18000457D
0x180004534  mov     [r8], rbx
0x180004537  cmp     [rdx], ebx
0x180004539  jnz     short loc_180004563
0x18000453b  cmp     [rdx+4], ebx
0x18000453e  jnz     short loc_180004563
0x180004540  cmp     dword ptr [rdx+8], 0C0h
0x180004547  jnz     short loc_180004563
0x180004549  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004550  jnz     short loc_180004563
0x180004552  mov     [r8], rcx
0x180004555  mov     rax, [rcx]
0x180004558  mov     rax, [rax+8]
0x18000455c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004561  jmp     short loc_18000457B
0x180004563  mov     r9, r8; void **
0x180004566  add     rcx, 18h; void *
0x18000456a  mov     r8, rdx; struct _GUID *
0x18000456d  lea     rdx, ?_entries@?1??_GetEntries@HtmlDocForParsingSiteUnmarshaller@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004574  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004579  mov     ebx, eax
0x18000457b  mov     eax, ebx
0x18000457d  add     rsp, 20h
0x180004581  pop     rbx
0x180004582  retn
```
