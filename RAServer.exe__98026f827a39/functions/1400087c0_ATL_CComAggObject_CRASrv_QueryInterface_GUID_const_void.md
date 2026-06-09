# ATL::CComAggObject<CRASrv>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400087c0`
- end: `0x14000881a`
- name: `?QueryInterface@?$CComAggObject@VCRASrv@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140004db8`
- `0x140007328`
- `0x1400087c0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRASrv>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  char **v6; // r8
  char *v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = v7;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)ATL::AtlInternalQueryInterface(
                           v7 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRASrv::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x1400087c0  push    rbx
0x1400087c2  sub     rsp, 20h
0x1400087c6  xor     ebx, ebx
0x1400087c8  mov     r9, rcx
0x1400087cb  test    r8, r8
0x1400087ce  jnz     short loc_1400087D7
0x1400087d0  mov     eax, 80004003h
0x1400087d5  jmp     short loc_140008814
0x1400087d7  mov     rcx, rdx; struct _GUID *
0x1400087da  mov     [r8], rbx
0x1400087dd  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1400087e2  test    eax, eax
0x1400087e4  jz      short loc_1400087FA
0x1400087e6  mov     [r8], r9
0x1400087e9  mov     rcx, r9
0x1400087ec  mov     rax, [r9]
0x1400087ef  mov     rax, [rax+8]
0x1400087f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087f8  jmp     short loc_140008812
0x1400087fa  lea     rcx, [r9+18h]; void *
0x1400087fe  mov     r9, r8; void **
0x140008801  mov     r8, rdx; struct _GUID *
0x140008804  lea     rdx, ?_entries@?1??_GetEntries@CRASrv@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000880b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x140008810  mov     ebx, eax
0x140008812  mov     eax, ebx
0x140008814  add     rsp, 20h
0x140008818  pop     rbx
0x140008819  retn
```
