# UWAInstallWork::_DownloadWithOptionalRetry(IUpdateSession *,bool,uint,uint,bool,long,char const *,long *)

- ea: `0x1800f7914`
- end: `0x1800f8471`
- name: `?_DownloadWithOptionalRetry@UWAInstallWork@@AEAAJPEAUIUpdateSession@@_NII1JPEBDPEAJ@Z`
- size: `2909`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, struct IUpdateSession *, bool, unsigned int, unsigned int, bool, int, const char *, int *)`
- caller_count: `2`
- callee_count: `45`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f17e0`
- `0x1800f7914`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800116f4`
- `0x180012368`
- `0x1800123f8`
- `0x1800127c8`
- `0x18001c414`
- `0x18001c844`
- `0x18003dcd4`
- `0x18003e024`
- `0x18003e558`
- `0x180040268`
- `0x180042b9c`
- `0x180044bc0`
- `0x180044c3c`
- `0x180044cf4`
- `0x180044f88`
- `0x180046110`
- `0x180052008`
- `0x180073690`
- `0x1800755d0`
- `0x18007aa00`
- `0x18007c3c4`
- `0x1800de12c`
- `0x1800de530`
- `0x1800de5d4`
- `0x1800e23d8`
- `0x1800e41d0`
- `0x1800e4684`
- `0x1800e4b84`
- `0x1800e4d14`
- `0x1800e4fb0`
- `0x1800e5ee8`
- `0x1800e9334`
- `0x1800ee3e8`
- `0x1800f7914`
- `0x1800f964c`
- `0x1800f9764`
- `0x1800fa4c0`
- `0x1800fba28`
- `0x1800fbfc4`
- `0x1800fdbb8`
- `0x1800fe6dc`
- `0x180149adc`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f7ec2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f7ec2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f79d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f79d6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f7ce8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f7ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7b07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7ed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7f1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7f2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7f40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f811c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f812e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f834b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7b07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7ed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7f1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7f2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7f40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f811c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f812e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f834b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f81dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f81dd`

## string_xrefs

