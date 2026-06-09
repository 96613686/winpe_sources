# Windows::Graphics::Capture::Server::CapturableItem::CreateSession(void *,ICaptureSessionCom * *)

- ea: `0x18000f800`
- end: `0x18000f8a4`
- name: `?CreateSession@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAXPEAPEAUICaptureSessionCom@@@Z`
- size: `164`
- prototype: `int(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, void *, struct ICaptureSessionCom **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18000c4d0`
- `0x18000ddc4`
- `0x18000f800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f819`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f819`

## string_xrefs

- `0x18000f85f`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::CreateSession(
        RTL_SRWLOCK *this,
        void *a2,
        struct ICaptureSessionCom **a3)
{
  RTL_SRWLOCK *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  struct ICaptureSessionCom *v8; // rax
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct ICaptureSessionCom *v12; // [rsp+40h] [rbp+8h] BYREF
  void *v13; // [rsp+48h] [rbp+10h] BYREF
  RTL_SRWLOCK *v14; // [rsp+50h] [rbp+18h] BYREF
  RTL_SRWLOCK *v15; // [rsp+58h] [rbp+20h] BYREF

  v13 = a2;
  v5 = this + 11;
  AcquireSRWLockExclusive(this + 11);
  v15 = v5;
  *a3 = 0;
  v14 = this - 3;
  v12 = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureSession,ICaptureSessionCom,Windows::Graphics::Capture::Server::CapturableItem *,void * &>(
         &v12,
         (struct Windows::Graphics::Capture::Server::CapturableItem **)&v14,
         &v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = v12;
    v12 = 0;
    *a3 = v8;
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v6,
      v10);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  return v7;
}

```

## disassembly

```asm
0x18000f800  mov     [rsp+arg_8], rdx
0x18000f805  push    rbx
0x18000f806  push    rsi
0x18000f807  push    rdi; int
0x18000f808  sub     rsp, 20h
0x18000f80c  mov     rsi, r8
0x18000f80f  mov     rdi, rcx
0x18000f812  lea     rbx, [rcx+58h]
0x18000f816  mov     rcx, rbx; SRWLock
0x18000f819  call    cs:__imp_AcquireSRWLockExclusive
0x18000f81f  mov     [rsp+38h+arg_18], rbx
0x18000f824  mov     qword ptr [rsi], 0
0x18000f82b  lea     rax, [rdi-18h]
0x18000f82f  mov     [rsp+38h+arg_10], rax
0x18000f834  mov     [rsp+38h+arg_0], 0
0x18000f83d  lea     r8, [rsp+38h+arg_8]
0x18000f842  lea     rdx, [rsp+38h+arg_10]
0x18000f847  lea     rcx, [rsp+38h+arg_0]
0x18000f84c  call    ??$MakeAndInitialize@VCaptureSession@Server@Capture@Graphics@Windows@@UICaptureSessionCom@@PEAVCapturableItem@2345@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUICaptureSessionCom@@$$QEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureSession,ICaptureSessionCom,Windows::Graphics::Capture::Server::CapturableItem *,void * &>(ICaptureSessionCom * *,Windows::Graphics::Capture::Server::CapturableItem * &&,void * &)
0x18000f851  mov     ebx, eax
0x18000f853  test    eax, eax
0x18000f855  jns     short loc_18000F872
0x18000f857  mov     rcx, [rsp+38h]; this
0x18000f85c  mov     r9d, eax; char *
0x18000f85f  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000f866  mov     edx, 1F3h; void *
0x18000f86b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f870  jmp     short loc_18000F885
0x18000f872  mov     rax, [rsp+38h+arg_0]
0x18000f877  mov     [rsp+38h+arg_0], 0
0x18000f880  mov     [rsi], rax
0x18000f883  xor     ebx, ebx
0x18000f885  lea     rcx, [rsp+38h+arg_0]
0x18000f88a  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18000f88f  nop
0x18000f890  lea     rcx, [rsp+38h+arg_18]
0x18000f895  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f89a  mov     eax, ebx
0x18000f89c  add     rsp, 20h
0x18000f8a0  pop     rdi
0x18000f8a1  pop     rsi
0x18000f8a2  pop     rbx
0x18000f8a3  retn
```
