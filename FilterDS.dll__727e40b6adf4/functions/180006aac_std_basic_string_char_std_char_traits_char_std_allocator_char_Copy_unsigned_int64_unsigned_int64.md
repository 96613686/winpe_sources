# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006aac`
- end: `0x180006b9c`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006c84`
- `0x180006d7c`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x180002326`
- `0x180006aac`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006b6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006aac  mov     [rsp+arg_10], r8
0x180006ab1  mov     [rsp+arg_8], rdx
0x180006ab6  mov     [rsp+arg_0], rcx
0x180006abb  push    rbx
0x180006abc  push    rsi
0x180006abd  push    rdi
0x180006abe  push    r14
0x180006ac0  sub     rsp, 28h
0x180006ac4  mov     r14, r8
0x180006ac7  mov     rdi, rdx
0x180006aca  mov     rbx, rcx
0x180006acd  or      rdx, 0Fh
0x180006ad1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180006ad8  cmp     rdx, r9
0x180006adb  ja      short loc_180006B11
0x180006add  mov     rdi, rdx
0x180006ae0  mov     r8, [rcx+18h]
0x180006ae4  mov     rcx, r8
0x180006ae7  shr     rcx, 1
0x180006aea  mov     rax, 0AAAAAAAAAAAAAAABh
0x180006af4  mul     rdx
0x180006af7  shr     rdx, 1
0x180006afa  cmp     rcx, rdx
0x180006afd  jbe     short loc_180006B11
0x180006aff  mov     rax, r9
0x180006b02  sub     rax, rcx
0x180006b05  cmp     r8, rax
0x180006b08  lea     rdi, [rcx+r8]
0x180006b0c  jbe     short loc_180006B11
0x180006b0e  mov     rdi, r9
0x180006b11  lea     rcx, [rdi+1]; Size
0x180006b15  test    rcx, rcx
0x180006b18  jz      short loc_180006B29
0x180006b1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b1f  mov     rsi, rax
0x180006b22  test    rax, rax
0x180006b25  jz      short loc_180006B95
0x180006b27  jmp     short loc_180006B2B
0x180006b29  xor     esi, esi
0x180006b2b  jmp     short loc_180006B41
0x180006b2d  mov     rbx, [rsp+48h+arg_0]
0x180006b32  mov     r14, [rsp+48h+arg_10]
0x180006b37  mov     rdi, [rsp+48h+arg_8]
0x180006b3c  mov     rsi, [rsp+48h+arg_18]
0x180006b41  test    r14, r14
0x180006b44  jz      short loc_180006B60
0x180006b46  cmp     qword ptr [rbx+18h], 10h
0x180006b4b  jb      short loc_180006B52
0x180006b4d  mov     rdx, [rbx]
0x180006b50  jmp     short loc_180006B55
0x180006b52  mov     rdx, rbx; Src
0x180006b55  mov     r8, r14; Size
0x180006b58  mov     rcx, rsi; void *
0x180006b5b  call    memcpy_0
0x180006b60  cmp     qword ptr [rbx+18h], 10h
0x180006b65  jb      short loc_180006B70
0x180006b67  mov     rcx, [rbx]
0x180006b6a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b70  lea     rax, [rbx+10h]
0x180006b74  mov     [rbx], rsi
0x180006b77  mov     [rbx+18h], rdi
0x180006b7b  cmp     rdi, 10h
0x180006b7f  cmovnb  rbx, rsi
0x180006b83  mov     [rax], r14
0x180006b86  mov     byte ptr [rbx+r14], 0
0x180006b8b  add     rsp, 28h
0x180006b8f  pop     r14
0x180006b91  pop     rdi
0x180006b92  pop     rsi
0x180006b93  pop     rbx
0x180006b94  retn
0x180006b95  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
