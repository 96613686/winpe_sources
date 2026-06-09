# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800065a4`
- end: `0x180006694`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006ae0`
- `0x180006bd8`

## callees

- `0x180001e88`
- `0x180002038`
- `0x1800027a6`
- `0x1800065a4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006662`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006662`

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
0x1800065a4  mov     [rsp+arg_10], r8
0x1800065a9  mov     [rsp+arg_8], rdx
0x1800065ae  mov     [rsp+arg_0], rcx
0x1800065b3  push    rbx
0x1800065b4  push    rsi
0x1800065b5  push    rdi
0x1800065b6  push    r14
0x1800065b8  sub     rsp, 28h
0x1800065bc  mov     r14, r8
0x1800065bf  mov     rdi, rdx
0x1800065c2  mov     rbx, rcx
0x1800065c5  or      rdx, 0Fh
0x1800065c9  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800065d0  cmp     rdx, r9
0x1800065d3  ja      short loc_180006609
0x1800065d5  mov     rdi, rdx
0x1800065d8  mov     r8, [rcx+18h]
0x1800065dc  mov     rcx, r8
0x1800065df  shr     rcx, 1
0x1800065e2  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800065ec  mul     rdx
0x1800065ef  shr     rdx, 1
0x1800065f2  cmp     rcx, rdx
0x1800065f5  jbe     short loc_180006609
0x1800065f7  mov     rax, r9
0x1800065fa  sub     rax, rcx
0x1800065fd  cmp     r8, rax
0x180006600  lea     rdi, [rcx+r8]
0x180006604  jbe     short loc_180006609
0x180006606  mov     rdi, r9
0x180006609  lea     rcx, [rdi+1]; Size
0x18000660d  test    rcx, rcx
0x180006610  jz      short loc_180006621
0x180006612  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006617  mov     rsi, rax
0x18000661a  test    rax, rax
0x18000661d  jz      short loc_18000668D
0x18000661f  jmp     short loc_180006623
0x180006621  xor     esi, esi
0x180006623  jmp     short loc_180006639
0x180006625  mov     rbx, [rsp+48h+arg_0]
0x18000662a  mov     r14, [rsp+48h+arg_10]
0x18000662f  mov     rdi, [rsp+48h+arg_8]
0x180006634  mov     rsi, [rsp+48h+arg_18]
0x180006639  test    r14, r14
0x18000663c  jz      short loc_180006658
0x18000663e  cmp     qword ptr [rbx+18h], 10h
0x180006643  jb      short loc_18000664A
0x180006645  mov     rdx, [rbx]
0x180006648  jmp     short loc_18000664D
0x18000664a  mov     rdx, rbx; Src
0x18000664d  mov     r8, r14; Size
0x180006650  mov     rcx, rsi; void *
0x180006653  call    memcpy_0
0x180006658  cmp     qword ptr [rbx+18h], 10h
0x18000665d  jb      short loc_180006668
0x18000665f  mov     rcx, [rbx]
0x180006662  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006668  lea     rax, [rbx+10h]
0x18000666c  mov     [rbx], rsi
0x18000666f  mov     [rbx+18h], rdi
0x180006673  cmp     rdi, 10h
0x180006677  cmovnb  rbx, rsi
0x18000667b  mov     [rax], r14
0x18000667e  mov     byte ptr [rbx+r14], 0
0x180006683  add     rsp, 28h
0x180006687  pop     r14
0x180006689  pop     rdi
0x18000668a  pop     rsi
0x18000668b  pop     rbx
0x18000668c  retn
0x18000668d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
