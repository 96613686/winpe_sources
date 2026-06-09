# win_dox::OpcPartContentStream::DoRealCreateTempFile(void)

- ea: `0x18005b7c0`
- end: `0x18005bafb`
- name: `?DoRealCreateTempFile@OpcPartContentStream@win_dox@@AEAAXXZ`
- size: `827`
- prototype: `void __fastcall(win_dox::OpcPartContentStream *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b4bd0`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x18000d200`
- `0x18000d950`
- `0x180010524`
- `0x180010a00`
- `0x180012fa0`
- `0x180015a68`
- `0x180018c00`
- `0x18004692c`
- `0x1800517a0`
- `0x180054450`
- `0x180055f5c`
- `0x180055ff4`
- `0x180057530`
- `0x1800576b8`
- `0x18005b7c0`
- `0x18005bb04`
- `0x18005bf60`
- `0x180079ca0`
- `0x1800c4998`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800d90c4`
- `0x1800d91bc`
- `0x1800dfdd8`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b830`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b830`

## string_xrefs

- `0x18005b894`: `Call to ::CreateFile failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_dox::OpcPartContentStream::DoRealCreateTempFile(win_dox::OpcPartContentStream *this)
{
  __int64 TemporaryFileName; // rax
  const WCHAR *v3; // rcx
  HANDLE FileW; // rdx
  const char *v5; // rdx
  win_musl::detail *v6; // rcx
  unsigned int v7; // r8d
  unsigned int LastErrorAsFailHR; // ebx
  void *v9; // rax
  __int128 *v10; // rax
  __int128 v11; // xmm1
  int v12; // ebx
  __int64 v13; // rax
  const char *v14; // rdx
  unsigned int v15; // r8d
  win_dox::Stream *v16; // rax
  win_dox::Stream *v17; // rbx
  win_scope::counted_strong_weak_base *v18; // rbx
  win_scope::counted_strong_weak_base *v19; // rdi
  __int64 Bytes; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  void *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+48h] [rbp-B8h] BYREF
  void **v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  void **v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h]
  win_scope::counted_strong_weak_base *v29[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[16]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  _BYTE v32[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[8]; // [rsp+B8h] [rbp-48h] BYREF
  void *Block; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v36; // [rsp+D8h] [rbp-28h]
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v38[512]; // [rsp+180h] [rbp+80h] BYREF

  v31 = -2;
  TemporaryFileName = win_musl::CreateTemporaryFileName((__int64)v33);
  v3 = (const WCHAR *)(TemporaryFileName + 8);
  if ( *(_QWORD *)(TemporaryFileName + 32) >= 8u )
    v3 = *(const WCHAR **)v3;
  FileW = CreateFileW(v3, 0xC0000000, 0, 0, 1u, 0x4000100u, 0);
  win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(
    v30,
    FileW);
  if ( v36 >= 8 )
    operator delete(Block);
  v36 = 7;
  v35 = 0;
  LOWORD(Block) = 0;
  if ( (unsigned __int8)win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::operator!(v30) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v6);
    memset_0(v38, 0, sizeof(v38));
    StringCchPrintfW(v38, 0x200u, L"Call to ::CreateFile failed with HResult 0x%X.", LastErrorAsFailHR);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x18Bu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)v38);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v9 = operator new(0x20u, v5, v7);
  v23 = v9;
  if ( v9 )
    v9 = (void *)win_dox::StreamOnFileHandle::StreamOnFileHandle(v9, v30);
  v10 = (__int128 *)win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(
                      &v24,
                      v9);
  v11 = *v10;
  *v10 = *((_OWORD *)this + 3);
  *((_OWORD *)this + 3) = v11;
  if ( *((_QWORD *)&v24 + 1) && (_QWORD)v24 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v24);
  win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
    &v23,
    (char *)this + 24);
  v12 = -1;
  if ( v23 )
  {
    v12 = dword_1801C4EA8;
    (*(void (**)(void))(*(_QWORD *)v23 + 16LL))();
  }
  if ( v12 != -1 )
  {
    v13 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
            &v25,
            (char *)this + 48);
    win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v23,
      v13);
    v16 = (win_dox::Stream *)operator new(0x10u, v14, v15);
    v17 = v16;
    *(_QWORD *)&v24 = v16;
    if ( v16 )
    {
      win_dox::Stream::Stream(v16, (const struct Stream *)&v23);
      *((_BYTE *)v17 + 8) = 1;
    }
    else
    {
      v17 = 0;
    }
    win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(
      v29,
      v17);
    v24 = 0;
    v18 = v29[0];
    v19 = v29[1];
    if ( v29[0] )
    {
      win_scope::counted_strong_weak_base::AddRef(v29[0]);
      *(_QWORD *)&v24 = v18;
      *((_QWORD *)&v24 + 1) = v19;
    }
    win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(
      v32,
      &v24);
    Bytes = win_dox::OpcPartContent::GetBytes((char *)this + 24, &v25);
    v21 = win_dox::CreateSenderBase<IByteCollection>::CreateSender(Bytes, &v27);
    win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(v21, v32);
    v27 = &win_dox::OpcRelationshipSender::`vftable';
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v28 = 0;
    }
    v25 = &win_dox::OpcRelationshipSender::`vftable';
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    win_dox::ByteReceiver::~ByteReceiver((win_dox::ByteReceiver *)v32);
    if ( v18 && v19 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v29);
    if ( v23 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v22 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v25,
          (char *)this + 48);
  win_dox::OpcPartContentStream::SendNotifications(this, v22);
  win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::~scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(v30);
}

```

