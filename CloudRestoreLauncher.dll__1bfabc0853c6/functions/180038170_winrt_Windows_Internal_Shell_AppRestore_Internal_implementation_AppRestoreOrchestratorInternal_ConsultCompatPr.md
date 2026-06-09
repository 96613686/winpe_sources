# winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::AppRestoreOrchestratorInternal::ConsultCompatProviders(std::unique_ptr<TraceLoggingCorrelationVector,std::default_delete<TraceLoggingCorrelationVector>> &,CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps &)

- ea: `0x180038170`
- end: `0x180038601`
- name: `?ConsultCompatProviders@AppRestoreOrchestratorInternal@implementation@Internal@AppRestore@Shell@3Windows@winrt@@CAXAEAV?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@AEAVAppRestoreOrchestratorRestoreApps@CloudRestoreLauncherTelemetry@@@Z`
- size: `1169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003fcd4`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180016708`
- `0x1800187a8`
- `0x18001c180`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001faa8`
- `0x18001fc28`
- `0x180025a9c`
- `0x180025af4`
- `0x1800273e0`
- `0x1800280ec`
- `0x180028858`
- `0x18002f61c`
- `0x1800364b8`
- `0x180038170`
- `0x180043f40`
- `0x180044898`
- `0x180046174`
- `0x18008421c`
- `0x1800842b8`

## import_xrefs

- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800383d7`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800383e7`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800383d7`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x1800383e7`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800382da`
- `KERNEL32!SubmitThreadpoolWork` at `0x180038395`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800382da`
- `KERNEL32!SubmitThreadpoolWork` at `0x180038395`
- `KERNEL32!CreateThreadpoolWork` at `0x1800382af`
- `KERNEL32!CreateThreadpoolWork` at `0x18003836a`
- `KERNEL32!CreateThreadpoolWork` at `0x1800382af`
- `KERNEL32!CreateThreadpoolWork` at `0x18003836a`
- `KERNEL32!AcquireSRWLockShared` at `0x1800381e0`
- `KERNEL32!AcquireSRWLockShared` at `0x180038208`
- `KERNEL32!AcquireSRWLockShared` at `0x1800381e0`
- `KERNEL32!AcquireSRWLockShared` at `0x180038208`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::AppRestoreOrchestratorInternal::ConsultCompatProviders(
        TraceLoggingCorrelationVector **a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  CbrOneSettings *v6; // rcx
  struct CbrOneSettings *Instance; // rdi
  char v8; // r15
  struct CbrOneSettings *v9; // rdi
  char v10; // r12
  __int64 v11; // rcx
  __int64 v12; // r8
  struct _TP_WORK *v13; // rdi
  int v14; // r8d
  PTP_WORK v15; // rax
  const char *v16; // r9
  int v17; // eax
  struct _TP_WORK *v18; // rbx
  int v19; // r8d
  PTP_WORK v20; // rax
  const char *v21; // r9
  int v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  int v29; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  bool v32; // [rsp+30h] [rbp-D0h] BYREF
  bool v33[7]; // [rsp+31h] [rbp-CFh] BYREF
  PTP_WORK pwk; // [rsp+38h] [rbp-C8h] BYREF
  PTP_WORK v35; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v36; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v37[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[40]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v41[130]; // [rsp+B0h] [rbp-50h] BYREF
  char *v42; // [rsp+1B4h] [rbp+B4h] BYREF
  __int128 pv; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v44[130]; // [rsp+1D0h] [rbp+D0h] BYREF
  char *v45; // [rsp+2D4h] [rbp+1D4h] BYREF
  int v46[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v4 = std::wstring::wstring(
         v37,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudRestore\\ProcessAppRestorability");
  RegistryDataHelper::RegistryDataHelper(&v38, v5, v4);
  CbrOneSettings::GetInstance();
  CbrOneSettings::RefreshSettings(v6);
  Instance = CbrOneSettings::GetInstance();
  AcquireSRWLockShared((PSRWLOCK)Instance + 1);
  pwk = (struct CbrOneSettings *)((char *)Instance + 8);
  v8 = *((_BYTE *)Instance + 24);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&pwk);
  v9 = CbrOneSettings::GetInstance();
  AcquireSRWLockShared((PSRWLOCK)v9 + 1);
  pwk = (struct CbrOneSettings *)((char *)v9 + 8);
  v10 = *((_BYTE *)v9 + 25);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&pwk);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, AppRestoreCompatProviderConsultStarted, v12, 1, v46);
  v13 = 0;
  pwk = 0;
  pv = 0;
  memset_0(v44, 0, 0x102u);
  LODWORD(v45) = -2147467259;
  pv = *(_OWORD *)(*(_QWORD *)(a2 + 272) + 8LL);
  TraceLoggingCorrelationVector::IncrementW(*a1, v44);
  if ( v8 )
  {
    v15 = CreateThreadpoolWork(lambda_c5e3eb1d415614a675cb71477b848dcb_::_lambda_invoker_cdecl_, &pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      &pwk,
      v15);
    v13 = pwk;
    if ( !pwk )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xE9,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
        v16);
    SubmitThreadpoolWork(pwk);
  }
  else
  {
    v17 = RegistryDataHelper::WriteBool((RegistryDataHelper *)&v38, L"StoreSkipped", v14, 1);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
        (const char *)(unsigned int)v17,
        v31);
    LODWORD(v45) = 0;
  }
  v18 = 0;
  v35 = 0;
  v40 = 0;
  memset_0(v41, 0, 0x102u);
  LODWORD(v42) = -2147467259;
  v40 = *(_OWORD *)(*(_QWORD *)(a2 + 272) + 8LL);
  TraceLoggingCorrelationVector::IncrementW(*a1, v41);
  if ( v10 )
  {
    v20 = CreateThreadpoolWork(lambda_0487aec909164b7aecdaa485945f39c4_::_lambda_invoker_cdecl_, &v40, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      &v35,
      v20);
    v18 = v35;
    if ( !v35 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x125,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
        v21);
    SubmitThreadpoolWork(v35);
  }
  else
  {
    v22 = RegistryDataHelper::WriteBool((RegistryDataHelper *)&v38, L"AppraiserSkipped", v19, 1);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12A,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
        (const char *)(unsigned int)v22,
        v31);
    LODWORD(v42) = 0;
  }
  if ( v13 )
    WaitForThreadpoolWorkCallbacks(v13, 0);
  if ( v18 )
    WaitForThreadpoolWorkCallbacks(v18, 0);
  v23 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>::ensure_data(&winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::AppRestoreOrchestratorInternal::s_test);
  *(_QWORD *)v46 = v23;
  if ( v23 )
    _InterlockedIncrement((volatile signed __int32 *)(v23 + 280));
  tip2::details::shared_data<1,0,0>::begin_update(v23 + 8);
  *(_DWORD *)(v23 + 272) = (_DWORD)v45;
  *(_DWORD *)(v23 + 276) = (_DWORD)v42;
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 2) != 0 )
    McTemplateU0dd_EventWriteTransfer(v25, v24, (unsigned int)v45, (unsigned int)v42);
  v27 = RegistryDataHelper::WriteUInt32((RegistryDataHelper *)&v38, L"StoreResult", v26, (unsigned int)v45);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
      (const char *)(unsigned int)v27,
      v31);
  v29 = RegistryDataHelper::WriteUInt32((RegistryDataHelper *)&v38, L"AppraiserResult", v28, (unsigned int)v42);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
      (const char *)(unsigned int)v29,
      v31);
  if ( (int)v45 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
      (const char *)(unsigned int)v45,
      v31);
  if ( (int)v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\apprestoreorchestratorinternal.cpp",
      (const char *)(unsigned int)v42,
      v31);
  v32 = v10 == 0;
  v33[0] = v8 == 0;
  v36 = CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId;
  CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps::AppRestoreOrchestratorRestoreApps_ConsultCompatProvidersResult<unsigned short *,bool,long &,bool,long &>(
    (__int64 *)&v36,
    v33,
    (int *)&v45,
    (char *)&v32,
    (int *)&v42);
  tip2::test_data_control<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>::~test_data_control<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>(v46);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
  return std::wstring::_Tidy_deallocate(v39);
}

