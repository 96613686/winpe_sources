# MyCreateMappedFileByHandle

- ea: `0x180006e64`
- end: `0x180006ee2`
- name: `MyCreateMappedFileByHandle`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003580`
- `0x1800036e0`

## callees

- `0x180006e64`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ebb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006eaf`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006eaf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180006e8b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180006e8b`

## pseudocode

```c
__int64 __fastcall MyCreateMappedFileByHandle(void *a1, DWORD a2, _QWORD *a3)
{
  HANDLE FileMappingA; // rax
  void *v5; // rdi
  LPVOID v6; // rbx

  FileMappingA = CreateFileMappingA(a1, 0, 4u, 0, a2, 0);
  v5 = FileMappingA;
  if ( !FileMappingA )
    return 0;
  v6 = MapViewOfFile(FileMappingA, 2u, 0, 0, 0);
  CloseHandle(v5);
  if ( !v6 )
    return 0;
  *a3 = v6;
  return 1;
}

```

## disassembly

```asm
0x180006e64  mov     rax, rsp
0x180006e67  mov     [rax+8], rbx
0x180006e6b  mov     [rax+10h], rsi
0x180006e6f  push    rdi
0x180006e70  sub     rsp, 30h
0x180006e74  xor     r9d, r9d; dwMaximumSizeHigh
0x180006e77  mov     qword ptr [rax-10h], 0
0x180006e7f  mov     rsi, r8
0x180006e82  mov     [rax-18h], edx
0x180006e85  xor     edx, edx; lpFileMappingAttributes
0x180006e87  lea     r8d, [r9+4]; flProtect
0x180006e8b  call    cs:__imp_CreateFileMappingA
0x180006e91  mov     rdi, rax
0x180006e94  test    rax, rax
0x180006e97  jz      short loc_180006ED0
0x180006e99  xor     r9d, r9d; dwFileOffsetLow
0x180006e9c  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180006ea5  xor     r8d, r8d; dwFileOffsetHigh
0x180006ea8  mov     rcx, rax; hFileMappingObject
0x180006eab  lea     edx, [r9+2]; dwDesiredAccess
0x180006eaf  call    cs:__imp_MapViewOfFile
0x180006eb5  mov     rcx, rdi; hObject
0x180006eb8  mov     rbx, rax
0x180006ebb  call    cs:__imp_CloseHandle
0x180006ec1  test    rbx, rbx
0x180006ec4  jz      short loc_180006ED0
0x180006ec6  mov     [rsi], rbx
0x180006ec9  mov     eax, 1
0x180006ece  jmp     short loc_180006ED2
0x180006ed0  xor     eax, eax
0x180006ed2  mov     rbx, [rsp+38h+arg_0]
0x180006ed7  mov     rsi, [rsp+38h+arg_8]
0x180006edc  add     rsp, 30h
0x180006ee0  pop     rdi
0x180006ee1  retn
```
