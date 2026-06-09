# CXAMLHostWindow::_ReleaseXAMLContent(void)

- ea: `0x18002f834`
- end: `0x18002f9a5`
- name: `?_ReleaseXAMLContent@CXAMLHostWindow@@AEAAXXZ`
- size: `369`
- prototype: `void __fastcall(CXAMLHostWindow *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002f9f0`

## callees

- `0x180007b3c`
- `0x18002a1bc`
- `0x18002e660`
- `0x18002f834`
- `0x180030cd4`
- `0x18003ec4c`
- `0x1800655cc`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x18002f909`
- `SHCORE!IUnknown_SetSite` at `0x18002f909`
- `SHCORE!__imp_SHRemoveWindowSubclass` at `0x18002f935`
- `SHCORE!__imp_SHRemoveWindowSubclass` at `0x18002f935`
- `ext-ms-win-uiacore-l1-1-2!UiaDisconnectAllProviders` at `0x18002f955`
- `ext-ms-win-uiacore-l1-1-2!UiaDisconnectAllProviders` at `0x18002f955`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CXAMLHostWindow::_ReleaseXAMLContent(CXAMLHostWindow *this)
{
  char *v2; // rbx
  struct INotificationDispatcher *v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v2 = (char *)this + 248;
  if ( *((_QWORD *)this + 31) )
  {
    if ( *((_QWORD *)this + 55) )
    {
      v4 = 0;
      if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Xaml::IUIElement>::As<Windows::UI::Xaml::IFrameworkElement>(
                  (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 31,
                  (__int64)&v4) >= 0 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 400LL))(v4, *((_QWORD *)this + 55));
        *((_QWORD *)this + 55) = 0;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v4);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v2);
  }
  CXAMLHostWindow::_DrainXAMLEventQueue(this);
  v3 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v3);
  if ( (int)CNotificationDispatcher::GetForCurrentThread(&v3) >= 0 )
    (*(void (__fastcall **)(struct INotificationDispatcher *))(*(_QWORD *)v3 + 40LL))(v3);
  IInspectable_SetSite(*((_QWORD *)this + 30), 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 240);
  IUnknown_SetSite(*((IUnknown **)this + 32), 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 256);
  if ( *((_QWORD *)this + 29) )
  {
    SHRemoveWindowSubclass(*((_QWORD *)this + 24), CXAMLHostWindow::s_SubclassWndProc, 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 29) + 56LL))(*((_QWORD *)this + 29), 0);
    if ( !*((_BYTE *)this + 504) )
      UiaDisconnectAllProviders();
    CXAMLHostWindow::_DrainXAMLEventQueue(this);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 232);
  }
  if ( *((_BYTE *)this + 449) )
  {
    if ( _InterlockedExchangeAdd(&g_cRegistrationCount, 0xFFFFFFFF) == 1 )
      SearchUI::SearchBoxControlBase::UnregisterDependencyProperties();
    *((_BYTE *)this + 449) = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v3);
}

```

## disassembly

