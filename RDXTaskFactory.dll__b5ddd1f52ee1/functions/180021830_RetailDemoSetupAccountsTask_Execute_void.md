# RetailDemoSetupAccountsTask::Execute(void)

- ea: `0x180021830`
- end: `0x18002213c`
- name: `?Execute@RetailDemoSetupAccountsTask@@MEAAXXZ`
- size: `2316`
- prototype: `void __fastcall(RetailDemoSetupAccountsTask *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000b218`
- `0x18000e3bc`
- `0x1800106c4`
- `0x18001094c`
- `0x180010a60`
- `0x18001ddb8`
- `0x18001eedc`
- `0x18001ff9c`
- `0x1800210b4`
- `0x1800212d4`
- `0x18002148c`
- `0x1800214f4`
- `0x1800215fc`
- `0x180021830`
- `0x180022180`
- `0x180022248`
- `0x180022298`
- `0x18002231c`
- `0x180022418`
- `0x180022448`
- `0x180022484`
- `0x18002f92c`
- `0x180030714`
- `0x180031284`
- `0x180031d7c`
- `0x180050010`

## import_xrefs

- `SHCORE!SHDeleteValueW` at `0x18002192d`
- `SHCORE!SHDeleteValueW` at `0x18002192d`
- `SHLWAPI!StrRChrW` at `0x180021a8c`
- `SHLWAPI!StrRChrW` at `0x180021a8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800218bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800219f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021c69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800218bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800219f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021c69`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021c18`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021c18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021983`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021d39`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021f5a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021983`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021d39`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021f5a`
- `samcli!NetUserGetInfo` at `0x180021ecd`
- `samcli!NetUserGetInfo` at `0x180021ecd`
- `samcli!NetUserSetInfo` at `0x180021f17`
- `samcli!NetUserSetInfo` at `0x180021f17`

## string_xrefs

