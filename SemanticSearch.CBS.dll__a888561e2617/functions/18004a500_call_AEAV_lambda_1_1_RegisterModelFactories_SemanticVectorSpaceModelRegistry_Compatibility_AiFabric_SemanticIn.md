# ??$call@AEAV_lambda_1_@?1??RegisterModelFactories@SemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIModelFactoryRegistrar@456789@@Z@@?$factory_cache_entry@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??RegisterModelFactories@SemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIModelFactoryRegistrar@6789Microsoft@2@@Z@@Z

- ea: `0x18004a500`
- end: `0x18004a71a`
- name: `??$call@AEAV_lambda_1_@?1??RegisterModelFactories@SemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIModelFactoryRegistrar@456789@@Z@@?$factory_cache_entry@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??RegisterModelFactories@SemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIModelFactoryRegistrar@6789Microsoft@2@@Z@@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800455b0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18004a500`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18004a625`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18004a685`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18004a543`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticVectorSpaceModelRegistry`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__RegisterModelFactories_SemanticVectorSpaceModelRegistry_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUIModelFactoryRegistrar_456789__Z____factory_cache_entry_USemanticVectorSpaceModelRegistry_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticVectorSpaceModelRegistryStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__RegisterModelFactories_SemanticVectorSpaceModelRegistry_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUIModelFactoryRegistrar_6789Microsoft_2__Z__Z(
        __int64 a1,
        __int64 a2,
        _QWORD **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rdi
  int v6; // eax
  int v7; // eax
  void (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-29h] BYREF
  int v10; // [rsp+38h] [rbp-21h] BYREF
  const char *v11; // [rsp+40h] [rbp-19h]
  _QWORD v12[2]; // [rsp+50h] [rbp-9h] BYREF
  _DWORD *v13; // [rsp+60h] [rbp+7h] BYREF
  _DWORD v14[4]; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v15; // [rsp+78h] [rbp+1Fh]
  __int64 v16; // [rsp+80h] [rbp+27h] BYREF
  void (__fastcall ***v17)(_QWORD, __int64 *, __int64 *); // [rsp+88h] [rbp+2Fh] BYREF

  v9 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
  v14[0] = 1;
  v14[1] = 83;
  v15 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticVectorSpaceModelRegistry";
  v13 = v14;
  v17 = 0;
  LODWORD(v12[0]) = 6148;
  v12[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v16,
    &v13,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>,
    (__int64)&v17);
  if ( (int)v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, v12);
  }
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  v9 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  if ( !v17 || (v16 = 0, (**v17)(v17, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v16), !v16) )
  {
    LODWORD(v16) = 0;
    v17 = 0;
    v10 = 1237;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD, __int64 *, void (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*v5)[6])(
           v5,
           **a3,
           &v16,
           &v17);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *(_QWORD *)a2 = v17;
    *(_DWORD *)(a2 + 8) = v16;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v16);
  v12[0] = &qword_180086B88;
  _InterlockedIncrement64(&qword_180086B88);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>,
          (signed __int64)v17,
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086B90);
    v5 = 0;
  }
  LODWORD(v16) = 0;
  v17 = 0;
  v10 = 1237;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, void (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics> + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>,
         **a3,
         &v16,
         &v17);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, &v10);
  }
  *(_QWORD *)a2 = v17;
  *(_DWORD *)(a2 + 8) = v16;
  _InterlockedDecrement64(&qword_180086B88);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18004a500  mov     [rsp-8+arg_0], rbx
