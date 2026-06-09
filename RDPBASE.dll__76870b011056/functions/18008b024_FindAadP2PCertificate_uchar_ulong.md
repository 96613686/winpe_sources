# FindAadP2PCertificate(uchar * *,ulong *)

- ea: `0x18008b024`
- end: `0x18008b64a`
- name: `?FindAadP2PCertificate@@YAJPEAPEAEPEAK@Z`
- size: `1574`
- prototype: `__int64 __fastcall(struct _CERT_CONTEXT *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005ece4`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180078820`
- `0x180078c20`
- `0x18008b024`
- `0x18008bf98`
- `0x1800952b0`
- `0x180095540`
- `0x1800969d8`
- `0x180096b08`
- `0x180096cf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b505`
- `CRYPT32!CertCloseStore` at `0x18008b60e`
- `CRYPT32!CertCloseStore` at `0x18008b60e`
- `CRYPT32!CertOpenStore` at `0x18008b17c`
- `CRYPT32!CertOpenStore` at `0x18008b17c`
- `CRYPT32!CertFindCertificateInStore` at `0x18008b259`
- `CRYPT32!CertFindCertificateInStore` at `0x18008b259`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b2af`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b4fa`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b5fe`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b2af`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b4fa`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b5fe`

## string_xrefs

- `0x18008b0ed`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008b1d6`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008b417`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008b4a2`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008b5a5`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008b04e`: `MS-Organization-P2P-Access`
- `0x18008b1b2`: `Failed to open machine's Personal cert store`
- `0x18008b32b`: `Found an AAD P2P certificate, but it does not have a private key or RDP stack has no access to it`

## pseudocode

