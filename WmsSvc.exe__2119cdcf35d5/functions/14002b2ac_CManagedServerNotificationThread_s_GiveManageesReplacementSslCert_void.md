# CManagedServerNotificationThread::s_GiveManageesReplacementSslCert(void)

- ea: `0x14002b2ac`
- end: `0x14002ba95`
- name: `?s_GiveManageesReplacementSslCert@CManagedServerNotificationThread@@SAJXZ`
- size: `2025`
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
- `0x14002b2ac`
- `0x14004c738`
- `0x140058f24`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064644`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002ba46`
- `ADVAPI32!RegCloseKey` at `0x14002ba46`
- `ADVAPI32!RegCreateKeyExW` at `0x14002b52d`
- `ADVAPI32!RegCreateKeyExW` at `0x14002b52d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002b5ec`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002b5ec`
- `ADVAPI32!RegEnumKeyExW` at `0x14002b779`
- `ADVAPI32!RegEnumKeyExW` at `0x14002b779`
- `KERNEL32!IsDebuggerPresent` at `0x14002b3f6`
- `KERNEL32!IsDebuggerPresent` at `0x14002b4c7`
- `KERNEL32!IsDebuggerPresent` at `0x14002b57e`
- `KERNEL32!IsDebuggerPresent` at `0x14002b63d`
- `KERNEL32!IsDebuggerPresent` at `0x14002b6d9`
- `KERNEL32!IsDebuggerPresent` at `0x14002b8bc`
- `KERNEL32!IsDebuggerPresent` at `0x14002b930`
- `KERNEL32!IsDebuggerPresent` at `0x14002b99e`
- `KERNEL32!IsDebuggerPresent` at `0x14002b3f6`
- `KERNEL32!IsDebuggerPresent` at `0x14002b4c7`
- `KERNEL32!IsDebuggerPresent` at `0x14002b57e`
- `KERNEL32!IsDebuggerPresent` at `0x14002b63d`
- `KERNEL32!IsDebuggerPresent` at `0x14002b6d9`
- `KERNEL32!IsDebuggerPresent` at `0x14002b8bc`
- `KERNEL32!IsDebuggerPresent` at `0x14002b930`
- `KERNEL32!IsDebuggerPresent` at `0x14002b99e`
- `msvcrt!_wcsicmp` at `0x14002b7b4`
- `msvcrt!_wcsicmp` at `0x14002b7b4`
- `CRYPT32!CertFreeCertificateContext` at `0x14002ba37`
- `CRYPT32!CertFreeCertificateContext` at `0x14002ba37`
- `ole32!CoCreateInstance` at `0x14002b483`
- `ole32!CoCreateInstance` at `0x14002b483`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b3a2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b798`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b3a2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b798`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b744`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ba1f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ba28`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b744`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ba1f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ba28`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b71a`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b9ec`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b71a`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b9ec`
- `OLEAUT32!__imp_VariantInit` at `0x14002b324`
- `OLEAUT32!__imp_VariantInit` at `0x14002b32e`
- `OLEAUT32!__imp_VariantInit` at `0x14002b324`
- `OLEAUT32!__imp_VariantInit` at `0x14002b32e`
- `OLEAUT32!__imp_VariantClear` at `0x14002b73b`
- `OLEAUT32!__imp_VariantClear` at `0x14002b9d6`
- `OLEAUT32!__imp_VariantClear` at `0x14002ba0d`
- `OLEAUT32!__imp_VariantClear` at `0x14002b73b`
- `OLEAUT32!__imp_VariantClear` at `0x14002b9d6`
- `OLEAUT32!__imp_VariantClear` at `0x14002ba0d`
- `PROPSYS!VariantToUInt32` at `0x14002b7fb`
- `PROPSYS!VariantToUInt32` at `0x14002b7fb`

## string_xrefs

- `0x14002b36d`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b3d9`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b4a4`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b55b`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b61a`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b6bc`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b899`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b913`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b97b`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b34f`: `No replacement cert, nothing to do.`
- `0x14002b2e4`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert - Start\n`
- `0x14002b35b`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b3cd`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b49a`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b551`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b610`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b6b0`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b88f`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b907`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b971`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert`
- `0x14002b83c`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert - Attempt to give replacement ssl cert to %s:%d.\n`
- `0x14002ba73`: `CManagedServerNotificationThread::s_GiveManageesReplacementSslCert - End, hr = 0x%08X\n`

## pseudocode

```c
__int64 CManagedServerNotificationThread::s_GiveManageesReplacementSslCert(void)
{
  WCHAR *v0; // r13
  OLECHAR *v1; // r12
  signed int DoesReplacementCertExist; // ebx
  unsigned __int16 *v3; // rsi
  bool v4; // zf
  const unsigned __int16 *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  HRESULT v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  __int64 v11; // rdx
  BYTE *i; // rax
  LSTATUS v13; // eax
  const wchar_t *v14; // rax
  unsigned __int16 *v15; // rdi
  HRESULT v16; // eax
  __int64 v17; // rcx
  BYTE *j; // rax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-69h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesa; // [rsp+30h] [rbp-69h]
  PHKEY phkResult; // [rsp+38h] [rbp-61h]
  PHKEY phkResulta; // [rsp+38h] [rbp-61h]
  HKEY hKey; // [rsp+60h] [rbp-39h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-31h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp-29h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp-21h] BYREF
  VARIANTARG v28; // [rsp+80h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-1h] BYREF
  DWORD cSubKeys; // [rsp+100h] [rbp+67h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+108h] [rbp+6Fh] BYREF
  ULONG pulRet; // [rsp+110h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+118h] [rbp+7Fh] BYREF

  ppv = 0;
  v0 = 0;
  cchName = 0;
  String1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pCertContext = 0;
  v1 = 0;
  memset(&v28, 0, sizeof(v28));
  pulRet = 0;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  DEBUGMSG(L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert - Start\n");
  VariantInit(&pvarg);
  VariantInit(&v28);
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
        561,
        L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
        L"No replacement cert, nothing to do.");
      goto LABEL_62;
    }
    DoesReplacementCertExist = GetLocalHostName(&String1);
    if ( DoesReplacementCertExist < 0 )
      goto LABEL_62;
    v3 = SysAllocString(L"WmsManagement");
    if ( !v3 )
    {
      DoesReplacementCertExist = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x238u,
        L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
        L"CPR",
        L"bstrUserName",
        -2147024882);
      v4 = !IsDebuggerPresent();
      v5 = L"bstrUserName";
      if ( !v4 )
      {
        v6 = 568;
LABEL_8:
        LODWORD(phkResult) = -2147024882;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          v6,
          L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
          L"CPR",
          v5,
          phkResult);
        goto LABEL_62;
      }
      v7 = 568;
      goto LABEL_10;
    }
    v8 = CoCreateInstance(&CLSID_EventNotificationService, 0, 4u, &GUID_28b159df_59eb_446b_9316_8b902f75fdf7, &ppv);
    DoesReplacementCertExist = v8;
    if ( v8 >= 0 )
    {
      v9 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows MultiPoint Server\\Managed Servers",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &hKey,
             0);
      if ( v9 )
      {
        if ( v9 > 0 )
          DoesReplacementCertExist = (unsigned __int16)v9 | 0x80070000;
        else
          DoesReplacementCertExist = v9;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          0x23Fu,
          L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
          L"CBRAEx",
          L"err == 0L",
          DoesReplacementCertExist);
        if ( IsDebuggerPresent() )
        {
          LODWORD(phkResulta) = DoesReplacementCertExist;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            575,
            L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
            L"CBRAEx",
            L"err == 0L",
            phkResulta);
        }
        else
        {
          LODWORD(lpSecurityAttributesa) = DoesReplacementCertExist;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            575,
            L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
            L"CBRAEx",
            L"err == 0L",
            lpSecurityAttributesa);
        }
      }
      else
      {
        v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( !v10 )
        {
          v0 = (WCHAR *)operator new(saturated_mul(cbMaxSubKeyLen + 1, 2u));
          if ( v0 )
          {
            if ( !cSubKeys )
              goto LABEL_62;
            while ( 1 )
            {
              if ( v28.vt == 8 && v28.llVal )
              {
                v11 = SysStringLen(v28.bstrVal);
                for ( i = v28.pbVal; v11; --v11 )
                  *i++ = 0;
                VariantClear(&v28);
              }
              SysFreeString(v1);
              v1 = 0;
              cchName = cbMaxSubKeyLen + 1;
              v13 = RegEnumKeyExW(hKey, cSubKeys - 1, v0, &cchName, 0, 0, 0, 0);
              if ( v13 == 259 )
              {
                DoesReplacementCertExist = 0;
                goto LABEL_62;
              }
              if ( v13 )
              {
                if ( v13 > 0 )
                  DoesReplacementCertExist = (unsigned __int16)v13 | 0x80070000;
                else
                  DoesReplacementCertExist = v13;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                  0x25Eu,
                  L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
                  L"CBRAEx",
                  L"err == 0L",
                  DoesReplacementCertExist);
                if ( IsDebuggerPresent() )
                {
                  LODWORD(phkResult) = DoesReplacementCertExist;
                  DEBUGMSGLEVEL(
                    2u,
                    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                    606,
                    L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
                    L"CBRAEx",
                    L"err == 0L",
                    phkResult);
                }
                else
                {
                  LODWORD(lpSecurityAttributes) = DoesReplacementCertExist;
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                    606,
                    L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
                    L"CBRAEx",
                    L"err == 0L",
                    lpSecurityAttributes);
                }
                goto LABEL_62;
              }
              --cSubKeys;
              v14 = SysAllocString(v0);
              v1 = (OLECHAR *)v14;
              if ( !v14 )
                break;
              v15 = String1;
              if ( _wcsicmp(String1, v14) )
              {
                DoesReplacementCertExist = (*(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64, VARIANTARG *))(*(_QWORD *)ppv + 216LL))(
                                             ppv,
                                             0,
                                             v1,
                                             6,
                                             &pvarg);
                if ( DoesReplacementCertExist < 0 )
                  goto LABEL_62;
                v16 = VariantToUInt32(&pvarg, &pulRet);
                DoesReplacementCertExist = v16;
                if ( v16 < 0 )
                {
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                    0x272u,
                    L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
                    L"CHRA",
                    L"hr",
                    v16);
                  if ( IsDebuggerPresent() )
                  {
                    LODWORD(phkResult) = DoesReplacementCertExist;
                    DEBUGMSGLEVEL(
                      2u,
                      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                      626,
                      L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
                      L"CHRA",
                      L"hr",
                      phkResult);
                  }
                  else
                  {
                    LODWORD(lpSecurityAttributes) = DoesReplacementCertExist;
                    DEBUGMSGBOX(
                      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                      626,
                      L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
                      L"CHRA",
                      L"hr",
                      lpSecurityAttributes);
                  }
                  goto LABEL_62;
                }
                DoesReplacementCertExist = (*(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64, VARIANTARG *))(*(_QWORD *)ppv + 216LL))(
                                             ppv,
                                             0,
                                             v1,
                                             2,
                                             &v28);
                if ( DoesReplacementCertExist < 0 )
                  goto LABEL_62;
                DEBUGMSG(
                  L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert - Attempt to give replacement ssl cert to %s:%d.\n",
                  v1,
                  pulRet);
                DoesReplacementCertExist = CWmsWebServiceProxy::s_SetReplacementSslCertificate(
                                             v1,
                                             pulRet,
                                             v3,
                                             v28.bstrVal,
                                             v15,
                                             pCertContext);
                if ( DoesReplacementCertExist < 0 )
                  goto LABEL_62;
              }
              if ( !cSubKeys )
                goto LABEL_62;
            }
            DoesReplacementCertExist = -2147024882;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              0x263u,
              L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
              L"CPR",
              L"bstrFqdnRemoteHost",
              -2147024882);
            v4 = !IsDebuggerPresent();
            v5 = L"bstrFqdnRemoteHost";
            if ( !v4 )
            {
              v6 = 611;
              goto LABEL_8;
            }
            v7 = 611;
          }
          else
          {
            DoesReplacementCertExist = -2147024882;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              0x247u,
              L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
              L"CPR",
              L"pszSubKeyNameBuffer",
              -2147024882);
            v4 = !IsDebuggerPresent();
            v5 = L"pszSubKeyNameBuffer";
            if ( !v4 )
            {
              v6 = 583;
              goto LABEL_8;
            }
            v7 = 583;
          }
