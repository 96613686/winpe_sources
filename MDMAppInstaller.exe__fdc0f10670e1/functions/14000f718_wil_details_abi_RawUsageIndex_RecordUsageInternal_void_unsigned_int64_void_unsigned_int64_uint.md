# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000f718`
- end: `0x14000f8f2`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f624`

## callees

- `0x14000a118`
- `0x14000b4b4`
- `0x14000cd44`
- `0x14000f198`
- `0x14000f718`
- `0x14001096c`
- `0x1400111f4`
- `0x140011524`

## import_xrefs

- `msvcrt!memmove_s` at `0x14000f888`
- `msvcrt!memmove_s` at `0x14000f888`

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
0x14000f718  mov     [rsp-38h+arg_8], rbx
0x14000f71d  mov     [rsp-38h+arg_18], r9
0x14000f722  push    rbp
0x14000f723  push    rsi
0x14000f724  push    rdi
0x14000f725  push    r12
0x14000f727  push    r13
0x14000f729  push    r14
0x14000f72b  push    r15
0x14000f72d  mov     rbp, rsp
0x14000f730  sub     rsp, 70h
0x14000f734  mov     rdi, [rcx+18h]
0x14000f738  mov     r14, r8
0x14000f73b  mov     r15, rdx
0x14000f73e  mov     rbx, rcx
0x14000f741  test    rdi, rdi
0x14000f744  jz      loc_14000F8D8
0x14000f74a  movzx   eax, word ptr [rcx+2]
0x14000f74e  add     rdi, 0Ah
0x14000f752  mov     [rbp+var_40], ax
0x14000f756  xorps   xmm0, xmm0
0x14000f759  mov     al, [rcx+4]
0x14000f75c  mov     [rbp+var_3E], al
0x14000f75f  xor     eax, eax
0x14000f761  mov     [rbp+var_38], ax
0x14000f765  xor     sil, sil
0x14000f768  mov     [rbp+arg_0], rdi
0x14000f76c  mov     [rbp+var_3C], 0
0x14000f773  movdqu  [rbp+var_30], xmm0
0x14000f778  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000f77c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000f780  lea     rcx, [rbp+var_40]; this
0x14000f784  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000f789  mov     r12d, [rbp+arg_28]
0x14000f78d  mov     r13, [rbp+arg_20]
0x14000f791  test    al, al
0x14000f793  jz      short loc_14000F7FC
0x14000f795  mov     r8, r14; unsigned __int64
0x14000f798  lea     rcx, [rbp+var_40]; this
0x14000f79c  mov     rdx, r15; void *
0x14000f79f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x14000f7a4  test    eax, eax
0x14000f7a6  js      short loc_14000F7EE
0x14000f7a8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x14000f7ac  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x14000f7b0  mov     rcx, rbx; this
0x14000f7b3  jz      short loc_14000F7C3
0x14000f7b5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x14000f7ba  mov     rdi, rax
0x14000f7bd  mov     [rbp+arg_0], rax
0x14000f7c1  jmp     short loc_14000F778
0x14000f7c3  mov     r9, [rbp+arg_18]; void *
0x14000f7c7  mov     [rsp+70h+var_48], r12d; unsigned int
0x14000f7cc  mov     [rsp+70h+var_50], r13; unsigned __int64
0x14000f7d1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14000f7d6  mov     [rbp+arg_0], rax
0x14000f7da  mov     rdi, rax
0x14000f7dd  test    rax, rax
0x14000f7e0  jnz     short loc_14000F7E9
0x14000f7e2  mov     al, 1
0x14000f7e4  jmp     loc_14000F8DA
0x14000f7e9  mov     sil, 1
0x14000f7ec  jmp     short loc_14000F7F2
0x14000f7ee  mov     [rbp+arg_0], rdi
0x14000f7f2  xor     r8d, r8d
0x14000f7f5  test    sil, sil
0x14000f7f8  jnz     short loc_14000F828
0x14000f7fa  jmp     short loc_14000F804
0x14000f7fc  mov     rdi, [rbp+arg_0]
0x14000f800  mov     [rbx+20h], rdi
0x14000f804  lea     rcx, [rbp+var_40]; this
0x14000f808  mov     [rbp+var_3C], 1
0x14000f80f  mov     [rbp+var_38], r14w
0x14000f814  mov     qword ptr [rbp+var_30], 0
0x14000f81c  mov     qword ptr [rbp+var_30+8], r15
0x14000f820  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000f825  mov     r8, rax
0x14000f828  movzx   ecx, word ptr [rbx+6]
0x14000f82c  mov     rax, [rbp+arg_18]
0x14000f830  mov     [rbp+var_20], cx
0x14000f834  mov     cl, [rbx+8]
0x14000f837  mov     [rbp+var_1E], cl
0x14000f83a  lea     rcx, [rbp+var_20]; this
0x14000f83e  mov     [rbp+var_1C], r12d
0x14000f842  mov     [rbp+var_18], r13w
0x14000f847  mov     [rbp+var_10], 0
0x14000f84f  mov     [rbp+var_8], rax
0x14000f853  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000f858  mov     rdx, [rbx+28h]
0x14000f85c  mov     r9, [rbx+20h]
0x14000f860  mov     rcx, rdx
0x14000f863  sub     rcx, r9
0x14000f866  lea     r14, [rax+r8]
0x14000f86a  cmp     r9, rdx
0x14000f86d  sbb     rax, rax
0x14000f870  and     rax, rcx
0x14000f873  cmp     rax, r14
0x14000f876  jb      short loc_14000F8D8
0x14000f878  sub     rdx, r14
0x14000f87b  lea     rcx, [r14+rdi]; Destination
0x14000f87f  sub     rdx, rdi; DestinationSize
0x14000f882  sub     r9, rdi; SourceSize
0x14000f885  mov     r8, rdi; Source
0x14000f888  call    cs:__imp_memmove_s
0x14000f88e  add     [rbx+20h], r14
0x14000f892  test    sil, sil
0x14000f895  jnz     short loc_14000F8AA
0x14000f897  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000f89b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000f89f  lea     rcx, [rbp+var_40]; this
0x14000f8a3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000f8a8  jmp     short loc_14000F8BE
0x14000f8aa  cmp     [rbp+var_3E], 0
0x14000f8ae  jz      short loc_14000F8BE
0x14000f8b0  mov     edx, [rbp+var_3C]
0x14000f8b3  lea     rcx, [rbp+var_40]; this
0x14000f8b7  inc     edx; unsigned int
0x14000f8b9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x14000f8be  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000f8c2  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000f8c6  lea     rcx, [rbp+var_20]; this
0x14000f8ca  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000f8cf  mov     byte ptr [rbx+38h], 1
0x14000f8d3  jmp     loc_14000F7E2
0x14000f8d8  xor     al, al
0x14000f8da  mov     rbx, [rsp+70h+arg_8]
0x14000f8e2  add     rsp, 70h
0x14000f8e6  pop     r15
0x14000f8e8  pop     r14
0x14000f8ea  pop     r13
0x14000f8ec  pop     r12
0x14000f8ee  pop     rdi
0x14000f8ef  pop     rsi
0x14000f8f0  pop     rbp
0x14000f8f1  retn
```
