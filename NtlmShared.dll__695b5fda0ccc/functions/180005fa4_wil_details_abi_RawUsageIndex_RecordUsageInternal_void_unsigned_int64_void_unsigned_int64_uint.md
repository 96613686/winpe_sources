# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005fa4`
- end: `0x180006324`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005df4`

## callees

- `0x180003ee0`
- `0x180005788`
- `0x180005fa4`
- `0x180007b6c`
- `0x18000c48c`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800060af`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006148`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800062ee`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800060af`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180006148`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800062ee`
- `api-ms-win-core-crt-l1-1-0!memmove_s` at `0x180006283`
- `api-ms-win-core-crt-l1-1-0!memmove_s` at `0x180006283`

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
0x180005fa4  push    rbp
0x180005fa6  push    rbx
0x180005fa7  push    rsi
0x180005fa8  push    rdi
0x180005fa9  push    r12
0x180005fab  push    r13
0x180005fad  push    r14
0x180005faf  push    r15
0x180005fb1  lea     rbp, [rsp-0Fh]
0x180005fb6  sub     rsp, 0A8h
0x180005fbd  mov     rbx, [rcx+18h]
0x180005fc1  mov     rdi, rcx
0x180005fc4  xor     ecx, ecx
0x180005fc6  mov     r13, r9
0x180005fc9  mov     r14, r8
0x180005fcc  mov     r15, rdx
0x180005fcf  test    rbx, rbx
0x180005fd2  jz      loc_18000630E
0x180005fd8  movzx   eax, word ptr [rdi+2]
0x180005fdc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180005fe0  mov     r8, [rdi+20h]; unsigned __int8 *
0x180005fe4  add     rbx, 0Ah
0x180005fe8  mov     [rbp+47h+var_A0], ax
0x180005fec  xorps   xmm0, xmm0
0x180005fef  mov     al, [rdi+4]
0x180005ff2  mov     [rbp+47h+Source], ecx
0x180005ff5  mov     [rbp+47h+var_98], cx
0x180005ff9  mov     byte ptr [rbp+47h+arg_0], cl
0x180005ffc  lea     rcx, [rbp+47h+var_A0]; this
0x180006000  mov     [rbp+47h+var_9E], al
0x180006003  mov     [rbp+47h+var_A8], rbx
0x180006007  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000600c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006011  mov     r12, [rbp+47h+arg_20]
0x180006015  jmp     loc_180006163
0x18000601a  movzx   eax, [rbp+47h+var_98]
0x18000601e  cmp     r14, rax
0x180006021  jnz     short loc_180006039
0x180006023  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180006027  mov     r8, r14; Size
0x18000602a  mov     rcx, r15; Buf1
0x18000602d  call    memcmp_0
0x180006032  mov     ecx, eax
0x180006034  xor     r9d, r9d
0x180006037  jmp     short loc_180006042
0x180006039  movzx   eax, [rbp+47h+var_98]
0x18000603d  mov     ecx, r14d
0x180006040  sub     ecx, eax
0x180006042  test    ecx, ecx
0x180006044  js      loc_1800061E8
0x18000604a  jz      loc_1800061AD
0x180006050  mov     rbx, [rbp+47h+var_A8]
0x180006054  mov     [rbp+47h+var_A8], rbx
0x180006058  cmp     [rdi+10h], r9
0x18000605c  jbe     short loc_1800060C7
0x18000605e  mov     rax, [rdi+20h]
0x180006062  xor     edx, edx
0x180006064  sub     rax, [rdi+18h]
0x180006068  mov     rsi, rbx
0x18000606b  div     qword ptr [rdi+10h]
0x18000606f  mov     edx, [rbp+47h+Source]
0x180006072  cmp     rdx, rax
0x180006075  jbe     short loc_1800060B8
0x180006077  cmp     edx, eax
0x180006079  jz      short loc_1800060B8
0x18000607b  mov     edx, eax
0x18000607d  mov     [rbp+47h+Source], eax
0x180006080  mov     al, [rbp+47h+var_9E]
0x180006083  cmp     al, 1
0x180006085  jnz     short loc_18000609A
0x180006087  movzx   eax, dx
0x18000608a  mov     [rbp+47h+var_B0], dx
0x18000608e  mov     r9d, 2
0x180006094  lea     r8, [rbp+47h+var_B0]
0x180006098  jmp     short loc_1800060A8
0x18000609a  cmp     al, 2
0x18000609c  jnz     short loc_1800060B8
0x18000609e  mov     r9d, 4; SourceSize
0x1800060a4  lea     r8, [rbp+47h+Source]; Source
0x1800060a8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800060ac  mov     rdx, r9; DestinationSize
0x1800060af  call    cs:__imp_memcpy_s
0x1800060b5  mov     edx, [rbp+47h+Source]
0x1800060b8  mov     ebx, edx
0x1800060ba  imul    rbx, [rdi+10h]
0x1800060bf  add     rbx, rsi
0x1800060c2  jmp     loc_18000614E
0x1800060c7  movzx   eax, word ptr [rdi+6]
0x1800060cb  xorps   xmm0, xmm0
0x1800060ce  mov     [rbp+47h+var_60], ax
0x1800060d2  mov     esi, r9d
0x1800060d5  mov     al, [rdi+8]
0x1800060d8  mov     [rbp+47h+var_5E], al
0x1800060db  mov     eax, [rbp+47h+Source]
0x1800060de  mov     [rbp+47h+var_5C], r9d
0x1800060e2  mov     [rbp+47h+var_58], r9w
0x1800060e7  movdqu  [rbp+47h+var_50], xmm0
0x1800060ec  test    eax, eax
0x1800060ee  jz      short loc_180006112
0x1800060f0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800060f4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800060f8  lea     rcx, [rbp+47h+var_60]; this
0x1800060fc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006101  test    al, al
0x180006103  mov     eax, [rbp+47h+Source]
0x180006106  jz      short loc_18000610E
0x180006108  inc     esi
0x18000610a  cmp     esi, eax
0x18000610c  jb      short loc_1800060F0
0x18000610e  mov     rbx, [rbp+47h+var_A8]
0x180006112  cmp     eax, esi
0x180006114  jz      short loc_18000614E
0x180006116  mov     al, [rbp+47h+var_9E]
0x180006119  mov     [rbp+47h+Source], esi
0x18000611c  cmp     al, 1
0x18000611e  jnz     short loc_180006134
0x180006120  mov     eax, 2
0x180006125  mov     [rbp+47h+var_B0], si
0x180006129  mov     r9d, eax
0x18000612c  lea     r8, [rbp+47h+var_B0]
0x180006130  mov     edx, eax
0x180006132  jmp     short loc_180006144
0x180006134  cmp     al, 2
0x180006136  jnz     short loc_18000614E
0x180006138  mov     edx, 4; DestinationSize
0x18000613d  lea     r8, [rbp+47h+Source]; Source
0x180006141  mov     r9d, edx; SourceSize
0x180006144  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006148  call    cs:__imp_memcpy_s
0x18000614e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006152  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006156  lea     rcx, [rbp+47h+var_A0]; this
0x18000615a  mov     [rbp+47h+var_A8], rbx
0x18000615e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006163  xor     r9d, r9d
0x180006166  mov     sil, al
0x180006169  test    al, al
0x18000616b  jnz     loc_18000601A
0x180006171  mov     rbx, [rbp+47h+var_A8]
0x180006175  mov     [rdi+20h], rbx
0x180006179  mov     rcx, r9
0x18000617c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180006180  jnz     loc_18000620B
0x180006186  movzx   eax, [rbp+47h+var_A0]
0x18000618a  mov     [rbp+47h+Source], 1
0x180006191  mov     [rbp+47h+var_98], r14w
0x180006196  mov     [rbp+47h+Buf2], r9
0x18000619a  mov     [rbp+47h+Buf2+8], r15
0x18000619e  test    ax, ax
0x1800061a1  jnz     short loc_1800061F3
0x1800061a3  movzx   ecx, r14w
0x1800061a7  add     rcx, 2
0x1800061ab  jmp     short loc_1800061F6
0x1800061ad  mov     eax, [rbp+47h+arg_28]
0x1800061b0  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1800061b4  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800061b8  mov     r9, r13; void *
0x1800061bb  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800061bf  mov     rcx, rdi; this
0x1800061c2  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800061c7  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800061cc  xor     r9d, r9d
0x1800061cf  mov     [rbp+47h+var_A8], rax
0x1800061d3  mov     rbx, rax
0x1800061d6  test    rax, rax
0x1800061d9  jnz     short loc_1800061E2
0x1800061db  mov     al, 1
0x1800061dd  jmp     loc_180006310
0x1800061e2  mov     byte ptr [rbp+47h+arg_0], 1
0x1800061e6  jmp     short loc_1800061EC
0x1800061e8  mov     [rbp+47h+var_A8], rbx
0x1800061ec  test    sil, sil
0x1800061ef  jnz     short loc_180006179
0x1800061f1  jmp     short loc_180006175
0x1800061f3  mov     rcx, rax
0x1800061f6  mov     al, [rbp+47h+var_9E]
0x1800061f9  cmp     al, 1
0x1800061fb  jnz     short loc_180006203
0x1800061fd  add     rcx, 2
0x180006201  jmp     short loc_18000620B
0x180006203  cmp     al, 2
0x180006205  jnz     short loc_18000620B
0x180006207  add     rcx, 4
0x18000620b  movzx   eax, word ptr [rdi+6]
0x18000620f  mov     dl, [rdi+8]
0x180006212  mov     r8d, [rbp+47h+arg_28]
0x180006216  mov     [rbp+47h+var_80], ax
0x18000621a  mov     [rbp+47h+var_7E], dl
0x18000621d  mov     [rbp+47h+var_7C], r8d
0x180006221  mov     [rbp+47h+var_78], r12w
0x180006226  mov     [rbp+47h+var_70], r9
0x18000622a  mov     [rbp+47h+var_68], r13
0x18000622e  test    ax, ax
0x180006231  jnz     short loc_18000623B
0x180006233  movzx   eax, r12w
0x180006237  add     rax, 2
0x18000623b  cmp     dl, 1
0x18000623e  jnz     short loc_180006246
0x180006240  add     rax, 2
0x180006244  jmp     short loc_18000624F
0x180006246  cmp     dl, 2
0x180006249  jnz     short loc_18000624F
0x18000624b  add     rax, 4
0x18000624f  mov     rdx, [rdi+28h]
0x180006253  lea     rsi, [rax+rcx]
0x180006257  mov     r9, [rdi+20h]
0x18000625b  mov     rcx, rdx
0x18000625e  sub     rcx, r9
0x180006261  cmp     r9, rdx
0x180006264  sbb     rax, rax
0x180006267  and     rax, rcx
0x18000626a  cmp     rax, rsi
0x18000626d  jb      loc_18000630E
0x180006273  sub     rdx, rsi
0x180006276  lea     rcx, [rsi+rbx]; Destination
0x18000627a  sub     rdx, rbx; DestinationSize
0x18000627d  sub     r9, rbx; SourceSize
0x180006280  mov     r8, rbx; Source
0x180006283  call    cs:__imp_memmove_s
0x180006289  add     [rdi+20h], rsi
0x18000628d  xor     ebx, ebx
0x18000628f  cmp     byte ptr [rbp+47h+arg_0], bl
0x180006292  jnz     short loc_1800062A7
0x180006294  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006298  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000629c  lea     rcx, [rbp+47h+var_A0]; this
0x1800062a0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800062a5  jmp     short loc_1800062F4
0x1800062a7  mov     cl, [rbp+47h+var_9E]
0x1800062aa  test    cl, cl
0x1800062ac  jz      short loc_1800062F4
0x1800062ae  mov     eax, [rbp+47h+Source]
0x1800062b1  lea     r8d, [rax+1]
0x1800062b5  cmp     eax, r8d
0x1800062b8  jz      short loc_1800062F4
0x1800062ba  mov     [rbp+47h+Source], r8d
0x1800062be  cmp     cl, 1
0x1800062c1  jnz     short loc_1800062D7
0x1800062c3  mov     r9d, 2
0x1800062c9  mov     [rbp+47h+arg_0], r8w
0x1800062ce  mov     edx, r9d
0x1800062d1  lea     r8, [rbp+47h+arg_0]
0x1800062d5  jmp     short loc_1800062EA
0x1800062d7  cmp     cl, 2
0x1800062da  jnz     short loc_1800062F4
0x1800062dc  mov     eax, 4
0x1800062e1  lea     r8, [rbp+47h+Source]; Source
0x1800062e5  mov     r9d, eax; SourceSize
0x1800062e8  mov     edx, eax; DestinationSize
0x1800062ea  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800062ee  call    cs:__imp_memcpy_s
0x1800062f4  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800062f8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800062fc  lea     rcx, [rbp+47h+var_80]; this
0x180006300  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006305  mov     byte ptr [rdi+38h], 1
0x180006309  jmp     loc_1800061DB
0x18000630e  xor     al, al
0x180006310  add     rsp, 0A8h
0x180006317  pop     r15
0x180006319  pop     r14
0x18000631b  pop     r13
0x18000631d  pop     r12
0x18000631f  pop     rdi
0x180006320  pop     rsi
0x180006321  pop     rbx
0x180006322  pop     rbp
0x180006323  retn
```
