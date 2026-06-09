# Windows::Management::Setup::ProvisioningSessionManager::NotifyMachineProvisioningUpdate(Windows::Management::Setup::IMachineProvisioningProgressReporter *,_GUID const &,Windows::Management::Setup::IAgentProvisioningProgressReport *)

- ea: `0x1801008f0`
- end: `0x18010117c`
- name: `?NotifyMachineProvisioningUpdate@ProvisioningSessionManager@Setup@Management@Windows@@UEAAJPEAUIMachineProvisioningProgressReporter@234@AEBU_GUID@@PEAUIAgentProvisioningProgressReport@234@@Z`
- size: `2188`
- prototype: `__int64 __fastcall(Windows::Management::Setup::ProvisioningSessionManager *__hidden this, struct Windows::Management::Setup::IMachineProvisioningProgressReporter *, const struct _GUID *, struct Windows::Management::Setup::IAgentProvisioningProgressReport *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077d0c`
- `0x180077de0`
- `0x180077e54`
- `0x180080bac`
- `0x180084574`
- `0x18008ed78`
- `0x1800d2460`
- `0x1800dabf0`
- `0x1800e2668`
- `0x1800e32c4`
- `0x1800fe924`
- `0x1800fea90`
- `0x1801000a0`
- `0x1801008f0`
- `0x180103114`
- `0x1801031ec`
- `0x1801033d4`
- `0x180106e0c`
- `0x1801078e0`
- `0x18010795c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180100c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180100c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100beb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100beb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100e17`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801010db`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801010db`

## string_xrefs

