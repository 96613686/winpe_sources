# ??$call@AEAV_lambda_e2c2817e144d514ec6be4410d5bbf5ff_@@@?$factory_cache_entry@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_e2c2817e144d514ec6be4410d5bbf5ff_@@@Z

- ea: `0x18000ec34`
- end: `0x18000ede9`
- name: `??$call@AEAV_lambda_e2c2817e144d514ec6be4410d5bbf5ff_@@@?$factory_cache_entry@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_e2c2817e144d514ec6be4410d5bbf5ff_@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64, _OWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f74c`

## callees

- `0x1800033e1`
- `0x18000ec34`
- `0x18000fbc4`
- `0x180012048`
- `0x180012514`
- `0x18001d2e8`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>::call<_lambda_e2c2817e144d514ec6be4410d5bbf5ff_ &>(
        __int64 a1,
        _OWORD **a2)
{
  signed __int64 v3; // rbx
  _OWORD *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _OWORD *v7; // rax
  unsigned int v8; // eax
  _QWORD v10[2]; // [rsp+20h] [rbp-29h] BYREF
  _BYTE v11[24]; // [rsp+30h] [rbp-19h] BYREF
  int v12; // [rsp+50h] [rbp+7h] BYREF
  __int128 v13; // [rsp+58h] [rbp+Fh]
  _BYTE v14[56]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v15; // [rsp+B0h] [rbp+67h] BYREF
  void (__fastcall ***v16)(_QWORD, __int64 *, __int64 *); // [rsp+C0h] [rbp+77h] BYREF
  void (__fastcall ***v17)(_QWORD, __int64 *, _QWORD *); // [rsp+C8h] [rbp+7Fh] BYREF

  v15 = a1;
  v10[0] = L"Windows.Internal.System.Profile.RegionPolicyEvaluator";
  v10[1] = 53;
  winrt::param::hstring::hstring(v14, v10);
  v16 = 0;
  *(_DWORD *)v11 = 0;
  *(_OWORD *)&v11[8] = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v15,
    v14,
    winrt::impl::guid_v<winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>,
    &v16);
  winrt::check_hresult(&v15, (unsigned int)v15, v11);
  v3 = (signed __int64)v16;
  v17 = v16;
  if ( v16 && (v15 = 0, (**v16)(v16, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v15), v15) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
    v10[0] = &qword_18002ED08;
    _InterlockedIncrement64(&qword_18002ED08);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>,
            v3,
            0) )
    {
      v17 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002ED10);
    }
    v4 = *a2;
    LODWORD(v15) = 0;
    v12 = 0;
    v13 = 0;
    *(_OWORD *)v11 = *v4;
    v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>
                                                                + 56LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>,
           v11,
           &v15);
    winrt::check_hresult(&v16, v5, &v12);
    v6 = v15;
    _InterlockedDecrement64(&qword_18002ED08);
  }
  else
  {
    v7 = *a2;
    LODWORD(v15) = 0;
    v12 = 0;
    v13 = 0;
    *(_OWORD *)v11 = *v7;
    v8 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v3 + 56LL))(v3, v11, &v15);
    winrt::check_hresult(&v16, v8, &v12);
    v6 = v15;
  }
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v17);
  return v6;
}

