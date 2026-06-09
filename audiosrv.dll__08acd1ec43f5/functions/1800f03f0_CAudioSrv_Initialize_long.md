# CAudioSrv::Initialize(long)

- ea: `0x1800f03f0`
- end: `0x1800f08b1`
- name: `?Initialize@CAudioSrv@@UEAAJJ@Z`
- size: `1217`
- prototype: `__int64 __fastcall(CAudioSrv *__hidden this, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001d90`
- `0x18000ae1c`
- `0x180012a0c`
- `0x18001b520`
- `0x180071f50`
- `0x180072e10`
- `0x1800b59b8`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800ce774`
- `0x1800e5330`
- `0x1800edaec`
- `0x1800edd0c`
- `0x1800edda4`
- `0x1800f03f0`
- `0x1800f222c`
- `0x1800f2f80`
- `0x1800f3000`
- `0x180113c80`
- `0x18012e8dc`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f080e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f080e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f0822`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f0822`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f07c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f07c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f0853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f0853`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f047e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f04bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f04fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0538`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f047e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f04bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f04fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0538`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f07d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f07d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f0697`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f0697`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f0781`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f0781`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x1800f05cb`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x1800f05cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSrv::Initialize(CAudioSrv *this, int a2)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rbx
  void *v6; // rax
  __int64 *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  HRESULT v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // ebx
  _DWORD *v16; // rdi
  int v17; // r8d
  int v18; // r9d
  int pvData; // [rsp+40h] [rbp-59h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-55h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-49h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+58h] [rbp-41h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+70h] [rbp-29h] BYREF

  memset_0(&spc, 0, sizeof(spc));
  pvData = 0;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"PerformStrictConnectorMatchOnMatchFormat",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    g_PerformStrictConnectorMatchOnMatchFormat = pvData;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"DisableSpatialOnLowLatency",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    g_DisableSpatialOnLowLatency = pvData;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"UseSoftwareLoopbackOnMatchFormat",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    g_UseSoftwareLoopbackOnMatchFormat = pvData;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"TimeoutRevertAudioPumpFormatAndPeriodInMs",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    g_TimeoutRevertAudioPumpFormatAndPeriodInMs = pvData;
  if ( !a2 )
  {
    v4 = operator new[](0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    ppv = v4;
    if ( v4 )
    {
      ATL::CAtlExeModuleT<CAudioServiceModule>::CAtlExeModuleT<CAudioServiceModule>(v4);
      *(_QWORD *)v5 = &CAudioServiceModule::`vftable';
      v5[96] = 0;
    }
    else
    {
      v5 = 0;
    }
    *((_QWORD *)this + 11) = v5;
    if ( !v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
      }
      a2 = -2147024882;
    }
  }
  GetPwrCapabilities(&spc);
  if ( !a2 )
  {
    v6 = operator new[](0xA0u, (const struct std::nothrow_t *)&std::nothrow);
    ppv = v6;
    if ( v6 )
    {
      g_ADGProcess = (LPCRITICAL_SECTION)CAudioDGProcess::CAudioDGProcess(
                                           (CAudioDGProcess *)v6,
                                           (struct IMonitorDGTermination *)(((unsigned __int64)this + 80)
                                                                          & -(__int64)(this != 0)));
      if ( g_ADGProcess )
      {
        v7 = (__int64 *)std::make_unique<CPowerReferenceManager,,0>(&ppv);
        v8 = *v7;
        *v7 = 0;
        std::unique_ptr<CPowerReferenceManager>::reset(v9, v8);
        std::unique_ptr<CPowerReferenceManager>::~unique_ptr<CPowerReferenceManager>(&ppv);
        goto LABEL_28;
      }
    }
    else
    {
      g_ADGProcess = 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
    }
  }
