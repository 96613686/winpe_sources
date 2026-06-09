# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180067d84`
- end: `0x180067f68`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180067c8c`

## callees

- `0x180066204`
- `0x1800667ac`
- `0x180066b3c`
- `0x1800677a8`
- `0x180067d84`
- `0x18006854c`
- `0x180068b84`
- `0x180069020`

## import_xrefs

- `msvcrt!memmove_s` at `0x180067ec6`
- `msvcrt!memmove_s` at `0x180067ec6`

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
0x180067d84  push    rbp
0x180067d86  push    rbx
0x180067d87  push    rsi
0x180067d88  push    rdi
0x180067d89  push    r12
0x180067d8b  push    r13
0x180067d8d  push    r14
0x180067d8f  push    r15
0x180067d91  mov     rbp, rsp
0x180067d94  sub     rsp, 78h
0x180067d98  mov     rdi, [rcx+18h]
0x180067d9c  mov     r13, r9
0x180067d9f  mov     r15, r8
0x180067da2  mov     r12, rdx
0x180067da5  mov     rbx, rcx
0x180067da8  test    rdi, rdi
0x180067dab  jz      loc_180067F55
0x180067db1  movzx   eax, word ptr [rcx+2]
0x180067db5  add     rdi, 0Ah
0x180067db9  mov     r8, [rcx+20h]
0x180067dbd  xorps   xmm0, xmm0
0x180067dc0  mov     [rbp+var_48], ax
0x180067dc4  mov     al, [rcx+4]
0x180067dc7  mov     [rbp+var_46], al
0x180067dca  xor     eax, eax
0x180067dcc  mov     [rbp+var_40], ax
0x180067dd0  xor     r14b, r14b
0x180067dd3  mov     [rbp+Source], rdi
0x180067dd7  mov     [rbp+var_44], 0
0x180067dde  movdqu  [rbp+var_38], xmm0
0x180067de3  jmp     short loc_180067E1D
0x180067de5  mov     r8, r15; unsigned __int64
0x180067de8  lea     rcx, [rbp+var_48]; this
0x180067dec  mov     rdx, r12; void *
0x180067def  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180067df4  test    eax, eax
0x180067df6  js      loc_180067F18
0x180067dfc  mov     r8, [rbp+Source]; unsigned __int8 *
0x180067e00  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180067e04  jz      loc_180067EE8
0x180067e0a  mov     rcx, rbx; this
0x180067e0d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180067e12  mov     r8, [rbx+20h]; unsigned __int8 *
0x180067e16  mov     rdi, rax
0x180067e19  mov     [rbp+Source], rax
0x180067e1d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180067e21  lea     rcx, [rbp+var_48]; this
0x180067e25  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180067e2a  mov     sil, al
0x180067e2d  test    al, al
0x180067e2f  jnz     short loc_180067DE5
0x180067e31  mov     rdi, [rbp+Source]
0x180067e35  mov     [rbx+20h], rdi
0x180067e39  xor     r8d, r8d
0x180067e3c  test    r14b, r14b
0x180067e3f  jnz     short loc_180067E61
0x180067e41  lea     rcx, [rbp+var_48]; this
0x180067e45  mov     [rbp+var_44], 1
0x180067e4c  mov     [rbp+var_40], r15w
0x180067e51  mov     qword ptr [rbp+var_38], r8
0x180067e55  mov     qword ptr [rbp+var_38+8], r12
0x180067e59  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180067e5e  mov     r8, rax
0x180067e61  movzx   ecx, word ptr [rbx+6]
0x180067e65  mov     eax, [rbp+arg_28]
0x180067e68  mov     [rbp+var_28], cx
0x180067e6c  mov     cl, [rbx+8]
0x180067e6f  mov     [rbp+var_24], eax
0x180067e72  mov     rax, [rbp+arg_20]
0x180067e76  mov     [rbp+var_26], cl
0x180067e79  lea     rcx, [rbp+var_28]; this
0x180067e7d  mov     [rbp+var_20], ax
0x180067e81  mov     [rbp+var_18], 0
0x180067e89  mov     [rbp+var_10], r13
0x180067e8d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180067e92  mov     rdx, [rbx+28h]
0x180067e96  mov     r9, [rbx+20h]
0x180067e9a  mov     rcx, rdx
0x180067e9d  sub     rcx, r9
0x180067ea0  lea     rsi, [rax+r8]
0x180067ea4  cmp     r9, rdx
0x180067ea7  sbb     rax, rax
0x180067eaa  and     rax, rcx
0x180067ead  cmp     rax, rsi
0x180067eb0  jb      loc_180067F55
0x180067eb6  sub     rdx, rsi
0x180067eb9  lea     rcx, [rsi+rdi]; Destination
0x180067ebd  sub     rdx, rdi; DestinationSize
0x180067ec0  sub     r9, rdi; SourceSize
0x180067ec3  mov     r8, rdi; Source
0x180067ec6  call    cs:__imp_memmove_s
0x180067ecc  add     [rbx+20h], rsi
0x180067ed0  test    r14b, r14b
0x180067ed3  jnz     short loc_180067F2A
0x180067ed5  mov     r8, [rbx+20h]; unsigned __int8 *
0x180067ed9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180067edd  lea     rcx, [rbp+var_48]; this
0x180067ee1  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180067ee6  jmp     short loc_180067F3E
0x180067ee8  mov     ecx, [rbp+arg_28]
0x180067eeb  mov     r9, r13; void *
0x180067eee  mov     [rsp+78h+var_50], ecx; unsigned int
0x180067ef2  mov     rcx, [rbp+arg_20]
0x180067ef6  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180067efb  mov     rcx, rbx; this
0x180067efe  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180067f03  mov     [rbp+Source], rax
0x180067f07  mov     rdi, rax
0x180067f0a  test    rax, rax
0x180067f0d  jnz     short loc_180067F13
0x180067f0f  mov     al, 1
0x180067f11  jmp     short loc_180067F57
0x180067f13  mov     r14b, 1
0x180067f16  jmp     short loc_180067F1C
0x180067f18  mov     [rbp+Source], rdi
0x180067f1c  test    sil, sil
0x180067f1f  jnz     loc_180067E39
0x180067f25  jmp     loc_180067E35
0x180067f2a  cmp     [rbp+var_46], 0
0x180067f2e  jz      short loc_180067F3E
0x180067f30  mov     edx, [rbp+var_44]
0x180067f33  lea     rcx, [rbp+var_48]; this
0x180067f37  inc     edx; unsigned int
0x180067f39  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180067f3e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180067f42  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180067f46  lea     rcx, [rbp+var_28]; this
0x180067f4a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180067f4f  mov     byte ptr [rbx+38h], 1
0x180067f53  jmp     short loc_180067F0F
0x180067f55  xor     al, al
0x180067f57  add     rsp, 78h
0x180067f5b  pop     r15
0x180067f5d  pop     r14
0x180067f5f  pop     r13
0x180067f61  pop     r12
0x180067f63  pop     rdi
0x180067f64  pop     rsi
0x180067f65  pop     rbx
0x180067f66  pop     rbp
0x180067f67  retn
```
