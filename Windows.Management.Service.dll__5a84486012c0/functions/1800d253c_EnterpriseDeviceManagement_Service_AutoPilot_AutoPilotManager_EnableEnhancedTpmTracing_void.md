# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::EnableEnhancedTpmTracing(void)

- ea: `0x1800d253c`
- end: `0x1800d27f0`
- name: `?EnableEnhancedTpmTracing@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ`
- size: `692`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d1f9c`
- `0x1800d4a68`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x18007748c`
- `0x180080708`
- `0x180084208`
- `0x180089614`
- `0x1800d253c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d2594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d262c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d26ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d2774`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d27b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d2594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d262c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d26ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d2774`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d27b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d257b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d257b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d2695`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d2695`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d25d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d25d7`
- `dmenterprisediagnostics!StopAutoLog` at `0x1800d2732`
- `dmenterprisediagnostics!StopAutoLog` at `0x1800d2732`
- `dmenterprisediagnostics!StartAutoLog` at `0x1800d273f`
- `dmenterprisediagnostics!StartAutoLog` at `0x1800d273f`
- `dmenterprisediagnostics!SetupAutoLogWithTraceLevel` at `0x1800d2719`
- `dmenterprisediagnostics!SetupAutoLogWithTraceLevel` at `0x1800d2719`

## string_xrefs

