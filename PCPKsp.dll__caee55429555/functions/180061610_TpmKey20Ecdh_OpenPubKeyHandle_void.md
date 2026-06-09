# TpmKey20Ecdh::OpenPubKeyHandle(void)

- ea: `0x180061610`
- end: `0x1800618b5`
- name: `?OpenPubKeyHandle@TpmKey20Ecdh@@UEAAJXZ`
- size: `677`
- prototype: `__int64 __fastcall(TpmKey20Ecdh *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008f050`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a20`
- `0x180031388`
- `0x18003d35c`
- `0x180061610`
- `0x180061bac`
- `0x18006b04c`
- `0x1800768a0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18006174f`
- `bcrypt!BCryptImportKeyPair` at `0x180061888`
- `bcrypt!BCryptImportKeyPair` at `0x18006174f`
- `bcrypt!BCryptImportKeyPair` at `0x180061888`
- `bcrypt!BCryptSetProperty` at `0x18006182c`
- `bcrypt!BCryptSetProperty` at `0x18006182c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006166b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006166b`

## string_xrefs

- `0x180061626`: `TpmKey20Ecdh::OpenPubKeyHandle`

## pseudocode

```c
__int64 __fastcall TpmKey20Ecdh::OpenPubKeyHandle(TpmKey20Ecdh *this)
{
  BCRYPT_KEY_HANDLE *v2; // r15
  BCRYPT_HANDLE *v3; // rsi
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  ULONG cbInput; // r14d
  UCHAR *v12; // rbx
  int v13; // eax
  int v14; // edi
  const struct std::nothrow_t *v15; // rdx
  NTSTATUS v16; // eax
  const struct std::nothrow_t *v17; // rdx
  __int64 v19; // rcx
  int pbInput; // [rsp+20h] [rbp-40h]
  int pbInputa; // [rsp+20h] [rbp-40h]
  _BYTE v22[32]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  PUCHAR v24; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int64 v25; // [rsp+98h] [rbp+38h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v22, L"TpmKey20Ecdh::OpenPubKeyHandle", 1);
  v2 = (BCRYPT_KEY_HANDLE *)((char *)this + 1040);
  if ( *((_QWORD *)this + 130) )
    goto LABEL_21;
  v3 = (BCRYPT_HANDLE *)((char *)this + 1032);
  if ( !*((_QWORD *)this + 129) )
  {
    v4 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 129, L"ECDH", L"Microsoft Primitive Provider", 0);
    if ( v4 < 0 )
    {
      v5 = 434;
LABEL_30:
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdh.cpp",
             (const char *)(unsigned int)v4,
             pbInput);
      goto LABEL_22;
    }
  }
  v6 = *((_QWORD *)this + 12);
  if ( !v6 )
  {
    if ( !*((_QWORD *)this + 81) )
    {
      v8 = -2144795646;
      v9 = 487;
      v10 = 2150171650LL;
      goto LABEL_9;
    }
    v19 = *((unsigned __int16 *)this + 512);
    v24 = 0;
    v25 = 0;
    v7 = CurveNameFromCurveID(v19, &v24);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 466;
      goto LABEL_8;
    }
    v7 = StringCchLengthW((const unsigned __int16 *)v24, 0x104u, &v25);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 467;
      goto LABEL_8;
    }
    v4 = BCryptSetProperty(*v3, L"ECCCurveName", v24, 2 * v25 + 2, 0);
    if ( v4 < 0 )
    {
      v5 = 474;
      goto LABEL_30;
    }
    v4 = BCryptImportKeyPair(
           *v3,
           0,
           L"ECCPUBLICBLOB",
           (BCRYPT_KEY_HANDLE *)this + 130,
           *((PUCHAR *)this + 81),
           *((_DWORD *)this + 164),
           0);
    if ( v4 < 0 )
    {
      v5 = 482;
      goto LABEL_30;
    }
    goto LABEL_21;
  }
  LODWORD(v24) = 0;
  v7 = BCRYPT_ECCFULLKEY_BLOB_From(v6, 0, 0, &v24);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 445;
