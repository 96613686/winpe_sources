# CreateTempFileStreamOnByteSender

- ea: `0x1800568d0`
- end: `0x180056fd9`
- name: `CreateTempFileStreamOnByteSender`
- size: `1801`
- prototype: `__int64 __fastcall(__int64, __int64, win_dox::Stream **)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800016b0`
- `0x180010524`
- `0x180010a00`
- `0x180012fa0`
- `0x180015a68`
- `0x180018c00`
- `0x18001a810`
- `0x1800460f0`
- `0x1800517a0`
- `0x180053f80`
- `0x180054450`
- `0x180055f5c`
- `0x180055ff4`
- `0x1800568d0`
- `0x180057530`
- `0x1800576b8`
- `0x180057770`
- `0x1800654b0`
- `0x180067218`
- `0x180079ca0`
- `0x1800c4998`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800d90c4`
- `0x1800d91bc`
- `0x1800dfe08`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800569b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800569b8`

## string_xrefs

- `0x180056f3d`: `Call to ::CreateFile failed with HResult 0x%X.`
- `0x180056dce`: `CreateTempFileStreamOnByteSender parameter rootFolder cannot be NULL`
- `0x180056e3e`: `CreateTempFileStreamOnByteSender parameter byteSender cannot be NULL`
- `0x180056eae`: `CreateTempFileStreamOnByteSender parameter stream cannot be NULL`

## pseudocode

