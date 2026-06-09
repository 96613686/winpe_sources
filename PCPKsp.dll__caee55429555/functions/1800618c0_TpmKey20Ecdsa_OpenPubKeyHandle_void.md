# TpmKey20Ecdsa::OpenPubKeyHandle(void)

- ea: `0x1800618c0`
- end: `0x180061b65`
- name: `?OpenPubKeyHandle@TpmKey20Ecdsa@@UEAAJXZ`
- size: `677`
- prototype: `__int64 __fastcall(TpmKey20Ecdsa *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180053080`
- `0x18008fdb0`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a20`
- `0x180031388`
- `0x18003d35c`
- `0x1800618c0`
- `0x180061bac`
- `0x18006b04c`
- `0x1800768a0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x1800619ff`
- `bcrypt!BCryptImportKeyPair` at `0x180061b38`
- `bcrypt!BCryptImportKeyPair` at `0x1800619ff`
- `bcrypt!BCryptImportKeyPair` at `0x180061b38`
- `bcrypt!BCryptSetProperty` at `0x180061adc`
- `bcrypt!BCryptSetProperty` at `0x180061adc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006191b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006191b`

## string_xrefs

- `0x1800618d6`: `TpmKey20Ecdsa::OpenPubKeyHandle`

## pseudocode

```c
__int64 __fastcall TpmKey20Ecdsa::OpenPubKeyHandle(TpmKey20Ecdsa *this)
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

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v22, L"TpmKey20Ecdsa::OpenPubKeyHandle", 1);
  v2 = (BCRYPT_KEY_HANDLE *)((char *)this + 1040);
  if ( *((_QWORD *)this + 130) )
    goto LABEL_21;
  v3 = (BCRYPT_HANDLE *)((char *)this + 1032);
  if ( !*((_QWORD *)this + 129) )
  {
    v4 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 129, L"ECDSA", L"Microsoft Primitive Provider", 0);
    if ( v4 < 0 )
    {
      v5 = 466;
LABEL_30:
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdsa.cpp",
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
      v9 = 519;
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
      v9 = 498;
      goto LABEL_8;
    }
    v7 = StringCchLengthW((const unsigned __int16 *)v24, 0x104u, &v25);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 499;
      goto LABEL_8;
    }
    v4 = BCryptSetProperty(*v3, L"ECCCurveName", v24, 2 * v25 + 2, 0);
    if ( v4 < 0 )
    {
      v5 = 506;
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
      v5 = 514;
      goto LABEL_30;
    }
    goto LABEL_21;
  }
  LODWORD(v24) = 0;
  v7 = BCRYPT_ECCFULLKEY_BLOB_From(v6, 0, 0, &v24);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 477;
