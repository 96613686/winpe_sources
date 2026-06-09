# __archive_write_program_close

- ea: `0x1800f2aa0`
- end: `0x1800f2bd7`
- name: `__archive_write_program_close`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800f1a20`
- `0x1800f2430`

## callees

- `0x180006c00`
- `0x18000e8d4`
- `0x18000eafc`
- `0x1800ef254`
- `0x1800f2aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2af7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2b32`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2b41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2b91`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2af7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2b32`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2b41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f2b91`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800f2ac9`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800f2b69`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800f2b77`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800f2ac9`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800f2b69`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800f2b77`

## string_xrefs

- `0x1800f2b4b`: `Error reading from program: %s`

## pseudocode

```c
__int64 __fastcall _archive_write_program_close(__int64 a1, __int64 a2)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rcx
  const char *v9; // rbx
  unsigned int *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // esi

  if ( !*(_QWORD *)a2 )
    return 0;
  v5 = 0;
  _o__close(*(unsigned int *)(a2 + 8));
  *(_DWORD *)(a2 + 8) = -1;
  while ( 1 )
  {
    do
      v7 = _la_read(
             *(_DWORD *)(a2 + 12),
             (void *)(*(_QWORD *)(a2 + 32) + *(_QWORD *)(a2 + 16)),
             *(_QWORD *)(a2 + 24) - *(_QWORD *)(a2 + 32));
    while ( v7 == -1 && *(_DWORD *)_o__errno(v6) == 4 );
    if ( !v7 )
      break;
    if ( v7 == -1 )
    {
      if ( *(_DWORD *)_o__errno(v6) == 32 )
        break;
      v9 = *(const char **)(a2 + 40);
      v10 = (unsigned int *)_o__errno(v8);
      archive_set_error(*(_QWORD *)(a1 + 8), *v10, "Error reading from program: %s", v9);
LABEL_12:
      v5 = -30;
      break;
    }
    *(_QWORD *)(a2 + 32) += v7;
    v5 = _archive_write_filter(*(_QWORD *)(a1 + 16), *(_QWORD *)(a2 + 16), *(_QWORD *)(a2 + 32));
    if ( v5 )
      goto LABEL_12;
    *(_QWORD *)(a2 + 32) = 0;
  }
  v11 = *(unsigned int *)(a2 + 8);
  if ( (_DWORD)v11 != -1 )
    _o__close(v11);
  v12 = *(unsigned int *)(a2 + 12);
  if ( (_DWORD)v12 != -1 )
    _o__close(v12);
  do
    v14 = _la_waitpid(*(HANDLE *)a2);
  while ( v14 == -1 && *(_DWORD *)_o__errno(v13) == 4 );
  *(_QWORD *)a2 = 0;
  if ( v14 < 0 )
  {
    archive_set_error(*(_QWORD *)(a1 + 8), 5, "Error closing program: %s", *(const char **)(a2 + 40));
    return (unsigned int)-30;
  }
  return v5;
}

```

## disassembly

