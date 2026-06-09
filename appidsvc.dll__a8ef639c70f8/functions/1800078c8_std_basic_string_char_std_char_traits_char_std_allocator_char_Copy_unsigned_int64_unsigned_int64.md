# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800078c8`
- end: `0x1800079c2`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007c94`
- `0x180007d8c`

## callees

- `0x1800011c8`
- `0x180001308`
- `0x180001bb6`
- `0x1800078c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000798c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000798c`

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
  void *v15; // [rsp+20h] [rbp-28h]

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
    v9 = 0;
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
    v15 = v9;
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
      v15 = v12;
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
    v9 = v15;
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
0x1800078c8  mov     rax, rsp
0x1800078cb  mov     [rax+20h], rbx
0x1800078cf  mov     [rax+18h], r8
0x1800078d3  mov     [rax+10h], rdx
0x1800078d7  mov     [rax+8], rcx
0x1800078db  push    rsi
0x1800078dc  push    rdi
0x1800078dd  push    r14
0x1800078df  sub     rsp, 30h
0x1800078e3  mov     r14, r8
0x1800078e6  mov     rdi, rdx
0x1800078e9  mov     rbx, rcx
0x1800078ec  or      rdx, 0Fh
0x1800078f0  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800078f7  cmp     rdx, r9
0x1800078fa  ja      short loc_180007930
0x1800078fc  mov     rdi, rdx
0x1800078ff  mov     r8, [rcx+18h]
0x180007903  mov     rcx, r8
0x180007906  shr     rcx, 1
0x180007909  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007913  mul     rdx
0x180007916  shr     rdx, 1
0x180007919  cmp     rcx, rdx
0x18000791c  jbe     short loc_180007930
0x18000791e  mov     rax, r9
0x180007921  sub     rax, rcx
0x180007924  cmp     r8, rax
0x180007927  lea     rdi, [rcx+r8]
0x18000792b  jbe     short loc_180007930
0x18000792d  mov     rdi, r9
0x180007930  lea     rcx, [rdi+1]; Size
0x180007934  xor     esi, esi
0x180007936  test    rcx, rcx
0x180007939  jz      short loc_180007948
0x18000793b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007940  mov     rsi, rax
0x180007943  test    rax, rax
0x180007946  jz      short loc_1800079BB
0x180007948  mov     [rsp+48h+var_28], rsi
0x18000794d  jmp     short loc_180007963
0x18000794f  mov     rbx, [rsp+48h+arg_0]
0x180007954  mov     r14, [rsp+48h+arg_10]
0x180007959  mov     rdi, [rsp+48h+arg_8]
0x18000795e  mov     rsi, [rsp+48h+var_28]
0x180007963  test    r14, r14
0x180007966  jz      short loc_180007982
0x180007968  cmp     qword ptr [rbx+18h], 10h
0x18000796d  jb      short loc_180007974
0x18000796f  mov     rdx, [rbx]
0x180007972  jmp     short loc_180007977
0x180007974  mov     rdx, rbx; Src
0x180007977  mov     r8, r14; Size
0x18000797a  mov     rcx, rsi; void *
0x18000797d  call    memcpy_0
0x180007982  cmp     qword ptr [rbx+18h], 10h
0x180007987  jb      short loc_180007992
0x180007989  mov     rcx, [rbx]
0x18000798c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007992  lea     rax, [rbx+10h]
0x180007996  mov     [rbx], rsi
0x180007999  mov     [rbx+18h], rdi
0x18000799d  cmp     rdi, 10h
0x1800079a1  cmovnb  rbx, rsi
0x1800079a5  mov     [rax], r14
0x1800079a8  mov     byte ptr [rbx+r14], 0
0x1800079ad  mov     rbx, [rsp+48h+arg_18]
0x1800079b2  add     rsp, 30h
0x1800079b6  pop     r14
0x1800079b8  pop     rdi
0x1800079b9  pop     rsi
0x1800079ba  retn
0x1800079bb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
