# write_text_ansi_nolock

- ea: `0x18003c820`
- end: `0x18003c92b`
- name: `write_text_ansi_nolock`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003cd08`

## callees

- `0x18002d2b0`
- `0x18002dee0`
- `0x18003c820`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003c8f8`
- `KERNEL32!GetLastError` at `0x18003c8f8`
- `KERNEL32!WriteFile` at `0x18003c8dc`
- `KERNEL32!WriteFile` at `0x18003c8dc`

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
0x18003c820  mov     [rsp+arg_0], rbx
0x18003c825  mov     [rsp+arg_10], rbp
0x18003c82a  push    rsi
0x18003c82b  push    rdi
0x18003c82c  push    r14
0x18003c82e  mov     eax, 1450h
0x18003c833  call    _alloca_probe
0x18003c838  sub     rsp, rax
0x18003c83b  mov     rax, cs:__security_cookie
0x18003c842  xor     rax, rsp
0x18003c845  mov     [rsp+1468h+var_28], rax
0x18003c84d  mov     eax, edx
0x18003c84f  movsxd  r10, edx
0x18003c852  and     eax, 3Fh
0x18003c855  sar     r10, 6
0x18003c859  mov     rdi, rcx
0x18003c85c  mov     ebp, r9d
0x18003c85f  lea     rcx, __pioinfo
0x18003c866  add     rbp, r8
0x18003c869  mov     rsi, r8
0x18003c86c  lea     rdx, [rax+rax*8]
0x18003c870  mov     rax, [rcx+r10*8]
0x18003c874  mov     r14, [rax+rdx*8+28h]
0x18003c879  xor     eax, eax
0x18003c87b  mov     [rdi], rax
0x18003c87e  mov     [rdi+8], eax
0x18003c881  cmp     r8, rbp
0x18003c884  jnb     short loc_18003C900
0x18003c886  lea     rbx, [rsp+1468h+Buffer]
0x18003c88b  cmp     rsi, rbp
0x18003c88e  jnb     short loc_18003C8B4
0x18003c890  mov     al, [rsi]
0x18003c892  inc     rsi
0x18003c895  cmp     al, 0Ah
0x18003c897  jnz     short loc_18003C8A2
0x18003c899  inc     dword ptr [rdi+8]
0x18003c89c  mov     byte ptr [rbx], 0Dh
0x18003c89f  inc     rbx
0x18003c8a2  mov     [rbx], al
0x18003c8a4  inc     rbx
0x18003c8a7  lea     rax, [rsp+1468h+var_29]
0x18003c8af  cmp     rbx, rax
0x18003c8b2  jb      short loc_18003C88B
0x18003c8b4  lea     rax, [rsp+1468h+Buffer]
0x18003c8b9  mov     [rsp+1468h+NumberOfBytesWritten], 0
0x18003c8c1  sub     ebx, eax
0x18003c8c3  mov     [rsp+1468h+lpOverlapped], 0; lpOverlapped
0x18003c8cc  mov     r8d, ebx; nNumberOfBytesToWrite
0x18003c8cf  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c8d4  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18003c8d9  mov     rcx, r14; hFile
0x18003c8dc  call    cs:__imp_WriteFile
0x18003c8e2  test    eax, eax
0x18003c8e4  jz      short loc_18003C8F8
0x18003c8e6  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18003c8ea  add     [rdi+4], eax
0x18003c8ed  cmp     eax, ebx
0x18003c8ef  jb      short loc_18003C900
0x18003c8f1  cmp     rsi, rbp
0x18003c8f4  jb      short loc_18003C886
0x18003c8f6  jmp     short loc_18003C900
0x18003c8f8  call    cs:__imp_GetLastError
0x18003c8fe  mov     [rdi], eax
0x18003c900  mov     rax, rdi
0x18003c903  mov     rcx, [rsp+1468h+var_28]
0x18003c90b  xor     rcx, rsp; StackCookie
0x18003c90e  call    __security_check_cookie
0x18003c913  lea     r11, [rsp+1468h+var_18]
0x18003c91b  mov     rbx, [r11+20h]
0x18003c91f  mov     rbp, [r11+30h]
0x18003c923  mov     rsp, r11
0x18003c926  pop     r14
0x18003c928  pop     rdi
0x18003c929  pop     rsi
0x18003c92a  retn
```
