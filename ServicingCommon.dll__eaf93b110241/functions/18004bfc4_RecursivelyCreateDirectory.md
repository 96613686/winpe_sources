# RecursivelyCreateDirectory

- ea: `0x18004bfc4`
- end: `0x18004c44b`
- name: `RecursivelyCreateDirectory`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180044c90`
- `0x18004bfc4`

## callees

- `0x18001e51c`
- `0x180022d80`
- `0x1800293a0`
- `0x18002a208`
- `0x180041a74`
- `0x180041c30`
- `0x180041de8`
- `0x180043380`
- `0x180043c00`
- `0x18004689c`
- `0x1800474d0`
- `0x18004ad14`
- `0x18004ad54`
- `0x18004bfc4`
- `0x18004d3a0`
- `0x18004dec8`
- `0x18006cbdc`
- `0x18006d0a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004c1f1`
- `KERNEL32!GetLastError` at `0x18004c3e0`
- `KERNEL32!GetLastError` at `0x18004c1f1`
- `KERNEL32!GetLastError` at `0x18004c3e0`
- `KERNEL32!CreateDirectoryW` at `0x18004c1dd`
- `KERNEL32!CreateDirectoryW` at `0x18004c3d0`
- `KERNEL32!CreateDirectoryW` at `0x18004c1dd`
- `KERNEL32!CreateDirectoryW` at `0x18004c3d0`

## string_xrefs

- `0x18004c02c`: `No path specified`
- `0x18004c165`: `Failed calling GetSystemSecurity`
- `0x18004c235`: `Cannot find parent for path: {}.`
- `0x18004c317`: `Failed to copy parent of path: {}`
- `0x18004c38b`: `Failed to create path: {}`

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
  unsigned int v11; // edi
  int v12; // edx
  __int64 v13; // rdx
  int SystemSecurity; // eax
  int v15; // edx
  const wchar_t *v16; // rbx
  wchar_t *v17; // rax
  int v18; // edx
  int v19; // r8d
  int v20; // edx
  unsigned __int64 v21; // rsi
  wchar_t *v22; // rdi
  __int64 v23; // rdx
  unsigned __int64 v24; // rax
  int v25; // eax
  int v26; // edx
  int Directory; // eax
  int v28; // edx
  signed int LastError; // eax
  int v31; // [rsp+20h] [rbp-49h]
  _BYTE v32[8]; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *v33; // [rsp+38h] [rbp-31h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-29h] BYREF
  int *v35; // [rsp+48h] [rbp-21h] BYREF
  int *v36; // [rsp+50h] [rbp-19h] BYREF
  __int128 v37; // [rsp+58h] [rbp-11h]
  __int64 v38; // [rsp+68h] [rbp-1h]
  __int64 v39; // [rsp+70h] [rbp+7h] BYREF
  int v40; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v41; // [rsp+80h] [rbp+17h] BYREF
  __int64 v42; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v39 = a1;
  v42 = 0;
  lpPathName = 0;
  v41 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v40 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      v33 = (wchar_t *)&v40;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&v33);
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
      v32[0] = 0;
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                            (Windows::WCP::Implementation::Rtl *)v32,
                            v8);
      v11 = CanSetSystemOwner;
      if ( CanSetSystemOwner < 0 )
      {
        v40 = CanSetSystemOwner;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling CanSetSystemOwner");
          v33 = (wchar_t *)&v40;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v12,
            3,
            (unsigned int)": {}",
            (__int64)&v33);
        }
        v13 = 367;
LABEL_16:
        v3 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v13,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v11,
               v31);
        goto LABEL_50;
      }
      if ( v32[0] )
      {
        v33 = 0;
        SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                           (Windows::WCP::Implementation::Rtl *)&v33,
                           v10);
        v11 = SystemSecurity;
        if ( SystemSecurity < 0 )
        {
          v40 = SystemSecurity;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling GetSystemSecurity");
            v33 = (wchar_t *)&v40;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v15,
              3,
              (unsigned int)": {}",
              (__int64)&v33);
          }
          v13 = 373;
          goto LABEL_16;
        }
        a2 = (struct _SECURITY_ATTRIBUTES *)&v41;
        *((_QWORD *)&v37 + 1) = v33;
        *(_QWORD *)&v37 = 24;
        v38 = 0;
        v42 = 0;
        v41 = v37;
      }
    }
    v16 = lpPathName;
    if ( !CreateDirectoryW(lpPathName, a2) && GetLastError() != 183 )
    {
      v17 = wcsrchr(v16, 0x5Cu);
      if ( !v17 )
      {
        v3 = -2147024893;
        v40 = -2147024893;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v18,
            v19,
            (unsigned int)"Cannot find parent for path: {}.",
            (__int64)&v39);
          v33 = (wchar_t *)&v40;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v20,
            3,
            (unsigned int)": {}",
            (__int64)&v33);
        }
        v5 = 2147942403LL;
        v6 = 392;
        goto LABEL_8;
      }
      v33 = 0;
      v21 = v17 - v16;
      Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(&v33, v21 + 1);
      v22 = v33;
      if ( !v33 )
      {
        v3 = -2147024882;
        v23 = 399;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v3,
          v31);
LABEL_32:
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
        goto LABEL_50;
      }
      v24 = -1;
      do
        ++v24;
      while ( v16[v24] );
      if ( v21 <= v24 )
      {
        v25 = StringCchCopyNW(v33, v21 + 1, v16, v21);
        v3 = v25;
        if ( v25 < 0 )
        {
          v40 = v25;
          if ( LogAdapter::g_Logger )
          {
            v35 = (int *)v16;
            LogAdapter::Logger::LogNumObjects<wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to copy parent of path: {}",
              (__int64)&v35);
            v36 = &v40;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v26,
              3,
              (unsigned int)": {}",
              (__int64)&v36);
          }
          v23 = 406;
          goto LABEL_31;
        }
      }
      Directory = RecursivelyCreateDirectory(v22, a2);
      v3 = Directory;
      if ( Directory < 0 )
      {
        v40 = Directory;
        if ( LogAdapter::g_Logger )
        {
          v36 = (int *)v22;
          LogAdapter::Logger::LogNumObjects<wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to create path: {}",
            (__int64)&v36);
          v35 = &v40;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v28,
            3,
            (unsigned int)": {}",
            (__int64)&v35);
        }
        v23 = 408;
        goto LABEL_31;
      }
      if ( !CreateDirectoryW(v16, a2) )
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
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v33);
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
    v31);
LABEL_50:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpPathName);
  return v3;
}

```

