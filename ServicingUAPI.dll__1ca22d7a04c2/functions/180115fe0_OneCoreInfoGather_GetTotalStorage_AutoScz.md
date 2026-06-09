# OneCoreInfoGather::GetTotalStorage(AutoScz *)

- ea: `0x180115fe0`
- end: `0x1801163c0`
- name: `?GetTotalStorage@OneCoreInfoGather@@MEAAJPEAVAutoScz@@@Z`
- size: `992`
- prototype: `__int64 __fastcall(OneCoreInfoGather *__hidden this, struct AutoScz *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x18000c350`
- `0x18000f614`
- `0x18000f874`
- `0x180115b88`
- `0x180115fe0`
- `0x180182d50`

## import_xrefs

- `ntdll!NtClose` at `0x180116387`
- `ntdll!NtClose` at `0x180116387`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180116080`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180116080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011615d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011615d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116216`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011613e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011613e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180116206`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180116206`

## string_xrefs

- `0x1801160bf`: `Failed to get System directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OneCoreInfoGather::GetTotalStorage(OneCoreInfoGather *this, struct AutoScz *a2)
{
  char *FileW; // rbx
  signed int LastError; // eax
  signed int StorageHelper; // edi
  __int64 v7; // rdx
  int v8; // edx
  signed int v9; // eax
  __int64 v10; // rdx
  signed int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  DWORD BytesReturned; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 OutBuffer; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h]
  WCHAR FileName[8]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v21[264]; // [rsp+290h] [rbp+190h] BYREF

  wcscpy(FileName, L"\\\\.\\#:");
  BytesReturned = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(v21, 0, 0x208u);
  OutBuffer = 0;
  v18 = 0;
  FileW = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    StorageHelper = LastError;
    if ( LastError > 0 )
      StorageHelper = (unsigned __int16)LastError | 0x80070000;
    if ( StorageHelper < 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get System directory");
        LOBYTE(v7) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v7,
          3,
          ": {0}");
      }
      v8 = 81;
LABEL_30:
      DebugOnError("onecore\\base\\servicing\\devicegather\\lib\\onecoreinfogather.cpp", v8);
      goto LABEL_31;
    }
  }
  FileName[4] = Buffer[0];
  FileW = (char *)CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v9 = GetLastError();
    StorageHelper = v9;
    if ( v9 > 0 )
      StorageHelper = (unsigned __int16)v9 | 0x80070000;
    if ( StorageHelper < 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get OS volume handle");
        LOBYTE(v10) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v10,
          3,
          ": {0}");
      }
      v8 = 89;
      goto LABEL_30;
    }
  }
  if ( !DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
  {
    v11 = GetLastError();
    StorageHelper = v11;
    if ( v11 > 0 )
      StorageHelper = (unsigned __int16)v11 | 0x80070000;
    if ( StorageHelper < 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Retrieving storage device number failed.");
        LOBYTE(v12) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v12,
          3,
          ": {0}");
      }
      v8 = 95;
      goto LABEL_30;
    }
  }
  StorageHelper = StringCchPrintfW(v21, 0x104u, L"\\\\.\\PhysicalDrive%u", HIDWORD(OutBuffer));
  if ( StorageHelper < 0 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "StringCchPrintf failed.");
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {0}");
    }
    v8 = 99;
    goto LABEL_30;
  }
  StorageHelper = OneCoreInfoGather::GetStorageHelper(this, v21, a2);
  if ( StorageHelper < 0 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "GetStorageHelper failed.");
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {0}");
    }
    v8 = 101;
    goto LABEL_30;
  }
LABEL_31:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
    __fastfail(7u);
  return (unsigned int)StorageHelper;
}

```

## disassembly

