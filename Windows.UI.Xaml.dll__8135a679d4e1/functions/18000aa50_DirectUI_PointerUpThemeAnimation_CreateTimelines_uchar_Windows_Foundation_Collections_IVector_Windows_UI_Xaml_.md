# DirectUI::PointerUpThemeAnimation::CreateTimelines(uchar,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *)

- ea: `0x18000aa50`
- end: `0x18000b629`
- name: `?CreateTimelines@PointerUpThemeAnimation@DirectUI@@UEAAJEPEAU?$IVector@PEAVTimeline@Animation@Media@Xaml@UI@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `3033`
- prototype: `HRESULT __fastcall(DirectUI::PointerUpThemeAnimation *this, unsigned __int8 bOnlyGenerateSteadyState, Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *pTimelineCollection)`
- caller_count: `0`
- callee_count: `34`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x180009af8`
- `0x18000aa50`
- `0x18000b630`
- `0x18000b660`
- `0x18000b724`
- `0x18001f3c0`
- `0x180027c80`
- `0x180029570`
- `0x18005f28c`
- `0x18005f6dc`
- `0x18005fb04`
- `0x1800607b8`
- `0x18006cfd0`
- `0x18007d590`
- `0x1800d5330`
- `0x1800f3fb4`
- `0x1800fe130`
- `0x180131190`
- `0x18018fa54`
- `0x1801df610`
- `0x1801e4a14`
- `0x180363614`
- `0x180421044`
- `0x180430ae4`
- `0x1804828c4`
- `0x180494e04`
- `0x18076e110`
- `0x18078c070`
- `0x1808fe580`
- `0x1808fe894`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b349`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b35e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b373`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b388`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b39d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b349`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b35e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b373`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b388`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b39d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000af32`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000af32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ae08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ae08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ab3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ab67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ab8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000abb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000abde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ab3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ab67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ab8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000abb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000abde`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall DirectUI::PointerUpThemeAnimation::CreateTimelines(
        DirectUI::PointerUpThemeAnimation *this,
        unsigned __int8 bOnlyGenerateSteadyState,
        Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *pTimelineCollection)
{
  Windows::Foundation::IEventHandler<IInspectable *> *v4; // r14
  HRESULT StoryboardTargetName; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  CDependencyObject *Handle; // rax
  CDependencyObject *v11; // rbx
  char *m_control_block; // r8
  CCoreServices *m_coreServices; // rsi
  Jupiter::NameScoping::NameScopeType v14; // ebx
  CPopup *StandardNameScopeOwnerInternal; // rax
  CDependencyObject *NamedObject; // rax
  HSTRING__ *v17; // rsi
  DirectUI::DXamlCore *Current; // rbx
  HRESULT PeerPrivate; // eax
  Windows::UI::Xaml::Media::ITransform *ptr; // rsi
  HRESULT (__fastcall *GetIids)(IInspectable *, unsigned int *, _GUID **); // rbx
  HRESULT v22; // eax
  unsigned int (__fastcall *AddRef)(IUnknown *); // rbx
  Windows::UI::Xaml::Media::IProjection *v24; // rcx
  Windows::Foundation::IEventHandler<IInspectable *> *v25; // rcx
  Windows::UI::Xaml::Media::ITransform *v26; // rcx
  CDependencyObject *m_ptr; // rcx
  __m128d v29; // xmm6
  __m128d v30; // xmm6
  HSTRING__ *hstring; // rcx
  int v32; // ebx
  bool v33; // zf
  Windows::Foundation::Point v34; // xmm6_8
  HRESULT v35; // eax
  __int64 v36; // r12
  __int64 v37; // rsi
  HRESULT v38; // eax
  HRESULT v39; // eax
  HRESULT v40; // eax
  HRESULT v41; // eax
  HRESULT v42; // eax
  EventRegistrationToken *p_m_completedToken; // rsi
  char *FailFast; // rax
  HRESULT v45; // eax
  const wchar_t *BufferAndCount; // rax
  CDependencyObject *v47; // rax
  HRESULT v48; // ecx
  const Windows::Internal::StringReference *v49; // rax
  const Windows::Internal::StringReference *v50; // rax
  HRESULT v51; // eax
  int v52; // ecx
  __int128 v53; // xmm0
  __int64 *p_m_begintime; // rcx
  CDependencyObject *v55; // rax
  HRESULT v56; // ecx
  ctl::ComPtr<Windows::UI::Xaml::Media::ITransform> spTransform; // [rsp+48h] [rbp-C0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Media::IProjection> spProjection; // [rsp+50h] [rbp-B8h] BYREF
  ctl::ComPtr<Windows::Foundation::IEventHandler<IInspectable *> > spTimelineCompletedHandler; // [rsp+58h] [rbp-B0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spTarget; // [rsp+60h] [rbp-A8h] BYREF
  xref_ptr<CDependencyObject> spCoreDO; // [rsp+68h] [rbp-A0h] BYREF
  Windows::Internal::String strTargetName; // [rsp+70h] [rbp-98h] BYREF
  HSTRING__ *pStoryboardTargetName; // [rsp+78h] [rbp-90h] BYREF
  _BYTE parameters[24]; // [rsp+80h] [rbp-88h] OVERLAPPED BYREF
  _BYTE easing_8[33]; // [rsp+A8h] [rbp-60h] OVERLAPPED BYREF
  DirectUI::ThemeGeneratorHelper tiltXSupplier; // [rsp+1C0h] [rbp+B8h] BYREF
  DirectUI::ThemeGeneratorHelper tiltYSupplier; // [rsp+2C0h] [rbp+1B8h] BYREF
  DirectUI::ThemeGeneratorHelper scaleYSupplier; // [rsp+3C0h] [rbp+2B8h] BYREF
  Windows::Internal::StringReference strScaleXPropertyName; // [rsp+4C0h] [rbp+3B8h] BYREF
  Windows::Internal::StringReference strScaleYPropertyName; // [rsp+4E0h] [rbp+3D8h] BYREF
  Windows::Internal::StringReference strGlobalOffsetZPropertyName; // [rsp+500h] [rbp+3F8h] BYREF
  Windows::Internal::StringReference strRotateYPropertyName; // [rsp+520h] [rbp+418h] BYREF
  Windows::Internal::StringReference strRotateXPropertyName; // [rsp+540h] [rbp+438h] BYREF
  Windows::Internal::StringReference v74; // [rsp+568h] [rbp+460h] BYREF

  *(_QWORD *)&parameters[8] = pTimelineCollection;
  v4 = 0;
  pStoryboardTargetName = 0;
  spCoreDO.m_ptr = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCoreDO);
  ctl::do_query_interface<Windows::UI::Xaml::IDependencyObject,DirectUI::DependencyObject>(
    (Windows::UI::Xaml::IDependencyObject **)&spCoreDO,
    (DirectUI::DependencyObject *)((unsigned __int128)&this->m_tpAnimationTarget.m_trackerReference.m_value[-1]
                                 & ((unsigned __int128)-(__int128)(unsigned __int64)this->m_tpAnimationTarget.m_trackerReference.m_value >> 64)));
  if ( !spCoreDO.m_ptr )
  {
    StoryboardTargetName = this->get_TargetName(
                             &this->Windows::UI::Xaml::Media::Animation::IPointerUpThemeAnimation,
                             &pStoryboardTargetName);
    v8 = StoryboardTargetName;
    if ( StoryboardTargetName < 0
      || !pStoryboardTargetName
      && (StoryboardTargetName = ThemeAnimation_GetStoryboardTargetName(this, &pStoryboardTargetName),
          v8 = StoryboardTargetName,
          StoryboardTargetName < 0) )
    {
LABEL_42:
      OnFailure_2990_(StoryboardTargetName);
      goto $Cleanup_18;
    }
  }
  if ( !TiltHelper::IsTiltAnimationEnabled() )
  {
    v29 = (__m128d)_mm_unpacklo_ps((__m128)0LL, (__m128)0LL);
    v30 = _mm_unpacklo_pd(v29, v29);
    StoryboardTargetName = DirectUI::ThemeGenerator::AddTimelinesForThemeAnimation(
                             21,
                             1,
                             pStoryboardTargetName,
                             (Windows::UI::Xaml::IDependencyObject *)spCoreDO.m_ptr,
                             bOnlyGenerateSteadyState,
                             *(Windows::Foundation::Point *)&v30.m128d_f64[0],
                             *(Windows::Foundation::Point *)&v30.m128d_f64[1],
                             pTimelineCollection);
    v8 = StoryboardTargetName;
    if ( StoryboardTargetName >= 0 )
      goto $Cleanup_18;
    goto LABEL_42;
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
  *(__m128i *)easing_8 = _mm_load_si128((const __m128i *)&_xmm);
  spTransform.ptr_ = 0;
  *(__m128i *)&easing_8[16] = _mm_load_si128((const __m128i *)&_xmm);
  spTimelineCompletedHandler.ptr_ = 0;
  spProjection.ptr_ = 0;
  if ( !spCoreDO.m_ptr )
  {
    spTarget.ptr_ = (Windows::UI::Xaml::IDependencyObject *)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    v9 = xstring_ptr::CloneRuntimeStringHandle(pStoryboardTargetName, (xstring_ptr *)&spTarget);
    v8 = v9;
    if ( v9 < 0 )
    {
      OnFailure_2990_(v9);
    }
    else
    {
      Handle = DirectUI::DependencyObject::GetHandle(this);
      strTargetName._hstring = 0;
      v11 = Handle;
      xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&strTargetName);
      m_control_block = (char *)v11;
      if ( v11[2].m_ref_count.m_ptr_as_int )
        m_control_block = (char *)v11[2].m_ref_count.m_control_block;
      m_coreServices = v11->m_sharedState.m_ptr->m_value.m_coreServices;
      v14 = (*((_DWORD *)m_control_block + 20) & 0x20) == 0;
      if ( (*((_DWORD *)m_control_block + 20) & 0x20) != 0 )
        StandardNameScopeOwnerInternal = xref::weakref_ptr<CScrollViewer>::lock_noref((xref::weakref_ptr<CPopup> *)(m_control_block + 264));
      else
        StandardNameScopeOwnerInternal = (CPopup *)CDependencyObject::GetStandardNameScopeOwnerInternal(
                                                     (CDependencyObject *)m_control_block,
                                                     0);
      NamedObject = CCoreServices::GetNamedObject(
                      m_coreServices,
                      (const xstring_ptr_view *)&spTarget,
                      StandardNameScopeOwnerInternal,
                      v14);
      v17 = (HSTRING__ *)NamedObject;
      if ( !NamedObject )
      {
        strTargetName._hstring = 0;
        *(_DWORD *)parameters = 0;
        BufferAndCount = xencoded_string_ptr::GetBufferAndCount(
                           (xencoded_string_ptr *)&spTarget,
                           (unsigned int *)parameters);
        if ( BufferAndCount && *(_DWORD *)parameters && *BufferAndCount )
        {
          `vector constructor iterator'(
            &parameters[8],
            0x14u,
            1u,
            (void *(__fastcall *)(void *))xstring_ptr::xstring_ptr);
          xephemeral_string_ptr::Decode((const xencoded_string_ptr *)&spTarget, (xephemeral_string_ptr *)&parameters[8]);
          v55 = DirectUI::DependencyObject::GetHandle(this);
          v8 = -2146496512;
          CDependencyObject::SetAndOriginateError(
            v55,
            -2146496512,
            RuntimeError,
            0x8A5u,
            1u,
            (const xephemeral_string_ptr *)&parameters[8]);
          OnFailure_966_(v56);
          `vector destructor iterator'(
            &parameters[8],
            0x14u,
            1u,
            (void (__fastcall *)(void *))xephemeral_string_ptr::~xephemeral_string_ptr);
        }
        else
        {
          v47 = DirectUI::DependencyObject::GetHandle(this);
          v8 = -2146496512;
          CDependencyObject::SetAndOriginateError(v47, -2146496512, RuntimeError, 0x8A4u, 0, 0);
          OnFailure_966_(v48);
        }
        xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&strTargetName);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&spTarget);
        goto LABEL_81;
      }
      CDependencyObject::AddRef(NamedObject);
      strTargetName._hstring = v17;
      Current = DirectUI::DXamlCore::GetCurrent();
      ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransform);
      PeerPrivate = DirectUI::DXamlCore::GetPeerPrivate(
                      Current,
                      0,
                      (CDependencyObject *)v17,
                      CreateIfNecessary,
                      0,
                      0,
                      (DirectUI::DependencyObject **)&spTransform);
      v8 = PeerPrivate;
      if ( PeerPrivate >= 0 )
      {
        xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&strTargetName);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&spTarget);
        goto LABEL_25;
      }
      OnFailure_2990_(PeerPrivate);
      xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&strTargetName);
    }
    xstring_ptr::~xstring_ptr((xstring_ptr *)&spTarget);
    goto LABEL_28;
  }
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransform);
  if ( spCoreDO.m_ptr )
  {
    v40 = ((__int64 (__fastcall *)(CDependencyObject *, GUID *, ctl::ComPtr<Windows::UI::Xaml::Media::ITransform> *))spCoreDO.m_ptr->ReleaseOverride)(
            spCoreDO.m_ptr,
            &GUID_659a8956_ef29_4f50_8724_7e3207d23076,
            &spTransform);
    v8 = v40;
    if ( v40 < 0 )
    {
      OnFailure_2990_(v40);
      goto LABEL_28;
    }
  }
