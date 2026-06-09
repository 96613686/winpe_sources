# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000645c`
- end: `0x180006549`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000310c`

## callees

- `0x1800018f4`
- `0x18000645c`
- `0x180010f36`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800064d7`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800064d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000651e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000651e`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( v9 )
        goto LABEL_31;
      std::_Xbad_alloc();
    }
    v9 = 0;
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
LABEL_31:
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000645c  mov     [rsp+arg_10], r8
0x180006461  mov     [rsp+arg_8], rdx
0x180006466  mov     [rsp+arg_0], rcx
0x18000646b  push    rbx
0x18000646c  push    rsi
0x18000646d  push    rdi
0x18000646e  push    r14
0x180006470  sub     rsp, 28h
0x180006474  mov     r14, r8
0x180006477  mov     rdi, rdx
0x18000647a  mov     rbx, rcx
0x18000647d  or      rdx, 0Fh
0x180006481  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180006488  cmp     rdx, r9
0x18000648b  ja      short loc_1800064C1
0x18000648d  mov     rdi, rdx
0x180006490  mov     r8, [rcx+18h]
0x180006494  mov     rcx, r8
0x180006497  shr     rcx, 1
0x18000649a  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800064a4  mul     rdx
0x1800064a7  shr     rdx, 1
0x1800064aa  cmp     rcx, rdx
0x1800064ad  jbe     short loc_1800064C1
0x1800064af  mov     rax, r9
0x1800064b2  sub     rax, rcx
0x1800064b5  cmp     r8, rax
0x1800064b8  lea     rdi, [rcx+r8]
0x1800064bc  jbe     short loc_1800064C1
0x1800064be  mov     rdi, r9
0x1800064c1  lea     rcx, [rdi+1]; Size
0x1800064c5  test    rcx, rcx
0x1800064c8  jz      short loc_1800064DD
0x1800064ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064cf  mov     rsi, rax
0x1800064d2  test    rax, rax
0x1800064d5  jnz     short loc_1800064DF
0x1800064d7  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800064dd  xor     esi, esi
0x1800064df  jmp     short loc_1800064F5
0x1800064e1  mov     rbx, [rsp+48h+arg_0]
0x1800064e6  mov     r14, [rsp+48h+arg_10]
0x1800064eb  mov     rdi, [rsp+48h+arg_8]
0x1800064f0  mov     rsi, [rsp+48h+arg_18]
0x1800064f5  test    r14, r14
0x1800064f8  jz      short loc_180006514
0x1800064fa  cmp     qword ptr [rbx+18h], 10h
0x1800064ff  jb      short loc_180006506
0x180006501  mov     rdx, [rbx]
0x180006504  jmp     short loc_180006509
0x180006506  mov     rdx, rbx; Src
0x180006509  mov     r8, r14; Size
0x18000650c  mov     rcx, rsi; void *
0x18000650f  call    memcpy_0
0x180006514  cmp     qword ptr [rbx+18h], 10h
0x180006519  jb      short loc_180006524
0x18000651b  mov     rcx, [rbx]
0x18000651e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006524  lea     rax, [rbx+10h]
0x180006528  mov     [rbx], rsi
0x18000652b  mov     [rbx+18h], rdi
0x18000652f  cmp     rdi, 10h
0x180006533  cmovnb  rbx, rsi
0x180006537  mov     [rax], r14
0x18000653a  mov     byte ptr [rbx+r14], 0
0x18000653f  add     rsp, 28h
0x180006543  pop     r14
0x180006545  pop     rdi
0x180006546  pop     rsi
0x180006547  pop     rbx
0x180006548  retn
```
