# RetrieveEkCert(ulong,wil::unique_any_t<wil::cert_context_t> &)

- ea: `0x180073810`
- end: `0x180073d1d`
- name: `?RetrieveEkCert@@YAJKAEAV?$unique_any_t@Ucert_context_t@wil@@@wil@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180082090`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029260`
- `0x180029384`
- `0x1800296b0`
- `0x180029a20`
- `0x18002b678`
- `0x18002bafc`
- `0x18002bb88`
- `0x18002c088`
- `0x180040850`
- `0x18004f1dc`
- `0x18004f7fc`
- `0x18005b6fc`
- `0x180073810`
- `0x180073d24`
- `0x180073d98`
- `0x180073e30`
- `0x1800768a0`
- `0x180076e70`
- `0x1800b8370`
- `0x1800b88d0`
- `0x1800b8990`

## import_xrefs

- `CRYPT32!CertCreateContext` at `0x180073b6b`
- `CRYPT32!CertCreateContext` at `0x180073ba9`
- `CRYPT32!CertCreateContext` at `0x180073b6b`
- `CRYPT32!CertCreateContext` at `0x180073ba9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RetrieveEkCert(unsigned int a1, __int64 a2)
{
  int v4; // eax
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  int EndorsementSession; // eax
  unsigned int v11; // r14d
  BYTE *v12; // rdi
  unsigned int v13; // esi
  __int64 v14; // rbx
  int v15; // ecx
  int v16; // r15d
  _BYTE *v17; // rcx
  __int64 v18; // rax
  const struct std::nothrow_t *v19; // rdx
  const void *v20; // rax
  __int64 v21; // rdx
  const void *Context; // rax
  const char *v23; // r9
  const struct std::nothrow_t *v24; // rdx
  const struct std::nothrow_t *v26; // rdx
  int dwFlags; // [rsp+20h] [rbp-E0h]
  int dwFlagsa; // [rsp+20h] [rbp-E0h]
  BYTE *v29; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v30[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+68h] [rbp-98h]
  char v34; // [rsp+70h] [rbp-90h]
  __int16 v35; // [rsp+78h] [rbp-88h]
  char v36; // [rsp+7Ah] [rbp-86h]
  unsigned __int16 v37; // [rsp+7Ch] [rbp-84h]
  __int16 v38; // [rsp+7Eh] [rbp-82h]
  BYTE *pbEncoded; // [rsp+80h] [rbp-80h]
  _QWORD v40[3]; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  char v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+F0h] [rbp-10h]
  unsigned int v47; // [rsp+F4h] [rbp-Ch]
  int v48; // [rsp+F8h] [rbp-8h]
  _DWORD SourceSize[5]; // [rsp+FCh] [rbp-4h]
  _QWORD v50[3]; // [rsp+110h] [rbp+10h] BYREF
  int v51; // [rsp+128h] [rbp+28h]
  __int64 v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  char v54; // [rsp+140h] [rbp+40h]
  int v55; // [rsp+14Ch] [rbp+4Ch]
  DWORD cbEncoded; // [rsp+16Ch] [rbp+6Ch]
  _BYTE v57[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v58[112]; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v59; // [rsp+200h] [rbp+100h]
  unsigned __int8 *v60; // [rsp+208h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]
  __int64 v62; // [rsp+260h] [rbp+160h] BYREF
  __int64 v63; // [rsp+268h] [rbp+168h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v57, L"RetrieveEkCert", 1);
  tpm12class::TPM_GetCapability::TPM_GetCapability((tpm12class::TPM_GetCapability *)v58);
  v40[1] = 0;
  v40[2] = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v40[0] = &tpm12class::TPM_COMMAND::`vftable';
  tpm12class::TPM_COMMAND::Clear((tpm12class::TPM_COMMAND *)v40, 1u);
  v40[0] = &tpm12class::TPM_NV_ReadValue::`vftable';
  tpm12class::TPM_NV_ReadValue::Clear((tpm12class::TPM_NV_ReadValue *)v40, 1u);
  v4 = tpm12class::TPM_GetCapability::SetupCapability((tpm12class::TPM_GetCapability *)v58, 0x11u, a1);
  LastError = v4;
  if ( v4 < 0 )
  {
    v6 = 59;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
      (const char *)(unsigned int)v4,
      dwFlags);
LABEL_43:
    tpm12class::TPM_NV_ReadValue::~TPM_NV_ReadValue((tpm12class::TPM_NV_ReadValue *)v40);
    tpm12class::TPM_GetCapability::~TPM_GetCapability((tpm12class::TPM_GetCapability *)v58);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v57);
    return LastError;
  }
  v4 = tpm12class::TPM_COMMAND::Execute((tpm12class::TPM_COMMAND *)v58);
  LastError = v4;
  if ( v4 < 0 )
  {
    v6 = 60;
    goto LABEL_5;
  }
  v50[1] = 0;
  v50[2] = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v50[0] = &tpm12class::TPM_NV_DATA_PUBLIC::`vftable';
  tpm12class::TPM_NV_DATA_PUBLIC::Clear((tpm12class::TPM_NV_DATA_PUBLIC *)v50, 1u);
  v7 = tpm12class::TpmDataObject::Set((tpm12class::TpmDataObject *)v50, v60, v59, 0, 0);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = 64;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
      (const char *)v8,
      dwFlagsa);
LABEL_42:
    tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC((tpm12class::TPM_NV_DATA_PUBLIC *)v50);
    goto LABEL_43;
  }
  if ( !cbEncoded )
  {
    LastError = -2146893807;
    v8 = 2148073489LL;
    v9 = 66;
    goto LABEL_8;
  }
  v63 = 0;
  EndorsementSession = GetEndorsementSession(&v63);
  LastError = EndorsementSession;
  if ( EndorsementSession < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
      (const char *)(unsigned int)EndorsementSession,
      dwFlagsa);
LABEL_41:
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v63, 0);
    goto LABEL_42;
  }
  v46 = v55;
  v11 = cbEncoded;
  wil::make_unique_nothrow<unsigned char [0]>(&v29, cbEncoded);
  v12 = v29;
  if ( v29 )
  {
    v13 = 0;
    v14 = v63;
    while ( v13 < v11 )
    {
      v47 = v13;
      v15 = v11 - v13;
      if ( v13 + 768 < v11 )
        v15 = 768;
      v48 = v15;
      v45 = v14;
      v16 = tpm12class::TPM_COMMAND::Execute((tpm12class::TPM_COMMAND *)v40);
      v45 = 0;
      if ( v16 < 0 && (SourceSize[0] != v48 || !*(_QWORD *)&SourceSize[1]) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
          (const char *)(unsigned int)v16,
          dwFlagsa);
        if ( v12 )
          operator delete(v12, v19);
        wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v63, 0);
        tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC((tpm12class::TPM_NV_DATA_PUBLIC *)v50);
        LastError = v16;
        goto LABEL_43;
      }
      memcpy_s(&v12[v13], v11 - v13, *(const void *const *)&SourceSize[1], SourceSize[0]);
      v13 += SourceSize[0];
      v17 = *(_BYTE **)&SourceSize[1];
      if ( *(_QWORD *)&SourceSize[1] )
      {
        v18 = SourceSize[0];
        if ( SourceSize[0] )
        {
          do
          {
            *v17++ = 0;
            --v18;
          }
          while ( v18 );
          v17 = *(_BYTE **)&SourceSize[1];
        }
        operator delete(v17);
        *(_QWORD *)&SourceSize[1] = 0;
      }
      SourceSize[0] = 0;
    }
    v62 = 0;
    v30[1] = 0;
    v30[2] = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v30[0] = &tpm12class::TCG_PCCLIENT_STORED_CERT::`vftable';
    tpm12class::TCG_PCCLIENT_STORED_CERT::Clear((tpm12class::TCG_PCCLIENT_STORED_CERT *)v30, 1u);
    if ( tpm12class::TpmDataObject::Set((tpm12class::TpmDataObject *)v30, v12, v11, 0, 0) < 0
      || v35 != 4097
      || v36
      || v38 != 4098
      || (v20 = CertCreateContext(1u, 0x10001u, pbEncoded, v37, 0, 0),
          wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
            &v62,
            v20),
          (v21 = v62) == 0) )
    {
      Context = CertCreateContext(1u, 0x10001u, v12, v11, 0, 0);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
        &v62,
        Context);
      v21 = v62;
      if ( !v62 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x94,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers12.cpp",
                      v23);
        tpm12class::TCG_PCCLIENT_STORED_CERT::~TCG_PCCLIENT_STORED_CERT((tpm12class::TCG_PCCLIENT_STORED_CERT *)v30);
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v62);
        if ( v12 )
          operator delete(v12, v26);
        goto LABEL_41;
      }
    }
    v62 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
      a2,
      v21);
    tpm12class::TCG_PCCLIENT_STORED_CERT::~TCG_PCCLIENT_STORED_CERT((tpm12class::TCG_PCCLIENT_STORED_CERT *)v30);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v62);
    if ( v12 )
      operator delete(v12, v24);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v63, 0);
    tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC((tpm12class::TPM_NV_DATA_PUBLIC *)v50);
    tpm12class::TPM_NV_ReadValue::~TPM_NV_ReadValue((tpm12class::TPM_NV_ReadValue *)v40);
    tpm12class::TPM_GetCapability::~TPM_GetCapability((tpm12class::TPM_GetCapability *)v58);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v57);
    return 0;
  }
  else
  {
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v63, 0);
    tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC((tpm12class::TPM_NV_DATA_PUBLIC *)v50);
    tpm12class::TPM_NV_ReadValue::~TPM_NV_ReadValue((tpm12class::TPM_NV_ReadValue *)v40);
    tpm12class::TPM_GetCapability::~TPM_GetCapability((tpm12class::TPM_GetCapability *)v58);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v57);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180073810  mov     [rsp-8+arg_0], rbx
