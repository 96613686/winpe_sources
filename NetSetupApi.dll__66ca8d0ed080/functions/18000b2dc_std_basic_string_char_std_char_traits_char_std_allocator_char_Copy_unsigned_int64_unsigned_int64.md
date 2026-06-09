# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000b2dc`
- end: `0x18000b3bd`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `225`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b3f8`

## callees

- `0x180008976`
- `0x1800092b0`
- `0x18000b2dc`
- `0x18000b4b8`

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
  _QWORD *v14; // rdx
  _QWORD v15[11]; // [rsp+0h] [rbp-58h] BYREF
  __int64 v23; // [rsp+78h] [rbp+20h]

  v15[4] = -2;
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
      v14 = v15;
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
0x18000b2dc  mov     rax, rsp
0x18000b2df  mov     [rax+18h], r8
0x18000b2e3  mov     [rax+10h], rdx
0x18000b2e7  mov     [rax+8], rcx
0x18000b2eb  push    rbx
0x18000b2ec  push    rsi
0x18000b2ed  push    rdi
0x18000b2ee  push    r14
0x18000b2f0  sub     rsp, 38h
0x18000b2f4  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18000b2fc  mov     rsi, r8
0x18000b2ff  mov     rdi, rdx
0x18000b302  mov     rbx, rcx
0x18000b305  or      rdx, 0Fh
0x18000b309  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000b310  cmp     rdx, r9
0x18000b313  ja      short loc_18000B349
0x18000b315  mov     rdi, rdx
0x18000b318  mov     r8, [rcx+18h]
0x18000b31c  mov     rcx, r8
0x18000b31f  shr     rcx, 1
0x18000b322  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000b32c  mul     rdx
0x18000b32f  shr     rdx, 1
0x18000b332  cmp     rcx, rdx
0x18000b335  jbe     short loc_18000B349
0x18000b337  mov     rax, r9
0x18000b33a  sub     rax, rcx
0x18000b33d  cmp     r8, rax
0x18000b340  lea     rdi, [rcx+r8]
0x18000b344  jbe     short loc_18000B349
0x18000b346  mov     rdi, r9
0x18000b349  lea     rcx, [rdi+1]
0x18000b34d  xor     edx, edx
0x18000b34f  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000b354  mov     r14, rax
0x18000b357  jmp     short loc_18000B36D
0x18000b359  mov     rbx, [rsp+58h+arg_0]
0x18000b35e  mov     rsi, [rsp+58h+arg_10]
0x18000b363  mov     rdi, [rsp+58h+arg_8]
0x18000b368  mov     r14, [rsp+58h+arg_18]
0x18000b36d  test    rsi, rsi
0x18000b370  jz      short loc_18000B38C
0x18000b372  cmp     qword ptr [rbx+18h], 10h
0x18000b377  jb      short loc_18000B37E
0x18000b379  mov     rdx, [rbx]
0x18000b37c  jmp     short loc_18000B381
0x18000b37e  mov     rdx, rbx; Src
0x18000b381  mov     r8, rsi; Size
0x18000b384  mov     rcx, r14; void *
0x18000b387  call    memcpy_0
0x18000b38c  xor     r8d, r8d
0x18000b38f  mov     dl, 1
0x18000b391  mov     rcx, rbx
0x18000b394  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000b399  mov     [rbx], r14
0x18000b39c  mov     [rbx+18h], rdi
0x18000b3a0  mov     rax, rbx
0x18000b3a3  cmp     rdi, 10h
0x18000b3a7  cmovnb  rax, r14
0x18000b3ab  mov     [rbx+10h], rsi
0x18000b3af  mov     byte ptr [rax+rsi], 0
0x18000b3b3  add     rsp, 38h
0x18000b3b7  pop     r14
0x18000b3b9  pop     rdi
0x18000b3ba  pop     rsi
0x18000b3bb  pop     rbx
0x18000b3bc  retn
```
