# winreCopyWIMFile

- ea: `0x18003aac0`
- end: `0x18003adc9`
- name: `winreCopyWIMFile`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x180019a90`

## callees

- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x1800103f4`
- `0x1800297cc`
- `0x180031434`
- `0x1800322a8`
- `0x180032728`
- `0x18003aac0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18003ac8c`
- `KERNEL32!CopyFileW` at `0x18003ad46`
- `KERNEL32!CopyFileW` at `0x18003ac8c`
- `KERNEL32!CopyFileW` at `0x18003ad46`
- `KERNEL32!GetLastError` at `0x18003ac96`
- `KERNEL32!GetLastError` at `0x18003ad50`
- `KERNEL32!GetLastError` at `0x18003ac96`
- `KERNEL32!GetLastError` at `0x18003ad50`
- `KERNEL32!DeleteFileW` at `0x18003ac6c`
- `KERNEL32!DeleteFileW` at `0x18003ad36`
- `KERNEL32!DeleteFileW` at `0x18003ac6c`
- `KERNEL32!DeleteFileW` at `0x18003ad36`
- `ole32!CoTaskMemFree` at `0x18003ad75`
- `ole32!CoTaskMemFree` at `0x18003ad84`
- `ole32!CoTaskMemFree` at `0x18003ad92`
- `ole32!CoTaskMemFree` at `0x18003ad75`
- `ole32!CoTaskMemFree` at `0x18003ad84`
- `ole32!CoTaskMemFree` at `0x18003ad92`

## string_xrefs

- `0x18003ab13`: `failed to allocate path`
- `0x18003ab6f`: `failed to allocate path`
- `0x18003ac4a`: `failed to add winre.wim to directory path`
- `0x18003aca6`: `failed to copy file`
- `0x18003ad00`: `failed to add boot.sdi to directory path`
- `0x18003ab1a`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003ab76`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003abbb`: `failed to create target directory name`
- `0x18003abda`: `failed to create \Recovery root directory`
- `0x18003ac1a`: `failed to create temp directory`
- `0x18003acd4`: `failed to get boot.sdi path`
- `0x18003ab24`: `winreCopyWIMFile %s (0x%x) in file %S line %d`
- `0x18003ab80`: `winreCopyWIMFile %s (0x%x) in file %S line %d`
- `0x18003ac75`: `winreCopyWIMFile Deleted existing wim file in %s`
- `0x18003ad22`: `winreCopyWIMFile Deleted existing sdi file in %s`
- `0x18003ad9f`: `winreCopyWIMFile failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCopyWIMFile(struct _GUID *a1, __int64 a2, const WCHAR *a3)
{
  WCHAR *v4; // rdi
  DWORD v7; // eax
  WCHAR *v8; // rsi
  DWORD TargetDirName; // ebx
  const wchar_t *v10; // r8
  __int64 v11; // rdx
  const wchar_t *v12; // r8
  __int64 v13; // rdx
  DWORD LastError; // eax
  int v16; // [rsp+28h] [rbp-18h]
  int v17; // [rsp+28h] [rbp-18h]
  LPCWSTR lpExistingFileName; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-8h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp+48h] BYREF

  pv = 0;
  v4 = 0;
  lpExistingFileName = 0;
  lpFileName = 0;
  v7 = winreAllocPath(&pv);
  v8 = (WCHAR *)pv;
  TargetDirName = v7;
  if ( v7 )
  {
    v16 = 1741;
LABEL_3:
    v10 = L"failed to allocate path";
LABEL_4:
    UnattendLogW(
      2,
      L"winreCopyWIMFile %s (0x%x) in file %S line %d",
      v10,
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v16);
    goto LABEL_35;
  }
  TargetDirName = winreAllocPath(&lpExistingFileName);
  if ( TargetDirName )
  {
    v16 = 1742;
    goto LABEL_3;
  }
  TargetDirName = winreAllocPath(&lpFileName);
  if ( TargetDirName )
  {
    v17 = 1743;
    v12 = L"failed to allocate path";
LABEL_9:
    UnattendLogW(
      2,
      L"winreCopyWIMFile %s (0x%x) in file %S line %d",
      v12,
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v17);
    v4 = (WCHAR *)lpFileName;
    goto LABEL_35;
  }
  TargetDirName = winreCreateTargetDirName(a2, v11, 0, v8);
  if ( TargetDirName )
  {
    v17 = 1754;
LABEL_12:
    v12 = L"failed to create target directory name";
    goto LABEL_9;
  }
  TargetDirName = winreOpenOrCreateDir(v8);
  if ( TargetDirName )
  {
    v17 = 1756;
    v12 = L"failed to create \\Recovery root directory";
    goto LABEL_9;
  }
  TargetDirName = winreCreateTargetDirName(a2, v13, 1, v8);
  if ( TargetDirName )
  {
    v17 = 1766;
    goto LABEL_12;
  }
  TargetDirName = winreOpenOrCreateDir(v8);
  if ( TargetDirName )
  {
    v17 = 1771;
    v12 = L"failed to create temp directory";
    goto LABEL_9;
  }
  v4 = (WCHAR *)lpFileName;
  TargetDirName = winreAddFileToDirPath(v8, L"Winre.wim", (unsigned __int16 *)lpFileName);
  if ( TargetDirName )
  {
    v16 = 1779;
    v10 = L"failed to add winre.wim to directory path";
    goto LABEL_4;
  }
  if ( (unsigned int)winreDoesFileExist(v8, L"Winre.wim") )
  {
    DeleteFileW(v4);
    UnattendLogW(0, L"winreCopyWIMFile Deleted existing wim file in %s", v4);
  }
  if ( !CopyFileW(a3, v4, 0) )
  {
    LastError = GetLastError();
    v16 = 1791;
LABEL_25:
    TargetDirName = LastError;
    v10 = L"failed to copy file";
    goto LABEL_4;
  }
  winreSetACL(v4);
  TargetDirName = winreGetBootSdiPath(a1, (unsigned __int16 *)lpExistingFileName);
  if ( TargetDirName )
  {
    v16 = 1795;
    v10 = L"failed to get boot.sdi path";
    goto LABEL_4;
  }
  TargetDirName = winreAddFileToDirPath(v8, L"boot.sdi", v4);
  if ( TargetDirName )
  {
    v16 = 1799;
    v10 = L"failed to add boot.sdi to directory path";
    goto LABEL_4;
  }
  if ( (unsigned int)winreDoesFileExist(v8, L"boot.sdi") )
  {
    UnattendLogW(2, L"winreCopyWIMFile Deleted existing sdi file in %s", v4);
    DeleteFileW(v4);
  }
  if ( !CopyFileW(lpExistingFileName, v4, 0) )
  {
    LastError = GetLastError();
    v16 = 1807;
    goto LABEL_25;
  }
  TargetDirName = 0;
  winreSetACL(v4);
LABEL_35:
  if ( v8 )
    CoTaskMemFree(v8);
  if ( lpExistingFileName )
    CoTaskMemFree((LPVOID)lpExistingFileName);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( TargetDirName )
    UnattendLogW(1, L"winreCopyWIMFile failed: 0x%x", TargetDirName);
  return TargetDirName;
}

```

