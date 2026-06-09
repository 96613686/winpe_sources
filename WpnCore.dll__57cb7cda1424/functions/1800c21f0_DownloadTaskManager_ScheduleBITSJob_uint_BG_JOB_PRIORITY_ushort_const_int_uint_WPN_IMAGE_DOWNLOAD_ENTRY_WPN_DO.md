# DownloadTaskManager::ScheduleBITSJob(uint,BG_JOB_PRIORITY,ushort const *,int,uint,WPN_IMAGE_DOWNLOAD_ENTRY *,WPN_DOWNLOAD_TASK *,uint)

- ea: `0x1800c21f0`
- end: `0x1800c2d56`
- name: `?ScheduleBITSJob@DownloadTaskManager@@AEAAJIW4BG_JOB_PRIORITY@@PEBGHIPEAUWPN_IMAGE_DOWNLOAD_ENTRY@@PEAUWPN_DOWNLOAD_TASK@@I@Z`
- size: `2918`
- prototype: `int(DownloadTaskManager *__hidden this, unsigned int, enum BG_JOB_PRIORITY, const unsigned __int16 *, int, unsigned int, struct WPN_IMAGE_DOWNLOAD_ENTRY *, struct WPN_DOWNLOAD_TASK *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0c30`

## callees

- `0x180004e38`
- `0x18002ee38`
- `0x18002ee68`
- `0x180067d58`
- `0x180067de0`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800c059c`
- `0x1800c21f0`
- `0x1800c2d88`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2cbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2cbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2bff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2ccd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2bff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2ccd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2358`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2358`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c2c18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c2c18`

## string_xrefs

