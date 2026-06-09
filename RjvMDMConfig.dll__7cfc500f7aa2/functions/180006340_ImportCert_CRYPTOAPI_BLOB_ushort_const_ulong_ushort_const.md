# ImportCert(_CRYPTOAPI_BLOB *,ushort const *,ulong,ushort const *)

- ea: `0x180006340`
- end: `0x180006493`
- name: `?ImportCert@@YAJPEAU_CRYPTOAPI_BLOB@@PEBGK1@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004168`

## callees

- `0x180003910`
- `0x180003938`
- `0x180005688`
- `0x180006340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000645b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000645b`
- `CRYPT32!CertOpenStore` at `0x18000639c`
- `CRYPT32!CertOpenStore` at `0x18000639c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800063ba`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800063f2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800063ba`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800063f2`
- `CRYPT32!PFXImportCertStore` at `0x180006365`
- `CRYPT32!PFXImportCertStore` at `0x180006365`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800063e0`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800063e0`

## pseudocode

```c
__int64 __fastcall ImportCert(
        struct _CRYPTOAPI_BLOB *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rdi
  const CERT_CONTEXT *v5; // rbx
  PCCERT_CONTEXT v6; // rax
  signed int v8; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  HCERTSTORE v11[3]; // [rsp+30h] [rbp-18h] BYREF
  const unsigned __int16 *v12; // [rsp+58h] [rbp+10h] BYREF
  const unsigned __int16 *v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a2;
  v12 = (const unsigned __int16 *)PFXImportCertStore(a1, szPassword, 0x1010u);
  v4 = (unsigned __int16 *)v12;
  if ( !v12 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  v11[0] = CertOpenStore((LPCSTR)0xD, 0, 0, 0x10000u, L"My");
  if ( !v11[0] )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v11);
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    return v9;
  }
  v5 = CertEnumCertificatesInStore(v4, 0);
  v13 = (const unsigned __int16 *)v5;
  while ( v5 )
  {
    CertAddCertificateContextToStore(v11[0], v5, 3u, 0);
    v6 = CertEnumCertificatesInStore(v4, v5);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
      &v13,
      v6);
    v5 = (const CERT_CONTEXT *)v13;
  }
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v11);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return 0;
}

```

## disassembly

```asm
0x180006340  mov     rax, rsp
0x180006343  mov     [rax+8], rbx
0x180006347  mov     [rax+18h], rsi
0x18000634b  mov     [rax+20h], r9
0x18000634f  mov     [rax+10h], rdx
0x180006353  push    rdi
0x180006354  sub     rsp, 40h
0x180006358  mov     r8d, 1010h; dwFlags
0x18000635e  lea     rdx, szPassword; "{EE9AA8E2-B182-4063-B3CC-F0B6C5DE6489}"
0x180006365  call    cs:__imp_PFXImportCertStore
0x18000636c  nop     dword ptr [rax+rax+00h]
0x180006371  mov     [rsp+48h+arg_8], rax
0x180006376  mov     rdi, rax
0x180006379  test    rax, rax
0x18000637c  jz      loc_18000645B
0x180006382  xor     edx, edx; dwEncodingType
0x180006384  lea     rax, aMy; "My"
0x18000638b  mov     r9d, 10000h; dwFlags
0x180006391  mov     [rsp+48h+pvPara], rax; pvPara
0x180006396  xor     r8d, r8d; hCryptProv
0x180006399  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18000639c  call    cs:__imp_CertOpenStore
0x1800063a3  nop     dword ptr [rax+rax+00h]
0x1800063a8  mov     [rsp+48h+var_18], rax
0x1800063ad  mov     rsi, rax
0x1800063b0  test    rax, rax
0x1800063b3  jz      short loc_180006434
0x1800063b5  xor     edx, edx; pPrevCertContext
0x1800063b7  mov     rcx, rdi; hCertStore
0x1800063ba  call    cs:__imp_CertEnumCertificatesInStore
0x1800063c1  nop     dword ptr [rax+rax+00h]
0x1800063c6  mov     rbx, rax
0x1800063c9  mov     [rsp+48h+arg_18], rax
0x1800063ce  test    rbx, rbx
0x1800063d1  jz      short loc_180006412
0x1800063d3  xor     r9d, r9d; ppStoreContext
0x1800063d6  mov     rdx, rbx; pCertContext
0x1800063d9  mov     rcx, rsi; hCertStore
0x1800063dc  lea     r8d, [r9+3]; dwAddDisposition
0x1800063e0  call    cs:__imp_CertAddCertificateContextToStore
0x1800063e7  nop     dword ptr [rax+rax+00h]
0x1800063ec  mov     rdx, rbx; pPrevCertContext
0x1800063ef  mov     rcx, rdi; hCertStore
0x1800063f2  call    cs:__imp_CertEnumCertificatesInStore
0x1800063f9  nop     dword ptr [rax+rax+00h]
0x1800063fe  mov     rdx, rax
0x180006401  lea     rcx, [rsp+48h+arg_18]
0x180006406  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x18000640b  mov     rbx, [rsp+48h+arg_18]
0x180006410  jmp     short loc_1800063CE
0x180006412  lea     rcx, [rsp+48h+arg_18]
0x180006417  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18000641c  lea     rcx, [rsp+48h+var_18]
0x180006421  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006426  lea     rcx, [rsp+48h+arg_8]
0x18000642b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006430  xor     eax, eax
0x180006432  jmp     short loc_180006482
0x180006434  call    cs:__imp_GetLastError
0x18000643b  nop     dword ptr [rax+rax+00h]
0x180006440  mov     ebx, eax
0x180006442  test    eax, eax
0x180006444  jle     short loc_18000644F
0x180006446  movzx   ebx, ax
0x180006449  or      ebx, 80070000h
0x18000644f  lea     rcx, [rsp+48h+var_18]
0x180006454  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006459  jmp     short loc_180006476
0x18000645b  call    cs:__imp_GetLastError
0x180006462  nop     dword ptr [rax+rax+00h]
0x180006467  mov     ebx, eax
0x180006469  test    eax, eax
0x18000646b  jle     short loc_180006476
0x18000646d  movzx   ebx, ax
0x180006470  or      ebx, 80070000h
0x180006476  lea     rcx, [rsp+48h+arg_8]
0x18000647b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006480  mov     eax, ebx
0x180006482  mov     rbx, [rsp+48h+arg_0]
0x180006487  mov     rsi, [rsp+48h+arg_10]
0x18000648c  add     rsp, 40h
0x180006490  pop     rdi
0x180006491  retn
```
