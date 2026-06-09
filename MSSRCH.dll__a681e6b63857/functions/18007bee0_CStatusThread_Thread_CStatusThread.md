# CStatusThread::Thread(CStatusThread *)

- ea: `0x18007bee0`
- end: `0x18007cad3`
- name: `?Thread@CStatusThread@@SAJPEAV1@@Z`
- size: `3059`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `59`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a23c`
- `0x18000b9cc`
- `0x18000c760`
- `0x18000d15c`
- `0x18000ec08`
- `0x18000ec50`
- `0x180019bb0`
- `0x180049b00`
- `0x180052460`
- `0x180052c3c`
- `0x18006028c`
- `0x180061f78`
- `0x18006a040`
- `0x18006a618`
- `0x18007bee0`
- `0x18007cadc`
- `0x18007cbf4`
- `0x18007cc78`
- `0x18007d088`
- `0x1800995c8`
- `0x1800c1be8`
- `0x1800cafcc`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800d4124`
- `0x1800e5d84`
- `0x1800f3140`
- `0x180100564`
- `0x180104754`
- `0x18010a8a8`
- `0x18010aa10`
- `0x18010c1a0`
- `0x18010cb1c`
- `0x18010e858`
- `0x180112b00`
- `0x180112fa4`
- `0x18011537c`
- `0x1801244c0`
- `0x1801485ec`
- `0x180180754`
- `0x1801bfa90`
- `0x1801c1748`
- `0x1801c21ec`
- `0x1801c6e60`
- `0x1801c800c`
- `0x1801ca410`
- `0x1801cae14`
- `0x1801d633c`
- `0x1801d6bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c00b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c00b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bfe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bfe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007bf75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007bf75`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007bf9f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007bf9f`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18007bf85`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18007bf85`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007bf6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007bf6a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007caa8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007caa8`

## string_xrefs

