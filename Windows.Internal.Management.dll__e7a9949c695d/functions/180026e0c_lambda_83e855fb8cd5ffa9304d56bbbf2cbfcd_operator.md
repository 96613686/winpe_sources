# _lambda_83e855fb8cd5ffa9304d56bbbf2cbfcd_::operator()

- ea: `0x180026e0c`
- end: `0x180027355`
- name: `_lambda_83e855fb8cd5ffa9304d56bbbf2cbfcd_::operator()`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034b10`

## callees

- `0x180004d50`
- `0x180008880`
- `0x18000992c`
- `0x18000a2a4`
- `0x18000d730`
- `0x180015f70`
- `0x1800169b8`
- `0x18001eb38`
- `0x180024cd0`
- `0x180024d2c`
- `0x180026e0c`
- `0x18003446c`
- `0x18003a430`
- `0x18003a690`
- `0x18003abb4`
- `0x18003b004`
- `0x18003b198`
- `0x18003b544`
- `0x18009d138`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmRunTask` at `0x180026e43`
- `DMCmnUtils!DmRunTask` at `0x1800272ec`
- `DMCmnUtils!DmRunTask` at `0x180026e43`
- `DMCmnUtils!DmRunTask` at `0x1800272ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180027162`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180027162`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800271a0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800271a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800270eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800270eb`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180026f43`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180026f43`

## string_xrefs

- `0x180026e5b`: `NOT A PACKAGE: Couldn't run post reset provisioning task.`
- `0x1800272dc`: `MDMMaintenenceTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 lambda_83e855fb8cd5ffa9304d56bbbf2cbfcd_::operator()()
{
  int v0; // eax
  int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // r8
  unsigned int v4; // ebx
  int wnf_subscription; // eax
  __int64 v6; // rcx
  unsigned int v7; // r8d
  int v8; // r9d
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  unsigned int (__fastcall *v13)(__int64, __int64 *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, PCWSTR *); // rbx
  int v16; // eax
  int FirstSyncKey; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  HKEY v20; // rbx
  unsigned int v21; // eax
  DWORD v22; // ecx
  const char *v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-128h]
  __int64 v29; // [rsp+60h] [rbp-E8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-D8h] BYREF
  PCWSTR pszMore; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+80h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-B8h] BYREF
  wil *v36; // [rsp+98h] [rbp-B0h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp-A8h] BYREF
  unsigned int v38; // [rsp+A4h] [rbp-A4h]
  LPCWSTR lpSubKey[2]; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-90h]
  _BYTE v41[8]; // [rsp+C0h] [rbp-88h] BYREF
  _QWORD v42[14]; // [rsp+C8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v0 = DmRunTask(L"\\Microsoft\\Windows\\Management\\Provisioning", 0, L"PostResetBoot", 0);
  if ( v0 < 0 && (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      PROVISIONING_DIAGNOSTICS_Context,
      PackageFailure,
      L"NOT A PACKAGE: Couldn't run post reset provisioning task.",
      (unsigned int)v0);
  v36 = 0;
  v1 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&v36);
  v4 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x559,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v1,
      lpcSubKeys);
    goto LABEL_37;
  }
  v42[0] = off_1800BF018;
  v42[1] = &v36;
  v42[13] = v42;
  v29 = 0;
  wnf_subscription = wil::details::make_wnf_subscription_state<_EA_EVENT_HEADER>(v2, v41, v3, &v29);
  v6 = 0;
  if ( wnf_subscription >= 0 )
    v6 = v29;
  v29 = v6;
  wistd::function<void (_EA_EVENT_HEADER const &)>::~function<void (_EA_EVENT_HEADER const &)>(v41);
  if ( !wil::handle_wait(v36, (void *)0x927C0, v7, v8) )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v29);
    v4 = -2147024638;
    goto LABEL_37;
  }
  v31 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v11 = v10(DatabaseManagerInstance, 8289, &v31);
  v4 = v11;
  if ( v11 >= 0 )
  {
    v33 = 0;
    while ( 1 )
    {
      v12 = v31;
      v13 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      if ( v13(v12, &v33) )
        break;
      pszMore = 0;
      v14 = v33;
      v15 = *(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v33 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszMore,
        0);
      v16 = v15(v14, &pszMore);
      v4 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x574,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)v16,
          lpcSubKeys);
        goto LABEL_16;
      }
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      FirstSyncKey = FirstSync::GetFirstSyncKey(pszMore, 0, (unsigned __int16 *)&hKey, 0);
      v4 = FirstSyncKey;
      if ( FirstSyncKey < 0 )
      {
        v18 = (unsigned int)FirstSyncKey;
        v19 = 1399;
        goto LABEL_19;
      }
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      v20 = hKey;
      v21 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v21 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x57C,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
               (const char *)v21,
               lpcSubKeys);
        goto LABEL_20;
      }
      v22 = cbMaxSubKeyLen + 1;
      if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
      {
        cbMaxSubKeyLen = -1;
        v4 = -2147024362;
        v18 = 2147942934LL;
        v19 = 1406;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)v18,
          lpcSubKeys);
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_16:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
LABEL_35:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        goto LABEL_36;
      }
      try
      {
        ++cbMaxSubKeyLen;
        *(_OWORD *)lpSubKey = 0;
        v40 = 0;
        std::vector<unsigned short>::reserve(lpSubKey, v22);
      }
      catch ( ... )
      {
        v38 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x584,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
                v23);
        std::vector<unsigned short>::_Tidy(lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v29);
        v4 = v38;
        goto LABEL_37;
      }
      while ( 1 )
      {
        cchName = cbMaxSubKeyLen;
        v24 = RegEnumKeyExW(v20, 0, (LPWSTR)lpSubKey[0], &cchName, 0, 0, 0, 0);
        if ( v24 )
          break;
        v24 = RegDeleteKeyExW(v20, lpSubKey[0], 0, 0);
        if ( v24 )
        {
          v25 = 1429;
          goto LABEL_30;
        }
      }
      if ( v24 != 259 )
      {
        v25 = 1424;
LABEL_30:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v25,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
               (const char *)v24,
               lpcSubKeys);
        std::vector<unsigned short>::_Tidy(lpSubKey);
        goto LABEL_20;
      }
      std::vector<unsigned short>::_Tidy(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
    }
    v26 = DmRunTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", 0, L"MDMMaintenenceTask", 0);
    v4 = 0;
    if ( v26 != -2147024894 )
      v4 = v26;
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56E,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
    (const char *)(unsigned int)v11,
    lpcSubKeys);
LABEL_36:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v29);
LABEL_37:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
  return v4;
}

```

