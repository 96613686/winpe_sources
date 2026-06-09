# common_expand_argv_wildcards_char_

- ea: `0x180008440`
- end: `0x18000867a`
- name: `common_expand_argv_wildcards_char_`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180009d84`

## callees

- `0x180004ca0`
- `0x180007c00`
- `0x180007c50`
- `0x180007ee8`
- `0x180008040`
- `0x180008440`
- `0x180008a7c`
- `0x180008d88`
- `0x180012fd0`
- `0x1800131c0`

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
0x180008440  mov     [rsp-38h+arg_0], rbx
0x180008445  push    rbp
0x180008446  push    rsi
0x180008447  push    rdi
0x180008448  push    r12
0x18000844a  push    r13
0x18000844c  push    r14
0x18000844e  push    r15
0x180008450  mov     rbp, rsp
0x180008453  sub     rsp, 50h
0x180008457  xor     r15d, r15d
0x18000845a  mov     r13, rdx
0x18000845d  mov     rbx, rcx
0x180008460  test    rdx, rdx
0x180008463  jnz     short loc_18000847C
0x180008465  call    _errno
0x18000846a  lea     ebx, [r13+16h]
0x18000846e  mov     [rax], ebx
0x180008470  call    _invalid_parameter_noinfo
0x180008475  mov     eax, ebx
0x180008477  jmp     loc_18000864C
0x18000847c  xorps   xmm0, xmm0
0x18000847f  mov     [rdx], r15
0x180008482  mov     rax, [rcx]
0x180008485  movdqu  xmmword ptr [rbp+Block], xmm0
0x18000848a  mov     [rbp+var_10], r15
0x18000848e  jmp     short loc_180008507
0x180008490  lea     rdx, [rbp+Control]; Control
0x180008494  mov     word ptr [rbp+Control], 3F2Ah
0x18000849a  mov     rcx, rax; Str
0x18000849d  mov     byte ptr [rbp+Control+2], r15b
0x1800084a1  call    strpbrk
0x1800084a6  mov     rcx, [rbx]; char *
0x1800084a9  test    rax, rax
0x1800084ac  jnz     short loc_1800084EA
0x1800084ae  lea     r9, [rbp+Block]
0x1800084b2  xor     r8d, r8d; MaxCount
0x1800084b5  xor     edx, edx; char *
0x1800084b7  call    copy_and_add_argument_to_buffer_char_
0x1800084bc  mov     esi, eax
0x1800084be  test    eax, eax
0x1800084c0  jz      short loc_180008500
0x1800084c2  mov     rdi, [rbp+Block]
0x1800084c6  mov     rbx, rdi
0x1800084c9  cmp     rdi, [rbp+Block+8]
0x1800084cd  jz      loc_18000858F
0x1800084d3  mov     rcx, [rbx]; Block
0x1800084d6  call    _free_base
0x1800084db  add     rbx, 8
0x1800084df  cmp     rbx, [rbp+Block+8]
0x1800084e3  jnz     short loc_1800084D3
0x1800084e5  jmp     loc_18000858F
0x1800084ea  lea     r8, [rbp+Block]
0x1800084ee  mov     rdx, rax
0x1800084f1  call    expand_argument_wildcards_char_
0x1800084f6  mov     esi, eax
0x1800084f8  test    eax, eax
0x1800084fa  jnz     loc_18000859E
0x180008500  add     rbx, 8
0x180008504  mov     rax, [rbx]
0x180008507  test    rax, rax
0x18000850a  jnz     short loc_180008490
0x18000850c  mov     rdi, [rbp+Block]
0x180008510  or      r12, 0FFFFFFFFFFFFFFFFh
0x180008514  mov     rsi, [rbp+Block+8]
0x180008518  mov     rdx, r15
0x18000851b  mov     r14, rsi
0x18000851e  mov     [rbp+arg_10], rdx
0x180008522  sub     r14, rdi
0x180008525  mov     rax, rdi
0x180008528  sar     r14, 3
0x18000852c  inc     r14
0x18000852f  cmp     rdi, rsi
0x180008532  jz      short loc_180008556
0x180008534  mov     r8, [rax]
0x180008537  mov     rcx, r12
0x18000853a  inc     rcx
0x18000853d  cmp     [r8+rcx], r15b
0x180008541  jnz     short loc_18000853A
0x180008543  inc     rdx
0x180008546  add     rax, 8
0x18000854a  add     rdx, rcx
0x18000854d  cmp     rax, rsi
0x180008550  jnz     short loc_180008534
0x180008552  mov     [rbp+arg_10], rdx
0x180008556  mov     r8d, 1
0x18000855c  mov     rcx, r14
0x18000855f  call    __acrt_allocate_buffer_for_argv
0x180008564  mov     rbx, rax
0x180008567  test    rax, rax
0x18000856a  jnz     short loc_1800085BF
0x18000856c  xor     ecx, ecx; Block
0x18000856e  call    _free_base
0x180008573  mov     rbx, rdi
0x180008576  cmp     rdi, rsi
0x180008579  jz      short loc_18000858C
0x18000857b  mov     rcx, [rbx]; Block
0x18000857e  call    _free_base
0x180008583  add     rbx, 8
0x180008587  cmp     rbx, rsi
0x18000858a  jnz     short loc_18000857B
0x18000858c  mov     esi, r12d
0x18000858f  mov     rcx, rdi; Block
0x180008592  call    _free_base
0x180008597  mov     eax, esi
0x180008599  jmp     loc_18000864C
0x18000859e  mov     rdi, [rbp+Block]
0x1800085a2  mov     rbx, rdi
0x1800085a5  cmp     rdi, [rbp+Block+8]
0x1800085a9  jz      short loc_18000858F
0x1800085ab  mov     rcx, [rbx]; Block
0x1800085ae  call    _free_base
0x1800085b3  add     rbx, 8
0x1800085b7  cmp     rbx, [rbp+Block+8]
0x1800085bb  jnz     short loc_1800085AB
0x1800085bd  jmp     short loc_18000858F
0x1800085bf  lea     rcx, [rax+r14*8]
0x1800085c3  mov     r14, rdi
0x1800085c6  mov     [rbp+arg_18], rcx
0x1800085ca  mov     r12, rcx
0x1800085cd  cmp     rdi, rsi
0x1800085d0  jz      short loc_18000861E
0x1800085d2  sub     rax, rdi
0x1800085d5  mov     [rbp+Control], rax
0x1800085d9  mov     r8, [r14]; Source
0x1800085dc  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800085e0  inc     r15
0x1800085e3  cmp     byte ptr [r8+r15], 0
0x1800085e8  jnz     short loc_1800085E0
0x1800085ea  mov     rdx, rcx
0x1800085ed  inc     r15
0x1800085f0  sub     rdx, r12
0x1800085f3  mov     r9, r15; MaxCount
0x1800085f6  add     rdx, [rbp+arg_10]; SizeInBytes
0x1800085fa  mov     rcx, r12; Destination
0x1800085fd  call    strncpy_s
0x180008602  test    eax, eax
0x180008604  jnz     short loc_180008664
0x180008606  mov     rax, [rbp+Control]
0x18000860a  mov     rcx, [rbp+arg_18]
0x18000860e  mov     [rax+r14], r12
0x180008612  add     r12, r15
0x180008615  add     r14, 8
0x180008619  cmp     r14, rsi
0x18000861c  jnz     short loc_1800085D9
0x18000861e  xor     ecx, ecx; Block
0x180008620  mov     [r13+0], rbx
0x180008624  call    _free_base
0x180008629  mov     rbx, rdi
0x18000862c  cmp     rdi, rsi
0x18000862f  jz      short loc_180008642
0x180008631  mov     rcx, [rbx]; Block
0x180008634  call    _free_base
0x180008639  add     rbx, 8
0x18000863d  cmp     rbx, rsi
0x180008640  jnz     short loc_180008631
0x180008642  mov     rcx, rdi; Block
0x180008645  call    _free_base
0x18000864a  xor     eax, eax
0x18000864c  mov     rbx, [rsp+50h+arg_0]
0x180008654  add     rsp, 50h
0x180008658  pop     r15
0x18000865a  pop     r14
0x18000865c  pop     r13
0x18000865e  pop     r12
0x180008660  pop     rdi
0x180008661  pop     rsi
0x180008662  pop     rbp
0x180008663  retn
0x180008664  and     [rsp+50h+var_30], 0
0x18000866a  xor     r9d, r9d; LineNo
0x18000866d  xor     r8d, r8d; FileName
0x180008670  xor     edx, edx; FunctionName
0x180008672  xor     ecx, ecx; Expression
0x180008674  call    _invoke_watson
```
