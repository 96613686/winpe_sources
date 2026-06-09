# TextLogRenameLogFile

- ea: `0x14000dc64`
- end: `0x14000de09`
- name: `TextLogRenameLogFile`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x14000ebf4`

## callees

- `0x14000c690`
- `0x14000cbe0`
- `0x14000cca8`
- `0x14000d348`
- `0x14000d530`
- `0x14000d6d8`
- `0x14000dc64`
- `0x14000df08`
- `0x14000e04c`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dcd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dcd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ddd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ddd3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x14000ddb5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x14000ddb5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000ddcb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000ddcb`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x14000dd33`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x14000dd33`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x14000dd0e`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x14000dd0e`

## pseudocode

```c
__int64 __fastcall TextLogRenameLogFile(__int64 a1)
{
  unsigned int v2; // ebx
  DWORD LastError; // edi
  int v4; // r15d
  int v5; // r14d
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+30h] [rbp-278h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-238h] BYREF

  v2 = 0;
  LastError = 0;
  v4 = 0;
  v5 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( (unsigned int)TextLogGetLogRenameFilename(*(_QWORD *)(a1 + 32), FileName) )
  {
    v4 = 1;
  }
  else if ( !*(_DWORD *)(a1 + 48)
         || !(unsigned int)TextLogGenerateBackupLogFileName(
                             *(unsigned __int16 **)(*(_QWORD *)(a1 + 32) + 16LL),
                             FileName) )
  {
LABEL_4:
    LastError = GetLastError();
    goto LABEL_13;
  }
  if ( !CreateHardLinkW(FileName, *(LPCWSTR *)(*(_QWORD *)(a1 + 32) + 16LL), 0) )
    goto LABEL_4;
  v5 = 1;
  if ( v4 )
    TextLogDeletePendingRenameTag(a1);
  FlushFileBuffers(*(HANDLE *)a1);
  *(_DWORD *)(a1 + 44) = 0;
  pSetupUnmapFileAndSetEOF(*(HANDLE *)a1, *(HANDLE *)(a1 + 8), *(LPCVOID *)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !(unsigned int)pSetupDeleteFileByHandle(*(HANDLE *)a1) )
    goto LABEL_4;
  v5 = 0;
  if ( v4 )
    TextLogSetLogRenameFilename(*(_QWORD *)(a1 + 32));
  TextLogUnmapFile(a1);
  pSetupSetFileCompressionState(FileName);
LABEL_13:
  if ( v5
    && *(_QWORD *)a1 != -1
    && GetFileInformationByHandle(*(HANDLE *)a1, &FileInformation)
    && FileInformation.nNumberOfLinks > 1 )
  {
    DeleteFileW(FileName);
  }
  SetLastError(LastError);
  LOBYTE(v2) = LastError == 0;
  return v2;
}

```

## disassembly

