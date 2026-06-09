# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140008344`
- end: `0x1400086c4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140008194`

## callees

- `0x140005408`
- `0x140007acc`
- `0x140008344`
- `0x14000a66c`
- `0x140015ab6`

## import_xrefs

- `msvcrt!memmove_s` at `0x140008623`
- `msvcrt!memmove_s` at `0x140008623`
- `msvcrt!memcpy_s` at `0x14000844f`
- `msvcrt!memcpy_s` at `0x1400084e8`
- `msvcrt!memcpy_s` at `0x14000868e`
- `msvcrt!memcpy_s` at `0x14000844f`
- `msvcrt!memcpy_s` at `0x1400084e8`
- `msvcrt!memcpy_s` at `0x14000868e`

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
  __int64 v6; // rbx
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rbx
  char v13; // al
  bool v14; // al
  unsigned __int64 v15; // r12
  int v16; // ecx
  unsigned __int8 *v17; // rsi
  unsigned __int64 v18; // rax
  unsigned int v19; // edx
  rsize_t v20; // r9
  unsigned int *p_Source; // r8
  unsigned int v22; // esi
  unsigned int v23; // eax
  bool v24; // zf
  rsize_t v25; // r9
  unsigned int *v26; // r8
  rsize_t v27; // rdx
  unsigned __int8 *v28; // r8
  bool v29; // si
  __int64 v30; // rcx
  __int64 v32; // rax
  char v33; // dl
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  unsigned __int64 v36; // r9
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  __int16 v41; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 v43; // [rsp+40h] [rbp-59h] BYREF
  char v44; // [rsp+42h] [rbp-57h]
  unsigned int Source; // [rsp+44h] [rbp-55h] BYREF
  unsigned __int16 v46; // [rsp+48h] [rbp-51h]
  void *Buf2[2]; // [rsp+50h] [rbp-49h]
  __int16 v48; // [rsp+60h] [rbp-39h] BYREF
  char v49; // [rsp+62h] [rbp-37h]
  unsigned int v50; // [rsp+64h] [rbp-35h]
  __int16 v51; // [rsp+68h] [rbp-31h]
  __int64 v52; // [rsp+70h] [rbp-29h]
  void *v53; // [rsp+78h] [rbp-21h]
  __int16 v54; // [rsp+80h] [rbp-19h] BYREF
  char v55; // [rsp+82h] [rbp-17h]
  int v56; // [rsp+84h] [rbp-15h]
  __int16 v57; // [rsp+88h] [rbp-11h]
  __int128 v58; // [rsp+90h] [rbp-9h]
  __int16 v59; // [rsp+F0h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v11 = (unsigned __int8 *)*((_QWORD *)this + 4);
  v12 = (unsigned __int8 *)(v6 + 10);
  v43 = *((_WORD *)this + 1);
  v13 = *((_BYTE *)this + 4);
  Source = 0;
  v46 = 0;
  LOBYTE(v59) = 0;
  v44 = v13;
  InsertionPointOrIncrement = v12;
  *(_OWORD *)Buf2 = 0;
  v14 = wil::details_abi::UsageIndexProperty::Read(
          (wil::details_abi::UsageIndexProperty *)&v43,
          &InsertionPointOrIncrement,
          v11);
  v15 = a5;
  while ( 1 )
  {
    v29 = v14;
    if ( !v14 )
    {
      v12 = InsertionPointOrIncrement;
      goto LABEL_30;
    }
    v16 = Size == v46 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v46;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v43,
                                    InsertionPointOrIncrement,
                                    a4,
                                    v15,
                                    a6);
      v12 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        LOBYTE(v59) = 1;
        goto LABEL_38;
      }
      return 1;
    }
    v12 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v17 = InsertionPointOrIncrement;
      v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v19 = Source;
      if ( Source > v18 && Source != (_DWORD)v18 )
      {
        v19 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v19;
        if ( v44 == 1 )
        {
          v41 = v18;
          v20 = 2;
          p_Source = (unsigned int *)&v41;
          goto LABEL_15;
        }
        if ( v44 == 2 )
        {
          v20 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v20, p_Source, v20);
          v19 = Source;
        }
      }
      v12 = &v17[*((_QWORD *)this + 2) * v19];
      goto LABEL_27;
    }
    v54 = *((_WORD *)this + 3);
    v22 = 0;
    v55 = *((_BYTE *)this + 8);
    v23 = Source;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( Source )
    {
      do
      {
        v24 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v54,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v23 = Source;
        if ( v24 )
          break;
        ++v22;
      }
      while ( v22 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v23 != v22 )
    {
      Source = v22;
      if ( v44 == 1 )
      {
        v41 = v22;
        v25 = 2;
        v26 = (unsigned int *)&v41;
        v27 = 2;
      }
      else
      {
        if ( v44 != 2 )
          goto LABEL_27;
        v27 = 4;
        v26 = &Source;
        v25 = 4;
      }
      memcpy_s(Buf2[0], v27, v26, v25);
    }
LABEL_27:
    v28 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v43,
            &InsertionPointOrIncrement,
            v28);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v29 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v30 = 0;
  if ( !(_BYTE)v59 )
  {
    Source = 1;
    v46 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v43 )
      v30 = v43;
    else
      v30 = (unsigned __int16)Size + 2LL;
    if ( v44 == 1 )
    {
      v30 += 2;
    }
    else if ( v44 == 2 )
    {
      v30 += 4;
    }
  }
  v32 = *((unsigned __int16 *)this + 3);
  v33 = *((_BYTE *)this + 8);
  v48 = v32;
  v49 = v33;
  v50 = a6;
  v51 = v15;
  v52 = 0;
  v53 = a4;
  if ( !(_WORD)v32 )
    v32 = (unsigned __int16)v15 + 2LL;
  if ( v33 == 1 )
  {
    v32 += 2;
  }
  else if ( v33 == 2 )
  {
    v32 += 4;
  }
  v34 = *((_QWORD *)this + 5);
  v35 = v32 + v30;
  v36 = *((_QWORD *)this + 4);
  if ( ((v34 - v36) & -(__int64)(v36 < v34)) >= v32 + v30 )
  {
    memmove_s(&v12[v35], v34 - v35 - (_QWORD)v12, v12, v36 - (_QWORD)v12);
    *((_QWORD *)this + 4) += v35;
    if ( !(_BYTE)v59 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v43,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
LABEL_61:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v48,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v44 )
      goto LABEL_61;
    v37 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_61;
    ++Source;
    if ( v44 == 1 )
    {
      v38 = 2;
      v59 = v37;
      v39 = 2;
      v40 = (unsigned int *)&v59;
    }
    else
    {
      if ( v44 != 2 )
        goto LABEL_61;
      v40 = &Source;
      v38 = 4;
      v39 = 4;
    }
    memcpy_s(Buf2[0], v39, v40, v38);
    goto LABEL_61;
  }
  return 0;
}

