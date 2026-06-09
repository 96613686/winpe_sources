# Windows::Networking::UX::Internal::MBCategory::~MBCategory(void)

- ea: `0x18000fa7c`
- end: `0x18000fd00`
- name: `??1MBCategory@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `644`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fa40`

## callees

- `0x180002150`
- `0x1800028d4`
- `0x180006208`
- `0x18000f9ac`
- `0x18000fa7c`
- `0x18000fde0`
- `0x18000fe58`
- `0x18001f5b8`
- `0x180024d3c`
- `0x1800252d4`
- `0x180026704`
- `0x18002d20c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fcb3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fcb3`
- `SHCORE!SHTaskPoolQueueTask` at `0x18000fb4c`
- `SHCORE!SHTaskPoolQueueTask` at `0x18000fbb8`
- `SHCORE!SHTaskPoolQueueTask` at `0x18000fb4c`
- `SHCORE!SHTaskPoolQueueTask` at `0x18000fbb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBCategory::~MBCategory(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  unsigned int v2; // esi
  void *v3; // rax
  void *v4; // rbx
  unsigned int v5; // esi
  void *v6; // rax
  void *v7; // rbx

  *(_QWORD *)this = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IUXCategory'};
  *((_QWORD *)this + 1) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IAvailableNetworkStore>'};
  *((_QWORD *)this + 25) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 26) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'};
  *((_QWORD *)this + 27) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IMBUXCategory'};
  *((_QWORD *)this + 28) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'};
  *((_QWORD *)this + 29) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 30) = &Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::Internal::IInterfaceNlmChangeListener'};
  Windows::Networking::UX::Internal::MBCategory::_CleanupConnectionFlow(this);
  v2 = *((_DWORD *)this + 178);
  v3 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v3);
    *(_QWORD *)v4 = &off_18005C3D8;
  }
  else
  {
    v4 = 0;
  }
  SHTaskPoolQueueTask(0, 258, v2, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_DWORD *)this + 179);
  v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v6);
    *(_QWORD *)v7 = &off_18005C3D8;
  }
  else
  {
    v7 = 0;
  }
  SHTaskPoolQueueTask(0, 258, v5, 0, v7, 0);
  if ( v7 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
  Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 960);
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>((char *)this + 944);
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>((char *)this + 928);
  std::unique_ptr<_WWAN_PIN_ACTION_RESULT>::~unique_ptr<_WWAN_PIN_ACTION_RESULT>((char *)this + 920);
  Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 896);
  Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 872);
  std::wstring::_Tidy_deallocate((char *)this + 840);
  std::wstring::_Tidy_deallocate((char *)this + 800);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease((char *)this + 792);
  std::wstring::_Tidy_deallocate((char *)this + 752);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 704);
  std::wstring::_Tidy_deallocate((char *)this + 672);
  std::wstring::_Tidy_deallocate((char *)this + 632);
  std::wstring::_Tidy_deallocate((char *)this + 432);
  std::wstring::_Tidy_deallocate((char *)this + 400);
  std::wstring::_Tidy_deallocate((char *)this + 368);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 360);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 352);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>((char *)this + 304);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 280);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 272);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 264);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>(this);
}

```

## disassembly

