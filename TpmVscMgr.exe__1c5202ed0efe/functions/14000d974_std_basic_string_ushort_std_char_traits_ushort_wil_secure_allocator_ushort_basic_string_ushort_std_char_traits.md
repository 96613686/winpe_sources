# std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)

- ea: `0x14000d974`
- end: `0x14000da9a`
- name: `??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z`
- size: `294`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x140001250`
- `0x140001280`
- `0x1400012b0`
- `0x14000ded8`
- `0x14000f280`
- `0x14000f54c`
- `0x140010a68`
- `0x140010c90`
- `0x140010de0`

## callees

- `0x140001990`
- `0x14000b04c`
- `0x14000b1ec`
- `0x14000d974`
- `0x140011524`

## pseudocode

```c
_QWORD *__fastcall std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
        _QWORD *a1,
        _WORD *a2)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  size_t v6; // rbx
  size_t v7; // rcx
  void *v8; // rax
  _QWORD *v9; // rsi
  size_t v10; // rbx

  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( (v4 | 7) < 0xA )
        v5 = 10;
      if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_22;
      v7 = 2 * (v5 + 1);
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v7 = -2;
    }
    if ( v7 >= 0x1000 )
    {
      if ( v7 + 39 >= v7 )
      {
        v8 = operator new(v7 + 39);
        if ( !v8 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v7);
LABEL_19:
    a1[2] = v4;
    v10 = 2 * v4;
    *a1 = v9;
    a1[3] = v5;
    memcpy_0(v9, a2, v10);
    *(_WORD *)((char *)v9 + v10) = 0;
    return a1;
  }
  a1[2] = v4;
  v6 = 2 * v4;
  a1[3] = 7;
  memcpy_0(a1, a2, v6);
  *(_WORD *)((char *)a1 + v6) = 0;
  return a1;
}

```

## disassembly

```asm
0x14000d974  push    rbx
0x14000d976  push    rbp
0x14000d977  push    rsi
0x14000d978  push    rdi
0x14000d979  push    r14
0x14000d97b  push    r15
0x14000d97d  sub     rsp, 28h
0x14000d981  xor     r15d, r15d
0x14000d984  xorps   xmm0, xmm0
0x14000d987  movups  xmmword ptr [rcx], xmm0
0x14000d98a  mov     [rcx+10h], r15
0x14000d98e  mov     r14, rdx
0x14000d991  mov     [rcx+18h], r15
0x14000d995  mov     rdi, rcx
0x14000d998  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000d99c  inc     rbx
0x14000d99f  cmp     [rdx+rbx*2], r15w
0x14000d9a4  jnz     short loc_14000D99C
0x14000d9a6  mov     rbp, 7FFFFFFFFFFFFFFEh
0x14000d9b0  cmp     rbx, rbp
0x14000d9b3  ja      loc_14000DA8E
0x14000d9b9  cmp     rbx, 7
0x14000d9bd  ja      short loc_14000D9E0
0x14000d9bf  mov     [rcx+10h], rbx
0x14000d9c3  add     rbx, rbx
0x14000d9c6  mov     r8, rbx; Size
0x14000d9c9  mov     qword ptr [rcx+18h], 7
0x14000d9d1  call    memcpy_0
0x14000d9d6  mov     [rbx+rdi], r15w
0x14000d9db  jmp     loc_14000DA7E
0x14000d9e0  mov     rax, rbx
0x14000d9e3  or      rax, 7
0x14000d9e7  cmp     rax, rbp
0x14000d9ea  jbe     short loc_14000DA1B
0x14000d9ec  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x14000d9f3  cmp     rcx, 1000h
0x14000d9fa  jb      short loc_14000DA55
0x14000d9fc  lea     rax, [rcx+27h]
0x14000da00  cmp     rax, rcx
0x14000da03  jbe     loc_14000DA94
0x14000da09  mov     rcx, rax; Size
0x14000da0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000da11  test    rax, rax
0x14000da14  jnz     short loc_14000DA47
0x14000da16  lea     ecx, [rax+5]
0x14000da19  int     29h; Win8: RtlFailFast(ecx)
0x14000da1b  mov     ecx, 0Ah
0x14000da20  mov     rbp, rax
0x14000da23  cmp     rax, rcx
0x14000da26  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000da30  cmovb   rbp, rcx
0x14000da34  lea     rcx, [rbp+1]
0x14000da38  cmp     rcx, rax
0x14000da3b  ja      short loc_14000DA94
0x14000da3d  add     rcx, rcx
0x14000da40  jnz     short loc_14000D9F3
0x14000da42  mov     rsi, r15
0x14000da45  jmp     short loc_14000DA5D
0x14000da47  lea     rsi, [rax+27h]
0x14000da4b  and     rsi, 0FFFFFFFFFFFFFFE0h
0x14000da4f  mov     [rsi-8], rax
0x14000da53  jmp     short loc_14000DA5D
0x14000da55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000da5a  mov     rsi, rax
0x14000da5d  mov     [rdi+10h], rbx
0x14000da61  mov     rdx, r14; Src
0x14000da64  add     rbx, rbx
0x14000da67  mov     [rdi], rsi
0x14000da6a  mov     r8, rbx; Size
0x14000da6d  mov     [rdi+18h], rbp
0x14000da71  mov     rcx, rsi; void *
0x14000da74  call    memcpy_0
0x14000da79  mov     [rbx+rsi], r15w
0x14000da7e  mov     rax, rdi
0x14000da81  add     rsp, 28h
0x14000da85  pop     r15
0x14000da87  pop     r14
0x14000da89  pop     rdi
0x14000da8a  pop     rsi
0x14000da8b  pop     rbp
0x14000da8c  pop     rbx
0x14000da8d  retn
0x14000da8e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000da94  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
