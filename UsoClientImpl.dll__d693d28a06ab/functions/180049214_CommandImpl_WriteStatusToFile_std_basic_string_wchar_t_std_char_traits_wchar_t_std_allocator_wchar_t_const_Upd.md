# CommandImpl::WriteStatusToFile(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,UpdateDiagnostics::update_diagnostics *,std::filesystem::path const &)

- ea: `0x180049214`
- end: `0x180049721`
- name: `?WriteStatusToFile@CommandImpl@@CAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUupdate_diagnostics@UpdateDiagnostics@@AEBVpath@filesystem@3@@Z`
- size: `1293`
- prototype: `void __fastcall(_QWORD *, __int64, std::filesystem *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180048fe4`

## callees

- `0x180009380`
- `0x18002e5c0`
- `0x18002ebe8`
- `0x18002ec24`
- `0x18002ed04`
- `0x180031e18`
- `0x180032dec`
- `0x180033b00`
- `0x180033f14`
- `0x180034a30`
- `0x180036b10`
- `0x18003a204`
- `0x1800439a4`
- `0x180049214`
- `0x1800498ec`
- `0x180049990`
- `0x18004a54c`
- `0x18004a8dc`
- `0x18004b3f0`
- `0x180056500`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049532`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049532`

## string_xrefs

- `0x1800496c8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800496e1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800496fa`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800495b9`: `C:\__w\1\s\src\orchestrator\clientImpl\lib\CommandImpl.cpp`
- `0x180049655`: `C:\__w\1\s\src\orchestrator\clientImpl\lib\CommandImpl.cpp`
- `0x18004934f`: `.json`
- `0x180049645`: `Failed to write to output file: %ws`
- `0x1800495a9`: `Unable to open output file: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=60
void __fastcall CommandImpl::WriteStatusToFile(_QWORD *a1, __int64 a2, std::filesystem *a3)
{
  std::filesystem *v3; // rbx
  std::filesystem *v6; // rcx
  const wchar_t *i; // rax
  const wchar_t *v8; // rdx
  __int64 v9; // r11
  const wchar_t *v10; // rcx
  __int64 traits_2_unsigned_short; // rax
  HSTRING v12; // r11
  HSTRING v13; // rcx
  __int64 v14; // rax
  const char *v15; // r9
  __int64 v16; // r11
  __int64 v17; // r8
  _QWORD *v18; // rax
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // r11
  __int64 v22; // r8
  HSTRING v23; // rax
  __int64 v24; // rax
  const char *v25; // r9
  __int64 v26; // r11
  __int64 v27; // r8
  HSTRING v28; // rax
  __int64 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  std::filesystem *v32; // rdx
  const char *v33; // rdx
  __int128 *v34; // rdx
  int v35; // [rsp+20h] [rbp-E0h]
  __int128 v36; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v37[34]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v39[2]; // [rsp+170h] [rbp+70h] BYREF
  HSTRING v40; // [rsp+180h] [rbp+80h]
  unsigned __int64 v41; // [rsp+188h] [rbp+88h]
  __int128 v42; // [rsp+190h] [rbp+90h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v3 = a3;
  v42 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v42) = 0;
  v6 = a3;
  if ( *((_QWORD *)a3 + 3) > 7u )
    v6 = *(std::filesystem **)a3;
  for ( i = std::filesystem::_Find_root_name_end(
              v6,
              (const wchar_t *const)v6 + *((_QWORD *)a3 + 2),
              (const wchar_t *const)a3); i != v8 && (*i == 92 || *i == 47); ++i )
    ;
  if ( i != v8 )
  {
    do
    {
      v10 = (const wchar_t *)(v9 - 2);
      if ( *(_WORD *)(v9 - 2) == 92 )
        break;
      if ( *v10 == 47 )
        break;
      v9 -= 2;
    }
    while ( i != v10 );
  }
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              v9,
                              v8,
                              58);
  if ( v12 == (HSTRING)traits_2_unsigned_short )
    goto LABEL_20;
  v13 = (HSTRING)(traits_2_unsigned_short - 2);
  if ( v12 == (HSTRING)(traits_2_unsigned_short - 2) )
    goto LABEL_20;
  if ( *(_WORD *)v13 != 46 )
  {
    while ( 1 )
    {
      v13 = (HSTRING)((char *)v13 - 2);
      if ( v12 == v13 )
        goto LABEL_20;
      if ( *(_WORD *)v13 == 46 )
        goto LABEL_21;
    }
  }
  if ( v12 == (HSTRING)(traits_2_unsigned_short - 4) && *(_WORD *)(traits_2_unsigned_short - 4) == 46 )
