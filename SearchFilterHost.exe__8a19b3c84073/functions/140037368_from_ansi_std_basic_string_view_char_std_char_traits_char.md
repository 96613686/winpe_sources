# from_ansi(std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x140037368`
- end: `0x1400374e4`
- name: `?from_ansi@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140037518`

## callees

- `0x1400030a0`
- `0x140003c80`
- `0x1400063bc`
- `0x14000b5c4`
- `0x14000d80c`
- `0x14001afb8`
- `0x14001b034`
- `0x140024944`
- `0x140037368`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003745c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003745c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400373f8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140037452`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400373f8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140037452`

## string_xrefs

- `0x14003740d`: `onecoreuap\base\appmodel\Search\common\include\ansi.h`
- `0x140037494`: `onecoreuap\base\appmodel\Search\common\include\ansi.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall from_ansi(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rdi
  const CHAR *v4; // rbp
  int v5; // eax
  const char *v6; // r9
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  const char *v9; // r9
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v12; // [rsp+50h] [rbp-58h]
  __int64 v13; // [rsp+58h] [rbp-50h]
  LPWSTR v14[4]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v12 = -2;
  v13 = a1;
  v3 = *(_QWORD *)(a2 + 8);
  if ( v3 )
  {
    if ( v3 > 0x7FFFFFFF )
    {
      std::invalid_argument::invalid_argument(
        (std::invalid_argument *)pExceptionObject,
        "Unable to convert strings longer than int chars.");
      throw (std::invalid_argument *)pExceptionObject;
    }
    v4 = *(const CHAR **)a2;
    v5 = MultiByteToWideChar(0, 0, *(LPCCH *)a2, v3, 0, 0);
    cchWideChar = v5;
    if ( !v5 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\ansi.h",
        v6);
    std::wstring::wstring(v14, v5);
    lpWideCharStr = (WCHAR *)v14;
    if ( v14[3] > (LPWSTR)7 )
      lpWideCharStr = v14[0];
    if ( MultiByteToWideChar(0, 8u, v4, v3, lpWideCharStr, cchWideChar) != cchWideChar )
    {
      if ( GetLastError() == 1113 )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid Unicode string.");
        throw (std::invalid_argument *)pExceptionObject;
      }
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\ansi.h",
        v9);
    }
    std::wstring::wstring(a1, v14);
    std::wstring::_Tidy_deallocate((__int64)v14);
  }
  else
  {
    std::wstring::wstring(a1);
  }
  return a1;
}

```

## disassembly

```asm
0x140037368  mov     rax, rsp
0x14003736b  push    rbp
0x14003736c  push    rsi
0x14003736d  push    rdi
0x14003736e  sub     rsp, 90h
0x140037375  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x14003737d  mov     [rax+18h], rbx
0x140037381  mov     rax, cs:__security_cookie
0x140037388  xor     rax, rsp
0x14003738b  mov     [rsp+0A8h+var_28], rax
0x140037393  mov     rbx, rcx
0x140037396  mov     [rsp+0A8h+var_50], rcx
0x14003739b  mov     rdi, [rdx+8]
0x14003739f  test    rdi, rdi
0x1400373a2  jnz     short loc_1400373AE
0x1400373a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400373a9  jmp     loc_1400374BE
0x1400373ae  cmp     rdi, 7FFFFFFFh
0x1400373b5  jbe     short loc_1400373DA
0x1400373b7  lea     rdx, aUnableToConver; "Unable to convert strings longer than i"...
0x1400373be  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1400373c3  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1400373c8  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1400373cf  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1400373d4  call    _CxxThrowException_0
0x1400373da  mov     rbp, [rdx]
0x1400373dd  mov     [rsp+0A8h+cchWideChar], 0; cchWideChar
0x1400373e5  mov     [rsp+0A8h+lpWideCharStr], 0; lpWideCharStr
0x1400373ee  mov     r9d, edi; cbMultiByte
0x1400373f1  mov     r8, rbp; lpMultiByteStr
0x1400373f4  xor     edx, edx; dwFlags
0x1400373f6  xor     ecx, ecx; CodePage
0x1400373f8  call    cs:__imp_MultiByteToWideChar
0x1400373fe  movsxd  rsi, eax
0x140037401  test    eax, eax
0x140037403  jnz     short loc_14003741D
0x140037405  mov     rcx, [rsp+0A8h]; this
0x14003740d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140037414  lea     edx, [rax+5Ah]; void *
0x140037417  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003741d  mov     rdx, rsi
0x140037420  lea     rcx, [rsp+0A8h+var_48]
0x140037425  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x14003742a  nop
0x14003742b  lea     rax, [rsp+0A8h+var_48]
0x140037430  cmp     [rsp+0A8h+var_30], 7
0x140037436  cmova   rax, [rsp+0A8h+var_48]
0x14003743c  mov     [rsp+0A8h+cchWideChar], esi; cchWideChar
0x140037440  mov     [rsp+0A8h+lpWideCharStr], rax; lpWideCharStr
0x140037445  mov     r9d, edi; cbMultiByte
0x140037448  mov     r8, rbp; lpMultiByteStr
0x14003744b  mov     edx, 8; dwFlags
0x140037450  xor     ecx, ecx; CodePage
0x140037452  call    cs:__imp_MultiByteToWideChar
0x140037458  cmp     eax, esi
0x14003745a  jz      short loc_1400374A6
0x14003745c  call    cs:__imp_GetLastError
0x140037462  cmp     eax, 459h
0x140037467  jnz     short loc_14003748C
0x140037469  lea     rdx, aInvalidUnicode; "Invalid Unicode string."
0x140037470  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x140037475  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x14003747a  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x140037481  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140037486  call    _CxxThrowException_0
0x14003748c  mov     rcx, [rsp+0A8h]; this
0x140037494  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14003749b  mov     edx, 70h ; 'p'; void *
0x1400374a0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400374a6  lea     rdx, [rsp+0A8h+var_48]
0x1400374ab  mov     rcx, rbx
0x1400374ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400374b3  nop
0x1400374b4  lea     rcx, [rsp+0A8h+var_48]
0x1400374b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400374be  mov     rax, rbx
0x1400374c1  mov     rcx, [rsp+0A8h+var_28]
0x1400374c9  xor     rcx, rsp; StackCookie
0x1400374cc  call    __security_check_cookie
0x1400374d1  mov     rbx, [rsp+0A8h+arg_10]
0x1400374d9  add     rsp, 90h
0x1400374e0  pop     rdi
0x1400374e1  pop     rsi
0x1400374e2  pop     rbp
0x1400374e3  retn
```
