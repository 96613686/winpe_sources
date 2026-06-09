# archive_read_data_into_fd

- ea: `0x1800bcab0`
- end: `0x1800bcc77`
- name: `archive_read_data_into_fd`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000523c`
- `0x180006c00`
- `0x18000f070`
- `0x18000f0b4`
- `0x18000fe9c`
- `0x1800bcab0`
- `0x1800bcc80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bcbfd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bcbfd`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800bcb59`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800bcb59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bcc4e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bcc4e`

## string_xrefs

- `0x1800bcc03`: `Write error`
- `0x1800bcaed`: `archive_read_data_into_fd`

## pseudocode

```c
__int64 __fastcall archive_read_data_into_fd(__int64 a1, unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  void *v6; // rsi
  unsigned int v7; // r12d
  __int64 v8; // rdi
  char *v9; // r15
  unsigned __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int *v13; // rax
  unsigned int v14; // eax
  char *v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+48h] [rbp-38h]
  __int128 v17; // [rsp+58h] [rbp-28h]
  __int128 v18; // [rsp+68h] [rbp-18h]
  unsigned __int64 v19; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v20; // [rsp+D8h] [rbp+58h] BYREF

  v15 = 0;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v4 = -30;
  if ( (unsigned int)_archive_check_magic(a1, 14594245, 4, "archive_read_data_into_fd") == -30 )
    return 4294967266LL;
  if ( !(unsigned int)_la_fstat(a2) && (WORD3(v16) & 0xF000) == 0x8000 )
  {
    v6 = 0;
    v7 = 1;
    goto LABEL_7;
  }
  v7 = 0;
  v6 = calloc(1u, 0x4000u);
  if ( v6 )
  {
LABEL_7:
    v8 = 0;
    while ( 1 )
    {
      v4 = archive_read_data_block(a1, &v15, &v19, &v20);
      if ( v4 )
        break;
      v9 = v15;
      if ( v20 > v8 )
      {
        v4 = pad_to(a1, a2, v7);
        if ( v4 )
          break;
        v8 = v20;
      }
      v10 = v19;
      while ( v10 )
      {
        if ( v10 > 0x100000 )
          v10 = 0x100000;
        v11 = _la_write(a2, v9, v10);
        v12 = v11;
        if ( v11 < 0 )
        {
          v13 = (unsigned int *)_o__errno(v11);
          archive_set_error(a1, *v13, "Write error");
          v4 = -30;
          goto LABEL_23;
        }
        v8 += v11;
        v9 += v11;
        v10 = v19 - v11;
        v19 -= v12;
      }
    }
    if ( v4 == 1 && v20 > v8 )
    {
      v14 = pad_to(a1, a2, v7);
      if ( v14 )
        v4 = v14;
    }
  }
