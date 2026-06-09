# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180014964`
- end: `0x180014ce4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800147a8`

## callees

- `0x18001203c`
- `0x18001419c`
- `0x180014964`
- `0x1800160fc`
- `0x180019716`

## import_xrefs

- `msvcrt!memmove_s` at `0x180014c43`
- `msvcrt!memmove_s` at `0x180014c43`
- `msvcrt!memcpy_s` at `0x180014a6f`
- `msvcrt!memcpy_s` at `0x180014b08`
- `msvcrt!memcpy_s` at `0x180014cae`
- `msvcrt!memcpy_s` at `0x180014a6f`
- `msvcrt!memcpy_s` at `0x180014b08`
- `msvcrt!memcpy_s` at `0x180014cae`

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
0x180014964  push    rbp
0x180014966  push    rbx
0x180014967  push    rsi
0x180014968  push    rdi
0x180014969  push    r12
0x18001496b  push    r13
0x18001496d  push    r14
0x18001496f  push    r15
0x180014971  lea     rbp, [rsp-0Fh]
0x180014976  sub     rsp, 0A8h
0x18001497d  mov     rbx, [rcx+18h]
0x180014981  mov     rdi, rcx
0x180014984  xor     ecx, ecx
0x180014986  mov     r13, r9
0x180014989  mov     r14, r8
0x18001498c  mov     r15, rdx
0x18001498f  test    rbx, rbx
0x180014992  jz      loc_180014CCE
0x180014998  movzx   eax, word ptr [rdi+2]
0x18001499c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800149a0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800149a4  add     rbx, 0Ah
0x1800149a8  mov     [rbp+47h+var_A0], ax
0x1800149ac  xorps   xmm0, xmm0
0x1800149af  mov     al, [rdi+4]
0x1800149b2  mov     [rbp+47h+Source], ecx
0x1800149b5  mov     [rbp+47h+var_98], cx
0x1800149b9  mov     byte ptr [rbp+47h+arg_0], cl
0x1800149bc  lea     rcx, [rbp+47h+var_A0]; this
0x1800149c0  mov     [rbp+47h+var_9E], al
0x1800149c3  mov     [rbp+47h+var_A8], rbx
0x1800149c7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800149cc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800149d1  mov     r12, [rbp+47h+arg_20]
0x1800149d5  jmp     loc_180014B23
0x1800149da  movzx   eax, [rbp+47h+var_98]
0x1800149de  cmp     r14, rax
0x1800149e1  jnz     short loc_1800149F9
0x1800149e3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1800149e7  mov     r8, r14; Size
0x1800149ea  mov     rcx, r15; Buf1
0x1800149ed  call    memcmp_0
0x1800149f2  mov     ecx, eax
0x1800149f4  xor     r9d, r9d
0x1800149f7  jmp     short loc_180014A02
0x1800149f9  movzx   eax, [rbp+47h+var_98]
0x1800149fd  mov     ecx, r14d
0x180014a00  sub     ecx, eax
0x180014a02  test    ecx, ecx
0x180014a04  js      loc_180014BA8
0x180014a0a  jz      loc_180014B6D
0x180014a10  mov     rbx, [rbp+47h+var_A8]
0x180014a14  mov     [rbp+47h+var_A8], rbx
0x180014a18  cmp     [rdi+10h], r9
0x180014a1c  jbe     short loc_180014A87
0x180014a1e  mov     rax, [rdi+20h]
0x180014a22  xor     edx, edx
0x180014a24  sub     rax, [rdi+18h]
0x180014a28  mov     rsi, rbx
0x180014a2b  div     qword ptr [rdi+10h]
0x180014a2f  mov     edx, [rbp+47h+Source]
0x180014a32  cmp     rdx, rax
0x180014a35  jbe     short loc_180014A78
0x180014a37  cmp     edx, eax
0x180014a39  jz      short loc_180014A78
0x180014a3b  mov     edx, eax
0x180014a3d  mov     [rbp+47h+Source], eax
0x180014a40  mov     al, [rbp+47h+var_9E]
0x180014a43  cmp     al, 1
0x180014a45  jnz     short loc_180014A5A
0x180014a47  movzx   eax, dx
0x180014a4a  mov     [rbp+47h+var_B0], dx
0x180014a4e  mov     r9d, 2
0x180014a54  lea     r8, [rbp+47h+var_B0]
0x180014a58  jmp     short loc_180014A68
0x180014a5a  cmp     al, 2
0x180014a5c  jnz     short loc_180014A78
0x180014a5e  mov     r9d, 4; SourceSize
0x180014a64  lea     r8, [rbp+47h+Source]; Source
0x180014a68  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014a6c  mov     rdx, r9; DestinationSize
0x180014a6f  call    cs:__imp_memcpy_s
0x180014a75  mov     edx, [rbp+47h+Source]
0x180014a78  mov     ebx, edx
0x180014a7a  imul    rbx, [rdi+10h]
0x180014a7f  add     rbx, rsi
0x180014a82  jmp     loc_180014B0E
0x180014a87  movzx   eax, word ptr [rdi+6]
0x180014a8b  xorps   xmm0, xmm0
0x180014a8e  mov     [rbp+47h+var_60], ax
0x180014a92  mov     esi, r9d
0x180014a95  mov     al, [rdi+8]
0x180014a98  mov     [rbp+47h+var_5E], al
0x180014a9b  mov     eax, [rbp+47h+Source]
0x180014a9e  mov     [rbp+47h+var_5C], r9d
0x180014aa2  mov     [rbp+47h+var_58], r9w
0x180014aa7  movdqu  [rbp+47h+var_50], xmm0
0x180014aac  test    eax, eax
0x180014aae  jz      short loc_180014AD2
0x180014ab0  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014ab4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014ab8  lea     rcx, [rbp+47h+var_60]; this
0x180014abc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014ac1  test    al, al
0x180014ac3  mov     eax, [rbp+47h+Source]
0x180014ac6  jz      short loc_180014ACE
0x180014ac8  inc     esi
0x180014aca  cmp     esi, eax
0x180014acc  jb      short loc_180014AB0
0x180014ace  mov     rbx, [rbp+47h+var_A8]
0x180014ad2  cmp     eax, esi
0x180014ad4  jz      short loc_180014B0E
0x180014ad6  mov     al, [rbp+47h+var_9E]
0x180014ad9  mov     [rbp+47h+Source], esi
0x180014adc  cmp     al, 1
0x180014ade  jnz     short loc_180014AF4
0x180014ae0  mov     eax, 2
0x180014ae5  mov     [rbp+47h+var_B0], si
0x180014ae9  mov     r9d, eax
0x180014aec  lea     r8, [rbp+47h+var_B0]
0x180014af0  mov     edx, eax
0x180014af2  jmp     short loc_180014B04
0x180014af4  cmp     al, 2
0x180014af6  jnz     short loc_180014B0E
0x180014af8  mov     edx, 4; DestinationSize
0x180014afd  lea     r8, [rbp+47h+Source]; Source
0x180014b01  mov     r9d, edx; SourceSize
0x180014b04  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014b08  call    cs:__imp_memcpy_s
0x180014b0e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014b12  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014b16  lea     rcx, [rbp+47h+var_A0]; this
0x180014b1a  mov     [rbp+47h+var_A8], rbx
0x180014b1e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014b23  xor     r9d, r9d
0x180014b26  mov     sil, al
0x180014b29  test    al, al
0x180014b2b  jnz     loc_1800149DA
0x180014b31  mov     rbx, [rbp+47h+var_A8]
0x180014b35  mov     [rdi+20h], rbx
0x180014b39  mov     rcx, r9
0x180014b3c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180014b40  jnz     loc_180014BCB
0x180014b46  movzx   eax, [rbp+47h+var_A0]
0x180014b4a  mov     [rbp+47h+Source], 1
0x180014b51  mov     [rbp+47h+var_98], r14w
0x180014b56  mov     [rbp+47h+Buf2], r9
0x180014b5a  mov     [rbp+47h+Buf2+8], r15
0x180014b5e  test    ax, ax
0x180014b61  jnz     short loc_180014BB3
0x180014b63  movzx   ecx, r14w
0x180014b67  add     rcx, 2
0x180014b6b  jmp     short loc_180014BB6
0x180014b6d  mov     eax, [rbp+47h+arg_28]
0x180014b70  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180014b74  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180014b78  mov     r9, r13; void *
0x180014b7b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180014b7f  mov     rcx, rdi; this
0x180014b82  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180014b87  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180014b8c  xor     r9d, r9d
0x180014b8f  mov     [rbp+47h+var_A8], rax
0x180014b93  mov     rbx, rax
0x180014b96  test    rax, rax
0x180014b99  jnz     short loc_180014BA2
0x180014b9b  mov     al, 1
0x180014b9d  jmp     loc_180014CD0
0x180014ba2  mov     byte ptr [rbp+47h+arg_0], 1
0x180014ba6  jmp     short loc_180014BAC
0x180014ba8  mov     [rbp+47h+var_A8], rbx
0x180014bac  test    sil, sil
0x180014baf  jnz     short loc_180014B39
0x180014bb1  jmp     short loc_180014B35
0x180014bb3  mov     rcx, rax
0x180014bb6  mov     al, [rbp+47h+var_9E]
0x180014bb9  cmp     al, 1
0x180014bbb  jnz     short loc_180014BC3
0x180014bbd  add     rcx, 2
0x180014bc1  jmp     short loc_180014BCB
0x180014bc3  cmp     al, 2
0x180014bc5  jnz     short loc_180014BCB
0x180014bc7  add     rcx, 4
0x180014bcb  movzx   eax, word ptr [rdi+6]
0x180014bcf  mov     dl, [rdi+8]
0x180014bd2  mov     r8d, [rbp+47h+arg_28]
0x180014bd6  mov     [rbp+47h+var_80], ax
0x180014bda  mov     [rbp+47h+var_7E], dl
0x180014bdd  mov     [rbp+47h+var_7C], r8d
0x180014be1  mov     [rbp+47h+var_78], r12w
0x180014be6  mov     [rbp+47h+var_70], r9
0x180014bea  mov     [rbp+47h+var_68], r13
0x180014bee  test    ax, ax
0x180014bf1  jnz     short loc_180014BFB
0x180014bf3  movzx   eax, r12w
0x180014bf7  add     rax, 2
0x180014bfb  cmp     dl, 1
0x180014bfe  jnz     short loc_180014C06
0x180014c00  add     rax, 2
0x180014c04  jmp     short loc_180014C0F
0x180014c06  cmp     dl, 2
0x180014c09  jnz     short loc_180014C0F
0x180014c0b  add     rax, 4
0x180014c0f  mov     rdx, [rdi+28h]
0x180014c13  lea     rsi, [rax+rcx]
0x180014c17  mov     r9, [rdi+20h]
0x180014c1b  mov     rcx, rdx
0x180014c1e  sub     rcx, r9
0x180014c21  cmp     r9, rdx
0x180014c24  sbb     rax, rax
0x180014c27  and     rax, rcx
0x180014c2a  cmp     rax, rsi
0x180014c2d  jb      loc_180014CCE
0x180014c33  sub     rdx, rsi
0x180014c36  lea     rcx, [rsi+rbx]; Destination
0x180014c3a  sub     rdx, rbx; DestinationSize
0x180014c3d  sub     r9, rbx; SourceSize
0x180014c40  mov     r8, rbx; Source
0x180014c43  call    cs:__imp_memmove_s
0x180014c49  add     [rdi+20h], rsi
0x180014c4d  xor     ebx, ebx
0x180014c4f  cmp     byte ptr [rbp+47h+arg_0], bl
0x180014c52  jnz     short loc_180014C67
0x180014c54  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014c58  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014c5c  lea     rcx, [rbp+47h+var_A0]; this
0x180014c60  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014c65  jmp     short loc_180014CB4
0x180014c67  mov     cl, [rbp+47h+var_9E]
0x180014c6a  test    cl, cl
0x180014c6c  jz      short loc_180014CB4
0x180014c6e  mov     eax, [rbp+47h+Source]
0x180014c71  lea     r8d, [rax+1]
0x180014c75  cmp     eax, r8d
0x180014c78  jz      short loc_180014CB4
0x180014c7a  mov     [rbp+47h+Source], r8d
0x180014c7e  cmp     cl, 1
0x180014c81  jnz     short loc_180014C97
0x180014c83  mov     r9d, 2
0x180014c89  mov     [rbp+47h+arg_0], r8w
0x180014c8e  mov     edx, r9d
0x180014c91  lea     r8, [rbp+47h+arg_0]
0x180014c95  jmp     short loc_180014CAA
0x180014c97  cmp     cl, 2
0x180014c9a  jnz     short loc_180014CB4
0x180014c9c  mov     eax, 4
0x180014ca1  lea     r8, [rbp+47h+Source]; Source
0x180014ca5  mov     r9d, eax; SourceSize
0x180014ca8  mov     edx, eax; DestinationSize
0x180014caa  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014cae  call    cs:__imp_memcpy_s
0x180014cb4  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014cb8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014cbc  lea     rcx, [rbp+47h+var_80]; this
0x180014cc0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014cc5  mov     byte ptr [rdi+38h], 1
0x180014cc9  jmp     loc_180014B9B
0x180014cce  xor     al, al
0x180014cd0  add     rsp, 0A8h
0x180014cd7  pop     r15
0x180014cd9  pop     r14
0x180014cdb  pop     r13
0x180014cdd  pop     r12
0x180014cdf  pop     rdi
0x180014ce0  pop     rsi
0x180014ce1  pop     rbx
0x180014ce2  pop     rbp
0x180014ce3  retn
```
