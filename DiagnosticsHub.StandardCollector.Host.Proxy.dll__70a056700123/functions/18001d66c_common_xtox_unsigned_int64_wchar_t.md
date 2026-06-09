# common_xtox_unsigned___int64_wchar_t_

- ea: `0x18001d66c`
- end: `0x18001d744`
- name: `common_xtox_unsigned___int64_wchar_t_`
- size: `216`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d880`
- `0x18001d944`
- `0x18001db14`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d66c`

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
0x18001d66c  mov     [rsp+arg_0], rbx
0x18001d671  mov     [rsp+arg_8], rbp
0x18001d676  mov     [rsp+arg_10], rsi
0x18001d67b  push    rdi
0x18001d67c  push    r14
0x18001d67e  push    r15
0x18001d680  sub     rsp, 20h
0x18001d684  xor     r15d, r15d
0x18001d687  mov     rdi, r8
0x18001d68a  mov     r10, rdx
0x18001d68d  mov     r11, rdx
0x18001d690  mov     ebx, r15d
0x18001d693  cmp     [rsp+38h+arg_20], r15b
0x18001d698  jz      short loc_18001D6AA
0x18001d69a  mov     word ptr [rdx], 2Dh ; '-'
0x18001d69f  lea     r11, [rdx+2]
0x18001d6a3  lea     ebx, [r15+1]
0x18001d6a7  neg     rcx
0x18001d6aa  mov     r8, r11
0x18001d6ad  mov     ebp, r9d
0x18001d6b0  xor     edx, edx
0x18001d6b2  lea     rsi, [r11+2]
0x18001d6b6  mov     rax, rcx
0x18001d6b9  mov     r9, r11
0x18001d6bc  div     rbp
0x18001d6bf  mov     rcx, rax
0x18001d6c2  cmp     edx, 9
0x18001d6c5  mov     eax, 57h ; 'W'
0x18001d6ca  lea     r14d, [rax-27h]
0x18001d6ce  cmovbe  ax, r14w
0x18001d6d3  inc     rbx
0x18001d6d6  add     ax, dx
0x18001d6d9  mov     [r11], ax
0x18001d6dd  test    rcx, rcx
0x18001d6e0  jz      short loc_18001D6EA
0x18001d6e2  mov     r11, rsi
0x18001d6e5  cmp     rbx, rdi
0x18001d6e8  jb      short loc_18001D6B0
0x18001d6ea  cmp     rbx, rdi
0x18001d6ed  jb      short loc_18001D708
0x18001d6ef  mov     [r10], r15w
0x18001d6f3  call    _errno
0x18001d6f8  mov     ebx, 22h ; '"'
0x18001d6fd  mov     [rax], ebx
0x18001d6ff  call    _invalid_parameter_noinfo
0x18001d704  mov     eax, ebx
0x18001d706  jmp     short loc_18001D72B
0x18001d708  mov     [rsi], r15w
0x18001d70c  movzx   eax, word ptr [r8]
0x18001d710  movzx   ecx, word ptr [r9]
0x18001d714  mov     [r9], ax
0x18001d718  sub     r9, 2
0x18001d71c  mov     [r8], cx
0x18001d720  add     r8, 2
0x18001d724  cmp     r8, r9
0x18001d727  jb      short loc_18001D70C
0x18001d729  xor     eax, eax
0x18001d72b  mov     rbx, [rsp+38h+arg_0]
0x18001d730  mov     rbp, [rsp+38h+arg_8]
0x18001d735  mov     rsi, [rsp+38h+arg_10]
0x18001d73a  add     rsp, 20h
0x18001d73e  pop     r15
0x18001d740  pop     r14
0x18001d742  pop     rdi
0x18001d743  retn
```
