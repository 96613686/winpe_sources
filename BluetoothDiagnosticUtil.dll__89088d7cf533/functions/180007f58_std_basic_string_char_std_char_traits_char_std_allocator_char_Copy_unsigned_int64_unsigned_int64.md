# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180007f58`
- end: `0x180008052`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003480`

## callees

- `0x180001184`
- `0x180007f58`
- `0x180009c46`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007fd3`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007fd3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008020`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008020`

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
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( v9 )
        goto LABEL_31;
      std::_Xbad_alloc();
    }
    v9 = 0;
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
LABEL_31:
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
0x180007f58  mov     [rsp+arg_10], r8
0x180007f5d  mov     [rsp+arg_8], rdx
0x180007f62  mov     [rsp+arg_0], rcx
0x180007f67  push    rbx
0x180007f68  push    rsi
0x180007f69  push    rdi
0x180007f6a  push    r14
0x180007f6c  sub     rsp, 28h
0x180007f70  mov     r14, r8
0x180007f73  mov     rdi, rdx
0x180007f76  mov     rbx, rcx
0x180007f79  or      rdx, 0Fh
0x180007f7d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180007f84  cmp     rdx, r9
0x180007f87  ja      short loc_180007FBD
0x180007f89  mov     rdi, rdx
0x180007f8c  mov     r8, [rcx+18h]
0x180007f90  mov     rcx, r8
0x180007f93  shr     rcx, 1
0x180007f96  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007fa0  mul     rdx
0x180007fa3  shr     rdx, 1
0x180007fa6  cmp     rcx, rdx
0x180007fa9  jbe     short loc_180007FBD
0x180007fab  mov     rax, r9
0x180007fae  sub     rax, rcx
0x180007fb1  cmp     r8, rax
0x180007fb4  lea     rdi, [rcx+r8]
0x180007fb8  jbe     short loc_180007FBD
0x180007fba  mov     rdi, r9
0x180007fbd  lea     rcx, [rdi+1]; Size
0x180007fc1  test    rcx, rcx
0x180007fc4  jz      short loc_180007FDF
0x180007fc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007fcb  mov     rsi, rax
0x180007fce  test    rax, rax
0x180007fd1  jnz     short loc_180007FE1
0x180007fd3  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007fda  nop     dword ptr [rax+rax+00h]
0x180007fdf  xor     esi, esi
0x180007fe1  jmp     short loc_180007FF7
0x180007fe3  mov     rbx, [rsp+48h+arg_0]
0x180007fe8  mov     r14, [rsp+48h+arg_10]
0x180007fed  mov     rdi, [rsp+48h+arg_8]
0x180007ff2  mov     rsi, [rsp+48h+arg_18]
0x180007ff7  test    r14, r14
0x180007ffa  jz      short loc_180008016
0x180007ffc  cmp     qword ptr [rbx+18h], 10h
0x180008001  jb      short loc_180008008
0x180008003  mov     rdx, [rbx]
0x180008006  jmp     short loc_18000800B
0x180008008  mov     rdx, rbx; Src
0x18000800b  mov     r8, r14; Size
0x18000800e  mov     rcx, rsi; void *
0x180008011  call    memcpy_0
0x180008016  cmp     qword ptr [rbx+18h], 10h
0x18000801b  jb      short loc_18000802C
0x18000801d  mov     rcx, [rbx]
0x180008020  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008027  nop     dword ptr [rax+rax+00h]
0x18000802c  lea     rax, [rbx+10h]
0x180008030  mov     [rbx], rsi
0x180008033  mov     [rbx+18h], rdi
0x180008037  cmp     rdi, 10h
0x18000803b  cmovnb  rbx, rsi
0x18000803f  mov     [rax], r14
0x180008042  mov     byte ptr [rbx+r14], 0
0x180008047  add     rsp, 28h
0x18000804b  pop     r14
0x18000804d  pop     rdi
0x18000804e  pop     rsi
0x18000804f  pop     rbx
0x180008050  retn
```
