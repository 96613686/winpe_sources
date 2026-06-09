# FirewallHelper::AddAppRoutePolicyRules(ushort const *,ushort const *,_FirewallWcmAppRoutePolicyKeys const &,_GUID const &,_FirewallWcmAppRoutePolicyFilterIds *)

- ea: `0x18002ae14`
- end: `0x18002b729`
- name: `?AddAppRoutePolicyRules@FirewallHelper@@YAJPEBG0AEBU_FirewallWcmAppRoutePolicyKeys@@AEBU_GUID@@PEAU_FirewallWcmAppRoutePolicyFilterIds@@@Z`
- size: `2325`
- prototype: `__int64 __fastcall(wchar_t *this, const unsigned __int16 *, const unsigned __int16 *, GUID *, UINT64 *id)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029960`

## callees

- `0x18001a1f8`
- `0x18001a27c`
- `0x18001c080`
- `0x18001d8e0`
- `0x18001e368`
- `0x1800290d4`
- `0x18002add8`
- `0x18002ae14`
- `0x18002bd8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002afd9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002afd9`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18002aff6`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18002aff6`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002b0f2`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002b0f2`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b1fc`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b29d`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b2ae`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b334`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b345`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b356`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b3e1`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b3f5`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b406`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b417`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b49f`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4b4`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4c6`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4d7`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4e8`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b570`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b585`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b598`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b5aa`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b5bb`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b5cc`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b659`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b66c`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b67f`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b692`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b6a4`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b6b5`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b6c6`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b1fc`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b29d`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b2ae`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b334`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b345`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b356`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b3e1`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b3f5`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b406`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b417`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b49f`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4b4`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4c6`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4d7`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b4e8`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b570`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b585`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b598`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b5aa`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b5bb`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b5cc`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b659`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b66c`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b67f`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b692`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b6a4`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b6b5`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b6c6`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b157`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b1cc`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b26d`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b304`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b3ac`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b46a`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b53b`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b622`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b157`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b1cc`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b26d`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b304`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b3ac`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b46a`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b53b`
- `fwpuclnt!FwpmFilterAdd0` at `0x18002b622`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b184`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b20a`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b2bc`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b364`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b425`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b4f6`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b5da`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b6d4`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b6ed`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b184`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b20a`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b2bc`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b364`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b425`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b4f6`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b5da`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b6d4`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b6ed`

## pseudocode

```c
__int64 __fastcall FirewallHelper::AddAppRoutePolicyRules(
        wchar_t *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        GUID *a4,
        UINT64 *id)
{
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  unsigned int v11; // ebx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // xmm0_8
  __int128 *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 result; // rax
  int v18; // eax
  unsigned int v19; // ebx
  DWORD v20; // eax
  unsigned int v21; // ebx
  DWORD v22; // eax
  unsigned int v23; // ebx
  unsigned __int8 *v24; // r14
  DWORD v25; // eax
  unsigned int v26; // ebx
  UINT64 *v27; // r15
  DWORD v28; // eax
  unsigned int v29; // ebx
  UINT64 *v30; // r12
  DWORD v31; // eax
  unsigned int v32; // ebx
  UINT64 *v33; // r13
  DWORD v34; // eax
  unsigned int v35; // ebx
  DWORD v36; // eax
  unsigned int v37; // ebx
  DWORD v38; // eax
  unsigned int v39; // ebx
  DWORD v40; // eax
  unsigned int v41; // ebx
  int engineHandle; // [rsp+20h] [rbp-178h]
  unsigned int engineHandlea; // [rsp+20h] [rbp-178h]
  HANDLE v44; // [rsp+30h] [rbp-168h] BYREF
  PSID pSid; // [rsp+38h] [rbp-160h] BYREF
  __int128 v46; // [rsp+40h] [rbp-158h] BYREF
  FWPM_FILTER0 filter; // [rsp+60h] [rbp-138h] BYREF
  unsigned int Data1; // [rsp+130h] [rbp-68h] BYREF
  __int128 v49; // [rsp+134h] [rbp-64h]
  _DWORD v50[5]; // [rsp+144h] [rbp-54h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  pSid = 0;
  v46 = 0;
  Data1 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  if ( (unsigned __int8)FirewallHelper::IsWin32AppId(a2) )
  {
    if ( a2 )
    {
      v9 = 0x7FFFFFFF;
      v10 = a2;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v9;
      }
      while ( v9 );
      v11 = v9 == 0 ? 0x80070057 : 0;
      if ( v9 )
      {
        v12 = (2 * (0x7FFFFFFF - v9)) & -(__int64)(v9 != 0);
        if ( v12 + 2 < v12 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x136,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
            (const char *)0x80070216LL,
            engineHandle);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
          result = 2147942934LL;
          goto LABEL_36;
        }
        *((_QWORD *)&v46 + 1) = a2;
        if ( v12 + 2 > 0xFFFFFFFF )
        {
          LODWORD(v46) = -1;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x139,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
            (const char *)0x80070216LL,
            engineHandle);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
          result = 2147942934LL;
          goto LABEL_36;
        }
        LODWORD(v46) = v12 + 2;
        Data1 = FWPM_CONDITION_ALE_APP_ID.Data1;
        v13 = *(_QWORD *)&FWPM_CONDITION_ALE_APP_ID.Data2;
        DWORD2(v49) = *(_DWORD *)&FWPM_CONDITION_ALE_APP_ID.Data4[4];
        v50[1] = 12;
        v14 = &v46;
        goto LABEL_17;
      }
    }
    else
    {
      v11 = -2147024809;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
      (const char *)v11,
      engineHandle);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
    result = v11;
    goto LABEL_36;
  }
  pSid = 0;
  v18 = DeriveAppContainerSidFromAppContainerName(a2, &pSid);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
      (const char *)(unsigned int)v18,
      engineHandle);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
    result = v19;
    goto LABEL_36;
  }
  Data1 = FWPM_CONDITION_ALE_PACKAGE_ID;
  v13 = 0xBB6A02A64997F17CuLL;
  DWORD2(v49) = 473243430;
  v50[1] = 13;
  v14 = (__int128 *)pSid;
