# ModernDeployment::Autopilot::Core::FwtRecordId::GetNextRecordId(ulong &)

- ea: `0x1800e25ec`
- end: `0x1800e284d`
- name: `?GetNextRecordId@FwtRecordId@Core@Autopilot@ModernDeployment@@SAJAEAK@Z`
- size: `609`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800daa7c`

## callees

- `0x180067a54`
- `0x18006e0a8`
- `0x1800775c4`
- `0x18007ff90`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x1800e25ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2638`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2638`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e2799`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e2799`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e26aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e26aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e274c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e274c`

## string_xrefs

- `0x1800e2616`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`
- `0x1800e26cb`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`
- `0x1800e27ba`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`
- `0x1800e280c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtrecordid.cpp`

## pseudocode

```c
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtRecordId::GetNextRecordId(unsigned int *a1)
{
  const char *v2; // r9
  __int64 result; // rax
  bool v4; // al
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int ValueW; // eax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  int dwOptions; // [rsp+20h] [rbp-58h]
  int dwOptionsa; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-58h]
  int dwOptionsc; // [rsp+20h] [rbp-58h]
  DWORD pdwType; // [rsp+50h] [rbp-28h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v18[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int pvData; // [rsp+88h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+90h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
    {
      AcquireSRWLockExclusive(&stru_1802B2330);
      v18[0] = &stru_1802B2330;
      hkey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v4 = ZTPIsStateSeparationEnabled();
      v5 = (const WCHAR *)&stru_180228C20;
      if ( !v4 )
        v5 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
      v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
      {
        pvData = 0;
        pcbData = 4;
        pdwType = 0;
        ValueW = RegGetValueW(hkey, 0, L"FwtRecordId", 0x10u, &pdwType, &pvData, &pcbData);
        if ( (ValueW & 0xFFFFFFFC) != 0 || ValueW == 1 )
        {
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x32,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
                  (const char *)ValueW,
                  dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
          result = v11;
        }
        else
        {
          Data = pvData + 1;
          v9 = RegSetValueExW(hkey, L"FwtRecordId", 0, 4u, (const BYTE *)&Data, 4u);
          v10 = v9;
          if ( v9 > 0 )
            v10 = (unsigned __int16)v9 | 0x80070000;
          if ( (v10 & 0x80000000) == 0 )
          {
            *a1 = Data;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3D,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
              (const char *)v10,
              dwOptionsc);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
            result = v10;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
          (const char *)v7,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v18);
        result = v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
        (const char *)0x80004001LL,
        dwOptions);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x42,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtrecordid.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800e25ec  mov     [rsp+arg_0], rbx
0x1800e25f1  push    rdi
0x1800e25f2  sub     rsp, 70h
0x1800e25f6  mov     rdi, rcx
0x1800e25f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e2600  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e2605  test    al, al
0x1800e2607  jnz     short loc_1800E262E
0x1800e2609  mov     rcx, [rsp+78h]; this
0x1800e260e  mov     ebx, 80004001h
0x1800e2613  mov     r9d, ebx; char *
0x1800e2616  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e261d  mov     edx, 12h; void *
0x1800e2622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2627  mov     eax, ebx
0x1800e2629  jmp     loc_1800E283E
0x1800e262e  lea     rbx, stru_1802B2330
0x1800e2635  mov     rcx, rbx; SRWLock
0x1800e2638  call    cs:__imp_AcquireSRWLockExclusive
0x1800e263e  mov     [rsp+78h+var_18], rbx
0x1800e2643  mov     [rsp+78h+hkey], 0
0x1800e264c  xor     edx, edx
0x1800e264e  lea     rcx, [rsp+78h+hkey]
0x1800e2653  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800e2658  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800e265d  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800e2664  lea     rdx, stru_180228C20
0x1800e266b  test    al, al
0x1800e266d  cmovz   rdx, rcx; lpSubKey
0x1800e2671  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800e267a  lea     rax, [rsp+78h+hkey]
0x1800e267f  mov     [rsp+78h+phkResult], rax; phkResult
0x1800e2684  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800e268d  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800e2695  mov     [rsp+78h+dwOptions], 0; int
0x1800e269d  xor     r9d, r9d; lpClass
0x1800e26a0  xor     r8d, r8d; Reserved
0x1800e26a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e26aa  call    cs:__imp_RegCreateKeyExW
0x1800e26b0  mov     ebx, eax
0x1800e26b2  test    eax, eax
0x1800e26b4  jle     short loc_1800E26BF
0x1800e26b6  movzx   ebx, ax
0x1800e26b9  or      ebx, 80070000h
0x1800e26bf  test    ebx, ebx
0x1800e26c1  jns     short loc_1800E26F7
0x1800e26c3  mov     rcx, [rsp+78h]; this
0x1800e26c8  mov     r9d, ebx; char *
0x1800e26cb  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e26d2  mov     edx, 21h ; '!'; void *
0x1800e26d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e26dc  lea     rcx, [rsp+78h+hkey]
0x1800e26e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e26e6  lea     rcx, [rsp+78h+var_18]
0x1800e26eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e26f0  mov     eax, ebx
0x1800e26f2  jmp     loc_1800E283E
0x1800e26f7  mov     [rsp+78h+pvData], 0
0x1800e2702  mov     ebx, 4
0x1800e2707  mov     [rsp+78h+pcbData], ebx
0x1800e270e  mov     [rsp+78h+pdwType], 0
0x1800e2716  lea     rax, [rsp+78h+pcbData]
0x1800e271e  mov     [rsp+78h+lpSecurityAttributes], rax; pcbData
0x1800e2723  lea     rax, [rsp+78h+pvData]
0x1800e272b  mov     qword ptr [rsp+78h+samDesired], rax; pvData
0x1800e2730  lea     rax, [rsp+78h+pdwType]
0x1800e2735  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int
0x1800e273a  lea     r9d, [rbx+0Ch]; dwFlags
0x1800e273e  lea     r8, aFwtrecordid; "FwtRecordId"
0x1800e2745  xor     edx, edx; lpSubKey
0x1800e2747  mov     rcx, [rsp+78h+hkey]; hkey
0x1800e274c  call    cs:__imp_RegGetValueW
0x1800e2752  test    eax, 0FFFFFFFCh
0x1800e2757  jnz     loc_1800E2804
0x1800e275d  cmp     eax, 1
0x1800e2760  jz      loc_1800E2804
0x1800e2766  mov     eax, [rsp+78h+pvData]
0x1800e276d  inc     eax
0x1800e276f  mov     [rsp+78h+Data], eax
0x1800e2776  mov     [rsp+78h+samDesired], ebx; cbData
0x1800e277a  lea     rax, [rsp+78h+Data]
0x1800e2782  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x1800e2787  mov     r9d, ebx; dwType
0x1800e278a  xor     r8d, r8d; Reserved
0x1800e278d  lea     rdx, aFwtrecordid; "FwtRecordId"
0x1800e2794  mov     rcx, [rsp+78h+hkey]; hKey
0x1800e2799  call    cs:__imp_RegSetValueExW
0x1800e279f  mov     ebx, eax
0x1800e27a1  test    eax, eax
0x1800e27a3  jle     short loc_1800E27AE
0x1800e27a5  movzx   ebx, ax
0x1800e27a8  or      ebx, 80070000h
0x1800e27ae  test    ebx, ebx
0x1800e27b0  jns     short loc_1800E27E3
0x1800e27b2  mov     rcx, [rsp+78h]; this
0x1800e27b7  mov     r9d, ebx; char *
0x1800e27ba  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e27c1  mov     edx, 3Dh ; '='; void *
0x1800e27c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e27cb  lea     rcx, [rsp+78h+hkey]
0x1800e27d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e27d5  lea     rcx, [rsp+78h+var_18]
0x1800e27da  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e27df  mov     eax, ebx
0x1800e27e1  jmp     short loc_1800E283E
0x1800e27e3  mov     eax, [rsp+78h+Data]
0x1800e27ea  mov     [rdi], eax
0x1800e27ec  lea     rcx, [rsp+78h+hkey]
0x1800e27f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e27f6  lea     rcx, [rsp+78h+var_18]
0x1800e27fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e2800  xor     eax, eax
0x1800e2802  jmp     short loc_1800E283E
0x1800e2804  mov     rcx, [rsp+78h]; this
0x1800e2809  mov     r9d, eax; char *
0x1800e280c  lea     r8, aOnecoreuapAdmi_122; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2813  mov     edx, 32h ; '2'; void *
0x1800e2818  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e281d  mov     ebx, eax
0x1800e281f  lea     rcx, [rsp+78h+hkey]
0x1800e2824  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e2829  lea     rcx, [rsp+78h+var_18]
0x1800e282e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800e2833  mov     eax, ebx
0x1800e2835  jmp     short loc_1800E283E
0x1800e2837  mov     eax, [rsp+78h+pvData]
0x1800e283e  mov     rbx, [rsp+78h+arg_0]
0x1800e2846  add     rsp, 70h
0x1800e284a  pop     rdi
0x1800e284b  retn
```
