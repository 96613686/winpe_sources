# write_text_utf16le_nolock

- ea: `0x18001518c`
- end: `0x1800152a7`
- name: `write_text_utf16le_nolock`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015610`

## callees

- `0x18001518c`
- `0x180032370`
- `0x180032760`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180015258`
- `KERNEL32!WriteFile` at `0x180015258`
- `KERNEL32!GetLastError` at `0x180015274`
- `KERNEL32!GetLastError` at `0x180015274`

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
0x18001518c  mov     [rsp+arg_0], rbx
0x180015191  mov     [rsp+arg_10], rbp
0x180015196  push    rsi
0x180015197  push    rdi
0x180015198  push    r14
0x18001519a  mov     eax, 1450h
0x18001519f  call    _alloca_probe
0x1800151a4  sub     rsp, rax
0x1800151a7  mov     rax, cs:__security_cookie
0x1800151ae  xor     rax, rsp
0x1800151b1  mov     [rsp+1468h+var_28], rax
0x1800151b9  movsxd  r10, edx
0x1800151bc  mov     rdi, rcx
0x1800151bf  mov     rax, r10
0x1800151c2  mov     ebp, r9d
0x1800151c5  sar     rax, 6
0x1800151c9  lea     rcx, __pioinfo
0x1800151d0  and     r10d, 3Fh
0x1800151d4  add     rbp, r8
0x1800151d7  mov     rsi, r8
0x1800151da  mov     rax, [rcx+rax*8]
0x1800151de  lea     rdx, [r10+r10*8]
0x1800151e2  mov     r14, [rax+rdx*8+28h]
0x1800151e7  xor     eax, eax
0x1800151e9  mov     [rdi], rax
0x1800151ec  mov     [rdi+8], eax
0x1800151ef  cmp     r8, rbp
0x1800151f2  jnb     loc_18001527C
0x1800151f8  lea     rbx, [rsp+1468h+Buffer]
0x1800151fd  cmp     rsi, rbp
0x180015200  jnb     short loc_180015230
0x180015202  movzx   eax, word ptr [rsi]
0x180015205  add     rsi, 2
0x180015209  cmp     ax, 0Ah
0x18001520d  jnz     short loc_18001521C
0x18001520f  add     dword ptr [rdi+8], 2
0x180015213  mov     word ptr [rbx], 0Dh
0x180015218  add     rbx, 2
0x18001521c  mov     [rbx], ax
0x18001521f  add     rbx, 2
0x180015223  lea     rax, [rsp+1468h+var_2A]
0x18001522b  cmp     rbx, rax
0x18001522e  jb      short loc_1800151FD
0x180015230  and     [rsp+1468h+NumberOfBytesWritten], 0
0x180015235  lea     rax, [rsp+1468h+Buffer]
0x18001523a  and     [rsp+1468h+var_1448], 0
0x180015240  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015245  sub     rbx, rax
0x180015248  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18001524d  sar     rbx, 1
0x180015250  mov     rcx, r14; hFile
0x180015253  add     ebx, ebx
0x180015255  mov     r8d, ebx; nNumberOfBytesToWrite
0x180015258  call    cs:__imp_WriteFile
0x18001525e  test    eax, eax
0x180015260  jz      short loc_180015274
0x180015262  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x180015266  add     [rdi+4], eax
0x180015269  cmp     eax, ebx
0x18001526b  jb      short loc_18001527C
0x18001526d  cmp     rsi, rbp
0x180015270  jb      short loc_1800151F8
0x180015272  jmp     short loc_18001527C
0x180015274  call    cs:__imp_GetLastError
0x18001527a  mov     [rdi], eax
0x18001527c  mov     rax, rdi
0x18001527f  mov     rcx, [rsp+1468h+var_28]
0x180015287  xor     rcx, rsp; StackCookie
0x18001528a  call    __security_check_cookie
0x18001528f  lea     r11, [rsp+1468h+var_18]
0x180015297  mov     rbx, [r11+20h]
0x18001529b  mov     rbp, [r11+30h]
0x18001529f  mov     rsp, r11
0x1800152a2  pop     r14
0x1800152a4  pop     rdi
0x1800152a5  pop     rsi
0x1800152a6  retn
```
