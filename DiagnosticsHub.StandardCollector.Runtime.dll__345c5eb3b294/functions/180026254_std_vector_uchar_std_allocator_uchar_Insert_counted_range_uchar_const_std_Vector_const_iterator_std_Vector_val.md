# std::vector<uchar,std::allocator<uchar>>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)

- ea: `0x180026254`
- end: `0x1800263f6`
- name: `??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z`
- size: `418`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020ccc`
- `0x18002259c`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180026254`
- `0x18002706c`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180026308`
- `VCRUNTIME140!memmove` at `0x180026332`
- `VCRUNTIME140!memmove` at `0x180026348`
- `VCRUNTIME140!memmove` at `0x18002637d`
- `VCRUNTIME140!memmove` at `0x18002639a`
- `VCRUNTIME140!memmove` at `0x1800263a9`
- `VCRUNTIME140!memmove` at `0x1800263bb`
- `VCRUNTIME140!memmove` at `0x1800263d2`
- `VCRUNTIME140!memmove` at `0x180026308`
- `VCRUNTIME140!memmove` at `0x180026332`
- `VCRUNTIME140!memmove` at `0x180026348`
- `VCRUNTIME140!memmove` at `0x18002637d`
- `VCRUNTIME140!memmove` at `0x18002639a`
- `VCRUNTIME140!memmove` at `0x1800263a9`
- `VCRUNTIME140!memmove` at `0x1800263bb`
- `VCRUNTIME140!memmove` at `0x1800263d2`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
        __int64 a1,
        _BYTE *a2,
        const void *a3,
        size_t a4)
{
  _BYTE *v8; // r12
  _BYTE *v9; // rbp
  __int64 v10; // rcx
  signed __int64 v11; // r14
  __int64 v12; // rdi
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  char *v15; // r15
  size_t v16; // r8
  const void *v17; // rdx
  char *v18; // rcx
  size_t v19; // r14
  char *v20; // rdi
  char *v21; // rdi
  size_t Size; // [rsp+28h] [rbp-50h]
  size_t v24; // [rsp+30h] [rbp-48h]

  if ( a4 )
  {
    v8 = *(_BYTE **)a1;
    v9 = *(_BYTE **)(a1 + 8);
    v10 = *(_QWORD *)(a1 + 16);
    if ( a4 <= v10 - (__int64)v9 )
    {
      v19 = v9 - a2;
      _mm_lfence();
      if ( a4 >= v9 - a2 )
      {
        v21 = &a2[a4];
        memmove(&a2[a4], a2, v19);
        *(_QWORD *)(a1 + 8) = &v21[v19];
      }
      else
      {
        v20 = &v9[-a4];
        memmove(v9, &v9[-a4], a4);
        *(_QWORD *)(a1 + 8) = &v9[a4];
        memmove(&v9[-(v20 - a2)], a2, v20 - a2);
      }
      memmove(a2, a3, a4);
    }
    else
    {
      v11 = v9 - v8;
      v12 = 0x7FFFFFFFFFFFFFFFLL;
      if ( a4 > 0x7FFFFFFFFFFFFFFFLL - (v9 - v8) )
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(v10, a2);
      _mm_lfence();
      v24 = a4 + v11;
      v13 = v10 - (_QWORD)v8;
      v14 = v13 >> 1;
      if ( v13 <= 0x7FFFFFFFFFFFFFFFLL - (v13 >> 1) )
      {
        v12 = v14 + v13;
        if ( v14 + v13 < a4 + v11 )
          v12 = a4 + v11;
      }
      v15 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v12);
      Size = a2 - v8;
      memmove(&v15[a2 - v8], a3, a4);
      if ( a4 == 1 && a2 == v9 )
      {
        v16 = v9 - v8;
        v17 = v8;
        v18 = v15;
      }
      else
      {
        memmove(v15, v8, Size);
        v18 = &v15[a4 + Size];
        v16 = v9 - a2;
        v17 = a2;
      }
      memmove(v18, v17, v16);
      std::vector<unsigned char>::_Change_array(a1, v15, v24, v12);
    }
  }
}

```

## disassembly

