# GetPreferredLanguagesForUser(void *)

- ea: `0x1800367f4`
- end: `0x180036935`
- name: `?GetPreferredLanguagesForUser@@YA?AU?$pair@V?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@V12@@std@@PEAX@Z`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019e40`
- `0x1800412a8`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180014e24`
- `0x180014f3c`
- `0x180027818`
- `0x18003566c`
- `0x180035810`
- `0x1800367f4`
- `0x180038cfc`
- `0x1800611f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800368a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800368a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800368f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800368f6`
- `Bcp47Langs!GetUserLanguages` at `0x180036856`
- `Bcp47Langs!GetUserLanguages` at `0x180036856`

## string_xrefs

- `0x180036923`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetPreferredLanguagesForUser(__int64 a1, __int64 a2)
{
  __int64 UserPreferredUILanguages; // rdi
  int UserLanguages; // eax
  int v6[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v7; // [rsp+30h] [rbp-D0h]
  _BYTE v8[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *v9; // [rsp+48h] [rbp-B8h] BYREF
  char *v10; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[8]; // [rsp+80h] [rbp-80h] BYREF
  void *v12; // [rsp+88h] [rbp-78h] BYREF
  char *v13; // [rsp+98h] [rbp-68h] BYREF
  HSTRING string[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v15[8]; // [rsp+D0h] [rbp-30h] BYREF
  void *v16; // [rsp+D8h] [rbp-28h] BYREF
  char *v17; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v7 = a1;
  raii::ImpersonateLoggedOnUser(v6, a2);
  UserPreferredUILanguages = GetUserPreferredUILanguages(v11);
  string[0] = 0;
  WindowsDeleteString(0);
  string[0] = 0;
  UserLanguages = GetUserLanguages(0, string);
  if ( UserLanguages < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)UserLanguages,
      v6[0]);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(v15);
  bcp47::MultiStringToBcp47Tags(string, v15);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(
    v8,
    v15);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v17);
  std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v16);
  WindowsDeleteString(string[0]);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(
    a1,
    v8);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(
    a1 + 64,
    UserPreferredUILanguages);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v10);
  std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v9);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v13);
  std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v12);
  if ( LOBYTE(v6[0]) )
    RevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x1800367f4  mov     [rsp-8+arg_10], rbx
0x1800367f9  mov     [rsp-8+arg_18], rdi
0x1800367fe  push    rbp
0x1800367ff  lea     rbp, [rsp-20h]
0x180036804  sub     rsp, 120h
0x18003680b  mov     rax, cs:__security_cookie
0x180036812  xor     rax, rsp
0x180036815  mov     [rbp+20h+var_10], rax
0x180036819  mov     rbx, rcx
0x18003681c  mov     [rsp+120h+var_F0], rcx
0x180036821  lea     rcx, [rsp+120h+var_100]
0x180036826  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x18003682b  nop
0x18003682c  lea     rcx, [rbp+20h+var_A0]
0x180036830  call    _GetUserPreferredUILanguages
0x180036835  mov     rdi, rax
0x180036838  mov     [rbp+20h+string], 0
0x180036840  xor     ecx, ecx; string
0x180036842  call    cs:__imp_WindowsDeleteString
0x180036848  mov     [rbp+20h+string], 0
0x180036850  xor     ecx, ecx
0x180036852  lea     rdx, [rbp+20h+string]
0x180036856  call    cs:__imp_GetUserLanguages
0x18003685c  mov     rcx, [rbp+28h]; this
0x180036860  test    eax, eax
0x180036862  js      loc_180036920
0x180036868  lea     rcx, [rbp+20h+var_50]
0x18003686c  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180036871  nop
0x180036872  lea     rdx, [rbp+20h+var_50]
0x180036876  lea     rcx, [rbp+20h+string]
0x18003687a  call    ?MultiStringToBcp47Tags@bcp47@@YAXAEBVHString@Wrappers@WRL@Microsoft@@PEAV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@_N@Z; bcp47::MultiStringToBcp47Tags(Microsoft::WRL::Wrappers::HString const &,std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> *,bool)
0x18003687f  lea     rdx, [rbp+20h+var_50]
0x180036883  lea     rcx, [rsp+120h+var_E0]
0x180036888  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> &&)
0x18003688d  nop
0x18003688e  lea     rcx, [rbp+20h+var_38]
0x180036892  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180036897  lea     rcx, [rbp+20h+var_48]
0x18003689b  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800368a0  nop
0x1800368a1  mov     rcx, [rbp+20h+string]; string
0x1800368a5  call    cs:__imp_WindowsDeleteString
0x1800368ab  nop
0x1800368ac  lea     rdx, [rsp+120h+var_E0]
0x1800368b1  mov     rcx, rbx
0x1800368b4  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> &&)
0x1800368b9  nop
0x1800368ba  lea     rcx, [rbx+40h]
0x1800368be  mov     rdx, rdi
0x1800368c1  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> &&)
0x1800368c6  nop
0x1800368c7  lea     rcx, [rsp+120h+var_C8]
0x1800368cc  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x1800368d1  lea     rcx, [rsp+120h+var_D8]
0x1800368d6  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800368db  nop
0x1800368dc  lea     rcx, [rbp+20h+var_88]
0x1800368e0  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x1800368e5  lea     rcx, [rbp+20h+var_98]
0x1800368e9  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800368ee  nop
0x1800368ef  cmp     byte ptr [rsp+120h+var_100], 0
0x1800368f4  jz      short loc_1800368FC
0x1800368f6  call    cs:__imp_RevertToSelf
0x1800368fc  mov     rax, rbx
0x1800368ff  mov     rcx, [rbp+20h+var_10]
0x180036903  xor     rcx, rsp; StackCookie
0x180036906  call    __security_check_cookie
0x18003690b  lea     r11, [rsp+120h+var_s0]
0x180036913  mov     rbx, [r11+20h]
0x180036917  mov     rdi, [r11+28h]
0x18003691b  mov     rsp, r11
0x18003691e  pop     rbp
0x18003691f  retn
0x180036920  mov     r9d, eax; char *
0x180036923  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x18003692a  mov     edx, 0E4h; void *
0x18003692f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
