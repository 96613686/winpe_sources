# HcfDetector::Start(void)

- ea: `0x180021d2c`
- end: `0x180022393`
- name: `?Start@HcfDetector@@AEAAXXZ`
- size: `1639`
- prototype: `void __fastcall(wchar_t *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800223dc`

## callees

- `0x180007ad0`
- `0x18000c478`
- `0x180013930`
- `0x180019c3c`
- `0x18001ee34`
- `0x18001fb38`
- `0x18001fdc0`
- `0x18001fe30`
- `0x18001fea0`
- `0x180021290`
- `0x180021d2c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022231`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022220`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022220`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022229`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022229`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800221ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800221ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022212`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022333`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022212`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022333`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800221aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800221aa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800221da`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800221da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002225f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002225f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002227e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002230f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002227e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002230f`

## string_xrefs

- `0x180021d58`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x1800221c7`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x180022350`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x180022344`: `[WSAIFabricHost][HcfDetection] Scheduled timer. detector=%p period=%I32ums windowLength=%I32ums`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall HcfDetector::Start(wchar_t *this)
{
  wchar_t *v2; // r15
  __m128i v3; // xmm0
  __int64 v4; // rcx
  HKEY v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  HKEY v9; // rbx
  wchar_t *v10; // rsi
  __int64 v11; // r14
  __int64 v12; // rax
  __m128i v13; // xmm0
  __int64 v14; // rcx
  HKEY v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  HKEY v19; // rbx
  wchar_t *v20; // rsi
  __int64 v21; // r14
  __int64 v22; // rax
  __m128i v23; // xmm0
  __int64 v24; // rdx
  HKEY v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  HKEY v29; // rbx
  wchar_t *v30; // rsi
  __int64 v31; // r14
  __int64 v32; // rax
  struct _TP_WORK *ThreadpoolWork; // rbx
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v35; // rsi
  DWORD LastError; // ebx
  LSTATUS v37; // eax
  __int64 v38; // r8
  bool v39; // sf
  DWORD v40; // esi
  DWORD v41; // ebx
  __int64 v42; // r8
  unsigned int v43; // eax
  int v44; // r14d
  PHKEY phkResult; // [rsp+20h] [rbp-79h]
  __m128i v46; // [rsp+30h] [rbp-69h] BYREF
  __m128i v47; // [rsp+40h] [rbp-59h] BYREF
  __m128i v48; // [rsp+50h] [rbp-49h] BYREF
  __int64 v49; // [rsp+60h] [rbp-39h] BYREF
  __int64 v50; // [rsp+68h] [rbp-31h] BYREF
  __int64 v51; // [rsp+70h] [rbp-29h] BYREF
  int v52; // [rsp+78h] [rbp-21h] BYREF
  __int128 v53; // [rsp+80h] [rbp-19h]
  __int64 v54[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v55[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v56[8]; // [rsp+B0h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+100h] [rbp+67h] BYREF
  HKEY v58; // [rsp+108h] [rbp+6Fh] BYREF
  struct _FILETIME pftDueTime; // [rsp+110h] [rbp+77h] BYREF
  __int64 v60; // [rsp+118h] [rbp+7Fh]

  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
    (const wchar_t *)0x10C,
    (unsigned int)L"[WSAIFabricHost][HcfDetection] Starting detector. detector=%p",
    this);
  v2 = this + 12;
  v3 = 0;
  v47 = 0;
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    v47.m128i_i64[0] = *(_QWORD *)this;
    v47.m128i_i64[1] = v4;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 12));
    v3 = _mm_load_si128(&v47);
  }
  v46 = v3;
  v47 = 0;
  hKey = (HKEY)&v46;
  v5 = (HKEY)operator new(0x20u);
  hKey = v5;
  *((_DWORD *)v5 + 2) = 1;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((__m128i *)v5 + 1) = v46;
  v46 = 0;
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v5 + 8));
  *(_QWORD *)v5 = &winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::PackageCatalog,winrt::Windows::ApplicationModel::PackageInstallingEventArgs>,_lambda_a05ab0008d2bed5444ec856fd80ee2f4_>::`vftable';
  v58 = v5;
  v6 = v46.m128i_i64[1];
  if ( v46.m128i_i64[1] && _InterlockedExchangeAdd((volatile signed __int32 *)(v46.m128i_i64[1] + 12), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  hKey = 0;
  v7 = *(_QWORD *)v2;
  v52 = 0;
  v53 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, HKEY, HKEY *))(*(_QWORD *)v7 + 64LL))(v7, v5, &hKey);
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v52);
  v9 = hKey;
  winrt::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>(
    &v48,
    this + 12);
  v48.m128i_i64[1] = (__int64)v9;
  v10 = this + 16;
  v11 = v48.m128i_i64[0];
  v48.m128i_i64[0] = 0;
  v54[0] = 0;
  v49 = v11;
  if ( v54 != (__int64 *)(this + 16) )
  {
    v12 = *(_QWORD *)v10;
    *(_QWORD *)v10 = 0;
    v54[0] = v12;
  }
  if ( v10 == (wchar_t *)&v49 )
  {
    if ( v11 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v49);
  }
  else
  {
    if ( *(_QWORD *)v10 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(this + 16);
    *(_QWORD *)v10 = v11;
  }
  v54[1] = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v9;
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BEI_AA_impl_winrt__QEAA_XZ(v54);
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BEI_AA_impl_winrt__QEAA_XZ(v48.m128i_i64);
  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v58);
  v13 = 0;
  v48 = 0;
  v14 = *((_QWORD *)this + 1);
  if ( v14 )
  {
    v48.m128i_i64[0] = *(_QWORD *)this;
    v48.m128i_i64[1] = v14;
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 12));
    v13 = _mm_load_si128(&v48);
  }
  v46 = v13;
  v48 = 0;
  hKey = (HKEY)&v46;
  v15 = (HKEY)operator new(0x20u);
  hKey = v15;
  *((_DWORD *)v15 + 2) = 1;
  *((_QWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 3) = 0;
  *((__m128i *)v15 + 1) = v46;
  v46 = 0;
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v15 + 8));
  *(_QWORD *)v15 = &winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::PackageCatalog,winrt::Windows::ApplicationModel::PackageStatusChangedEventArgs>,_lambda_aa7b611dc7a5a165e652cd110adbd0b3_>::`vftable';
  v58 = v15;
  v16 = v46.m128i_i64[1];
  if ( v46.m128i_i64[1] && _InterlockedExchangeAdd((volatile signed __int32 *)(v46.m128i_i64[1] + 12), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  hKey = 0;
  v17 = *(_QWORD *)v2;
  v52 = 0;
  v53 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, HKEY, HKEY *))(*(_QWORD *)v17 + 112LL))(v17, v15, &hKey);
  if ( v18 < 0 )
    winrt::throw_hresult((unsigned int)v18, &v52);
  v19 = hKey;
  winrt::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>(
    &v47,
    this + 12);
  v47.m128i_i64[1] = (__int64)v19;
  v20 = this + 24;
  v21 = v47.m128i_i64[0];
  v47.m128i_i64[0] = 0;
  v55[0] = 0;
  v50 = v21;
  if ( v55 != (__int64 *)(this + 24) )
  {
    v22 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    v55[0] = v22;
  }
  if ( v20 == (wchar_t *)&v50 )
  {
    if ( v21 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v50);
  }
  else
  {
    if ( *(_QWORD *)v20 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(this + 24);
    *(_QWORD *)v20 = v21;
  }
  v55[1] = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v19;
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BHI_AA_impl_winrt__QEAA_XZ(v55);
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BHI_AA_impl_winrt__QEAA_XZ(v47.m128i_i64);
  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v58);
  v23 = 0;
  v48 = 0;
  v24 = *((_QWORD *)this + 1);
  if ( v24 )
  {
    v48.m128i_i64[0] = *(_QWORD *)this;
    v48.m128i_i64[1] = v24;
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 12));
    v23 = _mm_load_si128(&v48);
  }
  v46 = v23;
  v48 = 0;
  hKey = (HKEY)&v46;
  v25 = (HKEY)operator new(0x20u);
  hKey = v25;
  *((_DWORD *)v25 + 2) = 1;
  *((_QWORD *)v25 + 2) = 0;
  *((_QWORD *)v25 + 3) = 0;
  *((__m128i *)v25 + 1) = v46;
  v46 = 0;
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v25 + 8));
  *(_QWORD *)v25 = &winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::PackageCatalog,winrt::Windows::ApplicationModel::PackageUninstallingEventArgs>,_lambda_d647519c5959a5ccfdcec94345adfb07_>::`vftable';
  v58 = v25;
  v26 = v46.m128i_i64[1];
  if ( v46.m128i_i64[1] && _InterlockedExchangeAdd((volatile signed __int32 *)(v46.m128i_i64[1] + 12), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  hKey = 0;
  v27 = *(_QWORD *)v2;
  v52 = 0;
  v53 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, HKEY, HKEY *))(*(_QWORD *)v27 + 96LL))(v27, v25, &hKey);
  if ( v28 < 0 )
    winrt::throw_hresult((unsigned int)v28, &v52);
  v29 = hKey;
  winrt::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>(
    &v47,
    this + 12);
  v47.m128i_i64[1] = (__int64)v29;
  v30 = this + 32;
  v31 = v47.m128i_i64[0];
  v47.m128i_i64[0] = 0;
  v56[0] = 0;
  v51 = v31;
  if ( v56 != (__int64 *)(this + 32) )
  {
    v32 = *(_QWORD *)v30;
    *(_QWORD *)v30 = 0;
    v56[0] = v32;
  }
  if ( v30 == (wchar_t *)&v51 )
  {
    if ( v31 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
  }
  else
  {
    if ( *(_QWORD *)v30 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(this + 32);
    *(_QWORD *)v30 = v31;
  }
  v56[1] = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v29;
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BGI_AA_impl_winrt__QEAA_XZ(v56);
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BGI_AA_impl_winrt__QEAA_XZ(v47.m128i_i64);
  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v58);
  ThreadpoolWork = CreateThreadpoolWork(HcfDetector::ThreadpoolWorkCallback, this, 0);
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
    (const wchar_t *)0x14D,
    (unsigned int)L"[WSAIFabricHost][HcfDetection] Scheduling one-shot detection. detector=%p work=%p",
    this,
    ThreadpoolWork);
  v60 = 0;
  SubmitThreadpoolWork(ThreadpoolWork);
  ThreadpoolTimer = CreateThreadpoolTimer(HcfDetector::ThreadpoolTimerCallback, this, 0);
  v35 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v35 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v35, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v35, 1);
    CloseThreadpoolTimer(v35);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = ThreadpoolTimer;
  hKey = 0;
  v37 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkloadManager\\HCF",
          0,
          0x20019u,
          &hKey);
  v39 = v37 < 0;
  if ( v37 > 0 )
    v39 = 1;
  if ( v39 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    v40 = 3600000;
    v41 = 600000;
    goto LABEL_66;
  }
  wil::reg::try_get_value<unsigned int>((__int64)&v58, hKey, v38, L"QueryPeriodMilliseconds");
  if ( BYTE4(v58) )
  {
    v43 = (unsigned int)v58;
    v44 = 86400000;
    if ( (unsigned int)v58 > 0x5265C00 )
      goto LABEL_57;
  }
  else
  {
    v43 = 3600000;
  }
  v44 = v43;
  if ( v43 < 0x3E8 )
    v44 = 1000;
