# RetailDemoUserAgent::IsLinkInAppList(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,ushort const *)

- ea: `0x18003df40`
- end: `0x18003e041`
- name: `?IsLinkInAppList@RetailDemoUserAgent@@CA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180036f74`

## callees

- `0x180003390`
- `0x18001092c`
- `0x18001094c`
- `0x18003df40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df8f`
- `SHLWAPI!StrStrIW` at `0x18003dfe5`
- `SHLWAPI!StrStrIW` at `0x18003dfe5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003df87`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003df87`

## string_xrefs

- `0x18003dfad`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e029`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
char __fastcall RetailDemoUserAgent::IsLinkInAppList(__int64 *a1, const WCHAR *a2)
{
  DWORD FullPathNameW; // ebx
  signed int LastError; // eax
  __int64 v5; // rbx
  char v6; // di
  __int64 v7; // rsi
  const WCHAR *v8; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  FilePart = 0;
  FullPathNameW = GetFullPathNameW(a2, 0x104u, Buffer, &FilePart);
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !FullPathNameW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x670,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)LastError,
      (int)FilePart);
  if ( FullPathNameW > 0x104 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x671,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)0x80070057LL,
      (int)FilePart);
  v5 = *a1;
  v6 = 0;
  v7 = a1[1];
  while ( v5 != v7 )
  {
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    if ( StrStrIW(v8, FilePart) )
      return 1;
    v5 += 32;
  }
  return v6;
}

```

## disassembly

```asm
0x18003df40  mov     [rsp+arg_10], rbx
0x18003df45  mov     [rsp+arg_18], rsi
0x18003df4a  push    rdi
0x18003df4b  sub     rsp, 250h
0x18003df52  mov     rax, cs:__security_cookie
0x18003df59  xor     rax, rsp
0x18003df5c  mov     [rsp+258h+var_18], rax
0x18003df64  mov     rax, rdx
0x18003df67  mov     [rsp+258h+FilePart], 0; int
0x18003df70  mov     rsi, rcx
0x18003df73  lea     r9, [rsp+258h+FilePart]; lpFilePart
0x18003df78  mov     edi, 104h
0x18003df7d  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x18003df82  mov     edx, edi; nBufferLength
0x18003df84  mov     rcx, rax; lpFileName
0x18003df87  call    cs:__imp_GetFullPathNameW
0x18003df8d  mov     ebx, eax
0x18003df8f  call    cs:__imp_GetLastError
0x18003df95  test    eax, eax
0x18003df97  jle     short loc_18003DFA1
0x18003df99  movzx   eax, ax
0x18003df9c  or      eax, 80070000h
0x18003dfa1  test    ebx, ebx
0x18003dfa3  jnz     short loc_18003DFC2
0x18003dfa5  mov     rcx, [rsp+258h]; this
0x18003dfad  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003dfb4  mov     r9d, eax; char *
0x18003dfb7  mov     edx, 670h; void *
0x18003dfbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003dfc2  cmp     ebx, edi
0x18003dfc4  ja      short loc_18003E021
0x18003dfc6  mov     rbx, [rsi]
0x18003dfc9  xor     dil, dil
0x18003dfcc  mov     rsi, [rsi+8]
0x18003dfd0  cmp     rbx, rsi
0x18003dfd3  jz      short loc_18003DFF9
0x18003dfd5  mov     rcx, rbx
0x18003dfd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dfdd  mov     rdx, [rsp+258h+FilePart]; pszSrch
0x18003dfe2  mov     rcx, rax; pszFirst
0x18003dfe5  call    cs:__imp_StrStrIW
0x18003dfeb  test    rax, rax
0x18003dfee  jnz     short loc_18003DFF6
0x18003dff0  add     rbx, 20h ; ' '
0x18003dff4  jmp     short loc_18003DFD0
0x18003dff6  mov     dil, 1
0x18003dff9  mov     al, dil
0x18003dffc  mov     rcx, [rsp+258h+var_18]
0x18003e004  xor     rcx, rsp; StackCookie
0x18003e007  call    __security_check_cookie
0x18003e00c  lea     r11, [rsp+258h+var_8]
0x18003e014  mov     rbx, [r11+20h]
0x18003e018  mov     rsi, [r11+28h]
0x18003e01c  mov     rsp, r11
0x18003e01f  pop     rdi
0x18003e020  retn
0x18003e021  mov     rcx, [rsp+258h]; this
0x18003e029  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e030  mov     r9d, 80070057h; char *
0x18003e036  mov     edx, 671h; void *
0x18003e03b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
