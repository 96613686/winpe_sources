# TpmProvider20::RetrieveEkCert(ulong,wil::unique_any_t<wil::cert_context_t> &)

- ea: `0x180028f24`
- end: `0x1800291ef`
- name: `?RetrieveEkCert@TpmProvider20@@QEAAJKAEAV?$unique_any_t@Ucert_context_t@wil@@@wil@@@Z`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180057934`

## callees

- `0x18000f858`
- `0x180010c90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180028f24`
- `0x1800291f8`
- `0x180029260`
- `0x180029320`
- `0x180029384`
- `0x1800293e0`
- `0x180029a20`
- `0x180032110`
- `0x18005b6fc`
- `0x180067e24`
- `0x180067fcc`
- `0x1800768a0`

## import_xrefs

- `CRYPT32!CertCreateContext` at `0x18002910b`
- `CRYPT32!CertCreateContext` at `0x18002910b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TpmProvider20::RetrieveEkCert(BYTE *a1, int a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // edi
  unsigned int LastError; // ebx
  __int64 v8; // r14
  BYTE *v9; // rdi
  int PrimaryAuthSession; // eax
  __int64 v11; // rdx
  unsigned __int16 i; // si
  BYTE *Context; // rax
  const char *v14; // r9
  const struct std::nothrow_t *v15; // rdx
  const struct std::nothrow_t *v17; // rdx
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  int *v19[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[168]; // [rsp+50h] [rbp-B0h] BYREF
  struct tpm12class::TPMW8_SESSION *v21; // [rsp+F8h] [rbp-8h]
  int v22; // [rsp+110h] [rbp+10h]
  int v23; // [rsp+160h] [rbp+60h]
  _BYTE v24[72]; // [rsp+168h] [rbp+68h] BYREF
  __int16 v25; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 v26; // [rsp+1B2h] [rbp+B2h]
  unsigned __int16 v27; // [rsp+1F0h] [rbp+F0h]
  void *Source; // [rsp+1F8h] [rbp+F8h]
  _BYTE v29[196]; // [rsp+200h] [rbp+100h] BYREF
  int v30; // [rsp+2C4h] [rbp+1C4h]
  __int64 v31; // [rsp+2C8h] [rbp+1C8h]
  _BYTE v32[144]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]
  BYTE *pbEncoded; // [rsp+370h] [rbp+270h] BYREF

  pbEncoded = a1;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v19, L"TpmProvider20::RetrieveEkCert", 1);
  tpm12class::TPMW8_NV_ReadPublic::TPMW8_NV_ReadPublic((tpm12class::TPMW8_NV_ReadPublic *)v29);
  v30 = a2;
  v5 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v29, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    LastError = -2144862069;
    if ( v5 != -2144862069 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B1,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider20.cpp",
        (const char *)(unsigned int)v5,
        dwFlags);
      LastError = v6;
    }
    goto LABEL_27;
  }
  v8 = *(unsigned __int16 *)(v31 + 144);
  if ( !(_WORD)v8 )
  {
    LastError = -2146893807;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B3,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider20.cpp",
      (const char *)0x80090011LL,
      dwFlags);
LABEL_27:
    tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic((tpm12class::TPMW8_NV_ReadPublic *)v29);
    KspFunctionLogger::~KspFunctionLogger(v19);
    return LastError;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&pbEncoded, *(unsigned __int16 *)(v31 + 144));
  v9 = pbEncoded;
  if ( pbEncoded )
  {
    tpm12class::TPMW8_NV_Read::TPMW8_NV_Read((tpm12class::TPMW8_NV_Read *)v20);
    v22 = 1073741825;
    v23 = a2;
    PrimaryAuthSession = tpm12class::TPMW82B_BUFFER::CopyFrom(
                           (tpm12class::TPMW82B_BUFFER *)v24,
                           (const struct tpm12class::TPMW82B_BUFFER *)v32);
    LastError = PrimaryAuthSession;
    if ( PrimaryAuthSession < 0 )
    {
      v11 = 1723;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider20.cpp",
        (const char *)(unsigned int)PrimaryAuthSession,
        dwFlags);
      goto LABEL_25;
    }
    PrimaryAuthSession = GetPrimaryAuthSession(v21, 0x40000001u);
    LastError = PrimaryAuthSession;
    if ( PrimaryAuthSession < 0 )
    {
      v11 = 1725;
      goto LABEL_9;
    }
    for ( i = 0; i < (unsigned __int16)v8; i += v27 )
    {
      v26 = i;
      if ( (unsigned int)i + 768 >= (unsigned int)v8 )
        v25 = v8 - i;
      else
        v25 = 768;
      PrimaryAuthSession = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v20, 0);
      LastError = PrimaryAuthSession;
      if ( PrimaryAuthSession < 0 )
      {
        v11 = 1741;
        goto LABEL_9;
      }
      memcpy_s(&v9[i], v8 - i, Source, v27);
    }
    Context = (BYTE *)CertCreateContext(1u, 0x10001u, v9, v8, 0, 0);
    pbEncoded = Context;
    if ( !Context )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6DE,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmprovider20.cpp",
                    v14);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pbEncoded);
