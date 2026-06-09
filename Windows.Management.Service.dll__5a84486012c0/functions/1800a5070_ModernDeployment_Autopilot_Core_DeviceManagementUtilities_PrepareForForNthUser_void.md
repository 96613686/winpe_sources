# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::PrepareForForNthUser(void)

- ea: `0x1800a5070`
- end: `0x1800a53bb`
- name: `?PrepareForForNthUser@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJXZ`
- size: `843`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::DeviceManagementUtilities *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800839bc`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x180089ff4`
- `0x1800a13d8`
- `0x1800a1fe4`
- `0x1800a211c`
- `0x1800a5070`
- `0x1800a7e6c`
- `0x1800a7f70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a531f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a531f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5133`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a51df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5133`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a51df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a52ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a52ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a50d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a50d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a5230`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a5230`

## string_xrefs

- `0x1800a518e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a51f4`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5302`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5334`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceManagementUtilities::PrepareForForNthUser(
        ModernDeployment::Autopilot::Core::DeviceManagementUtilities *this)
{
  LSTATUS v1; // eax
  bool v2; // sf
  LSTATUS v3; // eax
  bool v4; // sf
  const BYTE *v5; // rbx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  DWORD v10; // edi
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  int phkResult; // [rsp+20h] [rbp-2C8h]
  PHKEY phkResulta; // [rsp+20h] [rbp-2C8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-2C8h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-2C0h]
  DWORD Type; // [rsp+50h] [rbp-298h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-290h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-288h] BYREF
  LPBYTE lpData; // [rsp+68h] [rbp-280h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-278h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-268h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-248h] BYREF
  _BYTE v26[528]; // [rsp+C0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete>::GetImpl'::`2'::impl) )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Provisioning\\AutopilotSettings", 0, 0xF003Fu, &hKey);
    v2 = v1 < 0;
    if ( v1 > 0 )
      v2 = 1;
    if ( !v2 && hKey )
    {
      cbData = 0;
      Type = 1;
      v3 = RegQueryValueExW(hKey, L"AccountSetupCategory.Status", 0, &Type, 0, &cbData);
      v4 = v3 < 0;
      if ( v3 > 0 )
        v4 = 1;
      if ( !v4 && cbData && Type == 1 )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpData,
          0,
          cbData);
        v5 = lpData;
        if ( !lpData )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B5,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
            (const char *)0x8007000ELL,
            phkResult);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 2147942414LL;
        }
        v7 = RegQueryValueExW(hKey, L"AccountSetupCategory.Status", 0, &Type, lpData, &cbData);
        if ( v7 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x2BD,
                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                 (const char *)v7,
                 (unsigned int)phkResulta);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v8;
        }
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        LODWORD(lpcbData) = SystemTime.wHour;
        LODWORD(phkResulta) = SystemTime.wDay;
        swprintf_s<260>(
          v26,
          L".%04d-%02d-%02dT%02d:%02d:%02d.%03dZ",
          SystemTime.wYear,
          SystemTime.wMonth,
          phkResulta,
          lpcbData,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
        v9 = std::wstring::wstring(v25, L"AccountSetupCategory.Status");
        std::operator+<unsigned short>(v24, v9, v26);
        std::wstring::_Tidy_deallocate(v25);
        v10 = cbData;
        v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
        v12 = RegSetValueExW(hKey, v11, 0, 1u, v5, v10);
        if ( v12 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x2CD,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
            (const char *)v12,
            phkResultb);
        v13 = RegDeleteValueW(hKey, L"AccountSetupCategory.Status");
        if ( v13 )
        {
          v14 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2CF,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                  (const char *)v13,
                  phkResultb);
          std::wstring::_Tidy_deallocate(v24);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v14;
        }
        std::wstring::_Tidy_deallocate(v24);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a5070  mov     [rsp+arg_0], rbx
