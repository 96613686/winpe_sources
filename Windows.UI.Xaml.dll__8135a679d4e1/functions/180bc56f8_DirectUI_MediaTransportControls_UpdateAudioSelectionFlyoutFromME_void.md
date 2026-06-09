# DirectUI::MediaTransportControls::UpdateAudioSelectionFlyoutFromME(void)

- ea: `0x180bc56f8`
- end: `0x180bc5ce9`
- name: `?UpdateAudioSelectionFlyoutFromME@MediaTransportControls@DirectUI@@QEAAJXZ`
- size: `1521`
- prototype: `HRESULT __fastcall(DirectUI::MediaTransportControls *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180b9510c`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x18004e1a0`
- `0x18005c640`
- `0x180131190`
- `0x1801df610`
- `0x1801e5458`
- `0x1803839c0`
- `0x18038a9e4`
- `0x180613b44`
- `0x1807003cc`
- `0x18076e110`
- `0x180962898`
- `0x180b8c678`
- `0x180b8f358`
- `0x180b90764`
- `0x180b9f9bc`
- `0x180bbb7d0`
- `0x180bc56f8`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc598f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc59d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc598f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc59d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bc5a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180bc5974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180bc59be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180bc5974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180bc59be`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180bc589c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180bc589c`

## pseudocode

```c
__int64 __fastcall DirectUI::MediaTransportControls::UpdateAudioSelectionFlyoutFromME(
        DirectUI::MediaTransportControls *this)
{
  HSTRING__ *hstring; // rbx
  HRESULT ActiveAudioStream; // eax
  unsigned int v4; // edi
  __int64 ptr; // rcx
  Windows::Media::Playback::IMediaPlaybackItem *v6; // rsi
  HRESULT (__fastcall *get_AudioTracks)(Windows::Media::Playback::IMediaPlaybackItem *, Windows::Foundation::Collections::IVectorView<Windows::Media::Core::AudioTrack *> **); // rdi
  IUnknown *m_value; // rsi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  unsigned int i; // r15d
  _QWORD *v11; // rax
  HRESULT ActivationFactory; // eax
  Windows::Foundation::IPropertyValueStatics *v13; // rsi
  HRESULT (__fastcall *CreateInt32)(Windows::Foundation::IPropertyValueStatics *, int, IInspectable **); // rdi
  DirectUI::MediaTransportControls *v15; // rcx
  HRESULT LocalizedResourceString; // eax
  Windows::Media::Core::IMediaTrack *v17; // rsi
  HRESULT (__fastcall *get_Label)(Windows::Media::Core::IMediaTrack *, HSTRING__ **); // rdi
  HSTRING__ *v19; // rcx
  Windows::Media::Core::IMediaTrack *v20; // rsi
  HRESULT (__fastcall *get_Language)(Windows::Media::Core::IMediaTrack *, HSTRING__ **); // rdi
  DirectUI::DXamlCore *Current; // rdi
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, Windows::Foundation::IReference<int> *, Windows::Internal::String *); // rdi
  DirectUI::MediaTransportControls *v25; // rcx
  DirectUI::MediaTransportControls *v26; // rcx
  HRESULT v27; // eax
  Windows::Media::Core::IMediaTrack *FailFast; // rax
  Windows::Media::Core::IMediaTrack *v29; // rsi
  ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > **Mylast; // rdx
  Windows::Internal::String strLocalizedLanguageName; // [rsp+20h] [rbp-99h] BYREF
  ctl::ComPtr<Windows::Media::Core::IMediaTrack> spMediaTrack; // [rsp+28h] [rbp-91h] BYREF
  ctl::ComPtr<DirectUI::MenuFlyoutItem> spNewMenuFlyoutItem; // [rsp+30h] [rbp-89h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IMediaElement> spOwnerME; // [rsp+38h] [rbp-81h] BYREF
  int audioStreamCount; // [rsp+40h] [rbp-79h] BYREF
  int activeAudioStreamIndex; // [rsp+44h] [rbp-75h] BYREF
  Windows::Internal::String strProcessedLanguageName; // [rsp+48h] [rbp-71h] BYREF
  Windows::Internal::String strLanguageTag; // [rsp+50h] [rbp-69h] BYREF
  ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::MenuFlyoutItemBase *> > spMenuFlyoutItems; // [rsp+58h] [rbp-61h] BYREF
  ctl::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Media::Core::AudioTrack *> > spAudioTracks; // [rsp+60h] [rbp-59h] BYREF
  ctl::ComPtr<Windows::Foundation::IPropertyValue> spIndexAsPV; // [rsp+68h] [rbp-51h] BYREF
  ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> spPropertyValueFactory; // [rsp+70h] [rbp-49h] BYREF
  ctl::ComPtr<Windows::Foundation::IReference<int> > spIndex; // [rsp+78h] [rbp-41h] BYREF
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> v45; // [rsp+80h] [rbp-39h] BYREF

  activeAudioStreamIndex = -1;
  audioStreamCount = 0;
  hstring = 0;
  spOwnerME.ptr_ = 0;
  strProcessedLanguageName._hstring = 0;
  spMenuFlyoutItems.ptr_ = 0;
  spPropertyValueFactory.ptr_ = 0;
  spIndexAsPV.ptr_ = 0;
  spIndex.ptr_ = 0;
  strLanguageTag._hstring = 0;
  strLocalizedLanguageName._hstring = 0;
  spAudioTracks.ptr_ = 0;
  ActiveAudioStream = ctl::WeakRefPtr::As<Windows::UI::Xaml::Controls::IMediaElement>(
                        &this->m_wrOwnerParent,
                        (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IMediaElement> >)&spOwnerME);
  v4 = ActiveAudioStream;
  if ( ActiveAudioStream < 0 )
    goto LABEL_55;
  ptr = (__int64)spOwnerME.ptr_;
  if ( spOwnerME.ptr_ )
  {
    v6 = this->m_spCurrentItem.ptr_;
    if ( !v6 )
      goto LABEL_6;
    get_AudioTracks = v6->get_AudioTracks;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spAudioTracks);
    ActiveAudioStream = get_AudioTracks(v6, &spAudioTracks.ptr_);
    v4 = ActiveAudioStream;
    if ( ActiveAudioStream >= 0 )
    {
      ptr = (__int64)spOwnerME.ptr_;
LABEL_6:
      if ( !ptr )
        ptr = 448;
      ActiveAudioStream = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)ptr + 248LL))(ptr, &audioStreamCount);
      v4 = ActiveAudioStream;
      if ( ActiveAudioStream >= 0 )
      {
        ActiveAudioStream = DirectUI::MediaElement::GetActiveAudioStream(
                              (DirectUI::MediaElement *)((__int64)&spOwnerME.ptr_[-56] & -(__int64)(spOwnerME.ptr_ != 0)),
                              &activeAudioStreamIndex);
        v4 = ActiveAudioStream;
        if ( ActiveAudioStream >= 0 )
        {
          m_value = this->m_tpAvailableAudioTracksMenuFlyout.m_trackerReference.m_value;
          QueryInterface = m_value->__vftable[2].QueryInterface;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMenuFlyoutItems);
          ActiveAudioStream = ((__int64 (__fastcall *)(IUnknown *, ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::MenuFlyoutItemBase *> > *))QueryInterface)(
                                m_value,
                                &spMenuFlyoutItems);
          v4 = ActiveAudioStream;
          if ( ActiveAudioStream >= 0 )
          {
            ActiveAudioStream = spMenuFlyoutItems.ptr_->Clear(spMenuFlyoutItems.ptr_);
            v4 = ActiveAudioStream;
            if ( ActiveAudioStream >= 0 )
            {
              DirectUI::MediaTransportControls::ReleaseMenuFlyoutItemClickHandlers(this);
              for ( i = 0; ; ++i )
              {
                if ( (int)i >= audioStreamCount )
                  goto $Cleanup_13732;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
                Windows::Internal::StringReference::StringReference(
                  (Windows::Internal::StringReference *)&v45,
                  (const wchar_t (*)[33])RuntimeClass_Windows_Foundation_PropertyValue);
                ActivationFactory = RoGetActivationFactory(
                                      *v11,
                                      &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858,
                                      &spPropertyValueFactory);
                v4 = ActivationFactory;
                if ( ActivationFactory < 0 )
                  goto LABEL_51;
                v13 = spPropertyValueFactory.ptr_;
                CreateInt32 = spPropertyValueFactory.ptr_->CreateInt32;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIndexAsPV);
                ActivationFactory = CreateInt32(v13, i, &spIndexAsPV.ptr_);
                v4 = ActivationFactory;
                if ( ActivationFactory < 0 )
                  goto LABEL_51;
                ActivationFactory = ctl::ComPtr<Windows::Foundation::IPropertyValue>::As<Windows::Foundation::IReference<int>>(
                                      &spIndexAsPV,
                                      (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::Foundation::IReference<int> > >)&spIndex);
                v4 = ActivationFactory;
                if ( ActivationFactory < 0 )
                  goto LABEL_51;
                if ( !DirectUI::MediaTransportControls::IsWindowsBlue(v15) && this->m_spCurrentItem.ptr_ )
                  break;
                v23 = (__int64)spOwnerME.ptr_;
                if ( !spOwnerME.ptr_ )
                  v23 = 448;
                v24 = *(__int64 (__fastcall **)(__int64, Windows::Foundation::IReference<int> *, Windows::Internal::String *))(*(_QWORD *)v23 + 648LL);
                WindowsDeleteString(strLanguageTag._hstring);
                strLanguageTag._hstring = 0;
                ActivationFactory = v24(v23, spIndex.ptr_, &strLanguageTag);
                v4 = ActivationFactory;
                if ( ActivationFactory < 0
                  || (WindowsDeleteString(strLocalizedLanguageName._hstring),
                      strLocalizedLanguageName._hstring = 0,
                      ActivationFactory = DirectUI::MediaTransportControls::GetLocalizedLanguageName(
                                            v25,
                                            strLanguageTag._hstring,
                                            &strLocalizedLanguageName._hstring),
                      v4 = ActivationFactory,
                      ActivationFactory < 0) )
                {
LABEL_51:
                  OnFailure_2990_(ActivationFactory);
                  goto $Cleanup_13732;
                }
LABEL_33:
                WindowsDeleteString(hstring);
                if ( activeAudioStreamIndex == i )
                {
                  strProcessedLanguageName._hstring = 0;
                  ActivationFactory = DirectUI::MediaTransportControls::MarkLanguageSelection(
                                        v26,
                                        strLocalizedLanguageName._hstring,
                                        &strProcessedLanguageName._hstring);
                  v4 = ActivationFactory;
                  if ( ActivationFactory < 0 )
                    goto LABEL_51;
                  hstring = strProcessedLanguageName._hstring;
                }
                else
                {
                  hstring = strLocalizedLanguageName._hstring;
                  strProcessedLanguageName._hstring = strLocalizedLanguageName._hstring;
                  strLocalizedLanguageName._hstring = 0;
                }
                spNewMenuFlyoutItem.ptr_ = 0;
                v27 = ctl::make<DirectUI::MenuFlyoutItem>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::MenuFlyoutItem> >)&spNewMenuFlyoutItem);
                v4 = v27;
                if ( v27 < 0 )
                  goto LABEL_50;
                v27 = spNewMenuFlyoutItem.ptr_->put_Text(
                        &spNewMenuFlyoutItem.ptr_->Windows::UI::Xaml::Controls::IMenuFlyoutItem,
                        hstring);
                v4 = v27;
                if ( v27 < 0 )
                  goto LABEL_50;
                v27 = spMenuFlyoutItems.ptr_->Append(
                        spMenuFlyoutItems.ptr_,
                        (Windows::UI::Xaml::Controls::IMenuFlyoutItemBase *)((__int64)&spNewMenuFlyoutItem.ptr_->Windows::UI::Xaml::Controls::IMenuFlyoutItemBase
                                                                           & -(__int64)(spNewMenuFlyoutItem.ptr_ != 0)));
                v4 = v27;
                if ( v27 < 0 )
                  goto LABEL_50;
                FailFast = (Windows::Media::Core::IMediaTrack *)XcpAllocation::OSMemoryAllocateFailFast(8u);
                v29 = FailFast;
                if ( FailFast )
                  FailFast->__vftable = 0;
                else
                  v29 = 0;
                spMediaTrack.ptr_ = v29;
                v45._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_5dff4021e52f4b97272a9179205922dc__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
                v45._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
                v45._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&v45;
                v27 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits>>::AttachEventHandler(
                        (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *)v29,
                        (Windows::UI::Xaml::Controls::IMenuFlyoutItem *)((unsigned __int128)&spNewMenuFlyoutItem.ptr_->Windows::UI::Xaml::Controls::IMenuFlyoutItem
                                                                       & ((unsigned __int128)-(__int128)(unsigned __int64)spNewMenuFlyoutItem.ptr_ >> 64)),
                        &v45);
                v4 = v27;
                if ( v27 < 0 )
                {
LABEL_50:
                  OnFailure_2990_(v27);
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spNewMenuFlyoutItem);
                  goto $Cleanup_13732;
                }
                Mylast = this->m_audioTrackClickHandlers._Mypair._Myval2._Mylast;
                if ( Mylast == this->m_audioTrackClickHandlers._Mypair._Myval2._Myend )
                {
                  std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(
                    &this->m_audioTrackClickHandlers,
                    Mylast,
                    (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *const *)&spMediaTrack);
                }
                else
                {
                  *Mylast = (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits> > *)v29;
                  ++this->m_audioTrackClickHandlers._Mypair._Myval2._Mylast;
                }
                ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spNewMenuFlyoutItem);
              }
              spMediaTrack.ptr_ = 0;
              LocalizedResourceString = spAudioTracks.ptr_->GetAt(
                                          spAudioTracks.ptr_,
                                          i,
                                          (Windows::Media::Core::IMediaTrack **)&spMediaTrack);
              v4 = LocalizedResourceString;
              if ( LocalizedResourceString < 0 )
                goto LABEL_48;
              v17 = spMediaTrack.ptr_;
              get_Label = spMediaTrack.ptr_->get_Label;
              WindowsDeleteString(strLocalizedLanguageName._hstring);
              strLocalizedLanguageName._hstring = 0;
              LocalizedResourceString = get_Label(v17, &strLocalizedLanguageName._hstring);
              v4 = LocalizedResourceString;
              if ( LocalizedResourceString < 0 )
                goto LABEL_48;
              v19 = strLocalizedLanguageName._hstring;
              if ( strLocalizedLanguageName._hstring )
              {
                if ( WindowsGetStringLen(strLocalizedLanguageName._hstring) )
                {
LABEL_28:
                  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMediaTrack);
                  goto LABEL_33;
                }
                v19 = strLocalizedLanguageName._hstring;
              }
              v20 = spMediaTrack.ptr_;
              get_Language = spMediaTrack.ptr_->get_Language;
              WindowsDeleteString(v19);
              strLocalizedLanguageName._hstring = 0;
              LocalizedResourceString = get_Language(v20, &strLocalizedLanguageName._hstring);
              v4 = LocalizedResourceString;
              if ( LocalizedResourceString < 0
                || (!strLocalizedLanguageName._hstring || !WindowsGetStringLen(strLocalizedLanguageName._hstring))
                && (Current = DirectUI::DXamlCore::GetCurrent(),
                    WindowsDeleteString(strLocalizedLanguageName._hstring),
                    strLocalizedLanguageName._hstring = 0,
                    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                                Current,
                                                0x13D5u,
                                                &strLocalizedLanguageName._hstring),
                    v4 = LocalizedResourceString,
                    LocalizedResourceString < 0) )
              {
LABEL_48:
                OnFailure_2990_(LocalizedResourceString);
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMediaTrack);
                goto $Cleanup_13732;
              }
              goto LABEL_28;
            }
          }
        }
      }
    }
