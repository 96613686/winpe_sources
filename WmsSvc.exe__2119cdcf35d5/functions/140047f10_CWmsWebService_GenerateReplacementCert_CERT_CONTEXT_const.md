# CWmsWebService::GenerateReplacementCert(_CERT_CONTEXT const *)

- ea: `0x140047f10`
- end: `0x140048233`
- name: `?GenerateReplacementCert@CWmsWebService@@AEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `803`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140035ec0`
- `0x140046b60`
- `0x14004b218`

## callees

- `0x1400016b8`
- `0x14002b2ac`
- `0x14002ba9c`
- `0x140046d54`
- `0x140047f10`
- `0x140049494`
- `0x14004c738`
- `0x14004cbec`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063fd4`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140048043`
- `ADVAPI32!RegGetValueW` at `0x140048043`
- `ADVAPI32!RegSetKeyValueW` at `0x1400481bd`
- `ADVAPI32!RegSetKeyValueW` at `0x1400481bd`
- `KERNEL32!IsDebuggerPresent` at `0x140047f9c`
- `KERNEL32!IsDebuggerPresent` at `0x140047f9c`
- `CRYPT32!CertFreeCertificateContext` at `0x140048202`
- `CRYPT32!CertFreeCertificateContext` at `0x140048202`

## string_xrefs

- `0x140047f8a`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047faa`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047fdd`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400480b2`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047f70`: `CWmsWebService::GenerateReplacementCert`
- `0x1400480ab`: `CWmsWebService::GenerateReplacementCert`
- `0x140048099`: `Time is not yet right for generating a replacement SSL cert, do nothing.`
- `0x1400480ee`: `Replacement SSL cert already exists, do nothing.`
- `0x1400481d9`: `CWmsWebService::GenerateReplacementCert - Created cert thumprint %s\n`
- `0x1400481a7`: `ReplacementSslCertificateThumbprint`
- `0x140048014`: `SslCertificateReplacementWindowDays`

## pseudocode

```c
__int64 __fastcall CWmsWebService::GenerateReplacementCert(CWmsWebService *this, const struct _CERT_CONTEXT *a2)
{
  void *v4; // rdi
  signed int IsItTimeToGenerateCert; // ebx
  const unsigned __int16 *v6; // r13
  unsigned int v7; // r12d
  LSTATUS ValueW; // eax
  const wchar_t *v9; // rax
  __int64 v10; // r9
  int v11; // eax
  _WORD *v12; // rax
  __int64 v13; // rdx
  LSTATUS v14; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-40h]
  unsigned int v17; // [rsp+40h] [rbp-30h] BYREF
  LPCVOID lpData; // [rsp+48h] [rbp-28h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-20h] BYREF
  struct _CRYPTOAPI_BLOB Block; // [rsp+58h] [rbp-18h] BYREF
  DWORD v21; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int pvData; // [rsp+C0h] [rbp+50h] BYREF
  int v23; // [rsp+C8h] [rbp+58h] BYREF

  pvData = 120;
  v21 = 0;
  v17 = 0;
  v23 = 0;
  pCertContext = 0;
  v4 = 0;
  lpData = 0;
  Block = 0;
  if ( !a2 )
  {
    IsItTimeToGenerateCert = -2147024809;
    v6 = L"pCurrentCert != 0";
    v7 = 1570;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v7,
      L"CWmsWebService::GenerateReplacementCert",
      L"CBRAEx",
      v6,
      IsItTimeToGenerateCert);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v7,
        L"CWmsWebService::GenerateReplacementCert",
        L"CBRAEx",
        v6,
        IsItTimeToGenerateCert);
    }
    else
    {
      LODWORD(pcbData) = IsItTimeToGenerateCert;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v7,
        L"CWmsWebService::GenerateReplacementCert",
        L"CBRAEx",
        v6,
        pcbData);
    }
    goto LABEL_30;
  }
  v21 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
             L"SslCertificateReplacementWindowDays",
             0x10u,
             0,
             &pvData,
             &v21);
  IsItTimeToGenerateCert = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      IsItTimeToGenerateCert = (unsigned __int16)ValueW | 0x80070000;
    v6 = L"(lr == 0L) || (lr == 2L)";
    v7 = 1579;
    goto LABEL_3;
  }
  IsItTimeToGenerateCert = CWmsWebService::IsItTimeToGenerateCert(this, &a2->pCertInfo->NotAfter, pvData, &v23);
  if ( IsItTimeToGenerateCert < 0 )
    goto LABEL_30;
  if ( !v23 )
  {
    v9 = L"Time is not yet right for generating a replacement SSL cert, do nothing.";
    v10 = 1585;
LABEL_13:
    IsItTimeToGenerateCert = 0;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v10,
      L"CWmsWebService::GenerateReplacementCert",
      v9);
    goto LABEL_30;
  }
  IsItTimeToGenerateCert = CWmsWebService::s_DoesReplacementCertExist(&pCertContext);
  if ( IsItTimeToGenerateCert < 0 )
    goto LABEL_30;
  if ( pCertContext )
  {
    v9 = L"Replacement SSL cert already exists, do nothing.";
    v10 = 1591;
    goto LABEL_13;
  }
  IsItTimeToGenerateCert = CWmsWebService::s_GetCurrentCertKeyContainerIndex(&v17);
  if ( IsItTimeToGenerateCert >= 0 )
  {
    IsItTimeToGenerateCert = CWmsWebService::CreateSelfSignedSslCertificate(this, &Block, ((_BYTE)v17 - 1) & 1);
    if ( IsItTimeToGenerateCert >= 0 )
    {
      v11 = ConvertThumbprintBlobToString(&Block, (unsigned __int16 **)&lpData);
      v4 = (void *)lpData;
      IsItTimeToGenerateCert = v11;
      if ( v11 >= 0 )
      {
        if ( lpData )
        {
          v12 = lpData;
          v13 = 0x7FFFFFFF;
          do
          {
            if ( !*v12 )
              break;
            ++v12;
            --v13;
          }
          while ( v13 );
          IsItTimeToGenerateCert = v13 == 0 ? 0x80070057 : 0;
          if ( v13 )
          {
            v14 = RegSetKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                    L"ReplacementSslCertificateThumbprint",
                    1u,
                    lpData,
                    2 * (v13 != 0 ? 0x7FFFFFFF - v13 : 0) + 2);
            IsItTimeToGenerateCert = v14;
            if ( v14 )
            {
              if ( v14 > 0 )
                IsItTimeToGenerateCert = (unsigned __int16)v14 | 0x80070000;
            }
            else
            {
              DEBUGMSG(L"CWmsWebService::GenerateReplacementCert - Created cert thumprint %s\n", v4);
              CManagedServerNotificationThread::s_GiveManagersReplacementSslCert();
              CManagedServerNotificationThread::s_GiveManageesReplacementSslCert();
              IsItTimeToGenerateCert = 0;
            }
          }
        }
        else
        {
          IsItTimeToGenerateCert = -2147024809;
        }
      }
    }
  }
LABEL_30:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  operator delete(v4);
  operator delete(Block.pbData);
  return (unsigned int)IsItTimeToGenerateCert;
}

```

