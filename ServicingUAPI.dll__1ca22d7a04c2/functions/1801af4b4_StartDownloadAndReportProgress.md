# StartDownloadAndReportProgress

- ea: `0x1801af4b4`
- end: `0x1801b0663`
- name: `StartDownloadAndReportProgress`
- size: `4527`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801b164c`

## callees

- `0x1800031d0`
- `0x180006198`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18001b9e4`
- `0x1800296a4`
- `0x180036228`
- `0x1801acb3c`
- `0x1801acdd8`
- `0x1801af4b4`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801af83b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801af83b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801af80c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801af80c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801aff49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801aff49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801afa4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801afa4a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801afcb4`
- `OLEAUT32!__imp_SysAllocString` at `0x1801afcb4`
- `OLEAUT32!__imp_VariantInit` at `0x1801af4f9`
- `OLEAUT32!__imp_VariantInit` at `0x1801af525`
- `OLEAUT32!__imp_VariantInit` at `0x1801af4f9`
- `OLEAUT32!__imp_VariantInit` at `0x1801af525`
- `OLEAUT32!__imp_VariantClear` at `0x1801af616`
- `OLEAUT32!__imp_VariantClear` at `0x1801af6af`
- `OLEAUT32!__imp_VariantClear` at `0x1801af93d`
- `OLEAUT32!__imp_VariantClear` at `0x1801afa0c`
- `OLEAUT32!__imp_VariantClear` at `0x1801afcf4`
- `OLEAUT32!__imp_VariantClear` at `0x1801afdc3`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0034`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0103`
- `OLEAUT32!__imp_VariantClear` at `0x1801b029f`
- `OLEAUT32!__imp_VariantClear` at `0x1801b04e1`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0598`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0645`
- `OLEAUT32!__imp_VariantClear` at `0x1801af616`
- `OLEAUT32!__imp_VariantClear` at `0x1801af6af`
- `OLEAUT32!__imp_VariantClear` at `0x1801af93d`
- `OLEAUT32!__imp_VariantClear` at `0x1801afa0c`
- `OLEAUT32!__imp_VariantClear` at `0x1801afcf4`
- `OLEAUT32!__imp_VariantClear` at `0x1801afdc3`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0034`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0103`
- `OLEAUT32!__imp_VariantClear` at `0x1801b029f`
- `OLEAUT32!__imp_VariantClear` at `0x1801b04e1`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0598`
- `OLEAUT32!__imp_VariantClear` at `0x1801b0645`

## string_xrefs

- `0x1801af856`: `Failed to create event.`
- `0x1801af5fc`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801af826`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x1801af557`: `No update downloader specified`
- `0x1801af5b7`: `No update specified`
- `0x1801afbf0`: `WU: PSF is available and preferred for the update.`
- `0x1801afc02`: `WU: PSF is not available for the update.`
- `0x1801afbf9`: `WU: PSF is available but not preferred for the update.`
- `0x1801afa6f`: `Failed to create collection`
- `0x1801af8e2`: `Failed to initialize complete callback`
- `0x1801afb59`: `Failed to call put_updates on downloader`
- `0x1801afae6`: `Failed to add update to collection`
- `0x1801b03a3`: `DWLD: Failed to get update result`

## pseudocode