LABEL_20:
    v13 = (HSTRING)traits_2_unsigned_short;
LABEL_21:
  string[0] = v13;
  string[1] = (HSTRING)((traits_2_unsigned_short - (__int64)v13) >> 1);
  v36 = *(_OWORD *)string;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(string, &v36);
  std::wstring::wstring(v39, string);
  std::wstring::~wstring(string);
  v14 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L".json",
          &dword_18008D2B4,
          0);
  if ( v14 == v16 || (v17 = (v14 - (__int64)L".json") >> 1, v17 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v15);
  v18 = v39;
  if ( v41 > 7 )
    v18 = (_QWORD *)v39[0];
  string[0] = (HSTRING)L".json";
  string[1] = (HSTRING)v17;
  *(_QWORD *)&v36 = v18;
  *((_QWORD *)&v36 + 1) = v40;
  if ( (unsigned __int8)Strings::iequals(&v36, string) )
  {
    std::wstring::operator=(&v42);
  }
  else
  {
    v19 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L".html",
            &dword_18008D2F4,
            0);
    if ( v19 == v21 || (v22 = (v19 - (__int64)L".html") >> 1, v22 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v20);
    v23 = (HSTRING)v39;
    if ( v41 > 7 )
      v23 = (HSTRING)v39[0];
    *(_QWORD *)&v36 = L".html";
    *((_QWORD *)&v36 + 1) = v22;
    string[0] = v23;
    string[1] = v40;
    if ( (unsigned __int8)Strings::iequals(string, &v36) )
      goto LABEL_38;
    v24 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L".htm",
            word_18008D2E2,
            0);
    if ( v24 == v26 || (v27 = (v24 - (__int64)L".htm") >> 1, v27 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v25);
    v28 = (HSTRING)v39;
    if ( v41 > 7 )
      v28 = (HSTRING)v39[0];
    *(_QWORD *)&v36 = L".htm";
    *((_QWORD *)&v36 + 1) = v27;
    string[0] = v28;
    string[1] = v40;
    if ( (unsigned __int8)Strings::iequals(string, &v36) )
    {
LABEL_38:
      string[0] = 0;
      v29 = *(__int64 **)(a2 + 8);
      v30 = *v29;
      string[0] = 0;
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, HSTRING *))(v30 + 32))(v29, a1, string);
      if ( v31 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x18D,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
          (const char *)(unsigned int)v31,
          v35);
      std::wstring::operator=<UpdateDiagnostics::hstring_view,0>(&v42);
    }
    else
    {
      UpdateDiagnostics::update_diagnostics::FormatAsConsole(a2, string, a1);
      std::wstring::operator=<UpdateDiagnostics::hstring_view,0>(&v42);
    }
    if ( string[0] )
      WindowsDeleteString(string[0]);
  }
  memset(v37, 0, 0x108u);
  v32 = v3;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v32 = *(std::filesystem **)v3;
  std::wofstream::wofstream(v37, v32);
  *(_QWORD *)((char *)v37 + *(int *)(v37[0] + 4LL)) = &std::wofstream::`vftable';
  *(_DWORD *)((char *)&v36 + *(int *)(v37[0] + 4LL) + 12) = *(_DWORD *)(v37[0] + 4LL) - 168;
  v33 = (const char *)v3;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v33 = *(const char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x8D,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\lib\\CommandImpl.cpp",
    (const char *)(v37[17] == 0),
    "Unable to open output file: %ws",
    v33);
  v34 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v34 = (__int128 *)v42;
  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v37, v34, si128.m128i_i64[0]);
  if ( !std::wfilebuf::close(&v37[1]) )
    std::wios::setstate((char *)v37 + *(int *)(v37[0] + 4LL), 2);
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(std::filesystem **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x92,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\lib\\CommandImpl.cpp",
    (const char *)((*((_BYTE *)&v37[2] + *(int *)(v37[0] + 4LL)) & 6) != 0),
    "Failed to write to output file: %ws",
    (const char *)v3);
  std::wofstream::~wofstream<wchar_t,std::char_traits<wchar_t>>(&v37[21]);
  v37[21] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v37[21]);
  std::wstring::~wstring(v39);
  std::wstring::~wstring(&v42);
}

```

