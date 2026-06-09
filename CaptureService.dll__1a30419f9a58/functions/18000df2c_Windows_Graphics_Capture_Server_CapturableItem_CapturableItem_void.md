# Windows::Graphics::Capture::Server::CapturableItem::~CapturableItem(void)

- ea: `0x18000df2c`
- end: `0x18000e03d`
- name: `??1CapturableItem@Server@Capture@Graphics@Windows@@UEAA@XZ`
- size: `273`
- prototype: `void __fastcall(Windows::Graphics::Capture::Server::CapturableItem *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e830`

## callees

- `0x180005568`
- `0x18000dcb4`
- `0x18000ddc4`
- `0x18000dec8`
- `0x18000df2c`
- `0x180017ac0`
- `0x180017bfc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df8c`

## string_xrefs

- `0x18000dfdc`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18000e02b`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Graphics::Capture::Server::CapturableItem::~CapturableItem(
        Windows::Graphics::Capture::Server::CapturableItem *this)
{
  RTL_SRWLOCK *v2; // rbx
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Graphics::Capture::Server::CapturableItem::`vftable';
  *((_QWORD *)this + 1) = &Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFastRundown>'};
  *((_QWORD *)this + 2) = &Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>'};
  *((_QWORD *)this + 3) = &Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapturableItemCom>'};
  *((_QWORD *)this + 4) = &Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>'};
  *((_QWORD *)this + 5) = &Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>'};
  *((_QWORD *)this + 6) = &Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Capture::Server::ICapturableItem>'};
  v2 = (RTL_SRWLOCK *)((char *)this + 112);
  AcquireSRWLockExclusive((PSRWLOCK)this + 14);
  v9 = v2;
  v3 = (_QWORD *)((char *)this + 80);
  v4 = *((_QWORD *)this + 10);
  if ( v4 )
  {
    if ( *((_QWORD *)this + 12) )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 88LL))(v4);
      if ( v5 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v5,
          v7);
    }
  }
  if ( *v3 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 64LL))(*v3);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)this + 11);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 10);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 9);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>((__int64)this);
}

```

## disassembly

```asm
0x18000df2c  mov     [rsp+arg_8], rbx
0x18000df31  push    rdi; int
0x18000df32  sub     rsp, 20h
0x18000df36  mov     rdi, rcx
0x18000df39  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'
0x18000df40  mov     [rcx], rax
0x18000df43  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFastRundown@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFastRundown>'}
0x18000df4a  mov     [rcx+8], rax
0x18000df4e  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UICapturableItemCom@@@23@U?$CloakedIid@UICapturableItemCom_Old@@@23@U?$CloakedIid@UICapturableItemClosedHandler@Server@Capture@Graphics@Windows@@@23@UICapturableItem@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>'}
0x18000df55  mov     [rcx+10h], rax
0x18000df59  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapturableItemCom@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapturableItemCom>'}
0x18000df60  mov     [rcx+18h], rax
0x18000df64  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UICapturableItemCom_Old@@@23@U?$CloakedIid@UICapturableItemClosedHandler@Server@Capture@Graphics@Windows@@@23@UICapturableItem@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>'}
0x18000df6b  mov     [rcx+20h], rax
0x18000df6f  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapturableItemClosedHandler@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>'}
0x18000df76  mov     [rcx+28h], rax
0x18000df7a  lea     rax, ??_7CapturableItem@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapturableItem@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CapturableItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Capture::Server::ICapturableItem>'}
0x18000df81  mov     [rcx+30h], rax
0x18000df85  lea     rbx, [rcx+70h]
0x18000df89  mov     rcx, rbx; SRWLock
0x18000df8c  call    cs:__imp_AcquireSRWLockExclusive
0x18000df92  mov     [rsp+28h+arg_0], rbx
0x18000df97  lea     rbx, [rdi+50h]
0x18000df9b  mov     rcx, [rbx]
0x18000df9e  test    rcx, rcx
0x18000dfa1  jz      short loc_18000DFBC
0x18000dfa3  mov     rdx, [rdi+60h]
0x18000dfa7  test    rdx, rdx
0x18000dfaa  jz      short loc_18000DFBC
0x18000dfac  mov     rax, [rcx]
0x18000dfaf  mov     rax, [rax+58h]
0x18000dfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfb8  test    eax, eax
0x18000dfba  js      short loc_18000E023
0x18000dfbc  mov     rcx, [rbx]
0x18000dfbf  test    rcx, rcx
0x18000dfc2  jz      short loc_18000DFED
0x18000dfc4  mov     rax, [rcx]
0x18000dfc7  mov     rax, [rax+40h]
0x18000dfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd0  test    eax, eax
0x18000dfd2  jns     short loc_18000DFED
0x18000dfd4  mov     rcx, [rsp+28h]; this
0x18000dfd9  mov     r9d, eax; char *
0x18000dfdc  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000dfe3  mov     edx, 168h; void *
0x18000dfe8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dfed  lea     rcx, [rsp+28h+arg_0]
0x18000dff2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000dff7  lea     rcx, [rdi+58h]
0x18000dffb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e000  mov     rcx, rbx
0x18000e003  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18000e008  lea     rcx, [rdi+48h]
0x18000e00c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18000e011  mov     rcx, rdi
0x18000e014  mov     rbx, [rsp+28h+arg_8]
0x18000e019  add     rsp, 20h
0x18000e01d  pop     rdi
0x18000e01e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIFastRundown@@@23@U?$CloakedIid@UICapturableItemCom@@@23@U?$CloakedIid@UICapturableItemCom_Old@@@23@U?$CloakedIid@UICapturableItemClosedHandler@Server@Capture@Graphics@Windows@@@23@UICapturableItem@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>(void)
0x18000e023  mov     rcx, [rsp+28h]; this
0x18000e028  mov     r9d, eax; char *
0x18000e02b  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000e032  mov     edx, 162h; void *
0x18000e037  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
