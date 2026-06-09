# CFDRPlugin::GenerateLogPathAndFileName(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,ulong)

- ea: `0x1400569f0`
- end: `0x140056cb4`
- name: `?GenerateLogPathAndFileName@CFDRPlugin@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0K@Z`
- size: `708`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140058034`

## callees

- `0x140002748`
- `0x14000b580`
- `0x14000e658`
- `0x140014ee4`
- `0x1400569f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140056b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140056b3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140056b4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140056b4a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x140056a82`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x140056a82`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::GenerateLogPathAndFileName(WCHAR *a1, wchar_t **a2, wchar_t **a3)
{
  const struct std::nothrow_t *v5; // rdx
  LPWSTR v6; // rsi
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  HRESULT v9; // ebx
  CUserModeHangReport *v10; // rcx
  __int64 v11; // rdx
  const struct std::nothrow_t **unique_for; // rax
  wchar_t *v13; // rcx
  const struct std::nothrow_t **v14; // rax
  wchar_t *v15; // rcx
  DWORD TickCount; // [rsp+28h] [rbp-50h]
  DWORD CurrentThreadId; // [rsp+30h] [rbp-48h]
  LPWSTR pszPath; // [rsp+80h] [rbp+8h] BYREF

  pszPath = a1;
  if ( a3 && a2 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&pszPath, 260);
    v6 = pszPath;
    if ( !pszPath )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_8;
      }
      v8 = (unsigned int)((_DWORD)pszPath + 60);
LABEL_7:
      WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_8:
      v9 = -2147024882;
      goto LABEL_39;
    }
    v9 = SHGetFolderPathW(0, 28, 0, 0, pszPath);
    if ( v9 >= 0 )
    {
      unique_for = (const struct std::nothrow_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&pszPath, 260);
      v5 = *unique_for;
      *unique_for = 0;
      v13 = *a3;
      *a3 = (wchar_t *)v5;
      if ( v13 )
        operator delete(v13, v5);
      if ( pszPath )
        operator delete(pszPath, v5);
      if ( !*a3 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_8;
        }
        v8 = 62;
        goto LABEL_7;
      }
      CurrentThreadId = GetCurrentThreadId();
      TickCount = GetTickCount();
      v9 = StringCchPrintfW(
             *a3,
             0x104u,
             L"%s\\%s\\%u-%u.etl",
             v6,
             L"Microsoft\\Windows\\FDR",
             TickCount,
             CurrentThreadId);
      if ( v9 >= 0 )
      {
        v14 = (const struct std::nothrow_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&pszPath, 260);
        v5 = *v14;
        *v14 = 0;
        v15 = *a2;
        *a2 = (wchar_t *)v5;
        if ( v15 )
          operator delete(v15, v5);
        if ( pszPath )
          operator delete(pszPath, v5);
        if ( !*a2 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_8;
          }
          v8 = 64;
          goto LABEL_7;
        }
        v9 = StringCchPrintfW(*a2, 0x104u, L"%s\\%s", v6, L"Microsoft\\Windows\\FDR");
        if ( v9 >= 0 )
        {
          v9 = 0;
          goto LABEL_39;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 65;
          goto LABEL_13;
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 63;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 61;
LABEL_13:
        WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      }
    }
LABEL_39:
    if ( v6 )
      operator delete(v6, v5);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400569f0  mov     rax, rsp
