# WriteAllBuffers(wil::basic_zstring_view<wchar_t> const &,std::vector<std::pair<uchar const * const,unsigned __int64 const>,std::allocator<std::pair<uchar const * const,unsigned __int64 const>>> const &,bool)

- ea: `0x1801e35e8`
- end: `0x1801e3b16`
- name: `?WriteAllBuffers@@YAJAEBV?$basic_zstring_view@_W@wil@@AEBV?$vector@U?$pair@QEBE$$CB_K@std@@V?$allocator@U?$pair@QEBE$$CB_K@std@@@2@@std@@_N@Z`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801e3b1c`

## callees

- `0x1800059d0`
- `0x18000c4c4`
- `0x18000d2fc`
- `0x18000dd74`
- `0x180023b20`
- `0x18008b360`
- `0x18008b38c`
- `0x18008b3ec`
- `0x1801df878`
- `0x1801dfc4c`
- `0x1801e0318`
- `0x1801e25fc`
- `0x1801e28a4`
- `0x1801e32fc`
- `0x1801e35e8`

## import_xrefs

- `ntdll!NtClose` at `0x1801e3720`
- `ntdll!NtClose` at `0x1801e389a`
- `ntdll!NtClose` at `0x1801e3975`
- `ntdll!NtClose` at `0x1801e3aab`
- `ntdll!NtClose` at `0x1801e3720`
- `ntdll!NtClose` at `0x1801e389a`
- `ntdll!NtClose` at `0x1801e3975`
- `ntdll!NtClose` at `0x1801e3aab`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801e37f4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801e39ac`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801e37f4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801e39ac`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e36c8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e36c8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801e3785`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801e3785`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e364a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e364a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3808`

## string_xrefs

