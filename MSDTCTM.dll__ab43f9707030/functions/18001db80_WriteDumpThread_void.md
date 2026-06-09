# WriteDumpThread(void *)

- ea: `0x18001db80`
- end: `0x18001dfa8`
- name: `?WriteDumpThread@@YAKPEAX@Z`
- size: `1064`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800063b0`
- `0x180008a50`
- `0x18000f370`
- `0x18001db80`
- `0x180084af8`
- `0x180088948`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001dc9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001dc9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ded5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ded5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001dca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001dedd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001dca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001dedd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001df6d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001df6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ddf2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ddf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001df52`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001df52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001df60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001df60`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001dd03`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001dd03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001de9c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001de9c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001dcba`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001dcba`

## string_xrefs

- `0x18001dc78`: `WriteDumpThread`
- `0x18001df34`: `WriteDumpThread`
- `0x18001dc7f`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x18001df3b`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x18001debd`: `Failed to create dump file.`
- `0x18001de57`: `GetProcAddress(MiniDumpWriteDump) failed`
- `0x18001de12`: `LoadLibraryExW(DbgHelp.dll) failed.`
- `0x18001dd1f`: `GetFullPathNameW failed`
- `0x18001dc59`: `The memory dump location specified in the registry is invalid`
- `0x18001dd99`: `StringCchPrintf failed. Unable to compose file name.`
- `0x18001ddd4`: `StringCchPrintf failed. Unable to compose dump location.`
- `0x18001dde9`: `DBGHELP.DLL`
- `0x18001de2d`: `MiniDumpWriteDump`
- `0x18001df15`: `MiniDumpWriteDump failed`

## pseudocode

```c
__int64 __fastcall WriteDumpThread(PVOID Parameter)
{
  __int64 v1; // rdi
  unsigned int LocalDTCProfileInt; // r15d
  const unsigned __int16 *v3; // rcx
  unsigned int v4; // r8d
  unsigned __int16 *v5; // r9
  const wchar_t *v6; // rax
  __int64 v7; // r9
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v10; // eax
  HMODULE Library; // rax
  HMODULE v12; // rsi
  signed int v13; // eax
  FARPROC ProcAddress; // r14
  signed int v15; // eax
  signed int v16; // eax
  DWORD CurrentProcessId; // ebx
  HANDLE v18; // rax
  unsigned __int16 *v19; // rdx
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesb[2]; // [rsp+28h] [rbp-D8h]
  __int64 dwSize; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[526]; // [rsp+72h] [rbp-8Eh] BYREF
  unsigned __int16 v29; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v30[526]; // [rsp+282h] [rbp+182h] BYREF
  WCHAR ExeName; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v32[526]; // [rsp+492h] [rbp+392h] BYREF
  WCHAR Buffer; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v34[526]; // [rsp+6A2h] [rbp+5A2h] BYREF

  FileName = 0;
  memset_0(v28, 0, 0x206u);
  v29 = 0;
  v1 = -1;
  memset_0(v30, 0, 0x206u);
  FilePart = 0;
  Buffer = 0;
  SystemTime = 0;
  memset_0(v34, 0, 0x208u);
  ExeName = 0;
  memset_0(v32, 0, 0x208u);
  LODWORD(dwSize) = 261;
  LocalDTCProfileInt = GetLocalDTCProfileInt("MemoryDumpType", 0);
  GetLocalDTCProfileStrW(v3, &FileName, v4, v5);
  if ( !FileName )
  {
    v6 = L"The memory dump location specified in the registry is invalid";
    v7 = 1112;
LABEL_3:
    dwFlagsAndAttributes[0] = -2147467259;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      v7,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      v6);
LABEL_32:
    CloseHandle((HANDLE)v1);
    goto LABEL_33;
  }
  GetLocalTime(&SystemTime);
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, &ExeName, (PDWORD)&dwSize) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    dwFlagsAndAttributes[0] = LastError;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1125,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"QueryFullProcessImageNameW failed");
    goto LABEL_32;
  }
  if ( !GetFullPathNameW(&ExeName, 0x105u, &Buffer, &FilePart) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    dwFlagsAndAttributes[0] = v10;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1137,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"GetFullPathNameW failed");
    goto LABEL_32;
  }
  if ( (int)StringCchPrintfW(
              &v29,
              0x104u,
              L"%s_%02ld%02ld%04ld_%02ld%02ld%02ld",
              FilePart,
              SystemTime.wMonth,
              SystemTime.wDay,
              SystemTime.wYear,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              dwSize) < 0 )
  {
    v6 = L"StringCchPrintf failed. Unable to compose file name.";
    v7 = 1154;
    goto LABEL_3;
  }
  if ( (int)StringCchPrintfW(&FileName, 0x104u, L"%s\\%s.dmp", &FileName, &v29) < 0 )
  {
    v6 = L"StringCchPrintf failed. Unable to compose dump location.";
    v7 = 1164;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(L"DBGHELP.DLL", 0, 0);
  v12 = Library;
  if ( !Library )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    dwFlagsAndAttributes[0] = v13;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1172,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"LoadLibraryExW(DbgHelp.dll) failed.");
    goto LABEL_32;
  }
  ProcAddress = GetProcAddress(Library, "MiniDumpWriteDump");
  if ( ProcAddress )
  {
    v1 = (__int64)CreateFileW(&FileName, 0xC0000000, 1u, 0, 1u, 0x80u, 0);
    if ( v1 == -1 )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      dwFlagsAndAttributesa[0] = v16;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
        1209,
        L"WriteDumpThread",
        *(_QWORD *)dwFlagsAndAttributesa,
        L"Failed to create dump file.");
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      v18 = GetCurrentProcess();
      if ( !((unsigned int (__fastcall *)(HANDLE, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
              v18,
              CurrentProcessId,
              v1,
              LocalDTCProfileInt,
              0,
              0,
              0) )
      {
        dwFlagsAndAttributesb[0] = -2147467259;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
          1220,
          L"WriteDumpThread",
          *(_QWORD *)dwFlagsAndAttributesb,
          L"MiniDumpWriteDump failed");
      }
    }
  }
  else
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    dwFlagsAndAttributes[0] = v15;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1195,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"GetProcAddress(MiniDumpWriteDump) failed");
  }
  FreeLibrary(v12);
  if ( v1 )
    goto LABEL_32;
LABEL_33:
  if ( !SetEvent(g_writeDumpEventSem) )
    UtsemWin32Error(L"SetEvent fails in CEventSem::Set()", v19, 0x7Au);
  return 0;
}

```

