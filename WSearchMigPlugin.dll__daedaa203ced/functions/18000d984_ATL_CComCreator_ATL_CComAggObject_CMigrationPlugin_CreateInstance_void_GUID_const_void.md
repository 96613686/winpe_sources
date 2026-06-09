# ATL::CComCreator<ATL::CComAggObject<CMigrationPlugin>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d984`
- end: `0x18000dacc`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMigrationPlugin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d970`

## callees

- `0x180002c0c`
- `0x18000b69c`
- `0x18000d984`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMigrationPlugin>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  _DWORD *v7; // rbx
  int v8; // edi
  _DWORD *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x80u);
    v7[2] = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMigrationPlugin>::`vftable';
    *((_OWORD *)v7 + 5) = 0;
    *((_OWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 14) = 0;
    *((_BYTE *)v7 + 120) = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 4) = &ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 5) = &ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 6) = &ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 7) = &ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 8) = &ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 9) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 20));
    if ( v8 < 0
      || (*((_BYTE *)v7 + 120) = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d984  mov     [rsp+arg_10], r8
0x18000d989  mov     [rsp+arg_8], rdx
0x18000d98e  push    rbx
0x18000d98f  push    rsi
0x18000d990  push    rdi
0x18000d991  push    r14
0x18000d993  push    r15
0x18000d995  sub     rsp, 30h
0x18000d999  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x18000d9a2  mov     rsi, r8
0x18000d9a5  mov     r14, rdx
0x18000d9a8  mov     r15, rcx
0x18000d9ab  test    r8, r8
0x18000d9ae  jnz     short loc_18000D9BA
0x18000d9b0  mov     eax, 80004003h
0x18000d9b5  jmp     loc_18000DAC0
0x18000d9ba  mov     qword ptr [r8], 0
0x18000d9c1  mov     edi, 8007000Eh
0x18000d9c6  mov     [rsp+58h+arg_18], edi
0x18000d9ca  mov     [rsp+58h+var_38], 0
0x18000d9d3  mov     ecx, 80h; Size
0x18000d9d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d9dd  mov     rbx, rax
0x18000d9e0  mov     dword ptr [rax+8], 0
0x18000d9e7  lea     rax, ??_7?$CComAggObject@VCMigrationPlugin@@@ATL@@6B@; const ATL::CComAggObject<CMigrationPlugin>::`vftable'
0x18000d9ee  mov     [rbx], rax
0x18000d9f1  xorps   xmm0, xmm0
0x18000d9f4  xor     eax, eax
0x18000d9f6  movups  xmmword ptr [rbx+50h], xmm0
0x18000d9fa  movups  xmmword ptr [rbx+60h], xmm0
0x18000d9fe  mov     [rbx+70h], rax
0x18000da02  mov     [rbx+78h], al
0x18000da05  lea     rax, ??_7?$CComContainedObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000da0c  mov     [rbx+18h], rax
0x18000da10  lea     rax, ??_7?$CComContainedObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000da17  mov     [rbx+20h], rax
0x18000da1b  lea     rax, ??_7?$CComContainedObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000da22  mov     [rbx+28h], rax
0x18000da26  lea     rax, ??_7?$CComContainedObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPreApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000da2d  mov     [rbx+30h], rax
0x18000da31  lea     rax, ??_7?$CComContainedObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000da38  mov     [rbx+38h], rax
0x18000da3c  lea     rax, ??_7?$CComContainedObject@VCMigrationPlugin@@@ATL@@6B?$IProvideClassInfoImpl@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMigrationPlugin>::`vftable'{for `ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000da43  mov     [rbx+40h], rax
0x18000da47  mov     [rbx+48h], r15
0x18000da4b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000da52  mov     rax, [rcx]
0x18000da55  mov     rax, [rax+8]
0x18000da59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da5e  mov     [rsp+58h+var_38], rbx
0x18000da63  jmp     short loc_18000DA78
0x18000da65  mov     rsi, [rsp+58h+arg_10]
0x18000da6a  mov     r14, [rsp+58h+arg_8]
0x18000da6f  mov     edi, [rsp+58h+arg_18]
0x18000da73  mov     rbx, [rsp+58h+var_38]
0x18000da78  test    rbx, rbx
0x18000da7b  jz      short loc_18000DABE
0x18000da7d  lea     rcx, [rbx+50h]; this
0x18000da81  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000da86  mov     edi, eax
0x18000da88  test    eax, eax
0x18000da8a  js      short loc_18000DAAA
0x18000da8c  mov     byte ptr [rbx+78h], 1
0x18000da90  mov     rax, [rbx]
0x18000da93  mov     r8, rsi
0x18000da96  mov     rdx, r14
0x18000da99  mov     rcx, rbx
0x18000da9c  mov     rax, [rax]
0x18000da9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa4  mov     edi, eax
0x18000daa6  test    eax, eax
0x18000daa8  jz      short loc_18000DABE
0x18000daaa  mov     rax, [rbx]
0x18000daad  mov     edx, 1
0x18000dab2  mov     rcx, rbx
0x18000dab5  mov     rax, [rax+18h]
0x18000dab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dabe  mov     eax, edi
0x18000dac0  add     rsp, 30h
0x18000dac4  pop     r15
0x18000dac6  pop     r14
0x18000dac8  pop     rdi
0x18000dac9  pop     rsi
0x18000daca  pop     rbx
0x18000dacb  retn
```
