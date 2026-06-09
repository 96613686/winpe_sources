# GetCircularBufferNew

- ea: `0x18004c660`
- end: `0x18004c6e5`
- name: `GetCircularBufferNew`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004c1b8`

## callees

- `0x18004c660`
- `0x1800a55c8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c6dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c6dd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18004c68c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18004c68c`

## pseudocode

```c
__int64 GetCircularBufferNew()
{
  HANDLE FileMappingA; // rsi
  unsigned int v1; // ebx

  FileMappingA = CreateFileMappingA((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, 0x10000u, 0);
  if ( !FileMappingA )
    return 0;
  v1 = 1;
  if ( !(unsigned int)CreateFileMappingForCircularBuffer(FileMappingA) )
  {
    CloseHandle(FileMappingA);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18004c660  push    rbx
0x18004c662  push    rbp
0x18004c663  push    rsi
0x18004c664  push    rdi
0x18004c665  sub     rsp, 38h
0x18004c669  mov     rbp, rcx
0x18004c66c  mov     [rsp+58h+lpName], 0; lpName
0x18004c675  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004c679  mov     [rsp+58h+dwMaximumSizeLow], 10000h; dwMaximumSizeLow
0x18004c681  xor     r9d, r9d; dwMaximumSizeHigh
0x18004c684  xor     edx, edx; lpFileMappingAttributes
0x18004c686  mov     r8d, 8000004h; flProtect
0x18004c68c  call    cs:__imp_CreateFileMappingA
0x18004c692  mov     rsi, rax
0x18004c695  test    rax, rax
0x18004c698  jz      short loc_18004C6CB
0x18004c69a  xor     edi, edi
0x18004c69c  lea     ebx, [rdi+1]
0x18004c69f  cmp     edi, 64h ; 'd'
0x18004c6a2  jge     short loc_18004C6DA
0x18004c6a4  lea     r8, [rsp+58h+arg_8]
0x18004c6a9  mov     [rsp+58h+arg_8], 0
0x18004c6b1  mov     rdx, rbp
0x18004c6b4  mov     rcx, rsi; hFileMappingObject
0x18004c6b7  call    CreateFileMappingForCircularBuffer
0x18004c6bc  test    eax, eax
0x18004c6be  jz      short loc_18004C6CF
0x18004c6c0  mov     eax, ebx
0x18004c6c2  add     rsp, 38h
0x18004c6c6  pop     rdi
0x18004c6c7  pop     rsi
0x18004c6c8  pop     rbp
0x18004c6c9  pop     rbx
0x18004c6ca  retn
0x18004c6cb  xor     ebx, ebx
0x18004c6cd  jmp     short loc_18004C6C0
0x18004c6cf  cmp     [rsp+58h+arg_8], 0
0x18004c6d4  jz      short loc_18004C6DA
0x18004c6d6  add     edi, ebx
0x18004c6d8  jmp     short loc_18004C69F
0x18004c6da  mov     rcx, rsi; hObject
0x18004c6dd  call    cs:__imp_CloseHandle
0x18004c6e3  jmp     short loc_18004C6CB
```
