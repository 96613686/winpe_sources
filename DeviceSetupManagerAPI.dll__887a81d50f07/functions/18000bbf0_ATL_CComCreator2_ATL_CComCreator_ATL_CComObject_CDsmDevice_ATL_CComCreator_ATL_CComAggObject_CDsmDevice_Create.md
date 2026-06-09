# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDsmDevice>>,ATL::CComCreator<ATL::CComAggObject<CDsmDevice>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000bbf0`
- end: `0x18000bbfe`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDsmDevice@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDsmDevice@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bc04`
- `0x18000bd94`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDsmDevice>>,ATL::CComCreator<ATL::CComAggObject<CDsmDevice>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDsmDevice>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CDsmDevice>>::CreateInstance();
}

```

## disassembly

```asm
0x18000bbf0  test    rcx, rcx
0x18000bbf3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDsmDevice@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDsmDevice>>::CreateInstance(void *,_GUID const &,void * *)
0x18000bbf9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDsmDevice@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDsmDevice>>::CreateInstance(void *,_GUID const &,void * *)
```
