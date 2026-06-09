# WriteDumpThread(void *)

- ea: `0x18000e090`
- end: `0x18000e56b`
- name: `?WriteDumpThread@@YAKPEAX@Z`
- size: `1243`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ad1c`
- `0x18000ad90`
- `0x18000debc`
- `0x18000e000`
- `0x18000e090`
- `0x18000e6fc`
- `0x18001280a`
- `0x180012830`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000e276`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000e276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e476`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e52c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e52c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e4a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e4a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e27c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e4a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e27c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e4a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e3c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e3c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e40b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e40b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e511`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e511`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e181`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e225`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e225`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e1d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e1d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e467`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e467`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e2dd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e2dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e51f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e51f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000e293`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000e293`

## string_xrefs

- `0x18000e256`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x18000e4f8`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x18000e232`: `The memory dump location specified in the registry is invalid`
- `0x18000e24c`: `WriteDumpThread`
- `0x18000e4ee`: `WriteDumpThread`
- `0x18000e2f9`: `GetFullPathNameW failed`
- `0x18000e36f`: `StringCchPrintf failed. Unable to compose file name.`
- `0x18000e3a8`: `StringCchPrintf failed. Unable to compose dump location.`
- `0x18000e3bd`: `DBGHELP.DLL`
- `0x18000e3e6`: `LoadLibraryExW(DbgHelp.dll) failed.`
- `0x18000e401`: `MiniDumpWriteDump`
- `0x18000e42b`: `GetProcAddress(MiniDumpWriteDump) failed`
- `0x18000e488`: `Failed to create dump file.`
- `0x18000e4d4`: `MiniDumpWriteDump failed`

## pseudocode

