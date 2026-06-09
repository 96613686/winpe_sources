# ProvHostManager::CreateHost(InboundRequestDetails *,int,Catalog::Provider const *,int,ulong,CServiceConfigSettings *,ushort const *,int *,AutoReleaseEx<HostMappingTableEntry> &,AutoRelease<IWSManProvHost> &,CRequestContext *)

- ea: `0x18009a418`
- end: `0x18009b186`
- name: `?CreateHost@ProvHostManager@@AEAAHPEAVInboundRequestDetails@@HPEBVProvider@Catalog@@HKPEAVCServiceConfigSettings@@PEBGPEAHAEAV?$AutoReleaseEx@VHostMappingTableEntry@@@@AEAV?$AutoRelease@UIWSManProvHost@@@@PEAVCRequestContext@@@Z`
- size: `3438`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, int, int, __int64, unsigned __int16 *, _DWORD *, __int64, __int64, struct IRequestContext *)`
- caller_count: `2`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009977c`
- `0x180169b8c`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x180019950`
- `0x18002dd20`
- `0x1800567e0`
- `0x18005ee80`
- `0x1800621e0`
- `0x180063fa0`
- `0x180064250`
- `0x180068b24`
- `0x180071400`
- `0x180076d18`
- `0x18009a418`
- `0x18009b6a0`
- `0x18009b928`
- `0x18009bc00`
- `0x1800e8a50`
- `0x1800ea9b0`
- `0x1800f3d8c`
- `0x1800f5534`
- `0x1800f98f0`
- `0x1800f9960`
- `0x1800fe3b0`
- `0x1800fe7a0`
- `0x1800fe970`
- `0x1800ff510`
- `0x1800ffa10`
- `0x180112380`
- `0x1801123a8`
- `0x1801297b8`
- `0x18012d6f0`
- `0x18012d8f4`
- `0x180164cb4`
- `0x18016567c`
- `0x1801662a0`
- `0x180168fbc`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aa1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aa47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aa8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ab8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aa1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aa47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aa8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ab8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18009adea`
- `OLEAUT32!__imp_SysAllocString` at `0x18009adea`
- `OLEAUT32!__imp_SysStringLen` at `0x18009ae02`
- `OLEAUT32!__imp_SysStringLen` at `0x18009ae02`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18009af1a`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18009affc`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18009af1a`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18009affc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009aab8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009aab8`

## string_xrefs