```c
__int64 __fastcall CreateTempFileStreamOnByteSender(__int64 a1, __int64 a2, win_dox::Stream **a3)
{
  __int64 v6; // rdi
  __int64 TemporaryFileName; // rax
  const WCHAR *v8; // rcx
  HANDLE FileW; // rdx
  const char *v10; // rdx
  win_musl::detail *v11; // rcx
  unsigned int v12; // r8d
  win_dox::Stream *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  const char *v17; // rdx
  unsigned int v18; // r8d
  win_dox::Stream *v19; // rax
  win_dox::Stream *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rdx
  const char *v23; // rdx
  unsigned int v24; // r8d
  win_dox::Stream *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  win_musl *v30; // rcx
  win_musl::Formatter *v32; // rcx
  struct win_musl::TStringEllipseBase *v33; // rax
  win_musl::Formatter *v34; // rax
  struct win_musl::TStringEllipseBase *v35; // rax
  win_musl::Formatter *v36; // rax
  struct win_musl::TStringEllipseBase *v37; // rax
  unsigned int LastErrorAsFailHR; // ebx
  win_dox::Stream *v39; // [rsp+40h] [rbp-858h] BYREF
  __int64 v40; // [rsp+48h] [rbp-850h] BYREF
  __int128 v41; // [rsp+50h] [rbp-848h] BYREF
  __int64 v42; // [rsp+60h] [rbp-838h] BYREF
  __int128 v43; // [rsp+68h] [rbp-830h] BYREF
  __int64 v44; // [rsp+78h] [rbp-820h] BYREF
  win_scope::counted_strong_weak_base *v45; // [rsp+80h] [rbp-818h] BYREF
  __int64 v46; // [rsp+88h] [rbp-810h]
  win_scope::counted_strong_weak_base *v47; // [rsp+90h] [rbp-808h] BYREF
  __int64 v48; // [rsp+98h] [rbp-800h]
  win_scope::counted_strong_weak_base *v49; // [rsp+A0h] [rbp-7F8h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-7F0h]
  _BYTE v51[16]; // [rsp+B0h] [rbp-7E8h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-7D8h]
  _BYTE v53[24]; // [rsp+C8h] [rbp-7D0h] BYREF
  char v54[8]; // [rsp+E0h] [rbp-7B8h] BYREF
  void *v55; // [rsp+E8h] [rbp-7B0h]
  __int64 v56; // [rsp+F8h] [rbp-7A0h]
  unsigned __int64 v57; // [rsp+100h] [rbp-798h]
  char v58[8]; // [rsp+108h] [rbp-790h] BYREF
  void *v59; // [rsp+110h] [rbp-788h]
  __int64 v60; // [rsp+120h] [rbp-778h]
  unsigned __int64 v61; // [rsp+128h] [rbp-770h]
  char v62[8]; // [rsp+130h] [rbp-768h] BYREF
  void *v63; // [rsp+138h] [rbp-760h]
  __int64 v64; // [rsp+148h] [rbp-750h]
  unsigned __int64 v65; // [rsp+150h] [rbp-748h]
  char v66[8]; // [rsp+158h] [rbp-740h] BYREF
  void *Block; // [rsp+160h] [rbp-738h]
  __int64 v68; // [rsp+170h] [rbp-728h]
  unsigned __int64 v69; // [rsp+178h] [rbp-720h]
  _BYTE v70[96]; // [rsp+180h] [rbp-718h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+1E0h] [rbp-6B8h] BYREF
  _BYTE v72[160]; // [rsp+280h] [rbp-618h] BYREF
  _BYTE v73[160]; // [rsp+320h] [rbp-578h] BYREF
  _BYTE v74[160]; // [rsp+3C0h] [rbp-4D8h] BYREF
  wchar_t v75[512]; // [rsp+460h] [rbp-438h] BYREF

  v52 = -2;
  try
  {
    if ( !a1 )
    {
      std::wstring::wstring(v54, L"CreateTempFileStreamOnByteSender parameter rootFolder cannot be NULL");
      v32 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v70, v54);
      v33 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v32);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x240u,
        0x80004003,
        v33);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !a2 )
    {
      std::wstring::wstring(v54, L"CreateTempFileStreamOnByteSender parameter byteSender cannot be NULL");
      v34 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v70, v54);
      v35 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v34);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v72,
        0x247u,
        0x80004003,
        v35);
      throw (SplException::THResultException *)v72;
    }
    if ( !a3 )
    {
      std::wstring::wstring(v54, L"CreateTempFileStreamOnByteSender parameter stream cannot be NULL");
      v36 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v70, v54);
      v37 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v36);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v73,
        0x24Eu,
        0x80004003,
        v37);
      throw (SplException::THResultException *)v73;
    }
    v6 = std::wstring::wstring(v54, L".tmp");
    std::wstring::wstring(v62, L"APPX");
    std::wstring::wstring(v58, a1);
    TemporaryFileName = win_musl::CreateTemporaryFileName(v66, v58, v62, v6);
    v8 = (const WCHAR *)(TemporaryFileName + 8);
    if ( *(_QWORD *)(TemporaryFileName + 32) >= 8u )
      v8 = *(const WCHAR **)v8;
    FileW = CreateFileW(v8, 0xC0000000, 0, 0, 2u, 0x4000100u, 0);
    win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(
      v51,
      FileW);
    if ( v69 >= 8 )
      operator delete(Block);
    v69 = 7;
    v68 = 0;
    LOWORD(Block) = 0;
    if ( v61 >= 8 )
      operator delete(v59);
    v61 = 7;
    v60 = 0;
    LOWORD(v59) = 0;
    if ( v65 >= 8 )
      operator delete(v63);
    v65 = 7;
    v64 = 0;
    LOWORD(v63) = 0;
    if ( v57 >= 8 )
      operator delete(v55);
    v57 = 7;
    v56 = 0;
    LOWORD(v55) = 0;
    if ( (unsigned __int8)win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::operator!(v51) )
    {
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v11);
      memset_0(v75, 0, sizeof(v75));
      StringCchPrintfW(v75, 0x200u, L"Call to ::CreateFile failed with HResult 0x%X.", LastErrorAsFailHR);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v74,
        0x25Bu,
        LastErrorAsFailHR,
        (struct win_musl::TStringEllipseBase *)v75);
      throw (SplException::THResultException *)v74;
    }
    v13 = (win_dox::Stream *)operator new(0x20u, v10, v12);
    v39 = v13;
    if ( v13 )
      v14 = win_dox::StreamOnFileHandle::StreamOnFileHandle(v13, v51, 2);
    else
      v14 = 0;
    win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(
      &v49,
      v14);
    v41 = 0;
    if ( v49 )
    {
      win_scope::counted_strong_weak_base::AddRef(v49);
      *(_QWORD *)&v41 = v15;
      *((_QWORD *)&v41 + 1) = v16;
    }
    win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v44,
      &v41);
    v19 = (win_dox::Stream *)operator new(0x10u, v17, v18);
    v20 = v19;
    v39 = v19;
    if ( v19 )
    {
      win_dox::Stream::Stream(v19, (const struct Stream *)&v44);
      *((_BYTE *)v20 + 8) = 1;
    }
    else
    {
      v20 = 0;
    }
    win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(
      &v47,
      v20);
    v43 = 0;
    if ( v47 )
    {
      win_scope::counted_strong_weak_base::AddRef(v47);
      *(_QWORD *)&v43 = v21;
      *((_QWORD *)&v43 + 1) = v22;
    }
    win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(
      v53,
      &v43);
    *(_QWORD *)&v41 = &win_dox::OpcRelationshipSender::`vftable';
    v42 = a2;
    *((_QWORD *)&v41 + 1) = 0;
    win_scope::detail::scope_helper<IByteSender *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IByteSender *,win_scope::const_policies<win_scope::com_policies>,IByteSender *>(
      (char *)&v41 + 8,
      &v42);
    *(_QWORD *)&v41 = &win_dox::OpcRelationshipCollection::`vftable';
    win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(&v41, v53);
    v25 = (win_dox::Stream *)operator new(0x20u, v23, v24);
    v39 = v25;
    if ( v25 )
      v26 = win_dox::StreamOnFileHandle::StreamOnFileHandle(v25, v51, 0);
    else
      v26 = 0;
    win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(
      &v45,
      v26);
    v43 = 0;
    if ( v45 )
    {
      win_scope::counted_strong_weak_base::AddRef(v45);
      *(_QWORD *)&v43 = v27;
      *((_QWORD *)&v43 + 1) = v28;
    }
    win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v40,
      &v43);
    v29 = win_dox::Stream::Stream((win_dox::Stream *)&v42, (const struct Stream *)&v40);
    win_dox::to_interface_with_create<IStream>::resolve<win_dox::Stream>(&v39, v29);
    *a3 = v39;
    if ( v40 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v40 = 0;
    }
    if ( v46 && v45 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v45);
      v45 = 0;
      v46 = 0;
    }
    if ( *((_QWORD *)&v41 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v41 + 1) + 16LL))(*((_QWORD *)&v41 + 1));
    win_dox::ByteReceiver::~ByteReceiver((win_dox::ByteReceiver *)v53);
    if ( v48 && v47 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v47);
      v47 = 0;
      v48 = 0;
    }
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    if ( v50 && v49 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v49);
      v49 = 0;
      v50 = 0;
    }
    win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::~scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(v51);
  }
  catch ( ... )
  {
    win_musl::detail_process_errors(v30);
  }
  return 0;
}

```

