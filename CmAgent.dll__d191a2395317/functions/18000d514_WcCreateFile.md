# WcCreateFile

- ea: `0x18000d514`
- end: `0x18000d5ca`
- name: `WcCreateFile`
- size: `182`
- prototype: `__int64 __fastcall(int, int, int, int, void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d80c`

## callees

- `0x18000d514`
- `0x18000ddb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d5b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d5b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d589`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d577`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d577`

## pseudocode

```c
__int64 __fastcall WcCreateFile(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, void *Block)
{
  __int64 result; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  LPCWSTR lpFileName; // [rsp+50h] [rbp+8h] BYREF

  *a1 = -1;
  Block = 0;
  lpFileName = 0;
  result = WcpConstructLongPath(a2, &Block, &lpFileName);
  if ( (int)result >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      *a1 = FileW;
      v9 = 0;
    }
    if ( Block )
      free(Block);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18000d514  mov     r11, rsp
0x18000d517  push    rbx
0x18000d518  sub     rsp, 40h
0x18000d51c  mov     rax, rdx
0x18000d51f  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000d526  mov     rbx, rcx
0x18000d529  mov     qword ptr [r11+28h], 0
0x18000d531  mov     rcx, rax
0x18000d534  mov     qword ptr [r11+8], 0
0x18000d53c  lea     r8, [r11+8]
0x18000d540  lea     rdx, [r11+28h]
0x18000d544  call    WcpConstructLongPath
0x18000d549  test    eax, eax
0x18000d54b  js      short loc_18000D5C3
0x18000d54d  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x18000d552  xor     r9d, r9d; lpSecurityAttributes
0x18000d555  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000d55e  mov     edx, 80000000h; dwDesiredAccess
0x18000d563  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000d56b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d573  lea     r8d, [r9+7]; dwShareMode
0x18000d577  call    cs:__imp_CreateFileW
0x18000d57e  nop     dword ptr [rax+rax+00h]
0x18000d583  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d587  jnz     short loc_18000D5A6
0x18000d589  call    cs:__imp_GetLastError
0x18000d590  nop     dword ptr [rax+rax+00h]
0x18000d595  mov     ebx, eax
0x18000d597  test    eax, eax
0x18000d599  jle     short loc_18000D5AB
0x18000d59b  movzx   ebx, ax
0x18000d59e  or      ebx, 80070000h
0x18000d5a4  jmp     short loc_18000D5AB
0x18000d5a6  mov     [rbx], rax
0x18000d5a9  xor     ebx, ebx
0x18000d5ab  mov     rcx, [rsp+48h+Block]; Block
0x18000d5b0  test    rcx, rcx
0x18000d5b3  jz      short loc_18000D5C1
0x18000d5b5  call    cs:__imp_free
0x18000d5bc  nop     dword ptr [rax+rax+00h]
0x18000d5c1  mov     eax, ebx
0x18000d5c3  add     rsp, 40h
0x18000d5c7  pop     rbx
0x18000d5c8  retn
```
