# UserOOBEController::s_ProcessUserRegKeys(UserOOBEExitReason)

- ea: `0x180029260`
- end: `0x18002988a`
- name: `?s_ProcessUserRegKeys@UserOOBEController@@CAJW4UserOOBEExitReason@@@Z`
- size: `1578`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000a5e8`
- `0x18000d5a0`
- `0x18000d738`
- `0x18000e270`
- `0x180013688`
- `0x180014468`
- `0x1800169b0`
- `0x180018c98`
- `0x18001b61c`
- `0x18001ee68`
- `0x180022f2c`
- `0x180022f50`
- `0x1800233ec`
- `0x1800279b8`
- `0x1800279fc`
- `0x180027aec`
- `0x180027efc`
- `0x18002849c`
- `0x180028adc`
- `0x180029260`
- `0x18002a480`
- `0x18002c4f8`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180029826`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180029826`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1800297bb`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1800297bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180029606`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180029606`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800295a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800295a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002954a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002954a`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x1800296f7`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x1800296f7`

## string_xrefs

- `0x180029312`: `SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\Broker`
- `0x180029297`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800292e4`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029339`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029356`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800293db`: `Configuration`
- `0x18002940a`: `Configuration`
- `0x18002937d`: `%s\Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x180029460`: `SettingConfiguration`
- `0x18002948f`: `SettingConfiguration`
- `0x180029411`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x180029496`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x18002959d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE\ATConfig`
- `0x1800294cc`: `%s\Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
__int64 __fastcall UserOOBEController::s_ProcessUserRegKeys(unsigned int a1)
{
  int DefaultAccountSid; // eax
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rbx
  int v5; // eax
  int v6; // edi
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // eax
  LSTATUS v14; // edi
  unsigned int v15; // eax
  char v16; // di
  bool v17; // r8
  int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  unsigned int v21; // r9d
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  int phkResulta; // [rsp+20h] [rbp-99h]
  int phkResultb; // [rsp+20h] [rbp-99h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-89h]
  PHKEY v32; // [rsp+38h] [rbp-81h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-69h] BYREF
  void *v34; // [rsp+58h] [rbp-61h] BYREF
  __int64 v35; // [rsp+60h] [rbp-59h]
  HKEY v36; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v37; // [rsp+70h] [rbp-49h] BYREF
  LPCWSTR v38[3]; // [rsp+78h] [rbp-41h] BYREF
  HKEY *p_hKey; // [rsp+90h] [rbp-29h] BYREF
  HKEY v40; // [rsp+98h] [rbp-21h] BYREF
  char v41; // [rsp+A0h] [rbp-19h]
  unsigned __int16 *v42[3]; // [rsp+A8h] [rbp-11h] BYREF
  LPCWSTR pszSubKey[10]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  HKEY hKey; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned __int16 *v46; // [rsp+130h] [rbp+77h] BYREF
  unsigned __int16 *v47; // [rsp+138h] [rbp+7Fh] BYREF

  v37 = 0;
  DefaultAccountSid = UserOOBEController::s_GetDefaultAccountSid(&v37);
  v3 = DefaultAccountSid;
  if ( DefaultAccountSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)DefaultAccountSid,
      phkResult);
    goto LABEL_54;
  }
  memset(v38, 0, sizeof(v38));
  v4 = v37;
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v38,
         L"%s\\%s",
         v37,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE");
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
LABEL_5:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v38);
    v3 = v6;
    goto LABEL_54;
  }
  memset(pszSubKey, 0, 24);
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         pszSubKey,
         L"%s\\%s",
         v4,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Broker");
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x222,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
LABEL_8:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszSubKey);
    goto LABEL_5;
  }
  if ( a1 == 1 )
  {
    memset(v42, 0, sizeof(v42));
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
           v42,
           L"%s\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility",
           v4);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v8,
        phkResult);
