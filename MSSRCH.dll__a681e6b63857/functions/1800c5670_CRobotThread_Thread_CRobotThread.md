# CRobotThread::Thread(CRobotThread *)

- ea: `0x1800c5670`
- end: `0x1800c7837`
- name: `?Thread@CRobotThread@@SAJPEAV1@@Z`
- size: `8647`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `154`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a23c`
- `0x18000c760`
- `0x18000d0d0`
- `0x18000e40c`
- `0x18000e478`
- `0x18000e4a4`
- `0x18000ebb8`
- `0x18000f880`
- `0x180012120`
- `0x180012318`
- `0x180012370`
- `0x180013d40`
- `0x180013dd4`
- `0x180014ff0`
- `0x1800181b8`
- `0x180018a00`
- `0x18001d8a0`
- `0x180021e58`
- `0x180022b10`
- `0x180027164`
- `0x180027540`
- `0x180027970`
- `0x1800284e0`
- `0x1800294e4`
- `0x1800296b0`
- `0x18002dc6c`
- `0x18002e44c`
- `0x180032fcc`
- `0x180033120`
- `0x18003f9d4`
- `0x1800400ec`
- `0x1800412bc`
- `0x18004b348`
- `0x18005c150`
- `0x18005f648`
- `0x18005fde4`
- `0x18006059c`
- `0x180062b80`
- `0x180067318`
- `0x180067e64`
- `0x1800686c4`
- `0x180069318`
- `0x18006a618`
- `0x18006d080`
- `0x1800723ac`
- `0x1800723dc`
- `0x18007595c`
- `0x180079c44`
- `0x180079c7c`
- `0x180079d34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5832`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5832`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800c76a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800c76a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c6ed5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c6ed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c5910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c5910`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c5d5f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c6c8c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c5d5f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c6c8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c5de8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c5e00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c60ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c611f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c5de8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c5e00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c60ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c611f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c5815`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c5815`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x1800c592b`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x1800c592b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c56bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c56bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c574f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c77b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c574f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c77b8`

## string_xrefs

- `0x1800c580e`: `tquery.dll`
- `0x1800c56fc`: `Robot Thread`
- `0x1800c5828`: `ExternPropagateEventToOpenQueries`
- `0x1800c6362`: `RobotThreadTransactionPerfTest::reason::ImageCategoryGenerationFailed`
- `0x1800c6ba3`: `RobotThread - Protocol Handler reports PRTH_S_NOTMODIFIED - skipping indexing`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
__int64 __fastcall CRobotThread::Thread(CThread *Parameter)
{
  CThread *v1; // r13
  __int64 v2; // r8
  CActiveQueue *v3; // r14
  int inited; // eax
  unsigned int v5; // ebx
  __int64 v7; // rsi
  __int64 Instance; // rax
  __int64 v9; // rbx
  unsigned int v10; // eax
  enum AsyncStatus v11; // edx
  HMODULE LibraryW; // rax
  int v13; // eax
  struct IIndexerPlugIn *v14; // r15
  volatile signed __int32 *v15; // rcx
  HANDLE CurrentThread; // rax
  const char *v17; // r9
  int v18; // eax
  CBackOffController *v19; // r13
  unsigned int v20; // eax
  CSyncReadWrite *v21; // r14
  int GatherProject; // ebx
  struct IGatherDataChange **v23; // rdx
  _QWORD *i; // rbx
  __int64 v25; // r8
  __int64 v26; // rcx
  char v27; // al
  bool *v28; // rbx
  CActiveQueue *v29; // rsi
  int v30; // eax
  int NewTransaction; // ebx
  struct CTransaction *v32; // rsi
  void *v33; // rcx
  __int64 v34; // rcx
  volatile signed __int32 *v35; // rdx
  DWORD v36; // ebx
  int v37; // r8d
  volatile signed __int32 *v38; // rcx
  void *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  int v44; // ebx
  CGatheringService *v45; // rcx
  DWORD TickCount; // ebx
  DWORD v47; // r14d
  _DWORD *v48; // rbx
  int v49; // r14d
  _DWORD *v50; // rbx
  int v51; // r14d
  _DWORD *v52; // rbx
  int v53; // ebx
  _BYTE *v54; // r14
  int v55; // ebx
  int v56; // esi
  _BYTE *v57; // rbx
  _DWORD *v58; // rbx
  __int64 v59; // rdx
  const char *v60; // rdx
  const char *v61; // rax
  __int64 v62; // rdx
  char *v63; // rbx
  int v64; // eax
  wil::details::in1diag3 *v65; // rcx
  __int64 v66; // rdx
  _BYTE *v67; // rbx
  _DWORD *v68; // rbx
  _DWORD *v69; // r14
  _DWORD *v70; // rbx
  void *v71; // rax
  const wchar_t *v72; // rdx
  wchar_t *Buffer; // rax
  const wchar_t *v74; // rdx
  wchar_t v75; // ax
  __int64 v76; // rcx
  unsigned int *Extension; // rax
  __int64 v78; // rcx
  unsigned int v79; // r14d
  _DWORD *v80; // rbx
  char *v81; // rbx
  __int64 v82; // rbx
  __int64 v83; // rdx
  __int64 v84; // r14
  unsigned __int16 v85; // r13
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // rcx
  int v89; // esi
  _DWORD *v90; // rbx
  int v91; // edx
  __int64 v92; // rcx
  _BYTE *v93; // rbx
  const char *v94; // r9
  const char *v95; // r9
  int v96; // eax
  struct IIndexerPlugIn *v97; // rbx
  __int64 (__fastcall *v98)(struct IIndexerPlugIn *, GUID *, struct IInvertedProject **); // r14
  int v99; // eax
  void *v100; // rbx
  void *v101; // r14
  int GatherFilterSink; // eax
  int v103; // r13d
  wil::details::in1diag3 *v104; // rcx
  __int64 v105; // rdx
  int v106; // eax
  _DWORD *v107; // rbx
  unsigned __int64 v108; // r9
  struct CGthrPrj *v109; // rbx
  int v110; // eax
  unsigned int v111; // ecx
  CBackOffController *v112; // rbx
  unsigned int v113; // ecx
  __int64 v114; // rcx
  __int64 v115; // rbx
  struct CGatherApplication *Application; // rax
  __int64 DisplayName; // rax
  __int64 v118; // rcx
  _DWORD *v119; // rbx
  CBackOffController *v120; // rsi
  unsigned int v121; // ebx
  unsigned int v122; // eax
  CGatheringService *v123; // rcx
  int v124; // ecx
  unsigned int v125; // esi
  _DWORD *v126; // rbx
  int v127; // esi
  _DWORD *v128; // rbx
  char *v129; // rbx
  unsigned int v130; // eax
  CRegistry *v131; // rax
  volatile signed __int32 *v132; // rcx
  _DWORD *v133; // rcx
  unsigned int v134; // eax
  int *v135; // [rsp+20h] [rbp-4008h]
  int v136; // [rsp+20h] [rbp-4008h]
  __int64 v137; // [rsp+50h] [rbp-3FD8h] BYREF
  CThread *v138; // [rsp+58h] [rbp-3FD0h]
  __int128 v139; // [rsp+60h] [rbp-3FC8h] BYREF
  __int64 v140; // [rsp+70h] [rbp-3FB8h]
  struct CTransaction *v141; // [rsp+78h] [rbp-3FB0h] BYREF
  struct CGthrPrj *v142; // [rsp+80h] [rbp-3FA8h] BYREF
  unsigned int v143; // [rsp+88h] [rbp-3FA0h] BYREF
  int v144; // [rsp+8Ch] [rbp-3F9Ch]
  struct IGatherDataChange *v145; // [rsp+90h] [rbp-3F98h] BYREF
  CActiveQueue *v146; // [rsp+98h] [rbp-3F90h]
  unsigned int v147; // [rsp+A0h] [rbp-3F88h]
  __int64 v148; // [rsp+A8h] [rbp-3F80h] BYREF
  struct IIndexerPlugIn *v149; // [rsp+B0h] [rbp-3F78h] BYREF
  int v150; // [rsp+B8h] [rbp-3F70h]
  int v151; // [rsp+BCh] [rbp-3F6Ch] BYREF
  HRESULT v152; // [rsp+C0h] [rbp-3F68h]
  int v153; // [rsp+C4h] [rbp-3F64h] BYREF
  CBackOffController *v154; // [rsp+C8h] [rbp-3F60h]
  CWordBreakerHistory *v155; // [rsp+D0h] [rbp-3F58h] BYREF
  char *v156; // [rsp+D8h] [rbp-3F50h] BYREF
  int v157; // [rsp+E0h] [rbp-3F48h]
  __int64 v158; // [rsp+E8h] [rbp-3F40h] BYREF
  std::_Ref_count_base *v159; // [rsp+F0h] [rbp-3F38h]
  struct IInvertedProject *v160; // [rsp+F8h] [rbp-3F30h] BYREF
  void **v161; // [rsp+100h] [rbp-3F28h] BYREF
  _QWORD v162[3]; // [rsp+108h] [rbp-3F20h] BYREF
  int v163; // [rsp+120h] [rbp-3F08h]
  __int64 v164; // [rsp+128h] [rbp-3F00h]
  char v165; // [rsp+130h] [rbp-3EF8h]
  LPVOID pv; // [rsp+138h] [rbp-3EF0h] BYREF
  struct IIndexerPlugIn *v167; // [rsp+140h] [rbp-3EE8h] BYREF
  _DWORD *v168; // [rsp+148h] [rbp-3EE0h] BYREF
  std::_Ref_count_base *v169; // [rsp+150h] [rbp-3ED8h]
  char v170[8]; // [rsp+158h] [rbp-3ED0h] BYREF
  wchar_t *v171; // [rsp+160h] [rbp-3EC8h] BYREF
  wchar_t *v172[3]; // [rsp+168h] [rbp-3EC0h] BYREF
  _OWORD v173[2]; // [rsp+180h] [rbp-3EA8h] BYREF
  _DWORD v174[2]; // [rsp+1A0h] [rbp-3E88h] BYREF
  __int64 v175; // [rsp+1A8h] [rbp-3E80h]
  __int64 v176; // [rsp+1B0h] [rbp-3E78h] BYREF
  int v177; // [rsp+1B8h] [rbp-3E70h]
  char v178; // [rsp+1BCh] [rbp-3E6Ch]
  HMODULE v179; // [rsp+1C0h] [rbp-3E68h] BYREF
  char v180[8]; // [rsp+1C8h] [rbp-3E60h] BYREF
  __int64 v181; // [rsp+1D0h] [rbp-3E58h]
  int v182; // [rsp+1D8h] [rbp-3E50h]
  _QWORD v183[4]; // [rsp+1E0h] [rbp-3E48h] BYREF
  int v184[2]; // [rsp+200h] [rbp-3E28h] BYREF
  int v185; // [rsp+238h] [rbp-3DF0h]
  _QWORD v186[12]; // [rsp+250h] [rbp-3DD8h] BYREF
  int v187; // [rsp+2B0h] [rbp-3D78h]
  __int64 v188; // [rsp+2B8h] [rbp-3D70h]
  int v189; // [rsp+2ECh] [rbp-3D3Ch]
  int v190; // [rsp+2F0h] [rbp-3D38h]
  int v191; // [rsp+2F4h] [rbp-3D34h]
  char v192[16]; // [rsp+320h] [rbp-3D08h] BYREF
  char v193[16]; // [rsp+330h] [rbp-3CF8h] BYREF
  _BYTE v194[32]; // [rsp+340h] [rbp-3CE8h] BYREF
  int v195; // [rsp+360h] [rbp-3CC8h]
  volatile signed __int32 *v196; // [rsp+378h] [rbp-3CB0h]
  char v197[16]; // [rsp+380h] [rbp-3CA8h] BYREF
  struct CGthrPrj *v198[2]; // [rsp+390h] [rbp-3C98h] BYREF
  wchar_t *v199; // [rsp+3B0h] [rbp-3C78h] BYREF
  __int128 v200; // [rsp+3B8h] [rbp-3C70h]
  unsigned __int64 v201; // [rsp+3C8h] [rbp-3C60h]
  _DWORD v202[4]; // [rsp+3D0h] [rbp-3C58h] BYREF
  _DWORD v203[2]; // [rsp+3E0h] [rbp-3C48h] BYREF
  __int64 v204; // [rsp+3E8h] [rbp-3C40h]
  _DWORD v205[2]; // [rsp+3F0h] [rbp-3C38h] BYREF
  __int64 v206; // [rsp+3F8h] [rbp-3C30h]
  _BYTE v207[32]; // [rsp+400h] [rbp-3C28h] BYREF
  CActiveQueue *v208; // [rsp+420h] [rbp-3C08h]
  __int128 v209[2]; // [rsp+430h] [rbp-3BF8h] BYREF
  wchar_t *v210[4]; // [rsp+450h] [rbp-3BD8h] BYREF
  unsigned int v211; // [rsp+470h] [rbp-3BB8h]
  _BYTE v212[40]; // [rsp+478h] [rbp-3BB0h] BYREF
  _BYTE v213[96]; // [rsp+4A0h] [rbp-3B88h] BYREF
  char v214[8]; // [rsp+500h] [rbp-3B28h] BYREF
  __int64 v215; // [rsp+508h] [rbp-3B20h]
  int v216; // [rsp+514h] [rbp-3B14h]
  _BYTE v217[220]; // [rsp+6A0h] [rbp-3988h] BYREF
  int v218; // [rsp+77Ch] [rbp-38ACh]
  int IsUserActiveAfterIndexing; // [rsp+784h] [rbp-38A4h]
  struct CTransaction *v220; // [rsp+7C8h] [rbp-3860h]
  _BYTE v221[13336]; // [rsp+7D0h] [rbp-3858h] BYREF
  CGthrPrj *v222; // [rsp+3BE8h] [rbp-440h]
  int v223; // [rsp+3C24h] [rbp-404h]
  int v224; // [rsp+3C28h] [rbp-400h]
  int v225; // [rsp+3FB0h] [rbp-78h]
  int v226; // [rsp+3FD0h] [rbp-58h] BYREF
  void *v227; // [rsp+3FD8h] [rbp-50h]
  char v228; // [rsp+3FE0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4028h] [rbp+0h]

  v1 = Parameter;
  v138 = Parameter;
  v172[2] = (wchar_t *)Parameter;
  v150 = 0;
  v152 = CoInitializeEx(0, 0);
  if ( (byte_1802DA182 & 8) != 0 )
  {
    v135 = &v226;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      MSSearchTraceId_Service_Startup_Duration_Stop,
      v2,
      1);
  }
  SetCurrentThreadName(L"Robot Thread");
  v3 = (CActiveQueue *)*((_QWORD *)g_pGatheringService + 489);
  v146 = v3;
  inited = CGatheringService::WaitForInitDone(g_pGatheringService);
  v5 = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1748,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
      (const char *)(unsigned int)inited,
      (int)v135);
    if ( v152 >= 0 )
      CoUninitialize();
    return v5;
  }
  v7 = 0;
  v137 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
  {
    Instance = winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(&v148);
    winrt::Windows::Foundation::IUnknown::operator=(&v137, Instance);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v148);
    v9 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchConfigManager>::ProcessResultsForModelsAvailabilityAsync(
           &v137,
           &v148);
    v10 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncAction>::Status(v9);
    if ( !v10 )
      v10 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncAction>(v9);
    winrt::impl::check_status_canceled((winrt::impl *)v10, v11);
    winrt::impl::consume_Windows_System_Threading_IThreadPoolTimer<winrt::Windows::System::Threading::IThreadPoolTimer>::Cancel(v9);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v148);
    v7 = v137;
  }
  LibraryW = LoadLibraryW(L"tquery.dll");
  v179 = LibraryW;
  if ( LibraryW )
    g_PropagateEventSinks = (int (__high * near *)(enum PROPAGATE_EVENTTYPE, unsigned int, const wchar_t *))GetProcAddress(LibraryW, "ExternPropagateEventToOpenQueries");
  v180[0] = 0;
  v181 = 0;
  v182 = 0;
  v176 = 0;
  v177 = 0;
  v178 = 0;
  v155 = 0;
  v149 = 0;
  v13 = ATL::CComObject<CWordBreakerHistory>::CreateInstance(&v149);
  if ( v13 < 0 )
  {
    v134 = wil::verify_hresult<long>((unsigned int)v13);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x176A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
      (const char *)v134,
      (int)v135);
  }
  v172[1] = (wchar_t *)v3;
  v147 = 0;
  v14 = v149;
  v155 = v149;
  (*(void (__fastcall **)(struct IIndexerPlugIn *))(*(_QWORD *)v149 + 8LL))(v149);
  CWordBreakerSelector::CWordBreakerSelector(
    (CWordBreakerSelector *)v184,
    (struct CLanguageAutoDetection *)v180,
    (struct CScriptAutoDetection *)&v176,
    v14);
  v15 = (volatile signed __int32 *)*((_QWORD *)g_pGatheringService + 928);
  if ( v15 )
    _InterlockedAdd(v15, 1u);
  v202[0] = 1;
  v202[1] = 1;
  v202[2] = 1;
  CurrentThread = GetCurrentThread();
  if ( !(unsigned int)SetThreadInformation(CurrentThread, 3, v202) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x1778,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
      v17);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59306570>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59306570>::GetImpl'::`2'::impl) )
  {
    v18 = CRobotThread::ExecuteBulkFilenameIndexingForNewCatalog();
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x177D,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        (const char *)(unsigned int)v18,
        (int)v135);
  }
  while ( !*((_DWORD *)v1 + 10) )
  {
    v19 = (CBackOffController *)*((_QWORD *)g_pGatheringService + 500);
    v154 = v19;
    v141 = v19;
    if ( v19 && v147 )
    {
      CBackOffController::RecordOtherSleepTime(v19, v147);
      v147 = 0;
    }
    GetContainerStatusManager(&v158);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v158 + 40LL))(v158);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55745486>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55745486>::GetImpl'::`2'::impl) )
    {
      LODWORD(v199) = 0;
      v200 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 152LL))(v7);
      winrt::check_hresult(v170, v20, &v199);
    }
    v21 = (CRegistry *)((char *)g_pGatheringService + 7112);
    v156 = (char *)g_pGatheringService + 7112;
    v157 = 1;
    CSyncReadWrite::GetReadAccess((CRegistry *)((char *)g_pGatheringService + 7112));
    GatherProject = 0;
    v139 = 0;
    v140 = 0;
    memset(v173, 0, sizeof(v173));
    while ( !GatherProject )
    {
      v198[0] = 0;
      GatherProject = CEnumAllGatherCatalogs::NextGatherProject((CEnumAllGatherCatalogs *)v173, v198);
      LODWORD(v142) = GatherProject;
      if ( !GatherProject )
      {
        v145 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
        CGthrPrj::GetGatherDataChange(v198[0], &v145);
        if ( v145 )
        {
          v23 = (struct IGatherDataChange **)*((_QWORD *)&v139 + 1);
          if ( *((_QWORD *)&v139 + 1) == v140 )
          {
            try
            {
              std::vector<Microsoft::WRL::ComPtr<IGatherDataChange>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IGatherDataChange>>(
                &v139,
                *((_QWORD *)&v139 + 1),
                &v145);
            }
            catch ( ... )
            {
              indexer::result::details::result_from_caught_exception<1>(
                retaddr,
                6066,
                "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
            }
          }
          else
          {
            **((_QWORD **)&v139 + 1) = 0;
            if ( v23 != &v145 )
            {
              *v23 = v145;
              v145 = 0;
            }
            *((_QWORD *)&v139 + 1) += 8LL;
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
      }
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(v198);
    }
    CEnumAllGatherCatalogs::Reset((CEnumAllGatherCatalogs *)v173);
    for ( i = (_QWORD *)v139; i != *((_QWORD **)&v139 + 1); ++i )
    {
      if ( (*(int (__fastcall **)(_QWORD))(*(_QWORD *)*i + 40LL))(*i) >= 0 )
        goto LABEL_41;
    }
    v142 = v19;
    if ( (_QWORD)v139 != *((_QWORD *)&v139 + 1) )
    {
      ((void (*)(void))std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IGatherDataChange>>>)();
      *((_QWORD *)&v139 + 1) = v139;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl)
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    {
      v26 = v137 - 16;
      if ( !v137 )
        v26 = 0;
      v27 = *(_BYTE *)(v26 + 92);
      *(_BYTE *)(v26 + 92) = 0;
      v28 = (bool *)v138;
      if ( v27 )
        *((_BYTE *)v138 + 68) = 1;
      v29 = v146;
      if ( v28[68] )
      {
        v30 = CActiveQueue::PrioritizePostponedItems(v146, v28 + 68);
        if ( v30 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17D5,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
            (const char *)(unsigned int)v30,
            (int)v135);
      }
    }
    else
    {
      v29 = v146;
      v28 = (bool *)v138;
    }
    if ( (Microsoft_Windows_Search_CoreEnableBits & 0x40) != 0 )
    {
      v135 = (int *)&v228;
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Search_Core_Context,
        MSSearchTraceId_RobotThread_BeforeGetNewTransaction,
        v25,
        1);
    }
    v141 = 0;
    NewTransaction = CActiveQueue::GetNewTransaction(v29, (struct CRobotThread *)v28, &v141);
    CBackOffController::IndexingStart(v19);
    InitOnceExecuteOnce(
      &g_initOnceOnPerUserCatalogCheck,
      _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
      0,
      0);
    v32 = v141;
    if ( g_isPerUserCatalogEnabled && v141 )
      v33 = (void *)*((_QWORD *)CGthrPrj::GetApplication(*((CGthrPrj **)v141 + 162)) + 35);
    else
      v33 = 0;
    PerUserCatalogNameForCorruption::SetCatalog(v33);
    if ( !NewTransaction )
    {
      v161 = &tip2::test_watcher<tip2::details::merged_data<_tip_LexicalDbEncryptionTest,_tip_LexicalDbEncryptionTest>>::`vftable';
      v162[0] = 0;
      v162[1] = &v161;
      v162[2] = 0;
      v163 = 0;
      v164 = 0;
      v165 = 0;
      tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>,>(&pv);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
      {
        v198[0] = 0;
        tip2::tip_test<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::start_and_watch_errors(
          v198,
          v194);
        wil::com_ptr_t<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>,wil::err_returncode_policy>(v198);
        v39 = pv;
        pv = (LPVOID)v196;
        if ( v196 )
          _InterlockedAdd(v196 + 80, 1u);
        if ( v39 )
          tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>::Release(v39);
        wil::details::ThreadFailureCallbackHolder::SetWatching(
          (wil::details::ThreadFailureCallbackHolder *)v162,
          v195 != 0);
        tip2::test_watcher<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_watcher<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v194);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57813162>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57813162>::GetImpl'::`2'::impl) )
      {
        v40 = *((_QWORD *)CGthrPrj::GetApplication(*((CGthrPrj **)v32 + 162)) + 35);
        v41 = -1;
        do
          ++v41;
        while ( *(_WORD *)(v40 + 2 * v41) );
        v183[0] = v40;
        v183[1] = v41;
        to_utf8(v212, v183);
        v209[0] = *(_OWORD *)std::string::operator std::string_view(v212, v197);
        *(_OWORD *)v198 = *(_OWORD *)std::string::operator std::string_view(v212, v192);
        FirstUpgradeEncryptionUtil::BlockThreadWorkIfNonceRunningOnDB((__int128 *)v198, v209);
        std::string::_Tidy_deallocate(v212);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
      {
        v44 = *((_DWORD *)v32 + 464);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60604361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60604361>::GetImpl'::`2'::impl) )
        {
          if ( !CGatheringService::IsMultipassAllowed(v45) )
            goto LABEL_90;
        }
        else if ( !*((_DWORD *)g_pGatheringService + 896) )
        {
          goto LABEL_90;
        }
        *((_DWORD *)v138 + 16) = v44;
      }
LABEL_90:
      std::wstring::wstring(v207, (char *)v32 + 1808, v42, v43);
      v208 = v146;
      if ( v19 )
      {
        TickCount = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
          TickCount = GetTickCount();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56621484>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56621484>::GetImpl'::`2'::impl) )
          CBackOffController::PreTransactionResourceCheckSleep(v19);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdaptiveIndexing_Backoff>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdaptiveIndexing_Backoff>::GetImpl'::`2'::impl) )
          CBackOffController::SleepIfBackOff(v19, -1, *((unsigned int *)v32 + 464));
        else
          (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v19 + 1) + 40LL))((_QWORD *)v19 + 1);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
        {
          v47 = GetTickCount() - TickCount;
          v48 = pv;
          v198[0] = (struct CGthrPrj *)pv;
          if ( pv )
            _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
          tip2::details::shared_data<0,0,0>::begin_update(v48 + 2);
          v48[74] = v47;
          tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
      {
        v49 = *((_DWORD *)v32 + 314);
        v50 = pv;
        v198[0] = (struct CGthrPrj *)pv;
        if ( pv )
          _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
        tip2::details::shared_data<0,0,0>::begin_update(v50 + 2);
        v50[76] = v49;
        tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
        v51 = *((_DWORD *)v32 + 304);
        v52 = pv;
        v198[0] = (struct CGthrPrj *)pv;
        if ( pv )
          _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
        tip2::details::shared_data<0,0,0>::begin_update(v52 + 2);
        v52[77] = v51;
        tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
        {
          v53 = *((_DWORD *)v32 + 464);
          v54 = pv;
          v198[0] = (struct CGthrPrj *)pv;
          if ( pv )
            _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
          tip2::details::shared_data<0,0,0>::begin_update(v54 + 8);
          v54[312] = v53;
          tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
        }
      }
      TraceIndexTransaction(&MSSearchTraceId_RobotThread_ProcessNewTransaction, v32, 0, 0, 0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58816171>::GetImpl'::`2'::impl) )
      {
        v55 = *(_DWORD *)(*((_QWORD *)v32 + 224) + 148LL) & 8;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
        {
          if ( !v55 && *((_DWORD *)v32 + 464) == 8 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
            {
              v56 = CRobotThread::RunImageCategoryGenerationTransaction(v32);
              v57 = pv;
              v198[0] = (struct CGthrPrj *)pv;
              if ( pv )
                _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
              tip2::details::shared_data<0,0,0>::begin_update(v57 + 8);
              v57[300] = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
              v58 = pv;
              v198[0] = (struct CGthrPrj *)pv;
              if ( pv )
                _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
              tip2::details::shared_data<0,0,0>::begin_update(v58 + 2);
              v58[68] = v56;
              tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
              if ( v56 < 0 )
              {
                v59 = 6246;
                goto LABEL_122;
              }
              goto LABEL_123;
            }
            v64 = CRobotThread::RunImageCategoryGenerationTransaction(v32);
            v65 = retaddr;
            if ( v64 >= 0 )
              goto LABEL_129;
            v66 = 6256;
            goto LABEL_128;
          }
        }
        else if ( !v55 && (*(_DWORD *)(*((_QWORD *)v32 + 224) + 208LL) & 0x8000) != 0 )
        {
          if ( !(unsigned int)GetIsSemanticIndexingAllowed() )
          {
            SetImageCategoryGenerationAttempted(0);
            goto LABEL_129;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
          {
            v56 = CRobotThread::RunImageCategoryGenerationTransaction(v32);
            v67 = pv;
            v198[0] = (struct CGthrPrj *)pv;
            if ( pv )
              _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
            tip2::details::shared_data<0,0,0>::begin_update(v67 + 8);
            v67[300] = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
            v68 = pv;
            v198[0] = (struct CGthrPrj *)pv;
            if ( pv )
              _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
            tip2::details::shared_data<0,0,0>::begin_update(v68 + 2);
            v68[68] = v56;
            tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
            if ( v56 < 0 )
            {
              v59 = 6282;
LABEL_122:
              wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)v59,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                (const char *)(unsigned int)v56,
                (int)v135);
              v61 = tip2::details::reason_string(
                      (tip2::details *)"RobotThreadTransactionPerfTest::reason::ImageCategoryGenerationFailed",
                      v60);
              LOBYTE(v62) = 3;
              tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8, v62, 2, v61);
LABEL_129:
              CCatalogOwnerCleanup::~CCatalogOwnerCleanup((CCatalogOwnerCleanup *)v207);
              tip2::test_watcher<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_watcher<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(&v161);
              PerUserCatalogNameForCorruption::SetCatalog(0);
              TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v141);
LABEL_41:
              CEnumAllGatherCatalogs::~CEnumAllGatherCatalogs((CEnumAllGatherCatalogs *)v173);
              if ( (_QWORD)v139 )
              {
                std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IGatherDataChange>>>(
                  v139,
                  *((_QWORD *)&v139 + 1));
                std::_Deallocate<16>(v139, (v140 - v139) & 0xFFFFFFFFFFFFFFF8uLL);
                v139 = 0;
                v140 = 0;
              }
              CNonExclusiveReleaseable::~CNonExclusiveReleaseable((CNonExclusiveReleaseable *)&v156);
              v1 = v138;
              goto LABEL_44;
            }
