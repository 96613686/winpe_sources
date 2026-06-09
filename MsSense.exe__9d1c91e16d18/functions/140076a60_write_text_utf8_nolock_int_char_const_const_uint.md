# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x140076a60`
- end: `0x140076bd4`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140076cf4`

## callees

- `0x140051b40`
- `0x140051ba0`
- `0x140076a60`
- `0x14007ad18`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140076b78`
- `KERNEL32!WriteFile` at `0x140076b78`
- `KERNEL32!GetLastError` at `0x140076b9d`
- `KERNEL32!GetLastError` at `0x140076b9d`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  char *v9; // r9
  __int16 v10; // ax
  unsigned int v11; // ebp
  unsigned int v12; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v15[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v16; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(qword_1400C4950[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
LABEL_2:
    v9 = v15;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v10 = *v7++;
      if ( v10 == 10 )
      {
        *(_WORD *)v9 = 13;
        v9 += 2;
      }
      *(_WORD *)v9 = v10;
      v9 += 2;
    }
    while ( v9 < &v16 );
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)&Overlapped, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, (char *)&Overlapped + v12, v11 - v12, &NumberOfBytesWritten, 0) )
          break;
        v12 += NumberOfBytesWritten;
        if ( v12 >= v11 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          if ( (unsigned __int64)v7 < v5 )
            goto LABEL_2;
          return a1;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x140076a60  mov     [rsp+arg_0], rbx
0x140076a65  mov     [rsp+arg_10], rbp
0x140076a6a  push    rsi
0x140076a6b  push    rdi
0x140076a6c  push    r12
0x140076a6e  push    r14
0x140076a70  push    r15
0x140076a72  mov     eax, 1470h
0x140076a77  call    __alloca_probe
0x140076a7c  sub     rsp, rax
0x140076a7f  mov     rax, cs:__security_cookie
0x140076a86  xor     rax, rsp
0x140076a89  mov     [rsp+1498h+var_38], rax
0x140076a91  movsxd  r10, edx
0x140076a94  mov     rbx, rcx
0x140076a97  mov     rax, r10
0x140076a9a  mov     r14d, r9d
0x140076a9d  sar     rax, 6
0x140076aa1  lea     rcx, qword_1400C4950
0x140076aa8  and     r10d, 3Fh
0x140076aac  add     r14, r8
0x140076aaf  mov     r15, r8
0x140076ab2  mov     rdi, r8
0x140076ab5  mov     rax, [rcx+rax*8]
0x140076ab9  lea     rdx, [r10+r10*8]
0x140076abd  mov     r12, [rax+rdx*8+28h]
0x140076ac2  xor     eax, eax
0x140076ac4  mov     [rbx], rax
0x140076ac7  mov     [rbx+8], eax
0x140076aca  cmp     r8, r14
0x140076acd  jnb     loc_140076BA5
0x140076ad3  lea     r9, [rsp+1498h+var_1448]
0x140076ad8  cmp     rdi, r14
0x140076adb  jnb     short loc_140076B09
0x140076add  movzx   eax, word ptr [rdi]
0x140076ae0  add     rdi, 2
0x140076ae4  cmp     ax, 0Ah
0x140076ae8  jnz     short loc_140076AF4
0x140076aea  mov     word ptr [r9], 0Dh
0x140076af0  add     r9, 2
0x140076af4  mov     [r9], ax
0x140076af8  add     r9, 2
0x140076afc  lea     rax, [rsp+1498h+var_DA0]
0x140076b04  cmp     r9, rax
0x140076b07  jb      short loc_140076AD8
0x140076b09  and     [rsp+1498h+var_1460], 0
0x140076b0f  lea     rax, [rsp+1498h+var_1448]
0x140076b14  and     [rsp+1498h+var_1468], 0
0x140076b1a  lea     r8, [rsp+1498h+var_1448]
0x140076b1f  sub     r9, rax
0x140076b22  mov     [rsp+1498h+var_1470], 0D55h
0x140076b2a  lea     rax, [rsp+1498h+Overlapped]
0x140076b32  sar     r9, 1
0x140076b35  xor     edx, edx
0x140076b37  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x140076b3c  mov     ecx, 0FDE9h
0x140076b41  call    __acrt_WideCharToMultiByte
0x140076b46  mov     ebp, eax
0x140076b48  test    eax, eax
0x140076b4a  jz      short loc_140076B9D
0x140076b4c  xor     esi, esi
0x140076b4e  test    eax, eax
0x140076b50  jz      short loc_140076B8A
0x140076b52  and     [rsp+1498h+NumberOfBytesWritten], 0
0x140076b57  lea     rdx, [rsp+1498h+Overlapped]
0x140076b5f  and     [rsp+1498h+lpOverlapped], 0
0x140076b65  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140076b6a  mov     ecx, esi
0x140076b6c  mov     r8d, ebp
0x140076b6f  add     rdx, rcx; lpBuffer
0x140076b72  sub     r8d, esi; nNumberOfBytesToWrite
0x140076b75  mov     rcx, r12; hFile
0x140076b78  call    cs:WriteFile
0x140076b7e  test    eax, eax
0x140076b80  jz      short loc_140076B9D
0x140076b82  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x140076b86  cmp     esi, ebp
0x140076b88  jb      short loc_140076B52
0x140076b8a  mov     eax, edi
0x140076b8c  sub     eax, r15d
0x140076b8f  mov     [rbx+4], eax
0x140076b92  cmp     rdi, r14
0x140076b95  jb      loc_140076AD3
0x140076b9b  jmp     short loc_140076BA5
0x140076b9d  call    cs:GetLastError
0x140076ba3  mov     [rbx], eax
0x140076ba5  mov     rax, rbx
0x140076ba8  mov     rcx, [rsp+1498h+var_38]
0x140076bb0  xor     rcx, rsp; StackCookie
0x140076bb3  call    __security_check_cookie
0x140076bb8  lea     r11, [rsp+1498h+var_28]
0x140076bc0  mov     rbx, [r11+30h]
0x140076bc4  mov     rbp, [r11+40h]
0x140076bc8  mov     rsp, r11
0x140076bcb  pop     r15
0x140076bcd  pop     r14
0x140076bcf  pop     r12
0x140076bd1  pop     rdi
0x140076bd2  pop     rsi
0x140076bd3  retn
```
