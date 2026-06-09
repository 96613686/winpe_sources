# TpmProvider20::GetEkNvCert(TpmProvider20::EkCertType,uchar *,uint,uint *)

- ea: `0x180057934`
- end: `0x180057b1d`
- name: `?GetEkNvCert@TpmProvider20@@IEAAJW4EkCertType@1@PEAEIPEAI@Z`
- size: `489`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800578a0`
- `0x18006df60`
- `0x1800711c0`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180028f24`
- `0x180057934`
- `0x18005b6fc`
- `0x18006d388`
- `0x1800c2cd4`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1800579f5`
- `CRYPT32!CertOpenStore` at `0x1800579f5`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180057a80`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180057a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TpmProvider20::GetEkNvCert(__int64 a1, int a2, _QWORD *a3, unsigned int a4, _DWORD *a5)
{
  unsigned int LastError; // ebx
  __int64 v10; // rdx
  BYTE *v11; // rcx
  HCERTSTORE v12; // rsi
  const char *v13; // r9
  __int64 i; // rdi
  PCCERT_CONTEXT v15; // rbx
  int pvPara; // [rsp+20h] [rbp-41h]
  HCERTSTORE v18; // [rsp+30h] [rbp-31h] BYREF
  int *v19[3]; // [rsp+38h] [rbp-29h] BYREF
  _DWORD v20[24]; // [rsp+50h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]
  PCCERT_CONTEXT pCertContext; // [rsp+C0h] [rbp+5Fh] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v19, L"TpmProvider20::GetEkNvCert", 1);
  v20[0] = 29360130;
  v20[1] = 29360138;
  v20[2] = 29360146;
  v20[3] = 29360148;
  v20[4] = 29360150;
  v20[5] = 29360152;
  v20[6] = 29360154;
  v20[7] = 29360156;
  v20[8] = 29360158;
  if ( !*(_DWORD *)(a1 + 8) )
  {
    LastError = -2144795643;
    v10 = 417;
    goto LABEL_19;
  }
  *a5 = 8;
  if ( !a4 || !a3 )
  {
LABEL_16:
    KspFunctionLogger::~KspFunctionLogger(v19);
    return 0;
  }
  if ( a4 < 8 )
  {
    LastError = -2144795642;
    v10 = 425;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider20.cpp",
      (const char *)LastError,
      pvPara);
    goto LABEL_20;
  }
  v12 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  v18 = v12;
  if ( v12 )
  {
    pCertContext = 0;
    for ( i = 0; i != 9; ++i )
    {
      if ( (int)TpmProvider20::RetrieveEkCert(v11, v20[i], (__int64)&pCertContext) >= 0 )
      {
        if ( (v15 = pCertContext, !a2)
          && !strncmp_0(pCertContext->pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId, "1.2.840.113549", 0xEu)
          || a2 == 1 && !strncmp_0(v15->pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId, "1.2.840.10045.2.1", 0x11u) )
        {
          CertAddCertificateContextToStore(v12, v15, 4u, 0);
        }
      }
    }
    v18 = 0;
    *a3 = v12;
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pCertContext);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    goto LABEL_16;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1B1,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider20.cpp",
                v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
LABEL_20:
  KspFunctionLogger::~KspFunctionLogger(v19);
  return LastError;
}

