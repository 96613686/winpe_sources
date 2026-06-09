# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140010330`
- end: `0x140010352`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140010330`
- `0x140010358`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x140010330  test    rcx, rcx
0x140010333  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>>::CreateInstance(void *,_GUID const &,void * *)
0x140010339  test    r8, r8
0x14001033c  jnz     short loc_140010345
0x14001033e  mov     eax, 80004003h
0x140010343  jmp     short locret_140010351
0x140010345  mov     qword ptr [r8], 0
0x14001034c  mov     eax, 80040110h
0x140010351  retn
```