- `0x180100f4b`: `WindowsAutopilot.Telemetry.EarlyBoot.DPP.AgentProvisioning`
- `0x180100992`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x1801009d4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x180100f68`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x180100fcf`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x180101027`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x180101093`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x180101120`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionmanager.cpp`
- `0x180100933`: `NotifyMachineProvisioningUpdate`

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
0x1801008f0  mov     r11, rsp
0x1801008f3  push    rbx
0x1801008f4  push    rsi
0x1801008f5  push    rdi
0x1801008f6  push    r12
0x1801008f8  push    r13
0x1801008fa  push    r14
0x1801008fc  push    r15
0x1801008fe  sub     rsp, 1E0h
0x180100905  mov     rax, cs:__security_cookie
0x18010090c  xor     rax, rsp
0x18010090f  mov     [rsp+218h+var_48], rax
0x180100917  mov     r12, r9
0x18010091a  mov     r14, r8
0x18010091d  mov     [rsp+218h+var_150], r8
0x180100925  mov     r15, rdx
0x180100928  mov     [rsp+218h+var_170], rdx
0x180100930  mov     r13, rcx
0x180100933  lea     rdx, aNotifymachinep; "NotifyMachineProvisioningUpdate"
0x18010093a  lea     rcx, [r11-68h]
0x18010093e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180100943  nop
0x180100944  lea     rbx, [r13+530h]
0x18010094b  lea     r9, [rsp+218h+var_68]
0x180100953  mov     r8, r14
0x180100956  mov     rdx, rbx
0x180100959  lea     rcx, [rsp+218h+var_E8]; this
0x180100961  call    ??0ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@PEAUIProvisioningSessionLogger@123@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger(Windows::Management::Setup::IProvisioningSessionLogger *,_GUID const &,std::wstring const &)
0x180100966  nop
0x180100967  lea     rcx, [rsp+218h+var_68]
0x18010096f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100974  xor     esi, esi
0x180100976  test    r15, r15
0x180100979  jnz     short loc_1801009B8
0x18010097b  mov     ebx, 80070057h
0x180100980  mov     [rsp+218h+var_E8], ebx
0x180100987  mov     rcx, [rsp+218h]; this
0x18010098f  mov     r9d, ebx; char *
0x180100992  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\moderndeployment\\au"...
0x180100999  mov     edx, 148h; void *
0x18010099e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801009a3  nop
0x1801009a4  lea     rcx, [rsp+218h+var_E8]; this
0x1801009ac  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1801009b1  mov     eax, ebx
0x1801009b3  jmp     loc_180101158
0x1801009b8  test    r12, r12
0x1801009bb  jnz     short loc_1801009FA
0x1801009bd  mov     ebx, 80070057h
0x1801009c2  mov     [rsp+218h+var_E8], ebx
0x1801009c9  mov     rcx, [rsp+218h]; this
0x1801009d1  mov     r9d, ebx; char *
0x1801009d4  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801009db  mov     edx, 149h; void *
0x1801009e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801009e5  nop
0x1801009e6  lea     rcx, [rsp+218h+var_E8]; this
0x1801009ee  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1801009f3  mov     eax, ebx
0x1801009f5  jmp     loc_180101158
0x1801009fa  mov     rax, [rbx]
0x1801009fd  mov     r8, r12
0x180100a00  mov     rdx, r14
0x180100a03  mov     rcx, rbx
0x180100a06  mov     rax, [rax+38h]
0x180100a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x180100a16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x180100a1b  test    al, al
0x180100a1d  jz      loc_180100FA2
0x180100a23  mov     [rsp+218h+var_1D0], esi
0x180100a27  mov     rax, [r12]
0x180100a2b  lea     rdx, [rsp+218h+var_1D0]
0x180100a30  mov     rcx, r12
0x180100a33  mov     rax, [rax+30h]
0x180100a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a3c  test    eax, eax
0x180100a3e  js      loc_180100FA2
0x180100a44  mov     eax, [rsp+218h+var_1D0]
0x180100a48  add     eax, 0FFFFFFFDh
0x180100a4b  cmp     eax, 3
0x180100a4e  ja      loc_180100FA2
0x180100a54  xorps   xmm0, xmm0
0x180100a57  movdqu  [rsp+218h+var_168], xmm0
0x180100a60  mov     [rsp+218h+var_158], rsi
0x180100a68  mov     [rsp+218h+var_180], rsi
0x180100a70  mov     rax, [r12]
0x180100a74  mov     rbx, [rax+80h]
0x180100a7b  lea     rcx, [rsp+218h+var_180]
0x180100a83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100a88  lea     rdx, [rsp+218h+var_180]
0x180100a90  mov     rcx, r12
0x180100a93  mov     rax, rbx
0x180100a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a9b  test    eax, eax
0x180100a9d  js      loc_180100E71
0x180100aa3  mov     rcx, [rsp+218h+var_180]
0x180100aab  test    rcx, rcx
0x180100aae  jz      loc_180100E71
0x180100ab4  mov     [rsp+218h+var_1B8], esi
0x180100ab8  mov     rax, [rcx]
0x180100abb  lea     rdx, [rsp+218h+var_1B8]
0x180100ac0  mov     rax, [rax+38h]
0x180100ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100ac9  mov     r14d, esi
0x180100acc  cmp     r14d, [rsp+218h+var_1B8]
0x180100ad1  jnb     loc_180100E61
0x180100ad7  mov     [rsp+218h+var_178], rsi
0x180100adf  mov     rdi, [rsp+218h+var_180]
0x180100ae7  mov     rax, [rdi]
0x180100aea  mov     rbx, [rax+30h]
0x180100aee  lea     rcx, [rsp+218h+var_178]
0x180100af6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100afb  lea     r8, [rsp+218h+var_178]
0x180100b03  mov     edx, r14d
0x180100b06  mov     rcx, rdi
0x180100b09  mov     rax, rbx
0x180100b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100b11  test    eax, eax
0x180100b13  js      loc_180100E4C
0x180100b19  mov     rbx, [rsp+218h+var_178]
0x180100b21  test    rbx, rbx
0x180100b24  jz      loc_180100E4C
0x180100b2a  mov     [rsp+218h+var_188], rsi
0x180100b32  mov     rax, [rbx]
0x180100b35  mov     rdi, [rax+48h]
0x180100b39  lea     rcx, [rsp+218h+var_188]
0x180100b41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100b46  lea     rdx, [rsp+218h+var_188]
0x180100b4e  mov     rcx, rbx
0x180100b51  mov     rax, rdi
0x180100b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100b59  test    eax, eax
0x180100b5b  js      loc_180100E3E
0x180100b61  mov     rcx, [rsp+218h+var_188]
0x180100b69  test    rcx, rcx
0x180100b6c  jz      loc_180100E3E
0x180100b72  mov     [rsp+218h+var_1B4], esi
0x180100b76  mov     rax, [rcx]
0x180100b79  lea     rdx, [rsp+218h+var_1B4]
0x180100b7e  mov     rax, [rax+38h]
0x180100b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100b87  cmp     esi, [rsp+218h+var_1B4]
0x180100b8b  jnb     loc_180100E3C
0x180100b91  xor     r15d, r15d
0x180100b94  mov     [rsp+218h+var_1D8], r15
0x180100b99  mov     rdi, [rsp+218h+var_188]
0x180100ba1  mov     rax, [rdi]
0x180100ba4  mov     rbx, [rax+30h]
0x180100ba8  lea     rcx, [rsp+218h+var_1D8]
0x180100bad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100bb2  lea     r8, [rsp+218h+var_1D8]
0x180100bb7  mov     edx, esi
0x180100bb9  mov     rcx, rdi
0x180100bbc  mov     rax, rbx
0x180100bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100bc4  test    eax, eax
0x180100bc6  js      loc_180100E2B
0x180100bcc  mov     rbx, [rsp+218h+var_1D8]
0x180100bd1  test    rbx, rbx
0x180100bd4  jz      loc_180100E2B
0x180100bda  mov     [rsp+218h+string], r15
0x180100be2  mov     rax, [rbx]
0x180100be5  mov     rdi, [rax+30h]
0x180100be9  xor     ecx, ecx; string
0x180100beb  call    cs:__imp_WindowsDeleteString
0x180100bf2  nop     dword ptr [rax+rax+00h]
0x180100bf7  mov     [rsp+218h+string], r15
0x180100bff  lea     rdx, [rsp+218h+string]
0x180100c07  mov     rcx, rbx
0x180100c0a  mov     rax, rdi
0x180100c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100c12  lea     rdx, aWindowsautopil_18; "WindowsAutopilot.Telemetry.EarlyBoot.DP"...
0x180100c19  lea     rcx, [rsp+218h+var_128]
0x180100c21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180100c26  nop
0x180100c27  xor     edx, edx; length
0x180100c29  mov     rcx, [rsp+218h+string]; string
0x180100c31  call    cs:__imp_WindowsGetStringRawBuffer
0x180100c38  nop     dword ptr [rax+rax+00h]
0x180100c3d  mov     rdx, rax
0x180100c40  lea     rcx, [rsp+218h+var_128]
0x180100c48  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180100c4d  mov     [rsp+218h+var_1B0], r15d
0x180100c52  mov     rcx, [rsp+218h+var_1D8]
0x180100c57  mov     rax, [rcx]
0x180100c5a  lea     rdx, [rsp+218h+var_1B0]
0x180100c5f  mov     rax, [rax+0A8h]
0x180100c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100c6b  cmp     [rsp+218h+var_1B0], 2
0x180100c70  setz    r15b
0x180100c74  xor     ebx, ebx
0x180100c76  mov     [rsp+218h+var_1AC], ebx
0x180100c7a  mov     rcx, [rsp+218h+var_1D8]
0x180100c7f  mov     rax, [rcx]
0x180100c82  lea     rdx, [rsp+218h+var_1AC]
0x180100c87  mov     rax, [rax+68h]
0x180100c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100c90  mov     [rsp+218h+var_1C0], rbx
0x180100c95  mov     [rsp+218h+var_198], rbx
0x180100c9d  mov     [rsp+218h+var_1A0], rbx
0x180100ca2  mov     rdi, [rsp+218h+var_1D8]
0x180100ca7  mov     rax, [rdi]
0x180100caa  mov     rbx, [rax+48h]
0x180100cae  lea     rcx, [rsp+218h+var_198]
0x180100cb6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100cbb  lea     rdx, [rsp+218h+var_198]
0x180100cc3  mov     rcx, rdi
0x180100cc6  mov     rax, rbx
0x180100cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100cce  xor     ebx, ebx
0x180100cd0  test    eax, eax
0x180100cd2  js      loc_180100D7C
0x180100cd8  cmp     [rsp+218h+var_198], rbx
0x180100ce0  jz      loc_180100D7C
0x180100ce6  mov     rdi, [rsp+218h+var_1D8]
0x180100ceb  mov     rax, [rdi]
0x180100cee  mov     rbx, [rax+58h]
0x180100cf2  lea     rcx, [rsp+218h+var_1A0]
0x180100cf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100cfc  lea     rdx, [rsp+218h+var_1A0]
0x180100d01  mov     rcx, rdi
0x180100d04  mov     rax, rbx
0x180100d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100d0c  xor     ebx, ebx
0x180100d0e  test    eax, eax
0x180100d10  js      short loc_180100D7C
0x180100d12  cmp     [rsp+218h+var_1A0], rbx
0x180100d17  jz      short loc_180100D7C
0x180100d19  mov     [rsp+218h+var_1C8], rbx
0x180100d1e  mov     [rsp+218h+var_1C0], rbx
0x180100d23  mov     rcx, [rsp+218h+var_198]
0x180100d2b  mov     rax, [rcx]
0x180100d2e  lea     rdx, [rsp+218h+var_1C8]
0x180100d33  mov     rax, [rax+30h]
0x180100d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100d3c  mov     rcx, [rsp+218h+var_1A0]
0x180100d41  mov     rax, [rcx]
0x180100d44  lea     rdx, [rsp+218h+var_1C0]
0x180100d49  mov     rax, [rax+30h]
0x180100d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100d52  mov     rcx, [rsp+218h+var_1C0]
0x180100d57  sub     rcx, [rsp+218h+var_1C8]
0x180100d5c  mov     rax, 346DC5D63886594Bh
0x180100d66  imul    rcx
0x180100d69  sar     rdx, 0Bh
0x180100d6d  mov     rax, rdx
0x180100d70  shr     rax, 3Fh
0x180100d74  add     rdx, rax
0x180100d77  mov     [rsp+218h+var_1C0], rdx
0x180100d7c  mov     [rsp+218h+var_1A8], ebx
0x180100d80  mov     eax, [rsp+218h+var_1AC]
0x180100d84  mov     [rsp+218h+var_1A4], eax
0x180100d88  mov     dword ptr [rsp+218h+var_1C8], r15d
0x180100d8d  mov     rdx, qword ptr [rsp+218h+var_168+8]
0x180100d95  lea     rax, [rsp+218h+var_1A8]
0x180100d9a  lea     r9, [rsp+218h+var_1C8]
0x180100d9f  lea     r8, [rsp+218h+var_128]
0x180100da7  mov     [rsp+218h+var_1E8], rax
0x180100dac  lea     rax, [rsp+218h+var_1A4]
0x180100db1  mov     [rsp+218h+var_1F0], rax
0x180100db6  lea     rax, [rsp+218h+var_1C0]
0x180100dbb  mov     [rsp+218h+var_1F8], rax
0x180100dc0  cmp     rdx, [rsp+218h+var_158]
0x180100dc8  jz      short loc_180100DDA
0x180100dca  call    ??$construct@VFwtPhase@Core@Autopilot@ModernDeployment@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEA_JHH@?$_Default_allocator_traits@V?$allocator@VFwtPhase@Core@Autopilot@ModernDeployment@@@std@@@std@@SAXAEAV?$allocator@VFwtPhase@Core@Autopilot@ModernDeployment@@@1@QEAVFwtPhase@Core@Autopilot@ModernDeployment@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAHAEA_J33@Z; std::_Default_allocator_traits<std::allocator<ModernDeployment::Autopilot::Core::FwtPhase>>::construct<ModernDeployment::Autopilot::Core::FwtPhase,std::wstring &,int,__int64 &,int,int>(std::allocator<ModernDeployment::Autopilot::Core::FwtPhase> &,ModernDeployment::Autopilot::Core::FwtPhase * const,std::wstring &,int &&,__int64 &,int &&,int &&)
0x180100dcf  add     qword ptr [rsp+218h+var_168+8], 50h ; 'P'
0x180100dd8  jmp     short loc_180100DE8
0x180100dda  lea     rcx, [rsp+218h+var_168]
0x180100de2  call    ??$_Emplace_reallocate@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEA_JHH@?$vector@VFwtPhase@Core@Autopilot@ModernDeployment@@V?$allocator@VFwtPhase@Core@Autopilot@ModernDeployment@@@std@@@std@@AEAAPEAVFwtPhase@Core@Autopilot@ModernDeployment@@QEAV2345@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAHAEA_J22@Z; std::vector<ModernDeployment::Autopilot::Core::FwtPhase>::_Emplace_reallocate<std::wstring &,int,__int64 &,int,int>(ModernDeployment::Autopilot::Core::FwtPhase * const,std::wstring &,int &&,__int64 &,int &&,int &&)
0x180100de7  nop
0x180100de8  lea     rcx, [rsp+218h+var_1A0]
0x180100ded  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100df2  nop
0x180100df3  lea     rcx, [rsp+218h+var_198]
0x180100dfb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100e00  nop
0x180100e01  lea     rcx, [rsp+218h+var_128]
0x180100e09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100e0e  nop
0x180100e0f  mov     rcx, [rsp+218h+string]; string
0x180100e17  call    cs:__imp_WindowsDeleteString
0x180100e1e  nop     dword ptr [rax+rax+00h]
0x180100e23  mov     [rsp+218h+string], rbx
0x180100e2b  lea     rcx, [rsp+218h+var_1D8]
0x180100e30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100e35  inc     esi
0x180100e37  jmp     loc_180100B87
0x180100e3c  xor     esi, esi
0x180100e3e  lea     rcx, [rsp+218h+var_188]
0x180100e46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100e4b  nop
0x180100e4c  lea     rcx, [rsp+218h+var_178]
0x180100e54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100e59  inc     r14d
0x180100e5c  jmp     loc_180100ACC
0x180100e61  mov     r14, [rsp+218h+var_150]
0x180100e69  mov     r15, [rsp+218h+var_170]
0x180100e71  cmp     [rsp+218h+var_1D0], 3
0x180100e76  setz    sil
  ... truncated ...
```
