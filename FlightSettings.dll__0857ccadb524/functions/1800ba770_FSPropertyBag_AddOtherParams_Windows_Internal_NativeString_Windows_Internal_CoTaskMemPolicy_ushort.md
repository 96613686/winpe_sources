# FSPropertyBag::AddOtherParams(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x1800ba770`
- end: `0x1800bb119`
- name: `?AddOtherParams@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `2473`
- prototype: `__int64 __fastcall(FSPropertyBag *this)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bb5ec`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x18001c6f4`
- `0x1800254ac`
- `0x180046664`
- `0x1800859a4`
- `0x180086644`
- `0x180089f28`
- `0x18008a2fc`
- `0x18008aaf0`
- `0x18008af10`
- `0x180094d34`
- `0x180095a3c`
- `0x1800960cc`
- `0x180096674`
- `0x1800ba6e0`
- `0x1800ba770`
- `0x1800bb31c`
- `0x1800bf03c`
- `0x1800bf104`
- `0x1800c0588`
- `0x1800c0bf0`
- `0x1800c0c54`
- `0x1800c0d58`
- `0x1800c189c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800badb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800badb4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800bada5`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800bada5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800bad3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800bad3a`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800bac53`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800bac53`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1800bad77`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1800bad77`
- `NETAPI32!NetFreeAadJoinInformation` at `0x1800bafac`
- `NETAPI32!NetFreeAadJoinInformation` at `0x1800bafac`
- `NETAPI32!NetGetAadJoinInformation` at `0x1800baf2d`
- `NETAPI32!NetGetAadJoinInformation` at `0x1800baf2d`

## string_xrefs

- `0x1800ba7e0`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x1800bafb2`: `serviceInfo`
- `0x1800bb00f`: `serviceInfo`
- `0x1800badda`: `installLanguage`
- `0x1800ba82d`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800ba965`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800baa13`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800baba1`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800baee2`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bb031`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800ba875`: `IsVMCached`
- `0x1800ba8a4`: `IsVMCached`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FSPropertyBag::AddOtherParams(FSPropertyBag *this, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  BOOL v6; // eax
  int updated; // ebx
  __int64 v8; // rdx
  bool IsVM; // al
  unsigned int DeviceType; // eax
  int v11; // eax
  int v12; // eax
  unsigned int *v13; // r8
  __int64 v14; // rdx
  int v15; // ebx
  unsigned int CallerProcessImageName; // eax
  __int64 v17; // rcx
  const struct _GUID *v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  int Instance; // ebx
  unsigned int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rcx
  FlightSettingsAPITelemetryClass *v28; // rax
  BOOL ProductInfo; // eax
  __int64 v30; // rcx
  LCID SystemDefaultUILanguage; // ebx
  signed int LastError; // eax
  FSPropertyBag *v33; // rcx
  FSPropertyBag *v34; // rcx
  FSPropertyBag *v35; // rcx
  int v36; // eax
  __int64 v37; // rdx
  int AadJoinInformation; // eax
  unsigned int v39; // r14d
  __int64 v40; // r15
  unsigned int v41; // eax
  int v42; // eax
  unsigned int v43; // eax
  WCHAR *pdwReturnedProductType; // [rsp+20h] [rbp-E0h]
  int pdwReturnedProductTypea; // [rsp+20h] [rbp-E0h]
  int pdwReturnedProductTypeb; // [rsp+20h] [rbp-E0h]
  int pdwReturnedProductTypec; // [rsp+20h] [rbp-E0h]
  bool v49[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpExeName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwSize[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v53; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h]
  __int64 v56; // [rsp+78h] [rbp-88h]
  DWORD v57; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSize[3]; // [rsp+84h] [rbp-7Ch] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR LCData[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  if ( !FSPropertyBag::ShouldIncludeProperty(this, L"isUserAdmin") )
    goto LABEL_94;
  LODWORD(v51) = 0;
  v4 = LUAIsUserUACAdmin(&v51);
  v5 = v4 | 0x10000000;
  if ( v4 >= 0 )
  {
    v6 = v51 != 0;
    v5 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
      (const char *)v5,
      (int)pdwReturnedProductType);
    v6 = 0;
  }
  LODWORD(pdwReturnedProductType) = v6;
  updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"isUserAdmin", v5);
  if ( updated >= 0 )
  {
LABEL_94:
    if ( FSPropertyBag::ShouldIncludeProperty(this, L"isVirtualMachine") )
    {
      LODWORD(v51) = 0;
      lpExeName = (LPWSTR)-2147483646LL;
      if ( (int)FSRegUtils::GetFlightingRegDWORD((HKEY *)&lpExeName, 2u, L"IsVMCached", (unsigned int *)&v51) < 0 )
      {
        IsVM = FlightSettingsAPICommon::IsVM();
        LODWORD(v51) = IsVM;
        lpExeName = (LPWSTR)-2147483646LL;
        FSRegUtils::SetFlightingRegDWORD(&lpExeName, 2, L"IsVMCached", IsVM);
      }
      LODWORD(pdwReturnedProductType) = v51;
      updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"isVirtualMachine", 0);
      if ( updated < 0 )
      {
        v8 = 1027;
        goto LABEL_7;
      }
    }
    if ( FSPropertyBag::ShouldIncludeProperty(this, L"deviceType") )
    {
      v54 = 0;
      v55 = 0;
      v56 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
      v55 = -1;
      v56 = -1;
      DeviceType = FlightSettingsAPICommon::GetDeviceType(&v54);
      LODWORD(pdwReturnedProductType) = (_DWORD)v54;
      v11 = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"deviceType", DeviceType);
      updated = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
          (const char *)(unsigned int)v11,
          (int)pdwReturnedProductType);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
        return (unsigned int)updated;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
    }
    if ( FSPropertyBag::ShouldIncludeProperty(this, L"callerProcessImageName") )
    {
      dwSize[0] = 260;
      lpExeName = 0;
      v12 = _AllocArray<unsigned short,CTCoAllocPolicy>(260, 1, 260, &lpExeName);
      updated = v12;
      if ( v12 < 0 )
      {
        v14 = 1041;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
          (const char *)(unsigned int)v12,
          (int)pdwReturnedProductType);
LABEL_90:
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpExeName);
        return (unsigned int)updated;
      }
      v15 = (int)lpExeName;
      CallerProcessImageName = CallerIdentity::GetCallerProcessImageName(lpExeName, dwSize, v13);
      LODWORD(pdwReturnedProductType) = v15;
      v12 = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"callerProcessImageName", CallerProcessImageName);
      updated = v12;
      if ( v12 < 0 )
      {
        v14 = 1043;
        goto LABEL_22;
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpExeName);
    }
    if ( FSPropertyBag::ShouldIncludeProperty(this, L"connectedToCorpnetWifi")
      || FSPropertyBag::ShouldIncludeProperty(this, L"connectedToCorpnetVPN")
      || FSPropertyBag::ShouldIncludeProperty(this, L"connectionCostType") )
    {
      lpExeName = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&lpExeName);
      Instance = FSNetworkingInfo_CreateInstance(v18, (void **)&lpExeName);
      if ( Instance < 0 )
      {
        if ( FlightSettingsAPITelemetryClass::IsEnabled(v20, v19) )
        {
          v28 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                     v27,
                                                     _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
          FlightSettingsAPITelemetryClass::AddNetworkingSpecificPropertiesFailed_(v28, Instance);
        }
      }
      else
      {
        LODWORD(v51) = 0;
        if ( FSPropertyBag::ShouldIncludeProperty(this, L"connectedToCorpnetWifi") )
        {
          v22 = (*(__int64 (__fastcall **)(LPWSTR, __int64 *))(*(_QWORD *)lpExeName + 32LL))(lpExeName, &v51);
          pdwReturnedProductTypea = v51;
          v23 = FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(this, a2, L"connectedToCorpnetWifi", v22);
          updated = v23;
          if ( v23 < 0 )
          {
            v24 = 1061;
LABEL_37:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v24,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
              (const char *)(unsigned int)v23,
              pdwReturnedProductTypea);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&lpExeName);
            return (unsigned int)updated;
          }
        }
        if ( FSPropertyBag::ShouldIncludeProperty(this, L"connectedToCorpnetVPN") )
        {
          v25 = (*(__int64 (__fastcall **)(LPWSTR, __int64 *))(*(_QWORD *)lpExeName + 40LL))(lpExeName, &v51);
          pdwReturnedProductTypea = v51;
          v23 = FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(this, a2, L"connectedToCorpnetVPN", v25);
          updated = v23;
          if ( v23 < 0 )
          {
            v24 = 1067;
            goto LABEL_37;
          }
        }
        if ( FSPropertyBag::ShouldIncludeProperty(this, L"connectionCostType") )
        {
          dwSize[0] = 0;
          v26 = (*(__int64 (__fastcall **)(LPWSTR, DWORD *))(*(_QWORD *)lpExeName + 24LL))(lpExeName, dwSize);
          pdwReturnedProductTypea = dwSize[0];
          v23 = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"connectionCostType", v26);
          updated = v23;
          if ( v23 < 0 )
          {
            v24 = 1074;
            goto LABEL_37;
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&lpExeName);
    }
    lpExeName = (LPWSTR)-2147483646LL;
    pdwReturnedProductType = L"MachineId";
    updated = FSPropertyBag::AddStringRegKeyToParams(v17, a2, L"sqmMachineId", L"Software\\Microsoft\\SqmClient");
    if ( updated < 0 )
    {
      v8 = 1085;
      goto LABEL_7;
    }
    v57 = 0;
    ProductInfo = GetProductInfo(0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, &v57);
    LODWORD(pdwReturnedProductType) = v57;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"ossku", !ProductInfo ? 0x80004005 : 0);
    if ( updated < 0 )
    {
      v8 = 1090;
      goto LABEL_7;
    }
    lpExeName = (LPWSTR)-2147483646LL;
    pdwReturnedProductType = (WCHAR *)L"EditionID";
    updated = FSPropertyBag::AddStringRegKeyToParams(
                v30,
                a2,
                L"osEdition",
                L"Software\\Microsoft\\Windows NT\\CurrentVersion");
    if ( updated < 0 )
    {
      v8 = 1093;
      goto LABEL_7;
    }
    pdwReturnedProductType = L"AMD64";
    updated = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"osArchitecture", 0);
    if ( updated < 0 )
    {
      v8 = 1096;
      goto LABEL_7;
    }
    memset_0(Buffer, 0, 0x208u);
    nSize[0] = 260;
    if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, Buffer, nSize) )
    {
      pdwReturnedProductType = Buffer;
      updated = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"deviceName", 0);
      if ( updated < 0 )
      {
        v8 = 1103;
        goto LABEL_7;
      }
    }
    SystemDefaultUILanguage = GetSystemDefaultUILanguage();
    memset_0(LCData, 0, 0x208u);
    if ( GetLocaleInfoW(SystemDefaultUILanguage, 0x5Cu, LCData, 260) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    pdwReturnedProductType = LCData;
    updated = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"installLanguage", (unsigned int)LastError);
    if ( updated < 0 )
    {
      v8 = 1112;
      goto LABEL_7;
    }
    v49[0] = 0;
    FlightSettingsAPICommon::IsLocalSystem(v49);
    lpExeName = 0;
    if ( v49[0] )
    {
      v49[0] = 0;
      if ( (int)ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)v49) < 0
        || (int)FSPropertyBag::GetUserLocale(v34, &lpExeName) < 0 )
      {
        FSPropertyBag::GetSystemLocale(v34, &lpExeName);
      }
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v49);
    }
    else if ( (int)FSPropertyBag::GetUserLocale(v33, &lpExeName) < 0 )
    {
      FSPropertyBag::GetSystemLocale(v35, &lpExeName);
    }
    pdwReturnedProductTypeb = (int)lpExeName;
    v36 = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"osUILocale", 0);
    updated = v36;
    if ( v36 >= 0 )
    {
      if ( !FSPropertyBag::ShouldIncludeProperty(this, L"userActivityPresence")
        || (pdwReturnedProductTypeb = 0,
            v36 = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"userActivityPresence", 2147942402LL),
            updated = v36,
            v36 >= 0) )
      {
        if ( FSPropertyBag::ShouldIncludeProperty(this, L"AADTenantId")
          && FSPropertyBag::ShouldIncludeProperty(this, L"DeviceJoinType") )
        {
          *(_QWORD *)dwSize = 0;
          AadJoinInformation = NetGetAadJoinInformation(0, dwSize);
          v39 = AadJoinInformation;
          if ( AadJoinInformation >= 0 )
          {
            if ( *(_QWORD *)dwSize )
            {
              v40 = *(_QWORD *)(*(_QWORD *)dwSize + 32LL);
              pdwReturnedProductTypeb = **(_DWORD **)dwSize;
              v36 = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                      this,
                      a2,
                      L"DeviceJoinType",
                      (unsigned int)AadJoinInformation);
              updated = v36;
              if ( v36 < 0 )
              {
                v37 = 1175;
                goto LABEL_70;
              }
              pdwReturnedProductTypeb = v40;
              v36 = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"AADTenantId", v39);
              updated = v36;
              if ( v36 < 0 )
              {
                v37 = 1176;
                goto LABEL_70;
              }
              NetFreeAadJoinInformation(*(_QWORD *)dwSize);
            }
          }
        }
        if ( FSPropertyBag::ShouldIncludeProperty(this, L"serviceInfo") )
        {
          v54 = 0;
          v55 = 0;
          v56 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
          v55 = -1;
          v56 = -1;
          v41 = FSPropertyBag::QueryServiceList(this, &v54);
          pdwReturnedProductTypec = (int)v54;
          v42 = FSPropertyBag::UpdateParamsWithStringBasedOnHr(this, a2, L"serviceInfo", v41);
          updated = v42;
          if ( v42 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4A3,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
              (const char *)(unsigned int)v42,
              pdwReturnedProductTypec);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
            goto LABEL_90;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
        }
        v53 = 0;
        v51 = -2147483646;
        if ( (int)FSRegUtils::GetFlightingRegDWORD((HKEY *)&v51, 8u, L"UIUsage", &v53) >= 0 )
        {
          v43 = v53;
        }
        else
        {
          v43 = 0;
          v53 = 0;
        }
        pdwReturnedProductTypeb = v43;
        v36 = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"uiTelemetry", 0);
        updated = v36;
        if ( v36 >= 0 )
        {
          v51 = -2147483646;
          FSRegUtils::SetFlightingRegDWORD(&v51, 8, L"UIUsage", 0);
          updated = 0;
          goto LABEL_90;
        }
        v37 = 1199;
        goto LABEL_70;
      }
      v37 = 1163;
    }
    else
    {
      v37 = 1154;
    }
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v36,
      pdwReturnedProductTypeb);
    goto LABEL_90;
  }
  v8 = 1014;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
    (const char *)(unsigned int)updated,
    (int)pdwReturnedProductType);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800ba770  mov     [rsp-8+arg_10], rbx