```asm
0x180026254  test    r9, r9
0x180026257  jz      locret_1800263EF
0x18002625d  mov     [rsp+arg_8], rbx
0x180026262  push    rbp
0x180026263  push    rsi
0x180026264  push    rdi
0x180026265  push    r12
0x180026267  push    r13
0x180026269  push    r14
0x18002626b  push    r15
0x18002626d  sub     rsp, 40h
0x180026271  mov     rsi, r9
0x180026274  mov     r15, r8
0x180026277  mov     [rsp+78h+Src], r8
0x18002627c  mov     rbx, rdx
0x18002627f  mov     r13, rcx
0x180026282  mov     r12, [rcx]
0x180026285  mov     rbp, [rcx+8]
0x180026289  mov     rcx, [rcx+10h]
0x18002628d  mov     rax, rcx
0x180026290  sub     rax, rbp
0x180026293  mov     r14, rbp
0x180026296  cmp     r9, rax
0x180026299  jbe     loc_180026363
0x18002629f  sub     r14, r12
0x1800262a2  mov     rdi, 7FFFFFFFFFFFFFFFh
0x1800262ac  mov     rax, rdi
0x1800262af  sub     rax, r14
0x1800262b2  cmp     r9, rax
0x1800262b5  ja      loc_1800263F0
0x1800262bb  lfence
0x1800262be  lea     r8, [r9+r14]
0x1800262c2  mov     [rsp+78h+var_48], r8
0x1800262c7  sub     rcx, r12
0x1800262ca  mov     rdx, rcx
0x1800262cd  shr     rdx, 1
0x1800262d0  mov     rax, rdi
0x1800262d3  sub     rax, rdx
0x1800262d6  cmp     rcx, rax
0x1800262d9  ja      short loc_1800262E6
0x1800262db  lea     rdi, [rdx+rcx]
0x1800262df  cmp     rdi, r8
0x1800262e2  cmovb   rdi, r8
0x1800262e6  mov     rcx, rdi
0x1800262e9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800262ee  mov     r15, rax
0x1800262f1  mov     rax, rbx
0x1800262f4  sub     rax, r12
0x1800262f7  mov     [rsp+78h+Size], rax
0x1800262fc  lea     rcx, [rax+r15]; void *
0x180026300  mov     r8, rsi; Size
0x180026303  mov     rdx, [rsp+78h+Src]; Src
0x180026308  call    cs:__imp_memmove
0x18002630e  cmp     rsi, 1
0x180026312  jnz     short loc_180026324
0x180026314  cmp     rbx, rbp
0x180026317  jnz     short loc_180026324
0x180026319  mov     r8, r14
0x18002631c  mov     rdx, r12
0x18002631f  mov     rcx, r15
0x180026322  jmp     short loc_180026348
0x180026324  mov     r14, [rsp+78h+Size]
0x180026329  mov     r8, r14; Size
0x18002632c  mov     rdx, r12; Src
0x18002632f  mov     rcx, r15; void *
0x180026332  call    cs:__imp_memmove
0x180026338  sub     rbp, rbx
0x18002633b  lea     rcx, [rsi+r14]
0x18002633f  add     rcx, r15; void *
0x180026342  mov     r8, rbp; Size
0x180026345  mov     rdx, rbx; Src
0x180026348  call    cs:__imp_memmove
0x18002634e  mov     r9, rdi
0x180026351  mov     r8, [rsp+78h+var_48]
0x180026356  mov     rdx, r15
0x180026359  mov     rcx, r13
0x18002635c  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x180026361  jmp     short loc_1800263D8
0x180026363  sub     r14, rbx
0x180026366  lfence
0x180026369  cmp     rsi, r14
0x18002636c  jnb     short loc_1800263B1
0x18002636e  mov     rdi, rbp
0x180026371  sub     rdi, rsi
0x180026374  mov     r8, rsi; Size
0x180026377  mov     rdx, rdi; Src
0x18002637a  mov     rcx, rbp; void *
0x18002637d  call    cs:__imp_memmove
0x180026383  lea     rax, [rsi+rbp]
0x180026387  mov     [r13+8], rax
0x18002638b  sub     rdi, rbx
0x18002638e  sub     rbp, rdi
0x180026391  mov     r8, rdi; Size
0x180026394  mov     rdx, rbx; Src
0x180026397  mov     rcx, rbp; void *
0x18002639a  call    cs:__imp_memmove
0x1800263a0  mov     r8, rsi; Size
0x1800263a3  mov     rdx, r15; Src
0x1800263a6  mov     rcx, rbx; void *
0x1800263a9  call    cs:__imp_memmove
0x1800263af  jmp     short loc_1800263D8
0x1800263b1  lea     rdi, [r9+rdx]
0x1800263b5  mov     r8, r14; Size
0x1800263b8  mov     rcx, rdi; void *
0x1800263bb  call    cs:__imp_memmove
0x1800263c1  lea     rax, [r14+rdi]
0x1800263c5  mov     [r13+8], rax
0x1800263c9  mov     r8, rsi; Size
0x1800263cc  mov     rdx, r15; Src
0x1800263cf  mov     rcx, rbx; void *
0x1800263d2  call    cs:__imp_memmove
0x1800263d8  mov     rbx, [rsp+78h+arg_8]
0x1800263e0  add     rsp, 40h
0x1800263e4  pop     r15
0x1800263e6  pop     r14
0x1800263e8  pop     r13
0x1800263ea  pop     r12
0x1800263ec  pop     rdi
0x1800263ed  pop     rsi
0x1800263ee  pop     rbp
0x1800263ef  retn
0x1800263f0  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
```