## disassembly

```asm
0x180026e0c  mov     [rsp+arg_0], rbx
0x180026e11  mov     [rsp+arg_8], rsi
0x180026e16  push    rdi
0x180026e17  sub     rsp, 140h
0x180026e1e  mov     rax, cs:__security_cookie
0x180026e25  xor     rax, rsp
0x180026e28  mov     [rsp+148h+var_10], rax
0x180026e30  xor     r9d, r9d
0x180026e33  lea     r8, aPostresetboot; "PostResetBoot"
0x180026e3a  xor     edx, edx
0x180026e3c  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\Management\\Provi"...
0x180026e43  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x180026e49  xor     esi, esi
0x180026e4b  test    eax, eax
0x180026e4d  jns     short loc_180026E75
0x180026e4f  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 2
0x180026e56  jz      short loc_180026E75
0x180026e58  mov     r9d, eax
0x180026e5b  lea     r8, aNotAPackageCou; "NOT A PACKAGE: Couldn't run post reset "...
0x180026e62  lea     rdx, PackageFailure
0x180026e69  lea     rcx, PROVISIONING_DIAGNOSTICS_Context
0x180026e70  call    McTemplateU0zd_EventWriteTransfer
0x180026e75  mov     [rsp+148h+var_B0], rsi
0x180026e7d  lea     rcx, [rsp+148h+var_B0]
0x180026e85  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180026e8a  mov     ebx, eax
0x180026e8c  test    eax, eax
0x180026e8e  jns     short loc_180026EB1
0x180026e90  mov     rcx, [rsp+148h]; this
0x180026e98  mov     r9d, eax; char *
0x180026e9b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180026ea2  mov     edx, 559h; void *
0x180026ea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026eac  jmp     loc_180027321
0x180026eb1  lea     rax, off_1800BF018
0x180026eb8  mov     [rsp+148h+var_80], rax
0x180026ec0  lea     rax, [rsp+148h+var_B0]
0x180026ec8  mov     [rsp+148h+var_78], rax
0x180026ed0  lea     rax, [rsp+148h+var_80]
0x180026ed8  mov     [rsp+148h+var_18], rax
0x180026ee0  mov     [rsp+148h+var_E8], rsi
0x180026ee5  lea     r9, [rsp+148h+var_E8]
0x180026eea  lea     rdx, [rsp+148h+var_88]
0x180026ef2  call    ??$make_wnf_subscription_state@U_EA_EVENT_HEADER@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_EA_EVENT_HEADER@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@U_EA_EVENT_HEADER@@@01@@Z; wil::details::make_wnf_subscription_state<_EA_EVENT_HEADER>(_WNF_STATE_NAME const &,wistd::function<void (_EA_EVENT_HEADER const &)> &&,ulong,wil::details::wnf_subscription_state<_EA_EVENT_HEADER> * *)
0x180026ef7  mov     rcx, rsi
0x180026efa  test    eax, eax
0x180026efc  cmovns  rcx, [rsp+148h+var_E8]
0x180026f02  mov     [rsp+148h+var_E8], rcx
0x180026f07  lea     rcx, [rsp+148h+var_88]
0x180026f0f  call    ??1?$function@$$A6AXAEBU_EA_EVENT_HEADER@@@Z@wistd@@QEAA@XZ; wistd::function<void (_EA_EVENT_HEADER const &)>::~function<void (_EA_EVENT_HEADER const &)>(void)
0x180026f14  mov     edx, 927C0h; void *
0x180026f19  mov     rcx, [rsp+148h+var_B0]; this
0x180026f21  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180026f26  test    al, al
0x180026f28  jnz     short loc_180026F3E
0x180026f2a  lea     rcx, [rsp+148h+var_E8]
0x180026f2f  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180026f34  mov     ebx, 80070102h
0x180026f39  jmp     loc_180027321
0x180026f3e  mov     [rsp+148h+var_D8], rsi
0x180026f43  call    cs:__imp_GetDatabaseManagerInstance
0x180026f49  mov     rdi, rax
0x180026f4c  mov     rcx, [rax]
0x180026f4f  mov     rbx, [rcx+20h]
0x180026f53  lea     rcx, [rsp+148h+var_D8]
0x180026f58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026f5d  lea     r8, [rsp+148h+var_D8]
0x180026f62  mov     edx, 2061h
0x180026f67  mov     rcx, rdi
0x180026f6a  mov     rax, rbx
0x180026f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f72  mov     ebx, eax
0x180026f74  test    eax, eax
0x180026f76  jns     short loc_180026F99
0x180026f78  mov     rcx, [rsp+148h]; this
0x180026f80  mov     r9d, eax; char *
0x180026f83  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180026f8a  mov     edx, 56Eh; void *
0x180026f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f94  jmp     loc_18002730B
0x180026f99  mov     [rsp+148h+var_C8], rsi
0x180026fa1  mov     rdi, [rsp+148h+var_D8]
0x180026fa6  mov     rax, [rdi]
0x180026fa9  mov     rbx, [rax+18h]
0x180026fad  lea     rcx, [rsp+148h+var_C8]
0x180026fb5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026fba  lea     rdx, [rsp+148h+var_C8]
0x180026fc2  mov     rcx, rdi
0x180026fc5  mov     rax, rbx
0x180026fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fcd  test    eax, eax
0x180026fcf  jnz     loc_1800272D9
0x180026fd5  mov     [rsp+148h+pszMore], rsi
0x180026fda  mov     rdi, [rsp+148h+var_C8]
0x180026fe2  mov     rax, [rdi]
0x180026fe5  mov     rbx, [rax+20h]
0x180026fe9  xor     edx, edx
0x180026feb  lea     rcx, [rsp+148h+pszMore]
0x180026ff0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026ff5  lea     rdx, [rsp+148h+pszMore]
0x180026ffa  mov     rcx, rdi
0x180026ffd  mov     rax, rbx
0x180027000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027005  mov     ebx, eax
0x180027007  test    eax, eax
0x180027009  jns     short loc_180027038
0x18002700b  mov     rcx, [rsp+148h]; this
0x180027013  mov     r9d, eax; char *
0x180027016  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002701d  mov     edx, 574h; void *
0x180027022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027027  nop
0x180027028  lea     rcx, [rsp+148h+pszMore]
0x18002702d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027032  nop
0x180027033  jmp     loc_1800272FD
0x180027038  mov     [rsp+148h+hKey], rsi
0x180027040  xor     edx, edx
0x180027042  lea     rcx, [rsp+148h+hKey]
0x18002704a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002704f  xor     r9d, r9d; HKEY *
0x180027052  lea     r8, [rsp+148h+hKey]; unsigned __int16 *
0x18002705a  xor     edx, edx; PCWSTR
0x18002705c  mov     rcx, [rsp+148h+pszMore]; pszMore
0x180027061  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x180027066  mov     ebx, eax
0x180027068  test    eax, eax
0x18002706a  jns     short loc_180027098
0x18002706c  mov     r9d, eax; char *
0x18002706f  mov     edx, 577h; void *
0x180027074  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002707b  mov     rcx, [rsp+148h]; this
0x180027083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027088  nop
0x180027089  lea     rcx, [rsp+148h+hKey]
0x180027091  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027096  jmp     short loc_180027028
0x180027098  mov     [rsp+148h+cSubKeys], esi
0x18002709f  mov     [rsp+148h+cbMaxSubKeyLen], esi
0x1800270a3  mov     [rsp+148h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800270a8  mov     [rsp+148h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800270ad  mov     [rsp+148h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800270b2  mov     [rsp+148h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800270b7  mov     [rsp+148h+lpcValues], rsi; lpcValues
0x1800270bc  mov     [rsp+148h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800270c1  lea     rax, [rsp+148h+cbMaxSubKeyLen]
0x1800270c6  mov     [rsp+148h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800270cb  lea     rax, [rsp+148h+cSubKeys]
0x1800270d3  mov     [rsp+148h+lpcSubKeys], rax; unsigned int
0x1800270d8  xor     r9d, r9d; lpReserved
0x1800270db  xor     r8d, r8d; lpcchClass
0x1800270de  xor     edx, edx; lpClass
0x1800270e0  mov     rbx, [rsp+148h+hKey]
0x1800270e8  mov     rcx, rbx; hKey
0x1800270eb  call    cs:__imp_RegQueryInfoKeyW
0x1800270f1  test    eax, eax
0x1800270f3  jz      short loc_180027118
0x1800270f5  mov     rcx, [rsp+148h]; this
0x1800270fd  mov     r9d, eax; char *
0x180027100  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180027107  mov     edx, 57Ch; void *
0x18002710c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027111  mov     ebx, eax
0x180027113  jmp     loc_180027089
0x180027118  mov     eax, [rsp+148h+cbMaxSubKeyLen]
0x18002711c  lea     ecx, [rax+1]
0x18002711f  cmp     ecx, eax
0x180027121  jb      loc_1800272BF
0x180027127  mov     [rsp+148h+cbMaxSubKeyLen], ecx
0x18002712b  xorps   xmm0, xmm0
0x18002712e  movdqu  xmmword ptr [rsp+148h+lpSubKey], xmm0
0x180027137  mov     [rsp+148h+var_90], rsi
0x18002713f  mov     edx, ecx
0x180027141  lea     rcx, [rsp+148h+lpSubKey]
0x180027149  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x18002714e  nop
0x18002714f  jmp     short loc_18002716C
0x180027151  xor     r9d, r9d; Reserved
0x180027154  xor     r8d, r8d; samDesired
0x180027157  mov     rdx, [rsp+148h+lpSubKey]; lpSubKey
0x18002715f  mov     rcx, rbx; hKey
0x180027162  call    cs:__imp_RegDeleteKeyExW
0x180027168  test    eax, eax
0x18002716a  jnz     short loc_1800271C0
0x18002716c  mov     [rsp+148h+lpcValues], rsi; lpftLastWriteTime
0x180027171  mov     [rsp+148h+lpcbMaxClassLen], rsi; lpcchClass
0x180027176  mov     [rsp+148h+lpcbMaxSubKeyLen], rsi; lpClass
0x18002717b  mov     eax, [rsp+148h+cbMaxSubKeyLen]
0x18002717f  mov     [rsp+148h+lpcSubKeys], rsi; unsigned int
0x180027184  mov     [rsp+148h+cchName], eax
0x18002718b  lea     r9, [rsp+148h+cchName]; lpcchName
0x180027193  mov     r8, [rsp+148h+lpSubKey]; lpName
0x18002719b  xor     edx, edx; dwIndex
0x18002719d  mov     rcx, rbx; hKey
0x1800271a0  call    cs:__imp_RegEnumKeyExW
0x1800271a6  test    eax, eax
0x1800271a8  jz      short loc_180027151
0x1800271aa  cmp     eax, 103h
0x1800271af  jz      loc_180027241
0x1800271b5  test    eax, eax
0x1800271b7  jz      short loc_1800271F0
0x1800271b9  mov     edx, 590h
0x1800271be  jmp     short loc_1800271C5
0x1800271c0  mov     edx, 595h; void *
0x1800271c5  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800271cc  mov     r9d, eax; char *
0x1800271cf  mov     rcx, [rsp+148h]; this
0x1800271d7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800271dc  mov     ebx, eax
0x1800271de  lea     rcx, [rsp+148h+lpSubKey]
0x1800271e6  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800271eb  jmp     loc_180027089
0x1800271f0  lea     rcx, [rsp+148h+lpSubKey]
0x1800271f8  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800271fd  nop
0x1800271fe  lea     rcx, [rsp+148h+hKey]
0x180027206  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002720b  nop
0x18002720c  lea     rcx, [rsp+148h+pszMore]
0x180027211  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027216  nop
0x180027217  lea     rcx, [rsp+148h+var_C8]
0x18002721f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027224  nop
0x180027225  lea     rcx, [rsp+148h+var_D8]
0x18002722a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002722f  nop
0x180027230  lea     rcx, [rsp+148h+var_E8]
0x180027235  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18002723a  mov     ebx, esi
0x18002723c  jmp     loc_180027321
0x180027241  lea     rcx, [rsp+148h+lpSubKey]
0x180027249  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18002724e  nop
0x18002724f  lea     rcx, [rsp+148h+hKey]
0x180027257  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002725c  nop
0x18002725d  lea     rcx, [rsp+148h+pszMore]
0x180027262  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027267  jmp     loc_180026FA1
0x18002726c  lea     rcx, [rsp+148h+lpSubKey]
0x180027274  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180027279  nop
0x18002727a  lea     rcx, [rsp+148h+hKey]
0x180027282  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027287  nop
0x180027288  lea     rcx, [rsp+148h+pszMore]
0x18002728d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027292  nop
0x180027293  lea     rcx, [rsp+148h+var_C8]
0x18002729b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800272a0  nop
0x1800272a1  lea     rcx, [rsp+148h+var_D8]
0x1800272a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800272ab  nop
0x1800272ac  lea     rcx, [rsp+148h+var_E8]
0x1800272b1  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800272b6  mov     ebx, [rsp+148h+var_A4]
0x1800272bd  jmp     short loc_180027321
0x1800272bf  mov     [rsp+148h+cbMaxSubKeyLen], 0FFFFFFFFh
0x1800272c7  mov     ebx, 80070216h
0x1800272cc  mov     r9d, ebx
0x1800272cf  mov     edx, 57Eh
0x1800272d4  jmp     loc_180027074
0x1800272d9  xor     r9d, r9d
0x1800272dc  lea     r8, aMdmmaintenence; "MDMMaintenenceTask"
0x1800272e3  xor     edx, edx
0x1800272e5  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800272ec  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x1800272f2  nop
0x1800272f3  mov     ebx, esi
0x1800272f5  cmp     eax, 80070002h
0x1800272fa  cmovnz  ebx, eax
0x1800272fd  lea     rcx, [rsp+148h+var_C8]
0x180027305  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002730a  nop
0x18002730b  lea     rcx, [rsp+148h+var_D8]
0x180027310  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027315  nop
0x180027316  lea     rcx, [rsp+148h+var_E8]
0x18002731b  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180027320  nop
0x180027321  lea     rcx, [rsp+148h+var_B0]
0x180027329  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002732e  mov     eax, ebx
0x180027330  mov     rcx, [rsp+148h+var_10]
0x180027338  xor     rcx, rsp; StackCookie
0x18002733b  call    __security_check_cookie
0x180027340  lea     r11, [rsp+148h+var_8]
0x180027348  mov     rbx, [r11+10h]
0x18002734c  mov     rsi, [r11+18h]
0x180027350  mov     rsp, r11
0x180027353  pop     rdi
0x180027354  retn
```
