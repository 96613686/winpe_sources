# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180014c04`
- end: `0x180014f81`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `893`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180014a54`

## callees

- `0x180001f4c`
- `0x180012e3c`
- `0x1800145a8`
- `0x180014c04`
- `0x1800164dc`
- `0x18001a6a0`

## import_xrefs

- `ntdll!memmove_s` at `0x180014ee1`
- `ntdll!memmove_s` at `0x180014ee1`

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
0x180014c04  push    rbp
0x180014c06  push    rbx
0x180014c07  push    rsi
0x180014c08  push    rdi
0x180014c09  push    r12
0x180014c0b  push    r13
0x180014c0d  push    r14
0x180014c0f  push    r15
0x180014c11  lea     rbp, [rsp-0Fh]
0x180014c16  sub     rsp, 0A8h
0x180014c1d  mov     rbx, [rcx+18h]
0x180014c21  mov     rdi, rcx
0x180014c24  xor     ecx, ecx
0x180014c26  mov     r13, r9
0x180014c29  mov     r14, r8
0x180014c2c  mov     r15, rdx
0x180014c2f  test    rbx, rbx
0x180014c32  jz      loc_180014F6B
0x180014c38  movzx   eax, word ptr [rdi+2]
0x180014c3c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014c40  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014c44  add     rbx, 0Ah
0x180014c48  mov     [rbp+47h+var_A0], ax
0x180014c4c  xorps   xmm0, xmm0
0x180014c4f  mov     al, [rdi+4]
0x180014c52  mov     [rbp+47h+Source], ecx
0x180014c55  mov     [rbp+47h+var_98], cx
0x180014c59  mov     byte ptr [rbp+47h+arg_0], cl
0x180014c5c  lea     rcx, [rbp+47h+var_A0]; this
0x180014c60  mov     [rbp+47h+var_9E], al
0x180014c63  mov     [rbp+47h+var_A8], rbx
0x180014c67  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180014c6c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014c71  mov     r12, [rbp+47h+arg_20]
0x180014c75  jmp     loc_180014DC1
0x180014c7a  movzx   eax, [rbp+47h+var_98]
0x180014c7e  cmp     r14, rax
0x180014c81  jnz     short loc_180014C99
0x180014c83  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180014c87  mov     r8, r14; Size
0x180014c8a  mov     rcx, r15; Buf1
0x180014c8d  call    memcmp_0
0x180014c92  mov     ecx, eax
0x180014c94  xor     r9d, r9d
0x180014c97  jmp     short loc_180014CA2
0x180014c99  movzx   eax, [rbp+47h+var_98]
0x180014c9d  mov     ecx, r14d
0x180014ca0  sub     ecx, eax
0x180014ca2  test    ecx, ecx
0x180014ca4  js      loc_180014E46
0x180014caa  jz      loc_180014E0B
0x180014cb0  mov     rbx, [rbp+47h+var_A8]
0x180014cb4  mov     [rbp+47h+var_A8], rbx
0x180014cb8  cmp     [rdi+10h], r9
0x180014cbc  jbe     short loc_180014D26
0x180014cbe  mov     rax, [rdi+20h]
0x180014cc2  xor     edx, edx
0x180014cc4  sub     rax, [rdi+18h]
0x180014cc8  mov     rsi, rbx
0x180014ccb  div     qword ptr [rdi+10h]
0x180014ccf  mov     edx, [rbp+47h+Source]
0x180014cd2  cmp     rdx, rax
0x180014cd5  jbe     short loc_180014D17
0x180014cd7  cmp     edx, eax
0x180014cd9  jz      short loc_180014D17
0x180014cdb  mov     edx, eax
0x180014cdd  mov     [rbp+47h+Source], eax
0x180014ce0  mov     al, [rbp+47h+var_9E]
0x180014ce3  cmp     al, 1
0x180014ce5  jnz     short loc_180014CFA
0x180014ce7  movzx   eax, dx
0x180014cea  mov     [rbp+47h+var_B0], dx
0x180014cee  mov     r9d, 2
0x180014cf4  lea     r8, [rbp+47h+var_B0]
0x180014cf8  jmp     short loc_180014D08
0x180014cfa  cmp     al, 2
0x180014cfc  jnz     short loc_180014D17
0x180014cfe  mov     r9d, 4; SourceSize
0x180014d04  lea     r8, [rbp+47h+Source]; Source
0x180014d08  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014d0c  mov     rdx, r9; DestinationSize
0x180014d0f  call    memcpy_s
0x180014d14  mov     edx, [rbp+47h+Source]
0x180014d17  mov     ebx, edx
0x180014d19  imul    rbx, [rdi+10h]
0x180014d1e  add     rbx, rsi
0x180014d21  jmp     loc_180014DAC
0x180014d26  movzx   eax, word ptr [rdi+6]
0x180014d2a  xorps   xmm0, xmm0
0x180014d2d  mov     [rbp+47h+var_60], ax
0x180014d31  mov     esi, r9d
0x180014d34  mov     al, [rdi+8]
0x180014d37  mov     [rbp+47h+var_5E], al
0x180014d3a  mov     eax, [rbp+47h+Source]
0x180014d3d  mov     [rbp+47h+var_5C], r9d
0x180014d41  mov     [rbp+47h+var_58], r9w
0x180014d46  movdqu  [rbp+47h+var_50], xmm0
0x180014d4b  test    eax, eax
0x180014d4d  jz      short loc_180014D71
0x180014d4f  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014d53  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014d57  lea     rcx, [rbp+47h+var_60]; this
0x180014d5b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014d60  test    al, al
0x180014d62  mov     eax, [rbp+47h+Source]
0x180014d65  jz      short loc_180014D6D
0x180014d67  inc     esi
0x180014d69  cmp     esi, eax
0x180014d6b  jb      short loc_180014D4F
0x180014d6d  mov     rbx, [rbp+47h+var_A8]
0x180014d71  cmp     eax, esi
0x180014d73  jz      short loc_180014DAC
0x180014d75  mov     al, [rbp+47h+var_9E]
0x180014d78  mov     [rbp+47h+Source], esi
0x180014d7b  cmp     al, 1
0x180014d7d  jnz     short loc_180014D93
0x180014d7f  mov     eax, 2
0x180014d84  mov     [rbp+47h+var_B0], si
0x180014d88  mov     r9d, eax
0x180014d8b  lea     r8, [rbp+47h+var_B0]
0x180014d8f  mov     edx, eax
0x180014d91  jmp     short loc_180014DA3
0x180014d93  cmp     al, 2
0x180014d95  jnz     short loc_180014DAC
0x180014d97  mov     edx, 4; DestinationSize
0x180014d9c  lea     r8, [rbp+47h+Source]; Source
0x180014da0  mov     r9d, edx; SourceSize
0x180014da3  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014da7  call    memcpy_s
0x180014dac  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014db0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014db4  lea     rcx, [rbp+47h+var_A0]; this
0x180014db8  mov     [rbp+47h+var_A8], rbx
0x180014dbc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014dc1  xor     r9d, r9d
0x180014dc4  mov     sil, al
0x180014dc7  test    al, al
0x180014dc9  jnz     loc_180014C7A
0x180014dcf  mov     rbx, [rbp+47h+var_A8]
0x180014dd3  mov     [rdi+20h], rbx
0x180014dd7  mov     rcx, r9
0x180014dda  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180014dde  jnz     loc_180014E69
0x180014de4  movzx   eax, [rbp+47h+var_A0]
0x180014de8  mov     [rbp+47h+Source], 1
0x180014def  mov     [rbp+47h+var_98], r14w
0x180014df4  mov     [rbp+47h+Buf2], r9
0x180014df8  mov     [rbp+47h+Buf2+8], r15
0x180014dfc  test    ax, ax
0x180014dff  jnz     short loc_180014E51
0x180014e01  movzx   ecx, r14w
0x180014e05  add     rcx, 2
0x180014e09  jmp     short loc_180014E54
0x180014e0b  mov     eax, [rbp+47h+arg_28]
0x180014e0e  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180014e12  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180014e16  mov     r9, r13; void *
0x180014e19  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180014e1d  mov     rcx, rdi; this
0x180014e20  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180014e25  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180014e2a  xor     r9d, r9d
0x180014e2d  mov     [rbp+47h+var_A8], rax
0x180014e31  mov     rbx, rax
0x180014e34  test    rax, rax
0x180014e37  jnz     short loc_180014E40
0x180014e39  mov     al, 1
0x180014e3b  jmp     loc_180014F6D
0x180014e40  mov     byte ptr [rbp+47h+arg_0], 1
0x180014e44  jmp     short loc_180014E4A
0x180014e46  mov     [rbp+47h+var_A8], rbx
0x180014e4a  test    sil, sil
0x180014e4d  jnz     short loc_180014DD7
0x180014e4f  jmp     short loc_180014DD3
0x180014e51  mov     rcx, rax
0x180014e54  mov     al, [rbp+47h+var_9E]
0x180014e57  cmp     al, 1
0x180014e59  jnz     short loc_180014E61
0x180014e5b  add     rcx, 2
0x180014e5f  jmp     short loc_180014E69
0x180014e61  cmp     al, 2
0x180014e63  jnz     short loc_180014E69
0x180014e65  add     rcx, 4
0x180014e69  movzx   eax, word ptr [rdi+6]
0x180014e6d  mov     dl, [rdi+8]
0x180014e70  mov     r8d, [rbp+47h+arg_28]
0x180014e74  mov     [rbp+47h+var_80], ax
0x180014e78  mov     [rbp+47h+var_7E], dl
0x180014e7b  mov     [rbp+47h+var_7C], r8d
0x180014e7f  mov     [rbp+47h+var_78], r12w
0x180014e84  mov     [rbp+47h+var_70], r9
0x180014e88  mov     [rbp+47h+var_68], r13
0x180014e8c  test    ax, ax
0x180014e8f  jnz     short loc_180014E99
0x180014e91  movzx   eax, r12w
0x180014e95  add     rax, 2
0x180014e99  cmp     dl, 1
0x180014e9c  jnz     short loc_180014EA4
0x180014e9e  add     rax, 2
0x180014ea2  jmp     short loc_180014EAD
0x180014ea4  cmp     dl, 2
0x180014ea7  jnz     short loc_180014EAD
0x180014ea9  add     rax, 4
0x180014ead  mov     rdx, [rdi+28h]
0x180014eb1  lea     rsi, [rax+rcx]
0x180014eb5  mov     r9, [rdi+20h]
0x180014eb9  mov     rcx, rdx
0x180014ebc  sub     rcx, r9
0x180014ebf  cmp     r9, rdx
0x180014ec2  sbb     rax, rax
0x180014ec5  and     rax, rcx
0x180014ec8  cmp     rax, rsi
0x180014ecb  jb      loc_180014F6B
0x180014ed1  sub     rdx, rsi
0x180014ed4  lea     rcx, [rsi+rbx]; Destination
0x180014ed8  sub     rdx, rbx; DestinationSize
0x180014edb  sub     r9, rbx; SourceSize
0x180014ede  mov     r8, rbx; Source
0x180014ee1  call    cs:__imp_memmove_s
0x180014ee7  add     [rdi+20h], rsi
0x180014eeb  xor     ebx, ebx
0x180014eed  cmp     byte ptr [rbp+47h+arg_0], bl
0x180014ef0  jnz     short loc_180014F05
0x180014ef2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014ef6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014efa  lea     rcx, [rbp+47h+var_A0]; this
0x180014efe  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014f03  jmp     short loc_180014F51
0x180014f05  mov     cl, [rbp+47h+var_9E]
0x180014f08  test    cl, cl
0x180014f0a  jz      short loc_180014F51
0x180014f0c  mov     eax, [rbp+47h+Source]
0x180014f0f  lea     r8d, [rax+1]
0x180014f13  cmp     eax, r8d
0x180014f16  jz      short loc_180014F51
0x180014f18  mov     [rbp+47h+Source], r8d
0x180014f1c  cmp     cl, 1
0x180014f1f  jnz     short loc_180014F35
0x180014f21  mov     r9d, 2
0x180014f27  mov     [rbp+47h+arg_0], r8w
0x180014f2c  mov     edx, r9d
0x180014f2f  lea     r8, [rbp+47h+arg_0]
0x180014f33  jmp     short loc_180014F48
0x180014f35  cmp     cl, 2
0x180014f38  jnz     short loc_180014F51
0x180014f3a  mov     eax, 4
0x180014f3f  lea     r8, [rbp+47h+Source]; Source
0x180014f43  mov     r9d, eax; SourceSize
0x180014f46  mov     edx, eax; DestinationSize
0x180014f48  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014f4c  call    memcpy_s
0x180014f51  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014f55  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180014f59  lea     rcx, [rbp+47h+var_80]; this
0x180014f5d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014f62  mov     byte ptr [rdi+38h], 1
0x180014f66  jmp     loc_180014E39
0x180014f6b  xor     al, al
0x180014f6d  add     rsp, 0A8h
0x180014f74  pop     r15
0x180014f76  pop     r14
0x180014f78  pop     r13
0x180014f7a  pop     r12
0x180014f7c  pop     rdi
0x180014f7d  pop     rsi
0x180014f7e  pop     rbx
0x180014f7f  pop     rbp
0x180014f80  retn
```
