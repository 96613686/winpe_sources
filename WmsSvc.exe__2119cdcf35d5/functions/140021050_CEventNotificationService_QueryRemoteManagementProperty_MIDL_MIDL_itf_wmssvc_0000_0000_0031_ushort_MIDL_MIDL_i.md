# CEventNotificationService::QueryRemoteManagementProperty(__MIDL___MIDL_itf_wmssvc_0000_0000_0031,ushort *,__MIDL___MIDL_itf_wmssvc_0000_0000_0032,tagVARIANT *)

- ea: `0x140021050`
- end: `0x140021936`
- name: `?QueryRemoteManagementProperty@CEventNotificationService@@UEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0031@@PEAGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0032@@PEAUtagVARIANT@@@Z`
- size: `2278`
- prototype: `__int64 __fastcall(__int64, int, const WCHAR *, unsigned int, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140021050`
- `0x14002897c`
- `0x14005a88c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400633fc`
- `0x14006c590`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14002162d`
- `ADVAPI32!RegGetValueW` at `0x14002174a`
- `ADVAPI32!RegGetValueW` at `0x140021904`
- `ADVAPI32!RegGetValueW` at `0x14002162d`
- `ADVAPI32!RegGetValueW` at `0x14002174a`
- `ADVAPI32!RegGetValueW` at `0x140021904`
- `ADVAPI32!RegCloseKey` at `0x140021107`
- `ADVAPI32!RegCloseKey` at `0x14002111a`
- `ADVAPI32!RegCloseKey` at `0x140021107`
- `ADVAPI32!RegCloseKey` at `0x14002111a`
- `ADVAPI32!RegCreateKeyExW` at `0x140021326`
- `ADVAPI32!RegCreateKeyExW` at `0x140021326`
- `ADVAPI32!RegOpenKeyW` at `0x1400213aa`
- `ADVAPI32!RegOpenKeyW` at `0x1400213aa`
- `KERNEL32!IsDebuggerPresent` at `0x1400211dd`
- `KERNEL32!IsDebuggerPresent` at `0x140021294`
- `KERNEL32!IsDebuggerPresent` at `0x140021379`
- `KERNEL32!IsDebuggerPresent` at `0x14002143f`
- `KERNEL32!IsDebuggerPresent` at `0x140021504`
- `KERNEL32!IsDebuggerPresent` at `0x1400215b8`
- `KERNEL32!IsDebuggerPresent` at `0x1400216b4`
- `KERNEL32!IsDebuggerPresent` at `0x14002179d`
- `KERNEL32!IsDebuggerPresent` at `0x14002188d`
- `KERNEL32!IsDebuggerPresent` at `0x1400211dd`
- `KERNEL32!IsDebuggerPresent` at `0x140021294`
- `KERNEL32!IsDebuggerPresent` at `0x140021379`
- `KERNEL32!IsDebuggerPresent` at `0x14002143f`
- `KERNEL32!IsDebuggerPresent` at `0x140021504`
- `KERNEL32!IsDebuggerPresent` at `0x1400215b8`
- `KERNEL32!IsDebuggerPresent` at `0x1400216b4`
- `KERNEL32!IsDebuggerPresent` at `0x14002179d`
- `KERNEL32!IsDebuggerPresent` at `0x14002188d`
- `msvcrt!_wcsicmp` at `0x1400213d5`
- `msvcrt!_wcsicmp` at `0x1400213d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400213ea`
- `OLEAUT32!__imp_SysAllocString` at `0x140021542`
- `OLEAUT32!__imp_SysAllocString` at `0x140021804`
- `OLEAUT32!__imp_SysAllocString` at `0x1400213ea`
- `OLEAUT32!__imp_SysAllocString` at `0x140021542`
- `OLEAUT32!__imp_SysAllocString` at `0x140021804`
- `OLEAUT32!__imp_SysFreeString` at `0x140021128`
- `OLEAUT32!__imp_SysFreeString` at `0x140021132`
- `OLEAUT32!__imp_SysFreeString` at `0x140021128`
- `OLEAUT32!__imp_SysFreeString` at `0x140021132`
- `OLEAUT32!__imp_VariantInit` at `0x1400212df`
- `OLEAUT32!__imp_VariantInit` at `0x14002155d`
- `OLEAUT32!__imp_VariantInit` at `0x14002181d`
- `OLEAUT32!__imp_VariantInit` at `0x1400212df`
- `OLEAUT32!__imp_VariantInit` at `0x14002155d`
- `OLEAUT32!__imp_VariantInit` at `0x14002181d`

## string_xrefs

- `0x1400211b0`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x14002125f`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x14002134e`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x140021412`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x1400214d7`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x140021583`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x140021687`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x14002176c`: `CEventNotificationService::QueryRemoteManagementProperty`
- `0x140021858`: `CEventNotificationService::QueryRemoteManagementProperty`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::QueryRemoteManagementProperty(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        unsigned int a4,
        VARIANTARG *pvarg)
{
  unsigned int v6; // esi
  OLECHAR *v9; // r13
  unsigned int v10; // edi
  unsigned int v11; // ecx
  int NewHostName; // ebx
  unsigned __int16 *v13; // rsi
  __int64 v14; // rdx
  OLECHAR *v15; // rax
  unsigned int v17; // r12d
  bool v18; // zf
  const unsigned __int16 *v19; // rax
  VARIANTARG *v20; // rdi
  const WCHAR *v21; // rdx
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  OLECHAR *v24; // rax
  int v25; // r14d
  const OLECHAR *v26; // rcx
  BSTR v27; // rax
  const WCHAR *v28; // rax
  LSTATUS v29; // eax
  const WCHAR *v30; // rax
  LSTATUS v31; // eax
  int v32; // eax
  OLECHAR *v33; // rbx
  BSTR v34; // rax
  const WCHAR *v35; // rax
  LSTATUS ValueW; // eax
  const unsigned __int16 *dwOptions; // [rsp+20h] [rbp-61h]
  const unsigned __int16 *samDesired; // [rsp+28h] [rbp-59h]
  const unsigned __int16 *samDesireda; // [rsp+28h] [rbp-59h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-51h]
  const unsigned __int16 *lpSecurityAttributesa; // [rsp+30h] [rbp-51h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesb; // [rsp+30h] [rbp-51h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesc; // [rsp+30h] [rbp-51h]
  PHKEY phkResult; // [rsp+38h] [rbp-49h]
  unsigned __int16 *v45; // [rsp+50h] [rbp-31h]
  DWORD pcbData; // [rsp+58h] [rbp-29h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-25h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-21h] BYREF
  LONG pvData; // [rsp+68h] [rbp-19h] BYREF
  OLECHAR *psz; // [rsp+70h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-1h] BYREF
  BSTR v53; // [rsp+88h] [rbp+7h]
  unsigned int v54; // [rsp+F8h] [rbp+77h] BYREF

  hkey = 0;
  pvData = 0;
  v6 = a4;
  psz = 0;
  v54 = 0;
  pdwType = 0;
  pcbData = 0;
  v9 = 0;
  hKey = 0;
  v10 = 0;
  bstrString = 0;
  v53 = 0;
  if ( a4 != 2 )
  {
    if ( a4 == 7 )
    {
      v6 = 1;
      if ( (int)CUserManagement::s_VerifyAccessLevelEx(0, 1) < 0 )
      {
        v6 = 3;
        goto LABEL_18;
      }
    }
    else
    {
      if ( a4 != 8 )
      {
        v11 = 1;
        goto LABEL_5;
      }
      v6 = 2;
      if ( (int)CUserManagement::s_VerifyAccessLevelEx(0, 1) < 0 )
      {
        v6 = 4;
LABEL_18:
        v11 = 1;
        goto LABEL_5;
      }
    }
LABEL_22:
    if ( !a3 )
    {
      v17 = 3005;
      NewHostName = -2147024809;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0xBBDu,
        L"CEventNotificationService::QueryRemoteManagementProperty",
        L"CBRAEx",
        L"bstrRemoteHostName",
        -2147024809);
      v18 = !IsDebuggerPresent();
      v19 = L"bstrRemoteHostName";
LABEL_24:
      if ( !v18 )
      {
        LODWORD(phkResult) = -2147024809;
        lpSecurityAttributesa = v19;
LABEL_26:
        samDesired = L"CBRAEx";
LABEL_27:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v17,
          L"CEventNotificationService::QueryRemoteManagementProperty",
          samDesired,
          lpSecurityAttributesa,
          phkResult);
        goto LABEL_32;
      }
      LODWORD(lpSecurityAttributes) = -2147024809;
      samDesireda = v19;
LABEL_30:
      dwOptions = L"CBRAEx";
LABEL_31:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v17,
        L"CEventNotificationService::QueryRemoteManagementProperty",
        dwOptions,
        samDesireda,
        lpSecurityAttributes);
      goto LABEL_32;
    }
    v20 = pvarg;
    if ( !pvarg )
    {
      NewHostName = -2147467261;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0xBBEu,
        L"CEventNotificationService::QueryRemoteManagementProperty",
        L"CBRAEx",
        L"pvarSetting",
        -2147467261);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          3006,
          L"CEventNotificationService::QueryRemoteManagementProperty",
          L"CBRAEx",
          L"pvarSetting",
          -2147467261);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          3006,
          L"CEventNotificationService::QueryRemoteManagementProperty",
          L"CBRAEx",
          L"pvarSetting",
          -2147467261);
      goto LABEL_32;
    }
    if ( CEventNotificationService::m_sShutdownInProgress )
    {
      NewHostName = -2147023781;
      goto LABEL_32;
    }
    VariantInit(pvarg);
    v21 = L"Software\\Microsoft\\Windows MultiPoint Server\\Managed Servers";
    if ( a2 )
      v21 = L"Software\\Microsoft\\Windows MultiPoint Server\\Managed By Servers";
    v22 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0, 0, 0xF003Fu, 0, &hkey, 0);
    NewHostName = v22;
    if ( v22 )
    {
      if ( v22 > 0 )
        NewHostName = (unsigned __int16)v22 | 0x80070000;
      v17 = 3012;
LABEL_46:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v17,
        L"CEventNotificationService::QueryRemoteManagementProperty",
        L"CBRAEx",
        L"err == 0L",
        NewHostName);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = NewHostName;
        lpSecurityAttributesa = L"err == 0L";
        goto LABEL_26;
      }
      LODWORD(lpSecurityAttributes) = NewHostName;
      samDesireda = L"err == 0L";
      goto LABEL_30;
    }
    v23 = RegOpenKeyW(hkey, a3, &hKey);
    NewHostName = v23;
    if ( v23 == 2 )
    {
      NewHostName = GetNewHostName(&bstrString);
      if ( NewHostName < 0 )
        goto LABEL_32;
      if ( !_wcsicmp(a3, bstrString) )
      {
        v24 = SysAllocString((const OLECHAR *)(a1 + 864));
        v53 = v24;
        if ( !v24 )
        {
          v17 = 3026;
          NewHostName = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            0xBD2u,
            L"CEventNotificationService::QueryRemoteManagementProperty",
            L"CPR",
            L"bstrHostNameOld",
            -2147024882);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResult) = -2147024882;
            lpSecurityAttributesa = L"bstrHostNameOld";
            samDesired = L"CPR";
            goto LABEL_27;
          }
          LODWORD(lpSecurityAttributes) = -2147024882;
          samDesireda = L"bstrHostNameOld";
          dwOptions = L"CPR";
          goto LABEL_31;
        }
        a3 = v24;
      }
    }
    else if ( v23 )
    {
      if ( v23 > 0 )
        NewHostName = (unsigned __int16)v23 | 0x80070000;
      v17 = 3033;
      goto LABEL_46;
    }
    v25 = 0;
    switch ( v6 )
    {
      case 0u:
        if ( a2 )
        {
          NewHostName = -2147024809;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            0xC06u,
            L"CEventNotificationService::QueryRemoteManagementProperty",
            L"CBRAEx",
            L"eType == WRMT_Manager",
            -2147024809);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResult) = -2147024809;
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              3078,
              L"CEventNotificationService::QueryRemoteManagementProperty",
              L"CBRAEx",
              L"eType == WRMT_Manager",
              phkResult);
          }
          else
          {
            LODWORD(lpSecurityAttributes) = -2147024809;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              3078,
              L"CEventNotificationService::QueryRemoteManagementProperty",
              L"CBRAEx",
              L"eType == WRMT_Manager",
              lpSecurityAttributes);
          }
          goto LABEL_32;
        }
