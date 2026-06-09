# AddGlobalOptions(wchar_t * *,wchar_t *,CConfig *)

- ea: `0x14000b454`
- end: `0x14000ba30`
- name: `?AddGlobalOptions@@YAJPEAPEA_WPEA_WPEAVCConfig@@@Z`
- size: `1500`
- prototype: `int(wchar_t **, wchar_t *, struct CConfig *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000aca8`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000952c`
- `0x14000a1bc`
- `0x14000b454`
- `0x140011100`
- `0x1400113d4`
- `0x140011884`
- `0x140011d50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000b58d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000b58d`

## string_xrefs

- `0x14000b4ad`: `Failed to allocate memory for command line.`
- `0x14000b527`: `Failed to allocate memory for command line.`
- `0x14000b649`: `Failed to allocate memory for command line.`
- `0x14000b6d5`: `Failed to allocate memory for command line.`
- `0x14000b741`: `Failed to allocate memory for command line.`
- `0x14000b7ac`: `Failed to allocate memory for command line.`
- `0x14000b825`: `Failed to allocate memory for command line.`
- `0x14000b88d`: `Failed to allocate memory for command line.`
- `0x14000b901`: `Failed to allocate memory for command line.`
- `0x14000b96c`: `Failed to allocate memory for command line.`
- `0x14000b5a4`: `Invalid image path.`
- `0x14000b9bf`: ` /logpath:"%s.txt"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddGlobalOptions(wchar_t **a1, wchar_t *a2, struct CConfig *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // edx
  __int64 v8; // rdx
  CConfig *v9; // rcx
  const wchar_t *OfflineWinDirPath; // rax
  int v11; // eax
  int v12; // edx
  unsigned __int64 v13; // r9
  wchar_t *v14; // rbx
  wchar_t *v15; // rax
  int v16; // edx
  __int64 v17; // rax
  int v18; // eax
  int v19; // edx
  __int64 v20; // r9
  int v21; // eax
  int v22; // edx
  int v23; // eax
  int v24; // edx
  int v25; // eax
  int v26; // edx
  int v27; // eax
  int v28; // edx
  int v29; // eax
  int v30; // edx
  int v31; // eax
  int v32; // edx
  int v33; // eax
  int v34; // edx
  int v35; // eax
  int v36; // eax
  unsigned int v38; // [rsp+20h] [rbp-40h]
  unsigned int v39[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v40; // [rsp+38h] [rbp-28h] BYREF
  wchar_t *Str[2]; // [rsp+40h] [rbp-20h] BYREF
  int v42; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  Str[1] = (wchar_t *)-2LL;
  v40 = 0;
  Str[0] = 0;
  v5 = SczAllocFormatted(a1, L"\"%sdism.exe\"", a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    v42 = v5;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v39 = &v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v39);
    }
    v8 = 299;
    goto LABEL_10;
  }
  if ( !CConfig::GetOfflineWinDirPath(a3) )
  {
    v25 = SczAllocConcatSz(a1, L" /online");
    v6 = v25;
    if ( v25 < 0 )
    {
      v42 = v25;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {}",
          (__int64)v39);
      }
      v8 = 329;
      goto LABEL_10;
    }
LABEL_40:
    if ( *((_QWORD *)a3 + 10) )
    {
      v27 = SczAllocFormatted(&v40, L" /scratchdir:\"%s\"");
      v6 = v27;
      if ( v27 < 0 )
      {
        v42 = v27;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v39 = &v42;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v28,
            3,
            (unsigned int)": {}",
            (__int64)v39);
        }
        v8 = 336;
        goto LABEL_10;
      }
      v29 = SczAllocConcatSz(a1, v40);
      v6 = v29;
      if ( v29 < 0 )
      {
        v42 = v29;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v39 = &v42;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v30,
            3,
            (unsigned int)": {}",
            (__int64)v39);
        }
        v8 = 338;
        goto LABEL_10;
      }
    }
    if ( *((_DWORD *)a3 + 80) && (v31 = SczAllocConcatSz(a1, L" /quiet"), v6 = v31, v31 < 0) )
    {
      v42 = v31;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v32,
          3,
          (unsigned int)": {}",
          (__int64)v39);
      }
      v8 = 343;
    }
    else
    {
      v33 = SczAllocConcatSz(a1, L" /norestart");
      v6 = v33;
      if ( v33 >= 0 )
      {
        if ( *((_QWORD *)a3 + 30) )
        {
          v35 = SczAllocFormatted(&v40, L" /logpath:\"%s.txt\"");
          v6 = v35;
          if ( v35 < 0 )
          {
            v13 = (unsigned int)v35;
            v8 = 350;
            goto LABEL_11;
          }
          v36 = SczAllocConcatSz(a1, v40);
          v6 = v36;
          if ( v36 < 0 )
          {
            v13 = (unsigned int)v36;
            v8 = 351;
            goto LABEL_11;
          }
        }
        v6 = 0;
        goto LABEL_64;
      }
      v42 = v33;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v34,
          3,
          (unsigned int)": {}",
          (__int64)v39);
      }
      v8 = 346;
    }