- `0x18009a9e1`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`
- `0x18009ab5a`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`
- `0x18009b05c`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvHostManager::CreateHost(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        unsigned __int16 *a8,
        _DWORD *a9,
        __int64 a10,
        __int64 a11,
        struct IRequestContext *a12)
{
  OLECHAR *v15; // r10
  __int64 v16; // r9
  OLECHAR *v18; // rax
  HostMappingTableEntry *v19; // rsi
  int v20; // ebx
  int v21; // r13d
  const unsigned __int16 *v22; // r9
  BSTR v23; // rbx
  __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  GUID v28; // xmm0
  DWORD v29; // r15d
  DWORD LastError; // eax
  __int64 v31; // rdx
  void (__fastcall *v32)(struct IRequestContext *, _QWORD); // rbx
  DWORD v33; // eax
  HRESULT v34; // eax
  unsigned int v35; // r15d
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  HANDLE v39; // rcx
  DWORD v40; // eax
  int v41; // eax
  int v42; // eax
  __int64 v43; // r15
  unsigned __int16 *HostPluginXml; // rax
  _QWORD *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r9
  __int64 v48; // r9
  BSTR v49; // rax
  HostMappingTable *v50; // r12
  unsigned __int16 *v51; // rdx
  HANDLE v52; // rcx
  struct IWSManProvHost *v53; // rdx
  unsigned __int8 v54; // [rsp+60h] [rbp-A0h]
  BSTR pbstr; // [rsp+68h] [rbp-98h] BYREF
  struct IWSManProvHost *ppv; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  HostMappingTableEntry *v59; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-70h] BYREF
  int v61; // [rsp+98h] [rbp-68h]
  __int128 v62; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v63; // [rsp+B0h] [rbp-50h] BYREF
  int v64; // [rsp+B8h] [rbp-48h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  OLECHAR *psz; // [rsp+D8h] [rbp-28h]
  __int64 v69; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v70; // [rsp+E8h] [rbp-18h]
  _DWORD *v71; // [rsp+F0h] [rbp-10h]
  IID v72; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v73; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v74[2]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 v75[4]; // [rsp+120h] [rbp+20h] BYREF
  int v76; // [rsp+128h] [rbp+28h]
  wchar_t v77; // [rsp+12Ch] [rbp+2Ch]
  unsigned __int16 v78[37]; // [rsp+12Eh] [rbp+2Eh] BYREF
  __int128 v79; // [rsp+178h] [rbp+78h]
  __int128 v80; // [rsp+188h] [rbp+88h]
  __int128 v81; // [rsp+198h] [rbp+98h]
  __int128 v82; // [rsp+1A8h] [rbp+A8h]
  __int128 v83; // [rsp+1B8h] [rbp+B8h]
  __int64 v84; // [rsp+1C8h] [rbp+C8h]
  IID rclsid; // [rsp+1D0h] [rbp+D0h] BYREF

  v61 = a3;
  v69 = a1;
  v70 = a8;
  v67 = a7;
  v71 = a9;
  v65 = a10;
  v66 = a11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
  v63 = a1 + 112;
  v64 = 0;
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)(a1 + 112));
  v62 = 0;
  v15 = *(OLECHAR **)a4;
  psz = *(OLECHAR **)a4;
  if ( a5 )
  {
    if ( *(_BYTE *)(a4 + 224) )
    {
      v16 = 0;
      if ( a2 )
        v16 = *(_QWORD *)(a2 + 656);
      if ( (unsigned int)HostMappingTable::FindHostEntry(
                           a1 + 32,
                           v15,
                           a8,
                           v16,
                           *(unsigned __int8 *)(a4 + 240),
                           v65,
                           v66) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
        *a9 = 0;
        InCritSec::~InCritSec((InCritSec *)&v63);
        return 1;
      }
    }
  }
  else if ( (unsigned int)HostMappingTable::FindTableEntry(a1 + 32, a8, v65, v66) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    *a9 = 0;
    CWSManCriticalSection::Release((CWSManCriticalSection *)(a1 + 112));
    return 1;
  }
  v18 = (OLECHAR *)WSManMemory::Alloc(288, 0, 0);
  pbstr = v18;
  if ( v18 )
    v19 = HostMappingTableEntry::HostMappingTableEntry((HostMappingTableEntry *)v18);
  else
    v19 = 0;
  v59 = v19;
  if ( !v19 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a12 + 24LL))(a12);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, 14);
    AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&v59);
LABEL_27:
    InCritSec::~InCritSec((InCritSec *)&v63);
    return 0;
  }
  ppv = 0;
  v20 = *(unsigned __int8 *)(a4 + 224);
  v54 = *(_BYTE *)(a4 + 224);
  v21 = *(unsigned __int8 *)(a4 + 240);
  TokenHandle = 0;
  if ( !v21 )
    goto LABEL_64;
  if ( a2 )
    v22 = *(const unsigned __int16 **)(*(_QWORD *)(a2 + 656) + 8LL);
  else
    v22 = 0;
  if ( !Catalog::Provider::GetRunAsUserToken(
          (Catalog::Provider *)a4,
          a12,
          &TokenHandle,
          v22,
          (struct _RunAsContext *)&v62) )
  {
    if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a12 + 152LL))(a12) != -2144108037
      && (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a12 + 152LL))(a12) != -2144108036
      && (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a12 + 152LL))(a12) != -2144108035 )
    {
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a12 + 72LL))(a12, 2150859231LL);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&TokenHandle);
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
    AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&v59);
    goto LABEL_27;
  }
  if ( (_DWORD)v62 != 2 || !a2 )
  {
LABEL_64:
    v27 = v20;
    if ( !v21 )
      goto LABEL_67;
    goto LABEL_65;
  }
  pbstr = 0;
  v58 = 0;
  if ( !(unsigned int)CSecurity::ExtractSidFromToken(a12, TokenHandle, (struct AutoLocalFree *)&v58) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&v58);
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&pbstr);
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&TokenHandle);
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
    AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&v59);
    goto LABEL_27;
  }
  if ( (unsigned int)CSecurity::ExtractSidFromToken(
                       a12,
                       *(HANDLE *)(*(_QWORD *)(a2 + 656) + 32LL),
                       (struct AutoLocalFree *)&pbstr) )
  {
    v23 = pbstr;
    v24 = *(_QWORD *)(*(_QWORD *)(a2 + 656) + 8LL);
  }
  else
  {
    v25 = *(_QWORD *)(a2 + 32);
    if ( !v25 )
    {
LABEL_60:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
      AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&v58);
      AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&pbstr);
      AutoCleanup<AutoHandle,void *>::ReleasePtr(&TokenHandle);
      AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
      AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&v59);
      goto LABEL_27;
    }
    v23 = *(BSTR *)(v25 + 16);
    v24 = *(_QWORD *)(v25 + 24);
  }
  if ( !v23 || !v24 )
    goto LABEL_60;
  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_VIRTUAL_ACCOUNT_MAPPED) )
  {
    if ( *((_QWORD *)&v62 + 1) )
      v26 = **((_QWORD **)&v62 + 1);
    else
      v26 = 0;
    WSMan::LogEvent<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
      v26,
      v23,
      v24,
      v58,
      v26);
  }
  AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&v58);
  AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&pbstr);
  v27 = v54;
