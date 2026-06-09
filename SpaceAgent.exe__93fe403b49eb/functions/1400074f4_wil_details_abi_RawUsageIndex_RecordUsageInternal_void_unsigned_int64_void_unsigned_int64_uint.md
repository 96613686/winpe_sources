# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1400074f4`
- end: `0x1400076ce`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007400`

## callees

- `0x140004ecc`
- `0x140005358`
- `0x140005c14`
- `0x140006edc`
- `0x1400074f4`
- `0x140007fc0`
- `0x140008dfc`
- `0x1400091b4`

## import_xrefs

- `msvcrt!memmove_s` at `0x140007664`
- `msvcrt!memmove_s` at `0x140007664`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v10; // rdi
  char v11; // si
  bool v12; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r13
  int v15; // eax
  unsigned __int64 Size; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  const void *v22; // [rsp+30h] [rbp-40h] BYREF
  __int16 v23; // [rsp+38h] [rbp-38h]
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int16 v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+52h] [rbp-1Eh]
  unsigned int v27; // [rsp+54h] [rbp-1Ch]
  __int16 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  void *v30; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v32; // [rsp+C8h] [rbp+58h]

  v32 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    LOWORD(v22) = *((_WORD *)this + 1);
    BYTE2(v22) = *((_BYTE *)this + 4);
    v23 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    HIDWORD(v22) = 0;
    v24 = 0;
    while ( 1 )
    {
      v12 = wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v22,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4));
      v13 = a6;
      v14 = a5;
      if ( !v12 )
      {
        v10 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v15 = wil::details_abi::UsageIndexProperty::Compare(&v22, a2, a3);
      if ( v15 < 0 )
      {
        InsertionPointOrIncrement = v10;
        goto LABEL_11;
      }
      if ( !v15 )
        break;
      v10 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v22,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v10;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v22,
                                  InsertionPointOrIncrement,
                                  v32,
                                  v14,
                                  v13);
    v10 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v11 = 1;
LABEL_11:
    if ( v11 )
      goto LABEL_15;
LABEL_14:
    HIDWORD(v22) = 1;
    v23 = a3;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v25 = *((_WORD *)this + 3);
    v26 = *((_BYTE *)this + 8);
    v27 = v13;
    v28 = v14;
    v29 = 0;
    v30 = v32;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v25);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( BYTE2(v22) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v22,
            HIDWORD(v22) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v25,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400074f4  mov     [rsp-38h+arg_8], rbx
0x1400074f9  mov     [rsp-38h+arg_18], r9
0x1400074fe  push    rbp
0x1400074ff  push    rsi
0x140007500  push    rdi
0x140007501  push    r12
0x140007503  push    r13
0x140007505  push    r14
0x140007507  push    r15
0x140007509  mov     rbp, rsp
0x14000750c  sub     rsp, 70h
0x140007510  mov     rdi, [rcx+18h]
0x140007514  mov     r14, r8
0x140007517  mov     r15, rdx
0x14000751a  mov     rbx, rcx
0x14000751d  test    rdi, rdi
0x140007520  jz      loc_1400076B4
0x140007526  movzx   eax, word ptr [rcx+2]
0x14000752a  add     rdi, 0Ah
0x14000752e  mov     [rbp+var_40], ax
0x140007532  xorps   xmm0, xmm0
0x140007535  mov     al, [rcx+4]
0x140007538  mov     [rbp+var_3E], al
0x14000753b  xor     eax, eax
0x14000753d  mov     [rbp+var_38], ax
0x140007541  xor     sil, sil
0x140007544  mov     [rbp+arg_0], rdi
0x140007548  mov     [rbp+var_3C], 0
0x14000754f  movdqu  [rbp+var_30], xmm0
0x140007554  mov     r8, [rbx+20h]; unsigned __int8 *
0x140007558  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000755c  lea     rcx, [rbp+var_40]; this
0x140007560  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140007565  mov     r12d, [rbp+arg_28]
0x140007569  mov     r13, [rbp+arg_20]
0x14000756d  test    al, al
0x14000756f  jz      short loc_1400075D8
0x140007571  mov     r8, r14; unsigned __int64
0x140007574  lea     rcx, [rbp+var_40]; this
0x140007578  mov     rdx, r15; void *
0x14000757b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x140007580  test    eax, eax
0x140007582  js      short loc_1400075CA
0x140007584  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x140007588  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x14000758c  mov     rcx, rbx; this
0x14000758f  jz      short loc_14000759F
0x140007591  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x140007596  mov     rdi, rax
0x140007599  mov     [rbp+arg_0], rax
0x14000759d  jmp     short loc_140007554
0x14000759f  mov     r9, [rbp+arg_18]; void *
0x1400075a3  mov     [rsp+70h+var_48], r12d; unsigned int
0x1400075a8  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1400075ad  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1400075b2  mov     [rbp+arg_0], rax
0x1400075b6  mov     rdi, rax
0x1400075b9  test    rax, rax
0x1400075bc  jnz     short loc_1400075C5
0x1400075be  mov     al, 1
0x1400075c0  jmp     loc_1400076B6
0x1400075c5  mov     sil, 1
0x1400075c8  jmp     short loc_1400075CE
0x1400075ca  mov     [rbp+arg_0], rdi
0x1400075ce  xor     r8d, r8d
0x1400075d1  test    sil, sil
0x1400075d4  jnz     short loc_140007604
0x1400075d6  jmp     short loc_1400075E0
0x1400075d8  mov     rdi, [rbp+arg_0]
0x1400075dc  mov     [rbx+20h], rdi
0x1400075e0  lea     rcx, [rbp+var_40]; this
0x1400075e4  mov     [rbp+var_3C], 1
0x1400075eb  mov     [rbp+var_38], r14w
0x1400075f0  mov     qword ptr [rbp+var_30], 0
0x1400075f8  mov     qword ptr [rbp+var_30+8], r15
0x1400075fc  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140007601  mov     r8, rax
0x140007604  movzx   ecx, word ptr [rbx+6]
0x140007608  mov     rax, [rbp+arg_18]
0x14000760c  mov     [rbp+var_20], cx
0x140007610  mov     cl, [rbx+8]
0x140007613  mov     [rbp+var_1E], cl
0x140007616  lea     rcx, [rbp+var_20]; this
0x14000761a  mov     [rbp+var_1C], r12d
0x14000761e  mov     [rbp+var_18], r13w
0x140007623  mov     [rbp+var_10], 0
0x14000762b  mov     [rbp+var_8], rax
0x14000762f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140007634  mov     rdx, [rbx+28h]
0x140007638  mov     r9, [rbx+20h]
0x14000763c  mov     rcx, rdx
0x14000763f  sub     rcx, r9
0x140007642  lea     r14, [rax+r8]
0x140007646  cmp     r9, rdx
0x140007649  sbb     rax, rax
0x14000764c  and     rax, rcx
0x14000764f  cmp     rax, r14
0x140007652  jb      short loc_1400076B4
0x140007654  sub     rdx, r14
0x140007657  lea     rcx, [r14+rdi]; Destination
0x14000765b  sub     rdx, rdi; DestinationSize
0x14000765e  sub     r9, rdi; SourceSize
0x140007661  mov     r8, rdi; Source
0x140007664  call    cs:__imp_memmove_s
0x14000766a  add     [rbx+20h], r14
0x14000766e  test    sil, sil
0x140007671  jnz     short loc_140007686
0x140007673  mov     r8, [rbx+20h]; unsigned __int8 *
0x140007677  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000767b  lea     rcx, [rbp+var_40]; this
0x14000767f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140007684  jmp     short loc_14000769A
0x140007686  cmp     [rbp+var_3E], 0
0x14000768a  jz      short loc_14000769A
0x14000768c  mov     edx, [rbp+var_3C]
0x14000768f  lea     rcx, [rbp+var_40]; this
0x140007693  inc     edx; unsigned int
0x140007695  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x14000769a  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000769e  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1400076a2  lea     rcx, [rbp+var_20]; this
0x1400076a6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400076ab  mov     byte ptr [rbx+38h], 1
0x1400076af  jmp     loc_1400075BE
0x1400076b4  xor     al, al
0x1400076b6  mov     rbx, [rsp+70h+arg_8]
0x1400076be  add     rsp, 70h
0x1400076c2  pop     r15
0x1400076c4  pop     r14
0x1400076c6  pop     r13
0x1400076c8  pop     r12
0x1400076ca  pop     rdi
0x1400076cb  pop     rsi
0x1400076cc  pop     rbp
0x1400076cd  retn
```
