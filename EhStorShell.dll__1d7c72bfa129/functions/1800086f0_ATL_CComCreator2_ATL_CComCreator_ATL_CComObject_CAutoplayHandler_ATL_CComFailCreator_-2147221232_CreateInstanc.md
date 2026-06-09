# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAutoplayHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800086f0`
- end: `0x180008712`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAutoplayHandler@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800086f0`
- `0x180008718`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAutoplayHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CAutoplayHandler>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x1800086f0  test    rcx, rcx
0x1800086f3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCAutoplayHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CAutoplayHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x1800086f9  test    r8, r8
0x1800086fc  jnz     short loc_180008705
0x1800086fe  mov     eax, 80004003h
0x180008703  jmp     short locret_180008711
0x180008705  mov     qword ptr [r8], 0
0x18000870c  mov     eax, 80040110h
0x180008711  retn
```
