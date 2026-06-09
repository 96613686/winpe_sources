# StartDownloadAndReportProgress

- ea: `0x18029de68`
- end: `0x18029ef95`
- name: `StartDownloadAndReportProgress`
- size: `4397`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18029fda0`

## callees

- `0x180010cc0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f19ec`
- `0x18029b8c0`
- `0x18029bb4c`
- `0x18029c9e4`
- `0x18029de68`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18029e87c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18029e87c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029e2a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029e2a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18029e606`
- `OLEAUT32!__imp_SysAllocString` at `0x18029e606`
- `OLEAUT32!__imp_VariantInit` at `0x18029dea9`
- `OLEAUT32!__imp_VariantInit` at `0x18029ded3`
- `OLEAUT32!__imp_VariantInit` at `0x18029dea9`
- `OLEAUT32!__imp_VariantInit` at `0x18029ded3`
- `OLEAUT32!__imp_VariantClear` at `0x18029dfbd`
- `OLEAUT32!__imp_VariantClear` at `0x18029e054`
- `OLEAUT32!__imp_VariantClear` at `0x18029e19b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e268`
- `OLEAUT32!__imp_VariantClear` at `0x18029e52b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e645`
- `OLEAUT32!__imp_VariantClear` at `0x18029e9c5`
- `OLEAUT32!__imp_VariantClear` at `0x18029ece8`
- `OLEAUT32!__imp_VariantClear` at `0x18029edb7`
- `OLEAUT32!__imp_VariantClear` at `0x18029edef`
- `OLEAUT32!__imp_VariantClear` at `0x18029eec3`
- `OLEAUT32!__imp_VariantClear` at `0x18029ef5a`
- `OLEAUT32!__imp_VariantClear` at `0x18029dfbd`
- `OLEAUT32!__imp_VariantClear` at `0x18029e054`
- `OLEAUT32!__imp_VariantClear` at `0x18029e19b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e268`
- `OLEAUT32!__imp_VariantClear` at `0x18029e52b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e645`
- `OLEAUT32!__imp_VariantClear` at `0x18029e9c5`
- `OLEAUT32!__imp_VariantClear` at `0x18029ece8`
- `OLEAUT32!__imp_VariantClear` at `0x18029edb7`
- `OLEAUT32!__imp_VariantClear` at `0x18029edef`
- `OLEAUT32!__imp_VariantClear` at `0x18029eec3`
- `OLEAUT32!__imp_VariantClear` at `0x18029ef5a`

## string_xrefs

