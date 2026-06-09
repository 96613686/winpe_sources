# win_musl::production::XmlWriter::StartWriteContent(void)

- ea: `0x180077b44`
- end: `0x180077d9c`
- name: `?StartWriteContent@XmlWriter@production@win_musl@@QEAA?AV?$scope@PEAUISAXContentHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `600`
- prototype: `__int64 __fastcall(void **ppvObject)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3700`
- `0x1800a3824`

## callees

- `0x1800019b0`
- `0x1800155e8`
- `0x1800156a4`
- `0x180015a68`
- `0x180015af4`
- `0x1800517a0`
- `0x180077b44`
- `0x180077da4`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180077c1b`
- `XmlLite!CreateXmlWriter` at `0x180077c1b`

## string_xrefs

- `0x180077cba`: `Call to IXmlWriter::SetOutput failed with HResult 0x%X.`
- `0x180077c3b`: `Call to ::CreateXmlWriter failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall win_musl::production::XmlWriter::StartWriteContent(void **ppvObject, _QWORD *a2)
{
  __int64 v4; // rcx
  HRESULT XmlWriter; // esi
  signed int v6; // esi
  _QWORD *v7; // rax
  _QWORD v9[3]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v10[40]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v12[160]; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t v13[512]; // [rsp+168h] [rbp+60h] BYREF

  v9[2] = -2;
  v9[0] = a2;
  if ( *((_DWORD *)ppvObject + 4) == 2 )
  {
    win_musl::DebugLogHelper("(no filename)", &word_18013A0B6, 212, 1024, -2147418113, L"Writing content started");
    std::string::string(v10, "Program has entered an unexpected state");
    std::logic_error::logic_error(pExceptionObject, v10);
    throw (std::logic_error *)pExceptionObject;
  }
  v4 = (__int64)*ppvObject;
  *ppvObject = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *ppvObject = 0;
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlWriter < 0 )
  {
    memset_0(v13, 0, sizeof(v13));
    StringCchPrintfW(v13, 0x200u, L"Call to ::CreateXmlWriter failed with HResult 0x%X.", (unsigned int)XmlWriter);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v12,
      0xE1u,
      XmlWriter,
      (struct win_musl::TStringEllipseBase *)v13);
    throw (SplException::THResultException *)v12;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppvObject[1]);
  if ( v6 < 0 )
  {
    memset_0(v13, 0, sizeof(v13));
    StringCchPrintfW(v13, 0x200u, L"Call to IXmlWriter::SetOutput failed with HResult 0x%X.", (unsigned int)v6);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v12,
      0xE5u,
      v6,
      (struct win_musl::TStringEllipseBase *)v13);
    throw (SplException::THResultException *)v12;
  }
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 2);
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 1);
  *((_DWORD *)ppvObject + 4) = 2;
  v7 = (_QWORD *)win_musl::UnknownOnlyLite<win_musl::production::XmlWriterAdapter,win_mp_lib::type_list<ISAXContentHandler,win_mp_lib::null_type>,win_mp_lib::null_type>::CreateInstance<win_scope::no_addref_release<IXmlWriter> *>(
                   v9,
                   *ppvObject);
  *a2 = 0;
  win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
    a2,
    *v7);
  if ( v9[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
  return a2;
}

```

## disassembly

