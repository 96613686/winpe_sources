# ThreadManager::ThreadProc(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&)

- ea: `0x180016660`
- end: `0x180016b2c`
- name: `?ThreadProc@ThreadManager@@AEAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@Z`
- size: `1228`
- prototype: `__int64 __fastcall(ThreadManager *this)`
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x1800041c4`
- `0x1800049ac`
- `0x1800088ac`
- `0x180009ff0`
- `0x18000a130`
- `0x18000a1ac`
- `0x18000ae94`
- `0x18000d504`
- `0x18000e130`
- `0x18000e2a0`
- `0x18000ecd8`
- `0x18000edc0`
- `0x18000ee7c`
- `0x18000f454`
- `0x18000f52c`
- `0x18001049c`
- `0x180012eec`
- `0x18001600c`
- `0x180016038`
- `0x180016634`
- `0x180016660`
- `0x180016b34`
- `0x180016b60`
- `0x180017024`
- `0x180017124`
- `0x180017164`
- `0x1800171a0`
- `0x1800176b0`
- `0x180017a90`
- `0x18001d36c`
- `0x18004488c`
- `0x1800450ac`
- `0x18004b29c`
- `0x18004cda8`
- `0x18004d0b8`
- `0x18004d1ec`
- `0x18005a010`

## import_xrefs

- `combase!__imp_RoInitializeStrict` at `0x180016695`
- `combase!__imp_RoInitializeStrict` at `0x180016695`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180016958`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180016958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001694d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001694d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016934`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016934`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800166d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800169ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800166d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800169ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a59`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180016a9f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180016a9f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001674c`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001674c`
- `msvcp_win!_Thrd_id` at `0x180016708`
- `msvcp_win!_Thrd_id` at `0x180016708`

## string_xrefs

- `0x180016ac9`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`
- `0x180016ade`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`
- `0x180016af0`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`
- `0x180016b02`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`
- `0x180016b17`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ThreadManager::ThreadProc(RTL_SRWLOCK *this, struct SpecializationData **a2)
{
  int v4; // eax
  UXFrame *v5; // r14
  const char *v6; // r9
  RTL_SRWLOCK *v7; // r13
  __int64 *Ptr; // rdi
  __int64 *i; // rbx
  _QWORD *v10; // rdi
  __int128 v11; // xmm0
  __int64 *v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  RTL_SRWLOCK *v16; // rcx
  void *v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rdi
  _QWORD *j; // rbx
  wil::details **v21; // rax
  wil::details *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  const char *v25; // r9
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  HANDLE CurrentProcess; // rax
  ThreadManager *v29; // rcx
  bool IsUsingXaml; // bl
  __int64 v31; // rax
  const char *v32; // r9
  const char *v33; // r9
  int v34; // eax
  int v35; // eax
  int v37; // [rsp+20h] [rbp-40h]
  _BYTE v38[8]; // [rsp+28h] [rbp-38h] BYREF
  std::_Ref_count_base *v39; // [rsp+30h] [rbp-30h]
  RTL_SRWLOCK *v40; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v41; // [rsp+40h] [rbp-20h] BYREF
  std::_Ref_count_base *v42[2]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  UXFrameTelemetry::ThreadProc_Start();
  v4 = RoInitializeStrict(1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
      (const char *)(unsigned int)v4,
      v37);
  *(_OWORD *)v42 = 0;
  std::make_shared<UXFrame,>(v42);
  v5 = v42[0];
  UXFrame::Initialize(v42[0], *a2);
  AcquireSRWLockExclusive(this + 2);
  v40 = this + 2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
    || (v7 = this + 9, *a2) )
  {
    v7 = this + 7;
  }
  Ptr = (__int64 *)v7->Ptr;
  for ( i = *(__int64 **)v7->Ptr; i != Ptr && *((_DWORD *)i + 6) != _Thrd_id(); i = (__int64 *)*i )
    ;
  if ( i == v7->Ptr )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x72,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
      v6);
  v10 = operator new(0x20u);
  *(_OWORD *)v10 = 0;
  v10[2] = 0;
  v10[3] = 0;
  v41 = v10;
  if ( *((_DWORD *)v10 + 2) )
  {
    _o_terminate();
    __debugbreak();
  }
  v11 = *((_OWORD *)i + 1);
  *((_OWORD *)i + 1) = 0;
  *(_OWORD *)v10 = v11;
  *(_QWORD *)i[1] = *i;
  v12 = (__int64 *)*i;
  v12[1] = i[1];
  --v7[1].Ptr;
  std::_List_node<std::thread,void *>::_Freenode<std::allocator<std::_List_node<std::thread,void *>>>(v12, i);
  v13 = (__int64 *)std::shared_ptr<WindowingBehavior>::shared_ptr<WindowingBehavior>(v38, v42);
  v14 = *v13;
  *v13 = v10[2];
  v10[2] = v14;
  v15 = v13[1];
  v13[1] = v10[3];
  v10[3] = v15;
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  if ( *a2 )
    v16 = this + 3;
  else
    v16 = this + 5;
  std::list<std::unique_ptr<UXFrameThreadData>>::_Emplace<std::unique_ptr<UXFrameThreadData>>(v16, v16->Ptr, &v41);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
    && UXFrame::IsUsingXaml(v5) )
  {
    v19 = this[11].Ptr;
    for ( j = (_QWORD *)*v19; j != v19; j = (_QWORD *)*j )
    {
      v21 = (wil::details **)j[2];
      if ( v21 )
        v22 = *v21;
      else
        v22 = 0;
      wil::details::SetEvent(v22, v17);
    }
    ____Free_non_head_V__allocator_U___List_node_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAX_std___std______List_node_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAX_std__SAXAEAV__allocator_U___List_node_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAX_std___1_PEAU01__Z(
      v18,
      this[11].Ptr);
    *(RTL_SRWLOCK *)this[11].Ptr = this[11];
    *((RTL_SRWLOCK *)this[11].Ptr + 1) = this[11];
    this[12].Ptr = 0;
  }
  std::unique_ptr<UXFrameThreadData>::~unique_ptr<UXFrameThreadData>(&v41);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
  UXFrame::StartMessageLoop(v5);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
  {
    UXFrame::Uninitialize_Stage1_AfterFinalDismiss(v5);
  }
  else if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    UXFrame::Uninitialize(v5);
  }
  if ( *a2
    && (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator bool((char *)*a2 + 72) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete((char *)*a2 + 72);
  }
  AcquireSRWLockExclusive(this + 2);
  v40 = this + 2;
  if ( !(unsigned __int8)lambda_652d3b48ae862e20eefdda1ae8009b99_::operator()(v23, &this[3])
    && !(unsigned __int8)lambda_652d3b48ae862e20eefdda1ae8009b99_::operator()(v24, &this[5]) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xBE,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
      v25);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
  {
    fc::config_property_base::ensure_initialized((fc::config_property_base *)qword_1800737E0);
    if ( byte_180073801 )
    {
      if ( !this[14].Ptr && !this[4].Ptr )
      {
        UXFrameTelemetry::TerminatingProcessDueToLastThreadUnwind();
        ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
        if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
          || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
              ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestControlReporting"),
              (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress) != 0) )
        {
          ((void (__fastcall *)(_QWORD))ProcAddress)(0);
        }
        CurrentProcess = GetCurrentProcess();
        TerminateProcess(CurrentProcess, 0);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    ThreadManager::BlockAndPumpMessagesUntilSafeToUnwindThread(v29);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    IsUsingXaml = UXFrame::IsUsingXaml(v5);
    if ( IsUsingXaml )
    {
      ThreadManager::BlockUntilSafeToUninitializeXaml(this);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_XEFF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_XEFF>::GetImpl'::`2'::impl) )
      {
        AcquireSRWLockExclusive(this + 2);
        v40 = this + 2;
        if ( ++LODWORD(this[13].Ptr) == 1 )
          ThreadManager::SetFailFastOnXamlFailures((ThreadManager *)this, 0);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
      UXFrame::Uninitialize_Stage2_BeforeThreadShutdown(v5);
    else
      UXFrame::Uninitialize(v5);
    if ( IsUsingXaml )
    {
      v41 = 0;
      v31 = winrt::Microsoft::UI::Xaml::Hosting::WindowsXamlManager::GetForCurrentThread();
      if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(v31, &v41) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x101,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
          v32);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v40);
      if ( v41 )
        winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v41);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_XEFF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_XEFF>::GetImpl'::`2'::impl) )
      {
        AcquireSRWLockExclusive(this + 2);
        v40 = this + 2;
        v34 = (int)this[13].Ptr;
        if ( !v34 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x20A,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
            v33);
        v35 = v34 - 1;
        LODWORD(this[13].Ptr) = v35;
        if ( !v35 )
          ThreadManager::SetFailFastOnXamlFailures((ThreadManager *)this, 1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
      }
    }
  }
  UXFrameTelemetry::ThreadProc_Stop();
  if ( v42[1] )
    std::_Ref_count_base::_Decref(v42[1]);
  return RoUninitialize();
}

