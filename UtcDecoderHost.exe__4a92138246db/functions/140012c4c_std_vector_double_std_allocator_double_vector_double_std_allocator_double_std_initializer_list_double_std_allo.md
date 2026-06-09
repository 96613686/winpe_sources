# std::vector<double,std::allocator<double>>::vector<double,std::allocator<double>>(std::initializer_list<double>,std::allocator<double> const &)

- ea: `0x140012c4c`
- end: `0x140012d4b`
- name: `??0?$vector@NV?$allocator@N@std@@@std@@QEAA@V?$initializer_list@N@1@AEBV?$allocator@N@1@@Z`
- size: `255`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140001cf0`
- `0x140001db0`
- `0x140001e50`
- `0x140001f20`
- `0x140001fc0`
- `0x140002060`

## callees

- `0x14000892c`
- `0x140009533`
- `0x14000d918`
- `0x140012c4c`
- `0x140012ec8`
- `0x140016274`

## pseudocode

```c
_QWORD *__fastcall std::vector<double>::vector<double>(_QWORD *a1, __int64 a2, __int64 a3)
{
  const void *v3; // r14
  signed __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  size_t v7; // rdi
  _QWORD *v8; // rbx
  void *v9; // rax
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = a3;
  v3 = *(const void **)a2;
  v5 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
  *a1 = 0;
  a1[1] = 0;
  v6 = v5 >> 3;
  a1[2] = 0;
  if ( v5 >> 3 )
  {
    if ( v6 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<double>::_Xlength();
    v7 = 8 * v6;
    if ( v7 )
    {
      if ( v7 < 0x1000 )
      {
        v8 = operator new(v7);
      }
      else
      {
        if ( v7 + 39 < v7 )
          __scrt_throw_std_bad_array_new_length();
        v9 = operator new(v7 + 39);
        if ( !v9 )
          __fastfail(5u);
        v8 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v8 - 1) = v9;
      }
    }
    else
    {
      v8 = 0;
    }
    *a1 = v8;
    a1[1] = v8;
    a1[2] = &v8[v7 / 8];
    memmove_0(v8, v3, v5);
    v11 = 0;
    a1[1] = &v8[v7 / 8];
    std::_Tidy_guard<std::vector<double>>::~_Tidy_guard<std::vector<double>>(&v11);
  }
  return a1;
}

```

## disassembly

```asm
0x140012c4c  mov     [rsp+arg_0], rbx
0x140012c51  mov     [rsp+arg_8], rbp
0x140012c56  mov     [rsp+arg_10], r8
0x140012c5b  push    rsi
0x140012c5c  push    rdi
0x140012c5d  push    r14
0x140012c5f  sub     rsp, 20h
0x140012c63  mov     r14, [rdx]
0x140012c66  mov     rsi, rcx
0x140012c69  mov     rbp, [rdx+8]
0x140012c6d  sub     rbp, r14
0x140012c70  mov     qword ptr [rcx], 0
0x140012c77  mov     rdi, rbp
0x140012c7a  mov     qword ptr [rcx+8], 0
0x140012c82  sar     rdi, 3
0x140012c86  mov     qword ptr [rcx+10h], 0
0x140012c8e  test    rdi, rdi
0x140012c91  jz      loc_140012D29
0x140012c97  mov     rax, 1FFFFFFFFFFFFFFFh
0x140012ca1  cmp     rdi, rax
0x140012ca4  ja      loc_140012D45
0x140012caa  shl     rdi, 3
0x140012cae  test    rdi, rdi
0x140012cb1  jnz     short loc_140012CB7
0x140012cb3  xor     ebx, ebx
0x140012cb5  jmp     short loc_140012CF1
0x140012cb7  cmp     rdi, 1000h
0x140012cbe  jb      short loc_140012CE6
0x140012cc0  lea     rcx, [rdi+27h]; Size
0x140012cc4  cmp     rcx, rdi
0x140012cc7  jbe     short loc_140012D3F
0x140012cc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012cce  test    rax, rax
0x140012cd1  jnz     short loc_140012CD8
0x140012cd3  lea     ecx, [rax+5]
0x140012cd6  int     29h; Win8: RtlFailFast(ecx)
0x140012cd8  lea     rbx, [rax+27h]
0x140012cdc  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140012ce0  mov     [rbx-8], rax
0x140012ce4  jmp     short loc_140012CF1
0x140012ce6  mov     rcx, rdi; Size
0x140012ce9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012cee  mov     rbx, rax
0x140012cf1  mov     [rsi], rbx
0x140012cf4  lea     rcx, [rdi+rbx]
0x140012cf8  mov     [rsi+8], rbx
0x140012cfc  mov     r8, rbp; Size
0x140012cff  mov     [rsi+10h], rcx
0x140012d03  mov     rdx, r14; Src
0x140012d06  mov     rcx, rbx; void *
0x140012d09  call    memmove_0
0x140012d0e  lea     rax, [rdi+rbx]
0x140012d12  mov     [rsp+38h+arg_10], 0
0x140012d1b  lea     rcx, [rsp+38h+arg_10]
0x140012d20  mov     [rsi+8], rax
0x140012d24  call    ??1?$_Tidy_guard@V?$vector@NV?$allocator@N@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<double>>::~_Tidy_guard<std::vector<double>>(void)
0x140012d29  mov     rbx, [rsp+38h+arg_0]
0x140012d2e  mov     rax, rsi
0x140012d31  mov     rbp, [rsp+38h+arg_8]
0x140012d36  add     rsp, 20h
0x140012d3a  pop     r14
0x140012d3c  pop     rdi
0x140012d3d  pop     rsi
0x140012d3e  retn
0x140012d3f  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x140012d45  call    ?_Xlength@?$vector@NV?$allocator@N@std@@@std@@CAXXZ; std::vector<double>::_Xlength(void)
```