0x1400569f3  mov     [rax+8], rcx
0x1400569f7  push    rbx
0x1400569f8  push    rsi
0x1400569f9  push    rdi
0x1400569fa  push    r12
0x1400569fc  push    r14
0x1400569fe  push    r15
0x140056a00  sub     rsp, 48h
0x140056a04  mov     rdi, r8
0x140056a07  mov     r14, rdx
0x140056a0a  test    r8, r8
0x140056a0d  jz      loc_140056C72
0x140056a13  test    rdx, rdx
0x140056a16  jz      loc_140056C72
0x140056a1c  mov     r15d, 104h
0x140056a22  lea     rcx, [rax+8]
0x140056a26  mov     edx, r15d
0x140056a29  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140056a2e  mov     rsi, [rsp+78h+arg_0]
0x140056a36  test    rsi, rsi
0x140056a39  jnz     short loc_140056A71
0x140056a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a42  lea     rax, WPP_GLOBAL_Control
0x140056a49  cmp     rcx, rax
0x140056a4c  jz      short loc_140056A67
0x140056a4e  test    byte ptr [rcx+1Ch], 1
0x140056a52  jz      short loc_140056A67
0x140056a54  lea     edx, [rsi+3Ch]
0x140056a57  mov     rcx, [rcx+10h]
0x140056a5b  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140056a62  call    WPP_SF_
0x140056a67  mov     ebx, 8007000Eh
0x140056a6c  jmp     loc_140056C61
0x140056a71  xor     r9d, r9d; dwFlags
0x140056a74  mov     [rsp+78h+pszPath], rsi; pszPath
0x140056a79  xor     r8d, r8d; hToken
0x140056a7c  xor     ecx, ecx; hwnd
0x140056a7e  lea     edx, [r9+1Ch]; csidl
0x140056a82  call    cs:__imp_SHGetFolderPathW
0x140056a89  nop     dword ptr [rax+rax+00h]
0x140056a8e  mov     ebx, eax
0x140056a90  test    eax, eax
0x140056a92  jns     short loc_140056ACF
0x140056a94  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a9b  lea     rax, WPP_GLOBAL_Control
0x140056aa2  cmp     rcx, rax
0x140056aa5  jz      loc_140056C61
0x140056aab  test    byte ptr [rcx+1Ch], 1
0x140056aaf  jz      loc_140056C61
0x140056ab5  mov     edx, 3Dh ; '='
0x140056aba  mov     rcx, [rcx+10h]
0x140056abe  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140056ac5  call    WPP_SF_
0x140056aca  jmp     loc_140056C61
0x140056acf  mov     rdx, r15
0x140056ad2  lea     rcx, [rsp+78h+arg_0]
0x140056ada  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140056adf  mov     rdx, [rax]; struct std::nothrow_t *
0x140056ae2  mov     qword ptr [rax], 0
0x140056ae9  mov     rcx, [rdi]; void *
0x140056aec  mov     [rdi], rdx
0x140056aef  test    rcx, rcx
0x140056af2  jz      short loc_140056AF9
0x140056af4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056af9  mov     rcx, [rsp+78h+arg_0]; void *
0x140056b01  test    rcx, rcx
0x140056b04  jz      short loc_140056B0B
0x140056b06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056b0b  cmp     qword ptr [rdi], 0
0x140056b0f  jnz     short loc_140056B3C
0x140056b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140056b18  lea     rax, WPP_GLOBAL_Control
0x140056b1f  cmp     rcx, rax
0x140056b22  jz      loc_140056A67
0x140056b28  test    byte ptr [rcx+1Ch], 1
0x140056b2c  jz      loc_140056A67
0x140056b32  mov     edx, 3Eh ; '>'
0x140056b37  jmp     loc_140056A57
0x140056b3c  call    cs:__imp_GetCurrentThreadId
0x140056b43  nop     dword ptr [rax+rax+00h]
0x140056b48  mov     ebx, eax
0x140056b4a  call    cs:__imp_GetTickCount
0x140056b51  nop     dword ptr [rax+rax+00h]
0x140056b56  mov     rcx, [rdi]; wchar_t *
0x140056b59  lea     r12, aMicrosoftWindo; "Microsoft\\Windows\\FDR"
0x140056b60  mov     [rsp+78h+var_48], ebx
0x140056b64  lea     r8, aSSUUEtl; "%s\\%s\\%u-%u.etl"
0x140056b6b  mov     [rsp+78h+var_50], eax
0x140056b6f  mov     r9, rsi
0x140056b72  mov     rdx, r15; unsigned __int64
0x140056b75  mov     [rsp+78h+pszPath], r12
0x140056b7a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140056b7f  mov     ebx, eax
0x140056b81  test    eax, eax
0x140056b83  jns     short loc_140056BB0
0x140056b85  mov     rcx, cs:WPP_GLOBAL_Control
0x140056b8c  lea     rax, WPP_GLOBAL_Control
0x140056b93  cmp     rcx, rax
0x140056b96  jz      loc_140056C61
0x140056b9c  test    byte ptr [rcx+1Ch], 1
0x140056ba0  jz      loc_140056C61
0x140056ba6  mov     edx, 3Fh ; '?'
0x140056bab  jmp     loc_140056ABA
0x140056bb0  mov     rdx, r15
0x140056bb3  lea     rcx, [rsp+78h+arg_0]
0x140056bbb  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140056bc0  mov     rdx, [rax]; struct std::nothrow_t *
0x140056bc3  mov     qword ptr [rax], 0
0x140056bca  mov     rcx, [r14]; void *
0x140056bcd  mov     [r14], rdx
0x140056bd0  test    rcx, rcx
0x140056bd3  jz      short loc_140056BDA
0x140056bd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056bda  mov     rcx, [rsp+78h+arg_0]; void *
0x140056be2  test    rcx, rcx
0x140056be5  jz      short loc_140056BEC
0x140056be7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056bec  mov     rcx, [r14]; wchar_t *
0x140056bef  test    rcx, rcx
0x140056bf2  jnz     short loc_140056C1F
0x140056bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140056bfb  lea     rax, WPP_GLOBAL_Control
0x140056c02  cmp     rcx, rax
0x140056c05  jz      loc_140056A67
0x140056c0b  test    byte ptr [rcx+1Ch], 1
0x140056c0f  jz      loc_140056A67
0x140056c15  mov     edx, 40h ; '@'
0x140056c1a  jmp     loc_140056A57
0x140056c1f  mov     r9, rsi
0x140056c22  mov     [rsp+78h+pszPath], r12
0x140056c27  lea     r8, aSS_3; "%s\\%s"
0x140056c2e  mov     rdx, r15; unsigned __int64
0x140056c31  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140056c36  mov     ebx, eax
0x140056c38  test    eax, eax
0x140056c3a  jns     short loc_140056C5F
0x140056c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c43  lea     rax, WPP_GLOBAL_Control
0x140056c4a  cmp     rcx, rax
0x140056c4d  jz      short loc_140056C61
0x140056c4f  test    byte ptr [rcx+1Ch], 1
0x140056c53  jz      short loc_140056C61
0x140056c55  mov     edx, 41h ; 'A'
0x140056c5a  jmp     loc_140056ABA
0x140056c5f  xor     ebx, ebx
0x140056c61  test    rsi, rsi
0x140056c64  jz      short loc_140056C6E
0x140056c66  mov     rcx, rsi; void *
0x140056c69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056c6e  mov     eax, ebx
0x140056c70  jmp     short loc_140056CA5
0x140056c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c79  lea     rax, WPP_GLOBAL_Control
0x140056c80  cmp     rcx, rax
0x140056c83  jz      short loc_140056CA0
0x140056c85  test    byte ptr [rcx+1Ch], 1
0x140056c89  jz      short loc_140056CA0
0x140056c8b  mov     rcx, [rcx+10h]
0x140056c8f  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140056c96  mov     edx, 3Bh ; ';'
0x140056c9b  call    WPP_SF_
0x140056ca0  mov     eax, 80070057h
0x140056ca5  add     rsp, 48h
0x140056ca9  pop     r15
0x140056cab  pop     r14
0x140056cad  pop     r12
0x140056caf  pop     rdi
0x140056cb0  pop     rsi
0x140056cb1  pop     rbx
0x140056cb2  retn
```
