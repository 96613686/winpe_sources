# CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline(void)

- ea: `0x14002c1b8`
- end: `0x14002c8e1`
- name: `?s_WmsSvcNotifyWmsSystemOnline@CManagedServerNotificationThread@@SAJXZ`
- size: `1833`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140002268`
- `0x14002a700`
- `0x14002a960`
- `0x140045180`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14002c1b8`
- `0x140058b04`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064644`
- `0x140075824`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002c881`
- `ADVAPI32!RegCloseKey` at `0x14002c881`
- `ADVAPI32!RegCreateKeyExW` at `0x14002c3ac`
- `ADVAPI32!RegCreateKeyExW` at `0x14002c3ac`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002c459`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14002c459`
- `ADVAPI32!RegEnumKeyExW` at `0x14002c5a4`
- `ADVAPI32!RegEnumKeyExW` at `0x14002c5a4`
- `KERNEL32!IsDebuggerPresent` at `0x14002c29c`
- `KERNEL32!IsDebuggerPresent` at `0x14002c3fd`
- `KERNEL32!IsDebuggerPresent` at `0x14002c4aa`
- `KERNEL32!IsDebuggerPresent` at `0x14002c534`
- `KERNEL32!IsDebuggerPresent` at `0x14002c6c1`
- `KERNEL32!IsDebuggerPresent` at `0x14002c723`
- `KERNEL32!IsDebuggerPresent` at `0x14002c7a9`
- `KERNEL32!IsDebuggerPresent` at `0x14002c29c`
- `KERNEL32!IsDebuggerPresent` at `0x14002c3fd`
- `KERNEL32!IsDebuggerPresent` at `0x14002c4aa`
- `KERNEL32!IsDebuggerPresent` at `0x14002c534`
- `KERNEL32!IsDebuggerPresent` at `0x14002c6c1`
- `KERNEL32!IsDebuggerPresent` at `0x14002c723`
- `KERNEL32!IsDebuggerPresent` at `0x14002c7a9`
- `msvcrt!_wcsicmp` at `0x14002c5d9`
- `msvcrt!_wcsicmp` at `0x14002c5d9`
- `ole32!CoCreateInstance` at `0x14002c254`
- `ole32!CoCreateInstance` at `0x14002c254`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c5c0`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c5c0`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c66c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c821`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c82b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c85b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c868`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c872`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c66c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c821`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c82b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c85b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c868`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c872`
- `OLEAUT32!__imp_SysStringLen` at `0x14002c83a`
- `OLEAUT32!__imp_SysStringLen` at `0x14002c83a`
- `OLEAUT32!__imp_VariantInit` at `0x14002c21e`
- `OLEAUT32!__imp_VariantInit` at `0x14002c21e`
- `OLEAUT32!__imp_VariantClear` at `0x14002c80f`
- `OLEAUT32!__imp_VariantClear` at `0x14002c80f`
- `PROPSYS!VariantToUInt32` at `0x14002c625`
- `PROPSYS!VariantToUInt32` at `0x14002c625`

## string_xrefs

