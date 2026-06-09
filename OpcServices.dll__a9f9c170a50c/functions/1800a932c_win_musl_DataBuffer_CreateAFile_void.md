# win_musl::DataBuffer::CreateAFile(void)

- ea: `0x1800a932c`
- end: `0x1800a9489`
- name: `?CreateAFile@DataBuffer@win_musl@@AEAAXXZ`
- size: `349`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1800023f0`

## callees

- `0x180017dd0`
- `0x1800517a0`
- `0x18005bb04`
- `0x180066c30`
- `0x180079ca0`
- `0x1800a932c`
- `0x1800aaf88`
- `0x1800cd38c`
- `0x180110a58`
- `0x180110ab8`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a93c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a93c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall win_musl::DataBuffer::CreateAFile(win_musl::DataBuffer *this)
{
  __int64 TemporaryFileName; // rax
  __int64 v3; // rdx
  const WCHAR **v4; // rdi
  const WCHAR *v5; // rcx
  HANDLE FileW; // rdx
  win_musl::detail *v7; // rcx
  unsigned int LastErrorAsFailHR; // eax
  _BYTE v9[40]; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-B8h] BYREF

  TemporaryFileName = win_musl::CreateTemporaryFileName(v9);
  std::wstring::assign((char *)this + 24, TemporaryFileName, 0, -1);
  LOBYTE(v3) = 1;
  std::wstring::_Tidy(v9, v3, 0);
  v4 = (const WCHAR **)((char *)this + 32);
  if ( *((_QWORD *)this + 7) < 8u )
    v5 = (const WCHAR *)((char *)this + 32);
  else
    v5 = *v4;
  FileW = CreateFileW(v5, 0xC0000000, 7u, 0, 1u, 0xC000100u, 0);
  win_scope::reset<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>,void *>(
    (char *)this + 64,
    FileW);
  if ( (unsigned __int8)win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator!((char *)this + 64) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x170u,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)L"Unspecified error");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    if ( *((_QWORD *)this + 7) >= 8u )
      v4 = (const WCHAR **)*v4;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_b1a0d9529acd3e179f8746edc331057b_Traceguids, v4);
  }
}

```

## disassembly

```asm
0x1800a932c  mov     rax, rsp
0x1800a932f  push    rdi
0x1800a9330  sub     rsp, 120h
0x1800a9337  mov     [rsp+128h+var_E8], 0FFFFFFFFFFFFFFFEh
0x1800a9340  mov     [rax+10h], rbx
0x1800a9344  mov     [rax+18h], rsi
0x1800a9348  mov     rax, cs:__security_cookie
0x1800a934f  xor     rax, rsp
0x1800a9352  mov     [rsp+128h+var_18], rax
0x1800a935a  mov     rsi, rcx
0x1800a935d  lea     rcx, [rsp+128h+var_E0]
0x1800a9362  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_musl::CreateTemporaryFileName(void)
0x1800a9367  nop
0x1800a9368  lea     rcx, [rsi+18h]
0x1800a936c  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800a9370  xor     r8d, r8d
0x1800a9373  mov     rdx, rax
0x1800a9376  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800a937b  nop
0x1800a937c  xor     r8d, r8d
0x1800a937f  mov     dl, 1
0x1800a9381  lea     rcx, [rsp+128h+var_E0]
0x1800a9386  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800a938b  lea     rdi, [rsi+20h]
0x1800a938f  cmp     qword ptr [rsi+38h], 8
0x1800a9394  jb      short loc_1800A939B
0x1800a9396  mov     rcx, [rdi]
0x1800a9399  jmp     short loc_1800A939E
0x1800a939b  mov     rcx, rdi; lpFileName
0x1800a939e  mov     [rsp+128h+hTemplateFile], 0; hTemplateFile
0x1800a93a7  mov     [rsp+128h+dwFlagsAndAttributes], 0C000100h; dwFlagsAndAttributes
0x1800a93af  mov     [rsp+128h+dwCreationDisposition], 1; dwCreationDisposition
0x1800a93b7  xor     r9d, r9d; lpSecurityAttributes
0x1800a93ba  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a93bf  lea     r8d, [r9+7]; dwShareMode
0x1800a93c3  call    cs:__imp_CreateFileW
0x1800a93c9  mov     rdx, rax
0x1800a93cc  lea     rcx, [rsi+40h]
0x1800a93d0  call    ??$reset@PEAXU?$mutable_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@PEAX@win_scope@@YAXAEAV?$scope@PEAXU?$mutable_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@0@PEAX@Z; win_scope::reset<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>,void *>(win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,void *)
0x1800a93d5  lea     rcx, [rsi+40h]
0x1800a93d9  call    ??7?$scope@PEAXU?$mutable_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEBA_NXZ; win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator!(void)
0x1800a93de  test    al, al
0x1800a93e0  jz      short loc_1800A9429
0x1800a93e2  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a93e7  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x1800a93ee  mov     [rsp+128h+hTemplateFile], rcx; struct win_musl::TStringEllipseBase *
0x1800a93f3  mov     [rsp+128h+dwFlagsAndAttributes], eax; unsigned int
0x1800a93f7  mov     [rsp+128h+dwCreationDisposition], 170h; unsigned int
0x1800a93ff  lea     r9, word_18013A0B6
0x1800a9406  lea     r8, aNoFilename; "(no filename)"
0x1800a940d  lea     rcx, [rsp+128h+pExceptionObject]; this
0x1800a9412  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a9417  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a941e  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x1800a9423  call    _CxxThrowException_0
0x1800a9429  lea     rax, WPP_GLOBAL_Control
0x1800a9430  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9437  cmp     rcx, rax
0x1800a943a  jz      short loc_1800A9464
0x1800a943c  test    byte ptr [rcx+44h], 4
0x1800a9440  jz      short loc_1800A9464
0x1800a9442  cmp     qword ptr [rsi+38h], 8
0x1800a9447  jb      short loc_1800A944C
0x1800a9449  mov     rdi, [rdi]
0x1800a944c  mov     edx, 0Ah
0x1800a9451  mov     r9, rdi
0x1800a9454  lea     r8, WPP_b1a0d9529acd3e179f8746edc331057b_Traceguids
0x1800a945b  mov     rcx, [rcx+38h]
0x1800a945f  call    WPP_SF_S
0x1800a9464  mov     rcx, [rsp+128h+var_18]
0x1800a946c  xor     rcx, rsp; StackCookie
0x1800a946f  call    __security_check_cookie
0x1800a9474  lea     r11, [rsp+128h+var_8]
0x1800a947c  mov     rbx, [r11+18h]
0x1800a9480  mov     rsi, [r11+20h]
0x1800a9484  mov     rsp, r11
0x1800a9487  pop     rdi
0x1800a9488  retn
```
