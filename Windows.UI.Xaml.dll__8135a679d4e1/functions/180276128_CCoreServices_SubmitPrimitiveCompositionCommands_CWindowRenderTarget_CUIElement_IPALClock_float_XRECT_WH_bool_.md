# CCoreServices::SubmitPrimitiveCompositionCommands(CWindowRenderTarget *,CUIElement *,IPALClock *,float,XRECT_WH *,bool,bool)

- ea: `0x180276128`
- end: `0x18027741a`
- name: `?SubmitPrimitiveCompositionCommands@CCoreServices@@AEAAJPEAVCWindowRenderTarget@@PEAVCUIElement@@PEAUIPALClock@@MPEAUXRECT_WH@@_N4@Z`
- size: `4850`
- prototype: `HRESULT __fastcall(CCoreServices *this, CWindowRenderTarget *pRenderTarget, CUIElement *pVisualRoot, IPALClock *pClock, float rFrameStartTime, XRECT_WH *pDirtyRect, bool useDCompAnimations, bool pRenderTarget)`
- caller_count: `1`
- callee_count: `58`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802223d0`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180009af8`
- `0x18000b6c0`
- `0x180019e6c`
- `0x18001f3c0`
- `0x18006cfd0`
- `0x180070c4c`
- `0x1800710d0`
- `0x1800724b8`
- `0x180104190`
- `0x18013acfc`
- `0x180153724`
- `0x180157d70`
- `0x1801d1230`
- `0x18021e4e0`
- `0x180220e88`
- `0x180275058`
- `0x1802752b4`
- `0x180275e00`
- `0x180275e6c`
- `0x180276128`
- `0x180277420`
- `0x18027751c`
- `0x180277b3c`
- `0x180277b98`
- `0x180277c78`
- `0x180277dac`
- `0x180277fe8`
- `0x1802780b4`
- `0x1802780e4`
- `0x18027830c`
- `0x180278410`
- `0x18027d9d4`
- `0x1802fb830`
- `0x180379cdc`
- `0x1803cf44c`
- `0x1803cf9c4`
- `0x1804cad20`
- `0x1804cae3c`
- `0x1805784c0`
- `0x1805f3984`
- `0x1805fbf18`
- `0x1806f761c`
- `0x1806fc5d8`
- `0x18076e59c`
- `0x18076e7fc`
- `0x18076e864`
- `0x180773fd8`
- `0x1807b3eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180276269`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180276269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180276446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180276bc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180276446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180276bc0`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x1802770a4`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x1802772bd`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180277308`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180277338`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x1802770a4`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x1802772bd`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180277308`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180277338`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180276e10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180276ec6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180276e10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180276ec6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180276ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180276e95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180276ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180276e95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180276e23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180276ed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180276e23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180276ed9`
- `ext-ms-win-dwmapi-ext-l1-1-0!DwmSetWindowAttribute` at `0x1802769a1`
- `ext-ms-win-dwmapi-ext-l1-1-0!DwmSetWindowAttribute` at `0x1802769a1`

## pseudocode

