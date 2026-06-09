# WinReSetTriggerFile

- ea: `0x18002c590`
- end: `0x18002c80a`
- name: `WinReSetTriggerFile`
- size: `634`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x18002b358`
- `0x18002c810`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000fe58`
- `0x18000ffcc`
- `0x18002c590`
- `0x18002ca4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c747`
- `KERNEL32!GetLastError` at `0x18002c793`
- `KERNEL32!GetLastError` at `0x18002c747`
- `KERNEL32!GetLastError` at `0x18002c793`
- `KERNEL32!CreateFileW` at `0x18002c784`
- `KERNEL32!CreateFileW` at `0x18002c784`
- `KERNEL32!CloseHandle` at `0x18002c7de`
- `KERNEL32!CloseHandle` at `0x18002c7de`
- `KERNEL32!DeleteFileW` at `0x18002c73d`
- `KERNEL32!DeleteFileW` at `0x18002c73d`
- `ole32!CoTaskMemFree` at `0x18002c7b8`
- `ole32!CoTaskMemFree` at `0x18002c7cb`
- `ole32!CoTaskMemFree` at `0x18002c7b8`
- `ole32!CoTaskMemFree` at `0x18002c7cb`

## string_xrefs

- `0x18002c608`: `failed to allocate path`
- `0x18002c6de`: `failed to allocate path`
- `0x18002c72c`: `failed to add file to directory path`
- `0x18002c663`: `failed to copy string`
- `0x18002c60f`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c64c`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c6e5`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c69b`: `failed to drop file form path`
- `0x18002c5db`: `Parameters: DirName: %s, fDelete: %d`
- `0x18002c755`: `failed to delete file`
- `0x18002c79c`: `failed to create file %s: 0x%x`

## pseudocode

```c
__int64 __fastcall WinReSetTriggerFile(unsigned __int16 *a1, unsigned int a2)
{
  __int64 FileW; // rbp
  const unsigned __int16 *v5; // r8
  __int64 LastError; // rbx
  const wchar_t *v7; // r8
  int v8; // eax
  WCHAR *v9; // rdi
  const wchar_t *v10; // r8
  DWORD v11; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-30h]
  DWORD dwFlagsAndAttributesa; // [rsp+28h] [rbp-30h]
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp+18h] BYREF

  pv = 0;
  lpFileName = 0;
  FileW = -1;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetTriggerFile");
  v5 = a1;
  if ( !a1 )
    v5 = L"NULL";
  UnattendLogW(0, L"Parameters: DirName: %s, fDelete: %d", v5, a2);
  LODWORD(LastError) = winreAllocPath(&pv);
  if ( (_DWORD)LastError )
  {
    dwFlagsAndAttributes = 213;
    v7 = L"failed to allocate path";
LABEL_5:
    UnattendLogW(
      2,
      L"WinReSetTriggerFile %s (0x%x) in file %S line %d",
      v7,
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      dwFlagsAndAttributes);
    goto LABEL_25;
  }
  LODWORD(LastError) = StringCchCopyW((unsigned __int16 *)pv, 0x12Eu, a1);
  if ( (int)LastError < 0 )
  {
    UnattendLogW(
      2,
      L"WinReSetTriggerFile %s (0x%x) in file %S line %d",
      L"failed to copy string",
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      218);
    LODWORD(LastError) = (unsigned __int16)LastError;
    goto LABEL_25;
  }
  LODWORD(LastError) = winreDropFileFormPath(pv);
  if ( (_DWORD)LastError )
  {
    dwFlagsAndAttributes = 225;
LABEL_10:
    v7 = L"failed to drop file form path";
    goto LABEL_5;
  }
  LODWORD(LastError) = winreDropFileFormPath(pv);
  if ( (_DWORD)LastError )
  {
    dwFlagsAndAttributes = 226;
    goto LABEL_10;
  }
  v8 = winreAllocPath(&lpFileName);
  v9 = (WCHAR *)lpFileName;
  LODWORD(LastError) = v8;
  if ( v8 )
  {
    dwFlagsAndAttributesa = 229;
    v10 = L"failed to allocate path";
LABEL_15:
    UnattendLogW(
      2,
      L"WinReSetTriggerFile %s (0x%x) in file %S line %d",
      v10,
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      dwFlagsAndAttributesa);
    goto LABEL_23;
  }
  LODWORD(LastError) = winreAddFileToDirPath((unsigned __int16 *)pv, L"Recovery.txt", (unsigned __int16 *)lpFileName);
  if ( (_DWORD)LastError )
  {
    dwFlagsAndAttributesa = 233;
    v10 = L"failed to add file to directory path";
    goto LABEL_15;
  }
  if ( !a2 )
  {
    FileW = (__int64)CreateFileW(v9, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      UnattendLogW(2, L"failed to create file %s: 0x%x", v9, LastError);
    }
    goto LABEL_23;
  }
  if ( !DeleteFileW(v9) )
  {
    v11 = GetLastError();
    dwFlagsAndAttributesa = 237;
    v10 = L"failed to delete file";
    LODWORD(LastError) = v11;
    goto LABEL_15;
  }
