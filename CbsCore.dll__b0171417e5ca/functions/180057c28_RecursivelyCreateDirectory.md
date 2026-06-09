# RecursivelyCreateDirectory

- ea: `0x180057c28`
- end: `0x1800580c5`
- name: `RecursivelyCreateDirectory`
- size: `1181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800532d4`
- `0x180057c28`
- `0x18005b7e4`
- `0x180095950`
- `0x18009d188`
- `0x1800af8d8`
- `0x1800c8550`
- `0x1800c9494`
- `0x1800caa88`
- `0x1800cd91c`
- `0x1800d0cc0`
- `0x1800dc9c0`
- `0x1800e2f68`
- `0x1800e498c`
- `0x1800e9408`
- `0x1800f2214`
- `0x180121528`
- `0x18014cbf4`
- `0x18018add4`
- `0x18018fdd4`
- `0x18019762c`
- `0x1801c0d60`

## callees

- `0x18000b3f0`
- `0x180013250`
- `0x180015420`
- `0x18004f454`
- `0x180057c28`
- `0x18005eef0`
- `0x1800645d8`
- `0x180064788`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x180102728`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180057e76`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180057e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005805a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005805a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180057e43`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005804a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180057e43`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005804a`

## string_xrefs

- `0x180057c90`: `No path specified`
- `0x180057eaf`: `Cannot find parent for path: {}.`
- `0x180057f8d`: `Failed to copy parent of path: {}`
- `0x180057dcb`: `Failed calling GetSystemSecurity`
- `0x180058003`: `Failed to create path: {}`

## pseudocode

```c
__int64 __fastcall RecursivelyCreateDirectory(__int64 a1, struct _SECURITY_ATTRIBUTES *a2)
{
  unsigned int v3; // esi
  __int64 v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  bool *v7; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v9; // rdx
  unsigned int v10; // edi
  int v11; // edx
  __int64 v12; // rdx
  int SystemSecurity; // eax
  int v14; // edx
  const wchar_t *v15; // rbx
  wchar_t *v16; // rax
  unsigned __int64 v17; // rsi
  wchar_t *v18; // rdi
  __int64 v19; // rdx
  unsigned __int64 v20; // rax
  int v21; // eax
  int Directory; // eax
  signed int LastError; // eax
  int v25; // [rsp+20h] [rbp-49h]
  _BYTE v26[8]; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *v27; // [rsp+38h] [rbp-31h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-29h] BYREF
  int *v29; // [rsp+48h] [rbp-21h] BYREF
  int *v30; // [rsp+50h] [rbp-19h] BYREF
  __int128 v31; // [rsp+58h] [rbp-11h]
  __int64 v32; // [rsp+68h] [rbp-1h]
  __int64 v33; // [rsp+70h] [rbp+7h] BYREF
  int v34; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v35; // [rsp+80h] [rbp+17h] BYREF
  __int64 v36; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v33 = a1;
  v36 = 0;
  lpPathName = 0;
  v35 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v34 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      v27 = (wchar_t *)&v34;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v27);
    }
    v4 = 2147942487LL;
    v5 = 355;
    goto LABEL_8;
  }
  v6 = SczAllocFromSz(&lpPathName, a1);
  v3 = v6;
  if ( v6 >= 0 )
  {
    v6 = PathPrefix(&lpPathName);
    v3 = v6;
    if ( v6 < 0 )
    {
      v5 = 361;
      goto LABEL_7;
    }
    if ( !a2 )
    {
      v26[0] = 0;
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                            (Windows::WCP::Implementation::Rtl *)v26,
                            v7);
      v10 = CanSetSystemOwner;
      if ( CanSetSystemOwner < 0 )
      {
        v34 = CanSetSystemOwner;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling CanSetSystemOwner");
          v27 = (wchar_t *)&v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v11,
            3,
            (unsigned int)": {}",
            (__int64)&v27);
        }
        v12 = 367;
