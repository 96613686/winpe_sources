# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007b94`
- end: `0x180007f29`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `917`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800079c8`

## callees

- `0x180004cc0`
- `0x1800072cc`
- `0x180007b94`
- `0x18000a924`
- `0x18000c5d6`
- `0x18000c610`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007e75`
- `msvcrt!memmove_s` at `0x180007e75`
- `msvcrt!memcpy_s` at `0x180007ca1`
- `msvcrt!memcpy_s` at `0x180007d3a`
- `msvcrt!memcpy_s` at `0x180007ee0`
- `msvcrt!memcpy_s` at `0x180007ca1`
- `msvcrt!memcpy_s` at `0x180007d3a`
- `msvcrt!memcpy_s` at `0x180007ee0`

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
0x180007b94  mov     [rsp-8+arg_8], rbx
0x180007b99  push    rbp
0x180007b9a  push    rsi
0x180007b9b  push    rdi
0x180007b9c  push    r12
0x180007b9e  push    r13
0x180007ba0  push    r14
0x180007ba2  push    r15
0x180007ba4  lea     rbp, [rsp-17h]
0x180007ba9  sub     rsp, 0B0h
0x180007bb0  mov     rax, cs:__security_cookie
0x180007bb7  xor     rax, rsp
0x180007bba  mov     [rbp+47h+var_38], rax
0x180007bbe  mov     rbx, [rcx+18h]
0x180007bc2  mov     rdi, rcx
0x180007bc5  mov     eax, [rbp+47h+arg_28]
0x180007bc8  xor     ecx, ecx
0x180007bca  mov     r15, [rbp+47h+arg_20]
0x180007bce  mov     r13, r9
0x180007bd1  mov     [rbp+47h+var_A0], eax
0x180007bd4  mov     r14, r8
0x180007bd7  mov     r12, rdx
0x180007bda  test    rbx, rbx
0x180007bdd  jz      loc_180007F00
0x180007be3  movzx   eax, word ptr [rdi+2]
0x180007be7  xorps   xmm0, xmm0
0x180007bea  mov     [rbp+47h+var_98], ax
0x180007bee  add     rbx, 0Ah
0x180007bf2  mov     al, [rdi+4]
0x180007bf5  mov     [rbp+47h+var_96], al
0x180007bf8  mov     [rbp+47h+Source], ecx
0x180007bfb  mov     [rbp+47h+var_90], cx
0x180007bff  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180007c04  mov     [rbp+47h+var_B0], cl
0x180007c07  jmp     loc_180007D40
0x180007c0c  movzx   ecx, [rbp+47h+var_90]
0x180007c10  cmp     r14, rcx
0x180007c13  jnz     short loc_180007C2B
0x180007c15  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180007c19  mov     r8, r14; Size
0x180007c1c  mov     rcx, r12; Buf1
0x180007c1f  call    memcmp_0
0x180007c24  mov     ecx, eax
0x180007c26  xor     r9d, r9d
0x180007c29  jmp     short loc_180007C34
0x180007c2b  movzx   eax, [rbp+47h+var_90]
0x180007c2f  mov     ecx, r14d
0x180007c32  sub     ecx, eax
0x180007c34  test    ecx, ecx
0x180007c36  js      loc_180007DDA
0x180007c3c  jz      loc_180007D9F
0x180007c42  mov     rbx, [rbp+47h+var_A8]
0x180007c46  mov     [rbp+47h+var_A8], rbx
0x180007c4a  cmp     [rdi+10h], r9
0x180007c4e  jbe     short loc_180007CB9
0x180007c50  mov     rax, [rdi+20h]
0x180007c54  xor     edx, edx
0x180007c56  sub     rax, [rdi+18h]
0x180007c5a  mov     rsi, rbx
0x180007c5d  div     qword ptr [rdi+10h]
0x180007c61  mov     edx, [rbp+47h+Source]
0x180007c64  cmp     rdx, rax
0x180007c67  jbe     short loc_180007CAA
0x180007c69  cmp     edx, eax
0x180007c6b  jz      short loc_180007CAA
0x180007c6d  mov     edx, eax
0x180007c6f  mov     [rbp+47h+Source], eax
0x180007c72  mov     al, [rbp+47h+var_96]
0x180007c75  cmp     al, 1
0x180007c77  jnz     short loc_180007C8C
0x180007c79  movzx   eax, dx
0x180007c7c  mov     [rbp+47h+var_9C], dx
0x180007c80  mov     r9d, 2
0x180007c86  lea     r8, [rbp+47h+var_9C]
0x180007c8a  jmp     short loc_180007C9A
0x180007c8c  cmp     al, 2
0x180007c8e  jnz     short loc_180007CAA
0x180007c90  mov     r9d, 4; SourceSize
0x180007c96  lea     r8, [rbp+47h+Source]; Source
0x180007c9a  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007c9e  mov     rdx, r9; DestinationSize
0x180007ca1  call    cs:__imp_memcpy_s
0x180007ca7  mov     edx, [rbp+47h+Source]
0x180007caa  mov     ebx, edx
0x180007cac  imul    rbx, [rdi+10h]
0x180007cb1  add     rbx, rsi
0x180007cb4  jmp     loc_180007D40
0x180007cb9  movzx   eax, word ptr [rdi+6]
0x180007cbd  xorps   xmm0, xmm0
0x180007cc0  mov     [rbp+47h+var_58], ax
0x180007cc4  mov     esi, r9d
0x180007cc7  mov     al, [rdi+8]
0x180007cca  mov     [rbp+47h+var_56], al
0x180007ccd  mov     eax, [rbp+47h+Source]
0x180007cd0  mov     [rbp+47h+var_54], r9d
0x180007cd4  mov     [rbp+47h+var_50], r9w
0x180007cd9  movdqu  [rbp+47h+var_48], xmm0
0x180007cde  test    eax, eax
0x180007ce0  jz      short loc_180007D04
0x180007ce2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007ce6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007cea  lea     rcx, [rbp+47h+var_58]; this
0x180007cee  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007cf3  test    al, al
0x180007cf5  mov     eax, [rbp+47h+Source]
0x180007cf8  jz      short loc_180007D00
0x180007cfa  inc     esi
0x180007cfc  cmp     esi, eax
0x180007cfe  jb      short loc_180007CE2
0x180007d00  mov     rbx, [rbp+47h+var_A8]
0x180007d04  cmp     eax, esi
0x180007d06  jz      short loc_180007D40
0x180007d08  mov     al, [rbp+47h+var_96]
0x180007d0b  mov     [rbp+47h+Source], esi
0x180007d0e  cmp     al, 1
0x180007d10  jnz     short loc_180007D26
0x180007d12  mov     eax, 2
0x180007d17  mov     [rbp+47h+var_9C], si
0x180007d1b  mov     r9d, eax
0x180007d1e  lea     r8, [rbp+47h+var_9C]
0x180007d22  mov     edx, eax
0x180007d24  jmp     short loc_180007D36
0x180007d26  cmp     al, 2
0x180007d28  jnz     short loc_180007D40
0x180007d2a  mov     edx, 4; DestinationSize
0x180007d2f  lea     r8, [rbp+47h+Source]; Source
0x180007d33  mov     r9d, edx; SourceSize
0x180007d36  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007d3a  call    cs:__imp_memcpy_s
0x180007d40  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007d44  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007d48  lea     rcx, [rbp+47h+var_98]; this
0x180007d4c  mov     [rbp+47h+var_A8], rbx
0x180007d50  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007d55  xor     r9d, r9d
0x180007d58  mov     sil, al
0x180007d5b  test    al, al
0x180007d5d  jnz     loc_180007C0C
0x180007d63  mov     rbx, [rbp+47h+var_A8]
0x180007d67  mov     [rdi+20h], rbx
0x180007d6b  mov     rcx, r9
0x180007d6e  cmp     [rbp+47h+var_B0], r9b
0x180007d72  jnz     loc_180007DFD
0x180007d78  movzx   eax, [rbp+47h+var_98]
0x180007d7c  mov     [rbp+47h+Source], 1
0x180007d83  mov     [rbp+47h+var_90], r14w
0x180007d88  mov     [rbp+47h+Buf2], r9
0x180007d8c  mov     [rbp+47h+Buf2+8], r12
0x180007d90  test    ax, ax
0x180007d93  jnz     short loc_180007DE5
0x180007d95  movzx   ecx, r14w
0x180007d99  add     rcx, 2
0x180007d9d  jmp     short loc_180007DE8
0x180007d9f  mov     eax, [rbp+47h+var_A0]
0x180007da2  lea     rdx, [rbp+47h+var_98]; struct wil::details_abi::UsageIndexProperty *
0x180007da6  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180007daa  mov     r9, r13; void *
0x180007dad  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180007db1  mov     rcx, rdi; this
0x180007db4  mov     [rsp+0E0h+var_C0], r15; unsigned __int64
0x180007db9  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180007dbe  xor     r9d, r9d
0x180007dc1  mov     [rbp+47h+var_A8], rax
0x180007dc5  mov     rbx, rax
0x180007dc8  test    rax, rax
0x180007dcb  jnz     short loc_180007DD4
0x180007dcd  mov     al, 1
0x180007dcf  jmp     loc_180007F02
0x180007dd4  mov     [rbp+47h+var_B0], 1
0x180007dd8  jmp     short loc_180007DDE
0x180007dda  mov     [rbp+47h+var_A8], rbx
0x180007dde  test    sil, sil
0x180007de1  jnz     short loc_180007D6B
0x180007de3  jmp     short loc_180007D67
0x180007de5  mov     rcx, rax
0x180007de8  mov     al, [rbp+47h+var_96]
0x180007deb  cmp     al, 1
0x180007ded  jnz     short loc_180007DF5
0x180007def  add     rcx, 2
0x180007df3  jmp     short loc_180007DFD
0x180007df5  cmp     al, 2
0x180007df7  jnz     short loc_180007DFD
0x180007df9  add     rcx, 4
0x180007dfd  movzx   eax, word ptr [rdi+6]
0x180007e01  mov     dl, [rdi+8]
0x180007e04  mov     r8d, [rbp+47h+var_A0]
0x180007e08  mov     [rbp+47h+var_78], ax
0x180007e0c  mov     [rbp+47h+var_76], dl
0x180007e0f  mov     [rbp+47h+var_74], r8d
0x180007e13  mov     [rbp+47h+var_70], r15w
0x180007e18  mov     [rbp+47h+var_68], r9
0x180007e1c  mov     [rbp+47h+var_60], r13
0x180007e20  test    ax, ax
0x180007e23  jnz     short loc_180007E2D
0x180007e25  movzx   eax, r15w
0x180007e29  add     rax, 2
0x180007e2d  cmp     dl, 1
0x180007e30  jnz     short loc_180007E38
0x180007e32  add     rax, 2
0x180007e36  jmp     short loc_180007E41
0x180007e38  cmp     dl, 2
0x180007e3b  jnz     short loc_180007E41
0x180007e3d  add     rax, 4
0x180007e41  mov     rdx, [rdi+28h]
0x180007e45  lea     rsi, [rax+rcx]
0x180007e49  mov     r9, [rdi+20h]
0x180007e4d  mov     rcx, rdx
0x180007e50  sub     rcx, r9
0x180007e53  cmp     r9, rdx
0x180007e56  sbb     rax, rax
0x180007e59  and     rax, rcx
0x180007e5c  cmp     rax, rsi
0x180007e5f  jb      loc_180007F00
0x180007e65  sub     rdx, rsi
0x180007e68  lea     rcx, [rsi+rbx]; Destination
0x180007e6c  sub     rdx, rbx; DestinationSize
0x180007e6f  sub     r9, rbx; SourceSize
0x180007e72  mov     r8, rbx; Source
0x180007e75  call    cs:__imp_memmove_s
0x180007e7b  add     [rdi+20h], rsi
0x180007e7f  xor     ebx, ebx
0x180007e81  cmp     [rbp+47h+var_B0], bl
0x180007e84  jnz     short loc_180007E99
0x180007e86  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007e8a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007e8e  lea     rcx, [rbp+47h+var_98]; this
0x180007e92  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007e97  jmp     short loc_180007EE6
0x180007e99  mov     cl, [rbp+47h+var_96]
0x180007e9c  test    cl, cl
0x180007e9e  jz      short loc_180007EE6
0x180007ea0  mov     eax, [rbp+47h+Source]
0x180007ea3  lea     r8d, [rax+1]
0x180007ea7  cmp     eax, r8d
0x180007eaa  jz      short loc_180007EE6
0x180007eac  mov     [rbp+47h+Source], r8d
0x180007eb0  cmp     cl, 1
0x180007eb3  jnz     short loc_180007EC9
0x180007eb5  mov     r9d, 2
0x180007ebb  mov     [rbp+47h+var_9C], r8w
0x180007ec0  mov     edx, r9d
0x180007ec3  lea     r8, [rbp+47h+var_9C]
0x180007ec7  jmp     short loc_180007EDC
0x180007ec9  cmp     cl, 2
0x180007ecc  jnz     short loc_180007EE6
0x180007ece  mov     eax, 4
0x180007ed3  lea     r8, [rbp+47h+Source]; Source
0x180007ed7  mov     r9d, eax; SourceSize
0x180007eda  mov     edx, eax; DestinationSize
0x180007edc  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007ee0  call    cs:__imp_memcpy_s
0x180007ee6  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007eea  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007eee  lea     rcx, [rbp+47h+var_78]; this
0x180007ef2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007ef7  mov     byte ptr [rdi+38h], 1
0x180007efb  jmp     loc_180007DCD
0x180007f00  xor     al, al
0x180007f02  mov     rcx, [rbp+47h+var_38]
0x180007f06  xor     rcx, rsp; StackCookie
0x180007f09  call    __security_check_cookie
0x180007f0e  mov     rbx, [rsp+0E0h+arg_8]
0x180007f16  add     rsp, 0B0h
0x180007f1d  pop     r15
0x180007f1f  pop     r14
0x180007f21  pop     r13
0x180007f23  pop     r12
0x180007f25  pop     rdi
0x180007f26  pop     rsi
0x180007f27  pop     rbp
0x180007f28  retn
```
