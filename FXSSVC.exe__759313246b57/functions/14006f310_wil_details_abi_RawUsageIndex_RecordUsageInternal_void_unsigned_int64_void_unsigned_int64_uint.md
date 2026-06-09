# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14006f310`
- end: `0x14006f6a9`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006f13c`

## callees

- `0x14006d220`
- `0x14006ec68`
- `0x14006f310`
- `0x1400713a8`
- `0x140086e76`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14006f41b`
- `msvcrt!memcpy_s` at `0x14006f4ba`
- `msvcrt!memcpy_s` at `0x14006f66c`
- `msvcrt!memcpy_s` at `0x14006f41b`
- `msvcrt!memcpy_s` at `0x14006f4ba`
- `msvcrt!memcpy_s` at `0x14006f66c`
- `msvcrt!memmove_s` at `0x14006f5fb`
- `msvcrt!memmove_s` at `0x14006f5fb`

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
0x14006f310  push    rbp
0x14006f312  push    rbx
0x14006f313  push    rsi
0x14006f314  push    rdi
0x14006f315  push    r12
0x14006f317  push    r13
0x14006f319  push    r14
0x14006f31b  push    r15
0x14006f31d  lea     rbp, [rsp-0Fh]
0x14006f322  sub     rsp, 0A8h
0x14006f329  mov     rbx, [rcx+18h]
0x14006f32d  mov     rdi, rcx
0x14006f330  xor     ecx, ecx
0x14006f332  mov     r13, r9
0x14006f335  mov     r14, r8
0x14006f338  mov     r15, rdx
0x14006f33b  test    rbx, rbx
0x14006f33e  jz      loc_14006F692
0x14006f344  movzx   eax, word ptr [rdi+2]
0x14006f348  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006f34c  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006f350  add     rbx, 0Ah
0x14006f354  mov     [rbp+47h+var_A0], ax
0x14006f358  xorps   xmm0, xmm0
0x14006f35b  mov     al, [rdi+4]
0x14006f35e  mov     [rbp+47h+Source], ecx
0x14006f361  mov     [rbp+47h+var_98], cx
0x14006f365  mov     byte ptr [rbp+47h+arg_0], cl
0x14006f368  lea     rcx, [rbp+47h+var_A0]; this
0x14006f36c  mov     [rbp+47h+var_9E], al
0x14006f36f  mov     [rbp+47h+var_A8], rbx
0x14006f373  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14006f378  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14006f37d  mov     r12, [rbp+47h+arg_20]
0x14006f381  jmp     loc_14006F4DB
0x14006f386  movzx   eax, [rbp+47h+var_98]
0x14006f38a  cmp     r14, rax
0x14006f38d  jnz     short loc_14006F3A5
0x14006f38f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14006f393  mov     r8, r14; Size
0x14006f396  mov     rcx, r15; Buf1
0x14006f399  call    memcmp_0
0x14006f39e  mov     ecx, eax
0x14006f3a0  xor     r9d, r9d
0x14006f3a3  jmp     short loc_14006F3AE
0x14006f3a5  movzx   eax, [rbp+47h+var_98]
0x14006f3a9  mov     ecx, r14d
0x14006f3ac  sub     ecx, eax
0x14006f3ae  test    ecx, ecx
0x14006f3b0  js      loc_14006F560
0x14006f3b6  jz      loc_14006F525
0x14006f3bc  mov     rbx, [rbp+47h+var_A8]
0x14006f3c0  mov     [rbp+47h+var_A8], rbx
0x14006f3c4  cmp     [rdi+10h], r9
0x14006f3c8  jbe     short loc_14006F439
0x14006f3ca  mov     rax, [rdi+20h]
0x14006f3ce  xor     edx, edx
0x14006f3d0  sub     rax, [rdi+18h]
0x14006f3d4  mov     rsi, rbx
0x14006f3d7  div     qword ptr [rdi+10h]
0x14006f3db  mov     edx, [rbp+47h+Source]
0x14006f3de  cmp     rdx, rax
0x14006f3e1  jbe     short loc_14006F42A
0x14006f3e3  cmp     edx, eax
0x14006f3e5  jz      short loc_14006F42A
0x14006f3e7  mov     edx, eax
0x14006f3e9  mov     [rbp+47h+Source], eax
0x14006f3ec  mov     al, [rbp+47h+var_9E]
0x14006f3ef  cmp     al, 1
0x14006f3f1  jnz     short loc_14006F406
0x14006f3f3  movzx   eax, dx
0x14006f3f6  mov     [rbp+47h+var_B0], dx
0x14006f3fa  mov     r9d, 2
0x14006f400  lea     r8, [rbp+47h+var_B0]
0x14006f404  jmp     short loc_14006F414
0x14006f406  cmp     al, 2
0x14006f408  jnz     short loc_14006F42A
0x14006f40a  mov     r9d, 4; SourceSize
0x14006f410  lea     r8, [rbp+47h+Source]; Source
0x14006f414  mov     rcx, [rbp+47h+Buf2]; Destination
0x14006f418  mov     rdx, r9; DestinationSize
0x14006f41b  call    cs:__imp_memcpy_s
0x14006f422  nop     dword ptr [rax+rax+00h]
0x14006f427  mov     edx, [rbp+47h+Source]
0x14006f42a  mov     ebx, edx
0x14006f42c  imul    rbx, [rdi+10h]
0x14006f431  add     rbx, rsi
0x14006f434  jmp     loc_14006F4C6
0x14006f439  movzx   eax, word ptr [rdi+6]
0x14006f43d  xorps   xmm0, xmm0
0x14006f440  mov     [rbp+47h+var_60], ax
0x14006f444  mov     esi, r9d
0x14006f447  mov     al, [rdi+8]
0x14006f44a  mov     [rbp+47h+var_5E], al
0x14006f44d  mov     eax, [rbp+47h+Source]
0x14006f450  mov     [rbp+47h+var_5C], r9d
0x14006f454  mov     [rbp+47h+var_58], r9w
0x14006f459  movdqu  [rbp+47h+var_50], xmm0
0x14006f45e  test    eax, eax
0x14006f460  jz      short loc_14006F484
0x14006f462  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006f466  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006f46a  lea     rcx, [rbp+47h+var_60]; this
0x14006f46e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14006f473  test    al, al
0x14006f475  mov     eax, [rbp+47h+Source]
0x14006f478  jz      short loc_14006F480
0x14006f47a  inc     esi
0x14006f47c  cmp     esi, eax
0x14006f47e  jb      short loc_14006F462
0x14006f480  mov     rbx, [rbp+47h+var_A8]
0x14006f484  cmp     eax, esi
0x14006f486  jz      short loc_14006F4C6
0x14006f488  mov     al, [rbp+47h+var_9E]
0x14006f48b  mov     [rbp+47h+Source], esi
0x14006f48e  cmp     al, 1
0x14006f490  jnz     short loc_14006F4A6
0x14006f492  mov     eax, 2
0x14006f497  mov     [rbp+47h+var_B0], si
0x14006f49b  mov     r9d, eax
0x14006f49e  lea     r8, [rbp+47h+var_B0]
0x14006f4a2  mov     edx, eax
0x14006f4a4  jmp     short loc_14006F4B6
0x14006f4a6  cmp     al, 2
0x14006f4a8  jnz     short loc_14006F4C6
0x14006f4aa  mov     edx, 4; DestinationSize
0x14006f4af  lea     r8, [rbp+47h+Source]; Source
0x14006f4b3  mov     r9d, edx; SourceSize
0x14006f4b6  mov     rcx, [rbp+47h+Buf2]; Destination
0x14006f4ba  call    cs:__imp_memcpy_s
0x14006f4c1  nop     dword ptr [rax+rax+00h]
0x14006f4c6  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006f4ca  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006f4ce  lea     rcx, [rbp+47h+var_A0]; this
0x14006f4d2  mov     [rbp+47h+var_A8], rbx
0x14006f4d6  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14006f4db  xor     r9d, r9d
0x14006f4de  mov     sil, al
0x14006f4e1  test    al, al
0x14006f4e3  jnz     loc_14006F386
0x14006f4e9  mov     rbx, [rbp+47h+var_A8]
0x14006f4ed  mov     [rdi+20h], rbx
0x14006f4f1  mov     rcx, r9
0x14006f4f4  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14006f4f8  jnz     loc_14006F583
0x14006f4fe  movzx   eax, [rbp+47h+var_A0]
0x14006f502  mov     [rbp+47h+Source], 1
0x14006f509  mov     [rbp+47h+var_98], r14w
0x14006f50e  mov     [rbp+47h+Buf2], r9
0x14006f512  mov     [rbp+47h+Buf2+8], r15
0x14006f516  test    ax, ax
0x14006f519  jnz     short loc_14006F56B
0x14006f51b  movzx   ecx, r14w
0x14006f51f  add     rcx, 2
0x14006f523  jmp     short loc_14006F56E
0x14006f525  mov     eax, [rbp+47h+arg_28]
0x14006f528  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x14006f52c  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x14006f530  mov     r9, r13; void *
0x14006f533  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14006f537  mov     rcx, rdi; this
0x14006f53a  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x14006f53f  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14006f544  xor     r9d, r9d
0x14006f547  mov     [rbp+47h+var_A8], rax
0x14006f54b  mov     rbx, rax
0x14006f54e  test    rax, rax
0x14006f551  jnz     short loc_14006F55A
0x14006f553  mov     al, 1
0x14006f555  jmp     loc_14006F694
0x14006f55a  mov     byte ptr [rbp+47h+arg_0], 1
0x14006f55e  jmp     short loc_14006F564
0x14006f560  mov     [rbp+47h+var_A8], rbx
0x14006f564  test    sil, sil
0x14006f567  jnz     short loc_14006F4F1
0x14006f569  jmp     short loc_14006F4ED
0x14006f56b  mov     rcx, rax
0x14006f56e  mov     al, [rbp+47h+var_9E]
0x14006f571  cmp     al, 1
0x14006f573  jnz     short loc_14006F57B
0x14006f575  add     rcx, 2
0x14006f579  jmp     short loc_14006F583
0x14006f57b  cmp     al, 2
0x14006f57d  jnz     short loc_14006F583
0x14006f57f  add     rcx, 4
0x14006f583  movzx   eax, word ptr [rdi+6]
0x14006f587  mov     dl, [rdi+8]
0x14006f58a  mov     r8d, [rbp+47h+arg_28]
0x14006f58e  mov     [rbp+47h+var_80], ax
0x14006f592  mov     [rbp+47h+var_7E], dl
0x14006f595  mov     [rbp+47h+var_7C], r8d
0x14006f599  mov     [rbp+47h+var_78], r12w
0x14006f59e  mov     [rbp+47h+var_70], r9
0x14006f5a2  mov     [rbp+47h+var_68], r13
0x14006f5a6  test    ax, ax
0x14006f5a9  jnz     short loc_14006F5B3
0x14006f5ab  movzx   eax, r12w
0x14006f5af  add     rax, 2
0x14006f5b3  cmp     dl, 1
0x14006f5b6  jnz     short loc_14006F5BE
0x14006f5b8  add     rax, 2
0x14006f5bc  jmp     short loc_14006F5C7
0x14006f5be  cmp     dl, 2
0x14006f5c1  jnz     short loc_14006F5C7
0x14006f5c3  add     rax, 4
0x14006f5c7  mov     rdx, [rdi+28h]
0x14006f5cb  lea     rsi, [rax+rcx]
0x14006f5cf  mov     r9, [rdi+20h]
0x14006f5d3  mov     rcx, rdx
0x14006f5d6  sub     rcx, r9
0x14006f5d9  cmp     r9, rdx
0x14006f5dc  sbb     rax, rax
0x14006f5df  and     rax, rcx
0x14006f5e2  cmp     rax, rsi
0x14006f5e5  jb      loc_14006F692
0x14006f5eb  sub     rdx, rsi
0x14006f5ee  lea     rcx, [rsi+rbx]; Destination
0x14006f5f2  sub     rdx, rbx; DestinationSize
0x14006f5f5  sub     r9, rbx; SourceSize
0x14006f5f8  mov     r8, rbx; Source
0x14006f5fb  call    cs:__imp_memmove_s
0x14006f602  nop     dword ptr [rax+rax+00h]
0x14006f607  add     [rdi+20h], rsi
0x14006f60b  xor     ebx, ebx
0x14006f60d  cmp     byte ptr [rbp+47h+arg_0], bl
0x14006f610  jnz     short loc_14006F625
0x14006f612  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006f616  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006f61a  lea     rcx, [rbp+47h+var_A0]; this
0x14006f61e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14006f623  jmp     short loc_14006F678
0x14006f625  mov     cl, [rbp+47h+var_9E]
0x14006f628  test    cl, cl
0x14006f62a  jz      short loc_14006F678
0x14006f62c  mov     eax, [rbp+47h+Source]
0x14006f62f  lea     r8d, [rax+1]
0x14006f633  cmp     eax, r8d
0x14006f636  jz      short loc_14006F678
0x14006f638  mov     [rbp+47h+Source], r8d
0x14006f63c  cmp     cl, 1
0x14006f63f  jnz     short loc_14006F655
0x14006f641  mov     r9d, 2
0x14006f647  mov     [rbp+47h+arg_0], r8w
0x14006f64c  mov     edx, r9d
0x14006f64f  lea     r8, [rbp+47h+arg_0]
0x14006f653  jmp     short loc_14006F668
0x14006f655  cmp     cl, 2
0x14006f658  jnz     short loc_14006F678
0x14006f65a  mov     eax, 4
0x14006f65f  lea     r8, [rbp+47h+Source]; Source
0x14006f663  mov     r9d, eax; SourceSize
0x14006f666  mov     edx, eax; DestinationSize
0x14006f668  mov     rcx, [rbp+47h+Buf2]; Destination
0x14006f66c  call    cs:__imp_memcpy_s
0x14006f673  nop     dword ptr [rax+rax+00h]
0x14006f678  mov     r8, [rdi+20h]; unsigned __int8 *
0x14006f67c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14006f680  lea     rcx, [rbp+47h+var_80]; this
0x14006f684  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14006f689  mov     byte ptr [rdi+38h], 1
0x14006f68d  jmp     loc_14006F553
0x14006f692  xor     al, al
0x14006f694  add     rsp, 0A8h
0x14006f69b  pop     r15
0x14006f69d  pop     r14
0x14006f69f  pop     r13
0x14006f6a1  pop     r12
0x14006f6a3  pop     rdi
0x14006f6a4  pop     rsi
0x14006f6a5  pop     rbx
0x14006f6a6  pop     rbp
0x14006f6a7  retn
```
