# write_text_ansi_nolock

- ea: `0x1800157e4`
- end: `0x1800158eb`
- name: `write_text_ansi_nolock`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015d70`

## callees

- `0x180002810`
- `0x1800157e4`
- `0x180032a50`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18001589c`
- `KERNEL32!WriteFile` at `0x18001589c`
- `KERNEL32!GetLastError` at `0x1800158b8`
- `KERNEL32!GetLastError` at `0x1800158b8`

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
0x1800157e4  mov     [rsp+arg_0], rbx
0x1800157e9  mov     [rsp+arg_10], rbp
0x1800157ee  push    rsi
0x1800157ef  push    rdi
0x1800157f0  push    r14
0x1800157f2  mov     eax, 1450h
0x1800157f7  call    _alloca_probe
0x1800157fc  sub     rsp, rax
0x1800157ff  mov     rax, cs:__security_cookie
0x180015806  xor     rax, rsp
0x180015809  mov     [rsp+1468h+var_28], rax
0x180015811  movsxd  r10, edx
0x180015814  mov     rdi, rcx
0x180015817  mov     rax, r10
0x18001581a  mov     ebp, r9d
0x18001581d  sar     rax, 6
0x180015821  lea     rcx, __pioinfo
0x180015828  and     r10d, 3Fh
0x18001582c  add     rbp, r8
0x18001582f  mov     rsi, r8
0x180015832  mov     rax, [rcx+rax*8]
0x180015836  lea     rdx, [r10+r10*8]
0x18001583a  mov     r14, [rax+rdx*8+28h]
0x18001583f  xor     eax, eax
0x180015841  mov     [rdi], rax
0x180015844  mov     [rdi+8], eax
0x180015847  cmp     r8, rbp
0x18001584a  jnb     short loc_1800158C0
0x18001584c  lea     rbx, [rsp+1468h+Buffer]
0x180015851  cmp     rsi, rbp
0x180015854  jnb     short loc_18001587A
0x180015856  mov     al, [rsi]
0x180015858  inc     rsi
0x18001585b  cmp     al, 0Ah
0x18001585d  jnz     short loc_180015868
0x18001585f  inc     dword ptr [rdi+8]
0x180015862  mov     byte ptr [rbx], 0Dh
0x180015865  inc     rbx
0x180015868  mov     [rbx], al
0x18001586a  inc     rbx
0x18001586d  lea     rax, [rsp+1468h+var_29]
0x180015875  cmp     rbx, rax
0x180015878  jb      short loc_180015851
0x18001587a  and     [rsp+1468h+NumberOfBytesWritten], 0
0x18001587f  lea     rax, [rsp+1468h+Buffer]
0x180015884  and     [rsp+1468h+var_1448], 0
0x18001588a  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001588f  sub     ebx, eax
0x180015891  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x180015896  mov     r8d, ebx; nNumberOfBytesToWrite
0x180015899  mov     rcx, r14; hFile
0x18001589c  call    cs:__imp_WriteFile
0x1800158a2  test    eax, eax
0x1800158a4  jz      short loc_1800158B8
0x1800158a6  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800158aa  add     [rdi+4], eax
0x1800158ad  cmp     eax, ebx
0x1800158af  jb      short loc_1800158C0
0x1800158b1  cmp     rsi, rbp
0x1800158b4  jb      short loc_18001584C
0x1800158b6  jmp     short loc_1800158C0
0x1800158b8  call    cs:__imp_GetLastError
0x1800158be  mov     [rdi], eax
0x1800158c0  mov     rax, rdi
0x1800158c3  mov     rcx, [rsp+1468h+var_28]
0x1800158cb  xor     rcx, rsp; StackCookie
0x1800158ce  call    __security_check_cookie
0x1800158d3  lea     r11, [rsp+1468h+var_18]
0x1800158db  mov     rbx, [r11+20h]
0x1800158df  mov     rbp, [r11+30h]
0x1800158e3  mov     rsp, r11
0x1800158e6  pop     r14
0x1800158e8  pop     rdi
0x1800158e9  pop     rsi
0x1800158ea  retn
```