0x18004a505  mov     [rsp-8+arg_18], rsi
0x18004a50a  push    rbp
0x18004a50b  push    rdi
0x18004a50c  push    r14
0x18004a50e  lea     rbp, [rsp-47h]
0x18004a513  sub     rsp, 0A0h
0x18004a51a  mov     rax, cs:__security_cookie
0x18004a521  xor     rax, rsp
0x18004a524  mov     [rbp+57h+var_20], rax
0x18004a528  mov     rsi, r8
0x18004a52b  mov     rbx, rdx
0x18004a52e  mov     [rbp+57h+var_80], rdx
0x18004a532  xor     r14d, r14d
0x18004a535  mov     [rbp+57h+var_48], 1
0x18004a53c  mov     [rbp+57h+var_44], 53h ; 'S'
0x18004a543  lea     rax, aMicrosoftAsgSe_3; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18004a54a  mov     [rbp+57h+var_38], rax
0x18004a54e  lea     rax, [rbp+57h+var_48]
0x18004a552  mov     [rbp+57h+var_50], rax
0x18004a556  mov     [rbp+57h+var_28], r14
0x18004a55a  mov     dword ptr [rbp+57h+var_60], 1804h
0x18004a561  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18004a568  mov     [rbp+57h+var_58], rax
0x18004a56c  lea     r9, [rbp+57h+var_28]
0x18004a570  lea     r8, ??$guid_v@UISemanticVectorSpaceModelRegistryStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>
0x18004a577  lea     rdx, [rbp+57h+var_50]
0x18004a57b  lea     rcx, [rbp+57h+var_30]
0x18004a57f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18004a584  mov     ecx, dword ptr [rbp+57h+var_30]
0x18004a587  test    ecx, ecx
0x18004a589  js      loc_18004A6FE
0x18004a58f  mov     rdi, [rbp+57h+var_28]
0x18004a593  mov     [rbp+57h+var_80], rdi
0x18004a597  test    rdi, rdi
0x18004a59a  jz      loc_18004A676
0x18004a5a0  mov     [rbp+57h+var_30], r14
0x18004a5a4  mov     rax, [rdi]
0x18004a5a7  lea     r8, [rbp+57h+var_30]
0x18004a5ab  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18004a5b2  mov     rcx, rdi
0x18004a5b5  mov     rax, [rax]
0x18004a5b8  call    cs:__guard_dispatch_icall_fptr
0x18004a5be  mov     rax, [rbp+57h+var_30]
0x18004a5c2  mov     [rbp+57h+var_30], rax
0x18004a5c6  test    rax, rax
0x18004a5c9  jz      loc_18004A676
0x18004a5cf  lea     rcx, [rbp+57h+var_30]
0x18004a5d3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004a5d8  lea     rax, qword_180086B88
0x18004a5df  mov     [rbp+57h+var_60], rax
0x18004a5e3  lock inc cs:qword_180086B88
0x18004a5eb  mov     rcx, [rbp+57h+var_28]
0x18004a5ef  xor     eax, eax
0x18004a5f1  lock cmpxchg cs:??$factory_cache_entry_v@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>
0x18004a5fa  jnz     short loc_18004A616
0x18004a5fc  mov     [rbp+57h+var_80], r14
0x18004a600  lea     rdx, stru_180086B90; ListEntry
0x18004a607  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18004a60e  call    WINRT_IMPL_InterlockedPushEntrySList
0x18004a613  mov     edi, r14d
0x18004a616  mov     dword ptr [rbp+57h+var_30], r14d
0x18004a61a  mov     [rbp+57h+var_28], r14
0x18004a61e  mov     [rbp+57h+var_78], 4D5h
0x18004a625  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18004a62c  mov     [rbp+57h+var_70], rax
0x18004a630  mov     rcx, cs:??$factory_cache_entry_v@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticVectorSpaceModelRegistry@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticVectorSpaceModelRegistryStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticVectorSpaceModelRegistry,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticVectorSpaceModelRegistryStatics>
0x18004a637  mov     rdx, [rsi]
0x18004a63a  mov     rax, [rcx]
0x18004a63d  lea     r9, [rbp+57h+var_28]
0x18004a641  lea     r8, [rbp+57h+var_30]
0x18004a645  mov     rdx, [rdx]
0x18004a648  mov     rax, [rax+30h]
0x18004a64c  call    cs:__guard_dispatch_icall_fptr
0x18004a652  test    eax, eax
0x18004a654  js      loc_18004A70B
0x18004a65a  mov     rcx, [rbp+57h+var_28]
0x18004a65e  mov     [rbx], rcx
0x18004a661  mov     ecx, dword ptr [rbp+57h+var_30]
0x18004a664  mov     [rbx+8], ecx
0x18004a667  lock dec cs:qword_180086B88
0x18004a66f  test    rdi, rdi
0x18004a672  jz      short loc_18004A6C8
0x18004a674  jmp     short loc_18004A6BF
0x18004a676  mov     dword ptr [rbp+57h+var_30], r14d
0x18004a67a  mov     [rbp+57h+var_28], r14
0x18004a67e  mov     [rbp+57h+var_78], 4D5h
0x18004a685  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18004a68c  mov     [rbp+57h+var_70], rax
0x18004a690  mov     rdx, [rsi]
0x18004a693  mov     rax, [rdi]
0x18004a696  lea     r9, [rbp+57h+var_28]
0x18004a69a  lea     r8, [rbp+57h+var_30]
0x18004a69e  mov     rdx, [rdx]
0x18004a6a1  mov     rcx, rdi
0x18004a6a4  mov     rax, [rax+30h]
0x18004a6a8  call    cs:__guard_dispatch_icall_fptr
0x18004a6ae  test    eax, eax
0x18004a6b0  js      short loc_18004A6EF
0x18004a6b2  mov     rax, [rbp+57h+var_28]
0x18004a6b6  mov     [rbx], rax
0x18004a6b9  mov     eax, dword ptr [rbp+57h+var_30]
0x18004a6bc  mov     [rbx+8], eax
0x18004a6bf  lea     rcx, [rbp+57h+var_80]
0x18004a6c3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004a6c8  mov     rax, rbx
0x18004a6cb  mov     rcx, [rbp+57h+var_20]
0x18004a6cf  xor     rcx, rsp; StackCookie
0x18004a6d2  call    __security_check_cookie
0x18004a6d7  lea     r11, [rsp+0B0h+var_10]
0x18004a6df  mov     rbx, [r11+20h]
0x18004a6e3  mov     rsi, [r11+38h]
0x18004a6e7  mov     rsp, r11
0x18004a6ea  pop     r14
0x18004a6ec  pop     rdi
0x18004a6ed  pop     rbp
0x18004a6ee  retn
0x18004a6ef  lfence
0x18004a6f2  lea     rdx, [rbp+57h+var_78]
0x18004a6f6  mov     ecx, eax
0x18004a6f8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a6fe  lfence
0x18004a701  lea     rdx, [rbp+57h+var_60]
0x18004a705  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a70b  lfence
0x18004a70e  lea     rdx, [rbp+57h+var_78]
0x18004a712  mov     ecx, eax
0x18004a714  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
