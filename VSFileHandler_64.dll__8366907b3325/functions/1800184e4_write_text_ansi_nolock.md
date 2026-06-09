# write_text_ansi_nolock

- ea: `0x1800184e4`
- end: `0x1800185e6`
- name: `write_text_ansi_nolock`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018960`

## callees

- `0x180007700`
- `0x1800184e4`
- `0x18001aff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800185b3`
- `KERNEL32!GetLastError` at `0x1800185b3`
- `KERNEL32!WriteFile` at `0x180018597`
- `KERNEL32!WriteFile` at `0x180018597`

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
0x1800184e4  mov     [rsp+arg_0], rbx
0x1800184e9  mov     [rsp+arg_10], rbp
0x1800184ee  push    rsi
0x1800184ef  push    rdi
0x1800184f0  push    r14
0x1800184f2  mov     eax, 1450h
0x1800184f7  call    _alloca_probe
0x1800184fc  sub     rsp, rax
0x1800184ff  mov     rax, cs:__security_cookie
0x180018506  xor     rax, rsp
0x180018509  mov     [rsp+1468h+var_28], rax
0x180018511  movsxd  r10, edx
0x180018514  mov     rdi, rcx
0x180018517  mov     rax, r10
0x18001851a  mov     ebp, r9d
0x18001851d  sar     rax, 6
0x180018521  lea     rcx, __pioinfo
0x180018528  and     r10d, 3Fh
0x18001852c  add     rbp, r8
0x18001852f  mov     rsi, r8
0x180018532  mov     rax, [rcx+rax*8]
0x180018536  lea     rdx, [r10+r10*8]
0x18001853a  mov     r14, [rax+rdx*8+28h]
0x18001853f  xor     eax, eax
0x180018541  mov     [rdi], rax
0x180018544  mov     [rdi+8], eax
0x180018547  cmp     r8, rbp
0x18001854a  jnb     short loc_1800185BB
0x18001854c  lea     rbx, [rsp+1468h+Buffer]
0x180018551  cmp     rsi, rbp
0x180018554  jnb     short loc_18001857A
0x180018556  mov     al, [rsi]
0x180018558  inc     rsi
0x18001855b  cmp     al, 0Ah
0x18001855d  jnz     short loc_180018568
0x18001855f  inc     dword ptr [rdi+8]
0x180018562  mov     byte ptr [rbx], 0Dh
0x180018565  inc     rbx
0x180018568  mov     [rbx], al
0x18001856a  inc     rbx
0x18001856d  lea     rax, [rsp+1468h+var_29]
0x180018575  cmp     rbx, rax
0x180018578  jb      short loc_180018551
0x18001857a  and     [rsp+1468h+var_1448], 0
0x180018580  lea     rax, [rsp+1468h+Buffer]
0x180018585  sub     ebx, eax
0x180018587  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001858c  mov     r8d, ebx; nNumberOfBytesToWrite
0x18001858f  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x180018594  mov     rcx, r14; hFile
0x180018597  call    cs:__imp_WriteFile
0x18001859d  test    eax, eax
0x18001859f  jz      short loc_1800185B3
0x1800185a1  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800185a5  add     [rdi+4], eax
0x1800185a8  cmp     eax, ebx
0x1800185aa  jb      short loc_1800185BB
0x1800185ac  cmp     rsi, rbp
0x1800185af  jb      short loc_18001854C
0x1800185b1  jmp     short loc_1800185BB
0x1800185b3  call    cs:__imp_GetLastError
0x1800185b9  mov     [rdi], eax
0x1800185bb  mov     rax, rdi
0x1800185be  mov     rcx, [rsp+1468h+var_28]
0x1800185c6  xor     rcx, rsp; StackCookie
0x1800185c9  call    __security_check_cookie
0x1800185ce  lea     r11, [rsp+1468h+var_18]
0x1800185d6  mov     rbx, [r11+20h]
0x1800185da  mov     rbp, [r11+30h]
0x1800185de  mov     rsp, r11
0x1800185e1  pop     r14
0x1800185e3  pop     rdi
0x1800185e4  pop     rsi
0x1800185e5  retn
```
