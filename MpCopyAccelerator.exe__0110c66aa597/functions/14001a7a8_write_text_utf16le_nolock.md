# write_text_utf16le_nolock

- ea: `0x14001a7a8`
- end: `0x14001a8c3`
- name: `write_text_utf16le_nolock`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001ab58`

## callees

- `0x140005c20`
- `0x14001a7a8`
- `0x14001cfd0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14001a874`
- `KERNEL32!WriteFile` at `0x14001a874`
- `KERNEL32!GetLastError` at `0x14001a890`
- `KERNEL32!GetLastError` at `0x14001a890`

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
0x14001a7a8  mov     [rsp+arg_0], rbx
0x14001a7ad  mov     [rsp+arg_10], rbp
0x14001a7b2  push    rsi
0x14001a7b3  push    rdi
0x14001a7b4  push    r14
0x14001a7b6  mov     eax, 1450h
0x14001a7bb  call    _alloca_probe
0x14001a7c0  sub     rsp, rax
0x14001a7c3  mov     rax, cs:__security_cookie
0x14001a7ca  xor     rax, rsp
0x14001a7cd  mov     [rsp+1468h+var_28], rax
0x14001a7d5  movsxd  r10, edx
0x14001a7d8  mov     rdi, rcx
0x14001a7db  mov     rax, r10
0x14001a7de  mov     ebp, r9d
0x14001a7e1  sar     rax, 6
0x14001a7e5  lea     rcx, __pioinfo
0x14001a7ec  and     r10d, 3Fh
0x14001a7f0  add     rbp, r8
0x14001a7f3  mov     rsi, r8
0x14001a7f6  mov     rax, [rcx+rax*8]
0x14001a7fa  lea     rdx, [r10+r10*8]
0x14001a7fe  mov     r14, [rax+rdx*8+28h]
0x14001a803  xor     eax, eax
0x14001a805  mov     [rdi], rax
0x14001a808  mov     [rdi+8], eax
0x14001a80b  cmp     r8, rbp
0x14001a80e  jnb     loc_14001A898
0x14001a814  lea     rbx, [rsp+1468h+Buffer]
0x14001a819  cmp     rsi, rbp
0x14001a81c  jnb     short loc_14001A84C
0x14001a81e  movzx   eax, word ptr [rsi]
0x14001a821  add     rsi, 2
0x14001a825  cmp     ax, 0Ah
0x14001a829  jnz     short loc_14001A838
0x14001a82b  add     dword ptr [rdi+8], 2
0x14001a82f  mov     word ptr [rbx], 0Dh
0x14001a834  add     rbx, 2
0x14001a838  mov     [rbx], ax
0x14001a83b  add     rbx, 2
0x14001a83f  lea     rax, [rsp+1468h+var_2A]
0x14001a847  cmp     rbx, rax
0x14001a84a  jb      short loc_14001A819
0x14001a84c  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14001a851  lea     rax, [rsp+1468h+Buffer]
0x14001a856  and     [rsp+1468h+var_1448], 0
0x14001a85c  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001a861  sub     rbx, rax
0x14001a864  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14001a869  sar     rbx, 1
0x14001a86c  mov     rcx, r14; hFile
0x14001a86f  add     ebx, ebx
0x14001a871  mov     r8d, ebx; nNumberOfBytesToWrite
0x14001a874  call    cs:__imp_WriteFile
0x14001a87a  test    eax, eax
0x14001a87c  jz      short loc_14001A890
0x14001a87e  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14001a882  add     [rdi+4], eax
0x14001a885  cmp     eax, ebx
0x14001a887  jb      short loc_14001A898
0x14001a889  cmp     rsi, rbp
0x14001a88c  jb      short loc_14001A814
0x14001a88e  jmp     short loc_14001A898
0x14001a890  call    cs:__imp_GetLastError
0x14001a896  mov     [rdi], eax
0x14001a898  mov     rax, rdi
0x14001a89b  mov     rcx, [rsp+1468h+var_28]
0x14001a8a3  xor     rcx, rsp; StackCookie
0x14001a8a6  call    __security_check_cookie
0x14001a8ab  lea     r11, [rsp+1468h+var_18]
0x14001a8b3  mov     rbx, [r11+20h]
0x14001a8b7  mov     rbp, [r11+30h]
0x14001a8bb  mov     rsp, r11
0x14001a8be  pop     r14
0x14001a8c0  pop     rdi
0x14001a8c1  pop     rsi
0x14001a8c2  retn
```
