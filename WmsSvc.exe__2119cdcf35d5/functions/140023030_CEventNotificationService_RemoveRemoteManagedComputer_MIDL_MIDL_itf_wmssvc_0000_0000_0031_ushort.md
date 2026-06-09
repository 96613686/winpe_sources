# CEventNotificationService::RemoveRemoteManagedComputer(__MIDL___MIDL_itf_wmssvc_0000_0000_0031,ushort *)

- ea: `0x140023030`
- end: `0x1400233c9`
- name: `?RemoveRemoteManagedComputer@CEventNotificationService@@UEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0031@@PEAG@Z`
- size: `921`
- prototype: `int __high(enum __MIDL___MIDL_itf_wmssvc_0000_0000_0031, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x140023030`
- `0x140059ec0`
- `0x14005a4e8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064148`
- `0x14006440c`
- `0x14006c590`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140023393`
- `ADVAPI32!RegCloseKey` at `0x140023393`
- `ADVAPI32!RegCreateKeyExW` at `0x14002325e`
- `ADVAPI32!RegCreateKeyExW` at `0x14002325e`
- `ADVAPI32!RegDeleteTreeW` at `0x1400232df`
- `ADVAPI32!RegDeleteTreeW` at `0x1400232df`
- `KERNEL32!IsDebuggerPresent` at `0x1400230ea`
- `KERNEL32!IsDebuggerPresent` at `0x1400232af`
- `KERNEL32!IsDebuggerPresent` at `0x140023334`
- `KERNEL32!IsDebuggerPresent` at `0x1400230ea`
- `KERNEL32!IsDebuggerPresent` at `0x1400232af`
- `KERNEL32!IsDebuggerPresent` at `0x140023334`
- `msvcrt!_wcsicmp` at `0x1400231b4`
- `msvcrt!_wcsicmp` at `0x1400231b4`
- `CRYPT32!CertFreeCertificateContext` at `0x1400231f9`
- `CRYPT32!CertFreeCertificateContext` at `0x1400231f9`
- `OLEAUT32!__imp_VariantInit` at `0x140023078`
- `OLEAUT32!__imp_VariantInit` at `0x140023078`
- `OLEAUT32!__imp_VariantClear` at `0x14002337c`
- `OLEAUT32!__imp_VariantClear` at `0x14002337c`

## string_xrefs

- `0x140023081`: `CEventNotificationService::RemoveRemoteManagedComputer - bstrRemoteHostName=%s.\n`
- `0x1400230c0`: `CEventNotificationService::RemoveRemoteManagedComputer`
- `0x140023282`: `CEventNotificationService::RemoveRemoteManagedComputer`
- `0x140023307`: `CEventNotificationService::RemoveRemoteManagedComputer`
- `0x1400233a4`: `CEventNotificationService::RemoveRemoteManagedComputer - bstrRemoteHostName=%s returning hr=0x%08X\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::RemoveRemoteManagedComputer(__int64 a1, unsigned int a2, const WCHAR *a3)
{
  wchar_t *v4; // r12
  int CertificateContext; // ebx
  int v8; // eax
  int MultiPointSslInfo; // eax
  const unsigned __int16 *bstrVal; // rcx
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  __int64 v13; // r8
  LSTATUS v14; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-49h]
  PHKEY phkResult; // [rsp+38h] [rbp-41h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-21h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-19h] BYREF
  struct _CRYPTOAPI_BLOB pvFindPara; // [rsp+68h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v23; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = 0;
  pCertContext = 0;
  hKey = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v23 = 0;
  pvFindPara = 0;
  String2 = 0;
  VariantInit(&pvarg);
  DEBUGMSG(L"CEventNotificationService::RemoveRemoteManagedComputer - bstrRemoteHostName=%s.\n", a3);
  CertificateContext = CUserManagement::s_VerifyAccessLevelEx(0, 0);
  if ( CertificateContext >= 0 )
  {
    if ( a3 )
    {
      if ( CEventNotificationService::m_sShutdownInProgress )
      {
        CertificateContext = -2147023781;
        goto LABEL_38;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, __int64, VARIANTARG *))(*(_QWORD *)a1 + 216LL))(
             a1,
             a2,
             a3,
             5,
             &pvarg);
      CertificateContext = 0;
      if ( v8 != -2147024894 )
        CertificateContext = v8;
      if ( CertificateContext >= 0 )
      {
        MultiPointSslInfo = GetMultiPointSslInfo(&v23, &String2);
        v4 = String2;
        CertificateContext = MultiPointSslInfo;
        if ( MultiPointSslInfo >= 0 )
        {
          if ( pvarg.vt != 8 )
            goto LABEL_21;
          bstrVal = pvarg.bstrVal;
          if ( pvarg.llVal )
          {
            if ( !_wcsicmp(pvarg.bstrVal, String2) )
            {
              CertificateContext = 0;
              goto LABEL_38;
            }
            bstrVal = pvarg.bstrVal;
          }
          CertificateContext = ConvertThumbprintStringToBlob(bstrVal, &pvFindPara);
          if ( CertificateContext >= 0 )
          {
            CertificateContext = GetCertificateContext(&pvFindPara, 0, &pCertContext);
            if ( CertificateContext >= 0 )
            {
              CertFreeCertificateContext(pCertContext);
              CertificateContext = DeleteCert(&pvFindPara);
              if ( CertificateContext >= 0 )
              {
LABEL_21:
                v11 = L"Software\\Microsoft\\Windows MultiPoint Server\\Managed Servers";
                if ( a2 )
                  v11 = L"Software\\Microsoft\\Windows MultiPoint Server\\Managed By Servers";
                v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
                if ( v12 )
                {
                  if ( v12 > 0 )
                    CertificateContext = (unsigned __int16)v12 | 0x80070000;
                  else
                    CertificateContext = v12;
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                    0x1C2Cu,
                    L"CEventNotificationService::RemoveRemoteManagedComputer",
                    L"CBRAEx",
                    L"err == 0L",
                    CertificateContext);
                  if ( IsDebuggerPresent() )
                  {
                    LODWORD(phkResult) = CertificateContext;
                    DEBUGMSGLEVEL(
                      2u,
                      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                      7212,
                      L"CEventNotificationService::RemoveRemoteManagedComputer",
                      L"CBRAEx",
                      L"err == 0L",
                      phkResult);
                    goto LABEL_38;
                  }
                  v13 = 7212;
                }
                else
                {
                  v14 = RegDeleteTreeW(hKey, a3);
                  if ( !v14 )
                    goto LABEL_38;
                  if ( v14 > 0 )
                    CertificateContext = (unsigned __int16)v14 | 0x80070000;
                  else
                    CertificateContext = v14;
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                    0x1C2Fu,
                    L"CEventNotificationService::RemoveRemoteManagedComputer",
                    L"CBRAEx",
                    L"err == 0L",
                    CertificateContext);
                  if ( IsDebuggerPresent() )
                  {
                    LODWORD(phkResult) = CertificateContext;
                    DEBUGMSGLEVEL(
                      2u,
                      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                      7215,
                      L"CEventNotificationService::RemoveRemoteManagedComputer",
                      L"CBRAEx",
                      L"err == 0L",
                      phkResult);
                    goto LABEL_38;
                  }
                  v13 = 7215;
                }
                LODWORD(lpSecurityAttributes) = CertificateContext;
                DEBUGMSGBOX(
                  L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                  L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                  v13,
                  L"CEventNotificationService::RemoveRemoteManagedComputer",
                  L"CBRAEx",
                  L"err == 0L",
                  lpSecurityAttributes);
              }
            }
          }
        }
      }
    }
    else
    {
      CertificateContext = -2147024809;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x1C01u,
        L"CEventNotificationService::RemoveRemoteManagedComputer",
        L"CBRAEx",
        L"bstrRemoteHostName",
        -2147024809);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          7169,
          L"CEventNotificationService::RemoveRemoteManagedComputer",
          L"CBRAEx",
          L"bstrRemoteHostName",
          -2147024809);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          7169,
          L"CEventNotificationService::RemoveRemoteManagedComputer",
          L"CBRAEx",
          L"bstrRemoteHostName",
          -2147024809);
    }
  }