- `0x1800c22c1`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2397`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c23f3`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c246d`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c24f9`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2577`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c25f3`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2669`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c26de`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2755`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c27ce`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2838`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c289a`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c28fd`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2964`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c29d4`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2a52`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2abf`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2b21`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2b7a`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DownloadTaskManager::ScheduleBITSJob(
        DownloadTaskManager *this,
        int a2,
        enum BG_JOB_PRIORITY a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned int a6,
        struct WPN_IMAGE_DOWNLOAD_ENTRY *a7,
        struct WPN_DOWNLOAD_TASK *a8,
        unsigned int a9)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // r14d
  int v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rsi
  int v20; // eax
  BSTR v21; // rax
  __int64 v22; // rdi
  int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, const unsigned __int16 * near *, _QWORD, char *); // rbx
  int v28; // eax
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rdi
  int v31; // eax
  int v32; // eax
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  int v35; // eax
  int v36; // eax
  __int128 v37; // xmm6
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  DownloadTaskManager *v43; // rdi
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  unsigned int v50; // r14d
  __int64 v51; // rdi
  void *v52; // r15
  HANDLE ProcessHeap; // rax
  OLECHAR *v54; // rcx
  int v55; // r13d
  int v56; // edx
  int v57; // ecx
  unsigned __int16 *v58; // rdi
  __int64 v59; // rsi
  char v60; // di
  int v61; // ebx
  HANDLE v62; // rax
  int v64; // [rsp+28h] [rbp-E0h]
  __int64 v65; // [rsp+48h] [rbp-C0h] BYREF
  int v66[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v67; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v68; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v69; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v70[24]; // [rsp+70h] [rbp-98h] BYREF
  enum BG_JOB_PRIORITY v71; // [rsp+88h] [rbp-80h]
  int v72; // [rsp+8Ch] [rbp-7Ch]
  __int64 v73; // [rsp+90h] [rbp-78h] BYREF
  __int128 v74; // [rsp+98h] [rbp-70h] BYREF
  DownloadTaskManager *v75; // [rsp+A8h] [rbp-60h]
  __int128 v76; // [rsp+B8h] [rbp-50h]
  _OWORD v77[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v78[18]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+D8h]

  v71 = a3;
  v72 = a2;
  v75 = this;
  LODWORD(v68) = 0;
  v76 = 0;
  memset(v77, 0, 24);
  v69 = 0;
  *(_QWORD *)v66 = 0;
  v73 = 0;
  v67 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)a8 + 33) + 8LL))((char *)a8 + 264) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  v13 = a6;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  v14 = WpnStrCpy(a4, &v69);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v14,
      v64);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v17 = 32;
LABEL_11:
      v18 = v15;
LABEL_20:
      WPP_SF_d(v16[2], v17, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids, v18);
    }
    goto LABEL_95;
  }
  v19 = 0;
  while ( (unsigned int)v19 < v13 )
  {
    *((_DWORD *)a8 + 6 * v19 + 12) = *((_DWORD *)a7 + 6 * v19);
    *((_QWORD *)a8 + 3 * v19 + 7) = 0;
    v20 = WpnStrCpy(*((const unsigned __int16 **)a7 + 3 * v19 + 1), (unsigned __int16 **)a8 + 3 * v19 + 7);
    v15 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6A2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
        (const char *)(unsigned int)v20,
        v64);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v17 = 33;
        goto LABEL_11;
      }
LABEL_95:
      v50 = 0;
      if ( a6 )
      {
        v51 = 0;
        do
        {
          v52 = (void *)*((_QWORD *)a8 + 3 * v51 + 7);
          if ( v52 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v52);
            *((_QWORD *)a8 + 3 * v51 + 7) = 0;
          }
          v54 = (OLECHAR *)*((_QWORD *)a8 + 3 * v51 + 8);
          if ( v54 )
          {
            SysFreeString(v54);
            *((_QWORD *)a8 + 3 * v51 + 8) = 0;
          }
          ++v50;
          ++v51;
        }
        while ( v50 < a6 );
      }
      v55 = v68;
LABEL_109:
      v58 = v69;
      goto LABEL_110;
    }
    *((_QWORD *)a8 + 3 * v19 + 8) = 0;
    v21 = SysAllocString(*((const OLECHAR **)a7 + 3 * v19 + 2));
    *((_QWORD *)a8 + 3 * v19 + 8) = v21;
    if ( !v21 )
    {
      v15 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6AB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
        (const char *)0x8007000ELL,
        v64);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v17 = 34;
        v18 = 2147942414LL;
        goto LABEL_20;
      }
      goto LABEL_95;
    }
    v22 = 2LL * (unsigned int)v19;
    v78[v22 + 1] = v21;
    v78[v22] = *((_QWORD *)a8 + 3 * v19 + 7);
    v19 = (unsigned int)(v19 + 1);
    v13 = a6;
  }
  *((_DWORD *)a8 + 11) = v13;
  CRPCTimeout::CRPCTimeout((CRPCTimeout *)v70, 0xBB8u);
  v65 = 0;
  v23 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IBackgroundCopyManager>(
          (__int64)a8 + 264,
          &v65);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6BD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v23,
      v64);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 35;
LABEL_93:
    WPP_SF_d(v24[2], v25, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids, v15);
LABEL_94:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v70);
    goto LABEL_95;
  }
  v26 = v65;
  v27 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 * near *, _QWORD, char *))(*(_QWORD *)v65 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v66);
  v28 = v27(v26, (&g_BITSJobDisplayNames)[v72], 0, (char *)a8 + 8);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v28,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 36;
    goto LABEL_93;
  }
  LODWORD(v68) = 1;
  v29 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v66;
  v30 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v66;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  v31 = v30(v29, &GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af, &v73);
  v15 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6CD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v31,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 37;
    goto LABEL_93;
  }
  v77[0] = 0x400000002uLL;
  v32 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v73 + 328LL))(v73, v77);
  v15 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6D7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v32,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 38;
    goto LABEL_93;
  }
  v33 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v66;
  v34 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v66;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  v35 = v34(v33, &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe, &v67);
  v15 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6DA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v35,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 39;
    goto LABEL_93;
  }
  LODWORD(v76) = 2;
  v74 = v76;
  v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v67 + 424LL))(v67, 7, &v74);
  v15 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6E2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v36,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 40;
    goto LABEL_93;
  }
  LODWORD(v76) = 1;
  v37 = v76;
  v74 = v76;
  v38 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v67 + 424LL))(v67, 4, &v74);
  v15 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6EA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v38,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 41;
    goto LABEL_93;
  }
  if ( !a5 )
  {
    v74 = v37;
    v39 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v67 + 424LL))(v67, 6, &v74);
    v15 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6F3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
        (const char *)(unsigned int)v39,
        (int)v66);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_94;
      v25 = (unsigned int)(a5 + 42);
      goto LABEL_93;
    }
  }
  v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)v66 + 24LL))(*(_QWORD *)v66, a6, v78);
  v15 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6FB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v40,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 43;
    goto LABEL_93;
  }
  v41 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v66 + 232LL))(*(_QWORD *)v66, 0);
  v15 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x702,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v41,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 44;
    goto LABEL_93;
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v66 + 168LL))(*(_QWORD *)v66, (unsigned int)v71);
  v15 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x709,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v42,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 45;
    goto LABEL_93;
  }
  v43 = v75;
  v44 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 408LL))(v67, *((unsigned int *)v75 + 19));
  v15 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x710,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v44,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 46;
    goto LABEL_93;
  }
  v74 = v37;
  v45 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v67 + 424LL))(v67, 3, &v74);
  v15 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x717,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v45,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 47;
    goto LABEL_93;
  }
  *(_QWORD *)&v76 = a9 * a6;
  v74 = v76;
  v46 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v67 + 424LL))(v67, 5, &v74);
  v15 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x722,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v46,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 48;
    goto LABEL_93;
  }
  v47 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)v66 + 200LL))(
          *(_QWORD *)v66,
          ((unsigned __int64)v43 + 32) & -(__int64)(v43 != 0));
  v15 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x729,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v47,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 49;
    goto LABEL_93;
  }
  v48 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v66 + 184LL))(*(_QWORD *)v66, 3);
  v15 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x730,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v48,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 50;
    goto LABEL_93;
  }
  v49 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 56LL))(*(_QWORD *)v66);
  v15 = v49;
  LODWORD(v75) = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x733,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v49,
      (int)v66);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v25 = 51;
    goto LABEL_93;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v70);
  *((_QWORD *)a8 + 4) = v69;
  *((_DWORD *)a8 + 6) ^= (*((_DWORD *)a8 + 6) ^ (16 * a5)) & 0x10;
  v58 = 0;
  v69 = 0;
  v55 = 0;
  v59 = 0;
  if ( a6 )
  {
    v60 = v71;
    v61 = v72;
    do
    {
      if ( (byte_18015DE48 & 8) != 0 )
        McTemplateU0qqqtz_EventWriteTransfer(
          v57,
          v56,
          v61,
          *((_DWORD *)a7 + 6 * v59),
          v60,
          a5,
          *((_QWORD *)a7 + 3 * v59 + 1));
      v59 = (unsigned int)(v59 + 1);
    }
    while ( (unsigned int)v59 < a6 );
    v15 = (unsigned int)v75;
    goto LABEL_109;
  }
LABEL_110:
  if ( v58 )
  {
    v62 = GetProcessHeap();
    HeapFree(v62, 0, v58);
  }
  if ( *(_QWORD *)v66 && v55 )
  {
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)v70, 0x1F4u);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 64LL))(*(_QWORD *)v66);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v70);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v66);
  return v15;
}

```