LABEL_106:
        pcbData = 4;
        v35 = (const WCHAR *)CEventNotificationService::s_RemoteManagementPropertyValueName(v6);
        ValueW = RegGetValueW(hkey, a3, v35, 0x10u, &pdwType, &pvData, &pcbData);
        NewHostName = ValueW;
        if ( ValueW )
        {
          if ( ValueW > 0 )
            NewHostName = (unsigned __int16)ValueW | 0x80070000;
          v17 = 3083;
          goto LABEL_46;
        }
        v20->lVal = pvData;
        v20->vt = 19;
LABEL_71:
        NewHostName = 0;
        v13 = 0;
        goto LABEL_33;
      case 1u:
        v26 = L"WmsManagement";
        break;
      case 2u:
        goto LABEL_73;
      case 3u:
        v26 = L"WmsControl";
        break;
      case 4u:
LABEL_73:
        if ( a2 )
        {
          NewHostName = -2147024809;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            0xBEBu,
            L"CEventNotificationService::QueryRemoteManagementProperty",
            L"CBRAEx",
            L"eType == WRMT_Manager",
            -2147024809);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResult) = -2147024809;
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              3051,
              L"CEventNotificationService::QueryRemoteManagementProperty",
              L"CBRAEx",
              L"eType == WRMT_Manager",
              phkResult);
          }
          else
          {
            LODWORD(lpSecurityAttributes) = -2147024809;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              3051,
              L"CEventNotificationService::QueryRemoteManagementProperty",
              L"CBRAEx",
              L"eType == WRMT_Manager",
              lpSecurityAttributes);
          }
          goto LABEL_32;
        }
        v25 = 1;
        goto LABEL_78;
      case 5u:
