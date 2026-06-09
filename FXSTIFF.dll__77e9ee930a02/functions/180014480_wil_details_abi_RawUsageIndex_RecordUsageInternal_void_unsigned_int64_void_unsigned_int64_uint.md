# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180014480`
- end: `0x180014819`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800142ac`

## callees

- `0x1800122a8`
- `0x180013ddc`
- `0x180014480`
- `0x18001653c`
- `0x180018986`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001458b`
- `msvcrt!memcpy_s` at `0x18001462a`
- `msvcrt!memcpy_s` at `0x1800147dc`
- `msvcrt!memcpy_s` at `0x18001458b`
- `msvcrt!memcpy_s` at `0x18001462a`
- `msvcrt!memcpy_s` at `0x1800147dc`
- `msvcrt!memmove_s` at `0x18001476b`
- `msvcrt!memmove_s` at `0x18001476b`

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
0x180014480  push    rbp
0x180014482  push    rbx
0x180014483  push    rsi
0x180014484  push    rdi
0x180014485  push    r12
0x180014487  push    r13
0x180014489  push    r14
0x18001448b  push    r15
0x18001448d  lea     rbp, [rsp-0Fh]
0x180014492  sub     rsp, 0A8h
0x180014499  mov     rbx, [rcx+18h]
0x18001449d  mov     rdi, rcx
0x1800144a0  xor     ecx, ecx
0x1800144a2  mov     r13, r9
0x1800144a5  mov     r14, r8
0x1800144a8  mov     r15, rdx
0x1800144ab  test    rbx, rbx
0x1800144ae  jz      loc_180014802
0x1800144b4  movzx   eax, word ptr [rdi+2]
0x1800144b8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800144bc  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800144c0  add     rbx, 0Ah
0x1800144c4  mov     [rbp+47h+var_A0], ax
0x1800144c8  xorps   xmm0, xmm0
0x1800144cb  mov     al, [rdi+4]
0x1800144ce  mov     [rbp+47h+Source], ecx
0x1800144d1  mov     [rbp+47h+var_98], cx
0x1800144d5  mov     byte ptr [rbp+47h+arg_0], cl
0x1800144d8  lea     rcx, [rbp+47h+var_A0]; this
0x1800144dc  mov     [rbp+47h+var_9E], al
0x1800144df  mov     [rbp+47h+var_A8], rbx
0x1800144e3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800144e8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800144ed  mov     r12, [rbp+47h+arg_20]
0x1800144f1  jmp     loc_18001464B
0x1800144f6  movzx   eax, [rbp+47h+var_98]
0x1800144fa  cmp     r14, rax
0x1800144fd  jnz     short loc_180014515
0x1800144ff  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180014503  mov     r8, r14; Size
0x180014506  mov     rcx, r15; Buf1
0x180014509  call    memcmp_0
0x18001450e  mov     ecx, eax
0x180014510  xor     r9d, r9d
0x180014513  jmp     short loc_18001451E
0x180014515  movzx   eax, [rbp+47h+var_98]
0x180014519  mov     ecx, r14d
0x18001451c  sub     ecx, eax
0x18001451e  test    ecx, ecx
0x180014520  js      loc_1800146D0
0x180014526  jz      loc_180014695
0x18001452c  mov     rbx, [rbp+47h+var_A8]
0x180014530  mov     [rbp+47h+var_A8], rbx
0x180014534  cmp     [rdi+10h], r9
0x180014538  jbe     short loc_1800145A9
0x18001453a  mov     rax, [rdi+20h]
0x18001453e  xor     edx, edx
0x180014540  sub     rax, [rdi+18h]
0x180014544  mov     rsi, rbx
0x180014547  div     qword ptr [rdi+10h]
0x18001454b  mov     edx, [rbp+47h+Source]
0x18001454e  cmp     rdx, rax
0x180014551  jbe     short loc_18001459A
0x180014553  cmp     edx, eax
0x180014555  jz      short loc_18001459A
0x180014557  mov     edx, eax
0x180014559  mov     [rbp+47h+Source], eax
0x18001455c  mov     al, [rbp+47h+var_9E]
0x18001455f  cmp     al, 1
0x180014561  jnz     short loc_180014576
0x180014563  movzx   eax, dx
0x180014566  mov     [rbp+47h+var_B0], dx
0x18001456a  mov     r9d, 2
0x180014570  lea     r8, [rbp+47h+var_B0]
0x180014574  jmp     short loc_180014584
0x180014576  cmp     al, 2
0x180014578  jnz     short loc_18001459A
0x18001457a  mov     r9d, 4; SourceSize
0x180014580  lea     r8, [rbp+47h+Source]; Source
0x180014584  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014588  mov     rdx, r9; DestinationSize
0x18001458b  call    cs:__imp_memcpy_s
0x180014592  nop     dword ptr [rax+rax+00h]
0x180014597  mov     edx, [rbp+47h+Source]
0x18001459a  mov     ebx, edx
0x18001459c  imul    rbx, [rdi+10h]
0x1800145a1  add     rbx, rsi
0x1800145a4  jmp     loc_180014636
0x1800145a9  movzx   eax, word ptr [rdi+6]
0x1800145ad  xorps   xmm0, xmm0
0x1800145b0  mov     [rbp+47h+var_60], ax
0x1800145b4  mov     esi, r9d
0x1800145b7  mov     al, [rdi+8]
0x1800145ba  mov     [rbp+47h+var_5E], al
0x1800145bd  mov     eax, [rbp+47h+Source]
0x1800145c0  mov     [rbp+47h+var_5C], r9d
0x1800145c4  mov     [rbp+47h+var_58], r9w
0x1800145c9  movdqu  [rbp+47h+var_50], xmm0
0x1800145ce  test    eax, eax
0x1800145d0  jz      short loc_1800145F4
0x1800145d2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800145d6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800145da  lea     rcx, [rbp+47h+var_60]; this
0x1800145de  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800145e3  test    al, al
0x1800145e5  mov     eax, [rbp+47h+Source]
0x1800145e8  jz      short loc_1800145F0
0x1800145ea  inc     esi
0x1800145ec  cmp     esi, eax
0x1800145ee  jb      short loc_1800145D2
0x1800145f0  mov     rbx, [rbp+47h+var_A8]
0x1800145f4  cmp     eax, esi
0x1800145f6  jz      short loc_180014636
0x1800145f8  mov     al, [rbp+47h+var_9E]
0x1800145fb  mov     [rbp+47h+Source], esi
0x1800145fe  cmp     al, 1
0x180014600  jnz     short loc_180014616
0x180014602  mov     eax, 2
0x180014607  mov     [rbp+47h+var_B0], si
0x18001460b  mov     r9d, eax
0x18001460e  lea     r8, [rbp+47h+var_B0]
0x180014612  mov     edx, eax
0x180014614  jmp     short loc_180014626
0x180014616  cmp     al, 2
0x180014618  jnz     short loc_180014636
0x18001461a  mov     edx, 4; DestinationSize
0x18001461f  lea     r8, [rbp+47h+Source]; Source
0x180014623  mov     r9d, edx; SourceSize
0x180014626  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001462a  call    cs:__imp_memcpy_s
0x180014631  nop     dword ptr [rax+rax+00h]
0x180014636  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001463a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001463e  lea     rcx, [rbp+47h+var_A0]; this
0x180014642  mov     [rbp+47h+var_A8], rbx
0x180014646  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001464b  xor     r9d, r9d
0x18001464e  mov     sil, al
0x180014651  test    al, al
0x180014653  jnz     loc_1800144F6
0x180014659  mov     rbx, [rbp+47h+var_A8]
0x18001465d  mov     [rdi+20h], rbx
0x180014661  mov     rcx, r9
0x180014664  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180014668  jnz     loc_1800146F3
0x18001466e  movzx   eax, [rbp+47h+var_A0]
0x180014672  mov     [rbp+47h+Source], 1
0x180014679  mov     [rbp+47h+var_98], r14w
0x18001467e  mov     [rbp+47h+Buf2], r9
0x180014682  mov     [rbp+47h+Buf2+8], r15
0x180014686  test    ax, ax
0x180014689  jnz     short loc_1800146DB
0x18001468b  movzx   ecx, r14w
0x18001468f  add     rcx, 2
0x180014693  jmp     short loc_1800146DE
0x180014695  mov     eax, [rbp+47h+arg_28]
0x180014698  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18001469c  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800146a0  mov     r9, r13; void *
0x1800146a3  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800146a7  mov     rcx, rdi; this
0x1800146aa  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800146af  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800146b4  xor     r9d, r9d
0x1800146b7  mov     [rbp+47h+var_A8], rax
0x1800146bb  mov     rbx, rax
0x1800146be  test    rax, rax
0x1800146c1  jnz     short loc_1800146CA
0x1800146c3  mov     al, 1
0x1800146c5  jmp     loc_180014804
0x1800146ca  mov     byte ptr [rbp+47h+arg_0], 1
0x1800146ce  jmp     short loc_1800146D4
0x1800146d0  mov     [rbp+47h+var_A8], rbx
0x1800146d4  test    sil, sil
0x1800146d7  jnz     short loc_180014661
0x1800146d9  jmp     short loc_18001465D
0x1800146db  mov     rcx, rax
0x1800146de  mov     al, [rbp+47h+var_9E]
0x1800146e1  cmp     al, 1
0x1800146e3  jnz     short loc_1800146EB
0x1800146e5  add     rcx, 2
0x1800146e9  jmp     short loc_1800146F3
0x1800146eb  cmp     al, 2
0x1800146ed  jnz     short loc_1800146F3
0x1800146ef  add     rcx, 4
0x1800146f3  movzx   eax, word ptr [rdi+6]
0x1800146f7  mov     dl, [rdi+8]
0x1800146fa  mov     r8d, [rbp+47h+arg_28]
0x1800146fe  mov     [rbp+47h+var_80], ax
0x180014702  mov     [rbp+47h+var_7E], dl
0x180014705  mov     [rbp+47h+var_7C], r8d
0x180014709  mov     [rbp+47h+var_78], r12w
0x18001470e  mov     [rbp+47h+var_70], r9
0x180014712  mov     [rbp+47h+var_68], r13
0x180014716  test    ax, ax
0x180014719  jnz     short loc_180014723
0x18001471b  movzx   eax, r12w
0x18001471f  add     rax, 2
0x180014723  cmp     dl, 1
0x180014726  jnz     short loc_18001472E
0x180014728  add     rax, 2
0x18001472c  jmp     short loc_180014737
0x18001472e  cmp     dl, 2
0x180014731  jnz     short loc_180014737
0x180014733  add     rax, 4
0x180014737  mov     rdx, [rdi+28h]
0x18001473b  lea     rsi, [rax+rcx]
0x18001473f  mov     r9, [rdi+20h]
0x180014743  mov     rcx, rdx
0x180014746  sub     rcx, r9
0x180014749  cmp     r9, rdx
0x18001474c  sbb     rax, rax
0x18001474f  and     rax, rcx
0x180014752  cmp     rax, rsi
0x180014755  jb      loc_180014802
0x18001475b  sub     rdx, rsi
0x18001475e  lea     rcx, [rsi+rbx]; Destination
0x180014762  sub     rdx, rbx; DestinationSize
0x180014765  sub     r9, rbx; SourceSize
0x180014768  mov     r8, rbx; Source
0x18001476b  call    cs:__imp_memmove_s
0x180014772  nop     dword ptr [rax+rax+00h]
0x180014777  add     [rdi+20h], rsi
0x18001477b  xor     ebx, ebx
0x18001477d  cmp     byte ptr [rbp+47h+arg_0], bl
0x180014780  jnz     short loc_180014795
0x180014782  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014786  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001478a  lea     rcx, [rbp+47h+var_A0]; this
0x18001478e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014793  jmp     short loc_1800147E8
0x180014795  mov     cl, [rbp+47h+var_9E]
0x180014798  test    cl, cl
0x18001479a  jz      short loc_1800147E8
0x18001479c  mov     eax, [rbp+47h+Source]
0x18001479f  lea     r8d, [rax+1]
0x1800147a3  cmp     eax, r8d
0x1800147a6  jz      short loc_1800147E8
0x1800147a8  mov     [rbp+47h+Source], r8d
0x1800147ac  cmp     cl, 1
0x1800147af  jnz     short loc_1800147C5
0x1800147b1  mov     r9d, 2
0x1800147b7  mov     [rbp+47h+arg_0], r8w
0x1800147bc  mov     edx, r9d
0x1800147bf  lea     r8, [rbp+47h+arg_0]
0x1800147c3  jmp     short loc_1800147D8
0x1800147c5  cmp     cl, 2
0x1800147c8  jnz     short loc_1800147E8
0x1800147ca  mov     eax, 4
0x1800147cf  lea     r8, [rbp+47h+Source]; Source
0x1800147d3  mov     r9d, eax; SourceSize
0x1800147d6  mov     edx, eax; DestinationSize
0x1800147d8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800147dc  call    cs:__imp_memcpy_s
0x1800147e3  nop     dword ptr [rax+rax+00h]
0x1800147e8  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800147ec  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800147f0  lea     rcx, [rbp+47h+var_80]; this
0x1800147f4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800147f9  mov     byte ptr [rdi+38h], 1
0x1800147fd  jmp     loc_1800146C3
0x180014802  xor     al, al
0x180014804  add     rsp, 0A8h
0x18001480b  pop     r15
0x18001480d  pop     r14
0x18001480f  pop     r13
0x180014811  pop     r12
0x180014813  pop     rdi
0x180014814  pop     rsi
0x180014815  pop     rbx
0x180014816  pop     rbp
0x180014817  retn
```
