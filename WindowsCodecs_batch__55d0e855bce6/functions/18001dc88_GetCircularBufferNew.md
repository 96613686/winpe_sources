# GetCircularBufferNew

- ea: `0x18001dc88`
- end: `0x18001dd1a`
- name: `GetCircularBufferNew`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d7d0`

## callees

- `0x18001dc88`
- `0x1800a7aa4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd0c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18001dcb4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18001dcb4`

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
0x18001dc88  push    rbx
0x18001dc8a  push    rbp
0x18001dc8b  push    rsi
0x18001dc8c  push    rdi
0x18001dc8d  sub     rsp, 38h
0x18001dc91  mov     rbp, rcx
0x18001dc94  mov     [rsp+58h+lpName], 0; lpName
0x18001dc9d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001dca1  mov     [rsp+58h+dwMaximumSizeLow], 10000h; dwMaximumSizeLow
0x18001dca9  xor     r9d, r9d; dwMaximumSizeHigh
0x18001dcac  xor     edx, edx; lpFileMappingAttributes
0x18001dcae  mov     r8d, 8000004h; flProtect
0x18001dcb4  call    cs:__imp_CreateFileMappingA
0x18001dcbb  nop     dword ptr [rax+rax+00h]
0x18001dcc0  mov     rsi, rax
0x18001dcc3  test    rax, rax
0x18001dcc6  jz      short loc_18001DCFA
0x18001dcc8  xor     edi, edi
0x18001dcca  lea     ebx, [rdi+1]
0x18001dccd  cmp     edi, 64h ; 'd'
0x18001dcd0  jge     short loc_18001DD09
0x18001dcd2  lea     r8, [rsp+58h+arg_8]
0x18001dcd7  mov     [rsp+58h+arg_8], 0
0x18001dcdf  mov     rdx, rbp
0x18001dce2  mov     rcx, rsi; hFileMappingObject
0x18001dce5  call    CreateFileMappingForCircularBuffer
0x18001dcea  test    eax, eax
0x18001dcec  jz      short loc_18001DCFE
0x18001dcee  mov     eax, ebx
0x18001dcf0  add     rsp, 38h
0x18001dcf4  pop     rdi
0x18001dcf5  pop     rsi
0x18001dcf6  pop     rbp
0x18001dcf7  pop     rbx
0x18001dcf8  retn
0x18001dcfa  xor     ebx, ebx
0x18001dcfc  jmp     short loc_18001DCEE
0x18001dcfe  cmp     [rsp+58h+arg_8], 0
0x18001dd03  jz      short loc_18001DD09
0x18001dd05  add     edi, ebx
0x18001dd07  jmp     short loc_18001DCCD
0x18001dd09  mov     rcx, rsi; hObject
0x18001dd0c  call    cs:__imp_CloseHandle
0x18001dd13  nop     dword ptr [rax+rax+00h]
0x18001dd18  jmp     short loc_18001DCFA
```
