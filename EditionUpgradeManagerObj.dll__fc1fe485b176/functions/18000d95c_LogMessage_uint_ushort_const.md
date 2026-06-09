# LogMessage(uint,ushort const *,...)

- ea: `0x18000d95c`
- end: `0x18000dcf2`
- name: `?LogMessage@@YAXIPEBGZZ`
- size: `918`
- prototype: `void(int, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009300`

## callees

- `0x180001ac0`
- `0x1800026cc`
- `0x180007970`
- `0x1800090dc`
- `0x180009480`
- `0x18000d95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d9d1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d9d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dccb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000da53`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000da53`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000daef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db3f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000daef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000db1c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000db76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000db1c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000db76`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000db4e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000db4e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dc18`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dc8c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dcac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dc18`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dc8c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dcac`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000db97`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000db97`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000dbd0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000dc4b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000dbd0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000dc4b`

## pseudocode

```c
void LogMessage(int a1, const unsigned __int16 *a2, ...)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  DWORD LastError; // r15d
  signed int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // edi
  const wchar_t *v9; // rbx
  HANDLE FileW; // rbx
  CHAR *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  CHAR *v14; // rax
  __int64 NumberOfBytesWritten; // [rsp+58h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten_8[4]; // [rsp+60h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime_8; // [rsp+70h] [rbp-98h] BYREF
  WCHAR WideCharStr[80]; // [rsp+88h] [rbp-80h] BYREF
  CHAR MultiByteStr[512]; // [rsp+128h] [rbp+20h] BYREF
  WCHAR Dst[264]; // [rsp+328h] [rbp+220h] BYREF
  WCHAR PathName[264]; // [rsp+538h] [rbp+430h] BYREF
  wchar_t Buffer[504]; // [rsp+748h] [rbp+640h] BYREF
  va_list Args; // [rsp+B98h] [rbp+A90h] BYREF

  va_start(Args, a2);
  NumberOfBytesWritten = 0;
  v3 = 0;
  *(_OWORD *)NumberOfBytesWritten_8 = 0;
  SystemTime_8 = 0;
  LastError = GetLastError();
  if ( dword_18002FBC8 )
    goto LABEL_9;
  if ( InitializeCriticalSectionAndSpinCount(&g_csLog, 0) )
  {
    dword_18002FBC8 = 1;
LABEL_9:
    v7 = 0;
    goto LABEL_10;
  }
  v5 = GetLastError();
  v6 = (unsigned int)v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    v6 = 2147500037LL;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  v8 = NumberOfBytesWritten_8[2];
  if ( !NumberOfBytesWritten_8[2] )
  {
    v3 = &g_csLog;
    EnterCriticalSection(&g_csLog);
    v8 = 1;
  }
  if ( a1 == 1 )
  {
    v9 = L"Warning";
  }
  else
  {
    v9 = L"Error";
    if ( a1 != 2 )
      v9 = L"Info";
  }
  GetLocalTime(&SystemTime_8);
  StringCchPrintfW(
    WideCharStr,
    0x50u,
    L"%d-%02d-%02d %02d:%02d:%02d, %-8s              WAU    ",
    SystemTime_8.wYear,
    SystemTime_8.wMonth,
    SystemTime_8.wDay,
    SystemTime_8.wHour,
    SystemTime_8.wMinute,
    SystemTime_8.wSecond,
    v9,
    NumberOfBytesWritten,
    *(_QWORD *)NumberOfBytesWritten_8);
  if ( (unsigned int)vsnwprintf(Buffer, 0x1F3u, a2, Args) > 0x1F2 )
    Buffer[499] = 0;
  ExpandEnvironmentStringsW(L"%LOCALAPPDATA%\\Microsoft\\Windows\\Windows Anytime Upgrade\\Upgrade.log", Dst, 0x105u);
  FileW = CreateFileW(Dst, 6u, 1u, 0, 4u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL
    || (ExpandEnvironmentStringsW(L"%LOCALAPPDATA%\\Microsoft\\Windows\\Windows Anytime Upgrade\\", PathName, 0x104u),
        CreateDirectoryW(PathName, 0),
        FileW = CreateFileW(Dst, 6u, 1u, 0, 4u, 0x80u, 0),
        FileW != (HANDLE)-1LL) )
  {
    if ( SetFilePointer(FileW, 0, 0, 2u) != -1 )
    {
      WideCharToMultiByte(0, 0x400u, WideCharStr, -1, MultiByteStr, 500, 0, 0);
      v11 = MultiByteStr;
      v12 = 0x7FFFFFFF;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v12;
      }
      while ( v12 );
      WriteFile(FileW, MultiByteStr, v12 != 0 ? 0x7FFFFFFF - v12 : 0, (LPDWORD)&NumberOfBytesWritten, 0);
      WideCharToMultiByte(0, 0x400u, Buffer, -1, MultiByteStr, 500, 0, 0);
      v13 = 0x7FFFFFFF;
      v14 = MultiByteStr;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      WriteFile(FileW, MultiByteStr, v13 != 0 ? 0x7FFFFFFF - v13 : 0, (LPDWORD)&NumberOfBytesWritten, 0);
      WriteFile(FileW, "\r\n", 2u, (LPDWORD)&NumberOfBytesWritten, 0);
    }
    CloseHandle(FileW);
  }
  SetLastError(LastError);
  if ( v8 )
    LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x18000d95c  mov     rax, rsp
0x18000d95f  mov     [rax+10h], rdx
0x18000d963  mov     [rax+18h], r8
0x18000d967  mov     [rax+20h], r9
0x18000d96b  push    rbp
0x18000d96c  push    rbx
0x18000d96d  push    rsi
0x18000d96e  push    rdi
0x18000d96f  push    r12
0x18000d971  push    r14
0x18000d973  push    r15
0x18000d975  lea     rbp, [rax-0A78h]
0x18000d97c  sub     rsp, 0B40h
0x18000d983  mov     rax, cs:__security_cookie
0x18000d98a  xor     rax, rsp
0x18000d98d  mov     [rbp+0A70h+var_40], rax
0x18000d994  xor     r12d, r12d
0x18000d997  xorps   xmm0, xmm0
0x18000d99a  mov     qword ptr [rsp+0B70h+NumberOfBytesWritten], r12
0x18000d99f  mov     esi, ecx
0x18000d9a1  mov     [rsp+0B70h+NumberOfBytesWritten], r12d
0x18000d9a6  mov     r14d, r12d
0x18000d9a9  movups  xmmword ptr [rsp+0B70h+NumberOfBytesWritten+8], xmm0
0x18000d9ae  movups  xmmword ptr [rsp+0B70h+SystemTime+8], xmm0
0x18000d9b3  call    cs:__imp_GetLastError
0x18000d9b9  cmp     cs:dword_18002FBC8, r12d
0x18000d9c0  lea     rbx, ?g_csLog@@3V?$CWin32CriticalSectionT@VCEmptyType@@@@A; CWin32CriticalSectionT<CEmptyType> g_csLog
0x18000d9c7  mov     r15d, eax
0x18000d9ca  jnz     short loc_18000DA0A
0x18000d9cc  xor     edx, edx; dwSpinCount
0x18000d9ce  mov     rcx, rbx; lpCriticalSection
0x18000d9d1  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d9d7  test    eax, eax
0x18000d9d9  jnz     short loc_18000DA00
0x18000d9db  call    cs:__imp_GetLastError
0x18000d9e1  mov     ecx, eax
0x18000d9e3  test    eax, eax
0x18000d9e5  jnz     short loc_18000D9EE
0x18000d9e7  mov     ecx, 80004005h
0x18000d9ec  jmp     short loc_18000D9F9
0x18000d9ee  jle     short loc_18000D9F9
0x18000d9f0  movzx   ecx, ax
0x18000d9f3  or      ecx, 80070000h
0x18000d9f9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000d9fe  jmp     short loc_18000DA0D
0x18000da00  mov     cs:dword_18002FBC8, 1
0x18000da0a  mov     ecx, r12d
0x18000da0d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000da12  mov     edi, dword ptr [rsp+0B70h+SystemTime]
0x18000da16  test    edi, edi
0x18000da18  jnz     short loc_18000DA2B
0x18000da1a  mov     rcx, rbx; lpCriticalSection
0x18000da1d  mov     r14, rbx
0x18000da20  call    cs:__imp_EnterCriticalSection
0x18000da26  mov     edi, 1
0x18000da2b  cmp     esi, 1
0x18000da2e  jnz     short loc_18000DA39
0x18000da30  lea     rbx, aWarning; "Warning"
0x18000da37  jmp     short loc_18000DA4E
0x18000da39  cmp     esi, 2
0x18000da3c  lea     rbx, aError; "Error"
0x18000da43  lea     rax, aInfo; "Info"
0x18000da4a  cmovnz  rbx, rax
0x18000da4e  lea     rcx, [rsp+0B70h+SystemTime+8]; lpSystemTime
0x18000da53  call    cs:__imp_GetLocalTime
0x18000da59  movzx   ecx, word ptr [rsp+0B70h+SystemTime+12h]
0x18000da5e  movzx   edx, word ptr [rsp+0B70h+SystemTime+10h]
0x18000da63  movzx   r8d, word ptr [rsp+0B70h+SystemTime+0Eh]
0x18000da69  movzx   eax, word ptr [rsp+0B70h+SystemTime+14h]
0x18000da6e  movzx   r10d, word ptr [rsp+0B70h+SystemTime+0Ah]
0x18000da74  movzx   r9d, word ptr [rsp+0B70h+SystemTime+8]
0x18000da7a  mov     [rsp+0B70h+var_B28], rbx
0x18000da7f  mov     dword ptr [rsp+0B70h+var_B30], eax
0x18000da83  mov     dword ptr [rsp+0B70h+lpUsedDefaultChar], ecx
0x18000da87  lea     rcx, [rbp+0A70h+WideCharStr]; unsigned __int16 *
0x18000da8b  mov     dword ptr [rsp+0B70h+hTemplateFile], edx
0x18000da8f  mov     edx, 50h ; 'P'; unsigned __int64
0x18000da94  mov     [rsp+0B70h+dwFlagsAndAttributes], r8d
0x18000da99  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d, %-8s      "...
0x18000daa0  mov     [rsp+0B70h+dwCreationDisposition], r10d
0x18000daa5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000daaa  mov     r8, [rbp+0A70h+Format]; Format
0x18000dab1  lea     r9, [rbp+0A70h+Args]; Args
0x18000dab8  mov     ebx, 1F3h
0x18000dabd  lea     rcx, [rbp+0A70h+Buffer]; Buffer
0x18000dac4  mov     edx, ebx; BufferCount
0x18000dac6  call    _vsnwprintf
0x18000dacb  test    eax, eax
0x18000dacd  js      short loc_18000DAD3
0x18000dacf  cmp     eax, ebx
0x18000dad1  jb      short loc_18000DADB
0x18000dad3  mov     [rbp+0A70h+var_4A], r12w
0x18000dadb  mov     r8d, 105h; nSize
0x18000dae1  lea     rdx, [rbp+0A70h+Dst]; lpDst
0x18000dae8  lea     rcx, Src; "%LOCALAPPDATA%\\Microsoft\\Windows\\Win"...
0x18000daef  call    cs:__imp_ExpandEnvironmentStringsW
0x18000daf5  mov     esi, 80h
0x18000dafa  mov     [rsp+0B70h+hTemplateFile], r12; hTemplateFile
0x18000daff  mov     [rsp+0B70h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18000db03  lea     rcx, [rbp+0A70h+Dst]; lpFileName
0x18000db0a  xor     r9d, r9d; lpSecurityAttributes
0x18000db0d  mov     [rsp+0B70h+dwCreationDisposition], 4; dwCreationDisposition
0x18000db15  lea     edx, [rsi-7Ah]; dwDesiredAccess
0x18000db18  lea     r8d, [rsi-7Fh]; dwShareMode
0x18000db1c  call    cs:__imp_CreateFileW
0x18000db22  mov     rbx, rax
0x18000db25  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000db29  jnz     short loc_18000DB89
0x18000db2b  mov     r8d, 104h; nSize
0x18000db31  lea     rdx, [rbp+0A70h+PathName]; lpDst
0x18000db38  lea     rcx, aLocalappdataMi_0; "%LOCALAPPDATA%\\Microsoft\\Windows\\Win"...
0x18000db3f  call    cs:__imp_ExpandEnvironmentStringsW
0x18000db45  xor     edx, edx; lpSecurityAttributes
0x18000db47  lea     rcx, [rbp+0A70h+PathName]; lpPathName
0x18000db4e  call    cs:__imp_CreateDirectoryW
0x18000db54  mov     [rsp+0B70h+hTemplateFile], r12; hTemplateFile
0x18000db59  lea     edx, [rsi-7Ah]; dwDesiredAccess
0x18000db5c  mov     [rsp+0B70h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18000db60  lea     r8d, [rsi-7Fh]; dwShareMode
0x18000db64  xor     r9d, r9d; lpSecurityAttributes
0x18000db67  mov     [rsp+0B70h+dwCreationDisposition], 4; dwCreationDisposition
0x18000db6f  lea     rcx, [rbp+0A70h+Dst]; lpFileName
0x18000db76  call    cs:__imp_CreateFileW
0x18000db7c  mov     rbx, rax
0x18000db7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000db83  jz      loc_18000DCBB
0x18000db89  mov     r9d, 2; dwMoveMethod
0x18000db8f  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000db92  xor     edx, edx; lDistanceToMove
0x18000db94  mov     rcx, rbx; hFile
0x18000db97  call    cs:__imp_SetFilePointer
0x18000db9d  cmp     eax, 0FFFFFFFFh
0x18000dba0  jz      loc_18000DCB2
0x18000dba6  mov     [rsp+0B70h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000dbab  lea     rax, [rbp+0A70h+MultiByteStr]
0x18000dbaf  mov     [rsp+0B70h+hTemplateFile], r12; lpDefaultChar
0x18000dbb4  lea     r8, [rbp+0A70h+WideCharStr]; lpWideCharStr
0x18000dbb8  mov     [rsp+0B70h+dwFlagsAndAttributes], 1F4h; cbMultiByte
0x18000dbc0  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000dbc4  mov     edx, 400h; dwFlags
0x18000dbc9  mov     qword ptr [rsp+0B70h+dwCreationDisposition], rax; lpMultiByteStr
0x18000dbce  xor     ecx, ecx; CodePage
0x18000dbd0  call    cs:__imp_WideCharToMultiByte
0x18000dbd6  mov     esi, 7FFFFFFFh
0x18000dbdb  lea     rax, [rbp+0A70h+MultiByteStr]
0x18000dbdf  mov     edx, esi
0x18000dbe1  cmp     [rax], r12b
0x18000dbe4  jz      short loc_18000DBEF
0x18000dbe6  inc     rax
0x18000dbe9  sub     rdx, 1
0x18000dbed  jnz     short loc_18000DBE1
0x18000dbef  mov     rax, rdx
0x18000dbf2  mov     qword ptr [rsp+0B70h+dwCreationDisposition], r12; lpOverlapped
0x18000dbf7  mov     ecx, esi
0x18000dbf9  lea     r9, [rsp+0B70h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000dbfe  sub     ecx, edx
0x18000dc00  neg     rax
0x18000dc03  sbb     r8d, r8d
0x18000dc06  and     r8d, ecx
0x18000dc09  mov     rcx, rbx; hFile
0x18000dc0c  neg     rdx
0x18000dc0f  lea     rdx, [rbp+0A70h+MultiByteStr]; lpBuffer
0x18000dc13  sbb     eax, eax
0x18000dc15  and     r8d, eax; nNumberOfBytesToWrite
0x18000dc18  call    cs:__imp_WriteFile
0x18000dc1e  mov     [rsp+0B70h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000dc23  lea     rax, [rbp+0A70h+MultiByteStr]
0x18000dc27  mov     [rsp+0B70h+hTemplateFile], r12; lpDefaultChar
0x18000dc2c  lea     r8, [rbp+0A70h+Buffer]; lpWideCharStr
0x18000dc33  mov     [rsp+0B70h+dwFlagsAndAttributes], 1F4h; cbMultiByte
0x18000dc3b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000dc3f  mov     edx, 400h; dwFlags
0x18000dc44  mov     qword ptr [rsp+0B70h+dwCreationDisposition], rax; lpMultiByteStr
0x18000dc49  xor     ecx, ecx; CodePage
0x18000dc4b  call    cs:__imp_WideCharToMultiByte
0x18000dc51  mov     rdx, rsi
0x18000dc54  lea     rax, [rbp+0A70h+MultiByteStr]
0x18000dc58  cmp     [rax], r12b
0x18000dc5b  jz      short loc_18000DC66
0x18000dc5d  inc     rax
0x18000dc60  sub     rdx, 1
0x18000dc64  jnz     short loc_18000DC58
0x18000dc66  sub     esi, edx
0x18000dc68  mov     qword ptr [rsp+0B70h+dwCreationDisposition], r12; lpOverlapped
0x18000dc6d  mov     rax, rdx
0x18000dc70  lea     r9, [rsp+0B70h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000dc75  neg     rax
0x18000dc78  sbb     ecx, ecx
0x18000dc7a  and     ecx, esi
0x18000dc7c  neg     rdx
0x18000dc7f  lea     rdx, [rbp+0A70h+MultiByteStr]; lpBuffer
0x18000dc83  sbb     r8d, r8d
0x18000dc86  and     r8d, ecx; nNumberOfBytesToWrite
0x18000dc89  mov     rcx, rbx; hFile
0x18000dc8c  call    cs:__imp_WriteFile
0x18000dc92  lea     r9, [rsp+0B70h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000dc97  mov     qword ptr [rsp+0B70h+dwCreationDisposition], r12; lpOverlapped
0x18000dc9c  mov     r8d, 2; nNumberOfBytesToWrite
0x18000dca2  lea     rdx, asc_1800275F4; "\r\n"
0x18000dca9  mov     rcx, rbx; hFile
0x18000dcac  call    cs:__imp_WriteFile
0x18000dcb2  mov     rcx, rbx; hObject
0x18000dcb5  call    cs:__imp_CloseHandle
0x18000dcbb  mov     ecx, r15d; dwErrCode
0x18000dcbe  call    cs:__imp_SetLastError
0x18000dcc4  test    edi, edi
0x18000dcc6  jz      short loc_18000DCD1
0x18000dcc8  mov     rcx, r14; lpCriticalSection
0x18000dccb  call    cs:__imp_LeaveCriticalSection
0x18000dcd1  mov     rcx, [rbp+0A70h+var_40]
0x18000dcd8  xor     rcx, rsp; StackCookie
0x18000dcdb  call    __security_check_cookie
0x18000dce0  add     rsp, 0B40h
0x18000dce7  pop     r15
0x18000dce9  pop     r14
0x18000dceb  pop     r12
0x18000dced  pop     rdi
0x18000dcee  pop     rsi
0x18000dcef  pop     rbx
0x18000dcf0  pop     rbp
0x18000dcf1  retn
```
