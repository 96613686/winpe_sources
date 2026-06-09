# URLRewriteForHTTPS(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18007962c`
- end: `0x1800797d3`
- name: `?URLRewriteForHTTPS@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002d6ec`
- `0x18005ece0`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18007962c`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079765`
- `WININET!InternetCrackUrlW` at `0x1800796aa`
- `WININET!InternetCrackUrlW` at `0x1800796aa`
- `WININET!InternetCreateUrlW` at `0x18007975b`
- `WININET!InternetCreateUrlW` at `0x18007975b`

## pseudocode

```c
__int64 __fastcall URLRewriteForHTTPS(__int64 a1)
{
  const WCHAR *v2; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  DWORD dwUrlLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szUrl[2088]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  dwUrlLength[0] = 2084;
  UrlComponents.dwSchemeLength = 1;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUserNameLength = 1;
  UrlComponents.dwPasswordLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  UrlComponents.dwExtraInfoLength = 1;
  UrlComponents.dwStructSize = 104;
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( !InternetCrackUrlW(v2, 0, 0, &UrlComponents) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 30;
    goto LABEL_6;
  }
  UrlComponents.nScheme = INTERNET_SCHEME_HTTPS;
  UrlComponents.lpszScheme = 0;
  UrlComponents.dwSchemeLength = 0;
  if ( !UrlComponents.nPort )
    UrlComponents.nPort = 443;
  if ( InternetCreateUrlW(&UrlComponents, 0, szUrl, dwUrlLength) )
  {
    std::wstring::assign(a1, szUrl);
    return 0;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 31;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
LABEL_7:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18007962c  mov     [rsp-8+arg_8], rbx
0x180079631  push    rbp
0x180079632  lea     rbp, [rsp-1010h]
0x18007963a  mov     eax, 1110h
0x18007963f  call    _alloca_probe
0x180079644  sub     rsp, rax
0x180079647  mov     rax, cs:__security_cookie
0x18007964e  xor     rax, rsp
0x180079651  mov     [rbp+1010h+var_10], rax
0x180079658  xor     edx, edx; Val
0x18007965a  mov     rbx, rcx
0x18007965d  lea     rcx, [rsp+1110h+UrlComponents]; void *
0x180079662  lea     r8d, [rdx+68h]; Size
0x180079666  call    memset_0
0x18007966b  mov     eax, 1
0x180079670  mov     [rsp+1110h+dwUrlLength], 824h
0x180079678  mov     rcx, rbx
0x18007967b  mov     [rsp+1110h+UrlComponents.dwSchemeLength], eax
0x18007967f  mov     [rsp+1110h+UrlComponents.dwHostNameLength], eax
0x180079683  mov     [rsp+1110h+UrlComponents.dwUserNameLength], eax
0x180079687  mov     [rbp+1010h+UrlComponents.dwPasswordLength], eax
0x18007968a  mov     [rbp+1010h+UrlComponents.dwUrlPathLength], eax
0x18007968d  mov     [rbp+1010h+UrlComponents.dwExtraInfoLength], eax
0x180079690  mov     [rsp+1110h+UrlComponents.dwStructSize], 68h ; 'h'
0x180079698  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007969d  lea     r9, [rsp+1110h+UrlComponents]; lpUrlComponents
0x1800796a2  xor     r8d, r8d; dwFlags
0x1800796a5  xor     edx, edx; dwUrlLength
0x1800796a7  mov     rcx, rax; lpszUrl
0x1800796aa  call    cs:__imp_InternetCrackUrlW
0x1800796b0  test    eax, eax
0x1800796b2  jnz     short loc_18007971F
0x1800796b4  call    cs:__imp_GetLastError
0x1800796ba  mov     ebx, eax
0x1800796bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800796c3  lea     rcx, WPP_GLOBAL_Control
0x1800796ca  cmp     rax, rcx
0x1800796cd  jz      short loc_180079703
0x1800796cf  test    byte ptr [rax+1Ch], 8
0x1800796d3  jz      short loc_180079703
0x1800796d5  cmp     byte ptr [rax+19h], 2
0x1800796d9  jb      short loc_180079703
0x1800796db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800796e0  mov     edx, 1Eh
0x1800796e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796ec  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x1800796f3  mov     r9d, eax
0x1800796f6  mov     [rsp+1110h+var_10F0], ebx
0x1800796fa  mov     rcx, [rcx+10h]
0x1800796fe  call    WPP_SF_Dd
0x180079703  test    ebx, ebx
0x180079705  jle     short loc_180079710
0x180079707  movzx   ebx, bx
0x18007970a  or      ebx, 80070000h
0x180079710  test    ebx, ebx
0x180079712  mov     eax, 80004005h
0x180079717  cmovns  ebx, eax
0x18007971a  jmp     loc_1800797B1
0x18007971f  xor     eax, eax
0x180079721  mov     [rsp+1110h+UrlComponents.nScheme], 4
0x180079729  mov     [rsp+1110h+UrlComponents.lpszScheme], 0
0x180079732  mov     [rsp+1110h+UrlComponents.dwSchemeLength], 0
0x18007973a  cmp     ax, [rsp+1110h+UrlComponents.nPort]
0x18007973f  jnz     short loc_18007974B
0x180079741  mov     eax, 1BBh
0x180079746  mov     [rsp+1110h+UrlComponents.nPort], ax
0x18007974b  lea     r9, [rsp+1110h+dwUrlLength]; lpdwUrlLength
0x180079750  xor     edx, edx; dwFlags
0x180079752  lea     r8, [rbp+1010h+szUrl]; lpszUrl
0x180079756  lea     rcx, [rsp+1110h+UrlComponents]; lpUrlComponents
0x18007975b  call    cs:__imp_InternetCreateUrlW
0x180079761  test    eax, eax
0x180079763  jnz     short loc_1800797A3
0x180079765  call    cs:__imp_GetLastError
0x18007976b  mov     ebx, eax
0x18007976d  mov     rax, cs:WPP_GLOBAL_Control
0x180079774  lea     rcx, WPP_GLOBAL_Control
0x18007977b  cmp     rax, rcx
0x18007977e  jz      short loc_180079703
0x180079780  test    byte ptr [rax+1Ch], 8
0x180079784  jz      loc_180079703
0x18007978a  cmp     byte ptr [rax+19h], 2
0x18007978e  jb      loc_180079703
0x180079794  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079799  mov     edx, 1Fh
0x18007979e  jmp     loc_1800796E5
0x1800797a3  lea     rdx, [rbp+1010h+szUrl]
0x1800797a7  mov     rcx, rbx
0x1800797aa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800797af  xor     ebx, ebx
0x1800797b1  mov     eax, ebx
0x1800797b3  mov     rcx, [rbp+1010h+var_10]
0x1800797ba  xor     rcx, rsp; StackCookie
0x1800797bd  call    __security_check_cookie
0x1800797c2  mov     rbx, [rsp+1110h+arg_8]
0x1800797ca  add     rsp, 1110h
0x1800797d1  pop     rbp
0x1800797d2  retn
```
