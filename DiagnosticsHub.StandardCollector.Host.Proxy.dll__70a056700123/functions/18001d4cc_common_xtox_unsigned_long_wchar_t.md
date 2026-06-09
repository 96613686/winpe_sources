# common_xtox_unsigned_long_wchar_t_

- ea: `0x18001d4cc`
- end: `0x18001d59f`
- name: `common_xtox_unsigned_long_wchar_t_`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d7ac`
- `0x18001d9ec`
- `0x18001da8c`
- `0x18001db84`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d4cc`

## pseudocode

```c
__int64 __fastcall common_xtox_unsigned_long_wchar_t_(
        unsigned int a1,
        __int16 *a2,
        unsigned __int64 a3,
        unsigned int a4,
        char a5)
{
  __int16 *v8; // r10
  unsigned __int64 v9; // rbx
  __int16 *v10; // r8
  _WORD *v11; // rsi
  __int16 *v12; // r9
  unsigned int v13; // edx
  __int16 v14; // ax
  __int16 v16; // cx

  v8 = a2;
  v9 = 0;
  if ( a5 )
  {
    *a2 = 45;
    v8 = a2 + 1;
    v9 = 1;
    a1 = -a1;
  }
  v10 = v8;
  do
  {
    v11 = v8 + 1;
    v12 = v8;
    v13 = a1 % a4;
    a1 /= a4;
    v14 = 87;
    if ( v13 <= 9 )
      v14 = 48;
    ++v9;
    *v8 = v13 + v14;
    if ( !a1 )
      break;
    ++v8;
  }
  while ( v9 < a3 );
  if ( v9 < a3 )
  {
    *v11 = 0;
    do
    {
      v16 = *v12;
      *v12-- = *v10;
      *v10++ = v16;
    }
    while ( v10 < v12 );
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
0x18001d4cc  mov     [rsp+arg_0], rbx
0x18001d4d1  mov     [rsp+arg_8], rbp
0x18001d4d6  mov     [rsp+arg_10], rsi
0x18001d4db  push    rdi
0x18001d4dc  push    r14
0x18001d4de  push    r15
0x18001d4e0  sub     rsp, 20h
0x18001d4e4  xor     r15d, r15d
0x18001d4e7  mov     ebp, r9d
0x18001d4ea  mov     rdi, r8
0x18001d4ed  mov     r11, rdx
0x18001d4f0  mov     r10, rdx
0x18001d4f3  mov     ebx, r15d
0x18001d4f6  cmp     [rsp+38h+arg_20], r15b
0x18001d4fb  jz      short loc_18001D50C
0x18001d4fd  mov     word ptr [rdx], 2Dh ; '-'
0x18001d502  lea     r10, [rdx+2]
0x18001d506  lea     ebx, [r15+1]
0x18001d50a  neg     ecx
0x18001d50c  mov     r8, r10
0x18001d50f  xor     edx, edx
0x18001d511  lea     rsi, [r10+2]
0x18001d515  mov     eax, ecx
0x18001d517  mov     r9, r10
0x18001d51a  div     ebp
0x18001d51c  mov     ecx, eax
0x18001d51e  cmp     edx, 9
0x18001d521  mov     eax, 57h ; 'W'
0x18001d526  lea     r14d, [rax-27h]
0x18001d52a  cmovbe  ax, r14w
0x18001d52f  inc     rbx
0x18001d532  add     ax, dx
0x18001d535  mov     [r10], ax
0x18001d539  test    ecx, ecx
0x18001d53b  jz      short loc_18001D545
0x18001d53d  mov     r10, rsi
0x18001d540  cmp     rbx, rdi
0x18001d543  jb      short loc_18001D50F
0x18001d545  cmp     rbx, rdi
0x18001d548  jb      short loc_18001D563
0x18001d54a  mov     [r11], r15w
0x18001d54e  call    _errno
0x18001d553  mov     ebx, 22h ; '"'
0x18001d558  mov     [rax], ebx
0x18001d55a  call    _invalid_parameter_noinfo
0x18001d55f  mov     eax, ebx
0x18001d561  jmp     short loc_18001D586
0x18001d563  mov     [rsi], r15w
0x18001d567  movzx   eax, word ptr [r8]
0x18001d56b  movzx   ecx, word ptr [r9]
0x18001d56f  mov     [r9], ax
0x18001d573  sub     r9, 2
0x18001d577  mov     [r8], cx
0x18001d57b  add     r8, 2
0x18001d57f  cmp     r8, r9
0x18001d582  jb      short loc_18001D567
0x18001d584  xor     eax, eax
0x18001d586  mov     rbx, [rsp+38h+arg_0]
0x18001d58b  mov     rbp, [rsp+38h+arg_8]
0x18001d590  mov     rsi, [rsp+38h+arg_10]
0x18001d595  add     rsp, 20h
0x18001d599  pop     r15
0x18001d59b  pop     r14
0x18001d59d  pop     rdi
0x18001d59e  retn
```
