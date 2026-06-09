# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPimcSurrogate>>,ATL::CComCreator<ATL::CComAggObject<CPimcSurrogate>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000c4e0`
- end: `0x18000c4ee`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPimcSurrogate@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPimcSurrogate@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c4f0`
- `0x18000c5f8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPimcSurrogate>>,ATL::CComCreator<ATL::CComAggObject<CPimcSurrogate>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CPimcSurrogate>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CPimcSurrogate>>::CreateInstance(0, (const struct _GUID *)a2, (void **)a3);
}

```

## disassembly

```asm
0x18000c4e0  test    rcx, rcx
0x18000c4e3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPimcSurrogate@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPimcSurrogate>>::CreateInstance(void *,_GUID const &,void * *)
0x18000c4e9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPimcSurrogate@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPimcSurrogate>>::CreateInstance(void *,_GUID const &,void * *)
```
