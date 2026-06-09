# write_text_ansi_nolock

- ea: `0x180015084`
- end: `0x18001518b`
- name: `write_text_ansi_nolock`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015610`

## callees

- `0x180015084`
- `0x180032370`
- `0x180032760`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18001513c`
- `KERNEL32!WriteFile` at `0x18001513c`
- `KERNEL32!GetLastError` at `0x180015158`
- `KERNEL32!GetLastError` at `0x180015158`

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
0x180015084  mov     [rsp+arg_0], rbx
0x180015089  mov     [rsp+arg_10], rbp
0x18001508e  push    rsi
0x18001508f  push    rdi
0x180015090  push    r14
0x180015092  mov     eax, 1450h
0x180015097  call    _alloca_probe
0x18001509c  sub     rsp, rax
0x18001509f  mov     rax, cs:__security_cookie
0x1800150a6  xor     rax, rsp
0x1800150a9  mov     [rsp+1468h+var_28], rax
0x1800150b1  movsxd  r10, edx
0x1800150b4  mov     rdi, rcx
0x1800150b7  mov     rax, r10
0x1800150ba  mov     ebp, r9d
0x1800150bd  sar     rax, 6
0x1800150c1  lea     rcx, __pioinfo
0x1800150c8  and     r10d, 3Fh
0x1800150cc  add     rbp, r8
0x1800150cf  mov     rsi, r8
0x1800150d2  mov     rax, [rcx+rax*8]
0x1800150d6  lea     rdx, [r10+r10*8]
0x1800150da  mov     r14, [rax+rdx*8+28h]
0x1800150df  xor     eax, eax
0x1800150e1  mov     [rdi], rax
0x1800150e4  mov     [rdi+8], eax
0x1800150e7  cmp     r8, rbp
0x1800150ea  jnb     short loc_180015160
0x1800150ec  lea     rbx, [rsp+1468h+Buffer]
0x1800150f1  cmp     rsi, rbp
0x1800150f4  jnb     short loc_18001511A
0x1800150f6  mov     al, [rsi]
0x1800150f8  inc     rsi
0x1800150fb  cmp     al, 0Ah
0x1800150fd  jnz     short loc_180015108
0x1800150ff  inc     dword ptr [rdi+8]
0x180015102  mov     byte ptr [rbx], 0Dh
0x180015105  inc     rbx
0x180015108  mov     [rbx], al
0x18001510a  inc     rbx
0x18001510d  lea     rax, [rsp+1468h+var_29]
0x180015115  cmp     rbx, rax
0x180015118  jb      short loc_1800150F1
0x18001511a  and     [rsp+1468h+NumberOfBytesWritten], 0
0x18001511f  lea     rax, [rsp+1468h+Buffer]
0x180015124  and     [rsp+1468h+var_1448], 0
0x18001512a  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001512f  sub     ebx, eax
0x180015131  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x180015136  mov     r8d, ebx; nNumberOfBytesToWrite
0x180015139  mov     rcx, r14; hFile
0x18001513c  call    cs:__imp_WriteFile
0x180015142  test    eax, eax
0x180015144  jz      short loc_180015158
0x180015146  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18001514a  add     [rdi+4], eax
0x18001514d  cmp     eax, ebx
0x18001514f  jb      short loc_180015160
0x180015151  cmp     rsi, rbp
0x180015154  jb      short loc_1800150EC
0x180015156  jmp     short loc_180015160
0x180015158  call    cs:__imp_GetLastError
0x18001515e  mov     [rdi], eax
0x180015160  mov     rax, rdi
0x180015163  mov     rcx, [rsp+1468h+var_28]
0x18001516b  xor     rcx, rsp; StackCookie
0x18001516e  call    __security_check_cookie
0x180015173  lea     r11, [rsp+1468h+var_18]
0x18001517b  mov     rbx, [r11+20h]
0x18001517f  mov     rbp, [r11+30h]
0x180015183  mov     rsp, r11
0x180015186  pop     r14
0x180015188  pop     rdi
0x180015189  pop     rsi
0x18001518a  retn
```
