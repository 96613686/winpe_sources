# CProcessStateManager::RuntimeClassInitialize(IAutoLogonManager *,IBlockedShutdownDataConsumer *,IReturnToLockListener *)

- ea: `0x18000d2c8`
- end: `0x18000df08`
- name: `?RuntimeClassInitialize@CProcessStateManager@@QEAAJPEAUIAutoLogonManager@@PEAUIBlockedShutdownDataConsumer@@PEAUIReturnToLockListener@@@Z`
- size: `3136`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this, struct IAutoLogonManager *, struct IBlockedShutdownDataConsumer *, struct IReturnToLockListener *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020948`

## callees

- `0x180004c2c`
- `0x18000cd1c`
- `0x18000d2c8`
- `0x18000df10`
- `0x18000df3c`
- `0x18000dffc`
- `0x18000e0ec`
- `0x18000e338`
- `0x18000e480`
- `0x18000e528`
- `0x18000e5c8`
- `0x18000e72c`
- `0x18000e998`
- `0x18000e9dc`
- `0x18005d488`
- `0x18005d508`
- `0x18005f1a0`
- `0x180062028`
- `0x180064cb4`
- `0x18006c000`
- `0x18006f0d8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d99c`
- `KERNEL32!SetLastError` at `0x18000da2c`
- `KERNEL32!SetLastError` at `0x18000dc08`
- `KERNEL32!SetLastError` at `0x18000dc94`
- `KERNEL32!SetLastError` at `0x18000de9d`
- `KERNEL32!SetLastError` at `0x18000d99c`
- `KERNEL32!SetLastError` at `0x18000da2c`
- `KERNEL32!SetLastError` at `0x18000dc08`
- `KERNEL32!SetLastError` at `0x18000dc94`
- `KERNEL32!SetLastError` at `0x18000de9d`
- `KERNEL32!GetLastError` at `0x18000d989`
- `KERNEL32!GetLastError` at `0x18000da1a`
- `KERNEL32!GetLastError` at `0x18000dbf5`
- `KERNEL32!GetLastError` at `0x18000dc82`
- `KERNEL32!GetLastError` at `0x18000de8b`
- `KERNEL32!GetLastError` at `0x18000d989`
- `KERNEL32!GetLastError` at `0x18000da1a`
- `KERNEL32!GetLastError` at `0x18000dbf5`
- `KERNEL32!GetLastError` at `0x18000dc82`
- `KERNEL32!GetLastError` at `0x18000de8b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d4ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d5ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d684`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d786`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d4ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d5ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d684`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d476`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d476`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d466`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d466`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d435`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d435`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000d994`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000dc00`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000d994`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000dc00`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000d95f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000dbcb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000de08`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000d95f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000dbcb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000de08`
- `ntdll!NtQueryWnfStateData` at `0x18000d8d3`
- `ntdll!NtQueryWnfStateData` at `0x18000db3d`
- `ntdll!NtQueryWnfStateData` at `0x18000dd76`
- `ntdll!NtQueryWnfStateData` at `0x18000d8d3`
- `ntdll!NtQueryWnfStateData` at `0x18000db3d`
- `ntdll!NtQueryWnfStateData` at `0x18000dd76`

## pseudocode

```c
__int64 __fastcall CProcessStateManager::RuntimeClassInitialize(
        CProcessStateManager *this,
        struct IAutoLogonManager *a2,
        struct IBlockedShutdownDataConsumer *a3,
        struct IReturnToLockListener *a4)
{
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  BOOL v12; // esi
  LSTATUS ValueW; // eax
  unsigned __int64 v14; // rcx
  signed int v15; // ebx
  int IsFirstLogonAfterSignOut; // eax
  unsigned int v17; // r14d
  LSTATUS v18; // eax
  signed int v19; // ecx
  LSTATUS v20; // eax
  signed int v21; // ecx
  bool v22; // al
  int v23; // eax
  unsigned int v24; // esi
  bool v25; // si
  LSTATUS v26; // eax
  wil::details *v27; // r15
  HKEY *v28; // rsi
  int v29; // r14d
  __int64 v30; // r8
  int v31; // ebx
  int v32; // edx
  HKEY v33; // rax
  HKEY *v34; // r12
  HKEY v35; // r13
  DWORD LastError; // ebx
  wil::details **v37; // rsi
  wil::details *v38; // r12
  DWORD v39; // ebx
  struct wil::details::wnf_subscription_state_base *v40; // rdx
  wil::details *v41; // r15
  HKEY *v42; // rax
  HKEY *v43; // rsi
  __int64 v44; // r8
  int v45; // ebx
  int v46; // edx
  HKEY v47; // rax
  HKEY *v48; // r12
  HKEY v49; // r13
  DWORD v50; // ebx
  wil::details **v51; // rsi
  wil::details *v52; // r12
  DWORD v53; // ebx
  struct wil::details::wnf_subscription_state_base *v54; // rdx
  wil::details *v55; // rsi
  HKEY *v56; // rax
  HKEY *v57; // rbx
  __int64 v58; // r8
  int v59; // r14d
  wil::details **v60; // r14
  wil::details *v61; // r15
  DWORD v62; // ebx
  struct wil::details::wnf_subscription_state_base *v63; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  int dwOptionsc; // [rsp+20h] [rbp-E0h]
  int dwOptionsd; // [rsp+20h] [rbp-E0h]
  int dwOptionse; // [rsp+20h] [rbp-E0h]
  unsigned int pvData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  CProcessStateManager *v72; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY *v74; // [rsp+70h] [rbp-90h]
  HKEY v75; // [rsp+78h] [rbp-88h] BYREF
  char v76; // [rsp+80h] [rbp-80h]
  char v77; // [rsp+88h] [rbp-78h] BYREF
  char v78; // [rsp+90h] [rbp-70h] BYREF
  char v79; // [rsp+98h] [rbp-68h] BYREF
  char v80[8]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v81[13]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v82; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  if ( *((struct IAutoLogonManager **)this + 12) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct IAutoLogonManager *))(*(_QWORD *)a2 + 8LL))(a2);
    *(_QWORD *)Data = *((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = a2;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(Data);
  }
  if ( *((struct IBlockedShutdownDataConsumer **)this + 16) != a3 )
  {
    *(_QWORD *)Data = a3;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(Data);
    *(_QWORD *)Data = *((_QWORD *)this + 16);
    *((_QWORD *)this + 16) = a3;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(Data);
  }
  if ( *((struct IReturnToLockListener **)this + 17) != a4 )
  {
    if ( a4 )
      (*(void (__fastcall **)(struct IReturnToLockListener *))(*(_QWORD *)a4 + 8LL))(a4);
    v8 = *((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = a4;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  CProcessStateManager::_InitializeSessionData(this);
  CProcessStateManager::_InitializeFirstLogon(this);
  CProcessStateManager::_InitializeUserSid(this);
  *((_BYTE *)this + 537) = CLanguageProfileHelper::IsUserInputMethodLoadingEnabled();
  v9 = CProcessStateManager::_RunDelayedInit(this);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
      (const char *)(unsigned int)v9,
      dwOptions);
    return v10;
  }
  *(_DWORD *)Data = 0;
  hKey = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
          0,
          0,
          0,
          2u,
          0,
          &hKey,
          0) )
  {
    RegSetValueExW(hKey, L"IdleTime", 0, 4u, Data, 4u);
    if ( hKey != HKEY_LOCAL_MACHINE )
      RegCloseKey(hKey);
  }
  CProcessStateManager::_InitializeEmbeddedPolicy(this);
  CProcessStateManager::_InitializeOobeZDPRebootRequired(this);
  v12 = 0;
  LODWORD(hKey) = 0;
  *(_DWORD *)Data = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
             L"IsFirstLogonAfterSignOut",
             0x10000012u,
             (LPDWORD)&hKey,
             &pvData,
             (LPDWORD)Data);
  v14 = (unsigned int)ValueW;
  LOWORD(v15) = 13;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      LOWORD(v14) = 13;
    }
    else if ( ValueW <= 0 )
    {
      goto LABEL_28;
    }
    goto LABEL_27;
  }
  LOWORD(v14) = 13;
  if ( (_DWORD)hKey != 4 )
  {
    if ( *(_DWORD *)Data == 4 && (unsigned __int16)(pvData - 48) <= 1u )
    {
      v12 = (_WORD)pvData == 49;
      v14 = 0;
      goto LABEL_28;
    }
LABEL_27:
    v14 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_28;
  }
  if ( pvData > 1 )
    goto LABEL_27;
  v14 = 0;
  LOBYTE(v12) = pvData == 1;
