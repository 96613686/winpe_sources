# MoveToCbsTemp

- ea: `0x1801027b4`
- end: `0x180102b0f`
- name: `MoveToCbsTemp`
- size: `859`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, const WCHAR **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801035f0`

## callees

- `0x180013250`
- `0x180015420`
- `0x180059a00`
- `0x18005aa38`
- `0x18005ec58`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb500`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801027b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102a4b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180102921`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180102921`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18010294b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18010294b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180102a37`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180102a37`

## string_xrefs

- `0x180102a6a`: `Failed to move to CbsTemp`
- `0x1801028b3`: `CbsTemp`
- `0x1801028d9`: `Failed to get CbsTemp dir`
- `0x18010281f`: `No directory specified`
- `0x180102a12`: `Moving directory from {} to {}`

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
      LOBYTE(v8) = 1;
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
        LOBYTE(v13) = 1;
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
          LOBYTE(v14) = 1;
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
              LOBYTE(v18) = 1;
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
0x1801027b4  mov     [rsp-8+arg_18], rbx
0x1801027b9  push    rbp
0x1801027ba  push    rsi
0x1801027bb  push    rdi
0x1801027bc  lea     rbp, [rsp-47h]
0x1801027c1  sub     rsp, 0C0h
0x1801027c8  mov     rax, cs:__security_cookie
0x1801027cf  xor     rax, rsp
0x1801027d2  mov     [rbp+57h+var_20], rax
0x1801027d6  mov     rsi, rdx
0x1801027d9  mov     [rbp+57h+lpExistingFileName], rcx
0x1801027dd  xor     edx, edx; Val
0x1801027df  mov     [rbp+57h+lpNewFileName], 0
0x1801027e7  mov     rdi, r8
0x1801027ea  mov     rbx, rcx
0x1801027ed  xorps   xmm0, xmm0
0x1801027f0  lea     rcx, [rbp+57h+sz]; void *
0x1801027f4  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1801027f8  lea     r8d, [rdx+4Eh]; Size
0x1801027fc  call    memset_0
0x180102801  test    rbx, rbx
0x180102804  jnz     short loc_180102863
0x180102806  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010280d  mov     ebx, 80070057h
0x180102812  mov     [rbp+57h+var_88], ebx
0x180102815  test    rcx, rcx
0x180102818  jz      short loc_180102859
0x18010281a  mov     edi, 3
0x18010281f  lea     r9, aNoDirectorySpe; "No directory specified"
0x180102826  mov     r8d, edi
0x180102829  xor     edx, edx
0x18010282b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180102830  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180102837  lea     rax, [rbp+57h+var_88]
0x18010283b  mov     qword ptr [rbp+57h+var_A0], rax
0x18010283f  lea     r9, asc_1802EE7AC; ": {}"
0x180102846  lea     rax, [rbp+57h+var_A0]
0x18010284a  mov     r8d, edi
0x18010284d  mov     dl, 1
0x18010284f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180102854  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180102859  mov     r9d, ebx
0x18010285c  mov     edx, 2A4h
0x180102861  jmp     short loc_18010289E
0x180102863  mov     rcx, [rdi]
0x180102866  test    rcx, rcx
0x180102869  jz      short loc_18010287B
0x18010286b  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18010286f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180102874  mov     qword ptr [rdi], 0
0x18010287b  lea     rcx, [rbp+57h+lpNewFileName]
0x18010287f  test    rsi, rsi
0x180102882  jz      short loc_1801028B3
0x180102884  mov     rdx, rsi
0x180102887  call    SczAllocFromSz
0x18010288c  mov     ebx, eax
0x18010288e  test    eax, eax
0x180102890  jns     loc_18010291D
0x180102896  mov     edx, 2A9h; void *
0x18010289b  mov     r9d, eax; char *
0x18010289e  mov     rcx, [rbp+5Fh]; this
0x1801028a2  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1801028a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801028ae  jmp     loc_180102AE4
0x1801028b3  lea     rdx, aCbstemp; "CbsTemp"
0x1801028ba  call    PathGetWindowsDirectory
0x1801028bf  mov     ebx, eax
0x1801028c1  test    eax, eax
0x1801028c3  jns     short loc_18010291D
0x1801028c5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801028cc  mov     [rbp+57h+var_88], eax
0x1801028cf  test    rcx, rcx
0x1801028d2  jz      short loc_180102913
0x1801028d4  mov     edi, 3
0x1801028d9  lea     r9, aFailedToGetCbs_0; "Failed to get CbsTemp dir"
0x1801028e0  mov     r8d, edi
0x1801028e3  xor     edx, edx
0x1801028e5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801028ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801028f1  lea     rax, [rbp+57h+var_88]
0x1801028f5  mov     qword ptr [rbp+57h+var_A0], rax
0x1801028f9  lea     r9, asc_1802EE7AC; ": {}"
0x180102900  lea     rax, [rbp+57h+var_A0]
0x180102904  mov     r8d, edi
0x180102907  mov     dl, 1
0x180102909  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18010290e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180102913  mov     r9d, ebx
0x180102916  mov     edx, 2AFh
0x18010291b  jmp     short loc_18010289E
0x18010291d  lea     rcx, [rbp+57h+pguid]; pguid
0x180102921  call    cs:__imp_CoCreateGuid
0x180102928  nop     dword ptr [rax+rax+00h]
0x18010292d  mov     ebx, eax
0x18010292f  test    eax, eax
0x180102931  jns     short loc_18010293D
0x180102933  mov     edx, 2B2h
0x180102938  jmp     loc_18010289B
0x18010293d  mov     r8d, 27h ; '''; cchMax
0x180102943  lea     rdx, [rbp+57h+sz]; lpsz
0x180102947  lea     rcx, [rbp+57h+pguid]; rguid
0x18010294b  call    cs:__imp_StringFromGUID2
0x180102952  nop     dword ptr [rax+rax+00h]
0x180102957  test    eax, eax
0x180102959  jnz     short loc_1801029B9
0x18010295b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180102962  mov     ebx, 8000FFFFh
0x180102967  mov     [rbp+57h+var_88], ebx
0x18010296a  test    rcx, rcx
0x18010296d  jz      short loc_1801029AC
0x18010296f  lea     edi, [rax+3]
0x180102972  xor     edx, edx
0x180102974  mov     r8d, edi
0x180102977  lea     r9, aFailedToConver_4; "Failed to convert guid to string"
0x18010297e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180102983  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010298a  lea     rax, [rbp+57h+var_88]
0x18010298e  mov     qword ptr [rbp+57h+var_A0], rax
0x180102992  lea     r9, asc_1802EE7AC; ": {}"
0x180102999  lea     rax, [rbp+57h+var_A0]
0x18010299d  mov     r8d, edi
0x1801029a0  mov     dl, 1
0x1801029a2  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1801029a7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801029ac  mov     r9d, ebx
0x1801029af  mov     edx, 2B4h
0x1801029b4  jmp     loc_18010289E
0x1801029b9  lea     rcx, [rbp+57h+lpNewFileName]
0x1801029bd  call    SczEnsureBackslashTerminated
0x1801029c2  mov     ebx, eax
0x1801029c4  test    eax, eax
0x1801029c6  jns     short loc_1801029D2
0x1801029c8  mov     edx, 2B6h
0x1801029cd  jmp     loc_18010289B
0x1801029d2  lea     rdx, [rbp+57h+sz]
0x1801029d6  lea     rcx, [rbp+57h+lpNewFileName]
0x1801029da  call    SczAllocConcatSz
0x1801029df  mov     ebx, eax
0x1801029e1  test    eax, eax
0x1801029e3  jns     short loc_1801029EF
0x1801029e5  mov     edx, 2B7h
0x1801029ea  jmp     loc_18010289B
0x1801029ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801029f6  mov     rbx, [rbp+57h+lpNewFileName]
0x1801029fa  mov     qword ptr [rbp+57h+var_A0], rbx
0x1801029fe  test    rcx, rcx
0x180102a01  jz      short loc_180102A2A
0x180102a03  lea     rax, [rbp+57h+var_A0]
0x180102a07  mov     r8d, 1
0x180102a0d  mov     [rsp+0D0h+var_A8], rax
0x180102a12  lea     r9, aMovingDirector; "Moving directory from {} to {}"
0x180102a19  lea     rax, [rbp+57h+lpExistingFileName]
0x180102a1d  mov     dl, r8b
0x180102a20  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180102a25  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x180102a2a  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x180102a2e  mov     r8d, 1; dwFlags
0x180102a34  mov     rdx, rbx; lpNewFileName
0x180102a37  call    cs:__imp_MoveFileExW
0x180102a3e  nop     dword ptr [rax+rax+00h]
0x180102a43  test    eax, eax
0x180102a45  jnz     loc_180102AD7
0x180102a4b  call    cs:__imp_GetLastError
0x180102a52  nop     dword ptr [rax+rax+00h]
0x180102a57  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180102a5e  mov     ebx, eax
0x180102a60  test    rcx, rcx
0x180102a63  jz      short loc_180102AB7
0x180102a65  mov     edi, 3
0x180102a6a  lea     r9, aFailedToMoveTo_0; "Failed to move to CbsTemp"
0x180102a71  mov     r8d, edi
0x180102a74  xor     edx, edx
0x180102a76  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180102a7b  test    ebx, ebx
0x180102a7d  jg      short loc_180102A83
0x180102a7f  mov     eax, ebx
0x180102a81  jmp     short loc_180102A8B
0x180102a83  movzx   eax, bx
0x180102a86  or      eax, 80070000h
0x180102a8b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180102a92  lea     r9, a0; ": {0}"
0x180102a99  mov     [rbp+57h+var_88], eax
0x180102a9c  mov     r8d, edi
0x180102a9f  lea     rax, [rbp+57h+var_88]
0x180102aa3  mov     dl, 1
0x180102aa5  mov     qword ptr [rbp+57h+var_A0], rax
0x180102aa9  lea     rax, [rbp+57h+var_A0]
0x180102aad  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x180102ab2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180102ab7  test    ebx, ebx
0x180102ab9  jz      short loc_180102AE2
0x180102abb  mov     rcx, [rbp+5Fh]; this
0x180102abf  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180102ac6  mov     r9d, ebx; char *
0x180102ac9  mov     edx, 2BBh; void *
0x180102ace  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180102ad3  mov     ebx, eax
0x180102ad5  jmp     short loc_180102AE4
0x180102ad7  mov     [rbp+57h+lpNewFileName], 0
0x180102adf  mov     [rdi], rbx
0x180102ae2  xor     ebx, ebx
0x180102ae4  lea     rcx, [rbp+57h+lpNewFileName]
0x180102ae8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180102aed  mov     eax, ebx
0x180102aef  mov     rcx, [rbp+57h+var_20]
0x180102af3  xor     rcx, rsp; StackCookie
0x180102af6  call    __security_check_cookie
0x180102afb  mov     rbx, [rsp+0D0h+arg_18]
0x180102b03  add     rsp, 0C0h
0x180102b0a  pop     rdi
0x180102b0b  pop     rsi
0x180102b0c  pop     rbp
0x180102b0d  retn
```
