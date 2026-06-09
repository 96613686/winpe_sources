# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800141a4`
- end: `0x180014388`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800140b0`

## callees

- `0x180011f2c`
- `0x180012264`
- `0x180012bf4`
- `0x180013c00`
- `0x1800141a4`
- `0x180014db4`
- `0x180015e68`
- `0x18001623c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800142e6`
- `msvcrt!memmove_s` at `0x1800142e6`

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
  char *v11; // rdi
  unsigned __int8 *v12; // r8
  char v13; // r14
  int v14; // eax
  unsigned __int8 *v15; // rax
  char v17; // cl
  unsigned __int64 Size; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rsi
  __int16 v24; // [rsp+30h] [rbp-48h] BYREF
  char v25; // [rsp+32h] [rbp-46h]
  int v26; // [rsp+34h] [rbp-44h]
  __int16 v27; // [rsp+38h] [rbp-40h]
  __int128 v28; // [rsp+40h] [rbp-38h]
  __int16 v29; // [rsp+50h] [rbp-28h] BYREF
  char v30; // [rsp+52h] [rbp-26h]
  unsigned int v31; // [rsp+54h] [rbp-24h]
  __int16 v32; // [rsp+58h] [rbp-20h]
  __int64 v33; // [rsp+60h] [rbp-18h]
  void *v34; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    v24 = *((_WORD *)this + 1);
    v25 = *((_BYTE *)this + 4);
    v27 = 0;
    v13 = 0;
    Source = v11;
    v26 = 0;
    v28 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 **)&Source,
              v12) )
      {
        v11 = (char *)Source;
        *((_QWORD *)this + 4) = Source;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v24, a2, a3);
      if ( v14 < 0 )
      {
        Source = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 *)Source);
      v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
      v11 = (char *)v15;
      Source = v15;
    }
    Source = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               (struct wil::details_abi::UsageIndexProperty *)&v24,
               (unsigned __int8 *)Source,
               a4,
               a5,
               a6);
    v11 = (char *)Source;
    if ( !Source )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      v26 = 1;
      v27 = a3;
      *(_QWORD *)&v28 = 0;
      *((_QWORD *)&v28 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v29 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v31 = a6;
    v30 = v17;
    v32 = a5;
    v33 = 0;
    v34 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v29);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( v25 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v24, v26 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v29,
        (unsigned __int8 **)&Source,
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
0x1800141a4  push    rbp
0x1800141a6  push    rbx
0x1800141a7  push    rsi
0x1800141a8  push    rdi
0x1800141a9  push    r12
0x1800141ab  push    r13
0x1800141ad  push    r14
0x1800141af  push    r15
0x1800141b1  mov     rbp, rsp
0x1800141b4  sub     rsp, 78h
0x1800141b8  mov     rdi, [rcx+18h]
0x1800141bc  mov     r13, r9
0x1800141bf  mov     r15, r8
0x1800141c2  mov     r12, rdx
0x1800141c5  mov     rbx, rcx
0x1800141c8  test    rdi, rdi
0x1800141cb  jz      loc_180014375
0x1800141d1  movzx   eax, word ptr [rcx+2]
0x1800141d5  add     rdi, 0Ah
0x1800141d9  mov     r8, [rcx+20h]
0x1800141dd  xorps   xmm0, xmm0
0x1800141e0  mov     [rbp+var_48], ax
0x1800141e4  mov     al, [rcx+4]
0x1800141e7  mov     [rbp+var_46], al
0x1800141ea  xor     eax, eax
0x1800141ec  mov     [rbp+var_40], ax
0x1800141f0  xor     r14b, r14b
0x1800141f3  mov     [rbp+Source], rdi
0x1800141f7  mov     [rbp+var_44], 0
0x1800141fe  movdqu  [rbp+var_38], xmm0
0x180014203  jmp     short loc_18001423D
0x180014205  mov     r8, r15; unsigned __int64
0x180014208  lea     rcx, [rbp+var_48]; this
0x18001420c  mov     rdx, r12; void *
0x18001420f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180014214  test    eax, eax
0x180014216  js      loc_180014338
0x18001421c  mov     r8, [rbp+Source]; unsigned __int8 *
0x180014220  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180014224  jz      loc_180014308
0x18001422a  mov     rcx, rbx; this
0x18001422d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180014232  mov     r8, [rbx+20h]; unsigned __int8 *
0x180014236  mov     rdi, rax
0x180014239  mov     [rbp+Source], rax
0x18001423d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180014241  lea     rcx, [rbp+var_48]; this
0x180014245  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001424a  mov     sil, al
0x18001424d  test    al, al
0x18001424f  jnz     short loc_180014205
0x180014251  mov     rdi, [rbp+Source]
0x180014255  mov     [rbx+20h], rdi
0x180014259  xor     r8d, r8d
0x18001425c  test    r14b, r14b
0x18001425f  jnz     short loc_180014281
0x180014261  lea     rcx, [rbp+var_48]; this
0x180014265  mov     [rbp+var_44], 1
0x18001426c  mov     [rbp+var_40], r15w
0x180014271  mov     qword ptr [rbp+var_38], r8
0x180014275  mov     qword ptr [rbp+var_38+8], r12
0x180014279  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001427e  mov     r8, rax
0x180014281  movzx   ecx, word ptr [rbx+6]
0x180014285  mov     eax, [rbp+arg_28]
0x180014288  mov     [rbp+var_28], cx
0x18001428c  mov     cl, [rbx+8]
0x18001428f  mov     [rbp+var_24], eax
0x180014292  mov     rax, [rbp+arg_20]
0x180014296  mov     [rbp+var_26], cl
0x180014299  lea     rcx, [rbp+var_28]; this
0x18001429d  mov     [rbp+var_20], ax
0x1800142a1  mov     [rbp+var_18], 0
0x1800142a9  mov     [rbp+var_10], r13
0x1800142ad  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800142b2  mov     rdx, [rbx+28h]
0x1800142b6  mov     r9, [rbx+20h]
0x1800142ba  mov     rcx, rdx
0x1800142bd  sub     rcx, r9
0x1800142c0  lea     rsi, [rax+r8]
0x1800142c4  cmp     r9, rdx
0x1800142c7  sbb     rax, rax
0x1800142ca  and     rax, rcx
0x1800142cd  cmp     rax, rsi
0x1800142d0  jb      loc_180014375
0x1800142d6  sub     rdx, rsi
0x1800142d9  lea     rcx, [rsi+rdi]; Destination
0x1800142dd  sub     rdx, rdi; DestinationSize
0x1800142e0  sub     r9, rdi; SourceSize
0x1800142e3  mov     r8, rdi; Source
0x1800142e6  call    cs:__imp_memmove_s
0x1800142ec  add     [rbx+20h], rsi
0x1800142f0  test    r14b, r14b
0x1800142f3  jnz     short loc_18001434A
0x1800142f5  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800142f9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800142fd  lea     rcx, [rbp+var_48]; this
0x180014301  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014306  jmp     short loc_18001435E
0x180014308  mov     ecx, [rbp+arg_28]
0x18001430b  mov     r9, r13; void *
0x18001430e  mov     [rsp+78h+var_50], ecx; unsigned int
0x180014312  mov     rcx, [rbp+arg_20]
0x180014316  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001431b  mov     rcx, rbx; this
0x18001431e  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180014323  mov     [rbp+Source], rax
0x180014327  mov     rdi, rax
0x18001432a  test    rax, rax
0x18001432d  jnz     short loc_180014333
0x18001432f  mov     al, 1
0x180014331  jmp     short loc_180014377
0x180014333  mov     r14b, 1
0x180014336  jmp     short loc_18001433C
0x180014338  mov     [rbp+Source], rdi
0x18001433c  test    sil, sil
0x18001433f  jnz     loc_180014259
0x180014345  jmp     loc_180014255
0x18001434a  cmp     [rbp+var_46], 0
0x18001434e  jz      short loc_18001435E
0x180014350  mov     edx, [rbp+var_44]
0x180014353  lea     rcx, [rbp+var_48]; this
0x180014357  inc     edx; unsigned int
0x180014359  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001435e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180014362  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180014366  lea     rcx, [rbp+var_28]; this
0x18001436a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001436f  mov     byte ptr [rbx+38h], 1
0x180014373  jmp     short loc_18001432F
0x180014375  xor     al, al
0x180014377  add     rsp, 78h
0x18001437b  pop     r15
0x18001437d  pop     r14
0x18001437f  pop     r13
0x180014381  pop     r12
0x180014383  pop     rdi
0x180014384  pop     rsi
0x180014385  pop     rbx
0x180014386  pop     rbp
0x180014387  retn
```
