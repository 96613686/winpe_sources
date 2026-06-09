# write_text_utf8_nolock

- ea: `0x14006fac4`
- end: `0x14006fc38`
- name: `write_text_utf8_nolock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14006fdf0`

## callees

- `0x14003a5c0`
- `0x14003aab0`
- `0x14006fac4`
- `0x140072e98`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14006fbdc`
- `KERNEL32!WriteFile` at `0x14006fbdc`
- `KERNEL32!GetLastError` at `0x14006fc01`
- `KERNEL32!GetLastError` at `0x14006fc01`

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
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x14006fac4  mov     [rsp+arg_0], rbx
0x14006fac9  mov     [rsp+arg_10], rbp
0x14006face  push    rsi
0x14006facf  push    rdi
0x14006fad0  push    r12
0x14006fad2  push    r14
0x14006fad4  push    r15
0x14006fad6  mov     eax, 1470h
0x14006fadb  call    _alloca_probe
0x14006fae0  sub     rsp, rax
0x14006fae3  mov     rax, cs:__security_cookie
0x14006faea  xor     rax, rsp
0x14006faed  mov     [rsp+1498h+var_38], rax
0x14006faf5  movsxd  r10, edx
0x14006faf8  mov     rbx, rcx
0x14006fafb  mov     rax, r10
0x14006fafe  mov     r14d, r9d
0x14006fb01  sar     rax, 6
0x14006fb05  lea     rcx, __pioinfo
0x14006fb0c  and     r10d, 3Fh
0x14006fb10  add     r14, r8
0x14006fb13  mov     r15, r8
0x14006fb16  mov     rdi, r8
0x14006fb19  mov     rax, [rcx+rax*8]
0x14006fb1d  lea     rdx, [r10+r10*8]
0x14006fb21  mov     r12, [rax+rdx*8+28h]
0x14006fb26  xor     eax, eax
0x14006fb28  mov     [rbx], rax
0x14006fb2b  mov     [rbx+8], eax
0x14006fb2e  cmp     r8, r14
0x14006fb31  jnb     loc_14006FC09
0x14006fb37  lea     r9, [rsp+1498h+var_1448]
0x14006fb3c  cmp     rdi, r14
0x14006fb3f  jnb     short loc_14006FB6D
0x14006fb41  movzx   eax, word ptr [rdi]
0x14006fb44  add     rdi, 2
0x14006fb48  cmp     ax, 0Ah
0x14006fb4c  jnz     short loc_14006FB58
0x14006fb4e  mov     word ptr [r9], 0Dh
0x14006fb54  add     r9, 2
0x14006fb58  mov     [r9], ax
0x14006fb5c  add     r9, 2
0x14006fb60  lea     rax, [rsp+1498h+var_DA0]
0x14006fb68  cmp     r9, rax
0x14006fb6b  jb      short loc_14006FB3C
0x14006fb6d  and     [rsp+1498h+var_1460], 0
0x14006fb73  lea     rax, [rsp+1498h+var_1448]
0x14006fb78  and     [rsp+1498h+var_1468], 0
0x14006fb7e  lea     r8, [rsp+1498h+var_1448]
0x14006fb83  sub     r9, rax
0x14006fb86  mov     [rsp+1498h+var_1470], 0D55h
0x14006fb8e  lea     rax, [rsp+1498h+Overlapped]
0x14006fb96  sar     r9, 1
0x14006fb99  xor     edx, edx
0x14006fb9b  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x14006fba0  mov     ecx, 0FDE9h
0x14006fba5  call    __acrt_WideCharToMultiByte
0x14006fbaa  mov     ebp, eax
0x14006fbac  test    eax, eax
0x14006fbae  jz      short loc_14006FC01
0x14006fbb0  xor     esi, esi
0x14006fbb2  test    eax, eax
0x14006fbb4  jz      short loc_14006FBEE
0x14006fbb6  and     [rsp+1498h+NumberOfBytesWritten], 0
0x14006fbbb  lea     rdx, [rsp+1498h+Overlapped]
0x14006fbc3  and     [rsp+1498h+lpOverlapped], 0
0x14006fbc9  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14006fbce  mov     ecx, esi
0x14006fbd0  mov     r8d, ebp
0x14006fbd3  add     rdx, rcx; lpBuffer
0x14006fbd6  sub     r8d, esi; nNumberOfBytesToWrite
0x14006fbd9  mov     rcx, r12; hFile
0x14006fbdc  call    cs:__imp_WriteFile
0x14006fbe2  test    eax, eax
0x14006fbe4  jz      short loc_14006FC01
0x14006fbe6  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x14006fbea  cmp     esi, ebp
0x14006fbec  jb      short loc_14006FBB6
0x14006fbee  mov     eax, edi
0x14006fbf0  sub     eax, r15d
0x14006fbf3  mov     [rbx+4], eax
0x14006fbf6  cmp     rdi, r14
0x14006fbf9  jb      loc_14006FB37
0x14006fbff  jmp     short loc_14006FC09
0x14006fc01  call    cs:__imp_GetLastError
0x14006fc07  mov     [rbx], eax
0x14006fc09  mov     rax, rbx
0x14006fc0c  mov     rcx, [rsp+1498h+var_38]
0x14006fc14  xor     rcx, rsp; StackCookie
0x14006fc17  call    __security_check_cookie
0x14006fc1c  lea     r11, [rsp+1498h+var_28]
0x14006fc24  mov     rbx, [r11+30h]
0x14006fc28  mov     rbp, [r11+40h]
0x14006fc2c  mov     rsp, r11
0x14006fc2f  pop     r15
0x14006fc31  pop     r14
0x14006fc33  pop     r12
0x14006fc35  pop     rdi
0x14006fc36  pop     rsi
0x14006fc37  retn
```
