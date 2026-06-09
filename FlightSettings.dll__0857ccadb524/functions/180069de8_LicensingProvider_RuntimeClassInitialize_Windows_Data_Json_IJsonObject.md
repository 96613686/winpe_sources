# LicensingProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x180069de8`
- end: `0x180069ed4`
- name: `?RuntimeClassInitialize@LicensingProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(LicensingProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800472d0`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180069de8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069e5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069e5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069e1a`

## string_xrefs

- `0x180069e98`: `onecore\base\flighting\flightsettings\broker\libs\ctac\licensingprovider.cpp`

## pseudocode

```c
__int64 __fastcall LicensingProvider::RuntimeClassInitialize(
        HSTRING *this,
        struct Windows::Data::Json::IJsonObject *a2)
{
  _QWORD *v2; // rdi
  __int64 (__fastcall *v4)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD *); // rbp
  unsigned __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  UINT32 length; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = this + 2;
  v4 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, _QWORD *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(this[2]);
  *v2 = 0;
  v5 = -1;
  length = 0;
  do
    ++v5;
  while ( LicensingProvider::s_pszJsonTagPolicyName[v5] );
  if ( (int)ULongLongToUInt(v5, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(LicensingProvider::s_pszJsonTagPolicyName, length, &hstringHeader, &string);
  v6 = v4(a2, string, v2);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\licensingprovider.cpp",
    (const char *)(unsigned int)v6,
    length);
  return v7;
}

```

## disassembly

```asm
0x180069de8  mov     [rsp+arg_10], rbx
0x180069ded  mov     [rsp+arg_18], rbp
0x180069df2  push    rsi
0x180069df3  push    rdi
0x180069df4  push    r14
0x180069df6  sub     rsp, 50h
0x180069dfa  mov     rax, cs:__security_cookie
0x180069e01  xor     rax, rsp
0x180069e04  mov     [rsp+68h+var_20], rax
0x180069e09  mov     rax, [rdx]
0x180069e0c  lea     rdi, [rcx+10h]
0x180069e10  mov     rcx, [rdi]; string
0x180069e13  mov     rsi, rdx
0x180069e16  mov     rbp, [rax+50h]
0x180069e1a  call    cs:__imp_WindowsDeleteString
0x180069e20  xor     r14d, r14d
0x180069e23  mov     [rdi], r14
0x180069e26  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180069e2a  mov     rbx, cs:?s_pszJsonTagPolicyName@LicensingProvider@@0QEBGEB; ushort const * const LicensingProvider::s_pszJsonTagPolicyName
0x180069e31  mov     [rsp+68h+length], r14d; int
0x180069e36  inc     rcx; unsigned __int64
0x180069e39  cmp     [rbx+rcx*2], r14w
0x180069e3e  jnz     short loc_180069E36
0x180069e40  lea     rdx, [rsp+68h+length]; unsigned int *
0x180069e45  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180069e4a  test    eax, eax
0x180069e4c  jns     short loc_180069E63
0x180069e4e  xor     r9d, r9d; lpArguments
0x180069e51  xor     r8d, r8d; nNumberOfArguments
0x180069e54  mov     ecx, 0C000000Dh; dwExceptionCode
0x180069e59  lea     edx, [r9+1]; dwExceptionFlags
0x180069e5d  call    cs:__imp_RaiseException
0x180069e63  mov     edx, [rsp+68h+length]; length
0x180069e67  lea     r9, [rsp+68h+string]; string
0x180069e6c  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180069e71  mov     rcx, rbx; sourceString
0x180069e74  call    cs:__imp_WindowsCreateStringReference
0x180069e7a  mov     rdx, [rsp+68h+string]
0x180069e7f  mov     r8, rdi
0x180069e82  mov     rcx, rsi
0x180069e85  mov     rax, rbp
0x180069e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e8d  mov     ebx, eax
0x180069e8f  test    eax, eax
0x180069e91  jns     short loc_180069EB0
0x180069e93  mov     rcx, [rsp+68h]; this
0x180069e98  lea     r8, aOnecoreBaseFli_81; "onecore\\base\\flighting\\flightsetting"...
0x180069e9f  mov     r9d, eax; char *
0x180069ea2  mov     edx, 25h ; '%'; void *
0x180069ea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069eac  mov     eax, ebx
0x180069eae  jmp     short loc_180069EB2
0x180069eb0  xor     eax, eax
0x180069eb2  mov     rcx, [rsp+68h+var_20]
0x180069eb7  xor     rcx, rsp; StackCookie
0x180069eba  call    __security_check_cookie
0x180069ebf  lea     r11, [rsp+68h+var_18]
0x180069ec4  mov     rbx, [r11+30h]
0x180069ec8  mov     rbp, [r11+38h]
0x180069ecc  mov     rsp, r11
0x180069ecf  pop     r14
0x180069ed1  pop     rdi
0x180069ed2  pop     rsi
0x180069ed3  retn
```
