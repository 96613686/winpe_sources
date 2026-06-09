# TpmKey20Rsa::GenerateTpmStructuresForImport(tpm12class::TPMW8T_PUBLIC *,tpm12class::TPMW8S_ENCRYPT *,ushort)

- ea: `0x18008bcb4`
- end: `0x18008c141`
- name: `?GenerateTpmStructuresForImport@TpmKey20Rsa@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAVTPMW8S_ENCRYPT@3@G@Z`
- size: `1165`
- prototype: `__int64 __fastcall(TpmKey20Rsa *__hidden this, struct tpm12class::TPMW8T_PUBLIC *, struct tpm12class::TPMW8S_ENCRYPT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006a260`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a80`
- `0x18002aba0`
- `0x180032110`
- `0x18005c980`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x1800764d0`
- `0x180077028`
- `0x18008bcb4`
- `0x1800a68b4`
- `0x1800aa984`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18008bec1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18008bec1`
- `bcrypt!BCryptKeyDerivation` at `0x18008bf22`
- `bcrypt!BCryptKeyDerivation` at `0x18008bf22`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008be69`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008be69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmKey20Rsa::GenerateTpmStructuresForImport(
        TpmKey20Rsa *this,
        struct tpm12class::TPMW8T_PUBLIC *a2,
        struct tpm12class::TPMW8S_ENCRYPT *a3,
        unsigned __int16 a4)
{
  __int64 v8; // r14
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // eax
  unsigned __int64 v14; // r9
  int SymKey; // eax
  unsigned __int64 v16; // rcx
  UCHAR *v17; // r15
  __int64 cbSecret; // r12
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  const unsigned __int8 *v23; // rdx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // r9d
  int v29; // r8d
  int v30; // eax
  int v31; // eax
  PUCHAR pbSecret; // [rsp+20h] [rbp-79h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-59h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-51h] BYREF
  int v36; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int8 *v37; // [rsp+58h] [rbp-41h] BYREF
  _DWORD v38[2]; // [rsp+60h] [rbp-39h] BYREF
  _DWORD *v39; // [rsp+68h] [rbp-31h]
  int *v40[3]; // [rsp+70h] [rbp-29h] BYREF
  _DWORD v41[2]; // [rsp+88h] [rbp-11h] BYREF
  const char *v42; // [rsp+90h] [rbp-9h]
  int v43; // [rsp+98h] [rbp-1h]
  int v44; // [rsp+9Ch] [rbp+3h]
  const char *v45; // [rsp+A0h] [rbp+7h]
  __int64 v46; // [rsp+A8h] [rbp+Fh]
  const wchar_t *v47; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v40, L"TpmKey20Rsa::GenerateTpmStructuresForImport", 1);
  v8 = *((_QWORD *)this + 81);
  v41[0] = 14;
  v41[1] = 13;
  v42 = "ftpmimportkey";
  v43 = 18;
  v44 = 14;
  v45 = "Microsoft.Windows";
  v46 = 14;
  v47 = L"SHA256";
  v38[0] = 0;
  v38[1] = 3;
  v39 = v41;
  if ( !v8 || (v9 = *((unsigned int *)this + 164), (unsigned int)v9 < 0x18) )
  {
    v11 = 1416;
    goto LABEL_51;
  }
  v10 = *(unsigned int *)(v8 + 8);
  if ( v9 < *(unsigned int *)(v8 + 16)
          + 24LL
          + *(unsigned int *)(v8 + 20)
          + v10
          + (unsigned __int64)*(unsigned int *)(v8 + 12) )
  {
    v11 = 1423;
LABEL_51:
    v12 = -2144795625;
    goto LABEL_52;
  }
  if ( (unsigned int)v10 > 4 )
  {
    v12 = -2144795645;
    v11 = 1426;
LABEL_52:
    v14 = v12;
    goto LABEL_53;
  }
  v13 = TpmKey20Rsa::SetPublicFromUsagePolicy(this, a4, a2);
  v12 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
    v11 = 1428;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
      (const char *)v14,
      (int)pbSecret);
    goto LABEL_54;
  }
  *((_DWORD *)a2 + 15) &= 0xFFFFFFED;
  if ( *((_WORD *)a2 + 96) == 6 )
  {
    SymKey = tpm12class::TPMW8T_SENSITIVE::AllocateSymKey(
               (struct tpm12class::TPMW8S_ENCRYPT *)((char *)a3 + 64),
               ((unsigned __int64)*((unsigned __int16 *)a2 + 97) + 7) >> 3);
    v12 = SymKey;
    if ( SymKey < 0 )
    {
      v14 = (unsigned int)SymKey;
      v11 = 1435;
      goto LABEL_53;
    }
    v16 = *(unsigned int *)(v8 + 8) + (unsigned __int64)*(unsigned int *)(v8 + 12);
    v17 = (UCHAR *)(v16 + *((_QWORD *)this + 81) + 24LL);
    cbSecret = *(unsigned int *)(v8 + 16);
    if ( (unsigned int)cbSecret < *(_DWORD *)(v8 + 20)
      || memcmp_0((const void *)(v16 + *((_QWORD *)this + 81) + 24LL), &v17[cbSecret], *(unsigned int *)(v8 + 20)) > 0 )
    {
      v17 += cbSecret;
      LODWORD(cbSecret) = *(_DWORD *)(v8 + 20);
    }
    phAlgorithm = 0;
    v19 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SP800_108_CTR_HMAC", 0, 0);
    if ( v19 < 0 )
    {
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5B6,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
              (const char *)(unsigned int)v19,
              (int)pbSecret);
LABEL_17:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      goto LABEL_54;
    }
    phKey = 0;
    v20 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, v17, cbSecret, 0);
    if ( v20 < 0 )
    {
      v21 = 1471;
LABEL_20:
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v21,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
              (const char *)(unsigned int)v20,
              (int)pbSecret);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_17;
    }
    v36 = 0;
    pbSecret = (PUCHAR)&v36;
    v20 = BCryptKeyDerivation(phKey, v38, *((_QWORD *)a3 + 26), *((unsigned __int16 *)a3 + 100));
    if ( v20 < 0 )
    {
      v21 = 1479;
      goto LABEL_20;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  }
  v22 = *((_DWORD *)this + 248);
  if ( v22 && (v23 = (const unsigned __int8 *)*((_QWORD *)this + 123)) != 0 && *((_DWORD *)this + 249) )
  {
    v24 = tpm12class::TPMW82B_BUFFER::CopyFrom((struct tpm12class::TPMW8T_PUBLIC *)((char *)a2 + 64), v23, v22);
    v12 = v24;
    if ( v24 < 0 )
    {
      v14 = (unsigned int)v24;
      v11 = 1486;
      goto LABEL_53;
    }
    *((_DWORD *)a2 + 15) &= ~0x40u;
  }
  else
  {
    if ( *((_DWORD *)this + 140) )
    {
      v25 = tpm12class::TPMW82B_BUFFER::CopyFrom(
              (struct tpm12class::TPMW8S_ENCRYPT *)((char *)a3 + 128),
              (TpmKey20Rsa *)((char *)this + 488));
      v12 = v25;
      if ( v25 < 0 )
      {
        v14 = (unsigned int)v25;
        v11 = 1493;
        goto LABEL_53;
      }
      v26 = 1;
    }
    else
    {
      *((_DWORD *)a2 + 15) |= 0x400u;
      v26 = 0;
    }
    *((_DWORD *)this + 120) = v26;
    *((_DWORD *)a2 + 15) |= 0x40u;
  }
  if ( *((_DWORD *)this + 174) )
    *((_DWORD *)a2 + 15) |= 0x400u;
  v27 = TpmKey20::SetPublicFromMigrationAuth(this, a2);
  v12 = v27;
  if ( v27 < 0 )
  {
    v14 = (unsigned int)v27;
    v11 = 1512;
    goto LABEL_53;
  }
  *((_WORD *)a2 + 28) = 1;
  *((_DWORD *)a2 + 69) = 0;
  if ( *(_DWORD *)(v8 + 8) )
  {
    v28 = 0;
    v29 = 0;
    do
    {
      v29 = *(unsigned __int8 *)(v28 + *((_QWORD *)this + 81) + 24LL) + (v29 << 8);
      *((_DWORD *)a2 + 69) = v29;
      ++v28;
    }
    while ( v28 < *(_DWORD *)(v8 + 8) );
    if ( v29 == 65537 )
      *((_DWORD *)a2 + 69) = 0;
  }
  *((_WORD *)a2 + 136) = *(_WORD *)(v8 + 4);
  v30 = tpm12class::TPMW82B_BUFFER::CopyFrom(
          (struct tpm12class::TPMW8T_PUBLIC *)((char *)a2 + 760),
          (const unsigned __int8 *)(*(unsigned int *)(v8 + 8) + *((_QWORD *)this + 81) + 24LL),
          *(unsigned int *)(v8 + 12));
  v12 = v30;
  if ( v30 < 0 )
  {
    v14 = (unsigned int)v30;
    v11 = 1537;
    goto LABEL_53;
  }
  *((_WORD *)a3 + 60) = 1;
  v37 = (unsigned __int8 *)(*((_QWORD *)this + 81)
                          + 24LL
                          + *(unsigned int *)(v8 + 12)
                          + (unsigned __int64)*(unsigned int *)(v8 + 8));
  v31 = SetMemberKey(
          (unsigned __int8 **)a3 + 28,
          (unsigned __int16 *)a3 + 108,
          (const unsigned __int8 **)&v37,
          *(unsigned int *)(v8 + 16));
  v12 = v31;
  if ( v31 < 0 )
  {
    v14 = (unsigned int)v31;
    v11 = 1547;
    goto LABEL_53;
  }
  v12 = 0;