LABEL_25:
      tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read((tpm12class::TPMW8_NV_Read *)v20);
      if ( v9 )
        operator delete(v9, v17);
      goto LABEL_27;
    }
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
      a3,
      Context);
    tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read((tpm12class::TPMW8_NV_Read *)v20);
    if ( v9 )
      operator delete(v9, v15);
    tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic((tpm12class::TPMW8_NV_ReadPublic *)v29);
    KspFunctionLogger::~KspFunctionLogger(v19);
    return 0;
  }
  else
  {
    tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic((tpm12class::TPMW8_NV_ReadPublic *)v29);
    KspFunctionLogger::~KspFunctionLogger(v19);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180028f24  mov     [rsp-8+pbEncoded], rcx
0x180028f29  push    rbp
0x180028f2a  push    rbx
0x180028f2b  push    rsi
0x180028f2c  push    rdi
0x180028f2d  push    r12
0x180028f2f  push    r13
0x180028f31  push    r14
0x180028f33  push    r15
0x180028f35  lea     rbp, [rsp-228h]
0x180028f3d  sub     rsp, 328h
0x180028f44  mov     r12, r8
0x180028f47  mov     ebx, edx
0x180028f49  mov     r8b, 1; bool
0x180028f4c  lea     rdx, aTpmprovider20R; "TpmProvider20::RetrieveEkCert"
0x180028f53  lea     rcx, [rsp+360h+var_330]; this
0x180028f58  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180028f5d  nop
0x180028f5e  lea     rcx, [rbp+260h+var_160]; this
0x180028f65  call    ??0TPMW8_NV_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_NV_ReadPublic::TPMW8_NV_ReadPublic(void)
0x180028f6a  nop
0x180028f6b  mov     [rbp+260h+var_9C], ebx
0x180028f71  xor     edx, edx; void *
0x180028f73  lea     rcx, [rbp+260h+var_160]; this
0x180028f7a  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180028f7f  mov     edi, eax
0x180028f81  xor     r13d, r13d
0x180028f84  test    eax, eax
0x180028f86  jns     short loc_180028FB7
0x180028f88  mov     ebx, 8028008Bh
0x180028f8d  cmp     eax, ebx
0x180028f8f  jz      loc_1800291A3
0x180028f95  mov     rcx, [rbp+268h]; this
0x180028f9c  mov     r9d, eax; char *
0x180028f9f  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028fa6  mov     edx, 6B1h; void *
0x180028fab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028fb0  mov     ebx, edi
0x180028fb2  jmp     loc_1800291A3
0x180028fb7  mov     rax, [rbp+260h+var_98]
0x180028fbe  movzx   r14d, word ptr [rax+90h]
0x180028fc6  test    r14w, r14w
0x180028fca  jnz     short loc_180028FF1
0x180028fcc  mov     rcx, [rbp+268h]; this
0x180028fd3  mov     ebx, 80090011h
0x180028fd8  mov     r9d, ebx; char *
0x180028fdb  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028fe2  mov     edx, 6B3h; void *
0x180028fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028fec  jmp     loc_1800291A3
0x180028ff1  mov     rdx, r14
0x180028ff4  lea     rcx, [rbp+260h+pbEncoded]
0x180028ffb  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180029000  nop
0x180029001  mov     rdi, [rbp+260h+pbEncoded]
0x180029008  test    rdi, rdi
0x18002900b  jz      loc_1800291BE
0x180029011  lea     rcx, [rsp+360h+var_310]; this
0x180029016  call    ??0TPMW8_NV_Read@tpm12class@@QEAA@XZ; tpm12class::TPMW8_NV_Read::TPMW8_NV_Read(void)
0x18002901b  nop
0x18002901c  mov     esi, 40000001h
0x180029021  mov     [rbp+260h+var_250], esi
0x180029024  mov     [rbp+260h+var_200], ebx
0x180029027  lea     rdx, [rbp+260h+var_90]; struct tpm12class::TPMW82B_BUFFER *
0x18002902e  lea     rcx, [rbp+260h+var_1F8]; this
0x180029032  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x180029037  mov     ebx, eax
0x180029039  test    eax, eax
0x18002903b  jns     short loc_18002905D
0x18002903d  mov     edx, 6BBh; void *
0x180029042  mov     rcx, [rbp+268h]; this
0x180029049  mov     r9d, eax; char *
0x18002904c  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180029053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029058  jmp     loc_18002918A
0x18002905d  mov     edx, esi; unsigned int
0x18002905f  mov     rcx, [rbp+260h+var_268]; this
0x180029063  call    ?GetPrimaryAuthSession@@YAJPEAVTPMW8_SESSION@tpm12class@@I@Z; GetPrimaryAuthSession(tpm12class::TPMW8_SESSION *,uint)
0x180029068  mov     ebx, eax
0x18002906a  test    eax, eax
0x18002906c  jns     short loc_180029075
0x18002906e  mov     edx, 6BDh
0x180029073  jmp     short loc_180029042
0x180029075  mov     esi, r13d
0x180029078  mov     ecx, 300h
0x18002907d  cmp     si, r14w
0x180029081  jnb     short loc_1800290F1
0x180029083  mov     [rbp+260h+var_1AE], si
0x18002908a  movzx   eax, si
0x18002908d  add     eax, ecx
0x18002908f  cmp     eax, r14d
0x180029092  jnb     short loc_18002909D
0x180029094  mov     [rbp+260h+var_1B0], cx
0x18002909b  jmp     short loc_1800290AB
0x18002909d  movzx   eax, r14w
0x1800290a1  sub     ax, si
0x1800290a4  mov     [rbp+260h+var_1B0], ax
0x1800290ab  xor     edx, edx; void *
0x1800290ad  lea     rcx, [rsp+360h+var_310]; this
0x1800290b2  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1800290b7  mov     ebx, eax
0x1800290b9  test    eax, eax
0x1800290bb  js      short loc_1800290E7
0x1800290bd  movzx   eax, si
0x1800290c0  movzx   r9d, [rbp+260h+var_170]; SourceSize
0x1800290c8  mov     rdx, r14
0x1800290cb  sub     rdx, rax; DestinationSize
0x1800290ce  lea     rcx, [rax+rdi]; Destination
0x1800290d2  mov     r8, [rbp+260h+Source]; Source
0x1800290d9  call    memcpy_s
0x1800290de  add     si, [rbp+260h+var_170]
0x1800290e5  jmp     short loc_180029078
0x1800290e7  mov     edx, 6CDh
0x1800290ec  jmp     loc_180029042
0x1800290f1  mov     [rsp+360h+pCreatePara], r13; pCreatePara
0x1800290f6  mov     [rsp+360h+dwFlags], r13d; dwFlags
0x1800290fb  mov     r9d, r14d; cbEncoded
0x1800290fe  mov     r8, rdi; pbEncoded
0x180029101  mov     edx, 10001h; dwEncodingType
0x180029106  mov     ecx, 1; dwContextType
0x18002910b  call    cs:__imp_CertCreateContext
0x180029112  nop     dword ptr [rax+rax+00h]
0x180029117  mov     [rbp+260h+pbEncoded], rax
0x18002911e  test    rax, rax
0x180029121  jz      short loc_180029163
0x180029123  mov     rdx, rax
0x180029126  mov     rcx, r12
0x180029129  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x18002912e  nop
0x18002912f  lea     rcx, [rsp+360h+var_310]; this
0x180029134  call    ??1TPMW8_NV_Read@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read(void)
0x180029139  nop
0x18002913a  test    rdi, rdi
0x18002913d  jz      short loc_180029148
0x18002913f  mov     rcx, rdi; void *
0x180029142  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029147  nop
0x180029148  lea     rcx, [rbp+260h+var_160]; this
0x18002914f  call    ??1TPMW8_NV_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic(void)
0x180029154  nop
0x180029155  lea     rcx, [rsp+360h+var_330]; this
0x18002915a  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002915f  xor     eax, eax
0x180029161  jmp     short loc_1800291DA
0x180029163  mov     rcx, [rbp+268h]; this
0x18002916a  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180029171  mov     edx, 6DEh; void *
0x180029176  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002917b  mov     ebx, eax
0x18002917d  lea     rcx, [rbp+260h+pbEncoded]
0x180029184  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180029189  nop
0x18002918a  lea     rcx, [rsp+360h+var_310]; this
0x18002918f  call    ??1TPMW8_NV_Read@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read(void)
0x180029194  nop
0x180029195  test    rdi, rdi
0x180029198  jz      short loc_1800291A3
0x18002919a  mov     rcx, rdi; void *
0x18002919d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800291a2  nop
0x1800291a3  lea     rcx, [rbp+260h+var_160]; this
0x1800291aa  call    ??1TPMW8_NV_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic(void)
0x1800291af  nop
0x1800291b0  lea     rcx, [rsp+360h+var_330]; this
0x1800291b5  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800291ba  mov     eax, ebx
0x1800291bc  jmp     short loc_1800291DA
0x1800291be  lea     rcx, [rbp+260h+var_160]; this
0x1800291c5  call    ??1TPMW8_NV_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic(void)
0x1800291ca  nop
0x1800291cb  lea     rcx, [rsp+360h+var_330]; this
0x1800291d0  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800291d5  mov     eax, 80070008h
0x1800291da  add     rsp, 328h
0x1800291e1  pop     r15
0x1800291e3  pop     r14
0x1800291e5  pop     r13
0x1800291e7  pop     r12
0x1800291e9  pop     rdi
0x1800291ea  pop     rsi
0x1800291eb  pop     rbx
0x1800291ec  pop     rbp
0x1800291ed  retn
```
