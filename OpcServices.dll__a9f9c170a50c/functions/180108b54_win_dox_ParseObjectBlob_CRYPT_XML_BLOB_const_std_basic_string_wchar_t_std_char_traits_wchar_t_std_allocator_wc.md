# win_dox::ParseObjectBlob(_CRYPT_XML_BLOB const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,__MIDL___MIDL_itf_msopc_0001_0076_0005 *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> *,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>>>> *)

- ea: `0x180108b54`
- end: `0x180108e42`
- name: `?ParseObjectBlob@win_dox@@YAXPEBU_CRYPT_XML_BLOB@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0005@@PEAV34@PEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@@4@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x18009f9c4`

## callees

- `0x1800016b0`
- `0x18000405c`
- `0x180012fa0`
- `0x180018c00`
- `0x18002f13c`
- `0x1800517a0`
- `0x1800914f8`
- `0x18009c21c`
- `0x1800b839c`
- `0x1800babf0`
- `0x1800bf058`
- `0x1800cd38c`
- `0x1800d04d8`
- `0x1800d0694`
- `0x1800ece04`
- `0x1800ed254`
- `0x180106da4`
- `0x180107ea8`
- `0x180108b54`
- `0x180109c10`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x180108c93`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180108c93`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall win_dox::ParseObjectBlob(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4, __int64 a5)
{
  const char *v9; // rdx
  unsigned int v10; // r8d
  void *v11; // rax
  __int64 v12; // rsi
  win_scope::counted_strong_weak_base *v13; // r14
  IStream *v14; // rax
  IStream *v15; // rdi
  signed int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 *v19; // rsi
  __int64 i; // rbx
  __int64 j; // rax
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h]
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+78h] [rbp-88h] BYREF
  char v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  char v30[8]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  win_scope::counted_strong_weak_base *v34[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+D0h] [rbp-30h] BYREF

  v29 = -2;
  *a3 = 0;
  std::wstring::clear(a4);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(a5);
  v33 = 7;
  v32 = 0;
  v31 = 0;
  *(_OWORD *)v34 = 0;
  *((_QWORD *)&v27 + 1) = v30;
  v28 = 1;
  *(_QWORD *)&v27 = win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>();
  v11 = operator new(0x140u, v9, v10);
  v23 = (__int64)v11;
  if ( v11 )
    v12 = win_musl::consumption::SignaturePropertiesContentHandler::SignaturePropertiesContentHandler(v11, &v27);
  else
    v12 = 0;
  v27 = 0;
  v23 = v12;
  if ( v12 )
  {
    v13 = (win_scope::counted_strong_weak_base *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v13 )
    {
      win_scope::close_delete::close<win_musl::CallingThread>(&v23);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v13 + 1) = 0;
    *(_QWORD *)v13 = &win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v13 + 2) = v12;
    *(_QWORD *)&v27 = v13;
    win_scope::counted_strong_weak_base::AddRef(v13);
    *((_QWORD *)&v27 + 1) = v12;
  }
  else
  {
    v12 = *((_QWORD *)&v27 + 1);
    v13 = (win_scope::counted_strong_weak_base *)v27;
  }
  win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::SignaturePropertiesContentHandler *,win_scope::const_policies<win_scope::shared_policies>>>(&ppv);
  v14 = SHCreateMemStream(*(const BYTE **)(a1 + 8), *(_DWORD *)(a1 + 4));
  v15 = 0;
  if ( v14 )
    v15 = v14;
  v23 = (__int64)v15;
  *(_QWORD *)&v24 = 13;
  *((_QWORD *)&v24 + 1) = v15;
  v25 = 0;
  v16 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 152LL))(ppv, &v24);
  if ( v16 < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x2C7u,
      v16,
      (struct win_musl::TStringEllipseBase *)L"Parsing <SignatureProperties> failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::ValidateSignatureProperties(v34, a2);
  v24 = 0;
  if ( v34[0] )
  {
    win_scope::counted_strong_weak_base::AddRef(v34[0]);
    *(_QWORD *)&v24 = v17;
    *((_QWORD *)&v24 + 1) = v18;
  }
  win_dox::GetSignatureTime(&v24, a3, a4);
  v19 = *(__int64 **)(v12 + 296);
  for ( i = *v19; (__int64 *)i != v19; i = j )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert(
      a5,
      &v24,
      i + 24);
    if ( *(_BYTE *)(i + 105) )
      invalid_parameter(0, 0, 0, 0, 0);
    if ( *(_BYTE *)(*(_QWORD *)(i + 16) + 105LL) )
    {
      for ( j = *(_QWORD *)(i + 8); !*(_BYTE *)(j + 105) && i == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
        i = j;
    }
    else
    {
      j = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min();
    }
  }
  if ( v15 )
    ((void (__fastcall *)(IStream *))v15->lpVtbl->Release)(v15);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v13 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v27);
  return std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(v30);
}

