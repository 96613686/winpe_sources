# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180010e44`
- end: `0x18001101e`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010d50`

## callees

- `0x18000f958`
- `0x18000fc28`
- `0x18000ff8c`
- `0x1800108d0`
- `0x180010e44`
- `0x1800116b8`
- `0x180011d40`
- `0x180012064`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180010fb4`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180010fb4`

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
0x180010e44  mov     [rsp-38h+arg_8], rbx
0x180010e49  mov     [rsp-38h+arg_18], r9
0x180010e4e  push    rbp
0x180010e4f  push    rsi
0x180010e50  push    rdi
0x180010e51  push    r12
0x180010e53  push    r13
0x180010e55  push    r14
0x180010e57  push    r15
0x180010e59  mov     rbp, rsp
0x180010e5c  sub     rsp, 70h
0x180010e60  mov     rdi, [rcx+18h]
0x180010e64  mov     r14, r8
0x180010e67  mov     r15, rdx
0x180010e6a  mov     rbx, rcx
0x180010e6d  test    rdi, rdi
0x180010e70  jz      loc_180011004
0x180010e76  movzx   eax, word ptr [rcx+2]
0x180010e7a  add     rdi, 0Ah
0x180010e7e  mov     [rbp+var_40], ax
0x180010e82  xorps   xmm0, xmm0
0x180010e85  mov     al, [rcx+4]
0x180010e88  mov     [rbp+var_3E], al
0x180010e8b  xor     eax, eax
0x180010e8d  mov     [rbp+var_38], ax
0x180010e91  xor     sil, sil
0x180010e94  mov     [rbp+arg_0], rdi
0x180010e98  mov     [rbp+var_3C], 0
0x180010e9f  movdqu  [rbp+var_30], xmm0
0x180010ea4  mov     r8, [rbx+20h]; unsigned __int8 *
0x180010ea8  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180010eac  lea     rcx, [rbp+var_40]; this
0x180010eb0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180010eb5  mov     r12d, [rbp+arg_28]
0x180010eb9  mov     r13, [rbp+arg_20]
0x180010ebd  test    al, al
0x180010ebf  jz      short loc_180010F28
0x180010ec1  mov     r8, r14; unsigned __int64
0x180010ec4  lea     rcx, [rbp+var_40]; this
0x180010ec8  mov     rdx, r15; void *
0x180010ecb  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180010ed0  test    eax, eax
0x180010ed2  js      short loc_180010F1A
0x180010ed4  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180010ed8  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180010edc  mov     rcx, rbx; this
0x180010edf  jz      short loc_180010EEF
0x180010ee1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180010ee6  mov     rdi, rax
0x180010ee9  mov     [rbp+arg_0], rax
0x180010eed  jmp     short loc_180010EA4
0x180010eef  mov     r9, [rbp+arg_18]; void *
0x180010ef3  mov     [rsp+70h+var_48], r12d; unsigned int
0x180010ef8  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180010efd  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180010f02  mov     [rbp+arg_0], rax
0x180010f06  mov     rdi, rax
0x180010f09  test    rax, rax
0x180010f0c  jnz     short loc_180010F15
0x180010f0e  mov     al, 1
0x180010f10  jmp     loc_180011006
0x180010f15  mov     sil, 1
0x180010f18  jmp     short loc_180010F1E
0x180010f1a  mov     [rbp+arg_0], rdi
0x180010f1e  xor     r8d, r8d
0x180010f21  test    sil, sil
0x180010f24  jnz     short loc_180010F54
0x180010f26  jmp     short loc_180010F30
0x180010f28  mov     rdi, [rbp+arg_0]
0x180010f2c  mov     [rbx+20h], rdi
0x180010f30  lea     rcx, [rbp+var_40]; this
0x180010f34  mov     [rbp+var_3C], 1
0x180010f3b  mov     [rbp+var_38], r14w
0x180010f40  mov     qword ptr [rbp+var_30], 0
0x180010f48  mov     qword ptr [rbp+var_30+8], r15
0x180010f4c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180010f51  mov     r8, rax
0x180010f54  movzx   ecx, word ptr [rbx+6]
0x180010f58  mov     rax, [rbp+arg_18]
0x180010f5c  mov     [rbp+var_20], cx
0x180010f60  mov     cl, [rbx+8]
0x180010f63  mov     [rbp+var_1E], cl
0x180010f66  lea     rcx, [rbp+var_20]; this
0x180010f6a  mov     [rbp+var_1C], r12d
0x180010f6e  mov     [rbp+var_18], r13w
0x180010f73  mov     [rbp+var_10], 0
0x180010f7b  mov     [rbp+var_8], rax
0x180010f7f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180010f84  mov     rdx, [rbx+28h]
0x180010f88  mov     r9, [rbx+20h]
0x180010f8c  mov     rcx, rdx
0x180010f8f  sub     rcx, r9
0x180010f92  lea     r14, [rax+r8]
0x180010f96  cmp     r9, rdx
0x180010f99  sbb     rax, rax
0x180010f9c  and     rax, rcx
0x180010f9f  cmp     rax, r14
0x180010fa2  jb      short loc_180011004
0x180010fa4  sub     rdx, r14
0x180010fa7  lea     rcx, [r14+rdi]; Destination
0x180010fab  sub     rdx, rdi; DestinationSize
0x180010fae  sub     r9, rdi; SourceSize
0x180010fb1  mov     r8, rdi; Source
0x180010fb4  call    cs:__imp_memmove_s
0x180010fba  add     [rbx+20h], r14
0x180010fbe  test    sil, sil
0x180010fc1  jnz     short loc_180010FD6
0x180010fc3  mov     r8, [rbx+20h]; unsigned __int8 *
0x180010fc7  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180010fcb  lea     rcx, [rbp+var_40]; this
0x180010fcf  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180010fd4  jmp     short loc_180010FEA
0x180010fd6  cmp     [rbp+var_3E], 0
0x180010fda  jz      short loc_180010FEA
0x180010fdc  mov     edx, [rbp+var_3C]
0x180010fdf  lea     rcx, [rbp+var_40]; this
0x180010fe3  inc     edx; unsigned int
0x180010fe5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180010fea  mov     r8, [rbx+20h]; unsigned __int8 *
0x180010fee  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180010ff2  lea     rcx, [rbp+var_20]; this
0x180010ff6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180010ffb  mov     byte ptr [rbx+38h], 1
0x180010fff  jmp     loc_180010F0E
0x180011004  xor     al, al
0x180011006  mov     rbx, [rsp+70h+arg_8]
0x18001100e  add     rsp, 70h
0x180011012  pop     r15
0x180011014  pop     r14
0x180011016  pop     r13
0x180011018  pop     r12
0x18001101a  pop     rdi
0x18001101b  pop     rsi
0x18001101c  pop     rbp
0x18001101d  retn
```
