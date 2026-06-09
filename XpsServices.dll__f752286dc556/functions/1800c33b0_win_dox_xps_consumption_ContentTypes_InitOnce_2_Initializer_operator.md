# _win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer::operator()

- ea: `0x1800c33b0`
- end: `0x1800c406f`
- name: `_win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer::operator()`
- size: `3263`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180088a18`

## callees

- `0x1800228a4`
- `0x1800a15bc`
- `0x1800a3c1c`
- `0x1800c12a8`
- `0x1800c33b0`
- `0x1800c4078`
- `0x1800c40b8`
- `0x1800c4964`
- `0x1800c4a0c`
- `0x180134b70`

## string_xrefs

- `0x1800c3974`: `application/vnd.ms-package.obfuscated-opentype`
- `0x1800c341d`: `application/vnd.ms-package.xps-fixeddocumentsequence+xml`
- `0x1800c3e3f`: `application/vnd.ms-package.xps-fixeddocument+xml`
- `0x1800c36c4`: `application/vnd.ms-package.xps-discard-control+xml`
- `0x1800c3d2d`: `application/vnd.ms-package.xps-storyfragments+xml`
- `0x1800c3fda`: `application/vnd.ms-package.xps-signaturedefinitions+xml`
- `0x1800c34a7`: `application/vnd.openxmlformats-package.core-properties+xml`
- `0x1800c3529`: `application/vnd.openxmlformats-package.digital-signature-xmlsignature+xml`
- `0x1800c363e`: `application/vnd.openxmlformats-package.digital-signature-certificate`
- `0x1800c3ca4`: `application/vnd.ms-package.xps-resourcedictionary+xml`
- `0x1800c3db6`: `application/vnd.ms-package.xps-documentstructure+xml`
- `0x1800c35b5`: `application/vnd.openxmlformats-package.digital-signature-origin`
- `0x1800c3f51`: `application/xml`
- `0x1800c38eb`: `application/vnd.ms-opentype`
- `0x1800c3862`: `application/vnd.ms-printing.printticket+xml`
- `0x1800c3ec8`: `application/vnd.ms-package.xps-fixedpage+xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer::operator()(
        __int64 a1,
        char *a2,
        unsigned int a3)
{
  __int64 v4; // rbx
  win_dox::xps_consumption::ContentTypes::Store *v5; // rax
  __int128 v7; // [rsp+30h] [rbp-69h] BYREF
  __int128 v8; // [rsp+40h] [rbp-59h]
  _BYTE v9[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v10[32]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v11[24]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v12[40]; // [rsp+A8h] [rbp+Fh] BYREF

  v4 = 0;
  v5 = (win_dox::xps_consumption::ContentTypes::Store *)operator new(0xAC8u, a2, a3);
  if ( v5 )
    v4 = win_dox::xps_consumption::ContentTypes::Store::Store(v5);
  *(_QWORD *)a2 = v4;
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 120, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 240, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 360, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 480, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 600, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 720, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 840, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 960, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1080, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1200, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1320, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1440, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1560, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1680, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1800, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 1920, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 2040, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 2160, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 2280, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 2400, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 2520, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v7);
  win_musl::ContentTypeFromStdString(v9, &v7);
  win_musl::ContentType::operator=(v4 + 2640, v9);
  std::string::_Tidy_deallocate(v12);
  std::vector<win_musl::ContentType::Parameter>::_Tidy(v11);
  std::string::_Tidy_deallocate(v10);
  std::string::_Tidy_deallocate(v9);
  if ( *((_QWORD *)&v8 + 1) > 7u )
    std::_Deallocate<16>(v7, 2LL * *((_QWORD *)&v8 + 1) + 2);
  return a2;
}

