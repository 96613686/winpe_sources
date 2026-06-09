# CheckSSLCertificateTrustImp(ulong,_CERT_CONTEXT const *,bool)

- ea: `0x14002cbd8`
- end: `0x14002cea1`
- name: `?CheckSSLCertificateTrustImp@@YAJKPEBU_CERT_CONTEXT@@_N@Z`
- size: `713`
- prototype: `__int64 __fastcall(char, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140031d1c`

## callees

- `0x140003de4`
- `0x1400154b4`
- `0x140017934`
- `0x14002ae70`
- `0x14002b0c8`
- `0x14002b118`
- `0x14002b38c`
- `0x14002cbd8`
- `0x14002d6f4`
- `0x14002d7f0`
- `0x14002e080`
- `0x140045dc0`

## import_xrefs

- `CRYPT32!CertFreeCertificateChain` at `0x14002cccf`
- `CRYPT32!CertFreeCertificateChain` at `0x14002ce74`
- `CRYPT32!CertFreeCertificateChain` at `0x14002cccf`
- `CRYPT32!CertFreeCertificateChain` at `0x14002ce74`

## string_xrefs

- `0x14002cc4a`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x14002ce09`: `WindowsServerUpdateServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CheckSSLCertificateTrustImp(char a1, const struct _CERT_CONTEXT *a2)
{
  unsigned int v3; // r14d
  __int64 v4; // r15
  char v5; // di
  char v6; // r12
  __int64 v7; // rcx
  int CertificateChainHelper; // ebx
  unsigned int v9; // ebx
  int v10; // eax
  struct _FILETIME *v12; // [rsp+20h] [rbp-50h]
  bool v13; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-2Ch] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-28h] BYREF
  const struct _CERT_CHAIN_CONTEXT *pChainContext_8; // [rsp+58h] [rbp-18h] BYREF

  v15[1] = 0;
  pChainContext_8 = 0;
  v3 = 0;
  v14 = 0;
  v4 = 0;
  v15[0] = 0;
  v5 = a1 & 1;
  v6 = (a1 & 2) != 0;
  if ( (unsigned int)AreTestKeysAllowed()
    && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                       v7,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                       L"AllowAnySSL",
                       0) == 1 )
  {
    CertificateChainHelper = 0;
    goto LABEL_20;
  }
  WUTrace(0, 0, 32, 5, 0, L"Validating SSL certificate for:%ws%ws");
  if ( !a2 )
    goto LABEL_5;
  CertificateChainHelper = CertGetCertificateChainHelper(a2, a2->hCertStore, v6, 1, 0, &pChainContext_8);
  if ( CertificateChainHelper >= 0 )
  {
    CertificateChainHelper = CertVerifyCertificateChainPolicyHelper((const char *)4, pChainContext_8, 0xF00u, 0);
    if ( CertificateChainHelper < 0 )
    {
      LODWORD(v12) = CertificateChainHelper;
      WUTrace(0, 0, 0x4000, 1, v12, L"Certificate used for SSL failed chain policy check");
      goto LABEL_20;
    }
    if ( v5 )
    {
      WUTrace(0, 0, 0x4000, 5, 0, L"Checking SSL intermediate CA ...");
      if ( (unsigned int)AreTestKeysAllowed() )
      {
        GetSubCAOverrides(&v14, v15);
        v3 = v14;
        v4 = v15[0];
      }
      v9 = DetermineSubCAIdentity(pChainContext_8, v3, v4);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
      {
        if ( v9 > 0x13 || (v10 = 788016, !_bittest(&v10, v9)) )
        {
LABEL_15:
          WUTrace(0, 0, 0x4000, 1, 0, L"Certificate failed SSL intermediate CA check.");
LABEL_5:
          CertificateChainHelper = -2143485942;
          goto LABEL_20;
        }
      }
      else if ( v9 - 4 > 1 && v9 - 9 > 1 )
      {
        goto LABEL_15;
      }
    }
    v13 = 0;
    CertificateChainHelper = IsCertInStore(a2, aWindowsserveru, &v13);
    if ( CertificateChainHelper >= 0 )
      WUTrace(0, 0, 32, 5, 0, L"Cert in WSUS store: %ws");
  }
LABEL_20:
  FreeSubCAOverrides(v3, v4);
  if ( pChainContext_8 )
    CertFreeCertificateChain(pChainContext_8);
  return (unsigned int)CertificateChainHelper;
}

