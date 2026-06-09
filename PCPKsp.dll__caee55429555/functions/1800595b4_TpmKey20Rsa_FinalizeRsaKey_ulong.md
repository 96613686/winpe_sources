# TpmKey20Rsa::FinalizeRsaKey(ulong)

- ea: `0x1800595b4`
- end: `0x180059b3a`
- name: `?FinalizeRsaKey@TpmKey20Rsa@@IEAAJK@Z`
- size: `1414`
- prototype: `__int64 __fastcall(TpmKey20Rsa *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18008bb60`

## callees

- `0x180010c90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800294d4`
- `0x180029a20`
- `0x180029a80`
- `0x18002b3d0`
- `0x180032110`
- `0x18003335c`
- `0x180033d00`
- `0x180034464`
- `0x1800595b4`
- `0x18005ba18`
- `0x18005be94`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x180065d78`
- `0x18006a260`
- `0x1800768a0`
- `0x18007bdbc`
- `0x1800c8010`

## import_xrefs

- `bcrypt!BCryptGenerateKeyPair` at `0x180059697`
- `bcrypt!BCryptGenerateKeyPair` at `0x180059697`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800596ea`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800596ea`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180059631`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180059631`
- `bcrypt!BCryptExportKey` at `0x180059731`
- `bcrypt!BCryptExportKey` at `0x18005978e`
- `bcrypt!BCryptExportKey` at `0x180059731`
- `bcrypt!BCryptExportKey` at `0x18005978e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey20Rsa::FinalizeRsaKey(TpmKey20Rsa *this, unsigned int a2)
{
  NTSTATUS v3; // eax
  void *v4; // rdx
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  PUCHAR v8; // rdi
  NTSTATUS v9; // eax
  const struct std::nothrow_t *v10; // rdx
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rcx
  PUCHAR v17; // rax
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // esi
  unsigned __int8 *v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  unsigned int v23; // esi
  unsigned __int8 *v24; // rdx
  int v25; // eax
  ULONG cbOutput; // [rsp+20h] [rbp-E0h]
  PUCHAR pbOutput; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v28[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v29[200]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v31[72]; // [rsp+130h] [rbp+30h] BYREF
  struct tpm12class::TPMW8S_SENSITIVE_CREATE *v32; // [rsp+178h] [rbp+78h]
  struct tpm12class::TPMW8T_PUBLIC *v33; // [rsp+180h] [rbp+80h]
  _BYTE v34[72]; // [rsp+218h] [rbp+118h] BYREF
  struct tpm12class::TPMW8T_PUBLIC *v35; // [rsp+260h] [rbp+160h]
  _BYTE v36[72]; // [rsp+270h] [rbp+170h] BYREF
  tpm12class::TpmDataObject *v37; // [rsp+2B8h] [rbp+1B8h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]
  ULONG pcbResult; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned int v40; // [rsp+2F8h] [rbp+1F8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+300h] [rbp+200h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+308h] [rbp+208h] BYREF

  v40 = a2;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v28, L"TpmKey20Rsa::FinalizeRsaKey", 1);
  if ( !*((_DWORD *)this + 160) || *((_DWORD *)this + 170) != 65540 || *((_QWORD *)this + 81) )
    goto LABEL_19;
  phAlgorithm = 0;
  v3 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", L"Microsoft Primitive Provider", 0);
  if ( v3 >= 0 )
  {
    phKey = 0;
    v6 = BCryptGenerateKeyPair(phAlgorithm, &phKey, *((_DWORD *)this + 169), 0);
    if ( v6 < 0 )
    {
      v7 = 2143;
LABEL_9:
      v5 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
             (const char *)(unsigned int)v6,
             cbOutput);
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      goto LABEL_45;
    }
    v6 = BCryptFinalizeKeyPair(phKey, 0);
    if ( v6 < 0 )
    {
      v7 = 2145;
      goto LABEL_9;
    }
    pcbResult = 0;
    v6 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", 0, 0, &pcbResult, 0);
    if ( v6 < 0 )
    {
      v7 = 2154;
      goto LABEL_9;
    }
    wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, pcbResult);
    v8 = pbOutput;
    v9 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", pbOutput, pcbResult, &pcbResult, 0);
    if ( v9 < 0 )
    {
      v5 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x874,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
             (const char *)(unsigned int)v9,
             cbOutput);
      if ( v8 )
        operator delete(v8, v10);
      goto LABEL_10;
    }
    *((_QWORD *)this + 81) = v8;
    *((_DWORD *)this + 164) = pcbResult;
    pcbResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_19:
    if ( !*((_QWORD *)this + 12) && !*((_DWORD *)this + 116) && *((_QWORD *)this + 81) )
    {
      v11 = TpmKey20Rsa::PerformKeyImport(this);
      v5 = v11;
      if ( v11 < 0 )
      {
        v12 = (unsigned int)v11;
        v13 = 2179;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
          (const char *)v12,
          cbOutput);
        goto LABEL_45;
      }