LABEL_25:
  ptr = spTransform.ptr_;
  GetIids = spTransform.ptr_[23].__vftable[2].GetIids;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimelineCompletedHandler);
  v22 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::ITransform *, ctl::ComPtr<Windows::Foundation::IEventHandler<IInspectable *> > *))GetIids)(
          &ptr[23],
          &spTimelineCompletedHandler);
  v8 = v22;
  if ( v22 < 0
    || (AddRef = ptr[23].__vftable[2].AddRef,
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spProjection),
        v22 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::ITransform *, ctl::ComPtr<Windows::UI::Xaml::Media::IProjection> *))AddRef)(
                &ptr[23],
                &spProjection),
        v8 = v22,
        v22 < 0) )
  {
    OnFailure_2990_(v22);
    goto LABEL_81;
  }
  if ( !spTimelineCompletedHandler.ptr_ || !spProjection.ptr_ )
    goto LABEL_28;
  spTarget.ptr_ = 0;
  strTargetName._hstring = 0;
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&strTargetName);
  if ( spProjection.ptr_ )
    spProjection.ptr_->QueryInterface(
      spProjection.ptr_,
      &GUID_eaf2ce09_ecf2_48f8_8327_5ae4f5e792ce,
      (void **)&strTargetName);
  hstring = strTargetName._hstring;
  v32 = (strTargetName._hstring != 0) - 1;
  if ( strTargetName._hstring )
  {
    strTargetName._hstring = 0;
    (*(void (__fastcall **)(HSTRING__ *))(*((_QWORD *)hstring + 1) + 16LL))(hstring + 2);
  }
  if ( v32 != -1 )
  {
    Windows::Internal::StringReference::StringReference(
      &v74,
      (const wchar_t (*)[81])L"(UIElement.RenderTransform).(TransformGroup.Children)[1].(ScaleTransform.ScaleX)");
    Windows::Internal::StringReference::operator=(
      (Windows::Internal::StringReference *)&strScaleXPropertyName._header,
      v49);
    Windows::Internal::StringReference::StringReference(
      &v74,
      (const wchar_t (*)[81])L"(UIElement.RenderTransform).(TransformGroup.Children)[1].(ScaleTransform.ScaleY)");
    Windows::Internal::StringReference::operator=(
      (Windows::Internal::StringReference *)&strScaleYPropertyName._header,
      v50);
  }
  if ( CQuirksMode2::m_quirkCacheSuppressions )
  {
    v33 = !CQuirksMode2::XamlQuirkIsEnabled(0x20040u);
  }
  else
  {
    InitOnceExecuteOnce(&InitOnce, CQuirksMode2::InitOnceCallback, &qword_180F72750, 0);
    v33 = ((*(unsigned __int8 *)(qword_180F72750 + 1) >> 3) & 1) == 0;
  }
  if ( v33 )
  {
    v34 = (Windows::Foundation::Point)_mm_unpacklo_ps((__m128)0LL, (__m128)0LL).m128_u64[0];
    DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
      (DirectUI::ThemeGeneratorHelper *)&easing_8[32],
      v34,
      v34,
      pStoryboardTargetName,
      (Windows::UI::Xaml::IDependencyObject *)spCoreDO.m_ptr,
      bOnlyGenerateSteadyState,
      pTimelineCollection);
    v35 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&easing_8[32]);
    v8 = v35;
    if ( v35 < 0 )
    {
      OnFailure_2990_(v35);
      goto LABEL_57;
    }
    v36 = 200;
    v37 = 150;
    v38 = DirectUI::ThemeGeneratorHelper::RegisterKeyFrame(
            (DirectUI::ThemeGeneratorHelper *)&easing_8[32],
            (HSTRING__ *)strScaleXPropertyName._header.Reserved.Reserved1,
            1.0,
            150,
            200,
            (DirectUI::TimingFunctionDescription *)easing_8);
    v8 = v38;
    if ( v38 >= 0 )
    {
      DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
        (DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime,
        v34,
        v34,
        pStoryboardTargetName,
        (Windows::UI::Xaml::IDependencyObject *)spCoreDO.m_ptr,
        bOnlyGenerateSteadyState,
        *(Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> **)&parameters[8]);
      v39 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
      v8 = v39;
      if ( v39 < 0 )
      {
        OnFailure_2990_(v39);
        DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
LABEL_57:
        DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&easing_8[32]);
        goto LABEL_28;
      }
      v51 = DirectUI::ThemeGeneratorHelper::RegisterKeyFrame(
              (DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime,
              (HSTRING__ *)strScaleYPropertyName._header.Reserved.Reserved1,
              1.0,
              150,
              200,
              (DirectUI::TimingFunctionDescription *)easing_8);
      v8 = v51;
      if ( v51 >= 0 )
      {
        DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
        goto LABEL_64;
      }
      OnFailure_2990_(v51);
      DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&scaleYSupplier.m_begintime);