LABEL_10:
    v13 = v6;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
      (const char *)v13,
      v38);
    goto LABEL_64;
  }
  OfflineWinDirPath = CConfig::GetOfflineWinDirPath(v9);
  v11 = SczAllocFromSz(Str, OfflineWinDirPath);
  v6 = v11;
  if ( v11 < 0 )
  {
    v42 = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v39 = &v42;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v39);
    }
    v8 = 303;
    goto LABEL_10;
  }
  v14 = Str[0];
  v15 = wcsrchr(Str[0], 0x5Cu);
  if ( v15 )
  {
    *v15 = 0;
    v17 = -1;
    do
      ++v17;
    while ( v14[v17] );
    if ( v17 == 2 && v14[1] == 58 )
    {
      v18 = SczEnsureBackslashTerminated(Str);
      v6 = v18;
      if ( v18 < 0 )
      {
        v42 = v18;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v39 = &v42;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v19,
            3,
            (unsigned int)": {}",
            (__int64)v39);
        }
        v8 = 315;
        goto LABEL_10;
      }
      v14 = Str[0];
    }
    if ( *((_QWORD *)a3 + 35) == 2 )
      v20 = **((_QWORD **)a3 + 37);
    else
      v20 = 0;
    v21 = SczAllocFormatted(&v40, L" /image:\"%s\" /sysdrivedir:\"%s\"", v14, v20);
    v6 = v21;
    if ( v21 < 0 )
    {
      v42 = v21;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {}",
          (__int64)v39);
      }
      v8 = 323;
      goto LABEL_10;
    }
    v23 = SczAllocConcatSz(a1, v40);
    v6 = v23;
    if ( v23 < 0 )
    {
      v42 = v23;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v24,
          3,
          (unsigned int)": {}",
          (__int64)v39);
      }
      v8 = 325;
      goto LABEL_10;
    }
    goto LABEL_40;
  }
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid image path.");
    v42 = -2147024883;
    *(_QWORD *)v39 = &v42;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v16,
      3,
      (unsigned int)": {0}",
      (__int64)v39);
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x134,
         (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
         (const char *)0xD,
         v38);
LABEL_64:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(Str);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v40);
  return v6;
}

