# win_musl::consumption::ContainerSender::ContentTypeContentHandler::StartElement(win_musl::sax::qualified_name,win_musl::consumption::SaxAttributes)

- ea: `0x1800390ac`
- end: `0x18003948d`
- name: `?StartElement@ContentTypeContentHandler@ContainerSender@consumption@win_musl@@QEAAXUqualified_name@sax@4@VSaxAttributes@34@@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180088eb4`

## callees

- `0x180012874`
- `0x180015af4`
- `0x18001a810`
- `0x180038bc8`
- `0x1800390ac`
- `0x18003a034`
- `0x18003b260`
- `0x1800517a0`
- `0x1800650ec`
- `0x1800654b0`
- `0x18006afbc`
- `0x18007500c`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180039314`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180039314`

## string_xrefs

- `0x18003921f`: `Invalid element in Content Types XML: element=<%{Element}>, namespace=%{ns}`
- `0x1800393bb`: `Content Types XML: <Types> has invalid attribute.`
- `0x180039401`: `Content Types XML: <Types> should be the root element.`
- `0x180039447`: `Content Types XML: <Default> and <Override> should be the direct child of root element <Types>.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall win_musl::consumption::ContainerSender::ContentTypeContentHandler::StartElement(
        _QWORD *a1,
        _QWORD *a2,
        const char *a3)
{
  const char *v6; // rdi
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rbx
  const char *v10; // rcx
  __int64 v11; // rbx
  const char *v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  const char *v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v18[2]; // [rsp+78h] [rbp-88h] BYREF
  const char *v19; // [rsp+80h] [rbp-80h]
  _BYTE v20[56]; // [rsp+88h] [rbp-78h] BYREF
  GUID v21; // [rsp+C0h] [rbp-40h]
  int v22; // [rsp+E8h] [rbp-18h]
  _BYTE v23[8]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v24[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v25[8]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v26[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v27[40]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v28[40]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v29[48]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v30[96]; // [rsp+1D0h] [rbp+D0h] BYREF

  v16[1] = (const char *)-2LL;
  v16[2] = a3;
  v16[0] = 0;
  v6 = *(const char **)a3;
  if ( *(_QWORD *)a3 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*(_QWORD *)a3);
  v16[0] = v6;
  win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(
    a1,
    a2,
    v16);
  if ( (unsigned __int8)win_musl::sax::operator==(a2, a1 + 44) )
  {
    if ( a1[6] != 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x429u,
        0x80510008,
        (struct win_musl::TStringEllipseBase *)L"Content Types XML: <Types> should be the root element.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v15 = a1[5] - a1[4];
    if ( a1[4] > a1[5] )
      v15 = a1[5];
    result = std::vector<win_musl::sax::attribute>::size(*(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v15) + 8LL) + 32LL);
    if ( result )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x42Fu,
        0x80510008,
        (struct win_musl::TStringEllipseBase *)L"Content Types XML: <Types> has invalid attribute.");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    if ( !(unsigned __int8)win_musl::sax::operator==(a2, a1 + 50)
      && !(unsigned __int8)win_musl::sax::operator==(a2, a1 + 56) )
    {
      std::wstring::wstring(v23, a2[2], a2[3]);
      std::wstring::wstring(v25, *a2, a2[1]);
      std::wstring::wstring(v27, L"Invalid element in Content Types XML: element=<%{Element}>, namespace=%{ns}");
      v9 = win_musl::Formatter::Formatter(v30, v27);
      v10 = (const char *)v24;
      if ( v24[3] >= 8u )
        v10 = (const char *)v24[0];
      v16[0] = v10;
      std::wstring::wstring(v28, L"Element");
      v11 = win_musl::Formatter::insert<wchar_t const *>(v9, v28, v16);
      v12 = (const char *)v26;
      if ( v26[3] >= 8u )
        v12 = (const char *)v26[0];
      v16[0] = v12;
      std::wstring::wstring(v29, L"ns");
      v13 = (_QWORD *)win_musl::Formatter::insert<wchar_t const *>(v11, v29, v16);
      win_musl::Formatter::gather((win_musl::Formatter *)v13);
      v14 = v13 + 8;
      if ( v13[11] >= 8u )
        v14 = (_QWORD *)*v14;
      win_musl::DebugLogHelper("(no filename)", &word_18013A0B6, 1094, 1024, -2142175224, v14);
      v16[0] = "Unexpected HRESULT returned by API";
      exception::exception((exception *)pExceptionObject, v16);
      memset_0(v20, 0, 0x68u);
      v19 = "(no filename)";
      v18[1] = 1094;
      v22 = -1;
      pExceptionObject[0] = &SplException::THResultException::`vftable';
      v18[0] = -2142175224;
      v21 = GUID_NULL;
      if ( SplException::Functions )
        v22 = SplException::Functions(v18);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( a1[6] != 2 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x436u,
        0x80510008,
        (struct win_musl::TStringEllipseBase *)L"Content Types XML: <Default> and <Override> should be the direct child of"
                                                " root element <Types>.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = a1[5] + 1LL - a1[4];
    if ( a1[4] > (unsigned __int64)(a1[5] + 1LL) )
      v7 = a1[5] + 1LL;
    result = win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(
               *(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v7) + 8LL),
               a1 + 41);
  }
  if ( *(_QWORD *)a3 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a3 + 16LL))(*(_QWORD *)a3);
    *(_QWORD *)a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800390ac  push    rbp
