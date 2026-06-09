# ATL::CComCreator<ATL::CComObject<CMigrationPlugin>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000dad4`
- end: `0x18000dc52`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMigrationPlugin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d970`

## callees

- `0x180002c0c`
- `0x18000b69c`
- `0x18000dad4`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMigrationPlugin>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v6; // rbx
  signed __int32 v7; // eax
  int v8; // edi
  signed __int32 v9; // eax
  char *v12; // [rsp+88h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v6 = (char *)operator new(0x68u);
    *((_DWORD *)v6 + 12) = 0;
    *(_OWORD *)(v6 + 56) = 0;
    *(_OWORD *)(v6 + 72) = 0;
    *((_QWORD *)v6 + 11) = 0;
    v6[96] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 2) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 3) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 4) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 5) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v12 = v6;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v6 = v12;
  }
  if ( v6 )
  {
    do
      v7 = *((_DWORD *)v6 + 12);
    while ( v7 != 0x7FFFFFFF && v7 != _InterlockedCompareExchange((volatile signed __int32 *)v6 + 12, v7 + 1, v7) );
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v6 + 56));
    if ( v8 >= 0 )
    {
      v6[96] = 1;
      v8 = 0;
    }
    do
      v9 = *((_DWORD *)v6 + 12);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v6 + 12, v9 - 1, v9) );
    if ( v8 || (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 80LL))(v6, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000dad4  mov     rax, rsp
0x18000dad7  mov     [rax+18h], r8
0x18000dadb  mov     [rax+10h], rdx
0x18000dadf  mov     [rax+8], rcx
0x18000dae3  push    rbx
0x18000dae4  push    rsi
0x18000dae5  push    rdi
0x18000dae6  push    r12
0x18000dae8  push    r14
0x18000daea  push    r15
0x18000daec  sub     rsp, 38h
0x18000daf0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000daf8  mov     rsi, r8
0x18000dafb  mov     r14, rdx
0x18000dafe  test    r8, r8
0x18000db01  jnz     short loc_18000DB0D
0x18000db03  mov     eax, 80004003h
0x18000db08  jmp     loc_18000DC44
0x18000db0d  mov     qword ptr [r8], 0
0x18000db14  mov     edi, 8007000Eh
0x18000db19  mov     [rsp+68h+arg_0], edi
0x18000db1d  mov     [rsp+68h+arg_18], 0
0x18000db29  mov     ecx, 68h ; 'h'; Size
0x18000db2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db33  mov     rbx, rax
0x18000db36  mov     dword ptr [rax+30h], 0
0x18000db3d  xorps   xmm0, xmm0
0x18000db40  xor     eax, eax
0x18000db42  movups  xmmword ptr [rbx+38h], xmm0
0x18000db46  movups  xmmword ptr [rbx+48h], xmm0
0x18000db4a  mov     [rbx+58h], rax
0x18000db4e  mov     [rbx+60h], al
0x18000db51  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000db58  mov     [rbx], rax
0x18000db5b  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000db62  mov     [rbx+8], rax
0x18000db66  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000db6d  mov     [rbx+10h], rax
0x18000db71  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPreApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000db78  mov     [rbx+18h], rax
0x18000db7c  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000db83  mov     [rbx+20h], rax
0x18000db87  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IProvideClassInfoImpl@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000db8e  mov     [rbx+28h], rax
0x18000db92  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000db99  mov     rax, [rcx]
0x18000db9c  mov     rax, [rax+8]
0x18000dba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba5  mov     [rsp+68h+arg_18], rbx
0x18000dbad  jmp     short loc_18000DBC8
0x18000dbaf  mov     rsi, [rsp+68h+arg_10]
0x18000dbb7  mov     r14, [rsp+68h+arg_8]
0x18000dbbc  mov     edi, [rsp+68h+arg_0]
0x18000dbc0  mov     rbx, [rsp+68h+arg_18]
0x18000dbc8  test    rbx, rbx
0x18000dbcb  jz      short loc_18000DC42
0x18000dbcd  mov     r12d, 7FFFFFFFh
0x18000dbd3  jmp     short loc_18000DBDF
0x18000dbd5  lea     ecx, [rax+1]
0x18000dbd8  lock cmpxchg [rbx+30h], ecx
0x18000dbdd  jz      short loc_18000DBE7
0x18000dbdf  mov     eax, [rbx+30h]
0x18000dbe2  cmp     eax, r12d
0x18000dbe5  jnz     short loc_18000DBD5
0x18000dbe7  lea     rcx, [rbx+38h]; this
0x18000dbeb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000dbf0  mov     edi, eax
0x18000dbf2  test    eax, eax
0x18000dbf4  js      short loc_18000DC08
0x18000dbf6  mov     byte ptr [rbx+60h], 1
0x18000dbfa  xor     edi, edi
0x18000dbfc  jmp     short loc_18000DC08
0x18000dbfe  lea     ecx, [rax-1]
0x18000dc01  lock cmpxchg [rbx+30h], ecx
0x18000dc06  jz      short loc_18000DC10
0x18000dc08  mov     eax, [rbx+30h]
0x18000dc0b  cmp     eax, r12d
0x18000dc0e  jnz     short loc_18000DBFE
0x18000dc10  test    edi, edi
0x18000dc12  jnz     short loc_18000DC2E
0x18000dc14  mov     rax, [rbx]
0x18000dc17  mov     r8, rsi
0x18000dc1a  mov     rdx, r14
0x18000dc1d  mov     rcx, rbx
0x18000dc20  mov     rax, [rax]
0x18000dc23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc28  mov     edi, eax
0x18000dc2a  test    eax, eax
0x18000dc2c  jz      short loc_18000DC42
0x18000dc2e  mov     r8, [rbx]
0x18000dc31  mov     edx, 1
0x18000dc36  mov     rcx, rbx
0x18000dc39  mov     rax, [r8+50h]
0x18000dc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc42  mov     eax, edi
0x18000dc44  add     rsp, 38h
0x18000dc48  pop     r15
0x18000dc4a  pop     r14
0x18000dc4c  pop     r12
0x18000dc4e  pop     rdi
0x18000dc4f  pop     rsi
0x18000dc50  pop     rbx
0x18000dc51  retn
```
