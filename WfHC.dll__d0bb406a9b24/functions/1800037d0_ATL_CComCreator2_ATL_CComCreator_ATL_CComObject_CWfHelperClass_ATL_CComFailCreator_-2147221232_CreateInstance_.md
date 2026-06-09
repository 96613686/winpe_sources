# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWfHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800037d0`
- end: `0x1800037f1`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCWfHelperClass@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800037d0`
- `0x180003800`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWfHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CWfHelperClass>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x1800037d0  test    rcx, rcx
0x1800037d3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCWfHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CWfHelperClass>>::CreateInstance(void *,_GUID const &,void * *)
0x1800037d9  test    r8, r8
0x1800037dc  jnz     short loc_1800037E4
0x1800037de  mov     eax, 80004003h
0x1800037e3  retn
0x1800037e4  mov     qword ptr [r8], 0
0x1800037eb  mov     eax, 80040110h
0x1800037f0  retn
```
