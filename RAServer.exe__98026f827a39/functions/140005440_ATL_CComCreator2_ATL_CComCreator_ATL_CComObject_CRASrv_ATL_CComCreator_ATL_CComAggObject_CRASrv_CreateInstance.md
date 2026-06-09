# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRASrv>>,ATL::CComCreator<ATL::CComAggObject<CRASrv>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005440`
- end: `0x14000544e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRASrv@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRASrv@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005488`
- `0x140005818`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRASrv>>,ATL::CComCreator<ATL::CComAggObject<CRASrv>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CRASrv>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CRASrv>>::CreateInstance();
}

```

## disassembly

```asm
0x140005440  test    rcx, rcx
0x140005443  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCRASrv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CRASrv>>::CreateInstance(void *,_GUID const &,void * *)
0x140005449  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCRASrv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CRASrv>>::CreateInstance(void *,_GUID const &,void * *)
```
