# CCertRequest::ParseCertificate(uchar *,ulong,ulong,ulong,uint)

- ea: `0x180036090`
- end: `0x1800365e0`
- name: `?ParseCertificate@CCertRequest@@QEAAJPEAEKKKI@Z`
- size: `1360`
- prototype: `__int64 __fastcall(CCertRequest *this, unsigned __int8 *, DWORD, DWORD, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18004c428`

## callees

- `0x18001e1a8`
- `0x180023dd0`
- `0x1800353e4`
- `0x180035568`
- `0x180035650`
- `0x180035868`
- `0x180035924`
- `0x1800359fc`
- `0x180035c34`
- `0x180035dac`
- `0x180036090`
- `0x1800365e8`
- `0x180036a58`
- `0x1800406b0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800362a4`
- `KERNEL32!HeapFree` at `0x1800363ac`
- `KERNEL32!HeapFree` at `0x1800362a4`
- `KERNEL32!HeapFree` at `0x1800363ac`
- `CRYPT32!CertCreateCertificateContext` at `0x1800360f1`
- `CRYPT32!CertCreateCertificateContext` at `0x1800360f1`
- `CRYPT32!CertFreeCertificateContext` at `0x180036590`
- `CRYPT32!CertFreeCertificateContext` at `0x180036590`

## pseudocode

