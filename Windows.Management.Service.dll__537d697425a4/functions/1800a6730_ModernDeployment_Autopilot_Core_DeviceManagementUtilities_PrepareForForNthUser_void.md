# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::PrepareForForNthUser(void)

- ea: `0x1800a6730`
- end: `0x1800a6a9f`
- name: `?PrepareForForNthUser@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJXZ`
- size: `879`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::DeviceManagementUtilities *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180084574`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x18008aea8`
- `0x1800a29e0`
- `0x1800a35f8`
- `0x1800a373c`
- `0x1800a6730`
- `0x1800a9668`
- `0x1800a9778`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a69fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a69fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a67f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a68ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a67f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a68ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a69c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a69c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a6799`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a6799`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a6902`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a6902`

## string_xrefs

- `0x1800a685a`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a68c6`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a69e0`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6a18`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`

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
0x1800a6730  mov     [rsp+arg_0], rbx
0x1800a6735  push    rdi
0x1800a6736  sub     rsp, 2E0h
0x1800a673d  mov     rax, cs:__security_cookie
0x1800a6744  xor     rax, rsp
0x1800a6747  mov     [rsp+2E8h+var_18], rax
0x1800a674f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete> `wil::Feature<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete>::GetImpl(void)'::`2'::impl
0x1800a6756  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotClearUserEspCacheOnComplete>::__private_IsEnabled(void)
0x1800a675b  test    al, al
0x1800a675d  jz      loc_1800A6A75
0x1800a6763  mov     [rsp+2E8h+hKey], 0
0x1800a676c  xor     edx, edx
0x1800a676e  lea     rcx, [rsp+2E8h+hKey]
0x1800a6773  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a6778  lea     rax, [rsp+2E8h+hKey]
0x1800a677d  mov     [rsp+2E8h+phkResult], rax; phkResult
0x1800a6782  mov     r9d, 0F003Fh; samDesired
0x1800a6788  xor     r8d, r8d; ulOptions
0x1800a678b  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800a6792  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a6799  call    cs:__imp_RegOpenKeyExW
0x1800a67a0  nop     dword ptr [rax+rax+00h]
0x1800a67a5  test    eax, eax
0x1800a67a7  jle     short loc_1800A67B3
0x1800a67a9  movzx   eax, ax
0x1800a67ac  or      eax, 80070000h
0x1800a67b1  test    eax, eax
0x1800a67b3  js      loc_1800A6A6B
0x1800a67b9  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a67be  test    rcx, rcx
0x1800a67c1  jz      loc_1800A6A6B
0x1800a67c7  mov     [rsp+2E8h+cbData], 0
0x1800a67cf  mov     [rsp+2E8h+Type], 1
0x1800a67d7  lea     rax, [rsp+2E8h+cbData]
0x1800a67dc  mov     [rsp+2E8h+lpcbData], rax; lpcbData
0x1800a67e1  mov     [rsp+2E8h+phkResult], 0; int
0x1800a67ea  lea     r9, [rsp+2E8h+Type]; lpType
0x1800a67ef  xor     r8d, r8d; lpReserved
0x1800a67f2  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a67f9  call    cs:__imp_RegQueryValueExW
0x1800a6800  nop     dword ptr [rax+rax+00h]
0x1800a6805  test    eax, eax
0x1800a6807  jle     short loc_1800A6813
0x1800a6809  movzx   eax, ax
0x1800a680c  or      eax, 80070000h
0x1800a6811  test    eax, eax
0x1800a6813  js      loc_1800A6A6B
0x1800a6819  mov     eax, [rsp+2E8h+cbData]
0x1800a681d  test    eax, eax
0x1800a681f  jz      loc_1800A6A6B
0x1800a6825  cmp     [rsp+2E8h+Type], 1
0x1800a682a  jnz     loc_1800A6A6B
0x1800a6830  mov     r8d, eax
0x1800a6833  xor     edx, edx
0x1800a6835  lea     rcx, [rsp+2E8h+lpData]
0x1800a683a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a683f  nop
0x1800a6840  mov     rbx, [rsp+2E8h+lpData]
0x1800a6845  test    rbx, rbx
0x1800a6848  jnz     short loc_1800A6888
0x1800a684a  mov     rcx, [rsp+2E8h]; this
0x1800a6852  mov     ebx, 8007000Eh
0x1800a6857  mov     r9d, ebx; char *
0x1800a685a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a6861  mov     edx, 2B5h; void *
0x1800a6866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a686b  nop
0x1800a686c  lea     rcx, [rsp+2E8h+lpData]
0x1800a6871  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6876  nop
0x1800a6877  lea     rcx, [rsp+2E8h+hKey]
0x1800a687c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6881  mov     eax, ebx
0x1800a6883  jmp     loc_1800A6A7D
0x1800a6888  lea     rax, [rsp+2E8h+cbData]
0x1800a688d  mov     [rsp+2E8h+lpcbData], rax; lpcbData
0x1800a6892  mov     [rsp+2E8h+phkResult], rbx; unsigned int
0x1800a6897  lea     r9, [rsp+2E8h+Type]; lpType
0x1800a689c  xor     r8d, r8d; lpReserved
0x1800a689f  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a68a6  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a68ab  call    cs:__imp_RegQueryValueExW
0x1800a68b2  nop     dword ptr [rax+rax+00h]
0x1800a68b7  test    eax, eax
0x1800a68b9  jz      short loc_1800A68F5
0x1800a68bb  mov     rcx, [rsp+2E8h]; this
0x1800a68c3  mov     r9d, eax; char *
0x1800a68c6  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a68cd  mov     edx, 2BDh; void *
0x1800a68d2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a68d7  mov     ebx, eax
0x1800a68d9  lea     rcx, [rsp+2E8h+lpData]
0x1800a68de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a68e3  nop
0x1800a68e4  lea     rcx, [rsp+2E8h+hKey]
0x1800a68e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a68ee  mov     eax, ebx
0x1800a68f0  jmp     loc_1800A6A7D
0x1800a68f5  xorps   xmm0, xmm0
0x1800a68f8  movups  xmmword ptr [rsp+2E8h+SystemTime.wYear], xmm0
0x1800a68fd  lea     rcx, [rsp+2E8h+SystemTime]; lpSystemTime
0x1800a6902  call    cs:__imp_GetSystemTime
0x1800a6909  nop     dword ptr [rax+rax+00h]
0x1800a690e  movzx   eax, [rsp+2E8h+SystemTime.wMilliseconds]
0x1800a6913  movzx   ecx, [rsp+2E8h+SystemTime.wSecond]
0x1800a6918  movzx   edx, [rsp+2E8h+SystemTime.wMinute]
0x1800a691d  movzx   r10d, [rsp+2E8h+SystemTime.wHour]
0x1800a6923  movzx   r11d, [rsp+2E8h+SystemTime.wDay]
0x1800a6929  movzx   r9d, [rsp+2E8h+SystemTime.wMonth]
0x1800a692f  movzx   r8d, [rsp+2E8h+SystemTime.wYear]
0x1800a6935  mov     [rsp+2E8h+var_2A8], eax
0x1800a6939  mov     [rsp+2E8h+var_2B0], ecx
0x1800a693d  mov     [rsp+2E8h+var_2B8], edx
0x1800a6941  mov     dword ptr [rsp+2E8h+lpcbData], r10d
0x1800a6946  mov     dword ptr [rsp+2E8h+phkResult], r11d
0x1800a694b  lea     rdx, a04d02d02dt02d0_0; ".%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x1800a6952  lea     rcx, [rsp+2E8h+var_228]
0x1800a695a  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x1800a695f  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a6966  lea     rcx, [rsp+2E8h+var_248]
0x1800a696e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a6973  nop
0x1800a6974  lea     r8, [rsp+2E8h+var_228]
0x1800a697c  mov     rdx, rax
0x1800a697f  lea     rcx, [rsp+2E8h+var_268]
0x1800a6987  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a698c  nop
0x1800a698d  lea     rcx, [rsp+2E8h+var_248]
0x1800a6995  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a699a  mov     edi, [rsp+2E8h+cbData]
0x1800a699e  lea     rcx, [rsp+2E8h+var_268]
0x1800a69a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a69ab  mov     rdx, rax; lpValueName
0x1800a69ae  mov     dword ptr [rsp+2E8h+lpcbData], edi; cbData
0x1800a69b2  mov     [rsp+2E8h+phkResult], rbx; unsigned int
0x1800a69b7  mov     r9d, 1; dwType
0x1800a69bd  xor     r8d, r8d; Reserved
0x1800a69c0  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a69c5  call    cs:__imp_RegSetValueExW
0x1800a69cc  nop     dword ptr [rax+rax+00h]
0x1800a69d1  mov     rcx, [rsp+2E8h]; this
0x1800a69d9  test    eax, eax
0x1800a69db  jz      short loc_1800A69F1
0x1800a69dd  mov     r9d, eax; char *
0x1800a69e0  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a69e7  mov     edx, 2CDh; void *
0x1800a69ec  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800a69f1  lea     rdx, aAccountsetupca; "AccountSetupCategory.Status"
0x1800a69f8  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a69fd  call    cs:__imp_RegDeleteValueW
0x1800a6a04  nop     dword ptr [rax+rax+00h]
0x1800a6a09  test    eax, eax
0x1800a6a0b  jz      short loc_1800A6A52
0x1800a6a0d  mov     rcx, [rsp+2E8h]; this
0x1800a6a15  mov     r9d, eax; char *
0x1800a6a18  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a6a1f  mov     edx, 2CFh; void *
0x1800a6a24  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6a29  mov     ebx, eax
0x1800a6a2b  lea     rcx, [rsp+2E8h+var_268]
0x1800a6a33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6a38  nop
0x1800a6a39  lea     rcx, [rsp+2E8h+lpData]
0x1800a6a3e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6a43  nop
0x1800a6a44  lea     rcx, [rsp+2E8h+hKey]
0x1800a6a49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6a4e  mov     eax, ebx
0x1800a6a50  jmp     short loc_1800A6A7D
0x1800a6a52  lea     rcx, [rsp+2E8h+var_268]
0x1800a6a5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6a5f  nop
0x1800a6a60  lea     rcx, [rsp+2E8h+lpData]
0x1800a6a65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6a6a  nop
0x1800a6a6b  lea     rcx, [rsp+2E8h+hKey]
0x1800a6a70  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6a75  xor     eax, eax
0x1800a6a77  jmp     short loc_1800A6A7D
0x1800a6a79  mov     eax, [rsp+2E8h+Type]
0x1800a6a7d  mov     rcx, [rsp+2E8h+var_18]
0x1800a6a85  xor     rcx, rsp; StackCookie
0x1800a6a88  call    __security_check_cookie
0x1800a6a8d  mov     rbx, [rsp+2E8h+arg_0]
0x1800a6a95  add     rsp, 2E0h
0x1800a6a9c  pop     rdi
0x1800a6a9d  retn
```
