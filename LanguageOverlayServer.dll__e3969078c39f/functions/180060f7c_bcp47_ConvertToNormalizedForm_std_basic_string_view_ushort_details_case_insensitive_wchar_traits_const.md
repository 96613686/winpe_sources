# bcp47::ConvertToNormalizedForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)

- ea: `0x180060f7c`
- end: `0x180061037`
- name: `?ConvertToNormalizedForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180052ad0`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180014720`
- `0x180060f7c`
- `0x18006182c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060fab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060fab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060fe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060fe7`
- `Bcp47Langs!Bcp47Normalize` at `0x180060fd1`
- `Bcp47Langs!Bcp47Normalize` at `0x180060fd1`

## string_xrefs

- `0x180061025`: `onecore\base\languageoverlay\common\bcp47utils.cpp`

## pseudocode

```c
_QWORD *__fastcall bcp47::ConvertToNormalizedForm(_QWORD *a1)
{
  __int64 HStringReference; // rax
  int v3; // eax
  WCHAR *StringRawBuffer; // rax
  HSTRING string[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  WindowsDeleteString(0);
  string[0] = 0;
  HStringReference = bcp47::_MakeHStringReference(&hstringHeader);
  v3 = Bcp47Normalize(*(_QWORD *)(HStringReference + 24), string);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
      (const char *)(unsigned int)v3,
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
0x180060f7c  mov     [rsp+arg_10], rbx
0x180060f81  push    rdi
0x180060f82  sub     rsp, 60h
0x180060f86  mov     rax, cs:__security_cookie
0x180060f8d  xor     rax, rsp
0x180060f90  mov     [rsp+68h+var_18], rax
0x180060f95  mov     rbx, rdx
0x180060f98  mov     rdi, rcx
0x180060f9b  mov     [rsp+68h+string], rcx
0x180060fa0  mov     [rsp+68h+string], 0
0x180060fa9  xor     ecx, ecx; string
0x180060fab  call    cs:__imp_WindowsDeleteString
0x180060fb1  mov     [rsp+68h+string], 0; int
0x180060fba  mov     rdx, rbx
0x180060fbd  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180060fc2  call    bcp47___MakeHStringReference
0x180060fc7  nop
0x180060fc8  lea     rdx, [rsp+68h+string]
0x180060fcd  mov     rcx, [rax+18h]
0x180060fd1  call    cs:__imp_Bcp47Normalize
0x180060fd7  mov     rcx, [rsp+68h]; this
0x180060fdc  test    eax, eax
0x180060fde  js      short loc_180061022
0x180060fe0  xor     edx, edx; length
0x180060fe2  mov     rcx, [rsp+68h+string]; string
0x180060fe7  call    cs:__imp_WindowsGetStringRawBuffer
0x180060fed  mov     rdx, rax
0x180060ff0  mov     rcx, rdi
0x180060ff3  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180060ff8  nop
0x180060ff9  mov     rcx, [rsp+68h+string]; string
0x180060ffe  call    cs:__imp_WindowsDeleteString
0x180061004  mov     rax, rdi
0x180061007  mov     rcx, [rsp+68h+var_18]
0x18006100c  xor     rcx, rsp; StackCookie
0x18006100f  call    __security_check_cookie
0x180061014  mov     rbx, [rsp+68h+arg_10]
0x18006101c  add     rsp, 60h
0x180061020  pop     rdi
0x180061021  retn
0x180061022  mov     r9d, eax; char *
0x180061025  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x18006102c  mov     edx, 3Bh ; ';'; void *
0x180061031  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
