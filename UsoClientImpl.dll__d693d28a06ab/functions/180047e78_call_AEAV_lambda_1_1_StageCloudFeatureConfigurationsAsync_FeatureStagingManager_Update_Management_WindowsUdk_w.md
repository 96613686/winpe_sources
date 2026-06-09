# ??$call@AEAV_lambda_1_@?1??StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@winrt@@SA@AEBU?$map@Uhstring@winrt@@U12@@param@7@@Z@@?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@2@SA@AEBU?$map@Uhstring@winrt@@U12@@param@2@@Z@@Z

- ea: `0x180047e78`
- end: `0x180047ff2`
- name: `??$call@AEAV_lambda_1_@?1??StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@winrt@@SA@AEBU?$map@Uhstring@winrt@@U12@@param@7@@Z@@?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@2@SA@AEBU?$map@Uhstring@winrt@@U12@@param@2@@Z@@Z`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180047ff8`

## callees

- `0x18002d1a4`
- `0x180035a50`
- `0x180047e08`
- `0x180047e78`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x180047ead`: `WindowsUdk.Management.Update.FeatureStagingManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__StageCloudFeatureConfigurationsAsync_FeatureStagingManager_Update_Management_WindowsUdk_winrt__SA_AEBU__map_Uhstring_winrt__U12__param_7__Z____factory_cache_entry_UFeatureStagingManager_Update_Management_WindowsUdk_winrt__UIFeatureStagingManagerStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__StageCloudFeatureConfigurationsAsync_FeatureStagingManager_Update_Management_WindowsUdk_2_SA_AEBU__map_Uhstring_winrt__U12__param_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  _QWORD v9[2]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v10; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v11[4]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-28h]
  __int64 *v13; // [rsp+50h] [rbp-20h]
  _QWORD *v14; // [rsp+58h] [rbp-18h] BYREF

  v14 = a2;
  v11[0] = 1;
  v11[1] = 50;
  v12 = L"WindowsUdk.Management.Update.FeatureStagingManager";
  v10 = v11;
  winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>(v9, &v10);
  v5 = v9[0];
  if ( !v9[0]
    || (v14 = 0,
        (**(void (__fastcall ***)(_QWORD, __int64 *, _QWORD **))v9[0])(
          v9[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v14),
        !v14) )
  {
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v14);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7);
    *a2 = v14;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  v13 = &qword_18009FB18;
  _InterlockedIncrement64(&qword_18009FB18);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v9[0] = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009FB20);
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>,
         **a3,
         &v14);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  *a2 = v14;
  _InterlockedDecrement64(&qword_18009FB18);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x180047e78  mov     [rsp-18h+arg_0], rbx
0x180047e7d  push    rbp
0x180047e7e  push    rsi
0x180047e7f  push    rdi
0x180047e80  mov     rbp, rsp
0x180047e83  sub     rsp, 70h
0x180047e87  mov     rax, cs:__security_cookie
0x180047e8e  xor     rax, rsp
0x180047e91  mov     [rbp+var_10], rax
0x180047e95  mov     rsi, r8
0x180047e98  mov     rdi, rdx
0x180047e9b  mov     [rbp+var_18], rdx
0x180047e9f  mov     [rbp+var_38], 1
0x180047ea6  mov     [rbp+var_34], 32h ; '2'
0x180047ead  lea     rax, aWindowsudkMana; "WindowsUdk.Management.Update.FeatureSta"...
0x180047eb4  mov     [rbp+var_28], rax
0x180047eb8  lea     rax, [rbp+var_38]
0x180047ebc  mov     [rbp+var_40], rax
0x180047ec0  lea     rdx, [rbp+var_40]
0x180047ec4  lea     rcx, [rbp+var_50]
0x180047ec8  call    ??$get_activation_factory@UIFeatureStagingManagerStatics@Update@Management@WindowsUdk@winrt@@@winrt@@YA?AUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>(winrt::param::hstring const &)
0x180047ecd  nop
0x180047ece  mov     rbx, [rbp+var_50]
0x180047ed2  test    rbx, rbx
0x180047ed5  jz      loc_180047F8E
0x180047edb  mov     [rbp+var_18], 0
0x180047ee3  mov     rax, [rbx]
0x180047ee6  lea     r8, [rbp+var_18]
0x180047eea  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180047ef1  mov     rcx, rbx
0x180047ef4  mov     rax, [rax]
0x180047ef7  call    _guard_dispatch_icall
0x180047efc  mov     rax, [rbp+var_18]
0x180047f00  mov     [rbp+var_18], rax
0x180047f04  test    rax, rax
0x180047f07  jz      loc_180047F8E
0x180047f0d  lea     rcx, [rbp+var_18]
0x180047f11  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047f16  lea     rax, qword_18009FB18
0x180047f1d  mov     [rbp+var_20], rax
0x180047f21  lock inc cs:qword_18009FB18
0x180047f29  xor     eax, eax
0x180047f2b  lock cmpxchg cs:??$factory_cache_entry_v@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@12@A, rbx; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
0x180047f34  jnz     short loc_180047F4F
0x180047f36  xor     ebx, ebx
0x180047f38  mov     [rbp+var_50], rbx
0x180047f3c  lea     rdx, stru_18009FB20; ListEntry
0x180047f43  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180047f4a  call    WINRT_IMPL_InterlockedPushEntrySList
0x180047f4f  mov     [rbp+var_18], 0
0x180047f57  mov     rcx, cs:??$factory_cache_entry_v@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
0x180047f5e  mov     rdx, [rsi]
0x180047f61  mov     rax, [rcx]
0x180047f64  lea     r8, [rbp+var_18]
0x180047f68  mov     rdx, [rdx]
0x180047f6b  mov     rax, [rax+30h]
0x180047f6f  call    _guard_dispatch_icall
0x180047f74  test    eax, eax
0x180047f76  js      short loc_180047FEA
0x180047f78  mov     rcx, [rbp+var_18]
0x180047f7c  mov     [rdi], rcx
0x180047f7f  lock dec cs:qword_18009FB18
0x180047f87  test    rbx, rbx
0x180047f8a  jz      short loc_180047FC3
0x180047f8c  jmp     short loc_180047FBA
0x180047f8e  mov     [rbp+var_18], 0
0x180047f96  mov     rdx, [rsi]
0x180047f99  mov     rax, [rbx]
0x180047f9c  lea     r8, [rbp+var_18]
0x180047fa0  mov     rdx, [rdx]
0x180047fa3  mov     rcx, rbx
0x180047fa6  mov     rax, [rax+30h]
0x180047faa  call    _guard_dispatch_icall
0x180047faf  test    eax, eax
0x180047fb1  js      short loc_180047FE2
0x180047fb3  mov     rax, [rbp+var_18]
0x180047fb7  mov     [rdi], rax
0x180047fba  lea     rcx, [rbp+var_50]
0x180047fbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047fc3  mov     rax, rdi
0x180047fc6  mov     rcx, [rbp+var_10]
0x180047fca  xor     rcx, rsp; StackCookie
0x180047fcd  call    __security_check_cookie
0x180047fd2  mov     rbx, [rsp+70h+arg_0]
0x180047fda  add     rsp, 70h
0x180047fde  pop     rdi
0x180047fdf  pop     rsi
0x180047fe0  pop     rbp
0x180047fe1  retn
0x180047fe2  mov     ecx, eax
0x180047fe4  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180047fea  mov     ecx, eax
0x180047fec  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
