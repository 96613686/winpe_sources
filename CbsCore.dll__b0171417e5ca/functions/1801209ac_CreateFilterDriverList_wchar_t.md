# CreateFilterDriverList(wchar_t *)

- ea: `0x1801209ac`
- end: `0x1801211e8`
- name: `?CreateFilterDriverList@@YAJPEA_W@Z`
- size: `2108`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18011f2e4`
- `0x180120774`

## callees

- `0x18004b098`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801209ac`
- `0x18012197c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121121`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180120a8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180120a8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180120cfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180120cfa`
- `ntdll!RtlNtStatusToDosError` at `0x180120d3e`
- `ntdll!RtlNtStatusToDosError` at `0x180120df9`
- `ntdll!RtlNtStatusToDosError` at `0x180120ec5`
- `ntdll!RtlNtStatusToDosError` at `0x180120f65`
- `ntdll!RtlNtStatusToDosError` at `0x180120d3e`
- `ntdll!RtlNtStatusToDosError` at `0x180120df9`
- `ntdll!RtlNtStatusToDosError` at `0x180120ec5`
- `ntdll!RtlNtStatusToDosError` at `0x180120f65`
- `ntdll!LdrLoadDll` at `0x180120d28`
- `ntdll!LdrLoadDll` at `0x180120d28`
- `ntdll!LdrUnloadDll` at `0x180120e91`
- `ntdll!LdrUnloadDll` at `0x180121104`
- `ntdll!LdrUnloadDll` at `0x180120e91`
- `ntdll!LdrUnloadDll` at `0x180121104`
- `ntdll!RtlInitUnicodeString` at `0x180120c41`
- `ntdll!RtlInitUnicodeString` at `0x180120c41`
- `ntdll!LdrGetProcedureAddress` at `0x180120de3`
- `ntdll!LdrGetProcedureAddress` at `0x180120eb3`
- `ntdll!LdrGetProcedureAddress` at `0x180120f53`
- `ntdll!LdrGetProcedureAddress` at `0x180120de3`
- `ntdll!LdrGetProcedureAddress` at `0x180120eb3`
- `ntdll!LdrGetProcedureAddress` at `0x180120f53`

## string_xrefs

- `0x180120bb0`: `system32\FltLib.dll`
- `0x180120b39`: `Failed to get Windows directory.`
- `0x180120ab4`: `Windows directory path is too long and cannot be used`
- `0x180120d6d`: `Failed to load fltlib.dll.`
- `0x180121140`: `Failed to create filter driver list file.`

## pseudocode

```c
int __fastcall CreateFilterDriverList(wchar_t *a1)
{
  UINT WindowsDirectoryW; // eax
  signed int v2; // edi
  __int64 v3; // rdx
  signed int LastError; // edi
  unsigned int v6; // eax
  int v7; // eax
  int v8; // eax
  enum _FILTER_INFORMATION_CLASS v9; // edi
  char *FileW; // rbx
  int v11; // eax
  signed int v12; // eax
  int v13; // eax
  signed int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  signed int v17; // eax
  int v18; // eax
  signed int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // ebx
  signed int v23; // edi
  unsigned int v24; // eax
  const wchar_t *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned int v27[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v28[2]; // [rsp+48h] [rbp-B8h] BYREF
  PVOID BaseAddress; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  PVOID ProcedureAddress; // [rsp+60h] [rbp-A0h] BYREF
  PVOID v32; // [rsp+68h] [rbp-98h] BYREF
  PVOID v33; // [rsp+70h] [rbp-90h] BYREF
  struct _STRING Name; // [rsp+78h] [rbp-88h] BYREF
  struct _STRING v35; // [rsp+88h] [rbp-78h] BYREF
  struct _STRING v36; // [rsp+98h] [rbp-68h] BYREF
  int v37; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v38; // [rsp+ACh] [rbp-54h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SourceString[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v42[2048]; // [rsp+4E0h] [rbp+3E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D18h] [rbp+C18h]

  memset_0(v42, 0, sizeof(v42));
  v38 = 0;
  Name.Buffer = "FilterFindFirst";
  v30 = -1;
  v35.Buffer = "FilterFindNext";
  BaseAddress = 0;
  v36.Buffer = "FilterFindClose";
  *(_QWORD *)&Name.Length = 1048591;
  *(_QWORD *)&v35.Length = 983054;
  DestinationString = 0;
  *(_QWORD *)&v36.Length = 1048591;
  ProcedureAddress = 0;
  v32 = 0;
  v33 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(SourceString, 0, 0x208u);
  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( WindowsDirectoryW > 0x104 )
  {
    v2 = -2147467263;
    v37 = -2147467263;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Windows directory path is too long and cannot be used");
      *(_QWORD *)v27 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v27);
    }
    v3 = 574;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
      (const char *)(unsigned int)v2,
      (int)dwCreationDisposition);
    return v2;
  }
  if ( !WindowsDirectoryW )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get Windows directory.");
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      else
        v6 = LastError;
      v37 = v6;
      *(_QWORD *)v27 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v27);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x23F,
               (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)dwCreationDisposition);
    return 0;
  }
  dwCreationDisposition = L"system32\\FltLib.dll";
  v7 = StringCbPrintfW(SourceString, 0x208u, L"%ws\\%ws", Buffer);
  v2 = v7;
  if ( v7 < 0 )
  {
    v37 = v7;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Fail to generate FLTBLIB file name.");
      *(_QWORD *)v27 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v27);
    }
    v3 = 579;
    goto LABEL_5;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  dwCreationDisposition = L"Logs\\Cbs\\FilterList.log";
  v8 = StringCbPrintfW(Buffer, 0x208u, L"%ws\\%ws", Buffer);
  v2 = v8;
  if ( v8 < 0 )
  {
    v37 = v8;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Fail to generate driverlist file name.");
      *(_QWORD *)v27 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v27);
    }
    v3 = 585;
    goto LABEL_5;
  }
  v9 = FilterAggregateStandardInformation;
  FileW = (char *)CreateFileW(Buffer, 0x40000000u, 1u, 0, 2u, 0, 0);
  *(_QWORD *)v27 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v23 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create filter driver list file.");
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0x80070000;
      else
        v24 = v23;
      v37 = v24;
      *(_QWORD *)v28 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v28);
    }
    if ( !v23 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
      return 0;
    }
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x24D,
           (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
           (const char *)(unsigned int)v23,
           (unsigned int)dwCreationDispositiona);
