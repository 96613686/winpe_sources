# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::append(ushort const *)

- ea: `0x1800038a8`
- end: `0x1800039e1`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003210`
- `0x180003330`

## callees

- `0x1800016a4`
- `0x1800035a4`
- `0x18000379c`
- `0x1800038a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800039b8`
- `msvcrt!memcpy_s` at `0x1800039b8`

## pseudocode

```c
__int64 __fastcall std::wstring::append(_QWORD *a1, char *a2)
{
  unsigned __int64 v2; // r14
  _QWORD *v4; // rdi
  char *v5; // rbx
  char *v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdx
  _QWORD *v10; // rax

  v2 = -1;
  v4 = a1;
  do
    ++v2;
  while ( *(_WORD *)&a2[2 * v2] );
  v5 = (char *)(a1 + 1);
  if ( a1[4] < 8u )
    v6 = (char *)(a1 + 1);
  else
    v6 = *(char **)v5;
  if ( a2 >= v6 )
  {
    v7 = a1[4] < 8u ? (__int64)(a1 + 1) : *(_QWORD *)v5;
    if ( v7 + 2LL * v4[3] > (unsigned __int64)a2 )
    {
      if ( v4[4] >= 8u )
        v5 = *(char **)v5;
      return std::wstring::append((__int64)v4, v4, (a2 - v5) >> 1, v2);
    }
  }
  if ( ~v4[3] <= v2 )
    std::_String_base::_Xlen();
  if ( v2 )
  {
    v8 = v2 + v4[3];
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( v4[4] < v8 )
    {
      std::wstring::_Copy((__int64)v4, v2 + v4[3], v4[3]);
      if ( !v8 )
        return (__int64)v4;
      goto LABEL_21;
    }
    if ( v8 )
    {
LABEL_21:
      v9 = v4[4];
      if ( v9 < 8 )
        v10 = v5;
      else
        v10 = *(_QWORD **)v5;
      memcpy_s((char *)v10 + 2 * v4[3], 2 * (v9 - v4[3]), a2, 2 * v2);
      if ( v4[4] >= 8u )
        v5 = *(char **)v5;
      v4[3] = v8;
      *(_WORD *)&v5[2 * v8] = 0;
      return (__int64)v4;
    }
    if ( v4[4] >= 8u )
      v5 = *(char **)v5;
    v4[3] = 0;
    *(_WORD *)v5 = 0;
  }
  return (__int64)v4;
}

```

## disassembly

```asm
0x1800038a8  push    rbx
0x1800038aa  push    rbp
0x1800038ab  push    rsi
0x1800038ac  push    rdi
0x1800038ad  push    r14
0x1800038af  push    r15
0x1800038b1  sub     rsp, 28h
0x1800038b5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800038b9  mov     rbp, rdx
0x1800038bc  xor     r15d, r15d
0x1800038bf  mov     rdi, rcx
0x1800038c2  inc     r14
0x1800038c5  cmp     [rdx+r14*2], r15w
0x1800038ca  jnz     short loc_1800038C2
0x1800038cc  cmp     qword ptr [rcx+20h], 8
0x1800038d1  lea     rbx, [rcx+8]
0x1800038d5  jb      short loc_1800038DC
0x1800038d7  mov     rax, [rbx]
0x1800038da  jmp     short loc_1800038DF
0x1800038dc  mov     rax, rbx
0x1800038df  cmp     rbp, rax
0x1800038e2  jb      short loc_180003929
0x1800038e4  cmp     qword ptr [rcx+20h], 8
0x1800038e9  jb      short loc_1800038F0
0x1800038eb  mov     rcx, [rbx]
0x1800038ee  jmp     short loc_1800038F3
0x1800038f0  mov     rcx, rbx
0x1800038f3  mov     rax, [rdi+18h]
0x1800038f7  lea     rcx, [rcx+rax*2]
0x1800038fb  cmp     rcx, rbp
0x1800038fe  jbe     short loc_180003929
0x180003900  cmp     qword ptr [rdi+20h], 8
0x180003905  jb      short loc_18000390A
0x180003907  mov     rbx, [rbx]
0x18000390a  sub     rbp, rbx
0x18000390d  mov     r9, r14
0x180003910  sar     rbp, 1
0x180003913  mov     rdx, rdi
0x180003916  mov     r8, rbp
0x180003919  mov     rcx, rdi
0x18000391c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180003921  mov     rdi, rax
0x180003924  jmp     loc_1800039D1
0x180003929  mov     rax, [rdi+18h]
0x18000392d  not     rax
0x180003930  cmp     rax, r14
0x180003933  ja      short loc_18000393A
0x180003935  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18000393a  test    r14, r14
0x18000393d  jz      loc_1800039D1
0x180003943  mov     rsi, [rdi+18h]
0x180003947  mov     rax, 7FFFFFFFFFFFFFFEh
0x180003951  add     rsi, r14
0x180003954  cmp     rsi, rax
0x180003957  jbe     short loc_18000395E
0x180003959  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18000395e  cmp     [rdi+20h], rsi
0x180003962  jnb     short loc_18000398B
0x180003964  mov     r8, [rdi+18h]
0x180003968  mov     rdx, rsi
0x18000396b  mov     rcx, rdi
0x18000396e  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180003973  test    rsi, rsi
0x180003976  jz      short loc_1800039D1
0x180003978  mov     rdx, [rdi+20h]
0x18000397c  mov     rcx, [rdi+18h]
0x180003980  cmp     rdx, 8
0x180003984  jb      short loc_1800039A4
0x180003986  mov     rax, [rbx]
0x180003989  jmp     short loc_1800039A7
0x18000398b  test    rsi, rsi
0x18000398e  jnz     short loc_180003978
0x180003990  cmp     qword ptr [rdi+20h], 8
0x180003995  jb      short loc_18000399A
0x180003997  mov     rbx, [rbx]
0x18000399a  mov     [rdi+18h], r15
0x18000399e  mov     [rbx], r15w
0x1800039a2  jmp     short loc_1800039D1
0x1800039a4  mov     rax, rbx
0x1800039a7  sub     rdx, rcx
0x1800039aa  lea     r9, [r14+r14]; SourceSize
0x1800039ae  add     rdx, rdx; DestinationSize
0x1800039b1  lea     rcx, [rax+rcx*2]; Destination
0x1800039b5  mov     r8, rbp; Source
0x1800039b8  call    cs:__imp_memcpy_s
0x1800039be  cmp     qword ptr [rdi+20h], 8
0x1800039c3  jb      short loc_1800039C8
0x1800039c5  mov     rbx, [rbx]
0x1800039c8  mov     [rdi+18h], rsi
0x1800039cc  mov     [rbx+rsi*2], r15w
0x1800039d1  mov     rax, rdi
0x1800039d4  add     rsp, 28h
0x1800039d8  pop     r15
0x1800039da  pop     r14
0x1800039dc  pop     rdi
0x1800039dd  pop     rsi
0x1800039de  pop     rbp
0x1800039df  pop     rbx
0x1800039e0  retn
```
