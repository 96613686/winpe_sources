# ConfigProvider::Create(CRequestContext *,_WSMAN_PLUGIN_REQUEST *,ulong,ushort const *,ulong,void *,TSTRBUFFER *)

- ea: `0x1801a94cc`
- end: `0x1801aa192`
- name: `?Create@ConfigProvider@@QEAA_NPEAVCRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@KPEBGKPEAXPEAVTSTRBUFFER@@@Z`
- size: `3270`
- prototype: `char __fastcall(ConfigProvider *this, struct CRequestContext *, struct _WSMAN_PLUGIN_REQUEST *, int, const unsigned __int16 *, unsigned int, unsigned int *, struct TSTRBUFFER *)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18010b140`
- `0x1801ae400`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x180031350`
- `0x180033dd0`
- `0x180034850`
- `0x180035ee0`
- `0x180035f80`
- `0x18005eba0`
- `0x1800621e0`
- `0x180077490`
- `0x1800a901c`
- `0x1800ce6a0`
- `0x180110190`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x1801133b0`
- `0x18011a6d4`
- `0x18011d8c0`
- `0x1801902b0`
- `0x1801930d0`
- `0x1801a94cc`
- `0x1801aa60c`
- `0x1801ab600`
- `0x1801abbec`
- `0x1801ac6d0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_scwprintf` at `0x1801a981a`
- `msvcrt!_scwprintf` at `0x1801a9ca4`
- `msvcrt!_scwprintf` at `0x1801a9e75`
- `msvcrt!_scwprintf` at `0x1801a9fac`
- `msvcrt!_scwprintf` at `0x1801a981a`
- `msvcrt!_scwprintf` at `0x1801a9ca4`
- `msvcrt!_scwprintf` at `0x1801a9e75`
- `msvcrt!_scwprintf` at `0x1801a9fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a978c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a978c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9a42`

## string_xrefs

