# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000af54`
- end: `0x18000b2d4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ad98`

## callees

- `0x180009d2c`
- `0x18000a980`
- `0x18000af54`
- `0x18000c324`
- `0x180021816`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000b233`
- `msvcrt!memmove_s` at `0x18000b233`
- `msvcrt!memcpy_s` at `0x18000b05f`
- `msvcrt!memcpy_s` at `0x18000b0f8`
- `msvcrt!memcpy_s` at `0x18000b29e`
- `msvcrt!memcpy_s` at `0x18000b05f`
- `msvcrt!memcpy_s` at `0x18000b0f8`
- `msvcrt!memcpy_s` at `0x18000b29e`

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
  __int64 v6; // rbx
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rbx
  char v13; // al
  bool v14; // al
  unsigned __int64 v15; // r12
  int v16; // ecx
  unsigned __int8 *v17; // rsi
  unsigned __int64 v18; // rax
  unsigned int v19; // edx
  rsize_t v20; // r9
  unsigned int *p_Source; // r8
  unsigned int v22; // esi
  unsigned int v23; // eax
  bool v24; // zf
  rsize_t v25; // r9
  unsigned int *v26; // r8
  rsize_t v27; // rdx
  unsigned __int8 *v28; // r8
  bool v29; // si
  __int64 v30; // rcx
  __int64 v32; // rax
  char v33; // dl
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  unsigned __int64 v36; // r9
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  __int16 v41; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 v43; // [rsp+40h] [rbp-59h] BYREF
  char v44; // [rsp+42h] [rbp-57h]
  unsigned int Source; // [rsp+44h] [rbp-55h] BYREF
  unsigned __int16 v46; // [rsp+48h] [rbp-51h]
  void *Buf2[2]; // [rsp+50h] [rbp-49h]
  __int16 v48; // [rsp+60h] [rbp-39h] BYREF
  char v49; // [rsp+62h] [rbp-37h]
  unsigned int v50; // [rsp+64h] [rbp-35h]
  __int16 v51; // [rsp+68h] [rbp-31h]
  __int64 v52; // [rsp+70h] [rbp-29h]
  void *v53; // [rsp+78h] [rbp-21h]
  __int16 v54; // [rsp+80h] [rbp-19h] BYREF
  char v55; // [rsp+82h] [rbp-17h]
  int v56; // [rsp+84h] [rbp-15h]
  __int16 v57; // [rsp+88h] [rbp-11h]
  __int128 v58; // [rsp+90h] [rbp-9h]
  __int16 v59; // [rsp+F0h] [rbp+57h] BYREF

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
    v29 = v14;
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
      v17 = InsertionPointOrIncrement;
      v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v19 = Source;
      if ( Source > v18 && Source != (_DWORD)v18 )
      {
        v19 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v19;
        if ( v44 == 1 )
        {
          v41 = v18;
          v20 = 2;
          p_Source = (unsigned int *)&v41;
          goto LABEL_15;
        }
        if ( v44 == 2 )
        {
          v20 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v20, p_Source, v20);
          v19 = Source;
        }
      }
      v12 = &v17[*((_QWORD *)this + 2) * v19];
      goto LABEL_27;
    }
    v54 = *((_WORD *)this + 3);
    v22 = 0;
    v55 = *((_BYTE *)this + 8);
    v23 = Source;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( Source )
    {
      do
      {
        v24 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v54,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v23 = Source;
        if ( v24 )
          break;
        ++v22;
      }
      while ( v22 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v23 != v22 )
    {
      Source = v22;
      if ( v44 == 1 )
      {
        v41 = v22;
        v25 = 2;
        v26 = (unsigned int *)&v41;
        v27 = 2;
      }
      else
      {
        if ( v44 != 2 )
          goto LABEL_27;
        v27 = 4;
        v26 = &Source;
        v25 = 4;
      }
      memcpy_s(Buf2[0], v27, v26, v25);
    }
LABEL_27:
    v28 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v43,
            &InsertionPointOrIncrement,
            v28);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v29 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v30 = 0;
  if ( !(_BYTE)v59 )
  {
    Source = 1;
    v46 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v43 )
      v30 = v43;
    else
      v30 = (unsigned __int16)Size + 2LL;
    if ( v44 == 1 )
    {
      v30 += 2;
    }
    else if ( v44 == 2 )
    {
      v30 += 4;
    }
  }
  v32 = *((unsigned __int16 *)this + 3);
  v33 = *((_BYTE *)this + 8);
  v48 = v32;
  v49 = v33;
  v50 = a6;
  v51 = v15;
  v52 = 0;
  v53 = a4;
  if ( !(_WORD)v32 )
    v32 = (unsigned __int16)v15 + 2LL;
  if ( v33 == 1 )
  {
    v32 += 2;
  }
  else if ( v33 == 2 )
  {
    v32 += 4;
  }
  v34 = *((_QWORD *)this + 5);
  v35 = v32 + v30;
  v36 = *((_QWORD *)this + 4);
  if ( ((v34 - v36) & -(__int64)(v36 < v34)) >= v32 + v30 )
  {
    memmove_s(&v12[v35], v34 - v35 - (_QWORD)v12, v12, v36 - (_QWORD)v12);
    *((_QWORD *)this + 4) += v35;
    if ( !(_BYTE)v59 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v43,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
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
0x18000af54  push    rbp
0x18000af56  push    rbx
0x18000af57  push    rsi
0x18000af58  push    rdi
0x18000af59  push    r12
0x18000af5b  push    r13
0x18000af5d  push    r14
0x18000af5f  push    r15
0x18000af61  lea     rbp, [rsp-0Fh]
0x18000af66  sub     rsp, 0A8h
0x18000af6d  mov     rbx, [rcx+18h]
0x18000af71  mov     rdi, rcx
0x18000af74  xor     ecx, ecx
0x18000af76  mov     r13, r9
0x18000af79  mov     r14, r8
0x18000af7c  mov     r15, rdx
0x18000af7f  test    rbx, rbx
0x18000af82  jz      loc_18000B2BE
0x18000af88  movzx   eax, word ptr [rdi+2]
0x18000af8c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000af90  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000af94  add     rbx, 0Ah
0x18000af98  mov     [rbp+47h+var_A0], ax
0x18000af9c  xorps   xmm0, xmm0
0x18000af9f  mov     al, [rdi+4]
0x18000afa2  mov     [rbp+47h+Source], ecx
0x18000afa5  mov     [rbp+47h+var_98], cx
0x18000afa9  mov     byte ptr [rbp+47h+arg_0], cl
0x18000afac  lea     rcx, [rbp+47h+var_A0]; this
0x18000afb0  mov     [rbp+47h+var_9E], al
0x18000afb3  mov     [rbp+47h+var_A8], rbx
0x18000afb7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000afbc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000afc1  mov     r12, [rbp+47h+arg_20]
0x18000afc5  jmp     loc_18000B113
0x18000afca  movzx   eax, [rbp+47h+var_98]
0x18000afce  cmp     r14, rax
0x18000afd1  jnz     short loc_18000AFE9
0x18000afd3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000afd7  mov     r8, r14; Size
0x18000afda  mov     rcx, r15; Buf1
0x18000afdd  call    memcmp_0
0x18000afe2  mov     ecx, eax
0x18000afe4  xor     r9d, r9d
0x18000afe7  jmp     short loc_18000AFF2
0x18000afe9  movzx   eax, [rbp+47h+var_98]
0x18000afed  mov     ecx, r14d
0x18000aff0  sub     ecx, eax
0x18000aff2  test    ecx, ecx
0x18000aff4  js      loc_18000B198
0x18000affa  jz      loc_18000B15D
0x18000b000  mov     rbx, [rbp+47h+var_A8]
0x18000b004  mov     [rbp+47h+var_A8], rbx
0x18000b008  cmp     [rdi+10h], r9
0x18000b00c  jbe     short loc_18000B077
0x18000b00e  mov     rax, [rdi+20h]
0x18000b012  xor     edx, edx
0x18000b014  sub     rax, [rdi+18h]
0x18000b018  mov     rsi, rbx
0x18000b01b  div     qword ptr [rdi+10h]
0x18000b01f  mov     edx, [rbp+47h+Source]
0x18000b022  cmp     rdx, rax
0x18000b025  jbe     short loc_18000B068
0x18000b027  cmp     edx, eax
0x18000b029  jz      short loc_18000B068
0x18000b02b  mov     edx, eax
0x18000b02d  mov     [rbp+47h+Source], eax
0x18000b030  mov     al, [rbp+47h+var_9E]
0x18000b033  cmp     al, 1
0x18000b035  jnz     short loc_18000B04A
0x18000b037  movzx   eax, dx
0x18000b03a  mov     [rbp+47h+var_B0], dx
0x18000b03e  mov     r9d, 2
0x18000b044  lea     r8, [rbp+47h+var_B0]
0x18000b048  jmp     short loc_18000B058
0x18000b04a  cmp     al, 2
0x18000b04c  jnz     short loc_18000B068
0x18000b04e  mov     r9d, 4; SourceSize
0x18000b054  lea     r8, [rbp+47h+Source]; Source
0x18000b058  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b05c  mov     rdx, r9; DestinationSize
0x18000b05f  call    cs:__imp_memcpy_s
0x18000b065  mov     edx, [rbp+47h+Source]
0x18000b068  mov     ebx, edx
0x18000b06a  imul    rbx, [rdi+10h]
0x18000b06f  add     rbx, rsi
0x18000b072  jmp     loc_18000B0FE
0x18000b077  movzx   eax, word ptr [rdi+6]
0x18000b07b  xorps   xmm0, xmm0
0x18000b07e  mov     [rbp+47h+var_60], ax
0x18000b082  mov     esi, r9d
0x18000b085  mov     al, [rdi+8]
0x18000b088  mov     [rbp+47h+var_5E], al
0x18000b08b  mov     eax, [rbp+47h+Source]
0x18000b08e  mov     [rbp+47h+var_5C], r9d
0x18000b092  mov     [rbp+47h+var_58], r9w
0x18000b097  movdqu  [rbp+47h+var_50], xmm0
0x18000b09c  test    eax, eax
0x18000b09e  jz      short loc_18000B0C2
0x18000b0a0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b0a4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b0a8  lea     rcx, [rbp+47h+var_60]; this
0x18000b0ac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b0b1  test    al, al
0x18000b0b3  mov     eax, [rbp+47h+Source]
0x18000b0b6  jz      short loc_18000B0BE
0x18000b0b8  inc     esi
0x18000b0ba  cmp     esi, eax
0x18000b0bc  jb      short loc_18000B0A0
0x18000b0be  mov     rbx, [rbp+47h+var_A8]
0x18000b0c2  cmp     eax, esi
0x18000b0c4  jz      short loc_18000B0FE
0x18000b0c6  mov     al, [rbp+47h+var_9E]
0x18000b0c9  mov     [rbp+47h+Source], esi
0x18000b0cc  cmp     al, 1
0x18000b0ce  jnz     short loc_18000B0E4
0x18000b0d0  mov     eax, 2
0x18000b0d5  mov     [rbp+47h+var_B0], si
0x18000b0d9  mov     r9d, eax
0x18000b0dc  lea     r8, [rbp+47h+var_B0]
0x18000b0e0  mov     edx, eax
0x18000b0e2  jmp     short loc_18000B0F4
0x18000b0e4  cmp     al, 2
0x18000b0e6  jnz     short loc_18000B0FE
0x18000b0e8  mov     edx, 4; DestinationSize
0x18000b0ed  lea     r8, [rbp+47h+Source]; Source
0x18000b0f1  mov     r9d, edx; SourceSize
0x18000b0f4  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b0f8  call    cs:__imp_memcpy_s
0x18000b0fe  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b102  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b106  lea     rcx, [rbp+47h+var_A0]; this
0x18000b10a  mov     [rbp+47h+var_A8], rbx
0x18000b10e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b113  xor     r9d, r9d
0x18000b116  mov     sil, al
0x18000b119  test    al, al
0x18000b11b  jnz     loc_18000AFCA
0x18000b121  mov     rbx, [rbp+47h+var_A8]
0x18000b125  mov     [rdi+20h], rbx
0x18000b129  mov     rcx, r9
0x18000b12c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000b130  jnz     loc_18000B1BB
0x18000b136  movzx   eax, [rbp+47h+var_A0]
0x18000b13a  mov     [rbp+47h+Source], 1
0x18000b141  mov     [rbp+47h+var_98], r14w
0x18000b146  mov     [rbp+47h+Buf2], r9
0x18000b14a  mov     [rbp+47h+Buf2+8], r15
0x18000b14e  test    ax, ax
0x18000b151  jnz     short loc_18000B1A3
0x18000b153  movzx   ecx, r14w
0x18000b157  add     rcx, 2
0x18000b15b  jmp     short loc_18000B1A6
0x18000b15d  mov     eax, [rbp+47h+arg_28]
0x18000b160  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000b164  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000b168  mov     r9, r13; void *
0x18000b16b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000b16f  mov     rcx, rdi; this
0x18000b172  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000b177  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000b17c  xor     r9d, r9d
0x18000b17f  mov     [rbp+47h+var_A8], rax
0x18000b183  mov     rbx, rax
0x18000b186  test    rax, rax
0x18000b189  jnz     short loc_18000B192
0x18000b18b  mov     al, 1
0x18000b18d  jmp     loc_18000B2C0
0x18000b192  mov     byte ptr [rbp+47h+arg_0], 1
0x18000b196  jmp     short loc_18000B19C
0x18000b198  mov     [rbp+47h+var_A8], rbx
0x18000b19c  test    sil, sil
0x18000b19f  jnz     short loc_18000B129
0x18000b1a1  jmp     short loc_18000B125
0x18000b1a3  mov     rcx, rax
0x18000b1a6  mov     al, [rbp+47h+var_9E]
0x18000b1a9  cmp     al, 1
0x18000b1ab  jnz     short loc_18000B1B3
0x18000b1ad  add     rcx, 2
0x18000b1b1  jmp     short loc_18000B1BB
0x18000b1b3  cmp     al, 2
0x18000b1b5  jnz     short loc_18000B1BB
0x18000b1b7  add     rcx, 4
0x18000b1bb  movzx   eax, word ptr [rdi+6]
0x18000b1bf  mov     dl, [rdi+8]
0x18000b1c2  mov     r8d, [rbp+47h+arg_28]
0x18000b1c6  mov     [rbp+47h+var_80], ax
0x18000b1ca  mov     [rbp+47h+var_7E], dl
0x18000b1cd  mov     [rbp+47h+var_7C], r8d
0x18000b1d1  mov     [rbp+47h+var_78], r12w
0x18000b1d6  mov     [rbp+47h+var_70], r9
0x18000b1da  mov     [rbp+47h+var_68], r13
0x18000b1de  test    ax, ax
0x18000b1e1  jnz     short loc_18000B1EB
0x18000b1e3  movzx   eax, r12w
0x18000b1e7  add     rax, 2
0x18000b1eb  cmp     dl, 1
0x18000b1ee  jnz     short loc_18000B1F6
0x18000b1f0  add     rax, 2
0x18000b1f4  jmp     short loc_18000B1FF
0x18000b1f6  cmp     dl, 2
0x18000b1f9  jnz     short loc_18000B1FF
0x18000b1fb  add     rax, 4
0x18000b1ff  mov     rdx, [rdi+28h]
0x18000b203  lea     rsi, [rax+rcx]
0x18000b207  mov     r9, [rdi+20h]
0x18000b20b  mov     rcx, rdx
0x18000b20e  sub     rcx, r9
0x18000b211  cmp     r9, rdx
0x18000b214  sbb     rax, rax
0x18000b217  and     rax, rcx
0x18000b21a  cmp     rax, rsi
0x18000b21d  jb      loc_18000B2BE
0x18000b223  sub     rdx, rsi
0x18000b226  lea     rcx, [rsi+rbx]; Destination
0x18000b22a  sub     rdx, rbx; DestinationSize
0x18000b22d  sub     r9, rbx; SourceSize
0x18000b230  mov     r8, rbx; Source
0x18000b233  call    cs:__imp_memmove_s
0x18000b239  add     [rdi+20h], rsi
0x18000b23d  xor     ebx, ebx
0x18000b23f  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000b242  jnz     short loc_18000B257
0x18000b244  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b248  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b24c  lea     rcx, [rbp+47h+var_A0]; this
0x18000b250  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b255  jmp     short loc_18000B2A4
0x18000b257  mov     cl, [rbp+47h+var_9E]
0x18000b25a  test    cl, cl
0x18000b25c  jz      short loc_18000B2A4
0x18000b25e  mov     eax, [rbp+47h+Source]
0x18000b261  lea     r8d, [rax+1]
0x18000b265  cmp     eax, r8d
0x18000b268  jz      short loc_18000B2A4
0x18000b26a  mov     [rbp+47h+Source], r8d
0x18000b26e  cmp     cl, 1
0x18000b271  jnz     short loc_18000B287
0x18000b273  mov     r9d, 2
0x18000b279  mov     [rbp+47h+arg_0], r8w
0x18000b27e  mov     edx, r9d
0x18000b281  lea     r8, [rbp+47h+arg_0]
0x18000b285  jmp     short loc_18000B29A
0x18000b287  cmp     cl, 2
0x18000b28a  jnz     short loc_18000B2A4
0x18000b28c  mov     eax, 4
0x18000b291  lea     r8, [rbp+47h+Source]; Source
0x18000b295  mov     r9d, eax; SourceSize
0x18000b298  mov     edx, eax; DestinationSize
0x18000b29a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b29e  call    cs:__imp_memcpy_s
0x18000b2a4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b2a8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b2ac  lea     rcx, [rbp+47h+var_80]; this
0x18000b2b0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b2b5  mov     byte ptr [rdi+38h], 1
0x18000b2b9  jmp     loc_18000B18B
0x18000b2be  xor     al, al
0x18000b2c0  add     rsp, 0A8h
0x18000b2c7  pop     r15
0x18000b2c9  pop     r14
0x18000b2cb  pop     r13
0x18000b2cd  pop     r12
0x18000b2cf  pop     rdi
0x18000b2d0  pop     rsi
0x18000b2d1  pop     rbx
0x18000b2d2  pop     rbp
0x18000b2d3  retn
```
