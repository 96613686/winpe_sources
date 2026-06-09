# LoadAuthrootCTL

- ea: `0x1800ce658`
- end: `0x1800cea0b`
- name: `LoadAuthrootCTL`
- size: `947`
- prototype: `__int64 __fastcall(BYTE *pbCtlEncoded, DWORD cbCtlEncoded)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x1800cea14`
- `0x1800cec2c`

## callees

- `0x1800133fc`
- `0x18006a900`
- `0x1800cdfcc`
- `0x1800cdff8`
- `0x1800ce05c`
- `0x1800ce080`
- `0x1800ce0a4`
- `0x1800ce440`
- `0x1800ce658`
- `0x1800e7490`
- `0x1801051b4`
- `0x1801051d8`

## import_xrefs

- `WINTRUST!WTConvertCertCtxToChainInfo` at `0x1800ce8eb`
- `WINTRUST!WTConvertCertCtxToChainInfo` at `0x1800ce8eb`
- `CRYPT32!CryptMsgUpdate` at `0x1800ce6c5`
- `CRYPT32!CryptMsgUpdate` at `0x1800ce6c5`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1800ce69c`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1800ce69c`
- `CRYPT32!CertCreateCTLContext` at `0x1800ce943`
- `CRYPT32!CertCreateCTLContext` at `0x1800ce943`
- `CRYPT32!CryptVerifyMessageSignature` at `0x1800ce831`
- `CRYPT32!CryptVerifyMessageSignature` at `0x1800ce831`

## pseudocode

```c
__int64 __fastcall LoadAuthrootCTL(BYTE *pbCtlEncoded, DWORD cbCtlEncoded)
{
  HCRYPTMSG v4; // rax
  const char *v5; // r9
  void *v6; // rbx
  const char *v7; // r9
  int LastError; // edi
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v12; // ebx
  int pRecipientInfo; // [rsp+20h] [rbp-89h]
  _DWORD *v14; // [rsp+40h] [rbp-69h] BYREF
  void *Buf1; // [rsp+48h] [rbp-61h] BYREF
  void **p_Buf1; // [rsp+58h] [rbp-51h] BYREF
  PCCERT_CONTEXT v17; // [rsp+60h] [rbp-49h]
  char v18; // [rsp+68h] [rbp-41h]
  HCRYPTMSG v19; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v19 = v4;
  v6 = v4;
  if ( v4 )
  {
    if ( !CryptMsgUpdate(v4, pbCtlEncoded, cbCtlEncoded, 1) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5E,
                    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\certauthroot.cpp",
                    v7);
      goto LABEL_14;
    }
    v14 = 0;
    p_Buf1 = (void **)&v14;
    v17 = 0;
    v18 = 1;
    LastError = GetMessageParam(v6, 1u);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_Buf1);
    if ( LastError >= 0 )
    {
      if ( *v14 == 2 )
      {
        Buf1 = 0;
        p_Buf1 = &Buf1;
        v17 = 0;
        v18 = 1;
        LastError = GetMessageParam(v6, 4u);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_Buf1);
        if ( LastError >= 0 )
        {
          LastError = -2147024809;
          v10 = 110;
        }
        else
        {
          v10 = 109;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\certauthroot.cpp",
          (const char *)(unsigned int)LastError,
          pRecipientInfo);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset<unsigned char *>(
          &Buf1,
          0);
        goto LABEL_6;
      }
      LastError = -2147024809;
      v9 = 102;
    }
    else
    {
      v9 = 101;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\certauthroot.cpp",
      (const char *)(unsigned int)LastError,
      pRecipientInfo);
LABEL_6:
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset<unsigned char *>(
      &v14,
      0);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    return (unsigned int)LastError;
  }
  v12 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\certauthroot.cpp",
          v5);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  return v12;
}

```

## disassembly

