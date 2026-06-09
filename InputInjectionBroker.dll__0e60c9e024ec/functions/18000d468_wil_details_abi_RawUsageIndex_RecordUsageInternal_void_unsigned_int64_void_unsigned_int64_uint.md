# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000d468`
- end: `0x18000d7e8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d2b8`

## callees

- `0x18000a628`
- `0x18000cea0`
- `0x18000d468`
- `0x18000e8b4`
- `0x18001142e`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000d747`
- `msvcrt!memmove_s` at `0x18000d747`
- `msvcrt!memcpy_s` at `0x18000d573`
- `msvcrt!memcpy_s` at `0x18000d60c`
- `msvcrt!memcpy_s` at `0x18000d7b2`
- `msvcrt!memcpy_s` at `0x18000d573`
- `msvcrt!memcpy_s` at `0x18000d60c`
- `msvcrt!memcpy_s` at `0x18000d7b2`

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
0x18000d468  push    rbp
0x18000d46a  push    rbx
0x18000d46b  push    rsi
0x18000d46c  push    rdi
0x18000d46d  push    r12
0x18000d46f  push    r13
0x18000d471  push    r14
0x18000d473  push    r15
0x18000d475  lea     rbp, [rsp-0Fh]
0x18000d47a  sub     rsp, 0A8h
0x18000d481  mov     rbx, [rcx+18h]
0x18000d485  mov     rdi, rcx
0x18000d488  xor     ecx, ecx
0x18000d48a  mov     r13, r9
0x18000d48d  mov     r14, r8
0x18000d490  mov     r15, rdx
0x18000d493  test    rbx, rbx
0x18000d496  jz      loc_18000D7D2
0x18000d49c  movzx   eax, word ptr [rdi+2]
0x18000d4a0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d4a4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d4a8  add     rbx, 0Ah
0x18000d4ac  mov     [rbp+47h+var_A0], ax
0x18000d4b0  xorps   xmm0, xmm0
0x18000d4b3  mov     al, [rdi+4]
0x18000d4b6  mov     [rbp+47h+Source], ecx
0x18000d4b9  mov     [rbp+47h+var_98], cx
0x18000d4bd  mov     byte ptr [rbp+47h+arg_0], cl
0x18000d4c0  lea     rcx, [rbp+47h+var_A0]; this
0x18000d4c4  mov     [rbp+47h+var_9E], al
0x18000d4c7  mov     [rbp+47h+var_A8], rbx
0x18000d4cb  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000d4d0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d4d5  mov     r12, [rbp+47h+arg_20]
0x18000d4d9  jmp     loc_18000D627
0x18000d4de  movzx   eax, [rbp+47h+var_98]
0x18000d4e2  cmp     r14, rax
0x18000d4e5  jnz     short loc_18000D4FD
0x18000d4e7  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000d4eb  mov     r8, r14; Size
0x18000d4ee  mov     rcx, r15; Buf1
0x18000d4f1  call    memcmp_0
0x18000d4f6  mov     ecx, eax
0x18000d4f8  xor     r9d, r9d
0x18000d4fb  jmp     short loc_18000D506
0x18000d4fd  movzx   eax, [rbp+47h+var_98]
0x18000d501  mov     ecx, r14d
0x18000d504  sub     ecx, eax
0x18000d506  test    ecx, ecx
0x18000d508  js      loc_18000D6AC
0x18000d50e  jz      loc_18000D671
0x18000d514  mov     rbx, [rbp+47h+var_A8]
0x18000d518  mov     [rbp+47h+var_A8], rbx
0x18000d51c  cmp     [rdi+10h], r9
0x18000d520  jbe     short loc_18000D58B
0x18000d522  mov     rax, [rdi+20h]
0x18000d526  xor     edx, edx
0x18000d528  sub     rax, [rdi+18h]
0x18000d52c  mov     rsi, rbx
0x18000d52f  div     qword ptr [rdi+10h]
0x18000d533  mov     edx, [rbp+47h+Source]
0x18000d536  cmp     rdx, rax
0x18000d539  jbe     short loc_18000D57C
0x18000d53b  cmp     edx, eax
0x18000d53d  jz      short loc_18000D57C
0x18000d53f  mov     edx, eax
0x18000d541  mov     [rbp+47h+Source], eax
0x18000d544  mov     al, [rbp+47h+var_9E]
0x18000d547  cmp     al, 1
0x18000d549  jnz     short loc_18000D55E
0x18000d54b  movzx   eax, dx
0x18000d54e  mov     [rbp+47h+var_B0], dx
0x18000d552  mov     r9d, 2
0x18000d558  lea     r8, [rbp+47h+var_B0]
0x18000d55c  jmp     short loc_18000D56C
0x18000d55e  cmp     al, 2
0x18000d560  jnz     short loc_18000D57C
0x18000d562  mov     r9d, 4; SourceSize
0x18000d568  lea     r8, [rbp+47h+Source]; Source
0x18000d56c  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d570  mov     rdx, r9; DestinationSize
0x18000d573  call    cs:__imp_memcpy_s
0x18000d579  mov     edx, [rbp+47h+Source]
0x18000d57c  mov     ebx, edx
0x18000d57e  imul    rbx, [rdi+10h]
0x18000d583  add     rbx, rsi
0x18000d586  jmp     loc_18000D612
0x18000d58b  movzx   eax, word ptr [rdi+6]
0x18000d58f  xorps   xmm0, xmm0
0x18000d592  mov     [rbp+47h+var_60], ax
0x18000d596  mov     esi, r9d
0x18000d599  mov     al, [rdi+8]
0x18000d59c  mov     [rbp+47h+var_5E], al
0x18000d59f  mov     eax, [rbp+47h+Source]
0x18000d5a2  mov     [rbp+47h+var_5C], r9d
0x18000d5a6  mov     [rbp+47h+var_58], r9w
0x18000d5ab  movdqu  [rbp+47h+var_50], xmm0
0x18000d5b0  test    eax, eax
0x18000d5b2  jz      short loc_18000D5D6
0x18000d5b4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d5b8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d5bc  lea     rcx, [rbp+47h+var_60]; this
0x18000d5c0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d5c5  test    al, al
0x18000d5c7  mov     eax, [rbp+47h+Source]
0x18000d5ca  jz      short loc_18000D5D2
0x18000d5cc  inc     esi
0x18000d5ce  cmp     esi, eax
0x18000d5d0  jb      short loc_18000D5B4
0x18000d5d2  mov     rbx, [rbp+47h+var_A8]
0x18000d5d6  cmp     eax, esi
0x18000d5d8  jz      short loc_18000D612
0x18000d5da  mov     al, [rbp+47h+var_9E]
0x18000d5dd  mov     [rbp+47h+Source], esi
0x18000d5e0  cmp     al, 1
0x18000d5e2  jnz     short loc_18000D5F8
0x18000d5e4  mov     eax, 2
0x18000d5e9  mov     [rbp+47h+var_B0], si
0x18000d5ed  mov     r9d, eax
0x18000d5f0  lea     r8, [rbp+47h+var_B0]
0x18000d5f4  mov     edx, eax
0x18000d5f6  jmp     short loc_18000D608
0x18000d5f8  cmp     al, 2
0x18000d5fa  jnz     short loc_18000D612
0x18000d5fc  mov     edx, 4; DestinationSize
0x18000d601  lea     r8, [rbp+47h+Source]; Source
0x18000d605  mov     r9d, edx; SourceSize
0x18000d608  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d60c  call    cs:__imp_memcpy_s
0x18000d612  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d616  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d61a  lea     rcx, [rbp+47h+var_A0]; this
0x18000d61e  mov     [rbp+47h+var_A8], rbx
0x18000d622  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d627  xor     r9d, r9d
0x18000d62a  mov     sil, al
0x18000d62d  test    al, al
0x18000d62f  jnz     loc_18000D4DE
0x18000d635  mov     rbx, [rbp+47h+var_A8]
0x18000d639  mov     [rdi+20h], rbx
0x18000d63d  mov     rcx, r9
0x18000d640  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000d644  jnz     loc_18000D6CF
0x18000d64a  movzx   eax, [rbp+47h+var_A0]
0x18000d64e  mov     [rbp+47h+Source], 1
0x18000d655  mov     [rbp+47h+var_98], r14w
0x18000d65a  mov     [rbp+47h+Buf2], r9
0x18000d65e  mov     [rbp+47h+Buf2+8], r15
0x18000d662  test    ax, ax
0x18000d665  jnz     short loc_18000D6B7
0x18000d667  movzx   ecx, r14w
0x18000d66b  add     rcx, 2
0x18000d66f  jmp     short loc_18000D6BA
0x18000d671  mov     eax, [rbp+47h+arg_28]
0x18000d674  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000d678  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000d67c  mov     r9, r13; void *
0x18000d67f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000d683  mov     rcx, rdi; this
0x18000d686  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000d68b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000d690  xor     r9d, r9d
0x18000d693  mov     [rbp+47h+var_A8], rax
0x18000d697  mov     rbx, rax
0x18000d69a  test    rax, rax
0x18000d69d  jnz     short loc_18000D6A6
0x18000d69f  mov     al, 1
0x18000d6a1  jmp     loc_18000D7D4
0x18000d6a6  mov     byte ptr [rbp+47h+arg_0], 1
0x18000d6aa  jmp     short loc_18000D6B0
0x18000d6ac  mov     [rbp+47h+var_A8], rbx
0x18000d6b0  test    sil, sil
0x18000d6b3  jnz     short loc_18000D63D
0x18000d6b5  jmp     short loc_18000D639
0x18000d6b7  mov     rcx, rax
0x18000d6ba  mov     al, [rbp+47h+var_9E]
0x18000d6bd  cmp     al, 1
0x18000d6bf  jnz     short loc_18000D6C7
0x18000d6c1  add     rcx, 2
0x18000d6c5  jmp     short loc_18000D6CF
0x18000d6c7  cmp     al, 2
0x18000d6c9  jnz     short loc_18000D6CF
0x18000d6cb  add     rcx, 4
0x18000d6cf  movzx   eax, word ptr [rdi+6]
0x18000d6d3  mov     dl, [rdi+8]
0x18000d6d6  mov     r8d, [rbp+47h+arg_28]
0x18000d6da  mov     [rbp+47h+var_80], ax
0x18000d6de  mov     [rbp+47h+var_7E], dl
0x18000d6e1  mov     [rbp+47h+var_7C], r8d
0x18000d6e5  mov     [rbp+47h+var_78], r12w
0x18000d6ea  mov     [rbp+47h+var_70], r9
0x18000d6ee  mov     [rbp+47h+var_68], r13
0x18000d6f2  test    ax, ax
0x18000d6f5  jnz     short loc_18000D6FF
0x18000d6f7  movzx   eax, r12w
0x18000d6fb  add     rax, 2
0x18000d6ff  cmp     dl, 1
0x18000d702  jnz     short loc_18000D70A
0x18000d704  add     rax, 2
0x18000d708  jmp     short loc_18000D713
0x18000d70a  cmp     dl, 2
0x18000d70d  jnz     short loc_18000D713
0x18000d70f  add     rax, 4
0x18000d713  mov     rdx, [rdi+28h]
0x18000d717  lea     rsi, [rax+rcx]
0x18000d71b  mov     r9, [rdi+20h]
0x18000d71f  mov     rcx, rdx
0x18000d722  sub     rcx, r9
0x18000d725  cmp     r9, rdx
0x18000d728  sbb     rax, rax
0x18000d72b  and     rax, rcx
0x18000d72e  cmp     rax, rsi
0x18000d731  jb      loc_18000D7D2
0x18000d737  sub     rdx, rsi
0x18000d73a  lea     rcx, [rsi+rbx]; Destination
0x18000d73e  sub     rdx, rbx; DestinationSize
0x18000d741  sub     r9, rbx; SourceSize
0x18000d744  mov     r8, rbx; Source
0x18000d747  call    cs:__imp_memmove_s
0x18000d74d  add     [rdi+20h], rsi
0x18000d751  xor     ebx, ebx
0x18000d753  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000d756  jnz     short loc_18000D76B
0x18000d758  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d75c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d760  lea     rcx, [rbp+47h+var_A0]; this
0x18000d764  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000d769  jmp     short loc_18000D7B8
0x18000d76b  mov     cl, [rbp+47h+var_9E]
0x18000d76e  test    cl, cl
0x18000d770  jz      short loc_18000D7B8
0x18000d772  mov     eax, [rbp+47h+Source]
0x18000d775  lea     r8d, [rax+1]
0x18000d779  cmp     eax, r8d
0x18000d77c  jz      short loc_18000D7B8
0x18000d77e  mov     [rbp+47h+Source], r8d
0x18000d782  cmp     cl, 1
0x18000d785  jnz     short loc_18000D79B
0x18000d787  mov     r9d, 2
0x18000d78d  mov     [rbp+47h+arg_0], r8w
0x18000d792  mov     edx, r9d
0x18000d795  lea     r8, [rbp+47h+arg_0]
0x18000d799  jmp     short loc_18000D7AE
0x18000d79b  cmp     cl, 2
0x18000d79e  jnz     short loc_18000D7B8
0x18000d7a0  mov     eax, 4
0x18000d7a5  lea     r8, [rbp+47h+Source]; Source
0x18000d7a9  mov     r9d, eax; SourceSize
0x18000d7ac  mov     edx, eax; DestinationSize
0x18000d7ae  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d7b2  call    cs:__imp_memcpy_s
0x18000d7b8  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d7bc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d7c0  lea     rcx, [rbp+47h+var_80]; this
0x18000d7c4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000d7c9  mov     byte ptr [rdi+38h], 1
0x18000d7cd  jmp     loc_18000D69F
0x18000d7d2  xor     al, al
0x18000d7d4  add     rsp, 0A8h
0x18000d7db  pop     r15
0x18000d7dd  pop     r14
0x18000d7df  pop     r13
0x18000d7e1  pop     r12
0x18000d7e3  pop     rdi
0x18000d7e4  pop     rsi
0x18000d7e5  pop     rbx
0x18000d7e6  pop     rbp
0x18000d7e7  retn
```
