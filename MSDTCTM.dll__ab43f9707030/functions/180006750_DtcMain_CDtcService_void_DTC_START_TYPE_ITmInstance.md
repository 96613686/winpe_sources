# DtcMain(CDtcService *,void *,_DTC_START_TYPE,ITmInstance *)

- ea: `0x180006750`
- end: `0x180007536`
- name: `?DtcMain@@YAHPEAVCDtcService@@PEAXW4_DTC_START_TYPE@@PEAUITmInstance@@@Z`
- size: `3558`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010b40`
- `0x180083b00`

## callees

- `0x18000112c`
- `0x180006220`
- `0x1800063b0`
- `0x180006750`
- `0x180007668`
- `0x180007d08`
- `0x180007d90`
- `0x18000862c`
- `0x180008ad8`
- `0x180013c10`
- `0x180013dc8`
- `0x180013e24`
- `0x180015230`
- `0x1800160c4`
- `0x180016270`
- `0x180016344`
- `0x180017fe8`
- `0x180018608`
- `0x18001a210`
- `0x18001cb38`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x180082660`
- `0x180083a7c`
- `0x180084650`
- `0x1800846c0`
- `0x180085488`
- `0x1800856d4`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180006830`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180006830`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006f5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000735e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800073cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800073dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800074ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000735e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800073cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800073dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800074ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180006933`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000694d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180006933`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000694d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800074bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800074bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007478`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007478`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006a31`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800067f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180006804`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800068b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800067f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180006804`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800068b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800068ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800068ad`
- `USER32!GetMessageA` at `0x180007444`
- `USER32!GetMessageA` at `0x18000746e`
- `USER32!GetMessageA` at `0x180007444`
- `USER32!GetMessageA` at `0x18000746e`
- `USER32!DispatchMessageA` at `0x18000745c`
- `USER32!DispatchMessageA` at `0x18000745c`
- `USER32!TranslateMessage` at `0x180007452`
- `USER32!TranslateMessage` at `0x180007452`
- `msvcrt!mbstowcs` at `0x180006dc8`
- `msvcrt!mbstowcs` at `0x180006e04`
- `msvcrt!mbstowcs` at `0x180006dc8`
- `msvcrt!mbstowcs` at `0x180006e04`

## string_xrefs

