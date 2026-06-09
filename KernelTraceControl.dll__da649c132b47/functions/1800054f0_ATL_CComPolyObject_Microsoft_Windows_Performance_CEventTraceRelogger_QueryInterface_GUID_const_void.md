# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800054f0`
- end: `0x180005554`
- name: `?QueryInterface@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800054f0`
- `0x180006a90`
- `0x180027910`

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
0x1800054f0  push    rbx
0x1800054f2  sub     rsp, 20h
0x1800054f6  xor     ebx, ebx
0x1800054f8  test    r8, r8
0x1800054fb  jnz     short loc_180005504
0x1800054fd  mov     eax, 80004003h
0x180005502  jmp     short loc_18000554E
0x180005504  mov     [r8], rbx
0x180005507  cmp     [rdx], ebx
0x180005509  jnz     short loc_180005534
0x18000550b  cmp     [rdx+4], ebx
0x18000550e  jnz     short loc_180005534
0x180005510  cmp     dword ptr [rdx+8], 0C0h
0x180005517  jnz     short loc_180005534
0x180005519  cmp     dword ptr [rdx+0Ch], 46000000h
0x180005520  jnz     short loc_180005534
0x180005522  mov     [r8], rcx
0x180005525  mov     rax, [rcx]
0x180005528  mov     rax, [rax+8]
0x18000552c  call    cs:__guard_dispatch_icall_fptr
0x180005532  jmp     short loc_18000554C
0x180005534  mov     r9, r8; void **
0x180005537  add     rcx, 10h; void *
0x18000553b  mov     r8, rdx; struct _GUID *
0x18000553e  lea     rdx, ?_entries@?1??_GetEntries@CEventTraceRelogger@Performance@Windows@Microsoft@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU67@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180005545  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000554a  mov     ebx, eax
0x18000554c  mov     eax, ebx
0x18000554e  add     rsp, 20h
0x180005552  pop     rbx
0x180005553  retn
```