- `0x1800f7bdd`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f7dc0`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f7e04`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f7f05`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f7ff9`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f8388`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f7bd6`: `UWAInstallWork::_DownloadWithOptionalRetry`
- `0x1800f7ef8`: `UWAInstallWork::_DownloadWithOptionalRetry`
- `0x1800f8005`: `UWAInstallWork::_DownloadWithOptionalRetry`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall UWAInstallWork::_DownloadWithOptionalRetry(
        UWAInstallWork *this,
        struct IUpdateSession *a2,
        bool a3,
        unsigned __int32 a4,
        unsigned int a5,
        bool a6,
        int a7,
        char *a8,
        int *a9)
{
  __int16 v10; // di
  __int64 v12; // rax
  __int64 v13; // rax
  struct IUpdateDownloader *v14; // rcx
  struct IDownloadProgressChangedCallback *v15; // rbx
  int v16; // edx
  int v17; // ecx
  int v18; // r12d
  __int16 v19; // cx
  __int16 v20; // r12
  HSTRING v21; // r15
  struct IDownloadCompletedCallback *v22; // r14
  unsigned __int16 *StringRawBuffer; // rsi
  HSTRING Intent; // rbx
  struct IUpdateCollection *v25; // rdi
  char *v26; // rdx
  __int64 TokenOrEmpty; // rax
  int v28; // esi
  UWAInstallWork *v29; // rcx
  int v31; // ecx
  const unsigned __int16 *v32; // rax
  int v33; // eax
  UWAInstallWork *v34; // rcx
  int DownloadExtendedHResult; // eax
  struct IUpdateDownloader *v36; // rdi
  HRESULT (__stdcall *EndDownload)(IUpdateDownloader *, IDownloadJob *, IDownloadResult **); // rbx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int Update; // eax
  _QWORD *v42; // rax
  DWORD ImmediateRetryDownloadDelayFromOneSettings; // eax
  const unsigned __int16 *v44; // rax
  const unsigned __int16 *v45; // rdi
  const unsigned __int16 *v46; // rbx
  WindowsUpdate::CommonTelemetry *v47; // rax
  int v48; // r14d
  const unsigned __int16 *v49; // rdi
  const unsigned __int16 *v50; // rbx
  WindowsUpdate::CommonTelemetry *v51; // rax
  const unsigned __int16 *v52; // rdi
  const unsigned __int16 *v53; // rbx
  WindowsUpdate::CommonTelemetry *v54; // rax
  __int64 v55; // rcx
  LPVOID v56; // rax
  wil::details::in1diag3 *v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  char v60; // bl
  const unsigned __int16 *v61; // rax
  int v62; // ebx
  int v64; // [rsp+28h] [rbp-D8h]
  int v65; // [rsp+28h] [rbp-D8h]
  int v66; // [rsp+28h] [rbp-D8h]
  int v67; // [rsp+28h] [rbp-D8h]
  struct IDownloadProgressChangedCallback *v68; // [rsp+30h] [rbp-D0h]
  struct IDownloadCompletedCallback *v69; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v70; // [rsp+38h] [rbp-C8h]
  struct IDownloadCompletedCallback *v71; // [rsp+38h] [rbp-C8h]
  struct IDownloadCompletedCallback *v72; // [rsp+38h] [rbp-C8h]
  struct IUpdateDownloader **v73; // [rsp+50h] [rbp-B0h]
  struct IUpdateDownloader **v74; // [rsp+50h] [rbp-B0h]
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  enum tagOperationResultCode v77; // [rsp+70h] [rbp-90h] BYREF
  UWAInstallWork *p_pv; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR bstrString[4]; // [rsp+80h] [rbp-80h] BYREF
  struct IUpdateDownloader *v80; // [rsp+88h] [rbp-78h] BYREF
  __int128 v81; // [rsp+90h] [rbp-70h] BYREF
  char *v82; // [rsp+A0h] [rbp-60h]
  struct IDownloadProgressChangedCallback *v83; // [rsp+A8h] [rbp-58h] BYREF
  struct IUpdateSession *v84; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v85; // [rsp+B8h] [rbp-48h]
  int *v86; // [rsp+C0h] [rbp-40h]
  __int128 pv; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v88; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v89; // [rsp+E4h] [rbp-1Ch]
  __int64 v90; // [rsp+F0h] [rbp-10h]
  __int64 v91; // [rsp+F8h] [rbp-8h]
  __int64 v92; // [rsp+100h] [rbp+0h]
  __int64 v93; // [rsp+108h] [rbp+8h]
  char v94[16]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v95; // [rsp+120h] [rbp+20h]
  __int128 v96; // [rsp+130h] [rbp+30h]
  __int128 v97; // [rsp+140h] [rbp+40h]
  __int128 v98; // [rsp+150h] [rbp+50h]
  __int128 v99; // [rsp+160h] [rbp+60h]
  __int128 v100; // [rsp+170h] [rbp+70h]
  __int128 v101; // [rsp+180h] [rbp+80h]
  char v102; // [rsp+190h] [rbp+90h]

  v85 = a4;
  v10 = a3;
  v84 = a2;
  v77 = a4;
  v82 = a8;
  v86 = a9;
  pv = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v83 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl'::`2'::impl)
    && GetEnablePollDownloadProgress() )
  {
    *(_QWORD *)&pv = this;
    LOBYTE(v88) = 0;
    v89 = __PAIR64__(a5, a4);
    *((_QWORD *)&pv + 1) = CreateThreadpoolWork(UWAInstallWork::s_PollDownloadProgressCallback, &pv, 0);
    p_pv = (UWAInstallWork *)&pv;
    *(_QWORD *)bstrString = this;
    v12 = Microsoft::WRL::Details::Make<DownloadProgress,UWAInstallWork *,unsigned int &,unsigned int &,UWAInstallWork::PollingDownloadProgressContext *>(
            (unsigned int)&v80,
            (unsigned int)bstrString,
            (unsigned int)&v77,
            (unsigned int)&a5,
            (__int64)&p_pv);
    Microsoft::WRL::ComPtr<DownloadProgress>::operator=(&v83, v12);
  }
  else
  {
    p_pv = this;
    v13 = Microsoft::WRL::Details::Make<DownloadProgress,UWAInstallWork *,unsigned int &,unsigned int &>(
            &v80,
            &p_pv,
            &v77,
            &a5);
    Microsoft::WRL::ComPtr<DownloadProgress>::operator=(&v83, v13);
  }
  v14 = v80;
  if ( v80 )
  {
    v80 = 0;
    ((void (__fastcall *)(struct IUpdateDownloader *))v14->lpVtbl->Release)(v14);
  }
  v15 = v83;
  if ( v83 )
  {
    v80 = 0;
    *(_QWORD *)bstrString = 0;
    v16 = *((_DWORD *)this + 32);
    v17 = 32;
    if ( v16 != 4 )
      v17 = 0;
    v18 = (v16 == 1)
        | v17
        | (16 * (*((_DWORD *)this + 264) & 1))
        | (*((_DWORD *)this + 264) >> 2) & 0x4000
        | (32 * (*((_DWORD *)this + 264) & 6));
    v19 = 8200;
    if ( v16 != 3 )
      v19 = 0;
    v20 = (v10 << 10) | v19 | v18;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(bstrString);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v80);
    v21 = (HSTRING)*((_QWORD *)this + 10);
    v22 = (struct IDownloadCompletedCallback *)((unsigned __int64)&v15[1] & -(__int64)(v15 != 0));
    StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
    Intent = UWAInstallWork::_GetIntent(this);
    v25 = (struct IUpdateCollection *)*((_QWORD *)this + 13);
    v26 = (char *)this + 224;
    if ( !*((_QWORD *)this + 28) )
      v26 = (char *)this + 152;
    TokenOrEmpty = CallerContext::ContextData::_TryGetTokenOrEmpty(v26);
    v28 = DownloadPackages(
            *(void **)(TokenOrEmpty + 8),
            v84,
            v25,
            v20,
            Intent,
            StringRawBuffer,
            v83,
            v22,
            v21,
            v82,
            &v80,
            (struct IUpdateInternalConfiguration *)bstrString);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl'::`2'::impl) )
    {
      if ( v28 < 0 )
      {
        if ( *((_QWORD *)&pv + 1) )
          UWAInstallWork::CleanupDownloadProgressPollingThread(
            v29,
            (struct UWAInstallWork::PollingDownloadProgressContext *)&pv);
        goto LABEL_82;
      }
    }
    else if ( v28 < 0 )
    {
LABEL_82:
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(bstrString);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v80);
      v15 = v83;
      goto LABEL_84;
    }
    wil::AcquireSRWLockExclusive(&p_pv, (char *)this + 1048);
    if ( *((_DWORD *)this + 265) == 2 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
      {
        if ( !((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl'::`2'::impl)
             ? !UWAInstallWork::_ShouldUseAsyncLicensing(this)
             : GetDisableAsyncLicensing()) )
        {
          v31 = *((_DWORD *)this + 281);
          if ( (int)(v31 + 0x80000000) >= 0 && v31 != -2147483638 )
          {
            v32 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
            LogSimpleMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0x1173u,
              "UWAInstallWork::_DownloadWithOptionalRetry",
              *((_DWORD *)this + 281),
              L"Licensing failed, aborting download",
              (const char *)this + 304,
              v32);
            v28 = *((_DWORD *)this + 281);
          }
        }
      }
      if ( v28 >= 0 )
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
          (char *)this + 1144,
          bstrString);
    }
    else
    {
      v28 = -2147467260;
    }
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&p_pv);
    if ( v28 < 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)bstrString + 96LL))(*(_QWORD *)bstrString);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl'::`2'::impl)
      && *((_QWORD *)&pv + 1) )
    {
      SubmitThreadpoolWork(*((PTP_WORK *)&pv + 1));
    }
    v33 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)bstrString + 80LL))(*(_QWORD *)bstrString);
    v28 = TraceHR(
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            0x118Cu,
            "UWAInstallWork::_DownloadWithOptionalRetry",
            "spJob->CleanUp()",
            v33,
            v64);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl'::`2'::impl) )
      UWAInstallWork::CleanupDownloadProgressPollingThread(
        v34,
        (struct UWAInstallWork::PollingDownloadProgressContext *)&pv);
    if ( v28 >= 0 )
    {
      v76 = *(_QWORD *)bstrString;
      if ( *(_QWORD *)bstrString )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)bstrString + 8LL))(*(_QWORD *)bstrString);
      DownloadExtendedHResult = GetDownloadExtendedHResult(&v76, v86);
      TraceHR(
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x1196u,
        "UWAInstallWork::_DownloadWithOptionalRetry",
        "GetDownloadExtendedHResult(spJob, phrExtended)",
        DownloadExtendedHResult,
        v65);
      p_pv = 0;
      v36 = v80;
      EndDownload = v80->lpVtbl->EndDownload;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&p_pv);
      v38 = ((__int64 (__fastcall *)(struct IUpdateDownloader *, _QWORD, UWAInstallWork **))EndDownload)(
              v36,
              *(_QWORD *)bstrString,
              &p_pv);
      v28 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0x1198u,
              "UWAInstallWork::_DownloadWithOptionalRetry",
              "spDownloader->EndDownload(spJob.Get(), &spResult)",
              v38,
              v66);
      if ( v28 >= 0 )
      {
        v77 = orcNotStarted;
        v39 = (*(__int64 (__fastcall **)(UWAInstallWork *, enum tagOperationResultCode *))(*(_QWORD *)p_pv + 64LL))(
                p_pv,
                &v77);
        v28 = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                0x119Cu,
                "UWAInstallWork::_DownloadWithOptionalRetry",
                "spResult->get_ResultCode(&orc)",
                v39,
                v67);
        if ( v28 >= 0 )
        {
          v40 = HResultFromWUResult(v77);
          v28 = v40;
          if ( v40 >= 0 )
            goto LABEL_63;
          if ( v40 != -2147467260 )
          {
            Update = GetUpdateResult<IUpdateDownloadResult,IDownloadResult>(*((_QWORD *)this + 13), p_pv);
            v28 = Update;
            if ( a6 && IsImmediateRetryDownloadErrorCode(Update) )
            {
              ++*((_DWORD *)this + 270);
              v76 = 0;
              v42 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::ensure_data(&v76);
              tip2::details::shared_data<1,0,0>::start(*v42 + 8LL, &v81);
              *(_OWORD *)((char *)this + 1324) = v81;
              *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::operator->(
                                       &v76,
                                       &v81)
                        + 272LL) = v28;
              tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>(&v81);
              ImmediateRetryDownloadDelayFromOneSettings = GetImmediateRetryDownloadDelayFromOneSettings();
              if ( ImmediateRetryDownloadDelayFromOneSettings )
                Sleep(ImmediateRetryDownloadDelayFromOneSettings);
              v44 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
              LogSimpleMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                0x11B0u,
                "UWAInstallWork::_DownloadWithOptionalRetry",
                v28,
                L"Immediate Retry Download for Error ",
                (const char *)this + 304,
                v44);
              v45 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
              v46 = WindowsGetStringRawBuffer(*((HSTRING *)this + 57), 0);
              v47 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
              LOBYTE(v69) = 4;
              WindowsUpdate::CommonTelemetry::StateTransition(
                v47,
                v46,
                v45,
                0,
                0,
                (const unsigned __int16 *)"Error",
                "ImmediateRetry",
                (const char *)v69,
                v28,
                (__int64)v82,
                (const char *)v73);
              v48 = v28;
              v28 = UWAInstallWork::_DownloadWithOptionalRetry(this, v84, a3, v85, a5, 0, v28, v82, v86);
              *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::operator->(
                                       &v76,
                                       &v81)
                        + 276LL) = v28;
              tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>(&v81);
              v70 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
              v68 = (struct IDownloadProgressChangedCallback *)((char *)this + 304);
              if ( v28 < 0 )
              {
                LogSimpleMessage(
                  1u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                  0x11D2u,
                  "UWAInstallWork::_DownloadWithOptionalRetry",
                  v28,
                  L"Immediate Retry Download failed",
                  (const char *)v68,
                  v70);
                *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::operator->(
                                        &v76,
                                        &v81)
                         + 280LL) = 0;
                tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>(&v81);
                v52 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
                v53 = WindowsGetStringRawBuffer(*((HSTRING *)this + 57), 0);
                v54 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
                LOBYTE(v72) = 4;
                WindowsUpdate::CommonTelemetry::StateTransition(
                  v54,
                  v53,
                  v52,
                  0,
                  0,
                  (const unsigned __int16 *)"ImmediateRetry",
                  "Error",
                  (const char *)v72,
                  v48,
                  (__int64)v82,
                  (const char *)v74);
                v28 = v48;
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
                  *((_BYTE *)this + 986) = 1;
              }
              else
              {
                LogSimpleMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                  0x11C2u,
                  "UWAInstallWork::_DownloadWithOptionalRetry",
                  -1,
                  L"Immediate Retry Download Succeeded",
                  (const char *)v68,
                  v70);
                *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::operator->(
                                        &v76,
                                        &v81)
                         + 280LL) = 1;
                tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>>(&v81);
                v49 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
                v50 = WindowsGetStringRawBuffer(*((HSTRING *)this + 57), 0);
                v51 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
                LOBYTE(v71) = 4;
                WindowsUpdate::CommonTelemetry::StateTransition(
                  v51,
                  v50,
                  v49,
                  0,
                  0,
                  (const unsigned __int16 *)"ImmediateRetry",
                  "Working",
                  (const char *)v71,
                  v48,
                  (__int64)v82,
                  (const char *)v74);
              }
              v81 = *(_OWORD *)((char *)this + 1324);
              if ( !v76 || (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v76 + 8) )
              {
                v56 = CoTaskMemAlloc(0x128u);
                if ( !v56 )
                  wil::details::in1diag3::_FailFastImmediate_Unexpected(v57);
                v84 = (struct IUpdateSession *)tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>(
                                                 v56,
                                                 &v81);
                wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>,wil::err_returncode_policy>::operator=(
                  &v76,
                  &v84);
                wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>,wil::err_returncode_policy>(&v84);
              }
              else
              {
                tip2::details::shared_data<1,0,0>::open_without_lock(v55, &v81);
              }
              if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v76 + 8) && v58 )
                tip2::details::shared_data<1,0,0>::complete_without_lock(v59);
              wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ImmediateRetryDownloadTipTest,TipTests::_tip_ImmediateRetryDownloadTipTest>,wil::err_returncode_policy>(&v76);
            }
            *((_DWORD *)this + 268) = *v86;
            if ( v28 >= 0 )
            {
LABEL_63:
              v60 = 0;
              wil::AcquireSRWLockExclusive(&v81, (char *)this + 1048);
              if ( *((_DWORD *)this + 265) == 2 )
              {
                *((_DWORD *)this + 273) = *((_DWORD *)this + 272);
                if ( a3 || *((_DWORD *)this + 32) == 1 )
                  *((_DWORD *)this + 265) = 8;
                else
                  v60 = 1;
              }
              if ( !*((_DWORD *)this + 283) )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
                {
                  *(_OWORD *)v94 = *((_OWORD *)this + 19);
                  v95 = *((_OWORD *)this + 20);
                  v96 = *((_OWORD *)this + 21);
                  v97 = *((_OWORD *)this + 22);
                  v98 = *((_OWORD *)this + 23);
                  v99 = *((_OWORD *)this + 24);
                  v100 = *((_OWORD *)this + 25);
                  v101 = *((_OWORD *)this + 26);
                  v102 = *((_BYTE *)this + 432);
                }
                else
                {
                  TraceLoggingCorrelationVector::ToStringImpl(
                    *((TraceLoggingCorrelationVector **)this + 37),
                    _InterlockedExchangeAdd64((volatile signed __int64 *)(*((_QWORD *)this + 37) + 136LL), 0),
                    v94);
                }
                v61 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
                LogMessage(
                  1u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                  0x1203u,
                  "UWAInstallWork::_DownloadWithOptionalRetry",
                  -1,
                  L"Assert (%s): Failed",
                  v94,
                  v61,
                  L"_streamingType != StreamingType_Undetermined");
                __int2c();
              }
              Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v81);
              if ( v60 )
                UWAInstallWork::_InstallCompleted(this);
              if ( (*((_BYTE *)this + 1056) & 0x40) != 0 )
                UWAInstallWork::_RaiseProgressEvent(this, 0);
            }
          }
        }
      }
      if ( v28 == -2145124341 )
        v28 = -2147467260;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&p_pv);
    }
    wil::AcquireSRWLockExclusive(&v81, (char *)this + 1048);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)this + 1144);
    v62 = *((_DWORD *)this + 265);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v81);
    if ( v62 == 5 )
      UWAInstallWork::_CleanupAfterCancel(this);
    goto LABEL_82;
  }
  v28 = a7;
