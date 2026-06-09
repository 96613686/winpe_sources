# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession::ActivateBackgroundAndWaitForStart(void)

- ea: `0x18004848c`
- end: `0x180048731`
- name: `?ActivateBackgroundAndWaitForStart@PrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAAXXZ`
- size: `677`
- prototype: `void __fastcall(BackgroundTaskHandler **this)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180048e58`

## callees

- `0x180003ca0`
- `0x1800075ac`
- `0x180008610`
- `0x18000a094`
- `0x18000a724`
- `0x18000b390`
- `0x18000e0ec`
- `0x1800127a4`
- `0x1800128a4`
- `0x180012940`
- `0x1800129f8`
- `0x1800147dc`
- `0x1800147fc`
- `0x180014950`
- `0x1800275e0`
- `0x180029208`
- `0x180029b10`
- `0x18002d9d0`
- `0x18002dafc`
- `0x180031228`
- `0x18003787c`
- `0x180047ae0`
- `0x18004848c`
- `0x180048868`
- `0x18004e904`
- `0x18004e984`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800485da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800485f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800485da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800485f8`

## string_xrefs

- `0x1800486d3`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportextensionbrokersession.cpp`
- `0x1800486e8`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportextensionbrokersession.cpp`
- `0x18004871f`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportextensionbrokersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession::ActivateBackgroundAndWaitForStart(
        BackgroundTaskHandler **this)
{
  __int64 v2; // rbx
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, _QWORD *); // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  struct IBackgroundSessionCallbacks *v6; // rbx
  unsigned int v7; // eax
  void *v8; // rax
  int v9; // esi
  unsigned int v10; // esi
  bool IsPsaDebugEnabled; // al
  bool v12; // di
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // [rsp+20h] [rbp-99h]
  const char *v16; // [rsp+28h] [rbp-91h]
  _QWORD v17[2]; // [rsp+30h] [rbp-89h] BYREF
  __int128 v18; // [rsp+40h] [rbp-79h] BYREF
  __int64 v19; // [rsp+50h] [rbp-69h] BYREF
  __int64 v20; // [rsp+58h] [rbp-61h] BYREF
  int v21; // [rsp+60h] [rbp-59h] BYREF
  __int128 v22; // [rsp+68h] [rbp-51h]
  _QWORD v23[2]; // [rsp+78h] [rbp-41h] BYREF
  __m128i si128; // [rsp+88h] [rbp-31h]
  _QWORD v25[8]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(
    this,
    &v20);
  v2 = v20;
  *(_QWORD *)&v18 = v20;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v18);
  v25[0] = off_180062BD0;
  *(_QWORD *)&v18 = 0;
  v25[1] = v2;
  v25[7] = v25;
  lambda_df897e6668674d5dce194a7e6d974069_::__lambda_df897e6668674d5dce194a7e6d974069_(&v18);
  v3 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *))winrt::make<OnDemandBrokerCallBack,std::function<void (enum BackgroundTaskExitReason)> &>(
                                                                  &v19,
                                                                  v25);
  if ( v3 )
  {
    v17[0] = 0;
    v21 = 0;
    v22 = 0;
    v7 = (**v3)(v3, &winrt::impl::guid_v<IBackgroundSessionCallbacks>, v17);
    winrt::check_hresult(&v18, v7, &v21);
    v6 = (struct IBackgroundSessionCallbacks *)v17[0];
  }
  else
  {
    v6 = 0;
  }
  v17[0] = v6;
  if ( v19 )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v19);
  v18 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(this + 4, &v21, v4, v5);
  winrt::to_string(v23, &v18);
  v8 = (void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v23);
  v9 = BackgroundTaskHandler::LaunchBackGroundTask(this[7], &stru_18006C188, v8, si128.m128i_u32[0], v6);
  LODWORD(v18) = v9;
  PrintSupportTraceLoggingProvider::PsaExtensionSessionBackgroundTaskLaunched<long &>(&v18);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportextensionbrokersession.cpp",
      (const char *)(unsigned int)v9,
      v15);
  v10 = 10000;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    if ( !IsDebuggerPresent() && !BackgroundTaskHandler::IsAppBeingDebugged(this[7]) )
    {
      IsPsaDebugEnabled = PrintCore::PrintSupportDebugHelper::IsPsaDebugEnabled();
      goto LABEL_13;
    }
  }
  else if ( !IsDebuggerPresent() )
  {
    IsPsaDebugEnabled = BackgroundTaskHandler::IsAppBeingDebugged(this[7]);
LABEL_13:
    if ( !IsPsaDebugEnabled )
      goto LABEL_15;
  }
  v10 = -1;
LABEL_15:
  if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                           this + 3,
                           v10) )
  {
    winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession::CancelBackgroundTask((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession *)this);
    v14 = wil::verify_hresult<long>(2147943860LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportextensionbrokersession.cpp",
      (const char *)v14,
      (int)"Background process timeout",
      v16);
  }
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&v19, this + 12);
  v12 = (unsigned int)(*((_DWORD *)this + 12) - 2) <= 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  if ( v12 )
  {
    v13 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportextensionbrokersession.cpp",
      (const char *)v13,
      (int)"Background process terminated unexpectedly",
      v16);
  }
  if ( si128.m128i_i64[1] > 0xFuLL )
    std::_Deallocate<16>(v23[0], si128.m128i_i64[1] + 1);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v23[0]) = 0;
  if ( v6 )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(v17);
  std::function<std::pair<winrt::hstring,unsigned int> (winrt::Windows::Data::Json::JsonObject const &)>::~function<std::pair<winrt::hstring,unsigned int> (winrt::Windows::Data::Json::JsonObject const &)>(v25);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
}

```

