# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180010f1c`
- end: `0x1800110f6`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dd00`

## callees

- `0x180008840`
- `0x18000f79c`
- `0x18000fa84`
- `0x180010ce4`
- `0x180010f1c`
- `0x180011a5c`
- `0x180011d14`
- `0x1800120ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001108c`
- `msvcrt!memmove_s` at `0x18001108c`

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
0x180010f1c  mov     [rsp-38h+arg_8], rbx
0x180010f21  mov     [rsp-38h+arg_18], r9
0x180010f26  push    rbp
0x180010f27  push    rsi
0x180010f28  push    rdi
0x180010f29  push    r12
0x180010f2b  push    r13
0x180010f2d  push    r14
0x180010f2f  push    r15
0x180010f31  mov     rbp, rsp
0x180010f34  sub     rsp, 70h
0x180010f38  mov     rdi, [rcx+18h]
0x180010f3c  mov     r14, r8
0x180010f3f  mov     r15, rdx
0x180010f42  mov     rbx, rcx
0x180010f45  test    rdi, rdi
0x180010f48  jz      loc_1800110DC
0x180010f4e  movzx   eax, word ptr [rcx+2]
0x180010f52  add     rdi, 0Ah
0x180010f56  mov     [rbp+var_40], ax
0x180010f5a  xorps   xmm0, xmm0
0x180010f5d  mov     al, [rcx+4]
0x180010f60  mov     [rbp+var_3E], al
0x180010f63  xor     eax, eax
0x180010f65  mov     [rbp+var_38], ax
0x180010f69  xor     sil, sil
0x180010f6c  mov     [rbp+arg_0], rdi
0x180010f70  mov     [rbp+var_3C], 0
0x180010f77  movdqu  [rbp+var_30], xmm0
0x180010f7c  mov     r8, [rbx+20h]; unsigned __int8 *
0x180010f80  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180010f84  lea     rcx, [rbp+var_40]; this
0x180010f88  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180010f8d  mov     r12d, [rbp+arg_28]
0x180010f91  mov     r13, [rbp+arg_20]
0x180010f95  test    al, al
0x180010f97  jz      short loc_180011000
0x180010f99  mov     r8, r14; unsigned __int64
0x180010f9c  lea     rcx, [rbp+var_40]; this
0x180010fa0  mov     rdx, r15; void *
0x180010fa3  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180010fa8  test    eax, eax
0x180010faa  js      short loc_180010FF2
0x180010fac  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180010fb0  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180010fb4  mov     rcx, rbx; this
0x180010fb7  jz      short loc_180010FC7
0x180010fb9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180010fbe  mov     rdi, rax
0x180010fc1  mov     [rbp+arg_0], rax
0x180010fc5  jmp     short loc_180010F7C
0x180010fc7  mov     r9, [rbp+arg_18]; void *
0x180010fcb  mov     [rsp+70h+var_48], r12d; unsigned int
0x180010fd0  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180010fd5  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180010fda  mov     [rbp+arg_0], rax
0x180010fde  mov     rdi, rax
0x180010fe1  test    rax, rax
0x180010fe4  jnz     short loc_180010FED
0x180010fe6  mov     al, 1
0x180010fe8  jmp     loc_1800110DE
0x180010fed  mov     sil, 1
0x180010ff0  jmp     short loc_180010FF6
0x180010ff2  mov     [rbp+arg_0], rdi
0x180010ff6  xor     r8d, r8d
0x180010ff9  test    sil, sil
0x180010ffc  jnz     short loc_18001102C
0x180010ffe  jmp     short loc_180011008
0x180011000  mov     rdi, [rbp+arg_0]
0x180011004  mov     [rbx+20h], rdi
0x180011008  lea     rcx, [rbp+var_40]; this
0x18001100c  mov     [rbp+var_3C], 1
0x180011013  mov     [rbp+var_38], r14w
0x180011018  mov     qword ptr [rbp+var_30], 0
0x180011020  mov     qword ptr [rbp+var_30+8], r15
0x180011024  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180011029  mov     r8, rax
0x18001102c  movzx   ecx, word ptr [rbx+6]
0x180011030  mov     rax, [rbp+arg_18]
0x180011034  mov     [rbp+var_20], cx
0x180011038  mov     cl, [rbx+8]
0x18001103b  mov     [rbp+var_1E], cl
0x18001103e  lea     rcx, [rbp+var_20]; this
0x180011042  mov     [rbp+var_1C], r12d
0x180011046  mov     [rbp+var_18], r13w
0x18001104b  mov     [rbp+var_10], 0
0x180011053  mov     [rbp+var_8], rax
0x180011057  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001105c  mov     rdx, [rbx+28h]
0x180011060  mov     r9, [rbx+20h]
0x180011064  mov     rcx, rdx
0x180011067  sub     rcx, r9
0x18001106a  lea     r14, [rax+r8]
0x18001106e  cmp     r9, rdx
0x180011071  sbb     rax, rax
0x180011074  and     rax, rcx
0x180011077  cmp     rax, r14
0x18001107a  jb      short loc_1800110DC
0x18001107c  sub     rdx, r14
0x18001107f  lea     rcx, [r14+rdi]; Destination
0x180011083  sub     rdx, rdi; DestinationSize
0x180011086  sub     r9, rdi; SourceSize
0x180011089  mov     r8, rdi; Source
0x18001108c  call    cs:__imp_memmove_s
0x180011092  add     [rbx+20h], r14
0x180011096  test    sil, sil
0x180011099  jnz     short loc_1800110AE
0x18001109b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001109f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800110a3  lea     rcx, [rbp+var_40]; this
0x1800110a7  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800110ac  jmp     short loc_1800110C2
0x1800110ae  cmp     [rbp+var_3E], 0
0x1800110b2  jz      short loc_1800110C2
0x1800110b4  mov     edx, [rbp+var_3C]
0x1800110b7  lea     rcx, [rbp+var_40]; this
0x1800110bb  inc     edx; unsigned int
0x1800110bd  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800110c2  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800110c6  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800110ca  lea     rcx, [rbp+var_20]; this
0x1800110ce  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800110d3  mov     byte ptr [rbx+38h], 1
0x1800110d7  jmp     loc_180010FE6
0x1800110dc  xor     al, al
0x1800110de  mov     rbx, [rsp+70h+arg_8]
0x1800110e6  add     rsp, 70h
0x1800110ea  pop     r15
0x1800110ec  pop     r14
0x1800110ee  pop     r13
0x1800110f0  pop     r12
0x1800110f2  pop     rdi
0x1800110f3  pop     rsi
0x1800110f4  pop     rbp
0x1800110f5  retn
```
