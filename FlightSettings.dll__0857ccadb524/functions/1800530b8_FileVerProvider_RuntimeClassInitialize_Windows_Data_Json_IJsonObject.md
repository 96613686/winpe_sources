# FileVerProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x1800530b8`
- end: `0x18005329c`
- name: `?RuntimeClassInitialize@FileVerProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(FileVerProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047200`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x1800530b8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053135`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800531d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053241`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053135`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800531d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800531e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800531e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800530f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800530f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053194`

## string_xrefs

- `0x18005316b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`

## pseudocode

```c
__int64 __fastcall FileVerProvider::RuntimeClassInitialize(HSTRING *this, struct Windows::Data::Json::IJsonObject *a2)
{
  _QWORD *v2; // rdi
  __int64 (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD *); // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  __int64 (__fastcall *v11)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r12
  unsigned __int64 v12; // rcx
  int v13; // eax
  int (__fastcall *v14)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *); // r15
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
  while ( FileVerProvider::s_pszJsonTagPath[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FileVerProvider::s_pszJsonTagPath, length, &hstringHeader, &string);
  v8 = v5(a2, string, v2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
    WindowsDeleteString(this[3]);
    this[3] = 0;
    v12 = -1;
    length = 0;
    do
      ++v12;
    while ( FileVerProvider::s_pszJsonTagGuid[v12] );
    if ( (int)ULongLongToUInt(v12, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FileVerProvider::s_pszJsonTagGuid, length, &hstringHeader, &string);
    v13 = v11(a2, string, this + 3);
    length = 0;
    *((_BYTE *)this + 32) = v13 >= 0;
    v14 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *))(*(_QWORD *)a2 + 96LL);
    do
      ++v6;
    while ( FileVerProvider::s_pszJsonTagExists[v6] );
    if ( (int)ULongLongToUInt(v6, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FileVerProvider::s_pszJsonTagExists, length, &hstringHeader, &string);
    if ( v14(a2, string, (char *)this + 33) < 0 )
      *((_BYTE *)this + 33) = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\fileverprovider.cpp",
      (const char *)(unsigned int)v8,
      length);
    return v9;
  }
}

```

## disassembly

