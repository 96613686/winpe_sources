# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogAppsState(ushort const * const,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState>>> const &)

- ea: `0x1800cb194`
- end: `0x1800cb473`
- name: `?LogAppsState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJQEBGAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@@std@@@2@@std@@@Z`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c7500`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x1800ca2d0`
- `0x1800cb194`
- `0x1800ce040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb220`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb2b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb220`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb2b4`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cb343`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cb343`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cb3d1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cb3d1`

## string_xrefs

- `0x1800cb241`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb2c9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb3e8`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb426`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

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
  DWORD dwOptionsa; // [rsp+20h] [rbp-98h]
  unsigned int v25; // [rsp+50h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v28[32]; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ProviderSubkeyName = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(
                         v28,
                         a1);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ProviderSubkeyName);
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v28);
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
            dwOptionsa);
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
    v25 = 0;
    v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
    DWORD = OmaDmRegistryGetDWORD(phkResult, 0, v13, &v25);
    v15 = DWORD;
    if ( DWORD <= -2147024895 || (unsigned int)(DWORD + 2147024892) <= 0x7FF8FFFB )
      break;
    v16 = *((_DWORD *)i + 12);
    if ( v25 == v16 )
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
        dwOptionsa);
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
    dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v15;
}

```

## disassembly

```asm
0x1800cb194  push    rbx
0x1800cb196  push    rsi
0x1800cb197  push    rdi
0x1800cb198  push    r14
0x1800cb19a  sub     rsp, 98h
0x1800cb1a1  mov     rax, cs:__security_cookie
0x1800cb1a8  xor     rax, rsp
0x1800cb1ab  mov     [rsp+0B8h+var_30], rax
0x1800cb1b3  mov     rdi, rdx
0x1800cb1b6  mov     rbx, rcx
0x1800cb1b9  mov     [rsp+0B8h+hKey], 0
0x1800cb1c2  xor     edx, edx
0x1800cb1c4  lea     rcx, [rsp+0B8h+hKey]
0x1800cb1c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cb1ce  mov     rdx, rbx
0x1800cb1d1  lea     rcx, [rsp+0B8h+var_50]
0x1800cb1d6  call    ?GetProviderSubkeyName@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(ushort const * const)
0x1800cb1db  mov     rcx, rax
0x1800cb1de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb1e3  mov     [rsp+0B8h+lpdwDisposition], 0; lpdwDisposition
0x1800cb1ec  lea     rcx, [rsp+0B8h+hKey]
0x1800cb1f1  mov     [rsp+0B8h+phkResult], rcx; phkResult
0x1800cb1f6  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cb1ff  mov     esi, 0F003Fh
0x1800cb204  mov     [rsp+0B8h+samDesired], esi; samDesired
0x1800cb208  mov     [rsp+0B8h+dwOptions], 0; unsigned int
0x1800cb210  xor     r9d, r9d; lpClass
0x1800cb213  xor     r8d, r8d; Reserved
0x1800cb216  mov     rdx, rax; lpSubKey
0x1800cb219  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cb220  call    cs:__imp_RegCreateKeyExW
0x1800cb226  mov     ebx, eax
0x1800cb228  lea     rcx, [rsp+0B8h+var_50]
0x1800cb22d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb232  test    ebx, ebx
0x1800cb234  jz      short loc_1800CB265
0x1800cb236  mov     rcx, [rsp+0B8h]; this
0x1800cb23e  mov     r9d, ebx; char *
0x1800cb241  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb248  mov     edx, 3C1h; void *
0x1800cb24d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cb252  mov     ebx, eax
0x1800cb254  lea     rcx, [rsp+0B8h+hKey]
0x1800cb259  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb25e  mov     eax, ebx
0x1800cb260  jmp     loc_1800CB455
0x1800cb265  mov     [rsp+0B8h+var_60], 0
0x1800cb26e  xor     edx, edx
0x1800cb270  lea     rcx, [rsp+0B8h+var_60]
0x1800cb275  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cb27a  mov     [rsp+0B8h+lpdwDisposition], 0; lpdwDisposition
0x1800cb283  lea     rax, [rsp+0B8h+var_60]
0x1800cb288  mov     [rsp+0B8h+phkResult], rax; phkResult
0x1800cb28d  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cb296  mov     [rsp+0B8h+samDesired], esi; samDesired
0x1800cb29a  mov     [rsp+0B8h+dwOptions], 0; int
0x1800cb2a2  xor     r9d, r9d; lpClass
0x1800cb2a5  xor     r8d, r8d; Reserved
0x1800cb2a8  lea     rdx, aLastloggedstat; "LastLoggedState"
0x1800cb2af  mov     rcx, [rsp+0B8h+hKey]; hKey
0x1800cb2b4  call    cs:__imp_RegCreateKeyExW
0x1800cb2ba  test    eax, eax
0x1800cb2bc  jz      short loc_1800CB2F8
0x1800cb2be  mov     rcx, [rsp+0B8h]; this
0x1800cb2c6  mov     r9d, eax; char *
0x1800cb2c9  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb2d0  mov     edx, 3CDh; void *
0x1800cb2d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cb2da  mov     ebx, eax
0x1800cb2dc  lea     rcx, [rsp+0B8h+var_60]
0x1800cb2e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb2e6  nop
0x1800cb2e7  lea     rcx, [rsp+0B8h+hKey]
0x1800cb2ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb2f1  mov     eax, ebx
0x1800cb2f3  jmp     loc_1800CB455
0x1800cb2f8  mov     rdi, [rdi+8]
0x1800cb2fc  mov     rbx, [rdi]
0x1800cb2ff  cmp     rbx, rdi
0x1800cb302  jnz     short loc_1800CB320
0x1800cb304  lea     rcx, [rsp+0B8h+var_60]
0x1800cb309  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb30e  nop
0x1800cb30f  lea     rcx, [rsp+0B8h+hKey]
0x1800cb314  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb319  xor     eax, eax
0x1800cb31b  jmp     loc_1800CB455
0x1800cb320  mov     [rsp+0B8h+var_68], 0
0x1800cb328  lea     r14, [rbx+10h]
0x1800cb32c  mov     rcx, r14
0x1800cb32f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb334  lea     r9, [rsp+0B8h+var_68]
0x1800cb339  mov     r8, rax
0x1800cb33c  xor     edx, edx
0x1800cb33e  mov     rcx, [rsp+0B8h+var_60]
0x1800cb343  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cb349  mov     esi, eax
0x1800cb34b  cmp     eax, 80070001h
0x1800cb350  jle     loc_1800CB41B
0x1800cb356  lea     ecx, [rax+7FF8FFFCh]
0x1800cb35c  cmp     ecx, 7FF8FFFBh
0x1800cb362  jbe     loc_1800CB41B
0x1800cb368  mov     eax, [rbx+30h]
0x1800cb36b  cmp     [rsp+0B8h+var_68], eax
0x1800cb36f  jz      short loc_1800CB3BB
0x1800cb371  cmp     eax, 3
0x1800cb374  jnz     short loc_1800CB390
0x1800cb376  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800cb37d  jz      short loc_1800CB3BB
0x1800cb37f  mov     rcx, r14
0x1800cb382  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb387  lea     rdx, AutopilotManagerProviderAppInstallationSucceeded
0x1800cb38e  jmp     short loc_1800CB3AC
0x1800cb390  cmp     eax, 2
0x1800cb393  jnz     short loc_1800CB3BB
0x1800cb395  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, al
0x1800cb39b  jz      short loc_1800CB3BB
0x1800cb39d  mov     rcx, r14
0x1800cb3a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb3a5  lea     rdx, AutopilotManagerProviderAppInstallationTrackingStarted
0x1800cb3ac  mov     r9, rax
0x1800cb3af  lea     r8, aApplication; "Application"
0x1800cb3b6  call    McTemplateU0zz_EventWriteTransfer
0x1800cb3bb  mov     rcx, r14
0x1800cb3be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb3c3  mov     r9d, [rbx+30h]
0x1800cb3c7  mov     r8, rax
0x1800cb3ca  xor     edx, edx
0x1800cb3cc  mov     rcx, [rsp+0B8h+var_60]
0x1800cb3d1  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800cb3d7  mov     esi, eax
0x1800cb3d9  test    eax, eax
0x1800cb3db  jns     short loc_1800CB413
0x1800cb3dd  mov     rcx, [rsp+0B8h]; this
0x1800cb3e5  mov     r9d, eax; char *
0x1800cb3e8  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb3ef  mov     edx, 3E2h; void *
0x1800cb3f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb3f9  nop
0x1800cb3fa  lea     rcx, [rsp+0B8h+var_60]
0x1800cb3ff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb404  nop
0x1800cb405  lea     rcx, [rsp+0B8h+hKey]
0x1800cb40a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb40f  mov     eax, esi
0x1800cb411  jmp     short loc_1800CB455
0x1800cb413  mov     rbx, [rbx]
0x1800cb416  jmp     loc_1800CB2FF
0x1800cb41b  mov     rcx, [rsp+0B8h]; this
0x1800cb423  mov     r9d, esi; char *
0x1800cb426  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb42d  mov     edx, 3D3h; void *
0x1800cb432  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb437  nop
0x1800cb438  lea     rcx, [rsp+0B8h+var_60]
0x1800cb43d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb442  nop
0x1800cb443  lea     rcx, [rsp+0B8h+hKey]
0x1800cb448  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb44d  mov     eax, esi
0x1800cb44f  jmp     short loc_1800CB455
0x1800cb451  mov     eax, [rsp+0B8h+var_68]
0x1800cb455  mov     rcx, [rsp+0B8h+var_30]
0x1800cb45d  xor     rcx, rsp; StackCookie
0x1800cb460  call    __security_check_cookie
0x1800cb465  add     rsp, 98h
0x1800cb46c  pop     r14
0x1800cb46e  pop     rdi
0x1800cb46f  pop     rsi
0x1800cb470  pop     rbx
0x1800cb471  retn
```