LABEL_78:
        v28 = (const WCHAR *)CEventNotificationService::s_RemoteManagementPropertyValueName(v6);
        v29 = RegGetValueW(hkey, a3, v28, 2u, &pdwType, 0, &pcbData);
        NewHostName = v29;
        if ( !v29 || v29 == 234 )
        {
          v45 = (unsigned __int16 *)operator new(pcbData);
          if ( v45 )
          {
            v30 = (const WCHAR *)CEventNotificationService::s_RemoteManagementPropertyValueName(v6);
            v31 = RegGetValueW(hkey, a3, v30, 2u, &pdwType, v45, &pcbData);
            NewHostName = v31;
            if ( !v31 )
            {
              v13 = v45;
              if ( v25 )
              {
                v32 = WmsDecrypt(v45, &psz, &v54);
                v9 = psz;
                NewHostName = v32;
                if ( v32 < 0 )
                  goto LABEL_33;
                v33 = psz;
              }
              else
              {
                v33 = v45;
              }
              v20->vt = 8;
              v34 = SysAllocString(v33);
              v20->llVal = (LONGLONG)v34;
              if ( v34 )
              {
                NewHostName = 0;
              }
              else
              {
                VariantInit(v20);
                NewHostName = v33 != 0 ? -2147024882 : -2147024809;
              }
              goto LABEL_33;
            }
            if ( v31 > 0 )
              NewHostName = (unsigned __int16)v31 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              0xBF9u,
              L"CEventNotificationService::QueryRemoteManagementProperty",
              L"CBRAEx",
              L"err == 0L",
              NewHostName);
            if ( IsDebuggerPresent() )
            {
              LODWORD(phkResult) = NewHostName;
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                3065,
                L"CEventNotificationService::QueryRemoteManagementProperty",
                L"CBRAEx",
                L"err == 0L",
                phkResult);
            }
            else
            {
              LODWORD(lpSecurityAttributesc) = NewHostName;
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                3065,
                L"CEventNotificationService::QueryRemoteManagementProperty",
                L"CBRAEx",
                L"err == 0L",
                lpSecurityAttributesc);
            }
          }
          else
          {
            NewHostName = -2147024882;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              0xBF6u,
              L"CEventNotificationService::QueryRemoteManagementProperty",
              L"CPR",
              L"pszSetting",
              -2147024882);
            if ( IsDebuggerPresent() )
            {
              LODWORD(phkResult) = -2147024882;
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                3062,
                L"CEventNotificationService::QueryRemoteManagementProperty",
                L"CPR",
                L"pszSetting",
                phkResult);
            }
            else
            {
              LODWORD(lpSecurityAttributesb) = -2147024882;
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                3062,
                L"CEventNotificationService::QueryRemoteManagementProperty",
                L"CPR",
                L"pszSetting",
                lpSecurityAttributesb);
            }
          }
          v13 = v45;
