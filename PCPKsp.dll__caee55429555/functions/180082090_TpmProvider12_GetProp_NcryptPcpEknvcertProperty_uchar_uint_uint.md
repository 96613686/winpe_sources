# TpmProvider12::GetProp_NcryptPcpEknvcertProperty(uchar *,uint,uint *)

- ea: `0x180082090`
- end: `0x18008226e`
- name: `?GetProp_NcryptPcpEknvcertProperty@TpmProvider12@@UEAAJPEAEIPEAI@Z`
- size: `478`
- prototype: `__int64 __fastcall(TpmProvider12 *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800827c0`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x18005b6fc`
- `0x180073810`
- `0x180082090`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180082137`
- `CRYPT32!CertOpenStore` at `0x180082137`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800821d4`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800821d4`
- `CRYPT32!CertCloseStore` at `0x180082175`
- `CRYPT32!CertCloseStore` at `0x18008220e`
- `CRYPT32!CertCloseStore` at `0x180082175`
- `CRYPT32!CertCloseStore` at `0x18008220e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TpmProvider12::GetProp_NcryptPcpEknvcertProperty(
        TpmProvider12 *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned int LastError; // ebx
  __int64 v9; // rdx
  const char *v10; // r9
  __int64 i; // rbx
  int pvPara; // [rsp+20h] [rbp-50h]
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v15[4]; // [rsp+38h] [rbp-38h]
  HCERTSTORE *p_hCertStore; // [rsp+48h] [rbp-28h]
  char v17; // [rsp+50h] [rbp-20h]
  int *v18[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HCERTSTORE hCertStore; // [rsp+A8h] [rbp+38h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v18, L"TpmProvider12::GetProp_NcryptPcpEknvcertProperty", 1);
  if ( a4 )
  {
    if ( !*((_DWORD *)this + 2) )
    {
      LastError = -2144795643;
      v9 = 364;
      goto LABEL_19;
    }
    *a4 = 8;
    if ( a3 && a2 )
    {
      if ( a3 < 8 )
      {
        LastError = -2144795642;
        v9 = 372;
        goto LABEL_19;
      }
      hCertStore = 0;
      p_hCertStore = &hCertStore;
      v17 = 1;
      hCertStore = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
      if ( !hCertStore )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x185,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider12.cpp",
                      v10);
        if ( hCertStore )
        {
          CertCloseStore(hCertStore, 1u);
          hCertStore = 0;
        }
        goto LABEL_20;
      }
      pCertContext = 0;
      v15[0] = 268496896;
      v15[1] = 61440;
      v15[2] = 268496898;
      v15[3] = 61442;
      for ( i = 0; i != 4; ++i )
      {
        if ( (int)RetrieveEkCert(v15[i], (__int64)&pCertContext) >= 0 )
          CertAddCertificateContextToStore(hCertStore, pCertContext, 4u, 0);
      }
      *(_QWORD *)a2 = hCertStore;
      hCertStore = 0;
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pCertContext);
      if ( hCertStore )
      {
        CertCloseStore(hCertStore, 1u);
        hCertStore = 0;
      }
    }
    KspFunctionLogger::~KspFunctionLogger(v18);
    return 0;
  }
  LastError = -2144795645;
  v9 = 362;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider12.cpp",
    (const char *)LastError,
    pvPara);
LABEL_20:
  KspFunctionLogger::~KspFunctionLogger(v18);
  return LastError;
}

```

## disassembly

