# win_dox::AllocAndCopyString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &)

- ea: `0x1800af8d8`
- end: `0x1800afa52`
- name: `?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z`
- size: `378`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800af820`
- `0x1800c12f0`
- `0x1800da4f0`
- `0x1800ee368`
- `0x1800f5920`
- `0x1800f5a10`
- `0x1800fa380`
- `0x1800fa7e0`
- `0x1800fa920`
- `0x1800fa9e0`
- `0x1800fadd0`
- `0x1800fb490`
- `0x1800fb540`
- `0x1800fb670`
- `0x1800fb730`
- `0x1800fbd40`
- `0x180103860`
- `0x1801039a0`
- `0x180103b30`
- `0x180103ff0`

## callees

- `0x1800517a0`
- `0x1800af8d8`
- `0x1800afa58`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af99c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af99c`

## string_xrefs

- `0x1800af936`: `Unable to copy string`
- `0x1800af9a2`: `StringCchCopy() failed.`

## pseudocode

```c
void *__fastcall win_dox::AllocAndCopyString(__int64 a1)
{
  unsigned __int64 v1; // rax
  unsigned __int64 v3; // rdi
  wchar_t *v4; // rax
  const wchar_t *v5; // r8
  void *v6; // r11
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v3 = v1 + 1;
  if ( v1 + 1 < v1 || !is_mul_ok(v3, 2u) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x34u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Overflow - String too long.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v4 = (wchar_t *)CoTaskMemAlloc(2 * v3);
  if ( !v4 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x3Cu,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to copy string");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v5 = (const wchar_t *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) >= 8u )
    v5 = *(const wchar_t **)v5;
  if ( (int)StringCchCopyW(v4, v3, v5) < 0 )
  {
    CoTaskMemFree(v6);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x43u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"StringCchCopy() failed.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return v6;
}

```

## disassembly

```asm
0x1800af8d8  mov     [rsp+arg_8], rbx
0x1800af8dd  push    rdi
0x1800af8de  sub     rsp, 100h
0x1800af8e5  mov     rax, cs:__security_cookie
0x1800af8ec  xor     rax, rsp
0x1800af8ef  mov     [rsp+108h+var_18], rax
0x1800af8f7  mov     rax, [rcx+18h]
0x1800af8fb  mov     rbx, rcx
0x1800af8fe  lea     rdi, [rax+1]
0x1800af902  cmp     rdi, rax
0x1800af905  jb      loc_1800AFA0C
0x1800af90b  mov     eax, 2
0x1800af910  mov     [rsp+108h+var_C8], 0
0x1800af919  mul     rdi
0x1800af91c  test    rdx, rdx
0x1800af91f  jnz     loc_1800AFA0C
0x1800af925  mov     rcx, rax; cb
0x1800af928  call    cs:__imp_CoTaskMemAlloc
0x1800af92e  mov     r11, rax
0x1800af931  test    rax, rax
0x1800af934  jnz     short loc_1800AF97C
0x1800af936  lea     rax, aUnableToCopySt; "Unable to copy string"
0x1800af93d  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800af942  lea     r9, word_18013A0B6
0x1800af949  mov     [rsp+108h+var_E0], 8007000Eh; unsigned int
0x1800af951  lea     r8, aNoFilename; "(no filename)"
0x1800af958  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800af95d  mov     [rsp+108h+var_E8], 3Ch ; '<'; unsigned int
0x1800af965  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800af96a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800af971  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800af976  call    _CxxThrowException_0
0x1800af97c  cmp     qword ptr [rbx+20h], 8
0x1800af981  lea     r8, [rbx+8]
0x1800af985  jb      short loc_1800AF98A
0x1800af987  mov     r8, [r8]; wchar_t *
0x1800af98a  mov     rdx, rdi; unsigned __int64
0x1800af98d  mov     rcx, r11; wchar_t *
0x1800af990  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800af995  test    eax, eax
0x1800af997  jns     short loc_1800AF9E8
0x1800af999  mov     rcx, r11; pv
0x1800af99c  call    cs:__imp_CoTaskMemFree
0x1800af9a2  lea     rax, aStringcchcopyF; "StringCchCopy() failed."
0x1800af9a9  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800af9ae  lea     r9, word_18013A0B6
0x1800af9b5  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x1800af9bd  lea     r8, aNoFilename; "(no filename)"
0x1800af9c4  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800af9c9  mov     [rsp+108h+var_E8], 43h ; 'C'; unsigned int
0x1800af9d1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800af9d6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800af9dd  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800af9e2  call    _CxxThrowException_0
0x1800af9e8  mov     rax, r11
0x1800af9eb  mov     rcx, [rsp+108h+var_18]
0x1800af9f3  xor     rcx, rsp; StackCookie
0x1800af9f6  call    __security_check_cookie
0x1800af9fb  mov     rbx, [rsp+108h+arg_8]
0x1800afa03  add     rsp, 100h
0x1800afa0a  pop     rdi
0x1800afa0b  retn
0x1800afa0c  lea     rax, aOverflowString; "Overflow - String too long."
0x1800afa13  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800afa18  lea     r9, word_18013A0B6
0x1800afa1f  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x1800afa27  lea     r8, aNoFilename; "(no filename)"
0x1800afa2e  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800afa33  mov     [rsp+108h+var_E8], 34h ; '4'; unsigned int
0x1800afa3b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800afa40  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800afa47  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800afa4c  call    _CxxThrowException_0
```