```asm
0x1800ce658  mov     [rsp-8+arg_0], rbx
0x1800ce65d  mov     [rsp-8+arg_10], r8
0x1800ce662  push    rbp
0x1800ce663  push    rsi
0x1800ce664  push    rdi
0x1800ce665  push    r12
0x1800ce667  push    r13
0x1800ce669  push    r14
0x1800ce66b  push    r15
0x1800ce66d  lea     rbp, [rsp-27h]
0x1800ce672  sub     rsp, 0D0h
0x1800ce679  xor     esi, esi
0x1800ce67b  mov     r15d, edx
0x1800ce67e  mov     r12, rcx
0x1800ce681  mov     [rsp+100h+pStreamInfo], rsi; pStreamInfo
0x1800ce686  mov     r14d, 10001h
0x1800ce68c  mov     [rsp+100h+pRecipientInfo], rsi; int
0x1800ce691  mov     ecx, r14d; dwMsgEncodingType
0x1800ce694  xor     r9d, r9d; hCryptProv
0x1800ce697  xor     r8d, r8d; dwMsgType
0x1800ce69a  xor     edx, edx; dwFlags
0x1800ce69c  call    cs:__imp_CryptMsgOpenToDecode
0x1800ce6a3  nop     dword ptr [rax+rax+00h]
0x1800ce6a8  mov     [rbp+57h+var_90], rax
0x1800ce6ac  mov     rbx, rax
0x1800ce6af  test    rax, rax
0x1800ce6b2  jz      loc_1800CE9CD
0x1800ce6b8  lea     r9d, [rsi+1]; fFinal
0x1800ce6bc  mov     r8d, r15d; cbData
0x1800ce6bf  mov     rdx, r12; pbData
0x1800ce6c2  mov     rcx, rax; hCryptMsg
0x1800ce6c5  call    cs:__imp_CryptMsgUpdate
0x1800ce6cc  nop     dword ptr [rax+rax+00h]
0x1800ce6d1  test    eax, eax
0x1800ce6d3  jz      loc_1800CE9A9
0x1800ce6d9  lea     rax, [rbp+57h+var_C0]
0x1800ce6dd  mov     [rbp+57h+var_C0], rsi
0x1800ce6e1  lea     r9, [rbp+57h+arg_18]
0x1800ce6e5  mov     [rbp+57h+var_A8], rax
0x1800ce6e9  lea     r8, [rbp+57h+var_A0]
0x1800ce6ed  mov     [rbp+57h+arg_18], esi
0x1800ce6f0  lea     edx, [rsi+1]; dwParamType
0x1800ce6f3  mov     [rbp+57h+var_A0], rsi
0x1800ce6f7  mov     rcx, rbx; hCryptMsg
0x1800ce6fa  mov     [rbp+57h+var_98], 1
0x1800ce6fe  call    GetMessageParam
0x1800ce703  lea     rcx, [rbp+57h+var_A8]
0x1800ce707  mov     edi, eax
0x1800ce709  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800ce70e  test    edi, edi
0x1800ce710  jns     short loc_1800CE738
0x1800ce712  lea     edx, [rsi+65h]; void *
0x1800ce715  mov     rcx, [rbp+5Fh]; this
0x1800ce719  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce720  mov     r9d, edi; char *
0x1800ce723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce728  xor     edx, edx
0x1800ce72a  lea     rcx, [rbp+57h+var_C0]
0x1800ce72e  call    ??$reset@PEAE@?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset<uchar *>(uchar *)
0x1800ce733  jmp     loc_1800CE9C0
0x1800ce738  mov     rax, [rbp+57h+var_C0]
0x1800ce73c  cmp     dword ptr [rax], 2
0x1800ce73f  jz      short loc_1800CE74D
0x1800ce741  mov     edi, 80070057h
0x1800ce746  mov     edx, 66h ; 'f'
0x1800ce74b  jmp     short loc_1800CE715
0x1800ce74d  lea     rax, [rbp+57h+Buf1]
0x1800ce751  mov     [rbp+57h+Buf1], rsi
0x1800ce755  lea     r9, [rbp+57h+arg_18]
0x1800ce759  mov     [rbp+57h+var_A8], rax
0x1800ce75d  lea     r8, [rbp+57h+var_A0]
0x1800ce761  mov     [rbp+57h+arg_18], esi
0x1800ce764  mov     edx, 4; dwParamType
0x1800ce769  mov     [rbp+57h+var_A0], rsi
0x1800ce76d  mov     rcx, rbx; hCryptMsg
0x1800ce770  mov     [rbp+57h+var_98], 1
0x1800ce774  call    GetMessageParam
0x1800ce779  lea     rcx, [rbp+57h+var_A8]
0x1800ce77d  mov     edi, eax
0x1800ce77f  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800ce784  test    edi, edi
0x1800ce786  jns     short loc_1800CE7B0
0x1800ce788  mov     edx, 6Dh ; 'm'; void *
0x1800ce78d  mov     rcx, [rbp+5Fh]; this
0x1800ce791  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce798  mov     r9d, edi; char *
0x1800ce79b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce7a0  xor     edx, edx
0x1800ce7a2  lea     rcx, [rbp+57h+Buf1]
0x1800ce7a6  call    ??$reset@PEAE@?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset<uchar *>(uchar *)
0x1800ce7ab  jmp     loc_1800CE728
0x1800ce7b0  mov     r8d, 15h; Size
0x1800ce7b6  cmp     [rbp+57h+arg_18], r8d
0x1800ce7ba  jz      short loc_1800CE7C7
0x1800ce7bc  mov     edi, 80070057h
0x1800ce7c1  lea     edx, [r8+59h]
0x1800ce7c5  jmp     short loc_1800CE78D
0x1800ce7c7  mov     rcx, [rbp+57h+Buf1]; Buf1
0x1800ce7cb  lea     rdx, a136141311101; "1.3.6.1.4.1.311.10.1"
0x1800ce7d2  call    memcmp_0
0x1800ce7d7  test    eax, eax
0x1800ce7d9  jz      short loc_1800CE7E7
0x1800ce7db  mov     edi, 80070057h
0x1800ce7e0  mov     edx, 6Fh ; 'o'
0x1800ce7e5  jmp     short loc_1800CE78D
0x1800ce7e7  lea     rax, [rbp+57h+var_B0]
0x1800ce7eb  mov     [rbp+57h+pVerifyPara.pvGetArg], rsi
0x1800ce7ef  mov     [rbp+57h+var_A8], rax
0x1800ce7f3  lea     rcx, [rbp+57h+pVerifyPara]; pVerifyPara
0x1800ce7f7  lea     rax, [rbp+57h+var_A0]
0x1800ce7fb  mov     [rbp+57h+pVerifyPara.cbSize], 20h ; ' '
0x1800ce802  mov     [rsp+100h+ppSignerCert], rax; ppSignerCert
0x1800ce807  xorps   xmm0, xmm0
0x1800ce80a  mov     [rsp+100h+pStreamInfo], rsi; pcbDecoded
0x1800ce80f  mov     r9d, r15d; cbSignedBlob
0x1800ce812  mov     r8, r12; pbSignedBlob
0x1800ce815  mov     [rsp+100h+pRecipientInfo], rsi; int
0x1800ce81a  xor     edx, edx; dwSignerIndex
0x1800ce81c  mov     [rbp+57h+pVerifyPara.dwMsgAndCertEncodingType], r14d
0x1800ce820  movdqu  xmmword ptr [rbp+57h+pVerifyPara.hCryptProv], xmm0
0x1800ce825  mov     [rbp+57h+var_B0], rsi
0x1800ce829  mov     [rbp+57h+var_A0], rsi
0x1800ce82d  mov     [rbp+57h+var_98], 1
0x1800ce831  call    cs:__imp_CryptVerifyMessageSignature
0x1800ce838  nop     dword ptr [rax+rax+00h]
0x1800ce83d  lea     rcx, [rbp+57h+var_A8]
0x1800ce841  mov     edi, eax
0x1800ce843  call    ??1?$out_param_t@V?$unique_any_t@Ucert_context_t@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::cert_context_t>>::~out_param_t<wil::unique_any_t<wil::cert_context_t>>(void)
0x1800ce848  test    edi, edi
0x1800ce84a  jnz     short loc_1800CE86F
0x1800ce84c  mov     rcx, [rbp+5Fh]; this
0x1800ce850  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce857  lea     edx, [rdi+7Eh]; void *
0x1800ce85a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ce85f  mov     edi, eax
0x1800ce861  lea     rcx, [rbp+57h+var_B0]
0x1800ce865  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800ce86a  jmp     loc_1800CE7A0
0x1800ce86f  mov     rdi, [rbp+57h+var_B0]
0x1800ce873  mov     rax, [rdi+18h]
0x1800ce877  mov     r14d, [rax+0C0h]
0x1800ce87e  test    r14, r14
0x1800ce881  jz      short loc_1800CE8AD
0x1800ce883  mov     r13, [rax+0C8h]
0x1800ce88a  mov     rcx, rsi
0x1800ce88d  lea     rdx, a1361413111039; "1.3.6.1.4.1.311.10.3.9"
0x1800ce894  shl     rcx, 5
0x1800ce898  mov     rcx, [rcx+r13]; Str1
0x1800ce89c  call    strcmp_0
0x1800ce8a1  test    eax, eax
0x1800ce8a3  jnz     short loc_1800CE8CC
0x1800ce8a5  inc     rsi
0x1800ce8a8  cmp     rsi, r14
0x1800ce8ab  jb      short loc_1800CE88A
0x1800ce8ad  mov     edi, 800B0110h
0x1800ce8b2  mov     edx, 8Dh; void *
0x1800ce8b7  mov     r9d, edi; char *
0x1800ce8ba  mov     rcx, [rbp+5Fh]; this
0x1800ce8be  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce8c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce8ca  jmp     short loc_1800CE861
0x1800ce8cc  xorps   xmm0, xmm0
0x1800ce8cf  lea     r8, [rbp+57h+var_88]
0x1800ce8d3  xor     eax, eax
0x1800ce8d5  mov     rdx, rdi
0x1800ce8d8  mov     rcx, rbx
0x1800ce8db  mov     [rbp+57h+var_58], rax
0x1800ce8df  movups  [rbp+57h+var_88], xmm0
0x1800ce8e3  movups  [rbp+57h+var_78], xmm0
0x1800ce8e7  movups  [rbp+57h+var_68], xmm0
0x1800ce8eb  call    cs:__imp_WTConvertCertCtxToChainInfo
0x1800ce8f2  nop     dword ptr [rax+rax+00h]
0x1800ce8f7  mov     edi, eax
0x1800ce8f9  test    eax, eax
0x1800ce8fb  jns     short loc_1800CE907
0x1800ce8fd  mov     r9d, eax
0x1800ce900  mov     edx, 93h
0x1800ce905  jmp     short loc_1800CE8BA
0x1800ce907  cmp     dword ptr [rbp+57h+var_68+4], 6
0x1800ce90b  jz      short loc_1800CE938
0x1800ce90d  mov     rcx, [rbp+5Fh]; this
0x1800ce911  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce918  mov     edi, 800B0109h
0x1800ce91d  mov     edx, 99h; void *
0x1800ce922  mov     r9d, edi; char *
0x1800ce925  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce92a  lea     rcx, [rbp+57h+var_88]
0x1800ce92e  call    SIPolicyFreeSIChainInfo
0x1800ce933  jmp     loc_1800CE861
0x1800ce938  mov     r8d, r15d; cbCtlEncoded
0x1800ce93b  mov     rdx, r12; pbCtlEncoded
0x1800ce93e  mov     ecx, 10001h; dwMsgAndCertEncodingType
0x1800ce943  call    cs:__imp_CertCreateCTLContext
0x1800ce94a  nop     dword ptr [rax+rax+00h]
0x1800ce94f  mov     rcx, [rbp+57h+arg_10]
0x1800ce953  mov     [rcx], rax
0x1800ce956  test    rax, rax
0x1800ce959  jnz     short loc_1800CE974
0x1800ce95b  mov     rcx, [rbp+5Fh]; this
0x1800ce95f  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce966  mov     edx, 0A1h; void *
0x1800ce96b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ce970  mov     edi, eax
0x1800ce972  jmp     short loc_1800CE92A
0x1800ce974  lea     rcx, [rbp+57h+var_88]
0x1800ce978  call    SIPolicyFreeSIChainInfo
0x1800ce97d  lea     rcx, [rbp+57h+var_B0]
0x1800ce981  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800ce986  xor     edx, edx
0x1800ce988  lea     rcx, [rbp+57h+Buf1]
0x1800ce98c  call    ??$reset@PEAE@?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset<uchar *>(uchar *)
0x1800ce991  xor     edx, edx
0x1800ce993  lea     rcx, [rbp+57h+var_C0]
0x1800ce997  call    ??$reset@PEAE@?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset<uchar *>(uchar *)
0x1800ce99c  lea     rcx, [rbp+57h+var_90]
0x1800ce9a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CryptMsgClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ce9a5  xor     eax, eax
0x1800ce9a7  jmp     short loc_1800CE9EF
0x1800ce9a9  mov     rcx, [rbp+5Fh]; this
0x1800ce9ad  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce9b4  mov     edx, 5Eh ; '^'; void *
0x1800ce9b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ce9be  mov     edi, eax
0x1800ce9c0  lea     rcx, [rbp+57h+var_90]
0x1800ce9c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CryptMsgClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ce9c9  mov     eax, edi
0x1800ce9cb  jmp     short loc_1800CE9EF
0x1800ce9cd  mov     rcx, [rbp+5Fh]; this
0x1800ce9d1  lea     r8, aOnecorePrintsc_3; "onecore\\printscan\\appxpackaging\\cons"...
0x1800ce9d8  mov     edx, 5Dh ; ']'; void *
0x1800ce9dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ce9e2  lea     rcx, [rbp+57h+var_90]
0x1800ce9e6  mov     ebx, eax
0x1800ce9e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CryptMsgClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CryptMsgClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ce9ed  mov     eax, ebx
0x1800ce9ef  mov     rbx, [rsp+100h+arg_0]
0x1800ce9f7  add     rsp, 0D0h
0x1800ce9fe  pop     r15
0x1800cea00  pop     r14
0x1800cea02  pop     r13
0x1800cea04  pop     r12
0x1800cea06  pop     rdi
0x1800cea07  pop     rsi
0x1800cea08  pop     rbp
0x1800cea09  retn
```
