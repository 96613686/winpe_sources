# winreRenameWIMDir

- ea: `0x180032564`
- end: `0x18003271f`
- name: `winreRenameWIMDir`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180018870`
- `0x180019a90`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000fe58`
- `0x18000ffcc`
- `0x180031434`
- `0x18003158c`
- `0x180032564`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003269d`
- `KERNEL32!GetLastError` at `0x18003269d`
- `KERNEL32!RemoveDirectoryW` at `0x180032682`
- `KERNEL32!RemoveDirectoryW` at `0x180032682`
- `KERNEL32!MoveFileExW` at `0x180032693`
- `KERNEL32!MoveFileExW` at `0x180032693`
- `ole32!CoTaskMemFree` at `0x1800326df`
- `ole32!CoTaskMemFree` at `0x1800326ed`
- `ole32!CoTaskMemFree` at `0x1800326df`
- `ole32!CoTaskMemFree` at `0x1800326ed`

## string_xrefs

- `0x1800325a7`: `failed to allocate path`
- `0x1800325e9`: `failed to allocate path`
- `0x1800325ae`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x1800325f0`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x18003266b`: `failed to add OEM install directory to directory path`
- `0x1800325b8`: `winreRenameWIMDir %s (0x%x) in file %S line %d`
- `0x1800325fa`: `winreRenameWIMDir %s (0x%x) in file %S line %d`
- `0x180032639`: `failed to create temporary directory`
- `0x1800326ab`: `failed to move file`
- `0x1800326fa`: `winreRenameWIMDir failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRenameWIMDir(__int64 a1, unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rdi
  DWORD TargetDirName; // ebx
  const wchar_t *v6; // r8
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  DWORD LastError; // eax
  int v11; // [rsp+28h] [rbp-20h]
  int v12; // [rsp+28h] [rbp-20h]
  LPCWSTR lpExistingFileName; // [rsp+60h] [rbp+18h] BYREF
  LPCWSTR lpPathName; // [rsp+68h] [rbp+20h] BYREF

  lpExistingFileName = 0;
  v3 = 0;
  lpPathName = 0;
  TargetDirName = winreAllocPath(&lpExistingFileName);
  if ( TargetDirName )
  {
    v11 = 1306;
    v6 = L"failed to allocate path";
LABEL_3:
    UnattendLogW(
      2,
      L"winreRenameWIMDir %s (0x%x) in file %S line %d",
      v6,
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      v11);
    goto LABEL_15;
  }
  TargetDirName = winreAllocPath(&lpPathName);
  if ( TargetDirName )
  {
    v12 = 1307;
    v8 = L"failed to allocate path";
LABEL_6:
    UnattendLogW(
      2,
      L"winreRenameWIMDir %s (0x%x) in file %S line %d",
      v8,
      TargetDirName,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      v12);
    v3 = (unsigned __int16 *)lpPathName;
    goto LABEL_15;
  }
  TargetDirName = winreCreateTargetDirName(a1, v7, 1, lpExistingFileName);
  if ( TargetDirName )
  {
    v12 = 1317;
    v8 = L"failed to create temporary directory";
    goto LABEL_6;
  }
  v3 = (unsigned __int16 *)lpPathName;
  TargetDirName = winreAddFileToDirPath(
                    (unsigned __int16 *)(a1 + 656),
                    L"\\Recovery\\WindowsRE",
                    (unsigned __int16 *)lpPathName);
  if ( TargetDirName )
  {
    v11 = 1321;
    v6 = L"failed to add OEM install directory to directory path";
    goto LABEL_3;
  }
  winreDeleteAllFiles(v3);
  RemoveDirectoryW(v3);
  if ( !MoveFileExW(lpExistingFileName, v3, 0) )
  {
    LastError = GetLastError();
    v11 = 1332;
    v6 = L"failed to move file";
    TargetDirName = LastError;
    goto LABEL_3;
  }
  if ( a2 )
    StringCchCopyW(a2, 0x12Eu, L"\\Recovery\\WindowsRE");
LABEL_15:
  if ( lpExistingFileName )
    CoTaskMemFree((LPVOID)lpExistingFileName);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( TargetDirName )
    UnattendLogW(2, L"winreRenameWIMDir failed: 0x%x", TargetDirName);
  return TargetDirName;
}

