# CFDRPlugin::GenerateLogPathAndFileName(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,ulong)

- ea: `0x1400530a8`
- end: `0x140053359`
- name: `?GenerateLogPathAndFileName@CFDRPlugin@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0K@Z`
- size: `689`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14005463c`

## callees

- `0x140002728`
- `0x14000b540`
- `0x14000e3c4`
- `0x14001444c`
- `0x1400530a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400531ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400531ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400531f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400531f6`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x14005313a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x14005313a`

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
0x1400530a8  mov     rax, rsp
0x1400530ab  mov     [rax+8], rcx
0x1400530af  push    rbx
0x1400530b0  push    rsi
0x1400530b1  push    rdi
0x1400530b2  push    r12
0x1400530b4  push    r14
0x1400530b6  push    r15
0x1400530b8  sub     rsp, 48h
0x1400530bc  mov     rdi, r8
0x1400530bf  mov     r14, rdx
0x1400530c2  test    r8, r8
0x1400530c5  jz      loc_140053318
0x1400530cb  test    rdx, rdx
0x1400530ce  jz      loc_140053318
0x1400530d4  mov     r15d, 104h
0x1400530da  lea     rcx, [rax+8]
0x1400530de  mov     edx, r15d
0x1400530e1  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1400530e6  mov     rsi, [rsp+78h+arg_0]
0x1400530ee  test    rsi, rsi
0x1400530f1  jnz     short loc_140053129
0x1400530f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400530fa  lea     rax, WPP_GLOBAL_Control
0x140053101  cmp     rcx, rax
0x140053104  jz      short loc_14005311F
0x140053106  test    byte ptr [rcx+1Ch], 1
0x14005310a  jz      short loc_14005311F
0x14005310c  lea     edx, [rsi+3Ch]
0x14005310f  mov     rcx, [rcx+10h]
0x140053113  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005311a  call    WPP_SF_
0x14005311f  mov     ebx, 8007000Eh
0x140053124  jmp     loc_140053307
0x140053129  xor     r9d, r9d; dwFlags
0x14005312c  mov     [rsp+78h+pszPath], rsi; pszPath
0x140053131  xor     r8d, r8d; hToken
0x140053134  xor     ecx, ecx; hwnd
0x140053136  lea     edx, [r9+1Ch]; csidl
0x14005313a  call    cs:__imp_SHGetFolderPathW
0x140053140  mov     ebx, eax
0x140053142  test    eax, eax
0x140053144  jns     short loc_140053181
0x140053146  mov     rcx, cs:WPP_GLOBAL_Control
0x14005314d  lea     rax, WPP_GLOBAL_Control
0x140053154  cmp     rcx, rax
0x140053157  jz      loc_140053307
0x14005315d  test    byte ptr [rcx+1Ch], 1
0x140053161  jz      loc_140053307
0x140053167  mov     edx, 3Dh ; '='
0x14005316c  mov     rcx, [rcx+10h]
0x140053170  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140053177  call    WPP_SF_
0x14005317c  jmp     loc_140053307
0x140053181  mov     rdx, r15
0x140053184  lea     rcx, [rsp+78h+arg_0]
0x14005318c  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140053191  mov     rdx, [rax]; struct std::nothrow_t *
0x140053194  mov     qword ptr [rax], 0
0x14005319b  mov     rcx, [rdi]; void *
0x14005319e  mov     [rdi], rdx
0x1400531a1  test    rcx, rcx
0x1400531a4  jz      short loc_1400531AB
0x1400531a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400531ab  mov     rcx, [rsp+78h+arg_0]; void *
0x1400531b3  test    rcx, rcx
0x1400531b6  jz      short loc_1400531BD
0x1400531b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400531bd  cmp     qword ptr [rdi], 0
0x1400531c1  jnz     short loc_1400531EE
0x1400531c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400531ca  lea     rax, WPP_GLOBAL_Control
0x1400531d1  cmp     rcx, rax
0x1400531d4  jz      loc_14005311F
0x1400531da  test    byte ptr [rcx+1Ch], 1
0x1400531de  jz      loc_14005311F
0x1400531e4  mov     edx, 3Eh ; '>'
0x1400531e9  jmp     loc_14005310F
0x1400531ee  call    cs:__imp_GetCurrentThreadId
0x1400531f4  mov     ebx, eax
0x1400531f6  call    cs:__imp_GetTickCount
0x1400531fc  mov     rcx, [rdi]; wchar_t *
0x1400531ff  lea     r12, aMicrosoftWindo; "Microsoft\\Windows\\FDR"
0x140053206  mov     [rsp+78h+var_48], ebx
0x14005320a  lea     r8, aSSUUEtl; "%s\\%s\\%u-%u.etl"
0x140053211  mov     [rsp+78h+var_50], eax
0x140053215  mov     r9, rsi
0x140053218  mov     rdx, r15; unsigned __int64
0x14005321b  mov     [rsp+78h+pszPath], r12
0x140053220  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140053225  mov     ebx, eax
0x140053227  test    eax, eax
0x140053229  jns     short loc_140053256
0x14005322b  mov     rcx, cs:WPP_GLOBAL_Control
0x140053232  lea     rax, WPP_GLOBAL_Control
0x140053239  cmp     rcx, rax
0x14005323c  jz      loc_140053307
0x140053242  test    byte ptr [rcx+1Ch], 1
0x140053246  jz      loc_140053307
0x14005324c  mov     edx, 3Fh ; '?'
0x140053251  jmp     loc_14005316C
0x140053256  mov     rdx, r15
0x140053259  lea     rcx, [rsp+78h+arg_0]
0x140053261  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140053266  mov     rdx, [rax]; struct std::nothrow_t *
0x140053269  mov     qword ptr [rax], 0
0x140053270  mov     rcx, [r14]; void *
0x140053273  mov     [r14], rdx
0x140053276  test    rcx, rcx
0x140053279  jz      short loc_140053280
0x14005327b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140053280  mov     rcx, [rsp+78h+arg_0]; void *
0x140053288  test    rcx, rcx
0x14005328b  jz      short loc_140053292
0x14005328d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140053292  mov     rcx, [r14]; wchar_t *
0x140053295  test    rcx, rcx
0x140053298  jnz     short loc_1400532C5
0x14005329a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400532a1  lea     rax, WPP_GLOBAL_Control
0x1400532a8  cmp     rcx, rax
0x1400532ab  jz      loc_14005311F
0x1400532b1  test    byte ptr [rcx+1Ch], 1
0x1400532b5  jz      loc_14005311F
0x1400532bb  mov     edx, 40h ; '@'
0x1400532c0  jmp     loc_14005310F
0x1400532c5  mov     r9, rsi
0x1400532c8  mov     [rsp+78h+pszPath], r12
0x1400532cd  lea     r8, aSS_3; "%s\\%s"
0x1400532d4  mov     rdx, r15; unsigned __int64
0x1400532d7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400532dc  mov     ebx, eax
0x1400532de  test    eax, eax
0x1400532e0  jns     short loc_140053305
0x1400532e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400532e9  lea     rax, WPP_GLOBAL_Control
0x1400532f0  cmp     rcx, rax
0x1400532f3  jz      short loc_140053307
0x1400532f5  test    byte ptr [rcx+1Ch], 1
0x1400532f9  jz      short loc_140053307
0x1400532fb  mov     edx, 41h ; 'A'
0x140053300  jmp     loc_14005316C
0x140053305  xor     ebx, ebx
0x140053307  test    rsi, rsi
0x14005330a  jz      short loc_140053314
0x14005330c  mov     rcx, rsi; void *
0x14005330f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140053314  mov     eax, ebx
0x140053316  jmp     short loc_14005334B
0x140053318  mov     rcx, cs:WPP_GLOBAL_Control
0x14005331f  lea     rax, WPP_GLOBAL_Control
0x140053326  cmp     rcx, rax
0x140053329  jz      short loc_140053346
0x14005332b  test    byte ptr [rcx+1Ch], 1
0x14005332f  jz      short loc_140053346
0x140053331  mov     rcx, [rcx+10h]
0x140053335  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005333c  mov     edx, 3Bh ; ';'
0x140053341  call    WPP_SF_
0x140053346  mov     eax, 80070057h
0x14005334b  add     rsp, 48h
0x14005334f  pop     r15
0x140053351  pop     r14
0x140053353  pop     r12
0x140053355  pop     rdi
0x140053356  pop     rsi
0x140053357  pop     rbx
0x140053358  retn
```
