# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006314`
- end: `0x140006404`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000649c`
- `0x140006594`

## callees

- `0x1400014fc`
- `0x140001758`
- `0x1400020c6`
- `0x140006314`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400063d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400063d2`

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
0x140006314  mov     [rsp+arg_10], r8
0x140006319  mov     [rsp+arg_8], rdx
0x14000631e  mov     [rsp+arg_0], rcx
0x140006323  push    rbx
0x140006324  push    rsi
0x140006325  push    rdi
0x140006326  push    r14
0x140006328  sub     rsp, 28h
0x14000632c  mov     r14, r8
0x14000632f  mov     rdi, rdx
0x140006332  mov     rbx, rcx
0x140006335  or      rdx, 0Fh
0x140006339  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140006340  cmp     rdx, r9
0x140006343  ja      short loc_140006379
0x140006345  mov     rdi, rdx
0x140006348  mov     r8, [rcx+18h]
0x14000634c  mov     rcx, r8
0x14000634f  shr     rcx, 1
0x140006352  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000635c  mul     rdx
0x14000635f  shr     rdx, 1
0x140006362  cmp     rcx, rdx
0x140006365  jbe     short loc_140006379
0x140006367  mov     rax, r9
0x14000636a  sub     rax, rcx
0x14000636d  cmp     r8, rax
0x140006370  lea     rdi, [rcx+r8]
0x140006374  jbe     short loc_140006379
0x140006376  mov     rdi, r9
0x140006379  lea     rcx, [rdi+1]; Size
0x14000637d  test    rcx, rcx
0x140006380  jz      short loc_140006391
0x140006382  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006387  mov     rsi, rax
0x14000638a  test    rax, rax
0x14000638d  jz      short loc_1400063FD
0x14000638f  jmp     short loc_140006393
0x140006391  xor     esi, esi
0x140006393  jmp     short loc_1400063A9
0x140006395  mov     rbx, [rsp+48h+arg_0]
0x14000639a  mov     r14, [rsp+48h+arg_10]
0x14000639f  mov     rdi, [rsp+48h+arg_8]
0x1400063a4  mov     rsi, [rsp+48h+arg_18]
0x1400063a9  test    r14, r14
0x1400063ac  jz      short loc_1400063C8
0x1400063ae  cmp     qword ptr [rbx+18h], 10h
0x1400063b3  jb      short loc_1400063BA
0x1400063b5  mov     rdx, [rbx]
0x1400063b8  jmp     short loc_1400063BD
0x1400063ba  mov     rdx, rbx; Src
0x1400063bd  mov     r8, r14; Size
0x1400063c0  mov     rcx, rsi; void *
0x1400063c3  call    memcpy_0
0x1400063c8  cmp     qword ptr [rbx+18h], 10h
0x1400063cd  jb      short loc_1400063D8
0x1400063cf  mov     rcx, [rbx]
0x1400063d2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400063d8  lea     rax, [rbx+10h]
0x1400063dc  mov     [rbx], rsi
0x1400063df  mov     [rbx+18h], rdi
0x1400063e3  cmp     rdi, 10h
0x1400063e7  cmovnb  rbx, rsi
0x1400063eb  mov     [rax], r14
0x1400063ee  mov     byte ptr [rbx+r14], 0
0x1400063f3  add     rsp, 28h
0x1400063f7  pop     r14
0x1400063f9  pop     rdi
0x1400063fa  pop     rsi
0x1400063fb  pop     rbx
0x1400063fc  retn
0x1400063fd  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