0x180073815  push    rbp
0x180073816  push    rsi
0x180073817  push    rdi
0x180073818  push    r12
0x18007381a  push    r13
0x18007381c  push    r14
0x18007381e  push    r15
0x180073820  lea     rbp, [rsp-110h]
0x180073828  sub     rsp, 210h
0x18007382f  mov     r13, rdx
0x180073832  mov     ebx, ecx
0x180073834  mov     r8b, 1; bool
0x180073837  lea     rdx, aRetrieveekcert; "RetrieveEkCert"
0x18007383e  lea     rcx, [rbp+140h+var_D0]; this
0x180073842  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180073847  nop
0x180073848  lea     rcx, [rbp+140h+var_B0]; this
0x18007384f  call    ??0TPM_GetCapability@tpm12class@@QEAA@XZ; tpm12class::TPM_GetCapability::TPM_GetCapability(void)
0x180073854  nop
0x180073855  xor     r15d, r15d
0x180073858  mov     [rbp+140h+var_1A8], r15
0x18007385c  mov     [rbp+140h+var_1A0], r15
0x180073860  mov     [rbp+140h+var_198], r15d
0x180073864  mov     [rbp+140h+var_190], r15
0x180073868  mov     [rbp+140h+var_188], r15
0x18007386c  mov     [rbp+140h+var_180], r15b
0x180073870  lea     rax, ??_7TPM_COMMAND@tpm12class@@6B@; const tpm12class::TPM_COMMAND::`vftable'
0x180073877  mov     [rbp+140h+var_1B0], rax
0x18007387b  mov     dl, 1; unsigned __int8
0x18007387d  lea     rcx, [rbp+140h+var_1B0]; this
0x180073881  call    ?Clear@TPM_COMMAND@tpm12class@@MEAAJE@Z; tpm12class::TPM_COMMAND::Clear(uchar)
0x180073886  lea     rax, ??_7TPM_NV_ReadValue@tpm12class@@6B@; const tpm12class::TPM_NV_ReadValue::`vftable'
0x18007388d  mov     [rbp+140h+var_1B0], rax
0x180073891  mov     dl, 1; unsigned __int8
0x180073893  lea     rcx, [rbp+140h+var_1B0]; this
0x180073897  call    ?Clear@TPM_NV_ReadValue@tpm12class@@MEAAJE@Z; tpm12class::TPM_NV_ReadValue::Clear(uchar)
0x18007389c  nop
0x18007389d  mov     r8d, ebx; unsigned int
0x1800738a0  lea     edx, [r15+11h]; unsigned int
0x1800738a4  lea     rcx, [rbp+140h+var_B0]; this
0x1800738ab  call    ?SetupCapability@TPM_GetCapability@tpm12class@@QEAAJII@Z; tpm12class::TPM_GetCapability::SetupCapability(uint,uint)
0x1800738b0  mov     ebx, eax
0x1800738b2  test    eax, eax
0x1800738b4  jns     short loc_1800738BC
0x1800738b6  lea     edx, [r15+3Bh]
0x1800738ba  jmp     short loc_1800738D3
0x1800738bc  lea     rcx, [rbp+140h+var_B0]; this
0x1800738c3  call    ?Execute@TPM_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPM_COMMAND::Execute(void)
0x1800738c8  mov     ebx, eax
0x1800738ca  test    eax, eax
0x1800738cc  jns     short loc_1800738EE
0x1800738ce  mov     edx, 3Ch ; '<'; void *
0x1800738d3  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800738da  mov     r9d, eax; char *
0x1800738dd  mov     rcx, [rbp+148h]; this
0x1800738e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800738e9  jmp     loc_180073C9F
0x1800738ee  mov     [rbp+140h+var_128], r15
0x1800738f2  mov     [rbp+140h+var_120], r15
0x1800738f6  mov     [rbp+140h+var_118], r15d
0x1800738fa  mov     [rbp+140h+var_110], r15
0x1800738fe  mov     [rbp+140h+var_108], r15
0x180073902  mov     [rbp+140h+var_100], r15b
0x180073906  lea     rax, ??_7TPM_NV_DATA_PUBLIC@tpm12class@@6B@; const tpm12class::TPM_NV_DATA_PUBLIC::`vftable'
0x18007390d  mov     [rbp+140h+var_130], rax
0x180073911  mov     dl, 1; unsigned __int8
0x180073913  lea     rcx, [rbp+140h+var_130]; this
0x180073917  call    ?Clear@TPM_NV_DATA_PUBLIC@tpm12class@@MEAAJE@Z; tpm12class::TPM_NV_DATA_PUBLIC::Clear(uchar)
0x18007391c  nop
0x18007391d  mov     qword ptr [rsp+240h+dwFlags], r15; int
0x180073922  xor     r9d, r9d; unsigned __int8 **
0x180073925  mov     r8d, [rbp+140h+var_40]; unsigned int
0x18007392c  mov     rdx, [rbp+140h+var_38]; unsigned __int8 *
0x180073933  lea     rcx, [rbp+140h+var_130]; this
0x180073937  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x18007393c  mov     ebx, eax
0x18007393e  test    eax, eax
0x180073940  jns     short loc_180073962
0x180073942  mov     r9d, eax; char *
0x180073945  mov     edx, 40h ; '@'; void *
0x18007394a  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180073951  mov     rcx, [rbp+148h]; this
0x180073958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007395d  jmp     loc_180073C95
0x180073962  cmp     [rbp+140h+cbEncoded], r15d
0x180073966  jnz     short loc_180073977
0x180073968  mov     ebx, 80090011h
0x18007396d  mov     r9d, ebx
0x180073970  mov     edx, 42h ; 'B'
0x180073975  jmp     short loc_18007394A
0x180073977  mov     [rbp+140h+arg_18], r15
0x18007397e  lea     rcx, [rbp+140h+arg_18]
0x180073985  call    ?GetEndorsementSession@@YAJAEAV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@@Z; GetEndorsementSession(wistd::unique_ptr<tpm12class::TPM_SESSION,wistd::default_delete<tpm12class::TPM_SESSION>> &)
0x18007398a  mov     ebx, eax
0x18007398c  test    eax, eax
0x18007398e  jns     short loc_1800739B0
0x180073990  mov     rcx, [rbp+148h]; this
0x180073997  mov     r9d, eax; char *
0x18007399a  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800739a1  mov     edx, 46h ; 'F'; void *
0x1800739a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800739ab  jmp     loc_180073C86
0x1800739b0  mov     eax, [rbp+140h+var_F4]
0x1800739b3  mov     [rbp+140h+var_150], eax
0x1800739b6  mov     r14d, [rbp+140h+cbEncoded]
0x1800739ba  mov     edx, r14d
0x1800739bd  lea     rcx, [rsp+240h+var_210]
0x1800739c2  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800739c7  nop
0x1800739c8  mov     rdi, [rsp+240h+var_210]
0x1800739cd  test    rdi, rdi
0x1800739d0  jz      loc_180073CC3
0x1800739d6  mov     esi, r15d
0x1800739d9  mov     rbx, [rbp+140h+arg_18]
0x1800739e0  cmp     esi, r14d
0x1800739e3  jnb     loc_180073ACA
0x1800739e9  mov     [rbp+140h+var_14C], esi
0x1800739ec  mov     r12d, r14d
0x1800739ef  sub     r12d, esi
0x1800739f2  lea     eax, [rsi+300h]
0x1800739f8  mov     ecx, r12d
0x1800739fb  mov     edx, 300h
0x180073a00  cmp     eax, r14d
0x180073a03  cmovb   ecx, edx
0x180073a06  mov     [rbp+140h+var_148], ecx
0x180073a09  mov     [rbp+140h+var_170], rbx
0x180073a0d  lea     rcx, [rbp+140h+var_1B0]; this
0x180073a11  call    ?Execute@TPM_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPM_COMMAND::Execute(void)
0x180073a16  mov     r15d, eax
0x180073a19  mov     [rbp+140h+var_170], 0
0x180073a21  mov     r8, qword ptr [rbp+140h+SourceSize+4]; Source
0x180073a25  mov     eax, [rbp+140h+SourceSize]
0x180073a28  test    r15d, r15d
0x180073a2b  jns     short loc_180073A37
0x180073a2d  cmp     eax, [rbp+140h+var_148]
0x180073a30  jnz     short loc_180073A80
0x180073a32  test    r8, r8
0x180073a35  jz      short loc_180073A80
0x180073a37  mov     r9, rax; SourceSize
0x180073a3a  mov     edx, r12d; DestinationSize
0x180073a3d  mov     ecx, esi
0x180073a3f  add     rcx, rdi; Destination
0x180073a42  call    memcpy_s
0x180073a47  add     esi, [rbp+140h+SourceSize]
0x180073a4a  mov     rcx, qword ptr [rbp+140h+SourceSize+4]
0x180073a4e  xor     r15d, r15d
0x180073a51  test    rcx, rcx
0x180073a54  jz      short loc_180073A77
0x180073a56  mov     eax, [rbp+140h+SourceSize]
0x180073a59  test    rax, rax
0x180073a5c  jz      short loc_180073A6E
0x180073a5e  mov     [rcx], r15b
0x180073a61  inc     rcx
0x180073a64  sub     rax, 1
0x180073a68  jnz     short loc_180073A5E
0x180073a6a  mov     rcx, qword ptr [rbp+140h+SourceSize+4]; Block
0x180073a6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180073a73  mov     qword ptr [rbp+140h+SourceSize+4], r15
0x180073a77  mov     [rbp+140h+SourceSize], r15d
0x180073a7b  jmp     loc_1800739E0
0x180073a80  mov     rcx, [rbp+148h]; this
0x180073a87  mov     r9d, r15d; char *
0x180073a8a  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180073a91  mov     edx, 65h ; 'e'; void *
0x180073a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073a9b  nop
0x180073a9c  test    rdi, rdi
0x180073a9f  jz      short loc_180073AAA
0x180073aa1  mov     rcx, rdi; void *
0x180073aa4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073aa9  nop
0x180073aaa  xor     edx, edx
0x180073aac  lea     rcx, [rbp+140h+arg_18]
0x180073ab3  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180073ab8  nop
0x180073ab9  lea     rcx, [rbp+140h+var_130]; this
0x180073abd  call    ??1TPM_NV_DATA_PUBLIC@tpm12class@@UEAA@XZ; tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC(void)
0x180073ac2  mov     ebx, r15d
0x180073ac5  jmp     loc_180073C9F
0x180073aca  mov     [rbp+140h+arg_10], r15
0x180073ad1  mov     [rsp+240h+var_1F8], r15
0x180073ad6  mov     [rsp+240h+var_1F0], 0
0x180073adf  mov     [rsp+240h+var_1E8], r15d
0x180073ae4  mov     [rsp+240h+var_1E0], r15
0x180073ae9  mov     [rsp+240h+var_1D8], 0
0x180073af2  mov     [rsp+240h+var_1D0], r15b
0x180073af7  lea     rax, ??_7TCG_PCCLIENT_STORED_CERT@tpm12class@@6B@; const tpm12class::TCG_PCCLIENT_STORED_CERT::`vftable'
0x180073afe  mov     [rsp+240h+var_200], rax
0x180073b03  mov     dl, 1; unsigned __int8
0x180073b05  lea     rcx, [rsp+240h+var_200]; this
0x180073b0a  call    ?Clear@TCG_PCCLIENT_STORED_CERT@tpm12class@@MEAAJE@Z; tpm12class::TCG_PCCLIENT_STORED_CERT::Clear(uchar)
0x180073b0f  nop
0x180073b10  mov     qword ptr [rsp+240h+dwFlags], r15; unsigned int *
0x180073b15  xor     r9d, r9d; unsigned __int8 **
0x180073b18  mov     r8d, r14d; unsigned int
0x180073b1b  mov     rdx, rdi; unsigned __int8 *
0x180073b1e  lea     rcx, [rsp+240h+var_200]; this
0x180073b23  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x180073b28  mov     ebx, 10001h
0x180073b2d  test    eax, eax
0x180073b2f  js      short loc_180073B92
0x180073b31  mov     eax, 1001h
0x180073b36  cmp     [rsp+240h+var_1C8], ax
0x180073b3b  jnz     short loc_180073B92
0x180073b3d  cmp     [rsp+240h+var_1C6], r15b
0x180073b42  jnz     short loc_180073B92
0x180073b44  mov     eax, 1002h
0x180073b49  cmp     [rsp+240h+var_1C2], ax
0x180073b4e  jnz     short loc_180073B92
0x180073b50  movzx   r9d, [rsp+240h+var_1C4]; cbEncoded
0x180073b56  mov     [rsp+240h+pCreatePara], r15; pCreatePara
0x180073b5b  mov     [rsp+240h+dwFlags], r15d; dwFlags
0x180073b60  mov     r8, [rbp+140h+pbEncoded]; pbEncoded
0x180073b64  mov     edx, ebx; dwEncodingType
0x180073b66  mov     ecx, 1; dwContextType
0x180073b6b  call    cs:__imp_CertCreateContext
0x180073b72  nop     dword ptr [rax+rax+00h]
0x180073b77  mov     rdx, rax
0x180073b7a  lea     rcx, [rbp+140h+arg_10]
0x180073b81  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180073b86  mov     rdx, [rbp+140h+arg_10]
0x180073b8d  test    rdx, rdx
0x180073b90  jnz     short loc_180073BD0
0x180073b92  mov     [rsp+240h+pCreatePara], r15; pCreatePara
0x180073b97  mov     [rsp+240h+dwFlags], r15d; dwFlags
0x180073b9c  mov     r9d, r14d; cbEncoded
0x180073b9f  mov     r8, rdi; pbEncoded
0x180073ba2  mov     edx, ebx; dwEncodingType
0x180073ba4  mov     ecx, 1; dwContextType
0x180073ba9  call    cs:__imp_CertCreateContext
0x180073bb0  nop     dword ptr [rax+rax+00h]
0x180073bb5  mov     rdx, rax
0x180073bb8  lea     rcx, [rbp+140h+arg_10]
0x180073bbf  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180073bc4  mov     rdx, [rbp+140h+arg_10]
0x180073bcb  test    rdx, rdx
0x180073bce  jz      short loc_180073C46
0x180073bd0  mov     [rbp+140h+arg_10], r15
0x180073bd7  mov     rcx, r13
0x180073bda  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180073bdf  nop
0x180073be0  lea     rcx, [rsp+240h+var_200]; this
0x180073be5  call    ??1TCG_PCCLIENT_STORED_CERT@tpm12class@@UEAA@XZ; tpm12class::TCG_PCCLIENT_STORED_CERT::~TCG_PCCLIENT_STORED_CERT(void)
0x180073bea  nop
0x180073beb  lea     rcx, [rbp+140h+arg_10]
0x180073bf2  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180073bf7  nop
0x180073bf8  test    rdi, rdi
0x180073bfb  jz      short loc_180073C06
0x180073bfd  mov     rcx, rdi; void *
0x180073c00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073c05  nop
0x180073c06  xor     edx, edx
0x180073c08  lea     rcx, [rbp+140h+arg_18]
0x180073c0f  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180073c14  nop
0x180073c15  lea     rcx, [rbp+140h+var_130]; this
0x180073c19  call    ??1TPM_NV_DATA_PUBLIC@tpm12class@@UEAA@XZ; tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC(void)
0x180073c1e  nop
0x180073c1f  lea     rcx, [rbp+140h+var_1B0]; this
0x180073c23  call    ??1TPM_NV_ReadValue@tpm12class@@UEAA@XZ; tpm12class::TPM_NV_ReadValue::~TPM_NV_ReadValue(void)
0x180073c28  nop
0x180073c29  lea     rcx, [rbp+140h+var_B0]; this
0x180073c30  call    ??1TPM_GetCapability@tpm12class@@UEAA@XZ; tpm12class::TPM_GetCapability::~TPM_GetCapability(void)
0x180073c35  nop
0x180073c36  lea     rcx, [rbp+140h+var_D0]; this
0x180073c3a  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180073c3f  xor     eax, eax
0x180073c41  jmp     loc_180073D01
0x180073c46  mov     rcx, [rbp+148h]; this
0x180073c4d  lea     r8, aOnecoreBaseNgs_24; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180073c54  mov     edx, 94h; void *
0x180073c59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073c5e  mov     ebx, eax
0x180073c60  lea     rcx, [rsp+240h+var_200]; this
0x180073c65  call    ??1TCG_PCCLIENT_STORED_CERT@tpm12class@@UEAA@XZ; tpm12class::TCG_PCCLIENT_STORED_CERT::~TCG_PCCLIENT_STORED_CERT(void)
0x180073c6a  nop
0x180073c6b  lea     rcx, [rbp+140h+arg_10]
0x180073c72  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180073c77  nop
0x180073c78  test    rdi, rdi
0x180073c7b  jz      short loc_180073C86
0x180073c7d  mov     rcx, rdi; void *
0x180073c80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073c85  nop
0x180073c86  xor     edx, edx
0x180073c88  lea     rcx, [rbp+140h+arg_18]
0x180073c8f  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180073c94  nop
0x180073c95  lea     rcx, [rbp+140h+var_130]; this
0x180073c99  call    ??1TPM_NV_DATA_PUBLIC@tpm12class@@UEAA@XZ; tpm12class::TPM_NV_DATA_PUBLIC::~TPM_NV_DATA_PUBLIC(void)
0x180073c9e  nop
0x180073c9f  lea     rcx, [rbp+140h+var_1B0]; this
0x180073ca3  call    ??1TPM_NV_ReadValue@tpm12class@@UEAA@XZ; tpm12class::TPM_NV_ReadValue::~TPM_NV_ReadValue(void)
0x180073ca8  nop
0x180073ca9  lea     rcx, [rbp+140h+var_B0]; this
0x180073cb0  call    ??1TPM_GetCapability@tpm12class@@UEAA@XZ; tpm12class::TPM_GetCapability::~TPM_GetCapability(void)
0x180073cb5  nop
0x180073cb6  lea     rcx, [rbp+140h+var_D0]; this
  ... truncated ...
```