- `0x14002c279`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c3da`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c487`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c517`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c69e`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c706`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c785`: `termsrv\wms\src\devices\wmssvc\managedserverthread.cpp`
- `0x14002c1d3`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline - Start\n`
- `0x14002c26f`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c3d0`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c47d`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c50b`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c694`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c6fa`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c778`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline`
- `0x14002c635`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline - Attempt to send managed system online event to %s:%d.\n`
- `0x14002c8bf`: `CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline - End, hr = 0x%08X\n`

## pseudocode

```c
__int64 CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline(void)
{
  WCHAR *v0; // r13
  OLECHAR *v1; // r14
  signed int LocalHostName; // ebx
  HRESULT v3; // eax
  const unsigned __int16 *v4; // r12
  const unsigned __int16 *v5; // r15
  __int64 v6; // r9
  __int64 v7; // r8
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  DWORD v10; // ecx
  LSTATUS v11; // eax
  const wchar_t *v12; // rax
  HRESULT v13; // eax
  bool v14; // zf
  OLECHAR *v15; // rcx
  __int64 v16; // rax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-79h]
  PHKEY phkResult; // [rsp+38h] [rbp-71h]
  BSTR pbstr; // [rsp+60h] [rbp-49h] BYREF
  __int64 v21; // [rsp+68h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-39h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp-31h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp-29h] BYREF
  BSTR v25; // [rsp+88h] [rbp-21h] BYREF
  BSTR bstrString[2]; // [rsp+90h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-9h] BYREF
  DWORD cSubKeys; // [rsp+110h] [rbp+67h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+118h] [rbp+6Fh] BYREF
  ULONG pulRet; // [rsp+120h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+128h] [rbp+7Fh] BYREF

  ppv = 0;
  v21 = 0;
  pulRet = 0;
  v0 = 0;
  v25 = 0;
  v1 = 0;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  String1 = 0;
  bstrString[0] = 0;
  pbstr = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  DEBUGMSG(L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline - Start\n");
  VariantInit(&pvarg);
  LocalHostName = GetLocalHostName(&String1);
  if ( LocalHostName < 0 )
    goto LABEL_55;
  v3 = CoCreateInstance(&CLSID_EventNotificationService, 0, 4u, &GUID_28b159df_59eb_446b_9316_8b902f75fdf7, &ppv);
  LocalHostName = v3;
  if ( v3 < 0 )
  {
    v4 = L"CHRA";
    v5 = L"hr";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
      0x81u,
      L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
      L"CHRA",
      L"hr",
      v3);
    if ( !IsDebuggerPresent() )
    {
      v7 = 129;
      goto LABEL_7;
    }
    v6 = 129;
LABEL_5:
    LODWORD(phkResult) = LocalHostName;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
      v6,
      L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
      v4,
      v5,
      phkResult);
    goto LABEL_55;
  }
  LocalHostName = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                    ppv,
                    &GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8,
                    &v21);
  if ( LocalHostName < 0 )
    goto LABEL_55;
  LocalHostName = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *, BSTR *))(*(_QWORD *)v21 + 224LL))(
                    v21,
                    0,
                    bstrString,
                    &pbstr);
  if ( LocalHostName < 0 )
    goto LABEL_55;
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  LocalHostName = GetWmsSystemIpAddresses(&v25);
  if ( LocalHostName < 0 )
    goto LABEL_55;
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
      LocalHostName = (unsigned __int16)v8 | 0x80070000;
    else
      LocalHostName = v8;
    v4 = L"CBRAEx";
    v5 = L"err == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
      0x91u,
      L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
      L"CBRAEx",
      L"err == 0L",
      LocalHostName);
    if ( !IsDebuggerPresent() )
    {
      v7 = 145;
      goto LABEL_7;
    }
    v6 = 145;
    goto LABEL_5;
  }
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v9 )
  {
    if ( v9 > 0 )
      LocalHostName = (unsigned __int16)v9 | 0x80070000;
    else
      LocalHostName = v9;
    v4 = L"CBRAEx";
    v5 = L"err == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
      0x95u,
      L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
      L"CBRAEx",
      L"err == 0L",
      LocalHostName);
    if ( !IsDebuggerPresent() )
    {
      v7 = 149;
      goto LABEL_7;
    }
    v6 = 149;
    goto LABEL_5;
  }
  v0 = (WCHAR *)operator new(saturated_mul(cbMaxSubKeyLen + 1, 2u));
  if ( !v0 )
  {
    LocalHostName = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
      0x99u,
      L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
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
        153,
        L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
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
        153,
        L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
        L"CPR",
        L"pszSubKeyNameBuffer",
        lpSecurityAttributes);
    }
    goto LABEL_55;
  }
  v10 = cSubKeys;
  if ( !cSubKeys )
    goto LABEL_55;
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen + 1;
    v11 = RegEnumKeyExW(hKey, v10 - 1, v0, &cchName, 0, 0, 0, 0);
    if ( v11 == 259 )
    {
      LocalHostName = 0;
LABEL_54:
      v1 = 0;
      goto LABEL_55;
    }
    if ( v11 )
    {
      if ( v11 > 0 )
        LocalHostName = (unsigned __int16)v11 | 0x80070000;
      else
        LocalHostName = v11;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0xA2u,
        L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
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
          162,
          L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
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
          162,
          L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
          L"CBRAEx",
          L"err == 0L",
          lpSecurityAttributes);
      }
      goto LABEL_54;
    }
    v12 = SysAllocString(v0);
    v1 = (OLECHAR *)v12;
    if ( !v12 )
    {
      LocalHostName = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
        0xA6u,
        L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
        L"CPR",
        L"bstrRemoteHostname",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = -2147024882;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          166,
          L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
          L"CPR",
          L"bstrRemoteHostname",
          phkResult);
      }
      else
      {
        LODWORD(lpSecurityAttributes) = -2147024882;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
          166,
          L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
          L"CPR",
          L"bstrRemoteHostname",
          lpSecurityAttributes);
      }
      goto LABEL_55;
    }
    if ( _wcsicmp(String1, v12) )
      break;