```asm
0x1800f2aa0  push    rbx
0x1800f2aa2  push    rbp
0x1800f2aa3  push    rsi
0x1800f2aa4  push    rdi
0x1800f2aa5  sub     rsp, 28h
0x1800f2aa9  cmp     qword ptr [rdx], 0
0x1800f2aad  mov     rdi, rdx
0x1800f2ab0  mov     rbp, rcx
0x1800f2ab3  mov     [rsp+48h+arg_8], 0
0x1800f2abb  jnz     short loc_1800F2AC4
0x1800f2abd  xor     eax, eax
0x1800f2abf  jmp     loc_1800F2BCE
0x1800f2ac4  mov     ecx, [rdx+8]
0x1800f2ac7  xor     ebx, ebx
0x1800f2ac9  call    cs:__imp__o__close
0x1800f2acf  mov     dword ptr [rdi+8], 0FFFFFFFFh
0x1800f2ad6  mov     r8, [rdi+18h]
0x1800f2ada  mov     rdx, [rdi+10h]
0x1800f2ade  sub     r8, [rdi+20h]
0x1800f2ae2  add     rdx, [rdi+20h]
0x1800f2ae6  mov     ecx, [rdi+0Ch]
0x1800f2ae9  call    __la_read
0x1800f2aee  mov     rsi, rax
0x1800f2af1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f2af5  jnz     short loc_1800F2B02
0x1800f2af7  call    cs:__imp__o__errno
0x1800f2afd  cmp     dword ptr [rax], 4
0x1800f2b00  jz      short loc_1800F2AD6
0x1800f2b02  test    rsi, rsi
0x1800f2b05  jz      short loc_1800F2B61
0x1800f2b07  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800f2b0b  jz      short loc_1800F2B32
0x1800f2b0d  add     [rdi+20h], rsi
0x1800f2b11  mov     r8, [rdi+20h]
0x1800f2b15  mov     rcx, [rbp+10h]
0x1800f2b19  mov     rdx, [rdi+10h]
0x1800f2b1d  call    __archive_write_filter
0x1800f2b22  mov     ebx, eax
0x1800f2b24  test    eax, eax
0x1800f2b26  jnz     short loc_1800F2B5C
0x1800f2b28  mov     qword ptr [rdi+20h], 0
0x1800f2b30  jmp     short loc_1800F2AD6
0x1800f2b32  call    cs:__imp__o__errno
0x1800f2b38  cmp     dword ptr [rax], 20h ; ' '
0x1800f2b3b  jz      short loc_1800F2B61
0x1800f2b3d  mov     rbx, [rdi+28h]
0x1800f2b41  call    cs:__imp__o__errno
0x1800f2b47  mov     rcx, [rbp+8]
0x1800f2b4b  lea     r8, aErrorReadingFr; "Error reading from program: %s"
0x1800f2b52  mov     r9, rbx
0x1800f2b55  mov     edx, [rax]
0x1800f2b57  call    archive_set_error
0x1800f2b5c  mov     ebx, 0FFFFFFE2h
0x1800f2b61  mov     ecx, [rdi+8]
0x1800f2b64  cmp     ecx, 0FFFFFFFFh
0x1800f2b67  jz      short loc_1800F2B6F
0x1800f2b69  call    cs:__imp__o__close
0x1800f2b6f  mov     ecx, [rdi+0Ch]
0x1800f2b72  cmp     ecx, 0FFFFFFFFh
0x1800f2b75  jz      short loc_1800F2B7D
0x1800f2b77  call    cs:__imp__o__close
0x1800f2b7d  mov     rcx, [rdi]; hObject
0x1800f2b80  lea     rdx, [rsp+48h+arg_8]
0x1800f2b85  call    __la_waitpid
0x1800f2b8a  mov     esi, eax
0x1800f2b8c  cmp     eax, 0FFFFFFFFh
0x1800f2b8f  jnz     short loc_1800F2B9C
0x1800f2b91  call    cs:__imp__o__errno
0x1800f2b97  cmp     dword ptr [rax], 4
0x1800f2b9a  jz      short loc_1800F2B7D
0x1800f2b9c  mov     qword ptr [rdi], 0
0x1800f2ba3  test    esi, esi
0x1800f2ba5  js      short loc_1800F2BAE
0x1800f2ba7  cmp     [rsp+48h+arg_8], 0
0x1800f2bac  jz      short loc_1800F2BCC
0x1800f2bae  mov     r9, [rdi+28h]
0x1800f2bb2  lea     r8, aErrorClosingPr; "Error closing program: %s"
0x1800f2bb9  mov     rcx, [rbp+8]
0x1800f2bbd  mov     edx, 5
0x1800f2bc2  call    archive_set_error
0x1800f2bc7  mov     ebx, 0FFFFFFE2h
0x1800f2bcc  mov     eax, ebx
0x1800f2bce  add     rsp, 28h
0x1800f2bd2  pop     rdi
0x1800f2bd3  pop     rsi
0x1800f2bd4  pop     rbp
0x1800f2bd5  pop     rbx
0x1800f2bd6  retn
```