```

## disassembly

```asm
0x180057934  push    rbp
0x180057936  push    rbx
0x180057937  push    rsi
0x180057938  push    rdi
0x180057939  push    r14
0x18005793b  push    r15
0x18005793d  lea     rbp, [rsp-27h]
0x180057942  sub     rsp, 88h
0x180057949  mov     edi, r9d
0x18005794c  mov     r15, r8
0x18005794f  mov     r14d, edx
0x180057952  mov     rbx, rcx
0x180057955  mov     r8b, 1; bool
0x180057958  lea     rdx, aTpmprovider20G_17; "TpmProvider20::GetEkNvCert"
0x18005795f  lea     rcx, [rbp+4Fh+var_78]; this
0x180057963  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180057968  nop
0x180057969  mov     [rbp+4Fh+var_60], 1C00002h
0x180057970  mov     [rbp+4Fh+var_5C], 1C0000Ah
0x180057977  mov     [rbp+4Fh+var_58], 1C00012h
0x18005797e  mov     [rbp+4Fh+var_54], 1C00014h
0x180057985  mov     [rbp+4Fh+var_50], 1C00016h
0x18005798c  mov     [rbp+4Fh+var_4C], 1C00018h
0x180057993  mov     [rbp+4Fh+var_48], 1C0001Ah
0x18005799a  mov     [rbp+4Fh+var_44], 1C0001Ch
0x1800579a1  mov     [rbp+4Fh+var_40], 1C0001Eh
0x1800579a8  cmp     dword ptr [rbx+8], 0
0x1800579ac  jz      loc_180057AE3
0x1800579b2  mov     rax, [rbp+4Fh+arg_20]
0x1800579b6  mov     dword ptr [rax], 8
0x1800579bc  test    edi, edi
0x1800579be  jz      loc_180057AB4
0x1800579c4  test    r15, r15
0x1800579c7  jz      loc_180057AB4
0x1800579cd  cmp     edi, 8
0x1800579d0  jnb     short loc_1800579E1
0x1800579d2  mov     ebx, 80290406h
0x1800579d7  mov     edx, 1A9h
0x1800579dc  jmp     loc_180057AED
0x1800579e1  mov     qword ptr [rsp+0B0h+pvPara], 0; pvPara
0x1800579ea  xor     r9d, r9d; dwFlags
0x1800579ed  xor     r8d, r8d; hCryptProv
0x1800579f0  xor     edx, edx; dwEncodingType
0x1800579f2  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800579f5  call    cs:__imp_CertOpenStore
0x1800579fc  nop     dword ptr [rax+rax+00h]
0x180057a01  mov     rsi, rax
0x180057a04  mov     [rbp+4Fh+var_80], rax
0x180057a08  test    rax, rax
0x180057a0b  jz      loc_180057AC1
0x180057a11  mov     [rbp+4Fh+pCertContext], 0
0x180057a19  xor     edi, edi
0x180057a1b  lea     r8, [rbp+4Fh+pCertContext]
0x180057a1f  mov     edx, [rbp+rdi*4+4Fh+var_60]
0x180057a23  call    ?RetrieveEkCert@TpmProvider20@@QEAAJKAEAV?$unique_any_t@Ucert_context_t@wil@@@wil@@@Z; TpmProvider20::RetrieveEkCert(ulong,wil::unique_any_t<wil::cert_context_t> &)
0x180057a28  test    eax, eax
0x180057a2a  js      short loc_180057A8C
0x180057a2c  mov     rbx, [rbp+4Fh+pCertContext]
0x180057a30  test    r14d, r14d
0x180057a33  jnz     short loc_180057A51
0x180057a35  mov     rcx, [rbx+18h]
0x180057a39  lea     r8d, [r14+0Eh]; MaxCount
0x180057a3d  lea     rdx, Str2; "1.2.840.113549"
0x180057a44  mov     rcx, [rcx+60h]; Str1
0x180057a48  call    strncmp_0
0x180057a4d  test    eax, eax
0x180057a4f  jz      short loc_180057A73
0x180057a51  cmp     r14d, 1
0x180057a55  jnz     short loc_180057A8C
0x180057a57  mov     rcx, [rbx+18h]
0x180057a5b  lea     r8d, [r14+10h]; MaxCount
0x180057a5f  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x180057a66  mov     rcx, [rcx+60h]; Str1
0x180057a6a  call    strncmp_0
0x180057a6f  test    eax, eax
0x180057a71  jnz     short loc_180057A8C
0x180057a73  xor     r9d, r9d; ppStoreContext
0x180057a76  lea     r8d, [r9+4]; dwAddDisposition
0x180057a7a  mov     rdx, rbx; pCertContext
0x180057a7d  mov     rcx, rsi; hCertStore
0x180057a80  call    cs:__imp_CertAddCertificateContextToStore
0x180057a87  nop     dword ptr [rax+rax+00h]
0x180057a8c  inc     rdi
0x180057a8f  cmp     rdi, 9
0x180057a93  jnz     short loc_180057A1B
0x180057a95  mov     [rbp+4Fh+var_80], 0
0x180057a9d  mov     [r15], rsi
0x180057aa0  lea     rcx, [rbp+4Fh+pCertContext]
0x180057aa4  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180057aa9  nop
0x180057aaa  lea     rcx, [rbp+4Fh+var_80]
0x180057aae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057ab3  nop
0x180057ab4  lea     rcx, [rbp+4Fh+var_78]; this
0x180057ab8  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180057abd  xor     eax, eax
0x180057abf  jmp     short loc_180057B0C
0x180057ac1  mov     rcx, [rbp+57h]; this
0x180057ac5  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180057acc  mov     edx, 1B1h; void *
0x180057ad1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180057ad6  mov     ebx, eax
0x180057ad8  lea     rcx, [rbp+4Fh+var_80]
0x180057adc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057ae1  jmp     short loc_180057B01
0x180057ae3  mov     ebx, 80290405h
0x180057ae8  mov     edx, 1A1h; void *
0x180057aed  mov     r9d, ebx; char *
0x180057af0  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180057af7  mov     rcx, [rbp+57h]; this
0x180057afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057b00  nop
0x180057b01  lea     rcx, [rbp+4Fh+var_78]; this
0x180057b05  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180057b0a  mov     eax, ebx
0x180057b0c  add     rsp, 88h
0x180057b13  pop     r15
0x180057b15  pop     r14
0x180057b17  pop     rdi
0x180057b18  pop     rsi
0x180057b19  pop     rbx
0x180057b1a  pop     rbp
0x180057b1b  retn
```
