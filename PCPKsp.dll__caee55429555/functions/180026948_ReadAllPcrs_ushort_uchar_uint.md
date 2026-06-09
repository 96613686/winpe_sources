# ReadAllPcrs(ushort,uchar *,uint)

- ea: `0x180026948`
- end: `0x180026b8a`
- name: `?ReadAllPcrs@@YAJGPEAEI@Z`
- size: `578`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180026830`
- `0x18002fd90`

## callees

- `0x180010c90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180026948`
- `0x18002c12c`
- `0x180031760`
- `0x180058d38`
- `0x18005cc84`
- `0x180061b6c`
- `0x180068fc0`
- `0x18006a710`

## string_xrefs

- `0x180026970`: `ReadAllPcrs`
- `0x180026b0d`: `PCR digest that was read is larger than the digest size should be for this algorithm.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ReadAllPcrs(unsigned __int16 a1, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // r12
  int v5; // ebx
  int Selections; // edi
  __int64 v7; // rdx
  unsigned int v8; // esi
  unsigned int v9; // r14d
  unsigned __int64 v10; // rdx
  __int64 v11; // r15
  __int64 i; // rbx
  int v14; // [rsp+20h] [rbp-E0h]
  const char *v15; // [rsp+28h] [rbp-D8h]
  _QWORD v16[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  __int64 v18; // [rsp+50h] [rbp-B0h]
  __int64 v19; // [rsp+58h] [rbp-A8h]
  char v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int *v22[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[248]; // [rsp+A0h] [rbp-60h] BYREF
  int v24; // [rsp+198h] [rbp+98h]
  __int64 v25; // [rsp+1A0h] [rbp+A0h]
  unsigned int v26; // [rsp+1F8h] [rbp+F8h]
  __int64 v27; // [rsp+200h] [rbp+100h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v3 = a3;
  v5 = a1;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v22, L"ReadAllPcrs", 1);
  switch ( v5 )
  {
    case 4:
      v8 = 20;
      break;
    case 11:
      v8 = 32;
      break;
    case 12:
      v8 = 48;
      break;
    case 13:
      v8 = 64;
      break;
    default:
      Selections = -2146893783;
      v7 = 697;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
        (const char *)(unsigned int)Selections,
        v14);
      goto LABEL_27;
  }
  if ( 24 * v8 > (unsigned int)v3 )
  {
    Selections = -2146893784;
    v7 = 700;
    goto LABEL_12;
  }
  v9 = 0;
  v16[1] = 0;
  v16[2] = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &tpm12class::TPMW8L_PCR_SELECTION::`vftable';
  tpm12class::TPMW8L_PCR_SELECTION::Clear((tpm12class::TPMW8L_PCR_SELECTION *)v16, 1u);
  Selections = tpm12class::TPMW8L_PCR_SELECTION::CreateSelections((tpm12class::TPMW8L_PCR_SELECTION *)v16, v10);
  if ( Selections >= 0 )
  {
    v11 = v21;
    *(_WORD *)(v21 + 56) = v5;
    *(_BYTE *)(v11 + 58) = 3;
LABEL_16:
    if ( v9 >= 3 )
    {
      tpm12class::TPMW8L_PCR_SELECTION::~TPMW8L_PCR_SELECTION((tpm12class::TPMW8L_PCR_SELECTION *)v16);
      Selections = 0;
      goto LABEL_27;
    }
    tpm12class::TPMW8_PCR_Read::TPMW8_PCR_Read((tpm12class::TPMW8_PCR_Read *)v23);
    v24 = 1;
    v25 = v11;
    *(_BYTE *)(v9 + *(_QWORD *)(v11 + 64)) = -1;
    Selections = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v23, 0);
    *(_BYTE *)(v9 + *(_QWORD *)(v25 + 64)) = 0;
    v25 = 0;
    if ( Selections < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D0,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
        (const char *)(unsigned int)Selections,
        v14);
    }
    else
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= v26 )
        {
          tpm12class::TPMW8_PCR_Read::~TPMW8_PCR_Read((tpm12class::TPMW8_PCR_Read *)v23);
          ++v9;
          goto LABEL_16;
        }
        if ( *(unsigned __int16 *)(v27 + 72 * i + 56) > v8 )
          break;
        memcpy_s_0(
          &a2[v8 * ((_DWORD)i + 8 * v9)],
          v3 - v8 * ((_DWORD)i + 8 * v9),
          *(const void *const *)(v27 + 72 * i + 64),
          *(unsigned __int16 *)(v27 + 72 * i + 56));
      }
      Selections = -2144862192;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2D7,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
        (const char *)0x80280010LL,
        (int)"PCR digest that was read is larger than the digest size should be for this algorithm.",
        v15);
    }
    tpm12class::TPMW8_PCR_Read::~TPMW8_PCR_Read((tpm12class::TPMW8_PCR_Read *)v23);
  }
  tpm12class::TPMW8L_PCR_SELECTION::~TPMW8L_PCR_SELECTION((tpm12class::TPMW8L_PCR_SELECTION *)v16);
LABEL_27:
  KspFunctionLogger::~KspFunctionLogger(v22);
  return (unsigned int)Selections;
}

```

## disassembly

```asm
0x180026948  push    rbp
0x18002694a  push    rbx
0x18002694b  push    rsi
0x18002694c  push    rdi
0x18002694d  push    r12
0x18002694f  push    r13
0x180026951  push    r14
0x180026953  push    r15
0x180026955  lea     rbp, [rsp-118h]
0x18002695d  sub     rsp, 218h
0x180026964  mov     r12d, r8d
0x180026967  mov     r13, rdx
0x18002696a  movzx   ebx, cx
0x18002696d  mov     r8b, 1; bool
0x180026970  lea     rdx, aReadallpcrs; "ReadAllPcrs"
0x180026977  lea     rcx, [rbp+150h+var_1D0]; this
0x18002697b  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180026980  nop
0x180026981  mov     r9d, ebx
0x180026984  sub     r9d, 4
0x180026988  jz      short loc_1800269BD
0x18002698a  sub     r9d, 7
0x18002698e  jz      short loc_1800269B6
0x180026990  sub     r9d, 1
0x180026994  jz      short loc_1800269AF
0x180026996  cmp     r9d, 1
0x18002699a  jz      short loc_1800269A8
0x18002699c  mov     edi, 80090029h
0x1800269a1  mov     edx, 2B9h
0x1800269a6  jmp     short loc_1800269D7
0x1800269a8  mov     esi, 40h ; '@'
0x1800269ad  jmp     short loc_1800269C2
0x1800269af  mov     esi, 30h ; '0'
0x1800269b4  jmp     short loc_1800269C2
0x1800269b6  mov     esi, 20h ; ' '
0x1800269bb  jmp     short loc_1800269C2
0x1800269bd  mov     esi, 14h
0x1800269c2  lea     eax, [rsi+rsi*2]
0x1800269c5  shl     eax, 3
0x1800269c8  cmp     eax, r12d
0x1800269cb  jbe     short loc_1800269F2
0x1800269cd  mov     edi, 80090028h
0x1800269d2  mov     edx, 2BCh; void *
0x1800269d7  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800269de  mov     r9d, edi; char *
0x1800269e1  mov     rcx, [rbp+158h]; this
0x1800269e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800269ed  jmp     loc_180026B6A
0x1800269f2  xor     r14d, r14d
0x1800269f5  mov     [rsp+250h+var_218], r14
0x1800269fa  mov     [rsp+250h+var_210], r14
0x1800269ff  mov     [rsp+250h+var_208], r14d
0x180026a04  mov     [rsp+250h+var_200], r14
0x180026a09  mov     [rsp+250h+var_1F8], r14
0x180026a0e  mov     [rsp+250h+var_1F0], r14b
0x180026a13  lea     rax, ??_7TPMW8L_PCR_SELECTION@tpm12class@@6B@; const tpm12class::TPMW8L_PCR_SELECTION::`vftable'
0x180026a1a  mov     [rsp+250h+var_220], rax
0x180026a1f  mov     dl, 1; unsigned __int8
0x180026a21  lea     rcx, [rsp+250h+var_220]; this
0x180026a26  call    ?Clear@TPMW8L_PCR_SELECTION@tpm12class@@MEAAJE@Z; tpm12class::TPMW8L_PCR_SELECTION::Clear(uchar)
0x180026a2b  nop
0x180026a2c  lea     rcx, [rsp+250h+var_220]; this
0x180026a31  call    ?CreateSelections@TPMW8L_PCR_SELECTION@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW8L_PCR_SELECTION::CreateSelections(unsigned __int64)
0x180026a36  mov     edi, eax
0x180026a38  test    eax, eax
0x180026a3a  jns     short loc_180026A4B
0x180026a3c  lea     rcx, [rsp+250h+var_220]; this
0x180026a41  call    ??1TPMW8L_PCR_SELECTION@tpm12class@@UEAA@XZ; tpm12class::TPMW8L_PCR_SELECTION::~TPMW8L_PCR_SELECTION(void)
0x180026a46  jmp     loc_180026B6A
0x180026a4b  mov     r15, [rsp+250h+var_1E0]
0x180026a50  mov     [r15+38h], bx
0x180026a55  mov     byte ptr [r15+3Ah], 3
0x180026a5a  cmp     r14d, 3
0x180026a5e  jnb     loc_180026B5E
0x180026a64  lea     rcx, [rbp+150h+var_1B0]; this
0x180026a68  call    ??0TPMW8_PCR_Read@tpm12class@@QEAA@XZ; tpm12class::TPMW8_PCR_Read::TPMW8_PCR_Read(void)
0x180026a6d  nop
0x180026a6e  mov     [rbp+150h+var_B8], 1
0x180026a78  mov     [rbp+150h+var_B0], r15
0x180026a7f  mov     ebx, r14d
0x180026a82  mov     rax, [r15+40h]
0x180026a86  mov     byte ptr [rbx+rax], 0FFh
0x180026a8a  xor     edx, edx; void *
0x180026a8c  lea     rcx, [rbp+150h+var_1B0]; this
0x180026a90  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180026a95  mov     edi, eax
0x180026a97  mov     rax, [rbp+150h+var_B0]
0x180026a9e  mov     rcx, [rax+40h]
0x180026aa2  mov     byte ptr [rbx+rcx], 0
0x180026aa6  mov     [rbp+150h+var_B0], 0
0x180026ab1  test    edi, edi
0x180026ab3  js      short loc_180026B34
0x180026ab5  xor     ebx, ebx
0x180026ab7  cmp     ebx, [rbp+150h+var_58]
0x180026abd  jnb     short loc_180026AF5
0x180026abf  lea     r8, [rbx+rbx*8]
0x180026ac3  mov     r10, [rbp+150h+var_50]
0x180026aca  movzx   edx, word ptr [r10+r8*8+38h]
0x180026ad0  cmp     edx, esi
0x180026ad2  ja      short loc_180026B06
0x180026ad4  lea     ecx, [rbx+r14*8]
0x180026ad8  imul    ecx, esi
0x180026adb  mov     r9d, edx; SourceSize
0x180026ade  mov     rdx, r12
0x180026ae1  sub     rdx, rcx; DestinationSize
0x180026ae4  add     rcx, r13; Destination
0x180026ae7  mov     r8, [r10+r8*8+40h]; Source
0x180026aec  call    memcpy_s_0
0x180026af1  inc     ebx
0x180026af3  jmp     short loc_180026AB7
0x180026af5  lea     rcx, [rbp+150h+var_1B0]; this
0x180026af9  call    ??1TPMW8_PCR_Read@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PCR_Read::~TPMW8_PCR_Read(void)
0x180026afe  inc     r14d
0x180026b01  jmp     loc_180026A5A
0x180026b06  mov     rcx, [rbp+158h]; this
0x180026b0d  lea     rax, aPcrDigestThatW; "PCR digest that was read is larger than"...
0x180026b14  mov     qword ptr [rsp+250h+var_230], rax; int
0x180026b19  mov     edi, 80280010h
0x180026b1e  mov     r9d, edi; char *
0x180026b21  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180026b28  mov     edx, 2D7h; void *
0x180026b2d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026b32  jmp     short loc_180026B50
0x180026b34  mov     rcx, [rbp+158h]; this
0x180026b3b  mov     r9d, edi; char *
0x180026b3e  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180026b45  mov     edx, 2D0h; void *
0x180026b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026b4f  nop
0x180026b50  lea     rcx, [rbp+150h+var_1B0]; this
0x180026b54  call    ??1TPMW8_PCR_Read@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PCR_Read::~TPMW8_PCR_Read(void)
0x180026b59  jmp     loc_180026A3C
0x180026b5e  lea     rcx, [rsp+250h+var_220]; this
0x180026b63  call    ??1TPMW8L_PCR_SELECTION@tpm12class@@UEAA@XZ; tpm12class::TPMW8L_PCR_SELECTION::~TPMW8L_PCR_SELECTION(void)
0x180026b68  xor     edi, edi
0x180026b6a  lea     rcx, [rbp+150h+var_1D0]; this
0x180026b6e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180026b73  mov     eax, edi
0x180026b75  add     rsp, 218h
0x180026b7c  pop     r15
0x180026b7e  pop     r14
0x180026b80  pop     r13
0x180026b82  pop     r12
0x180026b84  pop     rdi
0x180026b85  pop     rsi
0x180026b86  pop     rbx
0x180026b87  pop     rbp
0x180026b88  retn
```
