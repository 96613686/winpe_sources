# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x1400067e8`
- end: `0x1400068eb`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `259`
- prototype: `void *__fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140007210`
- `0x140007778`
- `0x14000bf30`
- `0x14000eb60`

## callees

- `0x140001990`
- `0x1400067e8`
- `0x14000b04c`
- `0x14000b1ec`
- `0x140011524`

## pseudocode

```c
void *__fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rbp
  __int64 v7; // rbx
  void *result; // rax
  size_t v9; // rcx
  void *v10; // rax
  _QWORD *v11; // rdi
  size_t v12; // rbx

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 <= 7 )
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    result = memcpy_0(a1, a2, 2 * a3);
    *(_WORD *)((char *)a1 + v7) = 0;
    return result;
  }
  if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v3 = a3 | 7;
    if ( (a3 | 7) < 0xA )
      v3 = 10;
    if ( (unsigned __int64)(v3 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_19;
    v9 = 2 * (v3 + 1);
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_17;
    }
  }
  else
  {
    v9 = -2;
  }
  if ( v9 >= 0x1000 )
  {
    if ( v9 + 39 >= v9 )
    {
      v10 = operator new(v9 + 39);
      if ( !v10 )
        __fastfail(5u);
      v11 = (_QWORD *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v11 - 1) = v10;
      goto LABEL_17;
    }
LABEL_19:
    __scrt_throw_std_bad_array_new_length();
  }
  v11 = operator new(v9);
LABEL_17:
  a1[2] = a3;
  v12 = 2 * a3;
  *a1 = v11;
  a1[3] = v3;
  result = memcpy_0(v11, a2, v12);
  *(_WORD *)((char *)v11 + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x1400067e8  push    rbx
0x1400067ea  push    rbp
0x1400067eb  push    rsi
0x1400067ec  push    rdi
0x1400067ed  push    r14
0x1400067ef  push    r15
0x1400067f1  sub     rsp, 28h
0x1400067f5  mov     rbp, 7FFFFFFFFFFFFFFEh
0x1400067ff  mov     rbx, r8
0x140006802  mov     r15, rdx
0x140006805  mov     r14, rcx
0x140006808  cmp     r8, rbp
0x14000680b  ja      loc_1400068DF
0x140006811  cmp     rbx, 7
0x140006815  ja      short loc_140006842
0x140006817  mov     [rcx+10h], rbx
0x14000681b  add     rbx, rbx
0x14000681e  mov     r8, rbx; Size
0x140006821  mov     qword ptr [rcx+18h], 7
0x140006829  call    memcpy_0
0x14000682e  xor     esi, esi
0x140006830  mov     [rbx+r14], si
0x140006835  add     rsp, 28h
0x140006839  pop     r15
0x14000683b  pop     r14
0x14000683d  pop     rdi
0x14000683e  pop     rsi
0x14000683f  pop     rbp
0x140006840  pop     rbx
0x140006841  retn
0x140006842  mov     rax, rbx
0x140006845  xor     esi, esi
0x140006847  or      rax, 7
0x14000684b  cmp     rax, rbp
0x14000684e  jbe     short loc_140006878
0x140006850  lea     rcx, [rsi-2]; Size
0x140006854  cmp     rcx, 1000h
0x14000685b  jb      short loc_1400068B2
0x14000685d  lea     rax, [rcx+27h]
0x140006861  cmp     rax, rcx
0x140006864  jbe     short loc_1400068E5
0x140006866  mov     rcx, rax; Size
0x140006869  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000686e  test    rax, rax
0x140006871  jnz     short loc_1400068A4
0x140006873  lea     ecx, [rax+5]
0x140006876  int     29h; Win8: RtlFailFast(ecx)
0x140006878  mov     ecx, 0Ah
0x14000687d  mov     rbp, rax
0x140006880  cmp     rax, rcx
0x140006883  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000688d  cmovb   rbp, rcx
0x140006891  lea     rcx, [rbp+1]
0x140006895  cmp     rcx, rax
0x140006898  ja      short loc_1400068E5
0x14000689a  add     rcx, rcx
0x14000689d  jnz     short loc_140006854
0x14000689f  mov     rdi, rsi
0x1400068a2  jmp     short loc_1400068BA
0x1400068a4  lea     rdi, [rax+27h]
0x1400068a8  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1400068ac  mov     [rdi-8], rax
0x1400068b0  jmp     short loc_1400068BA
0x1400068b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400068b7  mov     rdi, rax
0x1400068ba  mov     [r14+10h], rbx
0x1400068be  mov     rdx, r15; Src
0x1400068c1  add     rbx, rbx
0x1400068c4  mov     [r14], rdi
0x1400068c7  mov     r8, rbx; Size
0x1400068ca  mov     [r14+18h], rbp
0x1400068ce  mov     rcx, rdi; void *
0x1400068d1  call    memcpy_0
0x1400068d6  mov     [rbx+rdi], si
0x1400068da  jmp     loc_140006835
0x1400068df  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1400068e5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
