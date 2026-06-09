# BthLELib_SMPGenerateDHKey

- ea: `0x140207c78`
- end: `0x140208082`
- name: `BthLELib_SMPGenerateDHKey`
- size: `1034`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PUCHAR pbDerivedKey)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401fdd08`

## callees

- `0x140070298`
- `0x14015f170`
- `0x14015f1b0`
- `0x14015f1f0`
- `0x14015f230`
- `0x14015f298`
- `0x14015f2bc`
- `0x14015f2e0`
- `0x14015f308`
- `0x14015f3a4`
- `0x14015fa50`
- `0x140161a00`
- `0x140207c78`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140207cc3`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140207cc3`
- `ksecdd!BCryptDeriveKey` at `0x140208003`
- `ksecdd!BCryptDeriveKey` at `0x140208003`
- `ksecdd!BCryptImportKeyPair` at `0x140207e14`
- `ksecdd!BCryptImportKeyPair` at `0x140207ee9`
- `ksecdd!BCryptImportKeyPair` at `0x140207e14`
- `ksecdd!BCryptImportKeyPair` at `0x140207ee9`
- `ksecdd!BCryptSecretAgreement` at `0x140207f73`
- `ksecdd!BCryptSecretAgreement` at `0x140207f73`

## pseudocode

```c
__int64 __fastcall BthLELib_SMPGenerateDHKey(
        _OWORD *a1,
        _OWORD *a2,
        _OWORD *a3,
        _OWORD *a4,
        _OWORD *a5,
        PUCHAR pbDerivedKey)
{
  __int64 v10; // rax
  NTSTATUS v11; // ebx
  int v12; // edx
  __int64 v13; // rcx
  int v14; // r8d
  unsigned __int8 *Pool; // rax
  int v16; // edx
  int v17; // r8d
  PUCHAR pbInput; // rbx
  __int64 v19; // rax
  NTSTATUS v20; // edi
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rax
  int v24; // edx
  int v25; // r8d
  __int64 v26; // rax
  int v27; // edx
  int v28; // r8d
  int v29; // r9d
  BCRYPT_KEY_HANDLE hPrivKey; // [rsp+40h] [rbp-49h] BYREF
  BCRYPT_KEY_HANDLE hPubKey; // [rsp+48h] [rbp-41h] BYREF
  BCRYPT_SECRET_HANDLE hSharedSecret; // [rsp+50h] [rbp-39h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp-31h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-29h] BYREF
  PUCHAR v36[3]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v37[80]; // [rsp+80h] [rbp-9h] BYREF

  hAlgorithm = 0;
  v10 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
          v36,
          &hAlgorithm);
  v11 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(v10 + 8), L"ECDH_P256", L"Microsoft Primitive Provider", 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v36);
  if ( v11 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v14,
        22,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    goto LABEL_25;
  }
  v36[0] = 0;
  v36[1] = 0;
  Pool = (unsigned __int8 *)BthLELibAllocatePoolEx(v13, 104);
  unique_bthlelib_secure_pool::reset((unique_bthlelib_secure_pool *)v36, Pool, 0x68u);
  pbInput = v36[0];
  if ( !v36[0] )
  {
    v11 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        23,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    goto LABEL_7;
  }
  *(_DWORD *)v36[0] = 843793221;
  *((_DWORD *)pbInput + 1) = 32;
  *(_OWORD *)(pbInput + 8) = *a2;
  *(_OWORD *)(pbInput + 24) = a2[1];
  *(_OWORD *)(pbInput + 40) = *a3;
  *(_OWORD *)(pbInput + 56) = a3[1];
  *(_OWORD *)(pbInput + 72) = *a1;
  *(_OWORD *)(pbInput + 88) = a1[1];
  hPrivKey = 0;
  v19 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
          v37,
          &hPrivKey);
  v20 = BCryptImportKeyPair(hAlgorithm, 0, L"ECCPRIVATEBLOB", (BCRYPT_KEY_HANDLE *)(v19 + 8), pbInput, 0x68u, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v37);
  if ( v20 >= 0 )
  {
    *(_DWORD *)pbInput = 827016005;
    *((_DWORD *)pbInput + 1) = 32;
    *(_OWORD *)(pbInput + 8) = *a4;
    *(_OWORD *)(pbInput + 24) = a4[1];
    *(_OWORD *)(pbInput + 40) = *a5;
    *(_OWORD *)(pbInput + 56) = a5[1];
    hPubKey = 0;
    v23 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            v37,
            &hPubKey);
    v11 = BCryptImportKeyPair(hAlgorithm, 0, L"ECCPUBLICBLOB", (BCRYPT_KEY_HANDLE *)(v23 + 8), pbInput, 0x48u, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v37);
    if ( v11 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sd(
          WPP_GLOBAL_Control->DeviceExtension,
          v24,
          v25,
          25,
          (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
      goto LABEL_15;
    }
    hSharedSecret = 0;
    v26 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            v37,
            &hSharedSecret);
    v11 = BCryptSecretAgreement(hPrivKey, hPubKey, (BCRYPT_SECRET_HANDLE *)(v26 + 8), 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v37);
    if ( v11 >= 0 )
    {
      pcbResult = 0;
      v11 = BCryptDeriveKey(hSharedSecret, L"TRUNCATE", 0, pbDerivedKey, 0x20u, &pcbResult, 0);
      if ( v11 >= 0 )
      {
        utl::reverse<unsigned char *>(pbDerivedKey, pbDerivedKey + 32);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hSharedSecret);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPubKey);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrivKey);
        unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)v36);
        v11 = 0;
        goto LABEL_25;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_20;
      v29 = 27;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hSharedSecret);
