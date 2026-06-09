# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2MidiSrvTransport>>,ATL::CComCreator<ATL::CComAggObject<CMidi2MidiSrvTransport>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800051d0`
- end: `0x1800051de`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800051e4`
- `0x1800052f4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2MidiSrvTransport>>,ATL::CComCreator<ATL::CComAggObject<CMidi2MidiSrvTransport>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMidi2MidiSrvTransport>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMidi2MidiSrvTransport>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x1800051d0  test    rcx, rcx
0x1800051d3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMidi2MidiSrvTransport>>::CreateInstance(void *,_GUID const &,void * *)
0x1800051d9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMidi2MidiSrvTransport>>::CreateInstance(void *,_GUID const &,void * *)
```
