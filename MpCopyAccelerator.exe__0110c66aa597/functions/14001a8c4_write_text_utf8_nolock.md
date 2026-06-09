# write_text_utf8_nolock

- ea: `0x14001a8c4`
- end: `0x14001aa38`
- name: `write_text_utf8_nolock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14001ab58`

## callees

- `0x140005c20`
- `0x1400170b4`
- `0x14001a8c4`
- `0x14001cfd0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14001a9dc`
- `KERNEL32!WriteFile` at `0x14001a9dc`
- `KERNEL32!GetLastError` at `0x14001aa01`
- `KERNEL32!GetLastError` at `0x14001aa01`

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
0x14001a8c4  mov     [rsp+arg_0], rbx
0x14001a8c9  mov     [rsp+arg_10], rbp
0x14001a8ce  push    rsi
0x14001a8cf  push    rdi
0x14001a8d0  push    r12
0x14001a8d2  push    r14
0x14001a8d4  push    r15
0x14001a8d6  mov     eax, 1470h
0x14001a8db  call    _alloca_probe
0x14001a8e0  sub     rsp, rax
0x14001a8e3  mov     rax, cs:__security_cookie
0x14001a8ea  xor     rax, rsp
0x14001a8ed  mov     [rsp+1498h+var_38], rax
0x14001a8f5  movsxd  r10, edx
0x14001a8f8  mov     rbx, rcx
0x14001a8fb  mov     rax, r10
0x14001a8fe  mov     r14d, r9d
0x14001a901  sar     rax, 6
0x14001a905  lea     rcx, __pioinfo
0x14001a90c  and     r10d, 3Fh
0x14001a910  add     r14, r8
0x14001a913  mov     r15, r8
0x14001a916  mov     rdi, r8
0x14001a919  mov     rax, [rcx+rax*8]
0x14001a91d  lea     rdx, [r10+r10*8]
0x14001a921  mov     r12, [rax+rdx*8+28h]
0x14001a926  xor     eax, eax
0x14001a928  mov     [rbx], rax
0x14001a92b  mov     [rbx+8], eax
0x14001a92e  cmp     r8, r14
0x14001a931  jnb     loc_14001AA09
0x14001a937  lea     r9, [rsp+1498h+var_1448]
0x14001a93c  cmp     rdi, r14
0x14001a93f  jnb     short loc_14001A96D
0x14001a941  movzx   eax, word ptr [rdi]
0x14001a944  add     rdi, 2
0x14001a948  cmp     ax, 0Ah
0x14001a94c  jnz     short loc_14001A958
0x14001a94e  mov     word ptr [r9], 0Dh
0x14001a954  add     r9, 2
0x14001a958  mov     [r9], ax
0x14001a95c  add     r9, 2
0x14001a960  lea     rax, [rsp+1498h+var_DA0]
0x14001a968  cmp     r9, rax
0x14001a96b  jb      short loc_14001A93C
0x14001a96d  and     [rsp+1498h+var_1460], 0
0x14001a973  lea     rax, [rsp+1498h+var_1448]
0x14001a978  and     [rsp+1498h+var_1468], 0
0x14001a97e  lea     r8, [rsp+1498h+var_1448]
0x14001a983  sub     r9, rax
0x14001a986  mov     [rsp+1498h+var_1470], 0D55h
0x14001a98e  lea     rax, [rsp+1498h+Overlapped]
0x14001a996  sar     r9, 1
0x14001a999  xor     edx, edx
0x14001a99b  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x14001a9a0  mov     ecx, 0FDE9h
0x14001a9a5  call    __acrt_WideCharToMultiByte
0x14001a9aa  mov     ebp, eax
0x14001a9ac  test    eax, eax
0x14001a9ae  jz      short loc_14001AA01
0x14001a9b0  xor     esi, esi
0x14001a9b2  test    eax, eax
0x14001a9b4  jz      short loc_14001A9EE
0x14001a9b6  and     [rsp+1498h+NumberOfBytesWritten], 0
0x14001a9bb  lea     rdx, [rsp+1498h+Overlapped]
0x14001a9c3  and     [rsp+1498h+lpOverlapped], 0
0x14001a9c9  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001a9ce  mov     ecx, esi
0x14001a9d0  mov     r8d, ebp
0x14001a9d3  add     rdx, rcx; lpBuffer
0x14001a9d6  sub     r8d, esi; nNumberOfBytesToWrite
0x14001a9d9  mov     rcx, r12; hFile
0x14001a9dc  call    cs:__imp_WriteFile
0x14001a9e2  test    eax, eax
0x14001a9e4  jz      short loc_14001AA01
0x14001a9e6  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x14001a9ea  cmp     esi, ebp
0x14001a9ec  jb      short loc_14001A9B6
0x14001a9ee  mov     eax, edi
0x14001a9f0  sub     eax, r15d
0x14001a9f3  mov     [rbx+4], eax
0x14001a9f6  cmp     rdi, r14
0x14001a9f9  jb      loc_14001A937
0x14001a9ff  jmp     short loc_14001AA09
0x14001aa01  call    cs:__imp_GetLastError
0x14001aa07  mov     [rbx], eax
0x14001aa09  mov     rax, rbx
0x14001aa0c  mov     rcx, [rsp+1498h+var_38]
0x14001aa14  xor     rcx, rsp; StackCookie
0x14001aa17  call    __security_check_cookie
0x14001aa1c  lea     r11, [rsp+1498h+var_28]
0x14001aa24  mov     rbx, [r11+30h]
0x14001aa28  mov     rbp, [r11+40h]
0x14001aa2c  mov     rsp, r11
0x14001aa2f  pop     r15
0x14001aa31  pop     r14
0x14001aa33  pop     r12
0x14001aa35  pop     rdi
0x14001aa36  pop     rsi
0x14001aa37  retn
```
