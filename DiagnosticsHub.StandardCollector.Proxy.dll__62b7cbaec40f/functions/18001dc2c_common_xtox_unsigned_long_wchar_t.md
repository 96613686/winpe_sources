# common_xtox_unsigned_long_wchar_t_

- ea: `0x18001dc2c`
- end: `0x18001dcff`
- name: `common_xtox_unsigned_long_wchar_t_`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001df0c`
- `0x18001e14c`
- `0x18001e1ec`
- `0x18001e2e4`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001dc2c`

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
0x18001dc2c  mov     [rsp+arg_0], rbx
0x18001dc31  mov     [rsp+arg_8], rbp
0x18001dc36  mov     [rsp+arg_10], rsi
0x18001dc3b  push    rdi
0x18001dc3c  push    r14
0x18001dc3e  push    r15
0x18001dc40  sub     rsp, 20h
0x18001dc44  xor     r15d, r15d
0x18001dc47  mov     ebp, r9d
0x18001dc4a  mov     rdi, r8
0x18001dc4d  mov     r11, rdx
0x18001dc50  mov     r10, rdx
0x18001dc53  mov     ebx, r15d
0x18001dc56  cmp     [rsp+38h+arg_20], r15b
0x18001dc5b  jz      short loc_18001DC6C
0x18001dc5d  mov     word ptr [rdx], 2Dh ; '-'
0x18001dc62  lea     r10, [rdx+2]
0x18001dc66  lea     ebx, [r15+1]
0x18001dc6a  neg     ecx
0x18001dc6c  mov     r8, r10
0x18001dc6f  xor     edx, edx
0x18001dc71  lea     rsi, [r10+2]
0x18001dc75  mov     eax, ecx
0x18001dc77  mov     r9, r10
0x18001dc7a  div     ebp
0x18001dc7c  mov     ecx, eax
0x18001dc7e  cmp     edx, 9
0x18001dc81  mov     eax, 57h ; 'W'
0x18001dc86  lea     r14d, [rax-27h]
0x18001dc8a  cmovbe  ax, r14w
0x18001dc8f  inc     rbx
0x18001dc92  add     ax, dx
0x18001dc95  mov     [r10], ax
0x18001dc99  test    ecx, ecx
0x18001dc9b  jz      short loc_18001DCA5
0x18001dc9d  mov     r10, rsi
0x18001dca0  cmp     rbx, rdi
0x18001dca3  jb      short loc_18001DC6F
0x18001dca5  cmp     rbx, rdi
0x18001dca8  jb      short loc_18001DCC3
0x18001dcaa  mov     [r11], r15w
0x18001dcae  call    _errno
0x18001dcb3  mov     ebx, 22h ; '"'
0x18001dcb8  mov     [rax], ebx
0x18001dcba  call    _invalid_parameter_noinfo
0x18001dcbf  mov     eax, ebx
0x18001dcc1  jmp     short loc_18001DCE6
0x18001dcc3  mov     [rsi], r15w
0x18001dcc7  movzx   eax, word ptr [r8]
0x18001dccb  movzx   ecx, word ptr [r9]
0x18001dccf  mov     [r9], ax
0x18001dcd3  sub     r9, 2
0x18001dcd7  mov     [r8], cx
0x18001dcdb  add     r8, 2
0x18001dcdf  cmp     r8, r9
0x18001dce2  jb      short loc_18001DCC7
0x18001dce4  xor     eax, eax
0x18001dce6  mov     rbx, [rsp+38h+arg_0]
0x18001dceb  mov     rbp, [rsp+38h+arg_8]
0x18001dcf0  mov     rsi, [rsp+38h+arg_10]
0x18001dcf5  add     rsp, 20h
0x18001dcf9  pop     r15
0x18001dcfb  pop     r14
0x18001dcfd  pop     rdi
0x18001dcfe  retn
```