LABEL_57:
  wil::reg::try_get_value<unsigned int>((__int64)&v58, hKey, v42, L"QueryWindowLengthMilliseconds");
  if ( !BYTE4(v58) )
  {
    v41 = 600000;
LABEL_61:
    if ( v41 < 0x64 )
      v41 = 100;
    goto LABEL_63;
  }
  v41 = (unsigned int)v58;
  if ( (unsigned int)v58 <= 0x36EE80 )
    goto LABEL_61;
  v41 = 3600000;
LABEL_63:
  if ( hKey )
    RegCloseKey(hKey);
  v40 = v44;
LABEL_66:
  pftDueTime = (struct _FILETIME)(-10000LL * v40);
  SetThreadpoolTimer(*((PTP_TIMER *)this + 2), &pftDueTime, v40, v41);
  LODWORD(phkResult) = v40;
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
    (const wchar_t *)0x166,
    (unsigned int)L"[WSAIFabricHost][HcfDetection] Scheduled timer. detector=%p period=%I32ums windowLength=%I32ums",
    this,
    phkResult,
    v41);
}

```

## disassembly

```asm
0x180021d2c  push    rbp
0x180021d2e  push    rbx
0x180021d2f  push    rsi
0x180021d30  push    rdi
0x180021d31  push    r12
0x180021d33  push    r14
0x180021d35  push    r15
0x180021d37  lea     rbp, [rsp-27h]
0x180021d3c  sub     rsp, 0C0h
0x180021d43  mov     rdi, rcx
0x180021d46  xor     r12d, r12d
0x180021d49  mov     r9, rcx; wchar_t *
0x180021d4c  lea     r8, aWsaifabrichost_12; "[WSAIFabricHost][HcfDetection] Starting"...
0x180021d53  mov     edx, 10Ch; wchar_t *
0x180021d58  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180021d5f  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180021d64  lea     r15, [rdi+18h]
0x180021d68  xorps   xmm0, xmm0
0x180021d6b  movdqa  [rbp+57h+var_B0], xmm0
0x180021d70  mov     rcx, [rdi+8]
0x180021d74  test    rcx, rcx
0x180021d77  jz      short loc_180021D8D
0x180021d79  mov     rax, [rdi]
0x180021d7c  mov     qword ptr [rbp+57h+var_B0], rax
0x180021d80  mov     qword ptr [rbp+57h+var_B0+8], rcx
0x180021d84  lock inc dword ptr [rcx+0Ch]
0x180021d88  movdqa  xmm0, [rbp+57h+var_B0]
0x180021d8d  movdqa  [rbp+57h+var_C0], xmm0
0x180021d92  xorps   xmm0, xmm0
0x180021d95  movdqa  [rbp+57h+var_B0], xmm0
0x180021d9a  lea     rax, [rbp+57h+var_C0]
0x180021d9e  mov     [rbp+57h+hKey], rax
0x180021da2  mov     ecx, 20h ; ' '; Size
0x180021da7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021dac  mov     rbx, rax
0x180021daf  mov     [rbp+57h+hKey], rax
0x180021db3  mov     dword ptr [rax+8], 1
0x180021dba  mov     [rax+10h], r12
0x180021dbe  mov     [rax+18h], r12
0x180021dc2  mov     rcx, qword ptr [rbp+57h+var_C0]
0x180021dc6  mov     [rax+10h], rcx
0x180021dca  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x180021dce  mov     [rax+18h], rcx
0x180021dd2  xorps   xmm0, xmm0
0x180021dd5  movdqa  [rbp+57h+var_C0], xmm0
0x180021dda  lea     rcx, [rax+20h]
0x180021dde  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180021de3  lea     rax, ??_7?$delegate@U?$TypedEventHandler@UPackageCatalog@ApplicationModel@Windows@winrt@@UPackageInstallingEventArgs@234@@Foundation@Windows@winrt@@V_lambda_a05ab0008d2bed5444ec856fd80ee2f4_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::PackageCatalog,winrt::Windows::ApplicationModel::PackageInstallingEventArgs>,_lambda_a05ab0008d2bed5444ec856fd80ee2f4_>::`vftable'
0x180021dea  mov     [rbx], rax
0x180021ded  mov     [rbp+57h+arg_8], rbx
0x180021df1  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x180021df5  test    rcx, rcx
0x180021df8  jz      short loc_180021E14
0x180021dfa  or      eax, 0FFFFFFFFh
0x180021dfd  lock xadd [rcx+0Ch], eax
0x180021e02  cmp     eax, 1
0x180021e05  jnz     short loc_180021E14
0x180021e07  mov     rax, [rcx]
0x180021e0a  mov     rax, [rax+8]
0x180021e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e13  nop
0x180021e14  mov     [rbp+57h+hKey], r12
0x180021e18  mov     rcx, [r15]
0x180021e1b  mov     [rbp+57h+var_78], r12d
0x180021e1f  xorps   xmm0, xmm0
0x180021e22  movdqu  [rbp+57h+var_70], xmm0
0x180021e27  mov     rax, [rcx]
0x180021e2a  lea     r8, [rbp+57h+hKey]
0x180021e2e  mov     rdx, rbx
0x180021e31  mov     rax, [rax+40h]
0x180021e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e3a  test    eax, eax
0x180021e3c  js      loc_18002237B
0x180021e42  mov     rbx, [rbp+57h+hKey]
0x180021e46  mov     rdx, r15
0x180021e49  lea     rcx, [rbp+57h+var_A0]
0x180021e4d  call    ??$?0AEBUIPackageCatalog@ApplicationModel@Windows@winrt@@X@?$weak_ref@UIPackageCatalog@ApplicationModel@Windows@winrt@@@winrt@@QEAA@AEBUIPackageCatalog@ApplicationModel@Windows@1@@Z; winrt::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>(winrt::Windows::ApplicationModel::IPackageCatalog const &)
0x180021e52  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x180021e56  lea     rsi, [rdi+20h]
0x180021e5a  mov     r14, qword ptr [rbp+57h+var_A0]
0x180021e5e  mov     qword ptr [rbp+57h+var_A0], r12
0x180021e62  mov     [rbp+57h+var_60], r12
0x180021e66  mov     [rbp+57h+var_90], r14
0x180021e6a  lea     rax, [rbp+57h+var_60]
0x180021e6e  cmp     rax, rsi
0x180021e71  jz      short loc_180021E7D
0x180021e73  mov     rax, [rsi]
0x180021e76  mov     [rsi], r12
0x180021e79  mov     [rbp+57h+var_60], rax
0x180021e7d  lea     rax, [rbp+57h+var_90]
0x180021e81  cmp     rsi, rax
0x180021e84  jz      short loc_180021E98
0x180021e86  cmp     [rsi], r12
0x180021e89  jz      short loc_180021E93
0x180021e8b  mov     rcx, rsi
0x180021e8e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180021e93  mov     [rsi], r14
0x180021e96  jmp     short loc_180021EA6
0x180021e98  test    r14, r14
0x180021e9b  jz      short loc_180021EA6
0x180021e9d  lea     rcx, [rbp+57h+var_90]
0x180021ea1  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180021ea6  mov     rax, [rsi+8]
0x180021eaa  mov     [rbp+57h+var_58], rax
0x180021eae  mov     [rsi+8], rbx
0x180021eb2  lea     rcx, [rbp+57h+var_60]
0x180021eb6  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BEI@AA@impl@winrt@@QEAA@XZ
0x180021ebb  lea     rcx, [rbp+57h+var_A0]
0x180021ebf  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BEI@AA@impl@winrt@@QEAA@XZ
0x180021ec4  nop
0x180021ec5  lea     rcx, [rbp+57h+arg_8]
0x180021ec9  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180021ece  nop
0x180021ecf  xorps   xmm0, xmm0
0x180021ed2  movdqa  [rbp+57h+var_A0], xmm0
0x180021ed7  mov     rcx, [rdi+8]
0x180021edb  test    rcx, rcx
0x180021ede  jz      short loc_180021EF4
0x180021ee0  mov     rax, [rdi]
0x180021ee3  mov     qword ptr [rbp+57h+var_A0], rax
0x180021ee7  mov     qword ptr [rbp+57h+var_A0+8], rcx
0x180021eeb  lock inc dword ptr [rcx+0Ch]
0x180021eef  movdqa  xmm0, [rbp+57h+var_A0]
0x180021ef4  movdqa  [rbp+57h+var_C0], xmm0
0x180021ef9  xorps   xmm0, xmm0
0x180021efc  movdqa  [rbp+57h+var_A0], xmm0
0x180021f01  lea     rax, [rbp+57h+var_C0]
0x180021f05  mov     [rbp+57h+hKey], rax
0x180021f09  mov     ecx, 20h ; ' '; Size
0x180021f0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021f13  mov     rbx, rax
0x180021f16  mov     [rbp+57h+hKey], rax
0x180021f1a  mov     dword ptr [rax+8], 1
0x180021f21  mov     [rax+10h], r12
0x180021f25  mov     [rax+18h], r12
0x180021f29  mov     rcx, qword ptr [rbp+57h+var_C0]
0x180021f2d  mov     [rax+10h], rcx
0x180021f31  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x180021f35  mov     [rax+18h], rcx
0x180021f39  xorps   xmm0, xmm0
0x180021f3c  movdqa  [rbp+57h+var_C0], xmm0
0x180021f41  lea     rcx, [rax+20h]
0x180021f45  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180021f4a  lea     rax, ??_7?$delegate@U?$TypedEventHandler@UPackageCatalog@ApplicationModel@Windows@winrt@@UPackageStatusChangedEventArgs@234@@Foundation@Windows@winrt@@V_lambda_aa7b611dc7a5a165e652cd110adbd0b3_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::PackageCatalog,winrt::Windows::ApplicationModel::PackageStatusChangedEventArgs>,_lambda_aa7b611dc7a5a165e652cd110adbd0b3_>::`vftable'
0x180021f51  mov     [rbx], rax
0x180021f54  mov     [rbp+57h+arg_8], rbx
0x180021f58  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x180021f5c  test    rcx, rcx
0x180021f5f  jz      short loc_180021F7B
0x180021f61  or      eax, 0FFFFFFFFh
0x180021f64  lock xadd [rcx+0Ch], eax
0x180021f69  cmp     eax, 1
0x180021f6c  jnz     short loc_180021F7B
0x180021f6e  mov     rax, [rcx]
0x180021f71  mov     rax, [rax+8]
0x180021f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f7a  nop
0x180021f7b  mov     [rbp+57h+hKey], r12
0x180021f7f  mov     rcx, [r15]
0x180021f82  mov     [rbp+57h+var_78], r12d
0x180021f86  xorps   xmm0, xmm0
0x180021f89  movdqu  [rbp+57h+var_70], xmm0
0x180021f8e  mov     rax, [rcx]
0x180021f91  lea     r8, [rbp+57h+hKey]
0x180021f95  mov     rdx, rbx
0x180021f98  mov     rax, [rax+70h]
0x180021f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa1  test    eax, eax
0x180021fa3  js      loc_180022387
0x180021fa9  mov     rbx, [rbp+57h+hKey]
0x180021fad  mov     rdx, r15
0x180021fb0  lea     rcx, [rbp+57h+var_B0]
0x180021fb4  call    ??$?0AEBUIPackageCatalog@ApplicationModel@Windows@winrt@@X@?$weak_ref@UIPackageCatalog@ApplicationModel@Windows@winrt@@@winrt@@QEAA@AEBUIPackageCatalog@ApplicationModel@Windows@1@@Z; winrt::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>(winrt::Windows::ApplicationModel::IPackageCatalog const &)
0x180021fb9  mov     qword ptr [rbp+57h+var_B0+8], rbx
0x180021fbd  lea     rsi, [rdi+30h]
0x180021fc1  mov     r14, qword ptr [rbp+57h+var_B0]
0x180021fc5  mov     qword ptr [rbp+57h+var_B0], r12
0x180021fc9  mov     [rbp+57h+var_50], r12
0x180021fcd  mov     [rbp+57h+var_88], r14
0x180021fd1  lea     rax, [rbp+57h+var_50]
0x180021fd5  cmp     rax, rsi
0x180021fd8  jz      short loc_180021FE4
0x180021fda  mov     rax, [rsi]
0x180021fdd  mov     [rsi], r12
0x180021fe0  mov     [rbp+57h+var_50], rax
0x180021fe4  lea     rax, [rbp+57h+var_88]
0x180021fe8  cmp     rsi, rax
0x180021feb  jz      short loc_180021FFF
0x180021fed  cmp     [rsi], r12
0x180021ff0  jz      short loc_180021FFA
0x180021ff2  mov     rcx, rsi
0x180021ff5  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180021ffa  mov     [rsi], r14
0x180021ffd  jmp     short loc_18002200D
0x180021fff  test    r14, r14
0x180022002  jz      short loc_18002200D
0x180022004  lea     rcx, [rbp+57h+var_88]
0x180022008  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18002200d  mov     rax, [rsi+8]
0x180022011  mov     [rbp+57h+var_48], rax
0x180022015  mov     [rsi+8], rbx
0x180022019  lea     rcx, [rbp+57h+var_50]
0x18002201d  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BHI@AA@impl@winrt@@QEAA@XZ
0x180022022  lea     rcx, [rbp+57h+var_B0]
0x180022026  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BHI@AA@impl@winrt@@QEAA@XZ
0x18002202b  nop
0x18002202c  lea     rcx, [rbp+57h+arg_8]
0x180022030  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180022035  nop
0x180022036  xorps   xmm0, xmm0
0x180022039  movdqa  [rbp+57h+var_A0], xmm0
0x18002203e  mov     rdx, [rdi+8]
0x180022042  test    rdx, rdx
0x180022045  jz      short loc_18002205B
0x180022047  mov     rax, [rdi]
0x18002204a  mov     qword ptr [rbp+57h+var_A0], rax
0x18002204e  mov     qword ptr [rbp+57h+var_A0+8], rdx
0x180022052  lock inc dword ptr [rdx+0Ch]
0x180022056  movdqa  xmm0, [rbp+57h+var_A0]
0x18002205b  movdqa  [rbp+57h+var_C0], xmm0
0x180022060  xorps   xmm0, xmm0
0x180022063  movdqa  [rbp+57h+var_A0], xmm0
0x180022068  lea     rax, [rbp+57h+var_C0]
0x18002206c  mov     [rbp+57h+hKey], rax
0x180022070  mov     ecx, 20h ; ' '; Size
0x180022075  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002207a  mov     rbx, rax
0x18002207d  mov     [rbp+57h+hKey], rax
0x180022081  mov     dword ptr [rax+8], 1
0x180022088  mov     [rax+10h], r12
0x18002208c  mov     [rax+18h], r12
0x180022090  mov     rcx, qword ptr [rbp+57h+var_C0]
0x180022094  mov     [rax+10h], rcx
0x180022098  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18002209c  mov     [rax+18h], rcx
0x1800220a0  xorps   xmm0, xmm0
0x1800220a3  movdqa  [rbp+57h+var_C0], xmm0
0x1800220a8  lea     rcx, [rax+20h]
0x1800220ac  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800220b1  lea     rax, ??_7?$delegate@U?$TypedEventHandler@UPackageCatalog@ApplicationModel@Windows@winrt@@UPackageUninstallingEventArgs@234@@Foundation@Windows@winrt@@V_lambda_d647519c5959a5ccfdcec94345adfb07_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::ApplicationModel::PackageCatalog,winrt::Windows::ApplicationModel::PackageUninstallingEventArgs>,_lambda_d647519c5959a5ccfdcec94345adfb07_>::`vftable'
0x1800220b8  mov     [rbx], rax
0x1800220bb  mov     [rbp+57h+arg_8], rbx
0x1800220bf  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x1800220c3  test    rcx, rcx
0x1800220c6  jz      short loc_1800220E2
0x1800220c8  or      eax, 0FFFFFFFFh
0x1800220cb  lock xadd [rcx+0Ch], eax
0x1800220d0  cmp     eax, 1
0x1800220d3  jnz     short loc_1800220E2
0x1800220d5  mov     rax, [rcx]
0x1800220d8  mov     rax, [rax+8]
0x1800220dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e1  nop
0x1800220e2  mov     [rbp+57h+hKey], r12
0x1800220e6  mov     rcx, [r15]
0x1800220e9  mov     [rbp+57h+var_78], r12d
0x1800220ed  xorps   xmm0, xmm0
0x1800220f0  movdqu  [rbp+57h+var_70], xmm0
0x1800220f5  mov     rax, [rcx]
0x1800220f8  lea     r8, [rbp+57h+hKey]
0x1800220fc  mov     rdx, rbx
0x1800220ff  mov     rax, [rax+60h]
0x180022103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022108  test    eax, eax
0x18002210a  js      loc_18002236F
0x180022110  mov     rbx, [rbp+57h+hKey]
0x180022114  mov     rdx, r15
0x180022117  lea     rcx, [rbp+57h+var_B0]
0x18002211b  call    ??$?0AEBUIPackageCatalog@ApplicationModel@Windows@winrt@@X@?$weak_ref@UIPackageCatalog@ApplicationModel@Windows@winrt@@@winrt@@QEAA@AEBUIPackageCatalog@ApplicationModel@Windows@1@@Z; winrt::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>::weak_ref<winrt::Windows::ApplicationModel::IPackageCatalog>(winrt::Windows::ApplicationModel::IPackageCatalog const &)
0x180022120  mov     qword ptr [rbp+57h+var_B0+8], rbx
0x180022124  lea     rsi, [rdi+40h]
0x180022128  mov     r14, qword ptr [rbp+57h+var_B0]
0x18002212c  mov     qword ptr [rbp+57h+var_B0], r12
0x180022130  mov     [rbp+57h+var_40], r12
0x180022134  mov     [rbp+57h+var_80], r14
0x180022138  lea     rax, [rbp+57h+var_40]
0x18002213c  cmp     rax, rsi
0x18002213f  jz      short loc_18002214B
0x180022141  mov     rax, [rsi]
0x180022144  mov     [rsi], r12
0x180022147  mov     [rbp+57h+var_40], rax
0x18002214b  lea     rax, [rbp+57h+var_80]
0x18002214f  cmp     rsi, rax
0x180022152  jz      short loc_180022166
0x180022154  cmp     [rsi], r12
0x180022157  jz      short loc_180022161
0x180022159  mov     rcx, rsi
0x18002215c  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180022161  mov     [rsi], r14
0x180022164  jmp     short loc_180022174
0x180022166  test    r14, r14
0x180022169  jz      short loc_180022174
0x18002216b  lea     rcx, [rbp+57h+var_80]
0x18002216f  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180022174  mov     rax, [rsi+8]
0x180022178  mov     [rbp+57h+var_38], rax
0x18002217c  mov     [rsi+8], rbx
0x180022180  lea     rcx, [rbp+57h+var_40]
0x180022184  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BGI@AA@impl@winrt@@QEAA@XZ
0x180022189  lea     rcx, [rbp+57h+var_B0]
  ... truncated ...
```
