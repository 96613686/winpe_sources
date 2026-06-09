# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000aa14`
- end: `0x18000ab04`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ac50`
- `0x18000ad48`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180001d06`
- `0x18000aa14`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aad2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aad2`

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
0x18000aa14  mov     [rsp+arg_10], r8
0x18000aa19  mov     [rsp+arg_8], rdx
0x18000aa1e  mov     [rsp+arg_0], rcx
0x18000aa23  push    rbx
0x18000aa24  push    rsi
0x18000aa25  push    rdi
0x18000aa26  push    r14
0x18000aa28  sub     rsp, 28h
0x18000aa2c  mov     r14, r8
0x18000aa2f  mov     rdi, rdx
0x18000aa32  mov     rbx, rcx
0x18000aa35  or      rdx, 0Fh
0x18000aa39  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000aa40  cmp     rdx, r9
0x18000aa43  ja      short loc_18000AA79
0x18000aa45  mov     rdi, rdx
0x18000aa48  mov     r8, [rcx+18h]
0x18000aa4c  mov     rcx, r8
0x18000aa4f  shr     rcx, 1
0x18000aa52  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000aa5c  mul     rdx
0x18000aa5f  shr     rdx, 1
0x18000aa62  cmp     rcx, rdx
0x18000aa65  jbe     short loc_18000AA79
0x18000aa67  mov     rax, r9
0x18000aa6a  sub     rax, rcx
0x18000aa6d  cmp     r8, rax
0x18000aa70  lea     rdi, [rcx+r8]
0x18000aa74  jbe     short loc_18000AA79
0x18000aa76  mov     rdi, r9
0x18000aa79  lea     rcx, [rdi+1]; Size
0x18000aa7d  test    rcx, rcx
0x18000aa80  jz      short loc_18000AA91
0x18000aa82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa87  mov     rsi, rax
0x18000aa8a  test    rax, rax
0x18000aa8d  jz      short loc_18000AAFD
0x18000aa8f  jmp     short loc_18000AA93
0x18000aa91  xor     esi, esi
0x18000aa93  jmp     short loc_18000AAA9
0x18000aa95  mov     rbx, [rsp+48h+arg_0]
0x18000aa9a  mov     r14, [rsp+48h+arg_10]
0x18000aa9f  mov     rdi, [rsp+48h+arg_8]
0x18000aaa4  mov     rsi, [rsp+48h+arg_18]
0x18000aaa9  test    r14, r14
0x18000aaac  jz      short loc_18000AAC8
0x18000aaae  cmp     qword ptr [rbx+18h], 10h
0x18000aab3  jb      short loc_18000AABA
0x18000aab5  mov     rdx, [rbx]
0x18000aab8  jmp     short loc_18000AABD
0x18000aaba  mov     rdx, rbx; Src
0x18000aabd  mov     r8, r14; Size
0x18000aac0  mov     rcx, rsi; void *
0x18000aac3  call    memcpy_0
0x18000aac8  cmp     qword ptr [rbx+18h], 10h
0x18000aacd  jb      short loc_18000AAD8
0x18000aacf  mov     rcx, [rbx]
0x18000aad2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aad8  lea     rax, [rbx+10h]
0x18000aadc  mov     [rbx], rsi
0x18000aadf  mov     [rbx+18h], rdi
0x18000aae3  cmp     rdi, 10h
0x18000aae7  cmovnb  rbx, rsi
0x18000aaeb  mov     [rax], r14
0x18000aaee  mov     byte ptr [rbx+r14], 0
0x18000aaf3  add     rsp, 28h
0x18000aaf7  pop     r14
0x18000aaf9  pop     rdi
0x18000aafa  pop     rsi
0x18000aafb  pop     rbx
0x18000aafc  retn
0x18000aafd  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