LABEL_38:
  VariantClear(&pvarg);
  operator delete(v4);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  DEBUGMSG(
    L"CEventNotificationService::RemoveRemoteManagedComputer - bstrRemoteHostName=%s returning hr=0x%08X\n",
    a3,
    (unsigned int)CertificateContext);
  return (unsigned int)CertificateContext;
}

```

## disassembly

```asm
0x140023030  push    rbp
0x140023032  push    rbx
0x140023033  push    rsi
0x140023034  push    rdi
0x140023035  push    r12
0x140023037  push    r13
0x140023039  push    r14
0x14002303b  push    r15
0x14002303d  lea     rbp, [rsp-1Fh]
0x140023042  sub     rsp, 98h
0x140023049  xor     eax, eax
0x14002304b  xorps   xmm0, xmm0
0x14002304e  mov     rdi, rcx
0x140023051  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140023055  xor     r12d, r12d
0x140023058  mov     [rbp+57h+pCertContext], rax
0x14002305c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140023060  mov     [rbp+57h+hKey], rax
0x140023064  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x140023068  mov     [rbp+57h+arg_18], eax
0x14002306b  mov     r13, r8
0x14002306e  movups  xmmword ptr [rbp+57h+pvFindPara.cbData], xmm0
0x140023072  mov     [rbp+57h+String2], r12
0x140023076  mov     esi, edx
0x140023078  call    cs:__imp_VariantInit
0x14002307e  mov     rdx, r13
0x140023081  lea     rcx, aCeventnotifica_171; "CEventNotificationService::RemoveRemote"...
0x140023088  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002308d  xor     edx, edx
0x14002308f  xor     ecx, ecx
0x140023091  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140023096  mov     ebx, eax
0x140023098  test    eax, eax
0x14002309a  js      loc_140023378
0x1400230a0  test    r13, r13
0x1400230a3  jnz     loc_14002313B
0x1400230a9  lea     rax, aBstrremotehost; "bstrRemoteHostName"
0x1400230b0  mov     ebx, 80070057h
0x1400230b5  lea     r14, aCbraex; "CBRAEx"
0x1400230bc  mov     [rsp+0D0h+samDesired], ebx; int
0x1400230c0  lea     rsi, aCeventnotifica_170; "CEventNotificationService::RemoveRemote"...
0x1400230c7  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned __int16 *
0x1400230cc  mov     r15d, 1C01h
0x1400230d2  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400230d9  mov     r9, r14; unsigned __int16 *
0x1400230dc  mov     r8, rsi; unsigned __int16 *
0x1400230df  mov     edx, r15d; unsigned int
0x1400230e2  mov     rcx, rdi; unsigned __int16 *
0x1400230e5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400230ea  call    cs:__imp_IsDebuggerPresent
0x1400230f0  test    eax, eax
0x1400230f2  lea     rax, aBstrremotehost; "bstrRemoteHostName"
0x1400230f9  jz      short loc_14002312A
0x1400230fb  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x1400230ff  mov     r9d, r15d
0x140023102  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x140023107  mov     qword ptr [rsp+0D0h+samDesired], r14
0x14002310c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140023113  mov     r8, rdi
0x140023116  mov     qword ptr [rsp+0D0h+dwOptions], rsi
0x14002311b  mov     ecx, 2; unsigned __int8
0x140023120  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140023125  jmp     loc_140023378
0x14002312a  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], ebx
0x14002312e  mov     r8d, r15d
0x140023131  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140023136  jmp     loc_140023361
0x14002313b  cmp     cs:?m_sShutdownInProgress@CEventNotificationService@@2HA, r12d; int CEventNotificationService::m_sShutdownInProgress
0x140023142  jz      short loc_14002314E
0x140023144  mov     ebx, 8007045Bh
0x140023149  jmp     loc_140023378
0x14002314e  mov     rax, [rdi]
0x140023151  lea     rcx, [rbp+57h+pvarg]
0x140023155  mov     qword ptr [rsp+0D0h+dwOptions], rcx
0x14002315a  mov     r9d, 5
0x140023160  mov     r8, r13
0x140023163  mov     edx, esi
0x140023165  mov     rcx, rdi
0x140023168  mov     rax, [rax+0D8h]
0x14002316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023174  xor     ebx, ebx
0x140023176  cmp     eax, 80070002h
0x14002317b  cmovnz  ebx, eax
0x14002317e  test    ebx, ebx
0x140023180  js      loc_140023378
0x140023186  lea     rdx, [rbp+57h+String2]; unsigned __int16 **
0x14002318a  lea     rcx, [rbp+57h+arg_18]; unsigned int *
0x14002318e  call    ?GetMultiPointSslInfo@@YAJPEAKPEAPEAG@Z; GetMultiPointSslInfo(ulong *,ushort * *)
0x140023193  mov     r12, [rbp+57h+String2]
0x140023197  mov     ebx, eax
0x140023199  test    eax, eax
0x14002319b  js      loc_140023378
0x1400231a1  cmp     word ptr [rbp+57h+pvarg], 8
0x1400231a6  jnz     short loc_140023212
0x1400231a8  mov     rcx, qword ptr [rbp+57h+pvarg+8]; String1
0x1400231ac  test    rcx, rcx
0x1400231af  jz      short loc_1400231C9
0x1400231b1  mov     rdx, r12; String2
0x1400231b4  call    cs:__imp__wcsicmp
0x1400231ba  test    eax, eax
0x1400231bc  jnz     short loc_1400231C5
0x1400231be  xor     ebx, ebx
0x1400231c0  jmp     loc_140023378
0x1400231c5  mov     rcx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x1400231c9  lea     rdx, [rbp+57h+pvFindPara]; struct _CRYPTOAPI_BLOB *
0x1400231cd  call    ?ConvertThumbprintStringToBlob@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z; ConvertThumbprintStringToBlob(ushort const *,_CRYPTOAPI_BLOB *)
0x1400231d2  mov     ebx, eax
0x1400231d4  test    eax, eax
0x1400231d6  js      loc_140023378
0x1400231dc  lea     r8, [rbp+57h+pCertContext]
0x1400231e0  xor     edx, edx
0x1400231e2  lea     rcx, [rbp+57h+pvFindPara]
0x1400231e6  call    ?GetCertificateContext@@YAJPEAU_CRYPTOAPI_BLOB@@W4EBehaviorOnCertMissing@@PEAPEBU_CERT_CONTEXT@@@Z; GetCertificateContext(_CRYPTOAPI_BLOB *,EBehaviorOnCertMissing,_CERT_CONTEXT const * *)
0x1400231eb  mov     ebx, eax
0x1400231ed  test    eax, eax
0x1400231ef  js      loc_140023378
0x1400231f5  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x1400231f9  call    cs:__imp_CertFreeCertificateContext
0x1400231ff  lea     rcx, [rbp+57h+pvFindPara]; pvFindPara
0x140023203  call    ?DeleteCert@@YAJPEAU_CRYPTOAPI_BLOB@@@Z; DeleteCert(_CRYPTOAPI_BLOB *)
0x140023208  mov     ebx, eax
0x14002320a  test    eax, eax
0x14002320c  js      loc_140023378
0x140023212  mov     [rsp+0D0h+lpdwDisposition], 0; lpdwDisposition
0x14002321b  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows MultiPoint"...
0x140023222  test    esi, esi
0x140023224  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows MultiPoint"...
0x14002322b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023232  cmovnz  rdx, rax; lpSubKey
0x140023236  lea     rax, [rbp+57h+hKey]
0x14002323a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x14002323f  xor     r9d, r9d; lpClass
0x140023242  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14002324b  xor     r8d, r8d; Reserved
0x14002324e  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x140023256  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x14002325e  call    cs:__imp_RegCreateKeyExW
0x140023264  test    eax, eax
0x140023266  jz      short loc_1400232D8
0x140023268  jg      short loc_14002326E
0x14002326a  mov     ebx, eax
0x14002326c  jmp     short loc_140023277
0x14002326e  movzx   ebx, ax
0x140023271  or      ebx, 80070000h
0x140023277  lea     r14, aCbraex; "CBRAEx"
0x14002327e  mov     [rsp+0D0h+samDesired], ebx; int
0x140023282  lea     rsi, aCeventnotifica_170; "CEventNotificationService::RemoveRemote"...
0x140023289  mov     r9, r14; unsigned __int16 *
0x14002328c  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140023293  mov     r8, rsi; unsigned __int16 *
0x140023296  lea     r15, aErr0l; "err == 0L"
0x14002329d  mov     rcx, rdi; unsigned __int16 *
0x1400232a0  mov     edx, 1C2Ch; unsigned int
0x1400232a5  mov     qword ptr [rsp+0D0h+dwOptions], r15; unsigned __int16 *
0x1400232aa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400232af  call    cs:__imp_IsDebuggerPresent
0x1400232b5  test    eax, eax
0x1400232b7  jz      short loc_1400232CD
0x1400232b9  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x1400232bd  mov     r9d, 1C2Ch
0x1400232c3  mov     [rsp+0D0h+lpSecurityAttributes], r15
0x1400232c8  jmp     loc_140023107
0x1400232cd  mov     r8d, 1C2Ch
0x1400232d3  jmp     loc_140023358
0x1400232d8  mov     rcx, [rbp+57h+hKey]; hKey
0x1400232dc  mov     rdx, r13; lpSubKey
0x1400232df  call    cs:__imp_RegDeleteTreeW
0x1400232e5  test    eax, eax
0x1400232e7  jz      loc_140023378
0x1400232ed  jg      short loc_1400232F3
0x1400232ef  mov     ebx, eax
0x1400232f1  jmp     short loc_1400232FC
0x1400232f3  movzx   ebx, ax
0x1400232f6  or      ebx, 80070000h
0x1400232fc  lea     r14, aCbraex; "CBRAEx"
0x140023303  mov     [rsp+0D0h+samDesired], ebx; int
0x140023307  lea     rsi, aCeventnotifica_170; "CEventNotificationService::RemoveRemote"...
0x14002330e  mov     r9, r14; unsigned __int16 *
0x140023311  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140023318  mov     r8, rsi; unsigned __int16 *
0x14002331b  lea     r15, aErr0l; "err == 0L"
0x140023322  mov     rcx, rdi; unsigned __int16 *
0x140023325  mov     edx, 1C2Fh; unsigned int
0x14002332a  mov     qword ptr [rsp+0D0h+dwOptions], r15; unsigned __int16 *
0x14002332f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140023334  call    cs:__imp_IsDebuggerPresent
0x14002333a  test    eax, eax
0x14002333c  jz      short loc_140023352
0x14002333e  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x140023342  mov     r9d, 1C2Fh
0x140023348  mov     [rsp+0D0h+lpSecurityAttributes], r15
0x14002334d  jmp     loc_140023107
0x140023352  mov     r8d, 1C2Fh
0x140023358  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], ebx
0x14002335c  mov     qword ptr [rsp+0D0h+samDesired], r15
0x140023361  mov     r9, rsi
0x140023364  mov     qword ptr [rsp+0D0h+dwOptions], r14
0x140023369  mov     rdx, rdi
0x14002336c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140023373  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140023378  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002337c  call    cs:__imp_VariantClear
0x140023382  mov     rcx, r12; Block
0x140023385  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002338a  mov     rcx, [rbp+57h+hKey]; hKey
0x14002338e  test    rcx, rcx
0x140023391  jz      short loc_1400233A1
0x140023393  call    cs:__imp_RegCloseKey
0x140023399  mov     [rbp+57h+hKey], 0
0x1400233a1  mov     r8d, ebx
0x1400233a4  lea     rcx, aCeventnotifica_110; "CEventNotificationService::RemoveRemote"...
0x1400233ab  mov     rdx, r13
0x1400233ae  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400233b3  mov     eax, ebx
0x1400233b5  add     rsp, 98h
0x1400233bc  pop     r15
0x1400233be  pop     r14
0x1400233c0  pop     r13
0x1400233c2  pop     r12
0x1400233c4  pop     rdi
0x1400233c5  pop     rsi
0x1400233c6  pop     rbx
0x1400233c7  pop     rbp
0x1400233c8  retn
```
