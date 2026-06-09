# win_dox::OpcRelationshipsTransform::TransformContentHandler::StartElement(win_musl::sax::qualified_name,win_musl::consumption::SaxAttributes)

- ea: `0x1800be324`
- end: `0x1800be7ae`
- name: `?StartElement@TransformContentHandler@OpcRelationshipsTransform@win_dox@@QEAAXUqualified_name@sax@win_musl@@VSaxAttributes@consumption@6@@Z`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801069c0`

## callees

- `0x18000d950`
- `0x180017dd0`
- `0x1800191b0`
- `0x18001d200`
- `0x180038670`
- `0x180038bc8`
- `0x180039700`
- `0x18003a034`
- `0x18003a70c`
- `0x1800405c0`
- `0x1800517a0`
- `0x180066c30`
- `0x1800be324`
- `0x1800c560c`
- `0x1800cd38c`
- `0x1800d078c`
- `0x1800d07fc`
- `0x18010565c`
- `0x180117740`
- `0x18012a010`

## string_xrefs

- `0x1800be40e`: `Relationships Transform XML: <RelationshipReference> or <RelationshipsGroupReference> must have exactly one non-'xmlns' attribute.`
- `0x1800be76a`: `Relationships Transform XML: Child of <Transform> element must be <RelationshipReference> or <RelationshipsGroupReference>.`
- `0x1800be399`: `Relationships Transform XML: Children of <Transform> element cannot have their own children.`
- `0x1800be657`: `Relationships Transform XML: Attribute of <RelationshipReference> or <RelationshipsGroupReference> must not be prefixed.`
- `0x1800be6c5`: `Relationships Transform XML: Incorrect attribute of <RelationshipReference> or <RelationshipsGroupReference>.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall win_dox::OpcRelationshipsTransform::TransformContentHandler::StartElement(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r13
  __int64 v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  const wchar_t *v14; // r9
  _WORD *v15; // r8
  _WORD *v16; // r9
  __int128 v17; // xmm0
  __int64 v18; // r10
  __int64 v19; // rdx
  const wchar_t *v20; // r8
  const wchar_t *v21; // r9
  _WORD *v22; // r8
  _WORD *v23; // r9
  __int128 v24; // xmm0
  __int64 v25; // r10
  const struct win_musl::sax::wchar_range *v26; // rdx
  __int64 v27; // r14
  const wchar_t *v28; // rdi
  __int64 RawUri; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int128 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h]
  _QWORD *v35; // [rsp+58h] [rbp-A8h]
  _BYTE v36[48]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[40]; // [rsp+130h] [rbp+30h] BYREF

  v34 = -2;
  v35 = a3;
  v6 = win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
         &v33,
         a3);
  win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter>>::StartElement(
    a1,
    a2,
    v6);
  result = a1[6] - 1LL;
  if ( a1[6] != 1 )
  {
    if ( a1[6] != 2 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x157u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Children of <Transform> element cannot have "
                                                "their own children.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v8 = a1[5] + 1LL - a1[4];
    if ( a1[4] > (unsigned __int64)(a1[5] + 1LL) )
      v8 = a1[5] + 1LL;
    v9 = *(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v8) + 8LL);
    if ( std::vector<win_musl::sax::attribute>::size(v9 + 32) != 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x163u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: <RelationshipReference> or <RelationshipsGro"
                                                "upReference> must have exactly one non-'xmlns' attribute.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v11 = -1;
    if ( dword_1801C5390 > *(_DWORD *)(v10 + 4) )
    {
      Init_thread_header(&dword_1801C5390);
      if ( dword_1801C5390 == -1 )
      {
        v13 = (const wchar_t *)&dword_180144B44;
        do
          v14 = v13--;
        while ( !*v13 && v13 != L"RelationshipReference" );
        v17 = *(_OWORD *)win_musl::sax::wchar_range_make<wchar_t,65>(&v33, v12, v13, v14);
        *(_QWORD *)&v33 = v18;
        if ( *v15 )
          v15 = v16;
        *((_QWORD *)&v33 + 1) = v15;
        xmmword_1801C53A0 = v17;
        xmmword_1801C53B0 = v33;
        xmmword_1801C53C0 = 0;
        Init_thread_footer(&dword_1801C5390);
      }
    }
    if ( dword_1801C53D0 > *(_DWORD *)(v10 + 4) )
    {
      Init_thread_header(&dword_1801C53D0);
      if ( dword_1801C53D0 == -1 )
      {
        v20 = L"RelationshipReference";
        do
          v21 = v20--;
        while ( !*v20 && v20 != L"RelationshipsGroupReference" );
        v24 = *(_OWORD *)win_musl::sax::wchar_range_make<wchar_t,65>(&v33, v19, v20, v21);
        *(_QWORD *)&v33 = v25;
        if ( *v22 )
          v22 = v23;
        *((_QWORD *)&v33 + 1) = v22;
        xmmword_1801C53E0 = v24;
        xmmword_1801C53F0 = v33;
        xmmword_1801C5400 = 0;
        Init_thread_footer(&dword_1801C53D0);
      }
    }
    win_musl::StdStringFromSaxRange(v36, *(_QWORD *)(v9 + 40) + 64LL);
    if ( (unsigned __int8)win_musl::sax::operator==(a2, &xmmword_1801C53A0) )
    {
      v27 = a1[34];
      v28 = L"SourceId";
    }
    else
    {
      if ( !(unsigned __int8)win_musl::sax::operator==(a2, &xmmword_1801C53E0) )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x19Cu,
          0x80510021,
          (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Child of <Transform> element must be <Rela"
                                                  "tionshipReference> or <RelationshipsGroupReference>.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v27 = a1[35];
      v28 = L"SourceType";
      win_dox::Uri::CreateUri((__int64)&v33, (__int64)v36, 0x141u);
      RawUri = win_dox::Uri::GetRawUri(&v33, v38);
      std::wstring::assign(v36, RawUri, 0, -1);
      LOBYTE(v30) = 1;
      std::wstring::_Tidy(v38, v30, 0);
      if ( (_QWORD)v33 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33 + 16LL))(v33);
    }
    if ( !win_musl::sax::wchar_range_empty(*(win_musl::sax **)(v9 + 40), v26) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1A1u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Attribute of <RelationshipReference> or <Rel"
                                                "ationshipsGroupReference> must not be prefixed.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    do
      ++v11;
    while ( v28[v11] );
    *(_QWORD *)&v33 = v28;
    *((_QWORD *)&v33 + 1) = &v28[v11];
    if ( !(unsigned __int8)win_musl::sax::operator==((win_musl::sax *)(v31 + 16)) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1A6u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Incorrect attribute of <RelationshipReferenc"
                                                "e> or <RelationshipsGroupReference>.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
      v27,
      &v33,
      v36);
    LOBYTE(v32) = 1;
    result = std::wstring::_Tidy(v36, v32, 0);
  }
  if ( *a3 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800be324  mov     rax, rsp
0x1800be327  push    rbp
0x1800be328  push    rsi
0x1800be329  push    rdi
0x1800be32a  push    r12
0x1800be32c  push    r13
0x1800be32e  push    r14
0x1800be330  push    r15
0x1800be332  lea     rbp, [rsp-60h]
0x1800be337  sub     rsp, 160h
0x1800be33e  mov     [rsp+190h+var_140], 0FFFFFFFFFFFFFFFEh
0x1800be347  mov     [rax+20h], rbx
0x1800be34b  mov     rax, cs:__security_cookie
0x1800be352  xor     rax, rsp
0x1800be355  mov     [rbp+90h+var_38], rax
0x1800be359  mov     rsi, r8
0x1800be35c  mov     r15, rdx
0x1800be35f  mov     rdi, rcx
0x1800be362  mov     [rsp+190h+var_138], r8
0x1800be367  mov     rdx, r8
0x1800be36a  lea     rcx, [rsp+190h+var_150]
0x1800be36f  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800be374  mov     r8, rax
0x1800be377  mov     rdx, r15
0x1800be37a  mov     rcx, rdi
0x1800be37d  call    ?StartElement@?$DefaultContentHandler@V?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@@consumption@win_musl@@QEAAXAEBUqualified_name@sax@3@VSaxAttributes@23@@Z; win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter>>::StartElement(win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes)
0x1800be382  mov     rax, [rdi+30h]
0x1800be386  xor     r12d, r12d
0x1800be389  sub     rax, 1
0x1800be38d  jz      loc_1800BE72C
0x1800be393  cmp     rax, 1
0x1800be397  jz      short loc_1800BE3DD
0x1800be399  lea     rax, aRelationshipsT_1; "Relationships Transform XML: Children o"...
0x1800be3a0  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be3a5  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be3ad  mov     [rsp+190h+var_170], 157h; unsigned int
0x1800be3b5  lea     r9, word_18013A0B6
0x1800be3bc  lea     r8, aNoFilename; "(no filename)"
0x1800be3c3  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be3c7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be3cc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be3d3  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be3d7  call    _CxxThrowException_0
0x1800be3dd  mov     rax, [rdi+28h]
0x1800be3e1  inc     rax
0x1800be3e4  mov     rcx, rax
0x1800be3e7  sub     rcx, [rdi+20h]
0x1800be3eb  cmp     [rdi+20h], rax
0x1800be3ef  cmova   rcx, rax
0x1800be3f3  mov     rax, [rdi+18h]
0x1800be3f7  mov     rcx, [rax+rcx*8]
0x1800be3fb  mov     r13, [rcx+8]
0x1800be3ff  lea     rcx, [r13+20h]
0x1800be403  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x1800be408  cmp     rax, 1
0x1800be40c  jz      short loc_1800BE452
0x1800be40e  lea     rax, aRelationshipsT; "Relationships Transform XML: <Relations"...
0x1800be415  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be41a  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be422  mov     [rsp+190h+var_170], 163h; unsigned int
0x1800be42a  lea     r9, word_18013A0B6
0x1800be431  lea     r8, aNoFilename; "(no filename)"
0x1800be438  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be43c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be441  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be448  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be44c  call    _CxxThrowException_0
0x1800be452  mov     ecx, cs:_tls_index
0x1800be458  mov     rax, gs:58h
0x1800be461  mov     edx, 4
0x1800be466  mov     r14, [rax+rcx*8]
0x1800be46a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800be46e  mov     eax, [r14+rdx]
0x1800be472  cmp     cs:dword_1801C5390, eax
0x1800be478  jle     loc_1800BE502
0x1800be47e  lea     rcx, dword_1801C5390
0x1800be485  call    _Init_thread_header
0x1800be48a  cmp     cs:dword_1801C5390, ebx
0x1800be490  jnz     short loc_1800BE4FD
0x1800be492  lea     r8, dword_180144B44
0x1800be499  lea     r10, ?gc_relationshipIDSelector@Element@DigitalSignatures@win_musl@@3QB_WB; "RelationshipReference"
0x1800be4a0  mov     r9, r8
0x1800be4a3  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800be4a7  cmp     [r8], r12w
0x1800be4ab  jnz     short loc_1800BE4B2
0x1800be4ad  cmp     r8, r10
0x1800be4b0  jnz     short loc_1800BE4A0
0x1800be4b2  lea     rcx, [rsp+190h+var_150]
0x1800be4b7  call    ??$wchar_range_make@_W$0EB@@sax@win_musl@@YA?AUwchar_range@01@AEAY0EB@$$CB_W@Z; win_musl::sax::wchar_range_make<wchar_t,65>(wchar_t const (&)[65])
0x1800be4bc  movups  xmm0, xmmword ptr [rax]
0x1800be4bf  mov     qword ptr [rsp+190h+var_150], r10
0x1800be4c4  cmp     [r8], r12w
0x1800be4c8  cmovnz  r8, r9
0x1800be4cc  mov     qword ptr [rsp+190h+var_150+8], r8
0x1800be4d1  movdqa  cs:xmmword_1801C53A0, xmm0
0x1800be4d9  movaps  xmm0, [rsp+190h+var_150]
0x1800be4de  movdqa  cs:xmmword_1801C53B0, xmm0
0x1800be4e6  xorps   xmm1, xmm1
0x1800be4e9  movdqa  cs:xmmword_1801C53C0, xmm1
0x1800be4f1  lea     rcx, dword_1801C5390
0x1800be4f8  call    _Init_thread_footer
0x1800be4fd  mov     edx, 4
0x1800be502  mov     eax, [r14+rdx]
0x1800be506  cmp     cs:dword_1801C53D0, eax
0x1800be50c  jle     short loc_1800BE58D
0x1800be50e  lea     rcx, dword_1801C53D0
0x1800be515  call    _Init_thread_header
0x1800be51a  cmp     cs:dword_1801C53D0, ebx
0x1800be520  jnz     short loc_1800BE58D
0x1800be522  lea     r8, ?gc_relationshipIDSelector@Element@DigitalSignatures@win_musl@@3QB_WB; "RelationshipReference"
0x1800be529  lea     r10, ?gc_relationshipTypeSelector@Element@DigitalSignatures@win_musl@@3QB_WB; "RelationshipsGroupReference"
0x1800be530  mov     r9, r8
0x1800be533  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800be537  cmp     [r8], r12w
0x1800be53b  jnz     short loc_1800BE542
0x1800be53d  cmp     r8, r10
0x1800be540  jnz     short loc_1800BE530
0x1800be542  lea     rcx, [rsp+190h+var_150]
0x1800be547  call    ??$wchar_range_make@_W$0EB@@sax@win_musl@@YA?AUwchar_range@01@AEAY0EB@$$CB_W@Z; win_musl::sax::wchar_range_make<wchar_t,65>(wchar_t const (&)[65])
0x1800be54c  movups  xmm0, xmmword ptr [rax]
0x1800be54f  mov     qword ptr [rsp+190h+var_150], r10
0x1800be554  cmp     [r8], r12w
0x1800be558  cmovnz  r8, r9
0x1800be55c  mov     qword ptr [rsp+190h+var_150+8], r8
0x1800be561  movdqa  cs:xmmword_1801C53E0, xmm0
0x1800be569  movaps  xmm0, [rsp+190h+var_150]
0x1800be56e  movdqa  cs:xmmword_1801C53F0, xmm0
0x1800be576  xorps   xmm1, xmm1
0x1800be579  movdqa  cs:xmmword_1801C5400, xmm1
0x1800be581  lea     rcx, dword_1801C53D0
0x1800be588  call    _Init_thread_footer
0x1800be58d  mov     rdx, [r13+28h]
0x1800be591  add     rdx, 40h ; '@'
0x1800be595  lea     rcx, [rsp+190h+var_130]
0x1800be59a  call    ?StdStringFromSaxRange@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBUwchar_range@sax@1@@Z; win_musl::StdStringFromSaxRange(win_musl::sax::wchar_range const &)
0x1800be59f  nop
0x1800be5a0  lea     rdx, xmmword_1801C53A0
0x1800be5a7  mov     rcx, r15
0x1800be5aa  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800be5af  test    al, al
0x1800be5b1  jz      short loc_1800BE5C6
0x1800be5b3  mov     r14, [rdi+110h]
0x1800be5ba  lea     rdi, ?gc_sourceID@Attribute@DigitalSignatures@win_musl@@3QB_WB; "SourceId"
0x1800be5c1  jmp     loc_1800BE64A
0x1800be5c6  lea     rdx, xmmword_1801C53E0
0x1800be5cd  mov     rcx, r15
0x1800be5d0  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800be5d5  test    al, al
0x1800be5d7  jz      loc_1800BE76A
0x1800be5dd  mov     r14, [rdi+118h]
0x1800be5e4  lea     rdi, ?gc_sourceType@Attribute@DigitalSignatures@win_musl@@3QB_WB; "SourceType"
0x1800be5eb  mov     r8d, 141h
0x1800be5f1  lea     rdx, [rsp+190h+var_130]
0x1800be5f6  lea     rcx, [rsp+190h+var_150]
0x1800be5fb  call    ?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z; win_dox::Uri::CreateUri(std::wstring const &,ulong)
0x1800be600  nop
0x1800be601  lea     rdx, [rbp+90h+var_60]
0x1800be605  lea     rcx, [rsp+190h+var_150]
0x1800be60a  call    ?GetRawUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetRawUri(void)
0x1800be60f  nop
0x1800be610  mov     r9, rbx
0x1800be613  xor     r8d, r8d
0x1800be616  mov     rdx, rax
0x1800be619  lea     rcx, [rsp+190h+var_130]
0x1800be61e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800be623  nop
0x1800be624  xor     r8d, r8d
0x1800be627  mov     dl, 1
0x1800be629  lea     rcx, [rbp+90h+var_60]
0x1800be62d  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800be632  nop
0x1800be633  mov     rcx, qword ptr [rsp+190h+var_150]
0x1800be638  test    rcx, rcx
0x1800be63b  jz      short loc_1800BE64A
0x1800be63d  mov     rax, [rcx]
0x1800be640  mov     rax, [rax+10h]
0x1800be644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be649  nop
0x1800be64a  mov     rcx, [r13+28h]; this
0x1800be64e  call    ?wchar_range_empty@sax@win_musl@@YA_NAEBUwchar_range@12@@Z; win_musl::sax::wchar_range_empty(win_musl::sax::wchar_range const &)
0x1800be653  test    al, al
0x1800be655  jnz     short loc_1800BE69B
0x1800be657  lea     rax, aRelationshipsT_3; "Relationships Transform XML: Attribute "...
0x1800be65e  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be663  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be66b  mov     [rsp+190h+var_170], 1A1h; unsigned int
0x1800be673  lea     r9, word_18013A0B6
0x1800be67a  lea     r8, aNoFilename; "(no filename)"
0x1800be681  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be685  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be68a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be691  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be695  call    _CxxThrowException_0
0x1800be69b  inc     rbx
0x1800be69e  cmp     [rdi+rbx*2], r12w
0x1800be6a3  jnz     short loc_1800BE69B
0x1800be6a5  mov     qword ptr [rsp+190h+var_150], rdi
0x1800be6aa  lea     rax, [rdi+rbx*2]
0x1800be6ae  mov     qword ptr [rsp+190h+var_150+8], rax
0x1800be6b3  add     rcx, 10h; this
0x1800be6b7  lea     rdx, [rsp+190h+var_150]
0x1800be6bc  call    ??8sax@win_musl@@YA_NAEBUwchar_range@01@0@Z; win_musl::sax::operator==(win_musl::sax::wchar_range const &,win_musl::sax::wchar_range const &)
0x1800be6c1  test    al, al
0x1800be6c3  jnz     short loc_1800BE709
0x1800be6c5  lea     rax, aRelationshipsT_2; "Relationships Transform XML: Incorrect "...
0x1800be6cc  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be6d1  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be6d9  mov     [rsp+190h+var_170], 1A6h; unsigned int
0x1800be6e1  lea     r9, word_18013A0B6
0x1800be6e8  lea     r8, aNoFilename; "(no filename)"
0x1800be6ef  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be6f3  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be6f8  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be6ff  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be703  call    _CxxThrowException_0
0x1800be709  lea     r8, [rsp+190h+var_130]
0x1800be70e  lea     rdx, [rsp+190h+var_150]
0x1800be713  mov     rcx, r14
0x1800be716  call    ?insert@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@_N@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x1800be71b  nop
0x1800be71c  xor     r8d, r8d
0x1800be71f  mov     dl, 1
0x1800be721  lea     rcx, [rsp+190h+var_130]
0x1800be726  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800be72b  nop
0x1800be72c  mov     rcx, [rsi]
0x1800be72f  test    rcx, rcx
0x1800be732  jz      short loc_1800BE743
0x1800be734  mov     rax, [rcx]
0x1800be737  mov     rax, [rax+10h]
0x1800be73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be740  mov     [rsi], r12
0x1800be743  mov     rcx, [rbp+90h+var_38]
0x1800be747  xor     rcx, rsp; StackCookie
0x1800be74a  call    __security_check_cookie
0x1800be74f  mov     rbx, [rsp+190h+arg_18]
0x1800be757  add     rsp, 160h
0x1800be75e  pop     r15
0x1800be760  pop     r14
0x1800be762  pop     r13
0x1800be764  pop     r12
0x1800be766  pop     rdi
0x1800be767  pop     rsi
0x1800be768  pop     rbp
0x1800be769  retn
0x1800be76a  lea     rax, aRelationshipsT_0; "Relationships Transform XML: Child of <"...
0x1800be771  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be776  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be77e  mov     [rsp+190h+var_170], 19Ch; unsigned int
0x1800be786  lea     r9, word_18013A0B6
0x1800be78d  lea     r8, aNoFilename; "(no filename)"
0x1800be794  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be798  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be79d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be7a4  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be7a8  call    _CxxThrowException_0
```
