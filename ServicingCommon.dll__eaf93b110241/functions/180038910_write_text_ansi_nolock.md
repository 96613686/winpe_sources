# write_text_ansi_nolock

- ea: `0x180038910`
- end: `0x180038a1b`
- name: `write_text_ansi_nolock`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180038df8`

## callees

- `0x1800293a0`
- `0x180029fd0`
- `0x180038910`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800389e8`
- `KERNEL32!GetLastError` at `0x1800389e8`
- `KERNEL32!WriteFile` at `0x1800389cc`
- `KERNEL32!WriteFile` at `0x1800389cc`

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
0x180038910  mov     [rsp+arg_0], rbx
0x180038915  mov     [rsp+arg_10], rbp
0x18003891a  push    rsi
0x18003891b  push    rdi
0x18003891c  push    r14
0x18003891e  mov     eax, 1450h
0x180038923  call    _alloca_probe
0x180038928  sub     rsp, rax
0x18003892b  mov     rax, cs:__security_cookie
0x180038932  xor     rax, rsp
0x180038935  mov     [rsp+1468h+var_28], rax
0x18003893d  mov     eax, edx
0x18003893f  movsxd  r10, edx
0x180038942  and     eax, 3Fh
0x180038945  sar     r10, 6
0x180038949  mov     rdi, rcx
0x18003894c  mov     ebp, r9d
0x18003894f  lea     rcx, __pioinfo
0x180038956  add     rbp, r8
0x180038959  mov     rsi, r8
0x18003895c  lea     rdx, [rax+rax*8]
0x180038960  mov     rax, [rcx+r10*8]
0x180038964  mov     r14, [rax+rdx*8+28h]
0x180038969  xor     eax, eax
0x18003896b  mov     [rdi], rax
0x18003896e  mov     [rdi+8], eax
0x180038971  cmp     r8, rbp
0x180038974  jnb     short loc_1800389F0
0x180038976  lea     rbx, [rsp+1468h+Buffer]
0x18003897b  cmp     rsi, rbp
0x18003897e  jnb     short loc_1800389A4
0x180038980  mov     al, [rsi]
0x180038982  inc     rsi
0x180038985  cmp     al, 0Ah
0x180038987  jnz     short loc_180038992
0x180038989  inc     dword ptr [rdi+8]
0x18003898c  mov     byte ptr [rbx], 0Dh
0x18003898f  inc     rbx
0x180038992  mov     [rbx], al
0x180038994  inc     rbx
0x180038997  lea     rax, [rsp+1468h+var_29]
0x18003899f  cmp     rbx, rax
0x1800389a2  jb      short loc_18003897B
0x1800389a4  lea     rax, [rsp+1468h+Buffer]
0x1800389a9  mov     [rsp+1468h+NumberOfBytesWritten], 0
0x1800389b1  sub     ebx, eax
0x1800389b3  mov     [rsp+1468h+lpOverlapped], 0; lpOverlapped
0x1800389bc  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800389bf  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800389c4  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1800389c9  mov     rcx, r14; hFile
0x1800389cc  call    cs:__imp_WriteFile
0x1800389d2  test    eax, eax
0x1800389d4  jz      short loc_1800389E8
0x1800389d6  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800389da  add     [rdi+4], eax
0x1800389dd  cmp     eax, ebx
0x1800389df  jb      short loc_1800389F0
0x1800389e1  cmp     rsi, rbp
0x1800389e4  jb      short loc_180038976
0x1800389e6  jmp     short loc_1800389F0
0x1800389e8  call    cs:__imp_GetLastError
0x1800389ee  mov     [rdi], eax
0x1800389f0  mov     rax, rdi
0x1800389f3  mov     rcx, [rsp+1468h+var_28]
0x1800389fb  xor     rcx, rsp; StackCookie
0x1800389fe  call    __security_check_cookie
0x180038a03  lea     r11, [rsp+1468h+var_18]
0x180038a0b  mov     rbx, [r11+20h]
0x180038a0f  mov     rbp, [r11+30h]
0x180038a13  mov     rsp, r11
0x180038a16  pop     r14
0x180038a18  pop     rdi
0x180038a19  pop     rsi
0x180038a1a  retn
```
