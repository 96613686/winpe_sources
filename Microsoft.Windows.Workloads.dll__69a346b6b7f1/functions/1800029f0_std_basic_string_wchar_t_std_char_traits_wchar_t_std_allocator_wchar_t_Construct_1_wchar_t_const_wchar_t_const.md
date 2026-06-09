# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x1800029f0`
- end: `0x180002acd`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `26`
- callee_count: `5`
- tags: ``

## callers

- `0x1800025f0`
- `0x180002ad0`
- `0x1800058e0`
- `0x180007a20`
- `0x180008700`
- `0x180008a50`
- `0x180008c60`
- `0x180013ed0`
- `0x1800143f0`
- `0x180014870`
- `0x180015b30`
- `0x180016760`
- `0x180017340`
- `0x180017680`
- `0x180017910`
- `0x18001b9a0`
- `0x18001cc10`
- `0x18001d320`
- `0x18001d8e0`
- `0x18001dae0`
- `0x18001eb00`
- `0x180021b10`
- `0x180023400`
- `0x180026050`
- `0x1800271c0`
- `0x180028a70`

## callees

- `0x180002860`
- `0x180002880`
- `0x1800029d0`
- `0x1800029f0`
- `0x18003c020`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,wchar_t const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rbp
  __int64 v7; // rbx
  __int64 result; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  size_t v11; // rbx
  _QWORD *v12; // rdi

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( (a3 | 7) < 0xA )
        v3 = 10;
      v9 = v3 + 1;
      if ( (unsigned __int64)(v3 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v9 = 0x7FFFFFFFFFFFFFFFLL;
    }
    _mm_lfence();
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(2 * v9);
    a1[2] = a3;
    v11 = 2 * a3;
    *a1 = v10;
    a1[3] = v3;
    v12 = v10;
    memmove(v10, a2, v11);
    result = 0;
    *(_WORD *)((char *)v12 + v11) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    memmove(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800029f0  push    rbx
0x1800029f2  push    rbp
0x1800029f3  push    rsi
0x1800029f4  push    r14
0x1800029f6  sub     rsp, 28h
0x1800029fa  mov     rbp, 7FFFFFFFFFFFFFFEh
0x180002a04  mov     rbx, r8
0x180002a07  mov     r14, rdx
0x180002a0a  mov     rsi, rcx
0x180002a0d  cmp     r8, rbp
0x180002a10  ja      loc_180002AC1
0x180002a16  cmp     rbx, 7
0x180002a1a  ja      short loc_180002A43
0x180002a1c  mov     [rcx+10h], rbx
0x180002a20  add     rbx, rbx
0x180002a23  mov     r8, rbx; Size
0x180002a26  mov     qword ptr [rcx+18h], 7
0x180002a2e  call    memmove
0x180002a33  xor     eax, eax
0x180002a35  mov     [rbx+rsi], ax
0x180002a39  add     rsp, 28h
0x180002a3d  pop     r14
0x180002a3f  pop     rsi
0x180002a40  pop     rbp
0x180002a41  pop     rbx
0x180002a42  retn
0x180002a43  mov     rax, rbx
0x180002a46  or      rax, 7
0x180002a4a  cmp     rax, rbp
0x180002a4d  jbe     short loc_180002A9D
0x180002a4f  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180002a59  mov     [rsp+48h+var_28], rdi
0x180002a5e  lfence
0x180002a61  add     rcx, rcx
0x180002a64  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180002a69  mov     [rsi+10h], rbx
0x180002a6d  mov     rdx, r14; Src
0x180002a70  add     rbx, rbx
0x180002a73  mov     [rsi], rax
0x180002a76  mov     r8, rbx; Size
0x180002a79  mov     [rsi+18h], rbp
0x180002a7d  mov     rcx, rax; void *
0x180002a80  mov     rdi, rax
0x180002a83  call    memmove
0x180002a88  xor     eax, eax
0x180002a8a  mov     [rbx+rdi], ax
0x180002a8e  mov     rdi, [rsp+48h+var_28]
0x180002a93  add     rsp, 28h
0x180002a97  pop     r14
0x180002a99  pop     rsi
0x180002a9a  pop     rbp
0x180002a9b  pop     rbx
0x180002a9c  retn
0x180002a9d  mov     ecx, 0Ah
0x180002aa2  mov     rbp, rax
0x180002aa5  cmp     rax, rcx
0x180002aa8  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002ab2  cmovb   rbp, rcx
0x180002ab6  lea     rcx, [rbp+1]
0x180002aba  cmp     rcx, rax
0x180002abd  ja      short loc_180002AC7
0x180002abf  jmp     short loc_180002A59
0x180002ac1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180002ac7  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
