# CUIElement::GetLocalTransform(TransformRetrievalOptions,CMILMatrix *)

- ea: `0x180101ca0`
- end: `0x1801034bb`
- name: `?GetLocalTransform@CUIElement@@QEAAIW4TransformRetrievalOptions@@PEAVCMILMatrix@@@Z`
- size: `6171`
- prototype: `unsigned int __fastcall(CUIElement *this, TransformRetrievalOptions transformRetrievalOptions, CMILMatrix *pLocalTransform)`
- caller_count: `27`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180068420`
- `0x18006e1a0`
- `0x18010fb64`
- `0x180110c74`
- `0x18011136c`
- `0x180113620`
- `0x180135e20`
- `0x1801378fc`
- `0x18019a4c4`
- `0x18019caa4`
- `0x18019ec08`
- `0x1801a0aa0`
- `0x1802bfd54`
- `0x1802e2b80`
- `0x1802e35e0`
- `0x1802e3828`
- `0x1802e7d40`
- `0x1803ce408`
- `0x1803ce834`
- `0x1805ea104`
- `0x18066e084`
- `0x18077d1e0`
- `0x18077eb3c`
- `0x18077fd94`
- `0x180787590`
- `0x1809d84c0`
- `0x180a131fc`

## callees

- `0x180004bc0`
- `0x18000b6c0`
- `0x180021840`
- `0x180045d64`
- `0x18006c2b0`
- `0x180070c4c`
- `0x180100978`
- `0x180101ca0`
- `0x1801034d0`
- `0x180103530`
- `0x1801036c0`
- `0x180103860`
- `0x180103ab0`
- `0x180103b08`
- `0x180103c6c`
- `0x180103c78`
- `0x180103de8`
- `0x180103f68`
- `0x180103f80`
- `0x180104190`
- `0x180104490`
- `0x1801044a4`
- `0x1801044c8`
- `0x180104508`
- `0x180104518`
- `0x180105d8c`
- `0x18011a408`
- `0x180153724`
- `0x18018fa54`
- `0x1801a8b30`
- `0x1801cb2d8`
- `0x1801cbeb0`
- `0x18044bb6c`
- `0x18044be28`
- `0x1804633dc`
- `0x1804b05e0`
- `0x18065cf40`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x18076e59c`
- `0x18076e7fc`
- `0x18076e864`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180101d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180101d9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180101dbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180101dbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010332b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801033e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010332b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801033e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801032fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801033b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801032fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801033b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010333d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801033f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010333d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801033f5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801032bd`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801032bd`

## pseudocode

