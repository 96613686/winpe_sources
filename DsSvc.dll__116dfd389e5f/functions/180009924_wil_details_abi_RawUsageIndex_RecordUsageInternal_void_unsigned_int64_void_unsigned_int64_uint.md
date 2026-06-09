# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009924`
- end: `0x180009afe`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009830`

## callees

- `0x180008324`
- `0x180008720`
- `0x180008a9c`
- `0x1800093ac`
- `0x180009924`
- `0x18000a040`
- `0x18000a47c`
- `0x18000a780`

## import_xrefs

- `msvcrt!memmove_s` at `0x180009a94`
- `msvcrt!memmove_s` at `0x180009a94`

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
0x180009924  mov     [rsp-38h+arg_8], rbx
0x180009929  mov     [rsp-38h+arg_18], r9
0x18000992e  push    rbp
0x18000992f  push    rsi
0x180009930  push    rdi
0x180009931  push    r12
0x180009933  push    r13
0x180009935  push    r14
0x180009937  push    r15
0x180009939  mov     rbp, rsp
0x18000993c  sub     rsp, 70h
0x180009940  mov     rdi, [rcx+18h]
0x180009944  mov     r14, r8
0x180009947  mov     r15, rdx
0x18000994a  mov     rbx, rcx
0x18000994d  test    rdi, rdi
0x180009950  jz      loc_180009AE4
0x180009956  movzx   eax, word ptr [rcx+2]
0x18000995a  add     rdi, 0Ah
0x18000995e  mov     [rbp+var_40], ax
0x180009962  xorps   xmm0, xmm0
0x180009965  mov     al, [rcx+4]
0x180009968  mov     [rbp+var_3E], al
0x18000996b  xor     eax, eax
0x18000996d  mov     [rbp+var_38], ax
0x180009971  xor     sil, sil
0x180009974  mov     [rbp+arg_0], rdi
0x180009978  mov     [rbp+var_3C], 0
0x18000997f  movdqu  [rbp+var_30], xmm0
0x180009984  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009988  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000998c  lea     rcx, [rbp+var_40]; this
0x180009990  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009995  mov     r12d, [rbp+arg_28]
0x180009999  mov     r13, [rbp+arg_20]
0x18000999d  test    al, al
0x18000999f  jz      short loc_180009A08
0x1800099a1  mov     r8, r14; unsigned __int64
0x1800099a4  lea     rcx, [rbp+var_40]; this
0x1800099a8  mov     rdx, r15; void *
0x1800099ab  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800099b0  test    eax, eax
0x1800099b2  js      short loc_1800099FA
0x1800099b4  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800099b8  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800099bc  mov     rcx, rbx; this
0x1800099bf  jz      short loc_1800099CF
0x1800099c1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800099c6  mov     rdi, rax
0x1800099c9  mov     [rbp+arg_0], rax
0x1800099cd  jmp     short loc_180009984
0x1800099cf  mov     r9, [rbp+arg_18]; void *
0x1800099d3  mov     [rsp+70h+var_48], r12d; unsigned int
0x1800099d8  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1800099dd  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800099e2  mov     [rbp+arg_0], rax
0x1800099e6  mov     rdi, rax
0x1800099e9  test    rax, rax
0x1800099ec  jnz     short loc_1800099F5
0x1800099ee  mov     al, 1
0x1800099f0  jmp     loc_180009AE6
0x1800099f5  mov     sil, 1
0x1800099f8  jmp     short loc_1800099FE
0x1800099fa  mov     [rbp+arg_0], rdi
0x1800099fe  xor     r8d, r8d
0x180009a01  test    sil, sil
0x180009a04  jnz     short loc_180009A34
0x180009a06  jmp     short loc_180009A10
0x180009a08  mov     rdi, [rbp+arg_0]
0x180009a0c  mov     [rbx+20h], rdi
0x180009a10  lea     rcx, [rbp+var_40]; this
0x180009a14  mov     [rbp+var_3C], 1
0x180009a1b  mov     [rbp+var_38], r14w
0x180009a20  mov     qword ptr [rbp+var_30], 0
0x180009a28  mov     qword ptr [rbp+var_30+8], r15
0x180009a2c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180009a31  mov     r8, rax
0x180009a34  movzx   ecx, word ptr [rbx+6]
0x180009a38  mov     rax, [rbp+arg_18]
0x180009a3c  mov     [rbp+var_20], cx
0x180009a40  mov     cl, [rbx+8]
0x180009a43  mov     [rbp+var_1E], cl
0x180009a46  lea     rcx, [rbp+var_20]; this
0x180009a4a  mov     [rbp+var_1C], r12d
0x180009a4e  mov     [rbp+var_18], r13w
0x180009a53  mov     [rbp+var_10], 0
0x180009a5b  mov     [rbp+var_8], rax
0x180009a5f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180009a64  mov     rdx, [rbx+28h]
0x180009a68  mov     r9, [rbx+20h]
0x180009a6c  mov     rcx, rdx
0x180009a6f  sub     rcx, r9
0x180009a72  lea     r14, [rax+r8]
0x180009a76  cmp     r9, rdx
0x180009a79  sbb     rax, rax
0x180009a7c  and     rax, rcx
0x180009a7f  cmp     rax, r14
0x180009a82  jb      short loc_180009AE4
0x180009a84  sub     rdx, r14
0x180009a87  lea     rcx, [r14+rdi]; Destination
0x180009a8b  sub     rdx, rdi; DestinationSize
0x180009a8e  sub     r9, rdi; SourceSize
0x180009a91  mov     r8, rdi; Source
0x180009a94  call    cs:__imp_memmove_s
0x180009a9a  add     [rbx+20h], r14
0x180009a9e  test    sil, sil
0x180009aa1  jnz     short loc_180009AB6
0x180009aa3  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009aa7  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180009aab  lea     rcx, [rbp+var_40]; this
0x180009aaf  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009ab4  jmp     short loc_180009ACA
0x180009ab6  cmp     [rbp+var_3E], 0
0x180009aba  jz      short loc_180009ACA
0x180009abc  mov     edx, [rbp+var_3C]
0x180009abf  lea     rcx, [rbp+var_40]; this
0x180009ac3  inc     edx; unsigned int
0x180009ac5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180009aca  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009ace  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180009ad2  lea     rcx, [rbp+var_20]; this
0x180009ad6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009adb  mov     byte ptr [rbx+38h], 1
0x180009adf  jmp     loc_1800099EE
0x180009ae4  xor     al, al
0x180009ae6  mov     rbx, [rsp+70h+arg_8]
0x180009aee  add     rsp, 70h
0x180009af2  pop     r15
0x180009af4  pop     r14
0x180009af6  pop     r13
0x180009af8  pop     r12
0x180009afa  pop     rdi
0x180009afb  pop     rsi
0x180009afc  pop     rbp
0x180009afd  retn
```