LABEL_10:
          LODWORD(lpSecurityAttributes) = -2147024882;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            v7,
            L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
            L"CPR",
            v5,
            lpSecurityAttributes);
          goto LABEL_62;
        }
        if ( v10 > 0 )
          DoesReplacementCertExist = (unsigned __int16)v10 | 0x80070000;
        else
          DoesReplacementCertExist = v10;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          0x243u,
          L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
          L"CBRAEx",
          L"err == 0L",
          DoesReplacementCertExist);
        if ( IsDebuggerPresent() )
        {
          LODWORD(phkResult) = DoesReplacementCertExist;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            579,
            L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
            L"CBRAEx",
            L"err == 0L",
            phkResult);
        }
        else
        {
          LODWORD(lpSecurityAttributes) = DoesReplacementCertExist;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            579,
            L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
            L"CBRAEx",
            L"err == 0L",
            lpSecurityAttributes);
        }
      }
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x23Cu,
        L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
        L"CHRA",
        L"hr",
        v8);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          572,
          L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
          L"CHRA",
          L"hr",
          DoesReplacementCertExist);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          572,
          L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert",
          L"CHRA",
          L"hr",
          DoesReplacementCertExist);
    }
  }
LABEL_62:
  VariantClear(&pvarg);
  if ( v28.vt == 8 && v28.llVal )
  {
    v17 = SysStringLen(v28.bstrVal);
    for ( j = v28.pbVal; v17; --v17 )
      *j++ = 0;
    VariantClear(&v28);
  }
  operator delete(v0);
  SysFreeString(String1);
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
  DEBUGMSG(
    L"CManagedServerNotificationThread::s_GiveManageesReplacementSslCert - End, hr = 0x%08X\n",
    (unsigned int)DoesReplacementCertExist);
  return (unsigned int)DoesReplacementCertExist;
}

