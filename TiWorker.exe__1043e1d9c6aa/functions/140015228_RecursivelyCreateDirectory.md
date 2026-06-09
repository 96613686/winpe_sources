# RecursivelyCreateDirectory

- ea: `0x140015228`
- end: `0x140015697`
- name: `RecursivelyCreateDirectory`
- size: `1135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ed6c`
- `0x14000f02c`
- `0x14000f5b0`
- `0x140015228`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14001093c`
- `0x140010e3c`
- `0x140011d0c`
- `0x140014104`
- `0x140014128`
- `0x140015228`
- `0x140017004`
- `0x140017ec8`
- `0x1400266a4`
- `0x1400269f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140015461`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140015461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015633`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14001543a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140015629`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14001543a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140015629`

## string_xrefs

- `0x140015290`: `No path specified`
- `0x1400153c2`: `Failed calling GetSystemSecurity`
- `0x140015494`: `Cannot find parent for path: {}.`
- `0x140015570`: `Failed to copy parent of path: {}`
- `0x1400155e4`: `Failed to create path: {}`

## pseudocode

```c
__int64 __fastcall RecursivelyCreateDirectory(__int64 a1, struct _SECURITY_ATTRIBUTES *a2)
{
  unsigned int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  const struct std::nothrow_t *v8; // rdx
  bool *v9; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v11; // rdx
  unsigned int v12; // r8d
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rdx
  int SystemSecurity; // eax
  __int64 v17; // rdx
  const wchar_t *v18; // rbx
  wchar_t *v19; // rax
  __int64 v20; // rdx
  unsigned __int64 v21; // rsi
  wchar_t *v22; // rdi
  __int64 v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  unsigned __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  int Directory; // eax
  __int64 v29; // rdx
  signed int LastError; // eax
  int v32; // [rsp+20h] [rbp-49h]
  _BYTE v33[8]; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *v34; // [rsp+38h] [rbp-31h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-29h] BYREF
  int *v36; // [rsp+48h] [rbp-21h] BYREF
  int *v37; // [rsp+50h] [rbp-19h] BYREF
  __int128 v38; // [rsp+58h] [rbp-11h]
  __int64 v39; // [rsp+68h] [rbp-1h]
  __int64 v40; // [rsp+70h] [rbp+7h] BYREF
  int v41; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v42; // [rsp+80h] [rbp+17h] BYREF
  __int64 v43; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v40 = a1;
  v43 = 0;
  lpPathName = 0;
  v42 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v41 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      v34 = (wchar_t *)&v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v4,
        3,
        (__int64)": {}",
        (__int64)&v34);
    }
    v5 = 2147942487LL;
    v6 = 355;
    goto LABEL_8;
  }
  v7 = SczAllocFromSz(&lpPathName, a1);
  v3 = v7;
  if ( v7 >= 0 )
  {
    v7 = PathPrefix(&lpPathName);
    v3 = v7;
    if ( v7 < 0 )
    {
      v6 = 361;
      goto LABEL_7;
    }
    if ( !a2 )
    {
      v33[0] = 0;
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                            (Windows::WCP::Implementation::Rtl *)v33,
                            v9);
      v13 = CanSetSystemOwner;
      if ( CanSetSystemOwner < 0 )
      {
        v41 = CanSetSystemOwner;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling CanSetSystemOwner");
          v34 = (wchar_t *)&v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v14,
            3,
            (__int64)": {}",
            (__int64)&v34);
        }
        v15 = 367;
LABEL_16:
        v3 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v15, v12, (const char *)v13, v32);
        goto LABEL_50;
      }
      if ( v33[0] )
      {
        v34 = 0;
        SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                           (Windows::WCP::Implementation::Rtl *)&v34,
                           v11);
        v13 = SystemSecurity;
        if ( SystemSecurity < 0 )
        {
          v41 = SystemSecurity;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling GetSystemSecurity");
            v34 = (wchar_t *)&v41;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v17,
              3,
              (__int64)": {}",
              (__int64)&v34);
          }
          v15 = 373;
          goto LABEL_16;
        }
        a2 = (struct _SECURITY_ATTRIBUTES *)&v42;
        *((_QWORD *)&v38 + 1) = v34;
        *(_QWORD *)&v38 = 24;
        v39 = 0;
        v43 = 0;
        v42 = v38;
      }
    }
    v18 = lpPathName;
    if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
    {
      v19 = wcsrchr(v18, 0x5Cu);
      if ( !v19 )
      {
        v3 = -2147024893;
        v41 = -2147024893;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Cannot find parent for path: {}.",
            (__int64)&v40);
          v34 = (wchar_t *)&v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v20,
            3,
            (__int64)": {}",
            (__int64)&v34);
        }
        v5 = 2147942403LL;
        v6 = 392;
        goto LABEL_8;
      }
      v34 = 0;
      v21 = v19 - v18;
      Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(&v34, v21 + 1);
      v22 = v34;
      if ( !v34 )
      {
        v3 = -2147024882;
        v23 = 399;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v3);
LABEL_32:
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v34, v24);
        goto LABEL_50;
      }
      v25 = -1;
      do
        ++v25;
      while ( v18[v25] );
      if ( v21 <= v25 )
      {
        v26 = StringCchCopyNW(v34, v21 + 1, v18, v21);
        v3 = v26;
        if ( v26 < 0 )
        {
          v41 = v26;
          if ( LogAdapter::g_Logger )
          {
            v36 = (int *)v18;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to copy parent of path: {}",
              (__int64)&v36);
            v37 = &v41;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v27,
              3,
              (__int64)": {}",
              (__int64)&v37);
          }
          v23 = 406;
          goto LABEL_31;
        }
      }
      Directory = RecursivelyCreateDirectory(v22, a2);
      v3 = Directory;
      if ( Directory < 0 )
      {
        v41 = Directory;
        if ( LogAdapter::g_Logger )
        {
          v37 = (int *)v22;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to create path: {}",
            (__int64)&v37);
          v36 = &v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v29,
            3,
            (__int64)": {}",
            (__int64)&v36);
        }
        v23 = 408;
        goto LABEL_31;
      }
      if ( !CreateDirectoryW(v18, a2) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError != 183 )
        {
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_32;
        }
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v34, v24);
    }
    v3 = 0;
    goto LABEL_50;
  }
  v6 = 360;
LABEL_7:
  v5 = (unsigned int)v7;
LABEL_8:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v6, (int)"onecore\\base\\cbs\\util\\cbsfile.cpp", (const char *)v5);
LABEL_50:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpPathName, v8);
  return v3;
}

```

