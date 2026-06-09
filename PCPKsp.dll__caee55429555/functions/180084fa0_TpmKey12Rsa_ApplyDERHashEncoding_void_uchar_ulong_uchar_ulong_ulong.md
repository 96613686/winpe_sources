# TpmKey12Rsa::ApplyDERHashEncoding(void *,uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x180084fa0`
- end: `0x1800852f5`
- name: `?ApplyDERHashEncoding@TpmKey12Rsa@@IEAAJPEAXPEAEK1KPEAK@Z`
- size: `853`
- prototype: `int(TpmKey12Rsa *__hidden this, void *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180071b50`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x180029260`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`
- `0x180084fa0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180085060`
- `bcrypt!BCryptGetProperty` at `0x1800850e9`
- `bcrypt!BCryptGetProperty` at `0x180085195`
- `bcrypt!BCryptGetProperty` at `0x180085060`
- `bcrypt!BCryptGetProperty` at `0x1800850e9`
- `bcrypt!BCryptGetProperty` at `0x180085195`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800852bd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800852bd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180085021`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180085021`

## pseudocode

```c
__int64 __fastcall TpmKey12Rsa::ApplyDERHashEncoding(
        TpmKey12Rsa *this,
        LPCWSTR *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  rsize_t v8; // r14
  unsigned int v10; // edi
  unsigned __int8 *v11; // rsi
  NTSTATUS Property; // eax
  int v13; // ecx
  NTSTATUS v14; // eax
  int v15; // ecx
  UCHAR *v16; // rax
  UCHAR *v17; // rbx
  NTSTATUS v18; // eax
  const struct std::nothrow_t *v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  UCHAR *v22; // rcx
  unsigned int v23; // ebx
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-28h] BYREF
  int *v27[4]; // [rsp+40h] [rbp-20h] BYREF
  int v28; // [rsp+90h] [rbp+30h] BYREF
  int v29; // [rsp+94h] [rbp+34h]
  ULONG cbOutput; // [rsp+98h] [rbp+38h] BYREF

  v29 = HIDWORD(this);
  v8 = a4;
  v28 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v27, L"TpmKey12Rsa::ApplyDERHashEncoding", &v28);
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( !a2 )
    goto LABEL_46;
  if ( !*a2 )
    goto LABEL_46;
  v10 = a6;
  v11 = a5;
  if ( a6 )
  {
    if ( !a5 )
      goto LABEL_46;
  }
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, *a2, 0, 0) < 0 )
  {
    v28 = -2144795643;
    goto LABEL_47;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  if ( Property )
  {
    if ( (Property & 0xFFFF000) == 0x290000 )
    {
      v13 = Property & 0xFFF | 0x80280000;
    }
    else if ( (Property & 0xFFF0000) == 0x70000 )
    {
      v13 = (unsigned __int16)Property;
      if ( (_WORD)Property )
        v13 = (unsigned __int16)Property | 0x80070000;
    }
    else
    {
      v13 = Property | 0x10000000;
    }
    v28 = v13;
    if ( v13 < 0 )
      goto LABEL_47;
  }
  else
  {
    v28 = 0;
  }
  if ( *(_DWORD *)pbOutput != (_DWORD)v8 )
  {
LABEL_46:
    v28 = -2144795645;
    goto LABEL_47;
  }
  v14 = BCryptGetProperty(phAlgorithm, L"HashOIDList", 0, 0, &cbOutput, 0);
  if ( !v14 )
  {
    v28 = 0;
    goto LABEL_26;
  }
  if ( (v14 & 0xFFFF000) == 0x290000 )
  {
    v15 = v14 & 0xFFF | 0x80280000;
  }
  else if ( (v14 & 0xFFF0000) == 0x70000 )
  {
    v15 = (unsigned __int16)v14;
    if ( (_WORD)v14 )
      v15 = (unsigned __int16)v14 | 0x80070000;
  }
  else
  {
    v15 = v14 | 0x10000000;
  }
  v28 = v15;
  if ( v15 >= 0 )
  {
LABEL_26:
    v16 = (UCHAR *)operator new[](cbOutput, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( !v16 )
    {
      v28 = -2147024888;
      goto LABEL_47;
    }
    memset_0(v16, 0, cbOutput);
    v18 = BCryptGetProperty(phAlgorithm, L"HashOIDList", v17, cbOutput, &cbOutput, 0);
    if ( v18 )
    {
      if ( (v18 & 0xFFFF000) == 0x290000 )
      {
        v20 = v18 & 0xFFF | 0x80280000;
      }
      else if ( (v18 & 0xFFF0000) == 0x70000 )
      {
        v20 = (unsigned __int16)v18;
        if ( (_WORD)v18 )
          v20 = (unsigned __int16)v18 | 0x80070000;
      }
      else
      {
        v20 = v18 | 0x10000000;
      }
      v28 = v20;
      if ( v20 < 0 )
        goto LABEL_43;
    }
    else
    {
      v28 = 0;
    }
    if ( *(_DWORD *)v17 )
    {
      v19 = (const struct std::nothrow_t *)(unsigned int)(v8 + **((_DWORD **)v17 + 1) + 6);
      *a7 = (unsigned int)v19;
      if ( v10 )
      {
        if ( v10 >= (unsigned int)v19 )
        {
          *v11 = 48;
          v11[1] = (_BYTE)v19 - 2;
          v11[2] = 48;
          v11[3] = **((_BYTE **)v17 + 1);
          memcpy_s(v11 + 4, v10 - 4, *(const void *const *)(*((_QWORD *)v17 + 1) + 8LL), **((unsigned int **)v17 + 1));
          v11[**((_DWORD **)v17 + 1) + 4] = 4;
          v11[**((_DWORD **)v17 + 1) + 5] = v8;
          memcpy_s(&v11[**((_DWORD **)v17 + 1) + 6], v10 - **((_DWORD **)v17 + 1) - 6, a3, v8);
        }
        else
        {
          v28 = -2146893784;
        }
      }
    }
    else
    {
      v28 = -2146893779;
    }
LABEL_43:
    v21 = cbOutput;
    v22 = v17;
    if ( cbOutput )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    operator delete(v17, v19);
  }
LABEL_47:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  v23 = v28;
  KspFunctionLogger::~KspFunctionLogger(v27);
  return v23;
}

```