```asm
0x180082090  mov     [rsp-18h+arg_0], rbx
0x180082095  mov     [rsp-18h+arg_8], rsi
0x18008209a  push    rbp
0x18008209b  push    rdi
0x18008209c  push    r14
0x18008209e  mov     rbp, rsp
0x1800820a1  sub     rsp, 70h
0x1800820a5  mov     rsi, r9
0x1800820a8  mov     ebx, r8d
0x1800820ab  mov     rdi, rdx
0x1800820ae  mov     r14, rcx
0x1800820b1  mov     r8b, 1; bool
0x1800820b4  lea     rdx, aTpmprovider12G_7; "TpmProvider12::GetProp_NcryptPcpEknvcer"...
0x1800820bb  lea     rcx, [rbp+var_18]; this
0x1800820bf  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800820c4  nop
0x1800820c5  test    rsi, rsi
0x1800820c8  jnz     short loc_1800820D9
0x1800820ca  mov     ebx, 80290403h
0x1800820cf  mov     edx, 16Ah
0x1800820d4  jmp     loc_180082239
0x1800820d9  cmp     dword ptr [r14+8], 0
0x1800820de  jz      loc_18008222F
0x1800820e4  mov     dword ptr [rsi], 8
0x1800820ea  test    ebx, ebx
0x1800820ec  jz      loc_180082222
0x1800820f2  test    rdi, rdi
0x1800820f5  jz      loc_180082222
0x1800820fb  cmp     ebx, 8
0x1800820fe  jnb     short loc_18008210F
0x180082100  mov     ebx, 80290406h
0x180082105  mov     edx, 174h
0x18008210a  jmp     loc_180082239
0x18008210f  mov     [rbp+hCertStore], 0
0x180082117  lea     rax, [rbp+hCertStore]
0x18008211b  mov     [rbp+var_28], rax
0x18008211f  mov     [rbp+var_20], 1
0x180082123  mov     qword ptr [rsp+70h+pvPara], 0; pvPara
0x18008212c  xor     r9d, r9d; dwFlags
0x18008212f  xor     r8d, r8d; hCryptProv
0x180082132  xor     edx, edx; dwEncodingType
0x180082134  lea     ecx, [rdx+2]; lpszStoreProvider
0x180082137  call    cs:__imp_CertOpenStore
0x18008213e  nop     dword ptr [rax+rax+00h]
0x180082143  mov     [rbp+hCertStore], rax
0x180082147  test    rax, rax
0x18008214a  jnz     short loc_18008218E
0x18008214c  mov     rcx, [rbp+18h]; this
0x180082150  lea     r8, aOnecoreBaseNgs_19; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180082157  mov     edx, 185h; void *
0x18008215c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180082161  mov     ebx, eax
0x180082163  mov     rcx, [rbp+hCertStore]; hCertStore
0x180082167  test    rcx, rcx
0x18008216a  jz      loc_18008224D
0x180082170  mov     edx, 1; dwFlags
0x180082175  call    cs:__imp_CertCloseStore
0x18008217c  nop     dword ptr [rax+rax+00h]
0x180082181  mov     [rbp+hCertStore], 0
0x180082189  jmp     loc_18008224D
0x18008218e  mov     [rbp+pCertContext], 0
0x180082196  mov     [rbp+var_38], 1000F000h
0x18008219d  mov     [rbp+var_34], 0F000h
0x1800821a4  mov     [rbp+var_30], 1000F002h
0x1800821ab  mov     [rbp+var_2C], 0F002h
0x1800821b2  xor     ebx, ebx
0x1800821b4  lea     rdx, [rbp+pCertContext]
0x1800821b8  mov     ecx, [rbp+rbx*4+var_38]; unsigned int
0x1800821bc  call    ?RetrieveEkCert@@YAJKAEAV?$unique_any_t@Ucert_context_t@wil@@@wil@@@Z; RetrieveEkCert(ulong,wil::unique_any_t<wil::cert_context_t> &)
0x1800821c1  test    eax, eax
0x1800821c3  js      short loc_1800821E0
0x1800821c5  xor     r9d, r9d; ppStoreContext
0x1800821c8  lea     r8d, [r9+4]; dwAddDisposition
0x1800821cc  mov     rdx, [rbp+pCertContext]; pCertContext
0x1800821d0  mov     rcx, [rbp+hCertStore]; hCertStore
0x1800821d4  call    cs:__imp_CertAddCertificateContextToStore
0x1800821db  nop     dword ptr [rax+rax+00h]
0x1800821e0  inc     rbx
0x1800821e3  cmp     rbx, 4
0x1800821e7  jnz     short loc_1800821B4
0x1800821e9  mov     rax, [rbp+hCertStore]
0x1800821ed  mov     [rdi], rax
0x1800821f0  mov     [rbp+hCertStore], 0
0x1800821f8  lea     rcx, [rbp+pCertContext]
0x1800821fc  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180082201  nop
0x180082202  mov     rcx, [rbp+hCertStore]; hCertStore
0x180082206  test    rcx, rcx
0x180082209  jz      short loc_180082222
0x18008220b  lea     edx, [rbx-3]; dwFlags
0x18008220e  call    cs:__imp_CertCloseStore
0x180082215  nop     dword ptr [rax+rax+00h]
0x18008221a  mov     [rbp+hCertStore], 0
0x180082222  lea     rcx, [rbp+var_18]; this
0x180082226  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18008222b  xor     eax, eax
0x18008222d  jmp     short loc_180082258
0x18008222f  mov     ebx, 80290405h
0x180082234  mov     edx, 16Ch; void *
0x180082239  mov     r9d, ebx; char *
0x18008223c  lea     r8, aOnecoreBaseNgs_19; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180082243  mov     rcx, [rbp+18h]; this
0x180082247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008224c  nop
0x18008224d  lea     rcx, [rbp+var_18]; this
0x180082251  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180082256  mov     eax, ebx
0x180082258  lea     r11, [rsp+70h+var_s0]
0x18008225d  mov     rbx, [r11+20h]
0x180082261  mov     rsi, [r11+28h]
0x180082265  mov     rsp, r11
0x180082268  pop     r14
0x18008226a  pop     rdi
0x18008226b  pop     rbp
0x18008226c  retn
```
