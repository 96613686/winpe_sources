# P2PCertificatesHelper::AclCertificateForNetworkService(AadContextFunctions *,CertificateContext &)

- ea: `0x18004e2b8`
- end: `0x18004e671`
- name: `?AclCertificateForNetworkService@P2PCertificatesHelper@@SAJPEAVAadContextFunctions@@AEAVCertificateContext@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, PCCERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180031f04`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18004e2b8`
- `0x18004edec`
- `0x180050674`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e556`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004e467`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004e467`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004e54c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004e54c`
- `ncrypt!NCryptFreeObject` at `0x18004e638`
- `ncrypt!NCryptFreeObject` at `0x18004e638`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18004e37a`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18004e37a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004e4f3`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004e4f3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18004e642`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18004e642`

## string_xrefs

- `0x18004e308`: `P2PCertificatesHelper::AclCertificateForNetworkService`

## pseudocode

```c
__int64 __fastcall P2PCertificatesHelper::AclCertificateForNetworkService(
        struct AadContextFunctions *a1,
        PCCERT_CONTEXT *a2)
{
  PSECURITY_DESCRIPTOR v4; // rsi
  int v5; // ecx
  signed int LastError; // eax
  signed int v7; // ebx
  int SecurityDescriptor; // ecx
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  unsigned int v12; // ebx
  DWORD *pdwKeySpec; // [rsp+20h] [rbp-99h]
  int v15; // [rsp+30h] [rbp-89h]
  int v16; // [rsp+30h] [rbp-89h]
  DWORD v17; // [rsp+50h] [rbp-69h] BYREF
  PACL NewAcl; // [rsp+58h] [rbp-61h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+60h] [rbp-59h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+68h] [rbp-51h] BYREF
  WINBOOL bDaclPresent; // [rsp+6Ch] [rbp-4Dh] BYREF
  DWORD dwRevision; // [rsp+70h] [rbp-49h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-41h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-39h] BYREF
  const char *v25[12]; // [rsp+B0h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+120h] [rbp+67h] BYREF
  unsigned int v27; // [rsp+130h] [rbp+77h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+138h] [rbp+7Fh] BYREF

  v27 = 0;
  v4 = 0;
  pSecurityDescriptor = 0;
  phCryptProvOrNCryptKey = 0;
  v17 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  NewAcl = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v25,
    (int)"p2pcertificateshelper.cpp",
    (int)"P2PCertificatesHelper::AclCertificateForNetworkService",
    (int)&v27);
  if ( !a1 )
  {
    v5 = -1073741811;
    v27 = -1073741811;
    v15 = 672;
    goto LABEL_29;
  }
  if ( !CryptAcquireCertificatePrivateKey(*a2, 0x10044u, 0, &phCryptProvOrNCryptKey, &v17, &pfCallerFreeProvOrNCryptKey) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      v16 = 677;
LABEL_8:
      LODWORD(pdwKeySpec) = v7;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pdwKeySpec, "p2pcertificateshelper.cpp", v16, "HRESULT", &base);
      v27 = v7 & 0xAFFFFFFF | 0x40000000;
      goto LABEL_30;
    }
  }
  SecurityDescriptor = P2PCertificatesHelper::GetSecurityDescriptor(a1, phCryptProvOrNCryptKey, &pSecurityDescriptor);
  v27 = SecurityDescriptor;
  if ( SecurityDescriptor < 0 )
  {
    LODWORD(pdwKeySpec) = SecurityDescriptor;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pdwKeySpec, "p2pcertificateshelper.cpp", 680, "NTSTATUS", &base);
    v4 = pSecurityDescriptor;
    goto LABEL_30;
  }
  v4 = pSecurityDescriptor;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 < 0 )
    {
      v16 = 684;
      goto LABEL_8;
    }
  }
  if ( !pDacl )
    goto LABEL_30;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
  pListOfExplicitEntries.grfAccessPermissions = 1179785;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)qword_1800E5400;
  v10 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( v7 < 0 )
  {
    v16 = 702;
    goto LABEL_8;
  }
  if ( !NewAcl )
    goto LABEL_32;
  LOWORD(pSecurityDescriptor) = 0;
  dwRevision = 0;
  if ( !GetSecurityDescriptorControl(v4, (PSECURITY_DESCRIPTOR_CONTROL)&pSecurityDescriptor, &dwRevision) )
  {
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 < 0 )
    {
      v16 = 711;
      goto LABEL_8;
    }
  }
  v5 = P2PCertificatesHelper::SetSecurityDescriptor(
         a1,
         phCryptProvOrNCryptKey,
         NewAcl,
         ((unsigned __int16)pSecurityDescriptor & 0x1000) != 0);
  v27 = v5;
  if ( v5 >= 0 )
    goto LABEL_30;
  v15 = 716;