## disassembly

```asm
0x180084fa0  mov     [rsp-28h+arg_10], rbx
0x180084fa5  mov     [rsp-28h+arg_18], rsi
0x180084faa  mov     qword ptr [rsp-28h+arg_0], rcx
0x180084faf  push    rbp
0x180084fb0  push    rdi
0x180084fb1  push    r12
0x180084fb3  push    r14
0x180084fb5  push    r15
0x180084fb7  mov     rbp, rsp
0x180084fba  sub     rsp, 60h
0x180084fbe  mov     r15, r8
0x180084fc1  mov     r14d, r9d
0x180084fc4  mov     rbx, rdx
0x180084fc7  lea     r8, [rbp+arg_0]; int *
0x180084fcb  xor     r12d, r12d
0x180084fce  lea     rdx, aTpmkey12rsaApp; "TpmKey12Rsa::ApplyDERHashEncoding"
0x180084fd5  lea     rcx, [rbp+var_20]; this
0x180084fd9  mov     [rbp+arg_0], r12d
0x180084fdd  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180084fe2  mov     [rbp+phAlgorithm], r12
0x180084fe6  mov     dword ptr [rbp+pbOutput], r12d
0x180084fea  mov     [rbp+cbOutput], r12d
0x180084fee  test    rbx, rbx
0x180084ff1  jz      loc_1800852AB
0x180084ff7  mov     rdx, [rbx]; pszAlgId
0x180084ffa  test    rdx, rdx
0x180084ffd  jz      loc_1800852AB
0x180085003  mov     edi, [rbp+arg_28]
0x180085006  mov     rsi, [rbp+arg_20]
0x18008500a  test    edi, edi
0x18008500c  jz      short loc_180085017
0x18008500e  test    rsi, rsi
0x180085011  jz      loc_1800852AB
0x180085017  xor     r9d, r9d; dwFlags
0x18008501a  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18008501e  xor     r8d, r8d; pszImplementation
0x180085021  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180085028  nop     dword ptr [rax+rax+00h]
0x18008502d  test    eax, eax
0x18008502f  jns     short loc_18008503D
0x180085031  mov     [rbp+arg_0], 80290405h
0x180085038  jmp     loc_1800852B2
0x18008503d  mov     rcx, [rbp+phAlgorithm]; hObject
0x180085041  lea     rax, [rbp+cbOutput]
0x180085045  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x18008504a  lea     r8, [rbp+pbOutput]; pbOutput
0x18008504e  mov     r9d, 4; cbOutput
0x180085054  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180085059  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180085060  call    cs:__imp_BCryptGetProperty
0x180085067  nop     dword ptr [rax+rax+00h]
0x18008506c  mov     ecx, eax
0x18008506e  mov     ebx, 70000h
0x180085073  test    eax, eax
0x180085075  jnz     short loc_18008507D
0x180085077  mov     [rbp+arg_0], r12d
0x18008507b  jmp     short loc_1800850C0
0x18008507d  and     eax, 0FFFF000h
0x180085082  cmp     eax, 290000h
0x180085087  jnz     short loc_180085097
0x180085089  and     ecx, 0FFFh
0x18008508f  or      ecx, 80280000h
0x180085095  jmp     short loc_1800850B5
0x180085097  mov     eax, ecx
0x180085099  and     eax, 0FFF0000h
0x18008509e  cmp     eax, ebx
0x1800850a0  jnz     short loc_1800850B1
0x1800850a2  movzx   ecx, cx
0x1800850a5  test    ecx, ecx
0x1800850a7  jz      short loc_1800850B5
0x1800850a9  or      ecx, 80070000h
0x1800850af  jmp     short loc_1800850B5
0x1800850b1  bts     ecx, 1Ch
0x1800850b5  mov     [rbp+arg_0], ecx
0x1800850b8  test    ecx, ecx
0x1800850ba  js      loc_1800852B2
0x1800850c0  cmp     dword ptr [rbp+pbOutput], r14d
0x1800850c4  jnz     loc_1800852AB
0x1800850ca  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800850ce  lea     rax, [rbp+cbOutput]
0x1800850d2  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x1800850d7  lea     rdx, aHashoidlist; "HashOIDList"
0x1800850de  xor     r9d, r9d; cbOutput
0x1800850e1  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800850e6  xor     r8d, r8d; pbOutput
0x1800850e9  call    cs:__imp_BCryptGetProperty
0x1800850f0  nop     dword ptr [rax+rax+00h]
0x1800850f5  mov     ecx, eax
0x1800850f7  test    eax, eax
0x1800850f9  jnz     short loc_180085101
0x1800850fb  mov     [rbp+arg_0], r12d
0x1800850ff  jmp     short loc_180085144
0x180085101  and     eax, 0FFFF000h
0x180085106  cmp     eax, 290000h
0x18008510b  jnz     short loc_18008511B
0x18008510d  and     ecx, 0FFFh
0x180085113  or      ecx, 80280000h
0x180085119  jmp     short loc_180085139
0x18008511b  mov     eax, ecx
0x18008511d  and     eax, 0FFF0000h
0x180085122  cmp     eax, ebx
0x180085124  jnz     short loc_180085135
0x180085126  movzx   ecx, cx
0x180085129  test    ecx, ecx
0x18008512b  jz      short loc_180085139
0x18008512d  or      ecx, 80070000h
0x180085133  jmp     short loc_180085139
0x180085135  bts     ecx, 1Ch
0x180085139  mov     [rbp+arg_0], ecx
0x18008513c  test    ecx, ecx
0x18008513e  js      loc_1800852B2
0x180085144  mov     ecx, [rbp+cbOutput]; unsigned __int64
0x180085147  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008514e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180085153  mov     rbx, rax
0x180085156  test    rax, rax
0x180085159  jnz     short loc_180085167
0x18008515b  mov     [rbp+arg_0], 80070008h
0x180085162  jmp     loc_1800852B2
0x180085167  mov     r8d, [rbp+cbOutput]; Size
0x18008516b  xor     edx, edx; Val
0x18008516d  mov     rcx, rbx; void *
0x180085170  call    memset_0
0x180085175  mov     r9d, [rbp+cbOutput]; cbOutput
0x180085179  lea     rax, [rbp+cbOutput]
0x18008517d  mov     rcx, [rbp+phAlgorithm]; hObject
0x180085181  lea     rdx, aHashoidlist; "HashOIDList"
0x180085188  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x18008518d  mov     r8, rbx; pbOutput
0x180085190  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180085195  call    cs:__imp_BCryptGetProperty
0x18008519c  nop     dword ptr [rax+rax+00h]
0x1800851a1  mov     ecx, eax
0x1800851a3  test    eax, eax
0x1800851a5  jnz     short loc_1800851AD
0x1800851a7  mov     [rbp+arg_0], r12d
0x1800851ab  jmp     short loc_1800851F3
0x1800851ad  and     eax, 0FFFF000h
0x1800851b2  cmp     eax, 290000h
0x1800851b7  jnz     short loc_1800851C7
0x1800851b9  and     ecx, 0FFFh
0x1800851bf  or      ecx, 80280000h
0x1800851c5  jmp     short loc_1800851E8
0x1800851c7  mov     eax, ecx
0x1800851c9  and     eax, 0FFF0000h
0x1800851ce  cmp     eax, 70000h
0x1800851d3  jnz     short loc_1800851E4
0x1800851d5  movzx   ecx, cx
0x1800851d8  test    ecx, ecx
0x1800851da  jz      short loc_1800851E8
0x1800851dc  or      ecx, 80070000h
0x1800851e2  jmp     short loc_1800851E8
0x1800851e4  bts     ecx, 1Ch
0x1800851e8  mov     [rbp+arg_0], ecx
0x1800851eb  test    ecx, ecx
0x1800851ed  js      loc_18008528A
0x1800851f3  cmp     [rbx], r12d
0x1800851f6  jnz     short loc_180085204
0x1800851f8  mov     [rbp+arg_0], 8009002Dh
0x1800851ff  jmp     loc_18008528A
0x180085204  mov     rax, [rbx+8]
0x180085208  mov     edx, [rax]
0x18008520a  mov     rax, [rbp+arg_30]
0x18008520e  add     edx, 6
0x180085211  add     edx, r14d
0x180085214  mov     [rax], edx
0x180085216  test    edi, edi
0x180085218  jz      short loc_18008528A
0x18008521a  cmp     edi, edx
0x18008521c  jnb     short loc_180085227
0x18008521e  mov     [rbp+arg_0], 80090028h
0x180085225  jmp     short loc_18008528A
0x180085227  mov     byte ptr [rsi], 30h ; '0'
0x18008522a  sub     dl, 2
0x18008522d  mov     [rsi+1], dl
0x180085230  lea     edx, [rdi-4]; DestinationSize
0x180085233  mov     byte ptr [rsi+2], 30h ; '0'
0x180085237  mov     rax, [rbx+8]
0x18008523b  mov     cl, [rax]
0x18008523d  mov     [rsi+3], cl
0x180085240  lea     rcx, [rsi+4]; Destination
0x180085244  mov     r8, [rbx+8]
0x180085248  mov     r9d, [r8]; SourceSize
0x18008524b  mov     r8, [r8+8]; Source
0x18008524f  call    memcpy_s
0x180085254  mov     rax, [rbx+8]
0x180085258  mov     r9, r14; SourceSize
0x18008525b  mov     r8, r15; Source
0x18008525e  mov     ecx, [rax]
0x180085260  add     ecx, 4
0x180085263  mov     byte ptr [rcx+rsi], 4
0x180085267  mov     rax, [rbx+8]
0x18008526b  mov     ecx, [rax]
0x18008526d  add     ecx, 5
0x180085270  mov     [rcx+rsi], r14b
0x180085274  mov     rax, [rbx+8]
0x180085278  mov     eax, [rax]
0x18008527a  sub     edi, eax
0x18008527c  lea     ecx, [rax+6]
0x18008527f  add     rcx, rsi; Destination
0x180085282  lea     edx, [rdi-6]; DestinationSize
0x180085285  call    memcpy_s
0x18008528a  mov     eax, [rbp+cbOutput]
0x18008528d  mov     rcx, rbx
0x180085290  test    rax, rax
0x180085293  jz      short loc_1800852A1
0x180085295  mov     [rcx], r12b
0x180085298  inc     rcx
0x18008529b  sub     rax, 1
0x18008529f  jnz     short loc_180085295
0x1800852a1  mov     rcx, rbx; void *
0x1800852a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800852a9  jmp     short loc_1800852B2
0x1800852ab  mov     [rbp+arg_0], 80290403h
0x1800852b2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800852b6  test    rcx, rcx
0x1800852b9  jz      short loc_1800852CD
0x1800852bb  xor     edx, edx; dwFlags
0x1800852bd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800852c4  nop     dword ptr [rax+rax+00h]
0x1800852c9  mov     [rbp+phAlgorithm], r12
0x1800852cd  mov     ebx, [rbp+arg_0]
0x1800852d0  lea     rcx, [rbp+var_20]; this
0x1800852d4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800852d9  lea     r11, [rsp+60h+var_s0]
0x1800852de  mov     eax, ebx
0x1800852e0  mov     rbx, [r11+40h]
0x1800852e4  mov     rsi, [r11+48h]
0x1800852e8  mov     rsp, r11
0x1800852eb  pop     r15
0x1800852ed  pop     r14
0x1800852ef  pop     r12
0x1800852f1  pop     rdi
0x1800852f2  pop     rbp
0x1800852f3  retn
```
