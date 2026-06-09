# write_text_ansi_nolock

- ea: `0x14001a6a0`
- end: `0x14001a7a7`
- name: `write_text_ansi_nolock`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001ab58`

## callees

- `0x140005c20`
- `0x14001a6a0`
- `0x14001cfd0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14001a758`
- `KERNEL32!WriteFile` at `0x14001a758`
- `KERNEL32!GetLastError` at `0x14001a774`
- `KERNEL32!GetLastError` at `0x14001a774`

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
0x14001a6a0  mov     [rsp+arg_0], rbx
0x14001a6a5  mov     [rsp+arg_10], rbp
0x14001a6aa  push    rsi
0x14001a6ab  push    rdi
0x14001a6ac  push    r14
0x14001a6ae  mov     eax, 1450h
0x14001a6b3  call    _alloca_probe
0x14001a6b8  sub     rsp, rax
0x14001a6bb  mov     rax, cs:__security_cookie
0x14001a6c2  xor     rax, rsp
0x14001a6c5  mov     [rsp+1468h+var_28], rax
0x14001a6cd  movsxd  r10, edx
0x14001a6d0  mov     rdi, rcx
0x14001a6d3  mov     rax, r10
0x14001a6d6  mov     ebp, r9d
0x14001a6d9  sar     rax, 6
0x14001a6dd  lea     rcx, __pioinfo
0x14001a6e4  and     r10d, 3Fh
0x14001a6e8  add     rbp, r8
0x14001a6eb  mov     rsi, r8
0x14001a6ee  mov     rax, [rcx+rax*8]
0x14001a6f2  lea     rdx, [r10+r10*8]
0x14001a6f6  mov     r14, [rax+rdx*8+28h]
0x14001a6fb  xor     eax, eax
0x14001a6fd  mov     [rdi], rax
0x14001a700  mov     [rdi+8], eax
0x14001a703  cmp     r8, rbp
0x14001a706  jnb     short loc_14001A77C
0x14001a708  lea     rbx, [rsp+1468h+Buffer]
0x14001a70d  cmp     rsi, rbp
0x14001a710  jnb     short loc_14001A736
0x14001a712  mov     al, [rsi]
0x14001a714  inc     rsi
0x14001a717  cmp     al, 0Ah
0x14001a719  jnz     short loc_14001A724
0x14001a71b  inc     dword ptr [rdi+8]
0x14001a71e  mov     byte ptr [rbx], 0Dh
0x14001a721  inc     rbx
0x14001a724  mov     [rbx], al
0x14001a726  inc     rbx
0x14001a729  lea     rax, [rsp+1468h+var_29]
0x14001a731  cmp     rbx, rax
0x14001a734  jb      short loc_14001A70D
0x14001a736  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14001a73b  lea     rax, [rsp+1468h+Buffer]
0x14001a740  and     [rsp+1468h+var_1448], 0
0x14001a746  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001a74b  sub     ebx, eax
0x14001a74d  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14001a752  mov     r8d, ebx; nNumberOfBytesToWrite
0x14001a755  mov     rcx, r14; hFile
0x14001a758  call    cs:__imp_WriteFile
0x14001a75e  test    eax, eax
0x14001a760  jz      short loc_14001A774
0x14001a762  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14001a766  add     [rdi+4], eax
0x14001a769  cmp     eax, ebx
0x14001a76b  jb      short loc_14001A77C
0x14001a76d  cmp     rsi, rbp
0x14001a770  jb      short loc_14001A708
0x14001a772  jmp     short loc_14001A77C
0x14001a774  call    cs:__imp_GetLastError
0x14001a77a  mov     [rdi], eax
0x14001a77c  mov     rax, rdi
0x14001a77f  mov     rcx, [rsp+1468h+var_28]
0x14001a787  xor     rcx, rsp; StackCookie
0x14001a78a  call    __security_check_cookie
0x14001a78f  lea     r11, [rsp+1468h+var_18]
0x14001a797  mov     rbx, [r11+20h]
0x14001a79b  mov     rbp, [r11+30h]
0x14001a79f  mov     rsp, r11
0x14001a7a2  pop     r14
0x14001a7a4  pop     rdi
0x14001a7a5  pop     rsi
0x14001a7a6  retn
```
