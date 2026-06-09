# std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>,std::allocator<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>>::_Growmap(unsigned __int64)

- ea: `0x18000ce2c`
- end: `0x18000cffb`
- name: `?_Growmap@?$deque@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@@std@@@std@@AEAAX_K@Z`
- size: `463`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000c7ec`

## callees

- `0x180002100`
- `0x180002184`
- `0x1800027c8`
- `0x18000ce2c`
- `0x18000d004`
- `0x18000d02c`
- `0x18002988c`

## pseudocode

```c
void __fastcall std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::_Growmap(
        _QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  _QWORD *v6; // r14
  void *v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  size_t v13; // rbx
  const void *v14; // rdx
  char *v15; // rbx
  size_t v16; // r8
  char *v17; // rcx
  __int64 v18; // rcx
  const struct std::nothrow_t *v19; // rdx
  void *v20; // rax

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_29;
  v5 = 8 * v2;
  if ( !(8 * v2) )
  {
    v6 = 0;
    goto LABEL_15;
  }
  if ( v5 < 0x1000 )
  {
    v6 = operator new(v5);
    goto LABEL_15;
  }
  if ( v5 + 39 < v5 )
LABEL_29:
    __scrt_throw_std_bad_array_new_length();
  v7 = operator new(v5 + 39);
  if ( !v7 )
    goto LABEL_25;
  v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v6 - 1) = v7;
LABEL_15:
  v8 = v4 >> 1;
  v9 = v2 >> 1;
  v10 = 8 * v8;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v11 = a1[2];
  v12 = v2 - v11;
  v13 = 8 * v11 - v10;
  memmove_0(&v6[v8], (const void *)(a1[1] + v10), v13);
  v14 = (const void *)a1[1];
  v15 = (char *)&v6[v8] + v13;
  if ( v8 > v12 )
  {
    memmove_0(v15, v14, 8 * v12);
    memmove_0(v6, (const void *)(8 * v12 + a1[1]), v10 - 8 * v12);
    v17 = (char *)v6 + v10 - 8 * v12;
    v16 = 8 * v12;
  }
  else
  {
    memmove_0(v15, v14, 8 * v8);
    memset_0(&v15[v10], 0, 8 * (v12 - v8));
    v16 = 8 * v8;
    v17 = (char *)v6;
  }
  memset_0(v17, 0, v16);
  v18 = a1[1];
  if ( v18 )
  {
    v19 = (const struct std::nothrow_t *)(8LL * a1[2]);
    if ( (unsigned __int64)v19 < 0x1000 )
    {
      v20 = (void *)a1[1];
      goto LABEL_27;
    }
    v20 = *(void **)(v18 - 8);
    if ( (unsigned __int64)(v18 - (_QWORD)v20 - 8) <= 0x1F )
    {
      v19 = (const struct std::nothrow_t *)((char *)v19 + 39);
LABEL_27:
      operator delete(v20, v19);
      goto LABEL_28;
    }
LABEL_25:
    __fastfail(5u);
  }
LABEL_28:
  a1[2] += v12;
  a1[1] = v6;
}

