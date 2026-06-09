# CombineURL(ushort const *,ushort const *,ulong,ushort *)

- ea: `0x1800459d8`
- end: `0x180045c32`
- name: `?CombineURL@@YAJPEBG0KPEAG@Z`
- size: `602`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d6ec`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x1800459d8`
- `0x18009a520`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180045b44`
- `msvcrt!_wcsicmp` at `0x180045b44`
- `msvcrt!wcscat_s` at `0x180045b75`
- `msvcrt!wcscat_s` at `0x180045b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bf6`
- `SHLWAPI!PathIsContentTypeW` at `0x180045b5a`
- `SHLWAPI!PathIsContentTypeW` at `0x180045b5a`
- `WININET!InternetCanonicalizeUrlW` at `0x180045a1c`
- `WININET!InternetCanonicalizeUrlW` at `0x180045a1c`
- `WININET!InternetCombineUrlW` at `0x180045b93`
- `WININET!InternetCombineUrlW` at `0x180045b93`

## string_xrefs

- `0x180045b87`: `./RDWebService.asmx`

## pseudocode

```c
__int64 __fastcall CombineURL(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  signed int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  unsigned int v11; // eax
  int v12; // ecx
  WCHAR *v13; // r8
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v16; // eax
  DWORD dwBufferLength; // [rsp+30h] [rbp-238h] BYREF
  DWORD v19; // [rsp+38h] [rbp-230h] BYREF
  wchar_t szBuffer[264]; // [rsp+40h] [rbp-228h] BYREF

  v19 = 260;
  dwBufferLength = 260;
  if ( InternetCanonicalizeUrlW(a1, szBuffer, &dwBufferLength, 0) )
  {
    v9 = 0;
    v10 = -1;
    do
      ++v10;
    while ( szBuffer[v10] );
    if ( (_DWORD)v10 )
    {
      v12 = v10 - 1;
      if ( szBuffer[v12] != 47 )
      {
        while ( 1 )
        {
          if ( v12 < 0 )
            goto LABEL_24;
          v13 = &szBuffer[v12];
          if ( *v13 == 47 )
            goto LABEL_24;
          if ( *v13 == 46 )
            break;
          --v12;
        }
        if ( _wcsicmp(&szBuffer[v12], L".aspx") && !PathIsContentTypeW(szBuffer, L"text/html") )
LABEL_24:
          wcscat_s(szBuffer, 0x104u, L"/");
      }
      if ( !InternetCombineUrlW(szBuffer, L"./RDWebService.asmx", a4, &v19, 0) && GetLastError() )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
        }
        v16 = GetLastError();
        v9 = v16;
        if ( v16 > 0 )
          return (unsigned __int16)v16 | 0x80070000;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids, v11);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids, v7, v6);
    }
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return v9;
}

