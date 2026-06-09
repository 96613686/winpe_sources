# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x14000f060`
- end: `0x14000f167`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `263`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x1400077ec`
- `0x14000f170`
- `0x140011110`
- `0x140011770`
- `0x140011894`
- `0x140011ab0`

## callees

- `0x1400020c6`
- `0x14000646c`
- `0x140006484`
- `0x14000ea28`
- `0x14000f060`
- `0x14000f530`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // r14
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _WORD *v11; // rax
  void **v12; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] < v8 + a3 )
      std::wstring::_Xran();
    if ( (unsigned __int64)a1[3] >= 8 )
      a1 = (void **)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + (_QWORD)v9) = 0;
    std::wstring::erase(v7, 0);
  }
  else
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( (unsigned __int64)a1[3] >= v8 )
    {
      if ( !v8 )
      {
        if ( (unsigned __int64)a1[3] < 8 )
          v11 = a1;
        else
          v11 = *a1;
        a1[2] = 0;
        *v11 = 0;
        return v7;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)a1, v8, (__int64)a1[2]);
      if ( !v8 )
        return v7;
    }
    if ( (unsigned __int64)v6[3] >= 8 )
      v6 = (void **)*v6;
    if ( (unsigned __int64)v7[3] < 8 )
      v10 = v7;
    else
      v10 = *v7;
    memcpy_0(v10, (char *)v6 + 2 * a3, 2 * v8);
    if ( (unsigned __int64)v7[3] < 8 )
      v12 = v7;
    else
      v12 = (void **)*v7;
    v7[2] = (void *)v8;
    *((_WORD *)v12 + v8) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14000f060  push    rbx
0x14000f062  push    rbp
0x14000f063  push    rsi
0x14000f064  push    rdi
0x14000f065  push    r14
0x14000f067  sub     rsp, 20h
0x14000f06b  mov     rdi, [rdx+10h]
0x14000f06f  mov     rbp, r8
0x14000f072  mov     r14, rdx
0x14000f075  mov     rbx, rcx
0x14000f078  cmp     rdi, r8
0x14000f07b  jb      loc_14000F155
0x14000f081  sub     rdi, r8
0x14000f084  cmp     r9, rdi
0x14000f087  cmovb   rdi, r9
0x14000f08b  cmp     rcx, rdx
0x14000f08e  jnz     short loc_14000F0C1
0x14000f090  lea     rax, [rdi+r8]
0x14000f094  cmp     [rcx+10h], rax
0x14000f098  jb      loc_14000F15B
0x14000f09e  cmp     qword ptr [rcx+18h], 8
0x14000f0a3  jb      short loc_14000F0A8
0x14000f0a5  mov     rcx, [rcx]
0x14000f0a8  xor     esi, esi
0x14000f0aa  mov     [rbx+10h], rax
0x14000f0ae  mov     [rcx+rax*2], si
0x14000f0b2  xor     edx, edx
0x14000f0b4  mov     rcx, rbx
0x14000f0b7  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x14000f0bc  jmp     loc_14000F147
0x14000f0c1  mov     rax, 7FFFFFFFFFFFFFFEh
0x14000f0cb  cmp     rdi, rax
0x14000f0ce  ja      loc_14000F161
0x14000f0d4  xor     esi, esi
0x14000f0d6  cmp     [rcx+18h], rdi
0x14000f0da  jnb     short loc_14000F103
0x14000f0dc  mov     r8, [rcx+10h]
0x14000f0e0  mov     rdx, rdi
0x14000f0e3  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x14000f0e8  test    rdi, rdi
0x14000f0eb  jz      short loc_14000F147
0x14000f0ed  cmp     qword ptr [r14+18h], 8
0x14000f0f2  jb      short loc_14000F0F7
0x14000f0f4  mov     r14, [r14]
0x14000f0f7  cmp     qword ptr [rbx+18h], 8
0x14000f0fc  jb      short loc_14000F120
0x14000f0fe  mov     rcx, [rbx]
0x14000f101  jmp     short loc_14000F123
0x14000f103  test    rdi, rdi
0x14000f106  jnz     short loc_14000F0ED
0x14000f108  cmp     qword ptr [rcx+18h], 8
0x14000f10d  jb      short loc_14000F114
0x14000f10f  mov     rax, [rcx]
0x14000f112  jmp     short loc_14000F117
0x14000f114  mov     rax, rbx
0x14000f117  mov     [rcx+10h], rsi
0x14000f11b  mov     [rax], si
0x14000f11e  jmp     short loc_14000F147
0x14000f120  mov     rcx, rbx; void *
0x14000f123  lea     r8, [rdi+rdi]; Size
0x14000f127  lea     rdx, [r14+rbp*2]; Src
0x14000f12b  call    memcpy_0
0x14000f130  cmp     qword ptr [rbx+18h], 8
0x14000f135  jb      short loc_14000F13C
0x14000f137  mov     rax, [rbx]
0x14000f13a  jmp     short loc_14000F13F
0x14000f13c  mov     rax, rbx
0x14000f13f  mov     [rbx+10h], rdi
0x14000f143  mov     [rax+rdi*2], si
0x14000f147  mov     rax, rbx
0x14000f14a  add     rsp, 20h
0x14000f14e  pop     r14
0x14000f150  pop     rdi
0x14000f151  pop     rsi
0x14000f152  pop     rbp
0x14000f153  pop     rbx
0x14000f154  retn
0x14000f155  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x14000f15b  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x14000f161  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
