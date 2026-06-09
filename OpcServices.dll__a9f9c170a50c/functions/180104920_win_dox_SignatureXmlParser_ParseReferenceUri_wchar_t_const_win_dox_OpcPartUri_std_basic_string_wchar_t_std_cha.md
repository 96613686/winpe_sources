# win_dox::SignatureXmlParser::ParseReferenceUri(wchar_t const *,win_dox::OpcPartUri &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> &)

- ea: `0x180104920`
- end: `0x180104b24`
- name: `?ParseReferenceUri@SignatureXmlParser@win_dox@@CAXPEB_WAEAVOpcPartUri@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1af0`

## callees

- `0x1800172f4`
- `0x180017dd0`
- `0x18001c900`
- `0x18001cb40`
- `0x18003b260`
- `0x1800517a0`
- `0x1800aa8bc`
- `0x1800cd38c`
- `0x180104920`
- `0x180117740`

## import_xrefs

- `msvcrt!wcsstr` at `0x1801049a3`
- `msvcrt!wcsstr` at `0x1801049a3`

## string_xrefs

- `0x180104958`: `The Uri attribute in the Reference tag does not have the correct format`
- `0x1801049f7`: `The Uri attribute in the Reference tag does not have the correct format`
- `0x180104a5e`: `The Uri attribute in the Reference tag does not have the correct format`
- `0x180104ae0`: `The Uri attribute in the Reference tag does not have the correct format`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::SignatureXmlParser::ParseReferenceUri(const wchar_t *a1, __int64 a2, __int64 a3)
{
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  void **v8; // rcx
  win_scope::counted_strong_weak_base *v9; // rdi
  __int64 v10; // rdx
  win_scope::counted_strong_weak_base *v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h]
  _BYTE v14[8]; // [rsp+58h] [rbp-A8h] BYREF
  void *Source[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+80h] [rbp-80h] BYREF

  v13 = -2;
  if ( !a1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1C5u,
      0x80510030,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v6 = wcsstr(a1, L"?ContentType=");
  v7 = v6;
  if ( !v6 || v6 == a1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1D2u,
      0x80510030,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::wstring::wstring(v14, a1, v6);
  *(_OWORD *)v12 = 0;
  v8 = Source;
  if ( Source[3] >= (void *)8 )
    v8 = (void **)Source[0];
  if ( !win_dox::IsValidPartUriInternal(v8, (__int128 *)v12) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1DCu,
      0x80510001,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v9 = v12[1];
  win_dox::OpcPartUri::operator=(a2, v12[1]);
  std::wstring::assign(a3, v7 + 13);
  if ( !*(_QWORD *)(a3 + 24) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1EAu,
      0x80510030,
      (struct win_musl::TStringEllipseBase *)L"The Uri attribute in the Reference tag does not have the correct format");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v12[0] && v9 )
    win_scope::counted_strong_weak_base::Release(v12[0]);
  LOBYTE(v10) = 1;
  return std::wstring::_Tidy(v14, v10, 0);
}

```

## disassembly

```asm
0x180104920  push    rbp
0x180104922  push    rbx
0x180104923  push    rsi
0x180104924  push    rdi
0x180104925  push    r14
0x180104927  lea     rbp, [rsp-30h]
0x18010492c  sub     rsp, 130h
0x180104933  mov     [rsp+150h+var_100], 0FFFFFFFFFFFFFFFEh
0x18010493c  mov     rax, cs:__security_cookie
0x180104943  xor     rax, rsp
0x180104946  mov     [rbp+50h+var_30], rax
0x18010494a  mov     rsi, r8
0x18010494d  mov     r14, rdx
0x180104950  mov     rdi, rcx
0x180104953  test    rcx, rcx
0x180104956  jnz     short loc_18010499C
0x180104958  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x18010495f  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104964  mov     [rsp+150h+var_128], 80510030h; unsigned int
0x18010496c  mov     [rsp+150h+var_130], 1C5h; unsigned int
0x180104974  lea     r9, word_18013A0B6
0x18010497b  lea     r8, aNoFilename; "(no filename)"
0x180104982  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104986  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010498b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104992  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104996  call    _CxxThrowException_0
0x18010499c  lea     rdx, ?gc_contentTypeQueryStringPrefix@Value@DigitalSignatures@win_musl@@3QB_WB; "?ContentType="
0x1801049a3  call    cs:__imp_wcsstr
0x1801049a9  mov     rbx, rax
0x1801049ac  test    rax, rax
0x1801049af  jz      loc_180104AE0
0x1801049b5  cmp     rax, rdi
0x1801049b8  jz      loc_180104AE0
0x1801049be  mov     r8, rax
0x1801049c1  mov     rdx, rdi
0x1801049c4  lea     rcx, [rsp+150h+var_F8]
0x1801049c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x1801049ce  nop
0x1801049cf  xorps   xmm0, xmm0
0x1801049d2  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x1801049d8  lea     rcx, [rsp+150h+Source]
0x1801049dd  cmp     [rsp+150h+var_D8], 8
0x1801049e3  cmovnb  rcx, [rsp+150h+Source]; Source
0x1801049e9  lea     rdx, [rsp+150h+var_110]
0x1801049ee  call    ?IsValidPartUriInternal@win_dox@@YA_NPEB_WPEAV?$scope@PEAVOpcPartUri@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::IsValidPartUriInternal(wchar_t const *,win_scope::scope<win_dox::OpcPartUri *,win_scope::const_policies<win_scope::shared_policies>> *)
0x1801049f3  test    al, al
0x1801049f5  jnz     short loc_180104A3B
0x1801049f7  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x1801049fe  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104a03  mov     [rsp+150h+var_128], 80510001h; unsigned int
0x180104a0b  mov     [rsp+150h+var_130], 1DCh; unsigned int
0x180104a13  lea     r9, word_18013A0B6
0x180104a1a  lea     r8, aNoFilename; "(no filename)"
0x180104a21  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104a25  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104a2a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104a31  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104a35  call    _CxxThrowException_0
0x180104a3b  mov     rdi, [rsp+150h+var_110+8]
0x180104a40  mov     rdx, rdi
0x180104a43  mov     rcx, r14
0x180104a46  call    ??4OpcPartUri@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::OpcPartUri::operator=(win_dox::OpcPartUri const &)
0x180104a4b  lea     rdx, [rbx+1Ah]
0x180104a4f  mov     rcx, rsi
0x180104a52  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x180104a57  cmp     qword ptr [rsi+18h], 0
0x180104a5c  jnz     short loc_180104AA2
0x180104a5e  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x180104a65  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104a6a  mov     [rsp+150h+var_128], 80510030h; unsigned int
0x180104a72  mov     [rsp+150h+var_130], 1EAh; unsigned int
0x180104a7a  lea     r9, word_18013A0B6
0x180104a81  lea     r8, aNoFilename; "(no filename)"
0x180104a88  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104a8c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104a91  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104a98  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104a9c  call    _CxxThrowException_0
0x180104aa2  mov     rcx, [rsp+150h+var_110]; this
0x180104aa7  test    rcx, rcx
0x180104aaa  jz      short loc_180104AB7
0x180104aac  test    rdi, rdi
0x180104aaf  jz      short loc_180104AB7
0x180104ab1  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x180104ab6  nop
0x180104ab7  xor     r8d, r8d
0x180104aba  mov     dl, 1
0x180104abc  lea     rcx, [rsp+150h+var_F8]
0x180104ac1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180104ac6  mov     rcx, [rbp+50h+var_30]
0x180104aca  xor     rcx, rsp; StackCookie
0x180104acd  call    __security_check_cookie
0x180104ad2  add     rsp, 130h
0x180104ad9  pop     r14
0x180104adb  pop     rdi
0x180104adc  pop     rsi
0x180104add  pop     rbx
0x180104ade  pop     rbp
0x180104adf  retn
0x180104ae0  lea     rax, aTheUriAttribut; "The Uri attribute in the Reference tag "...
0x180104ae7  mov     [rsp+150h+var_120], rax; struct win_musl::TStringEllipseBase *
0x180104aec  mov     [rsp+150h+var_128], 80510030h; unsigned int
0x180104af4  mov     [rsp+150h+var_130], 1D2h; unsigned int
0x180104afc  lea     r9, word_18013A0B6
0x180104b03  lea     r8, aNoFilename; "(no filename)"
0x180104b0a  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180104b0e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180104b13  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180104b1a  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180104b1e  call    _CxxThrowException_0
```
