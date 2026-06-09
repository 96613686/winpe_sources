# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009a34`
- end: `0x180009c18`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009940`

## callees

- `0x180005ee4`
- `0x18000637c`
- `0x180007da0`
- `0x180009434`
- `0x180009a34`
- `0x18000ab60`
- `0x18000b3f0`
- `0x18000b778`

## import_xrefs

- `msvcrt!memmove_s` at `0x180009b76`
- `msvcrt!memmove_s` at `0x180009b76`

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
0x180009a34  push    rbp
0x180009a36  push    rbx
0x180009a37  push    rsi
0x180009a38  push    rdi
0x180009a39  push    r12
0x180009a3b  push    r13
0x180009a3d  push    r14
0x180009a3f  push    r15
0x180009a41  mov     rbp, rsp
0x180009a44  sub     rsp, 78h
0x180009a48  mov     rdi, [rcx+18h]
0x180009a4c  mov     r13, r9
0x180009a4f  mov     r15, r8
0x180009a52  mov     r12, rdx
0x180009a55  mov     rbx, rcx
0x180009a58  test    rdi, rdi
0x180009a5b  jz      loc_180009C05
0x180009a61  movzx   eax, word ptr [rcx+2]
0x180009a65  add     rdi, 0Ah
0x180009a69  mov     r8, [rcx+20h]
0x180009a6d  xorps   xmm0, xmm0
0x180009a70  mov     [rbp+var_48], ax
0x180009a74  mov     al, [rcx+4]
0x180009a77  mov     [rbp+var_46], al
0x180009a7a  xor     eax, eax
0x180009a7c  mov     [rbp+var_40], ax
0x180009a80  xor     r14b, r14b
0x180009a83  mov     [rbp+Source], rdi
0x180009a87  mov     [rbp+var_44], 0
0x180009a8e  movdqu  [rbp+var_38], xmm0
0x180009a93  jmp     short loc_180009ACD
0x180009a95  mov     r8, r15; unsigned __int64
0x180009a98  lea     rcx, [rbp+var_48]; this
0x180009a9c  mov     rdx, r12; void *
0x180009a9f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180009aa4  test    eax, eax
0x180009aa6  js      loc_180009BC8
0x180009aac  mov     r8, [rbp+Source]; unsigned __int8 *
0x180009ab0  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180009ab4  jz      loc_180009B98
0x180009aba  mov     rcx, rbx; this
0x180009abd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180009ac2  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009ac6  mov     rdi, rax
0x180009ac9  mov     [rbp+Source], rax
0x180009acd  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180009ad1  lea     rcx, [rbp+var_48]; this
0x180009ad5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009ada  mov     sil, al
0x180009add  test    al, al
0x180009adf  jnz     short loc_180009A95
0x180009ae1  mov     rdi, [rbp+Source]
0x180009ae5  mov     [rbx+20h], rdi
0x180009ae9  xor     r8d, r8d
0x180009aec  test    r14b, r14b
0x180009aef  jnz     short loc_180009B11
0x180009af1  lea     rcx, [rbp+var_48]; this
0x180009af5  mov     [rbp+var_44], 1
0x180009afc  mov     [rbp+var_40], r15w
0x180009b01  mov     qword ptr [rbp+var_38], r8
0x180009b05  mov     qword ptr [rbp+var_38+8], r12
0x180009b09  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180009b0e  mov     r8, rax
0x180009b11  movzx   ecx, word ptr [rbx+6]
0x180009b15  mov     eax, [rbp+arg_28]
0x180009b18  mov     [rbp+var_28], cx
0x180009b1c  mov     cl, [rbx+8]
0x180009b1f  mov     [rbp+var_24], eax
0x180009b22  mov     rax, [rbp+arg_20]
0x180009b26  mov     [rbp+var_26], cl
0x180009b29  lea     rcx, [rbp+var_28]; this
0x180009b2d  mov     [rbp+var_20], ax
0x180009b31  mov     [rbp+var_18], 0
0x180009b39  mov     [rbp+var_10], r13
0x180009b3d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180009b42  mov     rdx, [rbx+28h]
0x180009b46  mov     r9, [rbx+20h]
0x180009b4a  mov     rcx, rdx
0x180009b4d  sub     rcx, r9
0x180009b50  lea     rsi, [rax+r8]
0x180009b54  cmp     r9, rdx
0x180009b57  sbb     rax, rax
0x180009b5a  and     rax, rcx
0x180009b5d  cmp     rax, rsi
0x180009b60  jb      loc_180009C05
0x180009b66  sub     rdx, rsi
0x180009b69  lea     rcx, [rsi+rdi]; Destination
0x180009b6d  sub     rdx, rdi; DestinationSize
0x180009b70  sub     r9, rdi; SourceSize
0x180009b73  mov     r8, rdi; Source
0x180009b76  call    cs:__imp_memmove_s
0x180009b7c  add     [rbx+20h], rsi
0x180009b80  test    r14b, r14b
0x180009b83  jnz     short loc_180009BDA
0x180009b85  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009b89  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180009b8d  lea     rcx, [rbp+var_48]; this
0x180009b91  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009b96  jmp     short loc_180009BEE
0x180009b98  mov     ecx, [rbp+arg_28]
0x180009b9b  mov     r9, r13; void *
0x180009b9e  mov     [rsp+78h+var_50], ecx; unsigned int
0x180009ba2  mov     rcx, [rbp+arg_20]
0x180009ba6  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180009bab  mov     rcx, rbx; this
0x180009bae  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180009bb3  mov     [rbp+Source], rax
0x180009bb7  mov     rdi, rax
0x180009bba  test    rax, rax
0x180009bbd  jnz     short loc_180009BC3
0x180009bbf  mov     al, 1
0x180009bc1  jmp     short loc_180009C07
0x180009bc3  mov     r14b, 1
0x180009bc6  jmp     short loc_180009BCC
0x180009bc8  mov     [rbp+Source], rdi
0x180009bcc  test    sil, sil
0x180009bcf  jnz     loc_180009AE9
0x180009bd5  jmp     loc_180009AE5
0x180009bda  cmp     [rbp+var_46], 0
0x180009bde  jz      short loc_180009BEE
0x180009be0  mov     edx, [rbp+var_44]
0x180009be3  lea     rcx, [rbp+var_48]; this
0x180009be7  inc     edx; unsigned int
0x180009be9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180009bee  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009bf2  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180009bf6  lea     rcx, [rbp+var_28]; this
0x180009bfa  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009bff  mov     byte ptr [rbx+38h], 1
0x180009c03  jmp     short loc_180009BBF
0x180009c05  xor     al, al
0x180009c07  add     rsp, 78h
0x180009c0b  pop     r15
0x180009c0d  pop     r14
0x180009c0f  pop     r13
0x180009c11  pop     r12
0x180009c13  pop     rdi
0x180009c14  pop     rsi
0x180009c15  pop     rbx
0x180009c16  pop     rbp
0x180009c17  retn
```
