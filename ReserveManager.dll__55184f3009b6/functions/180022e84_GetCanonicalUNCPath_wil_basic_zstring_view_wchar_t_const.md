# GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x180022e84`
- end: `0x180023228`
- name: `?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001aff0`

## callees

- `0x180003870`
- `0x18000bfa0`
- `0x180011c38`
- `0x18001224c`
- `0x1800222f0`
- `0x1800228e4`
- `0x180022a00`
- `0x180022afc`
- `0x180022c50`
- `0x180022d54`
- `0x180022de4`
- `0x180022e84`
- `0x180031be0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180022fdf`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023041`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180022fdf`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023041`

## string_xrefs

- `0x180023201`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x180023216`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  __int64 v9; // rax
  __int64 not_ch; // rax
  __int64 v11; // r11
  __int64 v12; // rdx
  unsigned __int64 FullPathNameW; // rdx
  LPWSTR v14; // rbx
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  DWORD v17; // eax
  const char *v18; // r9
  const wchar_t *v19; // rdx
  size_t v20; // r14
  LPWSTR v21; // r8
  wchar_t **v22; // rdx
  const wchar_t *v23; // rdx
  LPWSTR v24; // rdx
  const wchar_t *v25; // rdx
  __int64 v26; // rax
  const wchar_t *v27; // rdx
  const wchar_t *v28; // rcx
  const char *v29; // r9
  __int64 v30; // rdx
  char *v32[3]; // [rsp+40h] [rbp-C8h] BYREF
  LPWSTR lpBuffer; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR *v34; // [rsp+68h] [rbp-A0h]
  _QWORD String1[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i si128; // [rsp+88h] [rbp-80h]
  wchar_t *v37[2]; // [rsp+98h] [rbp-70h] BYREF
  size_t v38[2]; // [rsp+A8h] [rbp-60h]
  wchar_t *v39[2]; // [rsp+B8h] [rbp-50h] BYREF
  size_t v40[2]; // [rsp+C8h] [rbp-40h]
  wchar_t *String2[2]; // [rsp+D8h] [rbp-30h] BYREF
  size_t MaxCount[2]; // [rsp+E8h] [rbp-20h]
  _OWORD v43[2]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  *(_OWORD *)&String1[1] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String1[1]) = 0;
  *(_OWORD *)String2 = 0;
  *(_OWORD *)MaxCount = 0;
  std::wstring::_Construct<1,wchar_t const *>(String2, L"\\\\");
  *(_OWORD *)v37 = 0;
  *(_OWORD *)v38 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( asc_18003EBE0[v5] );
  std::wstring::_Construct<1,wchar_t const *>(v37, L"\\\\?\\");
  memset(v43, 0, sizeof(v43));
  v6 = -1;
  do
    ++v6;
  while ( aUnc[v6] );
  std::wstring::_Construct<1,wchar_t const *>(v43, L"\\\\?\\UNC\\");
  *(_OWORD *)v39 = 0;
  *(_OWORD *)v40 = 0;
  v7 = -1;
  do
    ++v7;
  while ( asc_18003EBD0[v7] );
  std::wstring::_Construct<1,wchar_t const *>(v39, L"\\\\.\\");
  UnicodeStringBuffer::UnicodeStringBuffer((UnicodeStringBuffer *)&lpBuffer, v8);
  v9 = a2[1];
  if ( !v9
    || (not_ch = std::_Find_not_ch_vectorized<wchar_t>(*a2, *a2 + 2 * v9), not_ch == v12)
    || (not_ch - v11) >> 1 == -1 )
  {
    v30 = *a2;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a1, v30);
    goto LABEL_41;
  }
  FullPathNameW = GetFullPathNameW((LPCWSTR)*a2, (__int64)(String1[0] - (_QWORD)lpBuffer) >> 1, lpBuffer, 0);
  v14 = lpBuffer;
  v15 = String1[0];
  if ( (__int64)(String1[0] - (_QWORD)lpBuffer) >> 1 < FullPathNameW )
  {
    v16 = v34 - lpBuffer;
    if ( FullPathNameW >= v16 )
    {
      if ( FullPathNameW > v16 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpBuffer);
        v15 = String1[0];
        v14 = lpBuffer;
      }
    }
    else
    {
      v34 = &lpBuffer[FullPathNameW];
    }
    v17 = GetFullPathNameW((LPCWSTR)*a2, (v15 - (__int64)v14) >> 1, v14, 0);
    v14 = lpBuffer;
    if ( (__int64)(String1[0] - (_QWORD)lpBuffer) >> 1 <= (unsigned __int64)v17 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
        v18);
  }
  v19 = (const wchar_t *)String2;
  if ( MaxCount[1] > 7 )
    v19 = String2[0];
  v20 = MaxCount[0];
  if ( wcsncmp_0(v14, v19, LODWORD(MaxCount[0])) )
  {
    v21 = v14;
    v22 = v37;
LABEL_33:
    v26 = std::operator+<wchar_t>(v32, v22, v21);
    std::wstring::operator=(&String1[1], v26);
    std::wstring::~wstring(v32);
    goto LABEL_34;
  }
  v23 = (const wchar_t *)v39;
  if ( v40[1] > 7 )
    v23 = v39[0];
  if ( !wcsncmp_0(v14, v23, LODWORD(v40[0])) )
  {
    v14[2] = 63;
    v24 = lpBuffer;
    do
      ++v4;
    while ( lpBuffer[v4] );
  }
  else
  {
    v25 = (const wchar_t *)v37;
    if ( v38[1] > 7 )
      v25 = v37[0];
    if ( wcsncmp_0(v14, v25, LODWORD(v38[0])) )
    {
      v21 = &v14[v20];
      v22 = (wchar_t **)v43;
      goto LABEL_33;
    }
    do
      ++v4;
    while ( v14[v4] );
    v24 = v14;
  }
  std::wstring::_Assign<wchar_t>(&String1[1], v24, v4);
