# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogAppsState(ushort const * const,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState>>> const &)

- ea: `0x1800cd4b4`
- end: `0x1800cd7ab`
- name: `?LogAppsState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJQEBGAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@@std@@@2@@std@@@Z`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c961c`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x1800cc544`
- `0x1800cd4b4`
- `0x1800d0440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd540`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd5da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd540`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd5da`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cd66f`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cd66f`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cd703`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cd703`

## string_xrefs

- `0x1800cd567`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd5f5`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd720`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd75e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogAppsState(
        __int64 a1,
        __int64 a2)
{
  __int64 ProviderSubkeyName; // rax
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 **v11; // rdi
  __int64 *i; // rbx
  const unsigned __int16 *v13; // rax
  int DWORD; // eax
  unsigned int v15; // esi
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 *v19; // rdx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  unsigned int v22; // esi
  DWORD dwOptions; // [rsp+20h] [rbp-98h]
  unsigned int v24; // [rsp+50h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v27[32]; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ProviderSubkeyName = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(
                         v27,
                         a1);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ProviderSubkeyName);
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v27);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3C1,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
           (const char *)v6,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v7;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v9 = RegCreateKeyExW(hKey, L"LastLoggedState", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3CD,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
            (const char *)v9,
            dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v10;
  }
  v11 = *(__int64 ***)(a2 + 8);
  for ( i = *v11; ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)v11 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    v24 = 0;
    v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
    DWORD = OmaDmRegistryGetDWORD(phkResult, 0, v13, &v24);
    v15 = DWORD;
    if ( DWORD <= -2147024895 || (unsigned int)(DWORD + 2147024892) <= 0x7FF8FFFB )
      break;
    v16 = *((_DWORD *)i + 12);
    if ( v24 == v16 )
      goto LABEL_18;
    if ( v16 == 3 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) == 0 )
        goto LABEL_18;
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
      v19 = AutopilotManagerProviderAppInstallationSucceeded;
      goto LABEL_17;
    }
    if ( v16 == 2 && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
      v19 = AutopilotManagerProviderAppInstallationTrackingStarted;
LABEL_17:
      McTemplateU0zz_EventWriteTransfer(v18, v19, L"Application", v17);
    }
LABEL_18:
    v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
    v21 = OmaDmRegistrySetDWORD(phkResult, 0, v20, *((_DWORD *)i + 12));
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
        (const char *)(unsigned int)v21,
        dwOptions);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v22;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D3,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
    (const char *)(unsigned int)DWORD,
    dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v15;
}