LABEL_8:
    v10 = (unsigned int)v7;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdsa.cpp",
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
              (void *)0x1EA,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdsa.cpp",
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
    (void *)0x1E2,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdsa.cpp",
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
0x1800618c0  mov     [rsp-28h+arg_10], rbx
0x1800618c5  push    rbp
0x1800618c6  push    rsi
0x1800618c7  push    rdi
0x1800618c8  push    r14
0x1800618ca  push    r15
0x1800618cc  mov     rbp, rsp
0x1800618cf  sub     rsp, 60h
0x1800618d3  mov     rdi, rcx
0x1800618d6  lea     rdx, aTpmkey20ecdsaO; "TpmKey20Ecdsa::OpenPubKeyHandle"
0x1800618dd  lea     rcx, [rbp+var_20]; this
0x1800618e1  mov     r8b, 1; bool
0x1800618e4  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800618e9  lea     r15, [rdi+410h]
0x1800618f0  cmp     qword ptr [r15], 0
0x1800618f4  jnz     loc_180061A38
0x1800618fa  lea     rsi, [rdi+408h]
0x180061901  cmp     qword ptr [rsi], 0
0x180061905  jnz     short loc_180061935
0x180061907  xor     r9d, r9d; dwFlags
0x18006190a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180061911  lea     rdx, aEcdsa; "ECDSA"
0x180061918  mov     rcx, rsi; phAlgorithm
0x18006191b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180061922  nop     dword ptr [rax+rax+00h]
0x180061927  test    eax, eax
0x180061929  jns     short loc_180061935
0x18006192b  mov     edx, 1D2h
0x180061930  jmp     loc_180061AF1
0x180061935  mov     rcx, [rdi+60h]
0x180061939  test    rcx, rcx
0x18006193c  jz      loc_180061A5A
0x180061942  lea     r9, [rbp+arg_0]
0x180061946  mov     dword ptr [rbp+arg_0], 0
0x18006194d  xor     r8d, r8d
0x180061950  xor     edx, edx
0x180061952  call    BCRYPT_ECCFULLKEY_BLOB_From
0x180061957  mov     ebx, eax
0x180061959  test    eax, eax
0x18006195b  jns     short loc_18006197A
0x18006195d  mov     edx, 1DDh; void *
0x180061962  mov     r9d, eax; char *
0x180061965  mov     rcx, [rbp+28h]; this
0x180061969  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061975  jmp     loc_180061A3A
0x18006197a  mov     r14d, dword ptr [rbp+arg_0]
0x18006197e  lea     rcx, [rbp+arg_0]
0x180061982  mov     edx, r14d
0x180061985  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18006198a  mov     rbx, [rbp+arg_0]
0x18006198e  test    rbx, rbx
0x180061991  jnz     short loc_18006199D
0x180061993  mov     ebx, 80070008h
0x180061998  jmp     loc_180061A3A
0x18006199d  mov     rcx, [rdi+60h]
0x1800619a1  xor     r9d, r9d
0x1800619a4  mov     r8, rbx
0x1800619a7  mov     edx, r14d
0x1800619aa  call    BCRYPT_ECCFULLKEY_BLOB_From
0x1800619af  mov     edi, eax
0x1800619b1  test    eax, eax
0x1800619b3  jns     short loc_1800619DE
0x1800619b5  mov     rcx, [rbp+28h]; this
0x1800619b9  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800619c0  mov     r9d, eax; char *
0x1800619c3  mov     edx, 1E2h; void *
0x1800619c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800619cd  test    rbx, rbx
0x1800619d0  jz      short loc_1800619DA
0x1800619d2  mov     rcx, rbx; void *
0x1800619d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800619da  mov     ebx, edi
0x1800619dc  jmp     short loc_180061A3A
0x1800619de  mov     rcx, [rsi]; hAlgorithm
0x1800619e1  lea     r8, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x1800619e8  mov     [rsp+60h+dwFlags], 0; dwFlags
0x1800619f0  mov     r9, r15; phKey
0x1800619f3  mov     [rsp+60h+cbInput], r14d; cbInput
0x1800619f8  xor     edx, edx; hImportKey
0x1800619fa  mov     [rsp+60h+pbInput], rbx; int
0x1800619ff  call    cs:__imp_BCryptImportKeyPair
0x180061a06  nop     dword ptr [rax+rax+00h]
0x180061a0b  test    eax, eax
0x180061a0d  jns     short loc_180061A2B
0x180061a0f  mov     rcx, [rbp+28h]; this
0x180061a13  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061a1a  mov     r9d, eax; char *
0x180061a1d  mov     edx, 1EAh; void *
0x180061a22  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061a27  mov     edi, eax
0x180061a29  jmp     short loc_1800619CD
0x180061a2b  test    rbx, rbx
0x180061a2e  jz      short loc_180061A38
0x180061a30  mov     rcx, rbx; void *
0x180061a33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061a38  xor     ebx, ebx
0x180061a3a  lea     rcx, [rbp+var_20]; this
0x180061a3e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180061a43  mov     eax, ebx
0x180061a45  mov     rbx, [rsp+60h+arg_10]
0x180061a4d  add     rsp, 60h
0x180061a51  pop     r15
0x180061a53  pop     r14
0x180061a55  pop     rdi
0x180061a56  pop     rsi
0x180061a57  pop     rbp
0x180061a58  retn
0x180061a5a  cmp     qword ptr [rdi+288h], 0
0x180061a62  jz      loc_180061B53
0x180061a68  movzx   ecx, word ptr [rdi+400h]
0x180061a6f  lea     rdx, [rbp+arg_0]
0x180061a73  mov     [rbp+arg_0], 0
0x180061a7b  mov     [rbp+arg_8], 0
0x180061a83  call    CurveNameFromCurveID
0x180061a88  mov     ebx, eax
0x180061a8a  test    eax, eax
0x180061a8c  jns     short loc_180061A98
0x180061a8e  mov     edx, 1F2h
0x180061a93  jmp     loc_180061962
0x180061a98  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x180061a9c  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x180061aa0  mov     edx, 104h; unsigned __int64
0x180061aa5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180061aaa  mov     ebx, eax
0x180061aac  test    eax, eax
0x180061aae  jns     short loc_180061ABA
0x180061ab0  mov     edx, 1F3h
0x180061ab5  jmp     loc_180061962
0x180061aba  mov     r9d, dword ptr [rbp+arg_8]
0x180061abe  lea     rdx, aEcccurvename; "ECCCurveName"
0x180061ac5  mov     r8, [rbp+arg_0]; pbInput
0x180061ac9  mov     rcx, [rsi]; hObject
0x180061acc  mov     dword ptr [rsp+60h+pbInput], 0; int
0x180061ad4  lea     r9d, ds:2[r9*2]; cbInput
0x180061adc  call    cs:__imp_BCryptSetProperty
0x180061ae3  nop     dword ptr [rax+rax+00h]
0x180061ae8  test    eax, eax
0x180061aea  jns     short loc_180061B0B
0x180061aec  mov     edx, 1FAh; void *
0x180061af1  mov     rcx, [rbp+28h]; this
0x180061af5  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061afc  mov     r9d, eax; char *
0x180061aff  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061b04  mov     ebx, eax
0x180061b06  jmp     loc_180061A3A
0x180061b0b  mov     eax, [rdi+290h]
0x180061b11  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x180061b18  mov     rcx, [rsi]; hAlgorithm
0x180061b1b  mov     r9, r15; phKey
0x180061b1e  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180061b26  xor     edx, edx; hImportKey
0x180061b28  mov     [rsp+60h+cbInput], eax; cbInput
0x180061b2c  mov     rax, [rdi+288h]
0x180061b33  mov     [rsp+60h+pbInput], rax; pbInput
0x180061b38  call    cs:__imp_BCryptImportKeyPair
0x180061b3f  nop     dword ptr [rax+rax+00h]
0x180061b44  test    eax, eax
0x180061b46  jns     loc_180061A38
0x180061b4c  mov     edx, 202h
0x180061b51  jmp     short loc_180061AF1
0x180061b53  mov     ebx, 80290402h
0x180061b58  mov     edx, 207h
0x180061b5d  mov     r9d, ebx
0x180061b60  jmp     loc_180061965
```
