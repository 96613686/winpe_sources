# winreCopyWIMBack

- ea: `0x18003a248`
- end: `0x18003a771`
- name: `winreCopyWIMBack`
- size: `1321`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x1800174a0`
- `0x18001fd7c`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000fe58`
- `0x18000ff68`
- `0x18000ffcc`
- `0x1800103f4`
- `0x18001051c`
- `0x1800322a8`
- `0x18003a248`
- `0x18003bea8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003a47a`
- `msvcrt!_wcsicmp` at `0x18003a47a`
- `KERNEL32!GetLastError` at `0x18003a51b`
- `KERNEL32!GetLastError` at `0x18003a51b`
- `KERNEL32!RemoveDirectoryW` at `0x18003a60a`
- `KERNEL32!RemoveDirectoryW` at `0x18003a60a`
- `KERNEL32!MoveFileExW` at `0x18003a511`
- `KERNEL32!MoveFileExW` at `0x18003a511`
- `KERNEL32!DeleteFileW` at `0x18003a591`
- `KERNEL32!DeleteFileW` at `0x18003a5c9`
- `KERNEL32!DeleteFileW` at `0x18003a601`
- `KERNEL32!DeleteFileW` at `0x18003a640`
- `KERNEL32!DeleteFileW` at `0x18003a675`
- `KERNEL32!DeleteFileW` at `0x18003a6fc`
- `KERNEL32!DeleteFileW` at `0x18003a591`
- `KERNEL32!DeleteFileW` at `0x18003a5c9`
- `KERNEL32!DeleteFileW` at `0x18003a601`
- `KERNEL32!DeleteFileW` at `0x18003a640`
- `KERNEL32!DeleteFileW` at `0x18003a675`
- `KERNEL32!DeleteFileW` at `0x18003a6fc`
- `ole32!CoTaskMemFree` at `0x18003a735`
- `ole32!CoTaskMemFree` at `0x18003a743`
- `ole32!CoTaskMemFree` at `0x18003a751`
- `ole32!CoTaskMemFree` at `0x18003a735`
- `ole32!CoTaskMemFree` at `0x18003a743`
- `ole32!CoTaskMemFree` at `0x18003a751`

## string_xrefs

- `0x18003a2a2`: `failed to allocate path`
- `0x18003a2e8`: `failed to allocate path`
- `0x18003a39e`: `failed to find main os config directory`
- `0x18003a4f9`: `failed to add winre.wim to directory path`
- `0x18003a49e`: `failed to create directory`
- `0x18003a529`: `failed to move file`
- `0x18003a28b`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a2d1`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a387`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a3eb`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a539`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a6a5`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a453`: `failed to copy image location path`
- `0x18003a2a9`: `winreCopyWIMBack %s (0x%x) in file %S line %d`
- `0x18003a2f4`: `winreCopyWIMBack %s (0x%x) in file %S line %d`
- `0x18003a3aa`: `winreCopyWIMBack %s (0x%x) in file %S line %d`
- `0x18003a3f5`: `winreCopyWIMBack %s (0x%x) in file %S line %d`
- `0x18003a532`: `winreCopyWIMBack %s (0x%x) in file %S line %d`
- `0x18003a6af`: `winreCopyWIMBack %s (0x%x) in file %S line %d`
- `0x18003a3e4`: `failed to copy winre location path`
- `0x18003a4cd`: `failed to get the path of winre.wim`
- `0x18003a5ba`: `failed to get config file`
- `0x18003a669`: `failed to get source file config file`
- `0x18003a6da`: `winreCopyWIMBack failed to move WIM file from %s to %s: 0x%x`
- `0x18003a710`: `winreCopyWIMBack moved WIM file from %s to %s successfully!`
- `0x18003a5d2`: `ReCustomization.xml`
- `0x18003a67e`: `ReCustomization.xml`
- `0x18003a59a`: `ReAgent.xml`
- `0x18003a649`: `ReAgent.xml`

## pseudocode

