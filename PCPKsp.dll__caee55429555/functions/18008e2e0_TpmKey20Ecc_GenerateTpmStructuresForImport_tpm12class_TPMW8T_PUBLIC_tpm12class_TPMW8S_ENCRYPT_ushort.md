# TpmKey20Ecc::GenerateTpmStructuresForImport(tpm12class::TPMW8T_PUBLIC *,tpm12class::TPMW8S_ENCRYPT *,ushort)

- ea: `0x18008e2e0`
- end: `0x18008e712`
- name: `?GenerateTpmStructuresForImport@TpmKey20Ecc@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAVTPMW8S_ENCRYPT@3@G@Z`
- size: `1074`
- prototype: `__int64 __fastcall(TpmKey20Ecc *__hidden this, struct tpm12class::TPMW8T_PUBLIC *, struct tpm12class::TPMW8S_ENCRYPT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800532d0`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x18002aba0`
- `0x180032110`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x1800764d0`
- `0x18008e2e0`
- `0x1800a68b4`
- `0x1800aa984`
- `0x1800c8010`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18008e4b1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18008e4b1`
- `bcrypt!BCryptKeyDerivation` at `0x18008e50f`
- `bcrypt!BCryptKeyDerivation` at `0x18008e50f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008e448`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008e448`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmKey20Ecc::GenerateTpmStructuresForImport(
        TpmKey20Ecc *this,
        struct tpm12class::TPMW8T_PUBLIC *a2,
        struct tpm12class::TPMW8S_ENCRYPT *a3,
        unsigned __int16 a4)
{
  int v8; // r13d
  _DWORD *v9; // r14
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  unsigned __int64 v14; // r9
  int SymKey; // eax
  ULONG cbSecret; // ebx
  __int64 v17; // r12
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned __int64 v25; // r9
  int v26; // eax
  PUCHAR pbSecret; // [rsp+20h] [rbp-89h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-69h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-61h] BYREF
  int v31; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int8 *v32; // [rsp+58h] [rbp-51h] BYREF
  _DWORD v33[2]; // [rsp+60h] [rbp-49h] BYREF
  _DWORD *v34; // [rsp+68h] [rbp-41h]
  int *v35[3]; // [rsp+70h] [rbp-39h] BYREF
  _DWORD v36[2]; // [rsp+88h] [rbp-21h] BYREF
  const char *v37; // [rsp+90h] [rbp-19h]
  int v38; // [rsp+98h] [rbp-11h]
  int v39; // [rsp+9Ch] [rbp-Dh]
  const char *v40; // [rsp+A0h] [rbp-9h]
  __int64 v41; // [rsp+A8h] [rbp-1h]
  const wchar_t *v42; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v8 = 1;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v35, L"TpmKey20Ecc::GenerateTpmStructuresForImport", 1);
  v9 = (_DWORD *)*((_QWORD *)this + 81);
  v36[0] = 14;
  v36[1] = 13;
  v37 = "ftpmimportkey";
  v38 = 18;
  v39 = 14;
  v40 = "Microsoft.Windows";
  v41 = 14;
  v42 = L"SHA256";
  v33[0] = 0;
  v33[1] = 3;
  v34 = v36;
  if ( !v9 || (v10 = *((unsigned int *)this + 164), (unsigned int)v10 < 8) )
  {
    v11 = 879;
    goto LABEL_45;
  }
  if ( v10 < (unsigned __int64)(unsigned int)(3 * v9[1]) + 8 )
  {
    v11 = 882;
LABEL_45:
    v13 = -2144795645;
    goto LABEL_46;
  }
  v12 = (*(__int64 (__fastcall **)(TpmKey20Ecc *, _QWORD, struct tpm12class::TPMW8T_PUBLIC *))(*(_QWORD *)this + 1240LL))(
          this,
          a4,
          a2);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = (unsigned int)v12;
    v11 = 884;
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
      (const char *)v14,
      (int)pbSecret);
    goto LABEL_48;
  }
  *((_DWORD *)a2 + 15) &= 0xFFFFFFED;
  if ( *((_WORD *)a2 + 168) == 6 )
  {
    SymKey = tpm12class::TPMW8T_SENSITIVE::AllocateSymKey(
               (struct tpm12class::TPMW8S_ENCRYPT *)((char *)a3 + 64),
               ((unsigned __int64)*((unsigned __int16 *)a2 + 169) + 7) >> 3);
    v13 = SymKey;
    if ( SymKey < 0 )
    {
      v14 = (unsigned int)SymKey;
      v11 = 892;
      goto LABEL_47;
    }
    cbSecret = v9[1];
    v17 = *((_QWORD *)this + 81);
    phAlgorithm = 0;
    v18 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SP800_108_CTR_HMAC", 0, 0);
    if ( v18 < 0 )
    {
      v13 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x38A,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
              (const char *)(unsigned int)v18,
              (int)pbSecret);
LABEL_12:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      goto LABEL_48;
    }
    phKey = 0;
    v19 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, (PUCHAR)(v17 + 8 + 2 * cbSecret), cbSecret, 0);
    if ( v19 < 0 )
    {
      v20 = 915;
LABEL_15:
      v13 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v20,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
              (const char *)(unsigned int)v19,
              (int)pbSecret);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_12;
    }
    v31 = 0;
    pbSecret = (PUCHAR)&v31;
    v19 = BCryptKeyDerivation(phKey, v33, *((_QWORD *)a3 + 26), *((unsigned __int16 *)a3 + 100));
    if ( v19 < 0 )
    {
      v20 = 923;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  }
  if ( *((_DWORD *)this + 140) )
  {
    if ( *((_DWORD *)this + 174) )
      *((_DWORD *)a2 + 15) |= 0x400u;
    *((_DWORD *)a2 + 15) |= 0x40u;
    v21 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (struct tpm12class::TPMW8S_ENCRYPT *)((char *)a3 + 128),
            (TpmKey20Ecc *)((char *)this + 488));
    v13 = v21;
    if ( v21 < 0 )
    {
      v14 = (unsigned int)v21;
      v11 = 934;
      goto LABEL_47;
    }
  }
  else
  {
    *((_DWORD *)a2 + 15) |= 0x440u;
    v8 = 0;
  }
  *((_DWORD *)this + 120) = v8;
  v22 = (*(__int64 (__fastcall **)(TpmKey20Ecc *, struct tpm12class::TPMW8T_PUBLIC *))(*(_QWORD *)this + 1232LL))(
          this,
          a2);
  v13 = v22;
  if ( v22 < 0 )
  {
    v14 = (unsigned int)v22;
    v11 = 946;
    goto LABEL_47;
  }
  *((_WORD *)a2 + 28) = 35;
  switch ( *v9 )
  {
    case 0x324B4345:
    case 0x32534345:
      *((_WORD *)a2 + 208) = 3;
      break;
    case 0x344B4345:
    case 0x34534345:
      *((_WORD *)a2 + 208) = 4;
      break;
    case 0x364B4345:
    case 0x36534345:
      *((_WORD *)a2 + 208) = 5;
      break;
    default:
      v13 = -2146893783;
      v11 = 973;
LABEL_46:
      v14 = v13;
      goto LABEL_47;
  }
  v23 = tpm12class::TPMW82B_BUFFER::CopyFrom(
          (struct tpm12class::TPMW8T_PUBLIC *)((char *)a2 + 488),
          (const unsigned __int8 *)(*((_QWORD *)this + 81) + 8LL),
          (unsigned int)v9[1]);
  v13 = v23;
  if ( v23 < 0 )
  {
    v14 = (unsigned int)v23;
    v11 = 977;
    goto LABEL_47;
  }
  v24 = tpm12class::TPMW82B_BUFFER::CopyFrom(
          (struct tpm12class::TPMW8T_PUBLIC *)((char *)a2 + 560),
          (const unsigned __int8 *)((unsigned int)v9[1] + *((_QWORD *)this + 81) + 8LL),
          (unsigned int)v9[1]);
  v13 = v24;
  if ( v24 < 0 )
  {
    v14 = (unsigned int)v24;
    v11 = 979;
    goto LABEL_47;
  }
  *((_WORD *)a3 + 60) = 35;
  v25 = (unsigned int)v9[1];
  v32 = (unsigned __int8 *)(*((_QWORD *)this + 81) + 8LL + (unsigned int)(2 * v25));
  v26 = SetMemberKey((unsigned __int8 **)a3 + 30, (unsigned __int16 *)a3 + 116, (const unsigned __int8 **)&v32, v25);
  v13 = v26;
  if ( v26 < 0 )
  {
    v14 = (unsigned int)v26;
    v11 = 987;
    goto LABEL_47;
  }
  v13 = 0;
