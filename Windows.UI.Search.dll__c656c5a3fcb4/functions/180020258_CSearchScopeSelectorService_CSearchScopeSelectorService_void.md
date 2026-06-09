# CSearchScopeSelectorService::~CSearchScopeSelectorService(void)

- ea: `0x180020258`
- end: `0x18002039e`
- name: `??1CSearchScopeSelectorService@@EEAA@XZ`
- size: `326`
- prototype: `void __fastcall(CSearchScopeSelectorService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020870`

## callees

- `0x180007b3c`
- `0x1800120dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002037b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002037b`

## pseudocode

```c
void __fastcall CSearchScopeSelectorService::~CSearchScopeSelectorService(CSearchScopeSelectorService *this)
{
  *(_QWORD *)this = &CSearchScopeSelectorService::`vftable';
  *((_QWORD *)this + 3) = &CSearchScopeSelectorService::`vftable'{for `IViewService'};
  *((_QWORD *)this + 4) = &CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider,IImmersiveApplicationNotification,Windows::UI::Search::Internal::Common::IScopeChangedEventHandler,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxSuggestionsRequestedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQuerySubmittedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>,ISearchScopeSelector>'};
  *((_QWORD *)this + 5) = &CSearchScopeSelectorService::`vftable'{for `IImmersiveApplicationNotification'};
  *((_QWORD *)this + 6) = &CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::UI::Search::Internal::Common::IScopeChangedEventHandler,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxSuggestionsRequestedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQuerySubmittedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>,ISearchScopeSelector>'};
  *((_QWORD *)this + 7) = &CSearchScopeSelectorService::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxSuggestionsRequestedEventArgs *>'};
  *((_QWORD *)this + 8) = &CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQuerySubmittedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>,ISearchScopeSelector>'};
  *((_QWORD *)this + 9) = &CSearchScopeSelectorService::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>'};
  *((_QWORD *)this + 10) = &CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchScopeSelector>'};
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 272);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 216);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 200);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 192);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 184);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 176);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 168);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 160);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 152);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 144);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 136);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 128);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 120);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 112);
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 23) = -1073741823;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 16);
}

```

## disassembly

```asm
0x180020258  push    rbx
0x18002025a  sub     rsp, 20h
0x18002025e  lea     rax, ??_7CSearchScopeSelectorService@@6B@; const CSearchScopeSelectorService::`vftable'
0x180020265  mov     rbx, rcx
0x180020268  mov     [rcx], rax
0x18002026b  lea     rax, ??_7CSearchScopeSelectorService@@6BIViewService@@@; const CSearchScopeSelectorService::`vftable'{for `IViewService'}
0x180020272  mov     [rcx+18h], rax
0x180020276  lea     rax, ??_7CSearchScopeSelectorService@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIServiceProvider@@UIImmersiveApplicationNotification@@UIScopeChangedEventHandler@Common@Internal@Search@UI@Windows@@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxSuggestionsRequestedEventArgs@2345@@Foundation@Windows@@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxQuerySubmittedEventArgs@2345@@Foundation@Windows@@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxResultSuggestionChosenEventArgs@2345@@Foundation@Windows@@UISearchScopeSelector@@@Details@WRL@Microsoft@@@; const CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider,IImmersiveApplicationNotification,Windows::UI::Search::Internal::Common::IScopeChangedEventHandler,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxSuggestionsRequestedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQuerySubmittedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>,ISearchScopeSelector>'}
0x18002027d  mov     [rcx+20h], rax
0x180020281  lea     rax, ??_7CSearchScopeSelectorService@@6BIImmersiveApplicationNotification@@@; const CSearchScopeSelectorService::`vftable'{for `IImmersiveApplicationNotification'}
0x180020288  mov     [rcx+28h], rax
0x18002028c  lea     rax, ??_7CSearchScopeSelectorService@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIScopeChangedEventHandler@Common@Internal@Search@UI@Windows@@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxSuggestionsRequestedEventArgs@2345@@Foundation@9@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxQuerySubmittedEventArgs@2345@@Foundation@9@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxResultSuggestionChosenEventArgs@2345@@Foundation@9@UISearchScopeSelector@@@Details@WRL@Microsoft@@@; const CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::UI::Search::Internal::Common::IScopeChangedEventHandler,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxSuggestionsRequestedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQuerySubmittedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>,ISearchScopeSelector>'}
0x180020293  mov     [rcx+30h], rax
0x180020297  lea     rax, ??_7CSearchScopeSelectorService@@6B?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxSuggestionsRequestedEventArgs@2345@@Foundation@Windows@@@; const CSearchScopeSelectorService::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxSuggestionsRequestedEventArgs *>'}
0x18002029e  mov     [rcx+38h], rax
0x1800202a2  lea     rax, ??_7CSearchScopeSelectorService@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxQuerySubmittedEventArgs@2345@@Foundation@Windows@@U?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxResultSuggestionChosenEventArgs@2345@@56@UISearchScopeSelector@@@Details@WRL@Microsoft@@@; const CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxQuerySubmittedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>,ISearchScopeSelector>'}
0x1800202a9  mov     [rcx+40h], rax
0x1800202ad  lea     rax, ??_7CSearchScopeSelectorService@@6B?$ITypedEventHandler@PEAVSearchBox@Controls@Xaml@UI@Windows@@PEAVSearchBoxResultSuggestionChosenEventArgs@2345@@Foundation@Windows@@@; const CSearchScopeSelectorService::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::SearchBox *,Windows::UI::Xaml::Controls::SearchBoxResultSuggestionChosenEventArgs *>'}
0x1800202b4  mov     [rcx+48h], rax
0x1800202b8  lea     rax, ??_7CSearchScopeSelectorService@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISearchScopeSelector@@@Details@WRL@Microsoft@@@; const CSearchScopeSelectorService::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchScopeSelector>'}
0x1800202bf  mov     [rcx+50h], rax
0x1800202c3  add     rcx, 110h
0x1800202ca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800202cf  lea     rcx, [rbx+0D8h]
0x1800202d6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800202db  lea     rcx, [rbx+0C8h]
0x1800202e2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800202e7  lea     rcx, [rbx+0C0h]
0x1800202ee  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800202f3  lea     rcx, [rbx+0B8h]
0x1800202fa  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800202ff  lea     rcx, [rbx+0B0h]
0x180020306  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002030b  lea     rcx, [rbx+0A8h]
0x180020312  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180020317  lea     rcx, [rbx+0A0h]
0x18002031e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180020323  lea     rcx, [rbx+98h]
0x18002032a  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002032f  lea     rcx, [rbx+90h]
0x180020336  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002033b  lea     rcx, [rbx+88h]
0x180020342  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180020347  lea     rcx, [rbx+80h]
0x18002034e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180020353  lea     rcx, [rbx+78h]
0x180020357  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002035c  lea     rcx, [rbx+70h]
0x180020360  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180020365  mov     rcx, [rbx+68h]; string
0x180020369  call    cs:__imp_WindowsDeleteString
0x18002036f  mov     qword ptr [rbx+68h], 0
0x180020377  mov     rcx, [rbx+60h]; string
0x18002037b  call    cs:__imp_WindowsDeleteString
0x180020381  mov     qword ptr [rbx+60h], 0
0x180020389  lea     rcx, [rbx+10h]
0x18002038d  mov     dword ptr [rbx+5Ch], 0C0000001h
0x180020394  add     rsp, 20h
0x180020398  pop     rbx
0x180020399  jmp     ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
```