LABEL_28:
  ppv = 0;
  v10 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids,
        (unsigned int)v10);
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppv);
  if ( !v11 )
  {
    v11 = CAudioSrv::VAD_AudiosrvServiceStart(this);
    if ( !v11 )
    {
      v12 = MME_ServiceStart();
      v15 = v12;
      if ( v12 < 0 && (Microsoft_Windows_AudioEnableBits & 4) != 0 )
        McTemplateU0zq_EtwEventWriteTransfer(v14, v13, L"MME", (unsigned int)v12);
      *(_QWORD *)&EventAttributes.nLength = 24;
      EventAttributes.lpSecurityDescriptor = 0;
      *(_QWORD *)&EventAttributes.bInheritHandle = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
      }
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;;0x00100003;;;S-1-5-80-2676549577-1911656217-2625096541-4178041876-1366760775)(A;;0x00100000;;;SY)",
             1u,
             &EventAttributes.lpSecurityDescriptor,
             0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
        }
        g_hCanAcceptMMCClientEvent = CreateEventExW(
                                       &EventAttributes,
                                       L"Global\\AudioSrv_CanAcceptMMCClient",
                                       1u,
                                       0x100002u);
        LocalFree(EventAttributes.lpSecurityDescriptor);
      }
      if ( v15 < 0 )
        AudSrvTraceLoggingErrorHelper("CAudioSrv::Initialize", 0x279u, v15);
      if ( (char *)MyAtmosCheckCallback::m_pCallback != (char *)CPolicyConfig::UpdateRenderingEndpointsSpatialSettingsAsync )
      {
        EnterCriticalSection(&CSpatialAudioTech::s_atmosLock);
        MyAtmosCheckCallback::m_pCallback = (void (*)(void))CPolicyConfig::UpdateRenderingEndpointsSpatialSettingsAsync;
        LeaveCriticalSection(&CSpatialAudioTech::s_atmosLock);
      }
      v11 = KsNotifications_ServiceStart();
    }
  }
  v16 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  if ( *v16 > 4u && (unsigned __int8)tlgKeywordOn(v16, 128) )
  {
    v23 = v11;
    LODWORD(ppv) = GetCurrentProcessId();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v16,
      (unsigned int)&byte_1801A4387,
      v17,
      v18,
      (__int64)&ppv,
      (__int64)&v23);
  }
  g_StreamVolumeChangeAsTelemetryCounter = 10;
  return v11;
}

