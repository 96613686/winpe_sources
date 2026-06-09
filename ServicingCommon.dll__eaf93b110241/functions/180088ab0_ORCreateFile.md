# ORCreateFile

- ea: `0x180088ab0`
- end: `0x180088b03`
- name: `ORCreateFile`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180086498`
- `0x1800886d8`

## callees

- `0x180088ab0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180088aec`
- `KERNEL32!GetLastError` at `0x180088aec`
- `KERNEL32!CreateFileW` at `0x180088acf`
- `KERNEL32!CreateFileW` at `0x180088acf`

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
0x180088ab0  push    rbx
0x180088ab2  sub     rsp, 40h
0x180088ab6  xor     ebx, ebx
0x180088ab8  mov     r8d, r9d; dwShareMode
0x180088abb  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180088ac0  xor     r9d, r9d; lpSecurityAttributes
0x180088ac3  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180088ac7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180088acf  call    cs:__imp_CreateFileW
0x180088ad6  nop     dword ptr [rax+rax+00h]
0x180088adb  mov     rcx, rax
0x180088ade  mov     rax, [rsp+48h+arg_20]
0x180088ae3  mov     [rax], rcx
0x180088ae6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180088aea  jnz     short loc_180088AFA
0x180088aec  call    cs:__imp_GetLastError
0x180088af3  nop     dword ptr [rax+rax+00h]
0x180088af8  mov     ebx, eax
0x180088afa  mov     eax, ebx
0x180088afc  add     rsp, 40h
0x180088b00  pop     rbx
0x180088b01  retn
```