```c
__int64 __fastcall winreCopyWIMBack(struct _GUID *a1, __int64 a2)
{
  unsigned __int16 *v3; // r14
  __int64 LastError; // rbx
  unsigned __int16 *v6; // rdi
  unsigned __int16 *v7; // rsi
  int DoesFileExist; // eax
  unsigned __int16 *v9; // r12
  const wchar_t *v10; // r8
  const wchar_t *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r9
  __int64 v17; // [rsp+20h] [rbp-20h]
  int v18; // [rsp+28h] [rbp-18h]
  int v19; // [rsp+28h] [rbp-18h]
  wchar_t *String1; // [rsp+90h] [rbp+50h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  String1 = 0;
  String2 = 0;
  LODWORD(LastError) = winreAllocPath(&String1);
  if ( (_DWORD)LastError )
  {
    UnattendLogW(
      2,
      L"winreCopyWIMBack %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      2445);
    v6 = String1;
LABEL_49:
    v12 = L"NULL";
    LODWORD(v17) = LastError;
    v13 = L"NULL";
    if ( v3 )
      v13 = v3;
    if ( a2 != -16 )
      v12 = (const unsigned __int16 *)(a2 + 16);
    UnattendLogW(1, L"winreCopyWIMBack failed to move WIM file from %s to %s: 0x%x", v12, v13, v17);
    goto LABEL_60;
  }
  LODWORD(LastError) = winreAllocPath(&String2);
  if ( (_DWORD)LastError )
  {
    UnattendLogW(
      2,
      L"winreCopyWIMBack %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      2446);
    v6 = String1;
    v3 = String2;
    goto LABEL_49;
  }
  v7 = (unsigned __int16 *)(a2 + 16);
  DoesFileExist = winreDoesFileExist((unsigned __int16 *)(a2 + 16), L"Winre.wim");
  v6 = String1;
  v3 = String2;
  if ( !DoesFileExist )
  {
    UnattendLogW(2, L"winre.wim is not available under %s", v7);
    goto LABEL_55;
  }
  if ( !(unsigned int)winreDoesFileExist(v7, L"boot.sdi") )
  {
    UnattendLogW(2, L"boot.sdi is not available under %s", v7);
    goto LABEL_55;
  }
  v9 = (unsigned __int16 *)(a2 + 1256);
  if ( !*(_WORD *)(a2 + 1256) )
  {
    LODWORD(LastError) = winreFindMainOsConfigDir(a1);
    if ( (_DWORD)LastError )
    {
      UnattendLogW(
        2,
        L"winreCopyWIMBack %s (0x%x) in file %S line %d",
        L"failed to find main os config directory",
        (unsigned int)LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        2469);
      goto LABEL_49;
    }
    v9 = 0;
  }
  LODWORD(LastError) = StringCchCopyW(v6, 0x12Eu, v7);
  if ( (int)LastError < 0 )
  {
    v18 = 2483;
    v10 = L"failed to copy winre location path";
LABEL_15:
    UnattendLogW(
      2,
      L"winreCopyWIMBack %s (0x%x) in file %S line %d",
      v10,
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v18);
    LODWORD(LastError) = (unsigned __int16)LastError;
    goto LABEL_32;
  }
  LODWORD(LastError) = winreAddTrailingBackslash(v6);
  if ( (_DWORD)LastError )
  {
    v19 = 2485;
LABEL_18:
    v11 = L"failed to add trailing back slash";
    goto LABEL_48;
  }
  LODWORD(LastError) = StringCchCopyW(v3, 0x12Eu, v9);
  if ( (int)LastError < 0 )
  {
    v18 = 2489;
    v10 = L"failed to copy image location path";
    goto LABEL_15;
  }
  LODWORD(LastError) = winreAddTrailingBackslash(v3);
  if ( (_DWORD)LastError )
  {
    v19 = 2491;
    goto LABEL_18;
  }
  if ( !_wcsicmp(v6, v3) )
  {
    LODWORD(LastError) = winreGetSourceFile(a1, v7, L"boot.sdi", v6);
    if ( (_DWORD)LastError )
    {
      v19 = 2558;
      goto LABEL_36;
    }
    DeleteFileW(v6);
    LODWORD(LastError) = winreGetSourceFile(a1, v7, L"ReAgent.xml", v6);
    if ( (_DWORD)LastError )
    {
      v19 = 2564;
      v11 = L"failed to get source file config file";
    }
    else
    {
      DeleteFileW(v6);
      LODWORD(LastError) = winreGetSourceFile(a1, v7, L"ReCustomization.xml", v6);
      if ( !(_DWORD)LastError )
      {
        DeleteFileW(v6);
        goto LABEL_55;
      }
      v19 = 2570;
      v11 = L"failed to get customization file";
    }
LABEL_48:
    UnattendLogW(
      2,
      L"winreCopyWIMBack %s (0x%x) in file %S line %d",
      v11,
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v19);
    goto LABEL_49;
  }
  LODWORD(LastError) = winreOpenOrCreateDir(v9);
  if ( (_DWORD)LastError )
  {
    v19 = 2499;
    v11 = L"failed to create directory";
    goto LABEL_48;
  }
  LODWORD(LastError) = winreGetSourceFile(a1, v7, L"Winre.wim", v6);
  if ( (_DWORD)LastError )
  {
    v19 = 2508;
    v11 = L"failed to get the path of winre.wim";
    goto LABEL_48;
  }
  LODWORD(LastError) = winreAddFileToDirPath(v9, L"Winre.wim", v3);
  if ( (_DWORD)LastError )
  {
    v19 = 2512;
    v11 = L"failed to add winre.wim to directory path";
    goto LABEL_48;
  }
  if ( MoveFileExW(v6, v3, 3u) )
  {
    LODWORD(LastError) = winreGetSourceFile(a1, v7, L"boot.sdi", v6);
    if ( (_DWORD)LastError )
    {
      v19 = 2524;
LABEL_36:
      v11 = L"failed to get source file boot.sdi";
      goto LABEL_48;
    }
    DeleteFileW(v6);
    LODWORD(LastError) = winreGetSourceFile(a1, v7, L"ReAgent.xml", v6);
    if ( (_DWORD)LastError )
    {
      v19 = 2534;
      v11 = L"failed to get config file";
    }
    else
    {
      DeleteFileW(v6);
      LODWORD(LastError) = winreGetSourceFile(a1, v7, L"ReCustomization.xml", v6);
      if ( !(_DWORD)LastError )
      {
        DeleteFileW(v6);
        RemoveDirectoryW(v7);
        goto LABEL_55;
      }
      v19 = 2543;
      v11 = L"failed to get OEM customization file";
    }
    goto LABEL_48;
  }
  LastError = GetLastError();
  UnattendLogW(
    2,
    L"winreCopyWIMBack %s (0x%x) in file %S line %d",
    L"failed to move file",
    LastError,
    "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
    2516);
LABEL_32:
  if ( (_DWORD)LastError )
    goto LABEL_49;
LABEL_55:
  v14 = L"NULL";
  v15 = L"NULL";
  if ( v3 )
    v15 = v3;
  if ( a2 != -16 )
    v14 = (const unsigned __int16 *)(a2 + 16);
  UnattendLogW(0, L"winreCopyWIMBack moved WIM file from %s to %s successfully!", v14, v15);
LABEL_60:
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003a248  mov     [rsp-38h+arg_0], rbx
0x18003a24d  mov     [rsp-38h+arg_8], rdx
0x18003a252  push    rbp
0x18003a253  push    rsi
0x18003a254  push    rdi
0x18003a255  push    r12
0x18003a257  push    r13
0x18003a259  push    r14
0x18003a25b  push    r15
0x18003a25d  mov     rbp, rsp
0x18003a260  sub     rsp, 40h
0x18003a264  mov     r15, rcx
0x18003a267  xor     r13d, r13d
0x18003a26a  xor     r14d, r14d
0x18003a26d  mov     [rbp+var_10], r13
0x18003a271  lea     rcx, [rbp+String1]
0x18003a275  mov     [rbp+String1], r13
0x18003a279  mov     [rbp+String2], r14
0x18003a27d  mov     rdi, rdx
0x18003a280  call    winreAllocPath
0x18003a285  mov     ebx, eax
0x18003a287  test    eax, eax
0x18003a289  jz      short loc_18003A2C2
0x18003a28b  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a292  mov     [rsp+40h+var_18], 98Dh
0x18003a29a  mov     r9d, ebx
0x18003a29d  mov     [rsp+40h+var_20], rax
0x18003a2a2  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18003a2a9  lea     rdx, aWinrecopywimba_3; "winreCopyWIMBack %s (0x%x) in file %S l"...
0x18003a2b0  lea     ecx, [r13+2]
0x18003a2b4  call    UnattendLogW
0x18003a2b9  mov     rdi, [rbp+String1]
0x18003a2bd  jmp     loc_18003A6C5
0x18003a2c2  lea     rcx, [rbp+String2]
0x18003a2c6  call    winreAllocPath
0x18003a2cb  mov     ebx, eax
0x18003a2cd  test    eax, eax
0x18003a2cf  jz      short loc_18003A30D
0x18003a2d1  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a2d8  mov     [rsp+40h+var_18], 98Eh
0x18003a2e0  mov     r9d, ebx
0x18003a2e3  mov     [rsp+40h+var_20], rax
0x18003a2e8  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18003a2ef  mov     ecx, 2
0x18003a2f4  lea     rdx, aWinrecopywimba_3; "winreCopyWIMBack %s (0x%x) in file %S l"...
0x18003a2fb  call    UnattendLogW
0x18003a300  mov     rdi, [rbp+String1]
0x18003a304  mov     r14, [rbp+String2]
0x18003a308  jmp     loc_18003A6C5
0x18003a30d  lea     rsi, [rdi+10h]
0x18003a311  mov     rcx, rsi; unsigned __int16 *
0x18003a314  lea     rdx, aWinreWim; "Winre.wim"
0x18003a31b  call    winreDoesFileExist
0x18003a320  mov     rdi, [rbp+String1]
0x18003a324  mov     r14, [rbp+String2]
0x18003a328  test    eax, eax
0x18003a32a  jnz     short loc_18003A345
0x18003a32c  lea     rdx, aWinreWimIsNotA; "winre.wim is not available under %s"
0x18003a333  mov     r8, rsi
0x18003a336  mov     ecx, 2
0x18003a33b  call    UnattendLogW
0x18003a340  jmp     loc_18003A702
0x18003a345  lea     rdx, aBootSdi; "boot.sdi"
0x18003a34c  mov     rcx, rsi; unsigned __int16 *
0x18003a34f  call    winreDoesFileExist
0x18003a354  test    eax, eax
0x18003a356  jnz     short loc_18003A361
0x18003a358  lea     rdx, aBootSdiIsNotAv; "boot.sdi is not available under %s"
0x18003a35f  jmp     short loc_18003A333
0x18003a361  mov     r12, [rbp+arg_8]
0x18003a365  xor     eax, eax
0x18003a367  add     r12, 4E8h
0x18003a36e  cmp     ax, [r12]
0x18003a373  jnz     short loc_18003A3C6
0x18003a375  lea     rdx, [rbp+var_10]
0x18003a379  mov     rcx, r15
0x18003a37c  call    winreFindMainOsConfigDir
0x18003a381  mov     ebx, eax
0x18003a383  test    eax, eax
0x18003a385  jz      short loc_18003A3BF
0x18003a387  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a38e  mov     [rsp+40h+var_18], 9A5h
0x18003a396  mov     r9d, ebx
0x18003a399  mov     [rsp+40h+var_20], rax
0x18003a39e  lea     r8, aFailedToFindMa; "failed to find main os config directory"
0x18003a3a5  mov     ecx, 2
0x18003a3aa  lea     rdx, aWinrecopywimba_3; "winreCopyWIMBack %s (0x%x) in file %S l"...
0x18003a3b1  call    UnattendLogW
0x18003a3b6  mov     r13, [rbp+var_10]
0x18003a3ba  jmp     loc_18003A6C5
0x18003a3bf  mov     r13, [rbp+var_10]
0x18003a3c3  mov     r12, r13
0x18003a3c6  mov     r8, rsi; unsigned __int16 *
0x18003a3c9  mov     edx, 12Eh; unsigned __int64
0x18003a3ce  mov     rcx, rdi; unsigned __int16 *
0x18003a3d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a3d6  mov     ebx, eax
0x18003a3d8  test    eax, eax
0x18003a3da  jns     short loc_18003A413
0x18003a3dc  mov     [rsp+40h+var_18], 9B3h
0x18003a3e4  lea     r8, aFailedToCopyWi; "failed to copy winre location path"
0x18003a3eb  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a3f2  mov     r9d, ebx
0x18003a3f5  lea     rdx, aWinrecopywimba_3; "winreCopyWIMBack %s (0x%x) in file %S l"...
0x18003a3fc  mov     [rsp+40h+var_20], rax
0x18003a401  mov     ecx, 2
0x18003a406  call    UnattendLogW
0x18003a40b  movzx   ebx, bx
0x18003a40e  jmp     loc_18003A552
0x18003a413  mov     rcx, rdi
0x18003a416  call    winreAddTrailingBackslash
0x18003a41b  mov     ebx, eax
0x18003a41d  test    eax, eax
0x18003a41f  jz      short loc_18003A435
0x18003a421  mov     [rsp+40h+var_18], 9B5h
0x18003a429  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18003a430  jmp     loc_18003A6A5
0x18003a435  mov     r8, r12; unsigned __int16 *
0x18003a438  mov     edx, 12Eh; unsigned __int64
0x18003a43d  mov     rcx, r14; unsigned __int16 *
0x18003a440  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a445  mov     ebx, eax
0x18003a447  test    eax, eax
0x18003a449  jns     short loc_18003A45C
0x18003a44b  mov     [rsp+40h+var_18], 9B9h
0x18003a453  lea     r8, aFailedToCopyIm; "failed to copy image location path"
0x18003a45a  jmp     short loc_18003A3EB
0x18003a45c  mov     rcx, r14
0x18003a45f  call    winreAddTrailingBackslash
0x18003a464  mov     ebx, eax
0x18003a466  test    eax, eax
0x18003a468  jz      short loc_18003A474
0x18003a46a  mov     [rsp+40h+var_18], 9BBh
0x18003a472  jmp     short loc_18003A429
0x18003a474  mov     rdx, r14; String2
0x18003a477  mov     rcx, rdi; String1
0x18003a47a  call    cs:__imp__wcsicmp
0x18003a480  test    eax, eax
0x18003a482  jz      loc_18003A615
0x18003a488  mov     rcx, r12; lpFileName
0x18003a48b  call    winreOpenOrCreateDir
0x18003a490  mov     ebx, eax
0x18003a492  test    eax, eax
0x18003a494  jz      short loc_18003A4AA
0x18003a496  mov     [rsp+40h+var_18], 9C3h
0x18003a49e  lea     r8, aFailedToCreate_8; "failed to create directory"
0x18003a4a5  jmp     loc_18003A6A5
0x18003a4aa  mov     r9, rdi
0x18003a4ad  lea     r8, aWinreWim; "Winre.wim"
0x18003a4b4  mov     rdx, rsi
0x18003a4b7  mov     rcx, r15
0x18003a4ba  call    winreGetSourceFile
0x18003a4bf  mov     ebx, eax
0x18003a4c1  test    eax, eax
0x18003a4c3  jz      short loc_18003A4D9
0x18003a4c5  mov     [rsp+40h+var_18], 9CCh
0x18003a4cd  lea     r8, aFailedToGetThe_0; "failed to get the path of winre.wim"
0x18003a4d4  jmp     loc_18003A6A5
0x18003a4d9  mov     r8, r14; unsigned __int16 *
0x18003a4dc  lea     rdx, aWinreWim; "Winre.wim"
0x18003a4e3  mov     rcx, r12; unsigned __int16 *
0x18003a4e6  call    winreAddFileToDirPath
0x18003a4eb  mov     ebx, eax
0x18003a4ed  test    eax, eax
0x18003a4ef  jz      short loc_18003A505
0x18003a4f1  mov     [rsp+40h+var_18], 9D0h
0x18003a4f9  lea     r8, aFailedToAddWin_0; "failed to add winre.wim to directory pa"...
0x18003a500  jmp     loc_18003A6A5
0x18003a505  mov     r8d, 3; dwFlags
0x18003a50b  mov     rdx, r14; lpNewFileName
0x18003a50e  mov     rcx, rdi; lpExistingFileName
0x18003a511  call    cs:__imp_MoveFileExW
0x18003a517  test    eax, eax
0x18003a519  jnz     short loc_18003A55F
0x18003a51b  call    cs:__imp_GetLastError
0x18003a521  mov     [rsp+40h+var_18], 9D4h
0x18003a529  lea     r8, aFailedToMoveFi; "failed to move file"
0x18003a530  mov     ebx, eax
0x18003a532  lea     rdx, aWinrecopywimba_3; "winreCopyWIMBack %s (0x%x) in file %S l"...
0x18003a539  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a540  mov     r9d, ebx
0x18003a543  mov     ecx, 2
0x18003a548  mov     [rsp+40h+var_20], rax
0x18003a54d  call    UnattendLogW
0x18003a552  test    ebx, ebx
0x18003a554  jz      loc_18003A702
0x18003a55a  jmp     loc_18003A6C5
0x18003a55f  mov     r9, rdi
0x18003a562  lea     r8, aBootSdi; "boot.sdi"
0x18003a569  mov     rdx, rsi
0x18003a56c  mov     rcx, r15
0x18003a56f  call    winreGetSourceFile
0x18003a574  mov     ebx, eax
0x18003a576  test    eax, eax
0x18003a578  jz      short loc_18003A58E
0x18003a57a  mov     [rsp+40h+var_18], 9DCh
0x18003a582  lea     r8, aFailedToGetSou_0; "failed to get source file boot.sdi"
0x18003a589  jmp     loc_18003A6A5
0x18003a58e  mov     rcx, rdi; lpFileName
0x18003a591  call    cs:__imp_DeleteFileW
0x18003a597  mov     r9, rdi
0x18003a59a  lea     r8, aReagentXml_2; "ReAgent.xml"
0x18003a5a1  mov     rdx, rsi
0x18003a5a4  mov     rcx, r15
0x18003a5a7  call    winreGetSourceFile
0x18003a5ac  mov     ebx, eax
0x18003a5ae  test    eax, eax
0x18003a5b0  jz      short loc_18003A5C6
0x18003a5b2  mov     [rsp+40h+var_18], 9E6h
0x18003a5ba  lea     r8, aFailedToGetCon; "failed to get config file"
0x18003a5c1  jmp     loc_18003A6A5
0x18003a5c6  mov     rcx, rdi; lpFileName
0x18003a5c9  call    cs:__imp_DeleteFileW
0x18003a5cf  mov     r9, rdi
0x18003a5d2  lea     r8, aRecustomizatio_1; "ReCustomization.xml"
0x18003a5d9  mov     rdx, rsi
0x18003a5dc  mov     rcx, r15
0x18003a5df  call    winreGetSourceFile
0x18003a5e4  mov     ebx, eax
0x18003a5e6  test    eax, eax
0x18003a5e8  jz      short loc_18003A5FE
0x18003a5ea  mov     [rsp+40h+var_18], 9EFh
0x18003a5f2  lea     r8, aFailedToGetOem; "failed to get OEM customization file"
0x18003a5f9  jmp     loc_18003A6A5
0x18003a5fe  mov     rcx, rdi; lpFileName
0x18003a601  call    cs:__imp_DeleteFileW
0x18003a607  mov     rcx, rsi; lpPathName
0x18003a60a  call    cs:__imp_RemoveDirectoryW
0x18003a610  jmp     loc_18003A702
0x18003a615  mov     r9, rdi
0x18003a618  lea     r8, aBootSdi; "boot.sdi"
0x18003a61f  mov     rdx, rsi
0x18003a622  mov     rcx, r15
0x18003a625  call    winreGetSourceFile
0x18003a62a  mov     ebx, eax
0x18003a62c  test    eax, eax
0x18003a62e  jz      short loc_18003A63D
0x18003a630  mov     [rsp+40h+var_18], 9FEh
0x18003a638  jmp     loc_18003A582
0x18003a63d  mov     rcx, rdi; lpFileName
0x18003a640  call    cs:__imp_DeleteFileW
0x18003a646  mov     r9, rdi
0x18003a649  lea     r8, aReagentXml_2; "ReAgent.xml"
0x18003a650  mov     rdx, rsi
0x18003a653  mov     rcx, r15
0x18003a656  call    winreGetSourceFile
0x18003a65b  mov     ebx, eax
0x18003a65d  test    eax, eax
0x18003a65f  jz      short loc_18003A672
0x18003a661  mov     [rsp+40h+var_18], 0A04h
0x18003a669  lea     r8, aFailedToGetSou; "failed to get source file config file"
0x18003a670  jmp     short loc_18003A6A5
0x18003a672  mov     rcx, rdi; lpFileName
0x18003a675  call    cs:__imp_DeleteFileW
0x18003a67b  mov     r9, rdi
0x18003a67e  lea     r8, aRecustomizatio_1; "ReCustomization.xml"
0x18003a685  mov     rdx, rsi
0x18003a688  mov     rcx, r15
0x18003a68b  call    winreGetSourceFile
0x18003a690  mov     ebx, eax
0x18003a692  test    eax, eax
0x18003a694  jz      short loc_18003A6F9
0x18003a696  mov     [rsp+40h+var_18], 0A0Ah
0x18003a69e  lea     r8, aFailedToGetCus_0; "failed to get customization file"
0x18003a6a5  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a6ac  mov     r9d, ebx
0x18003a6af  lea     rdx, aWinrecopywimba_3; "winreCopyWIMBack %s (0x%x) in file %S l"...
0x18003a6b6  mov     [rsp+40h+var_20], rax
0x18003a6bb  mov     ecx, 2
0x18003a6c0  call    UnattendLogW
0x18003a6c5  mov     rax, [rbp+arg_8]
0x18003a6c9  lea     r8, aNull_0; "NULL"
0x18003a6d0  test    r14, r14
0x18003a6d3  mov     dword ptr [rsp+40h+var_20], ebx
0x18003a6d7  mov     r9, r8
0x18003a6da  lea     rdx, aWinrecopywimba_2; "winreCopyWIMBack failed to move WIM fil"...
0x18003a6e1  cmovnz  r9, r14
0x18003a6e5  mov     ecx, 1
0x18003a6ea  add     rax, 10h
0x18003a6ee  cmovnz  r8, rax
0x18003a6f2  call    UnattendLogW
0x18003a6f7  jmp     short loc_18003A72D
0x18003a6f9  mov     rcx, rdi; lpFileName
0x18003a6fc  call    cs:__imp_DeleteFileW
0x18003a702  mov     rax, [rbp+arg_8]
0x18003a706  lea     r8, aNull_0; "NULL"
0x18003a70d  test    r14, r14
0x18003a710  lea     rdx, aWinrecopywimba; "winreCopyWIMBack moved WIM file from %s"...
0x18003a717  mov     r9, r8
0x18003a71a  cmovnz  r9, r14
0x18003a71e  add     rax, 10h
0x18003a722  cmovnz  r8, rax
0x18003a726  xor     ecx, ecx
0x18003a728  call    UnattendLogW
0x18003a72d  test    r13, r13
0x18003a730  jz      short loc_18003A73B
0x18003a732  mov     rcx, r13; pv
0x18003a735  call    cs:__imp_CoTaskMemFree
0x18003a73b  test    rdi, rdi
0x18003a73e  jz      short loc_18003A749
  ... truncated ...
```
