# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007c84`
- end: `0x180008019`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `917`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007ab8`

## callees

- `0x180005240`
- `0x1800073bc`
- `0x180007c84`
- `0x18000b544`
- `0x180010786`
- `0x1800107c0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007f65`
- `msvcrt!memmove_s` at `0x180007f65`
- `msvcrt!memcpy_s` at `0x180007d91`
- `msvcrt!memcpy_s` at `0x180007e2a`
- `msvcrt!memcpy_s` at `0x180007fd0`
- `msvcrt!memcpy_s` at `0x180007d91`
- `msvcrt!memcpy_s` at `0x180007e2a`
- `msvcrt!memcpy_s` at `0x180007fd0`

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
  unsigned __int8 *v11; // rbx
  int v12; // ecx
  unsigned __int8 *v13; // rsi
  unsigned __int64 v14; // rax
  unsigned int v15; // edx
  rsize_t v16; // r9
  unsigned int *p_Source; // r8
  unsigned int v18; // esi
  unsigned int v19; // eax
  bool v20; // zf
  rsize_t v21; // r9
  unsigned int *v22; // r8
  rsize_t v23; // rdx
  unsigned __int8 *v24; // r8
  __int64 v26; // rcx
  __int64 v28; // rax
  char v29; // dl
  unsigned __int64 v30; // rdx
  __int64 v31; // rsi
  unsigned __int64 v32; // r9
  __int16 v33; // r8
  rsize_t v34; // r9
  rsize_t v35; // rdx
  unsigned int *v36; // r8
  char v37; // [rsp+30h] [rbp-69h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-59h]
  _WORD v40[2]; // [rsp+44h] [rbp-55h] BYREF
  unsigned __int16 v41; // [rsp+48h] [rbp-51h] BYREF
  char v42; // [rsp+4Ah] [rbp-4Fh]
  unsigned int Source; // [rsp+4Ch] [rbp-4Dh] BYREF
  unsigned __int16 v44; // [rsp+50h] [rbp-49h]
  void *Buf2[2]; // [rsp+58h] [rbp-41h]
  __int16 v46; // [rsp+68h] [rbp-31h] BYREF
  char v47; // [rsp+6Ah] [rbp-2Fh]
  unsigned int v48; // [rsp+6Ch] [rbp-2Dh]
  __int16 v49; // [rsp+70h] [rbp-29h]
  __int64 v50; // [rsp+78h] [rbp-21h]
  void *v51; // [rsp+80h] [rbp-19h]
  __int16 v52; // [rsp+88h] [rbp-11h] BYREF
  char v53; // [rsp+8Ah] [rbp-Fh]
  int v54; // [rsp+8Ch] [rbp-Dh]
  __int16 v55; // [rsp+90h] [rbp-9h]
  __int128 v56; // [rsp+98h] [rbp-1h]

  v6 = *((_QWORD *)this + 3);
  v39 = a6;
  if ( !v6 )
    return 0;
  v41 = *((_WORD *)this + 1);
  v11 = (unsigned __int8 *)(v6 + 10);
  v42 = *((_BYTE *)this + 4);
  Source = 0;
  v44 = 0;
  *(_OWORD *)Buf2 = 0;
  v37 = 0;
  while ( 1 )
  {
    v24 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v11;
    if ( !wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v41,
            &InsertionPointOrIncrement,
            v24) )
    {
      v11 = InsertionPointOrIncrement;
      *((_QWORD *)this + 4) = InsertionPointOrIncrement;
      goto LABEL_29;
    }
    if ( Size == v44 )
      v12 = memcmp_0(Buf1, Buf2[1], Size);
    else
      v12 = Size - v44;
    if ( v12 < 0 )
    {
      InsertionPointOrIncrement = v11;
      goto LABEL_29;
    }
    if ( !v12 )
      break;
    v11 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v13 = InsertionPointOrIncrement;
      v14 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v15 = Source;
      if ( Source > v14 && Source != (_DWORD)v14 )
      {
        v15 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v15;
        if ( v42 == 1 )
        {
          v40[0] = v14;
          v16 = 2;
          p_Source = (unsigned int *)v40;
        }
        else
        {
          if ( v42 != 2 )
            goto LABEL_16;
          v16 = 4;
          p_Source = &Source;
        }
        memcpy_s(Buf2[0], v16, p_Source, v16);
        v15 = Source;
      }
LABEL_16:
      v11 = &v13[*((_QWORD *)this + 2) * v15];
    }
    else
    {
      v52 = *((_WORD *)this + 3);
      v18 = 0;
      v53 = *((_BYTE *)this + 8);
      v19 = Source;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      if ( Source )
      {
        do
        {
          v20 = !wil::details_abi::UsageIndexProperty::Read(
                   (wil::details_abi::UsageIndexProperty *)&v52,
                   &InsertionPointOrIncrement,
                   *((unsigned __int8 **)this + 4));
          v19 = Source;
          if ( v20 )
            break;
          ++v18;
        }
        while ( v18 < Source );
        v11 = InsertionPointOrIncrement;
      }
      if ( v19 != v18 )
      {
        Source = v18;
        if ( v42 == 1 )
        {
          v40[0] = v18;
          v21 = 2;
          v22 = (unsigned int *)v40;
          v23 = 2;
          goto LABEL_26;
        }
        if ( v42 == 2 )
        {
          v23 = 4;
          v22 = &Source;
          v21 = 4;
LABEL_26:
          memcpy_s(Buf2[0], v23, v22, v21);
        }
      }
    }
  }
  InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                this,
                                (struct wil::details_abi::UsageIndexProperty *)&v41,
                                InsertionPointOrIncrement,
                                a4,
                                a5,
                                v39);
  v11 = InsertionPointOrIncrement;
  if ( !InsertionPointOrIncrement )
    return 1;
  v37 = 1;
LABEL_29:
  v26 = 0;
  if ( !v37 )
  {
    Source = 1;
    v44 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v41 )
      v26 = v41;
    else
      v26 = (unsigned __int16)Size + 2LL;
    if ( v42 == 1 )
    {
      v26 += 2;
    }
    else if ( v42 == 2 )
    {
      v26 += 4;
    }
  }
  v28 = *((unsigned __int16 *)this + 3);
  v29 = *((_BYTE *)this + 8);
  v46 = v28;
  v47 = v29;
  v48 = v39;
  v49 = a5;
  v50 = 0;
  v51 = a4;
  if ( !(_WORD)v28 )
    v28 = (unsigned __int16)a5 + 2LL;
  if ( v29 == 1 )
  {
    v28 += 2;
  }
  else if ( v29 == 2 )
  {
    v28 += 4;
  }
  v30 = *((_QWORD *)this + 5);
  v31 = v28 + v26;
  v32 = *((_QWORD *)this + 4);
  if ( ((v30 - v32) & -(__int64)(v32 < v30)) >= v28 + v26 )
  {
    memmove_s(&v11[v31], v30 - v31 - (_QWORD)v11, v11, v32 - (_QWORD)v11);
    *((_QWORD *)this + 4) += v31;
    if ( !v37 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v41,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
LABEL_57:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v46,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v42 )
      goto LABEL_57;
    v33 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_57;
    ++Source;
    if ( v42 == 1 )
    {
      v34 = 2;
      v40[0] = v33;
      v35 = 2;
      v36 = (unsigned int *)v40;
    }
    else
    {
      if ( v42 != 2 )
        goto LABEL_57;
      v36 = &Source;
      v34 = 4;
      v35 = 4;
    }
    memcpy_s(Buf2[0], v35, v36, v34);
    goto LABEL_57;
  }
  return 0;
}

```

