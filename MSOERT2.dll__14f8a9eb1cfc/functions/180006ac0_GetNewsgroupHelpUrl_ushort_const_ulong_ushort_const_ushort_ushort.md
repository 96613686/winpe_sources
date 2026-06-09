# GetNewsgroupHelpUrl(ushort const *,ulong,ushort const *,ushort *,ushort * *)

- ea: `0x180006ac0`
- end: `0x180006dfd`
- name: `?GetNewsgroupHelpUrl@@YAJPEBGK0PEAGPEAPEAG@Z`
- size: `829`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007ba8`

## callees

- `0x180001c80`
- `0x180002698`
- `0x180004640`
- `0x18000470c`
- `0x180006ac0`
- `0x180011a78`
- `0x180012fc0`
- `0x180013050`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180006dbb`
- `KERNEL32!LocalFree` at `0x180006dbb`
- `KERNEL32!LocalAlloc` at `0x180006d8e`
- `KERNEL32!LocalAlloc` at `0x180006d8e`
- `KERNEL32!GetThreadLocale` at `0x180006b09`
- `KERNEL32!GetThreadLocale` at `0x180006b09`
- `KERNEL32!GetLocaleInfoW` at `0x180006b7e`
- `KERNEL32!GetLocaleInfoW` at `0x180006b9e`
- `KERNEL32!GetLocaleInfoW` at `0x180006b7e`
- `KERNEL32!GetLocaleInfoW` at `0x180006b9e`
- `SHLWAPI!StrTrimW` at `0x180006b4c`
- `SHLWAPI!StrTrimW` at `0x180006b4c`
- `SHLWAPI!UrlEscapeW` at `0x180006d02`
- `SHLWAPI!UrlEscapeW` at `0x180006d02`

## string_xrefs

- `0x180006d35`: `https://r.office.microsoft.com/r/rlidWebNews?clid=%s-%s&query="%s"`
- `0x180006d58`: `https://r.office.microsoft.com/r/rlidWebNews?clid=%s-%s`

## pseudocode

