# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemoteAssistance>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005460`
- end: `0x140005482`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRemoteAssistance@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005460`
- `0x140005944`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRemoteAssistance>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CRemoteAssistance>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x140005460  test    rcx, rcx
0x140005463  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCRemoteAssistance@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CRemoteAssistance>>::CreateInstance(void *,_GUID const &,void * *)
0x140005469  test    r8, r8
0x14000546c  jnz     short loc_140005475
0x14000546e  mov     eax, 80004003h
0x140005473  jmp     short locret_140005481
0x140005475  mov     qword ptr [r8], 0
0x14000547c  mov     eax, 80040110h
0x140005481  retn
```