```

## disassembly

```asm
0x18000ec34  mov     [rsp-8+arg_0], rcx
0x18000ec39  push    rbp
0x18000ec3a  push    rbx
0x18000ec3b  push    rdi
0x18000ec3c  lea     rbp, [rsp-47h]
0x18000ec41  sub     rsp, 90h
0x18000ec48  mov     rdi, rdx
0x18000ec4b  lea     rax, aWindowsInterna; "Windows.Internal.System.Profile.RegionP"...
0x18000ec52  mov     [rbp+57h+var_80], rax
0x18000ec56  mov     [rbp+57h+var_78], 35h ; '5'
0x18000ec5e  lea     rdx, [rbp+57h+var_80]
0x18000ec62  lea     rcx, [rbp+57h+var_38]
0x18000ec66  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000ec6b  mov     [rbp+57h+arg_10], 0
0x18000ec73  mov     dword ptr [rbp+57h+var_70], 0
0x18000ec7a  xorps   xmm0, xmm0
0x18000ec7d  movdqu  [rbp+57h+var_70+8], xmm0
0x18000ec82  lea     r9, [rbp+57h+arg_10]
0x18000ec86  lea     r8, ??$guid_v@UIRegionPolicyEvaluatorStatics@Profile@System@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>
0x18000ec8d  lea     rdx, [rbp+57h+var_38]
0x18000ec91  lea     rcx, [rbp+57h+arg_0]
0x18000ec95  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000ec9a  lea     r8, [rbp+57h+var_70]
0x18000ec9e  mov     edx, dword ptr [rbp+57h+arg_0]
0x18000eca1  lea     rcx, [rbp+57h+arg_0]
0x18000eca5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ecaa  mov     rbx, [rbp+57h+arg_10]
0x18000ecae  mov     [rbp+57h+arg_18], rbx
0x18000ecb2  test    rbx, rbx
0x18000ecb5  jz      loc_18000ED89
0x18000ecbb  mov     [rbp+57h+arg_0], 0
0x18000ecc3  mov     rax, [rbx]
0x18000ecc6  lea     r8, [rbp+57h+arg_0]
0x18000ecca  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000ecd1  mov     rcx, rbx
0x18000ecd4  mov     rax, [rax]
0x18000ecd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecdc  mov     rax, [rbp+57h+arg_0]
0x18000ece0  mov     [rbp+57h+arg_0], rax
0x18000ece4  test    rax, rax
0x18000ece7  jz      loc_18000ED89
0x18000eced  lea     rcx, [rbp+57h+arg_0]
0x18000ecf1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ecf6  lea     rax, qword_18002ED08
0x18000ecfd  mov     [rbp+57h+var_80], rax
0x18000ed01  lock inc cs:qword_18002ED08
0x18000ed09  xor     eax, eax
0x18000ed0b  lock cmpxchg cs:??$factory_cache_entry_v@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@@impl@winrt@@3U?$factory_cache_entry@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>
0x18000ed14  jnz     short loc_18000ED31
0x18000ed16  mov     [rbp+57h+arg_18], 0
0x18000ed1e  lea     rdx, stru_18002ED10; ListEntry
0x18000ed25  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000ed2c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000ed31  mov     rax, [rdi]
0x18000ed34  mov     dword ptr [rbp+57h+arg_0], 0
0x18000ed3b  mov     rcx, cs:??$factory_cache_entry_v@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@@impl@winrt@@3U?$factory_cache_entry@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics>
0x18000ed42  mov     [rbp+57h+var_50], 0
0x18000ed49  xorps   xmm0, xmm0
0x18000ed4c  movdqu  [rbp+57h+var_48], xmm0
0x18000ed51  movups  xmm0, xmmword ptr [rax]
0x18000ed54  movdqu  [rbp+57h+var_70], xmm0
0x18000ed59  mov     rax, [rcx]
0x18000ed5c  lea     r8, [rbp+57h+arg_0]
0x18000ed60  lea     rdx, [rbp+57h+var_70]
0x18000ed64  mov     rax, [rax+38h]
0x18000ed68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed6d  lea     r8, [rbp+57h+var_50]
0x18000ed71  mov     edx, eax
0x18000ed73  lea     rcx, [rbp+57h+arg_10]
0x18000ed77  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ed7c  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18000ed7f  lock dec cs:qword_18002ED08
0x18000ed87  jmp     short loc_18000EDD3
0x18000ed89  mov     rax, [rdi]
0x18000ed8c  mov     dword ptr [rbp+57h+arg_0], 0
0x18000ed93  mov     [rbp+57h+var_50], 0
0x18000ed9a  xorps   xmm0, xmm0
0x18000ed9d  movdqu  [rbp+57h+var_48], xmm0
0x18000eda2  movups  xmm0, xmmword ptr [rax]
0x18000eda5  movdqu  [rbp+57h+var_70], xmm0
0x18000edaa  mov     rax, [rbx]
0x18000edad  lea     r8, [rbp+57h+arg_0]
0x18000edb1  lea     rdx, [rbp+57h+var_70]
0x18000edb5  mov     rcx, rbx
0x18000edb8  mov     rax, [rax+38h]
0x18000edbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edc1  lea     r8, [rbp+57h+var_50]
0x18000edc5  mov     edx, eax
0x18000edc7  lea     rcx, [rbp+57h+arg_10]
0x18000edcb  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000edd0  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18000edd3  lea     rcx, [rbp+57h+arg_18]
0x18000edd7  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000eddc  mov     eax, ebx
0x18000edde  add     rsp, 90h
0x18000ede5  pop     rdi
0x18000ede6  pop     rbx
0x18000ede7  pop     rbp
0x18000ede8  retn
```
