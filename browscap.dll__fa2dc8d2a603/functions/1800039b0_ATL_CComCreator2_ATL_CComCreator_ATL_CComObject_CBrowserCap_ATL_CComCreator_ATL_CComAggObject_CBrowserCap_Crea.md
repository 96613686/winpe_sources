# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CBrowserCap>>,ATL::CComCreator<ATL::CComAggObject<CBrowserCap>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800039b0`
- end: `0x1800039be`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCBrowserCap@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCBrowserCap@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800039c4`
- `0x180003b20`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CBrowserCap>>,ATL::CComCreator<ATL::CComAggObject<CBrowserCap>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CBrowserCap>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CBrowserCap>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x1800039b0  test    rcx, rcx
0x1800039b3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCBrowserCap@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CBrowserCap>>::CreateInstance(void *,_GUID const &,void * *)
0x1800039b9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCBrowserCap@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CBrowserCap>>::CreateInstance(void *,_GUID const &,void * *)
```
