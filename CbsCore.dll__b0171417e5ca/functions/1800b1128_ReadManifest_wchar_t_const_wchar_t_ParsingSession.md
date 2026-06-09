# ReadManifest(wchar_t const *,wchar_t * *,ParsingSession *)

- ea: `0x1800b1128`
- end: `0x1800b1627`
- name: `?ReadManifest@@YAJPEB_WPEAPEA_WPEAUParsingSession@@@Z`
- size: `1279`
- prototype: `int(const wchar_t *, wchar_t **, struct ParsingSession *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18012a0c8`
- `0x180193e68`

## callees

- `0x180013250`
- `0x180033d50`
- `0x18004f454`
- `0x180073d94`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800b1128`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801026fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b11d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b141f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b11d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b141f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1564`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b13a2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b140f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b13a2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b140f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b12e0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b12e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b1194`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b1194`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b11c5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b11c5`

## string_xrefs

- `0x1800b132b`: `Failed to read from file: {}`
- `0x1800b1594`: `Failed to open package file: {}`
- `0x1800b11fa`: `Failed to get size of package manifest: {}`

## pseudocode

```c
__int64 __fastcall ReadManifest(const wchar_t *a1, wchar_t **a2, struct ParsingSession *a3)
{
  HANDLE FileW; // rax
  HANDLE v6; // r14
  signed int LastError; // ebx
  DWORD v8; // eax
  __int64 v9; // rdx
  union _LARGE_INTEGER v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const CHAR *v13; // rbx
  union _LARGE_INTEGER v14; // rdi
  DWORD v15; // r8d
  unsigned int v16; // eax
  int v17; // r14d
  int v18; // eax
  unsigned int v19; // esi
  WCHAR *v20; // rsi
  unsigned int v21; // eax
  int v22; // eax
  unsigned int v24; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-49h]
  unsigned int v27[2]; // [rsp+40h] [rbp-29h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-21h] BYREF
  LPWSTR lpWideCharStr; // [rsp+50h] [rbp-19h] BYREF
  LPCCH lpMultiByteStr; // [rsp+58h] [rbp-11h] BYREF
  const wchar_t *v31; // [rsp+60h] [rbp-9h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-1h] BYREF
  DWORD *p_NumberOfBytesRead; // [rsp+70h] [rbp+7h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v31 = a1;
  FileSize.QuadPart = 0;
  lpMultiByteStr = 0;
  lpWideCharStr = 0;
  hFile = (HANDLE)-1LL;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  v6 = hFile;
  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to open package file: {}",
          (__int64)&v31);
        if ( LastError > 0 )
          v24 = (unsigned __int16)LastError | 0x80070000;
        else
          v24 = LastError;
        LODWORD(p_NumberOfBytesRead) = v24;
        *(_QWORD *)v27 = &p_NumberOfBytesRead;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v27);
      }
      if ( LastError )
      {
        v9 = 422;
        goto LABEL_54;
      }
