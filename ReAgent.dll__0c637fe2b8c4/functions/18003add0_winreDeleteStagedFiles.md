# winreDeleteStagedFiles

- ea: `0x18003add0`
- end: `0x18003af0b`
- name: `winreDeleteStagedFiles`
- size: `315`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18002a570`

## callees

- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x18001051c`
- `0x18003add0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003aea1`
- `KERNEL32!GetLastError` at `0x18003aea1`
- `KERNEL32!DeleteFileW` at `0x18003ae97`
- `KERNEL32!DeleteFileW` at `0x18003ae97`
- `ole32!CoTaskMemFree` at `0x18003aee5`
- `ole32!CoTaskMemFree` at `0x18003aef3`
- `ole32!CoTaskMemFree` at `0x18003aee5`
- `ole32!CoTaskMemFree` at `0x18003aef3`

## string_xrefs

- `0x18003ae08`: `failed to allocate path`
- `0x18003aeaf`: `failed to delete file`
- `0x18003ae89`: `failed to add winre.wim to directory`
- `0x18003ae2b`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003aeb8`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003ae42`: `failed to find main os config dir`
- `0x18003ae49`: `winreDeleteStagedFiles %s (0x%x) in file %S line %d`
- `0x18003aec2`: `winreDeleteStagedFiles %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall winreDeleteStagedFiles(unsigned __int16 *a1)
{
  void *v2; // rdi
  DWORD MainOsConfigDir; // ebx
  const wchar_t *v4; // r8
  DWORD LastError; // eax
  int v7; // [rsp+28h] [rbp-10h]
  LPCWSTR lpFileName; // [rsp+48h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h]

  lpFileName = 0;
  v2 = 0;
  pv = 0;
  MainOsConfigDir = winreAllocPath(&lpFileName);
  if ( MainOsConfigDir )
  {
    v7 = 1485;
    v4 = L"failed to allocate path";
  }
  else
  {
    if ( !a1 )
    {
      MainOsConfigDir = winreFindMainOsConfigDir(0);
      if ( MainOsConfigDir )
      {
        UnattendLogW(
          2,
          L"winreDeleteStagedFiles %s (0x%x) in file %S line %d",
          L"failed to find main os config dir",
          MainOsConfigDir,
          "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
          1493);
        v2 = pv;
        goto LABEL_12;
      }
      v2 = pv;
      a1 = (unsigned __int16 *)pv;
    }
    MainOsConfigDir = winreAddFileToDirPath(a1, L"Winre.wim", (unsigned __int16 *)lpFileName);
    if ( MainOsConfigDir )
    {
      v7 = 1503;
      v4 = L"failed to add winre.wim to directory";
    }
    else
    {
      if ( DeleteFileW(lpFileName) )
        goto LABEL_12;
      LastError = GetLastError();
      v7 = 1505;
      v4 = L"failed to delete file";
      MainOsConfigDir = LastError;
    }
  }
  UnattendLogW(
    2,
    L"winreDeleteStagedFiles %s (0x%x) in file %S line %d",
    v4,
    MainOsConfigDir,
    "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
    v7);
LABEL_12:
  if ( lpFileName )
    CoTaskMemFree((LPVOID)lpFileName);
  if ( v2 )
    CoTaskMemFree(v2);
  return MainOsConfigDir;
}

```

## disassembly

```asm
0x18003add0  mov     rax, rsp
0x18003add3  mov     [rax+8], rbx
0x18003add7  mov     [rax+20h], rbp
0x18003addb  push    rdi
0x18003addc  sub     rsp, 30h
0x18003ade0  mov     rbp, rcx
0x18003ade3  mov     qword ptr [rax+10h], 0
0x18003adeb  xor     edi, edi
0x18003aded  lea     rcx, [rax+10h]
0x18003adf1  mov     [rax+18h], rdi
0x18003adf5  call    winreAllocPath
0x18003adfa  mov     ebx, eax
0x18003adfc  test    eax, eax
0x18003adfe  jz      short loc_18003AE14
0x18003ae00  mov     [rsp+38h+var_10], 5CDh
0x18003ae08  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18003ae0f  jmp     loc_18003AEB8
0x18003ae14  test    rbp, rbp
0x18003ae17  jnz     short loc_18003AE67
0x18003ae19  lea     rdx, [rsp+38h+pv]
0x18003ae1e  xor     ecx, ecx
0x18003ae20  call    winreFindMainOsConfigDir
0x18003ae25  mov     ebx, eax
0x18003ae27  test    eax, eax
0x18003ae29  jz      short loc_18003AE5F
0x18003ae2b  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003ae32  mov     [rsp+38h+var_10], 5D5h
0x18003ae3a  mov     r9d, ebx
0x18003ae3d  mov     [rsp+38h+var_18], rax
0x18003ae42  lea     r8, aFailedToFindMa_1; "failed to find main os config dir"
0x18003ae49  lea     rdx, aWinredeletesta; "winreDeleteStagedFiles %s (0x%x) in fil"...
0x18003ae50  lea     ecx, [rbp+2]
0x18003ae53  call    UnattendLogW
0x18003ae58  mov     rdi, [rsp+38h+pv]
0x18003ae5d  jmp     short loc_18003AED8
0x18003ae5f  mov     rdi, [rsp+38h+pv]
0x18003ae64  mov     rbp, rdi
0x18003ae67  mov     r8, [rsp+38h+lpFileName]; unsigned __int16 *
0x18003ae6c  lea     rdx, aWinreWim; "Winre.wim"
0x18003ae73  mov     rcx, rbp; unsigned __int16 *
0x18003ae76  call    winreAddFileToDirPath
0x18003ae7b  mov     ebx, eax
0x18003ae7d  test    eax, eax
0x18003ae7f  jz      short loc_18003AE92
0x18003ae81  mov     [rsp+38h+var_10], 5DFh
0x18003ae89  lea     r8, aFailedToAddWin; "failed to add winre.wim to directory"
0x18003ae90  jmp     short loc_18003AEB8
0x18003ae92  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x18003ae97  call    cs:__imp_DeleteFileW
0x18003ae9d  test    eax, eax
0x18003ae9f  jnz     short loc_18003AED8
0x18003aea1  call    cs:__imp_GetLastError
0x18003aea7  mov     [rsp+38h+var_10], 5E1h
0x18003aeaf  lea     r8, aFailedToDelete_10; "failed to delete file"
0x18003aeb6  mov     ebx, eax
0x18003aeb8  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003aebf  mov     r9d, ebx
0x18003aec2  lea     rdx, aWinredeletesta; "winreDeleteStagedFiles %s (0x%x) in fil"...
0x18003aec9  mov     [rsp+38h+var_18], rax
0x18003aece  mov     ecx, 2
0x18003aed3  call    UnattendLogW
0x18003aed8  cmp     [rsp+38h+lpFileName], 0
0x18003aede  jz      short loc_18003AEEB
0x18003aee0  mov     rcx, [rsp+38h+lpFileName]; pv
0x18003aee5  call    cs:__imp_CoTaskMemFree
0x18003aeeb  test    rdi, rdi
0x18003aeee  jz      short loc_18003AEF9
0x18003aef0  mov     rcx, rdi; pv
0x18003aef3  call    cs:__imp_CoTaskMemFree
0x18003aef9  mov     rbp, [rsp+38h+arg_18]
0x18003aefe  mov     eax, ebx
0x18003af00  mov     rbx, [rsp+38h+arg_0]
0x18003af05  add     rsp, 30h
0x18003af09  pop     rdi
0x18003af0a  retn
```
