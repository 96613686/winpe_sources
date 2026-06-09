# QueryCorruptionState

- ea: `0x180003ca0`
- end: `0x180003d2d`
- name: `QueryCorruptionState`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800070d0`

## callees

- `0x1800033a0`
- `0x180003ca0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003cdd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d13`

## pseudocode

```c
char __fastcall QueryCorruptionState(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  char CorruptionStateByHandle; // di

  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CorruptionStateByHandle = QueryCorruptionStateByHandle(FileW);
  CloseHandle(v2);
  return CorruptionStateByHandle;
}

```

## disassembly

```asm
0x180003ca0  mov     [rsp+arg_0], rbx
0x180003ca5  mov     [rsp+arg_8], rsi
0x180003caa  push    rdi
0x180003cab  sub     rsp, 40h
0x180003caf  movzx   edi, r8b
0x180003cb3  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180003cbc  mov     rsi, rdx
0x180003cbf  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003cc7  mov     edx, 80000000h; dwDesiredAccess
0x180003ccc  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180003cd4  mov     r8d, 3; dwShareMode
0x180003cda  xor     r9d, r9d; lpSecurityAttributes
0x180003cdd  call    cs:__imp_CreateFileW
0x180003ce3  mov     rbx, rax
0x180003ce6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003cea  jnz     short loc_180003CFE
0x180003cec  xor     al, al
0x180003cee  mov     rbx, [rsp+48h+arg_0]
0x180003cf3  mov     rsi, [rsp+48h+arg_8]
0x180003cf8  add     rsp, 40h
0x180003cfc  pop     rdi
0x180003cfd  retn
0x180003cfe  movzx   r8d, dil
0x180003d02  mov     rdx, rsi
0x180003d05  mov     rcx, rbx; hDevice
0x180003d08  call    QueryCorruptionStateByHandle
0x180003d0d  mov     rcx, rbx; hObject
0x180003d10  movzx   edi, al
0x180003d13  call    cs:__imp_CloseHandle
0x180003d19  mov     rbx, [rsp+48h+arg_0]
0x180003d1e  movzx   eax, dil
0x180003d22  mov     rsi, [rsp+48h+arg_8]
0x180003d27  add     rsp, 40h
0x180003d2b  pop     rdi
0x180003d2c  retn
```
