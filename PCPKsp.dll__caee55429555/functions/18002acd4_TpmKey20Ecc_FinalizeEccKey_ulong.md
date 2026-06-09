# TpmKey20Ecc::FinalizeEccKey(ulong)

- ea: `0x18002acd4`
- end: `0x18002b3c7`
- name: `?FinalizeEccKey@TpmKey20Ecc@@IEAAJK@Z`
- size: `1779`
- prototype: `__int64 __fastcall(TpmKey20Ecc *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005c2c0`
- `0x18008f310`

## callees

- `0x180010c90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800294d4`
- `0x180029a20`
- `0x18002acd4`
- `0x18002b3d0`
- `0x18002b50c`
- `0x18002d890`
- `0x180032110`
- `0x18003335c`
- `0x180034464`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x180065d78`
- `0x1800768a0`
- `0x18007bdbc`
- `0x180091a64`
- `0x1800921a0`
- `0x1800c8010`

## import_xrefs

- `bcrypt!BCryptGenerateKeyPair` at `0x18002adad`
- `bcrypt!BCryptGenerateKeyPair` at `0x18002adad`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18002adfb`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18002adfb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002ad4f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002ad4f`
- `bcrypt!BCryptExportKey` at `0x18002ae40`
- `bcrypt!BCryptExportKey` at `0x18002aebf`
- `bcrypt!BCryptExportKey` at `0x18002ae40`
- `bcrypt!BCryptExportKey` at `0x18002aebf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TpmKey20Ecc::FinalizeEccKey(TpmKey20Ecc *this, char a2)
{
  NTSTATUS v4; // eax
  void *v5; // rdx
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  PUCHAR v9; // rdi
  NTSTATUS v10; // eax
  const struct std::nothrow_t *v11; // rdx
  int v12; // esi
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  unsigned int v16; // r14d
  const struct std::nothrow_t *v17; // rdx
  unsigned __int8 *v18; // r8
  const struct std::nothrow_t *v19; // rdx
  int v20; // eax
  int v21; // edi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v25; // rdx
  const struct std::nothrow_t *v26; // rdx
  unsigned int v27; // esi
  unsigned __int8 *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  unsigned int v30; // esi
  unsigned __int8 *v31; // rdx
  int v32; // eax
  int cbOutput; // [rsp+20h] [rbp-E0h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 *v36; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v38[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[200]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v41[72]; // [rsp+160h] [rbp+60h] BYREF
  struct tpm12class::TPMW8S_SENSITIVE_CREATE *v42; // [rsp+1A8h] [rbp+A8h]
  struct tpm12class::TPMW8T_PUBLIC *v43; // [rsp+1B0h] [rbp+B0h]
  _BYTE v44[72]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v45; // [rsp+290h] [rbp+190h]
  _QWORD v46[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned int v47; // [rsp+2B0h] [rbp+1B0h]
  tpm12class::TpmDataObject *v48; // [rsp+2E8h] [rbp+1E8h]
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]
  unsigned __int16 v50; // [rsp+320h] [rbp+220h] BYREF
  ULONG pcbResult; // [rsp+330h] [rbp+230h] BYREF
  PUCHAR pbOutput; // [rsp+338h] [rbp+238h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v38, L"TpmKey20Ecc::FinalizeEccKey", 1);
  if ( (!*((_DWORD *)this + 160) || *((_DWORD *)this + 170) != 65540 || *((_QWORD *)this + 81)) && (a2 & 0xC) == 0 )
    goto LABEL_36;
  phAlgorithm = 0;
  v4 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"ECDSA", L"Microsoft Primitive Provider", 0);
  if ( v4 < 0 )
  {
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x2E5,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
           (const char *)(unsigned int)v4,
           cbOutput);
    if ( phAlgorithm )
      wil::details::BCryptCloseAlgorithmProviderNoFlags((wil::details *)phAlgorithm, v5);
    goto LABEL_58;
  }
  phKey = 0;
  v7 = BCryptGenerateKeyPair(phAlgorithm, &phKey, *((_DWORD *)this + 169), 0);
  if ( v7 < 0 )
  {
    v8 = 747;
LABEL_10:
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v8,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
           (const char *)(unsigned int)v7,
           cbOutput);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    goto LABEL_58;
  }
  v7 = BCryptFinalizeKeyPair(phKey, 0);
  if ( v7 < 0 )
  {
    v8 = 749;
    goto LABEL_10;
  }
  pcbResult = 0;
  v7 = BCryptExportKey(phKey, 0, L"ECCFULLPRIVATEBLOB", 0, 0, &pcbResult, 0);
  if ( v7 < 0 )
  {
    v8 = 758;
    goto LABEL_10;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, pcbResult);
  v9 = pbOutput;
  if ( !pbOutput )
    goto LABEL_17;
  v10 = BCryptExportKey(phKey, 0, L"ECCFULLPRIVATEBLOB", pbOutput, pcbResult, &pcbResult, 0);
  if ( v10 < 0 )
  {
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x300,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
           (const char *)(unsigned int)v10,
           cbOutput);
    if ( v9 )
      operator delete(v9, v11);
    goto LABEL_11;
  }
  v12 = CurveIdFromFullKeyBlob(v9, pcbResult, (unsigned __int16 *)this + 512);
  if ( v12 >= 0 )
  {
    LODWORD(pbOutput) = 0;
    v12 = KeyBlobFromFullKeyBlob(v9, pcbResult, 0, 0, (unsigned int *)&pbOutput);
    if ( v12 < 0 )
    {
      v13 = 775;
      goto LABEL_23;
    }
    *((_DWORD *)this + 164) = 0;
    operator delete(*((void **)this + 81), v15);
    *((_QWORD *)this + 81) = 0;
    v16 = (unsigned int)pbOutput;
    wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, (unsigned int)pbOutput);
    v18 = pbOutput;
    if ( !pbOutput )
    {
      if ( v9 )
        operator delete(v9, v17);
LABEL_17:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_57:
      v6 = -2147024888;
      goto LABEL_58;
    }
    *((_QWORD *)this + 81) = pbOutput;
    *((_DWORD *)this + 164) = v16;
    v12 = KeyBlobFromFullKeyBlob(v9, pcbResult, v18, v16, (unsigned int *)this + 164);
    if ( v12 < 0 )
    {
      v13 = 779;
      goto LABEL_23;
    }
    if ( v9 )
      operator delete(v9, v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_36:
    if ( !*((_QWORD *)this + 12) && !*((_DWORD *)this + 116) && *((_QWORD *)this + 81) )
    {
      v20 = (*(__int64 (__fastcall **)(TpmKey20Ecc *))(*(_QWORD *)this + 1224LL))(this);
      v6 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x313,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
          (const char *)(unsigned int)v20,
          cbOutput);
        goto LABEL_58;
      }