LABEL_33:
          v10 = v54;
          goto LABEL_7;
        }
        if ( v29 > 0 )
          NewHostName = (unsigned __int16)v29 | 0x80070000;
LABEL_32:
        v13 = 0;
        goto LABEL_33;
      case 6u:
        goto LABEL_106;
      default:
        v17 = 3090;
        NewHostName = -2147024809;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          0xC12u,
          L"CEventNotificationService::QueryRemoteManagementProperty",
          L"CBRAEx",
          L"0",
          -2147024809);
        v18 = !IsDebuggerPresent();
        v19 = L"0";
        goto LABEL_24;
    }
    v20->vt = 8;
    v27 = SysAllocString(v26);
    v20->llVal = (LONGLONG)v27;
    if ( !v27 )
    {
      VariantInit(v20);
      NewHostName = -2147024882;
      goto LABEL_32;
    }
    goto LABEL_71;
  }
  v11 = 0;
LABEL_5:
  NewHostName = CUserManagement::s_VerifyAccessLevelEx(v11, 0);
  if ( NewHostName >= 0 )
    goto LABEL_22;
  v13 = 0;
LABEL_7:
  operator delete(v13);
  if ( v9 && v10 )
  {
    v14 = v10;
    v15 = v9;
    do
    {
      *(_BYTE *)v15 = 0;
      v15 = (OLECHAR *)((char *)v15 + 1);
      --v14;
    }
    while ( v14 );
  }
  operator delete(v9);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  SysFreeString(bstrString);
  SysFreeString(v53);
  return (unsigned int)NewHostName;
}

