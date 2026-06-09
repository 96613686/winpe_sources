# CManagedServerNotificationThread::s_GetManageesReplacementSslCert(void)

- ea: `0x14002aa70`
- end: `0x14002b2a5`
- name: `?s_GetManageesReplacementSslCert@CManagedServerNotificationThread@@KAJXZ`
- size: `2101`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002a960`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14002aa70`
- `0x140057ed8`
- `0x1400599e4`
- `0x14005b418`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064644`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002b256`
- `ADVAPI32!RegCloseKey` at `0x14002b256`
- `ADVAPI32!RegCreateKeyExW` at `0x14002aca1`
- `ADVAPI32!RegCreateKeyExW` at `0x14002aca1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002ad60`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002ad60`
- `ADVAPI32!RegEnumKeyExW` at `0x14002af54`
- `ADVAPI32!RegEnumKeyExW` at `0x14002af54`
- `KERNEL32!IsDebuggerPresent` at `0x14002ab6b`
- `KERNEL32!IsDebuggerPresent` at `0x14002ac3c`
- `KERNEL32!IsDebuggerPresent` at `0x14002acf2`
- `KERNEL32!IsDebuggerPresent` at `0x14002adb1`
- `KERNEL32!IsDebuggerPresent` at `0x14002ae55`
- `KERNEL32!IsDebuggerPresent` at `0x14002b0cd`
- `KERNEL32!IsDebuggerPresent` at `0x14002b141`
- `KERNEL32!IsDebuggerPresent` at `0x14002b1af`
- `KERNEL32!IsDebuggerPresent` at `0x14002ab6b`
- `KERNEL32!IsDebuggerPresent` at `0x14002ac3c`
- `KERNEL32!IsDebuggerPresent` at `0x14002acf2`
- `KERNEL32!IsDebuggerPresent` at `0x14002adb1`
- `KERNEL32!IsDebuggerPresent` at `0x14002ae55`
- `KERNEL32!IsDebuggerPresent` at `0x14002b0cd`
- `KERNEL32!IsDebuggerPresent` at `0x14002b141`
- `KERNEL32!IsDebuggerPresent` at `0x14002b1af`
- `msvcrt!_wcsicmp` at `0x14002af8c`
- `msvcrt!_wcsicmp` at `0x14002af8c`
- `CRYPT32!CertFreeCertificateContext` at `0x14002af1b`
- `CRYPT32!CertFreeCertificateContext` at `0x14002b247`
- `CRYPT32!CertFreeCertificateContext` at `0x14002af1b`
- `CRYPT32!CertFreeCertificateContext` at `0x14002b247`
- `ole32!CoCreateInstance` at `0x14002abf8`
- `ole32!CoCreateInstance` at `0x14002abf8`
- `OLEAUT32!__imp_SysAllocString` at `0x14002ab17`
- `OLEAUT32!__imp_SysAllocString` at `0x14002af73`
- `OLEAUT32!__imp_SysAllocString` at `0x14002ab17`
- `OLEAUT32!__imp_SysAllocString` at `0x14002af73`
- `OLEAUT32!__imp_SysFreeString` at `0x14002af0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b230`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b239`
- `OLEAUT32!__imp_SysFreeString` at `0x14002af0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b230`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b239`
- `OLEAUT32!__imp_SysStringLen` at `0x14002aee0`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b1fd`
- `OLEAUT32!__imp_SysStringLen` at `0x14002aee0`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b1fd`
- `OLEAUT32!__imp_VariantInit` at `0x14002aaed`
- `OLEAUT32!__imp_VariantInit` at `0x14002aaf7`
- `OLEAUT32!__imp_VariantInit` at `0x14002aaed`
- `OLEAUT32!__imp_VariantInit` at `0x14002aaf7`
- `OLEAUT32!__imp_VariantClear` at `0x14002af01`
- `OLEAUT32!__imp_VariantClear` at `0x14002b1e7`
- `OLEAUT32!__imp_VariantClear` at `0x14002b21e`
- `OLEAUT32!__imp_VariantClear` at `0x14002af01`
- `OLEAUT32!__imp_VariantClear` at `0x14002b1e7`
- `OLEAUT32!__imp_VariantClear` at `0x14002b21e`
- `PROPSYS!VariantToUInt32` at `0x14002afd3`
- `PROPSYS!VariantToUInt32` at `0x14002afd3`

## string_xrefs

- `0x14002ab4e`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002ac19`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002accf`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002ad8e`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002ae38`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b0aa`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b124`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002b18c`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002aaad`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert - Start\n`
- `0x14002ab42`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002ac0f`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002acc5`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002ad84`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002ae2c`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002b0a0`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002b118`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002b182`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert`
- `0x14002b018`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert - Attempt to get replacement ssl cert from %s:%d.\n`
- `0x14002b283`: `CManagedServerNotificationThread::s_GetManageesReplacementSslCert - End, hr = 0x%08X\n`

## pseudocode

```c
__int64 CManagedServerNotificationThread::s_GetManageesReplacementSslCert(void)
{
  WCHAR *v0; // rsi
  struct _CERT_CONTEXT *v1; // r14
  OLECHAR *v2; // r13
  int LocalHostName; // ebx
  unsigned __int16 *v4; // rdi
  HRESULT v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  bool v8; // zf
  const unsigned __int16 *v9; // rax
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  BYTE *i; // rax
  LSTATUS v14; // eax
  const wchar_t *v15; // rax
  HRESULT v16; // eax
  int ReplacementSslCertificate; // eax
  __int64 v18; // rdx
  BYTE *j; // rax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-79h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesa; // [rsp+30h] [rbp-79h]
  PHKEY phkResult; // [rsp+38h] [rbp-71h]
  PHKEY phkResulta; // [rsp+38h] [rbp-71h]
  WCHAR *v25; // [rsp+60h] [rbp-49h]
  HKEY hKey; // [rsp+68h] [rbp-41h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-39h] BYREF
  struct _CERT_CONTEXT *v28; // [rsp+78h] [rbp-31h] BYREF
  VARIANTARG v29; // [rsp+80h] [rbp-29h] BYREF
  wchar_t *String1; // [rsp+98h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-9h] BYREF
  DWORD cSubKeys; // [rsp+110h] [rbp+67h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+118h] [rbp+6Fh] BYREF
  ULONG pulRet; // [rsp+120h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+128h] [rbp+7Fh] BYREF

  v0 = 0;
  ppv = 0;
  cchName = 0;
  String1 = 0;
  v1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v28 = 0;
  v2 = 0;
  memset(&v29, 0, sizeof(v29));
  pulRet = 0;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  DEBUGMSG(L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert - Start\n");
  VariantInit(&pvarg);
  VariantInit(&v29);
  LocalHostName = GetLocalHostName(&String1);
  if ( LocalHostName >= 0 )
  {
    v4 = SysAllocString(L"WmsManagement");
    if ( !v4 )
    {
      LocalHostName = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x100u,
        L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
        L"CPR",
        L"bstrUserName",
        -2147024882);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          256,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CPR",
          L"bstrUserName",
          -2147024882);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          256,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CPR",
          L"bstrUserName",
          -2147024882);
LABEL_6:
      v0 = 0;
      goto LABEL_66;
    }
    v5 = CoCreateInstance(&CLSID_EventNotificationService, 0, 4u, &GUID_28b159df_59eb_446b_9316_8b902f75fdf7, &ppv);
    LocalHostName = v5;
    if ( v5 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x104u,
        L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
        L"CHRA",
        L"hr",
        v5);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          260,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CHRA",
          L"hr",
          LocalHostName);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          260,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CHRA",
          L"hr",
          LocalHostName);
      goto LABEL_6;
    }
    v6 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows MultiPoint Server\\Managed Servers",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           0);
    if ( v6 )
    {
      if ( v6 > 0 )
        LocalHostName = (unsigned __int16)v6 | 0x80070000;
      else
        LocalHostName = v6;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x107u,
        L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
        L"CBRAEx",
        L"err == 0L",
        LocalHostName);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = LocalHostName;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          263,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CBRAEx",
          L"err == 0L",
          phkResult);
      }
      else
      {
        LODWORD(lpSecurityAttributes) = LocalHostName;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          263,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CBRAEx",
          L"err == 0L",
          lpSecurityAttributes);
      }
      goto LABEL_6;
    }
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v7 )
    {
      if ( v7 > 0 )
        LocalHostName = (unsigned __int16)v7 | 0x80070000;
      else
        LocalHostName = v7;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x10Bu,
        L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
        L"CBRAEx",
        L"err == 0L",
        LocalHostName);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResulta) = LocalHostName;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          267,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CBRAEx",
          L"err == 0L",
          phkResulta);
      }
      else
      {
        LODWORD(lpSecurityAttributesa) = LocalHostName;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          267,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CBRAEx",
          L"err == 0L",
          lpSecurityAttributesa);
      }
      goto LABEL_6;
    }
    v25 = (WCHAR *)operator new(saturated_mul(cbMaxSubKeyLen + 1, 2u));
    v0 = v25;
    if ( v25 )
    {
      if ( !cSubKeys )
        goto LABEL_66;
      while ( 1 )
      {
        if ( v29.vt == 8 && v29.llVal )
        {
          v12 = SysStringLen(v29.bstrVal);
          for ( i = v29.pbVal; v12; --v12 )
            *i++ = 0;
          VariantClear(&v29);
        }
        SysFreeString(v2);
        v2 = 0;
        if ( v1 )
        {
          CertFreeCertificateContext(v1);
          v1 = 0;
          v28 = 0;
        }
        cchName = cbMaxSubKeyLen + 1;
        v14 = RegEnumKeyExW(hKey, cSubKeys - 1, v25, &cchName, 0, 0, 0, 0);
        if ( v14 == 259 )
        {
          LocalHostName = 0;
          goto LABEL_66;
        }
        if ( v14 )
        {
          if ( v14 > 0 )
            LocalHostName = (unsigned __int16)v14 | 0x80070000;
          else
            LocalHostName = v14;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
            0x12Cu,
            L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
            L"CBRAEx",
            L"err == 0L",
            LocalHostName);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResulta) = LocalHostName;
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              300,
              L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
              L"CBRAEx",
              L"err == 0L",
              phkResulta);
          }
          else
          {
            LODWORD(lpSecurityAttributesa) = LocalHostName;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              300,
              L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
              L"CBRAEx",
              L"err == 0L",
              lpSecurityAttributesa);
          }
          goto LABEL_31;
        }
        --cSubKeys;
        v15 = SysAllocString(v25);
        v2 = (OLECHAR *)v15;
        if ( !v15 )
          break;
        if ( _wcsicmp(String1, v15) )
        {
          LocalHostName = (*(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64, VARIANTARG *))(*(_QWORD *)ppv + 216LL))(
                            ppv,
                            0,
                            v2,
                            6,
                            &pvarg);
          if ( LocalHostName < 0 )
            goto LABEL_66;
          v16 = VariantToUInt32(&pvarg, &pulRet);
          LocalHostName = v16;
          if ( v16 < 0 )
          {
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
              0x140u,
              L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
              L"CHRA",
              L"hr",
              v16);
            if ( IsDebuggerPresent() )
            {
              LODWORD(phkResulta) = LocalHostName;
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                320,
                L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
                L"CHRA",
                L"hr",
                phkResulta);
            }
            else
            {
              LODWORD(lpSecurityAttributesa) = LocalHostName;
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
                320,
                L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
                L"CHRA",
                L"hr",
                lpSecurityAttributesa);
            }
            goto LABEL_31;
          }
          LocalHostName = (*(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64, VARIANTARG *))(*(_QWORD *)ppv + 216LL))(
                            ppv,
                            0,
                            v2,
                            2,
                            &v29);
          if ( LocalHostName < 0 )
            goto LABEL_66;
          DEBUGMSG(
            L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert - Attempt to get replacement ssl cert from %s:%d.\n",
            v2,
            pulRet);
          ReplacementSslCertificate = CWmsWebServiceProxy::s_GetReplacementSslCertificate(
                                        v2,
                                        pulRet,
                                        v4,
                                        v29.bstrVal,
                                        (const struct _CERT_CONTEXT **)&v28);
          v1 = v28;
          LocalHostName = ReplacementSslCertificate;
          if ( ReplacementSslCertificate < 0 )
            goto LABEL_66;
          if ( v28 )
          {
            LocalHostName = VerifySslCertificate(v2, v28->pbCertEncoded, v28->cbCertEncoded);
            if ( LocalHostName < 0 )
              goto LABEL_66;
            LocalHostName = AddSerializedCertificateToStore(v1->pbCertEncoded, v1->cbCertEncoded);
            if ( LocalHostName < 0 )
              goto LABEL_66;
          }
        }
        if ( !cSubKeys )
          goto LABEL_66;
      }
      LocalHostName = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x131u,
        L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
        L"CPR",
        L"bstrFqdnRemoteHost",
        -2147024882);
      v8 = !IsDebuggerPresent();
      v9 = L"bstrFqdnRemoteHost";
      if ( !v8 )
      {
        v10 = 305;
        goto LABEL_28;
      }
      v11 = 305;
    }
    else
    {
      LocalHostName = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0x10Fu,
        L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
        L"CPR",
        L"pszSubKeyNameBuffer",
        -2147024882);
      v8 = !IsDebuggerPresent();
      v9 = L"pszSubKeyNameBuffer";
      if ( !v8 )
      {
        v10 = 271;
LABEL_28:
        LODWORD(phkResulta) = -2147024882;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          v10,
          L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
          L"CPR",
          v9,
          phkResulta);
        goto LABEL_31;
      }
      v11 = 271;
    }
    LODWORD(lpSecurityAttributesa) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
      v11,
      L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert",
      L"CPR",
      v9,
      lpSecurityAttributesa);
