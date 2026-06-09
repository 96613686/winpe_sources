# bcp47::ConvertToMuiForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)

- ea: `0x180060df4`
- end: `0x180060eaf`
- name: `?ConvertToMuiForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z`
- size: `187`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800359cc`
- `0x180037aac`
- `0x18003bcbc`
- `0x180042460`
- `0x180047070`
- `0x18004c024`
- `0x18004d440`
- `0x180060c4c`
- `0x180060cd8`
- `0x1800610ec`
- `0x180061240`
- `0x18006132c`
- `0x1800614e8`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180014720`
- `0x180060df4`
- `0x18006182c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060e23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060e23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060e5f`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x180060e49`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x180060e49`

## string_xrefs

- `0x180060e9d`: `onecore\base\languageoverlay\common\bcp47utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall bcp47::ConvertToMuiForm(_QWORD *a1)
{
  __int64 HStringReference; // rax
  int MuiForm; // eax
  WCHAR *StringRawBuffer; // rax
  HSTRING string[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  WindowsDeleteString(0);
  string[0] = 0;
  HStringReference = bcp47::_MakeHStringReference(&hstringHeader);
  MuiForm = Bcp47GetMuiForm(*(_QWORD *)(HStringReference + 24), string);
  if ( MuiForm < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
      (const char *)(unsigned int)MuiForm,
      (int)string[0]);
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string[0], 0);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
    a1,
    StringRawBuffer);
  WindowsDeleteString(string[0]);
  return a1;
}

```

## disassembly

```asm
0x180060df4  mov     [rsp+arg_10], rbx
0x180060df9  push    rdi
0x180060dfa  sub     rsp, 60h
0x180060dfe  mov     rax, cs:__security_cookie
0x180060e05  xor     rax, rsp
0x180060e08  mov     [rsp+68h+var_18], rax
0x180060e0d  mov     rbx, rdx
0x180060e10  mov     rdi, rcx
0x180060e13  mov     [rsp+68h+string], rcx
0x180060e18  mov     [rsp+68h+string], 0
0x180060e21  xor     ecx, ecx; string
0x180060e23  call    cs:__imp_WindowsDeleteString
0x180060e29  mov     [rsp+68h+string], 0; int
0x180060e32  mov     rdx, rbx
0x180060e35  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180060e3a  call    bcp47___MakeHStringReference
0x180060e3f  nop
0x180060e40  lea     rdx, [rsp+68h+string]
0x180060e45  mov     rcx, [rax+18h]
0x180060e49  call    cs:__imp_Bcp47GetMuiForm
0x180060e4f  mov     rcx, [rsp+68h]; this
0x180060e54  test    eax, eax
0x180060e56  js      short loc_180060E9A
0x180060e58  xor     edx, edx; length
0x180060e5a  mov     rcx, [rsp+68h+string]; string
0x180060e5f  call    cs:__imp_WindowsGetStringRawBuffer
0x180060e65  mov     rdx, rax
0x180060e68  mov     rcx, rdi
0x180060e6b  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180060e70  nop
0x180060e71  mov     rcx, [rsp+68h+string]; string
0x180060e76  call    cs:__imp_WindowsDeleteString
0x180060e7c  mov     rax, rdi
0x180060e7f  mov     rcx, [rsp+68h+var_18]
0x180060e84  xor     rcx, rsp; StackCookie
0x180060e87  call    __security_check_cookie
0x180060e8c  mov     rbx, [rsp+68h+arg_10]
0x180060e94  add     rsp, 60h
0x180060e98  pop     rdi
0x180060e99  retn
0x180060e9a  mov     r9d, eax; char *
0x180060e9d  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x180060ea4  mov     edx, 4Fh ; 'O'; void *
0x180060ea9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
