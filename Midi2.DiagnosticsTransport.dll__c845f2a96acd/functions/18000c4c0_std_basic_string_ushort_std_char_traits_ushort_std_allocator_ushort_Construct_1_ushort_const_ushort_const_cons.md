# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x18000c4c0`
- end: `0x18000c5c3`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `259`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ccf8`
- `0x18000d0b4`
- `0x18000d31c`
- `0x18000f1e4`
- `0x18000f4f0`
- `0x180010b70`
- `0x180011630`
- `0x1800117e8`

## callees

- `0x180003420`
- `0x180004158`
- `0x18000c4c0`
- `0x180010038`
- `0x180010060`

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
0x18000c4c0  push    rbx
0x18000c4c2  push    rbp
0x18000c4c3  push    rsi
0x18000c4c4  push    rdi
0x18000c4c5  push    r14
0x18000c4c7  push    r15
0x18000c4c9  sub     rsp, 28h
0x18000c4cd  mov     rbp, 7FFFFFFFFFFFFFFEh
0x18000c4d7  mov     rbx, r8
0x18000c4da  mov     r15, rdx
0x18000c4dd  mov     r14, rcx
0x18000c4e0  cmp     r8, rbp
0x18000c4e3  ja      loc_18000C5B7
0x18000c4e9  cmp     rbx, 7
0x18000c4ed  ja      short loc_18000C51A
0x18000c4ef  mov     [rcx+10h], rbx
0x18000c4f3  add     rbx, rbx
0x18000c4f6  mov     r8, rbx; Size
0x18000c4f9  mov     qword ptr [rcx+18h], 7
0x18000c501  call    memcpy_0
0x18000c506  xor     esi, esi
0x18000c508  mov     [rbx+r14], si
0x18000c50d  add     rsp, 28h
0x18000c511  pop     r15
0x18000c513  pop     r14
0x18000c515  pop     rdi
0x18000c516  pop     rsi
0x18000c517  pop     rbp
0x18000c518  pop     rbx
0x18000c519  retn
0x18000c51a  mov     rax, rbx
0x18000c51d  xor     esi, esi
0x18000c51f  or      rax, 7
0x18000c523  cmp     rax, rbp
0x18000c526  jbe     short loc_18000C550
0x18000c528  lea     rcx, [rsi-2]; Size
0x18000c52c  cmp     rcx, 1000h
0x18000c533  jb      short loc_18000C58A
0x18000c535  lea     rax, [rcx+27h]
0x18000c539  cmp     rax, rcx
0x18000c53c  jbe     short loc_18000C5BD
0x18000c53e  mov     rcx, rax; Size
0x18000c541  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c546  test    rax, rax
0x18000c549  jnz     short loc_18000C57C
0x18000c54b  lea     ecx, [rax+5]
0x18000c54e  int     29h; Win8: RtlFailFast(ecx)
0x18000c550  mov     ecx, 0Ah
0x18000c555  mov     rbp, rax
0x18000c558  cmp     rax, rcx
0x18000c55b  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c565  cmovb   rbp, rcx
0x18000c569  lea     rcx, [rbp+1]
0x18000c56d  cmp     rcx, rax
0x18000c570  ja      short loc_18000C5BD
0x18000c572  add     rcx, rcx
0x18000c575  jnz     short loc_18000C52C
0x18000c577  mov     rdi, rsi
0x18000c57a  jmp     short loc_18000C592
0x18000c57c  lea     rdi, [rax+27h]
0x18000c580  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000c584  mov     [rdi-8], rax
0x18000c588  jmp     short loc_18000C592
0x18000c58a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c58f  mov     rdi, rax
0x18000c592  mov     [r14+10h], rbx
0x18000c596  mov     rdx, r15; Src
0x18000c599  add     rbx, rbx
0x18000c59c  mov     [r14], rdi
0x18000c59f  mov     r8, rbx; Size
0x18000c5a2  mov     [r14+18h], rbp
0x18000c5a6  mov     rcx, rdi; void *
0x18000c5a9  call    memcpy_0
0x18000c5ae  mov     [rbx+rdi], si
0x18000c5b2  jmp     loc_18000C50D
0x18000c5b7  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000c5bd  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
