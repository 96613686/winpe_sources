# NetSetupSvcDeviceManager::InstallNetworkInterfaces(NetSetup2::NonOwningTransaction &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,void *)

- ea: `0x18001f2e4`
- end: `0x18001f97d`
- name: `?InstallNetworkInterfaces@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z`
- size: `1689`
- prototype: `LSTATUS __fastcall(HKEY, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `36`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18001f258`
- `0x18002266c`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x180008d94`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d974`
- `0x18000d9b4`
- `0x18000de84`
- `0x1800174fc`
- `0x180018490`
- `0x18001aa84`
- `0x18001b168`
- `0x18001b414`
- `0x18001d258`
- `0x18001d780`
- `0x18001e3a8`
- `0x18001e734`
- `0x18001ea44`
- `0x18001f1cc`
- `0x18001f2e4`
- `0x1800207bc`
- `0x180021650`
- `0x180024cdc`
- `0x180026d3c`
- `0x18002729c`
- `0x1800275e4`
- `0x180027d2c`
- `0x180028334`
- `0x1800285cc`
- `0x1800286d8`
- `0x180028dc4`
- `0x18002923c`
- `0x180029840`
- `0x18002bba8`
- `0x18002d8e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f748`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f748`

## pseudocode

```c
LSTATUS __fastcall NetSetupSvcDeviceManager::InstallNetworkInterfaces(HKEY a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // r15
  __int64 v5; // r14
  __int64 v6; // rsi
  HKEY v7; // r13
  const wchar_t *v8; // rax
  char v9; // bl
  __int64 ValueString; // r8
  char v11; // r12
  __int64 v12; // rax
  char v13; // bl
  __int64 v14; // rax
  __int64 v15; // r8
  char v16; // bl
  __int64 v17; // rax
  unsigned int ValueDword; // eax
  _QWORD *v20; // [rsp+30h] [rbp-2D8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-2D0h]
  __int64 v22; // [rsp+40h] [rbp-2C8h]
  _BYTE pExceptionObject[208]; // [rsp+48h] [rbp-2C0h] BYREF
  _BYTE v24[208]; // [rsp+118h] [rbp-1F0h] BYREF
  HKEY v25; // [rsp+1E8h] [rbp-120h] BYREF
  HKEY v26; // [rsp+1F0h] [rbp-118h] BYREF
  __int128 v27; // [rsp+1F8h] [rbp-110h] BYREF
  _QWORD v28[3]; // [rsp+208h] [rbp-100h] BYREF
  __int128 v29; // [rsp+220h] [rbp-E8h] BYREF
  __int128 *v30; // [rsp+230h] [rbp-D8h] BYREF
  _QWORD v31[4]; // [rsp+238h] [rbp-D0h] BYREF
  _BYTE v32[8]; // [rsp+258h] [rbp-B0h] BYREF
  _BYTE v33[16]; // [rsp+260h] [rbp-A8h] BYREF
  _BYTE v34[8]; // [rsp+270h] [rbp-98h] BYREF
  _QWORD v35[4]; // [rsp+278h] [rbp-90h] BYREF
  __int64 v36; // [rsp+298h] [rbp-70h]
  _BYTE v37[32]; // [rsp+2A0h] [rbp-68h] BYREF

  v4 = (__int64)a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  v26 = a1;
  v21 = a2;
  v22 = a3;
  v20 = a4;
  v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  NetSetupDevice::NetSetupDevice((NetSetupDevice *)v33, v8, 0);
  NetSetupDevice::OpenSoftwareKey(v33, &v25, 3, v4);
  if ( RegistryKey::ValueExists((RegistryKey *)&v25, L"RetiredNetCfgInstanceId") )
  {
    if ( RegistryKey::ValueExists((RegistryKey *)&v25, L"NetSetupAnticipatedInstanceId") )
    {
      RegistryKey::GetValueString(&v25, (__int64)&v30, L"RetiredNetCfgInstanceId", 0);
      v29 = 0;
      if ( (unsigned __int8)GuidFromString(&v30, &v29) )
      {
        NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(v6, v34, &v29);
        v9 = v36;
        if ( (_BYTE)v36 )
        {
          try
          {
            NetSetup2::ActiveObject::Delete((NetSetup2::ActiveObject *)v34);
          }
          catch ( ... )
          {
            v9 = v36;
            v7 = v26;
            v6 = v21;
            v5 = v22;
            v4 = (__int64)v20;
          }
        }
        if ( v9 )
          std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v35);
      }
    }
    else
    {
      ValueString = RegistryKey::GetValueString(&v25, (__int64)&v30, L"RetiredNetCfgInstanceId", 0);
      RegistryKey::SetValue(&v25, L"NetSetupAnticipatedInstanceId", ValueString);
    }
    std::wstring::_Tidy_deallocate((__int64)&v30);
    RegistryKey::DeleteValue(&v25, L"RetiredNetCfgInstanceId");
  }
  NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate((NetSetup2::NetworkInterfaceTemplate *)v28);
  ReadNetworkInterfacePropertiesFromDriver(v6, v5, v4, v28);
  v27 = 0;
  v11 = 1;
  if ( RegistryKey::ValueExists((RegistryKey *)&v25, L"NetSetupAnticipatedInstanceId") )
  {
    v12 = RegistryKey::GetValueString(&v25, (__int64)&v30, L"NetSetupAnticipatedInstanceId", 0);
    v13 = GuidFromString(v12, &v27);
    std::wstring::_Tidy_deallocate((__int64)&v30);
    if ( v13 )
    {
      NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(v6, &v30, &v27);
      if ( v32[0] )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF__guid_S(*(_QWORD *)(v15 + 16), 59, v15, (unsigned int)&v27, v14);
        }
        try
        {
          v20 = v28;
          NetSetup2::ActiveObject::ActiveObjectTmpl_NetSetup2::NetworkInterface_::BatchPropertyChanges__lambda_99e8c98aa6ea81d16ab1784247d7da7a___(
            v32,
            &v20,
            0xAAAAAAAAAAAAAAABuLL * ((__int64)(v28[1] - v28[0]) >> 4) + 6);
          v11 = 0;
        }
        catch ( ... )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF__guid_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              60,
              WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
              &v27);
          NetSetup2::ActiveObject::Delete((NetSetup2::ActiveObject *)&v30);
          RegistryKey::DeleteValue(&v25, L"NetSetupAnticipatedInstanceId");
          throw;
        }
      }
      else
      {
        NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(
          (__int64)v28,
          &NETSETUPPKEY_Object_Id,
          (__int64)&v27);
      }
      if ( v32[0] )
        std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v31);
    }
    RegistryKey::DeleteValue(&v25, L"NetSetupAnticipatedInstanceId");
  }
  else if ( RegistryKey::ValueExists((RegistryKey *)&v25, L"SuggestedInstanceId") )
  {
    RegistryKey::GetValueBlob(&v25, &v30, L"SuggestedInstanceId", 0, 0);
    if ( v31[0] - (_QWORD)v30 == 16 )
    {
      v29 = *v30;
      v16 = *(_BYTE *)(NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(v6, v34, &v29) + 40);
      if ( (_BYTE)v36 )
        std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v35);
      if ( !v16 )
        NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(
          (__int64)v28,
          &NETSETUPPKEY_Object_Id,
          (__int64)&v29);
    }
    RegistryKey::DeleteValue(&v25, L"SuggestedInstanceId");
    std::vector<unsigned char>::_Tidy((__int64)&v30);
  }
  std::wstring::wstring((__int64)v37);
  if ( (unsigned __int8)NetSetupDevice::GetStringProperty(v33, &DEVPKEY_Device_Service, v37) )
  {
    v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    if ( !(unsigned int)_o__wcsicmp(v17, L"netvsc") )
      NetSetupFindPropertiesFromVmHost(v6, v5, v28);
  }
  LODWORD(v26) = 0;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    (__int64)v28,
    (__int128 *)NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber,
    (__int64)&v26);
  if ( v11 )
    v27 = *(_OWORD *)CreateNewNetworkInterface(&v29, v6, v28, v5);
  FinalizeNewlyCreatedNetworkInterface(v6, &v25, &v27);
  if ( RegistryKey::ValueExists((RegistryKey *)&v25, L"NumberOfNetworkInterfaces") )
  {
    RegistryKey::TryOpenSubKey(&v25, &v26, L"NetworkInterface", 1, v4);
    if ( !v26 || !RegistryKey::ValueExists((RegistryKey *)&v26, L"*IfConnectorPresent") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
          "networkInterfaceKey && networkInterfaceKey.ValueExists(L\"*IfConnectorPresent\")");
      HResultException::HResultException((HResultException *)v24, -2147024809);
      throw (HResultException *)v24;
    }
    ValueDword = RegistryKey::GetValueDword(&v25, L"NumberOfNetworkInterfaces", 0, 0);
    if ( !ValueDword || ValueDword > *((_DWORD *)v7 + 10) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
          *((unsigned int *)v7 + 10),
          ValueDword);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
      throw (HResultException *)pExceptionObject;
    }
    CreateNetworkInterfaces(v6, v5, (unsigned int)&v25, ValueDword, v4);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
  }
  std::wstring::_Tidy_deallocate((__int64)v37);
  NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate((NetSetup2::ObjectCreationTemplate *)v28);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
}

