# winreCopyBootSdiOnly

- ea: `0x180039b38`
- end: `0x180039dce`
- name: `winreCopyBootSdiOnly`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x180018870`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000fe58`
- `0x18000ffcc`
- `0x1800103f4`
- `0x1800297cc`
- `0x180032728`
- `0x180039b38`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180039d14`
- `KERNEL32!CopyFileW` at `0x180039d14`
- `KERNEL32!GetLastError` at `0x180039d1e`
- `KERNEL32!GetLastError` at `0x180039d1e`
- `KERNEL32!DeleteFileW` at `0x180039d04`
- `KERNEL32!DeleteFileW` at `0x180039d04`
- `ole32!CoTaskMemFree` at `0x180039d81`
- `ole32!CoTaskMemFree` at `0x180039d8f`
- `ole32!CoTaskMemFree` at `0x180039d9d`
- `ole32!CoTaskMemFree` at `0x180039d81`
- `ole32!CoTaskMemFree` at `0x180039d8f`
- `ole32!CoTaskMemFree` at `0x180039d9d`

## string_xrefs

- `0x180039b7c`: `failed to allocate path`
- `0x180039bce`: `failed to allocate path`
- `0x180039c06`: `failed to allocate path`
- `0x180039d2c`: `failed to copy file`
- `0x180039d62`: `failed to add winre.wim to directory`
- `0x180039b83`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039bb7`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039c0d`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039c77`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180039b8d`: `winreCopyBootSdiOnly %s (0x%x) in file %S line %d`
- `0x180039bda`: `winreCopyBootSdiOnly %s (0x%x) in file %S line %d`
- `0x180039c17`: `winreCopyBootSdiOnly %s (0x%x) in file %S line %d`
- `0x180039c9a`: `winreCopyBootSdiOnly %s (0x%x) in file %S line %d`
- `0x180039c54`: `failed to get boot sdi path`
- `0x180039c8e`: `failed to copy recovery directory`
- `0x180039ce2`: `failed to add boot sdi to directory`
- `0x180039daa`: `winreCopyBootSdiOnly failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCopyBootSdiOnly(struct _GUID *a1, unsigned __int16 *a2)
{
  WCHAR *v3; // rdi
  WCHAR *v4; // rsi
  unsigned int BootSdiPath; // ebx
  const wchar_t *v7; // r8
  const wchar_t *v8; // r8
  DWORD LastError; // eax
  int v11; // [rsp+28h] [rbp-18h]
  int v12; // [rsp+28h] [rbp-18h]
  LPCWSTR v13[2]; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp+40h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+88h] [rbp+48h] BYREF

  lpExistingFileName = 0;
  v3 = 0;
  v4 = 0;
  lpFileName = 0;
  v13[0] = 0;
  BootSdiPath = winreAllocPath(&lpExistingFileName);
  if ( BootSdiPath )
  {
    v11 = 1529;
    v7 = L"failed to allocate path";
LABEL_3:
    UnattendLogW(
      2,
      L"winreCopyBootSdiOnly %s (0x%x) in file %S line %d",
      v7,
      BootSdiPath,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v11);
    goto LABEL_23;
  }
  BootSdiPath = winreAllocPath(&lpFileName);
  if ( BootSdiPath )
  {
    UnattendLogW(
      2,
      L"winreCopyBootSdiOnly %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      BootSdiPath,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      1530);
LABEL_6:
    v3 = (WCHAR *)lpFileName;
    goto LABEL_23;
  }
  BootSdiPath = winreAllocPath(v13);
  if ( BootSdiPath )
  {
    v12 = 1531;
    v8 = L"failed to allocate path";
LABEL_9:
    UnattendLogW(
      2,
      L"winreCopyBootSdiOnly %s (0x%x) in file %S line %d",
      v8,
      BootSdiPath,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      v12);
    v3 = (WCHAR *)lpFileName;
    v4 = (WCHAR *)v13[0];
    goto LABEL_23;
  }
  BootSdiPath = winreGetBootSdiPath(a1, (unsigned __int16 *)lpExistingFileName);
  if ( BootSdiPath )
  {
    v12 = 1533;
    v8 = L"failed to get boot sdi path";
    goto LABEL_9;
  }
  v4 = (WCHAR *)v13[0];
  BootSdiPath = StringCchCopyW((unsigned __int16 *)v13[0], 0x12Eu, a2);
  if ( (BootSdiPath & 0x80000000) != 0 )
  {
    UnattendLogW(
      2,
      L"winreCopyBootSdiOnly %s (0x%x) in file %S line %d",
      L"failed to copy recovery directory",
      BootSdiPath,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      1541);
    BootSdiPath = (unsigned __int16)BootSdiPath;
    goto LABEL_6;
  }
  winreSetACL(a2);
  winreSetACL(v4);
  v3 = (WCHAR *)lpFileName;
  BootSdiPath = winreAddFileToDirPath(a2, L"boot.sdi", (unsigned __int16 *)lpFileName);
  if ( BootSdiPath )
  {
    v11 = 1547;
    v7 = (const wchar_t *)"failed to add boot sdi to directory";
    goto LABEL_3;
  }
  if ( (unsigned int)winreDoesFileExist(a2, L"boot.sdi") )
    DeleteFileW(v3);
  if ( !CopyFileW(lpExistingFileName, v3, 0) )
  {
    LastError = GetLastError();
    v11 = 1558;
    v7 = L"failed to copy file";
    BootSdiPath = LastError;
    goto LABEL_3;
  }
  winreSetACL(v3);
  BootSdiPath = winreAddFileToDirPath(a2, L"Winre.wim", v3);
  if ( BootSdiPath )
  {
    v11 = 1567;
    v7 = L"failed to add winre.wim to directory";
    goto LABEL_3;
  }
  winreSetACL(v3);
LABEL_23:
  if ( lpExistingFileName )
    CoTaskMemFree((LPVOID)lpExistingFileName);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( BootSdiPath )
    UnattendLogW(1, L"winreCopyBootSdiOnly failed: 0x%x", BootSdiPath);
  return BootSdiPath;
}

