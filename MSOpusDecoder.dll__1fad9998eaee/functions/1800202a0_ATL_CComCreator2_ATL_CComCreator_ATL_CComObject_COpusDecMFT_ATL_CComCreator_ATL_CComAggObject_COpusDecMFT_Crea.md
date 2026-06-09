# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<COpusDecMFT>>,ATL::CComCreator<ATL::CComAggObject<COpusDecMFT>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800202a0`
- end: `0x1800202ae`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCOpusDecMFT@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCOpusDecMFT@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800202b4`
- `0x1800203ec`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<COpusDecMFT>>,ATL::CComCreator<ATL::CComAggObject<COpusDecMFT>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<COpusDecMFT>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<COpusDecMFT>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x1800202a0  test    rcx, rcx
0x1800202a3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCOpusDecMFT@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<COpusDecMFT>>::CreateInstance(void *,_GUID const &,void * *)
0x1800202a9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCOpusDecMFT@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<COpusDecMFT>>::CreateInstance(void *,_GUID const &,void * *)
```