```asm
0x18000fa7c  mov     [rsp+arg_0], rbx
0x18000fa81  mov     [rsp+arg_8], rsi
0x18000fa86  push    rdi
0x18000fa87  sub     rsp, 30h
0x18000fa8b  mov     rdi, rcx
0x18000fa8e  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIUXCategory@234@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IUXCategory'}
0x18000fa95  mov     [rcx], rax
0x18000fa98  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIAvailableNetworkStore@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IAvailableNetworkStore>'}
0x18000fa9f  mov     [rcx+8], rax
0x18000faa3  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIWeakReferenceSource@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IWeakReferenceSource'}
0x18000faaa  mov     [rcx+0C8h], rax
0x18000fab1  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIMBCategory@Internal@UX@Networking@Windows@@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'}
0x18000fab8  mov     [rcx+0D0h], rax
0x18000fabf  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIMBUXCategory@234@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::IMBUXCategory'}
0x18000fac6  mov     [rcx+0D8h], rax
0x18000facd  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIMBConnectionFlowCallback@Internal@UX@Networking@Windows@@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>'}
0x18000fad4  mov     [rcx+0E0h], rax
0x18000fadb  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIInspectable@@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `IInspectable'}
0x18000fae2  mov     [rcx+0E8h], rax
0x18000fae9  lea     rax, ??_7MBCategory@Internal@UX@Networking@Windows@@6BIInterfaceNlmChangeListener@1234@@; const Windows::Networking::UX::Internal::MBCategory::`vftable'{for `Windows::Networking::UX::Internal::IInterfaceNlmChangeListener'}
0x18000faf0  mov     [rcx+0F0h], rax
0x18000faf7  call    ?_CleanupConnectionFlow@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::_CleanupConnectionFlow(void)
0x18000fafc  mov     esi, [rdi+2C8h]
0x18000fb02  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fb09  mov     ecx, 18h; unsigned __int64
0x18000fb0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fb13  mov     rbx, rax
0x18000fb16  test    rax, rax
0x18000fb19  jz      short loc_18000FB2F
0x18000fb1b  mov     rcx, rax
0x18000fb1e  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18000fb23  lea     rax, off_18005C3D8
0x18000fb2a  mov     [rbx], rax
0x18000fb2d  jmp     short loc_18000FB31
0x18000fb2f  xor     ebx, ebx
0x18000fb31  mov     [rsp+38h+var_10], 0
0x18000fb3a  mov     [rsp+38h+var_18], rbx
0x18000fb3f  xor     r9d, r9d
0x18000fb42  mov     r8d, esi
0x18000fb45  mov     edx, 102h
0x18000fb4a  xor     ecx, ecx
0x18000fb4c  call    cs:__imp_SHTaskPoolQueueTask
0x18000fb52  nop
0x18000fb53  test    rbx, rbx
0x18000fb56  jz      short loc_18000FB68
0x18000fb58  mov     rax, [rbx]
0x18000fb5b  mov     rcx, rbx
0x18000fb5e  mov     rax, [rax+10h]
0x18000fb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb67  nop
0x18000fb68  mov     esi, [rdi+2CCh]
0x18000fb6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fb75  mov     ecx, 18h; unsigned __int64
0x18000fb7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fb7f  mov     rbx, rax
0x18000fb82  test    rax, rax
0x18000fb85  jz      short loc_18000FB9B
0x18000fb87  mov     rcx, rax
0x18000fb8a  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18000fb8f  lea     rax, off_18005C3D8
0x18000fb96  mov     [rbx], rax
0x18000fb99  jmp     short loc_18000FB9D
0x18000fb9b  xor     ebx, ebx
0x18000fb9d  mov     [rsp+38h+var_10], 0
0x18000fba6  mov     [rsp+38h+var_18], rbx
0x18000fbab  xor     r9d, r9d
0x18000fbae  mov     r8d, esi
0x18000fbb1  mov     edx, 102h
0x18000fbb6  xor     ecx, ecx
0x18000fbb8  call    cs:__imp_SHTaskPoolQueueTask
0x18000fbbe  nop
0x18000fbbf  test    rbx, rbx
0x18000fbc2  jz      short loc_18000FBD4
0x18000fbc4  mov     rax, [rbx]
0x18000fbc7  mov     rcx, rbx
0x18000fbca  mov     rax, [rax+10h]
0x18000fbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbd3  nop
0x18000fbd4  lea     rcx, [rdi+3C0h]
0x18000fbdb  call    ??1?$EventSource@UIMbConnectionProfileUpdatedEventHandler@UX@Networking@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18000fbe0  lea     rcx, [rdi+3B0h]
0x18000fbe7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>(void)
0x18000fbec  lea     rcx, [rdi+3A0h]
0x18000fbf3  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>(void)
0x18000fbf8  lea     rcx, [rdi+398h]
0x18000fbff  call    ??1?$unique_ptr@U_WWAN_PIN_ACTION_RESULT@@U?$default_delete@U_WWAN_PIN_ACTION_RESULT@@@std@@@std@@QEAA@XZ; std::unique_ptr<_WWAN_PIN_ACTION_RESULT>::~unique_ptr<_WWAN_PIN_ACTION_RESULT>(void)
0x18000fc04  lea     rcx, [rdi+380h]
0x18000fc0b  call    ??1?$EventSource@UIMbConnectionProfileUpdatedEventHandler@UX@Networking@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18000fc10  lea     rcx, [rdi+368h]
0x18000fc17  call    ??1?$EventSource@UIMbConnectionProfileUpdatedEventHandler@UX@Networking@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Networking::UX::IMbConnectionProfileUpdatedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18000fc1c  lea     rcx, [rdi+348h]
0x18000fc23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc28  lea     rcx, [rdi+320h]
0x18000fc2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc34  lea     rcx, [rdi+318h]
0x18000fc3b  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18000fc40  lea     rcx, [rdi+2F0h]
0x18000fc47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc4c  lea     rcx, [rdi+2C0h]
0x18000fc53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fc58  lea     rcx, [rdi+2A0h]
0x18000fc5f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc64  lea     rcx, [rdi+278h]
0x18000fc6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc70  lea     rcx, [rdi+1B0h]
0x18000fc77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc7c  lea     rcx, [rdi+190h]
0x18000fc83  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc88  lea     rcx, [rdi+170h]
0x18000fc8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc94  lea     rcx, [rdi+168h]
0x18000fc9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fca0  lea     rcx, [rdi+160h]
0x18000fca7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fcac  lea     rcx, [rdi+138h]; lpCriticalSection
0x18000fcb3  call    cs:__imp_DeleteCriticalSection
0x18000fcb9  lea     rcx, [rdi+130h]
0x18000fcc0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18000fcc5  lea     rcx, [rdi+118h]
0x18000fccc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fcd1  lea     rcx, [rdi+110h]
0x18000fcd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fcdd  lea     rcx, [rdi+108h]
0x18000fce4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fce9  mov     rcx, rdi; this
0x18000fcec  mov     rbx, [rsp+38h+arg_0]
0x18000fcf1  mov     rsi, [rsp+38h+arg_8]
0x18000fcf6  add     rsp, 30h
0x18000fcfa  pop     rdi
0x18000fcfb  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@5678@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>(void)
```
