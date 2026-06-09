# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDsmControl>>,ATL::CComCreator<ATL::CComAggObject<CDsmControl>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a120`
- end: `0x18000a12e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDsmControl@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDsmControl@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a134`
- `0x18000a220`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDsmControl>>,ATL::CComCreator<ATL::CComAggObject<CDsmControl>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDsmControl>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CDsmControl>>::CreateInstance();
}

```

## disassembly

```asm
0x18000a120  test    rcx, rcx
0x18000a123  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDsmControl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDsmControl>>::CreateInstance(void *,_GUID const &,void * *)
0x18000a129  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDsmControl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDsmControl>>::CreateInstance(void *,_GUID const &,void * *)
```
