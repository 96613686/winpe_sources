# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18002cbf8`
- end: `0x18002cf78`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002ca48`

## callees

- `0x180026937`
- `0x18002a0ec`
- `0x18002c3c8`
- `0x18002cbf8`
- `0x18002fce4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002ced7`
- `msvcrt!memmove_s` at `0x18002ced7`
- `msvcrt!memcpy_s` at `0x18002cd03`
- `msvcrt!memcpy_s` at `0x18002cd9c`
- `msvcrt!memcpy_s` at `0x18002cf42`
- `msvcrt!memcpy_s` at `0x18002cd03`
- `msvcrt!memcpy_s` at `0x18002cd9c`
- `msvcrt!memcpy_s` at `0x18002cf42`

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
0x18002cbf8  push    rbp
0x18002cbfa  push    rbx
0x18002cbfb  push    rsi
0x18002cbfc  push    rdi
0x18002cbfd  push    r12
0x18002cbff  push    r13
0x18002cc01  push    r14
0x18002cc03  push    r15
0x18002cc05  lea     rbp, [rsp-0Fh]
0x18002cc0a  sub     rsp, 0A8h
0x18002cc11  mov     rbx, [rcx+18h]
0x18002cc15  mov     rdi, rcx
0x18002cc18  xor     ecx, ecx
0x18002cc1a  mov     r13, r9
0x18002cc1d  mov     r14, r8
0x18002cc20  mov     r15, rdx
0x18002cc23  test    rbx, rbx
0x18002cc26  jz      loc_18002CF62
0x18002cc2c  movzx   eax, word ptr [rdi+2]
0x18002cc30  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002cc34  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002cc38  add     rbx, 0Ah
0x18002cc3c  mov     [rbp+47h+var_A0], ax
0x18002cc40  xorps   xmm0, xmm0
0x18002cc43  mov     al, [rdi+4]
0x18002cc46  mov     [rbp+47h+Source], ecx
0x18002cc49  mov     [rbp+47h+var_98], cx
0x18002cc4d  mov     byte ptr [rbp+47h+arg_0], cl
0x18002cc50  lea     rcx, [rbp+47h+var_A0]; this
0x18002cc54  mov     [rbp+47h+var_9E], al
0x18002cc57  mov     [rbp+47h+var_A8], rbx
0x18002cc5b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18002cc60  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002cc65  mov     r12, [rbp+47h+arg_20]
0x18002cc69  jmp     loc_18002CDB7
0x18002cc6e  movzx   eax, [rbp+47h+var_98]
0x18002cc72  cmp     r14, rax
0x18002cc75  jnz     short loc_18002CC8D
0x18002cc77  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18002cc7b  mov     r8, r14; Size
0x18002cc7e  mov     rcx, r15; Buf1
0x18002cc81  call    memcmp_0
0x18002cc86  mov     ecx, eax
0x18002cc88  xor     r9d, r9d
0x18002cc8b  jmp     short loc_18002CC96
0x18002cc8d  movzx   eax, [rbp+47h+var_98]
0x18002cc91  mov     ecx, r14d
0x18002cc94  sub     ecx, eax
0x18002cc96  test    ecx, ecx
0x18002cc98  js      loc_18002CE3C
0x18002cc9e  jz      loc_18002CE01
0x18002cca4  mov     rbx, [rbp+47h+var_A8]
0x18002cca8  mov     [rbp+47h+var_A8], rbx
0x18002ccac  cmp     [rdi+10h], r9
0x18002ccb0  jbe     short loc_18002CD1B
0x18002ccb2  mov     rax, [rdi+20h]
0x18002ccb6  xor     edx, edx
0x18002ccb8  sub     rax, [rdi+18h]
0x18002ccbc  mov     rsi, rbx
0x18002ccbf  div     qword ptr [rdi+10h]
0x18002ccc3  mov     edx, [rbp+47h+Source]
0x18002ccc6  cmp     rdx, rax
0x18002ccc9  jbe     short loc_18002CD0C
0x18002cccb  cmp     edx, eax
0x18002cccd  jz      short loc_18002CD0C
0x18002cccf  mov     edx, eax
0x18002ccd1  mov     [rbp+47h+Source], eax
0x18002ccd4  mov     al, [rbp+47h+var_9E]
0x18002ccd7  cmp     al, 1
0x18002ccd9  jnz     short loc_18002CCEE
0x18002ccdb  movzx   eax, dx
0x18002ccde  mov     [rbp+47h+var_B0], dx
0x18002cce2  mov     r9d, 2
0x18002cce8  lea     r8, [rbp+47h+var_B0]
0x18002ccec  jmp     short loc_18002CCFC
0x18002ccee  cmp     al, 2
0x18002ccf0  jnz     short loc_18002CD0C
0x18002ccf2  mov     r9d, 4; SourceSize
0x18002ccf8  lea     r8, [rbp+47h+Source]; Source
0x18002ccfc  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002cd00  mov     rdx, r9; DestinationSize
0x18002cd03  call    cs:__imp_memcpy_s
0x18002cd09  mov     edx, [rbp+47h+Source]
0x18002cd0c  mov     ebx, edx
0x18002cd0e  imul    rbx, [rdi+10h]
0x18002cd13  add     rbx, rsi
0x18002cd16  jmp     loc_18002CDA2
0x18002cd1b  movzx   eax, word ptr [rdi+6]
0x18002cd1f  xorps   xmm0, xmm0
0x18002cd22  mov     [rbp+47h+var_60], ax
0x18002cd26  mov     esi, r9d
0x18002cd29  mov     al, [rdi+8]
0x18002cd2c  mov     [rbp+47h+var_5E], al
0x18002cd2f  mov     eax, [rbp+47h+Source]
0x18002cd32  mov     [rbp+47h+var_5C], r9d
0x18002cd36  mov     [rbp+47h+var_58], r9w
0x18002cd3b  movdqu  [rbp+47h+var_50], xmm0
0x18002cd40  test    eax, eax
0x18002cd42  jz      short loc_18002CD66
0x18002cd44  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002cd48  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002cd4c  lea     rcx, [rbp+47h+var_60]; this
0x18002cd50  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002cd55  test    al, al
0x18002cd57  mov     eax, [rbp+47h+Source]
0x18002cd5a  jz      short loc_18002CD62
0x18002cd5c  inc     esi
0x18002cd5e  cmp     esi, eax
0x18002cd60  jb      short loc_18002CD44
0x18002cd62  mov     rbx, [rbp+47h+var_A8]
0x18002cd66  cmp     eax, esi
0x18002cd68  jz      short loc_18002CDA2
0x18002cd6a  mov     al, [rbp+47h+var_9E]
0x18002cd6d  mov     [rbp+47h+Source], esi
0x18002cd70  cmp     al, 1
0x18002cd72  jnz     short loc_18002CD88
0x18002cd74  mov     eax, 2
0x18002cd79  mov     [rbp+47h+var_B0], si
0x18002cd7d  mov     r9d, eax
0x18002cd80  lea     r8, [rbp+47h+var_B0]
0x18002cd84  mov     edx, eax
0x18002cd86  jmp     short loc_18002CD98
0x18002cd88  cmp     al, 2
0x18002cd8a  jnz     short loc_18002CDA2
0x18002cd8c  mov     edx, 4; DestinationSize
0x18002cd91  lea     r8, [rbp+47h+Source]; Source
0x18002cd95  mov     r9d, edx; SourceSize
0x18002cd98  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002cd9c  call    cs:__imp_memcpy_s
0x18002cda2  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002cda6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002cdaa  lea     rcx, [rbp+47h+var_A0]; this
0x18002cdae  mov     [rbp+47h+var_A8], rbx
0x18002cdb2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002cdb7  xor     r9d, r9d
0x18002cdba  mov     sil, al
0x18002cdbd  test    al, al
0x18002cdbf  jnz     loc_18002CC6E
0x18002cdc5  mov     rbx, [rbp+47h+var_A8]
0x18002cdc9  mov     [rdi+20h], rbx
0x18002cdcd  mov     rcx, r9
0x18002cdd0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18002cdd4  jnz     loc_18002CE5F
0x18002cdda  movzx   eax, [rbp+47h+var_A0]
0x18002cdde  mov     [rbp+47h+Source], 1
0x18002cde5  mov     [rbp+47h+var_98], r14w
0x18002cdea  mov     [rbp+47h+Buf2], r9
0x18002cdee  mov     [rbp+47h+Buf2+8], r15
0x18002cdf2  test    ax, ax
0x18002cdf5  jnz     short loc_18002CE47
0x18002cdf7  movzx   ecx, r14w
0x18002cdfb  add     rcx, 2
0x18002cdff  jmp     short loc_18002CE4A
0x18002ce01  mov     eax, [rbp+47h+arg_28]
0x18002ce04  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18002ce08  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18002ce0c  mov     r9, r13; void *
0x18002ce0f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18002ce13  mov     rcx, rdi; this
0x18002ce16  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18002ce1b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18002ce20  xor     r9d, r9d
0x18002ce23  mov     [rbp+47h+var_A8], rax
0x18002ce27  mov     rbx, rax
0x18002ce2a  test    rax, rax
0x18002ce2d  jnz     short loc_18002CE36
0x18002ce2f  mov     al, 1
0x18002ce31  jmp     loc_18002CF64
0x18002ce36  mov     byte ptr [rbp+47h+arg_0], 1
0x18002ce3a  jmp     short loc_18002CE40
0x18002ce3c  mov     [rbp+47h+var_A8], rbx
0x18002ce40  test    sil, sil
0x18002ce43  jnz     short loc_18002CDCD
0x18002ce45  jmp     short loc_18002CDC9
0x18002ce47  mov     rcx, rax
0x18002ce4a  mov     al, [rbp+47h+var_9E]
0x18002ce4d  cmp     al, 1
0x18002ce4f  jnz     short loc_18002CE57
0x18002ce51  add     rcx, 2
0x18002ce55  jmp     short loc_18002CE5F
0x18002ce57  cmp     al, 2
0x18002ce59  jnz     short loc_18002CE5F
0x18002ce5b  add     rcx, 4
0x18002ce5f  movzx   eax, word ptr [rdi+6]
0x18002ce63  mov     dl, [rdi+8]
0x18002ce66  mov     r8d, [rbp+47h+arg_28]
0x18002ce6a  mov     [rbp+47h+var_80], ax
0x18002ce6e  mov     [rbp+47h+var_7E], dl
0x18002ce71  mov     [rbp+47h+var_7C], r8d
0x18002ce75  mov     [rbp+47h+var_78], r12w
0x18002ce7a  mov     [rbp+47h+var_70], r9
0x18002ce7e  mov     [rbp+47h+var_68], r13
0x18002ce82  test    ax, ax
0x18002ce85  jnz     short loc_18002CE8F
0x18002ce87  movzx   eax, r12w
0x18002ce8b  add     rax, 2
0x18002ce8f  cmp     dl, 1
0x18002ce92  jnz     short loc_18002CE9A
0x18002ce94  add     rax, 2
0x18002ce98  jmp     short loc_18002CEA3
0x18002ce9a  cmp     dl, 2
0x18002ce9d  jnz     short loc_18002CEA3
0x18002ce9f  add     rax, 4
0x18002cea3  mov     rdx, [rdi+28h]
0x18002cea7  lea     rsi, [rax+rcx]
0x18002ceab  mov     r9, [rdi+20h]
0x18002ceaf  mov     rcx, rdx
0x18002ceb2  sub     rcx, r9
0x18002ceb5  cmp     r9, rdx
0x18002ceb8  sbb     rax, rax
0x18002cebb  and     rax, rcx
0x18002cebe  cmp     rax, rsi
0x18002cec1  jb      loc_18002CF62
0x18002cec7  sub     rdx, rsi
0x18002ceca  lea     rcx, [rsi+rbx]; Destination
0x18002cece  sub     rdx, rbx; DestinationSize
0x18002ced1  sub     r9, rbx; SourceSize
0x18002ced4  mov     r8, rbx; Source
0x18002ced7  call    cs:__imp_memmove_s
0x18002cedd  add     [rdi+20h], rsi
0x18002cee1  xor     ebx, ebx
0x18002cee3  cmp     byte ptr [rbp+47h+arg_0], bl
0x18002cee6  jnz     short loc_18002CEFB
0x18002cee8  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002ceec  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002cef0  lea     rcx, [rbp+47h+var_A0]; this
0x18002cef4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002cef9  jmp     short loc_18002CF48
0x18002cefb  mov     cl, [rbp+47h+var_9E]
0x18002cefe  test    cl, cl
0x18002cf00  jz      short loc_18002CF48
0x18002cf02  mov     eax, [rbp+47h+Source]
0x18002cf05  lea     r8d, [rax+1]
0x18002cf09  cmp     eax, r8d
0x18002cf0c  jz      short loc_18002CF48
0x18002cf0e  mov     [rbp+47h+Source], r8d
0x18002cf12  cmp     cl, 1
0x18002cf15  jnz     short loc_18002CF2B
0x18002cf17  mov     r9d, 2
0x18002cf1d  mov     [rbp+47h+arg_0], r8w
0x18002cf22  mov     edx, r9d
0x18002cf25  lea     r8, [rbp+47h+arg_0]
0x18002cf29  jmp     short loc_18002CF3E
0x18002cf2b  cmp     cl, 2
0x18002cf2e  jnz     short loc_18002CF48
0x18002cf30  mov     eax, 4
0x18002cf35  lea     r8, [rbp+47h+Source]; Source
0x18002cf39  mov     r9d, eax; SourceSize
0x18002cf3c  mov     edx, eax; DestinationSize
0x18002cf3e  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002cf42  call    cs:__imp_memcpy_s
0x18002cf48  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002cf4c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002cf50  lea     rcx, [rbp+47h+var_80]; this
0x18002cf54  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002cf59  mov     byte ptr [rdi+38h], 1
0x18002cf5d  jmp     loc_18002CE2F
0x18002cf62  xor     al, al
0x18002cf64  add     rsp, 0A8h
0x18002cf6b  pop     r15
0x18002cf6d  pop     r14
0x18002cf6f  pop     r13
0x18002cf71  pop     r12
0x18002cf73  pop     rdi
0x18002cf74  pop     rsi
0x18002cf75  pop     rbx
0x18002cf76  pop     rbp
0x18002cf77  retn
```
