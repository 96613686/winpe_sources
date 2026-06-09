# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAxInstaller>>,ATL::CComCreator<ATL::CComAggObject<CAxInstaller>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a4d0`
- end: `0x18000a4de`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAxInstaller@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCAxInstaller@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a4e4`
- `0x18000a600`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAxInstaller>>,ATL::CComCreator<ATL::CComAggObject<CAxInstaller>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CAxInstaller>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CAxInstaller>>::CreateInstance();
}

```

## disassembly

```asm
0x18000a4d0  test    rcx, rcx
0x18000a4d3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCAxInstaller@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CAxInstaller>>::CreateInstance(void *,_GUID const &,void * *)
0x18000a4d9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCAxInstaller@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CAxInstaller>>::CreateInstance(void *,_GUID const &,void * *)
```
