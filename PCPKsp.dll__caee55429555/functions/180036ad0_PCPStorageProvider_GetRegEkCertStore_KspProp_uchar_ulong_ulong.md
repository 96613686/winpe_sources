# PCPStorageProvider::GetRegEkCertStore(KspProp,uchar *,ulong,ulong *)

- ea: `0x180036ad0`
- end: `0x180036e9d`
- name: `?GetRegEkCertStore@PCPStorageProvider@@AEAAJW4KspProp@@PEAEKPEAK@Z`
- size: `973`
- prototype: `int __high(enum KspProp, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001bb00`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800341ec`
- `0x180036a58`
- `0x180036ab4`
- `0x180036ad0`
- `0x1800389c0`
- `0x18005305c`
- `0x18005437c`
- `0x18005b6fc`
- `0x180061bac`
- `0x18006d388`
- `0x1800764d0`
- `0x18007704c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036bd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036cb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036bd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036cb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036c38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036d08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036c38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036d08`
- `ntdll!RtlGetPersistedStateLocation` at `0x180036b92`
- `ntdll!RtlGetPersistedStateLocation` at `0x180036b92`
- `CRYPT32!CertOpenStore` at `0x180036c5d`
- `CRYPT32!CertOpenStore` at `0x180036d43`
- `CRYPT32!CertOpenStore` at `0x180036c5d`
- `CRYPT32!CertOpenStore` at `0x180036d43`
- `CRYPT32!CertFreeCertificateContext` at `0x180036dfd`
- `CRYPT32!CertFreeCertificateContext` at `0x180036dfd`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180036d75`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180036d75`

## string_xrefs

- `0x180036b49`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStoreECC`
- `0x180036b39`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

## pseudocode

```c
__int64 __fastcall PCPStorageProvider::GetRegEkCertStore(__int64 a1, int a2, void *a3, unsigned int a4, _DWORD *a5)
{
  rsize_t v6; // rsi
  const wchar_t *v8; // r8
  const wchar_t *v9; // rcx
  int PersistedStateLocation; // eax
  int LastError; // eax
  const char *v12; // r9
  void *v13; // rbx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  HKEY v16; // rbx
  LSTATUS v17; // eax
  HCERTSTORE v18; // rax
  const CERT_CONTEXT *v19; // rdi
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT v24; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+68h] [rbp-98h]
  void *Source; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[24]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v6 = a4;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v28, L"PCPStorageProvider::GetRegEkCertStore", 1);
  memset_0(SubKey, 0, 0x208u);
  v26 = 520;
  v25 = 0;
  v8 = L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStoreECC";
  hKey = 0;
  if ( a2 != 38 )
    v8 = L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStore";
  *a5 = 0;
  v9 = L"TPMCoreProvisioningEKCertificatesECC";
  if ( a2 != 38 )
    v9 = L"TPMCoreProvisioningEKCertificates";
  PersistedStateLocation = RtlGetPersistedStateLocation(v9, 0, v8, 0);
  if ( PersistedStateLocation < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x389,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)(unsigned int)PersistedStateLocation,
                  (int)SubKey);
LABEL_13:
    v15 = LastError;
LABEL_32:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v28);
    return v15;
  }
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v24);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v24);
  }
  hKey = 0;
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    v16 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v24);
      RegCloseKey(v16);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v24);
    }
    hKey = 0;
    v17 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &hKey, 0);
    v15 = v17;
    if ( v17 > 0 )
      v15 = (unsigned __int16)v17 | 0x80070000;
    if ( (v15 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B2,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)v15,
        dwOptionsa);
      goto LABEL_32;
    }
    v18 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, hKey);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v25,
      v18);
    v13 = v25;
    if ( !v25 )
    {
      v14 = 941;
      goto LABEL_12;
    }
  }
  else
  {
    v25 = CertOpenStore((LPCSTR)4, 0, 0, 0, hKey);
    v13 = v25;
    if ( !v25 )
    {
      v14 = 923;
LABEL_12:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v14,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                    v12);
      goto LABEL_13;
    }
  }
  v24 = CertEnumCertificatesInStore(v13, 0);
  v19 = v24;
  TraceTpmInformation(v24 != 0, L"EKCertExists");
  Source = v13;
  *a5 = 8;
  if ( !(_DWORD)v6 || !a3 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v24);
    v15 = 0;
    goto LABEL_32;
  }
  if ( (unsigned int)v6 < 8 )
  {
    v15 = -2146893784;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)0x80090028LL,
      dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v24);
    goto LABEL_32;
  }
  memcpy_s_1(a3, v6, &Source, 8u);
  if ( v19 )
    CertFreeCertificateContext(v19);
  if ( hKey )
    RegCloseKey(hKey);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v28);
  return 0;
}

```