```

## disassembly

```asm
0x14002b2ac  push    rbp
0x14002b2ae  push    rbx
0x14002b2af  push    rsi
0x14002b2b0  push    rdi
0x14002b2b1  push    r12
0x14002b2b3  push    r13
0x14002b2b5  push    r14
0x14002b2b7  push    r15
0x14002b2b9  lea     rbp, [rsp-1Fh]
0x14002b2be  sub     rsp, 0B8h
0x14002b2c5  xor     eax, eax
0x14002b2c7  mov     [rbp+57h+var_88], 0
0x14002b2cf  xor     r13d, r13d
0x14002b2d2  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14002b2d6  xorps   xmm0, xmm0
0x14002b2d9  mov     [rbp+57h+cchName], r13d
0x14002b2dd  xorps   xmm1, xmm1
0x14002b2e0  mov     [rbp+57h+String1], r13
0x14002b2e4  lea     rcx, aCmanagedserver; "CManagedServerNotificationThread::s_Giv"...
0x14002b2eb  mov     qword ptr [rbp+57h+var_70+10h], rax
0x14002b2ef  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14002b2f3  mov     [rbp+57h+pCertContext], rax
0x14002b2f7  xor     r12d, r12d
0x14002b2fa  movups  xmmword ptr [rbp+57h+var_70], xmm1
0x14002b2fe  mov     [rbp+57h+pulRet], 0
0x14002b305  mov     [rbp+57h+hKey], 0
0x14002b30d  mov     [rbp+57h+cSubKeys], 0
0x14002b314  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x14002b31b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002b320  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002b324  call    cs:__imp_VariantInit
0x14002b32a  lea     rcx, [rbp+57h+var_70]; pvarg
0x14002b32e  call    cs:__imp_VariantInit
0x14002b334  lea     rcx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT **
0x14002b338  call    ?s_DoesReplacementCertExist@CWmsWebService@@SAJPEAPEBU_CERT_CONTEXT@@@Z; CWmsWebService::s_DoesReplacementCertExist(_CERT_CONTEXT const * *)
0x14002b33d  mov     ebx, eax
0x14002b33f  test    eax, eax
0x14002b341  js      loc_14002B9D2
0x14002b347  cmp     [rbp+57h+pCertContext], r12
0x14002b34b  jnz     short loc_14002B388
0x14002b34d  xor     ebx, ebx
0x14002b34f  lea     rax, aNoReplacementC; "No replacement cert, nothing to do."
0x14002b356  mov     qword ptr [rsp+0F0h+samDesired], rax
0x14002b35b  lea     rsi, aCmanagedserver_3; "CManagedServerNotificationThread::s_Giv"...
0x14002b362  mov     r9d, 231h
0x14002b368  mov     [rsp+0F0h+ppv], rsi
0x14002b36d  lea     r8, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002b374  lea     ecx, [rbx+4]; unsigned __int8
0x14002b377  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002b37e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002b383  jmp     loc_14002B9D2
0x14002b388  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x14002b38c  call    ?GetLocalHostName@@YAJPEAPEAG@Z; GetLocalHostName(ushort * *)
0x14002b391  mov     ebx, eax
0x14002b393  test    eax, eax
0x14002b395  js      loc_14002B9D2
0x14002b39b  lea     rcx, aWmsmanagement_0; "WmsManagement"
0x14002b3a2  call    cs:__imp_SysAllocString
0x14002b3a8  mov     rsi, rax
0x14002b3ab  test    rax, rax
0x14002b3ae  jnz     loc_14002B466
0x14002b3b4  mov     r14d, 8007000Eh
0x14002b3ba  lea     rax, aBstrusername; "bstrUserName"
0x14002b3c1  lea     r15, aCpr; "CPR"
0x14002b3c8  mov     [rsp+0F0h+samDesired], r14d; int
0x14002b3cd  lea     rsi, aCmanagedserver_3; "CManagedServerNotificationThread::s_Giv"...
0x14002b3d4  mov     [rsp+0F0h+ppv], rax; unsigned __int16 *
0x14002b3d9  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002b3e0  mov     r9, r15; unsigned __int16 *
0x14002b3e3  mov     r8, rsi; unsigned __int16 *
0x14002b3e6  mov     rcx, rdi; unsigned __int16 *
0x14002b3e9  mov     edx, 238h; unsigned int
0x14002b3ee  mov     ebx, r14d
0x14002b3f1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002b3f6  call    cs:__imp_IsDebuggerPresent
0x14002b3fc  test    eax, eax
0x14002b3fe  lea     rax, aBstrusername; "bstrUserName"
0x14002b405  jz      short loc_14002B43A
0x14002b407  mov     r9d, 238h
0x14002b40d  mov     dword ptr [rsp+0F0h+phkResult], r14d
0x14002b412  mov     [rsp+0F0h+lpSecurityAttributes], rax
0x14002b417  mov     qword ptr [rsp+0F0h+samDesired], r15
0x14002b41c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002b423  mov     r8, rdi
0x14002b426  mov     [rsp+0F0h+ppv], rsi
0x14002b42b  mov     ecx, 2; unsigned __int8
0x14002b430  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002b435  jmp     loc_14002B9D2
0x14002b43a  mov     r8d, 238h
0x14002b440  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], r14d
0x14002b445  mov     qword ptr [rsp+0F0h+samDesired], rax
0x14002b44a  mov     r9, rsi
0x14002b44d  mov     [rsp+0F0h+ppv], r15
0x14002b452  mov     rdx, rdi
0x14002b455  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002b45c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002b461  jmp     loc_14002B9D2
0x14002b466  xor     edx, edx; pUnkOuter
0x14002b468  lea     rax, [rbp+57h+var_88]
0x14002b46c  lea     r9, _GUID_28b159df_59eb_446b_9316_8b902f75fdf7; riid
0x14002b473  mov     [rsp+0F0h+ppv], rax; ppv
0x14002b478  lea     rcx, CLSID_EventNotificationService; rclsid
0x14002b47f  lea     r8d, [rdx+4]; dwClsContext
0x14002b483  call    cs:__imp_CoCreateInstance
0x14002b489  mov     ebx, eax
0x14002b48b  test    eax, eax
0x14002b48d  jns     short loc_14002B4F9
0x14002b48f  mov     [rsp+0F0h+samDesired], eax; int
0x14002b493  lea     r15, aChra; "CHRA"
0x14002b49a  lea     rsi, aCmanagedserver_3; "CManagedServerNotificationThread::s_Giv"...
0x14002b4a1  mov     r9, r15; unsigned __int16 *
0x14002b4a4  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002b4ab  mov     r8, rsi; unsigned __int16 *
0x14002b4ae  lea     r14, aHr; "hr"
0x14002b4b5  mov     rcx, rdi; unsigned __int16 *
0x14002b4b8  mov     edx, 23Ch; unsigned int
0x14002b4bd  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x14002b4c2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002b4c7  call    cs:__imp_IsDebuggerPresent
0x14002b4cd  test    eax, eax
0x14002b4cf  jz      short loc_14002B4E5
0x14002b4d1  mov     dword ptr [rsp+0F0h+phkResult], ebx
0x14002b4d5  mov     r9d, 23Ch
0x14002b4db  mov     [rsp+0F0h+lpSecurityAttributes], r14
0x14002b4e0  jmp     loc_14002B417
0x14002b4e5  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], ebx
0x14002b4e9  mov     r8d, 23Ch
0x14002b4ef  mov     qword ptr [rsp+0F0h+samDesired], r14
0x14002b4f4  jmp     loc_14002B44A
0x14002b4f9  mov     [rsp+0F0h+lpdwDisposition], r12; lpdwDisposition
0x14002b4fe  lea     rax, [rbp+57h+hKey]
0x14002b502  mov     [rsp+0F0h+phkResult], rax; phkResult
0x14002b507  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows MultiPoint"...
0x14002b50e  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x14002b513  xor     r9d, r9d; lpClass
0x14002b516  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x14002b51e  xor     r8d, r8d; Reserved
0x14002b521  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002b528  mov     dword ptr [rsp+0F0h+ppv], r12d; dwOptions
0x14002b52d  call    cs:__imp_RegCreateKeyExW
0x14002b533  test    eax, eax
0x14002b535  jz      short loc_14002B5B0
0x14002b537  jg      short loc_14002B53D
0x14002b539  mov     ebx, eax
0x14002b53b  jmp     short loc_14002B546
0x14002b53d  movzx   ebx, ax
0x14002b540  or      ebx, 80070000h
0x14002b546  lea     r15, aCbraex; "CBRAEx"
0x14002b54d  mov     [rsp+0F0h+samDesired], ebx; int
0x14002b551  lea     rsi, aCmanagedserver_3; "CManagedServerNotificationThread::s_Giv"...
0x14002b558  mov     r9, r15; unsigned __int16 *
0x14002b55b  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002b562  mov     r8, rsi; unsigned __int16 *
0x14002b565  lea     r14, aErr0l; "err == 0L"
0x14002b56c  mov     rcx, rdi; unsigned __int16 *
0x14002b56f  mov     edx, 23Fh; unsigned int
0x14002b574  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x14002b579  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002b57e  call    cs:__imp_IsDebuggerPresent
0x14002b584  test    eax, eax
0x14002b586  jz      short loc_14002B59C
0x14002b588  mov     dword ptr [rsp+0F0h+phkResult], ebx
0x14002b58c  mov     r9d, 23Fh
0x14002b592  mov     [rsp+0F0h+lpSecurityAttributes], r14
0x14002b597  jmp     loc_14002B417
0x14002b59c  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], ebx
0x14002b5a0  mov     r8d, 23Fh
0x14002b5a6  mov     qword ptr [rsp+0F0h+samDesired], r14
0x14002b5ab  jmp     loc_14002B44A
0x14002b5b0  mov     rcx, [rbp+57h+hKey]; hKey
0x14002b5b4  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14002b5b8  mov     [rsp+0F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14002b5bd  xor     r9d, r9d; lpReserved
0x14002b5c0  mov     [rsp+0F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14002b5c5  xor     r8d, r8d; lpcchClass
0x14002b5c8  mov     [rsp+0F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x14002b5cd  xor     edx, edx; lpClass
0x14002b5cf  mov     [rsp+0F0h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x14002b5d4  mov     [rsp+0F0h+phkResult], r12; lpcValues
0x14002b5d9  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x14002b5de  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbMaxSubKeyLen
0x14002b5e3  lea     rax, [rbp+57h+cSubKeys]
0x14002b5e7  mov     [rsp+0F0h+ppv], rax; lpcSubKeys
0x14002b5ec  call    cs:__imp_RegQueryInfoKeyW
0x14002b5f2  test    eax, eax
0x14002b5f4  jz      short loc_14002B66F
0x14002b5f6  jg      short loc_14002B5FC
0x14002b5f8  mov     ebx, eax
0x14002b5fa  jmp     short loc_14002B605
0x14002b5fc  movzx   ebx, ax
0x14002b5ff  or      ebx, 80070000h
0x14002b605  lea     r15, aCbraex; "CBRAEx"
0x14002b60c  mov     [rsp+0F0h+samDesired], ebx; int
0x14002b610  lea     rsi, aCmanagedserver_3; "CManagedServerNotificationThread::s_Giv"...
0x14002b617  mov     r9, r15; unsigned __int16 *
0x14002b61a  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002b621  mov     r8, rsi; unsigned __int16 *
0x14002b624  lea     r14, aErr0l; "err == 0L"
0x14002b62b  mov     rcx, rdi; unsigned __int16 *
0x14002b62e  mov     edx, 243h; unsigned int
0x14002b633  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x14002b638  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002b63d  call    cs:__imp_IsDebuggerPresent
0x14002b643  test    eax, eax
0x14002b645  jz      short loc_14002B65B
0x14002b647  mov     dword ptr [rsp+0F0h+phkResult], ebx
0x14002b64b  mov     r9d, 243h
0x14002b651  mov     [rsp+0F0h+lpSecurityAttributes], r14
0x14002b656  jmp     loc_14002B417
0x14002b65b  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], ebx
0x14002b65f  mov     r8d, 243h
0x14002b665  mov     qword ptr [rsp+0F0h+samDesired], r14
0x14002b66a  jmp     loc_14002B44A
0x14002b66f  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x14002b672  mov     eax, 2
0x14002b677  inc     ecx
0x14002b679  mul     rcx
0x14002b67c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002b683  cmovb   rax, rcx
0x14002b687  mov     rcx, rax; Size
0x14002b68a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002b68f  mov     r13, rax
0x14002b692  test    rax, rax
0x14002b695  jnz     short loc_14002B700
0x14002b697  mov     r14d, 8007000Eh
0x14002b69d  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002b6a4  lea     r15, aCpr; "CPR"
0x14002b6ab  mov     [rsp+0F0h+samDesired], r14d; int
0x14002b6b0  lea     rsi, aCmanagedserver_3; "CManagedServerNotificationThread::s_Giv"...
0x14002b6b7  mov     [rsp+0F0h+ppv], rax; unsigned __int16 *
0x14002b6bc  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002b6c3  mov     r9, r15; unsigned __int16 *
0x14002b6c6  mov     r8, rsi; unsigned __int16 *
0x14002b6c9  mov     rcx, rdi; unsigned __int16 *
0x14002b6cc  mov     edx, 247h; unsigned int
0x14002b6d1  mov     ebx, r14d
0x14002b6d4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002b6d9  call    cs:__imp_IsDebuggerPresent
0x14002b6df  test    eax, eax
0x14002b6e1  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002b6e8  jz      short loc_14002B6F5
0x14002b6ea  mov     r9d, 247h
0x14002b6f0  jmp     loc_14002B40D
0x14002b6f5  mov     r8d, 247h
0x14002b6fb  jmp     loc_14002B440
0x14002b700  cmp     [rbp+57h+cSubKeys], r12d
0x14002b704  jz      loc_14002B9D2
0x14002b70a  cmp     word ptr [rbp+57h+var_70], 8
0x14002b70f  jnz     short loc_14002B741
0x14002b711  mov     rcx, qword ptr [rbp+57h+var_70+8]; pbstr
0x14002b715  test    rcx, rcx
0x14002b718  jz      short loc_14002B741
0x14002b71a  call    cs:__imp_SysStringLen
0x14002b720  mov     edx, eax
0x14002b722  mov     rax, qword ptr [rbp+57h+var_70+8]
0x14002b726  test    rdx, rdx
0x14002b729  jz      short loc_14002B737
0x14002b72b  mov     byte ptr [rax], 0
0x14002b72e  inc     rax
0x14002b731  sub     rdx, 1
0x14002b735  jnz     short loc_14002B72B
0x14002b737  lea     rcx, [rbp+57h+var_70]; pvarg
0x14002b73b  call    cs:__imp_VariantClear
0x14002b741  mov     rcx, r12; bstrString
0x14002b744  call    cs:__imp_SysFreeString
0x14002b74a  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14002b74d  lea     r9, [rbp+57h+cchName]; lpcchName
0x14002b751  mov     edx, [rbp+57h+cSubKeys]
0x14002b754  xor     r12d, r12d
0x14002b757  mov     rcx, [rbp+57h+hKey]; hKey
0x14002b75b  inc     eax
0x14002b75d  mov     [rsp+0F0h+phkResult], r12; lpftLastWriteTime
0x14002b762  dec     edx; dwIndex
0x14002b764  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpcchClass
0x14002b769  mov     r8, r13; lpName
0x14002b76c  mov     qword ptr [rsp+0F0h+samDesired], r12; lpClass
0x14002b771  mov     [rbp+57h+cchName], eax
0x14002b774  mov     [rsp+0F0h+ppv], r12; lpReserved
0x14002b779  call    cs:__imp_RegEnumKeyExW
0x14002b77f  cmp     eax, 103h
0x14002b784  jz      loc_14002B9D0
0x14002b78a  test    eax, eax
0x14002b78c  jnz     loc_14002B957
0x14002b792  dec     [rbp+57h+cSubKeys]
0x14002b795  mov     rcx, r13; psz
0x14002b798  call    cs:__imp_SysAllocString
0x14002b79e  mov     r12, rax
0x14002b7a1  test    rax, rax
0x14002b7a4  jz      loc_14002B8EE
0x14002b7aa  mov     rdi, [rbp+57h+String1]
0x14002b7ae  mov     rdx, rax; String2
0x14002b7b1  mov     rcx, rdi; String1
0x14002b7b4  call    cs:__imp__wcsicmp
0x14002b7ba  test    eax, eax
0x14002b7bc  jz      loc_14002B875
0x14002b7c2  mov     rcx, [rbp+57h+var_88]
0x14002b7c6  lea     rdx, [rbp+57h+pvarg]
0x14002b7ca  mov     [rsp+0F0h+ppv], rdx
0x14002b7cf  mov     r9d, 6
0x14002b7d5  mov     r8, r12
  ... truncated ...
```
