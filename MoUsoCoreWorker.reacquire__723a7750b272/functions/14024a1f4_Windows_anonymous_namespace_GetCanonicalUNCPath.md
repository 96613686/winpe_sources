# Windows::_anonymous_namespace_::GetCanonicalUNCPath

- ea: `0x14024a1f4`
- end: `0x14024a6fb`
- name: `Windows::_anonymous_namespace_::GetCanonicalUNCPath`
- size: `1287`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140187c64`
- `0x14024a980`
- `0x14024a9dc`
- `0x14024af9c`
- `0x14024be7c`
- `0x14024c4b0`
- `0x14024c7d0`

## callees

- `0x140040184`
- `0x140040964`
- `0x140043284`
- `0x140044b18`
- `0x140045404`
- `0x14004c990`
- `0x140053618`
- `0x140057a20`
- `0x140072304`
- `0x14024a1f4`
- `0x14024d7a4`
- `0x140379070`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a44d`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a4ff`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a533`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a600`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a44d`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a4ff`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a533`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x14024a600`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14024a3c9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14024a401`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14024a3c9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14024a401`

## string_xrefs

- `0x14024a67a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024a690`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024a6d3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024a6e9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024a6a2`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024a6ba`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::_anonymous_namespace_::GetCanonicalUNCPath(__int64 a1, __int64 a2)
{
  __int64 traits_2_unsigned_short; // rax
  __int64 v4; // r8
  const char *v5; // r9
  __int64 v6; // r11
  size_t v7; // r14
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // r11
  size_t v13; // rsi
  __int64 v14; // rax
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r11
  __int64 v18; // rax
  const char *v19; // r9
  __int64 v20; // r11
  size_t v21; // r12
  __int64 v22; // rax
  const WCHAR *v23; // r13
  unsigned __int64 v24; // rdx
  const WCHAR *v25; // rax
  const WCHAR *v26; // rdx
  DWORD FullPathNameW; // eax
  const wchar_t *v28; // r9
  DWORD v29; // eax
  LPWSTR v30; // r14
  __int64 v31; // rax
  __int128 v32; // xmm7
  __m128i v33; // xmm6
  _QWORD *v34; // rcx
  WCHAR *v35; // r14
  __int64 v36; // rax
  __int128 v37; // xmm7
  __m128i v38; // xmm6
  const wchar_t *v39; // rcx
  const char *v40; // r9
  __int16 v42; // [rsp+28h] [rbp-B9h] BYREF
  char v43; // [rsp+2Ah] [rbp-B7h] BYREF
  _QWORD Src_8[5]; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v45; // [rsp+60h] [rbp-81h]
  __int128 v46; // [rsp+68h] [rbp-79h] BYREF
  __m128i v47; // [rsp+78h] [rbp-69h]
  _OWORD v48[2]; // [rsp+88h] [rbp-59h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-29h]
  wchar_t *String1[2]; // [rsp+C0h] [rbp-21h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]

  v45 = a2;
  Src_8[0] = a1;
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"\\\\",
                              &word_14047111E,
                              0);
  if ( traits_2_unsigned_short == v6 || (v7 = (traits_2_unsigned_short - (__int64)L"\\\\") >> 1, v8 = -1, v7 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v5);
  v9 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
         L"\\\\?\\",
         word_140416A82,
         v4);
  if ( v9 == v12 || (v13 = (v9 - (__int64)L"\\\\?\\") >> 1, v13 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v11);
  v14 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L"\\\\?\\UNC\\",
          word_140416ABA,
          v10);
  if ( v14 == v17 || (v14 - (__int64)L"\\\\?\\UNC\\") >> 1 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v16);
  v18 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L"\\\\.\\",
          word_1404710A2,
          v15);
  if ( v18 == v20 || (v21 = (v18 - (__int64)L"\\\\.\\") >> 1, v21 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v19);
  *(_OWORD *)lpBuffer = 0;
  v50 = 0;
  v42 = 260;
  Src_8[0] = &v42;
  Src_8[1] = &v43;
  std::vector<wchar_t>::vector<wchar_t>(lpBuffer, Src_8);
  v22 = *(_QWORD *)(v45 + 8);
  if ( !v22 )
    goto LABEL_13;
  v23 = *(const WCHAR **)v45;
  v24 = *(_QWORD *)v45 + 2 * v22;
  v25 = *(const WCHAR **)v45;
  if ( *(_QWORD *)v45 >= v24 )
    goto LABEL_13;
  while ( *v25 == 32 )
  {
    if ( (unsigned __int64)++v25 >= v24 )
      goto LABEL_13;
  }
  if ( v25 - v23 == -1 )
  {
LABEL_13:
    v26 = *(const WCHAR **)v45;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    do
      ++v8;
    while ( v26[v8] );
    std::wstring::_Construct<1,wchar_t const *>(a1, v26);
    goto LABEL_36;
  }
  FullPathNameW = GetFullPathNameW(
                    *(LPCWSTR *)v45,
                    (signed __int64)(v50 - (unsigned __int64)lpBuffer[0]) >> 1,
                    lpBuffer[0],
                    0);
  v28 = lpBuffer[0];
  if ( (signed __int64)(v50 - (unsigned __int64)lpBuffer[0]) >> 1 < (unsigned __int64)FullPathNameW )
  {
    std::vector<wchar_t>::resize(lpBuffer);
    v29 = GetFullPathNameW(v23, (signed __int64)(v50 - (unsigned __int64)lpBuffer[0]) >> 1, lpBuffer[0], 0);
    v28 = lpBuffer[0];
    if ( (signed __int64)(v50 - (unsigned __int64)lpBuffer[0]) >> 1 <= (unsigned __int64)v29 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x30,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
        (const char *)lpBuffer[0]);
  }
  *(_OWORD *)String1 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String1[0]) = 0;
  if ( wcsncmp(v28, L"\\\\", v7) )
  {
    v30 = lpBuffer[0];
    memset(Src_8, 0, 32);
    std::wstring::_Construct<1,wchar_t const *>(Src_8, L"\\\\?\\");
    do
      ++v8;
    while ( v30[v8] );
    v31 = std::wstring::append(Src_8);
    v46 = *(_OWORD *)v31;
    v32 = v46;
    v33 = *(__m128i *)(v31 + 16);
    *(_WORD *)v31 = 0;
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    std::wstring::~wstring(String1);
    *(_OWORD *)String1 = v32;
    si128 = v33;
    v47 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v46) = 0;
    std::wstring::~wstring(&v46);
    v34 = Src_8;
LABEL_31:
    std::wstring::~wstring(v34);
    goto LABEL_32;
  }
  if ( !wcsncmp(lpBuffer[0], L"\\\\.\\", v21) )
  {
    if ( (unsigned __int64)(lpBuffer[1] - lpBuffer[0]) <= 2 )
      gsl::details::terminate((gsl::details *)lpBuffer[0]);
    lpBuffer[0][2] = 63;
  }
  else if ( wcsncmp(lpBuffer[0], L"\\\\?\\", v13) )
  {
    v35 = &lpBuffer[0][v7];
    memset(v48, 0, sizeof(v48));
    std::wstring::_Construct<1,wchar_t const *>(v48, L"\\\\?\\UNC\\");
    do
      ++v8;
    while ( v35[v8] );
    v36 = std::wstring::append(v48);
    v46 = *(_OWORD *)v36;
    v37 = v46;
    v38 = *(__m128i *)(v36 + 16);
    *(_WORD *)v36 = 0;
    *(_QWORD *)(v36 + 16) = 0;
    *(_QWORD *)(v36 + 24) = 7;
    std::wstring::~wstring(String1);
    *(_OWORD *)String1 = v37;
    si128 = v38;
    v47 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v46) = 0;
    std::wstring::~wstring(&v46);
    v34 = v48;
    goto LABEL_31;
  }
  std::wstring::operator=(String1, lpBuffer[0]);
LABEL_32:
  v39 = (const wchar_t *)String1;
  if ( si128.m128i_i64[1] > 7uLL )
    v39 = String1[0];
  if ( wcsncmp(v39, L"\\\\?\\", v13) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      v40);
  *(_OWORD *)a1 = *(_OWORD *)String1;
  *(__m128i *)(a1 + 16) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String1[0]) = 0;
  std::wstring::~wstring(String1);
LABEL_36:
  std::vector<wchar_t>::_Tidy(lpBuffer);
  return a1;
}

```

