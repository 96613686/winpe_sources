# DirectUI::ModernCollectionBasePanel::UpdateItemClippingForStickyHeaders(Windows::Foundation::Size const &,bool,bool)

- ea: `0x18000baf8`
- end: `0x18000ce4b`
- name: `?UpdateItemClippingForStickyHeaders@ModernCollectionBasePanel@DirectUI@@AEAAJAEBUSize@Foundation@Windows@@_N1@Z`
- size: `4947`
- prototype: `HRESULT __fastcall(DirectUI::ModernCollectionBasePanel *this, const Windows::Foundation::Size *finalSize, bool manuallyUpdatePosition, bool updateClip)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18049deb0`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x18000baf8`
- `0x18000ce54`
- `0x18000ce70`
- `0x18007a5d4`
- `0x1800ed0c4`
- `0x1800f2084`
- `0x1800f4510`
- `0x1801bac6c`
- `0x1801dfeb0`
- `0x1801e5458`
- `0x180238364`
- `0x18023bc3c`
- `0x18029561c`
- `0x180298d6c`
- `0x18029e2f8`
- `0x18034c7d4`
- `0x180384178`
- `0x1804946d8`
- `0x1804a3b40`
- `0x18054ff4c`
- `0x18054ffd4`
- `0x180550390`
- `0x180550418`
- `0x18055042c`
- `0x180550440`
- `0x1805df7e4`
- `0x180662c08`
- `0x1806d1b40`
- `0x1806fa26c`
- `0x1806fe828`
- `0x180703b7c`
- `0x18076e110`
- `0x180b64a14`
- `0x180b64f30`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c16d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c17b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c16d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c17b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c0ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c0e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c0ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c0e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c218`

## pseudocode