```asm
0x180115fe0  push    rbp
0x180115fe2  push    rbx
0x180115fe3  push    rsi
0x180115fe4  push    rdi
0x180115fe5  push    r14
0x180115fe7  push    r15
0x180115fe9  lea     rbp, [rsp-3B8h]
0x180115ff1  sub     rsp, 4B8h
0x180115ff8  mov     [rsp+4E0h+var_490], 0FFFFFFFFFFFFFFFEh
0x180116001  mov     rax, cs:__security_cookie
0x180116008  xor     rax, rsp
0x18011600b  mov     [rbp+3E0h+var_40], rax
0x180116012  mov     r15, rdx
0x180116015  mov     r14, rcx
0x180116018  mov     rax, 5C002E005C005Ch
0x180116022  mov     qword ptr [rsp+4E0h+FileName], rax
0x180116027  mov     eax, 23h ; '#'
0x18011602c  mov     [rsp+4E0h+var_468], ax
0x180116031  mov     [rsp+4E0h+var_466], 3Ah ; ':'
0x180116039  mov     [rsp+4E0h+BytesReturned], 0
0x180116041  mov     ebx, 208h
0x180116046  mov     r8d, ebx; Size
0x180116049  xor     edx, edx; Val
0x18011604b  lea     rcx, [rbp+3E0h+Buffer]; void *
0x18011604f  call    memset_0
0x180116054  mov     r8d, ebx; Size
0x180116057  xor     edx, edx; Val
0x180116059  lea     rcx, [rbp+3E0h+var_250]; void *
0x180116060  call    memset_0
0x180116065  xor     eax, eax
0x180116067  mov     [rsp+4E0h+OutBuffer], rax
0x18011606c  mov     [rsp+4E0h+var_478], eax
0x180116070  xor     ebx, ebx
0x180116072  mov     [rsp+4E0h+var_498], rbx
0x180116077  mov     edx, 104h; uSize
0x18011607c  lea     rcx, [rbp+3E0h+Buffer]; lpBuffer
0x180116080  call    cs:__imp_GetSystemDirectoryW
0x180116087  nop     dword ptr [rax+rax+00h]
0x18011608c  test    eax, eax
0x18011608e  jnz     short loc_18011610B
0x180116090  call    cs:__imp_GetLastError
0x180116097  nop     dword ptr [rax+rax+00h]
0x18011609c  mov     edi, eax
0x18011609e  test    eax, eax
0x1801160a0  jle     short loc_1801160AB
0x1801160a2  movzx   edi, ax
0x1801160a5  or      edi, 80070000h
0x1801160ab  mov     [rsp+4E0h+var_488], edi
0x1801160af  test    edi, edi
0x1801160b1  jns     short loc_18011610B
0x1801160b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801160ba  test    rcx, rcx
0x1801160bd  jz      short loc_180116101
0x1801160bf  lea     r9, aFailedToGetSys_0; "Failed to get System directory"
0x1801160c6  mov     esi, 3
0x1801160cb  mov     r8d, esi
0x1801160ce  xor     edx, edx
0x1801160d0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801160d5  lea     rax, [rsp+4E0h+var_488]
0x1801160da  mov     [rsp+4E0h+var_4A0], rax
0x1801160df  lea     rax, [rsp+4E0h+var_4A0]
0x1801160e4  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x1801160e9  lea     r9, a0; ": {0}"
0x1801160f0  mov     r8d, esi
0x1801160f3  mov     dl, 1
0x1801160f5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801160fc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180116101  mov     edx, 51h ; 'Q'
0x180116106  jmp     loc_18011636D
0x18011610b  movzx   eax, [rbp+3E0h+Buffer]
0x18011610f  mov     [rsp+4E0h+var_468], ax
0x180116114  mov     [rsp+4E0h+hTemplateFile], 0; hTemplateFile
0x18011611d  mov     [rsp+4E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180116125  mov     esi, 3
0x18011612a  mov     [rsp+4E0h+dwCreationDisposition], esi; dwCreationDisposition
0x18011612e  xor     r9d, r9d; lpSecurityAttributes
0x180116131  mov     r8d, esi; dwShareMode
0x180116134  mov     edx, 80000000h; dwDesiredAccess
0x180116139  lea     rcx, [rsp+4E0h+FileName]; lpFileName
0x18011613e  call    cs:__imp_CreateFileW
0x180116145  nop     dword ptr [rax+rax+00h]
0x18011614a  mov     rbx, rax
0x18011614d  mov     [rsp+4E0h+var_498], rax
0x180116152  inc     rax
0x180116155  test    rax, 0FFFFFFFFFFFFFFFEh
0x18011615b  jnz     short loc_1801161D3
0x18011615d  call    cs:__imp_GetLastError
0x180116164  nop     dword ptr [rax+rax+00h]
0x180116169  mov     edi, eax
0x18011616b  test    eax, eax
0x18011616d  jle     short loc_180116178
0x18011616f  movzx   edi, ax
0x180116172  or      edi, 80070000h
0x180116178  mov     [rsp+4E0h+var_488], edi
0x18011617c  test    edi, edi
0x18011617e  jns     short loc_1801161D3
0x180116180  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180116187  test    rcx, rcx
0x18011618a  jz      short loc_1801161C9
0x18011618c  lea     r9, aFailedToGetOsV; "Failed to get OS volume handle"
0x180116193  mov     r8d, esi
0x180116196  xor     edx, edx
0x180116198  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011619d  lea     rax, [rsp+4E0h+var_488]
0x1801161a2  mov     [rsp+4E0h+var_4A0], rax
0x1801161a7  lea     rax, [rsp+4E0h+var_4A0]
0x1801161ac  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x1801161b1  lea     r9, a0; ": {0}"
0x1801161b8  mov     r8d, esi
0x1801161bb  mov     dl, 1
0x1801161bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801161c4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801161c9  mov     edx, 59h ; 'Y'
0x1801161ce  jmp     loc_18011636D
0x1801161d3  mov     [rsp+4E0h+lpOverlapped], 0; lpOverlapped
0x1801161dc  lea     rax, [rsp+4E0h+BytesReturned]
0x1801161e1  mov     [rsp+4E0h+hTemplateFile], rax; lpBytesReturned
0x1801161e6  mov     [rsp+4E0h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x1801161ee  lea     rax, [rsp+4E0h+OutBuffer]
0x1801161f3  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax; lpOutBuffer
0x1801161f8  xor     r9d, r9d; nInBufferSize
0x1801161fb  xor     r8d, r8d; lpInBuffer
0x1801161fe  mov     edx, 2D1080h; dwIoControlCode
0x180116203  mov     rcx, rbx; hDevice
0x180116206  call    cs:__imp_DeviceIoControl
0x18011620d  nop     dword ptr [rax+rax+00h]
0x180116212  test    eax, eax
0x180116214  jnz     short loc_18011628C
0x180116216  call    cs:__imp_GetLastError
0x18011621d  nop     dword ptr [rax+rax+00h]
0x180116222  mov     edi, eax
0x180116224  test    eax, eax
0x180116226  jle     short loc_180116231
0x180116228  movzx   edi, ax
0x18011622b  or      edi, 80070000h
0x180116231  mov     [rsp+4E0h+var_488], edi
0x180116235  test    edi, edi
0x180116237  jns     short loc_18011628C
0x180116239  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180116240  test    rcx, rcx
0x180116243  jz      short loc_180116282
0x180116245  lea     r9, aRetrievingStor; "Retrieving storage device number failed"...
0x18011624c  mov     r8d, esi
0x18011624f  xor     edx, edx
0x180116251  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180116256  lea     rax, [rsp+4E0h+var_488]
0x18011625b  mov     [rsp+4E0h+var_4A0], rax
0x180116260  lea     rax, [rsp+4E0h+var_4A0]
0x180116265  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x18011626a  lea     r9, a0; ": {0}"
0x180116271  mov     r8d, esi
0x180116274  mov     dl, 1
0x180116276  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011627d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180116282  mov     edx, 5Fh ; '_'
0x180116287  jmp     loc_18011636D
0x18011628c  mov     r9d, dword ptr [rsp+4E0h+OutBuffer+4]
0x180116291  lea     r8, aPhysicaldriveU; "\\\\.\\PhysicalDrive%u"
0x180116298  mov     edx, 104h; unsigned __int64
0x18011629d  lea     rcx, [rbp+3E0h+var_250]; wchar_t *
0x1801162a4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801162a9  mov     edi, eax
0x1801162ab  mov     [rsp+4E0h+var_488], eax
0x1801162af  test    eax, eax
0x1801162b1  jns     short loc_180116303
0x1801162b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801162ba  test    rcx, rcx
0x1801162bd  jz      short loc_1801162FC
0x1801162bf  lea     r9, aStringcchprint; "StringCchPrintf failed."
0x1801162c6  mov     r8d, esi
0x1801162c9  xor     edx, edx
0x1801162cb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801162d0  lea     rax, [rsp+4E0h+var_488]
0x1801162d5  mov     [rsp+4E0h+var_4A0], rax
0x1801162da  lea     rax, [rsp+4E0h+var_4A0]
0x1801162df  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x1801162e4  lea     r9, a0; ": {0}"
0x1801162eb  mov     r8d, esi
0x1801162ee  mov     dl, 1
0x1801162f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801162f7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801162fc  mov     edx, 63h ; 'c'
0x180116301  jmp     short loc_18011636D
0x180116303  mov     r8, r15; struct AutoScz *
0x180116306  lea     rdx, [rbp+3E0h+var_250]; wchar_t *
0x18011630d  mov     rcx, r14; this
0x180116310  call    ?GetStorageHelper@OneCoreInfoGather@@IEAAJPEB_WPEAVAutoScz@@@Z; OneCoreInfoGather::GetStorageHelper(wchar_t const *,AutoScz *)
0x180116315  mov     edi, eax
0x180116317  mov     [rsp+4E0h+var_488], eax
0x18011631b  test    eax, eax
0x18011631d  jns     short loc_18011637A
0x18011631f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180116326  test    rcx, rcx
0x180116329  jz      short loc_180116368
0x18011632b  lea     r9, aGetstoragehelp; "GetStorageHelper failed."
0x180116332  mov     r8d, esi
0x180116335  xor     edx, edx
0x180116337  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18011633c  lea     rax, [rsp+4E0h+var_488]
0x180116341  mov     [rsp+4E0h+var_4A0], rax
0x180116346  lea     rax, [rsp+4E0h+var_4A0]
0x18011634b  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x180116350  lea     r9, a0; ": {0}"
0x180116357  mov     r8d, esi
0x18011635a  mov     dl, 1
0x18011635c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180116363  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180116368  mov     edx, 65h ; 'e'; int
0x18011636d  lea     rcx, aOnecoreBaseSer_33; "onecore\\base\\servicing\\devicegather"...
0x180116374  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x180116379  nop
0x18011637a  lea     rax, [rbx-1]
0x18011637e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180116382  ja      short loc_18011639E
0x180116384  mov     rcx, rbx; Handle
0x180116387  call    cs:__imp_NtClose
0x18011638e  nop     dword ptr [rax+rax+00h]
0x180116393  test    eax, eax
0x180116395  jns     short loc_18011639E
0x180116397  mov     ecx, 7
0x18011639c  int     29h; Win8: RtlFailFast(ecx)
0x18011639e  mov     eax, edi
0x1801163a0  mov     rcx, [rbp+3E0h+var_40]
0x1801163a7  xor     rcx, rsp; StackCookie
0x1801163aa  call    __security_check_cookie
0x1801163af  add     rsp, 4B8h
0x1801163b6  pop     r15
0x1801163b8  pop     r14
0x1801163ba  pop     rdi
0x1801163bb  pop     rsi
0x1801163bc  pop     rbx
0x1801163bd  pop     rbp
0x1801163be  retn
```
