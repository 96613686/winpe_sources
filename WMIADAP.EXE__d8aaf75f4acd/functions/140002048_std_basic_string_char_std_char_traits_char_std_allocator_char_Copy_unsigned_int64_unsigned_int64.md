# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140002048`
- end: `0x14000213f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140002258`
- `0x140002350`

## callees

- `0x140002048`
- `0x1400021a8`
- `0x1400027e1`
- `0x140002abc`
- `0x140002acc`

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
0x140002048  mov     rax, rsp
0x14000204b  mov     [rax+18h], r8
0x14000204f  mov     [rax+10h], rdx
0x140002053  mov     [rax+8], rcx
0x140002057  push    rbx
0x140002058  push    rsi
0x140002059  push    rdi
0x14000205a  push    r14
0x14000205c  sub     rsp, 38h
0x140002060  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x140002068  mov     r14, r8
0x14000206b  mov     rdi, rdx
0x14000206e  mov     rbx, rcx
0x140002071  or      rdx, 0Fh
0x140002075  mov     r9, 0FFFFFFFFFFFFFFFEh
0x14000207c  cmp     rdx, r9
0x14000207f  ja      short loc_1400020B5
0x140002081  mov     rdi, rdx
0x140002084  mov     r8, [rcx+18h]
0x140002088  mov     rcx, r8
0x14000208b  shr     rcx, 1
0x14000208e  mov     rax, 0AAAAAAAAAAAAAAABh
0x140002098  mul     rdx
0x14000209b  shr     rdx, 1
0x14000209e  cmp     rcx, rdx
0x1400020a1  jbe     short loc_1400020B5
0x1400020a3  mov     rax, r9
0x1400020a6  sub     rax, rcx
0x1400020a9  cmp     r8, rax
0x1400020ac  lea     rdi, [rcx+r8]
0x1400020b0  jbe     short loc_1400020B5
0x1400020b2  mov     rdi, r9
0x1400020b5  lea     rcx, [rdi+1]; unsigned __int64
0x1400020b9  test    rcx, rcx
0x1400020bc  jz      short loc_1400020CD
0x1400020be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400020c3  mov     rsi, rax
0x1400020c6  test    rax, rax
0x1400020c9  jz      short loc_140002138
0x1400020cb  jmp     short loc_1400020CF
0x1400020cd  xor     esi, esi
0x1400020cf  jmp     short loc_1400020E5
0x1400020d1  mov     rbx, [rsp+58h+arg_0]
0x1400020d6  mov     r14, [rsp+58h+arg_10]
0x1400020db  mov     rdi, [rsp+58h+arg_8]
0x1400020e0  mov     rsi, [rsp+58h+arg_18]
0x1400020e5  test    r14, r14
0x1400020e8  jz      short loc_140002104
0x1400020ea  cmp     qword ptr [rbx+18h], 10h
0x1400020ef  jb      short loc_1400020F6
0x1400020f1  mov     rdx, [rbx]
0x1400020f4  jmp     short loc_1400020F9
0x1400020f6  mov     rdx, rbx; Src
0x1400020f9  mov     r8, r14; Size
0x1400020fc  mov     rcx, rsi; void *
0x1400020ff  call    memcpy_0
0x140002104  cmp     qword ptr [rbx+18h], 10h
0x140002109  jb      short loc_140002113
0x14000210b  mov     rcx, [rbx]; void *
0x14000210e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002113  lea     rax, [rbx+10h]
0x140002117  mov     [rbx], rsi
0x14000211a  mov     [rbx+18h], rdi
0x14000211e  cmp     rdi, 10h
0x140002122  cmovnb  rbx, rsi
0x140002126  mov     [rax], r14
0x140002129  mov     byte ptr [rbx+r14], 0
0x14000212e  add     rsp, 38h
0x140002132  pop     r14
0x140002134  pop     rdi
0x140002135  pop     rsi
0x140002136  pop     rbx
0x140002137  retn
0x140002138  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