LABEL_28:
  if ( (v14 & 0x80000000) == 0LL )
  {
    *((_BYTE *)this + 592) = v12;
    if ( v12 )
      *((_DWORD *)this + 128) |= 0x400u;
    IsFirstLogonAfterSignOut = CProcessStateManager::SetIsFirstLogonAfterSignOut((CProcessStateManager *)v14, 0);
    v17 = IsFirstLogonAfterSignOut;
    if ( IsFirstLogonAfterSignOut < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
        (const char *)(unsigned int)IsFirstLogonAfterSignOut,
        dwOptionsa);
      return v17;
    }
  }
  *(_DWORD *)Data = 0;
  LODWORD(hKey) = 4;
  v18 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
          L"Enabled",
          0x10000012u,
          (LPDWORD)Data,
          &pvData,
          (LPDWORD)&hKey);
  v19 = v18;
  if ( v18 )
  {
    if ( v18 == 234 )
    {
      LOWORD(v19) = 13;
    }
    else if ( v18 <= 0 )
    {
      goto LABEL_44;
    }
    goto LABEL_43;
  }
  LOWORD(v19) = 13;
  if ( *(_DWORD *)Data != 4 )
  {
    if ( (_DWORD)hKey == 4 && (unsigned __int16)(pvData - 48) <= 1u )
    {
      v12 = (_WORD)pvData == 49;
      v19 = 0;
      goto LABEL_44;
    }
LABEL_43:
    v19 = (unsigned __int16)v19 | 0x80070000;
    goto LABEL_44;
  }
  if ( pvData > 1 )
    goto LABEL_43;
  v19 = 0;
  v12 = pvData == 1;
