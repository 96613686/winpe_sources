# pSetupOpenFileForWrite

- ea: `0x14000cb60`
- end: `0x14000cbd7`
- name: `pSetupOpenFileForWrite`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x14000cbe0`
- `0x14000da54`

## callees

- `0x14000c4dc`
- `0x14000cb60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cbb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cbb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cbbd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000cba7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000cba7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000cb8f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000cb8f`

## pseudocode

```c
__int64 __fastcall pSetupOpenFileForWrite(const WCHAR *a1, int a2, __int64 a3, __int64 a4, HANDLE *a5, LONG *a6)
{
  DWORD File; // edi
  LONG FileSize; // eax
  int v9; // [rsp+20h] [rbp-28h]

  File = pSpUtilsCreateFile(a1, a2 | 0xC0000000, a3, a4, v9, a4, a5);
  if ( !File )
  {
    FileSize = GetFileSize(*a5, 0);
    *a6 = FileSize;
    if ( SetFilePointer(*a5, FileSize, 0, 0) == -1 )
    {
      File = GetLastError();
      CloseHandle(*a5);
      *a5 = (HANDLE)-1LL;
    }
  }
  return File;
}

```

## disassembly

```asm
0x14000cb60  mov     [rsp+arg_0], rbx
0x14000cb65  push    rdi
0x14000cb66  sub     rsp, 40h
0x14000cb6a  mov     rbx, [rsp+48h+arg_20]
0x14000cb6f  or      edx, 0C0000000h; dwDesiredAccess
0x14000cb75  mov     [rsp+48h+var_18], rbx; __int64
0x14000cb7a  mov     [rsp+48h+var_20], r9d; int
0x14000cb7f  call    _pSpUtilsCreateFile
0x14000cb84  mov     edi, eax
0x14000cb86  test    eax, eax
0x14000cb88  jnz     short loc_14000CBCA
0x14000cb8a  mov     rcx, [rbx]; hFile
0x14000cb8d  xor     edx, edx; lpFileSizeHigh
0x14000cb8f  call    cs:__imp_GetFileSize
0x14000cb95  mov     rcx, [rsp+48h+arg_28]
0x14000cb9a  xor     r9d, r9d; dwMoveMethod
0x14000cb9d  xor     r8d, r8d; lpDistanceToMoveHigh
0x14000cba0  mov     edx, eax; lDistanceToMove
0x14000cba2  mov     [rcx], eax
0x14000cba4  mov     rcx, [rbx]; hFile
0x14000cba7  call    cs:__imp_SetFilePointer
0x14000cbad  cmp     eax, 0FFFFFFFFh
0x14000cbb0  jnz     short loc_14000CBCA
0x14000cbb2  call    cs:__imp_GetLastError
0x14000cbb8  mov     rcx, [rbx]; hObject
0x14000cbbb  mov     edi, eax
0x14000cbbd  call    cs:__imp_CloseHandle
0x14000cbc3  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x14000cbca  mov     rbx, [rsp+48h+arg_0]
0x14000cbcf  mov     eax, edi
0x14000cbd1  add     rsp, 40h
0x14000cbd5  pop     rdi
0x14000cbd6  retn
```
