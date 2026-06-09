# winreDeleteAllFiles

- ea: `0x18003158c`
- end: `0x18003180c`
- name: `winreDeleteAllFiles`
- size: `640`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18002b358`
- `0x18002bd30`
- `0x18002bec4`
- `0x18002f6a0`
- `0x18002fc20`
- `0x18003158c`
- `0x180032488`
- `0x180032564`

## callees

- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x18003158c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800316eb`
- `msvcrt!_wcsicmp` at `0x180031701`
- `msvcrt!_wcsicmp` at `0x1800316eb`
- `msvcrt!_wcsicmp` at `0x180031701`
- `KERNEL32!GetLastError` at `0x1800316af`
- `KERNEL32!GetLastError` at `0x180031731`
- `KERNEL32!GetLastError` at `0x180031767`
- `KERNEL32!GetLastError` at `0x1800316af`
- `KERNEL32!GetLastError` at `0x180031731`
- `KERNEL32!GetLastError` at `0x180031767`
- `KERNEL32!RemoveDirectoryW` at `0x18003171c`
- `KERNEL32!RemoveDirectoryW` at `0x18003171c`
- `KERNEL32!FindFirstFileW` at `0x1800316a0`
- `KERNEL32!FindFirstFileW` at `0x1800316a0`
- `KERNEL32!FindNextFileW` at `0x180031759`
- `KERNEL32!FindNextFileW` at `0x180031759`
- `KERNEL32!FindClose` at `0x1800317bb`
- `KERNEL32!FindClose` at `0x1800317bb`
- `KERNEL32!SetFileAttributesW` at `0x180031742`
- `KERNEL32!SetFileAttributesW` at `0x180031742`
- `KERNEL32!DeleteFileW` at `0x180031727`
- `KERNEL32!DeleteFileW` at `0x18003174b`
- `KERNEL32!DeleteFileW` at `0x180031727`
- `KERNEL32!DeleteFileW` at `0x18003174b`
- `ole32!CoTaskMemFree` at `0x1800317ce`
- `ole32!CoTaskMemFree` at `0x1800317dc`
- `ole32!CoTaskMemFree` at `0x1800317ce`
- `ole32!CoTaskMemFree` at `0x1800317dc`

## string_xrefs

