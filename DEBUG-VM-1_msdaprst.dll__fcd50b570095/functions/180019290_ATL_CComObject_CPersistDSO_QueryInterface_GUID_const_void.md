# ATL::CComObject<CPersistDSO>::QueryInterface(_GUID const &,void * *)

- ea: `0x180019290`
- end: `0x1800192b0`
- name: `?QueryInterface@?$CComObject@VCPersistDSO@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `32`
- prototype: `__int64 __fastcall(struct CProviderDSO *, struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800192c0`
- `0x1800192d0`
- `0x1800192e0`
- `0x180019300`
- `0x180019320`
- `0x180019340`
- `0x180019360`
- `0x180019370`
- `0x180019380`

## callees

- `0x18002d0f4`

## pseudocode

```c
int __fastcall ATL::CComObject<CPersistDSO>::QueryInterface(struct CProviderDSO *a1, struct _GUID *a2, void **a3)
{
  return CProviderDSO::InternalQueryInterface(
           a1,
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPersistDSO::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180019290  sub     rsp, 38h
0x180019294  mov     [rsp+38h+var_18], r8; void **
0x180019299  mov     r9, rdx; struct _GUID *
0x18001929c  lea     r8, ?_entries@?1??_GetEntries@CPersistDSO@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800192a3  mov     rdx, rcx; struct CProviderDSO *
0x1800192a6  call    ?InternalQueryInterface@CProviderDSO@@IEAAJPEAV1@PEBU_ATL_INTMAP_ENTRY@ATL@@AEBU_GUID@@PEAPEAX@Z; CProviderDSO::InternalQueryInterface(CProviderDSO *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800192ab  add     rsp, 38h
0x1800192af  retn
```
