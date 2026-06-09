# MapFileClose

- ea: `0x1800160e0`
- end: `0x180016135`
- name: `MapFileClose`
- size: `85`
- prototype: `BOOL __fastcall(__int64, LONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800044f0`
- `0x180005b00`

## callees

- `0x1800160e0`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x18001611b`
- `KERNEL32!SetEndOfFile` at `0x18001611b`
- `KERNEL32!UnmapViewOfFile` at `0x1800160f3`
- `KERNEL32!UnmapViewOfFile` at `0x1800160f3`
- `KERNEL32!SetFilePointer` at `0x180016112`
- `KERNEL32!SetFilePointer` at `0x180016112`
- `KERNEL32!CloseHandle` at `0x1800160fd`
- `KERNEL32!CloseHandle` at `0x1800160fd`
- `KERNEL32!CloseHandle` at `0x18001612e`

## pseudocode

```c
BOOL __fastcall MapFileClose(__int64 a1, LONG a2)
{
  UnmapViewOfFile(*(LPCVOID *)(a1 + 16));
  CloseHandle(*(HANDLE *)(a1 + 8));
  if ( a2 )
  {
    SetFilePointer(*(HANDLE *)a1, a2, 0, 0);
    SetEndOfFile(*(HANDLE *)a1);
  }
  return CloseHandle(*(HANDLE *)a1);
}

```

## disassembly

```asm
0x1800160e0  mov     [rsp+arg_0], rbx
0x1800160e5  push    rdi
0x1800160e6  sub     rsp, 20h
0x1800160ea  mov     rbx, rcx
0x1800160ed  mov     edi, edx
0x1800160ef  mov     rcx, [rcx+10h]; lpBaseAddress
0x1800160f3  call    cs:__imp_UnmapViewOfFile
0x1800160f9  mov     rcx, [rbx+8]; hObject
0x1800160fd  call    cs:__imp_CloseHandle
0x180016103  test    edi, edi
0x180016105  jz      short loc_180016121
0x180016107  mov     rcx, [rbx]; hFile
0x18001610a  xor     r9d, r9d; dwMoveMethod
0x18001610d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016110  mov     edx, edi; lDistanceToMove
0x180016112  call    cs:__imp_SetFilePointer
0x180016118  mov     rcx, [rbx]; hFile
0x18001611b  call    cs:__imp_SetEndOfFile
0x180016121  mov     rcx, [rbx]
0x180016124  mov     rbx, [rsp+28h+arg_0]
0x180016129  add     rsp, 20h
0x18001612d  pop     rdi
0x18001612e  jmp     cs:__imp_CloseHandle
```
