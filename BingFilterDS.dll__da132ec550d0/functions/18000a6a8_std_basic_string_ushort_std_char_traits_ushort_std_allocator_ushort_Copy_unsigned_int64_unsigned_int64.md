# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000a6a8`
- end: `0x18000a7bb`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009b54`
- `0x18000ad28`
- `0x18000ae28`
- `0x18000afa0`

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x180002766`
- `0x18000a6a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a787`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a787`

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
0x18000a6a8  mov     [rsp+arg_10], r8
0x18000a6ad  mov     [rsp+arg_8], rdx
0x18000a6b2  mov     [rsp+arg_0], rcx
0x18000a6b7  push    rbx
0x18000a6b8  push    rsi
0x18000a6b9  push    rdi
0x18000a6ba  push    r14
0x18000a6bc  push    r15
0x18000a6be  sub     rsp, 20h
0x18000a6c2  mov     r15, r8
0x18000a6c5  mov     rdi, rdx
0x18000a6c8  mov     rbx, rcx
0x18000a6cb  or      rdx, 7
0x18000a6cf  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000a6d9  cmp     rdx, r9
0x18000a6dc  ja      short loc_18000A712
0x18000a6de  mov     rdi, rdx
0x18000a6e1  mov     r8, [rcx+18h]
0x18000a6e5  mov     rcx, r8
0x18000a6e8  shr     rcx, 1
0x18000a6eb  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000a6f5  mul     rdx
0x18000a6f8  shr     rdx, 1
0x18000a6fb  cmp     rcx, rdx
0x18000a6fe  jbe     short loc_18000A712
0x18000a700  mov     rax, r9
0x18000a703  sub     rax, rcx
0x18000a706  cmp     r8, rax
0x18000a709  lea     rdi, [rcx+r8]
0x18000a70d  jbe     short loc_18000A712
0x18000a70f  mov     rdi, r9
0x18000a712  lea     rcx, [rdi+1]
0x18000a716  xor     esi, esi
0x18000a718  test    rcx, rcx
0x18000a71b  jz      short loc_18000A742
0x18000a71d  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a727  cmp     rcx, rax
0x18000a72a  ja      loc_18000A7B4
0x18000a730  add     rcx, rcx; Size
0x18000a733  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a738  mov     r14, rax
0x18000a73b  test    rax, rax
0x18000a73e  jz      short loc_18000A7B4
0x18000a740  jmp     short loc_18000A745
0x18000a742  mov     r14, rsi
0x18000a745  jmp     short loc_18000A75D
0x18000a747  xor     esi, esi
0x18000a749  mov     rbx, [rsp+48h+arg_0]
0x18000a74e  mov     r15, [rsp+48h+arg_10]
0x18000a753  mov     rdi, [rsp+48h+arg_8]
0x18000a758  mov     r14, [rsp+48h+arg_18]
0x18000a75d  test    r15, r15
0x18000a760  jz      short loc_18000A77D
0x18000a762  cmp     qword ptr [rbx+18h], 8
0x18000a767  jb      short loc_18000A76E
0x18000a769  mov     rdx, [rbx]
0x18000a76c  jmp     short loc_18000A771
0x18000a76e  mov     rdx, rbx; Src
0x18000a771  lea     r8, [r15+r15]; Size
0x18000a775  mov     rcx, r14; void *
0x18000a778  call    memcpy_0
0x18000a77d  cmp     qword ptr [rbx+18h], 8
0x18000a782  jb      short loc_18000A78D
0x18000a784  mov     rcx, [rbx]
0x18000a787  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a78d  lea     rax, [rbx+10h]
0x18000a791  mov     [rbx], r14
0x18000a794  mov     [rbx+18h], rdi
0x18000a798  cmp     rdi, 8
0x18000a79c  cmovnb  rbx, r14
0x18000a7a0  mov     [rax], r15
0x18000a7a3  mov     [rbx+r15*2], si
0x18000a7a8  add     rsp, 20h
0x18000a7ac  pop     r15
0x18000a7ae  pop     r14
0x18000a7b0  pop     rdi
0x18000a7b1  pop     rsi
0x18000a7b2  pop     rbx
0x18000a7b3  retn
0x18000a7b4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
