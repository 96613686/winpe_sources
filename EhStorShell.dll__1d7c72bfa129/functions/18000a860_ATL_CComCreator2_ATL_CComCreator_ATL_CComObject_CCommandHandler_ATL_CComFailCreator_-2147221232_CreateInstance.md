# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCommandHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a860`
- end: `0x18000a882`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCommandHandler@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003104`
- `0x18000a860`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCommandHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CCommandHandler>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000a860  test    rcx, rcx
0x18000a863  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCCommandHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CCommandHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x18000a869  test    r8, r8
0x18000a86c  jnz     short loc_18000A875
0x18000a86e  mov     eax, 80004003h
0x18000a873  jmp     short locret_18000A881
0x18000a875  mov     qword ptr [r8], 0
0x18000a87c  mov     eax, 80040110h
0x18000a881  retn
```
