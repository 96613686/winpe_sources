# Windows::Graphics::Capture::Server::CapturableItem::CreateSession_Old(void *,unsigned __int64,ICaptureSessionCom * *)

- ea: `0x18000f8b0`
- end: `0x18000f9d6`
- name: `?CreateSession_Old@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAX_KPEAPEAUICaptureSessionCom@@@Z`
- size: `294`
- prototype: `int(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, void *, unsigned __int64, struct ICaptureSessionCom **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18000c4d0`
- `0x18000ddc4`
- `0x18000de20`
- `0x18000dec8`
- `0x18000f8b0`
- `0x18001ebf8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f8d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f8d6`

## string_xrefs

- `0x18000f980`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::CreateSession_Old(
        RTL_SRWLOCK *this,
        void *a2,
        void *a3,
        struct ICaptureSessionCom **a4)
{
  RTL_SRWLOCK *v8; // rbx
  void **v9; // r9
  int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  struct ICaptureSessionCom *v15; // rax
  void *v17; // [rsp+20h] [rbp-30h] BYREF
  RTL_SRWLOCK *v18; // [rsp+28h] [rbp-28h] BYREF
  RTL_SRWLOCK *v19; // [rsp+30h] [rbp-20h] BYREF
  void **v20; // [rsp+38h] [rbp-18h] BYREF
  HANDLE TargetHandle; // [rsp+40h] [rbp-10h] BYREF
  char v22; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct ICaptureSessionCom *v24; // [rsp+80h] [rbp+30h] BYREF
  void *v25; // [rsp+98h] [rbp+48h] BYREF

  v8 = this + 10;
  AcquireSRWLockExclusive(this + 10);
  v19 = v8;
  *a4 = 0;
  v24 = 0;
  v25 = 0;
  v20 = &v25;
  TargetHandle = 0;
  v22 = 1;
  v10 = Windows::Graphics::Capture::Server::DuplicateClientHandle(a2, a3, &TargetHandle, v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v20);
  if ( v10 >= 0 )
  {
    v17 = v25;
    v18 = this - 4;
    v13 = (__int64)v24;
    v24 = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureSession,ICaptureSessionCom,Windows::Graphics::Capture::Server::CapturableItem *,void * &>(
            &v24,
            (struct Windows::Graphics::Capture::Server::CapturableItem **)&v18,
            &v17);
    v10 = v14;
    if ( v14 >= 0 )
    {
      v15 = v24;
      v24 = 0;
      *a4 = v15;
      v10 = 0;
      goto LABEL_9;
    }
    v11 = (unsigned int)v14;
    v12 = 531;
  }
  else
  {
    v11 = (unsigned int)v10;
    v12 = 525;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)v11,
    (int)v17);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v24);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000f8b0  mov     [rsp-28h+arg_8], rbx
0x18000f8b5  push    rbp
0x18000f8b6  push    rsi
0x18000f8b7  push    rdi
0x18000f8b8  push    r14
0x18000f8ba  push    r15
0x18000f8bc  mov     rbp, rsp
0x18000f8bf  sub     rsp, 50h
0x18000f8c3  mov     r15, r9
0x18000f8c6  mov     rdi, r8
0x18000f8c9  mov     rsi, rdx
0x18000f8cc  mov     r14, rcx
0x18000f8cf  lea     rbx, [rcx+50h]
0x18000f8d3  mov     rcx, rbx; SRWLock
0x18000f8d6  call    cs:__imp_AcquireSRWLockExclusive
0x18000f8dc  mov     [rbp+var_20], rbx
0x18000f8e0  mov     qword ptr [r15], 0
0x18000f8e7  mov     [rbp+arg_0], 0
0x18000f8ef  mov     [rbp+arg_18], 0
0x18000f8f7  lea     rax, [rbp+arg_18]
0x18000f8fb  mov     [rbp+var_18], rax
0x18000f8ff  mov     [rbp+TargetHandle], 0
0x18000f907  mov     [rbp+var_8], 1
0x18000f90b  lea     r8, [rbp+TargetHandle]; lpTargetHandle
0x18000f90f  mov     rdx, rdi; hSourceHandle
0x18000f912  mov     rcx, rsi; hSourceProcessHandle
0x18000f915  call    ?DuplicateClientHandle@Server@Capture@Graphics@Windows@@YAJPEAX0PEAPEAX@Z; Windows::Graphics::Capture::Server::DuplicateClientHandle(void *,void *,void * *)
0x18000f91a  mov     ebx, eax
0x18000f91c  lea     rcx, [rbp+var_18]
0x18000f920  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18000f925  test    ebx, ebx
0x18000f927  jns     short loc_18000F933
0x18000f929  mov     r9d, ebx
0x18000f92c  mov     edx, 20Dh
0x18000f931  jmp     short loc_18000F980
0x18000f933  mov     rax, [rbp+arg_18]
0x18000f937  mov     [rbp+var_30], rax
0x18000f93b  lea     rax, [r14-20h]
0x18000f93f  mov     [rbp+var_28], rax
0x18000f943  mov     rcx, [rbp+arg_0]
0x18000f947  mov     [rbp+arg_0], 0
0x18000f94f  test    rcx, rcx
0x18000f952  jz      short loc_18000F961
0x18000f954  mov     rax, [rcx]
0x18000f957  mov     rax, [rax+10h]
0x18000f95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f960  nop
0x18000f961  lea     r8, [rbp+var_30]
0x18000f965  lea     rdx, [rbp+var_28]
0x18000f969  lea     rcx, [rbp+arg_0]
0x18000f96d  call    ??$MakeAndInitialize@VCaptureSession@Server@Capture@Graphics@Windows@@UICaptureSessionCom@@PEAVCapturableItem@2345@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUICaptureSessionCom@@$$QEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureSession,ICaptureSessionCom,Windows::Graphics::Capture::Server::CapturableItem *,void * &>(ICaptureSessionCom * *,Windows::Graphics::Capture::Server::CapturableItem * &&,void * &)
0x18000f972  mov     ebx, eax
0x18000f974  test    eax, eax
0x18000f976  jns     short loc_18000F992
0x18000f978  mov     r9d, eax; char *
0x18000f97b  mov     edx, 213h; void *
0x18000f980  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000f987  mov     rcx, [rbp+28h]; this
0x18000f98b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f990  jmp     short loc_18000F9A3
0x18000f992  mov     rax, [rbp+arg_0]
0x18000f996  mov     [rbp+arg_0], 0
0x18000f99e  mov     [r15], rax
0x18000f9a1  xor     ebx, ebx
0x18000f9a3  lea     rcx, [rbp+arg_18]
0x18000f9a7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000f9ac  nop
0x18000f9ad  lea     rcx, [rbp+arg_0]
0x18000f9b1  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18000f9b6  nop
0x18000f9b7  lea     rcx, [rbp+var_20]
0x18000f9bb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f9c0  mov     eax, ebx
0x18000f9c2  mov     rbx, [rsp+50h+arg_8]
0x18000f9ca  add     rsp, 50h
0x18000f9ce  pop     r15
0x18000f9d0  pop     r14
0x18000f9d2  pop     rdi
0x18000f9d3  pop     rsi
0x18000f9d4  pop     rbp
0x18000f9d5  retn
```