LABEL_65:
  if ( (_DWORD)v62 == 2 )
  {
LABEL_66:
    v28 = CLSID_WSManProvHost;
    goto LABEL_70;
  }
LABEL_67:
  if ( !v61 && !v27 )
    goto LABEL_66;
  v28 = CLSID_WSManProvHostWithUserSettings;
LABEL_70:
  rclsid = v28;
  v29 = 1114116;
  if ( *(_DWORD *)(a4 + 216) == 1 )
    v29 = 1376260;
  pbstr = 0;
  memset_0(v74, 0, 0xB8u);
  v73 = 0;
  v58 = 0;
  hObject = 0;
  if ( v21 )
  {
    if ( !TokenHandle )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 1521, L"1521", 0x54Fu, a12);
    if ( !(unsigned int)CSecurity::BeginRevertToSelf(&hObject, 0xCu) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_80;
      LastError = GetLastError();
      v31 = 109;
LABEL_79:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, LastError);
LABEL_80:
      v32 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a12 + 72LL);
      v33 = GetLastError();
      v32(a12, v33);
LABEL_144:
      v52 = hObject;
      if ( hObject )
      {
        if ( !v21 )
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 1709, L"1709", 0x54Fu, 0);
          v52 = hObject;
        }
        CSecurity::EndRevertToSelf(v52);
      }
      if ( v21 && (_DWORD)v62 )
        Catalog::Provider::FreeRunAsUserContext((struct _RunAsContext *)&v62);
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v58);
      AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&pbstr);
      AutoCleanup<AutoHandle,void *>::ReleasePtr(&TokenHandle);
      AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
      AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&v59);
      goto LABEL_27;
    }
    if ( !(unsigned int)CSecurity::ImpersonateUserOrSelf(695, TokenHandle) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_80;
      LastError = GetLastError();
      v31 = 110;
      goto LABEL_79;
    }
  }
  v34 = CoCreateInstance(&rclsid, 0, v29, &IID_IWSManProvHost, (LPVOID *)&ppv);
  v35 = v34;
  if ( v34 < 0 )
  {
    if ( (v34 & 0x1FFF0000) == 0x70000 )
      v35 = (unsigned __int16)v34;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD, __int64))(*(_QWORD *)a12 + 64LL))(a12, v35, 1077134554);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v37 = 111;
    goto LABEL_91;
  }
  if ( v21 )
  {
    v39 = hObject;
    if ( !hObject )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 1554, L"1554", 0x54Fu, a12);
      v39 = hObject;
    }
    if ( !(unsigned int)CSecurity::EndRevertToSelf(v39) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v40 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v40);
      }
      hObject = 0;
      goto LABEL_80;
    }
    hObject = 0;
  }
  v41 = WrapperCoSetProxyBlanket(ppv, 0xFFFFFFFFLL, 0xFFFFFFFFLL);
  v35 = v41;
  if ( v41 < 0 )
  {
    if ( (v41 & 0x1FFF0000) == 0x70000 )
      v35 = (unsigned __int16)v41;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a12 + 72LL))(a12, v35);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v37 = 113;
    goto LABEL_91;
  }
  v72 = rclsid;
  v42 = (*(__int64 (__fastcall **)(struct IWSManProvHost *, IID *, _QWORD))(*(_QWORD *)ppv + 24LL))(
          ppv,
          &v72,
          v61 | (unsigned int)v54);
  v35 = v42;
  if ( v42 < 0 )
  {
    if ( (v42 & 0x1FFF0000) == 0x70000 )
      v35 = (unsigned __int16)v42;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a12 + 72LL))(a12, v35);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v37 = 114;
    goto LABEL_91;
  }
  v43 = v69;
  HostPluginXml = Catalog::GetHostPluginXml(*(Catalog **)(v69 + 16), a12);
  v73 = HostPluginXml;
  if ( !HostPluginXml )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v46 = 115;
    goto LABEL_143;
  }
  AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&v58, HostPluginXml);
  LOBYTE(v47) = 1;
  v74[0] = Catalog::Provider::GetPluginQuota(a4, 6012, *(unsigned int *)(v67 + 376), v47, a12);
  LOBYTE(v48) = 1;
  v74[1] = Catalog::Provider::GetPluginQuota(a4, 6011, *(unsigned int *)(v67 + 380), v48, a12);
  *(_QWORD *)v75 = *(_QWORD *)L"Global\\";
  v76 = *(_DWORD *)L"al\\";
  v77 = aGlobal[6];
  WSManCreateUuidString(v78);
  v79 = *(_OWORD *)(v43 + 164);
  v80 = *(_OWORD *)(v43 + 180);
  v81 = *(_OWORD *)(v43 + 196);
  v82 = *(_OWORD *)(v43 + 212);
  v83 = *(_OWORD *)(v43 + 228);
  v84 = *(_QWORD *)(v43 + 244);
  v49 = SysAllocString(psz);
  AutoCleanup<AutoBstrNoAlloc,unsigned short *>::operator=(&pbstr, v49);
  if ( !SysStringLen(pbstr) )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a12 + 24LL))(a12);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v37 = 116;
    v38 = 14;
    goto LABEL_92;
  }
  v50 = (HostMappingTable *)(v43 + 32);
  if ( !HostMappingTableEntry::Initialize(
          v19,
          ppv,
          v70,
          psz,
          v54,
          v21,
          (struct _RunAsContext *)&v62,
          (struct HostMappingTable *)(v43 + 32),
          v75,
          a12,
          a5) )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v46 = 117;
    goto LABEL_143;
  }
  v62 = 0;
  v35 = (*(__int64 (__fastcall **)(struct IWSManProvHost *, unsigned __int16 **, HostMappingTableEntry *, BSTR, int, int, int, _DWORD))(*(_QWORD *)ppv + 32LL))(
          ppv,
          &v73,
          v19,
          pbstr,
          a6,
          a5,
          v21,
          v54);
  if ( (v35 & 0x80000000) != 0 )
  {
    CoDisconnectObject((LPUNKNOWN)v19, 0);
    if ( (v35 & 0x1FFF0000) == 0x70000 )
      v35 = (unsigned __int16)v35;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a12 + 72LL))(a12, v35);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v37 = 118;
