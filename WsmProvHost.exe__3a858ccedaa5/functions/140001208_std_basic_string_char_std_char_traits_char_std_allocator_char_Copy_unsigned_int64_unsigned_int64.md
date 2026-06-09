# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140001208`
- end: `0x1400012ff`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140001418`
- `0x140001510`

## callees

- `0x140001208`
- `0x140001368`
- `0x140001eb6`
- `0x140002d50`
- `0x140002d64`

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
  __int64 v12; // rax
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
      v9 = (void *)operator new(v4 + 1);
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
      v18 = (void *)v12;
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
0x140001208  mov     rax, rsp
0x14000120b  mov     [rax+18h], r8
0x14000120f  mov     [rax+10h], rdx
0x140001213  mov     [rax+8], rcx
0x140001217  push    rbx
0x140001218  push    rsi
0x140001219  push    rdi
0x14000121a  push    r14
0x14000121c  sub     rsp, 38h
0x140001220  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x140001228  mov     r14, r8
0x14000122b  mov     rdi, rdx
0x14000122e  mov     rbx, rcx
0x140001231  or      rdx, 0Fh
0x140001235  mov     r9, 0FFFFFFFFFFFFFFFEh
0x14000123c  cmp     rdx, r9
0x14000123f  ja      short loc_140001275
0x140001241  mov     rdi, rdx
0x140001244  mov     r8, [rcx+18h]
0x140001248  mov     rcx, r8
0x14000124b  shr     rcx, 1
0x14000124e  mov     rax, 0AAAAAAAAAAAAAAABh
0x140001258  mul     rdx
0x14000125b  shr     rdx, 1
0x14000125e  cmp     rcx, rdx
0x140001261  jbe     short loc_140001275
0x140001263  mov     rax, r9
0x140001266  sub     rax, rcx
0x140001269  cmp     r8, rax
0x14000126c  lea     rdi, [rcx+r8]
0x140001270  jbe     short loc_140001275
0x140001272  mov     rdi, r9
0x140001275  lea     rcx, [rdi+1]; unsigned __int64
0x140001279  test    rcx, rcx
0x14000127c  jz      short loc_14000128D
0x14000127e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001283  mov     rsi, rax
0x140001286  test    rax, rax
0x140001289  jz      short loc_1400012F8
0x14000128b  jmp     short loc_14000128F
0x14000128d  xor     esi, esi
0x14000128f  jmp     short loc_1400012A5
0x140001291  mov     rbx, [rsp+58h+arg_0]
0x140001296  mov     r14, [rsp+58h+arg_10]
0x14000129b  mov     rdi, [rsp+58h+arg_8]
0x1400012a0  mov     rsi, [rsp+58h+arg_18]
0x1400012a5  test    r14, r14
0x1400012a8  jz      short loc_1400012C4
0x1400012aa  cmp     qword ptr [rbx+18h], 10h
0x1400012af  jb      short loc_1400012B6
0x1400012b1  mov     rdx, [rbx]
0x1400012b4  jmp     short loc_1400012B9
0x1400012b6  mov     rdx, rbx; Src
0x1400012b9  mov     r8, r14; Size
0x1400012bc  mov     rcx, rsi; void *
0x1400012bf  call    memcpy_0
0x1400012c4  cmp     qword ptr [rbx+18h], 10h
0x1400012c9  jb      short loc_1400012D3
0x1400012cb  mov     rcx, [rbx]; void *
0x1400012ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400012d3  lea     rax, [rbx+10h]
0x1400012d7  mov     [rbx], rsi
0x1400012da  mov     [rbx+18h], rdi
0x1400012de  cmp     rdi, 10h
0x1400012e2  cmovnb  rbx, rsi
0x1400012e6  mov     [rax], r14
0x1400012e9  mov     byte ptr [rbx+r14], 0
0x1400012ee  add     rsp, 38h
0x1400012f2  pop     r14
0x1400012f4  pop     rdi
0x1400012f5  pop     rsi
0x1400012f6  pop     rbx
0x1400012f7  retn
0x1400012f8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
