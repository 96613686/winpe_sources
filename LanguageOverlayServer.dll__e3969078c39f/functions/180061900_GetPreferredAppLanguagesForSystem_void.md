# GetPreferredAppLanguagesForSystem(void)

- ea: `0x180061900`
- end: `0x180061992`
- name: `?GetPreferredAppLanguagesForSystem@@YA?AV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@XZ`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019cdc`

## callees

- `0x180012a98`
- `0x180035810`
- `0x1800611f4`
- `0x180061900`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006196e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006196e`
- `Bcp47Langs!GetUserLanguagesForAllUsers` at `0x18006193c`
- `Bcp47Langs!GetUserLanguagesForAllUsers` at `0x18006193c`

## string_xrefs

- `0x180061980`: `onecore\base\languageoverlay\common\languageutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetPreferredAppLanguagesForSystem(__int64 a1)
{
  int UserLanguagesForAllUsers; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  UserLanguagesForAllUsers = GetUserLanguagesForAllUsers(0, &string, 0, 0);
  if ( UserLanguagesForAllUsers < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\languageutils.cpp",
      (const char *)(unsigned int)UserLanguagesForAllUsers,
      0);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(a1);
  bcp47::MultiStringToBcp47Tags(&string, a1);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x180061900  mov     [rsp+arg_0], rcx
0x180061905  push    rbx
0x180061906  sub     rsp, 30h
0x18006190a  mov     rbx, rcx
0x18006190d  mov     [rsp+38h+var_18], 0; int
0x180061915  mov     [rsp+38h+string], 0
0x18006191e  xor     ecx, ecx; string
0x180061920  call    cs:__imp_WindowsDeleteString
0x180061926  mov     [rsp+38h+string], 0
0x18006192f  xor     ecx, ecx
0x180061931  xor     r9d, r9d
0x180061934  xor     r8d, r8d
0x180061937  lea     rdx, [rsp+38h+string]
0x18006193c  call    cs:__imp_GetUserLanguagesForAllUsers
0x180061942  mov     rcx, [rsp+38h]; this
0x180061947  test    eax, eax
0x180061949  js      short loc_18006197D
0x18006194b  mov     rcx, rbx
0x18006194e  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180061953  mov     [rsp+38h+var_18], 1
0x18006195b  mov     rdx, rbx
0x18006195e  lea     rcx, [rsp+38h+string]
0x180061963  call    ?MultiStringToBcp47Tags@bcp47@@YAXAEBVHString@Wrappers@WRL@Microsoft@@PEAV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@_N@Z; bcp47::MultiStringToBcp47Tags(Microsoft::WRL::Wrappers::HString const &,std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> *,bool)
0x180061968  nop
0x180061969  mov     rcx, [rsp+38h+string]; string
0x18006196e  call    cs:__imp_WindowsDeleteString
0x180061974  mov     rax, rbx
0x180061977  add     rsp, 30h
0x18006197b  pop     rbx
0x18006197c  retn
0x18006197d  mov     r9d, eax; char *
0x180061980  lea     r8, aOnecoreBaseLan_11; "onecore\\base\\languageoverlay\\common"...
0x180061987  mov     edx, 9Eh; void *
0x18006198c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