LABEL_44:
  if ( v19 >= 0 && v12 )
    *((_BYTE *)this + 453) = 1;
  *(_DWORD *)Data = 0;
  LODWORD(hKey) = 4;
  v20 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Power",
          L"LidNotifyReliable",
          0x10000012u,
          (LPDWORD)Data,
          &pvData,
          (LPDWORD)&hKey);
  v21 = v20;
  if ( v20 )
  {
    if ( v20 == 234 )
    {
      LOWORD(v21) = 13;
    }
    else if ( v20 <= 0 )
    {
      goto LABEL_58;
    }
  }
  else
  {
    LOWORD(v21) = 13;
    if ( *(_DWORD *)Data == 4 )
    {
      if ( pvData <= 1 )
      {
        v21 = 0;
        v12 = pvData == 1;
        goto LABEL_58;
      }
    }
    else if ( (_DWORD)hKey == 4 && (unsigned __int16)(pvData - 48) <= 1u )
    {
      v12 = (_WORD)pvData == 49;
      v21 = 0;
      goto LABEL_58;
    }
  }
  v21 = (unsigned __int16)v21 | 0x80070000;
LABEL_58:
  if ( v21 < 0 )
  {
    if ( (unsigned int)(v21 + 2147024894) <= 1 || (v22 = 0, v21 == -2147023728) )
      v22 = 1;
  }
  else
  {
    v22 = v12;
  }
  *((_BYTE *)this + 104) = v22;
  v23 = CProcessStateManager::_InitializeDisplayState(this);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
      (const char *)(unsigned int)v23,
      dwOptionsb);
    return v24;
  }
  v25 = 0;
  *(_DWORD *)Data = 0;
  LODWORD(hKey) = 4;
  v26 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"EnableLogonHIDControls",
          0x10000012u,
          (LPDWORD)Data,
          &pvData,
          (LPDWORD)&hKey);
  if ( !v26 )
  {
    if ( *(_DWORD *)Data == 4 )
    {
      if ( pvData <= 1 )
      {
        v15 = 0;
        v25 = pvData == 1;
        goto LABEL_75;
      }
    }
    else if ( (_DWORD)hKey == 4 && (unsigned __int16)(pvData - 48) <= 1u )
    {
      v25 = (_WORD)pvData == 49;
      v15 = 0;
      goto LABEL_75;
    }
    goto LABEL_74;
  }
  if ( v26 == 234 || (v15 = v26, v26 > 0) )
LABEL_74:
    v15 = (unsigned __int16)v15 | 0x80070000;
