# CGatheringService::Init(INDEXER_SETUP_ACTIONS,std::vector<ReIndexPatternInfo,std::allocator<ReIndexPatternInfo>> const *)

- ea: `0x18017d66c`
- end: `0x18017f61b`
- name: `?Init@CGatheringService@@QEAAJW4INDEXER_SETUP_ACTIONS@@PEBV?$vector@VReIndexPatternInfo@@V?$allocator@VReIndexPatternInfo@@@std@@@std@@@Z`
- size: `8111`
- prototype: ``
- caller_count: `1`
- callee_count: `94`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180142040`

## callees

- `0x18000a23c`
- `0x18000bf8c`
- `0x18000d15c`
- `0x18000e628`
- `0x18000efcc`
- `0x18000f880`
- `0x180012120`
- `0x180012318`
- `0x180019bb0`
- `0x180022710`
- `0x1800269b0`
- `0x180026b58`
- `0x180027164`
- `0x180027190`
- `0x18002dc6c`
- `0x18004b638`
- `0x18004e5d8`
- `0x180052460`
- `0x180054730`
- `0x1800548a4`
- `0x180054cb8`
- `0x180054e14`
- `0x1800555f0`
- `0x180056610`
- `0x18005c150`
- `0x18005cbf4`
- `0x18005edc4`
- `0x180061f78`
- `0x1800758b0`
- `0x180079c44`
- `0x180079d34`
- `0x1800800f4`
- `0x18008ad80`
- `0x18008da30`
- `0x1800904ec`
- `0x1800a1700`
- `0x1800a3a38`
- `0x1800abe78`
- `0x1800b4968`
- `0x1800bfb94`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800cff10`
- `0x1800d057c`
- `0x1800d2658`
- `0x1800d2754`
- `0x1800d34f4`
- `0x1800d3584`
- `0x1800d3e30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017ee5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017ee65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017ee6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017f34f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017ee5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017ee65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017ee6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017f34f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18017ee95`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18017ee95`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18017f33c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18017f33c`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18017ec75`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18017ec8a`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18017ec75`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18017ec8a`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18017d761`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18017d761`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18017eb5b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18017eb80`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18017eb5b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18017eb80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18017e3bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18017e3bf`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18017efa9`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18017efa9`

## string_xrefs