0x1800a5075  push    rdi
0x1800a5076  sub     rsp, 2E0h
0x1800a507d  mov     rax, cs:__security_cookie
0x1800a5084  xor     rax, rsp
0x1800a5087  mov     [rsp+2E8h+var_18], rax
0x1800a508f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete> `wil::Feature<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete>::GetImpl(void)'::`2'::impl
0x1800a5096  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete>::__private_IsEnabled(void)
0x1800a509b  test    al, al
0x1800a509d  jz      loc_1800A5391
0x1800a50a3  mov     [rsp+2E8h+hKey], 0
0x1800a50ac  xor     edx, edx
0x1800a50ae  lea     rcx, [rsp+2E8h+hKey]
0x1800a50b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a50b8  lea     rax, [rsp+2E8h+hKey]
0x1800a50bd  mov     [rsp+2E8h+phkResult], rax; phkResult
0x1800a50c2  mov     r9d, 0F003Fh; samDesired
0x1800a50c8  xor     r8d, r8d; ulOptions
0x1800a50cb  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800a50d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a50d9  call    cs:__imp_RegOpenKeyExW
0x1800a50df  test    eax, eax
0x1800a50e1  jle     short loc_1800A50ED
0x1800a50e3  movzx   eax, ax
0x1800a50e6  or      eax, 80070000h
0x1800a50eb  test    eax, eax
0x1800a50ed  js      loc_1800A5387
0x1800a50f3  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a50f8  test    rcx, rcx
0x1800a50fb  jz      loc_1800A5387
0x1800a5101  mov     [rsp+2E8h+cbData], 0
0x1800a5109  mov     [rsp+2E8h+Type], 1
0x1800a5111  lea     rax, [rsp+2E8h+cbData]
0x1800a5116  mov     [rsp+2E8h+lpcbData], rax; lpcbData
0x1800a511b  mov     [rsp+2E8h+phkResult], 0; int
0x1800a5124  lea     r9, [rsp+2E8h+Type]; lpType
0x1800a5129  xor     r8d, r8d; lpReserved
0x1800a512c  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a5133  call    cs:__imp_RegQueryValueExW
0x1800a5139  test    eax, eax
0x1800a513b  jle     short loc_1800A5147
0x1800a513d  movzx   eax, ax
0x1800a5140  or      eax, 80070000h
0x1800a5145  test    eax, eax
0x1800a5147  js      loc_1800A5387
0x1800a514d  mov     eax, [rsp+2E8h+cbData]
0x1800a5151  test    eax, eax
0x1800a5153  jz      loc_1800A5387
0x1800a5159  cmp     [rsp+2E8h+Type], 1
0x1800a515e  jnz     loc_1800A5387
0x1800a5164  mov     r8d, eax
0x1800a5167  xor     edx, edx
0x1800a5169  lea     rcx, [rsp+2E8h+lpData]
0x1800a516e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a5173  nop
0x1800a5174  mov     rbx, [rsp+2E8h+lpData]
0x1800a5179  test    rbx, rbx
0x1800a517c  jnz     short loc_1800A51BC
0x1800a517e  mov     rcx, [rsp+2E8h]; this
0x1800a5186  mov     ebx, 8007000Eh
0x1800a518b  mov     r9d, ebx; char *
0x1800a518e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5195  mov     edx, 2B5h; void *
0x1800a519a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a519f  nop
0x1800a51a0  lea     rcx, [rsp+2E8h+lpData]
0x1800a51a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a51aa  nop
0x1800a51ab  lea     rcx, [rsp+2E8h+hKey]
0x1800a51b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a51b5  mov     eax, ebx
0x1800a51b7  jmp     loc_1800A5399
0x1800a51bc  lea     rax, [rsp+2E8h+cbData]
0x1800a51c1  mov     [rsp+2E8h+lpcbData], rax; lpcbData
0x1800a51c6  mov     [rsp+2E8h+phkResult], rbx; unsigned int
0x1800a51cb  lea     r9, [rsp+2E8h+Type]; lpType
0x1800a51d0  xor     r8d, r8d; lpReserved
0x1800a51d3  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a51da  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a51df  call    cs:__imp_RegQueryValueExW
0x1800a51e5  test    eax, eax
0x1800a51e7  jz      short loc_1800A5223
0x1800a51e9  mov     rcx, [rsp+2E8h]; this
0x1800a51f1  mov     r9d, eax; char *
0x1800a51f4  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a51fb  mov     edx, 2BDh; void *
0x1800a5200  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a5205  mov     ebx, eax
0x1800a5207  lea     rcx, [rsp+2E8h+lpData]
0x1800a520c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5211  nop
0x1800a5212  lea     rcx, [rsp+2E8h+hKey]
0x1800a5217  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a521c  mov     eax, ebx
0x1800a521e  jmp     loc_1800A5399
0x1800a5223  xorps   xmm0, xmm0
0x1800a5226  movups  xmmword ptr [rsp+2E8h+SystemTime.wYear], xmm0
0x1800a522b  lea     rcx, [rsp+2E8h+SystemTime]; lpSystemTime
0x1800a5230  call    cs:__imp_GetSystemTime
0x1800a5236  movzx   eax, [rsp+2E8h+SystemTime.wMilliseconds]
0x1800a523b  movzx   ecx, [rsp+2E8h+SystemTime.wSecond]
0x1800a5240  movzx   edx, [rsp+2E8h+SystemTime.wMinute]
0x1800a5245  movzx   r10d, [rsp+2E8h+SystemTime.wHour]
0x1800a524b  movzx   r11d, [rsp+2E8h+SystemTime.wDay]
0x1800a5251  movzx   r9d, [rsp+2E8h+SystemTime.wMonth]
0x1800a5257  movzx   r8d, [rsp+2E8h+SystemTime.wYear]
0x1800a525d  mov     [rsp+2E8h+var_2A8], eax
0x1800a5261  mov     [rsp+2E8h+var_2B0], ecx
0x1800a5265  mov     [rsp+2E8h+var_2B8], edx
0x1800a5269  mov     dword ptr [rsp+2E8h+lpcbData], r10d
0x1800a526e  mov     dword ptr [rsp+2E8h+phkResult], r11d
0x1800a5273  lea     rdx, a04d02d02dt02d0_0; ".%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x1800a527a  lea     rcx, [rsp+2E8h+var_228]
0x1800a5282  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x1800a5287  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a528e  lea     rcx, [rsp+2E8h+var_248]
0x1800a5296  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a529b  nop
0x1800a529c  lea     r8, [rsp+2E8h+var_228]
0x1800a52a4  mov     rdx, rax
0x1800a52a7  lea     rcx, [rsp+2E8h+var_268]
0x1800a52af  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a52b4  nop
0x1800a52b5  lea     rcx, [rsp+2E8h+var_248]
0x1800a52bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a52c2  mov     edi, [rsp+2E8h+cbData]
0x1800a52c6  lea     rcx, [rsp+2E8h+var_268]
0x1800a52ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a52d3  mov     rdx, rax; lpValueName
0x1800a52d6  mov     dword ptr [rsp+2E8h+lpcbData], edi; cbData
0x1800a52da  mov     [rsp+2E8h+phkResult], rbx; unsigned int
0x1800a52df  mov     r9d, 1; dwType
0x1800a52e5  xor     r8d, r8d; Reserved
0x1800a52e8  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a52ed  call    cs:__imp_RegSetValueExW
0x1800a52f3  mov     rcx, [rsp+2E8h]; this
0x1800a52fb  test    eax, eax
0x1800a52fd  jz      short loc_1800A5313
0x1800a52ff  mov     r9d, eax; char *
0x1800a5302  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5309  mov     edx, 2CDh; void *
0x1800a530e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800a5313  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a531a  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a531f  call    cs:__imp_RegDeleteValueW
0x1800a5325  test    eax, eax
0x1800a5327  jz      short loc_1800A536E
0x1800a5329  mov     rcx, [rsp+2E8h]; this
0x1800a5331  mov     r9d, eax; char *
0x1800a5334  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a533b  mov     edx, 2CFh; void *
0x1800a5340  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a5345  mov     ebx, eax
0x1800a5347  lea     rcx, [rsp+2E8h+var_268]
0x1800a534f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5354  nop
0x1800a5355  lea     rcx, [rsp+2E8h+lpData]
0x1800a535a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a535f  nop
0x1800a5360  lea     rcx, [rsp+2E8h+hKey]
0x1800a5365  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a536a  mov     eax, ebx
0x1800a536c  jmp     short loc_1800A5399
0x1800a536e  lea     rcx, [rsp+2E8h+var_268]
0x1800a5376  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a537b  nop
0x1800a537c  lea     rcx, [rsp+2E8h+lpData]
0x1800a5381  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5386  nop
0x1800a5387  lea     rcx, [rsp+2E8h+hKey]
0x1800a538c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a5391  xor     eax, eax
0x1800a5393  jmp     short loc_1800A5399
0x1800a5395  mov     eax, [rsp+2E8h+Type]
0x1800a5399  mov     rcx, [rsp+2E8h+var_18]
0x1800a53a1  xor     rcx, rsp; StackCookie
0x1800a53a4  call    __security_check_cookie
0x1800a53a9  mov     rbx, [rsp+2E8h+arg_0]
0x1800a53b1  add     rsp, 2E0h
0x1800a53b8  pop     rdi
0x1800a53b9  retn
```
