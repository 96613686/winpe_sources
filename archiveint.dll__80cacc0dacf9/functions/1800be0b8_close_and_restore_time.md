# close_and_restore_time

- ea: `0x1800be0b8`
- end: `0x1800be19c`
- name: `close_and_restore_time`
- size: `228`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800bcd70`
- `0x1800bce30`
- `0x1800bd240`
- `0x1800bf708`
- `0x1800bf9b8`

## callees

- `0x1800be0b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be14c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be171`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be14c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800be171`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800be167`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800be167`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800be13e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800be13e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be0f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be0f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be184`

## pseudocode

```c
__int64 __fastcall close_and_restore_time(void *a1, __int64 a2, __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v7; // rcx
  void *v8; // rax
  void *v9; // rsi
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+40h] [rbp-18h]

  v3 = -1;
  v10 = 0;
  v11 = 0;
  if ( a1 == (void *)-1LL )
  {
    if ( *((_WORD *)a3 + 12) == 0xA000 )
      return 0;
  }
  else
  {
    CloseHandle(a1);
  }
  if ( *(char *)(a2 + 624) >= 0 )
    return 0;
  v7 = *a3;
  v10 = 0;
  LODWORD(v10) = 32;
  DWORD2(v10) = 0x2000000;
  v11 = 0;
  v8 = (void *)CreateFile2(v7, 256, 0, 3, &v10);
  v9 = v8;
  if ( v8 == (void *)-1LL )
  {
    *(_DWORD *)_o__errno() = 22;
  }
  else
  {
    if ( SetFileTime(v8, 0, (const FILETIME *)a3 + 2, (const FILETIME *)a3 + 1) )
      v3 = 0;
    else
      *(_DWORD *)_o__errno() = 22;
    CloseHandle(v9);
  }
  return v3;
}

```

## disassembly

```asm
0x1800be0b8  mov     rax, rsp
0x1800be0bb  mov     [rax+8], rbx
0x1800be0bf  mov     [rax+10h], rsi
0x1800be0c3  push    rdi
0x1800be0c4  sub     rsp, 50h
0x1800be0c8  xorps   xmm0, xmm0
0x1800be0cb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800be0cf  mov     rdi, r8
0x1800be0d2  mov     rsi, rdx
0x1800be0d5  movups  xmmword ptr [rax-28h], xmm0
0x1800be0d9  movups  xmmword ptr [rax-18h], xmm0
0x1800be0dd  cmp     rcx, rbx
0x1800be0e0  jnz     short loc_1800BE0F0
0x1800be0e2  mov     eax, 0A000h
0x1800be0e7  cmp     ax, [r8+18h]
0x1800be0ec  jz      short loc_1800BE0FF
0x1800be0ee  jmp     short loc_1800BE0F6
0x1800be0f0  call    cs:__imp_CloseHandle
0x1800be0f6  test    byte ptr [rsi+270h], 80h
0x1800be0fd  jnz     short loc_1800BE106
0x1800be0ff  xor     eax, eax
0x1800be101  jmp     loc_1800BE18C
0x1800be106  mov     rcx, [rdi]
0x1800be109  lea     rax, [rsp+58h+var_28]
0x1800be10e  xorps   xmm0, xmm0
0x1800be111  mov     [rsp+58h+var_38], rax
0x1800be116  movups  [rsp+58h+var_28], xmm0
0x1800be11b  mov     r9d, 3
0x1800be121  mov     dword ptr [rsp+58h+var_28], 20h ; ' '
0x1800be129  xor     r8d, r8d
0x1800be12c  mov     dword ptr [rsp+58h+var_28+8], 2000000h
0x1800be134  mov     edx, 100h
0x1800be139  movups  [rsp+58h+var_18], xmm0
0x1800be13e  call    cs:__imp_CreateFile2
0x1800be144  mov     rsi, rax
0x1800be147  cmp     rax, rbx
0x1800be14a  jnz     short loc_1800BE15A
0x1800be14c  call    cs:__imp__o__errno
0x1800be152  mov     dword ptr [rax], 16h
0x1800be158  jmp     short loc_1800BE18A
0x1800be15a  lea     r9, [rdi+8]; lpLastWriteTime
0x1800be15e  xor     edx, edx; lpCreationTime
0x1800be160  lea     r8, [rdi+10h]; lpLastAccessTime
0x1800be164  mov     rcx, rsi; hFile
0x1800be167  call    cs:__imp_SetFileTime
0x1800be16d  test    eax, eax
0x1800be16f  jnz     short loc_1800BE17F
0x1800be171  call    cs:__imp__o__errno
0x1800be177  mov     dword ptr [rax], 16h
0x1800be17d  jmp     short loc_1800BE181
0x1800be17f  xor     ebx, ebx
0x1800be181  mov     rcx, rsi; hObject
0x1800be184  call    cs:__imp_CloseHandle
0x1800be18a  mov     eax, ebx
0x1800be18c  mov     rbx, [rsp+58h+arg_0]
0x1800be191  mov     rsi, [rsp+58h+arg_8]
0x1800be196  add     rsp, 50h
0x1800be19a  pop     rdi
0x1800be19b  retn
```
