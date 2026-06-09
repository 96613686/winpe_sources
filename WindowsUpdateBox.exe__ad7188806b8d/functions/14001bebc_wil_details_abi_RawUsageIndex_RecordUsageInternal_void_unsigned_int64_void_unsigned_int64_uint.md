# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14001bebc`
- end: `0x14001c26d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `945`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001bd44`

## callees

- `0x14000dfbc`
- `0x14001b84c`
- `0x14001bebc`
- `0x140020d68`
- `0x140080d36`

## import_xrefs

- `msvcrt!memmove_s` at `0x14001c1ae`
- `msvcrt!memmove_s` at `0x14001c1ae`
- `msvcrt!memcpy_s` at `0x14001bfce`
- `msvcrt!memcpy_s` at `0x14001c06d`
- `msvcrt!memcpy_s` at `0x14001c223`
- `msvcrt!memcpy_s` at `0x14001bfce`
- `msvcrt!memcpy_s` at `0x14001c06d`
- `msvcrt!memcpy_s` at `0x14001c223`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rdi
  char v13; // al
  bool v14; // al
  unsigned __int64 v15; // r12
  int v16; // ecx
  unsigned __int64 v17; // rax
  unsigned int v18; // edx
  rsize_t v19; // r9
  unsigned int *p_Source; // r8
  unsigned int v21; // esi
  unsigned int v22; // eax
  bool v23; // zf
  rsize_t v24; // r9
  unsigned int *v25; // r8
  rsize_t v26; // rdx
  unsigned __int8 *v27; // r8
  bool v28; // si
  __int64 v29; // rcx
  __int64 v31; // rax
  char v32; // dl
  unsigned __int64 v33; // rdx
  __int64 v34; // rsi
  unsigned __int64 v35; // r9
  unsigned __int8 *v36; // r8
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  __int16 v41; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+40h] [rbp-41h] BYREF
  unsigned __int16 v43; // [rsp+48h] [rbp-39h] BYREF
  char v44; // [rsp+4Ah] [rbp-37h]
  unsigned int Source; // [rsp+4Ch] [rbp-35h] BYREF
  unsigned __int16 v46; // [rsp+50h] [rbp-31h]
  void *Buf2[2]; // [rsp+58h] [rbp-29h]
  __int16 v48; // [rsp+68h] [rbp-19h] BYREF
  char v49; // [rsp+6Ah] [rbp-17h]
  unsigned int v50; // [rsp+6Ch] [rbp-15h]
  __int16 v51; // [rsp+70h] [rbp-11h]
  __int64 v52; // [rsp+78h] [rbp-9h]
  void *v53; // [rsp+80h] [rbp-1h]
  __int16 v54; // [rsp+88h] [rbp+7h] BYREF
  char v55; // [rsp+8Ah] [rbp+9h]
  int v56; // [rsp+8Ch] [rbp+Bh]
  __int16 v57; // [rsp+90h] [rbp+Fh]
  __int128 v58; // [rsp+98h] [rbp+17h]
  __int16 v59; // [rsp+D8h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v11 = (unsigned __int8 *)*((_QWORD *)this + 4);
  v12 = (unsigned __int8 *)(v6 + 10);
  v43 = *((_WORD *)this + 1);
  v13 = *((_BYTE *)this + 4);
  Source = 0;
  v46 = 0;
  LOBYTE(v59) = 0;
  v44 = v13;
  InsertionPointOrIncrement = v12;
  *(_OWORD *)Buf2 = 0;
  v14 = wil::details_abi::UsageIndexProperty::Read(
          (wil::details_abi::UsageIndexProperty *)&v43,
          &InsertionPointOrIncrement,
          v11);
  v15 = a5;
  while ( 1 )
  {
    v28 = v14;
    if ( !v14 )
    {
      v12 = InsertionPointOrIncrement;
      goto LABEL_30;
    }
    v16 = Size == v46 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v46;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v43,
                                    InsertionPointOrIncrement,
                                    a4,
                                    v15,
                                    a6);
      v12 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        LOBYTE(v59) = 1;
        goto LABEL_38;
      }
      return 1;
    }
    v12 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v17 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v18 = Source;
      if ( Source > v17 && Source != (_DWORD)v17 )
      {
        v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v18;
        if ( v44 == 1 )
        {
          v41 = v17;
          v19 = 2;
          p_Source = (unsigned int *)&v41;
          goto LABEL_15;
        }
        if ( v44 == 2 )
        {
          v19 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v19, p_Source, v19);
          v18 = Source;
        }
      }
      v12 += *((_QWORD *)this + 2) * v18;
      goto LABEL_27;
    }
    v54 = *((_WORD *)this + 3);
    v21 = 0;
    v55 = *((_BYTE *)this + 8);
    v22 = Source;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( Source )
    {
      do
      {
        v23 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v54,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v22 = Source;
        if ( v23 )
          break;
        ++v21;
      }
      while ( v21 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v22 != v21 )
    {
      Source = v21;
      if ( v44 == 1 )
      {
        v41 = v21;
        v24 = 2;
        v25 = (unsigned int *)&v41;
        v26 = 2;
      }
      else
      {
        if ( v44 != 2 )
          goto LABEL_27;
        v26 = 4;
        v25 = &Source;
        v24 = 4;
      }
      memcpy_s(Buf2[0], v26, v25, v24);
    }
LABEL_27:
    v27 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v43,
            &InsertionPointOrIncrement,
            v27);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v28 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v29 = 0;
  if ( !(_BYTE)v59 )
  {
    Source = 1;
    v46 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v43 )
      v29 = v43;
    else
      v29 = (unsigned __int16)Size + 2LL;
    if ( v44 == 1 )
    {
      v29 += 2;
    }
    else if ( v44 == 2 )
    {
      v29 += 4;
    }
  }
  v31 = *((unsigned __int16 *)this + 3);
  v32 = *((_BYTE *)this + 8);
  v48 = v31;
  v49 = v32;
  v50 = a6;
  v51 = v15;
  v52 = 0;
  v53 = a4;
  if ( !(_WORD)v31 )
    v31 = (unsigned __int16)v15 + 2LL;
  if ( v32 == 1 )
  {
    v31 += 2;
  }
  else if ( v32 == 2 )
  {
    v31 += 4;
  }
  v33 = *((_QWORD *)this + 5);
  v34 = v31 + v29;
  v35 = *((_QWORD *)this + 4);
  if ( ((v33 - v35) & -(__int64)(v35 < v33)) >= v31 + v29 )
  {
    memmove_s(&v12[v34], v33 - v34 - (_QWORD)v12, v12, v35 - (_QWORD)v12);
    v36 = (unsigned __int8 *)(v34 + *((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = v36;
    if ( !(_BYTE)v59 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v43,
        &InsertionPointOrIncrement,
        v36);
LABEL_61:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v48,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v44 )
      goto LABEL_61;
    v37 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_61;
    ++Source;
    if ( v44 == 1 )
    {
      v38 = 2;
      v59 = v37;
      v39 = 2;
      v40 = (unsigned int *)&v59;
    }
    else
    {
      if ( v44 != 2 )
        goto LABEL_61;
      v40 = &Source;
      v38 = 4;
      v39 = 4;
    }
    memcpy_s(Buf2[0], v39, v40, v38);
    goto LABEL_61;
  }
  return 0;
}

```

## disassembly

```asm
0x14001bebc  mov     rax, rsp
0x14001bebf  mov     [rax+10h], rbx
0x14001bec3  mov     [rax+18h], rsi
0x14001bec7  mov     [rax+20h], rdi
0x14001becb  push    rbp
0x14001becc  push    r12
0x14001bece  push    r13
0x14001bed0  push    r14
0x14001bed2  push    r15
0x14001bed4  lea     rbp, [rax-4Fh]
0x14001bed8  sub     rsp, 0A0h
0x14001bedf  mov     rdi, [rcx+18h]
0x14001bee3  mov     rbx, rcx
0x14001bee6  xor     ecx, ecx
0x14001bee8  mov     r13, r9
0x14001beeb  mov     r14, r8
0x14001beee  mov     r15, rdx
0x14001bef1  test    rdi, rdi
0x14001bef4  jz      loc_14001C249
0x14001befa  movzx   eax, word ptr [rbx+2]
0x14001befe  lea     rdx, [rbp+47h+var_88]; unsigned __int8 **
0x14001bf02  mov     r8, [rbx+20h]; unsigned __int8 *
0x14001bf06  add     rdi, 0Ah
0x14001bf0a  mov     [rbp+47h+var_80], ax
0x14001bf0e  xorps   xmm0, xmm0
0x14001bf11  mov     al, [rbx+4]
0x14001bf14  mov     [rbp+47h+Source], ecx
0x14001bf17  mov     [rbp+47h+var_78], cx
0x14001bf1b  mov     byte ptr [rbp+47h+arg_0], cl
0x14001bf1e  lea     rcx, [rbp+47h+var_80]; this
0x14001bf22  mov     [rbp+47h+var_7E], al
0x14001bf25  mov     [rbp+47h+var_88], rdi
0x14001bf29  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14001bf2e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14001bf33  mov     r12, [rbp+47h+arg_20]
0x14001bf37  jmp     loc_14001C08E
0x14001bf3c  movzx   ecx, [rbp+47h+var_78]
0x14001bf40  cmp     r14, rcx
0x14001bf43  jnz     short loc_14001BF5B
0x14001bf45  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14001bf49  mov     r8, r14; Size
0x14001bf4c  mov     rcx, r15; Buf1
0x14001bf4f  call    memcmp_0
0x14001bf54  mov     ecx, eax
0x14001bf56  xor     r9d, r9d
0x14001bf59  jmp     short loc_14001BF64
0x14001bf5b  movzx   eax, [rbp+47h+var_78]
0x14001bf5f  mov     ecx, r14d
0x14001bf62  sub     ecx, eax
0x14001bf64  test    ecx, ecx
0x14001bf66  js      loc_14001C113
0x14001bf6c  jz      loc_14001C0D8
0x14001bf72  mov     rdi, [rbp+47h+var_88]
0x14001bf76  mov     [rbp+47h+var_88], rdi
0x14001bf7a  cmp     [rbx+10h], r9
0x14001bf7e  jbe     short loc_14001BFEC
0x14001bf80  mov     rax, [rbx+20h]
0x14001bf84  xor     edx, edx
0x14001bf86  sub     rax, [rbx+18h]
0x14001bf8a  div     qword ptr [rbx+10h]
0x14001bf8e  mov     edx, [rbp+47h+Source]
0x14001bf91  cmp     rdx, rax
0x14001bf94  jbe     short loc_14001BFDD
0x14001bf96  cmp     edx, eax
0x14001bf98  jz      short loc_14001BFDD
0x14001bf9a  mov     edx, eax
0x14001bf9c  mov     [rbp+47h+Source], eax
0x14001bf9f  mov     al, [rbp+47h+var_7E]
0x14001bfa2  cmp     al, 1
0x14001bfa4  jnz     short loc_14001BFB9
0x14001bfa6  movzx   eax, dx
0x14001bfa9  mov     [rbp+47h+var_90], dx
0x14001bfad  mov     r9d, 2
0x14001bfb3  lea     r8, [rbp+47h+var_90]
0x14001bfb7  jmp     short loc_14001BFC7
0x14001bfb9  cmp     al, 2
0x14001bfbb  jnz     short loc_14001BFDD
0x14001bfbd  mov     r9d, 4; SourceSize
0x14001bfc3  lea     r8, [rbp+47h+Source]; Source
0x14001bfc7  mov     rcx, [rbp+47h+Buf2]; Destination
0x14001bfcb  mov     rdx, r9; DestinationSize
0x14001bfce  call    cs:__imp_memcpy_s
0x14001bfd5  nop     dword ptr [rax+rax+00h]
0x14001bfda  mov     edx, [rbp+47h+Source]
0x14001bfdd  mov     eax, edx
0x14001bfdf  imul    rax, [rbx+10h]
0x14001bfe4  add     rdi, rax
0x14001bfe7  jmp     loc_14001C079
0x14001bfec  movzx   eax, word ptr [rbx+6]
0x14001bff0  xorps   xmm0, xmm0
0x14001bff3  mov     [rbp+47h+var_40], ax
0x14001bff7  mov     esi, r9d
0x14001bffa  mov     al, [rbx+8]
0x14001bffd  mov     [rbp+47h+var_3E], al
0x14001c000  mov     eax, [rbp+47h+Source]
0x14001c003  mov     [rbp+47h+var_3C], r9d
0x14001c007  mov     [rbp+47h+var_38], r9w
0x14001c00c  movdqu  [rbp+47h+var_30], xmm0
0x14001c011  test    eax, eax
0x14001c013  jz      short loc_14001C037
0x14001c015  mov     r8, [rbx+20h]; unsigned __int8 *
0x14001c019  lea     rdx, [rbp+47h+var_88]; unsigned __int8 **
0x14001c01d  lea     rcx, [rbp+47h+var_40]; this
0x14001c021  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14001c026  test    al, al
0x14001c028  mov     eax, [rbp+47h+Source]
0x14001c02b  jz      short loc_14001C033
0x14001c02d  inc     esi
0x14001c02f  cmp     esi, eax
0x14001c031  jb      short loc_14001C015
0x14001c033  mov     rdi, [rbp+47h+var_88]
0x14001c037  cmp     eax, esi
0x14001c039  jz      short loc_14001C079
0x14001c03b  mov     al, [rbp+47h+var_7E]
0x14001c03e  mov     [rbp+47h+Source], esi
0x14001c041  cmp     al, 1
0x14001c043  jnz     short loc_14001C059
0x14001c045  mov     eax, 2
0x14001c04a  mov     [rbp+47h+var_90], si
0x14001c04e  mov     r9d, eax
0x14001c051  lea     r8, [rbp+47h+var_90]
0x14001c055  mov     edx, eax
0x14001c057  jmp     short loc_14001C069
0x14001c059  cmp     al, 2
0x14001c05b  jnz     short loc_14001C079
0x14001c05d  mov     edx, 4; DestinationSize
0x14001c062  lea     r8, [rbp+47h+Source]; Source
0x14001c066  mov     r9d, edx; SourceSize
0x14001c069  mov     rcx, [rbp+47h+Buf2]; Destination
0x14001c06d  call    cs:__imp_memcpy_s
0x14001c074  nop     dword ptr [rax+rax+00h]
0x14001c079  mov     r8, [rbx+20h]; unsigned __int8 *
0x14001c07d  lea     rdx, [rbp+47h+var_88]; unsigned __int8 **
0x14001c081  lea     rcx, [rbp+47h+var_80]; this
0x14001c085  mov     [rbp+47h+var_88], rdi
0x14001c089  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14001c08e  xor     r9d, r9d
0x14001c091  mov     sil, al
0x14001c094  test    al, al
0x14001c096  jnz     loc_14001BF3C
0x14001c09c  mov     rdi, [rbp+47h+var_88]
0x14001c0a0  mov     [rbx+20h], rdi
0x14001c0a4  mov     rcx, r9
0x14001c0a7  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14001c0ab  jnz     loc_14001C136
0x14001c0b1  movzx   eax, [rbp+47h+var_80]
0x14001c0b5  mov     [rbp+47h+Source], 1
0x14001c0bc  mov     [rbp+47h+var_78], r14w
0x14001c0c1  mov     [rbp+47h+Buf2], r9
0x14001c0c5  mov     [rbp+47h+Buf2+8], r15
0x14001c0c9  test    ax, ax
0x14001c0cc  jnz     short loc_14001C11E
0x14001c0ce  movzx   ecx, r14w
0x14001c0d2  add     rcx, 2
0x14001c0d6  jmp     short loc_14001C121
0x14001c0d8  mov     eax, [rbp+47h+arg_28]
0x14001c0db  lea     rdx, [rbp+47h+var_80]; struct wil::details_abi::UsageIndexProperty *
0x14001c0df  mov     r8, [rbp+47h+var_88]; unsigned __int8 *
0x14001c0e3  mov     r9, r13; void *
0x14001c0e6  mov     [rsp+0C0h+var_98], eax; unsigned int
0x14001c0ea  mov     rcx, rbx; this
0x14001c0ed  mov     [rsp+0C0h+var_A0], r12; unsigned __int64
0x14001c0f2  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14001c0f7  xor     r9d, r9d
0x14001c0fa  mov     [rbp+47h+var_88], rax
0x14001c0fe  mov     rdi, rax
0x14001c101  test    rax, rax
0x14001c104  jnz     short loc_14001C10D
0x14001c106  mov     al, 1
0x14001c108  jmp     loc_14001C24B
0x14001c10d  mov     byte ptr [rbp+47h+arg_0], 1
0x14001c111  jmp     short loc_14001C117
0x14001c113  mov     [rbp+47h+var_88], rdi
0x14001c117  test    sil, sil
0x14001c11a  jnz     short loc_14001C0A4
0x14001c11c  jmp     short loc_14001C0A0
0x14001c11e  mov     rcx, rax
0x14001c121  mov     al, [rbp+47h+var_7E]
0x14001c124  cmp     al, 1
0x14001c126  jnz     short loc_14001C12E
0x14001c128  add     rcx, 2
0x14001c12c  jmp     short loc_14001C136
0x14001c12e  cmp     al, 2
0x14001c130  jnz     short loc_14001C136
0x14001c132  add     rcx, 4
0x14001c136  movzx   eax, word ptr [rbx+6]
0x14001c13a  mov     dl, [rbx+8]
0x14001c13d  mov     r8d, [rbp+47h+arg_28]
0x14001c141  mov     [rbp+47h+var_60], ax
0x14001c145  mov     [rbp+47h+var_5E], dl
0x14001c148  mov     [rbp+47h+var_5C], r8d
0x14001c14c  mov     [rbp+47h+var_58], r12w
0x14001c151  mov     [rbp+47h+var_50], r9
0x14001c155  mov     [rbp+47h+var_48], r13
0x14001c159  test    ax, ax
0x14001c15c  jnz     short loc_14001C166
0x14001c15e  movzx   eax, r12w
0x14001c162  add     rax, 2
0x14001c166  cmp     dl, 1
0x14001c169  jnz     short loc_14001C171
0x14001c16b  add     rax, 2
0x14001c16f  jmp     short loc_14001C17A
0x14001c171  cmp     dl, 2
0x14001c174  jnz     short loc_14001C17A
0x14001c176  add     rax, 4
0x14001c17a  mov     rdx, [rbx+28h]
0x14001c17e  lea     rsi, [rax+rcx]
0x14001c182  mov     r9, [rbx+20h]
0x14001c186  mov     rcx, rdx
0x14001c189  sub     rcx, r9
0x14001c18c  cmp     r9, rdx
0x14001c18f  sbb     rax, rax
0x14001c192  and     rax, rcx
0x14001c195  cmp     rax, rsi
0x14001c198  jb      loc_14001C249
0x14001c19e  sub     rdx, rsi
0x14001c1a1  lea     rcx, [rsi+rdi]; Destination
0x14001c1a5  sub     rdx, rdi; DestinationSize
0x14001c1a8  sub     r9, rdi; SourceSize
0x14001c1ab  mov     r8, rdi; Source
0x14001c1ae  call    cs:__imp_memmove_s
0x14001c1b5  nop     dword ptr [rax+rax+00h]
0x14001c1ba  mov     r8, [rbx+20h]
0x14001c1be  xor     edi, edi
0x14001c1c0  add     r8, rsi; unsigned __int8 *
0x14001c1c3  mov     [rbx+20h], r8
0x14001c1c7  cmp     byte ptr [rbp+47h+arg_0], dil
0x14001c1cb  jnz     short loc_14001C1DC
0x14001c1cd  lea     rdx, [rbp+47h+var_88]; unsigned __int8 **
0x14001c1d1  lea     rcx, [rbp+47h+var_80]; this
0x14001c1d5  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14001c1da  jmp     short loc_14001C22F
0x14001c1dc  mov     cl, [rbp+47h+var_7E]
0x14001c1df  test    cl, cl
0x14001c1e1  jz      short loc_14001C22F
0x14001c1e3  mov     eax, [rbp+47h+Source]
0x14001c1e6  lea     r8d, [rax+1]
0x14001c1ea  cmp     eax, r8d
0x14001c1ed  jz      short loc_14001C22F
0x14001c1ef  mov     [rbp+47h+Source], r8d
0x14001c1f3  cmp     cl, 1
0x14001c1f6  jnz     short loc_14001C20C
0x14001c1f8  mov     r9d, 2
0x14001c1fe  mov     [rbp+47h+arg_0], r8w
0x14001c203  mov     edx, r9d
0x14001c206  lea     r8, [rbp+47h+arg_0]
0x14001c20a  jmp     short loc_14001C21F
0x14001c20c  cmp     cl, 2
0x14001c20f  jnz     short loc_14001C22F
0x14001c211  mov     eax, 4
0x14001c216  lea     r8, [rbp+47h+Source]; Source
0x14001c21a  mov     r9d, eax; SourceSize
0x14001c21d  mov     edx, eax; DestinationSize
0x14001c21f  mov     rcx, [rbp+47h+Buf2]; Destination
0x14001c223  call    cs:__imp_memcpy_s
0x14001c22a  nop     dword ptr [rax+rax+00h]
0x14001c22f  mov     r8, [rbx+20h]; unsigned __int8 *
0x14001c233  lea     rdx, [rbp+47h+var_88]; unsigned __int8 **
0x14001c237  lea     rcx, [rbp+47h+var_60]; this
0x14001c23b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14001c240  mov     byte ptr [rbx+38h], 1
0x14001c244  jmp     loc_14001C106
0x14001c249  xor     al, al
0x14001c24b  lea     r11, [rsp+0C0h+var_20]
0x14001c253  mov     rbx, [r11+38h]
0x14001c257  mov     rsi, [r11+40h]
0x14001c25b  mov     rdi, [r11+48h]
0x14001c25f  mov     rsp, r11
0x14001c262  pop     r15
0x14001c264  pop     r14
0x14001c266  pop     r13
0x14001c268  pop     r12
0x14001c26a  pop     rbp
0x14001c26b  retn
```