LABEL_123:
            v63 = (char *)pv;
            v198[0] = (struct CGthrPrj *)pv;
            if ( pv )
              _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
            tip2::details::shared_data<0,0,0>::begin_update(v63 + 8);
            tip2::details::shared_data<0,0,0>::complete_helper(v63 + 8, 2048, 10);
            tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
            goto LABEL_129;
          }
          v64 = CRobotThread::RunImageCategoryGenerationTransaction(v32);
          v65 = retaddr;
          if ( v64 >= 0 )
            goto LABEL_129;
          v66 = 6292;
LABEL_128:
          wil::details::in1diag3::_Log_Hr(
            v65,
            (void *)v66,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
            (const char *)(unsigned int)v64,
            (int)v135);
          goto LABEL_129;
        }
      }
      v69 = operator new(0x88u);
      v183[2] = v69;
      *(_OWORD *)v69 = 0;
      v69[2] = 1;
      v69[3] = 1;
      *(_QWORD *)v69 = &std::_Ref_count_obj2<ScreenOnIndexingFileEvent>::`vftable';
      ScreenOnIndexingFileEvent::ScreenOnIndexingFileEvent((ScreenOnIndexingFileEvent *)(v69 + 4));
      v168 = v69 + 4;
      v169 = (std::_Ref_count_base *)v69;
      v150 |= 3u;
      CFilterDriver::CFilterDriver(v217, v32, &v168);
      v70 = v168;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v168 + 8LL))(v168);
      v226 = 2;
      std::wstring::wstring(&v199);
      try
      {
        GetProtocolHelper(*((_QWORD *)v220 + 13), &v199);
        v71 = &v199;
        if ( v201 > 7 )
          v71 = v199;
        v227 = v71;
        (*(void (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v70 + 24LL))(v70, &v226);
        v72 = (const wchar_t *)&v199;
        if ( v201 > 7 )
          v72 = v199;
        SearchIndexerTelemetryAggregatedHigh::IndexingItem::SetProtocol(
          (SearchIndexerTelemetryAggregatedHigh::IndexingItem *)v217,
          v72);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55683212>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55683212>::GetImpl'::`2'::impl) )
        {
          try
          {
            TLMString<192,64,32767>::TLMString<192,64,32767>(v214, (char *)v220 + 96);
            Buffer = CLMString::GetBuffer((CLMString *)v214, 0);
            std::wstring::wstring(v198, Buffer);
            std::wstring::wstring(v209, L"file");
            GetExtensionAndItemType(v210, v198, v209, &v199);
            SearchIndexerTelemetryAggregatedHigh::IndexingItem::SetItemType(v217, v211);
            if ( v210[2] )
            {
              v74 = (const wchar_t *)v210;
              if ( v210[3] > (wchar_t *)7 )
                v74 = v210[0];
              SearchIndexerTelemetryAggregatedHigh::IndexingItem::SetExtension(
                (SearchIndexerTelemetryAggregatedHigh::IndexingItem *)v217,
                v74);
            }
            ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v210);
            ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v209);
            ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v198);
            TLMString<192,64,32767>::~TLMString<192,64,32767>(v214);
          }
          catch ( ... )
          {
            indexer::result::details::result_from_caught_exception<1>(
              retaddr,
              6339,
              "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
          }
LABEL_163:
          v1 = v138;
          ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)&v199);
          goto LABEL_323;
        }
        TLMString<192,64,32767>::TLMString<192,64,32767>(v214, (char *)v220 + 96);
        if ( !(*(unsigned int (__fastcall **)(struct CTransaction *))(*(_QWORD *)v220 + 664LL))(v220) )
        {
          v75 = CLMString::Last((CLMString *)v214);
          if ( !(unsigned int)IsSlash(v75) )
          {
            v76 = (unsigned int)(v216 - 1);
            if ( v216 - 1 < 0 )
            {
LABEL_160:
              if ( (_DWORD)v76 != -1 )
                goto LABEL_161;
            }
            else
            {
              while ( *(_WORD *)(v215 + 2 * v76) != 46 )
              {
                v76 = (unsigned int)(v76 - 1);
                if ( (int)v76 < 0 )
                  goto LABEL_160;
              }
LABEL_161:
              Extension = (unsigned int *)CURL::GetExtension((char *)v220 + 72, v193);
              SearchIndexerTelemetryAggregatedHigh::IndexingItem::SetExtension(
                (SearchIndexerTelemetryAggregatedHigh::IndexingItem *)v217,
                (const wchar_t *)(*(_QWORD *)(*((_QWORD *)Extension + 1) + 8LL) + 2LL * *Extension));
            }
          }
        }
        TLMString<192,64,32767>::~TLMString<192,64,32767>(v214);
        goto LABEL_163;
      }
      catch ( ... )
      {
        indexer::result::details::result_from_caught_exception<1>(
          retaddr,
          6355,
          "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
      }
LABEL_323:
      v79 = CFilterDriver::Init((CFilterDriver *)v217);
      if ( v79 )
      {
        if ( (byte_1802DA182 & 2) != 0 )
          McTemplateU0x_EventWriteTransfer(v78, MSSearchTraceId_RobotThread_FilterDriver_Init_Failed, v32);
        LogTransaction(v79, &v141, v217);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
          goto LABEL_174;
        v80 = pv;
        v198[0] = (struct CGthrPrj *)pv;
        if ( pv )
          _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
        tip2::details::shared_data<0,0,0>::begin_update(v80 + 2);
        v80[70] = v79;
LABEL_171:
        tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
        v81 = (char *)pv;
        v198[0] = (struct CGthrPrj *)pv;
        if ( pv )
          _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
        tip2::details::shared_data<0,0,0>::begin_update(v81 + 8);
        tip2::details::shared_data<0,0,0>::complete_helper(v81 + 8, 2048, 10);
        tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
LABEL_174:
        CFilterDriver::~CFilterDriver((CFilterDriver *)v217);
        if ( v169 )
          std::_Ref_count_base::_Decref(v169);
        CCatalogOwnerCleanup::~CCatalogOwnerCleanup((CCatalogOwnerCleanup *)v207);
        tip2::test_watcher<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_watcher<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(&v161);
        goto LABEL_71;
      }
      if ( !(unsigned int)CURL::IsLocalPath((struct CTransaction *)((char *)v32 + 72))
        || (CURL::GetPath((char *)v32 + 72, v174), v174[1] < 2u)
        || (v82 = v175, v83 = *(_QWORD *)(v175 + 8), *(_WORD *)(v83 + 2LL * (unsigned int)(v174[0] + 1)) != 58) )
      {
        do
        {
LABEL_189:
          CFilterDriver::BindToFilter((CFilterDriver *)v217, (const wchar_t **)v220);
          CFilterDriver::GetStandardProperties((CFilterDriver *)v217);
        }
        while ( v223 == 265592 );
        if ( v223 >= 0 )
        {
          if ( v223 != 266755
            || *((_DWORD *)v32 + 304) == 3
            || CFilterDriver::IsTransactionUpdatingSupplementalProperties((CFilterDriver *)v217) )
          {
            CPluginCollectionSink::CPluginCollectionSink(
              (CPluginCollectionSink *)v186,
              (struct CFilterDriver *)v217,
              (struct CLanguageAutoDetection *)v180,
              (struct CScriptAutoDetection *)&v176,
              (struct CWordBreakerSelector *)v184);
            if ( !*((_BYTE *)v14 + 24) )
            {
              InitOnceExecuteOnce(
                &g_initOnceOnPerUserCatalogCheck,
                _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
                0,
                0);
              if ( g_isPerUserCatalogEnabled )
              {
                wil::make_bstr(&v171, L"Windows");
                if ( !v171 )
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0x1940,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                    v94);
                wil::make_bstr(v172, L"SystemIndex");
                if ( !v172[0] )
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0x1942,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                    v95);
                v167 = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167);
                v96 = WDSSUtilIndexerPlugInInterface(v171, v172[0], &v167);
                if ( v96 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1944,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                    (const char *)(unsigned int)v96,
                    v136);
                v160 = 0;
                v97 = v167;
                v98 = **(__int64 (__fastcall ***)(struct IIndexerPlugIn *, GUID *, struct IInvertedProject **))v167;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
                v99 = v98(v97, &GUID_487988ac_86f6_46c1_af89_9a407f39146e, &v160);
                if ( v99 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1946,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                    (const char *)(unsigned int)v99,
                    v136);
                CWordBreakerHistory::Load(v14, v160);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167);
                wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v172);
                wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v171);
              }
              else
              {
                v142 = 0;
                CFilterDriver::GetProject((CFilterDriver *)v217, &v142);
                v149 = 0;
                if ( (int)GetIndexerPlugin(v142, &v149) >= 0 )
                {
                  v198[0] = 0;
                  if ( (**(int (__fastcall ***)(struct IIndexerPlugIn *, GUID *, struct CGthrPrj **))v149)(
                         v149,
                         &GUID_487988ac_86f6_46c1_af89_9a407f39146e,
                         v198) >= 0 )
                    CWordBreakerHistory::Load(v14, v198[0]);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v198);
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v149);
                TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v142);
              }
            }
            v153 = 0;
            if ( (*(int (__fastcall **)(struct CTransaction *, int *))(*(_QWORD *)v32 + 160LL))(v32, &v153) >= 0 )
            {
              v185 = v153;
              CWordBreakerHistory::GetCurrentAllowList(*(CWordBreakerHistory **)v184);
            }
            v100 = (void *)*((_QWORD *)g_pGatheringService + 518);
            v101 = 0;
            if ( WaitForSingleObject(v100, 0xFFFFFFFF) != 258 )
              v101 = v100;
            *(_QWORD *)&v209[0] = v101;
            GatherFilterSink = CPluginCollectionSink::BuildSinkLists((CPluginCollectionSink *)v186);
            v103 = GatherFilterSink;
            v104 = retaddr;
            if ( GatherFilterSink < 0 )
            {
              v105 = 6500;
              goto LABEL_264;
            }
            GatherFilterSink = CPluginCollectionSink::CreateGatherFilterSink((CPluginCollectionSink *)v186, v32);
            v103 = GatherFilterSink;
            v104 = retaddr;
            if ( GatherFilterSink < 0 )
            {
              v105 = 6505;
              goto LABEL_264;
            }
            v106 = CPluginCollectionSink::OnActiveDataChange((CPluginCollectionSink *)v186);
            v103 = v106;
            if ( v106 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x196F,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                (const char *)(unsigned int)v106,
                v136);
            CPluginCollectionSink::InitActiveFilterSinks((CPluginCollectionSink *)v186);
            if ( v103 >= 0 )
            {
              v103 = CPluginCollectionSink::PushProperties((CPluginCollectionSink *)v186, 1, 0);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
              {
                v107 = pv;
                v198[0] = (struct CGthrPrj *)pv;
                if ( pv )
                  _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
                tip2::details::shared_data<0,0,0>::begin_update(v107 + 2);
                v107[72] = v103;
                tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
              }
              v104 = retaddr;
              if ( v103 < 0 )
              {
                v108 = (unsigned int)v103;
                v105 = 6523;
                goto LABEL_265;
              }
              if ( v188 && *(_BYTE *)(v188 + 48) )
              {
                v103 = -2147217989;
                v224 = -2147217989;
              }
              if ( v103 >= 0 )
              {
                LODWORD(v142) = 0;
                v199 = (wchar_t *)v221;
                *(_QWORD *)&v200 = v221;
                *((_QWORD *)&v200 + 1) = 0;
                if ( (unsigned int)CTComObjSListIter<TLMString<32,32,1024>,CUsnMonNotificationSource,TLMString<32,32,1024>>::operator++(&v199) )
                {
                  while ( 1 )
                  {
                    v198[0] = 0;
                    TNoUnkSListIter<CProtocol>::GetCurrentValue(&v199, v198);
                    v109 = v198[0];
                    if ( !v198[0] )
                      break;
                    v223 = 0;
                    v148 = 0;
                    (*(void (__fastcall **)(struct CGthrPrj *, __int64 *))(*(_QWORD *)v198[0] + 256LL))(v198[0], &v148);
                    v151 = 0;
                    v110 = CFilterDriver::LookupGathererRules((CFilterDriver *)v217, v109, 0, &v151, 0, 1, 1, 0);
                    v111 = v110;
                    v144 = v110;
                    if ( v151 )
                    {
                      v111 = -2147218169;
                      v144 = -2147218169;
                    }
                    else if ( v110 >= 0 )
                    {
                      if ( *((_DWORD *)v109 + 366) )
                      {
                        v190 = 1;
                        *(_DWORD *)(v188 + 39552) = 1;
                      }
                      if ( *((_DWORD *)v109 + 367) )
                      {
                        v225 = 1;
                        v191 = 1;
                      }
                      *((_QWORD *)v32 + 127) = (char *)v109 + 72;
                      *((_DWORD *)v32 + 370) = *((_DWORD *)v109 + 370);
                      CFilterDriver::BindToFilter((CFilterDriver *)v217, (const wchar_t **)v109);
                      v111 = v223;
                      v144 = v223;
                      if ( v223 >= 0 )
                      {
                        v189 = 1;
                        v111 = CPluginCollectionSink::PushProperties((CPluginCollectionSink *)v186, 0, 0);
                        v144 = v111;
                      }
                    }
                    *((_QWORD *)v32 + 127) = (char *)v32 + 72;
                    (*(void (__fastcall **)(struct CGthrPrj *, _QWORD))(*(_QWORD *)v109 + 88LL))(v109, v111);
                    CGthrPrj::ReportProjectLogError(v222, v109);
                    if ( !(_DWORD)v142 && (v144 < 0 || v144 == 265520) )
                      LODWORD(v142) = v144;
                    v190 = 0;
                    *(_DWORD *)(v188 + 39552) = 0;
                    v191 = 0;
                    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(v198);
                    if ( !(unsigned int)CTComObjSListIter<TLMString<32,32,1024>,CUsnMonNotificationSource,TLMString<32,32,1024>>::operator++(&v199) )
                      goto LABEL_257;
                  }
                  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(v198);
LABEL_257:
                  if ( (int)v142 < 0 || (_DWORD)v142 == 265520 )
                    v223 = 265582;
                }
                CFilterDriver::IgnoreProperties((CFilterDriver *)v217);
                if ( CFilterDriver::IsTransactionFromStoreApp((CFilterDriver *)v217)
                  || CFilterDriver::IsTransactionUpdatingSupplementalProperties((CFilterDriver *)v217) )
                {
                  GatherFilterSink = CPluginCollectionSink::PushStoreAppProperties((CPluginCollectionSink *)v186);
                  v103 = GatherFilterSink;
                  v224 = GatherFilterSink;
                  v104 = retaddr;
                  if ( GatherFilterSink < 0 )
                  {
                    v105 = 6626;
LABEL_264:
                    v108 = (unsigned int)GatherFilterSink;
LABEL_265:
                    wil::details::in1diag3::_Log_Hr(
                      v104,
                      (void *)v105,
                      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                      (const char *)v108,
                      v136);
                  }
                }
              }
            }
            *(_DWORD *)(*(_QWORD *)(v186[0] + 296LL) + 1352LL) = v187;
            CPluginCollectionSink::AddCompleted((CPluginCollectionSink *)v186);
            v112 = v154;
            if ( CBackOffController::CanHandleActivityWindows(v154) )
              CWaitThreadList::StopActivity((CBackOffController *)((char *)v112 + 624));
            CWordBreakerSelector::EndFile((CWordBreakerSelector *)v184);
            v113 = 0;
            v143 = 0;
            if ( v32 )
            {
              (*(void (__fastcall **)(struct CTransaction *, unsigned int *))(*(_QWORD *)v32 + 80LL))(v32, &v143);
              v113 = v143;
            }
            if ( (unsigned int)(v103 + 1073473536) <= 1
              || (unsigned int)(v224 + 1073473536) <= 1
              || v113 + 1073473536 <= 1 )
            {
              v198[0] = 0;
              CFilterDriver::GetProject((CFilterDriver *)v217, v198);
              if ( (Microsoft_Windows_Search_CoreEnableBits & 0x40) != 0 )
                McTemplateU0x_EventWriteTransfer(v114, MSSearchTraceId_RobotThread_CatalogResetRequested, v32);
              v115 = *((_QWORD *)v198[0] + 198);
              Application = CGthrPrj::GetApplication(v198[0]);
              DisplayName = CGatherApplication::GetDisplayName(Application, v213);
              RecoveryReportIndexRebuildEx(
                v118,
                *((_QWORD *)g_pGatheringService + 49),
                *(_QWORD *)(DisplayName + 8),
                v115);
              TLMString<32,32,1024>::~TLMString<32,32,1024>(v213);
              TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(v198);
              v113 = v143;
            }
            v205[1] = 0;
            v205[0] = 0x20000;
            v206 = v113;
            v119 = v168;
            (*(void (__fastcall **)(_DWORD *, _DWORD *))(*(_QWORD *)v168 + 24LL))(v168, v205);
            v203[1] = 0;
            v204 = 0;
            v203[0] = 0x40000;
            LODWORD(v204) = *((_DWORD *)v32 + 304);
            (*(void (__fastcall **)(_DWORD *, _DWORD *))(*(_QWORD *)v119 + 24LL))(v119, v203);
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v119 + 16LL))(v119);
            LogTransaction((unsigned int)v103, &v141, v217);
            TraceIndexTransaction(&MSSearchTraceId_IndexItem_DataComplete, v32, 0, 0, 0);
            if ( (unsigned __int8)IsAnyEnabled<wil::Feature<__WilFeatureTraits_Feature_55683212>,wil::Feature<__WilFeatureTraits_Feature_55904201>>() )
            {
              v120 = v154;
              if ( v154 )
              {
                IsAnyEnabled<wil::Feature<__WilFeatureTraits_Feature_55683212>,wil::Feature<__WilFeatureTraits_Feature_55904201>>();
                v121 = CBackOffController::PendingNotifications(v120, 0);
                v122 = CBackOffController::PendingNotifications(v120, 1);
                CGatheringService::UpdatePendingNotificationCount(v123, v121 + v122);
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerTelemetryFixes4B>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SearchIndexerTelemetryFixes4B>::GetImpl'::`2'::impl) )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56414827>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix56414827>::GetImpl'::`2'::impl) )
                  {
                    v124 = (*(__int64 (__fastcall **)(CBackOffController *))(*(_QWORD *)v120 + 32LL))(v120);
                    if ( *((_DWORD *)v120 + 107) )
                      v218 = 2;
                    else
                      v218 = v124 != 0;
                  }
                  else
                  {
                    v218 = 3;
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56621484>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56621484>::GetImpl'::`2'::impl) )
                    IsUserActiveAfterIndexing = CBackOffController::IsUserActiveAfterIndexing(v120);
                  else
                    IsUserActiveAfterIndexing = 2;
                }
              }
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
            {
              v125 = v143;
              v126 = pv;
              v198[0] = (struct CGthrPrj *)pv;
              if ( pv )
                _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
              tip2::details::shared_data<0,0,0>::begin_update(v126 + 2);
              v126[68] = v125;
              tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
              v127 = v224;
              v128 = pv;
              v198[0] = (struct CGthrPrj *)pv;
              if ( pv )
                _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
              tip2::details::shared_data<0,0,0>::begin_update(v128 + 2);
              v128[71] = v127;
              tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
              v129 = (char *)pv;
              v198[0] = (struct CGthrPrj *)pv;
              if ( pv )
                _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
              tip2::details::shared_data<0,0,0>::begin_update(v129 + 8);
              tip2::details::shared_data<0,0,0>::complete_helper(v129 + 8, 2048, 10);
              tip2::test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_RobotThreadTransactionPerfTest,_tip_RobotThreadTransactionPerfTest>>(v198);
            }
            if ( v101 )
              ReleaseSemaphore(v101, 1, 0);
            CPluginCollectionSink::~CPluginCollectionSink((CPluginCollectionSink *)v186);
            CFilterDriver::~CFilterDriver((CFilterDriver *)v217);
            if ( v169 )
              std::_Ref_count_base::_Decref(v169);
            goto LABEL_129;
          }
          ETWLog::LogItem(
            *((_DWORD *)v32 + 319),
            *((const wchar_t **)v32 + 13),
            L"RobotThread - Protocol Handler reports PRTH_S_NOTMODIFIED - skipping indexing");
          CFilterDriver::AdaptiveCrawlUpdate((CFilterDriver *)v217, v91, 0);
          if ( (Microsoft_Windows_Search_CoreEnableBits & 0x40) != 0 )
            McTemplateU0x_EventWriteTransfer(v92, MSSearchTraceId_RobotThread_TransactionNotModified, v32);
          LogTransaction(0, &v141, v217);
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v93 = pv;
          v198[0] = (struct CGthrPrj *)pv;
          if ( pv )
            _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
          tip2::details::shared_data<0,0,0>::begin_update(v93 + 8);
          v93[292] = 1;
        }
        else
        {
          if ( (byte_1802DA182 & 2) != 0 )
            McTemplateU0xq_EventWriteTransfer(v88, v87, v32, (unsigned int)v223);
          LogTransaction(0, &v141, v217);
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60912995>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60912995>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v89 = v223;
          v90 = pv;
          v198[0] = (struct CGthrPrj *)pv;
          if ( pv )
            _InterlockedAdd((volatile signed __int32 *)pv + 80, 1u);
          tip2::details::shared_data<0,0,0>::begin_update(v90 + 2);
          v90[69] = v89;
        }
        goto LABEL_171;
      }
      v84 = v174[0];
      v85 = *(_WORD *)(v83 + 2LL * v174[0]);
      v142 = 0;
      if ( (int)CGthrPrj::GetGatherer(*((CGthrPrj **)v32 + 162), &v142) < 0 )
      {
LABEL_188:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v142);
        v1 = v138;
        goto LABEL_189;
      }
      v198[0] = 0;
      if ( (**(int (__fastcall ***)(struct CGthrPrj *, GUID *, struct CGthrPrj **))v142)(
             v142,
             &GUID_1953486c_8ffa_453f_a489_9f691a007f5e,
             v198) >= 0 )
      {
        if ( !IsVolumeIdUrl((LPCWCH)(*(_QWORD *)(v82 + 8) + 2 * v84)) )
        {
          v86 = (*(__int64 (__fastcall **)(struct CGthrPrj *, _QWORD))(*(_QWORD *)v198[0] + 304LL))(v198[0], v85);
          if ( !v86 )
          {
            AdjustFileTransactionWithHandlerInfo(v32, (const struct CLMSubStr *)v174);
            goto LABEL_187;
          }
          if ( v86 != 1 )
            goto LABEL_187;
        }
        v223 = -2147216890;
      }
