# bcp47::ConvertToNlsForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)

- ea: `0x180060eb8`
- end: `0x180060f73`
- name: `?ConvertToNlsForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005515c`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180014720`
- `0x180060eb8`
- `0x18006182c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060f23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060f23`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x180060f0d`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x180060f0d`

## string_xrefs

- `0x180060f61`: `onecore\base\languageoverlay\common\bcp47utils.cpp`

## pseudocode

```c
_QWORD *__fastcall bcp47::ConvertToNlsForm(_QWORD *a1)
{
  __int64 HStringReference; // rax
  int NlsForm; // eax
  WCHAR *StringRawBuffer; // rax
  HSTRING string[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  WindowsDeleteString(0);
  string[0] = 0;
  HStringReference = bcp47::_MakeHStringReference(&hstringHeader);
  NlsForm = Bcp47GetNlsForm(*(_QWORD *)(HStringReference + 24), string);
  if ( NlsForm < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
      (const char *)(unsigned int)NlsForm,
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
0x180060eb8  mov     [rsp+arg_10], rbx
0x180060ebd  push    rdi
0x180060ebe  sub     rsp, 60h
0x180060ec2  mov     rax, cs:__security_cookie
0x180060ec9  xor     rax, rsp
0x180060ecc  mov     [rsp+68h+var_18], rax
0x180060ed1  mov     rbx, rdx
0x180060ed4  mov     rdi, rcx
0x180060ed7  mov     [rsp+68h+string], rcx
0x180060edc  mov     [rsp+68h+string], 0
0x180060ee5  xor     ecx, ecx; string
0x180060ee7  call    cs:__imp_WindowsDeleteString
0x180060eed  mov     [rsp+68h+string], 0; int
0x180060ef6  mov     rdx, rbx
0x180060ef9  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180060efe  call    bcp47___MakeHStringReference
0x180060f03  nop
0x180060f04  lea     rdx, [rsp+68h+string]
0x180060f09  mov     rcx, [rax+18h]
0x180060f0d  call    cs:__imp_Bcp47GetNlsForm
0x180060f13  mov     rcx, [rsp+68h]; this
0x180060f18  test    eax, eax
0x180060f1a  js      short loc_180060F5E
0x180060f1c  xor     edx, edx; length
0x180060f1e  mov     rcx, [rsp+68h+string]; string
0x180060f23  call    cs:__imp_WindowsGetStringRawBuffer
0x180060f29  mov     rdx, rax
0x180060f2c  mov     rcx, rdi
0x180060f2f  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180060f34  nop
0x180060f35  mov     rcx, [rsp+68h+string]; string
0x180060f3a  call    cs:__imp_WindowsDeleteString
0x180060f40  mov     rax, rdi
0x180060f43  mov     rcx, [rsp+68h+var_18]
0x180060f48  xor     rcx, rsp; StackCookie
0x180060f4b  call    __security_check_cookie
0x180060f50  mov     rbx, [rsp+68h+arg_10]
0x180060f58  add     rsp, 60h
0x180060f5c  pop     rdi
0x180060f5d  retn
0x180060f5e  mov     r9d, eax; char *
0x180060f61  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x180060f68  mov     edx, 63h ; 'c'; void *
0x180060f6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
