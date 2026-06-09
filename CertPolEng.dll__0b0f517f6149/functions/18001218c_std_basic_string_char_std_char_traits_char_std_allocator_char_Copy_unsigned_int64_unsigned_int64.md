# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18001218c`
- end: `0x180012265`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800122c0`

## callees

- `0x18000e8d6`
- `0x18000f2ec`
- `0x18001218c`
- `0x180012380`

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
0x18001218c  mov     [rsp+arg_10], r8
0x180012191  mov     [rsp+arg_8], rdx
0x180012196  mov     [rsp+arg_0], rcx
0x18001219b  push    rbx
0x18001219c  push    rsi
0x18001219d  push    rdi
0x18001219e  push    r14
0x1800121a0  sub     rsp, 28h
0x1800121a4  mov     rsi, r8
0x1800121a7  mov     rdi, rdx
0x1800121aa  mov     rbx, rcx
0x1800121ad  or      rdx, 0Fh
0x1800121b1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800121b8  cmp     rdx, r9
0x1800121bb  ja      short loc_1800121F1
0x1800121bd  mov     rdi, rdx
0x1800121c0  mov     r8, [rcx+18h]
0x1800121c4  mov     rcx, r8
0x1800121c7  shr     rcx, 1
0x1800121ca  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800121d4  mul     rdx
0x1800121d7  shr     rdx, 1
0x1800121da  cmp     rcx, rdx
0x1800121dd  jbe     short loc_1800121F1
0x1800121df  mov     rax, r9
0x1800121e2  sub     rax, rcx
0x1800121e5  cmp     r8, rax
0x1800121e8  lea     rdi, [rcx+r8]
0x1800121ec  jbe     short loc_1800121F1
0x1800121ee  mov     rdi, r9
0x1800121f1  lea     rcx, [rdi+1]
0x1800121f5  xor     edx, edx
0x1800121f7  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1800121fc  mov     r14, rax
0x1800121ff  jmp     short loc_180012215
0x180012201  mov     rbx, [rsp+48h+arg_0]
0x180012206  mov     rsi, [rsp+48h+arg_10]
0x18001220b  mov     rdi, [rsp+48h+arg_8]
0x180012210  mov     r14, [rsp+48h+arg_18]
0x180012215  test    rsi, rsi
0x180012218  jz      short loc_180012234
0x18001221a  cmp     qword ptr [rbx+18h], 10h
0x18001221f  jb      short loc_180012226
0x180012221  mov     rdx, [rbx]
0x180012224  jmp     short loc_180012229
0x180012226  mov     rdx, rbx; Src
0x180012229  mov     r8, rsi; Size
0x18001222c  mov     rcx, r14; void *
0x18001222f  call    memcpy_0
0x180012234  xor     r8d, r8d
0x180012237  mov     dl, 1
0x180012239  mov     rcx, rbx
0x18001223c  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180012241  mov     [rbx], r14
0x180012244  mov     [rbx+18h], rdi
0x180012248  mov     rax, rbx
0x18001224b  cmp     rdi, 10h
0x18001224f  cmovnb  rax, r14
0x180012253  mov     [rbx+10h], rsi
0x180012257  mov     byte ptr [rax+rsi], 0
0x18001225b  add     rsp, 28h
0x18001225f  pop     r14
0x180012261  pop     rdi
0x180012262  pop     rsi
0x180012263  pop     rbx
0x180012264  retn
```
