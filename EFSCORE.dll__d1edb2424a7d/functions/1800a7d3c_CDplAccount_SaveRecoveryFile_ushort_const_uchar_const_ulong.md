# CDplAccount::SaveRecoveryFile(ushort const *,uchar const *,ulong)

- ea: `0x1800a7d3c`
- end: `0x1800a8493`
- name: `?SaveRecoveryFile@CDplAccount@@AEAAJPEBGPEBEK@Z`
- size: `1879`
- prototype: `__int64 __fastcall(CDplServiceImpl **this, LPCWSTR lpNewFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800a5bdc`

## callees

- `0x180005045`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800920f8`
- `0x180097238`
- `0x1800a1d74`
- `0x1800a673c`
- `0x1800a7d3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a83e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a83e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a83f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a83f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a82b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a82b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a840f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a840f`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800a8187`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800a8187`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a80d5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a80d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a7ecd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8031`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a7ecd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8031`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a822e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a8294`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a8436`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a822e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a8294`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a8436`

## pseudocode

```c
__int64 __fastcall CDplAccount::SaveRecoveryFile(
        CDplServiceImpl **this,
        LPCWSTR lpNewFileName,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite)
{
  __int64 v8; // rdi
  int v9; // r13d
  int v10; // ecx
  int v11; // ecx
  unsigned int FileProtectionInfo; // ebx
  CDplAccount *v13; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  int v16; // ecx
  int v17; // ecx
  signed int v18; // eax
  int v19; // r14d
  int v20; // ecx
  signed int v21; // eax
  int v22; // ecx
  signed int v23; // eax
  signed int v24; // eax
  CDplAccount *v25; // rcx
  CDplAccount *v26; // rcx
  void *v27; // rsi
  HANDLE ProcessHeap; // rax
  char dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int *dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  char dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+40h] [rbp-C0h]
  int v34; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR NewFileName[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  v8 = -1;
  NumberOfBytesWritten = 0;
  v33 = 0;
  v34 = 0;
  v9 = 0;
  lpMem = 0;
  fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 36, 111);
  if ( !lpNewFileName )
  {
    dwCreationDisposition = 113;
LABEL_3:
    FileProtectionInfo = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 36, dwCreationDisposition);
    goto LABEL_49;
  }
  if ( !lpBuffer )
  {
    dwCreationDisposition = 114;
    goto LABEL_3;
  }
  if ( !nNumberOfBytesToWrite )
  {
    dwCreationDisposition = 118;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 128);
  FileProtectionInfo = CDplService::StringCchConcat(FileName, 0x104u, lpNewFileName, L".new", 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              FileProtectionInfo,
              36,
              128) < 0 )
  {
LABEL_49:
    v19 = 0;
    goto LABEL_50;
  }
  FileW = CreateFileW(FileName, 0x1F01FFu, 0, 0, 2u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    FileProtectionInfo = LastError;
    if ( LastError > 0 )
      FileProtectionInfo = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, FileProtectionInfo, 36, 140);
    goto LABEL_49;
  }
  CloseHandle(FileW);
  v8 = -1;
  v9 = 1;
  fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 154);
  FileProtectionInfo = CDplAccount::ProtectFileOrFolder((CDplAccount *)this, FileName);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              FileProtectionInfo,
              36,
              154) < 0
    || (fnEfsLogTrace1Strings((_DWORD)v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 163),
        FileProtectionInfo = CDplServiceImpl::GetFileProtectionInfo(
                               this[6],
                               FileName,
                               &v34,
                               (unsigned __int16 **)&lpMem,
                               dwCreationDispositionb),
        (int)fnEfsLogTrace1String1Dword(
               g_hPublisher,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
               (unsigned int)&sourceString,
               FileProtectionInfo,
               36,
               163) < 0) )
  {
LABEL_22:
    v19 = 0;
    goto LABEL_50;
  }
  if ( !v34 || !lpMem )
  {
    dwCreationDispositiona = -89;
    goto LABEL_29;
  }
  v8 = (__int64)CreateFileW(FileName, 0x1F01FFu, 3u, 0, 3u, 0x80u, 0);
  if ( v8 == -1 )
  {
    fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 184);
    v18 = GetLastError();
    FileProtectionInfo = v18;
    if ( v18 > 0 )
      FileProtectionInfo = (unsigned __int16)v18 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                FileProtectionInfo,
                36,
                184) < 0 )
      goto LABEL_22;
  }
  if ( !WriteFile((HANDLE)v8, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    fnEfsLogTrace1Strings(v20, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 193);
    v21 = GetLastError();
    FileProtectionInfo = v21;
    if ( v21 > 0 )
      FileProtectionInfo = (unsigned __int16)v21 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                FileProtectionInfo,
                36,
                193) < 0 )
    {
LABEL_30:
      v19 = v33;
      goto LABEL_50;
    }
  }
  if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
  {
    dwCreationDispositiona = -54;
LABEL_29:
    FileProtectionInfo = -2147024865;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024865, 36, dwCreationDispositiona);
    goto LABEL_30;
  }
  FlushFileBuffers((HANDLE)v8);
  if ( v8 != -1 )
  {
    CloseHandle((HANDLE)v8);
    v8 = -1;
  }
  fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 220);
  FileProtectionInfo = CDplService::StringCchConcat(NewFileName, 0x104u, lpNewFileName, L".bak", 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              FileProtectionInfo,
              36,
              220) < 0 )
    goto LABEL_30;
  if ( MoveFileExW(lpNewFileName, NewFileName, 0) )
  {
    v33 = 1;
  }
  else
  {
    v23 = GetLastError();
    FileProtectionInfo = v23;
    if ( v23 > 0 )
      FileProtectionInfo = (unsigned __int16)v23 | 0x80070000;
    if ( FileProtectionInfo != -2147024894 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, FileProtectionInfo, 36, 236);
      goto LABEL_30;
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 36, 232);
  }
  if ( !MoveFileExW(FileName, lpNewFileName, 0) )
  {
    fnEfsLogTrace1Strings((_DWORD)v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 250);
    v24 = GetLastError();
    FileProtectionInfo = v24;
    if ( v24 > 0 )
      FileProtectionInfo = (unsigned __int16)v24 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                FileProtectionInfo,
                36,
                250) < 0 )
      goto LABEL_30;
  }
  v19 = 0;
  fnEfsLogTrace1Strings((_DWORD)v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 4);
  FileProtectionInfo = CDplAccount::DeleteRecoveryFile(v25, NewFileName);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              FileProtectionInfo,
              36,
              4) >= 0 )
  {
    fnEfsLogTrace1Strings((_DWORD)v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 5);
    FileProtectionInfo = CDplAccount::DeleteRecoveryFile(v26, FileName);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                FileProtectionInfo,
                36,
                5) >= 0 )
      v9 = 0;
  }