0x1800390ae  push    rbx
0x1800390af  push    rsi
0x1800390b0  push    rdi
0x1800390b1  push    r14
0x1800390b3  lea     rbp, [rsp-140h]
0x1800390bb  sub     rsp, 240h
0x1800390c2  mov     [rsp+260h+var_218], 0FFFFFFFFFFFFFFFEh
0x1800390cb  mov     rax, cs:__security_cookie
0x1800390d2  xor     rax, rsp
0x1800390d5  mov     [rbp+160h+var_30], rax
0x1800390dc  mov     rsi, r8
0x1800390df  mov     r14, rdx
0x1800390e2  mov     rbx, rcx
0x1800390e5  mov     [rsp+260h+var_210], r8
0x1800390ea  xor     ecx, ecx
0x1800390ec  mov     [rsp+260h+var_220], rcx
0x1800390f1  mov     rdi, [r8]
0x1800390f4  test    rdi, rdi
0x1800390f7  jnz     loc_1800391BB
0x1800390fd  mov     [rsp+260h+var_220], rdi
0x180039102  test    rcx, rcx
0x180039105  jnz     loc_1800391D4
0x18003910b  lea     r8, [rsp+260h+var_220]
0x180039110  mov     rdx, r14
0x180039113  mov     rcx, rbx
0x180039116  call    ?StartElement@?$DefaultContentHandler@V?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@@consumption@win_musl@@QEAAXAEBUqualified_name@sax@3@VSaxAttributes@23@@Z; win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes)
0x18003911b  lea     rdx, [rbx+160h]
0x180039122  mov     rcx, r14
0x180039125  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x18003912a  test    al, al
0x18003912c  jnz     loc_180039383
0x180039132  lea     rdx, [rbx+190h]
0x180039139  mov     rcx, r14
0x18003913c  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x180039141  test    al, al
0x180039143  jz      loc_1800391E5
0x180039149  cmp     qword ptr [rbx+30h], 2
0x18003914e  jnz     loc_180039447
0x180039154  mov     rax, [rbx+28h]
0x180039158  inc     rax
0x18003915b  lea     rdx, [rbx+148h]
0x180039162  mov     rcx, rax
0x180039165  sub     rcx, [rbx+20h]
0x180039169  cmp     [rbx+20h], rax
0x18003916d  cmova   rcx, rax
0x180039171  mov     rax, [rbx+18h]
0x180039175  mov     rcx, [rax+rcx*8]
0x180039179  mov     rcx, [rcx+8]
0x18003917d  call    ?Parse@?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@QEAAXPEAV?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@23@@Z; win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl> *)
0x180039182  nop
0x180039183  mov     rcx, [rsi]
0x180039186  test    rcx, rcx
0x180039189  jz      short loc_18003919E
0x18003918b  mov     rax, [rcx]
0x18003918e  mov     rax, [rax+10h]
0x180039192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039197  mov     qword ptr [rsi], 0
0x18003919e  mov     rcx, [rbp+160h+var_30]
0x1800391a5  xor     rcx, rsp; StackCookie
0x1800391a8  call    __security_check_cookie
0x1800391ad  add     rsp, 240h
0x1800391b4  pop     r14
0x1800391b6  pop     rdi
0x1800391b7  pop     rsi
0x1800391b8  pop     rbx
0x1800391b9  pop     rbp
0x1800391ba  retn
0x1800391bb  mov     rax, [rdi]
0x1800391be  mov     rcx, rdi
0x1800391c1  mov     rax, [rax+8]
0x1800391c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391ca  mov     rcx, [rsp+260h+var_220]
0x1800391cf  jmp     loc_1800390FD
0x1800391d4  mov     rax, [rcx]
0x1800391d7  mov     rax, [rax+10h]
0x1800391db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391e0  jmp     loc_18003910B
0x1800391e5  lea     rdx, [rbx+1C0h]
0x1800391ec  mov     rcx, r14
0x1800391ef  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800391f4  test    al, al
0x1800391f6  jnz     loc_180039149
0x1800391fc  mov     r8, [r14+18h]
0x180039200  mov     rdx, [r14+10h]
0x180039204  lea     rcx, [rbp+160h+var_160]
0x180039208  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x18003920d  nop
0x18003920e  mov     r8, [r14+8]
0x180039212  mov     rdx, [r14]
0x180039215  lea     rcx, [rbp+160h+var_138]
0x180039219  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x18003921e  nop
0x18003921f  lea     rdx, aInvalidElement_0; "Invalid element in Content Types XML: e"...
0x180039226  lea     rcx, [rbp+160h+var_110]
0x18003922a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18003922f  nop
0x180039230  lea     rdx, [rbp+160h+var_110]
0x180039234  lea     rcx, [rbp+160h+var_90]
0x18003923b  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180039240  mov     rbx, rax
0x180039243  lea     rcx, [rbp+160h+var_158]
0x180039247  cmp     [rbp+160h+var_140], 8
0x18003924c  cmovnb  rcx, [rbp+160h+var_158]
0x180039251  mov     [rsp+260h+var_220], rcx
0x180039256  lea     rdx, aElement; "Element"
0x18003925d  lea     rcx, [rbp+160h+var_E8]
0x180039261  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180039266  nop
0x180039267  lea     r8, [rsp+260h+var_220]
0x18003926c  lea     rdx, [rbp+160h+var_E8]
0x180039270  mov     rcx, rbx
0x180039273  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x180039278  mov     rbx, rax
0x18003927b  lea     rcx, [rbp+160h+var_130]
0x18003927f  cmp     [rbp+160h+var_118], 8
0x180039284  cmovnb  rcx, [rbp+160h+var_130]
0x180039289  mov     [rsp+260h+var_220], rcx
0x18003928e  lea     rdx, aNs; "ns"
0x180039295  lea     rcx, [rbp+160h+var_C0]
0x18003929c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800392a1  nop
0x1800392a2  lea     r8, [rsp+260h+var_220]
0x1800392a7  lea     rdx, [rbp+160h+var_C0]
0x1800392ae  mov     rcx, rbx
0x1800392b1  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x1800392b6  mov     rbx, rax
0x1800392b9  mov     rcx, rax; this
0x1800392bc  call    ?gather@Formatter@win_musl@@QEAAXXZ; win_musl::Formatter::gather(void)
0x1800392c1  lea     rax, [rbx+40h]
0x1800392c5  cmp     qword ptr [rbx+58h], 8
0x1800392ca  jb      short loc_1800392CF
0x1800392cc  mov     rax, [rax]
0x1800392cf  mov     qword ptr [rsp+260h+var_238], rax
0x1800392d4  mov     [rsp+260h+var_240], 80510008h
0x1800392dc  mov     edi, 446h
0x1800392e1  lea     r9d, [rdi-46h]
0x1800392e5  mov     r8d, edi
0x1800392e8  lea     rdx, word_18013A0B6
0x1800392ef  lea     rbx, aNoFilename; "(no filename)"
0x1800392f6  mov     rcx, rbx
0x1800392f9  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800392fe  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x180039305  mov     [rsp+260h+var_220], rax
0x18003930a  lea     rdx, [rsp+260h+var_220]
0x18003930f  lea     rcx, [rsp+260h+pExceptionObject]
0x180039314  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18003931a  xor     edx, edx; Val
0x18003931c  lea     r8d, [rdx+68h]; Size
0x180039320  lea     rcx, [rbp+160h+var_1D8]; void *
0x180039324  call    memset_0
0x180039329  mov     [rbp+160h+var_1E0], rbx
0x18003932d  mov     [rsp+260h+var_1E4], edi
0x180039331  mov     [rbp+160h+var_178], 0FFFFFFFFh
0x180039338  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x18003933f  mov     [rsp+260h+pExceptionObject], rax
0x180039344  mov     [rsp+260h+var_1E8], 80510008h
0x18003934c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180039353  movdqu  [rbp+160h+var_1A0], xmm0
0x180039358  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18003935f  test    rax, rax
0x180039362  jz      short loc_180039371
0x180039364  lea     rcx, [rsp+260h+var_1E8]
0x180039369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003936e  mov     [rbp+160h+var_178], eax
0x180039371  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180039378  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x18003937d  call    _CxxThrowException_0
0x180039383  cmp     qword ptr [rbx+30h], 1
0x180039388  jnz     short loc_180039401
0x18003938a  mov     rax, [rbx+28h]
0x18003938e  mov     rcx, rax
0x180039391  sub     rcx, [rbx+20h]
0x180039395  cmp     [rbx+20h], rax
0x180039399  cmova   rcx, rax
0x18003939d  mov     rax, [rbx+18h]
0x1800393a1  mov     rcx, [rax+rcx*8]
0x1800393a5  mov     rcx, [rcx+8]
0x1800393a9  add     rcx, 20h ; ' '
0x1800393ad  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x1800393b2  test    rax, rax
0x1800393b5  jz      loc_180039183
0x1800393bb  lea     rax, aContentTypesXm_1; "Content Types XML: <Types> has invalid "...
0x1800393c2  mov     [rsp+260h+var_230], rax; struct win_musl::TStringEllipseBase *
0x1800393c7  mov     [rsp+260h+var_238], 80510008h; unsigned int
0x1800393cf  mov     [rsp+260h+var_240], 42Fh; unsigned int
0x1800393d7  lea     r9, word_18013A0B6
0x1800393de  lea     r8, aNoFilename; "(no filename)"
0x1800393e5  lea     rcx, [rsp+260h+pExceptionObject]; this
0x1800393ea  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800393ef  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800393f6  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x1800393fb  call    _CxxThrowException_0
0x180039401  lea     rax, aContentTypesXm; "Content Types XML: <Types> should be th"...
0x180039408  mov     [rsp+260h+var_230], rax; struct win_musl::TStringEllipseBase *
0x18003940d  mov     [rsp+260h+var_238], 80510008h; unsigned int
0x180039415  mov     [rsp+260h+var_240], 429h; unsigned int
0x18003941d  lea     r9, word_18013A0B6
0x180039424  lea     r8, aNoFilename; "(no filename)"
0x18003942b  lea     rcx, [rsp+260h+pExceptionObject]; this
0x180039430  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180039435  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18003943c  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x180039441  call    _CxxThrowException_0
0x180039447  lea     rax, aContentTypesXm_0; "Content Types XML: <Default> and <Overr"...
0x18003944e  mov     [rsp+260h+var_230], rax; struct win_musl::TStringEllipseBase *
0x180039453  mov     [rsp+260h+var_238], 80510008h; unsigned int
0x18003945b  mov     [rsp+260h+var_240], 436h; unsigned int
0x180039463  lea     r9, word_18013A0B6
0x18003946a  lea     r8, aNoFilename; "(no filename)"
0x180039471  lea     rcx, [rsp+260h+pExceptionObject]; this
0x180039476  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18003947b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180039482  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x180039487  call    _CxxThrowException_0
```
