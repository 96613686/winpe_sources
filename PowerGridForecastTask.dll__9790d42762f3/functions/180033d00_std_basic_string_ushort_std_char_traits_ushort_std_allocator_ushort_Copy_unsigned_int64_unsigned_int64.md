# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180033d00`
- end: `0x180033e13`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001592c`
- `0x180015a28`
- `0x180015cf4`
- `0x18001c6b4`
- `0x1800341fc`
- `0x180034304`

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x180026796`
- `0x180033d00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033ddf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033ddf`

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
0x180033d00  mov     [rsp+arg_10], r8
0x180033d05  mov     [rsp+arg_8], rdx
0x180033d0a  mov     [rsp+arg_0], rcx
0x180033d0f  push    rbx
0x180033d10  push    rsi
0x180033d11  push    rdi
0x180033d12  push    r14
0x180033d14  push    r15
0x180033d16  sub     rsp, 20h
0x180033d1a  mov     r15, r8
0x180033d1d  mov     rdi, rdx
0x180033d20  mov     rbx, rcx
0x180033d23  or      rdx, 7
0x180033d27  mov     r9, 7FFFFFFFFFFFFFFEh
0x180033d31  cmp     rdx, r9
0x180033d34  ja      short loc_180033D6A
0x180033d36  mov     rdi, rdx
0x180033d39  mov     r8, [rcx+18h]
0x180033d3d  mov     rcx, r8
0x180033d40  shr     rcx, 1
0x180033d43  mov     rax, 0AAAAAAAAAAAAAAABh
0x180033d4d  mul     rdx
0x180033d50  shr     rdx, 1
0x180033d53  cmp     rcx, rdx
0x180033d56  jbe     short loc_180033D6A
0x180033d58  mov     rax, r9
0x180033d5b  sub     rax, rcx
0x180033d5e  cmp     r8, rax
0x180033d61  lea     rdi, [rcx+r8]
0x180033d65  jbe     short loc_180033D6A
0x180033d67  mov     rdi, r9
0x180033d6a  lea     rcx, [rdi+1]
0x180033d6e  xor     esi, esi
0x180033d70  test    rcx, rcx
0x180033d73  jz      short loc_180033D9A
0x180033d75  mov     rax, 7FFFFFFFFFFFFFFFh
0x180033d7f  cmp     rcx, rax
0x180033d82  ja      loc_180033E0C
0x180033d88  add     rcx, rcx; Size
0x180033d8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033d90  mov     r14, rax
0x180033d93  test    rax, rax
0x180033d96  jz      short loc_180033E0C
0x180033d98  jmp     short loc_180033D9D
0x180033d9a  mov     r14, rsi
0x180033d9d  jmp     short loc_180033DB5
0x180033d9f  xor     esi, esi
0x180033da1  mov     rbx, [rsp+48h+arg_0]
0x180033da6  mov     r15, [rsp+48h+arg_10]
0x180033dab  mov     rdi, [rsp+48h+arg_8]
0x180033db0  mov     r14, [rsp+48h+arg_18]
0x180033db5  test    r15, r15
0x180033db8  jz      short loc_180033DD5
0x180033dba  cmp     qword ptr [rbx+18h], 8
0x180033dbf  jb      short loc_180033DC6
0x180033dc1  mov     rdx, [rbx]
0x180033dc4  jmp     short loc_180033DC9
0x180033dc6  mov     rdx, rbx; Src
0x180033dc9  lea     r8, [r15+r15]; Size
0x180033dcd  mov     rcx, r14; void *
0x180033dd0  call    memcpy_0
0x180033dd5  cmp     qword ptr [rbx+18h], 8
0x180033dda  jb      short loc_180033DE5
0x180033ddc  mov     rcx, [rbx]
0x180033ddf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033de5  lea     rax, [rbx+10h]
0x180033de9  mov     [rbx], r14
0x180033dec  mov     [rbx+18h], rdi
0x180033df0  cmp     rdi, 8
0x180033df4  cmovnb  rbx, r14
0x180033df8  mov     [rax], r15
0x180033dfb  mov     [rbx+r15*2], si
0x180033e00  add     rsp, 20h
0x180033e04  pop     r15
0x180033e06  pop     r14
0x180033e08  pop     rdi
0x180033e09  pop     rsi
0x180033e0a  pop     rbx
0x180033e0b  retn
0x180033e0c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
