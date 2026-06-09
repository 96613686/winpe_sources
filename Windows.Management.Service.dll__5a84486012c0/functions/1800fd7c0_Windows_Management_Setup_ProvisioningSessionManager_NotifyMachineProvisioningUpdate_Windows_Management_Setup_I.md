# Windows::Management::Setup::ProvisioningSessionManager::NotifyMachineProvisioningUpdate(Windows::Management::Setup::IMachineProvisioningProgressReporter *,_GUID const &,Windows::Management::Setup::IAgentProvisioningProgressReport *)

- ea: `0x1800fd7c0`
- end: `0x1800fe034`
- name: `?NotifyMachineProvisioningUpdate@ProvisioningSessionManager@Setup@Management@Windows@@UEAAJPEAUIMachineProvisioningProgressReporter@234@AEBU_GUID@@PEAUIAgentProvisioningProgressReport@234@@Z`
- size: `2164`
- prototype: `__int64 __fastcall(Windows::Management::Setup::ProvisioningSessionManager *__hidden this, struct Windows::Management::Setup::IMachineProvisioningProgressReporter *, const struct _GUID *, struct Windows::Management::Setup::IAgentProvisioningProgressReport *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007748c`
- `0x18007755c`
- `0x1800775c4`
- `0x18008019c`
- `0x1800839bc`
- `0x18008dc94`
- `0x1800cffd0`
- `0x1800d84e0`
- `0x1800dfdf0`
- `0x1800e0a4c`
- `0x1800fb834`
- `0x1800fb9a0`
- `0x1800fcf9c`
- `0x1800fd7c0`
- `0x1800fffa4`
- `0x18010006c`
- `0x18010024c`
- `0x180103b04`
- `0x1801045b4`
- `0x180104628`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fdafb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fdafb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fdabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fdcdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fdabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fdcdb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800fdf99`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800fdf99`

## string_xrefs

