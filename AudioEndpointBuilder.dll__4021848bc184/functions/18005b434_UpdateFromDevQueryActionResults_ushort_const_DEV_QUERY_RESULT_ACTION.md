# UpdateFromDevQueryActionResults(ushort const *,_DEV_QUERY_RESULT_ACTION)

- ea: `0x18005b434`
- end: `0x18005c130`
- name: `?UpdateFromDevQueryActionResults@@YAJPEBGW4_DEV_QUERY_RESULT_ACTION@@@Z`
- size: `3324`
- prototype: `__int64 __fastcall(struct IPropertyStore *, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005b270`

## callees

- `0x180002ef4`
- `0x180002fa4`
- `0x180006b0c`
- `0x180010da8`
- `0x180010dd0`
- `0x18001707c`
- `0x18001b5bc`
- `0x18001b5f8`
- `0x18001d560`
- `0x18001deb0`
- `0x18001f374`
- `0x180027c6c`
- `0x180029c9c`
- `0x180033464`
- `0x1800364d4`
- `0x18003e920`
- `0x18003f798`
- `0x180048590`
- `0x18005b0cc`
- `0x18005b194`
- `0x18005b29c`
- `0x18005b3b0`
- `0x18005b434`
- `0x180063d70`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b90e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b90e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b614`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b614`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b56e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b857`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bb26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bbe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005be14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bfd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b56e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b857`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bb26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bbe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005be14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bfd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b6ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b6ce`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18005b52c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18005b52c`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18005b4df`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18005b4df`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18005b539`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18005b539`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005b6f7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005b6f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b936`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005bf7d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005c070`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b936`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005bf7d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005c070`

## string_xrefs

- `0x18005b54e`: `avcore\audiocore\server\audioendpointbuilder\dll\globalapo.cpp`
- `0x18005b629`: `avcore\audiocore\server\audioendpointbuilder\dll\globalapo.cpp`
- `0x18005b68e`: `avcore\audiocore\server\audioendpointbuilder\dll\globalapo.cpp`

## pseudocode

