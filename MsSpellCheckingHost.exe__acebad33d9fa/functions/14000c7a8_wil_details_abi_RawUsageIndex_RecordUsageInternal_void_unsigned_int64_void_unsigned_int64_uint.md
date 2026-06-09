# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000c7a8`
- end: `0x14000cb28`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c5f8`

## callees

- `0x140009f90`
- `0x14000bf78`
- `0x14000c7a8`
- `0x14000e86c`
- `0x140011de6`

## import_xrefs

- `msvcrt!memmove_s` at `0x14000ca87`
- `msvcrt!memmove_s` at `0x14000ca87`
- `msvcrt!memcpy_s` at `0x14000c8b3`
- `msvcrt!memcpy_s` at `0x14000c94c`
- `msvcrt!memcpy_s` at `0x14000caf2`
- `msvcrt!memcpy_s` at `0x14000c8b3`
- `msvcrt!memcpy_s` at `0x14000c94c`
- `msvcrt!memcpy_s` at `0x14000caf2`

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
0x14000c7a8  push    rbp
0x14000c7aa  push    rbx
0x14000c7ab  push    rsi
0x14000c7ac  push    rdi
0x14000c7ad  push    r12
0x14000c7af  push    r13
0x14000c7b1  push    r14
0x14000c7b3  push    r15
0x14000c7b5  lea     rbp, [rsp-0Fh]
0x14000c7ba  sub     rsp, 0A8h
0x14000c7c1  mov     rbx, [rcx+18h]
0x14000c7c5  mov     rdi, rcx
0x14000c7c8  xor     ecx, ecx
0x14000c7ca  mov     r13, r9
0x14000c7cd  mov     r14, r8
0x14000c7d0  mov     r15, rdx
0x14000c7d3  test    rbx, rbx
0x14000c7d6  jz      loc_14000CB12
0x14000c7dc  movzx   eax, word ptr [rdi+2]
0x14000c7e0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000c7e4  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000c7e8  add     rbx, 0Ah
0x14000c7ec  mov     [rbp+47h+var_A0], ax
0x14000c7f0  xorps   xmm0, xmm0
0x14000c7f3  mov     al, [rdi+4]
0x14000c7f6  mov     [rbp+47h+Source], ecx
0x14000c7f9  mov     [rbp+47h+var_98], cx
0x14000c7fd  mov     byte ptr [rbp+47h+arg_0], cl
0x14000c800  lea     rcx, [rbp+47h+var_A0]; this
0x14000c804  mov     [rbp+47h+var_9E], al
0x14000c807  mov     [rbp+47h+var_A8], rbx
0x14000c80b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14000c810  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000c815  mov     r12, [rbp+47h+arg_20]
0x14000c819  jmp     loc_14000C967
0x14000c81e  movzx   eax, [rbp+47h+var_98]
0x14000c822  cmp     r14, rax
0x14000c825  jnz     short loc_14000C83D
0x14000c827  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14000c82b  mov     r8, r14; Size
0x14000c82e  mov     rcx, r15; Buf1
0x14000c831  call    memcmp_0
0x14000c836  mov     ecx, eax
0x14000c838  xor     r9d, r9d
0x14000c83b  jmp     short loc_14000C846
0x14000c83d  movzx   eax, [rbp+47h+var_98]
0x14000c841  mov     ecx, r14d
0x14000c844  sub     ecx, eax
0x14000c846  test    ecx, ecx
0x14000c848  js      loc_14000C9EC
0x14000c84e  jz      loc_14000C9B1
0x14000c854  mov     rbx, [rbp+47h+var_A8]
0x14000c858  mov     [rbp+47h+var_A8], rbx
0x14000c85c  cmp     [rdi+10h], r9
0x14000c860  jbe     short loc_14000C8CB
0x14000c862  mov     rax, [rdi+20h]
0x14000c866  xor     edx, edx
0x14000c868  sub     rax, [rdi+18h]
0x14000c86c  mov     rsi, rbx
0x14000c86f  div     qword ptr [rdi+10h]
0x14000c873  mov     edx, [rbp+47h+Source]
0x14000c876  cmp     rdx, rax
0x14000c879  jbe     short loc_14000C8BC
0x14000c87b  cmp     edx, eax
0x14000c87d  jz      short loc_14000C8BC
0x14000c87f  mov     edx, eax
0x14000c881  mov     [rbp+47h+Source], eax
0x14000c884  mov     al, [rbp+47h+var_9E]
0x14000c887  cmp     al, 1
0x14000c889  jnz     short loc_14000C89E
0x14000c88b  movzx   eax, dx
0x14000c88e  mov     [rbp+47h+var_B0], dx
0x14000c892  mov     r9d, 2
0x14000c898  lea     r8, [rbp+47h+var_B0]
0x14000c89c  jmp     short loc_14000C8AC
0x14000c89e  cmp     al, 2
0x14000c8a0  jnz     short loc_14000C8BC
0x14000c8a2  mov     r9d, 4; SourceSize
0x14000c8a8  lea     r8, [rbp+47h+Source]; Source
0x14000c8ac  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000c8b0  mov     rdx, r9; DestinationSize
0x14000c8b3  call    cs:__imp_memcpy_s
0x14000c8b9  mov     edx, [rbp+47h+Source]
0x14000c8bc  mov     ebx, edx
0x14000c8be  imul    rbx, [rdi+10h]
0x14000c8c3  add     rbx, rsi
0x14000c8c6  jmp     loc_14000C952
0x14000c8cb  movzx   eax, word ptr [rdi+6]
0x14000c8cf  xorps   xmm0, xmm0
0x14000c8d2  mov     [rbp+47h+var_60], ax
0x14000c8d6  mov     esi, r9d
0x14000c8d9  mov     al, [rdi+8]
0x14000c8dc  mov     [rbp+47h+var_5E], al
0x14000c8df  mov     eax, [rbp+47h+Source]
0x14000c8e2  mov     [rbp+47h+var_5C], r9d
0x14000c8e6  mov     [rbp+47h+var_58], r9w
0x14000c8eb  movdqu  [rbp+47h+var_50], xmm0
0x14000c8f0  test    eax, eax
0x14000c8f2  jz      short loc_14000C916
0x14000c8f4  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000c8f8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000c8fc  lea     rcx, [rbp+47h+var_60]; this
0x14000c900  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000c905  test    al, al
0x14000c907  mov     eax, [rbp+47h+Source]
0x14000c90a  jz      short loc_14000C912
0x14000c90c  inc     esi
0x14000c90e  cmp     esi, eax
0x14000c910  jb      short loc_14000C8F4
0x14000c912  mov     rbx, [rbp+47h+var_A8]
0x14000c916  cmp     eax, esi
0x14000c918  jz      short loc_14000C952
0x14000c91a  mov     al, [rbp+47h+var_9E]
0x14000c91d  mov     [rbp+47h+Source], esi
0x14000c920  cmp     al, 1
0x14000c922  jnz     short loc_14000C938
0x14000c924  mov     eax, 2
0x14000c929  mov     [rbp+47h+var_B0], si
0x14000c92d  mov     r9d, eax
0x14000c930  lea     r8, [rbp+47h+var_B0]
0x14000c934  mov     edx, eax
0x14000c936  jmp     short loc_14000C948
0x14000c938  cmp     al, 2
0x14000c93a  jnz     short loc_14000C952
0x14000c93c  mov     edx, 4; DestinationSize
0x14000c941  lea     r8, [rbp+47h+Source]; Source
0x14000c945  mov     r9d, edx; SourceSize
0x14000c948  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000c94c  call    cs:__imp_memcpy_s
0x14000c952  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000c956  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000c95a  lea     rcx, [rbp+47h+var_A0]; this
0x14000c95e  mov     [rbp+47h+var_A8], rbx
0x14000c962  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000c967  xor     r9d, r9d
0x14000c96a  mov     sil, al
0x14000c96d  test    al, al
0x14000c96f  jnz     loc_14000C81E
0x14000c975  mov     rbx, [rbp+47h+var_A8]
0x14000c979  mov     [rdi+20h], rbx
0x14000c97d  mov     rcx, r9
0x14000c980  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14000c984  jnz     loc_14000CA0F
0x14000c98a  movzx   eax, [rbp+47h+var_A0]
0x14000c98e  mov     [rbp+47h+Source], 1
0x14000c995  mov     [rbp+47h+var_98], r14w
0x14000c99a  mov     [rbp+47h+Buf2], r9
0x14000c99e  mov     [rbp+47h+Buf2+8], r15
0x14000c9a2  test    ax, ax
0x14000c9a5  jnz     short loc_14000C9F7
0x14000c9a7  movzx   ecx, r14w
0x14000c9ab  add     rcx, 2
0x14000c9af  jmp     short loc_14000C9FA
0x14000c9b1  mov     eax, [rbp+47h+arg_28]
0x14000c9b4  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x14000c9b8  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x14000c9bc  mov     r9, r13; void *
0x14000c9bf  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14000c9c3  mov     rcx, rdi; this
0x14000c9c6  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x14000c9cb  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14000c9d0  xor     r9d, r9d
0x14000c9d3  mov     [rbp+47h+var_A8], rax
0x14000c9d7  mov     rbx, rax
0x14000c9da  test    rax, rax
0x14000c9dd  jnz     short loc_14000C9E6
0x14000c9df  mov     al, 1
0x14000c9e1  jmp     loc_14000CB14
0x14000c9e6  mov     byte ptr [rbp+47h+arg_0], 1
0x14000c9ea  jmp     short loc_14000C9F0
0x14000c9ec  mov     [rbp+47h+var_A8], rbx
0x14000c9f0  test    sil, sil
0x14000c9f3  jnz     short loc_14000C97D
0x14000c9f5  jmp     short loc_14000C979
0x14000c9f7  mov     rcx, rax
0x14000c9fa  mov     al, [rbp+47h+var_9E]
0x14000c9fd  cmp     al, 1
0x14000c9ff  jnz     short loc_14000CA07
0x14000ca01  add     rcx, 2
0x14000ca05  jmp     short loc_14000CA0F
0x14000ca07  cmp     al, 2
0x14000ca09  jnz     short loc_14000CA0F
0x14000ca0b  add     rcx, 4
0x14000ca0f  movzx   eax, word ptr [rdi+6]
0x14000ca13  mov     dl, [rdi+8]
0x14000ca16  mov     r8d, [rbp+47h+arg_28]
0x14000ca1a  mov     [rbp+47h+var_80], ax
0x14000ca1e  mov     [rbp+47h+var_7E], dl
0x14000ca21  mov     [rbp+47h+var_7C], r8d
0x14000ca25  mov     [rbp+47h+var_78], r12w
0x14000ca2a  mov     [rbp+47h+var_70], r9
0x14000ca2e  mov     [rbp+47h+var_68], r13
0x14000ca32  test    ax, ax
0x14000ca35  jnz     short loc_14000CA3F
0x14000ca37  movzx   eax, r12w
0x14000ca3b  add     rax, 2
0x14000ca3f  cmp     dl, 1
0x14000ca42  jnz     short loc_14000CA4A
0x14000ca44  add     rax, 2
0x14000ca48  jmp     short loc_14000CA53
0x14000ca4a  cmp     dl, 2
0x14000ca4d  jnz     short loc_14000CA53
0x14000ca4f  add     rax, 4
0x14000ca53  mov     rdx, [rdi+28h]
0x14000ca57  lea     rsi, [rax+rcx]
0x14000ca5b  mov     r9, [rdi+20h]
0x14000ca5f  mov     rcx, rdx
0x14000ca62  sub     rcx, r9
0x14000ca65  cmp     r9, rdx
0x14000ca68  sbb     rax, rax
0x14000ca6b  and     rax, rcx
0x14000ca6e  cmp     rax, rsi
0x14000ca71  jb      loc_14000CB12
0x14000ca77  sub     rdx, rsi
0x14000ca7a  lea     rcx, [rsi+rbx]; Destination
0x14000ca7e  sub     rdx, rbx; DestinationSize
0x14000ca81  sub     r9, rbx; SourceSize
0x14000ca84  mov     r8, rbx; Source
0x14000ca87  call    cs:__imp_memmove_s
0x14000ca8d  add     [rdi+20h], rsi
0x14000ca91  xor     ebx, ebx
0x14000ca93  cmp     byte ptr [rbp+47h+arg_0], bl
0x14000ca96  jnz     short loc_14000CAAB
0x14000ca98  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000ca9c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000caa0  lea     rcx, [rbp+47h+var_A0]; this
0x14000caa4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000caa9  jmp     short loc_14000CAF8
0x14000caab  mov     cl, [rbp+47h+var_9E]
0x14000caae  test    cl, cl
0x14000cab0  jz      short loc_14000CAF8
0x14000cab2  mov     eax, [rbp+47h+Source]
0x14000cab5  lea     r8d, [rax+1]
0x14000cab9  cmp     eax, r8d
0x14000cabc  jz      short loc_14000CAF8
0x14000cabe  mov     [rbp+47h+Source], r8d
0x14000cac2  cmp     cl, 1
0x14000cac5  jnz     short loc_14000CADB
0x14000cac7  mov     r9d, 2
0x14000cacd  mov     [rbp+47h+arg_0], r8w
0x14000cad2  mov     edx, r9d
0x14000cad5  lea     r8, [rbp+47h+arg_0]
0x14000cad9  jmp     short loc_14000CAEE
0x14000cadb  cmp     cl, 2
0x14000cade  jnz     short loc_14000CAF8
0x14000cae0  mov     eax, 4
0x14000cae5  lea     r8, [rbp+47h+Source]; Source
0x14000cae9  mov     r9d, eax; SourceSize
0x14000caec  mov     edx, eax; DestinationSize
0x14000caee  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000caf2  call    cs:__imp_memcpy_s
0x14000caf8  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000cafc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000cb00  lea     rcx, [rbp+47h+var_80]; this
0x14000cb04  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000cb09  mov     byte ptr [rdi+38h], 1
0x14000cb0d  jmp     loc_14000C9DF
0x14000cb12  xor     al, al
0x14000cb14  add     rsp, 0A8h
0x14000cb1b  pop     r15
0x14000cb1d  pop     r14
0x14000cb1f  pop     r13
0x14000cb21  pop     r12
0x14000cb23  pop     rdi
0x14000cb24  pop     rsi
0x14000cb25  pop     rbx
0x14000cb26  pop     rbp
0x14000cb27  retn
```
