# ConvertStringScopeToScope(Windows::Internal::String const &,Windows::Security::Authentication::Web::Provider::WebAccountScope &)

- ea: `0x180048ab4`
- end: `0x180048bcc`
- name: `?ConvertStringScopeToScope@@YAJAEBVString@Internal@Windows@@AEAW4WebAccountScope@Provider@Web@Authentication@Security@3@@Z`
- size: `280`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, enum Windows::Security::Authentication::Web::Provider::WebAccountScope *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a790`

## callees

- `0x180048ab4`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048ba0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048bc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048ba0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180048b1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180048b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180048b1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180048b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180048add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180048add`

## pseudocode

```c
__int64 __fastcall ConvertStringScopeToScope(
        HSTRING *a1,
        enum Windows::Security::Authentication::Web::Provider::WebAccountScope *a2)
{
  HSTRING v4; // rdx
  HSTRING v6; // rdx
  INT32 result; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF

  if ( !WindowsIsStringEmpty(*a1) )
  {
    if ( WindowsCreateStringReference(L"Scope_PerUser", 0xDu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = *a1;
    result = 0;
    WindowsCompareStringOrdinal(string, v4, &result);
    if ( !result )
    {
      *(_DWORD *)a2 = 0;
      return 0;
    }
    if ( WindowsCreateStringReference(L"Scope_PerApp", 0xCu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = *a1;
    result = 0;
    WindowsCompareStringOrdinal(string, v6, &result);
    if ( !result )
    {
      *(_DWORD *)a2 = 1;
      return 0;
    }
  }
  return 2147942413LL;
}

```

## disassembly

```asm
0x180048ab4  mov     [rsp-8+arg_10], rbx
0x180048ab9  mov     [rsp-8+arg_18], rdi
0x180048abe  push    rbp
0x180048abf  mov     rbp, rsp
0x180048ac2  sub     rsp, 50h
0x180048ac6  mov     rax, cs:__security_cookie
0x180048acd  xor     rax, rsp
0x180048ad0  mov     [rbp+var_8], rax
0x180048ad4  mov     rdi, rcx
0x180048ad7  mov     rbx, rdx
0x180048ada  mov     rcx, [rcx]; string
0x180048add  call    cs:__imp_WindowsIsStringEmpty
0x180048ae3  test    eax, eax
0x180048ae5  jnz     loc_180048BAB
0x180048aeb  lea     r9, [rbp+string]; string
0x180048aef  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180048af3  lea     edx, [rax+0Dh]; length
0x180048af6  lea     rcx, aScopePeruser; "Scope_PerUser"
0x180048afd  call    cs:__imp_WindowsCreateStringReference
0x180048b03  test    eax, eax
0x180048b05  js      loc_180048B91
0x180048b0b  mov     rdx, [rdi]; string2
0x180048b0e  lea     r8, [rbp+result]; result
0x180048b12  mov     rcx, [rbp+string]; string1
0x180048b16  mov     [rbp+result], 0
0x180048b1d  call    cs:__imp_WindowsCompareStringOrdinal
0x180048b23  cmp     [rbp+result], 0
0x180048b27  jnz     short loc_180048B4D
0x180048b29  mov     dword ptr [rbx], 0
0x180048b2f  xor     eax, eax
0x180048b31  mov     rcx, [rbp+var_8]
0x180048b35  xor     rcx, rsp; StackCookie
0x180048b38  call    __security_check_cookie
0x180048b3d  mov     rbx, [rsp+50h+arg_10]
0x180048b42  mov     rdi, [rsp+50h+arg_18]
0x180048b47  add     rsp, 50h
0x180048b4b  pop     rbp
0x180048b4c  retn
0x180048b4d  lea     r9, [rbp+string]; string
0x180048b51  mov     edx, 0Ch; length
0x180048b56  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180048b5a  lea     rcx, aScopePerapp; "Scope_PerApp"
0x180048b61  call    cs:__imp_WindowsCreateStringReference
0x180048b67  test    eax, eax
0x180048b69  js      short loc_180048BB5
0x180048b6b  mov     rdx, [rdi]; string2
0x180048b6e  lea     r8, [rbp+result]; result
0x180048b72  mov     rcx, [rbp+string]; string1
0x180048b76  mov     [rbp+result], 0
0x180048b7d  call    cs:__imp_WindowsCompareStringOrdinal
0x180048b83  cmp     [rbp+result], 0
0x180048b87  jnz     short loc_180048BAB
0x180048b89  mov     dword ptr [rbx], 1
0x180048b8f  jmp     short loc_180048B2F
0x180048b91  xor     r9d, r9d; lpArguments
0x180048b94  xor     r8d, r8d; nNumberOfArguments
0x180048b97  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048b9c  lea     edx, [r9+1]; dwExceptionFlags
0x180048ba0  call    cs:__imp_RaiseException
0x180048ba6  jmp     loc_180048B0B
0x180048bab  mov     eax, 8007000Dh
0x180048bb0  jmp     loc_180048B31
0x180048bb5  xor     r9d, r9d; lpArguments
0x180048bb8  xor     r8d, r8d; nNumberOfArguments
0x180048bbb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048bc0  lea     edx, [r9+1]; dwExceptionFlags
0x180048bc4  call    cs:__imp_RaiseException
0x180048bca  jmp     short loc_180048B6B
```
