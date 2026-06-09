# StoreAppProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x1800559d8`
- end: `0x180055b39`
- name: `?RuntimeClassInitialize@StoreAppProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(StoreAppProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047610`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x1800559d8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055a55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055ade`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055a55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055ade`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055a11`

## string_xrefs

- `0x180055a8b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`

## pseudocode

```c
__int64 __fastcall StoreAppProvider::RuntimeClassInitialize(HSTRING *this, struct Windows::Data::Json::IJsonObject *a2)
{
  _QWORD *v2; // rdi
  __int64 (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD *); // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // rax
  int (__fastcall *v12)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r14
  UINT32 length; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v2 = this + 2;
  v5 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(this[2]);
  v6 = -1;
  *v2 = 0;
  v7 = -1;
  length = 0;
  do
    ++v7;
  while ( StoreAppProvider::s_pszJsonTagUwpApp[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(StoreAppProvider::s_pszJsonTagUwpApp, length, &hstringHeader, &string);
  v8 = v5(a2, string, v2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = *(_QWORD *)a2;
    length = 0;
    v12 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(v11 + 96);
    do
      ++v6;
    while ( StoreAppProvider::s_pszJsonTagExists[v6] );
    if ( (int)ULongLongToUInt(v6, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(StoreAppProvider::s_pszJsonTagExists, length, &hstringHeader, &string);
    if ( v12(a2, string, this + 3) < 0 )
      *((_BYTE *)this + 24) = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
      (const char *)(unsigned int)v8,
      length);
    return v9;
  }
}

```

## disassembly

```asm
0x1800559d8  mov     [rsp-38h+arg_10], rbx
0x1800559dd  push    rbp
0x1800559de  push    rsi
0x1800559df  push    rdi
0x1800559e0  push    r12
0x1800559e2  push    r13
0x1800559e4  push    r14
0x1800559e6  push    r15
0x1800559e8  mov     rbp, rsp
0x1800559eb  sub     rsp, 50h
0x1800559ef  mov     rax, cs:__security_cookie
0x1800559f6  xor     rax, rsp
0x1800559f9  mov     [rbp+var_8], rax
0x1800559fd  mov     rax, [rdx]
0x180055a00  lea     rdi, [rcx+10h]
0x180055a04  mov     r15, rcx
0x180055a07  mov     rsi, rdx
0x180055a0a  mov     rcx, [rdi]; string
0x180055a0d  mov     r12, [rax+50h]
0x180055a11  call    cs:__imp_WindowsDeleteString
0x180055a17  xor     r13d, r13d
0x180055a1a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180055a1e  mov     [rdi], r13
0x180055a21  mov     r14, cs:?s_pszJsonTagUwpApp@StoreAppProvider@@0QEBGEB; ushort const * const StoreAppProvider::s_pszJsonTagUwpApp
0x180055a28  mov     rcx, rbx
0x180055a2b  mov     [rbp+length], r13d
0x180055a2f  inc     rcx; unsigned __int64
0x180055a32  cmp     [r14+rcx*2], r13w
0x180055a37  jnz     short loc_180055A2F
0x180055a39  lea     rdx, [rbp+length]; unsigned int *
0x180055a3d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180055a42  test    eax, eax
0x180055a44  jns     short loc_180055A5B
0x180055a46  xor     r9d, r9d; lpArguments
0x180055a49  xor     r8d, r8d; nNumberOfArguments
0x180055a4c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180055a51  lea     edx, [r9+1]; dwExceptionFlags
0x180055a55  call    cs:__imp_RaiseException
0x180055a5b  mov     edx, [rbp+length]; length
0x180055a5e  lea     r9, [rbp+string]; string
0x180055a62  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180055a66  mov     rcx, r14; sourceString
0x180055a69  call    cs:__imp_WindowsCreateStringReference
0x180055a6f  mov     rdx, [rbp+string]
0x180055a73  mov     r8, rdi
0x180055a76  mov     rcx, rsi
0x180055a79  mov     rax, r12
0x180055a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a81  mov     edi, eax
0x180055a83  test    eax, eax
0x180055a85  jns     short loc_180055AA3
0x180055a87  mov     rcx, [rbp+38h]; this
0x180055a8b  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180055a92  mov     r9d, eax; char *
0x180055a95  mov     edx, 29h ; ')'; void *
0x180055a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055a9f  mov     eax, edi
0x180055aa1  jmp     short loc_180055B15
0x180055aa3  mov     rax, [rsi]
0x180055aa6  mov     rdi, cs:?s_pszJsonTagExists@StoreAppProvider@@0QEBGEB; ushort const * const StoreAppProvider::s_pszJsonTagExists
0x180055aad  mov     [rbp+length], r13d
0x180055ab1  mov     r14, [rax+60h]
0x180055ab5  inc     rbx
0x180055ab8  cmp     [rdi+rbx*2], r13w
0x180055abd  jnz     short loc_180055AB5
0x180055abf  lea     rdx, [rbp+length]; unsigned int *
0x180055ac3  mov     rcx, rbx; unsigned __int64
0x180055ac6  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180055acb  test    eax, eax
0x180055acd  jns     short loc_180055AE4
0x180055acf  xor     r9d, r9d; lpArguments
0x180055ad2  xor     r8d, r8d; nNumberOfArguments
0x180055ad5  mov     ecx, 0C000000Dh; dwExceptionCode
0x180055ada  lea     edx, [r9+1]; dwExceptionFlags
0x180055ade  call    cs:__imp_RaiseException
0x180055ae4  mov     edx, [rbp+length]; length
0x180055ae7  lea     r9, [rbp+string]; string
0x180055aeb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180055aef  mov     rcx, rdi; sourceString
0x180055af2  call    cs:__imp_WindowsCreateStringReference
0x180055af8  mov     rdx, [rbp+string]
0x180055afc  lea     r8, [r15+18h]
0x180055b00  mov     rcx, rsi
0x180055b03  mov     rax, r14
0x180055b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b0b  test    eax, eax
0x180055b0d  jns     short loc_180055B13
0x180055b0f  mov     [r15+18h], r13b
0x180055b13  xor     eax, eax
0x180055b15  mov     rcx, [rbp+var_8]
0x180055b19  xor     rcx, rsp; StackCookie
0x180055b1c  call    __security_check_cookie
0x180055b21  mov     rbx, [rsp+50h+arg_10]
0x180055b29  add     rsp, 50h
0x180055b2d  pop     r15
0x180055b2f  pop     r14
0x180055b31  pop     r13
0x180055b33  pop     r12
0x180055b35  pop     rdi
0x180055b36  pop     rsi
0x180055b37  pop     rbp
0x180055b38  retn
```