- `0x1800fde09`: `WindowsAutopilot.Telemetry.EarlyBoot.DPP.AgentProvisioning`
- `0x1800fd862`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fd8a4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fde26`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fde8d`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fdee5`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fdf51`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fdfd8`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1800fd803`: `NotifyMachineProvisioningUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall Windows::Management::Setup::ProvisioningSessionManager::NotifyMachineProvisioningUpdate(
        Windows::Management::Setup::ProvisioningSessionManager *this,
        struct Windows::Management::Setup::IMachineProvisioningProgressReporter *a2,
        const struct _GUID *a3,
        struct Windows::Management::Setup::IAgentProvisioningProgressReport *a4)
{
  const struct _GUID *v5; // r14
  const struct Windows::Management::Setup::IMachineProvisioningProgressReporter *v6; // r15
  unsigned int v8; // esi
  bool v10; // r9
  int (__fastcall *v11)(struct Windows::Management::Setup::IAgentProvisioningProgressReport *, __int64 *); // rbx
  unsigned int i; // r14d
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rbx
  int (__fastcall *v16)(__int64, __int64 *); // rdi
  int v17; // r15d
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, _QWORD, __int64 *); // rbx
  __int64 v20; // rbx
  void (__fastcall *v21)(__int64, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v23; // rdi
  int (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // ecx
  __int64 v26; // rdi
  int (__fastcall *v27)(__int64, __int64 *); // rbx
  bool v28; // si
  int v29; // edi
  __int64 j; // rax
  const unsigned __int16 *v31; // rbx
  __int64 v32; // rdx
  int v33; // eax
  int IsSame; // eax
  unsigned int v35; // ebx
  const struct ModernDeployment::Autopilot::Core::IAutopilotDevicePreparationOrchestrator *AutopilotDevicePreparationOrchestrator; // rax
  bool v37; // r9
  int v38; // eax
  unsigned int v39; // ebx
  bool v40; // bl
  __int64 AutopilotDevicePreparationOrchestratorFunction; // rax
  __int64 v42; // rcx
  int v43; // ebx
  int v44; // [rsp+20h] [rbp-1F8h]
  __int64 v45; // [rsp+40h] [rbp-1D8h] BYREF
  int v46; // [rsp+48h] [rbp-1D0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-1C8h] BYREF
  __int64 v48; // [rsp+58h] [rbp-1C0h] BYREF
  unsigned int v49; // [rsp+60h] [rbp-1B8h] BYREF
  unsigned int v50; // [rsp+64h] [rbp-1B4h] BYREF
  int v51; // [rsp+68h] [rbp-1B0h] BYREF
  int v52; // [rsp+6Ch] [rbp-1ACh] BYREF
  int v53; // [rsp+70h] [rbp-1A8h] BYREF
  int v54; // [rsp+74h] [rbp-1A4h] BYREF
  __int64 v55; // [rsp+78h] [rbp-1A0h] BYREF
  __int64 v56; // [rsp+80h] [rbp-198h] BYREF
  HSTRING string; // [rsp+88h] [rbp-190h] BYREF
  __int64 v58; // [rsp+90h] [rbp-188h] BYREF
  __int64 v59; // [rsp+98h] [rbp-180h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-178h] BYREF
  struct Windows::Management::Setup::IAgentProvisioningProgressReport *v61; // [rsp+A8h] [rbp-170h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-168h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-158h]
  const struct _GUID *v64; // [rsp+C8h] [rbp-150h]
  _OWORD v65[2]; // [rsp+D0h] [rbp-148h] BYREF
  _BYTE v66[64]; // [rsp+F0h] [rbp-128h] BYREF
  _DWORD v67[32]; // [rsp+130h] [rbp-E8h] BYREF
  _BYTE v68[32]; // [rsp+1B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v5 = a3;
  v64 = a3;
  v6 = a2;
  v61 = a2;
  std::wstring::wstring(v68, L"NotifyMachineProvisioningUpdate");
  Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
  std::wstring::_Tidy_deallocate(v68);
  v8 = 0;
  if ( v6 )
  {
    if ( a4 )
    {
      (*(void (__fastcall **)(char *, const struct _GUID *, struct Windows::Management::Setup::IAgentProvisioningProgressReport *))(*((_QWORD *)this + 166) + 56LL))(
        (char *)this + 1328,
        v5,
        a4);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
      {
        v46 = 0;
        if ( (*(int (__fastcall **)(struct Windows::Management::Setup::IAgentProvisioningProgressReport *, int *))(*(_QWORD *)a4 + 48LL))(
               a4,
               &v46) >= 0
          && (unsigned int)(v46 - 3) <= 3 )
        {
          v62 = 0;
          v63 = 0;
          v59 = 0;
          v11 = *(int (__fastcall **)(struct Windows::Management::Setup::IAgentProvisioningProgressReport *, __int64 *))(*(_QWORD *)a4 + 128LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
          if ( v11(a4, &v59) >= 0 && v59 )
          {
            v49 = 0;
            (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v59 + 56LL))(v59, &v49);
            for ( i = 0; i < v49; ++i )
            {
              v60 = 0;
              v13 = v59;
              v14 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v59 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
              if ( v14(v13, i, &v60) >= 0 )
              {
                v15 = v60;
                if ( v60 )
                {
                  v58 = 0;
                  v16 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 72LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
                  if ( v16(v15, &v58) >= 0 && v58 )
                  {
                    v50 = 0;
                    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 56LL))(v58, &v50);
                    while ( v8 < v50 )
                    {
                      v17 = 0;
                      v45 = 0;
                      v18 = v58;
                      v19 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 48LL);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                      if ( v19(v18, v8, &v45) >= 0 )
                      {
                        v20 = v45;
                        if ( v45 )
                        {
                          string = 0;
                          v21 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 48LL);
                          WindowsDeleteString(0);
                          string = 0;
                          v21(v20, &string);
                          std::wstring::wstring(v66, L"WindowsAutopilot.Telemetry.EarlyBoot.DPP.Workload.");
                          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                          std::wstring::append(v66, StringRawBuffer);
                          v51 = 0;
                          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 168LL))(v45, &v51);
                          LOBYTE(v17) = v51 == 2;
                          v52 = 0;
                          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 104LL))(v45, &v52);
                          v48 = 0;
                          v56 = 0;
                          v55 = 0;
                          v23 = v45;
                          v24 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 72LL);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
                          if ( v24(v23, &v56) >= 0 )
                          {
                            if ( v56 )
                            {
                              v26 = v45;
                              v27 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 88LL);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                              if ( v27(v26, &v55) >= 0 )
                              {
                                if ( v55 )
                                {
                                  v47 = 0;
                                  v48 = 0;
                                  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 48LL))(v56, &v47);
                                  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 48LL))(v55, &v48);
                                  v25 = v48 - v47;
                                  v48 = (v48 - v47) / 10000;
                                }
                              }
                            }
                          }
                          v53 = 0;
                          v54 = v52;
                          LODWORD(v47) = v17;
                          if ( *((_QWORD *)&v62 + 1) == v63 )
                          {
                            std::vector<ModernDeployment::Autopilot::Core::FwtPhase>::_Emplace_reallocate<std::wstring &,int,__int64 &,int,int>(
                              (unsigned int)&v62,
                              DWORD2(v62),
                              (unsigned int)v66,
                              (unsigned int)&v47,
                              (__int64)&v48,
                              (__int64)&v54,
                              (__int64)&v53);
                          }
                          else
                          {
                            std::_Default_allocator_traits<std::allocator<ModernDeployment::Autopilot::Core::FwtPhase>>::construct<ModernDeployment::Autopilot::Core::FwtPhase,std::wstring &,int,__int64 &,int,int>(
                              v25,
                              DWORD2(v62),
                              (unsigned int)v66,
                              (unsigned int)&v47,
                              (__int64)&v48,
                              (__int64)&v54,
                              (__int64)&v53);
                            *((_QWORD *)&v62 + 1) += 80LL;
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
                          std::wstring::_Tidy_deallocate(v66);
                          WindowsDeleteString(string);
                          string = 0;
                        }
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                      ++v8;
                    }
                    v8 = 0;
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
            }
            v5 = v64;
            v6 = v61;
          }
          v28 = v46 == 3;
          v29 = 0;
          for ( j = v62; j != *((_QWORD *)&v62 + 1); j += 80 )
          {
            if ( *(_DWORD *)(j + 48) )
            {
              v29 = *(_DWORD *)(j + 48);
              break;
            }
          }
          v65[0] = 0;
          v65[1] = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v65[0]) = 0;
          v31 = 0;
          if ( (_QWORD)v62 != *((_QWORD *)&v62 + 1)
            && (int)ModernDeployment::Autopilot::Core::FwtPhase::SerializePhasesToJsonString(&v62, v65) >= 0 )
          {
            v31 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
          }
          if ( *((_QWORD *)this + 51) )
            v32 = (*(_QWORD *)std::chrono::steady_clock::now(&v61) - *((_QWORD *)this + 51)) / 1000000LL;
          else
            v32 = 0;
          v33 = ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(
                  L"WindowsAutopilot.Telemetry.EarlyBoot.DPP.AgentProvisioning",
                  v28,
                  v29,
                  v32,
                  v31);
          if ( v33 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1B0,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningse"
                            "ssionmanager.cpp",
              (const char *)(unsigned int)v33,
              v44);
          std::wstring::_Tidy_deallocate(v65);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
          std::vector<ModernDeployment::Autopilot::Core::FwtPhase>::_Tidy(&v62);
        }
      }
      IsSame = Windows::Management::Setup::ProvisioningSessionAssociation::ValidateIsSame(
                 (Windows::Management::Setup::ProvisioningSessionManager *)((char *)this + 416),
                 v6,
                 v5,
                 v10);
      v35 = IsSame;
      v67[0] = IsSame;
      if ( IsSame >= 0 )
      {
        AutopilotDevicePreparationOrchestrator = Windows::Management::Setup::ProvisioningSessionAssociation::GetAutopilotDevicePreparationOrchestrator((Windows::Management::Setup::ProvisioningSessionManager *)((char *)this + 416));
        v38 = Windows::Management::Setup::ProvisioningSessionAssociation::ValidateIsSame(
                (Windows::Management::Setup::ProvisioningSessionManager *)((char *)this + 1120),
                AutopilotDevicePreparationOrchestrator,
                v5,
                v37);
        v39 = v38;
        v67[0] = v38;
        if ( v38 >= 0 )
        {
          v40 = *(_QWORD *)(Windows::Management::Setup::ProvisioningSessionAssociationWithFunctionT<std::function<long (Windows::Management::Setup::IAgentProvisioningProgressReport *)>>::GetAutopilotDevicePreparationOrchestratorFunction(
                              (char *)this + 496,
                              v66)
                          + 56) == 0;
          std::_Func_class<bool,std::wstring const &>::_Tidy(v66);
          if ( v40 )
          {
            v67[0] = -2130464762;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1BA,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningse"
                            "ssionmanager.cpp",
              (const char *)0x8103B006LL,
              v44);
            Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
            return 2164502534LL;
          }
          else
          {
            AutopilotDevicePreparationOrchestratorFunction = Windows::Management::Setup::ProvisioningSessionAssociationWithFunctionT<std::function<long (Windows::Management::Setup::IAgentProvisioningProgressReport *)>>::GetAutopilotDevicePreparationOrchestratorFunction(
                                                               (char *)this + 496,
                                                               v66);
            v61 = a4;
            v42 = *(_QWORD *)(AutopilotDevicePreparationOrchestratorFunction + 56);
            if ( !v42 )
              std::_Xbad_function_call();
            v43 = (*(__int64 (__fastcall **)(__int64, struct Windows::Management::Setup::IAgentProvisioningProgressReport **))(*(_QWORD *)v42 + 16LL))(
                    v42,
                    &v61);
            v67[0] = v43;
            std::_Func_class<bool,std::wstring const &>::_Tidy(v66);
            if ( v43 >= 0 )
            {
              Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1BC,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioning"
                              "sessionmanager.cpp",
                (const char *)(unsigned int)v43,
                v44);
              Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
              return (unsigned int)v43;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B8,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionmanager.cpp",
            (const char *)(unsigned int)v38,
            v44);
          Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
          return v39;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionmanager.cpp",
          (const char *)(unsigned int)IsSame,
          v44);
        Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
        return v35;
      }
    }
    else
    {
      v67[0] = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionmanager.cpp",
        (const char *)0x80070057LL,
        v44);
      Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
      return 2147942487LL;
    }
  }
  else
  {
    v67[0] = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionmanager.cpp",
      (const char *)0x80070057LL,
      v44);
    Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)v67);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800fd7c0  mov     r11, rsp
0x1800fd7c3  push    rbx
0x1800fd7c4  push    rsi
0x1800fd7c5  push    rdi
0x1800fd7c6  push    r12
0x1800fd7c8  push    r13
0x1800fd7ca  push    r14
0x1800fd7cc  push    r15
0x1800fd7ce  sub     rsp, 1E0h
0x1800fd7d5  mov     rax, cs:__security_cookie
0x1800fd7dc  xor     rax, rsp
0x1800fd7df  mov     [rsp+218h+var_48], rax
0x1800fd7e7  mov     r12, r9
0x1800fd7ea  mov     r14, r8
0x1800fd7ed  mov     [rsp+218h+var_150], r8
0x1800fd7f5  mov     r15, rdx
0x1800fd7f8  mov     [rsp+218h+var_170], rdx
0x1800fd800  mov     r13, rcx
0x1800fd803  lea     rdx, aNotifymachinep; "NotifyMachineProvisioningUpdate"
0x1800fd80a  lea     rcx, [r11-68h]
0x1800fd80e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fd813  nop
0x1800fd814  lea     rbx, [r13+530h]
0x1800fd81b  lea     r9, [rsp+218h+var_68]
0x1800fd823  mov     r8, r14
0x1800fd826  mov     rdx, rbx
0x1800fd829  lea     rcx, [rsp+218h+var_E8]; this
0x1800fd831  call    ??0ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@PEAUIProvisioningSessionLogger@123@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger(Windows::Management::Setup::IProvisioningSessionLogger *,_GUID const &,std::wstring const &)
0x1800fd836  nop
0x1800fd837  lea     rcx, [rsp+218h+var_68]
0x1800fd83f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800fd844  xor     esi, esi
0x1800fd846  test    r15, r15
0x1800fd849  jnz     short loc_1800FD888
0x1800fd84b  mov     ebx, 80070057h
0x1800fd850  mov     [rsp+218h+var_E8], ebx
0x1800fd857  mov     rcx, [rsp+218h]; this
0x1800fd85f  mov     r9d, ebx; char *
0x1800fd862  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fd869  mov     edx, 148h; void *
0x1800fd86e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fd873  nop
0x1800fd874  lea     rcx, [rsp+218h+var_E8]; this
0x1800fd87c  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1800fd881  mov     eax, ebx
0x1800fd883  jmp     loc_1800FE010
0x1800fd888  test    r12, r12
0x1800fd88b  jnz     short loc_1800FD8CA
0x1800fd88d  mov     ebx, 80070057h
0x1800fd892  mov     [rsp+218h+var_E8], ebx
0x1800fd899  mov     rcx, [rsp+218h]; this
0x1800fd8a1  mov     r9d, ebx; char *
0x1800fd8a4  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800fd8ab  mov     edx, 149h; void *
0x1800fd8b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fd8b5  nop
0x1800fd8b6  lea     rcx, [rsp+218h+var_E8]; this
0x1800fd8be  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1800fd8c3  mov     eax, ebx
0x1800fd8c5  jmp     loc_1800FE010
0x1800fd8ca  mov     rax, [rbx]
0x1800fd8cd  mov     r8, r12
0x1800fd8d0  mov     rdx, r14
0x1800fd8d3  mov     rcx, rbx
0x1800fd8d6  mov     rax, [rax+38h]
0x1800fd8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd8df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800fd8e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800fd8eb  test    al, al
0x1800fd8ed  jz      loc_1800FDE60
0x1800fd8f3  mov     [rsp+218h+var_1D0], esi
0x1800fd8f7  mov     rax, [r12]
0x1800fd8fb  lea     rdx, [rsp+218h+var_1D0]
0x1800fd900  mov     rcx, r12
0x1800fd903  mov     rax, [rax+30h]
0x1800fd907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd90c  test    eax, eax
0x1800fd90e  js      loc_1800FDE60
0x1800fd914  mov     eax, [rsp+218h+var_1D0]
0x1800fd918  add     eax, 0FFFFFFFDh
0x1800fd91b  cmp     eax, 3
0x1800fd91e  ja      loc_1800FDE60
0x1800fd924  xorps   xmm0, xmm0
0x1800fd927  movdqu  [rsp+218h+var_168], xmm0
0x1800fd930  mov     [rsp+218h+var_158], rsi
0x1800fd938  mov     [rsp+218h+var_180], rsi
0x1800fd940  mov     rax, [r12]
0x1800fd944  mov     rbx, [rax+80h]
0x1800fd94b  lea     rcx, [rsp+218h+var_180]
0x1800fd953  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fd958  lea     rdx, [rsp+218h+var_180]
0x1800fd960  mov     rcx, r12
0x1800fd963  mov     rax, rbx
0x1800fd966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd96b  test    eax, eax
0x1800fd96d  js      loc_1800FDD2F
0x1800fd973  mov     rcx, [rsp+218h+var_180]
0x1800fd97b  test    rcx, rcx
0x1800fd97e  jz      loc_1800FDD2F
0x1800fd984  mov     [rsp+218h+var_1B8], esi
0x1800fd988  mov     rax, [rcx]
0x1800fd98b  lea     rdx, [rsp+218h+var_1B8]
0x1800fd990  mov     rax, [rax+38h]
0x1800fd994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd999  mov     r14d, esi
0x1800fd99c  cmp     r14d, [rsp+218h+var_1B8]
0x1800fd9a1  jnb     loc_1800FDD1F
0x1800fd9a7  mov     [rsp+218h+var_178], rsi
0x1800fd9af  mov     rdi, [rsp+218h+var_180]
0x1800fd9b7  mov     rax, [rdi]
0x1800fd9ba  mov     rbx, [rax+30h]
0x1800fd9be  lea     rcx, [rsp+218h+var_178]
0x1800fd9c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fd9cb  lea     r8, [rsp+218h+var_178]
0x1800fd9d3  mov     edx, r14d
0x1800fd9d6  mov     rcx, rdi
0x1800fd9d9  mov     rax, rbx
0x1800fd9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd9e1  test    eax, eax
0x1800fd9e3  js      loc_1800FDD0A
0x1800fd9e9  mov     rbx, [rsp+218h+var_178]
0x1800fd9f1  test    rbx, rbx
0x1800fd9f4  jz      loc_1800FDD0A
0x1800fd9fa  mov     [rsp+218h+var_188], rsi
0x1800fda02  mov     rax, [rbx]
0x1800fda05  mov     rdi, [rax+48h]
0x1800fda09  lea     rcx, [rsp+218h+var_188]
0x1800fda11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fda16  lea     rdx, [rsp+218h+var_188]
0x1800fda1e  mov     rcx, rbx
0x1800fda21  mov     rax, rdi
0x1800fda24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fda29  test    eax, eax
0x1800fda2b  js      loc_1800FDCFC
0x1800fda31  mov     rcx, [rsp+218h+var_188]
0x1800fda39  test    rcx, rcx
0x1800fda3c  jz      loc_1800FDCFC
0x1800fda42  mov     [rsp+218h+var_1B4], esi
0x1800fda46  mov     rax, [rcx]
0x1800fda49  lea     rdx, [rsp+218h+var_1B4]
0x1800fda4e  mov     rax, [rax+38h]
0x1800fda52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fda57  cmp     esi, [rsp+218h+var_1B4]
0x1800fda5b  jnb     loc_1800FDCFA
0x1800fda61  xor     r15d, r15d
0x1800fda64  mov     [rsp+218h+var_1D8], r15
0x1800fda69  mov     rdi, [rsp+218h+var_188]
0x1800fda71  mov     rax, [rdi]
0x1800fda74  mov     rbx, [rax+30h]
0x1800fda78  lea     rcx, [rsp+218h+var_1D8]
0x1800fda7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fda82  lea     r8, [rsp+218h+var_1D8]
0x1800fda87  mov     edx, esi
0x1800fda89  mov     rcx, rdi
0x1800fda8c  mov     rax, rbx
0x1800fda8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fda94  test    eax, eax
0x1800fda96  js      loc_1800FDCE9
0x1800fda9c  mov     rbx, [rsp+218h+var_1D8]
0x1800fdaa1  test    rbx, rbx
0x1800fdaa4  jz      loc_1800FDCE9
0x1800fdaaa  mov     [rsp+218h+string], r15
0x1800fdab2  mov     rax, [rbx]
0x1800fdab5  mov     rdi, [rax+30h]
0x1800fdab9  xor     ecx, ecx; string
0x1800fdabb  call    cs:__imp_WindowsDeleteString
0x1800fdac1  mov     [rsp+218h+string], r15
0x1800fdac9  lea     rdx, [rsp+218h+string]
0x1800fdad1  mov     rcx, rbx
0x1800fdad4  mov     rax, rdi
0x1800fdad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdadc  lea     rdx, aWindowsautopil_18; "WindowsAutopilot.Telemetry.EarlyBoot.DP"...
0x1800fdae3  lea     rcx, [rsp+218h+var_128]
0x1800fdaeb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fdaf0  nop
0x1800fdaf1  xor     edx, edx; length
0x1800fdaf3  mov     rcx, [rsp+218h+string]; string
0x1800fdafb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fdb01  mov     rdx, rax
0x1800fdb04  lea     rcx, [rsp+218h+var_128]
0x1800fdb0c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800fdb11  mov     [rsp+218h+var_1B0], r15d
0x1800fdb16  mov     rcx, [rsp+218h+var_1D8]
0x1800fdb1b  mov     rax, [rcx]
0x1800fdb1e  lea     rdx, [rsp+218h+var_1B0]
0x1800fdb23  mov     rax, [rax+0A8h]
0x1800fdb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdb2f  cmp     [rsp+218h+var_1B0], 2
0x1800fdb34  setz    r15b
0x1800fdb38  xor     ebx, ebx
0x1800fdb3a  mov     [rsp+218h+var_1AC], ebx
0x1800fdb3e  mov     rcx, [rsp+218h+var_1D8]
0x1800fdb43  mov     rax, [rcx]
0x1800fdb46  lea     rdx, [rsp+218h+var_1AC]
0x1800fdb4b  mov     rax, [rax+68h]
0x1800fdb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdb54  mov     [rsp+218h+var_1C0], rbx
0x1800fdb59  mov     [rsp+218h+var_198], rbx
0x1800fdb61  mov     [rsp+218h+var_1A0], rbx
0x1800fdb66  mov     rdi, [rsp+218h+var_1D8]
0x1800fdb6b  mov     rax, [rdi]
0x1800fdb6e  mov     rbx, [rax+48h]
0x1800fdb72  lea     rcx, [rsp+218h+var_198]
0x1800fdb7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdb7f  lea     rdx, [rsp+218h+var_198]
0x1800fdb87  mov     rcx, rdi
0x1800fdb8a  mov     rax, rbx
0x1800fdb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdb92  xor     ebx, ebx
0x1800fdb94  test    eax, eax
0x1800fdb96  js      loc_1800FDC40
0x1800fdb9c  cmp     [rsp+218h+var_198], rbx
0x1800fdba4  jz      loc_1800FDC40
0x1800fdbaa  mov     rdi, [rsp+218h+var_1D8]
0x1800fdbaf  mov     rax, [rdi]
0x1800fdbb2  mov     rbx, [rax+58h]
0x1800fdbb6  lea     rcx, [rsp+218h+var_1A0]
0x1800fdbbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdbc0  lea     rdx, [rsp+218h+var_1A0]
0x1800fdbc5  mov     rcx, rdi
0x1800fdbc8  mov     rax, rbx
0x1800fdbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdbd0  xor     ebx, ebx
0x1800fdbd2  test    eax, eax
0x1800fdbd4  js      short loc_1800FDC40
0x1800fdbd6  cmp     [rsp+218h+var_1A0], rbx
0x1800fdbdb  jz      short loc_1800FDC40
0x1800fdbdd  mov     [rsp+218h+var_1C8], rbx
0x1800fdbe2  mov     [rsp+218h+var_1C0], rbx
0x1800fdbe7  mov     rcx, [rsp+218h+var_198]
0x1800fdbef  mov     rax, [rcx]
0x1800fdbf2  lea     rdx, [rsp+218h+var_1C8]
0x1800fdbf7  mov     rax, [rax+30h]
0x1800fdbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdc00  mov     rcx, [rsp+218h+var_1A0]
0x1800fdc05  mov     rax, [rcx]
0x1800fdc08  lea     rdx, [rsp+218h+var_1C0]
0x1800fdc0d  mov     rax, [rax+30h]
0x1800fdc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdc16  mov     rcx, [rsp+218h+var_1C0]
0x1800fdc1b  sub     rcx, [rsp+218h+var_1C8]
0x1800fdc20  mov     rax, 346DC5D63886594Bh
0x1800fdc2a  imul    rcx
0x1800fdc2d  sar     rdx, 0Bh
0x1800fdc31  mov     rax, rdx
0x1800fdc34  shr     rax, 3Fh
0x1800fdc38  add     rdx, rax
0x1800fdc3b  mov     [rsp+218h+var_1C0], rdx
0x1800fdc40  mov     [rsp+218h+var_1A8], ebx
0x1800fdc44  mov     eax, [rsp+218h+var_1AC]
0x1800fdc48  mov     [rsp+218h+var_1A4], eax
0x1800fdc4c  mov     dword ptr [rsp+218h+var_1C8], r15d
0x1800fdc51  mov     rdx, qword ptr [rsp+218h+var_168+8]
0x1800fdc59  lea     rax, [rsp+218h+var_1A8]
0x1800fdc5e  lea     r9, [rsp+218h+var_1C8]
0x1800fdc63  lea     r8, [rsp+218h+var_128]
0x1800fdc6b  mov     [rsp+218h+var_1E8], rax
0x1800fdc70  lea     rax, [rsp+218h+var_1A4]
0x1800fdc75  mov     [rsp+218h+var_1F0], rax
0x1800fdc7a  lea     rax, [rsp+218h+var_1C0]
0x1800fdc7f  mov     [rsp+218h+var_1F8], rax
0x1800fdc84  cmp     rdx, [rsp+218h+var_158]
0x1800fdc8c  jz      short loc_1800FDC9E
0x1800fdc8e  call    ??$construct@VFwtPhase@Core@Autopilot@ModernDeployment@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEA_JHH@?$_Default_allocator_traits@V?$allocator@VFwtPhase@Core@Autopilot@ModernDeployment@@@std@@@std@@SAXAEAV?$allocator@VFwtPhase@Core@Autopilot@ModernDeployment@@@1@QEAVFwtPhase@Core@Autopilot@ModernDeployment@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAHAEA_J33@Z; std::_Default_allocator_traits<std::allocator<ModernDeployment::Autopilot::Core::FwtPhase>>::construct<ModernDeployment::Autopilot::Core::FwtPhase,std::wstring &,int,__int64 &,int,int>(std::allocator<ModernDeployment::Autopilot::Core::FwtPhase> &,ModernDeployment::Autopilot::Core::FwtPhase * const,std::wstring &,int &&,__int64 &,int &&,int &&)
0x1800fdc93  add     qword ptr [rsp+218h+var_168+8], 50h ; 'P'
0x1800fdc9c  jmp     short loc_1800FDCAC
0x1800fdc9e  lea     rcx, [rsp+218h+var_168]
0x1800fdca6  call    ??$_Emplace_reallocate@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEA_JHH@?$vector@VFwtPhase@Core@Autopilot@ModernDeployment@@V?$allocator@VFwtPhase@Core@Autopilot@ModernDeployment@@@std@@@std@@AEAAPEAVFwtPhase@Core@Autopilot@ModernDeployment@@QEAV2345@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAHAEA_J22@Z; std::vector<ModernDeployment::Autopilot::Core::FwtPhase>::_Emplace_reallocate<std::wstring &,int,__int64 &,int,int>(ModernDeployment::Autopilot::Core::FwtPhase * const,std::wstring &,int &&,__int64 &,int &&,int &&)
0x1800fdcab  nop
0x1800fdcac  lea     rcx, [rsp+218h+var_1A0]
0x1800fdcb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdcb6  nop
0x1800fdcb7  lea     rcx, [rsp+218h+var_198]
0x1800fdcbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdcc4  nop
0x1800fdcc5  lea     rcx, [rsp+218h+var_128]
0x1800fdccd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800fdcd2  nop
0x1800fdcd3  mov     rcx, [rsp+218h+string]; string
0x1800fdcdb  call    cs:__imp_WindowsDeleteString
0x1800fdce1  mov     [rsp+218h+string], rbx
0x1800fdce9  lea     rcx, [rsp+218h+var_1D8]
0x1800fdcee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdcf3  inc     esi
0x1800fdcf5  jmp     loc_1800FDA57
0x1800fdcfa  xor     esi, esi
0x1800fdcfc  lea     rcx, [rsp+218h+var_188]
0x1800fdd04  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdd09  nop
0x1800fdd0a  lea     rcx, [rsp+218h+var_178]
0x1800fdd12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fdd17  inc     r14d
0x1800fdd1a  jmp     loc_1800FD99C
0x1800fdd1f  mov     r14, [rsp+218h+var_150]
0x1800fdd27  mov     r15, [rsp+218h+var_170]
0x1800fdd2f  cmp     [rsp+218h+var_1D0], 3
0x1800fdd34  setz    sil
0x1800fdd38  xor     edi, edi
0x1800fdd3a  mov     rax, qword ptr [rsp+218h+var_168]
0x1800fdd42  mov     rcx, qword ptr [rsp+218h+var_168+8]
  ... truncated ...
```
