# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005cf0`
- end: `0x180005cfe`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005d04`
- `0x180005e14`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180005cf0  test    rcx, rcx
0x180005cf3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>>::CreateInstance(void *,_GUID const &,void * *)
0x180005cf9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>>::CreateInstance(void *,_GUID const &,void * *)
```