LABEL_187:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v198);
      goto LABEL_188;
    }
    if ( (unsigned int)(NewTransaction + 1073473536) <= 1 )
      RecoveryReportIndexRebuildEx(v34, *((_QWORD *)g_pGatheringService + 49), 0, 0);
    v35 = (volatile signed __int32 *)*((_QWORD *)g_pGatheringService + 929);
    if ( v35 )
      _InterlockedAdd(v35, 1u);
    CSyncReadWrite::ReleaseReadAccess(v21);
    v157 = 0;
    v36 = GetTickCount();
    v1 = v138;
    CThread::WaitForEvent(v138, 0xFFFFFFFF, v37);
    v147 = GetTickCount() - v36;
    v38 = (volatile signed __int32 *)*((_QWORD *)g_pGatheringService + 929);
    if ( v38 )
      _InterlockedDecrement(v38);
LABEL_71:
    PerUserCatalogNameForCorruption::SetCatalog(0);
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v141);
    CEnumAllGatherCatalogs::~CEnumAllGatherCatalogs((CEnumAllGatherCatalogs *)v173);
    if ( (_QWORD)v139 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IGatherDataChange>>>(v139, *((_QWORD *)&v139 + 1));
      std::_Deallocate<16>(v139, (v140 - v139) & 0xFFFFFFFFFFFFFFF8uLL);
      v139 = 0;
      v140 = 0;
    }
    CNonExclusiveReleaseable::~CNonExclusiveReleaseable((CNonExclusiveReleaseable *)&v156);