LABEL_57:
      v5 = 0;
      goto LABEL_45;
    }
    if ( *((_DWORD *)this + 260) )
    {
      v5 = -2144795617;
      v12 = 2150171679LL;
      v13 = 2183;
      goto LABEL_24;
    }
    tpm12class::TPMW8_Create::TPMW8_Create((tpm12class::TPMW8_Create *)v29);
    LOWORD(v40) = 0;
    v14 = TpmKey20::ReadParent(this, &v30, (struct tpm12class::TPMW82B_BUFFER *)v31, (unsigned __int16 *)&v40);
    if ( v14 >= 0 )
    {
      v14 = TpmKey20Rsa::SetCommonRsaKeyAttributes(this, v33, v32, v40);
      if ( v14 >= 0 )
      {
        v14 = TpmKey20::SetPublicFromMigrationAuth(this, v33);
        if ( v14 >= 0 )
        {
          v14 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v29, 0);
          if ( v14 >= 0 )
          {
            v14 = TpmKey20Rsa::VerifyPublicKeyStrength(this, v35);
            if ( v14 >= 0 )
            {
              v14 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                      (TpmKey20Rsa *)((char *)this + 104),
                      (const struct tpm12class::TPMW82B_BUFFER *)v34);
              if ( v14 >= 0 )
              {
                v16 = *((_QWORD *)this + 12);
                if ( v16 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, 1);
                *((_QWORD *)this + 12) = 0;
                wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(&pbOutput, v35);
                v17 = pbOutput;
                if ( pbOutput )
                {
                  pbOutput = 0;
                  *((_QWORD *)this + 12) = v17;
                  wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
                    &pbOutput,
                    0);
                  v40 = 0;
                  v14 = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v36, 0, 0, &v40);
                  if ( v14 < 0 )
                  {
                    v15 = 2214;
                    goto LABEL_29;
                  }
                  *((_DWORD *)this + 178) = 0;
                  operator delete(*((void **)this + 88), v19);
                  *((_QWORD *)this + 88) = 0;
                  v20 = v40;
                  wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, v40);
                  v21 = pbOutput;
                  if ( pbOutput )
                  {
                    *((_QWORD *)this + 88) = pbOutput;
                    *((_DWORD *)this + 178) = v20;
                    v14 = tpm12class::TpmDataObject::Get(
                            (tpm12class::TpmDataObject *)v36,
                            v21,
                            v20,
                            (unsigned int *)this + 178);
                    if ( v14 < 0 )
                    {
                      v15 = 2220;
                      goto LABEL_29;
                    }
                    v14 = tpm12class::TpmDataObject::Get(v37, 0, 0, &v40);
                    if ( v14 < 0 )
                    {
                      v15 = 2224;
                      goto LABEL_29;
                    }
                    *((_DWORD *)this + 182) = 0;
                    operator delete(*((void **)this + 90), v22);
                    *((_QWORD *)this + 90) = 0;
                    v23 = v40;
                    wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, v40);
                    v24 = pbOutput;
                    if ( pbOutput )
                    {
                      *((_QWORD *)this + 90) = pbOutput;
                      *((_DWORD *)this + 182) = v23;
                      v25 = tpm12class::TpmDataObject::Get(v37, v24, v23, (unsigned int *)this + 182);
                      v5 = v25;
                      if ( v25 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x8B6,
                          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                          (const char *)(unsigned int)v25,
                          cbOutput);
                        tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v29);
                        goto LABEL_45;
                      }
                      tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v29);
                      goto LABEL_57;
                    }
                  }
                }
                else
                {
                  wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
                    &pbOutput,
                    0);
                }
                tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v29);
                v5 = -2147024888;
                goto LABEL_45;
              }
              v15 = 2202;
            }
            else
            {
              v15 = 2200;
            }
          }
          else
          {
            v15 = 2198;
          }
        }
        else
        {
          v15 = 2196;
        }
      }
      else
      {
        v15 = 2194;
      }
    }
    else
    {
      v15 = 2189;
    }
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
      (const char *)(unsigned int)v14,
      cbOutput);
    tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v29);
    v5 = v14;
    goto LABEL_45;
  }
  v5 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x859,
         (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
         (const char *)(unsigned int)v3,
         cbOutput);
  if ( phAlgorithm )
    wil::details::BCryptCloseAlgorithmProviderNoFlags((wil::details *)phAlgorithm, v4);