```

## disassembly

```asm
0x1800c33b0  mov     [rsp-8+arg_0], rbx
0x1800c33b5  mov     [rsp-8+arg_10], rsi
0x1800c33ba  push    rbp
0x1800c33bb  push    rdi
0x1800c33bc  push    r14
0x1800c33be  lea     rbp, [rsp-47h]
0x1800c33c3  sub     rsp, 0E0h
0x1800c33ca  mov     rax, cs:__security_cookie
0x1800c33d1  xor     rax, rsp
0x1800c33d4  mov     [rbp+57h+var_20], rax
0x1800c33d8  mov     rdi, rdx
0x1800c33db  mov     [rbp+57h+var_C8], rdx
0x1800c33df  xor     ebx, ebx
0x1800c33e1  mov     [rbp+57h+var_D0], ebx
0x1800c33e4  mov     ecx, 0AC8h; unsigned __int64
0x1800c33e9  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800c33ee  test    rax, rax
0x1800c33f1  jz      short loc_1800C33FE
0x1800c33f3  mov     rcx, rax; this
0x1800c33f6  call    ??0Store@ContentTypes@xps_consumption@win_dox@@QEAA@XZ; win_dox::xps_consumption::ContentTypes::Store::Store(void)
0x1800c33fb  mov     rbx, rax
0x1800c33fe  mov     [rdi], rbx
0x1800c3401  mov     [rbp+57h+var_D0], 1
0x1800c3408  xorps   xmm0, xmm0
0x1800c340b  movups  [rbp+57h+var_C0], xmm0
0x1800c340f  xorps   xmm1, xmm1
0x1800c3412  movdqu  [rbp+57h+var_B0], xmm1
0x1800c3417  mov     r8d, 38h ; '8'
0x1800c341d  lea     rdx, ?gc_FixedDocumentSequence@XpsDocument@ContentTypes@win_musl@@3QB_WB; "application/vnd.ms-package.xps-fixeddoc"...
0x1800c3424  lea     rcx, [rbp+57h+var_C0]
0x1800c3428  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c342d  nop
0x1800c342e  lea     rdx, [rbp+57h+var_C0]
0x1800c3432  lea     rcx, [rbp+57h+var_A0]
0x1800c3436  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c343b  mov     [rbp+57h+var_D0], 3
0x1800c3442  lea     rdx, [rbp+57h+var_A0]
0x1800c3446  mov     rcx, rbx
0x1800c3449  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c344e  lea     rcx, [rbp+57h+var_48]
0x1800c3452  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3457  lea     rcx, [rbp+57h+var_60]
0x1800c345b  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c3460  lea     rcx, [rbp+57h+var_80]
0x1800c3464  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3469  lea     rcx, [rbp+57h+var_A0]
0x1800c346d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3472  nop
0x1800c3473  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c3477  mov     esi, 7
0x1800c347c  cmp     rdx, rsi
0x1800c347f  jbe     short loc_1800C3492
0x1800c3481  lea     rdx, ds:2[rdx*2]
0x1800c3489  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c348d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c3492  xorps   xmm0, xmm0
0x1800c3495  movups  [rbp+57h+var_C0], xmm0
0x1800c3499  xorps   xmm1, xmm1
0x1800c349c  movdqu  [rbp+57h+var_B0], xmm1
0x1800c34a1  mov     r8d, 3Ah ; ':'
0x1800c34a7  lea     rdx, ?gc_CoreProperties@PackageWide@ContentTypes@win_musl@@3QB_WB; "application/vnd.openxmlformats-package."...
0x1800c34ae  lea     rcx, [rbp+57h+var_C0]
0x1800c34b2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c34b7  nop
0x1800c34b8  lea     rdx, [rbp+57h+var_C0]
0x1800c34bc  lea     rcx, [rbp+57h+var_A0]
0x1800c34c0  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c34c5  mov     [rbp+57h+var_D0], esi
0x1800c34c8  lea     rcx, [rbx+78h]
0x1800c34cc  lea     rdx, [rbp+57h+var_A0]
0x1800c34d0  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c34d5  lea     rcx, [rbp+57h+var_48]
0x1800c34d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c34de  lea     rcx, [rbp+57h+var_60]
0x1800c34e2  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c34e7  lea     rcx, [rbp+57h+var_80]
0x1800c34eb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c34f0  lea     rcx, [rbp+57h+var_A0]
0x1800c34f4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c34f9  nop
0x1800c34fa  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c34fe  cmp     rdx, rsi
0x1800c3501  jbe     short loc_1800C3514
0x1800c3503  lea     rdx, ds:2[rdx*2]
0x1800c350b  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c350f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c3514  xorps   xmm0, xmm0
0x1800c3517  movups  [rbp+57h+var_C0], xmm0
0x1800c351b  xorps   xmm1, xmm1
0x1800c351e  movdqu  [rbp+57h+var_B0], xmm1
0x1800c3523  mov     r8d, 49h ; 'I'
0x1800c3529  lea     rdx, ?gc_DigitalSignatureXmlSignature@PackageWide@ContentTypes@win_musl@@3QB_WB; "application/vnd.openxmlformats-package."...
0x1800c3530  lea     rcx, [rbp+57h+var_C0]
0x1800c3534  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c3539  nop
0x1800c353a  lea     rdx, [rbp+57h+var_C0]
0x1800c353e  lea     rcx, [rbp+57h+var_A0]
0x1800c3542  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c3547  mov     [rbp+57h+var_D0], 0Fh
0x1800c354e  lea     rcx, [rbx+0F0h]
0x1800c3555  lea     rdx, [rbp+57h+var_A0]
0x1800c3559  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c355e  lea     rcx, [rbp+57h+var_48]
0x1800c3562  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3567  lea     rcx, [rbp+57h+var_60]
0x1800c356b  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c3570  lea     rcx, [rbp+57h+var_80]
0x1800c3574  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3579  lea     rcx, [rbp+57h+var_A0]
0x1800c357d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3582  nop
0x1800c3583  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c3587  cmp     rdx, rsi
0x1800c358a  jbe     short loc_1800C359D
0x1800c358c  lea     rdx, ds:2[rdx*2]
0x1800c3594  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c3598  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c359d  xorps   xmm0, xmm0
0x1800c35a0  movups  [rbp+57h+var_C0], xmm0
0x1800c35a4  xorps   xmm1, xmm1
0x1800c35a7  movdqu  [rbp+57h+var_B0], xmm1
0x1800c35ac  mov     r14d, 3Fh ; '?'
0x1800c35b2  mov     r8d, r14d
0x1800c35b5  lea     rdx, ?gc_DigitalSignatureOrigin@PackageWide@ContentTypes@win_musl@@3QB_WB; "application/vnd.openxmlformats-package."...
0x1800c35bc  lea     rcx, [rbp+57h+var_C0]
0x1800c35c0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c35c5  nop
0x1800c35c6  lea     rdx, [rbp+57h+var_C0]
0x1800c35ca  lea     rcx, [rbp+57h+var_A0]
0x1800c35ce  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c35d3  mov     [rbp+57h+var_D0], 1Fh
0x1800c35da  lea     rcx, [rbx+168h]
0x1800c35e1  lea     rdx, [rbp+57h+var_A0]
0x1800c35e5  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c35ea  lea     rcx, [rbp+57h+var_48]
0x1800c35ee  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c35f3  lea     rcx, [rbp+57h+var_60]
0x1800c35f7  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c35fc  lea     rcx, [rbp+57h+var_80]
0x1800c3600  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3605  lea     rcx, [rbp+57h+var_A0]
0x1800c3609  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c360e  nop
0x1800c360f  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c3613  cmp     rdx, rsi
0x1800c3616  jbe     short loc_1800C3629
0x1800c3618  lea     rdx, ds:2[rdx*2]
0x1800c3620  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c3624  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c3629  xorps   xmm0, xmm0
0x1800c362c  movups  [rbp+57h+var_C0], xmm0
0x1800c3630  xorps   xmm1, xmm1
0x1800c3633  movdqu  [rbp+57h+var_B0], xmm1
0x1800c3638  mov     r8d, 44h ; 'D'
0x1800c363e  lea     rdx, ?gc_DigitalSignatureCertificate@PackageWide@ContentTypes@win_musl@@3QB_WB; "application/vnd.openxmlformats-package."...
0x1800c3645  lea     rcx, [rbp+57h+var_C0]
0x1800c3649  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c364e  nop
0x1800c364f  lea     rdx, [rbp+57h+var_C0]
0x1800c3653  lea     rcx, [rbp+57h+var_A0]
0x1800c3657  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c365c  mov     [rbp+57h+var_D0], r14d
0x1800c3660  lea     rcx, [rbx+1E0h]
0x1800c3667  lea     rdx, [rbp+57h+var_A0]
0x1800c366b  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c3670  lea     rcx, [rbp+57h+var_48]
0x1800c3674  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3679  lea     rcx, [rbp+57h+var_60]
0x1800c367d  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c3682  lea     rcx, [rbp+57h+var_80]
0x1800c3686  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c368b  lea     rcx, [rbp+57h+var_A0]
0x1800c368f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3694  nop
0x1800c3695  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c3699  cmp     rdx, rsi
0x1800c369c  jbe     short loc_1800C36AF
0x1800c369e  lea     rdx, ds:2[rdx*2]
0x1800c36a6  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c36aa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c36af  xorps   xmm0, xmm0
0x1800c36b2  movups  [rbp+57h+var_C0], xmm0
0x1800c36b6  xorps   xmm1, xmm1
0x1800c36b9  movdqu  [rbp+57h+var_B0], xmm1
0x1800c36be  mov     r8d, 32h ; '2'
0x1800c36c4  lea     rdx, ?gc_DiscardControl@XpsDocument@ContentTypes@win_musl@@3QB_WB; "application/vnd.ms-package.xps-discard-"...
0x1800c36cb  lea     rcx, [rbp+57h+var_C0]
0x1800c36cf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c36d4  nop
0x1800c36d5  lea     rdx, [rbp+57h+var_C0]
0x1800c36d9  lea     rcx, [rbp+57h+var_A0]
0x1800c36dd  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c36e2  mov     [rbp+57h+var_D0], 7Fh
0x1800c36e9  lea     rcx, [rbx+258h]
0x1800c36f0  lea     rdx, [rbp+57h+var_A0]
0x1800c36f4  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c36f9  lea     rcx, [rbp+57h+var_48]
0x1800c36fd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3702  lea     rcx, [rbp+57h+var_60]
0x1800c3706  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c370b  lea     rcx, [rbp+57h+var_80]
0x1800c370f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3714  lea     rcx, [rbp+57h+var_A0]
0x1800c3718  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c371d  nop
0x1800c371e  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c3722  cmp     rdx, rsi
0x1800c3725  jbe     short loc_1800C3738
0x1800c3727  lea     rdx, ds:2[rdx*2]
0x1800c372f  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c3733  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c3738  xorps   xmm0, xmm0
0x1800c373b  movups  [rbp+57h+var_C0], xmm0
0x1800c373f  xorps   xmm1, xmm1
0x1800c3742  movdqu  [rbp+57h+var_B0], xmm1
0x1800c3747  mov     r14d, 0Ah
0x1800c374d  mov     r8d, r14d
0x1800c3750  lea     rdx, ?gc_ThumbnailJpg@PackageWide@ContentTypes@win_musl@@3QB_WB; "image/jpeg"
0x1800c3757  lea     rcx, [rbp+57h+var_C0]
0x1800c375b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c3760  nop
0x1800c3761  lea     rdx, [rbp+57h+var_C0]
0x1800c3765  lea     rcx, [rbp+57h+var_A0]
0x1800c3769  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c376e  mov     [rbp+57h+var_D0], 0FFh
0x1800c3775  lea     rcx, [rbx+2D0h]
0x1800c377c  lea     rdx, [rbp+57h+var_A0]
0x1800c3780  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c3785  lea     rcx, [rbp+57h+var_48]
0x1800c3789  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c378e  lea     rcx, [rbp+57h+var_60]
0x1800c3792  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c3797  lea     rcx, [rbp+57h+var_80]
0x1800c379b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c37a0  lea     rcx, [rbp+57h+var_A0]
0x1800c37a4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c37a9  nop
0x1800c37aa  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c37ae  cmp     rdx, rsi
0x1800c37b1  jbe     short loc_1800C37C4
0x1800c37b3  lea     rdx, ds:2[rdx*2]
0x1800c37bb  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c37bf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c37c4  xorps   xmm0, xmm0
0x1800c37c7  movups  [rbp+57h+var_C0], xmm0
0x1800c37cb  xorps   xmm1, xmm1
0x1800c37ce  movdqu  [rbp+57h+var_B0], xmm1
0x1800c37d3  mov     r8d, 9
0x1800c37d9  lea     rdx, ?gc_ThumbnailPng@PackageWide@ContentTypes@win_musl@@3QB_WB; "image/png"
0x1800c37e0  lea     rcx, [rbp+57h+var_C0]
0x1800c37e4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c37e9  nop
0x1800c37ea  lea     rdx, [rbp+57h+var_C0]
0x1800c37ee  lea     rcx, [rbp+57h+var_A0]
0x1800c37f2  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c37f7  mov     [rbp+57h+var_D0], 1FFh
0x1800c37fe  lea     rcx, [rbx+348h]
0x1800c3805  lea     rdx, [rbp+57h+var_A0]
0x1800c3809  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c380e  lea     rcx, [rbp+57h+var_48]
0x1800c3812  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3817  lea     rcx, [rbp+57h+var_60]
0x1800c381b  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c3820  lea     rcx, [rbp+57h+var_80]
0x1800c3824  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3829  lea     rcx, [rbp+57h+var_A0]
0x1800c382d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c3832  nop
0x1800c3833  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x1800c3837  cmp     rdx, rsi
0x1800c383a  jbe     short loc_1800C384D
0x1800c383c  lea     rdx, ds:2[rdx*2]
0x1800c3844  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1800c3848  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c384d  xorps   xmm0, xmm0
0x1800c3850  movups  [rbp+57h+var_C0], xmm0
0x1800c3854  xorps   xmm1, xmm1
0x1800c3857  movdqu  [rbp+57h+var_B0], xmm1
0x1800c385c  mov     r8d, 2Bh ; '+'
0x1800c3862  lea     rdx, ?gc_PrintTicket@XpsDocument@ContentTypes@win_musl@@3QB_WB; "application/vnd.ms-printing.printticket"...
0x1800c3869  lea     rcx, [rbp+57h+var_C0]
0x1800c386d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800c3872  nop
0x1800c3873  lea     rdx, [rbp+57h+var_C0]
0x1800c3877  lea     rcx, [rbp+57h+var_A0]
0x1800c387b  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800c3880  mov     [rbp+57h+var_D0], 3FFh
0x1800c3887  lea     rcx, [rbx+3C0h]
0x1800c388e  lea     rdx, [rbp+57h+var_A0]
0x1800c3892  call    ??4ContentType@win_musl@@QEAAAEAU01@$$QEAU01@@Z; win_musl::ContentType::operator=(win_musl::ContentType &&)
0x1800c3897  lea     rcx, [rbp+57h+var_48]
0x1800c389b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c38a0  lea     rcx, [rbp+57h+var_60]
0x1800c38a4  call    ?_Tidy@?$vector@UParameter@ContentType@win_musl@@V?$allocator@UParameter@ContentType@win_musl@@@std@@@std@@AEAAXXZ; std::vector<win_musl::ContentType::Parameter>::_Tidy(void)
0x1800c38a9  lea     rcx, [rbp+57h+var_80]
0x1800c38ad  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c38b2  lea     rcx, [rbp+57h+var_A0]
0x1800c38b6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c38bb  nop
0x1800c38bc  mov     rdx, qword ptr [rbp+57h+var_B0+8]
  ... truncated ...
```
