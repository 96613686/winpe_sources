# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CSMBHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004a60`
- end: `0x180004a82`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCSMBHelperClass@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004a60`
- `0x180004a88`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CSMBHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CSMBHelperClass>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180004a60  test    rcx, rcx
0x180004a63  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCSMBHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CSMBHelperClass>>::CreateInstance(void *,_GUID const &,void * *)
0x180004a69  test    r8, r8
0x180004a6c  jnz     short loc_180004A75
0x180004a6e  mov     eax, 80004003h
0x180004a73  jmp     short locret_180004A81
0x180004a75  mov     qword ptr [r8], 0
0x180004a7c  mov     eax, 80040110h
0x180004a81  retn
```
