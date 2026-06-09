# win_musl::DataBuffer::LogicalFileIterator::LogicalFileIterator(win_musl::DataBuffer const &,win_musl::DataBuffer::IteratorType)

- ea: `0x18008a430`
- end: `0x18008a5c7`
- name: `??0LogicalFileIterator@DataBuffer@win_musl@@QEAA@AEBV12@W4IteratorType@12@@Z`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18008a3cc`

## callees

- `0x180018c00`
- `0x1800517a0`
- `0x180079ca0`
- `0x18008a430`
- `0x1800b6858`
- `0x1800c04c4`
- `0x1800cd38c`
- `0x1800d91bc`
- `0x180110a04`
- `0x180110a88`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008a4f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008a4f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_musl::DataBuffer::LogicalFileIterator::LogicalFileIterator(__int64 a1)
{
  _QWORD *v2; // rdx
  int v3; // r8d
  __int64 v4; // rcx
  const WCHAR *v6; // rcx
  HANDLE FileW; // rdx
  const char *v8; // rdx
  win_musl::detail *v9; // rcx
  unsigned int v10; // r8d
  unsigned int LastErrorAsFailHR; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  void *v15; // rax
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>();
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = v2[9];
  *(_QWORD *)(v4 + 40) = 0;
  *(_QWORD *)(v4 + 48) = 0;
  *(_DWORD *)(v4 + 56) = 0;
  if ( v2[9] && !v2[2] && v3 != 1 )
  {
    v6 = (const WCHAR *)(v2 + 4);
    if ( v2[7] >= 8u )
      v6 = *(const WCHAR **)v6;
    FileW = CreateFileW(v6, 0x80000000, 7u, 0, 3u, 0x8000100u, 0);
    win_scope::reset<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>,void *>(
      a1,
      FileW);
    if ( (unsigned __int8)win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::operator!(a1) )
    {
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v9);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x2B9u,
        LastErrorAsFailHR,
        (struct win_musl::TStringEllipseBase *)L"Unspecified error");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 24);
    v15 = operator new(0x20u, v8, v10);
    if ( v15 )
      v15 = (void *)std::vector<unsigned char>::vector<unsigned char>(v15, 28672);
    win_scope::detail::scope_helper<std::vector<unsigned char> *,win_scope::const_policies<win_scope::shared_policies>>::reset(
      a1 + 40,
      v15);
    v12 = *(_QWORD *)(a1 + 48);
    v13 = *(_QWORD *)(v12 + 8);
    if ( v13 )
      v14 = *(_QWORD *)(v12 + 16) - v13;
    else
      v14 = 0;
    *(_DWORD *)(a1 + 56) = v14;
  }
  return a1;
}

```

## disassembly

