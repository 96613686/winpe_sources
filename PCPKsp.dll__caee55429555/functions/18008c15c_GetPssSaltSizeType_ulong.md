# GetPssSaltSizeType(ulong *)

- ea: `0x18008c15c`
- end: `0x18008c647`
- name: `?GetPssSaltSizeType@@YAJPEAK@Z`
- size: `1259`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006e5a0`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180025344`
- `0x180036ab4`
- `0x18005b2d4`
- `0x180061bac`
- `0x180063cb8`
- `0x1800764d0`
- `0x18007704c`
- `0x18007ee34`
- `0x180080668`
- `0x18008aff0`
- `0x18008c15c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c563`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c563`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008c590`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008c590`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c231`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c231`
- `ntdll!RtlGetPersistedStateLocation` at `0x18008c1ec`
- `ntdll!RtlGetPersistedStateLocation` at `0x18008c1ec`
- `bcrypt!BCryptGenerateKeyPair` at `0x18008c265`
- `bcrypt!BCryptGenerateKeyPair` at `0x18008c265`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18008c283`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18008c283`
- `bcrypt!BCryptExportKey` at `0x18008c2ee`
- `bcrypt!BCryptExportKey` at `0x18008c368`
- `bcrypt!BCryptExportKey` at `0x18008c2ee`
- `bcrypt!BCryptExportKey` at `0x18008c368`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008c393`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008c393`
- `ncrypt!NCryptImportKey` at `0x18008c40a`
- `ncrypt!NCryptImportKey` at `0x18008c40a`
- `ncrypt!NCryptSignHash` at `0x18008c4b6`
- `ncrypt!NCryptSignHash` at `0x18008c4b6`

## string_xrefs

- `0x18008c1dc`: `System\CurrentControlSet\Services\TPM\WMI`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetPssSaltSizeType(BYTE *lpData)
{
  int v2; // esi
  int PersistedStateLocation; // r15d
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  BYTE *v9; // r14
  SECURITY_STATUS v10; // eax
  SECURITY_STATUS v11; // edi
  SECURITY_STATUS v12; // eax
  __int64 v13; // rdx
  WCHAR *pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  _BYTE v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSignature; // [rsp+48h] [rbp-B8h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp-B0h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _BCRYPT_PSS_PADDING_INFO phkResult; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+78h] [rbp-88h]
  PUCHAR pbOutput[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  PBYTE pbSignature[3]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD pPaddingInfo[2]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE v31[24]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE pbHashValue[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v33; // [rsp+E8h] [rbp-18h]
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v2 = 1;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v31, L"GetPssSaltSizeType", 1);
  *(_DWORD *)lpData = 0;
  memset_0(SubKey, 0, 0x208u);
  v26 = 520;
  pdwType = SubKey;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmRegDriverPersistedData",
                             0,
                             L"System\\CurrentControlSet\\Services\\TPM\\WMI",
                             0);
  if ( PersistedStateLocation >= 0 )
  {
    cbSignature = 4;
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"RsaPssSaltLengthType", 0x10u, 0, lpData, &cbSignature) )
      *(_DWORD *)lpData = 0;
  }
  if ( !*(_DWORD *)lpData )
  {
    phKey = 0;
    v4 = BCryptGenerateKeyPair((BCRYPT_ALG_HANDLE)0xE1, &phKey, 0x400u, 0);
    if ( v4 < 0 )
    {
      v5 = 150;
LABEL_9:
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
             (const char *)(unsigned int)v4,
             (int)pdwType);
LABEL_37:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_35;
    }
    v4 = BCryptFinalizeKeyPair(phKey, 0);
    if ( v4 < 0 )
    {
      v5 = 151;
      goto LABEL_9;
    }
    *(_OWORD *)pbOutput = 0;
    v28 = 0;
    pcbResult = 0;
    v7 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", 0, 0, &pcbResult, 0);
    if ( v7 < 0 )
    {
      v8 = 162;
LABEL_12:
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v8,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
             (const char *)(unsigned int)v7,
             pdwTypea);
      std::vector<unsigned char>::_Tidy(pbOutput);
      goto LABEL_37;
    }
    v19[0] = 0;
    std::vector<unsigned char>::assign(pbOutput, pcbResult, v19);
    v9 = pbOutput[0];
    v7 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", pbOutput[0], pcbResult, &pcbResult, 0);
    if ( v7 < 0 )
    {
      v8 = 170;
      goto LABEL_12;
    }
    phProvider = 0;
    v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
        (const char *)(unsigned int)v10,
        pdwTypea);
LABEL_17:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(pbOutput);
      v6 = v11;
      goto LABEL_37;
    }
    hKey = 0;
    v12 = NCryptImportKey(phProvider, 0, L"RSAPRIVATEBLOB", 0, &hKey, v9, pcbResult, 0);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
        (const char *)(unsigned int)v12,
        pdwTypeb);
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
      goto LABEL_17;
    }
    cbSignature = 128;
    v19[0] = 0;
    std::vector<unsigned char>::vector<unsigned char>(pbSignature, 128, v19);
    pPaddingInfo[0] = L"SHA256";
    pPaddingInfo[1] = 32;
    *(_OWORD *)pbHashValue = 0;
    v33 = 0;
    v11 = NCryptSignHash(hKey, pPaddingInfo, pbHashValue, 0x20u, pbSignature[0], cbSignature, &cbSignature, 0x28u);
    if ( v11 < 0 )
    {
      v13 = 205;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
        (const char *)(unsigned int)v11,
        pdwTypec);
      std::vector<unsigned char>::_Tidy(pbSignature);
      goto LABEL_20;
    }
    phkResult.pszAlgId = L"SHA256";
    *(_QWORD *)&phkResult.cbSalt = 0;
    v11 = DetectPSSPaddingSalt(phKey, &phkResult, pbSignature[0], cbSignature);
    if ( v11 < 0 )
    {
      v13 = 212;
      goto LABEL_23;
    }
    if ( phkResult.cbSalt == 32 )
    {
      v2 = 2;
    }
    else if ( phkResult.cbSalt != 94 )
    {
      std::vector<unsigned char>::_Tidy(pbSignature);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(pbOutput);
      v6 = 1076429859;
      goto LABEL_37;
    }
    *(_DWORD *)lpData = v2;
    if ( PersistedStateLocation >= 0 )
    {
      phkResult.pszAlgId = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)&phkResult) )
        RegSetValueExW((HKEY)phkResult.pszAlgId, L"RsaPssSaltLengthType", 0, 4u, lpData, 4u);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    std::vector<unsigned char>::_Tidy(pbSignature);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    std::vector<unsigned char>::_Tidy(pbOutput);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
  }
  v6 = 0;
LABEL_35:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v31);
  return v6;
}

```

