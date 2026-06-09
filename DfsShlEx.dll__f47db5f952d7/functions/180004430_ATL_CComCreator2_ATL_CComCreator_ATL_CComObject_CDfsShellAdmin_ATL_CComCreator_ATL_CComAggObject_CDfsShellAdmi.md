# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDfsShellAdmin>>,ATL::CComCreator<ATL::CComAggObject<CDfsShellAdmin>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004430`
- end: `0x18000443e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDfsShellAdmin@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDfsShellAdmin@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004550`
- `0x180004724`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDfsShellAdmin>>,ATL::CComCreator<ATL::CComAggObject<CDfsShellAdmin>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDfsShellAdmin>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CDfsShellAdmin>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180004430  test    rcx, rcx
0x180004433  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDfsShellAdmin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDfsShellAdmin>>::CreateInstance(void *,_GUID const &,void * *)
0x180004439  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDfsShellAdmin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDfsShellAdmin>>::CreateInstance(void *,_GUID const &,void * *)
```
