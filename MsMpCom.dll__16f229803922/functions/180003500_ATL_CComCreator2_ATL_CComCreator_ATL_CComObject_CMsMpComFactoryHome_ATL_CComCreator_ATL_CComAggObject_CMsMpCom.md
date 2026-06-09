# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMsMpComFactoryHome>>,ATL::CComCreator<ATL::CComAggObject<CMsMpComFactoryHome>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003500`
- end: `0x18000350e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMsMpComFactoryHome@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003514`
- `0x180003668`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMsMpComFactoryHome>>,ATL::CComCreator<ATL::CComAggObject<CMsMpComFactoryHome>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMsMpComFactoryHome>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMsMpComFactoryHome>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180003500  test    rcx, rcx
0x180003503  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMsMpComFactoryHome@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMsMpComFactoryHome>>::CreateInstance(void *,_GUID const &,void * *)
0x180003509  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMsMpComFactoryHome>>::CreateInstance(void *,_GUID const &,void * *)
```
