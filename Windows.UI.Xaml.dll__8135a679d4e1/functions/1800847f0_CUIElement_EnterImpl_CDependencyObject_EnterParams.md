# CUIElement::EnterImpl(CDependencyObject *,EnterParams)

- ea: `0x1800847f0`
- end: `0x180085c56`
- name: `?EnterImpl@CUIElement@@MEAAJPEAVCDependencyObject@@UEnterParams@@@Z`
- size: `5222`
- prototype: `HRESULT __fastcall(CUIElement *this, CDependencyObject *pNamescopeOwner, EnterParams params)`
- caller_count: `1`
- callee_count: `58`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180084420`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18001fe10`
- `0x1800207b0`
- `0x1800217b8`
- `0x180021840`
- `0x180021970`
- `0x180027f60`
- `0x18003fcfc`
- `0x180053680`
- `0x18006c2b0`
- `0x180070c4c`
- `0x1800710d0`
- `0x1800724b8`
- `0x18007d630`
- `0x1800841e8`
- `0x1800847f0`
- `0x180086790`
- `0x18008e368`
- `0x1800a21e0`
- `0x180100a40`
- `0x180100b70`
- `0x180100ca0`
- `0x180101870`
- `0x180131190`
- `0x180135e20`
- `0x1801376ac`
- `0x1801462b0`
- `0x1801468a0`
- `0x180147cec`
- `0x1801c3570`
- `0x1801c3dac`
- `0x1801c3f68`
- `0x1801c441c`
- `0x1801c80a0`
- `0x1801df610`
- `0x180208734`
- `0x1802b4018`
- `0x1802b4120`
- `0x1802b4358`
- `0x180354ee0`
- `0x1804fe8fc`
- `0x1804fedf8`
- `0x18054e2c4`
- `0x1805ba1e0`
- `0x180687a78`
- `0x180688828`
- `0x18069f6ac`
- `0x1806d15a4`
- `0x1806e40dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085711`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180084cfd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180084cfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085802`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800858b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085802`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800858b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800857d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085882`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800857d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800858cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800858cb`

## pseudocode