```

## disassembly

```asm
0x180108b54  push    rbp
0x180108b56  push    rbx
0x180108b57  push    rsi
0x180108b58  push    rdi
0x180108b59  push    r12
0x180108b5b  push    r13
0x180108b5d  push    r14
0x180108b5f  push    r15
0x180108b61  lea     rbp, [rsp-88h]
0x180108b69  sub     rsp, 188h
0x180108b70  mov     [rbp+0C0h+var_130], 0FFFFFFFFFFFFFFFEh
0x180108b78  mov     rax, cs:__security_cookie
0x180108b7f  xor     rax, rsp
0x180108b82  mov     [rbp+0C0h+var_50], rax
0x180108b86  mov     r15, r9
0x180108b89  mov     rbx, r8
0x180108b8c  mov     r13, rdx
0x180108b8f  mov     rdi, rcx
0x180108b92  mov     r12, [rbp+0C0h+arg_20]
0x180108b99  mov     dword ptr [r8], 0
0x180108ba0  mov     rcx, r9
0x180108ba3  call    ?clear@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAXXZ; std::wstring::clear(void)
0x180108ba8  mov     rcx, r12
0x180108bab  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x180108bb0  mov     [rbp+0C0h+var_108], 7
0x180108bb8  mov     [rbp+0C0h+var_110], 0
0x180108bc0  xor     eax, eax
0x180108bc2  mov     [rbp+0C0h+var_120], ax
0x180108bc6  xorps   xmm0, xmm0
0x180108bc9  movdqu  xmmword ptr [rbp+0C0h+var_100], xmm0
0x180108bce  lea     rax, [rbp+0C0h+var_128]
0x180108bd2  mov     qword ptr [rbp+0C0h+var_148+8], rax
0x180108bd6  mov     [rbp+0C0h+var_138], 1
0x180108bda  lea     rcx, [rbp+0C0h+var_128]
0x180108bde  call    ??$Get@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@341@@Z; win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>)
0x180108be3  mov     qword ptr [rsp+1C0h+var_148], rax
0x180108be8  mov     ecx, 140h; unsigned __int64
0x180108bed  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180108bf2  mov     [rsp+1C0h+var_180], rax
0x180108bf7  test    rax, rax
0x180108bfa  jz      short loc_180108C0E
0x180108bfc  lea     rdx, [rsp+1C0h+var_148]
0x180108c01  mov     rcx, rax
0x180108c04  call    ??0SignaturePropertiesContentHandler@consumption@win_musl@@QEAA@AEBV?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@12@@Z; win_musl::consumption::SignaturePropertiesContentHandler::SignaturePropertiesContentHandler(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl> const &)
0x180108c09  mov     rsi, rax
0x180108c0c  jmp     short loc_180108C10
0x180108c0e  xor     esi, esi
0x180108c10  xorps   xmm0, xmm0
0x180108c13  movdqu  [rsp+1C0h+var_148], xmm0
0x180108c19  mov     [rsp+1C0h+var_180], rsi
0x180108c1e  test    rsi, rsi
0x180108c21  jz      short loc_180108C73
0x180108c23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180108c2a  mov     ecx, 18h; unsigned __int64
0x180108c2f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180108c34  mov     r14, rax
0x180108c37  xor     eax, eax
0x180108c39  test    r14, r14
0x180108c3c  jz      short loc_180108C63
0x180108c3e  mov     [r14+8], rax
0x180108c42  lea     rax, ??_7?$counted_strong_weak@PEAVZipConsumptionPart@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180108c49  mov     [r14], rax
0x180108c4c  mov     [r14+10h], rsi
0x180108c50  mov     qword ptr [rsp+1C0h+var_148], r14
0x180108c55  mov     rcx, r14; this
0x180108c58  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180108c5d  mov     qword ptr [rbp+0C0h+var_148+8], rsi
0x180108c61  jmp     short loc_180108C7C
0x180108c63  lea     rcx, [rsp+1C0h+var_180]
0x180108c68  call    ??$close@VCallingThread@win_musl@@@close_delete@win_scope@@SAXPEAPEAVCallingThread@win_musl@@@Z; win_scope::close_delete::close<win_musl::CallingThread>(win_musl::CallingThread * *)
0x180108c6d  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x180108c73  mov     rsi, qword ptr [rbp+0C0h+var_148+8]
0x180108c77  mov     r14, qword ptr [rsp+1C0h+var_148]
0x180108c7c  lea     rdx, [rsp+1C0h+var_148]
0x180108c81  lea     rcx, [rsp+1C0h+ppv]; ppv
0x180108c86  call    ??$CreateSaxParser@V?$scope@PEAVSignaturePropertiesContentHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@consumption@win_musl@@YA?AV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAV?$scope@PEAVSignaturePropertiesContentHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@@Z; win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::SignaturePropertiesContentHandler *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::SignaturePropertiesContentHandler *,win_scope::const_policies<win_scope::shared_policies>> &)
0x180108c8b  nop
0x180108c8c  mov     edx, [rdi+4]; cbInit
0x180108c8f  mov     rcx, [rdi+8]; pInit
0x180108c93  call    cs:__imp_SHCreateMemStream
0x180108c99  xor     edi, edi
0x180108c9b  test    rax, rax
0x180108c9e  cmovnz  rdi, rax
0x180108ca2  mov     [rsp+1C0h+var_180], rdi
0x180108ca7  xorps   xmm0, xmm0
0x180108caa  xor     edx, edx
0x180108cac  movups  [rsp+1C0h+var_170], xmm0
0x180108cb1  lea     eax, [rdx+0Dh]
0x180108cb4  mov     word ptr [rsp+1C0h+var_170], ax
0x180108cb9  mov     qword ptr [rsp+1C0h+var_170+8], rdi
0x180108cbe  mov     rcx, [rsp+1C0h+ppv]
0x180108cc3  movups  xmm0, [rsp+1C0h+var_170]
0x180108cc8  movaps  [rsp+1C0h+var_170], xmm0
0x180108ccd  mov     [rsp+1C0h+var_160], rdx
0x180108cd2  mov     rax, [rcx]
0x180108cd5  lea     rdx, [rsp+1C0h+var_170]
0x180108cda  mov     rax, [rax+98h]
0x180108ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108ce6  test    eax, eax
0x180108ce8  jns     short loc_180108D2A
0x180108cea  lea     rcx, aParsingSignatu; "Parsing <SignatureProperties> failed"
0x180108cf1  mov     [rsp+1C0h+var_190], rcx; struct win_musl::TStringEllipseBase *
0x180108cf6  mov     [rsp+1C0h+var_198], eax; unsigned int
0x180108cfa  mov     dword ptr [rsp+1C0h+Reserved], 2C7h; unsigned int
0x180108d02  lea     r9, word_18013A0B6
0x180108d09  lea     r8, aNoFilename; "(no filename)"
0x180108d10  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x180108d14  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180108d19  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180108d20  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x180108d24  call    _CxxThrowException_0
0x180108d2a  mov     rdx, r13
0x180108d2d  lea     rcx, [rbp+0C0h+var_100]
0x180108d31  call    ?ValidateSignatureProperties@win_dox@@YAXAEBV?$scope@PEAVSignatureProperties@Model@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::ValidateSignatureProperties(win_scope::scope<win_dox::Model::SignatureProperties *,win_scope::const_policies<win_scope::shared_policies>> const &,std::wstring const &)
0x180108d36  xorps   xmm0, xmm0
0x180108d39  movdqu  [rsp+1C0h+var_170], xmm0
0x180108d3f  mov     rcx, [rbp+0C0h+var_100]; this
0x180108d43  xor     r13d, r13d
0x180108d46  test    rcx, rcx
0x180108d49  jz      short loc_180108D5E
0x180108d4b  mov     r9, [rbp+0C0h+var_100+8]
0x180108d4f  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180108d54  mov     qword ptr [rsp+1C0h+var_170], rcx
0x180108d59  mov     qword ptr [rsp+1C0h+var_170+8], r9
0x180108d5e  mov     r8, r15
0x180108d61  mov     rdx, rbx
0x180108d64  lea     rcx, [rsp+1C0h+var_170]
0x180108d69  call    ?GetSignatureTime@win_dox@@YAXV?$scope@PEAVSignatureProperties@Model@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0005@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::GetSignatureTime(win_scope::scope<win_dox::Model::SignatureProperties *,win_scope::const_policies<win_scope::shared_policies>>,__MIDL___MIDL_itf_msopc_0001_0076_0005 *,std::wstring *)
0x180108d6e  mov     rsi, [rsi+128h]
0x180108d75  mov     rbx, [rsi]
0x180108d78  cmp     rbx, rsi
0x180108d7b  jz      short loc_180108DD9
0x180108d7d  lea     r8, [rbx+18h]
0x180108d81  lea     rdx, [rsp+1C0h+var_170]
0x180108d86  mov     rcx, r12
0x180108d89  call    ?insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert(std::pair<std::wstring const,std::wstring> const &)
0x180108d8e  cmp     [rbx+69h], r13b
0x180108d92  jz      short loc_180108DAA
0x180108d94  mov     [rsp+1C0h+Reserved], r13; Reserved
0x180108d99  xor     r9d, r9d; LineNo
0x180108d9c  xor     r8d, r8d; FileName
0x180108d9f  xor     edx, edx; FunctionName
0x180108da1  xor     ecx, ecx; Expression
0x180108da3  call    _invalid_parameter
0x180108da8  jmp     short loc_180108D78
0x180108daa  mov     rcx, [rbx+10h]
0x180108dae  cmp     [rcx+69h], r13b
0x180108db2  jnz     short loc_180108DBB
0x180108db4  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Node *)
0x180108db9  jmp     short loc_180108DD4
0x180108dbb  mov     rax, [rbx+8]
0x180108dbf  jmp     short loc_180108DCE
0x180108dc1  cmp     rbx, [rax+10h]
0x180108dc5  jnz     short loc_180108DD4
0x180108dc7  mov     rbx, rax
0x180108dca  mov     rax, [rax+8]
0x180108dce  cmp     [rax+69h], r13b
0x180108dd2  jz      short loc_180108DC1
0x180108dd4  mov     rbx, rax
0x180108dd7  jmp     short loc_180108D78
0x180108dd9  test    rdi, rdi
0x180108ddc  jz      short loc_180108DEE
0x180108dde  mov     rax, [rdi]
0x180108de1  mov     rcx, rdi
0x180108de4  mov     rax, [rax+10h]
0x180108de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108ded  nop
0x180108dee  mov     rcx, [rsp+1C0h+ppv]
0x180108df3  test    rcx, rcx
0x180108df6  jz      short loc_180108E09
0x180108df8  mov     rax, [rcx]
0x180108dfb  mov     rax, [rax+10h]
0x180108dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108e04  mov     [rsp+1C0h+ppv], r13
0x180108e09  test    r14, r14
0x180108e0c  jz      short loc_180108E19
0x180108e0e  lea     rcx, [rsp+1C0h+var_148]
0x180108e13  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180108e18  nop
0x180108e19  lea     rcx, [rbp+0C0h+var_128]
0x180108e1d  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@std@@QEAA@XZ; std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(void)
0x180108e22  mov     rcx, [rbp+0C0h+var_50]
0x180108e26  xor     rcx, rsp; StackCookie
0x180108e29  call    __security_check_cookie
0x180108e2e  add     rsp, 188h
0x180108e35  pop     r15
0x180108e37  pop     r14
0x180108e39  pop     r13
0x180108e3b  pop     r12
0x180108e3d  pop     rdi
0x180108e3e  pop     rsi
0x180108e3f  pop     rbx
0x180108e40  pop     rbp
0x180108e41  retn
```
