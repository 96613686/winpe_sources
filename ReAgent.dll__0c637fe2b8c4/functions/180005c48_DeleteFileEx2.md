# DeleteFileEx2

- ea: `0x180005c48`
- end: `0x18000611a`
- name: `DeleteFileEx2`
- size: `1234`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180042324`
- `0x1800469e0`

## callees

- `0x180005c48`
- `0x1800061c0`
- `0x180006250`
- `0x180006578`
- `0x1800067f0`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005de6`
- `msvcrt!_wcsicmp` at `0x180005de6`
- `ntdll!RtlNtStatusToDosError` at `0x180005e97`
- `ntdll!RtlNtStatusToDosError` at `0x180005ed2`
- `ntdll!RtlNtStatusToDosError` at `0x180005e97`
- `ntdll!RtlNtStatusToDosError` at `0x180005ed2`
- `ntdll!NtSetInformationFile` at `0x180005e8b`
- `ntdll!NtSetInformationFile` at `0x180005ebf`
- `ntdll!NtSetInformationFile` at `0x180005e8b`
- `ntdll!NtSetInformationFile` at `0x180005ebf`
- `KERNEL32!GetLastError` at `0x180005f7b`
- `KERNEL32!GetLastError` at `0x180005fab`
- `KERNEL32!GetLastError` at `0x180005fe6`
- `KERNEL32!GetLastError` at `0x180005ff5`
- `KERNEL32!GetLastError` at `0x180006027`
- `KERNEL32!GetLastError` at `0x180006041`
- `KERNEL32!GetLastError` at `0x180006087`
- `KERNEL32!GetLastError` at `0x1800060c4`
- `KERNEL32!GetLastError` at `0x180005f7b`
- `KERNEL32!GetLastError` at `0x180005fab`
- `KERNEL32!GetLastError` at `0x180005fe6`
- `KERNEL32!GetLastError` at `0x180005ff5`
- `KERNEL32!GetLastError` at `0x180006027`
- `KERNEL32!GetLastError` at `0x180006041`
- `KERNEL32!GetLastError` at `0x180006087`
- `KERNEL32!GetLastError` at `0x1800060c4`
- `KERNEL32!HeapFree` at `0x180005e17`
- `KERNEL32!HeapFree` at `0x180005fde`
- `KERNEL32!HeapFree` at `0x18000607f`
- `KERNEL32!HeapFree` at `0x1800060bc`
- `KERNEL32!HeapFree` at `0x180005e17`
- `KERNEL32!HeapFree` at `0x180005fde`
- `KERNEL32!HeapFree` at `0x18000607f`
- `KERNEL32!HeapFree` at `0x1800060bc`
- `KERNEL32!HeapAlloc` at `0x180005d7c`
- `KERNEL32!HeapAlloc` at `0x180005d7c`
- `KERNEL32!GetProcessHeap` at `0x180005d6a`
- `KERNEL32!GetProcessHeap` at `0x180005e09`
- `KERNEL32!GetProcessHeap` at `0x180005fd0`
- `KERNEL32!GetProcessHeap` at `0x180006071`
- `KERNEL32!GetProcessHeap` at `0x1800060ae`
- `KERNEL32!GetProcessHeap` at `0x180005d6a`
- `KERNEL32!GetProcessHeap` at `0x180005e09`
- `KERNEL32!GetProcessHeap` at `0x180005fd0`
- `KERNEL32!GetProcessHeap` at `0x180006071`
- `KERNEL32!GetProcessHeap` at `0x1800060ae`
- `KERNEL32!SetLastError` at `0x1800060ed`
- `KERNEL32!SetLastError` at `0x1800060ed`
- `KERNEL32!CreateFileW` at `0x180005ccb`
- `KERNEL32!CreateFileW` at `0x180005f4d`
- `KERNEL32!CreateFileW` at `0x180005ccb`
- `KERNEL32!CreateFileW` at `0x180005f4d`
- `KERNEL32!CloseHandle` at `0x180005fa3`
- `KERNEL32!CloseHandle` at `0x18000601f`
- `KERNEL32!CloseHandle` at `0x180005fa3`
- `KERNEL32!CloseHandle` at `0x18000601f`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180005d22`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180005d22`
- `KERNEL32!FindFirstFileNameW` at `0x180005dcd`
- `KERNEL32!FindFirstFileNameW` at `0x180005dcd`
- `KERNEL32!FindClose` at `0x180005e22`
- `KERNEL32!FindClose` at `0x180005e22`
- `KERNEL32!GetFileInformationByHandle` at `0x180005d05`
- `KERNEL32!GetFileInformationByHandle` at `0x180005d05`
- `KERNEL32!SetFileInformationByHandle` at `0x180005d46`
- `KERNEL32!SetFileInformationByHandle` at `0x180005f71`
- `KERNEL32!SetFileInformationByHandle` at `0x180005d46`
- `KERNEL32!SetFileInformationByHandle` at `0x180005f71`
- `KERNEL32!DeleteFileW` at `0x180006037`
- `KERNEL32!DeleteFileW` at `0x180006037`
- `KERNEL32!FindNextFileNameW` at `0x180005dff`
- `KERNEL32!FindNextFileNameW` at `0x180005dff`

