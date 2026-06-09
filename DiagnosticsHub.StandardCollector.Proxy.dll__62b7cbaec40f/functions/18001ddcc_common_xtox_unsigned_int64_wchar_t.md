# common_xtox_unsigned___int64_wchar_t_

- ea: `0x18001ddcc`
- end: `0x18001dea4`
- name: `common_xtox_unsigned___int64_wchar_t_`
- size: `216`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001dfe0`
- `0x18001e0a4`
- `0x18001e274`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001ddcc`

## pseudocode

```c
__int64 __fastcall common_xtox_unsigned___int64_wchar_t_(
        unsigned __int64 a1,
        __int16 *a2,
        unsigned __int64 a3,
        unsigned int a4,
        char a5)
{
  __int16 *v7; // r11
  unsigned __int64 v8; // rbx
  __int16 *v9; // r8
  unsigned __int64 v10; // rbp
  _WORD *v11; // rsi
  __int16 *v12; // r9
  unsigned __int64 v13; // rdx
  __int16 v14; // ax
  __int16 v16; // cx

  v7 = a2;
  v8 = 0;
  if ( a5 )
  {
    *a2 = 45;
    v7 = a2 + 1;
    v8 = 1;
    a1 = -(__int64)a1;
  }
  v9 = v7;
  v10 = a4;
  do
  {
    v11 = v7 + 1;
    v12 = v7;
    v13 = a1 % v10;
    a1 /= v10;
    v14 = 87;
    if ( (unsigned int)v13 <= 9 )
      v14 = 48;
    ++v8;
    *v7 = v13 + v14;
    if ( !a1 )
      break;
    ++v7;
  }
  while ( v8 < a3 );
  if ( v8 < a3 )
  {
    *v11 = 0;
    do
    {
      v16 = *v12;
      *v12-- = *v9;
      *v9++ = v16;
    }
    while ( v9 < v12 );
    return 0;
  }
  else
  {
    *a2 = 0;
    *errno() = 34;
    invalid_parameter_noinfo();
    return 34;
  }
}

```

## disassembly

```asm
0x18001ddcc  mov     [rsp+arg_0], rbx
0x18001ddd1  mov     [rsp+arg_8], rbp
0x18001ddd6  mov     [rsp+arg_10], rsi
0x18001dddb  push    rdi
0x18001dddc  push    r14
0x18001ddde  push    r15
0x18001dde0  sub     rsp, 20h
0x18001dde4  xor     r15d, r15d
0x18001dde7  mov     rdi, r8
0x18001ddea  mov     r10, rdx
0x18001dded  mov     r11, rdx
0x18001ddf0  mov     ebx, r15d
0x18001ddf3  cmp     [rsp+38h+arg_20], r15b
0x18001ddf8  jz      short loc_18001DE0A
0x18001ddfa  mov     word ptr [rdx], 2Dh ; '-'
0x18001ddff  lea     r11, [rdx+2]
0x18001de03  lea     ebx, [r15+1]
0x18001de07  neg     rcx
0x18001de0a  mov     r8, r11
0x18001de0d  mov     ebp, r9d
0x18001de10  xor     edx, edx
0x18001de12  lea     rsi, [r11+2]
0x18001de16  mov     rax, rcx
0x18001de19  mov     r9, r11
0x18001de1c  div     rbp
0x18001de1f  mov     rcx, rax
0x18001de22  cmp     edx, 9
0x18001de25  mov     eax, 57h ; 'W'
0x18001de2a  lea     r14d, [rax-27h]
0x18001de2e  cmovbe  ax, r14w
0x18001de33  inc     rbx
0x18001de36  add     ax, dx
0x18001de39  mov     [r11], ax
0x18001de3d  test    rcx, rcx
0x18001de40  jz      short loc_18001DE4A
0x18001de42  mov     r11, rsi
0x18001de45  cmp     rbx, rdi
0x18001de48  jb      short loc_18001DE10
0x18001de4a  cmp     rbx, rdi
0x18001de4d  jb      short loc_18001DE68
0x18001de4f  mov     [r10], r15w
0x18001de53  call    _errno
0x18001de58  mov     ebx, 22h ; '"'
0x18001de5d  mov     [rax], ebx
0x18001de5f  call    _invalid_parameter_noinfo
0x18001de64  mov     eax, ebx
0x18001de66  jmp     short loc_18001DE8B
0x18001de68  mov     [rsi], r15w
0x18001de6c  movzx   eax, word ptr [r8]
0x18001de70  movzx   ecx, word ptr [r9]
0x18001de74  mov     [r9], ax
0x18001de78  sub     r9, 2
0x18001de7c  mov     [r8], cx
0x18001de80  add     r8, 2
0x18001de84  cmp     r8, r9
0x18001de87  jb      short loc_18001DE6C
0x18001de89  xor     eax, eax
0x18001de8b  mov     rbx, [rsp+38h+arg_0]
0x18001de90  mov     rbp, [rsp+38h+arg_8]
0x18001de95  mov     rsi, [rsp+38h+arg_10]
0x18001de9a  add     rsp, 20h
0x18001de9e  pop     r15
0x18001dea0  pop     r14
0x18001dea2  pop     rdi
0x18001dea3  retn
```