LABEL_44:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpWideCharStr);
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpMultiByteStr);
      return 0;
    }
    v11 = -2147024894;
  }
  else
  {
    if ( !GetFileSizeEx(hFile, &FileSize) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get size of package manifest: {}",
          (__int64)&v31);
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        else
          v8 = LastError;
        NumberOfBytesRead = v8;
        p_NumberOfBytesRead = &NumberOfBytesRead;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&p_NumberOfBytesRead);
      }
      if ( LastError )
      {
        v9 = 425;
LABEL_54:
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v9,
                (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                (const char *)(unsigned int)LastError,
                dwCreationDisposition);
        goto LABEL_55;
      }
      goto LABEL_44;
    }
    v10 = FileSize;
    if ( Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(
           &lpMultiByteStr,
           FileSize.QuadPart + 2) )
    {
      v13 = lpMultiByteStr;
      v14.QuadPart = 0;
      memset_0((void *)lpMultiByteStr, 0, v10.QuadPart + 2);
      while ( v14.QuadPart < (unsigned __int64)v10.QuadPart )
      {
        if ( v10.QuadPart - v14.QuadPart <= 0xFFFFFFFFuLL )
          v15 = v10.LowPart - v14.LowPart;
        else
          v15 = -1;
        NumberOfBytesRead = v15;
        if ( !ReadFile(v6, (LPVOID)&v13[v14.QuadPart], v15, &NumberOfBytesRead, 0) )
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to read from file: {}",
              (__int64)&v31);
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
            else
              v16 = LastError;
            LODWORD(p_NumberOfBytesRead) = v16;
            *(_QWORD *)v27 = &p_NumberOfBytesRead;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)v27);
          }
          if ( LastError )
          {
            v9 = 451;
            goto LABEL_54;
          }
          v11 = 0;
          goto LABEL_55;
        }
        if ( !NumberOfBytesRead )
          break;
        v14.QuadPart += NumberOfBytesRead;
      }
      v17 = MultiByteToWideChar(0xFDE9u, 0, v13, v14.LowPart, 0, 0) + 1;
      v18 = SczAlloc(&lpWideCharStr, v17);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D0,
          (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
          (const char *)(unsigned int)v18,
          dwCreationDispositiona);
        v11 = v19;
        goto LABEL_55;
      }
      v20 = lpWideCharStr;
      memset_0(lpWideCharStr, 0, 2LL * v17);
      if ( !MultiByteToWideChar(0xFDE9u, 0, v13, v14.LowPart, v20, v17) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert MultiByte to WideChar.");
          if ( LastError > 0 )
            v21 = (unsigned __int16)LastError | 0x80070000;
          else
            v21 = LastError;
          LODWORD(p_NumberOfBytesRead) = v21;
          *(_QWORD *)v27 = &p_NumberOfBytesRead;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v27);
        }
        if ( LastError )
        {
          v9 = 476;
          goto LABEL_54;
        }
        goto LABEL_44;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        -1);
      v22 = ParseCbsPackageFromBuffer(v20, a3);
      v11 = v22;
      if ( v22 >= 0 )
      {
        lpWideCharStr = 0;
        *a2 = v20;
        goto LABEL_44;
      }
      LODWORD(p_NumberOfBytesRead) = v22;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to parse cbs package.");
        *(_QWORD *)v27 = &p_NumberOfBytesRead;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v27);
      }
      v12 = 483;
    }
    else
    {
      v11 = -2147024882;
      v12 = 429;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
      (const char *)v11,
      dwCreationDisposition);
  }
LABEL_55:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpWideCharStr);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpMultiByteStr);
  return v11;
}

