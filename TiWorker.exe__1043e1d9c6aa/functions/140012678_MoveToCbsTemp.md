# MoveToCbsTemp

- ea: `0x140012678`
- end: `0x1400129b1`
- name: `MoveToCbsTemp`
- size: `825`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, const WCHAR **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001344c`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x140002cf8`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000dbc8`
- `0x14000f36c`
- `0x140012678`
- `0x140016d8c`
- `0x1400177d8`
- `0x140017ec8`
- `0x140018740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400128f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400128f6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1400127e1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1400127e1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012805`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012805`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400128e8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400128e8`

## string_xrefs

- `0x140012775`: `CbsTemp`
- `0x1400126e3`: `No directory specified`
- `0x14001279b`: `Failed to get CbsTemp dir`
- `0x1400128c6`: `Moving directory from {} to {}`
- `0x14001290f`: `Failed to move to CbsTemp`

## pseudocode

```c
__int64 __fastcall MoveToCbsTemp(const WCHAR *a1, __int64 a2, const WCHAR **a3)
{
  const struct std::nothrow_t *v6; // rdx
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  int WindowsDirectory; // eax
  int v13; // edx
  int v14; // edx
  int v15; // edx
  const WCHAR *v16; // rbx
  signed int LastError; // ebx
  int v18; // edx
  unsigned int v19; // eax
  unsigned int v21; // [rsp+20h] [rbp-59h]
  unsigned int v22[2]; // [rsp+30h] [rbp-49h] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-41h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+48h] [rbp-31h] BYREF
  GUID pguid; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  lpExistingFileName = a1;
  lpNewFileName = 0;
  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  if ( !a1 )
  {
    v7 = -2147024809;
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No directory specified");
      *(_QWORD *)v22 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v22);
    }
    v9 = 2147942487LL;
    v10 = 676;
    goto LABEL_11;
  }
  if ( *a3 )
  {
    operator delete((void *)(*a3 - 4), v6);
    *a3 = 0;
  }
  if ( !a2 )
  {
    WindowsDirectory = PathGetWindowsDirectory(&lpNewFileName, L"CbsTemp");
    v7 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v25 = WindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get CbsTemp dir");
        *(_QWORD *)v22 = &v25;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {}",
          (__int64)v22);
      }
      v9 = v7;
      v10 = 687;
      goto LABEL_11;
    }
LABEL_16:
    v11 = CoCreateGuid(&pguid);
    v7 = v11;
    if ( v11 >= 0 )
    {
      if ( !StringFromGUID2(&pguid, sz, 39) )
      {
        v7 = -2147418113;
        v25 = -2147418113;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to convert guid to string");
          *(_QWORD *)v22 = &v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v14,
            3,
            (unsigned int)": {}",
            (__int64)v22);
        }
        v9 = 2147549183LL;
        v10 = 692;
        goto LABEL_11;
      }
      v11 = SczEnsureBackslashTerminated(&lpNewFileName);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v11 = SczAllocConcatSz(&lpNewFileName, sz);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v16 = lpNewFileName;
          *(_QWORD *)v22 = lpNewFileName;
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v15) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              v15,
              1,
              (unsigned int)"Moving directory from {} to {}",
              (__int64)&lpExistingFileName,
              (__int64)v22);
          }
          if ( MoveFileExW(lpExistingFileName, v16, 1u) )
          {
            lpNewFileName = 0;
            *a3 = v16;
          }
          else
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to move to CbsTemp");
              if ( LastError > 0 )
                v19 = (unsigned __int16)LastError | 0x80070000;
              else
                v19 = LastError;
              v25 = v19;
              *(_QWORD *)v22 = &v25;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v18,
                3,
                (unsigned int)": {0}",
                (__int64)v22);
            }
            if ( LastError )
            {
              v7 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x2BB,
                     (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                     (const char *)(unsigned int)LastError,
                     v21);
              goto LABEL_38;
            }
          }
          v7 = 0;
          goto LABEL_38;
        }
        v10 = 695;
      }
      else
      {
        v10 = 694;
      }
    }
    else
    {
      v10 = 690;
    }
    goto LABEL_10;
  }
  v11 = SczAllocFromSz(&lpNewFileName, a2);
  v7 = v11;
  if ( v11 >= 0 )
    goto LABEL_16;
  v10 = 681;
LABEL_10:
  v9 = (unsigned int)v11;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v9,
    v21);
LABEL_38:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  return v7;
}

