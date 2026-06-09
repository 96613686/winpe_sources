# ReadNetworkInterfacePropertiesFromDriver

- ea: `0x180021650`
- end: `0x18002236a`
- name: `ReadNetworkInterfacePropertiesFromDriver`
- size: `3354`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `37`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e3a8`
- `0x18001f2e4`
- `0x180023af4`

## callees

- `0x180001b50`
- `0x180001b7c`
- `0x1800027c0`
- `0x1800032b4`
- `0x1800032e4`
- `0x180006e34`
- `0x180008348`
- `0x180008854`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000da60`
- `0x18000df60`
- `0x18001b168`
- `0x18001b1e8`
- `0x18001b2d0`
- `0x18001b35c`
- `0x180020d28`
- `0x180021350`
- `0x180021580`
- `0x180021650`
- `0x1800246c4`
- `0x180024cdc`
- `0x180026a10`
- `0x180026d3c`
- `0x180027560`
- `0x1800275e4`
- `0x180027d2c`
- `0x1800283fc`
- `0x180028500`
- `0x1800285cc`
- `0x1800286d8`
- `0x180028dc4`
- `0x1800290b8`
- `0x18002923c`
- `0x180029840`
- `0x180029ce4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022237`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022237`

## string_xrefs

- `0x180022257`: `DriverUpdated`
- `0x1800218e9`: `*AccessType`
- `0x180021906`: `*AccessType`
- `0x180021bd7`: `*AccessType`
- `0x1800220c2`: `DoNotReplaceUpperRange`
- `0x180022244`: `NetworkInterfaceInstallTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
LSTATUS __fastcall ReadNetworkInterfacePropertiesFromDriver(__int64 a1, __int64 a2, char *a3, __int64 a4)
{
  const wchar_t *v6; // rax
  int v7; // esi
  __int64 v8; // r15
  __int64 v9; // r12
  __int64 v10; // r14
  unsigned __int64 v11; // r13
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 *v14; // rax
  int v15; // edx
  __int64 v16; // rcx
  int v17; // ecx
  int v18; // esi
  const struct _DEVPROPKEY *v19; // rdx
  __int64 ValueString; // rax
  __int64 v21; // rax
  int v22; // eax
  __int64 v24; // rax
  __int64 v25; // r10
  __int64 v26; // rax
  __int64 v27; // r8
  unsigned int v28; // [rsp+70h] [rbp-90h] BYREF
  unsigned int ValueDword; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v30; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v31; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int64 v32; // [rsp+80h] [rbp-80h]
  unsigned __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v38; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-30h]
  _BYTE v43[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+F8h] [rbp-8h] BYREF
  char v45[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  HKEY v46; // [rsp+1D0h] [rbp+D0h] BYREF
  HKEY v47; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v48; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int64 v49; // [rsp+1E8h] [rbp+E8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD *v51; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 v52; // [rsp+200h] [rbp+100h]
  _BYTE v53[16]; // [rsp+210h] [rbp+110h] BYREF
  struct _GUID Buf1; // [rsp+220h] [rbp+120h] BYREF
  _QWORD *v55[4]; // [rsp+230h] [rbp+130h] BYREF
  _OWORD v56[2]; // [rsp+250h] [rbp+150h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v57; // [rsp+270h] [rbp+170h] BYREF
  __int64 *v58; // [rsp+290h] [rbp+190h]
  int v59; // [rsp+298h] [rbp+198h]
  int v60; // [rsp+29Ch] [rbp+19Ch]

  v34 = a2;
  v42 = a1;
  v6 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  NetSetupDevice::NetSetupDevice((NetSetupDevice *)v53, v6, 0);
  NetSetupDevice::OpenSoftwareKey((NetSetupDevice *)v53, (RegistryKey *)&v46, 7u, a3);
  ValueDword = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v7 = 0;
  LODWORD(v48) = 0;
  v8 = -1;
  v35 = -1;
  v9 = -1;
  v36 = -1;
  v10 = -1;
  v37 = -1;
  v32 = -1;
  v41 = -1;
  v11 = -1;
  v38 = -1;
  v33 = -1;
  v39 = -1;
  v49 = -1;
  v40 = -1;
  if ( RegistryKey::ValueExists((RegistryKey *)&v46, L"*IfType") )
  {
    ValueDword = RegistryKey::GetValueDword(&v46, L"*IfType", 0, 0);
    LODWORD(v47) = RegistryKey::GetValueDword(&v46, L"*MediaType", 0, 0);
    v30 = RegistryKey::GetValueDword(&v46, L"*PhysicalMediaType", 0, 0);
    v28 = RegistryKey::GetValueDword(&v46, L"Characteristics", 0, 0);
    if ( RegistryKey::ValueExists((RegistryKey *)&v46, L"EnableDhcp") )
      v7 = 2 - ((unsigned int)RegistryKey::GetValueDword(&v46, L"EnableDhcp", 0, 0) != 0);
    if ( RegistryKey::ValueExists((RegistryKey *)&v46, L"BusType") )
      v8 = (unsigned int)RegistryKey::GetValueDword(&v46, L"BusType", 1, 0);
    if ( RegistryKey::ValueExists((RegistryKey *)&v46, L"Port1DeviceNumber") )
      v9 = (unsigned int)RegistryKey::GetValueDword(&v46, L"Port1DeviceNumber", 1, 0);
    if ( RegistryKey::ValueExists((RegistryKey *)&v46, L"Port1FunctionNumber") )
      v10 = (unsigned int)RegistryKey::GetValueDword(&v46, L"Port1FunctionNumber", 1, 0);
    RegistryKey::TryOpenSubKey(&v46, &v48, L"NetworkInterface", 1, 0);
    if ( v48 )
    {
      if ( RegistryKey::ValueExists((RegistryKey *)&v48, L"*IfConnectorPresent") )
        v32 = (unsigned int)RegistryKey::GetValueDword((HKEY *)&v48, L"*IfConnectorPresent", 0, 0);
      if ( RegistryKey::ValueExists((RegistryKey *)&v48, L"*AccessType") )
        v11 = (unsigned int)RegistryKey::GetValueDword((HKEY *)&v48, L"*AccessType", 0, 0);
      if ( RegistryKey::ValueExists((RegistryKey *)&v48, L"*ConnectionType") )
        v33 = (unsigned int)RegistryKey::GetValueDword((HKEY *)&v48, L"*ConnectionType", 0, 0);
      if ( RegistryKey::ValueExists((RegistryKey *)&v48, L"*DirectionType") )
        v49 = (unsigned int)RegistryKey::GetValueDword((HKEY *)&v48, L"*DirectionType", 0, 0);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&v48);
    goto LABEL_46;
  }
  ReadInfProperties(
    (struct NetSetupDevice *)v53,
    &ValueDword,
    &v28,
    &v30,
    &v31,
    (int *)&v48,
    (unsigned __int64 *)&v35,
    (unsigned __int64 *)&v36,
    (unsigned __int64 *)&v37,
    (unsigned __int64 *)&v41,
    &v38,
    (unsigned __int64 *)&v39,
    (unsigned __int64 *)&v40);
  RegistryKey::SetValue(&v46, L"*IfType", ValueDword, 0);
  LODWORD(v47) = v28;
  RegistryKey::SetValue(&v46, L"*MediaType", v28, 0);
  RegistryKey::SetValue(&v46, L"*PhysicalMediaType", v30, 0);
  v28 = v31;
  RegistryKey::SetValue(&v46, L"Characteristics", v31, 0);
  v7 = v48;
  switch ( (_DWORD)v48 )
  {
    case 0:
      RegistryKey::DeleteValue(&v46, L"EnableDhcp");
      break;
    case 1:
      v13 = 1;
      goto LABEL_24;
    case 2:
      v13 = 0;
LABEL_24:
      RegistryKey::SetValue(&v46, L"EnableDhcp", v13, 0);
      break;
  }
  v8 = v35;
  if ( v35 != -1 )
    RegistryKey::SetValue(&v46, L"BusType", (unsigned int)v35, 1);
  v9 = v36;
  if ( v36 != -1 )
    RegistryKey::SetValue(&v46, L"Port1DeviceNumber", (unsigned int)v36, 1);
  v10 = v37;
  if ( v37 != -1 )
    RegistryKey::SetValue(&v46, L"Port1FunctionNumber", (unsigned int)v37, 1);
  v11 = v38;
  v33 = v39;
  v49 = v40;
  v32 = v41;
  if ( v41 != -1 && v38 != -1 && v39 != -1 && v40 != -1 )
  {
    RegistryKey::CreateSubKey(&v46, (RegistryKey *)&v48, L"NetworkInterface", 3u, 0);
    RegistryKey::SetValue((HKEY *)&v48, L"*IfConnectorPresent", v32);
    RegistryKey::SetValue((HKEY *)&v48, L"*AccessType", v11);
    RegistryKey::SetValue((HKEY *)&v48, L"*ConnectionType", v33);
    RegistryKey::SetValue((HKEY *)&v48, L"*DirectionType", v49);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&v48);
  }
  if ( (unsigned int)dword_180049000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180049000, 0x400000000000LL, v12) )
  {
    v14 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    if ( v14 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *((_WORD *)v14 + v16) != (_WORD)v15 );
      v17 = 2 * v16 + 2;
    }
    else
    {
      v14 = &qword_180037068;
      v17 = 2;
    }
    v58 = v14;
    v59 = v17;
    v60 = v15;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180049000, (int)&byte_1800418F1, 0, 0, 3u, &v57);
  }
