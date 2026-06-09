# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x14007683c`
- end: `0x140076943`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, int, char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140076cf4`

## callees

- `0x140051b40`
- `0x140051ba0`
- `0x14007683c`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1400768f4`
- `KERNEL32!WriteFile` at `0x1400768f4`
- `KERNEL32!GetLastError` at `0x140076910`
- `KERNEL32!GetLastError` at `0x140076910`

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
  v7 = *(void **)(qword_1400C4950[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x14007683c  mov     [rsp+arg_0], rbx
0x140076841  mov     [rsp+arg_10], rbp
0x140076846  push    rsi
0x140076847  push    rdi
0x140076848  push    r14
0x14007684a  mov     eax, 1450h
0x14007684f  call    __alloca_probe
0x140076854  sub     rsp, rax
0x140076857  mov     rax, cs:__security_cookie
0x14007685e  xor     rax, rsp
0x140076861  mov     [rsp+1468h+var_28], rax
0x140076869  movsxd  r10, edx
0x14007686c  mov     rdi, rcx
0x14007686f  mov     rax, r10
0x140076872  mov     ebp, r9d
0x140076875  sar     rax, 6
0x140076879  lea     rcx, qword_1400C4950
0x140076880  and     r10d, 3Fh
0x140076884  add     rbp, r8
0x140076887  mov     rsi, r8
0x14007688a  mov     rax, [rcx+rax*8]
0x14007688e  lea     rdx, [r10+r10*8]
0x140076892  mov     r14, [rax+rdx*8+28h]
0x140076897  xor     eax, eax
0x140076899  mov     [rdi], rax
0x14007689c  mov     [rdi+8], eax
0x14007689f  cmp     r8, rbp
0x1400768a2  jnb     short loc_140076918
0x1400768a4  lea     rbx, [rsp+1468h+Buffer]
0x1400768a9  cmp     rsi, rbp
0x1400768ac  jnb     short loc_1400768D2
0x1400768ae  mov     al, [rsi]
0x1400768b0  inc     rsi
0x1400768b3  cmp     al, 0Ah
0x1400768b5  jnz     short loc_1400768C0
0x1400768b7  inc     dword ptr [rdi+8]
0x1400768ba  mov     byte ptr [rbx], 0Dh
0x1400768bd  inc     rbx
0x1400768c0  mov     [rbx], al
0x1400768c2  inc     rbx
0x1400768c5  lea     rax, [rsp+1468h+var_29]
0x1400768cd  cmp     rbx, rax
0x1400768d0  jb      short loc_1400768A9
0x1400768d2  and     [rsp+1468h+NumberOfBytesWritten], 0
0x1400768d7  lea     rax, [rsp+1468h+Buffer]
0x1400768dc  and     [rsp+1468h+var_1448], 0
0x1400768e2  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400768e7  sub     ebx, eax
0x1400768e9  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1400768ee  mov     r8d, ebx; nNumberOfBytesToWrite
0x1400768f1  mov     rcx, r14; hFile
0x1400768f4  call    cs:WriteFile
0x1400768fa  test    eax, eax
0x1400768fc  jz      short loc_140076910
0x1400768fe  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x140076902  add     [rdi+4], eax
0x140076905  cmp     eax, ebx
0x140076907  jb      short loc_140076918
0x140076909  cmp     rsi, rbp
0x14007690c  jb      short loc_1400768A4
0x14007690e  jmp     short loc_140076918
0x140076910  call    cs:GetLastError
0x140076916  mov     [rdi], eax
0x140076918  mov     rax, rdi
0x14007691b  mov     rcx, [rsp+1468h+var_28]
0x140076923  xor     rcx, rsp; StackCookie
0x140076926  call    __security_check_cookie
0x14007692b  lea     r11, [rsp+1468h+var_18]
0x140076933  mov     rbx, [r11+20h]
0x140076937  mov     rbp, [r11+30h]
0x14007693b  mov     rsp, r11
0x14007693e  pop     r14
0x140076940  pop     rdi
0x140076941  pop     rsi
0x140076942  retn
```