LABEL_16:
        v3 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v12,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v10,
               v25);
        goto LABEL_50;
      }
      if ( v26[0] )
      {
        v27 = 0;
        SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                           (Windows::WCP::Implementation::Rtl *)&v27,
                           v9);
        v10 = SystemSecurity;
        if ( SystemSecurity < 0 )
        {
          v34 = SystemSecurity;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling GetSystemSecurity");
            v27 = (wchar_t *)&v34;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v14,
              3,
              (unsigned int)": {}",
              (__int64)&v27);
          }
          v12 = 373;
          goto LABEL_16;
        }
        a2 = (struct _SECURITY_ATTRIBUTES *)&v35;
        *((_QWORD *)&v31 + 1) = v27;
        *(_QWORD *)&v31 = 24;
        v32 = 0;
        v36 = 0;
        v35 = v31;
      }
    }
    v15 = lpPathName;
    if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
    {
      v16 = wcsrchr(v15, 0x5Cu);
      if ( !v16 )
      {
        v3 = -2147024893;
        v34 = -2147024893;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Cannot find parent for path: {}.",
            (__int64)&v33);
          v27 = (wchar_t *)&v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v27);
        }
        v4 = 2147942403LL;
        v5 = 392;
        goto LABEL_8;
      }
      v27 = 0;
      v17 = v16 - v15;
      Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(&v27, v17 + 1);
      v18 = v27;
      if ( !v27 )
      {
        v3 = -2147024882;
        v19 = 399;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v3,
          v25);
LABEL_32:
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v27);
        goto LABEL_50;
      }
      v20 = -1;
      do
        ++v20;
      while ( v15[v20] );
      if ( v17 <= v20 )
      {
        v21 = StringCchCopyNW(v27, v17 + 1, v15, v17);
        v3 = v21;
        if ( v21 < 0 )
        {
          v34 = v21;
          if ( LogAdapter::g_Logger )
          {
            v29 = (int *)v15;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to copy parent of path: {}",
              (__int64)&v29);
            v30 = &v34;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v30);
          }
          v19 = 406;
          goto LABEL_31;
        }
      }
      Directory = RecursivelyCreateDirectory(v18, a2);
      v3 = Directory;
      if ( Directory < 0 )
      {
        v34 = Directory;
        if ( LogAdapter::g_Logger )
        {
          v30 = (int *)v18;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to create path: {}",
            (__int64)&v30);
          v29 = &v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v29);
        }
        v19 = 408;
        goto LABEL_31;
      }
      if ( !CreateDirectoryW(v15, a2) )
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
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v27);
    }
    v3 = 0;
    goto LABEL_50;
  }
  v5 = 360;
LABEL_7:
  v4 = (unsigned int)v6;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v4,
    v25);
LABEL_50:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
  return v3;
}

