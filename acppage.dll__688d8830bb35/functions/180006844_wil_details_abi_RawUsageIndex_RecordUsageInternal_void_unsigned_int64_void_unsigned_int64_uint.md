# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006844`
- end: `0x180006bc4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006694`

## callees

- `0x1800046ac`
- `0x180006028`
- `0x180006844`
- `0x1800081cc`
- `0x180016216`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006b23`
- `msvcrt!memmove_s` at `0x180006b23`
- `msvcrt!memcpy_s` at `0x18000694f`
- `msvcrt!memcpy_s` at `0x1800069e8`
- `msvcrt!memcpy_s` at `0x180006b8e`
- `msvcrt!memcpy_s` at `0x18000694f`
- `msvcrt!memcpy_s` at `0x1800069e8`
- `msvcrt!memcpy_s` at `0x180006b8e`

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
0x180006844  push    rbp
0x180006846  push    rbx
0x180006847  push    rsi
0x180006848  push    rdi
0x180006849  push    r12
0x18000684b  push    r13
0x18000684d  push    r14
0x18000684f  push    r15
0x180006851  lea     rbp, [rsp-0Fh]
0x180006856  sub     rsp, 0A8h
0x18000685d  mov     rbx, [rcx+18h]
0x180006861  mov     rdi, rcx
0x180006864  xor     ecx, ecx
0x180006866  mov     r13, r9
0x180006869  mov     r14, r8
0x18000686c  mov     r15, rdx
0x18000686f  test    rbx, rbx
0x180006872  jz      loc_180006BAE
0x180006878  movzx   eax, word ptr [rdi+2]
0x18000687c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006880  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006884  add     rbx, 0Ah
0x180006888  mov     [rbp+47h+var_A0], ax
0x18000688c  xorps   xmm0, xmm0
0x18000688f  mov     al, [rdi+4]
0x180006892  mov     [rbp+47h+Source], ecx
0x180006895  mov     [rbp+47h+var_98], cx
0x180006899  mov     byte ptr [rbp+47h+arg_0], cl
0x18000689c  lea     rcx, [rbp+47h+var_A0]; this
0x1800068a0  mov     [rbp+47h+var_9E], al
0x1800068a3  mov     [rbp+47h+var_A8], rbx
0x1800068a7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800068ac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800068b1  mov     r12, [rbp+47h+arg_20]
0x1800068b5  jmp     loc_180006A03
0x1800068ba  movzx   eax, [rbp+47h+var_98]
0x1800068be  cmp     r14, rax
0x1800068c1  jnz     short loc_1800068D9
0x1800068c3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1800068c7  mov     r8, r14; Size
0x1800068ca  mov     rcx, r15; Buf1
0x1800068cd  call    memcmp_0
0x1800068d2  mov     ecx, eax
0x1800068d4  xor     r9d, r9d
0x1800068d7  jmp     short loc_1800068E2
0x1800068d9  movzx   eax, [rbp+47h+var_98]
0x1800068dd  mov     ecx, r14d
0x1800068e0  sub     ecx, eax
0x1800068e2  test    ecx, ecx
0x1800068e4  js      loc_180006A88
0x1800068ea  jz      loc_180006A4D
0x1800068f0  mov     rbx, [rbp+47h+var_A8]
0x1800068f4  mov     [rbp+47h+var_A8], rbx
0x1800068f8  cmp     [rdi+10h], r9
0x1800068fc  jbe     short loc_180006967
0x1800068fe  mov     rax, [rdi+20h]
0x180006902  xor     edx, edx
0x180006904  sub     rax, [rdi+18h]
0x180006908  mov     rsi, rbx
0x18000690b  div     qword ptr [rdi+10h]
0x18000690f  mov     edx, [rbp+47h+Source]
0x180006912  cmp     rdx, rax
0x180006915  jbe     short loc_180006958
0x180006917  cmp     edx, eax
0x180006919  jz      short loc_180006958
0x18000691b  mov     edx, eax
0x18000691d  mov     [rbp+47h+Source], eax
0x180006920  mov     al, [rbp+47h+var_9E]
0x180006923  cmp     al, 1
0x180006925  jnz     short loc_18000693A
0x180006927  movzx   eax, dx
0x18000692a  mov     [rbp+47h+var_B0], dx
0x18000692e  mov     r9d, 2
0x180006934  lea     r8, [rbp+47h+var_B0]
0x180006938  jmp     short loc_180006948
0x18000693a  cmp     al, 2
0x18000693c  jnz     short loc_180006958
0x18000693e  mov     r9d, 4; SourceSize
0x180006944  lea     r8, [rbp+47h+Source]; Source
0x180006948  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000694c  mov     rdx, r9; DestinationSize
0x18000694f  call    cs:__imp_memcpy_s
0x180006955  mov     edx, [rbp+47h+Source]
0x180006958  mov     ebx, edx
0x18000695a  imul    rbx, [rdi+10h]
0x18000695f  add     rbx, rsi
0x180006962  jmp     loc_1800069EE
0x180006967  movzx   eax, word ptr [rdi+6]
0x18000696b  xorps   xmm0, xmm0
0x18000696e  mov     [rbp+47h+var_60], ax
0x180006972  mov     esi, r9d
0x180006975  mov     al, [rdi+8]
0x180006978  mov     [rbp+47h+var_5E], al
0x18000697b  mov     eax, [rbp+47h+Source]
0x18000697e  mov     [rbp+47h+var_5C], r9d
0x180006982  mov     [rbp+47h+var_58], r9w
0x180006987  movdqu  [rbp+47h+var_50], xmm0
0x18000698c  test    eax, eax
0x18000698e  jz      short loc_1800069B2
0x180006990  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006994  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006998  lea     rcx, [rbp+47h+var_60]; this
0x18000699c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800069a1  test    al, al
0x1800069a3  mov     eax, [rbp+47h+Source]
0x1800069a6  jz      short loc_1800069AE
0x1800069a8  inc     esi
0x1800069aa  cmp     esi, eax
0x1800069ac  jb      short loc_180006990
0x1800069ae  mov     rbx, [rbp+47h+var_A8]
0x1800069b2  cmp     eax, esi
0x1800069b4  jz      short loc_1800069EE
0x1800069b6  mov     al, [rbp+47h+var_9E]
0x1800069b9  mov     [rbp+47h+Source], esi
0x1800069bc  cmp     al, 1
0x1800069be  jnz     short loc_1800069D4
0x1800069c0  mov     eax, 2
0x1800069c5  mov     [rbp+47h+var_B0], si
0x1800069c9  mov     r9d, eax
0x1800069cc  lea     r8, [rbp+47h+var_B0]
0x1800069d0  mov     edx, eax
0x1800069d2  jmp     short loc_1800069E4
0x1800069d4  cmp     al, 2
0x1800069d6  jnz     short loc_1800069EE
0x1800069d8  mov     edx, 4; DestinationSize
0x1800069dd  lea     r8, [rbp+47h+Source]; Source
0x1800069e1  mov     r9d, edx; SourceSize
0x1800069e4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800069e8  call    cs:__imp_memcpy_s
0x1800069ee  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800069f2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800069f6  lea     rcx, [rbp+47h+var_A0]; this
0x1800069fa  mov     [rbp+47h+var_A8], rbx
0x1800069fe  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006a03  xor     r9d, r9d
0x180006a06  mov     sil, al
0x180006a09  test    al, al
0x180006a0b  jnz     loc_1800068BA
0x180006a11  mov     rbx, [rbp+47h+var_A8]
0x180006a15  mov     [rdi+20h], rbx
0x180006a19  mov     rcx, r9
0x180006a1c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180006a20  jnz     loc_180006AAB
0x180006a26  movzx   eax, [rbp+47h+var_A0]
0x180006a2a  mov     [rbp+47h+Source], 1
0x180006a31  mov     [rbp+47h+var_98], r14w
0x180006a36  mov     [rbp+47h+Buf2], r9
0x180006a3a  mov     [rbp+47h+Buf2+8], r15
0x180006a3e  test    ax, ax
0x180006a41  jnz     short loc_180006A93
0x180006a43  movzx   ecx, r14w
0x180006a47  add     rcx, 2
0x180006a4b  jmp     short loc_180006A96
0x180006a4d  mov     eax, [rbp+47h+arg_28]
0x180006a50  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180006a54  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180006a58  mov     r9, r13; void *
0x180006a5b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180006a5f  mov     rcx, rdi; this
0x180006a62  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180006a67  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006a6c  xor     r9d, r9d
0x180006a6f  mov     [rbp+47h+var_A8], rax
0x180006a73  mov     rbx, rax
0x180006a76  test    rax, rax
0x180006a79  jnz     short loc_180006A82
0x180006a7b  mov     al, 1
0x180006a7d  jmp     loc_180006BB0
0x180006a82  mov     byte ptr [rbp+47h+arg_0], 1
0x180006a86  jmp     short loc_180006A8C
0x180006a88  mov     [rbp+47h+var_A8], rbx
0x180006a8c  test    sil, sil
0x180006a8f  jnz     short loc_180006A19
0x180006a91  jmp     short loc_180006A15
0x180006a93  mov     rcx, rax
0x180006a96  mov     al, [rbp+47h+var_9E]
0x180006a99  cmp     al, 1
0x180006a9b  jnz     short loc_180006AA3
0x180006a9d  add     rcx, 2
0x180006aa1  jmp     short loc_180006AAB
0x180006aa3  cmp     al, 2
0x180006aa5  jnz     short loc_180006AAB
0x180006aa7  add     rcx, 4
0x180006aab  movzx   eax, word ptr [rdi+6]
0x180006aaf  mov     dl, [rdi+8]
0x180006ab2  mov     r8d, [rbp+47h+arg_28]
0x180006ab6  mov     [rbp+47h+var_80], ax
0x180006aba  mov     [rbp+47h+var_7E], dl
0x180006abd  mov     [rbp+47h+var_7C], r8d
0x180006ac1  mov     [rbp+47h+var_78], r12w
0x180006ac6  mov     [rbp+47h+var_70], r9
0x180006aca  mov     [rbp+47h+var_68], r13
0x180006ace  test    ax, ax
0x180006ad1  jnz     short loc_180006ADB
0x180006ad3  movzx   eax, r12w
0x180006ad7  add     rax, 2
0x180006adb  cmp     dl, 1
0x180006ade  jnz     short loc_180006AE6
0x180006ae0  add     rax, 2
0x180006ae4  jmp     short loc_180006AEF
0x180006ae6  cmp     dl, 2
0x180006ae9  jnz     short loc_180006AEF
0x180006aeb  add     rax, 4
0x180006aef  mov     rdx, [rdi+28h]
0x180006af3  lea     rsi, [rax+rcx]
0x180006af7  mov     r9, [rdi+20h]
0x180006afb  mov     rcx, rdx
0x180006afe  sub     rcx, r9
0x180006b01  cmp     r9, rdx
0x180006b04  sbb     rax, rax
0x180006b07  and     rax, rcx
0x180006b0a  cmp     rax, rsi
0x180006b0d  jb      loc_180006BAE
0x180006b13  sub     rdx, rsi
0x180006b16  lea     rcx, [rsi+rbx]; Destination
0x180006b1a  sub     rdx, rbx; DestinationSize
0x180006b1d  sub     r9, rbx; SourceSize
0x180006b20  mov     r8, rbx; Source
0x180006b23  call    cs:__imp_memmove_s
0x180006b29  add     [rdi+20h], rsi
0x180006b2d  xor     ebx, ebx
0x180006b2f  cmp     byte ptr [rbp+47h+arg_0], bl
0x180006b32  jnz     short loc_180006B47
0x180006b34  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006b38  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006b3c  lea     rcx, [rbp+47h+var_A0]; this
0x180006b40  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006b45  jmp     short loc_180006B94
0x180006b47  mov     cl, [rbp+47h+var_9E]
0x180006b4a  test    cl, cl
0x180006b4c  jz      short loc_180006B94
0x180006b4e  mov     eax, [rbp+47h+Source]
0x180006b51  lea     r8d, [rax+1]
0x180006b55  cmp     eax, r8d
0x180006b58  jz      short loc_180006B94
0x180006b5a  mov     [rbp+47h+Source], r8d
0x180006b5e  cmp     cl, 1
0x180006b61  jnz     short loc_180006B77
0x180006b63  mov     r9d, 2
0x180006b69  mov     [rbp+47h+arg_0], r8w
0x180006b6e  mov     edx, r9d
0x180006b71  lea     r8, [rbp+47h+arg_0]
0x180006b75  jmp     short loc_180006B8A
0x180006b77  cmp     cl, 2
0x180006b7a  jnz     short loc_180006B94
0x180006b7c  mov     eax, 4
0x180006b81  lea     r8, [rbp+47h+Source]; Source
0x180006b85  mov     r9d, eax; SourceSize
0x180006b88  mov     edx, eax; DestinationSize
0x180006b8a  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006b8e  call    cs:__imp_memcpy_s
0x180006b94  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006b98  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006b9c  lea     rcx, [rbp+47h+var_80]; this
0x180006ba0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006ba5  mov     byte ptr [rdi+38h], 1
0x180006ba9  jmp     loc_180006A7B
0x180006bae  xor     al, al
0x180006bb0  add     rsp, 0A8h
0x180006bb7  pop     r15
0x180006bb9  pop     r14
0x180006bbb  pop     r13
0x180006bbd  pop     r12
0x180006bbf  pop     rdi
0x180006bc0  pop     rsi
0x180006bc1  pop     rbx
0x180006bc2  pop     rbp
0x180006bc3  retn
```
