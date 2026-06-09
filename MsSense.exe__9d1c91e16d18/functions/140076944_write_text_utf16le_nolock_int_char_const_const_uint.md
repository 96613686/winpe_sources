# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x140076944`
- end: `0x140076a5f`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140076cf4`

## callees

- `0x140051b40`
- `0x140051ba0`
- `0x140076944`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140076a10`
- `KERNEL32!WriteFile` at `0x140076a10`
- `KERNEL32!GetLastError` at `0x140076a2c`
- `KERNEL32!GetLastError` at `0x140076a2c`

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
0x140076944  mov     [rsp+arg_0], rbx
0x140076949  mov     [rsp+arg_10], rbp
0x14007694e  push    rsi
0x14007694f  push    rdi
0x140076950  push    r14
0x140076952  mov     eax, 1450h
0x140076957  call    __alloca_probe
0x14007695c  sub     rsp, rax
0x14007695f  mov     rax, cs:__security_cookie
0x140076966  xor     rax, rsp
0x140076969  mov     [rsp+1468h+var_28], rax
0x140076971  movsxd  r10, edx
0x140076974  mov     rdi, rcx
0x140076977  mov     rax, r10
0x14007697a  mov     ebp, r9d
0x14007697d  sar     rax, 6
0x140076981  lea     rcx, qword_1400C4950
0x140076988  and     r10d, 3Fh
0x14007698c  add     rbp, r8
0x14007698f  mov     rsi, r8
0x140076992  mov     rax, [rcx+rax*8]
0x140076996  lea     rdx, [r10+r10*8]
0x14007699a  mov     r14, [rax+rdx*8+28h]
0x14007699f  xor     eax, eax
0x1400769a1  mov     [rdi], rax
0x1400769a4  mov     [rdi+8], eax
0x1400769a7  cmp     r8, rbp
0x1400769aa  jnb     loc_140076A34
0x1400769b0  lea     rbx, [rsp+1468h+Buffer]
0x1400769b5  cmp     rsi, rbp
0x1400769b8  jnb     short loc_1400769E8
0x1400769ba  movzx   eax, word ptr [rsi]
0x1400769bd  add     rsi, 2
0x1400769c1  cmp     ax, 0Ah
0x1400769c5  jnz     short loc_1400769D4
0x1400769c7  add     dword ptr [rdi+8], 2
0x1400769cb  mov     word ptr [rbx], 0Dh
0x1400769d0  add     rbx, 2
0x1400769d4  mov     [rbx], ax
0x1400769d7  add     rbx, 2
0x1400769db  lea     rax, [rsp+1468h+var_2A]
0x1400769e3  cmp     rbx, rax
0x1400769e6  jb      short loc_1400769B5
0x1400769e8  and     [rsp+1468h+NumberOfBytesWritten], 0
0x1400769ed  lea     rax, [rsp+1468h+Buffer]
0x1400769f2  and     [rsp+1468h+var_1448], 0
0x1400769f8  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400769fd  sub     rbx, rax
0x140076a00  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x140076a05  sar     rbx, 1
0x140076a08  mov     rcx, r14; hFile
0x140076a0b  add     ebx, ebx
0x140076a0d  mov     r8d, ebx; nNumberOfBytesToWrite
0x140076a10  call    cs:WriteFile
0x140076a16  test    eax, eax
0x140076a18  jz      short loc_140076A2C
0x140076a1a  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x140076a1e  add     [rdi+4], eax
0x140076a21  cmp     eax, ebx
0x140076a23  jb      short loc_140076A34
0x140076a25  cmp     rsi, rbp
0x140076a28  jb      short loc_1400769B0
0x140076a2a  jmp     short loc_140076A34
0x140076a2c  call    cs:GetLastError
0x140076a32  mov     [rdi], eax
0x140076a34  mov     rax, rdi
0x140076a37  mov     rcx, [rsp+1468h+var_28]
0x140076a3f  xor     rcx, rsp; StackCookie
0x140076a42  call    __security_check_cookie
0x140076a47  lea     r11, [rsp+1468h+var_18]
0x140076a4f  mov     rbx, [r11+20h]
0x140076a53  mov     rbp, [r11+30h]
0x140076a57  mov     rsp, r11
0x140076a5a  pop     r14
0x140076a5c  pop     rdi
0x140076a5d  pop     rsi
0x140076a5e  retn
```
