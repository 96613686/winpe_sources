# ATL::CComAggObject<CAxInstaller>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000d730`
- end: `0x18000d78a`
- name: `?QueryInterface@?$CComAggObject@VCAxInstaller@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009e30`
- `0x18000c7d0`
- `0x18000d730`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAxInstaller>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  void **v6; // r8
  __int64 v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = (void *)v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)ATL::AtlInternalQueryInterface(
                           (void *)(v7 + 24),
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAxInstaller::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d730  push    rbx
0x18000d732  sub     rsp, 20h
0x18000d736  xor     ebx, ebx
0x18000d738  mov     r9, rcx
0x18000d73b  test    r8, r8
0x18000d73e  jnz     short loc_18000D747
0x18000d740  mov     eax, 80004003h
0x18000d745  jmp     short loc_18000D784
0x18000d747  mov     rcx, rdx; struct _GUID *
0x18000d74a  mov     [r8], rbx
0x18000d74d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000d752  test    eax, eax
0x18000d754  jz      short loc_18000D76A
0x18000d756  mov     [r8], r9
0x18000d759  mov     rcx, r9
0x18000d75c  mov     rax, [r9]
0x18000d75f  mov     rax, [rax+8]
0x18000d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d768  jmp     short loc_18000D782
0x18000d76a  lea     rcx, [r9+18h]; void *
0x18000d76e  mov     r9, r8; void **
0x18000d771  mov     r8, rdx; struct _GUID *
0x18000d774  lea     rdx, ?_entries@?1??_GetEntries@CAxInstaller@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000d77b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000d780  mov     ebx, eax
0x18000d782  mov     eax, ebx
0x18000d784  add     rsp, 20h
0x18000d788  pop     rbx
0x18000d789  retn
```
