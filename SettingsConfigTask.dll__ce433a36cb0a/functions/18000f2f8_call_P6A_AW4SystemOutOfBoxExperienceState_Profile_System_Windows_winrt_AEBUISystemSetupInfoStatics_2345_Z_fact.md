# ??$call@P6A?AW4SystemOutOfBoxExperienceState@Profile@System@Windows@winrt@@AEBUISystemSetupInfoStatics@2345@@Z@?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AW4SystemOutOfBoxExperienceState@Profile@System@Windows@2@AEBUISystemSetupInfoStatics@4562@@Z@Z

- ea: `0x18000f2f8`
- end: `0x18000f3fa`
- name: `??$call@P6A?AW4SystemOutOfBoxExperienceState@Profile@System@Windows@winrt@@AEBUISystemSetupInfoStatics@2345@@Z@?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AW4SystemOutOfBoxExperienceState@Profile@System@Windows@2@AEBUISystemSetupInfoStatics@4562@@Z@Z`
- size: `258`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64 (__fastcall **)(__int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f7e8`

## callees

- `0x1800033e1`
- `0x18000f2f8`
- `0x18000fb64`
- `0x180012048`
- `0x180012514`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::call<enum winrt::Windows::System::Profile::SystemOutOfBoxExperienceState (*)(winrt::Windows::System::Profile::ISystemSetupInfoStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 (__fastcall **a2)(__int64 *))
{
  unsigned int v3; // ebx
  _QWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v6[32]; // [rsp+30h] [rbp-20h] BYREF
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v8; // [rsp+70h] [rbp+20h] BYREF

  v7 = a1;
  v5[0] = L"Windows.System.Profile.SystemSetupInfo";
  v5[1] = 38;
  winrt::param::hstring::hstring(v6, v5);
  winrt::get_activation_factory<winrt::Windows::System::Profile::ISystemSetupInfoStatics>(&v7, v6);
  if ( v7 && (v8 = 0, (**v7)(v7, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
    v8 = &qword_18002EC28;
    _InterlockedIncrement64(&qword_18002EC28);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>,
            (signed __int64)v7,
            0) )
    {
      v7 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    v3 = (*a2)(&winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>);
    _InterlockedDecrement64(&qword_18002EC28);
  }
  else
  {
    v3 = (*a2)((__int64 *)&v7);
  }
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v7);
  return v3;
}

```

## disassembly

```asm
0x18000f2f8  mov     [rsp-8+arg_8], rbx
0x18000f2fd  mov     [rsp-8+arg_0], rcx
0x18000f302  push    rbp
0x18000f303  mov     rbp, rsp
0x18000f306  sub     rsp, 50h
0x18000f30a  mov     rbx, rdx
0x18000f30d  lea     rax, aWindowsSystemP; "Windows.System.Profile.SystemSetupInfo"
0x18000f314  mov     [rbp+var_30], rax
0x18000f318  mov     [rbp+var_28], 26h ; '&'
0x18000f320  lea     rdx, [rbp+var_30]
0x18000f324  lea     rcx, [rbp+var_20]
0x18000f328  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f32d  lea     rdx, [rbp+var_20]
0x18000f331  lea     rcx, [rbp+arg_0]
0x18000f335  call    ??$get_activation_factory@UISystemSetupInfoStatics@Profile@System@Windows@winrt@@@winrt@@YA?AUISystemSetupInfoStatics@Profile@System@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::System::Profile::ISystemSetupInfoStatics>(winrt::param::hstring const &)
0x18000f33a  nop
0x18000f33b  mov     rcx, [rbp+arg_0]
0x18000f33f  test    rcx, rcx
0x18000f342  jz      loc_18000F3D6
0x18000f348  mov     [rbp+arg_10], 0
0x18000f350  mov     rax, [rcx]
0x18000f353  lea     r8, [rbp+arg_10]
0x18000f357  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f35e  mov     rax, [rax]
0x18000f361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f366  mov     rax, [rbp+arg_10]
0x18000f36a  mov     [rbp+arg_10], rax
0x18000f36e  test    rax, rax
0x18000f371  jz      short loc_18000F3D6
0x18000f373  lea     rcx, [rbp+arg_10]
0x18000f377  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f37c  lea     rax, qword_18002EC28
0x18000f383  mov     [rbp+arg_10], rax
0x18000f387  lock inc cs:qword_18002EC28
0x18000f38f  mov     rcx, [rbp+arg_0]
0x18000f393  xor     eax, eax
0x18000f395  lock cmpxchg cs:??$factory_cache_entry_v@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::winrt::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>
0x18000f39e  jnz     short loc_18000F3BB
0x18000f3a0  mov     [rbp+arg_0], 0
0x18000f3a8  lea     rdx, ListEntry; ListEntry
0x18000f3af  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f3b6  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f3bb  lea     rcx, ??$factory_cache_entry_v@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::winrt::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>
0x18000f3c2  mov     rax, [rbx]
0x18000f3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3ca  mov     ebx, eax
0x18000f3cc  lock dec cs:qword_18002EC28
0x18000f3d4  jmp     short loc_18000F3E4
0x18000f3d6  lea     rcx, [rbp+arg_0]
0x18000f3da  mov     rax, [rbx]
0x18000f3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3e2  mov     ebx, eax
0x18000f3e4  lea     rcx, [rbp+arg_0]
0x18000f3e8  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f3ed  mov     eax, ebx
0x18000f3ef  mov     rbx, [rsp+50h+arg_8]
0x18000f3f4  add     rsp, 50h
0x18000f3f8  pop     rbp
0x18000f3f9  retn
```