```

## disassembly

```asm
0x140008344  push    rbp
0x140008346  push    rbx
0x140008347  push    rsi
0x140008348  push    rdi
0x140008349  push    r12
0x14000834b  push    r13
0x14000834d  push    r14
0x14000834f  push    r15
0x140008351  lea     rbp, [rsp-0Fh]
0x140008356  sub     rsp, 0A8h
0x14000835d  mov     rbx, [rcx+18h]
0x140008361  mov     rdi, rcx
0x140008364  xor     ecx, ecx
0x140008366  mov     r13, r9
0x140008369  mov     r14, r8
0x14000836c  mov     r15, rdx
0x14000836f  test    rbx, rbx
0x140008372  jz      loc_1400086AE
0x140008378  movzx   eax, word ptr [rdi+2]
0x14000837c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140008380  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008384  add     rbx, 0Ah
0x140008388  mov     [rbp+47h+var_A0], ax
0x14000838c  xorps   xmm0, xmm0
0x14000838f  mov     al, [rdi+4]
0x140008392  mov     [rbp+47h+Source], ecx
0x140008395  mov     [rbp+47h+var_98], cx
0x140008399  mov     byte ptr [rbp+47h+arg_0], cl
0x14000839c  lea     rcx, [rbp+47h+var_A0]; this
0x1400083a0  mov     [rbp+47h+var_9E], al
0x1400083a3  mov     [rbp+47h+var_A8], rbx
0x1400083a7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1400083ac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400083b1  mov     r12, [rbp+47h+arg_20]
0x1400083b5  jmp     loc_140008503
0x1400083ba  movzx   eax, [rbp+47h+var_98]
0x1400083be  cmp     r14, rax
0x1400083c1  jnz     short loc_1400083D9
0x1400083c3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1400083c7  mov     r8, r14; Size
0x1400083ca  mov     rcx, r15; Buf1
0x1400083cd  call    memcmp_0
0x1400083d2  mov     ecx, eax
0x1400083d4  xor     r9d, r9d
0x1400083d7  jmp     short loc_1400083E2
0x1400083d9  movzx   eax, [rbp+47h+var_98]
0x1400083dd  mov     ecx, r14d
0x1400083e0  sub     ecx, eax
0x1400083e2  test    ecx, ecx
0x1400083e4  js      loc_140008588
0x1400083ea  jz      loc_14000854D
0x1400083f0  mov     rbx, [rbp+47h+var_A8]
0x1400083f4  mov     [rbp+47h+var_A8], rbx
0x1400083f8  cmp     [rdi+10h], r9
0x1400083fc  jbe     short loc_140008467
0x1400083fe  mov     rax, [rdi+20h]
0x140008402  xor     edx, edx
0x140008404  sub     rax, [rdi+18h]
0x140008408  mov     rsi, rbx
0x14000840b  div     qword ptr [rdi+10h]
0x14000840f  mov     edx, [rbp+47h+Source]
0x140008412  cmp     rdx, rax
0x140008415  jbe     short loc_140008458
0x140008417  cmp     edx, eax
0x140008419  jz      short loc_140008458
0x14000841b  mov     edx, eax
0x14000841d  mov     [rbp+47h+Source], eax
0x140008420  mov     al, [rbp+47h+var_9E]
0x140008423  cmp     al, 1
0x140008425  jnz     short loc_14000843A
0x140008427  movzx   eax, dx
0x14000842a  mov     [rbp+47h+var_B0], dx
0x14000842e  mov     r9d, 2
0x140008434  lea     r8, [rbp+47h+var_B0]
0x140008438  jmp     short loc_140008448
0x14000843a  cmp     al, 2
0x14000843c  jnz     short loc_140008458
0x14000843e  mov     r9d, 4; SourceSize
0x140008444  lea     r8, [rbp+47h+Source]; Source
0x140008448  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000844c  mov     rdx, r9; DestinationSize
0x14000844f  call    cs:__imp_memcpy_s
0x140008455  mov     edx, [rbp+47h+Source]
0x140008458  mov     ebx, edx
0x14000845a  imul    rbx, [rdi+10h]
0x14000845f  add     rbx, rsi
0x140008462  jmp     loc_1400084EE
0x140008467  movzx   eax, word ptr [rdi+6]
0x14000846b  xorps   xmm0, xmm0
0x14000846e  mov     [rbp+47h+var_60], ax
0x140008472  mov     esi, r9d
0x140008475  mov     al, [rdi+8]
0x140008478  mov     [rbp+47h+var_5E], al
0x14000847b  mov     eax, [rbp+47h+Source]
0x14000847e  mov     [rbp+47h+var_5C], r9d
0x140008482  mov     [rbp+47h+var_58], r9w
0x140008487  movdqu  [rbp+47h+var_50], xmm0
0x14000848c  test    eax, eax
0x14000848e  jz      short loc_1400084B2
0x140008490  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008494  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140008498  lea     rcx, [rbp+47h+var_60]; this
0x14000849c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400084a1  test    al, al
0x1400084a3  mov     eax, [rbp+47h+Source]
0x1400084a6  jz      short loc_1400084AE
0x1400084a8  inc     esi
0x1400084aa  cmp     esi, eax
0x1400084ac  jb      short loc_140008490
0x1400084ae  mov     rbx, [rbp+47h+var_A8]
0x1400084b2  cmp     eax, esi
0x1400084b4  jz      short loc_1400084EE
0x1400084b6  mov     al, [rbp+47h+var_9E]
0x1400084b9  mov     [rbp+47h+Source], esi
0x1400084bc  cmp     al, 1
0x1400084be  jnz     short loc_1400084D4
0x1400084c0  mov     eax, 2
0x1400084c5  mov     [rbp+47h+var_B0], si
0x1400084c9  mov     r9d, eax
0x1400084cc  lea     r8, [rbp+47h+var_B0]
0x1400084d0  mov     edx, eax
0x1400084d2  jmp     short loc_1400084E4
0x1400084d4  cmp     al, 2
0x1400084d6  jnz     short loc_1400084EE
0x1400084d8  mov     edx, 4; DestinationSize
0x1400084dd  lea     r8, [rbp+47h+Source]; Source
0x1400084e1  mov     r9d, edx; SourceSize
0x1400084e4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400084e8  call    cs:__imp_memcpy_s
0x1400084ee  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400084f2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400084f6  lea     rcx, [rbp+47h+var_A0]; this
0x1400084fa  mov     [rbp+47h+var_A8], rbx
0x1400084fe  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140008503  xor     r9d, r9d
0x140008506  mov     sil, al
0x140008509  test    al, al
0x14000850b  jnz     loc_1400083BA
0x140008511  mov     rbx, [rbp+47h+var_A8]
0x140008515  mov     [rdi+20h], rbx
0x140008519  mov     rcx, r9
0x14000851c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x140008520  jnz     loc_1400085AB
0x140008526  movzx   eax, [rbp+47h+var_A0]
0x14000852a  mov     [rbp+47h+Source], 1
0x140008531  mov     [rbp+47h+var_98], r14w
0x140008536  mov     [rbp+47h+Buf2], r9
0x14000853a  mov     [rbp+47h+Buf2+8], r15
0x14000853e  test    ax, ax
0x140008541  jnz     short loc_140008593
0x140008543  movzx   ecx, r14w
0x140008547  add     rcx, 2
0x14000854b  jmp     short loc_140008596
0x14000854d  mov     eax, [rbp+47h+arg_28]
0x140008550  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140008554  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x140008558  mov     r9, r13; void *
0x14000855b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14000855f  mov     rcx, rdi; this
0x140008562  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140008567  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14000856c  xor     r9d, r9d
0x14000856f  mov     [rbp+47h+var_A8], rax
0x140008573  mov     rbx, rax
0x140008576  test    rax, rax
0x140008579  jnz     short loc_140008582
0x14000857b  mov     al, 1
0x14000857d  jmp     loc_1400086B0
0x140008582  mov     byte ptr [rbp+47h+arg_0], 1
0x140008586  jmp     short loc_14000858C
0x140008588  mov     [rbp+47h+var_A8], rbx
0x14000858c  test    sil, sil
0x14000858f  jnz     short loc_140008519
0x140008591  jmp     short loc_140008515
0x140008593  mov     rcx, rax
0x140008596  mov     al, [rbp+47h+var_9E]
0x140008599  cmp     al, 1
0x14000859b  jnz     short loc_1400085A3
0x14000859d  add     rcx, 2
0x1400085a1  jmp     short loc_1400085AB
0x1400085a3  cmp     al, 2
0x1400085a5  jnz     short loc_1400085AB
0x1400085a7  add     rcx, 4
0x1400085ab  movzx   eax, word ptr [rdi+6]
0x1400085af  mov     dl, [rdi+8]
0x1400085b2  mov     r8d, [rbp+47h+arg_28]
0x1400085b6  mov     [rbp+47h+var_80], ax
0x1400085ba  mov     [rbp+47h+var_7E], dl
0x1400085bd  mov     [rbp+47h+var_7C], r8d
0x1400085c1  mov     [rbp+47h+var_78], r12w
0x1400085c6  mov     [rbp+47h+var_70], r9
0x1400085ca  mov     [rbp+47h+var_68], r13
0x1400085ce  test    ax, ax
0x1400085d1  jnz     short loc_1400085DB
0x1400085d3  movzx   eax, r12w
0x1400085d7  add     rax, 2
0x1400085db  cmp     dl, 1
0x1400085de  jnz     short loc_1400085E6
0x1400085e0  add     rax, 2
0x1400085e4  jmp     short loc_1400085EF
0x1400085e6  cmp     dl, 2
0x1400085e9  jnz     short loc_1400085EF
0x1400085eb  add     rax, 4
0x1400085ef  mov     rdx, [rdi+28h]
0x1400085f3  lea     rsi, [rax+rcx]
0x1400085f7  mov     r9, [rdi+20h]
0x1400085fb  mov     rcx, rdx
0x1400085fe  sub     rcx, r9
0x140008601  cmp     r9, rdx
0x140008604  sbb     rax, rax
0x140008607  and     rax, rcx
0x14000860a  cmp     rax, rsi
0x14000860d  jb      loc_1400086AE
0x140008613  sub     rdx, rsi
0x140008616  lea     rcx, [rsi+rbx]; Destination
0x14000861a  sub     rdx, rbx; DestinationSize
0x14000861d  sub     r9, rbx; SourceSize
0x140008620  mov     r8, rbx; Source
0x140008623  call    cs:__imp_memmove_s
0x140008629  add     [rdi+20h], rsi
0x14000862d  xor     ebx, ebx
0x14000862f  cmp     byte ptr [rbp+47h+arg_0], bl
0x140008632  jnz     short loc_140008647
0x140008634  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008638  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000863c  lea     rcx, [rbp+47h+var_A0]; this
0x140008640  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140008645  jmp     short loc_140008694
0x140008647  mov     cl, [rbp+47h+var_9E]
0x14000864a  test    cl, cl
0x14000864c  jz      short loc_140008694
0x14000864e  mov     eax, [rbp+47h+Source]
0x140008651  lea     r8d, [rax+1]
0x140008655  cmp     eax, r8d
0x140008658  jz      short loc_140008694
0x14000865a  mov     [rbp+47h+Source], r8d
0x14000865e  cmp     cl, 1
0x140008661  jnz     short loc_140008677
0x140008663  mov     r9d, 2
0x140008669  mov     [rbp+47h+arg_0], r8w
0x14000866e  mov     edx, r9d
0x140008671  lea     r8, [rbp+47h+arg_0]
0x140008675  jmp     short loc_14000868A
0x140008677  cmp     cl, 2
0x14000867a  jnz     short loc_140008694
0x14000867c  mov     eax, 4
0x140008681  lea     r8, [rbp+47h+Source]; Source
0x140008685  mov     r9d, eax; SourceSize
0x140008688  mov     edx, eax; DestinationSize
0x14000868a  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000868e  call    cs:__imp_memcpy_s
0x140008694  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008698  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000869c  lea     rcx, [rbp+47h+var_80]; this
0x1400086a0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400086a5  mov     byte ptr [rdi+38h], 1
0x1400086a9  jmp     loc_14000857B
0x1400086ae  xor     al, al
0x1400086b0  add     rsp, 0A8h
0x1400086b7  pop     r15
0x1400086b9  pop     r14
0x1400086bb  pop     r13
0x1400086bd  pop     r12
0x1400086bf  pop     rdi
0x1400086c0  pop     rsi
0x1400086c1  pop     rbx
0x1400086c2  pop     rbp
0x1400086c3  retn
```
