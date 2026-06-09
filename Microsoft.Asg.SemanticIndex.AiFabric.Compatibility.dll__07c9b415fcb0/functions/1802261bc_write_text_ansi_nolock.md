# write_text_ansi_nolock

- ea: `0x1802261bc`
- end: `0x1802262c3`
- name: `write_text_ansi_nolock`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180226674`

## callees

- `0x1801f7110`
- `0x1801f7d30`
- `0x1802261bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180226290`
- `KERNEL32!GetLastError` at `0x180226290`
- `KERNEL32!WriteFile` at `0x180226274`
- `KERNEL32!WriteFile` at `0x180226274`

## pseudocode

```c
__int64 __fastcall write_text_ansi_nolock(__int64 a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  char v9; // al
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v15; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
  v6 = a3;
  v7 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          ++*(_DWORD *)(a1 + 8);
          *v8++ = 13;
        }
        *v8++ = v9;
      }
      while ( v8 < &v15 );
      NumberOfBytesWritten = 0;
      v10 = (_DWORD)v8 - (unsigned int)Buffer;
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x1802261bc  mov     [rsp+arg_0], rbx
0x1802261c1  mov     [rsp+arg_10], rbp
0x1802261c6  push    rsi
0x1802261c7  push    rdi
0x1802261c8  push    r14
0x1802261ca  mov     eax, 1450h
0x1802261cf  call    _alloca_probe
0x1802261d4  sub     rsp, rax
0x1802261d7  mov     rax, cs:__security_cookie
0x1802261de  xor     rax, rsp
0x1802261e1  mov     [rsp+1468h+var_28], rax
0x1802261e9  movsxd  r10, edx
0x1802261ec  mov     rdi, rcx
0x1802261ef  mov     rax, r10
0x1802261f2  mov     ebp, r9d
0x1802261f5  sar     rax, 6
0x1802261f9  lea     rcx, __pioinfo
0x180226200  and     r10d, 3Fh
0x180226204  add     rbp, r8
0x180226207  mov     rsi, r8
0x18022620a  mov     rax, [rcx+rax*8]
0x18022620e  lea     rdx, [r10+r10*8]
0x180226212  mov     r14, [rax+rdx*8+28h]
0x180226217  xor     eax, eax
0x180226219  mov     [rdi], rax
0x18022621c  mov     [rdi+8], eax
0x18022621f  cmp     r8, rbp
0x180226222  jnb     short loc_180226298
0x180226224  lea     rbx, [rsp+1468h+Buffer]
0x180226229  cmp     rsi, rbp
0x18022622c  jnb     short loc_180226252
0x18022622e  mov     al, [rsi]
0x180226230  inc     rsi
0x180226233  cmp     al, 0Ah
0x180226235  jnz     short loc_180226240
0x180226237  inc     dword ptr [rdi+8]
0x18022623a  mov     byte ptr [rbx], 0Dh
0x18022623d  inc     rbx
0x180226240  mov     [rbx], al
0x180226242  inc     rbx
0x180226245  lea     rax, [rsp+1468h+var_29]
0x18022624d  cmp     rbx, rax
0x180226250  jb      short loc_180226229
0x180226252  and     [rsp+1468h+NumberOfBytesWritten], 0
0x180226257  lea     rax, [rsp+1468h+Buffer]
0x18022625c  and     [rsp+1468h+var_1448], 0
0x180226262  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180226267  sub     ebx, eax
0x180226269  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18022626e  mov     r8d, ebx; nNumberOfBytesToWrite
0x180226271  mov     rcx, r14; hFile
0x180226274  call    cs:__imp_WriteFile
0x18022627a  test    eax, eax
0x18022627c  jz      short loc_180226290
0x18022627e  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x180226282  add     [rdi+4], eax
0x180226285  cmp     eax, ebx
0x180226287  jb      short loc_180226298
0x180226289  cmp     rsi, rbp
0x18022628c  jb      short loc_180226224
0x18022628e  jmp     short loc_180226298
0x180226290  call    cs:__imp_GetLastError
0x180226296  mov     [rdi], eax
0x180226298  mov     rax, rdi
0x18022629b  mov     rcx, [rsp+1468h+var_28]
0x1802262a3  xor     rcx, rsp; StackCookie
0x1802262a6  call    __security_check_cookie
0x1802262ab  lea     r11, [rsp+1468h+var_18]
0x1802262b3  mov     rbx, [r11+20h]
0x1802262b7  mov     rbp, [r11+30h]
0x1802262bb  mov     rsp, r11
0x1802262be  pop     r14
0x1802262c0  pop     rdi
0x1802262c1  pop     rsi
0x1802262c2  retn
```
