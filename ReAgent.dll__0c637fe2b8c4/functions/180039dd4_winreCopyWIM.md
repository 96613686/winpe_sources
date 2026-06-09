# winreCopyWIM

- ea: `0x180039dd4`
- end: `0x18003a241`
- name: `winreCopyWIM`
- size: `1133`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, LPCWSTR lpExistingFileName)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x180018870`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000fe58`
- `0x18000ffcc`
- `0x1800103f4`
- `0x18001e4c8`
- `0x1800297cc`
- `0x180031434`
- `0x1800322a8`
- `0x180032728`
- `0x180039dd4`
- `0x18003bea8`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18003a05d`
- `KERNEL32!CopyFileW` at `0x18003a119`
- `KERNEL32!CopyFileW` at `0x18003a1c5`
- `KERNEL32!CopyFileW` at `0x18003a05d`
- `KERNEL32!CopyFileW` at `0x18003a119`
- `KERNEL32!CopyFileW` at `0x18003a1c5`
- `KERNEL32!GetLastError` at `0x18003a067`
- `KERNEL32!GetLastError` at `0x18003a0ad`
- `KERNEL32!GetLastError` at `0x18003a0f9`
- `KERNEL32!GetLastError` at `0x18003a123`
- `KERNEL32!GetLastError` at `0x18003a1cf`
- `KERNEL32!GetLastError` at `0x18003a067`
- `KERNEL32!GetLastError` at `0x18003a0ad`
- `KERNEL32!GetLastError` at `0x18003a0f9`
- `KERNEL32!GetLastError` at `0x18003a123`
- `KERNEL32!GetLastError` at `0x18003a1cf`
- `KERNEL32!MoveFileExW` at `0x18003a0ef`
- `KERNEL32!MoveFileExW` at `0x18003a0ef`
- `KERNEL32!SetFileAttributesW` at `0x18003a09a`
- `KERNEL32!SetFileAttributesW` at `0x18003a09a`
- `KERNEL32!DeleteFileW` at `0x18003a00b`
- `KERNEL32!DeleteFileW` at `0x18003a088`
- `KERNEL32!DeleteFileW` at `0x18003a0a3`
- `KERNEL32!DeleteFileW` at `0x18003a1b6`
- `KERNEL32!DeleteFileW` at `0x18003a00b`
- `KERNEL32!DeleteFileW` at `0x18003a088`
- `KERNEL32!DeleteFileW` at `0x18003a0a3`
- `KERNEL32!DeleteFileW` at `0x18003a1b6`
- `ole32!CoTaskMemFree` at `0x18003a1f4`
- `ole32!CoTaskMemFree` at `0x18003a202`
- `ole32!CoTaskMemFree` at `0x18003a210`
- `ole32!CoTaskMemFree` at `0x18003a1f4`
- `ole32!CoTaskMemFree` at `0x18003a202`
- `ole32!CoTaskMemFree` at `0x18003a210`

## string_xrefs

- `0x180039e2e`: `failed to allocate path`
- `0x180039e80`: `failed to allocate path`
- `0x180039eb8`: `failed to allocate path`
- `0x180039fed`: `failed to add winre.wim to directory path`
- `0x18003a075`: `failed to copy file`
- `0x18003a183`: `failed to add boot.sdi to directory path`
- `0x18003a0ff`: `failed to move file`
- `0x180039e3a`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039e69`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039ebf`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039f99`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039e44`: `winreCopyWIM %s (0x%x) in file %S line %d`
- `0x180039e8c`: `winreCopyWIM %s (0x%x) in file %S line %d`
- `0x180039ec9`: `winreCopyWIM %s (0x%x) in file %S line %d`
- `0x180039fbc`: `winreCopyWIM %s (0x%x) in file %S line %d`
- `0x180039f08`: `failed to create target directory name`
- `0x180039f27`: `failed to create \Recovery root directory`
- `0x180039f67`: `failed to create temp directory`
- `0x18003a014`: `winreCopyWIM Deleted existing wim file in %s`
- `0x18003a043`: `winreCopyWIM Copying file from %s to %s`
- `0x18003a0b6`: `winreCopyWIM Could not delete %s (GLE 0X%X)`
- `0x18003a157`: `failed to get boot.sdi path`
- `0x18003a1a5`: `winreCopyWIM Deleted existing sdi file in %s`
- `0x18003a21d`: `winreCopyWIM failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCopyWIM(
        struct _GUID *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 *a5,
        WCHAR *lpExistingFileName)
{
  WCHAR *v6; // r14
  WCHAR *v7; // rsi
  unsigned int v11; // eax
  WCHAR *v12; // r15
  unsigned int TargetDirName; // ebx
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  const wchar_t *v16; // r8
  __int64 v17; // rdx
  DWORD LastError; // eax
  DWORD v19; // eax
  int v21; // [rsp+28h] [rbp-20h]
  int v22; // [rsp+28h] [rbp-20h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-10h] BYREF

  v6 = 0;
  pv[0] = 0;
  v7 = 0;
  lpExistingFileName = 0;
  lpFileName = 0;
  *a5 = 0;
  v11 = winreAllocPath(pv);
  v12 = (WCHAR *)pv[0];
  TargetDirName = v11;
  if ( v11 )
  {
    v21 = 1602;
    v14 = L"failed to allocate path";
LABEL_3:
    UnattendLogW(
      2,
      L"winreCopyWIM %s (0x%x) in file %S line %d",
      v14,
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v21);
    goto LABEL_49;
  }
  TargetDirName = winreAllocPath(&lpExistingFileName);
  if ( TargetDirName )
  {
    UnattendLogW(
      2,
      L"winreCopyWIM %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      1603);
    v6 = lpExistingFileName;
    goto LABEL_49;
  }
  TargetDirName = winreAllocPath(&lpFileName);
  if ( TargetDirName )
  {
    v22 = 1604;
    v16 = L"failed to allocate path";
LABEL_8:
    UnattendLogW(
      2,
      L"winreCopyWIM %s (0x%x) in file %S line %d",
      v16,
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v22);
    v6 = lpExistingFileName;
LABEL_9:
    v7 = (WCHAR *)lpFileName;
    goto LABEL_49;
  }
  TargetDirName = winreCreateTargetDirName(a2, v15, 0, v12);
  if ( TargetDirName )
  {
    v22 = 1615;
LABEL_12:
    v16 = L"failed to create target directory name";
    goto LABEL_8;
  }
  TargetDirName = winreOpenOrCreateDir(v12);
  if ( TargetDirName )
  {
    v22 = 1617;
    v16 = L"failed to create \\Recovery root directory";
    goto LABEL_8;
  }
  TargetDirName = winreCreateTargetDirName(a2, v17, 1, v12);
  if ( TargetDirName )
  {
    v22 = 1627;
    goto LABEL_12;
  }
  TargetDirName = winreOpenOrCreateDir(v12);
  if ( TargetDirName )
  {
    v22 = 1632;
    v16 = L"failed to create temp directory";
    goto LABEL_8;
  }
  v6 = lpExistingFileName;
  TargetDirName = winreGetSourceFile(a1, a3, L"Winre.wim", lpExistingFileName);
  if ( TargetDirName )
  {
    UnattendLogW(
      2,
      L"winreCopyWIM %s (0x%x) in file %S line %d",
      L"failed to get source file winre.wim",
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      1642);
    goto LABEL_9;
  }
  v7 = (WCHAR *)lpFileName;
  TargetDirName = winreAddFileToDirPath(v12, L"Winre.wim", (unsigned __int16 *)lpFileName);
  if ( TargetDirName )
  {
    v21 = 1646;
    v14 = L"failed to add winre.wim to directory path";
    goto LABEL_3;
  }
  if ( (unsigned int)winreDoesFileExist(v12, L"Winre.wim") )
  {
    DeleteFileW(v7);
    UnattendLogW(0, L"winreCopyWIM Deleted existing wim file in %s", v7);
  }
  if ( a4 )
  {
    if ( (unsigned int)WinReIsWimBootEnabledInternal(v6) )
    {
      UnattendLogW(0, L"winreCopyWIM Copying file from %s to %s", v6, v7);
      if ( !CopyFileW(v6, v7, 0) )
      {
        LastError = GetLastError();
        v21 = 1663;
LABEL_29:
        v14 = L"failed to copy file";
LABEL_30:
        TargetDirName = LastError;
        goto LABEL_3;
      }
      if ( !DeleteFileW(v6) )
      {
        SetFileAttributesW(v6, 0x80u);
        if ( !DeleteFileW(v6) )
        {
          v19 = GetLastError();
          UnattendLogW(2, L"winreCopyWIM Could not delete %s (GLE 0X%X)", v6, v19);
        }
      }
    }
    else if ( !MoveFileExW(v6, v7, 2u) )
    {
      LastError = GetLastError();
      v14 = L"failed to move file";
      v21 = 1680;
      goto LABEL_30;
    }
    if ( StringCchCopyW(a5, 0x12Eu, v7) < 0 )
    {
      TargetDirName = 13;
      goto LABEL_49;
    }
  }
  else if ( !CopyFileW(v6, v7, 0) )
  {
    LastError = GetLastError();
    v21 = 1692;
    goto LABEL_29;
  }
  winreSetACL(v7);
  TargetDirName = winreGetBootSdiPath(a1, v6);
  if ( TargetDirName )
  {
    v21 = 1697;
    v14 = L"failed to get boot.sdi path";
    goto LABEL_3;
  }
  TargetDirName = winreAddFileToDirPath(v12, L"boot.sdi", v7);
  if ( TargetDirName )
  {
    v21 = 1701;
    v14 = L"failed to add boot.sdi to directory path";
    goto LABEL_3;
  }
  if ( (unsigned int)winreDoesFileExist(v12, L"boot.sdi") )
  {
    UnattendLogW(2, L"winreCopyWIM Deleted existing sdi file in %s", v7);
    DeleteFileW(v7);
  }
  if ( !CopyFileW(v6, v7, 0) )
  {
    LastError = GetLastError();
    v21 = 1709;
    goto LABEL_29;
  }
  TargetDirName = 0;
  winreSetACL(v7);
LABEL_49:
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( TargetDirName )
    UnattendLogW(1, L"winreCopyWIM failed: 0x%x", TargetDirName);
  return TargetDirName;
}

```

## disassembly

```asm
0x180039dd4  mov     [rsp-40h+arg_0], rcx
0x180039dd9  push    rbp
0x180039dda  push    rbx
0x180039ddb  push    rsi
0x180039ddc  push    rdi
0x180039ddd  push    r12
0x180039ddf  push    r13
0x180039de1  push    r14
0x180039de3  push    r15
0x180039de5  mov     rbp, rsp
0x180039de8  sub     rsp, 48h
0x180039dec  mov     rcx, [rbp+arg_20]
0x180039df0  xor     eax, eax
0x180039df2  xor     r14d, r14d
0x180039df5  mov     [rbp+pv], 0
0x180039dfd  xor     esi, esi
0x180039dff  mov     [rbp+lpExistingFileName], r14
0x180039e03  mov     r13d, r9d
0x180039e06  mov     [rbp+lpFileName], rsi
0x180039e0a  mov     [rcx], ax
0x180039e0d  mov     r12, r8
0x180039e10  lea     rcx, [rbp+pv]
0x180039e14  mov     rdi, rdx
0x180039e17  call    winreAllocPath
0x180039e1c  mov     r15, [rbp+pv]
0x180039e20  mov     ebx, eax
0x180039e22  test    eax, eax
0x180039e24  jz      short loc_180039E5A
0x180039e26  mov     [rsp+48h+var_20], 642h
0x180039e2e  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180039e35  mov     ecx, 2
0x180039e3a  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039e41  mov     r9d, ebx
0x180039e44  lea     rdx, aWinrecopywimS0; "winreCopyWIM %s (0x%x) in file %S line "...
0x180039e4b  mov     [rsp+48h+var_28], rax
0x180039e50  call    UnattendLogW
0x180039e55  jmp     loc_18003A1EC
0x180039e5a  lea     rcx, [rbp+lpExistingFileName]
0x180039e5e  call    winreAllocPath
0x180039e63  mov     ebx, eax
0x180039e65  test    eax, eax
0x180039e67  jz      short loc_180039EA1
0x180039e69  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039e70  mov     [rsp+48h+var_20], 643h
0x180039e78  mov     r9d, ebx
0x180039e7b  mov     [rsp+48h+var_28], rax
0x180039e80  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180039e87  mov     ecx, 2
0x180039e8c  lea     rdx, aWinrecopywimS0; "winreCopyWIM %s (0x%x) in file %S line "...
0x180039e93  call    UnattendLogW
0x180039e98  mov     r14, [rbp+lpExistingFileName]
0x180039e9c  jmp     loc_18003A1EC
0x180039ea1  lea     rcx, [rbp+lpFileName]
0x180039ea5  call    winreAllocPath
0x180039eaa  mov     ebx, eax
0x180039eac  test    eax, eax
0x180039eae  jz      short loc_180039EEC
0x180039eb0  mov     [rsp+48h+var_20], 644h
0x180039eb8  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180039ebf  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039ec6  mov     r9d, ebx
0x180039ec9  lea     rdx, aWinrecopywimS0; "winreCopyWIM %s (0x%x) in file %S line "...
0x180039ed0  mov     [rsp+48h+var_28], rax
0x180039ed5  mov     ecx, 2
0x180039eda  call    UnattendLogW
0x180039edf  mov     r14, [rbp+lpExistingFileName]
0x180039ee3  mov     rsi, [rbp+lpFileName]
0x180039ee7  jmp     loc_18003A1EC
0x180039eec  mov     r9, r15
0x180039eef  xor     r8d, r8d
0x180039ef2  mov     rcx, rdi
0x180039ef5  call    winreCreateTargetDirName
0x180039efa  mov     ebx, eax
0x180039efc  test    eax, eax
0x180039efe  jz      short loc_180039F11
0x180039f00  mov     [rsp+48h+var_20], 64Fh
0x180039f08  lea     r8, aFailedToCreate_4; "failed to create target directory name"
0x180039f0f  jmp     short loc_180039EBF
0x180039f11  mov     rcx, r15; lpFileName
0x180039f14  call    winreOpenOrCreateDir
0x180039f19  mov     ebx, eax
0x180039f1b  test    eax, eax
0x180039f1d  jz      short loc_180039F30
0x180039f1f  mov     [rsp+48h+var_20], 651h
0x180039f27  lea     r8, aFailedToCreate_30; "failed to create \\Recovery root direct"...
0x180039f2e  jmp     short loc_180039EBF
0x180039f30  mov     r9, r15
0x180039f33  mov     r8d, 1
0x180039f39  mov     rcx, rdi
0x180039f3c  call    winreCreateTargetDirName
0x180039f41  mov     ebx, eax
0x180039f43  test    eax, eax
0x180039f45  jz      short loc_180039F51
0x180039f47  mov     [rsp+48h+var_20], 65Bh
0x180039f4f  jmp     short loc_180039F08
0x180039f51  mov     rcx, r15; lpFileName
0x180039f54  call    winreOpenOrCreateDir
0x180039f59  mov     ebx, eax
0x180039f5b  test    eax, eax
0x180039f5d  jz      short loc_180039F73
0x180039f5f  mov     [rsp+48h+var_20], 660h
0x180039f67  lea     r8, aFailedToCreate_20; "failed to create temp directory"
0x180039f6e  jmp     loc_180039EBF
0x180039f73  mov     r14, [rbp+lpExistingFileName]
0x180039f77  lea     rdi, aWinreWim; "Winre.wim"
0x180039f7e  mov     rdx, r12
0x180039f81  mov     r9, r14
0x180039f84  mov     r12, [rbp+arg_0]
0x180039f88  mov     r8, rdi
0x180039f8b  mov     rcx, r12
0x180039f8e  call    winreGetSourceFile
0x180039f93  mov     ebx, eax
0x180039f95  test    eax, eax
0x180039f97  jz      short loc_180039FCD
0x180039f99  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039fa0  mov     [rsp+48h+var_20], 66Ah
0x180039fa8  mov     r9d, ebx
0x180039fab  mov     [rsp+48h+var_28], rax
0x180039fb0  lea     r8, aFailedToGetSou_1; "failed to get source file winre.wim"
0x180039fb7  mov     ecx, 2
0x180039fbc  lea     rdx, aWinrecopywimS0; "winreCopyWIM %s (0x%x) in file %S line "...
0x180039fc3  call    UnattendLogW
0x180039fc8  jmp     loc_180039EE3
0x180039fcd  mov     rsi, [rbp+lpFileName]
0x180039fd1  mov     rdx, rdi; unsigned __int16 *
0x180039fd4  mov     r8, rsi; unsigned __int16 *
0x180039fd7  mov     rcx, r15; unsigned __int16 *
0x180039fda  call    winreAddFileToDirPath
0x180039fdf  mov     ebx, eax
0x180039fe1  test    eax, eax
0x180039fe3  jz      short loc_180039FF9
0x180039fe5  mov     [rsp+48h+var_20], 66Eh
0x180039fed  lea     r8, aFailedToAddWin_0; "failed to add winre.wim to directory pa"...
0x180039ff4  jmp     loc_180039E35
0x180039ff9  mov     rdx, rdi; unsigned __int16 *
0x180039ffc  mov     rcx, r15; unsigned __int16 *
0x180039fff  call    winreDoesFileExist
0x18003a004  test    eax, eax
0x18003a006  jz      short loc_18003A022
0x18003a008  mov     rcx, rsi; lpFileName
0x18003a00b  call    cs:__imp_DeleteFileW
0x18003a011  mov     r8, rsi
0x18003a014  lea     rdx, aWinrecopywimDe_0; "winreCopyWIM Deleted existing wim file "...
0x18003a01b  xor     ecx, ecx
0x18003a01d  call    UnattendLogW
0x18003a022  mov     edi, 2
0x18003a027  mov     rcx, r14; lpFileName
0x18003a02a  test    r13d, r13d
0x18003a02d  jz      loc_18003A113
0x18003a033  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x18003a038  test    eax, eax
0x18003a03a  jz      loc_18003A0E6
0x18003a040  mov     r9, rsi
0x18003a043  lea     rdx, aWinrecopywimCo; "winreCopyWIM Copying file from %s to %s"
0x18003a04a  mov     r8, r14
0x18003a04d  xor     ecx, ecx
0x18003a04f  call    UnattendLogW
0x18003a054  xor     r8d, r8d; bFailIfExists
0x18003a057  mov     rdx, rsi; lpNewFileName
0x18003a05a  mov     rcx, r14; lpExistingFileName
0x18003a05d  call    cs:__imp_CopyFileW
0x18003a063  test    eax, eax
0x18003a065  jnz     short loc_18003A085
0x18003a067  call    cs:__imp_GetLastError
0x18003a06d  mov     [rsp+48h+var_20], 67Fh
0x18003a075  lea     r8, aFailedToCopyFi; "failed to copy file"
0x18003a07c  mov     ebx, eax
0x18003a07e  mov     ecx, edi
0x18003a080  jmp     loc_180039E3A
0x18003a085  mov     rcx, r14; lpFileName
0x18003a088  call    cs:__imp_DeleteFileW
0x18003a08e  test    eax, eax
0x18003a090  jnz     short loc_18003A0C7
0x18003a092  mov     edx, 80h; dwFileAttributes
0x18003a097  mov     rcx, r14; lpFileName
0x18003a09a  call    cs:__imp_SetFileAttributesW
0x18003a0a0  mov     rcx, r14; lpFileName
0x18003a0a3  call    cs:__imp_DeleteFileW
0x18003a0a9  test    eax, eax
0x18003a0ab  jnz     short loc_18003A0C7
0x18003a0ad  call    cs:__imp_GetLastError
0x18003a0b3  mov     r8, r14
0x18003a0b6  lea     rdx, aWinrecopywimCo_0; "winreCopyWIM Could not delete %s (GLE 0"...
0x18003a0bd  mov     r9d, eax
0x18003a0c0  mov     ecx, edi
0x18003a0c2  call    UnattendLogW
0x18003a0c7  mov     rcx, [rbp+arg_20]; unsigned __int16 *
0x18003a0cb  mov     r8, rsi; unsigned __int16 *
0x18003a0ce  mov     edx, 12Eh; unsigned __int64
0x18003a0d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a0d8  test    eax, eax
0x18003a0da  jns     short loc_18003A136
0x18003a0dc  mov     ebx, 0Dh
0x18003a0e1  jmp     loc_18003A1EC
0x18003a0e6  mov     r8d, edi; dwFlags
0x18003a0e9  mov     rdx, rsi; lpNewFileName
0x18003a0ec  mov     rcx, r14; lpExistingFileName
0x18003a0ef  call    cs:__imp_MoveFileExW
0x18003a0f5  test    eax, eax
0x18003a0f7  jnz     short loc_18003A0C7
0x18003a0f9  call    cs:__imp_GetLastError
0x18003a0ff  lea     r8, aFailedToMoveFi; "failed to move file"
0x18003a106  mov     [rsp+48h+var_20], 690h
0x18003a10e  jmp     loc_18003A07C
0x18003a113  xor     r8d, r8d; bFailIfExists
0x18003a116  mov     rdx, rsi; lpNewFileName
0x18003a119  call    cs:__imp_CopyFileW
0x18003a11f  test    eax, eax
0x18003a121  jnz     short loc_18003A136
0x18003a123  call    cs:__imp_GetLastError
0x18003a129  mov     [rsp+48h+var_20], 69Ch
0x18003a131  jmp     loc_18003A075
0x18003a136  mov     rcx, rsi; lpFileName
0x18003a139  call    winreSetACL
0x18003a13e  mov     rdx, r14
0x18003a141  mov     rcx, r12
0x18003a144  call    winreGetBootSdiPath
0x18003a149  mov     ebx, eax
0x18003a14b  test    eax, eax
0x18003a14d  jz      short loc_18003A163
0x18003a14f  mov     [rsp+48h+var_20], 6A1h
0x18003a157  lea     r8, aFailedToGetBoo_0; "failed to get boot.sdi path"
0x18003a15e  jmp     loc_18003A07E
0x18003a163  mov     r8, rsi; unsigned __int16 *
0x18003a166  lea     rdx, aBootSdi; "boot.sdi"
0x18003a16d  mov     rcx, r15; unsigned __int16 *
0x18003a170  call    winreAddFileToDirPath
0x18003a175  mov     ebx, eax
0x18003a177  test    eax, eax
0x18003a179  jz      short loc_18003A18F
0x18003a17b  mov     [rsp+48h+var_20], 6A5h
0x18003a183  lea     r8, aFailedToAddBoo_0; "failed to add boot.sdi to directory pat"...
0x18003a18a  jmp     loc_18003A07E
0x18003a18f  lea     rdx, aBootSdi; "boot.sdi"
0x18003a196  mov     rcx, r15; unsigned __int16 *
0x18003a199  call    winreDoesFileExist
0x18003a19e  test    eax, eax
0x18003a1a0  jz      short loc_18003A1BC
0x18003a1a2  mov     r8, rsi
0x18003a1a5  lea     rdx, aWinrecopywimDe; "winreCopyWIM Deleted existing sdi file "...
0x18003a1ac  mov     ecx, edi
0x18003a1ae  call    UnattendLogW
0x18003a1b3  mov     rcx, rsi; lpFileName
0x18003a1b6  call    cs:__imp_DeleteFileW
0x18003a1bc  xor     r8d, r8d; bFailIfExists
0x18003a1bf  mov     rdx, rsi; lpNewFileName
0x18003a1c2  mov     rcx, r14; lpExistingFileName
0x18003a1c5  call    cs:__imp_CopyFileW
0x18003a1cb  test    eax, eax
0x18003a1cd  jnz     short loc_18003A1E2
0x18003a1cf  call    cs:__imp_GetLastError
0x18003a1d5  mov     [rsp+48h+var_20], 6ADh
0x18003a1dd  jmp     loc_18003A075
0x18003a1e2  xor     ebx, ebx
0x18003a1e4  mov     rcx, rsi; lpFileName
0x18003a1e7  call    winreSetACL
0x18003a1ec  test    r15, r15
0x18003a1ef  jz      short loc_18003A1FA
0x18003a1f1  mov     rcx, r15; pv
0x18003a1f4  call    cs:__imp_CoTaskMemFree
0x18003a1fa  test    r14, r14
0x18003a1fd  jz      short loc_18003A208
0x18003a1ff  mov     rcx, r14; pv
0x18003a202  call    cs:__imp_CoTaskMemFree
0x18003a208  test    rsi, rsi
0x18003a20b  jz      short loc_18003A216
0x18003a20d  mov     rcx, rsi; pv
0x18003a210  call    cs:__imp_CoTaskMemFree
0x18003a216  test    ebx, ebx
0x18003a218  jz      short loc_18003A22E
0x18003a21a  mov     r8d, ebx
0x18003a21d  lea     rdx, aWinrecopywimFa_0; "winreCopyWIM failed: 0x%x"
0x18003a224  mov     ecx, 1
0x18003a229  call    UnattendLogW
0x18003a22e  mov     eax, ebx
0x18003a230  add     rsp, 48h
0x18003a234  pop     r15
0x18003a236  pop     r14
0x18003a238  pop     r13
0x18003a23a  pop     r12
0x18003a23c  pop     rdi
0x18003a23d  pop     rsi
0x18003a23e  pop     rbx
0x18003a23f  pop     rbp
0x18003a240  retn
```
