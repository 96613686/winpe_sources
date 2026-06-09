# write_text_utf16le_nolock

- ea: `0x1802262c4`
- end: `0x1802263df`
- name: `write_text_utf16le_nolock`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180226674`

## callees

- `0x1801f7110`
- `0x1801f7d30`
- `0x1802262c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802263ac`
- `KERNEL32!GetLastError` at `0x1802263ac`
- `KERNEL32!WriteFile` at `0x180226390`
- `KERNEL32!WriteFile` at `0x180226390`

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
0x1802262c4  mov     [rsp+arg_0], rbx
0x1802262c9  mov     [rsp+arg_10], rbp
0x1802262ce  push    rsi
0x1802262cf  push    rdi
0x1802262d0  push    r14
0x1802262d2  mov     eax, 1450h
0x1802262d7  call    _alloca_probe
0x1802262dc  sub     rsp, rax
0x1802262df  mov     rax, cs:__security_cookie
0x1802262e6  xor     rax, rsp
0x1802262e9  mov     [rsp+1468h+var_28], rax
0x1802262f1  movsxd  r10, edx
0x1802262f4  mov     rdi, rcx
0x1802262f7  mov     rax, r10
0x1802262fa  mov     ebp, r9d
0x1802262fd  sar     rax, 6
0x180226301  lea     rcx, __pioinfo
0x180226308  and     r10d, 3Fh
0x18022630c  add     rbp, r8
0x18022630f  mov     rsi, r8
0x180226312  mov     rax, [rcx+rax*8]
0x180226316  lea     rdx, [r10+r10*8]
0x18022631a  mov     r14, [rax+rdx*8+28h]
0x18022631f  xor     eax, eax
0x180226321  mov     [rdi], rax
0x180226324  mov     [rdi+8], eax
0x180226327  cmp     r8, rbp
0x18022632a  jnb     loc_1802263B4
0x180226330  lea     rbx, [rsp+1468h+Buffer]
0x180226335  cmp     rsi, rbp
0x180226338  jnb     short loc_180226368
0x18022633a  movzx   eax, word ptr [rsi]
0x18022633d  add     rsi, 2
0x180226341  cmp     ax, 0Ah
0x180226345  jnz     short loc_180226354
0x180226347  add     dword ptr [rdi+8], 2
0x18022634b  mov     word ptr [rbx], 0Dh
0x180226350  add     rbx, 2
0x180226354  mov     [rbx], ax
0x180226357  add     rbx, 2
0x18022635b  lea     rax, [rsp+1468h+var_2A]
0x180226363  cmp     rbx, rax
0x180226366  jb      short loc_180226335
0x180226368  and     [rsp+1468h+NumberOfBytesWritten], 0
0x18022636d  lea     rax, [rsp+1468h+Buffer]
0x180226372  and     [rsp+1468h+var_1448], 0
0x180226378  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18022637d  sub     rbx, rax
0x180226380  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x180226385  sar     rbx, 1
0x180226388  mov     rcx, r14; hFile
0x18022638b  add     ebx, ebx
0x18022638d  mov     r8d, ebx; nNumberOfBytesToWrite
0x180226390  call    cs:__imp_WriteFile
0x180226396  test    eax, eax
0x180226398  jz      short loc_1802263AC
0x18022639a  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18022639e  add     [rdi+4], eax
0x1802263a1  cmp     eax, ebx
0x1802263a3  jb      short loc_1802263B4
0x1802263a5  cmp     rsi, rbp
0x1802263a8  jb      short loc_180226330
0x1802263aa  jmp     short loc_1802263B4
0x1802263ac  call    cs:__imp_GetLastError
0x1802263b2  mov     [rdi], eax
0x1802263b4  mov     rax, rdi
0x1802263b7  mov     rcx, [rsp+1468h+var_28]
0x1802263bf  xor     rcx, rsp; StackCookie
0x1802263c2  call    __security_check_cookie
0x1802263c7  lea     r11, [rsp+1468h+var_18]
0x1802263cf  mov     rbx, [r11+20h]
0x1802263d3  mov     rbp, [r11+30h]
0x1802263d7  mov     rsp, r11
0x1802263da  pop     r14
0x1802263dc  pop     rdi
0x1802263dd  pop     rsi
0x1802263de  retn
```
