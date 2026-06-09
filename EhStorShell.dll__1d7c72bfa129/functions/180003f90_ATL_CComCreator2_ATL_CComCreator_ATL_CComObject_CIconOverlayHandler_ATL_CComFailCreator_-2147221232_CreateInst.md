# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIconOverlayHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003f90`
- end: `0x180003fb2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCIconOverlayHandler@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003f90`
- `0x180003fb8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIconOverlayHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CIconOverlayHandler>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180003f90  test    rcx, rcx
0x180003f93  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCIconOverlayHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIconOverlayHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x180003f99  test    r8, r8
0x180003f9c  jnz     short loc_180003FA5
0x180003f9e  mov     eax, 80004003h
0x180003fa3  jmp     short locret_180003FB1
0x180003fa5  mov     qword ptr [r8], 0
0x180003fac  mov     eax, 80040110h
0x180003fb1  retn
```
