# ORCreateFile

- ea: `0x180030bd0`
- end: `0x180030c23`
- name: `ORCreateFile`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002c1fc`
- `0x18002f9c4`

## callees

- `0x180030bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030bef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030bef`

## pseudocode

```c
__int64 __fastcall ORCreateFile(const WCHAR *a1, DWORD a2, __int64 a3, DWORD a4, _QWORD *a5)
{
  unsigned int v5; // ebx
  HANDLE FileW; // rcx

  v5 = 0;
  FileW = CreateFileW(a1, a2, a4, 0, 3u, 0, 0);
  *a5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x180030bd0  push    rbx
0x180030bd2  sub     rsp, 40h
0x180030bd6  xor     ebx, ebx
0x180030bd8  mov     r8d, r9d; dwShareMode
0x180030bdb  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180030be0  xor     r9d, r9d; lpSecurityAttributes
0x180030be3  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180030be7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180030bef  call    cs:__imp_CreateFileW
0x180030bf6  nop     dword ptr [rax+rax+00h]
0x180030bfb  mov     rcx, rax
0x180030bfe  mov     rax, [rsp+48h+arg_20]
0x180030c03  mov     [rax], rcx
0x180030c06  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180030c0a  jnz     short loc_180030C1A
0x180030c0c  call    cs:__imp_GetLastError
0x180030c13  nop     dword ptr [rax+rax+00h]
0x180030c18  mov     ebx, eax
0x180030c1a  mov     eax, ebx
0x180030c1c  add     rsp, 40h
0x180030c20  pop     rbx
0x180030c21  retn
```
