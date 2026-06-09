# RecursivelyCreateDirectory

- ea: `0x14001fc6c`
- end: `0x1400200af`
- name: `RecursivelyCreateDirectory`
- size: `1091`
- prototype: `__int64 __fastcall(__int64, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140017ecc`
- `0x140018180`
- `0x140018630`
- `0x14001fc6c`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x140019a00`
- `0x140019bec`
- `0x14001b210`
- `0x14001c5fc`
- `0x14001d404`
- `0x14001e95c`
- `0x14001fc6c`
- `0x14002180c`
- `0x140026498`
- `0x1400267e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14001fe8e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14001fe8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002004b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002004b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14001fe67`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140020041`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14001fe67`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140020041`

## string_xrefs

- `0x14001fccc`: `No path specified`
- `0x14001fdfd`: `Failed calling GetSystemSecurity`
- `0x14001feb4`: `Cannot find parent for path: {}.`
- `0x14001ff89`: `Failed to copy parent of path: {}`
- `0x14001fff6`: `Failed to create path: {}`

## pseudocode

```c
__int64 __fastcall RecursivelyCreateDirectory(__int64 a1, struct _SECURITY_ATTRIBUTES *a2)
{
  unsigned int v3; // esi
  int v4; // edx
  __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  bool *v8; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v10; // rdx
  unsigned int v11; // ebx
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdx
  int SystemSecurity; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  const wchar_t *v20; // rbx
  wchar_t *v21; // rax
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  unsigned __int64 v25; // rsi
  wchar_t *v26; // rdi
  __int64 v27; // rdx
  unsigned __int64 v28; // rax
  int v29; // eax
  int v30; // edx
  int v31; // r8d
  int v32; // edx
  int Directory; // eax
  int v34; // edx
  int v35; // r8d
  int v36; // edx
  signed int LastError; // eax
  int v39; // [rsp+20h] [rbp-49h]
  _BYTE v40[8]; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *v41; // [rsp+38h] [rbp-31h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-29h] BYREF
  int *v43; // [rsp+48h] [rbp-21h] BYREF
  int *v44; // [rsp+50h] [rbp-19h] BYREF
  __int128 v45; // [rsp+58h] [rbp-11h]
  __int64 v46; // [rsp+68h] [rbp-1h]
  __int64 v47; // [rsp+70h] [rbp+7h] BYREF
  int v48; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v49; // [rsp+80h] [rbp+17h] BYREF
  __int64 v50; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v47 = a1;
  v50 = 0;
  lpPathName = 0;
  v49 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v48 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      v41 = (wchar_t *)&v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&v41);
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
      v40[0] = 0;
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                            (Windows::WCP::Implementation::Rtl *)v40,
                            v8);
      v11 = CanSetSystemOwner;
      if ( CanSetSystemOwner < 0 )
      {
        v48 = CanSetSystemOwner;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling CanSetSystemOwner");
          v41 = (wchar_t *)&v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v12,
            v13,
            v14,
            (__int64)&v41);
        }
        v15 = 367;
LABEL_16:
        v3 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v11,
               v39);
        goto LABEL_50;
      }
      if ( v40[0] )
      {
        v41 = 0;
        SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                           (Windows::WCP::Implementation::Rtl *)&v41,
                           v10);
        v11 = SystemSecurity;
        if ( SystemSecurity < 0 )
        {
          v48 = SystemSecurity;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling GetSystemSecurity");
            v41 = (wchar_t *)&v48;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v17,
              v18,
              v19,
              (__int64)&v41);
          }
          v15 = 373;
          goto LABEL_16;
        }
        a2 = (struct _SECURITY_ATTRIBUTES *)&v49;
        *((_QWORD *)&v45 + 1) = v41;
        *(_QWORD *)&v45 = 24;
        v46 = 0;
        v50 = 0;
        v49 = v45;
      }
    }
    v20 = lpPathName;
    if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
    {
      v21 = wcsrchr(v20, 0x5Cu);
      if ( !v21 )
      {
        v3 = -2147024893;
        v48 = -2147024893;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v22,
            v23,
            (unsigned int)"Cannot find parent for path: {}.",
            (__int64)&v47);
          v41 = (wchar_t *)&v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v24,
            3,
            (unsigned int)": {}",
            (__int64)&v41);
        }
        v5 = 2147942403LL;
        v6 = 392;
        goto LABEL_8;
      }
      v41 = 0;
      v25 = v21 - v20;
      Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(&v41, v25 + 1);
      v26 = v41;
      if ( !v41 )
      {
        v3 = -2147024882;
        v27 = 399;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v3,
          v39);
LABEL_32:
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v41);
        goto LABEL_50;
      }
      v28 = -1;
      do
        ++v28;
      while ( v20[v28] );
      if ( v25 <= v28 )
      {
        v29 = StringCchCopyNW(v41, v25 + 1, v20, v25);
        v3 = v29;
        if ( v29 < 0 )
        {
          v48 = v29;
          if ( LogAdapter::g_Logger )
          {
            v43 = (int *)v20;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v30,
              v31,
              (unsigned int)"Failed to copy parent of path: {}",
              (__int64)&v43);
            v44 = &v48;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v32,
              3,
              (unsigned int)": {}",
              (__int64)&v44);
          }
          v27 = 406;
          goto LABEL_31;
        }
      }
      Directory = RecursivelyCreateDirectory(v26, a2);
      v3 = Directory;
      if ( Directory < 0 )
      {
        v48 = Directory;
        if ( LogAdapter::g_Logger )
        {
          v44 = (int *)v26;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            v35,
            (unsigned int)"Failed to create path: {}",
            (__int64)&v44);
          v43 = &v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v36,
            3,
            (unsigned int)": {}",
            (__int64)&v43);
        }
        v27 = 408;
        goto LABEL_31;
      }
      if ( !CreateDirectoryW(v20, a2) )
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
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v41);
    }
    v3 = 0;
    goto LABEL_50;
  }
  v6 = 360;
LABEL_7:
  v5 = (unsigned int)v7;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v5,
    v39);
LABEL_50:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
  return v3;
}

```

