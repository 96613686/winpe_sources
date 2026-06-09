# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000b594`
- end: `0x18000b914`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b3d8`

## callees

- `0x18000a4f4`
- `0x18000afc0`
- `0x18000b594`
- `0x18000cac4`
- `0x18002bc56`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000b873`
- `msvcrt!memmove_s` at `0x18000b873`
- `msvcrt!memcpy_s` at `0x18000b69f`
- `msvcrt!memcpy_s` at `0x18000b738`
- `msvcrt!memcpy_s` at `0x18000b8de`
- `msvcrt!memcpy_s` at `0x18000b69f`
- `msvcrt!memcpy_s` at `0x18000b738`
- `msvcrt!memcpy_s` at `0x18000b8de`

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
0x18000b594  push    rbp
0x18000b596  push    rbx
0x18000b597  push    rsi
0x18000b598  push    rdi
0x18000b599  push    r12
0x18000b59b  push    r13
0x18000b59d  push    r14
0x18000b59f  push    r15
0x18000b5a1  lea     rbp, [rsp-0Fh]
0x18000b5a6  sub     rsp, 0A8h
0x18000b5ad  mov     rbx, [rcx+18h]
0x18000b5b1  mov     rdi, rcx
0x18000b5b4  xor     ecx, ecx
0x18000b5b6  mov     r13, r9
0x18000b5b9  mov     r14, r8
0x18000b5bc  mov     r15, rdx
0x18000b5bf  test    rbx, rbx
0x18000b5c2  jz      loc_18000B8FE
0x18000b5c8  movzx   eax, word ptr [rdi+2]
0x18000b5cc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b5d0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b5d4  add     rbx, 0Ah
0x18000b5d8  mov     [rbp+47h+var_A0], ax
0x18000b5dc  xorps   xmm0, xmm0
0x18000b5df  mov     al, [rdi+4]
0x18000b5e2  mov     [rbp+47h+Source], ecx
0x18000b5e5  mov     [rbp+47h+var_98], cx
0x18000b5e9  mov     byte ptr [rbp+47h+arg_0], cl
0x18000b5ec  lea     rcx, [rbp+47h+var_A0]; this
0x18000b5f0  mov     [rbp+47h+var_9E], al
0x18000b5f3  mov     [rbp+47h+var_A8], rbx
0x18000b5f7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000b5fc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b601  mov     r12, [rbp+47h+arg_20]
0x18000b605  jmp     loc_18000B753
0x18000b60a  movzx   eax, [rbp+47h+var_98]
0x18000b60e  cmp     r14, rax
0x18000b611  jnz     short loc_18000B629
0x18000b613  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000b617  mov     r8, r14; Size
0x18000b61a  mov     rcx, r15; Buf1
0x18000b61d  call    memcmp_0
0x18000b622  mov     ecx, eax
0x18000b624  xor     r9d, r9d
0x18000b627  jmp     short loc_18000B632
0x18000b629  movzx   eax, [rbp+47h+var_98]
0x18000b62d  mov     ecx, r14d
0x18000b630  sub     ecx, eax
0x18000b632  test    ecx, ecx
0x18000b634  js      loc_18000B7D8
0x18000b63a  jz      loc_18000B79D
0x18000b640  mov     rbx, [rbp+47h+var_A8]
0x18000b644  mov     [rbp+47h+var_A8], rbx
0x18000b648  cmp     [rdi+10h], r9
0x18000b64c  jbe     short loc_18000B6B7
0x18000b64e  mov     rax, [rdi+20h]
0x18000b652  xor     edx, edx
0x18000b654  sub     rax, [rdi+18h]
0x18000b658  mov     rsi, rbx
0x18000b65b  div     qword ptr [rdi+10h]
0x18000b65f  mov     edx, [rbp+47h+Source]
0x18000b662  cmp     rdx, rax
0x18000b665  jbe     short loc_18000B6A8
0x18000b667  cmp     edx, eax
0x18000b669  jz      short loc_18000B6A8
0x18000b66b  mov     edx, eax
0x18000b66d  mov     [rbp+47h+Source], eax
0x18000b670  mov     al, [rbp+47h+var_9E]
0x18000b673  cmp     al, 1
0x18000b675  jnz     short loc_18000B68A
0x18000b677  movzx   eax, dx
0x18000b67a  mov     [rbp+47h+var_B0], dx
0x18000b67e  mov     r9d, 2
0x18000b684  lea     r8, [rbp+47h+var_B0]
0x18000b688  jmp     short loc_18000B698
0x18000b68a  cmp     al, 2
0x18000b68c  jnz     short loc_18000B6A8
0x18000b68e  mov     r9d, 4; SourceSize
0x18000b694  lea     r8, [rbp+47h+Source]; Source
0x18000b698  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b69c  mov     rdx, r9; DestinationSize
0x18000b69f  call    cs:__imp_memcpy_s
0x18000b6a5  mov     edx, [rbp+47h+Source]
0x18000b6a8  mov     ebx, edx
0x18000b6aa  imul    rbx, [rdi+10h]
0x18000b6af  add     rbx, rsi
0x18000b6b2  jmp     loc_18000B73E
0x18000b6b7  movzx   eax, word ptr [rdi+6]
0x18000b6bb  xorps   xmm0, xmm0
0x18000b6be  mov     [rbp+47h+var_60], ax
0x18000b6c2  mov     esi, r9d
0x18000b6c5  mov     al, [rdi+8]
0x18000b6c8  mov     [rbp+47h+var_5E], al
0x18000b6cb  mov     eax, [rbp+47h+Source]
0x18000b6ce  mov     [rbp+47h+var_5C], r9d
0x18000b6d2  mov     [rbp+47h+var_58], r9w
0x18000b6d7  movdqu  [rbp+47h+var_50], xmm0
0x18000b6dc  test    eax, eax
0x18000b6de  jz      short loc_18000B702
0x18000b6e0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b6e4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b6e8  lea     rcx, [rbp+47h+var_60]; this
0x18000b6ec  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b6f1  test    al, al
0x18000b6f3  mov     eax, [rbp+47h+Source]
0x18000b6f6  jz      short loc_18000B6FE
0x18000b6f8  inc     esi
0x18000b6fa  cmp     esi, eax
0x18000b6fc  jb      short loc_18000B6E0
0x18000b6fe  mov     rbx, [rbp+47h+var_A8]
0x18000b702  cmp     eax, esi
0x18000b704  jz      short loc_18000B73E
0x18000b706  mov     al, [rbp+47h+var_9E]
0x18000b709  mov     [rbp+47h+Source], esi
0x18000b70c  cmp     al, 1
0x18000b70e  jnz     short loc_18000B724
0x18000b710  mov     eax, 2
0x18000b715  mov     [rbp+47h+var_B0], si
0x18000b719  mov     r9d, eax
0x18000b71c  lea     r8, [rbp+47h+var_B0]
0x18000b720  mov     edx, eax
0x18000b722  jmp     short loc_18000B734
0x18000b724  cmp     al, 2
0x18000b726  jnz     short loc_18000B73E
0x18000b728  mov     edx, 4; DestinationSize
0x18000b72d  lea     r8, [rbp+47h+Source]; Source
0x18000b731  mov     r9d, edx; SourceSize
0x18000b734  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b738  call    cs:__imp_memcpy_s
0x18000b73e  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b742  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b746  lea     rcx, [rbp+47h+var_A0]; this
0x18000b74a  mov     [rbp+47h+var_A8], rbx
0x18000b74e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b753  xor     r9d, r9d
0x18000b756  mov     sil, al
0x18000b759  test    al, al
0x18000b75b  jnz     loc_18000B60A
0x18000b761  mov     rbx, [rbp+47h+var_A8]
0x18000b765  mov     [rdi+20h], rbx
0x18000b769  mov     rcx, r9
0x18000b76c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000b770  jnz     loc_18000B7FB
0x18000b776  movzx   eax, [rbp+47h+var_A0]
0x18000b77a  mov     [rbp+47h+Source], 1
0x18000b781  mov     [rbp+47h+var_98], r14w
0x18000b786  mov     [rbp+47h+Buf2], r9
0x18000b78a  mov     [rbp+47h+Buf2+8], r15
0x18000b78e  test    ax, ax
0x18000b791  jnz     short loc_18000B7E3
0x18000b793  movzx   ecx, r14w
0x18000b797  add     rcx, 2
0x18000b79b  jmp     short loc_18000B7E6
0x18000b79d  mov     eax, [rbp+47h+arg_28]
0x18000b7a0  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000b7a4  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000b7a8  mov     r9, r13; void *
0x18000b7ab  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000b7af  mov     rcx, rdi; this
0x18000b7b2  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000b7b7  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000b7bc  xor     r9d, r9d
0x18000b7bf  mov     [rbp+47h+var_A8], rax
0x18000b7c3  mov     rbx, rax
0x18000b7c6  test    rax, rax
0x18000b7c9  jnz     short loc_18000B7D2
0x18000b7cb  mov     al, 1
0x18000b7cd  jmp     loc_18000B900
0x18000b7d2  mov     byte ptr [rbp+47h+arg_0], 1
0x18000b7d6  jmp     short loc_18000B7DC
0x18000b7d8  mov     [rbp+47h+var_A8], rbx
0x18000b7dc  test    sil, sil
0x18000b7df  jnz     short loc_18000B769
0x18000b7e1  jmp     short loc_18000B765
0x18000b7e3  mov     rcx, rax
0x18000b7e6  mov     al, [rbp+47h+var_9E]
0x18000b7e9  cmp     al, 1
0x18000b7eb  jnz     short loc_18000B7F3
0x18000b7ed  add     rcx, 2
0x18000b7f1  jmp     short loc_18000B7FB
0x18000b7f3  cmp     al, 2
0x18000b7f5  jnz     short loc_18000B7FB
0x18000b7f7  add     rcx, 4
0x18000b7fb  movzx   eax, word ptr [rdi+6]
0x18000b7ff  mov     dl, [rdi+8]
0x18000b802  mov     r8d, [rbp+47h+arg_28]
0x18000b806  mov     [rbp+47h+var_80], ax
0x18000b80a  mov     [rbp+47h+var_7E], dl
0x18000b80d  mov     [rbp+47h+var_7C], r8d
0x18000b811  mov     [rbp+47h+var_78], r12w
0x18000b816  mov     [rbp+47h+var_70], r9
0x18000b81a  mov     [rbp+47h+var_68], r13
0x18000b81e  test    ax, ax
0x18000b821  jnz     short loc_18000B82B
0x18000b823  movzx   eax, r12w
0x18000b827  add     rax, 2
0x18000b82b  cmp     dl, 1
0x18000b82e  jnz     short loc_18000B836
0x18000b830  add     rax, 2
0x18000b834  jmp     short loc_18000B83F
0x18000b836  cmp     dl, 2
0x18000b839  jnz     short loc_18000B83F
0x18000b83b  add     rax, 4
0x18000b83f  mov     rdx, [rdi+28h]
0x18000b843  lea     rsi, [rax+rcx]
0x18000b847  mov     r9, [rdi+20h]
0x18000b84b  mov     rcx, rdx
0x18000b84e  sub     rcx, r9
0x18000b851  cmp     r9, rdx
0x18000b854  sbb     rax, rax
0x18000b857  and     rax, rcx
0x18000b85a  cmp     rax, rsi
0x18000b85d  jb      loc_18000B8FE
0x18000b863  sub     rdx, rsi
0x18000b866  lea     rcx, [rsi+rbx]; Destination
0x18000b86a  sub     rdx, rbx; DestinationSize
0x18000b86d  sub     r9, rbx; SourceSize
0x18000b870  mov     r8, rbx; Source
0x18000b873  call    cs:__imp_memmove_s
0x18000b879  add     [rdi+20h], rsi
0x18000b87d  xor     ebx, ebx
0x18000b87f  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000b882  jnz     short loc_18000B897
0x18000b884  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b888  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b88c  lea     rcx, [rbp+47h+var_A0]; this
0x18000b890  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b895  jmp     short loc_18000B8E4
0x18000b897  mov     cl, [rbp+47h+var_9E]
0x18000b89a  test    cl, cl
0x18000b89c  jz      short loc_18000B8E4
0x18000b89e  mov     eax, [rbp+47h+Source]
0x18000b8a1  lea     r8d, [rax+1]
0x18000b8a5  cmp     eax, r8d
0x18000b8a8  jz      short loc_18000B8E4
0x18000b8aa  mov     [rbp+47h+Source], r8d
0x18000b8ae  cmp     cl, 1
0x18000b8b1  jnz     short loc_18000B8C7
0x18000b8b3  mov     r9d, 2
0x18000b8b9  mov     [rbp+47h+arg_0], r8w
0x18000b8be  mov     edx, r9d
0x18000b8c1  lea     r8, [rbp+47h+arg_0]
0x18000b8c5  jmp     short loc_18000B8DA
0x18000b8c7  cmp     cl, 2
0x18000b8ca  jnz     short loc_18000B8E4
0x18000b8cc  mov     eax, 4
0x18000b8d1  lea     r8, [rbp+47h+Source]; Source
0x18000b8d5  mov     r9d, eax; SourceSize
0x18000b8d8  mov     edx, eax; DestinationSize
0x18000b8da  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b8de  call    cs:__imp_memcpy_s
0x18000b8e4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b8e8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b8ec  lea     rcx, [rbp+47h+var_80]; this
0x18000b8f0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b8f5  mov     byte ptr [rdi+38h], 1
0x18000b8f9  jmp     loc_18000B7CB
0x18000b8fe  xor     al, al
0x18000b900  add     rsp, 0A8h
0x18000b907  pop     r15
0x18000b909  pop     r14
0x18000b90b  pop     r13
0x18000b90d  pop     r12
0x18000b90f  pop     rdi
0x18000b910  pop     rsi
0x18000b911  pop     rbx
0x18000b912  pop     rbp
0x18000b913  retn
```