```c
__int64 CCoreServices::SubmitPrimitiveCompositionCommands(
        CCoreServices *this,
        CWindowRenderTarget *pRenderTarget,
        CUIElement *pVisualRoot,
        IPALClock *pClock,
        float rFrameStartTime,
        XRECT_WH *pDirtyRect,
        bool useDCompAnimations,
        ...)
{
  IXcpBrowserHost *m_pBrowserHost; // rcx
  CWindowRenderTarget *v10; // r14
  CompositorScheduler *v11; // rax
  WindowsGraphicsDeviceManager *m_ptr; // rdx
  CompositorScheduler *v13; // rsi
  _QWORD *ThreadLocalStoragePointer; // rcx
  CPointKeyFrameCollection *m_pDCompTreeHost; // r13
  CD3D11Device *v16; // rax
  __int64 v17; // rbx
  __int64 (__fastcall ***v18)(_QWORD, std::shared_ptr<CAppWindowCollection> *, GUID *, __int64); // rax
  __int64 v19; // r9
  __int64 v20; // rax
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *Myval2; // rcx
  CTimeManager *m_pTimeManager; // r12
  HRESULT v23; // eax
  HRESULT v24; // r14d
  _RTL_CRITICAL_SECTION *p_m_cs; // rsi
  bool v26; // r8
  HRESULT v27; // eax
  _BOOL8 v28; // r9
  CConnectedAnimationService *v29; // rcx
  HWCompTreeNode *m_pCompositionPeer; // rbx
  WindowsGraphicsDeviceManager *v31; // rcx
  DCompTreeHost *v32; // r13
  std::pair<CXamlIslandRoot *,DCompTreeHost::XamlIslandRenderData> *Myfirst; // rbx
  std::pair<CXamlIslandRoot *,DCompTreeHost::XamlIslandRenderData> *Mylast; // rdi
  bool IsDropShadowMode; // al
  CPointKeyFrameCollection *v36; // r13
  ProjectedShadowManager *v37; // r14
  CRenderTargetBitmapManager *m_pRenderTargetBitmapManager; // rdi
  CAppWindowCollection *Ptr; // r12
  Windows::UI::Composition::ICompositor *v40; // rbx
  std::allocator<xref_ptr<CDependencyObject> > *v41; // r8
  CAppWindowCollection **v42; // r14
  CAppWindowCollection **v43; // rdi
  xref_ptr<CDependencyObject> *v44; // rdx
  xref_ptr<CDependencyObject> *v45; // rcx
  CompositorScheduler *v46; // rbx
  IPALEvent *m_pCompositorWait; // rcx
  _QWORD *v48; // rdi
  unsigned __int64 m_fIsSetLocally; // rcx
  CAppWindowCollection *v50; // rsi
  HRESULT v51; // eax
  HRESULT v52; // ebx
  std::shared_ptr<CAppWindowCollection> *v53; // rax
  unsigned __int64 v54; // rcx
  CXamlIslandRoot *first; // rcx
  CContentRoot *v56; // rax
  HWCompTreeNode *v57; // r12
  int v58; // ecx
  HRESULT v59; // eax
  HRESULT v60; // ebx
  HWND v61; // rcx
  CConnectedAnimationService *v62; // rcx
  RuntimeFeatureBehavior::RuntimeEnabledFeatureDetector *v63; // rdi
  unsigned __int8 v64; // bl
  char v65; // bl
  unsigned __int8 v66; // bl
  char v67; // bl
  CAppWindowCollection *v68; // rbx
  CWindowRenderTarget *v69; // r12
  IXcpHostSite *m_pHostSite; // rcx
  unsigned int v71; // esi
  WindowsPresentTarget *v72; // rcx
  int m_height; // eax
  bool v74; // zf
  volatile signed __int32 *v75; // rbx
  HRESULT v77; // eax
  CAppWindowCollection *v78; // rbx
  unsigned int v79; // edi
  unsigned int v80; // ebx
  unsigned int v81; // eax
  int v82; // eax
  HRESULT updated; // eax
  __int64 v84; // rax
  HRESULT v85; // eax
  DCompVisual *m_pBackgroundVisual; // rcx
  ThemeShadowScene *v87; // rcx
  xref::weakref_ptr<CXamlIslandRoot> *p_first; // rdi
  std::_List_node<xref_ptr<ThemeShadowScene>,void *> *Myhead; // rbx
  xref::weakref_ptr<CPopup> *v90; // rdi
  xref::weakref_ptr<CPopup> *i; // rbx
  ThemeShadowScene *v92; // rcx
  std::_List_node<xref_ptr<ThemeShadowScene>,void *> *Next; // rdi
  std::_List_node<xref_ptr<ThemeShadowScene>,void *> *v94; // rcx
  HRESULT v95; // eax
  CTimeManager *v96; // rcx
  int v97; // eax
  ITickableFrameScheduler *v98; // rax
  CCoreServices *m_pCoreNoRef; // rcx
  bool v100; // r12
  CXcpList<IRenderTargetElement>::XCPListNode *m_pHead; // rbx
  CXcpList<IRenderTargetElement>::XCPListNode *v102; // r12
  IRenderTargetElement *v103; // rbx
  IRenderTargetElement_vtbl *v104; // rax
  __int64 v105; // rcx
  HRESULT v106; // eax
  char v107; // cl
  int v108; // eax
  char v109; // cl
  int v110; // eax
  DependencyLocator::DependencyProvider<CAppWindowCollection> *v111; // rcx
  DependencyLocator::StoragePolicyFlags v112; // r8d
  CXamlIslandRoot *v113; // rax
  CPointKeyFrameCollection *v114; // rbx
  CXamlIslandRoot *v115; // r12
  CTimeline *m_pTimingOwner; // rcx
  HRESULT v117; // eax
  long double UIThreadFrameDelta; // xmm0_8
  CPopup *v119; // rax
  CXcpList<IRenderTargetElement>::XCPListNode *m_pNext; // rdi
  IRenderTargetElement *m_pData; // rbx
  CRenderTargetElementData *v122; // rax
  WindowsPresentTarget *v123; // rcx
  float v124; // xmm6_4
  float v125; // xmm6_4
  float v126; // xmm0_4
  unsigned int v127; // eax
  unsigned int v128; // r9d
  BOOL phkResult; // [rsp+28h] [rbp-A9h]
  CompositorScheduler *hKey; // [rsp+38h] [rbp-99h] BYREF
  std::function<std::shared_ptr<CAppWindowCollection> __cdecl(void)> hKey_8; // [rsp+40h] [rbp-91h] BYREF
  std::shared_ptr<CAppWindowCollection> v132; // [rsp+80h] [rbp-51h] BYREF
  CAppWindowCollection *v133; // [rsp+90h] [rbp-41h]
  std::shared_ptr<CAppWindowCollection> result; // [rsp+98h] [rbp-39h] BYREF
  XRECT_WH v135; // [rsp+A8h] [rbp-29h]
  CD3D11Device *v136; // [rsp+B8h] [rbp-19h]
  volatile signed __int32 *v137; // [rsp+C0h] [rbp-11h]
  xref_ptr<CPointKeyFrameCollection> cbData; // [rsp+118h] [rbp+47h] BYREF
  CWindowRenderTarget *renderTarget; // [rsp+120h] [rbp+4Fh]
  IPALClock *v140; // [rsp+130h] [rbp+5Fh]
  __int64 pRenderTarget_0; // [rsp+150h] [rbp+7Fh] BYREF
  va_list pRenderTarget_0a; // [rsp+150h] [rbp+7Fh]
  va_list va1; // [rsp+158h] [rbp+87h] BYREF

  va_start(va1, useDCompAnimations);
  va_start(pRenderTarget_0a, useDCompAnimations);
  pRenderTarget_0 = va_arg(va1, _QWORD);
  v140 = pClock;
  renderTarget = pRenderTarget;
  m_pBrowserHost = this->m_pBrowserHost;
  v10 = pRenderTarget;
  v135 = 0;
  v11 = m_pBrowserHost->GetCompositorScheduler(m_pBrowserHost);
  m_ptr = v10->m_graphicsDeviceManager.m_ptr;
  v13 = v11;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  hKey = v11;
  m_pDCompTreeHost = (CPointKeyFrameCollection *)m_ptr->m_pDCompTreeHost;
  v16 = m_ptr->m_cachedD3DDevice.m_ptr;
  cbData.m_ptr = m_pDCompTreeHost;
  v136 = v16;
  v17 = ThreadLocalStoragePointer[tls_index];
  if ( _TSS0_59 > *(_DWORD *)(v17 + 40) )
  {
    Init_thread_header(&_TSS0_59);
    if ( _TSS0_59 == -1 )
    {
      hKey_8._Mystorage._Ptrs[0] = (std::_Func_base<std::shared_ptr<CAppWindowCollection> > *)std::_Func_impl_no_alloc__lambda_616ed30a09447f595568e445f1e1026e__std::shared_ptr_CAppWindowCollection___::_vftable_;
      hKey_8._Mystorage._Ptrs[7] = (std::_Func_base<std::shared_ptr<CAppWindowCollection> > *)&hKey_8;
      DependencyLocator::DependencyProvider<CAppWindowCollection>::DependencyProvider<CAppWindowCollection>(
        v111,
        &hKey_8,
        v112);
      atexit(CAppWindowCollection::Get_::_2_::_dynamic_atexit_destructor_for____COUNTER__CAppWindowCollection__);
      Init_thread_footer(&_TSS0_59);
    }
  }
  v18 = (__int64 (__fastcall ***)(_QWORD, std::shared_ptr<CAppWindowCollection> *, GUID *, __int64))s_applicationWindowCollection.GetStorage(&s_applicationWindowCollection);
  LOBYTE(v19) = 1;
  v20 = (**v18)(v18, &v132, &GUID_36726fd8_242d_49e0_b0b7_6513bfc18a4b, v19);
  v133 = *(CAppWindowCollection **)v20;
  v137 = *(volatile signed __int32 **)(v20 + 8);
  *(_QWORD *)v20 = 0;
  *(_QWORD *)(v20 + 8) = 0;
  if ( v132._Rep )
    std::_Ref_count_base::_Decref(v132._Rep);
  if ( _TSS0_30 > *(_DWORD *)(v17 + 40) )
  {
    Init_thread_header(&_TSS0_30);
    if ( _TSS0_30 == -1 )
    {
      RuntimeFeatureBehavior::GetRuntimeEnabledFeatureDetector(&runtimeEnabledFeatureDetector_16);
      atexit(CCoreServices::SubmitPrimitiveCompositionCommands_::_2_::_dynamic_atexit_destructor_for__runtimeEnabledFeatureDetector__);
      Init_thread_footer(&_TSS0_30);
    }
  }
  Myval2 = m_pDCompTreeHost[2].m_pValueTable._Mypair._Myval2;
  m_pTimeManager = this->m_pTimeManager;
  result._Ptr = (CAppWindowCollection *)m_pTimeManager;
  if ( Myval2 )
  {
    v23 = (*(__int64 (__fastcall **)(containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *))((char *)&Myval2->m_data.m_vector._Mypair._Myval2._Myfirst[14].second.value.m_value + 4))(Myval2);
    v24 = v23;
    if ( v23 < 0 )
      goto LABEL_204;
    v10 = renderTarget;
  }
  p_m_cs = &v13->m_pDrawListsLock->m_cs;
  EnterCriticalSection(p_m_cs);
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x400) != 0 )
  {
    memset(&hKey_8, 0, 48);
    if ( McGenPreVista )
    {
      LOWORD(hKey_8._Mystorage._Dummy1) = 48;
      hKey_8._Mystorage._Ptrs[3] = (std::_Func_base<std::shared_ptr<CAppWindowCollection> > *)&CompositorLockId;
      HIDWORD(hKey_8._Mystorage._Ptrs[5]) = 1703936;
      HIDWORD(hKey_8._Mystorage._Ptrs[0]) = 1025;
      TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, (PEVENT_TRACE_HEADER)&hKey_8);
    }
    else
    {
      PfnEventWrite(WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle, &CompositorLockBegin, 0, 0);
    }
  }
  v27 = CompositorTreeHost::ProcessFrame(v10->m_pCompositorTreeHost, (DCompTreeHost *)m_pDCompTreeHost, v26);
  v24 = v27;
  if ( v27 < 0 )
    goto LABEL_161;
  v29 = this->m_connectedAnimationService.m_ptr;
  if ( v29 )
  {
    v27 = CConnectedAnimationService::PreCommit(v29);
    v24 = v27;
    if ( v27 < 0 )
      goto LABEL_161;
  }
  if ( pVisualRoot )
    m_pCompositionPeer = pVisualRoot->m_pCompositionPeer;
  else
    m_pCompositionPeer = 0;
  v24 = 0;
  if ( !useDCompAnimations && (*((_BYTE *)m_pTimeManager + 96) & 2) == 0 )
  {
    UIThreadFrameDelta = CTimeManager::GetUIThreadFrameDelta(m_pTimeManager);
    CTimeManager::SetIndependentStartTimes(m_pTimeManager, UIThreadFrameDelta);
  }
  v31 = this->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr;
  v32 = v31->m_pDCompTreeHost;
  if ( m_pCompositionPeer )
  {
    updated = HWCompTreeNode::UpdateTreeRoot(m_pCompositionPeer, v31->m_pDCompTreeHost, useDCompAnimations);
    v24 = updated;
    if ( updated < 0
      || (!m_pCompositionPeer->GetVisual(m_pCompositionPeer)
       || (v84 = (__int64)m_pCompositionPeer->GetVisual(m_pCompositionPeer),
           !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v84 + 216LL))(v84)))
      && (updated = DCompTreeHost::SetRoot(v32, m_pCompositionPeer), v24 = updated, updated < 0) )
    {
LABEL_154:
      OnFailure_2990_(updated);
LABEL_155:
      OnFailure_2990_(v24);
      goto LABEL_156;
    }
  }
  Myfirst = v32->m_islandRenderData.m_data.m_vector._Mypair._Myval2._Myfirst;
  Mylast = v32->m_islandRenderData.m_data.m_vector._Mypair._Myval2._Mylast;
  while ( Myfirst != Mylast )
  {
    first = Myfirst->first;
    if ( Myfirst->first )
    {
      v56 = first->m_contentRoot.m_ptr;
      if ( v56 )
      {
        if ( v56 != (CContentRoot *)-32LL )
        {
          v57 = first->m_pCompositionPeer;
          if ( v57 )
          {
            v58 = *((_DWORD *)&v57->HWCompNode + 26);
            LODWORD(pRenderTarget_0) = (2 * v58) >> 3;
            if ( !(_DWORD)pRenderTarget_0 )
            {
              if ( v32 )
              {
                if ( (v58 & 1) == 0 )
                {
                  if ( v32->m_legacyFullScreenSwapchainHandleNoRef )
                  {
                    v85 = DCompVisual::SetMedia(v32->m_pFullScreenMediaVisual, 0);
                    v24 = v85;
                    if ( v85 < 0
                      || (m_pBackgroundVisual = v32->m_pBackgroundVisual,
                          v32->m_legacyFullScreenSwapchainHandleNoRef = 0,
                          v85 = DCompVisual::SetVisible(m_pBackgroundVisual, 0),
                          v24 = v85,
                          v85 < 0) )
                    {
                      OnFailure_2990_(v85);
                      v60 = v24;
                      OnFailure_2990_(v24);
                      goto LABEL_73;
                    }
                  }
                }
              }
            }
            LOBYTE(v28) = useDCompAnimations;
            LOBYTE(phkResult) = 0;
            v59 = v57->UpdateTreeVirtual(v57, v32, (unsigned int *)pRenderTarget_0a, v28, phkResult);
            v24 = v59;
            if ( v59 < 0 )
            {
              OnFailure_2990_(v59);
              OnFailure_2990_(v24);
              v60 = v24;
LABEL_73:
              OnFailure_2990_(v60);
              goto LABEL_155;
            }
          }
        }
      }
    }
    ++Myfirst;
  }
  if ( v24 < 0 )
    goto LABEL_155;
  IsDropShadowMode = CThemeShadow::IsDropShadowMode();
  v36 = cbData.m_ptr;
  if ( !IsDropShadowMode )
  {
    v37 = (ProjectedShadowManager *)cbData.m_ptr[2].m_sharedState.m_ptr;
    if ( v37->m_hasEverHadCaster
      && ProjectedShadowManager::IsShadowImplementationEnabled()
      && DCompTreeHost::SpriteVisualsEnabled() )
    {
      if ( ProjectedShadowManager::DisabledByPolicy(v37) )
      {
        if ( v37->m_customScenesNeedClearing )
        {
          std::list<xref_ptr<ThemeShadowScene>>::clear(&v37->m_customScenes);
          v37->m_customScenesNeedClearing = 0;
        }
      }
      else
      {
        v87 = v37->m_globalScene.m_ptr;
        if ( v87 )
        {
          ThemeShadowScene::UpdateCasters(v87);
          ThemeShadowGlobalScene::PreprocessSharedCasters(v37->m_globalScene.m_ptr);
          ThemeShadowGlobalScene::UpdateReceiversAndFilterCasters(v37->m_globalScene.m_ptr, this, 0);
        }
        p_first = &v37->m_xamlIslandsGlobalScenes.m_data.m_vector._Mypair._Myval2._Myfirst->first;
        if ( ((char *)v37->m_xamlIslandsGlobalScenes.m_data.m_vector._Mypair._Myval2._Mylast - (char *)p_first) / 24 )
        {
          while ( p_first != (xref::weakref_ptr<CXamlIslandRoot> *)v37->m_xamlIslandsGlobalScenes.m_data.m_vector._Mypair._Myval2._Mylast )
          {
            v113 = xref::weakref_ptr<CXamlIslandRoot>::lock_noref(p_first);
            v114 = (CPointKeyFrameCollection *)p_first[1].m_ptr;
            v115 = v113;
            cbData.m_ptr = v114;
            if ( v114 )
              CDependencyObject::AddRef(v114);
            ThemeShadowScene::UpdateCasters((ThemeShadowScene *)v114);
            ThemeShadowGlobalScene::PreprocessSharedCasters((ThemeShadowGlobalScene *)v114);
            ThemeShadowGlobalScene::UpdateReceiversAndFilterCasters((ThemeShadowGlobalScene *)v114, this, v115);
            p_first = (xref::weakref_ptr<CXamlIslandRoot> *)((char *)p_first + 24);
            xref_ptr<CTranslateTransform>::DecrementRefCount(&cbData);
          }
        }
        Myhead = v37->m_customScenes._Mypair._Myval2._Myhead;
LABEL_146:
        for ( Myhead = Myhead->_Next; Myhead != v37->m_customScenes._Mypair._Myval2._Myhead; Myhead = Next )
        {
          ThemeShadowScene::UpdateCasters(Myhead->_Myval.m_ptr);
          Myhead->_Myval.m_ptr->UpdateReceivers(Myhead->_Myval.m_ptr, this, 0);
          v92 = Myhead->_Myval.m_ptr;
          if ( v92->m_shadowCasters._Mypair._Myval2._Mysize && ThemeShadowScene::GetNumOfReceivers(v92) )
            goto LABEL_146;
          Next = Myhead->_Next;
          Myhead->_Prev->_Next = Myhead->_Next;
          v94 = Myhead->_Next;
          v94->_Prev = Myhead->_Prev;
          --v37->m_customScenes._Mypair._Myval2._Mysize;
          std::_List_node<xref_ptr<ThemeShadowScene>,void *>::_Freenode<std::allocator<std::_List_node<xref_ptr<ThemeShadowScene>,void *>>>(
            (std::allocator<std::_List_node<xref_ptr<ThemeShadowScene>,void *> > *)v94,
            Myhead);
        }
        v90 = v37->m_popupsLookingForNewCasters._Mypair._Myval2._Mylast;
        for ( i = v37->m_popupsLookingForNewCasters._Mypair._Myval2._Myfirst; i != v90; ++i )
        {
          v119 = xref::weakref_ptr<CScrollViewer>::lock_noref(i);
          if ( v119 )
            CUIElement::SetEntireSubtreeDirty(v119);
        }
        std::vector<xref::weakref_ptr<CPopup>>::clear(&v37->m_popupsLookingForNewCasters);
      }
    }
  }
  m_pRenderTargetBitmapManager = this->m_pRenderTargetBitmapManager;
  if ( m_pRenderTargetBitmapManager->m_pRenderingListNoRef )
  {
    m_pCoreNoRef = m_pRenderTargetBitmapManager->m_pCoreNoRef;
    v100 = 0;
    if ( m_pCoreNoRef->m_initializationType == 4 )
    {
      updated = CCoreServices::FlushImageDecodeRequests(m_pCoreNoRef);
      v24 = updated;
      if ( updated < 0 )
        goto LABEL_154;
      v100 = m_pRenderTargetBitmapManager->m_pCoreNoRef->m_cPendingDecodes != 0;
    }
    m_pHead = m_pRenderTargetBitmapManager->m_pRenderingListNoRef->m_pHead;
    if ( v100 )
    {
      while ( m_pHead )
      {
        m_pNext = m_pHead->m_pNext;
        m_pData = m_pHead->m_pData;
        if ( m_pData->GetCurrentState(m_pData) == Deinitializing )
        {
          v122 = m_pData->GetRenderTargetElementData(m_pData);
          CRenderTargetElementData::ResetState(v122);
          updated = m_pData->SetCurrentState(m_pData, InitializationFailed);
          v24 = updated;
          if ( updated < 0 )
            goto LABEL_154;
        }
        m_pHead = m_pNext;
      }
    }
    else
    {
      while ( m_pHead )
      {
        v102 = m_pHead->m_pNext;
        v103 = m_pHead->m_pData;
        if ( v103->GetCurrentState(v103) == Deinitializing )
        {
          v104 = v103->__vftable;
          cbData.m_ptr = 0;
          if ( !v104->IsDrawRequired(v103) )
          {
            v105 = (__int64)&gps.m_pTarget->IPALThreadingServices & -(__int64)(gps.m_pTarget != 0);
            v106 = (*(__int64 (__fastcall **)(__int64, xref_ptr<CPointKeyFrameCollection> *, _QWORD, _QWORD))(*(_QWORD *)v105 + 8LL))(
                     v105,
                     &cbData,
                     0,
                     0);
            v24 = v106;
            if ( v106 < 0 )
              goto LABEL_229;
          }
          v106 = v103->PreCommit(v103, renderTarget, (IPALEvent *)cbData.m_ptr);
          v24 = v106;
          if ( v106 < 0 )
            goto LABEL_229;
          if ( !v103->IsDrawRequired(v103) )
          {
            CRenderTargetBitmapManager::AddWaitItem(m_pRenderTargetBitmapManager, v103, (IPALWaitable *)cbData.m_ptr);
            v106 = CRenderTargetBitmapManager::SubmitWaitWorkItem(
                     m_pRenderTargetBitmapManager,
                     (IPALWaitable *)cbData.m_ptr);
            v24 = v106;
            if ( v106 < 0 )
              goto LABEL_229;
            cbData.m_ptr = 0;
          }
          v106 = v103->SetCurrentState(v103, Deinitialized);
          v24 = v106;
          if ( v106 < 0 )
          {
LABEL_229:
            OnFailure_2990_(v106);
            if ( cbData.m_ptr )
              cbData.m_ptr->ReleaseOverride(cbData.m_ptr);
            goto LABEL_155;
          }
          if ( cbData.m_ptr )
            cbData.m_ptr->ReleaseOverride(cbData.m_ptr);
        }
        m_pHead = v102;
      }
    }
  }
  Ptr = result._Ptr;
  if ( result._Ptr )
  {
    v40 = this->m_pNWWindowRenderTarget->m_graphicsDeviceManager.m_ptr->m_pDCompTreeHost->m_spCompositor.ptr_;
    if ( DCompTreeHost::ContainerVisualsEnabled() )
    {
      v132._Ptr = (CAppWindowCollection *)v40;
      if ( v40 )
        v40->AddRef(v40);
      v42 = (CAppWindowCollection **)Ptr[7].m_pendingLayoutCompleted._Mypair._Myval2._Mylast;
      v43 = (CAppWindowCollection **)Ptr[7].m_pendingLayoutCompleted._Mypair._Myval2._Myfirst;
      LODWORD(v132._Rep) = 0;
      while ( v43 != v42 )
      {
        v78 = *v43;
        result._Ptr = v78;
        if ( v78 )
          CDependencyObject::AddRef((CDependencyObject *)v78);
        ((void (__fastcall *)(CAppWindowCollection *, std::shared_ptr<CAppWindowCollection> *))v78->m_appWindows._Mypair._Myval2._Myfirst[83]._Mypair._Myval2)(
          v78,
          &v132);
        xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&result);
        ++v43;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&v132);
    }
    v44 = (xref_ptr<CDependencyObject> *)Ptr[7].m_pendingLayoutCompleted._Mypair._Myval2._Mylast;
    v45 = (xref_ptr<CDependencyObject> *)Ptr[7].m_pendingLayoutCompleted._Mypair._Myval2._Myfirst;
    if ( v45 != v44 )
    {
      std::_Destroy_range<std::allocator<xref_ptr<CDependencyObject>>>(v45, v44, v41);
      Ptr[7].m_pendingLayoutCompleted._Mypair._Myval2._Mylast = Ptr[7].m_pendingLayoutCompleted._Mypair._Myval2._Myfirst;
    }
  }
  v46 = hKey;
  if ( this->m_renderStateChanged )
  {
    if ( this->m_isRenderEnabled )
    {
      v27 = CompositorScheduler::OnRenderStateChanged(hKey, 1u);
      v24 = v27;
      if ( v27 < 0 )
      {
LABEL_161:
        OnFailure_2990_(v27);
LABEL_156:
        LeaveCriticalSection(p_m_cs);
        goto $Cleanup_1556;
      }
    }
  }
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x400) != 0 )
  {
    memset(&hKey_8, 0, 48);
    if ( McGenPreVista )
    {
      hKey_8._Mystorage._Ptrs[3] = (std::_Func_base<std::shared_ptr<CAppWindowCollection> > *)&CompositorLockId;
      HIDWORD(hKey_8._Mystorage._Ptrs[5]) = 1703936;
      LOWORD(hKey_8._Mystorage._Dummy1) = 48;
      HIDWORD(hKey_8._Mystorage._Ptrs[0]) = 1026;
      TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, (PEVENT_TRACE_HEADER)&hKey_8);
    }
    else
    {
      PfnEventWrite(WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle, &CompositorLockEnd, 0, 0);
    }
  }
  LeaveCriticalSection(p_m_cs);
  LODWORD(Ptr[1].m_pendingLayoutCompleted._Mypair._Myval2._Myend) &= ~0x10u;
  m_pCompositorWait = v46->m_pCompositorWait;
  if ( m_pCompositorWait )
  {
    if ( v46->m_pRenderThread )
    {
      v23 = m_pCompositorWait->Set(m_pCompositorWait);
      v24 = v23;
      if ( v23 < 0 )
      {
LABEL_204:
        OnFailure_2990_(v23);
        OnFailure_2990_(v24);
        goto $Cleanup_1556;
      }
    }
  }
  if ( !v36[2].m_pValueTable._Mypair._Myval2 )
  {
    v24 = 0;
    goto LABEL_75;
  }
  if ( v36[3].m_pOwner.m_ref_count
    && _InterlockedCompareExchange((volatile signed __int32 *)&v36[3].m_pfnOwnerRenderChangedHandler, 0, 0)
    && (m_pTimingOwner = v36[2].m_pTimingOwner) != 0 )
  {
    v117 = ((__int64 (__fastcall *)(CTimeline *))m_pTimingOwner->~CDependencyObject)(m_pTimingOwner);
    v52 = v117;
    if ( v117 < 0 )
    {
      OnFailure_2990_(v117);
      goto LABEL_124;
    }
  }
  else
  {
    v48 = 0;
    m_fIsSetLocally = v36[2].m_pInheritedProperties->m_fIsSetLocally;
    if ( m_fIsSetLocally )
    {
      v48 = *(_QWORD **)(m_fIsSetLocally + 40);
      if ( v48 )
        v48 = (_QWORD *)v48[4];
    }
    CAppWindowCollection::Get(&v132);
    v50 = v132._Ptr;
    if ( !v48 && v132._Ptr )
      v48 = v132._Ptr->m_dcompSyncObject.m_ptr;
    if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x400) != 0 )
    {
      memset(&hKey_8, 0, 48);
      if ( McGenPreVista )
      {
        hKey_8._Mystorage._Ptrs[3] = (std::_Func_base<std::shared_ptr<CAppWindowCollection> > *)&CommitMainDeviceId;
        LOWORD(hKey_8._Mystorage._Dummy1) = 48;
        HIDWORD(hKey_8._Mystorage._Ptrs[5]) = 1703936;
        HIDWORD(hKey_8._Mystorage._Ptrs[0]) = 1025;
        TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, (PEVENT_TRACE_HEADER)&hKey_8);
      }
      else
      {
        PfnEventWrite(WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle, &CommitMainDeviceBegin, 0, 0);
      }
    }
    v51 = ((__int64 (__fastcall *)(containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *, _QWORD *))v36[2].m_pValueTable._Mypair._Myval2->m_data.m_vector._Mypair._Myval2._Myfirst[27].second.value.m_flags)(
            v36[2].m_pValueTable._Mypair._Myval2,
            v48);
    v52 = v51;
    if ( v51 >= 0 )
    {
      if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x400) != 0 )
      {
        memset(&hKey_8, 0, 48);
        if ( McGenPreVista )
        {
          hKey_8._Mystorage._Ptrs[3] = (std::_Func_base<std::shared_ptr<CAppWindowCollection> > *)&CommitMainDeviceId;
          HIDWORD(hKey_8._Mystorage._Ptrs[5]) = 1703936;
          HIDWORD(hKey_8._Mystorage._Ptrs[0]) = 1026;
          LOWORD(hKey_8._Mystorage._Dummy1) = 48;
          TraceEvent(WINDOWS_UI_XAML_ETW_PROVIDER_Context.Logger, (PEVENT_TRACE_HEADER)&hKey_8);
        }
        else
        {
          PfnEventWrite(WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle, &CommitMainDeviceEnd, 0, 0);
        }
      }
      if ( v50 )
      {
        v53 = CAppWindowCollection::Get(&result);
        CAppWindowCollection::ReleaseDCompSyncObject(v53->_Ptr);
        if ( result._Rep )
          std::_Ref_count_base::_Decref(result._Rep);
      }
      v54 = v36[2].m_pInheritedProperties->m_fIsSetLocally;
      if ( v54 )
      {
        if ( v48 )
        {
          v123 = *(WindowsPresentTarget **)(v54 + 40);
          if ( v123 )
            WindowsPresentTarget::ProcessSynchronization(v123);
        }
      }
      if ( v132._Rep )
        std::_Ref_count_base::_Decref(v132._Rep);
      v24 = v52;
      goto LABEL_75;
    }
    OnFailure_2990_(v51);
    if ( v132._Rep )
    {
      std::_Ref_count_base::_Decref(v132._Rep);
LABEL_124:
      v24 = v52;
LABEL_125:
      OnFailure_2990_(v52);
      goto $Cleanup_1556;
    }
  }
  v24 = v52;
  if ( v52 < 0 )
    goto LABEL_125;
LABEL_75:
  if ( IsDwmSetWindowAttributePresent() )
  {
    v61 = (HWND)*((_QWORD *)&v36[3].CDOCollection + 19);
    if ( v61 )
    {
      if ( *((_DWORD *)&v36[3].CKeyFrameCollection + 42) == 1 )
      {
        LODWORD(pRenderTarget_0) = 0;
        v82 = DwmSetWindowAttribute(v61, 0xFu, pRenderTarget_0a, 4u);
        if ( v82 < 0 )
          OnFailure_2990_(v82);
        else
          *((_DWORD *)&v36[3].CKeyFrameCollection + 42) = 0;
      }
    }
  }
  v62 = this->m_connectedAnimationService.m_ptr;
  if ( v62 )
  {
    v95 = CConnectedAnimationService::CleanupRetainedElements(v62);
    v24 = v95;
    if ( v95 < 0 )
    {
      OnFailure_2990_(v95);
      goto $Cleanup_1556;
    }
  }
  if ( !CThemeShadow::IsDropShadowMode() )
    ProjectedShadowManager::UpdateSharedCasters((ProjectedShadowManager *)v36[2].m_sharedState.m_ptr);
  v63 = runtimeEnabledFeatureDetector_16._Ptr;
  v64 = (unsigned __int8)runtimeEnabledFeatureDetector_16._Ptr->m_runtimeFeatureStates[44];
  if ( (v64 & 4) != 0 )
    goto LABEL_83;
  if ( (v64 & 8) != 0 )
  {
    v64 >>= 1;
LABEL_83:
    v65 = v64 & 1;
    goto LABEL_84;
  }
  LODWORD(pRenderTarget_0) = 0;
  hKey = 0;
  v65 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, (PHKEY)&hKey) )
  {
    LODWORD(cbData.m_ptr) = 4;
    if ( !RegQueryValueExW(
            (HKEY)hKey,
            RuntimeFeatureBehavior::s_runtimeFeatureData[44].FeatureName,
            0,
            0,
            (LPBYTE)pRenderTarget_0a,
            (LPDWORD)&cbData) )
      v65 = (_DWORD)pRenderTarget_0 != 0;
    RegCloseKey((HKEY)hKey);
  }
  v107 = *(_BYTE *)&v63->m_runtimeFeatureStates[44] ^ (*(_BYTE *)&v63->m_runtimeFeatureStates[44] ^ (2 * v65)) & 2;
  *(_BYTE *)&v63->m_runtimeFeatureStates[44] = v107;
  v108 = pRenderTarget_0;
  *(_BYTE *)&v63->m_runtimeFeatureStates[44] = v107 | 0x18;
  v63->m_runtimeFeatureStates[44].CacheDwordData = v108;
  v63 = runtimeEnabledFeatureDetector_16._Ptr;
LABEL_84:
  if ( v65 )
  {
LABEL_238:
    DCompSurfaceMonitor::DumpSurfacesDrawn(this->m_uFrameNumber);
    goto LABEL_90;
  }
  v66 = (unsigned __int8)v63->m_runtimeFeatureStates[45];
  if ( (v66 & 4) != 0 )
    goto LABEL_88;
  if ( (v66 & 8) != 0 )
  {
    v66 >>= 1;
LABEL_88:
    v67 = v66 & 1;
    goto LABEL_89;
  }
  LODWORD(pRenderTarget_0) = 0;
  hKey = 0;
  v67 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, (PHKEY)&hKey) )
  {
    LODWORD(cbData.m_ptr) = 4;
    if ( !RegQueryValueExW(
            (HKEY)hKey,
            RuntimeFeatureBehavior::s_runtimeFeatureData[45].FeatureName,
            0,
            0,
            (LPBYTE)pRenderTarget_0a,
            (LPDWORD)&cbData) )
      v67 = (_DWORD)pRenderTarget_0 != 0;
    RegCloseKey((HKEY)hKey);
  }
  v109 = *(_BYTE *)&v63->m_runtimeFeatureStates[45] ^ (*(_BYTE *)&v63->m_runtimeFeatureStates[45] ^ (2 * v67)) & 2;
  *(_BYTE *)&v63->m_runtimeFeatureStates[45] = v109;
  v110 = pRenderTarget_0;
  *(_BYTE *)&v63->m_runtimeFeatureStates[45] = v109 | 0x18;
  v63->m_runtimeFeatureStates[45].CacheDwordData = v110;
LABEL_89:
  if ( v67 )
    goto LABEL_238;
LABEL_90:
  v68 = v133;
  if ( this->m_fLayoutCompletedNeeded
    || v133
    && v133->m_pendingLayoutCompleted._Mypair._Myval2._Myfirst != v133->m_pendingLayoutCompleted._Mypair._Myval2._Mylast )
  {
    v69 = renderTarget;
    v77 = DCompTreeHost::NotifyWindowLayoutComplete((DCompTreeHost *)v36, renderTarget);
    v24 = v77;
    if ( v77 < 0 )
      goto LABEL_243;
    if ( v68 )
    {
      v77 = CAppWindowCollection::ProcessLayoutCompleted(v68);
      v24 = v77;
      if ( v77 < 0 )
        goto LABEL_243;
    }
  }
  else
  {
    v69 = renderTarget;
  }
  m_pHostSite = this->m_pHostSite;
  if ( m_pHostSite )
  {
    v71 = m_pHostSite->GetEnableFrameRateCounter(m_pHostSite);
    if ( (*((_BYTE *)this + 956) & 8) != 0 )
    {
      v79 = this->m_pHostSite->GetEnableRedrawRegions(this->m_pHostSite);
      v80 = this->m_pHostSite->GetEnableOverdrawHeatMap(this->m_pHostSite);
      v81 = this->m_pHostSite->GetEnableFrameRateCounter(this->m_pHostSite);
      v77 = DCompTreeHost::UpdateDebugSettings((DCompTreeHost *)v36, v81, v80, v79);
      v24 = v77;
      if ( v77 < 0 )
        goto LABEL_243;
    }
    if ( v71 )
    {
      if ( v140 )
      {
        v124 = v140->GetAbsoluteTimeInSeconds(v140);
        v125 = (float)(v124 - rFrameStartTime) * 1000.0;
      }
      else
      {
        v125 = 0.0;
      }
      v126 = this->m_pBrowserHost->get_CurrFrameRate(this->m_pBrowserHost);
      v127 = XcpFloor(v126 + 0.5);
      v77 = DCompTreeHost::UpdateUIThreadCounters((DCompTreeHost *)v36, v127, v125, v128);
      v24 = v77;
      if ( v77 < 0 )
        goto LABEL_243;
    }
    if ( (*((_BYTE *)this + 956) & 8) != 0 || v71 )
    {
      v77 = DCompTreeHost::CommitMainDevice((DCompTreeHost *)v36, 0);
      v24 = v77;
      if ( v77 < 0 )
        goto LABEL_243;
    }
  }
  if ( v136 )
    CD3D11Device::TrimMemory(v136);
  v72 = v69->m_presentTarget.m_ptr;
  if ( v72 )
  {
    v135.Width = v72->m_width;
    m_height = v72->m_height;
  }
  else
  {
    v135.Width = 0;
    m_height = 0;
  }
  ++this->m_uFrameNumber;
  v74 = !this->m_isFirstFrameAfterAppStart;
  v135.Height = m_height;
  this->m_fLayoutCompletedNeeded = 0;
  if ( !v74 || (LOBYTE(v72) = 3, DesignerInterop::GetDesignerMode((DesignerMode)v72)) )
  {
    v96 = this->m_pTimeManager;
    v97 = *((_DWORD *)v96 + 24);
    if ( (v97 & 2) != 0 )
    {
      *((_DWORD *)v96 + 24) = v97 & 0xFFFFFFE9 | 0x14;
      v98 = this->m_pBrowserHost->GetFrameScheduler(this->m_pBrowserHost);
      if ( v98 )
      {
        v77 = v98->RequestAdditionalFrame(v98, 0, UnknownType);
        v24 = v77;
        if ( v77 < 0 )
          goto LABEL_243;
      }
    }
  }
  if ( this->m_isFirstFrameAfterAppStart )
  {
    v77 = CCoreServices::ProcessDownloadRequests(this, 0);
    v24 = v77;
    if ( v77 < 0 )
    {
LABEL_243:
      OnFailure_2990_(v77);
      goto $Cleanup_1556;
    }
    this->m_pHostSite->OnFirstFrameDrawn(this->m_pHostSite);
    this->m_isFirstFrameAfterAppStart = 0;
  }
  if ( pDirtyRect )
    *pDirtyRect = v135;
$Cleanup_1556:
  v75 = v137;
  if ( v137 )
  {
    if ( _InterlockedExchangeAdd(v137 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
      if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180276128  mov     rax, rsp
0x18027612b  mov     [rax+18h], rbx
0x18027612f  mov     [rax+20h], pClock
0x180276133  mov     [rax+10h], pRenderTarget
0x180276137  push    rbp
0x180276138  push    rsi
0x180276139  push    rdi
0x18027613a  push    r12
0x18027613c  push    r13
0x18027613e  push    r14
0x180276140  push    r15
0x180276142  lea     rbp, [rax-3Fh]
0x180276146  sub     rsp, 0D0h
0x18027614d  movaps  xmmword ptr [rax-48h], xmm6
0x180276151  mov     r15, this
0x180276154  mov     this, [this+108h]
0x18027615b  xorps   xmm0, xmm0
0x18027615e  mov     rdi, pVisualRoot
0x180276161  mov     r14, pRenderTarget
0x180276164  movups  xmmword ptr [rbp-29h], xmm0
0x180276168  mov     rax, [this]
0x18027616b  mov     rax, [rax+208h]
0x180276172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276177  mov     pRenderTarget, [r14+20h]
0x18027617b  mov     rsi, rax
0x18027617e  mov     this, gs:58h
0x180276187  mov     [rsp+100h+hKey], rax
0x18027618c  mov     r12d, 28h ; '('
0x180276192  mov     r13, [pRenderTarget+58h]
0x180276196  mov     rax, [pRenderTarget+50h]
0x18027619a  mov     edx, cs:_tls_index
0x1802761a0  mov     [rbp+37h+cbData], r13
0x1802761a4  mov     [rbp+37h+var_50], rax
0x1802761a8  mov     rbx, [this+pRenderTarget*8]
0x1802761ac  mov     ecx, [rbx+r12]
0x1802761b0  cmp     cs:$TSS0_59, ecx
0x1802761b6  jg      loc_180276F8D
0x1802761bc  mov     rax, cs:s_applicationWindowCollection.__vftable
0x1802761c3  lea     this, s_applicationWindowCollection
0x1802761ca  mov     rax, [rax]
0x1802761cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802761d2  mov     r10, rax
0x1802761d5  lea     pVisualRoot, _GUID_36726fd8_242d_49e0_b0b7_6513bfc18a4b
0x1802761dc  mov     r9b, 1
0x1802761df  lea     pRenderTarget, [rbp+37h+var_88]
0x1802761e3  mov     this, [rax]
0x1802761e6  mov     rax, [this]
0x1802761e9  mov     this, r10
0x1802761ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802761f1  mov     this, [rax]
0x1802761f4  mov     [rbp+37h+var_78], this
0x1802761f8  mov     this, [rax+8]
0x1802761fc  mov     [rbp+37h+var_48], this
0x180276200  mov     qword ptr [rax], 0
0x180276207  mov     qword ptr [rax+8], 0
0x18027620f  mov     this, [rbp+37h+var_80]; this
0x180276213  test    this, this
0x180276216  jz      short loc_18027621D
0x180276218  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18027621d  mov     eax, [rbx+r12]
0x180276221  cmp     cs:$TSS0_30, eax
0x180276227  jg      loc_180276F0D
0x18027622d  mov     this, [r13+188h]
0x180276234  mov     r12, [r15+0E0h]
0x18027623b  mov     [rbp+37h+result._Ptr], r12
0x18027623f  test    this, this
0x180276242  jz      short loc_180276262
0x180276244  mov     rax, [this]
0x180276247  mov     rax, [rax+120h]
0x18027624e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276253  mov     r14d, eax
0x180276256  test    eax, eax
0x180276258  js      loc_18027706B
0x18027625e  mov     r14, [rbp+37h+renderTarget]
0x180276262  mov     rsi, [rsi+68h]
0x180276266  mov     this, rsi; lpCriticalSection
0x180276269  call    cs:__imp_EnterCriticalSection
0x18027626f  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+1, 4
0x180276276  lea     rax, CompositorLockId
0x18027627d  mov     ecx, 30h ; '0'
0x180276282  jz      short loc_1802762C2
0x180276284  cmp     cs:McGenPreVista, 0
0x18027628b  xorps   xmm0, xmm0
0x18027628e  movups  xmmword ptr [rsp+100h+hKey+8], xmm0
0x180276293  movups  [rsp+100h+var_C0+8], xmm0
0x180276298  movups  [rbp+37h+var_A8], xmm0
0x18027629c  jnz     loc_180277080
0x1802762a2  mov     this, cs:WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle
0x1802762a9  lea     pRenderTarget, CompositorLockBegin
0x1802762b0  mov     rax, cs:PfnEventWrite
0x1802762b7  xor     r9d, r9d
0x1802762ba  xor     r8d, r8d
0x1802762bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802762c2  mov     this, [r14+38h]; this
0x1802762c6  mov     pRenderTarget, r13; pVisualTreeHost
0x1802762c9  call    ?ProcessFrame@CompositorTreeHost@@QEAAJPEAVDCompTreeHost@@_N@Z; CompositorTreeHost::ProcessFrame(DCompTreeHost *,bool)
0x1802762ce  mov     r14d, eax
0x1802762d1  test    eax, eax
0x1802762d3  js      loc_18027740E
0x1802762d9  mov     this, [r15+930h]; this
0x1802762e0  test    this, this
0x1802762e3  jnz     loc_180276C04
0x1802762e9  test    rdi, rdi
0x1802762ec  jz      loc_180276BFD
0x1802762f2  mov     rbx, [rdi+118h]
0x1802762f9  xor     r14d, r14d
0x1802762fc  cmp     [rbp+37h+arg_30], r14b
0x180276300  jz      loc_1802770AF
0x180276306  mov     rax, [r15+660h]
0x18027630d  mov     this, [rax+20h]
0x180276311  mov     r13, [this+58h]
0x180276315  test    rbx, rbx
0x180276318  jnz     loc_1802769BF
0x18027631e  mov     rbx, [r13+10h]
0x180276322  mov     rdi, [r13+18h]
0x180276326  cmp     rbx, rdi
0x180276329  jnz     loc_1802765EF
0x18027632f  test    r14d, r14d
0x180276332  js      loc_180276BB5
0x180276338  call    ?IsDropShadowMode@CThemeShadow@@SA_NXZ; CThemeShadow::IsDropShadowMode(void)
0x18027633d  mov     r13, [rbp+37h+cbData]
0x180276341  test    al, al
0x180276343  jnz     short loc_180276355
0x180276345  mov     r14, [r13+170h]
0x18027634c  cmp     [r14], al
0x18027634f  jnz     loc_180276AC0
0x180276355  mov     rdi, [r15+4C8h]
0x18027635c  cmp     qword ptr [rdi+18h], 0
0x180276361  jnz     loc_180276CA4
0x180276367  mov     r12, [rbp+37h+result._Ptr]
0x18027636b  test    r12, r12
0x18027636e  jz      short loc_1802763E9
0x180276370  mov     rax, [r15+660h]
0x180276377  mov     this, [rax+20h]
0x18027637b  mov     rax, [this+58h]
0x18027637f  mov     rbx, [rax+1C8h]
0x180276386  call    ?ContainerVisualsEnabled@DCompTreeHost@@SA_NXZ; DCompTreeHost::ContainerVisualsEnabled(void)
0x18027638b  test    al, al
0x18027638d  jz      short loc_1802763D0
0x18027638f  mov     [rbp+37h+var_88.ptr_], rbx
0x180276393  test    rbx, rbx
0x180276396  jz      short loc_1802763A7
0x180276398  mov     rax, [rbx]
0x18027639b  mov     this, rbx
0x18027639e  mov     rax, [rax+8]
0x1802763a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802763a7  mov     r14, [r12+1A8h]
0x1802763af  mov     rdi, [r12+1A0h]
0x1802763b7  mov     dword ptr [rbp+37h+var_80], 0
0x1802763be  cmp     rdi, r14
0x1802763c1  jnz     loc_1802768B0
0x1802763c7  lea     this, [rbp+37h+var_88]; this
0x1802763cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802763d0  mov     pRenderTarget, [r12+1A8h]; _Last
0x1802763d8  mov     this, [r12+1A0h]; _First
0x1802763e0  cmp     this, pRenderTarget
0x1802763e3  jnz     loc_180276AA6
0x1802763e9  cmp     dword ptr [r15+3C8h], 0
0x1802763f1  mov     rbx, [rsp+100h+hKey]
0x1802763f6  jnz     loc_180276F4F
0x1802763fc  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+1, 4
0x180276403  jz      short loc_180276443
0x180276405  cmp     cs:McGenPreVista, 0
0x18027640c  xorps   xmm0, xmm0
0x18027640f  movups  xmmword ptr [rsp+100h+hKey+8], xmm0
0x180276414  movups  [rsp+100h+var_C0+8], xmm0
0x180276419  movups  [rbp+37h+var_A8], xmm0
0x18027641d  jnz     loc_18027728D
0x180276423  mov     this, cs:WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle
0x18027642a  lea     pRenderTarget, CompositorLockEnd
0x180276431  mov     rax, cs:PfnEventWrite
0x180276438  xor     r9d, r9d
0x18027643b  xor     r8d, r8d
0x18027643e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276443  mov     this, rsi; lpCriticalSection
0x180276446  call    cs:__imp_LeaveCriticalSection
0x18027644c  and     dword ptr [r12+60h], 0FFFFFFEFh
0x180276452  mov     this, [rbx+30h]
0x180276456  test    this, this
0x180276459  jz      short loc_180276479
0x18027645b  cmp     qword ptr [rbx+20h], 0
0x180276460  jz      short loc_180276479
0x180276462  mov     rax, [this]
0x180276465  mov     rax, [rax+10h]
0x180276469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027646e  mov     r14d, eax
0x180276471  test    eax, eax
0x180276473  js      loc_1802772C8
0x180276479  cmp     qword ptr [r13+188h], 0
0x180276481  jz      loc_180276686
0x180276487  cmp     qword ptr [r13+278h], 0
0x18027648f  jz      short loc_1802764A4
0x180276491  xor     ecx, ecx
0x180276493  xor     eax, eax
0x180276495  lock cmpxchg [r13+280h], ecx
0x18027649e  jnz     loc_180277039
0x1802764a4  mov     rax, [r13+180h]
0x1802764ab  xor     edi, edi
0x1802764ad  mov     this, [rax+68h]
0x1802764b1  test    this, this
0x1802764b4  jz      short loc_1802764C3
0x1802764b6  mov     rdi, [this+28h]
0x1802764ba  test    rdi, rdi
0x1802764bd  jz      short loc_1802764C3
0x1802764bf  mov     rdi, [rdi+20h]
0x1802764c3  lea     this, [rbp+37h+var_88]; result
0x1802764c7  call    ?Get@CAppWindowCollection@@SA?AV?$shared_ptr@VCAppWindowCollection@@@std@@XZ; CAppWindowCollection::Get(void)
0x1802764cc  mov     rsi, [rbp+37h+var_88.ptr_]
0x1802764d0  test    rdi, rdi
0x1802764d3  jnz     short loc_1802764DE
0x1802764d5  test    rsi, rsi
0x1802764d8  jz      short loc_1802764DE
0x1802764da  mov     rdi, [rsi+30h]
0x1802764de  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+1, 4
0x1802764e5  lea     r14, CommitMainDeviceId
0x1802764ec  jz      short loc_18027652C
0x1802764ee  cmp     cs:McGenPreVista, 0
0x1802764f5  xorps   xmm0, xmm0
0x1802764f8  movups  xmmword ptr [rsp+100h+hKey+8], xmm0
0x1802764fd  movups  [rsp+100h+var_C0+8], xmm0
0x180276502  movups  [rbp+37h+var_A8], xmm0
0x180276506  jnz     loc_1802772DD
0x18027650c  mov     this, cs:WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle
0x180276513  lea     pRenderTarget, CommitMainDeviceBegin
0x18027651a  mov     rax, cs:PfnEventWrite
0x180276521  xor     r9d, r9d
0x180276524  xor     r8d, r8d
0x180276527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027652c  mov     r12d, 30h ; '0'
0x180276532  mov     this, [r13+188h]
0x180276539  mov     pRenderTarget, rdi
0x18027653c  mov     rax, [this]
0x18027653f  mov     rax, [rax+228h]
0x180276546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027654b  mov     ebx, eax
0x18027654d  test    eax, eax
0x18027654f  js      loc_180276956
0x180276555  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+1, 4
0x18027655c  jz      short loc_18027659C
0x18027655e  cmp     cs:McGenPreVista, 0
0x180276565  xorps   xmm0, xmm0
0x180276568  movups  xmmword ptr [rsp+100h+hKey+8], xmm0
0x18027656d  movups  [rsp+100h+var_C0+8], xmm0
0x180276572  movups  [rbp+37h+var_A8], xmm0
0x180276576  jnz     loc_180277313
0x18027657c  mov     this, cs:WINDOWS_UI_XAML_ETW_PROVIDER_Context.RegistrationHandle
0x180276583  lea     pRenderTarget, CommitMainDeviceEnd
0x18027658a  mov     rax, cs:PfnEventWrite
0x180276591  xor     r9d, r9d
0x180276594  xor     r8d, r8d
0x180276597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027659c  test    rsi, rsi
0x18027659f  jz      short loc_1802765C0
0x1802765a1  lea     this, [rbp+37h+result]; result
0x1802765a5  call    ?Get@CAppWindowCollection@@SA?AV?$shared_ptr@VCAppWindowCollection@@@std@@XZ; CAppWindowCollection::Get(void)
0x1802765aa  mov     this, [rax]; this
0x1802765ad  call    ?ReleaseDCompSyncObject@CAppWindowCollection@@QEAAXXZ; CAppWindowCollection::ReleaseDCompSyncObject(void)
0x1802765b2  mov     this, [rbp+37h+result._Rep]; this
0x1802765b6  test    this, this
0x1802765b9  jz      short loc_1802765C0
0x1802765bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802765c0  mov     rax, [r13+180h]
0x1802765c7  mov     this, [rax+68h]
0x1802765cb  test    this, this
0x1802765ce  jz      short loc_1802765D9
0x1802765d0  test    rdi, rdi
0x1802765d3  jnz     loc_180277343
0x1802765d9  mov     this, [rbp+37h+var_80]; this
0x1802765dd  test    this, this
0x1802765e0  jz      short loc_1802765E7
0x1802765e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802765e7  mov     r14d, ebx
0x1802765ea  jmp     loc_180276689
0x1802765ef  mov     this, [rbx]
0x1802765f2  test    this, this
0x1802765f5  jz      short loc_180276615
0x1802765f7  mov     rax, [this+3D0h]
0x1802765fe  test    rax, rax
0x180276601  jz      short loc_180276615
0x180276603  add     rax, 20h ; ' '
0x180276607  jz      short loc_180276615
0x180276609  mov     r12, [this+118h]
0x180276610  test    r12, r12
0x180276613  jnz     short loc_18027661E
0x180276615  add     rbx, 18h
0x180276619  jmp     loc_180276326
0x18027661e  mov     ecx, [r12+68h]
0x180276623  lea     eax, [this+this]
0x180276626  sar     eax, 3
0x180276629  mov     dword ptr [rbp+37h+pRenderTarget_0], eax
0x18027662c  test    eax, eax
0x18027662e  jnz     short loc_18027663E
0x180276630  test    r13, r13
0x180276633  jz      short loc_18027663E
0x180276635  test    cl, 1
0x180276638  jz      loc_180276A4F
0x18027663e  mov     rax, [r12]
0x180276642  lea     pVisualRoot, [rbp+37h+pRenderTarget_0]
0x180276646  mov     r9b, [rbp+37h+arg_30]
0x18027664a  mov     pRenderTarget, r13
  ... truncated ...
```
