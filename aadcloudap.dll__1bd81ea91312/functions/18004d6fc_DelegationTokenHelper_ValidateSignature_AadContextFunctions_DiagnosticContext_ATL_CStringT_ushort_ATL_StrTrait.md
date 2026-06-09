# DelegationTokenHelper::ValidateSignature(AadContextFunctions *,DiagnosticContext &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,CSecureString const &)

- ea: `0x18004d6fc`
- end: `0x18004db16`
- name: `?ValidateSignature@DelegationTokenHelper@@CAJPEAVAadContextFunctions@@AEAVDiagnosticContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVCSecureString@@3@Z`
- size: `1050`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004be50`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180007bec`
- `0x18000943c`
- `0x18001d208`
- `0x18004d6fc`
- `0x180071e14`
- `0x180076758`
- `0x180076f14`
- `0x18007b0c0`
- `0x18007cdac`
- `0x18007e42c`
- `0x1800802e0`
- `0x180080750`
- `0x180080bb4`

## import_xrefs

- `ncrypt!NCryptImportKey` at `0x18004d9e6`
- `ncrypt!NCryptImportKey` at `0x18004d9e6`
- `ncrypt!NCryptVerifySignature` at `0x18004da42`
- `ncrypt!NCryptVerifySignature` at `0x18004da42`
- `ncrypt!NCryptFreeObject` at `0x18004dac1`
- `ncrypt!NCryptFreeObject` at `0x18004dad1`
- `ncrypt!NCryptFreeObject` at `0x18004dac1`
- `ncrypt!NCryptFreeObject` at `0x18004dad1`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004d989`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004d989`

## string_xrefs

- `0x18004d76a`: `DelegationTokenHelper::ValidateSignature`
- `0x18004d7fa`: `AAD Token Issuer`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DelegationTokenHelper::ValidateSignature(
        struct AadContextFunctions *this,
        __int64 a2,
        const WCHAR **a3,
        __int64 a4,
        __int64 a5)
{
  const WCHAR *v9; // rax
  SECURITY_STATUS v10; // eax
  const struct _CERT_CONTEXT *v11; // rdi
  __int64 v12; // r9
  unsigned int v13; // ebx
  NCRYPT_KEY_HANDLE *phKey; // [rsp+20h] [rbp-B1h]
  __int64 cbData; // [rsp+30h] [rbp-A1h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-81h] BYREF
  __int64 v18; // [rsp+58h] [rbp-79h] BYREF
  PBYTE pbHashValue[2]; // [rsp+60h] [rbp-71h] BYREF
  PBYTE pbSignature[2]; // [rsp+70h] [rbp-61h] BYREF
  PBYTE pbData[2]; // [rsp+80h] [rbp-51h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+90h] [rbp-41h] BYREF
  __int128 v23; // [rsp+98h] [rbp-39h] BYREF
  struct _CERT_CONTEXT *v24[4]; // [rsp+A8h] [rbp-29h] BYREF
  const char *v25[7]; // [rsp+C8h] [rbp-9h] BYREF
  int v26; // [rsp+130h] [rbp+5Fh] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+140h] [rbp+6Fh] BYREF

  v26 = 0;
  v23 = 0;
  *(_OWORD *)pbHashValue = 0;
  *(_OWORD *)pbSignature = 0;
  *(_OWORD *)pbData = 0;
  v18 = 0;
  CertificateContext::CertificateContext((CertificateContext *)v24);
  phProvider = 0;
  hKey = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v25,
    (int)"delegationtokenhelper.cpp",
    (int)"DelegationTokenHelper::ValidateSignature",
    (int)&v26);
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      Microsoft_Windows_AAD_Context,
      Aad_CloudAPPlugin_CACertHash_CorrelationID,
      *a3,
      *(_QWORD *)(a2 + 24));
  v9 = &base;
  if ( *a3 )
    v9 = *a3;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "delegationtokenhelper.cpp", 948, "CA cert hash", v9);
  v10 = CertificateStore::Open(&v18, 180224, L"AAD Token Issuer");
  v26 = v10;
  if ( v10 >= 0 )
  {
    v10 = CertificateStore::FindByKeyId(&v18, this, a3, v24);
    v26 = v10;
    if ( v10 >= 0 )
    {
      v11 = v24[0];
      if ( v24[0] )
      {
        LOBYTE(phKey) = 1;
        v10 = StringUtility::EncodeString(this, a4, &v23, 65001, (_DWORD)phKey);
        v26 = v10;
        if ( v10 >= 0 )
        {
          v10 = CryptoHelper::ComputeSha256Hash(this, (struct _AP_BLOB *)&v23, (struct _AP_BLOB *)pbHashValue);
          v26 = v10;
          if ( v10 >= 0 )
          {
            LOBYTE(v12) = 1;
            v10 = StringUtility::Base64UrlDecode(this, a5, pbSignature, v12);
            v26 = v10;
            if ( v10 >= 0 )
            {
              v10 = CryptoHelper::ExportCertificateNCryptPublicKey(this, v11, (struct _AP_BLOB *)pbData);
              v26 = v10;
              if ( v10 >= 0 )
              {
                v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
                v26 = v10;
                if ( v10 >= 0 )
                {
                  v10 = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &hKey, pbData[1], (DWORD)pbData[0], 0x40u);
                  v26 = v10;
                  if ( v10 >= 0 )
                  {
                    pPaddingInfo = L"SHA256";
                    v10 = NCryptVerifySignature(
                            hKey,
                            &pPaddingInfo,
                            pbHashValue[1],
                            (DWORD)pbHashValue[0],
                            pbSignature[1],
                            (DWORD)pbSignature[0],
                            0x42u);
                    v26 = v10;
                    if ( v10 >= 0 )
                      goto LABEL_26;
                    LODWORD(cbData) = 983;
                  }
                  else
                  {
                    LODWORD(cbData) = 969;
                  }
                }
                else
                {
                  LODWORD(cbData) = 967;
                }
              }
              else
              {
                LODWORD(cbData) = 965;
              }
            }
            else
            {
              LODWORD(cbData) = 963;
            }
          }
          else
          {
            LODWORD(cbData) = 961;
          }
        }
        else
        {
          LODWORD(cbData) = 959;
        }
      }
      else
      {
        v10 = -2147187367;
        v26 = -2147187367;
        LODWORD(cbData) = 956;
      }
    }
    else
    {
      LODWORD(cbData) = 952;
    }
  }
  else
  {
    LODWORD(cbData) = 950;
  }
  LODWORD(phKey) = v10;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phKey, "delegationtokenhelper.cpp", cbData, "HRESULT", &base);
