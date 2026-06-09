# CManagedServerNotificationThread::s_GiveManagersReplacementSslCert(void)

- ea: `0x14002ba9c`
- end: `0x14002c1af`
- name: `?s_GiveManagersReplacementSslCert@CManagedServerNotificationThread@@SAJXZ`
- size: `1811`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002a960`
- `0x140047f10`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14002ba9c`
- `0x14004c738`
- `0x140058d10`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064644`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002c14f`
- `ADVAPI32!RegCloseKey` at `0x14002c14f`
- `ADVAPI32!RegCreateKeyExW` at `0x14002bcc1`
- `ADVAPI32!RegCreateKeyExW` at `0x14002bcc1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002bd6e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002bd6e`
- `ADVAPI32!RegEnumKeyExW` at `0x14002bec0`
- `ADVAPI32!RegEnumKeyExW` at `0x14002bec0`
- `KERNEL32!IsDebuggerPresent` at `0x14002bbdb`
- `KERNEL32!IsDebuggerPresent` at `0x14002bd12`
- `KERNEL32!IsDebuggerPresent` at `0x14002bdbf`
- `KERNEL32!IsDebuggerPresent` at `0x14002be4d`
- `KERNEL32!IsDebuggerPresent` at `0x14002bfcd`
- `KERNEL32!IsDebuggerPresent` at `0x14002c02f`
- `KERNEL32!IsDebuggerPresent` at `0x14002c0b1`
- `KERNEL32!IsDebuggerPresent` at `0x14002bbdb`
- `KERNEL32!IsDebuggerPresent` at `0x14002bd12`
- `KERNEL32!IsDebuggerPresent` at `0x14002bdbf`
- `KERNEL32!IsDebuggerPresent` at `0x14002be4d`
- `KERNEL32!IsDebuggerPresent` at `0x14002bfcd`
- `KERNEL32!IsDebuggerPresent` at `0x14002c02f`
- `KERNEL32!IsDebuggerPresent` at `0x14002c0b1`
- `msvcrt!_wcsicmp` at `0x14002bef8`
- `msvcrt!_wcsicmp` at `0x14002bef8`
- `CRYPT32!CertFreeCertificateContext` at `0x14002c140`
- `CRYPT32!CertFreeCertificateContext` at `0x14002c140`
- `ole32!CoCreateInstance` at `0x14002bb93`
- `ole32!CoCreateInstance` at `0x14002bb93`
- `OLEAUT32!__imp_SysAllocString` at `0x14002bedf`
- `OLEAUT32!__imp_SysAllocString` at `0x14002bedf`
- `OLEAUT32!__imp_SysFreeString` at `0x14002be8b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c0ea`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c0f4`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c124`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c131`
- `OLEAUT32!__imp_SysFreeString` at `0x14002be8b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c0ea`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c0f4`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c124`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c131`
- `OLEAUT32!__imp_SysStringLen` at `0x14002c103`
- `OLEAUT32!__imp_SysStringLen` at `0x14002c103`
- `OLEAUT32!__imp_VariantInit` at `0x14002bb07`
- `OLEAUT32!__imp_VariantInit` at `0x14002bb07`
- `OLEAUT32!__imp_VariantClear` at `0x14002c0d8`
- `OLEAUT32!__imp_VariantClear` at `0x14002c0d8`
- `PROPSYS!VariantToUInt32` at `0x14002bf41`
- `PROPSYS!VariantToUInt32` at `0x14002bf41`

## string_xrefs

- `0x14002bb3f`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002bbb8`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002bcef`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002bd9c`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002be30`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002bfaa`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c012`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c08e`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002bab8`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert - Start\n`
- `0x14002bb38`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002bbae`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002bce5`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002bd92`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002be24`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002bfa0`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002c006`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002c084`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert`
- `0x14002bb26`: `No replacement cert, nothing to do.`
- `0x14002bf51`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert - Attempt to send OnNewServerCertificateReady event to %s:%d.\n`
- `0x14002c18d`: `CManagedServerNotificationThread::s_GiveManagersReplacementSslCert - End, hr = 0x%08X\n`