LABEL_17:
  *(_QWORD *)&v50[3] = v14;
  HIDWORD(v49) = 0;
  *(_QWORD *)&v49 = v13;
  memset_0(&filter, 0, sizeof(filter));
  filter.displayData.name = this;
  filter.weight.type = FWP_EMPTY;
  filter.filterCondition = (FWPM_FILTER_CONDITION0 *)&Data1;
  filter.numFilterConditions = 1;
  filter.providerKey = a4;
  filter.subLayerKey = (GUID)*((_OWORD *)a3 + 2);
  filter.action.type = 20483;
  v44 = 0;
  v20 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &v44);
  if ( v20 )
  {
    v21 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x157,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
            (const char *)v20,
            engineHandlea);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
    result = v21;
  }
  else
  {
    filter.layerKey = FWPM_LAYER_ALE_BIND_REDIRECT_V4;
    filter.action.4 = *(union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6 *)a3;
    v22 = FwpmFilterAdd0(v44, &filter, 0, id);
    if ( v22 )
    {
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x15F,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
              (const char *)v22,
              engineHandlea);
      FwpmEngineClose0(v44);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
      result = v23;
    }
    else
    {
      filter.layerKey = FWPM_LAYER_ALE_BIND_REDIRECT_V6;
      filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 1);
      v24 = (unsigned __int8 *)(id + 1);
      v25 = FwpmFilterAdd0(v44, &filter, 0, id + 1);
      if ( v25 )
      {
        v26 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x168,
                (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                (const char *)v25,
                engineHandlea);
        FwpmFilterDeleteById0(v44, *id);
        *id = 0;
        FwpmEngineClose0(v44);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
        result = v26;
      }
      else
      {
        filter.subLayerKey = FWPM_SUBLAYER_INSPECTION;
        filter.action.type = 24580;
        filter.layerKey = FWPM_LAYER_ALE_CONNECT_REDIRECT_V4;
        filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 3);
        v27 = id + 2;
        v28 = FwpmFilterAdd0(v44, &filter, 0, id + 2);
        if ( v28 )
        {
          v29 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x175,
                  (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                  (const char *)v28,
                  engineHandlea);
          FwpmFilterDeleteById0(v44, *(_QWORD *)v24);
          *(_QWORD *)v24 = 0;
          FwpmFilterDeleteById0(v44, *id);
          *id = 0;
          FwpmEngineClose0(v44);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
          result = v29;
        }
        else
        {
          filter.layerKey = FWPM_LAYER_ALE_CONNECT_REDIRECT_V6;
          filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 4);
          v30 = id + 3;
          v31 = FwpmFilterAdd0(v44, &filter, 0, id + 3);
          if ( v31 )
          {
            v32 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x17E,
                    (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                    (const char *)v31,
                    engineHandlea);
            FwpmFilterDeleteById0(v44, *v27);
            *v27 = 0;
            FwpmFilterDeleteById0(v44, *(_QWORD *)v24);
            *(_QWORD *)v24 = 0;
            FwpmFilterDeleteById0(v44, *id);
            *id = 0;
            FwpmEngineClose0(v44);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
            result = v32;
          }
          else
          {
            filter.layerKey = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4;
            filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 5);
            v33 = id + 4;
            v34 = FwpmFilterAdd0(v44, &filter, 0, id + 4);
            if ( v34 )
            {
              v35 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x187,
                      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                      (const char *)v34,
                      engineHandlea);
              FwpmFilterDeleteById0(v44, *v30);
              *v30 = 0;
              FwpmFilterDeleteById0(v44, *v27);
              *v27 = 0;
              FwpmFilterDeleteById0(v44, *(_QWORD *)v24);
              *(_QWORD *)v24 = 0;
              FwpmFilterDeleteById0(v44, *id);
              *id = 0;
              FwpmEngineClose0(v44);
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
              result = v35;
            }
            else
            {
              filter.layerKey = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6;
              filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 6);
              v36 = FwpmFilterAdd0(v44, &filter, 0, id + 5);
              if ( v36 )
              {
                v37 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x190,
                        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                        (const char *)v36,
                        engineHandlea);
                FwpmFilterDeleteById0(v44, *v33);
                *v33 = 0;
                FwpmFilterDeleteById0(v44, *v30);
                *v30 = 0;
                FwpmFilterDeleteById0(v44, *v27);
                *v27 = 0;
                FwpmFilterDeleteById0(v44, *(_QWORD *)v24);
                *(_QWORD *)v24 = 0;
                FwpmFilterDeleteById0(v44, *id);
                *id = 0;
                FwpmEngineClose0(v44);
                wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
                result = v37;
              }
              else
              {
                filter.layerKey = FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V4;
                filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 7);
                v38 = FwpmFilterAdd0(v44, &filter, 0, id + 6);
                if ( v38 )
                {
                  v39 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x199,
                          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                          (const char *)v38,
                          engineHandlea);
                  FwpmFilterDeleteById0(v44, id[5]);
                  id[5] = 0;
                  FwpmFilterDeleteById0(v44, *v33);
                  *v33 = 0;
                  FwpmFilterDeleteById0(v44, *v30);
                  *v30 = 0;
                  FwpmFilterDeleteById0(v44, *v27);
                  *v27 = 0;
                  FwpmFilterDeleteById0(v44, *(_QWORD *)v24);
                  *(_QWORD *)v24 = 0;
                  FwpmFilterDeleteById0(v44, *id);
                  *id = 0;
                  FwpmEngineClose0(v44);
                  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
                  result = v39;
                }
                else
                {
                  filter.layerKey = FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V6;
                  filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)*((_OWORD *)a3 + 8);
                  v40 = FwpmFilterAdd0(v44, &filter, 0, id + 7);
                  if ( v40 )
                  {
                    v41 = wil::details::in1diag3::Return_Win32(
                            retaddr,
                            (void *)0x1A2,
                            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                            (const char *)v40,
                            engineHandlea);
                    FwpmFilterDeleteById0(v44, id[6]);
                    id[6] = 0;
                    FwpmFilterDeleteById0(v44, id[5]);
                    id[5] = 0;
                    FwpmFilterDeleteById0(v44, *v33);
                    *v33 = 0;
                    FwpmFilterDeleteById0(v44, *v30);
                    *v30 = 0;
                    FwpmFilterDeleteById0(v44, *v27);
                    *v27 = 0;
                    FwpmFilterDeleteById0(v44, *(_QWORD *)v24);
                    *(_QWORD *)v24 = 0;
                    FwpmFilterDeleteById0(v44, *id);
                    *id = 0;
                    FwpmEngineClose0(v44);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
                    result = v41;
                  }
                  else
                  {
                    FwpmEngineClose0(v44);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
                    result = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_36:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      LODWORD(v44) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x1AD, v15, v16);
      result = (unsigned int)v44;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002ae14  mov     r11, rsp
