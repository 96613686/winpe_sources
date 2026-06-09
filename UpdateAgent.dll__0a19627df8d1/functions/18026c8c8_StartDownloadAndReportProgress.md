# StartDownloadAndReportProgress

- ea: `0x18026c8c8`
- end: `0x18026d9a9`
- name: `StartDownloadAndReportProgress`
- size: `4321`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18026e7b0`

## callees

- `0x1800059d0`
- `0x180005cf0`
- `0x18000a0e8`
- `0x18000aa98`
- `0x18000c4c4`
- `0x180012460`
- `0x18001270c`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3ec`
- `0x18026926c`
- `0x1802694c8`
- `0x18026c8c8`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18026d0ac`
- `OLEAUT32!__imp_SysAllocString` at `0x18026d0ac`
- `OLEAUT32!__imp_VariantInit` at `0x18026c904`
- `OLEAUT32!__imp_VariantInit` at `0x18026c930`
- `OLEAUT32!__imp_VariantInit` at `0x18026c904`
- `OLEAUT32!__imp_VariantInit` at `0x18026c930`
- `OLEAUT32!__imp_VariantClear` at `0x18026ca21`
- `OLEAUT32!__imp_VariantClear` at `0x18026caba`
- `OLEAUT32!__imp_VariantClear` at `0x18026cd37`
- `OLEAUT32!__imp_VariantClear` at `0x18026ce06`
- `OLEAUT32!__imp_VariantClear` at `0x18026d0ec`
- `OLEAUT32!__imp_VariantClear` at `0x18026d1bd`
- `OLEAUT32!__imp_VariantClear` at `0x18026d3f6`
- `OLEAUT32!__imp_VariantClear` at `0x18026d4c7`
- `OLEAUT32!__imp_VariantClear` at `0x18026d5f4`
- `OLEAUT32!__imp_VariantClear` at `0x18026d82c`
- `OLEAUT32!__imp_VariantClear` at `0x18026d8de`
- `OLEAUT32!__imp_VariantClear` at `0x18026d98b`
- `OLEAUT32!__imp_VariantClear` at `0x18026ca21`
- `OLEAUT32!__imp_VariantClear` at `0x18026caba`
- `OLEAUT32!__imp_VariantClear` at `0x18026cd37`
- `OLEAUT32!__imp_VariantClear` at `0x18026ce06`
- `OLEAUT32!__imp_VariantClear` at `0x18026d0ec`
- `OLEAUT32!__imp_VariantClear` at `0x18026d1bd`
- `OLEAUT32!__imp_VariantClear` at `0x18026d3f6`
- `OLEAUT32!__imp_VariantClear` at `0x18026d4c7`
- `OLEAUT32!__imp_VariantClear` at `0x18026d5f4`
- `OLEAUT32!__imp_VariantClear` at `0x18026d82c`
- `OLEAUT32!__imp_VariantClear` at `0x18026d8de`
- `OLEAUT32!__imp_VariantClear` at `0x18026d98b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18026d341`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18026d341`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18026cc06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18026cc06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026cc35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026cc35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026ce44`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026ce44`

## string_xrefs

- `0x18026ca07`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026cc20`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18026cc50`: `Failed to create event.`
- `0x18026c963`: `No update downloader specified`
- `0x18026c9c7`: `No update specified`
- `0x18026cf51`: `Failed to call put_updates on downloader`
- `0x18026cedf`: `Failed to add update to collection`
- `0x18026cfe8`: `WU: PSF is available and preferred for the update.`
- `0x18026ce69`: `Failed to create collection`
- `0x18026ccdc`: `Failed to initialize complete callback`
- `0x18026cffa`: `WU: PSF is not available for the update.`
- `0x18026cff1`: `WU: PSF is available but not preferred for the update.`
- `0x18026d6ee`: `DWLD: Failed to get update result`

## pseudocode

