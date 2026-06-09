# Windows::Graphics::Capture::Server::CapturableItem::SetClosedEvent(void *)

- ea: `0x180014ab0`
- end: `0x180014c92`
- name: `?SetClosedEvent@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAX@Z`
- size: `482`
- prototype: `int(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18000be90`
- `0x18000ddc4`
- `0x18000de20`
- `0x180014ab0`
- `0x180014cec`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ad0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ad0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014bfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014c04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014bfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014c04`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014c2f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014c2f`

## string_xrefs

- `0x180014bbf`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180014c50`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::SetClosedEvent(RTL_SRWLOCK *this, void *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 (__fastcall **Ptr)(RTL_SRWLOCK *, GUID *, __int64 *); // rax
  int v6; // ebx
  __int64 v7; // rdx
  PVOID v8; // rbx
  __int64 (__fastcall *v9)(PVOID, _QWORD, RTL_SRWLOCK *); // r14
  _QWORD *v10; // rax
  __int64 v11; // rcx
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-40h]
  DWORD dwDesiredAccessa; // [rsp+20h] [rbp-40h]
  RTL_SRWLOCK *v17; // [rsp+40h] [rbp-20h] BYREF
  RTL_SRWLOCK *v18; // [rsp+48h] [rbp-18h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-10h] BYREF
  char v20; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v22; // [rsp+90h] [rbp+30h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+48h] BYREF

  v4 = this + 11;
  AcquireSRWLockExclusive(this + 11);
  v17 = v4;
  if ( !BYTE2(this[10].Ptr) )
  {
    BYTE2(this[10].Ptr) = 1;
    v22 = 0;
    Ptr = (__int64 (__fastcall **)(RTL_SRWLOCK *, GUID *, __int64 *))this[-3].Ptr;
    v23 = 0;
    v6 = (*Ptr)(this - 3, &GUID_00000038_0000_0000_c000_000000000046, &v23);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 24LL))(v23, &v22);
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v23);
    if ( v6 < 0 )
    {
      v7 = 555;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v6,
        dwDesiredAccess);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v22);
      goto LABEL_19;
    }
    v8 = this[7].Ptr;
    v9 = *(__int64 (__fastcall **)(PVOID, _QWORD, RTL_SRWLOCK *))(*(_QWORD *)v8 + 80LL);
    v24 = v22;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
    v10 = (_QWORD *)Microsoft::WRL::Callback_Windows::Foundation::ITypedEventHandler_Windows::Internal::PlatformExtensions::Capture::CaptureSession___IInspectable_____lambda_3886ed14139e82f77ff3cbe89f2bf6ca___(
                      &v23,
                      &v24);
    v6 = v9(v8, *v10, this + 9);
    v11 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v24);
    if ( v6 < 0 )
    {
      v7 = 570;
      goto LABEL_12;
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v22);
  }
  v18 = this + 8;
  TargetHandle = 0;
  v20 = 1;
  CurrentProcess = GetCurrentProcess();
  v13 = GetCurrentProcess();
  LODWORD(CurrentProcess) = DuplicateHandle(v13, a2, CurrentProcess, &TargetHandle, 0, 0, 2u);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v18);
  if ( (_DWORD)CurrentProcess )
  {
    if ( LOBYTE(this[10].Ptr) )
      Windows::Graphics::Capture::Server::CapturableItem::SignalClosedEvent((Windows::Graphics::Capture::Server::CapturableItem *)&this[-3]);
    v6 = 0;
  }
  else
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)0x80070057LL,
      dwDesiredAccessa);
  }
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014ab0  mov     [rsp-28h+arg_8], rbx
0x180014ab5  push    rbp
0x180014ab6  push    rsi
0x180014ab7  push    rdi
0x180014ab8  push    r14
0x180014aba  push    r15
0x180014abc  mov     rbp, rsp
0x180014abf  sub     rsp, 60h
0x180014ac3  mov     r15, rdx
0x180014ac6  mov     rdi, rcx
0x180014ac9  lea     rbx, [rcx+58h]
0x180014acd  mov     rcx, rbx; SRWLock
0x180014ad0  call    cs:__imp_AcquireSRWLockExclusive
0x180014ad6  mov     [rbp+var_20], rbx
0x180014ada  lea     rsi, [rdi-18h]
0x180014ade  cmp     byte ptr [rsi+6Ah], 0
0x180014ae2  jnz     loc_180014BE7
0x180014ae8  mov     byte ptr [rdi+52h], 1
0x180014aec  mov     [rbp+arg_0], 0
0x180014af4  mov     rax, [rsi]
0x180014af7  mov     [rbp+arg_10], 0
0x180014aff  lea     r8, [rbp+arg_10]
0x180014b03  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180014b0a  mov     rcx, rsi
0x180014b0d  mov     rax, [rax]
0x180014b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b15  mov     ebx, eax
0x180014b17  test    eax, eax
0x180014b19  js      short loc_180014B31
0x180014b1b  mov     rcx, [rbp+arg_10]
0x180014b1f  mov     rax, [rcx]
0x180014b22  lea     rdx, [rbp+arg_0]
0x180014b26  mov     rax, [rax+18h]
0x180014b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b2f  mov     ebx, eax
0x180014b31  lea     rcx, [rbp+arg_10]
0x180014b35  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180014b3a  test    ebx, ebx
0x180014b3c  jns     short loc_180014B45
0x180014b3e  mov     edx, 22Bh
0x180014b43  jmp     short loc_180014BBC
0x180014b45  mov     rbx, [rdi+38h]
0x180014b49  mov     rax, [rbx]
0x180014b4c  mov     r14, [rax+50h]
0x180014b50  mov     rcx, [rbp+arg_0]
0x180014b54  mov     [rbp+arg_18], rcx
0x180014b58  test    rcx, rcx
0x180014b5b  jz      short loc_180014B6A
0x180014b5d  mov     rax, [rcx]
0x180014b60  mov     rax, [rax+8]
0x180014b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b69  nop
0x180014b6a  lea     rdx, [rbp+arg_18]
0x180014b6e  lea     rcx, [rbp+arg_10]
0x180014b72  call    Microsoft__WRL__Callback_Windows__Foundation__ITypedEventHandler_Windows__Internal__PlatformExtensions__Capture__CaptureSession___IInspectable_____lambda_3886ed14139e82f77ff3cbe89f2bf6ca___
0x180014b77  nop
0x180014b78  lea     r8, [rdi+48h]
0x180014b7c  mov     rdx, [rax]
0x180014b7f  mov     rcx, rbx
0x180014b82  mov     rax, r14
0x180014b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b8a  mov     ebx, eax
0x180014b8c  mov     rcx, [rbp+arg_10]
0x180014b90  test    rcx, rcx
0x180014b93  jz      short loc_180014BAA
0x180014b95  mov     [rbp+arg_10], 0
0x180014b9d  mov     rdx, [rcx]
0x180014ba0  mov     rax, [rdx+10h]
0x180014ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ba9  nop
0x180014baa  lea     rcx, [rbp+arg_18]
0x180014bae  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180014bb3  test    ebx, ebx
0x180014bb5  jns     short loc_180014BDE
0x180014bb7  mov     edx, 23Ah; void *
0x180014bbc  mov     r9d, ebx; char *
0x180014bbf  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180014bc6  mov     rcx, [rbp+28h]; this
0x180014bca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014bcf  nop
0x180014bd0  lea     rcx, [rbp+arg_0]
0x180014bd4  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180014bd9  jmp     loc_180014C73
0x180014bde  lea     rcx, [rbp+arg_0]
0x180014be2  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180014be7  lea     rax, [rdi+40h]
0x180014beb  mov     [rbp+var_18], rax
0x180014bef  mov     [rbp+TargetHandle], 0
0x180014bf7  mov     [rbp+var_8], 1
0x180014bfb  call    cs:__imp_GetCurrentProcess
0x180014c01  mov     rbx, rax
0x180014c04  call    cs:__imp_GetCurrentProcess
0x180014c0a  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180014c12  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x180014c1a  mov     [rsp+60h+dwDesiredAccess], 0; int
0x180014c22  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x180014c26  mov     r8, rbx; hTargetProcessHandle
0x180014c29  mov     rdx, r15; hSourceHandle
0x180014c2c  mov     rcx, rax; hSourceProcessHandle
0x180014c2f  call    cs:__imp_DuplicateHandle
0x180014c35  mov     ebx, eax
0x180014c37  lea     rcx, [rbp+var_18]
0x180014c3b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180014c40  test    ebx, ebx
0x180014c42  jnz     short loc_180014C63
0x180014c44  mov     rcx, [rbp+28h]; this
0x180014c48  mov     ebx, 80070057h
0x180014c4d  mov     r9d, ebx; char *
0x180014c50  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180014c57  mov     edx, 246h; void *
0x180014c5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c61  jmp     short loc_180014C73
0x180014c63  cmp     byte ptr [rdi+50h], 0
0x180014c67  jz      short loc_180014C71
0x180014c69  mov     rcx, rsi; this
0x180014c6c  call    ?SignalClosedEvent@CapturableItem@Server@Capture@Graphics@Windows@@QEAAXXZ; Windows::Graphics::Capture::Server::CapturableItem::SignalClosedEvent(void)
0x180014c71  xor     ebx, ebx
0x180014c73  lea     rcx, [rbp+var_20]
0x180014c77  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014c7c  mov     eax, ebx
0x180014c7e  mov     rbx, [rsp+60h+arg_8]
0x180014c86  add     rsp, 60h
0x180014c8a  pop     r15
0x180014c8c  pop     r14
0x180014c8e  pop     rdi
0x180014c8f  pop     rsi
0x180014c90  pop     rbp
0x180014c91  retn
```