```c
__int64 __fastcall DirectUI::ModernCollectionBasePanel::UpdateItemClippingForStickyHeaders(
        DirectUI::ModernCollectionBasePanel *this,
        const Windows::Foundation::Size *finalSize,
        bool manuallyUpdatePosition,
        char updateClip)
{
  float Width; // xmm1_4
  bool v5; // cc
  unsigned int v6; // esi
  float Height; // xmm0_4
  Windows::UI::Xaml::IUIElement *v10; // r13
  HRESULT (__fastcall *get_Clip)(Windows::UI::Xaml::IUIElement *, Windows::UI::Xaml::Media::IRectangleGeometry **); // rbx
  HRESULT v12; // eax
  int v13; // edi
  DirectUI::SecondaryContentRelationship *ptr; // rcx
  DirectUI::SecondaryContentRelationship *v15; // rdx
  ctl::ComPtr<DirectUI::RectangleGeometry> *v16; // rbx
  ctl::ComPtr<DirectUI::RectangleGeometry> *v17; // rax
  HRESULT v18; // eax
  DirectUI::TrackerPtr<DirectUI::CompositeTransform,1,0> *p_m_tpItemClippingTransform; // r12
  ctl::ComPtr<DirectUI::RectangleGeometry> *v20; // rdi
  ctl::interface_forwarder<Windows::UI::Xaml::Hosting::IReferenceTrackerInternal,ctl::WeakReferenceSourceNoThreadId>_vtbl *v21; // rbx
  IUnknown *v22; // rdx
  IUnknown *v23; // rdx
  bool v24; // al
  void *v25; // rcx
  DirectUI::ModernCollectionBasePanel::StickyHeaderInfo *Myfirst; // rax
  HRESULT ElementAtValidIndex; // eax
  DirectUI::ModernCollectionBasePanel::StickyHeaderInfo *Mylast; // rdx
  DirectUI::DPChangedEventSource *m_pDPChangedEventSource; // rcx
  float v30; // xmm0_4
  float v31; // xmm1_4
  DirectUI::SecondaryContentRelationship *v32; // rcx
  std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo> *v33; // rdx
  std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo> *v34; // r11
  DirectUI::TrackerPtr<DirectUI::SecondaryContentRelationship,1,0> *p_m_tpItemClippingRelationship; // rbx
  __int64 v36; // rdx
  __int64 v37; // rdx
  HRESULT v38; // eax
  DirectUI::TrackerPtr<DirectUI::CompositeTransform,1,0> *v39; // rcx
  DirectUI::SecondaryContentRelationship *v40; // rcx
  ctl::ComPtr<DirectUI::RectangleGeometry> *v41; // rcx
  HRESULT ValueByKnownIndex; // eax
  __int64 v44; // rdx
  Windows::UI::Xaml::IUIElement *v45; // rdx
  DirectUI::DependencyObject *v46; // rbx
  HRESULT v47; // eax
  HRESULT v48; // eax
  HRESULT v49; // eax
  DirectUI::ParametricCurveSegmentCollection *v50; // rdi
  DirectUI::DirectManipulationProperty v51; // edx
  Windows::UI::Xaml::Controls::IScrollViewer *v52; // rbx
  ctl::WeakReferenceSourceNoThreadId *v53; // rcx
  HRESULT v54; // eax
  HRESULT v55; // eax
  HRESULT v56; // eax
  HRESULT v57; // eax
  DirectUI::PresentationFrameworkCollectionTemplateBase<DirectUI::ParametricCurveSegment *> *v58; // rcx
  HSTRING v59; // rcx
  ctl::ComPtr<DirectUI::ParametricCurve> *v60; // rcx
  Windows::UI::Xaml::IDependencyObject *v61; // rcx
  DirectUI::ParametricCurveSegment *v62; // rcx
  DirectUI::KeyboardAcceleratorCollection *v63; // rcx
  HRESULT v64; // eax
  IUnknown *m_value; // rbx
  HRESULT v66; // eax
  DirectUI::SecondaryContentRelationship *v67; // rdi
  void (__fastcall *v68)(ctl::ComBase *); // rbx
  DirectUI::DependencyObject *v69; // rbx
  ctl::forwarder_holder<IWeakReferenceSource,ctl::WeakReferenceSourceNoThreadId> *v70; // rcx
  Windows::UI::Xaml::Controls::IScrollViewer *v71; // rcx
  std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo> *p_m_currentStickyHeaderLocations; // rdi
  DirectUI::ModernCollectionBasePanel::StickyHeaderInfo *v73; // rax
  DirectUI::ModernCollectionBasePanel::StickyHeaderInfo *v74; // rbx
  double m_size; // xmm10_8
  DirectUI::ModernCollectionBasePanel::StickyHeaderInfo *v76; // r12
  long double v77; // xmm7_8
  double v78; // xmm9_8
  char v79; // r15
  __int64 v80; // rcx
  HRESULT v81; // eax
  __int64 v82; // rcx
  ctl::WeakReferenceSourceNoThreadId *v83; // rcx
  __int64 v84; // rcx
  double m_offset; // xmm6_8
  double v86; // xmm8_8
  long double v87; // xmm6_8
  HRESULT v88; // eax
  HRESULT v89; // eax
  Windows::UI::Xaml::IDependencyObject *v90; // rcx
  DirectUI::KeyboardAcceleratorCollection *v91; // rcx
  Windows::UI::Xaml::IDependencyObject *v92; // rcx
  double v93; // xmm5_8
  long double v94; // xmm5_8
  DirectUI::DirectManipulationProperty v95; // edx
  DirectUI::DependencyObject *v96; // rbx
  HRESULT v97; // eax
  ctl::ComPtr<DirectUI::SoftwareBitmapSource> *p_spParametricCurveAsIDO; // rcx
  double m_cachedPannableExtent; // xmm0_8
  ctl::ComPtr<DirectUI::SoftwareBitmapSource> *v100; // rcx
  double v101; // xmm6_8
  ctl::ComPtr<DirectUI::SoftwareBitmapSource> *p_spRelationship; // rcx
  ctl::ComPtr<DirectUI::SecondaryContentRelationship> spRelationship; // [rsp+28h] [rbp-E0h] BYREF
  ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> curveCollectionSize; // [rsp+30h] [rbp-D8h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spParametricCurveAsIDO; // [rsp+38h] [rbp-D0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IScrollViewer> spScrollViewer; // [rsp+40h] [rbp-C8h] BYREF
  ctl::ComPtr<DirectUI::ParametricCurveSegment> spCurveSegment; // [rsp+48h] [rbp-C0h] BYREF
  ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection> spCurveSegmentCollection; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-B0h] BYREF
  ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurve> > ppNewInstance; // [rsp+60h] [rbp-A8h] BYREF
  ctl::ComPtr<DirectUI::RectangleGeometry> spClip; // [rsp+68h] [rbp-A0h]
  ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::RectangleGeometry> > v112; // [rsp+70h] [rbp-98h] BYREF
  HSTRING newValue; // [rsp+78h] [rbp-90h] BYREF
  Windows::Foundation::Rect bounds; // [rsp+80h] [rbp-88h] BYREF
  float v115; // [rsp+90h] [rbp-78h]
  float v116; // [rsp+94h] [rbp-74h] BYREF

  Width = this->m_estimatedSize.Width;
  v5 = Width <= finalSize->Width;
  v6 = 0;
  LOBYTE(spClip.ptr_) = manuallyUpdatePosition;
  *(_QWORD *)&bounds.Width = 0;
  if ( v5 )
    Width = finalSize->Width;
  Height = this->m_estimatedSize.Height;
  v5 = Height <= finalSize->Height;
  v115 = Width;
  if ( v5 )
    Height = finalSize->Height;
  v116 = Height;
  v112.ptr_ = 0;
  if ( !CQuirksMode2::QuirkShouldUseStickyGroupHeaders() )
    goto $Cleanup_22;
  spRelationship.ptr_ = 0;
  v10 = &this->Windows::UI::Xaml::IUIElement;
  get_Clip = this->get_Clip;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spRelationship);
  v12 = get_Clip(&this->Windows::UI::Xaml::IUIElement, (Windows::UI::Xaml::Media::IRectangleGeometry **)&spRelationship);
  v13 = 0;
  v6 = v12;
  if ( v12 < 0 )
    goto LABEL_158;
  ptr = spRelationship.ptr_;
  v15 = 0;
  spRelationship.ptr_ = 0;
  v16 = (ctl::ComPtr<DirectUI::RectangleGeometry> *)((unsigned __int64)&ptr[-1]
                                                   & ((unsigned __int128)-(__int128)(unsigned __int64)ptr >> 64));
  v17 = v112.ptr_;
  if ( v112.ptr_ != v16 )
  {
    if ( v112.ptr_ )
    {
      v112.ptr_ = 0;
      (*(void (**)(void))&v17[1].ptr_->m_inFinalRelease)();
      v15 = spRelationship.ptr_;
    }
    v17 = v16;
    v112.ptr_ = v16;
  }
  if ( v15 )
  {
    spRelationship.ptr_ = 0;
    v15->Release(v15);
    v17 = v112.ptr_;
  }
  if ( !v17 )
  {
    v18 = ctl::make<DirectUI::RectangleGeometry>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::RectangleGeometry> >)&v112);
    v6 = v18;
    if ( v18 < 0 )
      goto LABEL_120;
    updateClip = 1;
    v18 = v10->put_Clip(
            &this->Windows::UI::Xaml::IUIElement,
            (Windows::UI::Xaml::Media::IRectangleGeometry *)((__int64)&v112.ptr_[24] & -(__int64)(v112.ptr_ != 0)));
    v6 = v18;
    if ( v18 < 0 )
      goto LABEL_120;
  }
  if ( CQuirksMode2::QuirkOnlyPhoneBlue() )
  {
    spRelationship.ptr_ = 0;
    v12 = ctl::WeakRefPtr::As<Windows::UI::Xaml::Controls::IScrollViewer>(
            &this->m_wrScrollViewer,
            (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IScrollViewer> >)&spRelationship);
    v6 = v12;
    if ( v12 < 0 )
      goto LABEL_158;
    if ( spRelationship.ptr_ )
    {
      *(double *)&spCurveSegmentCollection.ptr_ = 0.0;
      *(double *)&spScrollViewer.ptr_ = 0.0;
      v12 = ((__int64 (__fastcall *)(DirectUI::SecondaryContentRelationship *, ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection> *))spRelationship.ptr_->__vftable[1].GetDefaultValue2)(
              spRelationship.ptr_,
              &spCurveSegmentCollection);
      v6 = v12;
      if ( v12 < 0 )
        goto LABEL_158;
      v12 = spRelationship.ptr_->__vftable[1].OnPropertyChanged2(
              spRelationship.ptr_,
              (const PropertyChangedParams *)&spScrollViewer);
      v6 = v12;
      if ( v12 < 0 )
        goto LABEL_158;
      v93 = *(double *)&spScrollViewer.ptr_ - *(double *)&spCurveSegmentCollection.ptr_;
      if ( *(double *)&spScrollViewer.ptr_ - *(double *)&spCurveSegmentCollection.ptr_ <= 0.0 )
        v93 = 0.0;
      if ( !DirectUI::DoubleUtil::AreClose(v93, this->m_cachedPannableExtent) )
      {
        this->m_cachedPannableExtent = v94;
        updateClip = 1;
      }
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spRelationship);
  }
  v18 = (*((__int64 (__fastcall **)(ctl::ComPtr<DirectUI::RectangleGeometry> *, float *))&v112.ptr_[24].ptr_->ctl::WeakReferenceSourceNoThreadId
         + 6))(
          v112.ptr_ + 24,
          &bounds.Width);
  v6 = v18;
  if ( v18 < 0 )
  {
LABEL_120:
    OnFailure_2990_(v18);
    goto $Cleanup_22;
  }
  p_m_tpItemClippingTransform = &this->m_tpItemClippingTransform;
  spRelationship.ptr_ = 0;
  if ( this->m_tpItemClippingTransform.m_trackerReference.m_value )
  {
    v20 = v112.ptr_;
    v21 = v112.ptr_[23].ptr_->m_forwarder.__vftable;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spRelationship);
    v12 = ((__int64 (__fastcall *)(ctl::ComPtr<DirectUI::RectangleGeometry> *, ctl::ComPtr<DirectUI::SecondaryContentRelationship> *))v21)(
            &v20[23],
            &spRelationship);
    v13 = 0;
    v6 = v12;
    if ( v12 >= 0 )
    {
      v22 = (IUnknown *)((unsigned __int128)&p_m_tpItemClippingTransform->m_trackerReference.m_value[-1]
                       & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpItemClippingTransform->m_trackerReference.m_value >> 64));
      if ( v22 )
        v23 = v22 + 1;
      else
        v23 = 0;
      v24 = ctl::are_equal<IInspectable,IInspectable>(spRelationship.ptr_, v23);
      v25 = spRelationship.ptr_;
      if ( !v24 )
        updateClip = 1;
      if ( !spRelationship.ptr_ )
        goto LABEL_24;
      goto LABEL_23;
    }
LABEL_158:
    OnFailure_2990_(v12);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spRelationship);
    goto $Cleanup_22;
  }
  v38 = ctl::make<DirectUI::CompositeTransform>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::CompositeTransform> >)&spRelationship);
  v6 = v38;
  if ( v38 < 0 )
  {
    OnFailure_2990_(v38);
    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRelationship);
    goto $Cleanup_22;
  }
  updateClip = 1;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpItemClippingTransform.m_trackerReference);
  v39 = &this->m_tpItemClippingTransform;
  if ( spRelationship.ptr_ )
    DirectUI::TrackerTargetReference::Set(
      &v39->m_trackerReference,
      &spRelationship.ptr_->ctl::WeakReferenceSourceNoThreadId,
      1u,
      0);
  else
    DirectUI::TrackerTargetReference::Clear(&v39->m_trackerReference, 1u, 0);
  if ( spRelationship.ptr_ )
  {
    v25 = &spRelationship.ptr_->ctl::WeakReferenceSourceNoThreadId;
LABEL_23:
    spRelationship.ptr_ = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
  }
LABEL_24:
  Myfirst = this->m_newStickyHeaderLocations._Mypair._Myval2._Myfirst;
  if ( Myfirst != this->m_newStickyHeaderLocations._Mypair._Myval2._Mylast )
    this->m_newStickyHeaderLocations._Mypair._Myval2._Mylast = Myfirst;
  std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo>::reserve(
    &this->m_newStickyHeaderLocations,
    SLODWORD(this->m_containerManager.m_validElements._Elems[1]._Mypair._Myval2._Mysize));
  while ( v13 < SLODWORD(this->m_containerManager.m_validElements._Elems[1]._Mypair._Myval2._Mysize) )
  {
    spRelationship.ptr_ = 0;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spRelationship);
    ElementAtValidIndex = DirectUI::ModernCollectionBasePanel::ContainerManager::GetElementAtValidIndex(
                            &this->m_containerManager,
                            ElementType_GroupHeader,
                            v13,
                            (ctl::ComPtr<Windows::UI::Xaml::IUIElement> *)&spRelationship);
    v6 = ElementAtValidIndex;
    if ( ElementAtValidIndex < 0 )
    {
      OnFailure_2990_(ElementAtValidIndex);
      v40 = spRelationship.ptr_;
      if ( !spRelationship.ptr_ )
        goto $Cleanup_22;
      spRelationship.ptr_ = 0;
      goto LABEL_48;
    }
    if ( spRelationship.ptr_ )
    {
      Mylast = this->m_newStickyHeaderLocations._Mypair._Myval2._Mylast;
      m_pDPChangedEventSource = spRelationship.ptr_->m_pDPChangedEventSource;
      v30 = *(float *)&m_pDPChangedEventSource->_bytes_18[4];
      v31 = *(float *)&m_pDPChangedEventSource->_bytes_18[12];
      bounds.Width = *(float *)m_pDPChangedEventSource->_bytes_18;
      v115 = *(float *)&m_pDPChangedEventSource->_bytes_18[8];
      bounds.Height = v30;
      v116 = v31;
      if ( Mylast == this->m_newStickyHeaderLocations._Mypair._Myval2._Myend )
      {
        std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo>::_Emplace_reallocate<float &,float &>(
          &this->m_newStickyHeaderLocations,
          Mylast,
          &bounds.Height,
          &v116);
      }
      else
      {
        this->m_newStickyHeaderLocations._Mypair._Myval2._Mylast = Mylast + 1;
        Mylast->m_offset = v30;
        Mylast->m_size = v31;
      }
      v32 = spRelationship.ptr_;
      if ( spRelationship.ptr_ )
      {
        spRelationship.ptr_ = 0;
        v32->Release(v32);
      }
    }
    ++v13;
  }
  if ( std::operator!=<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo,std::allocator<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo>>(
         &this->m_currentStickyHeaderLocations,
         &this->m_newStickyHeaderLocations) )
  {
    updateClip = 1;
    std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo>::swap(v34, v33);
  }
  p_m_tpItemClippingRelationship = &this->m_tpItemClippingRelationship;
  *(_QWORD *)&bounds.Width = &this->m_tpItemClippingRelationship;
  if ( this->m_tpItemClippingRelationship.m_trackerReference.m_value )
  {
    if ( !updateClip )
      goto LABEL_116;
    goto LABEL_39;
  }
  curveCollectionSize.ptr_ = 0;
  spCurveSegment.ptr_ = 0;
  spParametricCurveAsIDO.ptr_ = 0;
  ValueByKnownIndex = ctl::WeakRefPtr::As<Windows::UI::Xaml::Controls::IScrollViewer>(
                        &this->m_wrScrollViewer,
                        (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IScrollViewer> >)&spCurveSegment);
  v6 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0 )
    goto LABEL_209;
  ValueByKnownIndex = ctl::make<DirectUI::SecondaryContentRelationship>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::SecondaryContentRelationship> >)&curveCollectionSize);
  v6 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0 )
    goto LABEL_209;
  v44 = (unsigned __int128)&spCurveSegment.ptr_[-4].m_pInheritanceContextChangedEventSource
      & ((unsigned __int128)-(__int128)(unsigned __int64)spCurveSegment.ptr_ >> 64);
  v45 = v44 ? (Windows::UI::Xaml::IUIElement *)(v44 + 184) : 0LL;
  ValueByKnownIndex = DirectUI::SecondaryContentRelationship::SetPrimaryContent(
                        (DirectUI::SecondaryContentRelationship *)curveCollectionSize.ptr_,
                        v45);
  v6 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0 )
    goto LABEL_209;
  ValueByKnownIndex = DirectUI::SecondaryContentRelationship::SetSecondaryContent(
                        (DirectUI::SecondaryContentRelationship *)curveCollectionSize.ptr_,
                        (Windows::UI::Xaml::IUIElement *)((unsigned __int64)v10
                                                        & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                        (Windows::UI::Xaml::IDependencyObject *)((__int64)&p_m_tpItemClippingTransform->m_trackerReference.m_value[-1]
                                                               & -(__int64)(p_m_tpItemClippingTransform->m_trackerReference.m_value != 0)));
  v6 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0
    || (v46 = (DirectUI::DependencyObject *)curveCollectionSize.ptr_,
        ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&spParametricCurveAsIDO),
        ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                              v46,
                              SecondaryContentRelationship_Curves,
                              &GUID_5407a384_4f89_49d1_a185_c4cdeee5b571,
                              (void **)&spParametricCurveAsIDO.ptr_),
        v6 = ValueByKnownIndex,
        ValueByKnownIndex < 0)
    || (ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex<unsigned char>(
                              (DirectUI::DependencyObject *)curveCollectionSize.ptr_,
                              SecondaryContentRelationship_ShouldTargetClip,
                              1u),
        v6 = ValueByKnownIndex,
        ValueByKnownIndex < 0) )
  {
LABEL_209:
    OnFailure_2990_(ValueByKnownIndex);
    goto LABEL_210;
  }
  spRelationship.ptr_ = 0;
  *(double *)&spCurveSegmentCollection.ptr_ = 0.0;
  *(double *)&spScrollViewer.ptr_ = 0.0;
  v47 = ctl::make<DirectUI::ParametricCurve>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurve> >)&spRelationship);
  v6 = v47;
  if ( v47 < 0 )
    goto LABEL_207;
  string = 0;
  v48 = WindowsCreateString(L"VerticalOffset", 0xEu, &string);
  v47 = Windows::Internal::String::FreeAndAssignOnSuccess(v48, string, (HSTRING__ **)&spCurveSegmentCollection);
  v6 = v47;
  if ( v47 < 0 )
    goto LABEL_207;
  string = 0;
  v49 = WindowsCreateString(L"TranslateY", 0xAu, &string);
  v47 = Windows::Internal::String::FreeAndAssignOnSuccess(v49, string, (HSTRING__ **)&spScrollViewer);
  v6 = v47;
  if ( v47 < 0 )
    goto LABEL_207;
  v50 = spCurveSegmentCollection.ptr_;
  v47 = DirectUI::ParametricCurve::SetPrimaryContentProperty(
          (DirectUI::ParametricCurve *)spRelationship.ptr_,
          (HSTRING__ *)spCurveSegmentCollection.ptr_);
  v6 = v47;
  if ( v47 < 0
    || (v52 = spScrollViewer.ptr_,
        LOBYTE(v51) = 2,
        v47 = DirectUI::ParametricCurve::SetSecondaryContentProperty(
                (DirectUI::ParametricCurve *)spRelationship.ptr_,
                v51,
                (HSTRING__ *)spScrollViewer.ptr_),
        v6 = v47,
        v47 < 0)
    || (v47 = ((__int64 (__fastcall *)(Windows::UI::Xaml::IDependencyObject *, DirectUI::SecondaryContentRelationship *))spParametricCurveAsIDO.ptr_[2].__vftable[1].AddRef)(
                &spParametricCurveAsIDO.ptr_[2],
                spRelationship.ptr_),
        v6 = v47,
        v47 < 0) )
  {
LABEL_207:
    OnFailure_2990_(v47);
    Windows::Internal::String::~String((Windows::Internal::String *)&spScrollViewer);
    Windows::Internal::String::~String((Windows::Internal::String *)&spCurveSegmentCollection);
    p_spRelationship = (ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRelationship;
    goto LABEL_208;
  }
  if ( v52 )
    WindowsDeleteString((HSTRING)v52);
  if ( v50 )
    WindowsDeleteString((HSTRING)v50);
  if ( spRelationship.ptr_ )
  {
    v53 = &spRelationship.ptr_->ctl::WeakReferenceSourceNoThreadId;
    spRelationship.ptr_ = 0;
    v53->Release(v53);
  }
  ppNewInstance.ptr_ = 0;
  string = 0;
  *(double *)&spCurveSegmentCollection.ptr_ = 0.0;
  spRelationship.ptr_ = 0;
  *(double *)&spScrollViewer.ptr_ = 0.0;
  v54 = ctl::make<DirectUI::ParametricCurve>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurve> >)&ppNewInstance);
  v6 = v54;
  if ( v54 < 0 )
    goto LABEL_206;
  newValue = 0;
  v55 = WindowsCreateString(L"HorizontalOffset", 0x10u, &newValue);
  v54 = Windows::Internal::String::FreeAndAssignOnSuccess(v55, newValue, (HSTRING__ **)&spRelationship);
  v6 = v54;
  if ( v54 < 0 )
    goto LABEL_206;
  newValue = 0;
  v56 = WindowsCreateString(L"TranslateX", 0xAu, &newValue);
  v57 = Windows::Internal::String::FreeAndAssignOnSuccess(v56, newValue, (HSTRING__ **)&spScrollViewer);
  v6 = v57;
  if ( v57 < 0 )
  {
    OnFailure_2990_(v57);
    if ( *(double *)&spScrollViewer.ptr_ != 0.0 )
      WindowsDeleteString((HSTRING)spScrollViewer.ptr_);
    if ( spRelationship.ptr_ )
      WindowsDeleteString((HSTRING)spRelationship.ptr_);
    if ( *(double *)&spCurveSegmentCollection.ptr_ != 0.0 )
    {
      v58 = &spCurveSegmentCollection.ptr_->DirectUI::PresentationFrameworkCollectionTemplateBase<DirectUI::ParametricCurveSegment *>;
      *(double *)&spCurveSegmentCollection.ptr_ = 0.0;
      v58->Release(v58);
    }
    if ( string )
    {
      v59 = string + 10;
      string = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v59 + 16LL))(v59);
    }
    if ( ppNewInstance.ptr_ )
    {
      v60 = ppNewInstance.ptr_ + 1;
      ppNewInstance.ptr_ = 0;
      (*(void (__fastcall **)(ctl::ComPtr<DirectUI::ParametricCurve> *))&v60->ptr_->m_inFinalRelease)(v60);
    }
    if ( spParametricCurveAsIDO.ptr_ )
    {
      v61 = spParametricCurveAsIDO.ptr_ + 5;
      spParametricCurveAsIDO.ptr_ = 0;
      v61->Release(v61);
    }
    v62 = spCurveSegment.ptr_;
    if ( spCurveSegment.ptr_ )
    {
      spCurveSegment.ptr_ = 0;
      v62->Release(v62);
    }
    v63 = curveCollectionSize.ptr_;
    if ( !curveCollectionSize.ptr_ )
      goto $Cleanup_22;
    curveCollectionSize.ptr_ = 0;
    v40 = (DirectUI::SecondaryContentRelationship *)&v63->DirectUI::PresentationFrameworkCollectionTemplateBase<Windows::UI::Xaml::Input::KeyboardAccelerator *>;
    goto LABEL_48;
  }
  v54 = DirectUI::ParametricCurve::SetPrimaryContentProperty(
          (DirectUI::ParametricCurve *)ppNewInstance.ptr_,
          (HSTRING__ *)spRelationship.ptr_);
  v6 = v54;
  if ( v54 < 0 )
    goto LABEL_206;
  LOBYTE(v95) = 1;
  v54 = DirectUI::ParametricCurve::SetSecondaryContentProperty(
          (DirectUI::ParametricCurve *)ppNewInstance.ptr_,
          v95,
          (HSTRING__ *)spScrollViewer.ptr_);
  v6 = v54;
  if ( v54 < 0 )
    goto LABEL_206;
  v96 = (DirectUI::DependencyObject *)ppNewInstance.ptr_;
  ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&string);
  v54 = DirectUI::DependencyObject::GetValueByKnownIndex(
          v96,
          ParametricCurve_CurveSegments,
          &GUID_4bd24630_5850_41f0_9bb1_0e82533a4ea3,
          (void **)&string);
  v6 = v54;
  if ( v54 < 0
    || (v54 = ctl::make<DirectUI::ParametricCurveSegment>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurveSegment> >)&spCurveSegmentCollection),
        v6 = v54,
        v54 < 0)
    || (v54 = (*(__int64 (__fastcall **)(HSTRING, DirectUI::ParametricCurveSegmentCollection *))(*((_QWORD *)string + 2)
                                                                                               + 104LL))(
                string + 4,
                spCurveSegmentCollection.ptr_),
        v6 = v54,
        v54 < 0)
    || (v54 = ((__int64 (__fastcall *)(Windows::UI::Xaml::IDependencyObject *, ctl::ComPtr<DirectUI::ParametricCurve> *))spParametricCurveAsIDO.ptr_[2].__vftable[1].AddRef)(
                &spParametricCurveAsIDO.ptr_[2],
                ppNewInstance.ptr_),
        v6 = v54,
        v54 < 0) )
  {
LABEL_206:
    OnFailure_2990_(v54);
    Windows::Internal::String::~String((Windows::Internal::String *)&spScrollViewer);
    Windows::Internal::String::~String((Windows::Internal::String *)&spRelationship);
    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spCurveSegmentCollection);
    ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&string);
    p_spRelationship = (ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&ppNewInstance;
LABEL_208:
    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(p_spRelationship);
LABEL_210:
    ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&spParametricCurveAsIDO);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCurveSegment);
    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&curveCollectionSize);
    goto $Cleanup_22;
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&spScrollViewer);
  Windows::Internal::String::~String((Windows::Internal::String *)&spRelationship);
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spCurveSegmentCollection);
  ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&string);
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&ppNewInstance);
  p_m_tpItemClippingRelationship = &this->m_tpItemClippingRelationship;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<DirectUI::Border,DirectUI::Border>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpItemClippingRelationship,
    (const ctl::ComPtr<DirectUI::SecondaryContentRelationship> *)&curveCollectionSize);
  ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&spParametricCurveAsIDO);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCurveSegment);
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&curveCollectionSize);
LABEL_39:
  curveCollectionSize.ptr_ = 0;
  v36 = (unsigned __int128)&p_m_tpItemClippingTransform->m_trackerReference.m_value[-1]
      & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpItemClippingTransform->m_trackerReference.m_value >> 64);
  if ( v36 )
    v37 = v36 + 200;
  else
    v37 = 0;
  v64 = (*((__int64 (__fastcall **)(ctl::ComPtr<DirectUI::RectangleGeometry> *, __int64))&v112.ptr_[23].ptr_->ctl::WeakReferenceSourceNoThreadId
         + 6))(
          v112.ptr_ + 23,
          v37);
  v6 = v64;
  if ( v64 < 0 )
    goto LABEL_204;
  m_value = p_m_tpItemClippingRelationship->m_trackerReference.m_value;
  *(double *)&spScrollViewer.ptr_ = 0.0;
  spRelationship.ptr_ = 0;
  LODWORD(spParametricCurveAsIDO.ptr_) = 0;
  ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&spRelationship);
  v66 = DirectUI::DependencyObject::GetValueByKnownIndex(
          (DirectUI::DependencyObject *)((unsigned __int64)&m_value[-1] & -(__int64)(m_value != 0)),
          SecondaryContentRelationship_Curves,
          &GUID_5407a384_4f89_49d1_a185_c4cdeee5b571,
          (void **)&spRelationship.ptr_);
  v6 = v66;
  if ( v66 < 0 )
    goto LABEL_203;
  v66 = ((__int64 (__fastcall *)(ctl::WeakReferenceSourceNoThreadId *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))spRelationship.ptr_->GetTypeIndex)(
          &spRelationship.ptr_->ctl::WeakReferenceSourceNoThreadId,
          &spParametricCurveAsIDO);
  v6 = v66;
  if ( v66 < 0 )
    goto LABEL_203;
  v67 = spRelationship.ptr_;
  v68 = spRelationship.ptr_->~ComBase;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spScrollViewer);
  v66 = ((__int64 (__fastcall *)(ctl::WeakReferenceSourceNoThreadId *, _QWORD, ctl::ComPtr<Windows::UI::Xaml::Controls::IScrollViewer> *))v68)(
          &v67->ctl::WeakReferenceSourceNoThreadId,
          0,
          &spScrollViewer);
  v6 = v66;
  if ( v66 < 0
    || (v69 = (DirectUI::DependencyObject *)spScrollViewer.ptr_,
        ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease(&curveCollectionSize),
        v66 = DirectUI::DependencyObject::GetValueByKnownIndex(
                v69,
                ParametricCurve_CurveSegments,
                &GUID_4bd24630_5850_41f0_9bb1_0e82533a4ea3,
                (void **)&curveCollectionSize.ptr_),
        v6 = v66,
        v66 < 0) )
  {
LABEL_203:
    OnFailure_2990_(v66);
    ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease((ctl::ComPtr<DirectUI::KeyboardAcceleratorCollection> *)&spRelationship);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spScrollViewer);
LABEL_205:
    ctl::ComPtr<DirectUI::ParametricCurveSegmentCollection>::InternalRelease(&curveCollectionSize);
    goto $Cleanup_22;
  }
  if ( spRelationship.ptr_ )
  {
    v70 = &spRelationship.ptr_->ctl::forwarder_holder<IWeakReferenceSource,ctl::WeakReferenceSourceNoThreadId>;
    spRelationship.ptr_ = 0;
    v70->m_forwarder.Release(&v70->m_forwarder);
  }
  v71 = spScrollViewer.ptr_;
  if ( *(double *)&spScrollViewer.ptr_ != 0.0 )
  {
    *(double *)&spScrollViewer.ptr_ = 0.0;
    v71->Release(v71);
  }
  v64 = curveCollectionSize.ptr_->Clear(&curveCollectionSize.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>);
  v6 = v64;
  if ( v64 < 0 )
  {
LABEL_204:
    OnFailure_2990_(v64);
    goto LABEL_205;
  }
  p_m_currentStickyHeaderLocations = &this->m_currentStickyHeaderLocations;
  v73 = this->m_currentStickyHeaderLocations._Mypair._Myval2._Myfirst;
  if ( v73 != this->m_currentStickyHeaderLocations._Mypair._Myval2._Mylast )
  {
    if ( this->m_currentHeaderHeight + v73->m_offset > 0.0 )
    {
      spRelationship.ptr_ = 0;
      v97 = ctl::make<DirectUI::ParametricCurveSegment>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurveSegment> >)&spRelationship);
      v6 = v97;
      if ( v97 < 0 )
        goto LABEL_176;
      v97 = DirectUI::ParametricCurveSegment::put_BeginOffset(
              (DirectUI::ParametricCurveSegment *)spRelationship.ptr_,
              0.0);
      v6 = v97;
      if ( v97 < 0
        || (v97 = DirectUI::ParametricCurveSegment::put_ConstantCoefficient(
                    (DirectUI::ParametricCurveSegment *)spRelationship.ptr_,
                    0.0),
            v6 = v97,
            v97 < 0)
        || (v97 = DirectUI::ParametricCurveSegment::put_LinearCoefficient(
                    (DirectUI::ParametricCurveSegment *)spRelationship.ptr_,
                    0.0),
            v6 = v97,
            v97 < 0)
        || (v97 = curveCollectionSize.ptr_->Append(
                    &curveCollectionSize.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>,
                    (Windows::UI::Xaml::Input::IKeyboardAccelerator *)spRelationship.ptr_),
            v6 = v97,
            v97 < 0) )
      {
LABEL_176:
        OnFailure_2990_(v97);
        p_spParametricCurveAsIDO = (ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRelationship;
LABEL_178:
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(p_spParametricCurveAsIDO);
        goto LABEL_205;
      }
      ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRelationship);
    }
    v74 = p_m_currentStickyHeaderLocations->_Mypair._Myval2._Myfirst;
    m_size = 0.0;
    v76 = this->m_currentStickyHeaderLocations._Mypair._Myval2._Mylast;
    v77 = 0.0;
    v78 = 0.0;
    v79 = 0;
    while ( v74 != v76 )
    {
      m_offset = v74->m_offset;
      spParametricCurveAsIDO.ptr_ = 0;
      v86 = m_offset + v74->m_size;
      v87 = m_offset - m_size + this->m_currentHeaderHeight;
      if ( CQuirksMode2::QuirkOnlyPhoneBlue() )
      {
        m_cachedPannableExtent = this->m_cachedPannableExtent;
        if ( v87 > m_cachedPannableExtent )
        {
          v79 = 1;
          v87 = this->m_cachedPannableExtent;
          v86 = m_cachedPannableExtent - v77 + v78;
        }
      }
      v88 = ctl::make<DirectUI::ParametricCurveSegment>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurveSegment> >)&spParametricCurveAsIDO);
      v6 = v88;
      if ( v88 < 0 )
      {
LABEL_142:
        OnFailure_2990_(v88);
        if ( spParametricCurveAsIDO.ptr_ )
        {
          v92 = spParametricCurveAsIDO.ptr_ + 1;
          spParametricCurveAsIDO.ptr_ = 0;
          v92->Release(v92);
        }
        goto LABEL_139;
      }
      v89 = DirectUI::ParametricCurveSegment::put_BeginOffset(
              (DirectUI::ParametricCurveSegment *)spParametricCurveAsIDO.ptr_,
              v87);
      v6 = v89;
      if ( v89 < 0
        || (v89 = DirectUI::ParametricCurveSegment::put_ConstantCoefficient(
                    (DirectUI::ParametricCurveSegment *)spParametricCurveAsIDO.ptr_,
                    COERCE_LONG_DOUBLE(*(_QWORD *)&v86 ^ _xmm)),
            v6 = v89,
            v89 < 0)
        || (v89 = DirectUI::DependencyObject::SetValueByKnownIndex<double>(
                    (DirectUI::DependencyObject *)spParametricCurveAsIDO.ptr_,
                    ParametricCurveSegment_LinearCoefficient,
                    0.0),
            v6 = v89,
            v89 < 0) )
      {
LABEL_177:
        OnFailure_2990_(v89);
        p_spParametricCurveAsIDO = (ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spParametricCurveAsIDO;
        goto LABEL_178;
      }
      v88 = curveCollectionSize.ptr_->Append(
              &curveCollectionSize.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>,
              (Windows::UI::Xaml::Input::IKeyboardAccelerator *)spParametricCurveAsIDO.ptr_);
      v6 = v88;
      if ( v88 < 0 )
        goto LABEL_142;
      if ( v79
        || (v77 = v74->m_offset + this->m_currentHeaderHeight, CQuirksMode2::QuirkOnlyPhoneBlue())
        && v77 > this->m_cachedPannableExtent )
      {
        v100 = (ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spParametricCurveAsIDO;
LABEL_196:
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(v100);
        goto LABEL_108;
      }
      v89 = ctl::make<DirectUI::ParametricCurveSegment>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurveSegment> >)&spParametricCurveAsIDO);
      v6 = v89;
      if ( v89 < 0 )
        goto LABEL_177;
      v89 = DirectUI::ParametricCurveSegment::put_BeginOffset(
              (DirectUI::ParametricCurveSegment *)spParametricCurveAsIDO.ptr_,
              v77);
      v6 = v89;
      if ( v89 < 0 )
        goto LABEL_177;
      v89 = DirectUI::ParametricCurveSegment::put_ConstantCoefficient(
              (DirectUI::ParametricCurveSegment *)spParametricCurveAsIDO.ptr_,
              COERCE_LONG_DOUBLE(*(_QWORD *)&v86 ^ _xmm));
      v6 = v89;
      if ( v89 < 0 )
        goto LABEL_177;
      v89 = DirectUI::DependencyObject::SetValueByKnownIndex<double>(
              (DirectUI::DependencyObject *)spParametricCurveAsIDO.ptr_,
              ParametricCurveSegment_LinearCoefficient,
              -1.0);
      v6 = v89;
      if ( v89 < 0 )
        goto LABEL_177;
      v89 = curveCollectionSize.ptr_->Append(
              &curveCollectionSize.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>,
              (Windows::UI::Xaml::Input::IKeyboardAccelerator *)spParametricCurveAsIDO.ptr_);
      v6 = v89;
      if ( v89 < 0 )
        goto LABEL_177;
      v78 = v86;
      m_size = v74->m_size;
      if ( spParametricCurveAsIDO.ptr_ )
      {
        v90 = spParametricCurveAsIDO.ptr_ + 1;
        spParametricCurveAsIDO.ptr_ = 0;
        v90->Release(v90);
      }
      ++v74;
    }
    if ( p_m_currentStickyHeaderLocations->_Mypair._Myval2._Myfirst == this->m_currentStickyHeaderLocations._Mypair._Myval2._Mylast
      || !CQuirksMode2::QuirkOnlyPhoneBlue() )
    {
      goto LABEL_108;
    }
    v101 = this->m_cachedPannableExtent;
    spRelationship.ptr_ = 0;
    v97 = ctl::make<DirectUI::ParametricCurveSegment>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::ParametricCurveSegment> >)&spRelationship);
    v6 = v97;
    if ( v97 >= 0 )
    {
      v97 = DirectUI::ParametricCurveSegment::put_BeginOffset(
              (DirectUI::ParametricCurveSegment *)spRelationship.ptr_,
              this->m_cachedPannableExtent);
      v6 = v97;
      if ( v97 >= 0 )
      {
        v97 = DirectUI::ParametricCurveSegment::put_ConstantCoefficient(
                (DirectUI::ParametricCurveSegment *)spRelationship.ptr_,
                COERCE_LONG_DOUBLE(COERCE_UNSIGNED_INT64(v101 - v77 + v78) ^ _xmm));
        v6 = v97;
        if ( v97 >= 0 )
        {
          v97 = DirectUI::ParametricCurveSegment::put_LinearCoefficient(
                  (DirectUI::ParametricCurveSegment *)spRelationship.ptr_,
                  0.0);
          v6 = v97;
          if ( v97 >= 0 )
          {
            v97 = curveCollectionSize.ptr_->Append(
                    &curveCollectionSize.ptr_->Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Input::KeyboardAccelerator *>,
                    (Windows::UI::Xaml::Input::IKeyboardAccelerator *)spRelationship.ptr_);
            v6 = v97;
            if ( v97 >= 0 )
            {
              v100 = (ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRelationship;
              goto LABEL_196;
            }
          }
        }
      }
    }
    goto LABEL_176;
  }
LABEL_108:
  p_m_tpItemClippingRelationship = *(DirectUI::TrackerPtr<DirectUI::SecondaryContentRelationship,1,0> **)&bounds.Width;
  v80 = **(_QWORD **)&bounds.Width + 176LL;
  if ( !**(_QWORD **)&bounds.Width )
    v80 = 184;
  v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 56LL))(v80);
  v6 = v81;
  if ( v81 < 0 )
  {
    OnFailure_2990_(v81);
LABEL_139:
    v91 = curveCollectionSize.ptr_;
    if ( !curveCollectionSize.ptr_ )
      goto $Cleanup_22;
    curveCollectionSize.ptr_ = 0;
    v40 = (DirectUI::SecondaryContentRelationship *)&v91->ctl::WeakReferenceSourceNoThreadId;
LABEL_48:
    v40->Release(v40);
    goto $Cleanup_22;
  }
  v82 = (__int64)&p_m_tpItemClippingRelationship->m_trackerReference.m_value[22];
  if ( !p_m_tpItemClippingRelationship->m_trackerReference.m_value )
    v82 = 184;
  v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82 + 64LL))(v82);
  v6 = v64;
  if ( v64 < 0 )
    goto LABEL_204;
  if ( curveCollectionSize.ptr_ )
  {
    v83 = &curveCollectionSize.ptr_->ctl::WeakReferenceSourceNoThreadId;
    curveCollectionSize.ptr_ = 0;
    v83->Release(v83);
  }
LABEL_116:
  if ( LOBYTE(spClip.ptr_) )
  {
    v84 = (__int64)&p_m_tpItemClippingRelationship->m_trackerReference.m_value[22];
    if ( !p_m_tpItemClippingRelationship->m_trackerReference.m_value )
      v84 = 184;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 80LL))(v84, 184);
    v6 = v18;
    if ( v18 < 0 )
      goto LABEL_120;
  }
$Cleanup_22:
  if ( v112.ptr_ )
  {
    v41 = v112.ptr_ + 1;
    v112.ptr_ = 0;
    (*(void (__fastcall **)(ctl::ComPtr<DirectUI::RectangleGeometry> *))&v41->ptr_->m_inFinalRelease)(v41);
  }
  return v6;
}

```