LABEL_100:
      p_m_begintime = (__int64 *)&easing_8[32];
      goto LABEL_101;
    }
LABEL_99:
    OnFailure_2990_(v38);
    goto LABEL_100;
  }
  v34 = (Windows::Foundation::Point)_mm_unpacklo_ps((__m128)0LL, (__m128)0LL).m128_u64[0];
  DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
    (DirectUI::ThemeGeneratorHelper *)&easing_8[32],
    v34,
    v34,
    pStoryboardTargetName,
    (Windows::UI::Xaml::IDependencyObject *)spCoreDO.m_ptr,
    bOnlyGenerateSteadyState,
    pTimelineCollection);
  v38 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&easing_8[32]);
  v8 = v38;
  if ( v38 < 0 )
    goto LABEL_99;
  v37 = 167;
  v38 = DirectUI::ThemeGeneratorHelper::RegisterKeyFrame(
          (DirectUI::ThemeGeneratorHelper *)&easing_8[32],
          (HSTRING__ *)strGlobalOffsetZPropertyName._header.Reserved.Reserved1,
          0.0,
          167,
          167,
          (DirectUI::TimingFunctionDescription *)easing_8);
  v8 = v38;
  if ( v38 < 0 )
    goto LABEL_99;
  v36 = 167;
LABEL_64:
  DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&easing_8[32]);
  DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
    (DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime,
    v34,
    v34,
    pStoryboardTargetName,
    (Windows::UI::Xaml::IDependencyObject *)spCoreDO.m_ptr,
    bOnlyGenerateSteadyState,
    *(Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> **)&parameters[8]);
  v41 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime);
  v8 = v41;
  if ( v41 < 0
    || (v41 = DirectUI::ThemeGeneratorHelper::RegisterKeyFrame(
                (DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime,
                (HSTRING__ *)strRotateYPropertyName._header.Reserved.Reserved1,
                0.0,
                v37,
                v36,
                (DirectUI::TimingFunctionDescription *)easing_8),
        v8 = v41,
        v41 < 0) )
  {
    OnFailure_2990_(v41);
    goto LABEL_97;
  }
  DirectUI::ThemeGeneratorHelper::ThemeGeneratorHelper(
    (DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime,
    v34,
    v34,
    pStoryboardTargetName,
    (Windows::UI::Xaml::IDependencyObject *)spCoreDO.m_ptr,
    bOnlyGenerateSteadyState,
    *(Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> **)&parameters[8]);
  v42 = DirectUI::ThemeGeneratorHelper::Initialize((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
  v8 = v42;
  if ( v42 < 0
    || (v42 = DirectUI::ThemeGeneratorHelper::RegisterKeyFrame(
                (DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime,
                (HSTRING__ *)strRotateXPropertyName._header.Reserved.Reserved1,
                0.0,
                v37,
                v36,
                (DirectUI::TimingFunctionDescription *)easing_8),
        v8 = v42,
        v42 < 0) )
  {
LABEL_95:
    OnFailure_2990_(v42);
    DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
LABEL_97:
    p_m_begintime = &tiltXSupplier.m_begintime;
LABEL_101:
    DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)p_m_begintime);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTarget);
LABEL_81:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spProjection);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimelineCompletedHandler);
    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransform);
    goto $Cleanup_18;
  }
  p_m_completedToken = &this->m_completedToken;
  if ( this->m_completedToken.value )
  {
    v42 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::Animation::ITimeline *, __int64))this->remove_Completed)(
            &this->Windows::UI::Xaml::Media::Animation::ITimeline,
            p_m_completedToken->value);
    v8 = v42;
    if ( v42 >= 0 )
    {
      p_m_completedToken->value = 0;
      goto LABEL_69;
    }
    goto LABEL_95;
  }
