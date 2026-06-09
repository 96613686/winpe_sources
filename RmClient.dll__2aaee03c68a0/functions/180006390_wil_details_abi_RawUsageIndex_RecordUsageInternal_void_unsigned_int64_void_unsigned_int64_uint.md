# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006390`
- end: `0x180006812`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `1154`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180005fb8`
- `0x180006130`

## callees

- `0x180006390`
- `0x1800072c0`
- `0x180007a84`
- `0x1800172a4`
- `0x18001ae76`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006566`
- `msvcrt!memmove_s` at `0x180006566`
- `msvcrt!memcpy_s` at `0x1800065ba`
- `msvcrt!memcpy_s` at `0x180006604`
- `msvcrt!memcpy_s` at `0x180006636`
- `msvcrt!memcpy_s` at `0x180006662`
- `msvcrt!memcpy_s` at `0x180006687`
- `msvcrt!memcpy_s` at `0x1800066dc`
- `msvcrt!memcpy_s` at `0x18000670a`
- `msvcrt!memcpy_s` at `0x180006739`
- `msvcrt!memcpy_s` at `0x180006771`
- `msvcrt!memcpy_s` at `0x1800067df`
- `msvcrt!memcpy_s` at `0x180006807`
- `msvcrt!memcpy_s` at `0x1800065ba`
- `msvcrt!memcpy_s` at `0x180006604`
- `msvcrt!memcpy_s` at `0x180006636`
- `msvcrt!memcpy_s` at `0x180006662`
- `msvcrt!memcpy_s` at `0x180006687`
- `msvcrt!memcpy_s` at `0x1800066dc`
- `msvcrt!memcpy_s` at `0x18000670a`
- `msvcrt!memcpy_s` at `0x180006739`
- `msvcrt!memcpy_s` at `0x180006771`
- `msvcrt!memcpy_s` at `0x1800067df`
- `msvcrt!memcpy_s` at `0x180006807`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rax
  unsigned __int8 *InsertionPointOrIncrement; // rdi
  unsigned __int64 v12; // rcx
  unsigned __int8 *v13; // r13
  unsigned __int16 v14; // ax
  unsigned __int8 *v15; // r12
  int v16; // ecx
  char v17; // r12
  __int64 v18; // rdx
  __int64 v19; // rax
  char v20; // cl
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rax
  unsigned __int64 v26; // r14
  unsigned __int8 *v27; // rsi
  unsigned __int64 v28; // rsi
  unsigned __int8 *v29; // r14
  unsigned __int64 v30; // [rsp+30h] [rbp-49h]
  unsigned __int16 v31; // [rsp+40h] [rbp-39h] BYREF
  char v32; // [rsp+42h] [rbp-37h]
  int v33; // [rsp+44h] [rbp-35h] BYREF
  unsigned __int16 v34; // [rsp+48h] [rbp-31h] BYREF
  void *Source[2]; // [rsp+50h] [rbp-29h]
  __int16 v36; // [rsp+60h] [rbp-19h]
  char v37; // [rsp+62h] [rbp-17h]
  unsigned int v38; // [rsp+64h] [rbp-15h] BYREF
  unsigned __int16 v39; // [rsp+68h] [rbp-11h] BYREF
  __int64 v40; // [rsp+70h] [rbp-9h]
  void *v41; // [rsp+78h] [rbp-1h]
  unsigned __int16 Destination; // [rsp+D0h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  InsertionPointOrIncrement = (unsigned __int8 *)(v6 + 10);
  v33 = 0;
  v31 = *((_WORD *)this + 1);
  v32 = *((_BYTE *)this + 4);
  v34 = 0;
  *(_OWORD *)Source = 0;
  while ( 1 )
  {
    v12 = *((_QWORD *)this + 4);
    v30 = v12;
    if ( v32 == 1 )
    {
      v13 = InsertionPointOrIncrement + 2;
      if ( (unsigned __int64)(InsertionPointOrIncrement + 2) > v12 )
        goto LABEL_15;
      Source[0] = InsertionPointOrIncrement;
      Destination = 0;
      memcpy_s(&Destination, 2u, InsertionPointOrIncrement, 2u);
      v12 = v30;
      v33 = Destination;
    }
    else if ( v32 == 2 )
    {
      v13 = InsertionPointOrIncrement + 4;
      if ( (unsigned __int64)(InsertionPointOrIncrement + 4) > v12 )
        goto LABEL_15;
      Source[0] = InsertionPointOrIncrement;
      memcpy_s(&v33, 4u, InsertionPointOrIncrement, 4u);
      v12 = v30;
    }
    else
    {
      v13 = InsertionPointOrIncrement;
    }
    v14 = v31;
    v34 = v31;
    if ( !v31 )
      break;
LABEL_7:
    v15 = &v13[v14];
    if ( (unsigned __int64)v15 > v30 )
      goto LABEL_15;
    Source[1] = v13;
    if ( Size == v14 )
      v16 = memcmp_0(Buf1, v13, Size);
    else
      v16 = Size - v14;
    if ( v16 < 0 )
      goto LABEL_16;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v31,
                                    v15,
                                    a4,
                                    a5,
                                    a6);
      if ( InsertionPointOrIncrement )
      {
        v17 = 1;
        v18 = 0;
        goto LABEL_22;
      }
      return 1;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::SkipValues(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v31,
                                  v15);
  }
  if ( (unsigned __int64)(v13 + 2) <= v12 )
  {
    memcpy_s(&v34, 2u, v13, 2u);
    v14 = v34;
    v13 += 2;
    goto LABEL_7;
  }
