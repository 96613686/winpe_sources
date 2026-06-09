# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000b300`
- end: `0x18000b41a`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `282`
- prototype: `void __fastcall(__int64, unsigned __int64, void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000aa80`
- `0x18000ae10`
- `0x18000af60`
- `0x18000b0cc`
- `0x18000b270`

## callees

- `0x18000b300`
- `0x18000ed38`
- `0x18000f92c`
- `0x18000fad8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b3e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b3e7`

## pseudocode

```c
void __fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, void *a3)
{
  void *v3; // r14
  unsigned __int64 v4; // rdi
  void **v5; // rbx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void **v9; // rsi
  void *v10; // rdx
  void **v11; // rax
  unsigned __int64 v12; // rcx
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void **v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = (void **)a1;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = a2 | 7;
    v6 = *(_QWORD *)(a1 + 24);
    v7 = v6 >> 1;
    if ( v6 >> 1 > (a2 | 7) / 3 )
    {
      v4 = v7 + v6;
      if ( v6 > 0x7FFFFFFFFFFFFFFELL - v7 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v8 = v4 + 1;
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else if ( v8 > 0x7FFFFFFFFFFFFFFFLL || (v9 = (void **)operator new(2 * v8)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v11 = 0;
      v12 = a2 + 1;
      if ( a2 != -1 && (v12 > 0x7FFFFFFFFFFFFFFFLL || (v11 = (void **)operator new(2 * v12)) == 0) )
        std::_Xbad_alloc();
      v18 = v11;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::wstring::_Tidy(a1, v13, 0);
      throw;
    }
    v5 = (void **)a1;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v10 = v5;
    else
      v10 = *v5;
    std::char_traits<unsigned short>::copy(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete(*v5);
  v5[3] = (void *)7;
  *v5 = v9;
  v5[3] = (void *)v4;
  if ( v4 < 8 )
    v9 = v5;
  v5[2] = v3;
  *((_WORD *)v9 + (_QWORD)v3) = 0;
}

```

## disassembly

```asm
0x18000b300  mov     [rsp+arg_10], r8
0x18000b305  mov     [rsp+arg_8], rdx
0x18000b30a  mov     [rsp+arg_0], rcx
0x18000b30f  push    rbx
0x18000b310  push    rsi
0x18000b311  push    rdi
0x18000b312  push    r14
0x18000b314  push    r15
0x18000b316  sub     rsp, 20h
0x18000b31a  mov     r14, r8
0x18000b31d  mov     rdi, rdx
0x18000b320  mov     rbx, rcx
0x18000b323  mov     rcx, rdx
0x18000b326  or      rcx, 7
0x18000b32a  mov     r10, 7FFFFFFFFFFFFFFEh
0x18000b334  cmp     rcx, r10
0x18000b337  ja      short loc_18000B36D
0x18000b339  mov     rdi, rcx
0x18000b33c  mov     r9, [rbx+18h]
0x18000b340  mov     r8, r9
0x18000b343  shr     r8, 1
0x18000b346  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000b350  mul     rcx
0x18000b353  shr     rdx, 1
0x18000b356  cmp     r8, rdx
0x18000b359  jbe     short loc_18000B36D
0x18000b35b  mov     rax, r10
0x18000b35e  sub     rax, r8
0x18000b361  cmp     r9, rax
0x18000b364  lea     rdi, [r8+r9]
0x18000b368  jbe     short loc_18000B36D
0x18000b36a  mov     rdi, r10
0x18000b36d  lea     rcx, [rdi+1]
0x18000b371  test    rcx, rcx
0x18000b374  jz      short loc_18000B39F
0x18000b376  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000b380  cmp     rcx, rax
0x18000b383  ja      short loc_18000B39A
0x18000b385  add     rcx, rcx; Size
0x18000b388  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b38d  mov     rsi, rax
0x18000b390  test    rax, rax
0x18000b393  jz      short loc_18000B39A
0x18000b395  xor     r15d, r15d
0x18000b398  jmp     short loc_18000B3A5
0x18000b39a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000b39f  xor     r15d, r15d
0x18000b3a2  mov     esi, r15d
0x18000b3a5  jmp     short loc_18000B3BE
0x18000b3a7  xor     r15d, r15d
0x18000b3aa  mov     rbx, [rsp+48h+arg_0]
0x18000b3af  mov     r14, [rsp+48h+arg_10]
0x18000b3b4  mov     rdi, [rsp+48h+arg_8]
0x18000b3b9  mov     rsi, [rsp+48h+arg_18]
0x18000b3be  test    r14, r14
0x18000b3c1  jz      short loc_18000B3DD
0x18000b3c3  cmp     qword ptr [rbx+18h], 8
0x18000b3c8  jb      short loc_18000B3CF
0x18000b3ca  mov     rdx, [rbx]
0x18000b3cd  jmp     short loc_18000B3D2
0x18000b3cf  mov     rdx, rbx
0x18000b3d2  mov     r8, r14
0x18000b3d5  mov     rcx, rsi
0x18000b3d8  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18000b3dd  cmp     qword ptr [rbx+18h], 8
0x18000b3e2  jb      short loc_18000B3ED
0x18000b3e4  mov     rcx, [rbx]
0x18000b3e7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b3ed  mov     qword ptr [rbx+18h], 7
0x18000b3f5  mov     [rbx], rsi
0x18000b3f8  mov     [rbx+18h], rdi
0x18000b3fc  cmp     rdi, 8
0x18000b400  jnb     short loc_18000B405
0x18000b402  mov     rsi, rbx
0x18000b405  mov     [rbx+10h], r14
0x18000b409  mov     [rsi+r14*2], r15w
0x18000b40e  add     rsp, 20h
0x18000b412  pop     r15
0x18000b414  pop     r14
0x18000b416  pop     rdi
0x18000b417  pop     rsi
0x18000b418  pop     rbx
0x18000b419  retn
```