```c
_BOOL8 __fastcall CUIElement::GetLocalTransform(
        CUIElement *this,
        TransformRetrievalOptions transformRetrievalOptions,
        CMILMatrix *pLocalTransform)
{
  char v3; // r15
  bool v4; // zf
  char v6; // r14
  bool v8; // al
  float v9; // xmm12_4
  KnownTypeIndex v10; // ax
  int v11; // edi
  CCustomClassInfo *Myval2; // rdi
  char v13; // al
  float v14; // xmm8_4
  int v15; // eax
  bool v16; // di
  const Windows::Foundation::Numerics::Vector3 *v17; // rcx
  float Y; // xmm7_4
  float X; // xmm6_4
  double v20; // xmm0_8
  float v21; // xmm9_4
  double v22; // xmm0_8
  CUIElement_vtbl *v23; // rax
  float v24; // xmm10_4
  double v25; // xmm0_8
  float elementWidth; // xmm7_4
  double v27; // xmm0_8
  float elementHeight; // xmm11_4
  int v29; // r13d
  int v30; // eax
  CCoreServices *v31; // rax
  std::pair<CDependencyObject const *,DOFacadeStorage> *v32; // r9
  std::pair<CDependencyObject const *,DOFacadeStorage> *v33; // rax
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // r10
  const Windows::Foundation::Numerics::Vector3 *ImplSparse_48; // rax
  __int64 v37; // xmm0_8
  float v38; // eax
  CCoreServices *v39; // rax
  std::pair<CDependencyObject const *,DOFacadeStorage> *v40; // r9
  std::pair<CDependencyObject const *,DOFacadeStorage> *v41; // rax
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r10
  double ImplSparse_140; // xmm0_8
  float v45; // xmm0_4
  CCoreServices *v46; // rax
  std::pair<CDependencyObject const *,DOFacadeStorage> *v47; // r9
  std::pair<CDependencyObject const *,DOFacadeStorage> *v48; // rax
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // r10
  containers::detail::vector_tree<containers::detail::map_traits<enum KnownPropertyIndex,DOFacadeAnimationInfo,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> >,0> > *v51; // rax
  const Windows::Foundation::Numerics::Vector3 *v52; // rax
  __int64 v53; // xmm0_8
  FacadeTransformInfo *p_facadeInfo; // rdi
  std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *HandOffVisualTransform; // rax
  int v56; // r14d
  CTransform *pHandOffVisualTransform; // r15
  std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *TransitionTarget; // rax
  CTransitionTarget *pTransitionTarget; // r12
  XPOINTF renderTransformOrigin; // xmm6_8
  CTransform *pRenderTransform; // rax
  float v62; // xmm0_4
  float v63; // xmm1_4
  char *v65; // r9
  char *v66; // rcx
  unsigned __int64 v67; // rdx
  const Windows::Foundation::Numerics::Vector3 *Impl_2071; // rax
  float v69; // ecx
  std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> *v70; // r9
  std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> *v71; // rcx
  unsigned __int64 v72; // rdx
  std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *v73; // rax
  char *v74; // r9
  char *v75; // rcx
  unsigned __int64 v76; // rdx
  float Impl_2069; // xmm1_4
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *v78; // rax
  std::pair<enum KnownPropertyIndex,EffectiveValue> *Myfirst; // rcx
  unsigned __int64 v80; // rdx
  CCoreServices *m_coreServices; // rax
  std::pair<CDependencyObject const *,DOFacadeStorage> *Mylast; // r10
  std::pair<CDependencyObject const *,DOFacadeStorage> *v83; // rax
  unsigned __int64 v84; // rdx
  unsigned __int64 v85; // r9
  float *p_Z; // rax
  char *v87; // rcx
  CCoreServices *v88; // rax
  std::pair<CDependencyObject const *,DOFacadeStorage> *v89; // r10
  std::pair<CDependencyObject const *,DOFacadeStorage> *v90; // rax
  unsigned __int64 v91; // r8
  unsigned __int64 v92; // r9
  const Windows::Foundation::Numerics::Vector3 *p_second; // rcx
  __int64 v94; // xmm8_8
  _STOWED_EXCEPTION_INFORMATION_V2 **v95; // rbx
  float Z; // xmm11_4
  _STOWED_EXCEPTION_INFORMATION_V2 *v97; // rax
  CMILMatrix *m_pCombinedLocalTransform; // rax
  float _11; // xmm3_4
  float _12; // xmm2_4
  float _21; // xmm5_4
  float _22; // xmm4_4
  float _31; // xmm6_4
  float _32; // xmm7_4
  CMILMatrix *v105; // rax
  float v106; // xmm0_4
  CCoreServices *v107; // rdx
  std::pair<void *,Windows::Foundation::Numerics::Vector3> *v108; // r10
  std::pair<void *,Windows::Foundation::Numerics::Vector3> *v109; // rcx
  unsigned __int64 v110; // rdx
  CInputServices *m_ptr; // rax
  HRESULT DirectManipulationServiceAndContent; // eax
  IObject *v113; // r13
  HRESULT v114; // r12d
  std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> *v115; // r12
  HKEY__ *v116; // rdx
  IObject *v117; // rax
  int v118; // r14d
  HKEY__ *v119; // rcx
  KnownTypeIndex v120; // ax
  KnownTypeIndex i; // cx
  const CClassInfo *ClassInfoByIndex; // rax
  char v123; // al
  TextFormatting *m_pTextFormatting; // rax
  float v125; // xmm1_4
  char *v126; // r10
  char *v127; // rcx
  unsigned __int64 v128; // rdx
  CCoreServices *v129; // rdx
  std::pair<void *,Windows::Foundation::Numerics::Vector3> *v130; // r10
  std::pair<void *,Windows::Foundation::Numerics::Vector3> *v131; // rcx
  unsigned __int64 v132; // rdx
  CCoreServices *v133; // rdx
  unsigned __int64 v134; // rdx
  char *v135; // r9
  char *v136; // rcx
  unsigned __int64 v137; // rdx
  CCoreServices *v138; // rdx
  std::pair<void *,Windows::Foundation::Numerics::Vector3> *v139; // r10
  std::pair<void *,Windows::Foundation::Numerics::Vector3> *v140; // rcx
  unsigned __int64 v141; // rdx
  CCoreServices *v142; // rdx
  unsigned __int64 v143; // rdx
  bool IsEnabled; // al
  _QWORD *ThreadLocalStoragePointer; // rcx
  RuntimeFeatureBehavior::RuntimeEnabledFeatureDetector *Ptr; // r13
  char v147; // di
  char v148; // di
  char v149; // r12
  char v150; // r12
  CCoreServices *v151; // rax
  std::pair<CDependencyObject const *,DOFacadeStorage> *v152; // r10
  std::pair<CDependencyObject const *,DOFacadeStorage> *v153; // rax
  unsigned __int64 v154; // rdx
  unsigned __int64 v155; // r9
  char *v156; // r9
  char *v157; // rcx
  unsigned __int64 v158; // rdx
  CCoreServices *v159; // rdx
  unsigned __int64 v160; // rdx
  HRESULT Viewport; // eax
  char v162; // cl
  float v163; // eax
  char v164; // cl
  float v165; // eax
  float v166; // xmm1_4
  float dmZoomFactorX; // [rsp+A0h] [rbp-80h] BYREF
  float dmOffsetX; // [rsp+A4h] [rbp-7Ch] BYREF
  unsigned int cStowedExceptions; // [rsp+A8h] [rbp-78h] BYREF
  bool v170; // [rsp+ACh] [rbp-74h]
  HKEY__ *phkResult; // [rsp+B0h] [rbp-70h] BYREF
  int v172; // [rsp+B8h] [rbp-68h]
  float dmOffsetY; // [rsp+BCh] [rbp-64h] BYREF
  unsigned int shouldFlipRTL; // [rsp+C0h] [rbp-60h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+C8h] [rbp-58h] BYREF
  Windows::Foundation::Numerics::Vector3 v176; // [rsp+D0h] [rbp-50h] BYREF
  float dmZoomFactorY; // [rsp+E0h] [rbp-40h] BYREF
  std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > v178; // [rsp+E8h] [rbp-38h] BYREF
  XDMContentType pDMContentType[2]; // [rsp+F0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v181; // [rsp+108h] [rbp-18h]
  IObject *ppCompositorContent; // [rsp+110h] [rbp-10h] BYREF
  float dmUncompressedZoomFactor; // [rsp+118h] [rbp-8h] BYREF
  float pContentOffsetX; // [rsp+11Ch] [rbp-4h] BYREF
  unsigned int shouldFlipRTLInPlace; // [rsp+120h] [rbp+0h] BYREF
  int v186; // [rsp+124h] [rbp+4h] BYREF
  XamlLocalTransformBuilder builder; // [rsp+128h] [rbp+8h] BYREF
  Windows::Foundation::Numerics::Matrix4x4 result; // [rsp+140h] [rbp+20h] BYREF
  FacadeTransformInfo facadeInfo; // [rsp+180h] [rbp+60h] BYREF

  *(_QWORD *)&pLocalTransform->_11 = 1065353216;
  pLocalTransform->_21 = 0.0;
  v3 = transformRetrievalOptions & 1;
  *(_QWORD *)&pLocalTransform->_22 = 1065353216;
  v4 = !s_containerVisualsEnabledInitialized;
  pLocalTransform->_32 = 0.0;
  v6 = transformRetrievalOptions;
  builder.m_state = Initial;
  builder.__vftable = (XamlLocalTransformBuilder_vtbl *)XamlLocalTransformBuilder::`vftable';
  builder.m_pCombinedLocalTransform = pLocalTransform;
  if ( v4 )
  {
    IsEnabled = CQuirksMode2::XamlQuirkIsEnabled(0x2007Bu);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v170 = IsEnabled;
    if ( _TSS0_50 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 40LL) )
    {
      Init_thread_header(&_TSS0_50);
      if ( _TSS0_50 == -1 )
      {
        RuntimeFeatureBehavior::GetRuntimeEnabledFeatureDetector(&runtimeEnabledFeatureDetector_31);
        atexit(DCompTreeHost::ContainerVisualsEnabled_::_5_::_dynamic_atexit_destructor_for__runtimeEnabledFeatureDetector__);
        Init_thread_footer(&_TSS0_50);
      }
    }
    Ptr = runtimeEnabledFeatureDetector_31._Ptr;
    v147 = (char)runtimeEnabledFeatureDetector_31._Ptr->m_runtimeFeatureStates[21];
    if ( (v147 & 4) != 0 )
    {
      v148 = v147 & 1;
    }
    else if ( (v147 & 8) != 0 )
    {
      v148 = (v147 & 2) != 0;
    }
    else
    {
      dmZoomFactorX = 0.0;
      phkResult = 0;
      v148 = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, &phkResult) )
      {
        shouldFlipRTL = 4;
        if ( !RegQueryValueExW(
                phkResult,
                RuntimeFeatureBehavior::s_runtimeFeatureData[21].FeatureName,
                0,
                0,
                (LPBYTE)&dmZoomFactorX,
                &shouldFlipRTL) )
          v148 = LODWORD(dmZoomFactorX) != 0;
        RegCloseKey(phkResult);
      }
      v162 = *(_BYTE *)&Ptr->m_runtimeFeatureStates[21] ^ (*(_BYTE *)&Ptr->m_runtimeFeatureStates[21] ^ (2 * v148)) & 2;
      *(_BYTE *)&Ptr->m_runtimeFeatureStates[21] = v162;
      v163 = dmZoomFactorX;
      *(_BYTE *)&Ptr->m_runtimeFeatureStates[21] = v162 | 0x18;
      *(float *)&Ptr->m_runtimeFeatureStates[21].CacheDwordData = v163;
      Ptr = runtimeEnabledFeatureDetector_31._Ptr;
    }
    v149 = (char)Ptr->m_runtimeFeatureStates[22];
    if ( (v149 & 4) != 0 )
    {
      v150 = v149 & 1;
    }
    else if ( (v149 & 8) != 0 )
    {
      v150 = (v149 & 2) != 0;
    }
    else
    {
      ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)RuntimeFeatureBehavior::s_runtimeFeatureData[22].FeatureName;
      dmZoomFactorX = 0.0;
      phkResult = 0;
      v150 = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, &phkResult) )
      {
        shouldFlipRTL = 4;
        if ( !RegQueryValueExW(phkResult, (LPCWSTR)ppStowedExceptions, 0, 0, (LPBYTE)&dmZoomFactorX, &shouldFlipRTL) )
          v150 = LODWORD(dmZoomFactorX) != 0;
        RegCloseKey(phkResult);
      }
      v164 = *(_BYTE *)&Ptr->m_runtimeFeatureStates[22] ^ (*(_BYTE *)&Ptr->m_runtimeFeatureStates[22] ^ (2 * v150)) & 2;
      *(_BYTE *)&Ptr->m_runtimeFeatureStates[22] = v164;
      v165 = dmZoomFactorX;
      *(_BYTE *)&Ptr->m_runtimeFeatureStates[22] = v164 | 0x18;
      *(float *)&Ptr->m_runtimeFeatureStates[22].CacheDwordData = v165;
    }
    v8 = DCompTreeHost::SpriteVisualsEnabled();
    if ( !v170 && v148 || v150 || v8 )
      v8 = 1;
    s_containerVisualsEnabled = v8;
    s_containerVisualsEnabledInitialized = 1;
  }
  else
  {
    v8 = s_containerVisualsEnabled;
  }
  v9 = 0.0;
  if ( !v8 )
    goto LABEL_13;
  v10 = this->GetTypeIndex(this);
  v11 = (unsigned __int16)v10;
  if ( v10 == RootVisual )
    goto LABEL_13;
  if ( (unsigned __int16)v10 >= (XYFocusNavigationStrategy|IVectorOfUri) )
  {
    EnterCriticalSection(&g_csStatic);
    Myval2 = DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesCache._Mypair._Myval2._Myfirst[v11 - 1084]._Mypair._Myval2;
    LeaveCriticalSection(&g_csStatic);
    while ( Myval2->m_nIndex )
    {
      if ( Myval2->m_nIndex == RootVisual )
      {
        v13 = 1;
        goto LABEL_11;
      }
      Myval2 = (CCustomClassInfo *)DirectUI::MetadataAPI::GetClassInfoByIndex(Myval2->m_nBaseTypeIndex);
    }
    v13 = 0;
LABEL_11:
    if ( v13 )
      goto LABEL_13;
  }
  if ( (*((_DWORD *)this + 37) & 0x100) == 0 )
    goto LABEL_13;
  v78 = this->m_pValueTable._Mypair._Myval2;
  if ( !v78 )
    goto LABEL_13;
  Myfirst = v78->m_data.m_vector._Mypair._Myval2._Myfirst;
  v80 = v78->m_data.m_vector._Mypair._Myval2._Mylast - v78->m_data.m_vector._Mypair._Myval2._Myfirst;
  while ( (__int64)v80 > 0 )
  {
    if ( Myfirst[v80 >> 1].first < UIElement_HandOffVisualTransform )
    {
      Myfirst += (v80 >> 1) + 1;
      v80 += -1LL - (v80 >> 1);
    }
    else
    {
      v80 >>= 1;
    }
  }
  if ( Myfirst == v78->m_data.m_vector._Mypair._Myval2._Mylast || Myfirst->first > UIElement_HandOffVisualTransform )
    goto LABEL_13;
  m_coreServices = this->m_sharedState.m_ptr->m_value.m_coreServices;
  Mylast = m_coreServices->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Mylast;
  v83 = m_coreServices->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Myfirst;
  v84 = Mylast - v83;
  while ( (__int64)v84 > 0 )
  {
    v85 = v84 >> 1 << 6;
    if ( *(const CDependencyObject **)((char *)&v83->first + v85) < this )
    {
      v83 = (std::pair<CDependencyObject const *,DOFacadeStorage> *)((char *)v83 + v85 + 64);
      v84 += -1LL - (v84 >> 1);
    }
    else
    {
      v84 >>= 1;
    }
  }
  if ( v83 != Mylast && this >= v83->first && v83 != (std::pair<CDependencyObject const *,DOFacadeStorage> *)-8LL )
  {
    v135 = (char *)v83->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v136 = (char *)v83->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v137 = (v135 - v136) / 48;
    while ( (__int64)v137 > 0 )
    {
      if ( *(_WORD *)&v136[48 * (v137 >> 1)] < 0x822u )
      {
        v136 += 48 * (v137 >> 1) + 48;
        v137 += -1LL - (v137 >> 1);
      }
      else
      {
        v137 >>= 1;
      }
    }
    if ( v136 != v135 && *(_WORD *)v136 <= 0x822u && v136 != (char *)-8LL )
    {
      if ( SimpleProperty::Property::id<2073>::IsSet(this) )
      {
        v138 = this->m_sharedState.m_ptr->m_value.m_coreServices;
        v139 = v138->m_sparseTables.m_UIElement_AnimatedTranslation.m_data.m_vector._Mypair._Myval2._Mylast;
        v140 = v138->m_sparseTables.m_UIElement_AnimatedTranslation.m_data.m_vector._Mypair._Myval2._Myfirst;
        v141 = v139 - v140;
        while ( (__int64)v141 > 0 )
        {
          if ( v140[v141 >> 1].first < this )
          {
            v140 += (v141 >> 1) + 1;
            v141 += -1LL - (v141 >> 1);
          }
          else
          {
            v141 >>= 1;
          }
        }
        goto LABEL_224;
      }
LABEL_105:
      p_Z = &value.Z;
      v87 = (char *)&value.Z + 1;
      goto LABEL_106;
    }
  }
  if ( !(unsigned __int8)((__int64 (__fastcall *)(CUIElement *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                           this,
                           2082) )
    goto LABEL_105;
  v142 = this->m_sharedState.m_ptr->m_value.m_coreServices;
  v139 = v142->m_sparseTables.m_UIElement_Translation.m_data.m_vector._Mypair._Myval2._Mylast;
  v140 = v142->m_sparseTables.m_UIElement_Translation.m_data.m_vector._Mypair._Myval2._Myfirst;
  v143 = v139 - v140;
  while ( (__int64)v143 > 0 )
  {
    if ( v140[v143 >> 1].first < this )
    {
      v140 += (v143 >> 1) + 1;
      v143 += -1LL - (v143 >> 1);
    }
    else
    {
      v143 >>= 1;
    }
  }
LABEL_224:
  if ( v140 == v139 || this < v140->first )
    v140 = v139;
  p_Z = &v140->second.Z;
  v87 = (char *)&v140->second.Z + 1;
LABEL_106:
  LOBYTE(v176.Z) = *(_BYTE *)p_Z;
  *(_WORD *)((char *)&v176.Z + 1) = *(_WORD *)v87;
  HIBYTE(v176.Z) = v87[2];
  if ( v176.Z == 0.0 && v3 )
  {
    CUIElement::GetHandOffVisualTransform(this, (xref_ptr<CTransform> *)&ppStowedExceptions);
    v88 = this->m_sharedState.m_ptr->m_value.m_coreServices;
    v89 = v88->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v90 = v88->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v91 = v89 - v90;
    while ( (__int64)v91 > 0 )
    {
      v92 = v91 >> 1 << 6;
      if ( *(const CDependencyObject **)((char *)&v90->first + v92) < this )
      {
        v90 = (std::pair<CDependencyObject const *,DOFacadeStorage> *)((char *)v90 + v92 + 64);
        v91 += -1LL - (v91 >> 1);
      }
      else
      {
        v91 >>= 1;
      }
    }
    if ( v90 == v89 || this < v90->first || v90 == (std::pair<CDependencyObject const *,DOFacadeStorage> *)-8LL )
      goto LABEL_300;
    v126 = (char *)v90->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v127 = (char *)v90->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v128 = (v126 - v127) / 48;
    while ( (__int64)v128 > 0 )
    {
      if ( *(_WORD *)&v127[48 * (v128 >> 1)] < 0x822u )
      {
        v127 += 48 * (v128 >> 1) + 48;
        v128 += -1LL - (v128 >> 1);
      }
      else
      {
        v128 >>= 1;
      }
    }
    if ( v127 == v126 || *(_WORD *)v127 > 0x822u || v127 == (char *)-8LL )
    {
LABEL_300:
      if ( (unsigned __int8)((__int64 (__fastcall *)(CUIElement *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                              this,
                              2082) )
      {
        v133 = this->m_sharedState.m_ptr->m_value.m_coreServices;
        v130 = v133->m_sparseTables.m_UIElement_Translation.m_data.m_vector._Mypair._Myval2._Mylast;
        v131 = v133->m_sparseTables.m_UIElement_Translation.m_data.m_vector._Mypair._Myval2._Myfirst;
        v134 = v130 - v131;
        while ( (__int64)v134 > 0 )
        {
          if ( v131[v134 >> 1].first < this )
          {
            v131 += (v134 >> 1) + 1;
            v134 += -1LL - (v134 >> 1);
          }
          else
          {
            v134 >>= 1;
          }
        }
LABEL_196:
        if ( v131 == v130 || this < v131->first )
          v131 = v130;
        p_second = &v131->second;
        goto LABEL_117;
      }
    }
    else if ( (unsigned __int8)((__int64 (__fastcall *)(CUIElement *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                                 this,
                                 2073) )
    {
      v129 = this->m_sharedState.m_ptr->m_value.m_coreServices;
      v130 = v129->m_sparseTables.m_UIElement_AnimatedTranslation.m_data.m_vector._Mypair._Myval2._Mylast;
      v131 = v129->m_sparseTables.m_UIElement_AnimatedTranslation.m_data.m_vector._Mypair._Myval2._Myfirst;
      v132 = v130 - v131;
      while ( (__int64)v132 > 0 )
      {
        if ( v131[v132 >> 1].first < this )
        {
          v131 += (v132 >> 1) + 1;
          v132 += -1LL - (v132 >> 1);
        }
        else
        {
          v132 >>= 1;
        }
      }
      goto LABEL_196;
    }
    p_second = &value;
LABEL_117:
    v94 = *(_QWORD *)&p_second->X;
    v95 = ppStowedExceptions;
    Z = p_second->Z;
    *(_QWORD *)&v176.X = *(_QWORD *)&p_second->X;
    v97 = *ppStowedExceptions;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v181 = 0;
    (*(void (__fastcall **)(_STOWED_EXCEPTION_INFORMATION_V2 **, __m128i *))&v97[12].NestedExceptionType)(
      ppStowedExceptions,
      &si128);
    if ( *(float *)si128.m128i_i32 != 1.0
      || *(float *)&si128.m128i_i32[1] != 0.0
      || *(float *)&si128.m128i_i32[2] != 0.0
      || *(float *)&si128.m128i_i32[3] != 1.0
      || *(float *)&v181 != 0.0
      || *((float *)&v181 + 1) != 0.0 )
    {
      m_pCombinedLocalTransform = builder.m_pCombinedLocalTransform;
      _11 = builder.m_pCombinedLocalTransform->_11;
      _12 = builder.m_pCombinedLocalTransform->_12;
      _21 = builder.m_pCombinedLocalTransform->_21;
      _22 = builder.m_pCombinedLocalTransform->_22;
      _31 = builder.m_pCombinedLocalTransform->_31;
      _32 = builder.m_pCombinedLocalTransform->_32;
      builder.m_pCombinedLocalTransform->_11 = (float)(_12 * *(float *)&si128.m128i_i32[2])
                                             + (float)(builder.m_pCombinedLocalTransform->_11 * *(float *)si128.m128i_i32);
      m_pCombinedLocalTransform->_12 = (float)(_12 * *(float *)&si128.m128i_i32[3])
                                     + (float)(_11 * *(float *)&si128.m128i_i32[1]);
      m_pCombinedLocalTransform->_21 = (float)(_22 * *(float *)&si128.m128i_i32[2])
                                     + (float)(_21 * *(float *)si128.m128i_i32);
      m_pCombinedLocalTransform->_22 = (float)(_22 * *(float *)&si128.m128i_i32[3])
                                     + (float)(_21 * *(float *)&si128.m128i_i32[1]);
      m_pCombinedLocalTransform->_31 = (float)((float)(_32 * *(float *)&si128.m128i_i32[2])
                                             + (float)(_31 * *(float *)si128.m128i_i32))
                                     + *(float *)&v181;
      m_pCombinedLocalTransform->_32 = (float)((float)(_32 * *(float *)&si128.m128i_i32[3])
                                             + (float)(_31 * *(float *)&si128.m128i_i32[1]))
                                     + *((float *)&v181 + 1);
    }
    if ( Z == 0.0 )
    {
      v105 = builder.m_pCombinedLocalTransform;
      v106 = v176.Y + builder.m_pCombinedLocalTransform->_32;
      builder.m_pCombinedLocalTransform->_31 = *(float *)&v94 + builder.m_pCombinedLocalTransform->_31;
      v105->_32 = v106;
    }
    if ( v95 )
      CDependencyObject::Release((CDependencyObject *)v95);
    return CMILMatrix::IsIdentity(pLocalTransform);
  }
LABEL_13:
  v14 = FLOAT_1_0;
  v15 = *((_DWORD *)this + 38) >> 5;
  *(float *)&cStowedExceptions = 0.0;
  dmOffsetX = 0.0;
  dmOffsetY = 0.0;
  dmUncompressedZoomFactor = 1.0;
  dmZoomFactorX = 1.0;
  dmZoomFactorY = 1.0;
  if ( (v15 & 1) != 0 && v3 )
  {
    v16 = 1;
    v151 = this->m_sharedState.m_ptr->m_value.m_coreServices;
    v152 = v151->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v153 = v151->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v154 = v152 - v153;
    while ( (__int64)v154 > 0 )
    {
      v155 = v154 >> 1 << 6;
      if ( *(const CDependencyObject **)((char *)&v153->first + v155) < this )
      {
        v153 = (std::pair<CDependencyObject const *,DOFacadeStorage> *)((char *)v153 + v155 + 64);
        v154 += -1LL - (v154 >> 1);
      }
      else
      {
        v154 >>= 1;
      }
    }
    if ( v153 != v152 && this >= v153->first && v153 != (std::pair<CDependencyObject const *,DOFacadeStorage> *)-8LL )
    {
      v156 = (char *)v153->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Mylast;
      v157 = (char *)v153->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Myfirst;
      v158 = (v156 - v157) / 48;
      while ( (__int64)v158 > 0 )
      {
        if ( *(_WORD *)&v157[48 * (v158 >> 1)] < 0x822u )
        {
          v157 += 48 * (v158 >> 1) + 48;
          v158 += -1LL - (v158 >> 1);
        }
        else
        {
          v158 >>= 1;
        }
      }
      if ( v157 != v156 && *(_WORD *)v157 <= 0x822u && v157 != (char *)-8LL )
      {
        if ( (unsigned __int8)((__int64 (__fastcall *)(CUIElement *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                                this,
                                2073) )
        {
          v159 = this->m_sharedState.m_ptr->m_value.m_coreServices;
          v108 = v159->m_sparseTables.m_UIElement_AnimatedTranslation.m_data.m_vector._Mypair._Myval2._Mylast;
          v109 = v159->m_sparseTables.m_UIElement_AnimatedTranslation.m_data.m_vector._Mypair._Myval2._Myfirst;
          v160 = v108 - v109;
          while ( (__int64)v160 > 0 )
          {
            if ( v109[v160 >> 1].first < this )
            {
              v109 += (v160 >> 1) + 1;
              v160 += -1LL - (v160 >> 1);
            }
            else
            {
              v160 >>= 1;
            }
          }
LABEL_134:
          if ( v109 == v108 || this < v109->first )
            v109 = v108;
          v17 = &v109->second;
          goto LABEL_17;
        }
        goto LABEL_16;
      }
    }
  }
  else
  {
    v16 = 0;
  }
  if ( (unsigned __int8)((__int64 (__fastcall *)(CUIElement *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                          this,
                          2082) )
  {
    v107 = this->m_sharedState.m_ptr->m_value.m_coreServices;
    v108 = v107->m_sparseTables.m_UIElement_Translation.m_data.m_vector._Mypair._Myval2._Mylast;
    v109 = v107->m_sparseTables.m_UIElement_Translation.m_data.m_vector._Mypair._Myval2._Myfirst;
    v110 = v108 - v109;
    while ( (__int64)v110 > 0 )
    {
      if ( v109[v110 >> 1].first < this )
      {
        v109 += (v110 >> 1) + 1;
        v110 += -1LL - (v110 >> 1);
      }
      else
      {
        v110 >>= 1;
      }
    }
    goto LABEL_134;
  }
LABEL_16:
  v17 = &value;
LABEL_17:
  Y = v17->Y;
  X = v17->X;
  v20 = ((double (__fastcall *)(CUIElement *))this->GetActualOffsetX)(this);
  v21 = *(float *)&v20 + X;
  v22 = ((double (__fastcall *)(CUIElement *))this->GetActualOffsetY)(this);
  v23 = this->__vftable;
  shouldFlipRTL = 0;
  shouldFlipRTLInPlace = 0;
  v24 = *(float *)&v22 + Y;
  v23->GetShouldFlipRTL(this, &shouldFlipRTL, &shouldFlipRTLInPlace);
  v25 = ((double (__fastcall *)(CUIElement *))this->GetActualWidth)(this);
  elementWidth = *(float *)&v25;
  v27 = ((double (__fastcall *)(CUIElement *))this->GetActualHeight)(this);
  elementHeight = *(float *)&v27;
  v29 = 1;
  if ( (*((_BYTE *)this + 144) & 8) == 0 )
    goto LABEL_18;
  m_ptr = this->m_sharedState.m_ptr->m_value.m_coreServices->m_inputServices.m_ptr;
  *(_QWORD *)&v176.X = m_ptr;
  dmOffsetX = 0.0;
  dmUncompressedZoomFactor = 1.0;
  dmZoomFactorX = 1.0;
  dmZoomFactorY = 1.0;
  if ( !m_ptr )
  {
    v118 = 0;
    goto LABEL_163;
  }
  v172 = 0;
  dmOffsetY = 0.0;
  v178._Ptr = 0;
  phkResult = 0;
  ppCompositorContent = 0;
  ppStowedExceptions = 0;
  pDMContentType[0] = XcpDMContentTypePrimary;
  v186 = 0;
  pContentOffsetX = 0.0;
  *(float *)&cStowedExceptions = 0.0;
  DirectManipulationServiceAndContent = CInputServices::GetDirectManipulationServiceAndContent(
                                          m_ptr,
                                          this,
                                          (IPALDirectManipulationService **)&v178,
                                          &ppCompositorContent,
                                          (IObject **)&ppStowedExceptions,
                                          pDMContentType,
                                          &pContentOffsetX,
                                          (float *)&cStowedExceptions);
  v113 = ppCompositorContent;
  v114 = DirectManipulationServiceAndContent;
  if ( DirectManipulationServiceAndContent < 0 )
    goto LABEL_204;
  if ( !ppCompositorContent )
    goto LABEL_205;
  v115 = v178._Ptr;
  v116 = phkResult;
  v117 = *(IObject **)(*(_QWORD *)&v178._Ptr->first + 352LL);
  ppCompositorContent = v117;
  if ( phkResult )
  {
    phkResult = 0;
    (*(void (__fastcall **)(HKEY__ *))(*(_QWORD *)v116 + 8LL))(v116);
    v117 = ppCompositorContent;
  }
  DirectManipulationServiceAndContent = ((__int64 (__fastcall *)(std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> *, HKEY__ **))v117)(
                                          v115,
                                          &phkResult);
  v114 = DirectManipulationServiceAndContent;
  if ( DirectManipulationServiceAndContent < 0
    || (DirectManipulationServiceAndContent = (*(__int64 (__fastcall **)(HKEY__ *, IObject *, _QWORD, int *, float *, float *, float *, float *, float *))(*(_QWORD *)phkResult + 16LL))(
                                                phkResult,
                                                v113,
                                                (unsigned int)pDMContentType[0],
                                                &v186,
                                                &dmOffsetX,
                                                &dmOffsetY,
                                                &dmUncompressedZoomFactor,
                                                &dmZoomFactorX,
                                                &dmZoomFactorY),
        v114 = DirectManipulationServiceAndContent,
        DirectManipulationServiceAndContent < 0) )
  {
LABEL_204:
    OnFailure_2990_(DirectManipulationServiceAndContent);
    goto LABEL_205;
  }
  if ( (v6 & 2) != 0 )
  {
    *(_QWORD *)pDMContentType = 0;
    Viewport = CInputServices::GetViewport(*(CInputServices **)&v176.X, 0, this, (CDMViewport **)pDMContentType);
    v114 = Viewport;
    if ( Viewport >= 0 )
    {
      if ( *(_QWORD *)pDMContentType && *(_BYTE *)(*(_QWORD *)pDMContentType + 272LL) )
      {
        v166 = *(float *)(*(_QWORD *)pDMContentType + 268LL);
        dmOffsetX = *(float *)(*(_QWORD *)pDMContentType + 264LL);
        dmOffsetY = v166;
      }
      xref_ptr<WindowsPresentTarget>::DecrementRefCount((xref_ptr<CD3D11Device> *)pDMContentType);
      goto LABEL_151;
    }
    OnFailure_2990_(Viewport);
    if ( *(_QWORD *)pDMContentType )
    {
      CXcpObjectBaseInternal<IObject,CXcpObjectThreadSafeAddRefPolicy>::InternalRelease(*(ImageSharingEngineHost::ImageSharingState **)pDMContentType);
      v118 = v172;
      goto LABEL_152;
    }
LABEL_205:
    v118 = v172;
    goto LABEL_152;
  }
LABEL_151:
  v118 = 1;
  dmOffsetX = dmOffsetX + (float)(pContentOffsetX * dmZoomFactorX);
  dmOffsetY = dmOffsetY + (float)(*(float *)&cStowedExceptions * dmZoomFactorY);
LABEL_152:
  if ( ppStowedExceptions )
    (*(void (__fastcall **)(_STOWED_EXCEPTION_INFORMATION_V2 **))&(*ppStowedExceptions)->ResultCode)(ppStowedExceptions);
  if ( v113 )
    v113->Release(v113);
  v119 = phkResult;
  if ( phkResult )
  {
    phkResult = 0;
    (*(void (__fastcall **)(HKEY__ *))(*(_QWORD *)v119 + 8LL))(v119);
  }
  if ( v178._Ptr )
    (*(void (__fastcall **)(std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> *))(*(_QWORD *)&v178._Ptr->first
                                                                                       + 8LL))(v178._Ptr);
  if ( v114 < 0 )
  {
    OnFailure_2990_(v114);
    OnFailure_2990_(v114);
    ppStowedExceptions = 0;
    *(float *)&cStowedExceptions = 0.0;
    TraceForFailFast(v114);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v114, cStowedExceptions, ppStowedExceptions);
  }
  v29 = 1;
LABEL_163:
  v120 = this->GetTypeIndex(this);
  if ( v120 == TextBoxView )
    goto LABEL_171;
  if ( (unsigned __int16)v120 >= (XYFocusNavigationStrategy|IVectorOfUri) )
  {
    for ( i = v120; ; i = ClassInfoByIndex->m_nBaseTypeIndex )
    {
      ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(i);
      if ( ClassInfoByIndex->m_nIndex == UnknownType )
        break;
      if ( ClassInfoByIndex->m_nIndex == TextBoxView )
      {
        v123 = 1;
        goto LABEL_170;
      }
    }
    v123 = 0;
LABEL_170:
    if ( v123 )
    {
LABEL_171:
      m_pTextFormatting = this->m_pTextFormatting;
      v125 = 0.0;
      if ( m_pTextFormatting )
      {
        if ( m_pTextFormatting->m_nFlowDirection[0] == 1 )
        {
          v125 = *((float *)&this[1] + 37) - this[1].m_eOpacityPrivate;
          if ( v125 <= 0.0 )
            v125 = 0.0;
        }
      }
      dmOffsetX = dmOffsetX + v125;
    }
  }
  cStowedExceptions = v118 != 0;
LABEL_18:
  v30 = *((_DWORD *)this + 38) >> 12;
  memset(&facadeInfo, 0, sizeof(facadeInfo));
  if ( (v30 & 1) != 0 )
  {
    if ( !v16 )
      goto LABEL_301;
    v31 = this->m_sharedState.m_ptr->m_value.m_coreServices;
    v32 = v31->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v33 = v31->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v34 = v32 - v33;
    while ( (__int64)v34 > 0 )
    {
      v35 = v34 >> 1 << 6;
      if ( *(const CDependencyObject **)((char *)&v33->first + v35) < this )
      {
        v33 = (std::pair<CDependencyObject const *,DOFacadeStorage> *)((char *)v33 + v35 + 64);
        v34 += -1LL - (v34 >> 1);
      }
      else
      {
        v34 >>= 1;
      }
    }
    if ( v33 == v32 || this < v33->first || v33 == (std::pair<CDependencyObject const *,DOFacadeStorage> *)-8LL )
      goto LABEL_301;
    v65 = (char *)v33->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v66 = (char *)v33->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v67 = (v65 - v66) / 48;
    while ( (__int64)v67 > 0 )
    {
      if ( *(_WORD *)&v66[48 * (v67 >> 1)] < 0x81Fu )
      {
        v66 += 48 * (v67 >> 1) + 48;
        v67 += -1LL - (v67 >> 1);
      }
      else
      {
        v67 >>= 1;
      }
    }
    if ( v66 == v65 || *(_WORD *)v66 > 0x81Fu || v66 == (char *)-8LL )
    {
LABEL_301:
      if ( SimpleProperty::Property::id<2079>::IsSet(this) )
        ImplSparse_48 = SimpleProperty::details::GetImplSparse_48_(
                          &this->m_sharedState.m_ptr->m_value.m_coreServices->m_sparseTables.m_UIElement_Scale,
                          this);
      else
        ImplSparse_48 = &`SimpleProperty::Property::Default<2079>'::`2'::s_default;
      v37 = *(_QWORD *)&ImplSparse_48->X;
      v38 = ImplSparse_48->Z;
      *(_QWORD *)&facadeInfo.scale.X = v37;
      facadeInfo.scale.Z = v38;
      if ( !v16 )
        goto LABEL_37;
    }
    else
    {
      Impl_2071 = SimpleProperty::details::GetImpl_2071_(this, (SimpleProperty::details::tag_storage<1>)v67);
      v69 = Impl_2071->Z;
      *(_QWORD *)&facadeInfo.scale.X = *(_QWORD *)&Impl_2071->X;
      facadeInfo.scale.Z = v69;
    }
    v39 = this->m_sharedState.m_ptr->m_value.m_coreServices;
    v40 = v39->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Mylast;
    v41 = v39->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Myfirst;
    v42 = v40 - v41;
    while ( (__int64)v42 > 0 )
    {
      v43 = v42 >> 1 << 6;
      if ( *(const CDependencyObject **)((char *)&v41->first + v43) < this )
      {
        v41 = (std::pair<CDependencyObject const *,DOFacadeStorage> *)((char *)v41 + v43 + 64);
        v42 += -1LL - (v42 >> 1);
      }
      else
      {
        v42 >>= 1;
      }
    }
    if ( v41 != v40 && this >= v41->first && v41 != (std::pair<CDependencyObject const *,DOFacadeStorage> *)-8LL )
    {
      v74 = (char *)v41->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Mylast;
      v75 = (char *)v41->second.m_doFacadeAnimationMap.m_data.m_vector._Mypair._Myval2._Myfirst;
      v76 = (v74 - v75) / 48;
      while ( (__int64)v76 > 0 )
      {
        if ( *(_WORD *)&v75[48 * (v76 >> 1)] < 0x81Du )
        {
          v75 += 48 * (v76 >> 1) + 48;
          v76 += -1LL - (v76 >> 1);
        }
        else
        {
          v76 >>= 1;
        }
      }
      if ( v75 != v74 && *(_WORD *)v75 <= 0x81Du && v75 != (char *)-8LL )
      {
        Impl_2069 = SimpleProperty::details::GetImpl_2069_(this, (SimpleProperty::details::tag_storage<1>)v76);
        LODWORD(facadeInfo.rotationAngleInDegrees) = LODWORD(Impl_2069) ^ _xmm;
LABEL_40:
        v46 = this->m_sharedState.m_ptr->m_value.m_coreServices;
        v47 = v46->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Mylast;
        v48 = v46->m_facadeStorage.m_doFacadeMap.m_data.m_vector._Mypair._Myval2._Myfirst;
        v49 = v47 - v48;
        while ( (__int64)v49 > 0 )
        {
          v50 = v49 >> 1 << 6;
          if ( *(const CDependencyObject **)((char *)&v48->first + v50) < this )
          {
            v48 = (std::pair<CDependencyObject const *,DOFacadeStorage> *)((char *)v48 + v50 + 64);
            v49 += -1LL - (v49 >> 1);
          }
          else
          {
            v49 >>= 1;
          }
        }
        if ( v48 != v47 && this >= v48->first )
        {
          v51 = (containers::detail::vector_tree<containers::detail::map_traits<enum KnownPropertyIndex,DOFacadeAnimationInfo,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> >,0> > *)&v48->second;
          if ( v51 )
          {
            v70 = v51[1].m_data.m_vector._Mypair._Myval2._Mylast;
            v71 = v51[1].m_data.m_vector._Mypair._Myval2._Myfirst;
            v72 = v70 - v71;
            while ( (__int64)v72 > 0 )
            {
              if ( v71[v72 >> 1].first < UIElement_RotationAxis )
              {
                v71 += (v72 >> 1) + 1;
                v72 += -1LL - (v72 >> 1);
              }
              else
              {
                v72 >>= 1;
              }
            }
            if ( v71 == v70 || (v178._Ptr = v71, v71->first > UIElement_RotationAxis) )
              v178._Ptr = v70;
            v73 = containers::detail::vector_tree<containers::detail::map_traits<enum KnownPropertyIndex,DOFacadeAnimationInfo,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo>>,0>>::end(
                    v51 + 1,
                    (std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *)&v176);
            if ( std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo>>>>::operator!=(
                   &v178,
                   v73)
              && std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo>>>>::operator->((std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *)&v178) != (std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> *)-8LL )
            {
              v52 = SimpleProperty::Property::id<2070>::Get(this);
              goto LABEL_48;
            }
          }
        }
LABEL_47:
        v52 = SimpleProperty::Property::id<2078>::Get(this);
LABEL_48:
        v53 = *(_QWORD *)&v52->X;
        facadeInfo.rotationAxis.Z = v52->Z;
        *(_QWORD *)&facadeInfo.rotationAxis.X = v53;
        facadeInfo.transformMatrix = *CUIElement::GetTransformMatrix(this, &result, v16);
        facadeInfo.centerPoint = *CUIElement::GetCenterPoint(this, &v176, v16);
        facadeInfo.translationZ = CUIElement::GetTranslation(this, &v176, v16)->Z;
        goto LABEL_49;
      }
    }
LABEL_37:
    if ( (unsigned __int8)((__int64 (__fastcall *)(CUIElement *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                            this,
                            2077) )
      ImplSparse_140 = SimpleProperty::details::GetImplSparse_140_(
                         &this->m_sharedState.m_ptr->m_value.m_coreServices->m_sparseTables.m_UIElement_Rotation,
                         this);
    else
      ImplSparse_140 = 0.0;
    v45 = ImplSparse_140;
    LODWORD(facadeInfo.rotationAngleInDegrees) = LODWORD(v45) ^ _xmm;
    if ( !v16 )
      goto LABEL_47;
    goto LABEL_40;
  }
LABEL_49:
  p_facadeInfo = &facadeInfo;
  if ( !CUIElement::AreFacadesInUse(this) )
    p_facadeInfo = 0;
  if ( DCompTreeHost::ContainerVisualsEnabled() || !v3 )
  {
    ctl::ComPtr<Windows::UI::Xaml::IUIElement>::ComPtr<Windows::UI::Xaml::IUIElement>((std::pair<int,int> *)&ppStowedExceptions);
    v29 = 0;
    v56 = 2;
  }
  else
  {
    HandOffVisualTransform = (std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *)CUIElement::GetHandOffVisualTransform(this, (xref_ptr<CTransform> *)&ppCompositorContent);
    v56 = 0;
  }
  pHandOffVisualTransform = (CTransform *)std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo>>>>::operator->(HandOffVisualTransform);
  TransitionTarget = (std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo> > > > *)CUIElement::GetTransitionTarget(this, (xref_ptr<CTransitionTarget> *)&v176);
  pTransitionTarget = (CTransitionTarget *)std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<enum KnownPropertyIndex,DOFacadeAnimationInfo>>>>::operator->(TransitionTarget);
  renderTransformOrigin = **(XPOINTF **)&CUIElement::GetRenderTransformOrigin(this);
  pRenderTransform = CUIElement::GetRenderTransformLocal(this);
  if ( *(float *)&cStowedExceptions == 0.0 )
  {
    v62 = FLOAT_1_0;
    v63 = 0.0;
  }
  else
  {
    v14 = dmZoomFactorY;
    v62 = dmZoomFactorX;
    v9 = dmOffsetY;
    v63 = dmOffsetX;
  }
  CUIElement::GetLocalTransformHelper(
    &builder,
    v21,
    v24,
    0,
    v63,
    v9,
    v62,
    v14,
    shouldFlipRTL,
    shouldFlipRTLInPlace,
    elementWidth,
    elementHeight,
    pRenderTransform,
    renderTransformOrigin,
    pTransitionTarget,
    1,
    0,
    pHandOffVisualTransform,
    0,
    p_facadeInfo);
  xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&v176);
  if ( v56 )
    xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&ppStowedExceptions);
  if ( v29 )
    xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&ppCompositorContent);
  return CMILMatrix::IsIdentity(pLocalTransform);
}

```

## disassembly

```asm
0x180101ca0  mov     [rsp-8+arg_8], rbx
0x180101ca5  push    rbp
0x180101ca6  push    rsi
0x180101ca7  push    rdi
0x180101ca8  push    r12
0x180101caa  push    r13
0x180101cac  push    r14
0x180101cae  push    r15
0x180101cb0  lea     rbp, [rsp-150h]
0x180101cb8  sub     rsp, 270h
0x180101cbf  movaps  [rsp+2A0h+var_A0], xmm12
0x180101cc8  mov     rax, cs:__security_cookie
0x180101ccf  xor     rax, rsp
0x180101cd2  mov     [rbp+180h+var_B0], rax
0x180101cd9  xor     r12d, r12d
0x180101cdc  mov     qword ptr [pLocalTransform], 3F800000h
0x180101ce3  movzx   r15d, transformRetrievalOptions
0x180101ce7  mov     [pLocalTransform+8], r12d
0x180101ceb  and     r15b, 1
0x180101cef  mov     qword ptr [pLocalTransform+0Ch], 3F800000h
0x180101cf7  cmp     cs:s_containerVisualsEnabledInitialized, r12b
0x180101cfe  lea     rax, ??_7XamlLocalTransformBuilder@@6B@; const XamlLocalTransformBuilder::`vftable'
0x180101d05  mov     rsi, pLocalTransform
0x180101d08  mov     [pLocalTransform+14h], r12d
0x180101d0c  movzx   r14d, transformRetrievalOptions
0x180101d10  mov     [rbp+180h+builder.m_state], r12d
0x180101d14  mov     rbx, this
0x180101d17  mov     [rbp+180h+builder.__vftable], rax
0x180101d1b  mov     [rbp+180h+builder.m_pCombinedLocalTransform], pLocalTransform
0x180101d1f  jz      loc_180102EFA
0x180101d25  movzx   eax, cs:s_containerVisualsEnabled
0x180101d2c  movaps  [rsp+2A0h+var_40], xmm6
0x180101d34  xorps   xmm12, xmm12
0x180101d38  movaps  [rsp+2A0h+var_50], xmm7
0x180101d40  movaps  [rsp+2A0h+var_60], xmm8
0x180101d49  movaps  [rsp+2A0h+var_70], xmm9
0x180101d52  movaps  [rsp+2A0h+var_80], xmm10
0x180101d5b  movaps  [rsp+2A0h+var_90], xmm11
0x180101d64  test    al, al
0x180101d66  jz      loc_180101DFB
0x180101d6c  mov     rax, [rbx]
0x180101d6f  mov     this, rbx
0x180101d72  mov     rax, [rax+258h]
0x180101d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101d7e  movzx   edi, ax
0x180101d81  mov     r13d, 30Bh
0x180101d87  cmp     r13w, di
0x180101d8b  jz      short loc_180101DFB
0x180101d8d  mov     eax, 43Ch
0x180101d92  cmp     di, ax
0x180101d95  jb      short loc_180101DEA
0x180101d97  lea     this, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180101d9e  call    cs:__imp_EnterCriticalSection
0x180101da4  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x180101da9  lea     ecx, [rdi-43Ch]
0x180101daf  mov     rax, [rax+60h]
0x180101db3  mov     rdi, [rax+this*8]
0x180101db7  lea     this, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180101dbe  call    cs:__imp_LeaveCriticalSection
0x180101dc4  movzx   eax, word ptr [rdi]
0x180101dc7  test    ax, ax
0x180101dca  jz      loc_18010232D
0x180101dd0  cmp     ax, r13w
0x180101dd4  jz      short loc_180101DE4
0x180101dd6  movzx   ecx, word ptr [rdi+2]; eTypeIndex
0x180101dda  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x180101ddf  mov     rdi, rax
0x180101de2  jmp     short loc_180101DC4
0x180101de4  mov     al, 1
0x180101de6  test    al, al
0x180101de8  jnz     short loc_180101DFB
0x180101dea  mov     eax, [rbx+94h]
0x180101df0  shr     eax, 8
0x180101df3  test    al, 1
0x180101df5  jnz     loc_1801024F6
0x180101dfb  mov     r13d, 822h
0x180101e01  mov     eax, [rbx+98h]
0x180101e07  movss   xmm8, cs:__real@3f800000
0x180101e10  shr     eax, 5
0x180101e13  mov     [rbp+180h+cStowedExceptions], r12d
0x180101e17  mov     [rbp+180h+dmOffsetX], 0
0x180101e1e  mov     [rbp+180h+dmOffsetY], 0
0x180101e25  mov     [rbp+180h+dmUncompressedZoomFactor], 3F800000h
0x180101e2c  mov     [rbp+180h+dmZoomFactorX], 3F800000h
0x180101e33  mov     [rbp+180h+dmZoomFactorY], 3F800000h
0x180101e3a  test    al, 1
0x180101e3c  jnz     loc_18010300B
0x180101e42  xor     dil, dil
0x180101e45  movsxd  this, cs:dword_180C26FD0
0x180101e4c  mov     edx, r13d
0x180101e4f  mov     rax, cs:?query@?$sparse_host@VCUIElement@@@SimpleProperty@@2Q8CUIElement@@EBA_NW4KnownPropertyIndex@@@ZEQ3@; bool (CUIElement::*SimpleProperty::sparse_host<CUIElement>::query)(KnownPropertyIndex)
0x180101e56  add     this, rbx
0x180101e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e5e  test    al, al
0x180101e60  jnz     loc_18010287B
0x180101e66  lea     this, value
0x180101e6d  mov     rax, [rbx]
0x180101e70  movss   xmm7, dword ptr [this+4]
0x180101e75  movss   xmm6, dword ptr [this]
0x180101e79  mov     this, rbx
0x180101e7c  mov     rax, [rax+358h]
0x180101e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e88  mov     rax, [rbx]
0x180101e8b  movaps  xmm9, xmm0
0x180101e8f  mov     this, rbx
0x180101e92  addss   xmm9, xmm6
0x180101e97  mov     rax, [rax+360h]
0x180101e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ea3  mov     rax, [rbx]
0x180101ea6  lea     pLocalTransform, [rbp+180h+shouldFlipRTLInPlace]
0x180101eaa  movaps  xmm10, xmm0
0x180101eae  mov     [rbp+180h+shouldFlipRTL], r12d
0x180101eb2  lea     rdx, [rbp+180h+shouldFlipRTL]
0x180101eb6  mov     [rbp+180h+shouldFlipRTLInPlace], r12d
0x180101eba  mov     this, rbx
0x180101ebd  addss   xmm10, xmm7
0x180101ec2  mov     rax, [rax+2C8h]
0x180101ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ece  mov     rax, [rbx]
0x180101ed1  mov     this, rbx
0x180101ed4  mov     rax, [rax+2E8h]
0x180101edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ee0  mov     rax, [rbx]
0x180101ee3  mov     this, rbx
0x180101ee6  movaps  xmm7, xmm0
0x180101ee9  mov     rax, [rax+2F0h]
0x180101ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ef5  test    byte ptr [rbx+90h], 8
0x180101efc  movaps  xmm11, xmm0
0x180101f00  mov     r13d, 1
0x180101f06  jnz     loc_18010294B
0x180101f0c  mov     eax, [rbx+98h]
0x180101f12  xorps   xmm0, xmm0
0x180101f15  shr     eax, 0Ch
0x180101f18  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M42], xmm0
0x180101f1f  movups  xmmword ptr [rbp+180h+facadeInfo.scale.X], xmm0
0x180101f23  movups  xmmword ptr [rbp+180h+facadeInfo.rotationAxis.X], xmm0
0x180101f27  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M12], xmm0
0x180101f2e  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M22], xmm0
0x180101f35  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M32], xmm0
0x180101f3c  movups  xmmword ptr [rbp+180h+facadeInfo.centerPoint.X], xmm0
0x180101f43  test    al, 1
0x180101f45  jz      loc_180102156
0x180101f4b  mov     r14d, 81Dh
0x180101f51  test    dil, dil
0x180101f54  jz      short loc_180101FB0
0x180101f56  mov     rax, [rbx+10h]
0x180101f5a  mov     rax, [rax]
0x180101f5d  mov     r9, [rax+980h]
0x180101f64  mov     rax, [rax+978h]
0x180101f6b  mov     rdx, r9
0x180101f6e  sub     rdx, rax
0x180101f71  sar     rdx, 6
0x180101f75  test    rdx, rdx
0x180101f78  jle     short loc_180101F99
0x180101f7a  mov     pLocalTransform, rdx
0x180101f7d  shr     pLocalTransform, 1
0x180101f80  mov     r10, pLocalTransform
0x180101f83  shl     r10, 6
0x180101f87  cmp     [r10+rax], rbx
0x180101f8b  jb      loc_1801022E2
0x180101f91  mov     rdx, pLocalTransform
0x180101f94  test    rdx, rdx
0x180101f97  jg      short loc_180101F7A
0x180101f99  cmp     rax, r9
0x180101f9c  jz      short loc_180101FB0
0x180101f9e  cmp     rbx, [rax]
0x180101fa1  jb      short loc_180101FB0
0x180101fa3  lea     this, [rax+8]
0x180101fa7  test    this, this
0x180101faa  jnz     loc_180102334
0x180101fb0  mov     this, rbx; obj
0x180101fb3  call    ?IsSet@?$id@$0IBP@@Property@SimpleProperty@@SA_NPEBX@Z; SimpleProperty::Property::id<2079>::IsSet(void const *)
0x180101fb8  test    al, al
0x180101fba  jnz     loc_1801031E5
0x180101fc0  lea     rax, ?s_default@?1???$Default@$0IBP@@Property@SimpleProperty@@SAAEBUVector3@Numerics@Foundation@Windows@@XZ@4U3456@B; Windows::Foundation::Numerics::Vector3 const `SimpleProperty::Property::Default<2079>(void)'::`2'::s_default
0x180101fc7  movsd   xmm0, qword ptr [rax]
0x180101fcb  mov     eax, [rax+8]
0x180101fce  movsd   qword ptr [rbp+180h+facadeInfo.scale.X], xmm0
0x180101fd3  mov     [rbp+180h+facadeInfo.scale.Z], eax
0x180101fd6  test    dil, dil
0x180101fd9  jz      short loc_180102035
0x180101fdb  mov     rax, [rbx+10h]
0x180101fdf  mov     rax, [rax]
0x180101fe2  mov     r9, [rax+980h]
0x180101fe9  mov     rax, [rax+978h]
0x180101ff0  mov     rdx, r9
0x180101ff3  sub     rdx, rax
0x180101ff6  sar     rdx, 6
0x180101ffa  test    rdx, rdx
0x180101ffd  jle     short loc_18010201E
0x180101fff  mov     pLocalTransform, rdx
0x180102002  shr     pLocalTransform, 1
0x180102005  mov     r10, pLocalTransform
0x180102008  shl     r10, 6
0x18010200c  cmp     [r10+rax], rbx
0x180102010  jb      loc_180102314
0x180102016  mov     rdx, pLocalTransform
0x180102019  test    rdx, rdx
0x18010201c  jg      short loc_180101FFF
0x18010201e  cmp     rax, r9
0x180102021  jz      short loc_180102035
0x180102023  cmp     rbx, [rax]
0x180102026  jb      short loc_180102035
0x180102028  lea     this, [rax+8]
0x18010202c  test    this, this
0x18010202f  jnz     loc_18010246B
0x180102035  movsxd  this, cs:dword_180C26FD0
0x18010203c  mov     edx, r14d
0x18010203f  mov     rax, cs:?query@?$sparse_host@VCUIElement@@@SimpleProperty@@2Q8CUIElement@@EBA_NW4KnownPropertyIndex@@@ZEQ3@; bool (CUIElement::*SimpleProperty::sparse_host<CUIElement>::query)(KnownPropertyIndex)
0x180102046  add     this, rbx
0x180102049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010204e  test    al, al
0x180102050  jnz     loc_180103200
0x180102056  xorps   xmm0, xmm0
0x180102059  cvtsd2ss xmm0, xmm0
0x18010205d  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180102064  movss   [rbp+180h+facadeInfo.rotationAngleInDegrees], xmm0
0x180102069  test    dil, dil
0x18010206c  jz      short loc_1801020C5
0x18010206e  mov     rax, [rbx+10h]
0x180102072  mov     rax, [rax]
0x180102075  mov     r9, [rax+980h]
0x18010207c  mov     rax, [rax+978h]
0x180102083  mov     rdx, r9
0x180102086  sub     rdx, rax
0x180102089  sar     rdx, 6
0x18010208d  test    rdx, rdx
0x180102090  jle     short loc_1801020B1
0x180102092  mov     pLocalTransform, rdx
0x180102095  shr     pLocalTransform, 1
0x180102098  mov     r10, pLocalTransform
0x18010209b  shl     r10, 6
0x18010209f  cmp     [r10+rax], rbx
0x1801020a3  jb      loc_1801022FB
0x1801020a9  mov     rdx, pLocalTransform
0x1801020ac  test    rdx, rdx
0x1801020af  jg      short loc_180102092
0x1801020b1  cmp     rax, r9
0x1801020b4  jz      short loc_1801020C5
0x1801020b6  cmp     rbx, [rax]
0x1801020b9  jb      short loc_1801020C5
0x1801020bb  add     rax, 8
0x1801020bf  jnz     loc_1801023C1
0x1801020c5  mov     this, rbx; obj
0x1801020c8  call    ?Get@?$id@$0IBO@@Property@SimpleProperty@@SAAEBUVector3@Numerics@Foundation@Windows@@PEBX@Z; SimpleProperty::Property::id<2078>::Get(void const *)
0x1801020cd  mov     ecx, [rax+8]
0x1801020d0  lea     rdx, [rbp+180h+result]; result
0x1801020d4  movsd   xmm0, qword ptr [rax]
0x1801020d8  movzx   r8d, dil; preferAnimatingValue
0x1801020dc  mov     [rbp+180h+facadeInfo.rotationAxis.Z], ecx
0x1801020df  mov     this, rbx; this
0x1801020e2  movsd   qword ptr [rbp+180h+facadeInfo.rotationAxis.X], xmm0
0x1801020e7  call    ?GetTransformMatrix@CUIElement@@QEBA?AUMatrix4x4@Numerics@Foundation@Windows@@_N@Z; CUIElement::GetTransformMatrix(bool)
0x1801020ec  movzx   r8d, dil; preferAnimatingValue
0x1801020f0  lea     rdx, [rbp+180h+var_1D0]; result
0x1801020f4  mov     this, rbx; this
0x1801020f7  movups  xmm0, xmmword ptr [rax]
0x1801020fa  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M11], xmm0
0x1801020fe  movups  xmm1, xmmword ptr [rax+10h]
0x180102102  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M21], xmm1
0x180102109  movups  xmm0, xmmword ptr [rax+20h]
0x18010210d  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M31], xmm0
0x180102114  movups  xmm1, xmmword ptr [rax+30h]
0x180102118  movups  xmmword ptr [rbp+180h+facadeInfo.transformMatrix.M41], xmm1
0x18010211f  call    ?GetCenterPoint@CUIElement@@QEBA?AUVector3@Numerics@Foundation@Windows@@_N@Z; CUIElement::GetCenterPoint(bool)
0x180102124  movzx   r8d, dil; preferAnimatingValue
0x180102128  lea     rdx, [rbp+180h+var_1D0]; result
0x18010212c  mov     this, rbx; this
0x18010212f  movsd   xmm0, qword ptr [rax]
0x180102133  movsd   qword ptr [rbp+180h+facadeInfo.centerPoint.X], xmm0
0x18010213b  mov     eax, [rax+8]
0x18010213e  mov     [rbp+180h+facadeInfo.centerPoint.Z], eax
0x180102144  call    ?GetTranslation@CUIElement@@QEBA?AUVector3@Numerics@Foundation@Windows@@_N@Z; CUIElement::GetTranslation(bool)
0x180102149  movss   xmm0, dword ptr [rax+8]
0x18010214e  movss   [rbp+180h+facadeInfo.translationZ], xmm0
0x180102156  mov     this, rbx; this
0x180102159  call    ?AreFacadesInUse@CUIElement@@QEBA_NXZ; CUIElement::AreFacadesInUse(void)
0x18010215e  test    al, al
0x180102160  lea     rdi, [rbp+180h+facadeInfo]
0x180102164  cmovz   rdi, r12
0x180102168  call    ?ContainerVisualsEnabled@DCompTreeHost@@SA_NXZ; DCompTreeHost::ContainerVisualsEnabled(void)
0x18010216d  test    al, al
0x18010216f  jz      loc_18010321B
0x180102175  lea     this, [rbp+180h+ppStowedExceptions]; this
0x180102179  call    ??0?$ComPtr@UIUIElement@Xaml@UI@Windows@@@ctl@@QEAA@XZ; ctl::ComPtr<Windows::UI::Xaml::IUIElement>::ComPtr<Windows::UI::Xaml::IUIElement>(void)
0x18010217e  mov     r13d, r12d
0x180102181  mov     r14d, 2
0x180102187  mov     this, rax; this
0x18010218a  call    ??C?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@W4KnownPropertyIndex@@VDOFacadeAnimationInfo@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@W4KnownPropertyIndex@@VDOFacadeAnimationInfo@@@1@XZ; std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<KnownPropertyIndex,DOFacadeAnimationInfo>>>>::operator->(void)
0x18010218f  lea     rdx, [rbp+180h+var_1D0]; result
0x180102193  mov     this, rbx; this
0x180102196  mov     r15, rax
0x180102199  call    ?GetTransitionTarget@CUIElement@@QEBA?AV?$xref_ptr@VCTransitionTarget@@@@XZ; CUIElement::GetTransitionTarget(void)
0x18010219e  mov     this, rax; this
0x1801021a1  call    ??C?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@W4KnownPropertyIndex@@VDOFacadeAnimationInfo@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@W4KnownPropertyIndex@@VDOFacadeAnimationInfo@@@1@XZ; std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<KnownPropertyIndex,DOFacadeAnimationInfo>>>>::operator->(void)
0x1801021a6  lea     rdx, [rbp+180h+var_1B8]
0x1801021aa  mov     this, rbx; this
0x1801021ad  mov     r12, rax
0x1801021b0  call    ?GetRenderTransformOrigin@CUIElement@@QEBA?AUXPOINTF@@XZ; CUIElement::GetRenderTransformOrigin(void)
  ... truncated ...
```
