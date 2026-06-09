# CUserInformationStatics::_ValidateCallerCapability(bool *)

- ea: `0x1800c8d04`
- end: `0x1800c8e06`
- name: `?_ValidateCallerCapability@CUserInformationStatics@@AEAAJPEA_N@Z`
- size: `258`
- prototype: `__int64 __fastcall(CUserInformationStatics *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800c24b0`
- `0x1800c2990`
- `0x1800c2c90`

## callees

- `0x180043414`
- `0x180050ba0`
- `0x1800c8d04`
- `0x1800d5060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8d85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8dd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8d85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8dbf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c8de6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c8de6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserInformationStatics::_ValidateCallerCapability(CUserInformationStatics *this, bool *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  int v6; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v6 = 0;
  v3 = CheckAndGetCapability(WinCapabilityEnterpriseAuthenticationSid, a2, &v6, 0);
  if ( v3 >= 0 )
  {
    if ( v6 )
    {
      v3 = _ValidatePrivacyAccess();
      if ( v3 < 0 )
      {
        *a2 = 1;
        return 0;
      }
      return (unsigned int)v3;
    }
    v3 = -2147024891;
  }
  if ( v3 == -2147024891 )
  {
    if ( WindowsCreateStringReference(
           L"Caller does not have the EnterpriseAuthentication capability.",
           0x3Du,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = 2147942405LL;
LABEL_14:
    RoOriginateError(v4, string);
    return (unsigned int)v3;
  }
  if ( v3 < 0 )
  {
    if ( WindowsCreateStringReference(L"Unable to check for capability.", 0x1Fu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = (unsigned int)v3;
    goto LABEL_14;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c8d04  mov     [rsp+arg_0], rbx
0x1800c8d09  push    rdi
0x1800c8d0a  sub     rsp, 50h
0x1800c8d0e  mov     rax, cs:__security_cookie
0x1800c8d15  xor     rax, rsp
0x1800c8d18  mov     [rsp+58h+var_10], rax
0x1800c8d1d  mov     rdi, rdx
0x1800c8d20  mov     byte ptr [rdx], 0
0x1800c8d23  mov     [rsp+58h+var_38], 0
0x1800c8d2b  xor     r9d, r9d; void **
0x1800c8d2e  lea     r8, [rsp+58h+var_38]; int *
0x1800c8d33  lea     ecx, [r9+5Dh]; WellKnownSidType
0x1800c8d37  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x1800c8d3c  mov     ebx, eax
0x1800c8d3e  test    eax, eax
0x1800c8d40  js      short loc_1800C8D4E
0x1800c8d42  cmp     [rsp+58h+var_38], 0
0x1800c8d47  jnz     short loc_1800C8D93
0x1800c8d49  mov     ebx, 80070005h
0x1800c8d4e  cmp     ebx, 80070005h
0x1800c8d54  jnz     short loc_1800C8DA5
0x1800c8d56  lea     r9, [rsp+58h+string]; string
0x1800c8d5b  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800c8d60  mov     edx, 3Dh ; '='; length
0x1800c8d65  lea     rcx, aCallerDoesNotH; "Caller does not have the EnterpriseAuth"...
0x1800c8d6c  call    cs:__imp_WindowsCreateStringReference
0x1800c8d72  test    eax, eax
0x1800c8d74  jns     short loc_1800C8D8C
0x1800c8d76  xor     r9d, r9d; lpArguments
0x1800c8d79  xor     r8d, r8d; nNumberOfArguments
0x1800c8d7c  lea     edx, [r9+1]; dwExceptionFlags
0x1800c8d80  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c8d85  call    cs:__imp_RaiseException
0x1800c8d8b  nop
0x1800c8d8c  mov     ecx, 80070005h
0x1800c8d91  jmp     short loc_1800C8DE1
0x1800c8d93  call    ?_ValidatePrivacyAccess@@YAJXZ; _ValidatePrivacyAccess(void)
0x1800c8d98  mov     ebx, eax
0x1800c8d9a  test    eax, eax
0x1800c8d9c  jns     short loc_1800C8DEC
0x1800c8d9e  mov     byte ptr [rdi], 1
0x1800c8da1  xor     ebx, ebx
0x1800c8da3  jmp     short loc_1800C8DEC
0x1800c8da5  test    ebx, ebx
0x1800c8da7  jns     short loc_1800C8DEC
0x1800c8da9  lea     r9, [rsp+58h+string]; string
0x1800c8dae  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800c8db3  mov     edx, 1Fh; length
0x1800c8db8  lea     rcx, aUnableToCheckF; "Unable to check for capability."
0x1800c8dbf  call    cs:__imp_WindowsCreateStringReference
0x1800c8dc5  test    eax, eax
0x1800c8dc7  jns     short loc_1800C8DDF
0x1800c8dc9  xor     r9d, r9d; lpArguments
0x1800c8dcc  xor     r8d, r8d; nNumberOfArguments
0x1800c8dcf  lea     edx, [r9+1]; dwExceptionFlags
0x1800c8dd3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c8dd8  call    cs:__imp_RaiseException
0x1800c8dde  nop
0x1800c8ddf  mov     ecx, ebx
0x1800c8de1  mov     rdx, [rsp+58h+string]
0x1800c8de6  call    cs:__imp_RoOriginateError
0x1800c8dec  mov     eax, ebx
0x1800c8dee  mov     rcx, [rsp+58h+var_10]
0x1800c8df3  xor     rcx, rsp; StackCookie
0x1800c8df6  call    __security_check_cookie
0x1800c8dfb  mov     rbx, [rsp+58h+arg_0]
0x1800c8e00  add     rsp, 50h
0x1800c8e04  pop     rdi
0x1800c8e05  retn
```