## disassembly

```asm
0x18005b7c0  push    rbp
0x18005b7c2  push    rbx
0x18005b7c3  push    rsi
0x18005b7c4  push    rdi
0x18005b7c5  push    r14
0x18005b7c7  push    r15
0x18005b7c9  lea     rbp, [rsp-498h]
0x18005b7d1  sub     rsp, 598h
0x18005b7d8  mov     [rbp+4C0h+var_528], 0FFFFFFFFFFFFFFFEh
0x18005b7e0  mov     rax, cs:__security_cookie
0x18005b7e7  xor     rax, rsp
0x18005b7ea  mov     [rbp+4C0h+var_40], rax
0x18005b7f1  mov     r14, rcx
0x18005b7f4  lea     rcx, [rbp+4C0h+var_508]
0x18005b7f8  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_musl::CreateTemporaryFileName(void)
0x18005b7fd  nop
0x18005b7fe  lea     rcx, [rax+8]
0x18005b802  cmp     qword ptr [rax+20h], 8
0x18005b807  jb      short loc_18005B80C
0x18005b809  mov     rcx, [rcx]; lpFileName
0x18005b80c  mov     [rsp+5C0h+hTemplateFile], 0; hTemplateFile
0x18005b815  mov     [rsp+5C0h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x18005b81d  mov     [rsp+5C0h+dwCreationDisposition], 1; dwCreationDisposition
0x18005b825  xor     r9d, r9d; lpSecurityAttributes
0x18005b828  xor     r8d, r8d; dwShareMode
0x18005b82b  mov     edx, 0C0000000h; dwDesiredAccess
0x18005b830  call    cs:__imp_CreateFileW
0x18005b836  mov     rdx, rax
0x18005b839  lea     rcx, [rbp+4C0h+var_538]
0x18005b83d  call    ??0?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@PEAX@Z; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void *)
0x18005b842  nop
0x18005b843  cmp     [rbp+4C0h+var_4E8], 8
0x18005b848  jb      short loc_18005B853
0x18005b84a  mov     rcx, [rbp+4C0h+Block]; Block
0x18005b84e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b853  mov     [rbp+4C0h+var_4E8], 7
0x18005b85b  mov     [rbp+4C0h+var_4F0], 0
0x18005b863  xor     eax, eax
0x18005b865  mov     word ptr [rbp+4C0h+Block], ax
0x18005b869  lea     rcx, [rbp+4C0h+var_538]
0x18005b86d  call    ??7?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEBA_NXZ; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::operator!(void)
0x18005b872  test    al, al
0x18005b874  jz      short loc_18005B8EC
0x18005b876  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18005b87b  mov     ebx, eax
0x18005b87d  xor     edx, edx; Val
0x18005b87f  mov     r8d, 400h; Size
0x18005b885  lea     rcx, [rbp+4C0h+var_440]; void *
0x18005b88c  call    memset_0
0x18005b891  mov     r9d, ebx
0x18005b894  lea     r8, aCallToCreatefi; "Call to ::CreateFile failed with HResul"...
0x18005b89b  mov     edx, 200h; unsigned __int64
0x18005b8a0  lea     rcx, [rbp+4C0h+var_440]; wchar_t *
0x18005b8a7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18005b8ac  lea     rax, [rbp+4C0h+var_440]
0x18005b8b3  mov     [rsp+5C0h+hTemplateFile], rax; struct win_musl::TStringEllipseBase *
0x18005b8b8  mov     [rsp+5C0h+dwFlagsAndAttributes], ebx; unsigned int
0x18005b8bc  mov     [rsp+5C0h+dwCreationDisposition], 18Bh; unsigned int
0x18005b8c4  lea     r9, word_18013A0B6
0x18005b8cb  lea     r8, aNoFilename; "(no filename)"
0x18005b8d2  lea     rcx, [rbp+4C0h+pExceptionObject]; this
0x18005b8d6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18005b8db  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18005b8e2  lea     rcx, [rbp+4C0h+pExceptionObject]; pExceptionObject
0x18005b8e6  call    _CxxThrowException_0
0x18005b8ec  mov     ecx, 20h ; ' '; unsigned __int64
0x18005b8f1  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18005b8f6  mov     [rsp+5C0h+var_580], rax
0x18005b8fb  test    rax, rax
0x18005b8fe  jz      short loc_18005B90D
0x18005b900  lea     rdx, [rbp+4C0h+var_538]
0x18005b904  mov     rcx, rax
0x18005b907  call    ??0StreamOnFileHandle@win_dox@@QEAA@AEBV?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::StreamOnFileHandle::StreamOnFileHandle(win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>> const &)
0x18005b90c  nop
0x18005b90d  mov     rdx, rax
0x18005b910  lea     rcx, [rsp+5C0h+var_578]
0x18005b915  call    ??0?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVStreamOnFileHandle@win_dox@@@Z; win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::StreamOnFileHandle *)
0x18005b91a  lea     rsi, [r14+30h]
0x18005b91e  movups  xmm1, xmmword ptr [rax]
0x18005b921  movups  xmm0, xmmword ptr [rsi]
0x18005b924  movdqu  xmmword ptr [rax], xmm0
0x18005b928  movdqu  xmmword ptr [rsi], xmm1
0x18005b92c  cmp     qword ptr [rsp+5C0h+var_578+8], 0
0x18005b932  jz      short loc_18005B947
0x18005b934  cmp     qword ptr [rsp+5C0h+var_578], 0
0x18005b93a  jz      short loc_18005B947
0x18005b93c  lea     rcx, [rsp+5C0h+var_578]
0x18005b941  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18005b946  nop
0x18005b947  lea     rdx, [r14+18h]
0x18005b94b  lea     rcx, [rsp+5C0h+var_580]
0x18005b950  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18005b955  or      ebx, 0FFFFFFFFh
0x18005b958  mov     rcx, [rsp+5C0h+var_580]
0x18005b95d  test    rcx, rcx
0x18005b960  cmovnz  ebx, cs:dword_1801C4EA8
0x18005b967  jz      short loc_18005B976
0x18005b969  mov     rax, [rcx]
0x18005b96c  mov     rax, [rax+10h]
0x18005b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b975  nop
0x18005b976  cmp     ebx, 0FFFFFFFFh
0x18005b979  jz      loc_18005BABA
0x18005b97f  mov     rdx, rsi
0x18005b982  lea     rcx, [rsp+5C0h+var_568]
0x18005b987  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18005b98c  mov     rdx, rax
0x18005b98f  lea     rcx, [rsp+5C0h+var_580]
0x18005b994  call    ??$CreateInstanceFromInner@UIStream@@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVStream@0@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x18005b999  nop
0x18005b99a  mov     ecx, 10h; unsigned __int64
0x18005b99f  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18005b9a4  mov     rbx, rax
0x18005b9a7  mov     qword ptr [rsp+5C0h+var_578], rax
0x18005b9ac  test    rax, rax
0x18005b9af  jz      short loc_18005B9C4
0x18005b9b1  lea     rdx, [rsp+5C0h+var_580]; struct Stream *
0x18005b9b6  mov     rcx, rax; this
0x18005b9b9  call    ??0Stream@win_dox@@QEAA@AEBV01@@Z; win_dox::Stream::Stream(win_dox::Stream const &)
0x18005b9be  mov     byte ptr [rbx+8], 1
0x18005b9c2  jmp     short loc_18005B9C6
0x18005b9c4  xor     ebx, ebx
0x18005b9c6  mov     rdx, rbx
0x18005b9c9  lea     rcx, [rsp+5C0h+var_548]
0x18005b9ce  call    ??0?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVByteReceiverOnStream@win_dox@@@Z; win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::ByteReceiverOnStream *)
0x18005b9d3  nop
0x18005b9d4  xorps   xmm0, xmm0
0x18005b9d7  movdqu  [rsp+5C0h+var_578], xmm0
0x18005b9dd  mov     rbx, [rsp+5C0h+var_548]
0x18005b9e2  mov     rdi, [rbp+4C0h+var_540]
0x18005b9e6  test    rbx, rbx
0x18005b9e9  jz      short loc_18005B9FD
0x18005b9eb  mov     rcx, rbx; this
0x18005b9ee  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18005b9f3  mov     qword ptr [rsp+5C0h+var_578], rbx
0x18005b9f8  mov     qword ptr [rsp+5C0h+var_578+8], rdi
0x18005b9fd  lea     rdx, [rsp+5C0h+var_578]
0x18005ba02  lea     rcx, [rbp+4C0h+var_520]
0x18005ba06  call    ??$CreateInstanceFromInner@UIByteReceiver@@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVByteReceiver@0@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>)
0x18005ba0b  nop
0x18005ba0c  lea     rdx, [rsp+5C0h+var_568]
0x18005ba11  lea     rcx, [r14+18h]
0x18005ba15  call    ?GetBytes@OpcPartContent@win_dox@@QEBA?AVByteCollection@2@XZ; win_dox::OpcPartContent::GetBytes(void)
0x18005ba1a  nop
0x18005ba1b  lea     rdx, [rsp+5C0h+var_558]
0x18005ba20  mov     rcx, rax
0x18005ba23  call    ?CreateSender@?$CreateSenderBase@UIByteCollection@@@win_dox@@QEBA?AVByteSender@2@XZ; win_dox::CreateSenderBase<IByteCollection>::CreateSender(void)
0x18005ba28  nop
0x18005ba29  lea     rdx, [rbp+4C0h+var_520]
0x18005ba2d  mov     rcx, rax
0x18005ba30  call    ??$StartSend@VByteReceiver@win_dox@@@?$StartSendBase@UIByteSender@@@win_dox@@QEAAXAEAVByteReceiver@1@@Z; win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(win_dox::ByteReceiver &)
0x18005ba35  nop
0x18005ba36  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x18005ba3d  mov     [rsp+5C0h+var_558], rax
0x18005ba42  mov     rcx, [rsp+5C0h+var_550]
0x18005ba47  test    rcx, rcx
0x18005ba4a  jz      short loc_18005BA61
0x18005ba4c  mov     rax, [rcx]
0x18005ba4f  mov     rax, [rax+10h]
0x18005ba53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba58  mov     [rsp+5C0h+var_550], 0
0x18005ba61  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x18005ba68  mov     [rsp+5C0h+var_568], rax
0x18005ba6d  mov     rcx, [rsp+5C0h+var_560]
0x18005ba72  test    rcx, rcx
0x18005ba75  jz      short loc_18005BA84
0x18005ba77  mov     rax, [rcx]
0x18005ba7a  mov     rax, [rax+10h]
0x18005ba7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba83  nop
0x18005ba84  lea     rcx, [rbp+4C0h+var_520]; this
0x18005ba88  call    ??1ByteReceiver@win_dox@@UEAA@XZ; win_dox::ByteReceiver::~ByteReceiver(void)
0x18005ba8d  nop
0x18005ba8e  test    rbx, rbx
0x18005ba91  jz      short loc_18005BAA3
0x18005ba93  test    rdi, rdi
0x18005ba96  jz      short loc_18005BAA3
0x18005ba98  lea     rcx, [rsp+5C0h+var_548]
0x18005ba9d  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18005baa2  nop
0x18005baa3  mov     rcx, [rsp+5C0h+var_580]
0x18005baa8  test    rcx, rcx
0x18005baab  jz      short loc_18005BABA
0x18005baad  mov     rax, [rcx]
0x18005bab0  mov     rax, [rax+10h]
0x18005bab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bab9  nop
0x18005baba  mov     rdx, rsi
0x18005babd  lea     rcx, [rsp+5C0h+var_568]
0x18005bac2  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18005bac7  mov     rdx, rax
0x18005baca  mov     rcx, r14
0x18005bacd  call    ?SendNotifications@OpcPartContentStream@win_dox@@AEAAXV?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcPartContentStream::SendNotifications(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x18005bad2  nop
0x18005bad3  lea     rcx, [rbp+4C0h+var_538]
0x18005bad7  call    ??1?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::~scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void)
0x18005badc  mov     rcx, [rbp+4C0h+var_40]
0x18005bae3  xor     rcx, rsp; StackCookie
0x18005bae6  call    __security_check_cookie
0x18005baeb  add     rsp, 598h
0x18005baf2  pop     r15
0x18005baf4  pop     r14
0x18005baf6  pop     rdi
0x18005baf7  pop     rsi
0x18005baf8  pop     rbx
0x18005baf9  pop     rbp
0x18005bafa  retn
```