## disassembly

```asm
0x18000baf8  mov     rax, rsp
0x18000bafb  mov     [rax+18h], rbx
0x18000baff  push    rbp
0x18000bb00  push    rsi
0x18000bb01  push    rdi
0x18000bb02  push    r12
0x18000bb04  push    r13
0x18000bb06  push    r14
0x18000bb08  push    r15
0x18000bb0a  lea     rbp, [rax-48h]
0x18000bb0e  sub     rsp, 110h
0x18000bb15  movaps  xmmword ptr [rax-48h], xmm6
0x18000bb19  movaps  xmmword ptr [rax-58h], xmm7
0x18000bb1d  movaps  xmmword ptr [rax-68h], xmm8
0x18000bb22  movaps  xmmword ptr [rax-78h], xmm9
0x18000bb27  movaps  xmmword ptr [rax-88h], xmm10
0x18000bb2f  movaps  xmmword ptr [rax-98h], xmm11
0x18000bb37  movaps  xmmword ptr [rax-0A8h], xmm12
0x18000bb3f  mov     rax, cs:__security_cookie
0x18000bb46  xor     rax, rsp
0x18000bb49  mov     [rbp+40h+var_B0], rax
0x18000bb4d  movss   xmm1, dword ptr [this+668h]
0x18000bb55  xor     r13d, r13d
0x18000bb58  comiss  xmm1, dword ptr [finalSize]
0x18000bb5b  mov     esi, r13d
0x18000bb5e  mov     byte ptr [rsp+140h+spClip.ptr_], manuallyUpdatePosition
0x18000bb63  mov     qword ptr [rbp+40h+bounds.Width], rsi
0x18000bb67  mov     r15b, updateClip
0x18000bb6a  mov     r14, this
0x18000bb6d  ja      short loc_18000BB73
0x18000bb6f  movss   xmm1, dword ptr [finalSize]
0x18000bb73  movss   xmm0, dword ptr [this+66Ch]
0x18000bb7b  comiss  xmm0, dword ptr [finalSize+4]
0x18000bb7f  movss   [rbp+40h+var_B8], xmm1
0x18000bb84  jbe     loc_18000BE20
0x18000bb8a  movss   [rbp+40h+var_B4], xmm0
0x18000bb8f  mov     [rsp+140h+var_D8.ptr_], r13
0x18000bb94  call    ?QuirkShouldUseStickyGroupHeaders@CQuirksMode2@@SA_NXZ; CQuirksMode2::QuirkShouldUseStickyGroupHeaders(void)
0x18000bb99  test    al, al
0x18000bb9b  jz      $Cleanup_22
0x18000bba1  mov     [rsp+140h+spRelationship.ptr_], r13
0x18000bba6  lea     this, [rsp+140h+spRelationship]; this
0x18000bbab  lea     r13, [r14+0B8h]
0x18000bbb2  mov     rax, [r13+0]
0x18000bbb6  mov     rbx, [rax+58h]
0x18000bbba  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18000bbbf  lea     finalSize, [rsp+140h+spRelationship]
0x18000bbc4  mov     this, r13
0x18000bbc7  mov     rax, rbx
0x18000bbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbcf  xor     edi, edi
0x18000bbd1  mov     esi, eax
0x18000bbd3  test    eax, eax
0x18000bbd5  js      loc_18000CE35
0x18000bbdb  mov     this, [rsp+140h+spRelationship.ptr_]
0x18000bbe0  mov     edx, edi
0x18000bbe2  mov     [rsp+140h+spRelationship.ptr_], finalSize
0x18000bbe7  lea     rax, [this-0C0h]
0x18000bbee  neg     this
0x18000bbf1  sbb     rbx, rbx
0x18000bbf4  and     rbx, rax
0x18000bbf7  mov     rax, [rsp+140h+var_D8.ptr_]
0x18000bbfc  cmp     rax, rbx
0x18000bbff  jz      short loc_18000BC28
0x18000bc01  test    rax, rax
0x18000bc04  jz      short loc_18000BC20
0x18000bc06  lea     this, [rax+8]
0x18000bc0a  mov     [rsp+140h+var_D8.ptr_], rdi
0x18000bc0f  mov     rax, [this]
0x18000bc12  mov     rax, [rax+10h]
0x18000bc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc1b  mov     finalSize, [rsp+140h+spRelationship.ptr_]
0x18000bc20  mov     rax, rbx
0x18000bc23  mov     [rsp+140h+var_D8.ptr_], rbx
0x18000bc28  test    finalSize, finalSize
0x18000bc2b  jz      short loc_18000BC46
0x18000bc2d  mov     [rsp+140h+spRelationship.ptr_], rdi
0x18000bc32  mov     this, finalSize
0x18000bc35  mov     rax, [finalSize]
0x18000bc38  mov     rax, [rax+10h]
0x18000bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc41  mov     rax, [rsp+140h+var_D8.ptr_]
0x18000bc46  mov     ebx, 1
0x18000bc4b  test    rax, rax
0x18000bc4e  jz      loc_18000C7D3
0x18000bc54  call    ?QuirkOnlyPhoneBlue@CQuirksMode2@@SA_NXZ; CQuirksMode2::QuirkOnlyPhoneBlue(void)
0x18000bc59  xorps   xmm11, xmm11
0x18000bc5d  test    al, al
0x18000bc5f  jnz     loc_18000C825
0x18000bc65  mov     this, [rsp+140h+var_D8.ptr_]
0x18000bc6a  lea     finalSize, [rbp+40h+bounds.Width]
0x18000bc6e  movups  xmm0, xmmword ptr [rbp+40h+bounds.Width]
0x18000bc72  add     this, 0C0h
0x18000bc79  movups  xmmword ptr [rbp+40h+bounds.Width], xmm0
0x18000bc7d  mov     rax, [this]
0x18000bc80  mov     rax, [rax+38h]
0x18000bc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc89  mov     esi, eax
0x18000bc8b  test    eax, eax
0x18000bc8d  js      loc_18000C712
0x18000bc93  lea     r12, [r14+798h]
0x18000bc9a  mov     [rsp+140h+spRelationship.ptr_], rdi
0x18000bc9f  lea     this, [rsp+140h+spRelationship]; ppNewInstance
0x18000bca4  cmp     [r12], rdi
0x18000bca8  jz      loc_18000BE9F
0x18000bcae  mov     rdi, [rsp+140h+var_D8.ptr_]
0x18000bcb3  mov     rax, [rdi+0B8h]
0x18000bcba  mov     rbx, [rax+30h]
0x18000bcbe  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18000bcc3  lea     finalSize, [rsp+140h+spRelationship]
0x18000bcc8  mov     rax, rbx
0x18000bccb  lea     this, [rdi+0B8h]
0x18000bcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd7  xor     edi, edi
0x18000bcd9  mov     esi, eax
0x18000bcdb  test    eax, eax
0x18000bcdd  js      loc_18000C8C0
0x18000bce3  mov     rax, [r12]
0x18000bce7  lea     this, [rax-8]
0x18000bceb  neg     rax
0x18000bcee  sbb     finalSize, finalSize
0x18000bcf1  and     finalSize, this
0x18000bcf4  jz      loc_18000C8B8
0x18000bcfa  add     finalSize, 8; pSecond
0x18000bcfe  mov     this, [rsp+140h+spRelationship.ptr_]; pFirst
0x18000bd03  call    ??$are_equal@UIInspectable@@U1@@ctl@@YA_NPEAUIInspectable@@0@Z; ctl::are_equal<IInspectable,IInspectable>(IInspectable *,IInspectable *)
0x18000bd08  mov     this, [rsp+140h+spRelationship.ptr_]
0x18000bd0d  test    al, al
0x18000bd0f  mov     eax, 1
0x18000bd14  movzx   r15d, r15b
0x18000bd18  cmovz   r15d, eax
0x18000bd1c  test    this, this
0x18000bd1f  jz      short loc_18000BD32
0x18000bd21  mov     [rsp+140h+spRelationship.ptr_], rdi
0x18000bd26  mov     rax, [this]
0x18000bd29  mov     rax, [rax+10h]
0x18000bd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd32  lea     rbx, [r14+780h]
0x18000bd39  mov     rax, [rbx]
0x18000bd3c  cmp     rax, [rbx+8]
0x18000bd40  jz      short loc_18000BD46
0x18000bd42  mov     [rbx+8], rax
0x18000bd46  movsxd  finalSize, dword ptr [r14+3C8h]; _Newcapacity
0x18000bd4d  mov     this, rbx; this
0x18000bd50  call    ?reserve@?$vector@UStickyHeaderInfo@ModernCollectionBasePanel@DirectUI@@V?$allocator@UStickyHeaderInfo@ModernCollectionBasePanel@DirectUI@@@std@@@std@@QEAAX_K@Z; std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo>::reserve(unsigned __int64)
0x18000bd55  cmp     edi, [r14+3C8h]
0x18000bd5c  jge     loc_18000BE2A
0x18000bd62  lea     this, [rsp+140h+spRelationship]; this
0x18000bd67  mov     [rsp+140h+spRelationship.ptr_], 0
0x18000bd70  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18000bd75  lea     this, [r14+378h]; this
0x18000bd7c  mov     r8d, edi; indexInValidElements
0x18000bd7f  lea     r9, [rsp+140h+spRelationship]; pspElement
0x18000bd84  mov     edx, 1; type
0x18000bd89  call    ?GetElementAtValidIndex@ContainerManager@ModernCollectionBasePanel@DirectUI@@QEBAJW4ElementType@Controls@Xaml@UI@Windows@@HPEAV?$ComPtr@UIUIElement@Xaml@UI@Windows@@@ctl@@@Z; DirectUI::ModernCollectionBasePanel::ContainerManager::GetElementAtValidIndex(Windows::UI::Xaml::Controls::ElementType,int,ctl::ComPtr<Windows::UI::Xaml::IUIElement> *)
0x18000bd8e  mov     esi, eax
0x18000bd90  test    eax, eax
0x18000bd92  js      loc_18000BEEF
0x18000bd98  mov     this, [rsp+140h+spRelationship.ptr_]
0x18000bd9d  test    this, this
0x18000bda0  jz      short loc_18000BE19
0x18000bda2  lea     rax, [this+0A0h]
0x18000bda9  mov     edx, 158h
0x18000bdae  cmovz   rax, finalSize
0x18000bdb2  mov     finalSize, [rbx+8]; _Whereptr
0x18000bdb6  mov     this, [rax]
0x18000bdb9  mov     eax, [this+18h]
0x18000bdbc  movss   xmm0, dword ptr [this+1Ch]
0x18000bdc1  movss   xmm1, dword ptr [this+24h]
0x18000bdc6  mov     [rbp+40h+bounds.Width], eax
0x18000bdc9  mov     eax, [this+20h]
0x18000bdcc  mov     [rbp+40h+var_B8], eax
0x18000bdcf  movss   [rbp+40h+bounds.Height], xmm0
0x18000bdd4  movss   [rbp+40h+var_B4], xmm1
0x18000bdd9  cmp     finalSize, [rbx+10h]
0x18000bddd  jz      loc_18000C8EA
0x18000bde3  cvtps2pd xmm0, xmm0
0x18000bde6  lea     rax, [finalSize+10h]
0x18000bdea  mov     [rbx+8], rax
0x18000bdee  cvtps2pd xmm1, xmm1
0x18000bdf1  movsd   qword ptr [finalSize], xmm0
0x18000bdf5  movsd   qword ptr [finalSize+8], xmm1
0x18000bdfa  mov     this, [rsp+140h+spRelationship.ptr_]
0x18000bdff  test    this, this
0x18000be02  jz      short loc_18000BE19
0x18000be04  mov     [rsp+140h+spRelationship.ptr_], 0
0x18000be0d  mov     rax, [this]
0x18000be10  mov     rax, [rax+10h]
0x18000be14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be19  inc     edi
0x18000be1b  jmp     loc_18000BD55
0x18000be20  movss   xmm0, dword ptr [finalSize+4]
0x18000be25  jmp     loc_18000BB8A
0x18000be2a  lea     r11, [r14+768h]
0x18000be31  mov     finalSize, rbx; _Right
0x18000be34  mov     this, r11; _Left
0x18000be37  call    ??$?9UStickyHeaderInfo@ModernCollectionBasePanel@DirectUI@@V?$allocator@UStickyHeaderInfo@ModernCollectionBasePanel@DirectUI@@@std@@@std@@YA_NAEBV?$vector@UStickyHeaderInfo@ModernCollectionBasePanel@DirectUI@@V?$allocator@UStickyHeaderInfo@ModernCollectionBasePanel@DirectUI@@@std@@@0@0@Z; std::operator!=<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo,std::allocator<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo>>(std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo> const &,std::vector<DirectUI::ModernCollectionBasePanel::StickyHeaderInfo> const &)
0x18000be3c  xor     edi, edi
0x18000be3e  test    al, al
0x18000be40  jnz     loc_18000C8FF
0x18000be46  lea     rbx, [r14+7B0h]
0x18000be4d  mov     edx, 0B8h
0x18000be52  mov     qword ptr [rbp+40h+bounds.Width], rbx
0x18000be56  cmp     [rbx], rdi
0x18000be59  jz      loc_18000BF7F
0x18000be5f  xor     r13d, r13d
0x18000be62  test    r15b, r15b
0x18000be65  jz      loc_18000C53E
0x18000be6b  mov     r8, [rsp+140h+var_D8.ptr_]
0x18000be70  mov     [rsp+140h+curveCollectionSize], r13
0x18000be75  mov     rax, [r8+0B8h]
0x18000be7c  mov     r9, [rax+38h]
0x18000be80  mov     rax, [r12]
0x18000be84  lea     this, [rax-8]
0x18000be88  neg     rax
0x18000be8b  sbb     finalSize, finalSize
0x18000be8e  and     finalSize, this
0x18000be91  jnz     loc_18000C313
0x18000be97  mov     finalSize, r13
0x18000be9a  jmp     loc_18000C31A
0x18000be9f  call    ??$make@VCompositeTransform@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VCompositeTransform@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::CompositeTransform>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::CompositeTransform>>)
0x18000bea4  mov     esi, eax
0x18000bea6  test    eax, eax
0x18000bea8  js      loc_18000CE13
0x18000beae  lea     this, [r14+8]; this
0x18000beb2  mov     finalSize, r12; pTrackerPtr
0x18000beb5  mov     r15b, bl
0x18000beb8  call    ?RegisterPtr@WeakReferenceSourceNoThreadId@ctl@@AEAAXQEAVTrackerTargetReference@DirectUI@@@Z; ctl::WeakReferenceSourceNoThreadId::RegisterPtr(DirectUI::TrackerTargetReference * const)
0x18000bebd  mov     finalSize, [rsp+140h+spRelationship.ptr_]
0x18000bec2  mov     this, r12; this
0x18000bec5  test    finalSize, finalSize
0x18000bec8  jnz     loc_18000C8D6
0x18000bece  xor     r8d, r8d; bForceLoopback
0x18000bed1  mov     dl, bl; bEnsureTrackerTarget
0x18000bed3  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18000bed8  mov     this, [rsp+140h+spRelationship.ptr_]
0x18000bedd  test    this, this
0x18000bee0  jz      loc_18000BD32
0x18000bee6  add     this, 8
0x18000beea  jmp     loc_18000BD21
0x18000beef  mov     ecx, eax; failedFrameHR
0x18000bef1  call    OnFailure_2990_
0x18000bef6  mov     this, [rsp+140h+spRelationship.ptr_]
0x18000befb  xor     r13d, r13d
0x18000befe  test    this, this
0x18000bf01  jz      short $Cleanup_22
0x18000bf03  mov     [rsp+140h+spRelationship.ptr_], r13
0x18000bf08  mov     rax, [this]
0x18000bf0b  mov     rax, [rax+10h]
0x18000bf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf14  mov     this, [rsp+140h+var_D8.ptr_]
0x18000bf19  test    this, this
0x18000bf1c  jz      short loc_18000BF33
0x18000bf1e  add     this, 8
0x18000bf22  mov     [rsp+140h+var_D8.ptr_], r13
0x18000bf27  mov     rax, [this]
0x18000bf2a  mov     rax, [rax+10h]
0x18000bf2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf33  mov     eax, esi
0x18000bf35  mov     this, [rbp+40h+var_B0]
0x18000bf39  xor     this, rsp; StackCookie
0x18000bf3c  call    __security_check_cookie
0x18000bf41  lea     r11, [rsp+140h+var_30]
0x18000bf49  mov     rbx, [r11+50h]
0x18000bf4d  movaps  xmm6, xmmword ptr [r11-10h]
0x18000bf52  movaps  xmm7, xmmword ptr [r11-20h]
0x18000bf57  movaps  xmm8, xmmword ptr [r11-30h]
0x18000bf5c  movaps  xmm9, xmmword ptr [r11-40h]
0x18000bf61  movaps  xmm10, xmmword ptr [r11-50h]
0x18000bf66  movaps  xmm11, xmmword ptr [r11-60h]
0x18000bf6b  movaps  xmm12, xmmword ptr [r11-70h]
0x18000bf70  mov     rsp, r11
0x18000bf73  pop     r15
0x18000bf75  pop     r14
0x18000bf77  pop     r13
0x18000bf79  pop     r12
0x18000bf7b  pop     rdi
0x18000bf7c  pop     rsi
0x18000bf7d  pop     rbp
0x18000bf7e  retn
0x18000bf7f  lea     this, [r14+608h]; this
0x18000bf86  mov     [rsp+140h+curveCollectionSize], rdi
0x18000bf8b  lea     finalSize, [rsp+140h+spCurveSegment]; ptr
0x18000bf90  mov     [rsp+140h+spCurveSegment.ptr_], rdi
0x18000bf95  mov     [rsp+140h+spParametricCurveAsIDO.ptr_], rdi
0x18000bf9a  call    ??$As@UIScrollViewer@Controls@Xaml@UI@Windows@@@WeakRefPtr@ctl@@QEAAJV?$ComPtrRef@V?$ComPtr@UIScrollViewer@Controls@Xaml@UI@Windows@@@ctl@@@Internal@1@@Z; ctl::WeakRefPtr::As<Windows::UI::Xaml::Controls::IScrollViewer>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IScrollViewer>>)
0x18000bf9f  mov     esi, eax
0x18000bfa1  test    eax, eax
0x18000bfa3  js      loc_18000CDE0
0x18000bfa9  lea     this, [rsp+140h+curveCollectionSize]; ppNewInstance
0x18000bfae  call    ??$make@VSecondaryContentRelationship@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VSecondaryContentRelationship@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::SecondaryContentRelationship>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::SecondaryContentRelationship>>)
0x18000bfb3  mov     esi, eax
0x18000bfb5  test    eax, eax
0x18000bfb7  js      loc_18000CE0A
0x18000bfbd  mov     rax, [rsp+140h+spCurveSegment.ptr_]
0x18000bfc2  lea     this, [rax-238h]
0x18000bfc9  neg     rax
0x18000bfcc  sbb     finalSize, finalSize
0x18000bfcf  and     finalSize, this
0x18000bfd2  jz      loc_18000C744
  ... truncated ...
```
