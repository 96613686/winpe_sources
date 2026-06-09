# ORReadFile

- ea: `0x180088b44`
- end: `0x180088b81`
- name: `ORReadFile`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180086498`
- `0x1800886d8`

## callees

- `0x180088b44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180088b6a`
- `KERNEL32!GetLastError` at `0x180088b6a`
- `KERNEL32!ReadFile` at `0x180088b5a`
- `KERNEL32!ReadFile` at `0x180088b5a`

## pseudocode

```c
__int64 __fastcall ORReadFile(void *a1, DWORD a2, void *a3, DWORD *a4)
{
  unsigned int v4; // ebx

  v4 = 0;
  if ( !ReadFile(a1, a3, a2, a4, 0) )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x180088b44  push    rbx
0x180088b46  sub     rsp, 30h
0x180088b4a  mov     rax, r8
0x180088b4d  xor     ebx, ebx
0x180088b4f  mov     r8d, edx; nNumberOfBytesToRead
0x180088b52  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x180088b57  mov     rdx, rax; lpBuffer
0x180088b5a  call    cs:__imp_ReadFile
0x180088b61  nop     dword ptr [rax+rax+00h]
0x180088b66  test    eax, eax
0x180088b68  jnz     short loc_180088B78
0x180088b6a  call    cs:__imp_GetLastError
0x180088b71  nop     dword ptr [rax+rax+00h]
0x180088b76  mov     ebx, eax
0x180088b78  mov     eax, ebx
0x180088b7a  add     rsp, 30h
0x180088b7e  pop     rbx
0x180088b7f  retn
```
