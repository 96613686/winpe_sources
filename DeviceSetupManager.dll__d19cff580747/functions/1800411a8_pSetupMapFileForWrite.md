# pSetupMapFileForWrite

- ea: `0x1800411a8`
- end: `0x18004123b`
- name: `pSetupMapFileForWrite`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x18003f96c`

## callees

- `0x1800411a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041212`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800411f5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800411f5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800411d4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800411d4`

## pseudocode

```c
__int64 __fastcall pSetupMapFileForWrite(void *a1, DWORD a2, HANDLE *a3, _QWORD *a4)
{
  SIZE_T dwNumberOfBytesToMap; // rbx
  HANDLE FileMappingW; // rax
  LPVOID v8; // rax
  DWORD LastError; // ebx

  dwNumberOfBytesToMap = a2;
  FileMappingW = CreateFileMappingW(a1, 0, 4u, 0, a2, 0);
  *a3 = FileMappingW;
  if ( FileMappingW )
  {
    v8 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, dwNumberOfBytesToMap);
    *a4 = v8;
    if ( v8 )
      return 0;
    LastError = GetLastError();
    CloseHandle(*a3);
    *a3 = 0;
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800411a8  mov     rax, rsp
0x1800411ab  mov     [rax+8], rbx
0x1800411af  mov     [rax+10h], rsi
0x1800411b3  push    rdi
0x1800411b4  sub     rsp, 30h
0x1800411b8  mov     ebx, edx
0x1800411ba  mov     rsi, r9
0x1800411bd  xor     r9d, r9d; dwMaximumSizeHigh
0x1800411c0  mov     qword ptr [rax-10h], 0
0x1800411c8  mov     rdi, r8
0x1800411cb  mov     [rax-18h], ebx
0x1800411ce  xor     edx, edx; lpFileMappingAttributes
0x1800411d0  lea     r8d, [r9+4]; flProtect
0x1800411d4  call    cs:__imp_CreateFileMappingW
0x1800411da  mov     [rdi], rax
0x1800411dd  test    rax, rax
0x1800411e0  jz      short loc_180041221
0x1800411e2  xor     r9d, r9d; dwFileOffsetLow
0x1800411e5  mov     [rsp+38h+dwNumberOfBytesToMap], rbx; dwNumberOfBytesToMap
0x1800411ea  xor     r8d, r8d; dwFileOffsetHigh
0x1800411ed  mov     edx, 0F001Fh; dwDesiredAccess
0x1800411f2  mov     rcx, rax; hFileMappingObject
0x1800411f5  call    cs:__imp_MapViewOfFile
0x1800411fb  mov     [rsi], rax
0x1800411fe  test    rax, rax
0x180041201  jz      short loc_180041207
0x180041203  xor     eax, eax
0x180041205  jmp     short loc_18004122B
0x180041207  call    cs:__imp_GetLastError
0x18004120d  mov     rcx, [rdi]; hObject
0x180041210  mov     ebx, eax
0x180041212  call    cs:__imp_CloseHandle
0x180041218  mov     qword ptr [rdi], 0
0x18004121f  jmp     short loc_180041229
0x180041221  call    cs:__imp_GetLastError
0x180041227  mov     ebx, eax
0x180041229  mov     eax, ebx
0x18004122b  mov     rbx, [rsp+38h+arg_0]
0x180041230  mov     rsi, [rsp+38h+arg_8]
0x180041235  add     rsp, 30h
0x180041239  pop     rdi
0x18004123a  retn
```