LABEL_26:
  if ( this )
  {
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v23);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)pbHashValue);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)pbSignature);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)pbData);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( hKey )
    NCryptFreeObject(hKey);
  v13 = v26;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v25);
  CertificateContext::~CertificateContext((CertificateContext *)v24);
  CertificateStore::Close((CertificateStore *)&v18);
  return v13;
}

```

## disassembly

```asm
0x18004d6fc  mov     [rsp-8+arg_8], rbx
0x18004d701  mov     [rsp-8+arg_18], rsi
0x18004d706  push    rbp
0x18004d707  push    rdi
0x18004d708  push    r12
0x18004d70a  push    r13
0x18004d70c  push    r14
0x18004d70e  lea     rbp, [rsp-2Fh]
0x18004d713  sub     rsp, 100h
0x18004d71a  mov     r14, r9
0x18004d71d  mov     rdi, r8
0x18004d720  mov     rsi, rdx
0x18004d723  mov     rbx, rcx
0x18004d726  mov     [rbp+4Fh+arg_0], 0
0x18004d72d  xorps   xmm0, xmm0
0x18004d730  movups  [rbp+4Fh+var_88], xmm0
0x18004d734  xorps   xmm1, xmm1
0x18004d737  movups  xmmword ptr [rbp+4Fh+pbHashValue], xmm1
0x18004d73b  movups  xmmword ptr [rbp+4Fh+pbSignature], xmm0
0x18004d73f  movups  xmmword ptr [rbp+4Fh+var_A0], xmm1
0x18004d743  mov     [rbp+4Fh+var_C8], 0
0x18004d74b  lea     rcx, [rbp+4Fh+var_78]; this
0x18004d74f  call    ??0CertificateContext@@QEAA@XZ; CertificateContext::CertificateContext(void)
0x18004d754  nop
0x18004d755  mov     [rbp+4Fh+phProvider], 0
0x18004d75d  mov     [rsp+120h+hKey], 0
0x18004d766  lea     r9, [rbp+4Fh+arg_0]
0x18004d76a  lea     r8, aDelegationtoke_6; "DelegationTokenHelper::ValidateSignatur"...
0x18004d771  lea     r12, aOnecoreuapDsEx_26+21h; "delegationtokenhelper.cpp"
0x18004d778  mov     rdx, r12
0x18004d77b  lea     rcx, [rbp+4Fh+var_58]
0x18004d77f  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004d784  nop
0x18004d785  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18004d78c  jz      short loc_18004D7A8
0x18004d78e  mov     r9, [rsi+18h]
0x18004d792  mov     r8, [rdi]
0x18004d795  lea     rdx, Aad_CloudAPPlugin_CACertHash_CorrelationID
0x18004d79c  lea     rcx, Microsoft_Windows_AAD_Context
0x18004d7a3  call    McTemplateU0zz_EventWriteTransfer
0x18004d7a8  lea     r13, base
0x18004d7af  mov     rax, r13
0x18004d7b2  cmp     qword ptr [rdi], 0
0x18004d7b6  cmovnz  rax, [rdi]
0x18004d7ba  mov     [rsp+120h+var_E0], rax
0x18004d7bf  lea     rax, aCaCertHash; "CA cert hash"
0x18004d7c6  mov     qword ptr [rsp+120h+dwFlags], rax
0x18004d7cb  mov     dword ptr [rsp+120h+cbData], 3B4h
0x18004d7d3  mov     [rsp+120h+pbData], r12
0x18004d7d8  mov     [rsp+120h+phKey], 0
0x18004d7e1  mov     ecx, 4
0x18004d7e6  mov     r9d, ecx
0x18004d7e9  lea     rsi, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004d7f0  mov     r8, rsi
0x18004d7f3  xor     edx, edx
0x18004d7f5  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004d7fa  lea     r8, aAadTokenIssuer; "AAD Token Issuer"
0x18004d801  mov     edx, 2C000h
0x18004d806  lea     rcx, [rbp+4Fh+var_C8]
0x18004d80a  call    ?Open@CertificateStore@@QEAAJW4StoreProviderTypes@1@PEBG@Z; CertificateStore::Open(CertificateStore::StoreProviderTypes,ushort const *)
0x18004d80f  mov     [rbp+4Fh+arg_0], eax
0x18004d812  test    eax, eax
0x18004d814  jns     short loc_18004D834
0x18004d816  mov     [rsp+120h+var_E0], r13
0x18004d81b  lea     rcx, aHresult; "HRESULT"
0x18004d822  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d827  mov     dword ptr [rsp+120h+cbData], 3B6h
0x18004d82f  jmp     loc_18004DA68
0x18004d834  lea     r9, [rbp+4Fh+var_78]
0x18004d838  mov     r8, rdi
0x18004d83b  mov     rdx, rbx
0x18004d83e  lea     rcx, [rbp+4Fh+var_C8]
0x18004d842  call    ?FindByKeyId@CertificateStore@@QEAAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEBU_CERT_CONTEXT@@@Z; CertificateStore::FindByKeyId(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_CERT_CONTEXT const * *)
0x18004d847  mov     [rbp+4Fh+arg_0], eax
0x18004d84a  test    eax, eax
0x18004d84c  jns     short loc_18004D86C
0x18004d84e  mov     [rsp+120h+var_E0], r13
0x18004d853  lea     rcx, aHresult; "HRESULT"
0x18004d85a  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d85f  mov     dword ptr [rsp+120h+cbData], 3B8h
0x18004d867  jmp     loc_18004DA68
0x18004d86c  mov     rdi, [rbp+4Fh+var_78]
0x18004d870  test    rdi, rdi
0x18004d873  jnz     short loc_18004D89B
0x18004d875  mov     eax, 80048559h
0x18004d87a  mov     [rbp+4Fh+arg_0], eax
0x18004d87d  mov     [rsp+120h+var_E0], r13
0x18004d882  lea     rcx, aHresult; "HRESULT"
0x18004d889  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d88e  mov     dword ptr [rsp+120h+cbData], 3BCh
0x18004d896  jmp     loc_18004DA68
0x18004d89b  mov     byte ptr [rsp+120h+phKey], 1
0x18004d8a0  mov     r9d, 0FDE9h
0x18004d8a6  lea     r8, [rbp+4Fh+var_88]
0x18004d8aa  mov     rdx, r14
0x18004d8ad  mov     rcx, rbx
0x18004d8b0  call    ?EncodeString@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@I_N@Z; StringUtility::EncodeString(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,uint,bool)
0x18004d8b5  mov     [rbp+4Fh+arg_0], eax
0x18004d8b8  test    eax, eax
0x18004d8ba  jns     short loc_18004D8DA
0x18004d8bc  mov     [rsp+120h+var_E0], r13
0x18004d8c1  lea     rcx, aHresult; "HRESULT"
0x18004d8c8  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d8cd  mov     dword ptr [rsp+120h+cbData], 3BFh
0x18004d8d5  jmp     loc_18004DA68
0x18004d8da  lea     r8, [rbp+4Fh+pbHashValue]; struct _AP_BLOB *
0x18004d8de  lea     rdx, [rbp+4Fh+var_88]; struct _AP_BLOB *
0x18004d8e2  mov     rcx, rbx; this
0x18004d8e5  call    ?ComputeSha256Hash@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@1@Z; CryptoHelper::ComputeSha256Hash(AadContextFunctions *,_AP_BLOB *,_AP_BLOB *)
0x18004d8ea  mov     [rbp+4Fh+arg_0], eax
0x18004d8ed  test    eax, eax
0x18004d8ef  jns     short loc_18004D90F
0x18004d8f1  mov     [rsp+120h+var_E0], r13
0x18004d8f6  lea     rcx, aHresult; "HRESULT"
0x18004d8fd  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d902  mov     dword ptr [rsp+120h+cbData], 3C1h
0x18004d90a  jmp     loc_18004DA68
0x18004d90f  mov     r9b, 1
0x18004d912  lea     r8, [rbp+4Fh+pbSignature]
0x18004d916  mov     rdx, [rbp+4Fh+arg_20]
0x18004d91a  mov     rcx, rbx
0x18004d91d  call    ?Base64UrlDecode@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N@Z; StringUtility::Base64UrlDecode(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool)
0x18004d922  mov     [rbp+4Fh+arg_0], eax
0x18004d925  test    eax, eax
0x18004d927  jns     short loc_18004D947
0x18004d929  mov     [rsp+120h+var_E0], r13
0x18004d92e  lea     rcx, aHresult; "HRESULT"
0x18004d935  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d93a  mov     dword ptr [rsp+120h+cbData], 3C3h
0x18004d942  jmp     loc_18004DA68
0x18004d947  lea     r8, [rbp+4Fh+var_A0]; struct _AP_BLOB *
0x18004d94b  mov     rdx, rdi; struct _CERT_CONTEXT *
0x18004d94e  mov     rcx, rbx; this
0x18004d951  call    ?ExportCertificateNCryptPublicKey@CryptoHelper@@SAJPEAVAadContextFunctions@@PEBU_CERT_CONTEXT@@PEAU_AP_BLOB@@@Z; CryptoHelper::ExportCertificateNCryptPublicKey(AadContextFunctions *,_CERT_CONTEXT const *,_AP_BLOB *)
0x18004d956  mov     [rbp+4Fh+arg_0], eax
0x18004d959  test    eax, eax
0x18004d95b  jns     short loc_18004D97B
0x18004d95d  mov     [rsp+120h+var_E0], r13
0x18004d962  lea     rcx, aHresult; "HRESULT"
0x18004d969  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d96e  mov     dword ptr [rsp+120h+cbData], 3C5h
0x18004d976  jmp     loc_18004DA68
0x18004d97b  xor     r8d, r8d; dwFlags
0x18004d97e  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18004d985  lea     rcx, [rbp+4Fh+phProvider]; phProvider
0x18004d989  call    cs:__imp_NCryptOpenStorageProvider
0x18004d98f  mov     [rbp+4Fh+arg_0], eax
0x18004d992  xor     edx, edx; hImportKey
0x18004d994  test    eax, eax
0x18004d996  jns     short loc_18004D9B6
0x18004d998  mov     [rsp+120h+var_E0], r13
0x18004d99d  lea     rcx, aHresult; "HRESULT"
0x18004d9a4  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004d9a9  mov     dword ptr [rsp+120h+cbData], 3C7h
0x18004d9b1  jmp     loc_18004DA6A
0x18004d9b6  mov     [rsp+120h+dwFlags], 40h ; '@'; dwFlags
0x18004d9be  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x18004d9c1  mov     dword ptr [rsp+120h+cbData], eax; cbData
0x18004d9c5  mov     rax, [rbp+4Fh+var_A0+8]
0x18004d9c9  mov     [rsp+120h+pbData], rax; pbData
0x18004d9ce  lea     rax, [rsp+120h+hKey]
0x18004d9d3  mov     [rsp+120h+phKey], rax; phKey
0x18004d9d8  xor     r9d, r9d; pParameterList
0x18004d9db  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x18004d9e2  mov     rcx, [rbp+4Fh+phProvider]; hProvider
0x18004d9e6  call    cs:__imp_NCryptImportKey
0x18004d9ec  mov     [rbp+4Fh+arg_0], eax
0x18004d9ef  test    eax, eax
0x18004d9f1  jns     short loc_18004DA0E
0x18004d9f3  mov     [rsp+120h+var_E0], r13
0x18004d9f8  lea     rcx, aHresult; "HRESULT"
0x18004d9ff  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004da04  mov     dword ptr [rsp+120h+cbData], 3C9h
0x18004da0c  jmp     short loc_18004DA68
0x18004da0e  lea     rax, aSha256; "SHA256"
0x18004da15  mov     [rbp+4Fh+pPaddingInfo], rax
0x18004da19  mov     dword ptr [rsp+120h+cbData], 42h ; 'B'; dwFlags
0x18004da21  mov     eax, dword ptr [rbp+4Fh+pbSignature]
0x18004da24  mov     dword ptr [rsp+120h+pbData], eax; cbSignature
0x18004da28  mov     rax, [rbp+4Fh+pbSignature+8]
0x18004da2c  mov     [rsp+120h+phKey], rax; pbSignature
0x18004da31  mov     r9d, dword ptr [rbp+4Fh+pbHashValue]; cbHashValue
0x18004da35  mov     r8, [rbp+4Fh+pbHashValue+8]; pbHashValue
0x18004da39  lea     rdx, [rbp+4Fh+pPaddingInfo]; pPaddingInfo
0x18004da3d  mov     rcx, [rsp+120h+hKey]; hKey
0x18004da42  call    cs:__imp_NCryptVerifySignature
0x18004da48  mov     [rbp+4Fh+arg_0], eax
0x18004da4b  test    eax, eax
0x18004da4d  jns     short loc_18004DA83
0x18004da4f  mov     [rsp+120h+var_E0], r13
0x18004da54  lea     rcx, aHresult; "HRESULT"
0x18004da5b  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18004da60  mov     dword ptr [rsp+120h+cbData], 3D7h
0x18004da68  xor     edx, edx
0x18004da6a  mov     [rsp+120h+pbData], r12
0x18004da6f  mov     ecx, 2
0x18004da74  mov     dword ptr [rsp+120h+phKey], eax
0x18004da78  mov     r9d, ecx
0x18004da7b  mov     r8, rsi
0x18004da7e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004da83  test    rbx, rbx
0x18004da86  jz      short loc_18004DAB8
0x18004da88  lea     rdx, [rbp+4Fh+var_88]; struct _AP_BLOB *
0x18004da8c  mov     rcx, rbx; this
0x18004da8f  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18004da94  lea     rdx, [rbp+4Fh+pbHashValue]; struct _AP_BLOB *
0x18004da98  mov     rcx, rbx; this
0x18004da9b  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18004daa0  lea     rdx, [rbp+4Fh+pbSignature]; struct _AP_BLOB *
0x18004daa4  mov     rcx, rbx; this
0x18004daa7  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18004daac  lea     rdx, [rbp+4Fh+var_A0]; struct _AP_BLOB *
0x18004dab0  mov     rcx, rbx; this
0x18004dab3  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18004dab8  mov     rcx, [rbp+4Fh+phProvider]; hObject
0x18004dabc  test    rcx, rcx
0x18004dabf  jz      short loc_18004DAC7
0x18004dac1  call    cs:__imp_NCryptFreeObject
0x18004dac7  mov     rcx, [rsp+120h+hKey]; hObject
0x18004dacc  test    rcx, rcx
0x18004dacf  jz      short loc_18004DAD7
0x18004dad1  call    cs:__imp_NCryptFreeObject
0x18004dad7  mov     ebx, [rbp+4Fh+arg_0]
0x18004dada  lea     rcx, [rbp+4Fh+var_58]
0x18004dade  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004dae3  nop
0x18004dae4  lea     rcx, [rbp+4Fh+var_78]; this
0x18004dae8  call    ??1CertificateContext@@QEAA@XZ; CertificateContext::~CertificateContext(void)
0x18004daed  nop
0x18004daee  lea     rcx, [rbp+4Fh+var_C8]; this
0x18004daf2  call    ?Close@CertificateStore@@QEAAJXZ; CertificateStore::Close(void)
0x18004daf7  nop
0x18004daf8  mov     eax, ebx
0x18004dafa  lea     r11, [rsp+120h+var_20]
0x18004db02  mov     rbx, [r11+38h]
0x18004db06  mov     rsi, [r11+48h]
0x18004db0a  mov     rsp, r11
0x18004db0d  pop     r14
0x18004db0f  pop     r13
0x18004db11  pop     r12
0x18004db13  pop     rdi
0x18004db14  pop     rbp
0x18004db15  retn
```
