# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x14000c13c`
- end: `0x14000c22a`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `238`
- prototype: `void *__fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14000c430`
- `0x14000d75c`
- `0x14000d820`

## callees

- `0x14000367c`
- `0x140003f74`
- `0x14000c13c`
- `0x14000d4f4`
- `0x14000d59c`
- `0x14000d644`

## pseudocode

```c
void *__fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v6; // rbx
  void *result; // rax
  __int64 v8; // r15
  size_t v9; // rcx
  _QWORD *v10; // rdi
  void *v11; // rax
  size_t v12; // rbx

  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 <= 7 )
  {
    a1[2] = a3;
    v6 = 2 * a3;
    a1[3] = 7;
    result = memcpy_0(a1, a2, 2 * a3);
    *(_WORD *)((char *)a1 + v6) = 0;
    return result;
  }
  v8 = std::wstring::_Calculate_growth(a3);
  if ( (unsigned __int64)(v8 + 1) > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_15;
  v9 = 2 * (v8 + 1);
  if ( v9 )
  {
    if ( v9 < 0x1000 )
    {
      v10 = operator new(v9);
      goto LABEL_13;
    }
    if ( v9 + 39 >= v9 )
    {
      v11 = operator new(v9 + 39);
      if ( !v11 )
        __fastfail(5u);
      v10 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v10 - 1) = v11;
      goto LABEL_13;
    }
LABEL_15:
    std::_Throw_bad_array_new_length();
  }
  v10 = 0;
LABEL_13:
  a1[2] = a3;
  v12 = 2 * a3;
  *a1 = v10;
  a1[3] = v8;
  result = memcpy_0(v10, a2, v12);
  *(_WORD *)((char *)v10 + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x14000c13c  push    rbx
0x14000c13e  push    rbp
0x14000c13f  push    rsi
0x14000c140  push    rdi
0x14000c141  push    r14
0x14000c143  push    r15
0x14000c145  sub     rsp, 28h
0x14000c149  mov     rbx, r8
0x14000c14c  mov     rbp, rdx
0x14000c14f  mov     r8, 7FFFFFFFFFFFFFFEh
0x14000c159  mov     r14, rcx
0x14000c15c  cmp     rbx, r8
0x14000c15f  ja      loc_14000C21E
0x14000c165  cmp     rbx, 7
0x14000c169  ja      short loc_14000C196
0x14000c16b  mov     [rcx+10h], rbx
0x14000c16f  add     rbx, rbx
0x14000c172  mov     r8, rbx; Size
0x14000c175  mov     qword ptr [rcx+18h], 7
0x14000c17d  call    memcpy_0
0x14000c182  xor     esi, esi
0x14000c184  mov     [rbx+r14], si
0x14000c189  add     rsp, 28h
0x14000c18d  pop     r15
0x14000c18f  pop     r14
0x14000c191  pop     rdi
0x14000c192  pop     rsi
0x14000c193  pop     rbp
0x14000c194  pop     rbx
0x14000c195  retn
0x14000c196  mov     rcx, rbx
0x14000c199  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x14000c19e  mov     r15, rax
0x14000c1a1  lea     rcx, [rax+1]
0x14000c1a5  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000c1af  cmp     rcx, rax
0x14000c1b2  ja      short loc_14000C224
0x14000c1b4  xor     esi, esi
0x14000c1b6  add     rcx, rcx; Size
0x14000c1b9  jnz     short loc_14000C1BF
0x14000c1bb  mov     edi, esi
0x14000c1bd  jmp     short loc_14000C1F9
0x14000c1bf  cmp     rcx, 1000h
0x14000c1c6  jb      short loc_14000C1F1
0x14000c1c8  lea     rax, [rcx+27h]
0x14000c1cc  cmp     rax, rcx
0x14000c1cf  jbe     short loc_14000C224
0x14000c1d1  mov     rcx, rax; Size
0x14000c1d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c1d9  test    rax, rax
0x14000c1dc  jnz     short loc_14000C1E3
0x14000c1de  lea     ecx, [rax+5]
0x14000c1e1  int     29h; Win8: RtlFailFast(ecx)
0x14000c1e3  lea     rdi, [rax+27h]
0x14000c1e7  and     rdi, 0FFFFFFFFFFFFFFE0h
0x14000c1eb  mov     [rdi-8], rax
0x14000c1ef  jmp     short loc_14000C1F9
0x14000c1f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c1f6  mov     rdi, rax
0x14000c1f9  mov     [r14+10h], rbx
0x14000c1fd  mov     rdx, rbp; Src
0x14000c200  add     rbx, rbx
0x14000c203  mov     [r14], rdi
0x14000c206  mov     r8, rbx; Size
0x14000c209  mov     [r14+18h], r15
0x14000c20d  mov     rcx, rdi; void *
0x14000c210  call    memcpy_0
0x14000c215  mov     [rbx+rdi], si
0x14000c219  jmp     loc_14000C189
0x14000c21e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000c224  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
