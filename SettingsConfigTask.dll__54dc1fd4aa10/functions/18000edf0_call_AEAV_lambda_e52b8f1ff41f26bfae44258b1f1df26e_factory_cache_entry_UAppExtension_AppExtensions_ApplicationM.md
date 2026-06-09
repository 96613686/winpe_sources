# ??$call@AEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@Z

- ea: `0x18000edf0`
- end: `0x18000ef6d`
- name: `??$call@AEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@Z`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800135d8`

## callees

- `0x1800033e1`
- `0x18000edf0`
- `0x18000fbc4`
- `0x180012048`
- `0x180012514`
- `0x18001d2e8`
- `0x1800215e8`
- `0x180024010`

## string_xrefs

- `0x18000ee02`: `WindowsUdk.ApplicationModel.AppExtensions.AppExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::call<_lambda_e52b8f1ff41f26bfae44258b1f1df26e_ &>(
        __int64 a1,
        unsigned int **a2)
{
  signed __int64 v3; // rbx
  unsigned int v4; // eax
  unsigned int v5; // eax
  const wchar_t *v7; // [rsp+20h] [rbp-40h] BYREF
  __int128 v8; // [rsp+28h] [rbp-38h]
  _QWORD v9[5]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+80h] [rbp+20h] BYREF
  void (__fastcall ***v11)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+30h] BYREF
  __int64 *v12; // [rsp+98h] [rbp+38h]

  v10 = a1;
  v7 = L"WindowsUdk.ApplicationModel.AppExtensions.AppExtension";
  *(_QWORD *)&v8 = 54;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    (__int64)winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
    (__int64)&v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v3 = (signed __int64)v11;
  if ( v11 && (v10 = 0, (**v11)(v11, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v12 = &qword_18002EC08;
    _InterlockedIncrement64(&qword_18002EC08);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
            v3,
            0) )
    {
      v11 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002EC10);
    }
    LODWORD(v7) = 0;
    v8 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
                                                    + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
           **a2);
    winrt::check_hresult(&v10, v4, &v7);
    _InterlockedDecrement64(&qword_18002EC08);
  }
  else
  {
    LODWORD(v7) = 0;
    v8 = 0;
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, **a2);
    winrt::check_hresult(&v10, v5, &v7);
  }
  return winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v11);
}

```

## disassembly

```asm
0x18000edf0  mov     [rsp-18h+arg_0], rcx
0x18000edf5  push    rbp
0x18000edf6  push    rbx
0x18000edf7  push    rdi
0x18000edf8  mov     rbp, rsp
0x18000edfb  sub     rsp, 60h
0x18000edff  mov     rdi, rdx
0x18000ee02  lea     rax, aWindowsudkAppl; "WindowsUdk.ApplicationModel.AppExtensio"...
0x18000ee09  mov     [rbp+var_40], rax
0x18000ee0d  mov     qword ptr [rbp+var_38], 36h ; '6'
0x18000ee15  lea     rdx, [rbp+var_40]
0x18000ee19  lea     rcx, [rbp+var_28]
0x18000ee1d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000ee22  mov     [rbp+arg_10], 0
0x18000ee2a  mov     dword ptr [rbp+var_40], 0
0x18000ee31  xorps   xmm0, xmm0
0x18000ee34  movdqu  [rbp+var_38], xmm0
0x18000ee39  lea     r9, [rbp+arg_10]
0x18000ee3d  lea     r8, ??$guid_v@UIAppExtensionStatics2@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x18000ee44  lea     rdx, [rbp+var_28]
0x18000ee48  lea     rcx, [rbp+arg_0]
0x18000ee4c  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000ee51  lea     r8, [rbp+var_40]
0x18000ee55  mov     edx, dword ptr [rbp+arg_0]
0x18000ee58  lea     rcx, [rbp+arg_0]
0x18000ee5c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ee61  mov     rbx, [rbp+arg_10]
0x18000ee65  mov     [rbp+arg_10], rbx
0x18000ee69  test    rbx, rbx
0x18000ee6c  jz      loc_18000EF29
0x18000ee72  mov     [rbp+arg_0], 0
0x18000ee7a  mov     rax, [rbx]
0x18000ee7d  lea     r8, [rbp+arg_0]
0x18000ee81  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000ee88  mov     rcx, rbx
0x18000ee8b  mov     rax, [rax]
0x18000ee8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee93  mov     rax, [rbp+arg_0]
0x18000ee97  mov     [rbp+arg_0], rax
0x18000ee9b  test    rax, rax
0x18000ee9e  jz      loc_18000EF29
0x18000eea4  lea     rcx, [rbp+arg_0]
0x18000eea8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000eead  lea     rax, qword_18002EC08
0x18000eeb4  mov     [rbp+arg_18], rax
0x18000eeb8  lock inc cs:qword_18002EC08
0x18000eec0  xor     eax, eax
0x18000eec2  lock cmpxchg cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x18000eecb  jnz     short loc_18000EEE8
0x18000eecd  mov     [rbp+arg_10], 0
0x18000eed5  lea     rdx, stru_18002EC10; ListEntry
0x18000eedc  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000eee3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000eee8  mov     rcx, cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x18000eeef  mov     dword ptr [rbp+var_40], 0
0x18000eef6  xorps   xmm0, xmm0
0x18000eef9  movdqu  [rbp+var_38], xmm0
0x18000eefe  mov     rax, [rcx]
0x18000ef01  mov     rdx, [rdi]
0x18000ef04  mov     edx, [rdx]
0x18000ef06  mov     rax, [rax+30h]
0x18000ef0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef0f  lea     r8, [rbp+var_40]
0x18000ef13  mov     edx, eax
0x18000ef15  lea     rcx, [rbp+arg_0]
0x18000ef19  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ef1e  nop
0x18000ef1f  lock dec cs:qword_18002EC08
0x18000ef27  jmp     short loc_18000EF5C
0x18000ef29  mov     dword ptr [rbp+var_40], 0
0x18000ef30  xorps   xmm0, xmm0
0x18000ef33  movdqu  [rbp+var_38], xmm0
0x18000ef38  mov     rax, [rbx]
0x18000ef3b  mov     rdx, [rdi]
0x18000ef3e  mov     edx, [rdx]
0x18000ef40  mov     rcx, rbx
0x18000ef43  mov     rax, [rax+30h]
0x18000ef47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef4c  lea     r8, [rbp+var_40]
0x18000ef50  mov     edx, eax
0x18000ef52  lea     rcx, [rbp+arg_0]
0x18000ef56  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ef5b  nop
0x18000ef5c  lea     rcx, [rbp+arg_10]
0x18000ef60  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000ef65  add     rsp, 60h
0x18000ef69  pop     rdi
0x18000ef6a  pop     rbx
0x18000ef6b  pop     rbp
0x18000ef6c  retn
```
