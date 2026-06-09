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
  __int64 v7; // rdx
  __int64 v8; // rdx
  _QWORD *v10; // r14
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  char *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  HANDLE EventW; // rax
  signed int LastError; // r12d
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // eax
  int v22; // r12d
  __int64 v23; // rdx
  __int64 v24; // rdx
  char *v25; // rcx
  char *v26; // rcx
  HRESULT v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rax
  const char *v35; // r8
  const char *v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  char *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r10
  __int64 v44; // rax
  char *v45; // r8
  int v46; // eax
  __int64 v47; // rdx
  unsigned int v48; // eax
  DWORD v49; // eax
  unsigned int v50; // r15d
  __int64 v51; // rdx
  __int64 v52; // rdx
  char *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rdx
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rdx
  char *v60; // rcx
  char *v61; // rcx
  int v62; // eax
  __int64 v63; // rdx
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-B1h]
  unsigned int *ppva; // [rsp+20h] [rbp-B1h]
  unsigned int v69[2]; // [rsp+30h] [rbp-A1h] BYREF
  int v70[2]; // [rsp+38h] [rbp-99h] BYREF
  _QWORD v71[2]; // [rsp+40h] [rbp-91h] BYREF
  VARIANTARG v72; // [rsp+50h] [rbp-81h] BYREF
  int v73; // [rsp+70h] [rbp-61h] BYREF
  __int64 v74; // [rsp+78h] [rbp-59h] BYREF
  LPVOID v75; // [rsp+80h] [rbp-51h] BYREF
  __int64 *v76; // [rsp+88h] [rbp-49h] BYREF
  __int64 v77; // [rsp+90h] [rbp-41h] BYREF
  __int64 v78; // [rsp+98h] [rbp-39h] BYREF
  int v79; // [rsp+A0h] [rbp-31h] BYREF
  VARIANTARG v80; // [rsp+A8h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-11h] BYREF
  __int16 v82[2]; // [rsp+D8h] [rbp+7h] BYREF
  unsigned int v83; // [rsp+DCh] [rbp+Bh] BYREF
  int v84; // [rsp+E0h] [rbp+Fh] BYREF
  int v85; // [rsp+E4h] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v82[0] = 0;
  VariantInit(&pvarg);
  v83 = 0;
  v84 = 0;
  v74 = 0;
  v78 = 0;
  v77 = 0;
  v75 = 0;
  v76 = 0;
  VariantInit(&v80);
  v85 = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
    v79 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update downloader specified");
      *(_QWORD *)v70 = &v79;
      LOBYTE(v6) = 1;
      ppv = (LPVOID *)v70;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v6,
        3,
        ": {}");
    }
    v7 = 801;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    if ( v80.vt )
    {
      VariantClear(&v80);
      v80.vt = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
      v76 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
LABEL_21:
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return v5;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v79 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update specified");
      *(_QWORD *)v70 = &v79;
      LOBYTE(v8) = 1;
      ppv = (LPVOID *)v70;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v8,
        3,
        ": {}");
    }
    v7 = 802;
    goto LABEL_9;
  }
  v10 = operator new(0x40u);
  *(_QWORD *)v70 = v10;
  v10[1] = &CCbsStringArray::`vbtable';
  *v10 = &CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'};
  v10[7] = &CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `IDownloadProgressChangedCallback'};
  v11 = *(int *)(v10[1] + 4LL);
  *(_DWORD *)((char *)v10 + v11 + 4) = v11 - 24;
  *v10 = &CUUPDownloadProgressCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'};
  v12 = v10[1];
  *((_DWORD *)v10 + 4) = 1;
  *(_QWORD *)((char *)v10 + *(int *)(v12 + 4) + 8) = &CUUPDownloadProgressCallBack::`vftable'{for `IDownloadProgressChangedCallback'};
  v13 = *(int *)(v10[1] + 4LL);
  *(_DWORD *)((char *)v10 + v13 + 4) = v13 - 48;
  *((_BYTE *)v10 + 24) = 0;
  *(_QWORD *)((char *)v10 + 28) = 0;
  v10[5] = 0;
  v14 = (char *)operator new(0x30u);
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = 0;
  *((_QWORD *)v14 + 4) = 0;
  *((_QWORD *)v14 + 1) = &CUUPDownloadCompleteCallBack::`vbtable';
  *(_QWORD *)v14 = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  *((_QWORD *)v14 + 5) = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'};
  v15 = *((_QWORD *)v14 + 1);
  v71[0] = v14;
  *(_DWORD *)&v14[*(int *)(v15 + 4) + 4] = *(_DWORD *)(v15 + 4) - 24;
  *(_QWORD *)v14 = &CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v16 = *((_QWORD *)v14 + 1);
  *((_DWORD *)v14 + 4) = 1;
  *(_QWORD *)&v14[*(int *)(v16 + 4) + 8] = &CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'};
  *(_DWORD *)&v14[*(int *)(*((_QWORD *)v14 + 1) + 4LL) + 4] = 0;
  *((_QWORD *)v14 + 3) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( *((_QWORD *)v14 + 3) )
    goto LABEL_197;
  *((_QWORD *)v14 + 3) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create event.");
      if ( LastError > 0 )
        v20 = (unsigned __int16)LastError | 0x80070000;
      else
        v20 = LastError;
      v79 = v20;
      LOBYTE(v19) = 1;
      *(_QWORD *)v69 = &v79;
      ppv = (LPVOID *)v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v19,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x80,
              (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
              (const char *)(unsigned int)LastError,
              (unsigned int)ppv);
      v22 = v21;
      if ( v21 < 0 )
      {
        v73 = v21;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to initialize complete callback");
          *(_QWORD *)v69 = &v73;
          LOBYTE(v23) = 1;
          ppva = v69;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v23,
            3,
            ": {}");
        }
        v24 = 810;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)(unsigned int)v22,
          (int)ppva);
        if ( v80.vt )
        {
          VariantClear(&v80);
          v80.vt = 0;
        }
        if ( v76 )
        {
          (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
          v76 = 0;
        }
        if ( v75 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
          v75 = 0;
        }
        if ( v77 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
          v77 = 0;
        }
        if ( v78 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          v78 = 0;
        }
        if ( v74 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
          v74 = 0;
        }
        v25 = &v14[*(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8];
        (*(void (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))(v25);
        v26 = (char *)v10 + *(int *)(v10[1] + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 16LL))(v26);
        if ( pvarg.vt )
          VariantClear(&pvarg);
        return (unsigned int)v22;
      }
    }
  }
  if ( v75 )
    goto LABEL_197;
  v27 = CoCreateInstance(
          &GUID_13639463_00db_4646_803d_528026140d88,
          0,
          1u,
          &GUID_07f7438c_7709_4ca5_b518_91279288134e,
          &v75);
  v22 = v27;
  if ( v27 < 0 )
  {
    v73 = v27;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create collection");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v28) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v28,
        3,
        ": {}");
    }
    v24 = 813;
    goto LABEL_36;
  }
  v29 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v75 + 96LL))(v75, a3, &v85);
  v22 = v29;
  if ( v29 < 0 )
  {
    v73 = v29;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to add update to collection");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v30) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v30,
        3,
        ": {}");
    }
    v24 = 815;
    goto LABEL_36;
  }
  v31 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*a1 + 112))(a1, v75);
  v22 = v31;
  if ( v31 < 0 )
  {
    v73 = v31;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to call put_updates on downloader");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v32) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v32,
        3,
        ": {}");
    }
    v24 = 817;
    goto LABEL_36;
  }
  v33 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*a3 + 104))(a3, v82);
  if ( v33 )
  {
    if ( v33 < 0 )
    {
      v35 = "WU:Failed to check whether psf is available.";
      goto LABEL_76;
    }
  }
  else
  {
    if ( v82[0] != -1 )
    {
      v36 = "WU: PSF is not available for the update.";
LABEL_73:
      LogAdapter::TraceInfo<>(v36);
      goto LABEL_77;
    }
    v34 = *a3;
    LOWORD(v79) = 0;
    v33 = (*(__int64 (__fastcall **)(__int64 *, int *))(v34 + 112))(a3, &v79);
    if ( v33 < 0 )
    {
      v35 = "WU: Failed to check whether PSF is preferred.";
LABEL_76:
      LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v33, v35);
      goto LABEL_77;
    }
    if ( !v33 )
    {
      if ( (_WORD)v79 == 0xFFFF )
        v36 = "WU: PSF is available and preferred for the update.";
      else
        v36 = "WU: PSF is available but not preferred for the update.";
      goto LABEL_73;
    }
  }
LABEL_77:
  if ( v76 )
    goto LABEL_197;
  v37 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*a1)(
          a1,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v76);
  v22 = v37;
  if ( v37 < 0 )
  {
    v73 = v37;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v38) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v38,
        3,
        ": {}");
    }
    v24 = 856;
    goto LABEL_36;
  }
  v80.vt = 8;
  v80.llVal = (LONGLONG)SysAllocString(L"{\"ModuleID\" : \"CurrentVersionScan\"}");
  if ( !v80.llVal )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
    if ( v80.vt )
    {
      VariantClear(&v80);
      v80.vt = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
      v76 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    v39 = &v14[*(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v39 + 16LL))(v39);
    v40 = *(int *)(v10[1] + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)((char *)v10 + v40 + 8) + 16LL))((__int64)v10 + v40 + 8);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return 2147942414LL;
  }
  v41 = *v76;
  v72 = v80;
  v22 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v41 + 32))(v76, 196621, &v72);
  if ( v22 < 0 )
  {
    v73 = v22;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to set scan current product version only");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v42) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v42,
        3,
        ": {}");
    }
    v24 = 862;
    goto LABEL_36;
  }
  if ( v74 )
    goto LABEL_197;
  v43 = *a1;
  v44 = v10[1];
  v45 = &v14[*(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8];
  v72 = pvarg;
  ppva = (unsigned int *)&v74;
  v46 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *, VARIANTARG *))(v43 + 120))(
          a1,
          (__int64)v10 + *(int *)(v44 + 4) + 8,
          v45,
          &v72);
  v22 = v46;
  if ( v46 < 0 )
  {
    v73 = v46;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed calling begin download");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v47) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v47,
        3,
        ": {}");
    }
    v24 = 867;
    goto LABEL_36;
  }
  v48 = v83;
  while ( 1 )
  {
    if ( !*((_BYTE *)v10 + 24) && v48 > 0xDBBA0 || *((int *)v10 + 8) < 4 && v48 > 0x2932E0 )
    {
      CancelDownload(v74, a1, 0);
      v50 = -2145124319;
      v73 = -2145124319;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<unsigned long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Timed out waiting on WU download for {} milliseconds.",
          &v83);
        *(_QWORD *)v69 = &v73;
        LOBYTE(v51) = 1;
        ppva = v69;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v51,
          3,
          ": {}");
      }
      v52 = 882;
LABEL_118:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v52,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v50,
        (int)ppva);
      if ( v80.vt )
      {
        VariantClear(&v80);
        v80.vt = 0;
      }
      if ( v76 )
      {
        (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
        v76 = 0;
      }
      if ( v75 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
        v75 = 0;
      }
      if ( v77 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        v77 = 0;
      }
      if ( v78 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      if ( v74 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      v53 = &v14[*(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v53 + 16LL))(v53);
      v54 = *(int *)(v10[1] + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)((char *)v10 + v54 + 8) + 16LL))((__int64)v10 + v54 + 8);
      goto LABEL_131;
    }
    v49 = WaitForSingleObject(*((HANDLE *)v14 + 3), 0x7D0u);
    if ( !v49 )
      break;
    if ( v49 != 258 )
    {
      v50 = -2147467259;
      v73 = -2147467259;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to query status of event, assuming failure.");
        *(_QWORD *)v69 = &v73;
        LOBYTE(v55) = 1;
        ppva = v69;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v55,
          3,
          ": {}");
      }
      v52 = 911;
      goto LABEL_118;
    }
    v48 = v83 + 2000;
    v83 += 2000;
  }
  v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 80LL))(v74);
  if ( v56 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v56, "DWLD: Failed to call download job cleanup");
  if ( v78 )
    goto LABEL_197;
  v57 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*a1 + 136))(a1, v74, &v78);
  v50 = v57;
  if ( v57 < 0 )
  {
    v73 = v57;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to call end download");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v58) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v58,
        3,
        ": {}");
    }
    v59 = 935;
    goto LABEL_144;
  }
  if ( v77 )
  {
LABEL_197:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18026D9A8LL);
  }
  v62 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v78 + 72LL))(v78, 0, &v77);
  v50 = v62;
  if ( v62 < 0 )
  {
    v73 = v62;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to get update result");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v63) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v63,
        3,
        ": {}");
    }
    v59 = 942;
    goto LABEL_144;
  }
  v64 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v77 + 56LL))(v77, &v84);
  v50 = v64;
  if ( v64 >= 0 )
  {
    v5 = v84;
    if ( v84 < 0 )
    {
      v79 = v84;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        v71[1] = &v84;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Download failed with {}");
        *(_QWORD *)v69 = &v79;
        LOBYTE(v66) = 1;
        ppva = v69;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v66,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B2,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v5,
        (int)ppva);
      if ( v80.vt )
      {
        VariantClear(&v80);
        v80.vt = 0;
      }
      if ( v76 )
      {
        (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
        v76 = 0;
      }
      if ( v75 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
        v75 = 0;
      }
      if ( v77 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        v77 = 0;
      }
      if ( v78 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      if ( v74 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v71);
      Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v70);
      goto LABEL_21;
    }
    if ( v80.vt )
    {
      VariantClear(&v80);
      v80.vt = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
      v76 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v71);
    Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v70);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return 0;
  }
  else
  {
    v73 = v64;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: Failed to get download hresult");
      *(_QWORD *)v69 = &v73;
      LOBYTE(v65) = 1;
      ppva = v69;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v65,
        3,
        ": {}");
    }
    v59 = 944;
LABEL_144:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v59,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v50,
      (int)ppva);
    if ( v80.vt )
    {
      VariantClear(&v80);
      v80.vt = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
      v76 = 0;
    }
    if ( v75 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
      v75 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    v60 = &v14[*(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v60 + 16LL))(v60);
    v61 = (char *)v10 + *(int *)(v10[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v61 + 16LL))(v61);
LABEL_131:
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return v50;
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
