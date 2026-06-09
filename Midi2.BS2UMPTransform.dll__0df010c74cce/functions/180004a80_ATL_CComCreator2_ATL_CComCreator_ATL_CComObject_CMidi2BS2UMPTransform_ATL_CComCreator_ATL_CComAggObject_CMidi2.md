# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2BS2UMPTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2BS2UMPTransform>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004a80`
- end: `0x180004a8e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004a94`
- `0x180004ba4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMidi2BS2UMPTransform>>,ATL::CComCreator<ATL::CComAggObject<CMidi2BS2UMPTransform>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMidi2BS2UMPTransform>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMidi2BS2UMPTransform>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180004a80  test    rcx, rcx
0x180004a83  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMidi2BS2UMPTransform>>::CreateInstance(void *,_GUID const &,void * *)
0x180004a89  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMidi2BS2UMPTransform>>::CreateInstance(void *,_GUID const &,void * *)
```
