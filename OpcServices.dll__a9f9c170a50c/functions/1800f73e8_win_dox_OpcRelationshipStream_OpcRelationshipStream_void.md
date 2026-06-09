# win_dox::OpcRelationshipStream::OpcRelationshipStream(void)

- ea: `0x1800f73e8`
- end: `0x1800f7541`
- name: `??0OpcRelationshipStream@win_dox@@QEAA@XZ`
- size: `345`
- prototype: `__int64 __fastcall(win_dox::OpcRelationshipStream *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a9490`

## callees

- `0x1800019b0`
- `0x18000d950`
- `0x180015a68`
- `0x18004a444`
- `0x1800517a0`
- `0x1800544e8`
- `0x1800a3f18`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800f73e8`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f7459`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f7459`

## string_xrefs

- `0x1800f7479`: `Call to CreateStreamOnHGlobal failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
win_dox::OpcRelationshipStream *__fastcall win_dox::OpcRelationshipStream::OpcRelationshipStream(
        win_dox::OpcRelationshipStream *this)
{
  HRESULT v2; // edi
  __int64 v3; // rax
  LPSTREAM ppstm; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v6[8]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v7[4]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v9[512]; // [rsp+118h] [rbp+10h] BYREF

  v7[1] = -2;
  v7[2] = this;
  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  ppstm = 0;
  win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
    &ppstm,
    0);
  ppstm = 0;
  v2 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v2 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to CreateStreamOnHGlobal failed with HResult 0x%X.", (unsigned int)v2);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1Bu,
      v2,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v3 = win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
         v7,
         &ppstm);
  win_dox::Stream::Stream(v6, v3);
  win_dox::Stream::operator=(this, v6);
  win_dox::Uri::~Uri((win_dox::Uri *)v6);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM, struct IStreamVtbl *))ppstm->lpVtbl->Release)(ppstm, ppstm->lpVtbl);
  return this;
}

```

## disassembly

```asm
0x1800f73e8  mov     rax, rsp
0x1800f73eb  push    rbp
0x1800f73ec  lea     rbp, [rax-428h]
0x1800f73f3  sub     rsp, 520h
0x1800f73fa  mov     [rsp+520h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800f7403  mov     [rax+10h], rbx
0x1800f7407  mov     [rax+18h], rdi
0x1800f740b  mov     rax, cs:__security_cookie
0x1800f7412  xor     rax, rsp
0x1800f7415  mov     [rbp+420h+var_10], rax
0x1800f741c  mov     rbx, rcx
0x1800f741f  mov     [rsp+520h+var_4C0], rcx
0x1800f7424  mov     qword ptr [rcx], 0
0x1800f742b  mov     byte ptr [rcx+8], 0
0x1800f742f  mov     [rsp+520h+ppstm], 0
0x1800f7438  xor     edx, edx
0x1800f743a  lea     rcx, [rsp+520h+ppstm]
0x1800f743f  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x1800f7444  mov     [rsp+520h+ppstm], 0
0x1800f744d  lea     r8, [rsp+520h+ppstm]; ppstm
0x1800f7452  mov     edx, 1; fDeleteOnRelease
0x1800f7457  xor     ecx, ecx; hGlobal
0x1800f7459  call    cs:__imp_CreateStreamOnHGlobal
0x1800f745f  mov     edi, eax
0x1800f7461  test    eax, eax
0x1800f7463  jns     short loc_1800F74CD
0x1800f7465  xor     edx, edx; Val
0x1800f7467  mov     r8d, 400h; Size
0x1800f746d  lea     rcx, [rbp+420h+var_410]; void *
0x1800f7471  call    memset_0
0x1800f7476  mov     r9d, edi
0x1800f7479  lea     r8, aCallToCreatest; "Call to CreateStreamOnHGlobal failed wi"...
0x1800f7480  mov     edx, 200h; unsigned __int64
0x1800f7485  lea     rcx, [rbp+420h+var_410]; wchar_t *
0x1800f7489  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f748e  lea     rax, [rbp+420h+var_410]
0x1800f7492  mov     [rsp+520h+var_4F0], rax; struct win_musl::TStringEllipseBase *
0x1800f7497  mov     [rsp+520h+var_4F8], edi; unsigned int
0x1800f749b  mov     [rsp+520h+var_500], 1Bh; unsigned int
0x1800f74a3  lea     r9, word_18013A0B6
0x1800f74aa  lea     r8, aNoFilename; "(no filename)"
0x1800f74b1  lea     rcx, [rsp+520h+pExceptionObject]; this
0x1800f74b6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f74bb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f74c2  lea     rcx, [rsp+520h+pExceptionObject]; pExceptionObject
0x1800f74c7  call    _CxxThrowException_0
0x1800f74cd  lea     rdx, [rsp+520h+ppstm]
0x1800f74d2  lea     rcx, [rsp+520h+var_4D0]
0x1800f74d7  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800f74dc  mov     rdx, rax
0x1800f74df  lea     rcx, [rsp+520h+var_4D8]
0x1800f74e4  call    ??$?0V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Stream@win_dox@@QEAA@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::Stream::Stream(win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>)
0x1800f74e9  nop
0x1800f74ea  lea     rdx, [rsp+520h+var_4D8]
0x1800f74ef  mov     rcx, rbx
0x1800f74f2  call    ??4Stream@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::Stream::operator=(win_dox::Stream const &)
0x1800f74f7  nop
0x1800f74f8  lea     rcx, [rsp+520h+var_4D8]; this
0x1800f74fd  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1800f7502  nop
0x1800f7503  mov     rcx, [rsp+520h+ppstm]
0x1800f7508  test    rcx, rcx
0x1800f750b  jz      short loc_1800F751A
0x1800f750d  mov     rdx, [rcx]
0x1800f7510  mov     rax, [rdx+10h]
0x1800f7514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7519  nop
0x1800f751a  mov     rax, rbx
0x1800f751d  mov     rcx, [rbp+420h+var_10]
0x1800f7524  xor     rcx, rsp; StackCookie
0x1800f7527  call    __security_check_cookie
0x1800f752c  lea     r11, [rsp+520h+var_s0]
0x1800f7534  mov     rbx, [r11+18h]
0x1800f7538  mov     rdi, [r11+20h]
0x1800f753c  mov     rsp, r11
0x1800f753f  pop     rbp
0x1800f7540  retn
```
