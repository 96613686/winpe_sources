# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800079c8`
- end: `0x180007ade`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `278`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007e8c`
- `0x180007f9c`

## callees

- `0x1800011c8`
- `0x180001308`
- `0x180001bb6`
- `0x1800079c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007aaa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007aaa`

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
  __int64 v16; // [rsp+0h] [rbp-58h] BYREF
  void *v17; // [rsp+20h] [rbp-38h]

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
    v10 = 0;
    if ( v4 != -1 && (v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0) )
      std::_Xbad_alloc();
    v17 = v10;
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v17 = v13;
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
    v10 = v17;
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
0x1800079c8  mov     [rsp+arg_10], r8
0x1800079cd  mov     [rsp+arg_8], rdx
0x1800079d2  mov     [rsp+arg_0], rcx
0x1800079d7  push    rbx
0x1800079d8  push    rsi
0x1800079d9  push    rdi
0x1800079da  push    r14
0x1800079dc  push    r15
0x1800079de  sub     rsp, 30h
0x1800079e2  mov     r15, r8
0x1800079e5  mov     rdi, rdx
0x1800079e8  mov     rbx, rcx
0x1800079eb  or      rdx, 7
0x1800079ef  mov     r9, 7FFFFFFFFFFFFFFEh
0x1800079f9  cmp     rdx, r9
0x1800079fc  ja      short loc_180007A32
0x1800079fe  mov     rdi, rdx
0x180007a01  mov     r8, [rcx+18h]
0x180007a05  mov     rcx, r8
0x180007a08  shr     rcx, 1
0x180007a0b  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007a15  mul     rdx
0x180007a18  shr     rdx, 1
0x180007a1b  cmp     rcx, rdx
0x180007a1e  jbe     short loc_180007A32
0x180007a20  mov     rax, r9
0x180007a23  sub     rax, rcx
0x180007a26  cmp     r8, rax
0x180007a29  lea     rdi, [rcx+r8]
0x180007a2d  jbe     short loc_180007A32
0x180007a2f  mov     rdi, r9
0x180007a32  lea     rcx, [rdi+1]
0x180007a36  xor     esi, esi
0x180007a38  mov     r14d, esi
0x180007a3b  test    rcx, rcx
0x180007a3e  jz      short loc_180007A63
0x180007a40  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007a4a  cmp     rcx, rax
0x180007a4d  ja      loc_180007AD7
0x180007a53  add     rcx, rcx; Size
0x180007a56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a5b  mov     r14, rax
0x180007a5e  test    rax, rax
0x180007a61  jz      short loc_180007AD7
0x180007a63  mov     [rsp+58h+var_38], r14
0x180007a68  jmp     short loc_180007A80
0x180007a6a  xor     esi, esi
0x180007a6c  mov     rbx, [rsp+58h+arg_0]
0x180007a71  mov     r15, [rsp+58h+arg_10]
0x180007a76  mov     rdi, [rsp+58h+arg_8]
0x180007a7b  mov     r14, [rsp+58h+var_38]
0x180007a80  test    r15, r15
0x180007a83  jz      short loc_180007AA0
0x180007a85  cmp     qword ptr [rbx+18h], 8
0x180007a8a  jb      short loc_180007A91
0x180007a8c  mov     rdx, [rbx]
0x180007a8f  jmp     short loc_180007A94
0x180007a91  mov     rdx, rbx; Src
0x180007a94  lea     r8, [r15+r15]; Size
0x180007a98  mov     rcx, r14; void *
0x180007a9b  call    memcpy_0
0x180007aa0  cmp     qword ptr [rbx+18h], 8
0x180007aa5  jb      short loc_180007AB0
0x180007aa7  mov     rcx, [rbx]
0x180007aaa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007ab0  lea     rax, [rbx+10h]
0x180007ab4  mov     [rbx], r14
0x180007ab7  mov     [rbx+18h], rdi
0x180007abb  cmp     rdi, 8
0x180007abf  cmovnb  rbx, r14
0x180007ac3  mov     [rax], r15
0x180007ac6  mov     [rbx+r15*2], si
0x180007acb  add     rsp, 30h
0x180007acf  pop     r15
0x180007ad1  pop     r14
0x180007ad3  pop     rdi
0x180007ad4  pop     rsi
0x180007ad5  pop     rbx
0x180007ad6  retn
0x180007ad7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
