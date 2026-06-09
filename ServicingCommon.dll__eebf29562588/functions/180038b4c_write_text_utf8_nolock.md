# write_text_utf8_nolock

- ea: `0x180038b4c`
- end: `0x180038cca`
- name: `write_text_utf8_nolock`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180038df8`

## callees

- `0x180028d00`
- `0x1800293a0`
- `0x180029fd0`
- `0x180038b4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038c93`
- `KERNEL32!GetLastError` at `0x180038c93`
- `KERNEL32!WriteFile` at `0x180038c6e`
- `KERNEL32!WriteFile` at `0x180038c6e`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  char *v9; // r9
  __int16 v10; // ax
  unsigned int v11; // ebp
  unsigned int v12; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v15[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v16; // [rsp+6F8h] [rbp-DA0h] BYREF
  _BYTE v17[3424]; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
LABEL_2:
    v9 = v15;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v10 = *v7++;
      if ( v10 == 10 )
      {
        *(_WORD *)v9 = 13;
        v9 += 2;
      }
      *(_WORD *)v9 = v10;
      v9 += 2;
    }
    while ( v9 < &v16 );
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)v17, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, &v17[v12], v11 - v12, &NumberOfBytesWritten, 0) )
          break;
        v12 += NumberOfBytesWritten;
        if ( v12 >= v11 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          if ( (unsigned __int64)v7 < v5 )
            goto LABEL_2;
          return a1;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x180038b4c  mov     [rsp+arg_0], rbx
0x180038b51  mov     [rsp+arg_10], rbp
0x180038b56  push    rsi
0x180038b57  push    rdi
0x180038b58  push    r12
0x180038b5a  push    r14
0x180038b5c  push    r15
0x180038b5e  mov     eax, 1470h
0x180038b63  call    _alloca_probe
0x180038b68  sub     rsp, rax
0x180038b6b  mov     rax, cs:__security_cookie
0x180038b72  xor     rax, rsp
0x180038b75  mov     [rsp+1498h+var_38], rax
0x180038b7d  mov     eax, edx
0x180038b7f  movsxd  r10, edx
0x180038b82  and     eax, 3Fh
0x180038b85  sar     r10, 6
0x180038b89  mov     rbx, rcx
0x180038b8c  mov     r14d, r9d
0x180038b8f  lea     rcx, __pioinfo
0x180038b96  add     r14, r8
0x180038b99  mov     r15, r8
0x180038b9c  mov     rdi, r8
0x180038b9f  lea     rdx, [rax+rax*8]
0x180038ba3  mov     rax, [rcx+r10*8]
0x180038ba7  mov     r12, [rax+rdx*8+28h]
0x180038bac  xor     eax, eax
0x180038bae  mov     [rbx], rax
0x180038bb1  mov     [rbx+8], eax
0x180038bb4  cmp     r8, r14
0x180038bb7  jnb     loc_180038C9B
0x180038bbd  lea     r9, [rsp+1498h+var_1448]
0x180038bc2  cmp     rdi, r14
0x180038bc5  jnb     short loc_180038BF3
0x180038bc7  movzx   eax, word ptr [rdi]
0x180038bca  add     rdi, 2
0x180038bce  cmp     ax, 0Ah
0x180038bd2  jnz     short loc_180038BDE
0x180038bd4  mov     word ptr [r9], 0Dh
0x180038bda  add     r9, 2
0x180038bde  mov     [r9], ax
0x180038be2  add     r9, 2
0x180038be6  lea     rax, [rsp+1498h+var_DA0]
0x180038bee  cmp     r9, rax
0x180038bf1  jb      short loc_180038BC2
0x180038bf3  mov     [rsp+1498h+var_1460], 0
0x180038bfc  lea     rax, [rsp+1498h+var_1448]
0x180038c01  sub     r9, rax
0x180038c04  mov     [rsp+1498h+var_1468], 0
0x180038c0d  lea     rax, [rsp+1498h+var_D98]
0x180038c15  sar     r9, 1
0x180038c18  mov     [rsp+1498h+var_1470], 0D55h
0x180038c20  lea     r8, [rsp+1498h+var_1448]
0x180038c25  xor     edx, edx
0x180038c27  mov     [rsp+1498h+lpOverlapped], rax
0x180038c2c  mov     ecx, 0FDE9h
0x180038c31  call    __acrt_WideCharToMultiByte
0x180038c36  mov     ebp, eax
0x180038c38  test    eax, eax
0x180038c3a  jz      short loc_180038C93
0x180038c3c  xor     esi, esi
0x180038c3e  test    eax, eax
0x180038c40  jz      short loc_180038C80
0x180038c42  mov     ecx, esi
0x180038c44  lea     rdx, [rsp+1498h+var_D98]
0x180038c4c  mov     r8d, ebp
0x180038c4f  mov     [rsp+1498h+NumberOfBytesWritten], 0
0x180038c57  add     rdx, rcx; lpBuffer
0x180038c5a  mov     [rsp+1498h+lpOverlapped], 0; lpOverlapped
0x180038c63  mov     rcx, r12; hFile
0x180038c66  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180038c6b  sub     r8d, esi; nNumberOfBytesToWrite
0x180038c6e  call    cs:__imp_WriteFile
0x180038c74  test    eax, eax
0x180038c76  jz      short loc_180038C93
0x180038c78  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x180038c7c  cmp     esi, ebp
0x180038c7e  jb      short loc_180038C42
0x180038c80  mov     eax, edi
0x180038c82  sub     eax, r15d
0x180038c85  mov     [rbx+4], eax
0x180038c88  cmp     rdi, r14
0x180038c8b  jb      loc_180038BBD
0x180038c91  jmp     short loc_180038C9B
0x180038c93  call    cs:__imp_GetLastError
0x180038c99  mov     [rbx], eax
0x180038c9b  mov     rax, rbx
0x180038c9e  mov     rcx, [rsp+1498h+var_38]
0x180038ca6  xor     rcx, rsp; StackCookie
0x180038ca9  call    __security_check_cookie
0x180038cae  lea     r11, [rsp+1498h+var_28]
0x180038cb6  mov     rbx, [r11+30h]
0x180038cba  mov     rbp, [r11+40h]
0x180038cbe  mov     rsp, r11
0x180038cc1  pop     r15
0x180038cc3  pop     r14
0x180038cc5  pop     r12
0x180038cc7  pop     rdi
0x180038cc8  pop     rsi
0x180038cc9  retn
```