## disassembly

```asm
0x18004bfc4  mov     [rsp-8+arg_10], rbx
0x18004bfc9  mov     [rsp-8+arg_18], rsi
0x18004bfce  push    rbp
0x18004bfcf  push    rdi
0x18004bfd0  push    r12
0x18004bfd2  push    r14
0x18004bfd4  push    r15
0x18004bfd6  lea     rbp, [rsp-37h]
0x18004bfdb  sub     rsp, 0A0h
0x18004bfe2  mov     rax, cs:__security_cookie
0x18004bfe9  xor     rax, rsp
0x18004bfec  mov     [rbp+57h+var_28], rax
0x18004bff0  xor     eax, eax
0x18004bff2  mov     [rbp+57h+var_50], rcx
0x18004bff6  xor     r12d, r12d
0x18004bff9  mov     [rbp+57h+var_30], rax
0x18004bffd  mov     [rbp+57h+lpPathName], r12
0x18004c001  xorps   xmm0, xmm0
0x18004c004  mov     r14, rdx
0x18004c007  movups  [rbp+57h+var_40], xmm0
0x18004c00b  test    rcx, rcx
0x18004c00e  jnz     short loc_18004C069
0x18004c010  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c017  mov     esi, 80070057h
0x18004c01c  mov     [rbp+57h+var_48], esi
0x18004c01f  test    rcx, rcx
0x18004c022  jz      short loc_18004C05F
0x18004c024  lea     ebx, [rax+3]
0x18004c027  xor     edx, edx
0x18004c029  mov     r8d, ebx
0x18004c02c  lea     r9, aNoPathSpecifie; "No path specified"
0x18004c033  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004c038  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c03f  lea     rax, [rbp+57h+var_48]
0x18004c043  mov     [rbp+57h+var_88], rax
0x18004c047  lea     r9, asc_1800AFB70; ": {}"
0x18004c04e  lea     rax, [rbp+57h+var_88]
0x18004c052  mov     r8d, ebx
0x18004c055  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c05a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c05f  mov     r9d, esi
0x18004c062  mov     edx, 163h
0x18004c067  jmp     short loc_18004C083
0x18004c069  mov     rdx, rcx
0x18004c06c  lea     rcx, [rbp+57h+lpPathName]
0x18004c070  call    SczAllocFromSz
0x18004c075  mov     esi, eax
0x18004c077  test    eax, eax
0x18004c079  jns     short loc_18004C098
0x18004c07b  mov     edx, 168h; void *
0x18004c080  mov     r9d, eax; char *
0x18004c083  mov     rcx, [rbp+5Fh]; this
0x18004c087  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004c08e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c093  jmp     loc_18004C417
0x18004c098  lea     rcx, [rbp+57h+lpPathName]
0x18004c09c  call    PathPrefix
0x18004c0a1  mov     esi, eax
0x18004c0a3  test    eax, eax
0x18004c0a5  jns     short loc_18004C0AE
0x18004c0a7  mov     edx, 169h
0x18004c0ac  jmp     short loc_18004C080
0x18004c0ae  test    r14, r14
0x18004c0b1  jnz     loc_18004C1D3
0x18004c0b7  lea     rcx, [rbp+57h+var_90]; this
0x18004c0bb  mov     [rbp+57h+var_90], r12b
0x18004c0bf  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18004c0c4  mov     edi, eax
0x18004c0c6  test    eax, eax
0x18004c0c8  jns     short loc_18004C134
0x18004c0ca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c0d1  mov     [rbp+57h+var_48], eax
0x18004c0d4  test    rcx, rcx
0x18004c0d7  jz      short loc_18004C115
0x18004c0d9  lea     ebx, [r14+3]
0x18004c0dd  xor     edx, edx
0x18004c0df  mov     r8d, ebx
0x18004c0e2  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x18004c0e9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004c0ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c0f5  lea     rax, [rbp+57h+var_48]
0x18004c0f9  mov     [rbp+57h+var_88], rax
0x18004c0fd  lea     r9, asc_1800AFB70; ": {}"
0x18004c104  lea     rax, [rbp+57h+var_88]
0x18004c108  mov     r8d, ebx
0x18004c10b  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004c110  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004c115  mov     edx, 16Fh; void *
0x18004c11a  mov     rcx, [rbp+5Fh]; this
0x18004c11e  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004c125  mov     r9d, edi; char *
0x18004c128  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004c12d  mov     esi, eax
0x18004c12f  jmp     loc_18004C417
0x18004c134  cmp     [rbp+57h+var_90], r12b
0x18004c138  jz      loc_18004C1D3
0x18004c13e  lea     rcx, [rbp+57h+var_88]; this
0x18004c142  mov     [rbp+57h+var_88], r12
0x18004c146  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18004c14b  mov     edi, eax
0x18004c14d  test    eax, eax
0x18004c14f  jns     short loc_18004C1A7
0x18004c151  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c158  mov     [rbp+57h+var_48], eax
0x18004c15b  test    rcx, rcx
0x18004c15e  jz      short loc_18004C19D
0x18004c160  mov     ebx, 3
0x18004c165  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x18004c16c  mov     r8d, ebx
0x18004c16f  xor     edx, edx
0x18004c171  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004c176  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c17d  lea     rax, [rbp+57h+var_48]
0x18004c181  mov     [rbp+57h+var_88], rax
0x18004c185  lea     r9, asc_1800AFB70; ": {}"
0x18004c18c  lea     rax, [rbp+57h+var_88]
0x18004c190  mov     r8d, ebx
0x18004c193  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c198  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004c19d  mov     edx, 175h
0x18004c1a2  jmp     loc_18004C11A
0x18004c1a7  mov     rax, [rbp+57h+var_88]
0x18004c1ab  lea     r14, [rbp+57h+var_40]
0x18004c1af  mov     qword ptr [rbp+57h+var_68+8], rax
0x18004c1b3  xor     eax, eax
0x18004c1b5  mov     qword ptr [rbp+57h+var_68], 18h
0x18004c1bd  movups  xmm0, [rbp+57h+var_68]
0x18004c1c1  mov     [rbp+57h+var_58], rax
0x18004c1c5  movsd   xmm1, [rbp+57h+var_58]
0x18004c1ca  movsd   [rbp+57h+var_30], xmm1
0x18004c1cf  movups  [rbp+57h+var_40], xmm0
0x18004c1d3  mov     rbx, [rbp+57h+lpPathName]
0x18004c1d7  mov     rdx, r14; lpSecurityAttributes
0x18004c1da  mov     rcx, rbx; lpPathName
0x18004c1dd  call    cs:__imp_CreateDirectoryW
0x18004c1e4  nop     dword ptr [rax+rax+00h]
0x18004c1e9  test    eax, eax
0x18004c1eb  jnz     loc_18004C414
0x18004c1f1  call    cs:__imp_GetLastError
0x18004c1f8  nop     dword ptr [rax+rax+00h]
0x18004c1fd  cmp     eax, 0B7h
0x18004c202  jz      loc_18004C414
0x18004c208  mov     edx, 5Ch ; '\'; Ch
0x18004c20d  mov     rcx, rbx; Str
0x18004c210  call    wcsrchr
0x18004c215  mov     rsi, rax
0x18004c218  test    rax, rax
0x18004c21b  jnz     short loc_18004C27D
0x18004c21d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c224  mov     esi, 80070003h
0x18004c229  mov     [rbp+57h+var_48], esi
0x18004c22c  test    rcx, rcx
0x18004c22f  jz      short loc_18004C270
0x18004c231  lea     rax, [rbp+57h+var_50]
0x18004c235  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x18004c23c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c241  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004c246  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c24d  lea     rax, [rbp+57h+var_48]
0x18004c251  mov     [rbp+57h+var_88], rax
0x18004c255  lea     r9, asc_1800AFB70; ": {}"
0x18004c25c  lea     rax, [rbp+57h+var_88]
0x18004c260  mov     r8d, 3
0x18004c266  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c26b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c270  mov     r9d, esi
0x18004c273  mov     edx, 188h
0x18004c278  jmp     loc_18004C083
0x18004c27d  sub     rsi, rbx
0x18004c280  mov     [rbp+57h+var_88], r12
0x18004c284  sar     rsi, 1
0x18004c287  lea     rcx, [rbp+57h+var_88]
0x18004c28b  lea     rdx, [rsi+1]
0x18004c28f  call    ?AllocateArray@?$AutoNewArrayPtr@_W@Windows@@QEAAPEA_W_K@Z; Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(unsigned __int64)
0x18004c294  mov     rdi, [rbp+57h+var_88]
0x18004c298  test    rdi, rdi
0x18004c29b  jnz     short loc_18004C2C8
0x18004c29d  mov     esi, 8007000Eh
0x18004c2a2  mov     edx, 18Fh; void *
0x18004c2a7  mov     rcx, [rbp+5Fh]; this
0x18004c2ab  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004c2b2  mov     r9d, esi; char *
0x18004c2b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c2ba  lea     rcx, [rbp+57h+var_88]
0x18004c2be  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004c2c3  jmp     loc_18004C417
0x18004c2c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c2cc  inc     rax
0x18004c2cf  cmp     [rbx+rax*2], r12w
0x18004c2d4  jnz     short loc_18004C2CC
0x18004c2d6  cmp     rsi, rax
0x18004c2d9  ja      short loc_18004C356
0x18004c2db  mov     r9, rsi; unsigned __int64
0x18004c2de  lea     rdx, [rsi+1]; unsigned __int64
0x18004c2e2  mov     r8, rbx; wchar_t *
0x18004c2e5  mov     rcx, rdi; wchar_t *
0x18004c2e8  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18004c2ed  mov     esi, eax
0x18004c2ef  test    eax, eax
0x18004c2f1  jns     short loc_18004C356
0x18004c2f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c2fa  mov     [rbp+57h+var_48], eax
0x18004c2fd  test    rcx, rcx
0x18004c300  jz      short loc_18004C34C
0x18004c302  mov     [rbp+57h+var_78], rbx
0x18004c306  lea     rax, [rbp+57h+var_78]
0x18004c30a  mov     ebx, 3
0x18004c30f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c314  mov     r8d, ebx
0x18004c317  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x18004c31e  xor     edx, edx
0x18004c320  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004c325  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c32c  lea     rax, [rbp+57h+var_48]
0x18004c330  mov     [rbp+57h+var_70], rax
0x18004c334  lea     r9, asc_1800AFB70; ": {}"
0x18004c33b  lea     rax, [rbp+57h+var_70]
0x18004c33f  mov     r8d, ebx
0x18004c342  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c347  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c34c  mov     edx, 196h
0x18004c351  jmp     loc_18004C2A7
0x18004c356  mov     rdx, r14
0x18004c359  mov     rcx, rdi
0x18004c35c  call    RecursivelyCreateDirectory
0x18004c361  mov     esi, eax
0x18004c363  test    eax, eax
0x18004c365  jns     short loc_18004C3CA
0x18004c367  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c36e  mov     [rbp+57h+var_48], eax
0x18004c371  test    rcx, rcx
0x18004c374  jz      short loc_18004C3C0
0x18004c376  lea     rax, [rbp+57h+var_70]
0x18004c37a  mov     [rbp+57h+var_70], rdi
0x18004c37e  mov     ebx, 3
0x18004c383  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c388  mov     r8d, ebx
0x18004c38b  lea     r9, aFailedToCreate; "Failed to create path: {}"
0x18004c392  xor     edx, edx
0x18004c394  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004c399  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c3a0  lea     rax, [rbp+57h+var_48]
0x18004c3a4  mov     [rbp+57h+var_78], rax
0x18004c3a8  lea     r9, asc_1800AFB70; ": {}"
0x18004c3af  lea     rax, [rbp+57h+var_78]
0x18004c3b3  mov     r8d, ebx
0x18004c3b6  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004c3bb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c3c0  mov     edx, 198h
0x18004c3c5  jmp     loc_18004C2A7
0x18004c3ca  mov     rdx, r14; lpSecurityAttributes
0x18004c3cd  mov     rcx, rbx; lpPathName
0x18004c3d0  call    cs:__imp_CreateDirectoryW
0x18004c3d7  nop     dword ptr [rax+rax+00h]
0x18004c3dc  test    eax, eax
0x18004c3de  jnz     short loc_18004C40B
0x18004c3e0  call    cs:__imp_GetLastError
0x18004c3e7  nop     dword ptr [rax+rax+00h]
0x18004c3ec  mov     esi, eax
0x18004c3ee  cmp     eax, 0B7h
0x18004c3f3  jz      short loc_18004C40B
0x18004c3f5  test    eax, eax
0x18004c3f7  jle     loc_18004C2BA
0x18004c3fd  movzx   esi, ax
0x18004c400  or      esi, 80070000h
0x18004c406  jmp     loc_18004C2BA
0x18004c40b  lea     rcx, [rbp+57h+var_88]
0x18004c40f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004c414  mov     esi, r12d
0x18004c417  lea     rcx, [rbp+57h+lpPathName]
0x18004c41b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004c420  mov     eax, esi
0x18004c422  mov     rcx, [rbp+57h+var_28]
0x18004c426  xor     rcx, rsp; StackCookie
0x18004c429  call    __security_check_cookie
0x18004c42e  lea     r11, [rsp+0C0h+var_20]
0x18004c436  mov     rbx, [r11+40h]
0x18004c43a  mov     rsi, [r11+48h]
0x18004c43e  mov     rsp, r11
0x18004c441  pop     r15
0x18004c443  pop     r14
0x18004c445  pop     r12
0x18004c447  pop     rdi
0x18004c448  pop     rbp
0x18004c449  retn
```