- `0x180031607`: `failed to allocate path`
- `0x18003163a`: `failed to allocate path`
- `0x180031791`: `failed to add file to directory path`
- `0x1800315f0`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x180031641`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x180031798`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x18003160e`: `winreDeleteAllFiles %s (0x%x) in file %S line %d`
- `0x18003164b`: `winreDeleteAllFiles %s (0x%x) in file %S line %d`
- `0x1800317a2`: `winreDeleteAllFiles %s (0x%x) in file %S line %d`
- `0x18003168d`: `failed to add * to directory path`
- `0x180031780`: `faile to delete all files`

## pseudocode

```c
__int64 __fastcall winreDeleteAllFiles(unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rdi
  DWORD LastError; // ebx
  const wchar_t *v4; // r8
  HANDLE FirstFileW; // r14
  const char *v6; // r8
  int v8; // [rsp+28h] [rbp-D8h]
  int v9; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpPathName; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = 0;
  lpFileName = 0;
  lpPathName = 0;
  LastError = winreAllocPath(&lpFileName);
  if ( LastError )
  {
    UnattendLogW(
      2,
      L"winreDeleteAllFiles %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      915);
    goto LABEL_28;
  }
  LastError = winreAllocPath(&lpPathName);
  if ( LastError )
  {
    v8 = 916;
    v4 = L"failed to allocate path";
LABEL_5:
    UnattendLogW(
      2,
      L"winreDeleteAllFiles %s (0x%x) in file %S line %d",
      v4,
      LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      v8);
LABEL_6:
    v2 = (unsigned __int16 *)lpPathName;
    goto LABEL_28;
  }
  LastError = winreAddFileToDirPath(a1, L"*", (unsigned __int16 *)lpFileName);
  if ( LastError )
  {
    v8 = 920;
    v4 = L"failed to add * to directory path";
    goto LABEL_5;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_6;
  }
  v2 = (unsigned __int16 *)lpPathName;
  do
  {
    LastError = winreAddFileToDirPath(a1, FindFileData.cFileName, v2);
    if ( LastError )
    {
      v9 = 933;
      v6 = (const char *)L"failed to add file to directory path";
      goto LABEL_26;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( _wcsicmp(FindFileData.cFileName, L".") && _wcsicmp(FindFileData.cFileName, L"..") )
      {
        LastError = winreDeleteAllFiles(v2);
        if ( !LastError )
        {
          RemoveDirectoryW(v2);
          continue;
        }
        v9 = 948;
        v6 = "faile to delete all files";
LABEL_26:
        UnattendLogW(
          2,
          L"winreDeleteAllFiles %s (0x%x) in file %S line %d",
          v6,
          LastError,
          "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
          v9);
        goto LABEL_27;
      }
    }
    else if ( !DeleteFileW(v2) && GetLastError() == 5 )
    {
      SetFileAttributesW(v2, 0x80u);
      DeleteFileW(v2);
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  LastError = GetLastError();
  if ( LastError == 18 )
    LastError = 0;
LABEL_27:
  FindClose(FirstFileW);
LABEL_28:
  if ( lpFileName )
    CoTaskMemFree((LPVOID)lpFileName);
  if ( v2 )
    CoTaskMemFree(v2);
  return LastError;
}

```

## disassembly

```asm
0x18003158c  mov     [rsp-8+arg_8], rbx
0x180031591  mov     [rsp-8+arg_10], rdi
0x180031596  push    rbp
0x180031597  push    r14
0x180031599  push    r15
0x18003159b  lea     rbp, [rsp-1A0h]
0x1800315a3  sub     rsp, 2A0h
0x1800315aa  mov     rax, cs:__security_cookie
0x1800315b1  xor     rax, rsp
0x1800315b4  mov     [rbp+1B0h+var_20], rax
0x1800315bb  mov     r15, rcx
0x1800315be  xor     edx, edx; Val
0x1800315c0  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x1800315c5  mov     r8d, 250h; Size
0x1800315cb  call    memset_0
0x1800315d0  xor     edi, edi
0x1800315d2  mov     [rsp+2B0h+lpFileName], 0
0x1800315db  lea     rcx, [rsp+2B0h+lpFileName]
0x1800315e0  mov     [rsp+2B0h+lpPathName], rdi
0x1800315e5  call    winreAllocPath
0x1800315ea  mov     ebx, eax
0x1800315ec  test    eax, eax
0x1800315ee  jz      short loc_180031622
0x1800315f0  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800315f7  mov     [rsp+2B0h+var_288], 393h
0x1800315ff  mov     r9d, ebx
0x180031602  mov     [rsp+2B0h+var_290], rax
0x180031607  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18003160e  lea     rdx, aWinredeleteall_0; "winreDeleteAllFiles %s (0x%x) in file %"...
0x180031615  lea     ecx, [rdi+2]
0x180031618  call    UnattendLogW
0x18003161d  jmp     loc_1800317C1
0x180031622  lea     rcx, [rsp+2B0h+lpPathName]
0x180031627  call    winreAllocPath
0x18003162c  mov     ebx, eax
0x18003162e  test    eax, eax
0x180031630  jz      short loc_18003166B
0x180031632  mov     [rsp+2B0h+var_288], 394h
0x18003163a  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180031641  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180031648  mov     r9d, ebx
0x18003164b  lea     rdx, aWinredeleteall_0; "winreDeleteAllFiles %s (0x%x) in file %"...
0x180031652  mov     [rsp+2B0h+var_290], rax
0x180031657  mov     ecx, 2
0x18003165c  call    UnattendLogW
0x180031661  mov     rdi, [rsp+2B0h+lpPathName]
0x180031666  jmp     loc_1800317C1
0x18003166b  mov     r8, [rsp+2B0h+lpFileName]; unsigned __int16 *
0x180031670  lea     rdx, asc_18007D468; "*"
0x180031677  mov     rcx, r15; unsigned __int16 *
0x18003167a  call    winreAddFileToDirPath
0x18003167f  mov     ebx, eax
0x180031681  test    eax, eax
0x180031683  jz      short loc_180031696
0x180031685  mov     [rsp+2B0h+var_288], 398h
0x18003168d  lea     r8, aFailedToAddToD; "failed to add * to directory path"
0x180031694  jmp     short loc_180031641
0x180031696  mov     rcx, [rsp+2B0h+lpFileName]; lpFileName
0x18003169b  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800316a0  call    cs:__imp_FindFirstFileW
0x1800316a6  mov     r14, rax
0x1800316a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800316ad  jnz     short loc_1800316B9
0x1800316af  call    cs:__imp_GetLastError
0x1800316b5  mov     ebx, eax
0x1800316b7  jmp     short loc_180031661
0x1800316b9  mov     rdi, [rsp+2B0h+lpPathName]
0x1800316be  mov     r8, rdi; unsigned __int16 *
0x1800316c1  lea     rdx, [rsp+2B0h+FindFileData.cFileName]; unsigned __int16 *
0x1800316c6  mov     rcx, r15; unsigned __int16 *
0x1800316c9  call    winreAddFileToDirPath
0x1800316ce  mov     ebx, eax
0x1800316d0  test    eax, eax
0x1800316d2  jnz     loc_180031789
0x1800316d8  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x1800316dd  jz      short loc_180031724
0x1800316df  lea     rdx, asc_180070DA8; "."
0x1800316e6  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; String1
0x1800316eb  call    cs:__imp__wcsicmp
0x1800316f1  test    eax, eax
0x1800316f3  jz      short loc_180031751
0x1800316f5  lea     rdx, asc_18007D4E4; ".."
0x1800316fc  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; String1
0x180031701  call    cs:__imp__wcsicmp
0x180031707  test    eax, eax
0x180031709  jz      short loc_180031751
0x18003170b  mov     rcx, rdi
0x18003170e  call    winreDeleteAllFiles
0x180031713  mov     ebx, eax
0x180031715  test    eax, eax
0x180031717  jnz     short loc_180031778
0x180031719  mov     rcx, rdi; lpPathName
0x18003171c  call    cs:__imp_RemoveDirectoryW
0x180031722  jmp     short loc_180031751
0x180031724  mov     rcx, rdi; lpFileName
0x180031727  call    cs:__imp_DeleteFileW
0x18003172d  test    eax, eax
0x18003172f  jnz     short loc_180031751
0x180031731  call    cs:__imp_GetLastError
0x180031737  cmp     eax, 5
0x18003173a  jnz     short loc_180031751
0x18003173c  lea     edx, [rax+7Bh]; dwFileAttributes
0x18003173f  mov     rcx, rdi; lpFileName
0x180031742  call    cs:__imp_SetFileAttributesW
0x180031748  mov     rcx, rdi; lpFileName
0x18003174b  call    cs:__imp_DeleteFileW
0x180031751  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x180031756  mov     rcx, r14; hFindFile
0x180031759  call    cs:__imp_FindNextFileW
0x18003175f  test    eax, eax
0x180031761  jnz     loc_1800316BE
0x180031767  call    cs:__imp_GetLastError
0x18003176d  mov     ebx, eax
0x18003176f  cmp     eax, 12h
0x180031772  jnz     short loc_1800317B8
0x180031774  xor     ebx, ebx
0x180031776  jmp     short loc_1800317B8
0x180031778  mov     [rsp+2B0h+var_288], 3B4h
0x180031780  lea     r8, aFaileToDeleteA; "faile to delete all files"
0x180031787  jmp     short loc_180031798
0x180031789  mov     [rsp+2B0h+var_288], 3A5h
0x180031791  lea     r8, aFailedToAddFil_3; "failed to add file to directory path"
0x180031798  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003179f  mov     r9d, ebx
0x1800317a2  lea     rdx, aWinredeleteall_0; "winreDeleteAllFiles %s (0x%x) in file %"...
0x1800317a9  mov     [rsp+2B0h+var_290], rax
0x1800317ae  mov     ecx, 2
0x1800317b3  call    UnattendLogW
0x1800317b8  mov     rcx, r14; hFindFile
0x1800317bb  call    cs:__imp_FindClose
0x1800317c1  cmp     [rsp+2B0h+lpFileName], 0
0x1800317c7  jz      short loc_1800317D4
0x1800317c9  mov     rcx, [rsp+2B0h+lpFileName]; pv
0x1800317ce  call    cs:__imp_CoTaskMemFree
0x1800317d4  test    rdi, rdi
0x1800317d7  jz      short loc_1800317E2
0x1800317d9  mov     rcx, rdi; pv
0x1800317dc  call    cs:__imp_CoTaskMemFree
0x1800317e2  mov     eax, ebx
0x1800317e4  mov     rcx, [rbp+1B0h+var_20]
0x1800317eb  xor     rcx, rsp; StackCookie
0x1800317ee  call    __security_check_cookie
0x1800317f3  lea     r11, [rsp+2B0h+var_10]
0x1800317fb  mov     rbx, [r11+28h]
0x1800317ff  mov     rdi, [r11+30h]
0x180031803  mov     rsp, r11
0x180031806  pop     r15
0x180031808  pop     r14
0x18003180a  pop     rbp
0x18003180b  retn
```