- `0x18029df61`: `No update specified`
- `0x18029dfa4`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e182`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e511`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e623`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e9ab`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029edce`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029eea2`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e342`: `Failed to add update to collection`
- `0x18029e2ca`: `Failed to create collection`
- `0x18029e3b7`: `Failed to call put_updates on downloader`
- `0x18029e13d`: `Failed to initialize complete callback`
- `0x18029df03`: `No update downloader specified`
- `0x18029e464`: `WU: PSF is available but not preferred for the update.`
- `0x18029e45b`: `WU: PSF is available and preferred for the update.`
- `0x18029e46d`: `WU: PSF is not available for the update.`
- `0x18029ebb9`: `DWLD: Failed to get update result`

## pseudocode

```c
__int64 __fastcall StartDownloadAndReportProgress(__int64 *a1, OLECHAR *a2, __int64 *a3, struct IWULibCallback *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  bool v9; // zf
  CUUPDownloadProgressCallBack *v11; // rax
  CUUPDownloadProgressCallBack *v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // r13d
  __int64 v18; // rdx
  char *v19; // rcx
  char *v20; // rcx
  HRESULT v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rbx
  const char *v27; // rdx
  __int64 InitPointer; // rax
  int v29; // eax
  __int64 v30; // rdx
  char *v31; // rcx
  char *v32; // rcx
  char *v33; // rcx
  bool v34; // zf
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // r10
  __int64 v38; // rax
  char *v39; // r8
  int v40; // eax
  unsigned int v41; // eax
  DWORD v42; // eax
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rdx
  unsigned int v46; // eax
  __int64 (__fastcall *v47)(__int64 *, __int64, __int64); // rbx
  __int64 v48; // rax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  char *v52; // rcx
  char *v53; // rcx
  char *v54; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-A1h]
  int v56[2]; // [rsp+30h] [rbp-91h] BYREF
  int *v57; // [rsp+38h] [rbp-89h] BYREF
  VARIANTARG v58; // [rsp+40h] [rbp-81h] BYREF
  int v59; // [rsp+60h] [rbp-61h] BYREF
  __int64 v60; // [rsp+68h] [rbp-59h] BYREF
  LPVOID v61; // [rsp+70h] [rbp-51h] BYREF
  __int64 v62; // [rsp+78h] [rbp-49h] BYREF
  __int64 *v63; // [rsp+80h] [rbp-41h] BYREF
  __int64 v64; // [rsp+88h] [rbp-39h] BYREF
  OLECHAR *psz; // [rsp+90h] [rbp-31h] BYREF
  VARIANTARG v66; // [rsp+98h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-11h] BYREF
  __int16 v68[2]; // [rsp+C8h] [rbp+7h] BYREF
  unsigned int v69; // [rsp+CCh] [rbp+Bh] BYREF
  int v70; // [rsp+D0h] [rbp+Fh] BYREF
  int v71; // [rsp+D4h] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  *(_QWORD *)v56 = a4;
  psz = a2;
  v68[0] = 0;
  VariantInit(&pvarg);
  v69 = 0;
  v70 = 0;
  v60 = 0;
  v64 = 0;
  v62 = 0;
  v61 = 0;
  v63 = 0;
  VariantInit(&v66);
  v71 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    v59 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update downloader specified");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v8 = 801;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    if ( v66.vt )
    {
      VariantClear(&v66);
      v66.vt = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
      v63 = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    v9 = pvarg.vt == 0;
    goto LABEL_22;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    v59 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update specified");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v8 = 802;
    goto LABEL_9;
  }
  v11 = (CUUPDownloadProgressCallBack *)operator new(0x40u);
  if ( !v11 || (v12 = CUUPDownloadProgressCallBack::CUUPDownloadProgressCallBack(v11, a4)) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
    if ( v66.vt )
    {
      VariantClear(&v66);
      v66.vt = 0;
    }
    goto LABEL_177;
  }
  v13 = operator new(0x30u);
  v14 = v13;
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
    if ( v66.vt )
    {
      VariantClear(&v66);
      v66.vt = 0;
    }
    v54 = (char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v54 + 16LL))(v54);
LABEL_177:
    v34 = pvarg.vt == 0;
