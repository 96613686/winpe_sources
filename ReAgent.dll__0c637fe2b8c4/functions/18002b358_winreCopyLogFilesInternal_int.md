# winreCopyLogFilesInternal(int)

- ea: `0x18002b358`
- end: `0x18002b6ea`
- name: `?winreCopyLogFilesInternal@@YAKH@Z`
- size: `914`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x18002bc60`
- `0x18002c4f0`

## callees

- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x18002b358`
- `0x18002bfac`
- `0x18002c590`
- `0x18003158c`
- `0x1800322a8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18002b5e5`
- `KERNEL32!CopyFileW` at `0x18002b5e5`
- `KERNEL32!GetLastError` at `0x18002b592`
- `KERNEL32!GetLastError` at `0x18002b5fd`
- `KERNEL32!GetLastError` at `0x18002b592`
- `KERNEL32!GetLastError` at `0x18002b5fd`
- `KERNEL32!FindFirstFileW` at `0x18002b583`
- `KERNEL32!FindFirstFileW` at `0x18002b583`
- `KERNEL32!FindNextFileW` at `0x18002b5f3`
- `KERNEL32!FindNextFileW` at `0x18002b5f3`
- `KERNEL32!FindClose` at `0x18002b656`
- `KERNEL32!FindClose` at `0x18002b656`
- `ole32!CoTaskMemFree` at `0x18002b669`
- `ole32!CoTaskMemFree` at `0x18002b67c`
- `ole32!CoTaskMemFree` at `0x18002b68a`
- `ole32!CoTaskMemFree` at `0x18002b698`
- `ole32!CoTaskMemFree` at `0x18002b669`
- `ole32!CoTaskMemFree` at `0x18002b67c`
- `ole32!CoTaskMemFree` at `0x18002b68a`
- `ole32!CoTaskMemFree` at `0x18002b698`

## string_xrefs

