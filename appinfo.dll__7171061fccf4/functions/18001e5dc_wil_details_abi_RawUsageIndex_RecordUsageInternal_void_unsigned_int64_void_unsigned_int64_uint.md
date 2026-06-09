# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001e5dc`
- end: `0x18001e7b6`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e4e8`

## callees

- `0x180010e2c`
- `0x18001b604`
- `0x18001e5dc`
- `0x180021b6c`
- `0x180021fc0`
- `0x1800258f0`
- `0x180026170`
- `0x1800264c4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001e74c`
- `msvcrt!memmove_s` at `0x18001e74c`

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
0x18001e5dc  mov     [rsp-38h+arg_8], rbx
0x18001e5e1  mov     [rsp-38h+arg_18], r9
0x18001e5e6  push    rbp
0x18001e5e7  push    rsi
0x18001e5e8  push    rdi
0x18001e5e9  push    r12
0x18001e5eb  push    r13
0x18001e5ed  push    r14
0x18001e5ef  push    r15
0x18001e5f1  mov     rbp, rsp
0x18001e5f4  sub     rsp, 70h
0x18001e5f8  mov     rdi, [rcx+18h]
0x18001e5fc  mov     r14, r8
0x18001e5ff  mov     r15, rdx
0x18001e602  mov     rbx, rcx
0x18001e605  test    rdi, rdi
0x18001e608  jz      loc_18001E79C
0x18001e60e  movzx   eax, word ptr [rcx+2]
0x18001e612  add     rdi, 0Ah
0x18001e616  mov     [rbp+var_40], ax
0x18001e61a  xorps   xmm0, xmm0
0x18001e61d  mov     al, [rcx+4]
0x18001e620  mov     [rbp+var_3E], al
0x18001e623  xor     eax, eax
0x18001e625  mov     [rbp+var_38], ax
0x18001e629  xor     sil, sil
0x18001e62c  mov     [rbp+arg_0], rdi
0x18001e630  mov     [rbp+var_3C], 0
0x18001e637  movdqu  [rbp+var_30], xmm0
0x18001e63c  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001e640  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001e644  lea     rcx, [rbp+var_40]; this
0x18001e648  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001e64d  mov     r12d, [rbp+arg_28]
0x18001e651  mov     r13, [rbp+arg_20]
0x18001e655  test    al, al
0x18001e657  jz      short loc_18001E6C0
0x18001e659  mov     r8, r14; unsigned __int64
0x18001e65c  lea     rcx, [rbp+var_40]; this
0x18001e660  mov     rdx, r15; void *
0x18001e663  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001e668  test    eax, eax
0x18001e66a  js      short loc_18001E6B2
0x18001e66c  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001e670  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001e674  mov     rcx, rbx; this
0x18001e677  jz      short loc_18001E687
0x18001e679  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001e67e  mov     rdi, rax
0x18001e681  mov     [rbp+arg_0], rax
0x18001e685  jmp     short loc_18001E63C
0x18001e687  mov     r9, [rbp+arg_18]; void *
0x18001e68b  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001e690  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001e695  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001e69a  mov     [rbp+arg_0], rax
0x18001e69e  mov     rdi, rax
0x18001e6a1  test    rax, rax
0x18001e6a4  jnz     short loc_18001E6AD
0x18001e6a6  mov     al, 1
0x18001e6a8  jmp     loc_18001E79E
0x18001e6ad  mov     sil, 1
0x18001e6b0  jmp     short loc_18001E6B6
0x18001e6b2  mov     [rbp+arg_0], rdi
0x18001e6b6  xor     r8d, r8d
0x18001e6b9  test    sil, sil
0x18001e6bc  jnz     short loc_18001E6EC
0x18001e6be  jmp     short loc_18001E6C8
0x18001e6c0  mov     rdi, [rbp+arg_0]
0x18001e6c4  mov     [rbx+20h], rdi
0x18001e6c8  lea     rcx, [rbp+var_40]; this
0x18001e6cc  mov     [rbp+var_3C], 1
0x18001e6d3  mov     [rbp+var_38], r14w
0x18001e6d8  mov     qword ptr [rbp+var_30], 0
0x18001e6e0  mov     qword ptr [rbp+var_30+8], r15
0x18001e6e4  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001e6e9  mov     r8, rax
0x18001e6ec  movzx   ecx, word ptr [rbx+6]
0x18001e6f0  mov     rax, [rbp+arg_18]
0x18001e6f4  mov     [rbp+var_20], cx
0x18001e6f8  mov     cl, [rbx+8]
0x18001e6fb  mov     [rbp+var_1E], cl
0x18001e6fe  lea     rcx, [rbp+var_20]; this
0x18001e702  mov     [rbp+var_1C], r12d
0x18001e706  mov     [rbp+var_18], r13w
0x18001e70b  mov     [rbp+var_10], 0
0x18001e713  mov     [rbp+var_8], rax
0x18001e717  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001e71c  mov     rdx, [rbx+28h]
0x18001e720  mov     r9, [rbx+20h]
0x18001e724  mov     rcx, rdx
0x18001e727  sub     rcx, r9
0x18001e72a  lea     r14, [rax+r8]
0x18001e72e  cmp     r9, rdx
0x18001e731  sbb     rax, rax
0x18001e734  and     rax, rcx
0x18001e737  cmp     rax, r14
0x18001e73a  jb      short loc_18001E79C
0x18001e73c  sub     rdx, r14
0x18001e73f  lea     rcx, [r14+rdi]; Destination
0x18001e743  sub     rdx, rdi; DestinationSize
0x18001e746  sub     r9, rdi; SourceSize
0x18001e749  mov     r8, rdi; Source
0x18001e74c  call    cs:__imp_memmove_s
0x18001e752  add     [rbx+20h], r14
0x18001e756  test    sil, sil
0x18001e759  jnz     short loc_18001E76E
0x18001e75b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001e75f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001e763  lea     rcx, [rbp+var_40]; this
0x18001e767  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001e76c  jmp     short loc_18001E782
0x18001e76e  cmp     [rbp+var_3E], 0
0x18001e772  jz      short loc_18001E782
0x18001e774  mov     edx, [rbp+var_3C]
0x18001e777  lea     rcx, [rbp+var_40]; this
0x18001e77b  inc     edx; unsigned int
0x18001e77d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001e782  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001e786  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001e78a  lea     rcx, [rbp+var_20]; this
0x18001e78e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001e793  mov     byte ptr [rbx+38h], 1
0x18001e797  jmp     loc_18001E6A6
0x18001e79c  xor     al, al
0x18001e79e  mov     rbx, [rsp+70h+arg_8]
0x18001e7a6  add     rsp, 70h
0x18001e7aa  pop     r15
0x18001e7ac  pop     r14
0x18001e7ae  pop     r13
0x18001e7b0  pop     r12
0x18001e7b2  pop     rdi
0x18001e7b3  pop     rsi
0x18001e7b4  pop     rbp
0x18001e7b5  retn
```
