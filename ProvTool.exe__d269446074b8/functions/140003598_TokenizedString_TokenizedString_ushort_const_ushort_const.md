# TokenizedString::TokenizedString(ushort const *,ushort const *)

- ea: `0x140003598`
- end: `0x140003788`
- name: `??0TokenizedString@@QEAA@PEBG0@Z`
- size: `496`
- prototype: `TokenizedString *__fastcall(TokenizedString *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400041b0`

## callees

- `0x140003598`
- `0x140008850`
- `0x140008a90`
- `0x140008b88`
- `0x140008ca8`

## import_xrefs

- `msvcrt!wcstok_s` at `0x140003723`
- `msvcrt!wcstok_s` at `0x140003723`

## pseudocode

```c
TokenizedString *__fastcall TokenizedString::TokenizedString(
        TokenizedString *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v4; // r15
  wchar_t **v6; // r14
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rax
  unsigned __int64 v9; // r8
  signed int v10; // edi
  __int64 v11; // r9
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rdx
  wchar_t *v14; // rdx
  __int64 v15; // rax
  unsigned __int16 v16; // cx
  wchar_t *v17; // rcx
  wchar_t *i; // rcx
  wchar_t *v19; // rdi
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  wchar_t *Context; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v6 = (wchar_t **)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = 2147942487LL;
LABEL_8:
    v9 = 0;
    goto LABEL_9;
  }
  v7 = 0x7FFFFFFF;
  v8 = v4;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  v10 = -2147024809;
  v11 = v7 == 0 ? 0x80070057 : 0;
  if ( !v7 )
    goto LABEL_8;
LABEL_9:
  if ( (int)v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)v11,
      v21);
  if ( v9 + 1 < v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      v9 + 1 < v9 ? (const char *)0x80070216LL : 0,
      v21);
  v12 = v9 + 1;
  v13 = v9 + 2;
  if ( v9 != -2 )
  {
    if ( v13 > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<ProvPackage>>::_Xlen(retaddr, v13, v9);
    std::vector<unsigned short>::_Reallocate(v6, v13);
  }
  v14 = *v6;
  if ( v12 )
  {
    if ( v12 > 0x7FFFFFFF )
    {
      *v14 = 0;
    }
    else
    {
      v15 = 2147483646;
      do
      {
        if ( !v15 )
          break;
        v16 = *v4;
        if ( !*v4 )
          break;
        ++v4;
        *v14++ = v16;
        --v15;
        --v12;
      }
      while ( v12 );
      v17 = v14 - 1;
      if ( v12 )
        v17 = v14;
      *v17 = 0;
      v10 = v12 == 0 ? 0x8007007A : 0;
    }
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)v10,
      v21);
  Context = 0;
  for ( i = *v6; ; i = 0 )
  {
    v19 = wcstok_s(i, a3, &Context);
    if ( !v19 )
      break;
    if ( *((_QWORD *)this + 1) == *((_QWORD *)this + 2) )
      std::vector<unsigned short const *>::_Reserve(this);
    **((_QWORD **)this + 1) = v19;
    *((_QWORD *)this + 1) += 8LL;
  }
  return this;
}

```

## disassembly

