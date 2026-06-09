# std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &)

- ea: `0x14000d858`
- end: `0x14000d96c`
- name: `??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@AEBV01@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d5a8`
- `0x14000ded8`
- `0x14000f280`
- `0x14000f54c`
- `0x140010a68`
- `0x140010c90`

## callees

- `0x140001990`
- `0x14000b04c`
- `0x14000b1ec`
- `0x14000d858`
- `0x140011524`

## pseudocode

```c
__int64 __fastcall std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
        __int64 a1,
        __int64 a2)
{
  _OWORD *v3; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rbp
  size_t v6; // rcx
  void *v7; // rax
  void *v8; // rcx
  _QWORD *v9; // rax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = (_OWORD *)a2;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v3 = *(_OWORD **)a2;
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
      v6 = 2 * (v5 + 1);
      if ( !v6 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v6 = -2;
    }
    if ( v6 >= 0x1000 )
    {
      if ( v6 + 39 >= v6 )
      {
        v7 = operator new(v6 + 39);
        v8 = v7;
        if ( !v7 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v6);
LABEL_19:
    *(_QWORD *)a1 = v9;
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = v5;
    memcpy_0(v9, v3, 2 * v4 + 2);
    return a1;
  }
  *(_QWORD *)(a1 + 16) = v4;
  *(_QWORD *)(a1 + 24) = 7;
  *(_OWORD *)a1 = *v3;
  return a1;
}

```

## disassembly

```asm
0x14000d858  push    rbx
0x14000d85a  push    rbp
0x14000d85b  push    rsi
0x14000d85c  push    rdi
0x14000d85d  sub     rsp, 28h
0x14000d861  xorps   xmm0, xmm0
0x14000d864  mov     rbx, rcx
0x14000d867  movups  xmmword ptr [rcx], xmm0
0x14000d86a  mov     qword ptr [rcx+10h], 0
0x14000d872  mov     rsi, rdx
0x14000d875  mov     qword ptr [rcx+18h], 0
0x14000d87d  mov     ecx, 7
0x14000d882  mov     rdi, [rdx+10h]
0x14000d886  cmp     [rdx+18h], rcx
0x14000d88a  jbe     short loc_14000D88F
0x14000d88c  mov     rsi, [rdx]
0x14000d88f  mov     rbp, 7FFFFFFFFFFFFFFEh
0x14000d899  cmp     rdi, rbp
0x14000d89c  ja      loc_14000D960
0x14000d8a2  cmp     rdi, rcx
0x14000d8a5  ja      short loc_14000D8BB
0x14000d8a7  mov     [rbx+10h], rdi
0x14000d8ab  mov     [rbx+18h], rcx
0x14000d8af  movups  xmm0, xmmword ptr [rsi]
0x14000d8b2  movdqu  xmmword ptr [rbx], xmm0
0x14000d8b6  jmp     loc_14000D954
0x14000d8bb  mov     rax, rdi
0x14000d8be  or      rax, rcx
0x14000d8c1  cmp     rax, rbp
0x14000d8c4  jbe     short loc_14000D8F8
0x14000d8c6  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x14000d8cd  cmp     rcx, 1000h
0x14000d8d4  jb      short loc_14000D931
0x14000d8d6  lea     rax, [rcx+27h]
0x14000d8da  cmp     rax, rcx
0x14000d8dd  jbe     loc_14000D966
0x14000d8e3  mov     rcx, rax; Size
0x14000d8e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d8eb  mov     rcx, rax
0x14000d8ee  test    rax, rax
0x14000d8f1  jnz     short loc_14000D923
0x14000d8f3  lea     ecx, [rax+5]
0x14000d8f6  int     29h; Win8: RtlFailFast(ecx)
0x14000d8f8  mov     ecx, 0Ah
0x14000d8fd  mov     rbp, rax
0x14000d900  cmp     rax, rcx
0x14000d903  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000d90d  cmovb   rbp, rcx
0x14000d911  lea     rcx, [rbp+1]
0x14000d915  cmp     rcx, rax
0x14000d918  ja      short loc_14000D966
0x14000d91a  add     rcx, rcx
0x14000d91d  jnz     short loc_14000D8CD
0x14000d91f  xor     eax, eax
0x14000d921  jmp     short loc_14000D936
0x14000d923  add     rax, 27h ; '''
0x14000d927  and     rax, 0FFFFFFFFFFFFFFE0h
0x14000d92b  mov     [rax-8], rcx
0x14000d92f  jmp     short loc_14000D936
0x14000d931  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d936  lea     r8, ds:2[rdi*2]; Size
0x14000d93e  mov     [rbx], rax
0x14000d941  mov     rdx, rsi; Src
0x14000d944  mov     [rbx+10h], rdi
0x14000d948  mov     rcx, rax; void *
0x14000d94b  mov     [rbx+18h], rbp
0x14000d94f  call    memcpy_0
0x14000d954  mov     rax, rbx
0x14000d957  add     rsp, 28h
0x14000d95b  pop     rdi
0x14000d95c  pop     rsi
0x14000d95d  pop     rbp
0x14000d95e  pop     rbx
0x14000d95f  retn
0x14000d960  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000d966  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