## disassembly

```asm
0x18003aac0  mov     [rsp-28h+arg_0], rbx
0x18003aac5  mov     [rsp-28h+arg_8], rsi
0x18003aaca  push    rbp
0x18003aacb  push    rdi
0x18003aacc  push    r12
0x18003aace  push    r14
0x18003aad0  push    r15
0x18003aad2  mov     rbp, rsp
0x18003aad5  sub     rsp, 40h
0x18003aad9  mov     r12, rcx
0x18003aadc  mov     [rbp+pv], 0
0x18003aae4  xor     edi, edi
0x18003aae6  mov     [rbp+lpExistingFileName], 0
0x18003aaee  lea     rcx, [rbp+pv]
0x18003aaf2  mov     [rbp+lpFileName], rdi
0x18003aaf6  mov     r15, r8
0x18003aaf9  mov     r14, rdx
0x18003aafc  call    winreAllocPath
0x18003ab01  mov     rsi, [rbp+pv]
0x18003ab05  mov     ebx, eax
0x18003ab07  test    eax, eax
0x18003ab09  jz      short loc_18003AB3F
0x18003ab0b  mov     [rsp+40h+var_18], 6CDh
0x18003ab13  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18003ab1a  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003ab21  mov     r9d, ebx
0x18003ab24  lea     rdx, aWinrecopywimfi_3; "winreCopyWIMFile %s (0x%x) in file %S l"...
0x18003ab2b  mov     [rsp+40h+var_20], rax
0x18003ab30  mov     ecx, 2
0x18003ab35  call    UnattendLogW
0x18003ab3a  jmp     loc_18003AD6D
0x18003ab3f  lea     rcx, [rbp+lpExistingFileName]
0x18003ab43  call    winreAllocPath
0x18003ab48  mov     ebx, eax
0x18003ab4a  test    eax, eax
0x18003ab4c  jz      short loc_18003AB58
0x18003ab4e  mov     [rsp+40h+var_18], 6CEh
0x18003ab56  jmp     short loc_18003AB13
0x18003ab58  lea     rcx, [rbp+lpFileName]
0x18003ab5c  call    winreAllocPath
0x18003ab61  mov     ebx, eax
0x18003ab63  test    eax, eax
0x18003ab65  jz      short loc_18003AB9F
0x18003ab67  mov     [rsp+40h+var_18], 6CFh
0x18003ab6f  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18003ab76  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003ab7d  mov     r9d, ebx
0x18003ab80  lea     rdx, aWinrecopywimfi_3; "winreCopyWIMFile %s (0x%x) in file %S l"...
0x18003ab87  mov     [rsp+40h+var_20], rax
0x18003ab8c  mov     ecx, 2
0x18003ab91  call    UnattendLogW
0x18003ab96  mov     rdi, [rbp+lpFileName]
0x18003ab9a  jmp     loc_18003AD6D
0x18003ab9f  mov     r9, rsi
0x18003aba2  xor     r8d, r8d
0x18003aba5  mov     rcx, r14
0x18003aba8  call    winreCreateTargetDirName
0x18003abad  mov     ebx, eax
0x18003abaf  test    eax, eax
0x18003abb1  jz      short loc_18003ABC4
0x18003abb3  mov     [rsp+40h+var_18], 6DAh
0x18003abbb  lea     r8, aFailedToCreate_4; "failed to create target directory name"
0x18003abc2  jmp     short loc_18003AB76
0x18003abc4  mov     rcx, rsi; lpFileName
0x18003abc7  call    winreOpenOrCreateDir
0x18003abcc  mov     ebx, eax
0x18003abce  test    eax, eax
0x18003abd0  jz      short loc_18003ABE3
0x18003abd2  mov     [rsp+40h+var_18], 6DCh
0x18003abda  lea     r8, aFailedToCreate_30; "failed to create \\Recovery root direct"...
0x18003abe1  jmp     short loc_18003AB76
0x18003abe3  mov     r9, rsi
0x18003abe6  mov     r8d, 1
0x18003abec  mov     rcx, r14
0x18003abef  call    winreCreateTargetDirName
0x18003abf4  mov     ebx, eax
0x18003abf6  test    eax, eax
0x18003abf8  jz      short loc_18003AC04
0x18003abfa  mov     [rsp+40h+var_18], 6E6h
0x18003ac02  jmp     short loc_18003ABBB
0x18003ac04  mov     rcx, rsi; lpFileName
0x18003ac07  call    winreOpenOrCreateDir
0x18003ac0c  mov     ebx, eax
0x18003ac0e  test    eax, eax
0x18003ac10  jz      short loc_18003AC26
0x18003ac12  mov     [rsp+40h+var_18], 6EBh
0x18003ac1a  lea     r8, aFailedToCreate_20; "failed to create temp directory"
0x18003ac21  jmp     loc_18003AB76
0x18003ac26  mov     rdi, [rbp+lpFileName]
0x18003ac2a  lea     rdx, aWinreWim; "Winre.wim"
0x18003ac31  mov     r8, rdi; unsigned __int16 *
0x18003ac34  mov     rcx, rsi; unsigned __int16 *
0x18003ac37  call    winreAddFileToDirPath
0x18003ac3c  mov     ebx, eax
0x18003ac3e  test    eax, eax
0x18003ac40  jz      short loc_18003AC56
0x18003ac42  mov     [rsp+40h+var_18], 6F3h
0x18003ac4a  lea     r8, aFailedToAddWin_0; "failed to add winre.wim to directory pa"...
0x18003ac51  jmp     loc_18003AB1A
0x18003ac56  lea     rdx, aWinreWim; "Winre.wim"
0x18003ac5d  mov     rcx, rsi; unsigned __int16 *
0x18003ac60  call    winreDoesFileExist
0x18003ac65  test    eax, eax
0x18003ac67  jz      short loc_18003AC83
0x18003ac69  mov     rcx, rdi; lpFileName
0x18003ac6c  call    cs:__imp_DeleteFileW
0x18003ac72  mov     r8, rdi
0x18003ac75  lea     rdx, aWinrecopywimfi; "winreCopyWIMFile Deleted existing wim f"...
0x18003ac7c  xor     ecx, ecx
0x18003ac7e  call    UnattendLogW
0x18003ac83  xor     r8d, r8d; bFailIfExists
0x18003ac86  mov     rdx, rdi; lpNewFileName
0x18003ac89  mov     rcx, r15; lpExistingFileName
0x18003ac8c  call    cs:__imp_CopyFileW
0x18003ac92  test    eax, eax
0x18003ac94  jnz     short loc_18003ACB2
0x18003ac96  call    cs:__imp_GetLastError
0x18003ac9c  mov     [rsp+40h+var_18], 6FFh
0x18003aca4  mov     ebx, eax
0x18003aca6  lea     r8, aFailedToCopyFi; "failed to copy file"
0x18003acad  jmp     loc_18003AB1A
0x18003acb2  mov     rcx, rdi; lpFileName
0x18003acb5  call    winreSetACL
0x18003acba  mov     rdx, [rbp+lpExistingFileName]
0x18003acbe  mov     rcx, r12
0x18003acc1  call    winreGetBootSdiPath
0x18003acc6  mov     ebx, eax
0x18003acc8  test    eax, eax
0x18003acca  jz      short loc_18003ACE0
0x18003accc  mov     [rsp+40h+var_18], 703h
0x18003acd4  lea     r8, aFailedToGetBoo_0; "failed to get boot.sdi path"
0x18003acdb  jmp     loc_18003AB1A
0x18003ace0  mov     r8, rdi; unsigned __int16 *
0x18003ace3  lea     rdx, aBootSdi; "boot.sdi"
0x18003acea  mov     rcx, rsi; unsigned __int16 *
0x18003aced  call    winreAddFileToDirPath
0x18003acf2  mov     ebx, eax
0x18003acf4  test    eax, eax
0x18003acf6  jz      short loc_18003AD0C
0x18003acf8  mov     [rsp+40h+var_18], 707h
0x18003ad00  lea     r8, aFailedToAddBoo_0; "failed to add boot.sdi to directory pat"...
0x18003ad07  jmp     loc_18003AB1A
0x18003ad0c  lea     rdx, aBootSdi; "boot.sdi"
0x18003ad13  mov     rcx, rsi; unsigned __int16 *
0x18003ad16  call    winreDoesFileExist
0x18003ad1b  test    eax, eax
0x18003ad1d  jz      short loc_18003AD3C
0x18003ad1f  mov     r8, rdi
0x18003ad22  lea     rdx, aWinrecopywimfi_2; "winreCopyWIMFile Deleted existing sdi f"...
0x18003ad29  mov     ecx, 2
0x18003ad2e  call    UnattendLogW
0x18003ad33  mov     rcx, rdi; lpFileName
0x18003ad36  call    cs:__imp_DeleteFileW
0x18003ad3c  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x18003ad40  xor     r8d, r8d; bFailIfExists
0x18003ad43  mov     rdx, rdi; lpNewFileName
0x18003ad46  call    cs:__imp_CopyFileW
0x18003ad4c  test    eax, eax
0x18003ad4e  jnz     short loc_18003AD63
0x18003ad50  call    cs:__imp_GetLastError
0x18003ad56  mov     [rsp+40h+var_18], 70Fh
0x18003ad5e  jmp     loc_18003ACA4
0x18003ad63  xor     ebx, ebx
0x18003ad65  mov     rcx, rdi; lpFileName
0x18003ad68  call    winreSetACL
0x18003ad6d  test    rsi, rsi
0x18003ad70  jz      short loc_18003AD7B
0x18003ad72  mov     rcx, rsi; pv
0x18003ad75  call    cs:__imp_CoTaskMemFree
0x18003ad7b  mov     rcx, [rbp+lpExistingFileName]; pv
0x18003ad7f  test    rcx, rcx
0x18003ad82  jz      short loc_18003AD8A
0x18003ad84  call    cs:__imp_CoTaskMemFree
0x18003ad8a  test    rdi, rdi
0x18003ad8d  jz      short loc_18003AD98
0x18003ad8f  mov     rcx, rdi; pv
0x18003ad92  call    cs:__imp_CoTaskMemFree
0x18003ad98  test    ebx, ebx
0x18003ad9a  jz      short loc_18003ADB0
0x18003ad9c  mov     r8d, ebx
0x18003ad9f  lea     rdx, aWinrecopywimfi_0; "winreCopyWIMFile failed: 0x%x"
0x18003ada6  mov     ecx, 1
0x18003adab  call    UnattendLogW
0x18003adb0  mov     rsi, [rsp+40h+arg_8]
0x18003adb5  mov     eax, ebx
0x18003adb7  mov     rbx, [rsp+40h+arg_0]
0x18003adbc  add     rsp, 40h
0x18003adc0  pop     r15
0x18003adc2  pop     r14
0x18003adc4  pop     r12
0x18003adc6  pop     rdi
0x18003adc7  pop     rbp
0x18003adc8  retn
```