LABEL_54:
  KspFunctionLogger::~KspFunctionLogger(v40);
  return v12;
}

```

## disassembly

```asm
0x18008bcb4  mov     [rsp-8+arg_18], rbx
0x18008bcb9  push    rbp
0x18008bcba  push    rsi
0x18008bcbb  push    rdi
0x18008bcbc  push    r12
0x18008bcbe  push    r13
0x18008bcc0  push    r14
0x18008bcc2  push    r15
0x18008bcc4  lea     rbp, [rsp-27h]
0x18008bcc9  sub     rsp, 0C0h
0x18008bcd0  mov     rax, cs:__security_cookie
0x18008bcd7  xor     rax, rsp
0x18008bcda  mov     [rbp+57h+var_38], rax
0x18008bcde  movzx   ebx, r9w
0x18008bce2  mov     r13, r8
0x18008bce5  mov     rdi, rdx
0x18008bce8  mov     rsi, rcx
0x18008bceb  mov     r8b, 1; bool
0x18008bcee  lea     rdx, aTpmkey20rsaGen; "TpmKey20Rsa::GenerateTpmStructuresForIm"...
0x18008bcf5  lea     rcx, [rbp+57h+var_80]; this
0x18008bcf9  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18008bcfe  nop
0x18008bcff  mov     r14, [rsi+288h]
0x18008bd06  mov     ecx, 0Eh
0x18008bd0b  mov     [rbp+57h+var_68], ecx
0x18008bd0e  mov     [rbp+57h+var_64], 0Dh
0x18008bd15  lea     rax, aFtpmimportkey; "ftpmimportkey"
0x18008bd1c  mov     [rbp+57h+var_60], rax
0x18008bd20  mov     [rbp+57h+var_58], 12h
0x18008bd27  mov     [rbp+57h+var_54], ecx
0x18008bd2a  lea     rax, aMicrosoftWindo; "Microsoft.Windows"
0x18008bd31  mov     [rbp+57h+var_50], rax
0x18008bd35  mov     [rbp+57h+var_48], rcx
0x18008bd39  xor     r15d, r15d
0x18008bd3c  lea     rax, aSha256_0; "SHA256"
0x18008bd43  mov     [rbp+57h+var_40], rax
0x18008bd47  mov     [rbp+57h+var_90], r15d
0x18008bd4b  mov     [rbp+57h+var_8C], 3
0x18008bd52  lea     rax, [rbp+57h+var_68]
0x18008bd56  mov     [rbp+57h+var_88], rax
0x18008bd5a  test    r14, r14
0x18008bd5d  jz      loc_18008C0F0
0x18008bd63  mov     edx, [rsi+290h]
0x18008bd69  cmp     edx, 18h
0x18008bd6c  jb      loc_18008C0F0
0x18008bd72  mov     r8d, [r14+8]
0x18008bd76  mov     ecx, [r14+0Ch]
0x18008bd7a  add     rcx, r8
0x18008bd7d  mov     eax, [r14+14h]
0x18008bd81  add     rcx, rax
0x18008bd84  mov     eax, [r14+10h]
0x18008bd88  add     rax, 18h
0x18008bd8c  add     rcx, rax
0x18008bd8f  cmp     rdx, rcx
0x18008bd92  jnb     short loc_18008BD9E
0x18008bd94  mov     edx, 58Fh
0x18008bd99  jmp     loc_18008C0F5
0x18008bd9e  cmp     r8d, 4
0x18008bda2  jbe     short loc_18008BDB3
0x18008bda4  mov     ebx, 80290403h
0x18008bda9  mov     edx, 592h
0x18008bdae  jmp     loc_18008C0FA
0x18008bdb3  mov     r8, rdi; struct tpm12class::TPMW8T_PUBLIC *
0x18008bdb6  movzx   edx, bx; unsigned __int16
0x18008bdb9  mov     rcx, rsi; this
0x18008bdbc  call    ?SetPublicFromUsagePolicy@TpmKey20Rsa@@MEAAJGPEAVTPMW8T_PUBLIC@tpm12class@@@Z; TpmKey20Rsa::SetPublicFromUsagePolicy(ushort,tpm12class::TPMW8T_PUBLIC *)
0x18008bdc1  mov     ebx, eax
0x18008bdc3  test    eax, eax
0x18008bdc5  jns     short loc_18008BDD4
0x18008bdc7  mov     r9d, eax
0x18008bdca  mov     edx, 594h
0x18008bdcf  jmp     loc_18008C0FD
0x18008bdd4  and     dword ptr [rdi+3Ch], 0FFFFFFEDh
0x18008bdd8  cmp     word ptr [rdi+0C0h], 6
0x18008bde0  jnz     loc_18008BF4B
0x18008bde6  movzx   edx, word ptr [rdi+0C2h]
0x18008bded  add     rdx, 7
0x18008bdf1  shr     rdx, 3; unsigned __int64
0x18008bdf5  lea     rcx, [r13+40h]; this
0x18008bdf9  call    ?AllocateSymKey@TPMW8T_SENSITIVE@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW8T_SENSITIVE::AllocateSymKey(unsigned __int64)
0x18008bdfe  mov     ebx, eax
0x18008be00  test    eax, eax
0x18008be02  jns     short loc_18008BE11
0x18008be04  mov     r9d, eax
0x18008be07  mov     edx, 59Bh
0x18008be0c  jmp     loc_18008C0FD
0x18008be11  mov     ecx, [r14+0Ch]
0x18008be15  mov     eax, [r14+8]
0x18008be19  add     rcx, rax
0x18008be1c  mov     r15, [rsi+288h]
0x18008be23  add     r15, 18h
0x18008be27  add     r15, rcx
0x18008be2a  mov     r12d, [r14+10h]
0x18008be2e  lea     rbx, [r12+r15]
0x18008be32  cmp     r12d, [r14+14h]
0x18008be36  jb      short loc_18008BE4B
0x18008be38  mov     r8d, [r14+14h]; Size
0x18008be3c  mov     rdx, rbx; Buf2
0x18008be3f  mov     rcx, r15; Buf1
0x18008be42  call    memcmp_0
0x18008be47  test    eax, eax
0x18008be49  jle     short loc_18008BE52
0x18008be4b  mov     r15, rbx
0x18008be4e  mov     r12d, [r14+14h]
0x18008be52  xor     ebx, ebx
0x18008be54  mov     [rbp+57h+phAlgorithm], rbx
0x18008be58  xor     r9d, r9d; dwFlags
0x18008be5b  xor     r8d, r8d; pszImplementation
0x18008be5e  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18008be65  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18008be69  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008be70  nop     dword ptr [rax+rax+00h]
0x18008be75  test    eax, eax
0x18008be77  jns     short loc_18008BEA1
0x18008be79  mov     rcx, [rbp+5Fh]; this
0x18008be7d  mov     r9d, eax; char *
0x18008be80  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008be87  mov     edx, 5B6h; void *
0x18008be8c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008be91  mov     ebx, eax
0x18008be93  lea     rcx, [rbp+57h+phAlgorithm]
0x18008be97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008be9c  jmp     loc_18008C10E
0x18008bea1  mov     [rbp+57h+phKey], rbx
0x18008bea5  mov     [rsp+0F0h+dwFlags], ebx; dwFlags
0x18008bea9  mov     [rsp+0F0h+cbSecret], r12d; cbSecret
0x18008beae  mov     [rsp+0F0h+pbSecret], r15; int
0x18008beb3  xor     r9d, r9d; cbKeyObject
0x18008beb6  xor     r8d, r8d; pbKeyObject
0x18008beb9  lea     rdx, [rbp+57h+phKey]; phKey
0x18008bebd  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18008bec1  call    cs:__imp_BCryptGenerateSymmetricKey
0x18008bec8  nop     dword ptr [rax+rax+00h]
0x18008becd  xor     r15d, r15d
0x18008bed0  test    eax, eax
0x18008bed2  jns     short loc_18008BEF9
0x18008bed4  mov     edx, 5BFh; void *
0x18008bed9  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008bee0  mov     r9d, eax; char *
0x18008bee3  mov     rcx, [rbp+5Fh]; this
0x18008bee7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008beec  mov     ebx, eax
0x18008beee  lea     rcx, [rbp+57h+phKey]
0x18008bef2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008bef7  jmp     short loc_18008BE93
0x18008bef9  mov     [rbp+57h+var_A0], r15d
0x18008befd  movzx   r9d, word ptr [r13+0C8h]
0x18008bf05  mov     [rsp+0F0h+cbSecret], r15d
0x18008bf0a  lea     rax, [rbp+57h+var_A0]
0x18008bf0e  mov     [rsp+0F0h+pbSecret], rax
0x18008bf13  mov     r8, [r13+0D0h]
0x18008bf1a  lea     rdx, [rbp+57h+var_90]
0x18008bf1e  mov     rcx, [rbp+57h+phKey]
0x18008bf22  call    cs:__imp_BCryptKeyDerivation
0x18008bf29  nop     dword ptr [rax+rax+00h]
0x18008bf2e  test    eax, eax
0x18008bf30  jns     short loc_18008BF39
0x18008bf32  mov     edx, 5C7h
0x18008bf37  jmp     short loc_18008BED9
0x18008bf39  lea     rcx, [rbp+57h+phKey]
0x18008bf3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008bf42  lea     rcx, [rbp+57h+phAlgorithm]
0x18008bf46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008bf4b  mov     eax, [rsi+3E0h]
0x18008bf51  mov     r12d, 400h
0x18008bf57  test    eax, eax
0x18008bf59  jz      short loc_18008BF95
0x18008bf5b  mov     rdx, [rsi+3D8h]; Src
0x18008bf62  test    rdx, rdx
0x18008bf65  jz      short loc_18008BF95
0x18008bf67  cmp     [rsi+3E4h], r15d
0x18008bf6e  jz      short loc_18008BF95
0x18008bf70  mov     r8d, eax; Size
0x18008bf73  lea     rcx, [rdi+40h]; this
0x18008bf77  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x18008bf7c  mov     ebx, eax
0x18008bf7e  test    eax, eax
0x18008bf80  jns     short loc_18008BF8F
0x18008bf82  mov     r9d, eax
0x18008bf85  mov     edx, 5CEh
0x18008bf8a  jmp     loc_18008C0FD
0x18008bf8f  and     dword ptr [rdi+3Ch], 0FFFFFFBFh
0x18008bf93  jmp     short loc_18008BFDC
0x18008bf95  cmp     [rsi+230h], r15d
0x18008bf9c  jz      short loc_18008BFCB
0x18008bf9e  lea     rdx, [rsi+1E8h]; struct tpm12class::TPMW82B_BUFFER *
0x18008bfa5  lea     rcx, [r13+80h]; this
0x18008bfac  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x18008bfb1  mov     ebx, eax
0x18008bfb3  test    eax, eax
0x18008bfb5  jns     short loc_18008BFC4
0x18008bfb7  mov     r9d, eax
0x18008bfba  mov     edx, 5D5h
0x18008bfbf  jmp     loc_18008C0FD
0x18008bfc4  mov     eax, 1
0x18008bfc9  jmp     short loc_18008BFD2
0x18008bfcb  or      [rdi+3Ch], r12d
0x18008bfcf  mov     eax, r15d
0x18008bfd2  mov     [rsi+1E0h], eax
0x18008bfd8  or      dword ptr [rdi+3Ch], 40h
0x18008bfdc  mov     eax, [rdi+3Ch]
0x18008bfdf  cmp     [rsi+2B8h], r15d
0x18008bfe6  jz      short loc_18008BFEE
0x18008bfe8  or      eax, r12d
0x18008bfeb  mov     [rdi+3Ch], eax
0x18008bfee  mov     rdx, rdi; struct tpm12class::TPMW8T_PUBLIC *
0x18008bff1  mov     rcx, rsi; this
0x18008bff4  call    ?SetPublicFromMigrationAuth@TpmKey20@@MEAAJPEAVTPMW8T_PUBLIC@tpm12class@@@Z; TpmKey20::SetPublicFromMigrationAuth(tpm12class::TPMW8T_PUBLIC *)
0x18008bff9  mov     ebx, eax
0x18008bffb  test    eax, eax
0x18008bffd  jns     short loc_18008C00C
0x18008bfff  mov     r9d, eax
0x18008c002  mov     edx, 5E8h
0x18008c007  jmp     loc_18008C0FD
0x18008c00c  mov     r12d, 1
0x18008c012  mov     [rdi+38h], r12w
0x18008c017  mov     [rdi+114h], r15d
0x18008c01e  cmp     [r14+8], r15d
0x18008c022  jbe     short loc_18008C060
0x18008c024  mov     r9d, r15d
0x18008c027  mov     r8d, r15d
0x18008c02a  mov     ecx, r9d
0x18008c02d  mov     rax, [rsi+288h]
0x18008c034  movzx   edx, byte ptr [rcx+rax+18h]
0x18008c039  shl     r8d, 8
0x18008c03d  add     r8d, edx
0x18008c040  mov     [rdi+114h], r8d
0x18008c047  add     r9d, r12d
0x18008c04a  cmp     r9d, [r14+8]
0x18008c04e  jb      short loc_18008C02A
0x18008c050  cmp     r8d, 10001h
0x18008c057  jnz     short loc_18008C060
0x18008c059  mov     [rdi+114h], r15d
0x18008c060  movzx   eax, word ptr [r14+4]
0x18008c065  mov     [rdi+110h], ax
0x18008c06c  mov     r8d, [r14+0Ch]; Size
0x18008c070  mov     ecx, [r14+8]
0x18008c074  mov     rdx, [rsi+288h]
0x18008c07b  add     rdx, 18h
0x18008c07f  add     rdx, rcx; Src
0x18008c082  lea     rcx, [rdi+2F8h]; this
0x18008c089  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x18008c08e  mov     ebx, eax
0x18008c090  test    eax, eax
0x18008c092  jns     short loc_18008C09E
0x18008c094  mov     r9d, eax
0x18008c097  mov     edx, 601h
0x18008c09c  jmp     short loc_18008C0FD
0x18008c09e  mov     [r13+78h], r12w
0x18008c0a3  mov     ecx, [r14+8]
0x18008c0a7  mov     eax, [r14+0Ch]
0x18008c0ab  add     rcx, rax
0x18008c0ae  mov     rax, [rsi+288h]
0x18008c0b5  add     rax, 18h
0x18008c0b9  add     rcx, rax
0x18008c0bc  mov     [rbp+57h+var_98], rcx
0x18008c0c0  mov     r9d, [r14+10h]; unsigned __int64
0x18008c0c4  lea     rdx, [r13+0D8h]; unsigned __int16 *
0x18008c0cb  lea     rcx, [r13+0E0h]; unsigned __int8 **
0x18008c0d2  lea     r8, [rbp+57h+var_98]; unsigned __int8 **
0x18008c0d6  call    ?SetMemberKey@@YAJAEAPEAEAEAGAEAPEBE_K@Z; SetMemberKey(uchar * &,ushort &,uchar const * &,unsigned __int64)
0x18008c0db  mov     ebx, eax
0x18008c0dd  test    eax, eax
0x18008c0df  jns     short loc_18008C0EB
0x18008c0e1  mov     r9d, eax
0x18008c0e4  mov     edx, 60Bh
0x18008c0e9  jmp     short loc_18008C0FD
0x18008c0eb  mov     ebx, r15d
0x18008c0ee  jmp     short loc_18008C10E
0x18008c0f0  mov     edx, 588h; void *
0x18008c0f5  mov     ebx, 80290417h
0x18008c0fa  mov     r9d, ebx; char *
0x18008c0fd  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008c104  mov     rcx, [rbp+5Fh]; this
0x18008c108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c10d  nop
0x18008c10e  lea     rcx, [rbp+57h+var_80]; this
0x18008c112  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18008c117  mov     eax, ebx
0x18008c119  mov     rcx, [rbp+57h+var_38]
0x18008c11d  xor     rcx, rsp; StackCookie
0x18008c120  call    __security_check_cookie
0x18008c125  mov     rbx, [rsp+0F0h+arg_18]
0x18008c12d  add     rsp, 0C0h
0x18008c134  pop     r15
0x18008c136  pop     r14
0x18008c138  pop     r13
0x18008c13a  pop     r12
0x18008c13c  pop     rdi
0x18008c13d  pop     rsi
0x18008c13e  pop     rbp
0x18008c13f  retn
```