0x1800ba775  push    rbp
0x1800ba776  push    rsi
0x1800ba777  push    rdi
0x1800ba778  push    r12
0x1800ba77a  push    r13
0x1800ba77c  push    r14
0x1800ba77e  push    r15
0x1800ba780  lea     rbp, [rsp-3C0h]
0x1800ba788  sub     rsp, 4C0h
0x1800ba78f  mov     rax, cs:__security_cookie
0x1800ba796  xor     rax, rsp
0x1800ba799  mov     [rbp+3F0h+var_40], rax
0x1800ba7a0  mov     rsi, rdx
0x1800ba7a3  mov     rdi, rcx
0x1800ba7a6  lea     rdx, aIsuseradmin; "isUserAdmin"
0x1800ba7ad  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba7b2  xor     r12d, r12d
0x1800ba7b5  test    al, al
0x1800ba7b7  jz      loc_1800BA848
0x1800ba7bd  mov     dword ptr [rsp+4F0h+var_4A0], r12d
0x1800ba7c2  lea     rcx, [rsp+4F0h+var_4A0]
0x1800ba7c7  call    LUAIsUserUACAdmin
0x1800ba7cc  mov     ebx, eax
0x1800ba7ce  or      ebx, 10000000h
0x1800ba7d4  jge     short loc_1800BA7F6
0x1800ba7d6  mov     rcx, [rbp+3F8h]; this
0x1800ba7dd  mov     r9d, ebx; char *
0x1800ba7e0  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x1800ba7e7  mov     edx, 0A0h; void *
0x1800ba7ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba7f1  mov     eax, r12d
0x1800ba7f4  jmp     short loc_1800BA804
0x1800ba7f6  mov     eax, r12d
0x1800ba7f9  cmp     dword ptr [rsp+4F0h+var_4A0], r12d
0x1800ba7fe  setnz   al
0x1800ba801  mov     ebx, r12d
0x1800ba804  mov     [rsp+4F0h+var_4C8], r12b
0x1800ba809  mov     dword ptr [rsp+4F0h+pdwReturnedProductType], eax; int
0x1800ba80d  mov     r9d, ebx
0x1800ba810  lea     r8, aIsuseradmin; "isUserAdmin"
0x1800ba817  mov     rdx, rsi
0x1800ba81a  mov     rcx, rdi
0x1800ba81d  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba822  mov     ebx, eax
0x1800ba824  test    eax, eax
0x1800ba826  jns     short loc_1800BA848
0x1800ba828  mov     edx, 3F6h; void *
0x1800ba82d  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba834  mov     r9d, ebx; char *
0x1800ba837  mov     rcx, [rbp+3F8h]; this
0x1800ba83e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba843  jmp     loc_1800BB0ED
0x1800ba848  lea     rdx, aIsvirtualmachi; "isVirtualMachine"
0x1800ba84f  mov     rcx, rdi; this
0x1800ba852  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba857  mov     r14, 0FFFFFFFF80000002h
0x1800ba85e  test    al, al
0x1800ba860  jz      loc_1800BA8E9
0x1800ba866  mov     dword ptr [rsp+4F0h+var_4A0], r12d
0x1800ba86b  mov     [rsp+4F0h+lpExeName], r14
0x1800ba870  lea     r9, [rsp+4F0h+var_4A0]
0x1800ba875  lea     r8, aIsvmcached; "IsVMCached"
0x1800ba87c  mov     ebx, 2
0x1800ba881  mov     edx, ebx
0x1800ba883  lea     rcx, [rsp+4F0h+lpExeName]
0x1800ba888  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x1800ba88d  test    eax, eax
0x1800ba88f  jns     short loc_1800BA8B7
0x1800ba891  call    ?IsVM@FlightSettingsAPICommon@@SA_NXZ; FlightSettingsAPICommon::IsVM(void)
0x1800ba896  movzx   r9d, al
0x1800ba89a  mov     dword ptr [rsp+4F0h+var_4A0], r9d
0x1800ba89f  mov     [rsp+4F0h+lpExeName], r14
0x1800ba8a4  lea     r8, aIsvmcached; "IsVMCached"
0x1800ba8ab  mov     edx, ebx
0x1800ba8ad  lea     rcx, [rsp+4F0h+lpExeName]
0x1800ba8b2  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800ba8b7  mov     [rsp+4F0h+var_4C8], r12b
0x1800ba8bc  mov     eax, dword ptr [rsp+4F0h+var_4A0]
0x1800ba8c0  mov     dword ptr [rsp+4F0h+pdwReturnedProductType], eax
0x1800ba8c4  xor     r9d, r9d
0x1800ba8c7  lea     r8, aIsvirtualmachi; "isVirtualMachine"
0x1800ba8ce  mov     rdx, rsi
0x1800ba8d1  mov     rcx, rdi
0x1800ba8d4  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba8d9  mov     ebx, eax
0x1800ba8db  test    eax, eax
0x1800ba8dd  jns     short loc_1800BA8E9
0x1800ba8df  mov     edx, 403h
0x1800ba8e4  jmp     loc_1800BA82D
0x1800ba8e9  lea     rdx, aDevicetype; "deviceType"
0x1800ba8f0  mov     rcx, rdi; this
0x1800ba8f3  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba8f8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ba8fc  test    al, al
0x1800ba8fe  jz      loc_1800BA990
0x1800ba904  mov     [rsp+4F0h+var_488], r12
0x1800ba909  mov     [rsp+4F0h+var_480], r12
0x1800ba90e  mov     [rsp+4F0h+var_478], r12
0x1800ba913  lea     rcx, [rsp+4F0h+var_488]
0x1800ba918  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ba91d  mov     [rsp+4F0h+var_480], rbx
0x1800ba922  mov     [rsp+4F0h+var_478], rbx
0x1800ba927  lea     rcx, [rsp+4F0h+var_488]; unsigned __int16 **
0x1800ba92c  call    ?GetDeviceType@FlightSettingsAPICommon@@SAJPEAPEAG@Z; FlightSettingsAPICommon::GetDeviceType(ushort * *)
0x1800ba931  mov     [rsp+4F0h+var_4C8], r12b
0x1800ba936  mov     rcx, [rsp+4F0h+var_488]
0x1800ba93b  mov     [rsp+4F0h+pdwReturnedProductType], rcx; int
0x1800ba940  mov     r9d, eax
0x1800ba943  lea     r8, aDevicetype; "deviceType"
0x1800ba94a  mov     rdx, rsi
0x1800ba94d  mov     rcx, rdi
0x1800ba950  call    ?UpdateParamsWithStringBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJ1_N@Z; FSPropertyBag::UpdateParamsWithStringBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ushort const *,bool)
0x1800ba955  mov     ebx, eax
0x1800ba957  test    eax, eax
0x1800ba959  jns     short loc_1800BA986
0x1800ba95b  mov     rcx, [rbp+3F8h]; this
0x1800ba962  mov     r9d, eax; char *
0x1800ba965  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba96c  mov     edx, 40Ah; void *
0x1800ba971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba976  nop
0x1800ba977  lea     rcx, [rsp+4F0h+var_488]
0x1800ba97c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ba981  jmp     loc_1800BB0ED
0x1800ba986  lea     rcx, [rsp+4F0h+var_488]
0x1800ba98b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ba990  lea     rdx, aCallerprocessi; "callerProcessImageName"
0x1800ba997  mov     rcx, rdi; this
0x1800ba99a  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba99f  mov     ecx, 104h
0x1800ba9a4  test    al, al
0x1800ba9a6  jz      loc_1800BAA36
0x1800ba9ac  mov     [rsp+4F0h+dwSize], ecx
0x1800ba9b0  mov     [rsp+4F0h+lpExeName], r12
0x1800ba9b5  lea     r9, [rsp+4F0h+lpExeName]
0x1800ba9ba  mov     r8d, ecx
0x1800ba9bd  mov     edx, 1
0x1800ba9c2  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800ba9c7  mov     ebx, eax
0x1800ba9c9  test    eax, eax
0x1800ba9cb  jns     short loc_1800BA9D4
0x1800ba9cd  mov     edx, 411h
0x1800ba9d2  jmp     short loc_1800BAA10
0x1800ba9d4  lea     rdx, [rsp+4F0h+dwSize]; lpdwSize
0x1800ba9d9  mov     rbx, [rsp+4F0h+lpExeName]
0x1800ba9de  mov     rcx, rbx; lpExeName
0x1800ba9e1  call    ?GetCallerProcessImageName@CallerIdentity@@YAJPEAGPEAK@Z; CallerIdentity::GetCallerProcessImageName(ushort *,ulong *)
0x1800ba9e6  mov     [rsp+4F0h+var_4C8], r12b
0x1800ba9eb  mov     [rsp+4F0h+pdwReturnedProductType], rbx; int
0x1800ba9f0  mov     r9d, eax
0x1800ba9f3  lea     r8, aCallerprocessi; "callerProcessImageName"
0x1800ba9fa  mov     rdx, rsi
0x1800ba9fd  mov     rcx, rdi
0x1800baa00  call    ?UpdateParamsWithStringBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJ1_N@Z; FSPropertyBag::UpdateParamsWithStringBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ushort const *,bool)
0x1800baa05  mov     ebx, eax
0x1800baa07  test    eax, eax
0x1800baa09  jns     short loc_1800BAA2C
0x1800baa0b  mov     edx, 413h; void *
0x1800baa10  mov     r9d, eax; char *
0x1800baa13  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800baa1a  mov     rcx, [rbp+3F8h]; this
0x1800baa21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baa26  nop
0x1800baa27  jmp     loc_1800BB0E3
0x1800baa2c  lea     rcx, [rsp+4F0h+lpExeName]
0x1800baa31  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800baa36  lea     r14, aConnectedtocor; "connectedToCorpnetWifi"
0x1800baa3d  mov     rdx, r14; unsigned __int16 *
0x1800baa40  mov     rcx, rdi; this
0x1800baa43  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800baa48  lea     r15, aConnectedtocor_1; "connectedToCorpnetVPN"
0x1800baa4f  lea     r13, aConnectioncost; "connectionCostType"
0x1800baa56  test    al, al
0x1800baa58  jnz     short loc_1800BAA7C
0x1800baa5a  mov     rdx, r15; unsigned __int16 *
0x1800baa5d  mov     rcx, rdi; this
0x1800baa60  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800baa65  test    al, al
0x1800baa67  jnz     short loc_1800BAA7C
0x1800baa69  mov     rdx, r13; unsigned __int16 *
0x1800baa6c  mov     rcx, rdi; this
0x1800baa6f  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800baa74  test    al, al
0x1800baa76  jz      loc_1800BABEE
0x1800baa7c  mov     [rsp+4F0h+lpExeName], r12
0x1800baa81  lea     rcx, [rsp+4F0h+lpExeName]
0x1800baa86  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800baa8b  lea     rdx, [rsp+4F0h+lpExeName]; void **
0x1800baa90  call    ?FSNetworkingInfo_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; FSNetworkingInfo_CreateInstance(_GUID const &,void * *)
0x1800baa95  mov     ebx, eax
0x1800baa97  test    eax, eax
0x1800baa99  js      loc_1800BABC4
0x1800baa9f  mov     dword ptr [rsp+4F0h+var_4A0], r12d
0x1800baaa4  mov     rdx, r14; unsigned __int16 *
0x1800baaa7  mov     rcx, rdi; this
0x1800baaaa  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800baaaf  test    al, al
0x1800baab1  jz      short loc_1800BAAF7
0x1800baab3  mov     rcx, [rsp+4F0h+lpExeName]
0x1800baab8  mov     rax, [rcx]
0x1800baabb  lea     rdx, [rsp+4F0h+var_4A0]
0x1800baac0  mov     rax, [rax+20h]
0x1800baac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baac9  mov     byte ptr [rsp+4F0h+var_4C0], r12b
0x1800baace  mov     ecx, dword ptr [rsp+4F0h+var_4A0]
0x1800baad2  mov     dword ptr [rsp+4F0h+pdwReturnedProductType], ecx
0x1800baad6  mov     r9d, eax
0x1800baad9  mov     r8, r14
0x1800baadc  mov     rdx, rsi
0x1800baadf  mov     rcx, rdi
0x1800baae2  call    ?UpdateParamsWithBooleanBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJH1_N@Z; FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,int,ushort const *,bool)
0x1800baae7  mov     ebx, eax
0x1800baae9  test    eax, eax
0x1800baaeb  jns     short loc_1800BAAF7
0x1800baaed  mov     edx, 425h
0x1800baaf2  jmp     loc_1800BAB9E
0x1800baaf7  mov     rdx, r15; unsigned __int16 *
0x1800baafa  mov     rcx, rdi; this
0x1800baafd  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800bab02  test    al, al
0x1800bab04  jz      short loc_1800BAB47
0x1800bab06  mov     rcx, [rsp+4F0h+lpExeName]
0x1800bab0b  mov     rax, [rcx]
0x1800bab0e  lea     rdx, [rsp+4F0h+var_4A0]
0x1800bab13  mov     rax, [rax+28h]
0x1800bab17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab1c  mov     byte ptr [rsp+4F0h+var_4C0], r12b
0x1800bab21  mov     ecx, dword ptr [rsp+4F0h+var_4A0]
0x1800bab25  mov     dword ptr [rsp+4F0h+pdwReturnedProductType], ecx
0x1800bab29  mov     r9d, eax
0x1800bab2c  mov     r8, r15
0x1800bab2f  mov     rdx, rsi
0x1800bab32  mov     rcx, rdi
0x1800bab35  call    ?UpdateParamsWithBooleanBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJH1_N@Z; FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,int,ushort const *,bool)
0x1800bab3a  mov     ebx, eax
0x1800bab3c  test    eax, eax
0x1800bab3e  jns     short loc_1800BAB47
0x1800bab40  mov     edx, 42Bh
0x1800bab45  jmp     short loc_1800BAB9E
0x1800bab47  mov     rdx, r13; unsigned __int16 *
0x1800bab4a  mov     rcx, rdi; this
0x1800bab4d  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800bab52  test    al, al
0x1800bab54  jz      loc_1800BABE4
0x1800bab5a  mov     [rsp+4F0h+dwSize], r12d
0x1800bab5f  mov     rcx, [rsp+4F0h+lpExeName]
0x1800bab64  mov     rax, [rcx]
0x1800bab67  lea     rdx, [rsp+4F0h+dwSize]
0x1800bab6c  mov     rax, [rax+18h]
0x1800bab70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab75  mov     [rsp+4F0h+var_4C8], r12b
0x1800bab7a  mov     ecx, [rsp+4F0h+dwSize]
0x1800bab7e  mov     dword ptr [rsp+4F0h+pdwReturnedProductType], ecx; int
0x1800bab82  mov     r9d, eax
0x1800bab85  mov     r8, r13
0x1800bab88  mov     rdx, rsi
0x1800bab8b  mov     rcx, rdi
0x1800bab8e  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800bab93  mov     ebx, eax
0x1800bab95  test    eax, eax
0x1800bab97  jns     short loc_1800BABE4
0x1800bab99  mov     edx, 432h; void *
0x1800bab9e  mov     r9d, eax; char *
0x1800baba1  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800baba8  mov     rcx, [rbp+3F8h]; this
0x1800babaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800babb4  nop
0x1800babb5  lea     rcx, [rsp+4F0h+lpExeName]
0x1800babba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800babbf  jmp     loc_1800BB0ED
0x1800babc4  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800babc9  test    al, al
0x1800babcb  jz      short loc_1800BABE4
0x1800babcd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800babd4  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800babd9  mov     edx, ebx; int
0x1800babdb  mov     rcx, rax; this
0x1800babde  call    ?AddNetworkingSpecificPropertiesFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::AddNetworkingSpecificPropertiesFailed_(long)
0x1800babe3  nop
0x1800babe4  lea     rcx, [rsp+4F0h+lpExeName]
0x1800babe9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800babee  mov     r13, 0FFFFFFFF80000002h
0x1800babf5  mov     [rsp+4F0h+lpExeName], r13
0x1800babfa  mov     [rsp+4F0h+var_4B8], r12
0x1800babff  lea     rax, [rsp+4F0h+lpExeName]
0x1800bac04  mov     [rsp+4F0h+var_4C0], rax
0x1800bac09  lea     rax, aMachineid; "MachineId"
0x1800bac10  mov     [rsp+4F0h+pdwReturnedProductType], rax
0x1800bac15  lea     r9, aSoftwareMicros_15; "Software\\Microsoft\\SqmClient"
0x1800bac1c  lea     r8, aSqmmachineid; "sqmMachineId"
0x1800bac23  mov     rdx, rsi
0x1800bac26  call    ?AddStringRegKeyToParams@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBG111AEBQEAUHKEY__@@1@Z; FSPropertyBag::AddStringRegKeyToParams(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,ushort const *,ushort const *,ushort const *,HKEY__ * const &,ushort const *)
0x1800bac2b  mov     ebx, eax
0x1800bac2d  test    eax, eax
0x1800bac2f  jns     short loc_1800BAC3B
0x1800bac31  mov     edx, 43Dh
0x1800bac36  jmp     loc_1800BA82D
0x1800bac3b  mov     [rbp+3F0h+var_470], r12d
0x1800bac3f  lea     rax, [rbp+3F0h+var_470]
  ... truncated ...
```