```c
__int64 __fastcall UpdateFromDevQueryActionResults(struct IPropertyStore *a1, int a2)
{
  const struct _tlgProvider_t *v4; // rax
  int v5; // r9d
  int v6; // r8d
  CONFIGRET v7; // eax
  DWORD v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  DWORD i; // esi
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  _QWORD *v17; // rbx
  unsigned __int16 *v18; // rcx
  int RegistryPropertyStore; // eax
  unsigned int v20; // ebx
  char *v21; // rbx
  void *v22; // r8
  int v23; // eax
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  GUID *v27; // r13
  GUID *j; // r15
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // eax
  const struct _tlgProvider_t *v34; // rax
  int v35; // r8d
  int v36; // r9d
  unsigned __int64 v37; // rcx
  GUID *v38; // r13
  GUID *k; // r15
  int v40; // eax
  unsigned int v41; // ebx
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  unsigned int v45; // ebx
  const struct _tlgProvider_t *v46; // rax
  int v47; // r8d
  int v48; // r9d
  unsigned int phkDevice; // [rsp+20h] [rbp-768h]
  unsigned int phkDevicea; // [rsp+20h] [rbp-768h]
  int phkDeviceb; // [rsp+20h] [rbp-768h]
  int phkDevicec; // [rsp+20h] [rbp-768h]
  int phkDeviced; // [rsp+20h] [rbp-768h]
  struct IPropertyStore *v54; // [rsp+80h] [rbp-708h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-700h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-6F8h] BYREF
  __int128 v57; // [rsp+98h] [rbp-6F0h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-6E0h]
  __int128 v59; // [rsp+B0h] [rbp-6D8h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-6C8h]
  DEVNODE pdnDevInst; // [rsp+C8h] [rbp-6C0h] BYREF
  GUID *p_pclsid; // [rsp+D0h] [rbp-6B8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+D8h] [rbp-6B0h] BYREF
  __int64 v64; // [rsp+E8h] [rbp-6A0h]
  void *v65[2]; // [rsp+F0h] [rbp-698h] BYREF
  GUID v66; // [rsp+100h] [rbp-688h] BYREF
  GUID pclsid; // [rsp+110h] [rbp-678h] BYREF
  _QWORD Src[2]; // [rsp+120h] [rbp-668h] BYREF
  __int64 v69; // [rsp+130h] [rbp-658h]
  unsigned __int64 v70; // [rsp+138h] [rbp-650h]
  unsigned __int16 v71[264]; // [rsp+140h] [rbp-648h] BYREF
  WCHAR Name[512]; // [rsp+350h] [rbp-438h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v4 = AudioEndpointBuilderTelemetryProvider::Provider();
  v6 = *(_DWORD *)v4;
  if ( *(_DWORD *)v4 > 4u )
  {
    LODWORD(hKey) = a2;
    v54 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v4,
      (unsigned int)&dword_180078414,
      v6,
      v5,
      (__int64)&v54,
      (__int64)&hKey);
  }
  v59 = 0;
  v60 = 0;
  pdnDevInst = 0;
  if ( a2 != 3 && !CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)a1, 0) )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = CM_Open_DevNode_Key(pdnDevInst, 0x20019u, 0, 1u, &hKey, 1u);
    v8 = CM_MapCrToWin32Err(v7, 0x507u);
    if ( v8 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xF7,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
             (const char *)v8,
             phkDevice);
      if ( hKey )
        RegCloseKey(hKey);
      if ( (_QWORD)v59 )
        std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
      return v9;
    }
    GetEffectPackIdsInDevNode(hKey, (__int64)&v59);
    if ( hKey )
      RegCloseKey(hKey);
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v11 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\EffectsPacks\\",
          0,
          0,
          0,
          0x20019u,
          0,
          &phkResult,
          0);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x107,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
            (const char *)v11,
            phkDevicea);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( (_QWORD)v59 )
      std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
    return v12;
  }
  else
  {
    v57 = 0;
    v58 = 0;
    for ( i = 0; ; ++i )
    {
      LODWORD(hKey) = 512;
      if ( RegEnumKeyExW(phkResult, i, Name, (LPDWORD)&hKey, 0, 0, 0, 0) )
        break;
      pclsid = 0;
      if ( CLSIDFromString(Name, &pclsid) >= 0 )
      {
        std::wstring::wstring(Src, L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\EffectsPacks\\");
        v14 = -1;
        do
          ++v14;
        while ( Name[v14] );
        v15 = v69;
        if ( v14 > v70 - v69 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            Src,
            v14);
        }
        else
        {
          v16 = v69 + v14;
          v69 += v14;
          v17 = Src;
          if ( v70 > 7 )
            v17 = (_QWORD *)Src[0];
          memmove_0((char *)v17 + 2 * v15, Name, 2 * v14);
          *((_WORD *)v17 + v16) = 0;
        }
        v54 = 0;
        v18 = (unsigned __int16 *)Src;
        if ( v70 > 7 )
          v18 = (unsigned __int16 *)Src[0];
        RegistryPropertyStore = MMDeviceCreateRegistryPropertyStore(v18);
        v20 = RegistryPropertyStore;
        if ( RegistryPropertyStore < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x119,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
            (const char *)(unsigned int)RegistryPropertyStore,
            phkDeviceb);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
          std::wstring::_Tidy_deallocate(Src);
          if ( (_QWORD)v57 )
          {
            std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF0uLL);
            v57 = 0;
            v58 = 0;
          }
          if ( phkResult )
            RegCloseKey(phkResult);
          if ( (_QWORD)v59 )
            std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
          return v20;
        }
        std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,_GUID>(
          v65,
          v59,
          *((_QWORD *)&v59 + 1),
          &pclsid);
        v21 = (char *)v65[0];
        if ( v65[0] == v22 )
        {
          *(_OWORD *)pvar = 0;
          v64 = 0;
          if ( ((int (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v54->lpVtbl->GetValue)(
                 v54,
                 PKEY_FX_ObjectId,
                 pvar) >= 0
            && LOWORD(pvar[0]) == 31
            && !(unsigned int)_o__wcsicmp(pvar[1], a1) )
          {
            std::vector<_GUID>::emplace_back<_GUID &>(&v57, &pclsid);
          }
          PropVariantClear(pvar);
        }
        else
        {
          v23 = CopyEffectMetaData(v54, (const unsigned __int16 *)a1);
          if ( v23 >= 0 )
          {
            v24 = AudioEndpointBuilderTelemetryProvider::Provider();
            if ( *(_DWORD *)v24 > 4u )
            {
              p_pclsid = &pclsid;
              *(_QWORD *)&v66.Data1 = a1;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
                (_DWORD)v24,
                (unsigned int)&unk_1800783D0,
                v25,
                v26,
                (__int64)&v66,
                (__int64)&p_pclsid);
            }
            v66 = pclsid;
            SendMediaEvent(1, &v66);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x121,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
              (const char *)(unsigned int)v23,
              phkDeviceb);
          }
          memmove_0(v21, v21 + 16, *((_QWORD *)&v59 + 1) - (_QWORD)(v21 + 16));
          *((_QWORD *)&v59 + 1) -= 16LL;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
        std::wstring::_Tidy_deallocate(Src);
      }
    }
    v27 = (GUID *)*((_QWORD *)&v59 + 1);
    for ( j = (GUID *)v59; j != v27; ++j )
    {
      phkDevicec = j->Data1;
      v29 = StringCchPrintfW(
              v71,
              0x104u,
              L"%s{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\EffectsPacks\\");
      v30 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          (const char *)(unsigned int)v29,
          phkDevicec);
        if ( (_QWORD)v57 )
        {
          std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF0uLL);
          v57 = 0;
          v58 = 0;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( (_QWORD)v59 )
          std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
        return v30;
      }
      v54 = 0;
      v31 = MMDeviceCreateRegistryPropertyStore(v71);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          (const char *)(unsigned int)v31,
          phkDevicec);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
        if ( (_QWORD)v57 )
        {
          std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF0uLL);
          v57 = 0;
          v58 = 0;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( (_QWORD)v59 )
          std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
        return v32;
      }
      v33 = CopyEffectMetaData(v54, (const unsigned __int16 *)a1);
      if ( v33 >= 0 )
      {
        v34 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v34 > 4u && (unsigned __int8)tlgKeywordOn(v34, 0x400000000000LL, v34) )
        {
          *(_QWORD *)&v66.Data1 = 0x2000000;
          p_pclsid = j;
          v65[0] = a1;
          hKey = (HKEY)2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
            v35,
            (unsigned int)&unk_180078368,
            v35,
            v36,
            (__int64)&hKey,
            (__int64)v65,
            (__int64)&p_pclsid,
            (__int64)&v66);
        }
        pclsid = *j;
        SendMediaEvent(0, &pclsid);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          (const char *)(unsigned int)v33,
          phkDevicec);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
    }
    __SET_PAIR__((unsigned __int64)v38, v37, v57);
    for ( k = (GUID *)v57; k != v38; ++k )
    {
      phkDeviced = k->Data1;
      v40 = StringCchPrintfW(
              v71,
              0x104u,
              L"%s{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\EffectsPacks\\");
      v41 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          (const char *)(unsigned int)v40,
          phkDeviced);
        if ( (_QWORD)v57 )
        {
          std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF0uLL);
          v57 = 0;
          v58 = 0;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( (_QWORD)v59 )
          std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
        return v41;
      }
      v54 = 0;
      v42 = MMDeviceCreateRegistryPropertyStore(v71);
      v43 = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x164,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          (const char *)(unsigned int)v42,
          phkDeviced);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
        if ( (_QWORD)v57 )
        {
          std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF0uLL);
          v57 = 0;
          v58 = 0;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( (_QWORD)v59 )
          std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
        return v43;
      }
      *(_OWORD *)pvar = 0;
      v64 = 0;
      LOWORD(pvar[0]) = 19;
      LODWORD(pvar[1]) = 2;
      v44 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v54->lpVtbl->SetValue)(
              v54,
              PKEY_FX_State,
              pvar);
      v45 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
          (const char *)(unsigned int)v44,
          phkDeviced);
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
        if ( (_QWORD)v57 )
        {
          std::_Deallocate<16>(v57, (v58 - v57) & 0xFFFFFFFFFFFFFFF0uLL);
          v57 = 0;
          v58 = 0;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( (_QWORD)v59 )
          std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
        return v45;
      }
      v46 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v46 > 4u )
      {
        *(_QWORD *)&v66.Data1 = k;
        p_pclsid = (GUID *)a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
          (_DWORD)v46,
          (unsigned int)&dword_180078324,
          v47,
          v48,
          (__int64)&p_pclsid,
          (__int64)&v66);
      }
      pclsid = *k;
      SendMediaEvent(2, &pclsid);
      PropVariantClear(pvar);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
      v37 = v57;
    }
    if ( v37 )
    {
      std::_Deallocate<16>(v37, (v58 - v37) & 0xFFFFFFFFFFFFFFF0uLL);
      v57 = 0;
      v58 = 0;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( (_QWORD)v59 )
      std::_Deallocate<16>(v59, (v60 - v59) & 0xFFFFFFFFFFFFFFF0uLL);
    return 0;
  }
}

```