LABEL_76:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
    return v2;
  }
  v11 = LdrLoadDll(0, 0, &DestinationString, &BaseAddress);
  if ( v11 < 0 )
  {
    v12 = RtlNtStatusToDosError(v11);
    v2 = v12;
    if ( v12 > 0 )
      v2 = (unsigned __int16)v12 | 0x80070000;
    v37 = v2;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load fltlib.dll.");
      *(_QWORD *)v28 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    if ( v2 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
        (const char *)(unsigned int)v2,
        (int)dwCreationDispositiona);
    goto LABEL_76;
  }
  v13 = LdrGetProcedureAddress(BaseAddress, &Name, 0, &ProcedureAddress);
  if ( v13 < 0 )
  {
    v14 = RtlNtStatusToDosError(v13);
    v2 = v14;
    if ( v14 > 0 )
      v2 = (unsigned __int16)v14 | 0x80070000;
    v37 = v2;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address FilterFindFirst.");
      *(_QWORD *)v28 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    if ( v2 >= 0 )
      goto LABEL_39;
    v15 = 600;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\cbs\\werlib\\cbswer.cpp",
      (const char *)(unsigned int)v2,
      (int)dwCreationDispositiona);
LABEL_39:
    if ( BaseAddress )
      LdrUnloadDll(BaseAddress);
    goto LABEL_76;
  }
  v16 = LdrGetProcedureAddress(BaseAddress, &v35, 0, &v32);
  if ( v16 < 0 )
  {
    v17 = RtlNtStatusToDosError(v16);
    v2 = v17;
    if ( v17 > 0 )
      v2 = (unsigned __int16)v17 | 0x80070000;
    v37 = v2;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address FilterFindNext.");
      *(_QWORD *)v28 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    if ( v2 >= 0 )
      goto LABEL_39;
    v15 = 604;
    goto LABEL_38;
  }
  v18 = LdrGetProcedureAddress(BaseAddress, &v36, 0, &v33);
  if ( v18 < 0 )
  {
    v19 = RtlNtStatusToDosError(v18);
    v2 = v19;
    if ( v19 > 0 )
      v2 = (unsigned __int16)v19 | 0x80070000;
    v37 = v2;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address FilterFindClose.");
      *(_QWORD *)v28 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    if ( v2 >= 0 )
      goto LABEL_39;
    v15 = 608;
    goto LABEL_38;
  }
  if ( ((int (__fastcall *)(__int64, _BYTE *, __int64, unsigned int *, __int64 *))ProcedureAddress)(
         2,
         v42,
         2048,
         &v38,
         &v30) < 0 )
  {
    dwCreationDispositiona = &v30;
    v20 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64, unsigned int *))ProcedureAddress)(0, v42, 2048, &v38);
    v2 = v20;
    if ( v20 < 0 )
    {
      v37 = v20;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get mini filter info.");
        *(_QWORD *)v28 = &v37;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v28);
      }
      v15 = 623;
      goto LABEL_38;
    }
    v9 = FilterFullInformation;
  }
  do
  {
    PrintFilterInformation(FileW, v42, v38, v9);
    v21 = ((__int64 (__fastcall *)(__int64, _QWORD, _BYTE *, __int64, unsigned int *))v32)(
            v30,
            (unsigned int)v9,
            v42,
            2048,
            &v38);
  }
  while ( v21 >= 0 );
  v22 = 0;
  if ( v21 != -2147024637 )
    v22 = v21;
  if ( v30 != -1 )
    ((void (__fastcall *)(__int64))v33)(v30);
  if ( BaseAddress )
    LdrUnloadDll(BaseAddress);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
  return v22;
}

