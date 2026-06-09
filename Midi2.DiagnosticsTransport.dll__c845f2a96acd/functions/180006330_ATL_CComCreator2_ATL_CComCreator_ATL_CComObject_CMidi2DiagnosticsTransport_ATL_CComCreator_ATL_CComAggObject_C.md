# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2DiagnosticsTransport>>,ATL::CComCreator<ATL::CComAggObject<CMidi2DiagnosticsTransport>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006330`
- end: `0x18000633e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006344`
- `0x180006454`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2DiagnosticsTransport>>,ATL::CComCreator<ATL::CComAggObject<CMidi2DiagnosticsTransport>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMidi2DiagnosticsTransport>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMidi2DiagnosticsTransport>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180006330  test    rcx, rcx
0x180006333  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMidi2DiagnosticsTransport>>::CreateInstance(void *,_GUID const &,void * *)
0x180006339  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMidi2DiagnosticsTransport>>::CreateInstance(void *,_GUID const &,void * *)
```
