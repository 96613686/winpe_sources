# GetPreferredUILanguagesForSystem(void)

- ea: `0x180061998`
- end: `0x180061b8d`
- name: `?GetPreferredUILanguagesForSystem@@YA?AV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@XZ`
- size: `501`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180019cdc`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180014e24`
- `0x180014ed0`
- `0x180014f3c`
- `0x1800351dc`
- `0x180035810`
- `0x18003d0d4`
- `0x18005f26c`
- `0x180060cd8`
- `0x1800611f4`
- `0x180061998`
- `0x180061b94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180061ac5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180061ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061b57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061b57`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180061a44`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180061a44`
- `Bcp47Langs!GetDisplayLanguagesForAllUsers` at `0x1800619f8`
- `Bcp47Langs!GetDisplayLanguagesForAllUsers` at `0x1800619f8`

## string_xrefs

- `0x180061a6f`: `PreviousInstallLanguage`
- `0x180061b7b`: `onecore\base\languageoverlay\common\languageutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
float *__fastcall GetPreferredUILanguagesForSystem(float *a1)
{
  int DisplayLanguagesForAllUsers; // eax
  _QWORD *v3; // rsi
  _QWORD *i; // rbx
  LANGID SystemDefaultUILanguage; // ax
  const wchar_t *v6; // rcx
  unsigned __int16 v7; // ax
  int v9; // [rsp+20h] [rbp-E0h]
  HSTRING string[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v12; // [rsp+58h] [rbp-A8h] BYREF
  char *v13; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String[2]; // [rsp+90h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-60h]
  _OWORD v16[2]; // [rsp+B0h] [rbp-50h] BYREF
  char *v17[4]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  string[1] = (HSTRING)a1;
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(a1);
  WindowsDeleteString(0);
  string[0] = 0;
  DisplayLanguagesForAllUsers = GetDisplayLanguagesForAllUsers(0, string, 0);
  if ( DisplayLanguagesForAllUsers < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\languageutils.cpp",
      (const char *)(unsigned int)DisplayLanguagesForAllUsers,
      v9);
  bcp47::MultiStringToBcp47Tags(string, a1);
  GetSystemPreferredLanguages((__int64)v11);
  v3 = v12;
  for ( i = (_QWORD *)*v12; i != v3; i = (_QWORD *)*i )
    std::_Hash<std::_Uset_traits<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::_Uhash_compare<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::hash<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,std::equal_to<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>>,std::allocator<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,0>>::emplace<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>> const &>(
      a1,
      (__int64)String,
      i + 2);
  SystemDefaultUILanguage = GetSystemDefaultUILanguage();
  bcp47::ConvertLcidToMuiForm(v17, SystemDefaultUILanguage);
  std::_Hash<std::_Uset_traits<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::_Uhash_compare<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::hash<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,std::equal_to<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>>,std::allocator<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,0>>::emplace<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>> const &>(
    a1,
    (__int64)String,
    v17);
  GetRegValue(String, -2147483646, L"SYSTEM\\CurrentControlSet\\Control\\Nls\\Language", L"PreviousInstallLanguage");
  if ( si128.m128i_i64[0] )
  {
    v6 = (const wchar_t *)String;
    if ( si128.m128i_i64[1] > 7uLL )
      v6 = String[0];
    v7 = wcstol(v6, 0, 16);
    bcp47::ConvertLcidToMuiForm(v16, v7);
  }
  else
  {
    v16[0] = 0;
    v16[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v16[0]) = 0;
  }
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)String);
  std::_Hash<std::_Uset_traits<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::_Uhash_compare<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::hash<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,std::equal_to<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>>,std::allocator<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,0>>::emplace<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>> const &>(
    a1,
    (__int64)String,
    v16);
  *(_OWORD *)String = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String[0]) = 0;
  std::_Hash<std::_Uset_traits<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::_Uhash_compare<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>,std::hash<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,std::equal_to<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>>,std::allocator<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>,0>>::erase(
    a1,
    String);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)String);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v16);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v17);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v13);
  std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>((void **)&v12);
  WindowsDeleteString(string[0]);
  return a1;
}

```

## disassembly