```c
__int64 __fastcall StartDownloadAndReportProgress(__int64 *a1, __int64 a2, __int64 *a3)
{
  unsigned int v5; // esi
  __int64 v6; // rdx
  _QWORD *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  char *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rax
  HANDLE EventW; // rax
  signed int LastError; // r12d
  unsigned int v17; // eax
  int v18; // eax
  int v19; // r12d
  __int64 v20; // rdx
  char *v21; // rcx
  char *v22; // rcx
  HRESULT v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  const char *v28; // r8
  const char *v29; // rcx
  int v30; // eax
  char *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // r10
  __int64 v35; // rax
  char *v36; // r8
  int v37; // eax
  unsigned int v38; // eax
  DWORD v39; // eax
  unsigned int v40; // r15d
  __int64 v41; // rdx
  char *v42; // rcx
  __int64 v43; // rdx
  int v44; // eax
  int v45; // eax
  __int64 v46; // rdx
  char *v47; // rcx
  char *v48; // rcx
  int v49; // eax
  int v50; // eax
  unsigned int ppv; // [rsp+20h] [rbp-B1h]
  LPVOID *ppva; // [rsp+20h] [rbp-B1h]
  unsigned int v53[2]; // [rsp+30h] [rbp-A1h] BYREF
  int v54[2]; // [rsp+38h] [rbp-99h] BYREF
  char *v55; // [rsp+40h] [rbp-91h] BYREF
  int *v56; // [rsp+48h] [rbp-89h] BYREF
  VARIANTARG v57; // [rsp+50h] [rbp-81h] BYREF
  int v58; // [rsp+70h] [rbp-61h] BYREF
  __int64 v59; // [rsp+78h] [rbp-59h] BYREF
  LPVOID v60; // [rsp+80h] [rbp-51h] BYREF
  __int64 *v61; // [rsp+88h] [rbp-49h] BYREF
  __int64 v62; // [rsp+90h] [rbp-41h] BYREF
  __int64 v63; // [rsp+98h] [rbp-39h] BYREF
  int v64; // [rsp+A0h] [rbp-31h] BYREF
  VARIANTARG v65; // [rsp+A8h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-11h] BYREF
  __int16 v67[2]; // [rsp+D8h] [rbp+7h] BYREF
  unsigned int v68; // [rsp+DCh] [rbp+Bh] BYREF
  int v69; // [rsp+E0h] [rbp+Fh] BYREF
  int v70; // [rsp+E4h] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v67[0] = 0;
  VariantInit(&pvarg);
  v68 = 0;
  v69 = 0;
  v59 = 0;
  v63 = 0;
  v62 = 0;
  v60 = 0;
  v61 = 0;
  VariantInit(&v65);
  v70 = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
    v64 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update downloader specified");
      *(_QWORD *)v54 = &v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v54);
    }
    v6 = 801;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80070057LL,
      ppv);
    if ( v65.vt )
    {
      VariantClear(&v65);
      v65.vt = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
      v61 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v63 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
LABEL_21:
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return v5;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v64 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update specified");
      *(_QWORD *)v54 = &v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v54);
    }
    v6 = 802;
    goto LABEL_9;
  }
  v8 = operator new(0x40u);
  *(_QWORD *)v54 = v8;
  v8[1] = CCbsStringArray::`vbtable';
  *v8 = &CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'};
  v8[7] = &CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `IDownloadProgressChangedCallback'};
  v9 = *(int *)(v8[1] + 4LL);
  *(_DWORD *)((char *)v8 + v9 + 4) = v9 - 24;
  *v8 = &CUUPDownloadProgressCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'};
  v10 = v8[1];
  *((_DWORD *)v8 + 4) = 1;
  *(_QWORD *)((char *)v8 + *(int *)(v10 + 4) + 8) = &CUUPDownloadProgressCallBack::`vftable'{for `IDownloadProgressChangedCallback'};
  v11 = *(int *)(v8[1] + 4LL);
  *(_DWORD *)((char *)v8 + v11 + 4) = v11 - 48;
  *((_BYTE *)v8 + 24) = 0;
  *(_QWORD *)((char *)v8 + 28) = 0;
  v8[5] = 0;
  v12 = (char *)operator new(0x30u);
  *((_QWORD *)v12 + 2) = 0;
  *((_QWORD *)v12 + 3) = 0;
  *((_QWORD *)v12 + 4) = 0;
  *((_QWORD *)v12 + 1) = &CUUPDownloadCompleteCallBack::`vbtable';
  *(_QWORD *)v12 = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  *((_QWORD *)v12 + 5) = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'};
  v13 = *((_QWORD *)v12 + 1);
  v55 = v12;
  *(_DWORD *)&v12[*(int *)(v13 + 4) + 4] = *(_DWORD *)(v13 + 4) - 24;
  *(_QWORD *)v12 = &CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v14 = *((_QWORD *)v12 + 1);
  *((_DWORD *)v12 + 4) = 1;
  *(_QWORD *)&v12[*(int *)(v14 + 4) + 8] = &CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'};
  *(_DWORD *)&v12[*(int *)(*((_QWORD *)v12 + 1) + 4LL) + 4] = 0;
  *((_QWORD *)v12 + 3) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( *((_QWORD *)v12 + 3) )
    goto LABEL_197;
  *((_QWORD *)v12 + 3) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create event.");
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      else
        v17 = LastError;
      v64 = v17;
      *(_QWORD *)v53 = &v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v53);
    }
    if ( LastError )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x80,
              (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
              (const char *)(unsigned int)LastError,
              ppv);
      v19 = v18;
      if ( v18 < 0 )
      {
        v58 = v18;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize complete callback");
          *(_QWORD *)v53 = &v58;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v53);
        }
        v20 = 810;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)(unsigned int)v19,
          (int)ppva);
        if ( v65.vt )
        {
          VariantClear(&v65);
          v65.vt = 0;
        }
        if ( v61 )
        {
          (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
          v61 = 0;
        }
        if ( v60 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
          v60 = 0;
        }
        if ( v62 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          v62 = 0;
        }
        if ( v63 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
          v63 = 0;
        }
        if ( v59 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          v59 = 0;
        }
        v21 = &v12[*(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8];
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
        v22 = (char *)v8 + *(int *)(v8[1] + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
        if ( pvarg.vt )
          VariantClear(&pvarg);
        return (unsigned int)v19;
      }
    }
  }
  if ( v60 )
    goto LABEL_197;
  v23 = CoCreateInstance(
          &GUID_13639463_00db_4646_803d_528026140d88,
          0,
          1u,
          &GUID_07f7438c_7709_4ca5_b518_91279288134e,
          &v60);
  v19 = v23;
  if ( v23 < 0 )
  {
    v58 = v23;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create collection");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v20 = 813;
    goto LABEL_36;
  }
  v24 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v60 + 96LL))(v60, a3, &v70);
  v19 = v24;
  if ( v24 < 0 )
  {
    v58 = v24;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add update to collection");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v20 = 815;
    goto LABEL_36;
  }
  v25 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*a1 + 112))(a1, v60);
  v19 = v25;
  if ( v25 < 0 )
  {
    v58 = v25;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to call put_updates on downloader");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v20 = 817;
    goto LABEL_36;
  }
  v26 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*a3 + 104))(a3, v67);
  if ( v26 )
  {
    if ( v26 < 0 )
    {
      v28 = "WU:Failed to check whether psf is available.";
      goto LABEL_76;
    }
  }
  else
  {
    if ( v67[0] != -1 )
    {
      v29 = "WU: PSF is not available for the update.";
LABEL_73:
      LogAdapter::TraceInfo<>(v29);
      goto LABEL_77;
    }
    v27 = *a3;
    LOWORD(v64) = 0;
    v26 = (*(__int64 (__fastcall **)(__int64 *, int *))(v27 + 112))(a3, &v64);
    if ( v26 < 0 )
    {
      v28 = "WU: Failed to check whether PSF is preferred.";
LABEL_76:
      LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v26, v28);
      goto LABEL_77;
    }
    if ( !v26 )
    {
      if ( (_WORD)v64 == 0xFFFF )
        v29 = "WU: PSF is available and preferred for the update.";
      else
        v29 = "WU: PSF is available but not preferred for the update.";
      goto LABEL_73;
    }
  }
LABEL_77:
  if ( v61 )
    goto LABEL_197;
  v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*a1)(
          a1,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v61);
  v19 = v30;
  if ( v30 < 0 )
  {
    v58 = v30;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set client ID");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v20 = 856;
    goto LABEL_36;
  }
  v65.vt = 8;
  v65.llVal = (LONGLONG)SysAllocString(L"{\"ModuleID\" : \"CurrentVersionScan\"}");
  if ( !v65.llVal )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
    if ( v65.vt )
    {
      VariantClear(&v65);
      v65.vt = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
      v61 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v63 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    v31 = &v12[*(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = *(int *)(v8[1] + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)((char *)v8 + v32 + 8) + 16LL))((__int64)v8 + v32 + 8);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return 2147942414LL;
  }
  v33 = *v61;
  v57 = v65;
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v33 + 32))(v61, 196621, &v57);
  if ( v19 < 0 )
  {
    v58 = v19;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set scan current product version only");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v20 = 862;
    goto LABEL_36;
  }
  if ( v59 )
    goto LABEL_197;
  v34 = *a1;
  v35 = v8[1];
  v36 = &v12[*(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8];
  v57 = pvarg;
  ppva = (LPVOID *)&v59;
  v37 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *, VARIANTARG *))(v34 + 120))(
          a1,
          (__int64)v8 + *(int *)(v35 + 4) + 8,
          v36,
          &v57);
  v19 = v37;
  if ( v37 < 0 )
  {
    v58 = v37;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed calling begin download");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v20 = 867;
    goto LABEL_36;
  }
  v38 = v68;
  while ( 1 )
  {
    if ( !*((_BYTE *)v8 + 24) && v38 > 0xDBBA0 || *((int *)v8 + 8) < 4 && v38 > 0x2932E0 )
    {
      CancelDownload(v59, a1, 0);
      v40 = -2145124319;
      v58 = -2145124319;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<unsigned long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Timed out waiting on WU download for {} milliseconds.",
          &v68);
        *(_QWORD *)v53 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v53);
      }
      v41 = 882;
LABEL_118:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v40,
        (int)ppva);
      if ( v65.vt )
      {
        VariantClear(&v65);
        v65.vt = 0;
      }
      if ( v61 )
      {
        (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
        v61 = 0;
      }
      if ( v60 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
        v60 = 0;
      }
      if ( v62 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
        v62 = 0;
      }
      if ( v63 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        v63 = 0;
      }
      if ( v59 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        v59 = 0;
      }
      v42 = &v12[*(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v42 + 16LL))(v42);
      v43 = *(int *)(v8[1] + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)((char *)v8 + v43 + 8) + 16LL))((__int64)v8 + v43 + 8);
      goto LABEL_131;
    }
    v39 = WaitForSingleObject(*((HANDLE *)v12 + 3), 0x7D0u);
    if ( !v39 )
      break;
    if ( v39 != 258 )
    {
      v40 = -2147467259;
      v58 = -2147467259;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query status of event, assuming failure.");
        *(_QWORD *)v53 = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v53);
      }
      v41 = 911;
      goto LABEL_118;
    }
    v38 = v68 + 2000;
    v68 += 2000;
  }
  v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 80LL))(v59);
  if ( v44 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v44, "DWLD: Failed to call download job cleanup");
  if ( v63 )
    goto LABEL_197;
  v45 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*a1 + 136))(a1, v59, &v63);
  v40 = v45;
  if ( v45 < 0 )
  {
    v58 = v45;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to call end download");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v46 = 935;
    goto LABEL_144;
  }
  if ( v62 )
  {
LABEL_197:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026D9A8LL);
  }
  v49 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 72LL))(v63, 0, &v62);
  v40 = v49;
  if ( v49 < 0 )
  {
    v58 = v49;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to get update result");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v46 = 942;
    goto LABEL_144;
  }
  v50 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 56LL))(v62, &v69);
  v40 = v50;
  if ( v50 >= 0 )
  {
    v5 = v69;
    if ( v69 < 0 )
    {
      v64 = v69;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        v56 = &v69;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Download failed with {}",
          (__int64)&v56);
        *(_QWORD *)v53 = &v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v53);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B2,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v5,
        (int)ppva);
      if ( v65.vt )
      {
        VariantClear(&v65);
        v65.vt = 0;
      }
      if ( v61 )
      {
        (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
        v61 = 0;
      }
      if ( v60 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
        v60 = 0;
      }
      if ( v62 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
        v62 = 0;
      }
      if ( v63 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        v63 = 0;
      }
      if ( v59 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        v59 = 0;
      }
      Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(&v55);
      Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v54);
      goto LABEL_21;
    }
    if ( v65.vt )
    {
      VariantClear(&v65);
      v65.vt = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
      v61 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v63 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(&v55);
    Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v54);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return 0;
  }
  else
  {
    v58 = v50;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to get download hresult");
      *(_QWORD *)v53 = &v58;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v53);
    }
    v46 = 944;
LABEL_144:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v40,
      (int)ppva);
    if ( v65.vt )
    {
      VariantClear(&v65);
      v65.vt = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
      v61 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v63 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    v47 = &v12[*(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v47 + 16LL))(v47);
    v48 = (char *)v8 + *(int *)(v8[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v48 + 16LL))(v48);
LABEL_131:
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return v40;
  }
}

```