## disassembly

```asm
0x180049214  mov     [rsp-8+arg_18], rbx
0x180049219  push    rbp
0x18004921a  push    rsi
0x18004921b  push    rdi
0x18004921c  push    r14
0x18004921e  push    r15
0x180049220  lea     rbp, [rsp-0C0h]
0x180049228  sub     rsp, 1C0h
0x18004922f  mov     rax, cs:__security_cookie
0x180049236  xor     rax, rsp
0x180049239  mov     [rbp+0E0h+var_30], rax
0x180049240  mov     rbx, r8
0x180049243  mov     rsi, rdx
0x180049246  mov     rdi, rcx
0x180049249  xor     r14d, r14d
0x18004924c  xorps   xmm0, xmm0
0x18004924f  movups  [rbp+0E0h+var_50], xmm0
0x180049256  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004925e  movdqu  [rbp+0E0h+var_40], xmm1
0x180049266  mov     word ptr [rbp+0E0h+var_50], r14w
0x18004926e  mov     rcx, r8
0x180049271  cmp     qword ptr [r8+18h], 7
0x180049276  jbe     short loc_18004927B
0x180049278  mov     rcx, [r8]; this
0x18004927b  mov     rax, [r8+10h]
0x18004927f  lea     rdx, [rcx+rax*2]; wchar_t *
0x180049283  mov     r11, rdx
0x180049286  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18004928b  jmp     short loc_18004929D
0x18004928d  cmp     word ptr [rax], 5Ch ; '\'
0x180049291  jz      short loc_180049299
0x180049293  cmp     word ptr [rax], 2Fh ; '/'
0x180049297  jnz     short loc_1800492A2
0x180049299  add     rax, 2
0x18004929d  cmp     rax, rdx
0x1800492a0  jnz     short loc_18004928D
0x1800492a2  cmp     rax, rdx
0x1800492a5  jz      short loc_1800492BF
0x1800492a7  lea     rcx, [r11-2]
0x1800492ab  cmp     word ptr [rcx], 5Ch ; '\'
0x1800492af  jz      short loc_1800492BF
0x1800492b1  cmp     word ptr [rcx], 2Fh ; '/'
0x1800492b5  jz      short loc_1800492BF
0x1800492b7  mov     r11, rcx
0x1800492ba  cmp     rax, rcx
0x1800492bd  jnz     short loc_1800492A7
0x1800492bf  mov     r8d, 3Ah ; ':'
0x1800492c5  mov     rcx, r11
0x1800492c8  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800492cd  cmp     r11, rax
0x1800492d0  jz      short loc_180049301
0x1800492d2  lea     rcx, [rax-2]
0x1800492d6  cmp     r11, rcx
0x1800492d9  jz      short loc_180049301
0x1800492db  cmp     word ptr [rcx], 2Eh ; '.'
0x1800492df  jnz     short loc_1800492F8
0x1800492e1  lea     rdx, [rcx-2]
0x1800492e5  cmp     r11, rdx
0x1800492e8  jnz     short loc_180049304
0x1800492ea  cmp     word ptr [rdx], 2Eh ; '.'
0x1800492ee  jnz     short loc_180049304
0x1800492f0  jmp     short loc_180049301
0x1800492f2  cmp     word ptr [rcx], 2Eh ; '.'
0x1800492f6  jz      short loc_180049304
0x1800492f8  sub     rcx, 2
0x1800492fc  cmp     r11, rcx
0x1800492ff  jnz     short loc_1800492F2
0x180049301  mov     rcx, rax
0x180049304  mov     [rbp+0E0h+string], rcx
0x180049308  sub     rax, rcx
0x18004930b  sar     rax, 1
0x18004930e  mov     [rbp+0E0h+string+8], rax
0x180049312  movaps  xmm0, xmmword ptr [rbp+0E0h+string]
0x180049316  movdqa  [rsp+1E0h+var_1B0], xmm0
0x18004931c  lea     rdx, [rsp+1E0h+var_1B0]
0x180049321  lea     rcx, [rbp+0E0h+string]
0x180049325  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18004932a  nop
0x18004932b  lea     rdx, [rbp+0E0h+string]
0x18004932f  lea     rcx, [rbp+0E0h+var_70]
0x180049333  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180049338  nop
0x180049339  lea     rcx, [rbp+0E0h+string]; void *
0x18004933d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049342  xor     r8d, r8d
0x180049345  lea     r11, dword_18008D2B4
0x18004934c  mov     rdx, r11
0x18004934f  lea     r15, aJson_0; ".json"
0x180049356  mov     rcx, r15
0x180049359  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18004935e  mov     r8, rax
0x180049361  cmp     rax, r11
0x180049364  jz      loc_1800496DA
0x18004936a  sub     r8, r15
0x18004936d  sar     r8, 1
0x180049370  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180049374  jz      loc_1800496DA
0x18004937a  lea     rax, [rbp+0E0h+var_70]
0x18004937e  cmp     [rbp+0E0h+var_58], 7
0x180049386  cmova   rax, [rbp+0E0h+var_70]
0x18004938b  mov     [rbp+0E0h+string], r15
0x18004938f  mov     [rbp+0E0h+string+8], r8
0x180049393  mov     qword ptr [rsp+1E0h+var_1B0], rax
0x180049398  mov     rax, [rbp+0E0h+var_60]
0x18004939f  mov     qword ptr [rsp+1E0h+var_1B0+8], rax
0x1800493a4  lea     rdx, [rbp+0E0h+string]
0x1800493a8  lea     rcx, [rsp+1E0h+var_1B0]
0x1800493ad  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800493b2  test    al, al
0x1800493b4  jz      short loc_1800493CA
0x1800493b6  mov     rdx, rdi
0x1800493b9  lea     rcx, [rbp+0E0h+var_50]; void *
0x1800493c0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800493c5  jmp     loc_180049538
0x1800493ca  xor     r8d, r8d
0x1800493cd  lea     r11, dword_18008D2F4
0x1800493d4  mov     rdx, r11
0x1800493d7  lea     r15, aHtml; ".html"
0x1800493de  mov     rcx, r15
0x1800493e1  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800493e6  mov     r8, rax
0x1800493e9  cmp     rax, r11
0x1800493ec  jz      loc_1800496C1
0x1800493f2  sub     r8, r15
0x1800493f5  sar     r8, 1
0x1800493f8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800493fc  jz      loc_1800496C1
0x180049402  lea     rax, [rbp+0E0h+var_70]
0x180049406  cmp     [rbp+0E0h+var_58], 7
0x18004940e  cmova   rax, [rbp+0E0h+var_70]
0x180049413  mov     qword ptr [rsp+1E0h+var_1B0], r15
0x180049418  mov     qword ptr [rsp+1E0h+var_1B0+8], r8
0x18004941d  mov     [rbp+0E0h+string], rax
0x180049421  mov     rax, [rbp+0E0h+var_60]
0x180049428  mov     [rbp+0E0h+string+8], rax
0x18004942c  lea     rdx, [rsp+1E0h+var_1B0]
0x180049431  lea     rcx, [rbp+0E0h+string]
0x180049435  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18004943a  test    al, al
0x18004943c  jnz     loc_1800494D8
0x180049442  xor     r8d, r8d
0x180049445  lea     r11, word_18008D2E2
0x18004944c  mov     rdx, r11
0x18004944f  lea     r15, aHtm; ".htm"
0x180049456  mov     rcx, r15
0x180049459  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18004945e  mov     r8, rax
0x180049461  cmp     rax, r11
0x180049464  jz      loc_1800496F3
0x18004946a  sub     r8, r15
0x18004946d  sar     r8, 1
0x180049470  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180049474  jz      loc_1800496F3
0x18004947a  lea     rax, [rbp+0E0h+var_70]
0x18004947e  cmp     [rbp+0E0h+var_58], 7
0x180049486  cmova   rax, [rbp+0E0h+var_70]
0x18004948b  mov     qword ptr [rsp+1E0h+var_1B0], r15
0x180049490  mov     qword ptr [rsp+1E0h+var_1B0+8], r8
0x180049495  mov     [rbp+0E0h+string], rax
0x180049499  mov     rax, [rbp+0E0h+var_60]
0x1800494a0  mov     [rbp+0E0h+string+8], rax
0x1800494a4  lea     rdx, [rsp+1E0h+var_1B0]
0x1800494a9  lea     rcx, [rbp+0E0h+string]
0x1800494ad  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800494b2  test    al, al
0x1800494b4  jnz     short loc_1800494D8
0x1800494b6  mov     r8, rdi
0x1800494b9  lea     rdx, [rbp+0E0h+string]
0x1800494bd  mov     rcx, rsi
0x1800494c0  call    ?FormatAsConsole@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UpdateDiagnostics::update_diagnostics::FormatAsConsole(std::wstring const &)
0x1800494c5  nop
0x1800494c6  mov     rdx, rax
0x1800494c9  lea     rcx, [rbp+0E0h+var_50]; void *
0x1800494d0  call    ??$?4Uhstring_view@UpdateDiagnostics@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBUhstring_view@UpdateDiagnostics@@@Z; std::wstring::operator=<UpdateDiagnostics::hstring_view,0>(UpdateDiagnostics::hstring_view const &)
0x1800494d5  nop
0x1800494d6  jmp     short loc_180049529
0x1800494d8  mov     [rbp+0E0h+string], r14
0x1800494dc  mov     rcx, [rsi+8]
0x1800494e0  mov     rax, [rcx]
0x1800494e3  mov     [rbp+0E0h+string], r14
0x1800494e7  cmp     qword ptr [rdi+18h], 7
0x1800494ec  jbe     short loc_1800494F1
0x1800494ee  mov     rdi, [rdi]
0x1800494f1  lea     r8, [rbp+0E0h+string]
0x1800494f5  mov     rdx, rdi
0x1800494f8  mov     rax, [rax+20h]
0x1800494fc  call    _guard_dispatch_icall
0x180049501  mov     rcx, [rbp+0E8h]; this
0x180049508  test    eax, eax
0x18004950a  js      loc_18004970C
0x180049510  mov     rax, [rbp+0E0h+string]
0x180049514  mov     [rbp+0E0h+string], rax
0x180049518  lea     rdx, [rbp+0E0h+string]
0x18004951c  lea     rcx, [rbp+0E0h+var_50]; void *
0x180049523  call    ??$?4Uhstring_view@UpdateDiagnostics@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBUhstring_view@UpdateDiagnostics@@@Z; std::wstring::operator=<UpdateDiagnostics::hstring_view,0>(UpdateDiagnostics::hstring_view const &)
0x180049528  nop
0x180049529  mov     rcx, [rbp+0E0h+string]; string
0x18004952d  test    rcx, rcx
0x180049530  jz      short loc_180049538
0x180049532  call    cs:__imp_WindowsDeleteString
0x180049538  xor     edx, edx; Val
0x18004953a  mov     r8d, 108h; Size
0x180049540  lea     rcx, [rsp+1E0h+var_1A0]; void *
0x180049545  call    memset
0x18004954a  mov     rdx, rbx
0x18004954d  cmp     qword ptr [rbx+18h], 7
0x180049552  jbe     short loc_180049557
0x180049554  mov     rdx, [rbx]
0x180049557  lea     rcx, [rsp+1E0h+var_1A0]
0x18004955c  call    ??0?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@QEAA@PEB_WHH@Z; std::wofstream::wofstream(wchar_t const *,int,int)
0x180049561  mov     rax, [rsp+1E0h+var_1A0]
0x180049566  movsxd  rcx, dword ptr [rax+4]
0x18004956a  lea     rax, ??_7?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wofstream::`vftable'
0x180049571  mov     [rsp+rcx+1E0h+var_1A0], rax
0x180049576  mov     rax, [rsp+1E0h+var_1A0]
0x18004957b  movsxd  rcx, dword ptr [rax+4]
0x18004957f  lea     edx, [rcx-0A8h]
0x180049585  mov     dword ptr [rsp+rcx+1E0h+var_1B0+0Ch], edx
0x180049589  mov     rdx, rbx
0x18004958c  cmp     qword ptr [rbx+18h], 7
0x180049591  jbe     short loc_180049596
0x180049593  mov     rdx, [rbx]
0x180049596  cmp     [rbp+0E0h+var_118], r14
0x18004959a  setz    al
0x18004959d  mov     rcx, [rbp+0E8h]; this
0x1800495a4  mov     [rsp+1E0h+var_1B8], rdx; char *
0x1800495a9  lea     rdx, aUnableToOpenOu; "Unable to open output file: %ws"
0x1800495b0  mov     [rsp+1E0h+var_1C0], rdx; void *
0x1800495b5  movzx   r9d, al; char *
0x1800495b9  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x1800495c0  mov     edx, 8Dh; void *
0x1800495c5  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800495ca  lea     rdx, [rbp+0E0h+var_50]
0x1800495d1  cmp     qword ptr [rbp+0E0h+var_40+8], 7
0x1800495d9  cmova   rdx, qword ptr [rbp+0E0h+var_50]
0x1800495e1  mov     r8, qword ptr [rbp+0E0h+var_40]
0x1800495e8  lea     rcx, [rsp+1E0h+var_1A0]
0x1800495ed  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1800495f2  lea     rcx, [rsp+1E0h+var_198]
0x1800495f7  call    ?close@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAAPEAV12@XZ; std::wfilebuf::close(void)
0x1800495fc  test    rax, rax
0x1800495ff  jnz     short loc_18004961E
0x180049601  mov     rax, [rsp+1E0h+var_1A0]
0x180049606  movsxd  rcx, dword ptr [rax+4]
0x18004960a  lea     rax, [rsp+1E0h+var_1A0]
0x18004960f  add     rcx, rax
0x180049612  xor     r8d, r8d
0x180049615  lea     edx, [r8+2]
0x180049619  call    ?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z; std::wios::setstate(int,bool)
0x18004961e  cmp     qword ptr [rbx+18h], 7
0x180049623  jbe     short loc_180049628
0x180049625  mov     rbx, [rbx]
0x180049628  mov     rax, [rsp+1E0h+var_1A0]
0x18004962d  movsxd  rcx, dword ptr [rax+4]
0x180049631  test    [rsp+rcx+1E0h+var_190], 6
0x180049636  setnz   al
0x180049639  mov     rcx, [rbp+0E8h]; this
0x180049640  mov     [rsp+1E0h+var_1B8], rbx; char *
0x180049645  lea     rdx, aFailedToWriteT; "Failed to write to output file: %ws"
0x18004964c  mov     [rsp+1E0h+var_1C0], rdx; void *
0x180049651  movzx   r9d, al; char *
0x180049655  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18004965c  mov     edx, 92h; void *
0x180049661  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180049666  nop
0x180049667  lea     rcx, [rbp+0E0h+var_F8]
0x18004966b  call    ??1?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wofstream::~wofstream<wchar_t,std::char_traits<wchar_t>>(void)
0x180049670  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x180049677  mov     [rbp+0E0h+var_F8], rax
0x18004967b  lea     rcx, [rbp+0E0h+var_F8]; this
0x18004967f  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x180049684  nop
0x180049685  lea     rcx, [rbp+0E0h+var_70]; void *
0x180049689  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004968e  nop
0x18004968f  lea     rcx, [rbp+0E0h+var_50]; void *
0x180049696  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004969b  mov     rcx, [rbp+0E0h+var_30]
0x1800496a2  xor     rcx, rsp; StackCookie
0x1800496a5  call    __security_check_cookie
0x1800496aa  mov     rbx, [rsp+1E0h+arg_18]
0x1800496b2  add     rsp, 1C0h
0x1800496b9  pop     r15
0x1800496bb  pop     r14
0x1800496bd  pop     rdi
0x1800496be  pop     rsi
0x1800496bf  pop     rbp
0x1800496c0  retn
0x1800496c1  mov     rcx, [rbp+0E8h]; this
0x1800496c8  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800496cf  mov     edx, 0C9h; void *
0x1800496d4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800496da  mov     rcx, [rbp+0E8h]; this
0x1800496e1  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800496e8  mov     edx, 0C9h; void *
0x1800496ed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800496f3  mov     rcx, [rbp+0E8h]; this
0x1800496fa  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180049701  mov     edx, 0C9h; void *
0x180049706  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
  ... truncated ...
```