```

## disassembly

```asm
0x180039b38  mov     [rsp-28h+arg_0], rbx
0x180039b3d  push    rbp
0x180039b3e  push    rsi
0x180039b3f  push    rdi
0x180039b40  push    r12
0x180039b42  push    r14
0x180039b44  mov     rbp, rsp
0x180039b47  sub     rsp, 40h
0x180039b4b  mov     r12, rcx
0x180039b4e  mov     [rbp+lpExistingFileName], 0
0x180039b56  xor     edi, edi
0x180039b58  lea     rcx, [rbp+lpExistingFileName]
0x180039b5c  xor     esi, esi
0x180039b5e  mov     [rbp+lpFileName], rdi
0x180039b62  mov     [rbp+var_10], rsi
0x180039b66  mov     r14, rdx
0x180039b69  call    winreAllocPath
0x180039b6e  mov     ebx, eax
0x180039b70  test    eax, eax
0x180039b72  jz      short loc_180039BA8
0x180039b74  mov     [rsp+40h+var_18], 5F9h
0x180039b7c  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180039b83  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039b8a  mov     r9d, ebx
0x180039b8d  lea     rdx, aWinrecopyboots_0; "winreCopyBootSdiOnly %s (0x%x) in file "...
0x180039b94  mov     [rsp+40h+var_20], rax
0x180039b99  mov     ecx, 2
0x180039b9e  call    UnattendLogW
0x180039ba3  jmp     loc_180039D76
0x180039ba8  lea     rcx, [rbp+lpFileName]
0x180039bac  call    winreAllocPath
0x180039bb1  mov     ebx, eax
0x180039bb3  test    eax, eax
0x180039bb5  jz      short loc_180039BEF
0x180039bb7  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039bbe  mov     [rsp+40h+var_18], 5FAh
0x180039bc6  mov     r9d, ebx
0x180039bc9  mov     [rsp+40h+var_20], rax
0x180039bce  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180039bd5  mov     ecx, 2
0x180039bda  lea     rdx, aWinrecopyboots_0; "winreCopyBootSdiOnly %s (0x%x) in file "...
0x180039be1  call    UnattendLogW
0x180039be6  mov     rdi, [rbp+lpFileName]
0x180039bea  jmp     loc_180039D76
0x180039bef  lea     rcx, [rbp+var_10]
0x180039bf3  call    winreAllocPath
0x180039bf8  mov     ebx, eax
0x180039bfa  test    eax, eax
0x180039bfc  jz      short loc_180039C3A
0x180039bfe  mov     [rsp+40h+var_18], 5FBh
0x180039c06  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180039c0d  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039c14  mov     r9d, ebx
0x180039c17  lea     rdx, aWinrecopyboots_0; "winreCopyBootSdiOnly %s (0x%x) in file "...
0x180039c1e  mov     [rsp+40h+var_20], rax
0x180039c23  mov     ecx, 2
0x180039c28  call    UnattendLogW
0x180039c2d  mov     rdi, [rbp+lpFileName]
0x180039c31  mov     rsi, [rbp+var_10]
0x180039c35  jmp     loc_180039D76
0x180039c3a  mov     rdx, [rbp+lpExistingFileName]
0x180039c3e  mov     rcx, r12
0x180039c41  call    winreGetBootSdiPath
0x180039c46  mov     ebx, eax
0x180039c48  test    eax, eax
0x180039c4a  jz      short loc_180039C5D
0x180039c4c  mov     [rsp+40h+var_18], 5FDh
0x180039c54  lea     r8, aFailedToGetBoo_2; "failed to get boot sdi path"
0x180039c5b  jmp     short loc_180039C0D
0x180039c5d  mov     rsi, [rbp+var_10]
0x180039c61  mov     r8, r14; unsigned __int16 *
0x180039c64  mov     rcx, rsi; unsigned __int16 *
0x180039c67  mov     edx, 12Eh; unsigned __int64
0x180039c6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039c71  mov     ebx, eax
0x180039c73  test    eax, eax
0x180039c75  jns     short loc_180039CAE
0x180039c77  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180039c7e  mov     [rsp+40h+var_18], 605h
0x180039c86  mov     r9d, ebx
0x180039c89  mov     [rsp+40h+var_20], rax
0x180039c8e  lea     r8, aFailedToCopyRe_0; "failed to copy recovery directory"
0x180039c95  mov     ecx, 2
0x180039c9a  lea     rdx, aWinrecopyboots_0; "winreCopyBootSdiOnly %s (0x%x) in file "...
0x180039ca1  call    UnattendLogW
0x180039ca6  movzx   ebx, bx
0x180039ca9  jmp     loc_180039BE6
0x180039cae  mov     rcx, r14; lpFileName
0x180039cb1  call    winreSetACL
0x180039cb6  mov     rcx, rsi; lpFileName
0x180039cb9  call    winreSetACL
0x180039cbe  mov     rdi, [rbp+lpFileName]
0x180039cc2  lea     rdx, aBootSdi; "boot.sdi"
0x180039cc9  mov     r8, rdi; unsigned __int16 *
0x180039ccc  mov     rcx, r14; unsigned __int16 *
0x180039ccf  call    winreAddFileToDirPath
0x180039cd4  mov     ebx, eax
0x180039cd6  test    eax, eax
0x180039cd8  jz      short loc_180039CEE
0x180039cda  mov     [rsp+40h+var_18], 60Bh
0x180039ce2  lea     r8, aFailedToAddBoo_1; "failed to add boot sdi to directory"
0x180039ce9  jmp     loc_180039B83
0x180039cee  lea     rdx, aBootSdi; "boot.sdi"
0x180039cf5  mov     rcx, r14; unsigned __int16 *
0x180039cf8  call    winreDoesFileExist
0x180039cfd  test    eax, eax
0x180039cff  jz      short loc_180039D0A
0x180039d01  mov     rcx, rdi; lpFileName
0x180039d04  call    cs:__imp_DeleteFileW
0x180039d0a  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x180039d0e  xor     r8d, r8d; bFailIfExists
0x180039d11  mov     rdx, rdi; lpNewFileName
0x180039d14  call    cs:__imp_CopyFileW
0x180039d1a  test    eax, eax
0x180039d1c  jnz     short loc_180039D3A
0x180039d1e  call    cs:__imp_GetLastError
0x180039d24  mov     [rsp+40h+var_18], 616h
0x180039d2c  lea     r8, aFailedToCopyFi; "failed to copy file"
0x180039d33  mov     ebx, eax
0x180039d35  jmp     loc_180039B83
0x180039d3a  mov     rcx, rdi; lpFileName
0x180039d3d  call    winreSetACL
0x180039d42  mov     r8, rdi; unsigned __int16 *
0x180039d45  lea     rdx, aWinreWim; "Winre.wim"
0x180039d4c  mov     rcx, r14; unsigned __int16 *
0x180039d4f  call    winreAddFileToDirPath
0x180039d54  mov     ebx, eax
0x180039d56  test    eax, eax
0x180039d58  jz      short loc_180039D6E
0x180039d5a  mov     [rsp+40h+var_18], 61Fh
0x180039d62  lea     r8, aFailedToAddWin; "failed to add winre.wim to directory"
0x180039d69  jmp     loc_180039B83
0x180039d6e  mov     rcx, rdi; lpFileName
0x180039d71  call    winreSetACL
0x180039d76  cmp     [rbp+lpExistingFileName], 0
0x180039d7b  jz      short loc_180039D87
0x180039d7d  mov     rcx, [rbp+lpExistingFileName]; pv
0x180039d81  call    cs:__imp_CoTaskMemFree
0x180039d87  test    rdi, rdi
0x180039d8a  jz      short loc_180039D95
0x180039d8c  mov     rcx, rdi; pv
0x180039d8f  call    cs:__imp_CoTaskMemFree
0x180039d95  test    rsi, rsi
0x180039d98  jz      short loc_180039DA3
0x180039d9a  mov     rcx, rsi; pv
0x180039d9d  call    cs:__imp_CoTaskMemFree
0x180039da3  test    ebx, ebx
0x180039da5  jz      short loc_180039DBB
0x180039da7  mov     r8d, ebx
0x180039daa  lea     rdx, aWinrecopyboots; "winreCopyBootSdiOnly failed: 0x%x"
0x180039db1  mov     ecx, 1
0x180039db6  call    UnattendLogW
0x180039dbb  mov     eax, ebx
0x180039dbd  mov     rbx, [rsp+40h+arg_0]
0x180039dc2  add     rsp, 40h
0x180039dc6  pop     r14
0x180039dc8  pop     r12
0x180039dca  pop     rdi
0x180039dcb  pop     rsi
0x180039dcc  pop     rbp
0x180039dcd  retn
```