LABEL_75:
  if ( v15 >= 0 )
    *((_BYTE *)this + 593) = v25;
  (*(void (__fastcall **)(CProcessStateManager *))(*(_QWORD *)this + 8LL))(this);
  (*(void (__fastcall **)(CProcessStateManager *))(*(_QWORD *)this + 8LL))(this);
  v81[0] = &off_18009E070;
  v81[1] = this;
  v81[2] = this;
  v82 = v81;
  pvData = 0;
  v27 = 0;
  v28 = (HKEY *)operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  v29 = -2147024882;
  if ( v28 )
  {
    v28[1] = 0;
    *v28 = (HKEY)&wil::details::wnf_subscription_state<unsigned long>::`vftable';
    if ( v82 )
    {
      v28[16] = (HKEY)(v28 + 3);
      (*(void (__fastcall **)(_QWORD *))(*v82 + 16LL))(v82);
      (*(void (__fastcall **)(_QWORD *))(*v82 + 24LL))(v82);
      v82 = 0;
    }
    else
    {
      v28[16] = 0;
    }
    v30 = pvData;
    if ( pvData == -1 )
    {
      *(_DWORD *)Data = 0;
      v31 = NtQueryWnfStateData(&WNF_LOGN_SLIDE_TO_SHUTDOWN, 0, 0, &pvData) | 0x10000000;
      if ( (int)(v31 + 0x80000000) >= 0 && v31 != -805306333 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
          (const char *)(unsigned int)v31,
          0);
LABEL_85:
        (*(void (__fastcall **)(HKEY *, __int64))*v28)(v28, 1);
        goto LABEL_95;
      }
      v30 = pvData;
    }
    v74 = v28 + 1;
    v75 = 0;
    v76 = 1;
    dwOptionsd = (int)v28;
    v32 = RtlSubscribeWnfStateChangeNotification(
            &v75,
            WNF_LOGN_SLIDE_TO_SHUTDOWN,
            v30,
            _lambda_d93655bd33d44513d4ad201382c30aa7_::_lambda_invoker_cdecl_);
    *(_DWORD *)Data = v32;
    if ( v76 )
    {
      v33 = v75;
      hKey = v75;
      v34 = v74;
      v35 = *v74;
      if ( *v74 )
      {
        LastError = GetLastError();
        RtlUnsubscribeWnfStateChangeNotification(v35);
        SetLastError(LastError);
        v33 = hKey;
        v32 = *(_DWORD *)Data;
      }
      *v34 = v33;
    }
    if ( v32 < 0 )
    {
      v31 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x3C7,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
              (const char *)(unsigned int)v32,
              (int)v28);
      goto LABEL_85;
    }
    v27 = (wil::details *)v28;
    v31 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)0x8007000ELL,
      dwOptionsc);
    v31 = -2147024882;
  }
LABEL_95:
  if ( v31 < 0 )
    v27 = 0;
  v37 = (wil::details **)((char *)this + 144);
  if ( (char *)this + 144 == &v77 )
  {
    if ( v27 )
      (**(void (__fastcall ***)(wil::details *, __int64))v27)(v27, 1);
  }
  else
  {
    v38 = *v37;
    if ( *v37 )
    {
      v39 = GetLastError();
      wil::details::delete_wnf_subscription_state(v38, v40);
      SetLastError(v39);
    }
    *v37 = v27;
  }
  if ( v82 )
    (*(void (__fastcall **)(_QWORD *))(*v82 + 24LL))(v82);
  *(_QWORD *)Data = this;
  (*(void (__fastcall **)(CProcessStateManager *))(*(_QWORD *)this + 8LL))(this);
  v72 = this;
  v82 = 0;
  v82 = (_QWORD *)wistd::__function::__func__lambda_2db06854ef4c5bc5560d3ae5cb2f60da__void___cdecl_void__::__func__lambda_2db06854ef4c5bc5560d3ae5cb2f60da__void___cdecl_void__(
                    v81,
                    Data);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(Data);
  pvData = 0;
  v41 = 0;
  v42 = (HKEY *)operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  v43 = v42;
  if ( v42 )
  {
    v42[1] = 0;
    *v42 = (HKEY)&wil::details::wnf_subscription_state<unsigned long>::`vftable';
    if ( v82 )
    {
      v42[16] = (HKEY)(v42 + 3);
      (*(void (__fastcall **)(_QWORD *))(*v82 + 16LL))(v82);
      (*(void (__fastcall **)(_QWORD *))(*v82 + 24LL))(v82);
      v82 = 0;
    }
    else
    {
      v42[16] = 0;
    }
    v44 = pvData;
    if ( pvData == -1 )
    {
      *(_DWORD *)Data = 0;
      v45 = NtQueryWnfStateData(&WNF_LOGN_RETURN_TO_LOCK, 0, 0, &pvData) | 0x10000000;
      if ( (int)(v45 + 0x80000000) >= 0 && v45 != -805306333 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
          (const char *)(unsigned int)v45,
          0);
LABEL_113:
        (*(void (__fastcall **)(HKEY *, __int64))*v43)(v43, 1);
        goto LABEL_123;
      }
      v44 = pvData;
    }
    v74 = v43 + 1;
    v75 = 0;
    v76 = 1;
    dwOptionse = (int)v43;
    v46 = RtlSubscribeWnfStateChangeNotification(
            &v75,
            WNF_LOGN_RETURN_TO_LOCK,
            v44,
            _lambda_d93655bd33d44513d4ad201382c30aa7_::_lambda_invoker_cdecl_);
    *(_DWORD *)Data = v46;
    if ( v76 )
    {
      v47 = v75;
      hKey = v75;
      v48 = v74;
      v49 = *v74;
      if ( *v74 )
      {
        v50 = GetLastError();
        RtlUnsubscribeWnfStateChangeNotification(v49);
        SetLastError(v50);
        v47 = hKey;
        v46 = *(_DWORD *)Data;
      }
      *v48 = v47;
    }
    if ( v46 < 0 )
    {
      v45 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x3C7,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
              (const char *)(unsigned int)v46,
              (int)v43);
      goto LABEL_113;
    }
    v41 = (wil::details *)v43;
    v45 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)0x8007000ELL,
      dwOptionsd);
    v45 = -2147024882;
  }