LABEL_84:
  if ( v15 )
    ((void (__fastcall *)(struct IDownloadProgressChangedCallback *))v15->lpVtbl->Release)(v15);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x1800f7914  push    rbp
0x1800f7916  push    rbx
0x1800f7917  push    rsi
0x1800f7918  push    rdi
0x1800f7919  push    r12
0x1800f791b  push    r13
0x1800f791d  push    r14
0x1800f791f  push    r15
0x1800f7921  lea     rbp, [rsp-0B8h]
0x1800f7929  sub     rsp, 1B8h
0x1800f7930  mov     rax, cs:__security_cookie
0x1800f7937  xor     rax, rsp
0x1800f793a  mov     [rbp+0F0h+var_50], rax
0x1800f7941  mov     ebx, r9d
0x1800f7944  mov     [rbp+0F0h+var_138], ebx
0x1800f7947  movzx   edi, r8b
0x1800f794b  mov     [rsp+1F0h+var_190], dil
0x1800f7950  mov     [rbp+0F0h+var_140], rdx
0x1800f7954  mov     r13, rcx
0x1800f7957  mov     [rsp+1F0h+var_180], ebx
0x1800f795b  mov     rax, [rbp+0F0h+arg_38]
0x1800f7962  mov     [rbp+0F0h+var_150], rax
0x1800f7966  mov     rax, [rbp+0F0h+arg_40]
0x1800f796d  mov     [rbp+0F0h+var_130], rax
0x1800f7971  xorps   xmm0, xmm0
0x1800f7974  movdqa  [rbp+0F0h+pv], xmm0
0x1800f7979  xor     r14d, r14d
0x1800f797c  mov     [rbp+0F0h+var_110], r14w
0x1800f7981  mov     [rbp+0F0h+var_10C], r14
0x1800f7985  mov     [rbp+0F0h+var_100], r14
0x1800f7989  mov     [rbp+0F0h+var_F8], r14
0x1800f798d  mov     [rbp+0F0h+var_F0], r14
0x1800f7991  mov     [rbp+0F0h+var_E8], r14
0x1800f7995  mov     [rbp+0F0h+var_148], r14
0x1800f7999  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PollDownloadProgress@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PollDownloadProgress@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress> `wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl(void)'::`2'::impl
0x1800f79a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PollDownloadProgress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(void)
0x1800f79a5  test    al, al
0x1800f79a7  jz      short loc_1800F7A1F
0x1800f79a9  call    ?GetEnablePollDownloadProgress@@YA_NXZ; GetEnablePollDownloadProgress(void)
0x1800f79ae  test    al, al
0x1800f79b0  jz      short loc_1800F7A1F
0x1800f79b2  mov     qword ptr [rbp+0F0h+pv], r13
0x1800f79b6  mov     eax, r14d
0x1800f79b9  xchg    al, byte ptr [rbp+0F0h+var_110]
0x1800f79bc  mov     dword ptr [rbp+0F0h+var_10C], ebx
0x1800f79bf  mov     eax, [rbp+0F0h+arg_20]
0x1800f79c5  mov     dword ptr [rbp+0F0h+var_10C+4], eax
0x1800f79c8  xor     r8d, r8d; pcbe
0x1800f79cb  lea     rdx, [rbp+0F0h+pv]; pv
0x1800f79cf  lea     rcx, ?s_PollDownloadProgressCallback@UWAInstallWork@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f79d6  call    cs:__imp_CreateThreadpoolWork
0x1800f79dc  mov     qword ptr [rbp+0F0h+pv+8], rax
0x1800f79e0  lea     rax, [rbp+0F0h+pv]
0x1800f79e4  mov     [rsp+1F0h+var_178], rax
0x1800f79e9  mov     qword ptr [rbp+0F0h+var_170], r13
0x1800f79ed  lea     rax, [rsp+1F0h+var_178]
0x1800f79f2  mov     [rsp+1F0h+var_1D0], rax
0x1800f79f7  lea     r9, [rbp+0F0h+arg_20]
0x1800f79fe  lea     r8, [rsp+1F0h+var_180]
0x1800f7a03  lea     rdx, [rbp+0F0h+var_170]
0x1800f7a07  lea     rcx, [rbp+0F0h+var_168]
0x1800f7a0b  call    ??$Make@VDownloadProgress@@PEAVUWAInstallWork@@AEAIAEAIPEAUPollingDownloadProgressContext@2@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VDownloadProgress@@@12@$$QEAPEAVUWAInstallWork@@AEAI1$$QEAPEAUPollingDownloadProgressContext@4@@Z; Microsoft::WRL::Details::Make<DownloadProgress,UWAInstallWork *,uint &,uint &,UWAInstallWork::PollingDownloadProgressContext *>(UWAInstallWork * &&,uint &,uint &,UWAInstallWork::PollingDownloadProgressContext * &&)
0x1800f7a10  mov     rdx, rax
0x1800f7a13  lea     rcx, [rbp+0F0h+var_148]
0x1800f7a17  call    ??4?$ComPtr@VDownloadProgress@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<DownloadProgress>::operator=(Microsoft::WRL::ComPtr<DownloadProgress> &&)
0x1800f7a1c  nop
0x1800f7a1d  jmp     short loc_1800F7A4B
0x1800f7a1f  mov     [rsp+1F0h+var_178], r13
0x1800f7a24  lea     r9, [rbp+0F0h+arg_20]
0x1800f7a2b  lea     r8, [rsp+1F0h+var_180]
0x1800f7a30  lea     rdx, [rsp+1F0h+var_178]
0x1800f7a35  lea     rcx, [rbp+0F0h+var_168]
0x1800f7a39  call    ??$Make@VDownloadProgress@@PEAVUWAInstallWork@@AEAIAEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VDownloadProgress@@@12@$$QEAPEAVUWAInstallWork@@AEAI1@Z; Microsoft::WRL::Details::Make<DownloadProgress,UWAInstallWork *,uint &,uint &>(UWAInstallWork * &&,uint &,uint &)
0x1800f7a3e  mov     rdx, rax
0x1800f7a41  lea     rcx, [rbp+0F0h+var_148]
0x1800f7a45  call    ??4?$ComPtr@VDownloadProgress@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<DownloadProgress>::operator=(Microsoft::WRL::ComPtr<DownloadProgress> &&)
0x1800f7a4a  nop
0x1800f7a4b  mov     rcx, [rbp+0F0h+var_168]
0x1800f7a4f  test    rcx, rcx
0x1800f7a52  jz      short loc_1800F7A65
0x1800f7a54  mov     [rbp+0F0h+var_168], r14
0x1800f7a58  mov     rax, [rcx]
0x1800f7a5b  mov     rax, [rax+10h]
0x1800f7a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7a64  nop
0x1800f7a65  mov     rbx, [rbp+0F0h+var_148]
0x1800f7a69  test    rbx, rbx
0x1800f7a6c  jz      loc_1800F842B
0x1800f7a72  mov     [rbp+0F0h+var_168], r14
0x1800f7a76  mov     qword ptr [rbp+0F0h+var_170], r14
0x1800f7a7a  mov     edx, [r13+80h]
0x1800f7a81  mov     ecx, [r13+420h]
0x1800f7a88  mov     r12d, ecx
0x1800f7a8b  and     r12d, 6
0x1800f7a8f  shl     r12d, 5
0x1800f7a93  mov     eax, ecx
0x1800f7a95  shr     eax, 2
0x1800f7a98  and     eax, 4000h
0x1800f7a9d  or      r12d, eax
0x1800f7aa0  and     ecx, 1
0x1800f7aa3  shl     ecx, 4
0x1800f7aa6  or      r12d, ecx
0x1800f7aa9  mov     ecx, 20h ; ' '
0x1800f7aae  cmp     edx, 4
0x1800f7ab1  cmovnz  ecx, r14d
0x1800f7ab5  or      r12d, ecx
0x1800f7ab8  mov     eax, r14d
0x1800f7abb  cmp     edx, 1
0x1800f7abe  setz    al
0x1800f7ac1  or      r12d, eax
0x1800f7ac4  mov     ecx, 2008h
0x1800f7ac9  cmp     edx, 3
0x1800f7acc  cmovnz  ecx, r14d
0x1800f7ad0  or      r12d, ecx
0x1800f7ad3  mov     eax, edi
0x1800f7ad5  shl     eax, 0Ah
0x1800f7ad8  or      r12d, eax
0x1800f7adb  lea     rcx, [rbp+0F0h+var_170]
0x1800f7adf  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f7ae4  lea     rcx, [rbp+0F0h+var_168]
0x1800f7ae8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f7aed  mov     r15, [r13+50h]
0x1800f7af1  mov     rax, rbx
0x1800f7af4  lea     rcx, [rbx+8]
0x1800f7af8  neg     rax
0x1800f7afb  sbb     r14, r14
0x1800f7afe  and     r14, rcx
0x1800f7b01  xor     edx, edx; length
0x1800f7b03  mov     rcx, [r13+70h]; string
0x1800f7b07  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f7b0d  mov     rsi, rax
0x1800f7b10  mov     rcx, r13; this
0x1800f7b13  call    ?_GetIntent@UWAInstallWork@@AEBAPEAUHSTRING__@@XZ; UWAInstallWork::_GetIntent(void)
0x1800f7b18  mov     rbx, rax
0x1800f7b1b  mov     rdi, [r13+68h]
0x1800f7b1f  lea     rcx, [r13+98h]
0x1800f7b26  lea     rdx, [rcx+48h]
0x1800f7b2a  cmp     qword ptr [rdx], 0
0x1800f7b2e  cmovz   rdx, rcx
0x1800f7b32  mov     rcx, rdx
0x1800f7b35  call    ?_TryGetTokenOrEmpty@ContextData@CallerContext@@AEAAAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; CallerContext::ContextData::_TryGetTokenOrEmpty(void)
0x1800f7b3a  lea     rcx, [rbp+0F0h+var_170]
0x1800f7b3e  mov     [rsp+1F0h+bstrString], rcx; bstrString
0x1800f7b43  lea     rcx, [rbp+0F0h+var_168]
0x1800f7b47  mov     [rsp+1F0h+var_1A0], rcx; char *
0x1800f7b4c  mov     rcx, [rbp+0F0h+var_150]
0x1800f7b50  mov     [rsp+1F0h+var_1A8], rcx; char *
0x1800f7b55  mov     [rsp+1F0h+var_1B0], r15; HSTRING
0x1800f7b5a  mov     [rsp+1F0h+var_1B8], r14; struct IDownloadCompletedCallback *
0x1800f7b5f  mov     rcx, [rbp+0F0h+var_148]
0x1800f7b63  mov     [rsp+1F0h+var_1C0], rcx; struct IDownloadProgressChangedCallback *
0x1800f7b68  mov     [rsp+1F0h+var_1C8], rsi; unsigned __int16 *
0x1800f7b6d  mov     [rsp+1F0h+var_1D0], rbx; HSTRING
0x1800f7b72  mov     r9d, r12d; unsigned int
0x1800f7b75  mov     r8, rdi; struct IUpdateCollection *
0x1800f7b78  mov     rdx, [rbp+0F0h+var_140]; struct IUpdateSession *
0x1800f7b7c  mov     rcx, [rax+8]; void *
0x1800f7b80  call    ?DownloadPackages@@YAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIDownloadProgressChangedCallback@@PEAUIDownloadCompletedCallback@@3PEBDPEAPEAUIUpdateDownloader@@PEAPEAUIDownloadJob@@@Z; DownloadPackages(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IDownloadProgressChangedCallback *,IDownloadCompletedCallback *,HSTRING__ *,char const *,IUpdateDownloader * *,IDownloadJob * *)
0x1800f7b85  mov     esi, eax
0x1800f7b87  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PollDownloadProgress@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PollDownloadProgress@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress> `wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl(void)'::`2'::impl
0x1800f7b8e  mov     rcx, rdi
0x1800f7b91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PollDownloadProgress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(void)
0x1800f7b96  xor     r14d, r14d
0x1800f7b99  test    al, al
0x1800f7b9b  jz      short loc_1800F7BB9
0x1800f7b9d  test    esi, esi
0x1800f7b9f  jns     short loc_1800F7BC1
0x1800f7ba1  cmp     qword ptr [rbp+0F0h+pv+8], r14
0x1800f7ba5  jz      loc_1800F8412
0x1800f7bab  lea     rdx, [rbp+0F0h+pv]; struct UWAInstallWork::PollingDownloadProgressContext *
0x1800f7baf  call    ?CleanupDownloadProgressPollingThread@UWAInstallWork@@QEAAXPEAUPollingDownloadProgressContext@1@@Z; UWAInstallWork::CleanupDownloadProgressPollingThread(UWAInstallWork::PollingDownloadProgressContext *)
0x1800f7bb4  jmp     loc_1800F8412
0x1800f7bb9  test    esi, esi
0x1800f7bbb  js      loc_1800F8412
0x1800f7bc1  lea     r15, [r13+418h]
0x1800f7bc8  mov     rdx, r15
0x1800f7bcb  lea     rcx, [rsp+1F0h+var_178]
0x1800f7bd0  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f7bd5  nop
0x1800f7bd6  lea     r12, aUwainstallwork_19; "UWAInstallWork::_DownloadWithOptionalRe"...
0x1800f7bdd  lea     rbx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f7be4  cmp     dword ptr [r13+424h], 2
0x1800f7bec  jz      short loc_1800F7BF8
0x1800f7bee  mov     esi, 80004004h
0x1800f7bf3  jmp     loc_1800F7CB5
0x1800f7bf8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f7bff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(void)
0x1800f7c04  test    al, al
0x1800f7c06  jz      loc_1800F7CA0
0x1800f7c0c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f7c13  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(void)
0x1800f7c18  test    al, al
0x1800f7c1a  jz      short loc_1800F7C28
0x1800f7c1c  mov     rcx, r13; this
0x1800f7c1f  call    ?_ShouldUseAsyncLicensing@UWAInstallWork@@AEBA_NXZ; UWAInstallWork::_ShouldUseAsyncLicensing(void)
0x1800f7c24  xor     al, 1
0x1800f7c26  jmp     short loc_1800F7C2D
0x1800f7c28  call    ?GetDisableAsyncLicensing@@YA_NXZ; GetDisableAsyncLicensing(void)
0x1800f7c2d  test    al, al
0x1800f7c2f  jnz     short loc_1800F7CA0
0x1800f7c31  mov     ecx, [r13+464h]
0x1800f7c38  mov     edx, 80000000h
0x1800f7c3d  lea     eax, [rcx+rdx]
0x1800f7c40  test    edx, eax
0x1800f7c42  jnz     short loc_1800F7CA0
0x1800f7c44  cmp     ecx, 8000000Ah
0x1800f7c4a  jz      short loc_1800F7CA0
0x1800f7c4c  xor     edx, edx; length
0x1800f7c4e  mov     rcx, [r13+1D8h]; string
0x1800f7c55  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f7c5b  lea     rcx, [r13+130h]
0x1800f7c62  mov     [rsp+1F0h+var_1B8], rax; unsigned __int16 *
0x1800f7c67  mov     [rsp+1F0h+var_1C0], rcx; char *
0x1800f7c6c  lea     rax, aLicensingFaile; "Licensing failed, aborting download"
0x1800f7c73  mov     [rsp+1F0h+var_1C8], rax; int
0x1800f7c78  mov     eax, [r13+464h]
0x1800f7c7f  mov     dword ptr [rsp+1F0h+var_1D0], eax; int
0x1800f7c83  mov     r9, r12; char *
0x1800f7c86  mov     r8d, 1173h; unsigned int
0x1800f7c8c  mov     rdx, rbx; char *
0x1800f7c8f  mov     ecx, 1; unsigned int
0x1800f7c94  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800f7c99  mov     esi, [r13+464h]
0x1800f7ca0  test    esi, esi
0x1800f7ca2  js      short loc_1800F7CB5
0x1800f7ca4  lea     rcx, [r13+478h]
0x1800f7cab  lea     rdx, [rbp+0F0h+var_170]
0x1800f7caf  call    ??4?$ComPtr@U?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> const &)
0x1800f7cb4  nop
0x1800f7cb5  lea     rcx, [rsp+1F0h+var_178]; this
0x1800f7cba  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f7cbf  test    esi, esi
0x1800f7cc1  jns     short loc_1800F7CD3
0x1800f7cc3  mov     rcx, qword ptr [rbp+0F0h+var_170]
0x1800f7cc7  mov     rax, [rcx]
0x1800f7cca  mov     rax, [rax+60h]
0x1800f7cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7cd3  mov     rcx, rdi
0x1800f7cd6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PollDownloadProgress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(void)
0x1800f7cdb  test    al, al
0x1800f7cdd  jz      short loc_1800F7CEE
0x1800f7cdf  mov     rcx, qword ptr [rbp+0F0h+pv+8]; pwk
0x1800f7ce3  test    rcx, rcx
0x1800f7ce6  jz      short loc_1800F7CEE
0x1800f7ce8  call    cs:__imp_SubmitThreadpoolWork
0x1800f7cee  mov     rcx, qword ptr [rbp+0F0h+var_170]
0x1800f7cf2  mov     rax, [rcx]
0x1800f7cf5  mov     rax, [rax+50h]
0x1800f7cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7cfe  mov     dword ptr [rsp+1F0h+var_1D0], eax; int
0x1800f7d02  lea     r9, aSpjobCleanup; "spJob->CleanUp()"
0x1800f7d09  mov     r8, r12; char *
0x1800f7d0c  mov     edx, 118Ch; unsigned int
0x1800f7d11  mov     rcx, rbx; char *
0x1800f7d14  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800f7d19  mov     esi, eax
0x1800f7d1b  mov     rcx, rdi
0x1800f7d1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PollDownloadProgress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(void)
0x1800f7d23  test    al, al
0x1800f7d25  jz      short loc_1800F7D30
0x1800f7d27  lea     rdx, [rbp+0F0h+pv]; struct UWAInstallWork::PollingDownloadProgressContext *
0x1800f7d2b  call    ?CleanupDownloadProgressPollingThread@UWAInstallWork@@QEAAXPEAUPollingDownloadProgressContext@1@@Z; UWAInstallWork::CleanupDownloadProgressPollingThread(UWAInstallWork::PollingDownloadProgressContext *)
0x1800f7d30  test    esi, esi
0x1800f7d32  js      loc_1800F83DC
0x1800f7d38  mov     rcx, qword ptr [rbp+0F0h+var_170]
0x1800f7d3c  mov     [rsp+1F0h+var_188], rcx
0x1800f7d41  test    rcx, rcx
0x1800f7d44  jz      short loc_1800F7D53
0x1800f7d46  mov     rax, [rcx]
0x1800f7d49  mov     rax, [rax+8]
0x1800f7d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7d52  nop
0x1800f7d53  mov     rdx, [rbp+0F0h+var_130]
0x1800f7d57  lea     rcx, [rsp+1F0h+var_188]
0x1800f7d5c  call    ?GetDownloadExtendedHResult@@YAJV?$ComPtr@UIDownloadJob@@@WRL@Microsoft@@PEAJ@Z; GetDownloadExtendedHResult(Microsoft::WRL::ComPtr<IDownloadJob>,long *)
0x1800f7d61  mov     dword ptr [rsp+1F0h+var_1D0], eax; int
0x1800f7d65  lea     r9, aGetdownloadext; "GetDownloadExtendedHResult(spJob, phrEx"...
0x1800f7d6c  mov     r8, r12; char *
0x1800f7d6f  mov     edx, 1196h; unsigned int
0x1800f7d74  mov     rcx, rbx; char *
0x1800f7d77  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800f7d7c  mov     [rsp+1F0h+var_178], r14
0x1800f7d81  mov     rdi, [rbp+0F0h+var_168]
0x1800f7d85  mov     rax, [rdi]
0x1800f7d88  mov     rbx, [rax+88h]
0x1800f7d8f  lea     rcx, [rsp+1F0h+var_178]
0x1800f7d94  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f7d99  lea     r8, [rsp+1F0h+var_178]
0x1800f7d9e  mov     rdx, qword ptr [rbp+0F0h+var_170]
0x1800f7da2  mov     rcx, rdi
0x1800f7da5  mov     rax, rbx
0x1800f7da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7dad  mov     dword ptr [rsp+1F0h+var_1D0], eax; int
0x1800f7db1  lea     r9, aSpdownloaderEn; "spDownloader->EndDownload(spJob.Get(), "...
0x1800f7db8  mov     r8, r12; char *
0x1800f7dbb  mov     edx, 1198h; unsigned int
0x1800f7dc0  lea     rcx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f7dc7  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800f7dcc  mov     esi, eax
0x1800f7dce  test    eax, eax
  ... truncated ...
```