```asm
0x180077b44  mov     rax, rsp
0x180077b47  push    rbp
0x180077b48  push    rsi
0x180077b49  push    rdi
0x180077b4a  lea     rbp, [rax-488h]
0x180077b51  sub     rsp, 570h
0x180077b58  mov     qword ptr [rsp+580h+var_530], 0FFFFFFFFFFFFFFFEh
0x180077b61  mov     [rax+18h], rbx
0x180077b65  mov     rax, cs:__security_cookie
0x180077b6c  xor     rax, rsp
0x180077b6f  mov     [rbp+480h+var_20], rax
0x180077b76  mov     rdi, rdx
0x180077b79  mov     rbx, rcx
0x180077b7c  mov     [rsp+40h], rdx
0x180077b81  cmp     dword ptr [rcx+10h], 2
0x180077b85  jnz     short loc_180077BEB
0x180077b87  lea     rax, aWritingContent; "Writing content started"
0x180077b8e  mov     qword ptr [rsp+580h+var_558], rax
0x180077b93  mov     [rsp+580h+var_560], 8000FFFFh
0x180077b9b  mov     r9d, 400h
0x180077ba1  mov     r8d, 0D4h
0x180077ba7  lea     rdx, word_18013A0B6
0x180077bae  lea     rcx, aNoFilename; "(no filename)"
0x180077bb5  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x180077bba  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x180077bc1  lea     rcx, [rsp+58h]
0x180077bc6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180077bcb  nop
0x180077bcc  lea     rdx, [rsp+58h]
0x180077bd1  lea     rcx, [rbp+480h+pExceptionObject]
0x180077bd5  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x180077bda  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180077be1  lea     rcx, [rbp+480h+pExceptionObject]; pExceptionObject
0x180077be5  call    _CxxThrowException_0
0x180077beb  mov     rcx, [rcx]
0x180077bee  mov     qword ptr [rbx], 0
0x180077bf5  test    rcx, rcx
0x180077bf8  jz      short loc_180077C07
0x180077bfa  mov     rax, [rcx]
0x180077bfd  mov     rax, [rax+10h]
0x180077c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c06  nop
0x180077c07  mov     qword ptr [rbx], 0
0x180077c0e  xor     r8d, r8d; pMalloc
0x180077c11  mov     rdx, rbx; ppvObject
0x180077c14  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180077c1b  call    cs:__imp_CreateXmlWriter
0x180077c21  mov     esi, eax
0x180077c23  test    eax, eax
0x180077c25  jns     short loc_180077C8D
0x180077c27  xor     edx, edx; Val
0x180077c29  mov     r8d, 400h; Size
0x180077c2f  lea     rcx, [rbp+480h+var_420]; void *
0x180077c33  call    memset_0
0x180077c38  mov     r9d, esi
0x180077c3b  lea     r8, aCallToCreatexm; "Call to ::CreateXmlWriter failed with H"...
0x180077c42  mov     edx, 200h; unsigned __int64
0x180077c47  lea     rcx, [rbp+480h+var_420]; wchar_t *
0x180077c4b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180077c50  lea     rax, [rbp+480h+var_420]
0x180077c54  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180077c59  mov     [rsp+580h+var_558], esi; unsigned int
0x180077c5d  mov     [rsp+580h+var_560], 0E1h; unsigned int
0x180077c65  lea     r9, word_18013A0B6
0x180077c6c  lea     r8, aNoFilename; "(no filename)"
0x180077c73  lea     rcx, [rbp+480h+var_4C0]; this
0x180077c77  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180077c7c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180077c83  lea     rcx, [rbp+480h+var_4C0]; pExceptionObject
0x180077c87  call    _CxxThrowException_0
0x180077c8d  mov     rcx, [rbx]
0x180077c90  mov     rax, [rcx]
0x180077c93  mov     rdx, [rbx+8]
0x180077c97  mov     rax, [rax+18h]
0x180077c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ca0  mov     esi, eax
0x180077ca2  test    eax, eax
0x180077ca4  jns     short loc_180077D0C
0x180077ca6  xor     edx, edx; Val
0x180077ca8  mov     r8d, 400h; Size
0x180077cae  lea     rcx, [rbp+480h+var_420]; void *
0x180077cb2  call    memset_0
0x180077cb7  mov     r9d, esi
0x180077cba  lea     r8, aCallToIxmlwrit; "Call to IXmlWriter::SetOutput failed wi"...
0x180077cc1  mov     edx, 200h; unsigned __int64
0x180077cc6  lea     rcx, [rbp+480h+var_420]; wchar_t *
0x180077cca  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180077ccf  lea     rax, [rbp+480h+var_420]
0x180077cd3  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180077cd8  mov     [rsp+580h+var_558], esi; unsigned int
0x180077cdc  mov     [rsp+580h+var_560], 0E5h; unsigned int
0x180077ce4  lea     r9, word_18013A0B6
0x180077ceb  lea     r8, aNoFilename; "(no filename)"
0x180077cf2  lea     rcx, [rbp+480h+var_4C0]; this
0x180077cf6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180077cfb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180077d02  lea     rcx, [rbp+480h+var_4C0]; pExceptionObject
0x180077d06  call    _CxxThrowException_0
0x180077d0c  mov     rcx, [rbx]
0x180077d0f  mov     rax, [rcx]
0x180077d12  xor     r8d, r8d
0x180077d15  lea     edx, [r8+2]
0x180077d19  mov     rax, [rax+28h]
0x180077d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d22  mov     rcx, [rbx]
0x180077d25  mov     rax, [rcx]
0x180077d28  xor     r8d, r8d
0x180077d2b  lea     edx, [r8+1]
0x180077d2f  mov     rax, [rax+28h]
0x180077d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d38  mov     dword ptr [rbx+10h], 2
0x180077d3f  mov     rdx, [rbx]
0x180077d42  lea     rcx, [rsp+40h]
0x180077d47  call    ??$CreateInstance@PEAV?$no_addref_release@UIXmlWriter@@@win_scope@@@?$UnknownOnlyLite@VXmlWriterAdapter@production@win_musl@@V?$type_list@UISAXContentHandler@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@SA?AV?$scope@PEAV?$UnknownOnlyLite@VXmlWriterAdapter@production@win_musl@@V?$type_list@UISAXContentHandler@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAV?$no_addref_release@UIXmlWriter@@@3@@Z; win_musl::UnknownOnlyLite<win_musl::production::XmlWriterAdapter,win_mp_lib::type_list<ISAXContentHandler,win_mp_lib::null_type>,win_mp_lib::null_type>::CreateInstance<win_scope::no_addref_release<IXmlWriter> *>(win_scope::no_addref_release<IXmlWriter> *)
0x180077d4c  nop
0x180077d4d  mov     qword ptr [rdi], 0
0x180077d54  mov     rdx, [rax]
0x180077d57  mov     rcx, rdi
0x180077d5a  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x180077d5f  nop
0x180077d60  mov     rcx, [rsp+40h]
0x180077d65  test    rcx, rcx
0x180077d68  jz      short loc_180077D77
0x180077d6a  mov     rdx, [rcx]
0x180077d6d  mov     rax, [rdx+10h]
0x180077d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d76  nop
0x180077d77  mov     rax, rdi
0x180077d7a  mov     rcx, [rbp+480h+var_20]
0x180077d81  xor     rcx, rsp; StackCookie
0x180077d84  call    __security_check_cookie
0x180077d89  mov     rbx, [rsp+580h+arg_10]
0x180077d91  add     rsp, 570h
0x180077d98  pop     rdi
0x180077d99  pop     rsi
0x180077d9a  pop     rbp
0x180077d9b  retn
```
