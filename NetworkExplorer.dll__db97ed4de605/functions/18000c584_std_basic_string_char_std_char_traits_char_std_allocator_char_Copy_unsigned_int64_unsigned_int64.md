# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000c584`
- end: `0x18000c65d`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c878`

## callees

- `0x180007c76`
- `0x180008770`
- `0x18000c584`
- `0x18000cf10`

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
0x18000c584  mov     [rsp+arg_10], r8
0x18000c589  mov     [rsp+arg_8], rdx
0x18000c58e  mov     [rsp+arg_0], rcx
0x18000c593  push    rbx
0x18000c594  push    rsi
0x18000c595  push    rdi
0x18000c596  push    r14
0x18000c598  sub     rsp, 28h
0x18000c59c  mov     rsi, r8
0x18000c59f  mov     rdi, rdx
0x18000c5a2  mov     rbx, rcx
0x18000c5a5  or      rdx, 0Fh
0x18000c5a9  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000c5b0  cmp     rdx, r9
0x18000c5b3  ja      short loc_18000C5E9
0x18000c5b5  mov     rdi, rdx
0x18000c5b8  mov     r8, [rcx+18h]
0x18000c5bc  mov     rcx, r8
0x18000c5bf  shr     rcx, 1
0x18000c5c2  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000c5cc  mul     rdx
0x18000c5cf  shr     rdx, 1
0x18000c5d2  cmp     rcx, rdx
0x18000c5d5  jbe     short loc_18000C5E9
0x18000c5d7  mov     rax, r9
0x18000c5da  sub     rax, rcx
0x18000c5dd  cmp     r8, rax
0x18000c5e0  lea     rdi, [rcx+r8]
0x18000c5e4  jbe     short loc_18000C5E9
0x18000c5e6  mov     rdi, r9
0x18000c5e9  lea     rcx, [rdi+1]
0x18000c5ed  xor     edx, edx
0x18000c5ef  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000c5f4  mov     r14, rax
0x18000c5f7  jmp     short loc_18000C60D
0x18000c5f9  mov     rbx, [rsp+48h+arg_0]
0x18000c5fe  mov     rsi, [rsp+48h+arg_10]
0x18000c603  mov     rdi, [rsp+48h+arg_8]
0x18000c608  mov     r14, [rsp+48h+arg_18]
0x18000c60d  test    rsi, rsi
0x18000c610  jz      short loc_18000C62C
0x18000c612  cmp     qword ptr [rbx+18h], 10h
0x18000c617  jb      short loc_18000C61E
0x18000c619  mov     rdx, [rbx]
0x18000c61c  jmp     short loc_18000C621
0x18000c61e  mov     rdx, rbx; Src
0x18000c621  mov     r8, rsi; Size
0x18000c624  mov     rcx, r14; void *
0x18000c627  call    memcpy_0
0x18000c62c  xor     r8d, r8d
0x18000c62f  mov     dl, 1
0x18000c631  mov     rcx, rbx
0x18000c634  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000c639  mov     [rbx], r14
0x18000c63c  mov     [rbx+18h], rdi
0x18000c640  mov     rax, rbx
0x18000c643  cmp     rdi, 10h
0x18000c647  cmovnb  rax, r14
0x18000c64b  mov     [rbx+10h], rsi
0x18000c64f  mov     byte ptr [rax+rsi], 0
0x18000c653  add     rsp, 28h
0x18000c657  pop     r14
0x18000c659  pop     rdi
0x18000c65a  pop     rsi
0x18000c65b  pop     rbx
0x18000c65c  retn
```