```c
__int64 __fastcall CCertRequest::ParseCertificate(
        CCertRequest *this,
        unsigned __int8 *a2,
        DWORD a3,
        DWORD a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v6; // rax
  __int64 v9; // r9
  __int64 v10; // r14
  int v11; // r15d
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v13; // rsi
  unsigned int v14; // ebx
  char *v15; // rax
  struct _CERT_NAME_INFO *v16; // r15
  char *v17; // rbx
  int v18; // r8d
  __int64 v19; // rdx
  unsigned int v20; // r14d
  __int64 v21; // rdx
  char *v23; // rax
  struct _CERT_NAME_INFO *v24; // r15
  char *v25; // rbx
  int v26; // r8d
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  PCERT_INFO pCertInfo; // rcx
  DWORD cbData; // eax
  DWORD v33; // r10d
  __int64 v34; // r9
  int v35; // r8d
  unsigned __int64 v36; // rcx
  char v37; // al
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  _DWORD v44[2]; // [rsp+40h] [rbp-99h] BYREF
  __int64 v45; // [rsp+48h] [rbp-91h]
  LPVOID lpMem; // [rsp+50h] [rbp-89h] BYREF
  DWORD v47; // [rsp+58h] [rbp-81h] BYREF
  _BYTE v48[128]; // [rsp+60h] [rbp-79h] BYREF

  v6 = *(_QWORD *)this;
  v47 = a4;
  v44[1] = 0;
  lpMem = 0;
  v9 = *(_QWORD *)(v6 + 56);
  v10 = *(_QWORD *)(v9 + 392);
  v11 = *(_DWORD *)(v9 + 400);
  v45 = v10;
  v44[0] = v11;
  CertificateContext = CertCreateCertificateContext(a4, a2, a3);
  v13 = CertificateContext;
  if ( CertificateContext )
  {
    if ( !(unsigned int)XBF::Extend(
                          (XBF *)v44,
                          7 * CertificateContext->cbCertEncoded
                        + 157
                        + 3 * CertificateContext->pCertInfo->SerialNumber.cbData
                        + 2
                        * (CertificateContext->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData
                         + (4 * CertificateContext->pCertInfo->Issuer.cbData + 12) / 3
                         + (4 * CertificateContext->pCertInfo->Subject.cbData + 12) / 3)) )
    {
      ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
      v14 = -2147024882;
LABEL_34:
      CertFreeCertificateContext(v13);
      v10 = v45;
      v11 = v44[0];
      goto LABEL_35;
    }
    if ( !(unsigned int)DecodeRdn(&v13->pCertInfo->Issuer, (struct _CERT_NAME_INFO **)&lpMem) )
    {
LABEL_6:
      v14 = -2147467259;
      goto LABEL_34;
    }
    v15 = XBF::ReserveRange((XBF *)v44, 0, 1);
    v16 = (struct _CERT_NAME_INFO *)lpMem;
    v17 = v15;
    if ( !BuildRdnList((struct _CERT_NAME_INFO *)lpMem, (struct XBF *)v44, v18) )
    {
LABEL_8:
      ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
      goto LABEL_6;
    }
    v20 = a6;
    v14 = CCertRequest::AddStringPair(this, v19, "ISSUER", v17, v44, 0, a6);
    if ( v14 )
      goto LABEL_34;
    v14 = CCertRequest::AddUuBinaryPair(
            this,
            v21,
            "BINARYISSUER",
            v13->pCertInfo->Issuer.pbData,
            v13->pCertInfo->Issuer.cbData,
            v44,
            v20);
    if ( !v14 )
    {
      v14 = CCertRequest::ParseRDNS(this, v16, "ISSUER", (struct XBF *)v44, v20);
      if ( !v14 )
      {
        HeapFree(g_hDenaliHeap, 0, v16);
        if ( !(unsigned int)DecodeRdn(&v13->pCertInfo->Subject, (struct _CERT_NAME_INFO **)&lpMem) )
        {
          ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
          return 2147500037LL;
        }
        v23 = XBF::ReserveRange((XBF *)v44, 0, 1);
        v24 = (struct _CERT_NAME_INFO *)lpMem;
        v25 = v23;
        if ( !BuildRdnList((struct _CERT_NAME_INFO *)lpMem, (struct XBF *)v44, v26) )
          goto LABEL_8;
        v14 = CCertRequest::AddStringPair(this, v27, "SUBJECT", v25, v44, 0, v20);
        if ( !v14 )
        {
          v14 = CCertRequest::AddUuBinaryPair(
                  this,
                  v28,
                  "BINARYSUBJECT",
                  v13->pCertInfo->Subject.pbData,
                  v13->pCertInfo->Subject.cbData,
                  v44,
                  v20);
          if ( !v14 )
          {
            v14 = CCertRequest::ParseRDNS(this, v24, "SUBJECT", (struct XBF *)v44, v20);
            if ( !v14 )
            {
              HeapFree(g_hDenaliHeap, 0, v24);
              v14 = CCertRequest::AddBinaryPair(
                      this,
                      v29,
                      "CERTIFICATE",
                      v13->pbCertEncoded,
                      v13->cbCertEncoded,
                      v44,
                      v20);
              if ( !v14 )
              {
                pCertInfo = v13->pCertInfo;
                cbData = pCertInfo->SerialNumber.cbData;
                v33 = cbData - 1;
                if ( cbData - 1 <= 0x28 )
                {
                  if ( cbData )
                  {
                    v34 = 0;
                    do
                    {
                      v35 = 3 * (v33 - v34);
                      v48[v35] = a0123456789abcd_0[(unsigned __int64)pCertInfo->SerialNumber.pbData[v34] >> 4];
                      v30 = v13->pCertInfo->SerialNumber.pbData[v34] & 0xF;
                      v48[v35 + 1] = a0123456789abcd_0[v30];
                      v36 = (unsigned int)(v35 + 2);
                      if ( (_DWORD)v34 )
                      {
                        v37 = 45;
                      }
                      else
                      {
                        if ( v36 >= 0x80 )
                          _report_rangecheckfailure();
                        v37 = 0;
                      }
                      v48[v36] = v37;
                      v34 = (unsigned int)(v34 + 1);
                      pCertInfo = v13->pCertInfo;
                    }
                    while ( (unsigned int)v34 < pCertInfo->SerialNumber.cbData );
                  }
                  v14 = CCertRequest::AddStringPair(this, v30, "SERIALNUMBER", v48, v44, 1, v20);
                  if ( !v14 )
                  {
                    v14 = CCertRequest::AddBinaryPair(
                            this,
                            v38,
                            "PUBLICKEY",
                            v13->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
                            v13->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
                            v44,
                            v20);
                    if ( !v14 )
                    {
                      v14 = CCertRequest::AddDatePair(this, v39, "VALIDFROM", &v13->pCertInfo->NotBefore, v44);
                      if ( !v14 )
                      {
                        v14 = CCertRequest::AddDatePair(this, v40, "VALIDUNTIL", &v13->pCertInfo->NotAfter, v44);
                        if ( !v14 )
                        {
                          v14 = CCertRequest::AddDwordPair(this, v41, "FLAGS", &a5, v44);
                          if ( !v14 )
                          {
                            v14 = CCertRequest::AddDwordPair(this, v42, "ENCODING", &v47, v44);
                            if ( !v14 )
                              goto LABEL_34;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
    goto LABEL_34;
  }
  ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
  v14 = -2147467259;
LABEL_35:
  v43 = *(_QWORD *)this;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 56LL) + 392LL) = v10;
  *(_QWORD *)(*(_QWORD *)(v43 + 56) + 400LL) = v11;
  return v14;
}

```