```c
__int64 __fastcall WriteDumpThread(PVOID Parameter)
{
  __int64 FileW; // rsi
  unsigned int v2; // edx
  unsigned int LocalDTCProfileInt; // r15d
  const wchar_t *v4; // rax
  __int64 v5; // r9
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v8; // eax
  HMODULE Library; // rax
  HMODULE v10; // rdi
  signed int v11; // eax
  FARPROC ProcAddress; // r14
  signed int v13; // eax
  signed int v14; // eax
  DWORD CurrentProcessId; // ebx
  HANDLE v16; // rax
  unsigned __int16 *v17; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  DWORD dwSize; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR FilePart; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[526]; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int16 v29; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v30[526]; // [rsp+292h] [rbp+192h] BYREF
  WCHAR ExeName; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v32[526]; // [rsp+4A2h] [rbp+3A2h] BYREF
  WCHAR Buffer; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE v34[526]; // [rsp+6B2h] [rbp+5B2h] BYREF

  *(_WORD *)Data = 0;
  memset_0(v28, 0, 0x206u);
  v29 = 0;
  FileW = -1;
  memset_0(v30, 0, 0x206u);
  FilePart = 0;
  Buffer = 0;
  SystemTime = 0;
  memset_0(v34, 0, 0x208u);
  ExeName = 0;
  memset_0(v32, 0, 0x208u);
  dwSize = 261;
  LocalDTCProfileInt = GetLocalDTCProfileInt("MemoryDumpType", v2);
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey) )
  {
    StringCchCopyW((unsigned __int16 *)Data, 0x104u, &qword_180017E58);
  }
  else
  {
    cbData = 518;
    if ( RegQueryValueExW(hKey, L"MemoryDumpLocation", 0, &Type, Data, &cbData) )
      StringCchCopyW((unsigned __int16 *)Data, 0x104u, &qword_180017E58);
    else
      *(_WORD *)&Data[2 * ((unsigned __int64)cbData >> 1)] = 0;
    if ( Type != 1 )
      StringCchCopyW((unsigned __int16 *)Data, 0x104u, &qword_180017E58);
    RegCloseKey(hKey);
  }
  if ( !*(_WORD *)Data )
  {
    v4 = L"The memory dump location specified in the registry is invalid";
    v5 = 1112;
LABEL_11:
    TraceStringInline(7, 1, L"com\\complus\\dtc\\shared\\util\\dtcini.cpp", v5, L"WriteDumpThread", -2147467259, v4);
LABEL_40:
    CloseHandle((HANDLE)FileW);
    goto LABEL_41;
  }
  GetLocalTime(&SystemTime);
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, &ExeName, &dwSize) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1125,
      L"WriteDumpThread",
      LastError,
      L"QueryFullProcessImageNameW failed");
    goto LABEL_40;
  }
  if ( !GetFullPathNameW(&ExeName, 0x105u, &Buffer, &FilePart) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1137,
      L"WriteDumpThread",
      v8,
      L"GetFullPathNameW failed");
    goto LABEL_40;
  }
  LODWORD(lpcbData) = SystemTime.wDay;
  LODWORD(phkResult) = SystemTime.wMonth;
  if ( (int)StringCchPrintfW(
              &v29,
              0x104u,
              L"%s_%02ld%02ld%04ld_%02ld%02ld%02ld",
              FilePart,
              phkResult,
              lpcbData,
              SystemTime.wYear,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond) < 0 )
  {
    v4 = L"StringCchPrintf failed. Unable to compose file name.";
    v5 = 1154;
    goto LABEL_11;
  }
  if ( (int)StringCchPrintfW((unsigned __int16 *)Data, 0x104u, L"%s\\%s.dmp", Data, &v29) < 0 )
  {
    v4 = L"StringCchPrintf failed. Unable to compose dump location.";
    v5 = 1164;
    goto LABEL_11;
  }
  Library = LoadLibraryExW(L"DBGHELP.DLL", 0, 0);
  v10 = Library;
  if ( !Library )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1172,
      L"WriteDumpThread",
      v11,
      L"LoadLibraryExW(DbgHelp.dll) failed.");
    goto LABEL_40;
  }
  ProcAddress = GetProcAddress(Library, "MiniDumpWriteDump");
  if ( ProcAddress )
  {
    FileW = (__int64)CreateFileW((LPCWSTR)Data, 0xC0000000, 1u, 0, 1u, 0x80u, 0);
    if ( FileW == -1 )
    {
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
        1209,
        L"WriteDumpThread",
        v14,
        L"Failed to create dump file.");
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      v16 = GetCurrentProcess();
      if ( !((unsigned int (__fastcall *)(HANDLE, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
              v16,
              CurrentProcessId,
              FileW,
              LocalDTCProfileInt,
              0,
              0,
              0) )
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
          1220,
          L"WriteDumpThread",
          -2147467259,
          L"MiniDumpWriteDump failed");
    }
  }
  else
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1195,
      L"WriteDumpThread",
      v13,
      L"GetProcAddress(MiniDumpWriteDump) failed");
  }
  FreeLibrary(v10);
  if ( FileW )
    goto LABEL_40;
LABEL_41:
  if ( !SetEvent(g_writeDumpEventSem) )
    UtsemWin32Error(L"SetEvent fails in CEventSem::Set()", v17, 0x7Au);
  return 0;
}

```

## disassembly

