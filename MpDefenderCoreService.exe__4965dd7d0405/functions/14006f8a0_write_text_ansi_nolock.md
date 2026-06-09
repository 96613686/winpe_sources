# write_text_ansi_nolock

- ea: `0x14006f8a0`
- end: `0x14006f9a7`
- name: `write_text_ansi_nolock`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14006fdf0`

## callees

- `0x14003a5c0`
- `0x14003aab0`
- `0x14006f8a0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14006f958`
- `KERNEL32!WriteFile` at `0x14006f958`
- `KERNEL32!GetLastError` at `0x14006f974`
- `KERNEL32!GetLastError` at `0x14006f974`

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
0x14006f8a0  mov     [rsp+arg_0], rbx
0x14006f8a5  mov     [rsp+arg_10], rbp
0x14006f8aa  push    rsi
0x14006f8ab  push    rdi
0x14006f8ac  push    r14
0x14006f8ae  mov     eax, 1450h
0x14006f8b3  call    _alloca_probe
0x14006f8b8  sub     rsp, rax
0x14006f8bb  mov     rax, cs:__security_cookie
0x14006f8c2  xor     rax, rsp
0x14006f8c5  mov     [rsp+1468h+var_28], rax
0x14006f8cd  movsxd  r10, edx
0x14006f8d0  mov     rdi, rcx
0x14006f8d3  mov     rax, r10
0x14006f8d6  mov     ebp, r9d
0x14006f8d9  sar     rax, 6
0x14006f8dd  lea     rcx, __pioinfo
0x14006f8e4  and     r10d, 3Fh
0x14006f8e8  add     rbp, r8
0x14006f8eb  mov     rsi, r8
0x14006f8ee  mov     rax, [rcx+rax*8]
0x14006f8f2  lea     rdx, [r10+r10*8]
0x14006f8f6  mov     r14, [rax+rdx*8+28h]
0x14006f8fb  xor     eax, eax
0x14006f8fd  mov     [rdi], rax
0x14006f900  mov     [rdi+8], eax
0x14006f903  cmp     r8, rbp
0x14006f906  jnb     short loc_14006F97C
0x14006f908  lea     rbx, [rsp+1468h+Buffer]
0x14006f90d  cmp     rsi, rbp
0x14006f910  jnb     short loc_14006F936
0x14006f912  mov     al, [rsi]
0x14006f914  inc     rsi
0x14006f917  cmp     al, 0Ah
0x14006f919  jnz     short loc_14006F924
0x14006f91b  inc     dword ptr [rdi+8]
0x14006f91e  mov     byte ptr [rbx], 0Dh
0x14006f921  inc     rbx
0x14006f924  mov     [rbx], al
0x14006f926  inc     rbx
0x14006f929  lea     rax, [rsp+1468h+var_29]
0x14006f931  cmp     rbx, rax
0x14006f934  jb      short loc_14006F90D
0x14006f936  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14006f93b  lea     rax, [rsp+1468h+Buffer]
0x14006f940  and     [rsp+1468h+var_1448], 0
0x14006f946  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14006f94b  sub     ebx, eax
0x14006f94d  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14006f952  mov     r8d, ebx; nNumberOfBytesToWrite
0x14006f955  mov     rcx, r14; hFile
0x14006f958  call    cs:__imp_WriteFile
0x14006f95e  test    eax, eax
0x14006f960  jz      short loc_14006F974
0x14006f962  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14006f966  add     [rdi+4], eax
0x14006f969  cmp     eax, ebx
0x14006f96b  jb      short loc_14006F97C
0x14006f96d  cmp     rsi, rbp
0x14006f970  jb      short loc_14006F908
0x14006f972  jmp     short loc_14006F97C
0x14006f974  call    cs:__imp_GetLastError
0x14006f97a  mov     [rdi], eax
0x14006f97c  mov     rax, rdi
0x14006f97f  mov     rcx, [rsp+1468h+var_28]
0x14006f987  xor     rcx, rsp; StackCookie
0x14006f98a  call    __security_check_cookie
0x14006f98f  lea     r11, [rsp+1468h+var_18]
0x14006f997  mov     rbx, [r11+20h]
0x14006f99b  mov     rbp, [r11+30h]
0x14006f99f  mov     rsp, r11
0x14006f9a2  pop     r14
0x14006f9a4  pop     rdi
0x14006f9a5  pop     rsi
0x14006f9a6  retn
```
