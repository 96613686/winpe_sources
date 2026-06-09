# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIMOfferRA>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1400053e0`
- end: `0x140005402`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCIMOfferRA@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400053e0`
- `0x1400055b8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIMOfferRA>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CIMOfferRA>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x1400053e0  test    rcx, rcx
0x1400053e3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCIMOfferRA@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIMOfferRA>>::CreateInstance(void *,_GUID const &,void * *)
0x1400053e9  test    r8, r8
0x1400053ec  jnz     short loc_1400053F5
0x1400053ee  mov     eax, 80004003h
0x1400053f3  jmp     short locret_140005401
0x1400053f5  mov     qword ptr [r8], 0
0x1400053fc  mov     eax, 80040110h
0x140005401  retn
```