LABEL_178:
    if ( !v34 )
      VariantClear(&pvarg);
    return 2147942414LL;
  }
  v13[2] = 0;
  v13[3] = 0;
  v13[4] = 0;
  v13[1] = &CUUPDownloadCompleteCallBack::`vbtable';
  *v13 = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v13[5] = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'};
  *((_DWORD *)v13 + 9) = 8;
  *v13 = &CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v15 = v13[1];
  *((_DWORD *)v14 + 4) = 1;
  *(_QWORD *)((char *)v14 + *(int *)(v15 + 4) + 8) = &CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'};
  *(_DWORD *)((char *)v14 + *(int *)(v14[1] + 4LL) + 4) = 0;
  v14[3] = 0;
  v16 = CUUPDownloadCompleteCallBack::Initialize((CUUPDownloadCompleteCallBack *)v14);
  v17 = v16;
  if ( v16 < 0 )
  {
    v59 = v16;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize complete callback");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v18 = 810;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v17,
      (int)ppv);
    if ( v66.vt )
    {
      VariantClear(&v66);
      v66.vt = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
      v63 = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    v19 = (char *)v14 + *(int *)(v14[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 16LL))(v19);
    v20 = (char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))(v20);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return v17;
  }
  if ( v61 )
    goto LABEL_181;
  v21 = CoCreateInstance(
          &GUID_13639463_00db_4646_803d_528026140d88,
          0,
          1u,
          &GUID_07f7438c_7709_4ca5_b518_91279288134e,
          &v61);
  v17 = v21;
  if ( v21 < 0 )
  {
    v59 = v21;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create collection");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v18 = 813;
    goto LABEL_32;
  }
  v22 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v61 + 96LL))(v61, a3, &v71);
  v17 = v22;
  if ( v22 < 0 )
  {
    v59 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add update to collection");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v18 = 815;
    goto LABEL_32;
  }
  v23 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*a1 + 112))(a1, v61);
  v17 = v23;
  if ( v23 < 0 )
  {
    v59 = v23;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to call put_updates on downloader");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v18 = 817;
    goto LABEL_32;
  }
  v24 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*a3 + 104))(a3, v68);
  if ( v24 )
  {
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v24, "WU:Failed to check whether psf is available.");
  }
  else
  {
    if ( v68[0] == -1 )
    {
      v25 = *a3;
      LOWORD(v59) = 0;
      v26 = (*(unsigned int (__fastcall **)(__int64 *, int *))(v25 + 112))(a3, &v59);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v26, "WU: Failed to check whether PSF is preferred.");
      if ( (_DWORD)v26 )
        goto LABEL_69;
      if ( (_WORD)v59 == 0xFFFF )
        v27 = "WU: PSF is available and preferred for the update.";
      else
        v27 = "WU: PSF is available but not preferred for the update.";
    }
    else
    {
      v27 = "WU: PSF is not available for the update.";
    }
    LogAdapter::TraceAtLevel<>(1, v27);
  }
LABEL_69:
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v63);
  v29 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))*a1)(
          a1,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          InitPointer);
  v7 = v29;
  if ( v29 < 0 )
  {
    v59 = v29;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set client ID");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v30 = 856;
    goto LABEL_73;
  }
  v66.vt = 8;
  v66.llVal = (LONGLONG)SysAllocString(psz);
  if ( !v66.llVal )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
    if ( v66.vt )
    {
      VariantClear(&v66);
      v66.vt = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
      v63 = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    v32 = (char *)v14 + *(int *)(v14[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))(v32);
    v33 = (char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 16LL))(v33);
    v34 = pvarg.vt == 0;
    goto LABEL_178;
  }
  v35 = *v63;
  v58 = v66;
  v36 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v35 + 32))(v63, 196621, &v58);
  v7 = v36;
  if ( v36 < 0 )
  {
    v59 = v36;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set scan current product version only");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v30 = 862;
    goto LABEL_73;
  }
  if ( v60 )
    goto LABEL_181;
  v37 = *a1;
  v38 = *((_QWORD *)v12 + 1);
  v39 = (char *)v14 + *(int *)(v14[1] + 4LL) + 8;
  v58 = pvarg;
  ppv = (LPVOID *)&v60;
  v40 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *, VARIANTARG *))(v37 + 120))(
          a1,
          (__int64)v12 + *(int *)(v38 + 4) + 8,
          v39,
          &v58);
  v7 = v40;
  if ( v40 < 0 )
  {
    v59 = v40;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed calling begin download");
      psz = (OLECHAR *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&psz);
    }
    v30 = 867;
    goto LABEL_73;
  }
LABEL_109:
  v41 = v69;
  while ( (*((_BYTE *)v12 + 24) || v41 <= 0xDBBA0) && (*((int *)v12 + 8) >= 4 || v41 <= 0x2932E0) )
  {
    v42 = WaitForSingleObject((HANDLE)v14[3], 0x7D0u);
    if ( !v42 )
    {
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 80LL))(v60);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v46, "DWLD: Failed to call download job cleanup");
      v47 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 136);
      v48 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v64);
      v49 = v47(a1, v60, v48);
      v7 = v49;
      if ( v49 < 0 )
      {
        v59 = v49;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to call end download");
          *(_QWORD *)v56 = &v59;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v56);
        }
        v30 = 935;
        goto LABEL_73;
      }
      if ( !v62 )
      {
        v50 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v64 + 72LL))(v64, 0, &v62);
        v7 = v50;
        if ( v50 >= 0 )
        {
          v51 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 56LL))(v62, &v70);
          v7 = v51;
          if ( v51 >= 0 )
          {
            v7 = v70;
            if ( v70 < 0 )
            {
              LODWORD(psz) = v70;
              if ( LogAdapter::g_Logger )
              {
                v57 = &v70;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"DWLD: Download failed with {}",
                  (__int64)&v57);
                *(_QWORD *)v56 = &psz;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v56);
              }
              v45 = 946;
              goto LABEL_124;
            }
            if ( v66.vt )
            {
              VariantClear(&v66);
              v66.vt = 0;
            }
            if ( v63 )
            {
              (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
              v63 = 0;
            }
            if ( v61 )
            {
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
              v61 = 0;
            }
            if ( v62 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
              v62 = 0;
            }
            if ( v64 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
              v64 = 0;
            }
            if ( v60 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
              v60 = 0;
            }
            v52 = (char *)v14 + *(int *)(v14[1] + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v52 + 16LL))(v52);
            v53 = (char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v53 + 16LL))(v53);
            if ( pvarg.vt )
              VariantClear(&pvarg);
            return 0;
          }
          v59 = v51;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to get download hresult");
            *(_QWORD *)v56 = &v59;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v56);
          }
          v30 = 944;
        }
        else
        {
          v59 = v50;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Failed to get update result");
            *(_QWORD *)v56 = &v59;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v56);
          }
          v30 = 942;
        }
LABEL_73:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v7,
          (int)ppv);
        if ( v66.vt )
        {
          VariantClear(&v66);
          v66.vt = 0;
        }
        if ( v63 )
        {
          (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
          v63 = 0;
        }
        if ( v61 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
          v61 = 0;
        }
        if ( v62 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          v62 = 0;
        }
        if ( v64 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          v64 = 0;
        }
        if ( v60 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          v60 = 0;
        }
        goto LABEL_85;
      }
LABEL_181:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18029EF94LL);
    }
    if ( v42 != 258 )
    {
      v7 = -2147467259;
      v59 = -2147467259;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query status of event, assuming failure.");
        *(_QWORD *)v56 = &v59;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v56);
      }
      v45 = 911;
      goto LABEL_124;
    }
    v41 = v69 + 2000;
    v69 += 2000;
    if ( *(_QWORD *)v56 )
    {
      v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)v56 + 40LL))(
              *(_QWORD *)v56,
              *((unsigned int *)v12 + 7),
              100);
      if ( (unsigned int)(v43 + 2146498528) <= 1 )
      {
        LOBYTE(v44) = v43 == -2146498527;
        CancelDownload(v60, a1, v44);
        v7 = -2147467260;
        v59 = -2147467260;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"DWLD: Caller cancelled the download operation");
          *(_QWORD *)v56 = &v59;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v56);
        }
        v45 = 905;
        goto LABEL_124;
      }
      goto LABEL_109;
    }
  }
  CancelDownload(v60, a1, 0);
  v7 = -2145124319;
  v59 = -2145124319;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<unsigned long>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"DWLD: Timed out waiting on WU download for {} milliseconds.",
      (__int64)&v69);
    *(_QWORD *)v56 = &v59;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v56);
  }
  v45 = 882;
LABEL_124:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v45,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)v7,
    (int)ppv);
  if ( v66.vt )
  {
    VariantClear(&v66);
    v66.vt = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
    v63 = 0;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v60 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v60 = 0;
  }
LABEL_85:
  v31 = (char *)v14 + *(int *)(v14[1] + 4LL) + 8;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 16LL))(v31);
  (*(void (**)(void))(*(_QWORD *)((char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8) + 16LL))();
  v9 = pvarg.vt == 0;
LABEL_22:
  if ( !v9 )
    VariantClear(&pvarg);
  return v7;
}

```

