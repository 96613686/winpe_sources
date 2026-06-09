# HWCompTreeNodeWinRT::UpdatePrependTransform(void)

- ea: `0x180390f50`
- end: `0x1803917d2`
- name: `?UpdatePrependTransform@HWCompTreeNodeWinRT@@MEAAXXZ`
- size: `2178`
- prototype: `void __fastcall(HWCompTreeNodeWinRT *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180390ed0`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180021840`
- `0x180105d8c`
- `0x18019385c`
- `0x180390dd8`
- `0x180390f50`
- `0x1803917d8`
- `0x180391ef4`
- `0x180392ac4`
- `0x18039332c`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180391543`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803915cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180391652`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803916a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180391543`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803915cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180391652`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803916a2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180391529`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039163b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039168b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803916db`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039174d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039178a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803917c7`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180391529`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039163b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039168b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803916db`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039174d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039178a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803917c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803914cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18039158b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803914cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18039158b`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __fastcall HWCompTreeNodeWinRT::UpdatePrependTransform(HWCompTreeNodeWinRT *this)
{
  CDependencyObject *m_pUIElementNoRef; // r14
  float _11; // xmm7_4
  float _12; // xmm8_4
  float _21; // xmm9_4
  float _22; // xmm10_4
  float _31; // xmm11_4
  float _32; // xmm12_4
  CDependencyObject_vtbl *v9; // rax
  __m128i si128; // xmm6
  KnownTypeIndex (__fastcall *GetTypeIndex)(CDependencyObject *); // rax
  KnownTypeIndex v12; // ax
  KnownTypeIndex i; // cx
  const CClassInfo *ClassInfoByIndex; // rax
  char v15; // al
  int v16; // ebx
  char v17; // di
  bool IsSimplePropertySetToDefault; // al
  char v19; // dl
  int v20; // ecx
  int v21; // eax
  int m_translationScenariosInUse; // eax
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual> *p_m_prependVisual; // rbx
  Windows::UI::Composition::IVisual *v24; // rcx
  Windows::UI::Composition::IVisual_vtbl *v25; // rax
  HRESULT v26; // eax
  HRESULT v27; // edi
  Windows::UI::Composition::IVisual *v28; // rcx
  HRESULT v29; // eax
  HRESULT v30; // ebx
  __m128i v31; // xmm6
  const Windows::Foundation::Numerics::Vector3 *ImplSparse_48; // rax
  int v33; // edx
  float Y; // xmm1_4
  __int64 v35; // rax
  _BYTE *v36; // r9
  __int64 v37; // rcx
  float *v38; // r11
  float v39; // xmm1_4
  __int64 j; // r8
  __int64 v41; // rax
  HRESULT v42; // eax
  HRESULT v43; // ebx
  unsigned __int64 v44; // rdi
  Windows::UI::Composition::IVisual *ptr; // rdi
  HRESULT (__fastcall *get_Clip)(Windows::UI::Composition::IVisual *, Windows::UI::Composition::ICompositionClip **); // rbx
  HRESULT v47; // eax
  HRESULT v48; // ebx
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpressionAnimation> *p_m_prependClipTranslationExpressionCache; // r15
  Windows::UI::Composition::ICompositionObject *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // r15
  __int64 v53; // r13
  unsigned int v54; // eax
  UINT32 v55; // edx
  signed int v56; // eax
  HRESULT v57; // eax
  HRESULT v58; // ebx
  __int64 v59; // r15
  unsigned __int64 v60; // rbx
  __int64 v61; // r13
  unsigned int v62; // eax
  UINT32 v63; // edx
  signed int StringReference; // eax
  HRESULT v65; // eax
  HRESULT v66; // ebx
  Microsoft::WRL::Details::Dummy v67; // r8
  _STOWED_EXCEPTION_INFORMATION_V2 **v68; // rdi
  __int64 (__fastcall *v69)(_STOWED_EXCEPTION_INFORMATION_V2 **, _QWORD); // rbx
  __int64 v70; // rax
  HRESULT v71; // eax
  HRESULT v72; // ebx
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> compositionClipAsCO; // [rsp+28h] [rbp-E0h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+30h] [rbp-D8h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+38h] [rbp-D0h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionClip> compositionClip; // [rsp+40h] [rbp-C8h]
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> prependAsCompositionObject; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE prependTransform[72]; // [rsp+50h] [rbp-B8h] OVERLAPPED BYREF
  int v79; // [rsp+98h] [rbp-70h]
  CMILMatrix4x4 translation4x4; // [rsp+A0h] [rbp-68h] BYREF
  float Z; // [rsp+E0h] [rbp-28h]
  int v82; // [rsp+E4h] [rbp-24h]
  __int128 v83; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v84; // [rsp+F8h] [rbp-10h]
  __m128i v85; // [rsp+108h] [rbp+0h]
  _BYTE v86[80]; // [rsp+118h] [rbp+10h] OVERLAPPED BYREF

  m_pUIElementNoRef = this->m_pUIElementNoRef;
  _11 = this->m_prependTransform._11;
  _12 = this->m_prependTransform._12;
  _21 = this->m_prependTransform._21;
  _22 = this->m_prependTransform._22;
  _31 = this->m_prependTransform._31;
  _32 = this->m_prependTransform._32;
  v9 = m_pUIElementNoRef->__vftable;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  memset(&prependTransform[8], 0, 32);
  GetTypeIndex = v9->GetTypeIndex;
  *(float *)&prependTransform[8] = _11;
  *(float *)&prependTransform[12] = _12;
  *(float *)&prependTransform[24] = _21;
  *(float *)&prependTransform[28] = _22;
  *(float *)&prependTransform[56] = _31;
  *(float *)&prependTransform[60] = _32;
  *(__m128i *)&prependTransform[40] = si128;
  *(_DWORD *)&prependTransform[64] = 0;
  *(_DWORD *)&prependTransform[68] = 1065353216;
  v12 = GetTypeIndex(m_pUIElementNoRef);
  if ( v12 == LayoutTransitionElement )
    goto LABEL_9;
  if ( (unsigned __int16)v12 >= (XYFocusNavigationStrategy|IVectorOfUri) )
  {
    for ( i = v12; ; i = ClassInfoByIndex->m_nBaseTypeIndex )
    {
      ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(i);
      if ( ClassInfoByIndex->m_nIndex == UnknownType )
        break;
      if ( ClassInfoByIndex->m_nIndex == LayoutTransitionElement )
      {
        v15 = 1;
        goto LABEL_8;
      }
    }
    v15 = 0;
LABEL_8:
    if ( v15 )
LABEL_9:
      m_pUIElementNoRef = (CDependencyObject *)this->m_pUIElementNoRef[1].__vftable;
  }
  v16 = HIDWORD(m_pUIElementNoRef[1].m_hasEverHadManagedPeer) & 0x20000000;
  if ( ((__int64)m_pUIElementNoRef[1].m_pParent & 0x20) != 0
    && FacadeStorage::HasAnimation(
         &this->m_sharedState.m_ptr->m_value.m_coreServices->m_facadeStorage,
         m_pUIElementNoRef,
         UIElement_Translation) )
  {
    v17 = 1;
  }
  else
  {
    v17 = 0;
    IsSimplePropertySetToDefault = SimpleProperties::IsSimplePropertySetToDefault(
                                     UIElement_Translation,
                                     m_pUIElementNoRef);
    v19 = 1;
    if ( !IsSimplePropertySetToDefault )
      goto LABEL_12;
  }
  v19 = 0;
LABEL_12:
  v20 = (v16 != 0 ? 4 : 0) | 2;
  if ( !v17 )
    v20 = v16 != 0 ? 4 : 0;
  v21 = v20 | 1;
  if ( !v19 )
    v21 = v20;
  v79 = v21;
  if ( this->m_translationScenariosInUse != v21 )
  {
    *(_QWORD *)prependTransform = 0;
    v42 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IAmbientLight>::As<Windows::UI::Composition::ICompositionObject>(
            (Microsoft::WRL::ComPtr<Windows::UI::Composition::ILayerVisual> *)&this->m_prependVisual,
            (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> >)prependTransform);
    v43 = v42;
    if ( v42 < 0 )
    {
      OnFailure_2990_(v42);
      ppStowedExceptions = 0;
      LODWORD(compositionClipAsCO.ptr_) = 0;
      TraceForFailFast(v43);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&compositionClipAsCO);
      RoFailFastWithErrorContextInternal2(v43, (unsigned int)compositionClipAsCO.ptr_, ppStowedExceptions);
    }
    v44 = -1;
    if ( this->m_offsetTranslationExpressionCache.ptr_ )
    {
      v59 = *(_QWORD *)prependTransform;
      v60 = -1;
      v61 = **(_QWORD **)prependTransform;
      *(_QWORD *)&v86[40] = 0;
      do
        ++v60;
      while ( s_offsetString[v60] );
      if ( v60 > 0xFFFFFFFF )
      {
        RaiseException(0x80070216, 1u, 0, 0);
        __debugbreak();
      }
      v62 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v60);
      v63 = v62 - 1;
      if ( (unsigned int)v60 < v62 )
        v63 = v60;
      StringReference = WindowsCreateStringReference(
                          s_offsetString,
                          v63,
                          (HSTRING_HEADER *)&v86[16],
                          (HSTRING *)&v86[40]);
      if ( StringReference < 0 )
      {
        RaiseException(StringReference, 1u, 0, 0);
        __debugbreak();
      }
      v65 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v61 + 80))(v59, *(_QWORD *)&v86[40]);
      v66 = v65;
      if ( v65 < 0 )
      {
        OnFailure_2990_(v65);
        ppStowedExceptions = 0;
        LODWORD(compositionClipAsCO.ptr_) = 0;
        TraceForFailFast(v66);
        GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&compositionClipAsCO);
        RoFailFastWithErrorContextInternal2(v66, (unsigned int)compositionClipAsCO.ptr_, ppStowedExceptions);
      }
    }
    if ( this->m_matrixTranslationExpressionCache.ptr_ )
    {
      v52 = *(_QWORD *)prependTransform;
      v53 = **(_QWORD **)prependTransform;
      *(_QWORD *)&v86[40] = 0;
      do
        ++v44;
      while ( s_transformMatrixString[v44] );
      if ( v44 > 0xFFFFFFFF )
      {
        RaiseException(0x80070216, 1u, 0, 0);
        __debugbreak();
      }
      v54 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v44);
      v55 = v54 - 1;
      if ( (unsigned int)v44 < v54 )
        v55 = v44;
      v56 = WindowsCreateStringReference(s_transformMatrixString, v55, (HSTRING_HEADER *)&v86[16], (HSTRING *)&v86[40]);
      if ( v56 < 0 )
      {
        RaiseException(v56, 1u, 0, 0);
        __debugbreak();
      }
      v57 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v53 + 80))(v52, *(_QWORD *)&v86[40]);
      v58 = v57;
      if ( v57 < 0 )
      {
        OnFailure_2990_(v57);
        ppStowedExceptions = 0;
        LODWORD(compositionClipAsCO.ptr_) = 0;
        TraceForFailFast(v58);
        GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&compositionClipAsCO);
        RoFailFastWithErrorContextInternal2(v58, (unsigned int)compositionClipAsCO.ptr_, ppStowedExceptions);
      }
    }
    ptr = this->m_prependVisual.ptr_;
    prependAsCompositionObject.ptr_ = 0;
    get_Clip = ptr->get_Clip;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&prependAsCompositionObject);
    v47 = get_Clip(ptr, (Windows::UI::Composition::ICompositionClip **)&prependAsCompositionObject);
    v48 = v47;
    if ( v47 < 0 )
    {
      OnFailure_2990_(v47);
      ppStowedExceptions = 0;
      LODWORD(compositionClipAsCO.ptr_) = 0;
      TraceForFailFast(v48);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&compositionClipAsCO);
      RoFailFastWithErrorContextInternal2(v48, (unsigned int)compositionClipAsCO.ptr_, ppStowedExceptions);
    }
    if ( prependAsCompositionObject.ptr_ )
    {
      ppStowedExceptions = 0;
      Microsoft::WRL::ComPtr<Windows::UI::Composition::IAmbientLight>::As<Windows::UI::Composition::ICompositionObject>(
        (Microsoft::WRL::ComPtr<Windows::UI::Composition::ILayerVisual> *)&prependAsCompositionObject,
        (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> >)&ppStowedExceptions);
      p_m_prependClipTranslationExpressionCache = &this->m_prependClipTranslationExpressionCache;
      if ( this->m_prependClipTranslationExpressionCache.ptr_ )
      {
        v68 = ppStowedExceptions;
        v69 = *(__int64 (__fastcall **)(_STOWED_EXCEPTION_INFORMATION_V2 **, _QWORD))&(*ppStowedExceptions)[1].StackTraceWordSize;
        Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          (Microsoft::WRL::Wrappers::HStringReference *)&v86[16],
          &ExpressionHelper::sc_propertyName_TransformMatrix,
          v67);
        v71 = v69(v68, *(_QWORD *)(v70 + 24));
        v72 = v71;
        if ( v71 < 0 )
        {
          OnFailure_2990_(v71);
          pppStowedExceptions = 0;
          LODWORD(compositionClipAsCO.ptr_) = 0;
          TraceForFailFast(v72);
          GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&compositionClipAsCO);
          RoFailFastWithErrorContextInternal2(v72, (unsigned int)compositionClipAsCO.ptr_, pppStowedExceptions);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&ppStowedExceptions);
    }
    else
    {
      p_m_prependClipTranslationExpressionCache = &this->m_prependClipTranslationExpressionCache;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&this->m_offsetTranslationExpressionCache);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&this->m_matrixTranslationExpressionCache);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)p_m_prependClipTranslationExpressionCache);
    v50 = prependAsCompositionObject.ptr_;
    this->m_translationScenariosInUse = v79;
    if ( v50 )
    {
      prependAsCompositionObject.ptr_ = 0;
      v50->Release(v50);
    }
    v51 = *(_QWORD *)prependTransform;
    if ( *(_QWORD *)prependTransform )
    {
      *(_QWORD *)prependTransform = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
  }
  m_translationScenariosInUse = this->m_translationScenariosInUse;
  if ( m_translationScenariosInUse > 1 )
  {
    HWCompTreeNodeWinRT::EnsureTranslationExpressions(this, (FacadeReferenceWrapper *)m_pUIElementNoRef);
    p_m_prependVisual = &this->m_prependVisual;
  }
  else
  {
    if ( m_translationScenariosInUse )
    {
      v31 = _mm_load_si128((const __m128i *)&_xmm);
      *(float *)&v86[16] = _11;
      *(float *)&v86[20] = _12;
      *(float *)&v86[32] = _21;
      *(float *)&v86[36] = _22;
      *(float *)&v86[64] = _31;
      *(float *)&v86[68] = _32;
      *(_QWORD *)&v86[24] = 0;
      *(_QWORD *)&v86[40] = 0;
      *(__m128i *)&v86[48] = v31;
      *(_DWORD *)&v86[72] = 0;
      *(_DWORD *)&v86[76] = 1065353216;
      if ( (unsigned __int8)((__int64 (__fastcall *)(CDependencyObject *, __int64))SimpleProperty::sparse_host<CUIElement>::query)(
                              m_pUIElementNoRef,
                              2082) )
        ImplSparse_48 = SimpleProperty::details::GetImplSparse_48_(
                          &m_pUIElementNoRef->m_sharedState.m_ptr->m_value.m_coreServices->m_sparseTables.m_UIElement_Translation,
                          m_pUIElementNoRef);
      else
        ImplSparse_48 = &value;
      translation4x4._13 = 1.0;
      *(_OWORD *)&translation4x4.m[0][3] = 0;
      translation4x4._24 = 1.0;
      v33 = 0;
      translation4x4._43 = ImplSparse_48->X;
      Z = ImplSparse_48->Z;
      *(_OWORD *)&translation4x4.m[2][0] = 0;
      *(_QWORD *)&translation4x4.m[3][0] = 1065353216;
      Y = ImplSparse_48->Y;
      v83 = *(_OWORD *)&v86[16];
      translation4x4._44 = Y;
      *(_OWORD *)v86 = *(_OWORD *)&v86[64];
      v82 = 1065353216;
      v84 = *(_OWORD *)&v86[32];
      v85 = v31;
      do
      {
        v35 = 16LL * (unsigned int)v33;
        v36 = &v86[v35 + 16];
        v37 = 0;
        v38 = (float *)((char *)&translation4x4._13 + v35);
        do
        {
          v39 = 0.0;
          for ( j = 0; j != 4; ++j )
          {
            v41 = j;
            v39 = v39 + (float)(*((float *)&v83 + v37 + v41 * 4) * v38[v41]);
          }
          *(float *)&v36[4 * v37++] = v39;
        }
        while ( v37 != 4 );
        ++v33;
      }
      while ( v33 < 4 );
      *(_OWORD *)&prependTransform[8] = *(_OWORD *)&v86[16];
      *(_OWORD *)&prependTransform[24] = *(_OWORD *)&v86[32];
      *(_OWORD *)&prependTransform[40] = *(_OWORD *)&v86[48];
      si128 = *(__m128i *)&v86[48];
      *(_OWORD *)&prependTransform[56] = *(_OWORD *)&v86[64];
    }
    p_m_prependVisual = &this->m_prependVisual;
    v24 = this->m_prependVisual.ptr_;
    v83 = *(_OWORD *)&prependTransform[8];
    v25 = v24->__vftable;
    v84 = *(_OWORD *)&prependTransform[24];
    v85 = si128;
    *(_OWORD *)v86 = *(_OWORD *)&prependTransform[56];
    v26 = ((__int64 (__fastcall *)(Windows::UI::Composition::IVisual *, __int128 *))v25->put_TransformMatrix)(v24, &v83);
    v27 = v26;
    if ( v26 < 0 )
    {
      OnFailure_2990_(v26);
      pppStowedExceptions = 0;
      LODWORD(compositionClipAsCO.ptr_) = 0;
      TraceForFailFast(v27);
      GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&compositionClipAsCO);
      RoFailFastWithErrorContextInternal2(v27, (unsigned int)compositionClipAsCO.ptr_, pppStowedExceptions);
    }
  }
  if ( (this->m_translationScenariosInUse & 4) == 0 )
  {
    v28 = p_m_prependVisual->ptr_;
    pppStowedExceptions = 0;
    LODWORD(compositionClip.ptr_) = 0;
    v29 = ((__int64 (__fastcall *)(Windows::UI::Composition::IVisual *, _STOWED_EXCEPTION_INFORMATION_V2 ***))v28->put_Offset)(
            v28,
            &pppStowedExceptions);
    v30 = v29;
    if ( v29 < 0 )
    {
      OnFailure_2990_(v29);
      pppStowedExceptions = 0;
      LODWORD(compositionClipAsCO.ptr_) = 0;
      TraceForFailFast(v30);
      GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&compositionClipAsCO);
      RoFailFastWithErrorContextInternal2(v30, (unsigned int)compositionClipAsCO.ptr_, pppStowedExceptions);
    }
  }
}

```

