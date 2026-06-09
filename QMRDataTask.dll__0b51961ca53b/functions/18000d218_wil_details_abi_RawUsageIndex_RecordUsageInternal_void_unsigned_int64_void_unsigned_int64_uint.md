# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000d218`
- end: `0x18000d598`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d068`

## callees

- `0x180007a44`
- `0x18000c9e8`
- `0x18000d218`
- `0x1800112ac`
- `0x1800142c6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d323`
- `msvcrt!memcpy_s` at `0x18000d3bc`
- `msvcrt!memcpy_s` at `0x18000d562`
- `msvcrt!memcpy_s` at `0x18000d323`
- `msvcrt!memcpy_s` at `0x18000d3bc`
- `msvcrt!memcpy_s` at `0x18000d562`
- `msvcrt!memmove_s` at `0x18000d4f7`
- `msvcrt!memmove_s` at `0x18000d4f7`

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
0x18000d218  push    rbp
0x18000d21a  push    rbx
0x18000d21b  push    rsi
0x18000d21c  push    rdi
0x18000d21d  push    r12
0x18000d21f  push    r13
0x18000d221  push    r14
0x18000d223  push    r15
0x18000d225  lea     rbp, [rsp-0Fh]
0x18000d22a  sub     rsp, 0A8h
0x18000d231  mov     rbx, [rcx+18h]
0x18000d235  mov     rdi, rcx
0x18000d238  xor     ecx, ecx
0x18000d23a  mov     r13, r9
0x18000d23d  mov     r14, r8
0x18000d240  mov     r15, rdx
0x18000d243  test    rbx, rbx
0x18000d246  jz      loc_18000D582
0x18000d24c  movzx   eax, word ptr [rdi+2]
0x18000d250  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d254  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d258  add     rbx, 0Ah
0x18000d25c  mov     [rbp+47h+var_A0], ax
0x18000d260  xorps   xmm0, xmm0
0x18000d263  mov     al, [rdi+4]
0x18000d266  mov     [rbp+47h+Source], ecx
0x18000d269  mov     [rbp+47h+var_98], cx
0x18000d26d  mov     byte ptr [rbp+47h+arg_0], cl
0x18000d270  lea     rcx, [rbp+47h+var_A0]; this
0x18000d274  mov     [rbp+47h+var_9E], al
0x18000d277  mov     [rbp+47h+var_A8], rbx
0x18000d27b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000d280  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d285  mov     r12, [rbp+47h+arg_20]
0x18000d289  jmp     loc_18000D3D7
0x18000d28e  movzx   eax, [rbp+47h+var_98]
0x18000d292  cmp     r14, rax
0x18000d295  jnz     short loc_18000D2AD
0x18000d297  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000d29b  mov     r8, r14; Size
0x18000d29e  mov     rcx, r15; Buf1
0x18000d2a1  call    memcmp_0
0x18000d2a6  mov     ecx, eax
0x18000d2a8  xor     r9d, r9d
0x18000d2ab  jmp     short loc_18000D2B6
0x18000d2ad  movzx   eax, [rbp+47h+var_98]
0x18000d2b1  mov     ecx, r14d
0x18000d2b4  sub     ecx, eax
0x18000d2b6  test    ecx, ecx
0x18000d2b8  js      loc_18000D45C
0x18000d2be  jz      loc_18000D421
0x18000d2c4  mov     rbx, [rbp+47h+var_A8]
0x18000d2c8  mov     [rbp+47h+var_A8], rbx
0x18000d2cc  cmp     [rdi+10h], r9
0x18000d2d0  jbe     short loc_18000D33B
0x18000d2d2  mov     rax, [rdi+20h]
0x18000d2d6  xor     edx, edx
0x18000d2d8  sub     rax, [rdi+18h]
0x18000d2dc  mov     rsi, rbx
0x18000d2df  div     qword ptr [rdi+10h]
0x18000d2e3  mov     edx, [rbp+47h+Source]
0x18000d2e6  cmp     rdx, rax
0x18000d2e9  jbe     short loc_18000D32C
0x18000d2eb  cmp     edx, eax
0x18000d2ed  jz      short loc_18000D32C
0x18000d2ef  mov     edx, eax
0x18000d2f1  mov     [rbp+47h+Source], eax
0x18000d2f4  mov     al, [rbp+47h+var_9E]
0x18000d2f7  cmp     al, 1
0x18000d2f9  jnz     short loc_18000D30E
0x18000d2fb  movzx   eax, dx
0x18000d2fe  mov     [rbp+47h+var_B0], dx
0x18000d302  mov     r9d, 2
0x18000d308  lea     r8, [rbp+47h+var_B0]
0x18000d30c  jmp     short loc_18000D31C
0x18000d30e  cmp     al, 2
0x18000d310  jnz     short loc_18000D32C
0x18000d312  mov     r9d, 4; SourceSize
0x18000d318  lea     r8, [rbp+47h+Source]; Source
0x18000d31c  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d320  mov     rdx, r9; DestinationSize
0x18000d323  call    cs:__imp_memcpy_s
0x18000d329  mov     edx, [rbp+47h+Source]
0x18000d32c  mov     ebx, edx
0x18000d32e  imul    rbx, [rdi+10h]
0x18000d333  add     rbx, rsi
0x18000d336  jmp     loc_18000D3C2
0x18000d33b  movzx   eax, word ptr [rdi+6]
0x18000d33f  xorps   xmm0, xmm0
0x18000d342  mov     [rbp+47h+var_60], ax
0x18000d346  mov     esi, r9d
0x18000d349  mov     al, [rdi+8]
0x18000d34c  mov     [rbp+47h+var_5E], al
0x18000d34f  mov     eax, [rbp+47h+Source]
0x18000d352  mov     [rbp+47h+var_5C], r9d
0x18000d356  mov     [rbp+47h+var_58], r9w
0x18000d35b  movdqu  [rbp+47h+var_50], xmm0
0x18000d360  test    eax, eax
0x18000d362  jz      short loc_18000D386
0x18000d364  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d368  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d36c  lea     rcx, [rbp+47h+var_60]; this
0x18000d370  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d375  test    al, al
0x18000d377  mov     eax, [rbp+47h+Source]
0x18000d37a  jz      short loc_18000D382
0x18000d37c  inc     esi
0x18000d37e  cmp     esi, eax
0x18000d380  jb      short loc_18000D364
0x18000d382  mov     rbx, [rbp+47h+var_A8]
0x18000d386  cmp     eax, esi
0x18000d388  jz      short loc_18000D3C2
0x18000d38a  mov     al, [rbp+47h+var_9E]
0x18000d38d  mov     [rbp+47h+Source], esi
0x18000d390  cmp     al, 1
0x18000d392  jnz     short loc_18000D3A8
0x18000d394  mov     eax, 2
0x18000d399  mov     [rbp+47h+var_B0], si
0x18000d39d  mov     r9d, eax
0x18000d3a0  lea     r8, [rbp+47h+var_B0]
0x18000d3a4  mov     edx, eax
0x18000d3a6  jmp     short loc_18000D3B8
0x18000d3a8  cmp     al, 2
0x18000d3aa  jnz     short loc_18000D3C2
0x18000d3ac  mov     edx, 4; DestinationSize
0x18000d3b1  lea     r8, [rbp+47h+Source]; Source
0x18000d3b5  mov     r9d, edx; SourceSize
0x18000d3b8  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d3bc  call    cs:__imp_memcpy_s
0x18000d3c2  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d3c6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d3ca  lea     rcx, [rbp+47h+var_A0]; this
0x18000d3ce  mov     [rbp+47h+var_A8], rbx
0x18000d3d2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d3d7  xor     r9d, r9d
0x18000d3da  mov     sil, al
0x18000d3dd  test    al, al
0x18000d3df  jnz     loc_18000D28E
0x18000d3e5  mov     rbx, [rbp+47h+var_A8]
0x18000d3e9  mov     [rdi+20h], rbx
0x18000d3ed  mov     rcx, r9
0x18000d3f0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000d3f4  jnz     loc_18000D47F
0x18000d3fa  movzx   eax, [rbp+47h+var_A0]
0x18000d3fe  mov     [rbp+47h+Source], 1
0x18000d405  mov     [rbp+47h+var_98], r14w
0x18000d40a  mov     [rbp+47h+Buf2], r9
0x18000d40e  mov     [rbp+47h+Buf2+8], r15
0x18000d412  test    ax, ax
0x18000d415  jnz     short loc_18000D467
0x18000d417  movzx   ecx, r14w
0x18000d41b  add     rcx, 2
0x18000d41f  jmp     short loc_18000D46A
0x18000d421  mov     eax, [rbp+47h+arg_28]
0x18000d424  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000d428  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000d42c  mov     r9, r13; void *
0x18000d42f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000d433  mov     rcx, rdi; this
0x18000d436  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000d43b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000d440  xor     r9d, r9d
0x18000d443  mov     [rbp+47h+var_A8], rax
0x18000d447  mov     rbx, rax
0x18000d44a  test    rax, rax
0x18000d44d  jnz     short loc_18000D456
0x18000d44f  mov     al, 1
0x18000d451  jmp     loc_18000D584
0x18000d456  mov     byte ptr [rbp+47h+arg_0], 1
0x18000d45a  jmp     short loc_18000D460
0x18000d45c  mov     [rbp+47h+var_A8], rbx
0x18000d460  test    sil, sil
0x18000d463  jnz     short loc_18000D3ED
0x18000d465  jmp     short loc_18000D3E9
0x18000d467  mov     rcx, rax
0x18000d46a  mov     al, [rbp+47h+var_9E]
0x18000d46d  cmp     al, 1
0x18000d46f  jnz     short loc_18000D477
0x18000d471  add     rcx, 2
0x18000d475  jmp     short loc_18000D47F
0x18000d477  cmp     al, 2
0x18000d479  jnz     short loc_18000D47F
0x18000d47b  add     rcx, 4
0x18000d47f  movzx   eax, word ptr [rdi+6]
0x18000d483  mov     dl, [rdi+8]
0x18000d486  mov     r8d, [rbp+47h+arg_28]
0x18000d48a  mov     [rbp+47h+var_80], ax
0x18000d48e  mov     [rbp+47h+var_7E], dl
0x18000d491  mov     [rbp+47h+var_7C], r8d
0x18000d495  mov     [rbp+47h+var_78], r12w
0x18000d49a  mov     [rbp+47h+var_70], r9
0x18000d49e  mov     [rbp+47h+var_68], r13
0x18000d4a2  test    ax, ax
0x18000d4a5  jnz     short loc_18000D4AF
0x18000d4a7  movzx   eax, r12w
0x18000d4ab  add     rax, 2
0x18000d4af  cmp     dl, 1
0x18000d4b2  jnz     short loc_18000D4BA
0x18000d4b4  add     rax, 2
0x18000d4b8  jmp     short loc_18000D4C3
0x18000d4ba  cmp     dl, 2
0x18000d4bd  jnz     short loc_18000D4C3
0x18000d4bf  add     rax, 4
0x18000d4c3  mov     rdx, [rdi+28h]
0x18000d4c7  lea     rsi, [rax+rcx]
0x18000d4cb  mov     r9, [rdi+20h]
0x18000d4cf  mov     rcx, rdx
0x18000d4d2  sub     rcx, r9
0x18000d4d5  cmp     r9, rdx
0x18000d4d8  sbb     rax, rax
0x18000d4db  and     rax, rcx
0x18000d4de  cmp     rax, rsi
0x18000d4e1  jb      loc_18000D582
0x18000d4e7  sub     rdx, rsi
0x18000d4ea  lea     rcx, [rsi+rbx]; Destination
0x18000d4ee  sub     rdx, rbx; DestinationSize
0x18000d4f1  sub     r9, rbx; SourceSize
0x18000d4f4  mov     r8, rbx; Source
0x18000d4f7  call    cs:__imp_memmove_s
0x18000d4fd  add     [rdi+20h], rsi
0x18000d501  xor     ebx, ebx
0x18000d503  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000d506  jnz     short loc_18000D51B
0x18000d508  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d50c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d510  lea     rcx, [rbp+47h+var_A0]; this
0x18000d514  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000d519  jmp     short loc_18000D568
0x18000d51b  mov     cl, [rbp+47h+var_9E]
0x18000d51e  test    cl, cl
0x18000d520  jz      short loc_18000D568
0x18000d522  mov     eax, [rbp+47h+Source]
0x18000d525  lea     r8d, [rax+1]
0x18000d529  cmp     eax, r8d
0x18000d52c  jz      short loc_18000D568
0x18000d52e  mov     [rbp+47h+Source], r8d
0x18000d532  cmp     cl, 1
0x18000d535  jnz     short loc_18000D54B
0x18000d537  mov     r9d, 2
0x18000d53d  mov     [rbp+47h+arg_0], r8w
0x18000d542  mov     edx, r9d
0x18000d545  lea     r8, [rbp+47h+arg_0]
0x18000d549  jmp     short loc_18000D55E
0x18000d54b  cmp     cl, 2
0x18000d54e  jnz     short loc_18000D568
0x18000d550  mov     eax, 4
0x18000d555  lea     r8, [rbp+47h+Source]; Source
0x18000d559  mov     r9d, eax; SourceSize
0x18000d55c  mov     edx, eax; DestinationSize
0x18000d55e  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d562  call    cs:__imp_memcpy_s
0x18000d568  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d56c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d570  lea     rcx, [rbp+47h+var_80]; this
0x18000d574  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000d579  mov     byte ptr [rdi+38h], 1
0x18000d57d  jmp     loc_18000D44F
0x18000d582  xor     al, al
0x18000d584  add     rsp, 0A8h
0x18000d58b  pop     r15
0x18000d58d  pop     r14
0x18000d58f  pop     r13
0x18000d591  pop     r12
0x18000d593  pop     rdi
0x18000d594  pop     rsi
0x18000d595  pop     rbx
0x18000d596  pop     rbp
0x18000d597  retn
```
