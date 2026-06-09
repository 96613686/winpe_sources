# write_text_utf16le_nolock

- ea: `0x180038a24`
- end: `0x180038b43`
- name: `write_text_utf16le_nolock`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180038df8`

## callees

- `0x1800293a0`
- `0x180029fd0`
- `0x180038a24`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038b10`
- `KERNEL32!GetLastError` at `0x180038b10`
- `KERNEL32!WriteFile` at `0x180038af4`
- `KERNEL32!WriteFile` at `0x180038af4`

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
0x180038a24  mov     [rsp+arg_0], rbx
0x180038a29  mov     [rsp+arg_10], rbp
0x180038a2e  push    rsi
0x180038a2f  push    rdi
0x180038a30  push    r14
0x180038a32  mov     eax, 1450h
0x180038a37  call    _alloca_probe
0x180038a3c  sub     rsp, rax
0x180038a3f  mov     rax, cs:__security_cookie
0x180038a46  xor     rax, rsp
0x180038a49  mov     [rsp+1468h+var_28], rax
0x180038a51  mov     eax, edx
0x180038a53  movsxd  r10, edx
0x180038a56  and     eax, 3Fh
0x180038a59  sar     r10, 6
0x180038a5d  mov     rdi, rcx
0x180038a60  mov     ebp, r9d
0x180038a63  lea     rcx, __pioinfo
0x180038a6a  add     rbp, r8
0x180038a6d  mov     rsi, r8
0x180038a70  lea     rdx, [rax+rax*8]
0x180038a74  mov     rax, [rcx+r10*8]
0x180038a78  mov     r14, [rax+rdx*8+28h]
0x180038a7d  xor     eax, eax
0x180038a7f  mov     [rdi], rax
0x180038a82  mov     [rdi+8], eax
0x180038a85  cmp     r8, rbp
0x180038a88  jnb     loc_180038B18
0x180038a8e  lea     rbx, [rsp+1468h+Buffer]
0x180038a93  cmp     rsi, rbp
0x180038a96  jnb     short loc_180038AC6
0x180038a98  movzx   eax, word ptr [rsi]
0x180038a9b  add     rsi, 2
0x180038a9f  cmp     ax, 0Ah
0x180038aa3  jnz     short loc_180038AB2
0x180038aa5  add     dword ptr [rdi+8], 2
0x180038aa9  mov     word ptr [rbx], 0Dh
0x180038aae  add     rbx, 2
0x180038ab2  mov     [rbx], ax
0x180038ab5  add     rbx, 2
0x180038ab9  lea     rax, [rsp+1468h+var_2A]
0x180038ac1  cmp     rbx, rax
0x180038ac4  jb      short loc_180038A93
0x180038ac6  lea     rax, [rsp+1468h+Buffer]
0x180038acb  mov     [rsp+1468h+NumberOfBytesWritten], 0
0x180038ad3  sub     rbx, rax
0x180038ad6  mov     [rsp+1468h+lpOverlapped], 0; lpOverlapped
0x180038adf  sar     rbx, 1
0x180038ae2  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180038ae7  add     ebx, ebx
0x180038ae9  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x180038aee  mov     r8d, ebx; nNumberOfBytesToWrite
0x180038af1  mov     rcx, r14; hFile
0x180038af4  call    cs:__imp_WriteFile
0x180038afa  test    eax, eax
0x180038afc  jz      short loc_180038B10
0x180038afe  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x180038b02  add     [rdi+4], eax
0x180038b05  cmp     eax, ebx
0x180038b07  jb      short loc_180038B18
0x180038b09  cmp     rsi, rbp
0x180038b0c  jb      short loc_180038A8E
0x180038b0e  jmp     short loc_180038B18
0x180038b10  call    cs:__imp_GetLastError
0x180038b16  mov     [rdi], eax
0x180038b18  mov     rax, rdi
0x180038b1b  mov     rcx, [rsp+1468h+var_28]
0x180038b23  xor     rcx, rsp; StackCookie
0x180038b26  call    __security_check_cookie
0x180038b2b  lea     r11, [rsp+1468h+var_18]
0x180038b33  mov     rbx, [r11+20h]
0x180038b37  mov     rbp, [r11+30h]
0x180038b3b  mov     rsp, r11
0x180038b3e  pop     r14
0x180038b40  pop     rdi
0x180038b41  pop     rsi
0x180038b42  retn
```
