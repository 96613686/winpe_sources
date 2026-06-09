# GetDevicesNeedingWork

- ea: `0x18001eb14`
- end: `0x18001f1c6`
- name: `GetDevicesNeedingWork`
- size: `1714`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022fd4`

## callees

- `0x180001b50`
- `0x180001d2c`
- `0x1800027c0`
- `0x180006e34`
- `0x180007d80`
- `0x180008380`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d974`
- `0x18000d9b4`
- `0x18000df60`
- `0x1800182b0`
- `0x18001a7dc`
- `0x18001ac78`
- `0x18001b598`
- `0x18001bc00`
- `0x18001ca3c`
- `0x18001ca70`
- `0x18001d080`
- `0x18001d0ac`
- `0x18001d0d8`
- `0x18001d3b4`
- `0x18001d444`
- `0x18001d6f4`
- `0x18001e12c`
- `0x18001e828`
- `0x18001eb14`
- `0x18001f1cc`
- `0x18002459c`
- `0x180026958`
- `0x180027560`
- `0x1800275e4`
- `0x180027d2c`
- `0x1800285cc`
- `0x1800286d8`
- `0x180029528`
- `0x1800295e0`
- `0x180029840`
- `0x18002c728`
- `0x18002cab8`

## string_xrefs

- `0x18001ee05`: `AwaitingNetCfgInstall`
- `0x18001f02e`: `NdisUpdatedNetworkInterface`
- `0x18001f068`: `DriverUpdated`
- `0x18001f082`: `DriverUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall GetDevicesNeedingWork(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 *v7; // r15
  __int64 v10; // r8
  NetSetup2::ActiveObject **v11; // rbx
  __int64 v12; // rdi
  char v13; // r14
  __int64 String; // rax
  RegistryKey *v15; // rax
  __int64 *v16; // rdi
  __int64 *v17; // rsi
  __int64 v18; // r15
  bool v19; // bl
  __int64 v20; // rax
  __int64 v21; // r10
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 ValueString; // rax
  char v25; // bl
  __int64 v26; // rax
  char v27; // bl
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 *v38; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h]
  __int64 v41; // [rsp+58h] [rbp-A8h]
  __int64 v42; // [rsp+60h] [rbp-A0h]
  _QWORD v43[2]; // [rsp+70h] [rbp-90h] BYREF
  char v44[16]; // [rsp+80h] [rbp-80h] BYREF
  char v45; // [rsp+90h] [rbp-70h] BYREF
  char v46[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v47[16]; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v48; // [rsp+C0h] [rbp-40h] BYREF
  HKEY v49; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v50; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v51; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v52; // [rsp+F0h] [rbp-10h] BYREF
  char v53; // [rsp+100h] [rbp+0h]
  __int64 v54; // [rsp+110h] [rbp+10h] BYREF
  __int64 v55; // [rsp+118h] [rbp+18h]
  _BYTE v56[16]; // [rsp+120h] [rbp+20h] BYREF
  char v57[32]; // [rsp+130h] [rbp+30h] BYREF
  NetSetup2::ActiveObject **v58; // [rsp+150h] [rbp+50h] BYREF
  NetSetup2::ActiveObject **v59; // [rsp+158h] [rbp+58h]
  __int64 v60; // [rsp+160h] [rbp+60h]
  _BYTE v61[16]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v62[16]; // [rsp+178h] [rbp+78h] BYREF
  __int128 v63; // [rsp+188h] [rbp+88h] BYREF
  int v64; // [rsp+19Ch] [rbp+9Ch]
  char v65[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  NetSetupDevice *v66; // [rsp+1C0h] [rbp+C0h] BYREF
  NetSetupDevice *v67; // [rsp+1C8h] [rbp+C8h]
  __int128 v68; // [rsp+220h] [rbp+120h] BYREF
  int v69; // [rsp+230h] [rbp+130h]
  __int64 v70; // [rsp+234h] [rbp+134h]
  int v71; // [rsp+23Ch] [rbp+13Ch]
  __int128 v72; // [rsp+240h] [rbp+140h]
  int v73; // [rsp+250h] [rbp+150h]
  __int64 v74; // [rsp+254h] [rbp+154h]
  int v75; // [rsp+25Ch] [rbp+15Ch]

  v7 = a4;
  v38 = a4;
  *(_QWORD *)&v50 = a3;
  v41 = a5;
  v40 = a6;
  v42 = a7;
  std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(v62);
  std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(v61);
  std::set<std::wstring>::set<std::wstring>(&v54);
  v68 = NETSETUPPKEY_Interface_PnpInstance;
  v69 = 50;
  v70 = 0;
  v71 = 0;
  v72 = NETSETUPPKEY_Interface_RemoveInterfaceWhenPnpDeviceRemoved;
  v73 = 140;
  v74 = 0;
  v75 = 0;
  NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(
    a1,
    (__int64 *)&v58,
    v10,
    (__int64)&v68,
    2,
    0,
    0);
  v11 = v58;
  v12 = (__int64)v59;
  v13 = 1;
  if ( v58 != v59 )
  {
    do
    {
      NetSetup2::ActiveObject::GetProperty(
        *v11,
        (const struct _NETSETUPPROPKEY *)&v63,
        (unsigned int)&NETSETUPPKEY_Interface_PnpInstance);
      if ( v64 )
      {
        String = NetSetup2::Property::GetString(&v63, v56);
        v53 = 1;
        v51 = 0;
        v52 = 0;
        v51 = *(_OWORD *)String;
        v52 = *(_OWORD *)(String + 16);
        *(_QWORD *)(String + 16) = 0;
        *(_QWORD *)(String + 24) = 7;
        *(_WORD *)String = 0;
        std::wstring::_Tidy_deallocate((__int64)v56);
      }
      else
      {
        v53 = 0;
      }
      std::vector<unsigned char>::_Tidy((__int64)v65);
      if ( v53 )
      {
        if ( NetSetup2::NetworkInterface::get_RemoveInterfaceWhenPnpDeviceRemoved(*v11) )
        {
          v23 = std::pair<_GUID,std::wstring>::pair<_GUID,std::wstring>(v56, (char *)*v11 + 20, &v51);
          std::_Tree<std::_Tmap_traits<_GUID,std::wstring,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::emplace<std::pair<_GUID,std::wstring>>(
            v62,
            v43,
            v23);
          std::wstring::_Tidy_deallocate((__int64)v57);
        }
        if ( v53 )
          std::wstring::_Tidy_deallocate((__int64)&v51);
      }
      ++v11;
    }
    while ( v11 != (NetSetup2::ActiveObject **)v12 );
    v12 = (__int64)v59;
    v11 = v58;
  }
  if ( v11 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>((__int64)v11, v12);
    std::_Deallocate<16>(v58, (v60 - (_QWORD)v58) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  NetDevices::NetDevices((NetDevices *)&v66);
  v15 = RegistryKey::RegistryKey((RegistryKey *)&v39, HKEY_LOCAL_MACHINE);
  RegistryKey::TryOpenSubKey(v15, &v49, L"System\\CurrentControlSet\\Control\\NetworkSetup2\\NetworkReset", 1, 0);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
  if ( !v49
    || !RegistryKey::ValueExists((RegistryKey *)&v49, L"ResetInProgress")
    || !(unsigned int)RegistryKey::GetValueDword(&v49, L"ResetInProgress", 0, 0) )
  {
    v13 = 0;
  }
  v16 = (__int64 *)v66;
  v17 = (__int64 *)v67;
  if ( v66 != v67 )
  {
    v18 = v50;
    while ( 1 )
    {
      if ( !NetSetupDevice::IsAvailable((NetSetupDevice *)v16)
        || !NetSetupDevice::IsPnpSoftwareKeyAvailable((NetSetupDevice *)v16) )
      {
        goto LABEL_48;
      }
      std::wstring::wstring((__int64)v56, v16[1]);
      v50 = 0;
      NetSetupDevice::OpenSoftwareKey((NetSetupDevice *)v16, (RegistryKey *)&v48, 3u, a2);
      v19 = RegistryKey::ValueExists((RegistryKey *)&v48, L"NetCfgInstanceId");
      if ( v19 || RegistryKey::GetValueBoolean((__int64)&v48, (__int64)L"AwaitingNetCfgInstall") )
      {
        if ( v19 )
        {
          ValueString = RegistryKey::GetValueString(&v48, (__int64)&v63, L"NetCfgInstanceId", 0);
          v25 = GuidFromString(ValueString, &v50);
          std::wstring::_Tidy_deallocate((__int64)&v63);
          if ( !v25 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_47;
            v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
            v22 = 16;
LABEL_34:
            WPP_SF_S(*(_QWORD *)(v21 + 16), v22, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v20);
            goto LABEL_47;
          }
          if ( RegistryKey::ValueExists((RegistryKey *)&v48, L"RetiredNetCfgInstanceId") )
          {
            v63 = 0;
            v26 = RegistryKey::GetValueString(&v48, (__int64)&v51, L"RetiredNetCfgInstanceId", 0);
            v27 = GuidFromString(v26, &v63);
            std::wstring::_Tidy_deallocate((__int64)&v51);
            if ( v27 )
            {
              std::_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>::_Emplace<std::wstring &,_GUID &,_GUID &>(
                v40,
                (unsigned int)&v45,
                (unsigned int)v56,
                (unsigned int)&v63,
                (__int64)&v50);
              goto LABEL_47;
            }
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_47;
            v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
            v22 = 17;
            goto LABEL_34;
          }
          v28 = std::pair<_GUID,std::wstring>::pair<_GUID,std::wstring>(&v51, &v50, v56);
          std::_Tree<std::_Tmap_traits<_GUID,std::wstring,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::emplace<std::pair<_GUID,std::wstring>>(
            v61,
            v46,
            v28);
          std::wstring::_Tidy_deallocate((__int64)&v52);
          v43[0] = v61;
          v43[1] = v56;
          ForEachAuxiliaryInterface__lambda_d1fa83141937cf0ec8e7b733387754a4_(a1, v56, a2, v43);
          if ( RegistryKey::ValueExists((RegistryKey *)&v48, L"NdisUpdatedNetworkInterface") )
          {
            v29 = std::pair<_GUID,std::wstring>::pair<_GUID,std::wstring>(&v51, &v50, v56);
            std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::emplace<std::pair<_GUID,std::wstring>>(
              v41,
              v47,
              v29);
          }
          else
          {
            if ( !RegistryKey::ValueExists((RegistryKey *)&v48, L"DriverUpdated")
              || !(unsigned int)RegistryKey::GetValueDword(&v48, L"DriverUpdated", 0, 0) )
            {
              goto LABEL_47;
            }
            v30 = std::pair<_GUID,std::wstring>::pair<_GUID,std::wstring>(&v51, &v50, v56);
            std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::emplace<std::pair<_GUID,std::wstring>>(
              v42,
              &v58,
              v30);
          }
          std::wstring::_Tidy_deallocate((__int64)&v52);
        }
      }
      else
      {
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_47;
          v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          v22 = 15;
          goto LABEL_34;
        }
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
          v18,
          v44,
          v56);
      }
LABEL_47:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      std::wstring::_Tidy_deallocate((__int64)v56);
LABEL_48:
      v16 += 2;
      if ( v16 == v17 )
      {
        v7 = v38;
        break;
      }
    }
  }
  ComputeSetDifferences(v61, v62, &v54, v7);
  FilterDevicesToUninstallList(a1, v7);
  if ( v55
    && (unsigned int)dword_180049000 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180049000, 0x400000000000LL, v31) )
  {
    LODWORD(v48) = v55;
    v38 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v32,
      (int)&unk_180041A48,
      v33,
      v34,
      &v38,
      (__int64)&v48);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v49);
  NetDevices::~NetDevices((NetDevices *)&v66);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
  std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>(
    v61,
    v35);
  return std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>(
           v62,
           v36);
}

```

