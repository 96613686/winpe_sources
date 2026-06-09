# ATL::CComAggObject<CALACDecMFT>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005ac0`
- end: `0x180005b23`
- name: `?QueryInterface@?$CComAggObject@VCALACDecMFT@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800054d4`
- `0x180005ac0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CALACDecMFT>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CALACDecMFT::_GetEntries'::`2'::_entries,
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
0x180005ac0  push    rbx
0x180005ac2  sub     rsp, 20h
0x180005ac6  xor     ebx, ebx
0x180005ac8  test    r8, r8
0x180005acb  jnz     short loc_180005AD4
0x180005acd  mov     eax, 80004003h
0x180005ad2  jmp     short loc_180005B1D
0x180005ad4  mov     [r8], rbx
0x180005ad7  cmp     [rdx], ebx
0x180005ad9  jnz     short loc_180005B03
0x180005adb  cmp     [rdx+4], ebx
0x180005ade  jnz     short loc_180005B03
0x180005ae0  cmp     dword ptr [rdx+8], 0C0h
0x180005ae7  jnz     short loc_180005B03
0x180005ae9  cmp     dword ptr [rdx+0Ch], 46000000h
0x180005af0  jnz     short loc_180005B03
0x180005af2  mov     [r8], rcx
0x180005af5  mov     rax, [rcx]
0x180005af8  mov     rax, [rax+8]
0x180005afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b01  jmp     short loc_180005B1B
0x180005b03  mov     r9, r8; void **
0x180005b06  add     rcx, 18h; void *
0x180005b0a  mov     r8, rdx; struct _GUID *
0x180005b0d  lea     rdx, ?_entries@?1??_GetEntries@CALACDecMFT@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180005b14  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005b19  mov     ebx, eax
0x180005b1b  mov     eax, ebx
0x180005b1d  add     rsp, 20h
0x180005b21  pop     rbx
0x180005b22  retn
```
