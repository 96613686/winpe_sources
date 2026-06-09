# DirectUI::PointerDownThemeAnimation::CreateTimelines(uchar,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *)

- ea: `0x180493040`
- end: `0x1804940cb`
- name: `?CreateTimelines@PointerDownThemeAnimation@DirectUI@@UEAAJEPEAU?$IVector@PEAVTimeline@Animation@Media@Xaml@UI@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `4235`
- prototype: `HRESULT __fastcall(DirectUI::PointerDownThemeAnimation *this, unsigned __int8 bOnlyGenerateSteadyState, Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *pTimelineCollection)`
- caller_count: `0`
- callee_count: `43`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x18000b630`
- `0x18000b660`
- `0x18000b724`
- `0x18001f3c0`
- `0x18005f28c`
- `0x18005f6dc`
- `0x18005fb04`
- `0x18006cfd0`
- `0x18007d590`
- `0x1800d5330`
- `0x1800f3fb4`
- `0x1800fe130`
- `0x180128e0c`
- `0x18018fa54`
- `0x1801df610`
- `0x1801e4a14`
- `0x1801f943c`
- `0x180243f44`
- `0x18034c7d4`
- `0x180363614`
- `0x180421044`
- `0x180430ae4`
- `0x1804828c4`
- `0x180493040`
- `0x1804940d4`
- `0x1804946d8`
- `0x180494e04`
- `0x1804951ac`
- `0x1805a496c`
- `0x1806f6f8c`
- `0x1806f72ec`
- `0x18076e110`
- `0x18076f014`
- `0x18078c070`
- `0x1808fe580`
- `0x1808fe6fc`
- `0x1808fe7ac`
- `0x1808fe894`
- `0x1809f6308`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180493170`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804931a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804931d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18049320b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18049323c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180493170`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804931a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804931d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18049320b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18049323c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180493401`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180493401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180494076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180494076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180493154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18049318d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1804931c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1804931f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180493228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180493154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18049318d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1804931c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1804931f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180493228`

## pseudocode