```

## disassembly

```asm
0x18000ce2c  push    rbx
0x18000ce2e  push    rbp
0x18000ce2f  push    rsi
0x18000ce30  push    rdi
0x18000ce31  push    r12
0x18000ce33  push    r14
0x18000ce35  push    r15
0x18000ce37  sub     rsp, 20h
0x18000ce3b  mov     rbp, rcx
0x18000ce3e  mov     esi, 1
0x18000ce43  mov     rcx, [rcx+10h]
0x18000ce47  test    rcx, rcx
0x18000ce4a  cmovnz  rsi, rcx
0x18000ce4e  mov     rax, rsi
0x18000ce51  sub     rax, rcx
0x18000ce54  cmp     rax, 1
0x18000ce58  jb      short loc_18000CE60
0x18000ce5a  cmp     rsi, 8
0x18000ce5e  jnb     short loc_18000CE7B
0x18000ce60  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000ce6a  sub     rax, rsi
0x18000ce6d  cmp     rax, rsi
0x18000ce70  jb      loc_18000CFF5
0x18000ce76  add     rsi, rsi
0x18000ce79  jmp     short loc_18000CE4E
0x18000ce7b  mov     rdi, [rbp+18h]
0x18000ce7f  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000ce89  cmp     rsi, rax
0x18000ce8c  ja      loc_18000CFEF
0x18000ce92  lea     rcx, ds:0[rsi*8]; Size
0x18000ce9a  test    rcx, rcx
0x18000ce9d  jnz     short loc_18000CEA4
0x18000ce9f  xor     r14d, r14d
0x18000cea2  jmp     short loc_18000CEE1
0x18000cea4  cmp     rcx, 1000h
0x18000ceab  jb      short loc_18000CED9
0x18000cead  lea     rax, [rcx+27h]
0x18000ceb1  cmp     rax, rcx
0x18000ceb4  jbe     loc_18000CFEF
0x18000ceba  mov     rcx, rax; Size
0x18000cebd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cec2  test    rax, rax
0x18000cec5  jz      loc_18000CFC6
0x18000cecb  lea     r14, [rax+27h]
0x18000cecf  and     r14, 0FFFFFFFFFFFFFFE0h
0x18000ced3  mov     [r14-8], rax
0x18000ced7  jmp     short loc_18000CEE1
0x18000ced9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cede  mov     r14, rax
0x18000cee1  shr     rdi, 1
0x18000cee4  mov     rax, rsi
0x18000cee7  shr     rax, 1
0x18000ceea  lea     r15, ds:0[rdi*8]
0x18000cef2  lea     r12, [r15+r14]
0x18000cef6  jmp     short loc_18000CEFB
0x18000cef8  add     rsi, rsi
0x18000cefb  cmp     rsi, rax
0x18000cefe  jbe     short loc_18000CEF8
0x18000cf00  mov     rcx, [rbp+8]
0x18000cf04  mov     rax, [rbp+10h]
0x18000cf08  sub     rsi, rax
0x18000cf0b  shl     rax, 3
0x18000cf0f  lea     rdx, [rcx+r15]; Src
0x18000cf13  sub     rax, rdx
0x18000cf16  lea     rbx, [rax+rcx]
0x18000cf1a  mov     rcx, r12; void *
0x18000cf1d  mov     r8, rbx; Size
0x18000cf20  call    memmove_0
0x18000cf25  mov     rdx, [rbp+8]; Src
0x18000cf29  add     rbx, r12
0x18000cf2c  mov     rcx, rbx; void *
0x18000cf2f  cmp     rdi, rsi
0x18000cf32  ja      short loc_18000CF59
0x18000cf34  mov     r8, r15; Size
0x18000cf37  call    memmove_0
0x18000cf3c  mov     r8, rsi
0x18000cf3f  lea     rcx, [rbx+r15]; void *
0x18000cf43  sub     r8, rdi
0x18000cf46  xor     edx, edx; Val
0x18000cf48  shl     r8, 3; Size
0x18000cf4c  call    memset_0
0x18000cf51  mov     r8, r15
0x18000cf54  mov     rcx, r14
0x18000cf57  jmp     short loc_18000CF8A
0x18000cf59  lea     rdi, ds:0[rsi*8]
0x18000cf61  mov     r8, rdi; Size
0x18000cf64  call    memmove_0
0x18000cf69  mov     rax, [rbp+8]
0x18000cf6d  mov     rcx, r14; void *
0x18000cf70  lea     rdx, [rdi+rax]; Src
0x18000cf74  sub     rax, rdx
0x18000cf77  lea     rbx, [rax+r15]
0x18000cf7b  mov     r8, rbx; Size
0x18000cf7e  call    memmove_0
0x18000cf83  lea     rcx, [rbx+r14]; void *
0x18000cf87  mov     r8, rdi; Size
0x18000cf8a  xor     edx, edx; Val
0x18000cf8c  call    memset_0
0x18000cf91  mov     rcx, [rbp+8]
0x18000cf95  test    rcx, rcx
0x18000cf98  jz      short loc_18000CFD8
0x18000cf9a  mov     rax, [rbp+10h]
0x18000cf9e  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000cfa6  cmp     rdx, 1000h
0x18000cfad  jb      short loc_18000CFCD
0x18000cfaf  mov     rax, [rcx-8]
0x18000cfb3  sub     rcx, rax
0x18000cfb6  sub     rcx, 8
0x18000cfba  cmp     rcx, 1Fh
0x18000cfbe  ja      short loc_18000CFC6
0x18000cfc0  add     rdx, 27h ; '''
0x18000cfc4  jmp     short loc_18000CFD0
0x18000cfc6  mov     ecx, 5
0x18000cfcb  int     29h; Win8: RtlFailFast(ecx)
0x18000cfcd  mov     rax, rcx
0x18000cfd0  mov     rcx, rax; void *
0x18000cfd3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cfd8  add     [rbp+10h], rsi
0x18000cfdc  mov     [rbp+8], r14
0x18000cfe0  add     rsp, 20h
0x18000cfe4  pop     r15
0x18000cfe6  pop     r14
0x18000cfe8  pop     r12
0x18000cfea  pop     rdi
0x18000cfeb  pop     rsi
0x18000cfec  pop     rbp
0x18000cfed  pop     rbx
0x18000cfee  retn
0x18000cfef  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18000cff5  call    ?_Xlen@?$deque@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@@std@@@std@@CAXXZ; std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::_Xlen(void)
```
