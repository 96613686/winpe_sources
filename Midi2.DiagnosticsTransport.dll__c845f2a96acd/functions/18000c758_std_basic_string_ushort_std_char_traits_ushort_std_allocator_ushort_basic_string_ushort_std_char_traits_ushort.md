# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000c758`
- end: `0x18000c86c`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cb4c`
- `0x18000ccf8`
- `0x18000d31c`

## callees

- `0x180003420`
- `0x180004158`
- `0x18000c758`
- `0x180010038`
- `0x180010060`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
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
0x18000c758  push    rbx
0x18000c75a  push    rbp
0x18000c75b  push    rsi
0x18000c75c  push    rdi
0x18000c75d  sub     rsp, 28h
0x18000c761  xorps   xmm0, xmm0
0x18000c764  mov     rbx, rcx
0x18000c767  movups  xmmword ptr [rcx], xmm0
0x18000c76a  mov     qword ptr [rcx+10h], 0
0x18000c772  mov     rsi, rdx
0x18000c775  mov     qword ptr [rcx+18h], 0
0x18000c77d  mov     ecx, 7
0x18000c782  mov     rdi, [rdx+10h]
0x18000c786  cmp     [rdx+18h], rcx
0x18000c78a  jbe     short loc_18000C78F
0x18000c78c  mov     rsi, [rdx]
0x18000c78f  mov     rbp, 7FFFFFFFFFFFFFFEh
0x18000c799  cmp     rdi, rbp
0x18000c79c  ja      loc_18000C860
0x18000c7a2  cmp     rdi, rcx
0x18000c7a5  ja      short loc_18000C7BB
0x18000c7a7  mov     [rbx+10h], rdi
0x18000c7ab  mov     [rbx+18h], rcx
0x18000c7af  movups  xmm0, xmmword ptr [rsi]
0x18000c7b2  movdqu  xmmword ptr [rbx], xmm0
0x18000c7b6  jmp     loc_18000C854
0x18000c7bb  mov     rax, rdi
0x18000c7be  or      rax, rcx
0x18000c7c1  cmp     rax, rbp
0x18000c7c4  jbe     short loc_18000C7F8
0x18000c7c6  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000c7cd  cmp     rcx, 1000h
0x18000c7d4  jb      short loc_18000C831
0x18000c7d6  lea     rax, [rcx+27h]
0x18000c7da  cmp     rax, rcx
0x18000c7dd  jbe     loc_18000C866
0x18000c7e3  mov     rcx, rax; Size
0x18000c7e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c7eb  mov     rcx, rax
0x18000c7ee  test    rax, rax
0x18000c7f1  jnz     short loc_18000C823
0x18000c7f3  lea     ecx, [rax+5]
0x18000c7f6  int     29h; Win8: RtlFailFast(ecx)
0x18000c7f8  mov     ecx, 0Ah
0x18000c7fd  mov     rbp, rax
0x18000c800  cmp     rax, rcx
0x18000c803  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c80d  cmovb   rbp, rcx
0x18000c811  lea     rcx, [rbp+1]
0x18000c815  cmp     rcx, rax
0x18000c818  ja      short loc_18000C866
0x18000c81a  add     rcx, rcx
0x18000c81d  jnz     short loc_18000C7CD
0x18000c81f  xor     eax, eax
0x18000c821  jmp     short loc_18000C836
0x18000c823  add     rax, 27h ; '''
0x18000c827  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000c82b  mov     [rax-8], rcx
0x18000c82f  jmp     short loc_18000C836
0x18000c831  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c836  lea     r8, ds:2[rdi*2]; Size
0x18000c83e  mov     [rbx], rax
0x18000c841  mov     rdx, rsi; Src
0x18000c844  mov     [rbx+10h], rdi
0x18000c848  mov     rcx, rax; void *
0x18000c84b  mov     [rbx+18h], rbp
0x18000c84f  call    memcpy_0
0x18000c854  mov     rax, rbx
0x18000c857  add     rsp, 28h
0x18000c85b  pop     rdi
0x18000c85c  pop     rsi
0x18000c85d  pop     rbp
0x18000c85e  pop     rbx
0x18000c85f  retn
0x18000c860  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000c866  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
