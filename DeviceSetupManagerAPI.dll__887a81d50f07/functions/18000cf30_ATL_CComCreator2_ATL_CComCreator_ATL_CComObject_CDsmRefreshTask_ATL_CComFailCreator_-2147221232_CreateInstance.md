# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDsmRefreshTask>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000cf30`
- end: `0x18000cf52`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDsmRefreshTask@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cf30`
- `0x18000cf58`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDsmRefreshTask>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CDsmRefreshTask>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000cf30  test    rcx, rcx
0x18000cf33  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDsmRefreshTask@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDsmRefreshTask>>::CreateInstance(void *,_GUID const &,void * *)
0x18000cf39  test    r8, r8
0x18000cf3c  jnz     short loc_18000CF45
0x18000cf3e  mov     eax, 80004003h
0x18000cf43  jmp     short locret_18000CF51
0x18000cf45  mov     qword ptr [r8], 0
0x18000cf4c  mov     eax, 80040110h
0x18000cf51  retn
```