```

## disassembly

```asm
0x180016660  mov     [rsp-38h+arg_10], rbx
0x180016665  push    rbp
0x180016666  push    rsi
0x180016667  push    rdi
0x180016668  push    r12
0x18001666a  push    r13
0x18001666c  push    r14
0x18001666e  push    r15
0x180016670  mov     rbp, rsp
0x180016673  sub     rsp, 60h
0x180016677  mov     rax, cs:__security_cookie
0x18001667e  xor     rax, rsp
0x180016681  mov     [rbp+var_8], rax
0x180016685  mov     r12, rdx
0x180016688  mov     rsi, rcx
0x18001668b  call    ?ThreadProc_Start@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::ThreadProc_Start(void)
0x180016690  mov     ecx, 1
0x180016695  call    cs:__imp_RoInitializeStrict
0x18001669b  mov     rcx, [rbp+38h]; this
0x18001669f  test    eax, eax
0x1800166a1  js      loc_180016ADB
0x1800166a7  mov     [rbp+var_3F], 1
0x1800166ab  xorps   xmm0, xmm0
0x1800166ae  movups  xmmword ptr [rbp+var_18], xmm0
0x1800166b2  lea     rcx, [rbp+var_18]
0x1800166b6  call    ??$make_shared@VUXFrame@@$$V@std@@YA?AV?$shared_ptr@VUXFrame@@@0@XZ; std::make_shared<UXFrame,>(void)
0x1800166bb  nop
0x1800166bc  mov     rdx, [r12]; struct SpecializationData *
0x1800166c0  mov     r14, [rbp+var_18]
0x1800166c4  mov     rcx, r14; this
0x1800166c7  call    ?Initialize@UXFrame@@QEAAXPEAUSpecializationData@@@Z; UXFrame::Initialize(SpecializationData *)
0x1800166cc  lea     r15, [rsi+10h]
0x1800166d0  mov     rcx, r15; SRWLock
0x1800166d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800166d9  mov     [rbp+var_28], r15
0x1800166dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1800166e4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1800166e9  test    al, al
0x1800166eb  jz      short loc_1800166F8
0x1800166ed  cmp     qword ptr [r12], 0
0x1800166f2  lea     r13, [rsi+48h]
0x1800166f6  jz      short loc_1800166FC
0x1800166f8  lea     r13, [rsi+38h]
0x1800166fc  mov     rdi, [r13+0]
0x180016700  mov     rbx, [rdi]
0x180016703  cmp     rbx, rdi
0x180016706  jz      short loc_180016718
0x180016708  call    cs:__imp__Thrd_id
0x18001670e  cmp     [rbx+18h], eax
0x180016711  jz      short loc_180016718
0x180016713  mov     rbx, [rbx]
0x180016716  jmp     short loc_180016703
0x180016718  mov     rcx, [rbp+38h]; this
0x18001671c  cmp     rbx, [r13+0]
0x180016720  jz      loc_180016AF0
0x180016726  mov     ecx, 20h ; ' '; Size
0x18001672b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016730  mov     rdi, rax
0x180016733  xorps   xmm0, xmm0
0x180016736  movups  xmmword ptr [rax], xmm0
0x180016739  xor     eax, eax
0x18001673b  mov     [rdi+10h], rax
0x18001673f  mov     [rdi+18h], rax
0x180016743  mov     [rbp+var_20], rdi
0x180016747  cmp     [rdi+8], eax
0x18001674a  jz      short loc_180016753
0x18001674c  call    cs:__imp__o_terminate
0x180016752  int     3; Trap to Debugger
0x180016753  xorps   xmm1, xmm1
0x180016756  movups  xmm0, xmmword ptr [rbx+10h]
0x18001675a  movdqu  xmmword ptr [rbx+10h], xmm1
0x18001675f  movdqu  xmmword ptr [rdi], xmm0
0x180016763  mov     rcx, [rbx+8]
0x180016767  mov     rax, [rbx]
0x18001676a  mov     [rcx], rax
0x18001676d  mov     rcx, [rbx]
0x180016770  mov     rax, [rbx+8]
0x180016774  mov     [rcx+8], rax
0x180016778  dec     qword ptr [r13+8]
0x18001677c  mov     rdx, rbx
0x18001677f  call    ??$_Freenode@V?$allocator@U?$_List_node@Vthread@std@@PEAX@std@@@std@@@?$_List_node@Vthread@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@Vthread@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::thread,void *>::_Freenode<std::allocator<std::_List_node<std::thread,void *>>>(std::allocator<std::_List_node<std::thread,void *>> &,std::_List_node<std::thread,void *> *)
0x180016784  lea     rdx, [rbp+var_18]
0x180016788  lea     rcx, [rbp+var_38]
0x18001678c  call    ??0?$shared_ptr@VWindowingBehavior@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WindowingBehavior>::shared_ptr<WindowingBehavior>(std::shared_ptr<WindowingBehavior> const &)
0x180016791  mov     rdx, [rax]
0x180016794  mov     rcx, [rdi+10h]
0x180016798  mov     [rax], rcx
0x18001679b  mov     [rdi+10h], rdx
0x18001679f  mov     rdx, [rax+8]
0x1800167a3  mov     rcx, [rdi+18h]
0x1800167a7  mov     [rax+8], rcx
0x1800167ab  mov     [rdi+18h], rdx
0x1800167af  mov     rcx, [rbp+var_30]; this
0x1800167b3  xor     edi, edi
0x1800167b5  test    rcx, rcx
0x1800167b8  jz      short loc_1800167BF
0x1800167ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800167bf  lea     r8, [rbp+var_20]
0x1800167c3  cmp     [r12], rdi
0x1800167c7  jz      short loc_1800167D2
0x1800167c9  lea     rcx, [rsi+18h]
0x1800167cd  mov     r13, rcx
0x1800167d0  jmp     short loc_1800167DA
0x1800167d2  lea     rcx, [rsi+28h]
0x1800167d6  lea     r13, [rsi+18h]
0x1800167da  mov     rdx, rcx
0x1800167dd  mov     rdx, [rcx]
0x1800167e0  call    ??$_Emplace@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@@?$list@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@V?$allocator@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@PEAX@1@QEAU21@$$QEAV?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@1@@Z; std::list<std::unique_ptr<UXFrameThreadData>>::_Emplace<std::unique_ptr<UXFrameThreadData>>(std::_List_node<std::unique_ptr<UXFrameThreadData>,void *> * const,std::unique_ptr<UXFrameThreadData> &&)
0x1800167e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1800167ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1800167f1  test    al, al
0x1800167f3  jz      short loc_180016845
0x1800167f5  mov     rcx, r14; this
0x1800167f8  call    ?IsUsingXaml@UXFrame@@QEBA_NXZ; UXFrame::IsUsingXaml(void)
0x1800167fd  test    al, al
0x1800167ff  jz      short loc_180016845
0x180016801  mov     rdi, [rsi+58h]
0x180016805  mov     rbx, [rdi]
0x180016808  cmp     rbx, rdi
0x18001680b  jz      short loc_180016827
0x18001680d  mov     rax, [rbx+10h]
0x180016811  test    rax, rax
0x180016814  jz      short loc_18001681B
0x180016816  mov     rcx, [rax]
0x180016819  jmp     short loc_18001681D
0x18001681b  xor     ecx, ecx; this
0x18001681d  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180016822  mov     rbx, [rbx]
0x180016825  jmp     short loc_180016808
0x180016827  mov     rdx, [rsi+58h]
0x18001682b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@std@@@std@@@?$_List_node@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@std@@@1@PEAU01@@Z
0x180016830  mov     rax, [rsi+58h]
0x180016834  mov     [rax], rax
0x180016837  mov     rax, [rsi+58h]
0x18001683b  mov     [rax+8], rax
0x18001683f  xor     edi, edi
0x180016841  mov     [rsi+60h], rdi
0x180016845  lea     rcx, [rbp+var_20]
0x180016849  call    ??1?$unique_ptr@UUXFrameThreadData@@U?$default_delete@UUXFrameThreadData@@@std@@@std@@QEAA@XZ; std::unique_ptr<UXFrameThreadData>::~unique_ptr<UXFrameThreadData>(void)
0x18001684e  nop
0x18001684f  lea     rcx, [rbp+var_28]
0x180016853  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016858  mov     rcx, r14; this
0x18001685b  call    ?StartMessageLoop@UXFrame@@QEAAXXZ; UXFrame::StartMessageLoop(void)
0x180016860  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x180016867  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18001686c  test    al, al
0x18001686e  jz      short loc_18001687A
0x180016870  mov     rcx, r14; this
0x180016873  call    ?Uninitialize_Stage1_AfterFinalDismiss@UXFrame@@QEAAXXZ; UXFrame::Uninitialize_Stage1_AfterFinalDismiss(void)
0x180016878  jmp     short loc_180016892
0x18001687a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x180016881  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x180016886  test    al, al
0x180016888  jnz     short loc_180016892
0x18001688a  mov     rcx, r14; this
0x18001688d  call    ?Uninitialize@UXFrame@@QEAAXXZ; UXFrame::Uninitialize(void)
0x180016892  mov     rcx, [r12]
0x180016896  test    rcx, rcx
0x180016899  jz      short loc_1800168B5
0x18001689b  add     rcx, 48h ; 'H'
0x18001689f  call    ??B?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator bool(void)
0x1800168a4  test    al, al
0x1800168a6  jz      short loc_1800168B5
0x1800168a8  mov     rcx, [r12]
0x1800168ac  add     rcx, 48h ; 'H'
0x1800168b0  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x1800168b5  mov     rcx, r15; SRWLock
0x1800168b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800168be  mov     [rbp+var_28], r15
0x1800168c2  mov     rdx, r13
0x1800168c5  call    _lambda_652d3b48ae862e20eefdda1ae8009b99___operator__
0x1800168ca  test    al, al
0x1800168cc  jnz     short loc_1800168E3
0x1800168ce  lea     rdx, [rsi+28h]
0x1800168d2  mov     rbx, [rbp+38h]
0x1800168d6  call    _lambda_652d3b48ae862e20eefdda1ae8009b99___operator__
0x1800168db  test    al, al
0x1800168dd  jz      loc_180016B02
0x1800168e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x1800168ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x1800168ef  test    al, al
0x1800168f1  jz      short loc_18001695F
0x1800168f3  lea     rcx, qword_1800737E0; this
0x1800168fa  call    ?ensure_initialized@config_property_base@fc@@IEAAXXZ; fc::config_property_base::ensure_initialized(void)
0x1800168ff  cmp     cs:byte_180073801, dil
0x180016906  jz      short loc_18001695F
0x180016908  cmp     [rsi+70h], rdi
0x18001690c  jnz     short loc_18001695F
0x18001690e  cmp     [rsi+20h], rdi
0x180016912  jnz     short loc_18001695F
0x180016914  call    ?TerminatingProcessDueToLastThreadUnwind@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::TerminatingProcessDueToLastThreadUnwind(void)
0x180016919  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x180016920  test    rax, rax
0x180016923  jnz     short loc_180016946
0x180016925  call    tip_details_GetKernelBaseModuleHandle
0x18001692a  mov     rcx, rax; hModule
0x18001692d  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x180016934  call    cs:__imp_GetProcAddress
0x18001693a  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x180016941  test    rax, rax
0x180016944  jz      short loc_18001694D
0x180016946  xor     ecx, ecx
0x180016948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001694d  call    cs:__imp_GetCurrentProcess
0x180016953  mov     rcx, rax; hProcess
0x180016956  xor     edx, edx; uExitCode
0x180016958  call    cs:__imp_TerminateProcess
0x18001695e  nop
0x18001695f  lea     rcx, [rbp+var_28]
0x180016963  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016968  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18001696f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x180016974  test    al, al
0x180016976  jz      short loc_18001697D
0x180016978  call    ?BlockAndPumpMessagesUntilSafeToUnwindThread@ThreadManager@@AEAAXXZ; ThreadManager::BlockAndPumpMessagesUntilSafeToUnwindThread(void)
0x18001697d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x180016984  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x180016989  test    al, al
0x18001698b  jz      loc_180016A8A
0x180016991  mov     rcx, r14; this
0x180016994  call    ?IsUsingXaml@UXFrame@@QEBA_NXZ; UXFrame::IsUsingXaml(void)
0x180016999  mov     bl, al
0x18001699b  test    al, al
0x18001699d  jz      short loc_1800169E1
0x18001699f  mov     rcx, rsi; this
0x1800169a2  call    ?BlockUntilSafeToUninitializeXaml@ThreadManager@@AEAAXXZ; ThreadManager::BlockUntilSafeToUninitializeXaml(void)
0x1800169a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_XEFF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_XEFF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_XEFF> `wil::Feature<__WilFeatureTraits_Feature_SWT_XEFF>::GetImpl(void)'::`2'::impl
0x1800169ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_XEFF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_XEFF>::__private_IsEnabled(void)
0x1800169b3  test    al, al
0x1800169b5  jz      short loc_1800169E1
0x1800169b7  mov     rcx, r15; SRWLock
0x1800169ba  call    cs:__imp_AcquireSRWLockExclusive
0x1800169c0  mov     [rbp+var_28], r15
0x1800169c4  inc     dword ptr [rsi+68h]
0x1800169c7  cmp     dword ptr [rsi+68h], 1
0x1800169cb  jnz     short loc_1800169D8
0x1800169cd  xor     edx, edx; bool
0x1800169cf  mov     rcx, rsi; this
0x1800169d2  call    ?SetFailFastOnXamlFailures@ThreadManager@@AEAAX_N@Z; ThreadManager::SetFailFastOnXamlFailures(bool)
0x1800169d7  nop
0x1800169d8  lea     rcx, [rbp+var_28]
0x1800169dc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800169e1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x1800169e8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x1800169ed  mov     rcx, r14; this
0x1800169f0  test    al, al
0x1800169f2  jz      short loc_1800169FB
0x1800169f4  call    ?Uninitialize_Stage2_BeforeThreadShutdown@UXFrame@@QEAAXXZ; UXFrame::Uninitialize_Stage2_BeforeThreadShutdown(void)
0x1800169f9  jmp     short loc_180016A00
0x1800169fb  call    ?Uninitialize@UXFrame@@QEAAXXZ; UXFrame::Uninitialize(void)
0x180016a00  test    bl, bl
0x180016a02  jz      loc_180016A8A
0x180016a08  mov     [rbp+var_20], rdi
0x180016a0c  lea     rcx, [rbp+var_28]
0x180016a10  call    ?GetForCurrentThread@WindowsXamlManager@Hosting@Xaml@UI@Microsoft@winrt@@SA@XZ; winrt::Microsoft::UI::Xaml::Hosting::WindowsXamlManager::GetForCurrentThread(void)
0x180016a15  mov     rbx, [rbp+38h]
0x180016a19  lea     rdx, [rbp+var_20]
0x180016a1d  mov     rcx, rax
0x180016a20  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180016a25  test    al, al
0x180016a27  jz      loc_180016B17
0x180016a2d  lea     rcx, [rbp+var_28]; this
0x180016a31  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180016a36  nop
0x180016a37  cmp     [rbp+var_20], rdi
0x180016a3b  jz      short loc_180016A46
0x180016a3d  lea     rcx, [rbp+var_20]
0x180016a41  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180016a46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_XEFF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_XEFF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_XEFF> `wil::Feature<__WilFeatureTraits_Feature_SWT_XEFF>::GetImpl(void)'::`2'::impl
0x180016a4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_XEFF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_XEFF>::__private_IsEnabled(void)
0x180016a52  test    al, al
0x180016a54  jz      short loc_180016A8A
0x180016a56  mov     rcx, r15; SRWLock
0x180016a59  call    cs:__imp_AcquireSRWLockExclusive
0x180016a5f  mov     [rbp+var_28], r15
0x180016a63  mov     eax, [rsi+68h]
0x180016a66  mov     rcx, [rbp+38h]; this
0x180016a6a  test    eax, eax
0x180016a6c  jz      short loc_180016AC9
0x180016a6e  sub     eax, 1
0x180016a71  mov     [rsi+68h], eax
0x180016a74  jnz     short loc_180016A81
0x180016a76  mov     dl, 1; bool
0x180016a78  mov     rcx, rsi; this
0x180016a7b  call    ?SetFailFastOnXamlFailures@ThreadManager@@AEAAX_N@Z; ThreadManager::SetFailFastOnXamlFailures(bool)
0x180016a80  nop
0x180016a81  lea     rcx, [rbp+var_28]
0x180016a85  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016a8a  call    ?ThreadProc_Stop@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::ThreadProc_Stop(void)
0x180016a8f  nop
0x180016a90  mov     rcx, [rbp+var_18+8]; this
0x180016a94  test    rcx, rcx
0x180016a97  jz      short loc_180016A9F
0x180016a99  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016a9e  nop
0x180016a9f  call    cs:__imp_RoUninitialize
0x180016aa5  mov     rcx, [rbp+var_8]
0x180016aa9  xor     rcx, rsp; StackCookie
0x180016aac  call    __security_check_cookie
  ... truncated ...
```