```

## disassembly

```asm
0x1800f03f0  mov     [rsp-8+arg_10], rbx
0x1800f03f5  mov     [rsp-8+arg_18], rsi
0x1800f03fa  push    rbp
0x1800f03fb  push    rdi
0x1800f03fc  push    r12
0x1800f03fe  push    r13
0x1800f0400  push    r15
0x1800f0402  lea     rbp, [rsp-37h]
0x1800f0407  sub     rsp, 0D0h
0x1800f040e  mov     rax, cs:__security_cookie
0x1800f0415  xor     rax, rsp
0x1800f0418  mov     [rbp+57h+var_30], rax
0x1800f041c  mov     edi, edx
0x1800f041e  mov     rsi, rcx
0x1800f0421  xor     edx, edx; Val
0x1800f0423  lea     r8d, [rdx+4Ch]; Size
0x1800f0427  lea     rcx, [rbp+57h+spc]; void *
0x1800f042b  call    memset_0
0x1800f0430  mov     [rbp+57h+var_B0], 0
0x1800f0437  mov     r15d, 4
0x1800f043d  mov     [rbp+57h+var_AC], r15d
0x1800f0441  lea     rax, [rbp+57h+var_AC]
0x1800f0445  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f044a  lea     rax, [rbp+57h+var_B0]
0x1800f044e  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f0453  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f045c  lea     r13d, [r15+14h]
0x1800f0460  mov     r9d, r13d; dwFlags
0x1800f0463  lea     r8, aPerformstrictc; "PerformStrictConnectorMatchOnMatchForma"...
0x1800f046a  lea     rbx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800f0471  mov     rdx, rbx; lpSubKey
0x1800f0474  mov     r12, 0FFFFFFFF80000002h
0x1800f047b  mov     rcx, r12; hkey
0x1800f047e  call    cs:__imp_RegGetValueW
0x1800f0484  test    eax, eax
0x1800f0486  jnz     short loc_1800F0491
0x1800f0488  mov     eax, [rbp+57h+var_B0]
0x1800f048b  mov     cs:?g_PerformStrictConnectorMatchOnMatchFormat@@3HA, eax; int g_PerformStrictConnectorMatchOnMatchFormat
0x1800f0491  lea     rax, [rbp+57h+var_AC]
0x1800f0495  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f049a  lea     rax, [rbp+57h+var_B0]
0x1800f049e  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f04a3  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f04ac  mov     r9d, r13d; dwFlags
0x1800f04af  lea     r8, aDisablespatial_0; "DisableSpatialOnLowLatency"
0x1800f04b6  mov     rdx, rbx; lpSubKey
0x1800f04b9  mov     rcx, r12; hkey
0x1800f04bc  call    cs:__imp_RegGetValueW
0x1800f04c2  test    eax, eax
0x1800f04c4  jnz     short loc_1800F04CF
0x1800f04c6  mov     eax, [rbp+57h+var_B0]
0x1800f04c9  mov     cs:?g_DisableSpatialOnLowLatency@@3HA, eax; int g_DisableSpatialOnLowLatency
0x1800f04cf  lea     rax, [rbp+57h+var_AC]
0x1800f04d3  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f04d8  lea     rax, [rbp+57h+var_B0]
0x1800f04dc  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f04e1  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f04ea  mov     r9d, r13d; dwFlags
0x1800f04ed  lea     r8, aUsesoftwareloo; "UseSoftwareLoopbackOnMatchFormat"
0x1800f04f4  mov     rdx, rbx; lpSubKey
0x1800f04f7  mov     rcx, r12; hkey
0x1800f04fa  call    cs:__imp_RegGetValueW
0x1800f0500  test    eax, eax
0x1800f0502  jnz     short loc_1800F050D
0x1800f0504  mov     eax, [rbp+57h+var_B0]
0x1800f0507  mov     cs:?g_UseSoftwareLoopbackOnMatchFormat@@3HA, eax; int g_UseSoftwareLoopbackOnMatchFormat
0x1800f050d  lea     rax, [rbp+57h+var_AC]
0x1800f0511  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f0516  lea     rax, [rbp+57h+var_B0]
0x1800f051a  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f051f  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f0528  mov     r9d, r13d; dwFlags
0x1800f052b  lea     r8, aTimeoutreverta; "TimeoutRevertAudioPumpFormatAndPeriodIn"...
0x1800f0532  mov     rdx, rbx; lpSubKey
0x1800f0535  mov     rcx, r12; hkey
0x1800f0538  call    cs:__imp_RegGetValueW
0x1800f053e  test    eax, eax
0x1800f0540  jnz     short loc_1800F054B
0x1800f0542  mov     eax, [rbp+57h+var_B0]
0x1800f0545  mov     cs:?g_TimeoutRevertAudioPumpFormatAndPeriodInMs@@3HA, eax; int g_TimeoutRevertAudioPumpFormatAndPeriodInMs
0x1800f054b  lea     r12, WPP_GLOBAL_Control
0x1800f0552  lea     r13, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids
0x1800f0559  test    edi, edi
0x1800f055b  jnz     short loc_1800F05C7
0x1800f055d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f0564  lea     ecx, [rdi+68h]; unsigned __int64
0x1800f0567  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f056c  mov     rbx, rax
0x1800f056f  mov     [rbp+57h+ppv], rax
0x1800f0573  test    rax, rax
0x1800f0576  jz      short loc_1800F0590
0x1800f0578  mov     rcx, rax
0x1800f057b  call    ??0?$CAtlExeModuleT@VCAudioServiceModule@@@ATL@@QEAA@XZ; ATL::CAtlExeModuleT<CAudioServiceModule>::CAtlExeModuleT<CAudioServiceModule>(void)
0x1800f0580  lea     rax, ??_7CAudioServiceModule@@6B@; const CAudioServiceModule::`vftable'
0x1800f0587  mov     [rbx], rax
0x1800f058a  mov     [rbx+60h], dil
0x1800f058e  jmp     short loc_1800F0592
0x1800f0590  xor     ebx, ebx
0x1800f0592  mov     [rsi+58h], rbx
0x1800f0596  test    rbx, rbx
0x1800f0599  jnz     short loc_1800F05C7
0x1800f059b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f05a2  cmp     rcx, r12
0x1800f05a5  jz      short loc_1800F05C2
0x1800f05a7  test    [rcx+1Ch], r15b
0x1800f05ab  jz      short loc_1800F05C2
0x1800f05ad  cmp     [rcx+19h], r15b
0x1800f05b1  jb      short loc_1800F05C2
0x1800f05b3  lea     edx, [rbx+0Eh]
0x1800f05b6  mov     r8, r13
0x1800f05b9  mov     rcx, [rcx+10h]
0x1800f05bd  call    WPP_SF_
0x1800f05c2  mov     edi, 8007000Eh
0x1800f05c7  lea     rcx, [rbp+57h+spc]; lpspc
0x1800f05cb  call    cs:__imp_GetPwrCapabilities
0x1800f05d1  test    edi, edi
0x1800f05d3  jnz     loc_1800F066E
0x1800f05d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f05e0  mov     ecx, 0A0h; unsigned __int64
0x1800f05e5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f05ea  mov     [rbp+57h+ppv], rax
0x1800f05ee  test    rax, rax
0x1800f05f1  jz      short loc_1800F063A
0x1800f05f3  mov     rcx, rsi
0x1800f05f6  lea     r8, [rsi+50h]
0x1800f05fa  neg     rcx
0x1800f05fd  sbb     rdx, rdx
0x1800f0600  and     rdx, r8; struct IMonitorDGTermination *
0x1800f0603  mov     rcx, rax; this
0x1800f0606  call    ??0CAudioDGProcess@@QEAA@PEAUIMonitorDGTermination@@@Z; CAudioDGProcess::CAudioDGProcess(IMonitorDGTermination *)
0x1800f060b  mov     cs:?g_ADGProcess@@3PEAVCAudioDGProcess@@EA, rax; CAudioDGProcess * g_ADGProcess
0x1800f0612  test    rax, rax
0x1800f0615  jz      short loc_1800F0645
0x1800f0617  lea     rcx, [rbp+57h+ppv]
0x1800f061b  call    ??$make_unique@VCPowerReferenceManager@@$$V$0A@@std@@YA?AV?$unique_ptr@VCPowerReferenceManager@@U?$default_delete@VCPowerReferenceManager@@@std@@@0@XZ; std::make_unique<CPowerReferenceManager,,0>(void)
0x1800f0620  mov     rdx, [rax]
0x1800f0623  mov     qword ptr [rax], 0
0x1800f062a  call    ?reset@?$unique_ptr@VCPowerReferenceManager@@U?$default_delete@VCPowerReferenceManager@@@std@@@std@@QEAAXPEAVCPowerReferenceManager@@@Z; std::unique_ptr<CPowerReferenceManager>::reset(CPowerReferenceManager *)
0x1800f062f  lea     rcx, [rbp+57h+ppv]
0x1800f0633  call    ??1?$unique_ptr@VCPowerReferenceManager@@U?$default_delete@VCPowerReferenceManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPowerReferenceManager>::~unique_ptr<CPowerReferenceManager>(void)
0x1800f0638  jmp     short loc_1800F066E
0x1800f063a  mov     cs:?g_ADGProcess@@3PEAVCAudioDGProcess@@EA, 0; CAudioDGProcess * g_ADGProcess
0x1800f0645  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f064c  cmp     rcx, r12
0x1800f064f  jz      short loc_1800F066E
0x1800f0651  test    [rcx+1Ch], r15b
0x1800f0655  jz      short loc_1800F066E
0x1800f0657  cmp     [rcx+19h], r15b
0x1800f065b  jb      short loc_1800F066E
0x1800f065d  mov     edx, 0Fh
0x1800f0662  mov     r8, r13
0x1800f0665  mov     rcx, [rcx+10h]
0x1800f0669  call    WPP_SF_
0x1800f066e  mov     [rbp+57h+ppv], 0
0x1800f0676  lea     rax, [rbp+57h+ppv]
0x1800f067a  mov     [rsp+0F0h+pdwType], rax; ppv
0x1800f067f  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800f0686  mov     edi, 1
0x1800f068b  mov     r8d, edi; dwClsContext
0x1800f068e  xor     edx, edx; pUnkOuter
0x1800f0690  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800f0697  call    cs:__imp_CoCreateInstance
0x1800f069d  mov     ebx, eax
0x1800f069f  test    eax, eax
0x1800f06a1  js      short loc_1800F06BD
0x1800f06a3  mov     rcx, [rbp+57h+ppv]
0x1800f06a7  mov     rax, [rcx]
0x1800f06aa  mov     r8d, edi
0x1800f06ad  lea     edx, [rdi+4]
0x1800f06b0  mov     rax, [rax+18h]
0x1800f06b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f06b9  mov     ebx, eax
0x1800f06bb  jmp     short loc_1800F06EA
0x1800f06bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f06c4  cmp     rcx, r12
0x1800f06c7  jz      short loc_1800F06EA
0x1800f06c9  test    [rcx+1Ch], r15b
0x1800f06cd  jz      short loc_1800F06EA
0x1800f06cf  cmp     [rcx+19h], r15b
0x1800f06d3  jb      short loc_1800F06EA
0x1800f06d5  mov     edx, 10h
0x1800f06da  mov     r9d, eax
0x1800f06dd  mov     r8, r13
0x1800f06e0  mov     rcx, [rcx+10h]
0x1800f06e4  call    WPP_SF_d
0x1800f06e9  nop
0x1800f06ea  lea     rcx, [rbp+57h+ppv]
0x1800f06ee  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800f06f3  test    ebx, ebx
0x1800f06f5  jnz     loc_1800F082F
0x1800f06fb  mov     rcx, rsi; this
0x1800f06fe  call    ?VAD_AudiosrvServiceStart@CAudioSrv@@AEAAJXZ; CAudioSrv::VAD_AudiosrvServiceStart(void)
0x1800f0703  mov     ebx, eax
0x1800f0705  test    eax, eax
0x1800f0707  jnz     loc_1800F082F
0x1800f070d  call    ?MME_ServiceStart@@YAJXZ; MME_ServiceStart(void)
0x1800f0712  mov     ebx, eax
0x1800f0714  test    eax, eax
0x1800f0716  jns     short loc_1800F0730
0x1800f0718  test    cs:Microsoft_Windows_AudioEnableBits, r15b
0x1800f071f  jz      short loc_1800F0730
0x1800f0721  mov     r9d, eax
0x1800f0724  lea     r8, aMme; "MME"
0x1800f072b  call    McTemplateU0zq_EtwEventWriteTransfer
0x1800f0730  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x1800f0738  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], 0
0x1800f0740  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], 0
0x1800f0748  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f074f  cmp     rcx, r12
0x1800f0752  jz      short loc_1800F0771
0x1800f0754  test    [rcx+1Ch], r15b
0x1800f0758  jz      short loc_1800F0771
0x1800f075a  cmp     [rcx+19h], r15b
0x1800f075e  jb      short loc_1800F0771
0x1800f0760  mov     edx, 11h
0x1800f0765  mov     r8, r13
0x1800f0768  mov     rcx, [rcx+10h]
0x1800f076c  call    WPP_SF_
0x1800f0771  xor     r9d, r9d; SecurityDescriptorSize
0x1800f0774  lea     r8, [rbp+57h+EventAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x1800f0778  mov     edx, edi; StringSDRevision
0x1800f077a  lea     rcx, aDA0x00100003S1; "D:(A;;0x00100003;;;S-1-5-80-2676549577-"...
0x1800f0781  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f0787  test    eax, eax
0x1800f0789  jz      short loc_1800F07DF
0x1800f078b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0792  cmp     rcx, r12
0x1800f0795  jz      short loc_1800F07B4
0x1800f0797  test    [rcx+1Ch], r15b
0x1800f079b  jz      short loc_1800F07B4
0x1800f079d  cmp     [rcx+19h], r15b
0x1800f07a1  jb      short loc_1800F07B4
0x1800f07a3  mov     edx, 12h
0x1800f07a8  mov     r8, r13
0x1800f07ab  mov     rcx, [rcx+10h]
0x1800f07af  call    WPP_SF_
0x1800f07b4  mov     r9d, 100002h; dwDesiredAccess
0x1800f07ba  mov     r8d, edi; dwFlags
0x1800f07bd  lea     rdx, aGlobalAudiosrv; "Global\\AudioSrv_CanAcceptMMCClient"
0x1800f07c4  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800f07c8  call    cs:__imp_CreateEventExW
0x1800f07ce  mov     cs:?g_hCanAcceptMMCClientEvent@@3PEAXEA, rax; void * g_hCanAcceptMMCClientEvent
0x1800f07d5  mov     rcx, [rbp+57h+EventAttributes.lpSecurityDescriptor]; hMem
0x1800f07d9  call    cs:__imp_LocalFree
0x1800f07df  test    ebx, ebx
0x1800f07e1  jns     short loc_1800F07F7
0x1800f07e3  mov     r8d, ebx; int
0x1800f07e6  mov     edx, 279h; unsigned int
0x1800f07eb  lea     rcx, aCaudiosrvIniti; "CAudioSrv::Initialize"
0x1800f07f2  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x1800f07f7  lea     rbx, ?UpdateRenderingEndpointsSpatialSettingsAsync@CPolicyConfig@@SAXXZ; CPolicyConfig::UpdateRenderingEndpointsSpatialSettingsAsync(void)
0x1800f07fe  cmp     cs:?m_pCallback@MyAtmosCheckCallback@@0P6AXXZEA, rbx; void (*MyAtmosCheckCallback::m_pCallback)(void)
0x1800f0805  jz      short loc_1800F0828
0x1800f0807  lea     rcx, ?s_atmosLock@CSpatialAudioTech@@1VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x1800f080e  call    cs:__imp_EnterCriticalSection
0x1800f0814  mov     cs:?m_pCallback@MyAtmosCheckCallback@@0P6AXXZEA, rbx; void (*MyAtmosCheckCallback::m_pCallback)(void)
0x1800f081b  lea     rcx, ?s_atmosLock@CSpatialAudioTech@@1VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x1800f0822  call    cs:__imp_LeaveCriticalSection
0x1800f0828  call    ?KsNotifications_ServiceStart@@YAJXZ; KsNotifications_ServiceStart(void)
0x1800f082d  mov     ebx, eax
0x1800f082f  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f0834  mov     rdi, [rax+8]
0x1800f0838  mov     eax, [rdi]
0x1800f083a  cmp     eax, r15d
0x1800f083d  jbe     short loc_1800F087D
0x1800f083f  mov     edx, 80h
0x1800f0844  mov     rcx, rdi
0x1800f0847  call    _tlgKeywordOn
0x1800f084c  test    al, al
0x1800f084e  jz      short loc_1800F087D
0x1800f0850  mov     [rbp+57h+var_A0], ebx
0x1800f0853  call    cs:__imp_GetCurrentProcessId
0x1800f0859  mov     dword ptr [rbp+57h+ppv], eax
0x1800f085c  lea     rax, [rbp+57h+var_A0]
0x1800f0860  mov     [rsp+0F0h+pvData], rax
0x1800f0865  lea     rax, [rbp+57h+ppv]
0x1800f0869  mov     [rsp+0F0h+pdwType], rax
0x1800f086e  lea     rdx, byte_1801A4387
0x1800f0875  mov     rcx, rdi
0x1800f0878  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f087d  mov     cs:?g_StreamVolumeChangeAsTelemetryCounter@@3HA, 0Ah; int g_StreamVolumeChangeAsTelemetryCounter
0x1800f0887  mov     eax, ebx
0x1800f0889  mov     rcx, [rbp+57h+var_30]
0x1800f088d  xor     rcx, rsp; StackCookie
0x1800f0890  call    __security_check_cookie
0x1800f0895  lea     r11, [rsp+0F0h+var_20]
0x1800f089d  mov     rbx, [r11+40h]
0x1800f08a1  mov     rsi, [r11+48h]
0x1800f08a5  mov     rsp, r11
0x1800f08a8  pop     r15
0x1800f08aa  pop     r13
0x1800f08ac  pop     r12
0x1800f08ae  pop     rdi
0x1800f08af  pop     rbp
0x1800f08b0  retn
```
