# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180021240`
- end: `0x1800215c0`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021090`

## callees

- `0x18001b258`
- `0x18001f724`
- `0x180021240`
- `0x180024530`
- `0x1800322c6`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002151f`
- `msvcrt!memmove_s` at `0x18002151f`
- `msvcrt!memcpy_s` at `0x18002134b`
- `msvcrt!memcpy_s` at `0x1800213e4`
- `msvcrt!memcpy_s` at `0x18002158a`
- `msvcrt!memcpy_s` at `0x18002134b`
- `msvcrt!memcpy_s` at `0x1800213e4`
- `msvcrt!memcpy_s` at `0x18002158a`

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
0x180021240  push    rbp
0x180021242  push    rbx
0x180021243  push    rsi
0x180021244  push    rdi
0x180021245  push    r12
0x180021247  push    r13
0x180021249  push    r14
0x18002124b  push    r15
0x18002124d  lea     rbp, [rsp-0Fh]
0x180021252  sub     rsp, 0A8h
0x180021259  mov     rbx, [rcx+18h]
0x18002125d  mov     rdi, rcx
0x180021260  xor     ecx, ecx
0x180021262  mov     r13, r9
0x180021265  mov     r14, r8
0x180021268  mov     r15, rdx
0x18002126b  test    rbx, rbx
0x18002126e  jz      loc_1800215AA
0x180021274  movzx   eax, word ptr [rdi+2]
0x180021278  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002127c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180021280  add     rbx, 0Ah
0x180021284  mov     [rbp+47h+var_A0], ax
0x180021288  xorps   xmm0, xmm0
0x18002128b  mov     al, [rdi+4]
0x18002128e  mov     [rbp+47h+Source], ecx
0x180021291  mov     [rbp+47h+var_98], cx
0x180021295  mov     byte ptr [rbp+47h+arg_0], cl
0x180021298  lea     rcx, [rbp+47h+var_A0]; this
0x18002129c  mov     [rbp+47h+var_9E], al
0x18002129f  mov     [rbp+47h+var_A8], rbx
0x1800212a3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800212a8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800212ad  mov     r12, [rbp+47h+arg_20]
0x1800212b1  jmp     loc_1800213FF
0x1800212b6  movzx   eax, [rbp+47h+var_98]
0x1800212ba  cmp     r14, rax
0x1800212bd  jnz     short loc_1800212D5
0x1800212bf  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1800212c3  mov     r8, r14; Size
0x1800212c6  mov     rcx, r15; Buf1
0x1800212c9  call    memcmp_0
0x1800212ce  mov     ecx, eax
0x1800212d0  xor     r9d, r9d
0x1800212d3  jmp     short loc_1800212DE
0x1800212d5  movzx   eax, [rbp+47h+var_98]
0x1800212d9  mov     ecx, r14d
0x1800212dc  sub     ecx, eax
0x1800212de  test    ecx, ecx
0x1800212e0  js      loc_180021484
0x1800212e6  jz      loc_180021449
0x1800212ec  mov     rbx, [rbp+47h+var_A8]
0x1800212f0  mov     [rbp+47h+var_A8], rbx
0x1800212f4  cmp     [rdi+10h], r9
0x1800212f8  jbe     short loc_180021363
0x1800212fa  mov     rax, [rdi+20h]
0x1800212fe  xor     edx, edx
0x180021300  sub     rax, [rdi+18h]
0x180021304  mov     rsi, rbx
0x180021307  div     qword ptr [rdi+10h]
0x18002130b  mov     edx, [rbp+47h+Source]
0x18002130e  cmp     rdx, rax
0x180021311  jbe     short loc_180021354
0x180021313  cmp     edx, eax
0x180021315  jz      short loc_180021354
0x180021317  mov     edx, eax
0x180021319  mov     [rbp+47h+Source], eax
0x18002131c  mov     al, [rbp+47h+var_9E]
0x18002131f  cmp     al, 1
0x180021321  jnz     short loc_180021336
0x180021323  movzx   eax, dx
0x180021326  mov     [rbp+47h+var_B0], dx
0x18002132a  mov     r9d, 2
0x180021330  lea     r8, [rbp+47h+var_B0]
0x180021334  jmp     short loc_180021344
0x180021336  cmp     al, 2
0x180021338  jnz     short loc_180021354
0x18002133a  mov     r9d, 4; SourceSize
0x180021340  lea     r8, [rbp+47h+Source]; Source
0x180021344  mov     rcx, [rbp+47h+Buf2]; Destination
0x180021348  mov     rdx, r9; DestinationSize
0x18002134b  call    cs:__imp_memcpy_s
0x180021351  mov     edx, [rbp+47h+Source]
0x180021354  mov     ebx, edx
0x180021356  imul    rbx, [rdi+10h]
0x18002135b  add     rbx, rsi
0x18002135e  jmp     loc_1800213EA
0x180021363  movzx   eax, word ptr [rdi+6]
0x180021367  xorps   xmm0, xmm0
0x18002136a  mov     [rbp+47h+var_60], ax
0x18002136e  mov     esi, r9d
0x180021371  mov     al, [rdi+8]
0x180021374  mov     [rbp+47h+var_5E], al
0x180021377  mov     eax, [rbp+47h+Source]
0x18002137a  mov     [rbp+47h+var_5C], r9d
0x18002137e  mov     [rbp+47h+var_58], r9w
0x180021383  movdqu  [rbp+47h+var_50], xmm0
0x180021388  test    eax, eax
0x18002138a  jz      short loc_1800213AE
0x18002138c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180021390  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180021394  lea     rcx, [rbp+47h+var_60]; this
0x180021398  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002139d  test    al, al
0x18002139f  mov     eax, [rbp+47h+Source]
0x1800213a2  jz      short loc_1800213AA
0x1800213a4  inc     esi
0x1800213a6  cmp     esi, eax
0x1800213a8  jb      short loc_18002138C
0x1800213aa  mov     rbx, [rbp+47h+var_A8]
0x1800213ae  cmp     eax, esi
0x1800213b0  jz      short loc_1800213EA
0x1800213b2  mov     al, [rbp+47h+var_9E]
0x1800213b5  mov     [rbp+47h+Source], esi
0x1800213b8  cmp     al, 1
0x1800213ba  jnz     short loc_1800213D0
0x1800213bc  mov     eax, 2
0x1800213c1  mov     [rbp+47h+var_B0], si
0x1800213c5  mov     r9d, eax
0x1800213c8  lea     r8, [rbp+47h+var_B0]
0x1800213cc  mov     edx, eax
0x1800213ce  jmp     short loc_1800213E0
0x1800213d0  cmp     al, 2
0x1800213d2  jnz     short loc_1800213EA
0x1800213d4  mov     edx, 4; DestinationSize
0x1800213d9  lea     r8, [rbp+47h+Source]; Source
0x1800213dd  mov     r9d, edx; SourceSize
0x1800213e0  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800213e4  call    cs:__imp_memcpy_s
0x1800213ea  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800213ee  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800213f2  lea     rcx, [rbp+47h+var_A0]; this
0x1800213f6  mov     [rbp+47h+var_A8], rbx
0x1800213fa  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800213ff  xor     r9d, r9d
0x180021402  mov     sil, al
0x180021405  test    al, al
0x180021407  jnz     loc_1800212B6
0x18002140d  mov     rbx, [rbp+47h+var_A8]
0x180021411  mov     [rdi+20h], rbx
0x180021415  mov     rcx, r9
0x180021418  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18002141c  jnz     loc_1800214A7
0x180021422  movzx   eax, [rbp+47h+var_A0]
0x180021426  mov     [rbp+47h+Source], 1
0x18002142d  mov     [rbp+47h+var_98], r14w
0x180021432  mov     [rbp+47h+Buf2], r9
0x180021436  mov     [rbp+47h+Buf2+8], r15
0x18002143a  test    ax, ax
0x18002143d  jnz     short loc_18002148F
0x18002143f  movzx   ecx, r14w
0x180021443  add     rcx, 2
0x180021447  jmp     short loc_180021492
0x180021449  mov     eax, [rbp+47h+arg_28]
0x18002144c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180021450  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180021454  mov     r9, r13; void *
0x180021457  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18002145b  mov     rcx, rdi; this
0x18002145e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180021463  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180021468  xor     r9d, r9d
0x18002146b  mov     [rbp+47h+var_A8], rax
0x18002146f  mov     rbx, rax
0x180021472  test    rax, rax
0x180021475  jnz     short loc_18002147E
0x180021477  mov     al, 1
0x180021479  jmp     loc_1800215AC
0x18002147e  mov     byte ptr [rbp+47h+arg_0], 1
0x180021482  jmp     short loc_180021488
0x180021484  mov     [rbp+47h+var_A8], rbx
0x180021488  test    sil, sil
0x18002148b  jnz     short loc_180021415
0x18002148d  jmp     short loc_180021411
0x18002148f  mov     rcx, rax
0x180021492  mov     al, [rbp+47h+var_9E]
0x180021495  cmp     al, 1
0x180021497  jnz     short loc_18002149F
0x180021499  add     rcx, 2
0x18002149d  jmp     short loc_1800214A7
0x18002149f  cmp     al, 2
0x1800214a1  jnz     short loc_1800214A7
0x1800214a3  add     rcx, 4
0x1800214a7  movzx   eax, word ptr [rdi+6]
0x1800214ab  mov     dl, [rdi+8]
0x1800214ae  mov     r8d, [rbp+47h+arg_28]
0x1800214b2  mov     [rbp+47h+var_80], ax
0x1800214b6  mov     [rbp+47h+var_7E], dl
0x1800214b9  mov     [rbp+47h+var_7C], r8d
0x1800214bd  mov     [rbp+47h+var_78], r12w
0x1800214c2  mov     [rbp+47h+var_70], r9
0x1800214c6  mov     [rbp+47h+var_68], r13
0x1800214ca  test    ax, ax
0x1800214cd  jnz     short loc_1800214D7
0x1800214cf  movzx   eax, r12w
0x1800214d3  add     rax, 2
0x1800214d7  cmp     dl, 1
0x1800214da  jnz     short loc_1800214E2
0x1800214dc  add     rax, 2
0x1800214e0  jmp     short loc_1800214EB
0x1800214e2  cmp     dl, 2
0x1800214e5  jnz     short loc_1800214EB
0x1800214e7  add     rax, 4
0x1800214eb  mov     rdx, [rdi+28h]
0x1800214ef  lea     rsi, [rax+rcx]
0x1800214f3  mov     r9, [rdi+20h]
0x1800214f7  mov     rcx, rdx
0x1800214fa  sub     rcx, r9
0x1800214fd  cmp     r9, rdx
0x180021500  sbb     rax, rax
0x180021503  and     rax, rcx
0x180021506  cmp     rax, rsi
0x180021509  jb      loc_1800215AA
0x18002150f  sub     rdx, rsi
0x180021512  lea     rcx, [rsi+rbx]; Destination
0x180021516  sub     rdx, rbx; DestinationSize
0x180021519  sub     r9, rbx; SourceSize
0x18002151c  mov     r8, rbx; Source
0x18002151f  call    cs:__imp_memmove_s
0x180021525  add     [rdi+20h], rsi
0x180021529  xor     ebx, ebx
0x18002152b  cmp     byte ptr [rbp+47h+arg_0], bl
0x18002152e  jnz     short loc_180021543
0x180021530  mov     r8, [rdi+20h]; unsigned __int8 *
0x180021534  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180021538  lea     rcx, [rbp+47h+var_A0]; this
0x18002153c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180021541  jmp     short loc_180021590
0x180021543  mov     cl, [rbp+47h+var_9E]
0x180021546  test    cl, cl
0x180021548  jz      short loc_180021590
0x18002154a  mov     eax, [rbp+47h+Source]
0x18002154d  lea     r8d, [rax+1]
0x180021551  cmp     eax, r8d
0x180021554  jz      short loc_180021590
0x180021556  mov     [rbp+47h+Source], r8d
0x18002155a  cmp     cl, 1
0x18002155d  jnz     short loc_180021573
0x18002155f  mov     r9d, 2
0x180021565  mov     [rbp+47h+arg_0], r8w
0x18002156a  mov     edx, r9d
0x18002156d  lea     r8, [rbp+47h+arg_0]
0x180021571  jmp     short loc_180021586
0x180021573  cmp     cl, 2
0x180021576  jnz     short loc_180021590
0x180021578  mov     eax, 4
0x18002157d  lea     r8, [rbp+47h+Source]; Source
0x180021581  mov     r9d, eax; SourceSize
0x180021584  mov     edx, eax; DestinationSize
0x180021586  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002158a  call    cs:__imp_memcpy_s
0x180021590  mov     r8, [rdi+20h]; unsigned __int8 *
0x180021594  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180021598  lea     rcx, [rbp+47h+var_80]; this
0x18002159c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800215a1  mov     byte ptr [rdi+38h], 1
0x1800215a5  jmp     loc_180021477
0x1800215aa  xor     al, al
0x1800215ac  add     rsp, 0A8h
0x1800215b3  pop     r15
0x1800215b5  pop     r14
0x1800215b7  pop     r13
0x1800215b9  pop     r12
0x1800215bb  pop     rdi
0x1800215bc  pop     rsi
0x1800215bd  pop     rbx
0x1800215be  pop     rbp
0x1800215bf  retn
```