```

## disassembly

```asm
0x1800cd4b4  push    rbx
0x1800cd4b6  push    rsi
0x1800cd4b7  push    rdi
0x1800cd4b8  push    r14
0x1800cd4ba  sub     rsp, 98h
0x1800cd4c1  mov     rax, cs:__security_cookie
0x1800cd4c8  xor     rax, rsp
0x1800cd4cb  mov     [rsp+0B8h+var_30], rax
0x1800cd4d3  mov     rdi, rdx
0x1800cd4d6  mov     rbx, rcx
0x1800cd4d9  mov     [rsp+0B8h+hKey], 0
0x1800cd4e2  xor     edx, edx
0x1800cd4e4  lea     rcx, [rsp+0B8h+hKey]
0x1800cd4e9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cd4ee  mov     rdx, rbx
0x1800cd4f1  lea     rcx, [rsp+0B8h+var_50]
0x1800cd4f6  call    ?GetProviderSubkeyName@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(ushort const * const)
0x1800cd4fb  mov     rcx, rax
0x1800cd4fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cd503  mov     [rsp+0B8h+lpdwDisposition], 0; lpdwDisposition
0x1800cd50c  lea     rcx, [rsp+0B8h+hKey]
0x1800cd511  mov     [rsp+0B8h+phkResult], rcx; phkResult
0x1800cd516  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd51f  mov     esi, 0F003Fh
0x1800cd524  mov     [rsp+0B8h+samDesired], esi; samDesired
0x1800cd528  mov     [rsp+0B8h+dwOptions], 0; unsigned int
0x1800cd530  xor     r9d, r9d; lpClass
0x1800cd533  xor     r8d, r8d; Reserved
0x1800cd536  mov     rdx, rax; lpSubKey
0x1800cd539  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cd540  call    cs:__imp_RegCreateKeyExW
0x1800cd547  nop     dword ptr [rax+rax+00h]
0x1800cd54c  mov     ebx, eax
0x1800cd54e  lea     rcx, [rsp+0B8h+var_50]
0x1800cd553  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd558  test    ebx, ebx
0x1800cd55a  jz      short loc_1800CD58B
0x1800cd55c  mov     rcx, [rsp+0B8h]; this
0x1800cd564  mov     r9d, ebx; char *
0x1800cd567  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd56e  mov     edx, 3C1h; void *
0x1800cd573  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cd578  mov     ebx, eax
0x1800cd57a  lea     rcx, [rsp+0B8h+hKey]
0x1800cd57f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd584  mov     eax, ebx
0x1800cd586  jmp     loc_1800CD78D
0x1800cd58b  mov     [rsp+0B8h+var_60], 0
0x1800cd594  xor     edx, edx
0x1800cd596  lea     rcx, [rsp+0B8h+var_60]
0x1800cd59b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cd5a0  mov     [rsp+0B8h+lpdwDisposition], 0; lpdwDisposition
0x1800cd5a9  lea     rax, [rsp+0B8h+var_60]
0x1800cd5ae  mov     [rsp+0B8h+phkResult], rax; phkResult
0x1800cd5b3  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd5bc  mov     [rsp+0B8h+samDesired], esi; samDesired
0x1800cd5c0  mov     [rsp+0B8h+dwOptions], 0; int
0x1800cd5c8  xor     r9d, r9d; lpClass
0x1800cd5cb  xor     r8d, r8d; Reserved
0x1800cd5ce  lea     rdx, aLastloggedstat; "LastLoggedState"
0x1800cd5d5  mov     rcx, [rsp+0B8h+hKey]; hKey
0x1800cd5da  call    cs:__imp_RegCreateKeyExW
0x1800cd5e1  nop     dword ptr [rax+rax+00h]
0x1800cd5e6  test    eax, eax
0x1800cd5e8  jz      short loc_1800CD624
0x1800cd5ea  mov     rcx, [rsp+0B8h]; this
0x1800cd5f2  mov     r9d, eax; char *
0x1800cd5f5  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd5fc  mov     edx, 3CDh; void *
0x1800cd601  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cd606  mov     ebx, eax
0x1800cd608  lea     rcx, [rsp+0B8h+var_60]
0x1800cd60d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd612  nop
0x1800cd613  lea     rcx, [rsp+0B8h+hKey]
0x1800cd618  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd61d  mov     eax, ebx
0x1800cd61f  jmp     loc_1800CD78D
0x1800cd624  mov     rdi, [rdi+8]
0x1800cd628  mov     rbx, [rdi]
0x1800cd62b  cmp     rbx, rdi
0x1800cd62e  jnz     short loc_1800CD64C
0x1800cd630  lea     rcx, [rsp+0B8h+var_60]
0x1800cd635  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd63a  nop
0x1800cd63b  lea     rcx, [rsp+0B8h+hKey]
0x1800cd640  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd645  xor     eax, eax
0x1800cd647  jmp     loc_1800CD78D
0x1800cd64c  mov     [rsp+0B8h+var_68], 0
0x1800cd654  lea     r14, [rbx+10h]
0x1800cd658  mov     rcx, r14
0x1800cd65b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cd660  lea     r9, [rsp+0B8h+var_68]
0x1800cd665  mov     r8, rax
0x1800cd668  xor     edx, edx
0x1800cd66a  mov     rcx, [rsp+0B8h+var_60]
0x1800cd66f  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cd676  nop     dword ptr [rax+rax+00h]
0x1800cd67b  mov     esi, eax
0x1800cd67d  cmp     eax, 80070001h
0x1800cd682  jle     loc_1800CD753
0x1800cd688  lea     ecx, [rax+7FF8FFFCh]
0x1800cd68e  cmp     ecx, 7FF8FFFBh
0x1800cd694  jbe     loc_1800CD753
0x1800cd69a  mov     eax, [rbx+30h]
0x1800cd69d  cmp     [rsp+0B8h+var_68], eax
0x1800cd6a1  jz      short loc_1800CD6ED
0x1800cd6a3  cmp     eax, 3
0x1800cd6a6  jnz     short loc_1800CD6C2
0x1800cd6a8  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800cd6af  jz      short loc_1800CD6ED
0x1800cd6b1  mov     rcx, r14
0x1800cd6b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cd6b9  lea     rdx, AutopilotManagerProviderAppInstallationSucceeded
0x1800cd6c0  jmp     short loc_1800CD6DE
0x1800cd6c2  cmp     eax, 2
0x1800cd6c5  jnz     short loc_1800CD6ED
0x1800cd6c7  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, al
0x1800cd6cd  jz      short loc_1800CD6ED
0x1800cd6cf  mov     rcx, r14
0x1800cd6d2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cd6d7  lea     rdx, AutopilotManagerProviderAppInstallationTrackingStarted
0x1800cd6de  mov     r9, rax
0x1800cd6e1  lea     r8, aApplication; "Application"
0x1800cd6e8  call    McTemplateU0zz_EventWriteTransfer
0x1800cd6ed  mov     rcx, r14
0x1800cd6f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cd6f5  mov     r9d, [rbx+30h]
0x1800cd6f9  mov     r8, rax
0x1800cd6fc  xor     edx, edx
0x1800cd6fe  mov     rcx, [rsp+0B8h+var_60]
0x1800cd703  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800cd70a  nop     dword ptr [rax+rax+00h]
0x1800cd70f  mov     esi, eax
0x1800cd711  test    eax, eax
0x1800cd713  jns     short loc_1800CD74B
0x1800cd715  mov     rcx, [rsp+0B8h]; this
0x1800cd71d  mov     r9d, eax; char *
0x1800cd720  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd727  mov     edx, 3E2h; void *
0x1800cd72c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd731  nop
0x1800cd732  lea     rcx, [rsp+0B8h+var_60]
0x1800cd737  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd73c  nop
0x1800cd73d  lea     rcx, [rsp+0B8h+hKey]
0x1800cd742  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd747  mov     eax, esi
0x1800cd749  jmp     short loc_1800CD78D
0x1800cd74b  mov     rbx, [rbx]
0x1800cd74e  jmp     loc_1800CD62B
0x1800cd753  mov     rcx, [rsp+0B8h]; this
0x1800cd75b  mov     r9d, esi; char *
0x1800cd75e  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd765  mov     edx, 3D3h; void *
0x1800cd76a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd76f  nop
0x1800cd770  lea     rcx, [rsp+0B8h+var_60]
0x1800cd775  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd77a  nop
0x1800cd77b  lea     rcx, [rsp+0B8h+hKey]
0x1800cd780  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd785  mov     eax, esi
0x1800cd787  jmp     short loc_1800CD78D
0x1800cd789  mov     eax, [rsp+0B8h+var_68]
0x1800cd78d  mov     rcx, [rsp+0B8h+var_30]
0x1800cd795  xor     rcx, rsp; StackCookie
0x1800cd798  call    __security_check_cookie
0x1800cd79d  add     rsp, 98h
0x1800cd7a4  pop     r14
0x1800cd7a6  pop     rdi
0x1800cd7a7  pop     rsi
0x1800cd7a8  pop     rbx
0x1800cd7a9  retn
```
