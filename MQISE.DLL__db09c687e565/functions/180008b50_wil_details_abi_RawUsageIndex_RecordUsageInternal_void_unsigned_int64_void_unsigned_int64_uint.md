# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008b50`
- end: `0x180008ed0`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008998`

## callees

- `0x180005c70`
- `0x180008318`
- `0x180008b50`
- `0x18000af6c`
- `0x18000f5b6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180008e2f`
- `msvcrt!memmove_s` at `0x180008e2f`
- `msvcrt!memcpy_s` at `0x180008c5b`
- `msvcrt!memcpy_s` at `0x180008cf4`
- `msvcrt!memcpy_s` at `0x180008e9a`
- `msvcrt!memcpy_s` at `0x180008c5b`
- `msvcrt!memcpy_s` at `0x180008cf4`
- `msvcrt!memcpy_s` at `0x180008e9a`

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
0x180008b50  push    rbp
0x180008b52  push    rbx
0x180008b53  push    rsi
0x180008b54  push    rdi
0x180008b55  push    r12
0x180008b57  push    r13
0x180008b59  push    r14
0x180008b5b  push    r15
0x180008b5d  lea     rbp, [rsp-0Fh]
0x180008b62  sub     rsp, 0A8h
0x180008b69  mov     rbx, [rcx+18h]
0x180008b6d  mov     rdi, rcx
0x180008b70  xor     ecx, ecx
0x180008b72  mov     r13, r9
0x180008b75  mov     r14, r8
0x180008b78  mov     r15, rdx
0x180008b7b  test    rbx, rbx
0x180008b7e  jz      loc_180008EBA
0x180008b84  movzx   eax, word ptr [rdi+2]
0x180008b88  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008b8c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008b90  add     rbx, 0Ah
0x180008b94  mov     [rbp+47h+var_A0], ax
0x180008b98  xorps   xmm0, xmm0
0x180008b9b  mov     al, [rdi+4]
0x180008b9e  mov     [rbp+47h+Source], ecx
0x180008ba1  mov     [rbp+47h+var_98], cx
0x180008ba5  mov     byte ptr [rbp+47h+arg_0], cl
0x180008ba8  lea     rcx, [rbp+47h+var_A0]; this
0x180008bac  mov     [rbp+47h+var_9E], al
0x180008baf  mov     [rbp+47h+var_A8], rbx
0x180008bb3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180008bb8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008bbd  mov     r12, [rbp+47h+arg_20]
0x180008bc1  jmp     loc_180008D0F
0x180008bc6  movzx   eax, [rbp+47h+var_98]
0x180008bca  cmp     r14, rax
0x180008bcd  jnz     short loc_180008BE5
0x180008bcf  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180008bd3  mov     r8, r14; Size
0x180008bd6  mov     rcx, r15; Buf1
0x180008bd9  call    memcmp_0
0x180008bde  mov     ecx, eax
0x180008be0  xor     r9d, r9d
0x180008be3  jmp     short loc_180008BEE
0x180008be5  movzx   eax, [rbp+47h+var_98]
0x180008be9  mov     ecx, r14d
0x180008bec  sub     ecx, eax
0x180008bee  test    ecx, ecx
0x180008bf0  js      loc_180008D94
0x180008bf6  jz      loc_180008D59
0x180008bfc  mov     rbx, [rbp+47h+var_A8]
0x180008c00  mov     [rbp+47h+var_A8], rbx
0x180008c04  cmp     [rdi+10h], r9
0x180008c08  jbe     short loc_180008C73
0x180008c0a  mov     rax, [rdi+20h]
0x180008c0e  xor     edx, edx
0x180008c10  sub     rax, [rdi+18h]
0x180008c14  mov     rsi, rbx
0x180008c17  div     qword ptr [rdi+10h]
0x180008c1b  mov     edx, [rbp+47h+Source]
0x180008c1e  cmp     rdx, rax
0x180008c21  jbe     short loc_180008C64
0x180008c23  cmp     edx, eax
0x180008c25  jz      short loc_180008C64
0x180008c27  mov     edx, eax
0x180008c29  mov     [rbp+47h+Source], eax
0x180008c2c  mov     al, [rbp+47h+var_9E]
0x180008c2f  cmp     al, 1
0x180008c31  jnz     short loc_180008C46
0x180008c33  movzx   eax, dx
0x180008c36  mov     [rbp+47h+var_B0], dx
0x180008c3a  mov     r9d, 2
0x180008c40  lea     r8, [rbp+47h+var_B0]
0x180008c44  jmp     short loc_180008C54
0x180008c46  cmp     al, 2
0x180008c48  jnz     short loc_180008C64
0x180008c4a  mov     r9d, 4; SourceSize
0x180008c50  lea     r8, [rbp+47h+Source]; Source
0x180008c54  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008c58  mov     rdx, r9; DestinationSize
0x180008c5b  call    cs:__imp_memcpy_s
0x180008c61  mov     edx, [rbp+47h+Source]
0x180008c64  mov     ebx, edx
0x180008c66  imul    rbx, [rdi+10h]
0x180008c6b  add     rbx, rsi
0x180008c6e  jmp     loc_180008CFA
0x180008c73  movzx   eax, word ptr [rdi+6]
0x180008c77  xorps   xmm0, xmm0
0x180008c7a  mov     [rbp+47h+var_60], ax
0x180008c7e  mov     esi, r9d
0x180008c81  mov     al, [rdi+8]
0x180008c84  mov     [rbp+47h+var_5E], al
0x180008c87  mov     eax, [rbp+47h+Source]
0x180008c8a  mov     [rbp+47h+var_5C], r9d
0x180008c8e  mov     [rbp+47h+var_58], r9w
0x180008c93  movdqu  [rbp+47h+var_50], xmm0
0x180008c98  test    eax, eax
0x180008c9a  jz      short loc_180008CBE
0x180008c9c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008ca0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008ca4  lea     rcx, [rbp+47h+var_60]; this
0x180008ca8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008cad  test    al, al
0x180008caf  mov     eax, [rbp+47h+Source]
0x180008cb2  jz      short loc_180008CBA
0x180008cb4  inc     esi
0x180008cb6  cmp     esi, eax
0x180008cb8  jb      short loc_180008C9C
0x180008cba  mov     rbx, [rbp+47h+var_A8]
0x180008cbe  cmp     eax, esi
0x180008cc0  jz      short loc_180008CFA
0x180008cc2  mov     al, [rbp+47h+var_9E]
0x180008cc5  mov     [rbp+47h+Source], esi
0x180008cc8  cmp     al, 1
0x180008cca  jnz     short loc_180008CE0
0x180008ccc  mov     eax, 2
0x180008cd1  mov     [rbp+47h+var_B0], si
0x180008cd5  mov     r9d, eax
0x180008cd8  lea     r8, [rbp+47h+var_B0]
0x180008cdc  mov     edx, eax
0x180008cde  jmp     short loc_180008CF0
0x180008ce0  cmp     al, 2
0x180008ce2  jnz     short loc_180008CFA
0x180008ce4  mov     edx, 4; DestinationSize
0x180008ce9  lea     r8, [rbp+47h+Source]; Source
0x180008ced  mov     r9d, edx; SourceSize
0x180008cf0  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008cf4  call    cs:__imp_memcpy_s
0x180008cfa  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008cfe  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008d02  lea     rcx, [rbp+47h+var_A0]; this
0x180008d06  mov     [rbp+47h+var_A8], rbx
0x180008d0a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008d0f  xor     r9d, r9d
0x180008d12  mov     sil, al
0x180008d15  test    al, al
0x180008d17  jnz     loc_180008BC6
0x180008d1d  mov     rbx, [rbp+47h+var_A8]
0x180008d21  mov     [rdi+20h], rbx
0x180008d25  mov     rcx, r9
0x180008d28  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180008d2c  jnz     loc_180008DB7
0x180008d32  movzx   eax, [rbp+47h+var_A0]
0x180008d36  mov     [rbp+47h+Source], 1
0x180008d3d  mov     [rbp+47h+var_98], r14w
0x180008d42  mov     [rbp+47h+Buf2], r9
0x180008d46  mov     [rbp+47h+Buf2+8], r15
0x180008d4a  test    ax, ax
0x180008d4d  jnz     short loc_180008D9F
0x180008d4f  movzx   ecx, r14w
0x180008d53  add     rcx, 2
0x180008d57  jmp     short loc_180008DA2
0x180008d59  mov     eax, [rbp+47h+arg_28]
0x180008d5c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180008d60  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180008d64  mov     r9, r13; void *
0x180008d67  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180008d6b  mov     rcx, rdi; this
0x180008d6e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180008d73  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180008d78  xor     r9d, r9d
0x180008d7b  mov     [rbp+47h+var_A8], rax
0x180008d7f  mov     rbx, rax
0x180008d82  test    rax, rax
0x180008d85  jnz     short loc_180008D8E
0x180008d87  mov     al, 1
0x180008d89  jmp     loc_180008EBC
0x180008d8e  mov     byte ptr [rbp+47h+arg_0], 1
0x180008d92  jmp     short loc_180008D98
0x180008d94  mov     [rbp+47h+var_A8], rbx
0x180008d98  test    sil, sil
0x180008d9b  jnz     short loc_180008D25
0x180008d9d  jmp     short loc_180008D21
0x180008d9f  mov     rcx, rax
0x180008da2  mov     al, [rbp+47h+var_9E]
0x180008da5  cmp     al, 1
0x180008da7  jnz     short loc_180008DAF
0x180008da9  add     rcx, 2
0x180008dad  jmp     short loc_180008DB7
0x180008daf  cmp     al, 2
0x180008db1  jnz     short loc_180008DB7
0x180008db3  add     rcx, 4
0x180008db7  movzx   eax, word ptr [rdi+6]
0x180008dbb  mov     dl, [rdi+8]
0x180008dbe  mov     r8d, [rbp+47h+arg_28]
0x180008dc2  mov     [rbp+47h+var_80], ax
0x180008dc6  mov     [rbp+47h+var_7E], dl
0x180008dc9  mov     [rbp+47h+var_7C], r8d
0x180008dcd  mov     [rbp+47h+var_78], r12w
0x180008dd2  mov     [rbp+47h+var_70], r9
0x180008dd6  mov     [rbp+47h+var_68], r13
0x180008dda  test    ax, ax
0x180008ddd  jnz     short loc_180008DE7
0x180008ddf  movzx   eax, r12w
0x180008de3  add     rax, 2
0x180008de7  cmp     dl, 1
0x180008dea  jnz     short loc_180008DF2
0x180008dec  add     rax, 2
0x180008df0  jmp     short loc_180008DFB
0x180008df2  cmp     dl, 2
0x180008df5  jnz     short loc_180008DFB
0x180008df7  add     rax, 4
0x180008dfb  mov     rdx, [rdi+28h]
0x180008dff  lea     rsi, [rax+rcx]
0x180008e03  mov     r9, [rdi+20h]
0x180008e07  mov     rcx, rdx
0x180008e0a  sub     rcx, r9
0x180008e0d  cmp     r9, rdx
0x180008e10  sbb     rax, rax
0x180008e13  and     rax, rcx
0x180008e16  cmp     rax, rsi
0x180008e19  jb      loc_180008EBA
0x180008e1f  sub     rdx, rsi
0x180008e22  lea     rcx, [rsi+rbx]; Destination
0x180008e26  sub     rdx, rbx; DestinationSize
0x180008e29  sub     r9, rbx; SourceSize
0x180008e2c  mov     r8, rbx; Source
0x180008e2f  call    cs:__imp_memmove_s
0x180008e35  add     [rdi+20h], rsi
0x180008e39  xor     ebx, ebx
0x180008e3b  cmp     byte ptr [rbp+47h+arg_0], bl
0x180008e3e  jnz     short loc_180008E53
0x180008e40  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008e44  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008e48  lea     rcx, [rbp+47h+var_A0]; this
0x180008e4c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008e51  jmp     short loc_180008EA0
0x180008e53  mov     cl, [rbp+47h+var_9E]
0x180008e56  test    cl, cl
0x180008e58  jz      short loc_180008EA0
0x180008e5a  mov     eax, [rbp+47h+Source]
0x180008e5d  lea     r8d, [rax+1]
0x180008e61  cmp     eax, r8d
0x180008e64  jz      short loc_180008EA0
0x180008e66  mov     [rbp+47h+Source], r8d
0x180008e6a  cmp     cl, 1
0x180008e6d  jnz     short loc_180008E83
0x180008e6f  mov     r9d, 2
0x180008e75  mov     [rbp+47h+arg_0], r8w
0x180008e7a  mov     edx, r9d
0x180008e7d  lea     r8, [rbp+47h+arg_0]
0x180008e81  jmp     short loc_180008E96
0x180008e83  cmp     cl, 2
0x180008e86  jnz     short loc_180008EA0
0x180008e88  mov     eax, 4
0x180008e8d  lea     r8, [rbp+47h+Source]; Source
0x180008e91  mov     r9d, eax; SourceSize
0x180008e94  mov     edx, eax; DestinationSize
0x180008e96  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008e9a  call    cs:__imp_memcpy_s
0x180008ea0  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008ea4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008ea8  lea     rcx, [rbp+47h+var_80]; this
0x180008eac  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008eb1  mov     byte ptr [rdi+38h], 1
0x180008eb5  jmp     loc_180008D87
0x180008eba  xor     al, al
0x180008ebc  add     rsp, 0A8h
0x180008ec3  pop     r15
0x180008ec5  pop     r14
0x180008ec7  pop     r13
0x180008ec9  pop     r12
0x180008ecb  pop     rdi
0x180008ecc  pop     rsi
0x180008ecd  pop     rbx
0x180008ece  pop     rbp
0x180008ecf  retn
```
