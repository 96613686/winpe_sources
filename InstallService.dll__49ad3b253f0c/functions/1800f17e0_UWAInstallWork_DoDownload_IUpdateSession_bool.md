# UWAInstallWork::_DoDownload(IUpdateSession *,bool)

- ea: `0x1800f17e0`
- end: `0x1800f1fe8`
- name: `?_DoDownload@UWAInstallWork@@AEAAJPEAUIUpdateSession@@_N@Z`
- size: `2056`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, struct IUpdateSession *, bool)`
- caller_count: `2`
- callee_count: `40`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5020`
- `0x1800f584c`

## callees

- `0x180009ea0`
- `0x1800116f4`
- `0x180012368`
- `0x180012394`
- `0x1800123f8`
- `0x180012428`
- `0x1800127c8`
- `0x18001c414`
- `0x180032184`
- `0x1800321d4`
- `0x180034874`
- `0x18003f884`
- `0x180044bc0`
- `0x180044c3c`
- `0x180046110`
- `0x1800731a8`
- `0x18007aa00`
- `0x18007c3c4`
- `0x1800df870`
- `0x1800e018c`
- `0x1800e0914`
- `0x1800e1f48`
- `0x1800e4144`
- `0x1800e4cac`
- `0x1800e9440`
- `0x1800edf18`
- `0x1800f17e0`
- `0x1800f7914`
- `0x1800fa4c0`
- `0x1800fb908`
- `0x1800fcb08`
- `0x1800fd35c`
- `0x1800fd3a4`
- `0x1800fd9e8`
- `0x1800fe614`
- `0x1800ff460`
- `0x1801131e0`
- `0x180113ce8`
- `0x180116ee0`
- `0x180215010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f1b48`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f1b48`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f1b3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f1b3a`
- `msvcp_win!_Xtime_get_ticks` at `0x1800f1993`
- `msvcp_win!_Xtime_get_ticks` at `0x1800f1993`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1b28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1b9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1bb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1b28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1b9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1bb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1f8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f1ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f1ec8`

## string_xrefs

- `0x1800f1bf3`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f1dd5`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f1bd2`: `Created task progress for %s with parentbundleId %s`
- `0x1800f1be6`: `UWAInstallWork::_DoDownload`
- `0x1800f1dc8`: `UWAInstallWork::_DoDownload`
- `0x1800f1faa`: `StoreAgentDownloadFailure1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UWAInstallWork::_DoDownload(UWAInstallWork *this, struct IUpdateSession *a2, bool a3)
{
  char *v4; // r13
  int updated; // r12d
  char IsEnabled; // al
  TraceLoggingCorrelationVector *v7; // rcx
  const char *v8; // r8
  const char *v9; // r9
  _QWORD *v10; // rax
  _QWORD *v11; // r9
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rbx
  const OLECHAR *StringRawBuffer; // rdi
  OLECHAR *v21; // rcx
  BSTR v22; // rax
  int v23; // ecx
  __int64 v24; // rbx
  PCWSTR v25; // rdi
  PCWSTR v26; // rbx
  const unsigned __int16 *v27; // rax
  __int64 v28; // r14
  int v29; // eax
  unsigned int v30; // edi
  unsigned int v31; // ebx
  const unsigned __int16 *v32; // rax
  struct UWAInstallWork *v33; // rdx
  unsigned __int64 DurationInMilliseconds; // rax
  int v35; // eax
  _BYTE *v36; // rax
  LPVOID v37; // rax
  wil::details::in1diag3 *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  const unsigned __int16 *v41; // r14
  const unsigned __int16 *v42; // rsi
  const unsigned __int16 *v43; // rdi
  PCWSTR v44; // rbx
  const WCHAR *v45; // rax
  char *v47; // [rsp+30h] [rbp-188h]
  char *v48; // [rsp+38h] [rbp-180h]
  char *v50; // [rsp+60h] [rbp-158h] BYREF
  int v51; // [rsp+68h] [rbp-150h] BYREF
  int v52; // [rsp+6Ch] [rbp-14Ch]
  __int64 ticks; // [rsp+70h] [rbp-148h] BYREF
  struct UWAInstallWork *v54; // [rsp+78h] [rbp-140h] BYREF
  unsigned __int64 v55; // [rsp+80h] [rbp-138h] BYREF
  HSTRING string; // [rsp+88h] [rbp-130h] BYREF
  unsigned __int16 *v57[2]; // [rsp+90h] [rbp-128h] BYREF
  char v58; // [rsp+A0h] [rbp-118h]
  struct IUpdateSession *v59; // [rsp+B0h] [rbp-108h]
  __int128 v60; // [rsp+B8h] [rbp-100h] BYREF
  UWAInstallWork *v61; // [rsp+C8h] [rbp-F0h]
  struct IUpdateSession *v62; // [rsp+D0h] [rbp-E8h]
  char v63[16]; // [rsp+E0h] [rbp-D8h] BYREF
  __int128 v64; // [rsp+F0h] [rbp-C8h]
  __int128 v65; // [rsp+100h] [rbp-B8h]
  __int128 v66; // [rsp+110h] [rbp-A8h]
  __int128 v67; // [rsp+120h] [rbp-98h]
  __int128 v68; // [rsp+130h] [rbp-88h]
  __int128 v69; // [rsp+140h] [rbp-78h]
  __int128 v70; // [rsp+150h] [rbp-68h]
  char v71; // [rsp+160h] [rbp-58h]

  v59 = a2;
  v61 = this;
  v62 = a2;
  v4 = (char *)this + 1048;
  v57[0] = (unsigned __int16 *)((char *)this + 1048);
  wil::AcquireSRWLockExclusive(&v50, (char *)this + 1048);
  if ( (unsigned int)(*((_DWORD *)this + 265) - 5) <= 1 )
  {
    updated = -2147467260;
    v52 = -2147467260;
  }
  else
  {
    updated = 0;
    v52 = 0;
    *((_DWORD *)this + 265) = 2;
    *((_DWORD *)this + 267) = 0;
  }
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v50);
  if ( updated >= 0 )
  {
    UWAInstallWork::_RaiseProgressEvent(this, 0);
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v50, v4);
    if ( *((_DWORD *)this + 265) != 2 )
      updated = -2147467260;
    v52 = updated;
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v50);
  }
  wil::AcquireSRWLockExclusive(&v50, v4);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl);
  v7 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 37);
  if ( IsEnabled )
  {
    TraceLoggingCorrelationVector::Increment(v7, (char *)this + 304);
    *(_OWORD *)v63 = *((_OWORD *)this + 19);
    v64 = *((_OWORD *)this + 20);
    v65 = *((_OWORD *)this + 21);
    v66 = *((_OWORD *)this + 22);
    v67 = *((_OWORD *)this + 23);
    v68 = *((_OWORD *)this + 24);
    v69 = *((_OWORD *)this + 25);
    v70 = *((_OWORD *)this + 26);
    v71 = *((_BYTE *)this + 432);
  }
  else
  {
    TraceLoggingCorrelationVector::Increment(v7, v63);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v50);
  if ( updated >= 0 )
  {
    WindowsUpdate::Telemetry::BeginDownload(this, (struct UWAInstallWork *)v63, v8);
    ticks = _Xtime_get_ticks();
    v50 = (char *)this + 1056;
    if ( (*((_BYTE *)this + 1056) & 1) != 0 )
    {
      *((_QWORD *)this + 162) = *(_QWORD *)std::chrono::steady_clock::now(&v60);
      v55 = 0;
      v10 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>>::ensure_data(&v55);
      tip2::details::shared_data<1,0,0>::start(*v10 + 8LL, &v60);
      *(_OWORD *)((char *)this + 1308) = v60;
      wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>(&v55);
    }
    v11 = (_QWORD *)((char *)this + 1168);
    v12 = (__int64)(*((_QWORD *)this + 147) - *((_QWORD *)this + 146)) >> 3;
    v13 = *((_QWORD *)this + 149);
    v14 = 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 150) - v13) >> 3);
    if ( v12 >= v14 )
    {
      if ( v12 <= v14 )
      {
LABEL_21:
        v16 = 0;
        while ( 1 )
        {
          v55 = v16;
          if ( v16 >= (__int64)(*((_QWORD *)this + 147) - *v11) >> 3 )
            break;
          *(_QWORD *)&v60 = std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::at(
                              v11,
                              v16);
          string = 0;
          v17 = *(_QWORD *)v60;
          v18 = *(int (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v60 + 88LL);
          WindowsDeleteString(0);
          string = 0;
          if ( v18(v17, &string) >= 0 )
          {
            v19 = std::vector<UWAInstallWork::TaskProgressInfo>::at((char *)this + 1192, v55);
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v21 = *(OLECHAR **)(v19 + 8);
            if ( StringRawBuffer != v21 )
            {
              SysFreeString(v21);
              if ( StringRawBuffer )
              {
                v22 = SysAllocString(StringRawBuffer);
                *(_QWORD *)(v19 + 8) = v22;
                if ( !v22 )
                  ATL::AtlThrowImpl(v23);
              }
              else
              {
                *(_QWORD *)(v19 + 8) = 0;
              }
            }
            *(_QWORD *)(v19 + 32) = 0;
            *(_QWORD *)(v19 + 16) = 0;
            *(_QWORD *)(v19 + 24) = 0;
            *(_BYTE *)v19 = *((_QWORD *)this + 60) != 0;
            v24 = v60;
            v25 = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v60 + 144LL), 0);
            v26 = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v24 + 112LL), 0);
            v27 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0x1275u,
              "UWAInstallWork::_DoDownload",
              -1,
              L"Created task progress for %s with parentbundleId %s",
              (const char *)this + 304,
              v27,
              v26,
              v25);
          }
          WindowsDeleteString(string);
          string = 0;
          v16 = v55 + 1;
          v11 = (_QWORD *)((char *)this + 1168);
        }
        v28 = -1;
        Microsoft::WRL::Wrappers::SRWLock::LockShared(v57, v4);
        v29 = *((_DWORD *)this + 32);
        if ( *((_BYTE *)this + 1128) )
        {
          v31 = 100;
          if ( v29 )
          {
            v30 = 25;
            if ( v29 != 4 )
              v30 = 5;
          }
          else
          {
            v30 = 10;
          }
        }
        else
        {
          v30 = 0;
          if ( v29 )
          {
            v31 = 75;
            if ( v29 != 4 )
              v31 = 95;
          }
          else
          {
            v31 = 90;
          }
        }
        Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v57);
        v51 = -2147023728;
        updated = UWAInstallWork::_DownloadWithOptionalRetry(this, v59, a3, v30, v31, 1, updated, v63, &v51);
        v54 = 0;
        v57[0] = (unsigned __int16 *)&v54;
        v57[1] = 0;
        v58 = 1;
        UWAInstallWork::_AppendContentTypeToClientAppId(this, a3, &v57[1]);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v57);
        if ( updated < 0 )
          updated = UWAInstallWork::_UpdateHrIfNetworkIssueWithNoInternet(this, updated);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
        {
          if ( (unsigned __int8)UWAInstallWork::_ShouldFallbackToHarbor(this, (unsigned int)updated, 2) )
          {
            v32 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
            LogSimpleMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0x12BAu,
              "UWAInstallWork::_DoDownload",
              updated,
              L"Download failed, triggering fallback to direct download",
              (const char *)this + 304,
              v32);
            v33 = (struct UWAInstallWork *)&dword_18023C12C;
            if ( v54 )
              v33 = v54;
            do
              ++v28;
            while ( *((_WORD *)v33 + v28) );
            std::wstring::_Assign<unsigned short>((char *)this + 1008, v33, v28);
            DurationInMilliseconds = UWAInstallWork::StageTimer::GetDurationInMilliseconds((UWAInstallWork::StageTimer *)&ticks);
            *((_BYTE *)this + 985) = 1;
            *((_DWORD *)this + 248) = updated;
            *((_DWORD *)this + 249) = v51;
            *((_DWORD *)this + 247) = 2;
            *((_QWORD *)this + 125) = DurationInMilliseconds;
            goto LABEL_52;
          }
          *((_BYTE *)this + 985) = 0;
        }
        v35 = UWAInstallWork::StageTimer::GetDurationInMilliseconds((UWAInstallWork::StageTimer *)&ticks);
        WindowsUpdate::Telemetry::EndDownload(
          this,
          v54,
          (const unsigned __int16 *)v63,
          (const char *)(unsigned int)updated,
          v51,
          v35,
          (unsigned __int64)v47);