## disassembly

```asm
0x18029de68  push    rbp
0x18029de6a  push    rbx
0x18029de6b  push    rsi
0x18029de6c  push    rdi
0x18029de6d  push    r12
0x18029de6f  push    r13
0x18029de71  push    r15
0x18029de73  lea     rbp, [rsp-1Fh]
0x18029de78  sub     rsp, 0E0h
0x18029de7f  mov     rax, cs:__security_cookie
0x18029de86  xor     rax, rsp
0x18029de89  mov     [rbp+4Fh+var_38], rax
0x18029de8d  mov     r12, rcx
0x18029de90  mov     qword ptr [rsp+110h+var_E0], r9
0x18029de95  xor     esi, esi
0x18029de97  mov     [rbp+4Fh+psz], rdx
0x18029de9b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18029de9f  mov     [rbp+4Fh+var_48], si
0x18029dea3  mov     rdi, r9
0x18029dea6  mov     rbx, r8
0x18029dea9  call    cs:__imp_VariantInit
0x18029deb0  nop     dword ptr [rax+rax+00h]
0x18029deb5  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18029deb9  mov     [rbp+4Fh+var_44], esi
0x18029debc  mov     [rbp+4Fh+var_40], esi
0x18029debf  mov     [rbp+4Fh+var_A8], rsi
0x18029dec3  mov     [rbp+4Fh+var_88], rsi
0x18029dec7  mov     [rbp+4Fh+var_98], rsi
0x18029decb  mov     [rbp+4Fh+var_A0], rsi
0x18029decf  mov     [rbp+4Fh+var_90], rsi
0x18029ded3  call    cs:__imp_VariantInit
0x18029deda  nop     dword ptr [rax+rax+00h]
0x18029dedf  mov     [rbp+4Fh+var_3C], esi
0x18029dee2  test    r12, r12
0x18029dee5  jnz     short loc_18029DF3F
0x18029dee7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029deee  mov     ebx, 80070057h
0x18029def3  mov     [rbp+4Fh+var_B0], ebx
0x18029def6  test    rcx, rcx
0x18029def9  jz      short loc_18029DF38
0x18029defb  lea     edi, [rsi+3]
0x18029defe  xor     edx, edx
0x18029df00  mov     r8d, edi
0x18029df03  lea     r9, aNoUpdateDownlo; "No update downloader specified"
0x18029df0a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029df0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029df16  lea     rax, [rbp+4Fh+var_B0]
0x18029df1a  mov     [rbp+4Fh+psz], rax
0x18029df1e  lea     r9, asc_1802EE7AC; ": {}"
0x18029df25  lea     rax, [rbp+4Fh+psz]
0x18029df29  mov     r8d, edi
0x18029df2c  mov     dl, 1
0x18029df2e  mov     [rsp+110h+ppv], rax
0x18029df33  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029df38  mov     edx, 321h
0x18029df3d  jmp     short loc_18029DFA0
0x18029df3f  test    rbx, rbx
0x18029df42  jnz     loc_18029E067
0x18029df48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029df4f  mov     ebx, 80070057h
0x18029df54  mov     [rbp+4Fh+var_B0], ebx
0x18029df57  test    rcx, rcx
0x18029df5a  jz      short loc_18029DF9B
0x18029df5c  mov     edi, 3
0x18029df61  lea     r9, aNoUpdateSpecif; "No update specified"
0x18029df68  mov     r8d, edi
0x18029df6b  xor     edx, edx
0x18029df6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029df72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029df79  lea     rax, [rbp+4Fh+var_B0]
0x18029df7d  mov     [rbp+4Fh+psz], rax
0x18029df81  lea     r9, asc_1802EE7AC; ": {}"
0x18029df88  lea     rax, [rbp+4Fh+psz]
0x18029df8c  mov     r8d, edi
0x18029df8f  mov     dl, 1
0x18029df91  mov     [rsp+110h+ppv], rax; int
0x18029df96  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029df9b  mov     edx, 322h; void *
0x18029dfa0  mov     rcx, [rbp+57h]; this
0x18029dfa4  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029dfab  mov     r9d, ebx; char *
0x18029dfae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029dfb3  cmp     word ptr [rbp+4Fh+var_78], si
0x18029dfb7  jz      short loc_18029DFCD
0x18029dfb9  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18029dfbd  call    cs:__imp_VariantClear
0x18029dfc4  nop     dword ptr [rax+rax+00h]
0x18029dfc9  mov     word ptr [rbp+4Fh+var_78], si
0x18029dfcd  mov     rcx, [rbp+4Fh+var_90]
0x18029dfd1  test    rcx, rcx
0x18029dfd4  jz      short loc_18029DFE6
0x18029dfd6  mov     rax, [rcx]
0x18029dfd9  mov     rax, [rax+10h]
0x18029dfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029dfe2  mov     [rbp+4Fh+var_90], rsi
0x18029dfe6  mov     rcx, [rbp+4Fh+var_A0]
0x18029dfea  test    rcx, rcx
0x18029dfed  jz      short loc_18029DFFF
0x18029dfef  mov     rax, [rcx]
0x18029dff2  mov     rax, [rax+10h]
0x18029dff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029dffb  mov     [rbp+4Fh+var_A0], rsi
0x18029dfff  mov     rcx, [rbp+4Fh+var_98]
0x18029e003  test    rcx, rcx
0x18029e006  jz      short loc_18029E018
0x18029e008  mov     rax, [rcx]
0x18029e00b  mov     rax, [rax+10h]
0x18029e00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e014  mov     [rbp+4Fh+var_98], rsi
0x18029e018  mov     rcx, [rbp+4Fh+var_88]
0x18029e01c  test    rcx, rcx
0x18029e01f  jz      short loc_18029E031
0x18029e021  mov     rax, [rcx]
0x18029e024  mov     rax, [rax+10h]
0x18029e028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e02d  mov     [rbp+4Fh+var_88], rsi
0x18029e031  mov     rcx, [rbp+4Fh+var_A8]
0x18029e035  test    rcx, rcx
0x18029e038  jz      short loc_18029E04A
0x18029e03a  mov     rax, [rcx]
0x18029e03d  mov     rax, [rax+10h]
0x18029e041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e046  mov     [rbp+4Fh+var_A8], rsi
0x18029e04a  cmp     word ptr [rbp+4Fh+pvarg], si
0x18029e04e  jz      short loc_18029E060
0x18029e050  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18029e054  call    cs:__imp_VariantClear
0x18029e05b  nop     dword ptr [rax+rax+00h]
0x18029e060  mov     eax, ebx
0x18029e062  jmp     loc_18029EF6B
0x18029e067  mov     ecx, 40h ; '@'; Size
0x18029e06c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18029e071  test    rax, rax
0x18029e074  jz      loc_18029EE9C
0x18029e07a  mov     rdx, rdi; struct IWULibCallback *
0x18029e07d  mov     rcx, rax; this
0x18029e080  call    ??0CUUPDownloadProgressCallBack@@QEAA@PEAVIWULibCallback@@@Z; CUUPDownloadProgressCallBack::CUUPDownloadProgressCallBack(IWULibCallback *)
0x18029e085  xor     edi, edi
0x18029e087  mov     r15, rax
0x18029e08a  test    rax, rax
0x18029e08d  jz      loc_18029EE9E
0x18029e093  lea     ecx, [rdi+30h]; Size
0x18029e096  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18029e09b  mov     rsi, rax
0x18029e09e  test    rax, rax
0x18029e0a1  jz      loc_18029EDCA
0x18029e0a7  mov     [rax+10h], rdi
0x18029e0ab  mov     [rax+18h], rdi
0x18029e0af  mov     [rax+20h], rdi
0x18029e0b3  lea     rax, ??_8CUUPDownloadCompleteCallBack@@7B@; const CUUPDownloadCompleteCallBack::`vbtable'
0x18029e0ba  mov     [rsi+8], rax
0x18029e0be  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6B0@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x18029e0c5  mov     [rsi], rax
0x18029e0c8  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6BIDownloadCompletedCallback@@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'}
0x18029e0cf  mov     [rsi+28h], rax
0x18029e0d3  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6B?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x18029e0da  movsxd  rdx, cs:dword_1802EBBD0
0x18029e0e1  lea     ecx, [rdx-18h]
0x18029e0e4  mov     [rdx+rsi+4], ecx
0x18029e0e8  mov     [rsi], rax
0x18029e0eb  mov     rax, [rsi+8]
0x18029e0ef  mov     dword ptr [rsi+10h], 1
0x18029e0f6  movsxd  rcx, dword ptr [rax+4]
0x18029e0fa  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6BIDownloadCompletedCallback@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'}
0x18029e101  mov     [rcx+rsi+8], rax
0x18029e106  mov     rax, [rsi+8]
0x18029e10a  movsxd  rcx, dword ptr [rax+4]
0x18029e10e  mov     [rcx+rsi+4], edi
0x18029e112  mov     rcx, rsi; this
0x18029e115  mov     [rsi+18h], rdi
0x18029e119  call    ?Initialize@CUUPDownloadCompleteCallBack@@QEAAJXZ; CUUPDownloadCompleteCallBack::Initialize(void)
0x18029e11e  mov     r13d, eax
0x18029e121  test    eax, eax
0x18029e123  jns     loc_18029E27C
0x18029e129  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e130  mov     [rbp+4Fh+var_B0], eax
0x18029e133  test    rcx, rcx
0x18029e136  jz      short loc_18029E179
0x18029e138  mov     edi, 3
0x18029e13d  lea     r9, aFailedToInitia_19; "Failed to initialize complete callback"
0x18029e144  mov     r8d, edi
0x18029e147  xor     edx, edx
0x18029e149  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029e14e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e155  lea     rax, [rbp+4Fh+var_B0]
0x18029e159  mov     [rbp+4Fh+psz], rax
0x18029e15d  lea     r9, asc_1802EE7AC; ": {}"
0x18029e164  lea     rax, [rbp+4Fh+psz]
0x18029e168  mov     r8d, edi
0x18029e16b  mov     dl, 1
0x18029e16d  mov     [rsp+110h+ppv], rax; int
0x18029e172  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029e177  xor     edi, edi
0x18029e179  mov     edx, 32Ah; void *
0x18029e17e  mov     rcx, [rbp+57h]; this
0x18029e182  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029e189  mov     r9d, r13d; char *
0x18029e18c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029e191  cmp     word ptr [rbp+4Fh+var_78], di
0x18029e195  jz      short loc_18029E1AB
0x18029e197  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18029e19b  call    cs:__imp_VariantClear
0x18029e1a2  nop     dword ptr [rax+rax+00h]
0x18029e1a7  mov     word ptr [rbp+4Fh+var_78], di
0x18029e1ab  mov     rcx, [rbp+4Fh+var_90]
0x18029e1af  test    rcx, rcx
0x18029e1b2  jz      short loc_18029E1C4
0x18029e1b4  mov     rax, [rcx]
0x18029e1b7  mov     rax, [rax+10h]
0x18029e1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e1c0  mov     [rbp+4Fh+var_90], rdi
0x18029e1c4  mov     rcx, [rbp+4Fh+var_A0]
0x18029e1c8  test    rcx, rcx
0x18029e1cb  jz      short loc_18029E1DD
0x18029e1cd  mov     rax, [rcx]
0x18029e1d0  mov     rax, [rax+10h]
0x18029e1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e1d9  mov     [rbp+4Fh+var_A0], rdi
0x18029e1dd  mov     rcx, [rbp+4Fh+var_98]
0x18029e1e1  test    rcx, rcx
0x18029e1e4  jz      short loc_18029E1F6
0x18029e1e6  mov     rax, [rcx]
0x18029e1e9  mov     rax, [rax+10h]
0x18029e1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e1f2  mov     [rbp+4Fh+var_98], rdi
0x18029e1f6  mov     rcx, [rbp+4Fh+var_88]
0x18029e1fa  test    rcx, rcx
0x18029e1fd  jz      short loc_18029E20F
0x18029e1ff  mov     rax, [rcx]
0x18029e202  mov     rax, [rax+10h]
0x18029e206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e20b  mov     [rbp+4Fh+var_88], rdi
0x18029e20f  mov     rcx, [rbp+4Fh+var_A8]
0x18029e213  test    rcx, rcx
0x18029e216  jz      short loc_18029E228
0x18029e218  mov     rax, [rcx]
0x18029e21b  mov     rax, [rax+10h]
0x18029e21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e224  mov     [rbp+4Fh+var_A8], rdi
0x18029e228  mov     rax, [rsi+8]
0x18029e22c  movsxd  rcx, dword ptr [rax+4]
0x18029e230  add     rcx, 8
0x18029e234  add     rcx, rsi
0x18029e237  mov     rax, [rcx]
0x18029e23a  mov     rax, [rax+10h]
0x18029e23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e243  mov     rax, [r15+8]
0x18029e247  movsxd  rcx, dword ptr [rax+4]
0x18029e24b  add     rcx, 8
0x18029e24f  add     rcx, r15
0x18029e252  mov     rax, [rcx]
0x18029e255  mov     rax, [rax+10h]
0x18029e259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e25e  cmp     word ptr [rbp+4Fh+pvarg], di
0x18029e262  jz      short loc_18029E274
0x18029e264  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18029e268  call    cs:__imp_VariantClear
0x18029e26f  nop     dword ptr [rax+rax+00h]
0x18029e274  mov     eax, r13d
0x18029e277  jmp     loc_18029EF6B
0x18029e27c  cmp     [rbp+4Fh+var_A0], rdi
0x18029e280  jnz     loc_18029EF8A
0x18029e286  xor     edx, edx; pUnkOuter
0x18029e288  lea     rax, [rbp+4Fh+var_A0]
0x18029e28c  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x18029e293  mov     [rsp+110h+ppv], rax; int
0x18029e298  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x18029e29f  lea     r8d, [rdx+1]; dwClsContext
0x18029e2a3  call    cs:__imp_CoCreateInstance
0x18029e2aa  nop     dword ptr [rax+rax+00h]
0x18029e2af  mov     r13d, eax
0x18029e2b2  test    eax, eax
0x18029e2b4  jns     short loc_18029E310
0x18029e2b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e2bd  mov     [rbp+4Fh+var_B0], eax
0x18029e2c0  test    rcx, rcx
0x18029e2c3  jz      short loc_18029E306
0x18029e2c5  mov     edi, 3
0x18029e2ca  lea     r9, aFailedToCreate_37; "Failed to create collection"
0x18029e2d1  mov     r8d, edi
0x18029e2d4  xor     edx, edx
0x18029e2d6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029e2db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e2e2  lea     rax, [rbp+4Fh+var_B0]
0x18029e2e6  mov     [rbp+4Fh+psz], rax
0x18029e2ea  lea     r9, asc_1802EE7AC; ": {}"
0x18029e2f1  lea     rax, [rbp+4Fh+psz]
0x18029e2f5  mov     r8d, edi
0x18029e2f8  mov     dl, 1
0x18029e2fa  mov     [rsp+110h+ppv], rax
0x18029e2ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029e304  xor     edi, edi
0x18029e306  mov     edx, 32Dh
0x18029e30b  jmp     loc_18029E17E
0x18029e310  mov     rcx, [rbp+4Fh+var_A0]
0x18029e314  lea     r8, [rbp+4Fh+var_3C]
0x18029e318  mov     rdx, rbx
0x18029e31b  mov     rax, [rcx]
0x18029e31e  mov     rax, [rax+60h]
0x18029e322  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
