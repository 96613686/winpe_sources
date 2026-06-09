# RecursivelyCreateDirectory

- ea: `0x18004f0e4`
- end: `0x18004f56b`
- name: `RecursivelyCreateDirectory`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047e20`
- `0x18004f0e4`

## callees

- `0x180020440`
- `0x180026c90`
- `0x18002d2b0`
- `0x18002e118`
- `0x180045914`
- `0x180046650`
- `0x1800468fc`
- `0x180046bb4`
- `0x180046ca4`
- `0x1800499cc`
- `0x18004a5f8`
- `0x18004de34`
- `0x18004de74`
- `0x18004f0e4`
- `0x1800504d0`
- `0x180051000`
- `0x18006cacc`
- `0x18006cf90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f311`
- `KERNEL32!GetLastError` at `0x18004f500`
- `KERNEL32!GetLastError` at `0x18004f311`
- `KERNEL32!GetLastError` at `0x18004f500`
- `KERNEL32!CreateDirectoryW` at `0x18004f2fd`
- `KERNEL32!CreateDirectoryW` at `0x18004f4f0`
- `KERNEL32!CreateDirectoryW` at `0x18004f2fd`
- `KERNEL32!CreateDirectoryW` at `0x18004f4f0`

## string_xrefs

- `0x18004f14c`: `No path specified`
- `0x18004f285`: `Failed calling GetSystemSecurity`
- `0x18004f355`: `Cannot find parent for path: {}.`
- `0x18004f437`: `Failed to copy parent of path: {}`
- `0x18004f4ab`: `Failed to create path: {}`

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
0x18004f0e4  mov     [rsp-8+arg_10], rbx
0x18004f0e9  mov     [rsp-8+arg_18], rsi
0x18004f0ee  push    rbp
0x18004f0ef  push    rdi
0x18004f0f0  push    r12
0x18004f0f2  push    r14
0x18004f0f4  push    r15
0x18004f0f6  lea     rbp, [rsp-37h]
0x18004f0fb  sub     rsp, 0A0h
0x18004f102  mov     rax, cs:__security_cookie
0x18004f109  xor     rax, rsp
0x18004f10c  mov     [rbp+57h+var_28], rax
0x18004f110  xor     eax, eax
0x18004f112  mov     [rbp+57h+var_50], rcx
0x18004f116  xor     r12d, r12d
0x18004f119  mov     [rbp+57h+var_30], rax
0x18004f11d  mov     [rbp+57h+lpPathName], r12
0x18004f121  xorps   xmm0, xmm0
0x18004f124  mov     r14, rdx
0x18004f127  movups  [rbp+57h+var_40], xmm0
0x18004f12b  test    rcx, rcx
0x18004f12e  jnz     short loc_18004F189
0x18004f130  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f137  mov     esi, 80070057h
0x18004f13c  mov     [rbp+57h+var_48], esi
0x18004f13f  test    rcx, rcx
0x18004f142  jz      short loc_18004F17F
0x18004f144  lea     ebx, [rax+3]
0x18004f147  xor     edx, edx
0x18004f149  mov     r8d, ebx
0x18004f14c  lea     r9, aNoPathSpecifie; "No path specified"
0x18004f153  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004f158  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f15f  lea     rax, [rbp+57h+var_48]
0x18004f163  mov     [rbp+57h+var_88], rax
0x18004f167  lea     r9, asc_1800AFAD8; ": {}"
0x18004f16e  lea     rax, [rbp+57h+var_88]
0x18004f172  mov     r8d, ebx
0x18004f175  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f17a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004f17f  mov     r9d, esi
0x18004f182  mov     edx, 163h
0x18004f187  jmp     short loc_18004F1A3
0x18004f189  mov     rdx, rcx
0x18004f18c  lea     rcx, [rbp+57h+lpPathName]
0x18004f190  call    SczAllocFromSz
0x18004f195  mov     esi, eax
0x18004f197  test    eax, eax
0x18004f199  jns     short loc_18004F1B8
0x18004f19b  mov     edx, 168h; void *
0x18004f1a0  mov     r9d, eax; char *
0x18004f1a3  mov     rcx, [rbp+5Fh]; this
0x18004f1a7  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004f1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f1b3  jmp     loc_18004F537
0x18004f1b8  lea     rcx, [rbp+57h+lpPathName]
0x18004f1bc  call    PathPrefix
0x18004f1c1  mov     esi, eax
0x18004f1c3  test    eax, eax
0x18004f1c5  jns     short loc_18004F1CE
0x18004f1c7  mov     edx, 169h
0x18004f1cc  jmp     short loc_18004F1A0
0x18004f1ce  test    r14, r14
0x18004f1d1  jnz     loc_18004F2F3
0x18004f1d7  lea     rcx, [rbp+57h+var_90]; this
0x18004f1db  mov     [rbp+57h+var_90], r12b
0x18004f1df  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18004f1e4  mov     edi, eax
0x18004f1e6  test    eax, eax
0x18004f1e8  jns     short loc_18004F254
0x18004f1ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f1f1  mov     [rbp+57h+var_48], eax
0x18004f1f4  test    rcx, rcx
0x18004f1f7  jz      short loc_18004F235
0x18004f1f9  lea     ebx, [r14+3]
0x18004f1fd  xor     edx, edx
0x18004f1ff  mov     r8d, ebx
0x18004f202  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x18004f209  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004f20e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f215  lea     rax, [rbp+57h+var_48]
0x18004f219  mov     [rbp+57h+var_88], rax
0x18004f21d  lea     r9, asc_1800AFAD8; ": {}"
0x18004f224  lea     rax, [rbp+57h+var_88]
0x18004f228  mov     r8d, ebx
0x18004f22b  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004f230  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004f235  mov     edx, 16Fh; void *
0x18004f23a  mov     rcx, [rbp+5Fh]; this
0x18004f23e  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004f245  mov     r9d, edi; char *
0x18004f248  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004f24d  mov     esi, eax
0x18004f24f  jmp     loc_18004F537
0x18004f254  cmp     [rbp+57h+var_90], r12b
0x18004f258  jz      loc_18004F2F3
0x18004f25e  lea     rcx, [rbp+57h+var_88]; this
0x18004f262  mov     [rbp+57h+var_88], r12
0x18004f266  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18004f26b  mov     edi, eax
0x18004f26d  test    eax, eax
0x18004f26f  jns     short loc_18004F2C7
0x18004f271  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f278  mov     [rbp+57h+var_48], eax
0x18004f27b  test    rcx, rcx
0x18004f27e  jz      short loc_18004F2BD
0x18004f280  mov     ebx, 3
0x18004f285  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x18004f28c  mov     r8d, ebx
0x18004f28f  xor     edx, edx
0x18004f291  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004f296  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f29d  lea     rax, [rbp+57h+var_48]
0x18004f2a1  mov     [rbp+57h+var_88], rax
0x18004f2a5  lea     r9, asc_1800AFAD8; ": {}"
0x18004f2ac  lea     rax, [rbp+57h+var_88]
0x18004f2b0  mov     r8d, ebx
0x18004f2b3  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f2b8  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004f2bd  mov     edx, 175h
0x18004f2c2  jmp     loc_18004F23A
0x18004f2c7  mov     rax, [rbp+57h+var_88]
0x18004f2cb  lea     r14, [rbp+57h+var_40]
0x18004f2cf  mov     qword ptr [rbp+57h+var_68+8], rax
0x18004f2d3  xor     eax, eax
0x18004f2d5  mov     qword ptr [rbp+57h+var_68], 18h
0x18004f2dd  movups  xmm0, [rbp+57h+var_68]
0x18004f2e1  mov     [rbp+57h+var_58], rax
0x18004f2e5  movsd   xmm1, [rbp+57h+var_58]
0x18004f2ea  movsd   [rbp+57h+var_30], xmm1
0x18004f2ef  movups  [rbp+57h+var_40], xmm0
0x18004f2f3  mov     rbx, [rbp+57h+lpPathName]
0x18004f2f7  mov     rdx, r14; lpSecurityAttributes
0x18004f2fa  mov     rcx, rbx; lpPathName
0x18004f2fd  call    cs:__imp_CreateDirectoryW
0x18004f304  nop     dword ptr [rax+rax+00h]
0x18004f309  test    eax, eax
0x18004f30b  jnz     loc_18004F534
0x18004f311  call    cs:__imp_GetLastError
0x18004f318  nop     dword ptr [rax+rax+00h]
0x18004f31d  cmp     eax, 0B7h
0x18004f322  jz      loc_18004F534
0x18004f328  mov     edx, 5Ch ; '\'; Ch
0x18004f32d  mov     rcx, rbx; Str
0x18004f330  call    wcsrchr
0x18004f335  mov     rsi, rax
0x18004f338  test    rax, rax
0x18004f33b  jnz     short loc_18004F39D
0x18004f33d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f344  mov     esi, 80070003h
0x18004f349  mov     [rbp+57h+var_48], esi
0x18004f34c  test    rcx, rcx
0x18004f34f  jz      short loc_18004F390
0x18004f351  lea     rax, [rbp+57h+var_50]
0x18004f355  lea     r9, aCannotFindPare; "Cannot find parent for path: {}."
0x18004f35c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f361  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004f366  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f36d  lea     rax, [rbp+57h+var_48]
0x18004f371  mov     [rbp+57h+var_88], rax
0x18004f375  lea     r9, asc_1800AFAD8; ": {}"
0x18004f37c  lea     rax, [rbp+57h+var_88]
0x18004f380  mov     r8d, 3
0x18004f386  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f38b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004f390  mov     r9d, esi
0x18004f393  mov     edx, 188h
0x18004f398  jmp     loc_18004F1A3
0x18004f39d  sub     rsi, rbx
0x18004f3a0  mov     [rbp+57h+var_88], r12
0x18004f3a4  sar     rsi, 1
0x18004f3a7  lea     rcx, [rbp+57h+var_88]
0x18004f3ab  lea     rdx, [rsi+1]
0x18004f3af  call    ?AllocateArray@?$AutoNewArrayPtr@_W@Windows@@QEAAPEA_W_K@Z; Windows::AutoNewArrayPtr<wchar_t>::AllocateArray(unsigned __int64)
0x18004f3b4  mov     rdi, [rbp+57h+var_88]
0x18004f3b8  test    rdi, rdi
0x18004f3bb  jnz     short loc_18004F3E8
0x18004f3bd  mov     esi, 8007000Eh
0x18004f3c2  mov     edx, 18Fh; void *
0x18004f3c7  mov     rcx, [rbp+5Fh]; this
0x18004f3cb  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004f3d2  mov     r9d, esi; char *
0x18004f3d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f3da  lea     rcx, [rbp+57h+var_88]
0x18004f3de  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004f3e3  jmp     loc_18004F537
0x18004f3e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f3ec  inc     rax
0x18004f3ef  cmp     [rbx+rax*2], r12w
0x18004f3f4  jnz     short loc_18004F3EC
0x18004f3f6  cmp     rsi, rax
0x18004f3f9  ja      short loc_18004F476
0x18004f3fb  mov     r9, rsi; unsigned __int64
0x18004f3fe  lea     rdx, [rsi+1]; unsigned __int64
0x18004f402  mov     r8, rbx; wchar_t *
0x18004f405  mov     rcx, rdi; wchar_t *
0x18004f408  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18004f40d  mov     esi, eax
0x18004f40f  test    eax, eax
0x18004f411  jns     short loc_18004F476
0x18004f413  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f41a  mov     [rbp+57h+var_48], eax
0x18004f41d  test    rcx, rcx
0x18004f420  jz      short loc_18004F46C
0x18004f422  mov     [rbp+57h+var_78], rbx
0x18004f426  lea     rax, [rbp+57h+var_78]
0x18004f42a  mov     ebx, 3
0x18004f42f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f434  mov     r8d, ebx
0x18004f437  lea     r9, aFailedToCopyPa; "Failed to copy parent of path: {}"
0x18004f43e  xor     edx, edx
0x18004f440  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004f445  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f44c  lea     rax, [rbp+57h+var_48]
0x18004f450  mov     [rbp+57h+var_70], rax
0x18004f454  lea     r9, asc_1800AFAD8; ": {}"
0x18004f45b  lea     rax, [rbp+57h+var_70]
0x18004f45f  mov     r8d, ebx
0x18004f462  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f467  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004f46c  mov     edx, 196h
0x18004f471  jmp     loc_18004F3C7
0x18004f476  mov     rdx, r14
0x18004f479  mov     rcx, rdi
0x18004f47c  call    RecursivelyCreateDirectory
0x18004f481  mov     esi, eax
0x18004f483  test    eax, eax
0x18004f485  jns     short loc_18004F4EA
0x18004f487  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f48e  mov     [rbp+57h+var_48], eax
0x18004f491  test    rcx, rcx
0x18004f494  jz      short loc_18004F4E0
0x18004f496  lea     rax, [rbp+57h+var_70]
0x18004f49a  mov     [rbp+57h+var_70], rdi
0x18004f49e  mov     ebx, 3
0x18004f4a3  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f4a8  mov     r8d, ebx
0x18004f4ab  lea     r9, aFailedToCreate_0; "Failed to create path: {}"
0x18004f4b2  xor     edx, edx
0x18004f4b4  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004f4b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004f4c0  lea     rax, [rbp+57h+var_48]
0x18004f4c4  mov     [rbp+57h+var_78], rax
0x18004f4c8  lea     r9, asc_1800AFAD8; ": {}"
0x18004f4cf  lea     rax, [rbp+57h+var_78]
0x18004f4d3  mov     r8d, ebx
0x18004f4d6  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004f4db  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004f4e0  mov     edx, 198h
0x18004f4e5  jmp     loc_18004F3C7
0x18004f4ea  mov     rdx, r14; lpSecurityAttributes
0x18004f4ed  mov     rcx, rbx; lpPathName
0x18004f4f0  call    cs:__imp_CreateDirectoryW
0x18004f4f7  nop     dword ptr [rax+rax+00h]
0x18004f4fc  test    eax, eax
0x18004f4fe  jnz     short loc_18004F52B
0x18004f500  call    cs:__imp_GetLastError
0x18004f507  nop     dword ptr [rax+rax+00h]
0x18004f50c  mov     esi, eax
0x18004f50e  cmp     eax, 0B7h
0x18004f513  jz      short loc_18004F52B
0x18004f515  test    eax, eax
0x18004f517  jle     loc_18004F3DA
0x18004f51d  movzx   esi, ax
0x18004f520  or      esi, 80070000h
0x18004f526  jmp     loc_18004F3DA
0x18004f52b  lea     rcx, [rbp+57h+var_88]
0x18004f52f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004f534  mov     esi, r12d
0x18004f537  lea     rcx, [rbp+57h+lpPathName]
0x18004f53b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004f540  mov     eax, esi
0x18004f542  mov     rcx, [rbp+57h+var_28]
0x18004f546  xor     rcx, rsp; StackCookie
0x18004f549  call    __security_check_cookie
0x18004f54e  lea     r11, [rsp+0C0h+var_20]
0x18004f556  mov     rbx, [r11+40h]
0x18004f55a  mov     rsi, [r11+48h]
0x18004f55e  mov     rsp, r11
0x18004f561  pop     r15
0x18004f563  pop     r14
0x18004f565  pop     r12
0x18004f567  pop     rdi
0x18004f568  pop     rbp
0x18004f569  retn
```
