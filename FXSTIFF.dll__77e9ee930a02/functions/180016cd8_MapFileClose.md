# MapFileClose

- ea: `0x180016cd8`
- end: `0x180016d4a`
- name: `MapFileClose`
- size: `114`
- prototype: `BOOL __fastcall(__int64, LONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004540`
- `0x180005c30`

## callees

- `0x180016cd8`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x180016d25`
- `KERNEL32!SetEndOfFile` at `0x180016d25`
- `KERNEL32!UnmapViewOfFile` at `0x180016ceb`
- `KERNEL32!UnmapViewOfFile` at `0x180016ceb`
- `KERNEL32!SetFilePointer` at `0x180016d16`
- `KERNEL32!SetFilePointer` at `0x180016d16`
- `KERNEL32!CloseHandle` at `0x180016cfb`
- `KERNEL32!CloseHandle` at `0x180016cfb`
- `KERNEL32!CloseHandle` at `0x180016d3e`

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
0x180016cd8  mov     [rsp+arg_0], rbx
0x180016cdd  push    rdi
0x180016cde  sub     rsp, 20h
0x180016ce2  mov     rbx, rcx
0x180016ce5  mov     edi, edx
0x180016ce7  mov     rcx, [rcx+10h]; lpBaseAddress
0x180016ceb  call    cs:__imp_UnmapViewOfFile
0x180016cf2  nop     dword ptr [rax+rax+00h]
0x180016cf7  mov     rcx, [rbx+8]; hObject
0x180016cfb  call    cs:__imp_CloseHandle
0x180016d02  nop     dword ptr [rax+rax+00h]
0x180016d07  test    edi, edi
0x180016d09  jz      short loc_180016D31
0x180016d0b  mov     rcx, [rbx]; hFile
0x180016d0e  xor     r9d, r9d; dwMoveMethod
0x180016d11  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016d14  mov     edx, edi; lDistanceToMove
0x180016d16  call    cs:__imp_SetFilePointer
0x180016d1d  nop     dword ptr [rax+rax+00h]
0x180016d22  mov     rcx, [rbx]; hFile
0x180016d25  call    cs:__imp_SetEndOfFile
0x180016d2c  nop     dword ptr [rax+rax+00h]
0x180016d31  mov     rcx, [rbx]
0x180016d34  mov     rbx, [rsp+28h+arg_0]
0x180016d39  add     rsp, 20h
0x180016d3d  pop     rdi
0x180016d3e  jmp     cs:__imp_CloseHandle
```