```

## disassembly

```asm
0x14002cbd8  mov     [rsp-28h+arg_10], rbx
0x14002cbdd  mov     [rsp-28h+arg_18], rsi
0x14002cbe2  push    rbp
0x14002cbe3  push    rdi
0x14002cbe4  push    r12
0x14002cbe6  push    r14
0x14002cbe8  push    r15
0x14002cbea  mov     rbp, rsp
0x14002cbed  sub     rsp, 70h
0x14002cbf1  mov     rax, cs:__security_cookie
0x14002cbf8  xor     rax, rsp
0x14002cbfb  mov     [rbp+var_10], rax
0x14002cbff  mov     rsi, rdx
0x14002cc02  mov     ebx, ecx
0x14002cc04  xorps   xmm0, xmm0
0x14002cc07  movups  xmmword ptr [rbp+pChainContext], xmm0
0x14002cc0b  mov     [rbp+pChainContext+8], 0
0x14002cc13  xor     r14d, r14d
0x14002cc16  mov     [rbp+var_2C], r14d
0x14002cc1a  xor     r15d, r15d
0x14002cc1d  mov     [rbp+var_28], r15
0x14002cc21  mov     dil, cl
0x14002cc24  and     dil, 1
0x14002cc28  and     ebx, 2
0x14002cc2b  setnz   r12b
0x14002cc2f  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14002cc34  test    eax, eax
0x14002cc36  jz      short loc_14002CC62
0x14002cc38  mov     dword ptr [rsp+70h+var_48], 0FFFFFFFFh
0x14002cc40  xor     r9d, r9d
0x14002cc43  lea     r8, aAllowanyssl; "AllowAnySSL"
0x14002cc4a  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002cc51  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x14002cc56  cmp     eax, 1
0x14002cc59  jnz     short loc_14002CC62
0x14002cc5b  xor     ebx, ebx
0x14002cc5d  jmp     loc_14002CE5F
0x14002cc62  lea     rdx, aStrength; " strength"
0x14002cc69  lea     rcx, OutputString
0x14002cc70  mov     rax, rcx
0x14002cc73  test    ebx, ebx
0x14002cc75  cmovnz  rax, rdx
0x14002cc79  lea     rdx, aRoot; " root"
0x14002cc80  test    dil, dil
0x14002cc83  cmovnz  rcx, rdx
0x14002cc87  mov     [rsp+70h+var_38], rax
0x14002cc8c  mov     [rsp+70h+var_40], rcx
0x14002cc91  lea     rax, aValidatingSslC; "Validating SSL certificate for:%ws%ws"
0x14002cc98  mov     [rsp+70h+var_48], rax
0x14002cc9d  mov     [rsp+70h+var_50], r14
0x14002cca2  xor     edx, edx
0x14002cca4  xor     ecx, ecx
0x14002cca6  lea     r9d, [rdx+5]
0x14002ccaa  lea     r8d, [rdx+20h]
0x14002ccae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002ccb3  test    rsi, rsi
0x14002ccb6  jnz     short loc_14002CCC2
0x14002ccb8  mov     ebx, 803D000Ah
0x14002ccbd  jmp     loc_14002CE5F
0x14002ccc2  mov     rbx, [rsi+20h]
0x14002ccc6  mov     rcx, [rbp+pChainContext+8]; pChainContext
0x14002ccca  test    rcx, rcx
0x14002cccd  jz      short loc_14002CCD9
0x14002cccf  call    cs:__imp_CertFreeCertificateChain
0x14002ccd5  mov     [rbp+pChainContext+8], r14
0x14002ccd9  lea     rax, [rbp+pChainContext+8]
0x14002ccdd  mov     [rsp+70h+var_48], rax; struct _CERT_CHAIN_CONTEXT **
0x14002cce2  mov     [rsp+70h+var_50], r14; struct _FILETIME *
0x14002cce7  mov     r9b, 1; bool
0x14002ccea  mov     r8b, r12b; bool
0x14002cced  mov     rdx, rbx; hAdditionalStore
0x14002ccf0  mov     rcx, rsi; pCertContext
0x14002ccf3  call    ?CertGetCertificateChainHelper@@YAJPEBU_CERT_CONTEXT@@PEAX_N2PEAU_FILETIME@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z; CertGetCertificateChainHelper(_CERT_CONTEXT const *,void *,bool,bool,_FILETIME *,_CERT_CHAIN_CONTEXT const * *)
0x14002ccf8  mov     ebx, eax
0x14002ccfa  test    eax, eax
0x14002ccfc  js      loc_14002CE5F
0x14002cd02  xor     r9d, r9d; bool
0x14002cd05  mov     r8d, 0F00h; unsigned int
0x14002cd0b  mov     rdx, [rbp+pChainContext+8]; struct _CERT_CHAIN_CONTEXT *
0x14002cd0f  lea     ecx, [r9+4]; char *
0x14002cd13  call    ?CertVerifyCertificateChainPolicyHelper@@YAJPEBDPEBU_CERT_CHAIN_CONTEXT@@K_N@Z; CertVerifyCertificateChainPolicyHelper(char const *,_CERT_CHAIN_CONTEXT const *,ulong,bool)
0x14002cd18  mov     ebx, eax
0x14002cd1a  test    eax, eax
0x14002cd1c  jns     short loc_14002CD46
0x14002cd1e  lea     rax, aCertificateUse; "Certificate used for SSL failed chain p"...
0x14002cd25  mov     [rsp+70h+var_48], rax
0x14002cd2a  mov     dword ptr [rsp+70h+var_50], ebx
0x14002cd2e  xor     edx, edx
0x14002cd30  xor     ecx, ecx
0x14002cd32  lea     r9d, [rdx+1]
0x14002cd36  mov     r8d, 4000h
0x14002cd3c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002cd41  jmp     loc_14002CE5F
0x14002cd46  test    dil, dil
0x14002cd49  jz      loc_14002CE01
0x14002cd4f  lea     rax, aCheckingSslInt; "Checking SSL intermediate CA ..."
0x14002cd56  mov     [rsp+70h+var_48], rax
0x14002cd5b  mov     [rsp+70h+var_50], r14
0x14002cd60  mov     edi, 4000h
0x14002cd65  mov     r9d, 5
0x14002cd6b  mov     r8d, edi
0x14002cd6e  xor     edx, edx
0x14002cd70  xor     ecx, ecx
0x14002cd72  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002cd77  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14002cd7c  test    eax, eax
0x14002cd7e  jz      short loc_14002CD95
0x14002cd80  lea     rdx, [rbp+var_28]
0x14002cd84  lea     rcx, [rbp+var_2C]
0x14002cd88  call    GetSubCAOverrides
0x14002cd8d  mov     r14d, [rbp+var_2C]
0x14002cd91  mov     r15, [rbp+var_28]
0x14002cd95  mov     r8, r15
0x14002cd98  mov     edx, r14d
0x14002cd9b  mov     rcx, [rbp+pChainContext+8]
0x14002cd9f  call    DetermineSubCAIdentity
0x14002cda4  mov     ebx, eax
0x14002cda6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x14002cdad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x14002cdb2  test    al, al
0x14002cdb4  jz      short loc_14002CDF1
0x14002cdb6  cmp     ebx, 13h
0x14002cdb9  ja      short loc_14002CDC5
0x14002cdbb  mov     eax, 0C0630h
0x14002cdc0  bt      eax, ebx
0x14002cdc3  jb      short loc_14002CE01
0x14002cdc5  lea     rax, aCertificateFai; "Certificate failed SSL intermediate CA "...
0x14002cdcc  mov     [rsp+70h+var_48], rax
0x14002cdd1  mov     [rsp+70h+var_50], 0
0x14002cdda  mov     r9d, 1
0x14002cde0  mov     r8d, edi
0x14002cde3  xor     edx, edx
0x14002cde5  xor     ecx, ecx
0x14002cde7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002cdec  jmp     loc_14002CCB8
0x14002cdf1  lea     eax, [rbx-4]
0x14002cdf4  cmp     eax, 1
0x14002cdf7  jbe     short loc_14002CE01
0x14002cdf9  lea     eax, [rbx-9]
0x14002cdfc  cmp     eax, 1
0x14002cdff  ja      short loc_14002CDC5
0x14002ce01  mov     [rbp+var_30], 0
0x14002ce05  lea     r8, [rbp+var_30]; bool *
0x14002ce09  lea     rdx, aWindowsserveru; "WindowsServerUpdateServices"
0x14002ce10  mov     rcx, rsi; struct _CERT_CONTEXT *
0x14002ce13  call    ?IsCertInStore@@YAJQEBU_CERT_CONTEXT@@PEA_WPEA_N@Z; IsCertInStore(_CERT_CONTEXT const * const,wchar_t *,bool *)
0x14002ce18  mov     ebx, eax
0x14002ce1a  test    eax, eax
0x14002ce1c  js      short loc_14002CE5F
0x14002ce1e  lea     rcx, aYes_1; "Yes"
0x14002ce25  lea     rax, aNo_1; "No"
0x14002ce2c  cmp     [rbp+var_30], 0
0x14002ce30  cmovnz  rax, rcx
0x14002ce34  mov     [rsp+70h+var_40], rax
0x14002ce39  lea     rax, aCertInWsusStor; "Cert in WSUS store: %ws"
0x14002ce40  mov     [rsp+70h+var_48], rax
0x14002ce45  mov     [rsp+70h+var_50], 0
0x14002ce4e  xor     edx, edx
0x14002ce50  xor     ecx, ecx
0x14002ce52  lea     r9d, [rdx+5]
0x14002ce56  lea     r8d, [rdx+20h]
0x14002ce5a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002ce5f  mov     rdx, r15
0x14002ce62  mov     ecx, r14d
0x14002ce65  call    FreeSubCAOverrides
0x14002ce6a  nop
0x14002ce6b  mov     rcx, [rbp+pChainContext+8]; pChainContext
0x14002ce6f  test    rcx, rcx
0x14002ce72  jz      short loc_14002CE7A
0x14002ce74  call    cs:__imp_CertFreeCertificateChain
0x14002ce7a  mov     eax, ebx
0x14002ce7c  mov     rcx, [rbp+var_10]
0x14002ce80  xor     rcx, rsp; StackCookie
0x14002ce83  call    __security_check_cookie
0x14002ce88  lea     r11, [rsp+70h+var_s0]
0x14002ce8d  mov     rbx, [r11+40h]
0x14002ce91  mov     rsi, [r11+48h]
0x14002ce95  mov     rsp, r11
0x14002ce98  pop     r15
0x14002ce9a  pop     r14
0x14002ce9c  pop     r12
0x14002ce9e  pop     rdi
0x14002ce9f  pop     rbp
0x14002cea0  retn
```