LABEL_46:
  RegistryKey::SetValue(&v46, L"IfTypePreStart", ValueDword, 0);
  ReadNetworkInterfaceCompartmentGuid((RegistryKey *)&v46);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(a4, &NETSETUPPKEY_Interface_PnpInstance, v34);
  LODWORD(v48) = ValueDword;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_IfType,
    (__int64)&v48);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_MediaType,
    (__int64)&v47);
  LODWORD(v47) = v30;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_PhysicalMediaType,
    (__int64)&v47);
  v45[0] = v28 & 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_IsVirtual,
    (__int64)v45);
  v45[0] = (v28 & 4) != 0;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_IsPhysical,
    (__int64)v45);
  v45[0] = (v28 & 8) != 0;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    a4,
    (__int128 *)NETSETUPPKEY_Driver_HideInUi,
    (__int64)v45);
  LODWORD(v47) = v28;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    a4,
    (__int128 *)NETSETUPPKEY_INF_Characteristics,
    (__int64)&v47);
  if ( v32 != -1 )
  {
    v45[0] = v32 != 0;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_IfConnectorPresent,
      (__int64)v45);
  }
  if ( v11 != -1 )
  {
    LODWORD(v47) = v11;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_AccessType,
      (__int64)&v47);
  }
  if ( v33 != -1 )
  {
    LODWORD(v47) = v33;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_ConnectionType,
      (__int64)&v47);
  }
  if ( v49 != -1 )
  {
    LODWORD(v47) = v49;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_DirectionType,
      (__int64)&v47);
  }
  if ( v8 != -1 )
  {
    LODWORD(v47) = v8;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      a4,
      (__int128 *)NETSETUPPKEY_INF_ClaimedBusType,
      (__int64)&v47);
  }
  if ( v9 != -1 )
  {
    LODWORD(v47) = v9;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_PciPort1DeviceNumber,
      (__int64)&v47);
  }
  if ( v10 != -1 )
  {
    LODWORD(v47) = v10;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_PciPort1FunctionNumber,
      (__int64)&v47);
  }
  v56[0] = 0;
  v56[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v56[0]) = 0;
  if ( (unsigned __int8)NetSetupDevice::GetStringProperty(v53, &DEVPKEY_Device_MatchingDeviceId, v56) )
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(
      a4,
      (__int128 *)NETSETUPPKEY_Interface_PnpMatchingHardwareId,
      (__int64)v56);
  v18 = v7 - 1;
  if ( v18 )
  {
    if ( v18 != 1 )
      goto LABEL_67;
    v45[0] = 1;
  }
  else
  {
    v45[0] = 0;
  }
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_DisableDhcp,
    (__int64)v45);
