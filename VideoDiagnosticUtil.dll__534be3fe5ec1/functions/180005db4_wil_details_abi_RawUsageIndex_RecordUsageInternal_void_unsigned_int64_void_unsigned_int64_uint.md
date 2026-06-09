# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005db4`
- end: `0x18000614d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x180003e88`
- `0x18000572c`
- `0x180005db4`
- `0x180007774`
- `0x180009666`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000609f`
- `msvcrt!memmove_s` at `0x18000609f`
- `msvcrt!memcpy_s` at `0x180005ebf`
- `msvcrt!memcpy_s` at `0x180005f5e`
- `msvcrt!memcpy_s` at `0x180006110`
- `msvcrt!memcpy_s` at `0x180005ebf`
- `msvcrt!memcpy_s` at `0x180005f5e`
- `msvcrt!memcpy_s` at `0x180006110`

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
0x180005db4  push    rbp
0x180005db6  push    rbx
0x180005db7  push    rsi
0x180005db8  push    rdi
0x180005db9  push    r12
0x180005dbb  push    r13
0x180005dbd  push    r14
0x180005dbf  push    r15
0x180005dc1  lea     rbp, [rsp-0Fh]
0x180005dc6  sub     rsp, 0A8h
0x180005dcd  mov     rbx, [rcx+18h]
0x180005dd1  mov     rdi, rcx
0x180005dd4  xor     ecx, ecx
0x180005dd6  mov     r13, r9
0x180005dd9  mov     r14, r8
0x180005ddc  mov     r15, rdx
0x180005ddf  test    rbx, rbx
0x180005de2  jz      loc_180006136
0x180005de8  movzx   eax, word ptr [rdi+2]
0x180005dec  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180005df0  mov     r8, [rdi+20h]; unsigned __int8 *
0x180005df4  add     rbx, 0Ah
0x180005df8  mov     [rbp+47h+var_A0], ax
0x180005dfc  xorps   xmm0, xmm0
0x180005dff  mov     al, [rdi+4]
0x180005e02  mov     [rbp+47h+Source], ecx
0x180005e05  mov     [rbp+47h+var_98], cx
0x180005e09  mov     byte ptr [rbp+47h+arg_0], cl
0x180005e0c  lea     rcx, [rbp+47h+var_A0]; this
0x180005e10  mov     [rbp+47h+var_9E], al
0x180005e13  mov     [rbp+47h+var_A8], rbx
0x180005e17  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180005e1c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180005e21  mov     r12, [rbp+47h+arg_20]
0x180005e25  jmp     loc_180005F7F
0x180005e2a  movzx   eax, [rbp+47h+var_98]
0x180005e2e  cmp     r14, rax
0x180005e31  jnz     short loc_180005E49
0x180005e33  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180005e37  mov     r8, r14; Size
0x180005e3a  mov     rcx, r15; Buf1
0x180005e3d  call    memcmp_0
0x180005e42  mov     ecx, eax
0x180005e44  xor     r9d, r9d
0x180005e47  jmp     short loc_180005E52
0x180005e49  movzx   eax, [rbp+47h+var_98]
0x180005e4d  mov     ecx, r14d
0x180005e50  sub     ecx, eax
0x180005e52  test    ecx, ecx
0x180005e54  js      loc_180006004
0x180005e5a  jz      loc_180005FC9
0x180005e60  mov     rbx, [rbp+47h+var_A8]
0x180005e64  mov     [rbp+47h+var_A8], rbx
0x180005e68  cmp     [rdi+10h], r9
0x180005e6c  jbe     short loc_180005EDD
0x180005e6e  mov     rax, [rdi+20h]
0x180005e72  xor     edx, edx
0x180005e74  sub     rax, [rdi+18h]
0x180005e78  mov     rsi, rbx
0x180005e7b  div     qword ptr [rdi+10h]
0x180005e7f  mov     edx, [rbp+47h+Source]
0x180005e82  cmp     rdx, rax
0x180005e85  jbe     short loc_180005ECE
0x180005e87  cmp     edx, eax
0x180005e89  jz      short loc_180005ECE
0x180005e8b  mov     edx, eax
0x180005e8d  mov     [rbp+47h+Source], eax
0x180005e90  mov     al, [rbp+47h+var_9E]
0x180005e93  cmp     al, 1
0x180005e95  jnz     short loc_180005EAA
0x180005e97  movzx   eax, dx
0x180005e9a  mov     [rbp+47h+var_B0], dx
0x180005e9e  mov     r9d, 2
0x180005ea4  lea     r8, [rbp+47h+var_B0]
0x180005ea8  jmp     short loc_180005EB8
0x180005eaa  cmp     al, 2
0x180005eac  jnz     short loc_180005ECE
0x180005eae  mov     r9d, 4; SourceSize
0x180005eb4  lea     r8, [rbp+47h+Source]; Source
0x180005eb8  mov     rcx, [rbp+47h+Buf2]; Destination
0x180005ebc  mov     rdx, r9; DestinationSize
0x180005ebf  call    cs:__imp_memcpy_s
0x180005ec6  nop     dword ptr [rax+rax+00h]
0x180005ecb  mov     edx, [rbp+47h+Source]
0x180005ece  mov     ebx, edx
0x180005ed0  imul    rbx, [rdi+10h]
0x180005ed5  add     rbx, rsi
0x180005ed8  jmp     loc_180005F6A
0x180005edd  movzx   eax, word ptr [rdi+6]
0x180005ee1  xorps   xmm0, xmm0
0x180005ee4  mov     [rbp+47h+var_60], ax
0x180005ee8  mov     esi, r9d
0x180005eeb  mov     al, [rdi+8]
0x180005eee  mov     [rbp+47h+var_5E], al
0x180005ef1  mov     eax, [rbp+47h+Source]
0x180005ef4  mov     [rbp+47h+var_5C], r9d
0x180005ef8  mov     [rbp+47h+var_58], r9w
0x180005efd  movdqu  [rbp+47h+var_50], xmm0
0x180005f02  test    eax, eax
0x180005f04  jz      short loc_180005F28
0x180005f06  mov     r8, [rdi+20h]; unsigned __int8 *
0x180005f0a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180005f0e  lea     rcx, [rbp+47h+var_60]; this
0x180005f12  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180005f17  test    al, al
0x180005f19  mov     eax, [rbp+47h+Source]
0x180005f1c  jz      short loc_180005F24
0x180005f1e  inc     esi
0x180005f20  cmp     esi, eax
0x180005f22  jb      short loc_180005F06
0x180005f24  mov     rbx, [rbp+47h+var_A8]
0x180005f28  cmp     eax, esi
0x180005f2a  jz      short loc_180005F6A
0x180005f2c  mov     al, [rbp+47h+var_9E]
0x180005f2f  mov     [rbp+47h+Source], esi
0x180005f32  cmp     al, 1
0x180005f34  jnz     short loc_180005F4A
0x180005f36  mov     eax, 2
0x180005f3b  mov     [rbp+47h+var_B0], si
0x180005f3f  mov     r9d, eax
0x180005f42  lea     r8, [rbp+47h+var_B0]
0x180005f46  mov     edx, eax
0x180005f48  jmp     short loc_180005F5A
0x180005f4a  cmp     al, 2
0x180005f4c  jnz     short loc_180005F6A
0x180005f4e  mov     edx, 4; DestinationSize
0x180005f53  lea     r8, [rbp+47h+Source]; Source
0x180005f57  mov     r9d, edx; SourceSize
0x180005f5a  mov     rcx, [rbp+47h+Buf2]; Destination
0x180005f5e  call    cs:__imp_memcpy_s
0x180005f65  nop     dword ptr [rax+rax+00h]
0x180005f6a  mov     r8, [rdi+20h]; unsigned __int8 *
0x180005f6e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180005f72  lea     rcx, [rbp+47h+var_A0]; this
0x180005f76  mov     [rbp+47h+var_A8], rbx
0x180005f7a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180005f7f  xor     r9d, r9d
0x180005f82  mov     sil, al
0x180005f85  test    al, al
0x180005f87  jnz     loc_180005E2A
0x180005f8d  mov     rbx, [rbp+47h+var_A8]
0x180005f91  mov     [rdi+20h], rbx
0x180005f95  mov     rcx, r9
0x180005f98  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180005f9c  jnz     loc_180006027
0x180005fa2  movzx   eax, [rbp+47h+var_A0]
0x180005fa6  mov     [rbp+47h+Source], 1
0x180005fad  mov     [rbp+47h+var_98], r14w
0x180005fb2  mov     [rbp+47h+Buf2], r9
0x180005fb6  mov     [rbp+47h+Buf2+8], r15
0x180005fba  test    ax, ax
0x180005fbd  jnz     short loc_18000600F
0x180005fbf  movzx   ecx, r14w
0x180005fc3  add     rcx, 2
0x180005fc7  jmp     short loc_180006012
0x180005fc9  mov     eax, [rbp+47h+arg_28]
0x180005fcc  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180005fd0  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180005fd4  mov     r9, r13; void *
0x180005fd7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180005fdb  mov     rcx, rdi; this
0x180005fde  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180005fe3  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180005fe8  xor     r9d, r9d
0x180005feb  mov     [rbp+47h+var_A8], rax
0x180005fef  mov     rbx, rax
0x180005ff2  test    rax, rax
0x180005ff5  jnz     short loc_180005FFE
0x180005ff7  mov     al, 1
0x180005ff9  jmp     loc_180006138
0x180005ffe  mov     byte ptr [rbp+47h+arg_0], 1
0x180006002  jmp     short loc_180006008
0x180006004  mov     [rbp+47h+var_A8], rbx
0x180006008  test    sil, sil
0x18000600b  jnz     short loc_180005F95
0x18000600d  jmp     short loc_180005F91
0x18000600f  mov     rcx, rax
0x180006012  mov     al, [rbp+47h+var_9E]
0x180006015  cmp     al, 1
0x180006017  jnz     short loc_18000601F
0x180006019  add     rcx, 2
0x18000601d  jmp     short loc_180006027
0x18000601f  cmp     al, 2
0x180006021  jnz     short loc_180006027
0x180006023  add     rcx, 4
0x180006027  movzx   eax, word ptr [rdi+6]
0x18000602b  mov     dl, [rdi+8]
0x18000602e  mov     r8d, [rbp+47h+arg_28]
0x180006032  mov     [rbp+47h+var_80], ax
0x180006036  mov     [rbp+47h+var_7E], dl
0x180006039  mov     [rbp+47h+var_7C], r8d
0x18000603d  mov     [rbp+47h+var_78], r12w
0x180006042  mov     [rbp+47h+var_70], r9
0x180006046  mov     [rbp+47h+var_68], r13
0x18000604a  test    ax, ax
0x18000604d  jnz     short loc_180006057
0x18000604f  movzx   eax, r12w
0x180006053  add     rax, 2
0x180006057  cmp     dl, 1
0x18000605a  jnz     short loc_180006062
0x18000605c  add     rax, 2
0x180006060  jmp     short loc_18000606B
0x180006062  cmp     dl, 2
0x180006065  jnz     short loc_18000606B
0x180006067  add     rax, 4
0x18000606b  mov     rdx, [rdi+28h]
0x18000606f  lea     rsi, [rax+rcx]
0x180006073  mov     r9, [rdi+20h]
0x180006077  mov     rcx, rdx
0x18000607a  sub     rcx, r9
0x18000607d  cmp     r9, rdx
0x180006080  sbb     rax, rax
0x180006083  and     rax, rcx
0x180006086  cmp     rax, rsi
0x180006089  jb      loc_180006136
0x18000608f  sub     rdx, rsi
0x180006092  lea     rcx, [rsi+rbx]; Destination
0x180006096  sub     rdx, rbx; DestinationSize
0x180006099  sub     r9, rbx; SourceSize
0x18000609c  mov     r8, rbx; Source
0x18000609f  call    cs:__imp_memmove_s
0x1800060a6  nop     dword ptr [rax+rax+00h]
0x1800060ab  add     [rdi+20h], rsi
0x1800060af  xor     ebx, ebx
0x1800060b1  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800060b4  jnz     short loc_1800060C9
0x1800060b6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800060ba  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800060be  lea     rcx, [rbp+47h+var_A0]; this
0x1800060c2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800060c7  jmp     short loc_18000611C
0x1800060c9  mov     cl, [rbp+47h+var_9E]
0x1800060cc  test    cl, cl
0x1800060ce  jz      short loc_18000611C
0x1800060d0  mov     eax, [rbp+47h+Source]
0x1800060d3  lea     r8d, [rax+1]
0x1800060d7  cmp     eax, r8d
0x1800060da  jz      short loc_18000611C
0x1800060dc  mov     [rbp+47h+Source], r8d
0x1800060e0  cmp     cl, 1
0x1800060e3  jnz     short loc_1800060F9
0x1800060e5  mov     r9d, 2
0x1800060eb  mov     [rbp+47h+arg_0], r8w
0x1800060f0  mov     edx, r9d
0x1800060f3  lea     r8, [rbp+47h+arg_0]
0x1800060f7  jmp     short loc_18000610C
0x1800060f9  cmp     cl, 2
0x1800060fc  jnz     short loc_18000611C
0x1800060fe  mov     eax, 4
0x180006103  lea     r8, [rbp+47h+Source]; Source
0x180006107  mov     r9d, eax; SourceSize
0x18000610a  mov     edx, eax; DestinationSize
0x18000610c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006110  call    cs:__imp_memcpy_s
0x180006117  nop     dword ptr [rax+rax+00h]
0x18000611c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006120  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006124  lea     rcx, [rbp+47h+var_80]; this
0x180006128  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000612d  mov     byte ptr [rdi+38h], 1
0x180006131  jmp     loc_180005FF7
0x180006136  xor     al, al
0x180006138  add     rsp, 0A8h
0x18000613f  pop     r15
0x180006141  pop     r14
0x180006143  pop     r13
0x180006145  pop     r12
0x180006147  pop     rdi
0x180006148  pop     rsi
0x180006149  pop     rbx
0x18000614a  pop     rbp
0x18000614b  retn
```