```asm
0x180061998  push    rbp
0x18006199a  push    rbx
0x18006199b  push    rsi
0x18006199c  push    rdi
0x18006199d  lea     rbp, [rsp-8]
0x1800619a2  sub     rsp, 108h
0x1800619a9  mov     rax, cs:__security_cookie
0x1800619b0  xor     rax, rsp
0x1800619b3  mov     [rbp+20h+var_30], rax
0x1800619b7  mov     rdi, rcx
0x1800619ba  mov     [rsp+120h+var_E0], rcx
0x1800619bf  mov     [rsp+120h+var_F0], 0
0x1800619c7  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800619cc  mov     [rsp+120h+var_F0], 1
0x1800619d4  mov     [rsp+120h+string], 0
0x1800619dd  xor     ecx, ecx; string
0x1800619df  call    cs:__imp_WindowsDeleteString
0x1800619e5  mov     [rsp+120h+string], 0
0x1800619ee  xor     ecx, ecx
0x1800619f0  xor     r8d, r8d
0x1800619f3  lea     rdx, [rsp+120h+string]
0x1800619f8  call    cs:__imp_GetDisplayLanguagesForAllUsers
0x1800619fe  mov     rcx, [rbp+28h]; this
0x180061a02  test    eax, eax
0x180061a04  js      loc_180061B78
0x180061a0a  mov     rdx, rdi
0x180061a0d  lea     rcx, [rsp+120h+string]
0x180061a12  call    ?MultiStringToBcp47Tags@bcp47@@YAXAEBVHString@Wrappers@WRL@Microsoft@@PEAV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@_N@Z; bcp47::MultiStringToBcp47Tags(Microsoft::WRL::Wrappers::HString const &,std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> *,bool)
0x180061a17  lea     rcx, [rsp+120h+var_D0]
0x180061a1c  call    ?GetSystemPreferredLanguages@@YA?AV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@XZ; GetSystemPreferredLanguages(void)
0x180061a21  nop
0x180061a22  mov     rsi, [rsp+120h+var_C8]
0x180061a27  mov     rbx, [rsi]
0x180061a2a  cmp     rbx, rsi
0x180061a2d  jz      short loc_180061A44
0x180061a2f  lea     r8, [rbx+10h]
0x180061a33  lea     rdx, [rbp+20h+String]
0x180061a37  mov     rcx, rdi
0x180061a3a  call    ??$emplace@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$_Uhash_compare@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@1@@Z; std::_Hash<std::_Uset_traits<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::hash<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180061a3f  mov     rbx, [rbx]
0x180061a42  jmp     short loc_180061A2A
0x180061a44  call    cs:__imp_GetSystemDefaultUILanguage
0x180061a4a  movzx   edx, ax
0x180061a4d  lea     rcx, [rbp+20h+var_50]
0x180061a51  call    ?ConvertLcidToMuiForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@K@Z; bcp47::ConvertLcidToMuiForm(ulong)
0x180061a56  nop
0x180061a57  lea     r8, [rbp+20h+var_50]
0x180061a5b  lea     rdx, [rbp+20h+String]
0x180061a5f  mov     rcx, rdi
0x180061a62  call    ??$emplace@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$_Uhash_compare@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@1@@Z; std::_Hash<std::_Uset_traits<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::hash<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180061a67  mov     [rsp+120h+var_100], 2
0x180061a6f  lea     r9, aPreviousinstal; "PreviousInstallLanguage"
0x180061a76  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Nls"...
0x180061a7d  mov     rdx, 0FFFFFFFF80000002h
0x180061a84  lea     rcx, [rbp+20h+String]
0x180061a88  call    ?GetRegValue@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1K@Z; GetRegValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x180061a8d  nop
0x180061a8e  cmp     qword ptr [rbp+20h+var_80], 0
0x180061a93  jnz     short loc_180061AB1
0x180061a95  xorps   xmm0, xmm0
0x180061a98  movups  [rbp+20h+var_70], xmm0
0x180061a9c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180061aa4  movdqu  [rbp+20h+var_60], xmm1
0x180061aa9  xor     eax, eax
0x180061aab  mov     word ptr [rbp+20h+var_70], ax
0x180061aaf  jmp     short loc_180061AD7
0x180061ab1  lea     rcx, [rbp+20h+String]
0x180061ab5  cmp     qword ptr [rbp+20h+var_80+8], 7
0x180061aba  cmova   rcx, [rbp+20h+String]; String
0x180061abf  xor     edx, edx; EndPtr
0x180061ac1  lea     r8d, [rdx+10h]; Radix
0x180061ac5  call    cs:__imp_wcstol
0x180061acb  movzx   edx, ax
0x180061ace  lea     rcx, [rbp+20h+var_70]
0x180061ad2  call    ?ConvertLcidToMuiForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@K@Z; bcp47::ConvertLcidToMuiForm(ulong)
0x180061ad7  mov     [rsp+120h+var_F0], 3
0x180061adf  lea     rcx, [rbp+20h+String]; void *
0x180061ae3  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180061ae8  nop
0x180061ae9  lea     r8, [rbp+20h+var_70]
0x180061aed  lea     rdx, [rbp+20h+String]
0x180061af1  mov     rcx, rdi
0x180061af4  call    ??$emplace@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$_Uhash_compare@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@1@@Z; std::_Hash<std::_Uset_traits<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::hash<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180061af9  xorps   xmm0, xmm0
0x180061afc  movups  xmmword ptr [rbp+20h+String], xmm0
0x180061b00  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180061b08  movdqu  [rbp+20h+var_80], xmm1
0x180061b0d  xor     eax, eax
0x180061b0f  mov     word ptr [rbp+20h+String], ax
0x180061b13  lea     rdx, [rbp+20h+String]
0x180061b17  mov     rcx, rdi
0x180061b1a  call    ?erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$_Uhash_compare@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@2@@Z; std::_Hash<std::_Uset_traits<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>,std::hash<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>,0>>::erase(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180061b1f  lea     rcx, [rbp+20h+String]; void *
0x180061b23  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180061b28  nop
0x180061b29  lea     rcx, [rbp+20h+var_70]; void *
0x180061b2d  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180061b32  nop
0x180061b33  lea     rcx, [rbp+20h+var_50]; void *
0x180061b37  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180061b3c  nop
0x180061b3d  lea     rcx, [rsp+120h+var_B8]
0x180061b42  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180061b47  lea     rcx, [rsp+120h+var_C8]
0x180061b4c  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180061b51  nop
0x180061b52  mov     rcx, [rsp+120h+string]; string
0x180061b57  call    cs:__imp_WindowsDeleteString
0x180061b5d  mov     rax, rdi
0x180061b60  mov     rcx, [rbp+20h+var_30]
0x180061b64  xor     rcx, rsp; StackCookie
0x180061b67  call    __security_check_cookie
0x180061b6c  add     rsp, 108h
0x180061b73  pop     rdi
0x180061b74  pop     rsi
0x180061b75  pop     rbx
0x180061b76  pop     rbp
0x180061b77  retn
0x180061b78  mov     r9d, eax; char *
0x180061b7b  lea     r8, aOnecoreBaseLan_11; "onecore\\base\\languageoverlay\\common"...
0x180061b82  mov     edx, 84h; void *
0x180061b87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