- `0x18007bf7e`: `Gatherer Status Thread`
- `0x18007bf4e`: `[SrchGatherPI] Status Thread Started\n`
- `0x18007ca83`: `[SrchGatherPI] Status Thread Stopped\n`
- `0x18007c2a7`: `MSSrch.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CStatusThread::Thread(char *Parameter, __int64 a2, __int64 a3, const wchar_t *a4)
{
  char *v4; // rbx
  int v5; // r14d
  HRESULT v6; // edi
  HANDLE CurrentThread; // rax
  void *v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  CLnkList *v10; // r15
  struct CSingleLink *v11; // r13
  CGatherer **v12; // r12
  int v13; // ecx
  CSyncReadWrite *v14; // r15
  __int64 v15; // rcx
  struct CCrawl *v16; // rbx
  int v17; // ecx
  unsigned int v18; // esi
  unsigned int v19; // esi
  unsigned int v20; // esi
  unsigned int v21; // esi
  unsigned int v22; // esi
  unsigned int v23; // esi
  unsigned int v24; // esi
  unsigned int v25; // esi
  CGatherer *v26; // rsi
  volatile __int32 *v27; // rcx
  int v28; // edx
  int v29; // esi
  int v30; // r8d
  __int64 v31; // r15
  struct CGatherPluginMgr *v32; // rsi
  __int64 v33; // r15
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  volatile __int32 *v37; // rcx
  const wchar_t *v38; // r9
  CGatherer *v39; // rsi
  unsigned int v40; // esi
  unsigned int v41; // esi
  unsigned int v42; // esi
  unsigned int v43; // esi
  unsigned int v44; // esi
  unsigned int v45; // esi
  unsigned int v46; // esi
  int v47; // esi
  CGatherer *v48; // rcx
  __int64 v49; // r15
  void (__fastcall *v50)(__int64, __int64, const size_t *, _QWORD, __int128 *, int, int, _DWORD, const size_t *); // r14
  int v51; // esi
  int v52; // esi
  volatile __int32 *v53; // rcx
  unsigned int v54; // edx
  __int64 v55; // rdx
  unsigned int v56; // edx
  __int64 v57; // r8
  const wchar_t *v58; // r9
  __int128 *v60; // [rsp+20h] [rbp-E0h]
  __int128 *v61; // [rsp+20h] [rbp-E0h]
  __int64 v62; // [rsp+28h] [rbp-D8h]
  int v63; // [rsp+54h] [rbp-ACh]
  struct IGatherSite *v64; // [rsp+58h] [rbp-A8h] BYREF
  int v65; // [rsp+60h] [rbp-A0h] BYREF
  struct CGatherPluginMgr *v66; // [rsp+68h] [rbp-98h] BYREF
  struct CGatherPluginMgr *v67; // [rsp+70h] [rbp-90h] BYREF
  int v68; // [rsp+78h] [rbp-88h] BYREF
  int v69; // [rsp+7Ch] [rbp-84h]
  struct CCrawl *v70; // [rsp+80h] [rbp-80h] BYREF
  char *v71; // [rsp+88h] [rbp-78h]
  struct CSingleLink *v72; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_CRITICAL_SECTION *v73; // [rsp+98h] [rbp-68h]
  CLnkList *i; // [rsp+A0h] [rbp-60h]
  HRESULT v75; // [rsp+A8h] [rbp-58h]
  __int64 v76; // [rsp+B0h] [rbp-50h]
  CSyncReadWrite *v77; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v78[96]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v79[96]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v80[42]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v81[2416]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v82[8]; // [rsp+C40h] [rbp+B40h] BYREF
  __int64 v83; // [rsp+C48h] [rbp+B48h]
  __int128 v84; // [rsp+1460h] [rbp+1360h] BYREF
  __int128 *v85; // [rsp+1470h] [rbp+1370h]
  int v86; // [rsp+1478h] [rbp+1378h]

  v4 = Parameter;
  v71 = Parameter;
  v5 = 0;
  v63 = 0;
  if ( (byte_1802DA181 & 0x40) != 0 )
  {
    v60 = &v84;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      MSSearchTraceId_StatusThread_Start,
      a3,
      1);
  }
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\statthrd.cxx\"",
    (const wchar_t *)0x5D,
    (unsigned int)L"[SrchGatherPI] Status Thread Started\n",
    a4,
    v60);
  v6 = CoInitializeEx(0, 0);
  v75 = v6;
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"Gatherer Status Thread");
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    v8 = *(void **)(*(_QWORD *)(*((_QWORD *)v4 + 18) + 3600LL) + 232LL);
  else
    v8 = 0;
  PerUserCatalogNameForCorruption::SetCatalog(v8);
  v9 = (struct _RTL_CRITICAL_SECTION *)(v4 + 96);
  v73 = (struct _RTL_CRITICAL_SECTION *)(v4 + 96);
  v10 = (CLnkList *)(v4 + 64);
  for ( i = (CLnkList *)(v4 + 64); ; v10 = i )
  {
    while ( 1 )
    {
      EnterCriticalSection(v9);
      v11 = CLnkList::RemoveFirst(v10);
      v72 = v11;
      *((_DWORD *)v4 + 38) = v11 != 0;
      if ( v9 )
        LeaveCriticalSection(v9);
      if ( !v11 )
      {
        TPointer<CStatusChangeRequest>::~TPointer<CStatusChangeRequest>(&v72);
        goto LABEL_131;
      }
      v12 = (CGatherer **)(v4 + 144);
      if ( !*((_DWORD *)v4 + 10) && !*((_DWORD *)*v12 + 301) )
        break;
      v13 = *((_DWORD *)v11 + 2);
      if ( v13 == 17 || v13 == 13 )
        break;
      if ( ((v13 - 10) & 0xFFFFFFFD) != 0 && (!*((_QWORD *)v11 + 2) || v13 == 4 || v13 == 24) )
        CGatherer::UnlockQueue(*((CGatherer **)v4 + 18));
      TPointer<CStatusChangeRequest>::~TPointer<CStatusChangeRequest>(&v72);
    }
    v14 = 0;
    v70 = 0;
    CStatusChangeRequest::GetCrawl(v11, &v70);
    v65 = 0;
    v69 = 0;
    v68 = 0;
    if ( (byte_1802DA181 & 0x40) != 0 )
      McTemplateU0q_EventWriteTransfer(
        v15,
        MSSearchTraceId_StatusChange_ProcessInStatusThread,
        *((unsigned int *)v11 + 2));
    v16 = v70;
    if ( v70 )
      v17 = *((_DWORD *)v70 + 24);
    else
      v17 = -1;
    LODWORD(v62) = v17;
    SearchIndexerTrace::Information(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\statthrd.cxx\"",
      (const wchar_t *)0x98,
      (unsigned int)L"[SrchGatherStatus] Processing status change %d, project %ls, crawl %d\n",
      (const wchar_t *)*((unsigned int *)v11 + 2),
      *((_QWORD *)*v12 + 32),
      v62);
    v18 = *((_DWORD *)v11 + 2);
    if ( v18 == 16 || (v64 = 0, v18 == 5) )
    {
      v14 = (CRegistry *)((char *)g_pGatheringService + 7112);
      v64 = (CRegistry *)((char *)g_pGatheringService + 7112);
    }
    v77 = v14;
    if ( v14 )
      CSyncReadWrite::GetWriteAccess(v14);
    if ( v18 > 0xB )
    {
      v40 = v18 - 14;
      if ( !v40 )
        goto LABEL_101;
      v41 = v40 - 1;
      if ( !v41 )
      {
        CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v81, qword_1802DAFD8);
        CSearchEventEntry::DecodeProjectName((CSearchEventEntry *)v81, *((const wchar_t **)*v12 + 44));
        CSearchEventEntry::ReportInformation((CSearchEventEntry *)v81, 0x40000BE4u, 0);
        CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v81);
LABEL_100:
        CGatherer::SetIdleStatus(*v12);
        CGatherer::RecrawlAllMonitoringNotifications(*v12);
        goto LABEL_102;
      }
      v42 = v41 - 1;
      if ( !v42 )
        goto LABEL_86;
      v43 = v42 - 1;
      if ( v43 )
      {
        v44 = v43 - 1;
        if ( !v44 )
          goto LABEL_81;
        v45 = v44 - 4;
        if ( !v45 )
        {
LABEL_101:
          CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v81, qword_1802DAFD8);
          CSearchEventEntry::DecodeProjectName((CSearchEventEntry *)v81, *((const wchar_t **)*v12 + 44));
          CSearchEventEntry::ReportWarning((CSearchEventEntry *)v81, 0x80000BE2, 0);
          CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v81);
          goto LABEL_102;
        }
        v46 = v45 - 2;
        if ( !v46 )
          goto LABEL_82;
        if ( v46 == 5 )
          goto LABEL_81;
      }
      else
      {
        *((_DWORD *)v71 + 39) = 1;
      }
    }
    else
    {
      if ( v18 == 11 )
        goto LABEL_86;
      if ( !v18 || (v19 = v18 - 1) == 0 || (v20 = v19 - 1) == 0 )
      {
LABEL_81:
        CGatherer::ProcessStartCrawlStatus(*v12, *((_DWORD *)v11 + 2), v16);
        v47 = 1;
        goto LABEL_103;
      }
      v21 = v20 - 2;
      if ( !v21 )
      {
LABEL_82:
        LODWORD(v67) = (*(__int64 (__fastcall **)(struct CCrawl *))(*(_QWORD *)v16 + 96LL))(v16);
        v48 = *v12;
        if ( !*((_DWORD *)*v12 + 414) )
        {
          v66 = 0;
          CGatherer::GetPluginManager(v48, &v66);
          v49 = *((_QWORD *)*v12 + 445);
          v50 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD))(*(_QWORD *)v49 + 48LL);
          v51 = *((_DWORD *)v16 + 24);
          LODWORD(v61) = CCrawl::GetLogSA(v16);
          v50(v49, 1073741856, &cchOriginalDestLength, 0, v61, v51, -1, (_DWORD)v67, &cchOriginalDestLength);
          _InterlockedIncrement((volatile signed __int32 *)v16 + 88);
          TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v66);
          v5 = v63;
          v14 = v64;
        }
        CGatherer::RemoveCrawl(*v12, v16);
        goto LABEL_102;
      }
      v22 = v21 - 1;
      if ( !v22 || (v23 = v22 - 1) == 0 )
      {
LABEL_86:
        if ( *((_DWORD *)v11 + 2) == 5 )
          v65 = 1;
        if ( *((_DWORD *)v11 + 2) == 6 )
          CGatherer::ForceFullCrawlOnFullCrawlsInProgress(*v12);
        if ( *((_DWORD *)v11 + 2) == 5 || *((_DWORD *)v11 + 2) == 16 )
        {
          CStartPageCollection::ForceFullCrawlOnAllStartAddresses((CGatherer *)((char *)*v12 + 2504));
          v69 = 1;
        }
        v52 = CGatherer::DestroyQueue(*v12);
        if ( v52 < 0 )
        {
          CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v81, qword_1802DAFD8);
          CSearchEventEntry::DecodeProjectName((CSearchEventEntry *)v81, *((const wchar_t **)*v12 + 44));
          CSearchEventEntry::SetError((CSearchEventEntry *)v81, v52);
          CSearchEventEntry::ReportError((CSearchEventEntry *)v81, 0xC0000BD1, L"10", 0);
          CGatherer::SetShutdown(*v12);
          CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v81);
        }
        if ( *((_DWORD *)v11 + 2) == 11 )
        {
          CGatherer::SetShutdown(*v12);
          if ( *((_DWORD *)v11 + 2) == 11 )
          {
            CGatherer::SetPausedExternal(*v12, 0);
            *((_DWORD *)*v12 + 295) = 0;
            v53 = (volatile __int32 *)*((_QWORD *)*v12 + 564);
            if ( v53 )
              _InterlockedExchange(v53, 0);
          }
        }
        goto LABEL_102;
      }
      v24 = v23 - 2;
      if ( !v24 )
      {
        v39 = *v12;
        *((_DWORD *)v39 + 309) = 3;
        CGatherer::UpdateConsistentState(v39);
        CGatherer::UpdateStatusInternal(v39);
        goto LABEL_102;
      }
      v25 = v24 - 1;
      if ( !v25 )
        goto LABEL_100;
      if ( v25 == 1 )
      {
        wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v80);
        v80[0] = &SearchIndexerTelemetry::RecoverActivity::`vftable';
        SearchIndexerTelemetry::RecoverActivity::StartActivity((SearchIndexerTelemetry::RecoverActivity *)v80);
        v26 = *v12;
        *((_DWORD *)v26 + 309) = 4;
        CGatherer::UpdateConsistentState(v26);
        CGatherer::UpdateStatusInternal(v26);
        v27 = (volatile __int32 *)*((_QWORD *)*v12 + 565);
        if ( v27 )
          _InterlockedExchange(v27, 1);
        v29 = CGatherer::Recover(*v12, &v68, &v65);
        LODWORD(v66) = v29;
        if ( v29 < 0 )
        {
          LODWORD(v67) = 0;
          SearchIndexerTelemetry::Recover<long &,char const (&)[66],char const (&)[22],int,char const (&)[1]>(
            (unsigned int)&v66,
            v28,
            v30,
            (unsigned int)&v67,
            (__int64)v61);
          CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v81, qword_1802DAFD8);
          CSearchEventEntry::DecodeProjectName((CSearchEventEntry *)v81, *((const wchar_t **)*v12 + 44));
          CSearchEventEntry::SetError((CSearchEventEntry *)v81, v29);
          CSearchEventEntry::ReportError((CSearchEventEntry *)v81, 0xC0000E12, "1", 0);
          v67 = 0;
          CGatherer::GetPluginManager(*v12, &v67);
          if ( (unsigned int)(v29 + 1073473536) <= 1 )
          {
            v33 = *((_QWORD *)*v12 + 32);
            v32 = v67;
            if ( v67 )
            {
              v34 = TLMString<32,32,1024>::TLMString<32,32,1024>(v78, (char *)v67 + 320);
              v5 |= 1u;
            }
            else
            {
              v34 = TLMString<32,32,1024>::TLMString<32,32,1024>(v79, &cchOriginalDestLength);
              v5 |= 2u;
            }
            v63 = v5;
            RecoveryReportIndexRebuildEx_1(v35, qword_1802DAFD8, *(_QWORD *)(v34 + 8), v33);
            if ( (v5 & 2) != 0 )
            {
              v5 &= ~2u;
              v63 = v5;
              TLMString<32,32,1024>::~TLMString<32,32,1024>(v79);
            }
            if ( (v5 & 1) != 0 )
            {
              v5 &= ~1u;
              v63 = v5;
              TLMString<32,32,1024>::~TLMString<32,32,1024>(v78);
            }
          }
          else
          {
            v84 = 0;
            CResourceLibrary::Init((CResourceLibrary *)&v84, L"MSSrch.dll");
            TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v82, &v84, 523);
            v31 = v83;
            v76 = *((_QWORD *)*v12 + 32);
            v32 = v67;
            if ( v67 )
            {
              TLMString<32,32,1024>::TLMString<32,32,1024>(v79, (char *)v67 + 320);
              v5 |= 4u;
            }
            else
            {
              TLMString<32,32,1024>::TLMString<32,32,1024>(v78, &cchOriginalDestLength);
              v5 |= 8u;
            }
            v63 = v5;
            ShutdownSelf_1(qword_1802DAFD8, v31);
            if ( (v5 & 8) != 0 )
            {
              v5 &= ~8u;
              v63 = v5;
              TLMString<32,32,1024>::~TLMString<32,32,1024>(v78);
            }
            if ( (v5 & 4) != 0 )
            {
              v5 &= ~4u;
              v63 = v5;
              TLMString<32,32,1024>::~TLMString<32,32,1024>(v79);
            }
            TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v82);
            CResourceLibrary::FreeLibs((CResourceLibrary *)&v84);
          }
          if ( v32 )
            (*(void (__fastcall **)(struct CGatherPluginMgr *))(*(_QWORD *)v32 + 16LL))(v32);
          CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v81);
          v29 = (int)v66;
          v14 = v64;