LABEL_23:
  if ( v9 )
    CoTaskMemFree(v9);
LABEL_25:
  if ( pv )
    CoTaskMemFree(pv);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  UnattendLogW(0, L"Exit WinReSetTriggerFile return error code: 0x%x", (unsigned int)LastError);
  UnattendFinalizeLog();
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002c590  mov     [rsp+arg_8], rbx
0x18002c595  push    rbp
0x18002c596  push    rdi
0x18002c597  push    r14
0x18002c599  sub     rsp, 40h
0x18002c59d  mov     rdi, rcx
0x18002c5a0  mov     [rsp+58h+pv], 0
0x18002c5a9  xor     ecx, ecx
0x18002c5ab  mov     [rsp+58h+lpFileName], 0
0x18002c5b4  mov     r14d, edx
0x18002c5b7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002c5bb  call    UnattendInitializeLogEx2
0x18002c5c0  lea     rdx, aEnterWinresett; "Enter WinReSetTriggerFile"
0x18002c5c7  xor     ecx, ecx
0x18002c5c9  call    UnattendLogW
0x18002c5ce  lea     rax, aNull_0; "NULL"
0x18002c5d5  test    rdi, rdi
0x18002c5d8  mov     r8, rdi
0x18002c5db  lea     rdx, aParametersDirn; "Parameters: DirName: %s, fDelete: %d"
0x18002c5e2  cmovz   r8, rax
0x18002c5e6  mov     r9d, r14d
0x18002c5e9  xor     ecx, ecx
0x18002c5eb  call    UnattendLogW
0x18002c5f0  lea     rcx, [rsp+58h+pv]
0x18002c5f5  call    winreAllocPath
0x18002c5fa  mov     ebx, eax
0x18002c5fc  test    eax, eax
0x18002c5fe  jz      short loc_18002C634
0x18002c600  mov     [rsp+58h+dwFlagsAndAttributes], 0D5h
0x18002c608  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002c60f  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c616  mov     r9d, ebx
0x18002c619  lea     rdx, aWinresettrigge_0; "WinReSetTriggerFile %s (0x%x) in file %"...
0x18002c620  mov     qword ptr [rsp+58h+dwCreationDisposition], rax
0x18002c625  mov     ecx, 2
0x18002c62a  call    UnattendLogW
0x18002c62f  jmp     loc_18002C7BE
0x18002c634  mov     rcx, [rsp+58h+pv]; unsigned __int16 *
0x18002c639  mov     r8, rdi; unsigned __int16 *
0x18002c63c  mov     edx, 12Eh; unsigned __int64
0x18002c641  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c646  mov     ebx, eax
0x18002c648  test    eax, eax
0x18002c64a  jns     short loc_18002C683
0x18002c64c  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c653  mov     [rsp+58h+dwFlagsAndAttributes], 0DAh
0x18002c65b  mov     r9d, ebx
0x18002c65e  mov     qword ptr [rsp+58h+dwCreationDisposition], rax
0x18002c663  lea     r8, aFailedToCopySt; "failed to copy string"
0x18002c66a  mov     ecx, 2
0x18002c66f  lea     rdx, aWinresettrigge_0; "WinReSetTriggerFile %s (0x%x) in file %"...
0x18002c676  call    UnattendLogW
0x18002c67b  movzx   ebx, bx
0x18002c67e  jmp     loc_18002C7BE
0x18002c683  mov     rcx, [rsp+58h+pv]
0x18002c688  call    winreDropFileFormPath
0x18002c68d  mov     ebx, eax
0x18002c68f  test    eax, eax
0x18002c691  jz      short loc_18002C6A7
0x18002c693  mov     [rsp+58h+dwFlagsAndAttributes], 0E1h
0x18002c69b  lea     r8, aFailedToDropFi_0; "failed to drop file form path"
0x18002c6a2  jmp     loc_18002C60F
0x18002c6a7  mov     rcx, [rsp+58h+pv]
0x18002c6ac  call    winreDropFileFormPath
0x18002c6b1  mov     ebx, eax
0x18002c6b3  test    eax, eax
0x18002c6b5  jz      short loc_18002C6C1
0x18002c6b7  mov     [rsp+58h+dwFlagsAndAttributes], 0E2h
0x18002c6bf  jmp     short loc_18002C69B
0x18002c6c1  lea     rcx, [rsp+58h+lpFileName]
0x18002c6c6  call    winreAllocPath
0x18002c6cb  mov     rdi, [rsp+58h+lpFileName]
0x18002c6d0  mov     ebx, eax
0x18002c6d2  test    eax, eax
0x18002c6d4  jz      short loc_18002C70A
0x18002c6d6  mov     [rsp+58h+dwFlagsAndAttributes], 0E5h
0x18002c6de  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002c6e5  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c6ec  mov     r9d, ebx
0x18002c6ef  lea     rdx, aWinresettrigge_0; "WinReSetTriggerFile %s (0x%x) in file %"...
0x18002c6f6  mov     qword ptr [rsp+58h+dwCreationDisposition], rax
0x18002c6fb  mov     ecx, 2
0x18002c700  call    UnattendLogW
0x18002c705  jmp     loc_18002C7B0
0x18002c70a  mov     rcx, [rsp+58h+pv]; unsigned __int16 *
0x18002c70f  lea     rdx, aRecoveryTxt; "Recovery.txt"
0x18002c716  mov     r8, rdi; unsigned __int16 *
0x18002c719  call    winreAddFileToDirPath
0x18002c71e  mov     ebx, eax
0x18002c720  test    eax, eax
0x18002c722  jz      short loc_18002C735
0x18002c724  mov     [rsp+58h+dwFlagsAndAttributes], 0E9h
0x18002c72c  lea     r8, aFailedToAddFil_3; "failed to add file to directory path"
0x18002c733  jmp     short loc_18002C6E5
0x18002c735  mov     rcx, rdi; lpFileName
0x18002c738  test    r14d, r14d
0x18002c73b  jz      short loc_18002C760
0x18002c73d  call    cs:__imp_DeleteFileW
0x18002c743  test    eax, eax
0x18002c745  jnz     short loc_18002C7B0
0x18002c747  call    cs:__imp_GetLastError
0x18002c74d  mov     [rsp+58h+dwFlagsAndAttributes], 0EDh
0x18002c755  lea     r8, aFailedToDelete_10; "failed to delete file"
0x18002c75c  mov     ebx, eax
0x18002c75e  jmp     short loc_18002C6E5
0x18002c760  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18002c769  xor     r9d, r9d; lpSecurityAttributes
0x18002c76c  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002c774  xor     r8d, r8d; dwShareMode
0x18002c777  mov     edx, 40000000h; dwDesiredAccess
0x18002c77c  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x18002c784  call    cs:__imp_CreateFileW
0x18002c78a  mov     rbp, rax
0x18002c78d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c791  jnz     short loc_18002C7B0
0x18002c793  call    cs:__imp_GetLastError
0x18002c799  mov     r8, rdi
0x18002c79c  lea     rdx, aFailedToCreate_27; "failed to create file %s: 0x%x"
0x18002c7a3  mov     r9d, eax
0x18002c7a6  lea     ecx, [rbp+3]
0x18002c7a9  mov     ebx, eax
0x18002c7ab  call    UnattendLogW
0x18002c7b0  test    rdi, rdi
0x18002c7b3  jz      short loc_18002C7BE
0x18002c7b5  mov     rcx, rdi; pv
0x18002c7b8  call    cs:__imp_CoTaskMemFree
0x18002c7be  cmp     [rsp+58h+pv], 0
0x18002c7c4  jz      short loc_18002C7D1
0x18002c7c6  mov     rcx, [rsp+58h+pv]; pv
0x18002c7cb  call    cs:__imp_CoTaskMemFree
0x18002c7d1  lea     rax, [rbp-1]
0x18002c7d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c7d9  ja      short loc_18002C7E4
0x18002c7db  mov     rcx, rbp; hObject
0x18002c7de  call    cs:__imp_CloseHandle
0x18002c7e4  mov     r8d, ebx
0x18002c7e7  lea     rdx, aExitWinresettr; "Exit WinReSetTriggerFile return error c"...
0x18002c7ee  xor     ecx, ecx
0x18002c7f0  call    UnattendLogW
0x18002c7f5  call    UnattendFinalizeLog
0x18002c7fa  mov     eax, ebx
0x18002c7fc  mov     rbx, [rsp+58h+arg_8]
0x18002c801  add     rsp, 40h
0x18002c805  pop     r14
0x18002c807  pop     rdi
0x18002c808  pop     rbp
0x18002c809  retn
```
