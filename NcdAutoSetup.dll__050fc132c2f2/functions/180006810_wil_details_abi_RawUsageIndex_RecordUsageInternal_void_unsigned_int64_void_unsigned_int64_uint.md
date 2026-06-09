# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006810`
- end: `0x180006b90`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006660`

## callees

- `0x180004870`
- `0x1800061dc`
- `0x180006810`
- `0x180008b7c`
- `0x1800137f6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006aef`
- `msvcrt!memmove_s` at `0x180006aef`
- `msvcrt!memcpy_s` at `0x18000691b`
- `msvcrt!memcpy_s` at `0x1800069b4`
- `msvcrt!memcpy_s` at `0x180006b5a`
- `msvcrt!memcpy_s` at `0x18000691b`
- `msvcrt!memcpy_s` at `0x1800069b4`
- `msvcrt!memcpy_s` at `0x180006b5a`

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
0x180006810  push    rbp
0x180006812  push    rbx
0x180006813  push    rsi
0x180006814  push    rdi
0x180006815  push    r12
0x180006817  push    r13
0x180006819  push    r14
0x18000681b  push    r15
0x18000681d  lea     rbp, [rsp-0Fh]
0x180006822  sub     rsp, 0A8h
0x180006829  mov     rbx, [rcx+18h]
0x18000682d  mov     rdi, rcx
0x180006830  xor     ecx, ecx
0x180006832  mov     r13, r9
0x180006835  mov     r14, r8
0x180006838  mov     r15, rdx
0x18000683b  test    rbx, rbx
0x18000683e  jz      loc_180006B7A
0x180006844  movzx   eax, word ptr [rdi+2]
0x180006848  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000684c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006850  add     rbx, 0Ah
0x180006854  mov     [rbp+47h+var_A0], ax
0x180006858  xorps   xmm0, xmm0
0x18000685b  mov     al, [rdi+4]
0x18000685e  mov     [rbp+47h+Source], ecx
0x180006861  mov     [rbp+47h+var_98], cx
0x180006865  mov     byte ptr [rbp+47h+arg_0], cl
0x180006868  lea     rcx, [rbp+47h+var_A0]; this
0x18000686c  mov     [rbp+47h+var_9E], al
0x18000686f  mov     [rbp+47h+var_A8], rbx
0x180006873  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180006878  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000687d  mov     r12, [rbp+47h+arg_20]
0x180006881  jmp     loc_1800069CF
0x180006886  movzx   eax, [rbp+47h+var_98]
0x18000688a  cmp     r14, rax
0x18000688d  jnz     short loc_1800068A5
0x18000688f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180006893  mov     r8, r14; Size
0x180006896  mov     rcx, r15; Buf1
0x180006899  call    memcmp_0
0x18000689e  mov     ecx, eax
0x1800068a0  xor     r9d, r9d
0x1800068a3  jmp     short loc_1800068AE
0x1800068a5  movzx   eax, [rbp+47h+var_98]
0x1800068a9  mov     ecx, r14d
0x1800068ac  sub     ecx, eax
0x1800068ae  test    ecx, ecx
0x1800068b0  js      loc_180006A54
0x1800068b6  jz      loc_180006A19
0x1800068bc  mov     rbx, [rbp+47h+var_A8]
0x1800068c0  mov     [rbp+47h+var_A8], rbx
0x1800068c4  cmp     [rdi+10h], r9
0x1800068c8  jbe     short loc_180006933
0x1800068ca  mov     rax, [rdi+20h]
0x1800068ce  xor     edx, edx
0x1800068d0  sub     rax, [rdi+18h]
0x1800068d4  mov     rsi, rbx
0x1800068d7  div     qword ptr [rdi+10h]
0x1800068db  mov     edx, [rbp+47h+Source]
0x1800068de  cmp     rdx, rax
0x1800068e1  jbe     short loc_180006924
0x1800068e3  cmp     edx, eax
0x1800068e5  jz      short loc_180006924
0x1800068e7  mov     edx, eax
0x1800068e9  mov     [rbp+47h+Source], eax
0x1800068ec  mov     al, [rbp+47h+var_9E]
0x1800068ef  cmp     al, 1
0x1800068f1  jnz     short loc_180006906
0x1800068f3  movzx   eax, dx
0x1800068f6  mov     [rbp+47h+var_B0], dx
0x1800068fa  mov     r9d, 2
0x180006900  lea     r8, [rbp+47h+var_B0]
0x180006904  jmp     short loc_180006914
0x180006906  cmp     al, 2
0x180006908  jnz     short loc_180006924
0x18000690a  mov     r9d, 4; SourceSize
0x180006910  lea     r8, [rbp+47h+Source]; Source
0x180006914  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006918  mov     rdx, r9; DestinationSize
0x18000691b  call    cs:__imp_memcpy_s
0x180006921  mov     edx, [rbp+47h+Source]
0x180006924  mov     ebx, edx
0x180006926  imul    rbx, [rdi+10h]
0x18000692b  add     rbx, rsi
0x18000692e  jmp     loc_1800069BA
0x180006933  movzx   eax, word ptr [rdi+6]
0x180006937  xorps   xmm0, xmm0
0x18000693a  mov     [rbp+47h+var_60], ax
0x18000693e  mov     esi, r9d
0x180006941  mov     al, [rdi+8]
0x180006944  mov     [rbp+47h+var_5E], al
0x180006947  mov     eax, [rbp+47h+Source]
0x18000694a  mov     [rbp+47h+var_5C], r9d
0x18000694e  mov     [rbp+47h+var_58], r9w
0x180006953  movdqu  [rbp+47h+var_50], xmm0
0x180006958  test    eax, eax
0x18000695a  jz      short loc_18000697E
0x18000695c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006960  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006964  lea     rcx, [rbp+47h+var_60]; this
0x180006968  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000696d  test    al, al
0x18000696f  mov     eax, [rbp+47h+Source]
0x180006972  jz      short loc_18000697A
0x180006974  inc     esi
0x180006976  cmp     esi, eax
0x180006978  jb      short loc_18000695C
0x18000697a  mov     rbx, [rbp+47h+var_A8]
0x18000697e  cmp     eax, esi
0x180006980  jz      short loc_1800069BA
0x180006982  mov     al, [rbp+47h+var_9E]
0x180006985  mov     [rbp+47h+Source], esi
0x180006988  cmp     al, 1
0x18000698a  jnz     short loc_1800069A0
0x18000698c  mov     eax, 2
0x180006991  mov     [rbp+47h+var_B0], si
0x180006995  mov     r9d, eax
0x180006998  lea     r8, [rbp+47h+var_B0]
0x18000699c  mov     edx, eax
0x18000699e  jmp     short loc_1800069B0
0x1800069a0  cmp     al, 2
0x1800069a2  jnz     short loc_1800069BA
0x1800069a4  mov     edx, 4; DestinationSize
0x1800069a9  lea     r8, [rbp+47h+Source]; Source
0x1800069ad  mov     r9d, edx; SourceSize
0x1800069b0  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800069b4  call    cs:__imp_memcpy_s
0x1800069ba  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800069be  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800069c2  lea     rcx, [rbp+47h+var_A0]; this
0x1800069c6  mov     [rbp+47h+var_A8], rbx
0x1800069ca  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800069cf  xor     r9d, r9d
0x1800069d2  mov     sil, al
0x1800069d5  test    al, al
0x1800069d7  jnz     loc_180006886
0x1800069dd  mov     rbx, [rbp+47h+var_A8]
0x1800069e1  mov     [rdi+20h], rbx
0x1800069e5  mov     rcx, r9
0x1800069e8  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800069ec  jnz     loc_180006A77
0x1800069f2  movzx   eax, [rbp+47h+var_A0]
0x1800069f6  mov     [rbp+47h+Source], 1
0x1800069fd  mov     [rbp+47h+var_98], r14w
0x180006a02  mov     [rbp+47h+Buf2], r9
0x180006a06  mov     [rbp+47h+Buf2+8], r15
0x180006a0a  test    ax, ax
0x180006a0d  jnz     short loc_180006A5F
0x180006a0f  movzx   ecx, r14w
0x180006a13  add     rcx, 2
0x180006a17  jmp     short loc_180006A62
0x180006a19  mov     eax, [rbp+47h+arg_28]
0x180006a1c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180006a20  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180006a24  mov     r9, r13; void *
0x180006a27  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180006a2b  mov     rcx, rdi; this
0x180006a2e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180006a33  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006a38  xor     r9d, r9d
0x180006a3b  mov     [rbp+47h+var_A8], rax
0x180006a3f  mov     rbx, rax
0x180006a42  test    rax, rax
0x180006a45  jnz     short loc_180006A4E
0x180006a47  mov     al, 1
0x180006a49  jmp     loc_180006B7C
0x180006a4e  mov     byte ptr [rbp+47h+arg_0], 1
0x180006a52  jmp     short loc_180006A58
0x180006a54  mov     [rbp+47h+var_A8], rbx
0x180006a58  test    sil, sil
0x180006a5b  jnz     short loc_1800069E5
0x180006a5d  jmp     short loc_1800069E1
0x180006a5f  mov     rcx, rax
0x180006a62  mov     al, [rbp+47h+var_9E]
0x180006a65  cmp     al, 1
0x180006a67  jnz     short loc_180006A6F
0x180006a69  add     rcx, 2
0x180006a6d  jmp     short loc_180006A77
0x180006a6f  cmp     al, 2
0x180006a71  jnz     short loc_180006A77
0x180006a73  add     rcx, 4
0x180006a77  movzx   eax, word ptr [rdi+6]
0x180006a7b  mov     dl, [rdi+8]
0x180006a7e  mov     r8d, [rbp+47h+arg_28]
0x180006a82  mov     [rbp+47h+var_80], ax
0x180006a86  mov     [rbp+47h+var_7E], dl
0x180006a89  mov     [rbp+47h+var_7C], r8d
0x180006a8d  mov     [rbp+47h+var_78], r12w
0x180006a92  mov     [rbp+47h+var_70], r9
0x180006a96  mov     [rbp+47h+var_68], r13
0x180006a9a  test    ax, ax
0x180006a9d  jnz     short loc_180006AA7
0x180006a9f  movzx   eax, r12w
0x180006aa3  add     rax, 2
0x180006aa7  cmp     dl, 1
0x180006aaa  jnz     short loc_180006AB2
0x180006aac  add     rax, 2
0x180006ab0  jmp     short loc_180006ABB
0x180006ab2  cmp     dl, 2
0x180006ab5  jnz     short loc_180006ABB
0x180006ab7  add     rax, 4
0x180006abb  mov     rdx, [rdi+28h]
0x180006abf  lea     rsi, [rax+rcx]
0x180006ac3  mov     r9, [rdi+20h]
0x180006ac7  mov     rcx, rdx
0x180006aca  sub     rcx, r9
0x180006acd  cmp     r9, rdx
0x180006ad0  sbb     rax, rax
0x180006ad3  and     rax, rcx
0x180006ad6  cmp     rax, rsi
0x180006ad9  jb      loc_180006B7A
0x180006adf  sub     rdx, rsi
0x180006ae2  lea     rcx, [rsi+rbx]; Destination
0x180006ae6  sub     rdx, rbx; DestinationSize
0x180006ae9  sub     r9, rbx; SourceSize
0x180006aec  mov     r8, rbx; Source
0x180006aef  call    cs:__imp_memmove_s
0x180006af5  add     [rdi+20h], rsi
0x180006af9  xor     ebx, ebx
0x180006afb  cmp     byte ptr [rbp+47h+arg_0], bl
0x180006afe  jnz     short loc_180006B13
0x180006b00  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006b04  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006b08  lea     rcx, [rbp+47h+var_A0]; this
0x180006b0c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006b11  jmp     short loc_180006B60
0x180006b13  mov     cl, [rbp+47h+var_9E]
0x180006b16  test    cl, cl
0x180006b18  jz      short loc_180006B60
0x180006b1a  mov     eax, [rbp+47h+Source]
0x180006b1d  lea     r8d, [rax+1]
0x180006b21  cmp     eax, r8d
0x180006b24  jz      short loc_180006B60
0x180006b26  mov     [rbp+47h+Source], r8d
0x180006b2a  cmp     cl, 1
0x180006b2d  jnz     short loc_180006B43
0x180006b2f  mov     r9d, 2
0x180006b35  mov     [rbp+47h+arg_0], r8w
0x180006b3a  mov     edx, r9d
0x180006b3d  lea     r8, [rbp+47h+arg_0]
0x180006b41  jmp     short loc_180006B56
0x180006b43  cmp     cl, 2
0x180006b46  jnz     short loc_180006B60
0x180006b48  mov     eax, 4
0x180006b4d  lea     r8, [rbp+47h+Source]; Source
0x180006b51  mov     r9d, eax; SourceSize
0x180006b54  mov     edx, eax; DestinationSize
0x180006b56  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006b5a  call    cs:__imp_memcpy_s
0x180006b60  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006b64  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006b68  lea     rcx, [rbp+47h+var_80]; this
0x180006b6c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006b71  mov     byte ptr [rdi+38h], 1
0x180006b75  jmp     loc_180006A47
0x180006b7a  xor     al, al
0x180006b7c  add     rsp, 0A8h
0x180006b83  pop     r15
0x180006b85  pop     r14
0x180006b87  pop     r13
0x180006b89  pop     r12
0x180006b8b  pop     rdi
0x180006b8c  pop     rsi
0x180006b8d  pop     rbx
0x180006b8e  pop     rbp
0x180006b8f  retn
```