## disassembly

```asm
0x180036090  push    rbp
0x180036092  push    rbx
0x180036093  push    rsi
0x180036094  push    rdi
0x180036095  push    r14
0x180036097  push    r15
0x180036099  lea     rbp, [rsp-1Fh]
0x18003609e  sub     rsp, 0F8h
0x1800360a5  mov     rax, cs:__security_cookie
0x1800360ac  xor     rax, rsp
0x1800360af  mov     [rbp+47h+var_40], rax
0x1800360b3  mov     rax, [rcx]
0x1800360b6  mov     r10d, r9d
0x1800360b9  mov     [rsp+120h+var_C8], r9d
0x1800360be  mov     rdi, rcx
0x1800360c1  mov     ecx, r10d; dwCertEncodingType
0x1800360c4  mov     [rsp+120h+var_DC], 0
0x1800360cc  mov     [rsp+120h+lpMem], 0
0x1800360d5  mov     r9, [rax+38h]
0x1800360d9  mov     r14, [r9+188h]
0x1800360e0  mov     r15d, [r9+190h]
0x1800360e7  mov     [rsp+120h+var_D8], r14
0x1800360ec  mov     [rsp+120h+var_E0], r15d
0x1800360f1  call    cs:__imp_CertCreateCertificateContext
0x1800360f7  mov     rsi, rax
0x1800360fa  test    rax, rax
0x1800360fd  jnz     short loc_180036121
0x1800360ff  xor     r9d, r9d; int
0x180036102  lea     r8d, [rax+64h]; unsigned int
0x180036106  mov     edx, 1964h; unsigned int
0x18003610b  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x180036112  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180036117  mov     ebx, 80004005h
0x18003611c  jmp     loc_1800365A0
0x180036121  mov     r9, [rax+18h]
0x180036125  mov     r10d, 0AAAAAAABh
0x18003612b  mov     eax, [r9+50h]
0x18003612f  lea     ecx, ds:0Ch[rax*4]
0x180036136  mov     eax, r10d
0x180036139  mul     ecx
0x18003613b  mov     ecx, [r9+30h]
0x18003613f  mov     eax, r10d
0x180036142  mov     r8d, edx
0x180036145  shr     r8d, 1
0x180036148  lea     ecx, ds:0Ch[rcx*4]
0x18003614f  mul     ecx
0x180036151  mov     eax, [r9+8]
0x180036155  shr     edx, 1
0x180036157  add     r8d, edx
0x18003615a  add     r8d, [r9+78h]
0x18003615e  lea     ecx, [rax+rax*2]
0x180036161  imul    eax, [rsi+10h], 7
0x180036165  lea     edx, [rcx+r8*2]
0x180036169  lea     rcx, [rsp+120h+var_E0]; this
0x18003616e  add     eax, 9Dh
0x180036173  add     edx, eax; int
0x180036175  call    ?Extend@XBF@@QEAAHH@Z; XBF::Extend(int)
0x18003617a  test    eax, eax
0x18003617c  jnz     short loc_1800361A0
0x18003617e  xor     r9d, r9d; int
0x180036181  lea     r8d, [rax+64h]; unsigned int
0x180036185  mov     edx, 1964h; unsigned int
0x18003618a  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x180036191  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180036196  mov     ebx, 8007000Eh
0x18003619b  jmp     loc_18003658D
0x1800361a0  mov     rcx, [rsi+18h]
0x1800361a4  lea     rdx, [rsp+120h+lpMem]; struct _CERT_NAME_INFO **
0x1800361a9  add     rcx, 30h ; '0'; struct _CRYPTOAPI_BLOB *
0x1800361ad  call    ?DecodeRdn@@YAHPEAU_CRYPTOAPI_BLOB@@PEAPEAU_CERT_NAME_INFO@@@Z; DecodeRdn(_CRYPTOAPI_BLOB *,_CERT_NAME_INFO * *)
0x1800361b2  test    eax, eax
0x1800361b4  jnz     short loc_1800361C0
0x1800361b6  mov     ebx, 80004005h
0x1800361bb  jmp     loc_18003658D
0x1800361c0  xor     edx, edx; int
0x1800361c2  lea     rcx, [rsp+120h+var_E0]; this
0x1800361c7  lea     r8d, [rdx+1]; int
0x1800361cb  call    ?ReserveRange@XBF@@QEAAPEADHH@Z; XBF::ReserveRange(int,int)
0x1800361d0  mov     r15, [rsp+120h+lpMem]
0x1800361d5  lea     rdx, [rsp+120h+var_E0]; struct XBF *
0x1800361da  mov     rcx, r15; struct _CERT_NAME_INFO *
0x1800361dd  mov     rbx, rax
0x1800361e0  call    ?BuildRdnList@@YAHPEAU_CERT_NAME_INFO@@PEAVXBF@@H@Z; BuildRdnList(_CERT_NAME_INFO *,XBF *,int)
0x1800361e5  test    eax, eax
0x1800361e7  jnz     short loc_180036203
0x1800361e9  xor     r9d, r9d; int
0x1800361ec  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x1800361f3  mov     edx, 1964h; unsigned int
0x1800361f8  lea     r8d, [r9+64h]; unsigned int
0x1800361fc  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180036201  jmp     short loc_1800361B6
0x180036203  mov     r14d, [rbp+47h+arg_28]
0x180036207  lea     rax, [rsp+120h+var_E0]
0x18003620c  mov     [rsp+120h+var_F0], r14d
0x180036211  lea     r8, aIssuer; "ISSUER"
0x180036218  mov     dword ptr [rsp+120h+var_F8], 0
0x180036220  mov     r9, rbx
0x180036223  mov     rcx, rdi
0x180036226  mov     qword ptr [rsp+120h+var_100], rax
0x18003622b  call    ?AddStringPair@CCertRequest@@QEAAJW4CollectionType@@PEAD1PEAVXBF@@HI@Z; CCertRequest::AddStringPair(CollectionType,char *,char *,XBF *,int,uint)
0x180036230  mov     ebx, eax
0x180036232  test    eax, eax
0x180036234  jnz     loc_18003658D
0x18003623a  mov     r9, [rsi+18h]
0x18003623e  lea     rax, [rsp+120h+var_E0]
0x180036243  mov     [rsp+120h+var_F0], r14d
0x180036248  lea     r8, aBinaryissuer; "BINARYISSUER"
0x18003624f  mov     [rsp+120h+var_F8], rax
0x180036254  mov     rcx, rdi
0x180036257  mov     eax, [r9+30h]
0x18003625b  mov     r9, [r9+38h]
0x18003625f  mov     [rsp+120h+var_100], eax
0x180036263  call    ?AddUuBinaryPair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAEKPEAVXBF@@I@Z; CCertRequest::AddUuBinaryPair(CollectionType,char *,uchar *,ulong,XBF *,uint)
0x180036268  mov     ebx, eax
0x18003626a  test    eax, eax
0x18003626c  jnz     loc_180036575
0x180036272  lea     r9, [rsp+120h+var_E0]; struct XBF *
0x180036277  mov     [rsp+120h+var_100], r14d; unsigned int
0x18003627c  lea     r8, aIssuer; "ISSUER"
0x180036283  mov     rdx, r15; struct _CERT_NAME_INFO *
0x180036286  mov     rcx, rdi; this
0x180036289  call    ?ParseRDNS@CCertRequest@@QEAAJPEAU_CERT_NAME_INFO@@PEADPEAVXBF@@I@Z; CCertRequest::ParseRDNS(_CERT_NAME_INFO *,char *,XBF *,uint)
0x18003628e  mov     ebx, eax
0x180036290  test    eax, eax
0x180036292  jnz     loc_180036575
0x180036298  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18003629f  mov     r8, r15; lpMem
0x1800362a2  xor     edx, edx; dwFlags
0x1800362a4  call    cs:__imp_HeapFree
0x1800362aa  mov     rcx, [rsi+18h]
0x1800362ae  lea     rdx, [rsp+120h+lpMem]; struct _CERT_NAME_INFO **
0x1800362b3  add     rcx, 50h ; 'P'; struct _CRYPTOAPI_BLOB *
0x1800362b7  call    ?DecodeRdn@@YAHPEAU_CRYPTOAPI_BLOB@@PEAPEAU_CERT_NAME_INFO@@@Z; DecodeRdn(_CRYPTOAPI_BLOB *,_CERT_NAME_INFO * *)
0x1800362bc  test    eax, eax
0x1800362be  jnz     short loc_1800362E2
0x1800362c0  xor     r9d, r9d; int
0x1800362c3  lea     r8d, [rbx+64h]; unsigned int
0x1800362c7  mov     edx, 1964h; unsigned int
0x1800362cc  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x1800362d3  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x1800362d8  mov     eax, 80004005h
0x1800362dd  jmp     loc_1800365BE
0x1800362e2  xor     edx, edx; int
0x1800362e4  lea     rcx, [rsp+120h+var_E0]; this
0x1800362e9  lea     r8d, [rdx+1]; int
0x1800362ed  call    ?ReserveRange@XBF@@QEAAPEADHH@Z; XBF::ReserveRange(int,int)
0x1800362f2  mov     r15, [rsp+120h+lpMem]
0x1800362f7  lea     rdx, [rsp+120h+var_E0]; struct XBF *
0x1800362fc  mov     rcx, r15; struct _CERT_NAME_INFO *
0x1800362ff  mov     rbx, rax
0x180036302  call    ?BuildRdnList@@YAHPEAU_CERT_NAME_INFO@@PEAVXBF@@H@Z; BuildRdnList(_CERT_NAME_INFO *,XBF *,int)
0x180036307  test    eax, eax
0x180036309  jz      loc_1800361E9
0x18003630f  mov     [rsp+120h+var_F0], r14d
0x180036314  lea     rax, [rsp+120h+var_E0]
0x180036319  mov     dword ptr [rsp+120h+var_F8], 0
0x180036321  lea     r8, aSubject; "SUBJECT"
0x180036328  mov     r9, rbx
0x18003632b  mov     qword ptr [rsp+120h+var_100], rax
0x180036330  mov     rcx, rdi
0x180036333  call    ?AddStringPair@CCertRequest@@QEAAJW4CollectionType@@PEAD1PEAVXBF@@HI@Z; CCertRequest::AddStringPair(CollectionType,char *,char *,XBF *,int,uint)
0x180036338  mov     ebx, eax
0x18003633a  test    eax, eax
0x18003633c  jnz     loc_180036575
0x180036342  mov     r9, [rsi+18h]
0x180036346  lea     rax, [rsp+120h+var_E0]
0x18003634b  mov     [rsp+120h+var_F0], r14d
0x180036350  lea     r8, aBinarysubject; "BINARYSUBJECT"
0x180036357  mov     [rsp+120h+var_F8], rax
0x18003635c  mov     rcx, rdi
0x18003635f  mov     eax, [r9+50h]
0x180036363  mov     r9, [r9+58h]
0x180036367  mov     [rsp+120h+var_100], eax
0x18003636b  call    ?AddUuBinaryPair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAEKPEAVXBF@@I@Z; CCertRequest::AddUuBinaryPair(CollectionType,char *,uchar *,ulong,XBF *,uint)
0x180036370  mov     ebx, eax
0x180036372  test    eax, eax
0x180036374  jnz     loc_180036575
0x18003637a  lea     r9, [rsp+120h+var_E0]; struct XBF *
0x18003637f  mov     [rsp+120h+var_100], r14d; unsigned int
0x180036384  lea     r8, aSubject; "SUBJECT"
0x18003638b  mov     rdx, r15; struct _CERT_NAME_INFO *
0x18003638e  mov     rcx, rdi; this
0x180036391  call    ?ParseRDNS@CCertRequest@@QEAAJPEAU_CERT_NAME_INFO@@PEADPEAVXBF@@I@Z; CCertRequest::ParseRDNS(_CERT_NAME_INFO *,char *,XBF *,uint)
0x180036396  mov     ebx, eax
0x180036398  test    eax, eax
0x18003639a  jnz     loc_180036575
0x1800363a0  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800363a7  mov     r8, r15; lpMem
0x1800363aa  xor     edx, edx; dwFlags
0x1800363ac  call    cs:__imp_HeapFree
0x1800363b2  mov     r9, [rsi+8]
0x1800363b6  lea     rax, [rsp+120h+var_E0]
0x1800363bb  mov     [rsp+120h+var_F0], r14d
0x1800363c0  lea     r8, aCertificate_1; "CERTIFICATE"
0x1800363c7  mov     [rsp+120h+var_F8], rax
0x1800363cc  mov     rcx, rdi
0x1800363cf  mov     eax, [rsi+10h]
0x1800363d2  mov     [rsp+120h+var_100], eax
0x1800363d6  call    ?AddBinaryPair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAEKPEAVXBF@@I@Z; CCertRequest::AddBinaryPair(CollectionType,char *,uchar *,ulong,XBF *,uint)
0x1800363db  mov     ebx, eax
0x1800363dd  test    eax, eax
0x1800363df  jnz     loc_180036575
0x1800363e5  mov     rcx, [rsi+18h]
0x1800363e9  mov     eax, [rcx+8]
0x1800363ec  lea     r10d, [rax-1]
0x1800363f0  cmp     r10d, 28h ; '('
0x1800363f4  ja      loc_180036575
0x1800363fa  test    eax, eax
0x1800363fc  jz      short loc_180036471
0x1800363fe  xor     r9d, r9d
0x180036401  lea     r11, a0123456789abcd_0; "0123456789abcdef"
0x180036408  mov     eax, r10d
0x18003640b  sub     eax, r9d
0x18003640e  lea     r8d, [rax+rax*2]
0x180036412  mov     rax, [rcx+10h]
0x180036416  movzx   eax, byte ptr [rax+r9]
0x18003641b  shr     rax, 4
0x18003641f  mov     al, [rax+r11]
0x180036423  mov     [rbp+r8+47h+var_C0], al
0x180036428  mov     rax, [rsi+18h]
0x18003642c  mov     rcx, [rax+10h]
0x180036430  movzx   edx, byte ptr [rcx+r9]
0x180036435  lea     ecx, [r8+1]
0x180036439  and     edx, 0Fh
0x18003643c  mov     al, [rdx+r11]
0x180036440  mov     [rbp+rcx+47h+var_C0], al
0x180036444  lea     ecx, [r8+2]
0x180036448  test    r9d, r9d
0x18003644b  jz      short loc_180036451
0x18003644d  mov     al, 2Dh ; '-'
0x18003644f  jmp     short loc_180036460
0x180036451  cmp     rcx, 80h
0x180036458  jnb     loc_1800365DA
0x18003645e  xor     al, al
0x180036460  mov     [rbp+rcx+47h+var_C0], al
0x180036464  inc     r9d
0x180036467  mov     rcx, [rsi+18h]
0x18003646b  cmp     r9d, [rcx+8]
0x18003646f  jb      short loc_180036408
0x180036471  mov     [rsp+120h+var_F0], r14d
0x180036476  lea     rax, [rsp+120h+var_E0]
0x18003647b  mov     dword ptr [rsp+120h+var_F8], 1
0x180036483  lea     r9, [rbp+47h+var_C0]
0x180036487  lea     r8, aSerialnumber; "SERIALNUMBER"
0x18003648e  mov     qword ptr [rsp+120h+var_100], rax
0x180036493  mov     rcx, rdi
0x180036496  call    ?AddStringPair@CCertRequest@@QEAAJW4CollectionType@@PEAD1PEAVXBF@@HI@Z; CCertRequest::AddStringPair(CollectionType,char *,char *,XBF *,int,uint)
0x18003649b  mov     ebx, eax
0x18003649d  test    eax, eax
0x18003649f  jnz     loc_180036575
0x1800364a5  mov     r9, [rsi+18h]
0x1800364a9  lea     rax, [rsp+120h+var_E0]
0x1800364ae  mov     [rsp+120h+var_F0], r14d
0x1800364b3  lea     r8, aPublickey; "PUBLICKEY"
0x1800364ba  mov     [rsp+120h+var_F8], rax
0x1800364bf  mov     rcx, rdi
0x1800364c2  mov     eax, [r9+78h]
0x1800364c6  mov     r9, [r9+80h]
0x1800364cd  mov     [rsp+120h+var_100], eax
0x1800364d1  call    ?AddBinaryPair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAEKPEAVXBF@@I@Z; CCertRequest::AddBinaryPair(CollectionType,char *,uchar *,ulong,XBF *,uint)
0x1800364d6  mov     ebx, eax
0x1800364d8  test    eax, eax
0x1800364da  jnz     loc_180036575
0x1800364e0  mov     r9, [rsi+18h]
0x1800364e4  lea     rax, [rsp+120h+var_E0]
0x1800364e9  add     r9, 40h ; '@'
0x1800364ed  mov     qword ptr [rsp+120h+var_100], rax
0x1800364f2  lea     r8, aValidfrom; "VALIDFROM"
0x1800364f9  mov     rcx, rdi
0x1800364fc  call    ?AddDatePair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAU_FILETIME@@PEAVXBF@@@Z; CCertRequest::AddDatePair(CollectionType,char *,_FILETIME *,XBF *)
0x180036501  mov     ebx, eax
0x180036503  test    eax, eax
0x180036505  jnz     short loc_180036575
0x180036507  mov     r9, [rsi+18h]
0x18003650b  lea     rax, [rsp+120h+var_E0]
0x180036510  add     r9, 48h ; 'H'
0x180036514  mov     qword ptr [rsp+120h+var_100], rax
0x180036519  lea     r8, aValiduntil; "VALIDUNTIL"
0x180036520  mov     rcx, rdi
0x180036523  call    ?AddDatePair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAU_FILETIME@@PEAVXBF@@@Z; CCertRequest::AddDatePair(CollectionType,char *,_FILETIME *,XBF *)
0x180036528  mov     ebx, eax
0x18003652a  test    eax, eax
0x18003652c  jnz     short loc_180036575
0x18003652e  lea     rax, [rsp+120h+var_E0]
0x180036533  mov     rcx, rdi
0x180036536  lea     r9, [rbp+47h+arg_20]
0x18003653a  mov     qword ptr [rsp+120h+var_100], rax
0x18003653f  lea     r8, aFlags; "FLAGS"
0x180036546  call    ?AddDwordPair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAKPEAVXBF@@@Z; CCertRequest::AddDwordPair(CollectionType,char *,ulong *,XBF *)
0x18003654b  mov     ebx, eax
0x18003654d  test    eax, eax
0x18003654f  jnz     short loc_180036575
0x180036551  lea     rax, [rsp+120h+var_E0]
0x180036556  mov     rcx, rdi
0x180036559  lea     r9, [rsp+120h+var_C8]
0x18003655e  mov     qword ptr [rsp+120h+var_100], rax
0x180036563  lea     r8, aEncoding; "ENCODING"
0x18003656a  call    ?AddDwordPair@CCertRequest@@QEAAJW4CollectionType@@PEADPEAKPEAVXBF@@@Z; CCertRequest::AddDwordPair(CollectionType,char *,ulong *,XBF *)
0x18003656f  mov     ebx, eax
0x180036571  test    eax, eax
  ... truncated ...
```