## disassembly

```asm
0x1800568d0  mov     r11, rsp
0x1800568d3  push    rsi
0x1800568d4  push    rdi
0x1800568d5  push    r12
0x1800568d7  push    r14
0x1800568d9  push    r15
0x1800568db  sub     rsp, 870h
0x1800568e2  mov     qword ptr [r11-7D8h], 0FFFFFFFFFFFFFFFEh
0x1800568ed  mov     [r11+10h], rbx
0x1800568f1  mov     rax, cs:__security_cookie
0x1800568f8  xor     rax, rsp
0x1800568fb  mov     [rsp+898h+var_38], rax
0x180056903  mov     r14, r8
0x180056906  mov     rsi, rdx
0x180056909  mov     rbx, rcx
0x18005690c  xor     r12d, r12d
0x18005690f  mov     r15d, r12d
0x180056912  lea     rcx, [r11-7B8h]
0x180056919  test    rbx, rbx
0x18005691c  jz      loc_180056DCE
0x180056922  test    rdx, rdx
0x180056925  jz      loc_180056E3E
0x18005692b  test    r8, r8
0x18005692e  jz      loc_180056EAE
0x180056934  lea     rdx, aTmp; ".tmp"
0x18005693b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180056940  mov     rdi, rax
0x180056943  lea     rdx, aAppx; "APPX"
0x18005694a  lea     rcx, [rsp+898h+var_768]
0x180056952  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180056957  nop
0x180056958  mov     rdx, rbx
0x18005695b  lea     rcx, [rsp+898h+var_790]
0x180056963  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180056968  nop
0x180056969  mov     r9, rdi
0x18005696c  lea     r8, [rsp+898h+var_768]
0x180056974  lea     rdx, [rsp+898h+var_790]
0x18005697c  lea     rcx, [rsp+898h+var_740]
0x180056984  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@00@Z; win_musl::CreateTemporaryFileName(std::wstring const &,std::wstring const &,std::wstring const &)
0x180056989  nop
0x18005698a  lea     rcx, [rax+8]
0x18005698e  cmp     qword ptr [rax+20h], 8
0x180056993  jb      short loc_180056998
0x180056995  mov     rcx, [rcx]; lpFileName
0x180056998  mov     [rsp+898h+hTemplateFile], r12; hTemplateFile
0x18005699d  mov     [rsp+898h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x1800569a5  mov     [rsp+898h+dwCreationDisposition], 2; dwCreationDisposition
0x1800569ad  xor     r9d, r9d; lpSecurityAttributes
0x1800569b0  xor     r8d, r8d; dwShareMode
0x1800569b3  mov     edx, 0C0000000h; dwDesiredAccess
0x1800569b8  call    cs:__imp_CreateFileW
0x1800569be  mov     rdx, rax
0x1800569c1  lea     rcx, [rsp+898h+var_7E8]
0x1800569c9  call    ??0?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@PEAX@Z; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void *)
0x1800569ce  nop
0x1800569cf  cmp     [rsp+898h+var_720], 8
0x1800569d8  jnb     loc_180056D6E
0x1800569de  mov     ebx, 7
0x1800569e3  mov     [rsp+898h+var_720], rbx
0x1800569eb  mov     [rsp+898h+var_728], r12
0x1800569f3  mov     word ptr [rsp+898h+Block], r12w
0x1800569fc  cmp     [rsp+898h+var_770], 8
0x180056a05  jnb     loc_180056D80
0x180056a0b  mov     [rsp+898h+var_770], rbx
0x180056a13  mov     [rsp+898h+var_778], r12
0x180056a1b  mov     word ptr [rsp+898h+var_788], r12w
0x180056a24  cmp     [rsp+898h+var_748], 8
0x180056a2d  jnb     loc_180056D92
0x180056a33  mov     [rsp+898h+var_748], rbx
0x180056a3b  mov     [rsp+898h+var_750], r12
0x180056a43  mov     word ptr [rsp+898h+var_760], r12w
0x180056a4c  cmp     [rsp+898h+var_798], 8
0x180056a55  jnb     loc_180056DA4
0x180056a5b  mov     [rsp+898h+var_798], rbx
0x180056a63  mov     [rsp+898h+var_7A0], r12
0x180056a6b  mov     word ptr [rsp+898h+var_7B0], r12w
0x180056a74  lea     rcx, [rsp+898h+var_7E8]
0x180056a7c  call    ??7?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEBA_NXZ; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::operator!(void)
0x180056a81  test    al, al
0x180056a83  jnz     loc_180056F1E
0x180056a89  mov     edi, 20h ; ' '
0x180056a8e  mov     ecx, edi; unsigned __int64
0x180056a90  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180056a95  mov     [rsp+898h+var_858], rax
0x180056a9a  test    rax, rax
0x180056a9d  jz      loc_180056DC6
0x180056aa3  lea     r8d, [rdi-1Eh]
0x180056aa7  lea     rdx, [rsp+898h+var_7E8]
0x180056aaf  mov     rcx, rax
0x180056ab2  call    ??0StreamOnFileHandle@win_dox@@QEAA@AEBV?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@W4HandleAccessMode@01@@Z; win_dox::StreamOnFileHandle::StreamOnFileHandle(win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>> const &,win_dox::StreamOnFileHandle::HandleAccessMode)
0x180056ab7  nop
0x180056ab8  mov     rdx, rax
0x180056abb  lea     rcx, [rsp+898h+var_7F8]
0x180056ac3  call    ??0?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVStreamOnFileHandle@win_dox@@@Z; win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::StreamOnFileHandle *)
0x180056ac8  nop
0x180056ac9  xorps   xmm0, xmm0
0x180056acc  movdqu  [rsp+898h+var_848], xmm0
0x180056ad2  mov     rcx, [rsp+898h+var_7F8]; this
0x180056ada  test    rcx, rcx
0x180056add  jz      short loc_180056AF6
0x180056adf  mov     rdx, [rsp+898h+var_7F0]
0x180056ae7  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180056aec  mov     qword ptr [rsp+898h+var_848], rcx
0x180056af1  mov     qword ptr [rsp+898h+var_848+8], rdx
0x180056af6  lea     rdx, [rsp+898h+var_848]
0x180056afb  lea     rcx, [rsp+898h+var_820]
0x180056b00  call    ??$CreateInstanceFromInner@UIStream@@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVStream@0@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x180056b05  nop
0x180056b06  mov     ecx, 10h; unsigned __int64
0x180056b0b  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180056b10  mov     rbx, rax
0x180056b13  mov     [rsp+898h+var_858], rax
0x180056b18  test    rax, rax
0x180056b1b  jz      loc_180056DB6
0x180056b21  lea     rdx, [rsp+898h+var_820]; struct Stream *
0x180056b26  mov     rcx, rax; this
0x180056b29  call    ??0Stream@win_dox@@QEAA@AEBV01@@Z; win_dox::Stream::Stream(win_dox::Stream const &)
0x180056b2e  mov     byte ptr [rbx+8], 1
0x180056b32  mov     rdx, rbx
0x180056b35  lea     rcx, [rsp+898h+var_808]
0x180056b3d  call    ??0?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVByteReceiverOnStream@win_dox@@@Z; win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::ByteReceiverOnStream *)
0x180056b42  nop
0x180056b43  xorps   xmm0, xmm0
0x180056b46  movdqu  [rsp+898h+var_830], xmm0
0x180056b4c  mov     rcx, [rsp+898h+var_808]; this
0x180056b54  test    rcx, rcx
0x180056b57  jz      short loc_180056B70
0x180056b59  mov     rdx, [rsp+898h+var_800]
0x180056b61  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180056b66  mov     qword ptr [rsp+898h+var_830], rcx
0x180056b6b  mov     qword ptr [rsp+898h+var_830+8], rdx
0x180056b70  lea     rdx, [rsp+898h+var_830]
0x180056b75  lea     rcx, [rsp+898h+var_7D0]
0x180056b7d  call    ??$CreateInstanceFromInner@UIByteReceiver@@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVByteReceiver@0@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>)
0x180056b82  nop
0x180056b83  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x180056b8a  mov     qword ptr [rsp+898h+var_848], rax
0x180056b8f  mov     [rsp+898h+var_838], rsi
0x180056b94  mov     qword ptr [rsp+898h+var_848+8], r12
0x180056b99  lea     rdx, [rsp+898h+var_838]
0x180056b9e  lea     rcx, [rsp+898h+var_848+8]
0x180056ba3  call    ??$construct_acquire@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIByteSender@@@Z; win_scope::detail::scope_helper<IByteSender *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IByteSender *,win_scope::const_policies<win_scope::com_policies>,IByteSender *>(win_scope::scope<IByteSender *,win_scope::const_policies<win_scope::com_policies>> *,IByteSender * *)
0x180056ba8  lea     rax, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x180056baf  mov     qword ptr [rsp+898h+var_848], rax
0x180056bb4  lea     rdx, [rsp+898h+var_7D0]
0x180056bbc  lea     rcx, [rsp+898h+var_848]
0x180056bc1  call    ??$StartSend@VByteReceiver@win_dox@@@?$StartSendBase@UIByteSender@@@win_dox@@QEAAXAEAVByteReceiver@1@@Z; win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(win_dox::ByteReceiver &)
0x180056bc6  mov     rcx, rdi; unsigned __int64
0x180056bc9  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180056bce  mov     [rsp+898h+var_858], rax
0x180056bd3  test    rax, rax
0x180056bd6  jz      loc_180056DBE
0x180056bdc  xor     r8d, r8d
0x180056bdf  lea     rdx, [rsp+898h+var_7E8]
0x180056be7  mov     rcx, rax
0x180056bea  call    ??0StreamOnFileHandle@win_dox@@QEAA@AEBV?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@W4HandleAccessMode@01@@Z; win_dox::StreamOnFileHandle::StreamOnFileHandle(win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>> const &,win_dox::StreamOnFileHandle::HandleAccessMode)
0x180056bef  nop
0x180056bf0  mov     rdx, rax
0x180056bf3  lea     rcx, [rsp+898h+var_818]
0x180056bfb  call    ??0?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVStreamOnFileHandle@win_dox@@@Z; win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::StreamOnFileHandle *)
0x180056c00  nop
0x180056c01  xorps   xmm0, xmm0
0x180056c04  movdqu  [rsp+898h+var_830], xmm0
0x180056c0a  mov     rcx, [rsp+898h+var_818]; this
0x180056c12  test    rcx, rcx
0x180056c15  jz      short loc_180056C2E
0x180056c17  mov     rdx, [rsp+898h+var_810]
0x180056c1f  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180056c24  mov     qword ptr [rsp+898h+var_830], rcx
0x180056c29  mov     qword ptr [rsp+898h+var_830+8], rdx
0x180056c2e  lea     rdx, [rsp+898h+var_830]
0x180056c33  lea     rcx, [rsp+898h+var_850]
0x180056c38  call    ??$CreateInstanceFromInner@UIStream@@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVStream@0@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x180056c3d  nop
0x180056c3e  lea     rdx, [rsp+898h+var_850]; struct Stream *
0x180056c43  lea     rcx, [rsp+898h+var_838]; this
0x180056c48  call    ??0Stream@win_dox@@QEAA@AEBV01@@Z; win_dox::Stream::Stream(win_dox::Stream const &)
0x180056c4d  mov     rdx, rax
0x180056c50  lea     rcx, [rsp+898h+var_858]
0x180056c55  call    ??$resolve@VStream@win_dox@@@?$to_interface_with_create@UIStream@@@win_dox@@SA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VStream@1@@Z; win_dox::to_interface_with_create<IStream>::resolve<win_dox::Stream>(win_dox::Stream)
0x180056c5a  mov     rax, [rsp+898h+var_858]
0x180056c5f  mov     [r14], rax
0x180056c62  mov     rcx, [rsp+898h+var_850]
0x180056c67  test    rcx, rcx
0x180056c6a  jz      short loc_180056C7D
0x180056c6c  mov     rax, [rcx]
0x180056c6f  mov     rax, [rax+10h]
0x180056c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c78  mov     [rsp+898h+var_850], r12
0x180056c7d  cmp     [rsp+898h+var_810], r12
0x180056c85  jz      short loc_180056CAE
0x180056c87  cmp     [rsp+898h+var_818], r12
0x180056c8f  jz      short loc_180056CAE
0x180056c91  lea     rcx, [rsp+898h+var_818]
0x180056c99  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180056c9e  mov     [rsp+898h+var_818], r12
0x180056ca6  mov     [rsp+898h+var_810], r12
0x180056cae  mov     rcx, qword ptr [rsp+898h+var_848+8]
0x180056cb3  test    rcx, rcx
0x180056cb6  jnz     loc_180056D5D
0x180056cbc  lea     rcx, [rsp+898h+var_7D0]; this
0x180056cc4  call    ??1ByteReceiver@win_dox@@UEAA@XZ; win_dox::ByteReceiver::~ByteReceiver(void)
0x180056cc9  nop
0x180056cca  cmp     [rsp+898h+var_800], r12
0x180056cd2  jnz     loc_180056F9F
0x180056cd8  mov     rcx, [rsp+898h+var_820]
0x180056cdd  test    rcx, rcx
0x180056ce0  jz      short loc_180056CF3
0x180056ce2  mov     rax, [rcx]
0x180056ce5  mov     rax, [rax+10h]
0x180056ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cee  mov     [rsp+898h+var_820], r12
0x180056cf3  cmp     [rsp+898h+var_7F0], r12
0x180056cfb  jz      short loc_180056D24
0x180056cfd  cmp     [rsp+898h+var_7F8], r12
0x180056d05  jz      short loc_180056D24
0x180056d07  lea     rcx, [rsp+898h+var_7F8]
0x180056d0f  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180056d14  mov     [rsp+898h+var_7F8], r12
0x180056d1c  mov     [rsp+898h+var_7F0], r12
0x180056d24  lea     rcx, [rsp+898h+var_7E8]
0x180056d2c  call    ??1?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::~scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void)
0x180056d31  nop
0x180056d32  mov     eax, r15d
0x180056d35  mov     rcx, [rsp+898h+var_38]
0x180056d3d  xor     rcx, rsp; StackCookie
0x180056d40  call    __security_check_cookie
0x180056d45  mov     rbx, [rsp+898h+arg_8]
0x180056d4d  add     rsp, 870h
0x180056d54  pop     r15
0x180056d56  pop     r14
0x180056d58  pop     r12
0x180056d5a  pop     rdi
0x180056d5b  pop     rsi
0x180056d5c  retn
0x180056d5d  mov     rax, [rcx]
0x180056d60  mov     rax, [rax+10h]
0x180056d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d69  jmp     loc_180056CBC
0x180056d6e  mov     rcx, [rsp+898h+Block]; Block
0x180056d76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056d7b  jmp     loc_1800569DE
0x180056d80  mov     rcx, [rsp+898h+var_788]; Block
0x180056d88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056d8d  jmp     loc_180056A0B
0x180056d92  mov     rcx, [rsp+898h+var_760]; Block
0x180056d9a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056d9f  jmp     loc_180056A33
0x180056da4  mov     rcx, [rsp+898h+var_7B0]; Block
0x180056dac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056db1  jmp     loc_180056A5B
0x180056db6  mov     rbx, r12
0x180056db9  jmp     loc_180056B32
0x180056dbe  mov     rax, r12
0x180056dc1  jmp     loc_180056BF0
0x180056dc6  mov     rax, r12
0x180056dc9  jmp     loc_180056AB8
0x180056dce  lea     rdx, aCreatetempfile_2; "CreateTempFileStreamOnByteSender parame"...
0x180056dd5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180056dda  nop
0x180056ddb  lea     rdx, [rsp+898h+var_7B8]
0x180056de3  lea     rcx, [rsp+898h+var_718]
0x180056deb  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180056df0  nop
0x180056df1  mov     rcx, rax; this
0x180056df4  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180056df9  mov     [rsp+898h+hTemplateFile], rax; struct win_musl::TStringEllipseBase *
0x180056dfe  mov     [rsp+898h+dwFlagsAndAttributes], 80004003h; unsigned int
0x180056e06  mov     [rsp+898h+dwCreationDisposition], 240h; unsigned int
0x180056e0e  lea     r9, word_18013A0B6
0x180056e15  lea     r8, aNoFilename; "(no filename)"
0x180056e1c  lea     rcx, [rsp+898h+pExceptionObject]; this
0x180056e24  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180056e29  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180056e30  lea     rcx, [rsp+898h+pExceptionObject]; pExceptionObject
0x180056e38  call    _CxxThrowException_0
0x180056e3e  lea     rdx, aCreatetempfile_5; "CreateTempFileStreamOnByteSender parame"...
0x180056e45  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180056e4a  nop
0x180056e4b  lea     rdx, [rsp+898h+var_7B8]
0x180056e53  lea     rcx, [rsp+898h+var_718]
0x180056e5b  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180056e60  nop
0x180056e61  mov     rcx, rax; this
0x180056e64  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180056e69  mov     [rsp+898h+hTemplateFile], rax; struct win_musl::TStringEllipseBase *
0x180056e6e  mov     [rsp+898h+dwFlagsAndAttributes], 80004003h; unsigned int
0x180056e76  mov     [rsp+898h+dwCreationDisposition], 247h; unsigned int
0x180056e7e  lea     r9, word_18013A0B6
0x180056e85  lea     r8, aNoFilename; "(no filename)"
0x180056e8c  lea     rcx, [rsp+898h+var_618]; this
0x180056e94  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180056e99  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180056ea0  lea     rcx, [rsp+898h+var_618]; pExceptionObject
0x180056ea8  call    _CxxThrowException_0
0x180056eae  lea     rdx, aCreatetempfile_1; "CreateTempFileStreamOnByteSender parame"...
0x180056eb5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180056eba  nop
0x180056ebb  lea     rdx, [rsp+898h+var_7B8]
  ... truncated ...
```