LABEL_91:
    v38 = v35;
LABEL_92:
    WPP_SF_d(v36[2], v37, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v38);
    goto LABEL_144;
  }
  *((_DWORD *)v19 + 10) = 1;
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids,
        v69,
        v19,
        *(_QWORD *)(a2 + 656));
    HostMappingTableEntry::SetUserRecord(v19, *(struct UserRecord **)(a2 + 656), *(struct IRequestContext **)(a2 + 72));
  }
  v51 = 0;
  if ( !a5 )
    v51 = v70;
  if ( !HostMappingTable::AddTableEntry(v50, v51, v19, a12) )
  {
    CoDisconnectObject((LPUNKNOWN)v19, 0);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_144;
    v46 = 120;
LABEL_143:
    WPP_SF_(v45[2], v46, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    goto LABEL_144;
  }
  v59 = 0;
  AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::operator=(v65, v19);
  v53 = ppv;
  ppv = 0;
  AutoCleanup<AutoRelease<IWbemPath>,IWbemPath *>::operator=(v66, v53);
  *v71 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v58);
  AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&pbstr);
  AutoCleanup<AutoHandle,void *>::ReleasePtr(&TokenHandle);
  AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
  AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&v59);
  InCritSec::~InCritSec((InCritSec *)&v63);
  return 1;
}

