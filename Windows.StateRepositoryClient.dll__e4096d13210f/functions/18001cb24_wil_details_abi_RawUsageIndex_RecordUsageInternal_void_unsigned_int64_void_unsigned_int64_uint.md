# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001cb24`
- end: `0x18001ccfe`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ca30`

## callees

- `0x18001bc64`
- `0x18001bd24`
- `0x18001bf24`
- `0x18001c614`
- `0x18001cb24`
- `0x18001d060`
- `0x18001d3fc`
- `0x18001d654`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001cc94`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001cc94`

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
  const void *v22; // [rsp+30h] [rbp-40h] BYREF
  __int16 v23; // [rsp+38h] [rbp-38h]
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int16 v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+52h] [rbp-1Eh]
  unsigned int v27; // [rsp+54h] [rbp-1Ch]
  __int16 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  void *v30; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v32; // [rsp+C8h] [rbp+58h]

  v32 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    LOWORD(v22) = *((_WORD *)this + 1);
    BYTE2(v22) = *((_BYTE *)this + 4);
    v23 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    HIDWORD(v22) = 0;
    v24 = 0;
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
      v15 = wil::details_abi::UsageIndexProperty::Compare(&v22, a2, a3);
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
                                  v32,
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
    HIDWORD(v22) = 1;
    v23 = a3;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v25 = *((_WORD *)this + 3);
    v26 = *((_BYTE *)this + 8);
    v27 = v13;
    v28 = v14;
    v29 = 0;
    v30 = v32;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v25);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( BYTE2(v22) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v22,
            HIDWORD(v22) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v25,
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
0x18001cb24  mov     [rsp-38h+arg_8], rbx
0x18001cb29  mov     [rsp-38h+arg_18], r9
0x18001cb2e  push    rbp
0x18001cb2f  push    rsi
0x18001cb30  push    rdi
0x18001cb31  push    r12
0x18001cb33  push    r13
0x18001cb35  push    r14
0x18001cb37  push    r15
0x18001cb39  mov     rbp, rsp
0x18001cb3c  sub     rsp, 70h
0x18001cb40  mov     rdi, [rcx+18h]
0x18001cb44  mov     r14, r8
0x18001cb47  mov     r15, rdx
0x18001cb4a  mov     rbx, rcx
0x18001cb4d  test    rdi, rdi
0x18001cb50  jz      loc_18001CCE4
0x18001cb56  movzx   eax, word ptr [rcx+2]
0x18001cb5a  add     rdi, 0Ah
0x18001cb5e  mov     [rbp+var_40], ax
0x18001cb62  xorps   xmm0, xmm0
0x18001cb65  mov     al, [rcx+4]
0x18001cb68  mov     [rbp+var_3E], al
0x18001cb6b  xor     eax, eax
0x18001cb6d  mov     [rbp+var_38], ax
0x18001cb71  xor     sil, sil
0x18001cb74  mov     [rbp+arg_0], rdi
0x18001cb78  mov     [rbp+var_3C], 0
0x18001cb7f  movdqu  [rbp+var_30], xmm0
0x18001cb84  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001cb88  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001cb8c  lea     rcx, [rbp+var_40]; this
0x18001cb90  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001cb95  mov     r12d, [rbp+arg_28]
0x18001cb99  mov     r13, [rbp+arg_20]
0x18001cb9d  test    al, al
0x18001cb9f  jz      short loc_18001CC08
0x18001cba1  mov     r8, r14; unsigned __int64
0x18001cba4  lea     rcx, [rbp+var_40]; this
0x18001cba8  mov     rdx, r15; void *
0x18001cbab  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001cbb0  test    eax, eax
0x18001cbb2  js      short loc_18001CBFA
0x18001cbb4  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001cbb8  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001cbbc  mov     rcx, rbx; this
0x18001cbbf  jz      short loc_18001CBCF
0x18001cbc1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001cbc6  mov     rdi, rax
0x18001cbc9  mov     [rbp+arg_0], rax
0x18001cbcd  jmp     short loc_18001CB84
0x18001cbcf  mov     r9, [rbp+arg_18]; void *
0x18001cbd3  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001cbd8  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001cbdd  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001cbe2  mov     [rbp+arg_0], rax
0x18001cbe6  mov     rdi, rax
0x18001cbe9  test    rax, rax
0x18001cbec  jnz     short loc_18001CBF5
0x18001cbee  mov     al, 1
0x18001cbf0  jmp     loc_18001CCE6
0x18001cbf5  mov     sil, 1
0x18001cbf8  jmp     short loc_18001CBFE
0x18001cbfa  mov     [rbp+arg_0], rdi
0x18001cbfe  xor     r8d, r8d
0x18001cc01  test    sil, sil
0x18001cc04  jnz     short loc_18001CC34
0x18001cc06  jmp     short loc_18001CC10
0x18001cc08  mov     rdi, [rbp+arg_0]
0x18001cc0c  mov     [rbx+20h], rdi
0x18001cc10  lea     rcx, [rbp+var_40]; this
0x18001cc14  mov     [rbp+var_3C], 1
0x18001cc1b  mov     [rbp+var_38], r14w
0x18001cc20  mov     qword ptr [rbp+var_30], 0
0x18001cc28  mov     qword ptr [rbp+var_30+8], r15
0x18001cc2c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001cc31  mov     r8, rax
0x18001cc34  movzx   ecx, word ptr [rbx+6]
0x18001cc38  mov     rax, [rbp+arg_18]
0x18001cc3c  mov     [rbp+var_20], cx
0x18001cc40  mov     cl, [rbx+8]
0x18001cc43  mov     [rbp+var_1E], cl
0x18001cc46  lea     rcx, [rbp+var_20]; this
0x18001cc4a  mov     [rbp+var_1C], r12d
0x18001cc4e  mov     [rbp+var_18], r13w
0x18001cc53  mov     [rbp+var_10], 0
0x18001cc5b  mov     [rbp+var_8], rax
0x18001cc5f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001cc64  mov     rdx, [rbx+28h]
0x18001cc68  mov     r9, [rbx+20h]
0x18001cc6c  mov     rcx, rdx
0x18001cc6f  sub     rcx, r9
0x18001cc72  lea     r14, [rax+r8]
0x18001cc76  cmp     r9, rdx
0x18001cc79  sbb     rax, rax
0x18001cc7c  and     rax, rcx
0x18001cc7f  cmp     rax, r14
0x18001cc82  jb      short loc_18001CCE4
0x18001cc84  sub     rdx, r14
0x18001cc87  lea     rcx, [r14+rdi]; Destination
0x18001cc8b  sub     rdx, rdi; DestinationSize
0x18001cc8e  sub     r9, rdi; SourceSize
0x18001cc91  mov     r8, rdi; Source
0x18001cc94  call    cs:__imp_memmove_s
0x18001cc9a  add     [rbx+20h], r14
0x18001cc9e  test    sil, sil
0x18001cca1  jnz     short loc_18001CCB6
0x18001cca3  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001cca7  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001ccab  lea     rcx, [rbp+var_40]; this
0x18001ccaf  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001ccb4  jmp     short loc_18001CCCA
0x18001ccb6  cmp     [rbp+var_3E], 0
0x18001ccba  jz      short loc_18001CCCA
0x18001ccbc  mov     edx, [rbp+var_3C]
0x18001ccbf  lea     rcx, [rbp+var_40]; this
0x18001ccc3  inc     edx; unsigned int
0x18001ccc5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001ccca  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001ccce  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001ccd2  lea     rcx, [rbp+var_20]; this
0x18001ccd6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001ccdb  mov     byte ptr [rbx+38h], 1
0x18001ccdf  jmp     loc_18001CBEE
0x18001cce4  xor     al, al
0x18001cce6  mov     rbx, [rsp+70h+arg_8]
0x18001ccee  add     rsp, 70h
0x18001ccf2  pop     r15
0x18001ccf4  pop     r14
0x18001ccf6  pop     r13
0x18001ccf8  pop     r12
0x18001ccfa  pop     rdi
0x18001ccfb  pop     rsi
0x18001ccfc  pop     rbp
0x18001ccfd  retn
```
