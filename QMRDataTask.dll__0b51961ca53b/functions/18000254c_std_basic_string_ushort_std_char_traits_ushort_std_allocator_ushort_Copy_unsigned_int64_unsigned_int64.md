# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000254c`
- end: `0x18000265f`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000275c`
- `0x18000285c`
- `0x180002b74`
- `0x180003000`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180001d06`
- `0x18000254c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000262b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000262b`

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
0x18000254c  mov     [rsp+arg_10], r8
0x180002551  mov     [rsp+arg_8], rdx
0x180002556  mov     [rsp+arg_0], rcx
0x18000255b  push    rbx
0x18000255c  push    rsi
0x18000255d  push    rdi
0x18000255e  push    r14
0x180002560  push    r15
0x180002562  sub     rsp, 20h
0x180002566  mov     r15, r8
0x180002569  mov     rdi, rdx
0x18000256c  mov     rbx, rcx
0x18000256f  or      rdx, 7
0x180002573  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000257d  cmp     rdx, r9
0x180002580  ja      short loc_1800025B6
0x180002582  mov     rdi, rdx
0x180002585  mov     r8, [rcx+18h]
0x180002589  mov     rcx, r8
0x18000258c  shr     rcx, 1
0x18000258f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180002599  mul     rdx
0x18000259c  shr     rdx, 1
0x18000259f  cmp     rcx, rdx
0x1800025a2  jbe     short loc_1800025B6
0x1800025a4  mov     rax, r9
0x1800025a7  sub     rax, rcx
0x1800025aa  cmp     r8, rax
0x1800025ad  lea     rdi, [rcx+r8]
0x1800025b1  jbe     short loc_1800025B6
0x1800025b3  mov     rdi, r9
0x1800025b6  lea     rcx, [rdi+1]
0x1800025ba  xor     esi, esi
0x1800025bc  test    rcx, rcx
0x1800025bf  jz      short loc_1800025E6
0x1800025c1  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800025cb  cmp     rcx, rax
0x1800025ce  ja      loc_180002658
0x1800025d4  add     rcx, rcx; Size
0x1800025d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025dc  mov     r14, rax
0x1800025df  test    rax, rax
0x1800025e2  jz      short loc_180002658
0x1800025e4  jmp     short loc_1800025E9
0x1800025e6  mov     r14, rsi
0x1800025e9  jmp     short loc_180002601
0x1800025eb  xor     esi, esi
0x1800025ed  mov     rbx, [rsp+48h+arg_0]
0x1800025f2  mov     r15, [rsp+48h+arg_10]
0x1800025f7  mov     rdi, [rsp+48h+arg_8]
0x1800025fc  mov     r14, [rsp+48h+arg_18]
0x180002601  test    r15, r15
0x180002604  jz      short loc_180002621
0x180002606  cmp     qword ptr [rbx+18h], 8
0x18000260b  jb      short loc_180002612
0x18000260d  mov     rdx, [rbx]
0x180002610  jmp     short loc_180002615
0x180002612  mov     rdx, rbx; Src
0x180002615  lea     r8, [r15+r15]; Size
0x180002619  mov     rcx, r14; void *
0x18000261c  call    memcpy_0
0x180002621  cmp     qword ptr [rbx+18h], 8
0x180002626  jb      short loc_180002631
0x180002628  mov     rcx, [rbx]
0x18000262b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002631  lea     rax, [rbx+10h]
0x180002635  mov     [rbx], r14
0x180002638  mov     [rbx+18h], rdi
0x18000263c  cmp     rdi, 8
0x180002640  cmovnb  rbx, r14
0x180002644  mov     [rax], r15
0x180002647  mov     [rbx+r15*2], si
0x18000264c  add     rsp, 20h
0x180002650  pop     r15
0x180002652  pop     r14
0x180002654  pop     rdi
0x180002655  pop     rsi
0x180002656  pop     rbx
0x180002657  retn
0x180002658  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
