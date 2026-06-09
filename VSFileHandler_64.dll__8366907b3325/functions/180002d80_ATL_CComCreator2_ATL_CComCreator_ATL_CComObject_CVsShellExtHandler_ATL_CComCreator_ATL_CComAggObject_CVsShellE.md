# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CVsShellExtHandler>>,ATL::CComCreator<ATL::CComAggObject<CVsShellExtHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002d80`
- end: `0x180002d8e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCVsShellExtHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCVsShellExtHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002f5c`
- `0x180003074`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CVsShellExtHandler>>,ATL::CComCreator<ATL::CComAggObject<CVsShellExtHandler>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CVsShellExtHandler>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CVsShellExtHandler>>::CreateInstance(
             0,
             (const struct _GUID *)a2,
             (void **)a3);
}

```

## disassembly

```asm
0x180002d80  test    rcx, rcx
0x180002d83  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCVsShellExtHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CVsShellExtHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x180002d89  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCVsShellExtHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CVsShellExtHandler>>::CreateInstance(void *,_GUID const &,void * *)
```