LABEL_69:
  FailFast = (char *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
  if ( FailFast )
  {
    v52 = *(_DWORD *)&parameters[20];
    *(_QWORD *)&parameters[8] = DirectUI::PointerUpThemeAnimation::OnTimelineCompleted;
    *(_DWORD *)&parameters[16] = 0;
    *(_QWORD *)FailFast = DirectUI::ClassMemberEventHandler<DirectUI::PointerUpThemeAnimation,Windows::UI::Xaml::Media::Animation::IPointerUpThemeAnimation,Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable>::`vftable';
    *(_DWORD *)&parameters[20] = v52;
    v4 = (Windows::Foundation::IEventHandler<IInspectable *> *)FailFast;
    v53 = *(_OWORD *)&parameters[8];
    *((_DWORD *)FailFast + 2) = 1;
    spTarget.ptr_ = (Windows::UI::Xaml::IDependencyObject *)FailFast;
    *((_QWORD *)FailFast + 2) = (unsigned __int64)this & -(__int64)(&this->ctl::WeakReferenceSourceNoThreadId != 0) | 1;
    *(_OWORD *)(FailFast + 24) = v53;
  }
  v45 = this->add_Completed(&this->Windows::UI::Xaml::Media::Animation::ITimeline, v4, &this->m_completedToken);
  v8 = v45;
  if ( v45 < 0 )
  {
    OnFailure_2990_(v45);
    DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
    DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTarget);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spProjection);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimelineCompletedHandler);
    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spTransform);
    goto $Cleanup_18;
  }
  DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltYSupplier.m_begintime);
  DirectUI::ThemeGeneratorHelper::~ThemeGeneratorHelper((DirectUI::ThemeGeneratorHelper *)&tiltXSupplier.m_begintime);
  if ( v4 )
    v4->Release(v4);
LABEL_28:
  v24 = spProjection.ptr_;
  if ( spProjection.ptr_ )
  {
    spProjection.ptr_ = 0;
    v24->Release(v24);
  }
  v25 = spTimelineCompletedHandler.ptr_;
  if ( spTimelineCompletedHandler.ptr_ )
  {
    spTimelineCompletedHandler.ptr_ = 0;
    v25->Release(v25);
  }
  if ( spTransform.ptr_ )
  {
    v26 = spTransform.ptr_ + 1;
    spTransform.ptr_ = 0;
    v26->Release(v26);
  }
$Cleanup_18:
  m_ptr = spCoreDO.m_ptr;
  if ( spCoreDO.m_ptr )
  {
    spCoreDO.m_ptr = 0;
    ((void (__fastcall *)(CDependencyObject *))m_ptr->ReferenceTrackerWalkCore)(m_ptr);
  }
  if ( pStoryboardTargetName )
    WindowsDeleteString(pStoryboardTargetName);
  return v8;
}

```

## disassembly

```asm
0x18000aa50  mov     rax, rsp
0x18000aa53  mov     [rax+20h], rbx
0x18000aa57  push    rbp
0x18000aa58  push    rsi
0x18000aa59  push    rdi
0x18000aa5a  push    r12
0x18000aa5c  push    r13
0x18000aa5e  push    r14
0x18000aa60  push    r15
0x18000aa62  lea     rbp, [rax-4D8h]
0x18000aa69  sub     rsp, 5A0h
0x18000aa70  movaps  xmmword ptr [rax-48h], xmm6
0x18000aa74  mov     rax, cs:__security_cookie
0x18000aa7b  xor     rax, rsp
0x18000aa7e  mov     [rbp+4D0h+var_50], rax
0x18000aa85  mov     r15, this
0x18000aa88  mov     qword ptr [rbp+4D0h+parameters.m_ephemeralStorage.___u0], pTimelineCollection
0x18000aa8c  xor     r14d, r14d
0x18000aa8f  lea     this, [rsp+5D0h+spCoreDO]; this
0x18000aa94  mov     [rsp+5D0h+pStoryboardTargetName], r14
0x18000aa99  mov     r12, pTimelineCollection
0x18000aa9c  mov     [rsp+5D0h+spCoreDO.m_ptr], r14
0x18000aaa1  mov     r13b, bOnlyGenerateSteadyState
0x18000aaa4  xorps   xmm6, xmm6
0x18000aaa7  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18000aaac  mov     rax, [r15+0D0h]
0x18000aab3  lea     this, [rax-8]
0x18000aab7  neg     rax
0x18000aaba  sbb     rdx, rdx
0x18000aabd  and     rdx, this; pIn
0x18000aac0  lea     this, [rsp+5D0h+spCoreDO]; pOut
0x18000aac5  call    ??$do_query_interface@UIDependencyObject@Xaml@UI@Windows@@VDependencyObject@DirectUI@@@ctl@@YAJAEAPEAUIDependencyObject@Xaml@UI@Windows@@PEAVDependencyObject@DirectUI@@@Z; ctl::do_query_interface<Windows::UI::Xaml::IDependencyObject,DirectUI::DependencyObject>(Windows::UI::Xaml::IDependencyObject * &,DirectUI::DependencyObject *)
0x18000aaca  cmp     [rsp+5D0h+spCoreDO.m_ptr], r14
0x18000aacf  jnz     short loc_18000AB11
0x18000aad1  lea     this, [r15+0C0h]
0x18000aad8  mov     rax, [this]
0x18000aadb  lea     rdx, [rsp+5D0h+pStoryboardTargetName]
0x18000aae0  mov     rax, [rax+30h]
0x18000aae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aae9  mov     ebx, eax
0x18000aaeb  test    eax, eax
0x18000aaed  js      loc_18000B318
0x18000aaf3  cmp     [rsp+5D0h+pStoryboardTargetName], r14
0x18000aaf8  jnz     short loc_18000AB11
0x18000aafa  lea     rdx, [rsp+5D0h+pStoryboardTargetName]; pStoryboardTargetName
0x18000aaff  mov     this, r15; pThemeAnimation
0x18000ab02  call    ?ThemeAnimation_GetStoryboardTargetName@@YAJPEAVTimeline@DirectUI@@PEAPEAUHSTRING__@@@Z; ThemeAnimation_GetStoryboardTargetName(DirectUI::Timeline *,HSTRING__ * *)
0x18000ab07  mov     ebx, eax
0x18000ab09  test    eax, eax
0x18000ab0b  js      loc_18000B333
0x18000ab11  call    ?IsTiltAnimationEnabled@TiltHelper@@YA_NXZ; TiltHelper::IsTiltAnimationEnabled(void)
0x18000ab16  test    al, al
0x18000ab18  jz      loc_18000AE55
0x18000ab1e  mov     esi, 32h ; '2'
0x18000ab23  lea     r9, [rbp+4D0h+strRotateXPropertyName._header]; string
0x18000ab2a  mov     edx, esi; length
0x18000ab2c  lea     pTimelineCollection, [rbp+4D0h+strRotateXPropertyName._header.Reserved+8]; hstringHeader
0x18000ab33  lea     this, aUielementProje_3; "(UIElement.Projection).(PlaneProjection"...
0x18000ab3a  call    cs:__imp_WindowsCreateStringReference
0x18000ab40  lea     edi, [rsi-31h]
0x18000ab43  mov     ebx, 0C000000Dh
0x18000ab48  test    eax, eax
0x18000ab4a  js      loc_18000B33F
0x18000ab50  lea     r9, [rbp+4D0h+strRotateYPropertyName._header]; string
0x18000ab57  mov     edx, esi; length
0x18000ab59  lea     pTimelineCollection, [rbp+4D0h+strRotateYPropertyName._header.Reserved+8]; hstringHeader
0x18000ab60  lea     this, aUielementProje_4; "(UIElement.Projection).(PlaneProjection"...
0x18000ab67  call    cs:__imp_WindowsCreateStringReference
0x18000ab6d  test    eax, eax
0x18000ab6f  js      loc_18000B354
0x18000ab75  lea     r9, [rbp+4D0h+strGlobalOffsetZPropertyName._header]; string
0x18000ab7c  mov     edx, 36h ; '6'; length
0x18000ab81  lea     pTimelineCollection, [rbp+4D0h+strGlobalOffsetZPropertyName._header.Reserved+8]; hstringHeader
0x18000ab88  lea     this, aUielementProje_0; "(UIElement.Projection).(PlaneProjection"...
0x18000ab8f  call    cs:__imp_WindowsCreateStringReference
0x18000ab95  test    eax, eax
0x18000ab97  js      loc_18000B369
0x18000ab9d  mov     esi, 33h ; '3'
0x18000aba2  lea     r9, [rbp+4D0h+strScaleXPropertyName._header]; string
0x18000aba9  mov     edx, esi; length
0x18000abab  lea     pTimelineCollection, [rbp+4D0h+strScaleXPropertyName._header.Reserved+8]; hstringHeader
0x18000abb2  lea     this, aUielementRende_2; "(UIElement.RenderTransform).(ScaleTrans"...
0x18000abb9  call    cs:__imp_WindowsCreateStringReference
0x18000abbf  test    eax, eax
0x18000abc1  js      loc_18000B37E
0x18000abc7  lea     r9, [rbp+4D0h+strScaleYPropertyName._header]; string
0x18000abce  mov     edx, esi; length
0x18000abd0  lea     pTimelineCollection, [rbp+4D0h+strScaleYPropertyName._header.Reserved+8]; hstringHeader
0x18000abd7  lea     this, aUielementRende_0; "(UIElement.RenderTransform).(ScaleTrans"...
0x18000abde  call    cs:__imp_WindowsCreateStringReference
0x18000abe4  test    eax, eax
0x18000abe6  js      loc_18000B393
0x18000abec  movdqa  xmm0, cs:__xmm@3e8000003dcccccd0000000000000000
0x18000abf4  movdqa  xmm1, cs:__xmm@3f8000003f8000003f6666663f400000
0x18000abfc  movups  xmmword ptr [rbp+4D0h+easing.cp2.X], xmm0
0x18000ac00  mov     [rsp+5D0h+spTransform.ptr_], r14
0x18000ac05  movups  xmmword ptr [rbp+4D0h+easing.cp4.X], xmm1
0x18000ac09  mov     [rsp+5D0h+spTimelineCompletedHandler.ptr_], r14
0x18000ac0e  mov     [rsp+5D0h+spProjection.ptr_], r14
0x18000ac13  cmp     [rsp+5D0h+spCoreDO.m_ptr], r14
0x18000ac18  jnz     loc_18000B03E
0x18000ac1e  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18000ac25  lea     rdx, [rsp+5D0h+spTarget]; pstrCloned
0x18000ac2a  mov     this, [rsp+5D0h+pStoryboardTargetName]; handle
0x18000ac2f  mov     [rsp+5D0h+spTarget.ptr_], rax
0x18000ac34  call    ?CloneRuntimeStringHandle@xstring_ptr@@SAJPEAUHSTRING__@@PEAV1@@Z; xstring_ptr::CloneRuntimeStringHandle(HSTRING__ *,xstring_ptr *)
0x18000ac39  mov     ebx, eax
0x18000ac3b  test    eax, eax
0x18000ac3d  js      loc_18000AE3F
0x18000ac43  mov     this, r15; this
0x18000ac46  call    ?GetHandle@DependencyObject@DirectUI@@QEBAPEAVCDependencyObject@@XZ; DirectUI::DependencyObject::GetHandle(void)
0x18000ac4b  lea     this, [rsp+5D0h+strTargetName]; this
0x18000ac50  mov     [rsp+5D0h+strTargetName._hstring], r14
0x18000ac55  mov     rbx, rax
0x18000ac58  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x18000ac5d  mov     this, [rbx+100h]
0x18000ac64  mov     pTimelineCollection, rbx
0x18000ac67  mov     rax, [rbx+10h]
0x18000ac6b  test    this, this
0x18000ac6e  cmovnz  pTimelineCollection, this
0x18000ac72  mov     rsi, [rax]
0x18000ac75  mov     eax, [pTimelineCollection+50h]
0x18000ac79  shr     eax, 5
0x18000ac7c  and     al, dil
0x18000ac7f  movzx   ebx, al
0x18000ac82  xor     ebx, edi
0x18000ac84  test    al, al
0x18000ac86  jz      loc_18000B324
0x18000ac8c  lea     this, [pTimelineCollection+108h]; this
0x18000ac93  call    ?lock_noref@?$weakref_ptr@VCScrollViewer@@@xref@@QEBAPEAVCScrollViewer@@XZ; xref::weakref_ptr<CScrollViewer>::lock_noref(void)
0x18000ac98  mov     r9d, ebx; nameScopeType
0x18000ac9b  lea     rdx, [rsp+5D0h+spTarget]; strName
0x18000aca0  mov     pTimelineCollection, rax; pNamescopeOwner
0x18000aca3  mov     this, rsi; this
0x18000aca6  call    ?GetNamedObject@CCoreServices@@QEAAPEAVCDependencyObject@@AEBVxstring_ptr_view@@PEBV2@W4NameScopeType@NameScoping@Jupiter@@@Z; CCoreServices::GetNamedObject(xstring_ptr_view const &,CDependencyObject const *,Jupiter::NameScoping::NameScopeType)
0x18000acab  mov     rsi, rax
0x18000acae  test    rax, rax
0x18000acb1  jz      loc_18000B26A
0x18000acb7  mov     this, rax; this
0x18000acba  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x18000acbf  mov     [rsp+5D0h+strTargetName._hstring], rsi
0x18000acc4  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x18000acc9  lea     this, [rsp+5D0h+spTransform]; this
0x18000acce  mov     rbx, rax
0x18000acd1  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x18000acd6  lea     rax, [rsp+5D0h+spTransform]
0x18000acdb  mov     r9d, edi; createMode
0x18000acde  mov     [rsp+5D0h+ppObject], rax; ppObject
0x18000ace3  mov     pTimelineCollection, rsi; pDO
0x18000ace6  mov     qword ptr [rsp+5D0h+bInternalRef+8], r14; pIsPendingDelete
0x18000aceb  xor     edx, edx; pOuter
0x18000aced  mov     this, rbx; this
0x18000acf0  mov     [rsp+5D0h+bInternalRef], r14d; bInternalRef
0x18000acf5  call    ?GetPeerPrivate@DXamlCore@DirectUI@@AEAAJPEAUIInspectable@@PEAVCDependencyObject@@W4GetPeerPrivateCreateMode@12@IPEAIPEAPEAVDependencyObject@2@@Z; DirectUI::DXamlCore::GetPeerPrivate(IInspectable *,CDependencyObject *,DirectUI::DXamlCore::GetPeerPrivateCreateMode,uint,uint *,DirectUI::DependencyObject * *)
0x18000acfa  mov     ebx, eax
0x18000acfc  test    eax, eax
0x18000acfe  js      loc_18000B302
0x18000ad04  lea     this, [rsp+5D0h+strTargetName]; this
0x18000ad09  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x18000ad0e  lea     this, [rsp+5D0h+spTarget]; this
0x18000ad13  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18000ad18  mov     rsi, [rsp+5D0h+spTransform.ptr_]
0x18000ad1d  lea     this, [rsp+5D0h+spTimelineCompletedHandler]; this
0x18000ad22  mov     rax, [rsi+0B8h]
0x18000ad29  mov     rbx, [rax+78h]
0x18000ad2d  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18000ad32  lea     rdx, [rsp+5D0h+spTimelineCompletedHandler]
0x18000ad37  mov     rax, rbx
0x18000ad3a  lea     this, [rsi+0B8h]
0x18000ad41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad46  mov     ebx, eax
0x18000ad48  test    eax, eax
0x18000ad4a  js      loc_18000B5A8
0x18000ad50  mov     rax, [rsi+0B8h]
0x18000ad57  lea     this, [rsp+5D0h+spProjection]; this
0x18000ad5c  mov     rbx, [rax+68h]
0x18000ad60  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18000ad65  lea     rdx, [rsp+5D0h+spProjection]
0x18000ad6a  mov     rax, rbx
0x18000ad6d  lea     this, [rsi+0B8h]
0x18000ad74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad79  mov     ebx, eax
0x18000ad7b  test    eax, eax
0x18000ad7d  js      loc_18000B59C
0x18000ad83  cmp     [rsp+5D0h+spTimelineCompletedHandler.ptr_], r14
0x18000ad88  jnz     loc_18000AE98
0x18000ad8e  mov     this, [rsp+5D0h+spProjection.ptr_]
0x18000ad93  test    this, this
0x18000ad96  jz      short loc_18000ADA9
0x18000ad98  mov     [rsp+5D0h+spProjection.ptr_], r14
0x18000ad9d  mov     rax, [this]
0x18000ada0  mov     rax, [rax+10h]
0x18000ada4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada9  mov     this, [rsp+5D0h+spTimelineCompletedHandler.ptr_]
0x18000adae  test    this, this
0x18000adb1  jz      short loc_18000ADC4
0x18000adb3  mov     [rsp+5D0h+spTimelineCompletedHandler.ptr_], r14
0x18000adb8  mov     rax, [this]
0x18000adbb  mov     rax, [rax+10h]
0x18000adbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc4  mov     this, [rsp+5D0h+spTransform.ptr_]
0x18000adc9  test    this, this
0x18000adcc  jz      short $Cleanup_18
0x18000adce  add     this, 8
0x18000add2  mov     [rsp+5D0h+spTransform.ptr_], r14
0x18000add7  mov     rax, [this]
0x18000adda  mov     rax, [rax+10h]
0x18000adde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ade3  mov     this, [rsp+5D0h+spCoreDO.m_ptr]
0x18000ade8  test    this, this
0x18000adeb  jz      short loc_18000ADFE
0x18000aded  mov     [rsp+5D0h+spCoreDO.m_ptr], r14
0x18000adf2  mov     rax, [this]
0x18000adf5  mov     rax, [rax+10h]
0x18000adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adfe  mov     this, [rsp+5D0h+pStoryboardTargetName]; string
0x18000ae03  test    this, this
0x18000ae06  jz      short loc_18000AE0E
0x18000ae08  call    cs:__imp_WindowsDeleteString
0x18000ae0e  mov     eax, ebx
0x18000ae10  mov     this, [rbp+4D0h+var_50]
0x18000ae17  xor     this, rsp; StackCookie
0x18000ae1a  call    __security_check_cookie
0x18000ae1f  lea     r11, [rsp+5D0h+var_30]
0x18000ae27  mov     rbx, [r11+58h]
0x18000ae2b  movaps  xmm6, xmmword ptr [r11-10h]
0x18000ae30  mov     rsp, r11
0x18000ae33  pop     r15
0x18000ae35  pop     r14
0x18000ae37  pop     r13
0x18000ae39  pop     r12
0x18000ae3b  pop     rdi
0x18000ae3c  pop     rsi
0x18000ae3d  pop     rbp
0x18000ae3e  retn
0x18000ae3f  mov     ecx, eax; failedFrameHR
0x18000ae41  call    OnFailure_2990_
0x18000ae46  lea     this, [rsp+5D0h+spTarget]; this
0x18000ae4b  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18000ae50  jmp     loc_18000AD8E
0x18000ae55  mov     r9, [rsp+5D0h+spCoreDO.m_ptr]; pTarget
0x18000ae5a  mov     edx, 1; targetID
0x18000ae5f  mov     pTimelineCollection, [rsp+5D0h+pStoryboardTargetName]; targetName
0x18000ae64  unpcklps xmm6, xmm6
0x18000ae67  unpcklpd xmm6, xmm6
0x18000ae6b  mov     [rsp+5D0h+spDO.ptr_], r12; timelineCollection
0x18000ae70  lea     ecx, [rdx+14h]; storyboardID
0x18000ae73  movups  xmmword ptr [rsp+5D0h+bInternalRef+8], xmm6; startOffset
0x18000ae78  mov     byte ptr [rsp+5D0h+bInternalRef], r13b; onlyGenerateSteadyState
0x18000ae7d  call    ?AddTimelinesForThemeAnimation@ThemeGenerator@DirectUI@@SAJHHPEAUHSTRING__@@PEAUIDependencyObject@Xaml@UI@Windows@@EUPoint@Foundation@7@2PEAU?$IVector@PEAVTimeline@Animation@Media@Xaml@UI@Windows@@@Collections@97@@Z; DirectUI::ThemeGenerator::AddTimelinesForThemeAnimation(int,int,HSTRING__ *,Windows::UI::Xaml::IDependencyObject *,uchar,Windows::Foundation::Point,Windows::Foundation::Point,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> *)
0x18000ae82  mov     ebx, eax
0x18000ae84  test    eax, eax
0x18000ae86  jns     $Cleanup_18
0x18000ae8c  mov     ecx, eax; failedFrameHR
0x18000ae8e  call    OnFailure_2990_
0x18000ae93  jmp     $Cleanup_18
0x18000ae98  cmp     [rsp+5D0h+spProjection.ptr_], r14
0x18000ae9d  jz      loc_18000AD8E
0x18000aea3  xor     esi, esi
0x18000aea5  mov     [rsp+5D0h+spTarget.ptr_], r14
0x18000aeaa  lea     this, [rsp+5D0h+strTargetName]; this
0x18000aeaf  mov     [rsp+5D0h+strTargetName._hstring], rsi
0x18000aeb4  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x18000aeb9  mov     this, [rsp+5D0h+spProjection.ptr_]
0x18000aebe  test    this, this
0x18000aec1  jz      short loc_18000AEDA
0x18000aec3  mov     rax, [this]
0x18000aec6  lea     pTimelineCollection, [rsp+5D0h+strTargetName]
0x18000aecb  lea     rdx, _GUID_eaf2ce09_ecf2_48f8_8327_5ae4f5e792ce
0x18000aed2  mov     rax, [rax]
0x18000aed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeda  mov     this, [rsp+5D0h+strTargetName._hstring]
0x18000aedf  mov     rax, this
0x18000aee2  neg     rax
0x18000aee5  sbb     ebx, ebx
0x18000aee7  neg     ebx
0x18000aee9  sub     ebx, edi
0x18000aeeb  test    this, this
0x18000aeee  jz      short loc_18000AF05
0x18000aef0  add     this, 8
0x18000aef4  mov     [rsp+5D0h+strTargetName._hstring], rsi
0x18000aef9  mov     rax, [this]
0x18000aefc  mov     rax, [rax+10h]
0x18000af00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af05  cmp     ebx, 0FFFFFFFFh
0x18000af08  jnz     loc_18000B3A8
0x18000af0e  cmp     cs:?m_quirkCacheSuppressions@CQuirksMode2@@0JA, esi; long CQuirksMode2::m_quirkCacheSuppressions
0x18000af14  jnz     loc_18000B3F1
0x18000af1a  xor     r9d, r9d; Context
0x18000af1d  lea     pTimelineCollection, qword_180F72750; Parameter
0x18000af24  lea     rdx, ?InitOnceCallback@CQuirksMode2@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000af2b  lea     this, InitOnce; InitOnce
0x18000af32  call    cs:__imp_InitOnceExecuteOnce
0x18000af38  mov     rax, cs:qword_180F72750
0x18000af3f  movzx   ecx, byte ptr [rax+1]
0x18000af43  shr     ecx, 3
0x18000af46  test    edi, ecx
0x18000af48  mov     rax, [rsp+5D0h+spCoreDO.m_ptr]
0x18000af4d  lea     this, [rbp+4D0h+depressionSupplier.m_begintime]; this
0x18000af51  mov     r9, [rsp+5D0h+pStoryboardTargetName]; targetName
  ... truncated ...
```