```c
__int64 __fastcall GetNewsgroupHelpUrl(
        WCHAR *a1,
        char a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  LCID ThreadLocale; // edi
  __int64 v10; // rdi
  HRESULT v11; // ebx
  __int64 v12; // rdx
  __int64 i; // rcx
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  int v16; // eax
  unsigned __int16 *v17; // rax
  void *v18; // r11
  DWORD pcchEscaped; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszTrimChars[6]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR v22[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR LCData[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR pszEscaped[2088]; // [rsp+460h] [rbp+360h] BYREF
  char v25[2096]; // [rsp+14B0h] [rbp+13B0h] BYREF
  unsigned __int16 v26[2088]; // [rsp+1CE0h] [rbp+1BE0h] BYREF
  WCHAR pszUrl[2088]; // [rsp+2D30h] [rbp+2C30h] BYREF

  ThreadLocale = GetThreadLocale();
  v26[0] = 0;
  if ( a1 && a5 )
  {
    wcscpy(pszTrimChars, L"{}");
    StrTrimW(a1, pszTrimChars);
    if ( a4 )
      ThreadLocale = *a4;
    LCData[0] = 0;
    v22[0] = 0;
    if ( !GetLocaleInfoW(ThreadLocale, 0x59u, LCData, 260) || !GetLocaleInfoW(0x400u, 0x5Au, v22, 260) )
      return (unsigned int)HrGetLastError();
    v10 = -1;
    pszEscaped[0] = 0;
    pszUrl[0] = 0;
    v25[0] = 0;
    if ( a3 )
    {
      v11 = StringCchCopyW(pszEscaped, 0x824u, a3);
      if ( v11 < 0 )
        return (unsigned int)v11;
      v12 = -1;
      do
        ++v12;
      while ( pszEscaped[v12] );
      for ( i = 0; (int)i < (int)v12; i = (unsigned int)(i + 1) )
      {
        if ( pszEscaped[(int)i] == 44 )
        {
          pszEscaped[(int)i] = 32;
        }
        else if ( pszEscaped[(int)i] == 46 && (int)i < (int)v12 - 1 && pszEscaped[(int)i + 1] <= 0x20u )
        {
          v14 = 0x100002400LL;
          if ( _bittest64(&v14, pszEscaped[(int)i + 1]) )
          {
            v15 = 2LL * (int)i + 2;
            if ( v15 >= 0x1048 )
              _report_rangecheckfailure(i, v12, v15, 0x100002400LL);
            *(WCHAR *)((char *)pszEscaped + v15) = 0;
            break;
          }
        }
      }
      v11 = HrSHUnicodeToAnsiCP(0xFDE9u, pszEscaped, v25, 2084, &pcchEscaped);
      if ( v11 < 0 )
        return (unsigned int)v11;
      v11 = StringCchPrintfW(pszUrl, 0x824u, L"%S", v25);
      if ( v11 < 0 )
        return (unsigned int)v11;
      pcchEscaped = 2084;
      v11 = UrlEscapeW(pszUrl, pszEscaped, &pcchEscaped, 0x3000u);
      if ( v11 < 0 )
        return (unsigned int)v11;
    }
    v16 = (a2 & 1) != 0
        ? StringCchPrintfW(
            v26,
            0x824u,
            L"https://r.office.microsoft.com/r/rlidWebNews?clid=%s-%s&query=\"%s\"",
            LCData,
            v22,
            pszEscaped)
        : StringCchPrintfW(v26, 0x824u, L"https://r.office.microsoft.com/r/rlidWebNews?clid=%s-%s", LCData, v22);
    v11 = v16;
    if ( v16 < 0 )
      return (unsigned int)v11;
    do
      ++v10;
    while ( v26[v10] );
    v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (unsigned int)(v10 + 1));
    if ( v17 )
    {
      v11 = StringCchCopyW(v17, (unsigned int)(v10 + 1), v26);
      if ( v11 < 0 )
        LocalFree(v18);
      else
        *a5 = (unsigned __int16 *)v18;
    }
    else
    {
      return (unsigned int)HrGetLastError();
    }
    return (unsigned int)v11;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180006ac0  mov     [rsp-8+arg_8], rbx
0x180006ac5  push    rbp
0x180006ac6  push    rsi
0x180006ac7  push    rdi
0x180006ac8  push    r12
0x180006aca  push    r13
0x180006acc  push    r14
0x180006ace  push    r15
0x180006ad0  lea     rbp, [rsp-3C90h]
0x180006ad8  mov     eax, 3D90h
0x180006add  call    _alloca_probe
0x180006ae2  sub     rsp, rax
0x180006ae5  mov     rax, cs:__security_cookie
0x180006aec  xor     rax, rsp
0x180006aef  mov     [rbp+3CC0h+var_40], rax
0x180006af6  mov     r15, [rbp+3CC0h+arg_20]
0x180006afd  mov     rbx, r9
0x180006b00  mov     rsi, r8
0x180006b03  mov     r12d, edx
0x180006b06  mov     r14, rcx
0x180006b09  call    cs:__imp_GetThreadLocale
0x180006b0f  xor     r13d, r13d
0x180006b12  mov     edi, eax
0x180006b14  mov     [rbp+3CC0h+var_20E0], r13w
0x180006b1c  test    r14, r14
0x180006b1f  jz      loc_180006DCE
0x180006b25  test    r15, r15
0x180006b28  jz      loc_180006DCE
0x180006b2e  mov     eax, dword ptr cs:asc_180016BB8; "{}"
0x180006b34  lea     rdx, [rsp+3DC0h+pszTrimChars]; pszTrimChars
0x180006b39  mov     dword ptr [rsp+3DC0h+pszTrimChars], eax
0x180006b3d  mov     rcx, r14; psz
0x180006b40  movzx   eax, word ptr cs:asc_180016BB8+4; ""
0x180006b47  mov     [rsp+3DC0h+var_3D88], ax
0x180006b4c  call    cs:__imp_StrTrimW
0x180006b52  test    rbx, rbx
0x180006b55  jz      short loc_180006B5A
0x180006b57  movzx   edi, word ptr [rbx]
0x180006b5a  mov     ebx, 104h
0x180006b5f  mov     [rbp+3CC0h+LCData], r13w
0x180006b67  mov     r9d, ebx; cchData
0x180006b6a  mov     [rsp+3DC0h+var_3D80], r13w
0x180006b70  lea     r8, [rbp+3CC0h+LCData]; lpLCData
0x180006b77  mov     edx, 59h ; 'Y'; LCType
0x180006b7c  mov     ecx, edi; Locale
0x180006b7e  call    cs:__imp_GetLocaleInfoW
0x180006b84  test    eax, eax
0x180006b86  jz      loc_180006DC3
0x180006b8c  mov     r9d, ebx; cchData
0x180006b8f  lea     r8, [rsp+3DC0h+var_3D80]; lpLCData
0x180006b94  mov     edx, 5Ah ; 'Z'; LCType
0x180006b99  mov     ecx, 400h; Locale
0x180006b9e  call    cs:__imp_GetLocaleInfoW
0x180006ba4  test    eax, eax
0x180006ba6  jz      loc_180006DC3
0x180006bac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006bb0  mov     [rbp+3CC0h+pszEscaped], r13w
0x180006bb8  mov     [rbp+3CC0h+pszUrl], r13w
0x180006bc0  mov     r14d, 824h
0x180006bc6  mov     [rbp+3CC0h+var_2910], r13b
0x180006bcd  test    rsi, rsi
0x180006bd0  jz      loc_180006D12
0x180006bd6  mov     r8, rsi; unsigned __int16 *
0x180006bd9  lea     rcx, [rbp+3CC0h+pszEscaped]; unsigned __int16 *
0x180006be0  mov     edx, r14d; unsigned __int64
0x180006be3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006be8  mov     ebx, eax
0x180006bea  test    eax, eax
0x180006bec  js      loc_180006DCA
0x180006bf2  lea     rax, [rbp+3CC0h+pszEscaped]
0x180006bf9  mov     rdx, rdi
0x180006bfc  inc     rdx
0x180006bff  cmp     [rax+rdx*2], r13w
0x180006c04  jnz     short loc_180006BFC
0x180006c06  mov     ecx, r13d
0x180006c09  mov     r10d, 20h ; ' '
0x180006c0f  cmp     ecx, edx
0x180006c11  jge     short loc_180006C8E
0x180006c13  movsxd  r8, ecx
0x180006c16  mov     eax, 2Ch ; ','
0x180006c1b  cmp     ax, [rbp+r8*2+3CC0h+pszEscaped]
0x180006c24  jnz     short loc_180006C31
0x180006c26  mov     [rbp+r8*2+3CC0h+pszEscaped], r10w
0x180006c2f  jmp     short loc_180006C6C
0x180006c31  mov     eax, 2Eh ; '.'
0x180006c36  cmp     ax, [rbp+r8*2+3CC0h+pszEscaped]
0x180006c3f  jnz     short loc_180006C6C
0x180006c41  lea     eax, [rdx-1]
0x180006c44  cmp     ecx, eax
0x180006c46  jge     short loc_180006C6C
0x180006c48  cmp     [rbp+r8*2+3CC0h+var_395E], r10w
0x180006c51  ja      short loc_180006C6C
0x180006c53  movzx   eax, [rbp+r8*2+3CC0h+var_395E]
0x180006c5c  mov     r9, 100002400h
0x180006c66  bt      r9, rax
0x180006c6a  jb      short loc_180006C70
0x180006c6c  inc     ecx
0x180006c6e  jmp     short loc_180006C0F
0x180006c70  lea     r8, ds:2[r8*2]
0x180006c78  cmp     r8, 1048h
0x180006c7f  jnb     loc_180006D4D
0x180006c85  mov     [rbp+r8+3CC0h+pszEscaped], r13w
0x180006c8e  lea     rax, [rsp+3DC0h+pcchEscaped]
0x180006c93  mov     r9d, r14d; int
0x180006c96  lea     r8, [rbp+3CC0h+var_2910]; char *
0x180006c9d  mov     [rsp+3DC0h+var_3DA0], rax; unsigned int *
0x180006ca2  lea     rdx, [rbp+3CC0h+pszEscaped]; unsigned __int16 *
0x180006ca9  mov     ecx, 0FDE9h; unsigned int
0x180006cae  call    ?HrSHUnicodeToAnsiCP@@YAJIPEBGPEADHPEAK@Z; HrSHUnicodeToAnsiCP(uint,ushort const *,char *,int,ulong *)
0x180006cb3  mov     ebx, eax
0x180006cb5  test    eax, eax
0x180006cb7  js      loc_180006DCA
0x180006cbd  lea     r9, [rbp+3CC0h+var_2910]
0x180006cc4  mov     rdx, r14; unsigned __int64
0x180006cc7  lea     r8, aS_0; "%S"
0x180006cce  lea     rcx, [rbp+3CC0h+pszUrl]; unsigned __int16 *
0x180006cd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006cda  mov     ebx, eax
0x180006cdc  test    eax, eax
0x180006cde  js      loc_180006DCA
0x180006ce4  mov     r9d, 3000h; dwFlags
0x180006cea  mov     [rsp+3DC0h+pcchEscaped], r14d
0x180006cef  lea     r8, [rsp+3DC0h+pcchEscaped]; pcchEscaped
0x180006cf4  lea     rdx, [rbp+3CC0h+pszEscaped]; pszEscaped
0x180006cfb  lea     rcx, [rbp+3CC0h+pszUrl]; pszUrl
0x180006d02  call    cs:__imp_UrlEscapeW
0x180006d08  mov     ebx, eax
0x180006d0a  test    eax, eax
0x180006d0c  js      loc_180006DCA
0x180006d12  lea     r9, [rbp+3CC0h+LCData]
0x180006d19  mov     rdx, r14; unsigned __int64
0x180006d1c  lea     rcx, [rbp+3CC0h+var_20E0]; unsigned __int16 *
0x180006d23  test    r12b, 1
0x180006d27  jz      short loc_180006D53
0x180006d29  lea     rax, [rbp+3CC0h+pszEscaped]
0x180006d30  mov     [rsp+3DC0h+var_3D98], rax
0x180006d35  lea     r8, c_szHelpQueryUrlFmt; "https://r.office.microsoft.com/r/rlidWe"...
0x180006d3c  lea     rax, [rsp+3DC0h+var_3D80]
0x180006d41  mov     [rsp+3DC0h+var_3DA0], rax
0x180006d46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d4b  jmp     short loc_180006D69
0x180006d4d  call    __report_rangecheckfailure
0x180006d53  lea     rax, [rsp+3DC0h+var_3D80]
0x180006d58  lea     r8, c_szHelpDefaultUrlFmt; "https://r.office.microsoft.com/r/rlidWe"...
0x180006d5f  mov     [rsp+3DC0h+var_3DA0], rax
0x180006d64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d69  mov     ebx, eax
0x180006d6b  test    eax, eax
0x180006d6d  js      short loc_180006DCA
0x180006d6f  lea     rax, [rbp+3CC0h+var_20E0]
0x180006d76  inc     rdi
0x180006d79  cmp     [rax+rdi*2], r13w
0x180006d7e  jnz     short loc_180006D76
0x180006d80  lea     eax, [rdi+1]
0x180006d83  mov     ecx, 40h ; '@'; uFlags
0x180006d88  lea     rdx, [rax+rax]; uBytes
0x180006d8c  mov     ebx, eax
0x180006d8e  call    cs:__imp_LocalAlloc
0x180006d94  mov     r11, rax
0x180006d97  test    rax, rax
0x180006d9a  jz      short loc_180006DC3
0x180006d9c  lea     r8, [rbp+3CC0h+var_20E0]; unsigned __int16 *
0x180006da3  mov     edx, ebx; unsigned __int64
0x180006da5  mov     rcx, rax; unsigned __int16 *
0x180006da8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006dad  mov     ebx, eax
0x180006daf  test    eax, eax
0x180006db1  js      short loc_180006DB8
0x180006db3  mov     [r15], r11
0x180006db6  jmp     short loc_180006DCA
0x180006db8  mov     rcx, r11; hMem
0x180006dbb  call    cs:__imp_LocalFree
0x180006dc1  jmp     short loc_180006DCA
0x180006dc3  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006dc8  mov     ebx, eax
0x180006dca  mov     eax, ebx
0x180006dcc  jmp     short loc_180006DD3
0x180006dce  mov     eax, 80070057h
0x180006dd3  mov     rcx, [rbp+3CC0h+var_40]
0x180006dda  xor     rcx, rsp; StackCookie
0x180006ddd  call    __security_check_cookie
0x180006de2  mov     rbx, [rsp+3DC0h+arg_8]
0x180006dea  add     rsp, 3D90h
0x180006df1  pop     r15
0x180006df3  pop     r14
0x180006df5  pop     r13
0x180006df7  pop     r12
0x180006df9  pop     rdi
0x180006dfa  pop     rsi
0x180006dfb  pop     rbp
0x180006dfc  retn
```