LABEL_48:
  KspFunctionLogger::~KspFunctionLogger(v35);
  return v13;
}

```

## disassembly

```asm
0x18008e2e0  push    rbp
0x18008e2e2  push    rbx
0x18008e2e3  push    rsi
0x18008e2e4  push    rdi
0x18008e2e5  push    r12
0x18008e2e7  push    r13
0x18008e2e9  push    r14
0x18008e2eb  push    r15
0x18008e2ed  lea     rbp, [rsp-1Fh]
0x18008e2f2  sub     rsp, 0C8h
0x18008e2f9  mov     rax, cs:__security_cookie
0x18008e300  xor     rax, rsp
0x18008e303  mov     [rbp+57h+var_48], rax
0x18008e307  movzx   ebx, r9w
0x18008e30b  mov     r15, r8
0x18008e30e  mov     rdi, rdx
0x18008e311  mov     rsi, rcx
0x18008e314  mov     r13d, 1
0x18008e31a  mov     r8b, r13b; bool
0x18008e31d  lea     rdx, aTpmkey20eccGen; "TpmKey20Ecc::GenerateTpmStructuresForIm"...
0x18008e324  lea     rcx, [rbp+57h+var_90]; this
0x18008e328  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18008e32d  nop
0x18008e32e  mov     r14, [rsi+288h]
0x18008e335  lea     ecx, [r13+0Dh]
0x18008e339  mov     [rbp+57h+var_78], ecx
0x18008e33c  mov     [rbp+57h+var_74], 0Dh
0x18008e343  lea     rax, aFtpmimportkey_0; "ftpmimportkey"
0x18008e34a  mov     [rbp+57h+var_70], rax
0x18008e34e  mov     [rbp+57h+var_68], 12h
0x18008e355  mov     [rbp+57h+var_64], ecx
0x18008e358  lea     rax, aMicrosoftWindo_0; "Microsoft.Windows"
0x18008e35f  mov     [rbp+57h+var_60], rax
0x18008e363  mov     [rbp+57h+var_58], rcx
0x18008e367  xor     r12d, r12d
0x18008e36a  lea     rax, aSha256_0; "SHA256"
0x18008e371  mov     [rbp+57h+var_50], rax
0x18008e375  mov     [rbp+57h+var_A0], r12d
0x18008e379  mov     [rbp+57h+var_9C], 3
0x18008e380  lea     rax, [rbp+57h+var_78]
0x18008e384  mov     [rbp+57h+var_98], rax
0x18008e388  test    r14, r14
0x18008e38b  jz      loc_18008E6C8
0x18008e391  mov     r8d, [rsi+290h]
0x18008e398  cmp     r8d, 8
0x18008e39c  jb      loc_18008E6C8
0x18008e3a2  mov     eax, [r14+4]
0x18008e3a6  lea     edx, [rax+rax*2]
0x18008e3a9  add     rdx, 8
0x18008e3ad  cmp     r8, rdx
0x18008e3b0  jnb     short loc_18008E3BC
0x18008e3b2  mov     edx, 372h
0x18008e3b7  jmp     loc_18008E6CD
0x18008e3bc  mov     rax, [rsi]
0x18008e3bf  mov     r8, rdi
0x18008e3c2  movzx   edx, bx
0x18008e3c5  mov     rcx, rsi
0x18008e3c8  mov     rax, [rax+4D8h]
0x18008e3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e3d4  mov     ebx, eax
0x18008e3d6  test    eax, eax
0x18008e3d8  jns     short loc_18008E3E7
0x18008e3da  mov     r9d, eax
0x18008e3dd  mov     edx, 374h
0x18008e3e2  jmp     loc_18008E6D5
0x18008e3e7  and     dword ptr [rdi+3Ch], 0FFFFFFEDh
0x18008e3eb  cmp     word ptr [rdi+150h], 6
0x18008e3f3  jnz     loc_18008E538
0x18008e3f9  movzx   edx, word ptr [rdi+152h]
0x18008e400  add     rdx, 7
0x18008e404  shr     rdx, 3; unsigned __int64
0x18008e408  lea     rcx, [r15+40h]; this
0x18008e40c  call    ?AllocateSymKey@TPMW8T_SENSITIVE@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW8T_SENSITIVE::AllocateSymKey(unsigned __int64)
0x18008e411  mov     ebx, eax
0x18008e413  test    eax, eax
0x18008e415  jns     short loc_18008E424
0x18008e417  mov     r9d, eax
0x18008e41a  mov     edx, 37Ch
0x18008e41f  jmp     loc_18008E6D5
0x18008e424  mov     ebx, [r14+4]
0x18008e428  mov     r12, [rsi+288h]
0x18008e42f  mov     [rbp+57h+phAlgorithm], 0
0x18008e437  xor     r9d, r9d; dwFlags
0x18008e43a  xor     r8d, r8d; pszImplementation
0x18008e43d  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18008e444  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18008e448  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008e44f  nop     dword ptr [rax+rax+00h]
0x18008e454  test    eax, eax
0x18008e456  jns     short loc_18008E480
0x18008e458  mov     rcx, [rbp+5Fh]; this
0x18008e45c  mov     r9d, eax; char *
0x18008e45f  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008e466  mov     edx, 38Ah; void *
0x18008e46b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008e470  mov     ebx, eax
0x18008e472  lea     rcx, [rbp+57h+phAlgorithm]
0x18008e476  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008e47b  jmp     loc_18008E6E6
0x18008e480  mov     [rbp+57h+phKey], 0
0x18008e488  lea     eax, [rbx+rbx]
0x18008e48b  add     r12, 8
0x18008e48f  add     rax, r12
0x18008e492  xor     r12d, r12d
0x18008e495  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x18008e49a  mov     [rsp+100h+cbSecret], ebx; cbSecret
0x18008e49e  mov     [rsp+100h+pbSecret], rax; int
0x18008e4a3  xor     r9d, r9d; cbKeyObject
0x18008e4a6  xor     r8d, r8d; pbKeyObject
0x18008e4a9  lea     rdx, [rbp+57h+phKey]; phKey
0x18008e4ad  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18008e4b1  call    cs:__imp_BCryptGenerateSymmetricKey
0x18008e4b8  nop     dword ptr [rax+rax+00h]
0x18008e4bd  test    eax, eax
0x18008e4bf  jns     short loc_18008E4E6
0x18008e4c1  mov     edx, 393h; void *
0x18008e4c6  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008e4cd  mov     r9d, eax; char *
0x18008e4d0  mov     rcx, [rbp+5Fh]; this
0x18008e4d4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008e4d9  mov     ebx, eax
0x18008e4db  lea     rcx, [rbp+57h+phKey]
0x18008e4df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008e4e4  jmp     short loc_18008E472
0x18008e4e6  mov     [rbp+57h+var_B0], r12d
0x18008e4ea  movzx   r9d, word ptr [r15+0C8h]
0x18008e4f2  mov     [rsp+100h+cbSecret], r12d
0x18008e4f7  lea     rax, [rbp+57h+var_B0]
0x18008e4fb  mov     [rsp+100h+pbSecret], rax
0x18008e500  mov     r8, [r15+0D0h]
0x18008e507  lea     rdx, [rbp+57h+var_A0]
0x18008e50b  mov     rcx, [rbp+57h+phKey]
0x18008e50f  call    cs:__imp_BCryptKeyDerivation
0x18008e516  nop     dword ptr [rax+rax+00h]
0x18008e51b  test    eax, eax
0x18008e51d  jns     short loc_18008E526
0x18008e51f  mov     edx, 39Bh
0x18008e524  jmp     short loc_18008E4C6
0x18008e526  lea     rcx, [rbp+57h+phKey]
0x18008e52a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008e52f  lea     rcx, [rbp+57h+phAlgorithm]
0x18008e533  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008e538  cmp     [rsi+230h], r12d
0x18008e53f  jz      short loc_18008E579
0x18008e541  cmp     [rsi+2B8h], r12d
0x18008e548  jz      short loc_18008E54F
0x18008e54a  bts     dword ptr [rdi+3Ch], 0Ah
0x18008e54f  or      dword ptr [rdi+3Ch], 40h
0x18008e553  lea     rdx, [rsi+1E8h]; struct tpm12class::TPMW82B_BUFFER *
0x18008e55a  lea     rcx, [r15+80h]; this
0x18008e561  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x18008e566  mov     ebx, eax
0x18008e568  test    eax, eax
0x18008e56a  jns     short loc_18008E583
0x18008e56c  mov     r9d, eax
0x18008e56f  mov     edx, 3A6h
0x18008e574  jmp     loc_18008E6D5
0x18008e579  or      dword ptr [rdi+3Ch], 440h
0x18008e580  mov     r13d, r12d
0x18008e583  mov     [rsi+1E0h], r13d
0x18008e58a  mov     rax, [rsi]
0x18008e58d  mov     rdx, rdi
0x18008e590  mov     rcx, rsi
0x18008e593  mov     rax, [rax+4D0h]
0x18008e59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e59f  mov     ebx, eax
0x18008e5a1  test    eax, eax
0x18008e5a3  jns     short loc_18008E5B2
0x18008e5a5  mov     r9d, eax
0x18008e5a8  mov     edx, 3B2h
0x18008e5ad  jmp     loc_18008E6D5
0x18008e5b2  mov     r13d, 23h ; '#'
0x18008e5b8  mov     [rdi+38h], r13w
0x18008e5bd  cmp     dword ptr [r14], 324B4345h
0x18008e5c4  jz      short loc_18008E618
0x18008e5c6  cmp     dword ptr [r14], 32534345h
0x18008e5cd  jz      short loc_18008E618
0x18008e5cf  cmp     dword ptr [r14], 344B4345h
0x18008e5d6  jz      short loc_18008E60D
0x18008e5d8  cmp     dword ptr [r14], 34534345h
0x18008e5df  jz      short loc_18008E60D
0x18008e5e1  cmp     dword ptr [r14], 364B4345h
0x18008e5e8  jz      short loc_18008E602
0x18008e5ea  cmp     dword ptr [r14], 36534345h
0x18008e5f1  jz      short loc_18008E602
0x18008e5f3  mov     ebx, 80090029h
0x18008e5f8  mov     edx, 3CDh
0x18008e5fd  jmp     loc_18008E6D2
0x18008e602  mov     word ptr [rdi+1A0h], 5
0x18008e60b  jmp     short loc_18008E621
0x18008e60d  mov     word ptr [rdi+1A0h], 4
0x18008e616  jmp     short loc_18008E621
0x18008e618  mov     word ptr [rdi+1A0h], 3
0x18008e621  mov     r8d, [r14+4]; Size
0x18008e625  mov     rdx, [rsi+288h]
0x18008e62c  add     rdx, 8; Src
0x18008e630  lea     rcx, [rdi+1E8h]; this
0x18008e637  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x18008e63c  mov     ebx, eax
0x18008e63e  test    eax, eax
0x18008e640  jns     short loc_18008E64F
0x18008e642  mov     r9d, eax
0x18008e645  mov     edx, 3D1h
0x18008e64a  jmp     loc_18008E6D5
0x18008e64f  mov     r8d, [r14+4]; Size
0x18008e653  mov     rdx, [rsi+288h]
0x18008e65a  add     rdx, 8
0x18008e65e  add     rdx, r8; Src
0x18008e661  lea     rcx, [rdi+230h]; this
0x18008e668  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x18008e66d  mov     ebx, eax
0x18008e66f  test    eax, eax
0x18008e671  jns     short loc_18008E67D
0x18008e673  mov     r9d, eax
0x18008e676  mov     edx, 3D3h
0x18008e67b  jmp     short loc_18008E6D5
0x18008e67d  mov     [r15+78h], r13w
0x18008e682  mov     r9d, [r14+4]; unsigned __int64
0x18008e686  lea     ecx, [r9+r9]
0x18008e68a  mov     rax, [rsi+288h]
0x18008e691  add     rax, 8
0x18008e695  add     rcx, rax
0x18008e698  mov     [rbp+57h+var_A8], rcx
0x18008e69c  lea     rdx, [r15+0E8h]; unsigned __int16 *
0x18008e6a3  lea     rcx, [r15+0F0h]; unsigned __int8 **
0x18008e6aa  lea     r8, [rbp+57h+var_A8]; unsigned __int8 **
0x18008e6ae  call    ?SetMemberKey@@YAJAEAPEAEAEAGAEAPEBE_K@Z; SetMemberKey(uchar * &,ushort &,uchar const * &,unsigned __int64)
0x18008e6b3  mov     ebx, eax
0x18008e6b5  test    eax, eax
0x18008e6b7  jns     short loc_18008E6C3
0x18008e6b9  mov     r9d, eax
0x18008e6bc  mov     edx, 3DBh
0x18008e6c1  jmp     short loc_18008E6D5
0x18008e6c3  mov     ebx, r12d
0x18008e6c6  jmp     short loc_18008E6E6
0x18008e6c8  mov     edx, 36Fh; void *
0x18008e6cd  mov     ebx, 80290403h
0x18008e6d2  mov     r9d, ebx; char *
0x18008e6d5  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008e6dc  mov     rcx, [rbp+5Fh]; this
0x18008e6e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e6e5  nop
0x18008e6e6  lea     rcx, [rbp+57h+var_90]; this
0x18008e6ea  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18008e6ef  mov     eax, ebx
0x18008e6f1  mov     rcx, [rbp+57h+var_48]
0x18008e6f5  xor     rcx, rsp; StackCookie
0x18008e6f8  call    __security_check_cookie
0x18008e6fd  add     rsp, 0C8h
0x18008e704  pop     r15
0x18008e706  pop     r14
0x18008e708  pop     r13
0x18008e70a  pop     r12
0x18008e70c  pop     rdi
0x18008e70d  pop     rsi
0x18008e70e  pop     rbx
0x18008e70f  pop     rbp
0x18008e710  retn
```
