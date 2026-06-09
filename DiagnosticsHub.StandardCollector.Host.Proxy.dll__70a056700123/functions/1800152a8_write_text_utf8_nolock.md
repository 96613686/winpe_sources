# write_text_utf8_nolock

- ea: `0x1800152a8`
- end: `0x18001541c`
- name: `write_text_utf8_nolock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180015610`

## callees

- `0x18000b034`
- `0x1800152a8`
- `0x180032370`
- `0x180032760`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800153c0`
- `KERNEL32!WriteFile` at `0x1800153c0`
- `KERNEL32!GetLastError` at `0x1800153e5`
- `KERNEL32!GetLastError` at `0x1800153e5`

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
0x1800152a8  mov     [rsp+arg_0], rbx
0x1800152ad  mov     [rsp+arg_10], rbp
0x1800152b2  push    rsi
0x1800152b3  push    rdi
0x1800152b4  push    r12
0x1800152b6  push    r14
0x1800152b8  push    r15
0x1800152ba  mov     eax, 1470h
0x1800152bf  call    _alloca_probe
0x1800152c4  sub     rsp, rax
0x1800152c7  mov     rax, cs:__security_cookie
0x1800152ce  xor     rax, rsp
0x1800152d1  mov     [rsp+1498h+var_38], rax
0x1800152d9  movsxd  r10, edx
0x1800152dc  mov     rbx, rcx
0x1800152df  mov     rax, r10
0x1800152e2  mov     r14d, r9d
0x1800152e5  sar     rax, 6
0x1800152e9  lea     rcx, __pioinfo
0x1800152f0  and     r10d, 3Fh
0x1800152f4  add     r14, r8
0x1800152f7  mov     r15, r8
0x1800152fa  mov     rdi, r8
0x1800152fd  mov     rax, [rcx+rax*8]
0x180015301  lea     rdx, [r10+r10*8]
0x180015305  mov     r12, [rax+rdx*8+28h]
0x18001530a  xor     eax, eax
0x18001530c  mov     [rbx], rax
0x18001530f  mov     [rbx+8], eax
0x180015312  cmp     r8, r14
0x180015315  jnb     loc_1800153ED
0x18001531b  lea     r9, [rsp+1498h+var_1448]
0x180015320  cmp     rdi, r14
0x180015323  jnb     short loc_180015351
0x180015325  movzx   eax, word ptr [rdi]
0x180015328  add     rdi, 2
0x18001532c  cmp     ax, 0Ah
0x180015330  jnz     short loc_18001533C
0x180015332  mov     word ptr [r9], 0Dh
0x180015338  add     r9, 2
0x18001533c  mov     [r9], ax
0x180015340  add     r9, 2
0x180015344  lea     rax, [rsp+1498h+var_DA0]
0x18001534c  cmp     r9, rax
0x18001534f  jb      short loc_180015320
0x180015351  and     [rsp+1498h+var_1460], 0
0x180015357  lea     rax, [rsp+1498h+var_1448]
0x18001535c  and     [rsp+1498h+var_1468], 0
0x180015362  lea     r8, [rsp+1498h+var_1448]
0x180015367  sub     r9, rax
0x18001536a  mov     [rsp+1498h+var_1470], 0D55h
0x180015372  lea     rax, [rsp+1498h+Overlapped]
0x18001537a  sar     r9, 1
0x18001537d  xor     edx, edx
0x18001537f  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x180015384  mov     ecx, 0FDE9h
0x180015389  call    __acrt_WideCharToMultiByte
0x18001538e  mov     ebp, eax
0x180015390  test    eax, eax
0x180015392  jz      short loc_1800153E5
0x180015394  xor     esi, esi
0x180015396  test    eax, eax
0x180015398  jz      short loc_1800153D2
0x18001539a  and     [rsp+1498h+NumberOfBytesWritten], 0
0x18001539f  lea     rdx, [rsp+1498h+Overlapped]
0x1800153a7  and     [rsp+1498h+lpOverlapped], 0
0x1800153ad  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800153b2  mov     ecx, esi
0x1800153b4  mov     r8d, ebp
0x1800153b7  add     rdx, rcx; lpBuffer
0x1800153ba  sub     r8d, esi; nNumberOfBytesToWrite
0x1800153bd  mov     rcx, r12; hFile
0x1800153c0  call    cs:__imp_WriteFile
0x1800153c6  test    eax, eax
0x1800153c8  jz      short loc_1800153E5
0x1800153ca  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x1800153ce  cmp     esi, ebp
0x1800153d0  jb      short loc_18001539A
0x1800153d2  mov     eax, edi
0x1800153d4  sub     eax, r15d
0x1800153d7  mov     [rbx+4], eax
0x1800153da  cmp     rdi, r14
0x1800153dd  jb      loc_18001531B
0x1800153e3  jmp     short loc_1800153ED
0x1800153e5  call    cs:__imp_GetLastError
0x1800153eb  mov     [rbx], eax
0x1800153ed  mov     rax, rbx
0x1800153f0  mov     rcx, [rsp+1498h+var_38]
0x1800153f8  xor     rcx, rsp; StackCookie
0x1800153fb  call    __security_check_cookie
0x180015400  lea     r11, [rsp+1498h+var_28]
0x180015408  mov     rbx, [r11+30h]
0x18001540c  mov     rbp, [r11+40h]
0x180015410  mov     rsp, r11
0x180015413  pop     r15
0x180015415  pop     r14
0x180015417  pop     r12
0x180015419  pop     rdi
0x18001541a  pop     rsi
0x18001541b  retn
```