```

## disassembly

```asm
0x18009a418  push    rbp
0x18009a41a  push    rbx
0x18009a41b  push    rsi
0x18009a41c  push    rdi
0x18009a41d  push    r12
0x18009a41f  push    r13
0x18009a421  push    r14
0x18009a423  push    r15
0x18009a425  lea     rbp, [rsp-0F8h]
0x18009a42d  sub     rsp, 1F8h
0x18009a434  mov     rax, cs:__security_cookie
0x18009a43b  xor     rax, rsp
0x18009a43e  mov     [rbp+130h+var_50], rax
0x18009a445  mov     r12, r9
0x18009a448  mov     [rbp+130h+var_198], r8d
0x18009a44c  mov     r14, rdx
0x18009a44f  mov     r15, rcx
0x18009a452  mov     [rbp+130h+var_150], rcx
0x18009a456  mov     rsi, [rbp+130h+arg_38]
0x18009a45d  mov     [rbp+130h+var_148], rsi
0x18009a461  mov     rax, [rbp+130h+arg_30]
0x18009a468  mov     [rbp+130h+var_160], rax
0x18009a46c  mov     r13, [rbp+130h+arg_40]
0x18009a473  mov     [rbp+130h+var_140], r13
0x18009a477  mov     rax, [rbp+130h+arg_48]
0x18009a47e  mov     [rbp+130h+var_170], rax
0x18009a482  mov     rax, [rbp+130h+arg_50]
0x18009a489  mov     [rbp+130h+var_168], rax
0x18009a48d  mov     rdi, [rbp+130h+arg_58]
0x18009a494  lea     rax, WPP_GLOBAL_Control
0x18009a49b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a4a2  cmp     rcx, rax
0x18009a4a5  jz      short loc_18009A4C5
0x18009a4a7  test    dword ptr [rcx+1Ch], 400h
0x18009a4ae  jz      short loc_18009A4C5
0x18009a4b0  mov     edx, 66h ; 'f'
0x18009a4b5  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a4bc  mov     rcx, [rcx+10h]
0x18009a4c0  call    WPP_SF_
0x18009a4c5  lea     rbx, [r15+70h]
0x18009a4c9  mov     [rbp+130h+var_180], rbx
0x18009a4cd  mov     [rbp+130h+var_178], 0
0x18009a4d4  mov     rcx, rbx; this
0x18009a4d7  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18009a4dc  nop
0x18009a4dd  xorps   xmm0, xmm0
0x18009a4e0  movups  [rbp+130h+var_190], xmm0
0x18009a4e4  mov     r10, [r12]
0x18009a4e8  mov     [rbp+130h+psz], r10
0x18009a4ec  cmp     [rbp+130h+arg_20], 0
0x18009a4f3  jz      loc_18009A599
0x18009a4f9  cmp     byte ptr [r12+0E0h], 0
0x18009a502  jz      loc_18009A5F4
0x18009a508  movzx   eax, byte ptr [r12+0F0h]
0x18009a511  xor     r9d, r9d
0x18009a514  test    r14, r14
0x18009a517  jz      short loc_18009A520
0x18009a519  mov     r9, [r14+290h]
0x18009a520  lea     rcx, [r15+20h]
0x18009a524  mov     rdx, [rbp+130h+var_168]
0x18009a528  mov     [rsp+230h+var_200], rdx
0x18009a52d  mov     r8, [rbp+130h+var_170]
0x18009a531  mov     qword ptr [rsp+230h+var_208], r8
0x18009a536  mov     dword ptr [rsp+230h+ppv], eax
0x18009a53a  mov     r8, rsi
0x18009a53d  mov     rdx, r10
0x18009a540  call    ?FindHostEntry@HostMappingTable@@QEAAHPEBG0PEBVUserRecord@@HAEAV?$AutoReleaseEx@VHostMappingTableEntry@@@@AEAV?$AutoRelease@UIWSManProvHost@@@@@Z; HostMappingTable::FindHostEntry(ushort const *,ushort const *,UserRecord const *,int,AutoReleaseEx<HostMappingTableEntry> &,AutoRelease<IWSManProvHost> &)
0x18009a545  test    eax, eax
0x18009a547  jz      loc_18009A5F4
0x18009a54d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a554  lea     rdx, WPP_GLOBAL_Control
0x18009a55b  cmp     rcx, rdx
0x18009a55e  jz      short loc_18009A57E
0x18009a560  test    dword ptr [rcx+1Ch], 200h
0x18009a567  jz      short loc_18009A57E
0x18009a569  mov     edx, 67h ; 'g'
0x18009a56e  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a575  mov     rcx, [rcx+10h]
0x18009a579  call    WPP_SF_
0x18009a57e  mov     dword ptr [r13+0], 0
0x18009a586  lea     rcx, [rbp+130h+var_180]; this
0x18009a58a  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009a58f  mov     eax, 1
0x18009a594  jmp     loc_18009B163
0x18009a599  lea     rcx, [r15+20h]
0x18009a59d  mov     r9, [rbp+130h+var_168]
0x18009a5a1  mov     r8, [rbp+130h+var_170]
0x18009a5a5  mov     rdx, rsi
0x18009a5a8  call    ?FindTableEntry@HostMappingTable@@QEAAHPEBGAEAV?$AutoReleaseEx@VHostMappingTableEntry@@@@AEAV?$AutoRelease@UIWSManProvHost@@@@@Z; HostMappingTable::FindTableEntry(ushort const *,AutoReleaseEx<HostMappingTableEntry> &,AutoRelease<IWSManProvHost> &)
0x18009a5ad  test    eax, eax
0x18009a5af  jz      short loc_18009A5F4
0x18009a5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a5b8  lea     rdx, WPP_GLOBAL_Control
0x18009a5bf  cmp     rcx, rdx
0x18009a5c2  jz      short loc_18009A5E2
0x18009a5c4  test    dword ptr [rcx+1Ch], 400h
0x18009a5cb  jz      short loc_18009A5E2
0x18009a5cd  mov     edx, 68h ; 'h'
0x18009a5d2  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a5d9  mov     rcx, [rcx+10h]
0x18009a5dd  call    WPP_SF_
0x18009a5e2  mov     dword ptr [r13+0], 0
0x18009a5ea  mov     rcx, rbx; this
0x18009a5ed  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x18009a5f2  jmp     short loc_18009A58F
0x18009a5f4  xor     r8d, r8d
0x18009a5f7  xor     edx, edx
0x18009a5f9  mov     ecx, 120h
0x18009a5fe  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009a603  mov     [rsp+230h+pbstr], rax
0x18009a608  test    rax, rax
0x18009a60b  jz      short loc_18009A61A
0x18009a60d  mov     rcx, rax; this
0x18009a610  call    ??0HostMappingTableEntry@@QEAA@XZ; HostMappingTableEntry::HostMappingTableEntry(void)
0x18009a615  mov     rsi, rax
0x18009a618  jmp     short loc_18009A61C
0x18009a61a  xor     esi, esi
0x18009a61c  mov     [rbp+130h+var_1A8], rsi
0x18009a620  test    rsi, rsi
0x18009a623  jnz     short loc_18009A682
0x18009a625  mov     rax, [rdi]
0x18009a628  mov     rcx, rdi
0x18009a62b  mov     rax, [rax+18h]
0x18009a62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a634  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a63b  lea     rdx, WPP_GLOBAL_Control
0x18009a642  cmp     rcx, rdx
0x18009a645  jz      short loc_18009A668
0x18009a647  test    dword ptr [rcx+1Ch], 200h
0x18009a64e  jz      short loc_18009A668
0x18009a650  lea     edx, [rsi+69h]
0x18009a653  lea     r9d, [rsi+0Eh]
0x18009a657  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a65e  mov     rcx, [rcx+10h]
0x18009a662  call    WPP_SF_d
0x18009a667  nop
0x18009a668  lea     rcx, [rbp+130h+var_1A8]
0x18009a66c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoReleaseEx@VHostMappingTableEntry@@@@PEAVHostMappingTableEntry@@@@AEAAXXZ; AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(void)
0x18009a671  nop
0x18009a672  lea     rcx, [rbp+130h+var_180]; this
0x18009a676  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009a67b  xor     eax, eax
0x18009a67d  jmp     loc_18009B163
0x18009a682  mov     [rsp+230h+var_1C0], 0
0x18009a68b  movzx   ebx, byte ptr [r12+0E0h]
0x18009a694  mov     [rsp+230h+var_1D0], bl
0x18009a698  movzx   r13d, byte ptr [r12+0F0h]
0x18009a6a1  mov     [rsp+230h+TokenHandle], 0
0x18009a6aa  test    r13d, r13d
0x18009a6ad  jz      loc_18009A947
0x18009a6b3  test    r14, r14
0x18009a6b6  jz      short loc_18009A6C5
0x18009a6b8  mov     rax, [r14+290h]
0x18009a6bf  mov     r9, [rax+8]
0x18009a6c3  jmp     short loc_18009A6C8
0x18009a6c5  xor     r9d, r9d; unsigned __int16 *
0x18009a6c8  lea     rax, [rbp+130h+var_190]
0x18009a6cc  mov     [rsp+230h+ppv], rax; struct _RunAsContext *
0x18009a6d1  lea     r8, [rsp+230h+TokenHandle]; void **
0x18009a6d6  mov     rdx, rdi; struct IRequestContext *
0x18009a6d9  mov     rcx, r12; this
0x18009a6dc  call    ?GetRunAsUserToken@Provider@Catalog@@QEBA_NAEAVIRequestContext@@PEAPEAXPEBGAEAU_RunAsContext@@@Z; Catalog::Provider::GetRunAsUserToken(IRequestContext &,void * *,ushort const *,_RunAsContext &)
0x18009a6e1  test    al, al
0x18009a6e3  jnz     loc_18009A79F
0x18009a6e9  mov     rax, [rdi]
0x18009a6ec  mov     rcx, rdi
0x18009a6ef  mov     rax, [rax+98h]
0x18009a6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6fb  cmp     eax, 803381FBh
0x18009a700  jz      short loc_18009A748
0x18009a702  mov     rax, [rdi]
0x18009a705  mov     rcx, rdi
0x18009a708  mov     rax, [rax+98h]
0x18009a70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a714  cmp     eax, 803381FCh
0x18009a719  jz      short loc_18009A748
0x18009a71b  mov     rax, [rdi]
0x18009a71e  mov     rcx, rdi
0x18009a721  mov     rax, [rax+98h]
0x18009a728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a72d  cmp     eax, 803381FDh
0x18009a732  jz      short loc_18009A748
0x18009a734  mov     rax, [rdi]
0x18009a737  mov     edx, 803381DFh
0x18009a73c  mov     rcx, rdi
0x18009a73f  mov     rax, [rax+48h]
0x18009a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a748  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a74f  lea     rdx, WPP_GLOBAL_Control
0x18009a756  cmp     rcx, rdx
0x18009a759  jz      short loc_18009A77A
0x18009a75b  test    dword ptr [rcx+1Ch], 200h
0x18009a762  jz      short loc_18009A77A
0x18009a764  mov     edx, 6Ah ; 'j'
0x18009a769  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a770  mov     rcx, [rcx+10h]
0x18009a774  call    WPP_SF_
0x18009a779  nop
0x18009a77a  lea     rcx, [rsp+230h+TokenHandle]
0x18009a77f  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x18009a784  nop
0x18009a785  lea     rcx, [rsp+230h+var_1C0]
0x18009a78a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18009a78f  nop
0x18009a790  lea     rcx, [rbp+130h+var_1A8]
0x18009a794  call    ?ReleasePtr@?$AutoCleanup@V?$AutoReleaseEx@VHostMappingTableEntry@@@@PEAVHostMappingTableEntry@@@@AEAAXXZ; AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(void)
0x18009a799  nop
0x18009a79a  jmp     loc_18009A672
0x18009a79f  cmp     dword ptr [rbp+130h+var_190], 2
0x18009a7a3  jnz     loc_18009A947
0x18009a7a9  test    r14, r14
0x18009a7ac  jz      loc_18009A947
0x18009a7b2  mov     [rsp+230h+pbstr], 0
0x18009a7bb  mov     [rbp+130h+var_1B0], 0
0x18009a7c3  lea     r8, [rbp+130h+var_1B0]; struct AutoLocalFree *
0x18009a7c7  mov     rdx, [rsp+230h+TokenHandle]; TokenHandle
0x18009a7cc  mov     rcx, rdi; struct IRequestContext *
0x18009a7cf  call    ?ExtractSidFromToken@CSecurity@@SAHPEAVIRequestContext@@PEAXAEAVAutoLocalFree@@@Z; CSecurity::ExtractSidFromToken(IRequestContext *,void *,AutoLocalFree &)
0x18009a7d4  test    eax, eax
0x18009a7d6  jnz     short loc_18009A842
0x18009a7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a7df  lea     rdx, WPP_GLOBAL_Control
0x18009a7e6  cmp     rcx, rdx
0x18009a7e9  jz      short loc_18009A808
0x18009a7eb  test    dword ptr [rcx+1Ch], 200h
0x18009a7f2  jz      short loc_18009A808
0x18009a7f4  lea     edx, [rax+6Bh]
0x18009a7f7  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a7fe  mov     rcx, [rcx+10h]
0x18009a802  call    WPP_SF_
0x18009a807  nop
0x18009a808  lea     rcx, [rbp+130h+var_1B0]; void *
0x18009a80c  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18009a811  nop
0x18009a812  lea     rcx, [rsp+230h+pbstr]; void *
0x18009a817  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18009a81c  nop
0x18009a81d  lea     rcx, [rsp+230h+TokenHandle]
0x18009a822  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x18009a827  nop
0x18009a828  lea     rcx, [rsp+230h+var_1C0]
0x18009a82d  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18009a832  nop
0x18009a833  lea     rcx, [rbp+130h+var_1A8]
0x18009a837  call    ?ReleasePtr@?$AutoCleanup@V?$AutoReleaseEx@VHostMappingTableEntry@@@@PEAVHostMappingTableEntry@@@@AEAAXXZ; AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(void)
0x18009a83c  nop
0x18009a83d  jmp     loc_18009A672
0x18009a842  mov     rdx, [r14+290h]
0x18009a849  lea     r8, [rsp+230h+pbstr]; struct AutoLocalFree *
0x18009a84e  mov     rdx, [rdx+20h]; TokenHandle
0x18009a852  mov     rcx, rdi; struct IRequestContext *
0x18009a855  call    ?ExtractSidFromToken@CSecurity@@SAHPEAVIRequestContext@@PEAXAEAVAutoLocalFree@@@Z; CSecurity::ExtractSidFromToken(IRequestContext *,void *,AutoLocalFree &)
0x18009a85a  test    eax, eax
0x18009a85c  jz      short loc_18009A870
0x18009a85e  mov     rbx, [rsp+230h+pbstr]
0x18009a863  mov     rax, [r14+290h]
0x18009a86a  mov     r15, [rax+8]
0x18009a86e  jmp     short loc_18009A881
0x18009a870  mov     rax, [r14+20h]
0x18009a874  test    rax, rax
0x18009a877  jz      short loc_18009A8DB
0x18009a879  mov     rbx, [rax+10h]
0x18009a87d  mov     r15, [rax+18h]
0x18009a881  test    rbx, rbx
0x18009a884  jz      short loc_18009A8DB
0x18009a886  test    r15, r15
0x18009a889  jz      short loc_18009A8DB
0x18009a88b  lea     rcx, LOG_WSMAN_OP_VIRTUAL_ACCOUNT_MAPPED; struct _EVENT_DESCRIPTOR *
0x18009a892  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x18009a897  test    al, al
0x18009a899  jz      short loc_18009A8C0
0x18009a89b  mov     rax, qword ptr [rbp+130h+var_190+8]
0x18009a89f  test    rax, rax
0x18009a8a2  jz      short loc_18009A8A9
0x18009a8a4  mov     rcx, [rax]
0x18009a8a7  jmp     short loc_18009A8AB
0x18009a8a9  xor     ecx, ecx
0x18009a8ab  mov     [rsp+230h+ppv], rcx
0x18009a8b0  mov     r9, [rbp+130h+var_1B0]
0x18009a8b4  mov     r8, r15
0x18009a8b7  mov     rdx, rbx
0x18009a8ba  call    ??$LogEvent@PEBGPEBGPEBGPEBG@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@PEBG111@Z; WSMan::LogEvent<ushort const *,ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *,ushort const *)
0x18009a8bf  nop
0x18009a8c0  lea     rcx, [rbp+130h+var_1B0]; void *
0x18009a8c4  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18009a8c9  nop
0x18009a8ca  lea     rcx, [rsp+230h+pbstr]; void *
0x18009a8cf  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18009a8d4  movzx   eax, [rsp+230h+var_1D0]
0x18009a8d9  jmp     short loc_18009A94E
0x18009a8db  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a8e2  lea     rdx, WPP_GLOBAL_Control
0x18009a8e9  cmp     rcx, rdx
0x18009a8ec  jz      short loc_18009A90D
0x18009a8ee  test    dword ptr [rcx+1Ch], 200h
0x18009a8f5  jz      short loc_18009A90D
0x18009a8f7  mov     edx, 6Ch ; 'l'
0x18009a8fc  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009a903  mov     rcx, [rcx+10h]
0x18009a907  call    WPP_SF_
  ... truncated ...
```
