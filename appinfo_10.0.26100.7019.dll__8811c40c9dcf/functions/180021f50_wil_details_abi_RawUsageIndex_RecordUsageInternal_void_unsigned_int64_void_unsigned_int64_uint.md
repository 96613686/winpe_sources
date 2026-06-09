# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180021f50`
- end: `0x18002213d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `493`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021e4c`

## callees

- `0x180012260`
- `0x180018ee4`
- `0x18001e6ac`
- `0x18001eb60`
- `0x180021f50`
- `0x1800235a8`
- `0x180023f3c`
- `0x180024258`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800220c0`
- `msvcrt!memmove_s` at `0x1800220c0`

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
  unsigned __int8 *v11; // rdi
  char v12; // si
  int v13; // eax
  __int16 v15; // cx
  unsigned __int64 Size; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // r14
  unsigned __int8 *v21; // r8
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+30h] [rbp-50h] BYREF
  __int16 v23; // [rsp+38h] [rbp-48h] BYREF
  char v24; // [rsp+3Ah] [rbp-46h]
  int v25; // [rsp+3Ch] [rbp-44h]
  __int16 v26; // [rsp+40h] [rbp-40h]
  __int128 v27; // [rsp+48h] [rbp-38h]
  __int16 v28; // [rsp+58h] [rbp-28h] BYREF
  char v29; // [rsp+5Ah] [rbp-26h]
  unsigned int v30; // [rsp+5Ch] [rbp-24h]
  __int16 v31; // [rsp+60h] [rbp-20h]
  __int64 v32; // [rsp+68h] [rbp-18h]
  void *v33; // [rsp+70h] [rbp-10h]

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (unsigned __int8 *)(v6 + 10);
    v23 = *((_WORD *)this + 1);
    v12 = 0;
    v24 = *((_BYTE *)this + 4);
    InsertionPointOrIncrement = v11;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v23,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4)) )
      {
        v11 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v13 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v23, a2, a3);
      if ( v13 < 0 )
      {
        InsertionPointOrIncrement = v11;
        goto LABEL_11;
      }
      if ( !v13 )
        break;
      v11 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v23,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v11;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v23,
                                  InsertionPointOrIncrement,
                                  a4,
                                  a5,
                                  a6);
    v11 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v12 = 1;
LABEL_11:
    if ( v12 )
      goto LABEL_15;
LABEL_14:
    *(_QWORD *)&v27 = 0;
    v25 = 1;
    v26 = a3;
    *((_QWORD *)&v27 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v23);
LABEL_15:
    v15 = *((_WORD *)this + 3);
    v32 = 0;
    v28 = v15;
    v29 = *((_BYTE *)this + 8);
    v30 = a6;
    v31 = a5;
    v33 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v28);
    v17 = *((_QWORD *)this + 5);
    v18 = *((_QWORD *)this + 4);
    v20 = v19 + Size;
    if ( ((v17 - v18) & -(__int64)(v18 < v17)) >= v19 + Size )
    {
      memmove_s(&v11[v20], v17 - v20 - (_QWORD)v11, v11, v18 - (_QWORD)v11);
      v21 = (unsigned __int8 *)(v20 + *((_QWORD *)this + 4));
      *((_QWORD *)this + 4) = v21;
      if ( v12 )
      {
        if ( v24 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v23, v25 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v23,
          &InsertionPointOrIncrement,
          v21);
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v28,
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
0x180021f50  mov     [rsp-28h+arg_8], rbx
0x180021f55  mov     [rsp-28h+arg_10], rsi
0x180021f5a  mov     [rsp-28h+arg_18], rdi
0x180021f5f  push    rbp
0x180021f60  push    r12
0x180021f62  push    r13
0x180021f64  push    r14
0x180021f66  push    r15
0x180021f68  mov     rbp, rsp
0x180021f6b  sub     rsp, 80h
0x180021f72  mov     rdi, [rcx+18h]
0x180021f76  mov     rbx, rcx
0x180021f79  xor     ecx, ecx
0x180021f7b  mov     r12, r9
0x180021f7e  mov     r14, r8
0x180021f81  mov     r15, rdx
0x180021f84  test    rdi, rdi
0x180021f87  jz      loc_180022119
0x180021f8d  movzx   eax, word ptr [rbx+2]
0x180021f91  add     rdi, 0Ah
0x180021f95  mov     [rbp+var_48], ax
0x180021f99  xorps   xmm0, xmm0
0x180021f9c  mov     al, [rbx+4]
0x180021f9f  mov     sil, cl
0x180021fa2  mov     [rbp+var_46], al
0x180021fa5  mov     [rbp+var_50], rdi
0x180021fa9  mov     [rbp+var_44], ecx
0x180021fac  mov     [rbp+var_40], cx
0x180021fb0  movdqu  [rbp+var_38], xmm0
0x180021fb5  mov     r8, [rbx+20h]; unsigned __int8 *
0x180021fb9  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180021fbd  lea     rcx, [rbp+var_48]; this
0x180021fc1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180021fc6  mov     r13d, [rbp+arg_28]
0x180021fca  test    al, al
0x180021fcc  jz      short loc_18002203B
0x180021fce  mov     r8, r14; unsigned __int64
0x180021fd1  lea     rcx, [rbp+var_48]; this
0x180021fd5  mov     rdx, r15; void *
0x180021fd8  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180021fdd  test    eax, eax
0x180021fdf  js      short loc_18002202D
0x180021fe1  mov     r8, [rbp+var_50]; unsigned __int8 *
0x180021fe5  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180021fe9  jz      short loc_180021FFC
0x180021feb  mov     rcx, rbx; this
0x180021fee  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180021ff3  mov     rdi, rax
0x180021ff6  mov     [rbp+var_50], rax
0x180021ffa  jmp     short loc_180021FB5
0x180021ffc  mov     rcx, [rbp+arg_20]
0x180022000  mov     r9, r12; void *
0x180022003  mov     [rsp+80h+var_58], r13d; unsigned int
0x180022008  mov     [rsp+80h+var_60], rcx; unsigned __int64
0x18002200d  mov     rcx, rbx; this
0x180022010  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180022015  mov     [rbp+var_50], rax
0x180022019  mov     rdi, rax
0x18002201c  test    rax, rax
0x18002201f  jnz     short loc_180022028
0x180022021  mov     al, 1
0x180022023  jmp     loc_18002211B
0x180022028  mov     sil, 1
0x18002202b  jmp     short loc_180022031
0x18002202d  mov     [rbp+var_50], rdi
0x180022031  xor     r8d, r8d
0x180022034  test    sil, sil
0x180022037  jnz     short loc_180022064
0x180022039  jmp     short loc_180022043
0x18002203b  mov     rdi, [rbp+var_50]
0x18002203f  mov     [rbx+20h], rdi
0x180022043  and     qword ptr [rbp+var_38], 0
0x180022048  lea     rcx, [rbp+var_48]; this
0x18002204c  mov     [rbp+var_44], 1
0x180022053  mov     [rbp+var_40], r14w
0x180022058  mov     qword ptr [rbp+var_38+8], r15
0x18002205c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180022061  mov     r8, rax
0x180022064  movzx   ecx, word ptr [rbx+6]
0x180022068  mov     rax, [rbp+arg_20]
0x18002206c  and     [rbp+var_18], 0
0x180022071  mov     [rbp+var_28], cx
0x180022075  mov     cl, [rbx+8]
0x180022078  mov     [rbp+var_26], cl
0x18002207b  lea     rcx, [rbp+var_28]; this
0x18002207f  mov     [rbp+var_24], r13d
0x180022083  mov     [rbp+var_20], ax
0x180022087  mov     [rbp+var_10], r12
0x18002208b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180022090  mov     rdx, [rbx+28h]
0x180022094  mov     r9, [rbx+20h]
0x180022098  mov     r10, rdx
0x18002209b  sub     r10, r9
0x18002209e  cmp     r9, rdx
0x1800220a1  lea     r14, [r8+rax]
0x1800220a5  sbb     rcx, rcx
0x1800220a8  and     rcx, r10
0x1800220ab  cmp     rcx, r14
0x1800220ae  jb      short loc_180022119
0x1800220b0  sub     rdx, r14
0x1800220b3  lea     rcx, [r14+rdi]; Destination
0x1800220b7  sub     rdx, rdi; DestinationSize
0x1800220ba  sub     r9, rdi; SourceSize
0x1800220bd  mov     r8, rdi; Source
0x1800220c0  call    cs:__imp_memmove_s
0x1800220c7  nop     dword ptr [rax+rax+00h]
0x1800220cc  mov     r8, [rbx+20h]
0x1800220d0  add     r8, r14; unsigned __int8 *
0x1800220d3  mov     [rbx+20h], r8
0x1800220d7  test    sil, sil
0x1800220da  jnz     short loc_1800220EB
0x1800220dc  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x1800220e0  lea     rcx, [rbp+var_48]; this
0x1800220e4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800220e9  jmp     short loc_1800220FF
0x1800220eb  cmp     [rbp+var_46], 0
0x1800220ef  jz      short loc_1800220FF
0x1800220f1  mov     edx, [rbp+var_44]
0x1800220f4  lea     rcx, [rbp+var_48]; this
0x1800220f8  inc     edx; unsigned int
0x1800220fa  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800220ff  mov     r8, [rbx+20h]; unsigned __int8 *
0x180022103  lea     rdx, [rbp+var_50]; unsigned __int8 **
0x180022107  lea     rcx, [rbp+var_28]; this
0x18002210b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180022110  mov     byte ptr [rbx+38h], 1
0x180022114  jmp     loc_180022021
0x180022119  xor     al, al
0x18002211b  lea     r11, [rsp+80h+var_s0]
0x180022123  mov     rbx, [r11+38h]
0x180022127  mov     rsi, [r11+40h]
0x18002212b  mov     rdi, [r11+48h]
0x18002212f  mov     rsp, r11
0x180022132  pop     r15
0x180022134  pop     r14
0x180022136  pop     r13
0x180022138  pop     r12
0x18002213a  pop     rbp
0x18002213b  retn
```
