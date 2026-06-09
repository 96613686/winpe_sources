# ORReadFile

- ea: `0x180087be4`
- end: `0x180087c21`
- name: `ORReadFile`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18008552c`
- `0x180087778`

## callees

- `0x180087be4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180087c0a`
- `KERNEL32!GetLastError` at `0x180087c0a`
- `KERNEL32!ReadFile` at `0x180087bfa`
- `KERNEL32!ReadFile` at `0x180087bfa`

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
0x180087be4  push    rbx
0x180087be6  sub     rsp, 30h
0x180087bea  mov     rax, r8
0x180087bed  xor     ebx, ebx
0x180087bef  mov     r8d, edx; nNumberOfBytesToRead
0x180087bf2  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x180087bf7  mov     rdx, rax; lpBuffer
0x180087bfa  call    cs:__imp_ReadFile
0x180087c01  nop     dword ptr [rax+rax+00h]
0x180087c06  test    eax, eax
0x180087c08  jnz     short loc_180087C18
0x180087c0a  call    cs:__imp_GetLastError
0x180087c11  nop     dword ptr [rax+rax+00h]
0x180087c16  mov     ebx, eax
0x180087c18  mov     eax, ebx
0x180087c1a  add     rsp, 30h
0x180087c1e  pop     rbx
0x180087c1f  retn
```
