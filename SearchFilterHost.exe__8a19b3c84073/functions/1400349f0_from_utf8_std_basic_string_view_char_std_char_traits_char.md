# from_utf8(std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x1400349f0`
- end: `0x140034b72`
- name: `?from_utf8@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140034e80`

## callees

- `0x1400030a0`
- `0x140003c80`
- `0x1400063bc`
- `0x14000b5c4`
- `0x14000d80c`
- `0x14001afb8`
- `0x14001b034`
- `0x140024944`
- `0x1400349f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034aea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140034a83`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140034ae0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140034a83`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140034ae0`

## string_xrefs

- `0x140034a98`: `onecoreuap\base\appmodel\Search\common\include\utf8.h`
- `0x140034b22`: `onecoreuap\base\appmodel\Search\common\include\utf8.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall from_utf8(__int64 a1, __int64 a2)
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
    v5 = MultiByteToWideChar(0xFDE9u, 0, *(LPCCH *)a2, v3, 0, 0);
    cchWideChar = v5;
    if ( !v5 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\utf8.h",
        v6);
    std::wstring::wstring(v14, v5);
    lpWideCharStr = (WCHAR *)v14;
    if ( v14[3] > (LPWSTR)7 )
      lpWideCharStr = v14[0];
    if ( MultiByteToWideChar(0xFDE9u, 8u, v4, v3, lpWideCharStr, cchWideChar) != cchWideChar )
    {
      if ( GetLastError() == 1113 )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid Unicode string.");
        throw (std::invalid_argument *)pExceptionObject;
      }
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\utf8.h",
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
0x1400349f0  mov     rax, rsp
0x1400349f3  push    rbp
0x1400349f4  push    rsi
0x1400349f5  push    rdi
0x1400349f6  sub     rsp, 90h
0x1400349fd  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x140034a05  mov     [rax+18h], rbx
0x140034a09  mov     rax, cs:__security_cookie
0x140034a10  xor     rax, rsp
0x140034a13  mov     [rsp+0A8h+var_28], rax
0x140034a1b  mov     rbx, rcx
0x140034a1e  mov     [rsp+0A8h+var_50], rcx
0x140034a23  mov     rdi, [rdx+8]
0x140034a27  test    rdi, rdi
0x140034a2a  jnz     short loc_140034A36
0x140034a2c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140034a31  jmp     loc_140034B4C
0x140034a36  cmp     rdi, 7FFFFFFFh
0x140034a3d  jbe     short loc_140034A62
0x140034a3f  lea     rdx, aUnableToConver; "Unable to convert strings longer than i"...
0x140034a46  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x140034a4b  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x140034a50  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x140034a57  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140034a5c  call    _CxxThrowException_0
0x140034a62  mov     rbp, [rdx]
0x140034a65  mov     [rsp+0A8h+cchWideChar], 0; cchWideChar
0x140034a6d  mov     [rsp+0A8h+lpWideCharStr], 0; lpWideCharStr
0x140034a76  mov     r9d, edi; cbMultiByte
0x140034a79  mov     r8, rbp; lpMultiByteStr
0x140034a7c  xor     edx, edx; dwFlags
0x140034a7e  mov     ecx, 0FDE9h; CodePage
0x140034a83  call    cs:__imp_MultiByteToWideChar
0x140034a89  movsxd  rsi, eax
0x140034a8c  test    eax, eax
0x140034a8e  jnz     short loc_140034AA8
0x140034a90  mov     rcx, [rsp+0A8h]; this
0x140034a98  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140034a9f  lea     edx, [rax+51h]; void *
0x140034aa2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140034aa8  mov     rdx, rsi
0x140034aab  lea     rcx, [rsp+0A8h+var_48]
0x140034ab0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x140034ab5  nop
0x140034ab6  lea     rax, [rsp+0A8h+var_48]
0x140034abb  cmp     [rsp+0A8h+var_30], 7
0x140034ac1  cmova   rax, [rsp+0A8h+var_48]
0x140034ac7  mov     [rsp+0A8h+cchWideChar], esi; cchWideChar
0x140034acb  mov     [rsp+0A8h+lpWideCharStr], rax; lpWideCharStr
0x140034ad0  mov     r9d, edi; cbMultiByte
0x140034ad3  mov     r8, rbp; lpMultiByteStr
0x140034ad6  mov     edx, 8; dwFlags
0x140034adb  mov     ecx, 0FDE9h; CodePage
0x140034ae0  call    cs:__imp_MultiByteToWideChar
0x140034ae6  cmp     eax, esi
0x140034ae8  jz      short loc_140034B34
0x140034aea  call    cs:__imp_GetLastError
0x140034af0  cmp     eax, 459h
0x140034af5  jnz     short loc_140034B1A
0x140034af7  lea     rdx, aInvalidUnicode; "Invalid Unicode string."
0x140034afe  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x140034b03  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x140034b08  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x140034b0f  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140034b14  call    _CxxThrowException_0
0x140034b1a  mov     rcx, [rsp+0A8h]; this
0x140034b22  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140034b29  mov     edx, 63h ; 'c'; void *
0x140034b2e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140034b34  lea     rdx, [rsp+0A8h+var_48]
0x140034b39  mov     rcx, rbx
0x140034b3c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x140034b41  nop
0x140034b42  lea     rcx, [rsp+0A8h+var_48]
0x140034b47  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140034b4c  mov     rax, rbx
0x140034b4f  mov     rcx, [rsp+0A8h+var_28]
0x140034b57  xor     rcx, rsp; StackCookie
0x140034b5a  call    __security_check_cookie
0x140034b5f  mov     rbx, [rsp+0A8h+arg_10]
0x140034b67  add     rsp, 90h
0x140034b6e  pop     rdi
0x140034b6f  pop     rsi
0x140034b70  pop     rbp
0x140034b71  retn
```