LABEL_72:
      v6 = 0;
      goto LABEL_58;
    }
    tpm12class::TPMW8_Create::TPMW8_Create((tpm12class::TPMW8_Create *)v39);
    v50 = 0;
    v21 = (*(__int64 (__fastcall **)(TpmKey20Ecc *, _BYTE *, _BYTE *, unsigned __int16 *))(*(_QWORD *)this + 1256LL))(
            this,
            v40,
            v41,
            &v50);
    if ( v21 >= 0 )
    {
      v21 = TpmKey20Ecc::SetCommonEccKeyAttributes(this, v43, v42, v50);
      if ( v21 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(TpmKey20Ecc *, struct tpm12class::TPMW8T_PUBLIC *))(*(_QWORD *)this + 1232LL))(
                this,
                v43);
        if ( v21 >= 0 )
        {
          v21 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v39, 0);
          if ( v21 >= 0 )
          {
            KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v37, L"TpmKey20Ecc::VerifyPublicKeyStrength", 0);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v37);
            v21 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                    (TpmKey20Ecc *)((char *)this + 104),
                    (const struct tpm12class::TPMW82B_BUFFER *)v44);
            if ( v21 >= 0 )
            {
              v23 = *((_QWORD *)this + 12);
              if ( v23 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 32LL))(v23, 1);
              *((_QWORD *)this + 12) = 0;
              wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(&pbOutput, v45);
              if ( pbOutput )
              {
                *((_QWORD *)this + 12) = pbOutput;
                LODWORD(pbOutput) = 0;
                v21 = tpm12class::TpmDataObject::Clear((tpm12class::TpmDataObject *)v46, 0);
                if ( v21 < 0
                  || (LOBYTE(v25) = 1,
                      v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v46[0] + 16LL))(v46, v25),
                      v21 < 0)
                  || (v21 = (*(__int64 (__fastcall **)(_QWORD *))v46[0])(v46), v21 < 0) )
                {
                  v22 = 818;
                  goto LABEL_43;
                }
                v27 = v47;
                LODWORD(pbOutput) = v47;
                *((_DWORD *)this + 178) = 0;
                operator delete(*((void **)this + 88), v26);
                *((_QWORD *)this + 88) = 0;
                wil::make_unique_nothrow<unsigned char [0]>(&v36, v27);
                v28 = v36;
                if ( v36 )
                {
                  *((_QWORD *)this + 88) = v36;
                  *((_DWORD *)this + 178) = v27;
                  v21 = tpm12class::TpmDataObject::Get(
                          (tpm12class::TpmDataObject *)v46,
                          v28,
                          v27,
                          (unsigned int *)this + 178);
                  if ( v21 < 0 )
                  {
                    v22 = 824;
                    goto LABEL_43;
                  }
                  v21 = tpm12class::TpmDataObject::Get(v48, 0, 0, (unsigned int *)&pbOutput);
                  if ( v21 < 0 )
                  {
                    v22 = 828;
                    goto LABEL_43;
                  }
                  *((_DWORD *)this + 182) = 0;
                  operator delete(*((void **)this + 90), v29);
                  *((_QWORD *)this + 90) = 0;
                  v30 = (unsigned int)pbOutput;
                  wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, (unsigned int)pbOutput);
                  v31 = pbOutput;
                  if ( pbOutput )
                  {
                    *((_QWORD *)this + 90) = pbOutput;
                    *((_DWORD *)this + 182) = v30;
                    v32 = tpm12class::TpmDataObject::Get(v48, v31, v30, (unsigned int *)this + 182);
                    v6 = v32;
                    if ( v32 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x342,
                        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
                        (const char *)(unsigned int)v32,
                        cbOutput);
                      tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v39);
                      goto LABEL_58;
                    }
                    tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v39);
                    goto LABEL_72;
                  }
                }
              }
              else
              {
                wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
                  &pbOutput,
                  0);
              }
              tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v39);
              goto LABEL_57;
            }
            v22 = 807;
          }
          else
          {
            v22 = 803;
          }
        }
        else
        {
          v22 = 801;
        }
      }
      else
      {
        v22 = 799;
      }
    }
    else
    {
      v22 = 795;
    }
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
      (const char *)(unsigned int)v21,
      cbOutput);
    tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v39);
    v6 = v21;
    goto LABEL_58;
  }
  v13 = 773;
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecc.cpp",
    (const char *)(unsigned int)v12,
    cbOutput);
  if ( v9 )
    operator delete(v9, v14);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  v6 = v12;
