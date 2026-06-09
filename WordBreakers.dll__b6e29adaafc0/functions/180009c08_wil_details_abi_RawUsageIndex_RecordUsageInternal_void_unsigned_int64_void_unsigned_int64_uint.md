# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009c08`
- end: `0x180009f88`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009a58`

## callees

- `0x18000882c`
- `0x180009640`
- `0x180009c08`
- `0x18000ae94`
- `0x18000b606`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009d13`
- `msvcrt!memcpy_s` at `0x180009dac`
- `msvcrt!memcpy_s` at `0x180009f52`
- `msvcrt!memcpy_s` at `0x180009d13`
- `msvcrt!memcpy_s` at `0x180009dac`
- `msvcrt!memcpy_s` at `0x180009f52`
- `msvcrt!memmove_s` at `0x180009ee7`
- `msvcrt!memmove_s` at `0x180009ee7`

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
0x180009c08  push    rbp
0x180009c0a  push    rbx
0x180009c0b  push    rsi
0x180009c0c  push    rdi
0x180009c0d  push    r12
0x180009c0f  push    r13
0x180009c11  push    r14
0x180009c13  push    r15
0x180009c15  lea     rbp, [rsp-0Fh]
0x180009c1a  sub     rsp, 0A8h
0x180009c21  mov     rbx, [rcx+18h]
0x180009c25  mov     rdi, rcx
0x180009c28  xor     ecx, ecx
0x180009c2a  mov     r13, r9
0x180009c2d  mov     r14, r8
0x180009c30  mov     r15, rdx
0x180009c33  test    rbx, rbx
0x180009c36  jz      loc_180009F72
0x180009c3c  movzx   eax, word ptr [rdi+2]
0x180009c40  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180009c44  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009c48  add     rbx, 0Ah
0x180009c4c  mov     [rbp+47h+var_A0], ax
0x180009c50  xorps   xmm0, xmm0
0x180009c53  mov     al, [rdi+4]
0x180009c56  mov     [rbp+47h+Source], ecx
0x180009c59  mov     [rbp+47h+var_98], cx
0x180009c5d  mov     byte ptr [rbp+47h+arg_0], cl
0x180009c60  lea     rcx, [rbp+47h+var_A0]; this
0x180009c64  mov     [rbp+47h+var_9E], al
0x180009c67  mov     [rbp+47h+var_A8], rbx
0x180009c6b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180009c70  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009c75  mov     r12, [rbp+47h+arg_20]
0x180009c79  jmp     loc_180009DC7
0x180009c7e  movzx   eax, [rbp+47h+var_98]
0x180009c82  cmp     r14, rax
0x180009c85  jnz     short loc_180009C9D
0x180009c87  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180009c8b  mov     r8, r14; Size
0x180009c8e  mov     rcx, r15; Buf1
0x180009c91  call    memcmp_0
0x180009c96  mov     ecx, eax
0x180009c98  xor     r9d, r9d
0x180009c9b  jmp     short loc_180009CA6
0x180009c9d  movzx   eax, [rbp+47h+var_98]
0x180009ca1  mov     ecx, r14d
0x180009ca4  sub     ecx, eax
0x180009ca6  test    ecx, ecx
0x180009ca8  js      loc_180009E4C
0x180009cae  jz      loc_180009E11
0x180009cb4  mov     rbx, [rbp+47h+var_A8]
0x180009cb8  mov     [rbp+47h+var_A8], rbx
0x180009cbc  cmp     [rdi+10h], r9
0x180009cc0  jbe     short loc_180009D2B
0x180009cc2  mov     rax, [rdi+20h]
0x180009cc6  xor     edx, edx
0x180009cc8  sub     rax, [rdi+18h]
0x180009ccc  mov     rsi, rbx
0x180009ccf  div     qword ptr [rdi+10h]
0x180009cd3  mov     edx, [rbp+47h+Source]
0x180009cd6  cmp     rdx, rax
0x180009cd9  jbe     short loc_180009D1C
0x180009cdb  cmp     edx, eax
0x180009cdd  jz      short loc_180009D1C
0x180009cdf  mov     edx, eax
0x180009ce1  mov     [rbp+47h+Source], eax
0x180009ce4  mov     al, [rbp+47h+var_9E]
0x180009ce7  cmp     al, 1
0x180009ce9  jnz     short loc_180009CFE
0x180009ceb  movzx   eax, dx
0x180009cee  mov     [rbp+47h+var_B0], dx
0x180009cf2  mov     r9d, 2
0x180009cf8  lea     r8, [rbp+47h+var_B0]
0x180009cfc  jmp     short loc_180009D0C
0x180009cfe  cmp     al, 2
0x180009d00  jnz     short loc_180009D1C
0x180009d02  mov     r9d, 4; SourceSize
0x180009d08  lea     r8, [rbp+47h+Source]; Source
0x180009d0c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180009d10  mov     rdx, r9; DestinationSize
0x180009d13  call    cs:__imp_memcpy_s
0x180009d19  mov     edx, [rbp+47h+Source]
0x180009d1c  mov     ebx, edx
0x180009d1e  imul    rbx, [rdi+10h]
0x180009d23  add     rbx, rsi
0x180009d26  jmp     loc_180009DB2
0x180009d2b  movzx   eax, word ptr [rdi+6]
0x180009d2f  xorps   xmm0, xmm0
0x180009d32  mov     [rbp+47h+var_60], ax
0x180009d36  mov     esi, r9d
0x180009d39  mov     al, [rdi+8]
0x180009d3c  mov     [rbp+47h+var_5E], al
0x180009d3f  mov     eax, [rbp+47h+Source]
0x180009d42  mov     [rbp+47h+var_5C], r9d
0x180009d46  mov     [rbp+47h+var_58], r9w
0x180009d4b  movdqu  [rbp+47h+var_50], xmm0
0x180009d50  test    eax, eax
0x180009d52  jz      short loc_180009D76
0x180009d54  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009d58  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180009d5c  lea     rcx, [rbp+47h+var_60]; this
0x180009d60  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009d65  test    al, al
0x180009d67  mov     eax, [rbp+47h+Source]
0x180009d6a  jz      short loc_180009D72
0x180009d6c  inc     esi
0x180009d6e  cmp     esi, eax
0x180009d70  jb      short loc_180009D54
0x180009d72  mov     rbx, [rbp+47h+var_A8]
0x180009d76  cmp     eax, esi
0x180009d78  jz      short loc_180009DB2
0x180009d7a  mov     al, [rbp+47h+var_9E]
0x180009d7d  mov     [rbp+47h+Source], esi
0x180009d80  cmp     al, 1
0x180009d82  jnz     short loc_180009D98
0x180009d84  mov     eax, 2
0x180009d89  mov     [rbp+47h+var_B0], si
0x180009d8d  mov     r9d, eax
0x180009d90  lea     r8, [rbp+47h+var_B0]
0x180009d94  mov     edx, eax
0x180009d96  jmp     short loc_180009DA8
0x180009d98  cmp     al, 2
0x180009d9a  jnz     short loc_180009DB2
0x180009d9c  mov     edx, 4; DestinationSize
0x180009da1  lea     r8, [rbp+47h+Source]; Source
0x180009da5  mov     r9d, edx; SourceSize
0x180009da8  mov     rcx, [rbp+47h+Buf2]; Destination
0x180009dac  call    cs:__imp_memcpy_s
0x180009db2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009db6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180009dba  lea     rcx, [rbp+47h+var_A0]; this
0x180009dbe  mov     [rbp+47h+var_A8], rbx
0x180009dc2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009dc7  xor     r9d, r9d
0x180009dca  mov     sil, al
0x180009dcd  test    al, al
0x180009dcf  jnz     loc_180009C7E
0x180009dd5  mov     rbx, [rbp+47h+var_A8]
0x180009dd9  mov     [rdi+20h], rbx
0x180009ddd  mov     rcx, r9
0x180009de0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180009de4  jnz     loc_180009E6F
0x180009dea  movzx   eax, [rbp+47h+var_A0]
0x180009dee  mov     [rbp+47h+Source], 1
0x180009df5  mov     [rbp+47h+var_98], r14w
0x180009dfa  mov     [rbp+47h+Buf2], r9
0x180009dfe  mov     [rbp+47h+Buf2+8], r15
0x180009e02  test    ax, ax
0x180009e05  jnz     short loc_180009E57
0x180009e07  movzx   ecx, r14w
0x180009e0b  add     rcx, 2
0x180009e0f  jmp     short loc_180009E5A
0x180009e11  mov     eax, [rbp+47h+arg_28]
0x180009e14  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180009e18  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180009e1c  mov     r9, r13; void *
0x180009e1f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180009e23  mov     rcx, rdi; this
0x180009e26  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180009e2b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180009e30  xor     r9d, r9d
0x180009e33  mov     [rbp+47h+var_A8], rax
0x180009e37  mov     rbx, rax
0x180009e3a  test    rax, rax
0x180009e3d  jnz     short loc_180009E46
0x180009e3f  mov     al, 1
0x180009e41  jmp     loc_180009F74
0x180009e46  mov     byte ptr [rbp+47h+arg_0], 1
0x180009e4a  jmp     short loc_180009E50
0x180009e4c  mov     [rbp+47h+var_A8], rbx
0x180009e50  test    sil, sil
0x180009e53  jnz     short loc_180009DDD
0x180009e55  jmp     short loc_180009DD9
0x180009e57  mov     rcx, rax
0x180009e5a  mov     al, [rbp+47h+var_9E]
0x180009e5d  cmp     al, 1
0x180009e5f  jnz     short loc_180009E67
0x180009e61  add     rcx, 2
0x180009e65  jmp     short loc_180009E6F
0x180009e67  cmp     al, 2
0x180009e69  jnz     short loc_180009E6F
0x180009e6b  add     rcx, 4
0x180009e6f  movzx   eax, word ptr [rdi+6]
0x180009e73  mov     dl, [rdi+8]
0x180009e76  mov     r8d, [rbp+47h+arg_28]
0x180009e7a  mov     [rbp+47h+var_80], ax
0x180009e7e  mov     [rbp+47h+var_7E], dl
0x180009e81  mov     [rbp+47h+var_7C], r8d
0x180009e85  mov     [rbp+47h+var_78], r12w
0x180009e8a  mov     [rbp+47h+var_70], r9
0x180009e8e  mov     [rbp+47h+var_68], r13
0x180009e92  test    ax, ax
0x180009e95  jnz     short loc_180009E9F
0x180009e97  movzx   eax, r12w
0x180009e9b  add     rax, 2
0x180009e9f  cmp     dl, 1
0x180009ea2  jnz     short loc_180009EAA
0x180009ea4  add     rax, 2
0x180009ea8  jmp     short loc_180009EB3
0x180009eaa  cmp     dl, 2
0x180009ead  jnz     short loc_180009EB3
0x180009eaf  add     rax, 4
0x180009eb3  mov     rdx, [rdi+28h]
0x180009eb7  lea     rsi, [rax+rcx]
0x180009ebb  mov     r9, [rdi+20h]
0x180009ebf  mov     rcx, rdx
0x180009ec2  sub     rcx, r9
0x180009ec5  cmp     r9, rdx
0x180009ec8  sbb     rax, rax
0x180009ecb  and     rax, rcx
0x180009ece  cmp     rax, rsi
0x180009ed1  jb      loc_180009F72
0x180009ed7  sub     rdx, rsi
0x180009eda  lea     rcx, [rsi+rbx]; Destination
0x180009ede  sub     rdx, rbx; DestinationSize
0x180009ee1  sub     r9, rbx; SourceSize
0x180009ee4  mov     r8, rbx; Source
0x180009ee7  call    cs:__imp_memmove_s
0x180009eed  add     [rdi+20h], rsi
0x180009ef1  xor     ebx, ebx
0x180009ef3  cmp     byte ptr [rbp+47h+arg_0], bl
0x180009ef6  jnz     short loc_180009F0B
0x180009ef8  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009efc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180009f00  lea     rcx, [rbp+47h+var_A0]; this
0x180009f04  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009f09  jmp     short loc_180009F58
0x180009f0b  mov     cl, [rbp+47h+var_9E]
0x180009f0e  test    cl, cl
0x180009f10  jz      short loc_180009F58
0x180009f12  mov     eax, [rbp+47h+Source]
0x180009f15  lea     r8d, [rax+1]
0x180009f19  cmp     eax, r8d
0x180009f1c  jz      short loc_180009F58
0x180009f1e  mov     [rbp+47h+Source], r8d
0x180009f22  cmp     cl, 1
0x180009f25  jnz     short loc_180009F3B
0x180009f27  mov     r9d, 2
0x180009f2d  mov     [rbp+47h+arg_0], r8w
0x180009f32  mov     edx, r9d
0x180009f35  lea     r8, [rbp+47h+arg_0]
0x180009f39  jmp     short loc_180009F4E
0x180009f3b  cmp     cl, 2
0x180009f3e  jnz     short loc_180009F58
0x180009f40  mov     eax, 4
0x180009f45  lea     r8, [rbp+47h+Source]; Source
0x180009f49  mov     r9d, eax; SourceSize
0x180009f4c  mov     edx, eax; DestinationSize
0x180009f4e  mov     rcx, [rbp+47h+Buf2]; Destination
0x180009f52  call    cs:__imp_memcpy_s
0x180009f58  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009f5c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180009f60  lea     rcx, [rbp+47h+var_80]; this
0x180009f64  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009f69  mov     byte ptr [rdi+38h], 1
0x180009f6d  jmp     loc_180009E3F
0x180009f72  xor     al, al
0x180009f74  add     rsp, 0A8h
0x180009f7b  pop     r15
0x180009f7d  pop     r14
0x180009f7f  pop     r13
0x180009f81  pop     r12
0x180009f83  pop     rdi
0x180009f84  pop     rsi
0x180009f85  pop     rbx
0x180009f86  pop     rbp
0x180009f87  retn
```
