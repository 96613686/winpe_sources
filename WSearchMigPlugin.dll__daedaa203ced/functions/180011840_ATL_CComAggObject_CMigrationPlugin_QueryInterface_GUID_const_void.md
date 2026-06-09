# ATL::CComAggObject<CMigrationPlugin>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011840`
- end: `0x1800118a3`
- name: `?QueryInterface@?$CComAggObject@VCMigrationPlugin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001013c`
- `0x180011840`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMigrationPlugin>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMigrationPlugin::_GetEntries'::`2'::_entries,
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
0x180011840  push    rbx
0x180011842  sub     rsp, 20h
0x180011846  xor     ebx, ebx
0x180011848  test    r8, r8
0x18001184b  jnz     short loc_180011854
0x18001184d  mov     eax, 80004003h
0x180011852  jmp     short loc_18001189D
0x180011854  mov     [r8], rbx
0x180011857  cmp     [rdx], ebx
0x180011859  jnz     short loc_180011883
0x18001185b  cmp     [rdx+4], ebx
0x18001185e  jnz     short loc_180011883
0x180011860  cmp     dword ptr [rdx+8], 0C0h
0x180011867  jnz     short loc_180011883
0x180011869  cmp     dword ptr [rdx+0Ch], 46000000h
0x180011870  jnz     short loc_180011883
0x180011872  mov     [r8], rcx
0x180011875  mov     rax, [rcx]
0x180011878  mov     rax, [rax+8]
0x18001187c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011881  jmp     short loc_18001189B
0x180011883  mov     r9, r8; void **
0x180011886  add     rcx, 18h; void *
0x18001188a  mov     r8, rdx; struct _GUID *
0x18001188d  lea     rdx, ?_entries@?1??_GetEntries@CMigrationPlugin@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180011894  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180011899  mov     ebx, eax
0x18001189b  mov     eax, ebx
0x18001189d  add     rsp, 20h
0x1800118a1  pop     rbx
0x1800118a2  retn
```
