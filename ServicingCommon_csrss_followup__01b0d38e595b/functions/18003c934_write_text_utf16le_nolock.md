# write_text_utf16le_nolock

- ea: `0x18003c934`
- end: `0x18003ca53`
- name: `write_text_utf16le_nolock`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003cd08`

## callees

- `0x18002d2b0`
- `0x18002dee0`
- `0x18003c934`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003ca20`
- `KERNEL32!GetLastError` at `0x18003ca20`
- `KERNEL32!WriteFile` at `0x18003ca04`
- `KERNEL32!WriteFile` at `0x18003ca04`

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
0x18003c934  mov     [rsp+arg_0], rbx
0x18003c939  mov     [rsp+arg_10], rbp
0x18003c93e  push    rsi
0x18003c93f  push    rdi
0x18003c940  push    r14
0x18003c942  mov     eax, 1450h
0x18003c947  call    _alloca_probe
0x18003c94c  sub     rsp, rax
0x18003c94f  mov     rax, cs:__security_cookie
0x18003c956  xor     rax, rsp
0x18003c959  mov     [rsp+1468h+var_28], rax
0x18003c961  mov     eax, edx
0x18003c963  movsxd  r10, edx
0x18003c966  and     eax, 3Fh
0x18003c969  sar     r10, 6
0x18003c96d  mov     rdi, rcx
0x18003c970  mov     ebp, r9d
0x18003c973  lea     rcx, __pioinfo
0x18003c97a  add     rbp, r8
0x18003c97d  mov     rsi, r8
0x18003c980  lea     rdx, [rax+rax*8]
0x18003c984  mov     rax, [rcx+r10*8]
0x18003c988  mov     r14, [rax+rdx*8+28h]
0x18003c98d  xor     eax, eax
0x18003c98f  mov     [rdi], rax
0x18003c992  mov     [rdi+8], eax
0x18003c995  cmp     r8, rbp
0x18003c998  jnb     loc_18003CA28
0x18003c99e  lea     rbx, [rsp+1468h+Buffer]
0x18003c9a3  cmp     rsi, rbp
0x18003c9a6  jnb     short loc_18003C9D6
0x18003c9a8  movzx   eax, word ptr [rsi]
0x18003c9ab  add     rsi, 2
0x18003c9af  cmp     ax, 0Ah
0x18003c9b3  jnz     short loc_18003C9C2
0x18003c9b5  add     dword ptr [rdi+8], 2
0x18003c9b9  mov     word ptr [rbx], 0Dh
0x18003c9be  add     rbx, 2
0x18003c9c2  mov     [rbx], ax
0x18003c9c5  add     rbx, 2
0x18003c9c9  lea     rax, [rsp+1468h+var_2A]
0x18003c9d1  cmp     rbx, rax
0x18003c9d4  jb      short loc_18003C9A3
0x18003c9d6  lea     rax, [rsp+1468h+Buffer]
0x18003c9db  mov     [rsp+1468h+NumberOfBytesWritten], 0
0x18003c9e3  sub     rbx, rax
0x18003c9e6  mov     [rsp+1468h+lpOverlapped], 0; lpOverlapped
0x18003c9ef  sar     rbx, 1
0x18003c9f2  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c9f7  add     ebx, ebx
0x18003c9f9  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18003c9fe  mov     r8d, ebx; nNumberOfBytesToWrite
0x18003ca01  mov     rcx, r14; hFile
0x18003ca04  call    cs:__imp_WriteFile
0x18003ca0a  test    eax, eax
0x18003ca0c  jz      short loc_18003CA20
0x18003ca0e  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18003ca12  add     [rdi+4], eax
0x18003ca15  cmp     eax, ebx
0x18003ca17  jb      short loc_18003CA28
0x18003ca19  cmp     rsi, rbp
0x18003ca1c  jb      short loc_18003C99E
0x18003ca1e  jmp     short loc_18003CA28
0x18003ca20  call    cs:__imp_GetLastError
0x18003ca26  mov     [rdi], eax
0x18003ca28  mov     rax, rdi
0x18003ca2b  mov     rcx, [rsp+1468h+var_28]
0x18003ca33  xor     rcx, rsp; StackCookie
0x18003ca36  call    __security_check_cookie
0x18003ca3b  lea     r11, [rsp+1468h+var_18]
0x18003ca43  mov     rbx, [r11+20h]
0x18003ca47  mov     rbp, [r11+30h]
0x18003ca4b  mov     rsp, r11
0x18003ca4e  pop     r14
0x18003ca50  pop     rdi
0x18003ca51  pop     rsi
0x18003ca52  retn
```