## disassembly

```asm
0x18004848c  push    rbp
0x18004848e  push    rbx
0x18004848f  push    rsi
0x180048490  push    rdi
0x180048491  lea     rbp, [rsp-3Fh]
0x180048496  sub     rsp, 0F8h
0x18004849d  mov     rax, cs:__security_cookie
0x1800484a4  xor     rax, rsp
0x1800484a7  mov     [rbp+57h+var_30], rax
0x1800484ab  mov     rdi, rcx
0x1800484ae  lea     rdx, [rbp+57h+var_B8]
0x1800484b2  call    ??$get_weak@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@?$root_implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U1345678@@impl@winrt@@IEAA?AU?$weak_ref@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@2@XZ; winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(void)
0x1800484b7  nop
0x1800484b8  mov     rbx, [rbp+57h+var_B8]
0x1800484bc  mov     qword ptr [rbp+57h+var_D0], rbx
0x1800484c0  lea     rcx, [rbp+57h+var_D0]
0x1800484c4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800484c9  lea     rax, off_180062BD0
0x1800484d0  mov     [rbp+57h+var_70], rax
0x1800484d4  mov     qword ptr [rbp+57h+var_D0], 0
0x1800484dc  mov     [rbp+57h+var_68], rbx
0x1800484e0  lea     rax, [rbp+57h+var_70]
0x1800484e4  mov     [rbp+57h+var_38], rax
0x1800484e8  lea     rcx, [rbp+57h+var_D0]
0x1800484ec  call    _lambda_df897e6668674d5dce194a7e6d974069_____lambda_df897e6668674d5dce194a7e6d974069_
0x1800484f1  lea     rdx, [rbp+57h+var_70]
0x1800484f5  lea     rcx, [rbp+57h+var_C0]
0x1800484f9  call    ??$make@UOnDemandBrokerCallBack@@AEAV?$function@$$A6AXW4BackgroundTaskExitReason@@@Z@std@@@winrt@@YA?A_PAEAV?$function@$$A6AXW4BackgroundTaskExitReason@@@Z@std@@@Z
0x1800484fe  nop
0x1800484ff  mov     rcx, [rax]
0x180048502  test    rcx, rcx
0x180048505  jnz     short loc_18004850B
0x180048507  xor     ebx, ebx
0x180048509  jmp     short loc_18004854E
0x18004850b  mov     [rsp+110h+var_E0], 0
0x180048514  mov     [rbp+57h+var_B0], 0
0x18004851b  xorps   xmm0, xmm0
0x18004851e  movdqu  [rbp+57h+var_A8], xmm0
0x180048523  mov     rax, [rcx]
0x180048526  lea     r8, [rsp+110h+var_E0]
0x18004852b  lea     rdx, ??$guid_v@UIBackgroundSessionCallbacks@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IBackgroundSessionCallbacks>
0x180048532  mov     rax, [rax]
0x180048535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004853a  lea     r8, [rbp+57h+var_B0]
0x18004853e  mov     edx, eax
0x180048540  lea     rcx, [rbp+57h+var_D0]
0x180048544  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180048549  mov     rbx, [rsp+110h+var_E0]
0x18004854e  mov     [rsp+110h+var_E0], rbx
0x180048553  cmp     [rbp+57h+var_C0], 0
0x180048558  jz      short loc_180048563
0x18004855a  lea     rcx, [rbp+57h+var_C0]
0x18004855e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180048563  lea     rcx, [rdi+20h]
0x180048567  lea     rdx, [rbp+57h+var_B0]
0x18004856b  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180048570  movups  xmm0, xmmword ptr [rax]
0x180048573  movdqu  [rbp+57h+var_D0], xmm0
0x180048578  lea     rdx, [rbp+57h+var_D0]
0x18004857c  lea     rcx, [rbp+57h+var_98]
0x180048580  call    ?to_string@winrt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; winrt::to_string(std::basic_string_view<ushort>)
0x180048585  nop
0x180048586  lea     rcx, [rbp+57h+var_98]
0x18004858a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEAAPEADXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004858f  mov     r8, rax; void *
0x180048592  mov     [rsp+110h+var_F0], rbx; int
0x180048597  mov     r9d, dword ptr [rbp+57h+var_88]; unsigned int
0x18004859b  lea     rdx, stru_18006C188; struct _GUID *
0x1800485a2  mov     rcx, [rdi+38h]; this
0x1800485a6  call    ?LaunchBackGroundTask@BackgroundTaskHandler@@QEAAJPEBU_GUID@@PEAXKPEAUIBackgroundSessionCallbacks@@@Z; BackgroundTaskHandler::LaunchBackGroundTask(_GUID const *,void *,ulong,IBackgroundSessionCallbacks *)
0x1800485ab  mov     esi, eax
0x1800485ad  mov     dword ptr [rbp+57h+var_D0], eax
0x1800485b0  lea     rcx, [rbp+57h+var_D0]
0x1800485b4  call    ??$PsaExtensionSessionBackgroundTaskLaunched@AEAJ@PrintSupportTraceLoggingProvider@@SAXAEAJ@Z; PrintSupportTraceLoggingProvider::PsaExtensionSessionBackgroundTaskLaunched<long &>(long &)
0x1800485b9  mov     rcx, [rbp+5Fh]; this
0x1800485bd  test    esi, esi
0x1800485bf  js      loc_1800486E5
0x1800485c5  mov     esi, 2710h
0x1800485ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x1800485d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x1800485d6  test    al, al
0x1800485d8  jz      short loc_1800485F8
0x1800485da  call    cs:__imp_IsDebuggerPresent
0x1800485e0  test    eax, eax
0x1800485e2  jnz     short loc_18004860F
0x1800485e4  mov     rcx, [rdi+38h]; this
0x1800485e8  call    ?IsAppBeingDebugged@BackgroundTaskHandler@@QEAA_NXZ; BackgroundTaskHandler::IsAppBeingDebugged(void)
0x1800485ed  test    al, al
0x1800485ef  jnz     short loc_18004860F
0x1800485f1  call    ?IsPsaDebugEnabled@PrintSupportDebugHelper@PrintCore@@SA_NXZ; PrintCore::PrintSupportDebugHelper::IsPsaDebugEnabled(void)
0x1800485f6  jmp     short loc_18004860B
0x1800485f8  call    cs:__imp_IsDebuggerPresent
0x1800485fe  test    eax, eax
0x180048600  jnz     short loc_18004860F
0x180048602  mov     rcx, [rdi+38h]; this
0x180048606  call    ?IsAppBeingDebugged@BackgroundTaskHandler@@QEAA_NXZ; BackgroundTaskHandler::IsAppBeingDebugged(void)
0x18004860b  test    al, al
0x18004860d  jz      short loc_180048612
0x18004860f  or      esi, 0FFFFFFFFh
0x180048612  lea     rcx, [rdi+18h]
0x180048616  mov     edx, esi
0x180048618  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18004861d  test    al, al
0x18004861f  jz      loc_1800486FA
0x180048625  lea     rdx, [rdi+60h]
0x180048629  lea     rcx, [rbp+57h+var_C0]
0x18004862d  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180048632  mov     eax, [rdi+30h]
0x180048635  sub     eax, 2
0x180048638  cmp     eax, 1
0x18004863b  setbe   dil
0x18004863f  lea     rcx, [rbp+57h+var_C0]
0x180048643  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180048648  test    dil, dil
0x18004864b  jnz     short loc_1800486B6
0x18004864d  mov     rdx, qword ptr [rbp+57h+var_88+8]
0x180048651  cmp     rdx, 0Fh
0x180048655  jbe     short loc_180048663
0x180048657  inc     rdx
0x18004865a  mov     rcx, [rbp+57h+var_98]
0x18004865e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180048663  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18004866b  movdqu  [rbp+57h+var_88], xmm0
0x180048670  mov     byte ptr [rbp+57h+var_98], 0
0x180048674  test    rbx, rbx
0x180048677  jz      short loc_180048684
0x180048679  lea     rcx, [rsp+110h+var_E0]
0x18004867e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180048683  nop
0x180048684  lea     rcx, [rbp+57h+var_70]
0x180048688  call    ??1?$function@$$A6A?AU?$pair@Uhstring@winrt@@I@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z@std@@QEAA@XZ; std::function<std::pair<winrt::hstring,uint> (winrt::Windows::Data::Json::JsonObject const &)>::~function<std::pair<winrt::hstring,uint> (winrt::Windows::Data::Json::JsonObject const &)>(void)
0x18004868d  nop
0x18004868e  cmp     [rbp+57h+var_B8], 0
0x180048693  jz      short loc_18004869E
0x180048695  lea     rcx, [rbp+57h+var_B8]
0x180048699  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004869e  mov     rcx, [rbp+57h+var_30]
0x1800486a2  xor     rcx, rsp; StackCookie
0x1800486a5  call    __security_check_cookie
0x1800486aa  add     rsp, 0F8h
0x1800486b1  pop     rdi
0x1800486b2  pop     rsi
0x1800486b3  pop     rbx
0x1800486b4  pop     rbp
0x1800486b5  retn
0x1800486b6  mov     ecx, 8000FFFFh
0x1800486bb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800486c0  mov     r9d, eax; char *
0x1800486c3  mov     rcx, [rbp+5Fh]; this
0x1800486c7  lea     rax, aBackgroundProc; "Background process terminated unexpecte"...
0x1800486ce  mov     [rsp+110h+var_F0], rax; int
0x1800486d3  lea     r8, aOnecoreuapPrin_13; "onecoreuap\\printscan\\print\\workflow"...
0x1800486da  mov     edx, 0EBh; void *
0x1800486df  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800486e5  mov     r9d, esi; char *
0x1800486e8  lea     r8, aOnecoreuapPrin_13; "onecoreuap\\printscan\\print\\workflow"...
0x1800486ef  mov     edx, 0E1h; void *
0x1800486f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800486fa  mov     rcx, rdi; this
0x1800486fd  call    ?CancelBackgroundTask@PrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession::CancelBackgroundTask(void)
0x180048702  mov     ecx, 800705B4h
0x180048707  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004870c  mov     r9d, eax; char *
0x18004870f  mov     rcx, [rbp+5Fh]; this
0x180048713  lea     rax, aBackgroundProc_0; "Background process timeout"
0x18004871a  mov     [rsp+110h+var_F0], rax; int
0x18004871f  lea     r8, aOnecoreuapPrin_13; "onecoreuap\\printscan\\print\\workflow"...
0x180048726  mov     edx, 0E7h; void *
0x18004872b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