## disassembly

```asm
0x18005b434  mov     [rsp+arg_8], rbx
0x18005b439  mov     [rsp+arg_10], rsi
0x18005b43e  push    rdi
0x18005b43f  push    r12
0x18005b441  push    r13
0x18005b443  push    r14
0x18005b445  push    r15
0x18005b447  sub     rsp, 760h
0x18005b44e  mov     rax, cs:__security_cookie
0x18005b455  xor     rax, rsp
0x18005b458  mov     [rsp+788h+var_38], rax
0x18005b460  mov     ebx, edx
0x18005b462  mov     r12, rcx
0x18005b465  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005b46a  mov     r8d, [rax]
0x18005b46d  cmp     r8d, 4
0x18005b471  jbe     short loc_18005B4AB
0x18005b473  mov     dword ptr [rsp+788h+hKey], ebx
0x18005b47a  mov     [rsp+788h+var_708], r12
0x18005b482  lea     rcx, [rsp+788h+hKey]
0x18005b48a  mov     qword ptr [rsp+788h+ulFlags], rcx
0x18005b48f  lea     rcx, [rsp+788h+var_708]
0x18005b497  mov     [rsp+788h+phkDevice], rcx
0x18005b49c  lea     rdx, dword_180078414
0x18005b4a3  mov     rcx, rax
0x18005b4a6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18005b4ab  xorps   xmm0, xmm0
0x18005b4ae  movdqu  [rsp+788h+var_6D8], xmm0
0x18005b4b7  xor     edi, edi
0x18005b4b9  mov     [rsp+788h+var_6C8], rdi
0x18005b4c1  mov     [rsp+788h+pdnDevInst], edi
0x18005b4c8  cmp     ebx, 3
0x18005b4cb  jz      loc_18005B5C6
0x18005b4d1  xor     r8d, r8d; ulFlags
0x18005b4d4  mov     rdx, r12; pDeviceID
0x18005b4d7  lea     rcx, [rsp+788h+pdnDevInst]; pdnDevInst
0x18005b4df  call    cs:__imp_CM_Locate_DevNodeW
0x18005b4e5  test    eax, eax
0x18005b4e7  jnz     loc_18005B5C6
0x18005b4ed  mov     [rsp+788h+hKey], rdi
0x18005b4f5  xor     edx, edx
0x18005b4f7  lea     rcx, [rsp+788h+hKey]
0x18005b4ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005b504  mov     [rsp+788h+ulFlags], 1; ulFlags
0x18005b50c  lea     rax, [rsp+788h+hKey]
0x18005b514  mov     [rsp+788h+phkDevice], rax; unsigned int
0x18005b519  lea     r9d, [rdi+1]; Disposition
0x18005b51d  xor     r8d, r8d; ulHardwareProfile
0x18005b520  mov     edx, 20019h; samDesired
0x18005b525  mov     ecx, [rsp+788h+pdnDevInst]; dnDevNode
0x18005b52c  call    cs:__imp_CM_Open_DevNode_Key
0x18005b532  mov     ecx, eax; CmReturnCode
0x18005b534  mov     edx, 507h; DefaultErr
0x18005b539  call    cs:__imp_CM_MapCrToWin32Err
0x18005b53f  test    eax, eax
0x18005b541  jz      short loc_18005B59D
0x18005b543  mov     rcx, [rsp+788h]; this
0x18005b54b  mov     r9d, eax; char *
0x18005b54e  lea     r8, aAvcoreAudiocor_8; "avcore\\audiocore\\server\\audioendpoin"...
0x18005b555  mov     edx, 0F7h; void *
0x18005b55a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b55f  mov     ebx, eax
0x18005b561  mov     rcx, [rsp+788h+hKey]; hKey
0x18005b569  test    rcx, rcx
0x18005b56c  jz      short loc_18005B575
0x18005b56e  call    cs:__imp_RegCloseKey
0x18005b574  nop
0x18005b575  mov     rcx, qword ptr [rsp+788h+var_6D8]
0x18005b57d  test    rcx, rcx
0x18005b580  jz      short loc_18005B596
0x18005b582  mov     rdx, [rsp+788h+var_6C8]
0x18005b58a  sub     rdx, rcx
0x18005b58d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18005b591  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005b596  mov     eax, ebx
0x18005b598  jmp     loc_18005C102
0x18005b59d  lea     rdx, [rsp+788h+var_6D8]
0x18005b5a5  mov     rcx, [rsp+788h+hKey]; hKey
0x18005b5ad  call    ?GetEffectPackIdsInDevNode@@YAXPEAUHKEY__@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@Z; GetEffectPackIdsInDevNode(HKEY__ *,std::vector<_GUID> &)
0x18005b5b2  nop
0x18005b5b3  mov     rcx, [rsp+788h+hKey]; hKey
0x18005b5bb  test    rcx, rcx
0x18005b5be  jz      short loc_18005B5C6
0x18005b5c0  call    cs:__imp_RegCloseKey
0x18005b5c6  mov     [rsp+788h+var_6F8], rdi
0x18005b5ce  xor     edx, edx
0x18005b5d0  lea     rcx, [rsp+788h+var_6F8]
0x18005b5d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005b5dd  mov     [rsp+788h+lpdwDisposition], rdi; lpdwDisposition
0x18005b5e2  lea     rax, [rsp+788h+var_6F8]
0x18005b5ea  mov     [rsp+788h+phkResult], rax; phkResult
0x18005b5ef  mov     [rsp+788h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18005b5f4  mov     [rsp+788h+ulFlags], 20019h; samDesired
0x18005b5fc  mov     dword ptr [rsp+788h+phkDevice], edi; unsigned int
0x18005b600  xor     r9d, r9d; lpClass
0x18005b603  xor     r8d, r8d; Reserved
0x18005b606  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b60d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b614  call    cs:__imp_RegCreateKeyExW
0x18005b61a  test    eax, eax
0x18005b61c  jz      short loc_18005B678
0x18005b61e  mov     rcx, [rsp+788h]; this
0x18005b626  mov     r9d, eax; char *
0x18005b629  lea     r8, aAvcoreAudiocor_8; "avcore\\audiocore\\server\\audioendpoin"...
0x18005b630  mov     edx, 107h; void *
0x18005b635  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b63a  mov     ebx, eax
0x18005b63c  mov     rcx, [rsp+788h+var_6F8]; hKey
0x18005b644  test    rcx, rcx
0x18005b647  jz      short loc_18005B650
0x18005b649  call    cs:__imp_RegCloseKey
0x18005b64f  nop
0x18005b650  mov     rcx, qword ptr [rsp+788h+var_6D8]
0x18005b658  test    rcx, rcx
0x18005b65b  jz      short loc_18005B671
0x18005b65d  mov     rdx, [rsp+788h+var_6C8]
0x18005b665  sub     rdx, rcx
0x18005b668  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18005b66c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005b671  mov     eax, ebx
0x18005b673  jmp     loc_18005C102
0x18005b678  xorps   xmm0, xmm0
0x18005b67b  movdqu  [rsp+788h+var_6F0], xmm0
0x18005b684  mov     [rsp+788h+var_6E0], rdi
0x18005b68c  mov     esi, edi
0x18005b68e  lea     r14, aAvcoreAudiocor_8; "avcore\\audiocore\\server\\audioendpoin"...
0x18005b695  mov     dword ptr [rsp+788h+hKey], 200h
0x18005b6a0  mov     [rsp+788h+phkResult], rdi; lpftLastWriteTime
0x18005b6a5  mov     [rsp+788h+lpSecurityAttributes], rdi; lpcchClass
0x18005b6aa  mov     qword ptr [rsp+788h+ulFlags], rdi; lpClass
0x18005b6af  mov     [rsp+788h+phkDevice], rdi; lpReserved
0x18005b6b4  lea     r9, [rsp+788h+hKey]; lpcchName
0x18005b6bc  lea     r8, [rsp+788h+Name]; lpName
0x18005b6c4  mov     edx, esi; dwIndex
0x18005b6c6  mov     rcx, [rsp+788h+var_6F8]; hKey
0x18005b6ce  call    cs:__imp_RegEnumKeyExW
0x18005b6d4  test    eax, eax
0x18005b6d6  jnz     loc_18005BA21
0x18005b6dc  xorps   xmm0, xmm0
0x18005b6df  movups  xmmword ptr [rsp+788h+pclsid.Data1], xmm0
0x18005b6e7  lea     rdx, [rsp+788h+pclsid]; pclsid
0x18005b6ef  lea     rcx, [rsp+788h+Name]; lpsz
0x18005b6f7  call    cs:__imp_CLSIDFromString
0x18005b6fd  test    eax, eax
0x18005b6ff  js      loc_18005BA1A
0x18005b705  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b70c  lea     rcx, [rsp+788h+Src]
0x18005b714  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005b719  nop
0x18005b71a  lea     rax, [rsp+788h+Name]
0x18005b722  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005b726  inc     rdx
0x18005b729  cmp     [rax+rdx*2], di
0x18005b72d  jnz     short loc_18005B726
0x18005b72f  mov     rcx, [rsp+788h+var_658]
0x18005b737  mov     rax, [rsp+788h+var_650]
0x18005b73f  sub     rax, rcx
0x18005b742  cmp     rdx, rax
0x18005b745  ja      short loc_18005B78C
0x18005b747  lea     rdi, [rcx+rdx]
0x18005b74b  mov     [rsp+788h+var_658], rdi
0x18005b753  lea     rbx, [rsp+788h+Src]
0x18005b75b  cmp     [rsp+788h+var_650], 7
0x18005b764  cmova   rbx, [rsp+788h+Src]
0x18005b76d  lea     r8, [rdx+rdx]; Size
0x18005b771  lea     rcx, [rbx+rcx*2]; void *
0x18005b775  lea     rdx, [rsp+788h+Name]; Src
0x18005b77d  call    memmove_0
0x18005b782  xor     eax, eax
0x18005b784  mov     [rbx+rdi*2], ax
0x18005b788  xor     edi, edi
0x18005b78a  jmp     short loc_18005B7A7
0x18005b78c  mov     [rsp+788h+phkDevice], rdx; int
0x18005b791  lea     r9, [rsp+788h+Name]
0x18005b799  lea     rcx, [rsp+788h+Src]; Src
0x18005b7a1  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18005b7a6  nop
0x18005b7a7  mov     [rsp+788h+var_708], rdi
0x18005b7af  lea     rcx, [rsp+788h+Src]
0x18005b7b7  cmp     [rsp+788h+var_650], 7
0x18005b7c0  cmova   rcx, [rsp+788h+Src]; unsigned __int16 *
0x18005b7c9  lea     r8, [rsp+788h+var_708]
0x18005b7d1  call    MMDeviceCreateRegistryPropertyStore
0x18005b7d6  mov     ebx, eax
0x18005b7d8  test    eax, eax
0x18005b7da  jns     loc_18005B886
0x18005b7e0  mov     rcx, [rsp+788h]; this
0x18005b7e8  mov     r9d, eax; char *
0x18005b7eb  mov     r8, r14; unsigned int
0x18005b7ee  mov     edx, 119h; void *
0x18005b7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b7f8  nop
0x18005b7f9  lea     rcx, [rsp+788h+var_708]
0x18005b801  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005b806  nop
0x18005b807  lea     rcx, [rsp+788h+Src]
0x18005b80f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b814  nop
0x18005b815  mov     rcx, qword ptr [rsp+788h+var_6F0]
0x18005b81d  test    rcx, rcx
0x18005b820  jz      short loc_18005B84A
0x18005b822  mov     rdx, [rsp+788h+var_6E0]
0x18005b82a  sub     rdx, rcx
0x18005b82d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18005b831  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005b836  xorps   xmm0, xmm0
0x18005b839  movdqu  [rsp+788h+var_6F0], xmm0
0x18005b842  mov     [rsp+788h+var_6E0], rdi
0x18005b84a  mov     rcx, [rsp+788h+var_6F8]; hKey
0x18005b852  test    rcx, rcx
0x18005b855  jz      short loc_18005B85E
0x18005b857  call    cs:__imp_RegCloseKey
0x18005b85d  nop
0x18005b85e  mov     rcx, qword ptr [rsp+788h+var_6D8]
0x18005b866  test    rcx, rcx
0x18005b869  jz      short loc_18005B87F
0x18005b86b  mov     rdx, [rsp+788h+var_6C8]
0x18005b873  sub     rdx, rcx
0x18005b876  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18005b87a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005b87f  mov     eax, ebx
0x18005b881  jmp     loc_18005C102
0x18005b886  mov     r8, qword ptr [rsp+788h+var_6D8+8]
0x18005b88e  lea     r9, [rsp+788h+pclsid]
0x18005b896  mov     rdx, qword ptr [rsp+788h+var_6D8]
0x18005b89e  lea     rcx, [rsp+788h+var_698]
0x18005b8a6  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@std@@U_GUID@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_GUID@@@std@@@std@@@0@V10@V10@AEBU_GUID@@@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,_GUID>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_GUID>>>,_GUID const &)
0x18005b8ab  mov     rbx, [rsp+788h+var_698]
0x18005b8b3  cmp     rbx, r8
0x18005b8b6  jnz     loc_18005B941
0x18005b8bc  xorps   xmm0, xmm0
0x18005b8bf  xor     eax, eax
0x18005b8c1  movups  xmmword ptr [rsp+788h+pvar], xmm0
0x18005b8c9  mov     [rsp+788h+var_6A0], rax
0x18005b8d1  mov     rcx, [rsp+788h+var_708]
0x18005b8d9  mov     rax, [rcx]
0x18005b8dc  lea     r8, [rsp+788h+pvar]
0x18005b8e4  lea     rdx, PKEY_FX_ObjectId
0x18005b8eb  mov     rax, [rax+28h]
0x18005b8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8f4  test    eax, eax
0x18005b8f6  js      short loc_18005B92E
0x18005b8f8  cmp     word ptr [rsp+788h+pvar], 1Fh
0x18005b901  jnz     short loc_18005B92E
0x18005b903  mov     rdx, r12
0x18005b906  mov     rcx, [rsp+788h+pvar+8]
0x18005b90e  call    cs:__imp__o__wcsicmp
0x18005b914  test    eax, eax
0x18005b916  jnz     short loc_18005B92E
0x18005b918  lea     rdx, [rsp+788h+pclsid]
0x18005b920  lea     rcx, [rsp+788h+var_6F0]
0x18005b928  call    ??$emplace_back@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAU_GUID@@AEAU2@@Z; std::vector<_GUID>::emplace_back<_GUID &>(_GUID &)
0x18005b92d  nop
0x18005b92e  lea     rcx, [rsp+788h+pvar]; pvar
0x18005b936  call    cs:__imp_PropVariantClear
0x18005b93c  jmp     loc_18005B9FF
0x18005b941  mov     rdx, r12; unsigned __int16 *
0x18005b944  mov     rcx, [rsp+788h+var_708]; struct IPropertyStore *
0x18005b94c  call    ?CopyEffectMetaData@@YAJPEAUIPropertyStore@@PEBG@Z; CopyEffectMetaData(IPropertyStore *,ushort const *)
0x18005b951  mov     rcx, [rsp+788h]; this
0x18005b959  test    eax, eax
0x18005b95b  jns     short loc_18005B96F
0x18005b95d  mov     r9d, eax; char *
0x18005b960  mov     r8, r14; unsigned int
0x18005b963  mov     edx, 121h; void *
0x18005b968  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b96d  jmp     short loc_18005B9DF
0x18005b96f  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005b974  mov     ecx, [rax]
0x18005b976  cmp     ecx, 4
0x18005b979  jbe     short loc_18005B9BC
0x18005b97b  lea     rcx, [rsp+788h+pclsid]
0x18005b983  mov     [rsp+788h+var_6B8], rcx
0x18005b98b  mov     qword ptr [rsp+788h+var_688], r12
0x18005b993  lea     rcx, [rsp+788h+var_6B8]
0x18005b99b  mov     qword ptr [rsp+788h+ulFlags], rcx
0x18005b9a0  lea     rcx, [rsp+788h+var_688]
0x18005b9a8  mov     [rsp+788h+phkDevice], rcx
0x18005b9ad  lea     rdx, unk_1800783D0
0x18005b9b4  mov     rcx, rax
0x18005b9b7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x18005b9bc  movaps  xmm0, xmmword ptr [rsp+788h+pclsid.Data1]
0x18005b9c4  movdqa  [rsp+788h+var_688], xmm0
0x18005b9cd  lea     rdx, [rsp+788h+var_688]
0x18005b9d5  mov     ecx, 1
0x18005b9da  call    ?SendMediaEvent@@YAJW4EffectPackEventState@@U_GUID@@@Z; SendMediaEvent(EffectPackEventState,_GUID)
0x18005b9df  lea     rdx, [rbx+10h]; Src
0x18005b9e3  mov     r8, qword ptr [rsp+788h+var_6D8+8]
0x18005b9eb  sub     r8, rdx; Size
0x18005b9ee  mov     rcx, rbx; void *
0x18005b9f1  call    memmove_0
0x18005b9f6  sub     qword ptr [rsp+788h+var_6D8+8], 10h
0x18005b9ff  lea     rcx, [rsp+788h+var_708]
0x18005ba07  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005ba0c  nop
0x18005ba0d  lea     rcx, [rsp+788h+Src]
0x18005ba15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ba1a  inc     esi
0x18005ba1c  jmp     loc_18005B695
0x18005ba21  mov     r15, qword ptr [rsp+788h+var_6D8]
  ... truncated ...
```