## disassembly

```asm
0x1800c21f0  mov     rax, rsp
0x1800c21f3  push    rbp
0x1800c21f4  push    rbx
0x1800c21f5  push    rsi
0x1800c21f6  push    rdi
0x1800c21f7  push    r12
0x1800c21f9  push    r13
0x1800c21fb  push    r14
0x1800c21fd  push    r15
0x1800c21ff  lea     rbp, [rax-0D8h]
0x1800c2206  sub     rsp, 198h
0x1800c220d  movaps  xmmword ptr [rax-58h], xmm6
0x1800c2211  mov     rax, cs:__security_cookie
0x1800c2218  xor     rax, rsp
0x1800c221b  mov     [rbp+0D0h+var_60], rax
0x1800c221f  mov     rbx, r9
0x1800c2222  mov     [rbp+0D0h+var_150], r8d
0x1800c2226  mov     [rbp+0D0h+var_14C], edx
0x1800c2229  mov     [rbp+0D0h+var_130], rcx
0x1800c222d  mov     r12, [rbp+0D0h+arg_30]
0x1800c2234  mov     r13, [rbp+0D0h+arg_38]
0x1800c223b  mov     dword ptr [rsp+1D0h+var_178], 0
0x1800c2243  xorps   xmm0, xmm0
0x1800c2246  movups  [rbp+0D0h+var_120], xmm0
0x1800c224a  xorps   xmm1, xmm1
0x1800c224d  xor     eax, eax
0x1800c224f  movups  [rbp+0D0h+var_110], xmm1
0x1800c2253  mov     [rbp+0D0h+var_100], rax
0x1800c2257  mov     [rsp+1D0h+var_170], rax
0x1800c225c  mov     qword ptr [rsp+1D0h+var_188], rax
0x1800c2261  mov     [rbp+0D0h+var_148], rax
0x1800c2265  mov     [rsp+1D0h+var_180], rax
0x1800c226a  lea     rdi, [r13+108h]
0x1800c2271  mov     rax, [rdi]
0x1800c2274  mov     rcx, rdi
0x1800c2277  mov     rax, [rax+8]
0x1800c227b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2280  test    al, al
0x1800c2282  jnz     short loc_1800C2289
0x1800c2284  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Task->Bits.IsInitialized()")
0x1800c2289  mov     r14d, [rbp+0D0h+arg_28]
0x1800c2290  test    r14d, r14d
0x1800c2293  jnz     short loc_1800C229A
0x1800c2295  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Count > 0")
0x1800c229a  test    r12, r12
0x1800c229d  jnz     short loc_1800C22A4
0x1800c229f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "DownloadEntry != NULL")
0x1800c22a4  lea     rdx, [rsp+1D0h+var_170]; unsigned __int16 **
0x1800c22a9  mov     rcx, rbx; unsigned __int16 *
0x1800c22ac  call    ?WpnStrCpy@@YAJPEBGPEAPEAG@Z; WpnStrCpy(ushort const *,ushort * *)
0x1800c22b1  mov     ebx, eax
0x1800c22b3  test    eax, eax
0x1800c22b5  jns     short loc_1800C2300
0x1800c22b7  mov     rcx, [rbp+0D8h]; this
0x1800c22be  mov     r9d, eax; char *
0x1800c22c1  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c22c8  mov     edx, 696h; void *
0x1800c22cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c22d2  lea     rax, WPP_GLOBAL_Control
0x1800c22d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c22e0  cmp     rcx, rax
0x1800c22e3  jz      loc_1800C2BD2
0x1800c22e9  test    byte ptr [rcx+1Ch], 80h
0x1800c22ed  jz      loc_1800C2BD2
0x1800c22f3  mov     edx, 20h ; ' '
0x1800c22f8  mov     r9d, ebx
0x1800c22fb  jmp     loc_1800C23D4
0x1800c2300  xor     esi, esi
0x1800c2302  cmp     esi, r14d
0x1800c2305  jnb     loc_1800C242F
0x1800c230b  mov     edi, esi
0x1800c230d  lea     r14, [rsi+rsi*2]
0x1800c2311  lea     rcx, [rsi+rsi*2]
0x1800c2315  mov     eax, [r12+r14*8]
0x1800c2319  mov     [r13+rcx*8+30h], eax
0x1800c231e  lea     r15, ds:0[r14*8]
0x1800c2326  mov     qword ptr [r15+r13+38h], 0
0x1800c232f  lea     rdx, [r13+38h]
0x1800c2333  add     rdx, r15; unsigned __int16 **
0x1800c2336  mov     rcx, [r12+r14*8+8]; unsigned __int16 *
0x1800c233b  call    ?WpnStrCpy@@YAJPEBGPEAPEAG@Z; WpnStrCpy(ushort const *,ushort * *)
0x1800c2340  mov     ebx, eax
0x1800c2342  test    eax, eax
0x1800c2344  js      loc_1800C23E9
0x1800c234a  mov     qword ptr [r13+r14*8+40h], 0
0x1800c2353  mov     rcx, [r12+r14*8+10h]; psz
0x1800c2358  call    cs:__imp_SysAllocString
0x1800c235e  mov     [r13+r14*8+40h], rax
0x1800c2363  test    rax, rax
0x1800c2366  jz      short loc_1800C2388
0x1800c2368  add     rdi, rdi
0x1800c236b  mov     [rbp+rdi*8+0D0h+var_E8], rax
0x1800c2370  mov     rax, [r15+r13+38h]
0x1800c2375  mov     [rbp+rdi*8+0D0h+var_F0], rax
0x1800c237a  inc     esi
0x1800c237c  mov     r14d, [rbp+0D0h+arg_28]
0x1800c2383  jmp     loc_1800C2302
0x1800c2388  mov     ebx, 8007000Eh
0x1800c238d  mov     rcx, [rbp+0D8h]; this
0x1800c2394  mov     r9d, ebx; char *
0x1800c2397  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c239e  mov     edx, 6ABh; void *
0x1800c23a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c23a8  lea     rax, WPP_GLOBAL_Control
0x1800c23af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c23b6  cmp     rcx, rax
0x1800c23b9  jz      loc_1800C2BD2
0x1800c23bf  test    byte ptr [rcx+1Ch], 80h
0x1800c23c3  jz      loc_1800C2BD2
0x1800c23c9  mov     edx, 22h ; '"'
0x1800c23ce  mov     r9d, 8007000Eh
0x1800c23d4  lea     r8, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids
0x1800c23db  mov     rcx, [rcx+10h]
0x1800c23df  call    WPP_SF_d
0x1800c23e4  jmp     loc_1800C2BD2
0x1800c23e9  mov     rcx, [rbp+0D8h]; this
0x1800c23f0  mov     r9d, ebx; char *
0x1800c23f3  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c23fa  mov     edx, 6A2h; void *
0x1800c23ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2404  lea     rax, WPP_GLOBAL_Control
0x1800c240b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2412  cmp     rcx, rax
0x1800c2415  jz      loc_1800C2BD2
0x1800c241b  test    byte ptr [rcx+1Ch], 80h
0x1800c241f  jz      loc_1800C2BD2
0x1800c2425  mov     edx, 21h ; '!'
0x1800c242a  jmp     loc_1800C22F8
0x1800c242f  mov     [r13+2Ch], r14d
0x1800c2433  mov     edx, 0BB8h; DueTime
0x1800c2438  lea     rcx, [rsp+1D0h+var_168]; this
0x1800c243d  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x1800c2442  nop
0x1800c2443  mov     [rsp+1D0h+var_190], 0
0x1800c244c  lea     rdx, [rsp+1D0h+var_190]
0x1800c2451  lea     rcx, [r13+108h]
0x1800c2458  call    ??$CopyLocal@UIBackgroundCopyManager@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UIBackgroundCopyManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IBackgroundCopyManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundCopyManager>>)
0x1800c245d  mov     ebx, eax
0x1800c245f  test    eax, eax
0x1800c2461  jns     short loc_1800C24A9
0x1800c2463  mov     rcx, [rbp+0D8h]; this
0x1800c246a  mov     r9d, eax; char *
0x1800c246d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c2474  mov     edx, 6BDh; void *
0x1800c2479  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c247e  lea     rax, WPP_GLOBAL_Control
0x1800c2485  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c248c  cmp     rcx, rax
0x1800c248f  jz      loc_1800C2BBD
0x1800c2495  test    byte ptr [rcx+1Ch], 80h
0x1800c2499  jz      loc_1800C2BBD
0x1800c249f  mov     edx, 23h ; '#'
0x1800c24a4  jmp     loc_1800C2BA9
0x1800c24a9  mov     rdi, [rsp+1D0h+var_190]
0x1800c24ae  mov     rax, [rdi]
0x1800c24b1  mov     rbx, [rax+18h]
0x1800c24b5  lea     rcx, [rsp+1D0h+var_188]
0x1800c24ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c24bf  lea     r9, [r13+8]
0x1800c24c3  mov     edx, [rbp+0D0h+var_14C]
0x1800c24c6  lea     rcx, ?g_BITSJobDisplayNames@@3PAPEBGA; ushort const * near * g_BITSJobDisplayNames
0x1800c24cd  lea     rax, [rsp+1D0h+var_188]
0x1800c24d2  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x1800c24d7  xor     r8d, r8d
0x1800c24da  mov     rdx, [rcx+rdx*8]
0x1800c24de  mov     rcx, rdi
0x1800c24e1  mov     rax, rbx
0x1800c24e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c24e9  mov     ebx, eax
0x1800c24eb  test    eax, eax
0x1800c24ed  jns     short loc_1800C2535
0x1800c24ef  mov     rcx, [rbp+0D8h]; this
0x1800c24f6  mov     r9d, eax; char *
0x1800c24f9  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c2500  mov     edx, 6C4h; void *
0x1800c2505  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c250a  lea     rax, WPP_GLOBAL_Control
0x1800c2511  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2518  cmp     rcx, rax
0x1800c251b  jz      loc_1800C2BBD
0x1800c2521  test    byte ptr [rcx+1Ch], 80h
0x1800c2525  jz      loc_1800C2BBD
0x1800c252b  mov     edx, 24h ; '$'
0x1800c2530  jmp     loc_1800C2BA9
0x1800c2535  mov     dword ptr [rsp+1D0h+var_178], 1
0x1800c253d  mov     rbx, qword ptr [rsp+1D0h+var_188]
0x1800c2542  mov     rax, [rbx]
0x1800c2545  mov     rdi, [rax]
0x1800c2548  lea     rcx, [rbp+0D0h+var_148]
0x1800c254c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2551  lea     r8, [rbp+0D0h+var_148]
0x1800c2555  lea     rdx, _GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af
0x1800c255c  mov     rcx, rbx
0x1800c255f  mov     rax, rdi
0x1800c2562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2567  mov     ebx, eax
0x1800c2569  test    eax, eax
0x1800c256b  jns     short loc_1800C25B3
0x1800c256d  mov     rcx, [rbp+0D8h]; this
0x1800c2574  mov     r9d, eax; char *
0x1800c2577  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c257e  mov     edx, 6CDh; void *
0x1800c2583  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2588  lea     rax, WPP_GLOBAL_Control
0x1800c258f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2596  cmp     rcx, rax
0x1800c2599  jz      loc_1800C2BBD
0x1800c259f  test    byte ptr [rcx+1Ch], 80h
0x1800c25a3  jz      loc_1800C2BBD
0x1800c25a9  mov     edx, 25h ; '%'
0x1800c25ae  jmp     loc_1800C2BA9
0x1800c25b3  mov     r14d, 4
0x1800c25b9  mov     dword ptr [rbp+0D0h+var_110+4], r14d
0x1800c25bd  xorps   xmm0, xmm0
0x1800c25c0  movdqu  [rbp+0D0h+var_110+8], xmm0
0x1800c25c5  lea     esi, [r14-2]
0x1800c25c9  mov     dword ptr [rbp+0D0h+var_110], esi
0x1800c25cc  mov     rcx, [rbp+0D0h+var_148]
0x1800c25d0  mov     rax, [rcx]
0x1800c25d3  lea     rdx, [rbp+0D0h+var_110]
0x1800c25d7  mov     rax, [rax+148h]
0x1800c25de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c25e3  mov     ebx, eax
0x1800c25e5  test    eax, eax
0x1800c25e7  jns     short loc_1800C262D
0x1800c25e9  mov     rcx, [rbp+0D8h]; this
0x1800c25f0  mov     r9d, eax; char *
0x1800c25f3  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c25fa  mov     edx, 6D7h; void *
0x1800c25ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2604  lea     rax, WPP_GLOBAL_Control
0x1800c260b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2612  cmp     rcx, rax
0x1800c2615  jz      loc_1800C2BBD
0x1800c261b  test    byte ptr [rcx+1Ch], 80h
0x1800c261f  jz      loc_1800C2BBD
0x1800c2625  lea     edx, [rsi+24h]
0x1800c2628  jmp     loc_1800C2BA9
0x1800c262d  mov     rbx, qword ptr [rsp+1D0h+var_188]
0x1800c2632  mov     rax, [rbx]
0x1800c2635  mov     rdi, [rax]
0x1800c2638  lea     rcx, [rsp+1D0h+var_180]
0x1800c263d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2642  lea     r8, [rsp+1D0h+var_180]
0x1800c2647  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x1800c264e  mov     rcx, rbx
0x1800c2651  mov     rax, rdi
0x1800c2654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2659  mov     ebx, eax
0x1800c265b  test    eax, eax
0x1800c265d  jns     short loc_1800C26A5
0x1800c265f  mov     rcx, [rbp+0D8h]; this
0x1800c2666  mov     r9d, eax; char *
0x1800c2669  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c2670  mov     edx, 6DAh; void *
0x1800c2675  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c267a  lea     rax, WPP_GLOBAL_Control
0x1800c2681  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2688  cmp     rcx, rax
0x1800c268b  jz      loc_1800C2BBD
0x1800c2691  test    byte ptr [rcx+1Ch], 80h
0x1800c2695  jz      loc_1800C2BBD
0x1800c269b  mov     edx, 27h ; '''
0x1800c26a0  jmp     loc_1800C2BA9
0x1800c26a5  mov     dword ptr [rbp+0D0h+var_120], esi
0x1800c26a8  mov     rcx, [rsp+1D0h+var_180]
0x1800c26ad  movaps  xmm0, [rbp+0D0h+var_120]
0x1800c26b1  movdqa  [rbp+0D0h+var_140], xmm0
0x1800c26b6  mov     rax, [rcx]
0x1800c26b9  lea     r8, [rbp+0D0h+var_140]
0x1800c26bd  mov     edx, 7
0x1800c26c2  mov     rax, [rax+1A8h]
0x1800c26c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c26ce  mov     ebx, eax
0x1800c26d0  test    eax, eax
0x1800c26d2  jns     short loc_1800C271A
0x1800c26d4  mov     rcx, [rbp+0D8h]; this
0x1800c26db  mov     r9d, eax; char *
0x1800c26de  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c26e5  mov     edx, 6E2h; void *
0x1800c26ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c26ef  lea     rax, WPP_GLOBAL_Control
0x1800c26f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c26fd  cmp     rcx, rax
0x1800c2700  jz      loc_1800C2BBD
0x1800c2706  test    byte ptr [rcx+1Ch], 80h
0x1800c270a  jz      loc_1800C2BBD
0x1800c2710  mov     edx, 28h ; '('
0x1800c2715  jmp     loc_1800C2BA9
0x1800c271a  mov     dword ptr [rbp+0D0h+var_120], 1
0x1800c2721  mov     rcx, [rsp+1D0h+var_180]
0x1800c2726  movaps  xmm6, [rbp+0D0h+var_120]
0x1800c272a  movdqa  [rbp+0D0h+var_140], xmm6
0x1800c272f  mov     rax, [rcx]
0x1800c2732  lea     r8, [rbp+0D0h+var_140]
0x1800c2736  mov     edx, r14d
0x1800c2739  mov     rax, [rax+1A8h]
0x1800c2740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2745  mov     ebx, eax
0x1800c2747  test    eax, eax
  ... truncated ...
```
