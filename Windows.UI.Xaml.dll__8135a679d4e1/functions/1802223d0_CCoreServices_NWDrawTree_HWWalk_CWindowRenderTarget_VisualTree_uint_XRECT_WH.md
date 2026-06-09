# CCoreServices::NWDrawTree(HWWalk *,CWindowRenderTarget *,VisualTree *,uint,XRECT_WH *)

- ea: `0x1802223d0`
- end: `0x180224ec0`
- name: `?NWDrawTree@CCoreServices@@QEAAJPEAVHWWalk@@PEAVCWindowRenderTarget@@PEAVVisualTree@@IPEAUXRECT_WH@@@Z`
- size: `10992`
- prototype: `HRESULT __fastcall(CCoreServices *this, HWWalk *pHWWalk, CWindowRenderTarget *pRenderTarget, VisualTree *pVisualTree, unsigned int forceRedraw, XRECT_WH *prcDirtyRect)`
- caller_count: `2`
- callee_count: `109`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180221e70`
- `0x180808cec`

## callees

- `0x180004bc0`
- `0x18001ac98`
- `0x18001fec0`
- `0x1800217b8`
- `0x180021840`
- `0x180057508`
- `0x18005799c`
- `0x180059c00`
- `0x180059e30`
- `0x18006c2b0`
- `0x18006cfd0`
- `0x1800710d0`
- `0x180089690`
- `0x18008a0b0`
- `0x1800ab600`
- `0x1800ea064`
- `0x180104190`
- `0x180104f34`
- `0x180117aac`
- `0x18012246c`
- `0x180131190`
- `0x180138834`
- `0x1801423d8`
- `0x180146914`
- `0x18014da58`
- `0x18014f62c`
- `0x180150310`
- `0x180150504`
- `0x18015211c`
- `0x18018fa54`
- `0x1801a7f9c`
- `0x1801c2674`
- `0x1801c3570`
- `0x1801c3dac`
- `0x1801d0178`
- `0x1801df610`
- `0x1801f949c`
- `0x18020c2c0`
- `0x18020ca40`
- `0x18021e4e0`
- `0x18021fa00`
- `0x1802204d4`
- `0x180220da0`
- `0x1802223d0`
- `0x1802736ac`
- `0x180275e6c`
- `0x180276128`
- `0x18027751c`
- `0x180278344`
- `0x180278e68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180223a29`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180223a29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180223bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180223d95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180223bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180223d95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222c57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222c57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180222845`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180222c65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180222845`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180222c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180222579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180222579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223bea`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180222557`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180222fc5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180223060`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180224ce3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180222557`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180222fc5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180223060`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180224ce3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180223bd3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180223bd3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180223c3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180223c3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18022256b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802227ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222812`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222945`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222c05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222c29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222d6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802230f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180224b6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18022256b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802227ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222812`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222945`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222c05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222c29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180222d6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802230f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180224b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180223ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180224d71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180223ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180224d71`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1802227c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180222be4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1802227c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180222be4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18022265c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180224825`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18022265c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180224825`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180222a11`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180222e2c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180222e3f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180223a95`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180223b29`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180223c2e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180224329`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802244aa`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18022467d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18022495b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180224a07`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180224a6e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180222a11`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180222e2c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180222e3f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180223a95`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180223b29`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180223c2e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180224329`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802244aa`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18022467d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18022495b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180224a07`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180224a6e`
- `api-ms-win-rtcore-navigation-l1-1-0!RegisterNavigationWindowHandle` at `0x180223cdc`
- `api-ms-win-rtcore-navigation-l1-1-0!RegisterNavigationWindowHandle` at `0x180223cdc`
- `ext-ms-win-xaml-pal-l1-1-0!XamlBehaviorEnabled` at `0x18022377a`
- `ext-ms-win-xaml-pal-l1-1-0!XamlBehaviorEnabled` at `0x180223cc2`
- `ext-ms-win-xaml-pal-l1-1-0!XamlBehaviorEnabled` at `0x18022377a`
- `ext-ms-win-xaml-pal-l1-1-0!XamlBehaviorEnabled` at `0x180223cc2`

## string_xrefs

- `0x180224b7f`: `FlushCompositorCommandsOnDeviceLost(pRenderTarget)`
- `0x180224b94`: `onecoreuap\windows\dxaml\xcp\core\dll\xcpcore.cpp`

## pseudocode

