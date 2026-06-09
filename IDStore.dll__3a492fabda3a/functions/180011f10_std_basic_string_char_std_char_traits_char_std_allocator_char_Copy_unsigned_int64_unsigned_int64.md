# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180011f10`
- end: `0x180011fe9`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011ff0`

## callees

- `0x18000fb96`
- `0x1800106d0`
- `0x180011f10`
- `0x1800120b0`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180011f10  mov     [rsp+arg_10], r8
0x180011f15  mov     [rsp+arg_8], rdx
0x180011f1a  mov     [rsp+arg_0], rcx
0x180011f1f  push    rbx
0x180011f20  push    rsi
0x180011f21  push    rdi
0x180011f22  push    r14
0x180011f24  sub     rsp, 28h
0x180011f28  mov     rsi, r8
0x180011f2b  mov     rdi, rdx
0x180011f2e  mov     rbx, rcx
0x180011f31  or      rdx, 0Fh
0x180011f35  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180011f3c  cmp     rdx, r9
0x180011f3f  ja      short loc_180011F75
0x180011f41  mov     rdi, rdx
0x180011f44  mov     r8, [rcx+18h]
0x180011f48  mov     rcx, r8
0x180011f4b  shr     rcx, 1
0x180011f4e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180011f58  mul     rdx
0x180011f5b  shr     rdx, 1
0x180011f5e  cmp     rcx, rdx
0x180011f61  jbe     short loc_180011F75
0x180011f63  mov     rax, r9
0x180011f66  sub     rax, rcx
0x180011f69  cmp     r8, rax
0x180011f6c  lea     rdi, [rcx+r8]
0x180011f70  jbe     short loc_180011F75
0x180011f72  mov     rdi, r9
0x180011f75  lea     rcx, [rdi+1]
0x180011f79  xor     edx, edx
0x180011f7b  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x180011f80  mov     r14, rax
0x180011f83  jmp     short loc_180011F99
0x180011f85  mov     rbx, [rsp+48h+arg_0]
0x180011f8a  mov     rsi, [rsp+48h+arg_10]
0x180011f8f  mov     rdi, [rsp+48h+arg_8]
0x180011f94  mov     r14, [rsp+48h+arg_18]
0x180011f99  test    rsi, rsi
0x180011f9c  jz      short loc_180011FB8
0x180011f9e  cmp     qword ptr [rbx+18h], 10h
0x180011fa3  jb      short loc_180011FAA
0x180011fa5  mov     rdx, [rbx]
0x180011fa8  jmp     short loc_180011FAD
0x180011faa  mov     rdx, rbx; Src
0x180011fad  mov     r8, rsi; Size
0x180011fb0  mov     rcx, r14; void *
0x180011fb3  call    memcpy_0
0x180011fb8  xor     r8d, r8d
0x180011fbb  mov     dl, 1
0x180011fbd  mov     rcx, rbx
0x180011fc0  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180011fc5  mov     [rbx], r14
0x180011fc8  mov     [rbx+18h], rdi
0x180011fcc  mov     rax, rbx
0x180011fcf  cmp     rdi, 10h
0x180011fd3  cmovnb  rax, r14
0x180011fd7  mov     [rbx+10h], rsi
0x180011fdb  mov     byte ptr [rax+rsi], 0
0x180011fdf  add     rsp, 28h
0x180011fe3  pop     r14
0x180011fe5  pop     rdi
0x180011fe6  pop     rsi
0x180011fe7  pop     rbx
0x180011fe8  retn
```