## disassembly

```asm
0x140047f10  mov     [rsp-38h+arg_0], rbx
0x140047f15  push    rbp
0x140047f16  push    rsi
0x140047f17  push    rdi
0x140047f18  push    r12
0x140047f1a  push    r13
0x140047f1c  push    r14
0x140047f1e  push    r15
0x140047f20  mov     rbp, rsp
0x140047f23  sub     rsp, 70h
0x140047f27  xor     r15d, r15d
0x140047f2a  mov     [rbp+arg_10], 78h ; 'x'
0x140047f31  mov     [rbp+arg_8], r15d
0x140047f35  xorps   xmm0, xmm0
0x140047f38  mov     [rbp+var_30], r15d
0x140047f3c  mov     rsi, rdx
0x140047f3f  mov     [rbp+arg_18], r15d
0x140047f43  mov     r14, rcx
0x140047f46  mov     [rbp+pCertContext], r15
0x140047f4a  mov     edi, r15d
0x140047f4d  mov     [rbp+lpData], r15
0x140047f51  movups  xmmword ptr [rbp+Block.cbData], xmm0
0x140047f55  test    rdx, rdx
0x140047f58  jnz     loc_140048005
0x140047f5e  mov     ebx, 80070057h
0x140047f63  lea     r13, aPcurrentcert0; "pCurrentCert != 0"
0x140047f6a  mov     r12d, 622h
0x140047f70  lea     rsi, aCwmswebservice_69; "CWmsWebService::GenerateReplacementCert"
0x140047f77  mov     dword ptr [rsp+70h+pvData], ebx; int
0x140047f7b  lea     r14, aCbraex; "CBRAEx"
0x140047f82  mov     [rsp+70h+pdwType], r13; unsigned __int16 *
0x140047f87  mov     r8, rsi; unsigned __int16 *
0x140047f8a  lea     rcx, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140047f91  mov     r9, r14; unsigned __int16 *
0x140047f94  mov     edx, r12d; unsigned int
0x140047f97  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140047f9c  call    cs:__imp_IsDebuggerPresent
0x140047fa2  test    eax, eax
0x140047fa4  jz      short loc_140047FD9
0x140047fa6  mov     [rsp+70h+var_38], ebx
0x140047faa  lea     r8, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140047fb1  mov     [rsp+70h+pcbData], r13
0x140047fb6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140047fbd  mov     [rsp+70h+pvData], r14
0x140047fc2  mov     r9d, r12d
0x140047fc5  mov     ecx, 2; unsigned __int8
0x140047fca  mov     [rsp+70h+pdwType], rsi
0x140047fcf  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140047fd4  jmp     loc_1400481F9
0x140047fd9  mov     dword ptr [rsp+70h+pcbData], ebx
0x140047fdd  lea     rdx, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140047fe4  mov     [rsp+70h+pvData], r13
0x140047fe9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140047ff0  mov     r9, rsi
0x140047ff3  mov     [rsp+70h+pdwType], r14
0x140047ff8  mov     r8d, r12d
0x140047ffb  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140048000  jmp     loc_1400481F9
0x140048005  mov     r12d, 4
0x14004800b  lea     rax, [rbp+arg_8]
0x14004800f  mov     [rsp+70h+pcbData], rax; pcbData
0x140048014  lea     r8, aSslcertificate_0; "SslCertificateReplacementWindowDays"
0x14004801b  lea     rax, [rbp+arg_10]
0x14004801f  mov     [rbp+arg_8], r12d
0x140048023  mov     [rsp+70h+pvData], rax; pvData
0x140048028  lea     rdx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14004802f  mov     r13, 0FFFFFFFF80000002h
0x140048036  mov     [rsp+70h+pdwType], r15; pdwType
0x14004803b  lea     r9d, [r12+0Ch]; dwFlags
0x140048040  mov     rcx, r13; hkey
0x140048043  call    cs:__imp_RegGetValueW
0x140048049  mov     ebx, eax
0x14004804b  test    eax, 0FFFFFFFDh
0x140048050  jz      short loc_140048071
0x140048052  test    eax, eax
0x140048054  jle     short loc_14004805F
0x140048056  movzx   ebx, ax
0x140048059  or      ebx, 80070000h
0x14004805f  lea     r13, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x140048066  mov     r12d, 62Bh
0x14004806c  jmp     loc_140047F70
0x140048071  mov     rdx, [rsi+18h]
0x140048075  lea     r9, [rbp+arg_18]; int *
0x140048079  mov     r8d, [rbp+arg_10]; unsigned int
0x14004807d  add     rdx, 48h ; 'H'; struct _FILETIME *
0x140048081  mov     rcx, r14; this
0x140048084  call    ?IsItTimeToGenerateCert@CWmsWebService@@AEAAJPEBU_FILETIME@@KPEAH@Z; CWmsWebService::IsItTimeToGenerateCert(_FILETIME const *,ulong,int *)
0x140048089  mov     ebx, eax
0x14004808b  test    eax, eax
0x14004808d  js      loc_1400481F9
0x140048093  cmp     [rbp+arg_18], r15d
0x140048097  jnz     short loc_1400480D5
0x140048099  lea     rax, aTimeIsNotYetRi; "Time is not yet right for generating a "...
0x1400480a0  mov     r9d, 631h
0x1400480a6  mov     [rsp+70h+pvData], rax
0x1400480ab  lea     rsi, aCwmswebservice_69; "CWmsWebService::GenerateReplacementCert"
0x1400480b2  lea     r8, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400480b9  mov     [rsp+70h+pdwType], rsi
0x1400480be  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x1400480c5  mov     ecx, r12d; unsigned __int8
0x1400480c8  mov     ebx, r15d
0x1400480cb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400480d0  jmp     loc_1400481F9
0x1400480d5  lea     rcx, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x1400480d9  call    ?s_DoesReplacementCertExist@CWmsWebService@@SAJPEAPEBU_CERT_CONTEXT@@@Z; CWmsWebService::s_DoesReplacementCertExist(_CERT_CONTEXT const * *)
0x1400480de  mov     ebx, eax
0x1400480e0  test    eax, eax
0x1400480e2  js      loc_1400481F9
0x1400480e8  cmp     [rbp+pCertContext], r15
0x1400480ec  jz      short loc_1400480FD
0x1400480ee  lea     rax, aReplacementSsl; "Replacement SSL cert already exists, do"...
0x1400480f5  mov     r9d, 637h
0x1400480fb  jmp     short loc_1400480A6
0x1400480fd  lea     rcx, [rbp+var_30]; unsigned int *
0x140048101  call    ?s_GetCurrentCertKeyContainerIndex@CWmsWebService@@CAJPEAK@Z; CWmsWebService::s_GetCurrentCertKeyContainerIndex(ulong *)
0x140048106  mov     ebx, eax
0x140048108  test    eax, eax
0x14004810a  js      loc_1400481F9
0x140048110  mov     r8d, [rbp+var_30]
0x140048114  lea     rdx, [rbp+Block]; struct _CRYPTOAPI_BLOB *
0x140048118  dec     r8d
0x14004811b  mov     rcx, r14; this
0x14004811e  and     r8d, 1; unsigned int
0x140048122  call    ?CreateSelfSignedSslCertificate@CWmsWebService@@AEAAJPEAU_CRYPTOAPI_BLOB@@K@Z; CWmsWebService::CreateSelfSignedSslCertificate(_CRYPTOAPI_BLOB *,ulong)
0x140048127  mov     ebx, eax
0x140048129  test    eax, eax
0x14004812b  js      loc_1400481F9
0x140048131  lea     rdx, [rbp+lpData]; unsigned __int16 **
0x140048135  lea     rcx, [rbp+Block]; struct _CRYPTOAPI_BLOB *
0x140048139  call    ?ConvertThumbprintBlobToString@@YAJPEAU_CRYPTOAPI_BLOB@@PEAPEAG@Z; ConvertThumbprintBlobToString(_CRYPTOAPI_BLOB *,ushort * *)
0x14004813e  mov     rdi, [rbp+lpData]
0x140048142  mov     ebx, eax
0x140048144  test    eax, eax
0x140048146  js      loc_1400481F9
0x14004814c  test    rdi, rdi
0x14004814f  jz      loc_1400481F4
0x140048155  mov     r8d, 7FFFFFFFh
0x14004815b  mov     rax, rdi
0x14004815e  mov     edx, r8d
0x140048161  cmp     [rax], r15w
0x140048165  jz      short loc_140048171
0x140048167  add     rax, 2
0x14004816b  sub     rdx, 1
0x14004816f  jnz     short loc_140048161
0x140048171  mov     rax, rdx
0x140048174  mov     ebx, 80070057h
0x140048179  neg     rax
0x14004817c  mov     rax, rdx
0x14004817f  sbb     ecx, ecx
0x140048181  sub     r8, rdx
0x140048184  not     ecx
0x140048186  and     ebx, ecx
0x140048188  neg     rax
0x14004818b  sbb     rax, rax
0x14004818e  and     rax, r8
0x140048191  test    rdx, rdx
0x140048194  jz      short loc_1400481F9
0x140048196  lea     eax, ds:2[rax*2]
0x14004819d  mov     r9d, 1; dwType
0x1400481a3  mov     dword ptr [rsp+70h+pvData], eax; cbData
0x1400481a7  lea     r8, aReplacementssl; "ReplacementSslCertificateThumbprint"
0x1400481ae  lea     rdx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x1400481b5  mov     [rsp+70h+pdwType], rdi; lpData
0x1400481ba  mov     rcx, r13; hKey
0x1400481bd  call    cs:__imp_RegSetKeyValueW
0x1400481c3  mov     ebx, eax
0x1400481c5  test    eax, eax
0x1400481c7  jz      short loc_1400481D6
0x1400481c9  jle     short loc_1400481F9
0x1400481cb  movzx   ebx, ax
0x1400481ce  or      ebx, 80070000h
0x1400481d4  jmp     short loc_1400481F9
0x1400481d6  mov     rdx, rdi
0x1400481d9  lea     rcx, aCwmswebservice_94; "CWmsWebService::GenerateReplacementCert"...
0x1400481e0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400481e5  call    ?s_GiveManagersReplacementSslCert@CManagedServerNotificationThread@@SAJXZ; CManagedServerNotificationThread::s_GiveManagersReplacementSslCert(void)
0x1400481ea  call    ?s_GiveManageesReplacementSslCert@CManagedServerNotificationThread@@SAJXZ; CManagedServerNotificationThread::s_GiveManageesReplacementSslCert(void)
0x1400481ef  mov     ebx, r15d
0x1400481f2  jmp     short loc_1400481F9
0x1400481f4  mov     ebx, 80070057h
0x1400481f9  mov     rcx, [rbp+pCertContext]; pCertContext
0x1400481fd  test    rcx, rcx
0x140048200  jz      short loc_140048208
0x140048202  call    cs:__imp_CertFreeCertificateContext
0x140048208  mov     rcx, rdi; Block
0x14004820b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140048210  mov     rcx, [rbp+Block.pbData]; Block
0x140048214  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140048219  mov     eax, ebx
0x14004821b  mov     rbx, [rsp+70h+arg_0]
0x140048223  add     rsp, 70h
0x140048227  pop     r15
0x140048229  pop     r14
0x14004822b  pop     r13
0x14004822d  pop     r12
0x14004822f  pop     rdi
0x140048230  pop     rsi
0x140048231  pop     rbp
0x140048232  retn
```
