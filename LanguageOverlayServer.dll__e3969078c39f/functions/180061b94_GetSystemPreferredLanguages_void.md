# GetSystemPreferredLanguages(void)

- ea: `0x180061b94`
- end: `0x180061caf`
- name: `?GetSystemPreferredLanguages@@YA?AV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@XZ`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800412a8`
- `0x180061998`

## callees

- `0x180003ea0`
- `0x1800044b8`
- `0x180005df8`
- `0x180011318`
- `0x180014e24`
- `0x180014f3c`
- `0x18003566c`
- `0x180035810`
- `0x180061240`
- `0x180061b94`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180061bc6`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180061c1d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180061bc6`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180061c1d`

## string_xrefs

- `0x180061c8b`: `onecore\base\languageoverlay\common\languageutils.cpp`
- `0x180061c9d`: `onecore\base\languageoverlay\common\languageutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSystemPreferredLanguages(__int64 a1)
{
  const char *v2; // r9
  unsigned __int64 v3; // rbx
  void *v4; // rsi
  const char *v5; // r9
  _QWORD v7[2]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v8[8]; // [rsp+40h] [rbp-40h] BYREF
  void *v9; // [rsp+48h] [rbp-38h] BYREF
  char *v10; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  ULONG pcchLanguagesBuffer; // [rsp+A8h] [rbp+28h] BYREF
  ULONG pulNumLanguages; // [rsp+B0h] [rbp+30h] BYREF
  void *v14; // [rsp+B8h] [rbp+38h]

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\languageutils.cpp",
      v2);
  v3 = saturated_mul(pcchLanguagesBuffer, 2u);
  v4 = operator new[](v3);
  memset_0(v4, 0, v3);
  v14 = v4;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, (PZZWSTR)v4, &pcchLanguagesBuffer) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\languageutils.cpp",
      v5);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(v8);
  v7[0] = v4;
  v7[1] = pcchLanguagesBuffer;
  bcp47::MultiStringToBcp47Tags(v7, v8);
  std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(
    a1,
    v8);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v10);
  std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v9);
  operator delete(v4);
  return a1;
}

```

## disassembly

```asm
0x180061b94  mov     [rsp-18h+arg_0], rbx
0x180061b99  push    rbp
0x180061b9a  push    rsi
0x180061b9b  push    rdi
0x180061b9c  mov     rbp, rsp
0x180061b9f  sub     rsp, 80h
0x180061ba6  mov     rdi, rcx
0x180061ba9  mov     [rbp+pulNumLanguages], 0
0x180061bb0  mov     [rbp+pcchLanguagesBuffer], 0
0x180061bb7  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180061bbb  xor     r8d, r8d; pwszLanguagesBuffer
0x180061bbe  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180061bc2  lea     ecx, [r8+8]; dwFlags
0x180061bc6  call    cs:__imp_GetSystemPreferredUILanguages
0x180061bcc  mov     rcx, [rbp+18h]; this
0x180061bd0  test    eax, eax
0x180061bd2  jz      loc_180061C9D
0x180061bd8  mov     ecx, [rbp+pcchLanguagesBuffer]
0x180061bdb  mov     eax, 2
0x180061be0  mul     rcx
0x180061be3  mov     rbx, rax
0x180061be6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180061bed  cmovb   rbx, rax
0x180061bf1  mov     rcx, rbx; unsigned __int64
0x180061bf4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180061bf9  mov     rsi, rax
0x180061bfc  mov     r8, rbx; Size
0x180061bff  xor     edx, edx; Val
0x180061c01  mov     rcx, rax; void *
0x180061c04  call    memset_0
0x180061c09  mov     [rbp+arg_18], rsi
0x180061c0d  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180061c11  mov     r8, rsi; pwszLanguagesBuffer
0x180061c14  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180061c18  mov     ecx, 8; dwFlags
0x180061c1d  call    cs:__imp_GetSystemPreferredUILanguages
0x180061c23  mov     rcx, [rbp+18h]; this
0x180061c27  test    eax, eax
0x180061c29  jz      short loc_180061C8B
0x180061c2b  lea     rcx, [rbp+var_40]
0x180061c2f  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180061c34  nop
0x180061c35  mov     [rbp+var_50], rsi
0x180061c39  mov     eax, [rbp+pcchLanguagesBuffer]
0x180061c3c  mov     [rbp+var_48], rax
0x180061c40  lea     rdx, [rbp+var_40]
0x180061c44  lea     rcx, [rbp+var_50]
0x180061c48  call    ?MultiStringToBcp47Tags@bcp47@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@3@_N@Z; bcp47::MultiStringToBcp47Tags(std::basic_string_view<ushort>,std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> *,bool)
0x180061c4d  lea     rdx, [rbp+var_40]
0x180061c51  mov     rcx, rdi
0x180061c54  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> &&)
0x180061c59  nop
0x180061c5a  lea     rcx, [rbp+var_28]
0x180061c5e  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180061c63  lea     rcx, [rbp+var_38]
0x180061c67  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180061c6c  nop
0x180061c6d  mov     rcx, rsi; void *
0x180061c70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180061c75  mov     rax, rdi
0x180061c78  mov     rbx, [rsp+80h+arg_0]
0x180061c80  add     rsp, 80h
0x180061c87  pop     rdi
0x180061c88  pop     rsi
0x180061c89  pop     rbp
0x180061c8a  retn
0x180061c8b  lea     r8, aOnecoreBaseLan_11; "onecore\\base\\languageoverlay\\common"...
0x180061c92  mov     edx, 6Fh ; 'o'; void *
0x180061c97  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180061c9d  lea     r8, aOnecoreBaseLan_11; "onecore\\base\\languageoverlay\\common"...
0x180061ca4  mov     edx, 68h ; 'h'; void *
0x180061ca9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