LABEL_123:
  if ( v45 < 0 )
    v41 = 0;
  v51 = (wil::details **)((char *)this + 152);
  if ( (char *)this + 152 == &v78 )
  {
    if ( v41 )
      (**(void (__fastcall ***)(wil::details *, __int64))v41)(v41, 1);
  }
  else
  {
    v52 = *v51;
    if ( *v51 )
    {
      v53 = GetLastError();
      wil::details::delete_wnf_subscription_state(v52, v54);
      SetLastError(v53);
    }
    *v51 = v41;
  }
  if ( v82 )
    (*(void (__fastcall **)(_QWORD *))(*v82 + 24LL))(v82);
  *(_QWORD *)Data = this;
  (*(void (__fastcall **)(CProcessStateManager *))(*(_QWORD *)this + 8LL))(this);
  v72 = this;
  v82 = 0;
  v82 = (_QWORD *)wistd::__function::__func__lambda_9230362c65f26d02c8520847a52916e9__void___cdecl_unsigned_long_const____::__func__lambda_9230362c65f26d02c8520847a52916e9__void___cdecl_unsigned_long_const____(
                    v81,
                    Data);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(Data);
  pvData = 0;
  v55 = 0;
  v56 = (HKEY *)operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  v57 = v56;
  if ( !v56 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)0x8007000ELL,
      dwOptionse);
    goto LABEL_146;
  }
  v56[1] = 0;
  *v56 = (HKEY)&wil::details::wnf_subscription_state<unsigned long>::`vftable';
  wistd::function<void (unsigned long const &)>::function<void (unsigned long const &)>(v56 + 2, v80);
  v58 = pvData;
  if ( pvData == -1 )
  {
    *(_DWORD *)Data = 0;
    v29 = NtQueryWnfStateData(&WNF_NGC_CREDENTIAL_RESET_EXPERIENCE_ACTIVE, 0, 0, &pvData) | 0x10000000;
    if ( (int)(v29 + 0x80000000) >= 0 && v29 != -805306333 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
        (const char *)(unsigned int)v29,
        0);
      goto LABEL_138;
    }
    v58 = pvData;
  }
  v74 = v57 + 1;
  v75 = 0;
  v76 = 1;
  v59 = RtlSubscribeWnfStateChangeNotification(
          &v75,
          WNF_NGC_CREDENTIAL_RESET_EXPERIENCE_ACTIVE,
          v58,
          _lambda_a14e49ce427a1853f087bba834558a2c_::_lambda_invoker_cdecl_);
  if ( v76 )
    wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(
      v74,
      v75);
  if ( v59 >= 0 )
  {
    v55 = (wil::details *)v57;
    v29 = 0;
    goto LABEL_146;
  }
  v29 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x3C7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
          (const char *)(unsigned int)v59,
          (int)v57);
LABEL_138:
  (*(void (__fastcall **)(HKEY *, __int64))*v57)(v57, 1);
LABEL_146:
  if ( v29 < 0 )
    v55 = 0;
  v60 = (wil::details **)((char *)this + 160);
  if ( (char *)this + 160 == &v79 )
  {
    if ( v55 )
      (**(void (__fastcall ***)(wil::details *, __int64))v55)(v55, 1);
  }
  else
  {
    v61 = *v60;
    if ( *v60 )
    {
      v62 = GetLastError();
      wil::details::delete_wnf_subscription_state(v61, v63);
      SetLastError(v62);
    }
    *v60 = v55;
  }
  if ( v82 )
    (*(void (__fastcall **)(_QWORD *))(*v82 + 24LL))(v82);
  (*(void (__fastcall **)(CProcessStateManager *))(*(_QWORD *)this + 16LL))(this);
  return 0;
}

```

## disassembly

