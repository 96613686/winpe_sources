# Windows::Graphics::Capture::Server::CaptureSession::~CaptureSession(void)

- ea: `0x18001c1b8`
- end: `0x18001c315`
- name: `??1CaptureSession@Server@Capture@Graphics@Windows@@UEAA@XZ`
- size: `349`
- prototype: `void __fastcall(Windows::Graphics::Capture::Server::CaptureSession *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e870`

## callees

- `0x180005568`
- `0x18000dcd4`
- `0x18000ddc4`
- `0x18000dec8`
- `0x180017ac0`
- `0x180017bfc`
- `0x18001881c`
- `0x18001892c`
- `0x18001c1b8`
- `0x18001d4b0`
- `0x18001e1e0`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c235`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c235`

## string_xrefs

- `0x18001c21a`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`
- `0x18001c303`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Graphics::Capture::Server::CaptureSession::~CaptureSession(
        Windows::Graphics::Capture::Server::CaptureSession *this)
{
  Windows::Graphics::Capture::Server::CaptureSession *v2; // rcx
  int v3; // eax
  Windows::Graphics::Capture::Server::CaptureSessionManager *v4; // rcx
  __int64 *v5; // r14
  int v6; // eax
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IFastRundown>,IWeakReferenceSource,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>'};
  *((_QWORD *)this + 2) = &Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>'};
  *((_QWORD *)this + 4) = &Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICaptureSessionCom_Old>'};
  v2 = (Windows::Graphics::Capture::Server::CaptureSession *)((char *)this + 40);
  *(_QWORD *)v2 = &Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Capture::Server::ICaptureSession>'};
  v3 = Windows::Graphics::Capture::Server::CaptureSession::StopCapture(v2);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
      (const char *)(unsigned int)v3,
      v8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 18);
  v10 = (RTL_SRWLOCK *)((char *)this + 144);
  v5 = (__int64 *)((char *)this + 88);
  if ( *((_QWORD *)this + 11) )
  {
    v6 = Windows::Graphics::Capture::Server::CaptureSessionManager::UnregisterCaptureSession(v4, this);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
        (const char *)(unsigned int)v6,
        v8);
    v7 = *v5;
    *v5 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 96,
    0);
  wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset((char *)this + 80);
  Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 16);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 15);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 14);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)this + 12);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 11);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 10);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 9);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)this + 8);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>((__int64)this);
}

```

## disassembly

