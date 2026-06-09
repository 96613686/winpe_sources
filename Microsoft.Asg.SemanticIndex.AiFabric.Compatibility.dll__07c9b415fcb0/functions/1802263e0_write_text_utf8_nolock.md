# write_text_utf8_nolock

- ea: `0x1802263e0`
- end: `0x180226554`
- name: `write_text_utf8_nolock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180226674`

## callees

- `0x1801f7110`
- `0x1801f7d30`
- `0x18021f770`
- `0x1802263e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18022651d`
- `KERNEL32!GetLastError` at `0x18022651d`
- `KERNEL32!WriteFile` at `0x1802264f8`
- `KERNEL32!WriteFile` at `0x1802264f8`

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
0x1802263e0  mov     [rsp+arg_0], rbx
0x1802263e5  mov     [rsp+arg_10], rbp
0x1802263ea  push    rsi
0x1802263eb  push    rdi
0x1802263ec  push    r12
0x1802263ee  push    r14
0x1802263f0  push    r15
0x1802263f2  mov     eax, 1470h
0x1802263f7  call    _alloca_probe
0x1802263fc  sub     rsp, rax
0x1802263ff  mov     rax, cs:__security_cookie
0x180226406  xor     rax, rsp
0x180226409  mov     [rsp+1498h+var_38], rax
0x180226411  movsxd  r10, edx
0x180226414  mov     rbx, rcx
0x180226417  mov     rax, r10
0x18022641a  mov     r14d, r9d
0x18022641d  sar     rax, 6
0x180226421  lea     rcx, __pioinfo
0x180226428  and     r10d, 3Fh
0x18022642c  add     r14, r8
0x18022642f  mov     r15, r8
0x180226432  mov     rdi, r8
0x180226435  mov     rax, [rcx+rax*8]
0x180226439  lea     rdx, [r10+r10*8]
0x18022643d  mov     r12, [rax+rdx*8+28h]
0x180226442  xor     eax, eax
0x180226444  mov     [rbx], rax
0x180226447  mov     [rbx+8], eax
0x18022644a  cmp     r8, r14
0x18022644d  jnb     loc_180226525
0x180226453  lea     r9, [rsp+1498h+var_1448]
0x180226458  cmp     rdi, r14
0x18022645b  jnb     short loc_180226489
0x18022645d  movzx   eax, word ptr [rdi]
0x180226460  add     rdi, 2
0x180226464  cmp     ax, 0Ah
0x180226468  jnz     short loc_180226474
0x18022646a  mov     word ptr [r9], 0Dh
0x180226470  add     r9, 2
0x180226474  mov     [r9], ax
0x180226478  add     r9, 2
0x18022647c  lea     rax, [rsp+1498h+var_DA0]
0x180226484  cmp     r9, rax
0x180226487  jb      short loc_180226458
0x180226489  and     [rsp+1498h+var_1460], 0
0x18022648f  lea     rax, [rsp+1498h+var_1448]
0x180226494  and     [rsp+1498h+var_1468], 0
0x18022649a  lea     r8, [rsp+1498h+var_1448]
0x18022649f  sub     r9, rax
0x1802264a2  mov     [rsp+1498h+var_1470], 0D55h
0x1802264aa  lea     rax, [rsp+1498h+Overlapped]
0x1802264b2  sar     r9, 1
0x1802264b5  xor     edx, edx
0x1802264b7  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x1802264bc  mov     ecx, 0FDE9h
0x1802264c1  call    __acrt_WideCharToMultiByte
0x1802264c6  mov     ebp, eax
0x1802264c8  test    eax, eax
0x1802264ca  jz      short loc_18022651D
0x1802264cc  xor     esi, esi
0x1802264ce  test    eax, eax
0x1802264d0  jz      short loc_18022650A
0x1802264d2  and     [rsp+1498h+NumberOfBytesWritten], 0
0x1802264d7  lea     rdx, [rsp+1498h+Overlapped]
0x1802264df  and     [rsp+1498h+lpOverlapped], 0
0x1802264e5  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802264ea  mov     ecx, esi
0x1802264ec  mov     r8d, ebp
0x1802264ef  add     rdx, rcx; lpBuffer
0x1802264f2  sub     r8d, esi; nNumberOfBytesToWrite
0x1802264f5  mov     rcx, r12; hFile
0x1802264f8  call    cs:__imp_WriteFile
0x1802264fe  test    eax, eax
0x180226500  jz      short loc_18022651D
0x180226502  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x180226506  cmp     esi, ebp
0x180226508  jb      short loc_1802264D2
0x18022650a  mov     eax, edi
0x18022650c  sub     eax, r15d
0x18022650f  mov     [rbx+4], eax
0x180226512  cmp     rdi, r14
0x180226515  jb      loc_180226453
0x18022651b  jmp     short loc_180226525
0x18022651d  call    cs:__imp_GetLastError
0x180226523  mov     [rbx], eax
0x180226525  mov     rax, rbx
0x180226528  mov     rcx, [rsp+1498h+var_38]
0x180226530  xor     rcx, rsp; StackCookie
0x180226533  call    __security_check_cookie
0x180226538  lea     r11, [rsp+1498h+var_28]
0x180226540  mov     rbx, [r11+30h]
0x180226544  mov     rbp, [r11+40h]
0x180226548  mov     rsp, r11
0x18022654b  pop     r15
0x18022654d  pop     r14
0x18022654f  pop     r12
0x180226551  pop     rdi
0x180226552  pop     rsi
0x180226553  retn
```