```

## disassembly

```asm
0x180057c28  mov     [rsp-8+arg_10], rbx
0x180057c2d  mov     [rsp-8+arg_18], rsi
0x180057c32  push    rbp
0x180057c33  push    rdi
0x180057c34  push    r12
0x180057c36  push    r14
0x180057c38  push    r15
0x180057c3a  lea     rbp, [rsp-37h]
0x180057c3f  sub     rsp, 0A0h
0x180057c46  mov     rax, cs:__security_cookie
0x180057c4d  xor     rax, rsp
0x180057c50  mov     [rbp+57h+var_28], rax
0x180057c54  xor     eax, eax
0x180057c56  mov     [rbp+57h+var_50], rcx
0x180057c5a  xor     r12d, r12d
0x180057c5d  mov     [rbp+57h+var_30], rax
0x180057c61  mov     [rbp+57h+lpPathName], r12
0x180057c65  xorps   xmm0, xmm0
0x180057c68  mov     r14, rdx
0x180057c6b  movups  [rbp+57h+var_40], xmm0
0x180057c6f  test    rcx, rcx
0x180057c72  jnz     short loc_180057CCF
0x180057c74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057c7b  mov     esi, 80070057h
0x180057c80  mov     [rbp+57h+var_48], esi
0x180057c83  test    rcx, rcx
0x180057c86  jz      short loc_180057CC5
0x180057c88  lea     ebx, [rax+3]
0x180057c8b  xor     edx, edx
0x180057c8d  mov     r8d, ebx
0x180057c90  lea     r9, aNoPathSpecifie; "No path specified"
0x180057c97  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180057c9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057ca3  lea     rax, [rbp+57h+var_48]
0x180057ca7  mov     [rbp+57h+var_88], rax
0x180057cab  lea     r9, asc_1802EE7AC; ": {}"
0x180057cb2  lea     rax, [rbp+57h+var_88]
0x180057cb6  mov     r8d, ebx
0x180057cb9  mov     dl, 1
0x180057cbb  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180057cc0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180057cc5  mov     r9d, esi
0x180057cc8  mov     edx, 163h
0x180057ccd  jmp     short loc_180057CE9
0x180057ccf  mov     rdx, rcx
0x180057cd2  lea     rcx, [rbp+57h+lpPathName]
0x180057cd6  call    SczAllocFromSz
0x180057cdb  mov     esi, eax
0x180057cdd  test    eax, eax
0x180057cdf  jns     short loc_180057CFE
0x180057ce1  mov     edx, 168h; void *
0x180057ce6  mov     r9d, eax; char *
0x180057ce9  mov     rcx, [rbp+5Fh]; this
0x180057ced  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180057cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057cf9  jmp     loc_180058091
0x180057cfe  lea     rcx, [rbp+57h+lpPathName]
0x180057d02  call    PathPrefix
0x180057d07  mov     esi, eax
0x180057d09  test    eax, eax
0x180057d0b  jns     short loc_180057D14
0x180057d0d  mov     edx, 169h
0x180057d12  jmp     short loc_180057CE6
0x180057d14  test    r14, r14
0x180057d17  jnz     loc_180057E39
0x180057d1d  lea     rcx, [rbp+57h+var_90]; this
0x180057d21  mov     [rbp+57h+var_90], r12b
0x180057d25  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x180057d2a  mov     edi, eax
0x180057d2c  test    eax, eax
0x180057d2e  jns     short loc_180057D9A
0x180057d30  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057d37  mov     [rbp+57h+var_48], eax
0x180057d3a  test    rcx, rcx
0x180057d3d  jz      short loc_180057D7B
0x180057d3f  lea     ebx, [r14+3]
0x180057d43  xor     edx, edx
0x180057d45  mov     r8d, ebx
0x180057d48  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x180057d4f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180057d54  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057d5b  lea     rax, [rbp+57h+var_48]
0x180057d5f  mov     [rbp+57h+var_88], rax
0x180057d63  lea     r9, asc_1802EE7AC; ": {}"
0x180057d6a  lea     rax, [rbp+57h+var_88]
0x180057d6e  mov     r8d, ebx
0x180057d71  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180057d76  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x180057d7b  mov     edx, 16Fh; void *
0x180057d80  mov     rcx, [rbp+5Fh]; this
0x180057d84  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180057d8b  mov     r9d, edi; char *
0x180057d8e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180057d93  mov     esi, eax
0x180057d95  jmp     loc_180058091
0x180057d9a  cmp     [rbp+57h+var_90], r12b
0x180057d9e  jz      loc_180057E39
0x180057da4  lea     rcx, [rbp+57h+var_88]; this
0x180057da8  mov     [rbp+57h+var_88], r12
0x180057dac  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x180057db1  mov     edi, eax
0x180057db3  test    eax, eax
0x180057db5  jns     short loc_180057E0D
0x180057db7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057dbe  mov     [rbp+57h+var_48], eax
0x180057dc1  test    rcx, rcx
0x180057dc4  jz      short loc_180057E03
0x180057dc6  mov     ebx, 3
0x180057dcb  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x180057dd2  mov     r8d, ebx
0x180057dd5  xor     edx, edx
0x180057dd7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180057ddc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057de3  lea     rax, [rbp+57h+var_48]
0x180057de7  mov     [rbp+57h+var_88], rax
0x180057deb  lea     r9, asc_1802EE7AC; ": {}"
0x180057df2  lea     rax, [rbp+57h+var_88]
0x180057df6  mov     r8d, ebx
0x180057df9  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180057dfe  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x180057e03  mov     edx, 175h
0x180057e08  jmp     loc_180057D80
0x180057e0d  mov     rax, [rbp+57h+var_88]
0x180057e11  lea     r14, [rbp+57h+var_40]
0x180057e15  mov     qword ptr [rbp+57h+var_68+8], rax
0x180057e19  xor     eax, eax
0x180057e1b  mov     qword ptr [rbp+57h+var_68], 18h
0x180057e23  movups  xmm0, [rbp+57h+var_68]
0x180057e27  mov     [rbp+57h+var_58], rax
0x180057e2b  movsd   xmm1, [rbp+57h+var_58]
0x180057e30  movsd   [rbp+57h+var_30], xmm1
0x180057e35  movups  [rbp+57h+var_40], xmm0
0x180057e39  mov     rbx, [rbp+57h+lpPathName]
0x180057e3d  mov     rdx, r14; lpSecurityAttributes
0x180057e40  mov     rcx, rbx; lpPathName
0x180057e43  call    cs:__imp_CreateDirectoryW
0x180057e4a  nop     dword ptr [rax+rax+00h]
0x180057e4f  test    eax, eax
0x180057e51  jnz     loc_18005808E
0x180057e57  call    cs:__imp_GetLastError
0x180057e5e  nop     dword ptr [rax+rax+00h]
0x180057e63  cmp     eax, 0B7h
0x180057e68  jz      loc_18005808E
0x180057e6e  mov     edx, 5Ch ; '\'; Ch
0x180057e73  mov     rcx, rbx; Str
0x180057e76  call    cs:__imp_wcsrchr
0x180057e7d  nop     dword ptr [rax+rax+00h]
0x180057e82  mov     rsi, rax
0x180057e85  test    rax, rax
0x180057e88  jnz     short loc_180057EF3
0x180057e8a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057e91  mov     esi, 80070003h
0x180057e96  mov     [rbp+57h+var_48], esi
0x180057e99  test    rcx, rcx
0x180057e9c  jz      short loc_180057EE6
0x180057e9e  lea     rax, [rbp+57h+var_50]
0x180057ea2  mov     ebx, 3
0x180057ea7  mov     r8d, ebx
0x180057eaa  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180057eaf  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x180057eb6  xor     edx, edx
0x180057eb8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180057ebd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057ec4  lea     rax, [rbp+57h+var_48]
0x180057ec8  mov     [rbp+57h+var_88], rax
0x180057ecc  lea     r9, asc_1802EE7AC; ": {}"
0x180057ed3  lea     rax, [rbp+57h+var_88]
0x180057ed7  mov     r8d, ebx
0x180057eda  mov     dl, 1
0x180057edc  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180057ee1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180057ee6  mov     r9d, esi
0x180057ee9  mov     edx, 188h
0x180057eee  jmp     loc_180057CE9
0x180057ef3  sub     rsi, rbx
0x180057ef6  mov     [rbp+57h+var_88], r12
0x180057efa  sar     rsi, 1
0x180057efd  lea     rcx, [rbp+57h+var_88]
0x180057f01  lea     rdx, [rsi+1]
0x180057f05  call    ?AllocateArray@?$AutoNewArrayPtr@_W@Windows@@QEAAPEA_W_K@Z; Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(unsigned __int64)
0x180057f0a  mov     rdi, [rbp+57h+var_88]
0x180057f0e  test    rdi, rdi
0x180057f11  jnz     short loc_180057F3E
0x180057f13  mov     esi, 8007000Eh
0x180057f18  mov     edx, 18Fh; void *
0x180057f1d  mov     rcx, [rbp+5Fh]; this
0x180057f21  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180057f28  mov     r9d, esi; char *
0x180057f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057f30  lea     rcx, [rbp+57h+var_88]
0x180057f34  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x180057f39  jmp     loc_180058091
0x180057f3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057f42  inc     rax
0x180057f45  cmp     [rbx+rax*2], r12w
0x180057f4a  jnz     short loc_180057F42
0x180057f4c  cmp     rsi, rax
0x180057f4f  ja      short loc_180057FCE
0x180057f51  mov     r9, rsi; unsigned __int64
0x180057f54  lea     rdx, [rsi+1]; unsigned __int64
0x180057f58  mov     r8, rbx; wchar_t *
0x180057f5b  mov     rcx, rdi; wchar_t *
0x180057f5e  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180057f63  mov     esi, eax
0x180057f65  test    eax, eax
0x180057f67  jns     short loc_180057FCE
0x180057f69  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057f70  mov     [rbp+57h+var_48], eax
0x180057f73  test    rcx, rcx
0x180057f76  jz      short loc_180057FC4
0x180057f78  mov     [rbp+57h+var_78], rbx
0x180057f7c  lea     rax, [rbp+57h+var_78]
0x180057f80  mov     ebx, 3
0x180057f85  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180057f8a  mov     r8d, ebx
0x180057f8d  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x180057f94  xor     edx, edx
0x180057f96  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180057f9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057fa2  lea     rax, [rbp+57h+var_48]
0x180057fa6  mov     [rbp+57h+var_70], rax
0x180057faa  lea     r9, asc_1802EE7AC; ": {}"
0x180057fb1  lea     rax, [rbp+57h+var_70]
0x180057fb5  mov     r8d, ebx
0x180057fb8  mov     dl, 1
0x180057fba  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180057fbf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180057fc4  mov     edx, 196h
0x180057fc9  jmp     loc_180057F1D
0x180057fce  mov     rdx, r14
0x180057fd1  mov     rcx, rdi
0x180057fd4  call    RecursivelyCreateDirectory
0x180057fd9  mov     esi, eax
0x180057fdb  test    eax, eax
0x180057fdd  jns     short loc_180058044
0x180057fdf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057fe6  mov     [rbp+57h+var_48], eax
0x180057fe9  test    rcx, rcx
0x180057fec  jz      short loc_18005803A
0x180057fee  lea     rax, [rbp+57h+var_70]
0x180057ff2  mov     [rbp+57h+var_70], rdi
0x180057ff6  mov     ebx, 3
0x180057ffb  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180058000  mov     r8d, ebx
0x180058003  lea     r9, aFailedToCreate_13; "Failed to create path: {}"
0x18005800a  xor     edx, edx
0x18005800c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180058011  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058018  lea     rax, [rbp+57h+var_48]
0x18005801c  mov     [rbp+57h+var_78], rax
0x180058020  lea     r9, asc_1802EE7AC; ": {}"
0x180058027  lea     rax, [rbp+57h+var_78]
0x18005802b  mov     r8d, ebx
0x18005802e  mov     dl, 1
0x180058030  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180058035  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005803a  mov     edx, 198h
0x18005803f  jmp     loc_180057F1D
0x180058044  mov     rdx, r14; lpSecurityAttributes
0x180058047  mov     rcx, rbx; lpPathName
0x18005804a  call    cs:__imp_CreateDirectoryW
0x180058051  nop     dword ptr [rax+rax+00h]
0x180058056  test    eax, eax
0x180058058  jnz     short loc_180058085
0x18005805a  call    cs:__imp_GetLastError
0x180058061  nop     dword ptr [rax+rax+00h]
0x180058066  mov     esi, eax
0x180058068  cmp     eax, 0B7h
0x18005806d  jz      short loc_180058085
0x18005806f  test    eax, eax
0x180058071  jle     loc_180057F30
0x180058077  movzx   esi, ax
0x18005807a  or      esi, 80070000h
0x180058080  jmp     loc_180057F30
0x180058085  lea     rcx, [rbp+57h+var_88]
0x180058089  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005808e  mov     esi, r12d
0x180058091  lea     rcx, [rbp+57h+lpPathName]
0x180058095  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18005809a  mov     eax, esi
0x18005809c  mov     rcx, [rbp+57h+var_28]
0x1800580a0  xor     rcx, rsp; StackCookie
0x1800580a3  call    __security_check_cookie
0x1800580a8  lea     r11, [rsp+0C0h+var_20]
0x1800580b0  mov     rbx, [r11+40h]
0x1800580b4  mov     rsi, [r11+48h]
0x1800580b8  mov     rsp, r11
0x1800580bb  pop     r15
0x1800580bd  pop     r14
0x1800580bf  pop     r12
0x1800580c1  pop     rdi
0x1800580c2  pop     rbp
0x1800580c3  retn
```
