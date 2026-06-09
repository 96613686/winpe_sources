# xpsutil::AllocAndCopyString(wchar_t * *,wchar_t const *)

- ea: `0x180046048`
- end: `0x18004628c`
- name: `?AllocAndCopyString@xpsutil@@YAXPEAPEA_WPEB_W@Z`
- size: `580`
- prototype: `void __fastcall(xpsutil *__hidden this, wchar_t **, const wchar_t *)`
- caller_count: `32`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800451d8`
- `0x180045280`
- `0x180045640`
- `0x1800457a0`
- `0x180045920`
- `0x180045fb0`
- `0x180046f30`
- `0x180047250`
- `0x180047330`
- `0x180047590`
- `0x180047670`
- `0x180047750`
- `0x1800b585c`
- `0x1800fc720`
- `0x18014f3b4`
- `0x1801671b4`
- `0x180179200`
- `0x18017ee10`
- `0x18017eed0`
- `0x18017ef90`
- `0x18017f100`
- `0x18017f1c0`
- `0x18017f280`
- `0x18017f340`
- `0x18017f400`
- `0x18017f4c0`
- `0x18017f790`
- `0x18017f850`
- `0x18017f910`
- `0x18017f9d0`
- `0x180181310`
- `0x1801b5398`

## callees

- `0x180012450`
- `0x180046048`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800c20c4`
- `0x180134b70`
- `0x1801359ce`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046220`

## string_xrefs

- `0x1800461a1`: `CoTaskMemAlloc returns NULL`
- `0x18004613a`: `size_t overflow in AllocAndCopyString`
- `0x180046229`: `StringCchCopy error when buffer is large enough!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall xpsutil::AllocAndCopyString(LPVOID *this, wchar_t **a2, const wchar_t *a3)
{
  wchar_t **v3; // rdi
  unsigned __int64 v5; // rbx
  SIZE_T v6; // rcx
  _WORD *v7; // rax
  _WORD *v8; // r8
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  __int16 v11; // cx
  _WORD *v12; // rcx
  int v13; // ebx
  win_musl::Formatter *v14; // rax
  const wchar_t *v15; // rax
  win_musl::Formatter *v16; // rax
  const wchar_t *v17; // rax
  win_musl::Formatter *v18; // rax
  const wchar_t *v19; // rax
  _BYTE v20[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[80]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = a2;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)a2 + v5) );
  v6 = 2 * v5 + 2;
  if ( v6 < v5 )
  {
    std::wstring::wstring(v20, L"size_t overflow in AllocAndCopyString", a3);
    v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v21, v20);
    v15 = win_musl::Formatter::c_str(v14);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x6Fu,
      -2142108928,
      (__int64)v15);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v7 = CoTaskMemAlloc(v6);
  v8 = v7;
  *this = v7;
  if ( !v7 )
  {
    std::wstring::wstring(v20, L"CoTaskMemAlloc returns NULL");
    v16 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v21, v20);
    v17 = win_musl::Formatter::c_str(v16);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x79u,
      -2147024882,
      (__int64)v17);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v9 = v5 + 1;
  if ( v5 == -1 )
  {
    v13 = -2147024809;
    if ( !v9 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( v9 > 0x7FFFFFFF )
  {
    v13 = -2147024809;
LABEL_19:
    *v7 = 0;
    goto LABEL_20;
  }
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    v11 = *(_WORD *)v3;
    if ( !*(_WORD *)v3 )
      break;
    v3 = (wchar_t **)((char *)v3 + 2);
    *v8++ = v11;
    --v10;
    --v9;
  }
  while ( v9 );
  v12 = v8 - 1;
  if ( v9 )
    v12 = v8;
  *v12 = 0;
  v13 = v9 == 0 ? 0x8007007A : 0;
  if ( !v9 )
  {
LABEL_20:
    CoTaskMemFree(*this);
    *this = 0;
    std::wstring::wstring(v20, L"StringCchCopy error when buffer is large enough!");
    v18 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v21, v20);
    v19 = win_musl::Formatter::c_str(v18);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x85u,
      v13,
      (__int64)v19);
    throw (SplException::THResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180046048  mov     [rsp-8+arg_10], rbx
0x18004604d  mov     [rsp-8+arg_18], rsi
0x180046052  push    rbp
0x180046053  push    rdi
0x180046054  push    r14
0x180046056  lea     rbp, [rsp-60h]
0x18004605b  sub     rsp, 160h
0x180046062  mov     rax, cs:__security_cookie
0x180046069  xor     rax, rsp
0x18004606c  mov     [rbp+70h+var_20], rax
0x180046070  mov     rdi, rdx
0x180046073  mov     rsi, rcx
0x180046076  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004607a  xor     r14d, r14d
0x18004607d  inc     rbx
0x180046080  cmp     [rdx+rbx*2], r14w
0x180046085  jnz     short loc_18004607D
0x180046087  lea     rcx, ds:2[rbx*2]; cb
0x18004608f  cmp     rcx, rbx
0x180046092  jb      loc_18004613A
0x180046098  call    cs:__imp_CoTaskMemAlloc
0x18004609e  mov     r8, rax
0x1800460a1  mov     [rsi], rax
0x1800460a4  test    rax, rax
0x1800460a7  jz      loc_1800461A1
0x1800460ad  lea     rdx, [rbx+1]
0x1800460b1  test    rdx, rdx
0x1800460b4  jz      loc_18004620F
0x1800460ba  cmp     rdx, 7FFFFFFFh
0x1800460c1  ja      loc_180046208
0x1800460c7  mov     eax, 7FFFFFFEh
0x1800460cc  test    rax, rax
0x1800460cf  jz      short loc_1800460EE
0x1800460d1  movzx   ecx, word ptr [rdi]
0x1800460d4  test    cx, cx
0x1800460d7  jz      short loc_1800460EE
0x1800460d9  add     rdi, 2
0x1800460dd  mov     [r8], cx
0x1800460e1  add     r8, 2
0x1800460e5  dec     rax
0x1800460e8  sub     rdx, 1
0x1800460ec  jnz     short loc_1800460CC
0x1800460ee  lea     rcx, [r8-2]
0x1800460f2  test    rdx, rdx
0x1800460f5  cmovnz  rcx, r8
0x1800460f9  mov     [rcx], r14w
0x1800460fd  mov     rax, rdx
0x180046100  neg     rax
0x180046103  sbb     ebx, ebx
0x180046105  not     ebx
0x180046107  and     ebx, 8007007Ah
0x18004610d  test    rdx, rdx
0x180046110  jz      loc_18004621D
0x180046116  mov     rcx, [rbp+70h+var_20]
0x18004611a  xor     rcx, rsp; StackCookie
0x18004611d  call    __security_check_cookie
0x180046122  lea     r11, [rsp+170h+var_10]
0x18004612a  mov     rbx, [r11+30h]
0x18004612e  mov     rsi, [r11+38h]
0x180046132  mov     rsp, r11
0x180046135  pop     r14
0x180046137  pop     rdi
0x180046138  pop     rbp
0x180046139  retn
0x18004613a  lea     rdx, aSizeTOverflowI; "size_t overflow in AllocAndCopyString"
0x180046141  lea     rcx, [rsp+170h+var_130]
0x180046146  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18004614b  nop
0x18004614c  lea     rdx, [rsp+170h+var_130]
0x180046151  lea     rcx, [rsp+170h+var_110]
0x180046156  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004615b  nop
0x18004615c  mov     rcx, rax; this
0x18004615f  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180046164  mov     [rsp+170h+var_140], rax; __int64
0x180046169  mov     [rsp+170h+var_148], 80520300h; int
0x180046171  mov     [rsp+170h+var_150], 6Fh ; 'o'; unsigned int
0x180046179  lea     r9, Src
0x180046180  lea     r8, aNoFilename; "(no filename)"
0x180046187  lea     rcx, [rbp+70h+pExceptionObject]; this
0x18004618b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180046190  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180046197  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x18004619b  call    _CxxThrowException_0
0x1800461a1  lea     rdx, aCotaskmemalloc; "CoTaskMemAlloc returns NULL"
0x1800461a8  lea     rcx, [rsp+170h+var_130]
0x1800461ad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800461b2  nop
0x1800461b3  lea     rdx, [rsp+170h+var_130]
0x1800461b8  lea     rcx, [rsp+170h+var_110]
0x1800461bd  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800461c2  nop
0x1800461c3  mov     rcx, rax; this
0x1800461c6  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800461cb  mov     [rsp+170h+var_140], rax; __int64
0x1800461d0  mov     [rsp+170h+var_148], 8007000Eh; int
0x1800461d8  mov     [rsp+170h+var_150], 79h ; 'y'; unsigned int
0x1800461e0  lea     r9, Src
0x1800461e7  lea     r8, aNoFilename; "(no filename)"
0x1800461ee  lea     rcx, [rbp+70h+pExceptionObject]; this
0x1800461f2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800461f7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800461fe  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180046202  call    _CxxThrowException_0
0x180046208  mov     ebx, 80070057h
0x18004620d  jmp     short loc_180046219
0x18004620f  mov     ebx, 80070057h
0x180046214  test    rdx, rdx
0x180046217  jz      short loc_18004621D
0x180046219  mov     [rax], r14w
0x18004621d  mov     rcx, [rsi]; pv
0x180046220  call    cs:__imp_CoTaskMemFree
0x180046226  mov     [rsi], r14
0x180046229  lea     rdx, aStringcchcopyE; "StringCchCopy error when buffer is larg"...
0x180046230  lea     rcx, [rsp+170h+var_130]
0x180046235  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18004623a  nop
0x18004623b  lea     rdx, [rsp+170h+var_130]
0x180046240  lea     rcx, [rsp+170h+var_110]
0x180046245  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18004624a  nop
0x18004624b  mov     rcx, rax; this
0x18004624e  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180046253  mov     [rsp+170h+var_140], rax; __int64
0x180046258  mov     [rsp+170h+var_148], ebx; int
0x18004625c  mov     [rsp+170h+var_150], 85h; unsigned int
0x180046264  lea     r9, Src
0x18004626b  lea     r8, aNoFilename; "(no filename)"
0x180046272  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180046276  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004627b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180046282  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180046286  call    _CxxThrowException_0
```