```asm
0x18001c1b8  push    rbx
0x18001c1ba  push    rsi
0x18001c1bb  push    rdi
0x18001c1bc  push    r14
0x18001c1be  sub     rsp, 28h
0x18001c1c2  mov     rsi, rcx
0x18001c1c5  lea     rax, ??_7CaptureSession@Server@Capture@Graphics@Windows@@6BIInspectable@@@; const Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `IInspectable'}
0x18001c1cc  mov     [rcx], rax
0x18001c1cf  lea     rax, ??_7CaptureSession@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIFastRundown@@@23@UIWeakReferenceSource@@U?$CloakedIid@UICaptureSessionCom@@@23@U?$CloakedIid@UICaptureSessionCom_Old@@@23@UICaptureSession@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IFastRundown>,IWeakReferenceSource,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>'}
0x18001c1d6  mov     [rcx+8], rax
0x18001c1da  lea     rax, ??_7CaptureSession@Server@Capture@Graphics@Windows@@6BIWeakReferenceSource@@@; const Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `IWeakReferenceSource'}
0x18001c1e1  mov     [rcx+10h], rax
0x18001c1e5  lea     rax, ??_7CaptureSession@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UICaptureSessionCom@@@23@U?$CloakedIid@UICaptureSessionCom_Old@@@23@UICaptureSession@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>'}
0x18001c1ec  mov     [rcx+18h], rax
0x18001c1f0  lea     rax, ??_7CaptureSession@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICaptureSessionCom_Old@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICaptureSessionCom_Old>'}
0x18001c1f7  mov     [rcx+20h], rax
0x18001c1fb  add     rcx, 28h ; '('; this
0x18001c1ff  lea     rax, ??_7CaptureSession@Server@Capture@Graphics@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICaptureSession@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@@; const Windows::Graphics::Capture::Server::CaptureSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Capture::Server::ICaptureSession>'}
0x18001c206  mov     [rcx], rax
0x18001c209  call    ?StopCapture@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJXZ; Windows::Graphics::Capture::Server::CaptureSession::StopCapture(void)
0x18001c20e  mov     rcx, [rsp+48h]; this
0x18001c213  test    eax, eax
0x18001c215  jns     short loc_18001C22B
0x18001c217  mov     r9d, eax; char *
0x18001c21a  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001c221  mov     edx, 13h; void *
0x18001c226  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c22b  lea     rbx, [rsi+90h]
0x18001c232  mov     rcx, rbx; SRWLock
0x18001c235  call    cs:__imp_AcquireSRWLockExclusive
0x18001c23b  mov     [rsp+48h+arg_0], rbx
0x18001c240  lea     r14, [rsi+58h]
0x18001c244  cmp     qword ptr [r14], 0
0x18001c248  jz      short loc_18001C27B
0x18001c24a  mov     rdx, rsi; struct Windows::Graphics::Capture::Server::CaptureSession *
0x18001c24d  call    ?UnregisterCaptureSession@CaptureSessionManager@Server@Capture@Graphics@Windows@@QEAAJPEAVCaptureSession@2345@@Z; Windows::Graphics::Capture::Server::CaptureSessionManager::UnregisterCaptureSession(Windows::Graphics::Capture::Server::CaptureSession *)
0x18001c252  mov     rcx, [rsp+48h]; this
0x18001c257  test    eax, eax
0x18001c259  js      loc_18001C300
0x18001c25f  mov     rcx, [r14]
0x18001c262  mov     qword ptr [r14], 0
0x18001c269  test    rcx, rcx
0x18001c26c  jz      short loc_18001C27B
0x18001c26e  mov     rax, [rcx]
0x18001c271  mov     rax, [rax+10h]
0x18001c275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c27a  nop
0x18001c27b  xor     edx, edx
0x18001c27d  lea     rcx, [rsi+60h]
0x18001c281  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001c286  lea     rcx, [rsi+50h]
0x18001c28a  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x18001c28f  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001c296  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001c29b  lea     rcx, [rsp+48h+arg_0]
0x18001c2a0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c2a5  lea     rcx, [rsi+80h]
0x18001c2ac  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2b1  lea     rcx, [rsi+78h]
0x18001c2b5  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2ba  lea     rcx, [rsi+70h]
0x18001c2be  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2c3  lea     rcx, [rsi+60h]
0x18001c2c7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c2cc  mov     rcx, r14
0x18001c2cf  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2d4  lea     rcx, [rsi+50h]
0x18001c2d8  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2dd  lea     rcx, [rsi+48h]
0x18001c2e1  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2e6  lea     rcx, [rsi+40h]
0x18001c2ea  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001c2ef  mov     rcx, rsi
0x18001c2f2  add     rsp, 28h
0x18001c2f6  pop     r14
0x18001c2f8  pop     rdi
0x18001c2f9  pop     rsi
0x18001c2fa  pop     rbx
0x18001c2fb  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIFastRundown@@@23@U?$CloakedIid@UICaptureSessionCom@@@23@U?$CloakedIid@UICaptureSessionCom_Old@@@23@UICaptureSession@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICaptureSessionCom>,Microsoft::WRL::CloakedIid<ICaptureSessionCom_Old>,Windows::Graphics::Capture::Server::ICaptureSession>(void)
0x18001c300  mov     r9d, eax; char *
0x18001c303  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001c30a  mov     edx, 1Bh; void *
0x18001c30f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