```c
__int64 __fastcall CUIElement::EnterImpl(CUIElement *this, CDependencyObject *pNamescopeOwner, EnterParams *params)
{
  int v4; // edi
  _QWORD *ThreadLocalStoragePointer; // rax
  bool v8; // al
  int v9; // edi
  VisualTree *visualTree; // xmm1_8
  HRESULT v11; // eax
  unsigned int v12; // edi
  xref_ptr<CFlyoutBase> *v13; // rax
  std::nothrow_t *v14; // rdx
  bool v15; // r9
  CDependencyObject *v16; // rcx
  __int64 *m_ptr; // rdi
  CUIElementCollection *m_pChildren; // rcx
  __int64 *v19; // rcx
  unsigned int v20; // r14d
  unsigned int v21; // r13d
  VisualTree *v22; // rax
  bool v23; // dl
  CCoreServices *m_coreServices; // rcx
  HKEY m_coreContentRoot; // r14
  CXcpList<REQUEST> *m_pEventList; // r14
  unsigned int m_layoutFlags; // esi
  const CPropertyBase *PropertyBaseByIndex; // rdx
  Flyweight::ValueObjectWrapper<CDOSharedState> *v29; // rax
  HRESULT v30; // eax
  bool v31; // dl
  const CDependencyProperty *DependencyPropertyByIndex; // rax
  unsigned __int64 v33; // rsi
  __int64 m_nIndex; // r12
  __int64 v35; // r14
  const CClassInfo *ClassInfoByIndex; // rax
  bool v37; // al
  unsigned __int8 m_nPropertySlotCount; // cl
  unsigned int v39; // edx
  CDependencyObject::BitField v40; // r8
  unsigned int v41; // eax
  unsigned __int8 v42; // cf
  __int64 v43; // rcx
  CRectangleGeometry *m_pLayoutClipGeometry; // rcx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  __int64 v48; // rdi
  KnownTypeIndex v49; // ax
  __int64 StableXbfTypeIndex; // rsi
  __int64 v51; // rax
  RuntimeProfiler::ProfileGroup v52; // eax
  RuntimeProfiler::CDynamicProfiler *DynamicProfiler; // rax
  DirectUI::DXamlCore *v55; // rdi
  HRESULT PeerPrivate; // eax
  HRESULT v57; // esi
  Windows::UI::Xaml::IDependencyObject *v58; // r15
  int v59; // edi
  unsigned int v60; // esi
  unsigned int v61; // r14d
  VisualTree *v62; // xmm1_8
  HRESULT v63; // eax
  RuntimeFeatureBehavior::RuntimeEnabledFeatureDetector *Ptr; // rsi
  unsigned __int8 v65; // di
  char v66; // di
  HRESULT v67; // eax
  HRESULT ValueByIndex; // eax
  unsigned __int64 m_handle; // rdx
  unsigned __int64 m_handleMask; // rcx
  containers::vector_map<enum KnownPropertyIndex,EffectiveValue,std::less<void>,std::allocator<std::pair<enum KnownPropertyIndex,EffectiveValue> > > *Myval2; // rcx
  std::pair<enum KnownPropertyIndex,EffectiveValue> *Mylast; // r11
  std::pair<enum KnownPropertyIndex,EffectiveValue> *Myfirst; // rcx
  KnownPropertyIndex v74; // r10
  unsigned __int64 v75; // rdx
  unsigned __int64 v76; // rax
  std::pair<enum KnownPropertyIndex,EffectiveValue> *v77; // r9
  bool v78; // zf
  LayoutTransitionStorage *m_pLayoutTransitionStorage; // rdi
  CEventManager *v80; // r15
  CXcpList<REQUEST> *FailFast; // rax
  unsigned int v82; // edx
  CXcpList<REQUEST> *v83; // rdi
  CXcpList<REQUEST>::XCPListNode *i; // r14
  REQUEST *m_pData; // r12
  CXcpList<REQUEST>::XCPListNode *m_pHead; // r13
  CXcpList<REQUEST>::XCPListNode *v87; // rax
  CXcpList<REQUEST>::XCPListNode *j; // r14
  HRESULT v89; // eax
  CXcpList<REQUEST>::XCPListNode *v90; // rcx
  bool v91; // dl
  bool v92; // zf
  int v93; // edi
  int v94; // r15d
  int v95; // r12d
  int v96; // esi
  CDependencyObject *v97; // rdi
  CUIElement *v98; // r14
  int RuntimeStringHandleMarker_high; // eax
  int v100; // eax
  CUIElement *v101; // rdi
  CUIElement *v102; // r14
  unsigned int v103; // eax
  int v104; // eax
  __int64 v105; // rax
  __int128 v106; // xmm0
  __int64 (__fastcall *v107)(__int64 *, CDependencyObject *, EnterParams *); // rax
  RuntimeFeatureBehavior::RuntimeEnabledFeatureDetector *v108; // r14
  unsigned __int8 v109; // di
  char v110; // di
  Diagnostics::DiagnosticsInterop *v111; // rdi
  DirectUI::DXamlCore *Current; // rax
  IXcpBrowserHost *v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rdi
  HRESULT v116; // eax
  Flyweight::ValueObjectWrapper<CDOSharedState> *v117; // rax
  IXcpBrowserHost *m_pBrowserHost; // rcx
  __int64 v119; // rax
  __int64 v120; // rdi
  CLayoutManager *LayoutManagerForElement; // rax
  unsigned int v122; // r9d
  CLayoutManager *v123; // r12
  CUIElement *m_pParent; // rcx
  HRESULT TransformToAncestorCommon; // eax
  __int64 v126; // r14
  float v127; // xmm1_4
  float v128; // xmm2_4
  __int64 v129; // rax
  __int64 (__fastcall *v130)(_QWORD, float *, float *, __int64); // rax
  HRESULT v131; // eax
  __int64 v132; // rax
  float v133; // xmm0_4
  float v134; // xmm1_4
  unsigned int bits; // eax
  CValue *p_value; // rcx
  RuntimeProfiler::ProfileGroup v137; // eax
  __int64 v138; // rcx
  VisualTree *v139; // xmm1_8
  __int64 (__fastcall *v140)(__int64, CDependencyObject *, EnterParams *); // rax
  HRESULT v141; // ecx
  InheritedProperties *m_pInheritedProperties; // r8
  char v143; // al
  __int64 v144; // r8
  HRESULT updated; // eax
  char v146; // cl
  int v147; // eax
  char v148; // cl
  int v149; // eax
  HRESULT DirectManipulationContainer; // eax
  __int64 v151; // rdi
  HRESULT v152; // eax
  KnownTypeIndex v153; // ax
  bool v154; // al
  const CClassInfo *v155; // rax
  KnownTypeIndex v156; // ax
  bool v157; // al
  const CClassInfo *v158; // rax
  KnownTypeIndex v159; // ax
  bool v160; // al
  const CClassInfo *v161; // rax
  CUIElement *v162; // rax
  bool v163; // dl
  CUIElement *UIElementParentInternal; // rax
  KnownTypeIndex fPegNoRef; // [rsp+28h] [rbp-A9h]
  unsigned int v166; // [rsp+38h] [rbp-99h]
  bool v167; // [rsp+58h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int8 Data[8]; // [rsp+68h] [rbp-69h] BYREF
  std::shared_ptr<Diagnostics::DiagnosticsInterop> result; // [rsp+70h] [rbp-61h] BYREF
  EnterParams value; // [rsp+88h] [rbp-49h] BYREF
  CValue isAnchorCandidateValue; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v173; // [rsp+B0h] [rbp-21h]
  float v174; // [rsp+B8h] [rbp-19h] BYREF
  float v175; // [rsp+BCh] [rbp-15h]
  float v176; // [rsp+C0h] [rbp-11h]
  float v177; // [rsp+C4h] [rbp-Dh]
  int v178; // [rsp+C8h] [rbp-9h]
  float v179; // [rsp+CCh] [rbp-5h]
  float v180; // [rsp+D0h] [rbp-1h]
  float v181; // [rsp+D4h] [rbp+3h]

  v4 = *(_DWORD *)params;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  isAnchorCandidateValue.m_flags = (CValueDetails::Flags)this->m_sharedState.m_ptr->m_value.m_coreServices;
  result._Ptr = (Diagnostics::DiagnosticsInterop *)ThreadLocalStoragePointer[tls_index];
  if ( _TSS0_5 > (signed int)result._Ptr[1].m_mainThreadId )
  {
    Init_thread_header(&_TSS0_5);
    if ( _TSS0_5 == -1 )
    {
      RuntimeFeatureBehavior::GetRuntimeEnabledFeatureDetector(&runtimeEnabledFeatureDetector_1);
      atexit(CUIElement::EnterImpl_::_2_::_dynamic_atexit_destructor_for__runtimeEnabledFeatureDetector__);
      Init_thread_footer(&_TSS0_5);
    }
  }
  v167 = 0;
  if ( (v4 & 1) != 0 && !CThemeShadow::IsDropShadowMode() )
  {
    *(_QWORD *)&value = 0;
    value.pParentResourceDictionary = 0;
    ValueByIndex = CDependencyObject::GetValueByIndex(this, UIElement_Shadow, (CValue *)&value);
    v57 = ValueByIndex;
    if ( ValueByIndex >= 0 )
    {
      if ( ((__int64)value.pParentResourceDictionary & 0x3F) != 0x18 )
        goto LABEL_100;
      hKey = (HKEY)value;
      if ( !*(_QWORD *)&value )
        goto LABEL_100;
      ValueByIndex = CThemeShadow::CheckForAncestorReceivers(*(CThemeShadow **)&value, this);
      v57 = ValueByIndex;
      if ( ValueByIndex >= 0 )
      {
        CUIElement::EnsureRootCanvasCompNode(this);
LABEL_100:
        CValue::ReleaseAndReset((CValue *)&value);
        goto LABEL_3;
      }
    }
    OnFailure_2990_(ValueByIndex);
    p_value = (CValue *)&value;
LABEL_215:
    CValue::ReleaseAndReset(p_value);
    goto LABEL_138;
  }
LABEL_3:
  v8 = (v4 & 4) != 0;
  if ( (v4 & 4) != 0 && (*((_DWORD *)this + 35) & 0x100) == 0 )
    *(_DWORD *)params = v4 & 0xFFFFFFFB;
  v9 = *(_DWORD *)params;
  if ( (*(_DWORD *)params & 1) != 0 )
  {
    if ( !v8 && (*((_DWORD *)this + 35) & 0x100) != 0 )
    {
      v116 = this->CoerceIsEnabled(this, 0, 0);
      v57 = v116;
      if ( v116 < 0 )
      {
        OnFailure_2990_(v116);
        goto LABEL_138;
      }
    }
    DependencyPropertyByIndex = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(UIElement_UseLayoutRounding);
    v33 = (unsigned __int64)DependencyPropertyByIndex;
    if ( DependencyPropertyByIndex )
    {
      if ( (DependencyPropertyByIndex->m_flags & 0x288) != 0x288 )
      {
        m_nIndex = (unsigned __int16)CDependencyObject::GetClassInformation(this)->m_nIndex;
        v35 = (unsigned __int16)DirectUI::MetadataAPI::GetClassInfoByIndex((KnownTypeIndex)*(_WORD *)(v33 + 6))->m_nIndex;
        if ( (_WORD)v35 != (_WORD)m_nIndex && (_DWORD)v35 != 40 )
        {
          if ( (unsigned __int16)v35 >= 0x43Cu || (unsigned __int16)m_nIndex >= 0x43Cu )
          {
            ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex((KnownTypeIndex)m_nIndex);
            v37 = DirectUI::MetadataAPI::CompareCustomTypesHelper(ClassInfoByIndex, (KnownTypeIndex)v35);
          }
          else
          {
            m_handle = c_aTypeCheckData[v35].m_handle;
            v37 = m_handle
               && (m_handleMask = c_aTypeCheckData[v35].m_handleMask, (m_handleMask & 0x800000000000LL) == 0)
               && (m_handleMask & c_aTypeCheckData[m_nIndex].m_handle) == m_handle;
          }
          v33 &= -(__int64)v37;
        }
      }
    }
    if ( (*(_DWORD *)(v33 + 8) & 1) != 0 )
    {
      Myval2 = this->m_pValueTable._Mypair._Myval2;
      if ( !Myval2 )
        goto LABEL_115;
      Mylast = Myval2->m_data.m_vector._Mypair._Myval2._Mylast;
      Myfirst = Myval2->m_data.m_vector._Mypair._Myval2._Myfirst;
      v74 = *(_WORD *)v33;
      v75 = (__int64)((unsigned __int128)(((char *)Mylast - (char *)Myfirst) * (__int128)0x6666666666666667LL) >> 64) >> 3;
      v76 = (unsigned __int64)((unsigned __int128)(((char *)Mylast - (char *)Myfirst) * (__int128)0x6666666666666667LL) >> 64) >> 63;
LABEL_107:
      for ( v75 += v76; (__int64)v75 > 0; v75 >>= 1 )
      {
        v77 = &Myfirst[v75 >> 1];
        if ( (unsigned int)v77->first < (unsigned __int16)v74 )
        {
          Myfirst = v77 + 1;
          v76 = -1LL - (v75 >> 1);
          goto LABEL_107;
        }
      }
      if ( Myfirst == Mylast || (unsigned __int16)v74 < (unsigned int)Myfirst->first )
        goto LABEL_115;
      v78 = (Myfirst->second.value.m_flags.m_state.m_asOne & 0x100) == 0;
    }
    else
    {
      if ( (*(_DWORD *)(v33 + 8) & 0x288) != 0x288 )
      {
        m_nPropertySlotCount = c_aTypeProperties[(unsigned __int16)this->GetTypeIndex(this)].m_nPropertySlotCount;
        v39 = c_aPropertySlot[*(unsigned __int16 *)v33];
        if ( (unsigned __int8)v39 >= m_nPropertySlotCount )
        {
LABEL_47:
          *(_DWORD *)params = v9
                            ^ ((unsigned __int8)v9
                             ^ (unsigned __int8)(8
                                               * ((__int64 (__fastcall *)(CUIElement *))this->GetUseLayoutRounding)(this)))
                            & 8;
          goto LABEL_116;
        }
        if ( m_nPropertySlotCount <= 0x20u )
        {
          bits = this->m_valid.bits;
          v42 = _bittest((const int *)&bits, v39);
        }
        else
        {
          v40.pointer = (unsigned int *)this->m_valid;
          if ( !v40.pointer )
            goto LABEL_115;
          v41 = v40.pointer[(unsigned __int64)c_aPropertySlot[*(unsigned __int16 *)v33] >> 5];
          v42 = _bittest((const int *)&v41, v39 & 0x1F);
        }
        if ( v42 )
          goto LABEL_47;
LABEL_115:
        *((_DWORD *)this + 35) ^= ((unsigned __int16)*((_DWORD *)this + 35)
                                 ^ (unsigned __int16)((_WORD)v9 << 7))
                                & 0x400;
LABEL_116:
        if ( this->IsActive(this) )
          goto LABEL_7;
        m_pLayoutTransitionStorage = this->m_pLayoutTransitionStorage;
        if ( !m_pLayoutTransitionStorage || !m_pLayoutTransitionStorage->m_nextGenerationCounter )
          goto LABEL_118;
        LayoutManagerForElement = VisualTree::GetLayoutManagerForElement(this);
        v78 = (this->m_bitFields.m_bitFieldsAsDWORD & 0x200000) == 0;
        v123 = LayoutManagerForElement;
        *(_QWORD *)&value = 0;
        if ( v78 )
          m_pParent = (CUIElement *)this->m_pParent;
        else
          m_pParent = 0;
        TransformToAncestorCommon = CUIElement::GetTransformToAncestorCommon(
                                      m_pParent,
                                      0,
                                      0,
                                      v122,
                                      (ITransformer **)&value);
        v57 = TransformToAncestorCommon;
        if ( TransformToAncestorCommon < 0 )
        {
          OnFailure_2990_(TransformToAncestorCommon);
        }
        else
        {
          v126 = (__int64)value;
          v127 = 0.0;
          v128 = 0.0;
          if ( !*(_QWORD *)&value )
          {
LABEL_208:
            v133 = m_pLayoutTransitionStorage->m_currentOffset.x - v127;
            v134 = m_pLayoutTransitionStorage->m_currentOffset.y - v128;
            m_pLayoutTransitionStorage->m_currentOffset.x = v133;
            m_pLayoutTransitionStorage->m_currentOffset.y = v134;
            m_pLayoutTransitionStorage->m_nextGenerationOffset = m_pLayoutTransitionStorage->m_currentOffset;
            if ( v123 )
              m_pLayoutTransitionStorage->m_nextGenerationCounter = CLayoutManager::GetNextLayoutCounter(v123);
            if ( v126 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 8LL))(v126);
LABEL_118:
            *((_WORD *)this + 60) = 0;
            goto LABEL_7;
          }
          v129 = **(_QWORD **)&value;
          v175 = _mm_shuffle_ps((__m128)0LL, (__m128)0LL, 85).m128_f32[0];
          v130 = *(__int64 (__fastcall **)(_QWORD, float *, float *, __int64))(v129 + 24);
          v177 = v175;
          v174 = 0.0;
          v178 = 0;
          v176 = _mm_shuffle_ps((__m128)0LL, (__m128)0LL, 170).m128_f32[0] + 0.0;
          v180 = v176;
          v179 = v175 + 0.0;
          v181 = v175 + 0.0;
          v131 = v130(*(_QWORD *)&value, &v174, &v174, 4);
          v57 = v131;
          if ( v131 >= 0 )
          {
            v127 = v174;
            v132 = 1;
            v128 = v175;
            do
            {
              v127 = fminf(v127, *(&v174 + 2 * v132));
              v128 = fminf(v128, *(&v175 + 2 * v132++));
            }
            while ( v132 != 4 );
            goto LABEL_208;
          }
          OnFailure_2990_(v131);
          OnFailure_2990_(v57);
        }
        xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&value);
        v92 = !v167;
        goto LABEL_139;
      }
      m_pInheritedProperties = this->m_pInheritedProperties;
      if ( !m_pInheritedProperties || m_pInheritedProperties->m_pWriter != this )
        goto LABEL_115;
      v143 = ToPropertyNumber(*(KnownPropertyIndex *)v33);
      v78 = ((1LL << v143) & *(_QWORD *)(v144 + 104)) == 0;
    }
    if ( !v78 )
      goto LABEL_47;
    goto LABEL_115;
  }
LABEL_7:
  visualTree = params->visualTree;
  *(_OWORD *)&value = *(_OWORD *)params;
  value.visualTree = visualTree;
  v11 = CDependencyObject::EnterImpl(this, pNamescopeOwner, &value);
  v12 = v11;
  if ( v11 < 0 )
  {
    OnFailure_2990_(v11);
    goto LABEL_86;
  }
  v13 = this->GetContextFlyout(this, &hKey);
  v16 = (CDependencyObject *)hKey;
  m_ptr = (__int64 *)v13->m_ptr;
  if ( hKey )
  {
    hKey = 0;
    CDependencyObject::Release(v16);
  }
  if ( m_ptr )
  {
    v105 = *m_ptr;
    v106 = *(_OWORD *)params;
    value.visualTree = 0;
    v107 = *(__int64 (__fastcall **)(__int64 *, CDependencyObject *, EnterParams *))(v105 + 512);
    *(_OWORD *)&value = v106;
    v63 = v107(m_ptr, pNamescopeOwner, &value);
    v12 = v63;
    if ( v63 < 0 )
      goto LABEL_85;
  }
  m_pChildren = this->m_pChildren;
  if ( m_pChildren )
  {
    v62 = params->visualTree;
    *(_OWORD *)&value = *(_OWORD *)params;
    value.visualTree = v62;
    v63 = CDependencyObject::Enter(m_pChildren, pNamescopeOwner, &value);
    v12 = v63;
    if ( v63 < 0 )
      goto LABEL_85;
  }
  if ( (this->m_associativeStorage.m_occupancy.m_value.m_value & 8) != 0 )
  {
    v14 = &std::nothrow;
    v19 = (__int64 *)(AssociativeStorage::Detail::VariableStorageBlock<AssociativeStorage::Detail::Bitfield<enum AssociativeStorage::CDOFields>>::s_lookupTable.m_table.m_sizes0._Elems[this->m_associativeStorage.m_occupancy.m_value.m_value & 7]
                    + *(_QWORD *)&this->m_associativeStorage.m_dataBlock);
    if ( v19 )
    {
      v138 = *v19;
      if ( v138 )
      {
        v139 = params->visualTree;
        v140 = *(__int64 (__fastcall **)(__int64, CDependencyObject *, EnterParams *))(*(_QWORD *)v138 + 512LL);
        *(_OWORD *)&value = *(_OWORD *)params;
        value.visualTree = v139;
        v63 = v140(v138, pNamescopeOwner, &value);
        v12 = v63;
        if ( v63 < 0 )
        {
LABEL_85:
          OnFailure_2990_(v63);
          goto LABEL_86;
        }
      }
    }
  }
  v20 = *(_DWORD *)params;
  v21 = *(_DWORD *)params & 1;
  if ( !v21 )
    goto LABEL_15;
  Ptr = runtimeEnabledFeatureDetector_1._Ptr;
  v65 = (unsigned __int8)runtimeEnabledFeatureDetector_1._Ptr->m_runtimeFeatureStates[5];
  if ( (v65 & 4) != 0 )
    goto LABEL_92;
  if ( (v65 & 8) != 0 )
  {
    v65 >>= 1;
LABEL_92:
    v66 = v65 & 1;
    goto LABEL_93;
  }
  *(_DWORD *)Data = 0;
  hKey = 0;
  v66 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, &hKey) )
  {
    *(_DWORD *)&value = 4;
    if ( !RegQueryValueExW(
            hKey,
            RuntimeFeatureBehavior::s_runtimeFeatureData[5].FeatureName,
            0,
            0,
            Data,
            (LPDWORD)&value) )
      v66 = *(_DWORD *)Data != 0;
    RegCloseKey(hKey);
  }
  v146 = *(_BYTE *)&Ptr->m_runtimeFeatureStates[5] ^ (*(_BYTE *)&Ptr->m_runtimeFeatureStates[5] ^ (2 * v66)) & 2;
  *(_BYTE *)&Ptr->m_runtimeFeatureStates[5] = v146;
  v147 = *(_DWORD *)Data;
  *(_BYTE *)&Ptr->m_runtimeFeatureStates[5] = v146 | 0x18;
  Ptr->m_runtimeFeatureStates[5].CacheDwordData = v147;
LABEL_93:
  if ( v66 )
  {
    v67 = CDependencyObject::PrivateEnsurePeerAndTryPeg(this, 0, 1, v15, &v167);
    v12 = v67;
    if ( v67 < 0 )
    {
      OnFailure_2990_(v67);
      goto LABEL_86;
    }
  }
LABEL_15:
  if ( (this->m_bitFields.m_bitFieldsAsDWORD & 0x200) == 0 )
    goto LABEL_16;
  hKey = 0;
  if ( DXamlInstanceStorage::g_dwTlsIndex == -1 )
  {
    v55 = 0;
    OnNewFailure_2955_(-1);
  }
  else
  {
    v55 = (DirectUI::DXamlCore *)TlsGetValue(DXamlInstanceStorage::g_dwTlsIndex);
    if ( !v55 && GetLastError() )
      OnFailure_977_(v141);
  }
  this->GetTypeIndex(this);
  PeerPrivate = DirectUI::DXamlCore::GetPeerPrivate(
                  v55,
                  0,
                  this,
                  GetOnly,
                  fPegNoRef,
                  0,
                  v166,
                  0,
                  (DirectUI::DependencyObject **)&hKey);
  v57 = PeerPrivate;
  v58 = (Windows::UI::Xaml::IDependencyObject *)hKey;
  if ( PeerPrivate < 0 )
    goto LABEL_295;
  if ( !hKey )
    goto LABEL_16;
  v59 = (v20 >> 3) & 1;
  v60 = (v20 >> 2) & 1;
  v61 = (v20 >> 1) & 1;
  if ( _TSS0_36 > (signed int)result._Ptr[1].m_mainThreadId )
  {
    Init_thread_header(&_TSS0_36);
    if ( _TSS0_36 == -1 )
    {
      RuntimeFeatureBehavior::GetRuntimeEnabledFeatureDetector(&runtimeEnabledFeatureDetector_21);
      atexit(DirectUI::DependencyObject::EnterImpl_::_11_::_dynamic_atexit_destructor_for__runtimeEnabledFeatureDetector__);
      Init_thread_footer(&_TSS0_36);
    }
  }
  PeerPrivate = ((__int64 (__fastcall *)(Windows::UI::Xaml::IDependencyObject *, _QWORD, _QWORD, _QWORD, int))v58->__vftable[1].ReadLocalValue)(
                  v58,
                  v21,
                  v61,
                  v60,
                  v59);
  v57 = PeerPrivate;
  if ( PeerPrivate < 0 )
  {
LABEL_295:
    OnFailure_2990_(PeerPrivate);
    goto LABEL_79;
  }
  if ( v21 )
  {
    v108 = runtimeEnabledFeatureDetector_21._Ptr;
    v109 = (unsigned __int8)runtimeEnabledFeatureDetector_21._Ptr->m_runtimeFeatureStates[5];
    if ( (v109 & 4) == 0 )
    {
      if ( (v109 & 8) == 0 )
      {
        *(_DWORD *)Data = 0;
        hKey = 0;
        v110 = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, &hKey) )
        {
          *(_DWORD *)&value = 4;
          if ( !RegQueryValueExW(
                  hKey,
                  RuntimeFeatureBehavior::s_runtimeFeatureData[5].FeatureName,
                  0,
                  0,
                  Data,
                  (LPDWORD)&value) )
            v110 = *(_DWORD *)Data != 0;
          RegCloseKey(hKey);
        }
        v148 = *(_BYTE *)&v108->m_runtimeFeatureStates[5]
             ^ (*(_BYTE *)&v108->m_runtimeFeatureStates[5]
              ^ (2 * v110))
             & 2;
        *(_BYTE *)&v108->m_runtimeFeatureStates[5] = v148;
        v149 = *(_DWORD *)Data;
        *(_BYTE *)&v108->m_runtimeFeatureStates[5] = v148 | 0x18;
        v108->m_runtimeFeatureStates[5].CacheDwordData = v149;
        goto LABEL_173;
      }
      v109 >>= 1;
    }
    v110 = v109 & 1;
LABEL_173:
    if ( v110 )
    {
      Diagnostics::GetDiagnosticsInterop(&result, (bool)v14);
      v111 = result._Ptr;
      if ( result._Ptr )
      {
        Current = DirectUI::DXamlCore::GetCurrent();
        if ( Diagnostics::DiagnosticsInterop::IsEnabledForThread(v111, Current->m_threadId) )
        {
          if ( v111->m_diagnostics )
            XamlDiagnostics::SignalMutation(v111->m_diagnostics, v58, Add);
        }
      }
      if ( result._Rep )
        std::_Ref_count_base::_Decref(result._Rep);
    }
  }
LABEL_79:
  if ( v58 && v58 != (Windows::UI::Xaml::IDependencyObject *)-8LL )
    v58[1].Release(v58 + 1);
  if ( v57 < 0 )
  {
LABEL_137:
    OnFailure_2990_(v57);
LABEL_138:
    v92 = !v167;
LABEL_139:
    if ( !v92 )
      CDependencyObject::UnpegManagedPeer(this, v91);
    return (unsigned int)v57;
  }
LABEL_16:
  v22 = VisualTree::GetForElementNoRef(this, (LookupOptions)v14);
  if ( v22 )
  {
    m_coreContentRoot = (HKEY)v22->m_coreContentRoot;
  }
  else
  {
    v117 = this->m_sharedState.m_ptr;
    m_coreServices = v117->m_value.m_coreServices;
    m_coreContentRoot = (HKEY)v117->m_value.m_coreServices->m_contentRootCoordinator.m_unsafe_XamlIslandsIncompatible_CoreWindowContentRoot;
  }
  hKey = m_coreContentRoot;
  if ( !v21 )
    goto LABEL_58;
  m_pEventList = this->m_pEventList;
  if ( !m_pEventList )
  {
LABEL_20:
    if ( this->GetIsLayoutElement(this) || CUIElement::GetIsParentLayoutElement(this) )
    {
      this->m_layoutFlags |= 0x11u;
      m_layoutFlags = this->m_layoutFlags;
    }
    else
    {
      m_layoutFlags = this->m_layoutFlags;
      if ( (m_layoutFlags & 1) == 0 )
      {
        m_layoutFlags |= 2u;
        this->m_layoutFlags = m_layoutFlags;
      }
      if ( (m_layoutFlags & 0x10) == 0 )
      {
        m_layoutFlags |= 0x20u;
        this->m_layoutFlags = m_layoutFlags;
      }
    }
    isAnchorCandidateValue.m_flags = 0;
    v173 = 0;
    PropertyBaseByIndex = DirectUI::MetadataAPI::GetPropertyBaseByIndex(UIElement_CanBeScrollAnchor);
    if ( PropertyBaseByIndex->m_nIndex >= BrushTransition_Duration
      && (PropertyBaseByIndex->m_flags & 0x800) == 0
      && (PropertyBaseByIndex->m_flags & 0x1000) == 0 )
    {
      PropertyBaseByIndex = 0;
    }
    if ( PropertyBaseByIndex->m_flags < None )
    {
      v29 = this->m_sharedState.m_ptr;
      if ( !v29->m_value.m_coreServices->m_accessedStaleMetadata )
        v29->m_value.m_coreServices->m_accessedStaleMetadata = (const CDependencyProperty *)PropertyBaseByIndex;
    }
    v30 = this->GetValue(
            this,
            (const CDependencyProperty *)PropertyBaseByIndex,
            (CValue *)&isAnchorCandidateValue.m_flags);
    v12 = v30;
    if ( v30 < 0 )
      goto LABEL_30;
    if ( isAnchorCandidateValue.m_flags.m_state.0 )
    {
      if ( (v173 & 0x3F) == 2 )
      {
        updated = CUIElement::UpdateAnchorCandidateOnParentScrollProvider(this, 1);
        v12 = updated;
        if ( updated < 0 )
        {
          OnFailure_2990_(updated);
          goto LABEL_31;
        }
      }
    }
    v93 = m_layoutFlags & 5;
    v94 = m_layoutFlags & 0x50;
    v95 = m_layoutFlags & 0x300000;
    v96 = m_layoutFlags & 0xC00000;
    if ( (Microsoft_Windows_XAML_DiagnosticsEnableBits[0] & 2) != 0 )
    {
      UIElementParentInternal = CDependencyObject::GetUIElementParentInternal(this, 1);
      if ( (Microsoft_Windows_XAML_DiagnosticsEnableBits[0] & 2) != 0 )
        McTemplateMofU0xx(
          &WINDOWS_UI_XAML_DIAG_ETW_PROVIDER_Context,
          &ElementAddedInfo,
          &ElementAddedId,
          (const unsigned __int64)this,
          (const unsigned __int64)UIElementParentInternal);
    }
    if ( v93 )
    {
      if ( (*(_BYTE *)&this->m_bitFields.0 & 0x40) == 0 || (this->m_bitFields.m_bitFieldsAsDWORD & 0x200000) != 0 )
        v101 = 0;
      else
        v101 = do_pointer_cast<CUIElement>(this->m_pParent);
      v102 = this;
      while ( v101 )
      {
        v103 = v101->m_layoutFlags;
        if ( (v103 & 4) != 0 )
          goto LABEL_165;
        v104 = v103 | 4;
        v101->m_layoutFlags = v104;
        if ( (v104 & 2) != 0 )
          v101->m_layoutFlags = v104 & 0xFFFFFFFC | 1;
        v102 = v101;
        if ( (*(_BYTE *)&v101->m_bitFields.0 & 0x40) != 0 && (v101->m_bitFields.m_bitFieldsAsDWORD & 0x200000) == 0 )
        {
          v101 = (CUIElement *)v101->m_pParent;
          if ( v101 )
          {
            v156 = v101->GetTypeIndex(v101);
            if ( v156 == UIElement )
              continue;
            if ( (unsigned __int16)v156 >= (XYFocusNavigationStrategy|IVectorOfUri) )
            {
              v158 = DirectUI::MetadataAPI::GetClassInfoByIndex(v156);
              v157 = DirectUI::MetadataAPI::CompareCustomTypesHelper(v158, UIElement);
            }
            else
            {
              v157 = LOBYTE(c_aTypeCheckData[(unsigned __int16)v156].m_handle) == 103;
            }
            if ( v157 )
              continue;
          }
        }
        v101 = 0;
      }
      if ( CDependencyObject::OfTypeByIndex<779>(v102) )
      {
        m_pBrowserHost = this->m_sharedState.m_ptr->m_value.m_coreServices->m_pBrowserHost;
        if ( m_pBrowserHost )
        {
          v119 = (__int64)m_pBrowserHost->GetFrameScheduler(m_pBrowserHost);
          v120 = v119;
          if ( v119 )
          {
            if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v119 + 40LL))(v119) )
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v120 + 16LL))(v120, 0, 32);
          }
        }
      }
LABEL_165:
      if ( (*(_BYTE *)&this->m_bitFields.0 & 0x40) != 0 && (this->m_bitFields.m_bitFieldsAsDWORD & 0x200000) == 0 )
      {
        v162 = do_pointer_cast<CUIElement>(this->m_pParent);
        if ( v162 )
          CUIElement::InvalidateMeasure(v162);
      }
    }
    if ( v94 )
    {
      if ( (*(_BYTE *)&this->m_bitFields.0 & 0x40) == 0
        || (this->m_bitFields.m_bitFieldsAsDWORD & 0x200000) != 0
        || (v97 = this->m_pParent) == 0
        || (v159 = v97->GetTypeIndex(this->m_pParent), v159 != UIElement)
        && ((unsigned __int16)v159 >= (XYFocusNavigationStrategy|IVectorOfUri)
          ? (v161 = DirectUI::MetadataAPI::GetClassInfoByIndex(v159),
             v160 = DirectUI::MetadataAPI::CompareCustomTypesHelper(v161, UIElement))
          : (v160 = LOBYTE(c_aTypeCheckData[(unsigned __int16)v159].m_handle) == 103),
            !v160) )
      {
        v97 = 0;
      }
      v98 = this;
      while ( v97 )
      {
        RuntimeStringHandleMarker_high = HIDWORD(v97[1].m_strName.m_encodedStorage.RuntimeStringHandleMarker);
        if ( (RuntimeStringHandleMarker_high & 0x40) != 0 )
          goto LABEL_49;
        v100 = RuntimeStringHandleMarker_high | 0x40;
        HIDWORD(v97[1].m_strName.m_encodedStorage.RuntimeStringHandleMarker) = v100;
        if ( (v100 & 0x20) != 0 )
          HIDWORD(v97[1].m_strName.m_encodedStorage.RuntimeStringHandleMarker) = v100 & 0xFFFFFFCF | 0x10;
        v98 = (CUIElement *)v97;
        if ( (*(_BYTE *)&v97->m_bitFields.0 & 0x40) != 0 && (v97->m_bitFields.m_bitFieldsAsDWORD & 0x200000) == 0 )
        {
          v97 = v97->m_pParent;
          if ( v97 )
          {
            v153 = v97->GetTypeIndex(v97);
            if ( v153 == UIElement )
              continue;
            if ( (unsigned __int16)v153 >= (XYFocusNavigationStrategy|IVectorOfUri) )
            {
              v155 = DirectUI::MetadataAPI::GetClassInfoByIndex(v153);
              v154 = DirectUI::MetadataAPI::CompareCustomTypesHelper(v155, UIElement);
            }
            else
            {
              v154 = LOBYTE(c_aTypeCheckData[(unsigned __int16)v153].m_handle) == 103;
            }
            if ( v154 )
              continue;
          }
        }
        v97 = 0;
      }
      if ( CDependencyObject::OfTypeByIndex<779>(v98) )
      {
        v113 = this->m_sharedState.m_ptr->m_value.m_coreServices->m_pBrowserHost;
        if ( v113 )
        {
          v114 = (__int64)v113->GetFrameScheduler(v113);
          v115 = v114;
          if ( v114 )
          {
            if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v114 + 40LL))(v114) )
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v115 + 16LL))(v115, 0, 32);
          }
        }
      }
    }
LABEL_49:
    if ( v95 )
      CUIElement::PropagateOnPathInternal(this, 0x200000u, 0, 0);
    if ( v96 )
      CUIElement::PropagateOnPathInternal(this, 0x400000u, 0, 0);
    CUIElement::InvalidateAutomationPeerDataInternal(this);
    m_coreContentRoot = hKey;
    v43 = *((_QWORD *)hKey + 114);
    if ( *(_BYTE *)(v43 + 8) )
    {
      if ( *(_BYTE *)(v43 + 113) )
      {
        if ( *(_BYTE *)(v43 + 112) )
        {
          v30 = AccessKeys::AKScopeTree<AccessKeys::AKScope<CDependencyObject,AccessKeys::AKOwner<CDependencyObject,CAutomationPeer,IUIAInvokeProvider,IUIAToggleProvider,IUIASelectionItemProvider,IUIAExpandCollapseProvider>>,AccessKeys::AKScopeBuilder<AccessKeys::AKTreeAnalyzer<CDOCollection,VisualTree,AccessKeys::AKVisualTreeFinder,CDependencyObject>,AccessKeys::AKParser,CDependencyObject,AccessKeys::AKScope<CDependencyObject,AccessKeys::AKOwner<CDependencyObject,CAutomationPeer,IUIAInvokeProvider,IUIAToggleProvider,IUIASelectionItemProvider,IUIAExpandCollapseProvider>>>,AccessKeys::AKModeContainer,CDependencyObject,AccessKeys::AKTreeAnalyzer<CDOCollection,VisualTree,AccessKeys::AKVisualTreeFinder,CDependencyObject>,CFocusManager>::AddElement(
                  (AccessKeys::AKScopeTree<AccessKeys::AKScope<CDependencyObject,AccessKeys::AKOwner<CDependencyObject,CAutomationPeer,IUIAInvokeProvider,IUIAToggleProvider,IUIASelectionItemProvider,IUIAExpandCollapseProvider> >,AccessKeys::AKScopeBuilder<AccessKeys::AKTreeAnalyzer<CDOCollection,VisualTree,AccessKeys::AKVisualTreeFinder,CDependencyObject>,AccessKeys::AKParser,CDependencyObject,AccessKeys::AKScope<CDependencyObject,AccessKeys::AKOwner<CDependencyObject,CAutomationPeer,IUIAInvokeProvider,IUIAToggleProvider,IUIASelectionItemProvider,IUIAExpandCollapseProvider> > >,AccessKeys::AKModeContainer,CDependencyObject,AccessKeys::AKTreeAnalyzer<CDOCollection,VisualTree,AccessKeys::AKVisualTreeFinder,CDependencyObject>,CFocusManager> *)(v43 + 40),
                  this);
          v12 = v30;
          if ( v30 < 0 )
          {
LABEL_30:
            OnFailure_2990_(v30);
            OnFailure_2990_(v12);
LABEL_31:
            CValue::ReleaseAndReset((CValue *)&isAnchorCandidateValue.m_flags);
LABEL_86:
            if ( v167 )
              CDependencyObject::UnpegManagedPeer(this, v31);
            return v12;
          }
        }
      }
    }
    this->m_layoutStorage.m_previousAvailableSize = 0;
    this->m_layoutStorage.m_desiredSize = 0;
    *(_QWORD *)&this->m_layoutStorage.m_finalRect.Width = 0;
    *(_QWORD *)&this->m_layoutStorage.m_finalRect.X = 0;
    this->m_layoutStorage.m_offset = 0;
    this->m_layoutStorage.m_unclippedDesiredSize = 0;
    this->m_layoutStorage.m_size = 0;
    m_pLayoutClipGeometry = this->m_layoutStorage.m_pLayoutClipGeometry;
    if ( m_pLayoutClipGeometry )
    {
      CDependencyObject::Release(m_pLayoutClipGeometry);
      this->m_layoutStorage.m_pLayoutClipGeometry = 0;
    }
    if ( (*((_DWORD *)this + 36) & 0x40000) != 0 )
    {
      *(_QWORD *)&value = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&value);
      DirectManipulationContainer = CUIElement::GetDirectManipulationContainer(this, (CUIDMContainer **)&value);
      v12 = DirectManipulationContainer;
      if ( DirectManipulationContainer < 0 )
      {
        OnFailure_2990_(DirectManipulationContainer);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&value);
        goto LABEL_31;
      }
      v151 = (__int64)value;
      if ( *(_QWORD *)&value )
      {
        v152 = CUIDMContainer::NotifyManipulatabilityAffectingPropertyChanged(*(CUIDMContainer **)&value, 1u);
        v57 = v152;
        if ( v152 < 0 )
        {
          OnFailure_2990_(v152);
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&value);
          p_value = (CValue *)&isAnchorCandidateValue.m_flags;
          goto LABEL_215;
        }
        if ( v151 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v151 + 16LL))(v151);
      }
    }
    CValue::ReleaseAndReset((CValue *)&isAnchorCandidateValue.m_flags);
LABEL_58:
    if ( !m_coreContentRoot )
      goto LABEL_69;
    v45 = *((_DWORD *)m_coreContentRoot + 4);
    if ( !v45 )
      goto LABEL_69;
    v46 = v45 - 1;
    if ( !v46 )
      goto LABEL_69;
    v47 = v46 - 1;
    if ( v47 )
    {
      if ( v47 != 1 )
        goto LABEL_69;
      v48 = qword_180F72728;
      if ( qword_180F72728 )
      {
LABEL_64:
        v49 = this->GetTypeIndex(this);
        StableXbfTypeIndex = (unsigned __int16)Parser::GetStableXbfTypeIndex(v49);
        v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
        if ( (unsigned __int16)StableXbfTypeIndex < 0x3D2u
          && !_InterlockedIncrement((volatile signed __int32 *)(v51 + 4 * StableXbfTypeIndex)) )
        {
          (**(void (__fastcall ***)(__int64, _QWORD))v48)(v48, (unsigned __int16)StableXbfTypeIndex);
        }
        goto LABEL_69;
      }
      v52 = RuntimeProfiler::MapToProfileGroup(DesktopWindowContentBridge);
      DynamicProfiler = RuntimeProfiler::CDynamicProfiler::CreateDynamicProfiler(v52);
      qword_180F72728 = (__int64)DynamicProfiler;
    }
    else
    {
      v48 = qword_180F72720;
      if ( qword_180F72720 )
        goto LABEL_64;
      v137 = RuntimeProfiler::MapToProfileGroup(AppWindow);
      DynamicProfiler = RuntimeProfiler::CDynamicProfiler::CreateDynamicProfiler(v137);
      qword_180F72720 = (__int64)DynamicProfiler;
    }
    v48 = (__int64)DynamicProfiler;
    if ( DynamicProfiler )
      goto LABEL_64;
LABEL_69:
    if ( v167 )
      CDependencyObject::UnpegManagedPeer(this, v23);
    return 0;
  }
  if ( isAnchorCandidateValue.m_flags )
  {
    v80 = *(CEventManager **)(*(_QWORD *)&isAnchorCandidateValue.m_flags + 232LL);
    if ( v80 )
    {
      v57 = 0;
      FailFast = (CXcpList<REQUEST> *)XcpAllocation::OSMemoryAllocateFailFast(0x10u);
      v83 = FailFast;
      if ( FailFast )
      {
        FailFast->m_pHead = 0;
        FailFast->m_pTail = 0;
      }
      else
      {
        v83 = 0;
      }
      for ( i = m_pEventList->m_pHead; i; i = i->m_pNext )
      {
        m_pData = i->m_pData;
        m_pHead = v83->m_pHead;
        v87 = (CXcpList<REQUEST>::XCPListNode *)XcpAllocation::OSMemoryAllocateFailFast(0x10u);
        v78 = v83->m_pTail == 0;
        v83->m_pHead = v87;
        if ( v78 )
          v83->m_pTail = v87;
        v87->m_pNext = m_pHead;
        v83->m_pHead->m_pData = m_pData;
      }
      for ( j = v83->m_pHead; j; j = j->m_pNext )
      {
        if ( !j->m_pData->m_bAdded )
        {
          v89 = CEventManager::AddRequest(v80, this, j->m_pData);
          v57 = v89;
          if ( v89 < 0 )
          {
            OnFailure_2990_(v89);
            break;
          }
        }
      }
      while ( 1 )
      {
        v90 = v83->m_pHead;
        if ( !v83->m_pHead )
          break;
        v83->m_pHead = v90->m_pNext;
        v90->m_pData = 0;
        operator delete(v90, 0x10u);
      }
      v83->m_pHead = 0;
      v83->m_pTail = 0;
      CXcpList<REQUEST>::`scalar deleting destructor'(v83, v82);
      if ( v57 >= 0 )
        goto LABEL_20;
      goto LABEL_137;
    }
  }
  OnNewFailure_1172_((HRESULT)m_coreServices);
  if ( v167 )
    CDependencyObject::UnpegManagedPeer(this, v163);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800847f0  mov     rax, rsp