```

## disassembly

```asm
0x14000b454  push    rbp
0x14000b456  push    rbx
0x14000b457  push    rsi
0x14000b458  push    rdi
0x14000b459  push    r14
0x14000b45b  mov     rbp, rsp
0x14000b45e  sub     rsp, 60h
0x14000b462  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x14000b46a  mov     rax, cs:__security_cookie
0x14000b471  xor     rax, rsp
0x14000b474  mov     [rbp+var_8], rax
0x14000b478  mov     rdi, r8
0x14000b47b  mov     rsi, rcx
0x14000b47e  xor     r14d, r14d
0x14000b481  mov     [rbp+var_28], r14
0x14000b485  mov     [rbp+Str], r14
0x14000b489  mov     r8, rdx
0x14000b48c  lea     rdx, aSdismExe; "\"%sdism.exe\""
0x14000b493  call    SczAllocFormatted
0x14000b498  mov     ebx, eax
0x14000b49a  test    eax, eax
0x14000b49c  jns     short loc_14000B4F0
0x14000b49e  mov     [rbp+var_10], eax
0x14000b4a1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b4a8  test    rcx, rcx
0x14000b4ab  jz      short loc_14000B4E9
0x14000b4ad  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b4b4  lea     edi, [r14+3]
0x14000b4b8  mov     r8d, edi
0x14000b4bb  xor     edx, edx
0x14000b4bd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b4c2  lea     rax, [rbp+var_10]
0x14000b4c6  mov     qword ptr [rbp+var_30], rax
0x14000b4ca  lea     rax, [rbp+var_30]
0x14000b4ce  mov     qword ptr [rsp+60h+var_40], rax
0x14000b4d3  lea     r9, asc_14002D4FC; ": {}"
0x14000b4da  mov     r8d, edi
0x14000b4dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b4e4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b4e9  mov     edx, 12Bh
0x14000b4ee  jmp     short loc_14000B569
0x14000b4f0  mov     rcx, rdi; this
0x14000b4f3  call    ?GetOfflineWinDirPath@CConfig@@QEAAPEB_WXZ; CConfig::GetOfflineWinDirPath(void)
0x14000b4f8  test    rax, rax
0x14000b4fb  jz      loc_14000B788
0x14000b501  call    ?GetOfflineWinDirPath@CConfig@@QEAAPEB_WXZ; CConfig::GetOfflineWinDirPath(void)
0x14000b506  mov     rdx, rax
0x14000b509  lea     rcx, [rbp+Str]
0x14000b50d  call    SczAllocFromSz
0x14000b512  mov     ebx, eax
0x14000b514  test    eax, eax
0x14000b516  jns     short loc_14000B581
0x14000b518  mov     [rbp+var_10], eax
0x14000b51b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b522  test    rcx, rcx
0x14000b525  jz      short loc_14000B564
0x14000b527  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b52e  mov     edi, 3
0x14000b533  mov     r8d, edi
0x14000b536  xor     edx, edx
0x14000b538  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b53d  lea     rax, [rbp+var_10]
0x14000b541  mov     qword ptr [rbp+var_30], rax
0x14000b545  lea     rax, [rbp+var_30]
0x14000b549  mov     qword ptr [rsp+60h+var_40], rax; int
0x14000b54e  lea     r9, asc_14002D4FC; ": {}"
0x14000b555  mov     r8d, edi
0x14000b558  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b55f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b564  mov     edx, 12Fh; void *
0x14000b569  mov     r9d, ebx; char *
0x14000b56c  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000b573  mov     rcx, [rbp+28h]; this
0x14000b577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b57c  jmp     loc_14000BA04
0x14000b581  mov     edx, 5Ch ; '\'; Ch
0x14000b586  mov     rbx, [rbp+Str]
0x14000b58a  mov     rcx, rbx; Str
0x14000b58d  call    cs:__imp_wcsrchr
0x14000b593  test    rax, rax
0x14000b596  jnz     short loc_14000B608
0x14000b598  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b59f  test    rcx, rcx
0x14000b5a2  jz      short loc_14000B5E6
0x14000b5a4  lea     r9, aInvalidImagePa; "Invalid image path."
0x14000b5ab  lea     edi, [rax+3]
0x14000b5ae  mov     r8d, edi
0x14000b5b1  xor     edx, edx
0x14000b5b3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b5b8  mov     [rbp+var_10], 8007000Dh
0x14000b5bf  lea     rax, [rbp+var_10]
0x14000b5c3  mov     qword ptr [rbp+var_30], rax
0x14000b5c7  lea     rax, [rbp+var_30]
0x14000b5cb  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x14000b5d0  lea     r9, a0; ": {0}"
0x14000b5d7  mov     r8d, edi
0x14000b5da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b5e1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b5e6  mov     rcx, [rbp+28h]; this
0x14000b5ea  mov     r9d, 0Dh; char *
0x14000b5f0  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000b5f7  mov     edx, 134h; void *
0x14000b5fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000b601  mov     ebx, eax
0x14000b603  jmp     loc_14000BA04
0x14000b608  mov     [rax], r14w
0x14000b60c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b610  inc     rax
0x14000b613  cmp     [rbx+rax*2], r14w
0x14000b618  jnz     short loc_14000B610
0x14000b61a  cmp     rax, 2
0x14000b61e  jnz     short loc_14000B694
0x14000b620  mov     eax, 3Ah ; ':'
0x14000b625  cmp     ax, [rbx+2]
0x14000b629  jnz     short loc_14000B694
0x14000b62b  lea     rcx, [rbp+Str]
0x14000b62f  call    SczEnsureBackslashTerminated
0x14000b634  mov     ebx, eax
0x14000b636  test    eax, eax
0x14000b638  jns     short loc_14000B690
0x14000b63a  mov     [rbp+var_10], eax
0x14000b63d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b644  test    rcx, rcx
0x14000b647  jz      short loc_14000B686
0x14000b649  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b650  mov     edi, 3
0x14000b655  mov     r8d, edi
0x14000b658  xor     edx, edx
0x14000b65a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b65f  lea     rax, [rbp+var_10]
0x14000b663  mov     qword ptr [rbp+var_30], rax
0x14000b667  lea     rax, [rbp+var_30]
0x14000b66b  mov     qword ptr [rsp+60h+var_40], rax
0x14000b670  lea     r9, asc_14002D4FC; ": {}"
0x14000b677  mov     r8d, edi
0x14000b67a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b681  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b686  mov     edx, 13Bh
0x14000b68b  jmp     loc_14000B569
0x14000b690  mov     rbx, [rbp+Str]
0x14000b694  cmp     qword ptr [rdi+118h], 2
0x14000b69c  jnz     short loc_14000B6AA
0x14000b69e  mov     rax, [rdi+128h]
0x14000b6a5  mov     r9, [rax]
0x14000b6a8  jmp     short loc_14000B6AD
0x14000b6aa  mov     r9, r14
0x14000b6ad  mov     r8, rbx
0x14000b6b0  lea     rdx, aImageSSysdrive; " /image:\"%s\" /sysdrivedir:\"%s\""
0x14000b6b7  lea     rcx, [rbp+var_28]
0x14000b6bb  call    SczAllocFormatted
0x14000b6c0  mov     ebx, eax
0x14000b6c2  test    eax, eax
0x14000b6c4  jns     short loc_14000B71C
0x14000b6c6  mov     [rbp+var_10], eax
0x14000b6c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b6d0  test    rcx, rcx
0x14000b6d3  jz      short loc_14000B712
0x14000b6d5  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b6dc  mov     edi, 3
0x14000b6e1  mov     r8d, edi
0x14000b6e4  xor     edx, edx
0x14000b6e6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b6eb  lea     rax, [rbp+var_10]
0x14000b6ef  mov     qword ptr [rbp+var_30], rax
0x14000b6f3  lea     rax, [rbp+var_30]
0x14000b6f7  mov     qword ptr [rsp+60h+var_40], rax
0x14000b6fc  lea     r9, asc_14002D4FC; ": {}"
0x14000b703  mov     r8d, edi
0x14000b706  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b70d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b712  mov     edx, 143h
0x14000b717  jmp     loc_14000B569
0x14000b71c  mov     rdx, [rbp+var_28]
0x14000b720  mov     rcx, rsi
0x14000b723  call    SczAllocConcatSz
0x14000b728  mov     ebx, eax
0x14000b72a  test    eax, eax
0x14000b72c  jns     loc_14000B7F3
0x14000b732  mov     [rbp+var_10], eax
0x14000b735  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b73c  test    rcx, rcx
0x14000b73f  jz      short loc_14000B77E
0x14000b741  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b748  mov     edi, 3
0x14000b74d  mov     r8d, edi
0x14000b750  xor     edx, edx
0x14000b752  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b757  lea     rax, [rbp+var_10]
0x14000b75b  mov     qword ptr [rbp+var_30], rax
0x14000b75f  lea     rax, [rbp+var_30]
0x14000b763  mov     qword ptr [rsp+60h+var_40], rax
0x14000b768  lea     r9, asc_14002D4FC; ": {}"
0x14000b76f  mov     r8d, edi
0x14000b772  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b779  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b77e  mov     edx, 145h
0x14000b783  jmp     loc_14000B569
0x14000b788  lea     rdx, aOnline; " /online"
0x14000b78f  mov     rcx, rsi
0x14000b792  call    SczAllocConcatSz
0x14000b797  mov     ebx, eax
0x14000b799  test    eax, eax
0x14000b79b  jns     short loc_14000B7F3
0x14000b79d  mov     [rbp+var_10], eax
0x14000b7a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b7a7  test    rcx, rcx
0x14000b7aa  jz      short loc_14000B7E9
0x14000b7ac  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b7b3  mov     edi, 3
0x14000b7b8  mov     r8d, edi
0x14000b7bb  xor     edx, edx
0x14000b7bd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b7c2  lea     rax, [rbp+var_10]
0x14000b7c6  mov     qword ptr [rbp+var_30], rax
0x14000b7ca  lea     rax, [rbp+var_30]
0x14000b7ce  mov     qword ptr [rsp+60h+var_40], rax
0x14000b7d3  lea     r9, asc_14002D4FC; ": {}"
0x14000b7da  mov     r8d, edi
0x14000b7dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b7e4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b7e9  mov     edx, 149h
0x14000b7ee  jmp     loc_14000B569
0x14000b7f3  mov     r8, [rdi+50h]
0x14000b7f7  test    r8, r8
0x14000b7fa  jz      loc_14000B8D4
0x14000b800  lea     rdx, aScratchdirS; " /scratchdir:\"%s\""
0x14000b807  lea     rcx, [rbp+var_28]
0x14000b80b  call    SczAllocFormatted
0x14000b810  mov     ebx, eax
0x14000b812  test    eax, eax
0x14000b814  jns     short loc_14000B86C
0x14000b816  mov     [rbp+var_10], eax
0x14000b819  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b820  test    rcx, rcx
0x14000b823  jz      short loc_14000B862
0x14000b825  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b82c  mov     edi, 3
0x14000b831  mov     r8d, edi
0x14000b834  xor     edx, edx
0x14000b836  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b83b  lea     rax, [rbp+var_10]
0x14000b83f  mov     qword ptr [rbp+var_30], rax
0x14000b843  lea     rax, [rbp+var_30]
0x14000b847  mov     qword ptr [rsp+60h+var_40], rax
0x14000b84c  lea     r9, asc_14002D4FC; ": {}"
0x14000b853  mov     r8d, edi
0x14000b856  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b85d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b862  mov     edx, 150h
0x14000b867  jmp     loc_14000B569
0x14000b86c  mov     rdx, [rbp+var_28]
0x14000b870  mov     rcx, rsi
0x14000b873  call    SczAllocConcatSz
0x14000b878  mov     ebx, eax
0x14000b87a  test    eax, eax
0x14000b87c  jns     short loc_14000B8D4
0x14000b87e  mov     [rbp+var_10], eax
0x14000b881  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b888  test    rcx, rcx
0x14000b88b  jz      short loc_14000B8CA
0x14000b88d  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b894  mov     edi, 3
0x14000b899  mov     r8d, edi
0x14000b89c  xor     edx, edx
0x14000b89e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b8a3  lea     rax, [rbp+var_10]
0x14000b8a7  mov     qword ptr [rbp+var_30], rax
0x14000b8ab  lea     rax, [rbp+var_30]
0x14000b8af  mov     qword ptr [rsp+60h+var_40], rax
0x14000b8b4  lea     r9, asc_14002D4FC; ": {}"
0x14000b8bb  mov     r8d, edi
0x14000b8be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b8c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b8ca  mov     edx, 152h
0x14000b8cf  jmp     loc_14000B569
0x14000b8d4  cmp     [rdi+140h], r14d
0x14000b8db  jz      short loc_14000B948
0x14000b8dd  lea     rdx, aQuiet; " /quiet"
0x14000b8e4  mov     rcx, rsi
0x14000b8e7  call    SczAllocConcatSz
0x14000b8ec  mov     ebx, eax
0x14000b8ee  test    eax, eax
0x14000b8f0  jns     short loc_14000B948
0x14000b8f2  mov     [rbp+var_10], eax
0x14000b8f5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b8fc  test    rcx, rcx
0x14000b8ff  jz      short loc_14000B93E
0x14000b901  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000b908  mov     edi, 3
0x14000b90d  mov     r8d, edi
0x14000b910  xor     edx, edx
0x14000b912  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b917  lea     rax, [rbp+var_10]
0x14000b91b  mov     qword ptr [rbp+var_30], rax
0x14000b91f  lea     rax, [rbp+var_30]
0x14000b923  mov     qword ptr [rsp+60h+var_40], rax
0x14000b928  lea     r9, asc_14002D4FC; ": {}"
0x14000b92f  mov     r8d, edi
0x14000b932  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b939  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
  ... truncated ...
```
