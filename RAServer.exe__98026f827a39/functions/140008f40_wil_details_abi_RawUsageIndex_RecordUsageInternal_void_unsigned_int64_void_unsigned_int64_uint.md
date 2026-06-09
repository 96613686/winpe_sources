# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140008f40`
- end: `0x14000911a`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008e4c`

## callees

- `0x14000518c`
- `0x140005fd8`
- `0x1400069c8`
- `0x1400089d4`
- `0x140008f40`
- `0x14000a878`
- `0x14000b170`
- `0x14000b868`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400090b0`
- `msvcrt!memmove_s` at `0x1400090b0`

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
0x140008f40  mov     [rsp-38h+arg_8], rbx
0x140008f45  mov     [rsp-38h+arg_18], r9
0x140008f4a  push    rbp
0x140008f4b  push    rsi
0x140008f4c  push    rdi
0x140008f4d  push    r12
0x140008f4f  push    r13
0x140008f51  push    r14
0x140008f53  push    r15
0x140008f55  mov     rbp, rsp
0x140008f58  sub     rsp, 70h
0x140008f5c  mov     rdi, [rcx+18h]
0x140008f60  mov     r14, r8
0x140008f63  mov     r15, rdx
0x140008f66  mov     rbx, rcx
0x140008f69  test    rdi, rdi
0x140008f6c  jz      loc_140009100
0x140008f72  movzx   eax, word ptr [rcx+2]
0x140008f76  add     rdi, 0Ah
0x140008f7a  mov     [rbp+var_40], ax
0x140008f7e  xorps   xmm0, xmm0
0x140008f81  mov     al, [rcx+4]
0x140008f84  mov     [rbp+var_3E], al
0x140008f87  xor     eax, eax
0x140008f89  mov     [rbp+var_38], ax
0x140008f8d  xor     sil, sil
0x140008f90  mov     [rbp+arg_0], rdi
0x140008f94  mov     [rbp+var_3C], 0
0x140008f9b  movdqu  [rbp+var_30], xmm0
0x140008fa0  mov     r8, [rbx+20h]; unsigned __int8 *
0x140008fa4  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x140008fa8  lea     rcx, [rbp+var_40]; this
0x140008fac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140008fb1  mov     r12d, [rbp+arg_28]
0x140008fb5  mov     r13, [rbp+arg_20]
0x140008fb9  test    al, al
0x140008fbb  jz      short loc_140009024
0x140008fbd  mov     r8, r14; unsigned __int64
0x140008fc0  lea     rcx, [rbp+var_40]; this
0x140008fc4  mov     rdx, r15; void *
0x140008fc7  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x140008fcc  test    eax, eax
0x140008fce  js      short loc_140009016
0x140008fd0  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x140008fd4  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x140008fd8  mov     rcx, rbx; this
0x140008fdb  jz      short loc_140008FEB
0x140008fdd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x140008fe2  mov     rdi, rax
0x140008fe5  mov     [rbp+arg_0], rax
0x140008fe9  jmp     short loc_140008FA0
0x140008feb  mov     r9, [rbp+arg_18]; void *
0x140008fef  mov     [rsp+70h+var_48], r12d; unsigned int
0x140008ff4  mov     [rsp+70h+var_50], r13; unsigned __int64
0x140008ff9  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140008ffe  mov     [rbp+arg_0], rax
0x140009002  mov     rdi, rax
0x140009005  test    rax, rax
0x140009008  jnz     short loc_140009011
0x14000900a  mov     al, 1
0x14000900c  jmp     loc_140009102
0x140009011  mov     sil, 1
0x140009014  jmp     short loc_14000901A
0x140009016  mov     [rbp+arg_0], rdi
0x14000901a  xor     r8d, r8d
0x14000901d  test    sil, sil
0x140009020  jnz     short loc_140009050
0x140009022  jmp     short loc_14000902C
0x140009024  mov     rdi, [rbp+arg_0]
0x140009028  mov     [rbx+20h], rdi
0x14000902c  lea     rcx, [rbp+var_40]; this
0x140009030  mov     [rbp+var_3C], 1
0x140009037  mov     [rbp+var_38], r14w
0x14000903c  mov     qword ptr [rbp+var_30], 0
0x140009044  mov     qword ptr [rbp+var_30+8], r15
0x140009048  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000904d  mov     r8, rax
0x140009050  movzx   ecx, word ptr [rbx+6]
0x140009054  mov     rax, [rbp+arg_18]
0x140009058  mov     [rbp+var_20], cx
0x14000905c  mov     cl, [rbx+8]
0x14000905f  mov     [rbp+var_1E], cl
0x140009062  lea     rcx, [rbp+var_20]; this
0x140009066  mov     [rbp+var_1C], r12d
0x14000906a  mov     [rbp+var_18], r13w
0x14000906f  mov     [rbp+var_10], 0
0x140009077  mov     [rbp+var_8], rax
0x14000907b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140009080  mov     rdx, [rbx+28h]
0x140009084  mov     r9, [rbx+20h]
0x140009088  mov     rcx, rdx
0x14000908b  sub     rcx, r9
0x14000908e  lea     r14, [rax+r8]
0x140009092  cmp     r9, rdx
0x140009095  sbb     rax, rax
0x140009098  and     rax, rcx
0x14000909b  cmp     rax, r14
0x14000909e  jb      short loc_140009100
0x1400090a0  sub     rdx, r14
0x1400090a3  lea     rcx, [r14+rdi]; Destination
0x1400090a7  sub     rdx, rdi; DestinationSize
0x1400090aa  sub     r9, rdi; SourceSize
0x1400090ad  mov     r8, rdi; Source
0x1400090b0  call    cs:__imp_memmove_s
0x1400090b6  add     [rbx+20h], r14
0x1400090ba  test    sil, sil
0x1400090bd  jnz     short loc_1400090D2
0x1400090bf  mov     r8, [rbx+20h]; unsigned __int8 *
0x1400090c3  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1400090c7  lea     rcx, [rbp+var_40]; this
0x1400090cb  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400090d0  jmp     short loc_1400090E6
0x1400090d2  cmp     [rbp+var_3E], 0
0x1400090d6  jz      short loc_1400090E6
0x1400090d8  mov     edx, [rbp+var_3C]
0x1400090db  lea     rcx, [rbp+var_40]; this
0x1400090df  inc     edx; unsigned int
0x1400090e1  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1400090e6  mov     r8, [rbx+20h]; unsigned __int8 *
0x1400090ea  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1400090ee  lea     rcx, [rbp+var_20]; this
0x1400090f2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400090f7  mov     byte ptr [rbx+38h], 1
0x1400090fb  jmp     loc_14000900A
0x140009100  xor     al, al
0x140009102  mov     rbx, [rsp+70h+arg_8]
0x14000910a  add     rsp, 70h
0x14000910e  pop     r15
0x140009110  pop     r14
0x140009112  pop     r13
0x140009114  pop     r12
0x140009116  pop     rdi
0x140009117  pop     rsi
0x140009118  pop     rbp
0x140009119  retn
```
