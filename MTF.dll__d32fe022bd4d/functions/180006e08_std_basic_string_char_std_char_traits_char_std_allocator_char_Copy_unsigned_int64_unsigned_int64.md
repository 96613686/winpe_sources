# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006e08`
- end: `0x180006ef8`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006fbc`
- `0x1800070b4`

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180002966`
- `0x180006e08`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006ec6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006ec6`

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
0x180006e08  mov     [rsp+arg_10], r8
0x180006e0d  mov     [rsp+arg_8], rdx
0x180006e12  mov     [rsp+arg_0], rcx
0x180006e17  push    rbx
0x180006e18  push    rsi
0x180006e19  push    rdi
0x180006e1a  push    r14
0x180006e1c  sub     rsp, 28h
0x180006e20  mov     r14, r8
0x180006e23  mov     rdi, rdx
0x180006e26  mov     rbx, rcx
0x180006e29  or      rdx, 0Fh
0x180006e2d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180006e34  cmp     rdx, r9
0x180006e37  ja      short loc_180006E6D
0x180006e39  mov     rdi, rdx
0x180006e3c  mov     r8, [rcx+18h]
0x180006e40  mov     rcx, r8
0x180006e43  shr     rcx, 1
0x180006e46  mov     rax, 0AAAAAAAAAAAAAAABh
0x180006e50  mul     rdx
0x180006e53  shr     rdx, 1
0x180006e56  cmp     rcx, rdx
0x180006e59  jbe     short loc_180006E6D
0x180006e5b  mov     rax, r9
0x180006e5e  sub     rax, rcx
0x180006e61  cmp     r8, rax
0x180006e64  lea     rdi, [rcx+r8]
0x180006e68  jbe     short loc_180006E6D
0x180006e6a  mov     rdi, r9
0x180006e6d  lea     rcx, [rdi+1]; Size
0x180006e71  test    rcx, rcx
0x180006e74  jz      short loc_180006E85
0x180006e76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006e7b  mov     rsi, rax
0x180006e7e  test    rax, rax
0x180006e81  jz      short loc_180006EF1
0x180006e83  jmp     short loc_180006E87
0x180006e85  xor     esi, esi
0x180006e87  jmp     short loc_180006E9D
0x180006e89  mov     rbx, [rsp+48h+arg_0]
0x180006e8e  mov     r14, [rsp+48h+arg_10]
0x180006e93  mov     rdi, [rsp+48h+arg_8]
0x180006e98  mov     rsi, [rsp+48h+arg_18]
0x180006e9d  test    r14, r14
0x180006ea0  jz      short loc_180006EBC
0x180006ea2  cmp     qword ptr [rbx+18h], 10h
0x180006ea7  jb      short loc_180006EAE
0x180006ea9  mov     rdx, [rbx]
0x180006eac  jmp     short loc_180006EB1
0x180006eae  mov     rdx, rbx; Src
0x180006eb1  mov     r8, r14; Size
0x180006eb4  mov     rcx, rsi; void *
0x180006eb7  call    memcpy_0
0x180006ebc  cmp     qword ptr [rbx+18h], 10h
0x180006ec1  jb      short loc_180006ECC
0x180006ec3  mov     rcx, [rbx]
0x180006ec6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006ecc  lea     rax, [rbx+10h]
0x180006ed0  mov     [rbx], rsi
0x180006ed3  mov     [rbx+18h], rdi
0x180006ed7  cmp     rdi, 10h
0x180006edb  cmovnb  rbx, rsi
0x180006edf  mov     [rax], r14
0x180006ee2  mov     byte ptr [rbx+r14], 0
0x180006ee7  add     rsp, 28h
0x180006eeb  pop     r14
0x180006eed  pop     rdi
0x180006eee  pop     rsi
0x180006eef  pop     rbx
0x180006ef0  retn
0x180006ef1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
