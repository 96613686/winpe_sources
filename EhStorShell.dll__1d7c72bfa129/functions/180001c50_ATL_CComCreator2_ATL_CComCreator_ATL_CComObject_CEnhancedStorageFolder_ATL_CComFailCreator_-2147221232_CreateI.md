# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageFolder>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001c50`
- end: `0x180001c74`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCEnhancedStorageFolder@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `36`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001c50`
- `0x180001c80`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageFolder>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CEnhancedStorageFolder>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180001c50  test    rcx, rcx
0x180001c53  jnz     short loc_180001C5B
0x180001c55  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageFolder@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CEnhancedStorageFolder>>::CreateInstance(void *,_GUID const &,void * *)
0x180001c5a  retn
0x180001c5b  test    r8, r8
0x180001c5e  jnz     short loc_180001C66
0x180001c60  mov     eax, 80004003h
0x180001c65  retn
0x180001c66  mov     qword ptr [r8], 0
0x180001c6d  mov     eax, 80040110h
0x180001c72  jmp     short locret_180001C5A
```