## disassembly

```asm
0x140015228  mov     [rsp-8+arg_10], rbx
0x14001522d  mov     [rsp-8+arg_18], rsi
0x140015232  push    rbp
0x140015233  push    rdi
0x140015234  push    r12
0x140015236  push    r14
0x140015238  push    r15
0x14001523a  lea     rbp, [rsp-37h]
0x14001523f  sub     rsp, 0A0h
0x140015246  mov     rax, cs:__security_cookie
0x14001524d  xor     rax, rsp
0x140015250  mov     [rbp+57h+var_28], rax
0x140015254  xor     eax, eax
0x140015256  mov     [rbp+57h+var_50], rcx
0x14001525a  xor     r12d, r12d
0x14001525d  mov     [rbp+57h+var_30], rax
0x140015261  mov     [rbp+57h+lpPathName], r12
0x140015265  xorps   xmm0, xmm0
0x140015268  mov     r14, rdx
0x14001526b  movups  [rbp+57h+var_40], xmm0
0x14001526f  test    rcx, rcx
0x140015272  jnz     short loc_1400152CD
0x140015274  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001527b  mov     esi, 80070057h
0x140015280  mov     [rbp+57h+var_48], esi
0x140015283  test    rcx, rcx
0x140015286  jz      short loc_1400152C3
0x140015288  lea     ebx, [rax+3]
0x14001528b  xor     edx, edx
0x14001528d  mov     r8d, ebx
0x140015290  lea     r9, aNoPathSpecifie; "No path specified"
0x140015297  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001529c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400152a3  lea     rax, [rbp+57h+var_48]
0x1400152a7  mov     [rbp+57h+var_88], rax
0x1400152ab  lea     r9, asc_140030534; ": {}"
0x1400152b2  lea     rax, [rbp+57h+var_88]
0x1400152b6  mov     r8d, ebx
0x1400152b9  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400152be  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400152c3  mov     r9d, esi
0x1400152c6  mov     edx, 163h
0x1400152cb  jmp     short loc_1400152E7
0x1400152cd  mov     rdx, rcx
0x1400152d0  lea     rcx, [rbp+57h+lpPathName]
0x1400152d4  call    SczAllocFromSz
0x1400152d9  mov     esi, eax
0x1400152db  test    eax, eax
0x1400152dd  jns     short loc_1400152FC
0x1400152df  mov     edx, 168h; void *
0x1400152e4  mov     r9d, eax; char *
0x1400152e7  mov     rcx, [rbp+5Fh]; this
0x1400152eb  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1400152f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400152f7  jmp     loc_140015664
0x1400152fc  lea     rcx, [rbp+57h+lpPathName]
0x140015300  call    PathPrefix
0x140015305  mov     esi, eax
0x140015307  test    eax, eax
0x140015309  jns     short loc_140015312
0x14001530b  mov     edx, 169h
0x140015310  jmp     short loc_1400152E4
0x140015312  test    r14, r14
0x140015315  jnz     loc_140015430
0x14001531b  lea     rcx, [rbp+57h+var_90]; this
0x14001531f  mov     [rbp+57h+var_90], r12b
0x140015323  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x140015328  mov     edi, eax
0x14001532a  test    eax, eax
0x14001532c  jns     short loc_140015391
0x14001532e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015335  mov     [rbp+57h+var_48], eax
0x140015338  test    rcx, rcx
0x14001533b  jz      short loc_140015379
0x14001533d  lea     ebx, [r14+3]
0x140015341  xor     edx, edx
0x140015343  mov     r8d, ebx
0x140015346  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x14001534d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140015352  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015359  lea     rax, [rbp+57h+var_48]
0x14001535d  mov     [rbp+57h+var_88], rax
0x140015361  lea     r9, asc_140030534; ": {}"
0x140015368  lea     rax, [rbp+57h+var_88]
0x14001536c  mov     r8d, ebx
0x14001536f  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x140015374  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140015379  mov     edx, 16Fh; void *
0x14001537e  mov     rcx, [rbp+5Fh]; this
0x140015382  mov     r9d, edi; char *
0x140015385  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14001538a  mov     esi, eax
0x14001538c  jmp     loc_140015664
0x140015391  cmp     [rbp+57h+var_90], r12b
0x140015395  jz      loc_140015430
0x14001539b  lea     rcx, [rbp+57h+var_88]; this
0x14001539f  mov     [rbp+57h+var_88], r12
0x1400153a3  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x1400153a8  mov     edi, eax
0x1400153aa  test    eax, eax
0x1400153ac  jns     short loc_140015404
0x1400153ae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400153b5  mov     [rbp+57h+var_48], eax
0x1400153b8  test    rcx, rcx
0x1400153bb  jz      short loc_1400153FA
0x1400153bd  mov     ebx, 3
0x1400153c2  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x1400153c9  mov     r8d, ebx
0x1400153cc  xor     edx, edx
0x1400153ce  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400153d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400153da  lea     rax, [rbp+57h+var_48]
0x1400153de  mov     [rbp+57h+var_88], rax
0x1400153e2  lea     r9, asc_140030534; ": {}"
0x1400153e9  lea     rax, [rbp+57h+var_88]
0x1400153ed  mov     r8d, ebx
0x1400153f0  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400153f5  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1400153fa  mov     edx, 175h
0x1400153ff  jmp     loc_14001537E
0x140015404  mov     rax, [rbp+57h+var_88]
0x140015408  lea     r14, [rbp+57h+var_40]
0x14001540c  mov     qword ptr [rbp+57h+var_68+8], rax
0x140015410  xor     eax, eax
0x140015412  mov     qword ptr [rbp+57h+var_68], 18h
0x14001541a  movups  xmm0, [rbp+57h+var_68]
0x14001541e  mov     [rbp+57h+var_58], rax
0x140015422  movsd   xmm1, [rbp+57h+var_58]
0x140015427  movsd   [rbp+57h+var_30], xmm1
0x14001542c  movups  [rbp+57h+var_40], xmm0
0x140015430  mov     rbx, [rbp+57h+lpPathName]
0x140015434  mov     rdx, r14; lpSecurityAttributes
0x140015437  mov     rcx, rbx; lpPathName
0x14001543a  call    cs:__imp_CreateDirectoryW
0x140015440  test    eax, eax
0x140015442  jnz     loc_140015661
0x140015448  call    cs:__imp_GetLastError
0x14001544e  cmp     eax, 0B7h
0x140015453  jz      loc_140015661
0x140015459  mov     edx, 5Ch ; '\'; Ch
0x14001545e  mov     rcx, rbx; Str
0x140015461  call    cs:__imp_wcsrchr
0x140015467  mov     rsi, rax
0x14001546a  test    rax, rax
0x14001546d  jnz     short loc_1400154D6
0x14001546f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015476  mov     esi, 80070003h
0x14001547b  mov     [rbp+57h+var_48], esi
0x14001547e  test    rcx, rcx
0x140015481  jz      short loc_1400154C9
0x140015483  lea     rax, [rbp+57h+var_50]
0x140015487  mov     ebx, 3
0x14001548c  mov     r8d, ebx
0x14001548f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140015494  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x14001549b  xor     edx, edx
0x14001549d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400154a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400154a9  lea     rax, [rbp+57h+var_48]
0x1400154ad  mov     [rbp+57h+var_88], rax
0x1400154b1  lea     r9, asc_140030534; ": {}"
0x1400154b8  lea     rax, [rbp+57h+var_88]
0x1400154bc  mov     r8d, ebx
0x1400154bf  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400154c4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400154c9  mov     r9d, esi
0x1400154cc  mov     edx, 188h
0x1400154d1  jmp     loc_1400152E7
0x1400154d6  sub     rsi, rbx
0x1400154d9  mov     [rbp+57h+var_88], r12
0x1400154dd  sar     rsi, 1
0x1400154e0  lea     rcx, [rbp+57h+var_88]
0x1400154e4  lea     rdx, [rsi+1]
0x1400154e8  call    ?AllocateArray@?$AutoNewArrayPtr@_W@Windows@@QEAAPEA_W_K@Z; Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(unsigned __int64)
0x1400154ed  mov     rdi, [rbp+57h+var_88]
0x1400154f1  test    rdi, rdi
0x1400154f4  jnz     short loc_140015521
0x1400154f6  mov     esi, 8007000Eh
0x1400154fb  mov     edx, 18Fh; void *
0x140015500  mov     rcx, [rbp+5Fh]; this
0x140015504  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001550b  mov     r9d, esi; char *
0x14001550e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015513  lea     rcx, [rbp+57h+var_88]
0x140015517  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x14001551c  jmp     loc_140015664
0x140015521  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015525  inc     rax
0x140015528  cmp     [rbx+rax*2], r12w
0x14001552d  jnz     short loc_140015525
0x14001552f  cmp     rsi, rax
0x140015532  ja      short loc_1400155AF
0x140015534  mov     r9, rsi; unsigned __int64
0x140015537  lea     rdx, [rsi+1]; unsigned __int64
0x14001553b  mov     r8, rbx; wchar_t *
0x14001553e  mov     rcx, rdi; wchar_t *
0x140015541  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x140015546  mov     esi, eax
0x140015548  test    eax, eax
0x14001554a  jns     short loc_1400155AF
0x14001554c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015553  mov     [rbp+57h+var_48], eax
0x140015556  test    rcx, rcx
0x140015559  jz      short loc_1400155A5
0x14001555b  mov     [rbp+57h+var_78], rbx
0x14001555f  lea     rax, [rbp+57h+var_78]
0x140015563  mov     ebx, 3
0x140015568  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001556d  mov     r8d, ebx
0x140015570  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x140015577  xor     edx, edx
0x140015579  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001557e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015585  lea     rax, [rbp+57h+var_48]
0x140015589  mov     [rbp+57h+var_70], rax
0x14001558d  lea     r9, asc_140030534; ": {}"
0x140015594  lea     rax, [rbp+57h+var_70]
0x140015598  mov     r8d, ebx
0x14001559b  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400155a0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400155a5  mov     edx, 196h
0x1400155aa  jmp     loc_140015500
0x1400155af  mov     rdx, r14
0x1400155b2  mov     rcx, rdi
0x1400155b5  call    RecursivelyCreateDirectory
0x1400155ba  mov     esi, eax
0x1400155bc  test    eax, eax
0x1400155be  jns     short loc_140015623
0x1400155c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400155c7  mov     [rbp+57h+var_48], eax
0x1400155ca  test    rcx, rcx
0x1400155cd  jz      short loc_140015619
0x1400155cf  lea     rax, [rbp+57h+var_70]
0x1400155d3  mov     [rbp+57h+var_70], rdi
0x1400155d7  mov     ebx, 3
0x1400155dc  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400155e1  mov     r8d, ebx
0x1400155e4  lea     r9, aFailedToCreate_0; "Failed to create path: {}"
0x1400155eb  xor     edx, edx
0x1400155ed  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400155f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400155f9  lea     rax, [rbp+57h+var_48]
0x1400155fd  mov     [rbp+57h+var_78], rax
0x140015601  lea     r9, asc_140030534; ": {}"
0x140015608  lea     rax, [rbp+57h+var_78]
0x14001560c  mov     r8d, ebx
0x14001560f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140015614  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015619  mov     edx, 198h
0x14001561e  jmp     loc_140015500
0x140015623  mov     rdx, r14; lpSecurityAttributes
0x140015626  mov     rcx, rbx; lpPathName
0x140015629  call    cs:__imp_CreateDirectoryW
0x14001562f  test    eax, eax
0x140015631  jnz     short loc_140015658
0x140015633  call    cs:__imp_GetLastError
0x140015639  mov     esi, eax
0x14001563b  cmp     eax, 0B7h
0x140015640  jz      short loc_140015658
0x140015642  test    eax, eax
0x140015644  jle     loc_140015513
0x14001564a  movzx   esi, ax
0x14001564d  or      esi, 80070000h
0x140015653  jmp     loc_140015513
0x140015658  lea     rcx, [rbp+57h+var_88]
0x14001565c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140015661  mov     esi, r12d
0x140015664  lea     rcx, [rbp+57h+lpPathName]
0x140015668  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001566d  mov     eax, esi
0x14001566f  mov     rcx, [rbp+57h+var_28]
0x140015673  xor     rcx, rsp; StackCookie
0x140015676  call    __security_check_cookie
0x14001567b  lea     r11, [rsp+0C0h+var_20]
0x140015683  mov     rbx, [r11+40h]
0x140015687  mov     rsi, [r11+48h]
0x14001568b  mov     rsp, r11
0x14001568e  pop     r15
0x140015690  pop     r14
0x140015692  pop     r12
0x140015694  pop     rdi
0x140015695  pop     rbp
0x140015696  retn
```
