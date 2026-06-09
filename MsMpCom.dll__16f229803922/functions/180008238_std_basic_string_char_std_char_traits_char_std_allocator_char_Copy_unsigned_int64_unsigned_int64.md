# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180008238`
- end: `0x180008328`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800083c0`
- `0x1800084b8`

## callees

- `0x18000126c`
- `0x180001418`
- `0x180001ce6`
- `0x180008238`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800082f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800082f6`

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
0x180008238  mov     [rsp+arg_10], r8
0x18000823d  mov     [rsp+arg_8], rdx
0x180008242  mov     [rsp+arg_0], rcx
0x180008247  push    rbx
0x180008248  push    rsi
0x180008249  push    rdi
0x18000824a  push    r14
0x18000824c  sub     rsp, 28h
0x180008250  mov     r14, r8
0x180008253  mov     rdi, rdx
0x180008256  mov     rbx, rcx
0x180008259  or      rdx, 0Fh
0x18000825d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180008264  cmp     rdx, r9
0x180008267  ja      short loc_18000829D
0x180008269  mov     rdi, rdx
0x18000826c  mov     r8, [rcx+18h]
0x180008270  mov     rcx, r8
0x180008273  shr     rcx, 1
0x180008276  mov     rax, 0AAAAAAAAAAAAAAABh
0x180008280  mul     rdx
0x180008283  shr     rdx, 1
0x180008286  cmp     rcx, rdx
0x180008289  jbe     short loc_18000829D
0x18000828b  mov     rax, r9
0x18000828e  sub     rax, rcx
0x180008291  cmp     r8, rax
0x180008294  lea     rdi, [rcx+r8]
0x180008298  jbe     short loc_18000829D
0x18000829a  mov     rdi, r9
0x18000829d  lea     rcx, [rdi+1]; Size
0x1800082a1  test    rcx, rcx
0x1800082a4  jz      short loc_1800082B5
0x1800082a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800082ab  mov     rsi, rax
0x1800082ae  test    rax, rax
0x1800082b1  jz      short loc_180008321
0x1800082b3  jmp     short loc_1800082B7
0x1800082b5  xor     esi, esi
0x1800082b7  jmp     short loc_1800082CD
0x1800082b9  mov     rbx, [rsp+48h+arg_0]
0x1800082be  mov     r14, [rsp+48h+arg_10]
0x1800082c3  mov     rdi, [rsp+48h+arg_8]
0x1800082c8  mov     rsi, [rsp+48h+arg_18]
0x1800082cd  test    r14, r14
0x1800082d0  jz      short loc_1800082EC
0x1800082d2  cmp     qword ptr [rbx+18h], 10h
0x1800082d7  jb      short loc_1800082DE
0x1800082d9  mov     rdx, [rbx]
0x1800082dc  jmp     short loc_1800082E1
0x1800082de  mov     rdx, rbx; Src
0x1800082e1  mov     r8, r14; Size
0x1800082e4  mov     rcx, rsi; void *
0x1800082e7  call    memcpy_0
0x1800082ec  cmp     qword ptr [rbx+18h], 10h
0x1800082f1  jb      short loc_1800082FC
0x1800082f3  mov     rcx, [rbx]
0x1800082f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800082fc  lea     rax, [rbx+10h]
0x180008300  mov     [rbx], rsi
0x180008303  mov     [rbx+18h], rdi
0x180008307  cmp     rdi, 10h
0x18000830b  cmovnb  rbx, rsi
0x18000830f  mov     [rax], r14
0x180008312  mov     byte ptr [rbx+r14], 0
0x180008317  add     rsp, 28h
0x18000831b  pop     r14
0x18000831d  pop     rdi
0x18000831e  pop     rsi
0x18000831f  pop     rbx
0x180008320  retn
0x180008321  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