LABEL_34:
  v27 = (const wchar_t *)v37;
  if ( v38[1] > 7 )
    v27 = v37[0];
  v28 = (const wchar_t *)&String1[1];
  if ( si128.m128i_i64[1] > 7uLL )
    v28 = (const wchar_t *)String1[1];
  if ( wcsncmp_0(v28, v27, LODWORD(v38[0])) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      v29);
  *(_OWORD *)a1 = *(_OWORD *)&String1[1];
  *(__m128i *)(a1 + 16) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String1[1]) = 0;
LABEL_41:
  std::vector<wchar_t>::~vector<wchar_t>(&lpBuffer);
  std::wstring::~wstring((char **)v39);
  std::wstring::~wstring((char **)v43);
  std::wstring::~wstring((char **)v37);
  std::wstring::~wstring((char **)String2);
  std::wstring::~wstring((char **)&String1[1]);
  return a1;
}

```

## disassembly

```asm
0x180022e84  mov     rax, rsp
0x180022e87  push    rbp
0x180022e88  push    rsi
0x180022e89  push    rdi
0x180022e8a  push    r14
0x180022e8c  push    r15
0x180022e8e  lea     rbp, [rax-48h]
0x180022e92  sub     rsp, 120h
0x180022e99  mov     [rsp+140h+var_118], 0FFFFFFFFFFFFFFFEh
0x180022ea2  mov     [rax+18h], rbx
0x180022ea6  mov     rax, cs:__security_cookie
0x180022ead  xor     rax, rsp
0x180022eb0  mov     [rbp+40h+var_30], rax
0x180022eb4  mov     r14, rdx
0x180022eb7  mov     rsi, rcx
0x180022eba  mov     qword ptr [rsp+140h+var_110], rcx
0x180022ebf  xor     r15d, r15d
0x180022ec2  xorps   xmm0, xmm0
0x180022ec5  movups  xmmword ptr [rsp+140h+String1+8], xmm0
0x180022eca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180022ed2  movdqu  [rbp+40h+var_C0], xmm1
0x180022ed7  mov     word ptr [rsp+140h+String1+8], r15w
0x180022edd  movups  xmmword ptr [rbp+40h+String2], xmm0
0x180022ee1  xorps   xmm1, xmm1
0x180022ee4  movdqu  xmmword ptr [rbp+40h+MaxCount], xmm1
0x180022ee9  lea     r8d, [r15+2]
0x180022eed  lea     rdx, asc_18003EC6C; "\\\\"
0x180022ef4  lea     rcx, [rbp+40h+String2]
0x180022ef8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180022efd  nop
0x180022efe  xorps   xmm0, xmm0
0x180022f01  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x180022f05  xorps   xmm1, xmm1
0x180022f08  movdqu  xmmword ptr [rbp+40h+var_A0], xmm1
0x180022f0d  lea     rdx, asc_18003EBE0; "\\\\?\\"
0x180022f14  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180022f18  mov     r8, rdi
0x180022f1b  inc     r8
0x180022f1e  cmp     [rdx+r8*2], r15w
0x180022f23  jnz     short loc_180022F1B
0x180022f25  lea     rcx, [rbp+40h+var_B0]
0x180022f29  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180022f2e  nop
0x180022f2f  xorps   xmm0, xmm0
0x180022f32  movups  [rbp+40h+var_50], xmm0
0x180022f36  xorps   xmm1, xmm1
0x180022f39  movdqu  [rbp+40h+var_40], xmm1
0x180022f3e  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x180022f45  mov     r8, rdi
0x180022f48  inc     r8
0x180022f4b  cmp     [rdx+r8*2], r15w
0x180022f50  jnz     short loc_180022F48
0x180022f52  lea     rcx, [rbp+40h+var_50]
0x180022f56  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180022f5b  nop
0x180022f5c  xorps   xmm0, xmm0
0x180022f5f  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x180022f63  xorps   xmm1, xmm1
0x180022f66  movdqu  xmmword ptr [rbp+40h+var_80], xmm1
0x180022f6b  lea     rdx, asc_18003EBD0; "\\\\.\\"
0x180022f72  mov     r8, rdi
0x180022f75  inc     r8
0x180022f78  cmp     [rdx+r8*2], r15w
0x180022f7d  jnz     short loc_180022F75
0x180022f7f  lea     rcx, [rbp+40h+var_90]
0x180022f83  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180022f88  nop
0x180022f89  lea     rcx, [rsp+140h+lpBuffer]; this
0x180022f8e  call    ??0UnicodeStringBuffer@@QEAA@_K@Z; UnicodeStringBuffer::UnicodeStringBuffer(unsigned __int64)
0x180022f93  nop
0x180022f94  mov     rax, [r14+8]
0x180022f98  cmp     rax, 1
0x180022f9c  jb      loc_180023180
0x180022fa2  mov     r11, [r14]
0x180022fa5  lea     rdx, [r11+rax*2]
0x180022fa9  mov     rcx, r11
0x180022fac  call    ??$_Find_not_ch_vectorized@_W@std@@YAPEB_WQEB_W0_W@Z; std::_Find_not_ch_vectorized<wchar_t>(wchar_t const * const,wchar_t const * const,wchar_t)
0x180022fb1  cmp     rax, rdx
0x180022fb4  jz      loc_180023180
0x180022fba  sub     rax, r11
0x180022fbd  sar     rax, 1
0x180022fc0  cmp     rax, rdi
0x180022fc3  jz      loc_180023180
0x180022fc9  mov     r8, [rsp+140h+lpBuffer]; lpBuffer
0x180022fce  mov     rdx, qword ptr [rsp+140h+String1]
0x180022fd3  sub     rdx, r8
0x180022fd6  sar     rdx, 1; nBufferLength
0x180022fd9  xor     r9d, r9d; lpFilePart
0x180022fdc  mov     rcx, [r14]; lpFileName
0x180022fdf  call    cs:__imp_GetFullPathNameW
0x180022fe5  mov     edx, eax
0x180022fe7  mov     rbx, [rsp+140h+lpBuffer]
0x180022fec  mov     rcx, qword ptr [rsp+140h+String1]
0x180022ff1  mov     rax, rcx
0x180022ff4  sub     rax, rbx
0x180022ff7  sar     rax, 1
0x180022ffa  cmp     rax, rdx
0x180022ffd  jnb     short loc_180023066
0x180022fff  mov     rax, [rsp+140h+var_E0]
0x180023004  sub     rax, rbx
0x180023007  sar     rax, 1
0x18002300a  cmp     rdx, rax
0x18002300d  jnb     short loc_18002301A
0x18002300f  lea     rax, [rbx+rdx*2]
0x180023013  mov     [rsp+140h+var_E0], rax
0x180023018  jmp     short loc_180023030
0x18002301a  jbe     short loc_180023030
0x18002301c  lea     rcx, [rsp+140h+lpBuffer]
0x180023021  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180023026  mov     rcx, qword ptr [rsp+140h+String1]
0x18002302b  mov     rbx, [rsp+140h+lpBuffer]
0x180023030  sub     rcx, rbx
0x180023033  sar     rcx, 1
0x180023036  xor     r9d, r9d; lpFilePart
0x180023039  mov     r8, rbx; lpBuffer
0x18002303c  mov     edx, ecx; nBufferLength
0x18002303e  mov     rcx, [r14]; lpFileName
0x180023041  call    cs:__imp_GetFullPathNameW
0x180023047  mov     rcx, [rbp+48h]; this
0x18002304b  mov     rdx, qword ptr [rsp+140h+String1]
0x180023050  mov     rbx, [rsp+140h+lpBuffer]
0x180023055  sub     rdx, rbx
0x180023058  sar     rdx, 1
0x18002305b  mov     eax, eax
0x18002305d  cmp     rdx, rax
0x180023060  jbe     loc_180023216
0x180023066  lea     rdx, [rbp+40h+String2]
0x18002306a  cmp     [rbp+40h+MaxCount+8], 7
0x18002306f  cmova   rdx, [rbp+40h+String2]; String2
0x180023074  mov     r14, [rbp+40h+MaxCount]
0x180023078  mov     r8d, r14d; MaxCount
0x18002307b  mov     rcx, rbx; String1
0x18002307e  call    wcsncmp_0
0x180023083  test    eax, eax
0x180023085  jz      short loc_180023090
0x180023087  mov     r8, rbx
0x18002308a  lea     rdx, [rbp+40h+var_B0]
0x18002308e  jmp     short loc_180023107
0x180023090  lea     rdx, [rbp+40h+var_90]
0x180023094  cmp     [rbp+40h+var_80+8], 7
0x180023099  cmova   rdx, [rbp+40h+var_90]; String2
0x18002309e  mov     r8d, dword ptr [rbp+40h+var_80]; MaxCount
0x1800230a2  mov     rcx, rbx; String1
0x1800230a5  call    wcsncmp_0
0x1800230aa  test    eax, eax
0x1800230ac  jnz     short loc_1800230C5
0x1800230ae  mov     word ptr [rbx+4], 3Fh ; '?'
0x1800230b4  mov     rdx, [rsp+140h+lpBuffer]
0x1800230b9  inc     rdi
0x1800230bc  cmp     [rdx+rdi*2], r15w
0x1800230c1  jnz     short loc_1800230B9
0x1800230c3  jmp     short loc_1800230F0
0x1800230c5  lea     rdx, [rbp+40h+var_B0]
0x1800230c9  cmp     [rbp+40h+var_A0+8], 7
0x1800230ce  cmova   rdx, [rbp+40h+var_B0]; String2
0x1800230d3  mov     r8d, dword ptr [rbp+40h+var_A0]; MaxCount
0x1800230d7  mov     rcx, rbx; String1
0x1800230da  call    wcsncmp_0
0x1800230df  test    eax, eax
0x1800230e1  jnz     short loc_1800230FF
0x1800230e3  inc     rdi
0x1800230e6  cmp     [rbx+rdi*2], r15w
0x1800230eb  jnz     short loc_1800230E3
0x1800230ed  mov     rdx, rbx
0x1800230f0  mov     r8, rdi
0x1800230f3  lea     rcx, [rsp+140h+String1+8]
0x1800230f8  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800230fd  jmp     short loc_180023128
0x1800230ff  lea     r8, [rbx+r14*2]
0x180023103  lea     rdx, [rbp+40h+var_50]
0x180023107  lea     rcx, [rsp+38h]
0x18002310c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180023111  mov     rdx, rax
0x180023114  lea     rcx, [rsp+140h+String1+8]
0x180023119  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002311e  lea     rcx, [rsp+38h]
0x180023123  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023128  lea     rdx, [rbp+40h+var_B0]
0x18002312c  cmp     [rbp+40h+var_A0+8], 7
0x180023131  cmova   rdx, [rbp+40h+var_B0]; String2
0x180023136  lea     rcx, [rsp+140h+String1+8]
0x18002313b  cmp     qword ptr [rbp+40h+var_C0+8], 7
0x180023140  cmova   rcx, qword ptr [rsp+140h+String1+8]; String1
0x180023146  mov     rbx, [rbp+48h]
0x18002314a  mov     r8d, dword ptr [rbp+40h+var_A0]; MaxCount
0x18002314e  call    wcsncmp_0
0x180023153  test    eax, eax
0x180023155  jnz     loc_180023201
0x18002315b  movups  xmm0, xmmword ptr [rsp+140h+String1+8]
0x180023160  movups  xmmword ptr [rsi], xmm0
0x180023163  movups  xmm1, [rbp+40h+var_C0]
0x180023167  movups  xmmword ptr [rsi+10h], xmm1
0x18002316b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180023173  movdqu  [rbp+40h+var_C0], xmm0
0x180023178  mov     word ptr [rsp+140h+String1+8], r15w
0x18002317e  jmp     short loc_18002319E
0x180023180  mov     rdx, [r14]
0x180023183  mov     r8, [r14+8]
0x180023187  xorps   xmm0, xmm0
0x18002318a  movups  xmmword ptr [rsi], xmm0
0x18002318d  mov     [rsi+10h], r15
0x180023191  mov     [rsi+18h], r15
0x180023195  mov     rcx, rsi
0x180023198  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002319d  nop
0x18002319e  lea     rcx, [rsp+140h+lpBuffer]
0x1800231a3  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1800231a8  nop
0x1800231a9  lea     rcx, [rbp+40h+var_90]
0x1800231ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231b2  nop
0x1800231b3  lea     rcx, [rbp+40h+var_50]
0x1800231b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231bc  nop
0x1800231bd  lea     rcx, [rbp+40h+var_B0]
0x1800231c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231c6  nop
0x1800231c7  lea     rcx, [rbp+40h+String2]
0x1800231cb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231d0  nop
0x1800231d1  lea     rcx, [rsp+140h+String1+8]
0x1800231d6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800231db  mov     rax, rsi
0x1800231de  mov     rcx, [rbp+40h+var_30]
0x1800231e2  xor     rcx, rsp; StackCookie
0x1800231e5  call    __security_check_cookie
0x1800231ea  mov     rbx, [rsp+140h+arg_10]
0x1800231f2  add     rsp, 120h
0x1800231f9  pop     r15
0x1800231fb  pop     r14
0x1800231fd  pop     rdi
0x1800231fe  pop     rsi
0x1800231ff  pop     rbp
0x180023200  retn
0x180023201  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x180023208  mov     edx, 18Eh; void *
0x18002320d  mov     rcx, rbx; this
0x180023210  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180023216  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002321d  mov     edx, 171h; void *
0x180023222  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
