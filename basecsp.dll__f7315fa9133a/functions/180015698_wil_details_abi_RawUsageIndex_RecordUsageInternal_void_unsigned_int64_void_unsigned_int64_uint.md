# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180015698`
- end: `0x180015872`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800155a4`

## callees

- `0x18000cd34`
- `0x18000dc70`
- `0x18000fcc8`
- `0x180014f38`
- `0x180015698`
- `0x180016cd8`
- `0x1800177bc`
- `0x180017d1c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180015808`
- `msvcrt!memmove_s` at `0x180015808`

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
0x180015698  mov     [rsp-38h+arg_8], rbx
0x18001569d  mov     [rsp-38h+arg_18], r9
0x1800156a2  push    rbp
0x1800156a3  push    rsi
0x1800156a4  push    rdi
0x1800156a5  push    r12
0x1800156a7  push    r13
0x1800156a9  push    r14
0x1800156ab  push    r15
0x1800156ad  mov     rbp, rsp
0x1800156b0  sub     rsp, 70h
0x1800156b4  mov     rdi, [rcx+18h]
0x1800156b8  mov     r14, r8
0x1800156bb  mov     r15, rdx
0x1800156be  mov     rbx, rcx
0x1800156c1  test    rdi, rdi
0x1800156c4  jz      loc_180015858
0x1800156ca  movzx   eax, word ptr [rcx+2]
0x1800156ce  add     rdi, 0Ah
0x1800156d2  mov     [rbp+var_40], ax
0x1800156d6  xorps   xmm0, xmm0
0x1800156d9  mov     al, [rcx+4]
0x1800156dc  mov     [rbp+var_3E], al
0x1800156df  xor     eax, eax
0x1800156e1  mov     [rbp+var_38], ax
0x1800156e5  xor     sil, sil
0x1800156e8  mov     [rbp+arg_0], rdi
0x1800156ec  mov     [rbp+var_3C], 0
0x1800156f3  movdqu  [rbp+var_30], xmm0
0x1800156f8  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800156fc  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180015700  lea     rcx, [rbp+var_40]; this
0x180015704  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015709  mov     r12d, [rbp+arg_28]
0x18001570d  mov     r13, [rbp+arg_20]
0x180015711  test    al, al
0x180015713  jz      short loc_18001577C
0x180015715  mov     r8, r14; unsigned __int64
0x180015718  lea     rcx, [rbp+var_40]; this
0x18001571c  mov     rdx, r15; void *
0x18001571f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180015724  test    eax, eax
0x180015726  js      short loc_18001576E
0x180015728  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001572c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180015730  mov     rcx, rbx; this
0x180015733  jz      short loc_180015743
0x180015735  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001573a  mov     rdi, rax
0x18001573d  mov     [rbp+arg_0], rax
0x180015741  jmp     short loc_1800156F8
0x180015743  mov     r9, [rbp+arg_18]; void *
0x180015747  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001574c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180015751  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180015756  mov     [rbp+arg_0], rax
0x18001575a  mov     rdi, rax
0x18001575d  test    rax, rax
0x180015760  jnz     short loc_180015769
0x180015762  mov     al, 1
0x180015764  jmp     loc_18001585A
0x180015769  mov     sil, 1
0x18001576c  jmp     short loc_180015772
0x18001576e  mov     [rbp+arg_0], rdi
0x180015772  xor     r8d, r8d
0x180015775  test    sil, sil
0x180015778  jnz     short loc_1800157A8
0x18001577a  jmp     short loc_180015784
0x18001577c  mov     rdi, [rbp+arg_0]
0x180015780  mov     [rbx+20h], rdi
0x180015784  lea     rcx, [rbp+var_40]; this
0x180015788  mov     [rbp+var_3C], 1
0x18001578f  mov     [rbp+var_38], r14w
0x180015794  mov     qword ptr [rbp+var_30], 0
0x18001579c  mov     qword ptr [rbp+var_30+8], r15
0x1800157a0  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800157a5  mov     r8, rax
0x1800157a8  movzx   ecx, word ptr [rbx+6]
0x1800157ac  mov     rax, [rbp+arg_18]
0x1800157b0  mov     [rbp+var_20], cx
0x1800157b4  mov     cl, [rbx+8]
0x1800157b7  mov     [rbp+var_1E], cl
0x1800157ba  lea     rcx, [rbp+var_20]; this
0x1800157be  mov     [rbp+var_1C], r12d
0x1800157c2  mov     [rbp+var_18], r13w
0x1800157c7  mov     [rbp+var_10], 0
0x1800157cf  mov     [rbp+var_8], rax
0x1800157d3  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800157d8  mov     rdx, [rbx+28h]
0x1800157dc  mov     r9, [rbx+20h]
0x1800157e0  mov     rcx, rdx
0x1800157e3  sub     rcx, r9
0x1800157e6  lea     r14, [rax+r8]
0x1800157ea  cmp     r9, rdx
0x1800157ed  sbb     rax, rax
0x1800157f0  and     rax, rcx
0x1800157f3  cmp     rax, r14
0x1800157f6  jb      short loc_180015858
0x1800157f8  sub     rdx, r14
0x1800157fb  lea     rcx, [r14+rdi]; Destination
0x1800157ff  sub     rdx, rdi; DestinationSize
0x180015802  sub     r9, rdi; SourceSize
0x180015805  mov     r8, rdi; Source
0x180015808  call    cs:__imp_memmove_s
0x18001580e  add     [rbx+20h], r14
0x180015812  test    sil, sil
0x180015815  jnz     short loc_18001582A
0x180015817  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001581b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001581f  lea     rcx, [rbp+var_40]; this
0x180015823  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180015828  jmp     short loc_18001583E
0x18001582a  cmp     [rbp+var_3E], 0
0x18001582e  jz      short loc_18001583E
0x180015830  mov     edx, [rbp+var_3C]
0x180015833  lea     rcx, [rbp+var_40]; this
0x180015837  inc     edx; unsigned int
0x180015839  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001583e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180015842  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180015846  lea     rcx, [rbp+var_20]; this
0x18001584a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001584f  mov     byte ptr [rbx+38h], 1
0x180015853  jmp     loc_180015762
0x180015858  xor     al, al
0x18001585a  mov     rbx, [rsp+70h+arg_8]
0x180015862  add     rsp, 70h
0x180015866  pop     r15
0x180015868  pop     r14
0x18001586a  pop     r13
0x18001586c  pop     r12
0x18001586e  pop     rdi
0x18001586f  pop     rsi
0x180015870  pop     rbp
0x180015871  retn
```