LABEL_39:
    SysFreeString(v1);
    v1 = 0;
    v14 = cSubKeys == 1;
    v10 = --cSubKeys;
    if ( v14 )
      goto LABEL_55;
  }
  LocalHostName = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *))(*(_QWORD *)ppv + 216LL))(ppv, 1, v1);
  if ( LocalHostName < 0 )
    goto LABEL_55;
  v13 = VariantToUInt32(&pvarg, &pulRet);
  LocalHostName = v13;
  if ( v13 >= 0 )
  {
    DEBUGMSG(
      L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline - Attempt to send managed system online event to %s:%d.\n",
      v1,
      pulRet);
    LocalHostName = CWmsWebServiceProxy::s_SendManagedSystemOnlineEvent(String1, pbstr, v25, v1, pulRet);
    if ( LocalHostName < 0 )
      goto LABEL_55;
    goto LABEL_39;
  }
  v4 = L"CHRA";
  v5 = L"hr";
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
    0xB0u,
    L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
    L"CHRA",
    L"hr",
    v13);
  if ( IsDebuggerPresent() )
  {
    v6 = 176;
    goto LABEL_5;
  }
  v7 = 176;
LABEL_7:
  LODWORD(lpSecurityAttributes) = LocalHostName;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\managedserverthread.cpp",
    v7,
    L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline",
    v4,
    v5,
    lpSecurityAttributes);
LABEL_55:
  VariantClear(&pvarg);
  operator delete(v0);
  SysFreeString(String1);
  SysFreeString(bstrString[0]);
  if ( pbstr )
  {
    LODWORD(v16) = SysStringLen(pbstr);
    v15 = pbstr;
    v16 = (unsigned int)v16;
    if ( (_DWORD)v16 )
    {
      do
      {
        *(_BYTE *)v15 = 0;
        v15 = (OLECHAR *)((char *)v15 + 1);
        --v16;
      }
      while ( v16 );
      v15 = pbstr;
    }
    SysFreeString(v15);
    pbstr = 0;
  }
  SysFreeString(v1);
  SysFreeString(v25);
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
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  DEBUGMSG(
    L"CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline - End, hr = 0x%08X\n",
    (unsigned int)LocalHostName);
  return (unsigned int)LocalHostName;
}