```asm
0x140003598  mov     [rsp+arg_10], rbx
0x14000359d  mov     [rsp+arg_0], rcx
0x1400035a2  push    rbp
0x1400035a3  push    rsi
0x1400035a4  push    rdi
0x1400035a5  push    r12
0x1400035a7  push    r13
0x1400035a9  push    r14
0x1400035ab  push    r15; int
0x1400035ad  sub     rsp, 20h
0x1400035b1  mov     rbp, r8
0x1400035b4  mov     r15, rdx
0x1400035b7  mov     rbx, rcx
0x1400035ba  xor     r12d, r12d
0x1400035bd  mov     [rcx], r12
0x1400035c0  mov     [rcx+8], r12
0x1400035c4  mov     [rcx+10h], r12
0x1400035c8  lea     r14, [rcx+18h]
0x1400035cc  mov     [r14], r12
0x1400035cf  mov     [r14+8], r12
0x1400035d3  mov     [r14+10h], r12
0x1400035d7  mov     r13d, 7FFFFFFFh
0x1400035dd  test    rdx, rdx
0x1400035e0  jz      short loc_140003625
0x1400035e2  mov     edx, r13d
0x1400035e5  mov     rax, r15
0x1400035e8  cmp     [rax], r12w
0x1400035ec  jz      short loc_1400035F8
0x1400035ee  add     rax, 2
0x1400035f2  sub     rdx, 1
0x1400035f6  jnz     short loc_1400035E8
0x1400035f8  mov     rax, rdx
0x1400035fb  mov     rcx, r13
0x1400035fe  sub     rcx, rdx
0x140003601  neg     rax
0x140003604  sbb     r8, r8
0x140003607  and     r8, rcx
0x14000360a  mov     rax, rdx
0x14000360d  neg     rax
0x140003610  sbb     r9d, r9d
0x140003613  not     r9d
0x140003616  mov     edi, 80070057h
0x14000361b  and     r9d, edi
0x14000361e  test    rdx, rdx
0x140003621  jz      short loc_14000362D
0x140003623  jmp     short loc_140003630
0x140003625  mov     edi, 80070057h
0x14000362a  mov     r9d, edi; char *
0x14000362d  mov     r8, r12
0x140003630  mov     rcx, [rsp+58h]; this
0x140003635  test    r9d, r9d
0x140003638  js      loc_14000375E
0x14000363e  lea     rax, [r8+1]
0x140003642  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140003646  cmp     rax, r8
0x140003649  cmovnb  rsi, rax
0x14000364d  sbb     r9d, r9d
0x140003650  and     r9d, 80070216h; char *
0x140003657  mov     rcx, [rsp+58h]; this
0x14000365c  cmp     rax, r8
0x14000365f  jb      loc_140003770
0x140003665  lea     rdx, [rsi+1]
0x140003669  mov     rax, r12
0x14000366c  sub     rax, r12
0x14000366f  sar     rax, 1
0x140003672  cmp     rax, rdx
0x140003675  jnb     short loc_140003692
0x140003677  mov     rax, 7FFFFFFFFFFFFFFFh
0x140003681  cmp     rdx, rax
0x140003684  ja      loc_140003782
0x14000368a  mov     rcx, r14
0x14000368d  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x140003692  mov     rdx, [r14]
0x140003695  test    rsi, rsi
0x140003698  jz      short loc_1400036E8
0x14000369a  cmp     rsi, r13
0x14000369d  ja      short loc_1400036E4
0x14000369f  mov     eax, 7FFFFFFEh
0x1400036a4  test    rax, rax
0x1400036a7  jz      short loc_1400036C6
0x1400036a9  movzx   ecx, word ptr [r15]
0x1400036ad  test    cx, cx
0x1400036b0  jz      short loc_1400036C6
0x1400036b2  add     r15, 2
0x1400036b6  mov     [rdx], cx
0x1400036b9  add     rdx, 2
0x1400036bd  dec     rax
0x1400036c0  sub     rsi, 1
0x1400036c4  jnz     short loc_1400036A4
0x1400036c6  lea     rcx, [rdx-2]
0x1400036ca  test    rsi, rsi
0x1400036cd  cmovnz  rcx, rdx
0x1400036d1  mov     [rcx], r12w
0x1400036d5  neg     rsi
0x1400036d8  sbb     edi, edi
0x1400036da  not     edi
0x1400036dc  and     edi, 8007007Ah
0x1400036e2  jmp     short loc_1400036E8
0x1400036e4  mov     [rdx], r12w
0x1400036e8  mov     rcx, [rsp+58h]; this
0x1400036ed  test    edi, edi
0x1400036ef  js      short loc_140003749
0x1400036f1  mov     [rsp+58h+Context], r12
0x1400036f6  mov     rcx, [r14]
0x1400036f9  jmp     short loc_14000371B
0x1400036fb  mov     rcx, [rbx+10h]
0x1400036ff  cmp     [rbx+8], rcx
0x140003703  jnz     short loc_14000370D
0x140003705  mov     rcx, rbx
0x140003708  call    ?_Reserve@?$vector@PEBGV?$allocator@PEBG@std@@@std@@IEAAX_K@Z; std::vector<ushort const *>::_Reserve(unsigned __int64)
0x14000370d  mov     rcx, [rbx+8]
0x140003711  mov     [rcx], rdi
0x140003714  add     qword ptr [rbx+8], 8
0x140003719  xor     ecx, ecx; String
0x14000371b  lea     r8, [rsp+58h+Context]; Context
0x140003720  mov     rdx, rbp; Delimiter
0x140003723  call    cs:__imp_wcstok_s
0x140003729  test    rax, rax
0x14000372c  mov     rdi, rax
0x14000372f  jnz     short loc_1400036FB
0x140003731  mov     rax, rbx
0x140003734  mov     rbx, [rsp+58h+arg_10]
0x140003739  add     rsp, 20h
0x14000373d  pop     r15
0x14000373f  pop     r14
0x140003741  pop     r13
0x140003743  pop     r12
0x140003745  pop     rdi
0x140003746  pop     rsi
0x140003747  pop     rbp
0x140003748  retn
0x140003749  mov     r9d, edi; char *
0x14000374c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140003753  mov     edx, 57h ; 'W'; void *
0x140003758  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000375e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140003765  mov     edx, 54h ; 'T'; void *
0x14000376a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140003770  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140003777  mov     edx, 55h ; 'U'; void *
0x14000377c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140003782  call    ?_Xlen@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<ProvPackage>>::_Xlen(void)
```
