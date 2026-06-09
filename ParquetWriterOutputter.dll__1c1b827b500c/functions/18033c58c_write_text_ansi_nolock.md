# write_text_ansi_nolock

- ea: `0x18033c58c`
- end: `0x18033c691`
- name: `write_text_ansi_nolock`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18033ca10`

## callees

- `0x18030c3f0`
- `0x18030cf60`
- `0x18033c58c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033c65e`
- `KERNEL32!GetLastError` at `0x18033c65e`
- `KERNEL32!WriteFile` at `0x18033c642`
- `KERNEL32!WriteFile` at `0x18033c642`

## pseudocode

```c
DWORD *__fastcall write_text_ansi_nolock(DWORD *a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  __int64 v7; // rax
  void *v8; // r14
  char *v9; // rdi
  char v10; // al
  DWORD v11; // edi
  DWORD v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v16; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
  *a1 = 0;
  v6 = a3;
  a1[1] = 0;
  v7 = _pioinfo[(__int64)a2 >> 6];
  a1[2] = 0;
  v8 = *(void **)(v7 + ((unsigned __int64)(a2 & 0x3F) << 6) + 40);
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v9 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v10 = *v6++;
        if ( v10 == 10 )
        {
          ++a1[2];
          *v9++ = 13;
        }
        *v9++ = v10;
      }
      while ( v9 < &v16 );
      v11 = (_DWORD)v9 - (unsigned int)Buffer;
      if ( !WriteFile(v8, Buffer, v11, &NumberOfBytesWritten, 0) )
        break;
      v12 = NumberOfBytesWritten;
      a1[1] += NumberOfBytesWritten;
      if ( v12 < v11 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x18033c58c  mov     [rsp+arg_0], rbx
0x18033c591  mov     [rsp+arg_10], rbp
0x18033c596  push    rsi
0x18033c597  push    rdi
0x18033c598  push    r14
0x18033c59a  mov     eax, 1450h
0x18033c59f  call    _alloca_probe
0x18033c5a4  sub     rsp, rax
0x18033c5a7  mov     rax, cs:__security_cookie
0x18033c5ae  xor     rax, rsp
0x18033c5b1  mov     [rsp+1468h+var_28], rax
0x18033c5b9  mov     rbx, rcx
0x18033c5bc  movsxd  r10, edx
0x18033c5bf  mov     rax, r10
0x18033c5c2  mov     ebp, r9d
0x18033c5c5  sar     rax, 6
0x18033c5c9  lea     rcx, __pioinfo
0x18033c5d0  and     r10d, 3Fh
0x18033c5d4  add     rbp, r8
0x18033c5d7  and     dword ptr [rbx], 0
0x18033c5da  mov     rsi, r8
0x18033c5dd  and     dword ptr [rbx+4], 0
0x18033c5e1  mov     rax, [rcx+rax*8]
0x18033c5e5  and     dword ptr [rbx+8], 0
0x18033c5e9  shl     r10, 6
0x18033c5ed  mov     r14, [rax+r10+28h]
0x18033c5f2  cmp     r8, rbp
0x18033c5f5  jnb     short loc_18033C666
0x18033c5f7  lea     rdi, [rsp+1468h+Buffer]
0x18033c5fc  cmp     rsi, rbp
0x18033c5ff  jnb     short loc_18033C625
0x18033c601  mov     al, [rsi]
0x18033c603  inc     rsi
0x18033c606  cmp     al, 0Ah
0x18033c608  jnz     short loc_18033C613
0x18033c60a  inc     dword ptr [rbx+8]
0x18033c60d  mov     byte ptr [rdi], 0Dh
0x18033c610  inc     rdi
0x18033c613  mov     [rdi], al
0x18033c615  inc     rdi
0x18033c618  lea     rax, [rsp+1468h+var_29]
0x18033c620  cmp     rdi, rax
0x18033c623  jb      short loc_18033C5FC
0x18033c625  and     [rsp+1468h+var_1448], 0
0x18033c62b  lea     rax, [rsp+1468h+Buffer]
0x18033c630  sub     edi, eax
0x18033c632  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18033c637  mov     r8d, edi; nNumberOfBytesToWrite
0x18033c63a  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18033c63f  mov     rcx, r14; hFile
0x18033c642  call    cs:__imp_WriteFile
0x18033c648  test    eax, eax
0x18033c64a  jz      short loc_18033C65E
0x18033c64c  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18033c650  add     [rbx+4], eax
0x18033c653  cmp     eax, edi
0x18033c655  jb      short loc_18033C666
0x18033c657  cmp     rsi, rbp
0x18033c65a  jb      short loc_18033C5F7
0x18033c65c  jmp     short loc_18033C666
0x18033c65e  call    cs:__imp_GetLastError
0x18033c664  mov     [rbx], eax
0x18033c666  mov     rax, rbx
0x18033c669  mov     rcx, [rsp+1468h+var_28]
0x18033c671  xor     rcx, rsp; StackCookie
0x18033c674  call    __security_check_cookie
0x18033c679  lea     r11, [rsp+1468h+var_18]
0x18033c681  mov     rbx, [r11+20h]
0x18033c685  mov     rbp, [r11+30h]
0x18033c689  mov     rsp, r11
0x18033c68c  pop     r14
0x18033c68e  pop     rdi
0x18033c68f  pop     rsi
0x18033c690  retn
```
