# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180013f34`
- end: `0x1800142c9`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `917`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013d68`

## callees

- `0x18000d3c0`
- `0x1800130b8`
- `0x180013f34`
- `0x18001db7c`
- `0x1800502b6`
- `0x180050300`

## import_xrefs

- `msvcrt!memmove_s` at `0x180014215`
- `msvcrt!memmove_s` at `0x180014215`
- `msvcrt!memcpy_s` at `0x180014041`
- `msvcrt!memcpy_s` at `0x1800140da`
- `msvcrt!memcpy_s` at `0x180014280`
- `msvcrt!memcpy_s` at `0x180014041`
- `msvcrt!memcpy_s` at `0x1800140da`
- `msvcrt!memcpy_s` at `0x180014280`

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
0x180013f34  mov     [rsp-8+arg_8], rbx
0x180013f39  push    rbp
0x180013f3a  push    rsi
0x180013f3b  push    rdi
0x180013f3c  push    r12
0x180013f3e  push    r13
0x180013f40  push    r14
0x180013f42  push    r15
0x180013f44  lea     rbp, [rsp-17h]
0x180013f49  sub     rsp, 0B0h
0x180013f50  mov     rax, cs:__security_cookie
0x180013f57  xor     rax, rsp
0x180013f5a  mov     [rbp+47h+var_38], rax
0x180013f5e  mov     rbx, [rcx+18h]
0x180013f62  mov     rdi, rcx
0x180013f65  mov     eax, [rbp+47h+arg_28]
0x180013f68  xor     ecx, ecx
0x180013f6a  mov     r15, [rbp+47h+arg_20]
0x180013f6e  mov     r13, r9
0x180013f71  mov     [rbp+47h+var_A0], eax
0x180013f74  mov     r14, r8
0x180013f77  mov     r12, rdx
0x180013f7a  test    rbx, rbx
0x180013f7d  jz      loc_1800142A0
0x180013f83  movzx   eax, word ptr [rdi+2]
0x180013f87  xorps   xmm0, xmm0
0x180013f8a  mov     [rbp+47h+var_98], ax
0x180013f8e  add     rbx, 0Ah
0x180013f92  mov     al, [rdi+4]
0x180013f95  mov     [rbp+47h+var_96], al
0x180013f98  mov     [rbp+47h+Source], ecx
0x180013f9b  mov     [rbp+47h+var_90], cx
0x180013f9f  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180013fa4  mov     [rbp+47h+var_B0], cl
0x180013fa7  jmp     loc_1800140E0
0x180013fac  movzx   ecx, [rbp+47h+var_90]
0x180013fb0  cmp     r14, rcx
0x180013fb3  jnz     short loc_180013FCB
0x180013fb5  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180013fb9  mov     r8, r14; Size
0x180013fbc  mov     rcx, r12; Buf1
0x180013fbf  call    memcmp_0
0x180013fc4  mov     ecx, eax
0x180013fc6  xor     r9d, r9d
0x180013fc9  jmp     short loc_180013FD4
0x180013fcb  movzx   eax, [rbp+47h+var_90]
0x180013fcf  mov     ecx, r14d
0x180013fd2  sub     ecx, eax
0x180013fd4  test    ecx, ecx
0x180013fd6  js      loc_18001417A
0x180013fdc  jz      loc_18001413F
0x180013fe2  mov     rbx, [rbp+47h+var_A8]
0x180013fe6  mov     [rbp+47h+var_A8], rbx
0x180013fea  cmp     [rdi+10h], r9
0x180013fee  jbe     short loc_180014059
0x180013ff0  mov     rax, [rdi+20h]
0x180013ff4  xor     edx, edx
0x180013ff6  sub     rax, [rdi+18h]
0x180013ffa  mov     rsi, rbx
0x180013ffd  div     qword ptr [rdi+10h]
0x180014001  mov     edx, [rbp+47h+Source]
0x180014004  cmp     rdx, rax
0x180014007  jbe     short loc_18001404A
0x180014009  cmp     edx, eax
0x18001400b  jz      short loc_18001404A
0x18001400d  mov     edx, eax
0x18001400f  mov     [rbp+47h+Source], eax
0x180014012  mov     al, [rbp+47h+var_96]
0x180014015  cmp     al, 1
0x180014017  jnz     short loc_18001402C
0x180014019  movzx   eax, dx
0x18001401c  mov     [rbp+47h+var_9C], dx
0x180014020  mov     r9d, 2
0x180014026  lea     r8, [rbp+47h+var_9C]
0x18001402a  jmp     short loc_18001403A
0x18001402c  cmp     al, 2
0x18001402e  jnz     short loc_18001404A
0x180014030  mov     r9d, 4; SourceSize
0x180014036  lea     r8, [rbp+47h+Source]; Source
0x18001403a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001403e  mov     rdx, r9; DestinationSize
0x180014041  call    cs:__imp_memcpy_s
0x180014047  mov     edx, [rbp+47h+Source]
0x18001404a  mov     ebx, edx
0x18001404c  imul    rbx, [rdi+10h]
0x180014051  add     rbx, rsi
0x180014054  jmp     loc_1800140E0
0x180014059  movzx   eax, word ptr [rdi+6]
0x18001405d  xorps   xmm0, xmm0
0x180014060  mov     [rbp+47h+var_58], ax
0x180014064  mov     esi, r9d
0x180014067  mov     al, [rdi+8]
0x18001406a  mov     [rbp+47h+var_56], al
0x18001406d  mov     eax, [rbp+47h+Source]
0x180014070  mov     [rbp+47h+var_54], r9d
0x180014074  mov     [rbp+47h+var_50], r9w
0x180014079  movdqu  [rbp+47h+var_48], xmm0
0x18001407e  test    eax, eax
0x180014080  jz      short loc_1800140A4
0x180014082  mov     r8, [rdi+20h]; unsigned __int8 *
0x180014086  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001408a  lea     rcx, [rbp+47h+var_58]; this
0x18001408e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014093  test    al, al
0x180014095  mov     eax, [rbp+47h+Source]
0x180014098  jz      short loc_1800140A0
0x18001409a  inc     esi
0x18001409c  cmp     esi, eax
0x18001409e  jb      short loc_180014082
0x1800140a0  mov     rbx, [rbp+47h+var_A8]
0x1800140a4  cmp     eax, esi
0x1800140a6  jz      short loc_1800140E0
0x1800140a8  mov     al, [rbp+47h+var_96]
0x1800140ab  mov     [rbp+47h+Source], esi
0x1800140ae  cmp     al, 1
0x1800140b0  jnz     short loc_1800140C6
0x1800140b2  mov     eax, 2
0x1800140b7  mov     [rbp+47h+var_9C], si
0x1800140bb  mov     r9d, eax
0x1800140be  lea     r8, [rbp+47h+var_9C]
0x1800140c2  mov     edx, eax
0x1800140c4  jmp     short loc_1800140D6
0x1800140c6  cmp     al, 2
0x1800140c8  jnz     short loc_1800140E0
0x1800140ca  mov     edx, 4; DestinationSize
0x1800140cf  lea     r8, [rbp+47h+Source]; Source
0x1800140d3  mov     r9d, edx; SourceSize
0x1800140d6  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800140da  call    cs:__imp_memcpy_s
0x1800140e0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800140e4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800140e8  lea     rcx, [rbp+47h+var_98]; this
0x1800140ec  mov     [rbp+47h+var_A8], rbx
0x1800140f0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800140f5  xor     r9d, r9d
0x1800140f8  mov     sil, al
0x1800140fb  test    al, al
0x1800140fd  jnz     loc_180013FAC
0x180014103  mov     rbx, [rbp+47h+var_A8]
0x180014107  mov     [rdi+20h], rbx
0x18001410b  mov     rcx, r9
0x18001410e  cmp     [rbp+47h+var_B0], r9b
0x180014112  jnz     loc_18001419D
0x180014118  movzx   eax, [rbp+47h+var_98]
0x18001411c  mov     [rbp+47h+Source], 1
0x180014123  mov     [rbp+47h+var_90], r14w
0x180014128  mov     [rbp+47h+Buf2], r9
0x18001412c  mov     [rbp+47h+Buf2+8], r12
0x180014130  test    ax, ax
0x180014133  jnz     short loc_180014185
0x180014135  movzx   ecx, r14w
0x180014139  add     rcx, 2
0x18001413d  jmp     short loc_180014188
0x18001413f  mov     eax, [rbp+47h+var_A0]
0x180014142  lea     rdx, [rbp+47h+var_98]; struct wil::details_abi::UsageIndexProperty *
0x180014146  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18001414a  mov     r9, r13; void *
0x18001414d  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180014151  mov     rcx, rdi; this
0x180014154  mov     [rsp+0E0h+var_C0], r15; unsigned __int64
0x180014159  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001415e  xor     r9d, r9d
0x180014161  mov     [rbp+47h+var_A8], rax
0x180014165  mov     rbx, rax
0x180014168  test    rax, rax
0x18001416b  jnz     short loc_180014174
0x18001416d  mov     al, 1
0x18001416f  jmp     loc_1800142A2
0x180014174  mov     [rbp+47h+var_B0], 1
0x180014178  jmp     short loc_18001417E
0x18001417a  mov     [rbp+47h+var_A8], rbx
0x18001417e  test    sil, sil
0x180014181  jnz     short loc_18001410B
0x180014183  jmp     short loc_180014107
0x180014185  mov     rcx, rax
0x180014188  mov     al, [rbp+47h+var_96]
0x18001418b  cmp     al, 1
0x18001418d  jnz     short loc_180014195
0x18001418f  add     rcx, 2
0x180014193  jmp     short loc_18001419D
0x180014195  cmp     al, 2
0x180014197  jnz     short loc_18001419D
0x180014199  add     rcx, 4
0x18001419d  movzx   eax, word ptr [rdi+6]
0x1800141a1  mov     dl, [rdi+8]
0x1800141a4  mov     r8d, [rbp+47h+var_A0]
0x1800141a8  mov     [rbp+47h+var_78], ax
0x1800141ac  mov     [rbp+47h+var_76], dl
0x1800141af  mov     [rbp+47h+var_74], r8d
0x1800141b3  mov     [rbp+47h+var_70], r15w
0x1800141b8  mov     [rbp+47h+var_68], r9
0x1800141bc  mov     [rbp+47h+var_60], r13
0x1800141c0  test    ax, ax
0x1800141c3  jnz     short loc_1800141CD
0x1800141c5  movzx   eax, r15w
0x1800141c9  add     rax, 2
0x1800141cd  cmp     dl, 1
0x1800141d0  jnz     short loc_1800141D8
0x1800141d2  add     rax, 2
0x1800141d6  jmp     short loc_1800141E1
0x1800141d8  cmp     dl, 2
0x1800141db  jnz     short loc_1800141E1
0x1800141dd  add     rax, 4
0x1800141e1  mov     rdx, [rdi+28h]
0x1800141e5  lea     rsi, [rax+rcx]
0x1800141e9  mov     r9, [rdi+20h]
0x1800141ed  mov     rcx, rdx
0x1800141f0  sub     rcx, r9
0x1800141f3  cmp     r9, rdx
0x1800141f6  sbb     rax, rax
0x1800141f9  and     rax, rcx
0x1800141fc  cmp     rax, rsi
0x1800141ff  jb      loc_1800142A0
0x180014205  sub     rdx, rsi
0x180014208  lea     rcx, [rsi+rbx]; Destination
0x18001420c  sub     rdx, rbx; DestinationSize
0x18001420f  sub     r9, rbx; SourceSize
0x180014212  mov     r8, rbx; Source
0x180014215  call    cs:__imp_memmove_s
0x18001421b  add     [rdi+20h], rsi
0x18001421f  xor     ebx, ebx
0x180014221  cmp     [rbp+47h+var_B0], bl
0x180014224  jnz     short loc_180014239
0x180014226  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001422a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001422e  lea     rcx, [rbp+47h+var_98]; this
0x180014232  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014237  jmp     short loc_180014286
0x180014239  mov     cl, [rbp+47h+var_96]
0x18001423c  test    cl, cl
0x18001423e  jz      short loc_180014286
0x180014240  mov     eax, [rbp+47h+Source]
0x180014243  lea     r8d, [rax+1]
0x180014247  cmp     eax, r8d
0x18001424a  jz      short loc_180014286
0x18001424c  mov     [rbp+47h+Source], r8d
0x180014250  cmp     cl, 1
0x180014253  jnz     short loc_180014269
0x180014255  mov     r9d, 2
0x18001425b  mov     [rbp+47h+var_9C], r8w
0x180014260  mov     edx, r9d
0x180014263  lea     r8, [rbp+47h+var_9C]
0x180014267  jmp     short loc_18001427C
0x180014269  cmp     cl, 2
0x18001426c  jnz     short loc_180014286
0x18001426e  mov     eax, 4
0x180014273  lea     r8, [rbp+47h+Source]; Source
0x180014277  mov     r9d, eax; SourceSize
0x18001427a  mov     edx, eax; DestinationSize
0x18001427c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180014280  call    cs:__imp_memcpy_s
0x180014286  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001428a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001428e  lea     rcx, [rbp+47h+var_78]; this
0x180014292  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180014297  mov     byte ptr [rdi+38h], 1
0x18001429b  jmp     loc_18001416D
0x1800142a0  xor     al, al
0x1800142a2  mov     rcx, [rbp+47h+var_38]
0x1800142a6  xor     rcx, rsp; StackCookie
0x1800142a9  call    __security_check_cookie
0x1800142ae  mov     rbx, [rsp+0E0h+arg_8]
0x1800142b6  add     rsp, 0B0h
0x1800142bd  pop     r15
0x1800142bf  pop     r14
0x1800142c1  pop     r13
0x1800142c3  pop     r12
0x1800142c5  pop     rdi
0x1800142c6  pop     rsi
0x1800142c7  pop     rbp
0x1800142c8  retn
```
