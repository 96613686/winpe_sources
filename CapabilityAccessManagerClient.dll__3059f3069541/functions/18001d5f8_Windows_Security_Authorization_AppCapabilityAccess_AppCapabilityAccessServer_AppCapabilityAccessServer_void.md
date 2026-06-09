# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::~AppCapabilityAccessServer(void)

- ea: `0x18001d5f8`
- end: `0x18001d73c`
- name: `??1AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@UEAA@XZ`
- size: `324`
- prototype: `void(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014d20`

## callees

- `0x18000aa04`
- `0x18000c6c8`
- `0x180013df8`
- `0x1800141fc`
- `0x180014318`
- `0x18001b5ac`
- `0x18001d5f8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001d63f`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001d63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d6bd`

## string_xrefs

- `0x18001d729`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::~AppCapabilityAccessServer(
        RTL_SRWLOCK *this)
{
  Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *v1; // rdi
  unsigned __int64 v2; // rbx
  BOOLEAN v3; // al
  __int64 v4; // rcx
  int v5; // eax
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  v1 = (Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *)this;
  this->Ptr = &Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Windows::Security::Authorization::AppCapabilityAccess::IAppCapability'};
  this[1].Ptr = &Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2,Microsoft::WRL::FtmBase>'};
  this[2].Ptr = &Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2'};
  this[3].Ptr = &Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (unsigned __int64)&this[17];
  v3 = TryAcquireSRWLockExclusive(this + 17);
  try
  {
    v11 = v2 & -(__int64)(v3 != 0);
    if ( v11 )
    {
      if ( *((_BYTE *)v1 + 233) )
      {
        if ( *((_BYTE *)v1 + 232) )
        {
          v4 = *((_QWORD *)v1 + 15);
          if ( v4 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 72LL))(v4, 0);
            if ( v5 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1B,
                (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
                (const char *)(unsigned int)v5,
                v7);
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
      v6);
    v1 = (Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *)this;
  }
  wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>::~AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>((_QWORD *)v1 + 20);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)v1 + 152);
  WindowsDeleteString(*((HSTRING *)v1 + 16));
  *((_QWORD *)v1 + 16) = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 120);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 112);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 104);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 96);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 88);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 80);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v1 + 72);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *>,Microsoft::WRL::FtmBase>((__int64)v1);
}

```

## disassembly

```asm
0x18001d5f8  mov     [rsp+arg_10], rbx
0x18001d5fd  mov     [rsp+arg_0], rcx
0x18001d602  push    rdi; int
0x18001d603  sub     rsp, 20h
0x18001d607  mov     rdi, rcx
0x18001d60a  lea     rax, ??_7AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@6BIAppCapability@1234@@; const Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Windows::Security::Authorization::AppCapabilityAccess::IAppCapability'}
0x18001d611  mov     [rcx], rax
0x18001d614  lea     rax, ??_7AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppCapability2@AppCapabilityAccess@Authorization@Security@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2,Microsoft::WRL::FtmBase>'}
0x18001d61b  mov     [rcx+8], rax
0x18001d61f  lea     rax, ??_7AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@6BIAppCapability2@1234@@; const Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2'}
0x18001d626  mov     [rcx+10h], rax
0x18001d62a  lea     rax, ??_7AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001d631  mov     [rcx+18h], rax
0x18001d635  lea     rbx, [rcx+88h]
0x18001d63c  mov     rcx, rbx; SRWLock
0x18001d63f  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001d645  neg     al
0x18001d647  sbb     rcx, rcx
0x18001d64a  and     rcx, rbx
0x18001d64d  mov     [rsp+28h+arg_8], rcx
0x18001d652  jz      short loc_18001D68A
0x18001d654  cmp     byte ptr [rdi+0E9h], 0
0x18001d65b  jz      short loc_18001D68A
0x18001d65d  cmp     byte ptr [rdi+0E8h], 0
0x18001d664  jz      short loc_18001D68A
0x18001d666  mov     rcx, [rdi+78h]
0x18001d66a  test    rcx, rcx
0x18001d66d  jz      short loc_18001D68A
0x18001d66f  mov     rax, [rcx]
0x18001d672  xor     edx, edx
0x18001d674  mov     rax, [rax+48h]
0x18001d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d67d  mov     rcx, [rsp+28h]; this
0x18001d682  test    eax, eax
0x18001d684  js      loc_18001D726
0x18001d68a  lea     rcx, [rsp+28h+arg_8]
0x18001d68f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d694  nop
0x18001d695  jmp     short loc_18001D69C
0x18001d697  mov     rdi, [rsp+28h+arg_0]
0x18001d69c  lea     rcx, [rdi+0A0h]
0x18001d6a3  call    ??1?$AsyncEventSourceT@U?$ITypedEventHandler@PEAVAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@PEAVAppCapabilityAccessChangedEventArgs@2345@@Foundation@Windows@@VGitEventSourceSupportsAgile@Internal@3@U?$InvokeModeOptions@$01@WRL@Microsoft@@$00Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>::~AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>(void)
0x18001d6a8  nop
0x18001d6a9  lea     rcx, [rdi+98h]
0x18001d6b0  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001d6b5  nop
0x18001d6b6  mov     rcx, [rdi+80h]; string
0x18001d6bd  call    cs:__imp_WindowsDeleteString
0x18001d6c3  mov     qword ptr [rdi+80h], 0
0x18001d6ce  lea     rcx, [rdi+78h]
0x18001d6d2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d6d7  nop
0x18001d6d8  lea     rcx, [rdi+70h]
0x18001d6dc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d6e1  nop
0x18001d6e2  lea     rcx, [rdi+68h]
0x18001d6e6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d6eb  nop
0x18001d6ec  lea     rcx, [rdi+60h]
0x18001d6f0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d6f5  nop
0x18001d6f6  lea     rcx, [rdi+58h]
0x18001d6fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d6ff  nop
0x18001d700  lea     rcx, [rdi+50h]
0x18001d704  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d709  nop
0x18001d70a  lea     rcx, [rdi+48h]
0x18001d70e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d713  nop
0x18001d714  mov     rcx, rdi
0x18001d717  mov     rbx, [rsp+28h+arg_10]
0x18001d71c  add     rsp, 20h
0x18001d720  pop     rdi
0x18001d721  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *>,Microsoft::WRL::FtmBase>(void)
0x18001d726  mov     r9d, eax; char *
0x18001d729  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001d730  mov     edx, 1Bh; void *
0x18001d735  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