```c
__int64 __fastcall StartDownloadAndReportProgress(__int64 *a1, OLECHAR *a2, __int64 *a3, __int64 a4)
{
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  bool v11; // zf
  _QWORD *v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  char *v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rax
  HANDLE EventW; // rax
  signed int LastError; // r15d
  __int64 v22; // rdx
  unsigned int v23; // eax
  int v24; // eax
  unsigned int v25; // r15d
  __int64 v26; // rdx
  __int64 v27; // rdx
  char *v28; // rcx
  char *v29; // rcx
  HRESULT v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rdx
  __int64 *v36; // r15
  int v37; // eax
  __int64 v38; // rax
  const char *v39; // r8
  const char *v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  char *v43; // rcx
  char *v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r10
  __int64 v48; // rax
  char *v49; // r8
  int v50; // eax
  __int64 v51; // rdx
  unsigned int v52; // eax
  DWORD v53; // eax
  int v54; // eax
  __int64 v55; // r8
  unsigned int v56; // r12d
  __int64 v57; // rdx
  __int64 v58; // rdx
  char *v59; // rcx
  char *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rdx
  int v63; // eax
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rdx
  int v67; // eax
  __int64 v68; // rdx
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-C1h]
  LPVOID *ppva; // [rsp+20h] [rbp-C1h]
  OLECHAR *psz; // [rsp+30h] [rbp-B1h] BYREF
  unsigned int v75[2]; // [rsp+38h] [rbp-A9h] BYREF
  int v76[2]; // [rsp+40h] [rbp-A1h] BYREF
  char *v77; // [rsp+48h] [rbp-99h] BYREF
  VARIANTARG v78; // [rsp+50h] [rbp-91h] BYREF
  __int64 v79; // [rsp+70h] [rbp-71h] BYREF
  LPVOID v80; // [rsp+78h] [rbp-69h] BYREF
  __int64 *v81; // [rsp+80h] [rbp-61h] BYREF
  __int64 v82; // [rsp+88h] [rbp-59h] BYREF
  __int64 v83; // [rsp+90h] [rbp-51h] BYREF
  __int64 *v84; // [rsp+98h] [rbp-49h] BYREF
  int v85; // [rsp+A0h] [rbp-41h] BYREF
  VARIANTARG v86; // [rsp+A8h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-21h] BYREF
  __int16 v88[2]; // [rsp+D8h] [rbp-9h] BYREF
  unsigned int v89; // [rsp+DCh] [rbp-5h] BYREF
  int v90; // [rsp+E0h] [rbp-1h] BYREF
  int v91; // [rsp+E4h] [rbp+3h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  psz = a2;
  v84 = a3;
  v88[0] = 0;
  VariantInit(&pvarg);
  v89 = 0;
  v90 = 0;
  v79 = 0;
  v83 = 0;
  v82 = 0;
  v80 = 0;
  v81 = 0;
  VariantInit(&v86);
  v91 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    v85 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update downloader specified");
      *(_QWORD *)v76 = &v85;
      LOBYTE(v8) = 1;
      ppv = (LPVOID *)v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v8,
        3,
        ": {}");
    }
    v9 = 801;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    if ( v86.vt )
    {
      VariantClear(&v86);
      v86.vt = 0;
    }
    if ( v81 )
    {
      (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
      v81 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      v82 = 0;
    }
    if ( v83 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      v83 = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      v79 = 0;
    }
    v11 = pvarg.vt == 0;
    goto LABEL_22;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    v85 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No update specified");
      *(_QWORD *)v76 = &v85;
      LOBYTE(v10) = 1;
      ppv = (LPVOID *)v76;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {}");
    }
    v9 = 802;
    goto LABEL_9;
  }
  v13 = operator new(0x40u);
  v13[1] = CCbsStringArray::`vbtable';
  *v13 = &CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'};
  v13[7] = &CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `IDownloadProgressChangedCallback'};
  v14 = *(int *)(v13[1] + 4LL);
  *(_DWORD *)((char *)v13 + v14 + 4) = v14 - 24;
  *v13 = &CUUPDownloadProgressCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'};
  v15 = v13[1];
  *((_DWORD *)v13 + 4) = 1;
  *(_QWORD *)((char *)v13 + *(int *)(v15 + 4) + 8) = &CUUPDownloadProgressCallBack::`vftable'{for `IDownloadProgressChangedCallback'};
  v16 = *(int *)(v13[1] + 4LL);
  *(_DWORD *)((char *)v13 + v16 + 4) = v16 - 48;
  *((_BYTE *)v13 + 24) = 0;
  *(_QWORD *)((char *)v13 + 28) = 0;
  v13[5] = 0;
  if ( a4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    v13[5] = a4;
  }
  *(_QWORD *)v76 = v13;
  v17 = (char *)operator new(0x30u);
  *((_QWORD *)v17 + 2) = 0;
  *((_QWORD *)v17 + 3) = 0;
  *((_QWORD *)v17 + 4) = 0;
  *((_QWORD *)v17 + 1) = &CUUPDownloadCompleteCallBack::`vbtable';
  *(_QWORD *)v17 = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  *((_QWORD *)v17 + 5) = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'};
  v18 = *((_QWORD *)v17 + 1);
  v77 = v17;
  *(_DWORD *)&v17[*(int *)(v18 + 4) + 4] = *(_DWORD *)(v18 + 4) - 24;
  *(_QWORD *)v17 = &CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v19 = *((_QWORD *)v17 + 1);
  *((_DWORD *)v17 + 4) = 1;
  *(_QWORD *)&v17[*(int *)(v19 + 4) + 8] = &CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'};
  *(_DWORD *)&v17[*(int *)(*((_QWORD *)v17 + 1) + 4LL) + 4] = 0;
  *((_QWORD *)v17 + 3) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( *((_QWORD *)v17 + 3) )
    goto LABEL_206;
  *((_QWORD *)v17 + 3) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create event.");
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      else
        v23 = LastError;
      v85 = v23;
      LOBYTE(v22) = 1;
      *(_QWORD *)v75 = &v85;
      ppv = (LPVOID *)v75;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x80,
              (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
              (const char *)(unsigned int)LastError,
              (unsigned int)ppv);
      v25 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v84) = v24;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to initialize complete callback");
          *(_QWORD *)v75 = &v84;
          LOBYTE(v26) = 1;
          ppva = (LPVOID *)v75;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v26,
            3,
            ": {}");
        }
        v27 = 810;
LABEL_39:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v25,
          (int)ppva);
        if ( v86.vt )
        {
          VariantClear(&v86);
          v86.vt = 0;
        }
        if ( v81 )
        {
          (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
          v81 = 0;
        }
        if ( v80 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
          v80 = 0;
        }
        if ( v82 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
          v82 = 0;
        }
        if ( v83 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
          v83 = 0;
        }
        if ( v79 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
          v79 = 0;
        }
        goto LABEL_51;
      }
    }
  }
  if ( v80 )
  {
LABEL_206:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801B0662LL);
  }
  v30 = CoCreateInstance(
          &GUID_13639463_00db_4646_803d_528026140d88,
          0,
          1u,
          &GUID_07f7438c_7709_4ca5_b518_91279288134e,
          &v80);
  v25 = v30;
  if ( v30 < 0 )
  {
    LODWORD(v84) = v30;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create collection");
      *(_QWORD *)v75 = &v84;
      LOBYTE(v31) = 1;
      ppva = (LPVOID *)v75;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v31,
        3,
        ": {}");
    }
    v27 = 813;
    goto LABEL_39;
  }
  v32 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v80 + 96LL))(v80, v84, &v91);
  v25 = v32;
  if ( v32 < 0 )
  {
    LODWORD(v84) = v32;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to add update to collection");
      *(_QWORD *)v75 = &v84;
      LOBYTE(v33) = 1;
      ppva = (LPVOID *)v75;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v33,
        3,
        ": {}");
    }
    v27 = 815;
    goto LABEL_39;
  }
  v34 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*a1 + 112))(a1, v80);
  v25 = v34;
  if ( v34 < 0 )
  {
    LODWORD(v84) = v34;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to call put_updates on downloader");
      *(_QWORD *)v75 = &v84;
      LOBYTE(v35) = 1;
      ppva = (LPVOID *)v75;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v35,
        3,
        ": {}");
    }
    v27 = 817;
    goto LABEL_39;
  }
  v36 = v84;
  v37 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v84 + 104))(v84, v88);
  if ( v37 )
  {
    if ( v37 < 0 )
    {
      v39 = "WU:Failed to check whether psf is available.";
      goto LABEL_79;
    }
  }
  else
  {
    if ( v88[0] != -1 )
    {
      v40 = "WU: PSF is not available for the update.";
LABEL_76:
      LogAdapter::TraceInfo<>(v40);
      goto LABEL_80;
    }
    v38 = *v36;
    LOWORD(v85) = 0;
    v37 = (*(__int64 (__fastcall **)(__int64 *, int *))(v38 + 112))(v36, &v85);
    if ( v37 < 0 )
    {
      v39 = "WU: Failed to check whether PSF is preferred.";
LABEL_79:
      LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v37, v39);
      goto LABEL_80;
    }
    if ( !v37 )
    {
      if ( (_WORD)v85 == 0xFFFF )
        v40 = "WU: PSF is available and preferred for the update.";
      else
        v40 = "WU: PSF is available but not preferred for the update.";
      goto LABEL_76;
    }
  }
LABEL_80:
  if ( v81 )
    goto LABEL_206;
  v41 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*a1)(
          a1,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v81);
  v25 = v41;
  if ( v41 < 0 )
  {
    LODWORD(v84) = v41;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      *(_QWORD *)v75 = &v84;
      LOBYTE(v42) = 1;
      ppva = (LPVOID *)v75;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v42,
        3,
        ": {}");
    }
    v27 = 856;
    goto LABEL_39;
  }
  v86.vt = 8;
  v86.llVal = (LONGLONG)SysAllocString(psz);
  if ( !v86.llVal )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
    if ( v86.vt )
    {
      VariantClear(&v86);
      v86.vt = 0;
    }
    if ( v81 )
    {
      (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
      v81 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      v82 = 0;
    }
    if ( v83 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      v83 = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      v79 = 0;
    }
    v43 = &v17[*(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v43 + 16LL))(v43);
    v44 = (char *)v13 + *(int *)(v13[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v44 + 16LL))(v44);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return 2147942414LL;
  }
  v45 = *v81;
  v78 = v86;
  v25 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v45 + 32))(v81, 196621, &v78);
  if ( (v25 & 0x80000000) != 0 )
  {
    LODWORD(v84) = v25;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to set scan current product version only");
      psz = (OLECHAR *)&v84;
      LOBYTE(v46) = 1;
      ppva = (LPVOID *)&psz;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v46,
        3,
        ": {}");
    }
    v27 = 862;
    goto LABEL_39;
  }
  if ( v79 )
    goto LABEL_206;
  v47 = *a1;
  v48 = v13[1];
  v49 = &v17[*(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8];
  v78 = pvarg;
  ppva = (LPVOID *)&v79;
  v50 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *, VARIANTARG *))(v47 + 120))(
          a1,
          (__int64)v13 + *(int *)(v48 + 4) + 8,
          v49,
          &v78);
  v25 = v50;
  if ( v50 < 0 )
  {
    LODWORD(v84) = v50;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed calling begin download");
      psz = (OLECHAR *)&v84;
      LOBYTE(v51) = 1;
      ppva = (LPVOID *)&psz;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v51,
        3,
        ": {}");
    }
    v27 = 867;
    goto LABEL_39;
  }
LABEL_110:
  v52 = v89;
  while ( 1 )
  {
    if ( !*((_BYTE *)v13 + 24) && v52 > 0xDBBA0 || *((int *)v13 + 8) < 4 && v52 > 0x2932E0 )
    {
      CancelDownload(v79, a1, 0);
      v56 = -2145124319;
      LODWORD(v84) = -2145124319;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<unsigned long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "DWLD: Timed out waiting on WU download for {} milliseconds.",
          &v89);
        psz = (OLECHAR *)&v84;
        LOBYTE(v57) = 1;
        ppva = (LPVOID *)&psz;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v57,
          3,
          ": {}");
      }
      v58 = 882;
      goto LABEL_124;
    }
    v53 = WaitForSingleObject(*((HANDLE *)v17 + 3), 0x7D0u);
    if ( !v53 )
      break;
    if ( v53 != 258 )
    {
      v56 = -2147467259;
      LODWORD(v84) = -2147467259;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to query status of event, assuming failure.");
        psz = (OLECHAR *)&v84;
        LOBYTE(v62) = 1;
        ppva = (LPVOID *)&psz;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v62,
          3,
          ": {}");
      }
      v58 = 911;
      goto LABEL_124;
    }
    v52 = v89 + 2000;
    v89 += 2000;
    if ( a4 )
    {
      v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a4 + 40LL))(
              a4,
              *((unsigned int *)v13 + 7),
              100);
      if ( v54 == -2146498527 )
      {
        LOBYTE(v55) = 1;
LABEL_140:
        CancelDownload(v79, a1, v55);
        v56 = -2147467260;
        LODWORD(v84) = -2147467260;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "DWLD: Caller cancelled the download operation");
          psz = (OLECHAR *)&v84;
          LOBYTE(v61) = 1;
          ppva = (LPVOID *)&psz;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v61,
            3,
            ": {}");
        }
        v58 = 905;
LABEL_124:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v58,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v56,
          (int)ppva);
        if ( v86.vt )
        {
          VariantClear(&v86);
          v86.vt = 0;
        }
        if ( v81 )
        {
          (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
          v81 = 0;
        }
        if ( v80 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
          v80 = 0;
        }
        if ( v82 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
          v82 = 0;
        }
        if ( v83 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
          v83 = 0;
        }
        if ( v79 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
          v79 = 0;
        }
        v59 = &v17[*(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8];
        (*(void (__fastcall **)(char *))(*(_QWORD *)v59 + 16LL))(v59);
        v60 = (char *)v13 + *(int *)(v13[1] + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v60 + 16LL))(v60);
        if ( pvarg.vt )
          VariantClear(&pvarg);
        return v56;
      }
      if ( v54 == -2146498528 )
      {
        LOBYTE(v55) = 0;
        goto LABEL_140;
      }
      goto LABEL_110;
    }
  }
  v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 80LL))(v79);
  if ( v63 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v63, "DWLD: Failed to call download job cleanup");
  if ( v83 )
    goto LABEL_206;
  v64 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*a1 + 136))(a1, v79, &v83);
  v25 = v64;
  if ( v64 < 0 )
  {
    LODWORD(v84) = v64;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to call end download");
      psz = (OLECHAR *)&v84;
      LOBYTE(v65) = 1;
      ppva = (LPVOID *)&psz;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v65,
        3,
        ": {}");
    }
    v66 = 935;
    goto LABEL_153;
  }
  if ( v82 )
    goto LABEL_206;
  v67 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v83 + 72LL))(v83, 0, &v82);
  v25 = v67;
  if ( v67 < 0 )
  {
    LODWORD(v84) = v67;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to get update result");
      psz = (OLECHAR *)&v84;
      LOBYTE(v68) = 1;
      ppva = (LPVOID *)&psz;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v68,
        3,
        ": {}");
    }
    v66 = 942;
    goto LABEL_153;
  }
  v69 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v82 + 56LL))(v82, &v90);
  v25 = v69;
  if ( v69 >= 0 )
  {
    v7 = v90;
    if ( v90 >= 0 )
    {
      if ( v86.vt )
      {
        VariantClear(&v86);
        v86.vt = 0;
      }
      if ( v81 )
      {
        (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
        v81 = 0;
      }
      if ( v80 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
        v80 = 0;
      }
      if ( v82 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
        v82 = 0;
      }
      if ( v83 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        v83 = 0;
      }
      if ( v79 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        v79 = 0;
      }
      Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(&v77);
      Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v76);
      if ( pvarg.vt )
        VariantClear(&pvarg);
      return 0;
    }
    v85 = v90;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      *(_QWORD *)v75 = &v90;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "DWLD: Download failed with {}");
      psz = (OLECHAR *)&v85;
      LOBYTE(v71) = 1;
      ppva = (LPVOID *)&psz;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v71,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v7,
      (int)ppva);
    if ( v86.vt )
    {
      VariantClear(&v86);
      v86.vt = 0;
    }
    if ( v81 )
    {
      (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
      v81 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      v82 = 0;
    }
    if ( v83 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      v83 = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      v79 = 0;
    }
    Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(&v77);
    Windows::AutoComPtr<CUUPDownloadProgressCallBack>::~AutoComPtr<CUUPDownloadProgressCallBack>(v76);
    v11 = pvarg.vt == 0;
LABEL_22:
    if ( !v11 )
      VariantClear(&pvarg);
    return v7;
  }
  LODWORD(v84) = v69;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "DWLD: Failed to get download hresult");
    psz = (OLECHAR *)&v84;
    LOBYTE(v70) = 1;
    ppva = (LPVOID *)&psz;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v70,
      3,
      ": {}");
  }
  v66 = 944;
LABEL_153:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v66,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)v25,
    (int)ppva);
  if ( v86.vt )
  {
    VariantClear(&v86);
    v86.vt = 0;
  }
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
    v81 = 0;
  }
  if ( v80 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
    v80 = 0;
  }
  if ( v82 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
    v82 = 0;
  }
  if ( v83 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    v83 = 0;
  }
  if ( v79 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    v79 = 0;
  }
LABEL_51:
  v28 = &v17[*(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v28 + 16LL))(v28);
  v29 = (char *)v13 + *(int *)(v13[1] + 4LL) + 8;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
  if ( pvarg.vt )
    VariantClear(&pvarg);
  return v25;
}

```