LABEL_8:
    v10 = (unsigned int)v7;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdh.cpp",
      (const char *)v10,
      pbInput);
    goto LABEL_22;
  }
  cbInput = (unsigned int)v24;
  wil::make_unique_nothrow<unsigned char [0]>(&v24, (unsigned int)v24);
  v12 = v24;
  if ( !v24 )
  {
    v8 = -2147024888;
    goto LABEL_22;
  }
  v13 = BCRYPT_ECCFULLKEY_BLOB_From(*((_QWORD *)this + 12), cbInput, v24, 0);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v16 = BCryptImportKeyPair(*v3, 0, L"ECCFULLPUBLICBLOB", v2, v12, cbInput, 0);
    if ( v16 < 0 )
    {
      v14 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x1CA,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdh.cpp",
              (const char *)(unsigned int)v16,
              pbInputa);
      goto LABEL_14;
    }
    if ( v12 )
      operator delete(v12, v17);
LABEL_21:
    v8 = 0;
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C2,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdh.cpp",
    (const char *)(unsigned int)v13,
    pbInput);
LABEL_14:
  if ( v12 )
    operator delete(v12, v15);
  v8 = v14;
LABEL_22:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v22);
  return v8;
}

```

## disassembly

```asm
0x180061610  mov     [rsp-28h+arg_10], rbx
0x180061615  push    rbp
0x180061616  push    rsi
0x180061617  push    rdi
0x180061618  push    r14
0x18006161a  push    r15
0x18006161c  mov     rbp, rsp
0x18006161f  sub     rsp, 60h
0x180061623  mov     rdi, rcx
0x180061626  lea     rdx, aTpmkey20ecdhOp; "TpmKey20Ecdh::OpenPubKeyHandle"
0x18006162d  lea     rcx, [rbp+var_20]; this
0x180061631  mov     r8b, 1; bool
0x180061634  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180061639  lea     r15, [rdi+410h]
0x180061640  cmp     qword ptr [r15], 0
0x180061644  jnz     loc_180061788
0x18006164a  lea     rsi, [rdi+408h]
0x180061651  cmp     qword ptr [rsi], 0
0x180061655  jnz     short loc_180061685
0x180061657  xor     r9d, r9d; dwFlags
0x18006165a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180061661  lea     rdx, aEcdh; "ECDH"
0x180061668  mov     rcx, rsi; phAlgorithm
0x18006166b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180061672  nop     dword ptr [rax+rax+00h]
0x180061677  test    eax, eax
0x180061679  jns     short loc_180061685
0x18006167b  mov     edx, 1B2h
0x180061680  jmp     loc_180061841
0x180061685  mov     rcx, [rdi+60h]
0x180061689  test    rcx, rcx
0x18006168c  jz      loc_1800617AA
0x180061692  lea     r9, [rbp+arg_0]
0x180061696  mov     dword ptr [rbp+arg_0], 0
0x18006169d  xor     r8d, r8d
0x1800616a0  xor     edx, edx
0x1800616a2  call    BCRYPT_ECCFULLKEY_BLOB_From
0x1800616a7  mov     ebx, eax
0x1800616a9  test    eax, eax
0x1800616ab  jns     short loc_1800616CA
0x1800616ad  mov     edx, 1BDh; void *
0x1800616b2  mov     r9d, eax; char *
0x1800616b5  mov     rcx, [rbp+28h]; this
0x1800616b9  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800616c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800616c5  jmp     loc_18006178A
0x1800616ca  mov     r14d, dword ptr [rbp+arg_0]
0x1800616ce  lea     rcx, [rbp+arg_0]
0x1800616d2  mov     edx, r14d
0x1800616d5  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800616da  mov     rbx, [rbp+arg_0]
0x1800616de  test    rbx, rbx
0x1800616e1  jnz     short loc_1800616ED
0x1800616e3  mov     ebx, 80070008h
0x1800616e8  jmp     loc_18006178A
0x1800616ed  mov     rcx, [rdi+60h]
0x1800616f1  xor     r9d, r9d
0x1800616f4  mov     r8, rbx
0x1800616f7  mov     edx, r14d
0x1800616fa  call    BCRYPT_ECCFULLKEY_BLOB_From
0x1800616ff  mov     edi, eax
0x180061701  test    eax, eax
0x180061703  jns     short loc_18006172E
0x180061705  mov     rcx, [rbp+28h]; this
0x180061709  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061710  mov     r9d, eax; char *
0x180061713  mov     edx, 1C2h; void *
0x180061718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006171d  test    rbx, rbx
0x180061720  jz      short loc_18006172A
0x180061722  mov     rcx, rbx; void *
0x180061725  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006172a  mov     ebx, edi
0x18006172c  jmp     short loc_18006178A
0x18006172e  mov     rcx, [rsi]; hAlgorithm
0x180061731  lea     r8, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180061738  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180061740  mov     r9, r15; phKey
0x180061743  mov     [rsp+60h+cbInput], r14d; cbInput
0x180061748  xor     edx, edx; hImportKey
0x18006174a  mov     [rsp+60h+pbInput], rbx; int
0x18006174f  call    cs:__imp_BCryptImportKeyPair
0x180061756  nop     dword ptr [rax+rax+00h]
0x18006175b  test    eax, eax
0x18006175d  jns     short loc_18006177B
0x18006175f  mov     rcx, [rbp+28h]; this
0x180061763  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006176a  mov     r9d, eax; char *
0x18006176d  mov     edx, 1CAh; void *
0x180061772  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061777  mov     edi, eax
0x180061779  jmp     short loc_18006171D
0x18006177b  test    rbx, rbx
0x18006177e  jz      short loc_180061788
0x180061780  mov     rcx, rbx; void *
0x180061783  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061788  xor     ebx, ebx
0x18006178a  lea     rcx, [rbp+var_20]; this
0x18006178e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180061793  mov     eax, ebx
0x180061795  mov     rbx, [rsp+60h+arg_10]
0x18006179d  add     rsp, 60h
0x1800617a1  pop     r15
0x1800617a3  pop     r14
0x1800617a5  pop     rdi
0x1800617a6  pop     rsi
0x1800617a7  pop     rbp
0x1800617a8  retn
0x1800617aa  cmp     qword ptr [rdi+288h], 0
0x1800617b2  jz      loc_1800618A3
0x1800617b8  movzx   ecx, word ptr [rdi+400h]
0x1800617bf  lea     rdx, [rbp+arg_0]
0x1800617c3  mov     [rbp+arg_0], 0
0x1800617cb  mov     [rbp+arg_8], 0
0x1800617d3  call    CurveNameFromCurveID
0x1800617d8  mov     ebx, eax
0x1800617da  test    eax, eax
0x1800617dc  jns     short loc_1800617E8
0x1800617de  mov     edx, 1D2h
0x1800617e3  jmp     loc_1800616B2
0x1800617e8  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x1800617ec  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x1800617f0  mov     edx, 104h; unsigned __int64
0x1800617f5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800617fa  mov     ebx, eax
0x1800617fc  test    eax, eax
0x1800617fe  jns     short loc_18006180A
0x180061800  mov     edx, 1D3h
0x180061805  jmp     loc_1800616B2
0x18006180a  mov     r9d, dword ptr [rbp+arg_8]
0x18006180e  lea     rdx, aEcccurvename; "ECCCurveName"
0x180061815  mov     r8, [rbp+arg_0]; pbInput
0x180061819  mov     rcx, [rsi]; hObject
0x18006181c  mov     dword ptr [rsp+60h+pbInput], 0; int
0x180061824  lea     r9d, ds:2[r9*2]; cbInput
0x18006182c  call    cs:__imp_BCryptSetProperty
0x180061833  nop     dword ptr [rax+rax+00h]
0x180061838  test    eax, eax
0x18006183a  jns     short loc_18006185B
0x18006183c  mov     edx, 1DAh; void *
0x180061841  mov     rcx, [rbp+28h]; this
0x180061845  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006184c  mov     r9d, eax; char *
0x18006184f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061854  mov     ebx, eax
0x180061856  jmp     loc_18006178A
0x18006185b  mov     eax, [rdi+290h]
0x180061861  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x180061868  mov     rcx, [rsi]; hAlgorithm
0x18006186b  mov     r9, r15; phKey
0x18006186e  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180061876  xor     edx, edx; hImportKey
0x180061878  mov     [rsp+60h+cbInput], eax; cbInput
0x18006187c  mov     rax, [rdi+288h]
0x180061883  mov     [rsp+60h+pbInput], rax; pbInput
0x180061888  call    cs:__imp_BCryptImportKeyPair
0x18006188f  nop     dword ptr [rax+rax+00h]
0x180061894  test    eax, eax
0x180061896  jns     loc_180061788
0x18006189c  mov     edx, 1E2h
0x1800618a1  jmp     short loc_180061841
0x1800618a3  mov     ebx, 80290402h
0x1800618a8  mov     edx, 1E7h
0x1800618ad  mov     r9d, ebx
0x1800618b0  jmp     loc_1800616B5
```