## pseudocode

```c
__int64 CManagedServerNotificationThread::s_GiveManagersReplacementSslCert(void)
{
  WCHAR *v0; // r13
  OLECHAR *v1; // r12
  signed int DoesReplacementCertExist; // ebx
  HRESULT v3; // eax
  const unsigned __int16 *v4; // r15
  const unsigned __int16 *v5; // r14
  __int64 v6; // r9
  __int64 v7; // r8
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  const wchar_t *v11; // rax
  HRESULT v12; // eax
  OLECHAR *v13; // rcx
  __int64 v14; // rax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-69h]
  PHKEY phkResult; // [rsp+38h] [rbp-61h]
  BSTR pbstr; // [rsp+60h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-29h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp-21h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+80h] [rbp-19h] BYREF
  __int64 v23; // [rsp+88h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-1h] BYREF
  DWORD cSubKeys; // [rsp+100h] [rbp+67h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+108h] [rbp+6Fh] BYREF
  ULONG pulRet; // [rsp+110h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+118h] [rbp+7Fh] BYREF

  ppv = 0;
  v23 = 0;
  pulRet = 0;
  v0 = 0;
  hKey = 0;
  v1 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  String1 = 0;
  bstrString = 0;
  pbstr = 0;
  pCertContext = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  DEBUGMSG(L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert - Start\n");
  VariantInit(&pvarg);
  DoesReplacementCertExist = CWmsWebService::s_DoesReplacementCertExist(&pCertContext);
  if ( DoesReplacementCertExist >= 0 )
  {
    if ( !pCertContext )
    {
      DoesReplacementCertExist = 0;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        419,
        L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
        L"No replacement cert, nothing to do.");
      goto LABEL_53;
    }
    DoesReplacementCertExist = GetLocalHostName(&String1);
    if ( DoesReplacementCertExist >= 0 )
    {
      v3 = CoCreateInstance(&CLSID_EventNotificationService, 0, 4u, &GUID_28b159df_59eb_446b_9316_8b902f75fdf7, &ppv);
      DoesReplacementCertExist = v3;
      if ( v3 < 0 )
      {
        v4 = L"CHRA";
        v5 = L"hr";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          0x1ABu,
          L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
          L"CHRA",
          L"hr",
          v3);
        if ( IsDebuggerPresent() )
        {
          v6 = 427;
LABEL_8:
          LODWORD(phkResult) = DoesReplacementCertExist;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            v6,
            L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
            v4,
            v5,
            phkResult);
          goto LABEL_53;
        }
        v7 = 427;
        goto LABEL_10;
      }
      DoesReplacementCertExist = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                                   ppv,
                                   &GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8,
                                   &v23);
      if ( DoesReplacementCertExist >= 0 )
      {
        DoesReplacementCertExist = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *, BSTR *))(*(_QWORD *)v23 + 224LL))(
                                     v23,
                                     0,
                                     &bstrString,
                                     &pbstr);
        if ( DoesReplacementCertExist >= 0 )
        {
          v8 = RegCreateKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows MultiPoint Server\\Managed By Servers",
                 0,
                 0,
                 0,
                 0xF003Fu,
                 0,
                 &hKey,
                 0);
          if ( v8 )
          {
            if ( v8 > 0 )
              DoesReplacementCertExist = (unsigned __int16)v8 | 0x80070000;
            else
              DoesReplacementCertExist = v8;
            v4 = L"CBRAEx";
            v5 = L"err == 0L";
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              0x1B5u,
              L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
              L"CBRAEx",
              L"err == 0L",
              DoesReplacementCertExist);
            if ( IsDebuggerPresent() )
            {
              v6 = 437;
              goto LABEL_8;
            }
            v7 = 437;
            goto LABEL_10;
          }
          v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
          if ( v9 )
          {
            if ( v9 > 0 )
              DoesReplacementCertExist = (unsigned __int16)v9 | 0x80070000;
            else
              DoesReplacementCertExist = v9;
            v4 = L"CBRAEx";
            v5 = L"err == 0L";
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              0x1B9u,
              L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
              L"CBRAEx",
              L"err == 0L",
              DoesReplacementCertExist);
            if ( IsDebuggerPresent() )
            {
              v6 = 441;
              goto LABEL_8;
            }
            v7 = 441;
LABEL_10:
            LODWORD(lpSecurityAttributes) = DoesReplacementCertExist;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              v7,
              L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
              v4,
              v5,
              lpSecurityAttributes);
            goto LABEL_53;
          }
          v0 = (WCHAR *)operator new(saturated_mul(cbMaxSubKeyLen + 1, 2u));
          if ( v0 )
          {
            while ( cSubKeys )
            {
              SysFreeString(v1);
              v1 = 0;
              cchName = cbMaxSubKeyLen + 1;
              v10 = RegEnumKeyExW(hKey, cSubKeys - 1, v0, &cchName, 0, 0, 0, 0);
              if ( v10 == 259 )
              {
                DoesReplacementCertExist = 0;
                break;
              }
              if ( v10 )
              {
                if ( v10 > 0 )
                  DoesReplacementCertExist = (unsigned __int16)v10 | 0x80070000;
                else
                  DoesReplacementCertExist = v10;
                v4 = L"CBRAEx";
                v5 = L"err == 0L";
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                  0x1D2u,
                  L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                  L"CBRAEx",
                  L"err == 0L",
                  DoesReplacementCertExist);
                if ( IsDebuggerPresent() )
                {
                  v6 = 466;
                  goto LABEL_8;
                }
                v7 = 466;
                goto LABEL_10;
              }
              --cSubKeys;
              v11 = SysAllocString(v0);
              v1 = (OLECHAR *)v11;
              if ( !v11 )
              {
                DoesReplacementCertExist = -2147024882;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                  0x1D7u,
                  L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                  L"CPR",
                  L"bstrFqdnRemoteHost",
                  -2147024882);
                if ( IsDebuggerPresent() )
                {
                  LODWORD(phkResult) = -2147024882;
                  DEBUGMSGLEVEL(
                    2u,
                    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                    471,
                    L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                    L"CPR",
                    L"bstrFqdnRemoteHost",
                    phkResult);
                }
                else
                {
                  LODWORD(lpSecurityAttributes) = -2147024882;
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                    471,
                    L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                    L"CPR",
                    L"bstrFqdnRemoteHost",
                    lpSecurityAttributes);
                }
                break;
              }
              if ( _wcsicmp(String1, v11) )
              {
                DoesReplacementCertExist = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *))(*(_QWORD *)ppv + 216LL))(
                                             ppv,
                                             1,
                                             v1);
                if ( DoesReplacementCertExist < 0 )
                  break;
                v12 = VariantToUInt32(&pvarg, &pulRet);
                DoesReplacementCertExist = v12;
                if ( v12 < 0 )
                {
                  v4 = L"CHRA";
                  v5 = L"hr";
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                    0x1E3u,
                    L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                    L"CHRA",
                    L"hr",
                    v12);
                  if ( IsDebuggerPresent() )
                  {
                    v6 = 483;
                    goto LABEL_8;
                  }
                  v7 = 483;
                  goto LABEL_10;
                }
                DEBUGMSG(
                  L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert - Attempt to send OnNewServerCertif"
                   "icateReady event to %s:%d.\n",
                  v1,
                  pulRet);
                DoesReplacementCertExist = CWmsWebServiceProxy::s_SendOnNewServerCertificateReady(
                                             v1,
                                             pulRet,
                                             String1,
                                             pbstr,
                                             pCertContext);
                if ( DoesReplacementCertExist < 0 )
                  break;
              }
            }
          }
          else
          {
            DoesReplacementCertExist = -2147024882;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              0x1BDu,
              L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
              L"CPR",
              L"pszSubKeyNameBuffer",
              -2147024882);
            if ( IsDebuggerPresent() )
            {
              LODWORD(phkResult) = -2147024882;
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                445,
                L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                L"CPR",
                L"pszSubKeyNameBuffer",
                phkResult);
            }
            else
            {
              LODWORD(lpSecurityAttributes) = -2147024882;
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                445,
                L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert",
                L"CPR",
                L"pszSubKeyNameBuffer",
                lpSecurityAttributes);
            }
          }
        }
      }
    }
  }
LABEL_53:
  VariantClear(&pvarg);
  operator delete(v0);
  SysFreeString(String1);
  SysFreeString(bstrString);
  if ( pbstr )
  {
    LODWORD(v14) = SysStringLen(pbstr);
    v13 = pbstr;
    v14 = (unsigned int)v14;
    if ( (_DWORD)v14 )
    {
      do
      {
        *(_BYTE *)v13 = 0;
        v13 = (OLECHAR *)((char *)v13 + 1);
        --v14;
      }
      while ( v14 );
      v13 = pbstr;
    }
    SysFreeString(v13);
    pbstr = 0;
  }
  SysFreeString(v1);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  DEBUGMSG(
    L"CManagedServerNotificationThread::s_GiveManagersReplacementSslCert - End, hr = 0x%08X\n",
    (unsigned int)DoesReplacementCertExist);
  return (unsigned int)DoesReplacementCertExist;
}

```