## disassembly

```asm
0x14024a1f4  mov     rax, rsp
0x14024a1f7  mov     [rax+18h], rbx
0x14024a1fb  mov     [rax+8], rcx
0x14024a1ff  push    rbp
0x14024a200  push    rsi
0x14024a201  push    rdi
0x14024a202  push    r12
0x14024a204  push    r13
0x14024a206  push    r14
0x14024a208  push    r15
0x14024a20a  lea     rbp, [rax-5Fh]
0x14024a20e  sub     rsp, 100h
0x14024a215  movaps  xmmword ptr [rax-48h], xmm6
0x14024a219  movaps  xmmword ptr [rax-58h], xmm7
0x14024a21d  mov     rax, cs:__security_cookie
0x14024a224  xor     rax, rsp
0x14024a227  mov     [rbp+57h+var_58], rax
0x14024a22b  mov     [rsp+130h+var_D8], rdx
0x14024a230  mov     rdi, rcx
0x14024a233  mov     qword ptr [rsp+130h+Src+8], rcx
0x14024a238  xor     r8d, r8d
0x14024a23b  lea     r11, word_14047111E
0x14024a242  mov     rdx, r11
0x14024a245  lea     rbx, asc_140471118; "\\\\"
0x14024a24c  mov     rcx, rbx
0x14024a24f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024a254  mov     r14, rax
0x14024a257  cmp     rax, r11
0x14024a25a  jz      loc_14024A68C
0x14024a260  sub     r14, rbx
0x14024a263  sar     r14, 1
0x14024a266  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14024a26a  cmp     r14, rbx
0x14024a26d  jz      loc_14024A68C
0x14024a273  lea     r11, word_140416A82
0x14024a27a  mov     rdx, r11
0x14024a27d  lea     r15, asc_140416A78; "\\\\?\\"
0x14024a284  mov     rcx, r15
0x14024a287  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024a28c  mov     rsi, rax
0x14024a28f  cmp     rax, r11
0x14024a292  jz      loc_14024A676
0x14024a298  sub     rsi, r15
0x14024a29b  sar     rsi, 1
0x14024a29e  cmp     rsi, rbx
0x14024a2a1  jz      loc_14024A676
0x14024a2a7  lea     r11, word_140416ABA
0x14024a2ae  mov     rdx, r11
0x14024a2b1  lea     r12, aUnc; "\\\\?\\UNC\\"
0x14024a2b8  mov     rcx, r12
0x14024a2bb  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024a2c0  mov     r15, rax
0x14024a2c3  cmp     rax, r11
0x14024a2c6  jz      loc_14024A6E5
0x14024a2cc  sub     r15, r12
0x14024a2cf  sar     r15, 1
0x14024a2d2  cmp     r15, rbx
0x14024a2d5  jz      loc_14024A6E5
0x14024a2db  lea     r11, word_1404710A2
0x14024a2e2  mov     rdx, r11
0x14024a2e5  lea     r13, asc_140471098; "\\\\.\\"
0x14024a2ec  mov     rcx, r13
0x14024a2ef  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024a2f4  mov     r12, rax
0x14024a2f7  cmp     rax, r11
0x14024a2fa  jz      loc_14024A6CF
0x14024a300  sub     r12, r13
0x14024a303  sar     r12, 1
0x14024a306  cmp     r12, rbx
0x14024a309  jz      loc_14024A6CF
0x14024a30f  xorps   xmm0, xmm0
0x14024a312  xor     eax, eax
0x14024a314  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x14024a318  mov     [rbp+57h+var_80], rax
0x14024a31c  mov     eax, 104h
0x14024a321  mov     [rsp+130h+var_110], ax
0x14024a326  lea     rax, [rsp+130h+var_110]
0x14024a32b  mov     qword ptr [rsp+130h+Src+8], rax
0x14024a330  lea     rax, [rsp+130h+var_10E]
0x14024a335  mov     qword ptr [rsp+130h+var_F8], rax
0x14024a33a  lea     rdx, [rsp+130h+Src+8]
0x14024a33f  lea     rcx, [rbp+57h+lpBuffer]
0x14024a343  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@V?$initializer_list@_W@1@AEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(std::initializer_list<wchar_t>,std::allocator<wchar_t> const &)
0x14024a348  nop
0x14024a349  mov     rcx, [rsp+130h+var_D8]
0x14024a34e  mov     rax, [rcx+8]
0x14024a352  xor     r8d, r8d
0x14024a355  test    rax, rax
0x14024a358  jz      short loc_14024A37F
0x14024a35a  mov     r13, [rcx]
0x14024a35d  lea     rdx, ds:0[rax*2]
0x14024a365  add     rdx, r13
0x14024a368  mov     rax, r13
0x14024a36b  cmp     r13, rdx
0x14024a36e  jnb     short loc_14024A37F
0x14024a370  cmp     word ptr [rax], 20h ; ' '
0x14024a374  jnz     short loc_14024A3AA
0x14024a376  add     rax, 2
0x14024a37a  cmp     rax, rdx
0x14024a37d  jb      short loc_14024A370
0x14024a37f  mov     rdx, [rcx]
0x14024a382  xorps   xmm0, xmm0
0x14024a385  movups  xmmword ptr [rdi], xmm0
0x14024a388  mov     [rdi+10h], r8
0x14024a38c  mov     [rdi+18h], r8
0x14024a390  inc     rbx
0x14024a393  cmp     [rdx+rbx*2], r8w
0x14024a398  jnz     short loc_14024A390
0x14024a39a  mov     r8, rbx
0x14024a39d  mov     rcx, rdi
0x14024a3a0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024a3a5  jmp     loc_14024A639
0x14024a3aa  sub     rax, r13
0x14024a3ad  sar     rax, 1
0x14024a3b0  cmp     rax, rbx
0x14024a3b3  jz      short loc_14024A37F
0x14024a3b5  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x14024a3b9  mov     rdx, [rbp+57h+var_80]
0x14024a3bd  sub     rdx, r8
0x14024a3c0  sar     rdx, 1; nBufferLength
0x14024a3c3  xor     r9d, r9d; lpFilePart
0x14024a3c6  mov     rcx, r13; lpFileName
0x14024a3c9  call    cs:__imp_GetFullPathNameW
0x14024a3cf  mov     edx, eax
0x14024a3d1  mov     r9, [rbp+57h+lpBuffer]
0x14024a3d5  mov     rax, [rbp+57h+var_80]
0x14024a3d9  sub     rax, r9
0x14024a3dc  sar     rax, 1
0x14024a3df  cmp     rax, rdx
0x14024a3e2  jnb     short loc_14024A424
0x14024a3e4  lea     rcx, [rbp+57h+lpBuffer]
0x14024a3e8  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x14024a3ed  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x14024a3f1  mov     rdx, [rbp+57h+var_80]
0x14024a3f5  sub     rdx, r8
0x14024a3f8  sar     rdx, 1; nBufferLength
0x14024a3fb  xor     r9d, r9d; lpFilePart
0x14024a3fe  mov     rcx, r13; lpFileName
0x14024a401  call    cs:__imp_GetFullPathNameW
0x14024a407  mov     rcx, [rbp+5Fh]; this
0x14024a40b  mov     r9, [rbp+57h+lpBuffer]; char *
0x14024a40f  mov     rdx, [rbp+57h+var_80]
0x14024a413  sub     rdx, r9
0x14024a416  sar     rdx, 1
0x14024a419  mov     eax, eax
0x14024a41b  cmp     rdx, rax
0x14024a41e  jbe     loc_14024A6A2
0x14024a424  xorps   xmm0, xmm0
0x14024a427  movups  xmmword ptr [rbp+57h+String1], xmm0
0x14024a42b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14024a433  movdqu  [rbp+57h+var_68], xmm1
0x14024a438  xor     r13d, r13d
0x14024a43b  mov     word ptr [rbp+57h+String1], r13w
0x14024a440  mov     r8, r14; MaxCount
0x14024a443  lea     rdx, asc_140471118; "\\\\"
0x14024a44a  mov     rcx, r9; String1
0x14024a44d  call    cs:__imp_wcsncmp
0x14024a453  test    eax, eax
0x14024a455  jz      loc_14024A4F1
0x14024a45b  mov     r14, [rbp+57h+lpBuffer]
0x14024a45f  xorps   xmm0, xmm0
0x14024a462  movups  [rsp+130h+Src+8], xmm0
0x14024a467  xorps   xmm1, xmm1
0x14024a46a  movdqu  [rsp+130h+var_F8+8], xmm1
0x14024a470  mov     r8, rsi
0x14024a473  lea     rdx, asc_140416A78; "\\\\?\\"
0x14024a47a  lea     rcx, [rsp+130h+Src+8]
0x14024a47f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024a484  nop
0x14024a485  inc     rbx
0x14024a488  cmp     [r14+rbx*2], r13w
0x14024a48d  jnz     short loc_14024A485
0x14024a48f  mov     r8, rbx
0x14024a492  mov     rdx, r14
0x14024a495  lea     rcx, [rsp+130h+Src+8]; Src
0x14024a49a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14024a49f  movups  xmm7, xmmword ptr [rax]
0x14024a4a2  movups  [rbp+57h+var_D0], xmm7
0x14024a4a6  movups  xmm6, xmmword ptr [rax+10h]
0x14024a4aa  mov     [rax], r13w
0x14024a4ae  mov     [rax+10h], r13
0x14024a4b2  mov     qword ptr [rax+18h], 7
0x14024a4ba  lea     rcx, [rbp+57h+String1]
0x14024a4be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024a4c3  movups  xmmword ptr [rbp+57h+String1], xmm7
0x14024a4c7  movups  [rbp+57h+var_68], xmm6
0x14024a4cb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14024a4d3  movdqu  [rbp+57h+var_C0], xmm0
0x14024a4d8  mov     word ptr [rbp+57h+var_D0], r13w
0x14024a4dd  lea     rcx, [rbp+57h+var_D0]
0x14024a4e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024a4e6  nop
0x14024a4e7  lea     rcx, [rsp+130h+Src+8]
0x14024a4ec  jmp     loc_14024A5DF
0x14024a4f1  mov     r8, r12; MaxCount
0x14024a4f4  lea     rdx, asc_140471098; "\\\\.\\"
0x14024a4fb  mov     rcx, [rbp+57h+lpBuffer]; String1
0x14024a4ff  call    cs:__imp_wcsncmp
0x14024a505  mov     rcx, [rbp+57h+lpBuffer]; this
0x14024a509  test    eax, eax
0x14024a50b  jnz     short loc_14024A529
0x14024a50d  mov     rax, [rbp+57h+lpBuffer+8]
0x14024a511  sub     rax, rcx
0x14024a514  sar     rax, 1
0x14024a517  cmp     rax, 2
0x14024a51b  jbe     loc_14024A6B4
0x14024a521  mov     word ptr [rcx+4], 3Fh ; '?'
0x14024a527  jmp     short loc_14024A53D
0x14024a529  mov     r8, rsi; MaxCount
0x14024a52c  lea     rdx, asc_140416A78; "\\\\?\\"
0x14024a533  call    cs:__imp_wcsncmp
0x14024a539  test    eax, eax
0x14024a53b  jnz     short loc_14024A54F
0x14024a53d  mov     rdx, [rbp+57h+lpBuffer]; Src
0x14024a541  lea     rcx, [rbp+57h+String1]; void *
0x14024a545  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14024a54a  jmp     loc_14024A5E4
0x14024a54f  mov     rax, [rbp+57h+lpBuffer]
0x14024a553  lea     r14, [rax+r14*2]
0x14024a557  xorps   xmm0, xmm0
0x14024a55a  movups  [rbp+57h+var_B0], xmm0
0x14024a55e  xorps   xmm1, xmm1
0x14024a561  movdqu  [rbp+57h+var_A0], xmm1
0x14024a566  mov     r8, r15
0x14024a569  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x14024a570  lea     rcx, [rbp+57h+var_B0]
0x14024a574  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024a579  nop
0x14024a57a  inc     rbx
0x14024a57d  cmp     [r14+rbx*2], r13w
0x14024a582  jnz     short loc_14024A57A
0x14024a584  mov     r8, rbx
0x14024a587  mov     rdx, r14
0x14024a58a  lea     rcx, [rbp+57h+var_B0]; Src
0x14024a58e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14024a593  movups  xmm7, xmmword ptr [rax]
0x14024a596  movups  [rbp+57h+var_D0], xmm7
0x14024a59a  movups  xmm6, xmmword ptr [rax+10h]
0x14024a59e  mov     [rax], r13w
0x14024a5a2  mov     [rax+10h], r13
0x14024a5a6  mov     qword ptr [rax+18h], 7
0x14024a5ae  lea     rcx, [rbp+57h+String1]
0x14024a5b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024a5b7  movups  xmmword ptr [rbp+57h+String1], xmm7
0x14024a5bb  movups  [rbp+57h+var_68], xmm6
0x14024a5bf  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14024a5c7  movdqu  [rbp+57h+var_C0], xmm0
0x14024a5cc  mov     word ptr [rbp+57h+var_D0], r13w
0x14024a5d1  lea     rcx, [rbp+57h+var_D0]
0x14024a5d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024a5da  nop
0x14024a5db  lea     rcx, [rbp+57h+var_B0]
0x14024a5df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024a5e4  lea     rcx, [rbp+57h+String1]
0x14024a5e8  cmp     qword ptr [rbp+57h+var_68+8], 7
0x14024a5ed  cmova   rcx, [rbp+57h+String1]; String1
0x14024a5f2  mov     rbx, [rbp+5Fh]
0x14024a5f6  mov     r8, rsi; MaxCount
0x14024a5f9  lea     rdx, asc_140416A78; "\\\\?\\"
0x14024a600  call    cs:__imp_wcsncmp
0x14024a606  test    eax, eax
0x14024a608  jnz     loc_14024A6BA
0x14024a60e  movups  xmm0, xmmword ptr [rbp+57h+String1]
0x14024a612  movups  xmmword ptr [rdi], xmm0
0x14024a615  movups  xmm1, [rbp+57h+var_68]
0x14024a619  movups  xmmword ptr [rdi+10h], xmm1
0x14024a61d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14024a625  movdqu  [rbp+57h+var_68], xmm0
0x14024a62a  mov     word ptr [rbp+57h+String1], r13w
0x14024a62f  lea     rcx, [rbp+57h+String1]
0x14024a633  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024a638  nop
0x14024a639  lea     rcx, [rbp+57h+lpBuffer]
0x14024a63d  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x14024a642  mov     rax, rdi
0x14024a645  mov     rcx, [rbp+57h+var_58]
0x14024a649  xor     rcx, rsp; StackCookie
0x14024a64c  call    __security_check_cookie
0x14024a651  lea     r11, [rsp+130h+var_30]
0x14024a659  mov     rbx, [r11+50h]
0x14024a65d  movaps  xmm6, xmmword ptr [r11-10h]
0x14024a662  movaps  xmm7, xmmword ptr [r11-20h]
0x14024a667  mov     rsp, r11
0x14024a66a  pop     r15
0x14024a66c  pop     r14
0x14024a66e  pop     r13
0x14024a670  pop     r12
0x14024a672  pop     rdi
0x14024a673  pop     rsi
0x14024a674  pop     rbp
0x14024a675  retn
0x14024a676  mov     rcx, [rbp+5Fh]; this
0x14024a67a  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14024a681  mov     edx, 0C9h; void *
0x14024a686  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14024a68c  mov     rcx, [rbp+5Fh]; this
0x14024a690  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14024a697  mov     edx, 0C9h; void *
0x14024a69c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14024a6a2  lea     r8, aCW1SSrcOrchest_33; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
  ... truncated ...
```