```asm
0x1800530b8  mov     [rsp-38h+arg_10], rbx
0x1800530bd  push    rbp
0x1800530be  push    rsi
0x1800530bf  push    rdi
0x1800530c0  push    r12
0x1800530c2  push    r13
0x1800530c4  push    r14
0x1800530c6  push    r15
0x1800530c8  mov     rbp, rsp
0x1800530cb  sub     rsp, 50h
0x1800530cf  mov     rax, cs:__security_cookie
0x1800530d6  xor     rax, rsp
0x1800530d9  mov     [rbp+var_8], rax
0x1800530dd  mov     rax, [rdx]
0x1800530e0  lea     rdi, [rcx+10h]
0x1800530e4  mov     r14, rcx
0x1800530e7  mov     rsi, rdx
0x1800530ea  mov     rcx, [rdi]; string
0x1800530ed  mov     r12, [rax+50h]
0x1800530f1  call    cs:__imp_WindowsDeleteString
0x1800530f7  xor     r13d, r13d
0x1800530fa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800530fe  mov     [rdi], r13
0x180053101  mov     r15, cs:?s_pszJsonTagPath@FileVerProvider@@0QEBGEB; ushort const * const FileVerProvider::s_pszJsonTagPath
0x180053108  mov     rcx, rbx
0x18005310b  mov     [rbp+length], r13d
0x18005310f  inc     rcx; unsigned __int64
0x180053112  cmp     [r15+rcx*2], r13w
0x180053117  jnz     short loc_18005310F
0x180053119  lea     rdx, [rbp+length]; unsigned int *
0x18005311d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180053122  test    eax, eax
0x180053124  jns     short loc_18005313B
0x180053126  xor     r9d, r9d; lpArguments
0x180053129  xor     r8d, r8d; nNumberOfArguments
0x18005312c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180053131  lea     edx, [r9+1]; dwExceptionFlags
0x180053135  call    cs:__imp_RaiseException
0x18005313b  mov     edx, [rbp+length]; length
0x18005313e  lea     r9, [rbp+string]; string
0x180053142  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180053146  mov     rcx, r15; sourceString
0x180053149  call    cs:__imp_WindowsCreateStringReference
0x18005314f  mov     rdx, [rbp+string]
0x180053153  mov     r8, rdi
0x180053156  mov     rcx, rsi
0x180053159  mov     rax, r12
0x18005315c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053161  mov     edi, eax
0x180053163  test    eax, eax
0x180053165  jns     short loc_180053186
0x180053167  mov     rcx, [rbp+38h]; this
0x18005316b  lea     r8, aOnecoreBaseFli_103; "onecore\\base\\flighting\\flightsetting"...
0x180053172  mov     r9d, eax; char *
0x180053175  mov     edx, 29h ; ')'; void *
0x18005317a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005317f  mov     eax, edi
0x180053181  jmp     loc_180053278
0x180053186  mov     rax, [rsi]
0x180053189  lea     rdi, [r14+18h]
0x18005318d  mov     rcx, [rdi]; string
0x180053190  mov     r12, [rax+50h]
0x180053194  call    cs:__imp_WindowsDeleteString
0x18005319a  mov     [rdi], r13
0x18005319d  mov     rcx, rbx
0x1800531a0  mov     r15, cs:?s_pszJsonTagGuid@FileVerProvider@@0QEBGEB; ushort const * const FileVerProvider::s_pszJsonTagGuid
0x1800531a7  mov     [rbp+length], r13d
0x1800531ab  inc     rcx; unsigned __int64
0x1800531ae  cmp     [r15+rcx*2], r13w
0x1800531b3  jnz     short loc_1800531AB
0x1800531b5  lea     rdx, [rbp+length]; unsigned int *
0x1800531b9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800531be  test    eax, eax
0x1800531c0  jns     short loc_1800531D7
0x1800531c2  xor     r9d, r9d; lpArguments
0x1800531c5  xor     r8d, r8d; nNumberOfArguments
0x1800531c8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800531cd  lea     edx, [r9+1]; dwExceptionFlags
0x1800531d1  call    cs:__imp_RaiseException
0x1800531d7  mov     edx, [rbp+length]; length
0x1800531da  lea     r9, [rbp+string]; string
0x1800531de  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800531e2  mov     rcx, r15; sourceString
0x1800531e5  call    cs:__imp_WindowsCreateStringReference
0x1800531eb  mov     rdx, [rbp+string]
0x1800531ef  mov     r8, rdi
0x1800531f2  mov     rcx, rsi
0x1800531f5  mov     rax, r12
0x1800531f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531fd  shr     eax, 1Fh
0x180053200  xor     al, 1
0x180053202  mov     [rbp+length], r13d
0x180053206  mov     [r14+20h], al
0x18005320a  mov     rax, [rsi]
0x18005320d  mov     rdi, cs:?s_pszJsonTagExists@FileVerProvider@@0QEBGEB; ushort const * const FileVerProvider::s_pszJsonTagExists
0x180053214  mov     r15, [rax+60h]
0x180053218  inc     rbx
0x18005321b  cmp     [rdi+rbx*2], r13w
0x180053220  jnz     short loc_180053218
0x180053222  lea     rdx, [rbp+length]; unsigned int *
0x180053226  mov     rcx, rbx; unsigned __int64
0x180053229  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005322e  test    eax, eax
0x180053230  jns     short loc_180053247
0x180053232  xor     r9d, r9d; lpArguments
0x180053235  xor     r8d, r8d; nNumberOfArguments
0x180053238  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005323d  lea     edx, [r9+1]; dwExceptionFlags
0x180053241  call    cs:__imp_RaiseException
0x180053247  mov     edx, [rbp+length]; length
0x18005324a  lea     r9, [rbp+string]; string
0x18005324e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180053252  mov     rcx, rdi; sourceString
0x180053255  call    cs:__imp_WindowsCreateStringReference
0x18005325b  mov     rdx, [rbp+string]
0x18005325f  lea     r8, [r14+21h]
0x180053263  mov     rcx, rsi
0x180053266  mov     rax, r15
0x180053269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005326e  test    eax, eax
0x180053270  jns     short loc_180053276
0x180053272  mov     [r14+21h], r13b
0x180053276  xor     eax, eax
0x180053278  mov     rcx, [rbp+var_8]
0x18005327c  xor     rcx, rsp; StackCookie
0x18005327f  call    __security_check_cookie
0x180053284  mov     rbx, [rsp+50h+arg_10]
0x18005328c  add     rsp, 50h
0x180053290  pop     r15
0x180053292  pop     r14
0x180053294  pop     r13
0x180053296  pop     r12
0x180053298  pop     rdi
0x180053299  pop     rsi
0x18005329a  pop     rbp
0x18005329b  retn
```
