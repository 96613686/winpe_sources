# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTieringEngineTaskHandler>>,ATL::CComCreator<ATL::CComAggObject<CTieringEngineTaskHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140002df0`
- end: `0x140002dfe`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCTieringEngineTaskHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002f58`
- `0x14000321c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTieringEngineTaskHandler>>,ATL::CComCreator<ATL::CComAggObject<CTieringEngineTaskHandler>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CTieringEngineTaskHandler>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CTieringEngineTaskHandler>>::CreateInstance();
}

```

## disassembly

```asm
0x140002df0  test    rcx, rcx
0x140002df3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCTieringEngineTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CTieringEngineTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x140002df9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CTieringEngineTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)
```
