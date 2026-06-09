# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIdentityProfileHandler>>,ATL::CComCreator<ATL::CComAggObject<CIdentityProfileHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007f40`
- end: `0x180007f4e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCIdentityProfileHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCIdentityProfileHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007b20`
- `0x180010e78`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIdentityProfileHandler>>,ATL::CComCreator<ATL::CComAggObject<CIdentityProfileHandler>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CIdentityProfileHandler>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CIdentityProfileHandler>>::CreateInstance();
}

```

## disassembly

```asm
0x180007f40  test    rcx, rcx
0x180007f43  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCIdentityProfileHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIdentityProfileHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x180007f49  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCIdentityProfileHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CIdentityProfileHandler>>::CreateInstance(void *,_GUID const &,void * *)
```