```asm
0x18008a430  mov     rax, rsp
0x18008a433  push    rdi
0x18008a434  sub     rsp, 110h
0x18008a43b  mov     [rsp+118h+var_D8], 0FFFFFFFFFFFFFFFEh
0x18008a444  mov     [rax+18h], rbx
0x18008a448  mov     rax, cs:__security_cookie
0x18008a44f  xor     rax, rsp
0x18008a452  mov     [rsp+118h+var_18], rax
0x18008a45a  mov     rbx, rcx
0x18008a45d  mov     [rsp+118h+var_D0], rcx
0x18008a462  call    ??0?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void)
0x18008a467  nop
0x18008a468  mov     qword ptr [rcx+10h], 0
0x18008a470  mov     rax, [rdx+48h]
0x18008a474  mov     [rcx+18h], rax
0x18008a478  mov     qword ptr [rcx+28h], 0
0x18008a480  mov     qword ptr [rcx+30h], 0
0x18008a488  mov     dword ptr [rcx+38h], 0
0x18008a48f  cmp     qword ptr [rdx+48h], 0
0x18008a494  jz      short loc_18008A4A1
0x18008a496  cmp     qword ptr [rdx+10h], 0
0x18008a49b  jz      loc_18008A58C
0x18008a4a1  mov     rax, rbx
0x18008a4a4  mov     rcx, [rsp+118h+var_18]
0x18008a4ac  xor     rcx, rsp; StackCookie
0x18008a4af  call    __security_check_cookie
0x18008a4b4  mov     rbx, [rsp+118h+arg_10]
0x18008a4bc  add     rsp, 110h
0x18008a4c3  pop     rdi
0x18008a4c4  retn
0x18008a4c5  lea     rcx, [rdx+20h]
0x18008a4c9  cmp     qword ptr [rdx+38h], 8
0x18008a4ce  jb      short loc_18008A4D3
0x18008a4d0  mov     rcx, [rcx]; lpFileName
0x18008a4d3  mov     [rsp+118h+hTemplateFile], 0; hTemplateFile
0x18008a4dc  mov     [rsp+118h+dwFlagsAndAttributes], 8000100h; dwFlagsAndAttributes
0x18008a4e4  mov     [rsp+118h+dwCreationDisposition], 3; dwCreationDisposition
0x18008a4ec  xor     r9d, r9d; lpSecurityAttributes
0x18008a4ef  mov     edx, 80000000h; dwDesiredAccess
0x18008a4f4  lea     r8d, [r9+7]; dwShareMode
0x18008a4f8  call    cs:__imp_CreateFileW
0x18008a4fe  mov     rdx, rax
0x18008a501  mov     rcx, rbx
0x18008a504  call    ??$reset@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@PEAX@win_scope@@YAXAEAV?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@0@PEAX@Z; win_scope::reset<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>,void *>(win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>> &,void *)
0x18008a509  mov     rcx, rbx
0x18008a50c  call    ??7?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEBA_NXZ; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::operator!(void)
0x18008a511  test    al, al
0x18008a513  jz      loc_18008A59B
0x18008a519  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008a51e  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x18008a525  mov     [rsp+118h+hTemplateFile], rcx; struct win_musl::TStringEllipseBase *
0x18008a52a  mov     [rsp+118h+dwFlagsAndAttributes], eax; unsigned int
0x18008a52e  mov     [rsp+118h+dwCreationDisposition], 2B9h; unsigned int
0x18008a536  lea     r9, word_18013A0B6
0x18008a53d  lea     r8, aNoFilename; "(no filename)"
0x18008a544  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18008a549  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008a54e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008a555  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18008a55a  call    _CxxThrowException_0
0x18008a560  mov     rdx, rax
0x18008a563  lea     rcx, [rbx+28h]
0x18008a567  call    ?reset@?$scope_helper@PEAV?$vector@EV?$allocator@E@std@@@std@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$vector@EV?$allocator@E@std@@@std@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; win_scope::detail::scope_helper<std::vector<uchar> *,win_scope::const_policies<win_scope::shared_policies>>::reset(win_scope::scope<std::vector<uchar> *,win_scope::const_policies<win_scope::shared_policies>> &,std::vector<uchar> *)
0x18008a56c  mov     rax, [rbx+30h]
0x18008a570  mov     rcx, [rax+8]
0x18008a574  test    rcx, rcx
0x18008a577  jnz     short loc_18008A583
0x18008a579  xor     eax, eax
0x18008a57b  mov     [rbx+38h], eax
0x18008a57e  jmp     loc_18008A4A1
0x18008a583  mov     rax, [rax+10h]
0x18008a587  sub     rax, rcx
0x18008a58a  jmp     short loc_18008A57B
0x18008a58c  cmp     r8d, 1
0x18008a590  jz      loc_18008A4A1
0x18008a596  jmp     loc_18008A4C5
0x18008a59b  mov     rax, [rbx+18h]
0x18008a59f  mov     [rbx+20h], rax
0x18008a5a3  mov     ecx, 20h ; ' '; unsigned __int64
0x18008a5a8  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18008a5ad  mov     [rsp+118h+var_C8], rax
0x18008a5b2  test    rax, rax
0x18008a5b5  jz      short loc_18008A560
0x18008a5b7  mov     edx, 7000h
0x18008a5bc  mov     rcx, rax
0x18008a5bf  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z; std::vector<uchar>::vector<uchar>(unsigned __int64)
0x18008a5c4  jmp     short loc_18008A560
```
