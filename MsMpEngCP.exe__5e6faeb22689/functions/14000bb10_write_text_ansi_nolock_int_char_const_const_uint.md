# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x14000bb10`
- end: `0x14000bc17`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000bfc8`

## callees

- `0x140001350`
- `0x14000bb10`
- `0x14000ce70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000bbe4`
- `KERNEL32!GetLastError` at `0x14000bbe4`
- `KERNEL32!WriteFile` at `0x14000bbc8`
- `KERNEL32!WriteFile` at `0x14000bbc8`

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
  v7 = *(void **)(qword_14001A750[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x14000bb10  mov     [rsp+arg_0], rbx
0x14000bb15  mov     [rsp+arg_10], rbp
0x14000bb1a  push    rsi
0x14000bb1b  push    rdi
0x14000bb1c  push    r14
0x14000bb1e  mov     eax, 1450h
0x14000bb23  call    __alloca_probe
0x14000bb28  sub     rsp, rax
0x14000bb2b  mov     rax, cs:__security_cookie
0x14000bb32  xor     rax, rsp
0x14000bb35  mov     [rsp+1468h+var_28], rax
0x14000bb3d  movsxd  r10, edx
0x14000bb40  mov     rdi, rcx
0x14000bb43  mov     rax, r10
0x14000bb46  mov     ebp, r9d
0x14000bb49  sar     rax, 6
0x14000bb4d  lea     rcx, qword_14001A750
0x14000bb54  and     r10d, 3Fh
0x14000bb58  add     rbp, r8
0x14000bb5b  mov     rsi, r8
0x14000bb5e  mov     rax, [rcx+rax*8]
0x14000bb62  lea     rdx, [r10+r10*8]
0x14000bb66  mov     r14, [rax+rdx*8+28h]
0x14000bb6b  xor     eax, eax
0x14000bb6d  mov     [rdi], rax
0x14000bb70  mov     [rdi+8], eax
0x14000bb73  cmp     r8, rbp
0x14000bb76  jnb     short loc_14000BBEC
0x14000bb78  lea     rbx, [rsp+1468h+Buffer]
0x14000bb7d  cmp     rsi, rbp
0x14000bb80  jnb     short loc_14000BBA6
0x14000bb82  mov     al, [rsi]
0x14000bb84  inc     rsi
0x14000bb87  cmp     al, 0Ah
0x14000bb89  jnz     short loc_14000BB94
0x14000bb8b  inc     dword ptr [rdi+8]
0x14000bb8e  mov     byte ptr [rbx], 0Dh
0x14000bb91  inc     rbx
0x14000bb94  mov     [rbx], al
0x14000bb96  inc     rbx
0x14000bb99  lea     rax, [rsp+1468h+var_29]
0x14000bba1  cmp     rbx, rax
0x14000bba4  jb      short loc_14000BB7D
0x14000bba6  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14000bbab  lea     rax, [rsp+1468h+Buffer]
0x14000bbb0  and     [rsp+1468h+var_1448], 0
0x14000bbb6  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000bbbb  sub     ebx, eax
0x14000bbbd  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14000bbc2  mov     r8d, ebx; nNumberOfBytesToWrite
0x14000bbc5  mov     rcx, r14; hFile
0x14000bbc8  call    cs:WriteFile
0x14000bbce  test    eax, eax
0x14000bbd0  jz      short loc_14000BBE4
0x14000bbd2  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14000bbd6  add     [rdi+4], eax
0x14000bbd9  cmp     eax, ebx
0x14000bbdb  jb      short loc_14000BBEC
0x14000bbdd  cmp     rsi, rbp
0x14000bbe0  jb      short loc_14000BB78
0x14000bbe2  jmp     short loc_14000BBEC
0x14000bbe4  call    cs:GetLastError
0x14000bbea  mov     [rdi], eax
0x14000bbec  mov     rax, rdi
0x14000bbef  mov     rcx, [rsp+1468h+var_28]
0x14000bbf7  xor     rcx, rsp; StackCookie
0x14000bbfa  call    __security_check_cookie
0x14000bbff  lea     r11, [rsp+1468h+var_18]
0x14000bc07  mov     rbx, [r11+20h]
0x14000bc0b  mov     rbp, [r11+30h]
0x14000bc0f  mov     rsp, r11
0x14000bc12  pop     r14
0x14000bc14  pop     rdi
0x14000bc15  pop     rsi
0x14000bc16  retn
```