## disassembly

```asm
0x180036ad0  mov     [rsp-8+arg_0], rbx
0x180036ad5  push    rbp
0x180036ad6  push    rsi
0x180036ad7  push    rdi
0x180036ad8  push    r14
0x180036ada  push    r15
0x180036adc  lea     rbp, [rsp-1B0h]
0x180036ae4  sub     rsp, 2B0h
0x180036aeb  mov     rax, cs:__security_cookie
0x180036af2  xor     rax, rsp
0x180036af5  mov     [rbp+1D0h+var_30], rax
0x180036afc  mov     r15, [rbp+1D0h+arg_20]
0x180036b03  lea     rcx, [rsp+2D0h+var_258]; this
0x180036b08  mov     r14, r8
0x180036b0b  mov     esi, r9d
0x180036b0e  mov     ebx, edx
0x180036b10  mov     r8b, 1; bool
0x180036b13  lea     rdx, aPcpstorageprov_7; "PCPStorageProvider::GetRegEkCertStore"
0x180036b1a  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180036b1f  mov     edi, 208h
0x180036b24  lea     rcx, [rbp+1D0h+SubKey]; void *
0x180036b28  mov     r8d, edi; Size
0x180036b2b  xor     edx, edx; Val
0x180036b2d  call    memset_0
0x180036b32  cmp     ebx, 26h ; '&'
0x180036b35  mov     [rsp+2D0h+var_268], edi
0x180036b39  lea     rax, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\TP"...
0x180036b40  mov     [rsp+2D0h+var_270], 0
0x180036b49  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\TP"...
0x180036b50  mov     [rsp+2D0h+hKey], 0
0x180036b59  cmovnz  r8, rax
0x180036b5d  mov     dword ptr [r15], 0
0x180036b64  lea     rax, aTpmcoreprovisi_2; "TPMCoreProvisioningEKCertificates"
0x180036b6b  lea     rcx, aTpmcoreprovisi_1; "TPMCoreProvisioningEKCertificatesECC"
0x180036b72  cmovnz  rcx, rax
0x180036b76  lea     rax, [rsp+2D0h+var_268]
0x180036b7b  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x180036b80  xor     r9d, r9d
0x180036b83  lea     rax, [rbp+1D0h+SubKey]
0x180036b87  mov     [rsp+2D0h+samDesired], edi
0x180036b8b  xor     edx, edx
0x180036b8d  mov     qword ptr [rsp+2D0h+dwOptions], rax; int
0x180036b92  call    cs:__imp_RtlGetPersistedStateLocation
0x180036b99  nop     dword ptr [rax+rax+00h]
0x180036b9e  test    eax, eax
0x180036ba0  jns     short loc_180036BC2
0x180036ba2  mov     rcx, [rbp+1D8h]; this
0x180036ba9  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036bb0  mov     r9d, eax; char *
0x180036bb3  mov     edx, 389h; void *
0x180036bb8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036bbd  jmp     loc_180036C92
0x180036bc2  mov     rbx, [rsp+2D0h+hKey]
0x180036bc7  test    rbx, rbx
0x180036bca  jz      short loc_180036BEF
0x180036bcc  lea     rcx, [rsp+2D0h+var_278]; this
0x180036bd1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036bd6  mov     rcx, rbx; hKey
0x180036bd9  call    cs:__imp_RegCloseKey
0x180036be0  nop     dword ptr [rax+rax+00h]
0x180036be5  lea     rcx, [rsp+2D0h+var_278]; this
0x180036bea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036bef  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x180036bf8  lea     rax, [rsp+2D0h+hKey]
0x180036bfd  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180036c02  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180036c06  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036c0f  mov     rdi, 0FFFFFFFF80000002h
0x180036c16  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180036c1e  xor     r9d, r9d; lpClass
0x180036c21  xor     r8d, r8d; Reserved
0x180036c24  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x180036c2c  mov     rcx, rdi; hKey
0x180036c2f  mov     [rsp+2D0h+hKey], 0
0x180036c38  call    cs:__imp_RegCreateKeyExW
0x180036c3f  nop     dword ptr [rax+rax+00h]
0x180036c44  test    eax, eax
0x180036c46  jnz     short loc_180036C99
0x180036c48  mov     rax, [rsp+2D0h+hKey]
0x180036c4d  xor     edx, edx; dwEncodingType
0x180036c4f  xor     r9d, r9d; dwFlags
0x180036c52  mov     qword ptr [rsp+2D0h+dwOptions], rax; int
0x180036c57  xor     r8d, r8d; hCryptProv
0x180036c5a  lea     ecx, [rdx+4]; lpszStoreProvider
0x180036c5d  call    cs:__imp_CertOpenStore
0x180036c64  nop     dword ptr [rax+rax+00h]
0x180036c69  mov     [rsp+2D0h+var_270], rax
0x180036c6e  mov     rbx, rax
0x180036c71  test    rax, rax
0x180036c74  jnz     loc_180036D70
0x180036c7a  mov     edx, 39Bh; void *
0x180036c7f  mov     rcx, [rbp+1D8h]; this
0x180036c86  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036c8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036c92  mov     ebx, eax
0x180036c94  jmp     loc_180036E56
0x180036c99  mov     rbx, [rsp+2D0h+hKey]
0x180036c9e  test    rbx, rbx
0x180036ca1  jz      short loc_180036CC6
0x180036ca3  lea     rcx, [rsp+2D0h+var_278]; this
0x180036ca8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036cad  mov     rcx, rbx; hKey
0x180036cb0  call    cs:__imp_RegCloseKey
0x180036cb7  nop     dword ptr [rax+rax+00h]
0x180036cbc  lea     rcx, [rsp+2D0h+var_278]; this
0x180036cc1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036cc6  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x180036ccf  lea     rax, [rsp+2D0h+hKey]
0x180036cd4  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180036cd9  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180036cdd  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036ce6  xor     r9d, r9d; lpClass
0x180036ce9  mov     [rsp+2D0h+samDesired], 20019h; samDesired
0x180036cf1  xor     r8d, r8d; Reserved
0x180036cf4  mov     rcx, rdi; hKey
0x180036cf7  mov     [rsp+2D0h+dwOptions], 0; int
0x180036cff  mov     [rsp+2D0h+hKey], 0
0x180036d08  call    cs:__imp_RegCreateKeyExW
0x180036d0f  nop     dword ptr [rax+rax+00h]
0x180036d14  mov     ebx, eax
0x180036d16  test    eax, eax
0x180036d18  jle     short loc_180036D23
0x180036d1a  movzx   ebx, ax
0x180036d1d  or      ebx, 80070000h
0x180036d23  test    ebx, ebx
0x180036d25  js      loc_180036E3B
0x180036d2b  mov     rax, [rsp+2D0h+hKey]
0x180036d30  xor     edx, edx; dwEncodingType
0x180036d32  mov     r9d, 8000h; dwFlags
0x180036d38  mov     qword ptr [rsp+2D0h+dwOptions], rax; pvPara
0x180036d3d  xor     r8d, r8d; hCryptProv
0x180036d40  lea     ecx, [rdx+4]; lpszStoreProvider
0x180036d43  call    cs:__imp_CertOpenStore
0x180036d4a  nop     dword ptr [rax+rax+00h]
0x180036d4f  mov     rdx, rax
0x180036d52  lea     rcx, [rsp+2D0h+var_270]
0x180036d57  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180036d5c  mov     rbx, [rsp+2D0h+var_270]
0x180036d61  test    rbx, rbx
0x180036d64  jnz     short loc_180036D70
0x180036d66  mov     edx, 3ADh
0x180036d6b  jmp     loc_180036C7F
0x180036d70  xor     edx, edx; pPrevCertContext
0x180036d72  mov     rcx, rbx; hCertStore
0x180036d75  call    cs:__imp_CertEnumCertificatesInStore
0x180036d7c  nop     dword ptr [rax+rax+00h]
0x180036d81  xor     ecx, ecx
0x180036d83  lea     rdx, aEkcertexists; "EKCertExists"
0x180036d8a  test    rax, rax
0x180036d8d  mov     [rsp+2D0h+var_278], rax
0x180036d92  mov     rdi, rax
0x180036d95  setnz   cl; unsigned int
0x180036d98  call    ?TraceTpmInformation@@YAXKPEAG@Z; TraceTpmInformation(ulong,ushort *)
0x180036d9d  mov     [rsp+2D0h+Source], rbx
0x180036da2  mov     r9d, 8; SourceSize
0x180036da8  mov     [r15], r9d
0x180036dab  test    esi, esi
0x180036dad  jz      short loc_180036E2D
0x180036daf  test    r14, r14
0x180036db2  jz      short loc_180036E2D
0x180036db4  cmp     esi, r9d
0x180036db7  jnb     short loc_180036DE5
0x180036db9  mov     rcx, [rbp+1D8h]; this
0x180036dc0  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036dc7  mov     ebx, 80090028h
0x180036dcc  mov     edx, 3CEh; void *
0x180036dd1  mov     r9d, ebx; char *
0x180036dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036dd9  lea     rcx, [rsp+2D0h+var_278]
0x180036dde  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180036de3  jmp     short loc_180036E56
0x180036de5  mov     rdx, rsi; DestinationSize
0x180036de8  lea     r8, [rsp+2D0h+Source]; Source
0x180036ded  mov     rcx, r14; Destination
0x180036df0  call    memcpy_s_1
0x180036df5  test    rdi, rdi
0x180036df8  jz      short loc_180036E09
0x180036dfa  mov     rcx, rdi; pCertContext
0x180036dfd  call    cs:__imp_CertFreeCertificateContext
0x180036e04  nop     dword ptr [rax+rax+00h]
0x180036e09  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180036e0e  test    rcx, rcx
0x180036e11  jz      short loc_180036E1F
0x180036e13  call    cs:__imp_RegCloseKey
0x180036e1a  nop     dword ptr [rax+rax+00h]
0x180036e1f  lea     rcx, [rsp+2D0h+var_258]; this
0x180036e24  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180036e29  xor     eax, eax
0x180036e2b  jmp     short loc_180036E76
0x180036e2d  lea     rcx, [rsp+2D0h+var_278]
0x180036e32  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180036e37  xor     ebx, ebx
0x180036e39  jmp     short loc_180036E56
0x180036e3b  mov     rcx, [rbp+1D8h]; this
0x180036e42  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036e49  mov     r9d, ebx; char *
0x180036e4c  mov     edx, 3B2h; void *
0x180036e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e56  lea     rcx, [rsp+2D0h+hKey]
0x180036e5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036e60  lea     rcx, [rsp+2D0h+var_270]
0x180036e65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036e6a  lea     rcx, [rsp+2D0h+var_258]; this
0x180036e6f  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180036e74  mov     eax, ebx
0x180036e76  mov     rcx, [rbp+1D0h+var_30]
0x180036e7d  xor     rcx, rsp; StackCookie
0x180036e80  call    __security_check_cookie
0x180036e85  mov     rbx, [rsp+2D0h+arg_0]
0x180036e8d  add     rsp, 2B0h
0x180036e94  pop     r15
0x180036e96  pop     r14
0x180036e98  pop     rdi
0x180036e99  pop     rsi
0x180036e9a  pop     rbp
0x180036e9b  retn
```