LABEL_44:
    v7 = v137;
    if ( v159 )
      std::_Ref_count_base::_Decref(v159);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
  {
    LODWORD(v199) = 0;
    v200 = 0;
    v130 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 80LL))(v7);
    winrt::check_hresult(v170, v130, &v199);
  }
  if ( v14 )
    CWordBreakerHistory::Shutdown(v14);
  v131 = g_pGatheringService;
  v132 = (volatile signed __int32 *)*((_QWORD *)g_pGatheringService + 928);
  if ( v132 )
  {
    _InterlockedDecrement(v132);
    v131 = g_pGatheringService;
  }
  v133 = (_DWORD *)*((_QWORD *)v131 + 928);
  if ( !v133 || !*v133 )
    g_PropagateEventSinks = 0;
  CWordBreakerSelector::~CWordBreakerSelector((CWordBreakerSelector *)v184);
  wil::com_ptr_t<CGthrPrj,wil::err_returncode_policy>::~com_ptr_t<CGthrPrj,wil::err_returncode_policy>(&v155);
  CLanguageAutoDetection::~CLanguageAutoDetection((CLanguageAutoDetection *)v180);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v179);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v137);
  if ( v152 >= 0 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1800c5670  mov     [rsp+arg_8], rbx
0x1800c5675  mov     [rsp+arg_10], rsi
0x1800c567a  push    rdi
0x1800c567b  push    r12
0x1800c567d  push    r13
0x1800c567f  push    r14
0x1800c5681  push    r15
0x1800c5683  mov     eax, 4000h
0x1800c5688  call    _alloca_probe
0x1800c568d  sub     rsp, rax
0x1800c5690  mov     rax, cs:__security_cookie
0x1800c5697  xor     rax, rsp
0x1800c569a  mov     [rsp+4028h+var_30], rax
0x1800c56a2  mov     r13, rcx
0x1800c56a5  mov     [rsp+4028h+var_3FD0], rcx
0x1800c56aa  mov     [rsp+4028h+var_3EB0], rcx
0x1800c56b2  xor     edi, edi
0x1800c56b4  mov     [rsp+4028h+var_3F70], edi
0x1800c56bb  xor     edx, edx; dwCoInit
0x1800c56bd  xor     ecx, ecx; pvReserved
0x1800c56bf  call    cs:__imp_CoInitializeEx
0x1800c56c5  mov     [rsp+4028h+var_3F68], eax
0x1800c56cc  lea     r12d, [rdi+1]
0x1800c56d0  test    cs:byte_1802DA182, 8
0x1800c56d7  jz      short loc_1800C56FC
0x1800c56d9  lea     rax, [rsp+4028h+var_58]
0x1800c56e1  mov     [rsp+4028h+var_4008], rax; int
0x1800c56e6  mov     r9d, r12d
0x1800c56e9  lea     rdx, MSSearchTraceId_Service_Startup_Duration_Stop
0x1800c56f0  lea     rcx, Microsoft_Windows_Search_Core_Context
0x1800c56f7  call    McGenEventWrite_EventWriteTransfer
0x1800c56fc  lea     rcx, aRobotThread; "Robot Thread"
0x1800c5703  call    ?SetCurrentThreadName@@YAXPEB_W@Z; SetCurrentThreadName(wchar_t const *)
0x1800c5708  mov     rcx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; this
0x1800c570f  mov     r14, [rcx+0F48h]
0x1800c5716  mov     [rsp+4028h+var_3F90], r14
0x1800c571e  call    ?WaitForInitDone@CGatheringService@@QEAAJXZ; CGatheringService::WaitForInitDone(void)
0x1800c5723  mov     ebx, eax
0x1800c5725  test    eax, eax
0x1800c5727  jns     short loc_1800C5784
0x1800c5729  mov     rcx, [rsp+4028h]; this
0x1800c5731  mov     r9d, eax; char *
0x1800c5734  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800c573b  mov     edx, 1748h; void *
0x1800c5740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5745  nop
0x1800c5746  cmp     [rsp+4028h+var_3F68], edi
0x1800c574d  jl      short loc_1800C5755
0x1800c574f  call    cs:__imp_CoUninitialize
0x1800c5755  mov     eax, ebx
0x1800c5757  mov     rcx, [rsp+4028h+var_30]
0x1800c575f  xor     rcx, rsp; StackCookie
0x1800c5762  call    __security_check_cookie
0x1800c5767  lea     r11, [rsp+4028h+var_28]
0x1800c576f  mov     rbx, [r11+38h]
0x1800c5773  mov     rsi, [r11+40h]
0x1800c5777  mov     rsp, r11
0x1800c577a  pop     r15
0x1800c577c  pop     r14
0x1800c577e  pop     r13
0x1800c5780  pop     r12
0x1800c5782  pop     rdi
0x1800c5783  retn
0x1800c5784  mov     rsi, rdi
0x1800c5787  mov     [rsp+4028h+var_3FD8], rdi
0x1800c578c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x1800c5793  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x1800c5798  test    al, al
0x1800c579a  jz      short loc_1800C580E
0x1800c579c  lea     rcx, [rsp+4028h+var_3F80]
0x1800c57a4  call    ?GetInstance@SemanticSearchConfigManager@SemanticSearch@Indexer@Windows@winrt@@SA?AU12345@XZ; winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(void)
0x1800c57a9  mov     rdx, rax
0x1800c57ac  lea     rcx, [rsp+4028h+var_3FD8]
0x1800c57b1  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800c57b6  lea     rcx, [rsp+4028h+var_3F80]; this
0x1800c57be  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800c57c3  lea     rdx, [rsp+4028h+var_3F80]
0x1800c57cb  lea     rcx, [rsp+4028h+var_3FD8]
0x1800c57d0  call    ?ProcessResultsForModelsAvailabilityAsync@?$consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager@UISemanticSearchConfigManager@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchConfigManager>::ProcessResultsForModelsAvailabilityAsync(void)
0x1800c57d5  mov     rbx, rax
0x1800c57d8  mov     rcx, rax
0x1800c57db  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncAction>::Status(void)
0x1800c57e0  test    eax, eax
0x1800c57e2  jnz     short loc_1800C57EC
0x1800c57e4  mov     rcx, rbx
0x1800c57e7  call    ??$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@1@I@Z
0x1800c57ec  mov     ecx, eax; this
0x1800c57ee  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800c57f3  mov     rcx, rbx
0x1800c57f6  call    ?Cancel@?$consume_Windows_System_Threading_IThreadPoolTimer@UIThreadPoolTimer@Threading@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_Threading_IThreadPoolTimer<winrt::Windows::System::Threading::IThreadPoolTimer>::Cancel(void)
0x1800c57fb  nop
0x1800c57fc  lea     rcx, [rsp+4028h+var_3F80]; this
0x1800c5804  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800c5809  mov     rsi, [rsp+4028h+var_3FD8]
0x1800c580e  lea     rcx, LibFileName; "tquery.dll"
0x1800c5815  call    cs:__imp_LoadLibraryW
0x1800c581b  mov     [rsp+4028h+var_3E68], rax
0x1800c5823  test    rax, rax
0x1800c5826  jz      short loc_1800C583F
0x1800c5828  lea     rdx, aExternpropagat; "ExternPropagateEventToOpenQueries"
0x1800c582f  mov     rcx, rax; hModule
0x1800c5832  call    cs:__imp_GetProcAddress
0x1800c5838  mov     cs:?g_PropagateEventSinks@@3PAP6AJW4PROPAGATE_EVENTTYPE@@KPEB_W@ZA, rax; long (*near * g_PropagateEventSinks)(PROPAGATE_EVENTTYPE,ulong,wchar_t const *)
0x1800c583f  mov     [rsp+4028h+var_3E60], dil
0x1800c5847  mov     [rsp+4028h+var_3E58], rdi
0x1800c584f  mov     [rsp+4028h+var_3E50], edi
0x1800c5856  mov     [rsp+4028h+var_3E78], rdi
0x1800c585e  mov     [rsp+4028h+var_3E70], edi
0x1800c5865  mov     [rsp+4028h+var_3E6C], dil
0x1800c586d  mov     [rsp+4028h+var_3F58], rdi
0x1800c5875  mov     [rsp+4028h+var_3F78], rdi
0x1800c587d  lea     rcx, [rsp+4028h+var_3F78]
0x1800c5885  call    ?CreateInstance@?$CComObject@VCWordBreakerHistory@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWordBreakerHistory>::CreateInstance(ATL::CComObject<CWordBreakerHistory> * *)
0x1800c588a  test    eax, eax
0x1800c588c  js      loc_1800C77C5
0x1800c5892  mov     [rsp+4028h+var_3EB8], r14
0x1800c589a  mov     [rsp+4028h+var_3F88], edi
0x1800c58a1  mov     r15, [rsp+4028h+var_3F78]
0x1800c58a9  mov     [rsp+4028h+var_3F58], r15
0x1800c58b1  mov     rax, [r15]
0x1800c58b4  mov     rcx, r15
0x1800c58b7  mov     rax, [rax+8]
0x1800c58bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c58c0  mov     r9, r15; struct CWordBreakerHistory *
0x1800c58c3  lea     r8, [rsp+4028h+var_3E78]; struct CScriptAutoDetection *
0x1800c58cb  lea     rdx, [rsp+4028h+var_3E60]; struct CLanguageAutoDetection *
0x1800c58d3  lea     rcx, [rsp+4028h+var_3E28]; this
0x1800c58db  call    ??0CWordBreakerSelector@@QEAA@AEAVCLanguageAutoDetection@@AEAVCScriptAutoDetection@@PEAVCWordBreakerHistory@@@Z; CWordBreakerSelector::CWordBreakerSelector(CLanguageAutoDetection &,CScriptAutoDetection &,CWordBreakerHistory *)
0x1800c58e0  nop
0x1800c58e1  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800c58e8  mov     rcx, [rax+1D00h]
0x1800c58ef  test    rcx, rcx
0x1800c58f2  jz      short loc_1800C58F8
0x1800c58f4  lock add [rcx], r12d
0x1800c58f8  mov     [rsp+4028h+var_3C58], r12d
0x1800c5900  mov     [rsp+4028h+var_3C54], r12d
0x1800c5908  mov     [rsp+4028h+var_3C50], r12d
0x1800c5910  call    cs:__imp_GetCurrentThread
0x1800c5916  mov     rcx, rax
0x1800c5919  mov     r9d, 0Ch
0x1800c591f  lea     r8, [rsp+4028h+var_3C58]
0x1800c5927  lea     edx, [r9-9]
0x1800c592b  call    cs:__imp_SetThreadInformation
0x1800c5931  mov     rcx, [rsp+4028h]; this
0x1800c5939  test    eax, eax
0x1800c593b  jnz     short loc_1800C594E
0x1800c593d  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800c5944  mov     edx, 1778h; void *
0x1800c5949  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800c594e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59306570@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59306570@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59306570> `wil::Feature<__WilFeatureTraits_Feature_59306570>::GetImpl(void)'::`2'::impl
0x1800c5955  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59306570@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59306570>::__private_IsEnabled(void)
0x1800c595a  test    al, al
0x1800c595c  jz      short loc_1800C5983
0x1800c595e  call    ?ExecuteBulkFilenameIndexingForNewCatalog@CRobotThread@@SAJXZ; CRobotThread::ExecuteBulkFilenameIndexingForNewCatalog(void)
0x1800c5963  mov     rcx, [rsp+4028h]; this
0x1800c596b  test    eax, eax
0x1800c596d  jns     short loc_1800C5983
0x1800c596f  mov     r9d, eax; char *
0x1800c5972  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800c5979  mov     edx, 177Dh; void *
0x1800c597e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c5983  cmp     [r13+28h], edi
0x1800c5987  jnz     loc_1800C76E2
0x1800c598d  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800c5994  mov     r13, [rax+0FA0h]
0x1800c599b  mov     [rsp+4028h+var_3F60], r13
0x1800c59a3  mov     [rsp+4028h+var_3FB0], r13
0x1800c59a8  test    r13, r13
0x1800c59ab  jz      short loc_1800C59C7
0x1800c59ad  mov     edx, [rsp+4028h+var_3F88]; unsigned int
0x1800c59b4  test    edx, edx
0x1800c59b6  jz      short loc_1800C59C7
0x1800c59b8  mov     rcx, r13; this
0x1800c59bb  call    ?RecordOtherSleepTime@CBackOffController@@QEAAXK@Z; CBackOffController::RecordOtherSleepTime(ulong)
0x1800c59c0  mov     [rsp+4028h+var_3F88], edi
0x1800c59c7  lea     rcx, [rsp+4028h+var_3F40]
0x1800c59cf  call    ?GetContainerStatusManager@@YA?AV?$shared_ptr@UIContainerStatusManager@@@std@@XZ; GetContainerStatusManager(void)
0x1800c59d4  nop
0x1800c59d5  mov     rcx, [rsp+4028h+var_3F40]
0x1800c59dd  mov     rax, [rcx]
0x1800c59e0  mov     rax, [rax+28h]
0x1800c59e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c59e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55745486@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55745486@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55745486> `wil::Feature<__WilFeatureTraits_Feature_55745486>::GetImpl(void)'::`2'::impl
0x1800c59f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55745486@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55745486>::__private_IsEnabled(void)
0x1800c59f5  test    al, al
0x1800c59f7  jz      short loc_1800C5A35
0x1800c59f9  mov     dword ptr [rsp+4028h+var_3C78], edi
0x1800c5a00  xorps   xmm0, xmm0
0x1800c5a03  movdqu  [rsp+4028h+var_3C70], xmm0
0x1800c5a0c  mov     rax, [rsi]
0x1800c5a0f  mov     rcx, rsi
0x1800c5a12  mov     rax, [rax+98h]
0x1800c5a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5a1e  lea     r8, [rsp+4028h+var_3C78]
0x1800c5a26  mov     edx, eax
0x1800c5a28  lea     rcx, [rsp+4028h+var_3ED0]
0x1800c5a30  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800c5a35  mov     r14, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800c5a3c  add     r14, 1BC8h
0x1800c5a43  mov     [rsp+4028h+var_3F50], r14
0x1800c5a4b  mov     [rsp+4028h+var_3F48], r12d
0x1800c5a53  mov     rcx, r14; this
0x1800c5a56  call    ?GetReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetReadAccess(void)
0x1800c5a5b  nop
0x1800c5a5c  mov     ebx, edi
0x1800c5a5e  xorps   xmm0, xmm0
0x1800c5a61  movdqu  [rsp+4028h+var_3FC8], xmm0
0x1800c5a67  mov     [rsp+4028h+var_3FB8], rdi
0x1800c5a6c  movdqu  [rsp+4028h+var_3EA8], xmm0
0x1800c5a75  xorps   xmm1, xmm1
0x1800c5a78  movdqu  [rsp+4028h+var_3E98], xmm1
0x1800c5a81  test    ebx, ebx
0x1800c5a83  jnz     loc_1800C5BA2
0x1800c5a89  mov     [rsp+4028h+var_3C98], rdi
0x1800c5a91  lea     rdx, [rsp+4028h+var_3C98]; struct CGthrPrj **
0x1800c5a99  lea     rcx, [rsp+4028h+var_3EA8]; this
0x1800c5aa1  call    ?NextGatherProject@CEnumAllGatherCatalogs@@QEAAJPEAPEAVCGthrPrj@@@Z; CEnumAllGatherCatalogs::NextGatherProject(CGthrPrj * *)
0x1800c5aa6  mov     ebx, eax
0x1800c5aa8  mov     dword ptr [rsp+4028h+var_3FA8], eax
0x1800c5aaf  test    eax, eax
0x1800c5ab1  jnz     loc_1800C5B90
0x1800c5ab7  mov     [rsp+4028h+var_3F98], rdi
0x1800c5abf  lea     rcx, [rsp+4028h+var_3F98]
0x1800c5ac7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c5acc  lea     rdx, [rsp+4028h+var_3F98]; struct IGatherDataChange **
0x1800c5ad4  mov     rcx, [rsp+4028h+var_3C98]; this
0x1800c5adc  call    ?GetGatherDataChange@CGthrPrj@@QEAAXPEAPEAUIGatherDataChange@@@Z; CGthrPrj::GetGatherDataChange(IGatherDataChange * *)
0x1800c5ae1  cmp     [rsp+4028h+var_3F98], rdi
0x1800c5ae9  jz      loc_1800C5B82
0x1800c5aef  mov     rdx, qword ptr [rsp+4028h+var_3FC8+8]
0x1800c5af4  cmp     rdx, [rsp+4028h+var_3FB8]
0x1800c5af9  jz      short loc_1800C5B26
0x1800c5afb  mov     [rdx], rdi
0x1800c5afe  lea     rax, [rsp+4028h+var_3F98]
0x1800c5b06  cmp     rdx, rax
0x1800c5b09  jz      short loc_1800C5B1E
0x1800c5b0b  mov     rax, [rsp+4028h+var_3F98]
0x1800c5b13  mov     [rdx], rax
0x1800c5b16  mov     [rsp+4028h+var_3F98], rdi
0x1800c5b1e  add     qword ptr [rsp+4028h+var_3FC8+8], 8
0x1800c5b24  jmp     short loc_1800C5B39
0x1800c5b26  lea     r8, [rsp+4028h+var_3F98]
0x1800c5b2e  lea     rcx, [rsp+4028h+var_3FC8]
0x1800c5b33  call    ??$_Emplace_reallocate@V?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<IGatherDataChange>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IGatherDataChange>>(Microsoft::WRL::ComPtr<IGatherDataChange> * const,Microsoft::WRL::ComPtr<IGatherDataChange> &&)
0x1800c5b38  nop
0x1800c5b39  jmp     short loc_1800C5B82
0x1800c5b3b  xor     edi, edi
0x1800c5b3d  lea     r12d, [rdi+1]
0x1800c5b41  mov     rax, [rsp+4028h+var_3EB8]
0x1800c5b49  mov     [rsp+4028h+var_3F90], rax
0x1800c5b51  mov     r15, [rsp+4028h+var_3F58]
0x1800c5b59  mov     r14, [rsp+4028h+var_3F50]
0x1800c5b61  mov     ebx, dword ptr [rsp+4028h+var_3FA8]
0x1800c5b68  mov     rax, [rsp+4028h+var_3EB0]
0x1800c5b70  mov     [rsp+4028h+var_3FD0], rax
0x1800c5b75  mov     r13, [rsp+4028h+var_3FB0]
0x1800c5b7a  mov     [rsp+4028h+var_3F60], r13
0x1800c5b82  lea     rcx, [rsp+4028h+var_3F98]
0x1800c5b8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c5b8f  nop
0x1800c5b90  lea     rcx, [rsp+4028h+var_3C98]
0x1800c5b98  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x1800c5b9d  jmp     loc_1800C5A81
0x1800c5ba2  lea     rcx, [rsp+4028h+var_3EA8]; this
0x1800c5baa  call    ?Reset@CEnumAllGatherCatalogs@@QEAAXXZ; CEnumAllGatherCatalogs::Reset(void)
0x1800c5baf  mov     rbx, qword ptr [rsp+4028h+var_3FC8]
0x1800c5bb4  mov     rdx, qword ptr [rsp+4028h+var_3FC8+8]
0x1800c5bb9  cmp     rbx, rdx
0x1800c5bbc  jz      loc_1800C5C54
0x1800c5bc2  mov     rcx, [rbx]
0x1800c5bc5  mov     rax, [rcx]
0x1800c5bc8  mov     rax, [rax+28h]
0x1800c5bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bd1  test    eax, eax
0x1800c5bd3  jns     short loc_1800C5BDB
0x1800c5bd5  add     rbx, 8
0x1800c5bd9  jmp     short loc_1800C5BB4
0x1800c5bdb  lea     rcx, [rsp+4028h+var_3EA8]; this
0x1800c5be3  call    ??1CEnumAllGatherCatalogs@@QEAA@XZ; CEnumAllGatherCatalogs::~CEnumAllGatherCatalogs(void)
0x1800c5be8  nop
0x1800c5be9  mov     rcx, qword ptr [rsp+4028h+var_3FC8]
0x1800c5bee  test    rcx, rcx
0x1800c5bf1  jz      short loc_1800C5C21
0x1800c5bf3  mov     rdx, qword ptr [rsp+4028h+var_3FC8+8]
0x1800c5bf8  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIGatherDataChange@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IGatherDataChange>>>(Microsoft::WRL::ComPtr<IGatherDataChange> *,Microsoft::WRL::ComPtr<IGatherDataChange> * const,std::allocator<Microsoft::WRL::ComPtr<IGatherDataChange>> &)
0x1800c5bfd  mov     rcx, qword ptr [rsp+4028h+var_3FC8]
0x1800c5c02  mov     rdx, [rsp+4028h+var_3FB8]
0x1800c5c07  sub     rdx, rcx
0x1800c5c0a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800c5c0e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c5c13  xorps   xmm0, xmm0
0x1800c5c16  movdqu  [rsp+4028h+var_3FC8], xmm0
0x1800c5c1c  mov     [rsp+4028h+var_3FB8], rdi
0x1800c5c21  lea     rcx, [rsp+4028h+var_3F50]; this
0x1800c5c29  call    ??1CNonExclusiveReleaseable@@QEAA@XZ; CNonExclusiveReleaseable::~CNonExclusiveReleaseable(void)
0x1800c5c2e  nop
0x1800c5c2f  mov     r13, [rsp+4028h+var_3FD0]
0x1800c5c34  mov     rcx, [rsp+4028h+var_3F38]; this
0x1800c5c3c  mov     rsi, [rsp+4028h+var_3FD8]
0x1800c5c41  test    rcx, rcx
  ... truncated ...
```
