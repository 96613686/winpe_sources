# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006fb0`
- end: `0x180007349`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006ddc`

## callees

- `0x180004d5c`
- `0x180006908`
- `0x180006fb0`
- `0x1800093f8`
- `0x18003d4a6`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000729b`
- `msvcrt!memmove_s` at `0x18000729b`
- `msvcrt!memcpy_s` at `0x1800070bb`
- `msvcrt!memcpy_s` at `0x18000715a`
- `msvcrt!memcpy_s` at `0x18000730c`
- `msvcrt!memcpy_s` at `0x1800070bb`
- `msvcrt!memcpy_s` at `0x18000715a`
- `msvcrt!memcpy_s` at `0x18000730c`

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
0x180006fb0  push    rbp
0x180006fb2  push    rbx
0x180006fb3  push    rsi
0x180006fb4  push    rdi
0x180006fb5  push    r12
0x180006fb7  push    r13
0x180006fb9  push    r14
0x180006fbb  push    r15
0x180006fbd  lea     rbp, [rsp-0Fh]
0x180006fc2  sub     rsp, 0A8h
0x180006fc9  mov     rbx, [rcx+18h]
0x180006fcd  mov     rdi, rcx
0x180006fd0  xor     ecx, ecx
0x180006fd2  mov     r13, r9
0x180006fd5  mov     r14, r8
0x180006fd8  mov     r15, rdx
0x180006fdb  test    rbx, rbx
0x180006fde  jz      loc_180007332
0x180006fe4  movzx   eax, word ptr [rdi+2]
0x180006fe8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006fec  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006ff0  add     rbx, 0Ah
0x180006ff4  mov     [rbp+47h+var_A0], ax
0x180006ff8  xorps   xmm0, xmm0
0x180006ffb  mov     al, [rdi+4]
0x180006ffe  mov     [rbp+47h+Source], ecx
0x180007001  mov     [rbp+47h+var_98], cx
0x180007005  mov     byte ptr [rbp+47h+arg_0], cl
0x180007008  lea     rcx, [rbp+47h+var_A0]; this
0x18000700c  mov     [rbp+47h+var_9E], al
0x18000700f  mov     [rbp+47h+var_A8], rbx
0x180007013  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180007018  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000701d  mov     r12, [rbp+47h+arg_20]
0x180007021  jmp     loc_18000717B
0x180007026  movzx   eax, [rbp+47h+var_98]
0x18000702a  cmp     r14, rax
0x18000702d  jnz     short loc_180007045
0x18000702f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180007033  mov     r8, r14; Size
0x180007036  mov     rcx, r15; Buf1
0x180007039  call    memcmp_0
0x18000703e  mov     ecx, eax
0x180007040  xor     r9d, r9d
0x180007043  jmp     short loc_18000704E
0x180007045  movzx   eax, [rbp+47h+var_98]
0x180007049  mov     ecx, r14d
0x18000704c  sub     ecx, eax
0x18000704e  test    ecx, ecx
0x180007050  js      loc_180007200
0x180007056  jz      loc_1800071C5
0x18000705c  mov     rbx, [rbp+47h+var_A8]
0x180007060  mov     [rbp+47h+var_A8], rbx
0x180007064  cmp     [rdi+10h], r9
0x180007068  jbe     short loc_1800070D9
0x18000706a  mov     rax, [rdi+20h]
0x18000706e  xor     edx, edx
0x180007070  sub     rax, [rdi+18h]
0x180007074  mov     rsi, rbx
0x180007077  div     qword ptr [rdi+10h]
0x18000707b  mov     edx, [rbp+47h+Source]
0x18000707e  cmp     rdx, rax
0x180007081  jbe     short loc_1800070CA
0x180007083  cmp     edx, eax
0x180007085  jz      short loc_1800070CA
0x180007087  mov     edx, eax
0x180007089  mov     [rbp+47h+Source], eax
0x18000708c  mov     al, [rbp+47h+var_9E]
0x18000708f  cmp     al, 1
0x180007091  jnz     short loc_1800070A6
0x180007093  movzx   eax, dx
0x180007096  mov     [rbp+47h+var_B0], dx
0x18000709a  mov     r9d, 2
0x1800070a0  lea     r8, [rbp+47h+var_B0]
0x1800070a4  jmp     short loc_1800070B4
0x1800070a6  cmp     al, 2
0x1800070a8  jnz     short loc_1800070CA
0x1800070aa  mov     r9d, 4; SourceSize
0x1800070b0  lea     r8, [rbp+47h+Source]; Source
0x1800070b4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800070b8  mov     rdx, r9; DestinationSize
0x1800070bb  call    cs:__imp_memcpy_s
0x1800070c2  nop     dword ptr [rax+rax+00h]
0x1800070c7  mov     edx, [rbp+47h+Source]
0x1800070ca  mov     ebx, edx
0x1800070cc  imul    rbx, [rdi+10h]
0x1800070d1  add     rbx, rsi
0x1800070d4  jmp     loc_180007166
0x1800070d9  movzx   eax, word ptr [rdi+6]
0x1800070dd  xorps   xmm0, xmm0
0x1800070e0  mov     [rbp+47h+var_60], ax
0x1800070e4  mov     esi, r9d
0x1800070e7  mov     al, [rdi+8]
0x1800070ea  mov     [rbp+47h+var_5E], al
0x1800070ed  mov     eax, [rbp+47h+Source]
0x1800070f0  mov     [rbp+47h+var_5C], r9d
0x1800070f4  mov     [rbp+47h+var_58], r9w
0x1800070f9  movdqu  [rbp+47h+var_50], xmm0
0x1800070fe  test    eax, eax
0x180007100  jz      short loc_180007124
0x180007102  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007106  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000710a  lea     rcx, [rbp+47h+var_60]; this
0x18000710e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007113  test    al, al
0x180007115  mov     eax, [rbp+47h+Source]
0x180007118  jz      short loc_180007120
0x18000711a  inc     esi
0x18000711c  cmp     esi, eax
0x18000711e  jb      short loc_180007102
0x180007120  mov     rbx, [rbp+47h+var_A8]
0x180007124  cmp     eax, esi
0x180007126  jz      short loc_180007166
0x180007128  mov     al, [rbp+47h+var_9E]
0x18000712b  mov     [rbp+47h+Source], esi
0x18000712e  cmp     al, 1
0x180007130  jnz     short loc_180007146
0x180007132  mov     eax, 2
0x180007137  mov     [rbp+47h+var_B0], si
0x18000713b  mov     r9d, eax
0x18000713e  lea     r8, [rbp+47h+var_B0]
0x180007142  mov     edx, eax
0x180007144  jmp     short loc_180007156
0x180007146  cmp     al, 2
0x180007148  jnz     short loc_180007166
0x18000714a  mov     edx, 4; DestinationSize
0x18000714f  lea     r8, [rbp+47h+Source]; Source
0x180007153  mov     r9d, edx; SourceSize
0x180007156  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000715a  call    cs:__imp_memcpy_s
0x180007161  nop     dword ptr [rax+rax+00h]
0x180007166  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000716a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000716e  lea     rcx, [rbp+47h+var_A0]; this
0x180007172  mov     [rbp+47h+var_A8], rbx
0x180007176  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000717b  xor     r9d, r9d
0x18000717e  mov     sil, al
0x180007181  test    al, al
0x180007183  jnz     loc_180007026
0x180007189  mov     rbx, [rbp+47h+var_A8]
0x18000718d  mov     [rdi+20h], rbx
0x180007191  mov     rcx, r9
0x180007194  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180007198  jnz     loc_180007223
0x18000719e  movzx   eax, [rbp+47h+var_A0]
0x1800071a2  mov     [rbp+47h+Source], 1
0x1800071a9  mov     [rbp+47h+var_98], r14w
0x1800071ae  mov     [rbp+47h+Buf2], r9
0x1800071b2  mov     [rbp+47h+Buf2+8], r15
0x1800071b6  test    ax, ax
0x1800071b9  jnz     short loc_18000720B
0x1800071bb  movzx   ecx, r14w
0x1800071bf  add     rcx, 2
0x1800071c3  jmp     short loc_18000720E
0x1800071c5  mov     eax, [rbp+47h+arg_28]
0x1800071c8  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1800071cc  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800071d0  mov     r9, r13; void *
0x1800071d3  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800071d7  mov     rcx, rdi; this
0x1800071da  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800071df  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800071e4  xor     r9d, r9d
0x1800071e7  mov     [rbp+47h+var_A8], rax
0x1800071eb  mov     rbx, rax
0x1800071ee  test    rax, rax
0x1800071f1  jnz     short loc_1800071FA
0x1800071f3  mov     al, 1
0x1800071f5  jmp     loc_180007334
0x1800071fa  mov     byte ptr [rbp+47h+arg_0], 1
0x1800071fe  jmp     short loc_180007204
0x180007200  mov     [rbp+47h+var_A8], rbx
0x180007204  test    sil, sil
0x180007207  jnz     short loc_180007191
0x180007209  jmp     short loc_18000718D
0x18000720b  mov     rcx, rax
0x18000720e  mov     al, [rbp+47h+var_9E]
0x180007211  cmp     al, 1
0x180007213  jnz     short loc_18000721B
0x180007215  add     rcx, 2
0x180007219  jmp     short loc_180007223
0x18000721b  cmp     al, 2
0x18000721d  jnz     short loc_180007223
0x18000721f  add     rcx, 4
0x180007223  movzx   eax, word ptr [rdi+6]
0x180007227  mov     dl, [rdi+8]
0x18000722a  mov     r8d, [rbp+47h+arg_28]
0x18000722e  mov     [rbp+47h+var_80], ax
0x180007232  mov     [rbp+47h+var_7E], dl
0x180007235  mov     [rbp+47h+var_7C], r8d
0x180007239  mov     [rbp+47h+var_78], r12w
0x18000723e  mov     [rbp+47h+var_70], r9
0x180007242  mov     [rbp+47h+var_68], r13
0x180007246  test    ax, ax
0x180007249  jnz     short loc_180007253
0x18000724b  movzx   eax, r12w
0x18000724f  add     rax, 2
0x180007253  cmp     dl, 1
0x180007256  jnz     short loc_18000725E
0x180007258  add     rax, 2
0x18000725c  jmp     short loc_180007267
0x18000725e  cmp     dl, 2
0x180007261  jnz     short loc_180007267
0x180007263  add     rax, 4
0x180007267  mov     rdx, [rdi+28h]
0x18000726b  lea     rsi, [rax+rcx]
0x18000726f  mov     r9, [rdi+20h]
0x180007273  mov     rcx, rdx
0x180007276  sub     rcx, r9
0x180007279  cmp     r9, rdx
0x18000727c  sbb     rax, rax
0x18000727f  and     rax, rcx
0x180007282  cmp     rax, rsi
0x180007285  jb      loc_180007332
0x18000728b  sub     rdx, rsi
0x18000728e  lea     rcx, [rsi+rbx]; Destination
0x180007292  sub     rdx, rbx; DestinationSize
0x180007295  sub     r9, rbx; SourceSize
0x180007298  mov     r8, rbx; Source
0x18000729b  call    cs:__imp_memmove_s
0x1800072a2  nop     dword ptr [rax+rax+00h]
0x1800072a7  add     [rdi+20h], rsi
0x1800072ab  xor     ebx, ebx
0x1800072ad  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800072b0  jnz     short loc_1800072C5
0x1800072b2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800072b6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800072ba  lea     rcx, [rbp+47h+var_A0]; this
0x1800072be  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800072c3  jmp     short loc_180007318
0x1800072c5  mov     cl, [rbp+47h+var_9E]
0x1800072c8  test    cl, cl
0x1800072ca  jz      short loc_180007318
0x1800072cc  mov     eax, [rbp+47h+Source]
0x1800072cf  lea     r8d, [rax+1]
0x1800072d3  cmp     eax, r8d
0x1800072d6  jz      short loc_180007318
0x1800072d8  mov     [rbp+47h+Source], r8d
0x1800072dc  cmp     cl, 1
0x1800072df  jnz     short loc_1800072F5
0x1800072e1  mov     r9d, 2
0x1800072e7  mov     [rbp+47h+arg_0], r8w
0x1800072ec  mov     edx, r9d
0x1800072ef  lea     r8, [rbp+47h+arg_0]
0x1800072f3  jmp     short loc_180007308
0x1800072f5  cmp     cl, 2
0x1800072f8  jnz     short loc_180007318
0x1800072fa  mov     eax, 4
0x1800072ff  lea     r8, [rbp+47h+Source]; Source
0x180007303  mov     r9d, eax; SourceSize
0x180007306  mov     edx, eax; DestinationSize
0x180007308  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000730c  call    cs:__imp_memcpy_s
0x180007313  nop     dword ptr [rax+rax+00h]
0x180007318  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000731c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007320  lea     rcx, [rbp+47h+var_80]; this
0x180007324  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007329  mov     byte ptr [rdi+38h], 1
0x18000732d  jmp     loc_1800071F3
0x180007332  xor     al, al
0x180007334  add     rsp, 0A8h
0x18000733b  pop     r15
0x18000733d  pop     r14
0x18000733f  pop     r13
0x180007341  pop     r12
0x180007343  pop     rdi
0x180007344  pop     rsi
0x180007345  pop     rbx
0x180007346  pop     rbp
0x180007347  retn
```
