# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIdentityStore>>,ATL::CComCreator<ATL::CComAggObject<CIdentityStore>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005fb0`
- end: `0x180005fce`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCIdentityStore@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCIdentityStore@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `30`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005fb0`
- `0x180005fe0`
- `0x18000e9fc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIdentityStore>>,ATL::CComCreator<ATL::CComAggObject<CIdentityStore>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CIdentityStore>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CIdentityStore>>::CreateInstance();
}

```

## disassembly

```asm
0x180005fb0  sub     rsp, 28h
0x180005fb4  test    rcx, rcx
0x180005fb7  jnz     short loc_180005FC7
0x180005fb9  add     rsp, 28h
0x180005fbd  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCIdentityStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIdentityStore>>::CreateInstance(void *,_GUID const &,void * *)
0x180005fc2  add     rsp, 28h
0x180005fc6  retn
0x180005fc7  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VCIdentityStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CIdentityStore>>::CreateInstance(void *,_GUID const &,void * *)
0x180005fcc  jmp     short loc_180005FC2
```
