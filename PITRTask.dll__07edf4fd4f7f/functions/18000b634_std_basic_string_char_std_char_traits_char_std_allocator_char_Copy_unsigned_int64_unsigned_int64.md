# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000b634`
- end: `0x18000b724`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000bc10`
- `0x18000bd08`

## callees

- `0x1800014b4`
- `0x180001658`
- `0x180001de6`
- `0x18000b634`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b6f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b6f2`

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
0x18000b634  mov     [rsp+arg_10], r8
0x18000b639  mov     [rsp+arg_8], rdx
0x18000b63e  mov     [rsp+arg_0], rcx
0x18000b643  push    rbx
0x18000b644  push    rsi
0x18000b645  push    rdi
0x18000b646  push    r14
0x18000b648  sub     rsp, 28h
0x18000b64c  mov     r14, r8
0x18000b64f  mov     rdi, rdx
0x18000b652  mov     rbx, rcx
0x18000b655  or      rdx, 0Fh
0x18000b659  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000b660  cmp     rdx, r9
0x18000b663  ja      short loc_18000B699
0x18000b665  mov     rdi, rdx
0x18000b668  mov     r8, [rcx+18h]
0x18000b66c  mov     rcx, r8
0x18000b66f  shr     rcx, 1
0x18000b672  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000b67c  mul     rdx
0x18000b67f  shr     rdx, 1
0x18000b682  cmp     rcx, rdx
0x18000b685  jbe     short loc_18000B699
0x18000b687  mov     rax, r9
0x18000b68a  sub     rax, rcx
0x18000b68d  cmp     r8, rax
0x18000b690  lea     rdi, [rcx+r8]
0x18000b694  jbe     short loc_18000B699
0x18000b696  mov     rdi, r9
0x18000b699  lea     rcx, [rdi+1]; Size
0x18000b69d  test    rcx, rcx
0x18000b6a0  jz      short loc_18000B6B1
0x18000b6a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b6a7  mov     rsi, rax
0x18000b6aa  test    rax, rax
0x18000b6ad  jz      short loc_18000B71D
0x18000b6af  jmp     short loc_18000B6B3
0x18000b6b1  xor     esi, esi
0x18000b6b3  jmp     short loc_18000B6C9
0x18000b6b5  mov     rbx, [rsp+48h+arg_0]
0x18000b6ba  mov     r14, [rsp+48h+arg_10]
0x18000b6bf  mov     rdi, [rsp+48h+arg_8]
0x18000b6c4  mov     rsi, [rsp+48h+arg_18]
0x18000b6c9  test    r14, r14
0x18000b6cc  jz      short loc_18000B6E8
0x18000b6ce  cmp     qword ptr [rbx+18h], 10h
0x18000b6d3  jb      short loc_18000B6DA
0x18000b6d5  mov     rdx, [rbx]
0x18000b6d8  jmp     short loc_18000B6DD
0x18000b6da  mov     rdx, rbx; Src
0x18000b6dd  mov     r8, r14; Size
0x18000b6e0  mov     rcx, rsi; void *
0x18000b6e3  call    memcpy_0
0x18000b6e8  cmp     qword ptr [rbx+18h], 10h
0x18000b6ed  jb      short loc_18000B6F8
0x18000b6ef  mov     rcx, [rbx]
0x18000b6f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b6f8  lea     rax, [rbx+10h]
0x18000b6fc  mov     [rbx], rsi
0x18000b6ff  mov     [rbx+18h], rdi
0x18000b703  cmp     rdi, 10h
0x18000b707  cmovnb  rbx, rsi
0x18000b70b  mov     [rax], r14
0x18000b70e  mov     byte ptr [rbx+r14], 0
0x18000b713  add     rsp, 28h
0x18000b717  pop     r14
0x18000b719  pop     rdi
0x18000b71a  pop     rsi
0x18000b71b  pop     rbx
0x18000b71c  retn
0x18000b71d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
