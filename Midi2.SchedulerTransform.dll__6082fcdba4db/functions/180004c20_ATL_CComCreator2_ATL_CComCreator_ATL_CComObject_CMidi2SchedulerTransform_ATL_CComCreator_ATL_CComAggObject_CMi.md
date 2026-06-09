# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2SchedulerTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2SchedulerTransform>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004c20`
- end: `0x180004c2e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMidi2SchedulerTransform@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004c34`
- `0x180004d44`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2SchedulerTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2SchedulerTransform>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMidi2SchedulerTransform>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMidi2SchedulerTransform>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180004c20  test    rcx, rcx
0x180004c23  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2SchedulerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMidi2SchedulerTransform>>::CreateInstance(void *,_GUID const &,void * *)
0x180004c29  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMidi2SchedulerTransform>>::CreateInstance(void *,_GUID const &,void * *)
```
