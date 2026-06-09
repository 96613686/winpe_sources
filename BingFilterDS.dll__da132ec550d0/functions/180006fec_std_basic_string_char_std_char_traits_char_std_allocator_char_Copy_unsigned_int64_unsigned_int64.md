# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006fec`
- end: `0x1800070dc`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800071a0`
- `0x180007298`

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x180002766`
- `0x180006fec`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800070aa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800070aa`

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
0x180006fec  mov     [rsp+arg_10], r8
0x180006ff1  mov     [rsp+arg_8], rdx
0x180006ff6  mov     [rsp+arg_0], rcx
0x180006ffb  push    rbx
0x180006ffc  push    rsi
0x180006ffd  push    rdi
0x180006ffe  push    r14
0x180007000  sub     rsp, 28h
0x180007004  mov     r14, r8
0x180007007  mov     rdi, rdx
0x18000700a  mov     rbx, rcx
0x18000700d  or      rdx, 0Fh
0x180007011  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180007018  cmp     rdx, r9
0x18000701b  ja      short loc_180007051
0x18000701d  mov     rdi, rdx
0x180007020  mov     r8, [rcx+18h]
0x180007024  mov     rcx, r8
0x180007027  shr     rcx, 1
0x18000702a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007034  mul     rdx
0x180007037  shr     rdx, 1
0x18000703a  cmp     rcx, rdx
0x18000703d  jbe     short loc_180007051
0x18000703f  mov     rax, r9
0x180007042  sub     rax, rcx
0x180007045  cmp     r8, rax
0x180007048  lea     rdi, [rcx+r8]
0x18000704c  jbe     short loc_180007051
0x18000704e  mov     rdi, r9
0x180007051  lea     rcx, [rdi+1]; Size
0x180007055  test    rcx, rcx
0x180007058  jz      short loc_180007069
0x18000705a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000705f  mov     rsi, rax
0x180007062  test    rax, rax
0x180007065  jz      short loc_1800070D5
0x180007067  jmp     short loc_18000706B
0x180007069  xor     esi, esi
0x18000706b  jmp     short loc_180007081
0x18000706d  mov     rbx, [rsp+48h+arg_0]
0x180007072  mov     r14, [rsp+48h+arg_10]
0x180007077  mov     rdi, [rsp+48h+arg_8]
0x18000707c  mov     rsi, [rsp+48h+arg_18]
0x180007081  test    r14, r14
0x180007084  jz      short loc_1800070A0
0x180007086  cmp     qword ptr [rbx+18h], 10h
0x18000708b  jb      short loc_180007092
0x18000708d  mov     rdx, [rbx]
0x180007090  jmp     short loc_180007095
0x180007092  mov     rdx, rbx; Src
0x180007095  mov     r8, r14; Size
0x180007098  mov     rcx, rsi; void *
0x18000709b  call    memcpy_0
0x1800070a0  cmp     qword ptr [rbx+18h], 10h
0x1800070a5  jb      short loc_1800070B0
0x1800070a7  mov     rcx, [rbx]
0x1800070aa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800070b0  lea     rax, [rbx+10h]
0x1800070b4  mov     [rbx], rsi
0x1800070b7  mov     [rbx+18h], rdi
0x1800070bb  cmp     rdi, 10h
0x1800070bf  cmovnb  rbx, rsi
0x1800070c3  mov     [rax], r14
0x1800070c6  mov     byte ptr [rbx+r14], 0
0x1800070cb  add     rsp, 28h
0x1800070cf  pop     r14
0x1800070d1  pop     rdi
0x1800070d2  pop     rsi
0x1800070d3  pop     rbx
0x1800070d4  retn
0x1800070d5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