LABEL_67:
  RegistryKey::TryOpenSubKey(&v46, &v49, L"Ndi", 1, 0);
  if ( v49 )
  {
    if ( RegistryKey::ValueExists((RegistryKey *)&v49, L"HelpText") )
    {
      RegistryKey::GetValueString((HKEY *)&v49, (__int64)v55, L"HelpText", 0);
      NetSetup2::NetworkInterfaceTemplate::set_languageneutral_Description(a4);
      std::wstring::_Tidy_deallocate((__int64)v55);
    }
    RegistryKey::TryOpenSubKey(&v46, &v47, L"Ndi\\Interfaces", 1, 0);
    if ( v47 )
    {
      ValueString = RegistryKey::GetValueString(&v47, (__int64)v43, L"UpperRange", 0);
      SplitCommaAndSpaceSeparatedList(v55, ValueString);
      std::wstring::_Tidy_deallocate((__int64)v43);
      NetSetup2::ObjectCreationTemplate::SetPropertyToValue<8210,std::vector<std::wstring>>(
        a4,
        (__int128 *)NETSETUPPKEY_Bind_UpperRange,
        (__int64)v55);
      v21 = RegistryKey::GetValueString(&v47, (__int64)&v57, L"LowerRange", 0);
      SplitCommaAndSpaceSeparatedList(&v51, v21);
      std::wstring::_Tidy_deallocate((__int64)&v57);
      NetSetup2::ObjectCreationTemplate::SetPropertyToValue<8210,std::vector<std::wstring>>(
        a4,
        (__int128 *)NETSETUPPKEY_Bind_LowerRange,
        (__int64)&v51);
      v45[0] = RegistryKey::GetValueBoolean((__int64)&v47, (__int64)L"DoNotReplaceUpperRange");
      NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
        a4,
        (__int128 *)NETSETUPPKEY_Interface_DoNotReplaceUpperRange,
        (__int64)v45);
      if ( v51 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v51);
        std::_Deallocate<16>(v51, (*((_QWORD *)&v52 + 1) - (_QWORD)v51) & 0xFFFFFFFFFFFFFFE0uLL);
        v51 = 0;
        v52 = 0;
      }
      if ( v55[0] )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v55[0]);
        std::_Deallocate<16>(v55[0], ((char *)v55[2] - (char *)v55[0]) & 0xFFFFFFFFFFFFFFE0uLL);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
  }
  Buf1 = 0;
  if ( !NetSetupDevice::GetGuidProperty((NetSetupDevice *)v53, v19, &Buf1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = std::wstring::c_str(v34);
      WPP_SF_S(*(_QWORD *)(v25 + 16), 52, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v24);
    }
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  if ( !memcmp_0(&Buf1, &GUID_DEVCLASS_NET, 0x10u) )
  {
    v22 = 0;
  }
  else
  {
    if ( memcmp_0(&Buf1, &GUID_DEVCLASS_INFRARED, 0x10u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = std::wstring::c_str(v34);
        WPP_SF__guid_S(*(_QWORD *)(v27 + 16), 53, v27, (unsigned int)&Buf1, v26);
      }
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
      throw (HResultException *)pExceptionObject;
    }
    v22 = 1;
  }
  LODWORD(v47) = v22;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_PnpDeviceClass,
    (__int64)&v47);
  v45[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    a4,
    (__int128 *)NETSETUPPKEY_Interface_DeviceNeedsRestart,
    (__int64)v45);
  ReadNetSetupPropertiesFromDriver(v42, &v46, a4);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  RegistryKey::SetValue(&v46, L"NetworkInterfaceInstallTimestamp", *(_QWORD *)&SystemTimeAsFileTime);
  RegistryKey::DeleteValue(&v46, L"DriverUpdated");
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&v49);
  std::wstring::_Tidy_deallocate((__int64)v56);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
}

