# write_text_utf16le_nolock

- ea: `0x14006f9a8`
- end: `0x14006fac3`
- name: `write_text_utf16le_nolock`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14006fdf0`

## callees

- `0x14003a5c0`
- `0x14003aab0`
- `0x14006f9a8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14006fa74`
- `KERNEL32!WriteFile` at `0x14006fa74`
- `KERNEL32!GetLastError` at `0x14006fa90`
- `KERNEL32!GetLastError` at `0x14006fa90`

## pseudocode

```c
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
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
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      NumberOfBytesWritten = 0;
      v10 = 2 * ((v8 - Buffer) >> 1);
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
0x14006f9a8  mov     [rsp+arg_0], rbx
0x14006f9ad  mov     [rsp+arg_10], rbp
0x14006f9b2  push    rsi
0x14006f9b3  push    rdi
0x14006f9b4  push    r14
0x14006f9b6  mov     eax, 1450h
0x14006f9bb  call    _alloca_probe
0x14006f9c0  sub     rsp, rax
0x14006f9c3  mov     rax, cs:__security_cookie
0x14006f9ca  xor     rax, rsp
0x14006f9cd  mov     [rsp+1468h+var_28], rax
0x14006f9d5  movsxd  r10, edx
0x14006f9d8  mov     rdi, rcx
0x14006f9db  mov     rax, r10
0x14006f9de  mov     ebp, r9d
0x14006f9e1  sar     rax, 6
0x14006f9e5  lea     rcx, __pioinfo
0x14006f9ec  and     r10d, 3Fh
0x14006f9f0  add     rbp, r8
0x14006f9f3  mov     rsi, r8
0x14006f9f6  mov     rax, [rcx+rax*8]
0x14006f9fa  lea     rdx, [r10+r10*8]
0x14006f9fe  mov     r14, [rax+rdx*8+28h]
0x14006fa03  xor     eax, eax
0x14006fa05  mov     [rdi], rax
0x14006fa08  mov     [rdi+8], eax
0x14006fa0b  cmp     r8, rbp
0x14006fa0e  jnb     loc_14006FA98
0x14006fa14  lea     rbx, [rsp+1468h+Buffer]
0x14006fa19  cmp     rsi, rbp
0x14006fa1c  jnb     short loc_14006FA4C
0x14006fa1e  movzx   eax, word ptr [rsi]
0x14006fa21  add     rsi, 2
0x14006fa25  cmp     ax, 0Ah
0x14006fa29  jnz     short loc_14006FA38
0x14006fa2b  add     dword ptr [rdi+8], 2
0x14006fa2f  mov     word ptr [rbx], 0Dh
0x14006fa34  add     rbx, 2
0x14006fa38  mov     [rbx], ax
0x14006fa3b  add     rbx, 2
0x14006fa3f  lea     rax, [rsp+1468h+var_2A]
0x14006fa47  cmp     rbx, rax
0x14006fa4a  jb      short loc_14006FA19
0x14006fa4c  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14006fa51  lea     rax, [rsp+1468h+Buffer]
0x14006fa56  and     [rsp+1468h+var_1448], 0
0x14006fa5c  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14006fa61  sub     rbx, rax
0x14006fa64  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14006fa69  sar     rbx, 1
0x14006fa6c  mov     rcx, r14; hFile
0x14006fa6f  add     ebx, ebx
0x14006fa71  mov     r8d, ebx; nNumberOfBytesToWrite
0x14006fa74  call    cs:__imp_WriteFile
0x14006fa7a  test    eax, eax
0x14006fa7c  jz      short loc_14006FA90
0x14006fa7e  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14006fa82  add     [rdi+4], eax
0x14006fa85  cmp     eax, ebx
0x14006fa87  jb      short loc_14006FA98
0x14006fa89  cmp     rsi, rbp
0x14006fa8c  jb      short loc_14006FA14
0x14006fa8e  jmp     short loc_14006FA98
0x14006fa90  call    cs:__imp_GetLastError
0x14006fa96  mov     [rdi], eax
0x14006fa98  mov     rax, rdi
0x14006fa9b  mov     rcx, [rsp+1468h+var_28]
0x14006faa3  xor     rcx, rsp; StackCookie
0x14006faa6  call    __security_check_cookie
0x14006faab  lea     r11, [rsp+1468h+var_18]
0x14006fab3  mov     rbx, [r11+20h]
0x14006fab7  mov     rbp, [r11+30h]
0x14006fabb  mov     rsp, r11
0x14006fabe  pop     r14
0x14006fac0  pop     rdi
0x14006fac1  pop     rsi
0x14006fac2  retn
```