- `0x1801a95e7`: `http://schemas.microsoft.com/wbem/wsman/1/config/listener`
- `0x1801a96d0`: `http://schemas.microsoft.com/wbem/wsman/1/config/listener`
- `0x1801a9633`: `Create`
- `0x1801a9519`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x1801a98ab`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x1801a9d3e`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x1801a9ef4`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x1801aa03c`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x1801a9620`: `http://schemas.microsoft.com/wbem/wsman/1/config/plugin`
- `0x1801a9f48`: `http://schemas.microsoft.com/wbem/wsman/1/config/plugin`
- `0x1801a97bf`: `CConfigManager::GetSetting`
- `0x1801a9a75`: `CConfigManager::GetSetting`
- `0x1801a95fa`: `http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping`
- `0x1801a992d`: `http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping`
- `0x1801a960d`: `http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell`
- `0x1801a9e11`: `http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell`
- `0x1801a9813`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/listener</w:ResourceURI><w:SelectorSet><w:Selector Name="Address">%s</w:Selector><w:Selector Name="Transport">%s</w:Selector></w:Se`
- `0x1801a987d`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/listener</w:ResourceURI><w:SelectorSet><w:Selector Name="Address">%s</w:Selector><w:Selector Name="Transport">%s</w:Selector></w:Se`
- `0x1801a9c9d`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping</w:ResourceURI><w:SelectorSet><w:Selector Name="URI">%s</w:Selector><w:Selector Name="Subject">%s</w:Selector><`
- `0x1801a9d0f`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping</w:ResourceURI><w:SelectorSet><w:Selector Name="URI">%s</w:Selector><w:Selector Name="Subject">%s</w:Selector><`
- `0x1801a9e6e`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell</w:ResourceURI><w:SelectorSet><w:Selector Name="uri">%s</w:Selector></w:SelectorSet></a:ReferenceParameters`
- `0x1801a9ec3`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell</w:ResourceURI><w:SelectorSet><w:Selector Name="uri">%s</w:Selector></w:SelectorSet></a:ReferenceParameters`
- `0x1801a9fa5`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/plugin</w:ResourceURI><w:SelectorSet><w:Selector Name="name">%s</w:Selector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceC`
- `0x1801aa00a`: `<wxf:ResourceCreated xmlns:wxf="http://schemas.xmlsoap.org/ws/2004/09/transfer" xmlns:a="http://schemas.xmlsoap.org/ws/2004/08/addressing" xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/plugin</w:ResourceURI><w:SelectorSet><w:Selector Name="name">%s</w:Selector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceC`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall ConfigProvider::Create(
        ConfigProvider *this,
        struct CRequestContext *a2,
        struct _WSMAN_PLUGIN_REQUEST *a3,
        int a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int *a7,
        struct TSTRBUFFER *a8)
{
  ConfigProvider *v10; // r13
  struct ConfigUpdate *v11; // r14
  const unsigned __int16 *v12; // r8
  unsigned int v13; // edx
  PVOID *v15; // rcx
  unsigned __int16 *resourceUri; // rsi
  int v17; // eax
  bool v18; // bl
  struct ConfigUpdate *v19; // rax
  char v20; // r12
  unsigned __int16 *v21; // rbx
  unsigned int *v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rdi
  DWORD LastError; // eax
  __int64 v26; // r10
  unsigned __int64 v27; // rax
  __int64 v28; // rax
  PVOID *v29; // rcx
  struct TSTRBUFFER *v30; // rbx
  void **v31; // rcx
  const unsigned __int16 *v32; // rsi
  const unsigned __int16 *v33; // rbx
  __int64 v34; // rax
  const unsigned __int16 *v35; // rdi
  DWORD v36; // eax
  __int64 v37; // r10
  RBUFFER *v38; // rax
  RBUFFER *v39; // r13
  RBUFFER *v40; // rax
  void **v41; // rbx
  __int64 v42; // r13
  unsigned int *v43; // rax
  unsigned int *v44; // rbx
  __int64 v45; // rdi
  unsigned __int64 v46; // rsi
  unsigned __int64 v47; // rax
  __int64 v48; // rax
  int v49; // edi
  struct TSTRBUFFER *v50; // rbx
  unsigned __int64 v51; // rsi
  __int64 v52; // rax
  __int64 v53; // rax
  int v54; // edi
  unsigned __int64 v55; // rsi
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // edi
  struct TSTRBUFFER *v59; // r14
  unsigned __int16 *Src; // [rsp+48h] [rbp-49h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-41h] BYREF
  __int64 v62; // [rsp+58h] [rbp-39h] BYREF
  const unsigned __int16 *v63; // [rsp+60h] [rbp-31h] BYREF
  const unsigned __int16 *v64; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int64 v65; // [rsp+70h] [rbp-21h]
  RBUFFER *v66; // [rsp+78h] [rbp-19h] BYREF
  void **v67; // [rsp+80h] [rbp-11h] BYREF
  unsigned __int16 *v68; // [rsp+88h] [rbp-9h]
  unsigned int *v69; // [rsp+90h] [rbp-1h]
  ConfigProvider *v70; // [rsp+D8h] [rbp+47h] BYREF
  int v71; // [rsp+F0h] [rbp+5Fh] BYREF

  v71 = a4;
  v70 = this;
  v10 = this;
  v11 = 0;
  if ( !*(_DWORD *)this )
  {
    v12 = L"1095";
    v13 = 1095;
LABEL_3:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp", v13, v12, 0x54Fu, 0);
    return 0;
  }
  if ( !a3 )
  {
    v12 = L"1096";
    v13 = 1096;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v12 = L"1097";
    v13 = 1097;
    goto LABEL_3;
  }
  if ( !a8 )
  {
    v12 = L"1098";
    v13 = 1098;
    goto LABEL_3;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, v10);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x200000) != 0 )
      WPP_SF_Sd(
        (unsigned int)v15[2],
        21,
        (unsigned int)&WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
        a3->resourceUri,
        a3->operationInfo->selectorSet.numberKeys);
  }
  *((_DWORD *)v10 + 4) = 3;
  resourceUri = (unsigned __int16 *)a3->resourceUri;
  v68 = resourceUri;
  if ( !(unsigned int)StringCchEqualsCI(
                        (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/listener",
                        resourceUri)
    && !(unsigned int)StringCchEqualsCI(
                        (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping",
                        resourceUri)
    && !(unsigned int)StringCchEqualsCI(
                        (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell",
                        resourceUri)
    && !(unsigned int)StringCchEqualsCI(
                        (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/plugin",
                        resourceUri) )
  {
    (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
      a2,
      2150858801LL,
      1077134173,
      L"Create");
    return 0;
  }
  if ( !(unsigned int)ConfigProvider::ValidateUri(v10, a2, a3, 0) )
    return 0;
  v17 = ConfigProvider::SetConfigManagerForTables(v10, a2, a3);
  v18 = v17 == 1;
  lpSubKey = 0;
  if ( v17 == 1 )
  {
    v19 = ConfigProvider::InitializeUpdates(v10, a2, a3, 1);
    AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::operator=(&lpSubKey, v19);
    v11 = (struct ConfigUpdate *)lpSubKey;
    v20 = lpSubKey != 0 && v18;
  }
  else
  {
    v20 = 0;
  }
  v21 = 0;
  Src = 0;
  if ( !v20 )
    goto LABEL_128;
  if ( (unsigned int)StringCchEqualsCI(
                       (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/listener",
                       resourceUri) )
  {
    v22 = (unsigned int *)WSManMemory::Alloc(20480, 0, 0);
    a7 = v22;
    v23 = WSManMemory::Alloc(20480, 0, 0);
    v24 = v23;
    v70 = (ConfigProvider *)v23;
    if ( v22 && v23 )
    {
      v71 = 0;
      if ( (unsigned int)CConfigManager::GetSetting(*((_QWORD *)v10 + 1), a2, 3000, 10240, v22, &v71, 0) == 1
        && (unsigned int)CConfigManager::GetSetting(*((_QWORD *)v10 + 1), a2, 3001, 10240, v24, &v71, 0) == 1 )
      {
        v20 = 1;
      }
      else
      {
        v20 = 0;
        LastError = GetLastError();
        v26 = *(_QWORD *)a2;
        if ( LastError == 5 )
        {
          (*(void (__fastcall **)(struct CRequestContext *))(v26 + 32))(a2);
        }
        else if ( LastError == -2144108539 )
        {
          (*(void (__fastcall **)(struct CRequestContext *))(v26 + 72))(a2);
        }
        else
        {
          (*(void (__fastcall **)(struct CRequestContext *, __int64, const wchar_t *, _QWORD))(v26 + 88))(
            a2,
            1077134176,
            L"CConfigManager::GetSetting",
            LastError);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
          (_DWORD)v22,
          v24);
      v65 = (unsigned int)(_scwprintf(
                             L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\""
                              "http://schemas.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/"
                              "wsman/1/wsman.xsd\"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anony"
                              "mous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/ws"
                              "man/1/config/listener</w:ResourceURI><w:SelectorSet><w:Selector Name=\"Address\">%s</w:Sel"
                              "ector><w:Selector Name=\"Transport\">%s</w:Selector></w:SelectorSet></a:ReferenceParameter"
                              "s></wxf:ResourceCreated>",
                             v22,
                             v24)
                         + 1);
      v27 = 2 * v65;
      if ( !is_mul_ok(v65, 2u) )
        v27 = -1;
      v28 = WSManMemory::Alloc(v27, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&Src, v28);
      v21 = Src;
      if ( Src )
      {
        if ( v20
          && (int)StringCchPrintfW(
                    Src,
                    v65,
                    L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\"http://s"
                     "chemas.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd"
                     "\"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:Referen"
                     "ceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/listener</w:ResourceUR"
                     "I><w:SelectorSet><w:Selector Name=\"Address\">%s</w:Selector><w:Selector Name=\"Transport\">%s</w:S"
                     "elector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                    v22,
                    v24) < 0 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
            0x4ADu,
            L"1197",
            0x54Fu,
            a2);
          v20 = 0;
        }
      }
      else
      {
        v20 = 0;
        (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
      }
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v70);
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&a7);
      v29 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_113;
    }
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v30 = a8;
    SBUFFER::SetSizeInUse(a8, 0);
    **(_WORD **)v30 = 0;
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v70);
    v31 = (void **)&a7;
LABEL_50:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(v31);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&Src);
    AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(&lpSubKey);
    return 0;
  }
  if ( !(unsigned int)StringCchEqualsCI(
                        (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping",
                        resourceUri) )
  {
    if ( (unsigned int)StringCchEqualsCI(
                         (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell",
                         resourceUri) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
          a3->operationInfo->selectorSet.keys->value);
      v51 = (unsigned int)(_scwprintf(
                             L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\""
                              "http://schemas.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/"
                              "wsman/1/wsman.xsd\"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anony"
                              "mous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/ws"
                              "man/1/config/winrs/customremoteshell</w:ResourceURI><w:SelectorSet><w:Selector Name=\"uri\""
                              ">%s</w:Selector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                             a3->operationInfo->selectorSet.keys->value)
                         + 1);
      v52 = 2 * v51;
      if ( !is_mul_ok(v51, 2u) )
        v52 = -1;
      v53 = WSManMemory::Alloc(v52, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&Src, v53);
      v21 = Src;
      if ( Src )
      {
        v54 = StringCchPrintfW(
                Src,
                (unsigned int)v51,
                L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\"http://schem"
                 "as.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd\"><a:Ad"
                 "dress>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters"
                 "><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell</w:ResourceURI"
                 "><w:SelectorSet><w:Selector Name=\"uri\">%s</w:Selector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                a3->operationInfo->selectorSet.keys->value);
        if ( v54 < 0 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
            0x53Du,
            L"1341",
            0x54Fu,
            a2);
          v29 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
              (unsigned int)v54);
            v29 = (PVOID *)WPP_GLOBAL_Control;
          }
          v20 = 0;
LABEL_113:
          if ( v20 )
            goto LABEL_131;
LABEL_128:
          v59 = a8;
          SBUFFER::SetSizeInUse(a8, 0);
          **(_WORD **)v59 = 0;
          goto LABEL_129;
        }
LABEL_130:
        v29 = (PVOID *)WPP_GLOBAL_Control;
LABEL_131:
        if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x200000) != 0 )
          WPP_SF_S(v29[2], 29, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, v21);
        if ( (int)TSTRBUFFER::Copy(a8, v21) >= 0 )
        {
          if ( (unsigned int)ConfigProvider::PutConfig(v10, a2, v11, v68, a5, 1) == 1
            && (unsigned int)ConfigUpdate::MakeChanges((unsigned int *)v11, a2) == 1 )
          {
            v20 = 1;
            goto LABEL_129;
          }
        }
        else
        {
          (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids);
        }
        goto LABEL_127;
      }
    }
    else
    {
      if ( !(unsigned int)StringCchEqualsCI(
                            (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/plugin",
                            resourceUri) )
        goto LABEL_130;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
          a3->operationInfo->selectorSet.keys->value);
      v55 = (unsigned int)(_scwprintf(
                             L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\""
                              "http://schemas.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/"
                              "wsman/1/wsman.xsd\"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anony"
                              "mous</a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/ws"
                              "man/1/config/plugin</w:ResourceURI><w:SelectorSet><w:Selector Name=\"name\">%s</w:Selector"
                              "></w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                             a3->operationInfo->selectorSet.keys->value)
                         + 1);
      v56 = 2 * v55;
      if ( !is_mul_ok(v55, 2u) )
        v56 = -1;
      v57 = WSManMemory::Alloc(v56, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&Src, v57);
      v21 = Src;
      if ( Src )
      {
        v58 = StringCchPrintfW(
                Src,
                v55,
                L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\"http://schem"
                 "as.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd\"><a:Ad"
                 "dress>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters"
                 "><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/plugin</w:ResourceURI><w:SelectorSet><"
                 "w:Selector Name=\"name\">%s</w:Selector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                a3->operationInfo->selectorSet.keys->value);
        if ( v58 < 0 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
            0x553u,
            L"1363",
            0x54Fu,
            a2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
              (unsigned int)v58);
LABEL_127:
          v20 = 0;
          goto LABEL_128;
        }
        goto LABEL_130;
      }
    }
    v20 = 0;
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    goto LABEL_128;
  }
  v32 = (const unsigned __int16 *)WSManMemory::Alloc(20480, 0, 0);
  v64 = v32;
  v33 = (const unsigned __int16 *)WSManMemory::Alloc(20480, 0, 0);
  v63 = v33;
  v34 = WSManMemory::Alloc(20480, 0, 0);
  v35 = (const unsigned __int16 *)v34;
  v62 = v34;
  if ( !v32 || !v33 || !v34 )
  {
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v50 = a8;
    SBUFFER::SetSizeInUse(a8, 0);
    **(_WORD **)v50 = 0;
    goto LABEL_100;
  }
  v71 = 0;
  if ( (unsigned int)CConfigManager::GetSetting(*((_QWORD *)v10 + 1), a2, 6000, 10240, v32, &v71, 0) == 1
    && (unsigned int)CConfigManager::GetSetting(*((_QWORD *)v10 + 1), a2, 6001, 10240, v33, &v71, 0) == 1
    && (unsigned int)CConfigManager::GetSetting(*((_QWORD *)v10 + 1), a2, 6002, 10240, v35, &v71, 0) == 1 )
  {
    v20 = 1;
  }
  else
  {
    v20 = 0;
    v36 = GetLastError();
    v37 = *(_QWORD *)a2;
    if ( v36 == 5 )
    {
      (*(void (__fastcall **)(struct CRequestContext *))(v37 + 32))(a2);
    }
    else if ( v36 == -2144108539 )
    {
      (*(void (__fastcall **)(struct CRequestContext *))(v37 + 72))(a2);
    }
    else
    {
      (*(void (__fastcall **)(struct CRequestContext *, __int64, const wchar_t *, _QWORD))(v37 + 88))(
        a2,
        1077134176,
        L"CConfigManager::GetSetting",
        v36);
    }
  }
  a6 = 0;
  a7 = &a6;
  v38 = (RBUFFER *)WSManMemory::Alloc(2592, 0, 0);
  v39 = v38;
  v65 = (unsigned __int64)v38;
  if ( v38 )
  {
    RBUFFER::RBUFFER(v38, 0);
    *((_DWORD *)v39 + 646) = 0;
  }
  else
  {
    v39 = 0;
  }
  v66 = v39;
  if ( !v39 || (int)TSTRBUFFER::AppendEscapeXmlContent(v39, v33, 0) < 0 )
  {
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
LABEL_69:
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v66);
LABEL_100:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v62);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v63);
    v31 = (void **)&v64;
    goto LABEL_50;
  }
  v65 = *(_QWORD *)v39;
  LODWORD(a7) = 0;
  v67 = (void **)&a7;
  v40 = (RBUFFER *)WSManMemory::Alloc(2592, 0, 0);
  v41 = (void **)v40;
  v69 = (unsigned int *)v40;
  if ( v40 )
  {
    RBUFFER::RBUFFER(v40, 0);
    *((_DWORD *)v41 + 646) = 0;
  }
  else
  {
    v41 = 0;
  }
  v67 = v41;
  if ( !v41 || (int)TSTRBUFFER::AppendEscapeXmlContent((TSTRBUFFER *)v41, v35, 0) < 0 )
  {
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
LABEL_76:
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v67);
    goto LABEL_69;
  }
  v42 = (__int64)*v41;
  a6 = 0;
  v69 = &a6;
  v43 = (unsigned int *)WSManMemory::Alloc(2592, 0, 0);
  v44 = v43;
  a7 = v43;
  if ( v43 )
  {
    RBUFFER::RBUFFER((RBUFFER *)v43, 0);
    v44[646] = 0;
  }
  else
  {
    v44 = 0;
  }
  a7 = v44;
  if ( !v44 )
  {
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
    goto LABEL_76;
  }
  if ( (int)TSTRBUFFER::AppendEscapeXmlContent((TSTRBUFFER *)v44, v32, 0) >= 0 )
  {
    v45 = *(_QWORD *)v44;
    v46 = v65;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v65, v42);
    v65 = (unsigned int)(_scwprintf(
                           L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\"h"
                            "ttp://schemas.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/wsm"
                            "an/1/wsman.xsd\"><a:Address>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous<"
                            "/a:Address><a:ReferenceParameters><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/c"
                            "onfig/service/certmapping</w:ResourceURI><w:SelectorSet><w:Selector Name=\"URI\">%s</w:Selec"
                            "tor><w:Selector Name=\"Subject\">%s</w:Selector><w:Selector Name=\"Issuer\">%s</w:Selector><"
                            "/w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                           v45,
                           v46,
                           v42)
                       + 1);
    v47 = 2 * v65;
    if ( !is_mul_ok(v65, 2u) )
      v47 = -1;
    v48 = WSManMemory::Alloc(v47, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&Src, v48);
    v21 = Src;
    if ( Src )
    {
      if ( v20 )
      {
        v49 = StringCchPrintfW(
                Src,
                v65,
                L"<wxf:ResourceCreated xmlns:wxf=\"http://schemas.xmlsoap.org/ws/2004/09/transfer\" xmlns:a=\"http://schem"
                 "as.xmlsoap.org/ws/2004/08/addressing\" xmlns:w=\"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd\"><a:Ad"
                 "dress>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address><a:ReferenceParameters"
                 "><w:ResourceURI>http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping</w:ResourceURI><w:"
                 "SelectorSet><w:Selector Name=\"URI\">%s</w:Selector><w:Selector Name=\"Subject\">%s</w:Selector><w:Sele"
                 "ctor Name=\"Issuer\">%s</w:Selector></w:SelectorSet></a:ReferenceParameters></wxf:ResourceCreated>",
                v45,
                v46,
                v42);
        if ( v49 < 0 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
            0x527u,
            L"1319",
            0x54Fu,
            a2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids,
              (unsigned int)v49);
          v20 = 0;
        }
      }
    }
    else
    {
      v20 = 0;
      (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    }
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v67);
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v66);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v62);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v63);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
    v29 = (PVOID *)WPP_GLOBAL_Control;
    v10 = v70;
    goto LABEL_113;
  }
  (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
  AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
  AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v67);
  AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v66);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v62);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v63);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
  v20 = 0;
LABEL_129:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&Src);
  AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(&lpSubKey);
  return v20;
}

```

