# ??$call@AEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@Z

- ea: `0x18000ef74`
- end: `0x18000f0b9`
- name: `??$call@AEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_f0867a2080869fb329157b990d30dd01_@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001871c`

## callees

- `0x1800033e1`
- `0x18000ef74`
- `0x18000fbc4`
- `0x180012048`
- `0x180012514`
- `0x180013334`
- `0x18001d2e8`
- `0x1800215e8`
- `0x180024010`

## string_xrefs

- `0x18000ef8e`: `Microsoft.Windows.Workloads.Internal.CacheManagerInternal`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::call<_lambda_f0867a2080869fb329157b990d30dd01_ &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  const wchar_t *v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _BYTE v9[32]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = a1;
  v7 = L"Microsoft.Windows.Workloads.Internal.CacheManagerInternal";
  *(_QWORD *)&v8 = 57;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>,
    &v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v5 = v11;
  v10 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
    v11 = &qword_18002ED28;
    _InterlockedIncrement64(&qword_18002ED28);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002ED30);
    }
    _lambda_f0867a2080869fb329157b990d30dd01_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>);
    _InterlockedDecrement64(&qword_18002ED28);
  }
  else
  {
    _lambda_f0867a2080869fb329157b990d30dd01_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v10);
  return a2;
}

```

## disassembly

```asm
0x18000ef74  mov     [rsp-18h+arg_8], rbx
0x18000ef79  mov     [rsp-18h+arg_0], rcx
0x18000ef7e  push    rbp
0x18000ef7f  push    rsi
0x18000ef80  push    rdi
0x18000ef81  mov     rbp, rsp
0x18000ef84  sub     rsp, 60h
0x18000ef88  mov     rsi, r8
0x18000ef8b  mov     rbx, rdx
0x18000ef8e  lea     rax, aMicrosoftWindo; "Microsoft.Windows.Workloads.Internal.Ca"...
0x18000ef95  mov     [rbp+var_38], rax
0x18000ef99  mov     qword ptr [rbp+var_30], 39h ; '9'
0x18000efa1  lea     rdx, [rbp+var_38]
0x18000efa5  lea     rcx, [rbp+var_20]
0x18000efa9  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000efae  mov     [rbp+arg_18], 0
0x18000efb6  mov     dword ptr [rbp+var_38], 0
0x18000efbd  xorps   xmm0, xmm0
0x18000efc0  movdqu  [rbp+var_30], xmm0
0x18000efc5  lea     r9, [rbp+arg_18]
0x18000efc9  lea     r8, ??$guid_v@UICacheManagerInternalStatics@Internal@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x18000efd0  lea     rdx, [rbp+var_20]
0x18000efd4  lea     rcx, [rbp+arg_0]
0x18000efd8  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000efdd  lea     r8, [rbp+var_38]
0x18000efe1  mov     edx, dword ptr [rbp+arg_0]
0x18000efe4  lea     rcx, [rbp+arg_0]
0x18000efe8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000efed  mov     rdi, [rbp+arg_18]
0x18000eff1  mov     [rbp+arg_0], rdi
0x18000eff5  test    rdi, rdi
0x18000eff8  jz      loc_18000F08D
0x18000effe  mov     [rbp+arg_18], 0
0x18000f006  mov     rax, [rdi]
0x18000f009  lea     r8, [rbp+arg_18]
0x18000f00d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f014  mov     rcx, rdi
0x18000f017  mov     rax, [rax]
0x18000f01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f01f  mov     rax, [rbp+arg_18]
0x18000f023  mov     [rbp+arg_18], rax
0x18000f027  test    rax, rax
0x18000f02a  jz      short loc_18000F08D
0x18000f02c  lea     rcx, [rbp+arg_18]
0x18000f030  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f035  lea     rax, qword_18002ED28
0x18000f03c  mov     [rbp+arg_18], rax
0x18000f040  lock inc cs:qword_18002ED28
0x18000f048  xor     eax, eax
0x18000f04a  lock cmpxchg cs:??$factory_cache_entry_v@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x18000f053  jnz     short loc_18000F070
0x18000f055  mov     [rbp+arg_0], 0
0x18000f05d  lea     rdx, stru_18002ED30; ListEntry
0x18000f064  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f06b  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f070  lea     r8, ??$factory_cache_entry_v@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCacheManagerInternal@Internal@Workloads@Windows@Microsoft@winrt@@UICacheManagerInternalStatics@23456@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::Internal::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics>
0x18000f077  mov     rdx, rbx
0x18000f07a  mov     rcx, rsi
0x18000f07d  call    ??R_lambda_f0867a2080869fb329157b990d30dd01_@@QEBA@AEBUICacheManagerInternalStatics@Internal@Workloads@Windows@Microsoft@winrt@@@Z; _lambda_f0867a2080869fb329157b990d30dd01_::operator()(winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics const &)
0x18000f082  nop
0x18000f083  lock dec cs:qword_18002ED28
0x18000f08b  jmp     short loc_18000F09D
0x18000f08d  lea     r8, [rbp+arg_0]
0x18000f091  mov     rdx, rbx
0x18000f094  mov     rcx, rsi
0x18000f097  call    ??R_lambda_f0867a2080869fb329157b990d30dd01_@@QEBA@AEBUICacheManagerInternalStatics@Internal@Workloads@Windows@Microsoft@winrt@@@Z; _lambda_f0867a2080869fb329157b990d30dd01_::operator()(winrt::Microsoft::Windows::Workloads::Internal::ICacheManagerInternalStatics const &)
0x18000f09c  nop
0x18000f09d  lea     rcx, [rbp+arg_0]
0x18000f0a1  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f0a6  mov     rax, rbx
0x18000f0a9  mov     rbx, [rsp+60h+arg_8]
0x18000f0b1  add     rsp, 60h
0x18000f0b5  pop     rdi
0x18000f0b6  pop     rsi
0x18000f0b7  pop     rbp
0x18000f0b8  retn
```