LABEL_45:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v28);
  return v5;
}

```

## disassembly

```asm
0x1800595b4  mov     [rsp-8+arg_8], edx
0x1800595b8  push    rbp
0x1800595b9  push    rbx
0x1800595ba  push    rsi
0x1800595bb  push    rdi
0x1800595bc  push    r14
0x1800595be  lea     rbp, [rsp-1C0h]
0x1800595c6  sub     rsp, 2C0h
0x1800595cd  mov     rbx, rcx
0x1800595d0  mov     r8b, 1; bool
0x1800595d3  lea     rdx, aTpmkey20rsaFin; "TpmKey20Rsa::FinalizeRsaKey"
0x1800595da  lea     rcx, [rsp+2E0h+var_298]; this
0x1800595df  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800595e4  nop
0x1800595e5  xor     r14d, r14d
0x1800595e8  cmp     [rbx+280h], r14d
0x1800595ef  jz      loc_180059803
0x1800595f5  cmp     dword ptr [rbx+2A8h], 10004h
0x1800595ff  jnz     loc_180059803
0x180059605  cmp     [rbx+288h], r14
0x18005960c  jnz     loc_180059803
0x180059612  mov     [rbp+1E0h+phAlgorithm], r14
0x180059619  xor     r9d, r9d; dwFlags
0x18005961c  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180059623  lea     rdx, aRsa; "RSA"
0x18005962a  lea     rcx, [rbp+1E0h+phAlgorithm]; phAlgorithm
0x180059631  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180059638  nop     dword ptr [rax+rax+00h]
0x18005963d  test    eax, eax
0x18005963f  jns     short loc_180059678
0x180059641  mov     rcx, [rbp+1E8h]; this
0x180059648  mov     r9d, eax; char *
0x18005964b  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180059652  mov     edx, 859h; void *
0x180059657  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005965c  mov     ebx, eax
0x18005965e  mov     rcx, [rbp+1E0h+phAlgorithm]; this
0x180059665  test    rcx, rcx
0x180059668  jz      loc_1800599B6
0x18005966e  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x180059673  jmp     loc_1800599B6
0x180059678  mov     [rbp+1E0h+phKey], r14
0x18005967f  xor     r9d, r9d; dwFlags
0x180059682  mov     r8d, [rbx+2A4h]; dwLength
0x180059689  lea     rdx, [rbp+1E0h+phKey]; phKey
0x180059690  mov     rcx, [rbp+1E0h+phAlgorithm]; hAlgorithm
0x180059697  call    cs:__imp_BCryptGenerateKeyPair
0x18005969e  nop     dword ptr [rax+rax+00h]
0x1800596a3  test    eax, eax
0x1800596a5  jns     short loc_1800596E1
0x1800596a7  mov     edx, 85Fh; void *
0x1800596ac  mov     rcx, [rbp+1E8h]; this
0x1800596b3  mov     r9d, eax; char *
0x1800596b6  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800596bd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800596c2  mov     ebx, eax
0x1800596c4  lea     rcx, [rbp+1E0h+phKey]
0x1800596cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800596d0  lea     rcx, [rbp+1E0h+phAlgorithm]
0x1800596d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800596dc  jmp     loc_1800599B6
0x1800596e1  xor     edx, edx; dwFlags
0x1800596e3  mov     rcx, [rbp+1E0h+phKey]; hKey
0x1800596ea  call    cs:__imp_BCryptFinalizeKeyPair
0x1800596f1  nop     dword ptr [rax+rax+00h]
0x1800596f6  test    eax, eax
0x1800596f8  jns     short loc_180059701
0x1800596fa  mov     edx, 861h
0x1800596ff  jmp     short loc_1800596AC
0x180059701  mov     [rbp+1E0h+arg_0], r14d
0x180059708  mov     [rsp+2E0h+dwFlags], r14d; dwFlags
0x18005970d  lea     rax, [rbp+1E0h+arg_0]
0x180059714  mov     [rsp+2E0h+pcbResult], rax; pcbResult
0x180059719  mov     [rsp+2E0h+cbOutput], r14d; cbOutput
0x18005971e  xor     r9d, r9d; pbOutput
0x180059721  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180059728  xor     edx, edx; hExportKey
0x18005972a  mov     rcx, [rbp+1E0h+phKey]; hKey
0x180059731  call    cs:__imp_BCryptExportKey
0x180059738  nop     dword ptr [rax+rax+00h]
0x18005973d  test    eax, eax
0x18005973f  jns     short loc_18005974B
0x180059741  mov     edx, 86Ah
0x180059746  jmp     loc_1800596AC
0x18005974b  mov     edx, [rbp+1E0h+arg_0]
0x180059751  lea     rcx, [rsp+2E0h+pbOutput]
0x180059756  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18005975b  mov     eax, [rbp+1E0h+arg_0]
0x180059761  mov     [rsp+2E0h+dwFlags], r14d; dwFlags
0x180059766  lea     rcx, [rbp+1E0h+arg_0]
0x18005976d  mov     [rsp+2E0h+pcbResult], rcx; pcbResult
0x180059772  mov     [rsp+2E0h+cbOutput], eax; int
0x180059776  mov     rdi, [rsp+2E0h+pbOutput]
0x18005977b  mov     r9, rdi; pbOutput
0x18005977e  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180059785  xor     edx, edx; hExportKey
0x180059787  mov     rcx, [rbp+1E0h+phKey]; hKey
0x18005978e  call    cs:__imp_BCryptExportKey
0x180059795  nop     dword ptr [rax+rax+00h]
0x18005979a  test    eax, eax
0x18005979c  jns     short loc_1800597D1
0x18005979e  mov     rcx, [rbp+1E8h]; this
0x1800597a5  mov     r9d, eax; char *
0x1800597a8  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800597af  mov     edx, 874h; void *
0x1800597b4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800597b9  mov     ebx, eax
0x1800597bb  test    rdi, rdi
0x1800597be  jz      loc_1800596C4
0x1800597c4  mov     rcx, rdi; void *
0x1800597c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800597cc  jmp     loc_1800596C4
0x1800597d1  mov     [rbx+288h], rdi
0x1800597d8  mov     eax, [rbp+1E0h+arg_0]
0x1800597de  mov     [rbx+290h], eax
0x1800597e4  mov     [rbp+1E0h+arg_0], r14d
0x1800597eb  lea     rcx, [rbp+1E0h+phKey]
0x1800597f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800597f7  lea     rcx, [rbp+1E0h+phAlgorithm]
0x1800597fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180059803  cmp     [rbx+60h], r14
0x180059807  jnz     short loc_18005984D
0x180059809  cmp     [rbx+1D0h], r14d
0x180059810  jnz     short loc_18005984D
0x180059812  cmp     [rbx+288h], r14
0x180059819  jz      short loc_18005984D
0x18005981b  mov     rcx, rbx; this
0x18005981e  call    ?PerformKeyImport@TpmKey20Rsa@@MEAAJXZ; TpmKey20Rsa::PerformKeyImport(void)
0x180059823  mov     ebx, eax
0x180059825  test    eax, eax
0x180059827  jns     loc_180059B31
0x18005982d  mov     r9d, eax; char *
0x180059830  mov     edx, 883h; void *
0x180059835  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005983c  mov     rcx, [rbp+1E8h]; this
0x180059843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059848  jmp     loc_1800599B6
0x18005984d  cmp     [rbx+410h], r14d
0x180059854  jz      short loc_180059865
0x180059856  mov     ebx, 8029041Fh
0x18005985b  mov     r9d, ebx
0x18005985e  mov     edx, 887h
0x180059863  jmp     short loc_180059835
0x180059865  lea     rcx, [rsp+2E0h+var_280]; this
0x18005986a  call    ??0TPMW8_Create@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Create::TPMW8_Create(void)
0x18005986f  nop
0x180059870  mov     word ptr [rbp+1E0h+arg_8], r14w
0x180059878  lea     r9, [rbp+1E0h+arg_8]; unsigned __int16 *
0x18005987f  lea     r8, [rbp+1E0h+var_1B0]; struct tpm12class::TPMW82B_BUFFER *
0x180059883  lea     rdx, [rbp+1E0h+var_1B8]; unsigned int *
0x180059887  mov     rcx, rbx; this
0x18005988a  call    ?ReadParent@TpmKey20@@MEAAJPEAIPEAVTPMW82B_BUFFER@tpm12class@@PEAG@Z; TpmKey20::ReadParent(uint *,tpm12class::TPMW82B_BUFFER *,ushort *)
0x18005988f  mov     edi, eax
0x180059891  test    eax, eax
0x180059893  jns     short loc_1800598C2
0x180059895  mov     edx, 88Dh; void *
0x18005989a  mov     rcx, [rbp+1E8h]; this
0x1800598a1  mov     r9d, edi; char *
0x1800598a4  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800598ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800598b0  nop
0x1800598b1  lea     rcx, [rsp+2E0h+var_280]; this
0x1800598b6  call    ??1TPMW8_Create@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Create::~TPMW8_Create(void)
0x1800598bb  mov     ebx, edi
0x1800598bd  jmp     loc_1800599B6
0x1800598c2  movzx   r9d, word ptr [rbp+1E0h+arg_8]; unsigned __int16
0x1800598ca  mov     r8, [rbp+1E0h+var_168]; struct tpm12class::TPMW8S_SENSITIVE_CREATE *
0x1800598ce  mov     rdx, [rbp+1E0h+var_160]; struct tpm12class::TPMW8T_PUBLIC *
0x1800598d5  mov     rcx, rbx; this
0x1800598d8  call    ?SetCommonRsaKeyAttributes@TpmKey20Rsa@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAVTPMW8S_SENSITIVE_CREATE@3@G@Z; TpmKey20Rsa::SetCommonRsaKeyAttributes(tpm12class::TPMW8T_PUBLIC *,tpm12class::TPMW8S_SENSITIVE_CREATE *,ushort)
0x1800598dd  mov     edi, eax
0x1800598df  test    eax, eax
0x1800598e1  jns     short loc_1800598EA
0x1800598e3  mov     edx, 892h
0x1800598e8  jmp     short loc_18005989A
0x1800598ea  mov     rdx, [rbp+1E0h+var_160]; struct tpm12class::TPMW8T_PUBLIC *
0x1800598f1  mov     rcx, rbx; this
0x1800598f4  call    ?SetPublicFromMigrationAuth@TpmKey20@@MEAAJPEAVTPMW8T_PUBLIC@tpm12class@@@Z; TpmKey20::SetPublicFromMigrationAuth(tpm12class::TPMW8T_PUBLIC *)
0x1800598f9  mov     edi, eax
0x1800598fb  test    eax, eax
0x1800598fd  jns     short loc_180059906
0x1800598ff  mov     edx, 894h
0x180059904  jmp     short loc_18005989A
0x180059906  xor     edx, edx; void *
0x180059908  lea     rcx, [rsp+2E0h+var_280]; this
0x18005990d  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180059912  mov     edi, eax
0x180059914  test    eax, eax
0x180059916  jns     short loc_180059922
0x180059918  mov     edx, 896h
0x18005991d  jmp     loc_18005989A
0x180059922  mov     rdx, [rbp+1E0h+var_80]; struct tpm12class::TPMW8T_PUBLIC *
0x180059929  mov     rcx, rbx; this
0x18005992c  call    ?VerifyPublicKeyStrength@TpmKey20Rsa@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@@Z; TpmKey20Rsa::VerifyPublicKeyStrength(tpm12class::TPMW8T_PUBLIC *)
0x180059931  mov     edi, eax
0x180059933  test    eax, eax
0x180059935  jns     short loc_180059941
0x180059937  mov     edx, 898h
0x18005993c  jmp     loc_18005989A
0x180059941  lea     rcx, [rbx+68h]; this
0x180059945  lea     rdx, [rbp+1E0h+var_C8]; struct tpm12class::TPMW82B_BUFFER *
0x18005994c  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x180059951  mov     edi, eax
0x180059953  test    eax, eax
0x180059955  jns     short loc_180059961
0x180059957  mov     edx, 89Ah
0x18005995c  jmp     loc_18005989A
0x180059961  mov     rcx, [rbx+60h]
0x180059965  test    rcx, rcx
0x180059968  jz      short loc_18005997B
0x18005996a  mov     rax, [rcx]
0x18005996d  mov     edx, 1
0x180059972  mov     rax, [rax+20h]
0x180059976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005997b  mov     [rbx+60h], r14
0x18005997f  mov     rdx, [rbp+1E0h+var_80]
0x180059986  lea     rcx, [rsp+2E0h+pbOutput]
0x18005998b  call    ??$make_unique_nothrow@VTPMW8T_PUBLIC@tpm12class@@AEAV12@@wil@@YA?AV?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(tpm12class::TPMW8T_PUBLIC &)
0x180059990  mov     rax, [rsp+2E0h+pbOutput]
0x180059995  xor     edx, edx
0x180059997  lea     rcx, [rsp+2E0h+pbOutput]
0x18005999c  test    rax, rax
0x18005999f  jnz     short loc_1800599D1
0x1800599a1  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x1800599a6  nop
0x1800599a7  lea     rcx, [rsp+2E0h+var_280]; this
0x1800599ac  call    ??1TPMW8_Create@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Create::~TPMW8_Create(void)
0x1800599b1  mov     ebx, 80070008h
0x1800599b6  lea     rcx, [rsp+2E0h+var_298]; this
0x1800599bb  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800599c0  mov     eax, ebx
0x1800599c2  add     rsp, 2C0h
0x1800599c9  pop     r14
0x1800599cb  pop     rdi
0x1800599cc  pop     rsi
0x1800599cd  pop     rbx
0x1800599ce  pop     rbp
0x1800599cf  retn
0x1800599d1  mov     [rsp+2E0h+pbOutput], r14
0x1800599d6  mov     [rbx+60h], rax
0x1800599da  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x1800599df  mov     [rbp+1E0h+arg_8], r14d
0x1800599e6  lea     r9, [rbp+1E0h+arg_8]; unsigned int *
0x1800599ed  xor     r8d, r8d; unsigned int
0x1800599f0  xor     edx, edx; unsigned __int8 *
0x1800599f2  lea     rcx, [rbp+1E0h+var_70]; this
0x1800599f9  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x1800599fe  mov     edi, eax
0x180059a00  test    eax, eax
0x180059a02  jns     short loc_180059A0E
0x180059a04  mov     edx, 8A6h
0x180059a09  jmp     loc_18005989A
0x180059a0e  lea     rdi, [rbx+2C8h]
0x180059a15  mov     [rdi], r14d
0x180059a18  mov     rcx, [rbx+2C0h]; void *
0x180059a1f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180059a24  mov     [rbx+2C0h], r14
0x180059a2b  mov     esi, [rbp+1E0h+arg_8]
0x180059a31  mov     edx, esi
0x180059a33  lea     rcx, [rsp+2E0h+pbOutput]
0x180059a38  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180059a3d  mov     rdx, [rsp+2E0h+pbOutput]; unsigned __int8 *
0x180059a42  test    rdx, rdx
0x180059a45  jz      loc_1800599A7
0x180059a4b  mov     [rbx+2C0h], rdx
0x180059a52  mov     [rdi], esi
0x180059a54  mov     r9, rdi; unsigned int *
0x180059a57  mov     r8d, esi; unsigned int
0x180059a5a  lea     rcx, [rbp+1E0h+var_70]; this
0x180059a61  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x180059a66  mov     edi, eax
0x180059a68  test    eax, eax
0x180059a6a  jns     short loc_180059A76
0x180059a6c  mov     edx, 8ACh
0x180059a71  jmp     loc_18005989A
0x180059a76  lea     r9, [rbp+1E0h+arg_8]; unsigned int *
0x180059a7d  xor     r8d, r8d; unsigned int
0x180059a80  xor     edx, edx; unsigned __int8 *
0x180059a82  mov     rcx, [rbp+1E0h+var_28]; this
0x180059a89  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x180059a8e  mov     edi, eax
0x180059a90  test    eax, eax
0x180059a92  jns     short loc_180059A9E
0x180059a94  mov     edx, 8B0h
0x180059a99  jmp     loc_18005989A
0x180059a9e  lea     rdi, [rbx+2D8h]
0x180059aa5  mov     [rdi], r14d
0x180059aa8  mov     rcx, [rbx+2D0h]; void *
0x180059aaf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180059ab4  mov     [rbx+2D0h], r14
0x180059abb  mov     esi, [rbp+1E0h+arg_8]
0x180059ac1  mov     edx, esi
0x180059ac3  lea     rcx, [rsp+2E0h+pbOutput]
0x180059ac8  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180059acd  mov     rdx, [rsp+2E0h+pbOutput]; unsigned __int8 *
0x180059ad2  test    rdx, rdx
0x180059ad5  jz      loc_1800599A7
0x180059adb  mov     [rbx+2D0h], rdx
0x180059ae2  mov     [rdi], esi
0x180059ae4  mov     r9, rdi; unsigned int *
  ... truncated ...
```