## disassembly

```asm
0x14002ba9c  push    rbp
0x14002ba9e  push    rbx
0x14002ba9f  push    rsi
0x14002baa0  push    rdi
0x14002baa1  push    r12
0x14002baa3  push    r13
0x14002baa5  push    r14
0x14002baa7  push    r15
0x14002baa9  lea     rbp, [rsp-1Fh]
0x14002baae  sub     rsp, 0B8h
0x14002bab5  xor     r14d, r14d
0x14002bab8  lea     rcx, aCmanagedserver_16; "CManagedServerNotificationThread::s_Giv"...
0x14002babf  xorps   xmm0, xmm0
0x14002bac2  mov     [rbp+57h+var_80], r14
0x14002bac6  xor     eax, eax
0x14002bac8  mov     [rbp+57h+var_68], r14
0x14002bacc  mov     [rbp+57h+pulRet], r14d
0x14002bad0  mov     r13d, r14d
0x14002bad3  mov     [rbp+57h+hKey], r14
0x14002bad7  mov     r12d, r14d
0x14002bada  mov     [rbp+57h+cSubKeys], r14d
0x14002bade  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x14002bae2  mov     [rbp+57h+cchName], r14d
0x14002bae6  mov     [rbp+57h+String1], r14
0x14002baea  mov     [rbp+57h+bstrString], r14
0x14002baee  mov     [rbp+57h+pbstr], r14
0x14002baf2  mov     [rbp+57h+pCertContext], r14
0x14002baf6  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14002bafa  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14002bafe  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002bb03  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002bb07  call    cs:__imp_VariantInit
0x14002bb0d  lea     rcx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT **
0x14002bb11  call    ?s_DoesReplacementCertExist@CWmsWebService@@SAJPEAPEBU_CERT_CONTEXT@@@Z; CWmsWebService::s_DoesReplacementCertExist(_CERT_CONTEXT const * *)
0x14002bb16  mov     ebx, eax
0x14002bb18  test    eax, eax
0x14002bb1a  js      loc_14002C0D4
0x14002bb20  cmp     [rbp+57h+pCertContext], r14
0x14002bb24  jnz     short loc_14002BB63
0x14002bb26  lea     rax, aNoReplacementC; "No replacement cert, nothing to do."
0x14002bb2d  mov     r9d, 1A3h
0x14002bb33  mov     qword ptr [rsp+0F0h+samDesired], rax
0x14002bb38  lea     rsi, aCmanagedserver_9; "CManagedServerNotificationThread::s_Giv"...
0x14002bb3f  lea     r8, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002bb46  mov     [rsp+0F0h+ppv], rsi
0x14002bb4b  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002bb52  mov     ebx, r14d
0x14002bb55  lea     ecx, [r14+4]; unsigned __int8
0x14002bb59  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002bb5e  jmp     loc_14002C0D4
0x14002bb63  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x14002bb67  call    ?GetLocalHostName@@YAJPEAPEAG@Z; GetLocalHostName(ushort * *)
0x14002bb6c  mov     ebx, eax
0x14002bb6e  test    eax, eax
0x14002bb70  js      loc_14002C0D4
0x14002bb76  xor     edx, edx; pUnkOuter
0x14002bb78  lea     rax, [rbp+57h+var_80]
0x14002bb7c  lea     r9, _GUID_28b159df_59eb_446b_9316_8b902f75fdf7; riid
0x14002bb83  mov     [rsp+0F0h+ppv], rax; ppv
0x14002bb88  lea     rcx, CLSID_EventNotificationService; rclsid
0x14002bb8f  lea     r8d, [rdx+4]; dwClsContext
0x14002bb93  call    cs:__imp_CoCreateInstance
0x14002bb99  mov     ebx, eax
0x14002bb9b  test    eax, eax
0x14002bb9d  jns     loc_14002BC42
0x14002bba3  mov     [rsp+0F0h+samDesired], eax; int
0x14002bba7  lea     r15, aChra; "CHRA"
0x14002bbae  lea     rsi, aCmanagedserver_9; "CManagedServerNotificationThread::s_Giv"...
0x14002bbb5  mov     r9, r15; unsigned __int16 *
0x14002bbb8  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002bbbf  mov     r8, rsi; unsigned __int16 *
0x14002bbc2  lea     r14, aHr; "hr"
0x14002bbc9  mov     rcx, rdi; unsigned __int16 *
0x14002bbcc  mov     edx, 1ABh; unsigned int
0x14002bbd1  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x14002bbd6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002bbdb  call    cs:__imp_IsDebuggerPresent
0x14002bbe1  test    eax, eax
0x14002bbe3  jz      short loc_14002BC14
0x14002bbe5  mov     r9d, 1ABh
0x14002bbeb  mov     dword ptr [rsp+0F0h+phkResult], ebx
0x14002bbef  mov     [rsp+0F0h+lpSecurityAttributes], r14
0x14002bbf4  mov     qword ptr [rsp+0F0h+samDesired], r15
0x14002bbf9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002bc00  mov     r8, rdi
0x14002bc03  mov     [rsp+0F0h+ppv], rsi
0x14002bc08  mov     ecx, 2; unsigned __int8
0x14002bc0d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002bc12  jmp     short loc_14002BC3A
0x14002bc14  mov     r8d, 1ABh
0x14002bc1a  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], ebx
0x14002bc1e  mov     qword ptr [rsp+0F0h+samDesired], r14
0x14002bc23  mov     r9, rsi
0x14002bc26  mov     [rsp+0F0h+ppv], r15
0x14002bc2b  mov     rdx, rdi
0x14002bc2e  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002bc35  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002bc3a  xor     r14d, r14d
0x14002bc3d  jmp     loc_14002C0D4
0x14002bc42  mov     rcx, [rbp+57h+var_80]
0x14002bc46  lea     r8, [rbp+57h+var_68]
0x14002bc4a  lea     rdx, _GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8
0x14002bc51  mov     rax, [rcx]
0x14002bc54  mov     rax, [rax]
0x14002bc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bc5c  mov     ebx, eax
0x14002bc5e  test    eax, eax
0x14002bc60  js      loc_14002C0D4
0x14002bc66  mov     rcx, [rbp+57h+var_68]
0x14002bc6a  lea     r9, [rbp+57h+pbstr]
0x14002bc6e  lea     r8, [rbp+57h+bstrString]
0x14002bc72  xor     edx, edx
0x14002bc74  mov     rax, [rcx]
0x14002bc77  mov     rax, [rax+0E0h]
0x14002bc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bc83  mov     ebx, eax
0x14002bc85  test    eax, eax
0x14002bc87  js      loc_14002C0D4
0x14002bc8d  mov     [rsp+0F0h+lpdwDisposition], r14; lpdwDisposition
0x14002bc92  lea     rax, [rbp+57h+hKey]
0x14002bc96  mov     [rsp+0F0h+phkResult], rax; phkResult
0x14002bc9b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows MultiPoint"...
0x14002bca2  mov     [rsp+0F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14002bca7  xor     r9d, r9d; lpClass
0x14002bcaa  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x14002bcb2  xor     r8d, r8d; Reserved
0x14002bcb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002bcbc  mov     dword ptr [rsp+0F0h+ppv], r14d; dwOptions
0x14002bcc1  call    cs:__imp_RegCreateKeyExW
0x14002bcc7  test    eax, eax
0x14002bcc9  jz      short loc_14002BD32
0x14002bccb  jg      short loc_14002BCD1
0x14002bccd  mov     ebx, eax
0x14002bccf  jmp     short loc_14002BCDA
0x14002bcd1  movzx   ebx, ax
0x14002bcd4  or      ebx, 80070000h
0x14002bcda  lea     r15, aCbraex; "CBRAEx"
0x14002bce1  mov     [rsp+0F0h+samDesired], ebx; int
0x14002bce5  lea     rsi, aCmanagedserver_9; "CManagedServerNotificationThread::s_Giv"...
0x14002bcec  mov     r9, r15; unsigned __int16 *
0x14002bcef  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002bcf6  mov     r8, rsi; unsigned __int16 *
0x14002bcf9  lea     r14, aErr0l; "err == 0L"
0x14002bd00  mov     rcx, rdi; unsigned __int16 *
0x14002bd03  mov     edx, 1B5h; unsigned int
0x14002bd08  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x14002bd0d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002bd12  call    cs:__imp_IsDebuggerPresent
0x14002bd18  test    eax, eax
0x14002bd1a  jz      short loc_14002BD27
0x14002bd1c  mov     r9d, 1B5h
0x14002bd22  jmp     loc_14002BBEB
0x14002bd27  mov     r8d, 1B5h
0x14002bd2d  jmp     loc_14002BC1A
0x14002bd32  mov     rcx, [rbp+57h+hKey]; hKey
0x14002bd36  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14002bd3a  mov     [rsp+0F0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14002bd3f  xor     r9d, r9d; lpReserved
0x14002bd42  mov     [rsp+0F0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x14002bd47  xor     r8d, r8d; lpcchClass
0x14002bd4a  mov     [rsp+0F0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14002bd4f  xor     edx, edx; lpClass
0x14002bd51  mov     [rsp+0F0h+lpdwDisposition], r14; lpcbMaxValueNameLen
0x14002bd56  mov     [rsp+0F0h+phkResult], r14; lpcValues
0x14002bd5b  mov     [rsp+0F0h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x14002bd60  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbMaxSubKeyLen
0x14002bd65  lea     rax, [rbp+57h+cSubKeys]
0x14002bd69  mov     [rsp+0F0h+ppv], rax; lpcSubKeys
0x14002bd6e  call    cs:__imp_RegQueryInfoKeyW
0x14002bd74  test    eax, eax
0x14002bd76  jz      short loc_14002BDDF
0x14002bd78  jg      short loc_14002BD7E
0x14002bd7a  mov     ebx, eax
0x14002bd7c  jmp     short loc_14002BD87
0x14002bd7e  movzx   ebx, ax
0x14002bd81  or      ebx, 80070000h
0x14002bd87  lea     r15, aCbraex; "CBRAEx"
0x14002bd8e  mov     [rsp+0F0h+samDesired], ebx; int
0x14002bd92  lea     rsi, aCmanagedserver_9; "CManagedServerNotificationThread::s_Giv"...
0x14002bd99  mov     r9, r15; unsigned __int16 *
0x14002bd9c  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002bda3  mov     r8, rsi; unsigned __int16 *
0x14002bda6  lea     r14, aErr0l; "err == 0L"
0x14002bdad  mov     rcx, rdi; unsigned __int16 *
0x14002bdb0  mov     edx, 1B9h; unsigned int
0x14002bdb5  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x14002bdba  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002bdbf  call    cs:__imp_IsDebuggerPresent
0x14002bdc5  test    eax, eax
0x14002bdc7  jz      short loc_14002BDD4
0x14002bdc9  mov     r9d, 1B9h
0x14002bdcf  jmp     loc_14002BBEB
0x14002bdd4  mov     r8d, 1B9h
0x14002bdda  jmp     loc_14002BC1A
0x14002bddf  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x14002bde2  mov     eax, 2
0x14002bde7  inc     ecx
0x14002bde9  mul     rcx
0x14002bdec  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002bdf3  cmovb   rax, rcx
0x14002bdf7  mov     rcx, rax; Size
0x14002bdfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002bdff  mov     r13, rax
0x14002be02  test    rax, rax
0x14002be05  jnz     loc_14002BF86
0x14002be0b  mov     r14d, 8007000Eh
0x14002be11  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002be18  lea     r15, aCpr; "CPR"
0x14002be1f  mov     [rsp+0F0h+samDesired], r14d; int
0x14002be24  lea     rsi, aCmanagedserver_9; "CManagedServerNotificationThread::s_Giv"...
0x14002be2b  mov     [rsp+0F0h+ppv], rax; unsigned __int16 *
0x14002be30  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002be37  mov     r9, r15; unsigned __int16 *
0x14002be3a  mov     r8, rsi; unsigned __int16 *
0x14002be3d  mov     rcx, rdi; unsigned __int16 *
0x14002be40  mov     edx, 1BDh; unsigned int
0x14002be45  mov     ebx, r14d
0x14002be48  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002be4d  call    cs:__imp_IsDebuggerPresent
0x14002be53  test    eax, eax
0x14002be55  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002be5c  jz      short loc_14002BE73
0x14002be5e  mov     dword ptr [rsp+0F0h+phkResult], r14d
0x14002be63  mov     r9d, 1BDh
0x14002be69  mov     [rsp+0F0h+lpSecurityAttributes], rax
0x14002be6e  jmp     loc_14002BBF4
0x14002be73  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], r14d
0x14002be78  mov     r8d, 1BDh
0x14002be7e  mov     qword ptr [rsp+0F0h+samDesired], rax
0x14002be83  jmp     loc_14002BC23
0x14002be88  mov     rcx, r12; bstrString
0x14002be8b  call    cs:__imp_SysFreeString
0x14002be91  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14002be94  lea     r9, [rbp+57h+cchName]; lpcchName
0x14002be98  mov     edx, [rbp+57h+cSubKeys]
0x14002be9b  inc     eax
0x14002be9d  mov     rcx, [rbp+57h+hKey]; hKey
0x14002bea1  dec     edx; dwIndex
0x14002bea3  mov     [rsp+0F0h+phkResult], r14; lpftLastWriteTime
0x14002bea8  mov     r8, r13; lpName
0x14002beab  mov     [rsp+0F0h+lpSecurityAttributes], r14; lpcchClass
0x14002beb0  mov     r12, r14
0x14002beb3  mov     qword ptr [rsp+0F0h+samDesired], r14; lpClass
0x14002beb8  mov     [rbp+57h+cchName], eax
0x14002bebb  mov     [rsp+0F0h+ppv], r14; lpReserved
0x14002bec0  call    cs:__imp_RegEnumKeyExW
0x14002bec6  cmp     eax, 103h
0x14002becb  jz      loc_14002C0D1
0x14002bed1  test    eax, eax
0x14002bed3  jnz     loc_14002C06A
0x14002bed9  dec     [rbp+57h+cSubKeys]
0x14002bedc  mov     rcx, r13; psz
0x14002bedf  call    cs:__imp_SysAllocString
0x14002bee5  mov     r12, rax
0x14002bee8  test    rax, rax
0x14002beeb  jz      loc_14002BFED
0x14002bef1  mov     rcx, [rbp+57h+String1]; String1
0x14002bef5  mov     rdx, rax; String2
0x14002bef8  call    cs:__imp__wcsicmp
0x14002befe  test    eax, eax
0x14002bf00  jz      loc_14002BF86
0x14002bf06  mov     rcx, [rbp+57h+var_80]
0x14002bf0a  lea     rdx, [rbp+57h+pvarg]
0x14002bf0e  mov     r9d, 6
0x14002bf14  mov     [rsp+0F0h+ppv], rdx
0x14002bf19  mov     r8, r12
0x14002bf1c  mov     rax, [rcx]
0x14002bf1f  lea     edx, [r9-5]
0x14002bf23  mov     rax, [rax+0D8h]
0x14002bf2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bf2f  mov     ebx, eax
0x14002bf31  test    eax, eax
0x14002bf33  js      loc_14002C0D4
0x14002bf39  lea     rdx, [rbp+57h+pulRet]; pulRet
0x14002bf3d  lea     rcx, [rbp+57h+pvarg]; varIn
0x14002bf41  call    cs:__imp_VariantToUInt32
0x14002bf47  mov     ebx, eax
0x14002bf49  test    eax, eax
0x14002bf4b  js      short loc_14002BF95
0x14002bf4d  mov     r8d, [rbp+57h+pulRet]
0x14002bf51  lea     rcx, aCmanagedserver_15; "CManagedServerNotificationThread::s_Giv"...
0x14002bf58  mov     rdx, r12
0x14002bf5b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002bf60  mov     rax, [rbp+57h+pCertContext]
0x14002bf64  mov     rcx, r12; unsigned __int16 *
0x14002bf67  mov     r9, [rbp+57h+pbstr]; unsigned __int16 *
0x14002bf6b  mov     r8, [rbp+57h+String1]; unsigned __int16 *
0x14002bf6f  mov     edx, [rbp+57h+pulRet]; unsigned int
0x14002bf72  mov     [rsp+0F0h+ppv], rax; struct _CERT_CONTEXT *
0x14002bf77  call    ?s_SendOnNewServerCertificateReady@CWmsWebServiceProxy@@SAJPEAGK00PEBU_CERT_CONTEXT@@@Z; CWmsWebServiceProxy::s_SendOnNewServerCertificateReady(ushort *,ulong,ushort *,ushort *,_CERT_CONTEXT const *)
0x14002bf7c  mov     ebx, eax
0x14002bf7e  test    eax, eax
0x14002bf80  js      loc_14002C0D4
0x14002bf86  cmp     [rbp+57h+cSubKeys], r14d
0x14002bf8a  jnz     loc_14002BE88
0x14002bf90  jmp     loc_14002C0D4
0x14002bf95  lea     r15, aChra; "CHRA"
0x14002bf9c  mov     [rsp+0F0h+samDesired], ebx; int
0x14002bfa0  lea     rsi, aCmanagedserver_9; "CManagedServerNotificationThread::s_Giv"...
0x14002bfa7  mov     r9, r15; unsigned __int16 *
  ... truncated ...
```