- `0x1801e3855`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e386c`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e38f7`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e39c0`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e3a57`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e3ad0`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e3a11`: `Failed to set compression on file {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteAllBuffers(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  const WCHAR *v4; // rcx
  DWORD FileAttributesW; // r13d
  LPCWSTR *v6; // rcx
  int v7; // edi
  LPCWSTR *v8; // rcx
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  LPCWSTR *v11; // rax
  int LastError; // edi
  HANDLE v13; // rcx
  _QWORD *v15; // rdi
  _QWORD *v16; // r12
  char *v17; // rbx
  unsigned __int64 v18; // rsi
  __int64 v19; // r15
  DWORD v20; // r14d
  const char *v21; // r9
  signed int v22; // edi
  DWORD v23; // eax
  bool v24; // cc
  HANDLE v25; // rcx
  int v26; // ebx
  const char *v27; // r9
  signed int v28; // eax
  unsigned int v29; // [rsp+28h] [rbp-69h]
  HANDLE Handle; // [rsp+38h] [rbp-59h] BYREF
  unsigned int v31[2]; // [rsp+40h] [rbp-51h] BYREF
  LPCWSTR *v32; // [rsp+48h] [rbp-49h] BYREF
  __int64 v33; // [rsp+50h] [rbp-41h]
  __int64 v34; // [rsp+58h] [rbp-39h]
  char v35[4]; // [rsp+60h] [rbp-31h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+64h] [rbp-2Dh] BYREF
  LPCWSTR lpFileName[2]; // [rsp+68h] [rbp-29h] BYREF
  __int64 v38; // [rsp+78h] [rbp-19h]
  unsigned __int64 v39; // [rsp+80h] [rbp-11h]
  _OWORD FileInformation[2]; // [rsp+88h] [rbp-9h] BYREF
  __int64 v41; // [rsp+A8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v34 = -2;
  v3 = a1;
  *(_QWORD *)v31 = a1;
  Handle = 0;
  GetCanonicalUNCPath(lpFileName, a1);
  v4 = (const WCHAR *)lpFileName;
  if ( v39 > 7 )
    v4 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v4);
  v6 = lpFileName;
  if ( v39 > 7 )
    v6 = (LPCWSTR *)lpFileName[0];
  v32 = v6;
  v33 = v38;
  v7 = (unsigned __int8)FileExists(&v32);
  if ( !*(_QWORD *)(v3 + 8) || *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
  {
    v26 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)0x80004003LL,
      v29);
    std::wstring::~wstring(lpFileName);
  }
  else
  {
    v8 = lpFileName;
    if ( v39 > 7 )
      v8 = (LPCWSTR *)lpFileName[0];
    v32 = v8;
    v33 = v38;
    EnsurePathForFileExists(&v32);
    v9 = (const WCHAR *)lpFileName;
    if ( v39 > 7 )
      v9 = lpFileName[0];
    SetFileAttributesW(v9, 0x80u);
    v11 = lpFileName;
    if ( v39 > 7 )
      v11 = (LPCWSTR *)lpFileName[0];
    v32 = v11;
    v33 = v38;
    LastError = AutoPersistedFile::OpenFile(&Handle, &v32, v10, (unsigned int)(4 * v7 + 1));
    if ( LastError < 0 )
    {
      std::wstring::~wstring(lpFileName);
      v13 = Handle;
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        goto LABEL_15;
      return (unsigned int)LastError;
    }
    v15 = *(_QWORD **)a2;
    v16 = *(_QWORD **)(a2 + 8);
    v17 = (char *)Handle;
    if ( v15 != v16 )
    {
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        v18 = v15[1];
        v19 = 0;
        if ( v18 )
          break;
LABEL_25:
        v15 += 2;
        if ( v15 == v16 )
        {
          v3 = *(_QWORD *)v31;
          goto LABEL_27;
        }
      }
      while ( 1 )
      {
        v20 = v18;
        if ( v18 >= 0xFFFFFFFF )
          v20 = -1;
        if ( !WriteFile(v17, (LPCVOID)(v19 + *v15), v20, &NumberOfBytesWritten, 0) )
          break;
        if ( NumberOfBytesWritten != v20 )
        {
          LastError = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34E,
            (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
            (const char *)0x8000FFFFLL,
            v29);
          goto LABEL_34;
        }
        v19 += v20;
        v18 -= v20;
        if ( !v18 )
          goto LABEL_25;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x34C,
                    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                    v21);
LABEL_34:
      std::wstring::~wstring(lpFileName);
      if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v17) < 0 )
LABEL_16:
        __fastfail(7u);
      return (unsigned int)LastError;
    }
LABEL_27:
    if ( FileAttributesW != -1 )
    {
      memset(FileInformation, 0, sizeof(FileInformation));
      v41 = FileAttributesW;
      if ( !SetFileInformationByHandle(v17, FileBasicInfo, FileInformation, 0x28u) )
      {
        v22 = GetLastError();
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to set original file attributes on file {0}",
            v3);
          if ( v22 > 0 )
            v23 = (unsigned __int16)v22 | 0x80070000;
          else
            v23 = v22;
          NumberOfBytesWritten = v23;
          *(_QWORD *)v31 = &NumberOfBytesWritten;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)v31);
        }
        if ( v22 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x35D,
                        (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                        (const char *)(unsigned int)v22,
                        v29);
LABEL_41:
          std::wstring::~wstring(lpFileName);
          v24 = (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
          goto LABEL_42;
        }
        std::wstring::~wstring(lpFileName);
        if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          return 0;
        v25 = v17;
        goto LABEL_58;
      }
    }
    v26 = AutoPersistedFile::PersistFile((AutoPersistedFile *)&Handle);
    if ( v26 >= 0 )
    {
      v35[0] = 1;
      v17 = (char *)Handle;
      if ( !SetFileInformationByHandle(Handle, FileDispositionInfo, v35, 1u) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x103A,
                      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                      v27);
        if ( LastError < 0 )
          goto LABEL_41;
      }
      v32 = 0;
      v33 = 0;
      v28 = SetFileCompressionState(&v32, v17);
      LastError = v28;
      if ( v28 < 0 )
      {
        NumberOfBytesWritten = v28;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<std::wstring>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to set compression on file {0}",
            lpFileName);
          *(_QWORD *)v31 = &NumberOfBytesWritten;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v31);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x366,
          (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
          (const char *)(unsigned int)LastError,
          v29);
        std::wstring::~wstring(lpFileName);
        v24 = (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_42:
        if ( v24 )
        {
          v13 = v17;
LABEL_15:
          if ( NtClose(v13) < 0 )
            goto LABEL_16;
        }
        return (unsigned int)LastError;
      }
      v26 = AutoPersistedFile::PersistFile((AutoPersistedFile *)&Handle);
      if ( v26 >= 0 )
      {
        std::wstring::~wstring(lpFileName);
        v25 = Handle;
        if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
          return 0;
LABEL_58:
        if ( NtClose(v25) < 0 )
          __fastfail(7u);
        return 0;
      }
    }
    std::wstring::~wstring(lpFileName);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && NtClose(Handle) < 0 )
      __fastfail(7u);
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1801e35e8  mov     rax, rsp
0x1801e35eb  push    rbp
0x1801e35ec  push    rsi
0x1801e35ed  push    rdi
0x1801e35ee  push    r12
0x1801e35f0  push    r13
0x1801e35f2  push    r14
0x1801e35f4  push    r15
0x1801e35f6  lea     rbp, [rax-5Fh]
0x1801e35fa  sub     rsp, 0B0h
0x1801e3601  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x1801e3609  mov     [rax+18h], rbx
0x1801e360d  mov     rax, cs:__security_cookie
0x1801e3614  xor     rax, rsp
0x1801e3617  mov     [rbp+57h+var_38], rax
0x1801e361b  mov     rbx, rdx
0x1801e361e  mov     rsi, rcx
0x1801e3621  mov     qword ptr [rbp+57h+var_A8], rcx
0x1801e3625  xor     r14d, r14d
0x1801e3628  mov     [rbp+57h+Handle], r14
0x1801e362c  mov     rdx, rcx
0x1801e362f  lea     rcx, [rbp+57h+lpFileName]
0x1801e3633  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x1801e3638  nop
0x1801e3639  lea     rcx, [rbp+57h+lpFileName]
0x1801e363d  lea     r15d, [r14+7]
0x1801e3641  cmp     [rbp+57h+var_68], r15
0x1801e3645  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801e364a  call    cs:__imp_GetFileAttributesW
0x1801e3651  nop     dword ptr [rax+rax+00h]
0x1801e3656  mov     r13d, eax
0x1801e3659  mov     rdx, [rbp+57h+var_70]
0x1801e365d  lea     rcx, [rbp+57h+lpFileName]
0x1801e3661  cmp     [rbp+57h+var_68], r15
0x1801e3665  cmova   rcx, [rbp+57h+lpFileName]
0x1801e366a  mov     [rbp+57h+var_A0], rcx
0x1801e366e  mov     [rbp+57h+var_98], rdx
0x1801e3672  lea     rcx, [rbp+57h+var_A0]
0x1801e3676  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x1801e367b  movzx   edi, al
0x1801e367e  cmp     [rsi+8], r14
0x1801e3682  jz      loc_1801E3AC4
0x1801e3688  mov     rcx, [rbx+8]
0x1801e368c  cmp     [rbx], rcx
0x1801e368f  jz      loc_1801E3AC4
0x1801e3695  mov     rdx, [rbp+57h+var_70]
0x1801e3699  lea     rcx, [rbp+57h+lpFileName]
0x1801e369d  cmp     [rbp+57h+var_68], r15
0x1801e36a1  cmova   rcx, [rbp+57h+lpFileName]
0x1801e36a6  mov     [rbp+57h+var_A0], rcx
0x1801e36aa  mov     [rbp+57h+var_98], rdx
0x1801e36ae  lea     rcx, [rbp+57h+var_A0]
0x1801e36b2  call    ?EnsurePathForFileExists@@YAXAEBV?$basic_zstring_view@_W@wil@@@Z; EnsurePathForFileExists(wil::basic_zstring_view<wchar_t> const &)
0x1801e36b7  lea     rcx, [rbp+57h+lpFileName]
0x1801e36bb  cmp     [rbp+57h+var_68], r15
0x1801e36bf  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801e36c4  lea     edx, [r15+79h]; dwFileAttributes
0x1801e36c8  call    cs:__imp_SetFileAttributesW
0x1801e36cf  nop     dword ptr [rax+rax+00h]
0x1801e36d4  lea     r9d, ds:1[rdi*4]
0x1801e36dc  mov     rcx, [rbp+57h+var_70]
0x1801e36e0  lea     rax, [rbp+57h+lpFileName]
0x1801e36e4  cmp     [rbp+57h+var_68], r15
0x1801e36e8  cmova   rax, [rbp+57h+lpFileName]
0x1801e36ed  mov     [rbp+57h+var_A0], rax
0x1801e36f1  mov     [rbp+57h+var_98], rcx
0x1801e36f5  lea     rdx, [rbp+57h+var_A0]
0x1801e36f9  lea     rcx, [rbp+57h+Handle]
0x1801e36fd  call    ?OpenFile@AutoPersistedFile@@QEAAJAEBV?$basic_zstring_view@_W@wil@@KK@Z; AutoPersistedFile::OpenFile(wil::basic_zstring_view<wchar_t> const &,ulong,ulong)
0x1801e3702  mov     edi, eax
0x1801e3704  test    eax, eax
0x1801e3706  jns     short loc_1801E373C
0x1801e3708  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e370c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e3711  nop
0x1801e3712  mov     rcx, [rbp+57h+Handle]; Handle
0x1801e3716  lea     rdx, [rcx-1]
0x1801e371a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801e371e  ja      short loc_1801E3735
0x1801e3720  call    cs:__imp_NtClose
0x1801e3727  nop     dword ptr [rax+rax+00h]
0x1801e372c  test    eax, eax
0x1801e372e  jns     short loc_1801E3735
0x1801e3730  mov     rcx, r15
0x1801e3733  int     29h; Win8: RtlFailFast(ecx)
0x1801e3735  mov     eax, edi
0x1801e3737  jmp     loc_1801E3AEE
0x1801e373c  mov     rdi, [rbx]
0x1801e373f  mov     r12, [rbx+8]
0x1801e3743  mov     eax, 0FFFFFFFFh
0x1801e3748  mov     rbx, [rbp+57h+Handle]
0x1801e374c  cmp     rdi, r12
0x1801e374f  jz      short loc_1801E37C9
0x1801e3751  mov     [rbp+57h+NumberOfBytesWritten], r14d
0x1801e3755  mov     rsi, [rdi+8]
0x1801e3759  mov     r15, r14
0x1801e375c  test    rsi, rsi
0x1801e375f  jz      short loc_1801E37B6
0x1801e3761  cmp     rsi, rax
0x1801e3764  mov     r14d, esi
0x1801e3767  jb      short loc_1801E376C
0x1801e3769  mov     r14d, eax
0x1801e376c  mov     rdx, [rdi]
0x1801e376f  add     rdx, r15; lpBuffer
0x1801e3772  mov     qword ptr [rsp+20h], 0; int
0x1801e377b  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801e377f  mov     r8d, r14d; nNumberOfBytesToWrite
0x1801e3782  mov     rcx, rbx; hFile
0x1801e3785  call    cs:__imp_WriteFile
0x1801e378c  nop     dword ptr [rax+rax+00h]
0x1801e3791  test    eax, eax
0x1801e3793  jz      loc_1801E3868
0x1801e3799  cmp     [rbp+57h+NumberOfBytesWritten], r14d
0x1801e379d  jnz     loc_1801E3849
0x1801e37a3  mov     eax, r14d
0x1801e37a6  add     r15, rax
0x1801e37a9  xor     r14d, r14d
0x1801e37ac  sub     rsi, rax
0x1801e37af  mov     eax, 0FFFFFFFFh
0x1801e37b4  jnz     short loc_1801E3761
0x1801e37b6  add     rdi, 10h
0x1801e37ba  cmp     rdi, r12
0x1801e37bd  jnz     short loc_1801E3751
0x1801e37bf  mov     rsi, qword ptr [rbp+57h+var_A8]
0x1801e37c3  mov     r15d, 7
0x1801e37c9  cmp     r13d, eax
0x1801e37cc  jz      loc_1801E394A
0x1801e37d2  xorps   xmm0, xmm0
0x1801e37d5  xor     eax, eax
0x1801e37d7  movups  [rbp+57h+FileInformation], xmm0
0x1801e37db  movups  [rbp+57h+var_50], xmm0
0x1801e37df  mov     [rbp+57h+var_40], rax
0x1801e37e3  mov     dword ptr [rbp+57h+var_40], r13d
0x1801e37e7  lea     r9d, [rax+28h]; dwBufferSize
0x1801e37eb  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1801e37ef  xor     edx, edx; FileInformationClass
0x1801e37f1  mov     rcx, rbx; hFile
0x1801e37f4  call    cs:__imp_SetFileInformationByHandle
0x1801e37fb  nop     dword ptr [rax+rax+00h]
0x1801e3800  test    eax, eax
0x1801e3802  jnz     loc_1801E394A
0x1801e3808  call    cs:__imp_GetLastError
0x1801e380f  nop     dword ptr [rax+rax+00h]
0x1801e3814  mov     edi, eax
0x1801e3816  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801e381d  test    rcx, rcx
0x1801e3820  jz      loc_1801E38EC
0x1801e3826  mov     [rsp+20h], rsi
0x1801e382b  lea     r9, aFailedToSetOri; "Failed to set original file attributes "...
0x1801e3832  mov     esi, 3
0x1801e3837  mov     r8d, esi
0x1801e383a  xor     edx, edx
0x1801e383c  call    ??$LogNumObjects@V?$basic_zstring_view@_W@wil@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_zstring_view@_W@wil@@@Z; LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(bool,LogAdapter::LogLevel,char const * const,wil::basic_zstring_view<wchar_t> const &)
0x1801e3841  test    edi, edi
0x1801e3843  jg      short loc_1801E38B8
0x1801e3845  mov     eax, edi
0x1801e3847  jmp     short loc_1801E38C0
0x1801e3849  mov     rcx, [rbp+5Fh]; this
0x1801e384d  mov     edi, 8000FFFFh
0x1801e3852  mov     r9d, edi; char *
0x1801e3855  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e385c  mov     edx, 34Eh; void *
0x1801e3861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3866  jmp     short loc_1801E387F
0x1801e3868  mov     rcx, [rbp+5Fh]; this
0x1801e386c  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e3873  mov     edx, 34Ch; void *
0x1801e3878  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e387d  mov     edi, eax
0x1801e387f  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e3883  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e3888  nop
0x1801e3889  lea     rcx, [rbx-1]
0x1801e388d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801e3891  ja      loc_1801E3735
0x1801e3897  mov     rcx, rbx; Handle
0x1801e389a  call    cs:__imp_NtClose
0x1801e38a1  nop     dword ptr [rax+rax+00h]
0x1801e38a6  test    eax, eax
0x1801e38a8  jns     loc_1801E3735
0x1801e38ae  mov     ecx, 7
0x1801e38b3  jmp     loc_1801E3733
0x1801e38b8  movzx   eax, di
0x1801e38bb  or      eax, 80070000h
0x1801e38c0  mov     [rbp+57h+NumberOfBytesWritten], eax
0x1801e38c3  lea     rax, [rbp+57h+NumberOfBytesWritten]
0x1801e38c7  mov     qword ptr [rbp+57h+var_A8], rax
0x1801e38cb  lea     rax, [rbp+57h+var_A8]
0x1801e38cf  mov     [rsp+20h], rax; unsigned int
0x1801e38d4  lea     r9, a0; ": {0}"
0x1801e38db  mov     r8d, esi
0x1801e38de  mov     dl, 1
0x1801e38e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801e38e7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801e38ec  test    edi, edi
0x1801e38ee  jz      short loc_1801E392A
0x1801e38f0  mov     rcx, [rbp+5Fh]; this
0x1801e38f4  mov     r9d, edi; char *
0x1801e38f7  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e38fe  mov     edx, 35Dh; void *
0x1801e3903  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e3908  mov     edi, eax
0x1801e390a  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e390e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e3913  nop
0x1801e3914  lea     rcx, [rbx-1]
0x1801e3918  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801e391c  ja      loc_1801E3735
0x1801e3922  mov     rcx, rbx
0x1801e3925  jmp     loc_1801E3720
0x1801e392a  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e392e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e3933  nop
0x1801e3934  lea     rax, [rbx-1]
0x1801e3938  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e393c  ja      loc_1801E3AC0
0x1801e3942  mov     rcx, rbx
0x1801e3945  jmp     loc_1801E3AAB
0x1801e394a  lea     rcx, [rbp+57h+Handle]; this
0x1801e394e  call    ?PersistFile@AutoPersistedFile@@QEAAJXZ; AutoPersistedFile::PersistFile(void)
0x1801e3953  mov     ebx, eax
0x1801e3955  test    eax, eax
0x1801e3957  jns     short loc_1801E3993
0x1801e3959  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e395d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e3962  nop
0x1801e3963  mov     rcx, [rbp+57h+Handle]; Handle
0x1801e3967  lea     rdx, [rcx-1]
0x1801e396b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801e396f  ja      loc_1801E3AEC
0x1801e3975  call    cs:__imp_NtClose
0x1801e397c  nop     dword ptr [rax+rax+00h]
0x1801e3981  test    eax, eax
0x1801e3983  jns     loc_1801E3AEC
0x1801e3989  mov     rcx, r15
0x1801e398c  int     29h; Win8: RtlFailFast(ecx)
0x1801e398e  jmp     loc_1801E3AEC
0x1801e3993  mov     [rbp+57h+var_88], 1
0x1801e3997  mov     r9d, 1; dwBufferSize
0x1801e399d  lea     r8, [rbp+57h+var_88]; lpFileInformation
0x1801e39a1  lea     edx, [r9+3]; FileInformationClass
0x1801e39a5  mov     rbx, [rbp+57h+Handle]
0x1801e39a9  mov     rcx, rbx; hFile
0x1801e39ac  call    cs:__imp_SetFileInformationByHandle
0x1801e39b3  nop     dword ptr [rax+rax+00h]
0x1801e39b8  test    eax, eax
0x1801e39ba  jnz     short loc_1801E39DB
0x1801e39bc  mov     rcx, [rbp+5Fh]; this
0x1801e39c0  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e39c7  mov     edx, 103Ah; void *
0x1801e39cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e39d1  mov     edi, eax
0x1801e39d3  test    eax, eax
0x1801e39d5  js      loc_1801E390A
0x1801e39db  mov     [rbp+57h+var_A0], r14
0x1801e39df  mov     [rbp+57h+var_98], r14
0x1801e39e3  mov     rdx, rbx
0x1801e39e6  lea     rcx, [rbp+57h+var_A0]
0x1801e39ea  call    ?SetFileCompressionState@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAX_N@Z; SetFileCompressionState(wil::basic_zstring_view<wchar_t> const &,void *,bool)
0x1801e39ef  mov     edi, eax
0x1801e39f1  test    eax, eax
0x1801e39f3  jns     loc_1801E3A80
0x1801e39f9  mov     [rbp+57h+NumberOfBytesWritten], eax
0x1801e39fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801e3a03  test    rcx, rcx
0x1801e3a06  jz      short loc_1801E3A50
0x1801e3a08  lea     rax, [rbp+57h+lpFileName]
0x1801e3a0c  mov     [rsp+20h], rax
0x1801e3a11  lea     r9, aFailedToSetCom; "Failed to set compression on file {0}"
0x1801e3a18  mov     esi, 3
0x1801e3a1d  mov     r8d, esi
0x1801e3a20  xor     edx, edx
0x1801e3a22  call    ??$LogNumObjects@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::Logger::LogNumObjects<std::wstring>(bool,LogAdapter::LogLevel,char const * const,std::wstring const &)
0x1801e3a27  lea     rax, [rbp+57h+NumberOfBytesWritten]
0x1801e3a2b  mov     qword ptr [rbp+57h+var_A8], rax
0x1801e3a2f  lea     rax, [rbp+57h+var_A8]
0x1801e3a33  mov     [rsp+20h], rax; int
0x1801e3a38  lea     r9, asc_1802C6678; ": {}"
0x1801e3a3f  mov     r8d, esi
0x1801e3a42  mov     dl, 1
0x1801e3a44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801e3a4b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801e3a50  mov     rcx, [rbp+5Fh]; this
0x1801e3a54  mov     r9d, edi; char *
0x1801e3a57  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e3a5e  mov     edx, 366h; void *
0x1801e3a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3a68  nop
0x1801e3a69  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e3a6d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e3a72  nop
0x1801e3a73  lea     rax, [rbx-1]
0x1801e3a77  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e3a7b  jmp     loc_1801E391C
0x1801e3a80  lea     rcx, [rbp+57h+Handle]; this
0x1801e3a84  call    ?PersistFile@AutoPersistedFile@@QEAAJXZ; AutoPersistedFile::PersistFile(void)
0x1801e3a89  mov     ebx, eax
0x1801e3a8b  lea     rcx, [rbp+57h+lpFileName]; void *
0x1801e3a8f  test    eax, eax
0x1801e3a91  js      loc_1801E395D
  ... truncated ...
```
