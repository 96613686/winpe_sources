# DirectUI::VisualStateManager::GoToStateImpl(Windows::UI::Xaml::Controls::IControl *,VisualStateToken,HSTRING__ *,int,uchar,uchar *)

- ea: `0x18007972c`
- end: `0x18007a1f8`
- name: `?GoToStateImpl@VisualStateManager@DirectUI@@SAJPEAUIControl@Controls@Xaml@UI@Windows@@VVisualStateToken@@PEAUHSTRING__@@HEPEAE@Z`
- size: `2764`
- prototype: `HRESULT __fastcall(Windows::UI::Xaml::Controls::IControl *pControl, VisualStateToken visualStateToken, HSTRING__ *hStateName, int groupIndex, unsigned __int8 bUseTransitions, unsigned __int8 *pbReturnValue)`
- caller_count: `9`
- callee_count: `36`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180079624`
- `0x18010a3a8`
- `0x1803db1c0`
- `0x1803db670`
- `0x1803db99c`
- `0x1804c94c0`
- `0x1804fd87c`
- `0x18054ee50`
- `0x18090e4f0`

## callees

- `0x180004bc0`
- `0x180004d2c`
- `0x1800053b0`
- `0x18000616c`
- `0x18001f3c0`
- `0x180045d64`
- `0x18004bfd0`
- `0x18005c640`
- `0x18006c2b0`
- `0x18006cfd0`
- `0x18007972c`
- `0x18007a5d4`
- `0x18007d590`
- `0x18007d630`
- `0x1800e4b00`
- `0x1800f3fb4`
- `0x1800fe130`
- `0x180108820`
- `0x180131190`
- `0x1801800b8`
- `0x1801df610`
- `0x1801e4554`
- `0x1801e5458`
- `0x1802499e4`
- `0x1802ab568`
- `0x1802ab698`
- `0x18031a0e4`
- `0x18033d2ec`
- `0x1805d9964`
- `0x18061a9b4`
- `0x180687a78`
- `0x180688828`
- `0x18069f6ac`
- `0x1807024a0`
- `0x1809ecb30`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079801`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079870`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079c79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079d2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a0f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079c79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079d2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a0f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007977e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007977e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800799f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180079a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180079ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800799f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180079a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180079ee7`

## pseudocode