```asm
0x14000dc64  mov     [rsp+arg_8], rbx
0x14000dc69  mov     [rsp+arg_10], rsi
0x14000dc6e  push    rdi
0x14000dc6f  push    r14
0x14000dc71  push    r15
0x14000dc73  sub     rsp, 290h
0x14000dc7a  mov     rax, cs:__security_cookie
0x14000dc81  xor     rax, rsp
0x14000dc84  mov     [rsp+2A8h+var_28], rax
0x14000dc8c  mov     rsi, rcx
0x14000dc8f  mov     [rsp+2A8h+var_280], rcx
0x14000dc94  xor     ebx, ebx
0x14000dc96  mov     edi, ebx
0x14000dc98  mov     r15d, ebx
0x14000dc9b  mov     r14d, ebx
0x14000dc9e  mov     [rsp+2A8h+var_284], ebx
0x14000dca2  xorps   xmm0, xmm0
0x14000dca5  xor     eax, eax
0x14000dca7  movups  xmmword ptr [rsp+2A8h+FileInformation.dwFileAttributes], xmm0
0x14000dcac  movups  xmmword ptr [rsp+2A8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x14000dcb1  movups  xmmword ptr [rsp+2A8h+FileInformation.nFileSizeHigh], xmm0
0x14000dcb6  mov     [rsp+2A8h+FileInformation.nFileIndexLow], eax
0x14000dcba  lea     rdx, [rsp+2A8h+FileName]
0x14000dcbf  mov     rcx, [rcx+20h]
0x14000dcc3  call    TextLogGetLogRenameFilename
0x14000dcc8  test    eax, eax
0x14000dcca  jz      short loc_14000DCD2
0x14000dccc  lea     r15d, [rbx+1]
0x14000dcd0  jmp     short loc_14000DCFE
0x14000dcd2  cmp     [rsi+30h], ebx
0x14000dcd5  jnz     short loc_14000DCE8
0x14000dcd7  call    cs:__imp_GetLastError
0x14000dcdd  mov     edi, eax
0x14000dcdf  mov     [rsp+2A8h+var_288], eax
0x14000dce3  jmp     loc_14000DD8B
0x14000dce8  mov     rcx, [rsi+20h]
0x14000dcec  lea     rdx, [rsp+2A8h+FileName]; pszDest
0x14000dcf1  mov     rcx, [rcx+10h]; unsigned __int16 *
0x14000dcf5  call    TextLogGenerateBackupLogFileName
0x14000dcfa  test    eax, eax
0x14000dcfc  jz      short loc_14000DCD7
0x14000dcfe  mov     rdx, [rsi+20h]
0x14000dd02  xor     r8d, r8d; lpSecurityAttributes
0x14000dd05  mov     rdx, [rdx+10h]; lpExistingFileName
0x14000dd09  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x14000dd0e  call    cs:__imp_CreateHardLinkW
0x14000dd14  test    eax, eax
0x14000dd16  jz      short loc_14000DCD7
0x14000dd18  mov     r14d, 1
0x14000dd1e  mov     [rsp+2A8h+var_284], r14d
0x14000dd23  test    r15d, r15d
0x14000dd26  jz      short loc_14000DD30
0x14000dd28  mov     rcx, rsi
0x14000dd2b  call    TextLogDeletePendingRenameTag
0x14000dd30  mov     rcx, [rsi]; hFile
0x14000dd33  call    cs:__imp_FlushFileBuffers
0x14000dd39  mov     [rsi+2Ch], ebx
0x14000dd3c  mov     r8, [rsi+10h]; lpBaseAddress
0x14000dd40  mov     rdx, [rsi+8]; hObject
0x14000dd44  mov     rcx, [rsi]; hFile
0x14000dd47  call    pSetupUnmapFileAndSetEOF
0x14000dd4c  mov     [rsi+10h], rbx
0x14000dd50  mov     [rsi+8], rbx
0x14000dd54  mov     rcx, [rsi]; FileHandle
0x14000dd57  call    pSetupDeleteFileByHandle
0x14000dd5c  test    eax, eax
0x14000dd5e  jz      loc_14000DCD7
0x14000dd64  mov     r14d, ebx
0x14000dd67  mov     [rsp+2A8h+var_284], ebx
0x14000dd6b  test    r15d, r15d
0x14000dd6e  jz      short loc_14000DD79
0x14000dd70  mov     rcx, [rsi+20h]
0x14000dd74  call    TextLogSetLogRenameFilename
0x14000dd79  mov     rcx, rsi
0x14000dd7c  call    TextLogUnmapFile
0x14000dd81  lea     rcx, [rsp+2A8h+FileName]
0x14000dd86  call    pSetupSetFileCompressionState
0x14000dd8b  jmp     short loc_14000DDA2
0x14000dd8d  mov     edi, 54Fh
0x14000dd92  mov     [rsp+2A8h+var_288], edi
0x14000dd96  xor     ebx, ebx
0x14000dd98  mov     r14d, [rsp+2A8h+var_284]
0x14000dd9d  mov     rsi, [rsp+2A8h+var_280]
0x14000dda2  test    r14d, r14d
0x14000dda5  jz      short loc_14000DDD1
0x14000dda7  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x14000ddab  jz      short loc_14000DDD1
0x14000ddad  lea     rdx, [rsp+2A8h+FileInformation]; lpFileInformation
0x14000ddb2  mov     rcx, [rsi]; hFile
0x14000ddb5  call    cs:__imp_GetFileInformationByHandle
0x14000ddbb  test    eax, eax
0x14000ddbd  jz      short loc_14000DDD1
0x14000ddbf  cmp     [rsp+2A8h+FileInformation.nNumberOfLinks], 1
0x14000ddc4  jbe     short loc_14000DDD1
0x14000ddc6  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x14000ddcb  call    cs:__imp_DeleteFileW
0x14000ddd1  mov     ecx, edi; dwErrCode
0x14000ddd3  call    cs:__imp_SetLastError
0x14000ddd9  test    edi, edi
0x14000dddb  setz    bl
0x14000ddde  mov     eax, ebx
0x14000dde0  mov     rcx, [rsp+2A8h+var_28]
0x14000dde8  xor     rcx, rsp; StackCookie
0x14000ddeb  call    __security_check_cookie
0x14000ddf0  lea     r11, [rsp+2A8h+var_18]
0x14000ddf8  mov     rbx, [r11+28h]
0x14000ddfc  mov     rsi, [r11+30h]
0x14000de00  mov     rsp, r11
0x14000de03  pop     r15
0x14000de05  pop     r14
0x14000de07  pop     rdi
0x14000de08  retn
```