LABEL_71:
          wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v80,
            (unsigned int)v29);
          SearchIndexerTelemetry::RecoverActivity::~RecoverActivity((SearchIndexerTelemetry::RecoverActivity *)v80);
          goto LABEL_102;
        }
        if ( v65 )
        {
          v36 = 1;
          goto LABEL_67;
        }
        if ( v68 )
        {
          v36 = 0;
LABEL_67:
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)*v12 + 3) + 24LL))((__int64)*v12 + 24, v36, 0);
        }
        v37 = (volatile __int32 *)*((_QWORD *)*v12 + 565);
        if ( v37 )
          _InterlockedExchange(v37, 0);
        CGatherer::SetStatus(*v12, 0);
        CGatherer::SetIdleStatus(*v12);
        SearchIndexerTrace::Information(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\statthrd.cxx\"",
          (const wchar_t *)0xEC,
          (unsigned int)L"[SrchGatherPI] Finished recovery\n",
          v38);
        goto LABEL_71;
      }
    }
LABEL_102:
    v47 = 0;
LABEL_103:
    if ( *((_DWORD *)v11 + 2) == 10 )
      goto LABEL_114;
    CGatherer::SetIdleStatus(*v12);
    if ( !v47 )
    {
      v64 = 0;
      CGatherer::GetSite(*v12, &v64);
      (*(void (__fastcall **)(struct IGatherSite *, _QWORD, struct CCrawl *, _QWORD))(*(_QWORD *)v64 + 32LL))(
        v64,
        *((unsigned int *)v11 + 2),
        v16,
        0);
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v64);
    }
    if ( *((_DWORD *)v11 + 2) == 17 )
      break;
    if ( v65 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v81, qword_1802DAFD8);
      CSearchEventEntry::DecodeProjectName((CSearchEventEntry *)v81, *((const wchar_t **)*v12 + 44));
      CSearchEventEntry::ReportWarning((CSearchEventEntry *)v81, 0x80000BED, 0);
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)*v12 + 3) + 24LL))((__int64)*v12 + 24, 1, 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v81);
    }
    if ( (unsigned int)(*((_DWORD *)v11 + 2) - 12) <= 1 || v47 )
    {
      if ( v14 )
        CSyncReadWrite::ReleaseWriteAccess(v14);
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v70);
      v4 = v71;
      CStatusChangeRequest::`scalar deleting destructor'(v11, v54);
      goto LABEL_126;
    }
LABEL_114:
    CExclusiveOptional::~CExclusiveOptional((CExclusiveOptional *)&v77);
    if ( v69 )
      CGatherer::InitializeDirectoryNotifications(*v12);
    v64 = 0;
    CGatherer::GetPluginManager(*v12, &v64);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v12 + 445) + 56LL))(*((_QWORD *)*v12 + 445), 1);
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v64);
    if ( *((_DWORD *)v11 + 2) == 5 )
      *((_DWORD *)*v12 + 1148) = 0;
    CGatherer::UnlockQueue(*v12);
    if ( *((_DWORD *)v11 + 2) == 16 )
    {
      *((_QWORD *)&v84 + 1) = (char *)&v84 + 8;
      *(_QWORD *)&v84 = (char *)&v84 + 8;
      v85 = &v84;
      v86 = 0;
      LODWORD(v66) = CStartPageCollection::GetStartPagesByType((char *)*v12 + 2504, v55, &v84);
      if ( (int)v66 >= 0 )
      {
        LODWORD(v61) = 0;
        CGatherer::CreateCrawlFromStartAddressList(*v12, 1, &v84, 0);
      }
      CUnkSList::RemoveAll((CUnkSList *)&v84);
    }
    if ( *((_DWORD *)v11 + 2) == 5 || *((_DWORD *)v11 + 2) == 16 )
      CGatherer::UpdateCatalogSignature(*v12);
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v70);
    TPointer<CStatusChangeRequest>::~TPointer<CStatusChangeRequest>(&v72);
    v4 = v71;
LABEL_126:
    v9 = v73;
  }
  if ( v14 )
    CSyncReadWrite::ReleaseWriteAccess(v14);
  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v70);
  CStatusChangeRequest::`scalar deleting destructor'(v11, v56);