```asm
0x18000e090  push    rbp
0x18000e092  push    rbx
0x18000e093  push    rsi
0x18000e094  push    rdi
0x18000e095  push    r12
0x18000e097  push    r13
0x18000e099  push    r14
0x18000e09b  push    r15
0x18000e09d  lea     rbp, [rsp-7D8h]
0x18000e0a5  sub     rsp, 8D8h
0x18000e0ac  mov     rax, cs:__security_cookie
0x18000e0b3  xor     rax, rsp
0x18000e0b6  mov     [rbp+810h+var_50], rax
0x18000e0bd  mov     edi, 206h
0x18000e0c2  lea     rcx, [rbp+810h+var_88E]; void *
0x18000e0c6  xor     r12d, r12d
0x18000e0c9  mov     r8d, edi; Size
0x18000e0cc  xor     edx, edx; Val
0x18000e0ce  mov     word ptr [rbp+810h+Data], r12w
0x18000e0d3  call    memset_0
0x18000e0d8  mov     r8d, edi; Size
0x18000e0db  mov     [rbp+810h+var_680], r12w
0x18000e0e3  xor     edx, edx; Val
0x18000e0e5  lea     rcx, [rbp+810h+var_67E]; void *
0x18000e0ec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e0f0  call    memset_0
0x18000e0f5  xorps   xmm0, xmm0
0x18000e0f8  mov     [rsp+910h+FilePart], r12
0x18000e0fd  lea     ebx, [rdi+2]
0x18000e100  mov     [rbp+810h+Buffer], r12w
0x18000e108  mov     r8d, ebx; Size
0x18000e10b  lea     rcx, [rbp+810h+var_25E]; void *
0x18000e112  xor     edx, edx; Val
0x18000e114  movups  xmmword ptr [rsp+910h+SystemTime.wYear], xmm0
0x18000e119  call    memset_0
0x18000e11e  mov     r8d, ebx; Size
0x18000e121  mov     [rbp+810h+ExeName], r12w
0x18000e129  xor     edx, edx; Val
0x18000e12b  lea     rcx, [rbp+810h+var_46E]; void *
0x18000e132  call    memset_0
0x18000e137  mov     r14d, 105h
0x18000e13d  lea     rcx, aMemorydumptype; "MemoryDumpType"
0x18000e144  mov     [rsp+910h+dwSize], r14d
0x18000e149  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x18000e14e  mov     r15d, eax
0x18000e151  mov     [rsp+910h+hKey], r12
0x18000e156  lea     rax, [rsp+910h+hKey]
0x18000e15b  mov     [rsp+910h+Type], r12d
0x18000e160  mov     r9d, 20119h; samDesired
0x18000e166  mov     [rsp+910h+phkResult], rax; phkResult
0x18000e16b  xor     r8d, r8d; ulOptions
0x18000e16e  mov     [rsp+910h+cbData], r12d
0x18000e173  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MSDTC"
0x18000e17a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e181  call    cs:__imp_RegOpenKeyExW
0x18000e187  lea     r13d, [r12+1]
0x18000e18c  test    eax, eax
0x18000e18e  jz      short loc_18000E1AB
0x18000e190  lea     ebx, [r14-1]
0x18000e194  mov     edx, ebx; unsigned __int64
0x18000e196  lea     r8, qword_180017E58; unsigned __int16 *
0x18000e19d  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x18000e1a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e1a6  jmp     loc_18000E22B
0x18000e1ab  mov     rcx, [rsp+910h+hKey]; hKey
0x18000e1b0  lea     rax, [rsp+910h+cbData]
0x18000e1b5  mov     [rsp+910h+lpcbData], rax; lpcbData
0x18000e1ba  lea     r9, [rsp+910h+Type]; lpType
0x18000e1bf  lea     rax, [rbp+810h+Data]
0x18000e1c3  mov     [rsp+910h+cbData], edi
0x18000e1c7  xor     r8d, r8d; lpReserved
0x18000e1ca  mov     [rsp+910h+phkResult], rax; lpData
0x18000e1cf  lea     rdx, aMemorydumploca; "MemoryDumpLocation"
0x18000e1d6  call    cs:__imp_RegQueryValueExW
0x18000e1dc  mov     ebx, 104h
0x18000e1e1  test    eax, eax
0x18000e1e3  jz      short loc_18000E1F9
0x18000e1e5  lea     r8, qword_180017E58; unsigned __int16 *
0x18000e1ec  mov     edx, ebx; unsigned __int64
0x18000e1ee  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x18000e1f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e1f7  jmp     short loc_18000E206
0x18000e1f9  mov     ecx, [rsp+910h+cbData]
0x18000e1fd  shr     rcx, 1
0x18000e200  mov     word ptr [rbp+rcx*2+810h+Data], r12w
0x18000e206  cmp     [rsp+910h+Type], r13d
0x18000e20b  jz      short loc_18000E220
0x18000e20d  lea     r8, qword_180017E58; unsigned __int16 *
0x18000e214  mov     rdx, rbx; unsigned __int64
0x18000e217  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x18000e21b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e220  mov     rcx, [rsp+910h+hKey]; hKey
0x18000e225  call    cs:__imp_RegCloseKey
0x18000e22b  cmp     word ptr [rbp+810h+Data], r12w
0x18000e230  jnz     short loc_18000E271
0x18000e232  lea     rax, aTheMemoryDumpL; "The memory dump location specified in t"...
0x18000e239  mov     r9d, 458h
0x18000e23f  mov     [rsp+910h+hTemplateFile], rax
0x18000e244  mov     dword ptr [rsp+910h+lpcbData], 80004005h
0x18000e24c  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x18000e253  mov     edx, r13d
0x18000e256  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x18000e25d  mov     [rsp+910h+phkResult], rax
0x18000e262  mov     ecx, 7
0x18000e267  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000e26c  jmp     loc_18000E51C
0x18000e271  lea     rcx, [rsp+910h+SystemTime]; lpSystemTime
0x18000e276  call    cs:__imp_GetLocalTime
0x18000e27c  call    cs:__imp_GetCurrentProcess
0x18000e282  lea     r9, [rsp+910h+dwSize]; lpdwSize
0x18000e287  xor     edx, edx; dwFlags
0x18000e289  mov     rcx, rax; hProcess
0x18000e28c  lea     r8, [rbp+810h+ExeName]; lpExeName
0x18000e293  call    cs:__imp_QueryFullProcessImageNameW
0x18000e299  test    eax, eax
0x18000e29b  jnz     short loc_18000E2C7
0x18000e29d  call    cs:__imp_GetLastError
0x18000e2a3  test    eax, eax
0x18000e2a5  jle     short loc_18000E2AF
0x18000e2a7  movzx   eax, ax
0x18000e2aa  or      eax, 80070000h
0x18000e2af  lea     rcx, aQueryfullproce; "QueryFullProcessImageNameW failed"
0x18000e2b6  mov     r9d, 465h
0x18000e2bc  mov     [rsp+910h+hTemplateFile], rcx
0x18000e2c1  mov     dword ptr [rsp+910h+lpcbData], eax
0x18000e2c5  jmp     short loc_18000E24C
0x18000e2c7  lea     r9, [rsp+910h+FilePart]; lpFilePart
0x18000e2cc  mov     edx, r14d; nBufferLength
0x18000e2cf  lea     r8, [rbp+810h+Buffer]; lpBuffer
0x18000e2d6  lea     rcx, [rbp+810h+ExeName]; lpFileName
0x18000e2dd  call    cs:__imp_GetFullPathNameW
0x18000e2e3  test    eax, eax
0x18000e2e5  jnz     short loc_18000E314
0x18000e2e7  call    cs:__imp_GetLastError
0x18000e2ed  test    eax, eax
0x18000e2ef  jle     short loc_18000E2F9
0x18000e2f1  movzx   eax, ax
0x18000e2f4  or      eax, 80070000h
0x18000e2f9  lea     rcx, aGetfullpathnam_0; "GetFullPathNameW failed"
0x18000e300  mov     r9d, 471h
0x18000e306  mov     [rsp+910h+hTemplateFile], rcx
0x18000e30b  mov     dword ptr [rsp+910h+lpcbData], eax
0x18000e30f  jmp     loc_18000E24C
0x18000e314  movzx   ecx, [rsp+910h+SystemTime.wMinute]
0x18000e319  movzx   edx, [rsp+910h+SystemTime.wHour]
0x18000e31e  movzx   r8d, [rsp+910h+SystemTime.wYear]
0x18000e324  movzx   r9d, [rsp+910h+SystemTime.wDay]
0x18000e32a  movzx   eax, [rsp+910h+SystemTime.wSecond]
0x18000e32f  movzx   r10d, [rsp+910h+SystemTime.wMonth]
0x18000e335  mov     [rsp+910h+var_8C8], eax
0x18000e339  mov     [rsp+910h+var_8D0], ecx
0x18000e33d  lea     rcx, [rbp+810h+var_680]; unsigned __int16 *
0x18000e344  mov     [rsp+910h+var_8D8], edx
0x18000e348  mov     rdx, rbx; unsigned __int64
0x18000e34b  mov     dword ptr [rsp+910h+hTemplateFile], r8d
0x18000e350  lea     r8, aS02ld02ld04ld0; "%s_%02ld%02ld%04ld_%02ld%02ld%02ld"
0x18000e357  mov     dword ptr [rsp+910h+lpcbData], r9d
0x18000e35c  mov     r9, [rsp+910h+FilePart]
0x18000e361  mov     dword ptr [rsp+910h+phkResult], r10d
0x18000e366  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e36b  test    eax, eax
0x18000e36d  jns     short loc_18000E381
0x18000e36f  lea     rax, aStringcchprint_0; "StringCchPrintf failed. Unable to compo"...
0x18000e376  mov     r9d, 482h
0x18000e37c  jmp     loc_18000E23F
0x18000e381  lea     rax, [rbp+810h+var_680]
0x18000e388  mov     rdx, rbx; unsigned __int64
0x18000e38b  lea     r9, [rbp+810h+Data]
0x18000e38f  mov     [rsp+910h+phkResult], rax
0x18000e394  lea     r8, aSSDmp; "%s\\%s.dmp"
0x18000e39b  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x18000e39f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e3a4  test    eax, eax
0x18000e3a6  jns     short loc_18000E3BA
0x18000e3a8  lea     rax, aStringcchprint; "StringCchPrintf failed. Unable to compo"...
0x18000e3af  mov     r9d, 48Ch
0x18000e3b5  jmp     loc_18000E23F
0x18000e3ba  xor     r8d, r8d; dwFlags
0x18000e3bd  lea     rcx, LibFileName; "DBGHELP.DLL"
0x18000e3c4  xor     edx, edx; hFile
0x18000e3c6  call    cs:__imp_LoadLibraryExW
0x18000e3cc  mov     rdi, rax
0x18000e3cf  test    rax, rax
0x18000e3d2  jnz     short loc_18000E401
0x18000e3d4  call    cs:__imp_GetLastError
0x18000e3da  test    eax, eax
0x18000e3dc  jle     short loc_18000E3E6
0x18000e3de  movzx   eax, ax
0x18000e3e1  or      eax, 80070000h
0x18000e3e6  lea     rcx, aLoadlibraryexw; "LoadLibraryExW(DbgHelp.dll) failed."
0x18000e3ed  mov     r9d, 494h
0x18000e3f3  mov     [rsp+910h+hTemplateFile], rcx
0x18000e3f8  mov     dword ptr [rsp+910h+lpcbData], eax
0x18000e3fc  jmp     loc_18000E24C
0x18000e401  lea     rdx, ProcName; "MiniDumpWriteDump"
0x18000e408  mov     rcx, rdi; hModule
0x18000e40b  call    cs:__imp_GetProcAddress
0x18000e411  mov     r14, rax
0x18000e414  test    rax, rax
0x18000e417  jnz     short loc_18000E446
0x18000e419  call    cs:__imp_GetLastError
0x18000e41f  test    eax, eax
0x18000e421  jle     short loc_18000E42B
0x18000e423  movzx   eax, ax
0x18000e426  or      eax, 80070000h
0x18000e42b  lea     rcx, aGetprocaddress; "GetProcAddress(MiniDumpWriteDump) faile"...
0x18000e432  mov     r9d, 4ABh
0x18000e438  mov     [rsp+910h+hTemplateFile], rcx
0x18000e43d  mov     dword ptr [rsp+910h+lpcbData], eax
0x18000e441  jmp     loc_18000E4EE
0x18000e446  mov     [rsp+910h+hTemplateFile], r12; hTemplateFile
0x18000e44b  lea     rcx, [rbp+810h+Data]; lpFileName
0x18000e44f  mov     dword ptr [rsp+910h+lpcbData], 80h; dwFlagsAndAttributes
0x18000e457  xor     r9d, r9d; lpSecurityAttributes
0x18000e45a  mov     r8d, r13d; dwShareMode
0x18000e45d  mov     dword ptr [rsp+910h+phkResult], r13d; dwCreationDisposition
0x18000e462  mov     edx, 0C0000000h; dwDesiredAccess
0x18000e467  call    cs:__imp_CreateFileW
0x18000e46d  mov     rsi, rax
0x18000e470  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e474  jnz     short loc_18000E4A0
0x18000e476  call    cs:__imp_GetLastError
0x18000e47c  test    eax, eax
0x18000e47e  jle     short loc_18000E488
0x18000e480  movzx   eax, ax
0x18000e483  or      eax, 80070000h
0x18000e488  lea     rcx, aFailedToCreate; "Failed to create dump file."
0x18000e48f  mov     r9d, 4B9h
0x18000e495  mov     [rsp+910h+hTemplateFile], rcx
0x18000e49a  mov     dword ptr [rsp+910h+lpcbData], eax
0x18000e49e  jmp     short loc_18000E4EE
0x18000e4a0  call    cs:__imp_GetCurrentProcessId
0x18000e4a6  mov     ebx, eax
0x18000e4a8  call    cs:__imp_GetCurrentProcess
0x18000e4ae  mov     [rsp+910h+hTemplateFile], r12
0x18000e4b3  mov     r9d, r15d
0x18000e4b6  mov     rcx, rax
0x18000e4b9  mov     [rsp+910h+lpcbData], r12
0x18000e4be  mov     rax, r14
0x18000e4c1  mov     [rsp+910h+phkResult], r12
0x18000e4c6  mov     r8, rsi
0x18000e4c9  mov     edx, ebx
0x18000e4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d0  test    eax, eax
0x18000e4d2  jnz     short loc_18000E50E
0x18000e4d4  lea     rax, aMinidumpwrited; "MiniDumpWriteDump failed"
0x18000e4db  mov     r9d, 4C4h
0x18000e4e1  mov     [rsp+910h+hTemplateFile], rax
0x18000e4e6  mov     dword ptr [rsp+910h+lpcbData], 80004005h
0x18000e4ee  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x18000e4f5  mov     edx, r13d
0x18000e4f8  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x18000e4ff  mov     [rsp+910h+phkResult], rax
0x18000e504  mov     ecx, 7
0x18000e509  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000e50e  mov     rcx, rdi; hLibModule
0x18000e511  call    cs:__imp_FreeLibrary
0x18000e517  test    rsi, rsi
0x18000e51a  jz      short loc_18000E525
0x18000e51c  mov     rcx, rsi; hObject
0x18000e51f  call    cs:__imp_CloseHandle
0x18000e525  mov     rcx, cs:?g_writeDumpEventSem@@3VCEventSem@@A; hEvent
0x18000e52c  call    cs:__imp_SetEvent
0x18000e532  test    eax, eax
0x18000e534  jnz     short loc_18000E546
0x18000e536  lea     r8d, [rax+7Ah]; unsigned int
0x18000e53a  lea     rcx, aSeteventFailsI; "SetEvent fails in CEventSem::Set()"
0x18000e541  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x18000e546  xor     eax, eax
0x18000e548  mov     rcx, [rbp+810h+var_50]
0x18000e54f  xor     rcx, rsp; StackCookie
0x18000e552  call    __security_check_cookie
0x18000e557  add     rsp, 8D8h
0x18000e55e  pop     r15
0x18000e560  pop     r14
0x18000e562  pop     r13
0x18000e564  pop     r12
0x18000e566  pop     rdi
0x18000e567  pop     rsi
0x18000e568  pop     rbx
0x18000e569  pop     rbp
0x18000e56a  retn
```