LABEL_50:
  v27 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v27);
    lpMem = 0;
  }
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  if ( v9 )
    CDplAccount::DeleteRecoveryFile(v13, FileName);
  if ( v19 )
    MoveFileExW(NewFileName, lpNewFileName, 0);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    FileProtectionInfo,
    36,
    24);
  return FileProtectionInfo;
}

```

## disassembly

```asm
0x1800a7d3c  push    rbp
0x1800a7d3e  push    rbx
0x1800a7d3f  push    rsi
0x1800a7d40  push    rdi
0x1800a7d41  push    r12
0x1800a7d43  push    r13
0x1800a7d45  push    r14
0x1800a7d47  push    r15
0x1800a7d49  lea     rbp, [rsp-398h]
0x1800a7d51  sub     rsp, 498h
0x1800a7d58  mov     rax, cs:__security_cookie
0x1800a7d5f  xor     rax, rsp
0x1800a7d62  mov     [rbp+3D0h+var_50], rax
0x1800a7d69  mov     r15, r8
0x1800a7d6c  mov     r12, rdx
0x1800a7d6f  mov     rsi, rcx
0x1800a7d72  mov     ebx, 208h
0x1800a7d77  mov     r8d, ebx; Size
0x1800a7d7a  lea     rcx, [rsp+4D0h+FileName]; void *
0x1800a7d7f  xor     edx, edx; Val
0x1800a7d81  mov     r14d, r9d
0x1800a7d84  call    memset_0
0x1800a7d89  mov     r8d, ebx; Size
0x1800a7d8c  lea     rcx, [rbp+3D0h+NewFileName]; void *
0x1800a7d93  xor     edx, edx; Val
0x1800a7d95  call    memset_0
0x1800a7d9a  xor     ebx, ebx
0x1800a7d9c  mov     [rsp+4D0h+dwCreationDisposition], 0D6Fh
0x1800a7da4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a7da8  mov     [rsp+4D0h+NumberOfBytesWritten], ebx
0x1800a7dac  lea     r8, sourceString
0x1800a7db3  mov     [rsp+4D0h+var_490], ebx
0x1800a7db7  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800a7dbe  mov     [rsp+4D0h+var_48C], ebx
0x1800a7dc2  mov     r13d, ebx
0x1800a7dc5  mov     [rsp+4D0h+lpMem], rbx
0x1800a7dca  lea     r9d, [rdi+25h]
0x1800a7dce  call    fnEfsLogTrace1Strings
0x1800a7dd3  test    r12, r12
0x1800a7dd6  jnz     short loc_1800A7E0C
0x1800a7dd8  mov     [rsp+4D0h+dwCreationDisposition], 0D71h
0x1800a7de0  mov     ebx, 80070057h
0x1800a7de5  mov     r8d, 80070057h
0x1800a7deb  mov     rcx, cs:g_hPublisher
0x1800a7df2  lea     rdx, EFS_TRACE_ERROR
0x1800a7df9  mov     r15d, 24h ; '$'
0x1800a7dff  mov     r9d, r15d
0x1800a7e02  call    fnEfsLogTrace1
0x1800a7e07  jmp     loc_1800A83DC
0x1800a7e0c  test    r15, r15
0x1800a7e0f  jnz     short loc_1800A7E1B
0x1800a7e11  mov     [rsp+4D0h+dwCreationDisposition], 0D72h
0x1800a7e19  jmp     short loc_1800A7DE0
0x1800a7e1b  test    r14d, r14d
0x1800a7e1e  jnz     short loc_1800A7E2A
0x1800a7e20  mov     [rsp+4D0h+dwCreationDisposition], 0D76h
0x1800a7e28  jmp     short loc_1800A7DE0
0x1800a7e2a  mov     r9d, 24h ; '$'
0x1800a7e30  mov     [rsp+4D0h+dwCreationDisposition], 0D80h
0x1800a7e38  lea     r8, sourceString
0x1800a7e3f  lea     rdx, EFS_TRACE_START_EVENT
0x1800a7e46  call    fnEfsLogTrace1Strings
0x1800a7e4b  lea     r9, aNew_0; ".new"
0x1800a7e52  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rbx
0x1800a7e57  mov     r8, r12
0x1800a7e5a  lea     rcx, [rsp+4D0h+FileName]; unsigned __int16 *
0x1800a7e5f  mov     edx, 104h; unsigned int
0x1800a7e64  call    ?StringCchConcat@CDplService@@SAJPEAGKZZ; CDplService::StringCchConcat(ushort *,ulong,...)
0x1800a7e69  mov     rcx, cs:g_hPublisher
0x1800a7e70  lea     r9, sourceString
0x1800a7e77  mov     dword ptr [rsp+4D0h+hTemplateFile], 0D80h
0x1800a7e7f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a7e86  mov     [rsp+4D0h+dwFlagsAndAttributes], 24h ; '$'
0x1800a7e8e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7e95  mov     [rsp+4D0h+dwCreationDisposition], eax
0x1800a7e99  mov     ebx, eax
0x1800a7e9b  call    fnEfsLogTrace1String1Dword
0x1800a7ea0  test    eax, eax
0x1800a7ea2  js      loc_1800A83D6
0x1800a7ea8  mov     [rsp+4D0h+hTemplateFile], r13; hTemplateFile
0x1800a7ead  lea     rcx, [rsp+4D0h+FileName]; lpFileName
0x1800a7eb2  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a7eba  xor     r9d, r9d; lpSecurityAttributes
0x1800a7ebd  xor     r8d, r8d; dwShareMode
0x1800a7ec0  mov     [rsp+4D0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800a7ec8  mov     edx, 1F01FFh; dwDesiredAccess
0x1800a7ecd  call    cs:__imp_CreateFileW
0x1800a7ed3  mov     rdi, rax
0x1800a7ed6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a7eda  jnz     short loc_1800A7F01
0x1800a7edc  call    cs:__imp_GetLastError
0x1800a7ee2  mov     ebx, eax
0x1800a7ee4  test    eax, eax
0x1800a7ee6  jle     short loc_1800A7EF1
0x1800a7ee8  movzx   ebx, ax
0x1800a7eeb  or      ebx, 80070000h
0x1800a7ef1  mov     [rsp+4D0h+dwCreationDisposition], 0D8Ch
0x1800a7ef9  mov     r8d, ebx
0x1800a7efc  jmp     loc_1800A7DEB
0x1800a7f01  mov     rcx, rax; hObject
0x1800a7f04  call    cs:__imp_CloseHandle
0x1800a7f0a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a7f0e  mov     [rsp+4D0h+dwCreationDisposition], 0D9Ah
0x1800a7f16  lea     r8, sourceString
0x1800a7f1d  lea     rdx, EFS_TRACE_START_EVENT
0x1800a7f24  lea     r9d, [rdi+25h]
0x1800a7f28  lea     r13d, [rdi+2]
0x1800a7f2c  call    fnEfsLogTrace1Strings
0x1800a7f31  lea     rdx, [rsp+4D0h+FileName]; unsigned __int16 *
0x1800a7f36  mov     rcx, rsi; this
0x1800a7f39  call    ?ProtectFileOrFolder@CDplAccount@@AEAAJPEBG@Z; CDplAccount::ProtectFileOrFolder(ushort const *)
0x1800a7f3e  mov     rcx, cs:g_hPublisher
0x1800a7f45  lea     r9, sourceString
0x1800a7f4c  mov     dword ptr [rsp+4D0h+hTemplateFile], 0D9Ah
0x1800a7f54  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a7f5b  mov     [rsp+4D0h+dwFlagsAndAttributes], 24h ; '$'
0x1800a7f63  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7f6a  mov     [rsp+4D0h+dwCreationDisposition], eax
0x1800a7f6e  mov     ebx, eax
0x1800a7f70  call    fnEfsLogTrace1String1Dword
0x1800a7f75  test    eax, eax
0x1800a7f77  js      loc_1800A80AE
0x1800a7f7d  lea     r9d, [rdi+25h]
0x1800a7f81  mov     [rsp+4D0h+dwCreationDisposition], 0DA3h; int *
0x1800a7f89  lea     r8, sourceString
0x1800a7f90  lea     rdx, EFS_TRACE_START_EVENT
0x1800a7f97  call    fnEfsLogTrace1Strings
0x1800a7f9c  mov     rcx, [rsi+30h]; this
0x1800a7fa0  lea     r9, [rsp+4D0h+lpMem]; unsigned __int16 **
0x1800a7fa5  lea     r8, [rsp+4D0h+var_48C]; int *
0x1800a7faa  lea     rdx, [rsp+4D0h+FileName]; unsigned __int16 *
0x1800a7faf  call    ?GetFileProtectionInfo@CDplServiceImpl@@AEAAJPEBGPEAHPEAPEAG1@Z; CDplServiceImpl::GetFileProtectionInfo(ushort const *,int *,ushort * *,int *)
0x1800a7fb4  mov     rcx, cs:g_hPublisher
0x1800a7fbb  lea     r9, sourceString
0x1800a7fc2  mov     dword ptr [rsp+4D0h+hTemplateFile], 0DA3h
0x1800a7fca  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a7fd1  mov     [rsp+4D0h+dwFlagsAndAttributes], 24h ; '$'
0x1800a7fd9  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7fe0  mov     [rsp+4D0h+dwCreationDisposition], eax
0x1800a7fe4  mov     ebx, eax
0x1800a7fe6  call    fnEfsLogTrace1String1Dword
0x1800a7feb  test    eax, eax
0x1800a7fed  js      loc_1800A80AE
0x1800a7ff3  cmp     [rsp+4D0h+var_48C], 0
0x1800a7ff8  jz      loc_1800A83C3
0x1800a7ffe  cmp     [rsp+4D0h+lpMem], 0
0x1800a8004  jz      loc_1800A83C3
0x1800a800a  mov     [rsp+4D0h+hTemplateFile], 0; hTemplateFile
0x1800a8013  lea     r8d, [rdi+4]; dwShareMode
0x1800a8017  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a801f  lea     rcx, [rsp+4D0h+FileName]; lpFileName
0x1800a8024  xor     r9d, r9d; lpSecurityAttributes
0x1800a8027  mov     [rsp+4D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a802c  mov     edx, 1F01FFh; dwDesiredAccess
0x1800a8031  call    cs:__imp_CreateFileW
0x1800a8037  mov     rdi, rax
0x1800a803a  mov     esi, 80070000h
0x1800a803f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a8043  jnz     short loc_1800A80BE
0x1800a8045  lea     r9d, [r13+23h]
0x1800a8049  mov     [rsp+4D0h+dwCreationDisposition], 0DB8h
0x1800a8051  lea     r8, sourceString
0x1800a8058  lea     rdx, EFS_TRACE_START_EVENT
0x1800a805f  call    fnEfsLogTrace1Strings
0x1800a8064  call    cs:__imp_GetLastError
0x1800a806a  mov     ebx, eax
0x1800a806c  test    eax, eax
0x1800a806e  jle     short loc_1800A8075
0x1800a8070  movzx   ebx, ax
0x1800a8073  or      ebx, esi
0x1800a8075  mov     rcx, cs:g_hPublisher
0x1800a807c  lea     r9, sourceString
0x1800a8083  mov     dword ptr [rsp+4D0h+hTemplateFile], 0DB8h
0x1800a808b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a8092  mov     [rsp+4D0h+dwFlagsAndAttributes], 24h ; '$'
0x1800a809a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a80a1  mov     [rsp+4D0h+dwCreationDisposition], ebx
0x1800a80a5  call    fnEfsLogTrace1String1Dword
0x1800a80aa  test    eax, eax
0x1800a80ac  jns     short loc_1800A80BE
0x1800a80ae  mov     r14d, [rsp+4D0h+var_490]
0x1800a80b3  mov     r15d, 24h ; '$'
0x1800a80b9  jmp     loc_1800A83DF
0x1800a80be  lea     r9, [rsp+4D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a80c3  mov     qword ptr [rsp+4D0h+dwCreationDisposition], 0; lpOverlapped
0x1800a80cc  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800a80cf  mov     rdx, r15; lpBuffer
0x1800a80d2  mov     rcx, rdi; hFile
0x1800a80d5  call    cs:__imp_WriteFile
0x1800a80db  mov     r15d, 24h ; '$'
0x1800a80e1  test    eax, eax
0x1800a80e3  jnz     short loc_1800A814A
0x1800a80e5  mov     r9d, r15d
0x1800a80e8  mov     [rsp+4D0h+dwCreationDisposition], 0DC1h
0x1800a80f0  lea     r8, sourceString
0x1800a80f7  lea     rdx, EFS_TRACE_START_EVENT
0x1800a80fe  call    fnEfsLogTrace1Strings
0x1800a8103  call    cs:__imp_GetLastError
0x1800a8109  mov     ebx, eax
0x1800a810b  test    eax, eax
0x1800a810d  jle     short loc_1800A8114
0x1800a810f  movzx   ebx, ax
0x1800a8112  or      ebx, esi
0x1800a8114  mov     rcx, cs:g_hPublisher
0x1800a811b  lea     r9, sourceString
0x1800a8122  mov     dword ptr [rsp+4D0h+hTemplateFile], 0DC1h
0x1800a812a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a8131  mov     [rsp+4D0h+dwFlagsAndAttributes], r15d
0x1800a8136  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a813d  mov     [rsp+4D0h+dwCreationDisposition], ebx
0x1800a8141  call    fnEfsLogTrace1String1Dword
0x1800a8146  test    eax, eax
0x1800a8148  js      short loc_1800A817A
0x1800a814a  cmp     [rsp+4D0h+NumberOfBytesWritten], r14d
0x1800a814f  jz      short loc_1800A8184
0x1800a8151  mov     [rsp+4D0h+dwCreationDisposition], 0DCAh
0x1800a8159  mov     rcx, cs:g_hPublisher
0x1800a8160  mov     ebx, 8007001Fh
0x1800a8165  mov     r9d, r15d
0x1800a8168  mov     r8d, 8007001Fh
0x1800a816e  lea     rdx, EFS_TRACE_ERROR
0x1800a8175  call    fnEfsLogTrace1
0x1800a817a  mov     r14d, [rsp+4D0h+var_490]
0x1800a817f  jmp     loc_1800A83DF
0x1800a8184  mov     rcx, rdi; hFile
0x1800a8187  call    cs:__imp_FlushFileBuffers
0x1800a818d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a8191  jz      short loc_1800A81A0
0x1800a8193  mov     rcx, rdi; hObject
0x1800a8196  call    cs:__imp_CloseHandle
0x1800a819c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a81a0  mov     r14d, 0DDCh
0x1800a81a6  lea     r8, sourceString
0x1800a81ad  mov     r9d, r15d
0x1800a81b0  mov     [rsp+4D0h+dwCreationDisposition], r14d
0x1800a81b5  lea     rdx, EFS_TRACE_START_EVENT
0x1800a81bc  call    fnEfsLogTrace1Strings
0x1800a81c1  lea     r9, aBak; ".bak"
0x1800a81c8  mov     qword ptr [rsp+4D0h+dwCreationDisposition], 0
0x1800a81d1  mov     r8, r12
0x1800a81d4  lea     rcx, [rbp+3D0h+NewFileName]; unsigned __int16 *
0x1800a81db  mov     edx, 104h; unsigned int
0x1800a81e0  call    ?StringCchConcat@CDplService@@SAJPEAGKZZ; CDplService::StringCchConcat(ushort *,ulong,...)
0x1800a81e5  mov     rcx, cs:g_hPublisher
0x1800a81ec  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a81f3  mov     dword ptr [rsp+4D0h+hTemplateFile], r14d
0x1800a81f8  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a81ff  lea     r14, sourceString
0x1800a8206  mov     [rsp+4D0h+dwFlagsAndAttributes], r15d
0x1800a820b  mov     r9, r14
0x1800a820e  mov     [rsp+4D0h+dwCreationDisposition], eax
0x1800a8212  mov     ebx, eax
0x1800a8214  call    fnEfsLogTrace1String1Dword
0x1800a8219  test    eax, eax
0x1800a821b  js      loc_1800A817A
0x1800a8221  xor     r8d, r8d; dwFlags
0x1800a8224  lea     rdx, [rbp+3D0h+NewFileName]; lpNewFileName
0x1800a822b  mov     rcx, r12; lpExistingFileName
0x1800a822e  call    cs:__imp_MoveFileExW
0x1800a8234  test    eax, eax
0x1800a8236  jnz     short loc_1800A8284
0x1800a8238  call    cs:__imp_GetLastError
0x1800a823e  mov     ebx, eax
0x1800a8240  test    eax, eax
0x1800a8242  jle     short loc_1800A8249
0x1800a8244  movzx   ebx, ax
0x1800a8247  or      ebx, esi
0x1800a8249  mov     rcx, cs:g_hPublisher
0x1800a8250  mov     r9d, r15d
0x1800a8253  cmp     ebx, 80070002h
0x1800a8259  jnz     short loc_1800A8274
0x1800a825b  xor     r8d, r8d
0x1800a825e  mov     [rsp+4D0h+dwCreationDisposition], 0DE8h
0x1800a8266  lea     rdx, EFS_TRACE_STATUS
0x1800a826d  call    fnEfsLogTrace1
0x1800a8272  jmp     short loc_1800A8289
0x1800a8274  mov     [rsp+4D0h+dwCreationDisposition], 0DECh
0x1800a827c  mov     r8d, ebx
0x1800a827f  jmp     loc_1800A816E
0x1800a8284  mov     [rsp+4D0h+var_490], r13d
0x1800a8289  xor     r8d, r8d; dwFlags
0x1800a828c  lea     rcx, [rsp+4D0h+FileName]; lpExistingFileName
0x1800a8291  mov     rdx, r12; lpNewFileName
0x1800a8294  call    cs:__imp_MoveFileExW
0x1800a829a  test    eax, eax
0x1800a829c  jnz     short loc_1800A82FF
0x1800a829e  mov     r9d, r15d
0x1800a82a1  mov     [rsp+4D0h+dwCreationDisposition], 0DFAh
0x1800a82a9  mov     r8, r14
0x1800a82ac  lea     rdx, EFS_TRACE_START_EVENT
0x1800a82b3  call    fnEfsLogTrace1Strings
0x1800a82b8  call    cs:__imp_GetLastError
0x1800a82be  mov     ebx, eax
0x1800a82c0  test    eax, eax
0x1800a82c2  jle     short loc_1800A82C9
0x1800a82c4  movzx   ebx, ax
0x1800a82c7  or      ebx, esi
0x1800a82c9  mov     rcx, cs:g_hPublisher
0x1800a82d0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a82d7  mov     dword ptr [rsp+4D0h+hTemplateFile], 0DFAh
  ... truncated ...
```