LABEL_131:
  if ( (byte_1802DA181 & 0x40) != 0 )
  {
    v61 = &v84;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      MSSearchTraceId_StatusThread_Stop,
      v57,
      1);
  }
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\statthrd.cxx\"",
    (const wchar_t *)0x1D5,
    (unsigned int)L"[SrchGatherPI] Status Thread Stopped\n",
    v58,
    v61);
  PerUserCatalogNameForCorruption::SetCatalog(0);
  if ( v6 >= 0 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18007bee0  push    rbp
0x18007bee2  push    rbx
0x18007bee3  push    rsi
0x18007bee4  push    rdi
0x18007bee5  push    r12
0x18007bee7  push    r13
0x18007bee9  push    r14
0x18007beeb  push    r15
0x18007beed  lea     rbp, [rsp-1398h]
0x18007bef5  mov     eax, 1498h
0x18007befa  call    _alloca_probe
0x18007beff  sub     rsp, rax
0x18007bf02  mov     rax, cs:__security_cookie
0x18007bf09  xor     rax, rsp
0x18007bf0c  mov     [rbp+13D0h+var_48], rax
0x18007bf13  mov     rbx, rcx
0x18007bf16  mov     [rbp+13D0h+var_1448], rcx
0x18007bf1a  xor     r14d, r14d
0x18007bf1d  mov     [rsp+14D0h+var_147C], r14d
0x18007bf22  test    cs:byte_1802DA181, 40h
0x18007bf29  jz      short loc_18007BF4E
0x18007bf2b  lea     rax, [rbp+13D0h+var_70]
0x18007bf32  mov     [rsp+14D0h+var_14B0], rax
0x18007bf37  lea     r9d, [r14+1]
0x18007bf3b  lea     rdx, MSSearchTraceId_StatusThread_Start
0x18007bf42  lea     rcx, Microsoft_Windows_Search_Core_Context
0x18007bf49  call    McGenEventWrite_EventWriteTransfer
0x18007bf4e  lea     r8, aSrchgatherpiSt; "[SrchGatherPI] Status Thread Started\n"
0x18007bf55  mov     edx, 5Dh ; ']'; wchar_t *
0x18007bf5a  lea     rcx, aOnecoreuapBase_220; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18007bf61  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18007bf66  xor     edx, edx; dwCoInit
0x18007bf68  xor     ecx, ecx; pvReserved
0x18007bf6a  call    cs:__imp_CoInitializeEx
0x18007bf70  mov     edi, eax
0x18007bf72  mov     [rbp+13D0h+var_1428], eax
0x18007bf75  call    cs:__imp_GetCurrentThread
0x18007bf7b  mov     rcx, rax; hThread
0x18007bf7e  lea     rdx, aGathererStatus; "Gatherer Status Thread"
0x18007bf85  call    cs:__imp_SetThreadDescription
0x18007bf8b  xor     r9d, r9d; Context
0x18007bf8e  xor     r8d, r8d; Parameter
0x18007bf91  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18007bf98  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18007bf9f  call    cs:__imp_InitOnceExecuteOnce
0x18007bfa5  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, 0; bool g_isPerUserCatalogEnabled
0x18007bfac  jz      short loc_18007BFC5
0x18007bfae  mov     rax, [rbx+90h]
0x18007bfb5  mov     rcx, [rax+0E10h]
0x18007bfbc  mov     rcx, [rcx+0E8h]
0x18007bfc3  jmp     short loc_18007BFC7
0x18007bfc5  xor     ecx, ecx; lpTlsValue
0x18007bfc7  call    PerUserCatalogNameForCorruption__SetCatalog
0x18007bfcc  nop
0x18007bfcd  lea     rsi, [rbx+60h]
0x18007bfd1  mov     [rbp+13D0h+var_1438], rsi
0x18007bfd5  lea     r15, [rbx+40h]
0x18007bfd9  mov     [rbp+13D0h+var_1430], r15
0x18007bfdd  mov     rcx, rsi; lpCriticalSection
0x18007bfe0  call    cs:__imp_EnterCriticalSection
0x18007bfe6  mov     rcx, r15; this
0x18007bfe9  call    ?RemoveFirst@CLnkList@@QEAAPEAVCSingleLink@@XZ; CLnkList::RemoveFirst(void)
0x18007bfee  mov     r13, rax
0x18007bff1  mov     [rbp+13D0h+var_1440], rax
0x18007bff5  xor     eax, eax
0x18007bff7  test    r13, r13
0x18007bffa  setnz   al
0x18007bffd  mov     [rbx+98h], eax
0x18007c003  test    rsi, rsi
0x18007c006  jz      short loc_18007C011
0x18007c008  mov     rcx, rsi; lpCriticalSection
0x18007c00b  call    cs:__imp_LeaveCriticalSection
0x18007c011  test    r13, r13
0x18007c014  jz      loc_18007CA4C
0x18007c01a  lea     r12, [rbx+90h]
0x18007c021  cmp     dword ptr [rbx+28h], 0
0x18007c025  jnz     short loc_18007C034
0x18007c027  mov     rax, [r12]
0x18007c02b  cmp     dword ptr [rax+4B4h], 0
0x18007c032  jz      short loc_18007C078
0x18007c034  mov     ecx, [r13+8]
0x18007c038  cmp     ecx, 11h
0x18007c03b  jz      short loc_18007C078
0x18007c03d  cmp     ecx, 0Dh
0x18007c040  jz      short loc_18007C078
0x18007c042  lea     eax, [rcx-0Ah]
0x18007c045  test    eax, 0FFFFFFFDh
0x18007c04a  jz      short loc_18007C06A
0x18007c04c  cmp     qword ptr [r13+10h], 0
0x18007c051  jz      short loc_18007C05D
0x18007c053  cmp     ecx, 4
0x18007c056  jz      short loc_18007C05D
0x18007c058  cmp     ecx, 18h
0x18007c05b  jnz     short loc_18007C06A
0x18007c05d  mov     rcx, [rbx+90h]; this
0x18007c064  call    ?UnlockQueue@CGatherer@@QEAAXXZ; CGatherer::UnlockQueue(void)
0x18007c069  nop
0x18007c06a  lea     rcx, [rbp+13D0h+var_1440]
0x18007c06e  call    ??1?$TPointer@VCStatusChangeRequest@@@@QEAA@XZ; TPointer<CStatusChangeRequest>::~TPointer<CStatusChangeRequest>(void)
0x18007c073  jmp     loc_18007BFDD
0x18007c078  xor     r15d, r15d
0x18007c07b  mov     [rbp+13D0h+var_1450], r15
0x18007c07f  lea     rdx, [rbp+13D0h+var_1450]; struct CCrawl **
0x18007c083  mov     rcx, r13; this
0x18007c086  call    ?GetCrawl@CStatusChangeRequest@@QEAAXPEAPEAVCCrawl@@@Z; CStatusChangeRequest::GetCrawl(CCrawl * *)
0x18007c08b  mov     [rsp+14D0h+var_1480], r15d
0x18007c090  mov     [rsp+14D0h+var_1470], r15d
0x18007c095  mov     [rsp+14D0h+var_1454], r15d
0x18007c09a  mov     [rsp+14D0h+var_1458], r15d
0x18007c09f  test    cs:byte_1802DA181, 40h
0x18007c0a6  jz      short loc_18007C0B8
0x18007c0a8  mov     r8d, [r13+8]
0x18007c0ac  lea     rdx, MSSearchTraceId_StatusChange_ProcessInStatusThread
0x18007c0b3  call    McTemplateU0q_EventWriteTransfer
0x18007c0b8  mov     rbx, [rbp+13D0h+var_1450]
0x18007c0bc  test    rbx, rbx
0x18007c0bf  jz      short loc_18007C0C6
0x18007c0c1  mov     ecx, [rbx+60h]
0x18007c0c4  jmp     short loc_18007C0C9
0x18007c0c6  or      ecx, 0FFFFFFFFh
0x18007c0c9  mov     rax, [r12]
0x18007c0cd  mov     dword ptr [rsp+14D0h+var_14A8], ecx
0x18007c0d1  mov     rax, [rax+100h]
0x18007c0d8  mov     [rsp+14D0h+var_14B0], rax
0x18007c0dd  mov     r9d, [r13+8]; wchar_t *
0x18007c0e1  lea     r8, aSrchgatherstat_3; "[SrchGatherStatus] Processing status ch"...
0x18007c0e8  mov     edx, 98h; wchar_t *
0x18007c0ed  lea     rcx, aOnecoreuapBase_220; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18007c0f4  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18007c0f9  mov     esi, [r13+8]
0x18007c0fd  cmp     esi, 10h
0x18007c100  jz      short loc_18007C10C
0x18007c102  mov     [rsp+14D0h+var_1478], r15
0x18007c107  cmp     esi, 5
0x18007c10a  jnz     short loc_18007C11F
0x18007c10c  mov     r15, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18007c113  add     r15, 1BC8h
0x18007c11a  mov     [rsp+14D0h+var_1478], r15
0x18007c11f  mov     [rbp+13D0h+var_1418], r15
0x18007c123  test    r15, r15
0x18007c126  jz      short loc_18007C131
0x18007c128  mov     rcx, r15; this
0x18007c12b  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x18007c130  nop
0x18007c131  cmp     esi, 0Bh
0x18007c134  ja      loc_18007C4FB
0x18007c13a  jz      loc_18007C622
0x18007c140  test    esi, esi
0x18007c142  jz      loc_18007C53B
0x18007c148  sub     esi, 1
0x18007c14b  jz      loc_18007C53B
0x18007c151  sub     esi, 1
0x18007c154  jz      loc_18007C53B
0x18007c15a  sub     esi, 2
0x18007c15d  jz      loc_18007C555
0x18007c163  sub     esi, 1
0x18007c166  jz      loc_18007C622
0x18007c16c  sub     esi, 1
0x18007c16f  jz      loc_18007C622
0x18007c175  sub     esi, 2
0x18007c178  jz      loc_18007C4D8
0x18007c17e  sub     esi, 1
0x18007c181  jz      loc_18007C781
0x18007c187  cmp     esi, 1
0x18007c18a  jnz     loc_18007C7E1
0x18007c190  lea     rcx, [rbp+13D0h+var_1350]; struct wil::details::IFailureCallback *
0x18007c197  call    ??0?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007c19c  lea     rax, ??_7RecoverActivity@SearchIndexerTelemetry@@6B@; const SearchIndexerTelemetry::RecoverActivity::`vftable'
0x18007c1a3  mov     [rbp+13D0h+var_1350], rax
0x18007c1aa  lea     rcx, [rbp+13D0h+var_1350]; this
0x18007c1b1  call    ?StartActivity@RecoverActivity@SearchIndexerTelemetry@@QEAAXXZ; SearchIndexerTelemetry::RecoverActivity::StartActivity(void)
0x18007c1b6  nop
0x18007c1b7  mov     rsi, [r12]
0x18007c1bb  mov     dword ptr [rsi+4D4h], 4
0x18007c1c5  mov     rcx, rsi; this
0x18007c1c8  call    ?UpdateConsistentState@CGatherer@@AEAAXXZ; CGatherer::UpdateConsistentState(void)
0x18007c1cd  mov     rcx, rsi; this
0x18007c1d0  call    ?UpdateStatusInternal@CGatherer@@QEAAKXZ; CGatherer::UpdateStatusInternal(void)
0x18007c1d5  mov     rax, [r12]
0x18007c1d9  mov     rcx, [rax+11A8h]
0x18007c1e0  test    rcx, rcx
0x18007c1e3  jz      short loc_18007C1EC
0x18007c1e5  mov     eax, 1
0x18007c1ea  xchg    eax, [rcx]
0x18007c1ec  lea     r8, [rsp+14D0h+var_1470]; int *
0x18007c1f1  lea     rdx, [rsp+14D0h+var_1458]; int *
0x18007c1f6  mov     rcx, [r12]; this
0x18007c1fa  call    ?Recover@CGatherer@@QEAAJAEAH0@Z; CGatherer::Recover(int &,int &)
0x18007c1ff  mov     esi, eax
0x18007c201  mov     dword ptr [rsp+14D0h+var_1468], eax
0x18007c205  xor     eax, eax
0x18007c207  test    esi, esi
0x18007c209  jns     loc_18007C44C
0x18007c20f  mov     dword ptr [rsp+14D0h+var_1460], eax
0x18007c213  lea     r9, [rsp+14D0h+var_1460]
0x18007c218  lea     rcx, [rsp+14D0h+var_1468]
0x18007c21d  call    ??$Recover@AEAJAEAY0EC@$$CBDAEAY0BG@$$CBDHAEAY00$$CBD@SearchIndexerTelemetry@@SAXAEAJAEAY0EC@$$CBDAEAY0BG@$$CBD$$QEAHAEAY00$$CBD@Z; SearchIndexerTelemetry::Recover<long &,char const (&)[66],char const (&)[22],int,char const (&)[1]>(long &,char const (&)[66],char const (&)[22],int &&,char const (&)[1])
0x18007c222  mov     rdx, cs:qword_1802DAFD8; struct CEventLog *
0x18007c229  lea     rcx, [rbp+13D0h+var_1200]; this
0x18007c230  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x18007c235  nop
0x18007c236  mov     rdx, [r12]
0x18007c23a  mov     rdx, [rdx+160h]; wchar_t *
0x18007c241  lea     rcx, [rbp+13D0h+var_1200]; this
0x18007c248  call    ?DecodeProjectName@CSearchEventEntry@@QEAAXPEB_W@Z; CSearchEventEntry::DecodeProjectName(wchar_t const *)
0x18007c24d  mov     edx, esi; int
0x18007c24f  lea     rcx, [rbp+13D0h+var_1200]; this
0x18007c256  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x18007c25b  xor     r9d, r9d
0x18007c25e  lea     r8, a1_0; "1"
0x18007c265  mov     edx, 0C0000E12h; unsigned int
0x18007c26a  lea     rcx, [rbp+13D0h+var_1200]; this
0x18007c271  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x18007c276  mov     [rsp+14D0h+var_1460], 0
0x18007c27f  lea     rdx, [rsp+14D0h+var_1460]; struct CGatherPluginMgr **
0x18007c284  mov     rcx, [r12]; this
0x18007c288  call    ?GetPluginManager@CGatherer@@QEAAXPEAPEAVCGatherPluginMgr@@@Z; CGatherer::GetPluginManager(CGatherPluginMgr * *)
0x18007c28d  lea     eax, [rsi+3FFBE800h]
0x18007c293  cmp     eax, 1
0x18007c296  jbe     loc_18007C395
0x18007c29c  xorps   xmm0, xmm0
0x18007c29f  movdqu  [rbp+13D0h+var_70], xmm0
0x18007c2a7  lea     rdx, aMssrchDll_0; "MSSrch.dll"
0x18007c2ae  lea     rcx, [rbp+13D0h+var_70]; this
0x18007c2b5  call    ?Init@CResourceLibrary@@QEAAXPEB_W@Z; CResourceLibrary::Init(wchar_t const *)
0x18007c2ba  nop
0x18007c2bb  mov     r8d, 20Bh
0x18007c2c1  lea     rdx, [rbp+13D0h+var_70]
0x18007c2c8  lea     rcx, [rbp+13D0h+var_890]
0x18007c2cf  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@AEAVCResourceLibrary@@I@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(CResourceLibrary &,uint)
0x18007c2d4  nop
0x18007c2d5  mov     r15, [rbp+13D0h+var_888]
0x18007c2dc  mov     rax, [r12]
0x18007c2e0  mov     rax, [rax+100h]
0x18007c2e7  mov     [rbp+13D0h+var_1420], rax
0x18007c2eb  mov     rsi, [rsp+14D0h+var_1460]
0x18007c2f0  test    rsi, rsi
0x18007c2f3  jz      short loc_18007C30C
0x18007c2f5  lea     rdx, [rsi+140h]
0x18007c2fc  lea     rcx, [rbp+13D0h+var_13B0]
0x18007c300  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@AEBV0@@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(TLMString<32,32,1024> const &)
0x18007c305  nop
0x18007c306  or      r14d, 4
0x18007c30a  jmp     short loc_18007C321
0x18007c30c  lea     rdx, cchOriginalDestLength
0x18007c313  lea     rcx, [rbp+13D0h+var_1410]
0x18007c317  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x18007c31c  nop
0x18007c31d  or      r14d, 8
0x18007c321  mov     [rsp+14D0h+var_147C], r14d
0x18007c326  mov     [rsp+14D0h+var_14B0], r15; __int64
0x18007c32b  mov     r9d, dword ptr [rsp+14D0h+var_1468]
0x18007c330  mov     r8, [rbp+13D0h+var_1420]
0x18007c334  mov     rdx, [rax+8]
0x18007c338  mov     rcx, cs:qword_1802DAFD8; struct CEventLog *
0x18007c33f  call    ShutdownSelf_1
0x18007c344  nop
0x18007c345  test    r14b, 8
0x18007c349  jz      short loc_18007C35E
0x18007c34b  and     r14d, 0FFFFFFF7h
0x18007c34f  mov     [rsp+14D0h+var_147C], r14d
0x18007c354  lea     rcx, [rbp+13D0h+var_1410]
0x18007c358  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18007c35d  nop
0x18007c35e  test    r14b, 4
0x18007c362  jz      short loc_18007C377
0x18007c364  and     r14d, 0FFFFFFFBh
0x18007c368  mov     [rsp+14D0h+var_147C], r14d
0x18007c36d  lea     rcx, [rbp+13D0h+var_13B0]
0x18007c371  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18007c376  nop
0x18007c377  lea     rcx, [rbp+13D0h+var_890]
0x18007c37e  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18007c383  nop
0x18007c384  lea     rcx, [rbp+13D0h+var_70]; this
0x18007c38b  call    ?FreeLibs@CResourceLibrary@@AEAAXXZ; CResourceLibrary::FreeLibs(void)
0x18007c390  jmp     loc_18007C420
0x18007c395  mov     rax, [r12]
0x18007c399  mov     r15, [rax+100h]
0x18007c3a0  mov     rsi, [rsp+14D0h+var_1460]
0x18007c3a5  test    rsi, rsi
0x18007c3a8  jz      short loc_18007C3C1
0x18007c3aa  lea     rdx, [rsi+140h]
0x18007c3b1  lea     rcx, [rbp+13D0h+var_1410]
0x18007c3b5  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@AEBV0@@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(TLMString<32,32,1024> const &)
0x18007c3ba  nop
0x18007c3bb  or      r14d, 1
0x18007c3bf  jmp     short loc_18007C3D6
0x18007c3c1  lea     rdx, cchOriginalDestLength
0x18007c3c8  lea     rcx, [rbp+13D0h+var_13B0]
0x18007c3cc  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x18007c3d1  nop
0x18007c3d2  or      r14d, 2
0x18007c3d6  mov     [rsp+14D0h+var_147C], r14d
0x18007c3db  mov     r9, r15
0x18007c3de  mov     r8, [rax+8]
0x18007c3e2  mov     rdx, cs:qword_1802DAFD8
0x18007c3e9  call    RecoveryReportIndexRebuildEx_1
0x18007c3ee  nop
0x18007c3ef  test    r14b, 2
  ... truncated ...
```