## disassembly

```asm
0x180007c84  mov     [rsp-8+arg_8], rbx
0x180007c89  push    rbp
0x180007c8a  push    rsi
0x180007c8b  push    rdi
0x180007c8c  push    r12
0x180007c8e  push    r13
0x180007c90  push    r14
0x180007c92  push    r15
0x180007c94  lea     rbp, [rsp-17h]
0x180007c99  sub     rsp, 0B0h
0x180007ca0  mov     rax, cs:__security_cookie
0x180007ca7  xor     rax, rsp
0x180007caa  mov     [rbp+47h+var_38], rax
0x180007cae  mov     rbx, [rcx+18h]
0x180007cb2  mov     rdi, rcx
0x180007cb5  mov     eax, [rbp+47h+arg_28]
0x180007cb8  xor     ecx, ecx
0x180007cba  mov     r15, [rbp+47h+arg_20]
0x180007cbe  mov     r13, r9
0x180007cc1  mov     [rbp+47h+var_A0], eax
0x180007cc4  mov     r14, r8
0x180007cc7  mov     r12, rdx
0x180007cca  test    rbx, rbx
0x180007ccd  jz      loc_180007FF0
0x180007cd3  movzx   eax, word ptr [rdi+2]
0x180007cd7  xorps   xmm0, xmm0
0x180007cda  mov     [rbp+47h+var_98], ax
0x180007cde  add     rbx, 0Ah
0x180007ce2  mov     al, [rdi+4]
0x180007ce5  mov     [rbp+47h+var_96], al
0x180007ce8  mov     [rbp+47h+Source], ecx
0x180007ceb  mov     [rbp+47h+var_90], cx
0x180007cef  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180007cf4  mov     [rbp+47h+var_B0], cl
0x180007cf7  jmp     loc_180007E30
0x180007cfc  movzx   ecx, [rbp+47h+var_90]
0x180007d00  cmp     r14, rcx
0x180007d03  jnz     short loc_180007D1B
0x180007d05  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180007d09  mov     r8, r14; Size
0x180007d0c  mov     rcx, r12; Buf1
0x180007d0f  call    memcmp_0
0x180007d14  mov     ecx, eax
0x180007d16  xor     r9d, r9d
0x180007d19  jmp     short loc_180007D24
0x180007d1b  movzx   eax, [rbp+47h+var_90]
0x180007d1f  mov     ecx, r14d
0x180007d22  sub     ecx, eax
0x180007d24  test    ecx, ecx
0x180007d26  js      loc_180007ECA
0x180007d2c  jz      loc_180007E8F
0x180007d32  mov     rbx, [rbp+47h+var_A8]
0x180007d36  mov     [rbp+47h+var_A8], rbx
0x180007d3a  cmp     [rdi+10h], r9
0x180007d3e  jbe     short loc_180007DA9
0x180007d40  mov     rax, [rdi+20h]
0x180007d44  xor     edx, edx
0x180007d46  sub     rax, [rdi+18h]
0x180007d4a  mov     rsi, rbx
0x180007d4d  div     qword ptr [rdi+10h]
0x180007d51  mov     edx, [rbp+47h+Source]
0x180007d54  cmp     rdx, rax
0x180007d57  jbe     short loc_180007D9A
0x180007d59  cmp     edx, eax
0x180007d5b  jz      short loc_180007D9A
0x180007d5d  mov     edx, eax
0x180007d5f  mov     [rbp+47h+Source], eax
0x180007d62  mov     al, [rbp+47h+var_96]
0x180007d65  cmp     al, 1
0x180007d67  jnz     short loc_180007D7C
0x180007d69  movzx   eax, dx
0x180007d6c  mov     [rbp+47h+var_9C], dx
0x180007d70  mov     r9d, 2
0x180007d76  lea     r8, [rbp+47h+var_9C]
0x180007d7a  jmp     short loc_180007D8A
0x180007d7c  cmp     al, 2
0x180007d7e  jnz     short loc_180007D9A
0x180007d80  mov     r9d, 4; SourceSize
0x180007d86  lea     r8, [rbp+47h+Source]; Source
0x180007d8a  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007d8e  mov     rdx, r9; DestinationSize
0x180007d91  call    cs:__imp_memcpy_s
0x180007d97  mov     edx, [rbp+47h+Source]
0x180007d9a  mov     ebx, edx
0x180007d9c  imul    rbx, [rdi+10h]
0x180007da1  add     rbx, rsi
0x180007da4  jmp     loc_180007E30
0x180007da9  movzx   eax, word ptr [rdi+6]
0x180007dad  xorps   xmm0, xmm0
0x180007db0  mov     [rbp+47h+var_58], ax
0x180007db4  mov     esi, r9d
0x180007db7  mov     al, [rdi+8]
0x180007dba  mov     [rbp+47h+var_56], al
0x180007dbd  mov     eax, [rbp+47h+Source]
0x180007dc0  mov     [rbp+47h+var_54], r9d
0x180007dc4  mov     [rbp+47h+var_50], r9w
0x180007dc9  movdqu  [rbp+47h+var_48], xmm0
0x180007dce  test    eax, eax
0x180007dd0  jz      short loc_180007DF4
0x180007dd2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007dd6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007dda  lea     rcx, [rbp+47h+var_58]; this
0x180007dde  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007de3  test    al, al
0x180007de5  mov     eax, [rbp+47h+Source]
0x180007de8  jz      short loc_180007DF0
0x180007dea  inc     esi
0x180007dec  cmp     esi, eax
0x180007dee  jb      short loc_180007DD2
0x180007df0  mov     rbx, [rbp+47h+var_A8]
0x180007df4  cmp     eax, esi
0x180007df6  jz      short loc_180007E30
0x180007df8  mov     al, [rbp+47h+var_96]
0x180007dfb  mov     [rbp+47h+Source], esi
0x180007dfe  cmp     al, 1
0x180007e00  jnz     short loc_180007E16
0x180007e02  mov     eax, 2
0x180007e07  mov     [rbp+47h+var_9C], si
0x180007e0b  mov     r9d, eax
0x180007e0e  lea     r8, [rbp+47h+var_9C]
0x180007e12  mov     edx, eax
0x180007e14  jmp     short loc_180007E26
0x180007e16  cmp     al, 2
0x180007e18  jnz     short loc_180007E30
0x180007e1a  mov     edx, 4; DestinationSize
0x180007e1f  lea     r8, [rbp+47h+Source]; Source
0x180007e23  mov     r9d, edx; SourceSize
0x180007e26  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007e2a  call    cs:__imp_memcpy_s
0x180007e30  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007e34  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007e38  lea     rcx, [rbp+47h+var_98]; this
0x180007e3c  mov     [rbp+47h+var_A8], rbx
0x180007e40  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007e45  xor     r9d, r9d
0x180007e48  mov     sil, al
0x180007e4b  test    al, al
0x180007e4d  jnz     loc_180007CFC
0x180007e53  mov     rbx, [rbp+47h+var_A8]
0x180007e57  mov     [rdi+20h], rbx
0x180007e5b  mov     rcx, r9
0x180007e5e  cmp     [rbp+47h+var_B0], r9b
0x180007e62  jnz     loc_180007EED
0x180007e68  movzx   eax, [rbp+47h+var_98]
0x180007e6c  mov     [rbp+47h+Source], 1
0x180007e73  mov     [rbp+47h+var_90], r14w
0x180007e78  mov     [rbp+47h+Buf2], r9
0x180007e7c  mov     [rbp+47h+Buf2+8], r12
0x180007e80  test    ax, ax
0x180007e83  jnz     short loc_180007ED5
0x180007e85  movzx   ecx, r14w
0x180007e89  add     rcx, 2
0x180007e8d  jmp     short loc_180007ED8
0x180007e8f  mov     eax, [rbp+47h+var_A0]
0x180007e92  lea     rdx, [rbp+47h+var_98]; struct wil::details_abi::UsageIndexProperty *
0x180007e96  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180007e9a  mov     r9, r13; void *
0x180007e9d  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180007ea1  mov     rcx, rdi; this
0x180007ea4  mov     [rsp+0E0h+var_C0], r15; unsigned __int64
0x180007ea9  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180007eae  xor     r9d, r9d
0x180007eb1  mov     [rbp+47h+var_A8], rax
0x180007eb5  mov     rbx, rax
0x180007eb8  test    rax, rax
0x180007ebb  jnz     short loc_180007EC4
0x180007ebd  mov     al, 1
0x180007ebf  jmp     loc_180007FF2
0x180007ec4  mov     [rbp+47h+var_B0], 1
0x180007ec8  jmp     short loc_180007ECE
0x180007eca  mov     [rbp+47h+var_A8], rbx
0x180007ece  test    sil, sil
0x180007ed1  jnz     short loc_180007E5B
0x180007ed3  jmp     short loc_180007E57
0x180007ed5  mov     rcx, rax
0x180007ed8  mov     al, [rbp+47h+var_96]
0x180007edb  cmp     al, 1
0x180007edd  jnz     short loc_180007EE5
0x180007edf  add     rcx, 2
0x180007ee3  jmp     short loc_180007EED
0x180007ee5  cmp     al, 2
0x180007ee7  jnz     short loc_180007EED
0x180007ee9  add     rcx, 4
0x180007eed  movzx   eax, word ptr [rdi+6]
0x180007ef1  mov     dl, [rdi+8]
0x180007ef4  mov     r8d, [rbp+47h+var_A0]
0x180007ef8  mov     [rbp+47h+var_78], ax
0x180007efc  mov     [rbp+47h+var_76], dl
0x180007eff  mov     [rbp+47h+var_74], r8d
0x180007f03  mov     [rbp+47h+var_70], r15w
0x180007f08  mov     [rbp+47h+var_68], r9
0x180007f0c  mov     [rbp+47h+var_60], r13
0x180007f10  test    ax, ax
0x180007f13  jnz     short loc_180007F1D
0x180007f15  movzx   eax, r15w
0x180007f19  add     rax, 2
0x180007f1d  cmp     dl, 1
0x180007f20  jnz     short loc_180007F28
0x180007f22  add     rax, 2
0x180007f26  jmp     short loc_180007F31
0x180007f28  cmp     dl, 2
0x180007f2b  jnz     short loc_180007F31
0x180007f2d  add     rax, 4
0x180007f31  mov     rdx, [rdi+28h]
0x180007f35  lea     rsi, [rax+rcx]
0x180007f39  mov     r9, [rdi+20h]
0x180007f3d  mov     rcx, rdx
0x180007f40  sub     rcx, r9
0x180007f43  cmp     r9, rdx
0x180007f46  sbb     rax, rax
0x180007f49  and     rax, rcx
0x180007f4c  cmp     rax, rsi
0x180007f4f  jb      loc_180007FF0
0x180007f55  sub     rdx, rsi
0x180007f58  lea     rcx, [rsi+rbx]; Destination
0x180007f5c  sub     rdx, rbx; DestinationSize
0x180007f5f  sub     r9, rbx; SourceSize
0x180007f62  mov     r8, rbx; Source
0x180007f65  call    cs:__imp_memmove_s
0x180007f6b  add     [rdi+20h], rsi
0x180007f6f  xor     ebx, ebx
0x180007f71  cmp     [rbp+47h+var_B0], bl
0x180007f74  jnz     short loc_180007F89
0x180007f76  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007f7a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007f7e  lea     rcx, [rbp+47h+var_98]; this
0x180007f82  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007f87  jmp     short loc_180007FD6
0x180007f89  mov     cl, [rbp+47h+var_96]
0x180007f8c  test    cl, cl
0x180007f8e  jz      short loc_180007FD6
0x180007f90  mov     eax, [rbp+47h+Source]
0x180007f93  lea     r8d, [rax+1]
0x180007f97  cmp     eax, r8d
0x180007f9a  jz      short loc_180007FD6
0x180007f9c  mov     [rbp+47h+Source], r8d
0x180007fa0  cmp     cl, 1
0x180007fa3  jnz     short loc_180007FB9
0x180007fa5  mov     r9d, 2
0x180007fab  mov     [rbp+47h+var_9C], r8w
0x180007fb0  mov     edx, r9d
0x180007fb3  lea     r8, [rbp+47h+var_9C]
0x180007fb7  jmp     short loc_180007FCC
0x180007fb9  cmp     cl, 2
0x180007fbc  jnz     short loc_180007FD6
0x180007fbe  mov     eax, 4
0x180007fc3  lea     r8, [rbp+47h+Source]; Source
0x180007fc7  mov     r9d, eax; SourceSize
0x180007fca  mov     edx, eax; DestinationSize
0x180007fcc  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007fd0  call    cs:__imp_memcpy_s
0x180007fd6  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007fda  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007fde  lea     rcx, [rbp+47h+var_78]; this
0x180007fe2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007fe7  mov     byte ptr [rdi+38h], 1
0x180007feb  jmp     loc_180007EBD
0x180007ff0  xor     al, al
0x180007ff2  mov     rcx, [rbp+47h+var_38]
0x180007ff6  xor     rcx, rsp; StackCookie
0x180007ff9  call    __security_check_cookie
0x180007ffe  mov     rbx, [rsp+0E0h+arg_8]
0x180008006  add     rsp, 0B0h
0x18000800d  pop     r15
0x18000800f  pop     r14
0x180008011  pop     r13
0x180008013  pop     r12
0x180008015  pop     rdi
0x180008016  pop     rsi
0x180008017  pop     rbp
0x180008018  retn
```
