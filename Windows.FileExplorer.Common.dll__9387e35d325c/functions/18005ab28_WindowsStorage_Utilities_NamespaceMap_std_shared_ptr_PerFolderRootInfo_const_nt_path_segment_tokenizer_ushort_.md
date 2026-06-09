# WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>::make_Hstring(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18005ab28`
- end: `0x18005abc6`
- name: `?make_Hstring@?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@CA?AVHString@Wrappers@WRL@Microsoft@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180033af0`

## callees

- `0x1800348e8`
- `0x18005ab28`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ab93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ab93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ab7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ab7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>::make_Hstring(
        HSTRING *string,
        __int64 a2)
{
  HRESULT v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_QWORD *)(a2 + 8) > 0x7FE7u )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\NamespaceMap.h",
      (const char *)0x80070057LL,
      0);
  *string = 0;
  WindowsDeleteString(0);
  *string = 0;
  v4 = WindowsCreateString(*(PCNZWCH *)a2, *(_DWORD *)(a2 + 8), string);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\NamespaceMap.h",
      (const char *)(unsigned int)v4,
      1);
  return string;
}

```

## disassembly

```asm
0x18005ab28  mov     [rsp+arg_8], rbx
0x18005ab2d  mov     [rsp+arg_0], rcx
0x18005ab32  push    rdi
0x18005ab33  sub     rsp, 30h
0x18005ab37  mov     rdi, rdx
0x18005ab3a  mov     rbx, rcx
0x18005ab3d  mov     [rsp+38h+var_18], 0; int
0x18005ab45  mov     rcx, [rsp+38h]; this
0x18005ab4a  cmp     qword ptr [rdx+8], 7FE7h
0x18005ab52  jbe     short loc_18005AB6C
0x18005ab54  mov     r9d, 80070057h; char *
0x18005ab5a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\NamespaceM"...
0x18005ab61  mov     edx, 0EFh; void *
0x18005ab66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ab6c  mov     qword ptr [rbx], 0
0x18005ab73  mov     [rsp+38h+var_18], 1; int
0x18005ab7b  xor     ecx, ecx; string
0x18005ab7d  call    cs:__imp_WindowsDeleteString
0x18005ab83  mov     qword ptr [rbx], 0
0x18005ab8a  mov     r8, rbx; string
0x18005ab8d  mov     edx, [rdi+8]; length
0x18005ab90  mov     rcx, [rdi]; sourceString
0x18005ab93  call    cs:__imp_WindowsCreateString
0x18005ab99  test    eax, eax
0x18005ab9b  jns     short loc_18005ABB7
0x18005ab9d  mov     rcx, [rsp+38h]; this
0x18005aba2  mov     r9d, eax; char *
0x18005aba5  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\NamespaceM"...
0x18005abac  mov     edx, 0F1h; void *
0x18005abb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005abb7  mov     rax, rbx
0x18005abba  mov     rbx, [rsp+38h+arg_8]
0x18005abbf  add     rsp, 30h
0x18005abc3  pop     rdi
0x18005abc4  retn
```