LABEL_15:
  *((_QWORD *)this + 4) = InsertionPointOrIncrement;
LABEL_16:
  v33 = 1;
  v34 = Size;
  Source[0] = 0;
  Source[1] = Buf1;
  if ( v31 )
    v18 = v31;
  else
    v18 = (unsigned __int16)Size + 2LL;
  if ( v32 == 1 )
  {
    v18 += 2;
  }
  else if ( v32 == 2 )
  {
    v18 += 4;
  }
  v17 = 0;
LABEL_22:
  v19 = *((unsigned __int16 *)this + 3);
  v20 = *((_BYTE *)this + 8);
  v38 = a6;
  v39 = a5;
  v36 = v19;
  v37 = v20;
  v40 = 0;
  v41 = a4;
  if ( !(_WORD)v19 )
    v19 = (unsigned __int16)a5 + 2LL;
  if ( v20 == 1 )
  {
    v19 += 2;
  }
  else if ( v20 == 2 )
  {
    v19 += 4;
  }
  v21 = *((_QWORD *)this + 4);
  v22 = v19 + v18;
  v23 = *((_QWORD *)this + 5);
  v24 = 0;
  if ( v21 < v23 )
    v24 = *((_QWORD *)this + 5) - v21;
  if ( v24 >= v22 )
  {
    memmove_s(
      &InsertionPointOrIncrement[v22],
      v23 - v22 - (_QWORD)InsertionPointOrIncrement,
      InsertionPointOrIncrement,
      v21 - (_QWORD)InsertionPointOrIncrement);
    *((_QWORD *)this + 4) += v22;
    v26 = *((_QWORD *)this + 4);
    if ( v17 )
    {
      if ( v32 )
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v31, v33 + 1);
    }
    else
    {
      if ( v32 == 1 )
      {
        v27 = InsertionPointOrIncrement + 2;
        if ( (unsigned __int64)(InsertionPointOrIncrement + 2) > v26 )
          goto LABEL_38;
        Destination = v33;
        memcpy_s(InsertionPointOrIncrement, 2u, &Destination, 2u);
      }
      else if ( v32 == 2 )
      {
        v27 = InsertionPointOrIncrement + 4;
        if ( (unsigned __int64)(InsertionPointOrIncrement + 4) > v26 )
          goto LABEL_38;
        memcpy_s(InsertionPointOrIncrement, 4u, &v33, 4u);
      }
      else
      {
        v27 = InsertionPointOrIncrement;
      }
      if ( !v31 )
      {
        if ( (unsigned __int64)(v27 + 2) > v26 )
          goto LABEL_38;
        memcpy_s(v27, v26 - (_QWORD)v27, &v34, 2u);
        v27 += 2;
      }
      if ( (unsigned __int64)&v27[v34] <= v26 )
      {
        memcpy_s(v27, v26 - (_QWORD)v27, Source[1], v34);
        InsertionPointOrIncrement = &v27[v34];
      }
    }
