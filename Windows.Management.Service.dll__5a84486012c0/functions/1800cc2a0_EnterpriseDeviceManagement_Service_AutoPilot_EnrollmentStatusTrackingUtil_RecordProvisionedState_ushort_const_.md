# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::RecordProvisionedState(ushort const *,ulong,int,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState>>> const &)

- ea: `0x1800cc2a0`
- end: `0x1800cc654`
- name: `?RecordProvisionedState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJPEBGKHAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@@std@@@2@@std@@@Z`
- size: `948`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800c7500`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x180067ffc`
- `0x18007755c`
- `0x18008019c`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x1800ca2d0`
- `0x1800cc2a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cc342`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cc50e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cc342`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cc50e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800cc410`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800cc410`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cc3a2`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cc3a2`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cc56f`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cc5e1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cc56f`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cc5e1`

## string_xrefs

- `0x1800cc363`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cc3c4`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cc497`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cc523`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cc586`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cc5f8`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::RecordProvisionedState(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4)
{
  __int64 ProviderSubkeyName; // rax
  const WCHAR *v10; // rax
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  int DWORD; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  __int64 **v19; // rdi
  __int64 *i; // rbx
  int v21; // eax
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rax
  int v24; // eax
  unsigned int v25; // esi
  DWORD dwOptions; // [rsp+20h] [rbp-2B8h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-2B8h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-2B8h]
  HKEY hKey; // [rsp+50h] [rbp-288h] BYREF
  unsigned int v30; // [rsp+58h] [rbp-280h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-278h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-270h] BYREF
  _BYTE v33[40]; // [rsp+78h] [rbp-260h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( !*(_QWORD *)(a4 + 16) )
    return 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ProviderSubkeyName = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(
                         v33,
                         a1);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ProviderSubkeyName);
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v33);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x380,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
            (const char *)v11,
            dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v12;
  }
  v30 = 0;
  DWORD = OmaDmRegistryGetDWORD(hKey, 0, L"LastProvisionedCount", &v30);
  v14 = DWORD;
  if ( DWORD >= 0 )
  {
    if ( v30 == a2 && !a3 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
  }
  else if ( (unsigned int)(DWORD + 2147024894) > 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x389,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
      (const char *)(unsigned int)DWORD,
      dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v14;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  memset_0(SubKey, 0, 0x208u);
  dwOptionsa = SystemTime.wMonth;
  v15 = StringCchPrintfW(SubKey, 0x104u, L"%04d-%02d-%02dT%02d:%02d:%02d.%03dZ", SystemTime.wYear);
  v16 = v15;
  if ( v15 >= 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v17 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    if ( v17 )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x3A7,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
              (const char *)v17,
              dwOptionsb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v18;
    }
    else
    {
      v19 = *(__int64 ***)(a4 + 8);
      for ( i = *v19; i != (__int64 *)v19; i = (__int64 *)*i )
      {
        v23 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
        v24 = OmaDmRegistrySetDWORD(phkResult, 0, v23, *((_DWORD *)i + 12));
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3AB,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
            (const char *)(unsigned int)v24,
            dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v25;
        }
      }
      v21 = OmaDmRegistrySetDWORD(hKey, 0, L"LastProvisionedCount", a2);
      v22 = v21;
      if ( v21 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AE,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
          (const char *)(unsigned int)v21,
          dwOptionsb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v22;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
      (const char *)(unsigned int)v15,
      dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v16;
  }
}

```

## disassembly

```asm
0x1800cc2a0  mov     [rsp+arg_10], rbx
0x1800cc2a5  push    rsi
0x1800cc2a6  push    rdi
0x1800cc2a7  push    r14
0x1800cc2a9  sub     rsp, 2C0h
0x1800cc2b0  mov     rax, cs:__security_cookie
0x1800cc2b7  xor     rax, rsp
0x1800cc2ba  mov     [rsp+2D8h+var_28], rax
0x1800cc2c2  mov     rdi, r9
0x1800cc2c5  mov     esi, r8d
0x1800cc2c8  mov     r14d, edx
0x1800cc2cb  mov     rbx, rcx
0x1800cc2ce  cmp     qword ptr [r9+10h], 0
0x1800cc2d3  jnz     short loc_1800CC2DC
0x1800cc2d5  xor     eax, eax
0x1800cc2d7  jmp     loc_1800CC62F
0x1800cc2dc  mov     [rsp+2D8h+hKey], 0
0x1800cc2e5  xor     edx, edx
0x1800cc2e7  lea     rcx, [rsp+2D8h+hKey]
0x1800cc2ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cc2f1  mov     rdx, rbx
0x1800cc2f4  lea     rcx, [rsp+2D8h+var_260]
0x1800cc2f9  call    ?GetProviderSubkeyName@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(ushort const * const)
0x1800cc2fe  mov     rcx, rax
0x1800cc301  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cc306  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x1800cc30f  lea     rcx, [rsp+2D8h+hKey]
0x1800cc314  mov     [rsp+2D8h+phkResult], rcx; phkResult
0x1800cc319  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cc322  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x1800cc32a  mov     [rsp+2D8h+dwOptions], 0; int
0x1800cc332  xor     r9d, r9d; lpClass
0x1800cc335  xor     r8d, r8d; Reserved
0x1800cc338  mov     rdx, rax; lpSubKey
0x1800cc33b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cc342  call    cs:__imp_RegCreateKeyExW
0x1800cc348  mov     ebx, eax
0x1800cc34a  lea     rcx, [rsp+2D8h+var_260]
0x1800cc34f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc354  test    ebx, ebx
0x1800cc356  jz      short loc_1800CC387
0x1800cc358  mov     rcx, [rsp+2D8h]; this
0x1800cc360  mov     r9d, ebx; char *
0x1800cc363  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cc36a  mov     edx, 380h; void *
0x1800cc36f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cc374  mov     ebx, eax
0x1800cc376  lea     rcx, [rsp+2D8h+hKey]
0x1800cc37b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc380  mov     eax, ebx
0x1800cc382  jmp     loc_1800CC62F
0x1800cc387  mov     [rsp+2D8h+var_280], 0
0x1800cc38f  lea     r9, [rsp+2D8h+var_280]
0x1800cc394  lea     r8, aLastprovisione; "LastProvisionedCount"
0x1800cc39b  xor     edx, edx
0x1800cc39d  mov     rcx, [rsp+2D8h+hKey]
0x1800cc3a2  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cc3a8  mov     ebx, eax
0x1800cc3aa  test    eax, eax
0x1800cc3ac  jns     short loc_1800CC3E7
0x1800cc3ae  lea     ecx, [rax+7FF8FFFEh]
0x1800cc3b4  cmp     ecx, 1
0x1800cc3b7  jbe     short loc_1800CC403
0x1800cc3b9  mov     rcx, [rsp+2D8h]; this
0x1800cc3c1  mov     r9d, eax; char *
0x1800cc3c4  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cc3cb  mov     edx, 389h; void *
0x1800cc3d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc3d5  nop
0x1800cc3d6  lea     rcx, [rsp+2D8h+hKey]
0x1800cc3db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc3e0  mov     eax, ebx
0x1800cc3e2  jmp     loc_1800CC62F
0x1800cc3e7  cmp     [rsp+2D8h+var_280], r14d
0x1800cc3ec  jnz     short loc_1800CC403
0x1800cc3ee  test    esi, esi
0x1800cc3f0  jnz     short loc_1800CC403
0x1800cc3f2  lea     rcx, [rsp+2D8h+hKey]
0x1800cc3f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc3fc  xor     eax, eax
0x1800cc3fe  jmp     loc_1800CC62F
0x1800cc403  xorps   xmm0, xmm0
0x1800cc406  movups  xmmword ptr [rsp+2D8h+SystemTime.wYear], xmm0
0x1800cc40b  lea     rcx, [rsp+2D8h+SystemTime]; lpSystemTime
0x1800cc410  call    cs:__imp_GetSystemTime
0x1800cc416  xor     edx, edx; Val
0x1800cc418  mov     r8d, 208h; Size
0x1800cc41e  lea     rcx, [rsp+2D8h+SubKey]; void *
0x1800cc426  call    memset_0
0x1800cc42b  movzx   eax, [rsp+2D8h+SystemTime.wMilliseconds]
0x1800cc430  movzx   ecx, [rsp+2D8h+SystemTime.wSecond]
0x1800cc435  movzx   edx, [rsp+2D8h+SystemTime.wMinute]
0x1800cc43a  movzx   r8d, [rsp+2D8h+SystemTime.wHour]
0x1800cc440  movzx   r10d, [rsp+2D8h+SystemTime.wDay]
0x1800cc446  movzx   r11d, [rsp+2D8h+SystemTime.wMonth]
0x1800cc44c  movzx   r9d, [rsp+2D8h+SystemTime.wYear]
0x1800cc452  mov     [rsp+2D8h+var_290], eax
0x1800cc456  mov     dword ptr [rsp+2D8h+lpdwDisposition], ecx
0x1800cc45a  mov     dword ptr [rsp+2D8h+phkResult], edx
0x1800cc45e  mov     dword ptr [rsp+2D8h+lpSecurityAttributes], r8d
0x1800cc463  mov     [rsp+2D8h+samDesired], r10d
0x1800cc468  mov     [rsp+2D8h+dwOptions], r11d; int
0x1800cc46d  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x1800cc474  mov     edx, 104h; unsigned __int64
0x1800cc479  lea     rcx, [rsp+2D8h+SubKey]; unsigned __int16 *
0x1800cc481  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cc486  mov     ebx, eax
0x1800cc488  test    eax, eax
0x1800cc48a  jns     short loc_1800CC4BA
0x1800cc48c  mov     rcx, [rsp+2D8h]; this
0x1800cc494  mov     r9d, eax; char *
0x1800cc497  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cc49e  mov     edx, 39Bh; void *
0x1800cc4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc4a8  nop
0x1800cc4a9  lea     rcx, [rsp+2D8h+hKey]
0x1800cc4ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc4b3  mov     eax, ebx
0x1800cc4b5  jmp     loc_1800CC62F
0x1800cc4ba  mov     [rsp+2D8h+var_278], 0
0x1800cc4c3  xor     edx, edx
0x1800cc4c5  lea     rcx, [rsp+2D8h+var_278]
0x1800cc4ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cc4cf  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x1800cc4d8  lea     rax, [rsp+2D8h+var_278]
0x1800cc4dd  mov     [rsp+2D8h+phkResult], rax; phkResult
0x1800cc4e2  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cc4eb  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x1800cc4f3  mov     [rsp+2D8h+dwOptions], 0; int
0x1800cc4fb  xor     r9d, r9d; lpClass
0x1800cc4fe  xor     r8d, r8d; Reserved
0x1800cc501  lea     rdx, [rsp+2D8h+SubKey]; lpSubKey
0x1800cc509  mov     rcx, [rsp+2D8h+hKey]; hKey
0x1800cc50e  call    cs:__imp_RegCreateKeyExW
0x1800cc514  test    eax, eax
0x1800cc516  jz      short loc_1800CC552
0x1800cc518  mov     rcx, [rsp+2D8h]; this
0x1800cc520  mov     r9d, eax; char *
0x1800cc523  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cc52a  mov     edx, 3A7h; void *
0x1800cc52f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cc534  mov     ebx, eax
0x1800cc536  lea     rcx, [rsp+2D8h+var_278]
0x1800cc53b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc540  nop
0x1800cc541  lea     rcx, [rsp+2D8h+hKey]
0x1800cc546  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc54b  mov     eax, ebx
0x1800cc54d  jmp     loc_1800CC62F
0x1800cc552  mov     rdi, [rdi+8]
0x1800cc556  mov     rbx, [rdi]
0x1800cc559  cmp     rbx, rdi
0x1800cc55c  jnz     short loc_1800CC5CA
0x1800cc55e  mov     r9d, r14d
0x1800cc561  lea     r8, aLastprovisione; "LastProvisionedCount"
0x1800cc568  xor     edx, edx
0x1800cc56a  mov     rcx, [rsp+2D8h+hKey]
0x1800cc56f  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800cc575  mov     ebx, eax
0x1800cc577  test    eax, eax
0x1800cc579  jns     short loc_1800CC5B1
0x1800cc57b  mov     rcx, [rsp+2D8h]; this
0x1800cc583  mov     r9d, eax; char *
0x1800cc586  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cc58d  mov     edx, 3AEh; void *
0x1800cc592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc597  nop
0x1800cc598  lea     rcx, [rsp+2D8h+var_278]
0x1800cc59d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc5a2  nop
0x1800cc5a3  lea     rcx, [rsp+2D8h+hKey]
0x1800cc5a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc5ad  mov     eax, ebx
0x1800cc5af  jmp     short loc_1800CC62F
0x1800cc5b1  lea     rcx, [rsp+2D8h+var_278]
0x1800cc5b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc5bb  nop
0x1800cc5bc  lea     rcx, [rsp+2D8h+hKey]
0x1800cc5c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc5c6  xor     eax, eax
0x1800cc5c8  jmp     short loc_1800CC62F
0x1800cc5ca  lea     rcx, [rbx+10h]
0x1800cc5ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cc5d3  mov     r9d, [rbx+30h]
0x1800cc5d7  mov     r8, rax
0x1800cc5da  xor     edx, edx
0x1800cc5dc  mov     rcx, [rsp+2D8h+var_278]
0x1800cc5e1  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800cc5e7  mov     esi, eax
0x1800cc5e9  test    eax, eax
0x1800cc5eb  jns     short loc_1800CC623
0x1800cc5ed  mov     rcx, [rsp+2D8h]; this
0x1800cc5f5  mov     r9d, eax; char *
0x1800cc5f8  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cc5ff  mov     edx, 3ABh; void *
0x1800cc604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc609  nop
0x1800cc60a  lea     rcx, [rsp+2D8h+var_278]
0x1800cc60f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc614  nop
0x1800cc615  lea     rcx, [rsp+2D8h+hKey]
0x1800cc61a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cc61f  mov     eax, esi
0x1800cc621  jmp     short loc_1800CC62F
0x1800cc623  mov     rbx, [rbx]
0x1800cc626  jmp     loc_1800CC559
0x1800cc62b  mov     eax, [rsp+2D8h+var_280]
0x1800cc62f  mov     rcx, [rsp+2D8h+var_28]
0x1800cc637  xor     rcx, rsp; StackCookie
0x1800cc63a  call    __security_check_cookie
0x1800cc63f  mov     rbx, [rsp+2D8h+arg_10]
0x1800cc647  add     rsp, 2C0h
0x1800cc64e  pop     r14
0x1800cc650  pop     rdi
0x1800cc651  pop     rsi
0x1800cc652  retn
```
