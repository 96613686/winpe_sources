# MyMapViewOfFileByHandle

- ea: `0x180006ee8`
- end: `0x180006fc7`
- name: `MyMapViewOfFileByHandle`
- size: `223`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002720`
- `0x180004310`

## callees

- `0x180006ee8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f39`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006f1d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006fb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006fb4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006fa8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006fa8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180006f84`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180006f84`

## pseudocode

```c
__int64 __fastcall MyMapViewOfFileByHandle(HANDLE hFile, DWORD *a2, _QWORD *a3)
{
  DWORD FileSize; // ebx
  HANDLE FileMappingA; // rax
  void *v9; // rdi
  LPVOID v10; // rsi
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v11 = 0;
  FileSize = GetFileSize(hFile, &v11);
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
      return 0;
LABEL_3:
    SetLastError(0xDFu);
    return 0;
  }
  if ( v11 )
    goto LABEL_3;
  if ( FileSize )
  {
    FileMappingA = CreateFileMappingA(hFile, 0, 8u, 0, 0, 0);
    v9 = FileMappingA;
    if ( !FileMappingA )
      return 0;
    v10 = MapViewOfFile(FileMappingA, 1u, 0, 0, 0);
    CloseHandle(v9);
    if ( !v10 )
      return 0;
    *a3 = v10;
    *a2 = FileSize;
  }
  return 1;
}

```

## disassembly

```asm
0x180006ee8  mov     rax, rsp
0x180006eeb  mov     [rax+8], rbx
0x180006eef  mov     [rax+18h], rsi
0x180006ef3  push    rdi
0x180006ef4  push    r14
0x180006ef6  push    r15
0x180006ef8  sub     rsp, 30h
0x180006efc  mov     qword ptr [r8], 0
0x180006f03  mov     r15, rdx
0x180006f06  mov     dword ptr [rdx], 0
0x180006f0c  mov     r14, r8
0x180006f0f  lea     rdx, [rax+10h]; lpFileSizeHigh
0x180006f13  mov     dword ptr [rax+10h], 0
0x180006f1a  mov     rdi, rcx
0x180006f1d  call    cs:__imp_GetFileSize
0x180006f23  mov     ebx, eax
0x180006f25  cmp     eax, 0FFFFFFFFh
0x180006f28  jnz     short loc_180006F55
0x180006f2a  call    cs:__imp_GetLastError
0x180006f30  test    eax, eax
0x180006f32  jnz     short loc_180006F3F
0x180006f34  mov     ecx, 0DFh; dwErrCode
0x180006f39  call    cs:__imp_SetLastError
0x180006f3f  xor     eax, eax
0x180006f41  mov     rbx, [rsp+48h+arg_0]
0x180006f46  mov     rsi, [rsp+48h+arg_10]
0x180006f4b  add     rsp, 30h
0x180006f4f  pop     r15
0x180006f51  pop     r14
0x180006f53  pop     rdi
0x180006f54  retn
0x180006f55  cmp     [rsp+48h+arg_8], 0
0x180006f5a  jnz     short loc_180006F34
0x180006f5c  test    ebx, ebx
0x180006f5e  jnz     short loc_180006F67
0x180006f60  mov     eax, 1
0x180006f65  jmp     short loc_180006F41
0x180006f67  xor     r9d, r9d; dwMaximumSizeHigh
0x180006f6a  mov     [rsp+48h+lpName], 0; lpName
0x180006f73  xor     edx, edx; lpFileMappingAttributes
0x180006f75  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180006f7d  mov     rcx, rdi; hFile
0x180006f80  lea     r8d, [r9+8]; flProtect
0x180006f84  call    cs:__imp_CreateFileMappingA
0x180006f8a  mov     rdi, rax
0x180006f8d  test    rax, rax
0x180006f90  jz      short loc_180006F3F
0x180006f92  xor     r9d, r9d; dwFileOffsetLow
0x180006f95  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180006f9e  xor     r8d, r8d; dwFileOffsetHigh
0x180006fa1  mov     rcx, rax; hFileMappingObject
0x180006fa4  lea     edx, [r9+1]; dwDesiredAccess
0x180006fa8  call    cs:__imp_MapViewOfFile
0x180006fae  mov     rcx, rdi; hObject
0x180006fb1  mov     rsi, rax
0x180006fb4  call    cs:__imp_CloseHandle
0x180006fba  test    rsi, rsi
0x180006fbd  jz      short loc_180006F3F
0x180006fbf  mov     [r14], rsi
0x180006fc2  mov     [r15], ebx
0x180006fc5  jmp     short loc_180006F60
```
