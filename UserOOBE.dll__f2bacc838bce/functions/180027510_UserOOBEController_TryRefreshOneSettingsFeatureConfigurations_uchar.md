# UserOOBEController::TryRefreshOneSettingsFeatureConfigurations(uchar *)

- ea: `0x180027510`
- end: `0x1800278d1`
- name: `?TryRefreshOneSettingsFeatureConfigurations@UserOOBEController@@UEAAJPEAE@Z`
- size: `961`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800032b0`
- `0x1800056c8`
- `0x18000a528`
- `0x18000e2bc`
- `0x18001136c`
- `0x180012328`
- `0x1800216d4`
- `0x180022bac`
- `0x180023010`
- `0x180027510`
- `0x180027ab0`
- `0x18002adac`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002760b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002773a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002760b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002773a`

## string_xrefs

- `0x18002787f`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180027894`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800278a9`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800278be`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall UserOOBEController::TryRefreshOneSettingsFeatureConfigurations(
        UserOOBEController *this,
        unsigned __int8 *a2)
{
  char v3; // r14
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // eax
  int ActivationFactory; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v10; // rbx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v15; // rbx
  int v16; // eax
  const char *v17; // r9
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-128h]
  __int64 v20; // [rsp+30h] [rbp-118h] BYREF
  __int64 v21; // [rsp+38h] [rbp-110h] BYREF
  __int64 v22; // [rsp+40h] [rbp-108h] BYREF
  __int64 v23; // [rsp+48h] [rbp-100h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-E0h]
  HSTRING_HEADER v26; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+88h] [rbp-C0h]
  _BYTE v28[8]; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD v29[14]; // [rsp+98h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    *a2 = 0;
    v3 = 1;
    LODWORD(v20) = 1;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &v22,
      (int *)&v20);
    v29[0] = off_180050428;
    v29[1] = &v22;
    v29[13] = v29;
    v21 = 0;
    v6 = wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v4, v28, v5, &v21);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v6,
        v19);
    v23 = v21;
    wistd::function<void (void)>::~function<void (void)>(v28);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeForceFeatureConfigurations>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeForceFeatureConfigurations>::GetImpl'::`2'::impl) )
    {
      v21 = 0;
      v25 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
        0x3Au,
        0x39u);
      ActivationFactory = RoGetActivationFactory(v25, &GUID_28f28e22_0ecf_45cc_a9b6_fe4148ac1268, &v21);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x12A,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v19);
      v20 = 0;
      v8 = v21;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v21 + 48LL);
      v20 = 0;
      v25 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &qword_180054928, 1u, 0);
      v10 = v25;
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v26, L"FCON", 5u, 4u);
      v11 = v9(v8, v27, v10, &v20);
      if ( v11 >= 0 || v11 == -2147012889 || v11 == -2147012894 || v11 == -2147024894 || v11 == -2147023665 )
        v3 = 0;
      if ( v3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x130,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v11,
          v19);
      if ( v11 >= 0 )
        *a2 = _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                &v22,
                15000);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
    }
    else
    {
      v20 = 0;
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v26,
        L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
        0x3Au,
        0x39u);
      v12 = RoGetActivationFactory(v27, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v20);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v12,
          v19);
      v21 = 0;
      v13 = v20;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v20 + 56LL);
      v21 = 0;
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v26, &qword_180054928, 1u, 0);
      v15 = v27;
      v25 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"FCON", 5u, 4u);
      v16 = v14(v13, v25, v15, &v21);
      if ( v16 >= 0 || v16 == -2147012889 || v16 == -2147012894 || v16 == -2147024894 || v16 == -2147023665 )
        v3 = 0;
      if ( v3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x13F,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v16,
          v19);
      if ( v16 >= 0 )
        *a2 = _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                &v22,
                15000);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
    }
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x146,
                           (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x180027510  push    rbx
0x180027512  push    rsi
0x180027513  push    rdi
0x180027514  push    r12
0x180027516  push    r14
0x180027518  push    r15
0x18002751a  sub     rsp, 118h
0x180027521  mov     rax, cs:__security_cookie
0x180027528  xor     rax, rsp
0x18002752b  mov     [rsp+148h+var_40], rax
0x180027533  mov     r15, rdx
0x180027536  xor     r12d, r12d
0x180027539  mov     [rdx], r12b
0x18002753c  lea     r14d, [r12+1]
0x180027541  mov     dword ptr [rsp+148h+var_118], r14d
0x180027546  lea     rdx, [rsp+148h+var_118]
0x18002754b  lea     rcx, [rsp+148h+var_108]
0x180027550  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180027555  nop
0x180027556  lea     rax, off_180050428
0x18002755d  mov     [rsp+148h+var_B0], rax
0x180027565  lea     rax, [rsp+148h+var_108]
0x18002756a  mov     [rsp+148h+var_A8], rax
0x180027572  lea     rax, [rsp+148h+var_B0]
0x18002757a  mov     [rsp+148h+var_48], rax
0x180027582  mov     [rsp+148h+var_110], r12
0x180027587  lea     r9, [rsp+148h+var_110]
0x18002758c  lea     rdx, [rsp+148h+var_B8]
0x180027594  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x180027599  mov     rcx, [rsp+148h]; this
0x1800275a1  test    eax, eax
0x1800275a3  js      loc_180027867
0x1800275a9  mov     rax, [rsp+148h+var_110]
0x1800275ae  mov     [rsp+148h+var_100], rax
0x1800275b3  lea     rcx, [rsp+148h+var_B8]
0x1800275bb  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x1800275c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeForceFeatureConfigurations@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeForceFeatureConfigurations@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeForceFeatureConfigurations> `wil::Feature<__WilFeatureTraits_Feature_OobeForceFeatureConfigurations>::GetImpl(void)'::`2'::impl
0x1800275c7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeForceFeatureConfigurations@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeForceFeatureConfigurations>::__private_IsEnabled(void)
0x1800275cc  test    al, al
0x1800275ce  jz      loc_1800276FD
0x1800275d4  mov     [rsp+148h+var_110], r12
0x1800275d9  mov     [rsp+148h+var_E0], r12
0x1800275de  mov     r9d, 39h ; '9'; unsigned int
0x1800275e4  lea     r8d, [r9+1]; unsigned int
0x1800275e8  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1800275ef  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x1800275f4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800275f9  nop
0x1800275fa  lea     r8, [rsp+148h+var_110]
0x1800275ff  lea     rdx, _GUID_28f28e22_0ecf_45cc_a9b6_fe4148ac1268
0x180027606  mov     rcx, [rsp+148h+var_E0]
0x18002760b  call    cs:__imp_RoGetActivationFactory
0x180027611  mov     rcx, [rsp+148h]; this
0x180027619  test    eax, eax
0x18002761b  js      loc_18002787C
0x180027621  mov     [rsp+148h+var_118], r12
0x180027626  mov     rsi, [rsp+148h+var_110]
0x18002762b  mov     rax, [rsi]
0x18002762e  mov     rdi, [rax+30h]
0x180027632  mov     [rsp+148h+var_118], r12
0x180027637  mov     [rsp+148h+var_E0], r12
0x18002763c  xor     r9d, r9d; unsigned int
0x18002763f  mov     r8d, r14d; unsigned int
0x180027642  lea     rdx, qword_180054928; sourceString
0x180027649  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x18002764e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027653  nop
0x180027654  mov     rbx, [rsp+148h+var_E0]
0x180027659  mov     [rsp+148h+var_C0], r12
0x180027661  mov     r9d, 4; unsigned int
0x180027667  lea     r8d, [r9+1]; unsigned int
0x18002766b  lea     rdx, aFcon; "FCON"
0x180027672  lea     rcx, [rsp+148h+var_D8]; hstringHeader
0x180027677  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002767c  nop
0x18002767d  lea     r9, [rsp+148h+var_118]
0x180027682  mov     r8, rbx
0x180027685  mov     rdx, [rsp+148h+var_C0]
0x18002768d  mov     rcx, rsi
0x180027690  mov     rax, rdi
0x180027693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027698  nop
0x180027699  test    eax, eax
0x18002769b  jns     short loc_1800276B9
0x18002769d  cmp     eax, 80072EE7h
0x1800276a2  jz      short loc_1800276B9
0x1800276a4  cmp     eax, 80072EE2h
0x1800276a9  jz      short loc_1800276B9
0x1800276ab  cmp     eax, 80070002h
0x1800276b0  jz      short loc_1800276B9
0x1800276b2  cmp     eax, 800704CFh
0x1800276b7  jnz     short loc_1800276BC
0x1800276b9  mov     r14b, r12b
0x1800276bc  mov     rcx, [rsp+148h]; this
0x1800276c4  test    r14b, r14b
0x1800276c7  jnz     loc_180027891
0x1800276cd  test    eax, eax
0x1800276cf  js      short loc_1800276E3
0x1800276d1  mov     edx, 3A98h
0x1800276d6  lea     rcx, [rsp+148h+var_108]
0x1800276db  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x1800276e0  mov     [r15], al
0x1800276e3  lea     rcx, [rsp+148h+var_118]
0x1800276e8  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800276ed  nop
0x1800276ee  lea     rcx, [rsp+148h+var_110]
0x1800276f3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800276f8  jmp     loc_180027828
0x1800276fd  mov     [rsp+148h+var_118], r12
0x180027702  mov     [rsp+148h+var_C0], r12
0x18002770a  mov     r9d, 39h ; '9'; unsigned int
0x180027710  lea     r8d, [r9+1]; unsigned int
0x180027714  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18002771b  lea     rcx, [rsp+148h+var_D8]; hstringHeader
0x180027720  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027725  nop
0x180027726  lea     r8, [rsp+148h+var_118]
0x18002772b  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x180027732  mov     rcx, [rsp+148h+var_C0]
0x18002773a  call    cs:__imp_RoGetActivationFactory
0x180027740  mov     rcx, [rsp+148h]; this
0x180027748  test    eax, eax
0x18002774a  js      loc_1800278A6
0x180027750  mov     [rsp+148h+var_110], r12
0x180027755  mov     rsi, [rsp+148h+var_118]
0x18002775a  mov     rax, [rsi]
0x18002775d  mov     rdi, [rax+38h]
0x180027761  mov     [rsp+148h+var_110], r12
0x180027766  mov     [rsp+148h+var_C0], r12
0x18002776e  xor     r9d, r9d; unsigned int
0x180027771  mov     r8d, r14d; unsigned int
0x180027774  lea     rdx, qword_180054928; sourceString
0x18002777b  lea     rcx, [rsp+148h+var_D8]; hstringHeader
0x180027780  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027785  nop
0x180027786  mov     rbx, [rsp+148h+var_C0]
0x18002778e  mov     [rsp+148h+var_E0], r12
0x180027793  mov     r9d, 4; unsigned int
0x180027799  lea     r8d, [r9+1]; unsigned int
0x18002779d  lea     rdx, aFcon; "FCON"
0x1800277a4  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x1800277a9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800277ae  nop
0x1800277af  lea     r9, [rsp+148h+var_110]
0x1800277b4  mov     r8, rbx
0x1800277b7  mov     rdx, [rsp+148h+var_E0]
0x1800277bc  mov     rcx, rsi
0x1800277bf  mov     rax, rdi
0x1800277c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277c7  nop
0x1800277c8  test    eax, eax
0x1800277ca  jns     short loc_1800277E8
0x1800277cc  cmp     eax, 80072EE7h
0x1800277d1  jz      short loc_1800277E8
0x1800277d3  cmp     eax, 80072EE2h
0x1800277d8  jz      short loc_1800277E8
0x1800277da  cmp     eax, 80070002h
0x1800277df  jz      short loc_1800277E8
0x1800277e1  cmp     eax, 800704CFh
0x1800277e6  jnz     short loc_1800277EB
0x1800277e8  mov     r14b, r12b
0x1800277eb  mov     rcx, [rsp+148h]; this
0x1800277f3  test    r14b, r14b
0x1800277f6  jnz     loc_1800278BB
0x1800277fc  test    eax, eax
0x1800277fe  js      short loc_180027812
0x180027800  mov     edx, 3A98h
0x180027805  lea     rcx, [rsp+148h+var_108]
0x18002780a  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18002780f  mov     [r15], al
0x180027812  lea     rcx, [rsp+148h+var_110]
0x180027817  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002781c  nop
0x18002781d  lea     rcx, [rsp+148h+var_118]
0x180027822  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180027827  nop
0x180027828  lea     rcx, [rsp+148h+var_100]
0x18002782d  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180027832  nop
0x180027833  lea     rcx, [rsp+148h+var_108]
0x180027838  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002783d  nop
0x18002783e  xor     eax, eax
0x180027840  jmp     short loc_180027846
0x180027842  mov     eax, dword ptr [rsp+148h+var_118]
0x180027846  mov     rcx, [rsp+148h+var_40]
0x18002784e  xor     rcx, rsp; StackCookie
0x180027851  call    __security_check_cookie
0x180027856  add     rsp, 118h
0x18002785d  pop     r15
0x18002785f  pop     r14
0x180027861  pop     r12
0x180027863  pop     rdi
0x180027864  pop     rsi
0x180027865  pop     rbx
0x180027866  retn
0x180027867  mov     r9d, eax; char *
0x18002786a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180027871  mov     edx, 43Ch; void *
0x180027876  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002787c  mov     r9d, eax; char *
0x18002787f  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180027886  mov     edx, 12Ah; void *
0x18002788b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027891  mov     r9d, eax; char *
0x180027894  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002789b  mov     edx, 130h; void *
0x1800278a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800278a6  mov     r9d, eax; char *
0x1800278a9  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800278b0  mov     edx, 139h; void *
0x1800278b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800278bb  mov     r9d, eax; char *
0x1800278be  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800278c5  mov     edx, 13Fh; void *
0x1800278ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
