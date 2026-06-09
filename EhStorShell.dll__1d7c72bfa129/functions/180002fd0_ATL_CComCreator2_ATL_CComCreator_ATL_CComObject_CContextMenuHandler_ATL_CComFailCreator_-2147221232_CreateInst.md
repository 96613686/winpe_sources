# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CContextMenuHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002fd0`
- end: `0x180002ff1`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCContextMenuHandler@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002fd0`
- `0x180003000`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CContextMenuHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CContextMenuHandler>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180002fd0  test    rcx, rcx
0x180002fd3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCContextMenuHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CContextMenuHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x180002fd9  test    r8, r8
0x180002fdc  jnz     short loc_180002FE4
0x180002fde  mov     eax, 80004003h
0x180002fe3  retn
0x180002fe4  mov     qword ptr [r8], 0
0x180002feb  mov     eax, 80040110h
0x180002ff0  retn
```