LABEL_55:
    OnFailure_2990_(ActiveAudioStream);
  }
$Cleanup_13732:
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spAudioTracks);
  Windows::Internal::String::~String(&strProcessedLanguageName);
  Windows::Internal::String::~String(&strLocalizedLanguageName);
  Windows::Internal::String::~String(&strLanguageTag);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIndex);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIndexAsPV);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMenuFlyoutItems);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spOwnerME);
  return v4;
}

```

## disassembly

```asm
0x180bc56f8  push    rbp
0x180bc56fa  push    rbx
0x180bc56fb  push    rsi
0x180bc56fc  push    rdi
0x180bc56fd  push    r12
0x180bc56ff  push    r13
0x180bc5701  push    r14
0x180bc5703  push    r15
0x180bc5705  lea     rbp, [rsp-1Fh]
0x180bc570a  sub     rsp, 0D8h
0x180bc5711  mov     rax, cs:__security_cookie
0x180bc5718  xor     rax, rsp
0x180bc571b  mov     [rbp+57h+var_50], rax
0x180bc571f  xor     r12d, r12d
0x180bc5722  mov     [rbp+57h+activeAudioStreamIndex], 0FFFFFFFFh
0x180bc5729  mov     r14, this
0x180bc572c  mov     [rbp+57h+audioStreamCount], r12d
0x180bc5730  mov     ebx, r12d
0x180bc5733  mov     [rsp+110h+spOwnerME.ptr_], r12
0x180bc5738  add     this, 240h; this
0x180bc573f  mov     [rbp+57h+strProcessedLanguageName._hstring], rbx
0x180bc5743  lea     rdx, [rsp+110h+spOwnerME]; ptr
0x180bc5748  mov     [rbp+57h+spMenuFlyoutItems.ptr_], r12
0x180bc574c  mov     [rbp+57h+spPropertyValueFactory.ptr_], r12
0x180bc5750  mov     [rbp+57h+spIndexAsPV.ptr_], r12
0x180bc5754  mov     [rbp+57h+spIndex.ptr_], r12
0x180bc5758  mov     [rbp+57h+strLanguageTag._hstring], r12
0x180bc575c  mov     [rsp+110h+strLocalizedLanguageName._hstring], r12
0x180bc5761  mov     [rbp+57h+spAudioTracks.ptr_], r12
0x180bc5765  call    ??$As@UIMediaElement@Controls@Xaml@UI@Windows@@@WeakRefPtr@ctl@@QEAAJV?$ComPtrRef@V?$ComPtr@UIMediaElement@Controls@Xaml@UI@Windows@@@ctl@@@Internal@1@@Z; ctl::WeakRefPtr::As<Windows::UI::Xaml::Controls::IMediaElement>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IMediaElement>>)
0x180bc576a  mov     edi, eax
0x180bc576c  test    eax, eax
0x180bc576e  js      loc_180BC5C6D
0x180bc5774  mov     this, [rsp+110h+spOwnerME.ptr_]
0x180bc5779  test    this, this
0x180bc577c  jz      $Cleanup_13732
0x180bc5782  mov     rsi, [r14+0AD8h]
0x180bc5789  test    rsi, rsi
0x180bc578c  jz      short loc_180BC57C4
0x180bc578e  mov     rax, [rsi]
0x180bc5791  lea     this, [rbp+57h+spAudioTracks]; this
0x180bc5795  mov     rdi, [rax+68h]
0x180bc5799  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180bc579e  lea     rdx, [rbp+57h+spAudioTracks]
0x180bc57a2  mov     this, rsi
0x180bc57a5  mov     rax, rdi
0x180bc57a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc57ad  mov     edi, eax
0x180bc57af  test    eax, eax
0x180bc57b1  jns     short loc_180BC57BF
0x180bc57b3  mov     ecx, eax; failedFrameHR
0x180bc57b5  call    OnFailure_2990_
0x180bc57ba  jmp     $Cleanup_13732
0x180bc57bf  mov     this, [rsp+110h+spOwnerME.ptr_]
0x180bc57c4  test    this, this
0x180bc57c7  lea     rdx, [rbp+57h+audioStreamCount]
0x180bc57cb  mov     r13d, 1C0h
0x180bc57d1  cmovz   this, r13
0x180bc57d5  mov     rax, [this]
0x180bc57d8  mov     rax, [rax+0F8h]
0x180bc57df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc57e4  mov     edi, eax
0x180bc57e6  test    eax, eax
0x180bc57e8  js      loc_180BC5C64
0x180bc57ee  mov     rax, [rsp+110h+spOwnerME.ptr_]
0x180bc57f3  lea     rdx, [rax-1C0h]
0x180bc57fa  neg     rax
0x180bc57fd  sbb     this, this
0x180bc5800  and     this, rdx; this
0x180bc5803  lea     rdx, [rbp+57h+activeAudioStreamIndex]; pActiveAudioStream
0x180bc5807  call    ?GetActiveAudioStream@MediaElement@DirectUI@@QEAAJPEAH@Z; DirectUI::MediaElement::GetActiveAudioStream(int *)
0x180bc580c  mov     edi, eax
0x180bc580e  test    eax, eax
0x180bc5810  js      loc_180BC5C5B
0x180bc5816  mov     rsi, [r14+4A0h]
0x180bc581d  lea     this, [rbp+57h+spMenuFlyoutItems]; this
0x180bc5821  mov     rax, [rsi]
0x180bc5824  mov     rdi, [rax+30h]
0x180bc5828  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180bc582d  lea     rdx, [rbp+57h+spMenuFlyoutItems]
0x180bc5831  mov     this, rsi
0x180bc5834  mov     rax, rdi
0x180bc5837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc583c  mov     edi, eax
0x180bc583e  test    eax, eax
0x180bc5840  js      loc_180BC5C52
0x180bc5846  mov     this, [rbp+57h+spMenuFlyoutItems.ptr_]
0x180bc584a  mov     rax, [this]
0x180bc584d  mov     rax, [rax+78h]
0x180bc5851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc5856  mov     edi, eax
0x180bc5858  test    eax, eax
0x180bc585a  js      loc_180BC5C49
0x180bc5860  mov     this, r14; this
0x180bc5863  call    ?ReleaseMenuFlyoutItemClickHandlers@MediaTransportControls@DirectUI@@QEAAXXZ; DirectUI::MediaTransportControls::ReleaseMenuFlyoutItemClickHandlers(void)
0x180bc5868  mov     r15d, r12d
0x180bc586b  cmp     r15d, [rbp+57h+audioStreamCount]
0x180bc586f  jge     $Cleanup_13732
0x180bc5875  lea     this, [rbp+57h+spPropertyValueFactory]; this
0x180bc5879  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180bc587e  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; stringRef
0x180bc5885  lea     this, [rbp+57h+var_90]; this
0x180bc5889  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x180bc588e  lea     r8, [rbp+57h+spPropertyValueFactory]
0x180bc5892  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180bc5899  mov     this, [rax]
0x180bc589c  call    cs:__imp_RoGetActivationFactory
0x180bc58a2  mov     edi, eax
0x180bc58a4  test    eax, eax
0x180bc58a6  js      loc_180BC5C40
0x180bc58ac  mov     rsi, [rbp+57h+spPropertyValueFactory.ptr_]
0x180bc58b0  lea     this, [rbp+57h+spIndexAsPV]; this
0x180bc58b4  mov     rax, [rsi]
0x180bc58b7  mov     rdi, [rax+50h]
0x180bc58bb  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180bc58c0  lea     r8, [rbp+57h+spIndexAsPV]
0x180bc58c4  mov     edx, r15d
0x180bc58c7  mov     this, rsi
0x180bc58ca  mov     rax, rdi
0x180bc58cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc58d2  mov     edi, eax
0x180bc58d4  test    eax, eax
0x180bc58d6  js      loc_180BC5C37
0x180bc58dc  lea     rdx, [rbp+57h+spIndex]; p
0x180bc58e0  lea     this, [rbp+57h+spIndexAsPV]; this
0x180bc58e4  call    ??$As@U?$IReference@H@Foundation@Windows@@@?$ComPtr@UIPropertyValue@Foundation@Windows@@@ctl@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IReference@H@Foundation@Windows@@@ctl@@@Internal@1@@Z; ctl::ComPtr<Windows::Foundation::IPropertyValue>::As<Windows::Foundation::IReference<int>>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::Foundation::IReference<int>>>)
0x180bc58e9  mov     edi, eax
0x180bc58eb  test    eax, eax
0x180bc58ed  js      loc_180BC5C2E
0x180bc58f3  call    ?IsWindowsBlue@MediaTransportControls@DirectUI@@AEAA_NXZ; DirectUI::MediaTransportControls::IsWindowsBlue(void)
0x180bc58f8  test    al, al
0x180bc58fa  jnz     loc_180BC5A08
0x180bc5900  cmp     [r14+0AD8h], r12
0x180bc5907  jz      loc_180BC5A08
0x180bc590d  mov     this, [rbp+57h+spAudioTracks.ptr_]
0x180bc5911  lea     r8, [rsp+110h+spMediaTrack]
0x180bc5916  mov     [rsp+110h+spMediaTrack.ptr_], r12
0x180bc591b  mov     edx, r15d
0x180bc591e  mov     rax, [this]
0x180bc5921  mov     rax, [rax+30h]
0x180bc5925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc592a  mov     edi, eax
0x180bc592c  test    eax, eax
0x180bc592e  js      loc_180BC5BCC
0x180bc5934  mov     rsi, [rsp+110h+spMediaTrack.ptr_]
0x180bc5939  mov     this, [rsp+110h+strLocalizedLanguageName._hstring]; string
0x180bc593e  mov     rax, [rsi]
0x180bc5941  mov     rdi, [rax+50h]
0x180bc5945  call    cs:__imp_WindowsDeleteString
0x180bc594b  lea     rdx, [rsp+110h+strLocalizedLanguageName]
0x180bc5950  mov     [rsp+110h+strLocalizedLanguageName._hstring], r12
0x180bc5955  mov     this, rsi
0x180bc5958  mov     rax, rdi
0x180bc595b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc5960  mov     edi, eax
0x180bc5962  test    eax, eax
0x180bc5964  js      loc_180BC5BC3
0x180bc596a  mov     this, [rsp+110h+strLocalizedLanguageName._hstring]; string
0x180bc596f  test    this, this
0x180bc5972  jz      short loc_180BC5983
0x180bc5974  call    cs:__imp_WindowsGetStringLen
0x180bc597a  test    eax, eax
0x180bc597c  jnz     short loc_180BC59FC
0x180bc597e  mov     this, [rsp+110h+strLocalizedLanguageName._hstring]; string
0x180bc5983  mov     rsi, [rsp+110h+spMediaTrack.ptr_]
0x180bc5988  mov     rax, [rsi]
0x180bc598b  mov     rdi, [rax+38h]
0x180bc598f  call    cs:__imp_WindowsDeleteString
0x180bc5995  lea     rdx, [rsp+110h+strLocalizedLanguageName]
0x180bc599a  mov     [rsp+110h+strLocalizedLanguageName._hstring], r12
0x180bc599f  mov     this, rsi
0x180bc59a2  mov     rax, rdi
0x180bc59a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc59aa  mov     edi, eax
0x180bc59ac  test    eax, eax
0x180bc59ae  js      loc_180BC5BBA
0x180bc59b4  mov     this, [rsp+110h+strLocalizedLanguageName._hstring]; string
0x180bc59b9  test    this, this
0x180bc59bc  jz      short loc_180BC59C8
0x180bc59be  call    cs:__imp_WindowsGetStringLen
0x180bc59c4  test    eax, eax
0x180bc59c6  jnz     short loc_180BC59FC
0x180bc59c8  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180bc59cd  mov     this, [rsp+110h+strLocalizedLanguageName._hstring]; string
0x180bc59d2  mov     rdi, rax
0x180bc59d5  call    cs:__imp_WindowsDeleteString
0x180bc59db  lea     r8, [rsp+110h+strLocalizedLanguageName]; resourceString
0x180bc59e0  mov     [rsp+110h+strLocalizedLanguageName._hstring], r12
0x180bc59e5  mov     edx, 13D5h; resourceStringID
0x180bc59ea  mov     this, rdi; this
0x180bc59ed  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180bc59f2  mov     edi, eax
0x180bc59f4  test    eax, eax
0x180bc59f6  js      loc_180BC5BB1
0x180bc59fc  lea     this, [rsp+110h+spMediaTrack]; this
0x180bc5a01  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180bc5a06  jmp     short loc_180BC5A71
0x180bc5a08  mov     rsi, [rsp+110h+spOwnerME.ptr_]
0x180bc5a0d  mov     this, [rbp+57h+strLanguageTag._hstring]; string
0x180bc5a11  test    rsi, rsi
0x180bc5a14  cmovz   rsi, r13
0x180bc5a18  mov     rax, [rsi]
0x180bc5a1b  mov     rdi, [rax+288h]
0x180bc5a22  call    cs:__imp_WindowsDeleteString
0x180bc5a28  mov     rdx, [rbp+57h+spIndex.ptr_]
0x180bc5a2c  lea     r8, [rbp+57h+strLanguageTag]
0x180bc5a30  mov     this, rsi
0x180bc5a33  mov     [rbp+57h+strLanguageTag._hstring], r12
0x180bc5a37  mov     rax, rdi
0x180bc5a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc5a3f  mov     edi, eax
0x180bc5a41  test    eax, eax
0x180bc5a43  js      loc_180BC5C25
0x180bc5a49  mov     this, [rsp+110h+strLocalizedLanguageName._hstring]; string
0x180bc5a4e  call    cs:__imp_WindowsDeleteString
0x180bc5a54  mov     rdx, [rbp+57h+strLanguageTag._hstring]; languageTag
0x180bc5a58  lea     r8, [rsp+110h+strLocalizedLanguageName]; pProcessedLanguageName
0x180bc5a5d  mov     [rsp+110h+strLocalizedLanguageName._hstring], r12
0x180bc5a62  call    ?GetLocalizedLanguageName@MediaTransportControls@DirectUI@@AEAAJPEAUHSTRING__@@PEAPEAU3@@Z; DirectUI::MediaTransportControls::GetLocalizedLanguageName(HSTRING__ *,HSTRING__ * *)
0x180bc5a67  mov     edi, eax
0x180bc5a69  test    eax, eax
0x180bc5a6b  js      loc_180BC5C1C
0x180bc5a71  mov     this, rbx; string
0x180bc5a74  call    cs:__imp_WindowsDeleteString
0x180bc5a7a  cmp     [rbp+57h+activeAudioStreamIndex], r15d
0x180bc5a7e  jnz     short loc_180BC5AA2
0x180bc5a80  mov     rdx, [rsp+110h+strLocalizedLanguageName._hstring]; localizedLanguage
0x180bc5a85  lea     r8, [rbp+57h+strProcessedLanguageName]; pMarkedLocalizedLanguage
0x180bc5a89  mov     [rbp+57h+strProcessedLanguageName._hstring], r12
0x180bc5a8d  call    ?MarkLanguageSelection@MediaTransportControls@DirectUI@@AEAAJPEAUHSTRING__@@PEAPEAU3@@Z; DirectUI::MediaTransportControls::MarkLanguageSelection(HSTRING__ *,HSTRING__ * *)
0x180bc5a92  mov     edi, eax
0x180bc5a94  test    eax, eax
0x180bc5a96  js      loc_180BC5BE2
0x180bc5a9c  mov     rbx, [rbp+57h+strProcessedLanguageName._hstring]
0x180bc5aa0  jmp     short loc_180BC5AB0
0x180bc5aa2  mov     rbx, [rsp+110h+strLocalizedLanguageName._hstring]
0x180bc5aa7  mov     [rbp+57h+strProcessedLanguageName._hstring], rbx
0x180bc5aab  mov     [rsp+110h+strLocalizedLanguageName._hstring], r12
0x180bc5ab0  lea     this, [rsp+110h+spNewMenuFlyoutItem]; ppNewInstance
0x180bc5ab5  mov     [rsp+110h+spNewMenuFlyoutItem.ptr_], r12
0x180bc5aba  call    ??$make@VMenuFlyoutItem@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VMenuFlyoutItem@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::MenuFlyoutItem>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::MenuFlyoutItem>>)
0x180bc5abf  mov     edi, eax
0x180bc5ac1  test    eax, eax
0x180bc5ac3  js      loc_180BC5C09
0x180bc5ac9  mov     this, [rsp+110h+spNewMenuFlyoutItem.ptr_]
0x180bc5ace  mov     rdx, rbx
0x180bc5ad1  add     this, 228h
0x180bc5ad8  mov     rax, [this]
0x180bc5adb  mov     rax, [rax+38h]
0x180bc5adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc5ae4  mov     edi, eax
0x180bc5ae6  test    eax, eax
0x180bc5ae8  js      loc_180BC5C00
0x180bc5aee  mov     rdx, [rsp+110h+spNewMenuFlyoutItem.ptr_]
0x180bc5af3  mov     this, [rbp+57h+spMenuFlyoutItems.ptr_]
0x180bc5af7  lea     rax, [rdx+218h]
0x180bc5afe  neg     rdx
0x180bc5b01  mov     r8, [this]
0x180bc5b04  sbb     rdx, rdx
0x180bc5b07  and     rdx, rax
0x180bc5b0a  mov     rax, [r8+68h]
0x180bc5b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180bc5b13  mov     edi, eax
0x180bc5b15  test    eax, eax
0x180bc5b17  js      loc_180BC5BF7
0x180bc5b1d  mov     ecx, 8; cSize
0x180bc5b22  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180bc5b27  mov     rsi, rax
0x180bc5b2a  test    rax, rax
0x180bc5b2d  jz      short loc_180BC5B34
0x180bc5b2f  mov     [rax], r12
0x180bc5b32  jmp     short loc_180BC5B37
0x180bc5b34  mov     rsi, r12
0x180bc5b37  lea     rax, std___Func_impl_no_alloc__lambda_5dff4021e52f4b97272a9179205922dc__long_IInspectable___Windows__UI__Xaml__IRoutedEventArgs______vftable_
0x180bc5b3e  mov     [rsp+110h+spMediaTrack.ptr_], rsi
0x180bc5b43  mov     [rbp+57h+var_90._hstring], rax
0x180bc5b47  lea     r8, [rbp+57h+var_90]
0x180bc5b4b  lea     rax, [rbp+57h+var_90]
0x180bc5b4f  mov     qword ptr [rbp+57h+var_90._header.Reserved], r14
0x180bc5b53  mov     [rbp+57h+var_58], rax
0x180bc5b57  mov     rax, [rsp+110h+spNewMenuFlyoutItem.ptr_]
0x180bc5b5c  lea     this, [rax+228h]
0x180bc5b63  neg     rax
0x180bc5b66  sbb     rdx, rdx
0x180bc5b69  and     rdx, this
0x180bc5b6c  mov     this, rsi
0x180bc5b6f  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UIRoutedEventHandler@Xaml@UI@Windows@@UIInspectable@@UIRoutedEventArgs@234@UMenuFlyoutItemClickTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIMenuFlyoutItem@Controls@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::MenuFlyoutItemClickTraits>>::AttachEventHandler(Windows::UI::Xaml::Controls::IMenuFlyoutItem *,std::function<long (IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)>)
0x180bc5b74  mov     edi, eax
0x180bc5b76  test    eax, eax
0x180bc5b78  js      short loc_180BC5BEE
0x180bc5b7a  lea     this, [r14+0A48h]; this
0x180bc5b81  mov     rdx, [this+8]; _Whereptr
0x180bc5b85  cmp     rdx, [this+10h]
0x180bc5b89  jz      short loc_180BC5B95
0x180bc5b8b  mov     [rdx], rsi
0x180bc5b8e  add     qword ptr [this+8], 8
0x180bc5b93  jmp     short loc_180BC5B9F
0x180bc5b95  lea     r8, [rsp+110h+spMediaTrack]; <_Val_0>
0x180bc5b9a  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x180bc5b9f  lea     this, [rsp+110h+spNewMenuFlyoutItem]; this
  ... truncated ...
```
