# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::EnableEnhancedTpmTracing(void)

- ea: `0x1800d4a9c`
- end: `0x1800d4d92`
- name: `?EnableEnhancedTpmTracing@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ`
- size: `758`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d44e0`
- `0x1800d7080`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x180077d0c`
- `0x180081150`
- `0x180084d80`
- `0x18008a454`
- `0x1800d4a9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4afa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4b9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4c6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4d54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4afa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4b9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4c6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d4d54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d4adb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d4adb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d4c0d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d4c0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d4b43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d4b43`
- `dmenterprisediagnostics!StopAutoLog` at `0x1800d4cbc`
- `dmenterprisediagnostics!StopAutoLog` at `0x1800d4cbc`
- `dmenterprisediagnostics!StartAutoLog` at `0x1800d4ccf`
- `dmenterprisediagnostics!StartAutoLog` at `0x1800d4ccf`
- `dmenterprisediagnostics!SetupAutoLogWithTraceLevel` at `0x1800d4c9d`
- `dmenterprisediagnostics!SetupAutoLogWithTraceLevel` at `0x1800d4c9d`

## string_xrefs

- `0x1800d4b79`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d4c48`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d4d2f`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::EnableEnhancedTpmTracing(
        EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *this)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int v4; // edi
  bool v5; // sf
  DWORD v6; // r15d
  LSTATUS v7; // eax
  LSTATUS v8; // r14d
  unsigned int v9; // edi
  __int64 v10; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-278h]
  DWORD cchValueName; // [rsp+40h] [rbp-258h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-250h] BYREF
  DWORD Type; // [rsp+50h] [rbp-248h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+58h] [rbp-240h]
  WCHAR ValueName[264]; // [rsp+60h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( *((_BYTE *)this + 112) )
    return 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v15 = v3;
  if ( *((_BYTE *)this + 112) )
  {
    if ( v3 )
      LeaveCriticalSection(v3);
    return 0;
  }
  else
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Provisioning\\AutopilotTpmEnhancedLogging",
           0,
           0x20019u,
           &hKey);
    if ( (unsigned int)(v4 - 2) <= 1 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x835,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
        (const char *)((unsigned __int16)v4 | 0x80070000),
        (int)phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( v3 )
        LeaveCriticalSection(v3);
      return 0;
    }
    else
    {
      v5 = v4 < 0;
      if ( v4 > 0 )
      {
        v4 = (unsigned __int16)v4 | 0x80070000;
        v5 = v4 < 0;
      }
      if ( v5 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x838,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
          (const char *)(unsigned int)v4,
          (int)phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        if ( v3 )
          LeaveCriticalSection(v3);
        return (unsigned int)v4;
      }
      else
      {
        v6 = 0;
        do
        {
          memset_0(ValueName, 0, 0x208u);
          cchValueName = 260;
          Type = 0;
          v7 = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, &Type, 0, 0);
          v8 = v7;
          if ( v7 == 259 )
            break;
          if ( v7 > 0 )
            v9 = (unsigned __int16)v7 | 0x80070000;
          else
            v9 = v7;
          if ( (v9 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x852,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
              (const char *)v9,
              (int)phkResult);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            if ( v3 )
              LeaveCriticalSection(v3);
            return v9;
          }
          if ( Type == 1 )
            SetupAutoLogWithTraceLevel(L"Autopilot", ValueName, 1, 5);
          ++v6;
        }
        while ( !v8 );
        StopAutoLog(L"Autopilot");
        StartAutoLog(L"Autopilot");
        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
          McTemplateU0q_EventWriteTransfer(v10, AutopilotManagerTpmEnhancedTracingEnabled, v6);
        *((_BYTE *)this + 112) = 1;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        if ( v3 )
          LeaveCriticalSection(v3);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800d4a9c  mov     [rsp+arg_8], rbx
0x1800d4aa1  mov     [rsp+arg_10], rsi
0x1800d4aa6  push    rdi
0x1800d4aa7  push    r14
0x1800d4aa9  push    r15
0x1800d4aab  sub     rsp, 280h
0x1800d4ab2  mov     rax, cs:__security_cookie
0x1800d4ab9  xor     rax, rsp
0x1800d4abc  mov     [rsp+298h+var_28], rax
0x1800d4ac4  mov     rsi, rcx
0x1800d4ac7  cmp     byte ptr [rcx+70h], 0
0x1800d4acb  jz      short loc_1800D4AD4
0x1800d4acd  xor     eax, eax
0x1800d4acf  jmp     loc_1800D4D68
0x1800d4ad4  lea     rbx, [rcx+30h]
0x1800d4ad8  mov     rcx, rbx; lpCriticalSection
0x1800d4adb  call    cs:__imp_EnterCriticalSection
0x1800d4ae2  nop     dword ptr [rax+rax+00h]
0x1800d4ae7  mov     [rsp+298h+var_240], rbx
0x1800d4aec  cmp     byte ptr [rsi+70h], 0
0x1800d4af0  jz      short loc_1800D4B0D
0x1800d4af2  test    rbx, rbx
0x1800d4af5  jz      short loc_1800D4B06
0x1800d4af7  mov     rcx, rbx; lpCriticalSection
0x1800d4afa  call    cs:__imp_LeaveCriticalSection
0x1800d4b01  nop     dword ptr [rax+rax+00h]
0x1800d4b06  xor     eax, eax
0x1800d4b08  jmp     loc_1800D4D68
0x1800d4b0d  mov     [rsp+298h+hKey], 0
0x1800d4b16  xor     edx, edx
0x1800d4b18  lea     rcx, [rsp+298h+hKey]
0x1800d4b1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d4b22  lea     rax, [rsp+298h+hKey]
0x1800d4b27  mov     [rsp+298h+phkResult], rax; int
0x1800d4b2c  mov     r9d, 20019h; samDesired
0x1800d4b32  xor     r8d, r8d; ulOptions
0x1800d4b35  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800d4b3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d4b43  call    cs:__imp_RegOpenKeyExW
0x1800d4b4a  nop     dword ptr [rax+rax+00h]
0x1800d4b4f  mov     edi, eax
0x1800d4b51  add     eax, 0FFFFFFFEh
0x1800d4b54  cmp     eax, 1
0x1800d4b57  jbe     loc_1800D4D1A
0x1800d4b5d  test    edi, edi
0x1800d4b5f  jle     short loc_1800D4B6C
0x1800d4b61  movzx   edi, di
0x1800d4b64  or      edi, 80070000h
0x1800d4b6a  test    edi, edi
0x1800d4b6c  jns     short loc_1800D4BB1
0x1800d4b6e  mov     rcx, [rsp+298h]; this
0x1800d4b76  mov     r9d, edi; char *
0x1800d4b79  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d4b80  mov     edx, 838h; void *
0x1800d4b85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4b8a  nop
0x1800d4b8b  lea     rcx, [rsp+298h+hKey]
0x1800d4b90  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d4b95  nop
0x1800d4b96  test    rbx, rbx
0x1800d4b99  jz      short loc_1800D4BAA
0x1800d4b9b  mov     rcx, rbx; lpCriticalSection
0x1800d4b9e  call    cs:__imp_LeaveCriticalSection
0x1800d4ba5  nop     dword ptr [rax+rax+00h]
0x1800d4baa  mov     eax, edi
0x1800d4bac  jmp     loc_1800D4D68
0x1800d4bb1  xor     r15d, r15d
0x1800d4bb4  xor     edx, edx; Val
0x1800d4bb6  mov     r8d, 208h; Size
0x1800d4bbc  lea     rcx, [rsp+298h+ValueName]; void *
0x1800d4bc1  call    memset_0
0x1800d4bc6  mov     [rsp+298h+cchValueName], 104h
0x1800d4bce  mov     [rsp+298h+Type], 0
0x1800d4bd6  mov     [rsp+298h+lpcbData], 0; lpcbData
0x1800d4bdf  mov     [rsp+298h+lpData], 0; lpData
0x1800d4be8  lea     rax, [rsp+298h+Type]
0x1800d4bed  mov     [rsp+298h+lpType], rax; lpType
0x1800d4bf2  mov     [rsp+298h+phkResult], 0; int
0x1800d4bfb  lea     r9, [rsp+298h+cchValueName]; lpcchValueName
0x1800d4c00  lea     r8, [rsp+298h+ValueName]; lpValueName
0x1800d4c05  mov     edx, r15d; dwIndex
0x1800d4c08  mov     rcx, [rsp+298h+hKey]; hKey
0x1800d4c0d  call    cs:__imp_RegEnumValueW
0x1800d4c14  nop     dword ptr [rax+rax+00h]
0x1800d4c19  mov     r14d, eax
0x1800d4c1c  cmp     eax, 103h
0x1800d4c21  jz      loc_1800D4CB5
0x1800d4c27  test    eax, eax
0x1800d4c29  jg      short loc_1800D4C2F
0x1800d4c2b  mov     edi, eax
0x1800d4c2d  jmp     short loc_1800D4C39
0x1800d4c2f  movzx   edi, r14w
0x1800d4c33  or      edi, 80070000h
0x1800d4c39  test    edi, edi
0x1800d4c3b  jns     short loc_1800D4C80
0x1800d4c3d  mov     rcx, [rsp+298h]; this
0x1800d4c45  mov     r9d, edi; char *
0x1800d4c48  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d4c4f  mov     edx, 852h; void *
0x1800d4c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4c59  nop
0x1800d4c5a  lea     rcx, [rsp+298h+hKey]
0x1800d4c5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d4c64  nop
0x1800d4c65  test    rbx, rbx
0x1800d4c68  jz      short loc_1800D4C79
0x1800d4c6a  mov     rcx, rbx; lpCriticalSection
0x1800d4c6d  call    cs:__imp_LeaveCriticalSection
0x1800d4c74  nop     dword ptr [rax+rax+00h]
0x1800d4c79  mov     eax, edi
0x1800d4c7b  jmp     loc_1800D4D68
0x1800d4c80  cmp     [rsp+298h+Type], 1
0x1800d4c85  jnz     short loc_1800D4CA9
0x1800d4c87  mov     r9d, 5
0x1800d4c8d  lea     r8d, [r9-4]
0x1800d4c91  lea     rdx, [rsp+298h+ValueName]
0x1800d4c96  lea     rcx, aAutopilot; "Autopilot"
0x1800d4c9d  call    cs:__imp_?SetupAutoLogWithTraceLevel@@YAJPEBG0HH@Z; SetupAutoLogWithTraceLevel(ushort const *,ushort const *,int,int)
0x1800d4ca4  nop     dword ptr [rax+rax+00h]
0x1800d4ca9  inc     r15d
0x1800d4cac  test    r14d, r14d
0x1800d4caf  jz      loc_1800D4BB4
0x1800d4cb5  lea     rcx, aAutopilot; "Autopilot"
0x1800d4cbc  call    cs:__imp_?StopAutoLog@@YAJPEBG@Z; StopAutoLog(ushort const *)
0x1800d4cc3  nop     dword ptr [rax+rax+00h]
0x1800d4cc8  lea     rcx, aAutopilot; "Autopilot"
0x1800d4ccf  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x1800d4cd6  nop     dword ptr [rax+rax+00h]
0x1800d4cdb  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800d4ce2  jz      short loc_1800D4CF3
0x1800d4ce4  mov     r8d, r15d
0x1800d4ce7  lea     rdx, AutopilotManagerTpmEnhancedTracingEnabled
0x1800d4cee  call    McTemplateU0q_EventWriteTransfer
0x1800d4cf3  mov     byte ptr [rsi+70h], 1
0x1800d4cf7  lea     rcx, [rsp+298h+hKey]
0x1800d4cfc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d4d01  nop
0x1800d4d02  test    rbx, rbx
0x1800d4d05  jz      short loc_1800D4D16
0x1800d4d07  mov     rcx, rbx; lpCriticalSection
0x1800d4d0a  call    cs:__imp_LeaveCriticalSection
0x1800d4d11  nop     dword ptr [rax+rax+00h]
0x1800d4d16  xor     eax, eax
0x1800d4d18  jmp     short loc_1800D4D68
0x1800d4d1a  movzx   r9d, di
0x1800d4d1e  or      r9d, 80070000h; char *
0x1800d4d25  mov     rcx, [rsp+298h]; this
0x1800d4d2d  jge     short loc_1800D4D41
0x1800d4d2f  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d4d36  mov     edx, 835h; void *
0x1800d4d3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d4d40  nop
0x1800d4d41  lea     rcx, [rsp+298h+hKey]
0x1800d4d46  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d4d4b  nop
0x1800d4d4c  test    rbx, rbx
0x1800d4d4f  jz      short loc_1800D4D60
0x1800d4d51  mov     rcx, rbx; lpCriticalSection
0x1800d4d54  call    cs:__imp_LeaveCriticalSection
0x1800d4d5b  nop     dword ptr [rax+rax+00h]
0x1800d4d60  xor     eax, eax
0x1800d4d62  jmp     short loc_1800D4D68
0x1800d4d64  mov     eax, [rsp+298h+cchValueName]
0x1800d4d68  mov     rcx, [rsp+298h+var_28]
0x1800d4d70  xor     rcx, rsp; StackCookie
0x1800d4d73  call    __security_check_cookie
0x1800d4d78  lea     r11, [rsp+298h+var_18]
0x1800d4d80  mov     rbx, [r11+28h]
0x1800d4d84  mov     rsi, [r11+30h]
0x1800d4d88  mov     rsp, r11
0x1800d4d8b  pop     r15
0x1800d4d8d  pop     r14
0x1800d4d8f  pop     rdi
0x1800d4d90  retn
```