LABEL_29:
  LODWORD(pdwKeySpec) = v5;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pdwKeySpec, "p2pcertificateshelper.cpp", v15, "NTSTATUS", &base);
LABEL_30:
  if ( NewAcl )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
LABEL_32:
  if ( v4 )
    (*(void (__fastcall **)(struct AadContextFunctions *, PSECURITY_DESCRIPTOR))(*(_QWORD *)a1 + 16LL))(a1, v4);
  if ( pfCallerFreeProvOrNCryptKey && phCryptProvOrNCryptKey )
  {
    if ( v17 == -1 )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  }
  v12 = v27;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v25);
  return v12;
}

```

## disassembly

```asm
0x18004e2b8  mov     [rsp-8+arg_8], rbx
0x18004e2bd  push    rbp
0x18004e2be  push    rsi
0x18004e2bf  push    rdi
0x18004e2c0  push    r12
0x18004e2c2  push    r13
0x18004e2c4  push    r14
0x18004e2c6  push    r15
0x18004e2c8  lea     rbp, [rsp-27h]
0x18004e2cd  sub     rsp, 0E0h
0x18004e2d4  mov     rbx, rdx
0x18004e2d7  mov     r14, rcx
0x18004e2da  xor     r15d, r15d
0x18004e2dd  mov     [rbp+57h+arg_10], r15d
0x18004e2e1  mov     esi, r15d
0x18004e2e4  mov     [rbp+57h+pSecurityDescriptor], r15
0x18004e2e8  mov     [rbp+57h+phCryptProvOrNCryptKey], r15
0x18004e2ec  mov     [rbp+57h+var_C0], r15d
0x18004e2f0  mov     [rbp+57h+arg_18], r15d
0x18004e2f4  mov     [rbp+57h+bDaclPresent], r15d
0x18004e2f8  mov     [rbp+57h+bDaclDefaulted], r15d
0x18004e2fc  mov     [rbp+57h+pDacl], r15
0x18004e300  mov     [rbp+57h+NewAcl], r15
0x18004e304  lea     r9, [rbp+57h+arg_10]
0x18004e308  lea     r8, aP2pcertificate_2; "P2PCertificatesHelper::AclCertificateFo"...
0x18004e30f  lea     r13, aOnecoreuapDsEx_12+21h; "p2pcertificateshelper.cpp"
0x18004e316  mov     rdx, r13
0x18004e319  lea     rcx, [rbp+57h+var_60]
0x18004e31d  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004e322  nop
0x18004e323  test    r14, r14
0x18004e326  jnz     short loc_18004E359
0x18004e328  mov     ecx, 0C000000Dh
0x18004e32d  mov     [rbp+57h+arg_10], ecx
0x18004e330  lea     rax, base
0x18004e337  mov     [rsp+110h+var_D0], rax
0x18004e33c  lea     rax, aNtstatus; "NTSTATUS"
0x18004e343  mov     [rsp+110h+var_D8], rax
0x18004e348  mov     [rsp+110h+var_E0], 2A0h
0x18004e350  lea     edi, [r15+2]
0x18004e354  jmp     loc_18004E5D8
0x18004e359  lea     rax, [rbp+57h+arg_18]
0x18004e35d  mov     [rsp+110h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x18004e362  lea     rax, [rbp+57h+var_C0]
0x18004e366  mov     [rsp+110h+pdwKeySpec], rax; pdwKeySpec
0x18004e36b  lea     r9, [rbp+57h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18004e36f  xor     r8d, r8d; pvParameters
0x18004e372  mov     edx, 10044h; dwFlags
0x18004e377  mov     rcx, [rbx]; pCert
0x18004e37a  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x18004e380  mov     r12d, 80070000h
0x18004e386  test    eax, eax
0x18004e388  jnz     short loc_18004E3F1
0x18004e38a  call    cs:__imp_GetLastError
0x18004e390  mov     ebx, eax
0x18004e392  test    eax, eax
0x18004e394  jle     short loc_18004E39C
0x18004e396  movzx   ebx, ax
0x18004e399  or      ebx, r12d
0x18004e39c  test    ebx, ebx
0x18004e39e  jns     short loc_18004E3F1
0x18004e3a0  lea     rax, base
0x18004e3a7  mov     [rsp+110h+var_D0], rax
0x18004e3ac  lea     rax, aHresult; "HRESULT"
0x18004e3b3  mov     [rsp+110h+var_D8], rax
0x18004e3b8  mov     [rsp+110h+var_E0], 2A5h
0x18004e3c0  mov     edi, 2
0x18004e3c5  mov     [rsp+110h+pfCallerFreeProvOrNCryptKey], r13
0x18004e3ca  mov     dword ptr [rsp+110h+pdwKeySpec], ebx
0x18004e3ce  mov     r9d, edi
0x18004e3d1  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004e3d8  xor     edx, edx
0x18004e3da  mov     ecx, edi
0x18004e3dc  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004e3e1  btr     ebx, 1Ch
0x18004e3e5  bts     ebx, 1Eh
0x18004e3e9  mov     [rbp+57h+arg_10], ebx
0x18004e3ec  jmp     loc_18004E5F4
0x18004e3f1  lea     r8, [rbp+57h+pSecurityDescriptor]; void **
0x18004e3f5  mov     rdx, [rbp+57h+phCryptProvOrNCryptKey]; unsigned __int64
0x18004e3f9  mov     rcx, r14; struct AadContextFunctions *
0x18004e3fc  call    ?GetSecurityDescriptor@P2PCertificatesHelper@@CAJPEAVAadContextFunctions@@_KPEAPEAX@Z; P2PCertificatesHelper::GetSecurityDescriptor(AadContextFunctions *,unsigned __int64,void * *)
0x18004e401  mov     ecx, eax
0x18004e403  mov     [rbp+57h+arg_10], eax
0x18004e406  test    eax, eax
0x18004e408  jns     short loc_18004E454
0x18004e40a  lea     rax, base
0x18004e411  mov     [rsp+110h+var_D0], rax
0x18004e416  lea     rax, aNtstatus; "NTSTATUS"
0x18004e41d  mov     [rsp+110h+var_D8], rax
0x18004e422  mov     [rsp+110h+var_E0], 2A8h
0x18004e42a  mov     [rsp+110h+pfCallerFreeProvOrNCryptKey], r13
0x18004e42f  mov     dword ptr [rsp+110h+pdwKeySpec], ecx
0x18004e433  mov     edi, 2
0x18004e438  mov     r9d, edi
0x18004e43b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004e442  xor     edx, edx
0x18004e444  mov     ecx, edi
0x18004e446  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004e44b  mov     rsi, [rbp+57h+pSecurityDescriptor]
0x18004e44f  jmp     loc_18004E5F4
0x18004e454  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18004e458  lea     r8, [rbp+57h+pDacl]; pDacl
0x18004e45c  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18004e460  mov     rsi, [rbp+57h+pSecurityDescriptor]
0x18004e464  mov     rcx, rsi; pSecurityDescriptor
0x18004e467  call    cs:__imp_GetSecurityDescriptorDacl
0x18004e46d  test    eax, eax
0x18004e46f  jnz     short loc_18004E4AC
0x18004e471  call    cs:__imp_GetLastError
0x18004e477  mov     ebx, eax
0x18004e479  test    eax, eax
0x18004e47b  jle     short loc_18004E483
0x18004e47d  movzx   ebx, ax
0x18004e480  or      ebx, r12d
0x18004e483  test    ebx, ebx
0x18004e485  jns     short loc_18004E4AC
0x18004e487  lea     rax, base
0x18004e48e  mov     [rsp+110h+var_D0], rax
0x18004e493  lea     rax, aHresult; "HRESULT"
0x18004e49a  mov     [rsp+110h+var_D8], rax
0x18004e49f  mov     [rsp+110h+var_E0], 2ACh
0x18004e4a7  jmp     loc_18004E3C0
0x18004e4ac  mov     r8, [rbp+57h+pDacl]; OldAcl
0x18004e4b0  test    r8, r8
0x18004e4b3  jz      loc_18004E5F4
0x18004e4b9  xorps   xmm0, xmm0
0x18004e4bc  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x18004e4c1  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18004e4c9  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 120089h
0x18004e4d0  mov     edi, 2
0x18004e4d5  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], rdi
0x18004e4d9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x18004e4dd  lea     ecx, [rdi-1]; cCountOfExplicitEntries
0x18004e4e0  lea     rax, qword_1800E5400
0x18004e4e7  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18004e4eb  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18004e4ef  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004e4f3  call    cs:__imp_SetEntriesInAclW
0x18004e4f9  mov     ebx, eax
0x18004e4fb  test    eax, eax
0x18004e4fd  jle     short loc_18004E505
0x18004e4ff  movzx   ebx, ax
0x18004e502  or      ebx, r12d
0x18004e505  test    ebx, ebx
0x18004e507  jns     short loc_18004E52E
0x18004e509  lea     rax, base
0x18004e510  mov     [rsp+110h+var_D0], rax
0x18004e515  lea     rax, aHresult; "HRESULT"
0x18004e51c  mov     [rsp+110h+var_D8], rax
0x18004e521  mov     [rsp+110h+var_E0], 2BEh
0x18004e529  jmp     loc_18004E3C5
0x18004e52e  cmp     [rbp+57h+NewAcl], r15
0x18004e532  jz      loc_18004E60C
0x18004e538  mov     word ptr [rbp+57h+pSecurityDescriptor], r15w
0x18004e53d  mov     [rbp+57h+dwRevision], r15d
0x18004e541  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18004e545  lea     rdx, [rbp+57h+pSecurityDescriptor]; pControl
0x18004e549  mov     rcx, rsi; pSecurityDescriptor
0x18004e54c  call    cs:__imp_GetSecurityDescriptorControl
0x18004e552  test    eax, eax
0x18004e554  jnz     short loc_18004E591
0x18004e556  call    cs:__imp_GetLastError
0x18004e55c  mov     ebx, eax
0x18004e55e  test    eax, eax
0x18004e560  jle     short loc_18004E568
0x18004e562  movzx   ebx, ax
0x18004e565  or      ebx, r12d
0x18004e568  test    ebx, ebx
0x18004e56a  jns     short loc_18004E591
0x18004e56c  lea     rax, base
0x18004e573  mov     [rsp+110h+var_D0], rax
0x18004e578  lea     rax, aHresult; "HRESULT"
0x18004e57f  mov     [rsp+110h+var_D8], rax
0x18004e584  mov     [rsp+110h+var_E0], 2C7h
0x18004e58c  jmp     loc_18004E3C5
0x18004e591  movzx   r9d, word ptr [rbp+57h+pSecurityDescriptor]
0x18004e596  shr     r9w, 0Ch
0x18004e59b  and     r9b, 1; bool
0x18004e59f  mov     r8, [rbp+57h+NewAcl]; struct _ACL *
0x18004e5a3  mov     rdx, [rbp+57h+phCryptProvOrNCryptKey]; unsigned __int64
0x18004e5a7  mov     rcx, r14; struct AadContextFunctions *
0x18004e5aa  call    ?SetSecurityDescriptor@P2PCertificatesHelper@@CAJPEAVAadContextFunctions@@_KQEAU_ACL@@_N@Z; P2PCertificatesHelper::SetSecurityDescriptor(AadContextFunctions *,unsigned __int64,_ACL * const,bool)
0x18004e5af  mov     ecx, eax
0x18004e5b1  mov     [rbp+57h+arg_10], eax
0x18004e5b4  test    eax, eax
0x18004e5b6  jns     short loc_18004E5F4
0x18004e5b8  lea     rax, base
0x18004e5bf  mov     [rsp+110h+var_D0], rax
0x18004e5c4  lea     rax, aNtstatus; "NTSTATUS"
0x18004e5cb  mov     [rsp+110h+var_D8], rax
0x18004e5d0  mov     [rsp+110h+var_E0], 2CCh
0x18004e5d8  mov     [rsp+110h+pfCallerFreeProvOrNCryptKey], r13
0x18004e5dd  mov     dword ptr [rsp+110h+pdwKeySpec], ecx
0x18004e5e1  mov     r9d, edi
0x18004e5e4  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004e5eb  xor     edx, edx
0x18004e5ed  mov     ecx, edi
0x18004e5ef  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004e5f4  mov     rdx, [rbp+57h+NewAcl]
0x18004e5f8  test    rdx, rdx
0x18004e5fb  jz      short loc_18004E60C
0x18004e5fd  mov     rax, [r14]
0x18004e600  mov     rcx, r14
0x18004e603  mov     rax, [rax+10h]
0x18004e607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e60c  test    rsi, rsi
0x18004e60f  jz      short loc_18004E623
0x18004e611  mov     rax, [r14]
0x18004e614  mov     rdx, rsi
0x18004e617  mov     rcx, r14
0x18004e61a  mov     rax, [rax+10h]
0x18004e61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e623  cmp     [rbp+57h+arg_18], r15d
0x18004e627  jz      short loc_18004E648
0x18004e629  mov     rcx, [rbp+57h+phCryptProvOrNCryptKey]; hProv
0x18004e62d  test    rcx, rcx
0x18004e630  jz      short loc_18004E648
0x18004e632  cmp     [rbp+57h+var_C0], 0FFFFFFFFh
0x18004e636  jnz     short loc_18004E640
0x18004e638  call    cs:__imp_NCryptFreeObject
0x18004e63e  jmp     short loc_18004E648
0x18004e640  xor     edx, edx; dwFlags
0x18004e642  call    cs:__imp_CryptReleaseContext
0x18004e648  mov     ebx, [rbp+57h+arg_10]
0x18004e64b  lea     rcx, [rbp+57h+var_60]
0x18004e64f  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004e654  mov     eax, ebx
0x18004e656  mov     rbx, [rsp+110h+arg_8]
0x18004e65e  add     rsp, 0E0h
0x18004e665  pop     r15
0x18004e667  pop     r14
0x18004e669  pop     r13
0x18004e66b  pop     r12
0x18004e66d  pop     rdi
0x18004e66e  pop     rsi
0x18004e66f  pop     rbp
0x18004e670  retn
```
