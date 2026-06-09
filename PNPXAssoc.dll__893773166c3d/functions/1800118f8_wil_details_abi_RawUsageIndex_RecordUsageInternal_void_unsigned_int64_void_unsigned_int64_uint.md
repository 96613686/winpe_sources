# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800118f8`
- end: `0x180011c78`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011748`

## callees

- `0x180010dbc`
- `0x180011338`
- `0x1800118f8`
- `0x1800128b4`
- `0x180012db6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180011bd7`
- `msvcrt!memmove_s` at `0x180011bd7`
- `msvcrt!memcpy_s` at `0x180011a03`
- `msvcrt!memcpy_s` at `0x180011a9c`
- `msvcrt!memcpy_s` at `0x180011c42`
- `msvcrt!memcpy_s` at `0x180011a03`
- `msvcrt!memcpy_s` at `0x180011a9c`
- `msvcrt!memcpy_s` at `0x180011c42`

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
0x1800118f8  push    rbp
0x1800118fa  push    rbx
0x1800118fb  push    rsi
0x1800118fc  push    rdi
0x1800118fd  push    r12
0x1800118ff  push    r13
0x180011901  push    r14
0x180011903  push    r15
0x180011905  lea     rbp, [rsp-0Fh]
0x18001190a  sub     rsp, 0A8h
0x180011911  mov     rbx, [rcx+18h]
0x180011915  mov     rdi, rcx
0x180011918  xor     ecx, ecx
0x18001191a  mov     r13, r9
0x18001191d  mov     r14, r8
0x180011920  mov     r15, rdx
0x180011923  test    rbx, rbx
0x180011926  jz      loc_180011C62
0x18001192c  movzx   eax, word ptr [rdi+2]
0x180011930  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180011934  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011938  add     rbx, 0Ah
0x18001193c  mov     [rbp+47h+var_A0], ax
0x180011940  xorps   xmm0, xmm0
0x180011943  mov     al, [rdi+4]
0x180011946  mov     [rbp+47h+Source], ecx
0x180011949  mov     [rbp+47h+var_98], cx
0x18001194d  mov     byte ptr [rbp+47h+arg_0], cl
0x180011950  lea     rcx, [rbp+47h+var_A0]; this
0x180011954  mov     [rbp+47h+var_9E], al
0x180011957  mov     [rbp+47h+var_A8], rbx
0x18001195b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180011960  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011965  mov     r12, [rbp+47h+arg_20]
0x180011969  jmp     loc_180011AB7
0x18001196e  movzx   eax, [rbp+47h+var_98]
0x180011972  cmp     r14, rax
0x180011975  jnz     short loc_18001198D
0x180011977  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18001197b  mov     r8, r14; Size
0x18001197e  mov     rcx, r15; Buf1
0x180011981  call    memcmp_0
0x180011986  mov     ecx, eax
0x180011988  xor     r9d, r9d
0x18001198b  jmp     short loc_180011996
0x18001198d  movzx   eax, [rbp+47h+var_98]
0x180011991  mov     ecx, r14d
0x180011994  sub     ecx, eax
0x180011996  test    ecx, ecx
0x180011998  js      loc_180011B3C
0x18001199e  jz      loc_180011B01
0x1800119a4  mov     rbx, [rbp+47h+var_A8]
0x1800119a8  mov     [rbp+47h+var_A8], rbx
0x1800119ac  cmp     [rdi+10h], r9
0x1800119b0  jbe     short loc_180011A1B
0x1800119b2  mov     rax, [rdi+20h]
0x1800119b6  xor     edx, edx
0x1800119b8  sub     rax, [rdi+18h]
0x1800119bc  mov     rsi, rbx
0x1800119bf  div     qword ptr [rdi+10h]
0x1800119c3  mov     edx, [rbp+47h+Source]
0x1800119c6  cmp     rdx, rax
0x1800119c9  jbe     short loc_180011A0C
0x1800119cb  cmp     edx, eax
0x1800119cd  jz      short loc_180011A0C
0x1800119cf  mov     edx, eax
0x1800119d1  mov     [rbp+47h+Source], eax
0x1800119d4  mov     al, [rbp+47h+var_9E]
0x1800119d7  cmp     al, 1
0x1800119d9  jnz     short loc_1800119EE
0x1800119db  movzx   eax, dx
0x1800119de  mov     [rbp+47h+var_B0], dx
0x1800119e2  mov     r9d, 2
0x1800119e8  lea     r8, [rbp+47h+var_B0]
0x1800119ec  jmp     short loc_1800119FC
0x1800119ee  cmp     al, 2
0x1800119f0  jnz     short loc_180011A0C
0x1800119f2  mov     r9d, 4; SourceSize
0x1800119f8  lea     r8, [rbp+47h+Source]; Source
0x1800119fc  mov     rcx, [rbp+47h+Buf2]; Destination
0x180011a00  mov     rdx, r9; DestinationSize
0x180011a03  call    cs:__imp_memcpy_s
0x180011a09  mov     edx, [rbp+47h+Source]
0x180011a0c  mov     ebx, edx
0x180011a0e  imul    rbx, [rdi+10h]
0x180011a13  add     rbx, rsi
0x180011a16  jmp     loc_180011AA2
0x180011a1b  movzx   eax, word ptr [rdi+6]
0x180011a1f  xorps   xmm0, xmm0
0x180011a22  mov     [rbp+47h+var_60], ax
0x180011a26  mov     esi, r9d
0x180011a29  mov     al, [rdi+8]
0x180011a2c  mov     [rbp+47h+var_5E], al
0x180011a2f  mov     eax, [rbp+47h+Source]
0x180011a32  mov     [rbp+47h+var_5C], r9d
0x180011a36  mov     [rbp+47h+var_58], r9w
0x180011a3b  movdqu  [rbp+47h+var_50], xmm0
0x180011a40  test    eax, eax
0x180011a42  jz      short loc_180011A66
0x180011a44  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011a48  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180011a4c  lea     rcx, [rbp+47h+var_60]; this
0x180011a50  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011a55  test    al, al
0x180011a57  mov     eax, [rbp+47h+Source]
0x180011a5a  jz      short loc_180011A62
0x180011a5c  inc     esi
0x180011a5e  cmp     esi, eax
0x180011a60  jb      short loc_180011A44
0x180011a62  mov     rbx, [rbp+47h+var_A8]
0x180011a66  cmp     eax, esi
0x180011a68  jz      short loc_180011AA2
0x180011a6a  mov     al, [rbp+47h+var_9E]
0x180011a6d  mov     [rbp+47h+Source], esi
0x180011a70  cmp     al, 1
0x180011a72  jnz     short loc_180011A88
0x180011a74  mov     eax, 2
0x180011a79  mov     [rbp+47h+var_B0], si
0x180011a7d  mov     r9d, eax
0x180011a80  lea     r8, [rbp+47h+var_B0]
0x180011a84  mov     edx, eax
0x180011a86  jmp     short loc_180011A98
0x180011a88  cmp     al, 2
0x180011a8a  jnz     short loc_180011AA2
0x180011a8c  mov     edx, 4; DestinationSize
0x180011a91  lea     r8, [rbp+47h+Source]; Source
0x180011a95  mov     r9d, edx; SourceSize
0x180011a98  mov     rcx, [rbp+47h+Buf2]; Destination
0x180011a9c  call    cs:__imp_memcpy_s
0x180011aa2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011aa6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180011aaa  lea     rcx, [rbp+47h+var_A0]; this
0x180011aae  mov     [rbp+47h+var_A8], rbx
0x180011ab2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011ab7  xor     r9d, r9d
0x180011aba  mov     sil, al
0x180011abd  test    al, al
0x180011abf  jnz     loc_18001196E
0x180011ac5  mov     rbx, [rbp+47h+var_A8]
0x180011ac9  mov     [rdi+20h], rbx
0x180011acd  mov     rcx, r9
0x180011ad0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180011ad4  jnz     loc_180011B5F
0x180011ada  movzx   eax, [rbp+47h+var_A0]
0x180011ade  mov     [rbp+47h+Source], 1
0x180011ae5  mov     [rbp+47h+var_98], r14w
0x180011aea  mov     [rbp+47h+Buf2], r9
0x180011aee  mov     [rbp+47h+Buf2+8], r15
0x180011af2  test    ax, ax
0x180011af5  jnz     short loc_180011B47
0x180011af7  movzx   ecx, r14w
0x180011afb  add     rcx, 2
0x180011aff  jmp     short loc_180011B4A
0x180011b01  mov     eax, [rbp+47h+arg_28]
0x180011b04  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180011b08  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180011b0c  mov     r9, r13; void *
0x180011b0f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180011b13  mov     rcx, rdi; this
0x180011b16  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180011b1b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180011b20  xor     r9d, r9d
0x180011b23  mov     [rbp+47h+var_A8], rax
0x180011b27  mov     rbx, rax
0x180011b2a  test    rax, rax
0x180011b2d  jnz     short loc_180011B36
0x180011b2f  mov     al, 1
0x180011b31  jmp     loc_180011C64
0x180011b36  mov     byte ptr [rbp+47h+arg_0], 1
0x180011b3a  jmp     short loc_180011B40
0x180011b3c  mov     [rbp+47h+var_A8], rbx
0x180011b40  test    sil, sil
0x180011b43  jnz     short loc_180011ACD
0x180011b45  jmp     short loc_180011AC9
0x180011b47  mov     rcx, rax
0x180011b4a  mov     al, [rbp+47h+var_9E]
0x180011b4d  cmp     al, 1
0x180011b4f  jnz     short loc_180011B57
0x180011b51  add     rcx, 2
0x180011b55  jmp     short loc_180011B5F
0x180011b57  cmp     al, 2
0x180011b59  jnz     short loc_180011B5F
0x180011b5b  add     rcx, 4
0x180011b5f  movzx   eax, word ptr [rdi+6]
0x180011b63  mov     dl, [rdi+8]
0x180011b66  mov     r8d, [rbp+47h+arg_28]
0x180011b6a  mov     [rbp+47h+var_80], ax
0x180011b6e  mov     [rbp+47h+var_7E], dl
0x180011b71  mov     [rbp+47h+var_7C], r8d
0x180011b75  mov     [rbp+47h+var_78], r12w
0x180011b7a  mov     [rbp+47h+var_70], r9
0x180011b7e  mov     [rbp+47h+var_68], r13
0x180011b82  test    ax, ax
0x180011b85  jnz     short loc_180011B8F
0x180011b87  movzx   eax, r12w
0x180011b8b  add     rax, 2
0x180011b8f  cmp     dl, 1
0x180011b92  jnz     short loc_180011B9A
0x180011b94  add     rax, 2
0x180011b98  jmp     short loc_180011BA3
0x180011b9a  cmp     dl, 2
0x180011b9d  jnz     short loc_180011BA3
0x180011b9f  add     rax, 4
0x180011ba3  mov     rdx, [rdi+28h]
0x180011ba7  lea     rsi, [rax+rcx]
0x180011bab  mov     r9, [rdi+20h]
0x180011baf  mov     rcx, rdx
0x180011bb2  sub     rcx, r9
0x180011bb5  cmp     r9, rdx
0x180011bb8  sbb     rax, rax
0x180011bbb  and     rax, rcx
0x180011bbe  cmp     rax, rsi
0x180011bc1  jb      loc_180011C62
0x180011bc7  sub     rdx, rsi
0x180011bca  lea     rcx, [rsi+rbx]; Destination
0x180011bce  sub     rdx, rbx; DestinationSize
0x180011bd1  sub     r9, rbx; SourceSize
0x180011bd4  mov     r8, rbx; Source
0x180011bd7  call    cs:__imp_memmove_s
0x180011bdd  add     [rdi+20h], rsi
0x180011be1  xor     ebx, ebx
0x180011be3  cmp     byte ptr [rbp+47h+arg_0], bl
0x180011be6  jnz     short loc_180011BFB
0x180011be8  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011bec  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180011bf0  lea     rcx, [rbp+47h+var_A0]; this
0x180011bf4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180011bf9  jmp     short loc_180011C48
0x180011bfb  mov     cl, [rbp+47h+var_9E]
0x180011bfe  test    cl, cl
0x180011c00  jz      short loc_180011C48
0x180011c02  mov     eax, [rbp+47h+Source]
0x180011c05  lea     r8d, [rax+1]
0x180011c09  cmp     eax, r8d
0x180011c0c  jz      short loc_180011C48
0x180011c0e  mov     [rbp+47h+Source], r8d
0x180011c12  cmp     cl, 1
0x180011c15  jnz     short loc_180011C2B
0x180011c17  mov     r9d, 2
0x180011c1d  mov     [rbp+47h+arg_0], r8w
0x180011c22  mov     edx, r9d
0x180011c25  lea     r8, [rbp+47h+arg_0]
0x180011c29  jmp     short loc_180011C3E
0x180011c2b  cmp     cl, 2
0x180011c2e  jnz     short loc_180011C48
0x180011c30  mov     eax, 4
0x180011c35  lea     r8, [rbp+47h+Source]; Source
0x180011c39  mov     r9d, eax; SourceSize
0x180011c3c  mov     edx, eax; DestinationSize
0x180011c3e  mov     rcx, [rbp+47h+Buf2]; Destination
0x180011c42  call    cs:__imp_memcpy_s
0x180011c48  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011c4c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180011c50  lea     rcx, [rbp+47h+var_80]; this
0x180011c54  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180011c59  mov     byte ptr [rdi+38h], 1
0x180011c5d  jmp     loc_180011B2F
0x180011c62  xor     al, al
0x180011c64  add     rsp, 0A8h
0x180011c6b  pop     r15
0x180011c6d  pop     r14
0x180011c6f  pop     r13
0x180011c71  pop     r12
0x180011c73  pop     rdi
0x180011c74  pop     rsi
0x180011c75  pop     rbx
0x180011c76  pop     rbp
0x180011c77  retn
```