```

## disassembly

```asm
0x180032564  mov     rax, rsp
0x180032567  mov     [rax+8], rbx
0x18003256b  mov     [rax+10h], rbp
0x18003256f  push    rdi
0x180032570  push    r14
0x180032572  push    r15
0x180032574  sub     rsp, 30h
0x180032578  mov     r14, rcx
0x18003257b  mov     qword ptr [rax+18h], 0
0x180032583  xor     edi, edi
0x180032585  lea     rcx, [rax+18h]
0x180032589  mov     [rax+20h], rdi
0x18003258d  mov     rbp, rdx
0x180032590  call    winreAllocPath
0x180032595  lea     r15d, [rdi+2]
0x180032599  mov     ebx, eax
0x18003259b  test    eax, eax
0x18003259d  jz      short loc_1800325D1
0x18003259f  mov     [rsp+48h+var_20], 51Ah
0x1800325a7  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x1800325ae  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800325b5  mov     r9d, ebx
0x1800325b8  lea     rdx, aWinrerenamewim_0; "winreRenameWIMDir %s (0x%x) in file %S "...
0x1800325bf  mov     [rsp+48h+var_28], rax
0x1800325c4  mov     ecx, r15d
0x1800325c7  call    UnattendLogW
0x1800325cc  jmp     loc_1800326D2
0x1800325d1  lea     rcx, [rsp+48h+lpPathName]
0x1800325d6  call    winreAllocPath
0x1800325db  mov     ebx, eax
0x1800325dd  test    eax, eax
0x1800325df  jz      short loc_180032618
0x1800325e1  mov     [rsp+48h+var_20], 51Bh
0x1800325e9  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x1800325f0  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800325f7  mov     r9d, ebx
0x1800325fa  lea     rdx, aWinrerenamewim_0; "winreRenameWIMDir %s (0x%x) in file %S "...
0x180032601  mov     [rsp+48h+var_28], rax
0x180032606  mov     ecx, r15d
0x180032609  call    UnattendLogW
0x18003260e  mov     rdi, [rsp+48h+lpPathName]
0x180032613  jmp     loc_1800326D2
0x180032618  mov     r9, [rsp+48h+lpExistingFileName]
0x18003261d  mov     r8d, 1
0x180032623  mov     rcx, r14
0x180032626  call    winreCreateTargetDirName
0x18003262b  mov     ebx, eax
0x18003262d  test    eax, eax
0x18003262f  jz      short loc_180032642
0x180032631  mov     [rsp+48h+var_20], 525h
0x180032639  lea     r8, aFailedToCreate_5; "failed to create temporary directory"
0x180032640  jmp     short loc_1800325F0
0x180032642  mov     rdi, [rsp+48h+lpPathName]
0x180032647  lea     rcx, [r14+290h]; unsigned __int16 *
0x18003264e  mov     r8, rdi; unsigned __int16 *
0x180032651  lea     rdx, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x180032658  call    winreAddFileToDirPath
0x18003265d  mov     ebx, eax
0x18003265f  test    eax, eax
0x180032661  jz      short loc_180032677
0x180032663  mov     [rsp+48h+var_20], 529h
0x18003266b  lea     r8, aFailedToAddOem; "failed to add OEM install directory to "...
0x180032672  jmp     loc_1800325AE
0x180032677  mov     rcx, rdi
0x18003267a  call    winreDeleteAllFiles
0x18003267f  mov     rcx, rdi; lpPathName
0x180032682  call    cs:__imp_RemoveDirectoryW
0x180032688  mov     rcx, [rsp+48h+lpExistingFileName]; lpExistingFileName
0x18003268d  xor     r8d, r8d; dwFlags
0x180032690  mov     rdx, rdi; lpNewFileName
0x180032693  call    cs:__imp_MoveFileExW
0x180032699  test    eax, eax
0x18003269b  jnz     short loc_1800326B9
0x18003269d  call    cs:__imp_GetLastError
0x1800326a3  mov     [rsp+48h+var_20], 534h
0x1800326ab  lea     r8, aFailedToMoveFi; "failed to move file"
0x1800326b2  mov     ebx, eax
0x1800326b4  jmp     loc_1800325AE
0x1800326b9  test    rbp, rbp
0x1800326bc  jz      short loc_1800326D2
0x1800326be  lea     r8, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x1800326c5  mov     edx, 12Eh; unsigned __int64
0x1800326ca  mov     rcx, rbp; unsigned __int16 *
0x1800326cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800326d2  cmp     [rsp+48h+lpExistingFileName], 0
0x1800326d8  jz      short loc_1800326E5
0x1800326da  mov     rcx, [rsp+48h+lpExistingFileName]; pv
0x1800326df  call    cs:__imp_CoTaskMemFree
0x1800326e5  test    rdi, rdi
0x1800326e8  jz      short loc_1800326F3
0x1800326ea  mov     rcx, rdi; pv
0x1800326ed  call    cs:__imp_CoTaskMemFree
0x1800326f3  test    ebx, ebx
0x1800326f5  jz      short loc_180032709
0x1800326f7  mov     r8d, ebx
0x1800326fa  lea     rdx, aWinrerenamewim; "winreRenameWIMDir failed: 0x%x"
0x180032701  mov     ecx, r15d
0x180032704  call    UnattendLogW
0x180032709  mov     rbp, [rsp+48h+arg_8]
0x18003270e  mov     eax, ebx
0x180032710  mov     rbx, [rsp+48h+arg_0]
0x180032715  add     rsp, 30h
0x180032719  pop     r15
0x18003271b  pop     r14
0x18003271d  pop     rdi
0x18003271e  retn
```
