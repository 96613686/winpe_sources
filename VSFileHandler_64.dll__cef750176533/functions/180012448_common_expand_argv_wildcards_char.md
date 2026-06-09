# common_expand_argv_wildcards_char_

- ea: `0x180012448`
- end: `0x180012651`
- name: `common_expand_argv_wildcards_char_`
- size: `521`
- prototype: `__int64 __fastcall(const char **, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180012aec`

## callees

- `0x18000be9c`
- `0x18000bebc`
- `0x18000bfbc`
- `0x18000dd40`
- `0x18000fe3c`
- `0x180012448`
- `0x180012654`
- `0x1800127dc`
- `0x180017470`
- `0x1800175f0`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards_char_(const char **a1, __int64 *a2)
{
  const char **v2; // rbx
  const char *i; // rax
  char *v5; // rax
  char *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // esi
  __int64 buffer_for_argv; // rax
  __int64 v10; // rdx
  __int64 Control; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v13; // [rsp+B8h] [rbp+58h]

  v2 = a1;
  if ( a2 )
  {
    *a2 = 0;
    for ( i = *a1; i; i = *v2 )
    {
      strcpy((char *)&Control, "*?");
      v5 = strpbrk(i, (const char *)&Control);
      v6 = (char *)*v2;
      if ( v5 )
        v7 = expand_argument_wildcards_char_(v6);
      else
        v7 = copy_and_add_argument_to_buffer_char_(v6, 0, 0);
      v8 = v7;
      if ( v7 )
        goto LABEL_14;
      ++v2;
    }
    Control = 0;
    v8 = -1;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(1, 0, 1);
    if ( buffer_for_argv )
    {
      v10 = buffer_for_argv + 8;
      v13 = v10;
      v8 = 0;
      *a2 = buffer_for_argv;
    }
    free_base(0);
LABEL_14:
    free_base(0);
    return v8;
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
0x180012448  mov     [rsp-38h+arg_0], rbx
0x18001244d  mov     [rsp-38h+arg_8], rdx
0x180012452  push    rbp
0x180012453  push    rsi
0x180012454  push    rdi
0x180012455  push    r12
0x180012457  push    r13
0x180012459  push    r14
0x18001245b  push    r15
0x18001245d  mov     rbp, rsp
0x180012460  sub     rsp, 60h
0x180012464  xor     edi, edi
0x180012466  mov     rbx, rcx
0x180012469  test    rdx, rdx
0x18001246c  jnz     short loc_180012484
0x18001246e  call    _errno
0x180012473  lea     ebx, [rdi+16h]
0x180012476  mov     [rax], ebx
0x180012478  call    _invalid_parameter_noinfo
0x18001247d  mov     eax, ebx
0x18001247f  jmp     loc_180012624
0x180012484  xorps   xmm0, xmm0
0x180012487  mov     [rdx], rdi
0x18001248a  mov     rax, [rcx]
0x18001248d  movdqu  xmmword ptr [rbp+Block], xmm0
0x180012492  mov     [rbp+var_10], rdi
0x180012496  test    rax, rax
0x180012499  jz      short loc_1800124F1
0x18001249b  lea     rdx, [rbp+Control]; Control
0x18001249f  mov     word ptr [rbp+Control], 3F2Ah
0x1800124a5  mov     rcx, rax; Str
0x1800124a8  mov     byte ptr [rbp+Control+2], dil
0x1800124ac  call    strpbrk
0x1800124b1  mov     rcx, [rbx]; char *
0x1800124b4  test    rax, rax
0x1800124b7  jnz     short loc_1800124C9
0x1800124b9  lea     r9, [rbp+Block]
0x1800124bd  xor     r8d, r8d; MaxCount
0x1800124c0  xor     edx, edx; char *
0x1800124c2  call    copy_and_add_argument_to_buffer_char_
0x1800124c7  jmp     short loc_1800124D5
0x1800124c9  lea     r8, [rbp+Block]
0x1800124cd  mov     rdx, rax
0x1800124d0  call    expand_argument_wildcards_char_
0x1800124d5  mov     esi, eax
0x1800124d7  test    eax, eax
0x1800124d9  jnz     short loc_1800124E4
0x1800124db  add     rbx, 8
0x1800124df  mov     rax, [rbx]
0x1800124e2  jmp     short loc_180012496
0x1800124e4  mov     r12, [rbp+Block+8]
0x1800124e8  mov     r15, [rbp+Block]
0x1800124ec  jmp     loc_1800125E9
0x1800124f1  mov     r15, [rbp+Block]
0x1800124f5  mov     r9, rdi
0x1800124f8  mov     r12, [rbp+Block+8]
0x1800124fc  mov     rdx, r15
0x1800124ff  mov     rax, r12
0x180012502  mov     [rbp+Control], rdi
0x180012506  sub     rax, r15
0x180012509  mov     r8, rdi
0x18001250c  mov     r14, rax
0x18001250f  sar     r14, 3
0x180012513  inc     r14
0x180012516  lea     rcx, [rax+7]
0x18001251a  shr     rcx, 3
0x18001251e  cmp     r15, r12
0x180012521  cmova   rcx, rdi
0x180012525  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012529  test    rcx, rcx
0x18001252c  jz      short loc_180012553
0x18001252e  mov     r10, [rdx]
0x180012531  mov     rax, rsi
0x180012534  inc     rax
0x180012537  cmp     [r10+rax], dil
0x18001253b  jnz     short loc_180012534
0x18001253d  inc     r9
0x180012540  add     rdx, 8
0x180012544  add     r9, rax
0x180012547  inc     r8
0x18001254a  cmp     r8, rcx
0x18001254d  jnz     short loc_18001252E
0x18001254f  mov     [rbp+Control], r9
0x180012553  mov     r8d, 1
0x180012559  mov     rdx, r9
0x18001255c  mov     rcx, r14
0x18001255f  call    __acrt_allocate_buffer_for_argv
0x180012564  mov     rbx, rax
0x180012567  test    rax, rax
0x18001256a  jz      short loc_1800125E2
0x18001256c  lea     rdx, [rax+r14*8]
0x180012570  mov     r14, r15
0x180012573  mov     [rbp+var_28], rdx
0x180012577  mov     rax, rdx
0x18001257a  mov     [rbp+arg_18], rdx
0x18001257e  cmp     r15, r12
0x180012581  jz      short loc_1800125D9
0x180012583  mov     rcx, rbx
0x180012586  sub     rcx, r15
0x180012589  mov     [rbp+var_30], rcx
0x18001258d  mov     r8, [r14]; Source
0x180012590  mov     r13, rsi
0x180012593  inc     r13
0x180012596  cmp     [r8+r13], dil
0x18001259a  jnz     short loc_180012593
0x18001259c  sub     rdx, rax
0x18001259f  inc     r13
0x1800125a2  add     rdx, [rbp+Control]; SizeInBytes
0x1800125a6  mov     r9, r13; MaxCount
0x1800125a9  mov     rcx, rax; Destination
0x1800125ac  call    strncpy_s
0x1800125b1  test    eax, eax
0x1800125b3  jnz     loc_18001263C
0x1800125b9  mov     rax, [rbp+arg_18]
0x1800125bd  mov     rcx, [rbp+var_30]
0x1800125c1  mov     rdx, [rbp+var_28]
0x1800125c5  mov     [rcx+r14], rax
0x1800125c9  add     rax, r13
0x1800125cc  add     r14, 8
0x1800125d0  mov     [rbp+arg_18], rax
0x1800125d4  cmp     r14, r12
0x1800125d7  jnz     short loc_18001258D
0x1800125d9  mov     rax, [rbp+arg_8]
0x1800125dd  mov     esi, edi
0x1800125df  mov     [rax], rbx
0x1800125e2  xor     ecx, ecx; Block
0x1800125e4  call    _free_base
0x1800125e9  mov     rbx, r12
0x1800125ec  mov     r14, r15
0x1800125ef  sub     rbx, r15
0x1800125f2  add     rbx, 7
0x1800125f6  shr     rbx, 3
0x1800125fa  cmp     r15, r12
0x1800125fd  cmova   rbx, rdi
0x180012601  test    rbx, rbx
0x180012604  jz      short loc_18001261A
0x180012606  mov     rcx, [r14]; Block
0x180012609  call    _free_base
0x18001260e  inc     rdi
0x180012611  lea     r14, [r14+8]
0x180012615  cmp     rdi, rbx
0x180012618  jnz     short loc_180012606
0x18001261a  mov     rcx, r15; Block
0x18001261d  call    _free_base
0x180012622  mov     eax, esi
0x180012624  mov     rbx, [rsp+60h+arg_0]
0x18001262c  add     rsp, 60h
0x180012630  pop     r15
0x180012632  pop     r14
0x180012634  pop     r13
0x180012636  pop     r12
0x180012638  pop     rdi
0x180012639  pop     rsi
0x18001263a  pop     rbp
0x18001263b  retn
0x18001263c  xor     r9d, r9d; LineNo
0x18001263f  mov     [rsp+60h+Reserved], rdi; Reserved
0x180012644  xor     r8d, r8d; FileName
0x180012647  xor     edx, edx; FunctionName
0x180012649  xor     ecx, ecx; Expression
0x18001264b  call    _invoke_watson
```
