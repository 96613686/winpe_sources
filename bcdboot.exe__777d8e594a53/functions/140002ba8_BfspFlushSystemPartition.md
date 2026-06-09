# BfspFlushSystemPartition

- ea: `0x140002ba8`
- end: `0x140002c0e`
- name: `BfspFlushSystemPartition`
- size: `102`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004080`
- `0x140009fd4`

## callees

- `0x140002ba8`
- `0x1400032d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140002be2`
- `KERNEL32!GetLastError` at `0x140002be2`
- `KERNEL32!CloseHandle` at `0x140002bfb`
- `KERNEL32!CloseHandle` at `0x140002bfb`
- `KERNEL32!FlushFileBuffers` at `0x140002bd8`
- `KERNEL32!FlushFileBuffers` at `0x140002bd8`

## pseudocode

```c
__int64 BfspFlushSystemPartition()
{
  DWORD v0; // eax
  char *v1; // rdi
  DWORD LastError; // ebx
  HANDLE hFile; // [rsp+30h] [rbp+8h] BYREF

  hFile = 0;
  v0 = BfspOpenSystemPartition(&hFile, 3221225472LL);
  v1 = (char *)hFile;
  LastError = v0;
  if ( !v0 )
  {
    if ( FlushFileBuffers(hFile) )
      LastError = 0;
    else
      LastError = GetLastError();
  }
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v1);
  return LastError;
}

```

## disassembly

```asm
0x140002ba8  mov     [rsp+arg_8], rbx
0x140002bad  push    rdi
0x140002bae  sub     rsp, 20h
0x140002bb2  mov     edx, 0C0000000h
0x140002bb7  mov     [rsp+28h+hFile], 0
0x140002bc0  lea     rcx, [rsp+28h+hFile]
0x140002bc5  call    BfspOpenSystemPartition
0x140002bca  mov     rdi, [rsp+28h+hFile]
0x140002bcf  mov     ebx, eax
0x140002bd1  test    eax, eax
0x140002bd3  jnz     short loc_140002BEE
0x140002bd5  mov     rcx, rdi; hFile
0x140002bd8  call    cs:__imp_FlushFileBuffers
0x140002bde  test    eax, eax
0x140002be0  jnz     short loc_140002BEC
0x140002be2  call    cs:__imp_GetLastError
0x140002be8  mov     ebx, eax
0x140002bea  jmp     short loc_140002BEE
0x140002bec  xor     ebx, ebx
0x140002bee  lea     rax, [rdi-1]
0x140002bf2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002bf6  ja      short loc_140002C01
0x140002bf8  mov     rcx, rdi; hObject
0x140002bfb  call    cs:__imp_CloseHandle
0x140002c01  mov     eax, ebx
0x140002c03  mov     rbx, [rsp+28h+arg_8]
0x140002c08  add     rsp, 20h
0x140002c0c  pop     rdi
0x140002c0d  retn
```