```

## disassembly

```asm
0x1801209ac  push    rbp
0x1801209ae  push    rbx
0x1801209af  push    rdi
0x1801209b0  push    r14
0x1801209b2  lea     rbp, [rsp-0BF8h]
0x1801209ba  sub     rsp, 0CF8h
0x1801209c1  mov     rax, cs:__security_cookie
0x1801209c8  xor     rax, rsp
0x1801209cb  mov     [rbp+0C10h+var_30], rax
0x1801209d2  xor     edx, edx; Val
0x1801209d4  lea     rcx, [rbp+0C10h+var_830]; void *
0x1801209db  mov     r8d, 800h; Size
0x1801209e1  call    memset_0
0x1801209e6  lea     rax, aFilterfindfirs; "FilterFindFirst"
0x1801209ed  mov     [rbp+0C10h+var_C64], 0
0x1801209f4  mov     [rbp+0C10h+Name.Buffer], rax
0x1801209f8  lea     rcx, [rbp+0C10h+Buffer]; void *
0x1801209fc  lea     rax, aFilterfindnext; "FilterFindNext"
0x180120a03  mov     [rsp+0D10h+var_CB8], 0FFFFFFFFFFFFFFFFh
0x180120a0c  mov     [rbp+0C10h+var_C88.Buffer], rax
0x180120a10  xorps   xmm0, xmm0
0x180120a13  lea     rax, aFilterfindclos; "FilterFindClose"
0x180120a1a  mov     [rsp+0D10h+BaseAddress], 0
0x180120a23  mov     r14d, 208h
0x180120a29  mov     [rbp+0C10h+var_C78.Buffer], rax
0x180120a2d  mov     r8d, r14d; Size
0x180120a30  mov     qword ptr [rsp+0D10h+Name.Length], 10000Fh
0x180120a39  xor     edx, edx; Val
0x180120a3b  mov     qword ptr [rbp+0C10h+var_C88.Length], 0F000Eh
0x180120a43  movups  xmmword ptr [rbp+0C10h+DestinationString.Length], xmm0
0x180120a47  mov     qword ptr [rbp+0C10h+var_C78.Length], 10000Fh
0x180120a4f  mov     [rsp+0D10h+ProcedureAddress], 0
0x180120a58  mov     [rsp+0D10h+var_CA8], 0
0x180120a61  mov     [rsp+0D10h+var_CA0], 0
0x180120a6a  call    memset_0
0x180120a6f  mov     r8d, r14d; Size
0x180120a72  lea     rcx, [rbp+0C10h+SourceString]; void *
0x180120a79  xor     edx, edx; Val
0x180120a7b  call    memset_0
0x180120a80  mov     ebx, 104h
0x180120a85  lea     rcx, [rbp+0C10h+Buffer]; lpBuffer
0x180120a89  mov     edx, ebx; uSize
0x180120a8b  call    cs:__imp_GetWindowsDirectoryW
0x180120a92  nop     dword ptr [rax+rax+00h]
0x180120a97  cmp     eax, ebx
0x180120a99  jbe     short loc_180120B12
0x180120a9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120aa2  mov     edi, 80004001h
0x180120aa7  mov     [rbp+0C10h+var_C68], edi
0x180120aaa  test    rcx, rcx
0x180120aad  jz      short loc_180120AF0
0x180120aaf  mov     ebx, 3
0x180120ab4  lea     r9, aWindowsDirecto_0; "Windows directory path is too long and "...
0x180120abb  mov     r8d, ebx
0x180120abe  xor     edx, edx
0x180120ac0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180120ac5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120acc  lea     rax, [rbp+0C10h+var_C68]
0x180120ad0  mov     qword ptr [rsp+0D10h+var_CD0], rax
0x180120ad5  lea     r9, asc_1802EE7AC; ": {}"
0x180120adc  lea     rax, [rsp+0D10h+var_CD0]
0x180120ae1  mov     r8d, ebx
0x180120ae4  mov     dl, 1
0x180120ae6  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax; int
0x180120aeb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180120af0  mov     edx, 23Eh; void *
0x180120af5  mov     rcx, [rbp+0C18h]; this
0x180120afc  lea     r8, aOnecoreBaseCbs_72; "onecore\\base\\cbs\\werlib\\cbswer.cpp"
0x180120b03  mov     r9d, edi; char *
0x180120b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120b0b  mov     eax, edi
0x180120b0d  jmp     loc_1801211CB
0x180120b12  test    eax, eax
0x180120b14  jnz     loc_180120BB0
0x180120b1a  call    cs:__imp_GetLastError
0x180120b21  nop     dword ptr [rax+rax+00h]
0x180120b26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120b2d  mov     edi, eax
0x180120b2f  test    rcx, rcx
0x180120b32  jz      short loc_180120B88
0x180120b34  mov     ebx, 3
0x180120b39  lea     r9, aFailedToGetWin; "Failed to get Windows directory."
0x180120b40  mov     r8d, ebx
0x180120b43  xor     edx, edx
0x180120b45  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180120b4a  test    edi, edi
0x180120b4c  jg      short loc_180120B52
0x180120b4e  mov     eax, edi
0x180120b50  jmp     short loc_180120B5A
0x180120b52  movzx   eax, di
0x180120b55  or      eax, 80070000h
0x180120b5a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120b61  lea     r9, a0; ": {0}"
0x180120b68  mov     [rbp+0C10h+var_C68], eax
0x180120b6b  mov     r8d, ebx
0x180120b6e  lea     rax, [rbp+0C10h+var_C68]
0x180120b72  mov     dl, 1
0x180120b74  mov     qword ptr [rsp+0D10h+var_CD0], rax
0x180120b79  lea     rax, [rsp+0D10h+var_CD0]
0x180120b7e  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax; unsigned int
0x180120b83  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180120b88  test    edi, edi
0x180120b8a  jz      loc_1801211C9
0x180120b90  mov     rcx, [rbp+0C18h]; this
0x180120b97  lea     r8, aOnecoreBaseCbs_72; "onecore\\base\\cbs\\werlib\\cbswer.cpp"
0x180120b9e  mov     r9d, edi; char *
0x180120ba1  mov     edx, 23Fh; void *
0x180120ba6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180120bab  jmp     loc_1801211CB
0x180120bb0  lea     rax, aSystem32Fltlib; "system32\\FltLib.dll"
0x180120bb7  mov     rdx, r14; unsigned __int64
0x180120bba  lea     r9, [rbp+0C10h+Buffer]
0x180120bbe  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax
0x180120bc3  lea     r8, aWsWs_4; "%ws\\%ws"
0x180120bca  lea     rcx, [rbp+0C10h+SourceString]; wchar_t *
0x180120bd1  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180120bd6  mov     edi, eax
0x180120bd8  test    eax, eax
0x180120bda  jns     short loc_180120C36
0x180120bdc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120be3  mov     [rbp+0C10h+var_C68], eax
0x180120be6  test    rcx, rcx
0x180120be9  jz      short loc_180120C2C
0x180120beb  mov     ebx, 3
0x180120bf0  lea     r9, aFailToGenerate; "Fail to generate FLTBLIB file name."
0x180120bf7  mov     r8d, ebx
0x180120bfa  xor     edx, edx
0x180120bfc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180120c01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120c08  lea     rax, [rbp+0C10h+var_C68]
0x180120c0c  mov     qword ptr [rsp+0D10h+var_CD0], rax
0x180120c11  lea     r9, asc_1802EE7AC; ": {}"
0x180120c18  lea     rax, [rsp+0D10h+var_CD0]
0x180120c1d  mov     r8d, ebx
0x180120c20  mov     dl, 1
0x180120c22  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax
0x180120c27  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180120c2c  mov     edx, 243h
0x180120c31  jmp     loc_180120AF5
0x180120c36  lea     rdx, [rbp+0C10h+SourceString]; SourceString
0x180120c3d  lea     rcx, [rbp+0C10h+DestinationString]; DestinationString
0x180120c41  call    cs:__imp_RtlInitUnicodeString
0x180120c48  nop     dword ptr [rax+rax+00h]
0x180120c4d  lea     rax, aLogsCbsFilterl; "Logs\\Cbs\\FilterList.log"
0x180120c54  mov     rdx, r14; unsigned __int64
0x180120c57  lea     r9, [rbp+0C10h+Buffer]
0x180120c5b  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax
0x180120c60  lea     r8, aWsWs_4; "%ws\\%ws"
0x180120c67  lea     rcx, [rbp+0C10h+Buffer]; wchar_t *
0x180120c6b  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180120c70  mov     edi, eax
0x180120c72  test    eax, eax
0x180120c74  jns     short loc_180120CD0
0x180120c76  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120c7d  mov     [rbp+0C10h+var_C68], eax
0x180120c80  test    rcx, rcx
0x180120c83  jz      short loc_180120CC6
0x180120c85  mov     ebx, 3
0x180120c8a  lea     r9, aFailToGenerate_0; "Fail to generate driverlist file name."
0x180120c91  mov     r8d, ebx
0x180120c94  xor     edx, edx
0x180120c96  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180120c9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120ca2  lea     rax, [rbp+0C10h+var_C68]
0x180120ca6  mov     qword ptr [rsp+0D10h+var_CD0], rax
0x180120cab  lea     r9, asc_1802EE7AC; ": {}"
0x180120cb2  lea     rax, [rsp+0D10h+var_CD0]
0x180120cb7  mov     r8d, ebx
0x180120cba  mov     dl, 1
0x180120cbc  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax
0x180120cc1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180120cc6  mov     edx, 249h
0x180120ccb  jmp     loc_180120AF5
0x180120cd0  mov     edi, 2
0x180120cd5  mov     [rsp+0D10h+hTemplateFile], 0; hTemplateFile
0x180120cde  mov     [rsp+0D10h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180120ce6  lea     rcx, [rbp+0C10h+Buffer]; lpFileName
0x180120cea  xor     r9d, r9d; lpSecurityAttributes
0x180120ced  mov     [rsp+0D10h+dwCreationDisposition], edi; dwCreationDisposition
0x180120cf1  mov     edx, 40000000h; dwDesiredAccess
0x180120cf6  lea     r8d, [rdi-1]; dwShareMode
0x180120cfa  call    cs:__imp_CreateFileW
0x180120d01  nop     dword ptr [rax+rax+00h]
0x180120d06  mov     rbx, rax
0x180120d09  mov     qword ptr [rsp+0D10h+var_CD0], rax
0x180120d0e  dec     rax
0x180120d11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180120d15  ja      loc_180121121
0x180120d1b  lea     r9, [rsp+0D10h+BaseAddress]; BaseAddress
0x180120d20  xor     edx, edx; LoadFlags
0x180120d22  lea     r8, [rbp+0C10h+DestinationString]; Name
0x180120d26  xor     ecx, ecx; SearchPath
0x180120d28  call    cs:__imp_LdrLoadDll
0x180120d2f  nop     dword ptr [rax+rax+00h]
0x180120d34  test    eax, eax
0x180120d36  jns     loc_180120DD1
0x180120d3c  mov     ecx, eax; Status
0x180120d3e  call    cs:__imp_RtlNtStatusToDosError
0x180120d45  nop     dword ptr [rax+rax+00h]
0x180120d4a  mov     edi, eax
0x180120d4c  test    eax, eax
0x180120d4e  jle     short loc_180120D59
0x180120d50  movzx   edi, ax
0x180120d53  or      edi, 80070000h
0x180120d59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120d60  mov     [rbp+0C10h+var_C68], edi
0x180120d63  test    rcx, rcx
0x180120d66  jz      short loc_180120DA9
0x180120d68  mov     ebx, 3
0x180120d6d  lea     r9, aFailedToLoadFl; "Failed to load fltlib.dll."
0x180120d74  mov     r8d, ebx
0x180120d77  xor     edx, edx
0x180120d79  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180120d7e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120d85  lea     rax, [rbp+0C10h+var_C68]
0x180120d89  mov     qword ptr [rsp+0D10h+var_CC8], rax
0x180120d8e  lea     r9, asc_1802EE7AC; ": {}"
0x180120d95  lea     rax, [rsp+0D10h+var_CC8]
0x180120d9a  mov     r8d, ebx
0x180120d9d  mov     dl, 1
0x180120d9f  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax; int
0x180120da4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180120da9  test    edi, edi
0x180120dab  jns     loc_1801211B0
0x180120db1  mov     rcx, [rbp+0C18h]; this
0x180120db8  lea     r8, aOnecoreBaseCbs_72; "onecore\\base\\cbs\\werlib\\cbswer.cpp"
0x180120dbf  mov     r9d, edi; char *
0x180120dc2  mov     edx, 252h; void *
0x180120dc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120dcc  jmp     loc_1801211B0
0x180120dd1  mov     rcx, [rsp+0D10h+BaseAddress]; BaseAddress
0x180120dd6  lea     r9, [rsp+0D10h+ProcedureAddress]; ProcedureAddress
0x180120ddb  xor     r8d, r8d; Ordinal
0x180120dde  lea     rdx, [rsp+0D10h+Name]; Name
0x180120de3  call    cs:__imp_LdrGetProcedureAddress
0x180120dea  nop     dword ptr [rax+rax+00h]
0x180120def  test    eax, eax
0x180120df1  jns     loc_180120EA2
0x180120df7  mov     ecx, eax; Status
0x180120df9  call    cs:__imp_RtlNtStatusToDosError
0x180120e00  nop     dword ptr [rax+rax+00h]
0x180120e05  mov     edi, eax
0x180120e07  test    eax, eax
0x180120e09  jle     short loc_180120E14
0x180120e0b  movzx   edi, ax
0x180120e0e  or      edi, 80070000h
0x180120e14  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120e1b  mov     [rbp+0C10h+var_C68], edi
0x180120e1e  test    rcx, rcx
0x180120e21  jz      short loc_180120E64
0x180120e23  mov     ebx, 3
0x180120e28  lea     r9, aFailedToGetPro_56; "Failed to get proc address FilterFindFi"...
0x180120e2f  mov     r8d, ebx
0x180120e32  xor     edx, edx
0x180120e34  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180120e39  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120e40  lea     rax, [rbp+0C10h+var_C68]
0x180120e44  mov     qword ptr [rsp+0D10h+var_CC8], rax
0x180120e49  lea     r9, asc_1802EE7AC; ": {}"
0x180120e50  lea     rax, [rsp+0D10h+var_CC8]
0x180120e55  mov     r8d, ebx
0x180120e58  mov     dl, 1
0x180120e5a  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax; int
0x180120e5f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180120e64  test    edi, edi
0x180120e66  jns     short loc_180120E83
0x180120e68  mov     edx, 258h; void *
0x180120e6d  mov     rcx, [rbp+0C18h]; this
0x180120e74  lea     r8, aOnecoreBaseCbs_72; "onecore\\base\\cbs\\werlib\\cbswer.cpp"
0x180120e7b  mov     r9d, edi; char *
0x180120e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120e83  mov     rcx, [rsp+0D10h+BaseAddress]; BaseAddress
0x180120e88  test    rcx, rcx
0x180120e8b  jz      loc_1801211B0
0x180120e91  call    cs:__imp_LdrUnloadDll
0x180120e98  nop     dword ptr [rax+rax+00h]
0x180120e9d  jmp     loc_1801211B0
0x180120ea2  mov     rcx, [rsp+0D10h+BaseAddress]; BaseAddress
0x180120ea7  lea     r9, [rsp+0D10h+var_CA8]; ProcedureAddress
0x180120eac  xor     r8d, r8d; Ordinal
0x180120eaf  lea     rdx, [rbp+0C10h+var_C88]; Name
0x180120eb3  call    cs:__imp_LdrGetProcedureAddress
0x180120eba  nop     dword ptr [rax+rax+00h]
0x180120ebf  test    eax, eax
0x180120ec1  jns     short loc_180120F42
0x180120ec3  mov     ecx, eax; Status
0x180120ec5  call    cs:__imp_RtlNtStatusToDosError
0x180120ecc  nop     dword ptr [rax+rax+00h]
0x180120ed1  mov     edi, eax
0x180120ed3  test    eax, eax
0x180120ed5  jle     short loc_180120EE0
0x180120ed7  movzx   edi, ax
0x180120eda  or      edi, 80070000h
0x180120ee0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180120ee7  mov     [rbp+0C10h+var_C68], edi
0x180120eea  test    rcx, rcx
0x180120eed  jz      short loc_180120F30
0x180120eef  mov     ebx, 3
0x180120ef4  lea     r9, aFailedToGetPro_40; "Failed to get proc address FilterFindNe"...
0x180120efb  mov     r8d, ebx
  ... truncated ...
```
