# URLRewriteForIDN(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800797dc`
- end: `0x180079a69`
- name: `?URLRewriteForIDN@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005ece0`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x1800797dc`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799f4`
- `Normaliz!IdnToAscii` at `0x180079949`
- `Normaliz!IdnToAscii` at `0x180079949`
- `WININET!InternetCrackUrlW` at `0x1800798b9`
- `WININET!InternetCrackUrlW` at `0x1800798b9`
- `WININET!InternetCreateUrlW` at `0x1800799ea`
- `WININET!InternetCreateUrlW` at `0x1800799ea`

## pseudocode

```c
__int64 __fastcall URLRewriteForIDN(__int64 a1)
{
  bool v2; // cc
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // ebx
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  signed int v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  signed int v12; // eax
  DWORD dwUrlLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ASCIICharStr[2088]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szUrl[2088]; // [rsp+1100h] [rbp+1000h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  v2 = *(_QWORD *)(a1 + 16) <= 0x824u;
  dwUrlLength[0] = 2084;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    return (unsigned int)-2147024809;
  }
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = 1;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUserNameLength = 1;
  UrlComponents.dwPasswordLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  UrlComponents.dwExtraInfoLength = 1;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( !InternetCrackUrlW(v5, 0, 0, &UrlComponents) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 33;
LABEL_12:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids, v6, LastError);
LABEL_13:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  v8 = IdnToAscii(2u, UrlComponents.lpszHostName, UrlComponents.dwHostNameLength, ASCIICharStr, 2084);
  if ( v8 > 0 )
  {
    UrlComponents.dwHostNameLength = v8;
    UrlComponents.lpszHostName = ASCIICharStr;
    if ( InternetCreateUrlW(&UrlComponents, 0, szUrl, dwUrlLength) )
    {
      std::wstring::assign(a1, szUrl);
      return 0;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 35;
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids, v11, v10);
  }
  v12 = GetLastError();
  LastError = v12;
  if ( v12 > 0 )
    return (unsigned __int16)v12 | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800797dc  mov     [rsp-8+arg_8], rbx
0x1800797e1  push    rbp
0x1800797e2  lea     rbp, [rsp-2060h]
0x1800797ea  mov     eax, 2160h
0x1800797ef  call    _alloca_probe
0x1800797f4  sub     rsp, rax
0x1800797f7  mov     rax, cs:__security_cookie
0x1800797fe  xor     rax, rsp
0x180079801  mov     [rbp+2060h+var_10], rax
0x180079808  xor     edx, edx; Val
0x18007980a  mov     rbx, rcx
0x18007980d  lea     rcx, [rsp+2160h+UrlComponents]; void *
0x180079812  lea     r8d, [rdx+68h]; Size
0x180079816  call    memset_0
0x18007981b  cmp     qword ptr [rbx+10h], 824h
0x180079823  mov     [rsp+2160h+dwUrlLength], 824h
0x18007982b  jbe     short loc_180079882
0x18007982d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079834  lea     rax, WPP_GLOBAL_Control
0x18007983b  cmp     rcx, rax
0x18007983e  jz      short loc_180079878
0x180079840  test    byte ptr [rcx+1Ch], 8
0x180079844  jz      short loc_180079878
0x180079846  cmp     byte ptr [rcx+19h], 2
0x18007984a  jb      short loc_180079878
0x18007984c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079851  mov     rcx, cs:WPP_GLOBAL_Control
0x180079858  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x18007985f  mov     edx, 20h ; ' '
0x180079864  mov     [rsp+2160h+cchASCIIChar], 80070057h
0x18007986c  mov     r9d, eax
0x18007986f  mov     rcx, [rcx+10h]
0x180079873  call    WPP_SF_Dd
0x180079878  mov     ebx, 80070057h
0x18007987d  jmp     loc_180079A47
0x180079882  mov     eax, 1
0x180079887  mov     [rsp+2160h+UrlComponents.dwStructSize], 68h ; 'h'
0x18007988f  mov     rcx, rbx
0x180079892  mov     [rsp+2160h+UrlComponents.dwSchemeLength], eax
0x180079896  mov     [rsp+2160h+UrlComponents.dwHostNameLength], eax
0x18007989a  mov     [rsp+2160h+UrlComponents.dwUserNameLength], eax
0x18007989e  mov     [rbp+2060h+UrlComponents.dwPasswordLength], eax
0x1800798a1  mov     [rbp+2060h+UrlComponents.dwUrlPathLength], eax
0x1800798a4  mov     [rbp+2060h+UrlComponents.dwExtraInfoLength], eax
0x1800798a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800798ac  lea     r9, [rsp+2160h+UrlComponents]; lpUrlComponents
0x1800798b1  xor     r8d, r8d; dwFlags
0x1800798b4  xor     edx, edx; dwUrlLength
0x1800798b6  mov     rcx, rax; lpszUrl
0x1800798b9  call    cs:__imp_InternetCrackUrlW
0x1800798bf  test    eax, eax
0x1800798c1  jnz     short loc_18007992E
0x1800798c3  call    cs:__imp_GetLastError
0x1800798c9  mov     ebx, eax
0x1800798cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800798d2  lea     rax, WPP_GLOBAL_Control
0x1800798d9  cmp     rcx, rax
0x1800798dc  jz      short loc_180079912
0x1800798de  test    byte ptr [rcx+1Ch], 8
0x1800798e2  jz      short loc_180079912
0x1800798e4  cmp     byte ptr [rcx+19h], 2
0x1800798e8  jb      short loc_180079912
0x1800798ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800798ef  mov     edx, 21h ; '!'
0x1800798f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800798fb  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x180079902  mov     r9d, eax
0x180079905  mov     [rsp+2160h+cchASCIIChar], ebx
0x180079909  mov     rcx, [rcx+10h]
0x18007990d  call    WPP_SF_Dd
0x180079912  test    ebx, ebx
0x180079914  jle     short loc_18007991F
0x180079916  movzx   ebx, bx
0x180079919  or      ebx, 80070000h
0x18007991f  test    ebx, ebx
0x180079921  mov     eax, 80004005h
0x180079926  cmovns  ebx, eax
0x180079929  jmp     loc_180079A47
0x18007992e  mov     r8d, [rsp+2160h+UrlComponents.dwHostNameLength]; cchUnicodeChar
0x180079933  lea     r9, [rbp+2060h+ASCIICharStr]; lpASCIICharStr
0x180079937  mov     rdx, [rsp+2160h+UrlComponents.lpszHostName]; lpUnicodeCharStr
0x18007993c  mov     ecx, 2; dwFlags
0x180079941  mov     [rsp+2160h+cchASCIIChar], 824h; cchASCIIChar
0x180079949  call    cs:__imp_IdnToAscii
0x18007994f  test    eax, eax
0x180079951  jg      short loc_1800799CA
0x180079953  mov     rcx, cs:WPP_GLOBAL_Control
0x18007995a  lea     rax, WPP_GLOBAL_Control
0x180079961  cmp     rcx, rax
0x180079964  jz      short loc_1800799AF
0x180079966  test    byte ptr [rcx+1Ch], 8
0x18007996a  jz      short loc_1800799AF
0x18007996c  cmp     byte ptr [rcx+19h], 2
0x180079970  jb      short loc_1800799AF
0x180079972  call    cs:__imp_GetLastError
0x180079978  mov     ebx, eax
0x18007997a  test    eax, eax
0x18007997c  jle     short loc_180079987
0x18007997e  movzx   ebx, ax
0x180079981  or      ebx, 80070000h
0x180079987  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007998c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079993  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x18007999a  mov     edx, 22h ; '"'
0x18007999f  mov     [rsp+2160h+cchASCIIChar], ebx
0x1800799a3  mov     r9d, eax
0x1800799a6  mov     rcx, [rcx+10h]
0x1800799aa  call    WPP_SF_Dd
0x1800799af  call    cs:__imp_GetLastError
0x1800799b5  mov     ebx, eax
0x1800799b7  test    eax, eax
0x1800799b9  jle     loc_180079A47
0x1800799bf  movzx   ebx, ax
0x1800799c2  or      ebx, 80070000h
0x1800799c8  jmp     short loc_180079A47
0x1800799ca  lea     rcx, [rbp+2060h+ASCIICharStr]
0x1800799ce  mov     [rsp+2160h+UrlComponents.dwHostNameLength], eax
0x1800799d2  mov     [rsp+2160h+UrlComponents.lpszHostName], rcx
0x1800799d7  lea     r9, [rsp+2160h+dwUrlLength]; lpdwUrlLength
0x1800799dc  lea     rcx, [rsp+2160h+UrlComponents]; lpUrlComponents
0x1800799e1  xor     edx, edx; dwFlags
0x1800799e3  lea     r8, [rbp+2060h+szUrl]; lpszUrl
0x1800799ea  call    cs:__imp_InternetCreateUrlW
0x1800799f0  test    eax, eax
0x1800799f2  jnz     short loc_180079A36
0x1800799f4  call    cs:__imp_GetLastError
0x1800799fa  mov     ebx, eax
0x1800799fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180079a03  lea     rax, WPP_GLOBAL_Control
0x180079a0a  cmp     rcx, rax
0x180079a0d  jz      loc_180079912
0x180079a13  test    byte ptr [rcx+1Ch], 8
0x180079a17  jz      loc_180079912
0x180079a1d  cmp     byte ptr [rcx+19h], 2
0x180079a21  jb      loc_180079912
0x180079a27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079a2c  mov     edx, 23h ; '#'
0x180079a31  jmp     loc_1800798F4
0x180079a36  lea     rdx, [rbp+2060h+szUrl]
0x180079a3d  mov     rcx, rbx
0x180079a40  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180079a45  xor     ebx, ebx
0x180079a47  mov     eax, ebx
0x180079a49  mov     rcx, [rbp+2060h+var_10]
0x180079a50  xor     rcx, rsp; StackCookie
0x180079a53  call    __security_check_cookie
0x180079a58  mov     rbx, [rsp+2160h+arg_8]
0x180079a60  add     rsp, 2160h
0x180079a67  pop     rbp
0x180079a68  retn
```
