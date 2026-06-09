# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::RecordProvisionedState(ushort const *,ulong,int,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::Management::EnrollmentStatusTracking::ConfigProvider::AppInstallState>>> const &)

- ea: `0x1800ce5f4`
- end: `0x1800ce9cf`
- name: `?RecordProvisionedState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJPEBGKHAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppInstallState@ConfigProvider@EnrollmentStatusTracking@Management@Windows@@@std@@@2@@std@@@Z`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800c961c`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006841c`
- `0x180077de0`
- `0x180080bac`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x1800cc544`
- `0x1800ce5f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce696`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce874`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce696`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ce874`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800ce770`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800ce770`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce6fc`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce6fc`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800ce8db`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800ce956`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800ce8db`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800ce956`

## string_xrefs

- `0x1800ce6bd`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800ce724`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800ce7fd`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800ce88f`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800ce8f8`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800ce973`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

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
0x1800ce5f4  mov     [rsp+arg_10], rbx
0x1800ce5f9  push    rsi
0x1800ce5fa  push    rdi
0x1800ce5fb  push    r14
0x1800ce5fd  sub     rsp, 2C0h
0x1800ce604  mov     rax, cs:__security_cookie
0x1800ce60b  xor     rax, rsp
0x1800ce60e  mov     [rsp+2D8h+var_28], rax
0x1800ce616  mov     rdi, r9
0x1800ce619  mov     esi, r8d
0x1800ce61c  mov     r14d, edx
0x1800ce61f  mov     rbx, rcx
0x1800ce622  cmp     qword ptr [r9+10h], 0
0x1800ce627  jnz     short loc_1800CE630
0x1800ce629  xor     eax, eax
0x1800ce62b  jmp     loc_1800CE9AA
0x1800ce630  mov     [rsp+2D8h+hKey], 0
0x1800ce639  xor     edx, edx
0x1800ce63b  lea     rcx, [rsp+2D8h+hKey]
0x1800ce640  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ce645  mov     rdx, rbx
0x1800ce648  lea     rcx, [rsp+2D8h+var_260]
0x1800ce64d  call    ?GetProviderSubkeyName@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(ushort const * const)
0x1800ce652  mov     rcx, rax
0x1800ce655  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ce65a  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x1800ce663  lea     rcx, [rsp+2D8h+hKey]
0x1800ce668  mov     [rsp+2D8h+phkResult], rcx; phkResult
0x1800ce66d  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ce676  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x1800ce67e  mov     [rsp+2D8h+dwOptions], 0; int
0x1800ce686  xor     r9d, r9d; lpClass
0x1800ce689  xor     r8d, r8d; Reserved
0x1800ce68c  mov     rdx, rax; lpSubKey
0x1800ce68f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ce696  call    cs:__imp_RegCreateKeyExW
0x1800ce69d  nop     dword ptr [rax+rax+00h]
0x1800ce6a2  mov     ebx, eax
0x1800ce6a4  lea     rcx, [rsp+2D8h+var_260]
0x1800ce6a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ce6ae  test    ebx, ebx
0x1800ce6b0  jz      short loc_1800CE6E1
0x1800ce6b2  mov     rcx, [rsp+2D8h]; this
0x1800ce6ba  mov     r9d, ebx; char *
0x1800ce6bd  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ce6c4  mov     edx, 380h; void *
0x1800ce6c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ce6ce  mov     ebx, eax
0x1800ce6d0  lea     rcx, [rsp+2D8h+hKey]
0x1800ce6d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce6da  mov     eax, ebx
0x1800ce6dc  jmp     loc_1800CE9AA
0x1800ce6e1  mov     [rsp+2D8h+var_280], 0
0x1800ce6e9  lea     r9, [rsp+2D8h+var_280]
0x1800ce6ee  lea     r8, aLastprovisione; "LastProvisionedCount"
0x1800ce6f5  xor     edx, edx
0x1800ce6f7  mov     rcx, [rsp+2D8h+hKey]
0x1800ce6fc  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ce703  nop     dword ptr [rax+rax+00h]
0x1800ce708  mov     ebx, eax
0x1800ce70a  test    eax, eax
0x1800ce70c  jns     short loc_1800CE747
0x1800ce70e  lea     ecx, [rax+7FF8FFFEh]
0x1800ce714  cmp     ecx, 1
0x1800ce717  jbe     short loc_1800CE763
0x1800ce719  mov     rcx, [rsp+2D8h]; this
0x1800ce721  mov     r9d, eax; char *
0x1800ce724  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ce72b  mov     edx, 389h; void *
0x1800ce730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce735  nop
0x1800ce736  lea     rcx, [rsp+2D8h+hKey]
0x1800ce73b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce740  mov     eax, ebx
0x1800ce742  jmp     loc_1800CE9AA
0x1800ce747  cmp     [rsp+2D8h+var_280], r14d
0x1800ce74c  jnz     short loc_1800CE763
0x1800ce74e  test    esi, esi
0x1800ce750  jnz     short loc_1800CE763
0x1800ce752  lea     rcx, [rsp+2D8h+hKey]
0x1800ce757  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce75c  xor     eax, eax
0x1800ce75e  jmp     loc_1800CE9AA
0x1800ce763  xorps   xmm0, xmm0
0x1800ce766  movups  xmmword ptr [rsp+2D8h+SystemTime.wYear], xmm0
0x1800ce76b  lea     rcx, [rsp+2D8h+SystemTime]; lpSystemTime
0x1800ce770  call    cs:__imp_GetSystemTime
0x1800ce777  nop     dword ptr [rax+rax+00h]
0x1800ce77c  xor     edx, edx; Val
0x1800ce77e  mov     r8d, 208h; Size
0x1800ce784  lea     rcx, [rsp+2D8h+SubKey]; void *
0x1800ce78c  call    memset_0
0x1800ce791  movzx   eax, [rsp+2D8h+SystemTime.wMilliseconds]
0x1800ce796  movzx   ecx, [rsp+2D8h+SystemTime.wSecond]
0x1800ce79b  movzx   edx, [rsp+2D8h+SystemTime.wMinute]
0x1800ce7a0  movzx   r8d, [rsp+2D8h+SystemTime.wHour]
0x1800ce7a6  movzx   r10d, [rsp+2D8h+SystemTime.wDay]
0x1800ce7ac  movzx   r11d, [rsp+2D8h+SystemTime.wMonth]
0x1800ce7b2  movzx   r9d, [rsp+2D8h+SystemTime.wYear]
0x1800ce7b8  mov     [rsp+2D8h+var_290], eax
0x1800ce7bc  mov     dword ptr [rsp+2D8h+lpdwDisposition], ecx
0x1800ce7c0  mov     dword ptr [rsp+2D8h+phkResult], edx
0x1800ce7c4  mov     dword ptr [rsp+2D8h+lpSecurityAttributes], r8d
0x1800ce7c9  mov     [rsp+2D8h+samDesired], r10d
0x1800ce7ce  mov     [rsp+2D8h+dwOptions], r11d; int
0x1800ce7d3  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x1800ce7da  mov     edx, 104h; unsigned __int64
0x1800ce7df  lea     rcx, [rsp+2D8h+SubKey]; unsigned __int16 *
0x1800ce7e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ce7ec  mov     ebx, eax
0x1800ce7ee  test    eax, eax
0x1800ce7f0  jns     short loc_1800CE820
0x1800ce7f2  mov     rcx, [rsp+2D8h]; this
0x1800ce7fa  mov     r9d, eax; char *
0x1800ce7fd  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ce804  mov     edx, 39Bh; void *
0x1800ce809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce80e  nop
0x1800ce80f  lea     rcx, [rsp+2D8h+hKey]
0x1800ce814  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce819  mov     eax, ebx
0x1800ce81b  jmp     loc_1800CE9AA
0x1800ce820  mov     [rsp+2D8h+var_278], 0
0x1800ce829  xor     edx, edx
0x1800ce82b  lea     rcx, [rsp+2D8h+var_278]
0x1800ce830  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ce835  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x1800ce83e  lea     rax, [rsp+2D8h+var_278]
0x1800ce843  mov     [rsp+2D8h+phkResult], rax; phkResult
0x1800ce848  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ce851  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x1800ce859  mov     [rsp+2D8h+dwOptions], 0; int
0x1800ce861  xor     r9d, r9d; lpClass
0x1800ce864  xor     r8d, r8d; Reserved
0x1800ce867  lea     rdx, [rsp+2D8h+SubKey]; lpSubKey
0x1800ce86f  mov     rcx, [rsp+2D8h+hKey]; hKey
0x1800ce874  call    cs:__imp_RegCreateKeyExW
0x1800ce87b  nop     dword ptr [rax+rax+00h]
0x1800ce880  test    eax, eax
0x1800ce882  jz      short loc_1800CE8BE
0x1800ce884  mov     rcx, [rsp+2D8h]; this
0x1800ce88c  mov     r9d, eax; char *
0x1800ce88f  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ce896  mov     edx, 3A7h; void *
0x1800ce89b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ce8a0  mov     ebx, eax
0x1800ce8a2  lea     rcx, [rsp+2D8h+var_278]
0x1800ce8a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce8ac  nop
0x1800ce8ad  lea     rcx, [rsp+2D8h+hKey]
0x1800ce8b2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce8b7  mov     eax, ebx
0x1800ce8b9  jmp     loc_1800CE9AA
0x1800ce8be  mov     rdi, [rdi+8]
0x1800ce8c2  mov     rbx, [rdi]
0x1800ce8c5  cmp     rbx, rdi
0x1800ce8c8  jnz     short loc_1800CE93F
0x1800ce8ca  mov     r9d, r14d
0x1800ce8cd  lea     r8, aLastprovisione; "LastProvisionedCount"
0x1800ce8d4  xor     edx, edx
0x1800ce8d6  mov     rcx, [rsp+2D8h+hKey]
0x1800ce8db  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800ce8e2  nop     dword ptr [rax+rax+00h]
0x1800ce8e7  mov     ebx, eax
0x1800ce8e9  test    eax, eax
0x1800ce8eb  jns     short loc_1800CE926
0x1800ce8ed  mov     rcx, [rsp+2D8h]; this
0x1800ce8f5  mov     r9d, eax; char *
0x1800ce8f8  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ce8ff  mov     edx, 3AEh; void *
0x1800ce904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce909  nop
0x1800ce90a  lea     rcx, [rsp+2D8h+var_278]
0x1800ce90f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce914  nop
0x1800ce915  lea     rcx, [rsp+2D8h+hKey]
0x1800ce91a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce91f  mov     eax, ebx
0x1800ce921  jmp     loc_1800CE9AA
0x1800ce926  lea     rcx, [rsp+2D8h+var_278]
0x1800ce92b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce930  nop
0x1800ce931  lea     rcx, [rsp+2D8h+hKey]
0x1800ce936  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce93b  xor     eax, eax
0x1800ce93d  jmp     short loc_1800CE9AA
0x1800ce93f  lea     rcx, [rbx+10h]
0x1800ce943  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ce948  mov     r9d, [rbx+30h]
0x1800ce94c  mov     r8, rax
0x1800ce94f  xor     edx, edx
0x1800ce951  mov     rcx, [rsp+2D8h+var_278]
0x1800ce956  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800ce95d  nop     dword ptr [rax+rax+00h]
0x1800ce962  mov     esi, eax
0x1800ce964  test    eax, eax
0x1800ce966  jns     short loc_1800CE99E
0x1800ce968  mov     rcx, [rsp+2D8h]; this
0x1800ce970  mov     r9d, eax; char *
0x1800ce973  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ce97a  mov     edx, 3ABh; void *
0x1800ce97f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce984  nop
0x1800ce985  lea     rcx, [rsp+2D8h+var_278]
0x1800ce98a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce98f  nop
0x1800ce990  lea     rcx, [rsp+2D8h+hKey]
0x1800ce995  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ce99a  mov     eax, esi
0x1800ce99c  jmp     short loc_1800CE9AA
0x1800ce99e  mov     rbx, [rbx]
0x1800ce9a1  jmp     loc_1800CE8C5
0x1800ce9a6  mov     eax, [rsp+2D8h+var_280]
0x1800ce9aa  mov     rcx, [rsp+2D8h+var_28]
0x1800ce9b2  xor     rcx, rsp; StackCookie
0x1800ce9b5  call    __security_check_cookie
0x1800ce9ba  mov     rbx, [rsp+2D8h+arg_10]
0x1800ce9c2  add     rsp, 2C0h
0x1800ce9c9  pop     r14
0x1800ce9cb  pop     rdi
0x1800ce9cc  pop     rsi
0x1800ce9cd  retn
```
