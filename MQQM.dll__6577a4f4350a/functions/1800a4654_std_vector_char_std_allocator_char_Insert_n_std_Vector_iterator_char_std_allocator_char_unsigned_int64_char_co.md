# std::vector<char,std::allocator<char>>::_Insert_n(std::_Vector_iterator<char,std::allocator<char>>,unsigned __int64,char const &)

- ea: `0x1800a4654`
- end: `0x1800a4852`
- name: `?_Insert_n@?$vector@DV?$allocator@D@std@@@std@@IEAAXV?$_Vector_iterator@DV?$allocator@D@std@@@2@_KAEBD@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a4b54`

## callees

- `0x18000f44c`
- `0x1800111d0`
- `0x180064830`
- `0x1800a4654`
- `0x1800d6e56`

## import_xrefs

- `msvcrt!free` at `0x1800a4785`
- `msvcrt!free` at `0x1800a4785`
- `msvcrt!memmove_s` at `0x1800a4742`
- `msvcrt!memmove_s` at `0x1800a476c`
- `msvcrt!memmove_s` at `0x1800a47c7`
- `msvcrt!memmove_s` at `0x1800a47ff`
- `msvcrt!memmove_s` at `0x1800a4823`
- `msvcrt!memmove_s` at `0x1800a4742`
- `msvcrt!memmove_s` at `0x1800a476c`
- `msvcrt!memmove_s` at `0x1800a47c7`
- `msvcrt!memmove_s` at `0x1800a47ff`
- `msvcrt!memmove_s` at `0x1800a4823`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<char>::_Insert_n(__int64 a1, _BYTE *a2, rsize_t a3, _BYTE *a4)
{
  char *result; // rax
  __int64 v7; // rsi
  __int64 v8; // rdx
  rsize_t v9; // r8
  void **v10; // r14
  unsigned __int64 v11; // rax
  char *v12; // rax
  char *v13; // r13
  char *v14; // rax
  char *v15; // rax
  char *v16; // rax
  int v17; // edx
  char *v18; // r15
  _BYTE *v19; // r8
  signed __int64 v20; // r12
  char *v21; // r12
  _BYTE *v22; // rcx
  char *v23; // r15
  unsigned __int64 v24; // rsi
  size_t v25; // r15
  char *v26; // rdx
  signed __int64 v27; // rsi
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF
  char Val; // [rsp+50h] [rbp+8h]
  char *v30; // [rsp+60h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  v7 = a1;
  LOBYTE(a1) = *a4;
  Val = *a4;
  LOBYTE(v30) = *a4;
  v8 = *(_QWORD *)(v7 + 8);
  if ( v8 )
    v9 = *(_QWORD *)(v7 + 24) - v8;
  else
    v9 = 0;
  if ( a3 )
  {
    v10 = (void **)(v7 + 16);
    if ( v8 )
      v11 = (unsigned __int64)*v10 - v8;
    else
      v11 = 0;
    if ( ~v11 < a3 )
      std::vector<CAttachment>::_Xlen(a1, v8, v9);
    if ( v8 )
      v12 = (char *)*v10 - v8;
    else
      v12 = 0;
    if ( v9 >= (unsigned __int64)&v12[a3] )
    {
      v23 = (char *)*v10;
      v24 = (_BYTE *)*v10 - a2;
      if ( v24 >= a3 )
      {
        memmove_s(*v10, a3, &v23[-a3], a3);
        *v10 = &v23[a3];
        v27 = v24 - a3;
        if ( v27 > 0 )
          memmove_s(&v23[-v27], v27, a2, v27);
        v26 = &a2[a3];
      }
      else
      {
        if ( v24 )
        {
          memmove_s(&a2[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
          LOBYTE(a1) = Val;
        }
        v25 = &a2[a3] - (_BYTE *)*v10;
        if ( v25 )
        {
          LOBYTE(v8) = a1;
          memset_0(*v10, v8, v25);
        }
        v26 = (char *)*v10;
        *v10 = (char *)*v10 + a3;
      }
      return (char *)std::fill<unsigned char *,unsigned char>(a2, v26, &v30);
    }
    else
    {
      v13 = 0;
      if ( ~(v9 >> 1) >= v9 )
        v13 = (char *)(v9 + (v9 >> 1));
      if ( v8 )
        v14 = (char *)*v10 - v8;
      else
        v14 = 0;
      if ( v13 < &v14[a3] )
      {
        if ( v8 )
          v15 = (char *)*v10 - v8;
        else
          v15 = 0;
        v13 = &v15[a3];
      }
      v16 = (char *)std::_Allocate<char>(v13, 0);
      v18 = v16;
      v30 = v16;
      try
      {
        v19 = *(_BYTE **)(v7 + 8);
        v20 = a2 - v19;
        if ( a2 != v19 )
          memmove_s(v16, a2 - v19, v19, a2 - v19);
        v21 = &v18[v20];
        LOBYTE(v17) = Val;
        memset_0(v21, v17, a3);
        if ( *v10 != a2 )
          memmove_s(&v21[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
      }
      catch ( ... )
      {
        free(v30);
        throw;
      }
      v22 = *(_BYTE **)(v7 + 8);
      if ( v22 )
      {
        a3 += (_BYTE *)*v10 - v22;
        free(v22);
      }
      *(_QWORD *)(v7 + 24) = &v13[(_QWORD)v18];
      result = &v18[a3];
      *v10 = &v18[a3];
      *(_QWORD *)(v7 + 8) = v18;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a4654  mov     rax, rsp
0x1800a4657  mov     [rax+10h], rbx
0x1800a465b  mov     [rax+20h], rsi
0x1800a465f  push    rdi
0x1800a4660  push    r12
0x1800a4662  push    r13
0x1800a4664  push    r14
0x1800a4666  push    r15
0x1800a4668  sub     rsp, 20h
0x1800a466c  mov     rdi, r8
0x1800a466f  mov     rbx, rdx
0x1800a4672  mov     rsi, rcx
0x1800a4675  mov     cl, [r9]
0x1800a4678  mov     [rax+8], cl
0x1800a467b  mov     [rax+18h], cl
0x1800a467e  mov     rdx, [rsi+8]
0x1800a4682  test    rdx, rdx
0x1800a4685  jnz     short loc_1800A468C
0x1800a4687  xor     r8d, r8d
0x1800a468a  jmp     short loc_1800A4693
0x1800a468c  mov     r8, [rsi+18h]
0x1800a4690  sub     r8, rdx
0x1800a4693  test    rdi, rdi
0x1800a4696  jz      loc_1800A483A
0x1800a469c  lea     r14, [rsi+10h]
0x1800a46a0  test    rdx, rdx
0x1800a46a3  jnz     short loc_1800A46A9
0x1800a46a5  xor     eax, eax
0x1800a46a7  jmp     short loc_1800A46AF
0x1800a46a9  mov     rax, [r14]
0x1800a46ac  sub     rax, rdx
0x1800a46af  not     rax
0x1800a46b2  cmp     rax, rdi
0x1800a46b5  jnb     short loc_1800A46BD
0x1800a46b7  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x1800a46bd  test    rdx, rdx
0x1800a46c0  jnz     short loc_1800A46C6
0x1800a46c2  xor     eax, eax
0x1800a46c4  jmp     short loc_1800A46CC
0x1800a46c6  mov     rax, [r14]
0x1800a46c9  sub     rax, rdx
0x1800a46cc  add     rax, rdi
0x1800a46cf  cmp     r8, rax
0x1800a46d2  jnb     loc_1800A47A4
0x1800a46d8  mov     rax, r8
0x1800a46db  shr     rax, 1
0x1800a46de  mov     rcx, rax
0x1800a46e1  not     rcx
0x1800a46e4  add     rax, r8
0x1800a46e7  xor     r13d, r13d
0x1800a46ea  cmp     rcx, r8
0x1800a46ed  cmovnb  r13, rax
0x1800a46f1  test    rdx, rdx
0x1800a46f4  jnz     short loc_1800A46FA
0x1800a46f6  xor     eax, eax
0x1800a46f8  jmp     short loc_1800A4700
0x1800a46fa  mov     rax, [r14]
0x1800a46fd  sub     rax, rdx
0x1800a4700  add     rax, rdi
0x1800a4703  cmp     r13, rax
0x1800a4706  jnb     short loc_1800A471B
0x1800a4708  test    rdx, rdx
0x1800a470b  jnz     short loc_1800A4711
0x1800a470d  xor     eax, eax
0x1800a470f  jmp     short loc_1800A4717
0x1800a4711  mov     rax, [r14]
0x1800a4714  sub     rax, rdx
0x1800a4717  lea     r13, [rax+rdi]
0x1800a471b  xor     edx, edx
0x1800a471d  mov     rcx, r13
0x1800a4720  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1800a4725  mov     r15, rax
0x1800a4728  mov     [rsp+48h+arg_10], rax
0x1800a472d  mov     r8, [rsi+8]; Source
0x1800a4731  mov     r12, rbx
0x1800a4734  sub     r12, r8
0x1800a4737  jz      short loc_1800A4748
0x1800a4739  mov     r9, r12; SourceSize
0x1800a473c  mov     rdx, r12; DestinationSize
0x1800a473f  mov     rcx, rax; Destination
0x1800a4742  call    cs:__imp_memmove_s
0x1800a4748  add     r12, r15
0x1800a474b  mov     r8, rdi; Size
0x1800a474e  mov     dl, byte ptr [rsp+48h+Val]; Val
0x1800a4752  mov     rcx, r12; void *
0x1800a4755  call    memset_0
0x1800a475a  mov     rdx, [r14]
0x1800a475d  sub     rdx, rbx; DestinationSize
0x1800a4760  jz      short loc_1800A4773
0x1800a4762  lea     rcx, [r12+rdi]; Destination
0x1800a4766  mov     r9, rdx; SourceSize
0x1800a4769  mov     r8, rbx; Source
0x1800a476c  call    cs:__imp_memmove_s
0x1800a4772  nop
0x1800a4773  mov     rcx, [rsi+8]; Block
0x1800a4777  test    rcx, rcx
0x1800a477a  jz      short loc_1800A478C
0x1800a477c  mov     rax, [r14]
0x1800a477f  sub     rax, rcx
0x1800a4782  add     rdi, rax
0x1800a4785  call    cs:__imp_free
0x1800a478b  nop
0x1800a478c  lea     rax, [r15+r13]
0x1800a4790  mov     [rsi+18h], rax
0x1800a4794  lea     rax, [rdi+r15]
0x1800a4798  mov     [r14], rax
0x1800a479b  mov     [rsi+8], r15
0x1800a479f  jmp     loc_1800A483A
0x1800a47a4  mov     r15, [r14]
0x1800a47a7  mov     rsi, r15
0x1800a47aa  sub     rsi, rbx
0x1800a47ad  cmp     rsi, rdi
0x1800a47b0  jnb     short loc_1800A47F0
0x1800a47b2  lea     r15, [rbx+rdi]
0x1800a47b6  test    rsi, rsi
0x1800a47b9  jz      short loc_1800A47D1
0x1800a47bb  mov     r9, rsi; SourceSize
0x1800a47be  mov     r8, rbx; Source
0x1800a47c1  mov     rdx, rsi; DestinationSize
0x1800a47c4  mov     rcx, r15; Destination
0x1800a47c7  call    cs:__imp_memmove_s
0x1800a47cd  mov     cl, byte ptr [rsp+48h+Val]
0x1800a47d1  sub     r15, [r14]
0x1800a47d4  jz      short loc_1800A47E4
0x1800a47d6  mov     r8, r15; Size
0x1800a47d9  mov     dl, cl; Val
0x1800a47db  mov     rcx, [r14]; void *
0x1800a47de  call    memset_0
0x1800a47e3  nop
0x1800a47e4  mov     rdx, [r14]
0x1800a47e7  lea     rax, [rdx+rdi]
0x1800a47eb  mov     [r14], rax
0x1800a47ee  jmp     short loc_1800A482D
0x1800a47f0  mov     r8, r15
0x1800a47f3  sub     r8, rdi; Source
0x1800a47f6  mov     r9, rdi; SourceSize
0x1800a47f9  mov     rdx, rdi; DestinationSize
0x1800a47fc  mov     rcx, r15; Destination
0x1800a47ff  call    cs:__imp_memmove_s
0x1800a4805  lea     rax, [r15+rdi]
0x1800a4809  mov     [r14], rax
0x1800a480c  sub     rsi, rdi
0x1800a480f  test    rsi, rsi
0x1800a4812  jle     short loc_1800A4829
0x1800a4814  sub     r15, rsi
0x1800a4817  mov     r9, rsi; SourceSize
0x1800a481a  mov     r8, rbx; Source
0x1800a481d  mov     rdx, rsi; DestinationSize
0x1800a4820  mov     rcx, r15; Destination
0x1800a4823  call    cs:__imp_memmove_s
0x1800a4829  lea     rdx, [rbx+rdi]
0x1800a482d  lea     r8, [rsp+48h+arg_10]
0x1800a4832  mov     rcx, rbx
0x1800a4835  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x1800a483a  mov     rbx, [rsp+48h+arg_8]
0x1800a483f  mov     rsi, [rsp+48h+arg_18]
0x1800a4844  add     rsp, 20h
0x1800a4848  pop     r15
0x1800a484a  pop     r14
0x1800a484c  pop     r13
0x1800a484e  pop     r12
0x1800a4850  pop     rdi
0x1800a4851  retn
```
