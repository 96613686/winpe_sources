# TextLogUpdateEof

- ea: `0x14000e0b4`
- end: `0x14000e0ed`
- name: `TextLogUpdateEof`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x14000d2ec`
- `0x14000d3c4`

## callees

- `0x14000e0b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0dd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000e0d2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000e0d2`

## pseudocode

```c
__int64 __fastcall TextLogUpdateEof(__int64 a1, int a2)
{
  unsigned int v2; // ebx

  *(_QWORD *)(a1 + 24) += a2;
  v2 = 0;
  if ( SetFilePointer(*(HANDLE *)a1, *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16), 0, 0) == -1 )
    return GetLastError();
  return v2;
}

```

## disassembly

```asm
0x14000e0b4  push    rbx
0x14000e0b6  sub     rsp, 20h
0x14000e0ba  movsxd  rax, edx
0x14000e0bd  xor     r9d, r9d; dwMoveMethod
0x14000e0c0  add     [rcx+18h], rax
0x14000e0c4  xor     r8d, r8d; lpDistanceToMoveHigh
0x14000e0c7  mov     edx, [rcx+18h]
0x14000e0ca  xor     ebx, ebx
0x14000e0cc  sub     edx, [rcx+10h]; lDistanceToMove
0x14000e0cf  mov     rcx, [rcx]; hFile
0x14000e0d2  call    cs:__imp_SetFilePointer
0x14000e0d8  cmp     eax, 0FFFFFFFFh
0x14000e0db  jnz     short loc_14000E0E5
0x14000e0dd  call    cs:__imp_GetLastError
0x14000e0e3  mov     ebx, eax
0x14000e0e5  mov     eax, ebx
0x14000e0e7  add     rsp, 20h
0x14000e0eb  pop     rbx
0x14000e0ec  retn
```