## disassembly

```asm
0x180390f50  mov     rax, rsp
0x180390f53  push    rbp
0x180390f54  push    rbx
0x180390f55  push    rsi
0x180390f56  push    rdi
0x180390f57  push    r12
0x180390f59  push    r13
0x180390f5b  push    r14
0x180390f5d  push    r15
0x180390f5f  lea     rbp, [rax-128h]
0x180390f66  sub     rsp, 1E8h
0x180390f6d  movaps  xmmword ptr [rax-58h], xmm6
0x180390f71  movaps  xmmword ptr [rax-68h], xmm7
0x180390f75  movaps  xmmword ptr [rax-78h], xmm8
0x180390f7a  movaps  xmmword ptr [rax-88h], xmm9
0x180390f82  movaps  xmmword ptr [rax-98h], xmm10
0x180390f8a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180390f92  movaps  xmmword ptr [rax-0B8h], xmm12
0x180390f9a  mov     rax, cs:__security_cookie
0x180390fa1  xor     rax, rsp
0x180390fa4  mov     [rbp+120h+var_C0], rax
0x180390fa8  mov     r14, [this+98h]
0x180390faf  xor     r13d, r13d
0x180390fb2  movss   xmm7, dword ptr [this+70h]
0x180390fb7  mov     rsi, this
0x180390fba  movss   xmm8, dword ptr [this+74h]
0x180390fc0  movss   xmm9, dword ptr [this+78h]
0x180390fc6  movss   xmm10, dword ptr [this+7Ch]
0x180390fcc  movss   xmm11, dword ptr [this+80h]
0x180390fd5  movss   xmm12, dword ptr [this+84h]
0x180390fde  mov     this, r14
0x180390fe1  mov     rax, [r14]
0x180390fe4  movdqa  xmm6, cs:__xmm@000000003f8000000000000000000000
0x180390fec  mov     qword ptr [rsp+220h+prependTransform.M13], r13
0x180390ff1  mov     qword ptr [rsp+220h+prependTransform.M23], r13
0x180390ff6  mov     rax, [rax+258h]
0x180390ffd  mov     qword ptr [rbp+120h+prependTransform.M43], r13
0x180391001  movss   [rsp+220h+prependTransform.M13], xmm7
0x180391007  movss   [rsp+220h+prependTransform.M14], xmm8
0x18039100e  movss   [rsp+220h+prependTransform.M23], xmm9
0x180391015  movss   [rsp+220h+prependTransform.M24], xmm10
0x18039101c  movss   [rbp+120h+prependTransform.M43], xmm11
0x180391022  movss   [rbp+120h+prependTransform.M44], xmm12
0x180391028  mov     qword ptr [rsp+220h+prependTransform.M21], r13
0x18039102d  mov     qword ptr [rsp+220h+prependTransform.M31], r13
0x180391032  movaps  xmmword ptr [rsp+220h+prependTransform.M33], xmm6
0x180391037  mov     [rbp+120h+var_198], r13d
0x18039103b  mov     [rbp+120h+var_194], 3F800000h
0x180391042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180391047  mov     ebx, 1C7h
0x18039104c  cmp     bx, ax
0x18039104f  jz      short loc_18039107E
0x180391051  mov     ecx, 43Ch
0x180391056  cmp     ax, cx
0x180391059  jb      short loc_18039108C
0x18039105b  movzx   ecx, ax; eTypeIndex
0x18039105e  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x180391063  cmp     [rax], r13w
0x180391067  jz      loc_180391345
0x18039106d  cmp     [rax], bx
0x180391070  jz      short loc_180391078
0x180391072  movzx   ecx, word ptr [rax+2]
0x180391076  jmp     short loc_18039105E
0x180391078  mov     al, 1
0x18039107a  test    al, al
0x18039107c  jz      short loc_18039108C
0x18039107e  mov     rax, [rsi+98h]
0x180391085  mov     r14, [rax+180h]
0x18039108c  mov     ebx, [r14+94h]
0x180391093  mov     eax, [r14+98h]
0x18039109a  and     ebx, 20000000h
0x1803910a0  shr     eax, 5
0x1803910a3  test    al, 1
0x1803910a5  jnz     loc_18039145C
0x1803910ab  mov     ecx, 822h; propertyIndex
0x1803910b0  mov     rdx, r14; obj
0x1803910b3  mov     dil, r13b
0x1803910b6  call    ?IsSimplePropertySetToDefault@SimpleProperties@@YA_NW4KnownPropertyIndex@@PEBX@Z; SimpleProperties::IsSimplePropertySetToDefault(KnownPropertyIndex,void const *)
0x1803910bb  mov     dl, 1
0x1803910bd  test    al, al
0x1803910bf  jnz     loc_180391483
0x1803910c5  neg     ebx
0x1803910c7  sbb     eax, eax
0x1803910c9  and     eax, 4
0x1803910cc  mov     ecx, eax
0x1803910ce  or      ecx, 2
0x1803910d1  test    dil, dil
0x1803910d4  cmovz   ecx, eax
0x1803910d7  mov     eax, ecx
0x1803910d9  or      eax, 1
0x1803910dc  test    dl, dl
0x1803910de  cmovz   eax, ecx
0x1803910e1  mov     [rbp+120h+var_190], eax
0x1803910e4  cmp     [rsi+290h], eax
0x1803910ea  jnz     loc_180391368
0x1803910f0  mov     eax, [rsi+290h]
0x1803910f6  cmp     eax, 1
0x1803910f9  jg      loc_18039132E
0x1803910ff  test    eax, eax
0x180391101  jnz     loc_1803911C8
0x180391107  movaps  xmm0, xmmword ptr [rsp+220h+prependTransform.M13]
0x18039110c  lea     rbx, [rsi+140h]
0x180391113  mov     this, [rbx]
0x180391116  lea     rdx, [rbp+120h+var_140]
0x18039111a  movaps  xmm1, xmmword ptr [rsp+220h+prependTransform.M23]
0x18039111f  movaps  [rbp+120h+var_140], xmm0
0x180391123  movaps  xmm0, xmmword ptr [rbp+120h+prependTransform.M43]
0x180391127  mov     rax, [this]
0x18039112a  movaps  [rbp+120h+var_130], xmm1
0x18039112e  movaps  [rbp+120h+var_120], xmm6
0x180391132  movaps  xmmword ptr [rbp+10h], xmm0
0x180391136  mov     rax, [rax+130h]
0x18039113d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180391142  mov     edi, eax
0x180391144  test    eax, eax
0x180391146  js      loc_180391758
0x18039114c  test    byte ptr [rsi+290h], 4
0x180391153  jnz     short loc_180391181
0x180391155  mov     this, [rbx]
0x180391158  lea     rdx, [rsp+220h+pppStowedExceptions]
0x18039115d  xor     eax, eax
0x18039115f  mov     [rsp+220h+pppStowedExceptions], rax
0x180391164  mov     dword ptr [rsp+220h+compositionClip.ptr_], eax
0x180391168  mov     rax, [this]
0x18039116b  mov     rax, [rax+0A8h]
0x180391172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180391177  mov     ebx, eax
0x180391179  test    eax, eax
0x18039117b  js      loc_180391795
0x180391181  mov     this, [rbp+120h+var_C0]
0x180391185  xor     this, rsp; StackCookie
0x180391188  call    __security_check_cookie
0x18039118d  lea     r11, [rsp+220h+var_38]
0x180391195  movaps  xmm6, xmmword ptr [r11-18h]
0x18039119a  movaps  xmm7, xmmword ptr [r11-28h]
0x18039119f  movaps  xmm8, xmmword ptr [r11-38h]
0x1803911a4  movaps  xmm9, xmmword ptr [r11-48h]
0x1803911a9  movaps  xmm10, xmmword ptr [r11-58h]
0x1803911ae  movaps  xmm11, xmmword ptr [r11-68h]
0x1803911b3  movaps  xmm12, xmmword ptr [r11-78h]
0x1803911b8  mov     rsp, r11
0x1803911bb  pop     r15
0x1803911bd  pop     r14
0x1803911bf  pop     r13
0x1803911c1  pop     r12
0x1803911c3  pop     rdi
0x1803911c4  pop     rsi
0x1803911c5  pop     rbx
0x1803911c6  pop     rbp
0x1803911c7  retn
0x1803911c8  movsxd  this, cs:dword_180C26FD0
0x1803911cf  mov     edx, 822h
0x1803911d4  movdqa  xmm6, cs:__xmm@000000003f8000000000000000000000
0x1803911dc  add     this, r14
0x1803911df  mov     rax, cs:?query@?$sparse_host@VCUIElement@@@SimpleProperty@@2Q8CUIElement@@EBA_NW4KnownPropertyIndex@@@ZEQ3@; bool (CUIElement::*SimpleProperty::sparse_host<CUIElement>::query)(KnownPropertyIndex)
0x1803911e6  movss   dword ptr [rbp+120h+prepend4x4.___u0+8], xmm7
0x1803911eb  movss   dword ptr [rbp+120h+prepend4x4.___u0+0Ch], xmm8
0x1803911f1  movss   dword ptr [rbp+120h+prepend4x4.___u0+18h], xmm9
0x1803911f7  movss   dword ptr [rbp+120h+prepend4x4.___u0+1Ch], xmm10
0x1803911fd  movss   dword ptr [rbp+120h+prepend4x4.___u0+38h], xmm11
0x180391203  movss   dword ptr [rbp+120h+prepend4x4.___u0+3Ch], xmm12
0x180391209  mov     qword ptr [rbp+120h+prepend4x4.___u0+10h], 0
0x180391211  mov     qword ptr [rbp+120h+prepend4x4.___u0+20h], 0
0x180391219  movaps  xmmword ptr [rbp+120h+prepend4x4.___u0+28h], xmm6
0x18039121d  mov     [rbp+120h+var_C8], 0
0x180391224  mov     [rbp+120h+var_C4], 3F800000h
0x18039122b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180391230  test    al, al
0x180391232  jnz     loc_18039134D
0x180391238  lea     rax, value
0x18039123f  xorps   xmm0, xmm0
0x180391242  mov     dword ptr [rbp+120h+translation4x4.___u0+8], 3F800000h
0x180391249  movups  xmmword ptr [rbp+120h+translation4x4.___u0+0Ch], xmm0
0x18039124d  mov     dword ptr [rbp+120h+translation4x4.___u0+1Ch], 3F800000h
0x180391254  mov     edx, r13d
0x180391257  movss   xmm0, dword ptr [rax]
0x18039125b  xorps   xmm1, xmm1
0x18039125e  movss   dword ptr [rbp+120h+translation4x4.___u0+38h], xmm0
0x180391263  movss   xmm0, dword ptr [rax+8]
0x180391268  movss   [rbp+120h+var_148], xmm0
0x18039126d  movaps  xmm0, xmmword ptr [rbp+120h+prepend4x4.___u0+8]
0x180391271  movups  xmmword ptr [rbp+120h+translation4x4.___u0+20h], xmm1
0x180391275  mov     qword ptr [rbp+120h+translation4x4.___u0+30h], 3F800000h
0x18039127d  movss   xmm1, dword ptr [rax+4]
0x180391282  movaps  [rbp+120h+var_140], xmm0
0x180391286  movaps  xmm0, xmmword ptr [rbp+120h+prepend4x4.___u0+38h]
0x18039128a  movss   dword ptr [rbp+120h+translation4x4.___u0+3Ch], xmm1
0x18039128f  movaps  xmm1, xmmword ptr [rbp+120h+prepend4x4.___u0+18h]
0x180391293  movaps  xmmword ptr [rbp+10h], xmm0
0x180391297  mov     [rbp+120h+var_144], 3F800000h
0x18039129e  movaps  [rbp+120h+var_130], xmm1
0x1803912a2  movaps  [rbp+120h+var_120], xmm6
0x1803912a6  mov     eax, edx
0x1803912a8  lea     r9, [rbp+120h+prepend4x4.___u0+8]
0x1803912ac  shl     rax, 4
0x1803912b0  lea     r11, [rbp+120h+translation4x4.___u0+8]
0x1803912b4  add     r9, rax
0x1803912b7  mov     this, r13
0x1803912ba  add     r11, rax
0x1803912bd  lea     r10, [rbp+120h+var_140]
0x1803912c1  xorps   xmm1, xmm1
0x1803912c4  lea     r10, [r10+this*4]
0x1803912c8  mov     r8, r13
0x1803912cb  lea     rax, ds:0[r8*4]
0x1803912d3  inc     r8
0x1803912d6  movss   xmm0, dword ptr [r10+rax*4]
0x1803912dc  mulss   xmm0, dword ptr [rax+r11]
0x1803912e2  addss   xmm1, xmm0
0x1803912e6  cmp     r8, 4
0x1803912ea  jnz     short loc_1803912CB
0x1803912ec  movss   dword ptr [r9+this*4], xmm1
0x1803912f2  inc     this
0x1803912f5  cmp     this, r8
0x1803912f8  jnz     short loc_1803912BD
0x1803912fa  inc     edx
0x1803912fc  cmp     edx, r8d
0x1803912ff  jl      short loc_1803912A6
0x180391301  movaps  xmm0, xmmword ptr [rbp+120h+prepend4x4.___u0+8]
0x180391305  movaps  xmmword ptr [rsp+220h+prependTransform.M13], xmm0
0x18039130a  movaps  xmm0, xmmword ptr [rbp+120h+prepend4x4.___u0+18h]
0x18039130e  movaps  xmmword ptr [rsp+220h+prependTransform.M23], xmm0
0x180391313  movaps  xmm0, xmmword ptr [rbp+120h+prepend4x4.___u0+28h]
0x180391317  movaps  xmmword ptr [rsp+220h+prependTransform.M33], xmm0
0x18039131c  movaps  xmm0, xmmword ptr [rbp+120h+prepend4x4.___u0+38h]
0x180391320  movaps  xmm6, xmmword ptr [rsp+220h+prependTransform.M33]
0x180391325  movaps  xmmword ptr [rbp+120h+prependTransform.M43], xmm0
0x180391329  jmp     loc_180391107
0x18039132e  mov     rdx, r14; elementForTranslation
0x180391331  mov     this, rsi; this
0x180391334  call    ?EnsureTranslationExpressions@HWCompTreeNodeWinRT@@IEAAXPEAVCUIElement@@@Z; HWCompTreeNodeWinRT::EnsureTranslationExpressions(CUIElement *)
0x180391339  lea     rbx, [rsi+140h]
0x180391340  jmp     loc_18039114C
0x180391345  mov     al, r13b
0x180391348  jmp     loc_18039107A
0x18039134d  mov     rax, [r14+10h]
0x180391351  mov     rdx, r14; obj
0x180391354  mov     this, [rax]
0x180391357  add     this, 0B30h; table
0x18039135e  call    SimpleProperty__details__GetImplSparse_48_
0x180391363  jmp     loc_18039123F
0x180391368  lea     this, [rsi+140h]; this
0x18039136f  mov     qword ptr [rsp+220h+prependTransform.M11], r13
0x180391374  lea     rdx, [rsp+220h+prependTransform]; p
0x180391379  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UIAmbientLight@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IAmbientLight>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x18039137e  mov     ebx, eax
0x180391380  test    eax, eax
0x180391382  js      loc_180391609
0x180391388  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18039138c  mov     ecx, 0FFFFFFFFh
0x180391391  cmp     [rsi+1E8h], r13
0x180391398  jnz     loc_18039154A
0x18039139e  lea     r12, [rsi+1F0h]
0x1803913a5  cmp     [r12], r13
0x1803913a9  jnz     loc_18039148B
0x1803913af  mov     rdi, [rsi+140h]
0x1803913b6  lea     this, [rsp+220h+prependAsCompositionObject]; this
0x1803913bb  mov     [rsp+220h+prependAsCompositionObject.ptr_], r13
0x1803913c0  mov     rax, [rdi]
0x1803913c3  mov     rbx, [rax+70h]
0x1803913c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803913cc  lea     rdx, [rsp+220h+prependAsCompositionObject]
0x1803913d1  mov     this, rdi
0x1803913d4  mov     rax, rbx
0x1803913d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803913dc  mov     ebx, eax
0x1803913de  test    eax, eax
0x1803913e0  js      loc_1803916A9
0x1803913e6  cmp     [rsp+220h+prependAsCompositionObject.ptr_], r13
0x1803913eb  jnz     loc_1803915D6
0x1803913f1  lea     r15, [rsi+1F8h]
0x1803913f8  lea     this, [rsi+1E8h]; this
0x1803913ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180391404  mov     this, r12; this
0x180391407  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18039140c  mov     this, r15; this
0x18039140f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180391414  mov     this, [rsp+220h+prependAsCompositionObject.ptr_]
0x180391419  mov     eax, [rbp+120h+var_190]
0x18039141c  mov     [rsi+290h], eax
0x180391422  test    this, this
0x180391425  jz      short loc_180391438
0x180391427  mov     [rsp+220h+prependAsCompositionObject.ptr_], r13
0x18039142c  mov     rax, [this]
0x18039142f  mov     rax, [rax+10h]
0x180391433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180391438  mov     this, qword ptr [rsp+220h+prependTransform.M11]
0x18039143d  test    this, this
0x180391440  jz      loc_1803910F0
0x180391446  mov     qword ptr [rsp+220h+prependTransform.M11], r13
0x18039144b  mov     rax, [this]
0x18039144e  mov     rax, [rax+10h]
0x180391452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180391457  jmp     loc_1803910F0
0x18039145c  mov     rax, [rsi+10h]
0x180391460  mov     r8d, 822h; facadeID
0x180391466  mov     rdx, r14; object
0x180391469  mov     this, [rax]
0x18039146c  add     this, 978h; this
0x180391473  call    ?HasAnimation@FacadeStorage@@QEBA_NPEBVCDependencyObject@@W4KnownPropertyIndex@@@Z; FacadeStorage::HasAnimation(CDependencyObject const *,KnownPropertyIndex)
0x180391478  test    al, al
  ... truncated ...
```