LABEL_31:
    v0 = v25;
  }
LABEL_66:
  VariantClear(&pvarg);
  if ( v29.vt == 8 && v29.llVal )
  {
    v18 = SysStringLen(v29.bstrVal);
    for ( j = v29.pbVal; v18; --v18 )
      *j++ = 0;
    VariantClear(&v29);
  }
  operator delete(v0);
  SysFreeString(String1);
  SysFreeString(v2);
  if ( v1 )
    CertFreeCertificateContext(v1);
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
    L"CManagedServerNotificationThread::s_GetManageesReplacementSslCert - End, hr = 0x%08X\n",
    (unsigned int)LocalHostName);
  return (unsigned int)LocalHostName;
}

```

## disassembly

```asm
0x14002aa70  push    rbp
0x14002aa72  push    rbx
0x14002aa73  push    rsi
0x14002aa74  push    rdi
0x14002aa75  push    r12
0x14002aa77  push    r13
0x14002aa79  push    r14
0x14002aa7b  push    r15
0x14002aa7d  lea     rbp, [rsp-1Fh]
0x14002aa82  sub     rsp, 0C8h
0x14002aa89  xor     esi, esi
0x14002aa8b  mov     [rbp+57h+var_90], 0
0x14002aa93  xor     eax, eax
0x14002aa95  mov     [rbp+57h+var_A0], rsi
0x14002aa99  xorps   xmm0, xmm0
0x14002aa9c  mov     [rbp+57h+cchName], esi
0x14002aa9f  xorps   xmm1, xmm1
0x14002aaa2  mov     [rbp+57h+String1], rsi
0x14002aaa6  xor     r14d, r14d
0x14002aaa9  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14002aaad  lea     rcx, aCmanagedserver_7; "CManagedServerNotificationThread::s_Get"...
0x14002aab4  mov     qword ptr [rbp+57h+var_80+10h], rax
0x14002aab8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14002aabc  mov     [rbp+57h+var_88], r14
0x14002aac0  xor     r13d, r13d
0x14002aac3  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x14002aac7  mov     [rbp+57h+pulRet], 0
0x14002aace  mov     [rbp+57h+hKey], 0
0x14002aad6  mov     [rbp+57h+cSubKeys], 0
0x14002aadd  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x14002aae4  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002aae9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002aaed  call    cs:__imp_VariantInit
0x14002aaf3  lea     rcx, [rbp+57h+var_80]; pvarg
0x14002aaf7  call    cs:__imp_VariantInit
0x14002aafd  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x14002ab01  call    ?GetLocalHostName@@YAJPEAPEAG@Z; GetLocalHostName(ushort * *)
0x14002ab06  mov     ebx, eax
0x14002ab08  test    eax, eax
0x14002ab0a  js      loc_14002B1E3
0x14002ab10  lea     rcx, aWmsmanagement_0; "WmsManagement"
0x14002ab17  call    cs:__imp_SysAllocString
0x14002ab1d  mov     rdi, rax
0x14002ab20  test    rax, rax
0x14002ab23  jnz     loc_14002ABDB
0x14002ab29  mov     r15d, 8007000Eh
0x14002ab2f  lea     rax, aBstrusername; "bstrUserName"
0x14002ab36  lea     r12, aCpr; "CPR"
0x14002ab3d  mov     [rsp+100h+samDesired], r15d; int
0x14002ab42  lea     rsi, aCmanagedserver_4; "CManagedServerNotificationThread::s_Get"...
0x14002ab49  mov     [rsp+100h+ppv], rax; unsigned __int16 *
0x14002ab4e  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002ab55  mov     r9, r12; unsigned __int16 *
0x14002ab58  mov     r8, rsi; unsigned __int16 *
0x14002ab5b  mov     rcx, rdi; unsigned __int16 *
0x14002ab5e  mov     edx, 100h; unsigned int
0x14002ab63  mov     ebx, r15d
0x14002ab66  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ab6b  call    cs:__imp_IsDebuggerPresent
0x14002ab71  test    eax, eax
0x14002ab73  lea     rax, aBstrusername; "bstrUserName"
0x14002ab7a  jz      short loc_14002ABAC
0x14002ab7c  mov     dword ptr [rsp+100h+phkResult], r15d
0x14002ab81  mov     r9d, 100h
0x14002ab87  mov     [rsp+100h+lpSecurityAttributes], rax
0x14002ab8c  mov     qword ptr [rsp+100h+samDesired], r12
0x14002ab91  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002ab98  mov     r8, rdi
0x14002ab9b  mov     [rsp+100h+ppv], rsi
0x14002aba0  mov     ecx, 2; unsigned __int8
0x14002aba5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002abaa  jmp     short loc_14002ABD3
0x14002abac  mov     dword ptr [rsp+100h+lpSecurityAttributes], r15d
0x14002abb1  mov     r8d, 100h
0x14002abb7  mov     qword ptr [rsp+100h+samDesired], rax
0x14002abbc  mov     r9, rsi
0x14002abbf  mov     [rsp+100h+ppv], r12
0x14002abc4  mov     rdx, rdi
0x14002abc7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002abce  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002abd3  mov     rsi, r13
0x14002abd6  jmp     loc_14002B1E3
0x14002abdb  xor     edx, edx; pUnkOuter
0x14002abdd  lea     rax, [rbp+57h+var_90]
0x14002abe1  lea     r9, _GUID_28b159df_59eb_446b_9316_8b902f75fdf7; riid
0x14002abe8  mov     [rsp+100h+ppv], rax; ppv
0x14002abed  lea     rcx, CLSID_EventNotificationService; rclsid
0x14002abf4  lea     r8d, [rdx+4]; dwClsContext
0x14002abf8  call    cs:__imp_CoCreateInstance
0x14002abfe  mov     ebx, eax
0x14002ac00  test    eax, eax
0x14002ac02  jns     short loc_14002AC6E
0x14002ac04  mov     [rsp+100h+samDesired], eax; int
0x14002ac08  lea     r12, aChra; "CHRA"
0x14002ac0f  lea     rsi, aCmanagedserver_4; "CManagedServerNotificationThread::s_Get"...
0x14002ac16  mov     r9, r12; unsigned __int16 *
0x14002ac19  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002ac20  mov     r8, rsi; unsigned __int16 *
0x14002ac23  lea     r15, aHr; "hr"
0x14002ac2a  mov     rcx, rdi; unsigned __int16 *
0x14002ac2d  mov     edx, 104h; unsigned int
0x14002ac32  mov     [rsp+100h+ppv], r15; unsigned __int16 *
0x14002ac37  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ac3c  call    cs:__imp_IsDebuggerPresent
0x14002ac42  test    eax, eax
0x14002ac44  jz      short loc_14002AC5A
0x14002ac46  mov     dword ptr [rsp+100h+phkResult], ebx
0x14002ac4a  mov     r9d, 104h
0x14002ac50  mov     [rsp+100h+lpSecurityAttributes], r15
0x14002ac55  jmp     loc_14002AB8C
0x14002ac5a  mov     dword ptr [rsp+100h+lpSecurityAttributes], ebx
0x14002ac5e  mov     r8d, 104h
0x14002ac64  mov     qword ptr [rsp+100h+samDesired], r15
0x14002ac69  jmp     loc_14002ABBC
0x14002ac6e  mov     [rsp+100h+lpdwDisposition], rsi; lpdwDisposition
0x14002ac73  lea     rax, [rbp+57h+hKey]
0x14002ac77  mov     [rsp+100h+phkResult], rax; phkResult
0x14002ac7c  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows MultiPoint"...
0x14002ac83  mov     [rsp+100h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x14002ac88  xor     r9d, r9d; lpClass
0x14002ac8b  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x14002ac93  xor     r8d, r8d; Reserved
0x14002ac96  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002ac9d  mov     dword ptr [rsp+100h+ppv], esi; dwOptions
0x14002aca1  call    cs:__imp_RegCreateKeyExW
0x14002aca7  test    eax, eax
0x14002aca9  jz      short loc_14002AD24
0x14002acab  jg      short loc_14002ACB1
0x14002acad  mov     ebx, eax
0x14002acaf  jmp     short loc_14002ACBA
0x14002acb1  movzx   ebx, ax
0x14002acb4  or      ebx, 80070000h
0x14002acba  lea     r12, aCbraex; "CBRAEx"
0x14002acc1  mov     [rsp+100h+samDesired], ebx; int
0x14002acc5  lea     rsi, aCmanagedserver_4; "CManagedServerNotificationThread::s_Get"...
0x14002accc  mov     r9, r12; unsigned __int16 *
0x14002accf  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002acd6  mov     r8, rsi; unsigned __int16 *
0x14002acd9  lea     r15, aErr0l; "err == 0L"
0x14002ace0  mov     rcx, rdi; unsigned __int16 *
0x14002ace3  mov     edx, 107h; unsigned int
0x14002ace8  mov     [rsp+100h+ppv], r15; unsigned __int16 *
0x14002aced  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002acf2  call    cs:__imp_IsDebuggerPresent
0x14002acf8  test    eax, eax
0x14002acfa  jz      short loc_14002AD10
0x14002acfc  mov     dword ptr [rsp+100h+phkResult], ebx
0x14002ad00  mov     r9d, 107h
0x14002ad06  mov     [rsp+100h+lpSecurityAttributes], r15
0x14002ad0b  jmp     loc_14002AB8C
0x14002ad10  mov     dword ptr [rsp+100h+lpSecurityAttributes], ebx
0x14002ad14  mov     r8d, 107h
0x14002ad1a  mov     qword ptr [rsp+100h+samDesired], r15
0x14002ad1f  jmp     loc_14002ABBC
0x14002ad24  mov     rcx, [rbp+57h+hKey]; hKey
0x14002ad28  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14002ad2c  mov     [rsp+100h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x14002ad31  xor     r9d, r9d; lpReserved
0x14002ad34  mov     [rsp+100h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x14002ad39  xor     r8d, r8d; lpcchClass
0x14002ad3c  mov     [rsp+100h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x14002ad41  xor     edx, edx; lpClass
0x14002ad43  mov     [rsp+100h+lpdwDisposition], rsi; lpcbMaxValueNameLen
0x14002ad48  mov     [rsp+100h+phkResult], rsi; lpcValues
0x14002ad4d  mov     [rsp+100h+lpSecurityAttributes], rsi; lpcbMaxClassLen
0x14002ad52  mov     qword ptr [rsp+100h+samDesired], rax; lpcbMaxSubKeyLen
0x14002ad57  lea     rax, [rbp+57h+cSubKeys]
0x14002ad5b  mov     [rsp+100h+ppv], rax; lpcSubKeys
0x14002ad60  call    cs:__imp_RegQueryInfoKeyW
0x14002ad66  test    eax, eax
0x14002ad68  jz      short loc_14002ADE3
0x14002ad6a  jg      short loc_14002AD70
0x14002ad6c  mov     ebx, eax
0x14002ad6e  jmp     short loc_14002AD79
0x14002ad70  movzx   ebx, ax
0x14002ad73  or      ebx, 80070000h
0x14002ad79  lea     r12, aCbraex; "CBRAEx"
0x14002ad80  mov     [rsp+100h+samDesired], ebx; int
0x14002ad84  lea     rsi, aCmanagedserver_4; "CManagedServerNotificationThread::s_Get"...
0x14002ad8b  mov     r9, r12; unsigned __int16 *
0x14002ad8e  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002ad95  mov     r8, rsi; unsigned __int16 *
0x14002ad98  lea     r15, aErr0l; "err == 0L"
0x14002ad9f  mov     rcx, rdi; unsigned __int16 *
0x14002ada2  mov     edx, 10Bh; unsigned int
0x14002ada7  mov     [rsp+100h+ppv], r15; unsigned __int16 *
0x14002adac  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002adb1  call    cs:__imp_IsDebuggerPresent
0x14002adb7  test    eax, eax
0x14002adb9  jz      short loc_14002ADCF
0x14002adbb  mov     dword ptr [rsp+100h+phkResult], ebx
0x14002adbf  mov     r9d, 10Bh
0x14002adc5  mov     [rsp+100h+lpSecurityAttributes], r15
0x14002adca  jmp     loc_14002AB8C
0x14002adcf  mov     dword ptr [rsp+100h+lpSecurityAttributes], ebx
0x14002add3  mov     r8d, 10Bh
0x14002add9  mov     qword ptr [rsp+100h+samDesired], r15
0x14002adde  jmp     loc_14002ABBC
0x14002ade3  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x14002ade6  mov     eax, 2
0x14002adeb  inc     ecx
0x14002aded  mul     rcx
0x14002adf0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002adf7  cmovb   rax, rcx
0x14002adfb  mov     rcx, rax; Size
0x14002adfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002ae03  mov     [rbp+57h+var_A0], rax
0x14002ae07  mov     rsi, rax
0x14002ae0a  test    rax, rax
0x14002ae0d  jnz     loc_14002AEC6
0x14002ae13  mov     r15d, 8007000Eh
0x14002ae19  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002ae20  lea     r12, aCpr; "CPR"
0x14002ae27  mov     [rsp+100h+samDesired], r15d; int
0x14002ae2c  lea     rsi, aCmanagedserver_4; "CManagedServerNotificationThread::s_Get"...
0x14002ae33  mov     [rsp+100h+ppv], rax; unsigned __int16 *
0x14002ae38  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002ae3f  mov     r9, r12; unsigned __int16 *
0x14002ae42  mov     r8, rsi; unsigned __int16 *
0x14002ae45  mov     rcx, rdi; unsigned __int16 *
0x14002ae48  mov     edx, 10Fh; unsigned int
0x14002ae4d  mov     ebx, r15d
0x14002ae50  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ae55  call    cs:__imp_IsDebuggerPresent
0x14002ae5b  test    eax, eax
0x14002ae5d  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002ae64  jz      short loc_14002AE96
0x14002ae66  mov     r9d, 10Fh
0x14002ae6c  mov     dword ptr [rsp+100h+phkResult], r15d
0x14002ae71  mov     [rsp+100h+lpSecurityAttributes], rax
0x14002ae76  mov     qword ptr [rsp+100h+samDesired], r12
0x14002ae7b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002ae82  mov     r8, rdi
0x14002ae85  mov     [rsp+100h+ppv], rsi
0x14002ae8a  mov     ecx, 2; unsigned __int8
0x14002ae8f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002ae94  jmp     short loc_14002AEBD
0x14002ae96  mov     r8d, 10Fh
0x14002ae9c  mov     dword ptr [rsp+100h+lpSecurityAttributes], r15d
0x14002aea1  mov     qword ptr [rsp+100h+samDesired], rax
0x14002aea6  mov     r9, rsi
0x14002aea9  mov     [rsp+100h+ppv], r12
0x14002aeae  mov     rdx, rdi
0x14002aeb1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002aeb8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002aebd  mov     rsi, [rbp+57h+var_A0]
0x14002aec1  jmp     loc_14002B1E3
0x14002aec6  cmp     [rbp+57h+cSubKeys], r13d
0x14002aeca  jz      loc_14002B1E3
0x14002aed0  cmp     word ptr [rbp+57h+var_80], 8
0x14002aed5  jnz     short loc_14002AF07
0x14002aed7  mov     rcx, qword ptr [rbp+57h+var_80+8]; pbstr
0x14002aedb  test    rcx, rcx
0x14002aede  jz      short loc_14002AF07
0x14002aee0  call    cs:__imp_SysStringLen
0x14002aee6  mov     edx, eax
0x14002aee8  mov     rax, qword ptr [rbp+57h+var_80+8]
0x14002aeec  test    rdx, rdx
0x14002aeef  jz      short loc_14002AEFD
0x14002aef1  mov     byte ptr [rax], 0
0x14002aef4  inc     rax
0x14002aef7  sub     rdx, 1
0x14002aefb  jnz     short loc_14002AEF1
0x14002aefd  lea     rcx, [rbp+57h+var_80]; pvarg
0x14002af01  call    cs:__imp_VariantClear
0x14002af07  mov     rcx, r13; bstrString
0x14002af0a  call    cs:__imp_SysFreeString
0x14002af10  xor     r13d, r13d
0x14002af13  test    r14, r14
0x14002af16  jz      short loc_14002AF28
0x14002af18  mov     rcx, r14; pCertContext
0x14002af1b  call    cs:__imp_CertFreeCertificateContext
0x14002af21  xor     r14d, r14d
0x14002af24  mov     [rbp+57h+var_88], r14
0x14002af28  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14002af2b  lea     r9, [rbp+57h+cchName]; lpcchName
0x14002af2f  mov     edx, [rbp+57h+cSubKeys]
0x14002af32  inc     eax
0x14002af34  mov     rcx, [rbp+57h+hKey]; hKey
0x14002af38  dec     edx; dwIndex
0x14002af3a  mov     [rsp+100h+phkResult], r13; lpftLastWriteTime
0x14002af3f  mov     r8, rsi; lpName
0x14002af42  mov     [rsp+100h+lpSecurityAttributes], r13; lpcchClass
0x14002af47  mov     qword ptr [rsp+100h+samDesired], r13; lpClass
0x14002af4c  mov     [rbp+57h+cchName], eax
0x14002af4f  mov     [rsp+100h+ppv], r13; lpReserved
0x14002af54  call    cs:__imp_RegEnumKeyExW
0x14002af5a  cmp     eax, 103h
0x14002af5f  jz      loc_14002B1E1
0x14002af65  test    eax, eax
0x14002af67  jnz     loc_14002B168
0x14002af6d  dec     [rbp+57h+cSubKeys]
0x14002af70  mov     rcx, rsi; psz
0x14002af73  call    cs:__imp_SysAllocString
0x14002af79  mov     r13, rax
0x14002af7c  test    rax, rax
0x14002af7f  jz      loc_14002B0FF
0x14002af85  mov     rcx, [rbp+57h+String1]; String1
0x14002af89  mov     rdx, rax; String2
0x14002af8c  call    cs:__imp__wcsicmp
  ... truncated ...
```
