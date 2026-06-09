# PeriodicUpdateManager::PostNotification(ushort const *,ushort const *,ushort const *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,_GUID const *)

- ea: `0x18005f240`
- end: `0x18005fd81`
- name: `?PostNotification@PeriodicUpdateManager@@UEAAJPEBG00W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@PEBU_GUID@@@Z`
- size: `2881`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180011e6c`
- `0x180013360`
- `0x180019418`
- `0x180024890`
- `0x18002b838`
- `0x18002c22c`
- `0x18002ce5c`
- `0x18002cf14`
- `0x18002df60`
- `0x18002ee38`
- `0x180030524`
- `0x180057b14`
- `0x18005e620`
- `0x18005f240`
- `0x18005fd88`
- `0x180097fa0`
- `0x1800a0b2c`
- `0x1800a1308`
- `0x1800b99f0`
- `0x1800d7d60`
- `0x1800d92a8`
- `0x1800f5dd8`
- `0x1800f5ee0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f612`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f612`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f601`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005faaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f601`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005faaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fabd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fabd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f94e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f94e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005f934`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005f934`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005f961`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005f961`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeW` at `0x18005f91d`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeW` at `0x18005f91d`

## string_xrefs

- `0x18005f3b0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f413`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f44f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f488`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f50a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f55a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f5a9`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f633`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f7b9`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f805`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f86b`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f8a8`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f8e0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f97e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f9b7`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall PeriodicUpdateManager::PostNotification(
        PeriodicUpdateManager *a1,
        unsigned __int16 *a2,
        struct _FILETIME a3,
        struct _FILETIME a4,
        unsigned int a5,
        const int *a6)
{
  unsigned int v8; // r13d
  unsigned int v9; // r15d
  const int *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  const int *v13; // rax
  _QWORD *v14; // r12
  __int64 (__fastcall *v15)(_QWORD *, unsigned __int16 *, struct INotificationHandler **); // rbx
  int v16; // eax
  PeriodicUpdateManager *v17; // rdi
  CtaManager **v18; // rbx
  const unsigned __int16 *v19; // rax
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rcx
  const char *v23; // r9
  char *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(__int64, _QWORD, GUID *, __int64 *); // rdi
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rdi
  int v31; // eax
  int v32; // esi
  HANDLE ProcessHeap; // rax
  __int64 v34; // rax
  const unsigned __int16 *v35; // r8
  DWORD v36; // r9d
  unsigned __int16 *v37; // rsi
  int v38; // edx
  int v39; // edi
  __int64 v40; // r10
  int v41; // eax
  __int128 *v42; // rax
  int v43; // eax
  int v44; // eax
  DWORD dwHighDateTime; // edi
  DWORD dwLowDateTime; // esi
  void *v47; // rdx
  wil::details *v48; // rcx
  void *v49; // rdi
  HANDLE v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rcx
  struct INotificationHandler *v53; // rcx
  unsigned __int16 *v54; // rax
  __int64 *v55; // rdx
  __int128 *v56; // rax
  __int128 *v57; // rax
  __int128 *v58; // rax
  __int64 result; // rax
  int v60; // r15d
  int v61; // esi
  DWORD v62; // ebx
  __int16 v63; // di
  LPCWSTR v64; // r14
  void *v65; // rax
  int v66; // [rsp+20h] [rbp-1C8h]
  int v67; // [rsp+20h] [rbp-1C8h]
  int v68; // [rsp+20h] [rbp-1C8h]
  struct _FILETIME FileTime; // [rsp+70h] [rbp-178h] BYREF
  DWORD v70; // [rsp+80h] [rbp-168h] BYREF
  __int16 v71; // [rsp+84h] [rbp-164h]
  unsigned __int16 *v72; // [rsp+88h] [rbp-160h]
  unsigned int v73[4]; // [rsp+90h] [rbp-158h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-148h] BYREF
  DWORD v75; // [rsp+A8h] [rbp-140h]
  __int64 v76; // [rsp+B0h] [rbp-138h] BYREF
  LPVOID lpMem; // [rsp+B8h] [rbp-130h] BYREF
  unsigned int v78; // [rsp+C0h] [rbp-128h] BYREF
  int v79; // [rsp+C4h] [rbp-124h] BYREF
  __int64 v80; // [rsp+C8h] [rbp-120h] BYREF
  struct INotificationHandler *v81; // [rsp+D0h] [rbp-118h] BYREF
  unsigned __int16 *v82; // [rsp+D8h] [rbp-110h] BYREF
  unsigned __int16 *v83; // [rsp+E0h] [rbp-108h] BYREF
  PeriodicUpdateManager *v84; // [rsp+E8h] [rbp-100h]
  __int64 v85; // [rsp+F0h] [rbp-F8h] BYREF
  LPCWSTR lpszTime; // [rsp+F8h] [rbp-F0h] BYREF
  wil::details *v87; // [rsp+100h] [rbp-E8h] BYREF
  unsigned __int16 *v88; // [rsp+108h] [rbp-E0h]
  const int *v89; // [rsp+110h] [rbp-D8h]
  const int *v90; // [rsp+118h] [rbp-D0h]
  __int64 v91; // [rsp+120h] [rbp-C8h]
  _QWORD v92[3]; // [rsp+128h] [rbp-C0h] BYREF
  char v93; // [rsp+140h] [rbp-A8h]
  _QWORD *v94; // [rsp+148h] [rbp-A0h]
  char v95; // [rsp+150h] [rbp-98h] BYREF
  LPVOID *p_lpMem; // [rsp+158h] [rbp-90h]
  char v97; // [rsp+160h] [rbp-88h]
  __int128 v98; // [rsp+168h] [rbp-80h] BYREF
  __int128 v99; // [rsp+178h] [rbp-70h]
  SYSTEMTIME pst; // [rsp+188h] [rbp-60h] BYREF
  unsigned __int64 v101; // [rsp+1A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  SystemTimeAsFileTime = a4;
  FileTime = a3;
  v88 = a2;
  v84 = a1;
  v89 = a6;
  v72 = a2;
  v8 = a5;
  v90 = a6;
  v9 = 0;
  lpszTime = 0;
  v98 = 0;
  v99 = 0;
  std::wstring::_Construct_empty(&v98, a6);
  try
  {
    v79 = 0;
    v70 = 0;
    v71 = 0;
    if ( !*((_QWORD *)a1 + 4) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
      v10 = v89;
    }
    if ( (byte_18015DE45 & 1) != 0 )
    {
      v13 = v10;
      if ( !v10 )
        v13 = &qword_18012F1D0;
      McTemplateU0zqj_EventWriteTransfer((unsigned int)&qword_18012F1D0, (_DWORD)v10, (_DWORD)a2, a5, (__int64)v13);
    }
    v14 = *(_QWORD **)(*((_QWORD *)a1 + 4) + 144LL);
    v94 = v14;
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *, const int *))(*v14 + 8LL))(v14, v10);
    v81 = 0;
    v15 = *(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *, struct INotificationHandler **))(v14[4] + 192LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v16 = v15(v14 + 4, a2, &v81);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v16,
        v66);
    v17 = v84;
    v18 = (CtaManager **)*((_QWORD *)v84 + 4);
    v19 = (const unsigned __int16 *)WpnDatabaseHelpers::NotificationTypeNameFromValue(a5);
    v20 = NotificationPlatform::CheckNotificationHandlerSettingsEnabled(
            v18,
            v81,
            *(WpnDatabaseHelpers **)&FileTime,
            v19,
            1,
            (enum NOTIFICATION_POLICY_REASON *)&v79,
            0);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2EE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v20,
        v67);
    v22 = *(_QWORD *)(*((_QWORD *)v17 + 4) + 240LL);
    v23 = v22 == 0 ? (const char *)0x803E0105LL : 0LL;
    if ( !v22 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        v23,
        v67);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, const char *))(*(_QWORD *)v22 + 40LL))(
            v22,
            0,
            v21,
            v23) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x80004005LL,
        v67);
    v80 = 0;
    v85 = 0;
    v24 = (char *)Microsoft::WRL::Details::Make<PlatformFactory,>(&v76);
    v25 = 0;
    if ( &v95 != v24 )
    {
      v25 = *(_QWORD *)v24;
      *(_QWORD *)v24 = 0;
    }
    v91 = v25;
    v26 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    if ( !v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2FE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x80004003LL,
        v67);
    v27 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v25 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
    v28 = v27(v25, 0, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, &v80);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2FF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v28,
        v67);
    v29 = v80;
    v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v80 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    v31 = v30(v29, &v85);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x300,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v31,
        v67);
    LODWORD(v76) = (a5 == 2) + 1;
    v32 = 256;
    if ( a5 != 2 )
      v32 = 5120;
    lpMem = 0;
    p_lpMem = &lpMem;
    v97 = 1;
    ProcessHeap = GetProcessHeap();
    lpMem = HeapAlloc(ProcessHeap, 8u, (unsigned int)(v32 + 1));
    if ( !lpMem )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x312,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x8007000ELL,
        v67);
    v73[0] = 0;
    v78 = 0;
    v83 = 0;
    v82 = 0;
    v92[0] = &v83;
    v92[1] = &v82;
    v92[2] = &lpszTime;
    v93 = 1;
    v34 = PeriodicUpdateManager::ReplaceLanguageAndRegionTokensInUri(&pst);
    std::wstring::operator=(&v98, v34);
    if ( v101 > 7 )
      std::_Deallocate<16>(*(void **)&pst.wYear, 2 * v101 + 2);
    v35 = (const unsigned __int16 *)&v98;
    if ( *((_QWORD *)&v99 + 1) > 7u )
      v35 = (const unsigned __int16 *)v98;
    v36 = v32;
    v37 = v88;
    v39 = PeriodicUpdateManager::RetrieveNotification(
            v84,
            (CtaHelpers *)v88,
            v35,
            v36,
            (char *)lpMem,
            v73,
            &v78,
            (struct CtaHelpers::CtaPolicy *)&v70,
            &v83,
            &v82,
            (unsigned __int16 **)&lpszTime);
    if ( v73[0] )
    {
      v40 = *(_QWORD *)(*((_QWORD *)v84 + 4) + 120LL);
      if ( !v40 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x330,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          *(_QWORD *)(*((_QWORD *)v84 + 4) + 120LL) == 0 ? (const char *)0x803E0105LL : 0,
          v68);
      v68 = 0;
      v41 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v40 + 64LL))(
              v40,
              v37,
              0,
              1);
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x336,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)(unsigned int)v41,
          0);
    }
    if ( v78 != 200 && (byte_18015DE46 & 1) != 0 )
    {
      v42 = &v98;
      if ( *((_QWORD *)&v99 + 1) > 7u )
        v42 = (__int128 *)v98;
      McTemplateU0zqzq_EventWriteTransfer(v78, v38, (_DWORD)v37, a5, (__int64)v42, v78);
    }
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v39,
        v68);
    if ( ((a5 - 1) & 0xFFFFFFFD) == 0 )
    {
      if ( v83 )
      {
        v43 = WpnValidateTag(v83);
        if ( v43 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x348,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
            (const char *)(unsigned int)v43,
            v68);
      }
      if ( a5 == 3 )
      {
        if ( v82 )
        {
          v44 = WpnValidateGroup(v82);
          if ( v44 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x34E,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
              (const char *)(unsigned int)v44,
              v68);
        }
      }
    }
    if ( lpszTime )
    {
      pst = 0;
      FileTime = 0;
      if ( !InternetTimeToSystemTimeW(lpszTime, &pst, 0) || !SystemTimeToFileTime(&pst, &FileTime) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)0x80004005LL,
          v68);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&FileTime, &SystemTimeAsFileTime) <= 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x365,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)0x80004005LL,
          v68);
      dwHighDateTime = FileTime.dwHighDateTime;
      dwLowDateTime = FileTime.dwLowDateTime;
      SystemTimeAsFileTime.dwLowDateTime = 1;
    }
    else
    {
      dwHighDateTime = 0;
      SystemTimeAsFileTime.dwLowDateTime = 0;
      dwLowDateTime = 0;
    }
    ConvertUtf8ToUtf16(&v87, lpMem);
    FileTime.dwLowDateTime = 0;
    SystemTimeAsFileTime.dwHighDateTime = dwLowDateTime;
    v75 = dwHighDateTime;
    PeriodicUpdateManager::PostNotificationInternal(
      v84,
      v88,
      (unsigned int)v76,
      v87,
      v83,
      v82,
      &SystemTimeAsFileTime,
      v89,
      &FileTime);
    v48 = v87;
    v87 = 0;
    if ( v48 )
      wil::details::FreeProcessHeap(v48, v47);
    v93 = 0;
    lambda_847135ce1ed02ebe366c05a84a7793cb_::operator()(v92);
    v49 = lpMem;
    if ( lpMem )
    {
      v50 = GetProcessHeap();
      HeapFree(v50, 0, v49);
      lpMem = 0;
    }
    v51 = v85;
    if ( v85 )
    {
      v85 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v53 = v81;
    if ( v81 )
    {
      v81 = 0;
      (*(void (__fastcall **)(struct INotificationHandler *))(*(_QWORD *)v53 + 16LL))(v53);
    }
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    v54 = v88;
  }
  catch ( ... )
  {
    v60 = wil::ResultFromCaughtException(v53);
    LODWORD(v76) = v60;
    v61 = v79;
    v62 = v70;
    v63 = v71;
    v64 = lpszTime;
    v65 = (void *)std::wstring::wstring(v92, &v98);
    FileTime.dwLowDateTime = v62;
    LOWORD(FileTime.dwHighDateTime) = v63;
    PeriodicUpdateManager::LogPostNotificationForPeriodicTrigger(
      (int)v65,
      v60,
      (int)v72,
      (int)v90,
      v65,
      (__int64)v64,
      a5,
      0,
      (__int64)&FileTime,
      v61);
    v9 = v76;
    if ( (int)v76 >= 0 )
    {
      v54 = v72;
      v8 = a5;
      goto LABEL_79;
    }
    if ( (_DWORD)v76 == -2143420139 )
    {
      if ( (byte_18015DE45 & 0x40) == 0 )
        goto LABEL_105;
      v55 = WPNEND_PERIODIC_UPDATE_POLL_STOP_SIZE;
LABEL_102:
      v58 = &v98;
      if ( *((_QWORD *)&v99 + 1) > 7u )
        v58 = (__int128 *)v98;
      McTemplateU0zqz_EventWriteTransfer((_DWORD)v53, (_DWORD)v55, (_DWORD)v72, a5, (__int64)v58);
      goto LABEL_105;
    }
    if ( (_DWORD)v76 == -2143420138 || (_DWORD)v76 == -2143420118 )
    {
      if ( (byte_18015DE45 & 0x40) == 0 )
        goto LABEL_105;
      v55 = WPNEND_PERIODIC_UPDATE_POLL_STOP_INVALID_TAG;
      goto LABEL_102;
    }
    if ( (unsigned int)(v76 + 2143419895) <= 1 )
    {
      if ( (byte_18015DE46 & 2) == 0 )
        goto LABEL_105;
      v55 = WPNEND_PERIODIC_UPDATE_POLL_STOP_INVALID_GROUP;
      goto LABEL_102;
    }
    if ( (_DWORD)v76 == -2143420143 || (_DWORD)v76 == -2143420140 )
    {
      if ( (byte_18015DE46 & 1) != 0 )
      {
        v57 = &v98;
        if ( *((_QWORD *)&v99 + 1) > 7u )
          v57 = (__int128 *)v98;
        McTemplateU0zqzd_EventWriteTransfer(
          (_DWORD)v53,
          (unsigned int)WPNEND_PERIODIC_UPDATE_POLL_STOP_SETTING_DISABLED,
          (_DWORD)v72,
          a5,
          (__int64)v57,
          v76);
      }
      v9 = 0;
    }
    else if ( (byte_18015DE45 & 0x40) != 0 )
    {
      v56 = &v98;
      if ( *((_QWORD *)&v99 + 1) > 7u )
        v56 = (__int128 *)v98;
      McTemplateU0zqzd_EventWriteTransfer(
        (_DWORD)v53,
        (unsigned int)WPNEND_PERIODIC_UPDATE_POLL_STOP_ERROR,
        (_DWORD)v72,
        a5,
        (__int64)v56,
        v76);
    }
LABEL_105:
    if ( *((_QWORD *)&v99 + 1) > 7u )
      std::_Deallocate<16>((void *)v98, 2LL * *((_QWORD *)&v99 + 1) + 2);
    result = v9;
  }