LABEL_58:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v38);
  return v6;
}

```

## disassembly

```asm
0x18002acd4  mov     [rsp-8+arg_8], rbx
0x18002acd9  push    rbp
0x18002acda  push    rsi
0x18002acdb  push    rdi
0x18002acdc  push    r14
0x18002acde  push    r15
0x18002ace0  lea     rbp, [rsp-1F0h]
0x18002ace8  sub     rsp, 2F0h
0x18002acef  mov     edi, edx
0x18002acf1  mov     rbx, rcx
0x18002acf4  mov     r8b, 1; bool
0x18002acf7  lea     rdx, aTpmkey20eccFin_0; "TpmKey20Ecc::FinalizeEccKey"
0x18002acfe  lea     rcx, [rsp+310h+var_2A0]; this
0x18002ad03  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18002ad08  nop
0x18002ad09  xor     r15d, r15d
0x18002ad0c  cmp     [rbx+280h], r15d
0x18002ad13  jz      short loc_18002AD2A
0x18002ad15  cmp     dword ptr [rbx+2A8h], 10004h
0x18002ad1f  jnz     short loc_18002AD2A
0x18002ad21  cmp     [rbx+288h], r15
0x18002ad28  jz      short loc_18002AD34
0x18002ad2a  test    dil, 0Ch
0x18002ad2e  jz      loc_18002B03F
0x18002ad34  mov     [rsp+310h+phAlgorithm], r15
0x18002ad39  xor     r9d, r9d; dwFlags
0x18002ad3c  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18002ad43  lea     rdx, aEcdsa; "ECDSA"
0x18002ad4a  lea     rcx, [rsp+310h+phAlgorithm]; phAlgorithm
0x18002ad4f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002ad56  nop     dword ptr [rax+rax+00h]
0x18002ad5b  test    eax, eax
0x18002ad5d  jns     short loc_18002AD94
0x18002ad5f  mov     rcx, [rbp+218h]; this
0x18002ad66  mov     r9d, eax; char *
0x18002ad69  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002ad70  mov     edx, 2E5h; void *
0x18002ad75  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002ad7a  mov     ebx, eax
0x18002ad7c  mov     rcx, [rsp+310h+phAlgorithm]; this
0x18002ad81  test    rcx, rcx
0x18002ad84  jz      loc_18002B1FC
0x18002ad8a  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x18002ad8f  jmp     loc_18002B1FC
0x18002ad94  mov     [rsp+310h+phKey], r15
0x18002ad99  xor     r9d, r9d; dwFlags
0x18002ad9c  mov     r8d, [rbx+2A4h]; dwLength
0x18002ada3  lea     rdx, [rsp+310h+phKey]; phKey
0x18002ada8  mov     rcx, [rsp+310h+phAlgorithm]; hAlgorithm
0x18002adad  call    cs:__imp_BCryptGenerateKeyPair
0x18002adb4  nop     dword ptr [rax+rax+00h]
0x18002adb9  test    eax, eax
0x18002adbb  jns     short loc_18002ADF4
0x18002adbd  mov     edx, 2EBh; void *
0x18002adc2  mov     rcx, [rbp+218h]; this
0x18002adc9  mov     r9d, eax; char *
0x18002adcc  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002add3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002add8  mov     ebx, eax
0x18002adda  lea     rcx, [rsp+310h+phKey]
0x18002addf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002ade4  nop
0x18002ade5  lea     rcx, [rsp+310h+phAlgorithm]
0x18002adea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002adef  jmp     loc_18002B1FC
0x18002adf4  xor     edx, edx; dwFlags
0x18002adf6  mov     rcx, [rsp+310h+phKey]; hKey
0x18002adfb  call    cs:__imp_BCryptFinalizeKeyPair
0x18002ae02  nop     dword ptr [rax+rax+00h]
0x18002ae07  test    eax, eax
0x18002ae09  jns     short loc_18002AE12
0x18002ae0b  mov     edx, 2EDh
0x18002ae10  jmp     short loc_18002ADC2
0x18002ae12  mov     [rbp+210h+arg_10], r15d
0x18002ae19  mov     [rsp+310h+dwFlags], r15d; dwFlags
0x18002ae1e  lea     rax, [rbp+210h+arg_10]
0x18002ae25  mov     [rsp+310h+pcbResult], rax; pcbResult
0x18002ae2a  mov     [rsp+310h+cbOutput], r15d; cbOutput
0x18002ae2f  xor     r9d, r9d; pbOutput
0x18002ae32  lea     r8, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x18002ae39  xor     edx, edx; hExportKey
0x18002ae3b  mov     rcx, [rsp+310h+phKey]; hKey
0x18002ae40  call    cs:__imp_BCryptExportKey
0x18002ae47  nop     dword ptr [rax+rax+00h]
0x18002ae4c  test    eax, eax
0x18002ae4e  jns     short loc_18002AE5A
0x18002ae50  mov     edx, 2F6h
0x18002ae55  jmp     loc_18002ADC2
0x18002ae5a  mov     edx, [rbp+210h+arg_10]
0x18002ae60  lea     rcx, [rbp+210h+pbOutput]
0x18002ae67  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18002ae6c  nop
0x18002ae6d  mov     rdi, [rbp+210h+pbOutput]
0x18002ae74  test    rdi, rdi
0x18002ae77  jnz     short loc_18002AE93
0x18002ae79  lea     rcx, [rsp+310h+phKey]
0x18002ae7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002ae83  nop
0x18002ae84  lea     rcx, [rsp+310h+phAlgorithm]
0x18002ae89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ae8e  jmp     loc_18002B1F7
0x18002ae93  mov     eax, [rbp+210h+arg_10]
0x18002ae99  mov     [rsp+310h+dwFlags], r15d; dwFlags
0x18002ae9e  lea     rcx, [rbp+210h+arg_10]
0x18002aea5  mov     [rsp+310h+pcbResult], rcx; pcbResult
0x18002aeaa  mov     [rsp+310h+cbOutput], eax; int
0x18002aeae  mov     r9, rdi; pbOutput
0x18002aeb1  lea     r8, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x18002aeb8  xor     edx, edx; hExportKey
0x18002aeba  mov     rcx, [rsp+310h+phKey]; hKey
0x18002aebf  call    cs:__imp_BCryptExportKey
0x18002aec6  nop     dword ptr [rax+rax+00h]
0x18002aecb  test    eax, eax
0x18002aecd  jns     short loc_18002AF02
0x18002aecf  mov     rcx, [rbp+218h]; this
0x18002aed6  mov     r9d, eax; char *
0x18002aed9  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002aee0  mov     edx, 300h; void *
0x18002aee5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002aeea  mov     ebx, eax
0x18002aeec  test    rdi, rdi
0x18002aeef  jz      loc_18002ADDA
0x18002aef5  mov     rcx, rdi; void *
0x18002aef8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002aefd  jmp     loc_18002ADDA
0x18002af02  lea     r8, [rbx+400h]; unsigned __int16 *
0x18002af09  mov     edx, [rbp+210h+arg_10]; unsigned int
0x18002af0f  mov     rcx, rdi; unsigned __int8 *
0x18002af12  call    ?CurveIdFromFullKeyBlob@@YAJPEBEKPEAG@Z; CurveIdFromFullKeyBlob(uchar const *,ulong,ushort *)
0x18002af17  mov     esi, eax
0x18002af19  test    eax, eax
0x18002af1b  jns     short loc_18002AF63
0x18002af1d  mov     edx, 305h; void *
0x18002af22  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002af29  mov     r9d, esi; char *
0x18002af2c  mov     rcx, [rbp+218h]; this
0x18002af33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af38  nop
0x18002af39  test    rdi, rdi
0x18002af3c  jz      short loc_18002AF47
0x18002af3e  mov     rcx, rdi; void *
0x18002af41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002af46  nop
0x18002af47  lea     rcx, [rsp+310h+phKey]
0x18002af4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002af51  nop
0x18002af52  lea     rcx, [rsp+310h+phAlgorithm]
0x18002af57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002af5c  mov     ebx, esi
0x18002af5e  jmp     loc_18002B1FC
0x18002af63  mov     dword ptr [rbp+210h+pbOutput], r15d
0x18002af6a  lea     rax, [rbp+210h+pbOutput]
0x18002af71  mov     qword ptr [rsp+310h+cbOutput], rax; unsigned int *
0x18002af76  xor     r9d, r9d; unsigned int
0x18002af79  xor     r8d, r8d; unsigned __int8 *
0x18002af7c  mov     edx, [rbp+210h+arg_10]; unsigned int
0x18002af82  mov     rcx, rdi; unsigned __int8 *
0x18002af85  call    ?KeyBlobFromFullKeyBlob@@YAJPEBEKPEAEKPEAK@Z; KeyBlobFromFullKeyBlob(uchar const *,ulong,uchar *,ulong,ulong *)
0x18002af8a  mov     esi, eax
0x18002af8c  test    eax, eax
0x18002af8e  jns     short loc_18002AF97
0x18002af90  mov     edx, 307h
0x18002af95  jmp     short loc_18002AF22
0x18002af97  lea     rsi, [rbx+290h]
0x18002af9e  mov     [rsi], r15d
0x18002afa1  mov     rcx, [rbx+288h]; void *
0x18002afa8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002afad  mov     [rbx+288h], r15
0x18002afb4  mov     r14d, dword ptr [rbp+210h+pbOutput]
0x18002afbb  mov     edx, r14d
0x18002afbe  lea     rcx, [rbp+210h+pbOutput]
0x18002afc5  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18002afca  mov     r8, [rbp+210h+pbOutput]; unsigned __int8 *
0x18002afd1  test    r8, r8
0x18002afd4  jnz     short loc_18002AFEC
0x18002afd6  test    rdi, rdi
0x18002afd9  jz      loc_18002AE79
0x18002afdf  mov     rcx, rdi; void *
0x18002afe2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002afe7  jmp     loc_18002AE79
0x18002afec  mov     [rbx+288h], r8
0x18002aff3  mov     [rsi], r14d
0x18002aff6  mov     qword ptr [rsp+310h+cbOutput], rsi; int
0x18002affb  mov     r9d, r14d; unsigned int
0x18002affe  mov     edx, [rbp+210h+arg_10]; unsigned int
0x18002b004  mov     rcx, rdi; unsigned __int8 *
0x18002b007  call    ?KeyBlobFromFullKeyBlob@@YAJPEBEKPEAEKPEAK@Z; KeyBlobFromFullKeyBlob(uchar const *,ulong,uchar *,ulong,ulong *)
0x18002b00c  mov     esi, eax
0x18002b00e  test    eax, eax
0x18002b010  jns     short loc_18002B01C
0x18002b012  mov     edx, 30Bh
0x18002b017  jmp     loc_18002AF22
0x18002b01c  test    rdi, rdi
0x18002b01f  jz      short loc_18002B02A
0x18002b021  mov     rcx, rdi; void *
0x18002b024  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b029  nop
0x18002b02a  lea     rcx, [rsp+310h+phKey]
0x18002b02f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b034  nop
0x18002b035  lea     rcx, [rsp+310h+phAlgorithm]
0x18002b03a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b03f  cmp     [rbx+60h], r15
0x18002b043  jnz     short loc_18002B093
0x18002b045  cmp     [rbx+1D0h], r15d
0x18002b04c  jnz     short loc_18002B093
0x18002b04e  cmp     [rbx+288h], r15
0x18002b055  jz      short loc_18002B093
0x18002b057  mov     rax, [rbx]
0x18002b05a  mov     rcx, rbx
0x18002b05d  mov     rax, [rax+4C8h]
0x18002b064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b069  mov     ebx, eax
0x18002b06b  test    eax, eax
0x18002b06d  jns     loc_18002B3BE
0x18002b073  mov     rcx, [rbp+218h]; this
0x18002b07a  mov     r9d, eax; char *
0x18002b07d  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002b084  mov     edx, 313h; void *
0x18002b089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b08e  jmp     loc_18002B1FC
0x18002b093  lea     rcx, [rbp+210h+var_280]; this
0x18002b097  call    ??0TPMW8_Create@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Create::TPMW8_Create(void)
0x18002b09c  nop
0x18002b09d  mov     [rbp+210h+arg_0], r15w
0x18002b0a5  mov     rax, [rbx]
0x18002b0a8  lea     r9, [rbp+210h+arg_0]
0x18002b0af  lea     r8, [rbp+210h+var_1B0]
0x18002b0b3  lea     rdx, [rbp+210h+var_1B8]
0x18002b0b7  mov     rcx, rbx
0x18002b0ba  mov     rax, [rax+4E8h]
0x18002b0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0c6  mov     edi, eax
0x18002b0c8  test    eax, eax
0x18002b0ca  jns     short loc_18002B0F8
0x18002b0cc  mov     edx, 31Bh; void *
0x18002b0d1  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002b0d8  mov     r9d, edi; char *
0x18002b0db  mov     rcx, [rbp+218h]; this
0x18002b0e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b0e7  nop
0x18002b0e8  lea     rcx, [rbp+210h+var_280]; this
0x18002b0ec  call    ??1TPMW8_Create@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Create::~TPMW8_Create(void)
0x18002b0f1  mov     ebx, edi
0x18002b0f3  jmp     loc_18002B1FC
0x18002b0f8  movzx   r9d, [rbp+210h+arg_0]; unsigned __int16
0x18002b100  mov     r8, [rbp+210h+var_168]; struct tpm12class::TPMW8S_SENSITIVE_CREATE *
0x18002b107  mov     rdx, [rbp+210h+var_160]; struct tpm12class::TPMW8T_PUBLIC *
0x18002b10e  mov     rcx, rbx; this
0x18002b111  call    ?SetCommonEccKeyAttributes@TpmKey20Ecc@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAVTPMW8S_SENSITIVE_CREATE@3@G@Z; TpmKey20Ecc::SetCommonEccKeyAttributes(tpm12class::TPMW8T_PUBLIC *,tpm12class::TPMW8S_SENSITIVE_CREATE *,ushort)
0x18002b116  mov     edi, eax
0x18002b118  test    eax, eax
0x18002b11a  jns     short loc_18002B123
0x18002b11c  mov     edx, 31Fh
0x18002b121  jmp     short loc_18002B0D1
0x18002b123  mov     rax, [rbx]
0x18002b126  mov     rdx, [rbp+210h+var_160]
0x18002b12d  mov     rcx, rbx
0x18002b130  mov     rax, [rax+4D0h]
0x18002b137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b13c  mov     edi, eax
0x18002b13e  test    eax, eax
0x18002b140  jns     short loc_18002B149
0x18002b142  mov     edx, 321h
0x18002b147  jmp     short loc_18002B0D1
0x18002b149  xor     edx, edx; void *
0x18002b14b  lea     rcx, [rbp+210h+var_280]; this
0x18002b14f  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x18002b154  mov     edi, eax
0x18002b156  test    eax, eax
0x18002b158  jns     short loc_18002B164
0x18002b15a  mov     edx, 323h
0x18002b15f  jmp     loc_18002B0D1
0x18002b164  xor     r8d, r8d; bool
0x18002b167  lea     rdx, aTpmkey20eccVer; "TpmKey20Ecc::VerifyPublicKeyStrength"
0x18002b16e  lea     rcx, [rsp+310h+var_2B8]; this
0x18002b173  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18002b178  lea     rcx, [rsp+310h+var_2B8]; this
0x18002b17d  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002b182  lea     rcx, [rbx+68h]; this
0x18002b186  lea     rdx, [rbp+210h+var_C8]; struct tpm12class::TPMW82B_BUFFER *
0x18002b18d  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x18002b192  mov     edi, eax
0x18002b194  test    eax, eax
0x18002b196  jns     short loc_18002B1A2
0x18002b198  mov     edx, 327h
0x18002b19d  jmp     loc_18002B0D1
0x18002b1a2  mov     rcx, [rbx+60h]
0x18002b1a6  test    rcx, rcx
0x18002b1a9  jz      short loc_18002B1BC
0x18002b1ab  mov     rax, [rcx]
0x18002b1ae  mov     edx, 1
0x18002b1b3  mov     rax, [rax+20h]
0x18002b1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1bc  mov     [rbx+60h], r15
0x18002b1c0  mov     rdx, [rbp+210h+var_80]
0x18002b1c7  lea     rcx, [rbp+210h+pbOutput]
0x18002b1ce  call    ??$make_unique_nothrow@VTPMW8T_PUBLIC@tpm12class@@AEAV12@@wil@@YA?AV?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(tpm12class::TPMW8T_PUBLIC &)
0x18002b1d3  mov     rax, [rbp+210h+pbOutput]
0x18002b1da  test    rax, rax
  ... truncated ...
```
