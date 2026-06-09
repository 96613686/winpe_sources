# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::ConvertStringTypeToType(Windows::Internal::String const &)

- ea: `0x18003e2f0`
- end: `0x18003e516`
- name: `?ConvertStringTypeToType@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@CA?AW4SerializedPropertyType@23456@AEBVString@56@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a250`

## callees

- `0x18003e2f0`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e450`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e46b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e490`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e4f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e50b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e450`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e46b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e490`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e4f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e50b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e3cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e3cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e34a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e3a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e3e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e4c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e34a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e3a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e3e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003e4c7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::ConvertStringTypeToType(
        HSTRING *a1)
{
  HSTRING v1; // rbx
  __int64 v3; // rax
  HSTRING v4; // rbx
  HSTRING v5; // rbx
  HSTRING v6; // rbx
  HSTRING v7; // rbx
  INT32 result; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF

  v1 = *a1;
  result = 0;
  if ( WindowsCreateStringReference(L"InlineString", 0xCu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v1, &result);
  if ( !result )
    return 0;
  v4 = *a1;
  if ( WindowsCreateStringReference(L"InlineStringArray", 0x11u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v4, &result);
  if ( !result )
    return 1;
  v5 = *a1;
  if ( WindowsCreateStringReference(L"InlineBytes", 0xBu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v5, &result);
  if ( !result )
    return 2;
  v6 = *a1;
  if ( WindowsCreateStringReference(L"Boolean", 7u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v6, &result);
  if ( !result )
    return 4;
  v7 = *a1;
  if ( WindowsCreateStringReference(L"IndirectBytes", 0xDu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v7, &result);
  v3 = 5;
  if ( !result )
    return 3;
  return v3;
}

```

## disassembly

```asm
0x18003e2f0  mov     [rsp-8+arg_8], rbx
0x18003e2f5  mov     [rsp-8+arg_10], rdi
0x18003e2fa  push    rbp
0x18003e2fb  mov     rbp, rsp
0x18003e2fe  sub     rsp, 50h
0x18003e302  mov     rax, cs:__security_cookie
0x18003e309  xor     rax, rsp
0x18003e30c  mov     [rbp+var_8], rax
0x18003e310  mov     rbx, [rcx]
0x18003e313  lea     r9, [rbp+string]; string
0x18003e317  mov     rdi, rcx
0x18003e31a  mov     [rbp+result], 0
0x18003e321  lea     rcx, aInlinestring; "InlineString"
0x18003e328  mov     edx, 0Ch; length
0x18003e32d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003e331  call    cs:__imp_WindowsCreateStringReference
0x18003e337  test    eax, eax
0x18003e339  js      loc_18003E440
0x18003e33f  mov     rcx, [rbp+string]; string1
0x18003e343  lea     r8, [rbp+result]; result
0x18003e347  mov     rdx, rbx; string2
0x18003e34a  call    cs:__imp_WindowsCompareStringOrdinal
0x18003e350  cmp     [rbp+result], 0
0x18003e354  jnz     short loc_18003E374
0x18003e356  xor     eax, eax
0x18003e358  mov     rcx, [rbp+var_8]
0x18003e35c  xor     rcx, rsp; StackCookie
0x18003e35f  call    __security_check_cookie
0x18003e364  mov     rbx, [rsp+50h+arg_8]
0x18003e369  mov     rdi, [rsp+50h+arg_10]
0x18003e36e  add     rsp, 50h
0x18003e372  pop     rbp
0x18003e373  retn
0x18003e374  mov     rbx, [rdi]
0x18003e377  lea     r9, [rbp+string]; string
0x18003e37b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003e37f  mov     edx, 11h; length
0x18003e384  lea     rcx, aInlinestringar; "InlineStringArray"
0x18003e38b  call    cs:__imp_WindowsCreateStringReference
0x18003e391  test    eax, eax
0x18003e393  js      loc_18003E45B
0x18003e399  mov     rcx, [rbp+string]; string1
0x18003e39d  lea     r8, [rbp+result]; result
0x18003e3a1  mov     rdx, rbx; string2
0x18003e3a4  call    cs:__imp_WindowsCompareStringOrdinal
0x18003e3aa  cmp     [rbp+result], 0
0x18003e3ae  jz      loc_18003E476
0x18003e3b4  mov     rbx, [rdi]
0x18003e3b7  lea     r9, [rbp+string]; string
0x18003e3bb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003e3bf  mov     edx, 0Bh; length
0x18003e3c4  lea     rcx, aInlinebytes; "InlineBytes"
0x18003e3cb  call    cs:__imp_WindowsCreateStringReference
0x18003e3d1  test    eax, eax
0x18003e3d3  js      loc_18003E480
0x18003e3d9  mov     rcx, [rbp+string]; string1
0x18003e3dd  lea     r8, [rbp+result]; result
0x18003e3e1  mov     rdx, rbx; string2
0x18003e3e4  call    cs:__imp_WindowsCompareStringOrdinal
0x18003e3ea  cmp     [rbp+result], 0
0x18003e3ee  jnz     short loc_18003E3FA
0x18003e3f0  mov     eax, 2
0x18003e3f5  jmp     loc_18003E358
0x18003e3fa  mov     rbx, [rdi]
0x18003e3fd  lea     r9, [rbp+string]; string
0x18003e401  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003e405  mov     edx, 7; length
0x18003e40a  lea     rcx, aBoolean; "Boolean"
0x18003e411  call    cs:__imp_WindowsCreateStringReference
0x18003e417  test    eax, eax
0x18003e419  js      loc_18003E4FB
0x18003e41f  mov     rcx, [rbp+string]; string1
0x18003e423  lea     r8, [rbp+result]; result
0x18003e427  mov     rdx, rbx; string2
0x18003e42a  call    cs:__imp_WindowsCompareStringOrdinal
0x18003e430  cmp     [rbp+result], 0
0x18003e434  jnz     short loc_18003E49B
0x18003e436  mov     eax, 4
0x18003e43b  jmp     loc_18003E358
0x18003e440  xor     r9d, r9d; lpArguments
0x18003e443  xor     r8d, r8d; nNumberOfArguments
0x18003e446  mov     edx, 1; dwExceptionFlags
0x18003e44b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e450  call    cs:__imp_RaiseException
0x18003e456  jmp     loc_18003E33F
0x18003e45b  xor     r9d, r9d; lpArguments
0x18003e45e  xor     r8d, r8d; nNumberOfArguments
0x18003e461  mov     edx, 1; dwExceptionFlags
0x18003e466  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e46b  call    cs:__imp_RaiseException
0x18003e471  jmp     loc_18003E399
0x18003e476  mov     eax, 1
0x18003e47b  jmp     loc_18003E358
0x18003e480  xor     r9d, r9d; lpArguments
0x18003e483  xor     r8d, r8d; nNumberOfArguments
0x18003e486  mov     edx, 1; dwExceptionFlags
0x18003e48b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e490  call    cs:__imp_RaiseException
0x18003e496  jmp     loc_18003E3D9
0x18003e49b  mov     rbx, [rdi]
0x18003e49e  lea     r9, [rbp+string]; string
0x18003e4a2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003e4a6  mov     edx, 0Dh; length
0x18003e4ab  lea     rcx, aIndirectbytes; "IndirectBytes"
0x18003e4b2  call    cs:__imp_WindowsCreateStringReference
0x18003e4b8  test    eax, eax
0x18003e4ba  js      short loc_18003E4E3
0x18003e4bc  mov     rcx, [rbp+string]; string1
0x18003e4c0  lea     r8, [rbp+result]; result
0x18003e4c4  mov     rdx, rbx; string2
0x18003e4c7  call    cs:__imp_WindowsCompareStringOrdinal
0x18003e4cd  cmp     [rbp+result], 0
0x18003e4d1  mov     eax, 5
0x18003e4d6  mov     ecx, 3
0x18003e4db  cmovz   eax, ecx
0x18003e4de  jmp     loc_18003E358
0x18003e4e3  xor     r9d, r9d; lpArguments
0x18003e4e6  xor     r8d, r8d; nNumberOfArguments
0x18003e4e9  mov     edx, 1; dwExceptionFlags
0x18003e4ee  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e4f3  call    cs:__imp_RaiseException
0x18003e4f9  jmp     short loc_18003E4BC
0x18003e4fb  xor     r9d, r9d; lpArguments
0x18003e4fe  xor     r8d, r8d; nNumberOfArguments
0x18003e501  mov     edx, 1; dwExceptionFlags
0x18003e506  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e50b  call    cs:__imp_RaiseException
0x18003e511  jmp     loc_18003E41F
```