```c
__int64 __fastcall DirectUI::PointerDownThemeAnimation::CreateTimelines(
        DirectUI::PointerDownThemeAnimation *this,
        unsigned __int8 bOnlyGenerateSteadyState,
        Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *pTimelineCollection)
{
  HRESULT StoryboardTargetName; // eax
  unsigned int v7; // ebx
  DirectUI::DependencyObject *v8; // rsi
  HRESULT v9; // eax
  DirectUI::DependencyObject *Handle; // rax
  HRESULT v11; // eax
  CTimeline *v12; // rax
  xref_ptr<CTransformCollection> *v13; // rax
  DirectUI::DXamlCore *Current; // rbx
  HRESULT PeerPrivate; // eax
  DirectUI::CompositeTransform *ptr; // r14
  bool v17; // zf
  Windows::Foundation::Point v18; // xmm7_8
  HRESULT v19; // eax
  long double v20; // xmm6_8
  float v21; // xmm10_4
  float v22; // xmm9_4
  double v23; // xmm0_8
  DirectUI::DependencyObject_vtbl *v24; // rax
  float v25; // xmm11_4
  double v26; // xmm0_8
  float v27; // xmm12_4
  HRESULT ParentStaticPrivate; // eax
  CDependencyObject *m_ptr; // rsi
  Windows::UI::Xaml::IDependencyObject *v30; // rcx
  int v31; // ebx
  HRESULT v32; // eax
  CAnimation *v33; // rax
  DirectUI::TranslateTransform *v34; // rbx
  double v35; // xmm0_8
  float v36; // xmm6_4
  double v37; // xmm0_8
  HRESULT v38; // eax
  const Windows::Internal::StringReference *v39; // rax
  const Windows::Internal::StringReference *v40; // rax
  double v41; // xmm9_8
  double v42; // xmm9_8
  double v43; // xmm10_8
  double v44; // xmm10_8
  HRESULT v45; // eax
  Windows::UI::Xaml::Media::IGeneralTransform *v46; // rsi
  HRESULT v47; // eax
  HRESULT v48; // eax
  HRESULT v49; // eax
  ctl::forwarder_holder<Windows::UI::Xaml::Core::Direct::IXamlDirectObject,CDependencyObject> *v50; // rcx
  ctl::WeakReferenceSourceNoThreadId *v51; // rcx
  ctl::WeakReferenceSourceNoThreadId *v52; // rcx
  ctl::WeakReferenceSourceNoThreadId *v53; // rcx
  __int64 *p_m_begintime; // rcx
  const wchar_t *BufferAndCount; // rax
  CDependencyObject *v56; // rax
  HRESULT v57; // ecx
  CDependencyObject *v58; // rax
  HRESULT v59; // ecx
  __m128d v60; // xmm7
  __m128d v61; // xmm7
  HSTRING__ *hstring; // rcx
  unsigned __int8 *bInternalRef; // [rsp+28h] [rbp-E0h]
  __int64 bInternalRef_8; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8a; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8b; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8c; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8d; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8e; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8f; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8g; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8h; // [rsp+30h] [rbp-D8h]
  __int64 bInternalRef_8i; // [rsp+30h] [rbp-D8h]
  ctl::ComPtr<DirectUI::CompositeTransform> spCompositeTransform; // [rsp+48h] [rbp-C0h] BYREF
  ctl::ComPtr<DirectUI::PlaneProjection> spProjection; // [rsp+50h] [rbp-B8h] BYREF
  ctl::ComPtr<DirectUI::TransformGroup> spTransformGroup; // [rsp+58h] [rbp-B0h] BYREF
  xref_ptr<CDependencyObject> spCoreDO; // [rsp+60h] [rbp-A8h] BYREF
  ctl::ComPtr<DirectUI::DependencyObject> spParentAsDO; // [rsp+68h] [rbp-A0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spParentAsIDO; // [rsp+70h] [rbp-98h] BYREF
  xref_ptr<CDependencyObject> spParentAsCDO; // [rsp+78h] [rbp-90h] BYREF
  ctl::ComPtr<DirectUI::TranslateTransform> spTranslateTransform; // [rsp+80h] [rbp-88h] BYREF
  ctl::ComPtr<DirectUI::TransformCollection> spTransforms; // [rsp+88h] [rbp-80h] BYREF
  ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> halfDifferenceY; // [rsp+90h] [rbp-78h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spTarget; // [rsp+98h] [rbp-70h] BYREF
  Windows::Internal::String strTargetName; // [rsp+A0h] [rbp-68h] BYREF
  HSTRING__ *controlWidth; // [rsp+A8h] [rbp-60h] BYREF
  float halfDifferenceX; // [rsp+B0h] [rbp-58h] BYREF
  float controlHeight; // [rsp+B4h] [rbp-54h] BYREF
  float v90; // [rsp+B8h] [rbp-50h] BYREF
  DirectUI::ThemeGeneratorHelper depressionSupplier; // [rsp+C0h] [rbp-48h] BYREF
  DirectUI::ThemeGeneratorHelper tiltXSupplier; // [rsp+1C0h] [rbp+B8h] BYREF
  DirectUI::ThemeGeneratorHelper tiltYSupplier; // [rsp+2C0h] [rbp+1B8h] BYREF
  DirectUI::ThemeGeneratorHelper scaleYSupplier; // [rsp+3C0h] [rbp+2B8h] BYREF
  xephemeral_string_ptr parameters[1]; // [rsp+4C0h] [rbp+3B8h] BYREF
  Windows::Internal::StringReference strScaleXPropertyName; // [rsp+4E0h] [rbp+3D8h] BYREF
  Windows::Internal::StringReference strScaleYPropertyName; // [rsp+500h] [rbp+3F8h] BYREF
  Windows::Internal::StringReference strGlobalOffsetZPropertyName; // [rsp+520h] [rbp+418h] BYREF
  Windows::Internal::StringReference strRotateYPropertyName; // [rsp+540h] [rbp+438h] BYREF
  Windows::Internal::StringReference strRotateXPropertyName; // [rsp+560h] [rbp+458h] BYREF

  controlWidth = 0;
  strTargetName._hstring = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&strTargetName);
  ctl::do_query_interface<Windows::UI::Xaml::IDependencyObject,DirectUI::DependencyObject>(
    (Windows::UI::Xaml::IDependencyObject **)&strTargetName,
    (DirectUI::DependencyObject *)((unsigned __int128)&this->m_tpAnimationTarget.m_trackerReference.m_value[-1]
                                 & ((unsigned __int128)-(__int128)(unsigned __int64)this->m_tpAnimationTarget.m_trackerReference.m_value >> 64)));
  if ( strTargetName._hstring
    || (StoryboardTargetName = this->get_TargetName(
                                 &this->Windows::UI::Xaml::Media::Animation::IPointerDownThemeAnimation,
                                 &controlWidth),
        v7 = StoryboardTargetName,
        StoryboardTargetName >= 0)
    && (controlWidth
     || (StoryboardTargetName = ThemeAnimation_GetStoryboardTargetName(this, &controlWidth),
         v7 = StoryboardTargetName,
         StoryboardTargetName >= 0)) )
  {
    if ( !TiltHelper::IsTiltAnimationEnabled() )
    {
      v60 = (__m128d)_mm_unpacklo_ps((__m128)0LL, (__m128)0LL);
      v61 = _mm_unpacklo_pd(v60, v60);
      StoryboardTargetName = DirectUI::ThemeGenerator::AddTimelinesForThemeAnimation(
                               20,
                               1,
                               controlWidth,
                               (Windows::UI::Xaml::IDependencyObject *)strTargetName._hstring,
                               bOnlyGenerateSteadyState,
                               *(Windows::Foundation::Point *)&v61.m128d_f64[0],
                               *(Windows::Foundation::Point *)&v61.m128d_f64[1],
                               pTimelineCollection);
      v7 = StoryboardTargetName;
      if ( StoryboardTargetName >= 0 )
        goto $Cleanup_3324;
      goto LABEL_125;
    }
    if ( WindowsCreateStringReference(
           L"(UIElement.Projection).(PlaneProjection.RotationX)",
           0x32u,
           (HSTRING_HEADER *)&strRotateXPropertyName._header.Reserved.Reserved2[8],
           (HSTRING *)&strRotateXPropertyName._header) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( WindowsCreateStringReference(
           L"(UIElement.Projection).(PlaneProjection.RotationY)",
           0x32u,
           (HSTRING_HEADER *)&strRotateYPropertyName._header.Reserved.Reserved2[8],
           (HSTRING *)&strRotateYPropertyName._header) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( WindowsCreateStringReference(
           L"(UIElement.Projection).(PlaneProjection.GlobalOffsetZ)",
           0x36u,
           (HSTRING_HEADER *)&strGlobalOffsetZPropertyName._header.Reserved.Reserved2[8],
           (HSTRING *)&strGlobalOffsetZPropertyName._header) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( WindowsCreateStringReference(
           L"(UIElement.RenderTransform).(ScaleTransform.ScaleX)",
           0x33u,
           (HSTRING_HEADER *)&strScaleXPropertyName._header.Reserved.Reserved2[8],
           (HSTRING *)&strScaleXPropertyName._header) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( WindowsCreateStringReference(
           L"(UIElement.RenderTransform).(ScaleTransform.ScaleY)",
           0x33u,
           (HSTRING_HEADER *)&strScaleYPropertyName._header.Reserved.Reserved2[8],
           (HSTRING *)&strScaleYPropertyName._header) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v8 = 0;
    spParentAsDO.ptr_ = 0;
    spCompositeTransform.ptr_ = 0;
    spTransformGroup.ptr_ = 0;
    spProjection.ptr_ = 0;
    spCoreDO.m_ptr = 0;
    if ( strTargetName._hstring )
    {
      ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spCompositeTransform);
      if ( strTargetName._hstring )
      {
        v9 = (**(__int64 (__fastcall ***)(HSTRING__ *, GUID *, ctl::ComPtr<DirectUI::CompositeTransform> *))strTargetName._hstring)(
               strTargetName._hstring,
               &GUID_659a8956_ef29_4f50_8724_7e3207d23076,
               &spCompositeTransform);
        v7 = v9;
        if ( v9 < 0 )
          goto LABEL_21;
      }
      Handle = (DirectUI::DependencyObject *)DirectUI::DependencyObject::GetHandle(spCompositeTransform.ptr_);
      if ( Handle )
      {
        spParentAsDO.ptr_ = Handle;
        v8 = Handle;
        CDependencyObject::AddRef((CDependencyObject *)Handle);
      }
LABEL_31:
      ptr = spCompositeTransform.ptr_;
      v9 = ctl::make<DirectUI::PlaneProjection>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::PlaneProjection> >)&spTransformGroup);
      v7 = v9;
      if ( v9 < 0 )
        goto LABEL_21;
      v9 = ctl::make<DirectUI::CompositeTransform>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::CompositeTransform> >)&spProjection);
      v7 = v9;
      if ( v9 < 0 )
        goto LABEL_21;
      if ( CQuirksMode2::m_quirkCacheSuppressions )
      {
        v17 = !CQuirksMode2::XamlQuirkIsEnabled(0x20040u);
      }
      else
      {
        InitOnceExecuteOnce(&InitOnce, CQuirksMode2::InitOnceCallback, &qword_180F72750, 0);
        v17 = ((*(unsigned __int8 *)(qword_180F72750 + 1) >> 3) & 1) == 0;
      }
      if ( !v17 )
      {
        v18 = (Windows::Foundation::Point)_mm_unpacklo_ps((__m128)0LL, (__m128)0LL).m128_u64[0];
        DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
          (DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime,
          v18,
          v18,
          controlWidth,
          (Windows::UI::Xaml::IDependencyObject *)strTargetName._hstring,
          bOnlyGenerateSteadyState,
          pTimelineCollection);
        v19 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime);
        v7 = v19;
        if ( v19 >= 0 )
        {
          v19 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                  (DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime,
                  (HSTRING__ *)strGlobalOffsetZPropertyName._header.Reserved.Reserved1,
                  PointerDirection_BothAxes,
                  0.0,
                  0.0,
                  bInternalRef_8);
          v7 = v19;
          if ( v19 >= 0 )
          {
            v20 = DOUBLE_1_0;
            v19 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                    (DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime,
                    (HSTRING__ *)strGlobalOffsetZPropertyName._header.Reserved.Reserved1,
                    PointerDirection_BothAxes,
                    1.0,
                    -25.0,
                    bInternalRef_8a);
            v7 = v19;
            if ( v19 >= 0 )
            {
              v21 = FLOAT_17_188734;
              v22 = FLOAT_17_188734;
LABEL_83:
              DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime);
              v46 = &ptr->Windows::UI::Xaml::Media::IGeneralTransform;
              v9 = ptr->DirectUI::Transform::DirectUI::TransformGenerated::DirectUI::GeneralTransform::Windows::UI::Xaml::Media::IGeneralTransform::IInspectable::IUnknown::__vftable[1].get_Inverse(
                     &ptr->Windows::UI::Xaml::Media::IGeneralTransform,
                     (Windows::UI::Xaml::Media::IGeneralTransform **)((__int64)&spTransformGroup.ptr_->Windows::UI::Xaml::Media::IGeneralTransform
                                                                    & -(__int64)(spTransformGroup.ptr_ != 0)));
              v7 = v9;
              if ( v9 < 0 )
                goto LABEL_21;
              if ( spCoreDO.m_ptr )
              {
                v9 = v46->__vftable[1].GetRuntimeClassName(
                       &ptr->Windows::UI::Xaml::Media::IGeneralTransform,
                       (HSTRING__ **)((__int64)&spCoreDO.m_ptr[2].ctl::forwarder_holder<Windows::UI::Xaml::Core::Direct::IXamlDirectObject,CDependencyObject>
                                    & -(__int64)(spCoreDO.m_ptr != 0)));
                v7 = v9;
                if ( v9 < 0 )
                {
LABEL_21:
                  OnFailure_2990_(v9);
LABEL_22:
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spCoreDO);
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spProjection);
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransformGroup);
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spCompositeTransform);
LABEL_23:
                  xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&spParentAsDO);
                  goto $Cleanup_3324;
                }
              }
              else
              {
                v9 = v46->__vftable[1].GetRuntimeClassName(
                       &ptr->Windows::UI::Xaml::Media::IGeneralTransform,
                       (HSTRING__ **)((__int64)&spProjection.ptr_[1] & -(__int64)(spProjection.ptr_ != 0)));
                v7 = v9;
                if ( v9 < 0 )
                  goto LABEL_21;
              }
              DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
                (DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime,
                v18,
                v18,
                controlWidth,
                (Windows::UI::Xaml::IDependencyObject *)strTargetName._hstring,
                bOnlyGenerateSteadyState,
                pTimelineCollection);
              v47 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime);
              v7 = v47;
              if ( v47 < 0 )
              {
                OnFailure_2990_(v47);
              }
              else
              {
                v48 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                        (DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime,
                        (HSTRING__ *)strRotateYPropertyName._header.Reserved.Reserved1,
                        PointerDirection_XAxis,
                        0.0,
                        v22,
                        bInternalRef_8f);
                v7 = v48;
                if ( v48 < 0
                  || (v48 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                              (DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime,
                              (HSTRING__ *)strRotateYPropertyName._header.Reserved.Reserved1,
                              PointerDirection_XAxis,
                              v20,
                              COERCE_FLOAT(LODWORD(v22) ^ _xmm),
                              bInternalRef_8g),
                      v7 = v48,
                      v48 < 0) )
                {
                  OnFailure_2990_(v48);
                  goto LABEL_97;
                }
                DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
                  (DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime,
                  v18,
                  v18,
                  controlWidth,
                  (Windows::UI::Xaml::IDependencyObject *)strTargetName._hstring,
                  bOnlyGenerateSteadyState,
                  pTimelineCollection);
                v49 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
                v7 = v49;
                if ( v49 >= 0 )
                {
                  v49 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                          (DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime,
                          (HSTRING__ *)strRotateXPropertyName._header.Reserved.Reserved1,
                          PointerDirection_YAxis,
                          0.0,
                          COERCE_FLOAT(LODWORD(v21) ^ _xmm),
                          bInternalRef_8h);
                  v7 = v49;
                  if ( v49 >= 0 )
                  {
                    v49 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                            (DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime,
                            (HSTRING__ *)strRotateXPropertyName._header.Reserved.Reserved1,
                            PointerDirection_YAxis,
                            v20,
                            v21,
                            bInternalRef_8i);
                    v7 = v49;
                    if ( v49 >= 0 )
                    {
                      DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
LABEL_97:
                      DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime);
                      if ( spCoreDO.m_ptr )
                      {
                        v50 = &spCoreDO.m_ptr->ctl::forwarder_holder<Windows::UI::Xaml::Core::Direct::IXamlDirectObject,CDependencyObject>;
                        spCoreDO.m_ptr = 0;
                        v50->m_forwarder.Release(&v50->m_forwarder);
                      }
                      if ( spProjection.ptr_ )
                      {
                        v51 = &spProjection.ptr_->ctl::WeakReferenceSourceNoThreadId;
                        spProjection.ptr_ = 0;
                        v51->Release(v51);
                      }
                      if ( spTransformGroup.ptr_ )
                      {
                        v52 = &spTransformGroup.ptr_->ctl::WeakReferenceSourceNoThreadId;
                        spTransformGroup.ptr_ = 0;
                        v52->Release(v52);
                      }
                      if ( spCompositeTransform.ptr_ )
                      {
                        v53 = &spCompositeTransform.ptr_->ctl::WeakReferenceSourceNoThreadId;
                        spCompositeTransform.ptr_ = 0;
                        v53->Release(v53);
                      }
                      goto LABEL_23;
                    }
                  }
                }
                OnFailure_2990_(v49);
                DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
              }
              p_m_begintime = &tiltXSupplier.m_begintime;
LABEL_112:
              DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)p_m_begintime);
              goto LABEL_22;
            }
          }
        }
        goto LABEL_110;
      }
      v23 = ((double (__fastcall *)(DirectUI::DependencyObject *))v8->Windows::UI::Xaml::IDependencyObject::IInspectable::IUnknown::__vftable[3].OnParentUpdated)(v8);
      v24 = v8->Windows::UI::Xaml::IDependencyObject::IInspectable::IUnknown::__vftable;
      halfDifferenceX = *(float *)&v23;
      v25 = *(float *)&v23;
      v26 = ((double (__fastcall *)(DirectUI::DependencyObject *))v24[3].OnTreeParentUpdated)(v8);
      controlHeight = *(float *)&v26;
      v27 = *(float *)&v26;
      spParentAsCDO.m_ptr = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spParentAsCDO);
      ParentStaticPrivate = DirectUI::VisualTreeHelper::GetParentStaticPrivate(
                              ptr,
                              1u,
                              (Windows::UI::Xaml::IDependencyObject **)&spParentAsCDO,
                              0,
                              bInternalRef);
      v7 = ParentStaticPrivate;
      if ( ParentStaticPrivate < 0 )
      {
        OnFailure_2990_(ParentStaticPrivate);
      }
      else
      {
        spParentAsIDO.ptr_ = 0;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spParentAsIDO);
        m_ptr = spParentAsCDO.m_ptr;
        if ( spParentAsCDO.m_ptr )
          ((void (__fastcall *)(CDependencyObject *, GUID *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))spParentAsCDO.m_ptr->ReleaseOverride)(
            spParentAsCDO.m_ptr,
            &GUID_fc8946bd_a3a2_4969_8174_25b5d3c28033,
            &spParentAsIDO);
        v30 = spParentAsIDO.ptr_;
        v31 = (spParentAsIDO.ptr_ != 0) - 1;
        if ( spParentAsIDO.ptr_ )
        {
          spParentAsIDO.ptr_ = 0;
          v30->Release(v30);
        }
        if ( v31 == -1 )
        {
LABEL_65:
          if ( m_ptr )
            ((void (__fastcall *)(CDependencyObject *))m_ptr->ReferenceTrackerWalkCore)(m_ptr);
          if ( v25 <= 925.0 )
          {
            v42 = pow(v25, 2.0) * 0.0001590400061104447;
            v41 = v42 - pow(v25, 3.0) * 0.00000006999999868639861 - (float)(v25 * 0.12506463) + 35.27311325073242;
          }
          else
          {
            v41 = 0.0;
          }
          if ( v27 <= 925.0 )
          {
            v44 = pow(v27, 2.0) * 0.0001590400061104447;
            v43 = v44 - pow(v27, 3.0) * 0.00000006999999868639861 - (float)(v27 * 0.12506463) + 35.27311325073242;
          }
          else
          {
            v43 = 0.0;
          }
          spProjection.ptr_[1].GetTypeIndex(&spProjection.ptr_[1].ctl::WeakReferenceSourceNoThreadId);
          ((void (__fastcall *)(ctl::WeakReferenceSourceNoThreadId *))spProjection.ptr_[1].QueryInterfaceImpl)(&spProjection.ptr_[1].ctl::WeakReferenceSourceNoThreadId);
          v18 = (Windows::Foundation::Point)_mm_unpacklo_ps((__m128)0LL, (__m128)0LL).m128_u64[0];
          DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
            (DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime,
            v18,
            v18,
            controlWidth,
            (Windows::UI::Xaml::IDependencyObject *)strTargetName._hstring,
            bOnlyGenerateSteadyState,
            pTimelineCollection);
          v19 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime);
          v7 = v19;
          if ( v19 >= 0 )
          {
            v20 = DOUBLE_1_0;
            v19 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                    (DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime,
                    (HSTRING__ *)strScaleXPropertyName._header.Reserved.Reserved1,
                    PointerDirection_BothAxes,
                    0.0,
                    1.0,
                    bInternalRef_8b);
            v7 = v19;
            if ( v19 >= 0 )
            {
              v19 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                      (DirectUI::ThemeGeneratorHelper *)&depressionSupplier.m_begintime,
                      (HSTRING__ *)strScaleXPropertyName._header.Reserved.Reserved1,
                      PointerDirection_BothAxes,
                      1.0,
                      0.9700000286102295,
                      bInternalRef_8c);
              v7 = v19;
              if ( v19 >= 0 )
              {
                DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
                  (DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime,
                  v18,
                  v18,
                  controlWidth,
                  (Windows::UI::Xaml::IDependencyObject *)strTargetName._hstring,
                  bOnlyGenerateSteadyState,
                  pTimelineCollection);
                v45 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
                v7 = v45;
                if ( v45 >= 0 )
                {
                  v45 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                          (DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime,
                          (HSTRING__ *)strScaleYPropertyName._header.Reserved.Reserved1,
                          PointerDirection_BothAxes,
                          0.0,
                          1.0,
                          bInternalRef_8d);
                  v7 = v45;
                  if ( v45 >= 0 )
                  {
                    v45 = DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(
                            (DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime,
                            (HSTRING__ *)strScaleYPropertyName._header.Reserved.Reserved1,
                            PointerDirection_BothAxes,
                            1.0,
                            0.9700000286102295,
                            bInternalRef_8e);
                    v7 = v45;
                    if ( v45 >= 0 )
                    {
                      v22 = v41;
                      v21 = v43;
                      DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
                      goto LABEL_83;
                    }
                  }
                }
                OnFailure_2990_(v45);
                DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
LABEL_111:
                p_m_begintime = &depressionSupplier.m_begintime;
                goto LABEL_112;
              }
            }
          }
LABEL_110:
          OnFailure_2990_(v19);
          goto LABEL_111;
        }
        spParentAsIDO.ptr_ = 0;
        spTranslateTransform.ptr_ = 0;
        v32 = ctl::ComPtr<Windows::UI::Xaml::IDependencyObject>::As<DirectUI::DependencyObject>(
                (ctl::ComPtr<IInspectable> *)&spParentAsCDO,
                (ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::DependencyObject> >)&spParentAsIDO);
        v7 = v32;
        if ( v32 < 0 )
        {
          OnFailure_2990_(v32);
        }
        else
        {
          v33 = (CAnimation *)DirectUI::DependencyObject::GetHandle((DirectUI::DependencyObject *)spParentAsIDO.ptr_);
          xref_ptr<CGrid>::operator=((xref_ptr<CAnimation> *)&spTranslateTransform, v33);
          v34 = spTranslateTransform.ptr_;
          if ( !spTranslateTransform.ptr_ )
          {
LABEL_64:
            xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&spTranslateTransform);
            ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spParentAsIDO);
            goto LABEL_65;
          }
          v35 = ((double (__fastcall *)(DirectUI::TranslateTransform *))spTranslateTransform.ptr_->__vftable[3].OnParentUpdated)(spTranslateTransform.ptr_);
          v36 = *(float *)&v35;
          v37 = ((double (__fastcall *)(DirectUI::TranslateTransform *))v34->DirectUI::Transform::DirectUI::TransformGenerated::DirectUI::GeneralTransform::DirectUI::DependencyObject::Windows::UI::Xaml::IDependencyObject::IInspectable::IUnknown::__vftable[3].OnTreeParentUpdated)(v34);
          v90 = 0.0;
          LODWORD(spTarget.ptr_) = 0;
          if ( !DirectUI::Components::ThemeAnimationsHelper::DoesLVIPNeedTransformGroupForPointerDownThemeAnimation(
                  v36,
                  *(float *)&v37,
                  &halfDifferenceX,
                  &controlHeight,
                  &v90,
                  (float *)&spTarget) )
          {
LABEL_63:
            v27 = controlHeight;
            v25 = halfDifferenceX;
            goto LABEL_64;
          }
          halfDifferenceY.ptr_ = 0;
          spTransforms.ptr_ = 0;
          v38 = ctl::make<DirectUI::TransformCollection>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::TransformCollection> >)&halfDifferenceY);
          v7 = v38;
          if ( v38 >= 0 )
          {
            v38 = ctl::make<DirectUI::TranslateTransform>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::TranslateTransform> >)&spTransforms);
            v7 = v38;
            if ( v38 >= 0 )
            {
              v38 = ctl::make<DirectUI::TransformGroup>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::TransformGroup> >)&spCoreDO);
              v7 = v38;
              if ( v38 >= 0 )
              {
                v38 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::IGeneralTransformOverrides *))spTransformGroup.ptr_->TryTransformCore)(&spTransformGroup.ptr_->Windows::UI::Xaml::Media::IGeneralTransformOverrides);
                v7 = v38;
                if ( v38 >= 0 )
                {
                  v38 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::IGeneralTransformOverrides *))spTransformGroup.ptr_->__vftable[1].QueryInterface)(&spTransformGroup.ptr_->Windows::UI::Xaml::Media::IGeneralTransformOverrides);
                  v7 = v38;
                  if ( v38 >= 0 )
                  {
                    v38 = ((__int64 (__fastcall *)(std::list<CDependencyObject *> **))spTransforms.ptr_->m_pM3Parents[3]._Mypair._Myval2._Mysize)(&spTransforms.ptr_->m_pM3Parents);
                    v7 = v38;
                    if ( v38 >= 0 )
                    {
                      v38 = ((__int64 (__fastcall *)(std::list<CDependencyObject *> **))spTransforms.ptr_->m_pM3Parents[4]._Mypair._Myval2._Mysize)(&spTransforms.ptr_->m_pM3Parents);
                      v7 = v38;
                      if ( v38 >= 0 )
                      {
                        v38 = halfDifferenceY.ptr_->Append(
                                &halfDifferenceY.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>,
                                (Windows::UI::Xaml::Input::IKeyboardAccelerator *)((__int64)&spTransforms.ptr_->m_pInheritanceContextChangedEventSource
                                                                                 & -(__int64)(spTransforms.ptr_ != 0)));
                        v7 = v38;
                        if ( v38 >= 0 )
                        {
                          v38 = halfDifferenceY.ptr_->Append(
                                  &halfDifferenceY.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>,
                                  (Windows::UI::Xaml::Input::IKeyboardAccelerator *)((__int64)&spProjection.ptr_[1]
                                                                                   & -(__int64)(spProjection.ptr_ != 0)));
                          v7 = v38;
                          if ( v38 >= 0 )
                          {
                            v38 = ((__int64 (__fastcall *)(xref_ptr<Flyweight::ValueObjectWrapper<CDOSharedState> > *, __int64))spCoreDO.m_ptr[2].m_sharedState.m_ptr[1].m_value.m_renderChangedHandler)(
                                    &spCoreDO.m_ptr[2].m_sharedState,
                                    (__int64)&halfDifferenceY.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>
                                  & -(__int64)(halfDifferenceY.ptr_ != 0));
                            v7 = v38;
                            if ( v38 >= 0 )
                            {
                              Windows::Internal::StringReference::StringReference(
                                (Windows::Internal::StringReference *)&parameters[0].m_ephemeralStorage,
                                (const wchar_t (*)[81])L"(UIElement.RenderTransform).(TransformGroup.Children)[1].(ScaleTransform.ScaleX)");
                              Windows::Internal::StringReference::operator=(
                                (Windows::Internal::StringReference *)&strScaleXPropertyName._header,
                                v39);
                              Windows::Internal::StringReference::StringReference(
                                (Windows::Internal::StringReference *)&parameters[0].m_ephemeralStorage,
                                (const wchar_t (*)[81])L"(UIElement.RenderTransform).(TransformGroup.Children)[1].(ScaleTransform.ScaleY)");
                              Windows::Internal::StringReference::operator=(
                                (Windows::Internal::StringReference *)&strScaleYPropertyName._header,
                                v40);
                              ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransforms);
                              ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease(&halfDifferenceY);
                              goto LABEL_63;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          OnFailure_2990_(v38);
          ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransforms);
          ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease(&halfDifferenceY);
        }
        xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&spTranslateTransform);
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spParentAsIDO);
      }
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spParentAsCDO);
      goto LABEL_22;
    }
    spParentAsIDO.ptr_ = (Windows::UI::Xaml::IDependencyObject *)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    v11 = xstring_ptr::CloneRuntimeStringHandle(controlWidth, (xstring_ptr *)&spParentAsIDO);
    v7 = v11;
    if ( v11 < 0 )
    {
      OnFailure_2990_(v11);
    }
    else
    {
      v12 = (CTimeline *)DirectUI::DependencyObject::GetHandle(this);
      v13 = (xref_ptr<CTransformCollection> *)Timeline_ResolveName(
                                                (xref_ptr<CDependencyObject> *)&spTranslateTransform,
                                                v12,
                                                (const xstring_ptr *)&spParentAsIDO);
      xref_ptr<CStyle>::operator=((xref_ptr<CTransformCollection> *)&spParentAsDO, v13);
      xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&spTranslateTransform);
      v8 = spParentAsDO.ptr_;
      if ( spParentAsDO.ptr_ )
      {
        Current = DirectUI::DXamlCore::GetCurrent();
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spCompositeTransform);
        PeerPrivate = DirectUI::DXamlCore::GetPeerPrivate(
                        Current,
                        0,
                        (CDependencyObject *)v8,
                        CreateIfNecessary,
                        0,
                        0,
                        &spCompositeTransform.ptr_);
        v7 = PeerPrivate;
        if ( PeerPrivate >= 0 )
        {
          xstring_ptr::~xstring_ptr((xstring_ptr *)&spParentAsIDO);
          goto LABEL_31;
        }
        OnFailure_2990_(PeerPrivate);
      }
      else
      {
        LODWORD(spTarget.ptr_) = 0;
        BufferAndCount = xencoded_string_ptr::GetBufferAndCount(
                           (xencoded_string_ptr *)&spParentAsIDO,
                           (unsigned int *)&spTarget);
        if ( BufferAndCount && LODWORD(spTarget.ptr_) && *BufferAndCount )
        {
          `vector constructor iterator'(
            (void *)&parameters[0].m_ephemeralStorage,
            0x14u,
            1u,
            (void *(__fastcall *)(void *))xstring_ptr::xstring_ptr);
          xephemeral_string_ptr::Decode(
            (const xencoded_string_ptr *)&spParentAsIDO,
            (xephemeral_string_ptr *)&parameters[0].m_ephemeralStorage);
          v56 = DirectUI::DependencyObject::GetHandle(this);
          v7 = -2146496512;
          CDependencyObject::SetAndOriginateError(
            v56,
            -2146496512,
            RuntimeError,
            0x8A5u,
            1u,
            (const xephemeral_string_ptr *)&parameters[0].m_ephemeralStorage);
          OnFailure_966_(v57);
          `vector destructor iterator'(
            (void *)&parameters[0].m_ephemeralStorage,
            0x14u,
            1u,
            (void (__fastcall *)(void *))xephemeral_string_ptr::~xephemeral_string_ptr);
        }
        else
        {
          v58 = DirectUI::DependencyObject::GetHandle(this);
          v7 = -2146496512;
          CDependencyObject::SetAndOriginateError(v58, -2146496512, RuntimeError, 0x8A4u, 0, 0);
          OnFailure_966_(v59);
        }
      }
    }
    xstring_ptr::~xstring_ptr((xstring_ptr *)&spParentAsIDO);
    goto LABEL_22;
  }
LABEL_125:
  OnFailure_2990_(StoryboardTargetName);
$Cleanup_3324:
  hstring = strTargetName._hstring;
  if ( strTargetName._hstring )
  {
    strTargetName._hstring = 0;
    (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)hstring + 16LL))(hstring);
  }
  if ( controlWidth )
    WindowsDeleteString(controlWidth);
  return v7;
}

```

