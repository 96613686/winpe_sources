# MapFileClose

- ea: `0x180030ee8`
- end: `0x180030f5a`
- name: `MapFileClose`
- size: `114`
- prototype: `BOOL __fastcall(__int64, LONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180035d78`
- `0x180036b20`

## callees

- `0x180030ee8`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180030f26`
- `KERNEL32!SetFilePointer` at `0x180030f26`
- `KERNEL32!SetEndOfFile` at `0x180030f35`
- `KERNEL32!SetEndOfFile` at `0x180030f35`
- `KERNEL32!UnmapViewOfFile` at `0x180030efb`
- `KERNEL32!UnmapViewOfFile` at `0x180030efb`
- `KERNEL32!CloseHandle` at `0x180030f0b`
- `KERNEL32!CloseHandle` at `0x180030f0b`
- `KERNEL32!CloseHandle` at `0x180030f4e`

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
0x180030ee8  mov     [rsp+arg_0], rbx
0x180030eed  push    rdi
0x180030eee  sub     rsp, 20h
0x180030ef2  mov     rbx, rcx
0x180030ef5  mov     edi, edx
0x180030ef7  mov     rcx, [rcx+10h]; lpBaseAddress
0x180030efb  call    cs:__imp_UnmapViewOfFile
0x180030f02  nop     dword ptr [rax+rax+00h]
0x180030f07  mov     rcx, [rbx+8]; hObject
0x180030f0b  call    cs:__imp_CloseHandle
0x180030f12  nop     dword ptr [rax+rax+00h]
0x180030f17  test    edi, edi
0x180030f19  jz      short loc_180030F41
0x180030f1b  mov     rcx, [rbx]; hFile
0x180030f1e  xor     r9d, r9d; dwMoveMethod
0x180030f21  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030f24  mov     edx, edi; lDistanceToMove
0x180030f26  call    cs:__imp_SetFilePointer
0x180030f2d  nop     dword ptr [rax+rax+00h]
0x180030f32  mov     rcx, [rbx]; hFile
0x180030f35  call    cs:__imp_SetEndOfFile
0x180030f3c  nop     dword ptr [rax+rax+00h]
0x180030f41  mov     rcx, [rbx]
0x180030f44  mov     rbx, [rsp+28h+arg_0]
0x180030f49  add     rsp, 20h
0x180030f4d  pop     rdi
0x180030f4e  jmp     cs:__imp_CloseHandle
```
