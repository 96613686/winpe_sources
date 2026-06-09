# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x140019898`
- end: `0x140019a0d`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `373`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140019bc8`

## callees

- `0x140015314`
- `0x140019898`
- `0x14001bf00`
- `0x14001c870`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400199d6`
- `KERNEL32!GetLastError` at `0x1400199d6`
- `KERNEL32!WriteFile` at `0x1400199b4`
- `KERNEL32!WriteFile` at `0x1400199b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  bool v9; // cf
  char *v10; // rax
  __int16 v11; // cx
  unsigned int v12; // ebp
  unsigned int v13; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v16[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v17; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(qword_1400D69C0[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  v9 = (unsigned __int64)a3 < v5;
  *(_DWORD *)(a1 + 8) = 0;
LABEL_2:
  if ( v9 )
  {
    v10 = v16;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v11 = *v7++;
      if ( v11 == 10 )
      {
        *(_WORD *)v10 = 13;
        v10 += 2;
      }
      *(_WORD *)v10 = v11;
      v10 += 2;
    }
    while ( v10 < &v17 );
    v12 = _acrt_WideCharToMultiByte(
            65001,
            0,
            (unsigned int)v16,
            (v10 - v16) >> 1,
            (unsigned int)&Overlapped,
            3413,
            0,
            0);
    if ( v12 )
    {
      v13 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, (char *)&Overlapped + v13, v12 - v13, &NumberOfBytesWritten, 0) )
          break;
        v13 += NumberOfBytesWritten;
        if ( v13 >= v12 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          v9 = (unsigned __int64)v7 < v5;
          goto LABEL_2;
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
0x140019898  mov     [rsp+arg_0], rbx
0x14001989d  mov     [rsp+arg_10], rbp
0x1400198a2  push    rsi
0x1400198a3  push    rdi
0x1400198a4  push    r12
0x1400198a6  push    r14
0x1400198a8  push    r15
0x1400198aa  mov     eax, 1470h
0x1400198af  call    __alloca_probe
0x1400198b4  sub     rsp, rax
0x1400198b7  mov     rax, cs:__security_cookie
0x1400198be  xor     rax, rsp
0x1400198c1  mov     [rsp+1498h+var_38], rax
0x1400198c9  movsxd  r10, edx
0x1400198cc  mov     rbx, rcx
0x1400198cf  mov     rax, r10
0x1400198d2  mov     r14d, r9d
0x1400198d5  sar     rax, 6
0x1400198d9  lea     rcx, qword_1400D69C0
0x1400198e0  and     r10d, 3Fh
0x1400198e4  add     r14, r8
0x1400198e7  mov     r15, r8
0x1400198ea  mov     rdi, r8
0x1400198ed  mov     rax, [rcx+rax*8]
0x1400198f1  lea     rdx, [r10+r10*8]
0x1400198f5  mov     r12, [rax+rdx*8+28h]
0x1400198fa  xor     eax, eax
0x1400198fc  mov     [rbx], rax
0x1400198ff  cmp     r8, r14
0x140019902  mov     [rbx+8], eax
0x140019905  jnb     loc_1400199DE
0x14001990b  lea     rax, [rsp+1498h+var_1448]
0x140019910  cmp     rdi, r14
0x140019913  jnb     short loc_140019942
0x140019915  movzx   ecx, word ptr [rdi]
0x140019918  add     rdi, 2
0x14001991c  cmp     cx, 0Ah
0x140019920  jnz     short loc_14001992E
0x140019922  mov     edx, 0Dh
0x140019927  mov     [rax], dx
0x14001992a  add     rax, 2
0x14001992e  mov     [rax], cx
0x140019931  add     rax, 2
0x140019935  lea     rcx, [rsp+1498h+var_DA0]
0x14001993d  cmp     rax, rcx
0x140019940  jb      short loc_140019910
0x140019942  and     [rsp+1498h+var_1460], 0
0x140019948  lea     rcx, [rsp+1498h+var_1448]
0x14001994d  and     [rsp+1498h+var_1468], 0
0x140019953  lea     r8, [rsp+1498h+var_1448]
0x140019958  sub     rax, rcx
0x14001995b  mov     [rsp+1498h+var_1470], 0D55h
0x140019963  lea     rcx, [rsp+1498h+Overlapped]
0x14001996b  sar     rax, 1
0x14001996e  mov     [rsp+1498h+lpOverlapped], rcx; lpOverlapped
0x140019973  mov     r9d, eax
0x140019976  mov     ecx, 0FDE9h
0x14001997b  xor     edx, edx
0x14001997d  call    __acrt_WideCharToMultiByte
0x140019982  mov     ebp, eax
0x140019984  test    eax, eax
0x140019986  jz      short loc_1400199D6
0x140019988  xor     esi, esi
0x14001998a  test    eax, eax
0x14001998c  jz      short loc_1400199C6
0x14001998e  and     [rsp+1498h+NumberOfBytesWritten], 0
0x140019993  lea     rdx, [rsp+1498h+Overlapped]
0x14001999b  and     [rsp+1498h+lpOverlapped], 0
0x1400199a1  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400199a6  mov     ecx, esi
0x1400199a8  mov     r8d, ebp
0x1400199ab  add     rdx, rcx; lpBuffer
0x1400199ae  sub     r8d, esi; nNumberOfBytesToWrite
0x1400199b1  mov     rcx, r12; hFile
0x1400199b4  call    cs:WriteFile
0x1400199ba  test    eax, eax
0x1400199bc  jz      short loc_1400199D6
0x1400199be  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x1400199c2  cmp     esi, ebp
0x1400199c4  jb      short loc_14001998E
0x1400199c6  mov     eax, edi
0x1400199c8  sub     eax, r15d
0x1400199cb  mov     [rbx+4], eax
0x1400199ce  cmp     rdi, r14
0x1400199d1  jmp     loc_140019905
0x1400199d6  call    cs:GetLastError
0x1400199dc  mov     [rbx], eax
0x1400199de  mov     rax, rbx
0x1400199e1  mov     rcx, [rsp+1498h+var_38]
0x1400199e9  xor     rcx, rsp; StackCookie
0x1400199ec  call    __security_check_cookie
0x1400199f1  lea     r11, [rsp+1498h+var_28]
0x1400199f9  mov     rbx, [r11+30h]
0x1400199fd  mov     rbp, [r11+40h]
0x140019a01  mov     rsp, r11
0x140019a04  pop     r15
0x140019a06  pop     r14
0x140019a08  pop     r12
0x140019a0a  pop     rdi
0x140019a0b  pop     rsi
0x140019a0c  retn
```