- `0x1800067df`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006889`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800068ed`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800069f7`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006a7a`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006af1`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006c26`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006caf`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006e9d`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006f49`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180007086`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800070b9`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180007177`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180007245`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18000738a`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180007409`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800074f4`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006847`: `%s\mtxoci.dll`
- `0x180007052`: `DtcSystemShutdown (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@2540): Shutting down with an error`
- `0x180006efa`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180006feb`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800069d8`: `Failed to create CDtcTmManager.`
- `0x180006ad6`: `Failed to get the security configuration options`
- `0x18000705f`: `ITmInit3::Start Completed.`
- `0x180007364`: `DtcCreateStartedEvents failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DtcMain(void *a1, void *a2, int a3, struct ITmInstance *a4)
{
  unsigned int v7; // r12d
  UINT v8; // ebx
  signed int v9; // eax
  unsigned int v10; // esi
  signed int v11; // eax
  CDtcTmManager *v12; // rax
  CDtcTmManager *v13; // rbx
  struct CDtcTmManager *v14; // rcx
  struct CDtcTmManager *v15; // rcx
  signed int v16; // eax
  char *v17; // rdx
  struct CDtcTmManager *v18; // rcx
  int v19; // r13d
  unsigned int v20; // r15d
  unsigned int v21; // r14d
  BOOL v22; // esi
  CDtcService *v23; // rdi
  struct CDtcTmManager *v24; // rcx
  char near **v25; // rcx
  char near **v26; // rax
  char near **v27; // rax
  char near **v28; // rax
  char near **v29; // rax
  char near **v30; // rax
  char near **v31; // rax
  _OWORD *v32; // rbx
  void *v33; // r9
  char *v34; // r14
  unsigned __int16 i; // di
  unsigned __int64 v36; // r12
  __int64 v37; // rax
  size_t v38; // r13
  size_t v39; // rax
  size_t v40; // r15
  wchar_t *v41; // rax
  size_t v42; // rax
  unsigned int v43; // edx
  int v44; // eax
  unsigned int v45; // edx
  int v46; // eax
  CTrace *v47; // rcx
  CUITrace *v48; // rcx
  __int64 v49; // rcx
  unsigned int v50; // eax
  __int64 v51; // rcx
  unsigned int v52; // eax
  __int64 v53; // rcx
  unsigned int v54; // eax
  void *StartedEvents; // rax
  struct CDtcTmManager *v56; // rcx
  char *v58; // [rsp+20h] [rbp-E0h]
  char *v59; // [rsp+20h] [rbp-E0h]
  char *v60; // [rsp+20h] [rbp-E0h]
  char *v61; // [rsp+20h] [rbp-E0h]
  char *v62; // [rsp+20h] [rbp-E0h]
  char *v63; // [rsp+20h] [rbp-E0h]
  char *v64; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+28h] [rbp-D8h]
  size_t Sizee; // [rsp+28h] [rbp-D8h]
  size_t Sizea; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *Sizeb; // [rsp+28h] [rbp-D8h]
  size_t Sizec; // [rsp+28h] [rbp-D8h]
  size_t Sized; // [rsp+28h] [rbp-D8h]
  int v71; // [rsp+30h] [rbp-D0h]
  void *Src; // [rsp+38h] [rbp-C8h]
  int v73; // [rsp+40h] [rbp-C0h]
  unsigned int inited; // [rsp+60h] [rbp-A0h] BYREF
  int v75; // [rsp+64h] [rbp-9Ch]
  int v76[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v77; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v78; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v79; // [rsp+78h] [rbp-88h] BYREF
  int v80; // [rsp+7Ch] [rbp-84h]
  void *Block; // [rsp+80h] [rbp-80h]
  HANDLE hEvent; // [rsp+88h] [rbp-78h]
  tagMSG Msg; // [rsp+90h] [rbp-70h] BYREF
  char *Source[8]; // [rsp+C0h] [rbp-40h]
  CHAR LibFileName[272]; // [rsp+100h] [rbp+0h] BYREF

  v80 = a3;
  hEvent = a2;
  Block = a1;
  v7 = 0;
  inited = 0;
  memset(&Msg, 0, sizeof(Msg));
  v77 = 0;
  v78 = 0;
  v79 = 0;
  TraceStringInline(3, 6, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 1452, L"DtcMain", 0, L"DtcMain IN");
  v8 = SetErrorMode(0);
  SetErrorMode(v8 | 1);
  memset_0(LibFileName, 0, 0x105u);
  if ( !dword_180166308 )
  {
    GetSystemDirectoryA(Buffer, 0x104u);
    dword_180166308 = 1;
  }
  v9 = StringCchPrintfA(LibFileName, 0x105u, "%s\\mtxoci.dll", Buffer);
  inited = v9;
  if ( v9 >= 0 )
  {
    LoadLibraryExA(LibFileName, 0, 0);
    SetErrorMode(v8);
    v11 = VerifyAccountInfo(a4);
    inited = v11;
    if ( v11 < 0 )
    {
      LODWORD(Size) = v11;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        1479,
        L"DtcMain",
        Size,
        L"VerifyAccountInfo FAILED");
      inited = 0;
    }
    CheckAndProcessRestore(a4);
    g_dwMessagePumpThread = GetCurrentThreadId();
    if ( a3 == 2 )
      EnableStdIO();
    z_hCleanUpDoneEvent = CreateEventA(0, 1, 0, 0);
    z_hServiceStopDone = CreateEventA(0, 1, 0, 0);
    v12 = (CDtcTmManager *)operator new(0x260u);
    v13 = v12;
    *(_QWORD *)v76 = v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = 0;
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 69) = 0;
      *((_QWORD *)v12 + 72) = 0;
      *((_QWORD *)v12 + 73) = 0;
      *((_QWORD *)v12 + 1) = 0;
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 74) = 0;
      *((_QWORD *)v12 + 70) = 0;
      *((_QWORD *)v12 + 71) = a4;
      (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)a4 + 8LL))(a4);
    }
    else
    {
      v13 = 0;
    }
    if ( v13 )
    {
      inited = CoInitializeEx(0, 0);
      if ( (inited & 0x80000000) != 0 )
      {
        locprint(0x1001u, 0xC0001070, 0, 0, v58);
        LODWORD(Size) = inited;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          1515,
          L"DtcMain",
          Size,
          L"CoInitializeEx failed.");
        DtcSystemShutdown(v15, (struct CDtcService *)a1, 0xC0001070, 1);
      }
      v16 = (*(__int64 (__fastcall **)(struct ITmInstance *, unsigned int *, unsigned int *, unsigned int *))(*(_QWORD *)a4 + 280LL))(
              a4,
              &v77,
              &v78,
              &v79);
      inited = v16;
      if ( v16 < 0 )
      {
        LODWORD(Size) = v16;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          1526,
          L"DtcMain",
          Size,
          L"Failed to get the security configuration options");
        locprint(0x1001u, 0xC0001142, 4u, &inited, v59);
        DtcSystemShutdown(v18, (struct CDtcService *)a1, 0xC0001142, 1);
      }
      v75 = 0;
      v76[0] = 0;
      v19 = 0;
      if ( (v77 & 1) != 0 )
      {
        v20 = (v77 >> 1) & 1;
        v7 = (v77 >> 3) & 1;
        if ( (v77 & 4) != 0 )
        {
          v75 = (v77 >> 6) & 1;
          if ( (v77 & 0x20) != 0 )
            v76[0] = 1;
          else
            v75 = (v77 >> 6) & 1;
        }
        if ( (v77 & 0x10) != 0 )
          v19 = 1;
      }
      else
      {
        v20 = 0;
      }
      v21 = v78 & 1;
      v22 = (v79 & 1) == 0;
      inited = CDtcTmManager::InitTm(v13, v17, v77, v78, v79, v20, v7, (int)Src, v73, v19, v21);
      if ( inited )
      {
        IssueSecurityConfigEvent(v20, v7, v75, v76[0], v19, v21, v22);
        LODWORD(Sizee) = inited;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          1603,
          L"DtcMain",
          Sizee,
          L"InitTm failed.");
        v23 = (CDtcService *)Block;
        DtcSystemShutdown(v24, (struct CDtcService *)Block, 0xC000103B, 1);
        if ( v23 )
        {
          CDtcService::~CDtcService(v23);
          operator delete(v23);
        }
        CDtcTmManager::~CDtcTmManager(v13);
        operator delete(v13);
        v10 = -1;
      }
      else
      {
        TraceStringInline(
          3,
          4,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          1611,
          L"DtcMain",
          0,
          L"TM initialized.");
        if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)v13 + 32LL))(
                *(_QWORD *)v13,
                *((_QWORD *)v13 + 3),
                (_QWORD *)v13 + 4) )
        {
          v25 = &g_szTrue;
          v26 = &g_szTrue;
          if ( v20 != 1 )
            v26 = &g_szFalse;
          Source[0] = (char *)v26;
          v27 = &g_szTrue;
          if ( v7 != 1 )
            v27 = &g_szFalse;
          Source[1] = (char *)v27;
          v28 = &g_szTrue;
          if ( v75 != 1 )
            v28 = &g_szFalse;
          Source[2] = (char *)v28;
          v29 = &g_szTrue;
          if ( v76[0] != 1 )
            v29 = &g_szFalse;
          Source[3] = (char *)v29;
          v30 = &g_szTrue;
          if ( v19 != 1 )
            v30 = &g_szFalse;
          Source[4] = (char *)v30;
          v31 = &g_szTrue;
          if ( !v21 )
            v31 = &g_szFalse;
          Source[5] = (char *)v31;
          if ( !v22 )
            v25 = &g_szFalse;
          Source[6] = (char *)v25;
          v32 = operator new[](0x38u);
          if ( v32 )
          {
            *v32 = 0;
            v32[1] = 0;
            v32[2] = 0;
            *((_QWORD *)v32 + 6) = 0;
            v34 = 0;
            for ( i = 0; ; ++i )
            {
              if ( i >= 7u )
              {
                LODWORD(Sizea) = (_DWORD)v34;
                DtcWriteToEventLoggerExW(
                  4u,
                  2u,
                  0x4000D023u,
                  v33,
                  7u,
                  Sizea,
                  (const unsigned __int16 **)v32,
                  v34,
                  (int)v34);
                FreeWideStringArray(v32);
                goto LABEL_60;
              }
              v36 = 8LL * i;
              v34 = Source[v36 / 8];
              if ( v34 )
              {
                v37 = -1;
                do
                  ++v37;
                while ( v34[v37] );
                v38 = v37 + 1;
                v39 = mbstowcs(0, Source[i], v37 + 1);
                v40 = v39;
                if ( v39 == -1
                  || (v41 = (wchar_t *)operator new[](saturated_mul(v39 + 1, 2u)),
                      (*(_QWORD *)((char *)v32 + v36) = v41) == 0) )
                {
                  v34 = 0;
LABEL_58:
                  FreeWideStringArray(v32);
LABEL_60:
                  LODWORD(Sizea) = -2147418113;
                  TraceStringInline(
                    3,
                    1,
                    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                    1634,
                    L"DtcMain",
                    Sizea,
                    L"TmInit::Start failed.");
                  if ( z_pTrace )
                  {
                    v44 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, char *, char *))(*(_QWORD *)z_pTrace + 24LL))(
                            z_pTrace,
                            4097,
                            1,
                            0,
                            -1073737712,
                            (_DWORD)v34,
                            v34,
                            v34);
                    if ( v44 < 0 )
                      TraceFile(
                        v44,
                        "failed in z_pTrace->Trace",
                        "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                        0x961u);
                  }
                  else
                  {
                    DtcWriteToEventLoggerW(1u, v43, 0xC0001010, 0, v34, Sizeb, v71);
                  }
                  TraceStringInline(
                    3,
                    6,
                    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                    2520,
                    L"DtcSystemShutdown",
                    v34,
                    L"In");
                  v76[0] = GetCurrentProcessId();
                  CTrace::TraceEvent((CTrace *)&g_Trace, 1u, 0, &stru_180125D68, 0xCu);
                  if ( z_pTrace )
                  {
                    v46 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _QWORD, char *, char *))(*(_QWORD *)z_pTrace + 24LL))(
                            z_pTrace,
                            4099,
                            1,
                            0,
                            1073745935,
                            (unsigned int)v34,
                            v34,
                            v34);
                    if ( v46 < 0 )
                      TraceFile(
                        v46,
                        "failed in z_pTrace->Trace",
                        "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                        0x961u);
                  }
                  else
                  {
                    DtcWriteToEventLoggerW(4u, v45, 0x4000100Fu, 0, v34, (unsigned __int16 *)4, (int)v76);
                  }
                  CTrace::Terminate(v47);
                  CUITrace::Terminate(v48);
                  TraceLoggingUnregister_EventUnregister();
                  if ( Block )
                    CDtcService::ReportStatus((CDtcService *)Block, 1u, 0xC0001010, 0, (unsigned int)v34, 1);
                  DtcInternalErrorW(
                    L"DtcSystemShutdown (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@2540): Shutting down with an error");
                }
                v42 = mbstowcs(v41, v34, v38);
                v34 = 0;
                if ( v42 != v40 )
                  goto LABEL_58;
                *(_WORD *)(*(_QWORD *)((char *)v32 + v36) + 2 * v40) = 0;
              }
            }
          }
          v34 = 0;
          goto LABEL_60;
        }
        TraceStringInline(
          3,
          4,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          1643,
          L"DtcMain",
          0,
          L"ITmInit3::Start Completed.");
        v49 = *((_QWORD *)v13 + 1);
        if ( v49 )
        {
          v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 32LL))(v49);
          inited = v50;
          if ( v50 )
          {
            LODWORD(Sizec) = v50;
            TraceStringInline(
              3,
              2,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              1650,
              L"DtcMain",
              Sizec,
              L"XaTM Start failed.");
            locprint(2u, 0xC0001064, 0, 0, v60);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 1) + 16LL))(*((_QWORD *)v13 + 1));
            *((_QWORD *)v13 + 1) = 0;
          }
          else
          {
            TraceStringInline(
              3,
              4,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              1658,
              L"DtcMain",
              0,
              L"XaTM started.");
          }
        }
        v51 = *((_QWORD *)v13 + 2);
        if ( v51 )
        {
          v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51);
          inited = v52;
          if ( v52 )
          {
            LODWORD(Sizec) = v52;
            TraceStringInline(
              3,
              2,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              1668,
              L"DtcMain",
              Sizec,
              L"Tip Gateway Start failed.");
            locprint(2u, 0xC0001069, inited, 0, v61);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 2) + 16LL))(*((_QWORD *)v13 + 2));
            *((_QWORD *)v13 + 2) = 0;
          }
          else
          {
            TraceStringInline(
              3,
              4,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              1676,
              L"DtcMain",
              0,
              L"TipGateway started.");
            _InterlockedExchange(&g_bTipFunctionalityWorking, 1);
          }
        }
        v53 = *((_QWORD *)v13 + 70);
        if ( v53 )
        {
          v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 32LL))(v53);
          inited = v54;
          if ( v54 )
          {
            LODWORD(Sizec) = v54;
            TraceStringInline(
              3,
              2,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              1687,
              L"DtcMain",
              Sizec,
              L"Transactions Bridge Start failed.");
            locprint(2u, 0xC000102D, inited, 0, v62);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 70) + 16LL))(*((_QWORD *)v13 + 70));
            *((_QWORD *)v13 + 70) = 0;
          }
          else
          {
            TraceStringInline(
              3,
              4,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              1695,
              L"DtcMain",
              0,
              L"TransactionBridge started.");
          }
        }
        IssueStartupEvent(a4, v20, v7, v75, v76[0], v19, v21, v77, v22, *((_QWORD *)v13 + 70) != 0);
        CTrace::PrintTraceSettings((CTrace *)&g_Trace);
        StartedEvents = DtcCreateStartedEvents(a4);
        g_hNamedEvent = StartedEvents;
        if ( StartedEvents )
        {
          if ( hEvent )
          {
            SetEvent(hEvent);
            StartedEvents = g_hNamedEvent;
          }
          SetEvent(StartedEvents);
          TraceStringInline(
            3,
            3,
            L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            1740,
            L"DtcMain",
            0,
            L"Dtc started.");
          if ( v80 == 2 )
            locprint(0x1004u, 0x4000100Cu, 0, 0, v64);
          while ( GetMessageA(&Msg, 0, 0, 0) )
          {
            TranslateMessage(&Msg);
            DispatchMessageA(&Msg);
          }
          CoUninitialize();
          DtcSystemShutdown(v56, (struct CDtcService *)Block, 0, 0);
          CDtcTmManager::~CDtcTmManager(v13);
          operator delete(v13);
          if ( (_DWORD)z_fService )
          {
            SetEvent(z_hCleanUpDoneEvent);
            WaitForSingleObject(z_hServiceStopDone, 0x7D0u);
          }
          CloseNetpEventLogHandle();
          v10 = 0;
        }
        else
        {
          if ( (_DWORD)z_fService )
            SetEvent(z_hCleanUpDoneEvent);
          LODWORD(Sized) = inited;
          TraceStringInline(
            3,
            1,
            L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            1726,
            L"DtcMain",
            Sized,
            L"DtcCreateStartedEvents failed.");
          locprint(0x1001u, 0xC000101B, 0, 0, v63);
          v10 = -1;
        }
      }
    }
    else
    {
      locprint(0x1001u, 0xC0001007, 0, 0, v58);
      LODWORD(Size) = inited;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        1504,
        L"DtcMain",
        Size,
        L"Failed to create CDtcTmManager.");
      DtcSystemShutdown(v14, (struct CDtcService *)a1, 0xC0001006, 1);
      v10 = -1;
    }
  }
  else
  {
    v10 = 0;
    LODWORD(Size) = v9;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      1465,
      L"DtcMain",
      Size,
      L"StringCbPrintfA FAILED");
  }
  LODWORD(Src) = v10;
  TraceStringInline(3, 6, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 1794, L"DtcMain", 0, L"DtcMain %d OUT", Src);
  return v10;
}