LABEL_23:
  free(v6);
  result = 0;
  if ( v4 != 1 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x1800bcab0  mov     [rsp-38h+arg_0], rbx
0x1800bcab5  push    rbp
0x1800bcab6  push    rsi
0x1800bcab7  push    rdi
0x1800bcab8  push    r12
0x1800bcaba  push    r13
0x1800bcabc  push    r14
0x1800bcabe  push    r15
0x1800bcac0  mov     rbp, rsp
0x1800bcac3  sub     rsp, 80h
0x1800bcaca  xorps   xmm0, xmm0
0x1800bcacd  mov     [rbp+var_40], 0
0x1800bcad5  mov     r13d, edx
0x1800bcad8  mov     [rbp+arg_10], 0
0x1800bcae0  mov     edx, 0DEB0C5h
0x1800bcae5  mov     [rbp+arg_18], 0
0x1800bcaed  lea     r9, aArchiveReadDat_3; "archive_read_data_into_fd"
0x1800bcaf4  mov     r8d, 4
0x1800bcafa  movups  [rbp+var_38], xmm0
0x1800bcafe  mov     r14, rcx
0x1800bcb01  movups  [rbp+var_28], xmm0
0x1800bcb05  movups  [rbp+var_18], xmm0
0x1800bcb09  call    __archive_check_magic
0x1800bcb0e  mov     ebx, 0FFFFFFE2h
0x1800bcb13  cmp     eax, ebx
0x1800bcb15  jnz     short loc_1800BCB1E
0x1800bcb17  mov     eax, ebx
0x1800bcb19  jmp     loc_1800BCC5C
0x1800bcb1e  lea     rdx, [rbp+var_38]
0x1800bcb22  mov     ecx, r13d; FileHandle
0x1800bcb25  call    __la_fstat
0x1800bcb2a  test    eax, eax
0x1800bcb2c  jnz     short loc_1800BCB4C
0x1800bcb2e  movzx   eax, word ptr [rbp+var_38+6]
0x1800bcb32  mov     ecx, 0F000h
0x1800bcb37  and     ax, cx
0x1800bcb3a  mov     ecx, 8000h
0x1800bcb3f  cmp     ax, cx
0x1800bcb42  jnz     short loc_1800BCB4C
0x1800bcb44  xor     esi, esi
0x1800bcb46  lea     r12d, [rsi+1]
0x1800bcb4a  jmp     short loc_1800BCB6B
0x1800bcb4c  xor     r12d, r12d
0x1800bcb4f  mov     edx, 4000h; Size
0x1800bcb54  lea     ecx, [r12+1]; Count
0x1800bcb59  call    cs:__imp_calloc
0x1800bcb5f  mov     rsi, rax
0x1800bcb62  test    rax, rax
0x1800bcb65  jz      loc_1800BCC4B
0x1800bcb6b  xor     edi, edi
0x1800bcb6d  lea     r9, [rbp+arg_18]
0x1800bcb71  mov     rcx, r14
0x1800bcb74  lea     r8, [rbp+arg_10]
0x1800bcb78  lea     rdx, [rbp+var_40]
0x1800bcb7c  call    archive_read_data_block
0x1800bcb81  mov     ebx, eax
0x1800bcb83  test    eax, eax
0x1800bcb85  jnz     loc_1800BCC1B
0x1800bcb8b  mov     rax, [rbp+arg_18]
0x1800bcb8f  mov     r15, [rbp+var_40]
0x1800bcb93  cmp     rax, rdi
0x1800bcb96  jle     short loc_1800BCBBF
0x1800bcb98  mov     [rsp+80h+var_50], rdi
0x1800bcb9d  mov     r8d, r12d
0x1800bcba0  mov     [rsp+80h+var_58], rax
0x1800bcba5  mov     edx, r13d
0x1800bcba8  mov     rcx, r14
0x1800bcbab  mov     [rsp+80h+var_60], rsi
0x1800bcbb0  call    pad_to
0x1800bcbb5  mov     ebx, eax
0x1800bcbb7  test    eax, eax
0x1800bcbb9  jnz     short loc_1800BCC1B
0x1800bcbbb  mov     rdi, [rbp+arg_18]
0x1800bcbbf  mov     rax, [rbp+arg_10]
0x1800bcbc3  test    rax, rax
0x1800bcbc6  jz      short loc_1800BCB6D
0x1800bcbc8  mov     ecx, 100000h
0x1800bcbcd  mov     rdx, r15
0x1800bcbd0  cmp     rax, rcx
0x1800bcbd3  cmova   rax, rcx
0x1800bcbd7  mov     ecx, r13d
0x1800bcbda  mov     r8, rax
0x1800bcbdd  call    __la_write
0x1800bcbe2  mov     rcx, rax
0x1800bcbe5  test    rax, rax
0x1800bcbe8  js      short loc_1800BCBFD
0x1800bcbea  add     rdi, rax
0x1800bcbed  add     r15, rax
0x1800bcbf0  mov     rax, [rbp+arg_10]
0x1800bcbf4  sub     rax, rcx
0x1800bcbf7  mov     [rbp+arg_10], rax
0x1800bcbfb  jmp     short loc_1800BCBC3
0x1800bcbfd  call    cs:__imp__o__errno
0x1800bcc03  lea     r8, aWriteError; "Write error"
0x1800bcc0a  mov     rcx, r14
0x1800bcc0d  mov     edx, [rax]
0x1800bcc0f  call    archive_set_error
0x1800bcc14  mov     ebx, 0FFFFFFE2h
0x1800bcc19  jmp     short loc_1800BCC4B
0x1800bcc1b  cmp     ebx, 1
0x1800bcc1e  jnz     short loc_1800BCC4B
0x1800bcc20  mov     rax, [rbp+arg_18]
0x1800bcc24  cmp     rax, rdi
0x1800bcc27  jle     short loc_1800BCC4B
0x1800bcc29  mov     [rsp+80h+var_50], rdi
0x1800bcc2e  mov     r8d, r12d
0x1800bcc31  mov     [rsp+80h+var_58], rax
0x1800bcc36  mov     edx, r13d
0x1800bcc39  mov     rcx, r14
0x1800bcc3c  mov     [rsp+80h+var_60], rsi
0x1800bcc41  call    pad_to
0x1800bcc46  test    eax, eax
0x1800bcc48  cmovnz  ebx, eax
0x1800bcc4b  mov     rcx, rsi; Block
0x1800bcc4e  call    cs:__imp_free
0x1800bcc54  xor     eax, eax
0x1800bcc56  cmp     ebx, 1
0x1800bcc59  cmovnz  eax, ebx
0x1800bcc5c  mov     rbx, [rsp+80h+arg_0]
0x1800bcc64  add     rsp, 80h
0x1800bcc6b  pop     r15
0x1800bcc6d  pop     r14
0x1800bcc6f  pop     r13
0x1800bcc71  pop     r12
0x1800bcc73  pop     rdi
0x1800bcc74  pop     rsi
0x1800bcc75  pop     rbp
0x1800bcc76  retn
```
