# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000ea28`
- end: `0x14000eb3b`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000ed4c`
- `0x14000eeb4`
- `0x14000ef9c`
- `0x14000f060`
- `0x140011ab0`

## callees

- `0x1400014fc`
- `0x140001758`
- `0x1400020c6`
- `0x14000ea28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000eb07`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000eb07`

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
0x14000ea28  mov     [rsp+arg_10], r8
0x14000ea2d  mov     [rsp+arg_8], rdx
0x14000ea32  mov     [rsp+arg_0], rcx
0x14000ea37  push    rbx
0x14000ea38  push    rsi
0x14000ea39  push    rdi
0x14000ea3a  push    r14
0x14000ea3c  push    r15
0x14000ea3e  sub     rsp, 20h
0x14000ea42  mov     r15, r8
0x14000ea45  mov     rdi, rdx
0x14000ea48  mov     rbx, rcx
0x14000ea4b  or      rdx, 7
0x14000ea4f  mov     r9, 7FFFFFFFFFFFFFFEh
0x14000ea59  cmp     rdx, r9
0x14000ea5c  ja      short loc_14000EA92
0x14000ea5e  mov     rdi, rdx
0x14000ea61  mov     r8, [rcx+18h]
0x14000ea65  mov     rcx, r8
0x14000ea68  shr     rcx, 1
0x14000ea6b  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000ea75  mul     rdx
0x14000ea78  shr     rdx, 1
0x14000ea7b  cmp     rcx, rdx
0x14000ea7e  jbe     short loc_14000EA92
0x14000ea80  mov     rax, r9
0x14000ea83  sub     rax, rcx
0x14000ea86  cmp     r8, rax
0x14000ea89  lea     rdi, [rcx+r8]
0x14000ea8d  jbe     short loc_14000EA92
0x14000ea8f  mov     rdi, r9
0x14000ea92  lea     rcx, [rdi+1]
0x14000ea96  xor     esi, esi
0x14000ea98  test    rcx, rcx
0x14000ea9b  jz      short loc_14000EAC2
0x14000ea9d  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000eaa7  cmp     rcx, rax
0x14000eaaa  ja      loc_14000EB34
0x14000eab0  add     rcx, rcx; Size
0x14000eab3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000eab8  mov     r14, rax
0x14000eabb  test    rax, rax
0x14000eabe  jz      short loc_14000EB34
0x14000eac0  jmp     short loc_14000EAC5
0x14000eac2  mov     r14, rsi
0x14000eac5  jmp     short loc_14000EADD
0x14000eac7  xor     esi, esi
0x14000eac9  mov     rbx, [rsp+48h+arg_0]
0x14000eace  mov     r15, [rsp+48h+arg_10]
0x14000ead3  mov     rdi, [rsp+48h+arg_8]
0x14000ead8  mov     r14, [rsp+48h+arg_18]
0x14000eadd  test    r15, r15
0x14000eae0  jz      short loc_14000EAFD
0x14000eae2  cmp     qword ptr [rbx+18h], 8
0x14000eae7  jb      short loc_14000EAEE
0x14000eae9  mov     rdx, [rbx]
0x14000eaec  jmp     short loc_14000EAF1
0x14000eaee  mov     rdx, rbx; Src
0x14000eaf1  lea     r8, [r15+r15]; Size
0x14000eaf5  mov     rcx, r14; void *
0x14000eaf8  call    memcpy_0
0x14000eafd  cmp     qword ptr [rbx+18h], 8
0x14000eb02  jb      short loc_14000EB0D
0x14000eb04  mov     rcx, [rbx]
0x14000eb07  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000eb0d  lea     rax, [rbx+10h]
0x14000eb11  mov     [rbx], r14
0x14000eb14  mov     [rbx+18h], rdi
0x14000eb18  cmp     rdi, 8
0x14000eb1c  cmovnb  rbx, r14
0x14000eb20  mov     [rax], r15
0x14000eb23  mov     [rbx+r15*2], si
0x14000eb28  add     rsp, 20h
0x14000eb2c  pop     r15
0x14000eb2e  pop     r14
0x14000eb30  pop     rdi
0x14000eb31  pop     rsi
0x14000eb32  pop     rbx
0x14000eb33  retn
0x14000eb34  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
