# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180019860`
- end: `0x180019a3a`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001976c`

## callees

- `0x180019860`
- `0x180024b44`
- `0x180024ed8`
- `0x1800256f0`
- `0x180026554`
- `0x1800275dc`
- `0x180027d98`
- `0x180028228`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800199d0`
- `msvcrt!memmove_s` at `0x1800199d0`

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
0x180019860  mov     [rsp-38h+arg_8], rbx
0x180019865  mov     [rsp-38h+arg_18], r9
0x18001986a  push    rbp
0x18001986b  push    rsi
0x18001986c  push    rdi
0x18001986d  push    r12
0x18001986f  push    r13
0x180019871  push    r14
0x180019873  push    r15
0x180019875  mov     rbp, rsp
0x180019878  sub     rsp, 70h
0x18001987c  mov     rdi, [rcx+18h]
0x180019880  mov     r14, r8
0x180019883  mov     r15, rdx
0x180019886  mov     rbx, rcx
0x180019889  test    rdi, rdi
0x18001988c  jz      loc_180019A20
0x180019892  movzx   eax, word ptr [rcx+2]
0x180019896  add     rdi, 0Ah
0x18001989a  mov     [rbp+var_40], ax
0x18001989e  xorps   xmm0, xmm0
0x1800198a1  mov     al, [rcx+4]
0x1800198a4  mov     [rbp+var_3E], al
0x1800198a7  xor     eax, eax
0x1800198a9  mov     [rbp+var_38], ax
0x1800198ad  xor     sil, sil
0x1800198b0  mov     [rbp+arg_0], rdi
0x1800198b4  mov     [rbp+var_3C], 0
0x1800198bb  movdqu  [rbp+var_30], xmm0
0x1800198c0  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800198c4  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800198c8  lea     rcx, [rbp+var_40]; this
0x1800198cc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800198d1  mov     r12d, [rbp+arg_28]
0x1800198d5  mov     r13, [rbp+arg_20]
0x1800198d9  test    al, al
0x1800198db  jz      short loc_180019944
0x1800198dd  mov     r8, r14; unsigned __int64
0x1800198e0  lea     rcx, [rbp+var_40]; this
0x1800198e4  mov     rdx, r15; void *
0x1800198e7  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800198ec  test    eax, eax
0x1800198ee  js      short loc_180019936
0x1800198f0  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800198f4  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800198f8  mov     rcx, rbx; this
0x1800198fb  jz      short loc_18001990B
0x1800198fd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180019902  mov     rdi, rax
0x180019905  mov     [rbp+arg_0], rax
0x180019909  jmp     short loc_1800198C0
0x18001990b  mov     r9, [rbp+arg_18]; void *
0x18001990f  mov     [rsp+70h+var_48], r12d; unsigned int
0x180019914  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180019919  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001991e  mov     [rbp+arg_0], rax
0x180019922  mov     rdi, rax
0x180019925  test    rax, rax
0x180019928  jnz     short loc_180019931
0x18001992a  mov     al, 1
0x18001992c  jmp     loc_180019A22
0x180019931  mov     sil, 1
0x180019934  jmp     short loc_18001993A
0x180019936  mov     [rbp+arg_0], rdi
0x18001993a  xor     r8d, r8d
0x18001993d  test    sil, sil
0x180019940  jnz     short loc_180019970
0x180019942  jmp     short loc_18001994C
0x180019944  mov     rdi, [rbp+arg_0]
0x180019948  mov     [rbx+20h], rdi
0x18001994c  lea     rcx, [rbp+var_40]; this
0x180019950  mov     [rbp+var_3C], 1
0x180019957  mov     [rbp+var_38], r14w
0x18001995c  mov     qword ptr [rbp+var_30], 0
0x180019964  mov     qword ptr [rbp+var_30+8], r15
0x180019968  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001996d  mov     r8, rax
0x180019970  movzx   ecx, word ptr [rbx+6]
0x180019974  mov     rax, [rbp+arg_18]
0x180019978  mov     [rbp+var_20], cx
0x18001997c  mov     cl, [rbx+8]
0x18001997f  mov     [rbp+var_1E], cl
0x180019982  lea     rcx, [rbp+var_20]; this
0x180019986  mov     [rbp+var_1C], r12d
0x18001998a  mov     [rbp+var_18], r13w
0x18001998f  mov     [rbp+var_10], 0
0x180019997  mov     [rbp+var_8], rax
0x18001999b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800199a0  mov     rdx, [rbx+28h]
0x1800199a4  mov     r9, [rbx+20h]
0x1800199a8  mov     rcx, rdx
0x1800199ab  sub     rcx, r9
0x1800199ae  lea     r14, [rax+r8]
0x1800199b2  cmp     r9, rdx
0x1800199b5  sbb     rax, rax
0x1800199b8  and     rax, rcx
0x1800199bb  cmp     rax, r14
0x1800199be  jb      short loc_180019A20
0x1800199c0  sub     rdx, r14
0x1800199c3  lea     rcx, [r14+rdi]; Destination
0x1800199c7  sub     rdx, rdi; DestinationSize
0x1800199ca  sub     r9, rdi; SourceSize
0x1800199cd  mov     r8, rdi; Source
0x1800199d0  call    cs:__imp_memmove_s
0x1800199d6  add     [rbx+20h], r14
0x1800199da  test    sil, sil
0x1800199dd  jnz     short loc_1800199F2
0x1800199df  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800199e3  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800199e7  lea     rcx, [rbp+var_40]; this
0x1800199eb  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800199f0  jmp     short loc_180019A06
0x1800199f2  cmp     [rbp+var_3E], 0
0x1800199f6  jz      short loc_180019A06
0x1800199f8  mov     edx, [rbp+var_3C]
0x1800199fb  lea     rcx, [rbp+var_40]; this
0x1800199ff  inc     edx; unsigned int
0x180019a01  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180019a06  mov     r8, [rbx+20h]; unsigned __int8 *
0x180019a0a  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180019a0e  lea     rcx, [rbp+var_20]; this
0x180019a12  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180019a17  mov     byte ptr [rbx+38h], 1
0x180019a1b  jmp     loc_18001992A
0x180019a20  xor     al, al
0x180019a22  mov     rbx, [rsp+70h+arg_8]
0x180019a2a  add     rsp, 70h
0x180019a2e  pop     r15
0x180019a30  pop     r14
0x180019a32  pop     r13
0x180019a34  pop     r12
0x180019a36  pop     rdi
0x180019a37  pop     rsi
0x180019a38  pop     rbp
0x180019a39  retn
```