```

## disassembly

```asm
0x140021050  push    rbp
0x140021052  push    rbx
0x140021053  push    rsi
0x140021054  push    rdi
0x140021055  push    r12
0x140021057  push    r13
0x140021059  push    r14
0x14002105b  push    r15
0x14002105d  lea     rbp, [rsp-17h]
0x140021062  sub     rsp, 98h
0x140021069  xor     ebx, ebx
0x14002106b  mov     r14, rcx
0x14002106e  mov     ecx, r9d
0x140021071  mov     [rbp+4Fh+hkey], rbx
0x140021075  mov     [rbp+4Fh+pvData], ebx
0x140021078  mov     esi, r9d
0x14002107b  mov     [rbp+4Fh+psz], rbx
0x14002107f  mov     r15, r8
0x140021082  mov     [rbp+4Fh+arg_18], ebx
0x140021085  lea     eax, [rbx+1]
0x140021088  mov     [rbp+4Fh+pdwType], ebx
0x14002108b  mov     r12d, edx
0x14002108e  mov     [rbp+4Fh+pcbData], ebx
0x140021091  mov     r13d, ebx
0x140021094  mov     [rbp+4Fh+hKey], rbx
0x140021098  mov     edi, ebx
0x14002109a  mov     [rbp+4Fh+bstrString], rbx
0x14002109e  mov     [rbp+4Fh+var_48], rbx
0x1400210a2  sub     ecx, 2
0x1400210a5  jz      loc_140021185
0x1400210ab  sub     ecx, 5
0x1400210ae  jz      loc_14002116F
0x1400210b4  cmp     ecx, eax
0x1400210b6  jz      loc_14002114E
0x1400210bc  mov     ecx, eax
0x1400210be  xor     edx, edx
0x1400210c0  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x1400210c5  mov     ebx, eax
0x1400210c7  test    eax, eax
0x1400210c9  jns     loc_14002118C
0x1400210cf  mov     rsi, rdi
0x1400210d2  mov     rcx, rsi; Block
0x1400210d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400210da  xor     esi, esi
0x1400210dc  test    r13, r13
0x1400210df  jz      short loc_1400210F6
0x1400210e1  test    edi, edi
0x1400210e3  jz      short loc_1400210F6
0x1400210e5  mov     edx, edi
0x1400210e7  mov     rax, r13
0x1400210ea  mov     [rax], sil
0x1400210ed  inc     rax
0x1400210f0  sub     rdx, 1
0x1400210f4  jnz     short loc_1400210EA
0x1400210f6  mov     rcx, r13; Block
0x1400210f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400210fe  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140021102  test    rcx, rcx
0x140021105  jz      short loc_140021111
0x140021107  call    cs:__imp_RegCloseKey
0x14002110d  mov     [rbp+4Fh+hKey], rsi
0x140021111  mov     rcx, [rbp+4Fh+hkey]; hKey
0x140021115  test    rcx, rcx
0x140021118  jz      short loc_140021124
0x14002111a  call    cs:__imp_RegCloseKey
0x140021120  mov     [rbp+4Fh+hkey], rsi
0x140021124  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x140021128  call    cs:__imp_SysFreeString
0x14002112e  mov     rcx, [rbp+4Fh+var_48]; bstrString
0x140021132  call    cs:__imp_SysFreeString
0x140021138  mov     eax, ebx
0x14002113a  add     rsp, 98h
0x140021141  pop     r15
0x140021143  pop     r14
0x140021145  pop     r13
0x140021147  pop     r12
0x140021149  pop     rdi
0x14002114a  pop     rsi
0x14002114b  pop     rbx
0x14002114c  pop     rbp
0x14002114d  retn
0x14002114e  mov     edx, eax
0x140021150  xor     ecx, ecx
0x140021152  mov     esi, 2
0x140021157  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x14002115c  test    eax, eax
0x14002115e  jns     short loc_14002118E
0x140021160  mov     esi, 4
0x140021165  mov     ecx, 1
0x14002116a  jmp     loc_1400210BE
0x14002116f  mov     edx, eax
0x140021171  xor     ecx, ecx
0x140021173  mov     esi, eax
0x140021175  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x14002117a  test    eax, eax
0x14002117c  jns     short loc_14002118E
0x14002117e  mov     esi, 3
0x140021183  jmp     short loc_140021165
0x140021185  xor     ecx, ecx
0x140021187  jmp     loc_1400210BE
0x14002118c  xor     ebx, ebx
0x14002118e  test    r15, r15
0x140021191  jnz     loc_14002124A
0x140021197  mov     r15d, 80070057h
0x14002119d  lea     rax, aBstrremotehost; "bstrRemoteHostName"
0x1400211a4  lea     r14, aCbraex; "CBRAEx"
0x1400211ab  mov     [rsp+0D0h+samDesired], r15d; int
0x1400211b0  lea     rsi, aCeventnotifica_204; "CEventNotificationService::QueryRemoteM"...
0x1400211b7  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned __int16 *
0x1400211bc  mov     r12d, 0BBDh
0x1400211c2  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400211c9  mov     r9, r14; unsigned __int16 *
0x1400211cc  mov     r8, rsi; unsigned __int16 *
0x1400211cf  mov     edx, r12d; unsigned int
0x1400211d2  mov     rcx, rdi; unsigned __int16 *
0x1400211d5  mov     ebx, r15d
0x1400211d8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400211dd  call    cs:__imp_IsDebuggerPresent
0x1400211e3  test    eax, eax
0x1400211e5  lea     rax, aBstrremotehost; "bstrRemoteHostName"
0x1400211ec  jz      short loc_14002121B
0x1400211ee  mov     dword ptr [rsp+0D0h+phkResult], r15d
0x1400211f3  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x1400211f8  mov     qword ptr [rsp+0D0h+samDesired], r14
0x1400211fd  mov     r9d, r12d
0x140021200  mov     r8, rdi
0x140021203  mov     qword ptr [rsp+0D0h+dwOptions], rsi
0x140021208  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002120f  mov     ecx, 2; unsigned __int8
0x140021214  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140021219  jmp     short loc_14002123F
0x14002121b  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], r15d
0x140021220  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140021225  mov     qword ptr [rsp+0D0h+dwOptions], r14
0x14002122a  mov     r8d, r12d
0x14002122d  mov     r9, rsi
0x140021230  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140021237  mov     rdx, rdi
0x14002123a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002123f  mov     rsi, r13
0x140021242  mov     edi, [rbp+4Fh+arg_18]
0x140021245  jmp     loc_1400210D2
0x14002124a  mov     rdi, [rbp+4Fh+pvarg]
0x14002124e  test    rdi, rdi
0x140021251  jnz     short loc_1400212CA
0x140021253  mov     ebx, 80004003h
0x140021258  lea     r14, aCbraex; "CBRAEx"
0x14002125f  lea     rsi, aCeventnotifica_204; "CEventNotificationService::QueryRemoteM"...
0x140021266  mov     [rsp+0D0h+samDesired], ebx; int
0x14002126a  mov     r15d, 0BBEh
0x140021270  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140021277  lea     r12, aPvarsetting; "pvarSetting"
0x14002127e  mov     r9, r14; unsigned __int16 *
0x140021281  mov     r8, rsi; unsigned __int16 *
0x140021284  mov     qword ptr [rsp+0D0h+dwOptions], r12; unsigned __int16 *
0x140021289  mov     edx, r15d; unsigned int
0x14002128c  mov     rcx, rdi; unsigned __int16 *
0x14002128f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140021294  call    cs:__imp_IsDebuggerPresent
0x14002129a  test    eax, eax
0x14002129c  jz      short loc_1400212B4
0x14002129e  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x1400212a2  mov     r9d, r15d
0x1400212a5  mov     [rsp+0D0h+lpSecurityAttributes], r12
0x1400212aa  mov     qword ptr [rsp+0D0h+samDesired], r14
0x1400212af  jmp     loc_140021200
0x1400212b4  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], ebx
0x1400212b8  mov     r8d, r15d
0x1400212bb  mov     qword ptr [rsp+0D0h+samDesired], r12
0x1400212c0  mov     qword ptr [rsp+0D0h+dwOptions], r14
0x1400212c5  jmp     loc_14002122D
0x1400212ca  cmp     cs:?m_sShutdownInProgress@CEventNotificationService@@2HA, ebx; int CEventNotificationService::m_sShutdownInProgress
0x1400212d0  jz      short loc_1400212DC
0x1400212d2  mov     ebx, 8007045Bh
0x1400212d7  jmp     loc_14002123F
0x1400212dc  mov     rcx, rdi; pvarg
0x1400212df  call    cs:__imp_VariantInit
0x1400212e5  mov     [rsp+0D0h+lpdwDisposition], rbx; lpdwDisposition
0x1400212ea  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows MultiPoint"...
0x1400212f1  test    r12d, r12d
0x1400212f4  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows MultiPoint"...
0x1400212fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140021302  cmovnz  rdx, rax; lpSubKey
0x140021306  lea     rax, [rbp+4Fh+hkey]
0x14002130a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x14002130f  xor     r9d, r9d; lpClass
0x140021312  mov     [rsp+0D0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x140021317  xor     r8d, r8d; Reserved
0x14002131a  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x140021322  mov     [rsp+0D0h+dwOptions], ebx; dwOptions
0x140021326  call    cs:__imp_RegCreateKeyExW
0x14002132c  mov     ebx, eax
0x14002132e  test    eax, eax
0x140021330  jz      short loc_14002139F
0x140021332  jle     short loc_14002133D
0x140021334  movzx   ebx, ax
0x140021337  or      ebx, 80070000h
0x14002133d  mov     r12d, 0BC4h
0x140021343  lea     r14, aCbraex; "CBRAEx"
0x14002134a  mov     [rsp+0D0h+samDesired], ebx; int
0x14002134e  lea     rsi, aCeventnotifica_204; "CEventNotificationService::QueryRemoteM"...
0x140021355  mov     r9, r14; unsigned __int16 *
0x140021358  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002135f  mov     r8, rsi; unsigned __int16 *
0x140021362  lea     r15, aErr0l; "err == 0L"
0x140021369  mov     rcx, rdi; unsigned __int16 *
0x14002136c  mov     edx, r12d; unsigned int
0x14002136f  mov     qword ptr [rsp+0D0h+dwOptions], r15; unsigned __int16 *
0x140021374  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140021379  call    cs:__imp_IsDebuggerPresent
0x14002137f  test    eax, eax
0x140021381  jz      short loc_140021391
0x140021383  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x140021387  mov     [rsp+0D0h+lpSecurityAttributes], r15
0x14002138c  jmp     loc_1400211F8
0x140021391  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], ebx
0x140021395  mov     qword ptr [rsp+0D0h+samDesired], r15
0x14002139a  jmp     loc_140021225
0x14002139f  mov     rcx, [rbp+4Fh+hkey]; hKey
0x1400213a3  lea     r8, [rbp+4Fh+hKey]; phkResult
0x1400213a7  mov     rdx, r15; lpSubKey
0x1400213aa  call    cs:__imp_RegOpenKeyW
0x1400213b0  mov     ebx, eax
0x1400213b2  cmp     eax, 2
0x1400213b5  jnz     loc_140021518
0x1400213bb  lea     rcx, [rbp+4Fh+bstrString]; unsigned __int16 **
0x1400213bf  call    ?GetNewHostName@@YAJPEAPEAG@Z; GetNewHostName(ushort * *)
0x1400213c4  mov     ebx, eax
0x1400213c6  test    eax, eax
0x1400213c8  js      loc_14002123F
0x1400213ce  mov     rdx, [rbp+4Fh+bstrString]; String2
0x1400213d2  mov     rcx, r15; String1
0x1400213d5  call    cs:__imp__wcsicmp
0x1400213db  test    eax, eax
0x1400213dd  jnz     loc_14002147B
0x1400213e3  lea     rcx, [r14+360h]; psz
0x1400213ea  call    cs:__imp_SysAllocString
0x1400213f0  mov     [rbp+4Fh+var_48], rax
0x1400213f4  test    rax, rax
0x1400213f7  jnz     short loc_140021478
0x1400213f9  mov     r14d, 8007000Eh
0x1400213ff  lea     rax, aBstrhostnameol; "bstrHostNameOld"
0x140021406  lea     r15, aCpr; "CPR"
0x14002140d  mov     [rsp+0D0h+samDesired], r14d; int
0x140021412  lea     rsi, aCeventnotifica_204; "CEventNotificationService::QueryRemoteM"...
0x140021419  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned __int16 *
0x14002141e  mov     r12d, 0BD2h
0x140021424  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002142b  mov     r9, r15; unsigned __int16 *
0x14002142e  mov     r8, rsi; unsigned __int16 *
0x140021431  mov     edx, r12d; unsigned int
0x140021434  mov     rcx, rdi; unsigned __int16 *
0x140021437  mov     ebx, r14d
0x14002143a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002143f  call    cs:__imp_IsDebuggerPresent
0x140021445  test    eax, eax
0x140021447  lea     rax, aBstrhostnameol; "bstrHostNameOld"
0x14002144e  jz      short loc_140021464
0x140021450  mov     dword ptr [rsp+0D0h+phkResult], r14d
0x140021455  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x14002145a  mov     qword ptr [rsp+0D0h+samDesired], r15
0x14002145f  jmp     loc_1400211FD
0x140021464  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], r14d
0x140021469  mov     qword ptr [rsp+0D0h+samDesired], rax
0x14002146e  mov     qword ptr [rsp+0D0h+dwOptions], r15
0x140021473  jmp     loc_14002122A
0x140021478  mov     r15, rax
0x14002147b  xor     r14d, r14d
0x14002147e  mov     ecx, esi
0x140021480  test    esi, esi
0x140021482  jz      loc_140021842
0x140021488  sub     ecx, 1
0x14002148b  jz      loc_140021836
0x140021491  sub     ecx, 1
0x140021494  jz      loc_14002156D
0x14002149a  sub     ecx, 1
0x14002149d  jz      loc_140021536
0x1400214a3  sub     ecx, 1
0x1400214a6  jz      loc_14002156D
0x1400214ac  sub     ecx, 1
0x1400214af  jz      loc_1400215FC
0x1400214b5  cmp     ecx, 1
0x1400214b8  jz      loc_1400218CB
0x1400214be  mov     r15d, 80070057h
0x1400214c4  lea     rax, a0; "0"
0x1400214cb  lea     r14, aCbraex; "CBRAEx"
0x1400214d2  mov     [rsp+0D0h+samDesired], r15d; int
0x1400214d7  lea     rsi, aCeventnotifica_204; "CEventNotificationService::QueryRemoteM"...
0x1400214de  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned __int16 *
0x1400214e3  mov     r12d, 0C12h
0x1400214e9  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400214f0  mov     r9, r14; unsigned __int16 *
0x1400214f3  mov     r8, rsi; unsigned __int16 *
0x1400214f6  mov     edx, r12d; unsigned int
0x1400214f9  mov     rcx, rdi; unsigned __int16 *
0x1400214fc  mov     ebx, r15d
0x1400214ff  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140021504  call    cs:__imp_IsDebuggerPresent
0x14002150a  test    eax, eax
0x14002150c  lea     rax, a0; "0"
  ... truncated ...
```