- `0x18002b3ce`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b411`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b45a`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b4c1`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b633`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b4ba`: `failed to get log directory path`
- `0x18002b532`: `failed to open directory`
- `0x18002b3e5`: `Failed to allocate path`
- `0x18002b428`: `Failed to allocate path`
- `0x18002b471`: `Failed to allocate path`
- `0x18002b3ec`: `winreCopyLogFilesInternal %s (0x%x) in file %S line %d`
- `0x18002b434`: `winreCopyLogFilesInternal %s (0x%x) in file %S line %d`
- `0x18002b47d`: `winreCopyLogFilesInternal %s (0x%x) in file %S line %d`
- `0x18002b4cb`: `winreCopyLogFilesInternal %s (0x%x) in file %S line %d`
- `0x18002b63d`: `winreCopyLogFilesInternal %s (0x%x) in file %S line %d`
- `0x18002b507`: `failed to open WinPE directory`
- `0x18002b6de`: `failed to add file to src directory path`
- `0x18002b6ca`: `failed to add file to dest directory path`

## pseudocode

```c
__int64 __fastcall winreCopyLogFilesInternal(int a1)
{
  unsigned __int16 *v2; // r14
  unsigned __int16 *v3; // r15
  DWORD Dir; // ebx
  DWORD LogDirPathInternal; // eax
  const wchar_t *v6; // r8
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // rdi
  HANDLE FirstFileW; // r13
  DWORD LastError; // eax
  const wchar_t *v11; // r8
  int v13; // [rsp+28h] [rbp-D8h]
  int v14; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpNewFileName; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v18 = a1;
  v2 = 0;
  pv = 0;
  v3 = 0;
  lpNewFileName = 0;
  lpFileName[0] = 0;
  lpExistingFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  Dir = winreAllocPath(&lpExistingFileName);
  if ( Dir )
  {
    UnattendLogW(
      2,
      L"winreCopyLogFilesInternal %s (0x%x) in file %S line %d",
      L"Failed to allocate path",
      Dir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      739);
    goto LABEL_35;
  }
  Dir = winreAllocPath(&lpNewFileName);
  if ( Dir )
  {
    UnattendLogW(
      2,
      L"winreCopyLogFilesInternal %s (0x%x) in file %S line %d",
      L"Failed to allocate path",
      Dir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      740);
    v2 = (unsigned __int16 *)lpNewFileName;
    goto LABEL_35;
  }
  Dir = winreAllocPath(lpFileName);
  if ( Dir )
  {
    UnattendLogW(
      2,
      L"winreCopyLogFilesInternal %s (0x%x) in file %S line %d",
      L"Failed to allocate path",
      Dir,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      741);
    v2 = (unsigned __int16 *)lpNewFileName;
    v3 = (unsigned __int16 *)lpFileName[0];
    goto LABEL_35;
  }
  LogDirPathInternal = WinReGetLogDirPathInternal(&pv);
  v2 = (unsigned __int16 *)lpNewFileName;
  Dir = LogDirPathInternal;
  v3 = (unsigned __int16 *)lpFileName[0];
  if ( LogDirPathInternal )
  {
    v13 = 747;
    v6 = L"failed to get log directory path";
  }
  else
  {
    if ( a1 )
    {
      Dir = winreOpenOrCreateDir(L"x:\\RecoveryLogs");
      if ( Dir )
      {
        v13 = 755;
        v6 = L"failed to open WinPE directory";
        goto LABEL_9;
      }
      v7 = L"x:\\RecoveryLogs";
      v8 = (unsigned __int16 *)pv;
    }
    else
    {
      Dir = winreOpenOrCreateDir((LPCWSTR)pv);
      if ( Dir )
      {
        v13 = 761;
        v6 = L"failed to open directory";
        goto LABEL_9;
      }
      v7 = (unsigned __int16 *)pv;
      v8 = L"x:\\RecoveryLogs";
    }
    winreDeleteAllFiles(v7);
    Dir = winreAddFileToDirPath(v8, L"*", v3);
    if ( !Dir )
    {
      FirstFileW = FindFirstFileW(v3, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        Dir = GetLastError();
      }
      else
      {
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          {
            Dir = winreAddFileToDirPath(v8, FindFileData.cFileName, (unsigned __int16 *)lpExistingFileName);
            if ( Dir )
            {
              v14 = 789;
              v11 = L"failed to add file to src directory path";
              goto LABEL_31;
            }
            Dir = winreAddFileToDirPath(v7, FindFileData.cFileName, v2);
            if ( Dir )
            {
              v14 = 793;
              v11 = L"failed to add file to dest directory path";
              goto LABEL_31;
            }
            CopyFileW(lpExistingFileName, v2, 0);
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        LastError = GetLastError();
        Dir = 0;
        if ( LastError != 18 )
          Dir = LastError;
        if ( !v18 )
        {
          Dir = WinReSetTriggerFile((unsigned __int16 *)pv);
          if ( Dir )
          {
            v14 = 811;
            v11 = L"failed to set trigger file";
LABEL_31:
            UnattendLogW(
              2,
              L"winreCopyLogFilesInternal %s (0x%x) in file %S line %d",
              v11,
              Dir,
              "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
              v14);
          }
        }
        FindClose(FirstFileW);
      }
      goto LABEL_33;
    }
    v13 = 770;
    v6 = L"failed to add * to search pattern";
  }
LABEL_9:
  UnattendLogW(
    2,
    L"winreCopyLogFilesInternal %s (0x%x) in file %S line %d",
    v6,
    Dir,
    "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
    v13);
LABEL_33:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_35:
  if ( lpExistingFileName )
    CoTaskMemFree((LPVOID)lpExistingFileName);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v3 )
    CoTaskMemFree(v3);
  return Dir;
}

