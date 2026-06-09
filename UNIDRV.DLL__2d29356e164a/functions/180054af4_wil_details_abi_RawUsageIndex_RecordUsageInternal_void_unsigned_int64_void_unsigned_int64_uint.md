# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180054af4`
- end: `0x180054cd8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180054a00`

## callees

- `0x180051b10`
- `0x180052054`
- `0x180052db8`
- `0x1800544d8`
- `0x180054af4`
- `0x180055824`
- `0x180055ecc`
- `0x180056284`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180054c36`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180054c36`

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
0x180054af4  push    rbp
0x180054af6  push    rbx
0x180054af7  push    rsi
0x180054af8  push    rdi
0x180054af9  push    r12
0x180054afb  push    r13
0x180054afd  push    r14
0x180054aff  push    r15
0x180054b01  mov     rbp, rsp
0x180054b04  sub     rsp, 78h
0x180054b08  mov     rdi, [rcx+18h]
0x180054b0c  mov     r13, r9
0x180054b0f  mov     r15, r8
0x180054b12  mov     r12, rdx
0x180054b15  mov     rbx, rcx
0x180054b18  test    rdi, rdi
0x180054b1b  jz      loc_180054CC5
0x180054b21  movzx   eax, word ptr [rcx+2]
0x180054b25  add     rdi, 0Ah
0x180054b29  mov     r8, [rcx+20h]
0x180054b2d  xorps   xmm0, xmm0
0x180054b30  mov     [rbp+var_48], ax
0x180054b34  mov     al, [rcx+4]
0x180054b37  mov     [rbp+var_46], al
0x180054b3a  xor     eax, eax
0x180054b3c  mov     [rbp+var_40], ax
0x180054b40  xor     r14b, r14b
0x180054b43  mov     [rbp+Source], rdi
0x180054b47  mov     [rbp+var_44], 0
0x180054b4e  movdqu  [rbp+var_38], xmm0
0x180054b53  jmp     short loc_180054B8D
0x180054b55  mov     r8, r15; unsigned __int64
0x180054b58  lea     rcx, [rbp+var_48]; this
0x180054b5c  mov     rdx, r12; void *
0x180054b5f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180054b64  test    eax, eax
0x180054b66  js      loc_180054C88
0x180054b6c  mov     r8, [rbp+Source]; unsigned __int8 *
0x180054b70  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180054b74  jz      loc_180054C58
0x180054b7a  mov     rcx, rbx; this
0x180054b7d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180054b82  mov     r8, [rbx+20h]; unsigned __int8 *
0x180054b86  mov     rdi, rax
0x180054b89  mov     [rbp+Source], rax
0x180054b8d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180054b91  lea     rcx, [rbp+var_48]; this
0x180054b95  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180054b9a  mov     sil, al
0x180054b9d  test    al, al
0x180054b9f  jnz     short loc_180054B55
0x180054ba1  mov     rdi, [rbp+Source]
0x180054ba5  mov     [rbx+20h], rdi
0x180054ba9  xor     r8d, r8d
0x180054bac  test    r14b, r14b
0x180054baf  jnz     short loc_180054BD1
0x180054bb1  lea     rcx, [rbp+var_48]; this
0x180054bb5  mov     [rbp+var_44], 1
0x180054bbc  mov     [rbp+var_40], r15w
0x180054bc1  mov     qword ptr [rbp+var_38], r8
0x180054bc5  mov     qword ptr [rbp+var_38+8], r12
0x180054bc9  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180054bce  mov     r8, rax
0x180054bd1  movzx   ecx, word ptr [rbx+6]
0x180054bd5  mov     eax, [rbp+arg_28]
0x180054bd8  mov     [rbp+var_28], cx
0x180054bdc  mov     cl, [rbx+8]
0x180054bdf  mov     [rbp+var_24], eax
0x180054be2  mov     rax, [rbp+arg_20]
0x180054be6  mov     [rbp+var_26], cl
0x180054be9  lea     rcx, [rbp+var_28]; this
0x180054bed  mov     [rbp+var_20], ax
0x180054bf1  mov     [rbp+var_18], 0
0x180054bf9  mov     [rbp+var_10], r13
0x180054bfd  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180054c02  mov     rdx, [rbx+28h]
0x180054c06  mov     r9, [rbx+20h]
0x180054c0a  mov     rcx, rdx
0x180054c0d  sub     rcx, r9
0x180054c10  lea     rsi, [rax+r8]
0x180054c14  cmp     r9, rdx
0x180054c17  sbb     rax, rax
0x180054c1a  and     rax, rcx
0x180054c1d  cmp     rax, rsi
0x180054c20  jb      loc_180054CC5
0x180054c26  sub     rdx, rsi
0x180054c29  lea     rcx, [rsi+rdi]; Destination
0x180054c2d  sub     rdx, rdi; DestinationSize
0x180054c30  sub     r9, rdi; SourceSize
0x180054c33  mov     r8, rdi; Source
0x180054c36  call    cs:__imp_memmove_s
0x180054c3c  add     [rbx+20h], rsi
0x180054c40  test    r14b, r14b
0x180054c43  jnz     short loc_180054C9A
0x180054c45  mov     r8, [rbx+20h]; unsigned __int8 *
0x180054c49  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180054c4d  lea     rcx, [rbp+var_48]; this
0x180054c51  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180054c56  jmp     short loc_180054CAE
0x180054c58  mov     ecx, [rbp+arg_28]
0x180054c5b  mov     r9, r13; void *
0x180054c5e  mov     [rsp+78h+var_50], ecx; unsigned int
0x180054c62  mov     rcx, [rbp+arg_20]
0x180054c66  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180054c6b  mov     rcx, rbx; this
0x180054c6e  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180054c73  mov     [rbp+Source], rax
0x180054c77  mov     rdi, rax
0x180054c7a  test    rax, rax
0x180054c7d  jnz     short loc_180054C83
0x180054c7f  mov     al, 1
0x180054c81  jmp     short loc_180054CC7
0x180054c83  mov     r14b, 1
0x180054c86  jmp     short loc_180054C8C
0x180054c88  mov     [rbp+Source], rdi
0x180054c8c  test    sil, sil
0x180054c8f  jnz     loc_180054BA9
0x180054c95  jmp     loc_180054BA5
0x180054c9a  cmp     [rbp+var_46], 0
0x180054c9e  jz      short loc_180054CAE
0x180054ca0  mov     edx, [rbp+var_44]
0x180054ca3  lea     rcx, [rbp+var_48]; this
0x180054ca7  inc     edx; unsigned int
0x180054ca9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180054cae  mov     r8, [rbx+20h]; unsigned __int8 *
0x180054cb2  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180054cb6  lea     rcx, [rbp+var_28]; this
0x180054cba  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180054cbf  mov     byte ptr [rbx+38h], 1
0x180054cc3  jmp     short loc_180054C7F
0x180054cc5  xor     al, al
0x180054cc7  add     rsp, 78h
0x180054ccb  pop     r15
0x180054ccd  pop     r14
0x180054ccf  pop     r13
0x180054cd1  pop     r12
0x180054cd3  pop     rdi
0x180054cd4  pop     rsi
0x180054cd5  pop     rbx
0x180054cd6  pop     rbp
0x180054cd7  retn
```
