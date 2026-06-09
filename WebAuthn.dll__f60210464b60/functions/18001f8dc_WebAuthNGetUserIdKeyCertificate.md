# WebAuthNGetUserIdKeyCertificate

- ea: `0x18001f8dc`
- end: `0x18001fa5d`
- name: `WebAuthNGetUserIdKeyCertificate`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004bb78`

## callees

- `0x18001687c`
- `0x18001f8dc`
- `0x180020584`
- `0x1800205c4`
- `0x180020614`
- `0x180036da4`
- `0x180036dc8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa42`
- `ngcutils!NgcGetNCryptBinaryBlob` at `0x18001f999`
- `ngcutils!NgcGetNCryptBinaryBlob` at `0x18001f999`
- `CRYPT32!CertCreateCertificateContext` at `0x18001f9ec`
- `CRYPT32!CertCreateCertificateContext` at `0x18001f9ec`
- `cryptngc!NgcOpenUserIdKey` at `0x18001f93a`
- `cryptngc!NgcOpenUserIdKey` at `0x18001f93a`

## string_xrefs

- `0x18001f8fb`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18001f94a`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18001f9b2`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18001f9ff`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`

## pseudocode

```c
__int64 __fastcall WebAuthNGetUserIdKeyCertificate(__int64 a1, PCCERT_CONTEXT *a2)
{
  __int64 v4; // rdx
  unsigned int NCryptBinaryBlob; // ebx
  int v6; // eax
  HLOCAL v7; // rcx
  PCCERT_CONTEXT CertificateContext; // rax
  const char *v9; // r9
  HLOCAL v10; // rcx
  PCCERT_CONTEXT v12; // [rsp+20h] [rbp-20h] BYREF
  HLOCAL *p_hMem; // [rsp+28h] [rbp-18h] BYREF
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  char v15; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbCertEncoded; // [rsp+60h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 1067;
      goto LABEL_3;
    }
    v19 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &v19,
      0);
    v6 = NgcOpenUserIdKey(a1, &v19);
    NCryptBinaryBlob = v6;
    if ( v6 >= 0 )
    {
      p_hMem = &hMem;
      cbCertEncoded = 0;
      hMem = 0;
      v14 = 0;
      v15 = 1;
      NCryptBinaryBlob = NgcGetNCryptBinaryBlob(v19, L"SmartCardKeyCertificate", &v14, &cbCertEncoded);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( (NCryptBinaryBlob & 0x80000000) == 0 )
      {
        CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)hMem, cbCertEncoded);
        v12 = CertificateContext;
        if ( CertificateContext )
        {
          v12 = 0;
          *a2 = CertificateContext;
          wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v12);
          v10 = hMem;
          hMem = 0;
          if ( v10 )
            LocalFree(v10);
          NCryptBinaryBlob = 0;
          goto LABEL_17;
        }
        NCryptBinaryBlob = wil::details::in1diag3::Return_GetLastError(
                             retaddr,
                             (void *)0x43E,
                             (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
                             v9);
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v12);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x438,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
          (const char *)NCryptBinaryBlob,
          (int)v12);
      }
      v7 = hMem;
      hMem = 0;
      if ( v7 )
        LocalFree(v7);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x430,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)v6,
        (int)v12);
    }
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v19);
    return NCryptBinaryBlob;
  }
  v4 = 1066;
LABEL_3:
  NCryptBinaryBlob = -2146893785;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
    (const char *)0x80090027LL,
    (int)v12);
  return NCryptBinaryBlob;
}