## disassembly

```asm
0x1801af4b4  push    rbp
0x1801af4b6  push    rbx
0x1801af4b7  push    rsi
0x1801af4b8  push    rdi
0x1801af4b9  push    r12
0x1801af4bb  push    r13
0x1801af4bd  push    r14
0x1801af4bf  push    r15
0x1801af4c1  lea     rbp, [rsp-17h]
0x1801af4c6  sub     rsp, 0F8h
0x1801af4cd  mov     rax, cs:__security_cookie
0x1801af4d4  xor     rax, rsp
0x1801af4d7  mov     [rbp+4Fh+var_48], rax
0x1801af4db  mov     rbx, r8
0x1801af4de  mov     [rsp+130h+psz], rdx
0x1801af4e3  mov     r12, rcx
0x1801af4e6  mov     [rbp+4Fh+var_98], rbx
0x1801af4ea  xor     r15d, r15d
0x1801af4ed  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x1801af4f1  mov     [rbp+4Fh+var_58], r15w
0x1801af4f6  mov     r13, r9
0x1801af4f9  call    cs:__imp_VariantInit
0x1801af500  nop     dword ptr [rax+rax+00h]
0x1801af505  lea     rcx, [rbp+4Fh+var_88]; pvarg
0x1801af509  mov     [rbp+4Fh+var_54], r15d
0x1801af50d  mov     dword ptr [rbp+4Fh+var_50], r15d
0x1801af511  mov     [rbp+4Fh+var_C0], r15
0x1801af515  mov     [rbp+4Fh+var_A0], r15
0x1801af519  mov     [rbp+4Fh+var_A8], r15
0x1801af51d  mov     [rbp+4Fh+var_B8], r15
0x1801af521  mov     [rbp+4Fh+var_B0], r15
0x1801af525  call    cs:__imp_VariantInit
0x1801af52c  nop     dword ptr [rax+rax+00h]
0x1801af531  mov     dword ptr [rbp+4Fh+var_50+4], r15d
0x1801af535  test    r12, r12
0x1801af538  jnz     short loc_1801AF595
0x1801af53a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af541  mov     esi, 80070057h
0x1801af546  mov     [rbp+4Fh+var_90], esi
0x1801af549  test    rcx, rcx
0x1801af54c  jz      short loc_1801AF58E
0x1801af54e  lea     ebx, [r15+3]
0x1801af552  xor     edx, edx
0x1801af554  mov     r8d, ebx
0x1801af557  lea     r9, aNoUpdateDownlo; "No update downloader specified"
0x1801af55e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801af563  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af56a  lea     rax, [rbp+4Fh+var_90]
0x1801af56e  mov     qword ptr [rsp+130h+var_F0], rax
0x1801af573  lea     r9, asc_1801CAFB4; ": {}"
0x1801af57a  lea     rax, [rsp+130h+var_F0]
0x1801af57f  mov     r8d, ebx
0x1801af582  mov     dl, 1
0x1801af584  mov     [rsp+130h+ppv], rax
0x1801af589  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801af58e  mov     edx, 321h
0x1801af593  jmp     short loc_1801AF5F8
0x1801af595  test    rbx, rbx
0x1801af598  jnz     loc_1801AF6DE
0x1801af59e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af5a5  mov     esi, 80070057h
0x1801af5aa  mov     [rbp+4Fh+var_90], esi
0x1801af5ad  test    rcx, rcx
0x1801af5b0  jz      short loc_1801AF5F3
0x1801af5b2  mov     ebx, 3
0x1801af5b7  lea     r9, aNoUpdateSpecif; "No update specified"
0x1801af5be  mov     r8d, ebx
0x1801af5c1  xor     edx, edx
0x1801af5c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801af5c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af5cf  lea     rax, [rbp+4Fh+var_90]
0x1801af5d3  mov     qword ptr [rsp+130h+var_F0], rax
0x1801af5d8  lea     r9, asc_1801CAFB4; ": {}"
0x1801af5df  lea     rax, [rsp+130h+var_F0]
0x1801af5e4  mov     r8d, ebx
0x1801af5e7  mov     dl, 1
0x1801af5e9  mov     [rsp+130h+ppv], rax; int
0x1801af5ee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801af5f3  mov     edx, 322h; void *
0x1801af5f8  mov     rcx, [rbp+57h]; this
0x1801af5fc  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801af603  mov     r9d, esi; char *
0x1801af606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801af60b  cmp     word ptr [rbp+4Fh+var_88], r15w
0x1801af610  jz      short loc_1801AF627
0x1801af612  lea     rcx, [rbp+4Fh+var_88]; pvarg
0x1801af616  call    cs:__imp_VariantClear
0x1801af61d  nop     dword ptr [rax+rax+00h]
0x1801af622  mov     word ptr [rbp+4Fh+var_88], r15w
0x1801af627  mov     rcx, [rbp+4Fh+var_B0]
0x1801af62b  test    rcx, rcx
0x1801af62e  jz      short loc_1801AF640
0x1801af630  mov     rax, [rcx]
0x1801af633  mov     rax, [rax+10h]
0x1801af637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af63c  mov     [rbp+4Fh+var_B0], r15
0x1801af640  mov     rcx, [rbp+4Fh+var_B8]
0x1801af644  test    rcx, rcx
0x1801af647  jz      short loc_1801AF659
0x1801af649  mov     rax, [rcx]
0x1801af64c  mov     rax, [rax+10h]
0x1801af650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af655  mov     [rbp+4Fh+var_B8], r15
0x1801af659  mov     rcx, [rbp+4Fh+var_A8]
0x1801af65d  test    rcx, rcx
0x1801af660  jz      short loc_1801AF672
0x1801af662  mov     rax, [rcx]
0x1801af665  mov     rax, [rax+10h]
0x1801af669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af66e  mov     [rbp+4Fh+var_A8], r15
0x1801af672  mov     rcx, [rbp+4Fh+var_A0]
0x1801af676  test    rcx, rcx
0x1801af679  jz      short loc_1801AF68B
0x1801af67b  mov     rax, [rcx]
0x1801af67e  mov     rax, [rax+10h]
0x1801af682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af687  mov     [rbp+4Fh+var_A0], r15
0x1801af68b  mov     rcx, [rbp+4Fh+var_C0]
0x1801af68f  test    rcx, rcx
0x1801af692  jz      short loc_1801AF6A4
0x1801af694  mov     rax, [rcx]
0x1801af697  mov     rax, [rax+10h]
0x1801af69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af6a0  mov     [rbp+4Fh+var_C0], r15
0x1801af6a4  cmp     word ptr [rbp+4Fh+pvarg], r15w
0x1801af6a9  jz      short loc_1801AF6BB
0x1801af6ab  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x1801af6af  call    cs:__imp_VariantClear
0x1801af6b6  nop     dword ptr [rax+rax+00h]
0x1801af6bb  mov     eax, esi
0x1801af6bd  mov     rcx, [rbp+4Fh+var_48]
0x1801af6c1  xor     rcx, rsp; StackCookie
0x1801af6c4  call    __security_check_cookie
0x1801af6c9  add     rsp, 0F8h
0x1801af6d0  pop     r15
0x1801af6d2  pop     r14
0x1801af6d4  pop     r13
0x1801af6d6  pop     r12
0x1801af6d8  pop     rdi
0x1801af6d9  pop     rsi
0x1801af6da  pop     rbx
0x1801af6db  pop     rbp
0x1801af6dc  retn
0x1801af6de  mov     ecx, 40h ; '@'; Size
0x1801af6e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801af6e8  mov     rsi, rax
0x1801af6eb  lea     rax, ??_8CCbsStringArray@@7B@; const CCbsStringArray::`vbtable'
0x1801af6f2  mov     [rsi+8], rax
0x1801af6f6  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadProgressChangedCallback@@$$V@@6B0@@; const CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'}
0x1801af6fd  mov     [rsi], rax
0x1801af700  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadProgressChangedCallback@@$$V@@6BIDownloadProgressChangedCallback@@@; const CCbsIUnknownImpl<IDownloadProgressChangedCallback,>::`vftable'{for `IDownloadProgressChangedCallback'}
0x1801af707  mov     [rsi+38h], rax
0x1801af70b  lea     rax, ??_7CUUPDownloadProgressCallBack@@6B?$CCbsIUnknownImpl@UIDownloadProgressChangedCallback@@$$V@@@; const CUUPDownloadProgressCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadProgressChangedCallback,>'}
0x1801af712  mov     rcx, [rsi+8]
0x1801af716  movsxd  rdx, dword ptr [rcx+4]
0x1801af71a  lea     r8d, [rdx-18h]
0x1801af71e  mov     [rdx+rsi+4], r8d
0x1801af723  mov     [rsi], rax
0x1801af726  mov     rax, [rsi+8]
0x1801af72a  mov     dword ptr [rsi+10h], 1
0x1801af731  movsxd  rcx, dword ptr [rax+4]
0x1801af735  lea     rax, ??_7CUUPDownloadProgressCallBack@@6BIDownloadProgressChangedCallback@@@; const CUUPDownloadProgressCallBack::`vftable'{for `IDownloadProgressChangedCallback'}
0x1801af73c  mov     [rcx+rsi+8], rax
0x1801af741  mov     rax, [rsi+8]
0x1801af745  movsxd  rcx, dword ptr [rax+4]
0x1801af749  lea     edx, [rcx-30h]
0x1801af74c  mov     [rcx+rsi+4], edx
0x1801af750  mov     [rsi+18h], r15b
0x1801af754  mov     [rsi+1Ch], r15
0x1801af758  mov     [rsi+28h], r15
0x1801af75c  test    r13, r13
0x1801af75f  jz      short loc_1801AF775
0x1801af761  mov     rax, [r13+0]
0x1801af765  mov     rcx, r13
0x1801af768  mov     rax, [rax+8]
0x1801af76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af771  mov     [rsi+28h], r13
0x1801af775  mov     ecx, 30h ; '0'; Size
0x1801af77a  mov     qword ptr [rsp+130h+var_F0], rsi
0x1801af77f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801af784  mov     r14, rax
0x1801af787  xor     r9d, r9d; lpName
0x1801af78a  mov     [rax+10h], r15
0x1801af78e  mov     [rax+18h], r15
0x1801af792  mov     [rax+20h], r15
0x1801af796  lea     rax, ??_8CUUPDownloadCompleteCallBack@@7B@; const CUUPDownloadCompleteCallBack::`vbtable'
0x1801af79d  mov     [r14+8], rax
0x1801af7a1  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6B0@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x1801af7a8  mov     [r14], rax
0x1801af7ab  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6BIDownloadCompletedCallback@@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'}
0x1801af7b2  mov     [r14+28h], rax
0x1801af7b6  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6B?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x1801af7bd  mov     rcx, [r14+8]
0x1801af7c1  mov     [rsp+130h+var_E8], r14
0x1801af7c6  movsxd  rdx, dword ptr [rcx+4]
0x1801af7ca  lea     r8d, [rdx-18h]
0x1801af7ce  mov     [rdx+r14+4], r8d
0x1801af7d3  xor     r8d, r8d; bInitialState
0x1801af7d6  mov     [r14], rax
0x1801af7d9  lea     edx, [r9+1]; bManualReset
0x1801af7dd  mov     rax, [r14+8]
0x1801af7e1  mov     dword ptr [r14+10h], 1
0x1801af7e9  movsxd  rcx, dword ptr [rax+4]
0x1801af7ed  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6BIDownloadCompletedCallback@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'}
0x1801af7f4  mov     [rcx+r14+8], rax
0x1801af7f9  mov     rax, [r14+8]
0x1801af7fd  movsxd  rcx, dword ptr [rax+4]
0x1801af801  mov     [rcx+r14+4], r15d
0x1801af806  xor     ecx, ecx; lpEventAttributes
0x1801af808  mov     [r14+18h], r15
0x1801af80c  call    cs:__imp_CreateEventW
0x1801af813  nop     dword ptr [rax+rax+00h]
0x1801af818  cmp     [r14+18h], r15
0x1801af81c  jnz     loc_1801B0658
0x1801af822  mov     [r14+18h], rax
0x1801af826  lea     rdi, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x1801af82d  mov     ebx, 3
0x1801af832  test    rax, rax
0x1801af835  jnz     loc_1801AFA23
0x1801af83b  call    cs:__imp_GetLastError
0x1801af842  nop     dword ptr [rax+rax+00h]
0x1801af847  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af84e  mov     r15d, eax
0x1801af851  test    rcx, rcx
0x1801af854  jz      short loc_1801AF8A8
0x1801af856  lea     r9, aFailedToCreate_24; "Failed to create event."
0x1801af85d  mov     r8d, ebx
0x1801af860  xor     edx, edx
0x1801af862  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801af867  test    r15d, r15d
0x1801af86a  jg      short loc_1801AF871
0x1801af86c  mov     eax, r15d
0x1801af86f  jmp     short loc_1801AF87A
0x1801af871  movzx   eax, r15w
0x1801af875  or      eax, 80070000h
0x1801af87a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af881  lea     r9, a0; ": {0}"
0x1801af888  mov     [rbp+4Fh+var_90], eax
0x1801af88b  mov     r8d, ebx
0x1801af88e  lea     rax, [rbp+4Fh+var_90]
0x1801af892  mov     dl, 1
0x1801af894  mov     qword ptr [rsp+130h+var_F8], rax
0x1801af899  lea     rax, [rsp+130h+var_F8]
0x1801af89e  mov     [rsp+130h+ppv], rax; unsigned int
0x1801af8a3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801af8a8  test    r15d, r15d
0x1801af8ab  jz      loc_1801AFA20
0x1801af8b1  mov     rcx, [rbp+57h]; this
0x1801af8b5  mov     r9d, r15d; char *
0x1801af8b8  mov     r8, rdi; unsigned int
0x1801af8bb  mov     edx, 80h; void *
0x1801af8c0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801af8c5  mov     r15d, eax
0x1801af8c8  test    eax, eax
0x1801af8ca  jns     loc_1801AFA20
0x1801af8d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af8d7  xor     r12d, r12d
0x1801af8da  mov     dword ptr [rbp+4Fh+var_98], eax
0x1801af8dd  test    rcx, rcx
0x1801af8e0  jz      short loc_1801AF91E
0x1801af8e2  lea     r9, aFailedToInitia_2; "Failed to initialize complete callback"
0x1801af8e9  mov     r8d, ebx
0x1801af8ec  xor     edx, edx
0x1801af8ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801af8f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801af8fa  lea     rax, [rbp+4Fh+var_98]
0x1801af8fe  mov     qword ptr [rsp+130h+var_F8], rax
0x1801af903  lea     r9, asc_1801CAFB4; ": {}"
0x1801af90a  lea     rax, [rsp+130h+var_F8]
0x1801af90f  mov     r8d, ebx
0x1801af912  mov     dl, 1
0x1801af914  mov     [rsp+130h+ppv], rax; int
0x1801af919  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801af91e  mov     edx, 32Ah; void *
0x1801af923  mov     rcx, [rbp+57h]; this
0x1801af927  mov     r9d, r15d; char *
0x1801af92a  mov     r8, rdi; unsigned int
0x1801af92d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801af932  cmp     word ptr [rbp+4Fh+var_88], r12w
0x1801af937  jz      short loc_1801AF94E
0x1801af939  lea     rcx, [rbp+4Fh+var_88]; pvarg
0x1801af93d  call    cs:__imp_VariantClear
0x1801af944  nop     dword ptr [rax+rax+00h]
0x1801af949  mov     word ptr [rbp+4Fh+var_88], r12w
0x1801af94e  mov     rcx, [rbp+4Fh+var_B0]
0x1801af952  test    rcx, rcx
0x1801af955  jz      short loc_1801AF967
0x1801af957  mov     rax, [rcx]
0x1801af95a  mov     rax, [rax+10h]
0x1801af95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af963  mov     [rbp+4Fh+var_B0], r12
0x1801af967  mov     rcx, [rbp+4Fh+var_B8]
0x1801af96b  test    rcx, rcx
0x1801af96e  jz      short loc_1801AF980
0x1801af970  mov     rax, [rcx]
0x1801af973  mov     rax, [rax+10h]
0x1801af977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af97c  mov     [rbp+4Fh+var_B8], r12
0x1801af980  mov     rcx, [rbp+4Fh+var_A8]
0x1801af984  test    rcx, rcx
  ... truncated ...
```