## disassembly

```asm
0x18001eb14  push    rbp
0x18001eb16  push    rbx
0x18001eb17  push    rsi
0x18001eb18  push    rdi
0x18001eb19  push    r12
0x18001eb1b  push    r13
0x18001eb1d  push    r14
0x18001eb1f  push    r15
0x18001eb21  lea     rbp, [rsp-178h]
0x18001eb29  sub     rsp, 278h
0x18001eb30  mov     rax, cs:__security_cookie
0x18001eb37  xor     rax, rsp
0x18001eb3a  mov     [rbp+1B0h+var_50], rax
0x18001eb41  mov     r15, r9
0x18001eb44  mov     [rsp+2B0h+var_270], r9
0x18001eb49  mov     qword ptr [rbp+1B0h+var_1E0], r8
0x18001eb4d  mov     r13, rdx
0x18001eb50  mov     r12, rcx
0x18001eb53  mov     rax, [rbp+1B0h+arg_20]
0x18001eb5a  mov     [rsp+2B0h+var_258], rax
0x18001eb5f  mov     rax, [rbp+1B0h+arg_28]
0x18001eb66  mov     [rsp+2B0h+var_260], rax
0x18001eb6b  mov     rax, [rbp+1B0h+arg_30]
0x18001eb72  mov     [rsp+2B0h+var_250], rax
0x18001eb77  xor     esi, esi
0x18001eb79  lea     rcx, [rbp+1B0h+var_138]
0x18001eb7d  call    ??0?$map@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@@std@@QEAA@XZ; std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(void)
0x18001eb82  nop
0x18001eb83  lea     rcx, [rbp+1B0h+var_148]
0x18001eb87  call    ??0?$map@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@@std@@QEAA@XZ; std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(void)
0x18001eb8c  nop
0x18001eb8d  lea     rcx, [rbp+1B0h+var_1A0]
0x18001eb91  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18001eb96  nop
0x18001eb97  movups  xmm0, cs:NETSETUPPKEY_Interface_PnpInstance
0x18001eb9e  movaps  [rbp+1B0h+var_90], xmm0
0x18001eba5  mov     eax, cs:dword_18003F100
0x18001ebab  mov     [rbp+1B0h+var_80], eax
0x18001ebb1  xor     eax, eax
0x18001ebb3  mov     [rbp+1B0h+var_7C], rax
0x18001ebba  mov     [rbp+1B0h+var_74], eax
0x18001ebc0  movups  xmm0, cs:NETSETUPPKEY_Interface_RemoveInterfaceWhenPnpDeviceRemoved
0x18001ebc7  movaps  [rbp+1B0h+var_70], xmm0
0x18001ebce  mov     eax, cs:dword_18003F010
0x18001ebd4  mov     [rbp+1B0h+var_60], eax
0x18001ebda  xor     eax, eax
0x18001ebdc  mov     [rbp+1B0h+var_5C], rax
0x18001ebe3  mov     [rbp+1B0h+var_54], eax
0x18001ebe9  mov     [rsp+2B0h+var_280], esi
0x18001ebed  mov     [rsp+2B0h+var_288], rsi
0x18001ebf2  mov     dword ptr [rsp+2B0h+var_290], 2
0x18001ebfa  lea     r9, [rbp+1B0h+var_90]
0x18001ec01  lea     rdx, [rbp+1B0h+var_160]
0x18001ec05  mov     rcx, r12
0x18001ec08  call    ??$GetAllObjectsInner@VNetworkInterface@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x18001ec0d  nop
0x18001ec0e  mov     rbx, [rbp+1B0h+var_160]
0x18001ec12  mov     rdi, [rbp+1B0h+var_158]
0x18001ec16  lea     r14d, [rsi+1]
0x18001ec1a  cmp     rbx, rdi
0x18001ec1d  jz      loc_18001ECE5
0x18001ec23  lea     r8, NETSETUPPKEY_Interface_PnpInstance
0x18001ec2a  lea     rdx, [rbp+1B0h+var_128]; struct _NETSETUPPROPKEY *
0x18001ec31  mov     rcx, [rbx]; this
0x18001ec34  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18001ec39  nop
0x18001ec3a  cmp     [rbp+1B0h+var_114], esi
0x18001ec40  jnz     short loc_18001EC48
0x18001ec42  mov     [rbp+1B0h+var_1B0], sil
0x18001ec46  jmp     short loc_18001EC9C
0x18001ec48  lea     rdx, [rbp+1B0h+var_190]
0x18001ec4c  lea     rcx, [rbp+1B0h+var_128]
0x18001ec53  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18001ec58  mov     [rbp+1B0h+var_1B0], r14b
0x18001ec5c  xorps   xmm0, xmm0
0x18001ec5f  movups  [rbp+1B0h+var_1D0], xmm0
0x18001ec63  xorps   xmm1, xmm1
0x18001ec66  movdqu  [rbp+1B0h+var_1C0], xmm1
0x18001ec6b  movups  xmm0, xmmword ptr [rax]
0x18001ec6e  movdqu  [rbp+1B0h+var_1D0], xmm0
0x18001ec73  mov     rcx, [rax+10h]
0x18001ec77  mov     qword ptr [rbp+1B0h+var_1C0], rcx
0x18001ec7b  mov     rcx, [rax+18h]
0x18001ec7f  mov     qword ptr [rbp+1B0h+var_1C0+8], rcx
0x18001ec83  mov     [rax+10h], rsi
0x18001ec87  mov     qword ptr [rax+18h], 7
0x18001ec8f  mov     [rax], si
0x18001ec92  lea     rcx, [rbp+1B0h+var_190]
0x18001ec96  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec9b  nop
0x18001ec9c  lea     rcx, [rbp+1B0h+var_110]
0x18001eca3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001eca8  nop
0x18001eca9  cmp     [rbp+1B0h+var_1B0], sil
0x18001ecad  jnz     short loc_18001ECB1
0x18001ecaf  jmp     short loc_18001ECD0
0x18001ecb1  mov     rcx, [rbx]; this
0x18001ecb4  call    ?get_RemoveInterfaceWhenPnpDeviceRemoved@NetworkInterface@NetSetup2@@QEBA_NXZ; NetSetup2::NetworkInterface::get_RemoveInterfaceWhenPnpDeviceRemoved(void)
0x18001ecb9  test    al, al
0x18001ecbb  jnz     loc_18001EE57
0x18001ecc1  cmp     [rbp+1B0h+var_1B0], sil
0x18001ecc5  jz      short loc_18001ECD0
0x18001ecc7  lea     rcx, [rbp+1B0h+var_1D0]
0x18001eccb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ecd0  add     rbx, 8
0x18001ecd4  cmp     rbx, rdi
0x18001ecd7  jnz     loc_18001EC23
0x18001ecdd  mov     rdi, [rbp+1B0h+var_158]
0x18001ece1  mov     rbx, [rbp+1B0h+var_160]
0x18001ece5  test    rbx, rbx
0x18001ece8  jz      short loc_18001ED09
0x18001ecea  mov     rdx, rdi
0x18001eced  mov     rcx, rbx
0x18001ecf0  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(std::unique_ptr<NetSetup2::ClientDriver> *,std::unique_ptr<NetSetup2::ClientDriver> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver>> &)
0x18001ecf5  mov     rcx, [rbp+1B0h+var_160]
0x18001ecf9  mov     rdx, [rbp+1B0h+var_150]
0x18001ecfd  sub     rdx, rcx
0x18001ed00  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001ed04  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ed09  lea     rcx, [rbp+1B0h+var_F0]; this
0x18001ed10  call    ??0NetDevices@@QEAA@XZ; NetDevices::NetDevices(void)
0x18001ed15  nop
0x18001ed16  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001ed1d  lea     rcx, [rsp+2B0h+var_268]; this
0x18001ed22  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18001ed27  nop
0x18001ed28  mov     [rsp+2B0h+var_290], rsi
0x18001ed2d  mov     r9d, r14d
0x18001ed30  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18001ed37  lea     rdx, [rbp+1B0h+var_1E8]
0x18001ed3b  mov     rcx, rax
0x18001ed3e  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18001ed43  nop
0x18001ed44  lea     rcx, [rsp+2B0h+var_268]
0x18001ed49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001ed4e  cmp     [rbp+1B0h+var_1E8], rsi
0x18001ed52  jz      short loc_18001ED82
0x18001ed54  lea     rdx, aResetinprogres; "ResetInProgress"
0x18001ed5b  lea     rcx, [rbp+1B0h+var_1E8]; this
0x18001ed5f  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001ed64  test    al, al
0x18001ed66  jz      short loc_18001ED82
0x18001ed68  xor     r9d, r9d
0x18001ed6b  xor     r8d, r8d
0x18001ed6e  lea     rdx, aResetinprogres; "ResetInProgress"
0x18001ed75  lea     rcx, [rbp+1B0h+var_1E8]
0x18001ed79  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18001ed7e  test    eax, eax
0x18001ed80  jnz     short loc_18001ED85
0x18001ed82  mov     r14b, sil
0x18001ed85  mov     rdi, [rbp+1B0h+var_F0]
0x18001ed8c  mov     rsi, [rbp+1B0h+var_E8]
0x18001ed93  cmp     rdi, rsi
0x18001ed96  jz      loc_18001F0E9
0x18001ed9c  mov     r15, qword ptr [rbp+1B0h+var_1E0]
0x18001eda0  mov     rcx, rdi; this
0x18001eda3  call    ?IsAvailable@NetSetupDevice@@QEAA_NXZ; NetSetupDevice::IsAvailable(void)
0x18001eda8  test    al, al
0x18001edaa  jz      loc_18001F0D7
0x18001edb0  mov     rcx, rdi; this
0x18001edb3  call    ?IsPnpSoftwareKeyAvailable@NetSetupDevice@@QEAA_NXZ; NetSetupDevice::IsPnpSoftwareKeyAvailable(void)
0x18001edb8  test    al, al
0x18001edba  jz      loc_18001F0D7
0x18001edc0  mov     rdx, [rdi+8]
0x18001edc4  lea     rcx, [rbp+1B0h+var_190]
0x18001edc8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001edcd  nop
0x18001edce  xorps   xmm0, xmm0
0x18001edd1  movups  [rbp+1B0h+var_1E0], xmm0
0x18001edd5  mov     r9, r13
0x18001edd8  mov     r8d, 3
0x18001edde  lea     rdx, [rbp+1B0h+var_1F0]
0x18001ede2  mov     rcx, rdi
0x18001ede5  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x18001edea  nop
0x18001edeb  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18001edf2  lea     rcx, [rbp+1B0h+var_1F0]; this
0x18001edf6  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001edfb  mov     bl, al
0x18001edfd  test    al, al
0x18001edff  jnz     loc_18001EEA1
0x18001ee05  lea     rdx, aAwaitingnetcfg; "AwaitingNetCfgInstall"
0x18001ee0c  lea     rcx, [rbp+1B0h+var_1F0]
0x18001ee10  call    ?GetValueBoolean@RegistryKey@@QEBA_NPEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBoolean(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001ee15  test    al, al
0x18001ee17  jnz     loc_18001EEA1
0x18001ee1d  test    r14b, r14b
0x18001ee20  jz      short loc_18001EE8C
0x18001ee22  mov     r10, cs:WPP_GLOBAL_Control
0x18001ee29  lea     rax, WPP_GLOBAL_Control
0x18001ee30  cmp     r10, rax
0x18001ee33  jz      loc_18001F0C4
0x18001ee39  cmp     byte ptr [r10+19h], 2
0x18001ee3e  jb      loc_18001F0C4
0x18001ee44  lea     rcx, [rbp+1B0h+var_190]
0x18001ee48  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ee4d  mov     edx, 0Fh
0x18001ee52  jmp     loc_18001EF11
0x18001ee57  mov     rdx, [rbx]
0x18001ee5a  add     rdx, 14h
0x18001ee5e  lea     r8, [rbp+1B0h+var_1D0]
0x18001ee62  lea     rcx, [rbp+1B0h+var_190]
0x18001ee66  call    ??$?0AEBU_GUID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@AEBU_GUID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::pair<_GUID,std::wstring>::pair<_GUID,std::wstring>(_GUID const &,std::wstring &)
0x18001ee6b  nop
0x18001ee6c  mov     r8, rax
0x18001ee6f  lea     rdx, [rsp+2B0h+var_240]
0x18001ee74  lea     rcx, [rbp+1B0h+var_138]
0x18001ee78  call    ??$emplace@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::wstring,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::emplace<std::pair<_GUID,std::wstring>>(std::pair<_GUID,std::wstring> &&)
0x18001ee7d  nop
0x18001ee7e  lea     rcx, [rbp+1B0h+var_180]
0x18001ee82  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee87  jmp     loc_18001ECC1
0x18001ee8c  lea     r8, [rbp+1B0h+var_190]
0x18001ee90  lea     rdx, [rbp+1B0h+var_230]
0x18001ee94  mov     rcx, r15
0x18001ee97  call    ??$_Emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x18001ee9c  jmp     loc_18001F0C4
0x18001eea1  test    bl, bl
0x18001eea3  jz      loc_18001F0C4
0x18001eea9  xor     r9d, r9d
0x18001eeac  lea     r8, aNetcfginstance; "NetCfgInstanceId"
0x18001eeb3  lea     rdx, [rbp+1B0h+var_128]
0x18001eeba  lea     rcx, [rbp+1B0h+var_1F0]
0x18001eebe  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001eec3  lea     rdx, [rbp+1B0h+var_1E0]
0x18001eec7  mov     rcx, rax
0x18001eeca  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18001eecf  mov     bl, al
0x18001eed1  lea     rcx, [rbp+1B0h+var_128]
0x18001eed8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eedd  test    bl, bl
0x18001eedf  jnz     short loc_18001EF29
0x18001eee1  mov     r10, cs:WPP_GLOBAL_Control
0x18001eee8  lea     rax, WPP_GLOBAL_Control
0x18001eeef  cmp     r10, rax
0x18001eef2  jz      loc_18001F0C4
0x18001eef8  cmp     byte ptr [r10+19h], 2
0x18001eefd  jb      loc_18001F0C4
0x18001ef03  lea     rcx, [rbp+1B0h+var_190]
0x18001ef07  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ef0c  mov     edx, 10h
0x18001ef11  mov     r9, rax
0x18001ef14  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001ef1b  mov     rcx, [r10+10h]
0x18001ef1f  call    WPP_SF_S
0x18001ef24  jmp     loc_18001F0C4
0x18001ef29  lea     rdx, aRetirednetcfgi; "RetiredNetCfgInstanceId"
0x18001ef30  lea     rcx, [rbp+1B0h+var_1F0]; this
0x18001ef34  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001ef39  test    al, al
0x18001ef3b  jz      loc_18001EFDC
0x18001ef41  xorps   xmm0, xmm0
0x18001ef44  movups  [rbp+1B0h+var_128], xmm0
0x18001ef4b  xor     r9d, r9d
0x18001ef4e  lea     r8, aRetirednetcfgi; "RetiredNetCfgInstanceId"
0x18001ef55  lea     rdx, [rbp+1B0h+var_1D0]
0x18001ef59  lea     rcx, [rbp+1B0h+var_1F0]
0x18001ef5d  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001ef62  lea     rdx, [rbp+1B0h+var_128]
0x18001ef69  mov     rcx, rax
0x18001ef6c  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18001ef71  mov     bl, al
0x18001ef73  lea     rcx, [rbp+1B0h+var_1D0]
0x18001ef77  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef7c  test    bl, bl
0x18001ef7e  jnz     short loc_18001EFB5
0x18001ef80  mov     r10, cs:WPP_GLOBAL_Control
0x18001ef87  lea     rax, WPP_GLOBAL_Control
0x18001ef8e  cmp     r10, rax
0x18001ef91  jz      loc_18001F0C4
0x18001ef97  cmp     byte ptr [r10+19h], 2
0x18001ef9c  jb      loc_18001F0C4
0x18001efa2  lea     rcx, [rbp+1B0h+var_190]
0x18001efa6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001efab  mov     edx, 11h
0x18001efb0  jmp     loc_18001EF11
0x18001efb5  lea     rax, [rbp+1B0h+var_1E0]
0x18001efb9  mov     [rsp+2B0h+var_290], rax
0x18001efbe  lea     r9, [rbp+1B0h+var_128]
0x18001efc5  lea     r8, [rbp+1B0h+var_190]
0x18001efc9  lea     rdx, [rbp+1B0h+var_220]
0x18001efcd  mov     rcx, [rsp+2B0h+var_260]
0x18001efd2  call    ??$_Emplace@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@AEAU3@@?$_Tree@V?$_Tset_traits@UInterfacesToMerge@@U?$less@UInterfacesToMerge@@@std@@V?$allocator@UInterfacesToMerge@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@UInterfacesToMerge@@PEAX@std@@_N@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAU_GUID@@1@Z; std::_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>::_Emplace<std::wstring &,_GUID &,_GUID &>(std::wstring &,_GUID &,_GUID &)
0x18001efd7  jmp     loc_18001F0C4
0x18001efdc  lea     r8, [rbp+1B0h+var_190]
0x18001efe0  lea     rdx, [rbp+1B0h+var_1E0]
0x18001efe4  lea     rcx, [rbp+1B0h+var_1D0]
0x18001efe8  call    ??$?0AEBU_GUID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@AEBU_GUID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::pair<_GUID,std::wstring>::pair<_GUID,std::wstring>(_GUID const &,std::wstring &)
0x18001efed  nop
0x18001efee  mov     r8, rax
0x18001eff1  lea     rdx, [rbp+1B0h+var_210]
0x18001eff5  lea     rcx, [rbp+1B0h+var_148]
0x18001eff9  call    ??$emplace@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::wstring,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::emplace<std::pair<_GUID,std::wstring>>(std::pair<_GUID,std::wstring> &&)
0x18001effe  nop
0x18001efff  lea     rcx, [rbp+1B0h+var_1C0]
0x18001f003  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f008  lea     rax, [rbp+1B0h+var_148]
0x18001f00c  mov     [rsp+2B0h+var_240], rax
0x18001f011  lea     rax, [rbp+1B0h+var_190]
0x18001f015  mov     [rsp+2B0h+var_238], rax
  ... truncated ...
```