```

## disassembly

```asm
0x1800b1128  mov     [rsp-8+arg_18], rbx
0x1800b112d  push    rbp
0x1800b112e  push    rsi
0x1800b112f  push    rdi
0x1800b1130  push    r12
0x1800b1132  push    r13
0x1800b1134  push    r14
0x1800b1136  push    r15
0x1800b1138  lea     rbp, [rsp-27h]
0x1800b113d  sub     rsp, 90h
0x1800b1144  mov     rax, cs:__security_cookie
0x1800b114b  xor     rax, rsp
0x1800b114e  mov     [rbp+57h+var_40], rax
0x1800b1152  xor     r15d, r15d
0x1800b1155  mov     [rbp+57h+var_60], rcx
0x1800b1159  mov     r13, r8
0x1800b115c  mov     [rsp+0C0h+hTemplateFile], r15; hTemplateFile
0x1800b1161  mov     r12, rdx
0x1800b1164  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b116c  xor     r9d, r9d; lpSecurityAttributes
0x1800b116f  mov     qword ptr [rbp+57h+FileSize], r15
0x1800b1173  lea     edi, [r15+3]
0x1800b1177  mov     [rbp+57h+lpMultiByteStr], r15
0x1800b117b  mov     edx, 80000000h; dwDesiredAccess
0x1800b1180  mov     [rsp+0C0h+dwCreationDisposition], edi; int
0x1800b1184  lea     r8d, [r15+1]; dwShareMode
0x1800b1188  mov     [rbp+57h+lpWideCharStr], r15
0x1800b118c  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1800b1194  call    cs:__imp_CreateFileW
0x1800b119b  nop     dword ptr [rax+rax+00h]
0x1800b11a0  mov     rdx, rax
0x1800b11a3  lea     rcx, [rbp+57h+hFile]
0x1800b11a7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b11ac  mov     r14, [rbp+57h+hFile]
0x1800b11b0  lea     rax, [r14-1]
0x1800b11b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b11b8  ja      loc_1800B1564
0x1800b11be  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1800b11c2  mov     rcx, r14; hFile
0x1800b11c5  call    cs:__imp_GetFileSizeEx
0x1800b11cc  nop     dword ptr [rax+rax+00h]
0x1800b11d1  test    eax, eax
0x1800b11d3  jnz     loc_1800B125B
0x1800b11d9  call    cs:__imp_GetLastError
0x1800b11e0  nop     dword ptr [rax+rax+00h]
0x1800b11e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b11ec  mov     ebx, eax
0x1800b11ee  test    rcx, rcx
0x1800b11f1  jz      short loc_1800B1249
0x1800b11f3  lea     rax, [rbp+57h+var_60]
0x1800b11f7  mov     r8d, edi
0x1800b11fa  lea     r9, aFailedToGetSiz; "Failed to get size of package manifest:"...
0x1800b1201  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b1206  xor     edx, edx
0x1800b1208  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b120d  test    ebx, ebx
0x1800b120f  jg      short loc_1800B1215
0x1800b1211  mov     eax, ebx
0x1800b1213  jmp     short loc_1800B121D
0x1800b1215  movzx   eax, bx
0x1800b1218  or      eax, 80070000h
0x1800b121d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1224  lea     r9, a0; ": {0}"
0x1800b122b  mov     [rbp+57h+NumberOfBytesRead], eax
0x1800b122e  mov     r8d, edi
0x1800b1231  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1800b1235  mov     dl, 1
0x1800b1237  mov     [rbp+57h+var_50], rax
0x1800b123b  lea     rax, [rbp+57h+var_50]
0x1800b123f  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b1244  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b1249  test    ebx, ebx
0x1800b124b  jz      loc_1800B151F
0x1800b1251  mov     edx, 1A9h
0x1800b1256  jmp     loc_1800B15F0
0x1800b125b  mov     rsi, qword ptr [rbp+57h+FileSize]
0x1800b125f  lea     rcx, [rbp+57h+lpMultiByteStr]
0x1800b1263  lea     rdx, [rsi+2]
0x1800b1267  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x1800b126c  test    rax, rax
0x1800b126f  jnz     short loc_1800B1293
0x1800b1271  mov     ebx, 8007000Eh
0x1800b1276  mov     edx, 1ADh; void *
0x1800b127b  mov     rcx, [rbp+5Fh]; this
0x1800b127f  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b1286  mov     r9d, ebx; char *
0x1800b1289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b128e  jmp     loc_1800B1605
0x1800b1293  mov     rbx, [rbp+57h+lpMultiByteStr]
0x1800b1297  lea     r8, [rsi+2]; Size
0x1800b129b  mov     rcx, rbx; void *
0x1800b129e  xor     edx, edx; Val
0x1800b12a0  mov     rdi, r15
0x1800b12a3  call    memset_0
0x1800b12a8  mov     ecx, 0FFFFFFFFh
0x1800b12ad  cmp     rdi, rsi
0x1800b12b0  jnb     loc_1800B138B
0x1800b12b6  mov     rax, rsi
0x1800b12b9  sub     rax, rdi
0x1800b12bc  cmp     rax, rcx
0x1800b12bf  jbe     short loc_1800B12C6
0x1800b12c1  mov     r8d, ecx
0x1800b12c4  jmp     short loc_1800B12CC
0x1800b12c6  mov     r8d, esi
0x1800b12c9  sub     r8d, edi; nNumberOfBytesToRead
0x1800b12cc  lea     rdx, [rdi+rbx]; lpBuffer
0x1800b12d0  mov     [rbp+57h+NumberOfBytesRead], r8d
0x1800b12d4  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b12d8  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r15; lpOverlapped
0x1800b12dd  mov     rcx, r14; hFile
0x1800b12e0  call    cs:__imp_ReadFile
0x1800b12e7  nop     dword ptr [rax+rax+00h]
0x1800b12ec  test    eax, eax
0x1800b12ee  jz      short loc_1800B1300
0x1800b12f0  mov     eax, [rbp+57h+NumberOfBytesRead]
0x1800b12f3  test    eax, eax
0x1800b12f5  jz      loc_1800B138B
0x1800b12fb  add     rdi, rax
0x1800b12fe  jmp     short loc_1800B12A8
0x1800b1300  call    cs:__imp_GetLastError
0x1800b1307  nop     dword ptr [rax+rax+00h]
0x1800b130c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1313  mov     ebx, eax
0x1800b1315  test    rcx, rcx
0x1800b1318  jz      short loc_1800B1375
0x1800b131a  lea     rax, [rbp+57h+var_60]
0x1800b131e  mov     edi, 3
0x1800b1323  mov     r8d, edi
0x1800b1326  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b132b  lea     r9, aFailedToReadFr_0; "Failed to read from file: {}"
0x1800b1332  xor     edx, edx
0x1800b1334  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b1339  test    ebx, ebx
0x1800b133b  jg      short loc_1800B1341
0x1800b133d  mov     eax, ebx
0x1800b133f  jmp     short loc_1800B1349
0x1800b1341  movzx   eax, bx
0x1800b1344  or      eax, 80070000h
0x1800b1349  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1350  lea     r9, a0; ": {0}"
0x1800b1357  mov     dword ptr [rbp+57h+var_50], eax
0x1800b135a  mov     r8d, edi
0x1800b135d  lea     rax, [rbp+57h+var_50]
0x1800b1361  mov     dl, 1
0x1800b1363  mov     qword ptr [rbp+57h+var_80], rax
0x1800b1367  lea     rax, [rbp+57h+var_80]
0x1800b136b  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b1370  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b1375  test    ebx, ebx
0x1800b1377  jz      short loc_1800B1383
0x1800b1379  mov     edx, 1C3h
0x1800b137e  jmp     loc_1800B15F0
0x1800b1383  mov     ebx, r15d
0x1800b1386  jmp     loc_1800B1605
0x1800b138b  mov     [rsp+0C0h+dwFlagsAndAttributes], r15d; cchWideChar
0x1800b1390  mov     r9d, edi; cbMultiByte
0x1800b1393  mov     r8, rbx; lpMultiByteStr
0x1800b1396  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r15; int
0x1800b139b  xor     edx, edx; dwFlags
0x1800b139d  mov     ecx, 0FDE9h; CodePage
0x1800b13a2  call    cs:__imp_MultiByteToWideChar
0x1800b13a9  nop     dword ptr [rax+rax+00h]
0x1800b13ae  lea     rcx, [rbp+57h+lpWideCharStr]
0x1800b13b2  lea     r14d, [rax+1]
0x1800b13b6  movsxd  r15, r14d
0x1800b13b9  mov     rdx, r15
0x1800b13bc  call    SczAlloc
0x1800b13c1  mov     esi, eax
0x1800b13c3  test    eax, eax
0x1800b13c5  jns     short loc_1800B13E6
0x1800b13c7  mov     rcx, [rbp+5Fh]; this
0x1800b13cb  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b13d2  mov     r9d, eax; char *
0x1800b13d5  mov     edx, 1D0h; void *
0x1800b13da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b13df  mov     ebx, esi
0x1800b13e1  jmp     loc_1800B1605
0x1800b13e6  mov     rsi, [rbp+57h+lpWideCharStr]
0x1800b13ea  lea     r8, [r15+r15]; Size
0x1800b13ee  mov     rcx, rsi; void *
0x1800b13f1  xor     edx, edx; Val
0x1800b13f3  call    memset_0
0x1800b13f8  mov     r9d, edi; cbMultiByte
0x1800b13fb  mov     [rsp+0C0h+dwFlagsAndAttributes], r14d; cchWideChar
0x1800b1400  mov     r8, rbx; lpMultiByteStr
0x1800b1403  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi; lpWideCharStr
0x1800b1408  xor     edx, edx; dwFlags
0x1800b140a  mov     ecx, 0FDE9h; CodePage
0x1800b140f  call    cs:__imp_MultiByteToWideChar
0x1800b1416  nop     dword ptr [rax+rax+00h]
0x1800b141b  test    eax, eax
0x1800b141d  jnz     short loc_1800B149D
0x1800b141f  call    cs:__imp_GetLastError
0x1800b1426  nop     dword ptr [rax+rax+00h]
0x1800b142b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1432  mov     ebx, eax
0x1800b1434  test    rcx, rcx
0x1800b1437  jz      short loc_1800B148B
0x1800b1439  mov     edi, 3
0x1800b143e  lea     r9, aFailedToConver_21; "Failed to convert MultiByte to WideChar"...
0x1800b1445  mov     r8d, edi
0x1800b1448  xor     edx, edx
0x1800b144a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b144f  test    ebx, ebx
0x1800b1451  jg      short loc_1800B1457
0x1800b1453  mov     eax, ebx
0x1800b1455  jmp     short loc_1800B145F
0x1800b1457  movzx   eax, bx
0x1800b145a  or      eax, 80070000h
0x1800b145f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1466  lea     r9, a0; ": {0}"
0x1800b146d  mov     dword ptr [rbp+57h+var_50], eax
0x1800b1470  mov     r8d, edi
0x1800b1473  lea     rax, [rbp+57h+var_50]
0x1800b1477  mov     dl, 1
0x1800b1479  mov     qword ptr [rbp+57h+var_80], rax
0x1800b147d  lea     rax, [rbp+57h+var_80]
0x1800b1481  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b1486  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b148b  test    ebx, ebx
0x1800b148d  jz      loc_1800B151F
0x1800b1493  mov     edx, 1DCh
0x1800b1498  jmp     loc_1800B15F0
0x1800b149d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b14a1  lea     rcx, [rbp+57h+hFile]
0x1800b14a5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b14aa  mov     rdx, r13; struct ParsingSession *
0x1800b14ad  mov     rcx, rsi; lpWideCharStr
0x1800b14b0  call    ?ParseCbsPackageFromBuffer@@YAJPEB_WPEAUParsingSession@@@Z; ParseCbsPackageFromBuffer(wchar_t const *,ParsingSession *)
0x1800b14b5  mov     ebx, eax
0x1800b14b7  test    eax, eax
0x1800b14b9  jns     short loc_1800B1513
0x1800b14bb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b14c2  mov     dword ptr [rbp+57h+var_50], eax
0x1800b14c5  test    rcx, rcx
0x1800b14c8  jz      short loc_1800B1509
0x1800b14ca  mov     edi, 3
0x1800b14cf  lea     r9, aFailedToParseC_2; "Failed to parse cbs package."
0x1800b14d6  mov     r8d, edi
0x1800b14d9  xor     edx, edx
0x1800b14db  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b14e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b14e7  lea     rax, [rbp+57h+var_50]
0x1800b14eb  mov     qword ptr [rbp+57h+var_80], rax
0x1800b14ef  lea     r9, asc_1802EE7AC; ": {}"
0x1800b14f6  lea     rax, [rbp+57h+var_80]
0x1800b14fa  mov     r8d, edi
0x1800b14fd  mov     dl, 1
0x1800b14ff  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b1504  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b1509  mov     edx, 1E3h
0x1800b150e  jmp     loc_1800B127B
0x1800b1513  mov     [rbp+57h+lpWideCharStr], 0
0x1800b151b  mov     [r12], rsi
0x1800b151f  lea     rcx, [rbp+57h+hFile]
0x1800b1523  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b1528  lea     rcx, [rbp+57h+lpWideCharStr]
0x1800b152c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b1531  lea     rcx, [rbp+57h+lpMultiByteStr]
0x1800b1535  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x1800b153a  xor     eax, eax
0x1800b153c  mov     rcx, [rbp+57h+var_40]
0x1800b1540  xor     rcx, rsp; StackCookie
0x1800b1543  call    __security_check_cookie
0x1800b1548  mov     rbx, [rsp+0C0h+arg_18]
0x1800b1550  add     rsp, 90h
0x1800b1557  pop     r15
0x1800b1559  pop     r14
0x1800b155b  pop     r13
0x1800b155d  pop     r12
0x1800b155f  pop     rdi
0x1800b1560  pop     rsi
0x1800b1561  pop     rbp
0x1800b1562  retn
0x1800b1564  call    cs:__imp_GetLastError
0x1800b156b  nop     dword ptr [rax+rax+00h]
0x1800b1570  mov     ebx, eax
0x1800b1572  cmp     eax, 2
0x1800b1575  jnz     short loc_1800B1581
0x1800b1577  mov     ebx, 80070002h
0x1800b157c  jmp     loc_1800B1605
0x1800b1581  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1588  test    rcx, rcx
0x1800b158b  jz      short loc_1800B15E3
0x1800b158d  lea     rax, [rbp+57h+var_60]
0x1800b1591  mov     r8d, edi
0x1800b1594  lea     r9, aFailedToOpenPa_6; "Failed to open package file: {}"
0x1800b159b  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800b15a0  xor     edx, edx
0x1800b15a2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b15a7  test    ebx, ebx
0x1800b15a9  jg      short loc_1800B15AF
0x1800b15ab  mov     eax, ebx
0x1800b15ad  jmp     short loc_1800B15B7
0x1800b15af  movzx   eax, bx
0x1800b15b2  or      eax, 80070000h
0x1800b15b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b15be  lea     r9, a0; ": {0}"
0x1800b15c5  mov     dword ptr [rbp+57h+var_50], eax
0x1800b15c8  mov     r8d, edi
  ... truncated ...
```
