# CryptoHelper::SignDataWithCert(AadContextFunctions *,_CERT_CONTEXT const *,bool,_AP_BLOB *,_AP_BLOB *)

- ea: `0x18007fca8`
- end: `0x1800801a5`
- name: `?SignDataWithCert@CryptoHelper@@SAJPEAVAadContextFunctions@@PEBU_CERT_CONTEXT@@_NPEAU_AP_BLOB@@3@Z`
- size: `1277`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, PCCERT_CONTEXT pCert@<rdx>, bool@<r8b>, struct _AP_BLOB *@<r9>, struct _AP_BLOB *)`
- caller_count: `6`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180021eb8`
- `0x1800225f4`
- `0x180059b74`
- `0x18005ef28`
- `0x18006044c`
- `0x18006abd8`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180009418`
- `0x1800256d0`
- `0x180071e14`
- `0x180078b18`
- `0x18007b0c0`
- `0x18007b0e4`
- `0x18007f9c4`
- `0x18007fca8`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fe46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007feec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ff40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ffa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fe46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007feec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ff40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ffa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080062`
- `ncrypt!NCryptFreeObject` at `0x180080168`
- `ncrypt!NCryptFreeObject` at `0x180080168`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007fd5a`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007fd5a`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18007fe36`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18007fe36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007ff36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007ff36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x18007ff98`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180080058`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x18007ff98`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x180080058`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18008014d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18008014d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007fee2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007fee2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180080172`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180080172`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CryptoHelper::SignDataWithCert(
        struct AadContextFunctions *a1,
        PCCERT_CONTEXT pCert,
        char a3,
        struct _AP_BLOB *a4,
        struct _AP_BLOB *a5)
{
  struct _AP_BLOB *v9; // rsi
  const struct _CERT_CONTEXT *v10; // rax
  int v11; // eax
  signed int LastError; // eax
  __int64 v13; // rbx
  BYTE *v14; // r14
  DWORD v15; // r9d
  DWORD v16; // r8d
  BYTE v17; // cl
  unsigned int v18; // ebx
  DWORD *pdwKeySpec; // [rsp+20h] [rbp-B1h]
  int v21; // [rsp+30h] [rbp-A1h]
  int v22; // [rsp+30h] [rbp-A1h]
  DWORD pdwSigLen; // [rsp+50h] [rbp-81h] BYREF
  DWORD dwKeySpec; // [rsp+54h] [rbp-7Dh] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+58h] [rbp-79h] BYREF
  HCRYPTHASH phHash; // [rsp+60h] [rbp-71h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+68h] [rbp-69h] BYREF
  BYTE *v28; // [rsp+70h] [rbp-61h] BYREF
  __int64 v29; // [rsp+78h] [rbp-59h]
  struct AadContextFunctions *v30; // [rsp+80h] [rbp-51h]
  _BYTE v31[24]; // [rsp+88h] [rbp-49h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+A0h] [rbp-31h]
  const char *v33[15]; // [rsp+A8h] [rbp-29h] BYREF
  int v34; // [rsp+130h] [rbp+5Fh] BYREF

  v34 = 0;
  phCryptProvOrNCryptKey = 0;
  dwKeySpec = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  phHash = 0;
  v28 = 0;
  v30 = a1;
  v29 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v33,
    (int)"crypto.cpp",
    (int)"CryptoHelper::SignDataWithCert",
    (int)&v34);
  if ( !a1 || !pCert || (v9 = a5) == 0 || !a4 || !IsApBlobDefined(a4) )
  {
    LastError = -2147024809;
    v22 = 549;
    goto LABEL_47;
  }
  *(_QWORD *)v9 = 0;
  *((_QWORD *)v9 + 1) = 0;
  if ( a3 )
  {
    v10 = CertDuplicateCertificateContext(pCert);
    CertificateContext::CertificateContext((CertificateContext *)v31, v10);
    v11 = CertificateContext::AcquirePrivateKey((CertificateContext *)v31, a1);
    v34 = v11;
    if ( v11 >= 0 )
    {
      v11 = CryptoHelper::SignData(a1, hKey, a4, v9);
      v34 = v11;
      if ( v11 >= 0 )
        goto LABEL_10;
      v21 = 560;
    }
    else
    {
      v21 = 559;
    }
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v11, "crypto.cpp", v21, "HRESULT", &base);
LABEL_10:
    CertificateContext::~CertificateContext((CertificateContext *)v31);
    goto LABEL_49;
  }
  pdwSigLen = 0;
  dwKeySpec = 2;
  if ( !CryptAcquireCertificatePrivateKey(
          pCert,
          0x20045u,
          0,
          &phCryptProvOrNCryptKey,
          &dwKeySpec,
          &pfCallerFreeProvOrNCryptKey) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v34 = LastError;
    if ( LastError < 0 )
    {
      v22 = 574;
LABEL_48:
      LODWORD(pdwKeySpec) = LastError;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pdwKeySpec, "crypto.cpp", v22, "HRESULT", &base);
      goto LABEL_49;
    }
  }
  if ( dwKeySpec == -1 )
  {
    LastError = CryptoHelper::SignData(a1, phCryptProvOrNCryptKey, a4, v9);
    v34 = LastError;
    if ( LastError >= 0 )
      goto LABEL_49;
    v22 = 579;
    goto LABEL_48;
  }
  if ( !CryptCreateHash(phCryptProvOrNCryptKey, 0x800Cu, 0, 0, &phHash) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v34 = LastError;
    if ( LastError < 0 )
    {
      v22 = 587;
      goto LABEL_48;
    }
  }
  if ( !CryptHashData(phHash, *((const BYTE **)a4 + 1), *(_DWORD *)a4, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v34 = LastError;
    if ( LastError < 0 )
    {
      v22 = 593;
      goto LABEL_48;
    }
  }
  if ( !CryptSignHashW(phHash, dwKeySpec, 0, 0, 0, &pdwSigLen) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v34 = LastError;
    if ( LastError < 0 )
    {
      v22 = 599;
      goto LABEL_48;
    }
  }
  v13 = pdwSigLen;
  v14 = (BYTE *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)a1 + 8LL))(
                  a1,
                  64,
                  pdwSigLen);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v28);
  v28 = v14;
  v29 = v13;
  if ( !v14 )
  {
    LastError = -2147024882;
    v22 = 605;
LABEL_47:
    v34 = LastError;
    goto LABEL_48;
  }
  if ( !CryptSignHashW(phHash, dwKeySpec, 0, 0, v14, &pdwSigLen) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v34 = LastError;
    if ( LastError < 0 )
    {
      v22 = 610;
      goto LABEL_48;
    }
  }
  v15 = 0;
  v16 = pdwSigLen;
  if ( (pdwSigLen & 0xFFFFFFFE) != 0 )
  {
    do
    {
      v17 = v14[v15];
      v14[v15] = v14[v16 - (unsigned __int64)v15 - 1];
      v14[pdwSigLen - (unsigned __int64)v15++ - 1] = v17;
      v16 = pdwSigLen;
    }
    while ( v15 < pdwSigLen >> 1 );
  }
  *(_DWORD *)v9 = v16;
  *((_DWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 1) = v14;
  v28 = 0;
  v29 = 0;
LABEL_49:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( pfCallerFreeProvOrNCryptKey && phCryptProvOrNCryptKey )
  {
    if ( dwKeySpec == -1 )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  }
  v18 = v34;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v33);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v28);
  return v18;
}

```