0x18002ae17  push    rbx
0x18002ae18  push    rsi
0x18002ae19  push    rdi
0x18002ae1a  push    r12
0x18002ae1c  push    r13
0x18002ae1e  push    r14
0x18002ae20  push    r15
0x18002ae22  sub     rsp, 160h
0x18002ae29  mov     rax, cs:__security_cookie
0x18002ae30  xor     rax, rsp
0x18002ae33  mov     [rsp+198h+var_40], rax
0x18002ae3b  mov     r12, r9
0x18002ae3e  mov     rsi, r8
0x18002ae41  mov     r14, rdx
0x18002ae44  mov     r15, rcx
0x18002ae47  mov     rdi, [rsp+198h+id]
0x18002ae4f  xor     r13d, r13d
0x18002ae52  mov     [rsp+198h+pSid], r13
0x18002ae57  xorps   xmm0, xmm0
0x18002ae5a  movups  [rsp+198h+var_158], xmm0
0x18002ae5f  mov     [r11-68h], r13d
0x18002ae63  xorps   xmm1, xmm1
0x18002ae66  xor     eax, eax
0x18002ae68  movups  xmmword ptr [r11-64h], xmm1
0x18002ae6d  movups  xmmword ptr [r11-54h], xmm1
0x18002ae72  mov     [r11-44h], eax
0x18002ae76  mov     rcx, rdx; SourceString
0x18002ae79  call    FirewallHelper__IsWin32AppId
0x18002ae7e  test    al, al
0x18002ae80  jz      loc_18002AFC2
0x18002ae86  test    r14, r14
0x18002ae89  jz      loc_18002AF90
0x18002ae8f  mov     edx, 7FFFFFFFh
0x18002ae94  mov     ecx, edx
0x18002ae96  mov     rax, r14
0x18002ae99  cmp     [rax], r13w
0x18002ae9d  jz      short loc_18002AEA9
0x18002ae9f  add     rax, 2
0x18002aea3  sub     rcx, 1
0x18002aea7  jnz     short loc_18002AE99
0x18002aea9  mov     rax, rcx
0x18002aeac  neg     rax
0x18002aeaf  sbb     ebx, ebx
0x18002aeb1  not     ebx
0x18002aeb3  and     ebx, 80070057h
0x18002aeb9  test    rcx, rcx
0x18002aebc  jz      loc_18002AF95
0x18002aec2  sub     rdx, rcx
0x18002aec5  add     rdx, rdx
0x18002aec8  neg     rcx
0x18002aecb  sbb     rax, rax
0x18002aece  and     rax, rdx
0x18002aed1  lea     rcx, [rax+2]
0x18002aed5  cmp     rcx, rax
0x18002aed8  jb      loc_18002AF5E
0x18002aede  mov     qword ptr [rsp+198h+var_158+8], r14
0x18002aee3  mov     ebx, 0FFFFFFFFh
0x18002aee8  cmp     rcx, rbx
0x18002aeeb  ja      short loc_18002AF28
0x18002aeed  mov     dword ptr [rsp+198h+var_158], ecx
0x18002aef1  mov     eax, cs:FWPM_CONDITION_ALE_APP_ID.Data1
0x18002aef7  mov     [rsp+198h+var_68], eax
0x18002aefe  movsd   xmm0, qword ptr cs:FWPM_CONDITION_ALE_APP_ID.Data2
0x18002af06  mov     eax, dword ptr cs:FWPM_CONDITION_ALE_APP_ID.Data4+4
0x18002af0c  mov     [rsp+198h+var_5C], eax
0x18002af13  mov     [rsp+198h+var_50], 0Ch
0x18002af1e  lea     rax, [rsp+198h+var_158]
0x18002af23  jmp     loc_18002B066
0x18002af28  mov     dword ptr [rsp+198h+var_158], ebx
0x18002af2c  mov     rcx, [rsp+198h]; this
0x18002af34  mov     ebx, 80070216h
0x18002af39  mov     r9d, ebx; char *
0x18002af3c  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002af43  mov     edx, 139h; void *
0x18002af48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af4d  lea     rcx, [rsp+198h+pSid]
0x18002af52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002af57  mov     eax, ebx
0x18002af59  jmp     loc_18002B705
0x18002af5e  mov     rcx, [rsp+198h]; this
0x18002af66  mov     ebx, 80070216h
0x18002af6b  mov     r9d, ebx; char *
0x18002af6e  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002af75  mov     edx, 136h; void *
0x18002af7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af7f  lea     rcx, [rsp+198h+pSid]
0x18002af84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002af89  mov     eax, ebx
0x18002af8b  jmp     loc_18002B705
0x18002af90  mov     ebx, 80070057h
0x18002af95  mov     rcx, [rsp+198h]; this
0x18002af9d  mov     r9d, ebx; char *
0x18002afa0  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002afa7  mov     edx, 135h; void *
0x18002afac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afb1  lea     rcx, [rsp+198h+pSid]
0x18002afb6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002afbb  mov     eax, ebx
0x18002afbd  jmp     loc_18002B705
0x18002afc2  mov     rbx, [rsp+198h+pSid]
0x18002afc7  test    rbx, rbx
0x18002afca  jz      short loc_18002AFE9
0x18002afcc  lea     rcx, [rsp+198h+var_148]; this
0x18002afd1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002afd6  mov     rcx, rbx; pSid
0x18002afd9  call    cs:__imp_FreeSid
0x18002afdf  lea     rcx, [rsp+198h+var_148]; this
0x18002afe4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002afe9  mov     [rsp+198h+pSid], r13
0x18002afee  lea     rdx, [rsp+198h+pSid]
0x18002aff3  mov     rcx, r14
0x18002aff6  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18002affc  mov     ebx, eax
0x18002affe  test    eax, eax
0x18002b000  jns     short loc_18002B02F
0x18002b002  mov     rcx, [rsp+198h]; this
0x18002b00a  mov     r9d, eax; char *
0x18002b00d  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b014  mov     edx, 142h; void *
0x18002b019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b01e  lea     rcx, [rsp+198h+pSid]
0x18002b023  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b028  mov     eax, ebx
0x18002b02a  jmp     loc_18002B705
0x18002b02f  mov     eax, cs:FWPM_CONDITION_ALE_PACKAGE_ID
0x18002b035  mov     [rsp+198h+var_68], eax
0x18002b03c  movsd   xmm0, cs:qword_180038AC4
0x18002b044  mov     eax, cs:dword_180038ACC
0x18002b04a  mov     [rsp+198h+var_5C], eax
0x18002b051  mov     [rsp+198h+var_50], 0Dh
0x18002b05c  mov     rax, [rsp+198h+pSid]
0x18002b061  mov     ebx, 0FFFFFFFFh
0x18002b066  mov     [rsp+198h+var_48], rax
0x18002b06e  mov     [rsp+198h+var_58], r13d
0x18002b076  movsd   [rsp+198h+var_64], xmm0
0x18002b07f  xor     edx, edx; Val
0x18002b081  mov     r8d, 0C8h; Size
0x18002b087  lea     rcx, [rsp+198h+filter]; void *
0x18002b08c  call    memset_0
0x18002b091  mov     [rsp+198h+filter.displayData.name], r15
0x18002b096  mov     [rsp+198h+filter.weight.type], r13d
0x18002b09e  lea     rax, [rsp+198h+var_68]
0x18002b0a6  mov     [rsp+198h+filter.filterCondition], rax
0x18002b0ae  mov     [rsp+198h+filter.numFilterConditions], 1
0x18002b0b9  mov     [rsp+198h+filter.providerKey], r12
0x18002b0c1  movups  xmm0, xmmword ptr [rsi+20h]
0x18002b0c5  movdqu  xmmword ptr [rsp+198h+filter.subLayerKey.Data1], xmm0
0x18002b0ce  mov     [rsp+198h+filter.action.type], 5003h
0x18002b0d9  mov     [rsp+198h+var_168], r13
0x18002b0de  lea     rax, [rsp+198h+var_168]
0x18002b0e3  mov     qword ptr [rsp+198h+engineHandle], rax; unsigned int
0x18002b0e8  xor     r9d, r9d; session
0x18002b0eb  xor     r8d, r8d; authIdentity
0x18002b0ee  mov     edx, ebx; authnService
0x18002b0f0  xor     ecx, ecx; serverName
0x18002b0f2  call    cs:__imp_FwpmEngineOpen0
0x18002b0f8  test    eax, eax
0x18002b0fa  jz      short loc_18002B12B
0x18002b0fc  mov     rcx, [rsp+198h]; this
0x18002b104  mov     r9d, eax; char *
0x18002b107  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b10e  mov     edx, 157h; void *
0x18002b113  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b118  mov     ebx, eax
0x18002b11a  lea     rcx, [rsp+198h+pSid]
0x18002b11f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b124  mov     eax, ebx
0x18002b126  jmp     loc_18002B705
0x18002b12b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V4.Data1
0x18002b132  movdqu  xmmword ptr [rsp+198h+filter.layerKey.Data1], xmm0
0x18002b13b  movups  xmm0, xmmword ptr [rsi]
0x18002b13e  movdqu  xmmword ptr [rsp+198h+filter.action.4], xmm0
0x18002b147  mov     r9, rdi; id
0x18002b14a  xor     r8d, r8d; sd
0x18002b14d  lea     rdx, [rsp+198h+filter]; filter
0x18002b152  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b157  call    cs:__imp_FwpmFilterAdd0
0x18002b15d  test    eax, eax
0x18002b15f  jz      short loc_18002B19B
0x18002b161  mov     rcx, [rsp+198h]; this
0x18002b169  mov     r9d, eax; char *
0x18002b16c  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b173  mov     edx, 15Fh; void *
0x18002b178  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b17d  mov     ebx, eax
0x18002b17f  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b184  call    cs:__imp_FwpmEngineClose0
0x18002b18a  lea     rcx, [rsp+198h+pSid]
0x18002b18f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b194  mov     eax, ebx
0x18002b196  jmp     loc_18002B705
0x18002b19b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V6.Data1
0x18002b1a2  movdqu  xmmword ptr [rsp+198h+filter.layerKey.Data1], xmm0
0x18002b1ab  movups  xmm0, xmmword ptr [rsi+10h]
0x18002b1af  movdqu  xmmword ptr [rsp+198h+filter.action.4], xmm0
0x18002b1b8  lea     r14, [rdi+8]
0x18002b1bc  mov     r9, r14; id
0x18002b1bf  xor     r8d, r8d; sd
0x18002b1c2  lea     rdx, [rsp+198h+filter]; filter
0x18002b1c7  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b1cc  call    cs:__imp_FwpmFilterAdd0
0x18002b1d2  test    eax, eax
0x18002b1d4  jz      short loc_18002B221
0x18002b1d6  mov     rcx, [rsp+198h]; this
0x18002b1de  mov     r9d, eax; char *
0x18002b1e1  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b1e8  mov     edx, 168h; void *
0x18002b1ed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b1f2  mov     ebx, eax
0x18002b1f4  mov     rdx, [rdi]; id
0x18002b1f7  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b1fc  call    cs:__imp_FwpmFilterDeleteById0
0x18002b202  mov     [rdi], r13
0x18002b205  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b20a  call    cs:__imp_FwpmEngineClose0
0x18002b210  lea     rcx, [rsp+198h+pSid]
0x18002b215  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b21a  mov     eax, ebx
0x18002b21c  jmp     loc_18002B705
0x18002b221  movups  xmm0, xmmword ptr cs:FWPM_SUBLAYER_INSPECTION.Data1
0x18002b228  movdqu  xmmword ptr [rsp+198h+filter.subLayerKey.Data1], xmm0
0x18002b231  mov     [rsp+198h+filter.action.type], 6004h
0x18002b23c  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_CONNECT_REDIRECT_V4.Data1
0x18002b243  movdqu  xmmword ptr [rsp+198h+filter.layerKey.Data1], xmm1
0x18002b24c  movups  xmm0, xmmword ptr [rsi+30h]
0x18002b250  movdqu  xmmword ptr [rsp+198h+filter.action.4], xmm0
0x18002b259  lea     r15, [rdi+10h]
0x18002b25d  mov     r9, r15; id
0x18002b260  xor     r8d, r8d; sd
0x18002b263  lea     rdx, [rsp+198h+filter]; filter
0x18002b268  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b26d  call    cs:__imp_FwpmFilterAdd0
0x18002b273  test    eax, eax
0x18002b275  jz      short loc_18002B2D3
0x18002b277  mov     rcx, [rsp+198h]; this
0x18002b27f  mov     r9d, eax; char *
0x18002b282  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b289  mov     edx, 175h; void *
0x18002b28e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b293  mov     ebx, eax
0x18002b295  mov     rdx, [r14]; id
0x18002b298  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b29d  call    cs:__imp_FwpmFilterDeleteById0
0x18002b2a3  mov     [r14], r13
0x18002b2a6  mov     rdx, [rdi]; id
0x18002b2a9  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b2ae  call    cs:__imp_FwpmFilterDeleteById0
0x18002b2b4  mov     [rdi], r13
0x18002b2b7  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b2bc  call    cs:__imp_FwpmEngineClose0
0x18002b2c2  lea     rcx, [rsp+198h+pSid]
0x18002b2c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b2cc  mov     eax, ebx
0x18002b2ce  jmp     loc_18002B705
0x18002b2d3  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_CONNECT_REDIRECT_V6.Data1
0x18002b2da  movdqu  xmmword ptr [rsp+198h+filter.layerKey.Data1], xmm0
0x18002b2e3  movups  xmm0, xmmword ptr [rsi+40h]
0x18002b2e7  movdqu  xmmword ptr [rsp+198h+filter.action.4], xmm0
0x18002b2f0  lea     r12, [rdi+18h]
0x18002b2f4  mov     r9, r12; id
0x18002b2f7  xor     r8d, r8d; sd
0x18002b2fa  lea     rdx, [rsp+198h+filter]; filter
0x18002b2ff  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b304  call    cs:__imp_FwpmFilterAdd0
0x18002b30a  test    eax, eax
0x18002b30c  jz      short loc_18002B37B
0x18002b30e  mov     rcx, [rsp+198h]; this
0x18002b316  mov     r9d, eax; char *
0x18002b319  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b320  mov     edx, 17Eh; void *
0x18002b325  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b32a  mov     ebx, eax
0x18002b32c  mov     rdx, [r15]; id
0x18002b32f  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b334  call    cs:__imp_FwpmFilterDeleteById0
0x18002b33a  mov     [r15], r13
0x18002b33d  mov     rdx, [r14]; id
0x18002b340  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b345  call    cs:__imp_FwpmFilterDeleteById0
0x18002b34b  mov     [r14], r13
0x18002b34e  mov     rdx, [rdi]; id
0x18002b351  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b356  call    cs:__imp_FwpmFilterDeleteById0
0x18002b35c  mov     [rdi], r13
0x18002b35f  mov     rcx, [rsp+198h+var_168]; engineHandle
0x18002b364  call    cs:__imp_FwpmEngineClose0
0x18002b36a  lea     rcx, [rsp+198h+pSid]
0x18002b36f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b374  mov     eax, ebx
0x18002b376  jmp     loc_18002B705
0x18002b37b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4.Data1
0x18002b382  movdqu  xmmword ptr [rsp+198h+filter.layerKey.Data1], xmm0
0x18002b38b  movups  xmm0, xmmword ptr [rsi+50h]
0x18002b38f  movdqu  xmmword ptr [rsp+198h+filter.action.4], xmm0
0x18002b398  lea     r13, [rdi+20h]
0x18002b39c  mov     r9, r13; id
0x18002b39f  xor     r8d, r8d; sd
0x18002b3a2  lea     rdx, [rsp+198h+filter]; filter
0x18002b3a7  mov     rcx, [rsp+198h+var_168]; engineHandle
  ... truncated ...
```
