# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPimcManager>>,ATL::CComCreator<ATL::CComAggObject<CPimcManager>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001970`
- end: `0x18000197e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPimcManager@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPimcManager@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001b50`
- `0x180001cac`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPimcManager>>,ATL::CComCreator<ATL::CComAggObject<CPimcManager>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CPimcManager>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CPimcManager>>::CreateInstance(0, (const struct _GUID *)a2, (void **)a3);
}

```

## disassembly

```asm
0x180001970  test    rcx, rcx
0x180001973  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPimcManager@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPimcManager>>::CreateInstance(void *,_GUID const &,void * *)
0x180001979  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPimcManager@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPimcManager>>::CreateInstance(void *,_GUID const &,void * *)
```