- `0x1800d2607`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d26ca`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d2793`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

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
0x1800d253c  mov     [rsp+arg_8], rbx
0x1800d2541  mov     [rsp+arg_10], rsi
0x1800d2546  push    rdi
0x1800d2547  push    r14
0x1800d2549  push    r15
0x1800d254b  sub     rsp, 280h
0x1800d2552  mov     rax, cs:__security_cookie
0x1800d2559  xor     rax, rsp
0x1800d255c  mov     [rsp+298h+var_28], rax
0x1800d2564  mov     rsi, rcx
0x1800d2567  cmp     byte ptr [rcx+70h], 0
0x1800d256b  jz      short loc_1800D2574
0x1800d256d  xor     eax, eax
0x1800d256f  jmp     loc_1800D27C6
0x1800d2574  lea     rbx, [rcx+30h]
0x1800d2578  mov     rcx, rbx; lpCriticalSection
0x1800d257b  call    cs:__imp_EnterCriticalSection
0x1800d2581  mov     [rsp+298h+var_240], rbx
0x1800d2586  cmp     byte ptr [rsi+70h], 0
0x1800d258a  jz      short loc_1800D25A1
0x1800d258c  test    rbx, rbx
0x1800d258f  jz      short loc_1800D259A
0x1800d2591  mov     rcx, rbx; lpCriticalSection
0x1800d2594  call    cs:__imp_LeaveCriticalSection
0x1800d259a  xor     eax, eax
0x1800d259c  jmp     loc_1800D27C6
0x1800d25a1  mov     [rsp+298h+hKey], 0
0x1800d25aa  xor     edx, edx
0x1800d25ac  lea     rcx, [rsp+298h+hKey]
0x1800d25b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d25b6  lea     rax, [rsp+298h+hKey]
0x1800d25bb  mov     [rsp+298h+phkResult], rax; int
0x1800d25c0  mov     r9d, 20019h; samDesired
0x1800d25c6  xor     r8d, r8d; ulOptions
0x1800d25c9  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800d25d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d25d7  call    cs:__imp_RegOpenKeyExW
0x1800d25dd  mov     edi, eax
0x1800d25df  add     eax, 0FFFFFFFEh
0x1800d25e2  cmp     eax, 1
0x1800d25e5  jbe     loc_1800D277E
0x1800d25eb  test    edi, edi
0x1800d25ed  jle     short loc_1800D25FA
0x1800d25ef  movzx   edi, di
0x1800d25f2  or      edi, 80070000h
0x1800d25f8  test    edi, edi
0x1800d25fa  jns     short loc_1800D2639
0x1800d25fc  mov     rcx, [rsp+298h]; this
0x1800d2604  mov     r9d, edi; char *
0x1800d2607  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d260e  mov     edx, 838h; void *
0x1800d2613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2618  nop
0x1800d2619  lea     rcx, [rsp+298h+hKey]
0x1800d261e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2623  nop
0x1800d2624  test    rbx, rbx
0x1800d2627  jz      short loc_1800D2632
0x1800d2629  mov     rcx, rbx; lpCriticalSection
0x1800d262c  call    cs:__imp_LeaveCriticalSection
0x1800d2632  mov     eax, edi
0x1800d2634  jmp     loc_1800D27C6
0x1800d2639  xor     r15d, r15d
0x1800d263c  xor     edx, edx; Val
0x1800d263e  mov     r8d, 208h; Size
0x1800d2644  lea     rcx, [rsp+298h+ValueName]; void *
0x1800d2649  call    memset_0
0x1800d264e  mov     [rsp+298h+cchValueName], 104h
0x1800d2656  mov     [rsp+298h+Type], 0
0x1800d265e  mov     [rsp+298h+lpcbData], 0; lpcbData
0x1800d2667  mov     [rsp+298h+lpData], 0; lpData
0x1800d2670  lea     rax, [rsp+298h+Type]
0x1800d2675  mov     [rsp+298h+lpType], rax; lpType
0x1800d267a  mov     [rsp+298h+phkResult], 0; int
0x1800d2683  lea     r9, [rsp+298h+cchValueName]; lpcchValueName
0x1800d2688  lea     r8, [rsp+298h+ValueName]; lpValueName
0x1800d268d  mov     edx, r15d; dwIndex
0x1800d2690  mov     rcx, [rsp+298h+hKey]; hKey
0x1800d2695  call    cs:__imp_RegEnumValueW
0x1800d269b  mov     r14d, eax
0x1800d269e  cmp     eax, 103h
0x1800d26a3  jz      loc_1800D272B
0x1800d26a9  test    eax, eax
0x1800d26ab  jg      short loc_1800D26B1
0x1800d26ad  mov     edi, eax
0x1800d26af  jmp     short loc_1800D26BB
0x1800d26b1  movzx   edi, r14w
0x1800d26b5  or      edi, 80070000h
0x1800d26bb  test    edi, edi
0x1800d26bd  jns     short loc_1800D26FC
0x1800d26bf  mov     rcx, [rsp+298h]; this
0x1800d26c7  mov     r9d, edi; char *
0x1800d26ca  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d26d1  mov     edx, 852h; void *
0x1800d26d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d26db  nop
0x1800d26dc  lea     rcx, [rsp+298h+hKey]
0x1800d26e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d26e6  nop
0x1800d26e7  test    rbx, rbx
0x1800d26ea  jz      short loc_1800D26F5
0x1800d26ec  mov     rcx, rbx; lpCriticalSection
0x1800d26ef  call    cs:__imp_LeaveCriticalSection
0x1800d26f5  mov     eax, edi
0x1800d26f7  jmp     loc_1800D27C6
0x1800d26fc  cmp     [rsp+298h+Type], 1
0x1800d2701  jnz     short loc_1800D271F
0x1800d2703  mov     r9d, 5
0x1800d2709  lea     r8d, [r9-4]
0x1800d270d  lea     rdx, [rsp+298h+ValueName]
0x1800d2712  lea     rcx, aAutopilot; "Autopilot"
0x1800d2719  call    cs:__imp_?SetupAutoLogWithTraceLevel@@YAJPEBG0HH@Z; SetupAutoLogWithTraceLevel(ushort const *,ushort const *,int,int)
0x1800d271f  inc     r15d
0x1800d2722  test    r14d, r14d
0x1800d2725  jz      loc_1800D263C
0x1800d272b  lea     rcx, aAutopilot; "Autopilot"
0x1800d2732  call    cs:__imp_?StopAutoLog@@YAJPEBG@Z; StopAutoLog(ushort const *)
0x1800d2738  lea     rcx, aAutopilot; "Autopilot"
0x1800d273f  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x1800d2745  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800d274c  jz      short loc_1800D275D
0x1800d274e  mov     r8d, r15d
0x1800d2751  lea     rdx, AutopilotManagerTpmEnhancedTracingEnabled
0x1800d2758  call    McTemplateU0q_EventWriteTransfer
0x1800d275d  mov     byte ptr [rsi+70h], 1
0x1800d2761  lea     rcx, [rsp+298h+hKey]
0x1800d2766  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d276b  nop
0x1800d276c  test    rbx, rbx
0x1800d276f  jz      short loc_1800D277A
0x1800d2771  mov     rcx, rbx; lpCriticalSection
0x1800d2774  call    cs:__imp_LeaveCriticalSection
0x1800d277a  xor     eax, eax
0x1800d277c  jmp     short loc_1800D27C6
0x1800d277e  movzx   r9d, di
0x1800d2782  or      r9d, 80070000h; char *
0x1800d2789  mov     rcx, [rsp+298h]; this
0x1800d2791  jge     short loc_1800D27A5
0x1800d2793  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d279a  mov     edx, 835h; void *
0x1800d279f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d27a4  nop
0x1800d27a5  lea     rcx, [rsp+298h+hKey]
0x1800d27aa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d27af  nop
0x1800d27b0  test    rbx, rbx
0x1800d27b3  jz      short loc_1800D27BE
0x1800d27b5  mov     rcx, rbx; lpCriticalSection
0x1800d27b8  call    cs:__imp_LeaveCriticalSection
0x1800d27be  xor     eax, eax
0x1800d27c0  jmp     short loc_1800D27C6
0x1800d27c2  mov     eax, [rsp+298h+cchValueName]
0x1800d27c6  mov     rcx, [rsp+298h+var_28]
0x1800d27ce  xor     rcx, rsp; StackCookie
0x1800d27d1  call    __security_check_cookie
0x1800d27d6  lea     r11, [rsp+298h+var_18]
0x1800d27de  mov     rbx, [r11+28h]
0x1800d27e2  mov     rsi, [r11+30h]
0x1800d27e6  mov     rsp, r11
0x1800d27e9  pop     r15
0x1800d27eb  pop     r14
0x1800d27ed  pop     rdi
0x1800d27ee  retn
```
