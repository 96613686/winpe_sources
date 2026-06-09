# std::_Func_impl_no_alloc__lambda_2f95d502a6b72396655f9d0e7f9ed0c1__void_unsigned_short_const___unsigned_short_const____FILETIME_const_&_::_Do_call

- ea: `0x180038a50`
- end: `0x180038afc`
- name: `std::_Func_impl_no_alloc__lambda_2f95d502a6b72396655f9d0e7f9ed0c1__void_unsigned_short_const___unsigned_short_const____FILETIME_const_&_::_Do_call`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003a00`
- `0x180038a50`
- `0x1800611f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038a91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038aca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038a91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038aca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180038a82`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180038a82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038ae3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038ae3`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x180038aac`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x180038aac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall std::_Func_impl_no_alloc__lambda_2f95d502a6b72396655f9d0e7f9ed0c1__void_unsigned_short_const___unsigned_short_const____FILETIME_const___::_Do_call(
        __int64 a1,
        const WCHAR **a2)
{
  const WCHAR *v3; // rcx
  HRESULT result; // eax
  HSTRING string; // [rsp+20h] [rbp-28h] BYREF
  PSID Sid; // [rsp+28h] [rbp-20h] BYREF

  v3 = *a2;
  string = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(v3, &Sid) )
  {
    WindowsDeleteString(string);
    string = 0;
    if ( (int)GetUserLanguagesForUser(Sid, 0, &string) >= 0 )
      bcp47::MultiStringToBcp47Tags(&string, *(_QWORD *)(a1 + 8));
  }
  result = WindowsDeleteString(string);
  string = 0;
  if ( Sid )
    return (unsigned int)LocalFree(Sid);
  return result;
}

```

## disassembly

```asm
0x180038a50  push    rbx
0x180038a52  sub     rsp, 40h
0x180038a56  mov     rax, cs:__security_cookie
0x180038a5d  xor     rax, rsp
0x180038a60  mov     [rsp+48h+var_18], rax
0x180038a65  mov     rbx, rcx
0x180038a68  mov     rcx, [rdx]; StringSid
0x180038a6b  mov     [rsp+48h+string], 0
0x180038a74  mov     [rsp+48h+Sid], 0
0x180038a7d  lea     rdx, [rsp+48h+Sid]; Sid
0x180038a82  call    cs:__imp_ConvertStringSidToSidW
0x180038a88  test    eax, eax
0x180038a8a  jz      short loc_180038AC5
0x180038a8c  mov     rcx, [rsp+48h+string]; string
0x180038a91  call    cs:__imp_WindowsDeleteString
0x180038a97  mov     [rsp+48h+string], 0
0x180038aa0  xor     edx, edx
0x180038aa2  lea     r8, [rsp+48h+string]
0x180038aa7  mov     rcx, [rsp+48h+Sid]
0x180038aac  call    cs:__imp_GetUserLanguagesForUser
0x180038ab2  test    eax, eax
0x180038ab4  js      short loc_180038AC5
0x180038ab6  mov     rdx, [rbx+8]
0x180038aba  lea     rcx, [rsp+48h+string]
0x180038abf  call    ?MultiStringToBcp47Tags@bcp47@@YAXAEBVHString@Wrappers@WRL@Microsoft@@PEAV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@_N@Z; bcp47::MultiStringToBcp47Tags(Microsoft::WRL::Wrappers::HString const &,std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> *,bool)
0x180038ac4  nop
0x180038ac5  mov     rcx, [rsp+48h+string]; string
0x180038aca  call    cs:__imp_WindowsDeleteString
0x180038ad0  mov     [rsp+48h+string], 0
0x180038ad9  mov     rcx, [rsp+48h+Sid]; hMem
0x180038ade  test    rcx, rcx
0x180038ae1  jz      short loc_180038AE9
0x180038ae3  call    cs:__imp_LocalFree
0x180038ae9  mov     rcx, [rsp+48h+var_18]
0x180038aee  xor     rcx, rsp; StackCookie
0x180038af1  call    __security_check_cookie
0x180038af6  add     rsp, 40h
0x180038afa  pop     rbx
0x180038afb  retn
```