- `0x1800219ea`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180021c07`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180021c5f`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180021de6`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x18002201b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180022030`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180022045`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x18002205a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x18002206d`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180022082`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180022097`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x1800220ac`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x1800220c1`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x1800220d6`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x1800220eb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180022100`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x180022115`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`
- `0x18002212a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptasksetupaccounts.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall RetailDemoSetupAccountsTask::Execute(RetailDemoSetupAccountsTask *this)
{
  int ValueW; // eax
  HKEY v2; // rcx
  unsigned int v3; // r9d
  int BOOLWithREGSAM; // eax
  DWORD v5; // r12d
  const unsigned __int16 *v6; // rdx
  HKEY v7; // rcx
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // r9
  HKEY v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  HRESULT v13; // eax
  int v14; // eax
  unsigned __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  const WCHAR *v19; // r14
  PWSTR v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  WCHAR *v23; // r14
  LPVOID v24; // rdi
  __int64 (__fastcall *v25)(LPVOID, WCHAR *, RetailDemoUtil **); // rbx
  int v26; // eax
  int v27; // eax
  unsigned __int64 v28; // rbx
  int v29; // edi
  LPVOID v30; // rdi
  __int64 (__fastcall *v31)(LPVOID, WCHAR *, RetailDemoUtil **); // rbx
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // eax
  unsigned int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  LPVOID v39; // rdi
  __int64 (__fastcall *v40)(LPVOID, unsigned __int16 *, RetailDemoUtil **); // rbx
  int v41; // eax
  unsigned int v42; // r8d
  __int64 v43; // rdx
  wil *v44; // rcx
  __int64 v45; // r8
  HRESULT v46; // eax
  int v47; // r15d
  RetailDemoSetupAccountsTask *v48; // rcx
  bool v49; // bl
  __int64 Singleton; // rdi
  __int64 v51; // rdx
  __int64 v52; // r8
  unsigned __int16 **v53; // r9
  unsigned int v54; // r8d
  unsigned int v55; // r8d
  const unsigned __int16 *v56; // rdx
  unsigned int v57; // r8d
  DWORD Info; // eax
  __int64 v59; // rdx
  __int64 v60; // r8
  int v61; // eax
  DWORD v62; // eax
  HRESULT Instance; // eax
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  unsigned int v71; // eax
  int pdwType; // [rsp+20h] [rbp-6F8h]
  int pdwTypea; // [rsp+20h] [rbp-6F8h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-6F8h]
  int pdwTypec; // [rsp+20h] [rbp-6F8h]
  int pdwTyped; // [rsp+20h] [rbp-6F8h]
  unsigned int pdwTypee; // [rsp+20h] [rbp-6F8h]
  unsigned int pdwTypef; // [rsp+20h] [rbp-6F8h]
  int pdwTypeg; // [rsp+20h] [rbp-6F8h]
  bool v80[8]; // [rsp+40h] [rbp-6D8h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-6D0h] BYREF
  DWORD v82[2]; // [rsp+50h] [rbp-6C8h] BYREF
  RetailDemoUtil *v83; // [rsp+58h] [rbp-6C0h] BYREF
  RetailDemoUtil *v84; // [rsp+60h] [rbp-6B8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-6B0h] BYREF
  unsigned __int16 v86[4]; // [rsp+70h] [rbp-6A8h] BYREF
  LPCVOID lpData; // [rsp+78h] [rbp-6A0h] BYREF
  __int64 v88; // [rsp+80h] [rbp-698h]
  __int64 v89; // [rsp+88h] [rbp-690h]
  unsigned int v90; // [rsp+90h] [rbp-688h] BYREF
  LPVOID v91; // [rsp+98h] [rbp-680h] BYREF
  LPBYTE bufptr[2]; // [rsp+A0h] [rbp-678h] BYREF
  int v93; // [rsp+B0h] [rbp-668h]
  WCHAR pszStart[264]; // [rsp+C0h] [rbp-658h] BYREF
  unsigned __int16 pvData[520]; // [rsp+2D0h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+0h]

  *(_QWORD *)v86 = this;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 168LL))(*((_QWORD *)this + 8));
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
             L"DefaultUserName",
             2u,
             0,
             pszStart,
             pcbData);
  if ( ValueW )
  {
    pszStart[0] = 0;
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( ValueW >= 0 )
  {
    pcbData[0] = 0;
    BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(
                       v2,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\TestHook",
                       L"KeepUserAdmin",
                       v3,
                       (int *)pcbData);
    v5 = pcbData[0];
    if ( BOOLWithREGSAM < 0 )
      v5 = 0;
    pcbData[0] = v5;
    SHDeleteValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"ForceAutoLogon");
    SHRegSetString(v7, v6, v8, v9);
    v90 = 0;
    SHRegGetDWORD(v10, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"IsConnectedAutoLogon", &v90);
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v11, v12);
    v13 = CoCreateInstance(&CLSID_UserAccounts, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
        (const char *)(unsigned int)v13,
        pdwType);
    lpData = 0;
    v88 = 0;
    v89 = 0;
    v84 = 0;
    if ( v5 )
    {
      pcbData[0] = 514;
      v14 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
              L"Account",
              2u,
              0,
              pvData,
              pcbData);
      if ( v14 )
      {
        pvData[0] = 0;
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
      }
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)(unsigned int)v14,
          pdwTypea);
      v15 = -1;
      do
        ++v15;
      while ( pvData[v15] );
      v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              &lpData,
              v15);
      v19 = (const WCHAR *)lpData;
      if ( v16 >= 0 )
      {
        StringCchCopyNW((unsigned __int16 *)lpData, v15 + 1, pvData, v15);
        v88 = v15;
      }
    }
    else
    {
      if ( v90 )
      {
        v20 = StrRChrW(pszStart, 0, 0x5Cu);
        v23 = v20 + 1;
        if ( !v20 )
          v23 = pszStart;
        v24 = ppv;
        v25 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, RetailDemoUtil **))(*(_QWORD *)ppv + 72LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84, v21, v22);
        v26 = v25(v24, v23, &v84);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
            (const char *)(unsigned int)v26,
            pdwType);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpData);
        v88 = -1;
        v89 = -1;
        *(_OWORD *)bufptr = PKEY_SAM_Name;
        v93 = 2;
        v27 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v84, bufptr, &lpData);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
            (const char *)(unsigned int)v27,
            pdwType);
      }
      else
      {
        v28 = -1;
        do
          ++v28;
        while ( pszStart[v28] );
        v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                &lpData,
                v28);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6D,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
            (const char *)(unsigned int)v29,
            pdwType);
        StringCchCopyNW((unsigned __int16 *)lpData, v28 + 1, pszStart, v28);
        v88 = v28;
        v30 = ppv;
        v31 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, RetailDemoUtil **))(*(_QWORD *)ppv + 72LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84, v32, v33);
        v34 = v31(v30, pszStart, &v84);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
            (const char *)(unsigned int)v34,
            pdwType);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpData);
      v19 = (const WCHAR *)lpData;
      v35 = RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
              L"Account",
              1u,
              lpData,
              2 * v88);
      if ( v35 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x73,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)v35,
          pdwTypeb);
      v82[0] = 514;
      v36 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
              L"AdminAccount",
              2u,
              0,
              pvData,
              v82);
      if ( v36 )
      {
        pvData[0] = 0;
        if ( v36 > 0 )
          v36 = (unsigned __int16)v36 | 0x80070000;
      }
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x77,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)(unsigned int)v36,
          pdwTypec);
      v83 = 0;
      v39 = ppv;
      v40 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, RetailDemoUtil **))(*(_QWORD *)ppv + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83, v37, v38);
      v41 = v40(v39, pvData, &v83);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)(unsigned int)v41,
          pdwTypec);
      try
      {
        RetailDemoUtil::AddUserToGroup(v83, (struct IPropertyStore *)0x220, v42);
      }
      catch ( ... )
      {
        v71 = wil::ResultFromCaughtException(v44);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x80,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)v71,
          (int)"RetailDemo failed to add %ws to admin group",
          (const char *)pvData);
        v5 = pcbData[0];
        v19 = (const WCHAR *)lpData;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83, v43, v45);
    }
    v91 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91, v17, v18);
    v46 = CoCreateInstance(
            &GUID_faf85f2e_a8e7_414d_a3e9_6b9e7b4a51ed,
            0,
            1u,
            &GUID_12614617_2e4b_4dd8_9fac_5c5183d3c95e,
            &v91);
    if ( v46 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
        (const char *)(unsigned int)v46,
        pdwTyped);
    pdwTypee = 0;
    v47 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *, GUID *, _QWORD))(*(_QWORD *)v91 + 24LL))(
            v91,
            v19,
            &GUID_2c932742_413c_4b70_82c9_252094ed4c3c,
            0);
    v49 = RetailDemoSetupAccountsTask::AreOfficeBitsOnBox(v48);
    Singleton = RetailDemo::Health::details::RetailDemoHealthTracker<1>::GetSingleton();
    v82[0] = v47;
    v80[0] = v49;
    RetailDemo::Health::details::RetailDemoScenarioEvents<1>::SetEventValueMember<bool>(Singleton, Singleton + 72, v80);
    RetailDemo::Health::details::RetailDemoScenarioEvents<1>::SetEventValueMember<long>(Singleton, Singleton + 76, v82);
    if ( v47 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
        (const char *)(unsigned int)v47,
        0);
    if ( !v5 )
    {
      *(_QWORD *)v86 = 0;
      *(_QWORD *)v82 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v82,
        0);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v86,
        0);
      RetailDemoUtil::GetDomainNameAndSidString(v19, v86, (unsigned __int16 **)v82, v53);
      if ( !RetailDemoUtil::IsUserInGroup(*(LPCWCH *)v82, (const unsigned __int16 *)0x221, v54) )
        RetailDemoUtil::AddUserToGroup(v84, (struct IPropertyStore *)0x221, v55);
      if ( RetailDemoUtil::IsUserInGroup(*(LPCWCH *)v82, (const unsigned __int16 *)0x220, v55) )
      {
        pdwTypee = (unsigned int)v19;
        StringCchPrintfW(pvData, 0x201u, L"%s\\%s", *(_QWORD *)v86);
        RetailDemoUtil::RemoveUserFromGroup((RetailDemoUtil *)pvData, v56, v57);
      }
      *(_QWORD *)pcbData = 0;
      bufptr[0] = (LPBYTE)pcbData;
      bufptr[1] = 0;
      LOBYTE(v93) = 1;
      Info = NetUserGetInfo(0, v19, 1u, &bufptr[1]);
      if ( Info )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xA9,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)Info,
          pdwTypee);
      wil::details::out_param_ptr_t<unsigned char * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_1 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_1 *,_USER_INFO_1 *,0,std::nullptr_t>>>>::~out_param_ptr_t<unsigned char * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_1 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_1 *,_USER_INFO_1 *,0,std::nullptr_t>>>>(bufptr);
      v61 = *(_DWORD *)(*(_QWORD *)pcbData + 40LL);
      if ( (v61 & 0x40) == 0 )
      {
        *(_DWORD *)(*(_QWORD *)pcbData + 40LL) = v61 | 0x40;
        v62 = NetUserSetInfo(0, v19, 1u, *(LPBYTE *)pcbData, 0);
        if ( v62 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0xAD,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
            (const char *)v62,
            pdwTypef);
      }
      v83 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83, v59, v60);
      Instance = CoCreateInstance(
                   &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
                   0,
                   1u,
                   &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
                   (LPVOID *)&v83);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB2,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)(unsigned int)Instance,
          pdwTypeg);
      v64 = (*(__int64 (__fastcall **)(RetailDemoUtil *))(*(_QWORD *)v83 + 48LL))(v83);
      if ( v64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptasksetupaccounts.cpp",
          (const char *)(unsigned int)v64,
          pdwTypeg);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83, v65, v66);
      wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_1 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_1 *,_USER_INFO_1 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_1 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_1 *,_USER_INFO_1 *,0,std::nullptr_t>>(pcbData);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v82);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v86);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91, v51, v52);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84, v67, v68);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpData);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v69, v70);
  }
}

```

