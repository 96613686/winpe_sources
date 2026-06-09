# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b978`
- end: `0x14000bb52`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000b888`

## callees

- `0x1400092a4`
- `0x1400095ac`
- `0x140009f44`
- `0x14000b4a0`
- `0x14000b978`
- `0x14000c584`
- `0x14000cf7c`
- `0x14000d22c`

## import_xrefs

- `ntdll!memmove_s` at `0x14000bae8`
- `ntdll!memmove_s` at `0x14000bae8`

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
0x14000b978  mov     [rsp-38h+arg_8], rbx
0x14000b97d  mov     [rsp-38h+arg_18], r9
0x14000b982  push    rbp
0x14000b983  push    rsi
0x14000b984  push    rdi
0x14000b985  push    r12
0x14000b987  push    r13
0x14000b989  push    r14
0x14000b98b  push    r15
0x14000b98d  mov     rbp, rsp
0x14000b990  sub     rsp, 70h
0x14000b994  mov     rdi, [rcx+18h]
0x14000b998  mov     r14, r8
0x14000b99b  mov     r15, rdx
0x14000b99e  mov     rbx, rcx
0x14000b9a1  test    rdi, rdi
0x14000b9a4  jz      loc_14000BB38
0x14000b9aa  movzx   eax, word ptr [rcx+2]
0x14000b9ae  add     rdi, 0Ah
0x14000b9b2  mov     [rbp+var_40], ax
0x14000b9b6  xorps   xmm0, xmm0
0x14000b9b9  mov     al, [rcx+4]
0x14000b9bc  mov     [rbp+var_3E], al
0x14000b9bf  xor     eax, eax
0x14000b9c1  mov     [rbp+var_38], ax
0x14000b9c5  xor     sil, sil
0x14000b9c8  mov     [rbp+arg_0], rdi
0x14000b9cc  mov     [rbp+var_3C], 0
0x14000b9d3  movdqu  [rbp+var_30], xmm0
0x14000b9d8  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000b9dc  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000b9e0  lea     rcx, [rbp+var_40]; this
0x14000b9e4  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b9e9  mov     r12d, [rbp+arg_28]
0x14000b9ed  mov     r13, [rbp+arg_20]
0x14000b9f1  test    al, al
0x14000b9f3  jz      short loc_14000BA5C
0x14000b9f5  mov     r8, r14; unsigned __int64
0x14000b9f8  lea     rcx, [rbp+var_40]; this
0x14000b9fc  mov     rdx, r15; void *
0x14000b9ff  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x14000ba04  test    eax, eax
0x14000ba06  js      short loc_14000BA4E
0x14000ba08  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x14000ba0c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x14000ba10  mov     rcx, rbx; this
0x14000ba13  jz      short loc_14000BA23
0x14000ba15  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x14000ba1a  mov     rdi, rax
0x14000ba1d  mov     [rbp+arg_0], rax
0x14000ba21  jmp     short loc_14000B9D8
0x14000ba23  mov     r9, [rbp+arg_18]; void *
0x14000ba27  mov     [rsp+70h+var_48], r12d; unsigned int
0x14000ba2c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x14000ba31  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14000ba36  mov     [rbp+arg_0], rax
0x14000ba3a  mov     rdi, rax
0x14000ba3d  test    rax, rax
0x14000ba40  jnz     short loc_14000BA49
0x14000ba42  mov     al, 1
0x14000ba44  jmp     loc_14000BB3A
0x14000ba49  mov     sil, 1
0x14000ba4c  jmp     short loc_14000BA52
0x14000ba4e  mov     [rbp+arg_0], rdi
0x14000ba52  xor     r8d, r8d
0x14000ba55  test    sil, sil
0x14000ba58  jnz     short loc_14000BA88
0x14000ba5a  jmp     short loc_14000BA64
0x14000ba5c  mov     rdi, [rbp+arg_0]
0x14000ba60  mov     [rbx+20h], rdi
0x14000ba64  lea     rcx, [rbp+var_40]; this
0x14000ba68  mov     [rbp+var_3C], 1
0x14000ba6f  mov     [rbp+var_38], r14w
0x14000ba74  mov     qword ptr [rbp+var_30], 0
0x14000ba7c  mov     qword ptr [rbp+var_30+8], r15
0x14000ba80  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000ba85  mov     r8, rax
0x14000ba88  movzx   ecx, word ptr [rbx+6]
0x14000ba8c  mov     rax, [rbp+arg_18]
0x14000ba90  mov     [rbp+var_20], cx
0x14000ba94  mov     cl, [rbx+8]
0x14000ba97  mov     [rbp+var_1E], cl
0x14000ba9a  lea     rcx, [rbp+var_20]; this
0x14000ba9e  mov     [rbp+var_1C], r12d
0x14000baa2  mov     [rbp+var_18], r13w
0x14000baa7  mov     [rbp+var_10], 0
0x14000baaf  mov     [rbp+var_8], rax
0x14000bab3  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000bab8  mov     rdx, [rbx+28h]
0x14000babc  mov     r9, [rbx+20h]
0x14000bac0  mov     rcx, rdx
0x14000bac3  sub     rcx, r9
0x14000bac6  lea     r14, [rax+r8]
0x14000baca  cmp     r9, rdx
0x14000bacd  sbb     rax, rax
0x14000bad0  and     rax, rcx
0x14000bad3  cmp     rax, r14
0x14000bad6  jb      short loc_14000BB38
0x14000bad8  sub     rdx, r14
0x14000badb  lea     rcx, [r14+rdi]; Destination
0x14000badf  sub     rdx, rdi; DestinationSize
0x14000bae2  sub     r9, rdi; SourceSize
0x14000bae5  mov     r8, rdi; Source
0x14000bae8  call    cs:__imp_memmove_s
0x14000baee  add     [rbx+20h], r14
0x14000baf2  test    sil, sil
0x14000baf5  jnz     short loc_14000BB0A
0x14000baf7  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000bafb  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000baff  lea     rcx, [rbp+var_40]; this
0x14000bb03  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000bb08  jmp     short loc_14000BB1E
0x14000bb0a  cmp     [rbp+var_3E], 0
0x14000bb0e  jz      short loc_14000BB1E
0x14000bb10  mov     edx, [rbp+var_3C]
0x14000bb13  lea     rcx, [rbp+var_40]; this
0x14000bb17  inc     edx; unsigned int
0x14000bb19  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x14000bb1e  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000bb22  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000bb26  lea     rcx, [rbp+var_20]; this
0x14000bb2a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000bb2f  mov     byte ptr [rbx+38h], 1
0x14000bb33  jmp     loc_14000BA42
0x14000bb38  xor     al, al
0x14000bb3a  mov     rbx, [rsp+70h+arg_8]
0x14000bb42  add     rsp, 70h
0x14000bb46  pop     r15
0x14000bb48  pop     r14
0x14000bb4a  pop     r13
0x14000bb4c  pop     r12
0x14000bb4e  pop     rdi
0x14000bb4f  pop     rsi
0x14000bb50  pop     rbp
0x14000bb51  retn
```