LABEL_15:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPubKey);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrivKey);
LABEL_7:
        unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)v36);
        goto LABEL_25;
      }
      v29 = 26;
    }
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v27,
      v28,
      v29,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    goto LABEL_20;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      v22,
      24,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrivKey);
  unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)v36);
  v11 = v20;
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hAlgorithm);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140207c78  push    rbp
0x140207c7a  push    rbx
0x140207c7b  push    rsi
0x140207c7c  push    rdi
0x140207c7d  push    r14
0x140207c7f  push    r15
0x140207c81  lea     rbp, [rsp-1Fh]
0x140207c86  sub     rsp, 0A8h
0x140207c8d  mov     r14, rdx
0x140207c90  mov     [rbp+47h+hAlgorithm], 0
0x140207c98  mov     r15, rcx
0x140207c9b  lea     rdx, [rbp+47h+hAlgorithm]
0x140207c9f  lea     rcx, [rbp+47h+var_68]
0x140207ca3  mov     rsi, r9
0x140207ca6  mov     rdi, r8
0x140207ca9  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140207cae  xor     r9d, r9d; dwFlags
0x140207cb1  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140207cb8  lea     rdx, aEcdhP256; "ECDH_P256"
0x140207cbf  lea     rcx, [rax+8]; phAlgorithm
0x140207cc3  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140207cca  nop     dword ptr [rax+rax+00h]
0x140207ccf  lea     rcx, [rbp+47h+var_68]
0x140207cd3  mov     ebx, eax
0x140207cd5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140207cda  test    ebx, ebx
0x140207cdc  jns     short loc_140207D1D
0x140207cde  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207ce5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207cec  jz      loc_140208066
0x140207cf2  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207cf9  mov     [rsp+0D0h+dwFlags], ebx
0x140207cfd  mov     [rsp+0D0h+pbInput], rcx
0x140207d02  mov     r9d, 16h
0x140207d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140207d0f  mov     rcx, [rcx+40h]
0x140207d13  call    WPP_RECORDER_SF_sd
0x140207d18  jmp     loc_140208066
0x140207d1d  mov     edx, 68h ; 'h'
0x140207d22  mov     [rbp+47h+var_68], 0
0x140207d2a  mov     [rbp+47h+var_60], 0
0x140207d32  call    BthLELibAllocatePoolEx
0x140207d37  mov     rdx, rax; unsigned __int8 *
0x140207d3a  lea     rcx, [rbp+47h+var_68]; this
0x140207d3e  mov     r8d, 68h ; 'h'; unsigned __int64
0x140207d44  call    ?reset@unique_bthlelib_secure_pool@@QEAAXPEAE_K@Z; unique_bthlelib_secure_pool::reset(uchar *,unsigned __int64)
0x140207d49  mov     rbx, [rbp+47h+var_68]
0x140207d4d  test    rbx, rbx
0x140207d50  jnz     short loc_140207D9B
0x140207d52  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207d59  mov     ebx, 0C000009Ah
0x140207d5e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207d65  jz      short loc_140207D8D
0x140207d67  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207d6e  mov     [rsp+0D0h+dwFlags], ebx
0x140207d72  mov     [rsp+0D0h+pbInput], rcx
0x140207d77  mov     r9d, 17h
0x140207d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140207d84  mov     rcx, [rcx+40h]
0x140207d88  call    WPP_RECORDER_SF_sd
0x140207d8d  lea     rcx, [rbp+47h+var_68]; this
0x140207d91  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140207d96  jmp     loc_140208066
0x140207d9b  mov     dword ptr [rbx], 324B4345h
0x140207da1  lea     rdx, [rbp+47h+hPrivKey]
0x140207da5  mov     dword ptr [rbx+4], 20h ; ' '
0x140207dac  lea     rcx, [rbp+47h+var_50]
0x140207db0  movups  xmm0, xmmword ptr [r14]
0x140207db4  movups  xmmword ptr [rbx+8], xmm0
0x140207db8  movups  xmm1, xmmword ptr [r14+10h]
0x140207dbd  movups  xmmword ptr [rbx+18h], xmm1
0x140207dc1  movups  xmm0, xmmword ptr [rdi]
0x140207dc4  movups  xmmword ptr [rbx+28h], xmm0
0x140207dc8  movups  xmm1, xmmword ptr [rdi+10h]
0x140207dcc  movups  xmmword ptr [rbx+38h], xmm1
0x140207dd0  movups  xmm0, xmmword ptr [r15]
0x140207dd4  movups  xmmword ptr [rbx+48h], xmm0
0x140207dd8  movups  xmm1, xmmword ptr [r15+10h]
0x140207ddd  movups  xmmword ptr [rbx+58h], xmm1
0x140207de1  mov     [rbp+47h+hPrivKey], 0
0x140207de9  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140207dee  mov     rcx, [rbp+47h+hAlgorithm]; hAlgorithm
0x140207df2  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x140207df9  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x140207e01  xor     edx, edx; hImportKey
0x140207e03  mov     [rsp+0D0h+cbInput], 68h ; 'h'; cbInput
0x140207e0b  lea     r9, [rax+8]; phKey
0x140207e0f  mov     [rsp+0D0h+pbInput], rbx; pbInput
0x140207e14  call    cs:__imp_BCryptImportKeyPair
0x140207e1b  nop     dword ptr [rax+rax+00h]
0x140207e20  lea     rcx, [rbp+47h+var_50]
0x140207e24  mov     edi, eax
0x140207e26  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140207e2b  test    edi, edi
0x140207e2d  jns     short loc_140207E7E
0x140207e2f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207e36  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207e3d  jz      short loc_140207E65
0x140207e3f  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207e46  mov     [rsp+0D0h+dwFlags], edi
0x140207e4a  mov     [rsp+0D0h+pbInput], rcx
0x140207e4f  mov     r9d, 18h
0x140207e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140207e5c  mov     rcx, [rcx+40h]
0x140207e60  call    WPP_RECORDER_SF_sd
0x140207e65  lea     rcx, [rbp+47h+hPrivKey]
0x140207e69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207e6e  lea     rcx, [rbp+47h+var_68]; this
0x140207e72  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140207e77  mov     ebx, edi
0x140207e79  jmp     loc_140208066
0x140207e7e  mov     rax, [rbp+47h+arg_20]
0x140207e82  lea     rdx, [rbp+47h+hPubKey]
0x140207e86  mov     dword ptr [rbx], 314B4345h
0x140207e8c  lea     rcx, [rbp+47h+var_50]
0x140207e90  mov     edi, 20h ; ' '
0x140207e95  mov     [rbx+4], edi
0x140207e98  movups  xmm0, xmmword ptr [rsi]
0x140207e9b  movups  xmmword ptr [rbx+8], xmm0
0x140207e9f  movups  xmm1, xmmword ptr [rsi+10h]
0x140207ea3  movups  xmmword ptr [rbx+18h], xmm1
0x140207ea7  movups  xmm0, xmmword ptr [rax]
0x140207eaa  movups  xmmword ptr [rbx+28h], xmm0
0x140207eae  movups  xmm1, xmmword ptr [rax+10h]
0x140207eb2  movups  xmmword ptr [rbx+38h], xmm1
0x140207eb6  mov     [rbp+47h+hPubKey], 0
0x140207ebe  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140207ec3  mov     rcx, [rbp+47h+hAlgorithm]; hAlgorithm
0x140207ec7  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x140207ece  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x140207ed6  xor     edx, edx; hImportKey
0x140207ed8  mov     [rsp+0D0h+cbInput], 48h ; 'H'; cbInput
0x140207ee0  lea     r9, [rax+8]; phKey
0x140207ee4  mov     [rsp+0D0h+pbInput], rbx; pbInput
0x140207ee9  call    cs:__imp_BCryptImportKeyPair
0x140207ef0  nop     dword ptr [rax+rax+00h]
0x140207ef5  lea     rcx, [rbp+47h+var_50]
0x140207ef9  mov     ebx, eax
0x140207efb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140207f00  test    ebx, ebx
0x140207f02  jns     short loc_140207F4F
0x140207f04  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207f0b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207f12  jz      short loc_140207F38
0x140207f14  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207f1b  mov     [rsp+0D0h+dwFlags], ebx
0x140207f1f  mov     [rsp+0D0h+pbInput], rcx
0x140207f24  lea     r9d, [rdi-7]
0x140207f28  mov     rcx, cs:WPP_GLOBAL_Control
0x140207f2f  mov     rcx, [rcx+40h]
0x140207f33  call    WPP_RECORDER_SF_sd
0x140207f38  lea     rcx, [rbp+47h+hPubKey]
0x140207f3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207f41  lea     rcx, [rbp+47h+hPrivKey]
0x140207f45  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207f4a  jmp     loc_140207D8D
0x140207f4f  lea     rdx, [rbp+47h+hSharedSecret]
0x140207f53  mov     [rbp+47h+hSharedSecret], 0
0x140207f5b  lea     rcx, [rbp+47h+var_50]
0x140207f5f  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140207f64  mov     rdx, [rbp+47h+hPubKey]; hPubKey
0x140207f68  xor     r9d, r9d; dwFlags
0x140207f6b  mov     rcx, [rbp+47h+hPrivKey]; hPrivKey
0x140207f6f  lea     r8, [rax+8]; phAgreedSecret
0x140207f73  call    cs:__imp_BCryptSecretAgreement
0x140207f7a  nop     dword ptr [rax+rax+00h]
0x140207f7f  lea     rcx, [rbp+47h+var_50]
0x140207f83  mov     ebx, eax
0x140207f85  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroySecret@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140207f8a  test    ebx, ebx
0x140207f8c  jns     short loc_140207FD2
0x140207f8e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207f95  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207f9c  jz      short loc_140207FC4
0x140207f9e  mov     r9d, 1Ah
0x140207fa4  mov     [rsp+0D0h+dwFlags], ebx
0x140207fa8  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207faf  mov     [rsp+0D0h+pbInput], rcx
0x140207fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140207fbb  mov     rcx, [rcx+40h]
0x140207fbf  call    WPP_RECORDER_SF_sd
0x140207fc4  lea     rcx, [rbp+47h+hSharedSecret]
0x140207fc8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroySecret@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207fcd  jmp     loc_140207F38
0x140207fd2  mov     rcx, [rbp+47h+hSharedSecret]; hSharedSecret
0x140207fd6  lea     rax, [rbp+47h+pcbResult]
0x140207fda  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x140207fe2  lea     rdx, pwszKDF; "TRUNCATE"
0x140207fe9  mov     qword ptr [rsp+0D0h+cbInput], rax; pcbResult
0x140207fee  xor     r8d, r8d; pParameterList
0x140207ff1  mov     dword ptr [rsp+0D0h+pbInput], edi; cbDerivedKey
0x140207ff5  mov     rdi, [rbp+47h+pbDerivedKey]
0x140207ff9  mov     r9, rdi; pbDerivedKey
0x140207ffc  mov     [rbp+47h+pcbResult], 0
0x140208003  call    cs:__imp_BCryptDeriveKey
0x14020800a  nop     dword ptr [rax+rax+00h]
0x14020800f  mov     ebx, eax
0x140208011  test    eax, eax
0x140208013  jns     short loc_140208034
0x140208015  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020801c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140208023  jz      short loc_140207FC4
0x140208025  mov     r9d, 1Bh
0x14020802b  mov     [rsp+0D0h+dwFlags], eax
0x14020802f  jmp     loc_140207FA8
0x140208034  lea     rdx, [rdi+20h]
0x140208038  mov     rcx, rdi
0x14020803b  call    ??$reverse@PEAE@utl@@YAXPEAE0@Z; utl::reverse<uchar *>(uchar *,uchar *)
0x140208040  lea     rcx, [rbp+47h+hSharedSecret]
0x140208044  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroySecret@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140208049  lea     rcx, [rbp+47h+hPubKey]
0x14020804d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140208052  lea     rcx, [rbp+47h+hPrivKey]
0x140208056  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14020805b  lea     rcx, [rbp+47h+var_68]; this
0x14020805f  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x140208064  xor     ebx, ebx
0x140208066  lea     rcx, [rbp+47h+hAlgorithm]
0x14020806a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseBcryptAlgHandle@Details@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&Details::CloseBcryptAlgHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14020806f  mov     eax, ebx
0x140208071  add     rsp, 0A8h
0x140208078  pop     r15
0x14020807a  pop     r14
0x14020807c  pop     rdi
0x14020807d  pop     rsi
0x14020807e  pop     rbx
0x14020807f  pop     rbp
0x140208080  retn
```
