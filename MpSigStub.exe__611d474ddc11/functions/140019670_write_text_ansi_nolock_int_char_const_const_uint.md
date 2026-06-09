# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x140019670`
- end: `0x140019777`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, int, char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140019bc8`

## callees

- `0x140019670`
- `0x14001bf00`
- `0x14001c870`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019744`
- `KERNEL32!GetLastError` at `0x140019744`
- `KERNEL32!WriteFile` at `0x140019728`
- `KERNEL32!WriteFile` at `0x140019728`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  v7 = *(void **)(qword_1400D69C0[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x140019670  mov     [rsp+arg_0], rbx
0x140019675  mov     [rsp+arg_10], rbp
0x14001967a  push    rsi
0x14001967b  push    rdi
0x14001967c  push    r14
0x14001967e  mov     eax, 1450h
0x140019683  call    __alloca_probe
0x140019688  sub     rsp, rax
0x14001968b  mov     rax, cs:__security_cookie
0x140019692  xor     rax, rsp
0x140019695  mov     [rsp+1468h+var_28], rax
0x14001969d  movsxd  r10, edx
0x1400196a0  mov     rdi, rcx
0x1400196a3  mov     rax, r10
0x1400196a6  mov     ebp, r9d
0x1400196a9  sar     rax, 6
0x1400196ad  lea     rcx, qword_1400D69C0
0x1400196b4  and     r10d, 3Fh
0x1400196b8  add     rbp, r8
0x1400196bb  mov     rsi, r8
0x1400196be  mov     rax, [rcx+rax*8]
0x1400196c2  lea     rdx, [r10+r10*8]
0x1400196c6  mov     r14, [rax+rdx*8+28h]
0x1400196cb  xor     eax, eax
0x1400196cd  mov     [rdi], rax
0x1400196d0  mov     [rdi+8], eax
0x1400196d3  cmp     r8, rbp
0x1400196d6  jnb     short loc_14001974C
0x1400196d8  lea     rbx, [rsp+1468h+Buffer]
0x1400196dd  cmp     rsi, rbp
0x1400196e0  jnb     short loc_140019706
0x1400196e2  mov     al, [rsi]
0x1400196e4  inc     rsi
0x1400196e7  cmp     al, 0Ah
0x1400196e9  jnz     short loc_1400196F4
0x1400196eb  inc     dword ptr [rdi+8]
0x1400196ee  mov     byte ptr [rbx], 0Dh
0x1400196f1  inc     rbx
0x1400196f4  mov     [rbx], al
0x1400196f6  inc     rbx
0x1400196f9  lea     rax, [rsp+1468h+var_29]
0x140019701  cmp     rbx, rax
0x140019704  jb      short loc_1400196DD
0x140019706  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14001970b  lea     rax, [rsp+1468h+Buffer]
0x140019710  and     [rsp+1468h+var_1448], 0
0x140019716  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001971b  sub     ebx, eax
0x14001971d  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x140019722  mov     r8d, ebx; nNumberOfBytesToWrite
0x140019725  mov     rcx, r14; hFile
0x140019728  call    cs:WriteFile
0x14001972e  test    eax, eax
0x140019730  jz      short loc_140019744
0x140019732  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x140019736  add     [rdi+4], eax
0x140019739  cmp     eax, ebx
0x14001973b  jb      short loc_14001974C
0x14001973d  cmp     rsi, rbp
0x140019740  jb      short loc_1400196D8
0x140019742  jmp     short loc_14001974C
0x140019744  call    cs:GetLastError
0x14001974a  mov     [rdi], eax
0x14001974c  mov     rax, rdi
0x14001974f  mov     rcx, [rsp+1468h+var_28]
0x140019757  xor     rcx, rsp; StackCookie
0x14001975a  call    __security_check_cookie
0x14001975f  lea     r11, [rsp+1468h+var_18]
0x140019767  mov     rbx, [r11+20h]
0x14001976b  mov     rbp, [r11+30h]
0x14001976f  mov     rsp, r11
0x140019772  pop     r14
0x140019774  pop     rdi
0x140019775  pop     rsi
0x140019776  retn
```
