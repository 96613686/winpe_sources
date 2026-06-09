# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x14000bc18`
- end: `0x14000bd33`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000bfc8`

## callees

- `0x140001350`
- `0x14000bc18`
- `0x14000ce70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000bd00`
- `KERNEL32!GetLastError` at `0x14000bd00`
- `KERNEL32!WriteFile` at `0x14000bce4`
- `KERNEL32!WriteFile` at `0x14000bce4`

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
0x14000bc18  mov     [rsp+arg_0], rbx
0x14000bc1d  mov     [rsp+arg_10], rbp
0x14000bc22  push    rsi
0x14000bc23  push    rdi
0x14000bc24  push    r14
0x14000bc26  mov     eax, 1450h
0x14000bc2b  call    __alloca_probe
0x14000bc30  sub     rsp, rax
0x14000bc33  mov     rax, cs:__security_cookie
0x14000bc3a  xor     rax, rsp
0x14000bc3d  mov     [rsp+1468h+var_28], rax
0x14000bc45  movsxd  r10, edx
0x14000bc48  mov     rdi, rcx
0x14000bc4b  mov     rax, r10
0x14000bc4e  mov     ebp, r9d
0x14000bc51  sar     rax, 6
0x14000bc55  lea     rcx, qword_14001A750
0x14000bc5c  and     r10d, 3Fh
0x14000bc60  add     rbp, r8
0x14000bc63  mov     rsi, r8
0x14000bc66  mov     rax, [rcx+rax*8]
0x14000bc6a  lea     rdx, [r10+r10*8]
0x14000bc6e  mov     r14, [rax+rdx*8+28h]
0x14000bc73  xor     eax, eax
0x14000bc75  mov     [rdi], rax
0x14000bc78  mov     [rdi+8], eax
0x14000bc7b  cmp     r8, rbp
0x14000bc7e  jnb     loc_14000BD08
0x14000bc84  lea     rbx, [rsp+1468h+Buffer]
0x14000bc89  cmp     rsi, rbp
0x14000bc8c  jnb     short loc_14000BCBC
0x14000bc8e  movzx   eax, word ptr [rsi]
0x14000bc91  add     rsi, 2
0x14000bc95  cmp     ax, 0Ah
0x14000bc99  jnz     short loc_14000BCA8
0x14000bc9b  add     dword ptr [rdi+8], 2
0x14000bc9f  mov     word ptr [rbx], 0Dh
0x14000bca4  add     rbx, 2
0x14000bca8  mov     [rbx], ax
0x14000bcab  add     rbx, 2
0x14000bcaf  lea     rax, [rsp+1468h+var_2A]
0x14000bcb7  cmp     rbx, rax
0x14000bcba  jb      short loc_14000BC89
0x14000bcbc  and     [rsp+1468h+NumberOfBytesWritten], 0
0x14000bcc1  lea     rax, [rsp+1468h+Buffer]
0x14000bcc6  and     [rsp+1468h+var_1448], 0
0x14000bccc  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000bcd1  sub     rbx, rax
0x14000bcd4  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14000bcd9  sar     rbx, 1
0x14000bcdc  mov     rcx, r14; hFile
0x14000bcdf  add     ebx, ebx
0x14000bce1  mov     r8d, ebx; nNumberOfBytesToWrite
0x14000bce4  call    cs:WriteFile
0x14000bcea  test    eax, eax
0x14000bcec  jz      short loc_14000BD00
0x14000bcee  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14000bcf2  add     [rdi+4], eax
0x14000bcf5  cmp     eax, ebx
0x14000bcf7  jb      short loc_14000BD08
0x14000bcf9  cmp     rsi, rbp
0x14000bcfc  jb      short loc_14000BC84
0x14000bcfe  jmp     short loc_14000BD08
0x14000bd00  call    cs:GetLastError
0x14000bd06  mov     [rdi], eax
0x14000bd08  mov     rax, rdi
0x14000bd0b  mov     rcx, [rsp+1468h+var_28]
0x14000bd13  xor     rcx, rsp; StackCookie
0x14000bd16  call    __security_check_cookie
0x14000bd1b  lea     r11, [rsp+1468h+var_18]
0x14000bd23  mov     rbx, [r11+20h]
0x14000bd27  mov     rbp, [r11+30h]
0x14000bd2b  mov     rsp, r11
0x14000bd2e  pop     r14
0x14000bd30  pop     rdi
0x14000bd31  pop     rsi
0x14000bd32  retn
```