## disassembly

```asm
0x18007fca8  push    rbp
0x18007fcaa  push    rbx
0x18007fcab  push    rsi
0x18007fcac  push    rdi
0x18007fcad  push    r12
0x18007fcaf  push    r13
0x18007fcb1  push    r14
0x18007fcb3  push    r15
0x18007fcb5  lea     rbp, [rsp-17h]
0x18007fcba  sub     rsp, 0E8h
0x18007fcc1  mov     rbx, r9
0x18007fcc4  mov     dil, r8b
0x18007fcc7  mov     r14, rdx
0x18007fcca  mov     r15, rcx
0x18007fccd  xor     r12d, r12d
0x18007fcd0  mov     [rbp+4Fh+arg_0], r12d
0x18007fcd4  mov     [rbp+4Fh+phCryptProvOrNCryptKey], r12
0x18007fcd8  mov     [rbp+4Fh+dwKeySpec], r12d
0x18007fcdc  mov     [rbp+4Fh+var_C8], r12d
0x18007fce0  mov     [rbp+4Fh+phHash], r12
0x18007fce4  mov     [rbp+4Fh+var_B0], r12
0x18007fce8  mov     [rbp+4Fh+var_A0], rcx
0x18007fcec  mov     [rbp+4Fh+var_A8], r12
0x18007fcf0  lea     r9, [rbp+4Fh+arg_0]
0x18007fcf4  lea     r8, aCryptohelperSi; "CryptoHelper::SignDataWithCert"
0x18007fcfb  lea     r13, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007fd02  mov     rdx, r13
0x18007fd05  lea     rcx, [rbp+4Fh+var_78]
0x18007fd09  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18007fd0e  nop
0x18007fd0f  test    r15, r15
0x18007fd12  jz      loc_1800800FB
0x18007fd18  test    r14, r14
0x18007fd1b  jz      loc_1800800FB
0x18007fd21  mov     rsi, [rbp+4Fh+arg_20]
0x18007fd25  test    rsi, rsi
0x18007fd28  jz      loc_1800800FB
0x18007fd2e  test    rbx, rbx
0x18007fd31  jz      loc_1800800FB
0x18007fd37  mov     rcx, rbx; struct _AP_BLOB *
0x18007fd3a  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007fd3f  test    al, al
0x18007fd41  jz      loc_1800800FB
0x18007fd47  mov     [rsi], r12
0x18007fd4a  mov     [rsi+8], r12
0x18007fd4e  mov     rcx, r14; pCert
0x18007fd51  test    dil, dil
0x18007fd54  jz      loc_18007FE0B
0x18007fd5a  call    cs:__imp_CertDuplicateCertificateContext
0x18007fd60  mov     rdx, rax; struct _CERT_CONTEXT *
0x18007fd63  lea     rcx, [rbp+4Fh+var_98]; this
0x18007fd67  call    ??0CertificateContext@@QEAA@PEBU_CERT_CONTEXT@@@Z; CertificateContext::CertificateContext(_CERT_CONTEXT const *)
0x18007fd6c  nop
0x18007fd6d  mov     rdx, r15; struct AadContextFunctions *
0x18007fd70  lea     rcx, [rbp+4Fh+var_98]; this
0x18007fd74  call    ?AcquirePrivateKey@CertificateContext@@QEAAJPEAVAadContextFunctions@@@Z; CertificateContext::AcquirePrivateKey(AadContextFunctions *)
0x18007fd79  mov     [rbp+4Fh+arg_0], eax
0x18007fd7c  test    eax, eax
0x18007fd7e  jns     short loc_18007FDD0
0x18007fd80  lea     rcx, base
0x18007fd87  mov     [rsp+120h+var_E0], rcx
0x18007fd8c  lea     rcx, aHresult; "HRESULT"
0x18007fd93  mov     [rsp+120h+var_E8], rcx
0x18007fd98  mov     [rsp+120h+var_F0], 22Fh
0x18007fda0  mov     [rsp+120h+pfCallerFreeProvOrNCryptKey], r13
0x18007fda5  mov     dword ptr [rsp+120h+pdwKeySpec], eax
0x18007fda9  mov     edi, 2
0x18007fdae  mov     r9d, edi
0x18007fdb1  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007fdb8  xor     edx, edx
0x18007fdba  mov     ecx, edi
0x18007fdbc  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007fdc1  nop
0x18007fdc2  lea     rcx, [rbp+4Fh+var_98]; this
0x18007fdc6  call    ??1CertificateContext@@QEAA@XZ; CertificateContext::~CertificateContext(void)
0x18007fdcb  jmp     loc_180080144
0x18007fdd0  mov     r9, rsi; struct _AP_BLOB *
0x18007fdd3  mov     r8, rbx; struct _AP_BLOB *
0x18007fdd6  mov     rdx, [rbp+4Fh+hKey]; hKey
0x18007fdda  mov     rcx, r15; this
0x18007fddd  call    ?SignData@CryptoHelper@@SAJPEAVAadContextFunctions@@_KPEAU_AP_BLOB@@2@Z; CryptoHelper::SignData(AadContextFunctions *,unsigned __int64,_AP_BLOB *,_AP_BLOB *)
0x18007fde2  mov     [rbp+4Fh+arg_0], eax
0x18007fde5  test    eax, eax
0x18007fde7  jns     short loc_18007FDC2
0x18007fde9  lea     rcx, base
0x18007fdf0  mov     [rsp+120h+var_E0], rcx
0x18007fdf5  lea     rcx, aHresult; "HRESULT"
0x18007fdfc  mov     [rsp+120h+var_E8], rcx
0x18007fe01  mov     [rsp+120h+var_F0], 230h
0x18007fe09  jmp     short loc_18007FDA0
0x18007fe0b  mov     [rsp+120h+pdwSigLen], r12d
0x18007fe10  mov     edi, 2
0x18007fe15  mov     [rbp+4Fh+dwKeySpec], edi
0x18007fe18  lea     rax, [rbp+4Fh+var_C8]
0x18007fe1c  mov     [rsp+120h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x18007fe21  lea     rax, [rbp+4Fh+dwKeySpec]
0x18007fe25  mov     [rsp+120h+pdwKeySpec], rax; pdwKeySpec
0x18007fe2a  lea     r9, [rbp+4Fh+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18007fe2e  xor     r8d, r8d; pvParameters
0x18007fe31  mov     edx, 20045h; dwFlags
0x18007fe36  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x18007fe3c  mov     r14d, 80070000h
0x18007fe42  test    eax, eax
0x18007fe44  jnz     short loc_18007FE82
0x18007fe46  call    cs:__imp_GetLastError
0x18007fe4c  test    eax, eax
0x18007fe4e  jle     short loc_18007FE56
0x18007fe50  movzx   eax, ax
0x18007fe53  or      eax, r14d
0x18007fe56  mov     [rbp+4Fh+arg_0], eax
0x18007fe59  test    eax, eax
0x18007fe5b  jns     short loc_18007FE82
0x18007fe5d  lea     rcx, base
0x18007fe64  mov     [rsp+120h+var_E0], rcx
0x18007fe69  lea     rcx, aHresult; "HRESULT"
0x18007fe70  mov     [rsp+120h+var_E8], rcx
0x18007fe75  mov     [rsp+120h+var_F0], 23Eh
0x18007fe7d  jmp     loc_180080128
0x18007fe82  cmp     [rbp+4Fh+dwKeySpec], 0FFFFFFFFh
0x18007fe86  jnz     short loc_18007FECA
0x18007fe88  mov     r9, rsi; struct _AP_BLOB *
0x18007fe8b  mov     r8, rbx; struct _AP_BLOB *
0x18007fe8e  mov     rdx, [rbp+4Fh+phCryptProvOrNCryptKey]; hKey
0x18007fe92  mov     rcx, r15; this
0x18007fe95  call    ?SignData@CryptoHelper@@SAJPEAVAadContextFunctions@@_KPEAU_AP_BLOB@@2@Z; CryptoHelper::SignData(AadContextFunctions *,unsigned __int64,_AP_BLOB *,_AP_BLOB *)
0x18007fe9a  mov     [rbp+4Fh+arg_0], eax
0x18007fe9d  test    eax, eax
0x18007fe9f  jns     loc_180080144
0x18007fea5  lea     rcx, base
0x18007feac  mov     [rsp+120h+var_E0], rcx
0x18007feb1  lea     rcx, aHresult; "HRESULT"
0x18007feb8  mov     [rsp+120h+var_E8], rcx
0x18007febd  mov     [rsp+120h+var_F0], 243h
0x18007fec5  jmp     loc_180080128
0x18007feca  lea     rax, [rbp+4Fh+phHash]
0x18007fece  mov     [rsp+120h+pdwKeySpec], rax; phHash
0x18007fed3  xor     r9d, r9d; dwFlags
0x18007fed6  xor     r8d, r8d; hKey
0x18007fed9  mov     edx, 800Ch; Algid
0x18007fede  mov     rcx, [rbp+4Fh+phCryptProvOrNCryptKey]; hProv
0x18007fee2  call    cs:__imp_CryptCreateHash
0x18007fee8  test    eax, eax
0x18007feea  jnz     short loc_18007FF28
0x18007feec  call    cs:__imp_GetLastError
0x18007fef2  test    eax, eax
0x18007fef4  jle     short loc_18007FEFC
0x18007fef6  movzx   eax, ax
0x18007fef9  or      eax, r14d
0x18007fefc  mov     [rbp+4Fh+arg_0], eax
0x18007feff  test    eax, eax
0x18007ff01  jns     short loc_18007FF28
0x18007ff03  lea     rcx, base
0x18007ff0a  mov     [rsp+120h+var_E0], rcx
0x18007ff0f  lea     rcx, aHresult; "HRESULT"
0x18007ff16  mov     [rsp+120h+var_E8], rcx
0x18007ff1b  mov     [rsp+120h+var_F0], 24Bh
0x18007ff23  jmp     loc_180080128
0x18007ff28  xor     r9d, r9d; dwFlags
0x18007ff2b  mov     r8d, [rbx]; dwDataLen
0x18007ff2e  mov     rdx, [rbx+8]; pbData
0x18007ff32  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18007ff36  call    cs:__imp_CryptHashData
0x18007ff3c  test    eax, eax
0x18007ff3e  jnz     short loc_18007FF7C
0x18007ff40  call    cs:__imp_GetLastError
0x18007ff46  test    eax, eax
0x18007ff48  jle     short loc_18007FF50
0x18007ff4a  movzx   eax, ax
0x18007ff4d  or      eax, r14d
0x18007ff50  mov     [rbp+4Fh+arg_0], eax
0x18007ff53  test    eax, eax
0x18007ff55  jns     short loc_18007FF7C
0x18007ff57  lea     rcx, base
0x18007ff5e  mov     [rsp+120h+var_E0], rcx
0x18007ff63  lea     rcx, aHresult; "HRESULT"
0x18007ff6a  mov     [rsp+120h+var_E8], rcx
0x18007ff6f  mov     [rsp+120h+var_F0], 251h
0x18007ff77  jmp     loc_180080128
0x18007ff7c  lea     rax, [rsp+120h+pdwSigLen]
0x18007ff81  mov     [rsp+120h+pfCallerFreeProvOrNCryptKey], rax; pdwSigLen
0x18007ff86  mov     [rsp+120h+pdwKeySpec], r12; pbSignature
0x18007ff8b  xor     r9d, r9d; dwFlags
0x18007ff8e  xor     r8d, r8d; szDescription
0x18007ff91  mov     edx, [rbp+4Fh+dwKeySpec]; dwKeySpec
0x18007ff94  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18007ff98  call    cs:__imp_CryptSignHashW
0x18007ff9e  test    eax, eax
0x18007ffa0  jnz     short loc_18007FFDE
0x18007ffa2  call    cs:__imp_GetLastError
0x18007ffa8  test    eax, eax
0x18007ffaa  jle     short loc_18007FFB2
0x18007ffac  movzx   eax, ax
0x18007ffaf  or      eax, r14d
0x18007ffb2  mov     [rbp+4Fh+arg_0], eax
0x18007ffb5  test    eax, eax
0x18007ffb7  jns     short loc_18007FFDE
0x18007ffb9  lea     rcx, base
0x18007ffc0  mov     [rsp+120h+var_E0], rcx
0x18007ffc5  lea     rcx, aHresult; "HRESULT"
0x18007ffcc  mov     [rsp+120h+var_E8], rcx
0x18007ffd1  mov     [rsp+120h+var_F0], 257h
0x18007ffd9  jmp     loc_180080128
0x18007ffde  mov     ebx, [rsp+120h+pdwSigLen]
0x18007ffe2  mov     rax, [r15]
0x18007ffe5  mov     r8d, ebx
0x18007ffe8  mov     edx, 40h ; '@'
0x18007ffed  mov     rcx, r15
0x18007fff0  mov     rax, [rax+8]
0x18007fff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fff9  mov     r14, rax
0x18007fffc  lea     rcx, [rbp+4Fh+var_B0]
0x180080000  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180080005  mov     [rbp+4Fh+var_B0], r14
0x180080009  mov     [rbp+4Fh+var_A8], rbx
0x18008000d  test    r14, r14
0x180080010  jnz     short loc_18008003C
0x180080012  mov     eax, 8007000Eh
0x180080017  lea     rcx, base
0x18008001e  mov     [rsp+120h+var_E0], rcx
0x180080023  lea     rcx, aHresult; "HRESULT"
0x18008002a  mov     [rsp+120h+var_E8], rcx
0x18008002f  mov     [rsp+120h+var_F0], 25Dh
0x180080037  jmp     loc_180080125
0x18008003c  lea     rax, [rsp+120h+pdwSigLen]
0x180080041  mov     [rsp+120h+pfCallerFreeProvOrNCryptKey], rax; pdwSigLen
0x180080046  mov     [rsp+120h+pdwKeySpec], r14; pbSignature
0x18008004b  xor     r9d, r9d; dwFlags
0x18008004e  xor     r8d, r8d; szDescription
0x180080051  mov     edx, [rbp+4Fh+dwKeySpec]; dwKeySpec
0x180080054  mov     rcx, [rbp+4Fh+phHash]; hHash
0x180080058  call    cs:__imp_CryptSignHashW
0x18008005e  test    eax, eax
0x180080060  jnz     short loc_1800800A0
0x180080062  call    cs:__imp_GetLastError
0x180080068  test    eax, eax
0x18008006a  jle     short loc_180080074
0x18008006c  movzx   eax, ax
0x18008006f  or      eax, 80070000h
0x180080074  mov     [rbp+4Fh+arg_0], eax
0x180080077  test    eax, eax
0x180080079  jns     short loc_1800800A0
0x18008007b  lea     rcx, base
0x180080082  mov     [rsp+120h+var_E0], rcx
0x180080087  lea     rcx, aHresult; "HRESULT"
0x18008008e  mov     [rsp+120h+var_E8], rcx
0x180080093  mov     [rsp+120h+var_F0], 262h
0x18008009b  jmp     loc_180080128
0x1800800a0  mov     r9d, r12d
0x1800800a3  mov     r8d, [rsp+120h+pdwSigLen]
0x1800800a8  test    r8d, 0FFFFFFFEh
0x1800800af  jbe     short loc_1800800E5
0x1800800b1  mov     edx, r9d
0x1800800b4  mov     cl, [rdx+r14]
0x1800800b8  mov     eax, r8d
0x1800800bb  sub     rax, rdx
0x1800800be  mov     al, [rax+r14-1]
0x1800800c3  mov     [rdx+r14], al
0x1800800c7  mov     eax, [rsp+120h+pdwSigLen]
0x1800800cb  sub     rax, rdx
0x1800800ce  mov     [rax+r14-1], cl
0x1800800d3  inc     r9d
0x1800800d6  mov     r8d, [rsp+120h+pdwSigLen]
0x1800800db  mov     eax, r8d
0x1800800de  shr     eax, 1
0x1800800e0  cmp     r9d, eax
0x1800800e3  jb      short loc_1800800B1
0x1800800e5  xor     eax, eax
0x1800800e7  mov     [rsi], r8d
0x1800800ea  mov     [rsi+4], eax
0x1800800ed  mov     [rsi+8], r14
0x1800800f1  mov     [rbp+4Fh+var_B0], r12
0x1800800f5  mov     [rbp+4Fh+var_A8], r12
0x1800800f9  jmp     short loc_180080144
0x1800800fb  mov     eax, 80070057h
0x180080100  lea     rcx, base
0x180080107  mov     [rsp+120h+var_E0], rcx
0x18008010c  lea     rcx, aHresult; "HRESULT"
0x180080113  mov     [rsp+120h+var_E8], rcx
0x180080118  mov     [rsp+120h+var_F0], 225h
0x180080120  mov     edi, 2
0x180080125  mov     [rbp+4Fh+arg_0], eax
0x180080128  mov     [rsp+120h+pfCallerFreeProvOrNCryptKey], r13
0x18008012d  mov     dword ptr [rsp+120h+pdwKeySpec], eax
0x180080131  mov     r9d, edi
0x180080134  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18008013b  xor     edx, edx
0x18008013d  mov     ecx, edi
0x18008013f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180080144  mov     rcx, [rbp+4Fh+phHash]; hHash
0x180080148  test    rcx, rcx
0x18008014b  jz      short loc_180080153
0x18008014d  call    cs:__imp_CryptDestroyHash
0x180080153  cmp     [rbp+4Fh+var_C8], r12d
0x180080157  jz      short loc_180080178
0x180080159  mov     rcx, [rbp+4Fh+phCryptProvOrNCryptKey]; hProv
0x18008015d  test    rcx, rcx
0x180080160  jz      short loc_180080178
0x180080162  cmp     [rbp+4Fh+dwKeySpec], 0FFFFFFFFh
0x180080166  jnz     short loc_180080170
0x180080168  call    cs:__imp_NCryptFreeObject
  ... truncated ...
```
