# write_text_utf16le_nolock

- ea: `0x1800158ec`
- end: `0x180015a07`
- name: `write_text_utf16le_nolock`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015d70`

## callees

- `0x180002810`
- `0x1800158ec`
- `0x180032a50`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800159b8`
- `KERNEL32!WriteFile` at `0x1800159b8`
- `KERNEL32!GetLastError` at `0x1800159d4`
- `KERNEL32!GetLastError` at `0x1800159d4`

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
0x1800158ec  mov     [rsp+arg_0], rbx
0x1800158f1  mov     [rsp+arg_10], rbp
0x1800158f6  push    rsi
0x1800158f7  push    rdi
0x1800158f8  push    r14
0x1800158fa  mov     eax, 1450h
0x1800158ff  call    _alloca_probe
0x180015904  sub     rsp, rax
0x180015907  mov     rax, cs:__security_cookie
0x18001590e  xor     rax, rsp
0x180015911  mov     [rsp+1468h+var_28], rax
0x180015919  movsxd  r10, edx
0x18001591c  mov     rdi, rcx
0x18001591f  mov     rax, r10
0x180015922  mov     ebp, r9d
0x180015925  sar     rax, 6
0x180015929  lea     rcx, __pioinfo
0x180015930  and     r10d, 3Fh
0x180015934  add     rbp, r8
0x180015937  mov     rsi, r8
0x18001593a  mov     rax, [rcx+rax*8]
0x18001593e  lea     rdx, [r10+r10*8]
0x180015942  mov     r14, [rax+rdx*8+28h]
0x180015947  xor     eax, eax
0x180015949  mov     [rdi], rax
0x18001594c  mov     [rdi+8], eax
0x18001594f  cmp     r8, rbp
0x180015952  jnb     loc_1800159DC
0x180015958  lea     rbx, [rsp+1468h+Buffer]
0x18001595d  cmp     rsi, rbp
0x180015960  jnb     short loc_180015990
0x180015962  movzx   eax, word ptr [rsi]
0x180015965  add     rsi, 2
0x180015969  cmp     ax, 0Ah
0x18001596d  jnz     short loc_18001597C
0x18001596f  add     dword ptr [rdi+8], 2
0x180015973  mov     word ptr [rbx], 0Dh
0x180015978  add     rbx, 2
0x18001597c  mov     [rbx], ax
0x18001597f  add     rbx, 2
0x180015983  lea     rax, [rsp+1468h+var_2A]
0x18001598b  cmp     rbx, rax
0x18001598e  jb      short loc_18001595D
0x180015990  and     [rsp+1468h+NumberOfBytesWritten], 0
0x180015995  lea     rax, [rsp+1468h+Buffer]
0x18001599a  and     [rsp+1468h+var_1448], 0
0x1800159a0  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800159a5  sub     rbx, rax
0x1800159a8  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1800159ad  sar     rbx, 1
0x1800159b0  mov     rcx, r14; hFile
0x1800159b3  add     ebx, ebx
0x1800159b5  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800159b8  call    cs:__imp_WriteFile
0x1800159be  test    eax, eax
0x1800159c0  jz      short loc_1800159D4
0x1800159c2  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800159c6  add     [rdi+4], eax
0x1800159c9  cmp     eax, ebx
0x1800159cb  jb      short loc_1800159DC
0x1800159cd  cmp     rsi, rbp
0x1800159d0  jb      short loc_180015958
0x1800159d2  jmp     short loc_1800159DC
0x1800159d4  call    cs:__imp_GetLastError
0x1800159da  mov     [rdi], eax
0x1800159dc  mov     rax, rdi
0x1800159df  mov     rcx, [rsp+1468h+var_28]
0x1800159e7  xor     rcx, rsp; StackCookie
0x1800159ea  call    __security_check_cookie
0x1800159ef  lea     r11, [rsp+1468h+var_18]
0x1800159f7  mov     rbx, [r11+20h]
0x1800159fb  mov     rbp, [r11+30h]
0x1800159ff  mov     rsp, r11
0x180015a02  pop     r14
0x180015a04  pop     rdi
0x180015a05  pop     rsi
0x180015a06  retn
```
