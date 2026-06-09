# ATL::CComAggObject<CDfsShell>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800050f0`
- end: `0x180005153`
- name: `?QueryInterface@?$CComAggObject@VCDfsShell@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004b24`
- `0x1800050f0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDfsShell>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDfsShell::_GetEntries'::`2'::_entries,
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
0x1800050f0  push    rbx
0x1800050f2  sub     rsp, 20h
0x1800050f6  xor     ebx, ebx
0x1800050f8  test    r8, r8
0x1800050fb  jnz     short loc_180005104
0x1800050fd  mov     eax, 80004003h
0x180005102  jmp     short loc_18000514D
0x180005104  mov     [r8], rbx
0x180005107  cmp     [rdx], ebx
0x180005109  jnz     short loc_180005133
0x18000510b  cmp     [rdx+4], ebx
0x18000510e  jnz     short loc_180005133
0x180005110  cmp     dword ptr [rdx+8], 0C0h
0x180005117  jnz     short loc_180005133
0x180005119  cmp     dword ptr [rdx+0Ch], 46000000h
0x180005120  jnz     short loc_180005133
0x180005122  mov     [r8], rcx
0x180005125  mov     rax, [rcx]
0x180005128  mov     rax, [rax+8]
0x18000512c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005131  jmp     short loc_18000514B
0x180005133  mov     r9, r8; void **
0x180005136  add     rcx, 10h; void *
0x18000513a  mov     r8, rdx; struct _GUID *
0x18000513d  lea     rdx, ?_entries@?1??_GetEntries@CDfsShell@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180005144  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005149  mov     ebx, eax
0x18000514b  mov     eax, ebx
0x18000514d  add     rsp, 20h
0x180005151  pop     rbx
0x180005152  retn
```
