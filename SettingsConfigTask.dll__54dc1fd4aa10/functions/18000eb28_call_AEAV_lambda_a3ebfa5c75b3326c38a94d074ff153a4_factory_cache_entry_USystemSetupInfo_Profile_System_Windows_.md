# ??$call@AEAV_lambda_a3ebfa5c75b3326c38a94d074ff153a4_@@@?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_a3ebfa5c75b3326c38a94d074ff153a4_@@@Z

- ea: `0x18000eb28`
- end: `0x18000ec2d`
- name: `??$call@AEAV_lambda_a3ebfa5c75b3326c38a94d074ff153a4_@@@?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_a3ebfa5c75b3326c38a94d074ff153a4_@@@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800197b0`

## callees

- `0x1800033e1`
- `0x18000c568`
- `0x18000eb28`
- `0x18000fb64`
- `0x180012048`
- `0x180012514`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::call<_lambda_a3ebfa5c75b3326c38a94d074ff153a4_ &>(
        __int64 a1,
        signed __int64 *a2,
        void (__fastcall ***a3)(_QWORD, __int64 *, __int64 *))
{
  signed __int64 v4; // rdi
  void (__fastcall **v5)(_QWORD, __int64 *, __int64 *); // rax
  __int64 v6; // rcx
  _QWORD v8[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v9[40]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+70h] [rbp+10h] BYREF
  void (__fastcall ***v11)(_QWORD, __int64 *, __int64 *); // [rsp+80h] [rbp+20h] BYREF

  v11 = a3;
  v10 = a1;
  v8[1] = 38;
  v8[0] = L"Windows.System.Profile.SystemSetupInfo";
  winrt::param::hstring::hstring(v9, v8);
  winrt::get_activation_factory<winrt::Windows::System::Profile::ISystemSetupInfoStatics>(&v11, v9);
  v4 = (signed __int64)v11;
  if ( v11 )
  {
    v5 = *v11;
    v10 = 0;
    (*v5)(v11, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10);
    if ( v10 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
      _InterlockedIncrement64(&qword_18002EC28);
      if ( !_InterlockedCompareExchange64(
              &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>,
              v4,
              0) )
      {
        v11 = 0;
        WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
      }
      _lambda_a3ebfa5c75b3326c38a94d074ff153a4_::operator()<winrt::Windows::System::Profile::ISystemSetupInfoStatics const &>(
        v6,
        a2);
      _InterlockedDecrement64(&qword_18002EC28);
    }
    else
    {
      *a2 = v4;
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  else
  {
    *a2 = 0;
  }
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v11);
  return a2;
}

```

## disassembly

```asm
0x18000eb28  mov     rax, rsp
0x18000eb2b  mov     [rax+10h], rbx
0x18000eb2f  mov     [rax+20h], rdi
0x18000eb33  mov     [rax+18h], r8
0x18000eb37  mov     [rax+8], rcx
0x18000eb3b  push    rbp
0x18000eb3c  mov     rbp, rsp
0x18000eb3f  sub     rsp, 60h
0x18000eb43  mov     rbx, rdx
0x18000eb46  mov     [rbp+var_30], 26h ; '&'
0x18000eb4e  lea     rax, aWindowsSystemP; "Windows.System.Profile.SystemSetupInfo"
0x18000eb55  lea     rdx, [rbp+var_38]
0x18000eb59  mov     [rbp+var_38], rax
0x18000eb5d  lea     rcx, [rbp+var_28]
0x18000eb61  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000eb66  lea     rdx, [rbp+var_28]
0x18000eb6a  lea     rcx, [rbp+arg_10]
0x18000eb6e  call    ??$get_activation_factory@UISystemSetupInfoStatics@Profile@System@Windows@winrt@@@winrt@@YA?AUISystemSetupInfoStatics@Profile@System@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::System::Profile::ISystemSetupInfoStatics>(winrt::param::hstring const &)
0x18000eb73  mov     rdi, [rbp+arg_10]
0x18000eb77  test    rdi, rdi
0x18000eb7a  jnz     short loc_18000EB84
0x18000eb7c  mov     [rbx], rdi
0x18000eb7f  jmp     loc_18000EC0F
0x18000eb84  mov     rax, [rdi]
0x18000eb87  lea     r8, [rbp+arg_0]
0x18000eb8b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000eb92  mov     [rbp+arg_0], 0
0x18000eb9a  mov     rcx, rdi
0x18000eb9d  mov     rax, [rax]
0x18000eba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba5  mov     rax, [rbp+arg_0]
0x18000eba9  mov     [rbp+arg_0], rax
0x18000ebad  test    rax, rax
0x18000ebb0  jz      short loc_18000EBFD
0x18000ebb2  lea     rcx, [rbp+arg_0]
0x18000ebb6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ebbb  lock inc cs:qword_18002EC28
0x18000ebc3  xor     eax, eax
0x18000ebc5  lock cmpxchg cs:??$factory_cache_entry_v@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::winrt::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>
0x18000ebce  jnz     short loc_18000EBEB
0x18000ebd0  lea     rdx, ListEntry; ListEntry
0x18000ebd7  mov     [rbp+arg_10], 0
0x18000ebdf  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000ebe6  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000ebeb  mov     rdx, rbx
0x18000ebee  call    ??$?RAEBUISystemSetupInfoStatics@Profile@System@Windows@winrt@@@_lambda_a3ebfa5c75b3326c38a94d074ff153a4_@@QEBA?A_PAEBUISystemSetupInfoStatics@Profile@System@Windows@winrt@@@Z
0x18000ebf3  lock dec cs:qword_18002EC28
0x18000ebfb  jmp     short loc_18000EC0F
0x18000ebfd  mov     [rbx], rdi
0x18000ec00  mov     rcx, rdi
0x18000ec03  mov     rax, [rdi]
0x18000ec06  mov     rax, [rax+8]
0x18000ec0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec0f  lea     rcx, [rbp+arg_10]
0x18000ec13  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000ec18  lea     r11, [rsp+60h+var_s0]
0x18000ec1d  mov     rax, rbx
0x18000ec20  mov     rbx, [r11+18h]
0x18000ec24  mov     rdi, [r11+28h]
0x18000ec28  mov     rsp, r11
0x18000ec2b  pop     rbp
0x18000ec2c  retn
```
