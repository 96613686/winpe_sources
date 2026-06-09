# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000b72c`
- end: `0x18000b83f`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003150`

## callees

- `0x1800014b4`
- `0x180001658`
- `0x180001de6`
- `0x18000b72c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b80b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b80b`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b72c  mov     [rsp+arg_10], r8
0x18000b731  mov     [rsp+arg_8], rdx
0x18000b736  mov     [rsp+arg_0], rcx
0x18000b73b  push    rbx
0x18000b73c  push    rsi
0x18000b73d  push    rdi
0x18000b73e  push    r14
0x18000b740  push    r15
0x18000b742  sub     rsp, 20h
0x18000b746  mov     r15, r8
0x18000b749  mov     rdi, rdx
0x18000b74c  mov     rbx, rcx
0x18000b74f  or      rdx, 7
0x18000b753  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000b75d  cmp     rdx, r9
0x18000b760  ja      short loc_18000B796
0x18000b762  mov     rdi, rdx
0x18000b765  mov     r8, [rcx+18h]
0x18000b769  mov     rcx, r8
0x18000b76c  shr     rcx, 1
0x18000b76f  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000b779  mul     rdx
0x18000b77c  shr     rdx, 1
0x18000b77f  cmp     rcx, rdx
0x18000b782  jbe     short loc_18000B796
0x18000b784  mov     rax, r9
0x18000b787  sub     rax, rcx
0x18000b78a  cmp     r8, rax
0x18000b78d  lea     rdi, [rcx+r8]
0x18000b791  jbe     short loc_18000B796
0x18000b793  mov     rdi, r9
0x18000b796  lea     rcx, [rdi+1]
0x18000b79a  xor     esi, esi
0x18000b79c  test    rcx, rcx
0x18000b79f  jz      short loc_18000B7C6
0x18000b7a1  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000b7ab  cmp     rcx, rax
0x18000b7ae  ja      loc_18000B838
0x18000b7b4  add     rcx, rcx; Size
0x18000b7b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b7bc  mov     r14, rax
0x18000b7bf  test    rax, rax
0x18000b7c2  jz      short loc_18000B838
0x18000b7c4  jmp     short loc_18000B7C9
0x18000b7c6  mov     r14, rsi
0x18000b7c9  jmp     short loc_18000B7E1
0x18000b7cb  xor     esi, esi
0x18000b7cd  mov     rbx, [rsp+48h+arg_0]
0x18000b7d2  mov     r15, [rsp+48h+arg_10]
0x18000b7d7  mov     rdi, [rsp+48h+arg_8]
0x18000b7dc  mov     r14, [rsp+48h+arg_18]
0x18000b7e1  test    r15, r15
0x18000b7e4  jz      short loc_18000B801
0x18000b7e6  cmp     qword ptr [rbx+18h], 8
0x18000b7eb  jb      short loc_18000B7F2
0x18000b7ed  mov     rdx, [rbx]
0x18000b7f0  jmp     short loc_18000B7F5
0x18000b7f2  mov     rdx, rbx; Src
0x18000b7f5  lea     r8, [r15+r15]; Size
0x18000b7f9  mov     rcx, r14; void *
0x18000b7fc  call    memcpy_0
0x18000b801  cmp     qword ptr [rbx+18h], 8
0x18000b806  jb      short loc_18000B811
0x18000b808  mov     rcx, [rbx]
0x18000b80b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b811  lea     rax, [rbx+10h]
0x18000b815  mov     [rbx], r14
0x18000b818  mov     [rbx+18h], rdi
0x18000b81c  cmp     rdi, 8
0x18000b820  cmovnb  rbx, r14
0x18000b824  mov     [rax], r15
0x18000b827  mov     [rbx+r15*2], si
0x18000b82c  add     rsp, 20h
0x18000b830  pop     r15
0x18000b832  pop     r14
0x18000b834  pop     rdi
0x18000b835  pop     rsi
0x18000b836  pop     rbx
0x18000b837  retn
0x18000b838  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