## disassembly

```asm
0x180021830  mov     [rsp+arg_8], rbx
0x180021835  mov     [rsp+arg_10], rsi
0x18002183a  push    rdi
0x18002183b  push    r12
0x18002183d  push    r13
0x18002183f  push    r14
0x180021841  push    r15
0x180021843  sub     rsp, 6F0h
0x18002184a  mov     rax, cs:__security_cookie
0x180021851  xor     rax, rsp
0x180021854  mov     [rsp+718h+var_38], rax
0x18002185c  mov     r13, rcx
0x18002185f  mov     qword ptr [rsp+718h+var_6A8], rcx
0x180021864  mov     rcx, [rcx+40h]
0x180021868  mov     rax, [rcx]
0x18002186b  mov     rax, [rax+0A8h]
0x180021872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021877  mov     [rsp+718h+var_6D0], 208h
0x18002187f  lea     rax, [rsp+718h+var_6D0]
0x180021884  mov     [rsp+718h+pcbData], rax; pcbData
0x180021889  lea     rax, [rsp+718h+pszStart]
0x180021891  mov     [rsp+718h+pvData], rax; pvData
0x180021896  xor     esi, esi
0x180021898  mov     [rsp+718h+pdwType], rsi; pdwType
0x18002189d  lea     r14d, [rsi+2]
0x1800218a1  mov     r9d, r14d; dwFlags
0x1800218a4  lea     r8, Value; "DefaultUserName"
0x1800218ab  lea     rdi, pszSubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800218b2  mov     rdx, rdi; lpSubKey
0x1800218b5  mov     rbx, 0FFFFFFFF80000002h
0x1800218bc  mov     rcx, rbx; hkey
0x1800218bf  call    cs:__imp_RegGetValueW
0x1800218c5  test    eax, eax
0x1800218c7  jz      short loc_1800218E1
0x1800218c9  mov     [rsp+718h+pszStart], si
0x1800218d1  jle     short loc_1800218E1
0x1800218d3  movzx   eax, ax
0x1800218d6  mov     r15d, 80070000h
0x1800218dc  or      eax, r15d
0x1800218df  jmp     short loc_1800218E7
0x1800218e1  mov     r15d, 80070000h
0x1800218e7  test    eax, eax
0x1800218e9  js      loc_180021FEB
0x1800218ef  mov     [rsp+718h+var_6D0], esi
0x1800218f3  lea     rax, [rsp+718h+var_6D0]
0x1800218f8  mov     [rsp+718h+pdwType], rax; int *
0x1800218fd  lea     r8, ?c_retailDemoKeepUserAdmin@@3QBGB; "KeepUserAdmin"
0x180021904  lea     rdx, ?c_retailDemoKeyTestHook@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002190b  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180021910  mov     r12d, [rsp+718h+var_6D0]
0x180021915  test    eax, eax
0x180021917  cmovs   r12d, esi
0x18002191b  mov     [rsp+718h+var_6D0], r12d
0x180021920  lea     r8, pszValue; "ForceAutoLogon"
0x180021927  mov     rdx, rdi; pszSubKey
0x18002192a  mov     rcx, rbx; hkey
0x18002192d  call    cs:__imp_SHDeleteValueW
0x180021933  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180021938  mov     [rsp+718h+var_688], esi
0x18002193f  lea     r9, [rsp+718h+var_688]; unsigned int *
0x180021947  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x18002194e  mov     rdx, rdi; unsigned __int16 *
0x180021951  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180021956  mov     [rsp+718h+ppv], rsi
0x18002195b  lea     rcx, [rsp+718h+ppv]
0x180021960  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021965  lea     rax, [rsp+718h+ppv]
0x18002196a  mov     [rsp+718h+pdwType], rax; int
0x18002196f  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180021976  xor     edx, edx; pUnkOuter
0x180021978  lea     r8d, [rdx+3]; dwClsContext
0x18002197c  lea     rcx, CLSID_UserAccounts; rclsid
0x180021983  call    cs:__imp_CoCreateInstance
0x180021989  mov     rcx, [rsp+718h]; this
0x180021991  test    eax, eax
0x180021993  js      loc_180022018
0x180021999  mov     [rsp+718h+lpData], rsi
0x18002199e  mov     [rsp+718h+var_698], rsi
0x1800219a6  mov     [rsp+718h+var_690], rsi
0x1800219ae  mov     [rsp+718h+var_6B8], rsi
0x1800219b3  test    r12d, r12d
0x1800219b6  jz      loc_180021A71
0x1800219bc  mov     [rsp+718h+var_6D0], 202h
0x1800219c4  lea     rax, [rsp+718h+var_6D0]
0x1800219c9  mov     [rsp+718h+pcbData], rax; pcbData
0x1800219ce  lea     rax, [rsp+718h+var_448]
0x1800219d6  mov     [rsp+718h+pvData], rax; pvData
0x1800219db  mov     [rsp+718h+pdwType], rsi; int
0x1800219e0  mov     r9d, r14d; dwFlags
0x1800219e3  lea     r8, ?c_retailDemoValueDemoAccountName@@3QBGB; "Account"
0x1800219ea  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800219f1  mov     rcx, rbx; hkey
0x1800219f4  call    cs:__imp_RegGetValueW
0x1800219fa  test    eax, eax
0x1800219fc  jz      short loc_180021A0E
0x1800219fe  mov     [rsp+718h+var_448], si
0x180021a06  jle     short loc_180021A0E
0x180021a08  movzx   eax, ax
0x180021a0b  or      eax, r15d
0x180021a0e  mov     rcx, [rsp+718h]; this
0x180021a16  test    eax, eax
0x180021a18  js      loc_18002202D
0x180021a1e  lea     rax, [rsp+718h+var_448]
0x180021a26  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021a2a  inc     rbx
0x180021a2d  cmp     [rax+rbx*2], si
0x180021a31  jnz     short loc_180021A2A
0x180021a33  mov     rdx, rbx
0x180021a36  lea     rcx, [rsp+718h+lpData]
0x180021a3b  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180021a40  mov     r14, [rsp+718h+lpData]
0x180021a45  test    eax, eax
0x180021a47  js      loc_180021D03
0x180021a4d  lea     rdx, [rbx+1]; unsigned __int64
0x180021a51  mov     r9, rbx; unsigned __int64
0x180021a54  lea     r8, [rsp+718h+var_448]; unsigned __int16 *
0x180021a5c  mov     rcx, r14; unsigned __int16 *
0x180021a5f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180021a64  mov     [rsp+718h+var_698], rbx
0x180021a6c  jmp     loc_180021D03
0x180021a71  cmp     [rsp+718h+var_688], esi
0x180021a78  jz      loc_180021B42
0x180021a7e  xor     edx, edx; pszEnd
0x180021a80  lea     r8d, [rdx+5Ch]; wMatch
0x180021a84  lea     rcx, [rsp+718h+pszStart]; pszStart
0x180021a8c  call    cs:__imp_StrRChrW
0x180021a92  test    rax, rax
0x180021a95  lea     r14, [rax+2]
0x180021a99  jnz     short loc_180021AA3
0x180021a9b  lea     r14, [rsp+718h+pszStart]
0x180021aa3  mov     rdi, [rsp+718h+ppv]
0x180021aa8  mov     rax, [rdi]
0x180021aab  mov     rbx, [rax+48h]
0x180021aaf  lea     rcx, [rsp+718h+var_6B8]
0x180021ab4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021ab9  lea     r8, [rsp+718h+var_6B8]
0x180021abe  mov     rdx, r14
0x180021ac1  mov     rcx, rdi
0x180021ac4  mov     rax, rbx
0x180021ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021acc  mov     rcx, [rsp+718h]; this
0x180021ad4  test    eax, eax
0x180021ad6  js      loc_180022042
0x180021adc  lea     rcx, [rsp+718h+lpData]
0x180021ae1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180021ae6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021aea  mov     [rsp+718h+var_698], rbx
0x180021af2  mov     [rsp+718h+var_690], rbx
0x180021afa  movups  xmm0, cs:PKEY_SAM_Name
0x180021b01  movaps  xmmword ptr [rsp+718h+bufptr], xmm0
0x180021b09  mov     eax, cs:dword_180059C08
0x180021b0f  mov     [rsp+718h+var_668], eax
0x180021b16  lea     r8, [rsp+718h+lpData]
0x180021b1b  lea     rdx, [rsp+718h+bufptr]
0x180021b23  lea     rcx, [rsp+718h+var_6B8]
0x180021b28  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180021b2d  mov     rcx, [rsp+718h]; this
0x180021b35  test    eax, eax
0x180021b37  js      loc_180022057
0x180021b3d  jmp     loc_180021BD9
0x180021b42  lea     rax, [rsp+718h+pszStart]
0x180021b4a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021b4e  inc     rbx
0x180021b51  cmp     [rax+rbx*2], si
0x180021b55  jnz     short loc_180021B4E
0x180021b57  mov     rdx, rbx
0x180021b5a  lea     rcx, [rsp+718h+lpData]
0x180021b5f  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180021b64  mov     edi, eax
0x180021b66  test    eax, eax
0x180021b68  js      short loc_180021B8B
0x180021b6a  lea     rdx, [rbx+1]; unsigned __int64
0x180021b6e  mov     r9, rbx; unsigned __int64
0x180021b71  lea     r8, [rsp+718h+pszStart]; unsigned __int16 *
0x180021b79  mov     rcx, [rsp+718h+lpData]; unsigned __int16 *
0x180021b7e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180021b83  mov     [rsp+718h+var_698], rbx
0x180021b8b  mov     rcx, [rsp+718h]; this
0x180021b93  test    edi, edi
0x180021b95  js      loc_18002206A
0x180021b9b  mov     rdi, [rsp+718h+ppv]
0x180021ba0  mov     rax, [rdi]
0x180021ba3  mov     rbx, [rax+48h]
0x180021ba7  lea     rcx, [rsp+718h+var_6B8]
0x180021bac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021bb1  lea     r8, [rsp+718h+var_6B8]
0x180021bb6  lea     rdx, [rsp+718h+pszStart]
0x180021bbe  mov     rcx, rdi
0x180021bc1  mov     rax, rbx
0x180021bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bc9  mov     rcx, [rsp+718h]; this
0x180021bd1  test    eax, eax
0x180021bd3  js      loc_18002207F
0x180021bd9  lea     rcx, [rsp+718h+lpData]
0x180021bde  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180021be3  mov     ecx, dword ptr [rsp+718h+var_698]
0x180021bea  add     ecx, ecx
0x180021bec  mov     dword ptr [rsp+718h+pvData], ecx; cbData
0x180021bf0  mov     r14, [rsp+718h+lpData]
0x180021bf5  mov     [rsp+718h+pdwType], r14; unsigned int
0x180021bfa  mov     r9d, 1; dwType
0x180021c00  lea     r8, ?c_retailDemoValueDemoAccountName@@3QBGB; "Account"
0x180021c07  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021c0e  mov     rbx, 0FFFFFFFF80000002h
0x180021c15  mov     rcx, rbx; hKey
0x180021c18  call    cs:__imp_RegSetKeyValueW
0x180021c1e  mov     rcx, [rsp+718h]; this
0x180021c26  test    eax, eax
0x180021c28  jnz     loc_180022094
0x180021c2e  mov     [rsp+718h+var_6C8], 202h
0x180021c36  lea     rax, [rsp+718h+var_6C8]
0x180021c3b  mov     [rsp+718h+pcbData], rax; pcbData
0x180021c40  lea     rax, [rsp+718h+var_448]
0x180021c48  mov     [rsp+718h+pvData], rax; pvData
0x180021c4d  mov     [rsp+718h+pdwType], rsi; int
0x180021c52  mov     r9d, 2; dwFlags
0x180021c58  lea     r8, ?c_retailDemoValueAdminAccountName@@3QBGB; "AdminAccount"
0x180021c5f  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021c66  mov     rcx, rbx; hkey
0x180021c69  call    cs:__imp_RegGetValueW
0x180021c6f  test    eax, eax
0x180021c71  jz      short loc_180021C83
0x180021c73  mov     [rsp+718h+var_448], si
0x180021c7b  jle     short loc_180021C83
0x180021c7d  movzx   eax, ax
0x180021c80  or      eax, r15d
0x180021c83  mov     rcx, [rsp+718h]; this
0x180021c8b  test    eax, eax
0x180021c8d  js      loc_1800220A9
0x180021c93  mov     [rsp+718h+var_6C0], rsi
0x180021c98  mov     rdi, [rsp+718h+ppv]
0x180021c9d  mov     rax, [rdi]
0x180021ca0  mov     rbx, [rax+48h]
0x180021ca4  lea     rcx, [rsp+718h+var_6C0]
0x180021ca9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021cae  lea     r8, [rsp+718h+var_6C0]
0x180021cb3  lea     rdx, [rsp+718h+var_448]
0x180021cbb  mov     rcx, rdi
0x180021cbe  mov     rax, rbx
0x180021cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cc6  mov     rcx, [rsp+718h]; this
0x180021cce  test    eax, eax
0x180021cd0  js      loc_1800220BE
0x180021cd6  mov     edx, 220h; struct IPropertyStore *
0x180021cdb  mov     rcx, [rsp+718h+var_6C0]; this
0x180021ce0  call    ?AddUserToGroup@RetailDemoUtil@@YAXPEAUIPropertyStore@@K@Z; RetailDemoUtil::AddUserToGroup(IPropertyStore *,ulong)
0x180021ce5  nop
0x180021ce6  jmp     short loc_180021CF9
0x180021ce8  xor     esi, esi
0x180021cea  mov     r12d, [rsp+718h+var_6D0]
0x180021cef  mov     r14, [rsp+718h+lpData]
0x180021cf4  mov     r13, qword ptr [rsp+718h+var_6A8]
0x180021cf9  lea     rcx, [rsp+718h+var_6C0]
0x180021cfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d03  mov     [rsp+718h+var_680], rsi
0x180021d0b  lea     rcx, [rsp+718h+var_680]
0x180021d13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d18  lea     rax, [rsp+718h+var_680]
0x180021d20  mov     [rsp+718h+pdwType], rax; int
0x180021d25  lea     r9, _GUID_12614617_2e4b_4dd8_9fac_5c5183d3c95e; riid
0x180021d2c  xor     edx, edx; pUnkOuter
0x180021d2e  lea     r8d, [rdx+1]; dwClsContext
0x180021d32  lea     rcx, _GUID_faf85f2e_a8e7_414d_a3e9_6b9e7b4a51ed; rclsid
0x180021d39  call    cs:__imp_CoCreateInstance
0x180021d3f  mov     rcx, [rsp+718h]; this
0x180021d47  test    eax, eax
0x180021d49  js      loc_1800220D3
0x180021d4f  mov     r10, [rsp+718h+var_680]
0x180021d57  mov     rax, [r10]
0x180021d5a  mov     r11, [rax+18h]
0x180021d5e  mov     rax, [r13+30h]
0x180021d62  test    rax, rax
0x180021d65  jz      short loc_180021D6C
0x180021d67  mov     rcx, [rax]
0x180021d6a  jmp     short loc_180021D6F
0x180021d6c  mov     rcx, rsi
0x180021d6f  mov     [rsp+718h+pcbData], rcx
0x180021d74  mov     dword ptr [rsp+718h+pvData], 36EE80h
0x180021d7c  mov     [rsp+718h+pdwType], rsi; int
0x180021d81  xor     r9d, r9d
0x180021d84  lea     r8, _GUID_2c932742_413c_4b70_82c9_252094ed4c3c
0x180021d8b  mov     rdx, r14
0x180021d8e  mov     rcx, r10
0x180021d91  mov     rax, r11
0x180021d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d99  mov     r15d, eax
0x180021d9c  call    ?AreOfficeBitsOnBox@RetailDemoSetupAccountsTask@@AEAA_NXZ; RetailDemoSetupAccountsTask::AreOfficeBitsOnBox(void)
0x180021da1  mov     bl, al
0x180021da3  call    ?GetSingleton@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@CAAEAV1234@XZ; RetailDemo::Health::details::RetailDemoHealthTracker<1>::GetSingleton(void)
0x180021da8  mov     rdi, rax
0x180021dab  mov     [rsp+718h+var_6C8], r15d
0x180021db0  mov     [rsp+718h+var_6D8], bl
0x180021db4  lea     rdx, [rax+48h]
0x180021db8  lea     r8, [rsp+718h+var_6D8]
0x180021dbd  mov     rcx, rax
0x180021dc0  call    ??$SetEventValueMember@_N@?$RetailDemoScenarioEvents@$00@details@Health@RetailDemo@@AEAAXAEA_NAEB_N@Z; RetailDemo::Health::details::RetailDemoScenarioEvents<1>::SetEventValueMember<bool>(bool &,bool const &)
0x180021dc5  lea     rdx, [rdi+4Ch]
0x180021dc9  lea     r8, [rsp+718h+var_6C8]
0x180021dce  mov     rcx, rdi
0x180021dd1  call    ??$SetEventValueMember@J@?$RetailDemoScenarioEvents@$00@details@Health@RetailDemo@@AEAAXAEAJAEBJ@Z; RetailDemo::Health::details::RetailDemoScenarioEvents<1>::SetEventValueMember<long>(long &,long const &)
  ... truncated ...
```