```

## disassembly

```asm
0x140012678  mov     [rsp-8+arg_18], rbx
0x14001267d  push    rbp
0x14001267e  push    rsi
0x14001267f  push    rdi
0x140012680  lea     rbp, [rsp-47h]
0x140012685  sub     rsp, 0C0h
0x14001268c  mov     rax, cs:__security_cookie
0x140012693  xor     rax, rsp
0x140012696  mov     [rbp+57h+var_20], rax
0x14001269a  mov     rsi, rdx
0x14001269d  mov     [rbp+57h+lpExistingFileName], rcx
0x1400126a1  xor     edx, edx; Val
0x1400126a3  mov     [rbp+57h+lpNewFileName], 0
0x1400126ab  mov     rdi, r8
0x1400126ae  mov     rbx, rcx
0x1400126b1  xorps   xmm0, xmm0
0x1400126b4  lea     rcx, [rbp+57h+sz]; void *
0x1400126b8  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1400126bc  lea     r8d, [rdx+4Eh]; Size
0x1400126c0  call    memset_0
0x1400126c5  test    rbx, rbx
0x1400126c8  jnz     short loc_140012725
0x1400126ca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400126d1  mov     ebx, 80070057h
0x1400126d6  mov     [rbp+57h+var_88], ebx
0x1400126d9  test    rcx, rcx
0x1400126dc  jz      short loc_14001271B
0x1400126de  mov     edi, 3
0x1400126e3  lea     r9, aNoDirectorySpe; "No directory specified"
0x1400126ea  mov     r8d, edi
0x1400126ed  xor     edx, edx
0x1400126ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400126f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400126fb  lea     rax, [rbp+57h+var_88]
0x1400126ff  mov     qword ptr [rbp+57h+var_A0], rax
0x140012703  lea     r9, asc_140030534; ": {}"
0x14001270a  lea     rax, [rbp+57h+var_A0]
0x14001270e  mov     r8d, edi
0x140012711  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140012716  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001271b  mov     r9d, ebx
0x14001271e  mov     edx, 2A4h
0x140012723  jmp     short loc_140012760
0x140012725  mov     rcx, [rdi]
0x140012728  test    rcx, rcx
0x14001272b  jz      short loc_14001273D
0x14001272d  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x140012731  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012736  mov     qword ptr [rdi], 0
0x14001273d  lea     rcx, [rbp+57h+lpNewFileName]
0x140012741  test    rsi, rsi
0x140012744  jz      short loc_140012775
0x140012746  mov     rdx, rsi
0x140012749  call    SczAllocFromSz
0x14001274e  mov     ebx, eax
0x140012750  test    eax, eax
0x140012752  jns     loc_1400127DD
0x140012758  mov     edx, 2A9h; void *
0x14001275d  mov     r9d, eax; char *
0x140012760  mov     rcx, [rbp+5Fh]; this
0x140012764  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001276b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012770  jmp     loc_140012987
0x140012775  lea     rdx, aCbstemp; "CbsTemp"
0x14001277c  call    PathGetWindowsDirectory
0x140012781  mov     ebx, eax
0x140012783  test    eax, eax
0x140012785  jns     short loc_1400127DD
0x140012787  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001278e  mov     [rbp+57h+var_88], eax
0x140012791  test    rcx, rcx
0x140012794  jz      short loc_1400127D3
0x140012796  mov     edi, 3
0x14001279b  lea     r9, aFailedToGetCbs; "Failed to get CbsTemp dir"
0x1400127a2  mov     r8d, edi
0x1400127a5  xor     edx, edx
0x1400127a7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400127ac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400127b3  lea     rax, [rbp+57h+var_88]
0x1400127b7  mov     qword ptr [rbp+57h+var_A0], rax
0x1400127bb  lea     r9, asc_140030534; ": {}"
0x1400127c2  lea     rax, [rbp+57h+var_A0]
0x1400127c6  mov     r8d, edi
0x1400127c9  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1400127ce  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400127d3  mov     r9d, ebx
0x1400127d6  mov     edx, 2AFh
0x1400127db  jmp     short loc_140012760
0x1400127dd  lea     rcx, [rbp+57h+pguid]; pguid
0x1400127e1  call    cs:__imp_CoCreateGuid
0x1400127e7  mov     ebx, eax
0x1400127e9  test    eax, eax
0x1400127eb  jns     short loc_1400127F7
0x1400127ed  mov     edx, 2B2h
0x1400127f2  jmp     loc_14001275D
0x1400127f7  mov     r8d, 27h ; '''; cchMax
0x1400127fd  lea     rdx, [rbp+57h+sz]; lpsz
0x140012801  lea     rcx, [rbp+57h+pguid]; rguid
0x140012805  call    cs:__imp_StringFromGUID2
0x14001280b  test    eax, eax
0x14001280d  jnz     short loc_14001286B
0x14001280f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012816  mov     ebx, 8000FFFFh
0x14001281b  mov     [rbp+57h+var_88], ebx
0x14001281e  test    rcx, rcx
0x140012821  jz      short loc_14001285E
0x140012823  lea     edi, [rax+3]
0x140012826  xor     edx, edx
0x140012828  mov     r8d, edi
0x14001282b  lea     r9, aFailedToConver; "Failed to convert guid to string"
0x140012832  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012837  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001283e  lea     rax, [rbp+57h+var_88]
0x140012842  mov     qword ptr [rbp+57h+var_A0], rax
0x140012846  lea     r9, asc_140030534; ": {}"
0x14001284d  lea     rax, [rbp+57h+var_A0]
0x140012851  mov     r8d, edi
0x140012854  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140012859  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001285e  mov     r9d, ebx
0x140012861  mov     edx, 2B4h
0x140012866  jmp     loc_140012760
0x14001286b  lea     rcx, [rbp+57h+lpNewFileName]
0x14001286f  call    SczEnsureBackslashTerminated
0x140012874  mov     ebx, eax
0x140012876  test    eax, eax
0x140012878  jns     short loc_140012884
0x14001287a  mov     edx, 2B6h
0x14001287f  jmp     loc_14001275D
0x140012884  lea     rdx, [rbp+57h+sz]
0x140012888  lea     rcx, [rbp+57h+lpNewFileName]
0x14001288c  call    SczAllocConcatSz
0x140012891  mov     ebx, eax
0x140012893  test    eax, eax
0x140012895  jns     short loc_1400128A1
0x140012897  mov     edx, 2B7h
0x14001289c  jmp     loc_14001275D
0x1400128a1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400128a8  mov     esi, 1
0x1400128ad  mov     rbx, [rbp+57h+lpNewFileName]
0x1400128b1  mov     qword ptr [rbp+57h+var_A0], rbx
0x1400128b5  test    rcx, rcx
0x1400128b8  jz      short loc_1400128DE
0x1400128ba  lea     rax, [rbp+57h+var_A0]
0x1400128be  mov     r8d, esi
0x1400128c1  mov     [rsp+0D0h+var_A8], rax
0x1400128c6  lea     r9, aMovingDirector; "Moving directory from {} to {}"
0x1400128cd  lea     rax, [rbp+57h+lpExistingFileName]
0x1400128d1  mov     dl, sil
0x1400128d4  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1400128d9  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1400128de  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1400128e2  mov     r8d, esi; dwFlags
0x1400128e5  mov     rdx, rbx; lpNewFileName
0x1400128e8  call    cs:__imp_MoveFileExW
0x1400128ee  test    eax, eax
0x1400128f0  jnz     loc_14001297A
0x1400128f6  call    cs:__imp_GetLastError
0x1400128fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012903  mov     ebx, eax
0x140012905  test    rcx, rcx
0x140012908  jz      short loc_14001295A
0x14001290a  mov     edi, 3
0x14001290f  lea     r9, aFailedToMoveTo_0; "Failed to move to CbsTemp"
0x140012916  mov     r8d, edi
0x140012919  xor     edx, edx
0x14001291b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012920  test    ebx, ebx
0x140012922  jg      short loc_140012928
0x140012924  mov     eax, ebx
0x140012926  jmp     short loc_140012930
0x140012928  movzx   eax, bx
0x14001292b  or      eax, 80070000h
0x140012930  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012937  lea     r9, a0; ": {0}"
0x14001293e  mov     [rbp+57h+var_88], eax
0x140012941  mov     r8d, edi
0x140012944  lea     rax, [rbp+57h+var_88]
0x140012948  mov     qword ptr [rbp+57h+var_A0], rax
0x14001294c  lea     rax, [rbp+57h+var_A0]
0x140012950  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x140012955  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001295a  test    ebx, ebx
0x14001295c  jz      short loc_140012985
0x14001295e  mov     rcx, [rbp+5Fh]; this
0x140012962  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140012969  mov     r9d, ebx; char *
0x14001296c  mov     edx, 2BBh; void *
0x140012971  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140012976  mov     ebx, eax
0x140012978  jmp     short loc_140012987
0x14001297a  mov     [rbp+57h+lpNewFileName], 0
0x140012982  mov     [rdi], rbx
0x140012985  xor     ebx, ebx
0x140012987  lea     rcx, [rbp+57h+lpNewFileName]
0x14001298b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012990  mov     eax, ebx
0x140012992  mov     rcx, [rbp+57h+var_20]
0x140012996  xor     rcx, rsp; StackCookie
0x140012999  call    __security_check_cookie
0x14001299e  mov     rbx, [rsp+0D0h+arg_18]
0x1400129a6  add     rsp, 0C0h
0x1400129ad  pop     rdi
0x1400129ae  pop     rsi
0x1400129af  pop     rbp
0x1400129b0  retn
```
