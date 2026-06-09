# Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::~SecondaryTileUserNotifierServer(void)

- ea: `0x18001e6bc`
- end: `0x18001e73c`
- name: `??1SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAA@XZ`
- size: `128`
- prototype: `void __fastcall(Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ea10`

## callees

- `0x18001e5b4`
- `0x18001e5dc`
- `0x18001e660`
- `0x180020028`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e70a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e70a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e71c`

## pseudocode

```c
void __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::~SecondaryTileUserNotifierServer(
        Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *this)
{
  unsigned int v2; // edx

  *(_QWORD *)this = &Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
    (char *)this + 80,
    0);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 88);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(
    (wil::details::event_watcher_state **)this + 10,
    v2);
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001e6bc  mov     [rsp+arg_0], rbx
0x18001e6c1  push    rdi
0x18001e6c2  sub     rsp, 20h
0x18001e6c6  lea     rax, ??_7SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@6B@; const Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::`vftable'
0x18001e6cd  mov     rdi, rcx
0x18001e6d0  mov     [rcx], rax
0x18001e6d3  xor     edx, edx
0x18001e6d5  lea     rax, ??_7SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::`vftable'{for `IWeakReferenceSource'}
0x18001e6dc  mov     [rcx+8], rax
0x18001e6e0  lea     rax, ??_7SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001e6e7  mov     [rcx+10h], rax
0x18001e6eb  add     rcx, 50h ; 'P'
0x18001e6ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18001e6f4  lea     rcx, [rdi+58h]
0x18001e6f8  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18001e6fd  lea     rcx, [rdi+50h]
0x18001e701  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x18001e706  mov     rcx, [rdi+48h]; string
0x18001e70a  call    cs:__imp_WindowsDeleteString
0x18001e710  mov     qword ptr [rdi+48h], 0
0x18001e718  mov     rcx, [rdi+40h]; string
0x18001e71c  call    cs:__imp_WindowsDeleteString
0x18001e722  mov     rcx, rdi
0x18001e725  mov     qword ptr [rdi+40h], 0
0x18001e72d  mov     rbx, [rsp+28h+arg_0]
0x18001e732  add     rsp, 20h
0x18001e736  pop     rdi
0x18001e737  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserChangedEventArgs@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>(void)
```