```

## disassembly

```asm
0x180006750  mov     [rsp-8+arg_10], rbx
0x180006755  push    rbp
0x180006756  push    rsi
0x180006757  push    rdi
0x180006758  push    r12
0x18000675a  push    r13
0x18000675c  push    r14
0x18000675e  push    r15
0x180006760  lea     rbp, [rsp-120h]
0x180006768  sub     rsp, 220h
0x18000676f  mov     rax, cs:__security_cookie
0x180006776  xor     rax, rsp
0x180006779  mov     [rbp+150h+var_40], rax
0x180006780  mov     rdi, r9
0x180006783  mov     esi, r8d
0x180006786  mov     [rsp+250h+var_1D4], r8d
0x18000678b  mov     [rbp+150h+hEvent], rdx
0x18000678f  mov     r14, rcx
0x180006792  mov     [rbp+150h+Block], rcx
0x180006796  xor     r12d, r12d
0x180006799  mov     [rsp+250h+var_1F0], r12d
0x18000679e  xorps   xmm0, xmm0
0x1800067a1  movups  xmmword ptr [rbp+150h+Msg.hwnd], xmm0
0x1800067a5  movups  xmmword ptr [rbp+150h+Msg.wParam], xmm0
0x1800067a9  movups  xmmword ptr [rbp+150h+Msg.time], xmm0
0x1800067ad  mov     [rsp+250h+var_1E0], r12d
0x1800067b2  mov     [rsp+250h+var_1DC], r12d
0x1800067b7  mov     [rsp+250h+var_1D8], r12d
0x1800067bc  lea     rax, aDtcmainIn; "DtcMain IN"
0x1800067c3  mov     [rsp+250h+var_220], rax
0x1800067c8  mov     [rsp+250h+Size], r12
0x1800067cd  lea     rax, aDtcmain; "DtcMain"
0x1800067d4  mov     [rsp+250h+var_230], rax
0x1800067d9  mov     r9d, 5ACh
0x1800067df  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800067e6  mov     edx, 6
0x1800067eb  mov     ecx, 3
0x1800067f0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800067f5  xor     ecx, ecx; uMode
0x1800067f7  call    cs:__imp_SetErrorMode
0x1800067fd  mov     ebx, eax
0x1800067ff  mov     ecx, eax
0x180006801  or      ecx, 1; uMode
0x180006804  call    cs:__imp_SetErrorMode
0x18000680a  xor     edx, edx; Val
0x18000680c  mov     r8d, 105h; Size
0x180006812  lea     rcx, [rbp+150h+LibFileName]; void *
0x180006816  call    memset_0
0x18000681b  cmp     cs:dword_180166308, r12d
0x180006822  jnz     short loc_180006840
0x180006824  mov     edx, 104h; uSize
0x180006829  lea     rcx, Buffer; lpBuffer
0x180006830  call    cs:__imp_GetSystemDirectoryA
0x180006836  mov     cs:dword_180166308, 1
0x180006840  lea     r9, Buffer
0x180006847  lea     r8, aSMtxociDll; "%s\\mtxoci.dll"
0x18000684e  mov     edx, 105h; unsigned __int64
0x180006853  lea     rcx, [rbp+150h+LibFileName]; char *
0x180006857  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000685c  mov     [rsp+250h+var_1F0], eax
0x180006860  test    eax, eax
0x180006862  jns     short loc_1800068A4
0x180006864  mov     esi, r12d
0x180006867  lea     rcx, aStringcbprintf; "StringCbPrintfA FAILED"
0x18000686e  mov     [rsp+250h+var_220], rcx
0x180006873  mov     dword ptr [rsp+250h+Size], eax
0x180006877  lea     rax, aDtcmain; "DtcMain"
0x18000687e  mov     [rsp+250h+var_230], rax
0x180006883  mov     r9d, 5B9h
0x180006889  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180006890  mov     edx, 1
0x180006895  mov     ecx, 3
0x18000689a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000689f  jmp     loc_1800074CD
0x1800068a4  xor     r8d, r8d; dwFlags
0x1800068a7  xor     edx, edx; hFile
0x1800068a9  lea     rcx, [rbp+150h+LibFileName]; lpLibFileName
0x1800068ad  call    cs:__imp_LoadLibraryExA
0x1800068b3  mov     ecx, ebx; uMode
0x1800068b5  call    cs:__imp_SetErrorMode
0x1800068bb  mov     rcx, rdi; struct ITmInstance *
0x1800068be  call    ?VerifyAccountInfo@@YAJPEAUITmInstance@@@Z; VerifyAccountInfo(ITmInstance *)
0x1800068c3  mov     [rsp+250h+var_1F0], eax
0x1800068c7  lea     r15, aDtcmain; "DtcMain"
0x1800068ce  test    eax, eax
0x1800068d0  jns     short loc_180006908
0x1800068d2  lea     rcx, aVerifyaccounti_2; "VerifyAccountInfo FAILED"
0x1800068d9  mov     [rsp+250h+var_220], rcx
0x1800068de  mov     dword ptr [rsp+250h+Size], eax
0x1800068e2  mov     [rsp+250h+var_230], r15; char *
0x1800068e7  mov     r9d, 5C7h
0x1800068ed  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800068f4  mov     edx, 1
0x1800068f9  mov     ecx, 3
0x1800068fe  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006903  mov     [rsp+250h+var_1F0], r12d
0x180006908  mov     rcx, rdi; struct ITmInstance *
0x18000690b  call    ?CheckAndProcessRestore@@YAXPEAUITmInstance@@@Z; CheckAndProcessRestore(ITmInstance *)
0x180006910  call    cs:__imp_GetCurrentThreadId
0x180006916  mov     cs:?g_dwMessagePumpThread@@3KA, eax; ulong g_dwMessagePumpThread
0x18000691c  cmp     esi, 2
0x18000691f  jnz     short loc_180006926
0x180006921  call    ?EnableStdIO@@YAXXZ; EnableStdIO(void)
0x180006926  xor     r9d, r9d; lpName
0x180006929  xor     r8d, r8d; bInitialState
0x18000692c  mov     edx, 1; bManualReset
0x180006931  xor     ecx, ecx; lpEventAttributes
0x180006933  call    cs:__imp_CreateEventA
0x180006939  mov     cs:?z_hCleanUpDoneEvent@@3PEAXEA, rax; void * z_hCleanUpDoneEvent
0x180006940  xor     r9d, r9d; lpName
0x180006943  xor     r8d, r8d; bInitialState
0x180006946  mov     edx, 1; bManualReset
0x18000694b  xor     ecx, ecx; lpEventAttributes
0x18000694d  call    cs:__imp_CreateEventA
0x180006953  mov     cs:?z_hServiceStopDone@@3PEAXEA, rax; void * z_hServiceStopDone
0x18000695a  mov     ecx, 260h; Size
0x18000695f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006964  mov     rbx, rax
0x180006967  mov     qword ptr [rsp+250h+var_1E8], rax
0x18000696c  test    rax, rax
0x18000696f  jz      short loc_1800069BB
0x180006971  mov     [rax], r12
0x180006974  mov     [rax+18h], r12
0x180006978  mov     [rax+228h], r12
0x18000697f  mov     [rax+240h], r12
0x180006986  mov     [rax+248h], r12
0x18000698d  mov     [rax+8], r12
0x180006991  mov     [rax+10h], r12
0x180006995  mov     [rax+250h], r12
0x18000699c  mov     [rax+230h], r12
0x1800069a3  mov     [rax+238h], rdi
0x1800069aa  mov     rax, [rdi]
0x1800069ad  mov     rcx, rdi
0x1800069b0  mov     rax, [rax+8]
0x1800069b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b9  jmp     short loc_1800069BE
0x1800069bb  mov     rbx, r12
0x1800069be  test    rbx, rbx
0x1800069c1  jnz     short loc_180006A2D
0x1800069c3  xor     r9d, r9d; void *
0x1800069c6  xor     r8d, r8d; unsigned int
0x1800069c9  mov     edx, 0C0001007h; unsigned int
0x1800069ce  mov     ecx, 1001h; unsigned int
0x1800069d3  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x1800069d8  lea     rax, aFailedToCreate_0; "Failed to create CDtcTmManager."
0x1800069df  mov     [rsp+250h+var_220], rax
0x1800069e4  mov     eax, [rsp+250h+var_1F0]
0x1800069e8  mov     dword ptr [rsp+250h+Size], eax
0x1800069ec  mov     [rsp+250h+var_230], r15
0x1800069f1  mov     r9d, 5E0h
0x1800069f7  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800069fe  mov     edx, 1
0x180006a03  mov     ecx, 3
0x180006a08  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006a0d  mov     r9d, 1; int
0x180006a13  mov     r8d, 0C0001006h; unsigned int
0x180006a19  mov     rdx, r14; struct CDtcService *
0x180006a1c  call    ?DtcSystemShutdown@@YAXPEAVCDtcTmManager@@PEAVCDtcService@@KH@Z; DtcSystemShutdown(CDtcTmManager *,CDtcService *,ulong,int)
0x180006a21  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180006a28  jmp     loc_1800074CD
0x180006a2d  xor     edx, edx; dwCoInit
0x180006a2f  xor     ecx, ecx; pvReserved
0x180006a31  call    cs:__imp_CoInitializeEx
0x180006a37  mov     [rsp+250h+var_1F0], eax
0x180006a3b  test    eax, eax
0x180006a3d  jns     short loc_180006AA6
0x180006a3f  xor     r9d, r9d; void *
0x180006a42  xor     r8d, r8d; unsigned int
0x180006a45  mov     edx, 0C0001070h; unsigned int
0x180006a4a  mov     ecx, 1001h; unsigned int
0x180006a4f  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x180006a54  lea     rax, aCoinitializeex; "CoInitializeEx failed."
0x180006a5b  mov     [rsp+250h+var_220], rax
0x180006a60  mov     eax, [rsp+250h+var_1F0]
0x180006a64  mov     dword ptr [rsp+250h+Size], eax
0x180006a68  lea     rsi, aDtcmain; "DtcMain"
0x180006a6f  mov     [rsp+250h+var_230], rsi
0x180006a74  mov     r9d, 5EBh
0x180006a7a  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180006a81  mov     edx, 1
0x180006a86  mov     ecx, 3
0x180006a8b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006a90  mov     r9d, 1; int
0x180006a96  mov     r8d, 0C0001070h; unsigned int
0x180006a9c  mov     rdx, r14; struct CDtcService *
0x180006a9f  call    ?DtcSystemShutdown@@YAXPEAVCDtcTmManager@@PEAVCDtcService@@KH@Z; DtcSystemShutdown(CDtcTmManager *,CDtcService *,ulong,int)
0x180006aa4  jmp     short loc_180006AAD
0x180006aa6  lea     rsi, aDtcmain; "DtcMain"
0x180006aad  mov     rax, [rdi]
0x180006ab0  lea     r9, [rsp+250h+var_1D8]
0x180006ab5  lea     r8, [rsp+250h+var_1DC]
0x180006aba  lea     rdx, [rsp+250h+var_1E0]
0x180006abf  mov     rcx, rdi
0x180006ac2  mov     rax, [rax+118h]
0x180006ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ace  mov     [rsp+250h+var_1F0], eax
0x180006ad2  test    eax, eax
0x180006ad4  jns     short loc_180006B35
0x180006ad6  lea     rcx, aFailedToGetThe_3; "Failed to get the security configuratio"...
0x180006add  mov     [rsp+250h+var_220], rcx
0x180006ae2  mov     dword ptr [rsp+250h+Size], eax
0x180006ae6  mov     [rsp+250h+var_230], rsi; char *
0x180006aeb  mov     r9d, 5F6h
0x180006af1  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180006af8  mov     edx, 1
0x180006afd  mov     ecx, 3
0x180006b02  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006b07  lea     r9, [rsp+250h+var_1F0]; void *
0x180006b0c  mov     edx, 0C0001142h; unsigned int
0x180006b11  mov     ecx, 1001h; unsigned int
0x180006b16  mov     r8d, 4; unsigned int
0x180006b1c  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x180006b21  mov     r9d, 1; int
0x180006b27  mov     r8d, 0C0001142h; unsigned int
0x180006b2d  mov     rdx, r14; struct CDtcService *
0x180006b30  call    ?DtcSystemShutdown@@YAXPEAVCDtcTmManager@@PEAVCDtcService@@KH@Z; DtcSystemShutdown(CDtcTmManager *,CDtcService *,ulong,int)
0x180006b35  mov     [rsp+250h+var_1EC], r12d
0x180006b3a  mov     [rsp+250h+var_1E8], r12d
0x180006b3f  mov     r13d, r12d
0x180006b42  mov     r8d, [rsp+250h+var_1E0]; unsigned int
0x180006b47  test    r8b, 1
0x180006b4b  jz      short loc_180006B97
0x180006b4d  mov     r15d, r8d
0x180006b50  shr     r15d, 1
0x180006b53  and     r15d, 1
0x180006b57  mov     r12d, r8d
0x180006b5a  shr     r12d, 3
0x180006b5e  and     r12d, 1
0x180006b62  test    r8b, 4
0x180006b66  jz      short loc_180006B89
0x180006b68  mov     eax, r8d
0x180006b6b  shr     eax, 6
0x180006b6e  and     eax, 1
0x180006b71  mov     [rsp+250h+var_1EC], eax
0x180006b75  test    r8b, 20h
0x180006b79  jz      short loc_180006B85
0x180006b7b  mov     [rsp+250h+var_1E8], 1
0x180006b83  jmp     short loc_180006B89
0x180006b85  mov     [rsp+250h+var_1EC], eax
0x180006b89  test    r8b, 10h
0x180006b8d  jz      short loc_180006B9A
0x180006b8f  mov     r13d, 1
0x180006b95  jmp     short loc_180006B9A
0x180006b97  mov     r15d, r12d
0x180006b9a  mov     r9d, [rsp+250h+var_1DC]; unsigned int
0x180006b9f  mov     r14d, r9d
0x180006ba2  and     r14d, 1
0x180006ba6  mov     eax, [rsp+250h+var_1D8]
0x180006baa  mov     esi, eax
0x180006bac  not     esi
0x180006bae  and     esi, 1
0x180006bb1  mov     [rsp+250h+var_200], r14d; int
0x180006bb6  mov     [rsp+250h+var_208], r13d; int
0x180006bbb  mov     dword ptr [rsp+250h+var_220], r12d; int
0x180006bc0  mov     dword ptr [rsp+250h+Size], r15d; int
0x180006bc5  mov     dword ptr [rsp+250h+var_230], eax; unsigned int
0x180006bc9  mov     rcx, rbx; this
0x180006bcc  call    ?InitTm@CDtcTmManager@@QEAAJPEADKKKHHHHHH@Z; CDtcTmManager::InitTm(char *,ulong,ulong,ulong,int,int,int,int,int,int)
0x180006bd1  mov     [rsp+250h+var_1F0], eax
0x180006bd5  test    eax, eax
0x180006bd7  jz      loc_180006C88
0x180006bdd  mov     dword ptr [rsp+250h+var_220], esi
0x180006be1  mov     dword ptr [rsp+250h+Size], r14d
0x180006be6  mov     dword ptr [rsp+250h+var_230], r13d
0x180006beb  mov     r9d, [rsp+250h+var_1E8]
0x180006bf0  mov     r8d, [rsp+250h+var_1EC]
0x180006bf5  mov     edx, r12d
0x180006bf8  mov     ecx, r15d
0x180006bfb  call    IssueSecurityConfigEvent
0x180006c00  lea     rax, aInittmFailed; "InitTm failed."
0x180006c07  mov     [rsp+250h+var_220], rax
0x180006c0c  mov     eax, [rsp+250h+var_1F0]
0x180006c10  mov     dword ptr [rsp+250h+Size], eax
0x180006c14  lea     rax, aDtcmain; "DtcMain"
0x180006c1b  mov     [rsp+250h+var_230], rax
0x180006c20  mov     r9d, 643h
0x180006c26  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180006c2d  mov     edx, 1
0x180006c32  mov     ecx, 3
0x180006c37  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006c3c  mov     r9d, 1; int
0x180006c42  mov     r8d, 0C000103Bh; unsigned int
0x180006c48  mov     rdi, [rbp+150h+Block]
0x180006c4c  mov     rdx, rdi; struct CDtcService *
0x180006c4f  call    ?DtcSystemShutdown@@YAXPEAVCDtcTmManager@@PEAVCDtcService@@KH@Z; DtcSystemShutdown(CDtcTmManager *,CDtcService *,ulong,int)
0x180006c54  test    rdi, rdi
0x180006c57  jz      short loc_180006C69
0x180006c59  mov     rcx, rdi; this
0x180006c5c  call    ??1CDtcService@@QEAA@XZ; CDtcService::~CDtcService(void)
0x180006c61  mov     rcx, rdi; Block
0x180006c64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006c69  mov     rcx, rbx; this
0x180006c6c  call    ??1CDtcTmManager@@QEAA@XZ; CDtcTmManager::~CDtcTmManager(void)
0x180006c71  mov     rcx, rbx; Block
0x180006c74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006c79  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180006c80  xor     r12d, r12d
0x180006c83  jmp     loc_1800074CD
0x180006c88  lea     rax, aTmInitialized; "TM initialized."
0x180006c8f  mov     [rsp+250h+var_220], rax
  ... truncated ...
```