## disassembly

```asm
0x18001db80  push    rbp
0x18001db82  push    rbx
0x18001db83  push    rsi
0x18001db84  push    rdi
0x18001db85  push    r14
0x18001db87  push    r15
0x18001db89  lea     rbp, [rsp-7C8h]
0x18001db91  sub     rsp, 8C8h
0x18001db98  mov     rax, cs:__security_cookie
0x18001db9f  xor     rax, rsp
0x18001dba2  mov     [rbp+7F0h+var_40], rax
0x18001dba9  xor     eax, eax
0x18001dbab  lea     rcx, [rsp+8F0h+var_87E]; void *
0x18001dbb0  mov     ebx, 206h
0x18001dbb5  mov     [rsp+8F0h+FileName], ax
0x18001dbba  mov     r8d, ebx; Size
0x18001dbbd  xor     edx, edx; Val
0x18001dbbf  call    memset_0
0x18001dbc4  xor     eax, eax
0x18001dbc6  lea     rcx, [rbp+7F0h+var_66E]; void *
0x18001dbcd  mov     r8d, ebx; Size
0x18001dbd0  mov     [rbp+7F0h+var_670], ax
0x18001dbd7  xor     edx, edx; Val
0x18001dbd9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001dbdd  call    memset_0
0x18001dbe2  xorps   xmm0, xmm0
0x18001dbe5  mov     [rsp+8F0h+FilePart], 0
0x18001dbee  xor     eax, eax
0x18001dbf0  lea     rcx, [rbp+7F0h+var_24E]; void *
0x18001dbf7  mov     ebx, 208h
0x18001dbfc  mov     [rbp+7F0h+Buffer], ax
0x18001dc03  mov     r8d, ebx; Size
0x18001dc06  xor     edx, edx; Val
0x18001dc08  movups  xmmword ptr [rsp+8F0h+SystemTime.wYear], xmm0
0x18001dc0d  call    memset_0
0x18001dc12  xor     eax, eax
0x18001dc14  lea     rcx, [rbp+7F0h+var_45E]; void *
0x18001dc1b  mov     r8d, ebx; Size
0x18001dc1e  mov     [rbp+7F0h+ExeName], ax
0x18001dc25  xor     edx, edx; Val
0x18001dc27  call    memset_0
0x18001dc2c  mov     ebx, 105h
0x18001dc31  lea     rcx, aMemorydumptype; "MemoryDumpType"
0x18001dc38  xor     edx, edx; unsigned int
0x18001dc3a  mov     dword ptr [rsp+8F0h+dwSize], ebx
0x18001dc3e  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x18001dc43  lea     rdx, [rsp+8F0h+FileName]; unsigned __int16 *
0x18001dc48  mov     r15d, eax
0x18001dc4b  call    ?GetLocalDTCProfileStrW@@YAXPEBGPEAGK1@Z; GetLocalDTCProfileStrW(ushort const *,ushort *,ulong,ushort *)
0x18001dc50  xor     eax, eax
0x18001dc52  cmp     [rsp+8F0h+FileName], ax
0x18001dc57  jnz     short loc_18001DC98
0x18001dc59  lea     rax, aTheMemoryDumpL; "The memory dump location specified in t"...
0x18001dc60  mov     r9d, 458h
0x18001dc66  mov     [rsp+8F0h+hTemplateFile], rax
0x18001dc6b  mov     [rsp+8F0h+dwFlagsAndAttributes], 80004005h
0x18001dc73  mov     edx, 1
0x18001dc78  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x18001dc7f  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x18001dc86  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax
0x18001dc8b  lea     ecx, [rdx+6]
0x18001dc8e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001dc93  jmp     loc_18001DF5D
0x18001dc98  lea     rcx, [rsp+8F0h+SystemTime]; lpSystemTime
0x18001dc9d  call    cs:__imp_GetLocalTime
0x18001dca3  call    cs:__imp_GetCurrentProcess
0x18001dca9  lea     r9, [rsp+8F0h+dwSize]; lpdwSize
0x18001dcae  xor     edx, edx; dwFlags
0x18001dcb0  mov     rcx, rax; hProcess
0x18001dcb3  lea     r8, [rbp+7F0h+ExeName]; lpExeName
0x18001dcba  call    cs:__imp_QueryFullProcessImageNameW
0x18001dcc0  test    eax, eax
0x18001dcc2  jnz     short loc_18001DCEE
0x18001dcc4  call    cs:__imp_GetLastError
0x18001dcca  test    eax, eax
0x18001dccc  jle     short loc_18001DCD6
0x18001dcce  movzx   eax, ax
0x18001dcd1  or      eax, 80070000h
0x18001dcd6  lea     rcx, aQueryfullproce; "QueryFullProcessImageNameW failed"
0x18001dcdd  mov     r9d, 465h
0x18001dce3  mov     [rsp+8F0h+hTemplateFile], rcx
0x18001dce8  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x18001dcec  jmp     short loc_18001DC73
0x18001dcee  lea     r9, [rsp+8F0h+FilePart]; lpFilePart
0x18001dcf3  mov     edx, ebx; nBufferLength
0x18001dcf5  lea     r8, [rbp+7F0h+Buffer]; lpBuffer
0x18001dcfc  lea     rcx, [rbp+7F0h+ExeName]; lpFileName
0x18001dd03  call    cs:__imp_GetFullPathNameW
0x18001dd09  test    eax, eax
0x18001dd0b  jnz     short loc_18001DD3A
0x18001dd0d  call    cs:__imp_GetLastError
0x18001dd13  test    eax, eax
0x18001dd15  jle     short loc_18001DD1F
0x18001dd17  movzx   eax, ax
0x18001dd1a  or      eax, 80070000h
0x18001dd1f  lea     rcx, aGetfullpathnam_0; "GetFullPathNameW failed"
0x18001dd26  mov     r9d, 471h
0x18001dd2c  mov     [rsp+8F0h+hTemplateFile], rcx
0x18001dd31  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x18001dd35  jmp     loc_18001DC73
0x18001dd3a  movzx   ecx, [rsp+8F0h+SystemTime.wMinute]
0x18001dd3f  mov     ebx, 104h
0x18001dd44  movzx   edx, [rsp+8F0h+SystemTime.wHour]
0x18001dd49  movzx   r8d, [rsp+8F0h+SystemTime.wYear]
0x18001dd4f  movzx   r9d, [rsp+8F0h+SystemTime.wDay]
0x18001dd55  movzx   eax, [rsp+8F0h+SystemTime.wSecond]
0x18001dd5a  movzx   r10d, [rsp+8F0h+SystemTime.wMonth]
0x18001dd60  mov     [rsp+8F0h+var_8A8], eax
0x18001dd64  mov     [rsp+8F0h+var_8B0], ecx
0x18001dd68  lea     rcx, [rbp+7F0h+var_670]; unsigned __int16 *
0x18001dd6f  mov     [rsp+8F0h+var_8B8], edx
0x18001dd73  mov     edx, ebx; unsigned __int64
0x18001dd75  mov     dword ptr [rsp+8F0h+hTemplateFile], r8d
0x18001dd7a  lea     r8, aS02ld02ld04ld0; "%s_%02ld%02ld%04ld_%02ld%02ld%02ld"
0x18001dd81  mov     [rsp+8F0h+dwFlagsAndAttributes], r9d
0x18001dd86  mov     r9, [rsp+8F0h+FilePart]
0x18001dd8b  mov     [rsp+8F0h+dwCreationDisposition], r10d
0x18001dd90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dd95  test    eax, eax
0x18001dd97  jns     short loc_18001DDAB
0x18001dd99  lea     rax, aStringcchprint_3; "StringCchPrintf failed. Unable to compo"...
0x18001dda0  mov     r9d, 482h
0x18001dda6  jmp     loc_18001DC66
0x18001ddab  lea     rax, [rbp+7F0h+var_670]
0x18001ddb2  mov     rdx, rbx; unsigned __int64
0x18001ddb5  lea     r9, [rsp+8F0h+FileName]
0x18001ddba  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax
0x18001ddbf  lea     r8, aSSDmp; "%s\\%s.dmp"
0x18001ddc6  lea     rcx, [rsp+8F0h+FileName]; unsigned __int16 *
0x18001ddcb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ddd0  test    eax, eax
0x18001ddd2  jns     short loc_18001DDE6
0x18001ddd4  lea     rax, aStringcchprint_0; "StringCchPrintf failed. Unable to compo"...
0x18001dddb  mov     r9d, 48Ch
0x18001dde1  jmp     loc_18001DC66
0x18001dde6  xor     r8d, r8d; dwFlags
0x18001dde9  lea     rcx, aDbghelpDll; "DBGHELP.DLL"
0x18001ddf0  xor     edx, edx; hFile
0x18001ddf2  call    cs:__imp_LoadLibraryExW
0x18001ddf8  mov     rsi, rax
0x18001ddfb  test    rax, rax
0x18001ddfe  jnz     short loc_18001DE2D
0x18001de00  call    cs:__imp_GetLastError
0x18001de06  test    eax, eax
0x18001de08  jle     short loc_18001DE12
0x18001de0a  movzx   eax, ax
0x18001de0d  or      eax, 80070000h
0x18001de12  lea     rcx, aLoadlibraryexw; "LoadLibraryExW(DbgHelp.dll) failed."
0x18001de19  mov     r9d, 494h
0x18001de1f  mov     [rsp+8F0h+hTemplateFile], rcx
0x18001de24  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x18001de28  jmp     loc_18001DC73
0x18001de2d  lea     rdx, aMinidumpwrited_0; "MiniDumpWriteDump"
0x18001de34  mov     rcx, rsi; hModule
0x18001de37  call    cs:__imp_GetProcAddress
0x18001de3d  mov     r14, rax
0x18001de40  test    rax, rax
0x18001de43  jnz     short loc_18001DE72
0x18001de45  call    cs:__imp_GetLastError
0x18001de4b  test    eax, eax
0x18001de4d  jle     short loc_18001DE57
0x18001de4f  movzx   eax, ax
0x18001de52  or      eax, 80070000h
0x18001de57  lea     rcx, aGetprocaddress; "GetProcAddress(MiniDumpWriteDump) faile"...
0x18001de5e  mov     r9d, 4ABh
0x18001de64  mov     [rsp+8F0h+hTemplateFile], rcx
0x18001de69  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x18001de6d  jmp     loc_18001DF2F
0x18001de72  xor     r9d, r9d; lpSecurityAttributes
0x18001de75  mov     [rsp+8F0h+hTemplateFile], 0; hTemplateFile
0x18001de7e  mov     [rsp+8F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001de86  lea     rcx, [rsp+8F0h+FileName]; lpFileName
0x18001de8b  mov     edx, 0C0000000h; dwDesiredAccess
0x18001de90  mov     [rsp+8F0h+dwCreationDisposition], 1; dwCreationDisposition
0x18001de98  lea     r8d, [r9+1]; dwShareMode
0x18001de9c  call    cs:__imp_CreateFileW
0x18001dea2  mov     rdi, rax
0x18001dea5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001dea9  jnz     short loc_18001DED5
0x18001deab  call    cs:__imp_GetLastError
0x18001deb1  test    eax, eax
0x18001deb3  jle     short loc_18001DEBD
0x18001deb5  movzx   eax, ax
0x18001deb8  or      eax, 80070000h
0x18001debd  lea     rcx, aFailedToCreate_2; "Failed to create dump file."
0x18001dec4  mov     r9d, 4B9h
0x18001deca  mov     [rsp+8F0h+hTemplateFile], rcx
0x18001decf  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x18001ded3  jmp     short loc_18001DF2F
0x18001ded5  call    cs:__imp_GetCurrentProcessId
0x18001dedb  mov     ebx, eax
0x18001dedd  call    cs:__imp_GetCurrentProcess
0x18001dee3  mov     [rsp+8F0h+hTemplateFile], 0
0x18001deec  mov     r9d, r15d
0x18001deef  mov     rcx, rax
0x18001def2  mov     qword ptr [rsp+8F0h+dwFlagsAndAttributes], 0
0x18001defb  mov     rax, r14
0x18001defe  mov     qword ptr [rsp+8F0h+dwCreationDisposition], 0
0x18001df07  mov     r8, rdi
0x18001df0a  mov     edx, ebx
0x18001df0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df11  test    eax, eax
0x18001df13  jnz     short loc_18001DF4F
0x18001df15  lea     rax, aMinidumpwrited; "MiniDumpWriteDump failed"
0x18001df1c  mov     r9d, 4C4h
0x18001df22  mov     [rsp+8F0h+hTemplateFile], rax
0x18001df27  mov     [rsp+8F0h+dwFlagsAndAttributes], 80004005h
0x18001df2f  mov     edx, 1
0x18001df34  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x18001df3b  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x18001df42  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax
0x18001df47  lea     ecx, [rdx+6]
0x18001df4a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001df4f  mov     rcx, rsi; hLibModule
0x18001df52  call    cs:__imp_FreeLibrary
0x18001df58  test    rdi, rdi
0x18001df5b  jz      short loc_18001DF66
0x18001df5d  mov     rcx, rdi; hObject
0x18001df60  call    cs:__imp_CloseHandle
0x18001df66  mov     rcx, cs:?g_writeDumpEventSem@@3VCEventSem@@A; hEvent
0x18001df6d  call    cs:__imp_SetEvent
0x18001df73  test    eax, eax
0x18001df75  jnz     short loc_18001DF87
0x18001df77  lea     r8d, [rax+7Ah]; unsigned int
0x18001df7b  lea     rcx, aSeteventFailsI; "SetEvent fails in CEventSem::Set()"
0x18001df82  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x18001df87  xor     eax, eax
0x18001df89  mov     rcx, [rbp+7F0h+var_40]
0x18001df90  xor     rcx, rsp; StackCookie
0x18001df93  call    __security_check_cookie
0x18001df98  add     rsp, 8C8h
0x18001df9f  pop     r15
0x18001dfa1  pop     r14
0x18001dfa3  pop     rdi
0x18001dfa4  pop     rsi
0x18001dfa5  pop     rbx
0x18001dfa6  pop     rbp
0x18001dfa7  retn
```
