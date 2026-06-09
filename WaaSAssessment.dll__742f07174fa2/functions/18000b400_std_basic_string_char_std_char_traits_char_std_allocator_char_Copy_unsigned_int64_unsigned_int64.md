# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000b400`
- end: `0x18000b4ed`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a204`

## callees

- `0x1800021a4`
- `0x18000b400`
- `0x180019722`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000b47b`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000b47b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4c2`

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
0x18000b400  mov     [rsp+arg_10], r8
0x18000b405  mov     [rsp+arg_8], rdx
0x18000b40a  mov     [rsp+arg_0], rcx
0x18000b40f  push    rbx
0x18000b410  push    rsi
0x18000b411  push    rdi
0x18000b412  push    r14
0x18000b414  sub     rsp, 28h
0x18000b418  mov     r14, r8
0x18000b41b  mov     rdi, rdx
0x18000b41e  mov     rbx, rcx
0x18000b421  or      rdx, 0Fh
0x18000b425  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000b42c  cmp     rdx, r9
0x18000b42f  ja      short loc_18000B465
0x18000b431  mov     rdi, rdx
0x18000b434  mov     r8, [rcx+18h]
0x18000b438  mov     rcx, r8
0x18000b43b  shr     rcx, 1
0x18000b43e  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000b448  mul     rdx
0x18000b44b  shr     rdx, 1
0x18000b44e  cmp     rcx, rdx
0x18000b451  jbe     short loc_18000B465
0x18000b453  mov     rax, r9
0x18000b456  sub     rax, rcx
0x18000b459  cmp     r8, rax
0x18000b45c  lea     rdi, [rcx+r8]
0x18000b460  jbe     short loc_18000B465
0x18000b462  mov     rdi, r9
0x18000b465  lea     rcx, [rdi+1]; Size
0x18000b469  test    rcx, rcx
0x18000b46c  jz      short loc_18000B481
0x18000b46e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b473  mov     rsi, rax
0x18000b476  test    rax, rax
0x18000b479  jnz     short loc_18000B483
0x18000b47b  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000b481  xor     esi, esi
0x18000b483  jmp     short loc_18000B499
0x18000b485  mov     rbx, [rsp+48h+arg_0]
0x18000b48a  mov     r14, [rsp+48h+arg_10]
0x18000b48f  mov     rdi, [rsp+48h+arg_8]
0x18000b494  mov     rsi, [rsp+48h+arg_18]
0x18000b499  test    r14, r14
0x18000b49c  jz      short loc_18000B4B8
0x18000b49e  cmp     qword ptr [rbx+18h], 10h
0x18000b4a3  jb      short loc_18000B4AA
0x18000b4a5  mov     rdx, [rbx]
0x18000b4a8  jmp     short loc_18000B4AD
0x18000b4aa  mov     rdx, rbx; Src
0x18000b4ad  mov     r8, r14; Size
0x18000b4b0  mov     rcx, rsi; void *
0x18000b4b3  call    memcpy_0
0x18000b4b8  cmp     qword ptr [rbx+18h], 10h
0x18000b4bd  jb      short loc_18000B4C8
0x18000b4bf  mov     rcx, [rbx]
0x18000b4c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b4c8  lea     rax, [rbx+10h]
0x18000b4cc  mov     [rbx], rsi
0x18000b4cf  mov     [rbx+18h], rdi
0x18000b4d3  cmp     rdi, 10h
0x18000b4d7  cmovnb  rbx, rsi
0x18000b4db  mov     [rax], r14
0x18000b4de  mov     byte ptr [rbx+r14], 0
0x18000b4e3  add     rsp, 28h
0x18000b4e7  pop     r14
0x18000b4e9  pop     rdi
0x18000b4ea  pop     rsi
0x18000b4eb  pop     rbx
0x18000b4ec  retn
```