LABEL_38:
    v28 = *((_QWORD *)this + 4);
    if ( v37 == 1 )
    {
      v29 = InsertionPointOrIncrement + 2;
      if ( (unsigned __int64)(InsertionPointOrIncrement + 2) > v28 )
        goto LABEL_44;
      Destination = v38;
      memcpy_s(InsertionPointOrIncrement, 2u, &Destination, 2u);
    }
    else if ( v37 == 2 )
    {
      v29 = InsertionPointOrIncrement + 4;
      if ( (unsigned __int64)(InsertionPointOrIncrement + 4) > v28 )
        goto LABEL_44;
      memcpy_s(InsertionPointOrIncrement, 4u, &v38, 4u);
    }
    else
    {
      v29 = InsertionPointOrIncrement;
    }
    if ( v36 )
      goto LABEL_42;
    if ( (unsigned __int64)(v29 + 2) <= v28 )
    {
      memcpy_s(v29, v28 - (_QWORD)v29, &v39, 2u);
      v29 += 2;
LABEL_42:
      if ( (unsigned __int64)&v29[v39] <= v28 )
        memcpy_s(v29, v28 - (_QWORD)v29, v41, v39);
    }
LABEL_44:
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180006390  push    rbp
0x180006392  push    rbx
0x180006393  push    rsi
0x180006394  push    rdi
0x180006395  push    r12
0x180006397  push    r13
0x180006399  push    r14
0x18000639b  push    r15
0x18000639d  lea     rbp, [rsp-0Fh]
0x1800063a2  sub     rsp, 88h
0x1800063a9  mov     rax, [rcx+18h]
0x1800063ad  mov     r15, r9
0x1800063b0  mov     rsi, r8
0x1800063b3  mov     r14, rdx
0x1800063b6  mov     rbx, rcx
0x1800063b9  test    rax, rax
0x1800063bc  jz      loc_180006540
0x1800063c2  lea     rdi, [rax+0Ah]
0x1800063c6  mov     [rbp+47h+var_7C], 0
0x1800063cd  movzx   eax, word ptr [rcx+2]
0x1800063d1  xorps   xmm0, xmm0
0x1800063d4  mov     [rbp+47h+var_80], ax
0x1800063d8  movzx   eax, byte ptr [rcx+4]
0x1800063dc  mov     [rbp+47h+var_7E], al
0x1800063df  xor     eax, eax
0x1800063e1  mov     [rbp+47h+var_78], ax
0x1800063e5  movdqu  xmmword ptr [rbp+47h+Source], xmm0
0x1800063ea  cmp     [rbp+47h+var_7E], 1
0x1800063ee  mov     rcx, [rbx+20h]
0x1800063f2  mov     [rbp+47h+var_90], rcx
0x1800063f6  mov     [rbp+47h+var_88], rdi
0x1800063fa  jz      loc_18000648F
0x180006400  cmp     [rbp+47h+var_7E], 2
0x180006404  jz      loc_180006718
0x18000640a  mov     r13, rdi
0x18000640d  movzx   eax, [rbp+47h+var_80]
0x180006411  mov     [rbp+47h+var_78], ax
0x180006415  test    ax, ax
0x180006418  jz      loc_180006754
0x18000641e  movzx   ecx, ax
0x180006421  lea     r12, [rcx+r13]
0x180006425  cmp     r12, [rbp+47h+var_90]
0x180006429  ja      short loc_18000649C
0x18000642b  mov     [rbp+47h+Source+8], r13
0x18000642f  cmp     rsi, rcx
0x180006432  jnz     loc_180006748
0x180006438  mov     r8, rsi; Size
0x18000643b  mov     rdx, r13; Buf2
0x18000643e  mov     rcx, r14; Buf1
0x180006441  call    memcmp_0
0x180006446  mov     ecx, eax
0x180006448  test    ecx, ecx
0x18000644a  js      loc_1800067A0
0x180006450  mov     r8, r12; unsigned __int8 *
0x180006453  lea     rdx, [rbp+47h+var_80]; struct wil::details_abi::UsageIndexProperty *
0x180006457  mov     rcx, rbx; this
0x18000645a  jnz     loc_1800066AF
0x180006460  mov     eax, [rbp+47h+arg_28]
0x180006463  mov     r9, r15; void *
0x180006466  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000646a  mov     rax, [rbp+47h+arg_20]
0x18000646e  mov     [rsp+0C0h+var_A0], rax; unsigned __int64
0x180006473  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006478  mov     rdi, rax
0x18000647b  test    rax, rax
0x18000647e  jz      loc_18000660E
0x180006484  xor     r10d, r10d
0x180006487  mov     r12b, 1
0x18000648a  mov     edx, r10d
0x18000648d  jmp     short loc_1800064DC
0x18000648f  lea     r13, [rdi+2]
0x180006493  cmp     r13, rcx
0x180006496  jbe     loc_18000666D
0x18000649c  mov     [rbx+20h], rdi
0x1800064a0  xor     r10d, r10d
0x1800064a3  mov     [rbp+47h+var_7C], 1
0x1800064aa  mov     [rbp+47h+var_78], si
0x1800064ae  mov     [rbp+47h+Source], r10
0x1800064b2  mov     [rbp+47h+Source+8], r14
0x1800064b6  cmp     [rbp+47h+var_80], r10w
0x1800064bb  jz      loc_1800067A9
0x1800064c1  movzx   edx, [rbp+47h+var_80]
0x1800064c5  cmp     [rbp+47h+var_7E], 1
0x1800064c9  jz      loc_1800066A6
0x1800064cf  cmp     [rbp+47h+var_7E], 2
0x1800064d3  jnz     short loc_1800064D9
0x1800064d5  add     rdx, 4
0x1800064d9  xor     r12b, r12b
0x1800064dc  mov     r8d, [rbp+47h+arg_28]
0x1800064e0  movzx   eax, word ptr [rbx+6]
0x1800064e4  movzx   ecx, byte ptr [rbx+8]
0x1800064e8  mov     [rbp+47h+var_5C], r8d
0x1800064ec  mov     r8, [rbp+47h+arg_20]
0x1800064f0  mov     [rbp+47h+var_58], r8w
0x1800064f5  mov     [rbp+47h+var_60], ax
0x1800064f9  mov     [rbp+47h+var_5E], cl
0x1800064fc  mov     [rbp+47h+var_50], r10
0x180006500  mov     [rbp+47h+var_48], r15
0x180006504  test    ax, ax
0x180006507  jz      loc_1800067B5
0x18000650d  cmp     cl, 1
0x180006510  jz      loc_18000669D
0x180006516  cmp     cl, 2
0x180006519  jnz     short loc_18000651F
0x18000651b  add     rax, 4
0x18000651f  mov     r9, [rbx+20h]
0x180006523  lea     rsi, [rax+rdx]
0x180006527  mov     rdx, [rbx+28h]
0x18000652b  mov     rax, r10
0x18000652e  mov     rcx, rdx
0x180006531  sub     rcx, r9
0x180006534  cmp     r9, rdx
0x180006537  cmovb   rax, rcx
0x18000653b  cmp     rax, rsi
0x18000653e  jnb     short loc_180006556
0x180006540  xor     al, al
0x180006542  add     rsp, 88h
0x180006549  pop     r15
0x18000654b  pop     r14
0x18000654d  pop     r13
0x18000654f  pop     r12
0x180006551  pop     rdi
0x180006552  pop     rsi
0x180006553  pop     rbx
0x180006554  pop     rbp
0x180006555  retn
0x180006556  sub     rdx, rsi
0x180006559  lea     rcx, [rsi+rdi]; Destination
0x18000655d  sub     rdx, rdi; DestinationSize
0x180006560  sub     r9, rdi; SourceSize
0x180006563  mov     r8, rdi; Source
0x180006566  call    cs:__imp_memmove_s
0x18000656c  add     [rbx+20h], rsi
0x180006570  mov     r14, [rbx+20h]
0x180006574  test    r12b, r12b
0x180006577  jnz     loc_180006783
0x18000657d  movzx   eax, [rbp+47h+var_7E]
0x180006581  cmp     al, 1
0x180006583  jz      loc_180006615
0x180006589  cmp     al, 2
0x18000658b  jz      loc_1800067C2
0x180006591  mov     rsi, rdi
0x180006594  cmp     [rbp+47h+var_80], 0
0x180006599  jz      loc_1800066BC
0x18000659f  movzx   r9d, [rbp+47h+var_78]; SourceSize
0x1800065a4  lea     rax, [r9+rsi]
0x1800065a8  cmp     rax, r14
0x1800065ab  ja      short loc_1800065C7
0x1800065ad  mov     r8, [rbp+47h+Source+8]; Source
0x1800065b1  sub     r14, rsi
0x1800065b4  mov     rdx, r14; DestinationSize
0x1800065b7  mov     rcx, rsi; Destination
0x1800065ba  call    cs:__imp_memcpy_s
0x1800065c0  movzx   edi, [rbp+47h+var_78]
0x1800065c4  add     rdi, rsi
0x1800065c7  movzx   eax, [rbp+47h+var_5E]
0x1800065cb  mov     rsi, [rbx+20h]
0x1800065cf  cmp     al, 1
0x1800065d1  jz      short loc_180006641
0x1800065d3  cmp     al, 2
0x1800065d5  jz      loc_1800067EA
0x1800065db  mov     r14, rdi
0x1800065de  cmp     [rbp+47h+var_60], 0
0x1800065e3  jz      loc_1800066EA
0x1800065e9  movzx   r9d, [rbp+47h+var_58]; SourceSize
0x1800065ee  lea     rax, [r9+r14]
0x1800065f2  cmp     rax, rsi
0x1800065f5  ja      short loc_18000660A
0x1800065f7  mov     r8, [rbp+47h+var_48]; Source
0x1800065fb  sub     rsi, r14
0x1800065fe  mov     rdx, rsi; DestinationSize
0x180006601  mov     rcx, r14; Destination
0x180006604  call    cs:__imp_memcpy_s
0x18000660a  mov     byte ptr [rbx+38h], 1
0x18000660e  mov     al, 1
0x180006610  jmp     loc_180006542
0x180006615  lea     rsi, [rdi+2]
0x180006619  cmp     rsi, r14
0x18000661c  ja      short loc_1800065C7
0x18000661e  movzx   eax, word ptr [rbp+47h+var_7C]
0x180006622  lea     r8, [rbp+47h+Destination]; Source
0x180006626  mov     r9d, 2; SourceSize
0x18000662c  mov     [rbp+47h+Destination], ax
0x180006630  mov     edx, r9d; DestinationSize
0x180006633  mov     rcx, rdi; Destination
0x180006636  call    cs:__imp_memcpy_s
0x18000663c  jmp     loc_180006594
0x180006641  lea     r14, [rdi+2]
0x180006645  cmp     r14, rsi
0x180006648  ja      short loc_18000660A
0x18000664a  movzx   eax, word ptr [rbp+47h+var_5C]
0x18000664e  lea     r8, [rbp+47h+Destination]; Source
0x180006652  mov     r9d, 2; SourceSize
0x180006658  mov     [rbp+47h+Destination], ax
0x18000665c  mov     edx, r9d; DestinationSize
0x18000665f  mov     rcx, rdi; Destination
0x180006662  call    cs:__imp_memcpy_s
0x180006668  jmp     loc_1800065DE
0x18000666d  mov     r9d, 2; SourceSize
0x180006673  mov     [rbp+47h+Source], rdi
0x180006677  xor     eax, eax
0x180006679  lea     rcx, [rbp+47h+Destination]; Destination
0x18000667d  mov     edx, r9d; DestinationSize
0x180006680  mov     [rbp+47h+Destination], ax
0x180006684  mov     r8, rdi; Source
0x180006687  call    cs:__imp_memcpy_s
0x18000668d  movzx   eax, [rbp+47h+Destination]
0x180006691  mov     rcx, [rbp+47h+var_90]
0x180006695  mov     [rbp+47h+var_7C], eax
0x180006698  jmp     loc_18000640D
0x18000669d  add     rax, 2
0x1800066a1  jmp     loc_18000651F
0x1800066a6  add     rdx, 2
0x1800066aa  jmp     loc_1800064D9
0x1800066af  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800066b4  mov     rdi, rax
0x1800066b7  jmp     loc_1800063EA
0x1800066bc  lea     r15, [rsi+2]
0x1800066c0  cmp     r15, r14
0x1800066c3  ja      loc_1800065C7
0x1800066c9  mov     rdx, r14
0x1800066cc  lea     r8, [rbp+47h+var_78]; Source
0x1800066d0  sub     rdx, rsi; DestinationSize
0x1800066d3  mov     r9d, 2; SourceSize
0x1800066d9  mov     rcx, rsi; Destination
0x1800066dc  call    cs:__imp_memcpy_s
0x1800066e2  mov     rsi, r15
0x1800066e5  jmp     loc_18000659F
0x1800066ea  lea     rdi, [r14+2]
0x1800066ee  cmp     rdi, rsi
0x1800066f1  ja      loc_18000660A
0x1800066f7  mov     rdx, rsi
0x1800066fa  lea     r8, [rbp+47h+var_58]; Source
0x1800066fe  sub     rdx, r14; DestinationSize
0x180006701  mov     r9d, 2; SourceSize
0x180006707  mov     rcx, r14; Destination
0x18000670a  call    cs:__imp_memcpy_s
0x180006710  mov     r14, rdi
0x180006713  jmp     loc_1800065E9
0x180006718  lea     r13, [rdi+4]
0x18000671c  cmp     r13, rcx
0x18000671f  ja      loc_18000649C
0x180006725  mov     r9d, 4; SourceSize
0x18000672b  mov     [rbp+47h+Source], rdi
0x18000672f  mov     edx, r9d; DestinationSize
0x180006732  lea     rcx, [rbp+47h+var_7C]; Destination
0x180006736  mov     r8, rdi; Source
0x180006739  call    cs:__imp_memcpy_s
0x18000673f  mov     rcx, [rbp+47h+var_90]
0x180006743  jmp     loc_18000640D
0x180006748  movzx   eax, ax
0x18000674b  mov     ecx, esi
0x18000674d  sub     ecx, eax
0x18000674f  jmp     loc_180006448
0x180006754  lea     r12, [r13+2]
0x180006758  cmp     r12, rcx
0x18000675b  ja      loc_18000649C
0x180006761  mov     r9d, 2; SourceSize
0x180006767  lea     rcx, [rbp+47h+var_78]; Destination
0x18000676b  mov     edx, r9d; DestinationSize
0x18000676e  mov     r8, r13; Source
0x180006771  call    cs:__imp_memcpy_s
0x180006777  movzx   eax, [rbp+47h+var_78]
0x18000677b  mov     r13, r12
0x18000677e  jmp     loc_18000641E
0x180006783  cmp     [rbp+47h+var_7E], 0
0x180006787  jz      loc_1800065C7
0x18000678d  mov     edx, [rbp+47h+var_7C]
0x180006790  lea     rcx, [rbp+47h+var_80]; this
0x180006794  inc     edx; unsigned int
0x180006796  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000679b  jmp     loc_1800065C7
0x1800067a0  mov     rdi, [rbp+47h+var_88]
0x1800067a4  jmp     loc_1800064A0
0x1800067a9  movzx   edx, si
0x1800067ac  add     rdx, 2
0x1800067b0  jmp     loc_1800064C5
0x1800067b5  movzx   eax, r8w
0x1800067b9  add     rax, 2
0x1800067bd  jmp     loc_18000650D
0x1800067c2  lea     rsi, [rdi+4]
0x1800067c6  cmp     rsi, r14
0x1800067c9  ja      loc_1800065C7
0x1800067cf  mov     r9d, 4; SourceSize
0x1800067d5  lea     r8, [rbp+47h+var_7C]; Source
0x1800067d9  mov     edx, r9d; DestinationSize
0x1800067dc  mov     rcx, rdi; Destination
0x1800067df  call    cs:__imp_memcpy_s
0x1800067e5  jmp     loc_180006594
0x1800067ea  lea     r14, [rdi+4]
0x1800067ee  cmp     r14, rsi
0x1800067f1  ja      loc_18000660A
0x1800067f7  mov     r9d, 4; SourceSize
0x1800067fd  lea     r8, [rbp+47h+var_5C]; Source
0x180006801  mov     edx, r9d; DestinationSize
0x180006804  mov     rcx, rdi; Destination
0x180006807  call    cs:__imp_memcpy_s
0x18000680d  jmp     loc_1800065DE
```