```

## disassembly

```asm
0x180038170  mov     [rsp-8+arg_10], rbx
0x180038175  mov     [rsp-8+arg_18], rsi
0x18003817a  push    rbp
0x18003817b  push    rdi
0x18003817c  push    r12
0x18003817e  push    r14
0x180038180  push    r15
0x180038182  lea     rbp, [rsp-200h]
0x18003818a  sub     rsp, 300h
0x180038191  mov     rax, cs:__security_cookie
0x180038198  xor     rax, rsp
0x18003819b  mov     [rbp+220h+var_30], rax
0x1800381a2  mov     r14, rdx
0x1800381a5  mov     rsi, rcx
0x1800381a8  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800381af  lea     rcx, [rsp+320h+var_2D0]
0x1800381b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800381b9  mov     r8, rax
0x1800381bc  lea     rcx, [rsp+320h+var_2B0]
0x1800381c1  call    ??0RegistryDataHelper@@QEAA@PEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; RegistryDataHelper::RegistryDataHelper(HKEY__ *,std::wstring,HKEY__ *)
0x1800381c6  nop
0x1800381c7  call    ?GetInstance@CbrOneSettings@@SAAEAV1@XZ; CbrOneSettings::GetInstance(void)
0x1800381cc  call    ?RefreshSettings@CbrOneSettings@@QEAAXXZ; CbrOneSettings::RefreshSettings(void)
0x1800381d1  call    ?GetInstance@CbrOneSettings@@SAAEAV1@XZ; CbrOneSettings::GetInstance(void)
0x1800381d6  mov     rdi, rax
0x1800381d9  lea     rbx, [rax+8]
0x1800381dd  mov     rcx, rbx; SRWLock
0x1800381e0  call    cs:__imp_AcquireSRWLockShared
0x1800381e6  mov     [rsp+320h+pwk], rbx
0x1800381eb  mov     r15b, [rdi+18h]
0x1800381ef  lea     rcx, [rsp+320h+pwk]
0x1800381f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800381f9  call    ?GetInstance@CbrOneSettings@@SAAEAV1@XZ; CbrOneSettings::GetInstance(void)
0x1800381fe  mov     rdi, rax
0x180038201  lea     rbx, [rax+8]
0x180038205  mov     rcx, rbx; SRWLock
0x180038208  call    cs:__imp_AcquireSRWLockShared
0x18003820e  mov     [rsp+320h+pwk], rbx
0x180038213  mov     r12b, [rdi+19h]
0x180038217  lea     rcx, [rsp+320h+pwk]
0x18003821c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180038221  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 2
0x180038228  jz      short loc_180038248
0x18003822a  lea     rax, [rbp+220h+var_40]
0x180038231  mov     qword ptr [rsp+320h+var_300], rax; int
0x180038236  mov     r9d, 1
0x18003823c  lea     rdx, AppRestoreCompatProviderConsultStarted
0x180038243  call    McGenEventWrite_EventWriteTransfer
0x180038248  xor     edi, edi
0x18003824a  mov     [rsp+320h+pwk], rdi
0x18003824f  xorps   xmm0, xmm0
0x180038252  movups  [rbp+220h+pv], xmm0
0x180038259  xor     edx, edx; Val
0x18003825b  mov     r8d, 102h; Size
0x180038261  lea     rcx, [rbp+220h+var_150]; void *
0x180038268  call    memset_0
0x18003826d  mov     dword ptr [rbp+220h+var_4C], 80004005h
0x180038277  mov     rax, [r14+110h]
0x18003827e  movups  xmm0, xmmword ptr [rax+8]
0x180038282  movdqu  [rbp+220h+pv], xmm0
0x18003828a  lea     rdx, [rbp+220h+var_150]; unsigned __int16 *
0x180038291  mov     rcx, [rsi]; this
0x180038294  call    ?IncrementW@TraceLoggingCorrelationVector@@QEAA_NPEAG@Z; TraceLoggingCorrelationVector::IncrementW(ushort *)
0x180038299  test    r15b, r15b
0x18003829c  jz      short loc_1800382E2
0x18003829e  xor     r8d, r8d; pcbe
0x1800382a1  lea     rdx, [rbp+220h+pv]; pv
0x1800382a8  lea     rcx, _lambda_c5e3eb1d415614a675cb71477b848dcb____lambda_invoker_cdecl_; pfnwk
0x1800382af  call    cs:__imp_CreateThreadpoolWork
0x1800382b5  mov     rdx, rax
0x1800382b8  lea     rcx, [rsp+320h+pwk]
0x1800382bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x1800382c2  mov     rcx, [rbp+228h]; this
0x1800382c9  mov     rdi, [rsp+320h+pwk]
0x1800382ce  test    rdi, rdi
0x1800382d1  jz      loc_180038577
0x1800382d7  mov     rcx, rdi; pwk
0x1800382da  call    cs:__imp_SubmitThreadpoolWork
0x1800382e0  jmp     short loc_180038312
0x1800382e2  mov     r9d, 1; int
0x1800382e8  lea     rdx, aStoreskipped; "StoreSkipped"
0x1800382ef  lea     rcx, [rsp+320h+var_2B0]; this
0x1800382f4  call    ?WriteBool@RegistryDataHelper@@QEAAJPEBGHH@Z; RegistryDataHelper::WriteBool(ushort const *,int,int)
0x1800382f9  mov     rcx, [rbp+228h]; this
0x180038300  test    eax, eax
0x180038302  js      loc_180038589
0x180038308  mov     dword ptr [rbp+220h+var_4C], 0
0x180038312  xor     ebx, ebx
0x180038314  mov     [rsp+320h+var_2E0], rbx
0x180038319  xorps   xmm0, xmm0
0x18003831c  movups  [rbp+220h+var_280], xmm0
0x180038320  xor     edx, edx; Val
0x180038322  mov     r8d, 102h; Size
0x180038328  lea     rcx, [rbp+220h+var_270]; void *
0x18003832c  call    memset_0
0x180038331  mov     dword ptr [rbp+220h+var_16C], 80004005h
0x18003833b  mov     rax, [r14+110h]
0x180038342  movups  xmm0, xmmword ptr [rax+8]
0x180038346  movdqu  [rbp+220h+var_280], xmm0
0x18003834b  lea     rdx, [rbp+220h+var_270]; unsigned __int16 *
0x18003834f  mov     rcx, [rsi]; this
0x180038352  call    ?IncrementW@TraceLoggingCorrelationVector@@QEAA_NPEAG@Z; TraceLoggingCorrelationVector::IncrementW(ushort *)
0x180038357  test    r12b, r12b
0x18003835a  jz      short loc_18003839D
0x18003835c  xor     r8d, r8d; pcbe
0x18003835f  lea     rdx, [rbp+220h+var_280]; pv
0x180038363  lea     rcx, _lambda_0487aec909164b7aecdaa485945f39c4____lambda_invoker_cdecl_; pfnwk
0x18003836a  call    cs:__imp_CreateThreadpoolWork
0x180038370  mov     rdx, rax
0x180038373  lea     rcx, [rsp+320h+var_2E0]
0x180038378  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18003837d  mov     rcx, [rbp+228h]; this
0x180038384  mov     rbx, [rsp+320h+var_2E0]
0x180038389  test    rbx, rbx
0x18003838c  jz      loc_18003859E
0x180038392  mov     rcx, rbx; pwk
0x180038395  call    cs:__imp_SubmitThreadpoolWork
0x18003839b  jmp     short loc_1800383CD
0x18003839d  mov     r9d, 1; int
0x1800383a3  lea     rdx, aAppraiserskipp; "AppraiserSkipped"
0x1800383aa  lea     rcx, [rsp+320h+var_2B0]; this
0x1800383af  call    ?WriteBool@RegistryDataHelper@@QEAAJPEBGHH@Z; RegistryDataHelper::WriteBool(ushort const *,int,int)
0x1800383b4  mov     rcx, [rbp+228h]; this
0x1800383bb  test    eax, eax
0x1800383bd  js      loc_1800385B0
0x1800383c3  mov     dword ptr [rbp+220h+var_16C], 0
0x1800383cd  test    rdi, rdi
0x1800383d0  jz      short loc_1800383DD
0x1800383d2  xor     edx, edx; fCancelPendingCallbacks
0x1800383d4  mov     rcx, rdi; pwk
0x1800383d7  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800383dd  test    rbx, rbx
0x1800383e0  jz      short loc_1800383ED
0x1800383e2  xor     edx, edx; fCancelPendingCallbacks
0x1800383e4  mov     rcx, rbx; pwk
0x1800383e7  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800383ed  lea     rcx, ?s_test@AppRestoreOrchestratorInternal@implementation@Internal@AppRestore@Shell@3Windows@winrt@@0V?$tip_test@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>> winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::AppRestoreOrchestratorInternal::s_test
0x1800383f4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>::ensure_data(void)
0x1800383f9  mov     rbx, [rax]
0x1800383fc  mov     qword ptr [rbp+220h+var_40], rbx
0x180038403  test    rbx, rbx
0x180038406  jz      short loc_18003840F
0x180038408  lock inc dword ptr [rbx+118h]
0x18003840f  lea     rcx, [rbx+8]
0x180038413  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180038418  nop
0x180038419  mov     eax, dword ptr [rbp+220h+var_4C]
0x18003841f  mov     [rbx+110h], eax
0x180038425  mov     eax, dword ptr [rbp+220h+var_16C]
0x18003842b  mov     [rbx+114h], eax
0x180038431  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 2
0x180038438  jz      short loc_18003844D
0x18003843a  mov     r9d, dword ptr [rbp+220h+var_16C]
0x180038441  mov     r8d, dword ptr [rbp+220h+var_4C]
0x180038448  call    McTemplateU0dd_EventWriteTransfer
0x18003844d  mov     r9d, dword ptr [rbp+220h+var_4C]; unsigned int
0x180038454  lea     rdx, aStoreresult; "StoreResult"
0x18003845b  lea     rcx, [rsp+320h+var_2B0]; this
0x180038460  call    ?WriteUInt32@RegistryDataHelper@@QEAAJPEBGII@Z; RegistryDataHelper::WriteUInt32(ushort const *,uint,uint)
0x180038465  mov     rcx, [rbp+228h]; this
0x18003846c  test    eax, eax
0x18003846e  js      loc_1800385C5
0x180038474  mov     r9d, dword ptr [rbp+220h+var_16C]; unsigned int
0x18003847b  lea     rdx, aAppraiserresul; "AppraiserResult"
0x180038482  lea     rcx, [rsp+320h+var_2B0]; this
0x180038487  call    ?WriteUInt32@RegistryDataHelper@@QEAAJPEBGII@Z; RegistryDataHelper::WriteUInt32(ushort const *,uint,uint)
0x18003848c  mov     rcx, [rbp+228h]; this
0x180038493  test    eax, eax
0x180038495  js      loc_1800385DA
0x18003849b  mov     r9d, dword ptr [rbp+220h+var_4C]; char *
0x1800384a2  mov     rcx, [rbp+228h]; this
0x1800384a9  test    r9d, r9d
0x1800384ac  js      loc_1800385EF
0x1800384b2  mov     r9d, dword ptr [rbp+220h+var_16C]; char *
0x1800384b9  mov     rcx, [rbp+228h]; this
0x1800384c0  test    r9d, r9d
0x1800384c3  js      loc_180038565
0x1800384c9  test    r12b, r12b
0x1800384cc  setz    [rsp+320h+var_2F0]
0x1800384d1  test    r15b, r15b
0x1800384d4  setz    [rsp+320h+var_2EF]
0x1800384d9  mov     rax, cs:?s_restoredDeviceProfileId@CloudRestoreLauncherTelemetry@@2V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId
0x1800384e0  mov     [rsp+320h+var_2D8], rax
0x1800384e5  lea     rax, [rbp+220h+var_16C]
0x1800384ec  mov     qword ptr [rsp+320h+var_300], rax
0x1800384f1  lea     r9, [rsp+320h+var_2F0]
0x1800384f6  lea     r8, [rbp+220h+var_4C]
0x1800384fd  lea     rdx, [rsp+320h+var_2EF]
0x180038502  lea     rcx, [rsp+320h+var_2D8]
0x180038507  call    ??$AppRestoreOrchestratorRestoreApps_ConsultCompatProvidersResult@PEAG_NAEAJ_NAEAJ@AppRestoreOrchestratorRestoreApps@CloudRestoreLauncherTelemetry@@SAX$$QEAPEAG$$QEA_NAEAJ12@Z; CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps::AppRestoreOrchestratorRestoreApps_ConsultCompatProvidersResult<ushort *,bool,long &,bool,long &>(ushort * &&,bool &&,long &,bool &&,long &)
0x18003850c  nop
0x18003850d  lea     rcx, [rbp+220h+var_40]
0x180038514  call    ??1?$test_data_control@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>::~test_data_control<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>(void)
0x180038519  nop
0x18003851a  lea     rcx, [rsp+320h+var_2E0]
0x18003851f  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x180038524  nop
0x180038525  lea     rcx, [rsp+320h+pwk]
0x18003852a  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18003852f  nop
0x180038530  lea     rcx, [rsp+320h+var_2A8]
0x180038535  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003853a  mov     rcx, [rbp+220h+var_30]
0x180038541  xor     rcx, rsp; StackCookie
0x180038544  call    __security_check_cookie
0x180038549  lea     r11, [rsp+320h+var_20]
0x180038551  mov     rbx, [r11+40h]
0x180038555  mov     rsi, [r11+48h]
0x180038559  mov     rsp, r11
0x18003855c  pop     r15
0x18003855e  pop     r14
0x180038560  pop     r12
0x180038562  pop     rdi
0x180038563  pop     rbp
0x180038564  retn
0x180038565  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x18003856c  mov     edx, 141h; void *
0x180038571  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038577  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x18003857e  mov     edx, 0E9h; void *
0x180038583  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180038589  mov     r9d, eax; char *
0x18003858c  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x180038593  mov     edx, 0EEh; void *
0x180038598  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003859e  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800385a5  mov     edx, 125h; void *
0x1800385aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800385b0  mov     r9d, eax; char *
0x1800385b3  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800385ba  mov     edx, 12Ah; void *
0x1800385bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800385c5  mov     r9d, eax; char *
0x1800385c8  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800385cf  mov     edx, 13Dh; void *
0x1800385d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800385da  mov     r9d, eax; char *
0x1800385dd  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800385e4  mov     edx, 13Eh; void *
0x1800385e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800385ef  lea     r8, aPcshellShellCl_22; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800385f6  mov     edx, 140h; void *
0x1800385fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