```c
__int64 __fastcall FindAadP2PCertificate(struct _CERT_CONTEXT *a1, unsigned __int8 **a2, int a3, int a4)
{
  void *v4; // rsi
  const CERT_CONTEXT *v5; // rdi
  int v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  signed int IssuerCertificate; // ebx
  HCERTSTORE v13; // r15
  signed int LastError; // eax
  const char *v15; // rax
  int *v16; // rdx
  CERT_CONTEXT *pPrevCertContext; // r14
  const CERT_CONTEXT *CertificateInStore; // rax
  const struct _CERT_CONTEXT *v19; // rdx
  const struct _CERT_CONTEXT **v20; // r9
  int v21; // ecx
  int v22; // r8d
  bool *v23; // r9
  int v24; // ecx
  bool *v25; // r8
  unsigned int *v26; // r9
  bool *v27; // r8
  const char *v28; // rax
  char *v29; // rdx
  const char *v30; // rax
  __int16 *v31; // rdx
  signed int v32; // eax
  void *pvPara; // [rsp+20h] [rbp-89h]
  bool v35[2]; // [rsp+50h] [rbp-59h] BYREF
  int v36; // [rsp+54h] [rbp-55h] BYREF
  int v37; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v38[44]; // [rsp+5Ch] [rbp-4Dh] BYREF
  wchar_t String1[28]; // [rsp+88h] [rbp-21h] BYREF

  v4 = 0;
  v5 = 0;
  v35[0] = 0;
  *(_QWORD *)&v38[12] = 0;
  *(_QWORD *)&v38[36] = 0;
  wcscpy(String1, L"MS-Organization-P2P-Acess");
  if ( !a1 || !a2 )
  {
    IssuerCertificate = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v13 = 0;
      v37 = 1367;
      *(_QWORD *)&v38[4] = "argument check failed";
      v36 = -2147024809;
      *(_QWORD *)&v38[28] = "FindAadP2PCertificate";
      *(_QWORD *)&v38[20] = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
      *(_QWORD *)&v38[12] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)&word_1801AC9A6,
        a3,
        a4,
        (__int64)&v38[12],
        (__int64)&v36,
        (__int64)&v38[20],
        (__int64)&v37,
        (__int64)&v38[28],
        (__int64)&v38[4]);
      goto LABEL_54;
    }
    return (unsigned int)IssuerCertificate;
  }
  v8 = IsDeviceAADJoined(v35, (unsigned __int16 **)&v38[12]);
  IssuerCertificate = v8;
  if ( v8 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v36 = 1371;
      *(_QWORD *)&v38[36] = "IsDeviceAADJoined failed";
      v37 = v8;
      *(_QWORD *)&v38[20] = "FindAadP2PCertificate";
      *(_QWORD *)&v38[28] = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
      *(_QWORD *)&v38[4] = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1801AC955,
        v10,
        v11,
        (__int64)&v38[4],
        (__int64)&v37,
        (__int64)&v38[28],
        (__int64)&v36,
        (__int64)&v38[20],
        (__int64)&v38[36]);
    }
    v4 = *(void **)&v38[12];
    goto LABEL_58;
  }
  v4 = *(void **)&v38[12];
  if ( !v35[0] || !*(_QWORD *)&v38[12] )
  {
    IssuerCertificate = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_58;
    v15 = "Local device is not AAD-Joined or Device ID is NULL";
    v37 = 1372;
    v16 = &dword_1801AC904;
    goto LABEL_14;
  }
  v13 = CertOpenStore("System", 0, 0, 0x24000u, L"My");
  if ( !v13 )
  {
    LastError = GetLastError();
    IssuerCertificate = LastError;
    if ( LastError > 0 )
      IssuerCertificate = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_58;
    v15 = "Failed to open machine's Personal cert store";
    v37 = 1384;
    v16 = (int *)byte_1801AC8B3;
LABEL_14:
    *(_QWORD *)&v38[4] = v15;
    *(_QWORD *)&v38[28] = "FindAadP2PCertificate";
    *(_QWORD *)&v38[20] = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
    *(_QWORD *)&v38[12] = "Error condition failed";
    v36 = IssuerCertificate;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v9,
      (_DWORD)v16,
      v10,
      v11,
      (__int64)&v38[12],
      (__int64)&v36,
      (__int64)&v38[20],
      (__int64)&v37,
      (__int64)&v38[28],
      (__int64)&v38[4]);
    goto LABEL_58;
  }
  pPrevCertContext = 0;
  while ( 1 )
  {
    *(_WORD *)v38 = 0;
    v35[0] = 0;
    CertificateInStore = CertFindCertificateInStore(v13, 0x10001u, 0, 0x80007u, v4, pPrevCertContext);
    pPrevCertContext = (CERT_CONTEXT *)CertificateInStore;
    if ( !CertificateInStore )
      break;
    IssuerCertificate = CertHelper::FindIssuerCertificate(
                          CertificateInStore,
                          v19,
                          (const unsigned __int16 *)&v38[36],
                          v20);
    if ( IssuerCertificate == -2147024894 )
    {
      v5 = *(const CERT_CONTEXT **)&v38[36];
    }
    else
    {
      if ( IssuerCertificate < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v37 = 1423;
          *(_QWORD *)&v38[4] = "FindIssuerCertificate failed";
          v36 = IssuerCertificate;
          *(_QWORD *)&v38[28] = "FindAadP2PCertificate";
          *(_QWORD *)&v38[20] = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          *(_QWORD *)&v38[12] = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v21,
            (unsigned int)word_1801AC862,
            v22,
            (_DWORD)v23,
            (__int64)&v38[12],
            (__int64)&v36,
            (__int64)&v38[20],
            (__int64)&v37,
            (__int64)&v38[28],
            (__int64)&v38[4]);
        }
        v5 = *(const CERT_CONTEXT **)&v38[36];
        goto LABEL_44;
      }
      v5 = *(const CERT_CONTEXT **)&v38[36];
      IssuerCertificate = CertHelper::MatchAgainstSubjectName(
                            *(PCCERT_CONTEXT *)&v38[36],
                            String1,
                            (const unsigned __int16 *)v35,
                            v23,
                            (unsigned __int64)pvPara);
      if ( IssuerCertificate < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v30 = "MatchAgainstSubjectName failed";
          v37 = 1429;
          v31 = (__int16 *)byte_1801AC811;
LABEL_40:
          *(_QWORD *)&v38[4] = v30;
          *(_QWORD *)&v38[28] = "FindAadP2PCertificate";
          *(_QWORD *)&v38[20] = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          *(_QWORD *)&v38[12] = "Error HResult failed";
          v36 = IssuerCertificate;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v24,
            (_DWORD)v31,
            (_DWORD)v25,
            (_DWORD)v26,
            (__int64)&v38[12],
            (__int64)&v36,
            (__int64)&v38[20],
            (__int64)&v37,
            (__int64)&v38[28],
            (__int64)&v38[4]);
        }
LABEL_44:
        CertFreeCertificateContext(pPrevCertContext);
        goto LABEL_54;
      }
      CertFreeCertificateContext(v5);
      v5 = 0;
      *(_QWORD *)&v38[36] = 0;
      if ( v35[0] )
      {
        IssuerCertificate = CertHelper::IsCertTimeValid(
                              (CertHelper *)pPrevCertContext,
                              (const struct _CERT_CONTEXT *)v38,
                              v27);
        if ( IssuerCertificate < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v30 = "IsCertTimeValid failed";
            v37 = 1441;
            v31 = (__int16 *)qword_1801AC7C0;
            goto LABEL_40;
          }
          goto LABEL_44;
        }
        if ( v38[0] )
        {
          IssuerCertificate = CertHelper::IsCertHasPrivateKey(
                                (CertHelper *)pPrevCertContext,
                                (const struct _CERT_CONTEXT *)&v38[1],
                                v25);
          if ( IssuerCertificate < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              v30 = "IsCertHasPrivateKey failed";
              v37 = 1455;
              v31 = word_1801AC74A;
              goto LABEL_40;
            }
            goto LABEL_44;
          }
          if ( v38[1] )
          {
            IssuerCertificate = CertHelper::GetCertificateHash(pPrevCertContext, a1, a2, v26);
            if ( IssuerCertificate < 0 && (unsigned int)CallbackContext > 2 )
            {
              v30 = "GetCertificateHash failed";
              v37 = 1467;
              v31 = (__int16 *)&dword_1801AC6D4;
              goto LABEL_40;
            }
            goto LABEL_44;
          }
          if ( (unsigned int)CallbackContext > 3 )
          {
            v28 = "Found an AAD P2P certificate, but it does not have a private key or RDP stack has no access to it";
            v29 = byte_1801AC725;
LABEL_30:
            *(_QWORD *)&v38[4] = v28;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (unsigned int)&CallbackContext,
              (_DWORD)v29,
              0,
              (_DWORD)v26,
              (__int64)&v38[4]);
          }
        }
        else if ( (unsigned int)CallbackContext > 3 )
        {
          v28 = "Found an AAD P2P certificate, but it's expired or not yet valid";
          v29 = byte_1801AC79B;
          goto LABEL_30;
        }
      }
    }
  }
  v32 = GetLastError();
  IssuerCertificate = v32;
  if ( v32 == -2146885628 || v32 == 18 )
  {
    IssuerCertificate = -2147024894;
  }
  else if ( v32 > 0 )
  {
    IssuerCertificate = (unsigned __int16)v32 | 0x80070000;
  }
LABEL_54:
  if ( v5 )
    CertFreeCertificateContext(v5);
  if ( v13 )
    CertCloseStore(v13, 0);
LABEL_58:
  if ( v4 )
    operator delete(v4);
  return (unsigned int)IssuerCertificate;
}

```

