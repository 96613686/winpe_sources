# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::ConvertStringTypeToType(Windows::Internal::String const &)

- ea: `0x180044e2c`
- end: `0x18004503c`
- name: `?ConvertStringTypeToType@JsonObjectHeader@TokenBroker@Authentication@Security@Internal@Windows@@SA?AW4SerializedObjectType@23456@AEBVString@56@@Z`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800792b0`

## callees

- `0x180044e2c`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044f59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044f6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044f84`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045016`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004502a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044f59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044f6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044f84`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045016`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004502a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044fa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044fa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044fbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044fbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180044ff3`

## string_xrefs

- `0x180044e61`: `TokenRequest`
- `0x180044eb6`: `TokenResponse`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::ConvertStringTypeToType(
        HSTRING *a1)
{
  HSTRING v1; // rdi
  HSTRING v3; // rdi
  HSTRING v4; // rdi
  HSTRING v6; // rdi
  HSTRING v7; // rbx
  INT32 result; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF

  v1 = *a1;
  result = 0;
  if ( WindowsCreateStringReference(L"TokenRequest", 0xCu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v1, &result);
  if ( !result )
    return 2;
  v3 = *a1;
  if ( WindowsCreateStringReference(L"TokenResponse", 0xDu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v3, &result);
  if ( !result )
    return 3;
  v4 = *a1;
  if ( WindowsCreateStringReference(L"AppAccountInformation", 0x15u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v4, &result);
  if ( !result )
    return 1;
  v6 = *a1;
  if ( WindowsCreateStringReference(L"Diagnostics", 0xBu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v6, &result);
  if ( !result )
    return 4;
  v7 = *a1;
  if ( WindowsCreateStringReference(L"SystemAccountInformation", 0x18u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCompareStringOrdinal(string, v7, &result);
  return result != 0 ? 5 : 0;
}

```

## disassembly

```asm
0x180044e2c  mov     [rsp-18h+arg_8], rbx
0x180044e31  mov     [rsp-18h+arg_10], rdi
0x180044e36  push    rbp
0x180044e37  push    r14
0x180044e39  push    r15
0x180044e3b  mov     rbp, rsp
0x180044e3e  sub     rsp, 50h
0x180044e42  mov     rax, cs:__security_cookie
0x180044e49  xor     rax, rsp
0x180044e4c  mov     [rbp+var_8], rax
0x180044e50  mov     rdi, [rcx]
0x180044e53  lea     r9, [rbp+string]; string
0x180044e57  mov     rbx, rcx
0x180044e5a  mov     [rbp+result], 0
0x180044e61  lea     rcx, aTokenrequest; "TokenRequest"
0x180044e68  mov     edx, 0Ch; length
0x180044e6d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180044e71  call    cs:__imp_WindowsCreateStringReference
0x180044e77  mov     r14d, 1
0x180044e7d  mov     r15d, 0C000000Dh
0x180044e83  test    eax, eax
0x180044e85  js      loc_180044F78
0x180044e8b  mov     rcx, [rbp+string]; string1
0x180044e8f  lea     r8, [rbp+result]; result
0x180044e93  mov     rdx, rdi; string2
0x180044e96  call    cs:__imp_WindowsCompareStringOrdinal
0x180044e9c  cmp     [rbp+result], 0
0x180044ea0  jz      loc_180044F3F
0x180044ea6  mov     rdi, [rbx]
0x180044ea9  lea     r9, [rbp+string]; string
0x180044ead  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180044eb1  mov     edx, 0Dh; length
0x180044eb6  lea     rcx, aTokenresponse; "TokenResponse"
0x180044ebd  call    cs:__imp_WindowsCreateStringReference
0x180044ec3  test    eax, eax
0x180044ec5  js      loc_180044F61
0x180044ecb  mov     rcx, [rbp+string]; string1
0x180044ecf  lea     r8, [rbp+result]; result
0x180044ed3  mov     rdx, rdi; string2
0x180044ed6  call    cs:__imp_WindowsCompareStringOrdinal
0x180044edc  cmp     [rbp+result], 0
0x180044ee0  jz      short loc_180044F46
0x180044ee2  mov     rdi, [rbx]
0x180044ee5  lea     r9, [rbp+string]; string
0x180044ee9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180044eed  mov     edx, 15h; length
0x180044ef2  lea     rcx, aAppaccountinfo; "AppAccountInformation"
0x180044ef9  call    cs:__imp_WindowsCreateStringReference
0x180044eff  test    eax, eax
0x180044f01  js      short loc_180044F4D
0x180044f03  mov     rcx, [rbp+string]; string1
0x180044f07  lea     r8, [rbp+result]; result
0x180044f0b  mov     rdx, rdi; string2
0x180044f0e  call    cs:__imp_WindowsCompareStringOrdinal
0x180044f14  cmp     [rbp+result], 0
0x180044f18  jnz     short loc_180044F8F
0x180044f1a  mov     eax, r14d
0x180044f1d  mov     rcx, [rbp+var_8]
0x180044f21  xor     rcx, rsp; StackCookie
0x180044f24  call    __security_check_cookie
0x180044f29  lea     r11, [rsp+50h+var_s0]
0x180044f2e  mov     rbx, [r11+28h]
0x180044f32  mov     rdi, [r11+30h]
0x180044f36  mov     rsp, r11
0x180044f39  pop     r15
0x180044f3b  pop     r14
0x180044f3d  pop     rbp
0x180044f3e  retn
0x180044f3f  mov     eax, 2
0x180044f44  jmp     short loc_180044F1D
0x180044f46  mov     eax, 3
0x180044f4b  jmp     short loc_180044F1D
0x180044f4d  xor     r9d, r9d; lpArguments
0x180044f50  xor     r8d, r8d; nNumberOfArguments
0x180044f53  mov     edx, r14d; dwExceptionFlags
0x180044f56  mov     ecx, r15d; dwExceptionCode
0x180044f59  call    cs:__imp_RaiseException
0x180044f5f  jmp     short loc_180044F03
0x180044f61  xor     r9d, r9d; lpArguments
0x180044f64  xor     r8d, r8d; nNumberOfArguments
0x180044f67  mov     edx, r14d; dwExceptionFlags
0x180044f6a  mov     ecx, r15d; dwExceptionCode
0x180044f6d  call    cs:__imp_RaiseException
0x180044f73  jmp     loc_180044ECB
0x180044f78  xor     r9d, r9d; lpArguments
0x180044f7b  xor     r8d, r8d; nNumberOfArguments
0x180044f7e  mov     edx, r14d; dwExceptionFlags
0x180044f81  mov     ecx, r15d; dwExceptionCode
0x180044f84  call    cs:__imp_RaiseException
0x180044f8a  jmp     loc_180044E8B
0x180044f8f  mov     rdi, [rbx]
0x180044f92  lea     r9, [rbp+string]; string
0x180044f96  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180044f9a  mov     edx, 0Bh; length
0x180044f9f  lea     rcx, aDiagnostics; "Diagnostics"
0x180044fa6  call    cs:__imp_WindowsCreateStringReference
0x180044fac  test    eax, eax
0x180044fae  js      short loc_18004500A
0x180044fb0  mov     rcx, [rbp+string]; string1
0x180044fb4  lea     r8, [rbp+result]; result
0x180044fb8  mov     rdx, rdi; string2
0x180044fbb  call    cs:__imp_WindowsCompareStringOrdinal
0x180044fc1  cmp     [rbp+result], 0
0x180044fc5  jz      short loc_180045032
0x180044fc7  mov     rbx, [rbx]
0x180044fca  lea     r9, [rbp+string]; string
0x180044fce  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180044fd2  mov     edx, 18h; length
0x180044fd7  lea     rcx, aSystemaccounti; "SystemAccountInformation"
0x180044fde  call    cs:__imp_WindowsCreateStringReference
0x180044fe4  test    eax, eax
0x180044fe6  js      short loc_18004501E
0x180044fe8  mov     rcx, [rbp+string]; string1
0x180044fec  lea     r8, [rbp+result]; result
0x180044ff0  mov     rdx, rbx; string2
0x180044ff3  call    cs:__imp_WindowsCompareStringOrdinal
0x180044ff9  xor     eax, eax
0x180044ffb  sub     eax, [rbp+result]
0x180044ffe  neg     eax
0x180045000  sbb     eax, eax
0x180045002  and     eax, 5
0x180045005  jmp     loc_180044F1D
0x18004500a  xor     r9d, r9d; lpArguments
0x18004500d  xor     r8d, r8d; nNumberOfArguments
0x180045010  mov     edx, r14d; dwExceptionFlags
0x180045013  mov     ecx, r15d; dwExceptionCode
0x180045016  call    cs:__imp_RaiseException
0x18004501c  jmp     short loc_180044FB0
0x18004501e  xor     r9d, r9d; lpArguments
0x180045021  xor     r8d, r8d; nNumberOfArguments
0x180045024  mov     edx, r14d; dwExceptionFlags
0x180045027  mov     ecx, r15d; dwExceptionCode
0x18004502a  call    cs:__imp_RaiseException
0x180045030  jmp     short loc_180044FE8
0x180045032  mov     eax, 4
0x180045037  jmp     loc_180044F1D
```