## disassembly

```asm
0x1801a94cc  mov     rax, rsp
0x1801a94cf  mov     [rax+10h], rbx
0x1801a94d3  mov     [rax+20h], r9d
0x1801a94d7  mov     [rax+8], rcx
0x1801a94db  push    rbp
0x1801a94dc  push    rsi
0x1801a94dd  push    rdi
0x1801a94de  push    r12
0x1801a94e0  push    r13
0x1801a94e2  push    r14
0x1801a94e4  push    r15
0x1801a94e6  lea     rbp, [rax-3Fh]
0x1801a94ea  sub     rsp, 90h
0x1801a94f1  mov     rdi, r8
0x1801a94f4  mov     r15, rdx
0x1801a94f7  mov     r13, rcx
0x1801a94fa  xor     r14d, r14d
0x1801a94fd  cmp     [rcx], r14d
0x1801a9500  jnz     short loc_1801A952C
0x1801a9502  lea     r8, a1095; "1095"
0x1801a9509  mov     edx, 447h; unsigned int
0x1801a950e  mov     r9d, 54Fh; unsigned int
0x1801a9514  mov     [rsp+0C0h+var_A0], r14; struct IRequestContext *
0x1801a9519  lea     rcx, aOnecoreAdminWm_139; "onecore\\admin\\wmi\\wmx\\providers\\co"...
0x1801a9520  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a9525  xor     al, al
0x1801a9527  jmp     loc_1801AA0A4
0x1801a952c  test    rdi, rdi
0x1801a952f  jnz     short loc_1801A953F
0x1801a9531  lea     r8, a1096; "1096"
0x1801a9538  mov     edx, 448h
0x1801a953d  jmp     short loc_1801A950E
0x1801a953f  cmp     [rbp+37h+arg_20], r14
0x1801a9543  jnz     short loc_1801A9553
0x1801a9545  lea     r8, a1097; "1097"
0x1801a954c  mov     edx, 449h
0x1801a9551  jmp     short loc_1801A950E
0x1801a9553  cmp     [rbp+37h+arg_38], r14
0x1801a9557  jnz     short loc_1801A9567
0x1801a9559  lea     r8, a1098; "1098"
0x1801a9560  mov     edx, 44Ah
0x1801a9565  jmp     short loc_1801A950E
0x1801a9567  lea     rbx, WPP_GLOBAL_Control
0x1801a956e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9575  cmp     rcx, rbx
0x1801a9578  jz      short loc_1801A95D4
0x1801a957a  test    dword ptr [rcx+1Ch], 200000h
0x1801a9581  jz      short loc_1801A95A2
0x1801a9583  mov     edx, 14h
0x1801a9588  mov     r9, r13
0x1801a958b  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x1801a9592  mov     rcx, [rcx+10h]
0x1801a9596  call    WPP_SF_q
0x1801a959b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a95a2  cmp     rcx, rbx
0x1801a95a5  jz      short loc_1801A95D4
0x1801a95a7  test    dword ptr [rcx+1Ch], 200000h
0x1801a95ae  jz      short loc_1801A95D4
0x1801a95b0  mov     rax, [rdi+18h]
0x1801a95b4  mov     edx, 15h
0x1801a95b9  mov     eax, [rax+20h]
0x1801a95bc  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1801a95c0  mov     r9, [rdi+10h]
0x1801a95c4  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x1801a95cb  mov     rcx, [rcx+10h]
0x1801a95cf  call    WPP_SF_Sd
0x1801a95d4  mov     dword ptr [r13+10h], 3
0x1801a95dc  mov     rsi, [rdi+10h]
0x1801a95e0  mov     [rbp+37h+var_40], rsi
0x1801a95e4  mov     rdx, rsi; String2
0x1801a95e7  lea     rcx, aHttpSchemasMic_3; "http://schemas.microsoft.com/wbem/wsman"...
0x1801a95ee  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x1801a95f3  test    eax, eax
0x1801a95f5  jnz     short loc_1801A9656
0x1801a95f7  mov     rdx, rsi; String2
0x1801a95fa  lea     rcx, aHttpSchemasMic_45; "http://schemas.microsoft.com/wbem/wsman"...
0x1801a9601  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x1801a9606  test    eax, eax
0x1801a9608  jnz     short loc_1801A9656
0x1801a960a  mov     rdx, rsi; String2
0x1801a960d  lea     rcx, aHttpSchemasMic_7; "http://schemas.microsoft.com/wbem/wsman"...
0x1801a9614  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x1801a9619  test    eax, eax
0x1801a961b  jnz     short loc_1801A9656
0x1801a961d  mov     rdx, rsi; String2
0x1801a9620  lea     rcx, aHttpSchemasMic_29; "http://schemas.microsoft.com/wbem/wsman"...
0x1801a9627  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x1801a962c  test    eax, eax
0x1801a962e  jnz     short loc_1801A9656
0x1801a9630  mov     rax, [r15]
0x1801a9633  lea     r9, aCreate_0; "Create"
0x1801a963a  mov     edx, 80338031h
0x1801a963f  mov     r8d, 4033C35Dh
0x1801a9645  mov     rcx, r15
0x1801a9648  mov     rax, [rax+40h]
0x1801a964c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9651  jmp     loc_1801A9525
0x1801a9656  xor     r9d, r9d; int
0x1801a9659  mov     r8, rdi; struct _WSMAN_PLUGIN_REQUEST *
0x1801a965c  mov     rdx, r15; struct IRequestContext *
0x1801a965f  mov     rcx, r13; this
0x1801a9662  call    ?ValidateUri@ConfigProvider@@AEAAHPEAVIRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@H@Z; ConfigProvider::ValidateUri(IRequestContext *,_WSMAN_PLUGIN_REQUEST *,int)
0x1801a9667  test    eax, eax
0x1801a9669  jz      loc_1801A9525
0x1801a966f  mov     r8, rdi; struct _WSMAN_PLUGIN_REQUEST *
0x1801a9672  mov     rdx, r15; struct CRequestContext *
0x1801a9675  mov     rcx, r13; this
0x1801a9678  call    ?SetConfigManagerForTables@ConfigProvider@@AEAAHPEAVCRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@@Z; ConfigProvider::SetConfigManagerForTables(CRequestContext *,_WSMAN_PLUGIN_REQUEST *)
0x1801a967d  cmp     eax, 1
0x1801a9680  setz    bl
0x1801a9683  mov     [rbp+37h+lpSubKey], r14
0x1801a9687  jnz     short loc_1801A96BB
0x1801a9689  mov     r9d, 1; int
0x1801a968f  mov     r8, rdi; struct _WSMAN_PLUGIN_REQUEST *
0x1801a9692  mov     rdx, r15; struct CRequestContext *
0x1801a9695  mov     rcx, r13; this
0x1801a9698  call    ?InitializeUpdates@ConfigProvider@@AEAAPEAVConfigUpdate@@PEAVCRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@H@Z; ConfigProvider::InitializeUpdates(CRequestContext *,_WSMAN_PLUGIN_REQUEST *,int)
0x1801a969d  mov     rdx, rax
0x1801a96a0  lea     rcx, [rbp+37h+lpSubKey]
0x1801a96a4  call    ??4?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@QEAAAEAV?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@Z; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::operator=(ConfigUpdate *)
0x1801a96a9  mov     r14, [rbp+37h+lpSubKey]
0x1801a96ad  mov     rax, r14
0x1801a96b0  neg     rax
0x1801a96b3  sbb     r12b, r12b
0x1801a96b6  and     r12b, bl
0x1801a96b9  jmp     short loc_1801A96BE
0x1801a96bb  mov     r12b, bl
0x1801a96be  xor     ebx, ebx
0x1801a96c0  mov     [rbp+37h+Src], rbx
0x1801a96c4  test    r12b, r12b
0x1801a96c7  jz      loc_1801AA078
0x1801a96cd  mov     rdx, rsi; String2
0x1801a96d0  lea     rcx, aHttpSchemasMic_3; "http://schemas.microsoft.com/wbem/wsman"...
0x1801a96d7  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x1801a96dc  test    eax, eax
0x1801a96de  jz      loc_1801A992A
0x1801a96e4  xor     r8d, r8d
0x1801a96e7  xor     edx, edx
0x1801a96e9  mov     edi, 5000h
0x1801a96ee  mov     ecx, edi
0x1801a96f0  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801a96f5  mov     rsi, rax
0x1801a96f8  mov     [rbp+37h+arg_30], rax
0x1801a96fc  xor     r8d, r8d
0x1801a96ff  xor     edx, edx
0x1801a9701  mov     ecx, edi
0x1801a9703  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801a9708  mov     rdi, rax
0x1801a970b  mov     [rbp+37h+arg_0], rax
0x1801a970f  test    rsi, rsi
0x1801a9712  jz      loc_1801A98D9
0x1801a9718  test    rax, rax
0x1801a971b  jz      loc_1801A98D9
0x1801a9721  mov     [rbp+37h+arg_18], ebx
0x1801a9724  mov     [rsp+30h], rbx
0x1801a9729  lea     rax, [rbp+37h+arg_18]
0x1801a972d  mov     [rsp+0C0h+var_98], rax
0x1801a9732  mov     [rsp+0C0h+var_A0], rsi
0x1801a9737  mov     r12d, 2800h
0x1801a973d  mov     r9d, r12d
0x1801a9740  mov     r8d, 0BB8h
0x1801a9746  mov     rdx, r15
0x1801a9749  mov     rcx, [r13+8]
0x1801a974d  call    ?GetSetting@CConfigManager@@QEAAHPEAVIRequestContext@@W4ConfigSetting@@KPEAGPEAKPEAW4WSManConfigSource@@@Z; CConfigManager::GetSetting(IRequestContext *,ConfigSetting,ulong,ushort *,ulong *,WSManConfigSource *)
0x1801a9752  cmp     eax, 1
0x1801a9755  jnz     short loc_1801A9789
0x1801a9757  mov     [rsp+30h], rbx
0x1801a975c  lea     rax, [rbp+37h+arg_18]
0x1801a9760  mov     [rsp+0C0h+var_98], rax
0x1801a9765  mov     [rsp+0C0h+var_A0], rdi
0x1801a976a  mov     r9d, r12d
0x1801a976d  mov     r8d, 0BB9h
0x1801a9773  mov     rdx, r15
0x1801a9776  mov     rcx, [r13+8]
0x1801a977a  call    ?GetSetting@CConfigManager@@QEAAHPEAVIRequestContext@@W4ConfigSetting@@KPEAGPEAKPEAW4WSManConfigSource@@@Z; CConfigManager::GetSetting(IRequestContext *,ConfigSetting,ulong,ushort *,ulong *,WSManConfigSource *)
0x1801a977f  cmp     eax, 1
0x1801a9782  jnz     short loc_1801A9789
0x1801a9784  mov     r12b, al
0x1801a9787  jmp     short loc_1801A97D4
0x1801a9789  xor     r12b, r12b
0x1801a978c  call    cs:__imp_GetLastError
0x1801a9792  mov     r10, [r15]
0x1801a9795  mov     rcx, r15
0x1801a9798  cmp     eax, 5
0x1801a979b  jnz     short loc_1801A97A8
0x1801a979d  mov     rax, [r10+20h]
0x1801a97a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a97a6  jmp     short loc_1801A97D4
0x1801a97a8  mov     edx, 80338005h
0x1801a97ad  cmp     eax, edx
0x1801a97af  jnz     short loc_1801A97BC
0x1801a97b1  mov     rax, [r10+48h]
0x1801a97b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a97ba  jmp     short loc_1801A97D4
0x1801a97bc  mov     r9d, eax
0x1801a97bf  lea     r8, aCconfigmanager; "CConfigManager::GetSetting"
0x1801a97c6  mov     edx, 4033C360h
0x1801a97cb  mov     rax, [r10+58h]
0x1801a97cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a97d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a97db  lea     rax, WPP_GLOBAL_Control
0x1801a97e2  cmp     rcx, rax
0x1801a97e5  jz      short loc_1801A980D
0x1801a97e7  test    dword ptr [rcx+1Ch], 200000h
0x1801a97ee  jz      short loc_1801A980D
0x1801a97f0  mov     edx, 16h
0x1801a97f5  mov     [rsp+0C0h+var_A0], rdi
0x1801a97fa  mov     r9, rsi
0x1801a97fd  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x1801a9804  mov     rcx, [rcx+10h]
0x1801a9808  call    WPP_SF_SS
0x1801a980d  mov     r8, rdi
0x1801a9810  mov     rdx, rsi
0x1801a9813  lea     rcx, aWxfResourcecre_0; "<wxf:ResourceCreated xmlns:wxf=\"http:/"...
0x1801a981a  call    cs:__imp__scwprintf
0x1801a9820  lea     ecx, [rax+1]
0x1801a9823  mov     [rbp+37h+var_58], rcx
0x1801a9827  mov     eax, 2
0x1801a982c  mul     rcx
0x1801a982f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801a9836  cmovb   rax, rcx
0x1801a983a  xor     r8d, r8d
0x1801a983d  xor     edx, edx
0x1801a983f  mov     rcx, rax
0x1801a9842  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801a9847  mov     rdx, rax
0x1801a984a  lea     rcx, [rbp+37h+Src]
0x1801a984e  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1801a9853  mov     rbx, [rbp+37h+Src]
0x1801a9857  test    rbx, rbx
0x1801a985a  jnz     short loc_1801A9870
0x1801a985c  xor     r12b, r12b
0x1801a985f  mov     rax, [r15]
0x1801a9862  mov     rcx, r15
0x1801a9865  mov     rax, [rax+18h]
0x1801a9869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a986e  jmp     short loc_1801A98BA
0x1801a9870  test    r12b, r12b
0x1801a9873  jz      short loc_1801A98BA
0x1801a9875  mov     [rsp+0C0h+var_A0], rdi
0x1801a987a  mov     r9, rsi
0x1801a987d  lea     r8, aWxfResourcecre_0; "<wxf:ResourceCreated xmlns:wxf=\"http:/"...
0x1801a9884  mov     rdx, [rbp+37h+var_58]; unsigned __int64
0x1801a9888  mov     rcx, rbx; unsigned __int16 *
0x1801a988b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a9890  test    eax, eax
0x1801a9892  jns     short loc_1801A98BA
0x1801a9894  mov     [rsp+0C0h+var_A0], r15; struct IRequestContext *
0x1801a9899  mov     r9d, 54Fh; unsigned int
0x1801a989f  lea     r8, a1197; "1197"
0x1801a98a6  mov     edx, 4ADh; unsigned int
0x1801a98ab  lea     rcx, aOnecoreAdminWm_139; "onecore\\admin\\wmi\\wmx\\providers\\co"...
0x1801a98b2  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a98b7  xor     r12b, r12b
0x1801a98ba  lea     rcx, [rbp+37h+arg_0]
0x1801a98be  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801a98c3  nop
0x1801a98c4  lea     rcx, [rbp+37h+arg_30]
0x1801a98c8  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801a98cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a98d4  jmp     loc_1801A9F37
0x1801a98d9  mov     rax, [r15]
0x1801a98dc  mov     rcx, r15
0x1801a98df  mov     rax, [rax+18h]
0x1801a98e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a98e8  xor     edx, edx; unsigned int
0x1801a98ea  mov     rbx, [rbp+37h+arg_38]
0x1801a98ee  mov     rcx, rbx; this
0x1801a98f1  call    ?SetSizeInUse@SBUFFER@@QEAAXI@Z; SBUFFER::SetSizeInUse(uint)
0x1801a98f6  mov     rcx, [rbx]
0x1801a98f9  xor     eax, eax
0x1801a98fb  mov     [rcx], ax
0x1801a98fe  lea     rcx, [rbp+37h+arg_0]
0x1801a9902  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801a9907  nop
0x1801a9908  lea     rcx, [rbp+37h+arg_30]
0x1801a990c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801a9911  nop
0x1801a9912  lea     rcx, [rbp+37h+Src]
0x1801a9916  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801a991b  nop
0x1801a991c  lea     rcx, [rbp+37h+lpSubKey]
0x1801a9920  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VConfigUpdate@@@@PEAVConfigUpdate@@@@AEAAXXZ; AutoCleanup<AutoDelete<ConfigUpdate>,ConfigUpdate *>::ReleasePtr(void)
0x1801a9925  jmp     loc_1801A9525
0x1801a992a  mov     rdx, rsi; String2
0x1801a992d  lea     rcx, aHttpSchemasMic_45; "http://schemas.microsoft.com/wbem/wsman"...
0x1801a9934  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x1801a9939  test    eax, eax
0x1801a993b  jz      loc_1801A9E0E
0x1801a9941  xor     r8d, r8d
0x1801a9944  xor     edx, edx
0x1801a9946  mov     edi, 5000h
0x1801a994b  mov     ecx, edi
0x1801a994d  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801a9952  mov     rsi, rax
0x1801a9955  mov     [rbp+37h+var_60], rax
0x1801a9959  xor     r8d, r8d
0x1801a995c  xor     edx, edx
0x1801a995e  mov     ecx, edi
0x1801a9960  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
  ... truncated ...
```
