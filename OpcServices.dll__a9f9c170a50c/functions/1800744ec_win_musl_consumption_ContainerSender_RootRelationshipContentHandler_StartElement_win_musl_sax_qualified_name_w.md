# win_musl::consumption::ContainerSender::RootRelationshipContentHandler::StartElement(win_musl::sax::qualified_name,win_musl::consumption::SaxAttributes)

- ea: `0x1800744ec`
- end: `0x18007485a`
- name: `?StartElement@RootRelationshipContentHandler@ContainerSender@consumption@win_musl@@QEAAXUqualified_name@sax@4@VSaxAttributes@34@@Z`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180075c24`

## callees

- `0x18000d950`
- `0x180012874`
- `0x18001a810`
- `0x180038bc8`
- `0x18003a034`
- `0x18003b260`
- `0x1800460f0`
- `0x1800517a0`
- `0x1800654b0`
- `0x18006afbc`
- `0x1800744ec`
- `0x18007500c`
- `0x1800cd38c`
- `0x180117740`
- `0x18012a010`

## string_xrefs

- `0x1800745da`: `Relationship XML: <Relationships> has invalid attribute.`
- `0x180074565`: `Relationship XML: <Relationships> should be the root element.`
- `0x180074710`: `Relationship XML: <Relationship> has invalid attributes or some required attributes are missing.`
- `0x18007463c`: `Relationship XML: <Relationship> should be the direct child of root element <Relationships>.`
- `0x180074778`: `Invalid element in Relationship XML: element=<%{Element}>, namespace=%{ns}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall win_musl::consumption::ContainerSender::RootRelationshipContentHandler::StartElement(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r9
  __int64 v12; // r10
  __int64 v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // rbx
  _QWORD *v16; // rcx
  win_musl::Formatter *v17; // rax
  struct win_musl::TStringEllipseBase *v18; // rax
  _QWORD v19[3]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v21[4]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v22[8]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v23[5]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v25[40]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v26[40]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v27[48]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v28[160]; // [rsp+1D8h] [rbp+D0h] BYREF

  v19[1] = -2;
  v19[2] = a3;
  v6 = win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
         v19,
         a3);
  win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(
    a1,
    a2,
    v6);
  if ( (unsigned __int8)win_musl::sax::operator==(a2, a1 + 50) )
  {
    if ( a1[6] != 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4E0u,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationships> should be the root element.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = a1[5] - a1[4];
    if ( a1[4] > a1[5] )
      v7 = a1[5];
    result = std::vector<win_musl::sax::attribute>::size(*(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v7) + 8LL) + 32LL);
    if ( result )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4E9u,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationships> has invalid attribute.");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    if ( !(unsigned __int8)win_musl::sax::operator==(a2, a1 + 44) )
    {
      std::wstring::wstring(&v20, a2[2], a2[3]);
      std::wstring::wstring(v22, *a2, a2[1]);
      std::wstring::wstring(v25, L"Invalid element in Relationship XML: element=<%{Element}>, namespace=%{ns}");
      v13 = win_musl::Formatter::Formatter(pExceptionObject, v25);
      v14 = v21;
      if ( v21[3] >= 8u )
        v14 = (_QWORD *)v21[0];
      v19[0] = v14;
      std::wstring::wstring(v26, L"Element");
      v15 = win_musl::Formatter::insert<wchar_t const *>(v13, v26, v19);
      v16 = v23;
      if ( v23[3] >= 8u )
        v16 = (_QWORD *)v23[0];
      v19[0] = v16;
      std::wstring::wstring(v27, L"ns");
      v17 = (win_musl::Formatter *)win_musl::Formatter::insert<wchar_t const *>(v15, v27, v19);
      v18 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v17);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v28,
        0x50Cu,
        0x80510009,
        v18);
      throw (SplException::THResultException *)v28;
    }
    if ( a1[6] != 2 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4F0u,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationship> should be the direct child of root eleme"
                                                "nt <Relationships>.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v9 = a1[5] + 1LL - a1[4];
    if ( a1[4] > (unsigned __int64)(a1[5] + 1LL) )
      v9 = a1[5] + 1LL;
    if ( (unsigned int)std::vector<win_musl::sax::attribute>::size(*(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v9) + 8LL) + 32LL)
       - 3 > 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4FBu,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationship> has invalid attributes or some required "
                                                "attributes are missing.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( a1[4] > v11 )
      v10 = v11;
    result = win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(
               *(_QWORD *)(*(_QWORD *)(v12 + 8 * v10) + 8LL),
               a1 + 41);
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
0x1800744ec  mov     rax, rsp
0x1800744ef  push    rbp
0x1800744f0  push    rsi
0x1800744f1  push    rdi
0x1800744f2  lea     rbp, [rax-198h]
0x1800744f9  sub     rsp, 280h
0x180074500  mov     [rsp+290h+var_248], 0FFFFFFFFFFFFFFFEh
0x180074509  mov     [rax+20h], rbx
0x18007450d  mov     rax, cs:__security_cookie
0x180074514  xor     rax, rsp
0x180074517  mov     [rbp+190h+var_20], rax
0x18007451e  mov     rdi, r8
0x180074521  mov     rsi, rdx
0x180074524  mov     rbx, rcx
0x180074527  mov     qword ptr [rsp+290h+var_240], r8
0x18007452c  mov     rdx, r8
0x18007452f  lea     rcx, [rsp+290h+var_250]
0x180074534  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x180074539  mov     r8, rax
0x18007453c  mov     rdx, rsi
0x18007453f  mov     rcx, rbx
0x180074542  call    ?StartElement@?$DefaultContentHandler@V?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@@consumption@win_musl@@QEAAXAEBUqualified_name@sax@3@VSaxAttributes@23@@Z; win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes)
0x180074547  lea     rdx, [rbx+190h]
0x18007454e  mov     rcx, rsi
0x180074551  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x180074556  test    al, al
0x180074558  jz      loc_18007461E
0x18007455e  cmp     qword ptr [rbx+30h], 1
0x180074563  jz      short loc_1800745A9
0x180074565  lea     rax, aRelationshipXm; "Relationship XML: <Relationships> shoul"...
0x18007456c  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180074571  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x180074579  mov     [rsp+290h+var_270], 4E0h; unsigned int
0x180074581  lea     r9, word_18013A0B6
0x180074588  lea     r8, aNoFilename; "(no filename)"
0x18007458f  lea     rcx, [rbp+190h+pExceptionObject]; this
0x180074593  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180074598  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007459f  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x1800745a3  call    _CxxThrowException_0
0x1800745a9  mov     rax, [rbx+28h]
0x1800745ad  mov     rcx, rax
0x1800745b0  sub     rcx, [rbx+20h]
0x1800745b4  cmp     [rbx+20h], rax
0x1800745b8  cmova   rcx, rax
0x1800745bc  mov     rax, [rbx+18h]
0x1800745c0  mov     rcx, [rax+rcx*8]
0x1800745c4  mov     rcx, [rcx+8]
0x1800745c8  add     rcx, 20h ; ' '
0x1800745cc  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x1800745d1  test    rax, rax
0x1800745d4  jz      loc_1800746D3
0x1800745da  lea     rax, aRelationshipXm_0; "Relationship XML: <Relationships> has i"...
0x1800745e1  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800745e6  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x1800745ee  mov     [rsp+290h+var_270], 4E9h; unsigned int
0x1800745f6  lea     r9, word_18013A0B6
0x1800745fd  lea     r8, aNoFilename; "(no filename)"
0x180074604  lea     rcx, [rbp+190h+pExceptionObject]; this
0x180074608  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18007460d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180074614  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x180074618  call    _CxxThrowException_0
0x18007461e  lea     rdx, [rbx+160h]
0x180074625  mov     rcx, rsi
0x180074628  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x18007462d  test    al, al
0x18007462f  jz      loc_180074754
0x180074635  cmp     qword ptr [rbx+30h], 2
0x18007463a  jz      short loc_180074680
0x18007463c  lea     rax, aRelationshipXm_2; "Relationship XML: <Relationship> should"...
0x180074643  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180074648  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x180074650  mov     [rsp+290h+var_270], 4F0h; unsigned int
0x180074658  lea     r9, word_18013A0B6
0x18007465f  lea     r8, aNoFilename; "(no filename)"
0x180074666  lea     rcx, [rbp+190h+pExceptionObject]; this
0x18007466a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18007466f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180074676  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x18007467a  call    _CxxThrowException_0
0x180074680  mov     r9, [rbx+28h]
0x180074684  inc     r9
0x180074687  mov     r8, r9
0x18007468a  sub     r8, [rbx+20h]
0x18007468e  mov     r10, [rbx+18h]
0x180074692  mov     rax, r8
0x180074695  cmp     [rbx+20h], r9
0x180074699  cmova   rax, r9
0x18007469d  mov     rax, [r10+rax*8]
0x1800746a1  mov     rcx, [rax+8]
0x1800746a5  add     rcx, 20h ; ' '
0x1800746a9  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x1800746ae  sub     eax, 3
0x1800746b1  cmp     eax, 1
0x1800746b4  ja      short loc_180074710
0x1800746b6  lea     rdx, [rbx+148h]
0x1800746bd  cmp     [rbx+20h], r9
0x1800746c1  cmova   r8, r9
0x1800746c5  mov     rcx, [r10+r8*8]
0x1800746c9  mov     rcx, [rcx+8]
0x1800746cd  call    ?Parse@?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@QEAAXPEAV?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@23@@Z; win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl> *)
0x1800746d2  nop
0x1800746d3  mov     rcx, [rdi]
0x1800746d6  test    rcx, rcx
0x1800746d9  jz      short loc_1800746EE
0x1800746db  mov     rax, [rcx]
0x1800746de  mov     rax, [rax+10h]
0x1800746e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800746e7  mov     qword ptr [rdi], 0
0x1800746ee  mov     rcx, [rbp+190h+var_20]
0x1800746f5  xor     rcx, rsp; StackCookie
0x1800746f8  call    __security_check_cookie
0x1800746fd  mov     rbx, [rsp+290h+arg_18]
0x180074705  add     rsp, 280h
0x18007470c  pop     rdi
0x18007470d  pop     rsi
0x18007470e  pop     rbp
0x18007470f  retn
0x180074710  lea     rax, aRelationshipXm_1; "Relationship XML: <Relationship> has in"...
0x180074717  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18007471c  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x180074724  mov     [rsp+290h+var_270], 4FBh; unsigned int
0x18007472c  lea     r9, word_18013A0B6
0x180074733  lea     r8, aNoFilename; "(no filename)"
0x18007473a  lea     rcx, [rbp+190h+pExceptionObject]; this
0x18007473e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180074743  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007474a  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x18007474e  call    _CxxThrowException_0
0x180074754  mov     r8, [rsi+18h]
0x180074758  mov     rdx, [rsi+10h]
0x18007475c  lea     rcx, [rsp+290h+var_238]
0x180074761  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x180074766  nop
0x180074767  mov     r8, [rsi+8]
0x18007476b  mov     rdx, [rsi]
0x18007476e  lea     rcx, [rbp+190h+var_210]
0x180074772  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x180074777  nop
0x180074778  lea     rdx, aInvalidElement; "Invalid element in Relationship XML: el"...
0x18007477f  lea     rcx, [rbp+190h+var_140]
0x180074783  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180074788  nop
0x180074789  lea     rdx, [rbp+190h+var_140]
0x18007478d  lea     rcx, [rbp+190h+pExceptionObject]
0x180074791  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180074796  mov     rbx, rax
0x180074799  lea     rcx, [rsp+60h]
0x18007479e  cmp     qword ptr [rsp+78h], 8
0x1800747a4  cmovnb  rcx, [rsp+60h]
0x1800747aa  mov     [rsp+290h+var_250], rcx
0x1800747af  lea     rdx, aElement; "Element"
0x1800747b6  lea     rcx, [rbp+190h+var_118]
0x1800747ba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800747bf  nop
0x1800747c0  lea     r8, [rsp+290h+var_250]
0x1800747c5  lea     rdx, [rbp+190h+var_118]
0x1800747c9  mov     rcx, rbx
0x1800747cc  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x1800747d1  mov     rbx, rax
0x1800747d4  lea     rcx, [rbp+190h+var_208]
0x1800747d8  cmp     [rbp+190h+var_1F0], 8
0x1800747dd  cmovnb  rcx, [rbp+190h+var_208]
0x1800747e2  mov     [rsp+290h+var_250], rcx
0x1800747e7  lea     rdx, aNs; "ns"
0x1800747ee  lea     rcx, [rbp+190h+var_F0]
0x1800747f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800747fa  nop
0x1800747fb  lea     r8, [rsp+290h+var_250]
0x180074800  lea     rdx, [rbp+190h+var_F0]
0x180074807  mov     rcx, rbx
0x18007480a  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x18007480f  mov     rcx, rax; this
0x180074812  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180074817  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18007481c  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x180074824  mov     [rsp+290h+var_270], 50Ch; unsigned int
0x18007482c  lea     r9, word_18013A0B6
0x180074833  lea     r8, aNoFilename; "(no filename)"
0x18007483a  lea     rcx, [rbp+190h+var_C0]; this
0x180074841  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180074846  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007484d  lea     rcx, [rbp+190h+var_C0]; pExceptionObject
0x180074854  call    _CxxThrowException_0
```
