# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180015304`
- end: `0x1800154de`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015210`

## callees

- `0x180005658`
- `0x180006438`
- `0x180007318`
- `0x180014cc4`
- `0x180015304`
- `0x18001a540`
- `0x18001aeb4`
- `0x18001b368`

## import_xrefs

- `msvcrt!memmove_s` at `0x180015474`
- `msvcrt!memmove_s` at `0x180015474`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        unsigned __int64 a3,
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
  __int16 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+32h] [rbp-3Eh]
  int v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h]
  __int16 v27; // [rsp+50h] [rbp-20h] BYREF
  char v28; // [rsp+52h] [rbp-1Eh]
  unsigned int v29; // [rsp+54h] [rbp-1Ch]
  __int16 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  void *v32; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    v22 = *((_WORD *)this + 1);
    v23 = *((_BYTE *)this + 4);
    v25 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    v24 = 0;
    v26 = 0;
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
      v15 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v22, a2, a3);
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
                                  v34,
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
    v24 = 1;
    v25 = a3;
    *(_QWORD *)&v26 = 0;
    *((_QWORD *)&v26 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v27 = *((_WORD *)this + 3);
    v28 = *((_BYTE *)this + 8);
    v29 = v13;
    v30 = v14;
    v31 = 0;
    v32 = v34;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( v23 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v22, v24 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
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
0x180015304  mov     [rsp-38h+arg_8], rbx
0x180015309  mov     [rsp-38h+arg_18], r9
0x18001530e  push    rbp
0x18001530f  push    rsi
0x180015310  push    rdi
0x180015311  push    r12
0x180015313  push    r13
0x180015315  push    r14
0x180015317  push    r15
0x180015319  mov     rbp, rsp
0x18001531c  sub     rsp, 70h
0x180015320  mov     rdi, [rcx+18h]
0x180015324  mov     r14, r8
0x180015327  mov     r15, rdx
0x18001532a  mov     rbx, rcx
0x18001532d  test    rdi, rdi
0x180015330  jz      loc_1800154C4
0x180015336  movzx   eax, word ptr [rcx+2]
0x18001533a  add     rdi, 0Ah
0x18001533e  mov     [rbp+var_40], ax
0x180015342  xorps   xmm0, xmm0
0x180015345  mov     al, [rcx+4]
0x180015348  mov     [rbp+var_3E], al
0x18001534b  xor     eax, eax
0x18001534d  mov     [rbp+var_38], ax
0x180015351  xor     sil, sil
0x180015354  mov     [rbp+arg_0], rdi
0x180015358  mov     [rbp+var_3C], 0
0x18001535f  movdqu  [rbp+var_30], xmm0
0x180015364  mov     r8, [rbx+20h]; unsigned __int8 *
0x180015368  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001536c  lea     rcx, [rbp+var_40]; this
0x180015370  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015375  mov     r12d, [rbp+arg_28]
0x180015379  mov     r13, [rbp+arg_20]
0x18001537d  test    al, al
0x18001537f  jz      short loc_1800153E8
0x180015381  mov     r8, r14; unsigned __int64
0x180015384  lea     rcx, [rbp+var_40]; this
0x180015388  mov     rdx, r15; void *
0x18001538b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180015390  test    eax, eax
0x180015392  js      short loc_1800153DA
0x180015394  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180015398  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001539c  mov     rcx, rbx; this
0x18001539f  jz      short loc_1800153AF
0x1800153a1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800153a6  mov     rdi, rax
0x1800153a9  mov     [rbp+arg_0], rax
0x1800153ad  jmp     short loc_180015364
0x1800153af  mov     r9, [rbp+arg_18]; void *
0x1800153b3  mov     [rsp+70h+var_48], r12d; unsigned int
0x1800153b8  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1800153bd  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800153c2  mov     [rbp+arg_0], rax
0x1800153c6  mov     rdi, rax
0x1800153c9  test    rax, rax
0x1800153cc  jnz     short loc_1800153D5
0x1800153ce  mov     al, 1
0x1800153d0  jmp     loc_1800154C6
0x1800153d5  mov     sil, 1
0x1800153d8  jmp     short loc_1800153DE
0x1800153da  mov     [rbp+arg_0], rdi
0x1800153de  xor     r8d, r8d
0x1800153e1  test    sil, sil
0x1800153e4  jnz     short loc_180015414
0x1800153e6  jmp     short loc_1800153F0
0x1800153e8  mov     rdi, [rbp+arg_0]
0x1800153ec  mov     [rbx+20h], rdi
0x1800153f0  lea     rcx, [rbp+var_40]; this
0x1800153f4  mov     [rbp+var_3C], 1
0x1800153fb  mov     [rbp+var_38], r14w
0x180015400  mov     qword ptr [rbp+var_30], 0
0x180015408  mov     qword ptr [rbp+var_30+8], r15
0x18001540c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180015411  mov     r8, rax
0x180015414  movzx   ecx, word ptr [rbx+6]
0x180015418  mov     rax, [rbp+arg_18]
0x18001541c  mov     [rbp+var_20], cx
0x180015420  mov     cl, [rbx+8]
0x180015423  mov     [rbp+var_1E], cl
0x180015426  lea     rcx, [rbp+var_20]; this
0x18001542a  mov     [rbp+var_1C], r12d
0x18001542e  mov     [rbp+var_18], r13w
0x180015433  mov     [rbp+var_10], 0
0x18001543b  mov     [rbp+var_8], rax
0x18001543f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180015444  mov     rdx, [rbx+28h]
0x180015448  mov     r9, [rbx+20h]
0x18001544c  mov     rcx, rdx
0x18001544f  sub     rcx, r9
0x180015452  lea     r14, [rax+r8]
0x180015456  cmp     r9, rdx
0x180015459  sbb     rax, rax
0x18001545c  and     rax, rcx
0x18001545f  cmp     rax, r14
0x180015462  jb      short loc_1800154C4
0x180015464  sub     rdx, r14
0x180015467  lea     rcx, [r14+rdi]; Destination
0x18001546b  sub     rdx, rdi; DestinationSize
0x18001546e  sub     r9, rdi; SourceSize
0x180015471  mov     r8, rdi; Source
0x180015474  call    cs:__imp_memmove_s
0x18001547a  add     [rbx+20h], r14
0x18001547e  test    sil, sil
0x180015481  jnz     short loc_180015496
0x180015483  mov     r8, [rbx+20h]; unsigned __int8 *
0x180015487  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001548b  lea     rcx, [rbp+var_40]; this
0x18001548f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180015494  jmp     short loc_1800154AA
0x180015496  cmp     [rbp+var_3E], 0
0x18001549a  jz      short loc_1800154AA
0x18001549c  mov     edx, [rbp+var_3C]
0x18001549f  lea     rcx, [rbp+var_40]; this
0x1800154a3  inc     edx; unsigned int
0x1800154a5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800154aa  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800154ae  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800154b2  lea     rcx, [rbp+var_20]; this
0x1800154b6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800154bb  mov     byte ptr [rbx+38h], 1
0x1800154bf  jmp     loc_1800153CE
0x1800154c4  xor     al, al
0x1800154c6  mov     rbx, [rsp+70h+arg_8]
0x1800154ce  add     rsp, 70h
0x1800154d2  pop     r15
0x1800154d4  pop     r14
0x1800154d6  pop     r13
0x1800154d8  pop     r12
0x1800154da  pop     rdi
0x1800154db  pop     rsi
0x1800154dc  pop     rbp
0x1800154dd  retn
```