## disassembly

```asm
0x180493040  mov     rax, rsp
0x180493043  mov     [rax+20h], rbx
0x180493047  push    rbp
0x180493048  push    rsi
0x180493049  push    rdi
0x18049304a  push    r12
0x18049304c  push    r13
0x18049304e  push    r14
0x180493050  push    r15
0x180493052  lea     rbp, [rax-538h]
0x180493059  sub     rsp, 600h
0x180493060  movaps  xmmword ptr [rax-48h], xmm6
0x180493064  movaps  xmmword ptr [rax-58h], xmm7
0x180493068  movaps  xmmword ptr [rax-68h], xmm8
0x18049306d  movaps  xmmword ptr [rax-78h], xmm9
0x180493072  movaps  xmmword ptr [rax-88h], xmm10
0x18049307a  movaps  xmmword ptr [rax-98h], xmm11
0x180493082  movaps  xmmword ptr [rax-0A8h], xmm12
0x18049308a  mov     rax, cs:__security_cookie
0x180493091  xor     rax, rsp
0x180493094  mov     [rbp+530h+var_B0], rax
0x18049309b  mov     r14, this
0x18049309e  xor     r13d, r13d
0x1804930a1  lea     this, [rbp+530h+strTargetName]; this
0x1804930a5  mov     [rbp+530h+controlWidth], r13
0x1804930a9  mov     [rbp+530h+strTargetName._hstring], r13
0x1804930ad  mov     r12, pTimelineCollection
0x1804930b0  mov     r15b, bOnlyGenerateSteadyState
0x1804930b3  xorps   xmm7, xmm7
0x1804930b6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1804930bb  mov     rax, [r14+0C8h]
0x1804930c2  lea     this, [rax-8]
0x1804930c6  neg     rax
0x1804930c9  sbb     rdx, rdx
0x1804930cc  and     rdx, this; pIn
0x1804930cf  lea     this, [rbp+530h+strTargetName]; pOut
0x1804930d3  call    ??$do_query_interface@UIDependencyObject@Xaml@UI@Windows@@VDependencyObject@DirectUI@@@ctl@@YAJAEAPEAUIDependencyObject@Xaml@UI@Windows@@PEAVDependencyObject@DirectUI@@@Z; ctl::do_query_interface<Windows::UI::Xaml::IDependencyObject,DirectUI::DependencyObject>(Windows::UI::Xaml::IDependencyObject * &,DirectUI::DependencyObject *)
0x1804930d8  cmp     [rbp+530h+strTargetName._hstring], r13
0x1804930dc  jnz     short loc_18049312B
0x1804930de  lea     this, [r14+0C0h]
0x1804930e5  mov     rax, [this]
0x1804930e8  lea     rdx, [rbp+530h+controlWidth]
0x1804930ec  mov     rax, [rax+30h]
0x1804930f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804930f5  mov     ebx, eax
0x1804930f7  test    eax, eax
0x1804930f9  js      short loc_18049311F
0x1804930fb  cmp     [rbp+530h+controlWidth], r13
0x1804930ff  jnz     short loc_18049312B
0x180493101  lea     rdx, [rbp+530h+controlWidth]; pStoryboardTargetName
0x180493105  mov     this, r14; pThemeAnimation
0x180493108  call    ?ThemeAnimation_GetStoryboardTargetName@@YAJPEAVTimeline@DirectUI@@PEAPEAUHSTRING__@@@Z; ThemeAnimation_GetStoryboardTargetName(DirectUI::Timeline *,HSTRING__ * *)
0x18049310d  mov     ebx, eax
0x18049310f  test    eax, eax
0x180493111  jns     short loc_18049312B
0x180493113  mov     ecx, eax; failedFrameHR
0x180493115  call    OnFailure_2990_
0x18049311a  jmp     $Cleanup_3324
0x18049311f  mov     ecx, eax; failedFrameHR
0x180493121  call    OnFailure_2990_
0x180493126  jmp     $Cleanup_3324
0x18049312b  call    ?IsTiltAnimationEnabled@TiltHelper@@YA_NXZ; TiltHelper::IsTiltAnimationEnabled(void)
0x180493130  test    al, al
0x180493132  jz      loc_18049401C
0x180493138  mov     esi, 32h ; '2'
0x18049313d  lea     r9, [rbp+530h+strRotateXPropertyName._header]; string
0x180493144  mov     edx, esi; length
0x180493146  lea     pTimelineCollection, [rbp+530h+strRotateXPropertyName._header.Reserved+8]; hstringHeader
0x18049314d  lea     this, aUielementProje_3; "(UIElement.Projection).(PlaneProjection"...
0x180493154  call    cs:__imp_WindowsCreateStringReference
0x18049315a  lea     edi, [rsi-31h]
0x18049315d  mov     ebx, 0C000000Dh
0x180493162  test    eax, eax
0x180493164  jns     short loc_180493176
0x180493166  xor     r9d, r9d; lpArguments
0x180493169  xor     r8d, r8d; nNumberOfArguments
0x18049316c  mov     edx, edi; dwExceptionFlags
0x18049316e  mov     ecx, ebx; dwExceptionCode
0x180493170  call    cs:__imp_RaiseException
0x180493176  lea     r9, [rbp+530h+strRotateYPropertyName._header]; string
0x18049317d  mov     edx, esi; length
0x18049317f  lea     pTimelineCollection, [rbp+530h+strRotateYPropertyName._header.Reserved+8]; hstringHeader
0x180493186  lea     this, aUielementProje_4; "(UIElement.Projection).(PlaneProjection"...
0x18049318d  call    cs:__imp_WindowsCreateStringReference
0x180493193  test    eax, eax
0x180493195  jns     short loc_1804931A7
0x180493197  xor     r9d, r9d; lpArguments
0x18049319a  xor     r8d, r8d; nNumberOfArguments
0x18049319d  mov     edx, edi; dwExceptionFlags
0x18049319f  mov     ecx, ebx; dwExceptionCode
0x1804931a1  call    cs:__imp_RaiseException
0x1804931a7  lea     r9, [rbp+530h+strGlobalOffsetZPropertyName._header]; string
0x1804931ae  mov     edx, 36h ; '6'; length
0x1804931b3  lea     pTimelineCollection, [rbp+530h+strGlobalOffsetZPropertyName._header.Reserved+8]; hstringHeader
0x1804931ba  lea     this, aUielementProje_0; "(UIElement.Projection).(PlaneProjection"...
0x1804931c1  call    cs:__imp_WindowsCreateStringReference
0x1804931c7  test    eax, eax
0x1804931c9  jns     short loc_1804931DB
0x1804931cb  xor     r9d, r9d; lpArguments
0x1804931ce  xor     r8d, r8d; nNumberOfArguments
0x1804931d1  mov     edx, edi; dwExceptionFlags
0x1804931d3  mov     ecx, ebx; dwExceptionCode
0x1804931d5  call    cs:__imp_RaiseException
0x1804931db  mov     esi, 33h ; '3'
0x1804931e0  lea     r9, [rbp+530h+strScaleXPropertyName._header]; string
0x1804931e7  mov     edx, esi; length
0x1804931e9  lea     pTimelineCollection, [rbp+530h+strScaleXPropertyName._header.Reserved+8]; hstringHeader
0x1804931f0  lea     this, aUielementRende_2; "(UIElement.RenderTransform).(ScaleTrans"...
0x1804931f7  call    cs:__imp_WindowsCreateStringReference
0x1804931fd  test    eax, eax
0x1804931ff  jns     short loc_180493211
0x180493201  xor     r9d, r9d; lpArguments
0x180493204  xor     r8d, r8d; nNumberOfArguments
0x180493207  mov     edx, edi; dwExceptionFlags
0x180493209  mov     ecx, ebx; dwExceptionCode
0x18049320b  call    cs:__imp_RaiseException
0x180493211  lea     r9, [rbp+530h+strScaleYPropertyName._header]; string
0x180493218  mov     edx, esi; length
0x18049321a  lea     pTimelineCollection, [rbp+530h+strScaleYPropertyName._header.Reserved+8]; hstringHeader
0x180493221  lea     this, aUielementRende_0; "(UIElement.RenderTransform).(ScaleTrans"...
0x180493228  call    cs:__imp_WindowsCreateStringReference
0x18049322e  test    eax, eax
0x180493230  jns     short loc_180493242
0x180493232  xor     r9d, r9d; lpArguments
0x180493235  xor     r8d, r8d; nNumberOfArguments
0x180493238  mov     edx, edi; dwExceptionFlags
0x18049323a  mov     ecx, ebx; dwExceptionCode
0x18049323c  call    cs:__imp_RaiseException
0x180493242  mov     rsi, r13
0x180493245  mov     [rsp+630h+spParentAsDO.ptr_], r13
0x18049324a  mov     [rsp+630h+spCompositeTransform.ptr_], r13
0x18049324f  mov     [rsp+630h+spTransformGroup.ptr_], r13
0x180493254  mov     [rsp+630h+spProjection.ptr_], r13
0x180493259  mov     [rsp+630h+spCoreDO.m_ptr], r13
0x18049325e  cmp     [rbp+530h+strTargetName._hstring], r13
0x180493262  jz      loc_1804932FE
0x180493268  lea     this, [rsp+630h+spCompositeTransform]; this
0x18049326d  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x180493272  mov     this, [rbp+530h+strTargetName._hstring]
0x180493276  test    this, this
0x180493279  jz      short loc_1804932D6
0x18049327b  mov     rax, [this]
0x18049327e  lea     pTimelineCollection, [rsp+630h+spCompositeTransform]
0x180493283  lea     rdx, _GUID_659a8956_ef29_4f50_8724_7e3207d23076
0x18049328a  mov     rax, [rax]
0x18049328d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180493292  mov     ebx, eax
0x180493294  test    eax, eax
0x180493296  jns     short loc_1804932D6
0x180493298  mov     ecx, eax; failedFrameHR
0x18049329a  call    OnFailure_2990_
0x18049329f  lea     this, [rsp+630h+spCoreDO]; this
0x1804932a4  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x1804932a9  lea     this, [rsp+630h+spProjection]; this
0x1804932ae  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x1804932b3  lea     this, [rsp+630h+spTransformGroup]; this
0x1804932b8  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x1804932bd  lea     this, [rsp+630h+spCompositeTransform]; this
0x1804932c2  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x1804932c7  lea     this, [rsp+630h+spParentAsDO]; this
0x1804932cc  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x1804932d1  jmp     $Cleanup_3324
0x1804932d6  mov     this, [rsp+630h+spCompositeTransform.ptr_]; this
0x1804932db  call    ?GetHandle@DependencyObject@DirectUI@@QEBAPEAVCDependencyObject@@XZ; DirectUI::DependencyObject::GetHandle(void)
0x1804932e0  test    rax, rax
0x1804932e3  jz      loc_1804933B3
0x1804932e9  mov     this, rax; this
0x1804932ec  mov     [rsp+630h+spParentAsDO.ptr_], rax
0x1804932f1  mov     rsi, rax
0x1804932f4  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x1804932f9  jmp     loc_1804933B3
0x1804932fe  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x180493305  lea     rdx, [rsp+630h+spParentAsIDO]; pstrCloned
0x18049330a  mov     this, [rbp+530h+controlWidth]; handle
0x18049330e  mov     [rsp+630h+spParentAsIDO.ptr_], rax
0x180493313  call    ?CloneRuntimeStringHandle@xstring_ptr@@SAJPEAUHSTRING__@@PEAV1@@Z; xstring_ptr::CloneRuntimeStringHandle(HSTRING__ *,xstring_ptr *)
0x180493318  mov     ebx, eax
0x18049331a  test    eax, eax
0x18049331c  js      loc_180494006
0x180493322  mov     this, r14; this
0x180493325  call    ?GetHandle@DependencyObject@DirectUI@@QEBAPEAVCDependencyObject@@XZ; DirectUI::DependencyObject::GetHandle(void)
0x18049332a  mov     rdx, rax; timeline
0x18049332d  lea     pTimelineCollection, [rsp+630h+spParentAsIDO]; strName
0x180493332  lea     this, [rsp+630h+spTranslateTransform]; result
0x180493337  call    ?Timeline_ResolveName@@YA?AV?$xref_ptr@VCDependencyObject@@@@PEAVCTimeline@@AEBVxstring_ptr@@@Z; Timeline_ResolveName(CTimeline *,xstring_ptr const &)
0x18049333c  mov     rdx, rax; rhs
0x18049333f  lea     this, [rsp+630h+spParentAsDO]; this
0x180493344  call    ??4?$xref_ptr@VCStyle@@@@QEAAAEAV0@$$QEAV0@@Z; xref_ptr<CStyle>::operator=(xref_ptr<CStyle> &&)
0x180493349  lea     this, [rsp+630h+spTranslateTransform]; this
0x18049334e  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x180493353  mov     rsi, [rsp+630h+spParentAsDO.ptr_]
0x180493358  test    rsi, rsi
0x18049335b  jz      loc_180493F22
0x180493361  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180493366  lea     this, [rsp+630h+spCompositeTransform]; this
0x18049336b  mov     rbx, rax
0x18049336e  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x180493373  lea     rax, [rsp+630h+spCompositeTransform]
0x180493378  mov     r9d, edi; createMode
0x18049337b  mov     [rsp+630h+ppObject], rax; ppObject
0x180493380  mov     pTimelineCollection, rsi; pDO
0x180493383  mov     qword ptr [rsp+630h+bInternalRef+8], r13; pIsPendingDelete
0x180493388  xor     edx, edx; pOuter
0x18049338a  mov     this, rbx; this
0x18049338d  mov     [rsp+630h+bInternalRef], r13d; pReference
0x180493392  call    ?GetPeerPrivate@DXamlCore@DirectUI@@AEAAJPEAUIInspectable@@PEAVCDependencyObject@@W4GetPeerPrivateCreateMode@12@IPEAIPEAPEAVDependencyObject@2@@Z; DirectUI::DXamlCore::GetPeerPrivate(IInspectable *,CDependencyObject *,DirectUI::DXamlCore::GetPeerPrivateCreateMode,uint,uint *,DirectUI::DependencyObject * *)
0x180493397  mov     ebx, eax
0x180493399  test    eax, eax
0x18049339b  jns     short loc_1804933A9
0x18049339d  mov     ecx, eax; failedFrameHR
0x18049339f  call    OnFailure_2990_
0x1804933a4  jmp     loc_18049400D
0x1804933a9  lea     this, [rsp+630h+spParentAsIDO]; this
0x1804933ae  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1804933b3  mov     r14, [rsp+630h+spCompositeTransform.ptr_]
0x1804933b8  lea     this, [rsp+630h+spTransformGroup]; ppNewInstance
0x1804933bd  call    ??$make@VPlaneProjection@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VPlaneProjection@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::PlaneProjection>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::PlaneProjection>>)
0x1804933c2  mov     ebx, eax
0x1804933c4  test    eax, eax
0x1804933c6  js      loc_180493F16
0x1804933cc  lea     this, [rsp+630h+spProjection]; ppNewInstance
0x1804933d1  call    ??$make@VCompositeTransform@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VCompositeTransform@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::CompositeTransform>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::CompositeTransform>>)
0x1804933d6  mov     ebx, eax
0x1804933d8  test    eax, eax
0x1804933da  js      loc_180493F0A
0x1804933e0  cmp     cs:?m_quirkCacheSuppressions@CQuirksMode2@@0JA, r13d; long CQuirksMode2::m_quirkCacheSuppressions
0x1804933e7  jnz     short loc_180493419
0x1804933e9  xor     r9d, r9d; Context
0x1804933ec  lea     pTimelineCollection, qword_180F72750; Parameter
0x1804933f3  lea     rdx, ?InitOnceCallback@CQuirksMode2@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1804933fa  lea     this, InitOnce; InitOnce
0x180493401  call    cs:__imp_InitOnceExecuteOnce
0x180493407  mov     rax, cs:qword_180F72750
0x18049340e  movzx   ecx, byte ptr [rax+1]
0x180493412  shr     ecx, 3
0x180493415  and     ecx, edi
0x180493417  jmp     short loc_180493425
0x180493419  mov     ecx, 20040h; quirk
0x18049341e  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
0x180493423  test    al, al
0x180493425  jz      loc_1804934FA
0x18049342b  mov     rax, [rbp+530h+strTargetName._hstring]
0x18049342f  lea     this, [rbp+530h+depressionSupplier.m_begintime]; this
0x180493433  mov     r9, [rbp+530h+controlWidth]; targetName
0x180493437  unpcklps xmm7, xmm7
0x18049343a  mov     [rsp+630h+ppObject], r12; timelineCollection
0x18049343f  movq    pTimelineCollection, xmm7; destinationOffset
0x180493444  movq    rdx, xmm7; startOffset
0x180493449  mov     byte ptr [rsp+630h+bInternalRef+8], r15b; targetPropertyName
0x18049344e  mov     qword ptr [rsp+630h+bInternalRef], rax; pTarget
0x180493453  call    ??0ThemeGeneratorHelper@DirectUI@@QEAA@UPoint@Foundation@Windows@@0PEAUHSTRING__@@PEAUIDependencyObject@Xaml@UI@4@EPEAU?$IVector@PEAVTimeline@Animation@Media@Xaml@UI@Windows@@@Collections@34@@Z; DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(Windows::Foundation::Point,Windows::Foundation::Point,HSTRING__ *,Windows::UI::Xaml::IDependencyObject *,uchar,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *)
0x180493458  lea     this, [rbp+530h+depressionSupplier.m_begintime]; this
0x18049345c  call    ?Initialize@ThemeGeneratorHelper@DirectUI@@QEAAJXZ; DirectUI::ThemeGeneratorHelper::Initialize(void)
0x180493461  mov     ebx, eax
0x180493463  test    eax, eax
0x180493465  js      loc_1804934EE
0x18049346b  mov     rdx, qword ptr [rbp+530h+strGlobalOffsetZPropertyName._header.Reserved]; targetPropertyName
0x180493472  lea     this, [rbp+530h+depressionSupplier.m_begintime]; this
0x180493476  xorps   xmm8, xmm8
0x18049347a  xorps   xmm3, xmm3; pointerValue
0x18049347d  mov     r8b, 2; sourceDirection
0x180493480  movsd   qword ptr [rsp+630h+bInternalRef], xmm8; value
0x180493487  call    ?RegisterPointerKeyFrame@ThemeGeneratorHelper@DirectUI@@QEAAJPEAUHSTRING__@@W4PointerDirection@2@NN_J@Z; DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(HSTRING__ *,DirectUI::PointerDirection,double,double,__int64)
0x18049348c  mov     ebx, eax
0x18049348e  test    eax, eax
0x180493490  js      short loc_1804934E2
0x180493492  movsd   xmm0, cs:__real@c039000000000000
0x18049349a  lea     this, [rbp+530h+depressionSupplier.m_begintime]; this
0x18049349e  movsd   xmm6, cs:__real@3ff0000000000000
0x1804934a6  mov     r8b, 2; sourceDirection
0x1804934a9  mov     rdx, qword ptr [rbp+530h+strGlobalOffsetZPropertyName._header.Reserved]; targetPropertyName
0x1804934b0  movaps  xmm3, xmm6; pointerValue
0x1804934b3  movsd   qword ptr [rsp+630h+bInternalRef], xmm0; value
0x1804934b9  call    ?RegisterPointerKeyFrame@ThemeGeneratorHelper@DirectUI@@QEAAJPEAUHSTRING__@@W4PointerDirection@2@NN_J@Z; DirectUI::ThemeGeneratorHelper::RegisterPointerKeyFrame(HSTRING__ *,DirectUI::PointerDirection,double,double,__int64)
0x1804934be  mov     ebx, eax
0x1804934c0  test    eax, eax
0x1804934c2  js      short loc_1804934D6
0x1804934c4  movss   xmm10, cs:__real@41898287
0x1804934cd  movaps  xmm9, xmm10
0x1804934d1  jmp     loc_180493B9F
0x1804934d6  mov     ecx, eax; failedFrameHR
0x1804934d8  call    OnFailure_2990_
0x1804934dd  jmp     loc_180493EE6
0x1804934e2  mov     ecx, eax; failedFrameHR
0x1804934e4  call    OnFailure_2990_
0x1804934e9  jmp     loc_180493EE6
0x1804934ee  mov     ecx, eax; failedFrameHR
0x1804934f0  call    OnFailure_2990_
0x1804934f5  jmp     loc_180493EE6
0x1804934fa  mov     rax, [rsi]
0x1804934fd  mov     this, rsi
0x180493500  mov     rax, [rax+2E8h]
0x180493507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18049350c  mov     rax, [rsi]
0x18049350f  mov     this, rsi
0x180493512  movss   [rbp+530h+halfDifferenceX], xmm0
0x180493517  movaps  xmm11, xmm0
0x18049351b  mov     rax, [rax+2F0h]
0x180493522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180493527  lea     this, [rsp+630h+spParentAsCDO]; this
  ... truncated ...
```
