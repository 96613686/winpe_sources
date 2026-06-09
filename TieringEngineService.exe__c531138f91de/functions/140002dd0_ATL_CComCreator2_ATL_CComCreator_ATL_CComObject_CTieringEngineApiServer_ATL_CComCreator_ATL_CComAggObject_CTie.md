# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTieringEngineApiServer>>,ATL::CComCreator<ATL::CComAggObject<CTieringEngineApiServer>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140002dd0`
- end: `0x140002dde`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCTieringEngineApiServer@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCTieringEngineApiServer@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002e04`
- `0x1400030b4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTieringEngineApiServer>>,ATL::CComCreator<ATL::CComAggObject<CTieringEngineApiServer>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CTieringEngineApiServer>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CTieringEngineApiServer>>::CreateInstance();
}

```

## disassembly

```asm
0x140002dd0  test    rcx, rcx
0x140002dd3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCTieringEngineApiServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CTieringEngineApiServer>>::CreateInstance(void *,_GUID const &,void * *)
0x140002dd9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCTieringEngineApiServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CTieringEngineApiServer>>::CreateInstance(void *,_GUID const &,void * *)
```