```asm
0x18000d2c8  push    rbp
0x18000d2ca  push    rbx
0x18000d2cb  push    rsi
0x18000d2cc  push    rdi
0x18000d2cd  push    r12
0x18000d2cf  push    r13
0x18000d2d1  push    r14
0x18000d2d3  push    r15
0x18000d2d5  lea     rbp, [rsp-28h]
0x18000d2da  sub     rsp, 128h
0x18000d2e1  mov     rax, cs:__security_cookie
0x18000d2e8  xor     rax, rsp
0x18000d2eb  mov     [rbp+60h+var_48], rax
0x18000d2ef  mov     rbx, r9
0x18000d2f2  mov     r14, r8
0x18000d2f5  mov     rsi, rdx
0x18000d2f8  mov     rdi, rcx
0x18000d2fb  xor     r13d, r13d
0x18000d2fe  cmp     [rcx+60h], rdx
0x18000d302  jz      short loc_18000D330
0x18000d304  test    rdx, rdx
0x18000d307  jz      short loc_18000D319
0x18000d309  mov     rax, [rdx]
0x18000d30c  mov     rcx, rdx
0x18000d30f  mov     rax, [rax+8]
0x18000d313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d318  nop
0x18000d319  mov     rax, [rdi+60h]
0x18000d31d  mov     qword ptr [rsp+160h+Data], rax
0x18000d322  mov     [rdi+60h], rsi
0x18000d326  lea     rcx, [rsp+160h+Data]
0x18000d32b  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18000d330  cmp     [rdi+80h], r14
0x18000d337  jz      short loc_18000D365
0x18000d339  mov     qword ptr [rsp+160h+Data], r14
0x18000d33e  lea     rcx, [rsp+160h+Data]
0x18000d343  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18000d348  mov     rax, [rdi+80h]
0x18000d34f  mov     qword ptr [rsp+160h+Data], rax
0x18000d354  mov     [rdi+80h], r14
0x18000d35b  lea     rcx, [rsp+160h+Data]
0x18000d360  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18000d365  cmp     [rdi+88h], rbx
0x18000d36c  jz      short loc_18000D3A3
0x18000d36e  test    rbx, rbx
0x18000d371  jz      short loc_18000D383
0x18000d373  mov     rax, [rbx]
0x18000d376  mov     rcx, rbx
0x18000d379  mov     rax, [rax+8]
0x18000d37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d382  nop
0x18000d383  mov     rcx, [rdi+88h]
0x18000d38a  mov     [rdi+88h], rbx
0x18000d391  test    rcx, rcx
0x18000d394  jz      short loc_18000D3A3
0x18000d396  mov     rax, [rcx]
0x18000d399  mov     rax, [rax+10h]
0x18000d39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a2  nop
0x18000d3a3  mov     rcx, rdi; this
0x18000d3a6  call    ?_InitializeSessionData@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_InitializeSessionData(void)
0x18000d3ab  mov     rcx, rdi; this
0x18000d3ae  call    ?_InitializeFirstLogon@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_InitializeFirstLogon(void)
0x18000d3b3  mov     rcx, rdi; this
0x18000d3b6  call    ?_InitializeUserSid@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_InitializeUserSid(void)
0x18000d3bb  call    ?IsUserInputMethodLoadingEnabled@CLanguageProfileHelper@@SA_NXZ; CLanguageProfileHelper::IsUserInputMethodLoadingEnabled(void)
0x18000d3c0  mov     [rdi+219h], al
0x18000d3c6  mov     rcx, rdi; this
0x18000d3c9  call    ?_RunDelayedInit@CProcessStateManager@@AEAAJXZ; CProcessStateManager::_RunDelayedInit(void)
0x18000d3ce  mov     ebx, eax
0x18000d3d0  test    eax, eax
0x18000d3d2  jns     short loc_18000D3F3
0x18000d3d4  mov     rcx, [rbp+68h]; this
0x18000d3d8  mov     r9d, eax; char *
0x18000d3db  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x18000d3e2  mov     edx, 95h; void *
0x18000d3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3ec  mov     eax, ebx
0x18000d3ee  jmp     loc_18000DEE8
0x18000d3f3  mov     dword ptr [rsp+160h+Data], r13d
0x18000d3f8  mov     [rsp+160h+hKey], r13
0x18000d3fd  mov     [rsp+160h+lpdwDisposition], r13; lpdwDisposition
0x18000d402  lea     rax, [rsp+160h+hKey]
0x18000d407  mov     [rsp+160h+phkResult], rax; phkResult
0x18000d40c  mov     [rsp+160h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18000d411  mov     [rsp+160h+samDesired], 2; samDesired
0x18000d419  mov     [rsp+160h+dwOptions], r13d; dwOptions
0x18000d41e  xor     r9d, r9d; lpClass
0x18000d421  xor     r8d, r8d; Reserved
0x18000d424  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d42b  mov     r14, 0FFFFFFFF80000002h
0x18000d432  mov     rcx, r14; hKey
0x18000d435  call    cs:__imp_RegCreateKeyExW
0x18000d43b  mov     r15d, 4
0x18000d441  test    eax, eax
0x18000d443  jnz     short loc_18000D47C
0x18000d445  mov     [rsp+160h+samDesired], r15d; cbData
0x18000d44a  lea     rax, [rsp+160h+Data]
0x18000d44f  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x18000d454  mov     r9d, r15d; dwType
0x18000d457  xor     r8d, r8d; Reserved
0x18000d45a  lea     rdx, aIdletime; "IdleTime"
0x18000d461  mov     rcx, [rsp+160h+hKey]; hKey
0x18000d466  call    cs:__imp_RegSetValueExW
0x18000d46c  mov     rcx, [rsp+160h+hKey]; hKey
0x18000d471  cmp     rcx, r14
0x18000d474  jz      short loc_18000D47C
0x18000d476  call    cs:__imp_RegCloseKey
0x18000d47c  mov     rcx, rdi; this
0x18000d47f  call    ?_InitializeEmbeddedPolicy@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_InitializeEmbeddedPolicy(void)
0x18000d484  mov     rcx, rdi; this
0x18000d487  call    ?_InitializeOobeZDPRebootRequired@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_InitializeOobeZDPRebootRequired(void)
0x18000d48c  mov     esi, r13d
0x18000d48f  mov     dword ptr [rsp+160h+hKey], r13d
0x18000d494  mov     dword ptr [rsp+160h+Data], r15d
0x18000d499  lea     rax, [rsp+160h+Data]
0x18000d49e  mov     [rsp+160h+lpSecurityAttributes], rax; pcbData
0x18000d4a3  lea     rax, [rsp+160h+pvData]
0x18000d4a8  mov     qword ptr [rsp+160h+samDesired], rax; pvData
0x18000d4ad  lea     rax, [rsp+160h+hKey]
0x18000d4b2  mov     qword ptr [rsp+160h+dwOptions], rax; int
0x18000d4b7  mov     r9d, 10000012h; dwFlags
0x18000d4bd  lea     r8, aIsfirstlogonaf; "IsFirstLogonAfterSignOut"
0x18000d4c4  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d4cb  mov     rcx, r14; hkey
0x18000d4ce  call    cs:__imp_RegGetValueW
0x18000d4d4  mov     ecx, eax
0x18000d4d6  mov     edx, 31h ; '1'
0x18000d4db  lea     ebx, [rdx-24h]
0x18000d4de  lea     r12d, [rdx-30h]
0x18000d4e2  test    eax, eax
0x18000d4e4  jnz     short loc_18000D526
0x18000d4e6  mov     ecx, ebx
0x18000d4e8  cmp     dword ptr [rsp+160h+hKey], r15d
0x18000d4ed  jnz     short loc_18000D4FF
0x18000d4ef  cmp     [rsp+160h+pvData], r12d
0x18000d4f4  ja      short loc_18000D535
0x18000d4f6  mov     ecx, r13d
0x18000d4f9  setz    sil
0x18000d4fd  jmp     short loc_18000D53E
0x18000d4ff  cmp     dword ptr [rsp+160h+Data], r15d
0x18000d504  jnz     short loc_18000D535
0x18000d506  movzx   eax, word ptr [rsp+160h+pvData]
0x18000d50b  sub     ax, 30h ; '0'
0x18000d50f  cmp     ax, r12w
0x18000d513  ja      short loc_18000D535
0x18000d515  mov     esi, r13d
0x18000d518  cmp     dx, word ptr [rsp+160h+pvData]
0x18000d51d  setz    sil
0x18000d521  mov     ecx, r13d
0x18000d524  jmp     short loc_18000D53E
0x18000d526  cmp     eax, 0EAh
0x18000d52b  jnz     short loc_18000D531
0x18000d52d  mov     ecx, ebx
0x18000d52f  jmp     short loc_18000D535
0x18000d531  test    eax, eax
0x18000d533  jle     short loc_18000D53E
0x18000d535  movzx   ecx, cx
0x18000d538  or      ecx, 80070000h; this
0x18000d53e  test    ecx, ecx
0x18000d540  js      short loc_18000D58B
0x18000d542  mov     [rdi+250h], sil
0x18000d549  test    sil, sil
0x18000d54c  jz      short loc_18000D556
0x18000d54e  bts     dword ptr [rdi+200h], 0Ah
0x18000d556  xor     edx, edx; unsigned __int8
0x18000d558  call    ?SetIsFirstLogonAfterSignOut@CProcessStateManager@@QEAAJE@Z; CProcessStateManager::SetIsFirstLogonAfterSignOut(uchar)
0x18000d55d  mov     r14d, eax
0x18000d560  test    eax, eax
0x18000d562  jns     short loc_18000D584
0x18000d564  mov     rcx, [rbp+68h]; this
0x18000d568  mov     r9d, eax; char *
0x18000d56b  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x18000d572  mov     edx, 0A5h; void *
0x18000d577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d57c  mov     eax, r14d
0x18000d57f  jmp     loc_18000DEE8
0x18000d584  mov     r14, 0FFFFFFFF80000002h
0x18000d58b  mov     dword ptr [rsp+160h+Data], r13d
0x18000d590  mov     dword ptr [rsp+160h+hKey], r15d
0x18000d595  lea     rax, [rsp+160h+hKey]
0x18000d59a  mov     [rsp+160h+lpSecurityAttributes], rax; pcbData
0x18000d59f  lea     rax, [rsp+160h+pvData]
0x18000d5a4  mov     qword ptr [rsp+160h+samDesired], rax; pvData
0x18000d5a9  lea     rax, [rsp+160h+Data]
0x18000d5ae  mov     qword ptr [rsp+160h+dwOptions], rax; pdwType
0x18000d5b3  mov     r9d, 10000012h; dwFlags
0x18000d5b9  lea     r8, aEnabled; "Enabled"
0x18000d5c0  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d5c7  mov     rcx, r14; hkey
0x18000d5ca  call    cs:__imp_RegGetValueW
0x18000d5d0  mov     ecx, eax
0x18000d5d2  test    eax, eax
0x18000d5d4  jnz     short loc_18000D61E
0x18000d5d6  mov     ecx, ebx
0x18000d5d8  cmp     dword ptr [rsp+160h+Data], r15d
0x18000d5dd  jnz     short loc_18000D5F2
0x18000d5df  cmp     [rsp+160h+pvData], r12d
0x18000d5e4  ja      short loc_18000D62D
0x18000d5e6  mov     ecx, r13d
0x18000d5e9  mov     esi, r13d
0x18000d5ec  setz    sil
0x18000d5f0  jmp     short loc_18000D636
0x18000d5f2  cmp     dword ptr [rsp+160h+hKey], r15d
0x18000d5f7  jnz     short loc_18000D62D
0x18000d5f9  movzx   eax, word ptr [rsp+160h+pvData]
0x18000d5fe  sub     ax, 30h ; '0'
0x18000d602  cmp     ax, r12w
0x18000d606  ja      short loc_18000D62D
0x18000d608  mov     esi, r13d
0x18000d60b  mov     eax, 31h ; '1'
0x18000d610  cmp     ax, word ptr [rsp+160h+pvData]
0x18000d615  setz    sil
0x18000d619  mov     ecx, r13d
0x18000d61c  jmp     short loc_18000D636
0x18000d61e  cmp     eax, 0EAh
0x18000d623  jnz     short loc_18000D629
0x18000d625  mov     ecx, ebx
0x18000d627  jmp     short loc_18000D62D
0x18000d629  test    eax, eax
0x18000d62b  jle     short loc_18000D636
0x18000d62d  movzx   ecx, cx
0x18000d630  or      ecx, 80070000h
0x18000d636  test    ecx, ecx
0x18000d638  js      short loc_18000D645
0x18000d63a  test    esi, esi
0x18000d63c  jz      short loc_18000D645
0x18000d63e  mov     [rdi+1C5h], r12b
0x18000d645  mov     dword ptr [rsp+160h+Data], r13d
0x18000d64a  mov     dword ptr [rsp+160h+hKey], r15d
0x18000d64f  lea     rax, [rsp+160h+hKey]
0x18000d654  mov     [rsp+160h+lpSecurityAttributes], rax; pcbData
0x18000d659  lea     rax, [rsp+160h+pvData]
0x18000d65e  mov     qword ptr [rsp+160h+samDesired], rax; pvData
0x18000d663  lea     rax, [rsp+160h+Data]
0x18000d668  mov     qword ptr [rsp+160h+dwOptions], rax; int
0x18000d66d  mov     r9d, 10000012h; dwFlags
0x18000d673  lea     r8, aLidnotifyrelia; "LidNotifyReliable"
0x18000d67a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pow"...
0x18000d681  mov     rcx, r14; hkey
0x18000d684  call    cs:__imp_RegGetValueW
0x18000d68a  mov     ecx, eax
0x18000d68c  test    eax, eax
0x18000d68e  jnz     short loc_18000D6D8
0x18000d690  mov     ecx, ebx
0x18000d692  cmp     dword ptr [rsp+160h+Data], r15d
0x18000d697  jnz     short loc_18000D6AC
0x18000d699  cmp     [rsp+160h+pvData], r12d
0x18000d69e  ja      short loc_18000D6E7
0x18000d6a0  mov     ecx, r13d
0x18000d6a3  mov     esi, r13d
0x18000d6a6  setz    sil
0x18000d6aa  jmp     short loc_18000D6F0
0x18000d6ac  cmp     dword ptr [rsp+160h+hKey], r15d
0x18000d6b1  jnz     short loc_18000D6E7
0x18000d6b3  movzx   eax, word ptr [rsp+160h+pvData]
0x18000d6b8  sub     ax, 30h ; '0'
0x18000d6bc  cmp     ax, r12w
0x18000d6c0  ja      short loc_18000D6E7
0x18000d6c2  mov     esi, r13d
0x18000d6c5  mov     eax, 31h ; '1'
0x18000d6ca  cmp     ax, word ptr [rsp+160h+pvData]
0x18000d6cf  setz    sil
0x18000d6d3  mov     ecx, r13d
0x18000d6d6  jmp     short loc_18000D6F0
0x18000d6d8  cmp     eax, 0EAh
0x18000d6dd  jnz     short loc_18000D6E3
0x18000d6df  mov     ecx, ebx
0x18000d6e1  jmp     short loc_18000D6E7
0x18000d6e3  test    eax, eax
0x18000d6e5  jle     short loc_18000D6F0
0x18000d6e7  movzx   ecx, cx
0x18000d6ea  or      ecx, 80070000h
0x18000d6f0  test    ecx, ecx
0x18000d6f2  js      short loc_18000D6FB
0x18000d6f4  test    esi, esi
0x18000d6f6  setnz   al
0x18000d6f9  jmp     short loc_18000D714
0x18000d6fb  lea     eax, [rcx+7FF8FFFEh]
0x18000d701  cmp     eax, r12d
0x18000d704  jbe     short loc_18000D711
0x18000d706  cmp     ecx, 80070490h
0x18000d70c  mov     eax, r13d
0x18000d70f  jnz     short loc_18000D714
0x18000d711  mov     eax, r12d
0x18000d714  mov     [rdi+68h], al
0x18000d717  mov     rcx, rdi; this
0x18000d71a  call    ?_InitializeDisplayState@CProcessStateManager@@AEAAJXZ; CProcessStateManager::_InitializeDisplayState(void)
0x18000d71f  mov     esi, eax
0x18000d721  test    eax, eax
0x18000d723  jns     short loc_18000D744
0x18000d725  mov     rcx, [rbp+68h]; this
0x18000d729  mov     r9d, eax; char *
0x18000d72c  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x18000d733  mov     edx, 0B1h; void *
0x18000d738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d73d  mov     eax, esi
0x18000d73f  jmp     loc_18000DEE8
0x18000d744  mov     esi, r13d
0x18000d747  mov     dword ptr [rsp+160h+Data], r13d
  ... truncated ...
```
