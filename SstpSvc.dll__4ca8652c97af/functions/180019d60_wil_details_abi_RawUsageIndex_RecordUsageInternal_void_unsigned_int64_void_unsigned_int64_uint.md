# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180019d60`
- end: `0x180019f44`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180019c6c`

## callees

- `0x180017b0c`
- `0x180017e44`
- `0x1800187d4`
- `0x1800197bc`
- `0x180019d60`
- `0x18001a70c`
- `0x18001ae5c`
- `0x18001b10c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180019ea2`
- `msvcrt!memmove_s` at `0x180019ea2`

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
  const void *v24; // [rsp+30h] [rbp-48h] BYREF
  __int16 v25; // [rsp+38h] [rbp-40h]
  __int128 v26; // [rsp+40h] [rbp-38h]
  __int16 v27; // [rsp+50h] [rbp-28h] BYREF
  char v28; // [rsp+52h] [rbp-26h]
  unsigned int v29; // [rsp+54h] [rbp-24h]
  __int16 v30; // [rsp+58h] [rbp-20h]
  __int64 v31; // [rsp+60h] [rbp-18h]
  void *v32; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    LOWORD(v24) = *((_WORD *)this + 1);
    BYTE2(v24) = *((_BYTE *)this + 4);
    v25 = 0;
    v13 = 0;
    Source = v11;
    HIDWORD(v24) = 0;
    v26 = 0;
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
      v14 = wil::details_abi::UsageIndexProperty::Compare(&v24, a2, a3);
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
      HIDWORD(v24) = 1;
      v25 = a3;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v27 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v29 = a6;
    v28 = v17;
    v30 = a5;
    v31 = 0;
    v32 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( BYTE2(v24) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v24,
            HIDWORD(v24) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
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
0x180019d60  push    rbp
0x180019d62  push    rbx
0x180019d63  push    rsi
0x180019d64  push    rdi
0x180019d65  push    r12
0x180019d67  push    r13
0x180019d69  push    r14
0x180019d6b  push    r15
0x180019d6d  mov     rbp, rsp
0x180019d70  sub     rsp, 78h
0x180019d74  mov     rdi, [rcx+18h]
0x180019d78  mov     r13, r9
0x180019d7b  mov     r15, r8
0x180019d7e  mov     r12, rdx
0x180019d81  mov     rbx, rcx
0x180019d84  test    rdi, rdi
0x180019d87  jz      loc_180019F31
0x180019d8d  movzx   eax, word ptr [rcx+2]
0x180019d91  add     rdi, 0Ah
0x180019d95  mov     r8, [rcx+20h]
0x180019d99  xorps   xmm0, xmm0
0x180019d9c  mov     [rbp+var_48], ax
0x180019da0  mov     al, [rcx+4]
0x180019da3  mov     [rbp+var_46], al
0x180019da6  xor     eax, eax
0x180019da8  mov     [rbp+var_40], ax
0x180019dac  xor     r14b, r14b
0x180019daf  mov     [rbp+Source], rdi
0x180019db3  mov     [rbp+var_44], 0
0x180019dba  movdqu  [rbp+var_38], xmm0
0x180019dbf  jmp     short loc_180019DF9
0x180019dc1  mov     r8, r15; unsigned __int64
0x180019dc4  lea     rcx, [rbp+var_48]; this
0x180019dc8  mov     rdx, r12; void *
0x180019dcb  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180019dd0  test    eax, eax
0x180019dd2  js      loc_180019EF4
0x180019dd8  mov     r8, [rbp+Source]; unsigned __int8 *
0x180019ddc  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180019de0  jz      loc_180019EC4
0x180019de6  mov     rcx, rbx; this
0x180019de9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180019dee  mov     r8, [rbx+20h]; unsigned __int8 *
0x180019df2  mov     rdi, rax
0x180019df5  mov     [rbp+Source], rax
0x180019df9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180019dfd  lea     rcx, [rbp+var_48]; this
0x180019e01  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180019e06  mov     sil, al
0x180019e09  test    al, al
0x180019e0b  jnz     short loc_180019DC1
0x180019e0d  mov     rdi, [rbp+Source]
0x180019e11  mov     [rbx+20h], rdi
0x180019e15  xor     r8d, r8d
0x180019e18  test    r14b, r14b
0x180019e1b  jnz     short loc_180019E3D
0x180019e1d  lea     rcx, [rbp+var_48]; this
0x180019e21  mov     [rbp+var_44], 1
0x180019e28  mov     [rbp+var_40], r15w
0x180019e2d  mov     qword ptr [rbp+var_38], r8
0x180019e31  mov     qword ptr [rbp+var_38+8], r12
0x180019e35  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180019e3a  mov     r8, rax
0x180019e3d  movzx   ecx, word ptr [rbx+6]
0x180019e41  mov     eax, [rbp+arg_28]
0x180019e44  mov     [rbp+var_28], cx
0x180019e48  mov     cl, [rbx+8]
0x180019e4b  mov     [rbp+var_24], eax
0x180019e4e  mov     rax, [rbp+arg_20]
0x180019e52  mov     [rbp+var_26], cl
0x180019e55  lea     rcx, [rbp+var_28]; this
0x180019e59  mov     [rbp+var_20], ax
0x180019e5d  mov     [rbp+var_18], 0
0x180019e65  mov     [rbp+var_10], r13
0x180019e69  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180019e6e  mov     rdx, [rbx+28h]
0x180019e72  mov     r9, [rbx+20h]
0x180019e76  mov     rcx, rdx
0x180019e79  sub     rcx, r9
0x180019e7c  lea     rsi, [rax+r8]
0x180019e80  cmp     r9, rdx
0x180019e83  sbb     rax, rax
0x180019e86  and     rax, rcx
0x180019e89  cmp     rax, rsi
0x180019e8c  jb      loc_180019F31
0x180019e92  sub     rdx, rsi
0x180019e95  lea     rcx, [rsi+rdi]; Destination
0x180019e99  sub     rdx, rdi; DestinationSize
0x180019e9c  sub     r9, rdi; SourceSize
0x180019e9f  mov     r8, rdi; Source
0x180019ea2  call    cs:__imp_memmove_s
0x180019ea8  add     [rbx+20h], rsi
0x180019eac  test    r14b, r14b
0x180019eaf  jnz     short loc_180019F06
0x180019eb1  mov     r8, [rbx+20h]; unsigned __int8 *
0x180019eb5  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180019eb9  lea     rcx, [rbp+var_48]; this
0x180019ebd  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180019ec2  jmp     short loc_180019F1A
0x180019ec4  mov     ecx, [rbp+arg_28]
0x180019ec7  mov     r9, r13; void *
0x180019eca  mov     [rsp+78h+var_50], ecx; unsigned int
0x180019ece  mov     rcx, [rbp+arg_20]
0x180019ed2  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180019ed7  mov     rcx, rbx; this
0x180019eda  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180019edf  mov     [rbp+Source], rax
0x180019ee3  mov     rdi, rax
0x180019ee6  test    rax, rax
0x180019ee9  jnz     short loc_180019EEF
0x180019eeb  mov     al, 1
0x180019eed  jmp     short loc_180019F33
0x180019eef  mov     r14b, 1
0x180019ef2  jmp     short loc_180019EF8
0x180019ef4  mov     [rbp+Source], rdi
0x180019ef8  test    sil, sil
0x180019efb  jnz     loc_180019E15
0x180019f01  jmp     loc_180019E11
0x180019f06  cmp     [rbp+var_46], 0
0x180019f0a  jz      short loc_180019F1A
0x180019f0c  mov     edx, [rbp+var_44]
0x180019f0f  lea     rcx, [rbp+var_48]; this
0x180019f13  inc     edx; unsigned int
0x180019f15  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180019f1a  mov     r8, [rbx+20h]; unsigned __int8 *
0x180019f1e  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180019f22  lea     rcx, [rbp+var_28]; this
0x180019f26  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180019f2b  mov     byte ptr [rbx+38h], 1
0x180019f2f  jmp     short loc_180019EEB
0x180019f31  xor     al, al
0x180019f33  add     rsp, 78h
0x180019f37  pop     r15
0x180019f39  pop     r14
0x180019f3b  pop     r13
0x180019f3d  pop     r12
0x180019f3f  pop     rdi
0x180019f40  pop     rsi
0x180019f41  pop     rbx
0x180019f42  pop     rbp
0x180019f43  retn
```