LABEL_52:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
        v36 = v50;
        goto LABEL_54;
      }
      if ( v12 <= 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 151) - v13) >> 3) )
        *((_QWORD *)this + 150) = std::_Uninitialized_value_construct_n<std::allocator<UWAInstallWork::TaskProgressInfo>>(
                                    *((_QWORD *)this + 150),
                                    v12 - v14);
      else
        std::vector<UWAInstallWork::TaskProgressInfo>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 1192);
    }
    else
    {
      v15 = v13 + 40 * v12;
      std::_Destroy_range<std::allocator<UWAInstallWork::TaskProgressInfo>>(v15, *((_QWORD *)this + 150));
      *((_QWORD *)this + 150) = v15;
    }
    v11 = (_QWORD *)((char *)this + 1168);
    goto LABEL_21;
  }
  WindowsUpdate::Telemetry::AbortedInstallation(this, (struct UWAInstallWork *)(unsigned int)updated, (int)v63, v9);
  v36 = (char *)this + 1056;
LABEL_54:
  if ( (*v36 & 1) != 0 )
  {
    ticks = 0;
    *(_OWORD *)v57 = *(_OWORD *)((char *)this + 1308);
    v37 = CoTaskMemAlloc(0x120u);
    if ( !v37 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v38);
    v50 = (char *)tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>(
                    v37,
                    v57);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>::operator=(
      &ticks,
      &v50);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>(&v50);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(ticks + 8) && v39 )
      tip2::details::shared_data<1,0,0>::complete_without_lock(v40);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>(&ticks);
  }
  if ( (int)(updated + 0x80000000) >= 0 && updated != -2147467260 )
  {
    v41 = WindowsGetStringRawBuffer(*((HSTRING *)this + 60), 0);
    v42 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
    v43 = WindowsGetStringRawBuffer(*((HSTRING *)this + 57), 0);
    v44 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
    v45 = WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
    WindowsUpdate::InstallAgentWERReporting::ReportAppAcquireUpdateFailure(
      L"StoreAgentDownloadFailure1",
      v45,
      (const unsigned __int16 *)(unsigned int)updated,
      (unsigned __int64)v44,
      v43,
      v42,
      v41,
      (const unsigned __int16 *)v48);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800f17e0  push    rbx
0x1800f17e2  push    rsi
0x1800f17e3  push    rdi
0x1800f17e4  push    r12
0x1800f17e6  push    r13
0x1800f17e8  push    r14
0x1800f17ea  push    r15
0x1800f17ec  sub     rsp, 180h
0x1800f17f3  mov     rax, cs:__security_cookie
0x1800f17fa  xor     rax, rsp
0x1800f17fd  mov     [rsp+1B8h+var_48], rax
0x1800f1805  mov     al, r8b
0x1800f1808  mov     [rsp+1B8h+var_168], al
0x1800f180c  mov     [rsp+1B8h+var_108], rdx
0x1800f1814  mov     r15, rcx
0x1800f1817  mov     [rsp+1B8h+var_F0], rcx
0x1800f181f  mov     [rsp+1B8h+var_E8], rdx
0x1800f1827  mov     [rsp+1B8h+var_160], al
0x1800f182b  lea     r13, [rcx+418h]
0x1800f1832  mov     [rsp+1B8h+var_128], r13
0x1800f183a  mov     rdx, r13
0x1800f183d  lea     rcx, [rsp+1B8h+var_158]
0x1800f1842  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f1847  mov     eax, [r15+424h]
0x1800f184e  sub     eax, 5
0x1800f1851  xor     esi, esi
0x1800f1853  mov     edi, 80004004h
0x1800f1858  cmp     eax, 1
0x1800f185b  jbe     short loc_1800F1878
0x1800f185d  mov     r12d, esi
0x1800f1860  mov     [rsp+1B8h+var_14C], esi
0x1800f1864  mov     dword ptr [r15+424h], 2
0x1800f186f  mov     [r15+42Ch], esi
0x1800f1876  jmp     short loc_1800F187F
0x1800f1878  mov     r12d, edi
0x1800f187b  mov     [rsp+1B8h+var_14C], edi
0x1800f187f  lea     rcx, [rsp+1B8h+var_158]; this
0x1800f1884  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f1889  test    r12d, r12d
0x1800f188c  js      short loc_1800F18C0
0x1800f188e  xor     edx, edx; bool
0x1800f1890  mov     rcx, r15; this
0x1800f1893  call    ?_RaiseProgressEvent@UWAInstallWork@@AEAAX_N@Z; UWAInstallWork::_RaiseProgressEvent(bool)
0x1800f1898  mov     rdx, r13
0x1800f189b  lea     rcx, [rsp+1B8h+var_158]
0x1800f18a0  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800f18a5  cmp     dword ptr [r15+424h], 2
0x1800f18ad  cmovnz  r12d, edi
0x1800f18b1  mov     [rsp+1B8h+var_14C], r12d
0x1800f18b6  lea     rcx, [rsp+1B8h+var_158]; this
0x1800f18bb  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800f18c0  mov     rdx, r13
0x1800f18c3  lea     rcx, [rsp+1B8h+var_158]
0x1800f18c8  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f18cd  nop
0x1800f18ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f18d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(void)
0x1800f18da  mov     rcx, [r15+128h]; this
0x1800f18e1  test    al, al
0x1800f18e3  jz      short loc_1800F1962
0x1800f18e5  lea     rbx, [r15+130h]
0x1800f18ec  mov     rdx, rbx; char *
0x1800f18ef  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800f18f4  movups  xmm0, xmmword ptr [rbx]
0x1800f18f7  movups  xmmword ptr [rsp+1B8h+var_D8], xmm0
0x1800f18ff  movups  xmm1, xmmword ptr [rbx+10h]
0x1800f1903  movups  [rsp+1B8h+var_C8], xmm1
0x1800f190b  movups  xmm0, xmmword ptr [rbx+20h]
0x1800f190f  movups  [rsp+1B8h+var_B8], xmm0
0x1800f1917  movups  xmm1, xmmword ptr [rbx+30h]
0x1800f191b  movups  [rsp+1B8h+var_A8], xmm1
0x1800f1923  movups  xmm0, xmmword ptr [rbx+40h]
0x1800f1927  movups  [rsp+1B8h+var_98], xmm0
0x1800f192f  movups  xmm1, xmmword ptr [rbx+50h]
0x1800f1933  movups  [rsp+1B8h+var_88], xmm1
0x1800f193b  movups  xmm0, xmmword ptr [rbx+60h]
0x1800f193f  movups  [rsp+1B8h+var_78], xmm0
0x1800f1947  movups  xmm1, xmmword ptr [rbx+70h]
0x1800f194b  movups  [rsp+1B8h+var_68], xmm1
0x1800f1953  mov     al, [rbx+80h]
0x1800f1959  mov     [rsp+1B8h+var_58], al
0x1800f1960  jmp     short loc_1800F1970
0x1800f1962  lea     rdx, [rsp+1B8h+var_D8]; char *
0x1800f196a  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800f196f  nop
0x1800f1970  lea     rcx, [rsp+1B8h+var_158]; this
0x1800f1975  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f197a  mov     rcx, r15; this
0x1800f197d  test    r12d, r12d
0x1800f1980  js      loc_1800F1E91
0x1800f1986  lea     rdx, [rsp+1B8h+var_D8]; struct UWAInstallWork *
0x1800f198e  call    ?BeginDownload@Telemetry@WindowsUpdate@@YAXPEAVUWAInstallWork@@PEBD@Z; WindowsUpdate::Telemetry::BeginDownload(UWAInstallWork *,char const *)
0x1800f1993  call    cs:__imp__Xtime_get_ticks
0x1800f1999  mov     [rsp+1B8h+var_148], rax
0x1800f199e  lea     rbx, [r15+420h]
0x1800f19a5  mov     [rsp+1B8h+var_158], rbx
0x1800f19aa  test    byte ptr [rbx], 1
0x1800f19ad  jz      short loc_1800F1A0E
0x1800f19af  lea     rcx, [rsp+1B8h+var_100]
0x1800f19b7  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800f19bc  mov     rcx, [rax]
0x1800f19bf  mov     [r15+510h], rcx
0x1800f19c6  mov     [rsp+1B8h+var_138], rsi
0x1800f19ce  lea     rcx, [rsp+1B8h+var_138]
0x1800f19d6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DownloadStuckTipTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DownloadStuckTipTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>>::ensure_data(void)
0x1800f19db  mov     rcx, [rax]
0x1800f19de  add     rcx, 8
0x1800f19e2  lea     rdx, [rsp+1B8h+var_100]
0x1800f19ea  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800f19ef  movups  xmm0, [rsp+1B8h+var_100]
0x1800f19f7  movdqu  xmmword ptr [r15+51Ch], xmm0
0x1800f1a00  lea     rcx, [rsp+1B8h+var_138]
0x1800f1a08  call    ??1?$com_ptr_t@V?$merged_data@U_tip_DownloadStuckTipTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_DownloadStuckTipTest,TipTests::_tip_DownloadStuckTipTest>,wil::err_returncode_policy>(void)
0x1800f1a0d  nop
0x1800f1a0e  lea     r14, [r15+4A8h]
0x1800f1a15  lea     r9, [r15+490h]
0x1800f1a1c  mov     rdx, [r9+8]
0x1800f1a20  sub     rdx, [r9]
0x1800f1a23  sar     rdx, 3
0x1800f1a27  mov     r8, [r14]
0x1800f1a2a  mov     rcx, [r14+8]
0x1800f1a2e  sub     rcx, r8
0x1800f1a31  sar     rcx, 3
0x1800f1a35  mov     r10, 0CCCCCCCCCCCCCCCDh
0x1800f1a3f  imul    rcx, r10
0x1800f1a43  cmp     rdx, rcx
0x1800f1a46  jnb     short loc_1800F1A62
0x1800f1a48  lea     rax, [rdx+rdx*4]
0x1800f1a4c  lea     rbx, [r8+rax*8]
0x1800f1a50  mov     rdx, [r14+8]
0x1800f1a54  mov     rcx, rbx
0x1800f1a57  call    ??$_Destroy_range@V?$allocator@UTaskProgressInfo@UWAInstallWork@@@std@@@std@@YAXPEAUTaskProgressInfo@UWAInstallWork@@QEAU12@AEAV?$allocator@UTaskProgressInfo@UWAInstallWork@@@0@@Z; std::_Destroy_range<std::allocator<UWAInstallWork::TaskProgressInfo>>(UWAInstallWork::TaskProgressInfo *,UWAInstallWork::TaskProgressInfo * const,std::allocator<UWAInstallWork::TaskProgressInfo> &)
0x1800f1a5c  mov     [r14+8], rbx
0x1800f1a60  jmp     short loc_1800F1A92
0x1800f1a62  jbe     short loc_1800F1A99
0x1800f1a64  mov     rax, [r14+10h]
0x1800f1a68  sub     rax, r8
0x1800f1a6b  sar     rax, 3
0x1800f1a6f  imul    rax, r10
0x1800f1a73  cmp     rdx, rax
0x1800f1a76  jbe     short loc_1800F1A82
0x1800f1a78  mov     rcx, r14
0x1800f1a7b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UTaskProgressInfo@UWAInstallWork@@V?$allocator@UTaskProgressInfo@UWAInstallWork@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<UWAInstallWork::TaskProgressInfo>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800f1a80  jmp     short loc_1800F1A92
0x1800f1a82  sub     rdx, rcx
0x1800f1a85  mov     rcx, [r14+8]
0x1800f1a89  call    ??$_Uninitialized_value_construct_n@V?$allocator@UTaskProgressInfo@UWAInstallWork@@@std@@@std@@YAPEAUTaskProgressInfo@UWAInstallWork@@PEAU12@_KAEAV?$allocator@UTaskProgressInfo@UWAInstallWork@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<UWAInstallWork::TaskProgressInfo>>(UWAInstallWork::TaskProgressInfo *,unsigned __int64,std::allocator<UWAInstallWork::TaskProgressInfo> &)
0x1800f1a8e  mov     [r14+8], rax
0x1800f1a92  lea     r9, [r15+490h]
0x1800f1a99  mov     rcx, rsi
0x1800f1a9c  mov     [rsp+1B8h+var_138], rcx
0x1800f1aa4  mov     rax, [r15+498h]
0x1800f1aab  sub     rax, [r9]
0x1800f1aae  sar     rax, 3
0x1800f1ab2  cmp     rcx, rax
0x1800f1ab5  jnb     loc_1800F1C32
0x1800f1abb  mov     rdx, rcx
0x1800f1abe  mov     rcx, r9
0x1800f1ac1  call    ?at@?$vector@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::at(unsigned __int64)
0x1800f1ac6  mov     qword ptr [rsp+1B8h+var_100], rax
0x1800f1ace  mov     [rsp+1B8h+string], rsi
0x1800f1ad6  mov     rdi, [rax]
0x1800f1ad9  mov     rax, [rdi]
0x1800f1adc  mov     rbx, [rax+58h]
0x1800f1ae0  xor     ecx, ecx; string
0x1800f1ae2  call    cs:__imp_WindowsDeleteString
0x1800f1ae8  mov     [rsp+1B8h+string], rsi
0x1800f1af0  lea     rdx, [rsp+1B8h+string]
0x1800f1af8  mov     rcx, rdi
0x1800f1afb  mov     rax, rbx
0x1800f1afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1b03  test    eax, eax
0x1800f1b05  js      loc_1800F1C05
0x1800f1b0b  mov     rdx, [rsp+1B8h+var_138]
0x1800f1b13  mov     rcx, r14
0x1800f1b16  call    ?at@?$vector@UTaskProgressInfo@UWAInstallWork@@V?$allocator@UTaskProgressInfo@UWAInstallWork@@@std@@@std@@QEAAAEAUTaskProgressInfo@UWAInstallWork@@_K@Z; std::vector<UWAInstallWork::TaskProgressInfo>::at(unsigned __int64)
0x1800f1b1b  mov     rbx, rax
0x1800f1b1e  xor     edx, edx; length
0x1800f1b20  mov     rcx, [rsp+1B8h+string]; string
0x1800f1b28  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1b2e  mov     rdi, rax
0x1800f1b31  mov     rcx, [rbx+8]; bstrString
0x1800f1b35  cmp     rax, rcx
0x1800f1b38  jz      short loc_1800F1B61
0x1800f1b3a  call    cs:__imp_SysFreeString
0x1800f1b40  test    rdi, rdi
0x1800f1b43  jz      short loc_1800F1B5D
0x1800f1b45  mov     rcx, rdi; psz
0x1800f1b48  call    cs:__imp_SysAllocString
0x1800f1b4e  mov     [rbx+8], rax
0x1800f1b52  test    rax, rax
0x1800f1b55  jz      loc_1800F1FDC
0x1800f1b5b  jmp     short loc_1800F1B61
0x1800f1b5d  mov     [rbx+8], rsi
0x1800f1b61  mov     [rbx+20h], rsi
0x1800f1b65  mov     [rbx+10h], rsi
0x1800f1b69  mov     [rbx+18h], rsi
0x1800f1b6d  cmp     [r15+1E0h], rsi
0x1800f1b74  setnz   al
0x1800f1b77  mov     [rbx], al
0x1800f1b79  mov     rbx, qword ptr [rsp+1B8h+var_100]
0x1800f1b81  mov     rcx, [rbx]
0x1800f1b84  xor     edx, edx; length
0x1800f1b86  mov     rcx, [rcx+90h]; string
0x1800f1b8d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1b93  mov     rdi, rax
0x1800f1b96  mov     rcx, [rbx]
0x1800f1b99  xor     edx, edx; length
0x1800f1b9b  mov     rcx, [rcx+70h]; string
0x1800f1b9f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1ba5  mov     rbx, rax
0x1800f1ba8  xor     edx, edx; length
0x1800f1baa  mov     rcx, [r15+1D8h]; string
0x1800f1bb1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1bb7  lea     rcx, [r15+130h]
0x1800f1bbe  mov     [rsp+1B8h+var_170], rdi
0x1800f1bc3  mov     [rsp+1B8h+var_178], rbx
0x1800f1bc8  mov     [rsp+1B8h+var_180], rax; unsigned __int16 *
0x1800f1bcd  mov     [rsp+1B8h+var_188], rcx; char *
0x1800f1bd2  lea     rax, aCreatedTaskPro; "Created task progress for %s with paren"...
0x1800f1bd9  mov     [rsp+1B8h+var_190], rax; unsigned __int16 *
0x1800f1bde  mov     dword ptr [rsp+1B8h+var_198], 0FFFFFFFFh; int
0x1800f1be6  lea     r9, aUwainstallwork_5; "UWAInstallWork::_DoDownload"
0x1800f1bed  mov     r8d, 1275h; unsigned int
0x1800f1bf3  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f1bfa  mov     ecx, 3; unsigned int
0x1800f1bff  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f1c04  nop
0x1800f1c05  mov     rcx, [rsp+1B8h+string]; string
0x1800f1c0d  call    cs:__imp_WindowsDeleteString
0x1800f1c13  mov     [rsp+1B8h+string], rsi
0x1800f1c1b  mov     rcx, [rsp+1B8h+var_138]
0x1800f1c23  inc     rcx
0x1800f1c26  lea     r9, [r15+490h]
0x1800f1c2d  jmp     loc_1800F1A9C
0x1800f1c32  jmp     short loc_1800F1C63
0x1800f1c34  xor     esi, esi
0x1800f1c36  mov     r12d, [rsp+1B8h+var_14C]
0x1800f1c3b  mov     r15, [rsp+1B8h+var_F0]
0x1800f1c43  mov     rax, [rsp+1B8h+var_E8]
0x1800f1c4b  mov     [rsp+1B8h+var_108], rax
0x1800f1c53  mov     al, [rsp+1B8h+var_160]
0x1800f1c57  mov     [rsp+1B8h+var_168], al
0x1800f1c5b  mov     r13, [rsp+1B8h+var_128]
0x1800f1c63  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800f1c67  mov     rdx, r13
0x1800f1c6a  lea     rcx, [rsp+1B8h+var_128]
0x1800f1c72  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800f1c77  mov     eax, [r15+80h]
0x1800f1c7e  cmp     [r15+468h], sil
0x1800f1c85  jnz     short loc_1800F1CA3
0x1800f1c87  mov     edi, esi
0x1800f1c89  test    eax, eax
0x1800f1c8b  jz      short loc_1800F1C9C
0x1800f1c8d  lea     ebx, [r14+4Ch]
0x1800f1c91  lea     ecx, [rbx+14h]
0x1800f1c94  cmp     eax, 4
0x1800f1c97  cmovnz  ebx, ecx
0x1800f1c9a  jmp     short loc_1800F1CBF
0x1800f1c9c  mov     ebx, 5Ah ; 'Z'
0x1800f1ca1  jmp     short loc_1800F1CBF
0x1800f1ca3  mov     ebx, 64h ; 'd'
0x1800f1ca8  test    eax, eax
0x1800f1caa  jz      short loc_1800F1CBA
0x1800f1cac  lea     edi, [rbx-4Bh]
0x1800f1caf  cmp     eax, 4
0x1800f1cb2  lea     eax, [rbx-5Fh]
0x1800f1cb5  cmovnz  edi, eax
0x1800f1cb8  jmp     short loc_1800F1CBF
0x1800f1cba  mov     edi, 0Ah
0x1800f1cbf  lea     rcx, [rsp+1B8h+var_128]; this
0x1800f1cc7  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800f1ccc  mov     [rsp+1B8h+var_150], 80070490h
0x1800f1cd4  lea     rax, [rsp+1B8h+var_150]
0x1800f1cd9  mov     [rsp+1B8h+var_178], rax; int *
0x1800f1cde  lea     rax, [rsp+1B8h+var_D8]
0x1800f1ce6  mov     [rsp+1B8h+var_180], rax; char *
0x1800f1ceb  mov     dword ptr [rsp+1B8h+var_188], r12d; unsigned __int64
0x1800f1cf0  mov     byte ptr [rsp+1B8h+var_190], 1; bool
0x1800f1cf5  mov     dword ptr [rsp+1B8h+var_198], ebx; unsigned int
0x1800f1cf9  mov     r9d, edi; unsigned int
0x1800f1cfc  mov     r8b, [rsp+1B8h+var_168]; bool
0x1800f1d01  mov     rdx, [rsp+1B8h+var_108]; struct IUpdateSession *
0x1800f1d09  mov     rcx, r15; this
0x1800f1d0c  call    ?_DownloadWithOptionalRetry@UWAInstallWork@@AEAAJPEAUIUpdateSession@@_NII1JPEBDPEAJ@Z; UWAInstallWork::_DownloadWithOptionalRetry(IUpdateSession *,bool,uint,uint,bool,long,char const *,long *)
0x1800f1d11  mov     r12d, eax
0x1800f1d14  mov     [rsp+1B8h+var_140], rsi
0x1800f1d19  lea     rax, [rsp+1B8h+var_140]
0x1800f1d1e  mov     [rsp+1B8h+var_128], rax
0x1800f1d26  mov     [rsp+1B8h+var_128+8], rsi
0x1800f1d2e  mov     [rsp+1B8h+var_118], 1
0x1800f1d36  lea     r8, [rsp+1B8h+var_128+8]; unsigned __int16 **
0x1800f1d3e  mov     dl, [rsp+1B8h+var_168]; bool
0x1800f1d42  mov     rcx, r15; this
0x1800f1d45  call    ?_AppendContentTypeToClientAppId@UWAInstallWork@@AEAAX_NPEAPEAG@Z; UWAInstallWork::_AppendContentTypeToClientAppId(bool,ushort * *)
0x1800f1d4a  lea     rcx, [rsp+1B8h+var_128]
0x1800f1d52  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800f1d57  test    r12d, r12d
0x1800f1d5a  jns     short loc_1800F1D6A
0x1800f1d5c  mov     edx, r12d; int
  ... truncated ...
```