## disassembly

```asm
0x18008c15c  push    rbp
0x18008c15e  push    rbx
0x18008c15f  push    rsi
0x18008c160  push    rdi
0x18008c161  push    r12
0x18008c163  push    r13
0x18008c165  push    r14
0x18008c167  push    r15
0x18008c169  lea     rbp, [rsp-228h]
0x18008c171  sub     rsp, 328h
0x18008c178  mov     rax, cs:__security_cookie
0x18008c17f  xor     rax, rsp
0x18008c182  mov     [rbp+260h+var_50], rax
0x18008c189  mov     rbx, rcx
0x18008c18c  mov     esi, 1
0x18008c191  mov     r8b, sil; bool
0x18008c194  lea     rdx, aGetpsssaltsize; "GetPssSaltSizeType"
0x18008c19b  lea     rcx, [rbp+260h+var_2A0]; this
0x18008c19f  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18008c1a4  nop
0x18008c1a5  xor     r12d, r12d
0x18008c1a8  mov     [rbx], r12d
0x18008c1ab  mov     edi, 208h
0x18008c1b0  mov     r8d, edi; Size
0x18008c1b3  xor     edx, edx; Val
0x18008c1b5  lea     rcx, [rbp+260h+SubKey]; void *
0x18008c1b9  call    memset_0
0x18008c1be  mov     [rsp+360h+var_2E8], edi
0x18008c1c2  lea     rax, [rsp+360h+var_2E8]
0x18008c1c7  mov     [rsp+360h+pcbData], rax
0x18008c1cc  mov     dword ptr [rsp+360h+pvData], edi
0x18008c1d0  lea     rax, [rbp+260h+SubKey]
0x18008c1d4  mov     [rsp+360h+pdwType], rax
0x18008c1d9  xor     r9d, r9d
0x18008c1dc  lea     r8, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\TP"...
0x18008c1e3  xor     edx, edx
0x18008c1e5  lea     rcx, aTpmregdriverpe_1; "TpmRegDriverPersistedData"
0x18008c1ec  call    cs:__imp_RtlGetPersistedStateLocation
0x18008c1f3  nop     dword ptr [rax+rax+00h]
0x18008c1f8  mov     r15d, eax
0x18008c1fb  test    eax, eax
0x18008c1fd  js      short loc_18008C244
0x18008c1ff  mov     [rsp+360h+cbSignature], 4
0x18008c207  lea     rax, [rsp+360h+cbSignature]
0x18008c20c  mov     [rsp+360h+pcbData], rax; pcbData
0x18008c211  mov     [rsp+360h+pvData], rbx; pvData
0x18008c216  mov     [rsp+360h+pdwType], r12; int
0x18008c21b  lea     r9d, [rsi+0Fh]; dwFlags
0x18008c21f  lea     r8, aRsapsssaltleng; "RsaPssSaltLengthType"
0x18008c226  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x18008c22a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18008c231  call    cs:__imp_RegGetValueW
0x18008c238  nop     dword ptr [rax+rax+00h]
0x18008c23d  test    eax, eax
0x18008c23f  jz      short loc_18008C244
0x18008c241  mov     [rbx], r12d
0x18008c244  cmp     [rbx], r12d
0x18008c247  jnz     loc_18008C5DA
0x18008c24d  mov     [rsp+360h+phKey], r12
0x18008c252  xor     r9d, r9d; dwFlags
0x18008c255  mov     r8d, 400h; dwLength
0x18008c25b  lea     rdx, [rsp+360h+phKey]; phKey
0x18008c260  mov     ecx, 0E1h; hAlgorithm
0x18008c265  call    cs:__imp_BCryptGenerateKeyPair
0x18008c26c  nop     dword ptr [rax+rax+00h]
0x18008c271  test    eax, eax
0x18008c273  jns     short loc_18008C27C
0x18008c275  mov     edx, 96h
0x18008c27a  jmp     short loc_18008C298
0x18008c27c  xor     edx, edx; dwFlags
0x18008c27e  mov     rcx, [rsp+360h+phKey]; hKey
0x18008c283  call    cs:__imp_BCryptFinalizeKeyPair
0x18008c28a  nop     dword ptr [rax+rax+00h]
0x18008c28f  test    eax, eax
0x18008c291  jns     short loc_18008C2B5
0x18008c293  mov     edx, 97h; void *
0x18008c298  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008c29f  mov     r9d, eax; char *
0x18008c2a2  mov     rcx, [rbp+268h]; this
0x18008c2a9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008c2ae  mov     ebx, eax
0x18008c2b0  jmp     loc_18008C63A
0x18008c2b5  xorps   xmm0, xmm0
0x18008c2b8  movdqu  xmmword ptr [rbp+260h+pbOutput], xmm0
0x18008c2bd  mov     [rbp+260h+var_2D0], r12
0x18008c2c1  mov     [rsp+360h+pcbResult], r12d
0x18008c2c6  mov     dword ptr [rsp+360h+pcbData], r12d; dwFlags
0x18008c2cb  lea     rax, [rsp+360h+pcbResult]
0x18008c2d0  mov     [rsp+360h+pvData], rax; pcbResult
0x18008c2d5  mov     dword ptr [rsp+360h+pdwType], r12d; int
0x18008c2da  xor     r9d, r9d; pbOutput
0x18008c2dd  lea     r13, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18008c2e4  mov     r8, r13; pszBlobType
0x18008c2e7  xor     edx, edx; hExportKey
0x18008c2e9  mov     rcx, [rsp+360h+phKey]; hKey
0x18008c2ee  call    cs:__imp_BCryptExportKey
0x18008c2f5  nop     dword ptr [rax+rax+00h]
0x18008c2fa  test    eax, eax
0x18008c2fc  jns     short loc_18008C329
0x18008c2fe  mov     edx, 0A2h; void *
0x18008c303  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008c30a  mov     r9d, eax; char *
0x18008c30d  mov     rcx, [rbp+268h]; this
0x18008c314  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008c319  mov     ebx, eax
0x18008c31b  lea     rcx, [rbp+260h+pbOutput]
0x18008c31f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c324  jmp     loc_18008C63A
0x18008c329  mov     [rsp+360h+var_320], r12b
0x18008c32e  mov     edx, [rsp+360h+pcbResult]
0x18008c332  lea     r8, [rsp+360h+var_320]
0x18008c337  lea     rcx, [rbp+260h+pbOutput]
0x18008c33b  call    ?assign@?$vector@EV?$allocator@E@std@@@std@@QEAAX_KAEBE@Z; std::vector<uchar>::assign(unsigned __int64,uchar const &)
0x18008c340  mov     eax, [rsp+360h+pcbResult]
0x18008c344  mov     dword ptr [rsp+360h+pcbData], r12d; dwFlags
0x18008c349  lea     rcx, [rsp+360h+pcbResult]
0x18008c34e  mov     [rsp+360h+pvData], rcx; pcbResult
0x18008c353  mov     dword ptr [rsp+360h+pdwType], eax; int
0x18008c357  mov     r14, [rbp+260h+pbOutput]
0x18008c35b  mov     r9, r14; pbOutput
0x18008c35e  mov     r8, r13; pszBlobType
0x18008c361  xor     edx, edx; hExportKey
0x18008c363  mov     rcx, [rsp+360h+phKey]; hKey
0x18008c368  call    cs:__imp_BCryptExportKey
0x18008c36f  nop     dword ptr [rax+rax+00h]
0x18008c374  test    eax, eax
0x18008c376  jns     short loc_18008C37F
0x18008c378  mov     edx, 0AAh
0x18008c37d  jmp     short loc_18008C303
0x18008c37f  mov     [rsp+360h+phProvider], r12
0x18008c384  xor     r8d, r8d; dwFlags
0x18008c387  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18008c38e  lea     rcx, [rsp+360h+phProvider]; phProvider
0x18008c393  call    cs:__imp_NCryptOpenStorageProvider
0x18008c39a  nop     dword ptr [rax+rax+00h]
0x18008c39f  mov     edi, eax
0x18008c3a1  test    eax, eax
0x18008c3a3  jns     short loc_18008C3DC
0x18008c3a5  mov     rcx, [rbp+268h]; this
0x18008c3ac  mov     r9d, eax; char *
0x18008c3af  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008c3b6  mov     edx, 0AFh; void *
0x18008c3bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c3c0  nop
0x18008c3c1  lea     rcx, [rsp+360h+phProvider]
0x18008c3c6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008c3cb  nop
0x18008c3cc  lea     rcx, [rbp+260h+pbOutput]
0x18008c3d0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c3d5  mov     ebx, edi
0x18008c3d7  jmp     loc_18008C63A
0x18008c3dc  mov     eax, [rsp+360h+pcbResult]
0x18008c3e0  mov     [rsp+360h+hKey], r12
0x18008c3e5  mov     [rsp+360h+dwFlags], r12d; dwFlags
0x18008c3ea  mov     dword ptr [rsp+360h+pcbData], eax; cbData
0x18008c3ee  mov     [rsp+360h+pvData], r14; pbData
0x18008c3f3  lea     rax, [rsp+360h+hKey]
0x18008c3f8  mov     [rsp+360h+pdwType], rax; int
0x18008c3fd  xor     r9d, r9d; pParameterList
0x18008c400  mov     r8, r13; pszBlobType
0x18008c403  xor     edx, edx; hImportKey
0x18008c405  mov     rcx, [rsp+360h+phProvider]; hProvider
0x18008c40a  call    cs:__imp_NCryptImportKey
0x18008c411  nop     dword ptr [rax+rax+00h]
0x18008c416  mov     edi, eax
0x18008c418  test    eax, eax
0x18008c41a  jns     short loc_18008C447
0x18008c41c  mov     rcx, [rbp+268h]; this
0x18008c423  mov     r9d, eax; char *
0x18008c426  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008c42d  mov     edx, 0BAh; void *
0x18008c432  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c437  nop
0x18008c438  lea     rcx, [rsp+360h+hKey]
0x18008c43d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008c442  jmp     loc_18008C3C1
0x18008c447  mov     edx, 80h
0x18008c44c  mov     [rsp+360h+cbSignature], edx
0x18008c450  mov     [rsp+360h+var_320], r12b
0x18008c455  lea     r8, [rsp+360h+var_320]
0x18008c45a  lea     rcx, [rbp+260h+pbSignature]
0x18008c45e  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18008c463  lea     r13, aSha256_0; "SHA256"
0x18008c46a  mov     [rbp+260h+pPaddingInfo], r13
0x18008c46e  mov     r14d, 20h ; ' '
0x18008c474  mov     [rbp+260h+var_2A8], r14
0x18008c478  xorps   xmm0, xmm0
0x18008c47b  movups  xmmword ptr [rbp+260h+pbHashValue], xmm0
0x18008c47f  movups  [rbp+260h+var_278], xmm0
0x18008c483  mov     eax, [rsp+360h+cbSignature]
0x18008c487  mov     rdx, [rbp+260h+pbSignature]
0x18008c48b  mov     [rsp+360h+dwFlags], 28h ; '('; dwFlags
0x18008c493  lea     rcx, [rsp+360h+cbSignature]
0x18008c498  mov     [rsp+360h+pcbData], rcx; pcbResult
0x18008c49d  mov     dword ptr [rsp+360h+pvData], eax; cbSignature
0x18008c4a1  mov     [rsp+360h+pdwType], rdx; int
0x18008c4a6  mov     r9d, r14d; cbHashValue
0x18008c4a9  lea     r8, [rbp+260h+pbHashValue]; pbHashValue
0x18008c4ad  lea     rdx, [rbp+260h+pPaddingInfo]; pPaddingInfo
0x18008c4b1  mov     rcx, [rsp+360h+hKey]; hKey
0x18008c4b6  call    cs:__imp_NCryptSignHash
0x18008c4bd  nop     dword ptr [rax+rax+00h]
0x18008c4c2  mov     edi, eax
0x18008c4c4  test    eax, eax
0x18008c4c6  jns     short loc_18008C4F1
0x18008c4c8  mov     edx, 0CDh; void *
0x18008c4cd  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008c4d4  mov     r9d, edi; char *
0x18008c4d7  mov     rcx, [rbp+268h]; this
0x18008c4de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c4e3  lea     rcx, [rbp+260h+pbSignature]
0x18008c4e7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c4ec  jmp     loc_18008C438
0x18008c4f1  mov     [rsp+360h+phkResult], r13
0x18008c4f6  mov     [rsp+360h+var_2F0], r12
0x18008c4fb  mov     r9d, [rsp+360h+cbSignature]; unsigned int
0x18008c500  mov     r8, [rbp+260h+pbSignature]; unsigned __int8 *
0x18008c504  lea     rdx, [rsp+360h+phkResult]; struct _BCRYPT_PSS_PADDING_INFO *
0x18008c509  mov     rcx, [rsp+360h+phKey]; hKey
0x18008c50e  call    ?DetectPSSPaddingSalt@@YAJPEAXPEAU_BCRYPT_PSS_PADDING_INFO@@PEAEK@Z; DetectPSSPaddingSalt(void *,_BCRYPT_PSS_PADDING_INFO *,uchar *,ulong)
0x18008c513  mov     edi, eax
0x18008c515  test    eax, eax
0x18008c517  jns     short loc_18008C520
0x18008c519  mov     edx, 0D4h
0x18008c51e  jmp     short loc_18008C4CD
0x18008c520  cmp     dword ptr [rsp+360h+var_2F0], r14d
0x18008c525  jnz     short loc_18008C52E
0x18008c527  mov     esi, 2
0x18008c52c  jmp     short loc_18008C539
0x18008c52e  cmp     dword ptr [rsp+360h+var_2F0], 5Eh ; '^'
0x18008c533  jnz     loc_18008C60C
0x18008c539  mov     [rbx], esi
0x18008c53b  test    r15d, r15d
0x18008c53e  js      short loc_18008C5A6
0x18008c540  mov     [rsp+360h+phkResult], r12
0x18008c545  lea     rax, [rsp+360h+phkResult]
0x18008c54a  mov     [rsp+360h+pdwType], rax; phkResult
0x18008c54f  mov     r9d, 20019h; samDesired
0x18008c555  xor     r8d, r8d; ulOptions
0x18008c558  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x18008c55c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008c563  call    cs:__imp_RegOpenKeyExW
0x18008c56a  nop     dword ptr [rax+rax+00h]
0x18008c56f  test    eax, eax
0x18008c571  jnz     short loc_18008C59C
0x18008c573  lea     r9d, [rax+4]; dwType
0x18008c577  mov     dword ptr [rsp+360h+pvData], r9d; cbData
0x18008c57c  mov     [rsp+360h+pdwType], rbx; lpData
0x18008c581  xor     r8d, r8d; Reserved
0x18008c584  lea     rdx, aRsapsssaltleng; "RsaPssSaltLengthType"
0x18008c58b  mov     rcx, [rsp+360h+phkResult]; hKey
0x18008c590  call    cs:__imp_RegSetValueExW
0x18008c597  nop     dword ptr [rax+rax+00h]
0x18008c59c  lea     rcx, [rsp+360h+phkResult]
0x18008c5a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c5a6  lea     rcx, [rbp+260h+pbSignature]
0x18008c5aa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c5af  nop
0x18008c5b0  lea     rcx, [rsp+360h+hKey]
0x18008c5b5  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008c5ba  nop
0x18008c5bb  lea     rcx, [rsp+360h+phProvider]
0x18008c5c0  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008c5c5  nop
0x18008c5c6  lea     rcx, [rbp+260h+pbOutput]
0x18008c5ca  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c5cf  nop
0x18008c5d0  lea     rcx, [rsp+360h+phKey]
0x18008c5d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008c5da  mov     ebx, r12d
0x18008c5dd  lea     rcx, [rbp+260h+var_2A0]; this
0x18008c5e1  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18008c5e6  mov     eax, ebx
0x18008c5e8  mov     rcx, [rbp+260h+var_50]
0x18008c5ef  xor     rcx, rsp; StackCookie
0x18008c5f2  call    __security_check_cookie
0x18008c5f7  add     rsp, 328h
0x18008c5fe  pop     r15
0x18008c600  pop     r14
0x18008c602  pop     r13
0x18008c604  pop     r12
0x18008c606  pop     rdi
0x18008c607  pop     rsi
0x18008c608  pop     rbx
0x18008c609  pop     rbp
0x18008c60a  retn
0x18008c60c  lea     rcx, [rbp+260h+pbSignature]
0x18008c610  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c615  nop
0x18008c616  lea     rcx, [rsp+360h+hKey]
0x18008c61b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008c620  nop
0x18008c621  lea     rcx, [rsp+360h+phProvider]
0x18008c626  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008c62b  nop
0x18008c62c  lea     rcx, [rbp+260h+pbOutput]
0x18008c630  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008c635  mov     ebx, 40290423h
0x18008c63a  lea     rcx, [rsp+360h+phKey]
0x18008c63f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
  ... truncated ...
```