## disassembly

```asm
0x14001fc6c  mov     [rsp-8+arg_10], rbx
0x14001fc71  mov     [rsp-8+arg_18], rsi
0x14001fc76  push    rbp
0x14001fc77  push    rdi
0x14001fc78  push    r12
0x14001fc7a  push    r14
0x14001fc7c  push    r15
0x14001fc7e  lea     rbp, [rsp-37h]
0x14001fc83  sub     rsp, 0A0h
0x14001fc8a  mov     rax, cs:__security_cookie
0x14001fc91  xor     rax, rsp
0x14001fc94  mov     [rbp+57h+var_28], rax
0x14001fc98  xor     eax, eax
0x14001fc9a  mov     [rbp+57h+var_50], rcx
0x14001fc9e  xor     r12d, r12d
0x14001fca1  mov     [rbp+57h+var_30], rax
0x14001fca5  mov     [rbp+57h+lpPathName], r12
0x14001fca9  xorps   xmm0, xmm0
0x14001fcac  mov     r14, rdx
0x14001fcaf  movups  [rbp+57h+var_40], xmm0
0x14001fcb3  test    rcx, rcx
0x14001fcb6  jnz     short loc_14001FD11
0x14001fcb8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fcbf  mov     esi, 80070057h
0x14001fcc4  mov     [rbp+57h+var_48], esi
0x14001fcc7  test    rcx, rcx
0x14001fcca  jz      short loc_14001FD07
0x14001fccc  lea     r9, aNoPathSpecifie; "No path specified"
0x14001fcd3  xor     edx, edx
0x14001fcd5  lea     r8d, [rax+3]
0x14001fcd9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001fcde  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fce5  lea     rax, [rbp+57h+var_48]
0x14001fce9  mov     [rbp+57h+var_88], rax
0x14001fced  lea     r9, asc_1400353E8; ": {}"
0x14001fcf4  lea     rax, [rbp+57h+var_88]
0x14001fcf8  lea     r8d, [r12+3]
0x14001fcfd  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001fd02  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001fd07  mov     r9d, esi
0x14001fd0a  mov     edx, 163h
0x14001fd0f  jmp     short loc_14001FD2B
0x14001fd11  mov     rdx, rcx
0x14001fd14  lea     rcx, [rbp+57h+lpPathName]
0x14001fd18  call    SczAllocFromSz
0x14001fd1d  mov     esi, eax
0x14001fd1f  test    eax, eax
0x14001fd21  jns     short loc_14001FD40
0x14001fd23  mov     edx, 168h; void *
0x14001fd28  mov     r9d, eax; char *
0x14001fd2b  mov     rcx, [rbp+5Fh]; this
0x14001fd2f  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001fd36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001fd3b  jmp     loc_14002007C
0x14001fd40  lea     rcx, [rbp+57h+lpPathName]
0x14001fd44  call    PathPrefix
0x14001fd49  mov     esi, eax
0x14001fd4b  test    eax, eax
0x14001fd4d  jns     short loc_14001FD56
0x14001fd4f  mov     edx, 169h
0x14001fd54  jmp     short loc_14001FD28
0x14001fd56  test    r14, r14
0x14001fd59  jnz     loc_14001FE5D
0x14001fd5f  lea     rcx, [rbp+57h+var_90]; this
0x14001fd63  mov     [rbp+57h+var_90], r12b
0x14001fd67  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x14001fd6c  mov     ebx, eax
0x14001fd6e  test    eax, eax
0x14001fd70  jns     short loc_14001FDCF
0x14001fd72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fd79  mov     [rbp+57h+var_48], eax
0x14001fd7c  test    rcx, rcx
0x14001fd7f  jz      short loc_14001FDB0
0x14001fd81  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x14001fd88  xor     edx, edx
0x14001fd8a  lea     r8d, [r14+3]
0x14001fd8e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001fd93  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fd9a  lea     rax, [rbp+57h+var_48]
0x14001fd9e  mov     [rbp+57h+var_88], rax
0x14001fda2  lea     rax, [rbp+57h+var_88]
0x14001fda6  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x14001fdab  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x14001fdb0  mov     edx, 16Fh; void *
0x14001fdb5  mov     rcx, [rbp+5Fh]; this
0x14001fdb9  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001fdc0  mov     r9d, ebx; char *
0x14001fdc3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14001fdc8  mov     esi, eax
0x14001fdca  jmp     loc_14002007C
0x14001fdcf  cmp     [rbp+57h+var_90], r12b
0x14001fdd3  jz      loc_14001FE5D
0x14001fdd9  lea     rcx, [rbp+57h+var_88]; this
0x14001fddd  mov     [rbp+57h+var_88], r12
0x14001fde1  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x14001fde6  mov     ebx, eax
0x14001fde8  test    eax, eax
0x14001fdea  jns     short loc_14001FE31
0x14001fdec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fdf3  mov     [rbp+57h+var_48], eax
0x14001fdf6  test    rcx, rcx
0x14001fdf9  jz      short loc_14001FE2A
0x14001fdfb  xor     edx, edx
0x14001fdfd  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x14001fe04  lea     r8d, [rdx+3]
0x14001fe08  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001fe0d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fe14  lea     rax, [rbp+57h+var_48]
0x14001fe18  mov     [rbp+57h+var_88], rax
0x14001fe1c  lea     rax, [rbp+57h+var_88]
0x14001fe20  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001fe25  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x14001fe2a  mov     edx, 175h
0x14001fe2f  jmp     short loc_14001FDB5
0x14001fe31  mov     rax, [rbp+57h+var_88]
0x14001fe35  lea     r14, [rbp+57h+var_40]
0x14001fe39  mov     qword ptr [rbp+57h+var_68+8], rax
0x14001fe3d  xor     eax, eax
0x14001fe3f  mov     qword ptr [rbp+57h+var_68], 18h
0x14001fe47  movups  xmm0, [rbp+57h+var_68]
0x14001fe4b  mov     [rbp+57h+var_58], rax
0x14001fe4f  movsd   xmm1, [rbp+57h+var_58]
0x14001fe54  movsd   [rbp+57h+var_30], xmm1
0x14001fe59  movups  [rbp+57h+var_40], xmm0
0x14001fe5d  mov     rbx, [rbp+57h+lpPathName]
0x14001fe61  mov     rdx, r14; lpSecurityAttributes
0x14001fe64  mov     rcx, rbx; lpPathName
0x14001fe67  call    cs:__imp_CreateDirectoryW
0x14001fe6d  test    eax, eax
0x14001fe6f  jnz     loc_140020079
0x14001fe75  call    cs:__imp_GetLastError
0x14001fe7b  cmp     eax, 0B7h
0x14001fe80  jz      loc_140020079
0x14001fe86  mov     edx, 5Ch ; '\'; Ch
0x14001fe8b  mov     rcx, rbx; Str
0x14001fe8e  call    cs:__imp_wcsrchr
0x14001fe94  mov     rsi, rax
0x14001fe97  test    rax, rax
0x14001fe9a  jnz     short loc_14001FEFC
0x14001fe9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fea3  mov     esi, 80070003h
0x14001fea8  mov     [rbp+57h+var_48], esi
0x14001feab  test    rcx, rcx
0x14001feae  jz      short loc_14001FEEF
0x14001feb0  lea     rax, [rbp+57h+var_50]
0x14001feb4  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x14001febb  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001fec0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001fec5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fecc  lea     rax, [rbp+57h+var_48]
0x14001fed0  mov     [rbp+57h+var_88], rax
0x14001fed4  lea     r9, asc_1400353E8; ": {}"
0x14001fedb  lea     rax, [rbp+57h+var_88]
0x14001fedf  mov     r8d, 3
0x14001fee5  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001feea  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001feef  mov     r9d, esi
0x14001fef2  mov     edx, 188h
0x14001fef7  jmp     loc_14001FD2B
0x14001fefc  sub     rsi, rbx
0x14001feff  mov     [rbp+57h+var_88], r12
0x14001ff03  sar     rsi, 1
0x14001ff06  lea     rcx, [rbp+57h+var_88]
0x14001ff0a  lea     rdx, [rsi+1]
0x14001ff0e  call    ?AllocateArray@?$AutoNewArrayPtr@_W@Windows@@QEAAPEA_W_K@Z; Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(unsigned __int64)
0x14001ff13  mov     rdi, [rbp+57h+var_88]
0x14001ff17  test    rdi, rdi
0x14001ff1a  jnz     short loc_14001FF47
0x14001ff1c  mov     esi, 8007000Eh
0x14001ff21  mov     edx, 18Fh; void *
0x14001ff26  mov     rcx, [rbp+5Fh]; this
0x14001ff2a  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001ff31  mov     r9d, esi; char *
0x14001ff34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ff39  lea     rcx, [rbp+57h+var_88]
0x14001ff3d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x14001ff42  jmp     loc_14002007C
0x14001ff47  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ff4b  inc     rax
0x14001ff4e  cmp     [rbx+rax*2], r12w
0x14001ff53  jnz     short loc_14001FF4B
0x14001ff55  cmp     rsi, rax
0x14001ff58  ja      short loc_14001FFCE
0x14001ff5a  mov     r9, rsi; unsigned __int64
0x14001ff5d  lea     rdx, [rsi+1]; unsigned __int64
0x14001ff61  mov     r8, rbx; wchar_t *
0x14001ff64  mov     rcx, rdi; wchar_t *
0x14001ff67  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x14001ff6c  mov     esi, eax
0x14001ff6e  test    eax, eax
0x14001ff70  jns     short loc_14001FFCE
0x14001ff72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ff79  mov     [rbp+57h+var_48], eax
0x14001ff7c  test    rcx, rcx
0x14001ff7f  jz      short loc_14001FFC4
0x14001ff81  lea     rax, [rbp+57h+var_78]
0x14001ff85  mov     [rbp+57h+var_78], rbx
0x14001ff89  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x14001ff90  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001ff95  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001ff9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ffa1  lea     rax, [rbp+57h+var_48]
0x14001ffa5  mov     [rbp+57h+var_70], rax
0x14001ffa9  lea     r9, asc_1400353E8; ": {}"
0x14001ffb0  lea     rax, [rbp+57h+var_70]
0x14001ffb4  mov     r8d, 3
0x14001ffba  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001ffbf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ffc4  mov     edx, 196h
0x14001ffc9  jmp     loc_14001FF26
0x14001ffce  mov     rdx, r14
0x14001ffd1  mov     rcx, rdi
0x14001ffd4  call    RecursivelyCreateDirectory
0x14001ffd9  mov     esi, eax
0x14001ffdb  test    eax, eax
0x14001ffdd  jns     short loc_14002003B
0x14001ffdf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ffe6  mov     [rbp+57h+var_48], eax
0x14001ffe9  test    rcx, rcx
0x14001ffec  jz      short loc_140020031
0x14001ffee  lea     rax, [rbp+57h+var_70]
0x14001fff2  mov     [rbp+57h+var_70], rdi
0x14001fff6  lea     r9, aFailedToCreate_2; "Failed to create path: {}"
0x14001fffd  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140020002  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140020007  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002000e  lea     rax, [rbp+57h+var_48]
0x140020012  mov     [rbp+57h+var_78], rax
0x140020016  lea     r9, asc_1400353E8; ": {}"
0x14002001d  lea     rax, [rbp+57h+var_78]
0x140020021  mov     r8d, 3
0x140020027  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14002002c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020031  mov     edx, 198h
0x140020036  jmp     loc_14001FF26
0x14002003b  mov     rdx, r14; lpSecurityAttributes
0x14002003e  mov     rcx, rbx; lpPathName
0x140020041  call    cs:__imp_CreateDirectoryW
0x140020047  test    eax, eax
0x140020049  jnz     short loc_140020070
0x14002004b  call    cs:__imp_GetLastError
0x140020051  mov     esi, eax
0x140020053  cmp     eax, 0B7h
0x140020058  jz      short loc_140020070
0x14002005a  test    eax, eax
0x14002005c  jle     loc_14001FF39
0x140020062  movzx   esi, ax
0x140020065  or      esi, 80070000h
0x14002006b  jmp     loc_14001FF39
0x140020070  lea     rcx, [rbp+57h+var_88]
0x140020074  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140020079  mov     esi, r12d
0x14002007c  lea     rcx, [rbp+57h+lpPathName]
0x140020080  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140020085  mov     eax, esi
0x140020087  mov     rcx, [rbp+57h+var_28]
0x14002008b  xor     rcx, rsp; StackCookie
0x14002008e  call    __security_check_cookie
0x140020093  lea     r11, [rsp+0C0h+var_20]
0x14002009b  mov     rbx, [r11+40h]
0x14002009f  mov     rsi, [r11+48h]
0x1400200a3  mov     rsp, r11
0x1400200a6  pop     r15
0x1400200a8  pop     r14
0x1400200aa  pop     r12
0x1400200ac  pop     rdi
0x1400200ad  pop     rbp
0x1400200ae  retn
```