LABEL_12:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v42);
      goto LABEL_8;
    }
    v47 = 0;
    lpSubKey = (LPCWSTR)&v47;
    v34 = 0;
    LOBYTE(v35) = 1;
    v9 = (unsigned int)SHRegAllocData(HKEY_USERS, v42[0], L"Configuration", 2, &v34, 0) >> 31;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&lpSubKey);
    if ( (unsigned __int8)v9 != 1 )
    {
      v10 = SHRegSetString(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
              L"Configuration",
              v47);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v10,
          phkResulta);
    }
    v46 = 0;
    lpSubKey = (LPCWSTR)&v46;
    v34 = 0;
    LOBYTE(v35) = 1;
    v11 = (unsigned int)SHRegAllocData(HKEY_USERS, v42[0], L"SettingConfiguration", 2, &v34, 0) >> 31;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&lpSubKey);
    if ( (unsigned __int8)v11 != 1 )
    {
      v12 = SHRegSetString(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
              L"SettingConfiguration",
              v46);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v12,
          phkResultb);
    }
    lpSubKey = 0;
    v34 = 0;
    v35 = 0;
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &lpSubKey,
            L"%s\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig",
            v4);
    v6 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v13,
        phkResultb);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v46);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
      goto LABEL_12;
    }
    v36 = 0;
    p_hKey = &v36;
    v40 = 0;
    v41 = 1;
    v14 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &v40);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( !v14 )
    {
      hKey = 0;
      p_hKey = &hKey;
      v40 = 0;
      v41 = 1;
      v15 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE\\ATConfig",
              0,
              0,
              0,
              0xF003Fu,
              0,
              &v40,
              0);
      if ( v15 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x240,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)v15,
          phkResult);
        v16 = 0;
      }
      else
      {
        v16 = 1;
      }
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( v16 )
      {
        v18 = CopyRegTreeWithoutACLs(v36, hKey, v17);
        if ( v18 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x242,
            (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
            (const char *)(unsigned int)v18,
            phkResult);
          v19 = RegDeleteTreeW(hKey, 0);
          if ( v19 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x245,
              (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
              (const char *)v19,
              phkResult);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v46);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v42);
  }
  LOBYTE(hKey) = 0;
  v20 = UserOOBEController::s_SetupAutologonIfNecessary(v38[0], a1, &hKey);
  if ( v20 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v20,
      phkResult);
  if ( (_BYTE)hKey )
  {
    LODWORD(hKey) = 0;
    if ( ((int)SHRegGetBOOLWithREGSAM(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
                 L"UnattendSetAutologon",
                 v21,
                 (int *)&hKey) < 0
       || !(_DWORD)hKey)
      && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_26370069>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_26370069>::GetImpl'::`2'::impl)
       || !UserOOBEController::s_IsInteractiveLoginTextMessageConfigured()) )
    {
      SetPersistedRegistryDWORD(
        L"Winlogon",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
        L"AnimationAfterUserOOBE",
        1);
    }
  }
  else if ( a1 == 1 )
  {
    v22 = UserOOBEController::s_CleanupNetworkCredentials();
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x26F,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v22,
        phkResult);
    v23 = SetAutologonDetails(0, 0, 0, 0, 0, 0);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x272,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v23,
        phkResult);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeHostAppInDefaultUserSession>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeHostAppInDefaultUserSession>::GetImpl'::`2'::impl) )
  {
    lpSubKey = 0;
    v34 = 0;
    v35 = 0;
    v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &lpSubKey,
            L"%s\\%s",
            v4,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\OobeStorage");
    if ( v24 >= 0 )
    {
      v25 = SHDeleteKeyW(HKEY_USERS, lpSubKey);
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      LODWORD(v32) = -2147023728;
      LODWORD(lpSecurityAttributes) = -2147024893;
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x27C,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v25,
        3,
        0x80070002,
        lpSecurityAttributes,
        v32);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v24,
        phkResult);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
  }
  ClearCachedAutologonSettings(v38[0], HKEY_CURRENT_USER);
  v26 = SHDeleteValueW(HKEY_USERS, pszSubKey[0], L"AuthenticationBuffer");
  if ( v26 > 0 )
    v26 = (unsigned __int16)v26 | 0x80070000;
  wil::details::in1diag3::Log_IfFailedWithExpected(
    retaddr,
    (void *)0x281,
    (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
    (const char *)(unsigned int)v26,
    1,
    0x80070002);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszSubKey);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v38);
  v3 = 0;