```

## disassembly

```asm
0x1800459d8  mov     [rsp+arg_8], rbx
0x1800459dd  mov     [rsp+arg_10], rsi
0x1800459e2  push    rdi
0x1800459e3  sub     rsp, 260h
0x1800459ea  mov     rax, cs:__security_cookie
0x1800459f1  xor     rax, rsp
0x1800459f4  mov     [rsp+268h+var_18], rax
0x1800459fc  mov     rdi, r9
0x1800459ff  mov     [rsp+268h+var_230], 104h
0x180045a07  xor     r9d, r9d; dwFlags
0x180045a0a  mov     [rsp+268h+dwBufferLength], 104h
0x180045a12  lea     r8, [rsp+268h+dwBufferLength]; lpdwBufferLength
0x180045a17  lea     rdx, [rsp+268h+szBuffer]; lpszBuffer
0x180045a1c  call    cs:__imp_InternetCanonicalizeUrlW
0x180045a22  xor     esi, esi
0x180045a24  test    eax, eax
0x180045a26  jnz     short loc_180045A9F
0x180045a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a2f  lea     rax, WPP_GLOBAL_Control
0x180045a36  mov     edi, 80070000h
0x180045a3b  cmp     rcx, rax
0x180045a3e  jz      short loc_180045A85
0x180045a40  test    byte ptr [rcx+1Ch], 8
0x180045a44  jz      short loc_180045A85
0x180045a46  cmp     byte ptr [rcx+19h], 2
0x180045a4a  jb      short loc_180045A85
0x180045a4c  call    cs:__imp_GetLastError
0x180045a52  mov     ebx, eax
0x180045a54  test    eax, eax
0x180045a56  jle     short loc_180045A5D
0x180045a58  movzx   ebx, ax
0x180045a5b  or      ebx, edi
0x180045a5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a69  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180045a70  mov     edx, 16h
0x180045a75  mov     [rsp+268h+dwFlags], ebx
0x180045a79  mov     r9d, eax
0x180045a7c  mov     rcx, [rcx+10h]
0x180045a80  call    WPP_SF_Dd
0x180045a85  call    cs:__imp_GetLastError
0x180045a8b  mov     ebx, eax
0x180045a8d  test    eax, eax
0x180045a8f  jle     loc_180045C0B
0x180045a95  movzx   ebx, ax
0x180045a98  or      ebx, edi
0x180045a9a  jmp     loc_180045C0B
0x180045a9f  mov     ebx, esi
0x180045aa1  lea     rax, [rsp+268h+szBuffer]
0x180045aa6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180045aaa  inc     rcx
0x180045aad  cmp     [rax+rcx*2], si
0x180045ab1  jnz     short loc_180045AAA
0x180045ab3  test    ecx, ecx
0x180045ab5  jnz     short loc_180045B0B
0x180045ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180045abe  lea     rax, WPP_GLOBAL_Control
0x180045ac5  cmp     rcx, rax
0x180045ac8  jz      loc_180045C0B
0x180045ace  test    byte ptr [rcx+1Ch], 1
0x180045ad2  jz      loc_180045C0B
0x180045ad8  cmp     byte ptr [rcx+19h], 2
0x180045adc  jb      loc_180045C0B
0x180045ae2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180045aee  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180045af5  mov     edx, 17h
0x180045afa  mov     r9d, eax
0x180045afd  mov     rcx, [rcx+10h]
0x180045b01  call    WPP_SF_D
0x180045b06  jmp     loc_180045C0B
0x180045b0b  dec     ecx
0x180045b0d  movsxd  rax, ecx
0x180045b10  cmp     [rsp+rax*2+268h+szBuffer], 2Fh ; '/'
0x180045b16  jz      short loc_180045B7B
0x180045b18  test    ecx, ecx
0x180045b1a  js      short loc_180045B64
0x180045b1c  movsxd  rax, ecx
0x180045b1f  lea     r8, [rsp+268h+szBuffer]
0x180045b24  lea     r8, [r8+rax*2]
0x180045b28  cmp     word ptr [r8], 2Fh ; '/'
0x180045b2d  jz      short loc_180045B64
0x180045b2f  cmp     word ptr [r8], 2Eh ; '.'
0x180045b34  jz      short loc_180045B3A
0x180045b36  dec     ecx
0x180045b38  jmp     short loc_180045B18
0x180045b3a  lea     rdx, aAspx; ".aspx"
0x180045b41  mov     rcx, r8; String1
0x180045b44  call    cs:__imp__wcsicmp
0x180045b4a  test    eax, eax
0x180045b4c  jz      short loc_180045B7B
0x180045b4e  lea     rdx, pszContentType; "text/html"
0x180045b55  lea     rcx, [rsp+268h+szBuffer]; pszPath
0x180045b5a  call    cs:__imp_PathIsContentTypeW
0x180045b60  test    eax, eax
0x180045b62  jnz     short loc_180045B7B
0x180045b64  lea     r8, asc_1800B7094; "/"
0x180045b6b  mov     edx, 104h; SizeInWords
0x180045b70  lea     rcx, [rsp+268h+szBuffer]; Destination
0x180045b75  call    cs:__imp_wcscat_s
0x180045b7b  lea     r9, [rsp+268h+var_230]; lpdwBufferLength
0x180045b80  mov     [rsp+268h+dwFlags], esi; dwFlags
0x180045b84  mov     r8, rdi; lpszBuffer
0x180045b87  lea     rdx, szRelativeUrl; "./RDWebService.asmx"
0x180045b8e  lea     rcx, [rsp+268h+szBuffer]; lpszBaseUrl
0x180045b93  call    cs:__imp_InternetCombineUrlW
0x180045b99  test    eax, eax
0x180045b9b  jnz     short loc_180045C0B
0x180045b9d  call    cs:__imp_GetLastError
0x180045ba3  test    eax, eax
0x180045ba5  jz      short loc_180045C0B
0x180045ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bae  lea     rax, WPP_GLOBAL_Control
0x180045bb5  cmp     rcx, rax
0x180045bb8  jz      short loc_180045BF6
0x180045bba  test    byte ptr [rcx+1Ch], 8
0x180045bbe  jz      short loc_180045BF6
0x180045bc0  cmp     byte ptr [rcx+19h], 2
0x180045bc4  jb      short loc_180045BF6
0x180045bc6  call    cs:__imp_GetLastError
0x180045bcc  mov     ebx, eax
0x180045bce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bda  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180045be1  mov     edx, 18h
0x180045be6  mov     [rsp+268h+dwFlags], ebx
0x180045bea  mov     r9d, eax
0x180045bed  mov     rcx, [rcx+10h]
0x180045bf1  call    WPP_SF_Dd
0x180045bf6  call    cs:__imp_GetLastError
0x180045bfc  mov     ebx, eax
0x180045bfe  test    eax, eax
0x180045c00  jle     short loc_180045C0B
0x180045c02  movzx   ebx, ax
0x180045c05  or      ebx, 80070000h
0x180045c0b  mov     eax, ebx
0x180045c0d  mov     rcx, [rsp+268h+var_18]
0x180045c15  xor     rcx, rsp; StackCookie
0x180045c18  call    __security_check_cookie
0x180045c1d  lea     r11, [rsp+268h+var_8]
0x180045c25  mov     rbx, [r11+18h]
0x180045c29  mov     rsi, [r11+20h]
0x180045c2d  mov     rsp, r11
0x180045c30  pop     rdi
0x180045c31  retn
```