```

## disassembly

```asm
0x18001f8dc  push    rbp
0x18001f8de  push    rbx
0x18001f8df  push    rdi
0x18001f8e0  mov     rbp, rsp
0x18001f8e3  sub     rsp, 40h
0x18001f8e7  mov     rdi, rdx
0x18001f8ea  mov     rbx, rcx
0x18001f8ed  test    rcx, rcx
0x18001f8f0  jnz     short loc_18001F914
0x18001f8f2  mov     edx, 42Ah; void *
0x18001f8f7  mov     rcx, [rbp+18h]; this
0x18001f8fb  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f902  mov     ebx, 80090027h
0x18001f907  mov     r9d, ebx; char *
0x18001f90a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f90f  jmp     loc_18001FA53
0x18001f914  test    rdi, rdi
0x18001f917  jnz     short loc_18001F920
0x18001f919  mov     edx, 42Bh
0x18001f91e  jmp     short loc_18001F8F7
0x18001f920  xor     edx, edx
0x18001f922  mov     [rbp+arg_18], 0
0x18001f92a  lea     rcx, [rbp+arg_18]
0x18001f92e  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18001f933  lea     rdx, [rbp+arg_18]
0x18001f937  mov     rcx, rbx
0x18001f93a  call    cs:__imp_NgcOpenUserIdKey
0x18001f940  mov     ebx, eax
0x18001f942  test    eax, eax
0x18001f944  jns     short loc_18001F963
0x18001f946  mov     rcx, [rbp+18h]; this
0x18001f94a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f951  mov     r9d, eax; char *
0x18001f954  mov     edx, 430h; void *
0x18001f959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f95e  jmp     loc_18001FA4A
0x18001f963  mov     rcx, [rbp+arg_18]
0x18001f967  lea     rax, [rbp+hMem]
0x18001f96b  lea     r9, [rbp+cbCertEncoded]
0x18001f96f  mov     [rbp+var_18], rax
0x18001f973  lea     r8, [rbp+var_10]
0x18001f977  mov     [rbp+cbCertEncoded], 0
0x18001f97e  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18001f985  mov     [rbp+hMem], 0
0x18001f98d  mov     [rbp+var_10], 0
0x18001f995  mov     [rbp+var_8], 1
0x18001f999  call    cs:__imp_NgcGetNCryptBinaryBlob
0x18001f99f  lea     rcx, [rbp+var_18]
0x18001f9a3  mov     ebx, eax
0x18001f9a5  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f9aa  test    ebx, ebx
0x18001f9ac  jns     short loc_18001F9DF
0x18001f9ae  mov     rcx, [rbp+18h]; this
0x18001f9b2  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f9b9  mov     r9d, ebx; char *
0x18001f9bc  mov     edx, 438h; void *
0x18001f9c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9c6  mov     rcx, [rbp+hMem]; hMem
0x18001f9ca  mov     [rbp+hMem], 0
0x18001f9d2  test    rcx, rcx
0x18001f9d5  jz      short loc_18001FA4A
0x18001f9d7  call    cs:__imp_LocalFree
0x18001f9dd  jmp     short loc_18001FA4A
0x18001f9df  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x18001f9e3  mov     ecx, 10001h; dwCertEncodingType
0x18001f9e8  mov     rdx, [rbp+hMem]; pbCertEncoded
0x18001f9ec  call    cs:__imp_CertCreateCertificateContext
0x18001f9f2  mov     [rbp+var_20], rax
0x18001f9f6  test    rax, rax
0x18001f9f9  jnz     short loc_18001FA1D
0x18001f9fb  mov     rcx, [rbp+18h]; this
0x18001f9ff  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001fa06  mov     edx, 43Eh; void *
0x18001fa0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fa10  lea     rcx, [rbp+var_20]
0x18001fa14  mov     ebx, eax
0x18001fa16  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18001fa1b  jmp     short loc_18001F9C6
0x18001fa1d  lea     rcx, [rbp+var_20]
0x18001fa21  mov     [rbp+var_20], 0
0x18001fa29  mov     [rdi], rax
0x18001fa2c  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18001fa31  mov     rcx, [rbp+hMem]; hMem
0x18001fa35  mov     [rbp+hMem], 0
0x18001fa3d  test    rcx, rcx
0x18001fa40  jz      short loc_18001FA48
0x18001fa42  call    cs:__imp_LocalFree
0x18001fa48  xor     ebx, ebx
0x18001fa4a  lea     rcx, [rbp+arg_18]
0x18001fa4e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001fa53  mov     eax, ebx
0x18001fa55  add     rsp, 40h
0x18001fa59  pop     rdi
0x18001fa5a  pop     rbx
0x18001fa5b  pop     rbp
0x18001fa5c  retn
```
