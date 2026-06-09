# common_expand_argv_wildcards_char_

- ea: `0x180007ce0`
- end: `0x180007f1a`
- name: `common_expand_argv_wildcards_char_`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180009624`

## callees

- `0x180004544`
- `0x1800074a0`
- `0x1800074f0`
- `0x180007788`
- `0x1800078e0`
- `0x180007ce0`
- `0x18000831c`
- `0x180008628`
- `0x180012870`
- `0x180012a60`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards_char_(const char **a1, __int64 *a2)
{
  const char **v3; // rbx
  const char *i; // rax
  char *v6; // rax
  char *v7; // rcx
  unsigned int v8; // esi
  __int64 buffer_for_argv; // rax
  __int64 v10; // rcx
  __int64 Control; // [rsp+98h] [rbp+48h] BYREF
  __int64 v12; // [rsp+A0h] [rbp+50h]
  __int64 v13; // [rsp+A8h] [rbp+58h]

  v3 = a1;
  if ( a2 )
  {
    *a2 = 0;
    for ( i = *a1; i; i = *v3 )
    {
      strcpy((char *)&Control, "*?");
      v6 = strpbrk(i, (const char *)&Control);
      v7 = (char *)*v3;
      if ( v6 )
      {
        v8 = expand_argument_wildcards_char_(v7);
        if ( v8 )
          goto LABEL_12;
      }
      else
      {
        v8 = copy_and_add_argument_to_buffer_char_(v7, 0, 0);
        if ( v8 )
          goto LABEL_12;
      }
      ++v3;
    }
    v12 = 0;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(1, 0, 1);
    if ( !buffer_for_argv )
    {
      free_base(0);
      v8 = -1;
LABEL_12:
      free_base(0);
      return v8;
    }
    v10 = buffer_for_argv + 8;
    v13 = v10;
    *a2 = buffer_for_argv;
    free_base(0);
    free_base(0);
    return 0;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x180007ce0  mov     [rsp-38h+arg_0], rbx
0x180007ce5  push    rbp
0x180007ce6  push    rsi
0x180007ce7  push    rdi
0x180007ce8  push    r12
0x180007cea  push    r13
0x180007cec  push    r14
0x180007cee  push    r15
0x180007cf0  mov     rbp, rsp
0x180007cf3  sub     rsp, 50h
0x180007cf7  xor     r15d, r15d
0x180007cfa  mov     r13, rdx
0x180007cfd  mov     rbx, rcx
0x180007d00  test    rdx, rdx
0x180007d03  jnz     short loc_180007D1C
0x180007d05  call    _errno
0x180007d0a  lea     ebx, [r13+16h]
0x180007d0e  mov     [rax], ebx
0x180007d10  call    _invalid_parameter_noinfo
0x180007d15  mov     eax, ebx
0x180007d17  jmp     loc_180007EEC
0x180007d1c  xorps   xmm0, xmm0
0x180007d1f  mov     [rdx], r15
0x180007d22  mov     rax, [rcx]
0x180007d25  movdqu  xmmword ptr [rbp+Block], xmm0
0x180007d2a  mov     [rbp+var_10], r15
0x180007d2e  jmp     short loc_180007DA7
0x180007d30  lea     rdx, [rbp+Control]; Control
0x180007d34  mov     word ptr [rbp+Control], 3F2Ah
0x180007d3a  mov     rcx, rax; Str
0x180007d3d  mov     byte ptr [rbp+Control+2], r15b
0x180007d41  call    strpbrk
0x180007d46  mov     rcx, [rbx]; char *
0x180007d49  test    rax, rax
0x180007d4c  jnz     short loc_180007D8A
0x180007d4e  lea     r9, [rbp+Block]
0x180007d52  xor     r8d, r8d; MaxCount
0x180007d55  xor     edx, edx; char *
0x180007d57  call    copy_and_add_argument_to_buffer_char_
0x180007d5c  mov     esi, eax
0x180007d5e  test    eax, eax
0x180007d60  jz      short loc_180007DA0
0x180007d62  mov     rdi, [rbp+Block]
0x180007d66  mov     rbx, rdi
0x180007d69  cmp     rdi, [rbp+Block+8]
0x180007d6d  jz      loc_180007E2F
0x180007d73  mov     rcx, [rbx]; Block
0x180007d76  call    _free_base
0x180007d7b  add     rbx, 8
0x180007d7f  cmp     rbx, [rbp+Block+8]
0x180007d83  jnz     short loc_180007D73
0x180007d85  jmp     loc_180007E2F
0x180007d8a  lea     r8, [rbp+Block]
0x180007d8e  mov     rdx, rax
0x180007d91  call    expand_argument_wildcards_char_
0x180007d96  mov     esi, eax
0x180007d98  test    eax, eax
0x180007d9a  jnz     loc_180007E3E
0x180007da0  add     rbx, 8
0x180007da4  mov     rax, [rbx]
0x180007da7  test    rax, rax
0x180007daa  jnz     short loc_180007D30
0x180007dac  mov     rdi, [rbp+Block]
0x180007db0  or      r12, 0FFFFFFFFFFFFFFFFh
0x180007db4  mov     rsi, [rbp+Block+8]
0x180007db8  mov     rdx, r15
0x180007dbb  mov     r14, rsi
0x180007dbe  mov     [rbp+arg_10], rdx
0x180007dc2  sub     r14, rdi
0x180007dc5  mov     rax, rdi
0x180007dc8  sar     r14, 3
0x180007dcc  inc     r14
0x180007dcf  cmp     rdi, rsi
0x180007dd2  jz      short loc_180007DF6
0x180007dd4  mov     r8, [rax]
0x180007dd7  mov     rcx, r12
0x180007dda  inc     rcx
0x180007ddd  cmp     [r8+rcx], r15b
0x180007de1  jnz     short loc_180007DDA
0x180007de3  inc     rdx
0x180007de6  add     rax, 8
0x180007dea  add     rdx, rcx
0x180007ded  cmp     rax, rsi
0x180007df0  jnz     short loc_180007DD4
0x180007df2  mov     [rbp+arg_10], rdx
0x180007df6  mov     r8d, 1
0x180007dfc  mov     rcx, r14
0x180007dff  call    __acrt_allocate_buffer_for_argv
0x180007e04  mov     rbx, rax
0x180007e07  test    rax, rax
0x180007e0a  jnz     short loc_180007E5F
0x180007e0c  xor     ecx, ecx; Block
0x180007e0e  call    _free_base
0x180007e13  mov     rbx, rdi
0x180007e16  cmp     rdi, rsi
0x180007e19  jz      short loc_180007E2C
0x180007e1b  mov     rcx, [rbx]; Block
0x180007e1e  call    _free_base
0x180007e23  add     rbx, 8
0x180007e27  cmp     rbx, rsi
0x180007e2a  jnz     short loc_180007E1B
0x180007e2c  mov     esi, r12d
0x180007e2f  mov     rcx, rdi; Block
0x180007e32  call    _free_base
0x180007e37  mov     eax, esi
0x180007e39  jmp     loc_180007EEC
0x180007e3e  mov     rdi, [rbp+Block]
0x180007e42  mov     rbx, rdi
0x180007e45  cmp     rdi, [rbp+Block+8]
0x180007e49  jz      short loc_180007E2F
0x180007e4b  mov     rcx, [rbx]; Block
0x180007e4e  call    _free_base
0x180007e53  add     rbx, 8
0x180007e57  cmp     rbx, [rbp+Block+8]
0x180007e5b  jnz     short loc_180007E4B
0x180007e5d  jmp     short loc_180007E2F
0x180007e5f  lea     rcx, [rax+r14*8]
0x180007e63  mov     r14, rdi
0x180007e66  mov     [rbp+arg_18], rcx
0x180007e6a  mov     r12, rcx
0x180007e6d  cmp     rdi, rsi
0x180007e70  jz      short loc_180007EBE
0x180007e72  sub     rax, rdi
0x180007e75  mov     [rbp+Control], rax
0x180007e79  mov     r8, [r14]; Source
0x180007e7c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007e80  inc     r15
0x180007e83  cmp     byte ptr [r8+r15], 0
0x180007e88  jnz     short loc_180007E80
0x180007e8a  mov     rdx, rcx
0x180007e8d  inc     r15
0x180007e90  sub     rdx, r12
0x180007e93  mov     r9, r15; MaxCount
0x180007e96  add     rdx, [rbp+arg_10]; SizeInBytes
0x180007e9a  mov     rcx, r12; Destination
0x180007e9d  call    strncpy_s
0x180007ea2  test    eax, eax
0x180007ea4  jnz     short loc_180007F04
0x180007ea6  mov     rax, [rbp+Control]
0x180007eaa  mov     rcx, [rbp+arg_18]
0x180007eae  mov     [rax+r14], r12
0x180007eb2  add     r12, r15
0x180007eb5  add     r14, 8
0x180007eb9  cmp     r14, rsi
0x180007ebc  jnz     short loc_180007E79
0x180007ebe  xor     ecx, ecx; Block
0x180007ec0  mov     [r13+0], rbx
0x180007ec4  call    _free_base
0x180007ec9  mov     rbx, rdi
0x180007ecc  cmp     rdi, rsi
0x180007ecf  jz      short loc_180007EE2
0x180007ed1  mov     rcx, [rbx]; Block
0x180007ed4  call    _free_base
0x180007ed9  add     rbx, 8
0x180007edd  cmp     rbx, rsi
0x180007ee0  jnz     short loc_180007ED1
0x180007ee2  mov     rcx, rdi; Block
0x180007ee5  call    _free_base
0x180007eea  xor     eax, eax
0x180007eec  mov     rbx, [rsp+50h+arg_0]
0x180007ef4  add     rsp, 50h
0x180007ef8  pop     r15
0x180007efa  pop     r14
0x180007efc  pop     r13
0x180007efe  pop     r12
0x180007f00  pop     rdi
0x180007f01  pop     rsi
0x180007f02  pop     rbp
0x180007f03  retn
0x180007f04  and     [rsp+50h+var_30], 0
0x180007f0a  xor     r9d, r9d; LineNo
0x180007f0d  xor     r8d, r8d; FileName
0x180007f10  xor     edx, edx; FunctionName
0x180007f12  xor     ecx, ecx; Expression
0x180007f14  call    _invoke_watson
```
