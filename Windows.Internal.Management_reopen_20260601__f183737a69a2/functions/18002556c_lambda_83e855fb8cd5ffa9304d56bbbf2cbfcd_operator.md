# _lambda_83e855fb8cd5ffa9304d56bbbf2cbfcd_::operator()

- ea: `0x18002556c`
- end: `0x180025ada`
- name: `_lambda_83e855fb8cd5ffa9304d56bbbf2cbfcd_::operator()`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033be0`

## callees

- `0x180004eb0`
- `0x1800089e8`
- `0x180009be4`
- `0x18000a5c4`
- `0x18000dc24`
- `0x180016698`
- `0x180017118`
- `0x18001d064`
- `0x18002335c`
- `0x1800233c4`
- `0x18002556c`
- `0x180033500`
- `0x18003973c`
- `0x1800399b4`
- `0x180039f24`
- `0x18003a394`
- `0x18003a52c`
- `0x18003a904`
- `0x1800a0060`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmRunTask` at `0x1800255a3`
- `DMCmnUtils!DmRunTask` at `0x180025a6a`
- `DMCmnUtils!DmRunTask` at `0x1800255a3`
- `DMCmnUtils!DmRunTask` at `0x180025a6a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800258d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800258d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180025918`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180025918`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180025857`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180025857`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800256a9`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800256a9`

## string_xrefs

- `0x1800255c1`: `NOT A PACKAGE: Couldn't run post reset provisioning task.`
- `0x180025a5a`: `MDMMaintenenceTask`

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
  v42[0] = off_1800C3018;
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
0x18002556c  mov     [rsp+arg_0], rbx
0x180025571  mov     [rsp+arg_8], rsi
0x180025576  push    rdi
0x180025577  sub     rsp, 140h
0x18002557e  mov     rax, cs:__security_cookie
0x180025585  xor     rax, rsp
0x180025588  mov     [rsp+148h+var_10], rax
0x180025590  xor     r9d, r9d
0x180025593  lea     r8, aPostresetboot; "PostResetBoot"
0x18002559a  xor     edx, edx
0x18002559c  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\Management\\Provi"...
0x1800255a3  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x1800255aa  nop     dword ptr [rax+rax+00h]
0x1800255af  xor     esi, esi
0x1800255b1  test    eax, eax
0x1800255b3  jns     short loc_1800255DB
0x1800255b5  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 2
0x1800255bc  jz      short loc_1800255DB
0x1800255be  mov     r9d, eax
0x1800255c1  lea     r8, aNotAPackageCou; "NOT A PACKAGE: Couldn't run post reset "...
0x1800255c8  lea     rdx, PackageFailure
0x1800255cf  lea     rcx, PROVISIONING_DIAGNOSTICS_Context
0x1800255d6  call    McTemplateU0zd_EventWriteTransfer
0x1800255db  mov     [rsp+148h+var_B0], rsi
0x1800255e3  lea     rcx, [rsp+148h+var_B0]
0x1800255eb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800255f0  mov     ebx, eax
0x1800255f2  test    eax, eax
0x1800255f4  jns     short loc_180025617
0x1800255f6  mov     rcx, [rsp+148h]; this
0x1800255fe  mov     r9d, eax; char *
0x180025601  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180025608  mov     edx, 559h; void *
0x18002560d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025612  jmp     loc_180025AA5
0x180025617  lea     rax, off_1800C3018
0x18002561e  mov     [rsp+148h+var_80], rax
0x180025626  lea     rax, [rsp+148h+var_B0]
0x18002562e  mov     [rsp+148h+var_78], rax
0x180025636  lea     rax, [rsp+148h+var_80]
0x18002563e  mov     [rsp+148h+var_18], rax
0x180025646  mov     [rsp+148h+var_E8], rsi
0x18002564b  lea     r9, [rsp+148h+var_E8]
0x180025650  lea     rdx, [rsp+148h+var_88]
0x180025658  call    ??$make_wnf_subscription_state@U_EA_EVENT_HEADER@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_EA_EVENT_HEADER@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@U_EA_EVENT_HEADER@@@01@@Z; wil::details::make_wnf_subscription_state<_EA_EVENT_HEADER>(_WNF_STATE_NAME const &,wistd::function<void (_EA_EVENT_HEADER const &)> &&,ulong,wil::details::wnf_subscription_state<_EA_EVENT_HEADER> * *)
0x18002565d  mov     rcx, rsi
0x180025660  test    eax, eax
0x180025662  cmovns  rcx, [rsp+148h+var_E8]
0x180025668  mov     [rsp+148h+var_E8], rcx
0x18002566d  lea     rcx, [rsp+148h+var_88]
0x180025675  call    ??1?$function@$$A6AXAEBU_EA_EVENT_HEADER@@@Z@wistd@@QEAA@XZ; wistd::function<void (_EA_EVENT_HEADER const &)>::~function<void (_EA_EVENT_HEADER const &)>(void)
0x18002567a  mov     edx, 927C0h; void *
0x18002567f  mov     rcx, [rsp+148h+var_B0]; this
0x180025687  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18002568c  test    al, al
0x18002568e  jnz     short loc_1800256A4
0x180025690  lea     rcx, [rsp+148h+var_E8]
0x180025695  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18002569a  mov     ebx, 80070102h
0x18002569f  jmp     loc_180025AA5
0x1800256a4  mov     [rsp+148h+var_D8], rsi
0x1800256a9  call    cs:__imp_GetDatabaseManagerInstance
0x1800256b0  nop     dword ptr [rax+rax+00h]
0x1800256b5  mov     rdi, rax
0x1800256b8  mov     rcx, [rax]
0x1800256bb  mov     rbx, [rcx+20h]
0x1800256bf  lea     rcx, [rsp+148h+var_D8]
0x1800256c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800256c9  lea     r8, [rsp+148h+var_D8]
0x1800256ce  mov     edx, 2061h
0x1800256d3  mov     rcx, rdi
0x1800256d6  mov     rax, rbx
0x1800256d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256de  mov     ebx, eax
0x1800256e0  test    eax, eax
0x1800256e2  jns     short loc_180025705
0x1800256e4  mov     rcx, [rsp+148h]; this
0x1800256ec  mov     r9d, eax; char *
0x1800256ef  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800256f6  mov     edx, 56Eh; void *
0x1800256fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025700  jmp     loc_180025A8F
0x180025705  mov     [rsp+148h+var_C8], rsi
0x18002570d  mov     rdi, [rsp+148h+var_D8]
0x180025712  mov     rax, [rdi]
0x180025715  mov     rbx, [rax+18h]
0x180025719  lea     rcx, [rsp+148h+var_C8]
0x180025721  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025726  lea     rdx, [rsp+148h+var_C8]
0x18002572e  mov     rcx, rdi
0x180025731  mov     rax, rbx
0x180025734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025739  test    eax, eax
0x18002573b  jnz     loc_180025A57
0x180025741  mov     [rsp+148h+pszMore], rsi
0x180025746  mov     rdi, [rsp+148h+var_C8]
0x18002574e  mov     rax, [rdi]
0x180025751  mov     rbx, [rax+20h]
0x180025755  xor     edx, edx
0x180025757  lea     rcx, [rsp+148h+pszMore]
0x18002575c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025761  lea     rdx, [rsp+148h+pszMore]
0x180025766  mov     rcx, rdi
0x180025769  mov     rax, rbx
0x18002576c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025771  mov     ebx, eax
0x180025773  test    eax, eax
0x180025775  jns     short loc_1800257A4
0x180025777  mov     rcx, [rsp+148h]; this
0x18002577f  mov     r9d, eax; char *
0x180025782  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180025789  mov     edx, 574h; void *
0x18002578e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025793  nop
0x180025794  lea     rcx, [rsp+148h+pszMore]
0x180025799  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002579e  nop
0x18002579f  jmp     loc_180025A81
0x1800257a4  mov     [rsp+148h+hKey], rsi
0x1800257ac  xor     edx, edx
0x1800257ae  lea     rcx, [rsp+148h+hKey]
0x1800257b6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800257bb  xor     r9d, r9d; HKEY *
0x1800257be  lea     r8, [rsp+148h+hKey]; unsigned __int16 *
0x1800257c6  xor     edx, edx; PCWSTR
0x1800257c8  mov     rcx, [rsp+148h+pszMore]; pszMore
0x1800257cd  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1800257d2  mov     ebx, eax
0x1800257d4  test    eax, eax
0x1800257d6  jns     short loc_180025804
0x1800257d8  mov     r9d, eax; char *
0x1800257db  mov     edx, 577h; void *
0x1800257e0  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800257e7  mov     rcx, [rsp+148h]; this
0x1800257ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800257f4  nop
0x1800257f5  lea     rcx, [rsp+148h+hKey]
0x1800257fd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180025802  jmp     short loc_180025794
0x180025804  mov     [rsp+148h+cSubKeys], esi
0x18002580b  mov     [rsp+148h+cbMaxSubKeyLen], esi
0x18002580f  mov     [rsp+148h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180025814  mov     [rsp+148h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180025819  mov     [rsp+148h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18002581e  mov     [rsp+148h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180025823  mov     [rsp+148h+lpcValues], rsi; lpcValues
0x180025828  mov     [rsp+148h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18002582d  lea     rax, [rsp+148h+cbMaxSubKeyLen]
0x180025832  mov     [rsp+148h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180025837  lea     rax, [rsp+148h+cSubKeys]
0x18002583f  mov     [rsp+148h+lpcSubKeys], rax; unsigned int
0x180025844  xor     r9d, r9d; lpReserved
0x180025847  xor     r8d, r8d; lpcchClass
0x18002584a  xor     edx, edx; lpClass
0x18002584c  mov     rbx, [rsp+148h+hKey]
0x180025854  mov     rcx, rbx; hKey
0x180025857  call    cs:__imp_RegQueryInfoKeyW
0x18002585e  nop     dword ptr [rax+rax+00h]
0x180025863  test    eax, eax
0x180025865  jz      short loc_18002588A
0x180025867  mov     rcx, [rsp+148h]; this
0x18002586f  mov     r9d, eax; char *
0x180025872  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180025879  mov     edx, 57Ch; void *
0x18002587e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180025883  mov     ebx, eax
0x180025885  jmp     loc_1800257F5
0x18002588a  mov     eax, [rsp+148h+cbMaxSubKeyLen]
0x18002588e  lea     ecx, [rax+1]
0x180025891  cmp     ecx, eax
0x180025893  jb      loc_180025A3D
0x180025899  mov     [rsp+148h+cbMaxSubKeyLen], ecx
0x18002589d  xorps   xmm0, xmm0
0x1800258a0  movdqu  xmmword ptr [rsp+148h+lpSubKey], xmm0
0x1800258a9  mov     [rsp+148h+var_90], rsi
0x1800258b1  mov     edx, ecx
0x1800258b3  lea     rcx, [rsp+148h+lpSubKey]
0x1800258bb  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800258c0  nop
0x1800258c1  jmp     short loc_1800258E4
0x1800258c3  xor     r9d, r9d; Reserved
0x1800258c6  xor     r8d, r8d; samDesired
0x1800258c9  mov     rdx, [rsp+148h+lpSubKey]; lpSubKey
0x1800258d1  mov     rcx, rbx; hKey
0x1800258d4  call    cs:__imp_RegDeleteKeyExW
0x1800258db  nop     dword ptr [rax+rax+00h]
0x1800258e0  test    eax, eax
0x1800258e2  jnz     short loc_18002593E
0x1800258e4  mov     [rsp+148h+lpcValues], rsi; lpftLastWriteTime
0x1800258e9  mov     [rsp+148h+lpcbMaxClassLen], rsi; lpcchClass
0x1800258ee  mov     [rsp+148h+lpcbMaxSubKeyLen], rsi; lpClass
0x1800258f3  mov     eax, [rsp+148h+cbMaxSubKeyLen]
0x1800258f7  mov     [rsp+148h+lpcSubKeys], rsi; unsigned int
0x1800258fc  mov     [rsp+148h+cchName], eax
0x180025903  lea     r9, [rsp+148h+cchName]; lpcchName
0x18002590b  mov     r8, [rsp+148h+lpSubKey]; lpName
0x180025913  xor     edx, edx; dwIndex
0x180025915  mov     rcx, rbx; hKey
0x180025918  call    cs:__imp_RegEnumKeyExW
0x18002591f  nop     dword ptr [rax+rax+00h]
0x180025924  test    eax, eax
0x180025926  jz      short loc_1800258C3
0x180025928  cmp     eax, 103h
0x18002592d  jz      loc_1800259BF
0x180025933  test    eax, eax
0x180025935  jz      short loc_18002596E
0x180025937  mov     edx, 590h
0x18002593c  jmp     short loc_180025943
0x18002593e  mov     edx, 595h; void *
0x180025943  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002594a  mov     r9d, eax; char *
0x18002594d  mov     rcx, [rsp+148h]; this
0x180025955  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002595a  mov     ebx, eax
0x18002595c  lea     rcx, [rsp+148h+lpSubKey]
0x180025964  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180025969  jmp     loc_1800257F5
0x18002596e  lea     rcx, [rsp+148h+lpSubKey]
0x180025976  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18002597b  nop
0x18002597c  lea     rcx, [rsp+148h+hKey]
0x180025984  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180025989  nop
0x18002598a  lea     rcx, [rsp+148h+pszMore]
0x18002598f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025994  nop
0x180025995  lea     rcx, [rsp+148h+var_C8]
0x18002599d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800259a2  nop
0x1800259a3  lea     rcx, [rsp+148h+var_D8]
0x1800259a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800259ad  nop
0x1800259ae  lea     rcx, [rsp+148h+var_E8]
0x1800259b3  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800259b8  mov     ebx, esi
0x1800259ba  jmp     loc_180025AA5
0x1800259bf  lea     rcx, [rsp+148h+lpSubKey]
0x1800259c7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800259cc  nop
0x1800259cd  lea     rcx, [rsp+148h+hKey]
0x1800259d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800259da  nop
0x1800259db  lea     rcx, [rsp+148h+pszMore]
0x1800259e0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800259e5  jmp     loc_18002570D
0x1800259ea  lea     rcx, [rsp+148h+lpSubKey]
0x1800259f2  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800259f7  nop
0x1800259f8  lea     rcx, [rsp+148h+hKey]
0x180025a00  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180025a05  nop
0x180025a06  lea     rcx, [rsp+148h+pszMore]
0x180025a0b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025a10  nop
0x180025a11  lea     rcx, [rsp+148h+var_C8]
0x180025a19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a1e  nop
0x180025a1f  lea     rcx, [rsp+148h+var_D8]
0x180025a24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a29  nop
0x180025a2a  lea     rcx, [rsp+148h+var_E8]
0x180025a2f  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180025a34  mov     ebx, [rsp+148h+var_A4]
0x180025a3b  jmp     short loc_180025AA5
0x180025a3d  mov     [rsp+148h+cbMaxSubKeyLen], 0FFFFFFFFh
0x180025a45  mov     ebx, 80070216h
0x180025a4a  mov     r9d, ebx
0x180025a4d  mov     edx, 57Eh
0x180025a52  jmp     loc_1800257E0
0x180025a57  xor     r9d, r9d
0x180025a5a  lea     r8, aMdmmaintenence; "MDMMaintenenceTask"
0x180025a61  xor     edx, edx
0x180025a63  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180025a6a  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x180025a71  nop     dword ptr [rax+rax+00h]
0x180025a76  nop
0x180025a77  mov     ebx, esi
0x180025a79  cmp     eax, 80070002h
0x180025a7e  cmovnz  ebx, eax
0x180025a81  lea     rcx, [rsp+148h+var_C8]
0x180025a89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a8e  nop
0x180025a8f  lea     rcx, [rsp+148h+var_D8]
0x180025a94  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a99  nop
0x180025a9a  lea     rcx, [rsp+148h+var_E8]
0x180025a9f  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180025aa4  nop
0x180025aa5  lea     rcx, [rsp+148h+var_B0]
0x180025aad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025ab2  mov     eax, ebx
0x180025ab4  mov     rcx, [rsp+148h+var_10]
0x180025abc  xor     rcx, rsp; StackCookie
0x180025abf  call    __security_check_cookie
0x180025ac4  lea     r11, [rsp+148h+var_8]
0x180025acc  mov     rbx, [r11+10h]
0x180025ad0  mov     rsi, [r11+18h]
0x180025ad4  mov     rsp, r11
0x180025ad7  pop     rdi
0x180025ad8  retn
  ... truncated ...
```
