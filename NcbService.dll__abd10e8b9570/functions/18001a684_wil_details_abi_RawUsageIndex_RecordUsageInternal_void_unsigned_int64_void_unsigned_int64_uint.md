# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001a684`
- end: `0x18001a85e`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a590`

## callees

- `0x18001a684`
- `0x18002e360`
- `0x18002e784`
- `0x18002f08c`
- `0x18002fcd0`
- `0x180030ae4`
- `0x180031288`
- `0x18003153c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001a7f4`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001a7f4`

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
0x18001a684  mov     [rsp-38h+arg_8], rbx
0x18001a689  mov     [rsp-38h+arg_18], r9
0x18001a68e  push    rbp
0x18001a68f  push    rsi
0x18001a690  push    rdi
0x18001a691  push    r12
0x18001a693  push    r13
0x18001a695  push    r14
0x18001a697  push    r15
0x18001a699  mov     rbp, rsp
0x18001a69c  sub     rsp, 70h
0x18001a6a0  mov     rdi, [rcx+18h]
0x18001a6a4  mov     r14, r8
0x18001a6a7  mov     r15, rdx
0x18001a6aa  mov     rbx, rcx
0x18001a6ad  test    rdi, rdi
0x18001a6b0  jz      loc_18001A844
0x18001a6b6  movzx   eax, word ptr [rcx+2]
0x18001a6ba  add     rdi, 0Ah
0x18001a6be  mov     [rbp+var_40], ax
0x18001a6c2  xorps   xmm0, xmm0
0x18001a6c5  mov     al, [rcx+4]
0x18001a6c8  mov     [rbp+var_3E], al
0x18001a6cb  xor     eax, eax
0x18001a6cd  mov     [rbp+var_38], ax
0x18001a6d1  xor     sil, sil
0x18001a6d4  mov     [rbp+arg_0], rdi
0x18001a6d8  mov     [rbp+var_3C], 0
0x18001a6df  movdqu  [rbp+var_30], xmm0
0x18001a6e4  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001a6e8  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001a6ec  lea     rcx, [rbp+var_40]; this
0x18001a6f0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001a6f5  mov     r12d, [rbp+arg_28]
0x18001a6f9  mov     r13, [rbp+arg_20]
0x18001a6fd  test    al, al
0x18001a6ff  jz      short loc_18001A768
0x18001a701  mov     r8, r14; unsigned __int64
0x18001a704  lea     rcx, [rbp+var_40]; this
0x18001a708  mov     rdx, r15; void *
0x18001a70b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001a710  test    eax, eax
0x18001a712  js      short loc_18001A75A
0x18001a714  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001a718  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001a71c  mov     rcx, rbx; this
0x18001a71f  jz      short loc_18001A72F
0x18001a721  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001a726  mov     rdi, rax
0x18001a729  mov     [rbp+arg_0], rax
0x18001a72d  jmp     short loc_18001A6E4
0x18001a72f  mov     r9, [rbp+arg_18]; void *
0x18001a733  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001a738  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001a73d  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001a742  mov     [rbp+arg_0], rax
0x18001a746  mov     rdi, rax
0x18001a749  test    rax, rax
0x18001a74c  jnz     short loc_18001A755
0x18001a74e  mov     al, 1
0x18001a750  jmp     loc_18001A846
0x18001a755  mov     sil, 1
0x18001a758  jmp     short loc_18001A75E
0x18001a75a  mov     [rbp+arg_0], rdi
0x18001a75e  xor     r8d, r8d
0x18001a761  test    sil, sil
0x18001a764  jnz     short loc_18001A794
0x18001a766  jmp     short loc_18001A770
0x18001a768  mov     rdi, [rbp+arg_0]
0x18001a76c  mov     [rbx+20h], rdi
0x18001a770  lea     rcx, [rbp+var_40]; this
0x18001a774  mov     [rbp+var_3C], 1
0x18001a77b  mov     [rbp+var_38], r14w
0x18001a780  mov     qword ptr [rbp+var_30], 0
0x18001a788  mov     qword ptr [rbp+var_30+8], r15
0x18001a78c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001a791  mov     r8, rax
0x18001a794  movzx   ecx, word ptr [rbx+6]
0x18001a798  mov     rax, [rbp+arg_18]
0x18001a79c  mov     [rbp+var_20], cx
0x18001a7a0  mov     cl, [rbx+8]
0x18001a7a3  mov     [rbp+var_1E], cl
0x18001a7a6  lea     rcx, [rbp+var_20]; this
0x18001a7aa  mov     [rbp+var_1C], r12d
0x18001a7ae  mov     [rbp+var_18], r13w
0x18001a7b3  mov     [rbp+var_10], 0
0x18001a7bb  mov     [rbp+var_8], rax
0x18001a7bf  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001a7c4  mov     rdx, [rbx+28h]
0x18001a7c8  mov     r9, [rbx+20h]
0x18001a7cc  mov     rcx, rdx
0x18001a7cf  sub     rcx, r9
0x18001a7d2  lea     r14, [rax+r8]
0x18001a7d6  cmp     r9, rdx
0x18001a7d9  sbb     rax, rax
0x18001a7dc  and     rax, rcx
0x18001a7df  cmp     rax, r14
0x18001a7e2  jb      short loc_18001A844
0x18001a7e4  sub     rdx, r14
0x18001a7e7  lea     rcx, [r14+rdi]; Destination
0x18001a7eb  sub     rdx, rdi; DestinationSize
0x18001a7ee  sub     r9, rdi; SourceSize
0x18001a7f1  mov     r8, rdi; Source
0x18001a7f4  call    cs:__imp_memmove_s
0x18001a7fa  add     [rbx+20h], r14
0x18001a7fe  test    sil, sil
0x18001a801  jnz     short loc_18001A816
0x18001a803  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001a807  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001a80b  lea     rcx, [rbp+var_40]; this
0x18001a80f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001a814  jmp     short loc_18001A82A
0x18001a816  cmp     [rbp+var_3E], 0
0x18001a81a  jz      short loc_18001A82A
0x18001a81c  mov     edx, [rbp+var_3C]
0x18001a81f  lea     rcx, [rbp+var_40]; this
0x18001a823  inc     edx; unsigned int
0x18001a825  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001a82a  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001a82e  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001a832  lea     rcx, [rbp+var_20]; this
0x18001a836  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001a83b  mov     byte ptr [rbx+38h], 1
0x18001a83f  jmp     loc_18001A74E
0x18001a844  xor     al, al
0x18001a846  mov     rbx, [rsp+70h+arg_8]
0x18001a84e  add     rsp, 70h
0x18001a852  pop     r15
0x18001a854  pop     r14
0x18001a856  pop     r13
0x18001a858  pop     r12
0x18001a85a  pop     rdi
0x18001a85b  pop     rsi
0x18001a85c  pop     rbp
0x18001a85d  retn
```
