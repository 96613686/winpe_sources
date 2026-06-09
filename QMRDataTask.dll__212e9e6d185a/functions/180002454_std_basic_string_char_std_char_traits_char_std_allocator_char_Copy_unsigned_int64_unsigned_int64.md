# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180002454`
- end: `0x180002544`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000297c`
- `0x180002a74`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180001d06`
- `0x180002454`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002512`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002512`

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
0x180002454  mov     [rsp+arg_10], r8
0x180002459  mov     [rsp+arg_8], rdx
0x18000245e  mov     [rsp+arg_0], rcx
0x180002463  push    rbx
0x180002464  push    rsi
0x180002465  push    rdi
0x180002466  push    r14
0x180002468  sub     rsp, 28h
0x18000246c  mov     r14, r8
0x18000246f  mov     rdi, rdx
0x180002472  mov     rbx, rcx
0x180002475  or      rdx, 0Fh
0x180002479  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180002480  cmp     rdx, r9
0x180002483  ja      short loc_1800024B9
0x180002485  mov     rdi, rdx
0x180002488  mov     r8, [rcx+18h]
0x18000248c  mov     rcx, r8
0x18000248f  shr     rcx, 1
0x180002492  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000249c  mul     rdx
0x18000249f  shr     rdx, 1
0x1800024a2  cmp     rcx, rdx
0x1800024a5  jbe     short loc_1800024B9
0x1800024a7  mov     rax, r9
0x1800024aa  sub     rax, rcx
0x1800024ad  cmp     r8, rax
0x1800024b0  lea     rdi, [rcx+r8]
0x1800024b4  jbe     short loc_1800024B9
0x1800024b6  mov     rdi, r9
0x1800024b9  lea     rcx, [rdi+1]; Size
0x1800024bd  test    rcx, rcx
0x1800024c0  jz      short loc_1800024D1
0x1800024c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800024c7  mov     rsi, rax
0x1800024ca  test    rax, rax
0x1800024cd  jz      short loc_18000253D
0x1800024cf  jmp     short loc_1800024D3
0x1800024d1  xor     esi, esi
0x1800024d3  jmp     short loc_1800024E9
0x1800024d5  mov     rbx, [rsp+48h+arg_0]
0x1800024da  mov     r14, [rsp+48h+arg_10]
0x1800024df  mov     rdi, [rsp+48h+arg_8]
0x1800024e4  mov     rsi, [rsp+48h+arg_18]
0x1800024e9  test    r14, r14
0x1800024ec  jz      short loc_180002508
0x1800024ee  cmp     qword ptr [rbx+18h], 10h
0x1800024f3  jb      short loc_1800024FA
0x1800024f5  mov     rdx, [rbx]
0x1800024f8  jmp     short loc_1800024FD
0x1800024fa  mov     rdx, rbx; Src
0x1800024fd  mov     r8, r14; Size
0x180002500  mov     rcx, rsi; void *
0x180002503  call    memcpy_0
0x180002508  cmp     qword ptr [rbx+18h], 10h
0x18000250d  jb      short loc_180002518
0x18000250f  mov     rcx, [rbx]
0x180002512  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002518  lea     rax, [rbx+10h]
0x18000251c  mov     [rbx], rsi
0x18000251f  mov     [rbx+18h], rdi
0x180002523  cmp     rdi, 10h
0x180002527  cmovnb  rbx, rsi
0x18000252b  mov     [rax], r14
0x18000252e  mov     byte ptr [rbx+r14], 0
0x180002533  add     rsp, 28h
0x180002537  pop     r14
0x180002539  pop     rdi
0x18000253a  pop     rsi
0x18000253b  pop     rbx
0x18000253c  retn
0x18000253d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
