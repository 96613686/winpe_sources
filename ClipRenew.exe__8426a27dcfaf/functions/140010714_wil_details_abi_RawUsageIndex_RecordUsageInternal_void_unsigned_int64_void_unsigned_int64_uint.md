# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140010714`
- end: `0x140010a94`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140010564`

## callees

- `0x140006e4c`
- `0x14000ff5c`
- `0x140010714`
- `0x140011c3c`
- `0x140013456`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400109f3`
- `msvcrt!memmove_s` at `0x1400109f3`
- `msvcrt!memcpy_s` at `0x14001081f`
- `msvcrt!memcpy_s` at `0x1400108b8`
- `msvcrt!memcpy_s` at `0x140010a5e`
- `msvcrt!memcpy_s` at `0x14001081f`
- `msvcrt!memcpy_s` at `0x1400108b8`
- `msvcrt!memcpy_s` at `0x140010a5e`

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
0x140010714  push    rbp
0x140010716  push    rbx
0x140010717  push    rsi
0x140010718  push    rdi
0x140010719  push    r12
0x14001071b  push    r13
0x14001071d  push    r14
0x14001071f  push    r15
0x140010721  lea     rbp, [rsp-0Fh]
0x140010726  sub     rsp, 0A8h
0x14001072d  mov     rbx, [rcx+18h]
0x140010731  mov     rdi, rcx
0x140010734  xor     ecx, ecx
0x140010736  mov     r13, r9
0x140010739  mov     r14, r8
0x14001073c  mov     r15, rdx
0x14001073f  test    rbx, rbx
0x140010742  jz      loc_140010A7E
0x140010748  movzx   eax, word ptr [rdi+2]
0x14001074c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140010750  mov     r8, [rdi+20h]; unsigned __int8 *
0x140010754  add     rbx, 0Ah
0x140010758  mov     [rbp+47h+var_A0], ax
0x14001075c  xorps   xmm0, xmm0
0x14001075f  mov     al, [rdi+4]
0x140010762  mov     [rbp+47h+Source], ecx
0x140010765  mov     [rbp+47h+var_98], cx
0x140010769  mov     byte ptr [rbp+47h+arg_0], cl
0x14001076c  lea     rcx, [rbp+47h+var_A0]; this
0x140010770  mov     [rbp+47h+var_9E], al
0x140010773  mov     [rbp+47h+var_A8], rbx
0x140010777  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14001077c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140010781  mov     r12, [rbp+47h+arg_20]
0x140010785  jmp     loc_1400108D3
0x14001078a  movzx   eax, [rbp+47h+var_98]
0x14001078e  cmp     r14, rax
0x140010791  jnz     short loc_1400107A9
0x140010793  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140010797  mov     r8, r14; Size
0x14001079a  mov     rcx, r15; Buf1
0x14001079d  call    memcmp_0
0x1400107a2  mov     ecx, eax
0x1400107a4  xor     r9d, r9d
0x1400107a7  jmp     short loc_1400107B2
0x1400107a9  movzx   eax, [rbp+47h+var_98]
0x1400107ad  mov     ecx, r14d
0x1400107b0  sub     ecx, eax
0x1400107b2  test    ecx, ecx
0x1400107b4  js      loc_140010958
0x1400107ba  jz      loc_14001091D
0x1400107c0  mov     rbx, [rbp+47h+var_A8]
0x1400107c4  mov     [rbp+47h+var_A8], rbx
0x1400107c8  cmp     [rdi+10h], r9
0x1400107cc  jbe     short loc_140010837
0x1400107ce  mov     rax, [rdi+20h]
0x1400107d2  xor     edx, edx
0x1400107d4  sub     rax, [rdi+18h]
0x1400107d8  mov     rsi, rbx
0x1400107db  div     qword ptr [rdi+10h]
0x1400107df  mov     edx, [rbp+47h+Source]
0x1400107e2  cmp     rdx, rax
0x1400107e5  jbe     short loc_140010828
0x1400107e7  cmp     edx, eax
0x1400107e9  jz      short loc_140010828
0x1400107eb  mov     edx, eax
0x1400107ed  mov     [rbp+47h+Source], eax
0x1400107f0  mov     al, [rbp+47h+var_9E]
0x1400107f3  cmp     al, 1
0x1400107f5  jnz     short loc_14001080A
0x1400107f7  movzx   eax, dx
0x1400107fa  mov     [rbp+47h+var_B0], dx
0x1400107fe  mov     r9d, 2
0x140010804  lea     r8, [rbp+47h+var_B0]
0x140010808  jmp     short loc_140010818
0x14001080a  cmp     al, 2
0x14001080c  jnz     short loc_140010828
0x14001080e  mov     r9d, 4; SourceSize
0x140010814  lea     r8, [rbp+47h+Source]; Source
0x140010818  mov     rcx, [rbp+47h+Buf2]; Destination
0x14001081c  mov     rdx, r9; DestinationSize
0x14001081f  call    cs:__imp_memcpy_s
0x140010825  mov     edx, [rbp+47h+Source]
0x140010828  mov     ebx, edx
0x14001082a  imul    rbx, [rdi+10h]
0x14001082f  add     rbx, rsi
0x140010832  jmp     loc_1400108BE
0x140010837  movzx   eax, word ptr [rdi+6]
0x14001083b  xorps   xmm0, xmm0
0x14001083e  mov     [rbp+47h+var_60], ax
0x140010842  mov     esi, r9d
0x140010845  mov     al, [rdi+8]
0x140010848  mov     [rbp+47h+var_5E], al
0x14001084b  mov     eax, [rbp+47h+Source]
0x14001084e  mov     [rbp+47h+var_5C], r9d
0x140010852  mov     [rbp+47h+var_58], r9w
0x140010857  movdqu  [rbp+47h+var_50], xmm0
0x14001085c  test    eax, eax
0x14001085e  jz      short loc_140010882
0x140010860  mov     r8, [rdi+20h]; unsigned __int8 *
0x140010864  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140010868  lea     rcx, [rbp+47h+var_60]; this
0x14001086c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140010871  test    al, al
0x140010873  mov     eax, [rbp+47h+Source]
0x140010876  jz      short loc_14001087E
0x140010878  inc     esi
0x14001087a  cmp     esi, eax
0x14001087c  jb      short loc_140010860
0x14001087e  mov     rbx, [rbp+47h+var_A8]
0x140010882  cmp     eax, esi
0x140010884  jz      short loc_1400108BE
0x140010886  mov     al, [rbp+47h+var_9E]
0x140010889  mov     [rbp+47h+Source], esi
0x14001088c  cmp     al, 1
0x14001088e  jnz     short loc_1400108A4
0x140010890  mov     eax, 2
0x140010895  mov     [rbp+47h+var_B0], si
0x140010899  mov     r9d, eax
0x14001089c  lea     r8, [rbp+47h+var_B0]
0x1400108a0  mov     edx, eax
0x1400108a2  jmp     short loc_1400108B4
0x1400108a4  cmp     al, 2
0x1400108a6  jnz     short loc_1400108BE
0x1400108a8  mov     edx, 4; DestinationSize
0x1400108ad  lea     r8, [rbp+47h+Source]; Source
0x1400108b1  mov     r9d, edx; SourceSize
0x1400108b4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400108b8  call    cs:__imp_memcpy_s
0x1400108be  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400108c2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400108c6  lea     rcx, [rbp+47h+var_A0]; this
0x1400108ca  mov     [rbp+47h+var_A8], rbx
0x1400108ce  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400108d3  xor     r9d, r9d
0x1400108d6  mov     sil, al
0x1400108d9  test    al, al
0x1400108db  jnz     loc_14001078A
0x1400108e1  mov     rbx, [rbp+47h+var_A8]
0x1400108e5  mov     [rdi+20h], rbx
0x1400108e9  mov     rcx, r9
0x1400108ec  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1400108f0  jnz     loc_14001097B
0x1400108f6  movzx   eax, [rbp+47h+var_A0]
0x1400108fa  mov     [rbp+47h+Source], 1
0x140010901  mov     [rbp+47h+var_98], r14w
0x140010906  mov     [rbp+47h+Buf2], r9
0x14001090a  mov     [rbp+47h+Buf2+8], r15
0x14001090e  test    ax, ax
0x140010911  jnz     short loc_140010963
0x140010913  movzx   ecx, r14w
0x140010917  add     rcx, 2
0x14001091b  jmp     short loc_140010966
0x14001091d  mov     eax, [rbp+47h+arg_28]
0x140010920  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140010924  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x140010928  mov     r9, r13; void *
0x14001092b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14001092f  mov     rcx, rdi; this
0x140010932  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140010937  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14001093c  xor     r9d, r9d
0x14001093f  mov     [rbp+47h+var_A8], rax
0x140010943  mov     rbx, rax
0x140010946  test    rax, rax
0x140010949  jnz     short loc_140010952
0x14001094b  mov     al, 1
0x14001094d  jmp     loc_140010A80
0x140010952  mov     byte ptr [rbp+47h+arg_0], 1
0x140010956  jmp     short loc_14001095C
0x140010958  mov     [rbp+47h+var_A8], rbx
0x14001095c  test    sil, sil
0x14001095f  jnz     short loc_1400108E9
0x140010961  jmp     short loc_1400108E5
0x140010963  mov     rcx, rax
0x140010966  mov     al, [rbp+47h+var_9E]
0x140010969  cmp     al, 1
0x14001096b  jnz     short loc_140010973
0x14001096d  add     rcx, 2
0x140010971  jmp     short loc_14001097B
0x140010973  cmp     al, 2
0x140010975  jnz     short loc_14001097B
0x140010977  add     rcx, 4
0x14001097b  movzx   eax, word ptr [rdi+6]
0x14001097f  mov     dl, [rdi+8]
0x140010982  mov     r8d, [rbp+47h+arg_28]
0x140010986  mov     [rbp+47h+var_80], ax
0x14001098a  mov     [rbp+47h+var_7E], dl
0x14001098d  mov     [rbp+47h+var_7C], r8d
0x140010991  mov     [rbp+47h+var_78], r12w
0x140010996  mov     [rbp+47h+var_70], r9
0x14001099a  mov     [rbp+47h+var_68], r13
0x14001099e  test    ax, ax
0x1400109a1  jnz     short loc_1400109AB
0x1400109a3  movzx   eax, r12w
0x1400109a7  add     rax, 2
0x1400109ab  cmp     dl, 1
0x1400109ae  jnz     short loc_1400109B6
0x1400109b0  add     rax, 2
0x1400109b4  jmp     short loc_1400109BF
0x1400109b6  cmp     dl, 2
0x1400109b9  jnz     short loc_1400109BF
0x1400109bb  add     rax, 4
0x1400109bf  mov     rdx, [rdi+28h]
0x1400109c3  lea     rsi, [rax+rcx]
0x1400109c7  mov     r9, [rdi+20h]
0x1400109cb  mov     rcx, rdx
0x1400109ce  sub     rcx, r9
0x1400109d1  cmp     r9, rdx
0x1400109d4  sbb     rax, rax
0x1400109d7  and     rax, rcx
0x1400109da  cmp     rax, rsi
0x1400109dd  jb      loc_140010A7E
0x1400109e3  sub     rdx, rsi
0x1400109e6  lea     rcx, [rsi+rbx]; Destination
0x1400109ea  sub     rdx, rbx; DestinationSize
0x1400109ed  sub     r9, rbx; SourceSize
0x1400109f0  mov     r8, rbx; Source
0x1400109f3  call    cs:__imp_memmove_s
0x1400109f9  add     [rdi+20h], rsi
0x1400109fd  xor     ebx, ebx
0x1400109ff  cmp     byte ptr [rbp+47h+arg_0], bl
0x140010a02  jnz     short loc_140010A17
0x140010a04  mov     r8, [rdi+20h]; unsigned __int8 *
0x140010a08  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140010a0c  lea     rcx, [rbp+47h+var_A0]; this
0x140010a10  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140010a15  jmp     short loc_140010A64
0x140010a17  mov     cl, [rbp+47h+var_9E]
0x140010a1a  test    cl, cl
0x140010a1c  jz      short loc_140010A64
0x140010a1e  mov     eax, [rbp+47h+Source]
0x140010a21  lea     r8d, [rax+1]
0x140010a25  cmp     eax, r8d
0x140010a28  jz      short loc_140010A64
0x140010a2a  mov     [rbp+47h+Source], r8d
0x140010a2e  cmp     cl, 1
0x140010a31  jnz     short loc_140010A47
0x140010a33  mov     r9d, 2
0x140010a39  mov     [rbp+47h+arg_0], r8w
0x140010a3e  mov     edx, r9d
0x140010a41  lea     r8, [rbp+47h+arg_0]
0x140010a45  jmp     short loc_140010A5A
0x140010a47  cmp     cl, 2
0x140010a4a  jnz     short loc_140010A64
0x140010a4c  mov     eax, 4
0x140010a51  lea     r8, [rbp+47h+Source]; Source
0x140010a55  mov     r9d, eax; SourceSize
0x140010a58  mov     edx, eax; DestinationSize
0x140010a5a  mov     rcx, [rbp+47h+Buf2]; Destination
0x140010a5e  call    cs:__imp_memcpy_s
0x140010a64  mov     r8, [rdi+20h]; unsigned __int8 *
0x140010a68  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140010a6c  lea     rcx, [rbp+47h+var_80]; this
0x140010a70  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140010a75  mov     byte ptr [rdi+38h], 1
0x140010a79  jmp     loc_14001094B
0x140010a7e  xor     al, al
0x140010a80  add     rsp, 0A8h
0x140010a87  pop     r15
0x140010a89  pop     r14
0x140010a8b  pop     r13
0x140010a8d  pop     r12
0x140010a8f  pop     rdi
0x140010a90  pop     rsi
0x140010a91  pop     rbx
0x140010a92  pop     rbp
0x140010a93  retn
```