```

## disassembly

```asm
0x14002c1b8  push    rbp
0x14002c1ba  push    rbx
0x14002c1bb  push    rsi
0x14002c1bc  push    rdi
0x14002c1bd  push    r12
0x14002c1bf  push    r13
0x14002c1c1  push    r14
0x14002c1c3  push    r15
0x14002c1c5  lea     rbp, [rsp-1Fh]
0x14002c1ca  sub     rsp, 0C8h
0x14002c1d1  xor     edi, edi
0x14002c1d3  lea     rcx, aCmanagedserver_5; "CManagedServerNotificationThread::s_Wms"...
0x14002c1da  xorps   xmm0, xmm0
0x14002c1dd  mov     [rbp+57h+var_88], rdi
0x14002c1e1  xor     eax, eax
0x14002c1e3  mov     [rbp+57h+var_98], rdi
0x14002c1e7  mov     [rbp+57h+pulRet], edi
0x14002c1ea  mov     r13d, edi
0x14002c1ed  mov     [rbp+57h+var_78], rdi
0x14002c1f1  mov     r14d, edi
0x14002c1f4  mov     [rbp+57h+hKey], rdi
0x14002c1f8  mov     [rbp+57h+cSubKeys], edi
0x14002c1fb  mov     [rbp+57h+cbMaxSubKeyLen], edi
0x14002c1fe  mov     [rbp+57h+cchName], edi
0x14002c201  mov     [rbp+57h+String1], rdi
0x14002c205  mov     [rbp+57h+bstrString], rdi
0x14002c209  mov     [rbp+57h+pbstr], rdi
0x14002c20d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14002c211  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14002c215  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002c21a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002c21e  call    cs:__imp_VariantInit
0x14002c224  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x14002c228  call    ?GetLocalHostName@@YAJPEAPEAG@Z; GetLocalHostName(ushort * *)
0x14002c22d  mov     ebx, eax
0x14002c22f  test    eax, eax
0x14002c231  js      loc_14002C80B
0x14002c237  lea     rax, [rbp+57h+var_88]
0x14002c23b  xor     edx, edx; pUnkOuter
0x14002c23d  lea     r9, _GUID_28b159df_59eb_446b_9316_8b902f75fdf7; riid
0x14002c244  mov     [rsp+100h+ppv], rax; ppv
0x14002c249  lea     r8d, [rdi+4]; dwClsContext
0x14002c24d  lea     rcx, CLSID_EventNotificationService; rclsid
0x14002c254  call    cs:__imp_CoCreateInstance
0x14002c25a  mov     ebx, eax
0x14002c25c  test    eax, eax
0x14002c25e  jns     loc_14002C302
0x14002c264  mov     [rsp+100h+samDesired], eax; int
0x14002c268  lea     r12, aChra; "CHRA"
0x14002c26f  lea     rsi, aCmanagedserver_6; "CManagedServerNotificationThread::s_Wms"...
0x14002c276  mov     r9, r12; unsigned __int16 *
0x14002c279  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002c280  mov     r8, rsi; unsigned __int16 *
0x14002c283  lea     r15, aHr; "hr"
0x14002c28a  mov     rcx, rdi; unsigned __int16 *
0x14002c28d  mov     edx, 81h; unsigned int
0x14002c292  mov     [rsp+100h+ppv], r15; unsigned __int16 *
0x14002c297  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002c29c  call    cs:__imp_IsDebuggerPresent
0x14002c2a2  test    eax, eax
0x14002c2a4  jz      short loc_14002C2D5
0x14002c2a6  mov     r9d, 81h
0x14002c2ac  mov     dword ptr [rsp+100h+phkResult], ebx
0x14002c2b0  mov     [rsp+100h+lpSecurityAttributes], r15
0x14002c2b5  mov     qword ptr [rsp+100h+samDesired], r12
0x14002c2ba  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002c2c1  mov     r8, rdi
0x14002c2c4  mov     [rsp+100h+ppv], rsi
0x14002c2c9  mov     ecx, 2; unsigned __int8
0x14002c2ce  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002c2d3  jmp     short loc_14002C2FB
0x14002c2d5  mov     r8d, 81h
0x14002c2db  mov     dword ptr [rsp+100h+lpSecurityAttributes], ebx
0x14002c2df  mov     qword ptr [rsp+100h+samDesired], r15
0x14002c2e4  mov     r9, rsi
0x14002c2e7  mov     [rsp+100h+ppv], r12
0x14002c2ec  mov     rdx, rdi
0x14002c2ef  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002c2f6  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002c2fb  xor     edi, edi
0x14002c2fd  jmp     loc_14002C80B
0x14002c302  mov     rcx, [rbp+57h+var_88]
0x14002c306  lea     r8, [rbp+57h+var_98]
0x14002c30a  lea     rdx, _GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8
0x14002c311  mov     rax, [rcx]
0x14002c314  mov     rax, [rax]
0x14002c317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c31c  mov     ebx, eax
0x14002c31e  test    eax, eax
0x14002c320  js      loc_14002C80B
0x14002c326  mov     rcx, [rbp+57h+var_98]
0x14002c32a  lea     r9, [rbp+57h+pbstr]
0x14002c32e  lea     r8, [rbp+57h+bstrString]
0x14002c332  xor     edx, edx
0x14002c334  mov     rax, [rcx]
0x14002c337  mov     rax, [rax+0E0h]
0x14002c33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c343  mov     ebx, eax
0x14002c345  test    eax, eax
0x14002c347  js      loc_14002C80B
0x14002c34d  mov     rcx, [rbp+57h+var_98]
0x14002c351  test    rcx, rcx
0x14002c354  jz      short loc_14002C366
0x14002c356  mov     rax, [rcx]
0x14002c359  mov     rax, [rax+10h]
0x14002c35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c362  mov     [rbp+57h+var_98], rdi
0x14002c366  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x14002c36a  call    ?GetWmsSystemIpAddresses@@YAJPEAPEAG@Z; GetWmsSystemIpAddresses(ushort * *)
0x14002c36f  mov     ebx, eax
0x14002c371  test    eax, eax
0x14002c373  js      loc_14002C80B
0x14002c379  mov     [rsp+100h+lpdwDisposition], rdi; lpdwDisposition
0x14002c37e  lea     rax, [rbp+57h+hKey]
0x14002c382  mov     [rsp+100h+phkResult], rax; phkResult
0x14002c387  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows MultiPoint"...
0x14002c38e  mov     [rsp+100h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14002c393  xor     r9d, r9d; lpClass
0x14002c396  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x14002c39e  xor     r8d, r8d; Reserved
0x14002c3a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002c3a8  mov     dword ptr [rsp+100h+ppv], edi; dwOptions
0x14002c3ac  call    cs:__imp_RegCreateKeyExW
0x14002c3b2  test    eax, eax
0x14002c3b4  jz      short loc_14002C41D
0x14002c3b6  jg      short loc_14002C3BC
0x14002c3b8  mov     ebx, eax
0x14002c3ba  jmp     short loc_14002C3C5
0x14002c3bc  movzx   ebx, ax
0x14002c3bf  or      ebx, 80070000h
0x14002c3c5  lea     r12, aCbraex; "CBRAEx"
0x14002c3cc  mov     [rsp+100h+samDesired], ebx; int
0x14002c3d0  lea     rsi, aCmanagedserver_6; "CManagedServerNotificationThread::s_Wms"...
0x14002c3d7  mov     r9, r12; unsigned __int16 *
0x14002c3da  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002c3e1  mov     r8, rsi; unsigned __int16 *
0x14002c3e4  lea     r15, aErr0l; "err == 0L"
0x14002c3eb  mov     rcx, rdi; unsigned __int16 *
0x14002c3ee  mov     edx, 91h; unsigned int
0x14002c3f3  mov     [rsp+100h+ppv], r15; unsigned __int16 *
0x14002c3f8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002c3fd  call    cs:__imp_IsDebuggerPresent
0x14002c403  test    eax, eax
0x14002c405  jz      short loc_14002C412
0x14002c407  mov     r9d, 91h
0x14002c40d  jmp     loc_14002C2AC
0x14002c412  mov     r8d, 91h
0x14002c418  jmp     loc_14002C2DB
0x14002c41d  mov     rcx, [rbp+57h+hKey]; hKey
0x14002c421  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14002c425  mov     [rsp+100h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x14002c42a  xor     r9d, r9d; lpReserved
0x14002c42d  mov     [rsp+100h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x14002c432  xor     r8d, r8d; lpcchClass
0x14002c435  mov     [rsp+100h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x14002c43a  xor     edx, edx; lpClass
0x14002c43c  mov     [rsp+100h+lpdwDisposition], rdi; lpcbMaxValueNameLen
0x14002c441  mov     [rsp+100h+phkResult], rdi; lpcValues
0x14002c446  mov     [rsp+100h+lpSecurityAttributes], rdi; lpcbMaxClassLen
0x14002c44b  mov     qword ptr [rsp+100h+samDesired], rax; lpcbMaxSubKeyLen
0x14002c450  lea     rax, [rbp+57h+cSubKeys]
0x14002c454  mov     [rsp+100h+ppv], rax; lpcSubKeys
0x14002c459  call    cs:__imp_RegQueryInfoKeyW
0x14002c45f  test    eax, eax
0x14002c461  jz      short loc_14002C4CA
0x14002c463  jg      short loc_14002C469
0x14002c465  mov     ebx, eax
0x14002c467  jmp     short loc_14002C472
0x14002c469  movzx   ebx, ax
0x14002c46c  or      ebx, 80070000h
0x14002c472  lea     r12, aCbraex; "CBRAEx"
0x14002c479  mov     [rsp+100h+samDesired], ebx; int
0x14002c47d  lea     rsi, aCmanagedserver_6; "CManagedServerNotificationThread::s_Wms"...
0x14002c484  mov     r9, r12; unsigned __int16 *
0x14002c487  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002c48e  mov     r8, rsi; unsigned __int16 *
0x14002c491  lea     r15, aErr0l; "err == 0L"
0x14002c498  mov     rcx, rdi; unsigned __int16 *
0x14002c49b  mov     edx, 95h; unsigned int
0x14002c4a0  mov     [rsp+100h+ppv], r15; unsigned __int16 *
0x14002c4a5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002c4aa  call    cs:__imp_IsDebuggerPresent
0x14002c4b0  test    eax, eax
0x14002c4b2  jz      short loc_14002C4BF
0x14002c4b4  mov     r9d, 95h
0x14002c4ba  jmp     loc_14002C2AC
0x14002c4bf  mov     r8d, 95h
0x14002c4c5  jmp     loc_14002C2DB
0x14002c4ca  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x14002c4cd  mov     eax, 2
0x14002c4d2  inc     ecx
0x14002c4d4  mul     rcx
0x14002c4d7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002c4de  cmovb   rax, rcx
0x14002c4e2  mov     rcx, rax; Size
0x14002c4e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002c4ea  mov     r13, rax
0x14002c4ed  test    rax, rax
0x14002c4f0  jnz     short loc_14002C56F
0x14002c4f2  mov     r15d, 8007000Eh
0x14002c4f8  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002c4ff  lea     r12, aCpr; "CPR"
0x14002c506  mov     [rsp+100h+samDesired], r15d; int
0x14002c50b  lea     rsi, aCmanagedserver_6; "CManagedServerNotificationThread::s_Wms"...
0x14002c512  mov     [rsp+100h+ppv], rax; unsigned __int16 *
0x14002c517  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002c51e  mov     r9, r12; unsigned __int16 *
0x14002c521  mov     r8, rsi; unsigned __int16 *
0x14002c524  mov     rcx, rdi; unsigned __int16 *
0x14002c527  mov     edx, 99h; unsigned int
0x14002c52c  mov     ebx, r15d
0x14002c52f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002c534  call    cs:__imp_IsDebuggerPresent
0x14002c53a  test    eax, eax
0x14002c53c  lea     rax, aPszsubkeynameb; "pszSubKeyNameBuffer"
0x14002c543  jz      short loc_14002C55A
0x14002c545  mov     dword ptr [rsp+100h+phkResult], r15d
0x14002c54a  mov     r9d, 99h
0x14002c550  mov     [rsp+100h+lpSecurityAttributes], rax
0x14002c555  jmp     loc_14002C2B5
0x14002c55a  mov     dword ptr [rsp+100h+lpSecurityAttributes], r15d
0x14002c55f  mov     r8d, 99h
0x14002c565  mov     qword ptr [rsp+100h+samDesired], rax
0x14002c56a  jmp     loc_14002C2E4
0x14002c56f  mov     ecx, [rbp+57h+cSubKeys]
0x14002c572  test    ecx, ecx
0x14002c574  jz      loc_14002C80B
0x14002c57a  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14002c57d  lea     edx, [rcx-1]; dwIndex
0x14002c580  mov     rcx, [rbp+57h+hKey]; hKey
0x14002c584  lea     r9, [rbp+57h+cchName]; lpcchName
0x14002c588  mov     [rsp+100h+phkResult], rdi; lpftLastWriteTime
0x14002c58d  inc     eax
0x14002c58f  mov     [rsp+100h+lpSecurityAttributes], rdi; lpcchClass
0x14002c594  mov     r8, r13; lpName
0x14002c597  mov     qword ptr [rsp+100h+samDesired], rdi; lpClass
0x14002c59c  mov     [rbp+57h+cchName], eax
0x14002c59f  mov     [rsp+100h+ppv], rdi; lpReserved
0x14002c5a4  call    cs:__imp_RegEnumKeyExW
0x14002c5aa  cmp     eax, 103h
0x14002c5af  jz      loc_14002C806
0x14002c5b5  test    eax, eax
0x14002c5b7  jnz     loc_14002C75E
0x14002c5bd  mov     rcx, r13; psz
0x14002c5c0  call    cs:__imp_SysAllocString
0x14002c5c6  mov     r14, rax
0x14002c5c9  test    rax, rax
0x14002c5cc  jz      loc_14002C6E1
0x14002c5d2  mov     rcx, [rbp+57h+String1]; String1
0x14002c5d6  mov     rdx, rax; String2
0x14002c5d9  call    cs:__imp__wcsicmp
0x14002c5df  test    eax, eax
0x14002c5e1  jz      loc_14002C669
0x14002c5e7  mov     r10, [rbp+57h+var_88]
0x14002c5eb  mov     r9d, 6
0x14002c5f1  mov     r8, r14
0x14002c5f4  mov     rcx, [r10]
0x14002c5f7  lea     edx, [r9-5]
0x14002c5fb  mov     rax, [rcx+0D8h]
0x14002c602  lea     rcx, [rbp+57h+pvarg]
0x14002c606  mov     [rsp+100h+ppv], rcx
0x14002c60b  mov     rcx, r10
0x14002c60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c613  mov     ebx, eax
0x14002c615  test    eax, eax
0x14002c617  js      loc_14002C80B
0x14002c61d  lea     rdx, [rbp+57h+pulRet]; pulRet
0x14002c621  lea     rcx, [rbp+57h+pvarg]; varIn
0x14002c625  call    cs:__imp_VariantToUInt32
0x14002c62b  mov     ebx, eax
0x14002c62d  test    eax, eax
0x14002c62f  js      short loc_14002C689
0x14002c631  mov     r8d, [rbp+57h+pulRet]
0x14002c635  lea     rcx, aCmanagedserver_14; "CManagedServerNotificationThread::s_Wms"...
0x14002c63c  mov     rdx, r14
0x14002c63f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002c644  mov     eax, [rbp+57h+pulRet]
0x14002c647  mov     r9, r14; unsigned __int16 *
0x14002c64a  mov     r8, [rbp+57h+var_78]; unsigned __int16 *
0x14002c64e  mov     rdx, [rbp+57h+pbstr]; unsigned __int16 *
0x14002c652  mov     rcx, [rbp+57h+String1]; unsigned __int16 *
0x14002c656  mov     dword ptr [rsp+100h+ppv], eax; unsigned int
0x14002c65a  call    ?s_SendManagedSystemOnlineEvent@CWmsWebServiceProxy@@SAJPEAG000K@Z; CWmsWebServiceProxy::s_SendManagedSystemOnlineEvent(ushort *,ushort *,ushort *,ushort *,ulong)
0x14002c65f  mov     ebx, eax
0x14002c661  test    eax, eax
0x14002c663  js      loc_14002C80B
0x14002c669  mov     rcx, r14; bstrString
0x14002c66c  call    cs:__imp_SysFreeString
0x14002c672  mov     ecx, [rbp+57h+cSubKeys]
0x14002c675  mov     r14, rdi
0x14002c678  add     ecx, 0FFFFFFFFh
0x14002c67b  mov     [rbp+57h+cSubKeys], ecx
0x14002c67e  jnz     loc_14002C57A
0x14002c684  jmp     loc_14002C80B
0x14002c689  lea     r12, aChra; "CHRA"
0x14002c690  mov     [rsp+100h+samDesired], ebx; int
0x14002c694  lea     rsi, aCmanagedserver_6; "CManagedServerNotificationThread::s_Wms"...
0x14002c69b  mov     r9, r12; unsigned __int16 *
0x14002c69e  lea     rdi, aTermsrvWmsSrcD_34; "termsrv\\wms\\src\\devices\\wmssvc\\man"...
0x14002c6a5  mov     r8, rsi; unsigned __int16 *
  ... truncated ...
```
