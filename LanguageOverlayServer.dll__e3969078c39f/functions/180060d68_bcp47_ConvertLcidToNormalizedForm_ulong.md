# bcp47::ConvertLcidToNormalizedForm(ulong)

- ea: `0x180060d68`
- end: `0x180060dee`
- name: `?ConvertLcidToNormalizedForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@K@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180060cd8`

## callees

- `0x180012a98`
- `0x180014720`
- `0x180060d68`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060dae`
- `Bcp47Langs!Bcp47FromLcid` at `0x180060d98`
- `Bcp47Langs!Bcp47FromLcid` at `0x180060d98`

## string_xrefs

- `0x180060ddc`: `onecore\base\languageoverlay\common\bcp47utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall bcp47::ConvertLcidToNormalizedForm(_QWORD *a1, unsigned int a2)
{
  int v4; // eax
  WCHAR *StringRawBuffer; // rax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v4 = Bcp47FromLcid(a2, &string);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
      (const char *)(unsigned int)v4,
      v7);
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
    a1,
    StringRawBuffer);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x180060d68  mov     [rsp+arg_0], rbx
0x180060d6d  push    rdi
0x180060d6e  sub     rsp, 30h
0x180060d72  mov     ebx, edx
0x180060d74  mov     rdi, rcx
0x180060d77  mov     [rsp+38h+string], 0
0x180060d80  xor     ecx, ecx; string
0x180060d82  call    cs:__imp_WindowsDeleteString
0x180060d88  mov     [rsp+38h+string], 0
0x180060d91  lea     rdx, [rsp+38h+string]
0x180060d96  mov     ecx, ebx
0x180060d98  call    cs:__imp_Bcp47FromLcid
0x180060d9e  mov     rcx, [rsp+38h]; this
0x180060da3  test    eax, eax
0x180060da5  js      short loc_180060DD9
0x180060da7  xor     edx, edx; length
0x180060da9  mov     rcx, [rsp+38h+string]; string
0x180060dae  call    cs:__imp_WindowsGetStringRawBuffer
0x180060db4  mov     rdx, rax
0x180060db7  mov     rcx, rdi
0x180060dba  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180060dbf  nop
0x180060dc0  mov     rcx, [rsp+38h+string]; string
0x180060dc5  call    cs:__imp_WindowsDeleteString
0x180060dcb  mov     rax, rdi
0x180060dce  mov     rbx, [rsp+38h+arg_0]
0x180060dd3  add     rsp, 30h
0x180060dd7  pop     rdi
0x180060dd8  retn
0x180060dd9  mov     r9d, eax; char *
0x180060ddc  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x180060de3  mov     edx, 77h ; 'w'; void *
0x180060de8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
