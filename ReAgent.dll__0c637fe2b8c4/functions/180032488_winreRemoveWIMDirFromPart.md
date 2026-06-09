# winreRemoveWIMDirFromPart

- ea: `0x180032488`
- end: `0x18003255b`
- name: `winreRemoveWIMDirFromPart`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180019a90`

## callees

- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x18003158c`
- `0x180032488`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x18003251d`
- `KERNEL32!RemoveDirectoryW` at `0x18003251d`
- `ole32!CoTaskMemFree` at `0x180032530`
- `ole32!CoTaskMemFree` at `0x180032530`

## string_xrefs

- `0x1800324b6`: `failed to allocate path`
- `0x1800324bd`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x1800324c7`: `winreRemoveWIMDirFromPart %s (0x%x) in file %S line %d`
- `0x180032505`: `failed to add OEM install directory to directory path`
- `0x18003253d`: `winreRemoveWIMDirFromPart failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRemoveWIMDirFromPart(__int64 a1)
{
  unsigned int v2; // ebx
  const wchar_t *v3; // r8
  int v5; // [rsp+28h] [rbp-10h]
  LPCWSTR lpPathName; // [rsp+48h] [rbp+10h] BYREF

  lpPathName = 0;
  v2 = winreAllocPath(&lpPathName);
  if ( v2 )
  {
    v5 = 1269;
    v3 = L"failed to allocate path";
LABEL_3:
    UnattendLogW(
      2,
      L"winreRemoveWIMDirFromPart %s (0x%x) in file %S line %d",
      v3,
      v2,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      v5);
    goto LABEL_7;
  }
  v2 = winreAddFileToDirPath((unsigned __int16 *)(a1 + 656), L"\\Recovery\\WindowsRE", (unsigned __int16 *)lpPathName);
  if ( v2 )
  {
    v5 = 1277;
    v3 = L"failed to add OEM install directory to directory path";
    goto LABEL_3;
  }
  winreDeleteAllFiles((unsigned __int16 *)lpPathName);
  RemoveDirectoryW(lpPathName);
LABEL_7:
  if ( lpPathName )
    CoTaskMemFree((LPVOID)lpPathName);
  if ( v2 )
    UnattendLogW(2, L"winreRemoveWIMDirFromPart failed: 0x%x", v2);
  return v2;
}

```

## disassembly

```asm
0x180032488  mov     [rsp+arg_0], rbx
0x18003248d  push    rsi
0x18003248e  sub     rsp, 30h
0x180032492  mov     rsi, rcx
0x180032495  mov     [rsp+38h+lpPathName], 0
0x18003249e  lea     rcx, [rsp+38h+lpPathName]
0x1800324a3  call    winreAllocPath
0x1800324a8  mov     ebx, eax
0x1800324aa  test    eax, eax
0x1800324ac  jz      short loc_1800324DF
0x1800324ae  mov     [rsp+38h+var_10], 4F5h
0x1800324b6  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x1800324bd  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800324c4  mov     r9d, ebx
0x1800324c7  lea     rdx, aWinreremovewim; "winreRemoveWIMDirFromPart %s (0x%x) in "...
0x1800324ce  mov     [rsp+38h+var_18], rax
0x1800324d3  mov     ecx, 2
0x1800324d8  call    UnattendLogW
0x1800324dd  jmp     short loc_180032523
0x1800324df  mov     r8, [rsp+38h+lpPathName]; unsigned __int16 *
0x1800324e4  lea     rcx, [rsi+290h]; unsigned __int16 *
0x1800324eb  lea     rdx, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x1800324f2  call    winreAddFileToDirPath
0x1800324f7  mov     ebx, eax
0x1800324f9  test    eax, eax
0x1800324fb  jz      short loc_18003250E
0x1800324fd  mov     [rsp+38h+var_10], 4FDh
0x180032505  lea     r8, aFailedToAddOem; "failed to add OEM install directory to "...
0x18003250c  jmp     short loc_1800324BD
0x18003250e  mov     rcx, [rsp+38h+lpPathName]
0x180032513  call    winreDeleteAllFiles
0x180032518  mov     rcx, [rsp+38h+lpPathName]; lpPathName
0x18003251d  call    cs:__imp_RemoveDirectoryW
0x180032523  cmp     [rsp+38h+lpPathName], 0
0x180032529  jz      short loc_180032536
0x18003252b  mov     rcx, [rsp+38h+lpPathName]; pv
0x180032530  call    cs:__imp_CoTaskMemFree
0x180032536  test    ebx, ebx
0x180032538  jz      short loc_18003254E
0x18003253a  mov     r8d, ebx
0x18003253d  lea     rdx, aWinreremovewim_0; "winreRemoveWIMDirFromPart failed: 0x%x"
0x180032544  mov     ecx, 2
0x180032549  call    UnattendLogW
0x18003254e  mov     eax, ebx
0x180032550  mov     rbx, [rsp+38h+arg_0]
0x180032555  add     rsp, 30h
0x180032559  pop     rsi
0x18003255a  retn
```