```asm
0x18002f834  mov     [rsp+arg_10], rbx
0x18002f839  push    rdi
0x18002f83a  sub     rsp, 20h
0x18002f83e  mov     rdi, rcx
0x18002f841  lea     rbx, [rcx+0F8h]
0x18002f848  cmp     qword ptr [rbx], 0
0x18002f84c  jz      short loc_18002F8AA
0x18002f84e  cmp     qword ptr [rcx+1B8h], 0
0x18002f856  jz      short loc_18002F8A2
0x18002f858  mov     [rsp+28h+arg_8], 0
0x18002f861  lea     rdx, [rsp+28h+arg_8]
0x18002f866  mov     rcx, rbx
0x18002f869  call    ??$As@UIFrameworkElement@Xaml@UI@Windows@@@?$ComPtr@UIUIElement@Xaml@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIFrameworkElement@Xaml@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::IUIElement>::As<Windows::UI::Xaml::IFrameworkElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Xaml::IFrameworkElement>>)
0x18002f86e  test    eax, eax
0x18002f870  js      short loc_18002F898
0x18002f872  mov     rcx, [rsp+28h+arg_8]
0x18002f877  mov     rax, [rcx]
0x18002f87a  mov     rdx, [rdi+1B8h]
0x18002f881  mov     rax, [rax+190h]
0x18002f888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f88d  mov     qword ptr [rdi+1B8h], 0
0x18002f898  lea     rcx, [rsp+28h+arg_8]
0x18002f89d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f8a2  mov     rcx, rbx
0x18002f8a5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f8aa  mov     rcx, rdi; this
0x18002f8ad  call    ?_DrainXAMLEventQueue@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_DrainXAMLEventQueue(void)
0x18002f8b2  mov     [rsp+28h+arg_0], 0
0x18002f8bb  lea     rcx, [rsp+28h+arg_0]
0x18002f8c0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f8c5  lea     rcx, [rsp+28h+arg_0]; struct INotificationDispatcher **
0x18002f8ca  call    ?GetForCurrentThread@CNotificationDispatcher@@SAJPEAPEAUINotificationDispatcher@@@Z; CNotificationDispatcher::GetForCurrentThread(INotificationDispatcher * *)
0x18002f8cf  test    eax, eax
0x18002f8d1  js      short loc_18002F8E4
0x18002f8d3  mov     rcx, [rsp+28h+arg_0]
0x18002f8d8  mov     rax, [rcx]
0x18002f8db  mov     rax, [rax+28h]
0x18002f8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8e4  lea     rbx, [rdi+0F0h]
0x18002f8eb  xor     edx, edx
0x18002f8ed  mov     rcx, [rbx]
0x18002f8f0  call    IInspectable_SetSite
0x18002f8f5  mov     rcx, rbx
0x18002f8f8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f8fd  lea     rbx, [rdi+100h]
0x18002f904  xor     edx, edx; punkSite
0x18002f906  mov     rcx, [rbx]; punk
0x18002f909  call    cs:__imp_IUnknown_SetSite
0x18002f90f  mov     rcx, rbx
0x18002f912  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f917  lea     rbx, [rdi+0E8h]
0x18002f91e  cmp     qword ptr [rbx], 0
0x18002f922  jz      short loc_18002F96B
0x18002f924  xor     r8d, r8d
0x18002f927  lea     rdx, ?s_SubclassWndProc@CXAMLHostWindow@@CA_JPEAUHWND__@@I_K_J11@Z; CXAMLHostWindow::s_SubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x18002f92e  mov     rcx, [rdi+0C0h]
0x18002f935  call    cs:__imp_SHRemoveWindowSubclass
0x18002f93b  mov     rcx, [rbx]
0x18002f93e  mov     rax, [rcx]
0x18002f941  xor     edx, edx
0x18002f943  mov     rax, [rax+38h]
0x18002f947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f94c  cmp     byte ptr [rdi+1F8h], 0
0x18002f953  jnz     short loc_18002F95B
0x18002f955  call    cs:__imp_UiaDisconnectAllProviders
0x18002f95b  mov     rcx, rdi; this
0x18002f95e  call    ?_DrainXAMLEventQueue@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_DrainXAMLEventQueue(void)
0x18002f963  mov     rcx, rbx
0x18002f966  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f96b  cmp     byte ptr [rdi+1C1h], 0
0x18002f972  jz      short loc_18002F990
0x18002f974  or      eax, 0FFFFFFFFh
0x18002f977  lock xadd cs:?g_cRegistrationCount@@3JA, eax; long g_cRegistrationCount
0x18002f97f  cmp     eax, 1
0x18002f982  jnz     short loc_18002F989
0x18002f984  call    ?UnregisterDependencyProperties@SearchBoxControlBase@SearchUI@@SAXXZ; SearchUI::SearchBoxControlBase::UnregisterDependencyProperties(void)
0x18002f989  mov     byte ptr [rdi+1C1h], 0
0x18002f990  lea     rcx, [rsp+28h+arg_0]
0x18002f995  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002f99a  mov     rbx, [rsp+28h+arg_10]
0x18002f99f  add     rsp, 20h
0x18002f9a3  pop     rdi
0x18002f9a4  retn
```
