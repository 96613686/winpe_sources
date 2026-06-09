# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800082c0`
- end: `0x180008640`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008110`

## callees

- `0x18000656c`
- `0x180007c8c`
- `0x1800082c0`
- `0x180009bbc`
- `0x18000a186`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000859f`
- `msvcrt!memmove_s` at `0x18000859f`
- `msvcrt!memcpy_s` at `0x1800083cb`
- `msvcrt!memcpy_s` at `0x180008464`
- `msvcrt!memcpy_s` at `0x18000860a`
- `msvcrt!memcpy_s` at `0x1800083cb`
- `msvcrt!memcpy_s` at `0x180008464`
- `msvcrt!memcpy_s` at `0x18000860a`

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
0x1800082c0  push    rbp
0x1800082c2  push    rbx
0x1800082c3  push    rsi
0x1800082c4  push    rdi
0x1800082c5  push    r12
0x1800082c7  push    r13
0x1800082c9  push    r14
0x1800082cb  push    r15
0x1800082cd  lea     rbp, [rsp-0Fh]
0x1800082d2  sub     rsp, 0A8h
0x1800082d9  mov     rbx, [rcx+18h]
0x1800082dd  mov     rdi, rcx
0x1800082e0  xor     ecx, ecx
0x1800082e2  mov     r13, r9
0x1800082e5  mov     r14, r8
0x1800082e8  mov     r15, rdx
0x1800082eb  test    rbx, rbx
0x1800082ee  jz      loc_18000862A
0x1800082f4  movzx   eax, word ptr [rdi+2]
0x1800082f8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800082fc  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008300  add     rbx, 0Ah
0x180008304  mov     [rbp+47h+var_A0], ax
0x180008308  xorps   xmm0, xmm0
0x18000830b  mov     al, [rdi+4]
0x18000830e  mov     [rbp+47h+Source], ecx
0x180008311  mov     [rbp+47h+var_98], cx
0x180008315  mov     byte ptr [rbp+47h+arg_0], cl
0x180008318  lea     rcx, [rbp+47h+var_A0]; this
0x18000831c  mov     [rbp+47h+var_9E], al
0x18000831f  mov     [rbp+47h+var_A8], rbx
0x180008323  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180008328  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000832d  mov     r12, [rbp+47h+arg_20]
0x180008331  jmp     loc_18000847F
0x180008336  movzx   eax, [rbp+47h+var_98]
0x18000833a  cmp     r14, rax
0x18000833d  jnz     short loc_180008355
0x18000833f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180008343  mov     r8, r14; Size
0x180008346  mov     rcx, r15; Buf1
0x180008349  call    memcmp_0
0x18000834e  mov     ecx, eax
0x180008350  xor     r9d, r9d
0x180008353  jmp     short loc_18000835E
0x180008355  movzx   eax, [rbp+47h+var_98]
0x180008359  mov     ecx, r14d
0x18000835c  sub     ecx, eax
0x18000835e  test    ecx, ecx
0x180008360  js      loc_180008504
0x180008366  jz      loc_1800084C9
0x18000836c  mov     rbx, [rbp+47h+var_A8]
0x180008370  mov     [rbp+47h+var_A8], rbx
0x180008374  cmp     [rdi+10h], r9
0x180008378  jbe     short loc_1800083E3
0x18000837a  mov     rax, [rdi+20h]
0x18000837e  xor     edx, edx
0x180008380  sub     rax, [rdi+18h]
0x180008384  mov     rsi, rbx
0x180008387  div     qword ptr [rdi+10h]
0x18000838b  mov     edx, [rbp+47h+Source]
0x18000838e  cmp     rdx, rax
0x180008391  jbe     short loc_1800083D4
0x180008393  cmp     edx, eax
0x180008395  jz      short loc_1800083D4
0x180008397  mov     edx, eax
0x180008399  mov     [rbp+47h+Source], eax
0x18000839c  mov     al, [rbp+47h+var_9E]
0x18000839f  cmp     al, 1
0x1800083a1  jnz     short loc_1800083B6
0x1800083a3  movzx   eax, dx
0x1800083a6  mov     [rbp+47h+var_B0], dx
0x1800083aa  mov     r9d, 2
0x1800083b0  lea     r8, [rbp+47h+var_B0]
0x1800083b4  jmp     short loc_1800083C4
0x1800083b6  cmp     al, 2
0x1800083b8  jnz     short loc_1800083D4
0x1800083ba  mov     r9d, 4; SourceSize
0x1800083c0  lea     r8, [rbp+47h+Source]; Source
0x1800083c4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800083c8  mov     rdx, r9; DestinationSize
0x1800083cb  call    cs:__imp_memcpy_s
0x1800083d1  mov     edx, [rbp+47h+Source]
0x1800083d4  mov     ebx, edx
0x1800083d6  imul    rbx, [rdi+10h]
0x1800083db  add     rbx, rsi
0x1800083de  jmp     loc_18000846A
0x1800083e3  movzx   eax, word ptr [rdi+6]
0x1800083e7  xorps   xmm0, xmm0
0x1800083ea  mov     [rbp+47h+var_60], ax
0x1800083ee  mov     esi, r9d
0x1800083f1  mov     al, [rdi+8]
0x1800083f4  mov     [rbp+47h+var_5E], al
0x1800083f7  mov     eax, [rbp+47h+Source]
0x1800083fa  mov     [rbp+47h+var_5C], r9d
0x1800083fe  mov     [rbp+47h+var_58], r9w
0x180008403  movdqu  [rbp+47h+var_50], xmm0
0x180008408  test    eax, eax
0x18000840a  jz      short loc_18000842E
0x18000840c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008410  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008414  lea     rcx, [rbp+47h+var_60]; this
0x180008418  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000841d  test    al, al
0x18000841f  mov     eax, [rbp+47h+Source]
0x180008422  jz      short loc_18000842A
0x180008424  inc     esi
0x180008426  cmp     esi, eax
0x180008428  jb      short loc_18000840C
0x18000842a  mov     rbx, [rbp+47h+var_A8]
0x18000842e  cmp     eax, esi
0x180008430  jz      short loc_18000846A
0x180008432  mov     al, [rbp+47h+var_9E]
0x180008435  mov     [rbp+47h+Source], esi
0x180008438  cmp     al, 1
0x18000843a  jnz     short loc_180008450
0x18000843c  mov     eax, 2
0x180008441  mov     [rbp+47h+var_B0], si
0x180008445  mov     r9d, eax
0x180008448  lea     r8, [rbp+47h+var_B0]
0x18000844c  mov     edx, eax
0x18000844e  jmp     short loc_180008460
0x180008450  cmp     al, 2
0x180008452  jnz     short loc_18000846A
0x180008454  mov     edx, 4; DestinationSize
0x180008459  lea     r8, [rbp+47h+Source]; Source
0x18000845d  mov     r9d, edx; SourceSize
0x180008460  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008464  call    cs:__imp_memcpy_s
0x18000846a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000846e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008472  lea     rcx, [rbp+47h+var_A0]; this
0x180008476  mov     [rbp+47h+var_A8], rbx
0x18000847a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000847f  xor     r9d, r9d
0x180008482  mov     sil, al
0x180008485  test    al, al
0x180008487  jnz     loc_180008336
0x18000848d  mov     rbx, [rbp+47h+var_A8]
0x180008491  mov     [rdi+20h], rbx
0x180008495  mov     rcx, r9
0x180008498  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000849c  jnz     loc_180008527
0x1800084a2  movzx   eax, [rbp+47h+var_A0]
0x1800084a6  mov     [rbp+47h+Source], 1
0x1800084ad  mov     [rbp+47h+var_98], r14w
0x1800084b2  mov     [rbp+47h+Buf2], r9
0x1800084b6  mov     [rbp+47h+Buf2+8], r15
0x1800084ba  test    ax, ax
0x1800084bd  jnz     short loc_18000850F
0x1800084bf  movzx   ecx, r14w
0x1800084c3  add     rcx, 2
0x1800084c7  jmp     short loc_180008512
0x1800084c9  mov     eax, [rbp+47h+arg_28]
0x1800084cc  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1800084d0  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800084d4  mov     r9, r13; void *
0x1800084d7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800084db  mov     rcx, rdi; this
0x1800084de  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800084e3  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800084e8  xor     r9d, r9d
0x1800084eb  mov     [rbp+47h+var_A8], rax
0x1800084ef  mov     rbx, rax
0x1800084f2  test    rax, rax
0x1800084f5  jnz     short loc_1800084FE
0x1800084f7  mov     al, 1
0x1800084f9  jmp     loc_18000862C
0x1800084fe  mov     byte ptr [rbp+47h+arg_0], 1
0x180008502  jmp     short loc_180008508
0x180008504  mov     [rbp+47h+var_A8], rbx
0x180008508  test    sil, sil
0x18000850b  jnz     short loc_180008495
0x18000850d  jmp     short loc_180008491
0x18000850f  mov     rcx, rax
0x180008512  mov     al, [rbp+47h+var_9E]
0x180008515  cmp     al, 1
0x180008517  jnz     short loc_18000851F
0x180008519  add     rcx, 2
0x18000851d  jmp     short loc_180008527
0x18000851f  cmp     al, 2
0x180008521  jnz     short loc_180008527
0x180008523  add     rcx, 4
0x180008527  movzx   eax, word ptr [rdi+6]
0x18000852b  mov     dl, [rdi+8]
0x18000852e  mov     r8d, [rbp+47h+arg_28]
0x180008532  mov     [rbp+47h+var_80], ax
0x180008536  mov     [rbp+47h+var_7E], dl
0x180008539  mov     [rbp+47h+var_7C], r8d
0x18000853d  mov     [rbp+47h+var_78], r12w
0x180008542  mov     [rbp+47h+var_70], r9
0x180008546  mov     [rbp+47h+var_68], r13
0x18000854a  test    ax, ax
0x18000854d  jnz     short loc_180008557
0x18000854f  movzx   eax, r12w
0x180008553  add     rax, 2
0x180008557  cmp     dl, 1
0x18000855a  jnz     short loc_180008562
0x18000855c  add     rax, 2
0x180008560  jmp     short loc_18000856B
0x180008562  cmp     dl, 2
0x180008565  jnz     short loc_18000856B
0x180008567  add     rax, 4
0x18000856b  mov     rdx, [rdi+28h]
0x18000856f  lea     rsi, [rax+rcx]
0x180008573  mov     r9, [rdi+20h]
0x180008577  mov     rcx, rdx
0x18000857a  sub     rcx, r9
0x18000857d  cmp     r9, rdx
0x180008580  sbb     rax, rax
0x180008583  and     rax, rcx
0x180008586  cmp     rax, rsi
0x180008589  jb      loc_18000862A
0x18000858f  sub     rdx, rsi
0x180008592  lea     rcx, [rsi+rbx]; Destination
0x180008596  sub     rdx, rbx; DestinationSize
0x180008599  sub     r9, rbx; SourceSize
0x18000859c  mov     r8, rbx; Source
0x18000859f  call    cs:__imp_memmove_s
0x1800085a5  add     [rdi+20h], rsi
0x1800085a9  xor     ebx, ebx
0x1800085ab  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800085ae  jnz     short loc_1800085C3
0x1800085b0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800085b4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800085b8  lea     rcx, [rbp+47h+var_A0]; this
0x1800085bc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800085c1  jmp     short loc_180008610
0x1800085c3  mov     cl, [rbp+47h+var_9E]
0x1800085c6  test    cl, cl
0x1800085c8  jz      short loc_180008610
0x1800085ca  mov     eax, [rbp+47h+Source]
0x1800085cd  lea     r8d, [rax+1]
0x1800085d1  cmp     eax, r8d
0x1800085d4  jz      short loc_180008610
0x1800085d6  mov     [rbp+47h+Source], r8d
0x1800085da  cmp     cl, 1
0x1800085dd  jnz     short loc_1800085F3
0x1800085df  mov     r9d, 2
0x1800085e5  mov     [rbp+47h+arg_0], r8w
0x1800085ea  mov     edx, r9d
0x1800085ed  lea     r8, [rbp+47h+arg_0]
0x1800085f1  jmp     short loc_180008606
0x1800085f3  cmp     cl, 2
0x1800085f6  jnz     short loc_180008610
0x1800085f8  mov     eax, 4
0x1800085fd  lea     r8, [rbp+47h+Source]; Source
0x180008601  mov     r9d, eax; SourceSize
0x180008604  mov     edx, eax; DestinationSize
0x180008606  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000860a  call    cs:__imp_memcpy_s
0x180008610  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008614  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008618  lea     rcx, [rbp+47h+var_80]; this
0x18000861c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008621  mov     byte ptr [rdi+38h], 1
0x180008625  jmp     loc_1800084F7
0x18000862a  xor     al, al
0x18000862c  add     rsp, 0A8h
0x180008633  pop     r15
0x180008635  pop     r14
0x180008637  pop     r13
0x180008639  pop     r12
0x18000863b  pop     rdi
0x18000863c  pop     rsi
0x18000863d  pop     rbx
0x18000863e  pop     rbp
0x18000863f  retn
```