LABEL_54:
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v37);
  return v3;
}

```

## disassembly

```asm
0x180029260  push    rbp
0x180029262  push    rbx
0x180029263  push    rsi
0x180029264  push    rdi
0x180029265  push    r13
0x180029267  push    r14
0x180029269  push    r15
0x18002926b  lea     rbp, [rsp-27h]
0x180029270  sub     rsp, 0E0h
0x180029277  mov     r14d, ecx
0x18002927a  xor     r15d, r15d
0x18002927d  mov     [rbp+57h+var_A0], r15
0x180029281  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 **
0x180029285  call    ?s_GetDefaultAccountSid@UserOOBEController@@CAJPEAPEAG@Z; UserOOBEController::s_GetDefaultAccountSid(ushort * *)
0x18002928a  mov     ebx, eax
0x18002928c  test    eax, eax
0x18002928e  jns     short loc_1800292AD
0x180029290  mov     rcx, [rbp+5Fh]; this
0x180029294  mov     r9d, eax; char *
0x180029297  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002929e  mov     edx, 21Eh; void *
0x1800292a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800292a8  jmp     loc_18002986D
0x1800292ad  mov     [rbp+57h+var_98], r15
0x1800292b1  mov     [rbp+57h+var_90], r15
0x1800292b5  mov     [rbp+57h+var_88], r15
0x1800292b9  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800292c0  mov     rbx, [rbp+57h+var_A0]
0x1800292c4  mov     r8, rbx
0x1800292c7  lea     rdx, aSS_0; "%s\\%s"
0x1800292ce  lea     rcx, [rbp+57h+var_98]
0x1800292d2  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800292d7  mov     edi, eax
0x1800292d9  test    eax, eax
0x1800292db  jns     short loc_180029306
0x1800292dd  mov     rcx, [rbp+5Fh]; this
0x1800292e1  mov     r9d, eax; char *
0x1800292e4  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800292eb  mov     edx, 220h; void *
0x1800292f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800292f5  nop
0x1800292f6  lea     rcx, [rbp+57h+var_98]
0x1800292fa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800292ff  mov     ebx, edi
0x180029301  jmp     loc_18002986D
0x180029306  mov     [rbp+57h+pszSubKey], r15
0x18002930a  mov     [rbp+57h+var_48], r15
0x18002930e  mov     [rbp+57h+var_40], r15
0x180029312  lea     r9, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180029319  mov     r8, rbx
0x18002931c  lea     rdx, aSS_0; "%s\\%s"
0x180029323  lea     rcx, [rbp+57h+pszSubKey]
0x180029327  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002932c  mov     edi, eax
0x18002932e  test    eax, eax
0x180029330  jns     short loc_180029356
0x180029332  mov     rcx, [rbp+5Fh]; this
0x180029336  mov     r9d, eax; char *
0x180029339  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029340  mov     edx, 222h; void *
0x180029345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002934a  nop
0x18002934b  lea     rcx, [rbp+57h+pszSubKey]
0x18002934f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029354  jmp     short loc_1800292F6
0x180029356  lea     rsi, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002935d  mov     r13, 0FFFFFFFF80000002h
0x180029364  cmp     r14d, 1
0x180029368  jnz     loc_180029660
0x18002936e  mov     [rbp+57h+var_68], r15
0x180029372  mov     [rbp+57h+var_60], r15
0x180029376  mov     [rbp+57h+var_58], r15
0x18002937a  mov     r8, rbx
0x18002937d  lea     rdx, aSSoftwareMicro; "%s\\Software\\Microsoft\\Windows NT\\Cu"...
0x180029384  lea     rcx, [rbp+57h+var_68]
0x180029388  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002938d  mov     edi, eax
0x18002938f  test    eax, eax
0x180029391  jns     short loc_1800293B3
0x180029393  mov     rcx, [rbp+5Fh]; this
0x180029397  mov     r9d, eax; char *
0x18002939a  mov     r8, rsi; unsigned int
0x18002939d  mov     edx, 229h; void *
0x1800293a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800293a7  nop
0x1800293a8  lea     rcx, [rbp+57h+var_68]
0x1800293ac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800293b1  jmp     short loc_18002934B
0x1800293b3  mov     [rbp+57h+arg_18], r15
0x1800293b7  lea     rax, [rbp+57h+arg_18]
0x1800293bb  mov     [rbp+57h+lpSubKey], rax
0x1800293bf  mov     [rbp+57h+var_B8], r15
0x1800293c3  mov     byte ptr [rbp+57h+var_B0], 1
0x1800293c7  mov     qword ptr [rsp+110h+samDesired], r15; unsigned int *
0x1800293cc  lea     rax, [rbp+57h+var_B8]
0x1800293d0  mov     [rsp+110h+phkResult], rax; int
0x1800293d5  mov     r9d, 2; int
0x1800293db  lea     r8, aConfiguration; "Configuration"
0x1800293e2  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800293e6  mov     rcx, 0FFFFFFFF80000003h; HKEY
0x1800293ed  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800293f2  mov     edi, eax
0x1800293f4  shr     edi, 1Fh
0x1800293f7  lea     rcx, [rbp+57h+lpSubKey]
0x1800293fb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180029400  xor     dil, 1
0x180029404  jz      short loc_180029438
0x180029406  mov     r9, [rbp+57h+arg_18]; unsigned __int16 *
0x18002940a  lea     r8, aConfiguration; "Configuration"
0x180029411  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows NT\\Curren"...
0x180029418  mov     rcx, r13; HKEY
0x18002941b  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180029420  mov     rcx, [rbp+5Fh]; this
0x180029424  test    eax, eax
0x180029426  jns     short loc_180029438
0x180029428  mov     r9d, eax; char *
0x18002942b  mov     r8, rsi; unsigned int
0x18002942e  mov     edx, 22Fh; void *
0x180029433  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029438  mov     [rbp+57h+arg_10], r15
0x18002943c  lea     rax, [rbp+57h+arg_10]
0x180029440  mov     [rbp+57h+lpSubKey], rax
0x180029444  mov     [rbp+57h+var_B8], r15
0x180029448  mov     byte ptr [rbp+57h+var_B0], 1
0x18002944c  mov     qword ptr [rsp+110h+samDesired], r15; unsigned int *
0x180029451  lea     rax, [rbp+57h+var_B8]
0x180029455  mov     [rsp+110h+phkResult], rax; int
0x18002945a  mov     r9d, 2; int
0x180029460  lea     r8, aSettingconfigu; "SettingConfiguration"
0x180029467  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x18002946b  mov     rcx, 0FFFFFFFF80000003h; HKEY
0x180029472  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180029477  mov     edi, eax
0x180029479  shr     edi, 1Fh
0x18002947c  lea     rcx, [rbp+57h+lpSubKey]
0x180029480  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180029485  xor     dil, 1
0x180029489  jz      short loc_1800294BD
0x18002948b  mov     r9, [rbp+57h+arg_10]; unsigned __int16 *
0x18002948f  lea     r8, aSettingconfigu; "SettingConfiguration"
0x180029496  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002949d  mov     rcx, r13; HKEY
0x1800294a0  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800294a5  mov     rcx, [rbp+5Fh]; this
0x1800294a9  test    eax, eax
0x1800294ab  jns     short loc_1800294BD
0x1800294ad  mov     r9d, eax; char *
0x1800294b0  mov     r8, rsi; unsigned int
0x1800294b3  mov     edx, 236h; void *
0x1800294b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800294bd  mov     [rbp+57h+lpSubKey], r15
0x1800294c1  mov     [rbp+57h+var_B8], r15
0x1800294c5  mov     [rbp+57h+var_B0], r15
0x1800294c9  mov     r8, rbx
0x1800294cc  lea     rdx, aSSoftwareMicro_0; "%s\\Software\\Microsoft\\Windows NT\\Cu"...
0x1800294d3  lea     rcx, [rbp+57h+lpSubKey]
0x1800294d7  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800294dc  mov     edi, eax
0x1800294de  test    eax, eax
0x1800294e0  jns     short loc_180029519
0x1800294e2  mov     rcx, [rbp+5Fh]; this
0x1800294e6  mov     r9d, eax; char *
0x1800294e9  mov     r8, rsi; unsigned int
0x1800294ec  mov     edx, 23Ah; void *
0x1800294f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800294f6  nop
0x1800294f7  lea     rcx, [rbp+57h+lpSubKey]
0x1800294fb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029500  nop
0x180029501  lea     rcx, [rbp+57h+arg_10]
0x180029505  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002950a  nop
0x18002950b  lea     rcx, [rbp+57h+arg_18]
0x18002950f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029514  jmp     loc_1800293A8
0x180029519  mov     [rbp+57h+var_A8], r15
0x18002951d  lea     rax, [rbp+57h+var_A8]
0x180029521  mov     [rbp+57h+var_80], rax
0x180029525  mov     [rbp+57h+var_78], r15
0x180029529  mov     [rbp+57h+var_70], 1
0x18002952d  lea     rax, [rbp+57h+var_78]
0x180029531  mov     [rsp+110h+phkResult], rax; phkResult
0x180029536  mov     r9d, 20019h; samDesired
0x18002953c  xor     r8d, r8d; ulOptions
0x18002953f  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180029543  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002954a  call    cs:__imp_RegOpenKeyExW
0x180029550  mov     edi, eax
0x180029552  lea     rcx, [rbp+57h+var_80]
0x180029556  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002955b  test    edi, edi
0x18002955d  jnz     loc_18002962F
0x180029563  mov     [rbp+57h+hKey], r15
0x180029567  lea     rax, [rbp+57h+hKey]
0x18002956b  mov     [rbp+57h+var_80], rax
0x18002956f  mov     [rbp+57h+var_78], r15
0x180029573  mov     [rbp+57h+var_70], 1
0x180029577  mov     [rsp+110h+lpdwDisposition], r15; lpdwDisposition
0x18002957c  lea     rax, [rbp+57h+var_78]
0x180029580  mov     [rsp+110h+var_D8], rax; phkResult
0x180029585  mov     [rsp+110h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002958a  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x180029592  mov     dword ptr [rsp+110h+phkResult], r15d; int
0x180029597  xor     r9d, r9d; lpClass
0x18002959a  xor     r8d, r8d; Reserved
0x18002959d  lea     rdx, aSoftwareMicros_30; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800295a4  mov     rcx, r13; hKey
0x1800295a7  call    cs:__imp_RegCreateKeyExW
0x1800295ad  mov     rcx, [rbp+5Fh]; this
0x1800295b1  test    eax, eax
0x1800295b3  jz      short loc_1800295CA
0x1800295b5  mov     r9d, eax; char *
0x1800295b8  mov     r8, rsi; unsigned int
0x1800295bb  mov     edx, 240h; void *
0x1800295c0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800295c5  mov     dil, r15b
0x1800295c8  jmp     short loc_1800295CD
0x1800295ca  mov     dil, 1
0x1800295cd  lea     rcx, [rbp+57h+var_80]
0x1800295d1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800295d6  test    dil, dil
0x1800295d9  jz      short loc_180029625
0x1800295db  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800295df  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800295e3  call    ?CopyRegTreeWithoutACLs@@YAJPEAUHKEY__@@0_N@Z; CopyRegTreeWithoutACLs(HKEY__ *,HKEY__ *,bool)
0x1800295e8  mov     rcx, [rbp+5Fh]; this
0x1800295ec  test    eax, eax
0x1800295ee  jns     short loc_180029625
0x1800295f0  mov     r9d, eax; char *
0x1800295f3  mov     r8, rsi; unsigned int
0x1800295f6  mov     edx, 242h; void *
0x1800295fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029600  xor     edx, edx; lpSubKey
0x180029602  mov     rcx, [rbp+57h+hKey]; hKey
0x180029606  call    cs:__imp_RegDeleteTreeW
0x18002960c  mov     rcx, [rbp+5Fh]; this
0x180029610  test    eax, eax
0x180029612  jz      short loc_180029625
0x180029614  mov     r9d, eax; char *
0x180029617  mov     r8, rsi; unsigned int
0x18002961a  mov     edx, 245h; void *
0x18002961f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180029624  nop
0x180029625  lea     rcx, [rbp+57h+hKey]
0x180029629  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002962e  nop
0x18002962f  lea     rcx, [rbp+57h+var_A8]
0x180029633  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029638  nop
0x180029639  lea     rcx, [rbp+57h+lpSubKey]
0x18002963d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029642  nop
0x180029643  lea     rcx, [rbp+57h+arg_10]
0x180029647  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002964c  nop
0x18002964d  lea     rcx, [rbp+57h+arg_18]
0x180029651  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029656  nop
0x180029657  lea     rcx, [rbp+57h+var_68]
0x18002965b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029660  mov     byte ptr [rbp+57h+hKey], r15b
0x180029664  lea     r8, [rbp+57h+hKey]
0x180029668  mov     edx, r14d
0x18002966b  mov     rcx, [rbp+57h+var_98]
0x18002966f  call    ?s_SetupAutologonIfNecessary@UserOOBEController@@CAJPEBGW4UserOOBEExitReason@@PEA_N@Z; UserOOBEController::s_SetupAutologonIfNecessary(ushort const *,UserOOBEExitReason,bool *)
0x180029674  mov     rcx, [rbp+5Fh]; this
0x180029678  test    eax, eax
0x18002967a  jns     short loc_18002968C
0x18002967c  mov     r9d, eax; char *
0x18002967f  mov     r8, rsi; unsigned int
0x180029682  mov     edx, 24Dh; void *
0x180029687  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002968c  cmp     byte ptr [rbp+57h+hKey], r15b
0x180029690  jz      short loc_1800296FF
0x180029692  mov     dword ptr [rbp+57h+hKey], r15d
0x180029696  lea     rax, [rbp+57h+hKey]
0x18002969a  mov     [rsp+110h+phkResult], rax; int *
0x18002969f  lea     r8, aUnattendsetaut; "UnattendSetAutologon"
0x1800296a6  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800296ad  mov     rcx, r13; HKEY
0x1800296b0  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800296b5  test    eax, eax
0x1800296b7  js      short loc_1800296C3
0x1800296b9  cmp     dword ptr [rbp+57h+hKey], r15d
0x1800296bd  jnz     loc_180029753
0x1800296c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_26370069@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_26370069@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_26370069> `wil::Feature<__WilFeatureTraits_Feature_26370069>::GetImpl(void)'::`2'::impl
0x1800296ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_26370069@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_26370069>::__private_IsEnabled(void)
0x1800296cf  test    al, al
0x1800296d1  jz      short loc_1800296DC
0x1800296d3  call    ?s_IsInteractiveLoginTextMessageConfigured@UserOOBEController@@CA_NXZ; UserOOBEController::s_IsInteractiveLoginTextMessageConfigured(void)
0x1800296d8  test    al, al
0x1800296da  jnz     short loc_180029753
0x1800296dc  mov     r9d, 1
0x1800296e2  lea     r8, aAnimationafter; "AnimationAfterUserOOBE"
0x1800296e9  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800296f0  lea     rcx, aWinlogon; "Winlogon"
0x1800296f7  call    cs:__imp_SetPersistedRegistryDWORD
0x1800296fd  jmp     short loc_180029753
0x1800296ff  cmp     r14d, 1
0x180029703  jnz     short loc_180029753
  ... truncated ...
```