## string_xrefs

- `0x180005e2a`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x180005e4f`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x180005ee5`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x180005f0d`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x180005f84`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x180005fb4`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180006052`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180005fec`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x180005ffb`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x180006049`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x180006090`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x1800060cd`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall DeleteFileEx2(__int64 a1)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // r12
  const WCHAR *v4; // rax
  WCHAR *v5; // rdi
  HANDLE FileW; // r14
  DWORD LastError; // ebx
  int v8; // eax
  ULONG v9; // eax
  int v10; // eax
  DWORD v11; // eax
  const wchar_t *v12; // r8
  DWORD v13; // eax
  const wchar_t *v14; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-99h]
  __int64 dwCreationDispositiona; // [rsp+20h] [rbp-99h]
  char v20[4]; // [rsp+40h] [rbp-79h] BYREF
  DWORD StringLength; // [rsp+44h] [rbp-75h] BYREF
  __int64 v22; // [rsp+48h] [rbp-71h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  _OWORD v24[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v25; // [rsp+88h] [rbp-31h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-29h] BYREF

  v2 = (unsigned __int16 *)FormLongPathName();
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_30;
  }
  v22 = 0;
  v4 = (const WCHAR *)PrepareUnicodePathEx(v2);
  v5 = (WCHAR *)v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v3, LastError);
    goto LABEL_28;
  }
  FileW = CreateFileW(v4, 0x10180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v13 = GetLastError();
    LastError = v13;
    if ( v13 == 5 )
    {
      if ( DeleteFileW(v5) )
        goto LABEL_26;
      v13 = GetLastError();
      LastError = v13;
      v14 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
    }
    else
    {
      v14 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    }
    LODWORD(dwCreationDisposition) = v13;
    LibLog(&g_WdsLibLog, 50331648, v14, v5, dwCreationDisposition);
    goto LABEL_26;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  v25 = 0;
  memset(v24, 0, sizeof(v24));
  if ( GetFileInformationByHandle(FileW, &FileInformation)
    && GetFileInformationByHandleEx(FileW, FileBasicInfo, v24, 0x28u) )
  {
    LODWORD(v25) = 0x2000;
    if ( SetFileInformationByHandle(FileW, FileBasicInfo, v24, 0x28u) )
    {
      LastError = 0;
      if ( FileInformation.nNumberOfLinks > 1 )
        LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v5);
      v20[0] = 1;
      IoStatusBlock = 0;
      v8 = NtSetInformationFile(FileW, &IoStatusBlock, v20, 1u, FileDispositionInformation);
      if ( v8 < 0 )
      {
        v9 = RtlNtStatusToDosError(v8);
        StringLength = 1;
        LastError = v9;
        v10 = NtSetInformationFile(FileW, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
        if ( v10 >= 0 )
        {
          LastError = 0;
        }
        else
        {
          if ( v10 != -1073741821 )
            LastError = RtlNtStatusToDosError(v10);
          if ( LastError )
          {
            LODWORD(dwCreationDispositiona) = LastError;
            LibLog(
              &g_WdsLibLog,
              50331648,
              L"DeleteFileEx: Unable to remove [%s]; GLE = 0x%x",
              v5,
              dwCreationDispositiona);
          }
        }
      }
      goto LABEL_20;
    }
    v11 = GetLastError();
    v12 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
  }
  else
  {
    v11 = GetLastError();
    v12 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
  }
  LODWORD(dwCreationDisposition) = v11;
  LastError = v11;
  LibLog(&g_WdsLibLog, 50331648, v12, v5, dwCreationDisposition);
LABEL_20:
  CloseHandle(FileW);
LABEL_26:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v5);
LABEL_28:
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v3);
LABEL_30:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180005c48  push    rbp
0x180005c4a  push    rbx
0x180005c4b  push    rsi
0x180005c4c  push    rdi
0x180005c4d  push    r12
0x180005c4f  push    r13
0x180005c51  push    r14
0x180005c53  push    r15
0x180005c55  lea     rbp, [rsp-1Fh]
0x180005c5a  sub     rsp, 0D8h
0x180005c61  mov     rax, cs:__security_cookie
0x180005c68  xor     rax, rsp
0x180005c6b  mov     [rbp+57h+var_48], rax
0x180005c6f  mov     rdi, rcx
0x180005c72  call    FormLongPathName
0x180005c77  mov     r12, rax
0x180005c7a  test    rax, rax
0x180005c7d  jz      loc_1800060C4
0x180005c83  lea     rdx, [rbp+57h+var_C8]
0x180005c87  mov     [rbp+57h+var_C8], 0
0x180005c8f  mov     rcx, rax; unsigned __int16 *
0x180005c92  call    PrepareUnicodePathEx
0x180005c97  mov     rdi, rax
0x180005c9a  test    rax, rax
0x180005c9d  jz      loc_180006087
0x180005ca3  xor     r9d, r9d; lpSecurityAttributes
0x180005ca6  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x180005caf  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180005cb7  mov     edx, 10180h; dwDesiredAccess
0x180005cbc  mov     rcx, rax; lpFileName
0x180005cbf  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180005cc7  lea     r8d, [r9+7]; dwShareMode
0x180005ccb  call    cs:__imp_CreateFileW
0x180005cd1  mov     r14, rax
0x180005cd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005cd8  jz      loc_180006027
0x180005cde  xorps   xmm0, xmm0
0x180005ce1  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180005ce5  xor     eax, eax
0x180005ce7  mov     rcx, r14; hFile
0x180005cea  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180005cee  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180005cf1  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180005cf5  mov     [rbp+57h+var_88], rax
0x180005cf9  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180005cfd  movups  [rbp+57h+var_A8], xmm0
0x180005d01  movups  [rbp+57h+var_98], xmm0
0x180005d05  call    cs:__imp_GetFileInformationByHandle
0x180005d0b  test    eax, eax
0x180005d0d  jz      loc_180005FF5
0x180005d13  mov     r9d, 28h ; '('; dwBufferSize
0x180005d19  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180005d1d  xor     edx, edx; FileInformationClass
0x180005d1f  mov     rcx, r14; hFile
0x180005d22  call    cs:__imp_GetFileInformationByHandleEx
0x180005d28  test    eax, eax
0x180005d2a  jz      loc_180005FF5
0x180005d30  mov     r9d, 28h ; '('; dwBufferSize
0x180005d36  mov     dword ptr [rbp+57h+var_88], 2000h
0x180005d3d  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180005d41  xor     edx, edx; FileInformationClass
0x180005d43  mov     rcx, r14; hFile
0x180005d46  call    cs:__imp_SetFileInformationByHandle
0x180005d4c  test    eax, eax
0x180005d4e  jz      loc_180005FE6
0x180005d54  xor     ebx, ebx
0x180005d56  cmp     [rbp+57h+var_C8], rbx
0x180005d5a  jz      loc_180005E44
0x180005d60  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180005d64  jbe     loc_180005E44
0x180005d6a  call    cs:__imp_GetProcessHeap
0x180005d70  lea     edx, [rbx+8]; dwFlags
0x180005d73  mov     r8d, 10000h; dwBytes
0x180005d79  mov     rcx, rax; hHeap
0x180005d7c  call    cs:__imp_HeapAlloc
0x180005d82  mov     rsi, rax
0x180005d85  test    rax, rax
0x180005d88  jz      loc_180005E2A
0x180005d8e  mov     rcx, [rbp+57h+var_C8]
0x180005d92  mov     r13d, 8000h
0x180005d98  sub     rcx, rdi
0x180005d9b  mov     r8, rdi; pszSrc
0x180005d9e  sar     rcx, 1
0x180005da1  mov     edx, r13d; cchDest
0x180005da4  mov     r11d, ecx
0x180005da7  mov     r9d, ecx; cchToCopy
0x180005daa  mov     rcx, rax; pszDest
0x180005dad  call    StringCchCopyNW
0x180005db2  lea     rax, [rsi+r11*2]
0x180005db6  sub     r13d, r11d
0x180005db9  mov     r9, rax; LinkName
0x180005dbc  mov     [rbp+57h+LinkName], rax
0x180005dc0  lea     r8, [rbp+57h+StringLength]; StringLength
0x180005dc4  mov     [rbp+57h+StringLength], r13d
0x180005dc8  xor     edx, edx; dwFlags
0x180005dca  mov     rcx, rdi; lpFileName
0x180005dcd  call    cs:__imp_FindFirstFileNameW
0x180005dd3  mov     r15, rax
0x180005dd6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005dda  jz      loc_180005E67
0x180005de0  mov     rdx, rdi; String2
0x180005de3  mov     rcx, rsi; String1
0x180005de6  call    cs:__imp__wcsicmp
0x180005dec  mov     [rbp+57h+StringLength], r13d
0x180005df0  test    eax, eax
0x180005df2  jnz     short loc_180005E1F
0x180005df4  mov     r8, [rbp+57h+LinkName]; LinkName
0x180005df8  lea     rdx, [rbp+57h+StringLength]; StringLength
0x180005dfc  mov     rcx, r15; hFindStream
0x180005dff  call    cs:__imp_FindNextFileNameW
0x180005e05  test    eax, eax
0x180005e07  jnz     short loc_180005DE0
0x180005e09  call    cs:__imp_GetProcessHeap
0x180005e0f  mov     r8, rsi; lpMem
0x180005e12  xor     edx, edx; dwFlags
0x180005e14  mov     rcx, rax; hHeap
0x180005e17  call    cs:__imp_HeapFree
0x180005e1d  xor     esi, esi
0x180005e1f  mov     rcx, r15; hFindFile
0x180005e22  call    cs:__imp_FindClose
0x180005e28  jmp     short loc_180005E67
0x180005e2a  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to allocate hardli"...
0x180005e31  mov     edx, 3000000h
0x180005e36  lea     rcx, g_WdsLibLog
0x180005e3d  call    LibLog
0x180005e42  jmp     short loc_180005E67
0x180005e44  xor     esi, esi
0x180005e46  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180005e4a  jbe     short loc_180005E67
0x180005e4c  mov     r9, rdi
0x180005e4f  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x180005e56  mov     edx, 3000000h
0x180005e5b  lea     rcx, g_WdsLibLog
0x180005e62  call    LibLog
0x180005e67  xorps   xmm0, xmm0
0x180005e6a  mov     [rbp+57h+var_D0], 1
0x180005e6e  mov     r9d, 1; Length
0x180005e74  mov     dword ptr [rsp+110h+dwCreationDisposition], 0Dh; FileInformationClass
0x180005e7c  lea     r8, [rbp+57h+var_D0]; FileInformation
0x180005e80  mov     rcx, r14; FileHandle
0x180005e83  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180005e87  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180005e8b  call    cs:__imp_NtSetInformationFile
0x180005e91  test    eax, eax
0x180005e93  jns     short loc_180005F01
0x180005e95  mov     ecx, eax; Status
0x180005e97  call    cs:__imp_RtlNtStatusToDosError
0x180005e9d  mov     r9d, 4; Length
0x180005ea3  mov     [rbp+57h+StringLength], 1
0x180005eaa  lea     r8, [rbp+57h+StringLength]; FileInformation
0x180005eae  mov     dword ptr [rsp+110h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180005eb6  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180005eba  mov     rcx, r14; FileHandle
0x180005ebd  mov     ebx, eax
0x180005ebf  call    cs:__imp_NtSetInformationFile
0x180005ec5  test    eax, eax
0x180005ec7  jns     short loc_180005EFF
0x180005ec9  cmp     eax, 0C0000003h
0x180005ece  jz      short loc_180005EDA
0x180005ed0  mov     ecx, eax; Status
0x180005ed2  call    cs:__imp_RtlNtStatusToDosError
0x180005ed8  mov     ebx, eax
0x180005eda  test    ebx, ebx
0x180005edc  jz      short loc_180005F01
0x180005ede  mov     r9, rdi
0x180005ee1  mov     dword ptr [rsp+110h+dwCreationDisposition], ebx
0x180005ee5  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x180005eec  mov     edx, 3000000h
0x180005ef1  lea     rcx, g_WdsLibLog
0x180005ef8  call    LibLog
0x180005efd  jmp     short loc_180005F01
0x180005eff  xor     ebx, ebx
0x180005f01  test    rsi, rsi
0x180005f04  jz      loc_18000601C
0x180005f0a  mov     r9, rsi
0x180005f0d  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x180005f14  mov     edx, 4000000h
0x180005f19  lea     rcx, g_WdsLibLog
0x180005f20  call    LibLog
0x180005f25  xor     r9d, r9d; lpSecurityAttributes
0x180005f28  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x180005f31  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180005f39  mov     edx, 100h; dwDesiredAccess
0x180005f3e  mov     rcx, rsi; lpFileName
0x180005f41  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180005f49  lea     r8d, [r9+7]; dwShareMode
0x180005f4d  call    cs:__imp_CreateFileW
0x180005f53  mov     r15, rax
0x180005f56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005f5a  jz      short loc_180005FAB
0x180005f5c  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x180005f5f  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180005f63  mov     dword ptr [rbp+57h+var_88], ecx
0x180005f66  mov     r9d, 28h ; '('; dwBufferSize
0x180005f6c  mov     rcx, rax; hFile
0x180005f6f  xor     edx, edx; FileInformationClass
0x180005f71  call    cs:__imp_SetFileInformationByHandle
0x180005f77  test    eax, eax
0x180005f79  jnz     short loc_180005FA0
0x180005f7b  call    cs:__imp_GetLastError
0x180005f81  mov     r9, rsi
0x180005f84  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x180005f8b  lea     rcx, g_WdsLibLog
0x180005f92  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180005f96  mov     edx, 3000000h
0x180005f9b  call    LibLog
0x180005fa0  mov     rcx, r15; hObject
0x180005fa3  call    cs:__imp_CloseHandle
0x180005fa9  jmp     short loc_180005FD0
0x180005fab  call    cs:__imp_GetLastError
0x180005fb1  mov     r9, rsi
0x180005fb4  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180005fbb  lea     rcx, g_WdsLibLog
0x180005fc2  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180005fc6  mov     edx, 3000000h
0x180005fcb  call    LibLog
0x180005fd0  call    cs:__imp_GetProcessHeap
0x180005fd6  mov     r8, rsi; lpMem
0x180005fd9  xor     edx, edx; dwFlags
0x180005fdb  mov     rcx, rax; hHeap
0x180005fde  call    cs:__imp_HeapFree
0x180005fe4  jmp     short loc_18000601C
0x180005fe6  call    cs:__imp_GetLastError
0x180005fec  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x180005ff3  jmp     short loc_180006002
0x180005ff5  call    cs:__imp_GetLastError
0x180005ffb  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to get information"...
0x180006002  mov     r9, rdi
0x180006005  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180006009  mov     edx, 3000000h
0x18000600e  lea     rcx, g_WdsLibLog
0x180006015  mov     ebx, eax
0x180006017  call    LibLog
0x18000601c  mov     rcx, r14; hObject
0x18000601f  call    cs:__imp_CloseHandle
0x180006025  jmp     short loc_180006071
0x180006027  call    cs:__imp_GetLastError
0x18000602d  mov     ebx, eax
0x18000602f  cmp     eax, 5
0x180006032  jnz     short loc_180006052
0x180006034  mov     rcx, rdi; lpFileName
0x180006037  call    cs:__imp_DeleteFileW
0x18000603d  test    eax, eax
0x18000603f  jnz     short loc_180006071
0x180006041  call    cs:__imp_GetLastError
0x180006047  mov     ebx, eax
0x180006049  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to delete [%s]; GL"...
0x180006050  jmp     short loc_180006059
0x180006052  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180006059  mov     r9, rdi
0x18000605c  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180006060  mov     edx, 3000000h
0x180006065  lea     rcx, g_WdsLibLog
0x18000606c  call    LibLog
0x180006071  call    cs:__imp_GetProcessHeap
0x180006077  mov     r8, rdi; lpMem
0x18000607a  xor     edx, edx; dwFlags
0x18000607c  mov     rcx, rax; hHeap
0x18000607f  call    cs:__imp_HeapFree
0x180006085  jmp     short loc_1800060AE
0x180006087  call    cs:__imp_GetLastError
0x18000608d  mov     r9, r12
0x180006090  lea     r8, aDeletefileexUn_3; "DeleteFileEx: Unable to prepare Unicode"...
0x180006097  lea     rcx, g_WdsLibLog
0x18000609e  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x1800060a2  mov     edx, 3000000h
0x1800060a7  mov     ebx, eax
0x1800060a9  call    LibLog
0x1800060ae  call    cs:__imp_GetProcessHeap
0x1800060b4  mov     r8, r12; lpMem
0x1800060b7  xor     edx, edx; dwFlags
0x1800060b9  mov     rcx, rax; hHeap
0x1800060bc  call    cs:__imp_HeapFree
0x1800060c2  jmp     short loc_1800060EB
0x1800060c4  call    cs:__imp_GetLastError
0x1800060ca  mov     r9, rdi
0x1800060cd  lea     r8, aDeletefileexUn_1; "DeleteFileEx: Unable to form long path "...
0x1800060d4  lea     rcx, g_WdsLibLog
0x1800060db  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x1800060df  mov     edx, 3000000h
0x1800060e4  mov     ebx, eax
0x1800060e6  call    LibLog
0x1800060eb  mov     ecx, ebx; dwErrCode
0x1800060ed  call    cs:__imp_SetLastError
0x1800060f3  xor     eax, eax
0x1800060f5  test    ebx, ebx
0x1800060f7  setz    al
0x1800060fa  mov     rcx, [rbp+57h+var_48]
0x1800060fe  xor     rcx, rsp; StackCookie
0x180006101  call    __security_check_cookie
0x180006106  add     rsp, 0D8h
0x18000610d  pop     r15
0x18000610f  pop     r14
0x180006111  pop     r13
0x180006113  pop     r12
0x180006115  pop     rdi
0x180006116  pop     rsi
0x180006117  pop     rbx
0x180006118  pop     rbp
0x180006119  retn
  ... truncated ...
```
