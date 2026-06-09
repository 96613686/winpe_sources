# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800056dc`
- end: `0x1800057cc`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005890`
- `0x180005988`

## callees

- `0x1800015c0`
- `0x180001768`
- `0x180001ee6`
- `0x1800056dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000579a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000579a`

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
0x1800056dc  mov     [rsp+arg_10], r8
0x1800056e1  mov     [rsp+arg_8], rdx
0x1800056e6  mov     [rsp+arg_0], rcx
0x1800056eb  push    rbx
0x1800056ec  push    rsi
0x1800056ed  push    rdi
0x1800056ee  push    r14
0x1800056f0  sub     rsp, 28h
0x1800056f4  mov     r14, r8
0x1800056f7  mov     rdi, rdx
0x1800056fa  mov     rbx, rcx
0x1800056fd  or      rdx, 0Fh
0x180005701  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180005708  cmp     rdx, r9
0x18000570b  ja      short loc_180005741
0x18000570d  mov     rdi, rdx
0x180005710  mov     r8, [rcx+18h]
0x180005714  mov     rcx, r8
0x180005717  shr     rcx, 1
0x18000571a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180005724  mul     rdx
0x180005727  shr     rdx, 1
0x18000572a  cmp     rcx, rdx
0x18000572d  jbe     short loc_180005741
0x18000572f  mov     rax, r9
0x180005732  sub     rax, rcx
0x180005735  cmp     r8, rax
0x180005738  lea     rdi, [rcx+r8]
0x18000573c  jbe     short loc_180005741
0x18000573e  mov     rdi, r9
0x180005741  lea     rcx, [rdi+1]; Size
0x180005745  test    rcx, rcx
0x180005748  jz      short loc_180005759
0x18000574a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000574f  mov     rsi, rax
0x180005752  test    rax, rax
0x180005755  jz      short loc_1800057C5
0x180005757  jmp     short loc_18000575B
0x180005759  xor     esi, esi
0x18000575b  jmp     short loc_180005771
0x18000575d  mov     rbx, [rsp+48h+arg_0]
0x180005762  mov     r14, [rsp+48h+arg_10]
0x180005767  mov     rdi, [rsp+48h+arg_8]
0x18000576c  mov     rsi, [rsp+48h+arg_18]
0x180005771  test    r14, r14
0x180005774  jz      short loc_180005790
0x180005776  cmp     qword ptr [rbx+18h], 10h
0x18000577b  jb      short loc_180005782
0x18000577d  mov     rdx, [rbx]
0x180005780  jmp     short loc_180005785
0x180005782  mov     rdx, rbx; Src
0x180005785  mov     r8, r14; Size
0x180005788  mov     rcx, rsi; void *
0x18000578b  call    memcpy_0
0x180005790  cmp     qword ptr [rbx+18h], 10h
0x180005795  jb      short loc_1800057A0
0x180005797  mov     rcx, [rbx]
0x18000579a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057a0  lea     rax, [rbx+10h]
0x1800057a4  mov     [rbx], rsi
0x1800057a7  mov     [rbx+18h], rdi
0x1800057ab  cmp     rdi, 10h
0x1800057af  cmovnb  rbx, rsi
0x1800057b3  mov     [rax], r14
0x1800057b6  mov     byte ptr [rbx+r14], 0
0x1800057bb  add     rsp, 28h
0x1800057bf  pop     r14
0x1800057c1  pop     rdi
0x1800057c2  pop     rsi
0x1800057c3  pop     rbx
0x1800057c4  retn
0x1800057c5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