## disassembly

```asm
0x18026c8c8  mov     [rsp-8+arg_8], rbx
0x18026c8cd  push    rbp
0x18026c8ce  push    rsi
0x18026c8cf  push    rdi
0x18026c8d0  push    r12
0x18026c8d2  push    r13
0x18026c8d4  push    r14
0x18026c8d6  push    r15
0x18026c8d8  lea     rbp, [rsp-1Fh]
0x18026c8dd  sub     rsp, 0F0h
0x18026c8e4  mov     rax, cs:__security_cookie
0x18026c8eb  xor     rax, rsp
0x18026c8ee  mov     [rbp+4Fh+var_38], rax
0x18026c8f2  mov     r15, rcx
0x18026c8f5  xor     r12d, r12d
0x18026c8f8  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18026c8fc  mov     [rbp+4Fh+var_48], r12w
0x18026c901  mov     r13, r8
0x18026c904  call    cs:__imp_VariantInit
0x18026c90b  nop     dword ptr [rax+rax+00h]
0x18026c910  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18026c914  mov     [rbp+4Fh+var_44], r12d
0x18026c918  mov     dword ptr [rbp+4Fh+var_40], r12d
0x18026c91c  mov     [rbp+4Fh+var_A8], r12
0x18026c920  mov     [rbp+4Fh+var_88], r12
0x18026c924  mov     [rbp+4Fh+var_90], r12
0x18026c928  mov     [rbp+4Fh+var_A0], r12
0x18026c92c  mov     [rbp+4Fh+var_98], r12
0x18026c930  call    cs:__imp_VariantInit
0x18026c937  nop     dword ptr [rax+rax+00h]
0x18026c93c  mov     dword ptr [rbp+4Fh+var_40+4], r12d
0x18026c940  test    r15, r15
0x18026c943  jnz     short loc_18026C9A1
0x18026c945  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c94c  mov     esi, 80070057h
0x18026c951  mov     [rbp+4Fh+var_80], esi
0x18026c954  test    rcx, rcx
0x18026c957  jz      short loc_18026C99A
0x18026c959  lea     ebx, [r12+3]
0x18026c95e  xor     edx, edx
0x18026c960  mov     r8d, ebx
0x18026c963  lea     r9, aNoUpdateDownlo; "No update downloader specified"
0x18026c96a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026c96f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c976  lea     rax, [rbp+4Fh+var_80]
0x18026c97a  mov     qword ptr [rsp+120h+var_E8], rax
0x18026c97f  lea     r9, asc_1802C6678; ": {}"
0x18026c986  lea     rax, [rsp+120h+var_E8]
0x18026c98b  mov     r8d, ebx
0x18026c98e  mov     dl, 1
0x18026c990  mov     [rsp+120h+ppv], rax
0x18026c995  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026c99a  mov     edx, 321h
0x18026c99f  jmp     short loc_18026CA03
0x18026c9a1  test    r13, r13
0x18026c9a4  jnz     loc_18026CAF0
0x18026c9aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c9b1  mov     esi, 80070057h
0x18026c9b6  mov     [rbp+4Fh+var_80], esi
0x18026c9b9  test    rcx, rcx
0x18026c9bc  jz      short loc_18026C9FE
0x18026c9be  lea     ebx, [r13+3]
0x18026c9c2  xor     edx, edx
0x18026c9c4  mov     r8d, ebx
0x18026c9c7  lea     r9, aNoUpdateSpecif; "No update specified"
0x18026c9ce  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026c9d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026c9da  lea     rax, [rbp+4Fh+var_80]
0x18026c9de  mov     qword ptr [rsp+120h+var_E8], rax
0x18026c9e3  lea     r9, asc_1802C6678; ": {}"
0x18026c9ea  lea     rax, [rsp+120h+var_E8]
0x18026c9ef  mov     r8d, ebx
0x18026c9f2  mov     dl, 1
0x18026c9f4  mov     [rsp+120h+ppv], rax; int
0x18026c9f9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026c9fe  mov     edx, 322h; void *
0x18026ca03  mov     rcx, [rbp+57h]; this
0x18026ca07  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026ca0e  mov     r9d, esi; char *
0x18026ca11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ca16  cmp     word ptr [rbp+4Fh+var_78], r12w
0x18026ca1b  jz      short loc_18026CA32
0x18026ca1d  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18026ca21  call    cs:__imp_VariantClear
0x18026ca28  nop     dword ptr [rax+rax+00h]
0x18026ca2d  mov     word ptr [rbp+4Fh+var_78], r12w
0x18026ca32  mov     rcx, [rbp+4Fh+var_98]
0x18026ca36  test    rcx, rcx
0x18026ca39  jz      short loc_18026CA4B
0x18026ca3b  mov     rax, [rcx]
0x18026ca3e  mov     rax, [rax+10h]
0x18026ca42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ca47  mov     [rbp+4Fh+var_98], r12
0x18026ca4b  mov     rcx, [rbp+4Fh+var_A0]
0x18026ca4f  test    rcx, rcx
0x18026ca52  jz      short loc_18026CA64
0x18026ca54  mov     rax, [rcx]
0x18026ca57  mov     rax, [rax+10h]
0x18026ca5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ca60  mov     [rbp+4Fh+var_A0], r12
0x18026ca64  mov     rcx, [rbp+4Fh+var_90]
0x18026ca68  test    rcx, rcx
0x18026ca6b  jz      short loc_18026CA7D
0x18026ca6d  mov     rax, [rcx]
0x18026ca70  mov     rax, [rax+10h]
0x18026ca74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ca79  mov     [rbp+4Fh+var_90], r12
0x18026ca7d  mov     rcx, [rbp+4Fh+var_88]
0x18026ca81  test    rcx, rcx
0x18026ca84  jz      short loc_18026CA96
0x18026ca86  mov     rax, [rcx]
0x18026ca89  mov     rax, [rax+10h]
0x18026ca8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ca92  mov     [rbp+4Fh+var_88], r12
0x18026ca96  mov     rcx, [rbp+4Fh+var_A8]
0x18026ca9a  test    rcx, rcx
0x18026ca9d  jz      short loc_18026CAAF
0x18026ca9f  mov     rax, [rcx]
0x18026caa2  mov     rax, [rax+10h]
0x18026caa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026caab  mov     [rbp+4Fh+var_A8], r12
0x18026caaf  cmp     word ptr [rbp+4Fh+pvarg], r12w
0x18026cab4  jz      short loc_18026CAC6
0x18026cab6  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18026caba  call    cs:__imp_VariantClear
0x18026cac1  nop     dword ptr [rax+rax+00h]
0x18026cac6  mov     eax, esi
0x18026cac8  mov     rcx, [rbp+4Fh+var_38]
0x18026cacc  xor     rcx, rsp; StackCookie
0x18026cacf  call    __security_check_cookie
0x18026cad4  mov     rbx, [rsp+120h+arg_8]
0x18026cadc  add     rsp, 0F0h
0x18026cae3  pop     r15
0x18026cae5  pop     r14
0x18026cae7  pop     r13
0x18026cae9  pop     r12
0x18026caeb  pop     rdi
0x18026caec  pop     rsi
0x18026caed  pop     rbp
0x18026caee  retn
0x18026caf0  mov     ecx, 40h ; '@'; Size
0x18026caf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18026cafa  mov     r14, rax
0x18026cafd  lea     rax, ??_8CCbsStringArray@@7B@; const CCbsStringArray::`vbtable'
0x18026cb04  mov     qword ptr [rsp+120h+var_E8], r14
0x18026cb09  mov     [r14+8], rax
0x18026cb0d  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadProgressChangedCallback@@$$V@@6B0@@; const CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'}
0x18026cb14  mov     [r14], rax
0x18026cb17  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadProgressChangedCallback@@$$V@@6BIDownloadProgressChangedCallback@@@; const CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `IDownloadProgressChangedCallback'}
0x18026cb1e  mov     [r14+38h], rax
0x18026cb22  lea     rax, ??_7CUUPDownloadProgressCallBack@@6B?$CCbsIUnknownImpl@UIDownloadProgressChangedCallback@@$$V@@@; const CUUPDownloadProgressCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'}
0x18026cb29  mov     rcx, [r14+8]
0x18026cb2d  movsxd  rdx, dword ptr [rcx+4]
0x18026cb31  lea     r8d, [rdx-18h]
0x18026cb35  mov     [rdx+r14+4], r8d
0x18026cb3a  mov     [r14], rax
0x18026cb3d  mov     rax, [r14+8]
0x18026cb41  mov     dword ptr [r14+10h], 1
0x18026cb49  movsxd  rcx, dword ptr [rax+4]
0x18026cb4d  lea     rax, ??_7CUUPDownloadProgressCallBack@@6BIDownloadProgressChangedCallback@@@; const CUUPDownloadProgressCallBack::`vftable'{for `IDownloadProgressChangedCallback'}
0x18026cb54  mov     [rcx+r14+8], rax
0x18026cb59  mov     rax, [r14+8]
0x18026cb5d  movsxd  rcx, dword ptr [rax+4]
0x18026cb61  lea     edx, [rcx-30h]
0x18026cb64  mov     [rcx+r14+4], edx
0x18026cb69  mov     ecx, 30h ; '0'; Size
0x18026cb6e  mov     [r14+18h], r12b
0x18026cb72  mov     [r14+1Ch], r12
0x18026cb76  mov     [r14+28h], r12
0x18026cb7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18026cb7f  mov     rsi, rax
0x18026cb82  xor     r9d, r9d; lpName
0x18026cb85  mov     [rax+10h], r12
0x18026cb89  mov     [rax+18h], r12
0x18026cb8d  mov     [rax+20h], r12
0x18026cb91  lea     rax, ??_8CUUPDownloadCompleteCallBack@@7B@; const CUUPDownloadCompleteCallBack::`vbtable'
0x18026cb98  mov     [rsi+8], rax
0x18026cb9c  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6B0@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x18026cba3  mov     [rsi], rax
0x18026cba6  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6BIDownloadCompletedCallback@@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'}
0x18026cbad  mov     [rsi+28h], rax
0x18026cbb1  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6B?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x18026cbb8  mov     rcx, [rsi+8]
0x18026cbbc  mov     [rsp+120h+var_E0], rsi
0x18026cbc1  movsxd  rdx, dword ptr [rcx+4]
0x18026cbc5  lea     r8d, [rdx-18h]
0x18026cbc9  mov     [rdx+rsi+4], r8d
0x18026cbce  xor     r8d, r8d; bInitialState
0x18026cbd1  mov     [rsi], rax
0x18026cbd4  lea     edx, [r9+1]; bManualReset
0x18026cbd8  mov     rax, [rsi+8]
0x18026cbdc  mov     dword ptr [rsi+10h], 1
0x18026cbe3  movsxd  rcx, dword ptr [rax+4]
0x18026cbe7  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6BIDownloadCompletedCallback@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'}
0x18026cbee  mov     [rcx+rsi+8], rax
0x18026cbf3  mov     rax, [rsi+8]
0x18026cbf7  movsxd  rcx, dword ptr [rax+4]
0x18026cbfb  mov     [rcx+rsi+4], r12d
0x18026cc00  xor     ecx, ecx; lpEventAttributes
0x18026cc02  mov     [rsi+18h], r12
0x18026cc06  call    cs:__imp_CreateEventW
0x18026cc0d  nop     dword ptr [rax+rax+00h]
0x18026cc12  cmp     [rsi+18h], r12
0x18026cc16  jnz     loc_18026D99E
0x18026cc1c  mov     [rsi+18h], rax
0x18026cc20  lea     rdi, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18026cc27  mov     ebx, 3
0x18026cc2c  test    rax, rax
0x18026cc2f  jnz     loc_18026CE1D
0x18026cc35  call    cs:__imp_GetLastError
0x18026cc3c  nop     dword ptr [rax+rax+00h]
0x18026cc41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026cc48  mov     r12d, eax
0x18026cc4b  test    rcx, rcx
0x18026cc4e  jz      short loc_18026CCA2
0x18026cc50  lea     r9, aFailedToCreate_52; "Failed to create event."
0x18026cc57  mov     r8d, ebx
0x18026cc5a  xor     edx, edx
0x18026cc5c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026cc61  test    r12d, r12d
0x18026cc64  jg      short loc_18026CC6B
0x18026cc66  mov     eax, r12d
0x18026cc69  jmp     short loc_18026CC74
0x18026cc6b  movzx   eax, r12w
0x18026cc6f  or      eax, 80070000h
0x18026cc74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026cc7b  lea     r9, a0; ": {0}"
0x18026cc82  mov     [rbp+4Fh+var_80], eax
0x18026cc85  mov     r8d, ebx
0x18026cc88  lea     rax, [rbp+4Fh+var_80]
0x18026cc8c  mov     dl, 1
0x18026cc8e  mov     qword ptr [rsp+120h+var_F0], rax
0x18026cc93  lea     rax, [rsp+120h+var_F0]
0x18026cc98  mov     [rsp+120h+ppv], rax; unsigned int
0x18026cc9d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026cca2  test    r12d, r12d
0x18026cca5  jz      loc_18026CE1A
0x18026ccab  mov     rcx, [rbp+57h]; this
0x18026ccaf  mov     r9d, r12d; char *
0x18026ccb2  mov     r8, rdi; unsigned int
0x18026ccb5  mov     edx, 80h; void *
0x18026ccba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026ccbf  mov     r12d, eax
0x18026ccc2  test    eax, eax
0x18026ccc4  jns     loc_18026CE1A
0x18026ccca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026ccd1  xor     r15d, r15d
0x18026ccd4  mov     [rbp+4Fh+var_B0], eax
0x18026ccd7  test    rcx, rcx
0x18026ccda  jz      short loc_18026CD18
0x18026ccdc  lea     r9, aFailedToInitia_1; "Failed to initialize complete callback"
0x18026cce3  mov     r8d, ebx
0x18026cce6  xor     edx, edx
0x18026cce8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18026cced  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18026ccf4  lea     rax, [rbp+4Fh+var_B0]
0x18026ccf8  mov     qword ptr [rsp+120h+var_F0], rax
0x18026ccfd  lea     r9, asc_1802C6678; ": {}"
0x18026cd04  lea     rax, [rsp+120h+var_F0]
0x18026cd09  mov     r8d, ebx
0x18026cd0c  mov     dl, 1
0x18026cd0e  mov     [rsp+120h+ppv], rax; int
0x18026cd13  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18026cd18  mov     edx, 32Ah; void *
0x18026cd1d  mov     rcx, [rbp+57h]; this
0x18026cd21  mov     r9d, r12d; char *
0x18026cd24  mov     r8, rdi; unsigned int
0x18026cd27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cd2c  cmp     word ptr [rbp+4Fh+var_78], r15w
0x18026cd31  jz      short loc_18026CD48
0x18026cd33  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18026cd37  call    cs:__imp_VariantClear
0x18026cd3e  nop     dword ptr [rax+rax+00h]
0x18026cd43  mov     word ptr [rbp+4Fh+var_78], r15w
0x18026cd48  mov     rcx, [rbp+4Fh+var_98]
0x18026cd4c  test    rcx, rcx
0x18026cd4f  jz      short loc_18026CD61
0x18026cd51  mov     rax, [rcx]
0x18026cd54  mov     rax, [rax+10h]
0x18026cd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cd5d  mov     [rbp+4Fh+var_98], r15
0x18026cd61  mov     rcx, [rbp+4Fh+var_A0]
0x18026cd65  test    rcx, rcx
0x18026cd68  jz      short loc_18026CD7A
0x18026cd6a  mov     rax, [rcx]
0x18026cd6d  mov     rax, [rax+10h]
0x18026cd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cd76  mov     [rbp+4Fh+var_A0], r15
0x18026cd7a  mov     rcx, [rbp+4Fh+var_90]
0x18026cd7e  test    rcx, rcx
0x18026cd81  jz      short loc_18026CD93
0x18026cd83  mov     rax, [rcx]
0x18026cd86  mov     rax, [rax+10h]
0x18026cd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cd8f  mov     [rbp+4Fh+var_90], r15
0x18026cd93  mov     rcx, [rbp+4Fh+var_88]
0x18026cd97  test    rcx, rcx
0x18026cd9a  jz      short loc_18026CDAC
0x18026cd9c  mov     rax, [rcx]
0x18026cd9f  mov     rax, [rax+10h]
  ... truncated ...
```
