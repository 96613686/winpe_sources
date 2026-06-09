# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001418`
- end: `0x18000150f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001628`
- `0x180001720`

## callees

- `0x18000123c`
- `0x180001418`
- `0x180001578`
- `0x180002066`
- `0x180002596`

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
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
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
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
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
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
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
0x180001418  mov     rax, rsp
0x18000141b  mov     [rax+18h], r8
0x18000141f  mov     [rax+10h], rdx
0x180001423  mov     [rax+8], rcx
0x180001427  push    rbx
0x180001428  push    rsi
0x180001429  push    rdi
0x18000142a  push    r14
0x18000142c  sub     rsp, 38h
0x180001430  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001438  mov     r14, r8
0x18000143b  mov     rdi, rdx
0x18000143e  mov     rbx, rcx
0x180001441  or      rdx, 0Fh
0x180001445  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000144c  cmp     rdx, r9
0x18000144f  ja      short loc_180001485
0x180001451  mov     rdi, rdx
0x180001454  mov     r8, [rcx+18h]
0x180001458  mov     rcx, r8
0x18000145b  shr     rcx, 1
0x18000145e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001468  mul     rdx
0x18000146b  shr     rdx, 1
0x18000146e  cmp     rcx, rdx
0x180001471  jbe     short loc_180001485
0x180001473  mov     rax, r9
0x180001476  sub     rax, rcx
0x180001479  cmp     r8, rax
0x18000147c  lea     rdi, [rcx+r8]
0x180001480  jbe     short loc_180001485
0x180001482  mov     rdi, r9
0x180001485  lea     rcx, [rdi+1]; Size
0x180001489  test    rcx, rcx
0x18000148c  jz      short loc_18000149D
0x18000148e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001493  mov     rsi, rax
0x180001496  test    rax, rax
0x180001499  jz      short loc_180001508
0x18000149b  jmp     short loc_18000149F
0x18000149d  xor     esi, esi
0x18000149f  jmp     short loc_1800014B5
0x1800014a1  mov     rbx, [rsp+58h+arg_0]
0x1800014a6  mov     r14, [rsp+58h+arg_10]
0x1800014ab  mov     rdi, [rsp+58h+arg_8]
0x1800014b0  mov     rsi, [rsp+58h+arg_18]
0x1800014b5  test    r14, r14
0x1800014b8  jz      short loc_1800014D4
0x1800014ba  cmp     qword ptr [rbx+18h], 10h
0x1800014bf  jb      short loc_1800014C6
0x1800014c1  mov     rdx, [rbx]
0x1800014c4  jmp     short loc_1800014C9
0x1800014c6  mov     rdx, rbx; Src
0x1800014c9  mov     r8, r14; Size
0x1800014cc  mov     rcx, rsi; void *
0x1800014cf  call    memcpy_0
0x1800014d4  cmp     qword ptr [rbx+18h], 10h
0x1800014d9  jb      short loc_1800014E3
0x1800014db  mov     rcx, [rbx]; void *
0x1800014de  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800014e3  lea     rax, [rbx+10h]
0x1800014e7  mov     [rbx], rsi
0x1800014ea  mov     [rbx+18h], rdi
0x1800014ee  cmp     rdi, 10h
0x1800014f2  cmovnb  rbx, rsi
0x1800014f6  mov     [rax], r14
0x1800014f9  mov     byte ptr [rbx+r14], 0
0x1800014fe  add     rsp, 38h
0x180001502  pop     r14
0x180001504  pop     rdi
0x180001505  pop     rsi
0x180001506  pop     rbx
0x180001507  retn
0x180001508  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
