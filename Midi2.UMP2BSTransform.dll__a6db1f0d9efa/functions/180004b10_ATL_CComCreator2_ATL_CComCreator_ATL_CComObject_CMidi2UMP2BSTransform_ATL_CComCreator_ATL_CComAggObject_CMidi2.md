# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2UMP2BSTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2UMP2BSTransform>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004b10`
- end: `0x180004b1e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004b24`
- `0x180004c34`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2UMP2BSTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2UMP2BSTransform>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMidi2UMP2BSTransform>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMidi2UMP2BSTransform>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180004b10  test    rcx, rcx
0x180004b13  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMidi2UMP2BSTransform>>::CreateInstance(void *,_GUID const &,void * *)
0x180004b19  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMidi2UMP2BSTransform>>::CreateInstance(void *,_GUID const &,void * *)
```
