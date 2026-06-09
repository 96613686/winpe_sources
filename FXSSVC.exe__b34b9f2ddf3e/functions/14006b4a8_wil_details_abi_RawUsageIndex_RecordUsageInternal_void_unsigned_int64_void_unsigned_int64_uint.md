# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14006b4a8`
- end: `0x14006b828`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006b2f8`

## callees

- `0x14006952c`
- `0x14006ae6c`
- `0x14006b4a8`
- `0x14006d25c`
- `0x140081866`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14006b5b3`
- `msvcrt!memcpy_s` at `0x14006b64c`
- `msvcrt!memcpy_s` at `0x14006b7f2`
- `msvcrt!memcpy_s` at `0x14006b5b3`
- `msvcrt!memcpy_s` at `0x14006b64c`
- `msvcrt!memcpy_s` at `0x14006b7f2`
- `msvcrt!memmove_s` at `0x14006b787`
- `msvcrt!memmove_s` at `0x14006b787`

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
0x14006b4a8  push    rbp
0x14006b4aa  push    rbx
0x14006b4ab  push    rsi
0x14006b4ac  push    rdi
0x14006b4ad  push    r12
0x14006b4af  push    r13
0x14006b4b1  push    r14
0x14006b4b3  push    r15
0x14006b4b5  lea     rbp, [rsp-0Fh]
0x14006b4ba  sub     rsp, 0A8h
0x14006b4c1  mov     rbx, [rcx+18h]
0x14006b4c5  mov     rdi, rcx
0x14006b4c8  xor     ecx, ecx
0x14006b4ca  mov     r13, r9
0x14006b4cd  mov     r14, r8
0x14006b4d0  mov     r15, rdx
0x14006b4d3  test    rbx, rbx
0x14006b4d6  jz      loc_14006B812
0x14006b4dc  movzx   eax, word ptr [rdi+2]
0x14006b4e0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006b4e4  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006b4e8  add     rbx, 0Ah
0x14006b4ec  mov     [rbp+47h+var_A0], ax
0x14006b4f0  xorps   xmm0, xmm0
0x14006b4f3  mov     al, [rdi+4]
0x14006b4f6  mov     [rbp+47h+Source], ecx
0x14006b4f9  mov     [rbp+47h+var_98], cx
0x14006b4fd  mov     byte ptr [rbp+47h+arg_0], cl
0x14006b500  lea     rcx, [rbp+47h+var_A0]; this
0x14006b504  mov     [rbp+47h+var_9E], al
0x14006b507  mov     [rbp+47h+var_A8], rbx
0x14006b50b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14006b510  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14006b515  mov     r12, [rbp+47h+arg_20]
0x14006b519  jmp     loc_14006B667
0x14006b51e  movzx   eax, [rbp+47h+var_98]
0x14006b522  cmp     r14, rax
0x14006b525  jnz     short loc_14006B53D
0x14006b527  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14006b52b  mov     r8, r14; Size
0x14006b52e  mov     rcx, r15; Buf1
0x14006b531  call    memcmp_0
0x14006b536  mov     ecx, eax
0x14006b538  xor     r9d, r9d
0x14006b53b  jmp     short loc_14006B546
0x14006b53d  movzx   eax, [rbp+47h+var_98]
0x14006b541  mov     ecx, r14d
0x14006b544  sub     ecx, eax
0x14006b546  test    ecx, ecx
0x14006b548  js      loc_14006B6EC
0x14006b54e  jz      loc_14006B6B1
0x14006b554  mov     rbx, [rbp+47h+var_A8]
0x14006b558  mov     [rbp+47h+var_A8], rbx
0x14006b55c  cmp     [rdi+10h], r9
0x14006b560  jbe     short loc_14006B5CB
0x14006b562  mov     rax, [rdi+20h]
0x14006b566  xor     edx, edx
0x14006b568  sub     rax, [rdi+18h]
0x14006b56c  mov     rsi, rbx
0x14006b56f  div     qword ptr [rdi+10h]
0x14006b573  mov     edx, [rbp+47h+Source]
0x14006b576  cmp     rdx, rax
0x14006b579  jbe     short loc_14006B5BC
0x14006b57b  cmp     edx, eax
0x14006b57d  jz      short loc_14006B5BC
0x14006b57f  mov     edx, eax
0x14006b581  mov     [rbp+47h+Source], eax
0x14006b584  mov     al, [rbp+47h+var_9E]
0x14006b587  cmp     al, 1
0x14006b589  jnz     short loc_14006B59E
0x14006b58b  movzx   eax, dx
0x14006b58e  mov     [rbp+47h+var_B0], dx
0x14006b592  mov     r9d, 2
0x14006b598  lea     r8, [rbp+47h+var_B0]
0x14006b59c  jmp     short loc_14006B5AC
0x14006b59e  cmp     al, 2
0x14006b5a0  jnz     short loc_14006B5BC
0x14006b5a2  mov     r9d, 4; SourceSize
0x14006b5a8  lea     r8, [rbp+47h+Source]; Source
0x14006b5ac  mov     rcx, [rbp+47h+Buf2]; Destination
0x14006b5b0  mov     rdx, r9; DestinationSize
0x14006b5b3  call    cs:__imp_memcpy_s
0x14006b5b9  mov     edx, [rbp+47h+Source]
0x14006b5bc  mov     ebx, edx
0x14006b5be  imul    rbx, [rdi+10h]
0x14006b5c3  add     rbx, rsi
0x14006b5c6  jmp     loc_14006B652
0x14006b5cb  movzx   eax, word ptr [rdi+6]
0x14006b5cf  xorps   xmm0, xmm0
0x14006b5d2  mov     [rbp+47h+var_60], ax
0x14006b5d6  mov     esi, r9d
0x14006b5d9  mov     al, [rdi+8]
0x14006b5dc  mov     [rbp+47h+var_5E], al
0x14006b5df  mov     eax, [rbp+47h+Source]
0x14006b5e2  mov     [rbp+47h+var_5C], r9d
0x14006b5e6  mov     [rbp+47h+var_58], r9w
0x14006b5eb  movdqu  [rbp+47h+var_50], xmm0
0x14006b5f0  test    eax, eax
0x14006b5f2  jz      short loc_14006B616
0x14006b5f4  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006b5f8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006b5fc  lea     rcx, [rbp+47h+var_60]; this
0x14006b600  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14006b605  test    al, al
0x14006b607  mov     eax, [rbp+47h+Source]
0x14006b60a  jz      short loc_14006B612
0x14006b60c  inc     esi
0x14006b60e  cmp     esi, eax
0x14006b610  jb      short loc_14006B5F4
0x14006b612  mov     rbx, [rbp+47h+var_A8]
0x14006b616  cmp     eax, esi
0x14006b618  jz      short loc_14006B652
0x14006b61a  mov     al, [rbp+47h+var_9E]
0x14006b61d  mov     [rbp+47h+Source], esi
0x14006b620  cmp     al, 1
0x14006b622  jnz     short loc_14006B638
0x14006b624  mov     eax, 2
0x14006b629  mov     [rbp+47h+var_B0], si
0x14006b62d  mov     r9d, eax
0x14006b630  lea     r8, [rbp+47h+var_B0]
0x14006b634  mov     edx, eax
0x14006b636  jmp     short loc_14006B648
0x14006b638  cmp     al, 2
0x14006b63a  jnz     short loc_14006B652
0x14006b63c  mov     edx, 4; DestinationSize
0x14006b641  lea     r8, [rbp+47h+Source]; Source
0x14006b645  mov     r9d, edx; SourceSize
0x14006b648  mov     rcx, [rbp+47h+Buf2]; Destination
0x14006b64c  call    cs:__imp_memcpy_s
0x14006b652  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006b656  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006b65a  lea     rcx, [rbp+47h+var_A0]; this
0x14006b65e  mov     [rbp+47h+var_A8], rbx
0x14006b662  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14006b667  xor     r9d, r9d
0x14006b66a  mov     sil, al
0x14006b66d  test    al, al
0x14006b66f  jnz     loc_14006B51E
0x14006b675  mov     rbx, [rbp+47h+var_A8]
0x14006b679  mov     [rdi+20h], rbx
0x14006b67d  mov     rcx, r9
0x14006b680  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14006b684  jnz     loc_14006B70F
0x14006b68a  movzx   eax, [rbp+47h+var_A0]
0x14006b68e  mov     [rbp+47h+Source], 1
0x14006b695  mov     [rbp+47h+var_98], r14w
0x14006b69a  mov     [rbp+47h+Buf2], r9
0x14006b69e  mov     [rbp+47h+Buf2+8], r15
0x14006b6a2  test    ax, ax
0x14006b6a5  jnz     short loc_14006B6F7
0x14006b6a7  movzx   ecx, r14w
0x14006b6ab  add     rcx, 2
0x14006b6af  jmp     short loc_14006B6FA
0x14006b6b1  mov     eax, [rbp+47h+arg_28]
0x14006b6b4  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x14006b6b8  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x14006b6bc  mov     r9, r13; void *
0x14006b6bf  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14006b6c3  mov     rcx, rdi; this
0x14006b6c6  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x14006b6cb  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14006b6d0  xor     r9d, r9d
0x14006b6d3  mov     [rbp+47h+var_A8], rax
0x14006b6d7  mov     rbx, rax
0x14006b6da  test    rax, rax
0x14006b6dd  jnz     short loc_14006B6E6
0x14006b6df  mov     al, 1
0x14006b6e1  jmp     loc_14006B814
0x14006b6e6  mov     byte ptr [rbp+47h+arg_0], 1
0x14006b6ea  jmp     short loc_14006B6F0
0x14006b6ec  mov     [rbp+47h+var_A8], rbx
0x14006b6f0  test    sil, sil
0x14006b6f3  jnz     short loc_14006B67D
0x14006b6f5  jmp     short loc_14006B679
0x14006b6f7  mov     rcx, rax
0x14006b6fa  mov     al, [rbp+47h+var_9E]
0x14006b6fd  cmp     al, 1
0x14006b6ff  jnz     short loc_14006B707
0x14006b701  add     rcx, 2
0x14006b705  jmp     short loc_14006B70F
0x14006b707  cmp     al, 2
0x14006b709  jnz     short loc_14006B70F
0x14006b70b  add     rcx, 4
0x14006b70f  movzx   eax, word ptr [rdi+6]
0x14006b713  mov     dl, [rdi+8]
0x14006b716  mov     r8d, [rbp+47h+arg_28]
0x14006b71a  mov     [rbp+47h+var_80], ax
0x14006b71e  mov     [rbp+47h+var_7E], dl
0x14006b721  mov     [rbp+47h+var_7C], r8d
0x14006b725  mov     [rbp+47h+var_78], r12w
0x14006b72a  mov     [rbp+47h+var_70], r9
0x14006b72e  mov     [rbp+47h+var_68], r13
0x14006b732  test    ax, ax
0x14006b735  jnz     short loc_14006B73F
0x14006b737  movzx   eax, r12w
0x14006b73b  add     rax, 2
0x14006b73f  cmp     dl, 1
0x14006b742  jnz     short loc_14006B74A
0x14006b744  add     rax, 2
0x14006b748  jmp     short loc_14006B753
0x14006b74a  cmp     dl, 2
0x14006b74d  jnz     short loc_14006B753
0x14006b74f  add     rax, 4
0x14006b753  mov     rdx, [rdi+28h]
0x14006b757  lea     rsi, [rax+rcx]
0x14006b75b  mov     r9, [rdi+20h]
0x14006b75f  mov     rcx, rdx
0x14006b762  sub     rcx, r9
0x14006b765  cmp     r9, rdx
0x14006b768  sbb     rax, rax
0x14006b76b  and     rax, rcx
0x14006b76e  cmp     rax, rsi
0x14006b771  jb      loc_14006B812
0x14006b777  sub     rdx, rsi
0x14006b77a  lea     rcx, [rsi+rbx]; Destination
0x14006b77e  sub     rdx, rbx; DestinationSize
0x14006b781  sub     r9, rbx; SourceSize
0x14006b784  mov     r8, rbx; Source
0x14006b787  call    cs:__imp_memmove_s
0x14006b78d  add     [rdi+20h], rsi
0x14006b791  xor     ebx, ebx
0x14006b793  cmp     byte ptr [rbp+47h+arg_0], bl
0x14006b796  jnz     short loc_14006B7AB
0x14006b798  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006b79c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006b7a0  lea     rcx, [rbp+47h+var_A0]; this
0x14006b7a4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14006b7a9  jmp     short loc_14006B7F8
0x14006b7ab  mov     cl, [rbp+47h+var_9E]
0x14006b7ae  test    cl, cl
0x14006b7b0  jz      short loc_14006B7F8
0x14006b7b2  mov     eax, [rbp+47h+Source]
0x14006b7b5  lea     r8d, [rax+1]
0x14006b7b9  cmp     eax, r8d
0x14006b7bc  jz      short loc_14006B7F8
0x14006b7be  mov     [rbp+47h+Source], r8d
0x14006b7c2  cmp     cl, 1
0x14006b7c5  jnz     short loc_14006B7DB
0x14006b7c7  mov     r9d, 2
0x14006b7cd  mov     [rbp+47h+arg_0], r8w
0x14006b7d2  mov     edx, r9d
0x14006b7d5  lea     r8, [rbp+47h+arg_0]
0x14006b7d9  jmp     short loc_14006B7EE
0x14006b7db  cmp     cl, 2
0x14006b7de  jnz     short loc_14006B7F8
0x14006b7e0  mov     eax, 4
0x14006b7e5  lea     r8, [rbp+47h+Source]; Source
0x14006b7e9  mov     r9d, eax; SourceSize
0x14006b7ec  mov     edx, eax; DestinationSize
0x14006b7ee  mov     rcx, [rbp+47h+Buf2]; Destination
0x14006b7f2  call    cs:__imp_memcpy_s
0x14006b7f8  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006b7fc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006b800  lea     rcx, [rbp+47h+var_80]; this
0x14006b804  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14006b809  mov     byte ptr [rdi+38h], 1
0x14006b80d  jmp     loc_14006B6DF
0x14006b812  xor     al, al
0x14006b814  add     rsp, 0A8h
0x14006b81b  pop     r15
0x14006b81d  pop     r14
0x14006b81f  pop     r13
0x14006b821  pop     r12
0x14006b823  pop     rdi
0x14006b824  pop     rsi
0x14006b825  pop     rbx
0x14006b826  pop     rbp
0x14006b827  retn
```
