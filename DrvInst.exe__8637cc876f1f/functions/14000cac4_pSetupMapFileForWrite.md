# pSetupMapFileForWrite

- ea: `0x14000cac4`
- end: `0x14000cb57`
- name: `pSetupMapFileForWrite`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x14000da54`
- `0x140010028`

## callees

- `0x14000cac4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cb2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cb2e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14000caf0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14000caf0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14000cb11`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14000cb11`

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
0x14000cac4  mov     rax, rsp
0x14000cac7  mov     [rax+8], rbx
0x14000cacb  mov     [rax+10h], rsi
0x14000cacf  push    rdi
0x14000cad0  sub     rsp, 30h
0x14000cad4  mov     ebx, edx
0x14000cad6  mov     rsi, r9
0x14000cad9  xor     r9d, r9d; dwMaximumSizeHigh
0x14000cadc  mov     qword ptr [rax-10h], 0
0x14000cae4  mov     rdi, r8
0x14000cae7  mov     [rax-18h], ebx
0x14000caea  xor     edx, edx; lpFileMappingAttributes
0x14000caec  lea     r8d, [r9+4]; flProtect
0x14000caf0  call    cs:__imp_CreateFileMappingW
0x14000caf6  mov     [rdi], rax
0x14000caf9  test    rax, rax
0x14000cafc  jz      short loc_14000CB3D
0x14000cafe  xor     r9d, r9d; dwFileOffsetLow
0x14000cb01  mov     [rsp+38h+dwNumberOfBytesToMap], rbx; dwNumberOfBytesToMap
0x14000cb06  xor     r8d, r8d; dwFileOffsetHigh
0x14000cb09  mov     edx, 0F001Fh; dwDesiredAccess
0x14000cb0e  mov     rcx, rax; hFileMappingObject
0x14000cb11  call    cs:__imp_MapViewOfFile
0x14000cb17  mov     [rsi], rax
0x14000cb1a  test    rax, rax
0x14000cb1d  jz      short loc_14000CB23
0x14000cb1f  xor     eax, eax
0x14000cb21  jmp     short loc_14000CB47
0x14000cb23  call    cs:__imp_GetLastError
0x14000cb29  mov     rcx, [rdi]; hObject
0x14000cb2c  mov     ebx, eax
0x14000cb2e  call    cs:__imp_CloseHandle
0x14000cb34  mov     qword ptr [rdi], 0
0x14000cb3b  jmp     short loc_14000CB45
0x14000cb3d  call    cs:__imp_GetLastError
0x14000cb43  mov     ebx, eax
0x14000cb45  mov     eax, ebx
0x14000cb47  mov     rbx, [rsp+38h+arg_0]
0x14000cb4c  mov     rsi, [rsp+38h+arg_8]
0x14000cb51  add     rsp, 30h
0x14000cb55  pop     rdi
0x14000cb56  retn
```