```

## disassembly

```asm
0x180021650  push    rbp
0x180021652  push    rbx
0x180021653  push    rsi
0x180021654  push    rdi
0x180021655  push    r12
0x180021657  push    r13
0x180021659  push    r14
0x18002165b  push    r15
0x18002165d  lea     rbp, [rsp-1B8h]
0x180021665  sub     rsp, 2B8h
0x18002166c  mov     rax, cs:__security_cookie
0x180021673  xor     rax, rsp
0x180021676  mov     [rbp+1F0h+var_50], rax
0x18002167d  mov     rdi, r9
0x180021680  mov     rbx, r8
0x180021683  mov     [rbp+1F0h+var_260], rdx
0x180021687  mov     [rbp+1F0h+var_220], rcx
0x18002168b  mov     rcx, rdx
0x18002168e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021693  xor     r8d, r8d; bool
0x180021696  mov     rdx, rax; wchar_t *
0x180021699  lea     rcx, [rbp+1F0h+var_E0]; this
0x1800216a0  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x1800216a5  mov     r9, rbx
0x1800216a8  mov     r8d, 7
0x1800216ae  lea     rdx, [rbp+1F0h+var_120]
0x1800216b5  lea     rcx, [rbp+1F0h+var_E0]
0x1800216bc  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x1800216c1  nop
0x1800216c2  xor     ebx, ebx
0x1800216c4  mov     [rsp+2F0h+var_27C], ebx
0x1800216c8  mov     [rsp+2F0h+var_280], ebx
0x1800216cc  mov     [rsp+2F0h+var_278], ebx
0x1800216d0  mov     [rsp+2F0h+var_274], ebx
0x1800216d4  mov     esi, ebx
0x1800216d6  mov     dword ptr [rbp+1F0h+var_110], ebx
0x1800216dc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800216e0  mov     r15, rcx
0x1800216e3  mov     [rbp+1F0h+var_258], rcx
0x1800216e7  mov     r12, rcx
0x1800216ea  mov     [rbp+1F0h+var_250], rcx
0x1800216ee  mov     r14, rcx
0x1800216f1  mov     [rbp+1F0h+var_248], rcx
0x1800216f5  mov     [rbp+1F0h+var_270], rcx
0x1800216f9  mov     [rbp+1F0h+var_228], rcx
0x1800216fd  mov     r13, rcx
0x180021700  mov     [rbp+1F0h+var_240], rcx
0x180021704  mov     [rbp+1F0h+var_268], rcx
0x180021708  mov     [rbp+1F0h+var_238], rcx
0x18002170c  mov     [rbp+1F0h+var_108], rcx
0x180021713  mov     [rbp+1F0h+var_230], rcx
0x180021717  lea     rdx, aIftype; "*IfType"
0x18002171e  lea     rcx, [rbp+1F0h+var_120]; this
0x180021725  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002172a  test    al, al
0x18002172c  jz      loc_18002199E
0x180021732  xor     r9d, r9d
0x180021735  xor     r8d, r8d
0x180021738  lea     rdx, aIftype; "*IfType"
0x18002173f  lea     rcx, [rbp+1F0h+var_120]
0x180021746  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18002174b  mov     [rsp+2F0h+var_27C], eax
0x18002174f  xor     r9d, r9d
0x180021752  xor     r8d, r8d
0x180021755  lea     rdx, aMediatype; "*MediaType"
0x18002175c  lea     rcx, [rbp+1F0h+var_120]
0x180021763  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180021768  mov     dword ptr [rbp+1F0h+var_118], eax
0x18002176e  xor     r9d, r9d
0x180021771  xor     r8d, r8d
0x180021774  lea     rdx, aPhysicalmediat; "*PhysicalMediaType"
0x18002177b  lea     rcx, [rbp+1F0h+var_120]
0x180021782  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180021787  mov     [rsp+2F0h+var_278], eax
0x18002178b  xor     r9d, r9d
0x18002178e  xor     r8d, r8d
0x180021791  lea     rdx, aCharacteristic; "Characteristics"
0x180021798  lea     rcx, [rbp+1F0h+var_120]
0x18002179f  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800217a4  mov     [rsp+2F0h+var_280], eax
0x1800217a8  lea     rdx, aEnabledhcp; "EnableDhcp"
0x1800217af  lea     rcx, [rbp+1F0h+var_120]; this
0x1800217b6  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800217bb  test    al, al
0x1800217bd  jz      short loc_1800217DF
0x1800217bf  xor     r9d, r9d
0x1800217c2  xor     r8d, r8d
0x1800217c5  lea     rdx, aEnabledhcp; "EnableDhcp"
0x1800217cc  lea     rcx, [rbp+1F0h+var_120]
0x1800217d3  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800217d8  neg     eax
0x1800217da  sbb     esi, esi
0x1800217dc  add     esi, 2
0x1800217df  lea     rdx, aBustype; "BusType"
0x1800217e6  lea     rcx, [rbp+1F0h+var_120]; this
0x1800217ed  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800217f2  mov     ebx, 1
0x1800217f7  test    al, al
0x1800217f9  jz      short loc_180021817
0x1800217fb  xor     r9d, r9d
0x1800217fe  mov     r8d, ebx
0x180021801  lea     rdx, aBustype; "BusType"
0x180021808  lea     rcx, [rbp+1F0h+var_120]
0x18002180f  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180021814  mov     r15d, eax
0x180021817  lea     rdx, aPort1devicenum; "Port1DeviceNumber"
0x18002181e  lea     rcx, [rbp+1F0h+var_120]; this
0x180021825  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002182a  test    al, al
0x18002182c  jz      short loc_18002184A
0x18002182e  xor     r9d, r9d
0x180021831  mov     r8d, ebx
0x180021834  lea     rdx, aPort1devicenum; "Port1DeviceNumber"
0x18002183b  lea     rcx, [rbp+1F0h+var_120]
0x180021842  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180021847  mov     r12d, eax
0x18002184a  lea     rdx, aPort1functionn; "Port1FunctionNumber"
0x180021851  lea     rcx, [rbp+1F0h+var_120]; this
0x180021858  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002185d  test    al, al
0x18002185f  jz      short loc_18002187D
0x180021861  xor     r9d, r9d
0x180021864  mov     r8d, ebx
0x180021867  lea     rdx, aPort1functionn; "Port1FunctionNumber"
0x18002186e  lea     rcx, [rbp+1F0h+var_120]
0x180021875  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18002187a  mov     r14d, eax
0x18002187d  mov     qword ptr [rsp+2F0h+var_2D0], 0
0x180021886  mov     r9d, ebx
0x180021889  lea     r8, aNetworkinterfa_2; "NetworkInterface"
0x180021890  lea     rdx, [rbp+1F0h+var_110]
0x180021897  lea     rcx, [rbp+1F0h+var_120]
0x18002189e  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x1800218a3  nop
0x1800218a4  cmp     [rbp+1F0h+var_110], 0
0x1800218ac  jz      loc_18002198D
0x1800218b2  lea     rdx, aIfconnectorpre; "*IfConnectorPresent"
0x1800218b9  lea     rcx, [rbp+1F0h+var_110]; this
0x1800218c0  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800218c5  test    al, al
0x1800218c7  jz      short loc_1800218E9
0x1800218c9  xor     r9d, r9d
0x1800218cc  xor     r8d, r8d
0x1800218cf  lea     rdx, aIfconnectorpre; "*IfConnectorPresent"
0x1800218d6  lea     rcx, [rbp+1F0h+var_110]
0x1800218dd  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800218e2  mov     r8d, eax
0x1800218e5  mov     [rbp+1F0h+var_270], r8
0x1800218e9  lea     rdx, aAccesstype; "*AccessType"
0x1800218f0  lea     rcx, [rbp+1F0h+var_110]; this
0x1800218f7  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800218fc  test    al, al
0x1800218fe  jz      short loc_18002191C
0x180021900  xor     r9d, r9d
0x180021903  xor     r8d, r8d
0x180021906  lea     rdx, aAccesstype; "*AccessType"
0x18002190d  lea     rcx, [rbp+1F0h+var_110]
0x180021914  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180021919  mov     r13d, eax
0x18002191c  lea     rdx, aConnectiontype; "*ConnectionType"
0x180021923  lea     rcx, [rbp+1F0h+var_110]; this
0x18002192a  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002192f  test    al, al
0x180021931  jz      short loc_180021953
0x180021933  xor     r9d, r9d
0x180021936  xor     r8d, r8d
0x180021939  lea     rdx, aConnectiontype; "*ConnectionType"
0x180021940  lea     rcx, [rbp+1F0h+var_110]
0x180021947  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18002194c  mov     r8d, eax
0x18002194f  mov     [rbp+1F0h+var_268], r8
0x180021953  lea     rdx, aDirectiontype; "*DirectionType"
0x18002195a  lea     rcx, [rbp+1F0h+var_110]; this
0x180021961  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180021966  test    al, al
0x180021968  jz      short loc_18002198D
0x18002196a  xor     r9d, r9d
0x18002196d  xor     r8d, r8d
0x180021970  lea     rdx, aDirectiontype; "*DirectionType"
0x180021977  lea     rcx, [rbp+1F0h+var_110]
0x18002197e  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180021983  mov     r8d, eax
0x180021986  mov     [rbp+1F0h+var_108], r8
0x18002198d  lea     rcx, [rbp+1F0h+var_110]
0x180021994  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180021999  jmp     loc_180021CC3
0x18002199e  lea     rax, [rbp+1F0h+var_230]
0x1800219a2  mov     [rsp+2F0h+var_290], rax; __int64
0x1800219a7  lea     rax, [rbp+1F0h+var_238]
0x1800219ab  mov     [rsp+2F0h+var_298], rax; __int64
0x1800219b0  lea     rax, [rbp+1F0h+var_240]
0x1800219b4  mov     [rsp+2F0h+var_2A0], rax; __int64
0x1800219b9  lea     rax, [rbp+1F0h+var_228]
0x1800219bd  mov     [rsp+2F0h+var_2A8], rax; __int64
0x1800219c2  lea     rax, [rbp+1F0h+var_248]
0x1800219c6  mov     [rsp+2F0h+var_2B0], rax; __int64
0x1800219cb  lea     rax, [rbp+1F0h+var_250]
0x1800219cf  mov     [rsp+2F0h+var_2B8], rax; __int64
0x1800219d4  lea     rax, [rbp+1F0h+var_258]
0x1800219d8  mov     [rsp+2F0h+var_2C0], rax; __int64
0x1800219dd  lea     rax, [rbp+1F0h+var_110]
0x1800219e4  mov     [rsp+2F0h+var_2C8], rax; __int64
0x1800219e9  lea     rax, [rsp+2F0h+var_274]
0x1800219ee  mov     qword ptr [rsp+2F0h+var_2D0], rax; unsigned int *
0x1800219f3  lea     r9, [rsp+2F0h+var_278]; unsigned int *
0x1800219f8  lea     r8, [rsp+2F0h+var_280]; unsigned int *
0x1800219fd  lea     rdx, [rsp+2F0h+var_27C]; unsigned int *
0x180021a02  lea     rcx, [rbp+1F0h+var_E0]; struct NetSetupDevice *
0x180021a09  call    ReadInfProperties
0x180021a0e  xor     r9d, r9d
0x180021a11  mov     eax, [rsp+2F0h+var_27C]
0x180021a15  mov     [rsp+2F0h+var_27C], eax
0x180021a19  mov     r8d, eax
0x180021a1c  lea     rdx, aIftype; "*IfType"
0x180021a23  lea     rcx, [rbp+1F0h+var_120]
0x180021a2a  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021a2f  xor     r9d, r9d
0x180021a32  mov     eax, [rsp+2F0h+var_280]
0x180021a36  mov     dword ptr [rbp+1F0h+var_118], eax
0x180021a3c  mov     r8d, eax
0x180021a3f  lea     rdx, aMediatype; "*MediaType"
0x180021a46  lea     rcx, [rbp+1F0h+var_120]
0x180021a4d  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021a52  xor     r9d, r9d
0x180021a55  mov     eax, [rsp+2F0h+var_278]
0x180021a59  mov     [rsp+2F0h+var_278], eax
0x180021a5d  mov     r8d, eax
0x180021a60  lea     rdx, aPhysicalmediat; "*PhysicalMediaType"
0x180021a67  lea     rcx, [rbp+1F0h+var_120]
0x180021a6e  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021a73  xor     r9d, r9d
0x180021a76  mov     eax, [rsp+2F0h+var_274]
0x180021a7a  mov     [rsp+2F0h+var_280], eax
0x180021a7e  mov     r8d, eax
0x180021a81  lea     rdx, aCharacteristic; "Characteristics"
0x180021a88  lea     rcx, [rbp+1F0h+var_120]
0x180021a8f  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021a94  mov     esi, dword ptr [rbp+1F0h+var_110]
0x180021a9a  mov     ecx, esi
0x180021a9c  mov     ebx, 1
0x180021aa1  test    esi, esi
0x180021aa3  jz      short loc_180021AD0
0x180021aa5  sub     ecx, ebx
0x180021aa7  jz      short loc_180021AC8
0x180021aa9  cmp     ecx, ebx
0x180021aab  jnz     short loc_180021AE3
0x180021aad  xor     r9d, r9d
0x180021ab0  xor     r8d, r8d
0x180021ab3  lea     rdx, aEnabledhcp; "EnableDhcp"
0x180021aba  lea     rcx, [rbp+1F0h+var_120]
0x180021ac1  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021ac6  jmp     short loc_180021AE3
0x180021ac8  xor     r9d, r9d
0x180021acb  mov     r8d, ebx
0x180021ace  jmp     short loc_180021AB3
0x180021ad0  lea     rdx, aEnabledhcp; "EnableDhcp"
0x180021ad7  lea     rcx, [rbp+1F0h+var_120]; this
0x180021ade  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x180021ae3  mov     r15, [rbp+1F0h+var_258]
0x180021ae7  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180021aeb  jz      short loc_180021B06
0x180021aed  mov     r9d, ebx
0x180021af0  mov     r8d, r15d
0x180021af3  lea     rdx, aBustype; "BusType"
0x180021afa  lea     rcx, [rbp+1F0h+var_120]
0x180021b01  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021b06  mov     r12, [rbp+1F0h+var_250]
0x180021b0a  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180021b0e  jz      short loc_180021B29
0x180021b10  mov     r9d, ebx
0x180021b13  mov     r8d, r12d
0x180021b16  lea     rdx, aPort1devicenum; "Port1DeviceNumber"
0x180021b1d  lea     rcx, [rbp+1F0h+var_120]
0x180021b24  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021b29  mov     r14, [rbp+1F0h+var_248]
0x180021b2d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180021b31  jz      short loc_180021B4C
0x180021b33  mov     r9d, ebx
0x180021b36  mov     r8d, r14d
0x180021b39  lea     rdx, aPort1functionn; "Port1FunctionNumber"
0x180021b40  lea     rcx, [rbp+1F0h+var_120]
0x180021b47  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180021b4c  mov     r13, [rbp+1F0h+var_240]
0x180021b50  mov     rax, [rbp+1F0h+var_238]
0x180021b54  mov     [rbp+1F0h+var_268], rax
0x180021b58  mov     rcx, [rbp+1F0h+var_230]
0x180021b5c  mov     [rbp+1F0h+var_108], rcx
0x180021b63  mov     rdx, [rbp+1F0h+var_228]
0x180021b67  mov     [rbp+1F0h+var_270], rdx
0x180021b6b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180021b6f  jz      loc_180021C28
0x180021b75  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180021b79  jz      loc_180021C28
0x180021b7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021b83  jz      loc_180021C28
0x180021b89  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021b8d  jz      loc_180021C28
0x180021b93  mov     qword ptr [rsp+2F0h+var_2D0], 0
0x180021b9c  mov     r9d, 3
0x180021ba2  lea     r8, aNetworkinterfa_2; "NetworkInterface"
  ... truncated ...
```
