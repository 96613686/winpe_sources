# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<AssessmentCore>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004870`
- end: `0x180004892`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VAssessmentCore@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004870`
- `0x180004898`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<AssessmentCore>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<AssessmentCore>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180004870  test    rcx, rcx
0x180004873  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VAssessmentCore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<AssessmentCore>>::CreateInstance(void *,_GUID const &,void * *)
0x180004879  test    r8, r8
0x18000487c  jnz     short loc_180004885
0x18000487e  mov     eax, 80004003h
0x180004883  jmp     short locret_180004891
0x180004885  mov     qword ptr [r8], 0
0x18000488c  mov     eax, 80040110h
0x180004891  retn
```