```

## disassembly

```asm
0x18001f2e4  push    rbx
0x18001f2e6  push    rsi
0x18001f2e7  push    r12
0x18001f2e9  push    r13
0x18001f2eb  push    r14
0x18001f2ed  push    r15
0x18001f2ef  sub     rsp, 2D8h
0x18001f2f6  mov     rax, cs:__security_cookie
0x18001f2fd  xor     rax, rsp
0x18001f300  mov     [rsp+308h+var_48], rax
0x18001f308  mov     r15, r9
0x18001f30b  mov     r14, r8
0x18001f30e  mov     rsi, rdx
0x18001f311  mov     r13, rcx
0x18001f314  mov     [rsp+308h+var_118], rcx
0x18001f31c  mov     [rsp+308h+var_2D0], rdx
0x18001f321  mov     [rsp+308h+var_2C8], r8
0x18001f326  mov     [rsp+308h+var_2D8], r9
0x18001f32b  mov     rcx, r8
0x18001f32e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f333  xor     r8d, r8d; bool
0x18001f336  mov     rdx, rax; wchar_t *
0x18001f339  lea     rcx, [rsp+308h+var_A8]; this
0x18001f341  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x18001f346  mov     r9, r15
0x18001f349  mov     r8d, 3
0x18001f34f  lea     rdx, [rsp+308h+var_120]
0x18001f357  lea     rcx, [rsp+308h+var_A8]
0x18001f35f  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x18001f364  nop
0x18001f365  lea     rdx, aRetirednetcfgi; "RetiredNetCfgInstanceId"
0x18001f36c  lea     rcx, [rsp+308h+var_120]; this
0x18001f374  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001f379  test    al, al
0x18001f37b  jz      loc_18001F488
0x18001f381  lea     rdx, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001f388  lea     rcx, [rsp+308h+var_120]; this
0x18001f390  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001f395  xor     r9d, r9d
0x18001f398  lea     r8, aRetirednetcfgi; "RetiredNetCfgInstanceId"
0x18001f39f  lea     rdx, [rsp+308h+var_D8]
0x18001f3a7  lea     rcx, [rsp+308h+var_120]
0x18001f3af  test    al, al
0x18001f3b1  jz      loc_18001F449
0x18001f3b7  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001f3bc  nop
0x18001f3bd  xorps   xmm0, xmm0
0x18001f3c0  movups  [rsp+308h+var_E8], xmm0
0x18001f3c8  lea     rdx, [rsp+308h+var_E8]
0x18001f3d0  lea     rcx, [rsp+308h+var_D8]
0x18001f3d8  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18001f3dd  test    al, al
0x18001f3df  jz      short loc_18001F447
0x18001f3e1  lea     r8, [rsp+308h+var_E8]
0x18001f3e9  lea     rdx, [rsp+308h+var_98]
0x18001f3f1  mov     rcx, rsi
0x18001f3f4  call    ?TryGetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AV?$Optional@VNetworkInterface@NetSetup2@@@23@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(_GUID const &)
0x18001f3f9  nop
0x18001f3fa  mov     rbx, [rsp+308h+var_70]
0x18001f402  test    bl, bl
0x18001f404  jz      short loc_18001F435
0x18001f406  lea     rcx, [rsp+308h+var_98]; this
0x18001f40e  call    ?Delete@ActiveObject@NetSetup2@@QEAAXXZ; NetSetup2::ActiveObject::Delete(void)
0x18001f413  nop
0x18001f414  jmp     short loc_18001F435
0x18001f416  mov     rbx, [rsp+308h+var_70]
0x18001f41e  mov     r13, [rsp+308h+var_118]
0x18001f426  mov     rsi, [rsp+308h+var_2D0]
0x18001f42b  mov     r14, [rsp+308h+var_2C8]
0x18001f430  mov     r15, [rsp+308h+var_2D8]
0x18001f435  test    bl, bl
0x18001f437  jz      short loc_18001F447
0x18001f439  lea     rcx, [rsp+308h+var_90]
0x18001f441  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001f446  nop
0x18001f447  jmp     short loc_18001F467
0x18001f449  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001f44e  nop
0x18001f44f  mov     r8, rax
0x18001f452  lea     rdx, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001f459  lea     rcx, [rsp+308h+var_120]
0x18001f461  call    ?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::SetValue(wchar_t const *,std::wstring const &)
0x18001f466  nop
0x18001f467  lea     rcx, [rsp+308h+var_D8]
0x18001f46f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f474  lea     rdx, aRetirednetcfgi; "RetiredNetCfgInstanceId"
0x18001f47b  lea     rcx, [rsp+308h+var_120]; this
0x18001f483  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x18001f488  lea     rcx, [rsp+308h+var_100]; this
0x18001f490  call    ??0NetworkInterfaceTemplate@NetSetup2@@QEAA@XZ; NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate(void)
0x18001f495  nop
0x18001f496  lea     r9, [rsp+308h+var_100]
0x18001f49e  mov     r8, r15
0x18001f4a1  mov     rdx, r14
0x18001f4a4  mov     rcx, rsi
0x18001f4a7  call    ReadNetworkInterfacePropertiesFromDriver
0x18001f4ac  xorps   xmm0, xmm0
0x18001f4af  movups  [rsp+308h+var_110], xmm0
0x18001f4b7  mov     r12b, 1
0x18001f4ba  lea     rdx, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001f4c1  lea     rcx, [rsp+308h+var_120]; this
0x18001f4c9  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001f4ce  lea     rcx, [rsp+308h+var_120]; this
0x18001f4d6  test    al, al
0x18001f4d8  jz      loc_18001F627
0x18001f4de  xor     r9d, r9d
0x18001f4e1  lea     r8, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001f4e8  lea     rdx, [rsp+308h+var_D8]
0x18001f4f0  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001f4f5  lea     rdx, [rsp+308h+var_110]
0x18001f4fd  mov     rcx, rax
0x18001f500  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18001f505  mov     bl, al
0x18001f507  lea     rcx, [rsp+308h+var_D8]
0x18001f50f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f514  test    bl, bl
0x18001f516  jz      loc_18001F607
0x18001f51c  lea     r8, [rsp+308h+var_110]
0x18001f524  lea     rdx, [rsp+308h+var_D8]
0x18001f52c  mov     rcx, rsi
0x18001f52f  call    ?TryGetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AV?$Optional@VNetworkInterface@NetSetup2@@@23@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(_GUID const &)
0x18001f534  nop
0x18001f535  cmp     [rsp+308h+var_B0], 0
0x18001f53d  jz      loc_18001F5CB
0x18001f543  lea     rbx, WPP_GLOBAL_Control
0x18001f54a  mov     r8, cs:WPP_GLOBAL_Control
0x18001f551  cmp     r8, rbx
0x18001f554  jz      short loc_18001F581
0x18001f556  cmp     byte ptr [r8+19h], 4
0x18001f55b  jb      short loc_18001F581
0x18001f55d  mov     rcx, r14
0x18001f560  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f565  mov     edx, 3Bh ; ';'
0x18001f56a  mov     [rsp+308h+var_2E8], rax
0x18001f56f  lea     r9, [rsp+308h+var_110]
0x18001f577  mov     rcx, [r8+10h]
0x18001f57b  call    WPP_SF__guid_S
0x18001f580  nop
0x18001f581  lea     rax, [rsp+308h+var_100]
0x18001f589  mov     [rsp+308h+var_2D8], rax
0x18001f58e  mov     r8, [rsp+308h+var_F8]
0x18001f596  sub     r8, [rsp+308h+var_100]
0x18001f59e  sar     r8, 4
0x18001f5a2  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001f5ac  imul    r8, rax
0x18001f5b0  add     r8, 6
0x18001f5b4  lea     rdx, [rsp+308h+var_2D8]
0x18001f5b9  lea     rcx, [rsp+308h+var_B0]
0x18001f5c1  call    NetSetup2__ActiveObject__ActiveObjectTmpl_NetSetup2__NetworkInterface___BatchPropertyChanges__lambda_99e8c98aa6ea81d16ab1784247d7da7a___
0x18001f5c6  xor     r12b, r12b
0x18001f5c9  jmp     short loc_18001F5EE
0x18001f5cb  lea     r8, [rsp+308h+var_110]
0x18001f5d3  lea     rdx, NETSETUPPKEY_Object_Id
0x18001f5da  lea     rcx, [rsp+308h+var_100]
0x18001f5e2  call    ??$SetPropertyToValue@$0N@U_GUID@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(_NETSETUPPROPKEY const &,_GUID const &)
0x18001f5e7  lea     rbx, WPP_GLOBAL_Control
0x18001f5ee  cmp     [rsp+308h+var_B0], 0
0x18001f5f6  jz      short loc_18001F60E
0x18001f5f8  lea     rcx, [rsp+308h+var_D0]
0x18001f600  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001f605  jmp     short loc_18001F60E
0x18001f607  lea     rbx, WPP_GLOBAL_Control
0x18001f60e  lea     rdx, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001f615  lea     rcx, [rsp+308h+var_120]; this
0x18001f61d  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x18001f622  jmp     loc_18001F703
0x18001f627  lea     rdx, aSuggestedinsta; "SuggestedInstanceId"
0x18001f62e  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001f633  test    al, al
0x18001f635  jz      loc_18001F6FC
0x18001f63b  mov     dword ptr [rsp+308h+var_2E8], 0
0x18001f643  xor     r9d, r9d
0x18001f646  lea     r8, aSuggestedinsta; "SuggestedInstanceId"
0x18001f64d  lea     rdx, [rsp+308h+var_D8]
0x18001f655  lea     rcx, [rsp+308h+var_120]
0x18001f65d  call    ?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)
0x18001f662  nop
0x18001f663  mov     rax, [rsp+308h+var_D0]
0x18001f66b  mov     rcx, [rsp+308h+var_D8]
0x18001f673  sub     rax, rcx
0x18001f676  cmp     rax, 10h
0x18001f67a  jnz     short loc_18001F6DA
0x18001f67c  movups  xmm0, xmmword ptr [rcx]
0x18001f67f  movdqu  [rsp+308h+var_E8], xmm0
0x18001f688  lea     r8, [rsp+308h+var_E8]
0x18001f690  lea     rdx, [rsp+308h+var_98]
0x18001f698  mov     rcx, rsi
0x18001f69b  call    ?TryGetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AV?$Optional@VNetworkInterface@NetSetup2@@@23@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(_GUID const &)
0x18001f6a0  mov     bl, [rax+28h]
0x18001f6a3  cmp     byte ptr [rsp+308h+var_70], 0
0x18001f6ab  jz      short loc_18001F6BA
0x18001f6ad  lea     rcx, [rsp+308h+var_90]
0x18001f6b5  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001f6ba  test    bl, bl
0x18001f6bc  jnz     short loc_18001F6DA
0x18001f6be  lea     r8, [rsp+308h+var_E8]
0x18001f6c6  lea     rdx, NETSETUPPKEY_Object_Id
0x18001f6cd  lea     rcx, [rsp+308h+var_100]
0x18001f6d5  call    ??$SetPropertyToValue@$0N@U_GUID@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(_NETSETUPPROPKEY const &,_GUID const &)
0x18001f6da  lea     rdx, aSuggestedinsta; "SuggestedInstanceId"
0x18001f6e1  lea     rcx, [rsp+308h+var_120]; this
0x18001f6e9  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x18001f6ee  nop
0x18001f6ef  lea     rcx, [rsp+308h+var_D8]
0x18001f6f7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001f6fc  lea     rbx, WPP_GLOBAL_Control
0x18001f703  lea     rcx, [rsp+308h+var_68]
0x18001f70b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f710  nop
0x18001f711  lea     r8, [rsp+308h+var_68]
0x18001f719  lea     rdx, DEVPKEY_Device_Service
0x18001f720  lea     rcx, [rsp+308h+var_A8]
0x18001f728  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x18001f72d  test    al, al
0x18001f72f  jz      short loc_18001F765
0x18001f731  lea     rcx, [rsp+308h+var_68]
0x18001f739  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f73e  mov     rcx, rax
0x18001f741  lea     rdx, aNetvsc; "netvsc"
0x18001f748  call    cs:__imp__o__wcsicmp
0x18001f74e  test    eax, eax
0x18001f750  jnz     short loc_18001F765
0x18001f752  lea     r8, [rsp+308h+var_100]
0x18001f75a  mov     rdx, r14
0x18001f75d  mov     rcx, rsi
0x18001f760  call    NetSetupFindPropertiesFromVmHost
0x18001f765  mov     dword ptr [rsp+308h+var_118], 0
0x18001f770  lea     r8, [rsp+308h+var_118]
0x18001f778  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber
0x18001f77f  lea     rcx, [rsp+308h+var_100]
0x18001f787  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x18001f78c  test    r12b, r12b
0x18001f78f  jz      short loc_18001F7B8
0x18001f791  mov     r9, r14
0x18001f794  lea     r8, [rsp+308h+var_100]
0x18001f79c  mov     rdx, rsi
0x18001f79f  lea     rcx, [rsp+308h+var_E8]
0x18001f7a7  call    CreateNewNetworkInterface
0x18001f7ac  movups  xmm0, xmmword ptr [rax]
0x18001f7af  movdqu  [rsp+308h+var_110], xmm0
0x18001f7b8  lea     r8, [rsp+308h+var_110]
0x18001f7c0  lea     rdx, [rsp+308h+var_120]
0x18001f7c8  mov     rcx, rsi
0x18001f7cb  call    FinalizeNewlyCreatedNetworkInterface
0x18001f7d0  lea     rdx, aNumberofnetwor; "NumberOfNetworkInterfaces"
0x18001f7d7  lea     rcx, [rsp+308h+var_120]; this
0x18001f7df  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001f7e4  test    al, al
0x18001f7e6  jz      loc_18001F88D
0x18001f7ec  mov     [rsp+308h+var_2E8], r15
0x18001f7f1  mov     r9d, 1
0x18001f7f7  lea     r8, aNetworkinterfa_2; "NetworkInterface"
0x18001f7fe  lea     rdx, [rsp+308h+var_118]
0x18001f806  lea     rcx, [rsp+308h+var_120]
0x18001f80e  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18001f813  nop
0x18001f814  cmp     [rsp+308h+var_118], 0
0x18001f81d  jz      loc_18001F928
0x18001f823  lea     rdx, aIfconnectorpre; "*IfConnectorPresent"
0x18001f82a  lea     rcx, [rsp+308h+var_118]; this
0x18001f832  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001f837  test    al, al
0x18001f839  jz      loc_18001F928
0x18001f83f  xor     r9d, r9d
0x18001f842  xor     r8d, r8d
0x18001f845  lea     rdx, aNumberofnetwor; "NumberOfNetworkInterfaces"
0x18001f84c  lea     rcx, [rsp+308h+var_120]
0x18001f854  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18001f859  test    eax, eax
0x18001f85b  jz      short loc_18001F8D8
0x18001f85d  cmp     eax, [r13+28h]
0x18001f861  ja      short loc_18001F8D8
0x18001f863  mov     r9d, eax
0x18001f866  mov     [rsp+308h+var_2E8], r15
0x18001f86b  lea     r8, [rsp+308h+var_120]
0x18001f873  mov     rdx, r14
0x18001f876  mov     rcx, rsi
0x18001f879  call    CreateNetworkInterfaces
0x18001f87e  nop
0x18001f87f  lea     rcx, [rsp+308h+var_118]
0x18001f887  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f88c  nop
0x18001f88d  lea     rcx, [rsp+308h+var_68]
0x18001f895  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f89a  nop
0x18001f89b  lea     rcx, [rsp+308h+var_100]; this
0x18001f8a3  call    ??1ObjectCreationTemplate@NetSetup2@@QEAA@XZ; NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(void)
0x18001f8a8  nop
0x18001f8a9  lea     rcx, [rsp+308h+var_120]
0x18001f8b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f8b6  mov     rcx, [rsp+308h+var_48]
0x18001f8be  xor     rcx, rsp; StackCookie
0x18001f8c1  call    __security_check_cookie
0x18001f8c6  add     rsp, 2D8h
0x18001f8cd  pop     r15
0x18001f8cf  pop     r14
0x18001f8d1  pop     r13
0x18001f8d3  pop     r12
0x18001f8d5  pop     rsi
0x18001f8d6  pop     rbx
  ... truncated ...
```
