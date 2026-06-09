# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007920`
- end: `0x180007983`
- name: `?QueryInterface@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002fac`
- `0x180007920`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(
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
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`Microsoft::Windows::Performance::CEventTraceRelogger::_GetEntries'::`2'::_entries,
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
0x180007920  push    rbx
0x180007922  sub     rsp, 20h
0x180007926  xor     ebx, ebx
0x180007928  test    r8, r8
0x18000792b  jnz     short loc_180007934
0x18000792d  mov     eax, 80004003h
0x180007932  jmp     short loc_18000797D
0x180007934  mov     [r8], rbx
0x180007937  cmp     [rdx], ebx
0x180007939  jnz     short loc_180007963
0x18000793b  cmp     [rdx+4], ebx
0x18000793e  jnz     short loc_180007963
0x180007940  cmp     dword ptr [rdx+8], 0C0h
0x180007947  jnz     short loc_180007963
0x180007949  cmp     dword ptr [rdx+0Ch], 46000000h
0x180007950  jnz     short loc_180007963
0x180007952  mov     [r8], rcx
0x180007955  mov     rax, [rcx]
0x180007958  mov     rax, [rax+8]
0x18000795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007961  jmp     short loc_18000797B
0x180007963  mov     r9, r8; void **
0x180007966  add     rcx, 10h; void *
0x18000796a  mov     r8, rdx; struct _GUID *
0x18000796d  lea     rdx, ?_entries@?1??_GetEntries@CEventTraceRelogger@Performance@Windows@Microsoft@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU67@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180007974  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180007979  mov     ebx, eax
0x18000797b  mov     eax, ebx
0x18000797d  add     rsp, 20h
0x180007981  pop     rbx
0x180007982  retn
```
