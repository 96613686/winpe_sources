# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b688`
- end: `0x14000ba08`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b4d8`

## callees

- `0x140009dec`
- `0x14000aecc`
- `0x14000b688`
- `0x14000d38c`
- `0x14000e196`

## import_xrefs

- `msvcrt!memmove_s` at `0x14000b967`
- `msvcrt!memmove_s` at `0x14000b967`
- `msvcrt!memcpy_s` at `0x14000b793`
- `msvcrt!memcpy_s` at `0x14000b82c`
- `msvcrt!memcpy_s` at `0x14000b9d2`
- `msvcrt!memcpy_s` at `0x14000b793`
- `msvcrt!memcpy_s` at `0x14000b82c`
- `msvcrt!memcpy_s` at `0x14000b9d2`

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
0x14000b688  push    rbp
0x14000b68a  push    rbx
0x14000b68b  push    rsi
0x14000b68c  push    rdi
0x14000b68d  push    r12
0x14000b68f  push    r13
0x14000b691  push    r14
0x14000b693  push    r15
0x14000b695  lea     rbp, [rsp-0Fh]
0x14000b69a  sub     rsp, 0A8h
0x14000b6a1  mov     rbx, [rcx+18h]
0x14000b6a5  mov     rdi, rcx
0x14000b6a8  xor     ecx, ecx
0x14000b6aa  mov     r13, r9
0x14000b6ad  mov     r14, r8
0x14000b6b0  mov     r15, rdx
0x14000b6b3  test    rbx, rbx
0x14000b6b6  jz      loc_14000B9F2
0x14000b6bc  movzx   eax, word ptr [rdi+2]
0x14000b6c0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b6c4  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b6c8  add     rbx, 0Ah
0x14000b6cc  mov     [rbp+47h+var_A0], ax
0x14000b6d0  xorps   xmm0, xmm0
0x14000b6d3  mov     al, [rdi+4]
0x14000b6d6  mov     [rbp+47h+Source], ecx
0x14000b6d9  mov     [rbp+47h+var_98], cx
0x14000b6dd  mov     byte ptr [rbp+47h+arg_0], cl
0x14000b6e0  lea     rcx, [rbp+47h+var_A0]; this
0x14000b6e4  mov     [rbp+47h+var_9E], al
0x14000b6e7  mov     [rbp+47h+var_A8], rbx
0x14000b6eb  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14000b6f0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b6f5  mov     r12, [rbp+47h+arg_20]
0x14000b6f9  jmp     loc_14000B847
0x14000b6fe  movzx   eax, [rbp+47h+var_98]
0x14000b702  cmp     r14, rax
0x14000b705  jnz     short loc_14000B71D
0x14000b707  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14000b70b  mov     r8, r14; Size
0x14000b70e  mov     rcx, r15; Buf1
0x14000b711  call    memcmp_0
0x14000b716  mov     ecx, eax
0x14000b718  xor     r9d, r9d
0x14000b71b  jmp     short loc_14000B726
0x14000b71d  movzx   eax, [rbp+47h+var_98]
0x14000b721  mov     ecx, r14d
0x14000b724  sub     ecx, eax
0x14000b726  test    ecx, ecx
0x14000b728  js      loc_14000B8CC
0x14000b72e  jz      loc_14000B891
0x14000b734  mov     rbx, [rbp+47h+var_A8]
0x14000b738  mov     [rbp+47h+var_A8], rbx
0x14000b73c  cmp     [rdi+10h], r9
0x14000b740  jbe     short loc_14000B7AB
0x14000b742  mov     rax, [rdi+20h]
0x14000b746  xor     edx, edx
0x14000b748  sub     rax, [rdi+18h]
0x14000b74c  mov     rsi, rbx
0x14000b74f  div     qword ptr [rdi+10h]
0x14000b753  mov     edx, [rbp+47h+Source]
0x14000b756  cmp     rdx, rax
0x14000b759  jbe     short loc_14000B79C
0x14000b75b  cmp     edx, eax
0x14000b75d  jz      short loc_14000B79C
0x14000b75f  mov     edx, eax
0x14000b761  mov     [rbp+47h+Source], eax
0x14000b764  mov     al, [rbp+47h+var_9E]
0x14000b767  cmp     al, 1
0x14000b769  jnz     short loc_14000B77E
0x14000b76b  movzx   eax, dx
0x14000b76e  mov     [rbp+47h+var_B0], dx
0x14000b772  mov     r9d, 2
0x14000b778  lea     r8, [rbp+47h+var_B0]
0x14000b77c  jmp     short loc_14000B78C
0x14000b77e  cmp     al, 2
0x14000b780  jnz     short loc_14000B79C
0x14000b782  mov     r9d, 4; SourceSize
0x14000b788  lea     r8, [rbp+47h+Source]; Source
0x14000b78c  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000b790  mov     rdx, r9; DestinationSize
0x14000b793  call    cs:__imp_memcpy_s
0x14000b799  mov     edx, [rbp+47h+Source]
0x14000b79c  mov     ebx, edx
0x14000b79e  imul    rbx, [rdi+10h]
0x14000b7a3  add     rbx, rsi
0x14000b7a6  jmp     loc_14000B832
0x14000b7ab  movzx   eax, word ptr [rdi+6]
0x14000b7af  xorps   xmm0, xmm0
0x14000b7b2  mov     [rbp+47h+var_60], ax
0x14000b7b6  mov     esi, r9d
0x14000b7b9  mov     al, [rdi+8]
0x14000b7bc  mov     [rbp+47h+var_5E], al
0x14000b7bf  mov     eax, [rbp+47h+Source]
0x14000b7c2  mov     [rbp+47h+var_5C], r9d
0x14000b7c6  mov     [rbp+47h+var_58], r9w
0x14000b7cb  movdqu  [rbp+47h+var_50], xmm0
0x14000b7d0  test    eax, eax
0x14000b7d2  jz      short loc_14000B7F6
0x14000b7d4  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b7d8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b7dc  lea     rcx, [rbp+47h+var_60]; this
0x14000b7e0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b7e5  test    al, al
0x14000b7e7  mov     eax, [rbp+47h+Source]
0x14000b7ea  jz      short loc_14000B7F2
0x14000b7ec  inc     esi
0x14000b7ee  cmp     esi, eax
0x14000b7f0  jb      short loc_14000B7D4
0x14000b7f2  mov     rbx, [rbp+47h+var_A8]
0x14000b7f6  cmp     eax, esi
0x14000b7f8  jz      short loc_14000B832
0x14000b7fa  mov     al, [rbp+47h+var_9E]
0x14000b7fd  mov     [rbp+47h+Source], esi
0x14000b800  cmp     al, 1
0x14000b802  jnz     short loc_14000B818
0x14000b804  mov     eax, 2
0x14000b809  mov     [rbp+47h+var_B0], si
0x14000b80d  mov     r9d, eax
0x14000b810  lea     r8, [rbp+47h+var_B0]
0x14000b814  mov     edx, eax
0x14000b816  jmp     short loc_14000B828
0x14000b818  cmp     al, 2
0x14000b81a  jnz     short loc_14000B832
0x14000b81c  mov     edx, 4; DestinationSize
0x14000b821  lea     r8, [rbp+47h+Source]; Source
0x14000b825  mov     r9d, edx; SourceSize
0x14000b828  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000b82c  call    cs:__imp_memcpy_s
0x14000b832  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b836  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b83a  lea     rcx, [rbp+47h+var_A0]; this
0x14000b83e  mov     [rbp+47h+var_A8], rbx
0x14000b842  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b847  xor     r9d, r9d
0x14000b84a  mov     sil, al
0x14000b84d  test    al, al
0x14000b84f  jnz     loc_14000B6FE
0x14000b855  mov     rbx, [rbp+47h+var_A8]
0x14000b859  mov     [rdi+20h], rbx
0x14000b85d  mov     rcx, r9
0x14000b860  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14000b864  jnz     loc_14000B8EF
0x14000b86a  movzx   eax, [rbp+47h+var_A0]
0x14000b86e  mov     [rbp+47h+Source], 1
0x14000b875  mov     [rbp+47h+var_98], r14w
0x14000b87a  mov     [rbp+47h+Buf2], r9
0x14000b87e  mov     [rbp+47h+Buf2+8], r15
0x14000b882  test    ax, ax
0x14000b885  jnz     short loc_14000B8D7
0x14000b887  movzx   ecx, r14w
0x14000b88b  add     rcx, 2
0x14000b88f  jmp     short loc_14000B8DA
0x14000b891  mov     eax, [rbp+47h+arg_28]
0x14000b894  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x14000b898  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x14000b89c  mov     r9, r13; void *
0x14000b89f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14000b8a3  mov     rcx, rdi; this
0x14000b8a6  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x14000b8ab  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14000b8b0  xor     r9d, r9d
0x14000b8b3  mov     [rbp+47h+var_A8], rax
0x14000b8b7  mov     rbx, rax
0x14000b8ba  test    rax, rax
0x14000b8bd  jnz     short loc_14000B8C6
0x14000b8bf  mov     al, 1
0x14000b8c1  jmp     loc_14000B9F4
0x14000b8c6  mov     byte ptr [rbp+47h+arg_0], 1
0x14000b8ca  jmp     short loc_14000B8D0
0x14000b8cc  mov     [rbp+47h+var_A8], rbx
0x14000b8d0  test    sil, sil
0x14000b8d3  jnz     short loc_14000B85D
0x14000b8d5  jmp     short loc_14000B859
0x14000b8d7  mov     rcx, rax
0x14000b8da  mov     al, [rbp+47h+var_9E]
0x14000b8dd  cmp     al, 1
0x14000b8df  jnz     short loc_14000B8E7
0x14000b8e1  add     rcx, 2
0x14000b8e5  jmp     short loc_14000B8EF
0x14000b8e7  cmp     al, 2
0x14000b8e9  jnz     short loc_14000B8EF
0x14000b8eb  add     rcx, 4
0x14000b8ef  movzx   eax, word ptr [rdi+6]
0x14000b8f3  mov     dl, [rdi+8]
0x14000b8f6  mov     r8d, [rbp+47h+arg_28]
0x14000b8fa  mov     [rbp+47h+var_80], ax
0x14000b8fe  mov     [rbp+47h+var_7E], dl
0x14000b901  mov     [rbp+47h+var_7C], r8d
0x14000b905  mov     [rbp+47h+var_78], r12w
0x14000b90a  mov     [rbp+47h+var_70], r9
0x14000b90e  mov     [rbp+47h+var_68], r13
0x14000b912  test    ax, ax
0x14000b915  jnz     short loc_14000B91F
0x14000b917  movzx   eax, r12w
0x14000b91b  add     rax, 2
0x14000b91f  cmp     dl, 1
0x14000b922  jnz     short loc_14000B92A
0x14000b924  add     rax, 2
0x14000b928  jmp     short loc_14000B933
0x14000b92a  cmp     dl, 2
0x14000b92d  jnz     short loc_14000B933
0x14000b92f  add     rax, 4
0x14000b933  mov     rdx, [rdi+28h]
0x14000b937  lea     rsi, [rax+rcx]
0x14000b93b  mov     r9, [rdi+20h]
0x14000b93f  mov     rcx, rdx
0x14000b942  sub     rcx, r9
0x14000b945  cmp     r9, rdx
0x14000b948  sbb     rax, rax
0x14000b94b  and     rax, rcx
0x14000b94e  cmp     rax, rsi
0x14000b951  jb      loc_14000B9F2
0x14000b957  sub     rdx, rsi
0x14000b95a  lea     rcx, [rsi+rbx]; Destination
0x14000b95e  sub     rdx, rbx; DestinationSize
0x14000b961  sub     r9, rbx; SourceSize
0x14000b964  mov     r8, rbx; Source
0x14000b967  call    cs:__imp_memmove_s
0x14000b96d  add     [rdi+20h], rsi
0x14000b971  xor     ebx, ebx
0x14000b973  cmp     byte ptr [rbp+47h+arg_0], bl
0x14000b976  jnz     short loc_14000B98B
0x14000b978  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b97c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b980  lea     rcx, [rbp+47h+var_A0]; this
0x14000b984  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000b989  jmp     short loc_14000B9D8
0x14000b98b  mov     cl, [rbp+47h+var_9E]
0x14000b98e  test    cl, cl
0x14000b990  jz      short loc_14000B9D8
0x14000b992  mov     eax, [rbp+47h+Source]
0x14000b995  lea     r8d, [rax+1]
0x14000b999  cmp     eax, r8d
0x14000b99c  jz      short loc_14000B9D8
0x14000b99e  mov     [rbp+47h+Source], r8d
0x14000b9a2  cmp     cl, 1
0x14000b9a5  jnz     short loc_14000B9BB
0x14000b9a7  mov     r9d, 2
0x14000b9ad  mov     [rbp+47h+arg_0], r8w
0x14000b9b2  mov     edx, r9d
0x14000b9b5  lea     r8, [rbp+47h+arg_0]
0x14000b9b9  jmp     short loc_14000B9CE
0x14000b9bb  cmp     cl, 2
0x14000b9be  jnz     short loc_14000B9D8
0x14000b9c0  mov     eax, 4
0x14000b9c5  lea     r8, [rbp+47h+Source]; Source
0x14000b9c9  mov     r9d, eax; SourceSize
0x14000b9cc  mov     edx, eax; DestinationSize
0x14000b9ce  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000b9d2  call    cs:__imp_memcpy_s
0x14000b9d8  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b9dc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b9e0  lea     rcx, [rbp+47h+var_80]; this
0x14000b9e4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000b9e9  mov     byte ptr [rdi+38h], 1
0x14000b9ed  jmp     loc_14000B8BF
0x14000b9f2  xor     al, al
0x14000b9f4  add     rsp, 0A8h
0x14000b9fb  pop     r15
0x14000b9fd  pop     r14
0x14000b9ff  pop     r13
0x14000ba01  pop     r12
0x14000ba03  pop     rdi
0x14000ba04  pop     rsi
0x14000ba05  pop     rbx
0x14000ba06  pop     rbp
0x14000ba07  retn
```