LABEL_79:
  if ( (byte_18015DE45 & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v53, WPNEND_PERIODIC_UPDATE_POLL_STOP, v54, v8);
  goto LABEL_105;
}

```

## disassembly

```asm
0x18005f240  mov     r11, rsp
0x18005f243  push    rbx
0x18005f244  push    rsi
0x18005f245  push    rdi
0x18005f246  push    r12
0x18005f248  push    r13
0x18005f24a  push    r14
0x18005f24c  push    r15
0x18005f24e  sub     rsp, 1B0h
0x18005f255  mov     rax, cs:__security_cookie
0x18005f25c  xor     rax, rsp
0x18005f25f  mov     [rsp+1E8h+var_40], rax
0x18005f267  mov     qword ptr [rsp+1E8h+SystemTimeAsFileTime.dwLowDateTime], r9
0x18005f26f  mov     qword ptr [rsp+1E8h+FileTime.dwLowDateTime], r8
0x18005f274  mov     rsi, rdx
0x18005f277  mov     [rsp+1E8h+var_E0], rdx
0x18005f27f  mov     rbx, rcx
0x18005f282  mov     [rsp+1E8h+var_100], rcx
0x18005f28a  mov     rdx, [rsp+1E8h+arg_28]
0x18005f292  mov     [rsp+1E8h+var_D8], rdx
0x18005f29a  mov     [rsp+1E8h+var_160], rsi
0x18005f2a2  mov     r13d, [rsp+1E8h+arg_20]
0x18005f2aa  mov     [rsp+1E8h+var_180], r13d
0x18005f2af  mov     [rsp+1E8h+var_D0], rdx
0x18005f2b7  xor     r14d, r14d
0x18005f2ba  mov     r15d, r14d
0x18005f2bd  mov     [rsp+1E8h+var_188], r14b
0x18005f2c2  mov     [rsp+1E8h+var_187], r14b
0x18005f2c7  mov     [r11-0F0h], r14
0x18005f2ce  xorps   xmm0, xmm0
0x18005f2d1  movups  xmmword ptr [r11-80h], xmm0
0x18005f2d6  xorps   xmm1, xmm1
0x18005f2d9  movdqu  xmmword ptr [r11-70h], xmm1
0x18005f2df  lea     rcx, [r11-80h]
0x18005f2e3  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18005f2e8  nop
0x18005f2e9  mov     [rsp+1E8h+var_124], r14d
0x18005f2f1  mov     [rsp+1E8h+var_168], r14d
0x18005f2f9  mov     [rsp+1E8h+var_164], r14w
0x18005f302  cmp     [rbx+20h], r14
0x18005f306  jnz     short loc_18005F315
0x18005f308  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_Platform != nullptr")
0x18005f30d  mov     rdx, [rsp+1E8h+var_D8]
0x18005f315  test    cs:byte_18015DE45, 1
0x18005f31c  jz      short loc_18005F33F
0x18005f31e  lea     rcx, qword_18012F1D0
0x18005f325  mov     rax, rdx
0x18005f328  test    rdx, rdx
0x18005f32b  cmovz   rax, rcx
0x18005f32f  mov     [rsp+1E8h+var_1C8], rax; int
0x18005f334  mov     r9d, r13d
0x18005f337  mov     r8, rsi
0x18005f33a  call    McTemplateU0zqj_EventWriteTransfer
0x18005f33f  mov     rax, [rbx+20h]
0x18005f343  mov     r12, [rax+90h]
0x18005f34a  mov     [rsp+1E8h+var_A0], r12
0x18005f352  test    r12, r12
0x18005f355  jz      short loc_18005F368
0x18005f357  mov     rax, [r12]
0x18005f35b  mov     rcx, r12
0x18005f35e  mov     rax, [rax+8]
0x18005f362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f367  nop
0x18005f368  mov     [rsp+1E8h+var_118], r14
0x18005f370  mov     rax, [r12+20h]
0x18005f375  mov     rbx, [rax+0C0h]
0x18005f37c  lea     rcx, [rsp+1E8h+var_118]
0x18005f384  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f389  lea     r8, [rsp+1E8h+var_118]
0x18005f391  mov     rdx, rsi
0x18005f394  lea     rcx, [r12+20h]
0x18005f399  mov     rax, rbx
0x18005f39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3a1  mov     rcx, [rsp+1E8h]; this
0x18005f3a9  test    eax, eax
0x18005f3ab  jns     short loc_18005F3C1
0x18005f3ad  mov     r9d, eax; char *
0x18005f3b0  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f3b7  mov     edx, 2E5h; void *
0x18005f3bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f3c1  mov     rdi, [rsp+1E8h+var_100]
0x18005f3c9  mov     rbx, [rdi+20h]
0x18005f3cd  mov     ecx, r13d
0x18005f3d0  call    ?NotificationTypeNameFromValue@WpnDatabaseHelpers@@YAPEBGW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@Z; WpnDatabaseHelpers::NotificationTypeNameFromValue(__MIDL___MIDL_itf_wpntypes_0000_0000_0005)
0x18005f3d5  mov     [rsp+1E8h+var_1B8], r14; enum PolicyLevel *
0x18005f3da  lea     rcx, [rsp+1E8h+var_124]
0x18005f3e2  mov     [rsp+1E8h+var_1C0], rcx; enum NOTIFICATION_POLICY_REASON *
0x18005f3e7  mov     byte ptr [rsp+1E8h+var_1C8], 1; int
0x18005f3ec  mov     r9, rax; unsigned __int16 *
0x18005f3ef  mov     r8, qword ptr [rsp+1E8h+FileTime.dwLowDateTime]; unsigned __int16 *
0x18005f3f4  mov     rdx, [rsp+1E8h+var_118]; struct INotificationHandler *
0x18005f3fc  mov     rcx, rbx; this
0x18005f3ff  call    ?CheckNotificationHandlerSettingsEnabled@NotificationPlatform@@QEAAJPEAUINotificationHandler@@PEBG1_NPEAW4NOTIFICATION_POLICY_REASON@@PEAW4PolicyLevel@@@Z; NotificationPlatform::CheckNotificationHandlerSettingsEnabled(INotificationHandler *,ushort const *,ushort const *,bool,NOTIFICATION_POLICY_REASON *,PolicyLevel *)
0x18005f404  mov     rcx, [rsp+1E8h]; this
0x18005f40c  test    eax, eax
0x18005f40e  jns     short loc_18005F424
0x18005f410  mov     r9d, eax; char *
0x18005f413  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f41a  mov     edx, 2EEh; void *
0x18005f41f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f424  mov     rax, [rdi+20h]
0x18005f428  mov     rcx, [rax+0F0h]
0x18005f42f  mov     rax, rcx
0x18005f432  neg     rax
0x18005f435  sbb     r9d, r9d
0x18005f438  not     r9d
0x18005f43b  and     r9d, 803E0105h; char *
0x18005f442  mov     rax, [rsp+1E8h]
0x18005f44a  test    rcx, rcx
0x18005f44d  jnz     short loc_18005F463
0x18005f44f  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f456  mov     edx, 2F2h; void *
0x18005f45b  mov     rcx, rax; this
0x18005f45e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f463  mov     rax, [rcx]
0x18005f466  xor     edx, edx
0x18005f468  mov     rax, [rax+28h]
0x18005f46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f471  test    al, al
0x18005f473  jnz     short loc_18005F49A
0x18005f475  mov     [rsp+1E8h+var_187], 1
0x18005f47a  mov     rcx, [rsp+1E8h]; this
0x18005f482  mov     r9d, 80004005h; char *
0x18005f488  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f48f  mov     edx, 2F6h; void *
0x18005f494  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f49a  mov     [rsp+1E8h+var_120], r14
0x18005f4a2  mov     [rsp+1E8h+var_F8], r14
0x18005f4aa  lea     rcx, [rsp+1E8h+var_138]
0x18005f4b2  call    ??$Make@VPlatformFactory@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VPlatformFactory@@@12@XZ; Microsoft::WRL::Details::Make<PlatformFactory,>(void)
0x18005f4b7  mov     rbx, r14
0x18005f4ba  lea     rcx, [rsp+1E8h+var_98]
0x18005f4c2  cmp     rcx, rax
0x18005f4c5  jz      short loc_18005F4CD
0x18005f4c7  mov     rbx, [rax]
0x18005f4ca  mov     [rax], r14
0x18005f4cd  mov     [rsp+1E8h+var_C8], rbx
0x18005f4d5  mov     rcx, [rsp+1E8h+var_138]
0x18005f4dd  test    rcx, rcx
0x18005f4e0  jz      short loc_18005F4F7
0x18005f4e2  mov     [rsp+1E8h+var_138], r14
0x18005f4ea  mov     rax, [rcx]
0x18005f4ed  mov     rax, [rax+10h]
0x18005f4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4f6  nop
0x18005f4f7  mov     rcx, [rsp+1E8h]; this
0x18005f4ff  test    rbx, rbx
0x18005f502  jnz     short loc_18005F51B
0x18005f504  mov     r9d, 80004003h; char *
0x18005f50a  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f511  mov     edx, 2FEh; void *
0x18005f516  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f51b  mov     rax, [rbx]
0x18005f51e  mov     rdi, [rax+18h]
0x18005f522  lea     rcx, [rsp+1E8h+var_120]
0x18005f52a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f52f  lea     r9, [rsp+1E8h+var_120]
0x18005f537  lea     r8, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18005f53e  xor     edx, edx
0x18005f540  mov     rcx, rbx
0x18005f543  mov     rax, rdi
0x18005f546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f54b  mov     rcx, [rsp+1E8h]; this
0x18005f553  test    eax, eax
0x18005f555  jns     short loc_18005F56B
0x18005f557  mov     r9d, eax; char *
0x18005f55a  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f561  mov     edx, 2FFh; void *
0x18005f566  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f56b  mov     rsi, [rsp+1E8h+var_120]
0x18005f573  mov     rax, [rsi]
0x18005f576  mov     rdi, [rax+18h]
0x18005f57a  lea     rcx, [rsp+1E8h+var_F8]
0x18005f582  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f587  lea     rdx, [rsp+1E8h+var_F8]
0x18005f58f  mov     rcx, rsi
0x18005f592  mov     rax, rdi
0x18005f595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f59a  mov     rcx, [rsp+1E8h]; this
0x18005f5a2  test    eax, eax
0x18005f5a4  jns     short loc_18005F5BA
0x18005f5a6  mov     r9d, eax; char *
0x18005f5a9  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f5b0  mov     edx, 300h; void *
0x18005f5b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f5ba  mov     eax, r14d
0x18005f5bd  cmp     r13d, 2
0x18005f5c1  setz    al
0x18005f5c4  inc     eax
0x18005f5c6  mov     dword ptr [rsp+1E8h+var_138], eax
0x18005f5cd  mov     esi, 100h
0x18005f5d2  mov     eax, 1400h
0x18005f5d7  cmp     r13d, 2
0x18005f5db  cmovnz  esi, eax
0x18005f5de  mov     [rsp+1E8h+lpMem], r14
0x18005f5e6  lea     rax, [rsp+1E8h+lpMem]
0x18005f5ee  mov     [rsp+1E8h+var_90], rax
0x18005f5f6  mov     [rsp+1E8h+var_88], 1
0x18005f5fe  lea     edi, [rsi+1]
0x18005f601  call    cs:__imp_GetProcessHeap
0x18005f607  mov     rcx, rax; hHeap
0x18005f60a  mov     r8d, edi; dwBytes
0x18005f60d  mov     edx, 8; dwFlags
0x18005f612  call    cs:__imp_HeapAlloc
0x18005f618  mov     [rsp+1E8h+lpMem], rax
0x18005f620  mov     rcx, [rsp+1E8h]; this
0x18005f628  test    rax, rax
0x18005f62b  jnz     short loc_18005F644
0x18005f62d  mov     r9d, 8007000Eh; char *
0x18005f633  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f63a  mov     edx, 312h; void *
0x18005f63f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f644  mov     [rsp+1E8h+var_158], r14d
0x18005f64c  mov     [rsp+1E8h+var_128], r14d
0x18005f654  mov     [rsp+1E8h+var_108], r14
0x18005f65c  mov     [rsp+1E8h+var_110], r14
0x18005f664  lea     rax, [rsp+1E8h+var_108]
0x18005f66c  mov     [rsp+1E8h+var_C0], rax
0x18005f674  lea     rax, [rsp+1E8h+var_110]
0x18005f67c  mov     [rsp+1E8h+var_B8], rax
0x18005f684  lea     rax, [rsp+1E8h+lpszTime]
0x18005f68c  mov     [rsp+1E8h+var_B0], rax
0x18005f694  mov     [rsp+1E8h+var_A8], 1
0x18005f69c  mov     r8, qword ptr [rsp+1E8h+FileTime.dwLowDateTime]
0x18005f6a1  mov     rdx, qword ptr [rsp+1E8h+SystemTimeAsFileTime.dwLowDateTime]
0x18005f6a9  lea     rcx, [rsp+1E8h+pst]; Src
0x18005f6b1  call    ?ReplaceLanguageAndRegionTokensInUri@PeriodicUpdateManager@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; PeriodicUpdateManager::ReplaceLanguageAndRegionTokensInUri(ushort const *,ushort const *)
0x18005f6b6  mov     rdx, rax
0x18005f6b9  lea     rcx, [rsp+1E8h+var_80]
0x18005f6c1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005f6c6  mov     rdx, [rsp+1E8h+var_48]
0x18005f6ce  cmp     rdx, 7
0x18005f6d2  jbe     short loc_18005F6E9
0x18005f6d4  lea     rdx, ds:2[rdx*2]
0x18005f6dc  mov     rcx, qword ptr [rsp+1E8h+pst.wYear]
0x18005f6e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005f6e9  mov     rax, [rsp+1E8h+lpMem]
0x18005f6f1  lea     r8, [rsp+1E8h+var_80]
0x18005f6f9  cmp     [rsp+1E8h+var_68], 7
0x18005f702  cmova   r8, qword ptr [rsp+1E8h+var_80]; unsigned __int16 *
0x18005f70b  lea     rcx, [rsp+1E8h+lpszTime]
0x18005f713  mov     [rsp+1E8h+var_198], rcx; unsigned __int16 **
0x18005f718  lea     rcx, [rsp+1E8h+var_110]
0x18005f720  mov     [rsp+1E8h+var_1A0], rcx; unsigned __int16 **
0x18005f725  lea     rcx, [rsp+1E8h+var_108]
0x18005f72d  mov     [rsp+1E8h+var_1A8], rcx; unsigned __int16 **
0x18005f732  lea     rcx, [rsp+1E8h+var_168]
0x18005f73a  mov     [rsp+1E8h+var_1B0], rcx; struct CtaHelpers::CtaPolicy *
0x18005f73f  lea     rcx, [rsp+1E8h+var_128]
0x18005f747  mov     [rsp+1E8h+var_1B8], rcx; unsigned int *
0x18005f74c  lea     rcx, [rsp+1E8h+var_158]
0x18005f754  mov     [rsp+1E8h+var_1C0], rcx; unsigned int *
0x18005f759  mov     [rsp+1E8h+var_1C8], rax; int
0x18005f75e  mov     r9d, esi; unsigned int
0x18005f761  mov     rsi, [rsp+1E8h+var_E0]
0x18005f769  mov     rdx, rsi; unsigned __int16 *
0x18005f76c  mov     rcx, [rsp+1E8h+var_100]; this
0x18005f774  call    ?RetrieveNotification@PeriodicUpdateManager@@AEAAJPEBG0KPEADPEAK2AEAUCtaPolicy@CtaHelpers@@PEAPEAG44@Z; PeriodicUpdateManager::RetrieveNotification(ushort const *,ushort const *,ulong,char *,ulong *,ulong *,CtaHelpers::CtaPolicy &,ushort * *,ushort * *,ushort * *)
0x18005f779  mov     edi, eax
0x18005f77b  cmp     [rsp+1E8h+var_158], r14d
0x18005f783  jz      loc_18005F816
0x18005f789  mov     rax, [rsp+1E8h+var_100]
0x18005f791  mov     rax, [rax+20h]
0x18005f795  mov     r10, [rax+78h]
0x18005f799  mov     rax, r10
0x18005f79c  neg     rax
0x18005f79f  sbb     r9d, r9d
0x18005f7a2  not     r9d
0x18005f7a5  and     r9d, 803E0105h; char *
0x18005f7ac  mov     rcx, [rsp+1E8h]; this
0x18005f7b4  test    r10, r10
0x18005f7b7  jnz     short loc_18005F7CA
0x18005f7b9  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f7c0  mov     edx, 330h; void *
0x18005f7c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f7ca  mov     rax, [r10]
0x18005f7cd  mov     ecx, [rsp+1E8h+var_158]
0x18005f7d4  mov     [rsp+1E8h+var_1C0], rcx
0x18005f7d9  mov     dword ptr [rsp+1E8h+var_1C8], r14d; int
0x18005f7de  mov     r9d, 1
0x18005f7e4  xor     r8d, r8d
0x18005f7e7  mov     rdx, rsi
0x18005f7ea  mov     rcx, r10
0x18005f7ed  mov     rax, [rax+40h]
0x18005f7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f7f6  mov     rcx, [rsp+1E8h]; this
0x18005f7fe  test    eax, eax
0x18005f800  jns     short loc_18005F816
0x18005f802  mov     r9d, eax; char *
0x18005f805  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005f80c  mov     edx, 336h; void *
0x18005f811  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f816  mov     ecx, [rsp+1E8h+var_128]
0x18005f81d  cmp     ecx, 0C8h
0x18005f823  jz      short loc_18005F85C
0x18005f825  test    cs:byte_18015DE46, 1
0x18005f82c  jz      short loc_18005F85C
0x18005f82e  lea     rax, [rsp+1E8h+var_80]
0x18005f836  cmp     [rsp+1E8h+var_68], 7
0x18005f83f  cmova   rax, qword ptr [rsp+1E8h+var_80]
  ... truncated ...
```
