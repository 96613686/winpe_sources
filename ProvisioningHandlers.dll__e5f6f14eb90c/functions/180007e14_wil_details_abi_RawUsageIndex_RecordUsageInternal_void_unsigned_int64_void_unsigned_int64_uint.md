# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007e14`
- end: `0x180007fff`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `491`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007d20`

## callees

- `0x1800050ac`
- `0x180005940`
- `0x1800062a8`
- `0x180007760`
- `0x180007e14`
- `0x180008e20`
- `0x180009684`
- `0x180009aa0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007f56`
- `msvcrt!memmove_s` at `0x180007f56`

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
0x180007e14  push    rbp
0x180007e16  push    rbx
0x180007e17  push    rsi
0x180007e18  push    rdi
0x180007e19  push    r12
0x180007e1b  push    r13
0x180007e1d  push    r14
0x180007e1f  push    r15
0x180007e21  mov     rbp, rsp
0x180007e24  sub     rsp, 78h
0x180007e28  mov     rdi, [rcx+18h]
0x180007e2c  mov     r13, r9
0x180007e2f  mov     r15, r8
0x180007e32  mov     r12, rdx
0x180007e35  mov     rbx, rcx
0x180007e38  test    rdi, rdi
0x180007e3b  jz      loc_180007FEB
0x180007e41  movzx   eax, word ptr [rcx+2]
0x180007e45  add     rdi, 0Ah
0x180007e49  mov     r8, [rcx+20h]
0x180007e4d  xorps   xmm0, xmm0
0x180007e50  mov     [rbp+var_48], ax
0x180007e54  mov     al, [rcx+4]
0x180007e57  mov     [rbp+var_46], al
0x180007e5a  xor     eax, eax
0x180007e5c  mov     [rbp+var_40], ax
0x180007e60  xor     r14b, r14b
0x180007e63  mov     [rbp+Source], rdi
0x180007e67  mov     [rbp+var_44], 0
0x180007e6e  movdqu  [rbp+var_38], xmm0
0x180007e73  jmp     short loc_180007EAD
0x180007e75  mov     r8, r15; unsigned __int64
0x180007e78  lea     rcx, [rbp+var_48]; this
0x180007e7c  mov     rdx, r12; void *
0x180007e7f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180007e84  test    eax, eax
0x180007e86  js      loc_180007FAE
0x180007e8c  mov     r8, [rbp+Source]; unsigned __int8 *
0x180007e90  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180007e94  jz      loc_180007F7E
0x180007e9a  mov     rcx, rbx; this
0x180007e9d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180007ea2  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007ea6  mov     rdi, rax
0x180007ea9  mov     [rbp+Source], rax
0x180007ead  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180007eb1  lea     rcx, [rbp+var_48]; this
0x180007eb5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007eba  mov     sil, al
0x180007ebd  test    al, al
0x180007ebf  jnz     short loc_180007E75
0x180007ec1  mov     rdi, [rbp+Source]
0x180007ec5  mov     [rbx+20h], rdi
0x180007ec9  xor     r8d, r8d
0x180007ecc  test    r14b, r14b
0x180007ecf  jnz     short loc_180007EF1
0x180007ed1  lea     rcx, [rbp+var_48]; this
0x180007ed5  mov     [rbp+var_44], 1
0x180007edc  mov     [rbp+var_40], r15w
0x180007ee1  mov     qword ptr [rbp+var_38], r8
0x180007ee5  mov     qword ptr [rbp+var_38+8], r12
0x180007ee9  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180007eee  mov     r8, rax
0x180007ef1  movzx   ecx, word ptr [rbx+6]
0x180007ef5  mov     eax, [rbp+arg_28]
0x180007ef8  mov     [rbp+var_28], cx
0x180007efc  mov     cl, [rbx+8]
0x180007eff  mov     [rbp+var_24], eax
0x180007f02  mov     rax, [rbp+arg_20]
0x180007f06  mov     [rbp+var_26], cl
0x180007f09  lea     rcx, [rbp+var_28]; this
0x180007f0d  mov     [rbp+var_20], ax
0x180007f11  mov     [rbp+var_18], 0
0x180007f19  mov     [rbp+var_10], r13
0x180007f1d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180007f22  mov     rdx, [rbx+28h]
0x180007f26  mov     r9, [rbx+20h]
0x180007f2a  mov     rcx, rdx
0x180007f2d  sub     rcx, r9
0x180007f30  lea     rsi, [rax+r8]
0x180007f34  cmp     r9, rdx
0x180007f37  sbb     rax, rax
0x180007f3a  and     rax, rcx
0x180007f3d  cmp     rax, rsi
0x180007f40  jb      loc_180007FEB
0x180007f46  sub     rdx, rsi
0x180007f49  lea     rcx, [rsi+rdi]; Destination
0x180007f4d  sub     rdx, rdi; DestinationSize
0x180007f50  sub     r9, rdi; SourceSize
0x180007f53  mov     r8, rdi; Source
0x180007f56  call    cs:__imp_memmove_s
0x180007f5d  nop     dword ptr [rax+rax+00h]
0x180007f62  add     [rbx+20h], rsi
0x180007f66  test    r14b, r14b
0x180007f69  jnz     short loc_180007FC0
0x180007f6b  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007f6f  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180007f73  lea     rcx, [rbp+var_48]; this
0x180007f77  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007f7c  jmp     short loc_180007FD4
0x180007f7e  mov     ecx, [rbp+arg_28]
0x180007f81  mov     r9, r13; void *
0x180007f84  mov     [rsp+78h+var_50], ecx; unsigned int
0x180007f88  mov     rcx, [rbp+arg_20]
0x180007f8c  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180007f91  mov     rcx, rbx; this
0x180007f94  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180007f99  mov     [rbp+Source], rax
0x180007f9d  mov     rdi, rax
0x180007fa0  test    rax, rax
0x180007fa3  jnz     short loc_180007FA9
0x180007fa5  mov     al, 1
0x180007fa7  jmp     short loc_180007FED
0x180007fa9  mov     r14b, 1
0x180007fac  jmp     short loc_180007FB2
0x180007fae  mov     [rbp+Source], rdi
0x180007fb2  test    sil, sil
0x180007fb5  jnz     loc_180007EC9
0x180007fbb  jmp     loc_180007EC5
0x180007fc0  cmp     [rbp+var_46], 0
0x180007fc4  jz      short loc_180007FD4
0x180007fc6  mov     edx, [rbp+var_44]
0x180007fc9  lea     rcx, [rbp+var_48]; this
0x180007fcd  inc     edx; unsigned int
0x180007fcf  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180007fd4  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007fd8  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180007fdc  lea     rcx, [rbp+var_28]; this
0x180007fe0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007fe5  mov     byte ptr [rbx+38h], 1
0x180007fe9  jmp     short loc_180007FA5
0x180007feb  xor     al, al
0x180007fed  add     rsp, 78h
0x180007ff1  pop     r15
0x180007ff3  pop     r14
0x180007ff5  pop     r13
0x180007ff7  pop     r12
0x180007ff9  pop     rdi
0x180007ffa  pop     rsi
0x180007ffb  pop     rbx
0x180007ffc  pop     rbp
0x180007ffd  retn
```