- `0x18017e7b9`: `TempPath`
- `0x18017e7a0`: `DefaultApplicationsPath`
- `0x18017e7d2`: `UseSystemTemp`
- `0x18017e7f4`: `UseSystemTemp`
- `0x18017e774`: `UserAgent`
- `0x18017df61`: `RobotThreadsNumber`
- `0x18017df7a`: `RobotThreadsNumber`
- `0x18017e965`: `PluginPingFrequency`
- `0x18017e982`: `PluginPingFrequency`
- `0x18017ea39`: `LinksInMemoryCacheSize`
- `0x18017ea53`: `LinksInMemoryCacheSize`
- `0x18017db14`: `[SrchGatherSvc] Error creating perfmon object instance for the gathering service`
- `0x18017e3d2`: `[SrchGatherSvc] CoCreate failed for back off controller, hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CGatheringService::Init(__int64 a1, int a2, __int64 a3)
{
  CRegistry *v5; // r13
  CPhMultiArch *v6; // rax
  CPhMultiArch *v7; // rax
  const struct System::CSystemInfo *v8; // rax
  HANDLE SemaphoreW; // rax
  const char *v10; // r9
  HKEY v11; // rcx
  _QWORD *Instance; // rax
  winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager *v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // r8
  CSyncReadWrite *v16; // rbx
  int v17; // eax
  CRobotThreadPool *v18; // rax
  CRobotThreadPool *v19; // rax
  CActiveQueue *v20; // rax
  CActiveQueue *v21; // rax
  int v22; // eax
  CThread *v23; // rax
  CThread *v24; // rdi
  PerfLibrary *v25; // r10
  const wchar_t *v26; // r9
  struct PerfObjectInstance *ObjectInstance; // rax
  const wchar_t *v28; // r9
  volatile __int32 *Counter; // rax
  volatile __int32 *v30; // rax
  volatile __int32 *v31; // rax
  volatile __int32 *v32; // rax
  volatile __int32 *v33; // rax
  volatile __int32 *v34; // rax
  volatile __int32 *v35; // rax
  volatile __int32 *v36; // rax
  volatile __int32 *v37; // rax
  volatile __int32 *v38; // rax
  volatile __int32 *v39; // rax
  volatile __int32 *v40; // rax
  volatile __int32 *v41; // rax
  volatile __int32 *v42; // rax
  volatile __int32 *v43; // rax
  volatile __int32 *v44; // rax
  volatile __int32 *v45; // rax
  volatile __int32 *v46; // rax
  volatile __int32 *v47; // rax
  volatile __int32 *v48; // rax
  volatile __int32 *v49; // rax
  volatile __int32 *v50; // rax
  volatile __int32 *v51; // rax
  volatile __int32 *v52; // rax
  volatile __int32 *v53; // rax
  volatile __int32 *v54; // rax
  volatile __int32 *v55; // rax
  volatile __int32 *v56; // rax
  volatile __int32 *v57; // rax
  volatile __int32 *v58; // rax
  volatile __int32 *v59; // rcx
  volatile __int32 *v60; // rcx
  volatile __int32 *v61; // rcx
  _DWORD *v62; // r12
  _DWORD *v63; // rsi
  _DWORD *v64; // r14
  volatile __int32 *v65; // rcx
  HRESULT v66; // eax
  unsigned int v67; // edi
  __int64 v68; // rcx
  int v70; // eax
  __int64 v71; // rcx
  int Policy; // eax
  CBackOffController **v73; // rdi
  __int64 v74; // r8
  int *v75; // r14
  int *v76; // rsi
  wchar_t *Buffer; // rax
  unsigned int TempPath2W; // eax
  const char *v79; // r9
  unsigned int v80; // edi
  wchar_t *v81; // rax
  unsigned int v82; // r9d
  __int64 i; // r9
  int v84; // edx
  const wchar_t *v85; // rdx
  int DirectoryDeepNoThrow; // eax
  int v87; // edi
  const wchar_t *v88; // r9
  __int64 v89; // r12
  CFilterPool **v90; // rdi
  __int64 v91; // rcx
  int v92; // eax
  CFilterPool *v93; // rcx
  int v94; // eax
  unsigned int v95; // edx
  int v96; // eax
  __int64 v97; // rcx
  _QWORD *v98; // rdx
  _QWORD *v99; // rdx
  HANDLE *v100; // r14
  HANDLE CurrentProcess; // rsi
  HANDLE v102; // rdi
  HANDLE v103; // rax
  const char *Error; // rsi
  int v105; // eax
  int v106; // eax
  _QWORD *v107; // rdx
  _QWORD *v108; // rdx
  const wchar_t *v109; // rdx
  const wchar_t *v110; // rcx
  int HandlerList; // eax
  _QWORD *v112; // rdx
  _QWORD *v113; // rdx
  int FilterHostProcessPoolManager; // eax
  _QWORD *v115; // rdx
  _QWORD *v116; // rdx
  _QWORD *v117; // rdx
  _QWORD *v118; // rdx
  __int64 v119; // rcx
  HANDLE v120; // rax
  int JobManagerInstance; // eax
  _QWORD *v122; // rdx
  _QWORD *v123; // rdx
  _QWORD *v124; // rdx
  _QWORD *v125; // rdx
  unsigned int v126; // eax
  unsigned int v127; // eax
  unsigned int v128; // eax
  unsigned int v129; // eax
  unsigned int v130; // eax
  unsigned int v131; // eax
  unsigned int v132; // eax
  int ppv; // [rsp+20h] [rbp-C68h]
  int ppva; // [rsp+20h] [rbp-C68h]
  int ppvb; // [rsp+20h] [rbp-C68h]
  bool v136[8]; // [rsp+40h] [rbp-C48h] BYREF
  unsigned int v137[4]; // [rsp+48h] [rbp-C40h] BYREF
  LPVOID v138; // [rsp+58h] [rbp-C30h] BYREF
  unsigned int *v139; // [rsp+60h] [rbp-C28h] BYREF
  std::_Ref_count_base *v140; // [rsp+68h] [rbp-C20h]
  CBackOffController **v141; // [rsp+70h] [rbp-C18h] BYREF
  _QWORD Recipient[2]; // [rsp+78h] [rbp-C10h] BYREF
  __int64 v143; // [rsp+88h] [rbp-C00h]
  char *v144; // [rsp+90h] [rbp-BF8h]
  CRegistry *v145; // [rsp+98h] [rbp-BF0h]
  __int64 v146; // [rsp+A0h] [rbp-BE8h]
  char *v147; // [rsp+A8h] [rbp-BE0h]
  char *v148; // [rsp+B0h] [rbp-BD8h]
  _QWORD v149[7]; // [rsp+C0h] [rbp-BC8h] BYREF
  _QWORD *v150; // [rsp+F8h] [rbp-B90h]
  _QWORD v151[7]; // [rsp+100h] [rbp-B88h] BYREF
  _QWORD *v152; // [rsp+138h] [rbp-B50h]
  _QWORD v153[4]; // [rsp+140h] [rbp-B48h] BYREF
  __int16 v154; // [rsp+160h] [rbp-B28h]
  int v155; // [rsp+162h] [rbp-B26h]
  __int16 v156; // [rsp+166h] [rbp-B22h]
  _QWORD *v157; // [rsp+178h] [rbp-B10h]
  const int *v158; // [rsp+180h] [rbp-B08h] BYREF
  LPCWSTR lpValue; // [rsp+188h] [rbp-B00h]
  __int64 v160; // [rsp+190h] [rbp-AF8h]
  __int16 v161; // [rsp+198h] [rbp-AF0h] BYREF
  _BYTE v162[16]; // [rsp+220h] [rbp-A68h] BYREF
  wchar_t *v163; // [rsp+230h] [rbp-A58h]
  HKEY v164; // [rsp+2D0h] [rbp-9B8h]
  _BYTE v165[2416]; // [rsp+2E0h] [rbp-9A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C88h] [rbp+0h]

  v143 = a3;
  v146 = a3;
  v5 = g_pGatheringService;
  v145 = g_pGatheringService;
  if ( (byte_1802DA181 & 8) != 0 )
    McTemplateU0t_EventWriteTransfer();
  CSearchRootRegistry::CSearchRootRegistry((CSearchRootRegistry *)v162, 0, 0xF003Fu);
  CRegistry::Init(v5, v164, L"Gathering Manager", 0xF003Fu, v163);
  v6 = (CPhMultiArch *)operator new(0x1340u, (const struct std::nothrow_t *)&std::nothrow);
  v139 = (unsigned int *)v6;
  if ( v6 )
    v7 = CPhMultiArch::CPhMultiArch(v6);
  else
    v7 = 0;
  *((_QWORD *)v5 + 45) = v7;
  if ( !v7 )
  {
    v126 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v126,
      ppv);
  }
  v8 = System::SystemInfo();
  SemaphoreW = CreateSemaphoreW(0, 4 * *((_DWORD *)v8 + 8), 4 * *((_DWORD *)v8 + 8), 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v5 + 4144,
    SemaphoreW);
  if ( (unsigned __int64)(*((_QWORD *)v5 + 518) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      v10);
  *((_BYTE *)v5 + 368) = ((a2 - 1) & 0xFFFFFFFD) == 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl)
    && (unsigned int)GetIsSemanticIndexingActive() )
  {
    SetClearSemanticIndexStore(0);
    SetClearSemanticIndexStore(1);
    v136[0] = 0;
    SetIsSemanticIndexingActive(v136);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
  {
    v137[0] = 17;
    WSearchRegSetKeyValue(
      v11,
      L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer",
      L"SemanticIndexingStatus",
      4u,
      v137,
      4u);
    Instance = (_QWORD *)winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(&v141);
    v13 = (winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager *)((*Instance - 16LL)
                                                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)*Instance >> 64));
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v141);
    v14 = winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::ValidateSemanticSearchSettings(v13);
    if ( v14 == 14 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl'::`2'::impl) )
        winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::CreateKeyWithRetriesAndCheckForModels(v13);
      else
        winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::StartCheckForModelsAvailability(
          v13,
          v136);
    }
    else
    {
      v136[0] = 0;
      LOBYTE(v15) = 1;
      SetIsSemanticIndexingAllowed(v136, v14, v15);
    }
  }
  if ( a2 == 4 )
  {
    ETWLog::Log(L"[SrchGatherSvc] System index is marked for inplace rebuild.");
    if ( g_pGatheringService )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v165, *((struct CEventLog **)g_pGatheringService + 49));
      CSearchEventEntry::ReportInformation((CSearchEventEntry *)v165, 0x40000E13u, 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v165);
    }
    if ( a3 )
    {
      if ( *(_QWORD *)a3 != *(_QWORD *)(a3 + 8) )
      {
        std::_Destroy_range<std::allocator<CPhMultiArch::MachineWithAumid>>(*(ReIndexPatternInfo **)a3);
        *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
      }
      std::wstring::wstring(v153, L"*");
      v154 = 257;
      v155 = 0;
      v156 = 0;
      std::vector<ReIndexPatternInfo>::push_back(a3, v153);
      ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v153);
    }
    else
    {
      ETWLog::Log(L"[SrchGatherSvc] Inplace indexing Failed, reIndexPatternInfo is NULL");
    }
  }
  v16 = (CRegistry *)((char *)v5 + 208);
  v144 = (char *)v5 + 208;
  CSyncReadWrite::GetWriteAccess((CRegistry *)((char *)v5 + 208));
  *(_QWORD *)v137 = 0;
  v17 = ATL::CComObject<CGatherApplicationCollection>::CreateInstance(v137);
  if ( v17 < 0 )
  {
    v127 = wil::verify_hresult<long>((unsigned int)v17);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v127,
      ppv);
  }
  TComNoUnkPointer<CPlugin>::operator=((char *)v5 + 376, *(_QWORD *)v137);
  v18 = (CRobotThreadPool *)operator new(0x100u, (const struct std::nothrow_t *)&std::nothrow);
  v139 = (unsigned int *)v18;
  if ( v18 )
    v19 = CRobotThreadPool::CRobotThreadPool(v18);
  else
    v19 = 0;
  *((_QWORD *)v5 + 488) = v19;
  if ( !v19 )
  {
    v128 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v128,
      ppv);
  }
  v20 = (CActiveQueue *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v139 = (unsigned int *)v20;
  if ( v20 )
    v21 = CActiveQueue::CActiveQueue(v20, *((struct CRobotThreadPool **)v5 + 488));
  else
    v21 = 0;
  *((_QWORD *)v5 + 489) = v21;
  if ( !v21 )
  {
    v129 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v129,
      ppv);
  }
  *(_QWORD *)v137 = 0;
  v22 = ATL::CComObject<CFilterPool>::CreateInstance(v137);
  if ( v22 < 0 )
  {
    v130 = wil::verify_hresult<long>((unsigned int)v22);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v130,
      ppv);
  }
  Recipient[0] = (char *)v5 + 3920;
  TComNoUnkPointer<CPlugin>::operator=((char *)v5 + 3920, *(_QWORD *)v137);
  v23 = (CThread *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v24 = v23;
  v139 = (unsigned int *)v23;
  if ( v23 )
  {
    CThread::CThread(v23);
    *(_QWORD *)v24 = &CTimerThread::`vftable';
  }
  else
  {
    v24 = 0;
  }
  *((_QWORD *)v5 + 498) = v24;
  if ( !v24 )
  {
    v131 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)v131,
      ppv);
  }
  StringCchCopyNW((wchar_t *)v5 + 2224, 0x10u, L"UGTHRSVC", 0x10u);
  StringCchCopyNW((wchar_t *)v5 + 2328, 0x10u, L"UGthrSvcObj", 0x10u);
  if ( (unsigned int)PerfLibrary::Init(v25) )
  {
    ObjectInstance = PerfObjectDefinition::CreateObjectInstance((CRegistry *)((char *)v5 + 4656), 0);
    *((_QWORD *)v5 + 834) = ObjectInstance;
    if ( ObjectInstance )
      goto LABEL_44;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\cgathersvc.cxx\"",
      (const wchar_t *)0x1C2,
      (unsigned int)L"[SrchGatherSvc] Error creating perfmon object instance for the gathering service",
      v28);
    CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v165, *((struct CEventLog **)v5 + 49));
    CSearchEventEntry::ReportError((CSearchEventEntry *)v165, 0xC0000BBE, 0);
  }
  else
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\cgathersvc.cxx\"",
      (const wchar_t *)0x1B9,
      (unsigned int)L"[SrchGatherSvc] Error initializing performance monitoring",
      v26);
    CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v165, *((struct CEventLog **)v5 + 49));
    CSearchEventEntry::ReportError((CSearchEventEntry *)v165, 0xC0000BBE, 0);
  }
  CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v165);
LABEL_44:
  Counter = (volatile __int32 *)CGatheringService::GetCounter(v5, 2u);
  *((_QWORD *)v5 + 924) = Counter;
  if ( Counter )
    _InterlockedExchange(Counter, 0);
  v30 = (volatile __int32 *)CGatheringService::GetCounter(v5, 4u);
  *((_QWORD *)v5 + 925) = v30;
  if ( v30 )
    _InterlockedExchange(v30, 0);
  v31 = (volatile __int32 *)CGatheringService::GetCounter(v5, 8u);
  *((_QWORD *)v5 + 926) = v31;
  if ( v31 )
    _InterlockedExchange(v31, 0);
  v32 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0xAu);
  *((_QWORD *)v5 + 927) = v32;
  if ( v32 )
    _InterlockedExchange(v32, 0);
  v33 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0xEu);
  *((_QWORD *)v5 + 928) = v33;
  if ( v33 )
    _InterlockedExchange(v33, 0);
  v34 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x10u);
  *((_QWORD *)v5 + 929) = v34;
  if ( v34 )
    _InterlockedExchange(v34, 0);
  v35 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x12u);
  *((_QWORD *)v5 + 930) = v35;
  if ( v35 )
    _InterlockedExchange(v35, 0);
  v36 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x14u);
  *((_QWORD *)v5 + 931) = v36;
  if ( v36 )
    _InterlockedExchange(v36, 0);
  v37 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x16u);
  *((_QWORD *)v5 + 932) = v37;
  if ( v37 )
    _InterlockedExchange(v37, 0);
  v38 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x18u);
  *((_QWORD *)v5 + 933) = v38;
  if ( v38 )
    _InterlockedExchange(v38, 0);
  v39 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x1Au);
  *((_QWORD *)v5 + 934) = v39;
  if ( v39 )
    _InterlockedExchange(v39, 0);
  v40 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x1Cu);
  *((_QWORD *)v5 + 935) = v40;
  if ( v40 )
    _InterlockedExchange(v40, 0);
  v41 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x1Eu);
  *((_QWORD *)v5 + 936) = v41;
  if ( v41 )
    _InterlockedExchange(v41, 0);
  v42 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x20u);
  *((_QWORD *)v5 + 937) = v42;
  if ( v42 )
    _InterlockedExchange(v42, 0);
  v43 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x22u);
  *((_QWORD *)v5 + 938) = v43;
  if ( v43 )
    _InterlockedExchange(v43, 0);
  v44 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x24u);
  *((_QWORD *)v5 + 939) = v44;
  if ( v44 )
    _InterlockedExchange(v44, 0);
  v45 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x26u);
  *((_QWORD *)v5 + 940) = v45;
  if ( v45 )
    _InterlockedExchange(v45, 0);
  v46 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x2Au);
  *((_QWORD *)v5 + 941) = v46;
  if ( v46 )
    _InterlockedExchange(v46, 0);
  v47 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x2Cu);
  *((_QWORD *)v5 + 942) = v47;
  if ( v47 )
    _InterlockedExchange(v47, 0);
  v48 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x2Eu);
  *((_QWORD *)v5 + 943) = v48;
  if ( v48 )
    _InterlockedExchange(v48, 0);
  v49 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x30u);
  *((_QWORD *)v5 + 944) = v49;
  if ( v49 )
    _InterlockedExchange(v49, 0);
  v50 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x32u);
  *((_QWORD *)v5 + 945) = v50;
  if ( v50 )
    _InterlockedExchange(v50, 0);
  v51 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x34u);
  *((_QWORD *)v5 + 946) = v51;
  if ( v51 )
    _InterlockedExchange(v51, 0);
  v52 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x38u);
  *((_QWORD *)v5 + 947) = v52;
  if ( v52 )
    _InterlockedExchange(v52, 0);
  v53 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x3Au);
  *((_QWORD *)v5 + 948) = v53;
  if ( v53 )
    _InterlockedExchange(v53, 0);
  v54 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x3Cu);
  *((_QWORD *)v5 + 949) = v54;
  if ( v54 )
    _InterlockedExchange(v54, 0);
  v55 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x3Eu);
  *((_QWORD *)v5 + 950) = v55;
  if ( v55 )
    _InterlockedExchange(v55, 0);
  v56 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x42u);
  *((_QWORD *)v5 + 951) = v56;
  if ( v56 )
    _InterlockedExchange(v56, 0);
  v57 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x44u);
  *((_QWORD *)v5 + 952) = v57;
  if ( v57 )
    _InterlockedExchange(v57, 0);
  v58 = (volatile __int32 *)CGatheringService::GetCounter(v5, 0x46u);
  *((_QWORD *)v5 + 953) = v58;
  if ( v58 )
    _InterlockedExchange(v58, 0);
  v59 = (volatile __int32 *)*((_QWORD *)v5 + 928);
  if ( v59 )
    _InterlockedExchange(v59, 0);
  v60 = (volatile __int32 *)*((_QWORD *)v5 + 952);
  if ( v60 )
    _InterlockedExchange(v60, 0);
  v61 = (volatile __int32 *)*((_QWORD *)v5 + 953);
  if ( v61 )
    _InterlockedExchange(v61, 0);
  *((_DWORD *)v5 + 1908) = 0;
  if ( !CRegistry::GetValue(v5, L"PerformanceLevel", (unsigned int *)v5 + 140) )
  {
    *((_DWORD *)v5 + 140) = 3;
    CRegistry::SetValue(v5, L"PerformanceLevel", 3u);
  }
  if ( !CRegistry::GetValue(v5, L"RobotThreadsNumber", (unsigned int *)v5 + 318) )
  {
    *((_DWORD *)v5 + 318) = 0;
    CRegistry::SetValue(v5, L"RobotThreadsNumber", 0);
  }
  if ( !CRegistry::GetValue(v5, L"RetryIntervalSharingViolationSeconds", (unsigned int *)v5 + 890) )
  {
    *((_DWORD *)v5 + 890) = 5;
    CRegistry::SetValue(v5, L"RetryIntervalSharingViolationSeconds", 5u);
  }
  if ( !CRegistry::GetValue(v5, L"RetryIntervalSeconds", (unsigned int *)v5 + 891) )
  {
    *((_DWORD *)v5 + 891) = 120;
    CRegistry::SetValue(v5, L"RetryIntervalSeconds", 0x78u);
  }
  v139 = (unsigned int *)((char *)v5 + 3572);
  if ( !CRegistry::GetValue(v5, L"FilterHostProcessTimeout", (unsigned int *)v5 + 893) )
  {
    *((_DWORD *)v5 + 893) = 120000;
    CRegistry::SetValue(v5, L"FilterHostProcessTimeout", 0x1D4C0u);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"DisableBackOff", v137) )
  {
    *((_DWORD *)v5 + 897) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 897) = 0;
    CRegistry::SetValue(v5, L"DisableBackOff", 0);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"DisableBackOffOnUser", v137) )
  {
    *((_DWORD *)v5 + 898) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 898) = 0;
    CRegistry::SetValue(v5, L"DisableBackOffOnUser", 0);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"DisableBackOffOnNotifications", v137) )
  {
    *((_DWORD *)v5 + 899) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 899) = 1;
    CRegistry::SetValue(v5, L"DisableBackOffOnNotifications", 1u);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"DisableBackOffNotificationOverride", v137) )
  {
    *((_DWORD *)v5 + 900) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 900) = 1;
    CRegistry::SetValue(v5, L"DisableBackOffNotificationOverride", 1u);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffDelay", (unsigned int *)v5 + 902) )
  {
    *((_DWORD *)v5 + 902) = 10;
    CRegistry::SetValue(v5, L"BackOffDelay", 0xAu);
  }
  v62 = (_DWORD *)((char *)v5 + 3612);
  if ( !CRegistry::GetValue(v5, L"BackOffNotificationsRateThreshold", (unsigned int *)v5 + 903) )
  {
    *v62 = 0;
    CRegistry::SetValue(v5, L"BackOffNotificationsRateThreshold", 0);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffLowMemoryThresholdKB", (unsigned int *)v5 + 905) )
  {
    *((_DWORD *)v5 + 905) = 0x10000;
    CRegistry::SetValue(v5, L"BackOffLowMemoryThresholdKB", 0x10000u);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffLowDiskThresholdMB", (unsigned int *)v5 + 906) )
  {
    *((_DWORD *)v5 + 906) = 1024;
    CRegistry::SetValue(v5, L"BackOffLowDiskThresholdMB", 0x400u);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffNotificationsProcessingDelay", (unsigned int *)v5 + 907) )
  {
    *((_DWORD *)v5 + 907) = 0;
    CRegistry::SetValue(v5, L"BackOffNotificationsProcessingDelay", 0);
  }
  v63 = (_DWORD *)((char *)v5 + 3632);
  if ( !CRegistry::GetValue(v5, L"BackOffDelayedNotificationsLimit", (unsigned int *)v5 + 908) )
  {
    *v63 = 0;
    CRegistry::SetValue(v5, L"BackOffDelayedNotificationsLimit", 0);
  }
  v64 = (_DWORD *)((char *)v5 + 3636);
  if ( !CRegistry::GetValue(v5, L"BackOffNotificationsForceAtMost", (unsigned int *)v5 + 909) )
  {
    *v64 = 0;
    CRegistry::SetValue(v5, L"BackOffNotificationsForceAtMost", 0);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffFlushInterval", (unsigned int *)v5 + 912) )
  {
    *((_DWORD *)v5 + 912) = 0;
    CRegistry::SetValue(v5, L"BackOffFlushInterval", 0);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffOnUserActivityInterval1", (unsigned int *)v5 + 910) )
  {
    *((_DWORD *)v5 + 910) = 70;
    CRegistry::SetValue(v5, L"BackOffOnUserActivityInterval1", 0x46u);
  }
  if ( !CRegistry::GetValue(v5, L"BackOffOnUserActivityInterval2", (unsigned int *)v5 + 911) )
  {
    *((_DWORD *)v5 + 911) = 40;
    CRegistry::SetValue(v5, L"BackOffOnUserActivityInterval2", 0x28u);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55683212>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55683212>::GetImpl'::`2'::impl)
    && !CRegistry::GetValue(v5, L"BulkIndexingState", (unsigned int *)v5 + 896) )
  {
    *((_DWORD *)v5 + 896) = 0;
    CRegistry::SetValue(v5, L"BulkIndexingState", 0);
  }
  v65 = (volatile __int32 *)*((_QWORD *)v5 + 931);
  if ( v65 )
    _InterlockedExchange(v65, *((_DWORD *)v5 + 140));
  CGatheringService::CalculateResources(v5);
  v138 = 0;
  v66 = CoCreateInstance(
          &GUID_9e175b7f_f52a_11d8_b9a5_505054503030,
          0,
          0x17u,
          &GUID_2387139f_6fb0_4136_a971_0a698fd2b488,
          &v138);
  v67 = v66;
  if ( v66 < 0 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\cgathersvc.cxx\"",
      (const wchar_t *)0x213,
      (unsigned int)L"[SrchGatherSvc] CoCreate failed for back off controller, hr = 0x%08x",
      (const wchar_t *)(unsigned int)v66);
    if ( (byte_1802DA181 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v68, MSSearchTraceId_Startup_CGatheringService_Init_Stop, v67);
LABEL_160:
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v138);
    CSyncReadWrite::ReleaseWriteAccess((CRegistry *)((char *)v5 + 208));
LABEL_161:
    CRegistry::~CRegistry((CRegistry *)v162);
    return v67;
  }
  v141 = (CBackOffController **)((char *)v5 + 4000);
  TComNoUnkPointer<CPlugin>::operator=((char *)v5 + 4000, v138);
  v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v5 + 500) + 8LL) + 24LL))(*((_QWORD *)v5 + 500) + 8LL);
  v67 = v70;
  if ( v70 < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)(unsigned int)v70,
      ppva);
    if ( (byte_1802DA181 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v71, MSSearchTraceId_Startup_CGatheringService_Init_Stop, v67);
    goto LABEL_160;
  }
  v151[0] = off_18024D7E8;
  v151[1] = v5;
  v152 = v151;
  Policy = PolicyHelper::GetPolicy(L"DisableBackoff", 0, v151);
  v73 = v141;
  CBackOffController::SetBackoffFeatureState(*v141, 0, Policy != 0);
  if ( *((_DWORD *)v5 + 902) )
    CBackOffController::SetBackoffParameter(*v73, 9, *((unsigned int *)v5 + 902));
  if ( *v62 )
    CBackOffController::SetBackoffParameter(*v73, 1, (unsigned int)*v62);
  if ( *v63 )
    CBackOffController::SetBackoffParameter(*v73, 5, (unsigned int)*v63);
  if ( *v64 )
    CBackOffController::SetBackoffParameter(*v73, 8, (unsigned int)*v64);
  CBackOffController::SetBackoffParameter(*v73, 2, *((unsigned int *)v5 + 905));
  v149[0] = off_18024D818;
  v149[1] = v5;
  v150 = v149;
  if ( (unsigned int)PolicyHelper::GetPolicy(L"PreventIndexingLowDiskSpaceMB", 0, v149) )
    v74 = *((unsigned int *)v5 + 906);
  else
    v74 = 0;
  CBackOffController::SetBackoffParameter(*v73, 10, v74);
  CBackOffController::SetBackoffParameter(*v73, 4, *((unsigned int *)v5 + 907));
  CBackOffController::SetBackoffParameter(*v73, 13, *((unsigned int *)v5 + 912));
  if ( !CRegistry::GetValue(v5, L"MaxGrowFactor", (unsigned int *)v5 + 312) )
  {
    *((_DWORD *)v5 + 312) = 4;
    CRegistry::SetValue(v5, L"MaxGrowFactor", 4u);
  }
  if ( !CRegistry::GetValue(v5, L"ConnectTimeout", (unsigned int *)v5 + 313) )
  {
    *((_DWORD *)v5 + 313) = 20;
    CRegistry::SetValue(v5, L"ConnectTimeout", 0x14u);
  }
  if ( !CRegistry::GetValue(v5, L"DataTimeout", (unsigned int *)v5 + 314) )
  {
    *((_DWORD *)v5 + 314) = 20;
    CRegistry::SetValue(v5, L"DataTimeout", 0x14u);
  }
  if ( !CRegistry::GetValue(v5, L"RetryLimit", (unsigned int *)v5 + 315) )
  {
    *((_DWORD *)v5 + 315) = 4;
    CRegistry::SetValue(v5, L"RetryLimit", 4u);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"DebugFilters", v137) )
  {
    *((_DWORD *)v5 + 316) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 316) = 0;
    CRegistry::SetValue(v5, L"DebugFilters", 0);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"DebugWordBreakers", v137) )
  {
    *((_DWORD *)v5 + 317) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 317) = 0;
    CRegistry::SetValue(v5, L"DebugWordBreakers", 0);
  }
  CRegistry::GetValue(v5, L"UserAgent", (CRegistry *)((char *)v5 + 568));
  CRegistry::GetValue(v5, L"EmailAddress", (CRegistry *)((char *)v5 + 664));
  CRegistry::GetValue(v5, L"DefaultApplicationsPath", (CRegistry *)((char *)v5 + 400));
  CRegistry::GetValue(v5, L"TempPath", (CRegistry *)((char *)v5 + 760));
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"UseSystemTemp", v137) )
  {
    *((_DWORD *)v5 + 270) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 270) = 1;
    CRegistry::SetValue(v5, L"UseSystemTemp", 1u);
  }
  if ( !CRegistry::GetValue(v5, L"UseProxy", (unsigned int *)v5 + 326) )
  {
    *((_DWORD *)v5 + 326) = 0;
    CRegistry::SetValue(v5, L"UseProxy", 0);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"LocalByPassProxy", v137) )
  {
    *((_DWORD *)v5 + 327) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 327) = 0;
    CRegistry::SetValue(v5, L"LocalByPassProxy", 0);
  }
  CRegistry::GetValue(v5, L"ProxyName", (CRegistry *)((char *)v5 + 1312));
  if ( !CRegistry::GetValue(v5, L"PortNumber", (unsigned int *)v5 + 368) )
  {
    *((_DWORD *)v5 + 368) = 0;
    CRegistry::SetValue(v5, L"PortNumber", 0);
  }
  CRegistry::GetValue(v5, L"ByPassList", (CRegistry *)((char *)v5 + 1480));
  v75 = (int *)((char *)v5 + 1276);
  v147 = (char *)v5 + 1276;
  if ( !CRegistry::GetValue(v5, L"FilterProcessMemoryQuota", (unsigned int *)v5 + 319) )
  {
    *v75 = 104857600;
    CRegistry::SetValue(v5, L"FilterProcessMemoryQuota", 0x6400000u);
  }
  v76 = (int *)((char *)v5 + 1280);
  v148 = (char *)v5 + 1280;
  if ( !CRegistry::GetValue(v5, L"DedicatedFilterProcessMemoryQuota", (unsigned int *)v5 + 320) )
  {
    *v76 = 104857600;
    CRegistry::SetValue(v5, L"DedicatedFilterProcessMemoryQuota", 0x6400000u);
  }
  if ( !CRegistry::GetValue(v5, L"PluginPingFrequency", (unsigned int *)v5 + 321) )
  {
    *((_DWORD *)v5 + 321) = 2;
    CRegistry::SetValue(v5, L"PluginPingFrequency", 2u);
  }
  if ( !CRegistry::GetValue(v5, L"EvictionCheckFrequency", (unsigned int *)v5 + 322) )
  {
    *((_DWORD *)v5 + 322) = 5;
    CRegistry::SetValue(v5, L"EvictionCheckFrequency", 5u);
  }
  if ( !CRegistry::GetValue(v5, L"MinEvictionTime", (unsigned int *)v5 + 323) )
  {
    *((_DWORD *)v5 + 323) = 2592000;
    CRegistry::SetValue(v5, L"MinEvictionTime", 0x278D00u);
  }
  if ( !CRegistry::GetValue(v5, L"GathererHeartbeat", (unsigned int *)v5 + 324) )
  {
    *((_DWORD *)v5 + 324) = 60;
    CRegistry::SetValue(v5, L"GathererHeartbeat", 0x3Cu);
  }
  if ( !CRegistry::GetValue(v5, L"LinksInMemoryCacheSize", (unsigned int *)v5 + 325) )
  {
    *((_DWORD *)v5 + 325) = 100;
    CRegistry::SetValue(v5, L"LinksInMemoryCacheSize", 0x64u);
  }
  if ( !CRegistry::GetValue(v5, L"StoreAppSizeReportThresholdInPercent", (unsigned int *)v5 + 894) )
  {
    *((_DWORD *)v5 + 894) = 25;
    CRegistry::SetValue(v5, L"StoreAppSizeReportThresholdInPercent", 0x19u);
  }
  if ( !CRegistry::GetValue(v5, L"StoreAppSizePerDocumentInByte", (unsigned int *)v5 + 895) )
  {
    *((_DWORD *)v5 + 895) = 20;
    CRegistry::SetValue(v5, L"StoreAppSizePerDocumentInByte", 0x14u);
  }
  v137[0] = 0;
  if ( CRegistry::GetValue(v5, L"IgnoreCertCNError", v137) )
  {
    *((_DWORD *)v5 + 892) = v137[0];
  }
  else
  {
    *((_DWORD *)v5 + 892) = 0;
    CRegistry::SetValue(v5, L"IgnoreCertCNError", 0);
  }
  lpValue = (LPCWSTR)&v161;
  v160 = 65;
  v161 = 0;
  v158 = &CCICommonPathString::`vftable';
  Buffer = CLMString::GetBuffer((CLMString *)&v158, 0);
  TempPath2W = GetTempPath2W((unsigned int)v160, Buffer);
  v80 = TempPath2W;
  if ( TempPath2W > (unsigned int)v160 )
  {
    v81 = CLMString::GetBuffer((CLMString *)&v158, TempPath2W);
    v80 = GetTempPath2W(v80, v81);
  }
  if ( !v80 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x28A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      v79);
  CLMString::Truncate((CLMString *)&v158, v80);
  TLMString<192,64,32767>::operator=((char *)v5 + 1088, &v158);
  v82 = *((_DWORD *)v5 + 195);
  if ( v82 <= 3 || *((_DWORD *)v5 + 270) )
  {
    v84 = 1;
  }
  else
  {
    for ( i = v82 - 1; (int)i >= 0; i = (unsigned int)(i - 1) )
    {
      if ( *(_WORD *)(*((_QWORD *)v5 + 96) + 2 * i) == 92 )
        break;
    }
    CLMString::Mid((char *)v5 + 760, v137, 0);
    CLMString::operator=(&v158, v137);
    v84 = 0;
  }
  CGatheringService::SetUseSystemTemp(v5, v84);
  try
  {
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)lpValue, v85);
    v87 = DirectoryDeepNoThrow;
    if ( DirectoryDeepNoThrow < 0 )
    {
      v132 = wil::verify_hresult<long>((unsigned int)DirectoryDeepNoThrow);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)v132,
        ppva);
    }
    AppendBackSlashIf((struct CLMString *)&v158);
    CLMString::Append((CLMString *)&v158, L"usgthrsvc", 0xFFFFFFFF);
    FSOp::CreateDirectoryWithSecurity((wchar_t *)lpValue, 0, 0, v88);
    SetEnvironmentVariableW(L"TMP", lpValue);
    SetEnvironmentVariableW(L"TEMP", lpValue);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      691,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx");
  }
  v89 = v143;
  if ( v87 < 0 )
  {
    CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v165, *((struct CEventLog **)v5 + 49));
    CSearchEventEntry::SetError((CSearchEventEntry *)v165, -2147023264);
    CSearchEventEntry::ReportError((CSearchEventEntry *)v165, 0xC0000BD6, 0);
    CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v165);
  }
  v90 = (CFilterPool **)Recipient[0];
  v91 = *(_QWORD *)Recipient[0];
  if ( !*(_BYTE *)(*(_QWORD *)Recipient[0] + 1448LL) )
  {
    v92 = *v75;
    *(_DWORD *)(v91 + 684) = *v75;
    *(_DWORD *)(v91 + 692) = v92;
  }
  v93 = *v90;
  if ( !*((_BYTE *)*v90 + 1448) )
  {
    v94 = *v76;
    *((_DWORD *)v93 + 172) = *v76;
    *((_DWORD *)v93 + 174) = v94;
  }
  CFilterPool::SetThreadsPerFilterDaemon(*v90, *((_DWORD *)v5 + 972));
  if ( !*((_BYTE *)*v90 + 1448) )
    CFilterPoolBase::SetMaxProcesses((CFilterPool *)((char *)*v90 + 24), v95);
  v96 = CFilterPoolBase::Init((CFilterPool *)((char *)*v90 + 24), L"MssGthrPipe");
  v67 = v96;
  if ( v96 < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)(unsigned int)v96,
      ppva);
    if ( (byte_1802DA181 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v97, MSSearchTraceId_Startup_CGatheringService_Init_Stop, v67);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
    if ( v150 )
    {
      v98 = v149;
      LOBYTE(v98) = v150 != v149;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v98);
      v150 = 0;
    }
    if ( v152 )
    {
      v99 = v151;
      LOBYTE(v99) = v152 != v151;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v99);
      v152 = 0;
    }
LABEL_297:
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v138);
    CSyncReadWrite::ReleaseWriteAccess(v16);
    goto LABEL_161;
  }
  v100 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)v5 + 4152);
  CurrentProcess = GetCurrentProcess();
  v102 = GetCurrentProcess();
  v103 = GetCurrentProcess();
  if ( DuplicateHandle(v103, v102, CurrentProcess, v100, 0x100000u, 1, 0)
    || (Error = (const char *)(unsigned int)ResultFromLastError(),
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x2DA,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          Error,
          ppvb),
        SearchIndexerTrace::Error(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\cgathersvc.cxx\"",
          (const wchar_t *)0x2DB,
          (unsigned int)L"[SrchGatherSvc] DuplicateHandle failed with hr = 0x%08x",
          (const wchar_t *)(unsigned int)Error),
        (int)Error >= 0) )
  {
    *(_QWORD *)v137 = 0;
    LODWORD(Error) = ATL::CComObject<CAccessControl>::CreateInstance(v137);
    if ( (int)Error >= 0 )
    {
      TComNoUnkPointer<CPlugin>::operator=((char *)v5 + 384, *(_QWORD *)v137);
      v105 = CAccessControlImpl::Init(*((CAccessControlImpl **)v5 + 48), v5, 1u, 0);
      LODWORD(Error) = v105;
      if ( v105 >= 0 )
      {
        *((_BYTE *)v5 + 7224) = LookupPerVolumeCatalogConfiguration();
        if ( (unsigned __int8)IsAnyEnabled<wil::Feature<__WilFeatureTraits_Feature_56981110>,wil::Feature<__WilFeatureTraits_Feature_55904201>>()
          && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
        {
          Recipient[1] = 0;
          Recipient[0] = CGatheringService::s_PowerStateChangeCallbackForSemanticSearch;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void ClosePowerNotifyHandleHelper(void *)>>::reset(
            (char *)v5 + 4200,
            0);
          PowerSettingRegisterNotification(&GUID_ACDC_POWER_SOURCE, 2u, Recipient, (PHPOWERNOTIFY)v5 + 525);
        }
        v106 = CBackOffController::RegisterCrmPolicies(*v141);
        v67 = v106;
        if ( v106 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x303,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)v106,
            ppvb);
          TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
          if ( v150 )
          {
            v107 = v149;
            LOBYTE(v107) = v150 != v149;
            (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v107);
            v150 = 0;
          }
          if ( v152 )
          {
            v108 = v151;
            LOBYTE(v108) = v152 != v151;
            (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v108);
            v152 = 0;
          }
          goto LABEL_297;
        }
        if ( v89 )
          std::vector<unsigned short>::swap(v89, (char *)v5 + 184);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E7,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          (const char *)(unsigned int)v105,
          ppvb);
      }
    }
  }
  v153[0] = off_18024D848;
  v153[1] = v5;
  v157 = v153;
  std::function<long (wchar_t const *,wchar_t const *,IGather * *)>::operator=((char *)v5 + 6688, v153);
  std::function<unsigned long (PolicyParameters)>::~function<unsigned long (PolicyParameters)>(v153);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v5 + 7312);
  HandlerList = CreateHandlerList(v110, v109, (struct ISearchHandlerList **)v5 + 914);
  v67 = HandlerList;
  if ( HandlerList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)(unsigned int)HandlerList,
      ppvb);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
    if ( v150 )
    {
      v112 = v149;
      LOBYTE(v112) = v150 != v149;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v112);
      v150 = 0;
    }
    if ( v152 )
    {
      v113 = v151;
      LOBYTE(v113) = v152 != v151;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v113);
      v152 = 0;
    }
    goto LABEL_297;
  }
  if ( *((_QWORD *)v5 + 956) )
    winrt::com_ptr<IDatabase>::unconditional_release_ref((char *)v5 + 7648);
  FilterHostProcessPoolManager = CreateFilterHostProcessPoolManager(
                                   *v139,
                                   *((struct ISearchHandlerList **)v5 + 914),
                                   (struct IFilterHostProcessPoolManager **)v5 + 956);
  v67 = FilterHostProcessPoolManager;
  if ( FilterHostProcessPoolManager < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)(unsigned int)FilterHostProcessPoolManager,
      ppvb);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
    if ( v150 )
    {
      v115 = v149;
      LOBYTE(v115) = v150 != v149;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v115);
      v150 = 0;
    }
    if ( v152 )
    {
      v116 = v151;
      LOBYTE(v116) = v152 != v151;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v116);
      v152 = 0;
    }
    goto LABEL_297;
  }
  GetContainerStatusManager(&v139);
  if ( !v139 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
      (const char *)0x8007000ELL,
      ppvb);
    if ( v140 )
      std::_Ref_count_base::_Decref(v140);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
    if ( v150 )
    {
      v117 = v149;
      LOBYTE(v117) = v150 != v149;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v117);
      v150 = 0;
    }
    if ( v152 )
    {
      v118 = v151;
      LOBYTE(v118) = v152 != v151;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v118);
      v152 = 0;
    }
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v138);
    CSyncReadWrite::ReleaseWriteAccess(v16);
    v67 = -2147024882;
    goto LABEL_161;
  }
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    (PINIT_ONCE_FN)_lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
  {
    v120 = GetCurrentProcess();
    JobManagerInstance = GetJobManagerInstance(v120);
    v67 = JobManagerInstance;
    if ( JobManagerInstance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x328,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)JobManagerInstance,
        ppvb);
      if ( v140 )
        std::_Ref_count_base::_Decref(v140);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
      if ( v150 )
      {
        v122 = v149;
        LOBYTE(v122) = v150 != v149;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v122);
        v150 = 0;
      }
      if ( v152 )
      {
        v123 = v151;
        LOBYTE(v123) = v152 != v151;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v123);
        v152 = 0;
      }
      goto LABEL_297;
    }
  }
  if ( (byte_1802DA181 & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(v119, MSSearchTraceId_Startup_CGatheringService_Init_Stop, (unsigned int)Error);
  if ( v140 )
    std::_Ref_count_base::_Decref(v140);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v158);
  if ( v150 )
  {
    v124 = v149;
    LOBYTE(v124) = v150 != v149;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v150 + 32LL))(v150, v124);
    v150 = 0;
  }
  if ( v152 )
  {
    v125 = v151;
    LOBYTE(v125) = v152 != v151;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v152 + 32LL))(v152, v125);
    v152 = 0;
  }
  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v138);
  CSyncReadWrite::ReleaseWriteAccess(v16);
  CRegistry::~CRegistry((CRegistry *)v162);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18017d66c  mov     [rsp+arg_0], rbx
0x18017d671  mov     [rsp+arg_8], rsi
0x18017d676  push    rdi
0x18017d677  push    r12
0x18017d679  push    r13
0x18017d67b  push    r14
0x18017d67d  push    r15
0x18017d67f  sub     rsp, 0C60h
0x18017d686  mov     rax, cs:__security_cookie
0x18017d68d  xor     rax, rsp
0x18017d690  mov     [rsp+0C88h+var_38], rax
0x18017d698  mov     rsi, r8
0x18017d69b  mov     [rsp+0C88h+var_C00], r8
0x18017d6a3  mov     edi, edx
0x18017d6a5  mov     [rsp+0C88h+var_BE8], r8
0x18017d6ad  mov     r13, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18017d6b4  mov     [rsp+0C88h+var_BF0], r13
0x18017d6bc  test    cs:byte_1802DA181, 8
0x18017d6c3  jz      short loc_18017D6CA
0x18017d6c5  call    McTemplateU0t_EventWriteTransfer
0x18017d6ca  mov     ebx, 0F003Fh
0x18017d6cf  mov     r8d, ebx; unsigned int
0x18017d6d2  xor     edx, edx; wchar_t *
0x18017d6d4  lea     rcx, [rsp+0C88h+var_A68]; this
0x18017d6dc  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x18017d6e1  nop
0x18017d6e2  mov     rax, [rsp+0C88h+var_A58]
0x18017d6ea  mov     [rsp+0C88h+ppv], rax; int
0x18017d6ef  mov     r9d, ebx; unsigned int
0x18017d6f2  lea     r8, aGatheringManag_0; "Gathering Manager"
0x18017d6f9  mov     rdx, [rsp+0C88h+var_9B8]; HKEY
0x18017d701  mov     rcx, r13; this
0x18017d704  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x18017d709  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18017d710  mov     rdx, r14; struct std::nothrow_t *
0x18017d713  mov     ecx, 1340h; unsigned __int64
0x18017d718  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18017d71d  mov     [rsp+0C88h+var_C28], rax
0x18017d722  xor     r15d, r15d
0x18017d725  test    rax, rax
0x18017d728  jz      short loc_18017D734
0x18017d72a  mov     rcx, rax; this
0x18017d72d  call    ??0CPhMultiArch@@QEAA@XZ; CPhMultiArch::CPhMultiArch(void)
0x18017d732  jmp     short loc_18017D737
0x18017d734  mov     rax, r15
0x18017d737  mov     [r13+168h], rax
0x18017d73e  test    rax, rax
0x18017d741  jz      loc_18017F4F8
0x18017d747  call    ?SystemInfo@System@@YAAEBVCSystemInfo@1@XZ; System::SystemInfo(void)
0x18017d74c  mov     edx, [rax+20h]
0x18017d74f  shl     edx, 2; lInitialCount
0x18017d752  lea     rbx, [r13+1030h]
0x18017d759  xor     r9d, r9d; lpName
0x18017d75c  mov     r8d, edx; lMaximumCount
0x18017d75f  xor     ecx, ecx; lpSemaphoreAttributes
0x18017d761  call    cs:__imp_CreateSemaphoreW
0x18017d767  mov     rdx, rax
0x18017d76a  mov     rcx, rbx
0x18017d76d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18017d772  mov     rax, [rbx]
0x18017d775  dec     rax
0x18017d778  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18017d77c  ja      loc_18017F4DE
0x18017d782  lea     eax, [rdi-1]
0x18017d785  test    eax, 0FFFFFFFDh
0x18017d78a  setz    al
0x18017d78d  mov     [r13+170h], al
0x18017d794  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x18017d79b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x18017d7a0  test    al, al
0x18017d7a2  jnz     short loc_18017D7CD
0x18017d7a4  call    ?GetIsSemanticIndexingActive@@YAHXZ; GetIsSemanticIndexingActive(void)
0x18017d7a9  test    eax, eax
0x18017d7ab  jz      short loc_18017D7CD
0x18017d7ad  xor     ecx, ecx
0x18017d7af  call    ?SetClearSemanticIndexStore@@YAXW4SemanticIndexStoreType@@@Z; SetClearSemanticIndexStore(SemanticIndexStoreType)
0x18017d7b4  mov     ecx, 1
0x18017d7b9  call    ?SetClearSemanticIndexStore@@YAXW4SemanticIndexStoreType@@@Z; SetClearSemanticIndexStore(SemanticIndexStoreType)
0x18017d7be  mov     [rsp+0C88h+var_C48], r15b
0x18017d7c3  lea     rcx, [rsp+0C88h+var_C48]; bool *
0x18017d7c8  call    ?SetIsSemanticIndexingActive@@YAXAEB_N@Z; SetIsSemanticIndexingActive(bool const &)
0x18017d7cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x18017d7d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x18017d7d9  test    al, al
0x18017d7db  jz      loc_18017D880
0x18017d7e1  mov     [rsp+0C88h+var_C40], 11h
0x18017d7e9  mov     [rsp+0C88h+bInheritHandle], 4; unsigned int
0x18017d7f1  lea     rax, [rsp+0C88h+var_C40]
0x18017d7f6  mov     [rsp+0C88h+ppv], rax; int
0x18017d7fb  mov     r9d, 4; unsigned int
0x18017d801  lea     r8, aSemanticindexi; "SemanticIndexingStatus"
0x18017d808  lea     rdx, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x18017d80f  call    ?WSearchRegSetKeyValue@@YAJPEAUHKEY__@@PEB_W1KPEBXK@Z; WSearchRegSetKeyValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong)
0x18017d814  nop
0x18017d815  lea     rcx, [rsp+0C88h+var_C18]
0x18017d81a  call    ?GetInstance@SemanticSearchConfigManager@SemanticSearch@Indexer@Windows@winrt@@SA?AU12345@XZ; winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(void)
0x18017d81f  mov     rcx, [rax]
0x18017d822  lea     rax, [rcx-10h]
0x18017d826  neg     rcx
0x18017d829  sbb     rbx, rbx
0x18017d82c  and     rbx, rax
0x18017d82f  lea     rcx, [rsp+0C88h+var_C18]; this
0x18017d834  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18017d839  mov     rcx, rbx
0x18017d83c  call    ?ValidateSemanticSearchSettings@SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@QEAA?AW4SemanticIndexingStatus@@XZ; winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::ValidateSemanticSearchSettings(void)
0x18017d841  cmp     eax, 0Eh
0x18017d844  jnz     short loc_18017D86C
0x18017d846  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54620742@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54620742@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742> `wil::Feature<__WilFeatureTraits_Feature_54620742>::GetImpl(void)'::`2'::impl
0x18017d84d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54620742@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54620742>::__private_IsEnabled(void)
0x18017d852  mov     rcx, rbx; this
0x18017d855  test    al, al
0x18017d857  jz      short loc_18017D860
0x18017d859  call    ?CreateKeyWithRetriesAndCheckForModels@SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@QEAAXXZ; winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::CreateKeyWithRetriesAndCheckForModels(void)
0x18017d85e  jmp     short loc_18017D880
0x18017d860  lea     rdx, [rsp+0C88h+var_C48]
0x18017d865  call    ?StartCheckForModelsAvailability@SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@QEAA?AUfire_and_forget@6@XZ; winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::StartCheckForModelsAvailability(void)
0x18017d86a  jmp     short loc_18017D880
0x18017d86c  mov     [rsp+0C88h+var_C48], r15b
0x18017d871  mov     r8b, 1
0x18017d874  mov     edx, eax
0x18017d876  lea     rcx, [rsp+0C88h+var_C48]
0x18017d87b  call    ?SetIsSemanticIndexingAllowed@@YAXAEB_NW4SemanticIndexingStatus@@_N@Z; SetIsSemanticIndexingAllowed(bool const &,SemanticIndexingStatus,bool)
0x18017d880  cmp     edi, 4
0x18017d883  jnz     loc_18017D951
0x18017d889  lea     rcx, aSrchgathersvcS_7; "[SrchGatherSvc] System index is marked "...
0x18017d890  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18017d895  mov     rdx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18017d89c  test    rdx, rdx
0x18017d89f  jz      short loc_18017D8D9
0x18017d8a1  mov     rdx, [rdx+188h]; struct CEventLog *
0x18017d8a8  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017d8b0  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x18017d8b5  nop
0x18017d8b6  xor     r8d, r8d
0x18017d8b9  mov     edx, 40000E13h; unsigned int
0x18017d8be  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017d8c6  call    ?ReportInformation@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportInformation(ulong,...)
0x18017d8cb  nop
0x18017d8cc  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017d8d4  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x18017d8d9  test    rsi, rsi
0x18017d8dc  jz      short loc_18017D945
0x18017d8de  mov     rdx, [rsi+8]
0x18017d8e2  cmp     [rsi], rdx
0x18017d8e5  jz      short loc_18017D8F6
0x18017d8e7  mov     rcx, [rsi]; this
0x18017d8ea  call    ??$_Destroy_range@V?$allocator@UMachineWithAumid@CPhMultiArch@@@std@@@std@@YAXPEAUMachineWithAumid@CPhMultiArch@@QEAU12@AEAV?$allocator@UMachineWithAumid@CPhMultiArch@@@0@@Z; std::_Destroy_range<std::allocator<CPhMultiArch::MachineWithAumid>>(CPhMultiArch::MachineWithAumid *,CPhMultiArch::MachineWithAumid * const,std::allocator<CPhMultiArch::MachineWithAumid> &)
0x18017d8ef  mov     rax, [rsi]
0x18017d8f2  mov     [rsi+8], rax
0x18017d8f6  lea     rdx, asc_18025DCBC; "*"
0x18017d8fd  lea     rcx, [rsp+0C88h+var_B48]
0x18017d905  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18017d90a  mov     [rsp+0C88h+var_B28], 101h
0x18017d914  xor     eax, eax
0x18017d916  mov     [rsp+0C88h+var_B26], eax
0x18017d91d  mov     [rsp+0C88h+var_B22], ax
0x18017d925  lea     rdx, [rsp+0C88h+var_B48]
0x18017d92d  mov     rcx, rsi
0x18017d930  call    ?push_back@?$vector@VReIndexPatternInfo@@V?$allocator@VReIndexPatternInfo@@@std@@@std@@QEAAX$$QEAVReIndexPatternInfo@@@Z; std::vector<ReIndexPatternInfo>::push_back(ReIndexPatternInfo &&)
0x18017d935  nop
0x18017d936  lea     rcx, [rsp+0C88h+var_B48]; this
0x18017d93e  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18017d943  jmp     short loc_18017D951
0x18017d945  lea     rcx, aSrchgathersvcI_1; "[SrchGatherSvc] Inplace indexing Failed"...
0x18017d94c  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18017d951  lea     rbx, [r13+0D0h]
0x18017d958  mov     [rsp+0C88h+var_BF8], rbx
0x18017d960  mov     rcx, rbx; this
0x18017d963  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x18017d968  nop
0x18017d969  mov     qword ptr [rsp+0C88h+var_C40], r15
0x18017d96e  lea     rcx, [rsp+0C88h+var_C40]
0x18017d973  call    ?CreateInstance@?$CComObject@VCGatherApplicationCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CGatherApplicationCollection>::CreateInstance(ATL::CComObject<CGatherApplicationCollection> * *)
0x18017d978  test    eax, eax
0x18017d97a  js      loc_18017F51F
0x18017d980  lea     rcx, [r13+178h]
0x18017d987  mov     rdx, qword ptr [rsp+0C88h+var_C40]
0x18017d98c  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x18017d991  mov     rdx, r14; struct std::nothrow_t *
0x18017d994  mov     ecx, 100h; unsigned __int64
0x18017d999  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18017d99e  mov     [rsp+0C88h+var_C28], rax
0x18017d9a3  test    rax, rax
0x18017d9a6  jz      short loc_18017D9B2
0x18017d9a8  mov     rcx, rax; this
0x18017d9ab  call    ??0CRobotThreadPool@@QEAA@XZ; CRobotThreadPool::CRobotThreadPool(void)
0x18017d9b0  jmp     short loc_18017D9B5
0x18017d9b2  mov     rax, r15
0x18017d9b5  mov     [r13+0F40h], rax
0x18017d9bc  test    rax, rax
0x18017d9bf  jz      loc_18017F543
0x18017d9c5  mov     rdx, r14; struct std::nothrow_t *
0x18017d9c8  mov     ecx, 80h; unsigned __int64
0x18017d9cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18017d9d2  mov     [rsp+0C88h+var_C28], rax
0x18017d9d7  test    rax, rax
0x18017d9da  jz      short loc_18017D9ED
0x18017d9dc  mov     rdx, [r13+0F40h]; struct CRobotThreadPool *
0x18017d9e3  mov     rcx, rax; this
0x18017d9e6  call    ??0CActiveQueue@@QEAA@AEAVCRobotThreadPool@@@Z; CActiveQueue::CActiveQueue(CRobotThreadPool &)
0x18017d9eb  jmp     short loc_18017D9F0
0x18017d9ed  mov     rax, r15
0x18017d9f0  mov     [r13+0F48h], rax
0x18017d9f7  test    rax, rax
0x18017d9fa  jz      loc_18017F56A
0x18017da00  mov     qword ptr [rsp+0C88h+var_C40], r15
0x18017da05  lea     rcx, [rsp+0C88h+var_C40]
0x18017da0a  call    ?CreateInstance@?$CComObject@VCFilterPool@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterPool>::CreateInstance(ATL::CComObject<CFilterPool> * *)
0x18017da0f  test    eax, eax
0x18017da11  js      loc_18017F591
0x18017da17  lea     rcx, [r13+0F50h]
0x18017da1e  mov     [rsp+0C88h+Recipient], rcx
0x18017da23  mov     rdx, qword ptr [rsp+0C88h+var_C40]
0x18017da28  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x18017da2d  mov     rdx, r14; struct std::nothrow_t *
0x18017da30  mov     r14d, 38h ; '8'
0x18017da36  mov     ecx, r14d; unsigned __int64
0x18017da39  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18017da3e  mov     rdi, rax
0x18017da41  mov     [rsp+0C88h+var_C28], rax
0x18017da46  test    rax, rax
0x18017da49  jz      short loc_18017DA5F
0x18017da4b  mov     rcx, rax; this
0x18017da4e  call    ??0CThread@@IEAA@XZ; CThread::CThread(void)
0x18017da53  lea     rax, ??_7CTimerThread@@6B@; const CTimerThread::`vftable'
0x18017da5a  mov     [rdi], rax
0x18017da5d  jmp     short loc_18017DA62
0x18017da5f  mov     rdi, r15
0x18017da62  mov     [r13+0F90h], rdi
0x18017da69  test    rdi, rdi
0x18017da6c  jz      loc_18017F5B5
0x18017da72  lea     r10, [r13+1160h]
0x18017da79  mov     esi, 10h
0x18017da7e  mov     r9d, esi; unsigned __int64
0x18017da81  lea     r8, aUgthrsvc; "UGTHRSVC"
0x18017da88  mov     edx, esi; unsigned __int64
0x18017da8a  mov     rcx, r10; wchar_t *
0x18017da8d  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18017da92  lea     rdi, [r13+1230h]
0x18017da99  mov     r9d, esi; unsigned __int64
0x18017da9c  lea     r8, aUgthrsvcobj; "UGthrSvcObj"
0x18017daa3  mov     edx, esi; unsigned __int64
0x18017daa5  mov     rcx, rdi; wchar_t *
0x18017daa8  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18017daad  mov     rcx, r10; this
0x18017dab0  call    ?Init@PerfLibrary@@QEAAHXZ; PerfLibrary::Init(void)
0x18017dab5  test    eax, eax
0x18017dab7  jnz     short loc_18017DAFE
0x18017dab9  lea     r8, aSrchgathersvcE_3; "[SrchGatherSvc] Error initializing perf"...
0x18017dac0  mov     edx, 1B9h; wchar_t *
0x18017dac5  lea     rcx, aOnecoreuapBase_186; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18017dacc  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18017dad1  mov     rdx, [r13+188h]; struct CEventLog *
0x18017dad8  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017dae0  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x18017dae5  nop
0x18017dae6  xor     r8d, r8d
0x18017dae9  mov     edx, 0C0000BBEh; unsigned int
0x18017daee  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017daf6  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x18017dafb  nop
0x18017dafc  jmp     short loc_18017DB57
0x18017dafe  xor     edx, edx; wchar_t *
0x18017db00  mov     rcx, rdi; this
0x18017db03  call    ?CreateObjectInstance@PerfObjectDefinition@@QEAAPEAVPerfObjectInstance@@PEB_W@Z; PerfObjectDefinition::CreateObjectInstance(wchar_t const *)
0x18017db08  mov     [r13+1A10h], rax
0x18017db0f  test    rax, rax
0x18017db12  jnz     short loc_18017DB64
0x18017db14  lea     r8, aSrchgathersvcE; "[SrchGatherSvc] Error creating perfmon "...
0x18017db1b  mov     edx, 1C2h; wchar_t *
0x18017db20  lea     rcx, aOnecoreuapBase_186; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18017db27  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18017db2c  mov     rdx, [r13+188h]; struct CEventLog *
0x18017db33  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017db3b  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x18017db40  nop
0x18017db41  xor     r8d, r8d
0x18017db44  mov     edx, 0C0000BBEh; unsigned int
0x18017db49  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017db51  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x18017db56  nop
0x18017db57  lea     rcx, [rsp+0C88h+var_9A8]; this
0x18017db5f  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x18017db64  mov     edx, 2; unsigned int
0x18017db69  mov     rcx, r13; this
0x18017db6c  call    ?GetCounter@CGatheringService@@IEAAPEAKK@Z; CGatheringService::GetCounter(ulong)
0x18017db71  mov     [r13+1CE0h], rax
0x18017db78  test    rax, rax
0x18017db7b  jz      short loc_18017DB82
0x18017db7d  mov     ecx, r15d
0x18017db80  xchg    ecx, [rax]
0x18017db82  mov     edx, 4; unsigned int
0x18017db87  mov     rcx, r13; this
0x18017db8a  call    ?GetCounter@CGatheringService@@IEAAPEAKK@Z; CGatheringService::GetCounter(ulong)
0x18017db8f  mov     [r13+1CE8h], rax
0x18017db96  test    rax, rax
0x18017db99  jz      short loc_18017DBA0
0x18017db9b  mov     ecx, r15d
0x18017db9e  xchg    ecx, [rax]
0x18017dba0  mov     edx, 8; unsigned int
  ... truncated ...
```
