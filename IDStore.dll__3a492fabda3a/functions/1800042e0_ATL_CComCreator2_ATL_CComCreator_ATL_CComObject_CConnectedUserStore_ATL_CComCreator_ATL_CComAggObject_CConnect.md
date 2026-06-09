# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CConnectedUserStore>>,ATL::CComCreator<ATL::CComAggObject<CConnectedUserStore>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800042e0`
- end: `0x1800042ee`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCConnectedUserStore@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCConnectedUserStore@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004300`
- `0x180010d24`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CConnectedUserStore>>,ATL::CComCreator<ATL::CComAggObject<CConnectedUserStore>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CConnectedUserStore>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CConnectedUserStore>>::CreateInstance();
}

```

## disassembly

```asm
0x1800042e0  test    rcx, rcx
0x1800042e3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCConnectedUserStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CConnectedUserStore>>::CreateInstance(void *,_GUID const &,void * *)
0x1800042e9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCConnectedUserStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CConnectedUserStore>>::CreateInstance(void *,_GUID const &,void * *)
```