0x1800847f3  mov     [rax+20h], rbx
0x1800847f7  push    rbp
0x1800847f8  push    rsi
0x1800847f9  push    rdi
0x1800847fa  push    r12
0x1800847fc  push    r13
0x1800847fe  push    r14
0x180084800  push    r15
0x180084802  lea     rbp, [rax-5Fh]
0x180084806  sub     rsp, 0F0h
0x18008480d  movaps  xmmword ptr [rax-48h], xmm6
0x180084811  mov     rax, cs:__security_cookie
0x180084818  xor     rax, rsp
0x18008481b  mov     [rbp+57h+var_50], rax
0x18008481f  mov     rax, [this+10h]
0x180084823  mov     rbx, this
0x180084826  mov     edi, [params]
0x180084829  mov     r13, pNamescopeOwner
0x18008482c  mov     edx, 28h ; '('
0x180084831  mov     r15, params
0x180084834  mov     this, [rax]
0x180084837  mov     rax, gs:58h
0x180084840  mov     qword ptr [rbp+57h+isAnchorCandidateValue.m_flags], this
0x180084844  mov     ecx, cs:_tls_index
0x18008484a  mov     rax, [rax+this*8]
0x18008484e  mov     [rbp+57h+result._Ptr], rax
0x180084852  mov     eax, [rax+pNamescopeOwner]
0x180084855  cmp     cs:$TSS0_5, eax
0x18008485b  jg      loc_1800855A5
0x180084861  xor     r12d, r12d
0x180084864  mov     [rbp+57h+var_D0], r12b
0x180084868  test    dil, 1
0x18008486c  jnz     loc_180084E8C
0x180084872  mov     eax, edi
0x180084874  mov     ecx, 100h
0x180084879  shr     eax, 2
0x18008487c  and     al, 1
0x18008487e  jz      short loc_18008488C
0x180084880  test    [rbx+8Ch], ecx
0x180084886  jz      loc_180084E81
0x18008488c  mov     edi, [r15]
0x18008488f  lea     r14, std__nothrow
0x180084896  test    dil, 1
0x18008489a  jnz     loc_180084A38
0x1800848a0  movups  xmm0, xmmword ptr [r15]
0x1800848a4  lea     params, [rbp+57h+value]
0x1800848a8  mov     pNamescopeOwner, r13
0x1800848ab  movsd   xmm1, qword ptr [r15+10h]
0x1800848b1  mov     this, rbx
0x1800848b4  movaps  xmmword ptr [rbp+57h+value.m_value], xmm0
0x1800848b8  movsd   [rbp+57h+var_90], xmm1
0x1800848bd  call    ?EnterImpl@CDependencyObject@@MEAAJPEAV1@UEnterParams@@@Z; CDependencyObject::EnterImpl(CDependencyObject *,EnterParams)
0x1800848c2  mov     edi, eax
0x1800848c4  test    eax, eax
0x1800848c6  js      loc_180085421
0x1800848cc  mov     rax, [rbx]
0x1800848cf  lea     pNamescopeOwner, [rbp+57h+hKey]
0x1800848d3  mov     this, rbx
0x1800848d6  mov     rax, [rax+2B0h]
0x1800848dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848e2  mov     this, [rbp+57h+hKey]; this
0x1800848e6  mov     rdi, [rax]
0x1800848e9  test    this, this
0x1800848ec  jz      short loc_1800848F7
0x1800848ee  mov     [rbp+57h+hKey], r12
0x1800848f2  call    ?Release@CDependencyObject@@QEAAXXZ; CDependencyObject::Release(void)
0x1800848f7  test    rdi, rdi
0x1800848fa  jnz     loc_1800851EF
0x180084900  mov     this, [rbx+160h]
0x180084907  test    this, this
0x18008490a  jnz     loc_180084DEC
0x180084910  test    byte ptr [rbx+5Ch], 8
0x180084914  jz      short loc_180084939
0x180084916  movzx   eax, byte ptr [rbx+5Ch]
0x18008491a  lea     pNamescopeOwner, std__nothrow; element
0x180084921  mov     this, [rbx+54h]
0x180084925  and     eax, 7
0x180084928  movzx   eax, byte ptr [rax+pNamescopeOwner+0F74DB0h]
0x180084930  add     this, rax
0x180084933  jnz     loc_18008564F
0x180084939  mov     r14d, [r15]
0x18008493c  mov     r13d, r14d
0x18008493f  and     r13d, 1
0x180084943  jnz     loc_180084E2D
0x180084949  test    dword ptr [rbx+50h], 200h
0x180084950  jnz     loc_180084CEA
0x180084956  mov     this, rbx; element
0x180084959  call    ?GetForElementNoRef@VisualTree@@SAPEAV1@PEAVCDependencyObject@@W4LookupOptions@@@Z; VisualTree::GetForElementNoRef(CDependencyObject *,LookupOptions)
0x18008495e  test    rax, rax
0x180084961  jz      loc_1800853AB
0x180084967  mov     r14, [rax+18h]
0x18008496b  mov     [rbp+57h+hKey], r14
0x18008496f  test    r13d, r13d
0x180084972  jz      loc_180084C07
0x180084978  mov     r14, [rbx+60h]
0x18008497c  test    r14, r14
0x18008497f  jnz     loc_180085001
0x180084985  mov     rax, [rbx]
0x180084988  mov     this, rbx
0x18008498b  mov     rax, [rax+350h]
0x180084992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084997  test    al, al
0x180084999  jz      loc_18008533E
0x18008499f  or      dword ptr [rbx+7Ch], 11h
0x1800849a3  mov     esi, [rbx+7Ch]
0x1800849a6  mov     ecx, 1A5h; ePropertyIndex
0x1800849ab  mov     qword ptr [rbp+57h+isAnchorCandidateValue.m_flags], 0
0x1800849b3  mov     [rbp+57h+var_78], 0
0x1800849bb  call    ?GetPropertyBaseByIndex@MetadataAPI@DirectUI@@SAPEBVCPropertyBase@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetPropertyBaseByIndex(KnownPropertyIndex)
0x1800849c0  mov     pNamescopeOwner, rax
0x1800849c3  mov     eax, 812h
0x1800849c8  cmp     [pNamescopeOwner], ax
0x1800849cb  jb      short loc_1800849E2
0x1800849cd  test    dword ptr [pNamescopeOwner+8], 800h
0x1800849d4  jnz     short loc_1800849E2
0x1800849d6  test    dword ptr [pNamescopeOwner+8], 1000h
0x1800849dd  jnz     short loc_1800849E2
0x1800849df  mov     pNamescopeOwner, r12
0x1800849e2  cmp     [pNamescopeOwner+8], r12d
0x1800849e6  jge     short loc_1800849FF
0x1800849e8  mov     rax, [rbx+10h]
0x1800849ec  mov     this, [rax]
0x1800849ef  cmp     [this+970h], r12
0x1800849f6  jnz     short loc_1800849FF
0x1800849f8  mov     [this+970h], pNamescopeOwner
0x1800849ff  mov     rax, [rbx]
0x180084a02  lea     params, [rbp+57h+isAnchorCandidateValue.m_flags]
0x180084a06  mov     this, rbx
0x180084a09  mov     rax, [rax+20h]
0x180084a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a12  mov     edi, eax
0x180084a14  test    eax, eax
0x180084a16  jns     loc_1800850EE
0x180084a1c  mov     ecx, eax; failedFrameHR
0x180084a1e  call    OnFailure_2990_
0x180084a23  mov     ecx, edi; failedFrameHR
0x180084a25  call    OnFailure_2990_
0x180084a2a  lea     this, [rbp+57h+isAnchorCandidateValue.m_flags]; this
0x180084a2e  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180084a33  jmp     loc_180084E1C
0x180084a38  test    al, al
0x180084a3a  jz      loc_180085372
0x180084a40  mov     ecx, 1D6h; ePropertyIndex
0x180084a45  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x180084a4a  mov     rsi, rax
0x180084a4d  test    rax, rax
0x180084a50  jz      short loc_180084AC6
0x180084a52  mov     ecx, [rax+8]
0x180084a55  and     ecx, 288h
0x180084a5b  cmp     ecx, 288h
0x180084a61  jz      short loc_180084AC6
0x180084a63  mov     this, rbx; this
0x180084a66  call    ?GetClassInformation@CDependencyObject@@QEBAPEBVCClassInfo@@XZ; CDependencyObject::GetClassInformation(void)
0x180084a6b  movzx   ecx, word ptr [rsi+6]; eTypeIndex
0x180084a6f  movzx   r12d, word ptr [rax]
0x180084a73  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x180084a78  movzx   r14d, word ptr [rax]
0x180084a7c  cmp     r14w, r12w
0x180084a80  jz      loc_18008542D
0x180084a86  cmp     r14d, 28h ; '('
0x180084a8a  jz      loc_18008542D
0x180084a90  mov     eax, 43Ch
0x180084a95  cmp     r14w, ax
0x180084a99  jb      loc_180084EED
0x180084a9f  movzx   ecx, r12w; eTypeIndex
0x180084aa3  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x180084aa8  mov     this, rax; typeClass
0x180084aab  movzx   edx, r14w; targetType
0x180084aaf  call    ?CompareCustomTypesHelper@MetadataAPI@DirectUI@@CA_NPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::CompareCustomTypesHelper(CClassInfo const *,KnownTypeIndex)
0x180084ab4  lea     r14, std__nothrow
0x180084abb  neg     al
0x180084abd  sbb     rax, rax
0x180084ac0  and     rsi, rax
0x180084ac3  xor     r12d, r12d
0x180084ac6  mov     eax, [rsi+8]
0x180084ac9  test    al, 1
0x180084acb  jnz     loc_180084F2B
0x180084ad1  and     eax, 288h
0x180084ad6  cmp     eax, 288h
0x180084adb  jz      loc_180085739
0x180084ae1  mov     rax, [rbx]
0x180084ae4  mov     this, rbx
0x180084ae7  mov     rax, [rax+258h]
0x180084aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084af3  movzx   ecx, ax
0x180084af6  lea     rax, [this+this*2]
0x180084afa  mov     cl, ds:rva ?c_aTypeProperties@@3QBUMetaDataTypeProperties@@B.m_nPropertySlotCount[r14+rax*4]; MetaDataTypeProperties const near * const c_aTypeProperties ...
0x180084b02  movzx   eax, word ptr [rsi]
0x180084b05  movzx   edx, byte ptr [rax+r14+0EBB030h]
0x180084b0e  cmp     dl, cl
0x180084b10  jnb     short loc_180084B45
0x180084b12  cmp     cl, 20h ; ' '
0x180084b15  jbe     loc_180085585
0x180084b1b  mov     params, [rbx+48h]
0x180084b1f  test    params, params
0x180084b22  jz      loc_180084F9B
0x180084b28  mov     eax, edx
0x180084b2a  mov     ecx, edx
0x180084b2c  shr     rax, 5
0x180084b30  and     ecx, 1Fh
0x180084b33  mov     eax, [params+rax*4]
0x180084b37  bt      eax, ecx
0x180084b3a  setb    al
0x180084b3d  test    al, al
0x180084b3f  jz      loc_180084F9B
0x180084b45  mov     rax, [rbx]
0x180084b48  mov     this, rbx
0x180084b4b  mov     rax, [rax+118h]
0x180084b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b57  movzx   eax, al
0x180084b5a  shl     eax, 3
0x180084b5d  xor     eax, edi
0x180084b5f  and     eax, 8
0x180084b62  xor     eax, edi
0x180084b64  mov     [r15], eax
0x180084b67  jmp     loc_180084FB4
0x180084b6c  mov     this, r14; this
0x180084b6f  call    ??$OfTypeByIndex@$0DAL@@CDependencyObject@@QEBA_NXZ; CDependencyObject::OfTypeByIndex<779>(void)
0x180084b74  test    al, al
0x180084b76  jnz     loc_1800852DB
0x180084b7c  test    r12d, r12d
0x180084b7f  jnz     loc_180085C29
0x180084b85  xor     r12d, r12d
0x180084b88  test    esi, esi
0x180084b8a  jnz     loc_1800852C3
0x180084b90  mov     this, rbx; this
0x180084b93  call    ?InvalidateAutomationPeerDataInternal@CUIElement@@AEAAXXZ; CUIElement::InvalidateAutomationPeerDataInternal(void)
0x180084b98  mov     r14, [rbp+57h+hKey]
0x180084b9c  mov     this, [r14+390h]
0x180084ba3  cmp     [this+8], r12b
0x180084ba7  jnz     loc_180085612
0x180084bad  mov     [rbx+120h], r12
0x180084bb4  mov     [rbx+128h], r12
0x180084bbb  mov     [rbx+138h], r12
0x180084bc2  mov     [rbx+130h], r12
0x180084bc9  mov     [rbx+140h], r12
0x180084bd0  mov     [rbx+148h], r12
0x180084bd7  mov     [rbx+150h], r12
0x180084bde  mov     this, [rbx+158h]; this
0x180084be5  test    this, this
0x180084be8  jnz     loc_18008522B
0x180084bee  test    dword ptr [rbx+90h], 40000h
0x180084bf8  jnz     loc_18008590C
0x180084bfe  lea     this, [rbp+57h+isAnchorCandidateValue.m_flags]; this
0x180084c02  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180084c07  test    r14, r14
0x180084c0a  jz      loc_180084CB2
0x180084c10  mov     ecx, [r14+10h]
0x180084c14  test    ecx, ecx
0x180084c16  jz      loc_180084CB2
0x180084c1c  sub     ecx, 1
0x180084c1f  jz      loc_180084CB2
0x180084c25  sub     ecx, 1
0x180084c28  jz      loc_1800855E7
0x180084c2e  cmp     ecx, 1
0x180084c31  jnz     short loc_180084CB2
0x180084c33  mov     rdi, cs:qword_180F72728
0x180084c3a  test    rdi, rdi
0x180084c3d  jz      short loc_180084C92
0x180084c3f  mov     rax, [rbx]
0x180084c42  mov     this, rbx
0x180084c45  mov     rax, [rax+258h]
0x180084c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c51  movzx   ecx, ax; index
0x180084c54  call    ?GetStableXbfTypeIndex@Parser@@YA?AW4StableXbfTypeIndex@1@W4KnownTypeIndex@@@Z; Parser::GetStableXbfTypeIndex(KnownTypeIndex)
0x180084c59  mov     this, [rdi]
0x180084c5c  movzx   esi, ax
0x180084c5f  mov     rax, [this+8]
0x180084c63  mov     this, rdi
0x180084c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c6b  mov     ecx, 3D2h
0x180084c70  cmp     si, cx
0x180084c73  jnb     short loc_180084CB2
0x180084c75  lea     params, [rax+rsi*4]
0x180084c79  lock inc dword ptr [params]
0x180084c7d  jnz     short loc_180084CB2
0x180084c7f  mov     rax, [rdi]
0x180084c82  movzx   edx, si
0x180084c85  mov     this, rdi
0x180084c88  mov     rax, [rax]
0x180084c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c90  jmp     short loc_180084CB2
0x180084c92  mov     ecx, 3; type
0x180084c97  call    ?MapToProfileGroup@RuntimeProfiler@@YA?AW4ProfileGroup@1@W4IslandType@CContentRoot@@@Z; RuntimeProfiler::MapToProfileGroup(CContentRoot::IslandType)
0x180084c9c  mov     ecx, eax; pg
0x180084c9e  call    ?CreateDynamicProfiler@CDynamicProfiler@RuntimeProfiler@@SAPEAV12@W4ProfileGroup@2@@Z; RuntimeProfiler::CDynamicProfiler::CreateDynamicProfiler(RuntimeProfiler::ProfileGroup)
0x180084ca3  mov     cs:qword_180F72728, rax
0x180084caa  mov     rdi, rax
0x180084cad  test    rax, rax
0x180084cb0  jnz     short loc_180084C3F
0x180084cb2  cmp     [rbp+57h+var_D0], r12b
0x180084cb6  jnz     loc_1800856E4
0x180084cbc  xor     eax, eax
0x180084cbe  mov     this, [rbp+57h+var_50]
0x180084cc2  xor     this, rsp; StackCookie
0x180084cc5  call    __security_check_cookie
0x180084cca  lea     r11, [rsp+120h+var_30]
0x180084cd2  mov     rbx, [r11+58h]
0x180084cd6  movaps  xmm6, xmmword ptr [r11-10h]
  ... truncated ...
```
