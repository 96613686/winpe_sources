# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001d320`
- end: `0x18001d504`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d22c`

## callees

- `0x18001c4b0`
- `0x18001c668`
- `0x18001c864`
- `0x18001cdf0`
- `0x18001d320`
- `0x18001d8f8`
- `0x18001dce4`
- `0x18001de54`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d462`
- `msvcrt!memmove_s` at `0x18001d462`

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
0x18001d320  push    rbp
0x18001d322  push    rbx
0x18001d323  push    rsi
0x18001d324  push    rdi
0x18001d325  push    r12
0x18001d327  push    r13
0x18001d329  push    r14
0x18001d32b  push    r15
0x18001d32d  mov     rbp, rsp
0x18001d330  sub     rsp, 78h
0x18001d334  mov     rdi, [rcx+18h]
0x18001d338  mov     r13, r9
0x18001d33b  mov     r15, r8
0x18001d33e  mov     r12, rdx
0x18001d341  mov     rbx, rcx
0x18001d344  test    rdi, rdi
0x18001d347  jz      loc_18001D4F1
0x18001d34d  movzx   eax, word ptr [rcx+2]
0x18001d351  add     rdi, 0Ah
0x18001d355  mov     r8, [rcx+20h]
0x18001d359  xorps   xmm0, xmm0
0x18001d35c  mov     [rbp+var_48], ax
0x18001d360  mov     al, [rcx+4]
0x18001d363  mov     [rbp+var_46], al
0x18001d366  xor     eax, eax
0x18001d368  mov     [rbp+var_40], ax
0x18001d36c  xor     r14b, r14b
0x18001d36f  mov     [rbp+Source], rdi
0x18001d373  mov     [rbp+var_44], 0
0x18001d37a  movdqu  [rbp+var_38], xmm0
0x18001d37f  jmp     short loc_18001D3B9
0x18001d381  mov     r8, r15; unsigned __int64
0x18001d384  lea     rcx, [rbp+var_48]; this
0x18001d388  mov     rdx, r12; void *
0x18001d38b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001d390  test    eax, eax
0x18001d392  js      loc_18001D4B4
0x18001d398  mov     r8, [rbp+Source]; unsigned __int8 *
0x18001d39c  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18001d3a0  jz      loc_18001D484
0x18001d3a6  mov     rcx, rbx; this
0x18001d3a9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001d3ae  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001d3b2  mov     rdi, rax
0x18001d3b5  mov     [rbp+Source], rax
0x18001d3b9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001d3bd  lea     rcx, [rbp+var_48]; this
0x18001d3c1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001d3c6  mov     sil, al
0x18001d3c9  test    al, al
0x18001d3cb  jnz     short loc_18001D381
0x18001d3cd  mov     rdi, [rbp+Source]
0x18001d3d1  mov     [rbx+20h], rdi
0x18001d3d5  xor     r8d, r8d
0x18001d3d8  test    r14b, r14b
0x18001d3db  jnz     short loc_18001D3FD
0x18001d3dd  lea     rcx, [rbp+var_48]; this
0x18001d3e1  mov     [rbp+var_44], 1
0x18001d3e8  mov     [rbp+var_40], r15w
0x18001d3ed  mov     qword ptr [rbp+var_38], r8
0x18001d3f1  mov     qword ptr [rbp+var_38+8], r12
0x18001d3f5  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001d3fa  mov     r8, rax
0x18001d3fd  movzx   ecx, word ptr [rbx+6]
0x18001d401  mov     eax, [rbp+arg_28]
0x18001d404  mov     [rbp+var_28], cx
0x18001d408  mov     cl, [rbx+8]
0x18001d40b  mov     [rbp+var_24], eax
0x18001d40e  mov     rax, [rbp+arg_20]
0x18001d412  mov     [rbp+var_26], cl
0x18001d415  lea     rcx, [rbp+var_28]; this
0x18001d419  mov     [rbp+var_20], ax
0x18001d41d  mov     [rbp+var_18], 0
0x18001d425  mov     [rbp+var_10], r13
0x18001d429  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001d42e  mov     rdx, [rbx+28h]
0x18001d432  mov     r9, [rbx+20h]
0x18001d436  mov     rcx, rdx
0x18001d439  sub     rcx, r9
0x18001d43c  lea     rsi, [rax+r8]
0x18001d440  cmp     r9, rdx
0x18001d443  sbb     rax, rax
0x18001d446  and     rax, rcx
0x18001d449  cmp     rax, rsi
0x18001d44c  jb      loc_18001D4F1
0x18001d452  sub     rdx, rsi
0x18001d455  lea     rcx, [rsi+rdi]; Destination
0x18001d459  sub     rdx, rdi; DestinationSize
0x18001d45c  sub     r9, rdi; SourceSize
0x18001d45f  mov     r8, rdi; Source
0x18001d462  call    cs:__imp_memmove_s
0x18001d468  add     [rbx+20h], rsi
0x18001d46c  test    r14b, r14b
0x18001d46f  jnz     short loc_18001D4C6
0x18001d471  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001d475  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001d479  lea     rcx, [rbp+var_48]; this
0x18001d47d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001d482  jmp     short loc_18001D4DA
0x18001d484  mov     ecx, [rbp+arg_28]
0x18001d487  mov     r9, r13; void *
0x18001d48a  mov     [rsp+78h+var_50], ecx; unsigned int
0x18001d48e  mov     rcx, [rbp+arg_20]
0x18001d492  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001d497  mov     rcx, rbx; this
0x18001d49a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001d49f  mov     [rbp+Source], rax
0x18001d4a3  mov     rdi, rax
0x18001d4a6  test    rax, rax
0x18001d4a9  jnz     short loc_18001D4AF
0x18001d4ab  mov     al, 1
0x18001d4ad  jmp     short loc_18001D4F3
0x18001d4af  mov     r14b, 1
0x18001d4b2  jmp     short loc_18001D4B8
0x18001d4b4  mov     [rbp+Source], rdi
0x18001d4b8  test    sil, sil
0x18001d4bb  jnz     loc_18001D3D5
0x18001d4c1  jmp     loc_18001D3D1
0x18001d4c6  cmp     [rbp+var_46], 0
0x18001d4ca  jz      short loc_18001D4DA
0x18001d4cc  mov     edx, [rbp+var_44]
0x18001d4cf  lea     rcx, [rbp+var_48]; this
0x18001d4d3  inc     edx; unsigned int
0x18001d4d5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001d4da  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001d4de  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001d4e2  lea     rcx, [rbp+var_28]; this
0x18001d4e6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001d4eb  mov     byte ptr [rbx+38h], 1
0x18001d4ef  jmp     short loc_18001D4AB
0x18001d4f1  xor     al, al
0x18001d4f3  add     rsp, 78h
0x18001d4f7  pop     r15
0x18001d4f9  pop     r14
0x18001d4fb  pop     r13
0x18001d4fd  pop     r12
0x18001d4ff  pop     rdi
0x18001d500  pop     rsi
0x18001d501  pop     rbx
0x18001d502  pop     rbp
0x18001d503  retn
```