## disassembly

```asm
0x18008b024  mov     [rsp-8+arg_10], rbx
0x18008b029  push    rbp
0x18008b02a  push    rsi
0x18008b02b  push    rdi
0x18008b02c  push    r12
0x18008b02e  push    r13
0x18008b030  push    r14
0x18008b032  push    r15
0x18008b034  lea     rbp, [rsp-27h]
0x18008b039  sub     rsp, 0D0h
0x18008b040  mov     rax, cs:__security_cookie
0x18008b047  xor     rax, rsp
0x18008b04a  mov     [rbp+57h+var_40], rax
0x18008b04e  movups  xmm0, xmmword ptr cs:aMsOrganization; "MS-Organization-P2P-Access"
0x18008b055  xor     esi, esi
0x18008b057  xor     edi, edi
0x18008b059  mov     [rbp+57h+var_B0], 0
0x18008b05d  mov     r12, rdx
0x18008b060  mov     qword ptr [rbp+57h+var_A4+0Ch], rsi
0x18008b064  mov     r13, rcx
0x18008b067  mov     qword ptr [rbp+57h+var_A4+24h], rdi
0x18008b06b  movups  xmm1, xmmword ptr cs:aMsOrganization+10h; "ization-P2P-Access"
0x18008b072  movups  xmmword ptr [rbp+57h+String1], xmm0
0x18008b076  movups  xmm0, xmmword ptr cs:aMsOrganization+20h; "P2P-Access"
0x18008b07d  movups  [rbp+57h+var_68], xmm1
0x18008b081  movsd   xmm1, qword ptr cs:aMsOrganization+2Eh; "ess"
0x18008b089  movups  [rbp+57h+var_58], xmm0
0x18008b08d  movsd   qword ptr [rbp+57h+var_58+0Eh], xmm1
0x18008b092  test    rcx, rcx
0x18008b095  jz      loc_18008B567
0x18008b09b  test    rdx, rdx
0x18008b09e  jz      loc_18008B567
0x18008b0a4  lea     rdx, [rbp+57h+var_A4+0Ch]; unsigned __int16 **
0x18008b0a8  lea     rcx, [rbp+57h+var_B0]; bool *
0x18008b0ac  call    ?IsDeviceAADJoined@@YAJAEA_NPEAPEAG@Z; IsDeviceAADJoined(bool &,ushort * *)
0x18008b0b1  mov     ebx, eax
0x18008b0b3  test    eax, eax
0x18008b0b5  jns     loc_18008B147
0x18008b0bb  mov     ecx, cs:CallbackContext
0x18008b0c1  cmp     ecx, 2
0x18008b0c4  jbe     short loc_18008B13E
0x18008b0c6  lea     rax, aIsdeviceaadjoi_0; "IsDeviceAADJoined failed"
0x18008b0cd  mov     [rbp+57h+var_AC], 55Bh
0x18008b0d4  mov     qword ptr [rbp+57h+var_A4+24h], rax
0x18008b0d8  lea     rdx, byte_1801AC955
0x18008b0df  lea     rax, aFindaadp2pcert; "FindAadP2PCertificate"
0x18008b0e6  mov     [rbp+57h+var_A8], ebx
0x18008b0e9  mov     qword ptr [rbp+57h+var_A4+14h], rax
0x18008b0ed  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008b0f4  mov     qword ptr [rbp+57h+var_A4+1Ch], rax
0x18008b0f8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008b0ff  mov     qword ptr [rbp+57h+var_A4+4], rax
0x18008b103  lea     rax, [rbp+57h+var_A4+24h]
0x18008b107  mov     [rsp+100h+var_B8], rax
0x18008b10c  lea     rax, [rbp+57h+var_A4+14h]
0x18008b110  mov     [rsp+100h+var_C0], rax
0x18008b115  lea     rax, [rbp+57h+var_AC]
0x18008b119  mov     [rsp+100h+var_C8], rax
0x18008b11e  lea     rax, [rbp+57h+var_A4+1Ch]
0x18008b122  mov     [rsp+100h+var_D0], rax
0x18008b127  lea     rax, [rbp+57h+var_A8]
0x18008b12b  mov     [rsp+100h+pPrevCertContext], rax
0x18008b130  lea     rax, [rbp+57h+var_A4+4]
0x18008b134  mov     [rsp+100h+pvPara], rax
0x18008b139  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008b13e  mov     rsi, qword ptr [rbp+57h+var_A4+0Ch]
0x18008b142  jmp     loc_18008B614
0x18008b147  mov     rsi, qword ptr [rbp+57h+var_A4+0Ch]
0x18008b14b  cmp     [rbp+57h+var_B0], dil
0x18008b14f  jz      loc_18008B539
0x18008b155  test    rsi, rsi
0x18008b158  jz      loc_18008B539
0x18008b15e  lea     rax, aMy; "My"
0x18008b165  mov     r9d, 24000h; dwFlags
0x18008b16b  xor     r8d, r8d; hCryptProv
0x18008b16e  mov     [rsp+100h+pvPara], rax; pvPara
0x18008b173  xor     edx, edx; dwEncodingType
0x18008b175  lea     rcx, szStoreProvider; "System"
0x18008b17c  call    cs:__imp_CertOpenStore
0x18008b182  mov     r15, rax
0x18008b185  test    rax, rax
0x18008b188  jnz     loc_18008B22F
0x18008b18e  call    cs:__imp_GetLastError
0x18008b194  mov     ebx, eax
0x18008b196  test    eax, eax
0x18008b198  jle     short loc_18008B1A3
0x18008b19a  movzx   ebx, ax
0x18008b19d  or      ebx, 80070000h
0x18008b1a3  mov     eax, cs:CallbackContext
0x18008b1a9  cmp     eax, 2
0x18008b1ac  jbe     loc_18008B614
0x18008b1b2  lea     rax, aFailedToOpenMa; "Failed to open machine's Personal cert "...
0x18008b1b9  mov     [rbp+57h+var_A8], 568h
0x18008b1c0  lea     rdx, byte_1801AC8B3
0x18008b1c7  mov     qword ptr [rbp+57h+var_A4+4], rax
0x18008b1cb  lea     rax, aFindaadp2pcert; "FindAadP2PCertificate"
0x18008b1d2  mov     qword ptr [rbp+57h+var_A4+1Ch], rax
0x18008b1d6  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008b1dd  mov     qword ptr [rbp+57h+var_A4+14h], rax
0x18008b1e1  lea     rax, aErrorCondition; "Error condition failed"
0x18008b1e8  mov     qword ptr [rbp+57h+var_A4+0Ch], rax
0x18008b1ec  lea     rax, [rbp+57h+var_A4+4]
0x18008b1f0  mov     [rsp+100h+var_B8], rax
0x18008b1f5  lea     rax, [rbp+57h+var_A4+1Ch]
0x18008b1f9  mov     [rsp+100h+var_C0], rax
0x18008b1fe  lea     rax, [rbp+57h+var_A8]
0x18008b202  mov     [rsp+100h+var_C8], rax
0x18008b207  lea     rax, [rbp+57h+var_A4+14h]
0x18008b20b  mov     [rsp+100h+var_D0], rax
0x18008b210  lea     rax, [rbp+57h+var_AC]
0x18008b214  mov     [rsp+100h+pPrevCertContext], rax
0x18008b219  lea     rax, [rbp+57h+var_A4+0Ch]
0x18008b21d  mov     [rsp+100h+pvPara], rax
0x18008b222  mov     [rbp+57h+var_AC], ebx
0x18008b225  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008b22a  jmp     loc_18008B614
0x18008b22f  xor     r14d, r14d
0x18008b232  mov     [rsp+100h+pPrevCertContext], r14; pPrevCertContext
0x18008b237  mov     r9d, 80007h; dwFindType
0x18008b23d  xor     r8d, r8d; dwFindFlags
0x18008b240  mov     [rsp+100h+pvPara], rsi; unsigned __int64
0x18008b245  mov     edx, 10001h; dwCertEncodingType
0x18008b24a  mov     [rbp+57h+var_A4+1], 0
0x18008b24e  mov     rcx, r15; hCertStore
0x18008b251  mov     [rbp+57h+var_A4], 0
0x18008b255  mov     [rbp+57h+var_B0], 0
0x18008b259  call    cs:__imp_CertFindCertificateInStore
0x18008b25f  mov     r14, rax
0x18008b262  test    rax, rax
0x18008b265  jz      loc_18008B505
0x18008b26b  lea     r8, [rbp+57h+var_A4+24h]; unsigned __int16 *
0x18008b26f  mov     rcx, rax; pSubjectContext
0x18008b272  call    ?FindIssuerCertificate@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEBGPEAPEBU2@@Z; CertHelper::FindIssuerCertificate(_CERT_CONTEXT const *,ushort const *,_CERT_CONTEXT const * *)
0x18008b277  mov     ebx, eax
0x18008b279  cmp     eax, 80070002h
0x18008b27e  jnz     short loc_18008B286
0x18008b280  mov     rdi, qword ptr [rbp+57h+var_A4+24h]
0x18008b284  jmp     short loc_18008B232
0x18008b286  test    ebx, ebx
0x18008b288  js      loc_18008B470
0x18008b28e  mov     rdi, qword ptr [rbp+57h+var_A4+24h]
0x18008b292  lea     r8, [rbp+57h+var_B0]; unsigned __int16 *
0x18008b296  mov     rcx, rdi; pCertContext
0x18008b299  lea     rdx, [rbp+57h+String1]; String1
0x18008b29d  call    ?MatchAgainstSubjectName@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEBGAEA_N_K@Z; CertHelper::MatchAgainstSubjectName(_CERT_CONTEXT const *,ushort const *,bool &,unsigned __int64)
0x18008b2a2  mov     ebx, eax
0x18008b2a4  test    eax, eax
0x18008b2a6  js      loc_18008B3E4
0x18008b2ac  mov     rcx, rdi; pCertContext
0x18008b2af  call    cs:__imp_CertFreeCertificateContext
0x18008b2b5  xor     edi, edi
0x18008b2b7  mov     qword ptr [rbp+57h+var_A4+24h], rdi
0x18008b2bb  cmp     [rbp+57h+var_B0], dil
0x18008b2bf  jz      loc_18008B232
0x18008b2c5  lea     rdx, [rbp+57h+var_A4]; struct _CERT_CONTEXT *
0x18008b2c9  mov     rcx, r14; this
0x18008b2cc  call    ?IsCertTimeValid@CertHelper@@YAJPEBU_CERT_CONTEXT@@AEA_N@Z; CertHelper::IsCertTimeValid(_CERT_CONTEXT const *,bool &)
0x18008b2d1  mov     ebx, eax
0x18008b2d3  test    eax, eax
0x18008b2d5  js      loc_18008B3BE
0x18008b2db  cmp     [rbp+57h+var_A4], dil
0x18008b2df  jnz     short loc_18008B300
0x18008b2e1  mov     eax, cs:CallbackContext
0x18008b2e7  cmp     eax, 3
0x18008b2ea  jbe     loc_18008B232
0x18008b2f0  lea     rax, aFoundAnAadP2pC_0; "Found an AAD P2P certificate, but it's "...
0x18008b2f7  lea     rdx, byte_1801AC79B
0x18008b2fe  jmp     short loc_18008B339
0x18008b300  lea     rdx, [rbp+57h+var_A4+1]; struct _CERT_CONTEXT *
0x18008b304  mov     rcx, r14; this
0x18008b307  call    ?IsCertHasPrivateKey@CertHelper@@YAJPEBU_CERT_CONTEXT@@AEA_N@Z; CertHelper::IsCertHasPrivateKey(_CERT_CONTEXT const *,bool &)
0x18008b30c  mov     ebx, eax
0x18008b30e  test    eax, eax
0x18008b310  js      loc_18008B398
0x18008b316  cmp     [rbp+57h+var_A4+1], dil
0x18008b31a  jnz     short loc_18008B35A
0x18008b31c  mov     eax, cs:CallbackContext
0x18008b322  cmp     eax, 3
0x18008b325  jbe     loc_18008B232
0x18008b32b  lea     rax, aFoundAnAadP2pC; "Found an AAD P2P certificate, but it do"...
0x18008b332  lea     rdx, byte_1801AC725
0x18008b339  mov     qword ptr [rbp+57h+var_A4+4], rax
0x18008b33d  lea     rcx, CallbackContext
0x18008b344  lea     rax, [rbp+57h+var_A4+4]
0x18008b348  xor     r8d, r8d
0x18008b34b  mov     [rsp+100h+pvPara], rax
0x18008b350  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008b355  jmp     loc_18008B232
0x18008b35a  mov     r8, r12; unsigned __int8 **
0x18008b35d  mov     rdx, r13; struct _CERT_CONTEXT *
0x18008b360  mov     rcx, r14; pCertContext
0x18008b363  call    ?GetCertificateHash@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; CertHelper::GetCertificateHash(_CERT_CONTEXT const *,uchar * *,ulong *)
0x18008b368  mov     ebx, eax
0x18008b36a  test    eax, eax
0x18008b36c  jns     loc_18008B4F7
0x18008b372  mov     eax, cs:CallbackContext
0x18008b378  cmp     eax, 2
0x18008b37b  jbe     loc_18008B4F7
0x18008b381  lea     rax, aGetcertificate_4; "GetCertificateHash failed"
0x18008b388  mov     [rbp+57h+var_A8], 5BBh
0x18008b38f  lea     rdx, dword_1801AC6D4
0x18008b396  jmp     short loc_18008B408
0x18008b398  mov     eax, cs:CallbackContext
0x18008b39e  cmp     eax, 2
0x18008b3a1  jbe     loc_18008B4F7
0x18008b3a7  lea     rax, aIscerthaspriva_0; "IsCertHasPrivateKey failed"
0x18008b3ae  mov     [rbp+57h+var_A8], 5AFh
0x18008b3b5  lea     rdx, word_1801AC74A
0x18008b3bc  jmp     short loc_18008B408
0x18008b3be  mov     eax, cs:CallbackContext
0x18008b3c4  cmp     eax, 2
0x18008b3c7  jbe     loc_18008B4F7
0x18008b3cd  lea     rax, aIscerttimevali_0; "IsCertTimeValid failed"
0x18008b3d4  mov     [rbp+57h+var_A8], 5A1h
0x18008b3db  lea     rdx, qword_1801AC7C0
0x18008b3e2  jmp     short loc_18008B408
0x18008b3e4  mov     eax, cs:CallbackContext
0x18008b3ea  cmp     eax, 2
0x18008b3ed  jbe     loc_18008B4F7
0x18008b3f3  lea     rax, aMatchagainstsu; "MatchAgainstSubjectName failed"
0x18008b3fa  mov     [rbp+57h+var_A8], 595h
0x18008b401  lea     rdx, byte_1801AC811
0x18008b408  mov     qword ptr [rbp+57h+var_A4+4], rax
0x18008b40c  lea     rax, aFindaadp2pcert; "FindAadP2PCertificate"
0x18008b413  mov     qword ptr [rbp+57h+var_A4+1Ch], rax
0x18008b417  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008b41e  mov     qword ptr [rbp+57h+var_A4+14h], rax
0x18008b422  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008b429  mov     qword ptr [rbp+57h+var_A4+0Ch], rax
0x18008b42d  lea     rax, [rbp+57h+var_A4+4]
0x18008b431  mov     [rsp+100h+var_B8], rax
0x18008b436  lea     rax, [rbp+57h+var_A4+1Ch]
0x18008b43a  mov     [rsp+100h+var_C0], rax
0x18008b43f  lea     rax, [rbp+57h+var_A8]
0x18008b443  mov     [rsp+100h+var_C8], rax
0x18008b448  lea     rax, [rbp+57h+var_A4+14h]
0x18008b44c  mov     [rsp+100h+var_D0], rax
0x18008b451  lea     rax, [rbp+57h+var_AC]
0x18008b455  mov     [rsp+100h+pPrevCertContext], rax
0x18008b45a  lea     rax, [rbp+57h+var_A4+0Ch]
0x18008b45e  mov     [rsp+100h+pvPara], rax
0x18008b463  mov     [rbp+57h+var_AC], ebx
0x18008b466  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008b46b  jmp     loc_18008B4F7
0x18008b470  mov     eax, cs:CallbackContext
0x18008b476  cmp     eax, 2
0x18008b479  jbe     short loc_18008B4F3
0x18008b47b  lea     rax, aFindissuercert; "FindIssuerCertificate failed"
0x18008b482  mov     [rbp+57h+var_A8], 58Fh
0x18008b489  mov     qword ptr [rbp+57h+var_A4+4], rax
0x18008b48d  lea     rdx, word_1801AC862
0x18008b494  lea     rax, aFindaadp2pcert; "FindAadP2PCertificate"
0x18008b49b  mov     [rbp+57h+var_AC], ebx
0x18008b49e  mov     qword ptr [rbp+57h+var_A4+1Ch], rax
0x18008b4a2  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008b4a9  mov     qword ptr [rbp+57h+var_A4+14h], rax
0x18008b4ad  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008b4b4  mov     qword ptr [rbp+57h+var_A4+0Ch], rax
0x18008b4b8  lea     rax, [rbp+57h+var_A4+4]
0x18008b4bc  mov     [rsp+100h+var_B8], rax
0x18008b4c1  lea     rax, [rbp+57h+var_A4+1Ch]
0x18008b4c5  mov     [rsp+100h+var_C0], rax
0x18008b4ca  lea     rax, [rbp+57h+var_A8]
0x18008b4ce  mov     [rsp+100h+var_C8], rax
0x18008b4d3  lea     rax, [rbp+57h+var_A4+14h]
0x18008b4d7  mov     [rsp+100h+var_D0], rax
0x18008b4dc  lea     rax, [rbp+57h+var_AC]
0x18008b4e0  mov     [rsp+100h+pPrevCertContext], rax
0x18008b4e5  lea     rax, [rbp+57h+var_A4+0Ch]
0x18008b4e9  mov     [rsp+100h+pvPara], rax
0x18008b4ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008b4f3  mov     rdi, qword ptr [rbp+57h+var_A4+24h]
0x18008b4f7  mov     rcx, r14; pCertContext
0x18008b4fa  call    cs:__imp_CertFreeCertificateContext
0x18008b500  jmp     loc_18008B5F6
0x18008b505  call    cs:__imp_GetLastError
0x18008b50b  mov     ebx, eax
0x18008b50d  cmp     eax, 80092004h
0x18008b512  jz      short loc_18008B52F
0x18008b514  cmp     eax, 12h
0x18008b517  jz      short loc_18008B52F
0x18008b519  test    eax, eax
0x18008b51b  jle     loc_18008B5F6
0x18008b521  movzx   ebx, ax
0x18008b524  or      ebx, 80070000h
0x18008b52a  jmp     loc_18008B5F6
0x18008b52f  mov     ebx, 80070002h
0x18008b534  jmp     loc_18008B5F6
0x18008b539  mov     eax, cs:CallbackContext
0x18008b53f  mov     ebx, 8000FFFFh
0x18008b544  cmp     eax, 2
0x18008b547  jbe     loc_18008B614
0x18008b54d  lea     rax, aLocalDeviceIsN_0; "Local device is not AAD-Joined or Devic"...
0x18008b554  mov     [rbp+57h+var_A8], 55Ch
0x18008b55b  lea     rdx, dword_1801AC904
0x18008b562  jmp     loc_18008B1C7
0x18008b567  mov     eax, cs:CallbackContext
0x18008b56d  mov     ebx, 80070057h
0x18008b572  cmp     eax, 2
0x18008b575  jbe     loc_18008B621
  ... truncated ...
```