```c
__int64 __fastcall CCoreServices::NWDrawTree(
        CCoreServices *this,
        _STOWED_EXCEPTION_INFORMATION_V2 **pHWWalk,
        CWindowRenderTarget *pRenderTarget,
        VisualTree *pVisualTree,
        unsigned int forceRedraw,
        XRECT_WH *prcDirtyRect)
{
  ctl::ComBase *v6; // rdi
  CCoreServices *v7; // r13
  CWindowRenderTarget *v8; // r12
  WindowsPresentTarget *m_ptr; // rcx
  int m_height; // eax
  CTimeManager *m_pTimeManager; // r15
  LARGE_INTEGER *v12; // rbx
  _QWORD *Value; // r14
  HRESULT v14; // ecx
  unsigned int v15; // edx
  char *FailFast; // rsi
  HRESULT InstanceBase; // eax
  HRESULT v18; // edi
  __int64 v19; // rcx
  ctl::WeakReferenceSourceNoThreadId *v20; // rdi
  LARGE_INTEGER *v21; // rsi
  __int64 v22; // r14
  HRESULT v23; // esi
  bool v24; // zf
  unsigned __int16 *p_tlgEvtMetaSize; // r8
  __int64 v26; // rdx
  _TraceLoggingMetadata_t *v27; // r9
  struct _STOWED_EXCEPTION_INFORMATION_V2 **v28; // rbx
  unsigned int v29; // esi
  _DWORD *v30; // rax
  _DWORD *v31; // rdi
  _QWORD *i; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int16 v34; // cx
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  char *j; // r9
  __int64 v39; // rax
  IXcpHostSite *m_pHostSite; // rcx
  HRESULT v41; // eax
  bool v42; // r8
  IPALClock *v43; // rcx
  bool v44; // di
  unsigned int v45; // edx
  double v46; // xmm6_8
  IFrameScheduler *pFrameScheduler; // rax
  HRESULT v48; // eax
  DesignerMode v49; // ecx
  HRESULT v50; // r15d
  struct _STOWED_EXCEPTION_INFORMATION_V2 **v51; // rbx
  unsigned int v52; // esi
  _DWORD *v53; // rax
  _DWORD *v54; // rdi
  _QWORD *k; // rax
  HANDLE v56; // rax
  unsigned __int16 v57; // cx
  __int64 v58; // rax
  int v59; // r8d
  __int64 v60; // rax
  char *m; // r9
  __int64 v62; // rax
  HRESULT v63; // eax
  XSIZE_PHYSICAL *v64; // r8
  HRESULT DirectManipulationChanges; // eax
  CDependencyObject *v66; // rbx
  int v67; // eax
  CLayoutManager *LayoutManagerForElement; // rax
  HRESULT v69; // ecx
  CLayoutManager *v70; // rdi
  unsigned int v71; // r14d
  unsigned int v72; // r15d
  HRESULT updated; // eax
  DirectUI::DXamlCore *v74; // rbx
  HRESULT v75; // ecx
  CEventManager *m_pEventManager; // rcx
  CTimeManager *v77; // rax
  BOOL v78; // edi
  DirectUI::DXamlCore *Current; // rax
  HRESULT BuildTreeService; // eax
  _STOWED_EXCEPTION_INFORMATION_V2 **v81; // rbx
  __int64 v82; // rax
  int v83; // r12d
  CXcpList<IRenderTargetElement> *m_pPendingListNoRef; // rcx
  CXcpList<IRenderTargetElement>::XCPListNode *m_pHead; // rcx
  CXcpList<IRenderTargetElement>::XCPListNode *m_pNext; // rbx
  CRenderTargetElementData *v87; // rax
  HRESULT v88; // eax
  xref_ptr<CContentRoot> *Mylast; // rdi
  xref_ptr<CContentRoot> *n; // rbx
  VisualTree *m_pVisualTree; // rcx
  CUIElement *v92; // rcx
  std::shared_ptr<Instrumentation::XamlTraceSession> m_arrangeRect; // xmm0
  HRESULT v94; // eax
  __int16 v95; // ax
  __int16 v96; // ax
  CRenderTargetBitmapManager *v97; // r12
  BOOL v98; // ecx
  CCoreServices *m_pCoreNoRef; // rdx
  CDeployment *m_pDeploymentTree; // rax
  CApplication *m_pApplication; // r8
  CXcpList<IRenderTargetElement> *v102; // rax
  CXcpList<IRenderTargetElement>::XCPListNode *v103; // rax
  IRenderTargetElement *m_pData; // r14
  CXcpList<IRenderTargetElement>::XCPListNode *v105; // r15
  CUIElement *m_pRenderElement; // rbx
  VisualTree *m_pMainVisualTree; // rcx
  CUIElement *v108; // rsi
  CDependencyObject *v109; // rdi
  KnownTypeIndex v110; // ax
  const CClassInfo *ClassInfoByIndex; // rax
  KnownTypeIndex v112; // ax
  HRESULT v113; // eax
  HRESULT v114; // ebx
  CTimeManager *v115; // r15
  IXcpBrowserHost *m_pBrowserHost; // rcx
  IFrameScheduler *v117; // rax
  DCompTreeHost *v118; // rcx
  FacadeReferenceWrapper *ptr; // rbx
  std::_List_node<xref_ptr<CTranslateTransform>,void *> *Myhead; // rdi
  std::_List_node<xref_ptr<CTranslateTransform>,void *> *ii; // rbx
  CTranslateTransform *v122; // rsi
  const CClassInfo *v123; // rax
  FacadeReferenceWrapper *v124; // rcx
  Instrumentation::XamlTraceSession *v125; // rcx
  unsigned __int64 v126; // rdx
  CInputServices *v127; // rcx
  KeyTipManager *KeyTipManager; // rax
  KeyTipManager::State v129; // r8d
  char v130; // cl
  unsigned int v131; // r14d
  HRESULT v132; // edi
  unsigned int v133; // ebx
  unsigned int v134; // eax
  unsigned int v135; // eax
  unsigned int v136; // ecx
  __int64 v137; // rcx
  HRESULT v138; // eax
  IComponentHostManager *m_pComponentHostManager; // rcx
  CWindowRenderTarget *v140; // rbx
  HRESULT v141; // eax
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (__cdecl*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy,wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t> > *p_m_deviceLostWaiter; // r14
  HANDLE *v143; // r12
  HANDLE EventW; // rax
  signed int LastError; // eax
  HRESULT v146; // ebx
  HANDLE v147; // r13
  CD3D11Device *v148; // rbx
  HRESULT v149; // eax
  _RTL_CRITICAL_SECTION *p_m_cs; // rsi
  __int64 v151; // rcx
  char v152; // bl
  _RTL_CRITICAL_SECTION *v153; // rdi
  void (__fastcall ***OwningThread)(_QWORD, GUID *, __int64 *); // rsi
  void (__fastcall *v155)(_QWORD, GUID *, __int64 *); // r15
  HRESULT v156; // eax
  __int64 v157; // rcx
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int v159; // eax
  HRESULT v160; // ebx
  InitializationType m_initializationType; // eax
  ImageSharingEngineHost::ImageSharingState *v162; // rbx
  HWND__ *v163; // rdi
  bool IsComponent; // si
  DCompTreeHost *v165; // r14
  DesignerMode v166; // ecx
  DWORD CurrentProcessId; // eax
  HRESULT v168; // eax
  __int64 v169; // rcx
  _RTL_CRITICAL_SECTION *v170; // rcx
  Windows::UI::Composition::ICompositionBrush *v171; // rdx
  Windows::UI::Composition::ICompositionBrush *v172; // rcx
  DCompTreeHost *v173; // rbx
  BOOL v174; // r12d
  CConnectedAnimationService *v175; // r13
  CConnectedAnimation **p_m_ptr; // r14
  unsigned __int64 v177; // rdi
  xref_ptr<CConnectedAnimation> *v178; // r15
  CConnectedAnimation *v179; // rsi
  unsigned __int64 v180; // rbx
  unsigned __int64 v181; // rax
  unsigned __int64 m_preparedTimestamp; // rcx
  HRESULT v183; // eax
  IXcpBrowserHost *v184; // rcx
  __int64 v185; // rax
  HRESULT v186; // eax
  unsigned __int8 m_State; // al
  CFxCallbacks *m_cTrackingInterval; // rcx
  unsigned __int64 v189; // rbx
  unsigned __int64 m_lPrvMemCount; // rax
  DCompTreeHost *v191; // r15
  std::pair<CXamlIslandRoot *,DCompTreeHost::XamlIslandRenderData> *Myfirst; // rbx
  std::pair<CXamlIslandRoot *,DCompTreeHost::XamlIslandRenderData> *v193; // rdi
  CXamlIslandRoot *first; // r14
  ImageSharingEngineHost::ImageSharingState **p_second; // rsi
  ImageSharingEngineHost::ImageSharingState *v196; // rcx
  IXcpHostSite *v197; // rcx
  __int64 v198; // rax
  HRESULT Worker; // eax
  CConnectedAnimationService *v200; // rax
  CConnectedAnimation **v201; // rdi
  CConnectedAnimation **v202; // r14
  CConnectedAnimation *v203; // rbx
  HRESULT v204; // eax
  CUIElement *v205; // rcx
  unsigned int v206; // eax
  int v207; // edi
  HRESULT v208; // eax
  CUIElement *v209; // r14
  HRESULT v210; // ebx
  HWWalk *v211; // r12
  HRESULT v212; // eax
  AutomationEventsHelper *p_m_automationEventsHelper; // rcx
  HRESULT v214; // ecx
  CRenderTargetBitmapManager *m_pRenderTargetBitmapManager; // rcx
  ImageSurfaceWrapper **v216; // r8
  ImageSurfaceWrapper **jj; // rcx
  ImageSurfaceWrapper *v218; // rax
  bool v219; // dl
  ImageSurfaceWrapper **v220; // rax
  int v221; // eax
  float v222; // xmm7_4
  ctl::implements<DCompHelpers::IDCompVisual> *m_pDisconnectedHwndRootVisual; // rcx
  xref_ptr<CContentRoot> *v224; // rdi
  CContentRoot **kk; // rbx
  CContentRoot *v226; // rcx
  volatile signed __int32 *m_ptr_as_int; // rax
  HRESULT v228; // eax
  float v229; // xmm6_4
  float v230; // xmm6_4
  CEventArgs *v231; // rax
  CFxCallbacks *v232; // rcx
  CEventArgs *v233; // rbx
  DirectUI::DXamlCore *v234; // rax
  HRESULT RenderedEventSource; // eax
  HRESULT v236; // edi
  signed __int64 v237; // rdi
  CTimeManager *v238; // r12
  DirectUI::DXamlCore *v239; // rax
  HRESULT BudgetManager; // eax
  _STOWED_EXCEPTION_INFORMATION_V2 **v241; // rbx
  unsigned __int64 v242; // rax
  CCoreServices *pNext; // rbx
  __int64 v244; // rdi
  unsigned __int64 v245; // r15
  CCoreServices *v246; // rcx
  ImageSurfaceWrapper *p_Myend; // rcx
  unsigned __int8 v248; // r14
  Flyweight::ValueObjectWrapper<CDOSharedState> *v249; // rax
  CCoreServices *m_coreServices; // rdi
  IPALEvent *m_pHasAnimationsEvent; // rcx
  HRESULT v252; // eax
  HRESULT v253; // ebx
  IPALEvent *m_pAnimationsCompleteEvent; // rcx
  HRESULT v255; // eax
  HRESULT v256; // ebx
  IPALEvent *v257; // rcx
  HRESULT v258; // eax
  HRESULT v259; // ebx
  unsigned __int64 v260; // rax
  unsigned __int64 v261; // rbx
  unsigned __int64 v262; // r14
  IXcpBrowserHost_vtbl *v263; // rax
  __int64 v264; // rax
  HRESULT v265; // ebx
  HRESULT v266; // eax
  _DWORD *v267; // rax
  unsigned int Height; // r8d
  unsigned int Width; // eax
  int Y; // ecx
  int X; // edx
  std::_Ref_count_base *Rep; // rcx
  unsigned int v273; // r15d
  unsigned int v274; // ebx
  unsigned int v275; // esi
  unsigned __int8 *v276; // r14
  unsigned int v277; // ecx
  __int64 v278; // rax
  __int64 v279; // rcx
  __int64 v280; // rdi
  unsigned int UserDataCount; // [rsp+20h] [rbp-E0h]
  float UserDataCounta; // [rsp+20h] [rbp-E0h]
  bool tickOnlyTimers; // [rsp+38h] [rbp-C8h]
  bool newAnimationsCheckForAnimationComplete; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int cStowedExceptions; // [rsp+58h] [rbp-A8h] BYREF
  char v287; // [rsp+60h] [rbp-A0h]
  bool DesignerMode; // [rsp+61h] [rbp-9Fh]
  bool newAnimationsHasActiveFiniteAnimations[6]; // [rsp+62h] [rbp-9Eh] BYREF
  CWindowRenderTarget *v290; // [rsp+68h] [rbp-98h]
  char v291; // [rsp+70h] [rbp-90h]
  CLayoutManager *v292; // [rsp+78h] [rbp-88h]
  unsigned int pCanPickupForRender; // [rsp+80h] [rbp-80h] BYREF
  int v294; // [rsp+88h] [rbp-78h]
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+90h] [rbp-70h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+98h] [rbp-68h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-60h]
  __int64 directManipulationViewportsChanged; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v299; // [rsp+B0h] [rbp-50h] BYREF
  DCompTreeHost *m_pDCompTreeHost; // [rsp+B8h] [rbp-48h]
  CCoreServices *core; // [rsp+C0h] [rbp-40h]
  unsigned int m_count; // [rsp+C8h] [rbp-38h]
  unsigned int m_StartOffset; // [rsp+CCh] [rbp-34h]
  unsigned int m_actualSize; // [rsp+D0h] [rbp-30h]
  CTimeManager *v305; // [rsp+D8h] [rbp-28h]
  CDependencyObject *pObject; // [rsp+E0h] [rbp-20h]
  XRECT_WH *pDirtyRect; // [rsp+E8h] [rbp-18h] BYREF
  xvector<CCompositorDirectManipulationViewport *> directManipulationViewports; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 *m_data; // [rsp+108h] [rbp+8h]
  XRECTF_RB windowBounds; // [rsp+110h] [rbp+10h] BYREF
  std::shared_ptr<Instrumentation::XamlTraceSession> traceSession; // [rsp+120h] [rbp+20h] BYREF
  Microsoft::WRL::ComPtr<FacadeReferenceWrapper> v312[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v313; // [rsp+140h] [rbp+40h]
  _QWORD v314[2]; // [rsp+150h] [rbp+50h] BYREF
  _EVENT_TRACE_HEADER pData; // [rsp+160h] [rbp+60h] BYREF
  _EVENT_DATA_DESCRIPTOR pDesc; // [rsp+190h] [rbp+90h] BYREF
  unsigned int *p_directManipulationViewportsChanged; // [rsp+1A0h] [rbp+A0h]
  __int64 v318; // [rsp+1A8h] [rbp+A8h]
  void *p_cStowedExceptions; // [rsp+1B0h] [rbp+B0h]
  __int64 v320; // [rsp+1B8h] [rbp+B8h]
  unsigned int *p_pCanPickupForRender; // [rsp+1C0h] [rbp+C0h]
  __int64 v322; // [rsp+1C8h] [rbp+C8h]

  v6 = 0;
  pDirtyRect = prcDirtyRect;
  core = this;
  v7 = this;
  m_count = 0;
  v8 = pRenderTarget;
  m_actualSize = 0;
  m_StartOffset = 0;
  v290 = pRenderTarget;
  pppStowedExceptions = pHWWalk;
  v292 = 0;
  m_data = 0;
  memset(&directManipulationViewports, 0, 20);
  LODWORD(directManipulationViewportsChanged) = 0;
  if ( pVisualTree )
    pObject = pVisualTree->m_rootVisual.m_ptr;
  else
    pObject = 0;
  m_ptr = pRenderTarget->m_presentTarget.m_ptr;
  ppStowedExceptions = 0;
  *(_QWORD *)&windowBounds.left = 0;
  if ( m_ptr )
  {
    m_height = m_ptr->m_height;
    windowBounds.right = (float)(int)m_ptr->m_width;
  }
  else
  {
    windowBounds.right = 0.0;
    m_height = 0;
  }
  m_pTimeManager = v7->m_pTimeManager;
  v305 = m_pTimeManager;
  v291 = 0;
  newAnimationsHasActiveFiniteAnimations[0] = 0;
  v287 = 0;
  newAnimationsCheckForAnimationComplete = 0;
  windowBounds.bottom = (float)m_height;
  if ( !v7->m_isRenderEnabled && !v7->m_isFirstFrameAfterAppStart || (v294 = 1, v7->m_isSuspended) )
    v294 = 0;
  LOBYTE(m_ptr) = 1;
  m_pDCompTreeHost = pRenderTarget->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost;
  DesignerMode = DesignerInterop::GetDesignerMode((DesignerMode)m_ptr);
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 2) != 0 )
  {
    traceSession = 0;
    *(_OWORD *)&v312[0].ptr_ = 0;
    v313 = 0;
    if ( McGenPreVista )
    {
      v312[1].ptr_ = (FacadeReferenceWrapper *)&FrameId;
      LOWORD(traceSession._Ptr) = 48;
      HIDWORD(v313) = 1703936;
      HIDWORD(traceSession._Ptr) = 1025;
      TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, (PEVENT_TRACE_HEADER)&traceSession);
    }
    else
    {
      PfnEventWrite(WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle, &FrameBegin, 0, 0);
    }
  }
  v12 = 0;
  if ( DXamlInstanceStorage::g_dwTlsIndex == -1 )
  {
    Value = 0;
    OnNewFailure_2955_(-1);
  }
  else
  {
    Value = TlsGetValue(DXamlInstanceStorage::g_dwTlsIndex);
    if ( !Value && GetLastError() )
      OnFailure_977_(v14);
  }
  if ( Value[32] )
    goto LABEL_30;
  FailFast = (char *)XcpAllocation::OSMemoryAllocateFailFast(0x80u);
  if ( FailFast )
  {
    *((_QWORD *)FailFast + 1) = 0;
    v6 = (ctl::ComBase *)(FailFast + 16);
    *(_QWORD *)FailFast = Windows::Foundation::Collections::IIterable<Windows::UI::Xaml::StateTriggerBase *>::`vftable';
    ctl::WeakReferenceSource::WeakReferenceSource((ctl::WeakReferenceSource *)(FailFast + 16));
    *((_QWORD *)FailFast + 13) = 0;
    *(_QWORD *)FailFast = ctl::ComObject<DirectUI::BudgetManager>::`vftable'{for `ctl::ComObjectBase'};
    *((_QWORD *)FailFast + 2) = ctl::ComObject<DirectUI::BudgetManager>::`vftable'{for `DirectUI::BudgetManager'};
  }
  else
  {
    FailFast = 0;
  }
  InstanceBase = ctl::ComObjectBase::CreateInstanceBase(v6, v15);
  v18 = InstanceBase;
  if ( InstanceBase >= 0 )
  {
    v19 = Value[32];
    v20 = (ctl::WeakReferenceSourceNoThreadId *)(FailFast + 16);
    if ( !FailFast )
      v20 = 0;
    if ( v19 )
    {
      Value[32] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    Value[32] = v20;
    ctl::WeakReferenceSourceNoThreadId::UpdatePeg(v20, 1);
LABEL_30:
    v21 = (LARGE_INTEGER *)Value[32];
    if ( v21 )
    {
      (*(void (__fastcall **)(_QWORD))(v21->QuadPart + 8))(Value[32]);
      v12 = v21;
    }
    QueryPerformanceCounter(v12 + 12);
    v22 = 0;
    v23 = 0;
    goto LABEL_36;
  }
  OnFailure_2990_(InstanceBase);
  if ( FailFast )
    ctl::ComObject<DirectUI::BudgetManager>::Release((ctl::ComObject<DirectUI::BudgetManager> *)(FailFast + 16));
  OnFailure_2990_(v18);
  OnFailure_2990_(v18);
  v23 = v18;
  OnFailure_2990_(v18);
  v22 = 0;
LABEL_36:
  if ( v12 )
    (*(void (__fastcall **)(LARGE_INTEGER *))(v12->QuadPart + 16))(v12);
  if ( v23 >= 0 )
  {
    v24 = v7->m_pDrawReentrancyCheck == 0;
    p_tlgEvtMetaSize = &tlgEvent._tlgEvtMetaSize;
    cStowedExceptions = 0;
    v26 = 0x200000000000LL;
    v27 = &TraceLoggingMetadata;
    if ( v24 )
    {
      if ( Tlgg_hTraceProviderProv.RegHandle
        && Tlgg_hTraceProviderProv.LevelPlus1 > 5
        && (Tlgg_hTraceProviderProv.KeywordAny & 0x200000000000LL) != 0
        && (Tlgg_hTraceProviderProv.KeywordAll & 0x200000000000LL) == Tlgg_hTraceProviderProv.KeywordAll )
      {
        traceSession._Rep = (std::_Ref_count_base *)0x200000000000LL;
        *(&pData.GuidPtr + 1) = (unsigned __int64)&pCanPickupForRender;
        HIDWORD(traceSession._Ptr) = *(unsigned __int16 *)&tlgEvent._tlgLevel;
        *(_QWORD *)&pData.Size = Tlgg_hTraceProviderProv.ProviderMetadataPtr;
        pCanPickupForRender = -2147418113;
        pData.ProcessorTime = 4;
        LODWORD(traceSession._Ptr) = 184549376;
        pData.ThreadId = *Tlgg_hTraceProviderProv.ProviderMetadataPtr;
        pData.TimeStamp.QuadPart = (__int64)&tlgEvent._tlgEvtMetaSize;
        pData.ProcessId = 2;
        pData.GuidPtr = 0x10000001BLL;
        v299 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(
          Tlgg_hTraceProviderProv.RegHandle,
          (PCEVENT_DESCRIPTOR)&traceSession,
          0,
          0,
          3u,
          (PEVENT_DATA_DESCRIPTOR)&pData);
      }
      OnNewFailureEncountered(-2147418113, 0, 0);
      v28 = 0;
      v29 = 0;
      if ( g_dwErrorContextTlsIndex != -1 )
      {
        v30 = TlsGetValue(g_dwErrorContextTlsIndex);
        v31 = v30;
        if ( v30 )
        {
          v30[1048] |= 2u;
          if ( g_dwWarningContextTlsIndex != -1 )
          {
            for ( i = TlsGetValue(g_dwWarningContextTlsIndex); i; ++v22 )
              i = (_QWORD *)i[525];
          }
          ProcessHeap = GetProcessHeap();
          v28 = (struct _STOWED_EXCEPTION_INFORMATION_V2 **)HeapAlloc(ProcessHeap, 0, 8 * v22 + 40);
          if ( !v28 )
            goto LABEL_64;
          do
          {
            if ( v29 >= 5 )
              break;
            v34 = 0;
            while ( v34 <= *((_WORD *)v31 + 3122) && v34 < *((_WORD *)v31 + 6) )
            {
              v35 = v34++;
              v36 = v31[v35 + 1049];
              if ( v36 )
                goto LABEL_58;
            }
            v36 = -2147467259;
LABEL_58:
            *(_QWORD *)(v31 + 1037) = 0;
            *(_QWORD *)(v31 + 1039) = 0;
            *(_QWORD *)(v31 + 1041) = 0;
            *(_QWORD *)(v31 + 1043) = 0;
            *(_QWORD *)(v31 + 1045) = 0;
            v31[1047] = 0;
            v31[1037] &= ~2u;
            v31[1037] |= 1u;
            v31[1036] = v36;
            v31[1034] = 56;
            v31[1035] = 1397043250;
            v31[1037] = v31[2] ^ (v31[1037] ^ v31[2]) & 3;
            v31[1040] = 8;
            v31[1041] = *((unsigned __int16 *)v31 + 6);
            *((_QWORD *)v31 + 521) = v31 + 4;
            v37 = v29++;
            v31[1044] = 1280131416;
            *((_QWORD *)v31 + 523) = v31;
            v28[v37] = (struct _STOWED_EXCEPTION_INFORMATION_V2 *)(v31 + 1034);
            v31 = (_DWORD *)*((_QWORD *)v31 + 936);
          }
          while ( v31 );
          if ( v22 && g_dwWarningContextTlsIndex != -1 )
          {
            v22 = 0;
            for ( j = (char *)TlsGetValue(g_dwWarningContextTlsIndex); j; j = (char *)*((_QWORD *)j + 525) )
            {
              *(_QWORD *)(j + 4148) = 0;
              *(_QWORD *)(j + 4156) = 0;
              *(_QWORD *)(j + 4164) = 0;
              *(_QWORD *)(j + 4172) = 0;
              *(_QWORD *)(j + 4180) = 0;
              *((_DWORD *)j + 1047) = 0;
              *((_DWORD *)j + 1037) &= ~2u;
              *((_DWORD *)j + 1037) |= 1u;
              *((_DWORD *)j + 1034) = 56;
              *((_DWORD *)j + 1035) = 1397043250;
              *((_DWORD *)j + 1036) = 1;
              *((_DWORD *)j + 1037) = *((_DWORD *)j + 2) ^ (*((_DWORD *)j + 1037) ^ *((_DWORD *)j + 2)) & 3;
              *((_DWORD *)j + 1040) = 8;
              *((_DWORD *)j + 1041) = *((unsigned __int16 *)j + 6);
              *((_QWORD *)j + 521) = j + 16;
              v39 = v29++;
              *((_DWORD *)j + 1044) = 1464680792;
              *((_QWORD *)j + 523) = j;
              v28[v39] = (struct _STOWED_EXCEPTION_INFORMATION_V2 *)(j + 4136);
            }
          }
          else
          {
LABEL_64:
            v22 = 0;
          }
        }
      }
      RoFailFastWithErrorContextInternal2(-2147418113, v29, v28);
    }
    m_pHostSite = v7->m_pHostSite;
    v7->m_pDrawReentrancyCheck = 0;
    if ( m_pHostSite )
      cStowedExceptions = ((__int64 (__fastcall *)(IXcpHostSite *, __int64, unsigned __int16 *, _TraceLoggingMetadata_t *))m_pHostSite->GetEnableOverdrawHeatMap)(
                            m_pHostSite,
                            v26,
                            p_tlgEvtMetaSize,
                            v27);
    if ( !v7->m_pPALClock.m_ptr )
    {
      v41 = ((__int64 (__fastcall *)(IPALCoreServices *, xref_ptr<IPALClock> *, unsigned __int16 *, _TraceLoggingMetadata_t *))gps.m_pTarget->CreateClock)(
              &gps.m_pTarget->IPALCoreServices,
              &v7->m_pPALClock,
              p_tlgEvtMetaSize,
              v27);
      v23 = v41;
      if ( v41 < 0 )
      {
        OnFailure_2990_(v41);
LABEL_316:
        v70 = v292;
        goto LABEL_317;
      }
    }
    v43 = v7->m_pPALClock.m_ptr;
    v44 = !DesignerMode;
    DesignerMode ^= 1u;
    v46 = ((double (__fastcall *)(IPALClock *, __int64, unsigned __int16 *, _TraceLoggingMetadata_t *))v43->GetAbsoluteTimeInSeconds)(
            v43,
            v26,
            p_tlgEvtMetaSize,
            v27);
    if ( v7->m_isSuspended )
    {
      CCoreServices::ProcessMediaEvents(v7, v45);
      pFrameScheduler = v7->m_pBrowserHost->GetFrameScheduler(v7->m_pBrowserHost);
      v48 = CTimeManager::Tick(m_pTimeManager, 0, 0, 0, 0, 0, pFrameScheduler, 1, 0, 0);
      v50 = v48;
      if ( v48 < 0 )
      {
        OnFailure_2990_(v48);
        if ( Tlgg_hTraceProviderProv.RegHandle
          && Tlgg_hTraceProviderProv.LevelPlus1 > 5
          && (Tlgg_hTraceProviderProv.KeywordAny & 0x200000000000LL) != 0
          && (Tlgg_hTraceProviderProv.KeywordAll & 0x200000000000LL) == Tlgg_hTraceProviderProv.KeywordAll )
        {
          traceSession._Rep = (std::_Ref_count_base *)0x200000000000LL;
          *(&pData.GuidPtr + 1) = (unsigned __int64)&v299;
          HIDWORD(traceSession._Ptr) = *(unsigned __int16 *)&tlgEvent._tlgLevel;
          *(_QWORD *)&pData.Size = Tlgg_hTraceProviderProv.ProviderMetadataPtr;
          v299 = v50;
          pData.ProcessorTime = 4;
          LODWORD(traceSession._Ptr) = 184549376;
          pData.ThreadId = *Tlgg_hTraceProviderProv.ProviderMetadataPtr;
          pData.TimeStamp.QuadPart = (__int64)&tlgEvent._tlgEvtMetaSize;
          pData.ProcessId = 2;
          pData.GuidPtr = 0x10000001BLL;
          pCanPickupForRender = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(
            Tlgg_hTraceProviderProv.RegHandle,
            (PCEVENT_DESCRIPTOR)&traceSession,
            0,
            0,
            3u,
            (PEVENT_DATA_DESCRIPTOR)&pData);
        }
        v51 = 0;
        v52 = 0;
        if ( g_dwErrorContextTlsIndex != -1 )
        {
          v53 = TlsGetValue(g_dwErrorContextTlsIndex);
          v54 = v53;
          if ( v53 )
          {
            v53[1048] |= 2u;
            if ( g_dwWarningContextTlsIndex != -1 )
            {
              for ( k = TlsGetValue(g_dwWarningContextTlsIndex); k; ++v22 )
                k = (_QWORD *)k[525];
            }
            v56 = GetProcessHeap();
            v51 = (struct _STOWED_EXCEPTION_INFORMATION_V2 **)HeapAlloc(v56, 0, 8 * v22 + 40);
            if ( v51 )
            {
              do
              {
                if ( v52 >= 5 )
                  break;
                v57 = 0;
                while ( v57 <= *((_WORD *)v54 + 3122) && v57 < *((_WORD *)v54 + 6) )
                {
                  v58 = v57++;
                  v59 = v54[v58 + 1049];
                  if ( v59 )
                    goto LABEL_91;
                }
                v59 = -2147467259;
LABEL_91:
                *(_QWORD *)(v54 + 1037) = 0;
                *(_QWORD *)(v54 + 1039) = 0;
                *(_QWORD *)(v54 + 1041) = 0;
                *(_QWORD *)(v54 + 1043) = 0;
                *(_QWORD *)(v54 + 1045) = 0;
                v54[1047] = 0;
                v54[1037] &= ~2u;
                v54[1037] |= 1u;
                v54[1034] = 56;
                v54[1035] = 1397043250;
                v54[1036] = v59;
                v54[1037] = v54[2] ^ (v54[1037] ^ v54[2]) & 3;
                v54[1040] = 8;
                v54[1041] = *((unsigned __int16 *)v54 + 6);
                *((_QWORD *)v54 + 521) = v54 + 4;
                v60 = v52++;
                v54[1044] = 1280131416;
                *((_QWORD *)v54 + 523) = v54;
                v51[v60] = (struct _STOWED_EXCEPTION_INFORMATION_V2 *)(v54 + 1034);
                v54 = (_DWORD *)*((_QWORD *)v54 + 936);
              }
              while ( v54 );
              v7 = core;
              if ( v22 )
              {
                if ( g_dwWarningContextTlsIndex != -1 )
                {
                  for ( m = (char *)TlsGetValue(g_dwWarningContextTlsIndex); m; m = (char *)*((_QWORD *)m + 525) )
                  {
                    *(_QWORD *)(m + 4148) = 0;
                    *(_QWORD *)(m + 4156) = 0;
                    *(_QWORD *)(m + 4164) = 0;
                    *(_QWORD *)(m + 4172) = 0;
                    *(_QWORD *)(m + 4180) = 0;
                    *((_DWORD *)m + 1047) = 0;
                    *((_DWORD *)m + 1037) &= ~2u;
                    *((_DWORD *)m + 1037) |= 1u;
                    *((_DWORD *)m + 1034) = 56;
                    *((_DWORD *)m + 1035) = 1397043250;
                    *((_DWORD *)m + 1036) = 1;
                    *((_DWORD *)m + 1037) = *((_DWORD *)m + 2) ^ (*((_DWORD *)m + 1037) ^ *((_DWORD *)m + 2)) & 3;
                    *((_DWORD *)m + 1040) = 8;
                    *((_DWORD *)m + 1041) = *((unsigned __int16 *)m + 6);
                    *((_QWORD *)m + 521) = m + 16;
                    v62 = v52++;
                    *((_DWORD *)m + 1044) = 1464680792;
                    *((_QWORD *)m + 523) = m;
                    v51[v62] = (struct _STOWED_EXCEPTION_INFORMATION_V2 *)(m + 4136);
                  }
                }
              }
            }
          }
        }
        RoFailFastWithErrorContextInternal2(v50, v52, v51);
      }
    }
    else
    {
      v63 = CCoreServices::Tick(
              v7,
              v44,
              1,
              newAnimationsHasActiveFiniteAnimations,
              &newAnimationsCheckForAnimationComplete);
      v23 = v63;
      if ( v63 < 0 )
        goto LABEL_478;
      v291 = newAnimationsHasActiveFiniteAnimations[0];
      v287 = newAnimationsCheckForAnimationComplete;
    }
    LOBYTE(v49) = 1;
    if ( !DesignerInterop::GetDesignerMode(v49) )
    {
      DirectManipulationChanges = CCoreServices::GetDirectManipulationChanges(
                                    v7,
                                    &directManipulationViewports,
                                    (unsigned int *)&directManipulationViewportsChanged);
      v23 = DirectManipulationChanges;
      if ( DirectManipulationChanges < 0 )
      {
        OnFailure_2990_(DirectManipulationChanges);
        m_StartOffset = directManipulationViewports.m_StartOffset;
        m_actualSize = directManipulationViewports.m_actualSize;
        m_count = directManipulationViewports.m_count;
        m_data = directManipulationViewports.m_data;
        goto LABEL_316;
      }
      m_StartOffset = directManipulationViewports.m_StartOffset;
      m_actualSize = directManipulationViewports.m_actualSize;
      m_count = directManipulationViewports.m_count;
      m_data = directManipulationViewports.m_data;
    }
    v66 = pObject;
    CCoreServices::GetWindowSize(v7, pObject, v64, (XSIZE_LOGICAL *)&ppStowedExceptions);
    if ( v66 )
    {
      v67 = *((_DWORD *)v7 + 239);
      if ( (v67 & 5) != 0 )
      {
        if ( v7->m_uFrameNumber != 1 )
        {
          if ( (v67 & 1) != 0 && (Microsoft_Windows_XAMLEnableBits[0] & 2) != 0 )
          {
            pDesc.Ptr = (unsigned __int64)L"Zoom Scale Changed";
            memset(&pData, 0, sizeof(pData));
            *(_QWORD *)&pDesc.Size = 38;
            if ( McGenPreVista )
            {
              pData.GuidPtr = (unsigned __int64)&RecursiveInvalidateMeasureId;
              pData.UserTime = 1703936;
              LOWORD(pData.Version) = 1024;
              pData.Size = 64;
              TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, &pData);
            }
            else
            {
              PfnEventWrite(
                WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle,
                &RecursiveInvalidateMeasureInfo,
                1u,
                &pDesc);
            }
          }
          if ( (*((_BYTE *)v7 + 956) & 4) != 0 && (Microsoft_Windows_XAMLEnableBits[0] & 2) != 0 )
          {
            v314[0] = L"Locale Setting Changed";
            v313 = 0;
            traceSession._Ptr = 0;
            traceSession._Rep = 0;
            v312[0].ptr_ = 0;
            v312[1].ptr_ = 0;
            v314[1] = 46;
            if ( McGenPreVista )
            {
              v312[1].ptr_ = (FacadeReferenceWrapper *)&RecursiveInvalidateMeasureId;
              HIDWORD(v313) = 1703936;
              WORD2(traceSession._Ptr) = 1024;
              LOWORD(traceSession._Ptr) = 64;
              TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, (PEVENT_TRACE_HEADER)&traceSession);
            }
            else
            {
              PfnEventWrite(
                WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle,
                &RecursiveInvalidateMeasureInfo,
                1u,
                (_EVENT_DATA_DESCRIPTOR *)v314);
            }
          }
          v66->__vftable[1].HasInheritedProperties(v66);
        }
        *((_DWORD *)v7 + 239) &= 0xFFFFFFFA;
      }
      LayoutManagerForElement = VisualTree::GetLayoutManagerForElement(v66);
      v292 = LayoutManagerForElement;
      v70 = LayoutManagerForElement;
      if ( !LayoutManagerForElement )
      {
        v23 = -2147467261;
        v294 = -2147467261;
        OnNewFailure_1172_(v69);
        goto LABEL_534;
      }
      v71 = (unsigned int)ppStowedExceptions;
      v72 = HIDWORD(ppStowedExceptions);
      updated = CLayoutManager::UpdateLayout(
                  LayoutManagerForElement,
                  (unsigned int)ppStowedExceptions,
                  HIDWORD(ppStowedExceptions));
      v23 = updated;
      if ( updated < 0 )
        goto LABEL_162;
      if ( v7->m_fSurfaceContentsLostEnqueued )
        CCoreServices::HandleVirtualSurfaceImageSourceLostResources(v7);
      if ( gps.m_pTarget && _InterlockedCompareExchange(&v7->m_fSurfaceContentsLostEnqueued, 0, 1) == 1 )
      {
        if ( DXamlInstanceStorage::g_dwTlsIndex == -1 )
        {
          v74 = 0;
          OnNewFailure_2955_(-1);
        }
        else
        {
          v74 = (DirectUI::DXamlCore *)TlsGetValue(DXamlInstanceStorage::g_dwTlsIndex);
          if ( !v74 && GetLastError() )
            OnFailure_977_(v75);
        }
        DirectUI::DXamlCore::RaiseEvent(v74, 0, 0, ManagedEventSurfaceContentsLost);
      }
      updated = CCoreServices::VirtualSurfaceImageSourcePerFrameWork(v7, &windowBounds);
      v23 = updated;
      if ( updated < 0 )
        goto LABEL_162;
      m_pEventManager = v7->m_pEventManager;
      if ( m_pEventManager )
      {
        if ( m_pEventManager->m_fRaiseLoadedEventNeeded )
        {
          updated = CEventManager::RaiseLoadedEvent(m_pEventManager);
          v23 = updated;
          if ( updated < 0 )
            goto LABEL_162;
          updated = CLayoutManager::UpdateLayout(v70, v71, v72);
          v23 = updated;
          if ( updated < 0 )
            goto LABEL_162;
        }
      }
      if ( v7->m_fWantsRenderingEvent )
      {
        v77 = v7->m_pTimeManager;
        if ( v77 )
        {
          updated = CCoreServices::CallPerFrameCallback(v7, v77->m_rLastTickTime);
          v23 = updated;
          if ( updated < 0 )
            goto LABEL_162;
          updated = CLayoutManager::UpdateLayout(v70, v71, v72);
          v23 = updated;
          if ( updated < 0 )
            goto LABEL_162;
        }
      }
      v78 = 0;
      newAnimationsCheckForAnimationComplete = 0;
      ppStowedExceptions = 0;
      v292->m_allowTransitionsToRun = 0;
      Current = DirectUI::DXamlCore::GetCurrent();
      BuildTreeService = DirectUI::DXamlCore::GetBuildTreeService(
                           Current,
                           (ctl::ComPtr<DirectUI::BuildTreeService> *)&ppStowedExceptions);
      v81 = ppStowedExceptions;
      v23 = BuildTreeService;
      if ( BuildTreeService < 0
        || (BuildTreeService = DirectUI::BuildTreeService::BuildTrees(
                                 (DirectUI::BuildTreeService *)ppStowedExceptions,
                                 &newAnimationsCheckForAnimationComplete),
            v23 = BuildTreeService,
            BuildTreeService < 0) )
      {
        OnFailure_2990_(BuildTreeService);
      }
      else
      {
        v78 = newAnimationsCheckForAnimationComplete;
      }
      if ( v81 )
        ((void (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **))(*v81)->ExceptionAddress)(v81);
      if ( v23 < 0 )
        goto LABEL_233;
      if ( v78 )
      {
        v82 = (__int64)v7->m_pBrowserHost->GetFrameScheduler(v7->m_pBrowserHost);
        if ( v82 )
        {
          v63 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v82 + 16LL))(v82, 0, 0x2000000);
          v23 = v63;
          if ( v63 < 0 )
            goto LABEL_478;
        }
      }
      v70 = v292;
      updated = CLayoutManager::UpdateLayout(v292, v71, v72);
      v23 = updated;
      if ( updated < 0 )
        goto LABEL_162;
      v83 = v294;
      v70->m_allowTransitionsToRun = 1;
      if ( v83 )
      {
        m_pPendingListNoRef = v7->m_pRenderTargetBitmapManager->m_pPendingListNoRef;
        if ( m_pPendingListNoRef )
        {
          m_pHead = m_pPendingListNoRef->m_pHead;
          if ( m_pHead )
          {
            while ( 1 )
            {
              m_pNext = m_pHead->m_pNext;
              v87 = m_pHead->m_pData->GetRenderTargetElementData(m_pHead->m_pData);
              v88 = CRenderTargetElementData::UpdateMetrics(v87);
              v23 = v88;
              if ( v88 < 0 )
                break;
              m_pHead = m_pNext;
              if ( !m_pNext )
                goto LABEL_161;
            }
            OnFailure_2990_(v88);
            OnFailure_2990_(v23);
            goto LABEL_317;
          }
        }
LABEL_161:
        updated = CLayoutManager::UpdateLayout(v70, v71, v72);
        v23 = updated;
        if ( updated < 0 )
          goto LABEL_162;
      }
      Mylast = v7->m_contentRootCoordinator.m_contentRoots._Mypair._Myval2._Mylast;
      for ( n = v7->m_contentRootCoordinator.m_contentRoots._Mypair._Myval2._Myfirst; n != Mylast; ++n )
        CFocusManager::UpdateFocusRect(&n->m_ptr->m_focusManager, (const DirectUI::FocusNavigationDirection)6, 0);
      v70 = v292;
      updated = CLayoutManager::RealizeRegisteredLayoutTransitions(v292);
      v23 = updated;
      if ( updated < 0 )
        goto LABEL_162;
      DCompTreeHost::UpdateImplicitShowHideAnimations(m_pDCompTreeHost);
      updated = CLayoutManager::UpdateLayout(v70, v71, v72);
      v23 = updated;
      if ( updated < 0 )
        goto LABEL_162;
      m_pVisualTree = v70->m_pVisualTree;
      if ( m_pVisualTree )
      {
        v92 = m_pVisualTree->m_rootVisual.m_ptr;
        if ( v92 )
        {
          m_arrangeRect = (std::shared_ptr<Instrumentation::XamlTraceSession>)v70->m_arrangeRect;
          v70->m_isInLayoutTransitionPhase = 1;
          traceSession = m_arrangeRect;
          v94 = CUIElement::TransitionLayout(v92, v92, (XRECTF_WH *)&traceSession);
          v23 = v94;
          if ( v94 < 0 )
            OnFailure_2990_(v94);
          v70->m_isInLayoutTransitionPhase = 0;
          if ( v23 < 0 )
          {
            OnFailure_2990_(v23);
            goto LABEL_317;
          }
        }
      }
      v95 = *((_WORD *)v70 + 82);
      if ( v95 == -1 )
        v96 = 2;
      else
        v96 = v95 + 1;
      *((_WORD *)v70 + 82) = v96;
      if ( !v83 )
      {
LABEL_209:
        v115 = v305;
        if ( v305 )
        {
          if ( !v7->m_isSuspended )
          {
            m_pBrowserHost = v7->m_pBrowserHost;
            newAnimationsCheckForAnimationComplete = 0;
            newAnimationsHasActiveFiniteAnimations[0] = 0;
            v117 = m_pBrowserHost->GetFrameScheduler(m_pBrowserHost);
            v118 = v7->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost;
            updated = CTimeManager::Tick(
                        v115,
                        DesignerMode,
                        1u,
                        1u,
                        v118->m_spMainDevice.ptr_,
                        v118->m_spCompositor.ptr_,
                        v117,
                        0,
                        &newAnimationsCheckForAnimationComplete,
                        newAnimationsHasActiveFiniteAnimations);
            v23 = updated;
            if ( updated < 0 )
            {
LABEL_162:
              OnFailure_2990_(updated);
LABEL_317:
              v8 = v290;
              goto $Cleanup_1273;
            }
            v291 |= newAnimationsCheckForAnimationComplete;
            v287 |= newAnimationsHasActiveFiniteAnimations[0];
          }
          ptr = (FacadeReferenceWrapper *)v7->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost->m_spMainDevice.ptr_;
          if ( !DCompTreeHost::ContainerVisualsEnabled() )
          {
            v312[0].ptr_ = 0;
            v312[1].ptr_ = ptr;
            traceSession = 0;
            Microsoft::WRL::ComPtr<FacadeReferenceWrapper>::InternalAddRef(&v312[1]);
            Myhead = v115->m_translatesWithEndingAnimations._List._Mypair._Myval2._Myhead;
            for ( ii = Myhead->_Next; ii != Myhead; ii = ii->_Next )
            {
              v122 = ii->_Myval.m_ptr;
              if ( v122 )
              {
                CDependencyObject::AddRef(v122);
                CTranslateTransform::MakeDCompTransform(v122, (DCompTransformConversionContext *)&traceSession);
                CDependencyObject::Release(v122);
              }
              else
              {
                CTranslateTransform::MakeDCompTransform(0, (DCompTransformConversionContext *)&traceSession);
              }
            }
            std::_Hash<std::_Uset_traits<xref_ptr<CTranslateTransform>,std::_Uhash_compare<xref_ptr<CTranslateTransform>,std::hash<xref_ptr<CTranslateTransform>>,std::equal_to<xref_ptr<CTranslateTransform>>>,std::allocator<xref_ptr<CTranslateTransform>>,0>>::clear(&v115->m_translatesWithEndingAnimations);
            v124 = v312[1].ptr_;
            if ( v312[1].ptr_ )
            {
              v312[1].ptr_ = 0;
              v124->Release(v124);
            }
            v125 = traceSession._Ptr;
            if ( traceSession._Ptr )
            {
              v126 = 8 * (((char *)v312[0].ptr_ - (char *)traceSession._Ptr) >> 3);
              if ( v126 >= 0x1000 )
              {
                if ( (unsigned __int64)traceSession._Ptr
                   - *(_QWORD *)&traceSession._Ptr[-1].m_mutex._Mtx_storage._Thread_id
                   - 8 > 0x1F )
                  __fastfail(5u);
                v126 += 39LL;
                v125 = *(Instrumentation::XamlTraceSession **)&traceSession._Ptr[-1].m_mutex._Mtx_storage._Thread_id;
              }
              operator delete(v125, v126);
            }
          }
        }
        v127 = v7->m_inputServices.m_ptr;
        if ( v127 )
        {
          KeyTipManager = CInputServices::GetKeyTipManager(v127);
          v130 = v287;
          if ( KeyTipManager->m_finiteAnimationIsRunning != v287 )
          {
            KeyTipManager->m_finiteAnimationIsRunning = v287;
            if ( !v130 && KeyTipManager->m_state[0] == 3 )
            {
              LOBYTE(v129) = 4;
              KeyTipManager::GoToState(KeyTipManager, v7, v129);
            }
          }
        }
        if ( v7->m_pHostSite->IsWindowDestroyed(v7->m_pHostSite) )
        {
          if ( !v83 )
          {
            v238 = v115;
            goto LABEL_487;
          }
          v8 = v290;
LABEL_481:
          v228 = CCoreServices::FlushImageDecodeRequests(v7);
          v23 = v228;
          if ( v228 < 0 )
            goto LABEL_483;
          v228 = CCoreServices::ProcessTrackedImages(v7);
          v23 = v228;
          if ( v228 < 0 )
            goto LABEL_483;
          v238 = v305;
LABEL_487:
          pppStowedExceptions = 0;
          v239 = DirectUI::DXamlCore::GetCurrent();
          BudgetManager = DirectUI::DXamlCore::GetBudgetManager(
                            v239,
                            (ctl::ComPtr<DirectUI::BudgetManager> *)&pppStowedExceptions);
          v241 = pppStowedExceptions;
          v23 = BudgetManager;
          v294 = BudgetManager;
          if ( BudgetManager < 0 )
          {
            OnFailure_2990_(BudgetManager);
          }
          else
          {
            QueryPerformanceCounter((LARGE_INTEGER *)pppStowedExceptions + 13);
            v23 = 0;
            v294 = 0;
          }
          if ( v241 )
            ((void (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **))(*v241)->ExceptionAddress)(v241);
          if ( v23 >= 0 )
          {
            v242 = gps.m_pTarget->GetCPUMilliseconds(&gps.m_pTarget->IPALCoreServices);
            pNext = (CCoreServices *)v7->m_imageSurfaceWrapperCleanupList.head.pNext;
            v244 = 0;
            v245 = v242;
            if ( !v7->m_testOverrideImageSurfaceWrapperReleaseDelay )
              v244 = 1000;
            HIDWORD(traceSession._Rep) = 0;
            while ( 1 )
            {
              HIDWORD(traceSession._Rep) = 0;
              if ( pNext == (CCoreServices *)&v7->m_imageSurfaceWrapperCleanupList.tail )
                break;
              v246 = pNext;
              pNext = (CCoreServices *)pNext->IParserCoreServices::__vftable;
              p_Myend = (ImageSurfaceWrapper *)&v246[-1].m_appliedStyleTables.m_data.m_vector._Mypair._Myval2._Myend;
              if ( v244 + p_Myend->m_deviceCleanupTimestamp < v245 )
                ImageSurfaceWrapper::CleanupDeviceRelatedResources(p_Myend);
            }
            v7 = core;
            if ( !v238 || !v291 )
              goto LABEL_514;
            v248 = v287;
            if ( (*((_BYTE *)v238 + 96) & 0x20) != 0 )
            {
              if ( v287 )
                goto LABEL_513;
              v249 = v238->m_sharedState.m_ptr;
              m_coreServices = v249->m_value.m_coreServices;
              m_pHasAnimationsEvent = v249->m_value.m_coreServices->m_pHasAnimationsEvent;
              if ( m_pHasAnimationsEvent )
              {
                v252 = m_pHasAnimationsEvent->Reset(m_pHasAnimationsEvent);
                v253 = v252;
                if ( v252 < 0 )
                {
                  OnFailure_2990_(v252);
                  OnFailure_2990_(v253);
                  pppStowedExceptions = 0;
                  cStowedExceptions = 0;
                  TraceForFailFast(v253);
                  GetStowedExceptionsForFailFast(&pppStowedExceptions, &cStowedExceptions);
                  RoFailFastWithErrorContextInternal2(v253, cStowedExceptions, pppStowedExceptions);
                }
              }
              m_pAnimationsCompleteEvent = m_coreServices->m_pAnimationsCompleteEvent;
              if ( !m_pAnimationsCompleteEvent )
                goto LABEL_513;
              v255 = m_pAnimationsCompleteEvent->Set(m_pAnimationsCompleteEvent);
              v256 = v255;
              if ( v255 >= 0 )
                goto LABEL_513;
            }
            else
            {
              if ( !v287 )
                goto LABEL_513;
              v257 = v238->m_sharedState.m_ptr->m_value.m_coreServices->m_pHasAnimationsEvent;
              if ( !v257 )
                goto LABEL_513;
              v255 = v257->Set(v257);
              v256 = v255;
              if ( v255 >= 0 )
                goto LABEL_513;
            }
            OnFailure_2990_(v255);
            OnFailure_2990_(v256);
            pppStowedExceptions = 0;
            cStowedExceptions = 0;
            TraceForFailFast(v256);
            GetStowedExceptionsForFailFast(&pppStowedExceptions, &cStowedExceptions);
            RoFailFastWithErrorContextInternal2(v256, cStowedExceptions, pppStowedExceptions);
LABEL_513:
            *((_DWORD *)v238 + 24) ^= (*((_DWORD *)v238 + 24) ^ (32 * v248)) & 0x20;
LABEL_514:
            if ( v7->m_isFrameAfterVisualTreeReset )
            {
              v258 = CCoreServices::SetRootVisualResetEventSignaledStatus(v7, 1u);
              v259 = v258;
              if ( v258 < 0 )
              {
                OnFailure_2990_(v258);
                pppStowedExceptions = 0;
                cStowedExceptions = 0;
                TraceForFailFast(v259);
                GetStowedExceptionsForFailFast(&pppStowedExceptions, &cStowedExceptions);
                RoFailFastWithErrorContextInternal2(v259, cStowedExceptions, pppStowedExceptions);
              }
              v7->m_isFrameAfterVisualTreeReset = 0;
            }
            if ( v7->m_replayPointerUpdateAfterTick )
            {
              v260 = gps.m_pTarget->GetCPUMilliseconds(&gps.m_pTarget->IPALCoreServices);
              v261 = v260 - v7->m_lastPointerReplayTime;
              v262 = v260;
              v263 = v7->m_pBrowserHost->__vftable;
              if ( v261 < 0x1F4 )
              {
                v264 = ((__int64 (*)(void))v263->GetFrameScheduler)();
                (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v264 + 16LL))(
                  v264,
                  (unsigned int)(500 - v261),
                  0x40000000);
              }
              else
              {
                ((void (*)(void))v263->RequestReplayPreviousPointerUpdate)();
                v7->m_lastPointerReplayTime = v262;
                v7->m_replayPointerUpdateAfterTick = 0;
              }
            }
            goto LABEL_532;
          }
LABEL_233:
          OnFailure_2990_(v23);
          goto LABEL_316;
        }
        v131 = v7->m_rgpChildrenForUpdate.m_count;
        v132 = 0;
        v133 = 0;
        while ( 1 )
        {
          v23 = v132;
          if ( v133 == v131 )
            break;
          v134 = v7->m_rgpChildrenForUpdate.m_StartOffset;
          if ( v134 )
          {
            v136 = v7->m_rgpChildrenForUpdate.m_actualSize;
            v135 = v133 + v134;
            if ( v135 >= v136 )
              v135 -= v136;
          }
          else
          {
            v135 = v133;
          }
          v137 = *(_QWORD *)&v7->m_rgpChildrenForUpdate.m_data[8 * v135];
          v138 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 168LL))(v137);
          v132 = v138;
          if ( v138 < 0 )
          {
            OnFailure_2990_(v138);
            v23 = v132;
LABEL_263:
            OnFailure_2990_(v132);
            goto LABEL_316;
          }
          if ( v133 < v7->m_rgpChildrenForUpdate.m_count )
            ++v133;
        }
        if ( v132 < 0 )
          goto LABEL_263;
        m_pComponentHostManager = v7->m_pComponentHostManager;
        if ( m_pComponentHostManager )
        {
          v63 = m_pComponentHostManager->Tick(m_pComponentHostManager);
          v23 = v63;
          if ( v63 < 0 )
            goto LABEL_478;
        }
        v140 = v290;
        if ( !v83 )
          goto LABEL_292;
        v141 = WindowsGraphicsDeviceManager::WaitForD3DDependentResourceCreation(v290->m_graphicsDeviceManager.m_ptr);
        v23 = v141;
        if ( v141 < 0 )
        {
          OnFailure_2990_(v141);
          v70 = v292;
          v8 = v140;
          goto $Cleanup_1273;
        }
        p_m_deviceLostWaiter = &v7->m_deviceLostWaiter;
        if ( v7->m_deviceLostWaiter.m_ptr )
        {
LABEL_292:
          m_initializationType = v7->m_initializationType;
          if ( m_initializationType == 4 || m_initializationType == 7 )
          {
            v173 = m_pDCompTreeHost;
            v63 = DCompTreeHost::UpdateExplicitAtlasHint(m_pDCompTreeHost);
            v23 = v63;
            if ( v63 < 0 )
              goto LABEL_478;
          }
          else
          {
            if ( v83 )
            {
              v162 = (ImageSharingEngineHost::ImageSharingState *)v140->m_presentTarget.m_ptr;
              if ( v162 )
              {
                _InterlockedIncrement(&v162->m_nRefCount);
                v163 = *(HWND__ **)&v162[2].m_nRefCount;
                IsComponent = HostingUtility::IsComponent(0);
                if ( v163 )
                {
                  v165 = m_pDCompTreeHost;
                  if ( !m_pDCompTreeHost->m_targetHwnd )
                  {
                    m_pDCompTreeHost->m_targetHwnd = v163;
                    if ( IsSetStatusBarOpacityPresent() && (unsigned int)XamlBehaviorEnabled(1003) == 1 )
                    {
                      CurrentProcessId = GetCurrentProcessId();
                      RegisterNavigationWindowHandle(v165->m_targetHwnd, CurrentProcessId);
                    }
                    if ( !IsComponent )
                    {
                      LOBYTE(v166) = 2;
                      if ( !DesignerInterop::GetDesignerMode(v166)
                        && !XamlOneCoreTransforms::IsEnabled()
                        && !v165->m_visualTreeCompIslandAdapter._Mypair._Myval2 )
                      {
                        XamlOneCoreTransforms::FailFastIfEnabled();
                        v168 = v165->m_spMainDevice.ptr_->CreateTargetForHwnd(
                                 v165->m_spMainDevice.ptr_,
                                 v165->m_targetHwnd,
                                 0,
                                 &v165->m_pTargetForHwnd);
                        v23 = v168;
                        if ( v168 < 0 )
                          goto LABEL_331;
                      }
                    }
                    v168 = DCompTreeHost::SetTargetHelper(v165);
                    v23 = v168;
                    if ( v168 < 0 )
                      goto LABEL_331;
                    v171 = v165->m_systemBackdropBrush.ptr_;
                    if ( v171 )
                    {
                      v168 = DCompTreeHost::SetSystemBackdropBrush(v165, v171);
                      v23 = v168;
                      if ( v168 < 0 )
                      {
LABEL_331:
                        OnFailure_2990_(v168);
                        OnFailure_2990_(v23);
                        if ( _InterlockedExchangeAdd(&v162->m_nRefCount, 0xFFFFFFFF) == 1 )
                          ((void (__fastcall *)(ImageSharingEngineHost::ImageSharingState *, __int64))v162->~ImageSharingEngineHost::ImageSharingState)(
                            v162,
                            1);
                        goto LABEL_316;
                      }
                      v172 = v165->m_systemBackdropBrush.ptr_;
                      if ( v172 )
                      {
                        v165->m_systemBackdropBrush.ptr_ = 0;
                        v172->Release(v172);
                      }
                    }
                  }
                  v168 = DCompTreeHost::UpdateAtlasHint(v165);
                  v23 = v168;
                  if ( v168 < 0 )
                    goto LABEL_331;
                }
                CXcpObjectBaseInternal<IObject,CXcpObjectThreadSafeAddRefPolicy>::InternalRelease(v162);
              }
              else
              {
                HostingUtility::IsComponent(0);
              }
            }
            v173 = m_pDCompTreeHost;
          }
          if ( v115 )
          {
            v63 = CTimeManager::UpdateIATargets(v115);
            v23 = v63;
            if ( v63 < 0 )
              goto LABEL_478;
          }
          if ( v83 )
          {
            v174 = forceRedraw || (*((_BYTE *)v7 + 956) & 2) != 0;
            v175 = v7->m_connectedAnimationService.m_ptr;
            if ( v175 )
            {
              p_m_ptr = &v175->m_animations._Mypair._Myval2._Myfirst->m_ptr;
              v177 = 0;
              v178 = v175->m_animations._Mypair._Myval2._Mylast;
              if ( p_m_ptr != (CConnectedAnimation **)v178 )
              {
                do
                {
                  v179 = *p_m_ptr;
                  v180 = 0;
                  if ( (*p_m_ptr)->m_state == Deinitializing )
                  {
                    v181 = gps.m_pTarget->GetCPUMilliseconds(&gps.m_pTarget->IPALCoreServices);
                    m_preparedTimestamp = v179->m_preparedTimestamp;
                    if ( v181 - m_preparedTimestamp < 0x7D0 )
                    {
                      v180 = m_preparedTimestamp - v181 + 2000;
                    }
                    else
                    {
                      v183 = CConnectedAnimation::Cancel(v179);
                      v23 = v183;
                      if ( v183 < 0 )
                      {
                        OnFailure_2990_(v183);
                        OnFailure_2990_(v23);
                        OnFailure_2990_(v23);
                        goto LABEL_315;
                      }
                    }
                  }
                  if ( v180 )
                  {
                    if ( v177 )
                    {
                      if ( v180 < v177 )
                        v177 = v180;
                    }
                    else
                    {
                      v177 = v180;
                    }
                  }
                  ++p_m_ptr;
                }
                while ( p_m_ptr != (CConnectedAnimation **)v178 );
                if ( v177 )
                {
                  v184 = v175->m_sharedState.m_ptr->m_value.m_coreServices->m_pBrowserHost;
                  v185 = (__int64)v184->GetFrameScheduler(v184);
                  if ( v185 )
                  {
                    v186 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v185 + 16LL))(
                             v185,
                             (unsigned int)v177,
                             0x8000000);
                    v23 = v186;
                    if ( v186 < 0 )
                    {
                      OnFailure_2990_(v186);
                      OnFailure_2990_(v23);
                      goto LABEL_315;
                    }
                  }
                }
              }
            }
            v7 = core;
            if ( core->m_initializationType == 4
              || !pObject
              || !v174 && !CUIElement::NWNeedsRendering((CUIElement *)pObject) && !v7->m_renderStateChanged )
            {
              v191 = m_pDCompTreeHost;
              v209 = (CUIElement *)pObject;
              v207 = 0;
              v211 = (HWWalk *)pppStowedExceptions;
              goto LABEL_414;
            }
            if ( ContentRootInput::PointerInputProcessor::IsAutoReplayPointerEnabled() )
              v7->m_replayPointerUpdateAfterTick = 1;
            m_State = v7->m_State;
            if ( !m_State )
            {
LABEL_385:
              v191 = m_pDCompTreeHost;
              Myfirst = m_pDCompTreeHost->m_islandRenderData.m_data.m_vector._Mypair._Myval2._Myfirst;
              v193 = m_pDCompTreeHost->m_islandRenderData.m_data.m_vector._Mypair._Myval2._Mylast;
              while ( Myfirst != v193 )
              {
                first = Myfirst->first;
                if ( Myfirst->first->m_isContentRequested )
                {
                  p_second = (ImageSharingEngineHost::ImageSharingState **)&Myfirst->second;
                  if ( !Myfirst->second.windowsPresentTarget.m_ptr )
                  {
                    CXamlIslandRoot::GetSize(Myfirst->first);
                    v196 = *p_second;
                    if ( *p_second )
                    {
                      *p_second = 0;
                      CXcpObjectBaseInternal<IObject,CXcpObjectThreadSafeAddRefPolicy>::InternalRelease(v196);
                    }
                    v197 = first->m_sharedState.m_ptr->m_value.m_coreServices->m_pHostSite;
                    v198 = (__int64)v197->GetXcpDispatcher(v197);
                    Worker = WindowsPresentTarget::CreateWorker(
                               *(void **)(v198 + 112),
                               (int)*(float *)&ppStowedExceptions,
                               (int)*((float *)&ppStowedExceptions + 1),
                               0,
                               0,
                               &Myfirst->second.windowsPresentTarget.m_ptr);
                    v23 = Worker;
                    if ( Worker < 0 )
                    {
                      OnFailure_2990_(Worker);
                      OnFailure_2990_(v23);
                      goto LABEL_316;
                    }
                  }
                }
                ++Myfirst;
              }
              v200 = v7->m_connectedAnimationService.m_ptr;
              if ( v200 )
              {
                v201 = &v200->m_animations._Mypair._Myval2._Myfirst->m_ptr;
                v202 = &v200->m_animations._Mypair._Myval2._Mylast->m_ptr;
                if ( v201 != v202 )
                {
                  while ( 1 )
                  {
                    v203 = *v201;
                    if ( (*v201)->m_state == 8 )
                    {
                      v204 = CConnectedAnimation::TryToCompleteAnimation(*v201);
                      v23 = v204;
                      if ( v204 < 0 )
                        break;
                    }
                    if ( v203->m_state != (Idle|Initialized) )
                    {
                      v205 = v203->m_destination.element.m_ptr;
                      if ( v205 )
                      {
                        if ( !v205->m_pCompositionPeer || (v206 = CUIElement::NWNeedsRendering(v205)) != 0 )
                          LOBYTE(v206) = 1;
                        v203->m_destination.refreshSnapshot = v206;
                      }
                    }
                    if ( ++v201 == v202 )
                      goto LABEL_405;
                  }
                  OnFailure_2990_(v204);
                  OnFailure_2990_(v23);
                  OnFailure_2990_(v23);
                  goto LABEL_316;
                }
              }
LABEL_405:
              v207 = 1;
              v208 = CCoreServices::UIAClientsAreListening(v7, AEStructureChanged);
              v209 = (CUIElement *)pObject;
              v210 = v208;
              UserDataCount = v174;
              v211 = (HWWalk *)pppStowedExceptions;
              v212 = CCoreServices::RenderWalk(
                       v7,
                       (HWWalk *)pppStowedExceptions,
                       v290,
                       (CUIElement *)pObject,
                       UserDataCount,
                       cStowedExceptions,
                       DesignerMode,
                       v208 == 0);
              p_m_automationEventsHelper = &v7->m_automationEventsHelper;
              v23 = v212;
              if ( v210 )
                AutomationEventsHelper::CleanUpStructureChangedRequests(p_m_automationEventsHelper);
              else
                AutomationEventsHelper::RaiseStructureChangedEvents(p_m_automationEventsHelper);
              if ( v23 < 0 )
              {
                if ( GraphicsUtility::IsDeviceLostError(v23) )
                {
                  OnFailure_2990_(v214);
                  goto LABEL_316;
                }
                OnFailure_2990_(v214);
                ppStowedExceptions = 0;
                cStowedExceptions = 0;
                TraceForFailFast(v23);
                GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
                RoFailFastWithErrorContextInternal2(v23, cStowedExceptions, ppStowedExceptions);
              }
LABEL_414:
              m_pRenderTargetBitmapManager = v7->m_pRenderTargetBitmapManager;
              cStowedExceptions = 0;
              v63 = CRenderTargetBitmapManager::RenderElements(
                      m_pRenderTargetBitmapManager,
                      v211,
                      v290,
                      &cStowedExceptions);
              v23 = v63;
              if ( v63 < 0 )
                goto LABEL_478;
              v216 = v7->m_pendingImageUpdates._Mypair._Myval2._Mylast;
              for ( jj = v7->m_pendingImageUpdates._Mypair._Myval2._Myfirst; jj != v216; ++jj )
              {
                v218 = *jj;
                if ( (*jj)->m_isUpdateRequired )
                {
                  v219 = !v218->m_isReferencingCache
                      && !v218->m_pTiledSurface
                      && !v218->m_pImageSurfaceHardware
                      && !v218->m_pD2DBitmap;
                  v218->m_isUpdateRequired = v219;
                }
              }
              v220 = v7->m_pendingImageUpdates._Mypair._Myval2._Myfirst;
              if ( v220 != v7->m_pendingImageUpdates._Mypair._Myval2._Mylast )
                v7->m_pendingImageUpdates._Mypair._Myval2._Mylast = v220;
              v63 = HWTextureManager::SubmitTextureUpdates(v211->m_pTextureManager);
              v23 = v63;
              if ( v63 < 0 )
                goto LABEL_478;
              if ( v207
                || v305 && (*((_BYTE *)v305 + 96) & 0x10) != 0
                || cStowedExceptions
                || (v221 = *((_DWORD *)v7 + 239), (v221 & 8) != 0)
                || v7->m_fLayoutCompletedNeeded
                || (v221 & 0x10) != 0 )
              {
                *((_DWORD *)v7 + 239) &= ~0x10u;
                v222 = v46;
                if ( (v7->m_forceDisconnectRootOnSuspend || IsXamlBehaviorEnabledForCurrentSku(Suspend_DisconnectRoot))
                  && v191->m_pDisconnectedHwndRootVisual )
                {
                  if ( DCompTreeHost::SetRootForCorrectContext(v191, v191->m_pHWndRootVisual->m_pDCompositionVisual) < 0 )
                  {
                    pppStowedExceptions = 0;
                    cStowedExceptions = 0;
                    TraceForFailFast(-2147418113);
                    OnNewFailureEncountered(-2147418113, 0, 0);
                    GetStowedExceptionsForFailFast(&pppStowedExceptions, &cStowedExceptions);
                    RoFailFastWithErrorContextInternal2(-2147418113, cStowedExceptions, pppStowedExceptions);
                  }
                  m_pDisconnectedHwndRootVisual = v191->m_pDisconnectedHwndRootVisual;
                  if ( m_pDisconnectedHwndRootVisual )
                  {
                    ctl::implements<DCompHelpers::IDCompVisual>::Release(m_pDisconnectedHwndRootVisual);
                    v191->m_pDisconnectedHwndRootVisual = 0;
                  }
                }
                v224 = v7->m_contentRootCoordinator.m_contentRoots._Mypair._Myval2._Mylast;
                for ( kk = &v7->m_contentRootCoordinator.m_contentRoots._Mypair._Myval2._Myfirst->m_ptr;
                      kk != (CContentRoot **)v224;
                      ++kk )
                {
                  v226 = *kk;
                  if ( *kk )
                  {
                    m_ptr_as_int = 0;
                    if ( (v226->m_ref_count.m_ptr_as_int & 1) == 0 )
                      m_ptr_as_int = (volatile signed __int32 *)v226->m_ref_count.m_ptr_as_int;
                    if ( m_ptr_as_int )
                      _InterlockedIncrement(m_ptr_as_int);
                    else
                      v226->m_ref_count.m_count_and_flag = v226->m_ref_count.m_ptr_as_int + 2;
                  }
                  v226->m_inputManager.m_keyboardInputProcessor.m_cKeyDownCountBeforeSubmitFrame = 0;
                  CContentRoot::Release(v226);
                }
                if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x400) != 0 )
                  McTemplateMofU0(&WINDOWS_UI_XAML_ETW_PROVIDER_Context, &SubmitFrameBegin, &SubmitFrameId);
                v8 = v290;
                UserDataCounta = v46;
                v228 = CCoreServices::SubmitPrimitiveCompositionCommands(
                         v7,
                         v290,
                         v209,
                         v7->m_pPALClock.m_ptr,
                         UserDataCounta,
                         pDirtyRect,
                         DesignerMode,
                         tickOnlyTimers);
                v23 = v228;
                if ( v228 < 0 )
                  goto LABEL_483;
                if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x400) != 0 )
                  McTemplateMofU0(&WINDOWS_UI_XAML_ETW_PROVIDER_Context, &SubmitFrameEnd, &SubmitFrameId);
                v228 = DCompTreeHost::ConnectXamlIslandTargetRoots(v191);
                v23 = v228;
                if ( v228 < 0 )
                  goto LABEL_483;
                if ( v7->m_fWantsCompositionTargetRenderedEvent )
                {
                  v229 = v7->m_pPALClock.m_ptr->GetAbsoluteTimeInSeconds(v7->m_pPALClock.m_ptr);
                  v230 = (float)(v229 - v222) * 1000.0;
                  v231 = (CEventArgs *)operator new(0x18u);
                  v233 = v231;
                  if ( v231 )
                  {
                    v231->m_cRef = 1;
                    v231->__vftable = (CEventArgs_vtbl *)CRenderedEventArgs::`vftable';
                  }
                  else
                  {
                    v233 = 0;
                  }
                  v233[1].__vftable = (CEventArgs_vtbl *)(unsigned int)(int)(float)(v230 * 10000.0);
                  CFxCallbacks::JoltHelper_RaiseEvent(v232, 0, ManagedEventRendered, v233);
                  ppStowedExceptions = 0;
                  v234 = DirectUI::DXamlCore::GetCurrent();
                  RenderedEventSource = DirectUI::DXamlCore::GetRenderedEventSource(
                                          v234,
                                          (DirectUI::CEventSource<Windows::Foundation::IEventHandler<Windows::UI::Xaml::Media::RenderedEventArgs *>,IInspectable,Windows::UI::Xaml::Media::IRenderedEventArgs> **)&ppStowedExceptions);
                  v236 = RenderedEventSource;
                  if ( RenderedEventSource < 0 )
                  {
                    OnFailure_2990_(RenderedEventSource);
                    pppStowedExceptions = 0;
                    cStowedExceptions = 0;
                    TraceForFailFast(v236);
                    GetStowedExceptionsForFailFast(&pppStowedExceptions, &cStowedExceptions);
                    RoFailFastWithErrorContextInternal2(v236, cStowedExceptions, pppStowedExceptions);
                  }
                  v237 = ((char *)ppStowedExceptions[7] - (char *)ppStowedExceptions[6]) / 24;
                  if ( ppStowedExceptions )
                    ((void (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **))ppStowedExceptions[2]->ExceptionAddress)(ppStowedExceptions + 2);
                  if ( !(_DWORD)v237 )
                    v7->m_fWantsCompositionTargetRenderedEvent = 0;
                  CEventArgs::Release(v233);
                }
                *((_DWORD *)v7 + 239) &= 0xFFFFFFF5;
                v7->m_renderStateChanged = 0;
              }
              else
              {
                *((_DWORD *)v7 + 239) &= ~0x10u;
                v8 = v290;
              }
              v228 = CRenderTargetBitmapManager::DrawCompTrees(v7->m_pRenderTargetBitmapManager, v8);
              v23 = v228;
              if ( v228 < 0 )
              {
LABEL_483:
                OnFailure_2990_(v228);
                v70 = v292;
                goto $Cleanup_1273;
              }
              goto LABEL_481;
            }
            m_cTrackingInterval = (CFxCallbacks *)v7->m_cTrackingInterval;
            if ( (_DWORD)m_cTrackingInterval )
            {
              v7->m_cTrackingInterval = (_DWORD)m_cTrackingInterval - 1;
              goto LABEL_385;
            }
            if ( m_State == 2 )
            {
              v7->m_cTrackingInterval = 50;
              v7->m_cMaxAllowedMemoryincrease = 52428800;
              v7->m_State = 1;
              CFxCallbacks::JoltHelper_TriggerGCCollect(m_cTrackingInterval);
              goto LABEL_385;
            }
            if ( m_State != 1 )
              goto LABEL_385;
            v189 = 0;
            if ( gps.m_pTarget )
              v189 = gps.m_pTarget->GetMemoryCount(gps.m_pTarget);
            m_lPrvMemCount = v7->m_lPrvMemCount;
            if ( m_lPrvMemCount < v189 )
            {
              if ( v189 - m_lPrvMemCount <= v7->m_cMaxAllowedMemoryincrease )
              {
LABEL_384:
                v7->m_cTrackingInterval = 50;
                v7->m_cMaxAllowedMemoryincrease = 52428800;
                v7->m_State = 1;
                goto LABEL_385;
              }
              CFxCallbacks::JoltHelper_TriggerGCCollect((CFxCallbacks *)(v189 - m_lPrvMemCount));
            }
            v7->m_lPrvMemCount = v189;
            goto LABEL_384;
          }
          v238 = v305;
          if ( !v305 )
            goto LABEL_487;
          if ( v305->m_targetDOs._Mypair._Myval2._Myfirst == v305->m_targetDOs._Mypair._Myval2._Mylast )
            goto LABEL_487;
          CTimeManager::UpdateTargetDOs(
            v305,
            v7->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost->m_spCompositor.ptr_);
          v63 = DCompTreeHost::CommitMainDevice(v173, 0);
          v23 = v63;
          if ( v63 >= 0 )
            goto LABEL_487;
LABEL_478:
          OnFailure_2990_(v63);
          goto LABEL_316;
        }
        v143 = &v7->m_deviceLostEvent.m_ptr;
        EventW = CreateEventW(0, 0, 0, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v7->m_deviceLostEvent,
          EventW);
        if ( (((unsigned __int64)v7->m_deviceLostEvent.m_ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          LastError = GetLastError();
          v146 = LastError;
          if ( LastError > 0 )
            v146 = (unsigned __int16)LastError | 0x80070000;
          if ( v146 < 0 )
          {
            OnFailure_2990_(v146);
            ppStowedExceptions = 0;
            pCanPickupForRender = 0;
            TraceForFailFast(v146);
            GetStowedExceptionsForFailFast(&ppStowedExceptions, &pCanPickupForRender);
            RoFailFastWithErrorContextInternal2(v146, pCanPickupForRender, ppStowedExceptions);
          }
        }
        v147 = *v143;
        LOBYTE(ppStowedExceptions) = 0;
        lpCriticalSection = 0;
        v148 = core->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr->m_cachedD3DDevice.m_ptr;
        v149 = CD3D11DeviceInstance::TakeLockAndCheckDeviceLost(
                 v148->m_deviceInstance._Ptr,
                 (CD3D11SharedDeviceGuard *)&ppStowedExceptions);
        v23 = v149;
        if ( v149 < 0 )
        {
          OnFailure_2990_(v149);
          if ( (_BYTE)ppStowedExceptions )
          {
            v170 = lpCriticalSection;
            goto LABEL_313;
          }
        }
        else
        {
          p_m_cs = &v148->m_deviceInstance._Ptr->m_lock.m_cs;
          v151 = 0;
          v152 = (char)ppStowedExceptions;
          v153 = lpCriticalSection;
          directManipulationViewportsChanged = 0;
          if ( !(_BYTE)ppStowedExceptions || lpCriticalSection != p_m_cs )
          {
            ppStowedExceptions = 0;
            pCanPickupForRender = 0;
            TraceForFailFast(-2147418113);
            OnNewFailureEncountered(-2147418113, 0, 0);
            GetStowedExceptionsForFailFast(&ppStowedExceptions, &pCanPickupForRender);
            RoFailFastWithErrorContextInternal2(-2147418113, pCanPickupForRender, ppStowedExceptions);
            v151 = directManipulationViewportsChanged;
          }
          OwningThread = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))p_m_cs[3].OwningThread;
          v155 = **OwningThread;
          if ( v151 )
          {
            directManipulationViewportsChanged = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v151 + 16LL))(v151);
          }
          v155(OwningThread, &GUID_8992ab71_02e6_4b8d_ba48_b056dcda42c4, &directManipulationViewportsChanged);
          v156 = (*(__int64 (__fastcall **)(__int64, HANDLE, unsigned int *))(*(_QWORD *)directManipulationViewportsChanged
                                                                            + 520LL))(
                   directManipulationViewportsChanged,
                   v147,
                   &core->m_deviceLostEventCookie);
          v23 = v156;
          if ( v156 >= 0 )
          {
            v157 = directManipulationViewportsChanged;
            if ( directManipulationViewportsChanged )
            {
              directManipulationViewportsChanged = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
            }
            if ( v152 )
              LeaveCriticalSection(v153);
            v7 = core;
            ThreadpoolWait = CreateThreadpoolWait(
                               lambda_abc5ad4fd539e516af6fd1c2368dec67_::_lambda_invoker_cdecl_,
                               core,
                               0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
              p_m_deviceLostWaiter,
              ThreadpoolWait);
            if ( !p_m_deviceLostWaiter->m_ptr )
            {
              v159 = GetLastError();
              v160 = v159;
              if ( v159 > 0 )
                v160 = (unsigned __int16)v159 | 0x80070000;
              if ( v160 < 0 )
              {
                OnFailure_2990_(v160);
                ppStowedExceptions = 0;
                pCanPickupForRender = 0;
                TraceForFailFast(v160);
                GetStowedExceptionsForFailFast(&ppStowedExceptions, &pCanPickupForRender);
                RoFailFastWithErrorContextInternal2(v160, pCanPickupForRender, ppStowedExceptions);
              }
            }
            SetThreadpoolWait(p_m_deviceLostWaiter->m_ptr, *v143, 0);
            v83 = v294;
            v115 = v305;
            v140 = v290;
            goto LABEL_292;
          }
          OnFailure_2990_(v156);
          v169 = directManipulationViewportsChanged;
          if ( directManipulationViewportsChanged )
          {
            directManipulationViewportsChanged = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v169 + 16LL))(v169);
          }
          if ( v152 )
          {
            v170 = v153;
LABEL_313:
            LeaveCriticalSection(v170);
          }
        }
        OnFailure_2990_(v23);
        OnFailure_2990_(v23);
LABEL_315:
        v7 = core;
        goto LABEL_316;
      }
      v97 = v7->m_pRenderTargetBitmapManager;
      v98 = 1;
      m_pCoreNoRef = v97->m_pCoreNoRef;
      m_pDeploymentTree = m_pCoreNoRef->m_pDeploymentTree;
      if ( m_pDeploymentTree )
      {
        m_pApplication = m_pDeploymentTree->m_pApplication;
        if ( m_pApplication )
          v98 = m_pApplication->m_fRootVisualSet == 0;
      }
      if ( m_pCoreNoRef->m_initializationType != 4 || !m_pCoreNoRef->m_cPendingDecodes )
      {
        if ( v98 )
        {
          v102 = v97->m_pPendingListNoRef;
          if ( v102 )
          {
            v103 = v102->m_pHead;
            if ( v103 )
            {
              while ( 1 )
              {
                m_pData = v103->m_pData;
                v105 = v103->m_pNext;
                m_pRenderElement = v103->m_pData->GetRenderTargetElementData(v103->m_pData)->m_pRenderElement;
                if ( (m_pRenderElement->IsActive(m_pRenderElement)
                   || CDependencyObject::OfTypeByIndex<779>(m_pRenderElement))
                  && !CDependencyObject::OfTypeByIndex<776>(m_pRenderElement) )
                {
                  m_pMainVisualTree = v97->m_pCoreNoRef->m_pMainVisualTree;
                  if ( m_pMainVisualTree )
                    v108 = m_pMainVisualTree->m_rootVisual.m_ptr;
                  else
                    v108 = 0;
                  while ( 1 )
                  {
                    v109 = (m_pRenderElement->m_bitFields.m_bitFieldsAsDWORD & 0x200000) != 0
                         ? 0LL
                         : m_pRenderElement->m_pParent;
                    if ( (*((_BYTE *)m_pRenderElement + 140) & 2) != 0 )
                      break;
                    v110 = m_pRenderElement->GetTypeIndex(m_pRenderElement);
                    if ( v110 == RootVisual
                      || (unsigned __int16)v110 >= (XYFocusNavigationStrategy|IVectorOfUri)
                      && (ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(v110),
                          DirectUI::MetadataAPI::CompareCustomTypesHelper(ClassInfoByIndex, RootVisual)) )
                    {
                      if ( m_pRenderElement != v108 )
                        break;
                    }
                    if ( !CRenderTargetBitmap::IsAncestorTypeEligible(m_pRenderElement) )
                      break;
                    if ( v109 )
                    {
                      v112 = v109->GetTypeIndex(v109);
                      if ( v112 != UIElement )
                      {
                        if ( (unsigned __int16)v112 >= (XYFocusNavigationStrategy|IVectorOfUri) )
                        {
                          v123 = DirectUI::MetadataAPI::GetClassInfoByIndex(v112);
                          if ( !DirectUI::MetadataAPI::CompareCustomTypesHelper(v123, UIElement) )
                            break;
                        }
                        else if ( LOBYTE(c_aTypeCheckData[(unsigned __int16)v112].m_handle) != 103 )
                        {
                          break;
                        }
                      }
                    }
                    pCanPickupForRender = 0;
                    if ( IsSetStatusBarOpacityPresent()
                      && (unsigned int)XamlBehaviorEnabled(22) == 1
                      && CQuirksMode2::XamlQuirkIsEnabled(0x20040u)
                      && DirectUI::CommandBar::CanPickupForRTBRender(v109, &pCanPickupForRender) >= 0
                      && pCanPickupForRender
                      || !v109 )
                    {
                      v113 = m_pData->SetCurrentState(m_pData, Initialized);
                      v114 = v113;
                      if ( v113 >= 0 )
                        goto LABEL_206;
                      goto LABEL_228;
                    }
                    m_pRenderElement = (CUIElement *)v109;
                  }
                }
                v113 = m_pData->FailRender(m_pData, 2147942487LL);
                v114 = v113;
                if ( v113 < 0 )
                  break;
LABEL_206:
                v103 = v105;
                if ( !v105 )
                  goto LABEL_207;
              }
LABEL_228:
              OnFailure_2990_(v113);
              v23 = v114;
              OnFailure_2990_(v114);
              goto LABEL_316;
            }
          }
        }
      }
    }
    else
    {
LABEL_207:
      v70 = v292;
    }
    v83 = v294;
    goto LABEL_209;
  }
  OnFailure_2990_(v23);
  v70 = v292;
$Cleanup_1273:
  if ( v23 == -2005270523 )
    goto LABEL_526;
  v292 = v70;
  if ( v23 == -2005270521 || v23 == -2003238900 || v23 == -2005270522 )
  {
    v292 = v70;
LABEL_526:
    v265 = v23;
    v266 = CompositorTreeHost::ProcessFrame(
             v8->m_pCompositorTreeHost,
             v8->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost,
             v42);
    v294 = v266;
    v23 = v266;
    if ( v266 >= 0 )
    {
      v23 = v265;
      v294 = v265;
    }
    else
    {
      OnNewFailure_3049_(v266);
      if ( g_dwErrorContextTlsIndex != -1 )
      {
        v267 = TlsGetValue(g_dwErrorContextTlsIndex);
        if ( v267 )
          v267[1048] |= 1u;
      }
      DisplayDebugMessage(
        DebugOutputOnly,
        Started,
        L"onecoreuap\\windows\\dxaml\\xcp\\core\\dll\\xcpcore.cpp",
        6805,
        v23,
        L"FlushCompositorCommandsOnDeviceLost(pRenderTarget)",
        0);
    }
    goto LABEL_532;
  }
  v294 = v23;
  if ( v23 == -2005270496 )
    goto LABEL_526;
LABEL_532:
  if ( v292 )
    v292->m_allowTransitionsToRun = 1;
LABEL_534:
  v7->m_pDrawReentrancyCheck = v7;
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x200) != 0 )
  {
    if ( pDirtyRect )
    {
      Height = pDirtyRect->Height;
      Width = pDirtyRect->Width;
      Y = pDirtyRect->Y;
      X = pDirtyRect->X;
    }
    else
    {
      Height = -1;
      X = -1;
      Width = -1;
      Y = -1;
    }
    cStowedExceptions = Width;
    LODWORD(directManipulationViewportsChanged) = X;
    pDesc.Ptr = (unsigned __int64)&directManipulationViewportsChanged;
    p_directManipulationViewportsChanged = &v299;
    p_cStowedExceptions = &cStowedExceptions;
    p_pCanPickupForRender = &pCanPickupForRender;
    pCanPickupForRender = Height;
    v299 = Y;
    memset(&pData, 0, sizeof(pData));
    *(_QWORD *)&pDesc.Size = 4;
    v318 = 4;
    v320 = 4;
    v322 = 4;
    if ( McGenPreVista )
    {
      pData.GuidPtr = (unsigned __int64)&FrameId;
      pData.Size = 112;
      pData.UserTime = 1703936;
      pData.Version = 1280;
      TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, &pData);
    }
    else
    {
      PfnEventWrite(WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle, &FrameInfo, 4u, &pDesc);
    }
  }
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 2) != 0 )
    McTemplateMofU0(&WINDOWS_UI_XAML_ETW_PROVIDER_Context, &FrameEnd, &FrameId);
  if ( v7->m_pendingFirstFrameTraceLoggingEvent )
  {
    Instrumentation::GetXamlTraceSession(&traceSession);
    if ( Tlgg_hTraceProviderProv.LevelPlus1
      && (Tlgg_hTraceProviderProv.KeywordAny & 0x400000000000LL) != 0
      && (Tlgg_hTraceProviderProv.KeywordAll & 0x400000000000LL) == Tlgg_hTraceProviderProv.KeywordAll )
    {
      pDirtyRect = (XRECT_WH *)0x1000000;
      LODWORD(directManipulationViewportsChanged) = GetCurrentProcessId();
      pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)Instrumentation::XamlTraceSession::GetAppId(traceSession._Ptr);
      ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)Instrumentation::XamlTraceSession::GetSessionId(traceSession._Ptr);
      v320 = 8;
      p_cStowedExceptions = &pDirtyRect;
      v318 = 4;
      p_directManipulationViewportsChanged = (unsigned int *)&directManipulationViewportsChanged;
      _tlgWrapSz<unsigned short>::Fill((_tlgWrapSz<unsigned short> *)&pppStowedExceptions, &pDesc);
      _tlgWrapSz<unsigned short>::Fill(
        (_tlgWrapSz<unsigned short> *)&ppStowedExceptions,
        (_EVENT_DATA_DESCRIPTOR *)(&pData.GuidPtr + 1));
      tlgWriteTransfer_EventWriteTransfer(
        &Tlgg_hTraceProviderProv,
        &tlgEvent_17._tlgChannel,
        0,
        0,
        6u,
        (_EVENT_DATA_DESCRIPTOR *)&pData);
    }
    Rep = traceSession._Rep;
    v7->m_pendingFirstFrameTraceLoggingEvent = 0;
    if ( Rep )
      std::_Ref_count_base::_Decref(Rep);
  }
  v273 = m_count;
  v274 = 0;
  v7->m_bVisibilityToggled = 0;
  if ( v273 )
  {
    v275 = m_StartOffset;
    v276 = m_data;
    do
    {
      if ( v275 )
      {
        v277 = v275 + v274 - m_actualSize;
        if ( v275 + v274 < m_actualSize )
          v277 = v275 + v274;
      }
      else
      {
        v277 = v274;
      }
      v278 = 8 * v277;
      v279 = *(_QWORD *)&v276[v278];
      v280 = (unsigned int)v278;
      if ( v279 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v279 + 8LL))(v279);
        *(_QWORD *)&v276[v280] = 0;
      }
      ++v274;
    }
    while ( v274 < v273 );
    v23 = v294;
  }
  _xvector_base<HWCompNode *>::clear((_xvector_base<SnapPointData> *)&directManipulationViewports);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1802223d0  push    rbp
0x1802223d2  push    rbx
0x1802223d3  push    rsi
0x1802223d4  push    rdi
0x1802223d5  push    r12
0x1802223d7  push    r13
0x1802223d9  push    r14
0x1802223db  push    r15
0x1802223dd  lea     rbp, [rsp-108h]
0x1802223e5  sub     rsp, 208h
0x1802223ec  mov     rax, cs:__security_cookie
0x1802223f3  xor     rax, rsp
0x1802223f6  mov     [rbp+140h+var_70], rax
0x1802223fd  mov     rax, [rbp+140h+arg_28]
0x180222404  xor     edi, edi
0x180222406  mov     [rbp+140h+pDirtyRect], rax
0x18022240a  mov     eax, edi
0x18022240c  mov     [rbp+140h+core], this
0x180222410  mov     r13, this
0x180222413  mov     [rbp+140h+var_178], eax
0x180222416  mov     ecx, edi
0x180222418  mov     [rbp+140h+directManipulationViewports.m_count], eax
0x18022241b  mov     r12, pRenderTarget
0x18022241e  mov     [rbp+140h+var_170], eax
0x180222421  mov     [rbp+140h+directManipulationViewports.m_actualSize], eax
0x180222424  mov     [rbp+140h+var_174], eax
0x180222427  mov     [rbp+140h+directManipulationViewports.m_StartOffset], eax
0x18022242a  mov     [rsp+240h+var_1D8], pRenderTarget
0x18022242f  mov     [rbp+140h+pppStowedExceptions], pHWWalk
0x180222433  mov     [rsp+240h+var_1C8], rdi
0x180222438  mov     [rbp+140h+var_138], this
0x18022243c  mov     [rbp+140h+directManipulationViewports.m_data], this
0x180222440  mov     dword ptr [rbp+140h+directManipulationViewportsChanged], edi
0x180222443  test    pVisualTree, pVisualTree
0x180222446  jz      short loc_180222452
0x180222448  mov     r14, [pVisualTree+28h]
0x18022244c  mov     [rbp+140h+pObject], r14
0x180222450  jmp     short loc_180222456
0x180222452  mov     [rbp+140h+pObject], rdi
0x180222456  mov     this, [pRenderTarget+28h]
0x18022245a  mov     [rbp+140h+ppStowedExceptions], rdi
0x18022245e  mov     qword ptr [rbp+140h+windowBounds.left], rax
0x180222462  test    this, this
0x180222465  jz      short loc_18022247C
0x180222467  mov     eax, [this+18h]
0x18022246a  xorps   xmm0, xmm0
0x18022246d  cvtsi2ss xmm0, rax
0x180222472  mov     eax, [this+1Ch]
0x180222475  movss   [rbp+140h+windowBounds.right], xmm0
0x18022247a  jmp     short loc_180222481
0x18022247c  mov     [rbp+140h+windowBounds.right], eax
0x18022247f  mov     eax, edi
0x180222481  mov     r15, [r13+0E0h]
0x180222488  xorps   xmm0, xmm0
0x18022248b  cvtsi2ss xmm0, rax
0x180222490  xor     al, al
0x180222492  mov     [rbp+140h+var_168], r15
0x180222496  mov     [rsp+240h+var_1D0], al
0x18022249a  mov     [rsp+240h+newAnimationsHasActiveFiniteAnimations], al
0x18022249e  mov     [rsp+240h+var_1E0], al
0x1802224a2  mov     [rsp+240h+newAnimationsCheckForAnimationComplete], al
0x1802224a6  movss   [rbp+140h+windowBounds.bottom], xmm0
0x1802224ab  cmp     [r13+3C4h], edi
0x1802224b2  jnz     short loc_1802224BD
0x1802224b4  cmp     [r13+6C0h], al
0x1802224bb  jz      short loc_1802224CD
0x1802224bd  mov     [rbp+140h+var_1B8], 1
0x1802224c4  cmp     [r13+3CCh], edi
0x1802224cb  jz      short loc_1802224D0
0x1802224cd  mov     [rbp+140h+var_1B8], edi
0x1802224d0  mov     rax, [pRenderTarget+20h]
0x1802224d4  mov     cl, 1; mode
0x1802224d6  mov     rax, [rax+58h]
0x1802224da  mov     [rbp+140h+var_188], rax
0x1802224de  call    ?GetDesignerMode@DesignerInterop@@SA_NW4DesignerMode@@@Z; DesignerInterop::GetDesignerMode(DesignerMode)
0x1802224e3  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits, 2
0x1802224ea  mov     [rsp+240h+var_1DF], al
0x1802224ee  lea     rax, FrameId
0x1802224f5  jz      short loc_18022255D
0x1802224f7  cmp     cs:McGenPreVista, dil
0x1802224fe  xorps   xmm0, xmm0
0x180222501  movups  xmmword ptr [rbp+140h+traceSession._Ptr], xmm0
0x180222505  movups  xmmword ptr [rbp+140h+var_110.ptr_], xmm0
0x180222509  movups  [rbp+140h+var_100], xmm0
0x18022250d  jnz     short loc_180222531
0x18022250f  mov     this, cs:WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle
0x180222516  lea     pHWWalk, FrameBegin
0x18022251d  mov     rax, cs:PfnEventWrite
0x180222524  xor     r9d, r9d
0x180222527  xor     r8d, r8d
0x18022252a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022252f  jmp     short loc_18022255D
0x180222531  mov     this, cs:WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger; TraceHandle
0x180222538  lea     pHWWalk, [rbp+140h+traceSession]; EventTrace
0x18022253c  mov     [rbp+140h+var_110.ptr_+8], rax
0x180222540  mov     eax, 30h ; '0'
0x180222545  mov     word ptr [rbp+140h+traceSession._Ptr], ax
0x180222549  mov     dword ptr [rbp+140h+var_100+0Ch], 1A0000h
0x180222550  mov     dword ptr [rbp+140h+traceSession._Ptr+4], 401h
0x180222557  call    cs:__imp_TraceEvent
0x18022255d  mov     ecx, cs:?g_dwTlsIndex@DXamlInstanceStorage@@3KA; failedFrameHR
0x180222563  mov     rbx, rdi
0x180222566  cmp     ecx, 0FFFFFFFFh
0x180222569  jz      short loc_18022258A
0x18022256b  call    cs:__imp_TlsGetValue
0x180222571  mov     r14, rax
0x180222574  test    rax, rax
0x180222577  jnz     short loc_180222592
0x180222579  call    cs:__imp_GetLastError
0x18022257f  test    eax, eax
0x180222581  jz      short loc_180222592
0x180222583  call    OnFailure_977_
0x180222588  jmp     short loc_180222592
0x18022258a  mov     r14, rdi
0x18022258d  call    OnNewFailure_2955_
0x180222592  cmp     [r14+100h], rbx
0x180222599  jnz     loc_180222636
0x18022259f  mov     ecx, 80h; cSize
0x1802225a4  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1802225a9  mov     rsi, rax
0x1802225ac  test    rax, rax
0x1802225af  jz      short loc_1802225E7
0x1802225b1  lea     rax, ??_7?$IIterable@PEAVStateTriggerBase@Xaml@UI@Windows@@@Collections@Foundation@Windows@@6B@; const Windows::Foundation::Collections::IIterable<Windows::UI::Xaml::StateTriggerBase *>::`vftable'
0x1802225b8  mov     [rsi+8], rbx
0x1802225bc  lea     rdi, [rsi+10h]
0x1802225c0  mov     [rsi], rax
0x1802225c3  mov     this, rdi; this
0x1802225c6  call    ??0WeakReferenceSource@ctl@@IEAA@XZ; ctl::WeakReferenceSource::WeakReferenceSource(void)
0x1802225cb  xor     eax, eax
0x1802225cd  mov     [rdi+58h], rax
0x1802225d1  lea     rax, ??_7?$ComObject@VBudgetManager@DirectUI@@@ctl@@6BComObjectBase@1@@; const ctl::ComObject<DirectUI::BudgetManager>::`vftable'{for `ctl::ComObjectBase'}
0x1802225d8  mov     [rsi], rax
0x1802225db  lea     rax, ??_7?$ComObject@VBudgetManager@DirectUI@@@ctl@@6BBudgetManager@DirectUI@@@; const ctl::ComObject<DirectUI::BudgetManager>::`vftable'{for `DirectUI::BudgetManager'}
0x1802225e2  mov     [rdi], rax
0x1802225e5  jmp     short loc_1802225E9
0x1802225e7  xor     esi, esi
0x1802225e9  mov     this, rdi; pNewInstance
0x1802225ec  call    ?CreateInstanceBase@ComObjectBase@ctl@@SAJPEAVComBase@2@I@Z; ctl::ComObjectBase::CreateInstanceBase(ctl::ComBase *,uint)
0x1802225f1  mov     edi, eax
0x1802225f3  test    eax, eax
0x1802225f5  js      short loc_18022266A
0x1802225f7  mov     this, [r14+100h]
0x1802225fe  lea     rdi, [rsi+10h]
0x180222602  xor     eax, eax
0x180222604  test    rsi, rsi
0x180222607  cmovz   rdi, rax
0x18022260b  test    this, this
0x18022260e  jz      short loc_180222623
0x180222610  mov     [r14+100h], rax
0x180222617  mov     rax, [this]
0x18022261a  mov     rax, [rax+10h]
0x18022261e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222623  mov     dl, 1; peg
0x180222625  mov     [r14+100h], rdi
0x18022262c  mov     this, rdi; this
0x18022262f  call    ?UpdatePeg@WeakReferenceSourceNoThreadId@ctl@@QEAAX_N@Z; ctl::WeakReferenceSourceNoThreadId::UpdatePeg(bool)
0x180222634  xor     edi, edi
0x180222636  mov     rsi, [r14+100h]
0x18022263d  test    rsi, rsi
0x180222640  jz      short loc_180222654
0x180222642  mov     rax, [rsi]
0x180222645  mov     this, rsi
0x180222648  mov     rax, [rax+8]
0x18022264c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222651  mov     rbx, rsi
0x180222654  test    edi, edi
0x180222656  js      short loc_18022268D
0x180222658  lea     this, [rbx+60h]; lpPerformanceCount
0x18022265c  call    cs:__imp_QueryPerformanceCounter
0x180222662  xor     r14d, r14d
0x180222665  mov     esi, r14d
0x180222668  jmp     short loc_180222699
0x18022266a  mov     ecx, edi; failedFrameHR
0x18022266c  call    OnFailure_2990_
0x180222671  test    rsi, rsi
0x180222674  jz      short loc_18022267F
0x180222676  lea     this, [rsi+10h]; this
0x18022267a  call    ?Release@?$ComObject@VBudgetManager@DirectUI@@@ctl@@UEAAKXZ; ctl::ComObject<DirectUI::BudgetManager>::Release(void)
0x18022267f  mov     ecx, edi; failedFrameHR
0x180222681  call    OnFailure_2990_
0x180222686  mov     ecx, edi; failedFrameHR
0x180222688  call    OnFailure_2990_
0x18022268d  mov     ecx, edi; failedFrameHR
0x18022268f  mov     esi, edi
0x180222691  call    OnFailure_2990_
0x180222696  xor     r14d, r14d
0x180222699  test    rbx, rbx
0x18022269c  jz      short loc_1802226AD
0x18022269e  mov     rax, [rbx]
0x1802226a1  mov     this, rbx
0x1802226a4  mov     rax, [rax+10h]
0x1802226a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802226ad  movaps  [rsp+240h+var_50], xmm6
0x1802226b5  movaps  [rsp+240h+var_60], xmm7
0x1802226bd  test    esi, esi
0x1802226bf  js      loc_180224B27
0x1802226c5  cmp     qword ptr [r13+1B8h], 0
0x1802226cd  lea     pRenderTarget, _tlgEvent._tlgEvtMetaSize
0x1802226d4  mov     [rsp+240h+cStowedExceptions], r14d
0x1802226d9  lea     r12, _TraceLoggingMetadataEnd
0x1802226e0  mov     pHWWalk, 200000000000h
0x1802226ea  lea     pVisualTree, _TraceLoggingMetadata
0x1802226f1  jnz     loc_180222A17
0x1802226f7  cmp     cs:_Tlgg_hTraceProviderProv.RegHandle, 0
0x1802226ff  jz      loc_1802227CA
0x180222705  mov     eax, cs:_Tlgg_hTraceProviderProv.LevelPlus1
0x18022270b  cmp     eax, 5
0x18022270e  jbe     loc_1802227CA
0x180222714  mov     this, cs:_Tlgg_hTraceProviderProv.KeywordAll
0x18022271b  mov     rax, cs:_Tlgg_hTraceProviderProv.KeywordAny
0x180222722  test    pHWWalk, rax
0x180222725  jz      loc_1802227CA
0x18022272b  mov     rax, this
0x18022272e  and     rax, pHWWalk
0x180222731  cmp     rax, this
0x180222734  jnz     loc_1802227CA
0x18022273a  mov     [rbp+140h+traceSession._Rep], pHWWalk; __annotation("_TlgWrite:|1345|g_hTraceProvider|"XamlFailFast"=|"ErrorCode"=")
0x18022273e  lea     rax, [rbp+140h+pCanPickupForRender]
0x180222742  mov     [rbp+140h+var_C0.Ptr], rax
0x180222749  lea     pHWWalk, [rbp+140h+traceSession]; EventDescriptor
0x18022274d  movzx   eax, word ptr cs:_tlgEvent._tlgLevel
0x180222754  mov     dword ptr [rbp+140h+traceSession._Ptr+4], eax
0x180222757  mov     rax, cs:_Tlgg_hTraceProviderProv.ProviderMetadataPtr
0x18022275e  mov     [rbp+140h+pData.Ptr], rax
0x180222762  mov     [rbp+140h+pCanPickupForRender], 8000FFFFh
0x180222769  mov     qword ptr [rbp+140h+var_C0.Size], 4
0x180222774  mov     dword ptr [rbp+140h+traceSession._Ptr], 0B000000h
0x18022277b  movzx   eax, word ptr [rax]
0x18022277e  mov     [rbp+140h+pData.Size], eax
0x180222781  mov     rax, r12
0x180222784  sub     eax, r9d
0x180222787  mov     qword ptr [rbp+140h+var_D0], pRenderTarget
0x18022278b  mov     dword ptr [rbp+140h+pData.___u2], 2
0x180222792  xor     r9d, r9d; RelatedActivityId
0x180222795  mov     dword ptr [rbp+140h+var_D0+8], 1Bh
0x18022279c  xor     r8d, r8d; ActivityId
0x18022279f  mov     dword ptr [rbp+140h+var_D0+0Ch], 1
0x1802227a6  mov     [rbp+140h+var_190], eax
0x1802227a9  mov     eax, [rbp+140h+var_190]
0x1802227ac  mov     this, cs:_Tlgg_hTraceProviderProv.RegHandle; RegHandle
0x1802227b3  lea     rax, [rbp+140h+pData]
0x1802227b7  mov     [rsp+240h+UserData], rax; UserData
0x1802227bc  mov     [rsp+240h+UserDataCount], 3; UserDataCount
0x1802227c4  call    cs:__imp_EventWriteTransfer
0x1802227ca  xor     r8d, r8d; contextRecord
0x1802227cd  xor     edx, edx; directCallerReturnAddress
0x1802227cf  mov     ecx, 8000FFFFh; failedFrameHR
0x1802227d4  call    OnNewFailureEncountered
0x1802227d9  mov     ecx, cs:g_dwErrorContextTlsIndex; dwTlsIndex
0x1802227df  mov     rbx, r14
0x1802227e2  mov     esi, r14d
0x1802227e5  cmp     ecx, 0FFFFFFFFh
0x1802227e8  jz      loc_180222A07
0x1802227ee  call    cs:__imp_TlsGetValue
0x1802227f4  mov     rdi, rax
0x1802227f7  test    rax, rax
0x1802227fa  jz      loc_180222A07
0x180222800  or      dword ptr [rax+1060h], 2
0x180222807  mov     ecx, cs:g_dwWarningContextTlsIndex; dwTlsIndex
0x18022280d  cmp     ecx, 0FFFFFFFFh
0x180222810  jz      short loc_18022282F
0x180222812  call    cs:__imp_TlsGetValue
0x180222818  test    rax, rax
0x18022281b  jz      short loc_18022282F
0x18022281d  nop     dword ptr [rax]
0x180222820  mov     rax, [rax+1068h]
0x180222827  inc     r14
0x18022282a  test    rax, rax
0x18022282d  jnz     short loc_180222820
0x18022282f  lea     rbx, ds:28h[r14*8]
0x180222837  call    cs:__imp_GetProcessHeap
0x18022283d  mov     pRenderTarget, rbx; dwBytes
0x180222840  xor     edx, edx; dwFlags
0x180222842  mov     this, rax; hHeap
0x180222845  call    cs:__imp_HeapAlloc
0x18022284b  mov     rbx, rax
0x18022284e  test    rax, rax
0x180222851  jz      loc_180222A04
0x180222857  xor     r9d, r9d
0x18022285a  mov     r10d, 80004005h
0x180222860  cmp     esi, 5
0x180222863  jnb     loc_18022292D
0x180222869  movzx   r8d, word ptr [rdi+1864h]
0x180222871  mov     eax, r9d
0x180222874  mov     ecx, r9d
0x180222877  cmp     cx, r8w
0x18022287b  ja      short loc_180222896
0x18022287d  cmp     cx, [rdi+0Ch]
0x180222881  jnb     short loc_180222896
0x180222883  movzx   eax, cx
0x180222886  inc     cx
0x180222889  mov     eax, [rdi+rax*4+1064h]
0x180222890  test    eax, eax
0x180222892  jz      short loc_180222877
0x180222894  jmp     short loc_18022289C
0x180222896  test    eax, eax
0x180222898  cmovz   eax, r10d
0x18022289c  mov     [rdi+1034h], pVisualTree
0x1802228a3  lea     pHWWalk, [rdi+1028h]
0x1802228aa  mov     [rdi+103Ch], pVisualTree
  ... truncated ...
```