```c
__int64 __fastcall DirectUI::VisualStateManager::GoToStateImpl(
        CDependencyObject *pControl,
        VisualStateToken visualStateToken,
        CDependencyObject *hStateName,
        int groupIndex,
        unsigned __int8 bUseTransitions,
        const xstring_ptr_storage *pbReturnValue)
{
  const xstring_ptr_storage *Storage; // r13
  DirectUI::DXamlCore *Value; // rsi
  int v10; // r14d
  HRESULT v11; // ecx
  HSTRING__ *hstring; // rcx
  Windows::UI::Xaml::Controls::IControl *p_m_pInheritedProperties; // r15
  int v14; // ebx
  Windows::UI::Xaml::Controls::IControl_vtbl *v15; // rcx
  CDependencyObject *v16; // rax
  CDependencyObject *v17; // rbx
  HRESULT PeerPrivate; // eax
  HRESULT v19; // esi
  DirectUI::DependencyObject *ptr; // r13
  ctl::WeakReferenceSourceNoThreadId *v21; // r14
  __int64 (__fastcall ***v22)(_QWORD, GUID *, ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> > *); // rcx
  HRESULT v23; // eax
  HRESULT v24; // ebx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> *v25; // rcx
  Windows::UI::Xaml::IVisualStateManager *v26; // rcx
  DirectUI::DependencyObject *v27; // rsi
  HRESULT ValueByKnownIndex; // eax
  Windows::UI::Xaml::IVisualStateManager *v29; // rcx
  Windows::UI::Xaml::IFrameworkElement *v30; // rcx
  HSTRING__ *v32; // r14
  _QWORD *v33; // rdi
  std::vector<ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *,std::allocator<ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *> > *v34; // rax
  ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > **Mylast; // rdx
  _MCGEN_TRACE_CONTEXT *v36; // rcx
  __int64 v37; // r8
  HRESULT v38; // eax
  __int64 v39; // r8
  HRESULT v40; // eax
  Windows::UI::Xaml::IVisualStateManager *v41; // rcx
  Windows::UI::Xaml::IFrameworkElement *v42; // rcx
  void (*Release)(void); // rax
  HRESULT v44; // eax
  HRESULT v45; // eax
  Windows::UI::Xaml::IVisualStateManager *v46; // rcx
  Windows::UI::Xaml::IFrameworkElement *v47; // rcx
  std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *FailFast; // rax
  HRESULT v49; // ecx
  CDependencyObject *v50; // rbx
  DirectUI::DependencyObject *v51; // r13
  CControl *v52; // rax
  xref_ptr<CDependencyObject> *v53; // rax
  CVisualState *m_ptr; // rdx
  Windows::UI::Xaml::IVisualState *v55; // rcx
  Windows::UI::Xaml::IVisualStateGroup *v56; // rcx
  const wchar_t *StringRawBuffer; // rax
  HRESULT State; // eax
  unsigned int v59; // esi
  HRESULT VisualStateGroupsStatic; // eax
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> *v61; // r14
  HRESULT (__fastcall *GetAt)(Windows::Foundation::Collections::IVector_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Xaml::VisualStateGroup *,Windows::UI::Xaml::IVisualStateGroup *>,1> *, unsigned int, Windows::UI::Xaml::IVisualStateGroup **); // rsi
  DirectUI::DXamlCore *Current; // rdi
  Windows::ApplicationModel::Activation::ITileActivatedInfo *v64; // rbx
  Windows::UI::Xaml::IVisualState *v65; // rdi
  HRESULT (__fastcall *get_Name)(Windows::UI::Xaml::IVisualState *, HSTRING__ **); // rbx
  CControl *Handle; // rax
  Windows::Internal::_StringDetail::dummy_t v68; // r8
  KnownTypeIndex Context; // [rsp+20h] [rbp-89h]
  unsigned int useTransitions; // [rsp+30h] [rbp-79h]
  unsigned __int8 bWentToState[8]; // [rsp+50h] [rbp-59h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spRoot; // [rsp+58h] [rbp-51h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IVisualStateManager> spCustomVsm; // [rsp+60h] [rbp-49h] BYREF
  Windows::Internal::String stateName; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int8 bIgnored[8]; // [rsp+70h] [rbp-39h] BYREF
  ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> > spGroups; // [rsp+78h] [rbp-31h] BYREF
  ctl::ComPtr<DirectUI::DependencyObject> spVisualStatePeer; // [rsp+80h] [rbp-29h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IVisualState> spState; // [rsp+88h] [rbp-21h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IVisualStateGroup> spGroup; // [rsp+90h] [rbp-19h] BYREF
  xstring_ptr name; // [rsp+98h] [rbp-11h] BYREF
  xref_ptr<CDependencyObject> visualState; // [rsp+A0h] [rbp-9h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo> v82; // [rsp+A8h] [rbp-1h] BYREF
  xref_ptr<CDependencyObject> result; // [rsp+B0h] [rbp+7h] BYREF

  Storage = pbReturnValue;
  Value = 0;
  name.m_encodedStorage.Storage = pbReturnValue;
  spRoot.ptr_ = 0;
  spCustomVsm.ptr_ = 0;
  bWentToState[0] = 0;
  stateName._hstring = 0;
  v10 = groupIndex;
  spGroups.ptr_ = 0;
  LODWORD(v82.ptr_) = groupIndex;
  result.m_ptr = hStateName;
  if ( WindowsDuplicateString((HSTRING)hStateName, (HSTRING *)&spGroups) >= 0 )
  {
    hstring = stateName._hstring;
    stateName._hstring = (HSTRING__ *)spGroups.ptr_;
    WindowsDeleteString(hstring);
  }
  if ( pControl )
  {
    if ( !pbReturnValue )
    {
      OnNewFailure_1172_(v11);
      v59 = -2147467261;
      goto LABEL_140;
    }
    p_m_pInheritedProperties = (Windows::UI::Xaml::Controls::IControl *)&pControl[-5].m_pInheritedProperties;
    LOBYTE(pbReturnValue->Buffer) = 0;
    spGroups.ptr_ = 0;
    if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x8000000) != 0 )
      DirectUI::ApiEtwStart(&pControl[-5].m_pInheritedProperties, Control_GetImplementationRoot);
    if ( (BYTE6(p_m_pInheritedProperties[8].__vftable) & 2) != 0 )
      v14 = (int)p_m_pInheritedProperties[18].__vftable;
    else
      v14 = *(_DWORD *)(*(_QWORD *)p_m_pInheritedProperties[18].Release + 188LL);
    if ( v14 == GetCurrentThreadId() )
    {
      v15 = 0;
      if ( (BYTE6(p_m_pInheritedProperties[8].__vftable) & 2) == 0 )
        v15 = p_m_pInheritedProperties[18].__vftable;
      v16 = (CDependencyObject *)(*((__int64 (__fastcall **)(Windows::UI::Xaml::Controls::IControl_vtbl *))v15->QueryInterface
                                  + 102))(v15);
      v17 = v16;
      if ( v16 )
      {
        CDependencyObject::Release(v16);
        CDependencyObject::AddRef(v17);
      }
      spVisualStatePeer.ptr_ = 0;
      xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&spVisualStatePeer);
      if ( !v17 )
      {
        spGroups.ptr_ = 0;
LABEL_22:
        v24 = 0;
        goto LABEL_23;
      }
      spVisualStatePeer.ptr_ = 0;
      if ( DXamlInstanceStorage::g_dwTlsIndex == -1 )
      {
        OnNewFailure_2955_(-1);
      }
      else
      {
        Value = (DirectUI::DXamlCore *)TlsGetValue(DXamlInstanceStorage::g_dwTlsIndex);
        if ( !Value && GetLastError() )
          OnFailure_977_(v49);
      }
      v17->GetTypeIndex(v17);
      PeerPrivate = DirectUI::DXamlCore::GetPeerPrivate(
                      Value,
                      0,
                      v17,
                      CreateIfNecessary,
                      Context,
                      0,
                      useTransitions,
                      0,
                      &spVisualStatePeer.ptr_);
      v19 = PeerPrivate;
      if ( PeerPrivate < 0 )
      {
        OnFailure_2990_(PeerPrivate);
        if ( spVisualStatePeer.ptr_ )
          spVisualStatePeer.ptr_->Release(&spVisualStatePeer.ptr_->ctl::WeakReferenceSourceNoThreadId);
        CDependencyObject::Release(v17);
      }
      else
      {
        ptr = spVisualStatePeer.ptr_;
        v21 = &spVisualStatePeer.ptr_->ctl::WeakReferenceSourceNoThreadId;
        v22 = (__int64 (__fastcall ***)(_QWORD, GUID *, ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> > *))((__int64)&spVisualStatePeer.ptr_->ctl::WeakReferenceSourceNoThreadId & -(__int64)(spVisualStatePeer.ptr_ != 0));
        v23 = (**v22)(v22, &GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1, &spGroups);
        v19 = v23;
        if ( v23 >= 0 )
        {
          if ( ptr )
            v21->Release(v21);
          CDependencyObject::Release(v17);
          v10 = (int)v82.ptr_;
          Storage = name.m_encodedStorage.Storage;
          goto LABEL_22;
        }
        OnFailure_2990_(v23);
        if ( ptr )
          v21->Release(v21);
        CDependencyObject::Release(v17);
        v10 = (int)v82.ptr_;
        Storage = name.m_encodedStorage.Storage;
      }
      v24 = v19;
      OnFailure_2990_(v19);
    }
    else
    {
      v24 = -2147417842;
      OnFailure_2990_(-2147417842);
    }
LABEL_23:
    if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x8000000) != 0 )
      DirectUI::ApiEtwStop(&pControl[-5].m_pInheritedProperties, v24);
    if ( v24 < 0 )
    {
      OnFailure_2990_(v24);
    }
    else
    {
      v24 = 0;
      if ( spGroups.ptr_ )
        v24 = spGroups.ptr_->QueryInterface(spGroups.ptr_, &GUID_a391d09b_4a99_4b7c_9d8d_6fa5d01f6fbf, (void **)&spRoot);
      if ( v24 < 0 )
        OnFailure_2990_(v24);
    }
    v25 = spGroups.ptr_;
    if ( spGroups.ptr_ )
    {
      spGroups.ptr_ = 0;
      v25->Release(v25);
    }
    if ( v24 < 0 )
    {
      OnFailure_2990_(v24);
      if ( stateName._hstring )
        WindowsDeleteString(stateName._hstring);
      v46 = spCustomVsm.ptr_;
      if ( spCustomVsm.ptr_ )
      {
        spCustomVsm.ptr_ = 0;
        v46->Release(v46);
      }
      v47 = spRoot.ptr_;
      if ( !spRoot.ptr_ )
        return (unsigned int)v24;
      spRoot.ptr_ = 0;
      Release = (void (*)(void))v47->Release;
      goto LABEL_90;
    }
    if ( !spRoot.ptr_ )
    {
LABEL_43:
      if ( stateName._hstring )
        WindowsDeleteString(stateName._hstring);
      v29 = spCustomVsm.ptr_;
      if ( spCustomVsm.ptr_ )
      {
        spCustomVsm.ptr_ = 0;
        v29->Release(v29);
      }
      v30 = spRoot.ptr_;
      if ( spRoot.ptr_ )
      {
        spRoot.ptr_ = 0;
        v30->Release(v30);
      }
      return 0;
    }
    v26 = spCustomVsm.ptr_;
    if ( spCustomVsm.ptr_ )
    {
      spCustomVsm.ptr_ = 0;
      v26->Release(v26);
    }
    v27 = (DirectUI::DependencyObject *)((__int64)&spRoot.ptr_[-44] & -(__int64)(spRoot.ptr_ != 0));
    if ( !v27
      && (ValueByKnownIndex = DirectUI::ErrorHelper::OriginateError(-2147024809, 7u, L"element"),
          v24 = ValueByKnownIndex,
          ValueByKnownIndex < 0)
      || (ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                                v27,
                                VisualStateManager_CustomVisualStateManager,
                                &GUID_6fda9f9a_6fab_4112_9258_1006a3c3476e,
                                (void **)&spCustomVsm.ptr_),
          v24 = ValueByKnownIndex,
          ValueByKnownIndex < 0) )
    {
      OnFailure_2990_(ValueByKnownIndex);
      OnFailure_2990_(v24);
      goto LABEL_69;
    }
    if ( !spCustomVsm.ptr_ )
    {
      if ( WindowsIsStringEmpty(stateName._hstring) )
      {
        Handle = (CControl *)DirectUI::DependencyObject::GetHandle((DirectUI::DependencyObject *)&pControl[-5].m_pInheritedProperties);
        CVisualStateManager2::GetVisualStateName(&name, Handle, visualStateToken);
        result.m_ptr = (CDependencyObject *)xstring_ptr_view::GetBuffer(&name);
        Windows::Internal::String::Initialize<unsigned short const *>(&stateName, (const wchar_t *const *)&result, v68);
        xstring_ptr::~xstring_ptr(&name);
      }
      if ( !WindowsIsStringEmpty(stateName._hstring) )
      {
        v32 = stateName._hstring;
        result.m_ptr = pControl;
        v33 = (_QWORD *)((__int64)&spRoot.ptr_[-44] & -(__int64)(spRoot.ptr_ != 0));
        v34 = (std::vector<ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *,std::allocator<ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *> > *)v33[55];
        if ( !v34 )
        {
          FailFast = (std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)XcpAllocation::OSMemoryAllocateFailFast(0x18u);
          if ( FailFast )
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>(FailFast);
          else
            v34 = 0;
          v33[55] = v34;
        }
        Mylast = v34->_Mypair._Myval2._Mylast;
        if ( Mylast == v34->_Mypair._Myval2._Myend )
        {
          std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(
            v34,
            Mylast,
            (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *const *)&result);
        }
        else
        {
          *Mylast = (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *)pControl;
          ++v34->_Mypair._Myval2._Mylast;
        }
        name.m_encodedStorage.Storage = 0;
        if ( (*(__int64 (__fastcall **)(_QWORD *))(v33[1] + 64LL))(v33 + 1) )
        {
          if ( v33
            && (v44 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, xstring_ptr *))v33[1])(
                        v33 + 1,
                        &GUID_cb5cd2b9_e3b4_458c_b64e_1434fd1bd88a,
                        &name),
                v24 = v44,
                v44 < 0) )
          {
            OnFailure_2990_(v44);
          }
          else
          {
            LOBYTE(v37) = bUseTransitions;
            v45 = (*(__int64 (__fastcall **)(const xstring_ptr_storage *, HSTRING__ *, __int64, unsigned __int8 *))(*(_QWORD *)name.m_encodedStorage.RuntimeStringHandleMarker + 48LL))(
                    name.m_encodedStorage.Storage,
                    v32,
                    v37,
                    bWentToState);
            v24 = v45;
            if ( v45 < 0 )
              OnFailure_2990_(v45);
          }
        }
        else
        {
          if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x8000000) != 0 )
            McTemplateMofU0xh(v36, &ApiFunctionCallStart, &ApiFunctionCallId, (const unsigned __int64)v33, 0x52u);
          if ( (v32 || (v38 = DirectUI::ErrorHelper::OriginateError(-2147024809, 9u, L"stateName"), v24 = v38, v38 >= 0))
            && (v38 = DirectUI::DependencyObject::CheckThread((DirectUI::DependencyObject *)(v33 + 1)),
                v24 = v38,
                v38 >= 0) )
          {
            LOBYTE(v39) = bUseTransitions;
            v40 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING__ *, __int64, unsigned __int8 *))(*v33 + 632LL))(
                    v33,
                    v32,
                    v39,
                    bWentToState);
            v24 = v40;
            if ( v40 < 0 )
              OnFailure_2990_(v40);
          }
          else
          {
            OnFailure_2990_(v38);
          }
          if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x8000000) != 0 )
            DirectUI::ApiEtwStop(v33, v24);
          if ( v24 < 0 )
            OnFailure_2990_(v24);
        }
        if ( name.m_encodedStorage.Storage )
          (*(void (__fastcall **)(const xstring_ptr_storage *))(*(_QWORD *)name.m_encodedStorage.RuntimeStringHandleMarker
                                                              + 16LL))(name.m_encodedStorage.Storage);
        *(_QWORD *)(v33[55] + 8LL) -= 8LL;
        if ( v24 < 0 )
        {
          OnFailure_2990_(v24);
LABEL_69:
          if ( stateName._hstring )
            WindowsDeleteString(stateName._hstring);
          v41 = spCustomVsm.ptr_;
          if ( spCustomVsm.ptr_ )
          {
            spCustomVsm.ptr_ = 0;
            v41->Release(v41);
          }
          v42 = spRoot.ptr_;
          if ( !spRoot.ptr_ )
            return (unsigned int)v24;
          spRoot.ptr_ = 0;
          Release = (void (*)(void))v42->Release;
LABEL_90:
          Release();
          return (unsigned int)v24;
        }
      }
      LOBYTE(Storage->Buffer) = bWentToState[0];
      goto LABEL_43;
    }
    spGroup.ptr_ = 0;
    v50 = 0;
    visualState.m_ptr = 0;
    v51 = 0;
    spState.ptr_ = 0;
    bIgnored[0] = 0;
    spVisualStatePeer.ptr_ = 0;
    if ( v10 != -1 )
    {
      spGroups.ptr_ = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroups);
      VisualStateGroupsStatic = DirectUI::VisualStateManagerFactory::GetVisualStateGroupsStatic(
                                  spRoot.ptr_,
                                  &spGroups.ptr_);
      v59 = VisualStateGroupsStatic;
      if ( VisualStateGroupsStatic < 0
        || (v61 = spGroups.ptr_,
            GetAt = spGroups.ptr_->GetAt,
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroup),
            VisualStateGroupsStatic = GetAt(v61, (unsigned int)v82.ptr_, &spGroup.ptr_),
            v59 = VisualStateGroupsStatic,
            VisualStateGroupsStatic < 0) )
      {
        OnFailure_2990_(VisualStateGroupsStatic);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroups);
LABEL_129:
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spVisualStatePeer);
        xref_ptr<CDependencyObject>::DecrementRefCount(&visualState);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spState);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroup);
LABEL_140:
        Windows::Internal::String::~String(&stateName);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCustomVsm);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spRoot);
        return v59;
      }
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroups);
    }
    if ( visualStateToken.m_value != -1 || WindowsIsStringEmpty(stateName._hstring) )
    {
      v52 = (CControl *)DirectUI::DependencyObject::GetHandle((DirectUI::DependencyObject *)&pControl[-5].m_pInheritedProperties);
      v53 = CVisualStateManager2::GetVisualState(&result, v52, visualStateToken);
      if ( &visualState != v53 )
      {
        m_ptr = (CVisualState *)v53->m_ptr;
        v53->m_ptr = 0;
        xref_ptr<CMediaPlayerPresenter>::attach<CMediaPlayerPresenter>((xref_ptr<CVisualState> *)&visualState, m_ptr);
        v50 = visualState.m_ptr;
      }
      xref_ptr<CDependencyObject>::DecrementRefCount(&result);
      if ( !v50 )
        goto LABEL_108;
      Current = DirectUI::DXamlCore::GetCurrent();
      ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spVisualStatePeer);
      State = DirectUI::DXamlCore::GetPeerPrivate(Current, 0, v50, CreateIfNecessary, 0, 0, &spVisualStatePeer.ptr_);
      v59 = State;
      if ( State >= 0 )
      {
        v51 = spVisualStatePeer.ptr_;
        v64 = (Windows::ApplicationModel::Activation::ITileActivatedInfo *)((__int64)&spVisualStatePeer.ptr_[1]
                                                                          & -(__int64)(spVisualStatePeer.ptr_ != 0));
        v82.ptr_ = v64;
        Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef(&v82);
        v82.ptr_ = (Windows::ApplicationModel::Activation::ITileActivatedInfo *)spState.ptr_;
        spState.ptr_ = (Windows::UI::Xaml::IVisualState *)v64;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&v82);
        v65 = spState.ptr_;
        get_Name = spState.ptr_->get_Name;
        WindowsDeleteString(stateName._hstring);
        stateName._hstring = 0;
        State = get_Name(v65, &stateName._hstring);
        v59 = State;
        if ( State >= 0 )
          goto LABEL_108;
      }
    }
    else
    {
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spState);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroup);
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)result.m_ptr, 0);
      State = DirectUI::VisualStateManager::TryGetState(
                (Windows::UI::Xaml::Controls::IControl *)pControl,
                StringRawBuffer,
                &spGroup.ptr_,
                &spState.ptr_,
                bIgnored);
      v59 = State;
      if ( State >= 0 )
      {
LABEL_108:
        v24 = DirectUI::VisualStateManagerGenerated::GoToStateCoreProtected(
                (DirectUI::VisualStateManagerGenerated *)((__int64)&spCustomVsm.ptr_[-23]
                                                        & -(__int64)(spCustomVsm.ptr_ != 0)),
                (Windows::UI::Xaml::Controls::IControl *)pControl,
                spRoot.ptr_,
                stateName._hstring,
                spGroup.ptr_,
                spState.ptr_,
                bUseTransitions,
                (unsigned __int8 *)name.m_encodedStorage.Storage);
        if ( v51 )
          v51->Release(&v51->ctl::WeakReferenceSourceNoThreadId);
        xref_ptr<CDependencyObject>::DecrementRefCount(&visualState);
        v55 = spState.ptr_;
        if ( spState.ptr_ )
        {
          spState.ptr_ = 0;
          v55->Release(v55);
        }
        v56 = spGroup.ptr_;
        if ( spGroup.ptr_ )
        {
          spGroup.ptr_ = 0;
          v56->Release(v56);
        }
        goto LABEL_69;
      }
    }
    OnFailure_2990_(State);
    goto LABEL_129;
  }
  OnNewFailure_1172_(v11);
  if ( stateName._hstring )
    WindowsDeleteString(stateName._hstring);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18007972c  mov     [rsp-8+arg_8], rbx
0x180079731  push    rbp
0x180079732  push    rsi
0x180079733  push    rdi
0x180079734  push    r12
0x180079736  push    r13
0x180079738  push    r14
0x18007973a  push    r15
0x18007973c  lea     rbp, [rsp-17h]
0x180079741  sub     rsp, 0C0h
0x180079748  mov     r13, [rbp+47h+arg_28]
0x18007974c  xor     esi, esi
0x18007974e  mov     rdi, visualStateToken
0x180079751  mov     qword ptr [rbp+47h+name.m_encodedStorage.___u0], r13
0x180079755  mov     r12, pControl
0x180079758  mov     [rbp+47h+spRoot.ptr_], rsi
0x18007975c  lea     visualStateToken, [rbp+47h+spGroups]; newString
0x180079760  mov     [rbp+47h+spCustomVsm.ptr_], rsi
0x180079764  mov     pControl, hStateName; string
0x180079767  mov     [rbp+47h+bWentToState], sil
0x18007976b  mov     [rbp+47h+stateName._hstring], rsi
0x18007976f  mov     r14d, groupIndex
0x180079772  mov     [rbp+47h+spGroups.ptr_], rsi
0x180079776  mov     dword ptr [rbp+47h+var_48.ptr_], groupIndex
0x18007977a  mov     [rbp+47h+result.m_ptr], hStateName
0x18007977e  call    cs:__imp_WindowsDuplicateString
0x180079784  test    eax, eax
0x180079786  js      short loc_18007979A
0x180079788  mov     rax, [rbp+47h+spGroups.ptr_]
0x18007978c  mov     pControl, [rbp+47h+stateName._hstring]; string
0x180079790  mov     [rbp+47h+stateName._hstring], rax
0x180079794  call    cs:__imp_WindowsDeleteString
0x18007979a  test    r12, r12
0x18007979d  jz      loc_180079D1E
0x1800797a3  test    r13, r13
0x1800797a6  jz      loc_18007A1CC
0x1800797ac  mov     pControl, [rbp+47h+spRoot.ptr_]
0x1800797b0  lea     r15, [r12-1C0h]
0x1800797b8  mov     [r13+0], sil
0x1800797bc  test    pControl, pControl
0x1800797bf  jz      short loc_1800797D1
0x1800797c1  mov     [rbp+47h+spRoot.ptr_], rsi
0x1800797c5  mov     rax, [pControl]
0x1800797c8  mov     rax, [rax+10h]
0x1800797cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797d1  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+3, 8
0x1800797d8  mov     [rbp+47h+spGroups.ptr_], rsi
0x1800797dc  jnz     loc_180079EA4
0x1800797e2  test    byte ptr [r15+46h], 2
0x1800797e7  jnz     loc_180079D12
0x1800797ed  mov     rax, [r15+90h]
0x1800797f4  mov     pControl, [rax+10h]
0x1800797f8  mov     rax, [pControl]
0x1800797fb  mov     ebx, [rax+0BCh]
0x180079801  call    cs:__imp_GetCurrentThreadId
0x180079807  cmp     ebx, eax
0x180079809  jnz     loc_180079A78
0x18007980f  test    byte ptr [r15+46h], 2
0x180079814  mov     pControl, rsi
0x180079817  jnz     short loc_180079820
0x180079819  mov     pControl, [r15+90h]
0x180079820  mov     rax, [pControl]
0x180079823  mov     rax, [rax+330h]
0x18007982a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007982f  mov     rbx, rax
0x180079832  test    rax, rax
0x180079835  jz      short loc_180079847
0x180079837  mov     pControl, rax; this
0x18007983a  call    ?Release@CDependencyObject@@QEAAXXZ; CDependencyObject::Release(void)
0x18007983f  mov     pControl, rbx; this
0x180079842  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x180079847  lea     pControl, [rbp+47h+spVisualStatePeer]; this
0x18007984b  mov     [rbp+47h+spVisualStatePeer.ptr_], rsi
0x18007984f  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x180079854  test    rbx, rbx
0x180079857  jz      loc_180079C01
0x18007985d  mov     ecx, cs:?g_dwTlsIndex@DXamlInstanceStorage@@3KA; failedFrameHR
0x180079863  mov     [rbp+47h+spVisualStatePeer.ptr_], rsi
0x180079867  cmp     ecx, 0FFFFFFFFh
0x18007986a  jz      loc_180079D86
0x180079870  call    cs:__imp_TlsGetValue
0x180079876  mov     rsi, rax
0x180079879  test    rax, rax
0x18007987c  jz      loc_180079D6E
0x180079882  mov     rax, [rbx]
0x180079885  mov     pControl, rbx
0x180079888  mov     rax, [rax+258h]
0x18007988f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079894  lea     rax, [rbp+47h+spVisualStatePeer]
0x180079898  mov     groupIndex, 1; createMode
0x18007989e  mov     [rsp+0F0h+pCoreDO], rax; pCoreDO
0x1800798a3  mov     hStateName, rbx; pCoreDO
0x1800798a6  mov     [rsp+0F0h+pOuter], 0; pOuter
0x1800798af  xor     edx, edx; pOuter
0x1800798b1  mov     pControl, rsi; this
0x1800798b4  mov     [rsp+0F0h+pIsPendingDelete], 0; pIsPendingDelete
0x1800798bc  call    ?GetPeerPrivate@DXamlCore@DirectUI@@AEAAJPEAUIInspectable@@PEAVCDependencyObject@@W4GetPeerPrivateCreateMode@12@W4KnownTypeIndex@@IIPEAIPEAPEAVDependencyObject@2@@Z; DirectUI::DXamlCore::GetPeerPrivate(IInspectable *,CDependencyObject *,DirectUI::DXamlCore::GetPeerPrivateCreateMode,KnownTypeIndex,uint,uint,uint *,DirectUI::DependencyObject * *)
0x1800798c1  mov     esi, eax
0x1800798c3  test    eax, eax
0x1800798c5  js      loc_180079F40
0x1800798cb  mov     r13, [rbp+47h+spVisualStatePeer.ptr_]
0x1800798cf  lea     hStateName, [rbp+47h+spGroups]
0x1800798d3  mov     rax, r13
0x1800798d6  lea     visualStateToken, _GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1
0x1800798dd  neg     rax
0x1800798e0  sbb     pControl, pControl
0x1800798e3  lea     r14, [r13+8]
0x1800798e7  and     pControl, r14
0x1800798ea  mov     rax, [pControl]
0x1800798ed  mov     rax, [rax]
0x1800798f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800798f5  mov     esi, eax
0x1800798f7  test    eax, eax
0x1800798f9  js      loc_180079BC6
0x1800798ff  xor     esi, esi
0x180079901  test    r13, r13
0x180079904  jz      short loc_180079915
0x180079906  mov     rax, [r14]
0x180079909  mov     pControl, r14
0x18007990c  mov     rax, [rax+10h]
0x180079910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079915  mov     pControl, rbx; this
0x180079918  call    ?Release@CDependencyObject@@QEAAXXZ; CDependencyObject::Release(void)
0x18007991d  mov     r14d, dword ptr [rbp+47h+var_48.ptr_]
0x180079921  mov     r13, qword ptr [rbp+47h+name.m_encodedStorage.___u0]
0x180079925  mov     ebx, esi
0x180079927  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+3, 8
0x18007992e  jnz     loc_180079EB6
0x180079934  test    ebx, ebx
0x180079936  js      loc_180079F79
0x18007993c  mov     pControl, [rbp+47h+spGroups.ptr_]
0x180079940  mov     ebx, esi
0x180079942  test    pControl, pControl
0x180079945  jz      short loc_18007995F
0x180079947  mov     rax, [pControl]
0x18007994a  lea     hStateName, [rbp+47h+spRoot]
0x18007994e  lea     visualStateToken, _GUID_a391d09b_4a99_4b7c_9d8d_6fa5d01f6fbf
0x180079955  mov     rax, [rax]
0x180079958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007995d  mov     ebx, eax
0x18007995f  test    ebx, ebx
0x180079961  js      loc_180079F6D
0x180079967  mov     pControl, [rbp+47h+spGroups.ptr_]
0x18007996b  test    pControl, pControl
0x18007996e  jz      short loc_180079980
0x180079970  mov     [rbp+47h+spGroups.ptr_], rsi
0x180079974  mov     rax, [pControl]
0x180079977  mov     rax, [rax+10h]
0x18007997b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079980  test    ebx, ebx
0x180079982  js      loc_180079C69
0x180079988  cmp     [rbp+47h+spRoot.ptr_], rsi
0x18007998c  jz      loc_180079A1A
0x180079992  mov     pControl, [rbp+47h+spCustomVsm.ptr_]
0x180079996  test    pControl, pControl
0x180079999  jz      short loc_1800799AB
0x18007999b  mov     [rbp+47h+spCustomVsm.ptr_], rsi
0x18007999f  mov     rax, [pControl]
0x1800799a2  mov     rax, [rax+10h]
0x1800799a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800799ab  mov     rax, [rbp+47h+spRoot.ptr_]
0x1800799af  lea     pControl, [rax-160h]
0x1800799b6  neg     rax
0x1800799b9  sbb     rsi, rsi
0x1800799bc  and     rsi, pControl
0x1800799bf  jz      loc_180079F85
0x1800799c5  mov     edx, 1E4h; nPropertyIndex
0x1800799ca  lea     r9, [rbp+47h+spCustomVsm]; ppValue
0x1800799ce  lea     hStateName, _GUID_6fda9f9a_6fab_4112_9258_1006a3c3476e; iid
0x1800799d5  mov     pControl, rsi; this
0x1800799d8  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@AEBU_GUID@@PEAPEAX@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,_GUID const &,void * *)
0x1800799dd  xor     esi, esi
0x1800799df  mov     ebx, eax
0x1800799e1  test    eax, eax
0x1800799e3  js      loc_180079FB0
0x1800799e9  cmp     [rbp+47h+spCustomVsm.ptr_], rsi
0x1800799ed  jnz     loc_180079D90
0x1800799f3  mov     pControl, [rbp+47h+stateName._hstring]; string
0x1800799f7  call    cs:__imp_WindowsIsStringEmpty
0x1800799fd  test    eax, eax
0x1800799ff  jnz     loc_18007A12F
0x180079a05  mov     pControl, [rbp+47h+stateName._hstring]; string
0x180079a09  call    cs:__imp_WindowsIsStringEmpty
0x180079a0f  test    eax, eax
0x180079a11  jz      short loc_180079A89
0x180079a13  mov     al, [rbp+47h+bWentToState]
0x180079a16  mov     [r13+0], al
0x180079a1a  mov     pControl, [rbp+47h+stateName._hstring]; string
0x180079a1e  test    pControl, pControl
0x180079a21  jz      short loc_180079A29
0x180079a23  call    cs:__imp_WindowsDeleteString
0x180079a29  mov     pControl, [rbp+47h+spCustomVsm.ptr_]
0x180079a2d  test    pControl, pControl
0x180079a30  jz      short loc_180079A42
0x180079a32  mov     [rbp+47h+spCustomVsm.ptr_], rsi
0x180079a36  mov     rax, [pControl]
0x180079a39  mov     rax, [rax+10h]
0x180079a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a42  mov     pControl, [rbp+47h+spRoot.ptr_]
0x180079a46  test    pControl, pControl
0x180079a49  jz      short loc_180079A5B
0x180079a4b  mov     [rbp+47h+spRoot.ptr_], rsi
0x180079a4f  mov     rax, [pControl]
0x180079a52  mov     rax, [rax+10h]
0x180079a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a5b  xor     eax, eax
0x180079a5d  mov     rbx, [rsp+0F0h+arg_8]
0x180079a65  add     rsp, 0C0h
0x180079a6c  pop     r15
0x180079a6e  pop     r14
0x180079a70  pop     r13
0x180079a72  pop     r12
0x180079a74  pop     rdi
0x180079a75  pop     rsi
0x180079a76  pop     rbp
0x180079a77  retn
0x180079a78  mov     ebx, 8001010Eh
0x180079a7d  mov     ecx, ebx; failedFrameHR
0x180079a7f  call    OnFailure_2990_
0x180079a84  jmp     loc_180079927
0x180079a89  mov     rax, [rbp+47h+spRoot.ptr_]
0x180079a8d  mov     r14, [rbp+47h+stateName._hstring]
0x180079a91  mov     [rbp+47h+result.m_ptr], r12
0x180079a95  lea     pControl, [rax-160h]
0x180079a9c  neg     rax
0x180079a9f  sbb     rdi, rdi
0x180079aa2  and     rdi, pControl
0x180079aa5  mov     rax, [rdi+1B8h]
0x180079aac  test    rax, rax
0x180079aaf  jz      loc_180079CDA
0x180079ab5  mov     visualStateToken, [rax+8]; _Whereptr
0x180079ab9  cmp     visualStateToken, [rax+10h]
0x180079abd  jz      loc_180079D01
0x180079ac3  mov     [visualStateToken], r12
0x180079ac6  add     qword ptr [rax+8], 8
0x180079acb  mov     qword ptr [rbp+47h+name.m_encodedStorage.___u0], rsi
0x180079acf  lea     rsi, [rdi+8]
0x180079ad3  mov     rax, [rsi]
0x180079ad6  mov     pControl, rsi
0x180079ad9  mov     rax, [rax+40h]
0x180079add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ae2  test    rax, rax
0x180079ae5  jnz     loc_180079C0A
0x180079aeb  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+3, 8
0x180079af2  jnz     loc_180079CB8
0x180079af8  test    r14, r14
0x180079afb  jz      loc_18007A17A
0x180079b01  mov     pControl, rsi; this
0x180079b04  call    ?CheckThread@DependencyObject@DirectUI@@UEBAJXZ; DirectUI::DependencyObject::CheckThread(void)
0x180079b09  xor     esi, esi
0x180079b0b  mov     ebx, eax
0x180079b0d  test    eax, eax
0x180079b0f  js      loc_18007A1B4
0x180079b15  mov     rax, [rdi]
0x180079b18  lea     r9, [rbp+47h+bWentToState]
0x180079b1c  mov     r8b, [rbp+47h+arg_20]
0x180079b20  mov     visualStateToken, r14
0x180079b23  mov     pControl, rdi
0x180079b26  mov     rax, [rax+278h]
0x180079b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b32  mov     ebx, eax
0x180079b34  test    eax, eax
0x180079b36  js      loc_18007A1A8
0x180079b3c  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+3, 8
0x180079b43  jnz     loc_180079ED4
0x180079b49  test    ebx, ebx
0x180079b4b  js      loc_18007A1C0
0x180079b51  mov     pControl, qword ptr [rbp+47h+name.m_encodedStorage.___u0]
0x180079b55  test    pControl, pControl
0x180079b58  jz      short loc_180079B66
0x180079b5a  mov     rax, [pControl]
0x180079b5d  mov     rax, [rax+10h]
0x180079b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b66  mov     rax, [rdi+1B8h]
0x180079b6d  add     qword ptr [rax+8], 0FFFFFFFFFFFFFFF8h
0x180079b72  test    ebx, ebx
0x180079b74  jns     loc_180079A13
0x180079b7a  mov     ecx, ebx; failedFrameHR
0x180079b7c  call    OnFailure_2990_
0x180079b81  mov     pControl, [rbp+47h+stateName._hstring]; string
0x180079b85  test    pControl, pControl
0x180079b88  jz      short loc_180079B90
0x180079b8a  call    cs:__imp_WindowsDeleteString
0x180079b90  mov     pControl, [rbp+47h+spCustomVsm.ptr_]
0x180079b94  test    pControl, pControl
0x180079b97  jz      short loc_180079BA9
0x180079b99  mov     [rbp+47h+spCustomVsm.ptr_], rsi
0x180079b9d  mov     rax, [pControl]
0x180079ba0  mov     rax, [rax+10h]
0x180079ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ba9  mov     pControl, [rbp+47h+spRoot.ptr_]
0x180079bad  test    pControl, pControl
0x180079bb0  jz      loc_180079CB1
0x180079bb6  mov     [rbp+47h+spRoot.ptr_], rsi
0x180079bba  mov     rax, [pControl]
0x180079bbd  mov     rax, [rax+10h]
0x180079bc1  jmp     loc_180079CAC
0x180079bc6  mov     ecx, esi; failedFrameHR
0x180079bc8  call    OnFailure_2990_
0x180079bcd  test    r13, r13
  ... truncated ...
```
