# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001908`
- end: `0x1800019ff`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001b18`
- `0x180001c10`

## callees

- `0x180001730`
- `0x180001908`
- `0x180001a68`
- `0x180002556`
- `0x180002706`

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
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
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
      v13 = v14;
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
0x180001908  mov     rax, rsp
0x18000190b  mov     [rax+18h], r8
0x18000190f  mov     [rax+10h], rdx
0x180001913  mov     [rax+8], rcx
0x180001917  push    rbx
0x180001918  push    rsi
0x180001919  push    rdi
0x18000191a  push    r14
0x18000191c  sub     rsp, 38h
0x180001920  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001928  mov     r14, r8
0x18000192b  mov     rdi, rdx
0x18000192e  mov     rbx, rcx
0x180001931  or      rdx, 0Fh
0x180001935  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000193c  cmp     rdx, r9
0x18000193f  ja      short loc_180001975
0x180001941  mov     rdi, rdx
0x180001944  mov     r8, [rcx+18h]
0x180001948  mov     rcx, r8
0x18000194b  shr     rcx, 1
0x18000194e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001958  mul     rdx
0x18000195b  shr     rdx, 1
0x18000195e  cmp     rcx, rdx
0x180001961  jbe     short loc_180001975
0x180001963  mov     rax, r9
0x180001966  sub     rax, rcx
0x180001969  cmp     r8, rax
0x18000196c  lea     rdi, [rcx+r8]
0x180001970  jbe     short loc_180001975
0x180001972  mov     rdi, r9
0x180001975  lea     rcx, [rdi+1]; Size
0x180001979  test    rcx, rcx
0x18000197c  jz      short loc_18000198D
0x18000197e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001983  mov     rsi, rax
0x180001986  test    rax, rax
0x180001989  jz      short loc_1800019F8
0x18000198b  jmp     short loc_18000198F
0x18000198d  xor     esi, esi
0x18000198f  jmp     short loc_1800019A5
0x180001991  mov     rbx, [rsp+58h+arg_0]
0x180001996  mov     r14, [rsp+58h+arg_10]
0x18000199b  mov     rdi, [rsp+58h+arg_8]
0x1800019a0  mov     rsi, [rsp+58h+arg_18]
0x1800019a5  test    r14, r14
0x1800019a8  jz      short loc_1800019C4
0x1800019aa  cmp     qword ptr [rbx+18h], 10h
0x1800019af  jb      short loc_1800019B6
0x1800019b1  mov     rdx, [rbx]
0x1800019b4  jmp     short loc_1800019B9
0x1800019b6  mov     rdx, rbx; Src
0x1800019b9  mov     r8, r14; Size
0x1800019bc  mov     rcx, rsi; void *
0x1800019bf  call    memcpy_0
0x1800019c4  cmp     qword ptr [rbx+18h], 10h
0x1800019c9  jb      short loc_1800019D3
0x1800019cb  mov     rcx, [rbx]; void *
0x1800019ce  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800019d3  lea     rax, [rbx+10h]
0x1800019d7  mov     [rbx], rsi
0x1800019da  mov     [rbx+18h], rdi
0x1800019de  cmp     rdi, 10h
0x1800019e2  cmovnb  rbx, rsi
0x1800019e6  mov     [rax], r14
0x1800019e9  mov     byte ptr [rbx+r14], 0
0x1800019ee  add     rsp, 38h
0x1800019f2  pop     r14
0x1800019f4  pop     rdi
0x1800019f5  pop     rsi
0x1800019f6  pop     rbx
0x1800019f7  retn
0x1800019f8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