```

## disassembly

```asm
0x18002b358  push    rbp
0x18002b35a  push    rbx
0x18002b35b  push    rdi
0x18002b35c  push    r12
0x18002b35e  push    r13
0x18002b360  push    r14
0x18002b362  push    r15
0x18002b364  lea     rbp, [rsp-1C0h]
0x18002b36c  sub     rsp, 2C0h
0x18002b373  mov     rax, cs:__security_cookie
0x18002b37a  xor     rax, rsp
0x18002b37d  mov     [rbp+1F0h+var_40], rax
0x18002b384  mov     edi, ecx
0x18002b386  mov     [rsp+2F0h+var_2A8], ecx
0x18002b38a  xor     r14d, r14d
0x18002b38d  mov     [rsp+2F0h+pv], 0
0x18002b396  xor     r15d, r15d
0x18002b399  mov     [rsp+2F0h+lpNewFileName], r14
0x18002b39e  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x18002b3a3  mov     [rsp+2F0h+lpFileName], r15
0x18002b3a8  xor     edx, edx; Val
0x18002b3aa  mov     [rsp+2F0h+lpExistingFileName], 0
0x18002b3b3  mov     r8d, 250h; Size
0x18002b3b9  call    memset_0
0x18002b3be  lea     rcx, [rsp+2F0h+lpExistingFileName]
0x18002b3c3  call    winreAllocPath
0x18002b3c8  mov     ebx, eax
0x18002b3ca  test    eax, eax
0x18002b3cc  jz      short loc_18002B401
0x18002b3ce  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b3d5  mov     [rsp+2F0h+var_2C8], 2E3h
0x18002b3dd  mov     r9d, ebx
0x18002b3e0  mov     [rsp+2F0h+var_2D0], rax
0x18002b3e5  lea     r8, aFailedToAlloca_2; "Failed to allocate path"
0x18002b3ec  lea     rdx, aWinrecopylogfi_0; "winreCopyLogFilesInternal %s (0x%x) in "...
0x18002b3f3  lea     ecx, [r14+2]
0x18002b3f7  call    UnattendLogW
0x18002b3fc  jmp     loc_18002B66F
0x18002b401  lea     rcx, [rsp+2F0h+lpNewFileName]
0x18002b406  call    winreAllocPath
0x18002b40b  mov     ebx, eax
0x18002b40d  test    eax, eax
0x18002b40f  jz      short loc_18002B44A
0x18002b411  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b418  mov     [rsp+2F0h+var_2C8], 2E4h
0x18002b420  mov     r9d, ebx
0x18002b423  mov     [rsp+2F0h+var_2D0], rax
0x18002b428  lea     r8, aFailedToAlloca_2; "Failed to allocate path"
0x18002b42f  mov     ecx, 2
0x18002b434  lea     rdx, aWinrecopylogfi_0; "winreCopyLogFilesInternal %s (0x%x) in "...
0x18002b43b  call    UnattendLogW
0x18002b440  mov     r14, [rsp+2F0h+lpNewFileName]
0x18002b445  jmp     loc_18002B66F
0x18002b44a  lea     rcx, [rsp+2F0h+lpFileName]
0x18002b44f  call    winreAllocPath
0x18002b454  mov     ebx, eax
0x18002b456  test    eax, eax
0x18002b458  jz      short loc_18002B498
0x18002b45a  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b461  mov     [rsp+2F0h+var_2C8], 2E5h
0x18002b469  mov     r9d, ebx
0x18002b46c  mov     [rsp+2F0h+var_2D0], rax
0x18002b471  lea     r8, aFailedToAlloca_2; "Failed to allocate path"
0x18002b478  mov     ecx, 2
0x18002b47d  lea     rdx, aWinrecopylogfi_0; "winreCopyLogFilesInternal %s (0x%x) in "...
0x18002b484  call    UnattendLogW
0x18002b489  mov     r14, [rsp+2F0h+lpNewFileName]
0x18002b48e  mov     r15, [rsp+2F0h+lpFileName]
0x18002b493  jmp     loc_18002B66F
0x18002b498  lea     rcx, [rsp+2F0h+pv]
0x18002b49d  call    WinReGetLogDirPathInternal
0x18002b4a2  mov     r14, [rsp+2F0h+lpNewFileName]
0x18002b4a7  mov     ebx, eax
0x18002b4a9  mov     r15, [rsp+2F0h+lpFileName]
0x18002b4ae  test    eax, eax
0x18002b4b0  jz      short loc_18002B4E6
0x18002b4b2  mov     [rsp+2F0h+var_2C8], 2EBh
0x18002b4ba  lea     r8, aFailedToGetLog_0; "failed to get log directory path"
0x18002b4c1  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b4c8  mov     r9d, ebx
0x18002b4cb  lea     rdx, aWinrecopylogfi_0; "winreCopyLogFilesInternal %s (0x%x) in "...
0x18002b4d2  mov     [rsp+2F0h+var_2D0], rax
0x18002b4d7  mov     ecx, 2
0x18002b4dc  call    UnattendLogW
0x18002b4e1  jmp     loc_18002B65C
0x18002b4e6  test    edi, edi
0x18002b4e8  jz      short loc_18002B51A
0x18002b4ea  lea     rdi, FileName; "x:\\RecoveryLogs"
0x18002b4f1  mov     rcx, rdi; lpFileName
0x18002b4f4  call    winreOpenOrCreateDir
0x18002b4f9  mov     ebx, eax
0x18002b4fb  test    eax, eax
0x18002b4fd  jz      short loc_18002B510
0x18002b4ff  mov     [rsp+2F0h+var_2C8], 2F3h
0x18002b507  lea     r8, aFailedToOpenWi; "failed to open WinPE directory"
0x18002b50e  jmp     short loc_18002B4C1
0x18002b510  mov     r12, rdi
0x18002b513  mov     rdi, [rsp+2F0h+pv]
0x18002b518  jmp     short loc_18002B547
0x18002b51a  mov     rcx, [rsp+2F0h+pv]; lpFileName
0x18002b51f  call    winreOpenOrCreateDir
0x18002b524  mov     ebx, eax
0x18002b526  test    eax, eax
0x18002b528  jz      short loc_18002B53B
0x18002b52a  mov     [rsp+2F0h+var_2C8], 2F9h
0x18002b532  lea     r8, aFailedToOpenDi; "failed to open directory"
0x18002b539  jmp     short loc_18002B4C1
0x18002b53b  mov     r12, [rsp+2F0h+pv]
0x18002b540  lea     rdi, FileName; "x:\\RecoveryLogs"
0x18002b547  mov     rcx, r12
0x18002b54a  call    winreDeleteAllFiles
0x18002b54f  mov     r8, r15; unsigned __int16 *
0x18002b552  lea     rdx, asc_18007D468; "*"
0x18002b559  mov     rcx, rdi; unsigned __int16 *
0x18002b55c  call    winreAddFileToDirPath
0x18002b561  mov     ebx, eax
0x18002b563  test    eax, eax
0x18002b565  jz      short loc_18002B57B
0x18002b567  mov     [rsp+2F0h+var_2C8], 302h
0x18002b56f  lea     r8, aFailedToAddToS; "failed to add * to search pattern"
0x18002b576  jmp     loc_18002B4C1
0x18002b57b  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18002b580  mov     rcx, r15; lpFileName
0x18002b583  call    cs:__imp_FindFirstFileW
0x18002b589  mov     r13, rax
0x18002b58c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b590  jnz     short loc_18002B59F
0x18002b592  call    cs:__imp_GetLastError
0x18002b598  mov     ebx, eax
0x18002b59a  jmp     loc_18002B65C
0x18002b59f  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x18002b5a4  jnz     short loc_18002B5EB
0x18002b5a6  mov     r8, [rsp+2F0h+lpExistingFileName]; unsigned __int16 *
0x18002b5ab  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; unsigned __int16 *
0x18002b5af  mov     rcx, rdi; unsigned __int16 *
0x18002b5b2  call    winreAddFileToDirPath
0x18002b5b7  mov     ebx, eax
0x18002b5b9  test    eax, eax
0x18002b5bb  jnz     loc_18002B6D6
0x18002b5c1  mov     r8, r14; unsigned __int16 *
0x18002b5c4  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; unsigned __int16 *
0x18002b5c8  mov     rcx, r12; unsigned __int16 *
0x18002b5cb  call    winreAddFileToDirPath
0x18002b5d0  mov     ebx, eax
0x18002b5d2  test    eax, eax
0x18002b5d4  jnz     loc_18002B6C2
0x18002b5da  mov     rcx, [rsp+2F0h+lpExistingFileName]; lpExistingFileName
0x18002b5df  xor     r8d, r8d; bFailIfExists
0x18002b5e2  mov     rdx, r14; lpNewFileName
0x18002b5e5  call    cs:__imp_CopyFileW
0x18002b5eb  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18002b5f0  mov     rcx, r13; hFindFile
0x18002b5f3  call    cs:__imp_FindNextFileW
0x18002b5f9  test    eax, eax
0x18002b5fb  jnz     short loc_18002B59F
0x18002b5fd  call    cs:__imp_GetLastError
0x18002b603  xor     ebx, ebx
0x18002b605  cmp     eax, 12h
0x18002b608  cmovnz  ebx, eax
0x18002b60b  cmp     [rsp+2F0h+var_2A8], 0
0x18002b610  jnz     short loc_18002B653
0x18002b612  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x18002b617  xor     edx, edx
0x18002b619  call    WinReSetTriggerFile
0x18002b61e  mov     ebx, eax
0x18002b620  test    eax, eax
0x18002b622  jz      short loc_18002B653
0x18002b624  mov     [rsp+2F0h+var_2C8], 32Bh
0x18002b62c  lea     r8, aFailedToSetTri; "failed to set trigger file"
0x18002b633  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b63a  mov     r9d, ebx
0x18002b63d  lea     rdx, aWinrecopylogfi_0; "winreCopyLogFilesInternal %s (0x%x) in "...
0x18002b644  mov     [rsp+2F0h+var_2D0], rax
0x18002b649  mov     ecx, 2
0x18002b64e  call    UnattendLogW
0x18002b653  mov     rcx, r13; hFindFile
0x18002b656  call    cs:__imp_FindClose
0x18002b65c  cmp     [rsp+2F0h+pv], 0
0x18002b662  jz      short loc_18002B66F
0x18002b664  mov     rcx, [rsp+2F0h+pv]; pv
0x18002b669  call    cs:__imp_CoTaskMemFree
0x18002b66f  cmp     [rsp+2F0h+lpExistingFileName], 0
0x18002b675  jz      short loc_18002B682
0x18002b677  mov     rcx, [rsp+2F0h+lpExistingFileName]; pv
0x18002b67c  call    cs:__imp_CoTaskMemFree
0x18002b682  test    r14, r14
0x18002b685  jz      short loc_18002B690
0x18002b687  mov     rcx, r14; pv
0x18002b68a  call    cs:__imp_CoTaskMemFree
0x18002b690  test    r15, r15
0x18002b693  jz      short loc_18002B69E
0x18002b695  mov     rcx, r15; pv
0x18002b698  call    cs:__imp_CoTaskMemFree
0x18002b69e  mov     eax, ebx
0x18002b6a0  mov     rcx, [rbp+1F0h+var_40]
0x18002b6a7  xor     rcx, rsp; StackCookie
0x18002b6aa  call    __security_check_cookie
0x18002b6af  add     rsp, 2C0h
0x18002b6b6  pop     r15
0x18002b6b8  pop     r14
0x18002b6ba  pop     r13
0x18002b6bc  pop     r12
0x18002b6be  pop     rdi
0x18002b6bf  pop     rbx
0x18002b6c0  pop     rbp
0x18002b6c1  retn
0x18002b6c2  mov     [rsp+2F0h+var_2C8], 319h
0x18002b6ca  lea     r8, aFailedToAddFil_2; "failed to add file to dest directory pa"...
0x18002b6d1  jmp     loc_18002B633
0x18002b6d6  mov     [rsp+2F0h+var_2C8], 315h
0x18002b6de  lea     r8, aFailedToAddFil_0; "failed to add file to src directory pat"...
0x18002b6e5  jmp     loc_18002B633
```
