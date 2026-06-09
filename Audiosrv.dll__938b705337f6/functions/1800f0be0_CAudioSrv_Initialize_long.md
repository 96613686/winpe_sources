# CAudioSrv::Initialize(long)

- ea: `0x1800f0be0`
- end: `0x1800f10a1`
- name: `?Initialize@CAudioSrv@@UEAAJJ@Z`
- size: `1217`
- prototype: `__int64 __fastcall(CAudioSrv *__hidden this, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001d90`
- `0x18000accc`
- `0x1800128bc`
- `0x18001b3d0`
- `0x180072450`
- `0x180073310`
- `0x1800a7220`
- `0x1800b7508`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800e5ab0`
- `0x1800ee290`
- `0x1800ee4b0`
- `0x1800ee548`
- `0x1800f0be0`
- `0x1800f2cf0`
- `0x1800f2d70`
- `0x180113a00`
- `0x18012e68c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f0ffe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f0ffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f1012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f1012`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f0fb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f0fb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f1043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f1043`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0c6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0cac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0cea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0d28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0c6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0cac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0cea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f0d28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0fc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0fc9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f0e87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f0e87`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f0f71`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f0f71`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x1800f0dbb`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x1800f0dbb`

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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
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
        &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids,
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
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
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
        }
        g_hCanAcceptMMCClientEvent = CreateEventExW(
                                       &EventAttributes,
                                       L"Global\\AudioSrv_CanAcceptMMCClient",
                                       1u,
                                       0x100002u);
        LocalFree(EventAttributes.lpSecurityDescriptor);
      }
      if ( v15 < 0 )
        AudSrvTraceLoggingErrorHelper("CAudioSrv::Initialize", 0x276u, v15);
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
      (unsigned int)&unk_1801A3144,
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
0x1800f0be0  mov     [rsp-8+arg_10], rbx
0x1800f0be5  mov     [rsp-8+arg_18], rsi
0x1800f0bea  push    rbp
0x1800f0beb  push    rdi
0x1800f0bec  push    r12
0x1800f0bee  push    r13
0x1800f0bf0  push    r15
0x1800f0bf2  lea     rbp, [rsp-37h]
0x1800f0bf7  sub     rsp, 0D0h
0x1800f0bfe  mov     rax, cs:__security_cookie
0x1800f0c05  xor     rax, rsp
0x1800f0c08  mov     [rbp+57h+var_30], rax
0x1800f0c0c  mov     edi, edx
0x1800f0c0e  mov     rsi, rcx
0x1800f0c11  xor     edx, edx; Val
0x1800f0c13  lea     r8d, [rdx+4Ch]; Size
0x1800f0c17  lea     rcx, [rbp+57h+spc]; void *
0x1800f0c1b  call    memset_0
0x1800f0c20  mov     [rbp+57h+var_B0], 0
0x1800f0c27  mov     r15d, 4
0x1800f0c2d  mov     [rbp+57h+var_AC], r15d
0x1800f0c31  lea     rax, [rbp+57h+var_AC]
0x1800f0c35  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f0c3a  lea     rax, [rbp+57h+var_B0]
0x1800f0c3e  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f0c43  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f0c4c  lea     r13d, [r15+14h]
0x1800f0c50  mov     r9d, r13d; dwFlags
0x1800f0c53  lea     r8, aPerformstrictc; "PerformStrictConnectorMatchOnMatchForma"...
0x1800f0c5a  lea     rbx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800f0c61  mov     rdx, rbx; lpSubKey
0x1800f0c64  mov     r12, 0FFFFFFFF80000002h
0x1800f0c6b  mov     rcx, r12; hkey
0x1800f0c6e  call    cs:__imp_RegGetValueW
0x1800f0c74  test    eax, eax
0x1800f0c76  jnz     short loc_1800F0C81
0x1800f0c78  mov     eax, [rbp+57h+var_B0]
0x1800f0c7b  mov     cs:?g_PerformStrictConnectorMatchOnMatchFormat@@3HA, eax; int g_PerformStrictConnectorMatchOnMatchFormat
0x1800f0c81  lea     rax, [rbp+57h+var_AC]
0x1800f0c85  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f0c8a  lea     rax, [rbp+57h+var_B0]
0x1800f0c8e  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f0c93  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f0c9c  mov     r9d, r13d; dwFlags
0x1800f0c9f  lea     r8, aDisablespatial_0; "DisableSpatialOnLowLatency"
0x1800f0ca6  mov     rdx, rbx; lpSubKey
0x1800f0ca9  mov     rcx, r12; hkey
0x1800f0cac  call    cs:__imp_RegGetValueW
0x1800f0cb2  test    eax, eax
0x1800f0cb4  jnz     short loc_1800F0CBF
0x1800f0cb6  mov     eax, [rbp+57h+var_B0]
0x1800f0cb9  mov     cs:?g_DisableSpatialOnLowLatency@@3HA, eax; int g_DisableSpatialOnLowLatency
0x1800f0cbf  lea     rax, [rbp+57h+var_AC]
0x1800f0cc3  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f0cc8  lea     rax, [rbp+57h+var_B0]
0x1800f0ccc  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f0cd1  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f0cda  mov     r9d, r13d; dwFlags
0x1800f0cdd  lea     r8, aUsesoftwareloo; "UseSoftwareLoopbackOnMatchFormat"
0x1800f0ce4  mov     rdx, rbx; lpSubKey
0x1800f0ce7  mov     rcx, r12; hkey
0x1800f0cea  call    cs:__imp_RegGetValueW
0x1800f0cf0  test    eax, eax
0x1800f0cf2  jnz     short loc_1800F0CFD
0x1800f0cf4  mov     eax, [rbp+57h+var_B0]
0x1800f0cf7  mov     cs:?g_UseSoftwareLoopbackOnMatchFormat@@3HA, eax; int g_UseSoftwareLoopbackOnMatchFormat
0x1800f0cfd  lea     rax, [rbp+57h+var_AC]
0x1800f0d01  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800f0d06  lea     rax, [rbp+57h+var_B0]
0x1800f0d0a  mov     [rsp+0F0h+pvData], rax; pvData
0x1800f0d0f  mov     [rsp+0F0h+pdwType], 0; pdwType
0x1800f0d18  mov     r9d, r13d; dwFlags
0x1800f0d1b  lea     r8, aTimeoutreverta; "TimeoutRevertAudioPumpFormatAndPeriodIn"...
0x1800f0d22  mov     rdx, rbx; lpSubKey
0x1800f0d25  mov     rcx, r12; hkey
0x1800f0d28  call    cs:__imp_RegGetValueW
0x1800f0d2e  test    eax, eax
0x1800f0d30  jnz     short loc_1800F0D3B
0x1800f0d32  mov     eax, [rbp+57h+var_B0]
0x1800f0d35  mov     cs:?g_TimeoutRevertAudioPumpFormatAndPeriodInMs@@3HA, eax; int g_TimeoutRevertAudioPumpFormatAndPeriodInMs
0x1800f0d3b  lea     r12, WPP_GLOBAL_Control
0x1800f0d42  lea     r13, WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids
0x1800f0d49  test    edi, edi
0x1800f0d4b  jnz     short loc_1800F0DB7
0x1800f0d4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f0d54  lea     ecx, [rdi+68h]; unsigned __int64
0x1800f0d57  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f0d5c  mov     rbx, rax
0x1800f0d5f  mov     [rbp+57h+ppv], rax
0x1800f0d63  test    rax, rax
0x1800f0d66  jz      short loc_1800F0D80
0x1800f0d68  mov     rcx, rax
0x1800f0d6b  call    ??0?$CAtlExeModuleT@VCAudioServiceModule@@@ATL@@QEAA@XZ; ATL::CAtlExeModuleT<CAudioServiceModule>::CAtlExeModuleT<CAudioServiceModule>(void)
0x1800f0d70  lea     rax, ??_7CAudioServiceModule@@6B@; const CAudioServiceModule::`vftable'
0x1800f0d77  mov     [rbx], rax
0x1800f0d7a  mov     [rbx+60h], dil
0x1800f0d7e  jmp     short loc_1800F0D82
0x1800f0d80  xor     ebx, ebx
0x1800f0d82  mov     [rsi+58h], rbx
0x1800f0d86  test    rbx, rbx
0x1800f0d89  jnz     short loc_1800F0DB7
0x1800f0d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0d92  cmp     rcx, r12
0x1800f0d95  jz      short loc_1800F0DB2
0x1800f0d97  test    [rcx+1Ch], r15b
0x1800f0d9b  jz      short loc_1800F0DB2
0x1800f0d9d  cmp     [rcx+19h], r15b
0x1800f0da1  jb      short loc_1800F0DB2
0x1800f0da3  lea     edx, [rbx+0Eh]
0x1800f0da6  mov     r8, r13
0x1800f0da9  mov     rcx, [rcx+10h]
0x1800f0dad  call    WPP_SF_
0x1800f0db2  mov     edi, 8007000Eh
0x1800f0db7  lea     rcx, [rbp+57h+spc]; lpspc
0x1800f0dbb  call    cs:__imp_GetPwrCapabilities
0x1800f0dc1  test    edi, edi
0x1800f0dc3  jnz     loc_1800F0E5E
0x1800f0dc9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f0dd0  mov     ecx, 0A0h; unsigned __int64
0x1800f0dd5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f0dda  mov     [rbp+57h+ppv], rax
0x1800f0dde  test    rax, rax
0x1800f0de1  jz      short loc_1800F0E2A
0x1800f0de3  mov     rcx, rsi
0x1800f0de6  lea     r8, [rsi+50h]
0x1800f0dea  neg     rcx
0x1800f0ded  sbb     rdx, rdx
0x1800f0df0  and     rdx, r8; struct IMonitorDGTermination *
0x1800f0df3  mov     rcx, rax; this
0x1800f0df6  call    ??0CAudioDGProcess@@QEAA@PEAUIMonitorDGTermination@@@Z; CAudioDGProcess::CAudioDGProcess(IMonitorDGTermination *)
0x1800f0dfb  mov     cs:?g_ADGProcess@@3PEAVCAudioDGProcess@@EA, rax; CAudioDGProcess * g_ADGProcess
0x1800f0e02  test    rax, rax
0x1800f0e05  jz      short loc_1800F0E35
0x1800f0e07  lea     rcx, [rbp+57h+ppv]
0x1800f0e0b  call    ??$make_unique@VCPowerReferenceManager@@$$V$0A@@std@@YA?AV?$unique_ptr@VCPowerReferenceManager@@U?$default_delete@VCPowerReferenceManager@@@std@@@0@XZ; std::make_unique<CPowerReferenceManager,,0>(void)
0x1800f0e10  mov     rdx, [rax]
0x1800f0e13  mov     qword ptr [rax], 0
0x1800f0e1a  call    ?reset@?$unique_ptr@VCPowerReferenceManager@@U?$default_delete@VCPowerReferenceManager@@@std@@@std@@QEAAXPEAVCPowerReferenceManager@@@Z; std::unique_ptr<CPowerReferenceManager>::reset(CPowerReferenceManager *)
0x1800f0e1f  lea     rcx, [rbp+57h+ppv]
0x1800f0e23  call    ??1?$unique_ptr@VCPowerReferenceManager@@U?$default_delete@VCPowerReferenceManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPowerReferenceManager>::~unique_ptr<CPowerReferenceManager>(void)
0x1800f0e28  jmp     short loc_1800F0E5E
0x1800f0e2a  mov     cs:?g_ADGProcess@@3PEAVCAudioDGProcess@@EA, 0; CAudioDGProcess * g_ADGProcess
0x1800f0e35  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0e3c  cmp     rcx, r12
0x1800f0e3f  jz      short loc_1800F0E5E
0x1800f0e41  test    [rcx+1Ch], r15b
0x1800f0e45  jz      short loc_1800F0E5E
0x1800f0e47  cmp     [rcx+19h], r15b
0x1800f0e4b  jb      short loc_1800F0E5E
0x1800f0e4d  mov     edx, 0Fh
0x1800f0e52  mov     r8, r13
0x1800f0e55  mov     rcx, [rcx+10h]
0x1800f0e59  call    WPP_SF_
0x1800f0e5e  mov     [rbp+57h+ppv], 0
0x1800f0e66  lea     rax, [rbp+57h+ppv]
0x1800f0e6a  mov     [rsp+0F0h+pdwType], rax; ppv
0x1800f0e6f  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800f0e76  mov     edi, 1
0x1800f0e7b  mov     r8d, edi; dwClsContext
0x1800f0e7e  xor     edx, edx; pUnkOuter
0x1800f0e80  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800f0e87  call    cs:__imp_CoCreateInstance
0x1800f0e8d  mov     ebx, eax
0x1800f0e8f  test    eax, eax
0x1800f0e91  js      short loc_1800F0EAD
0x1800f0e93  mov     rcx, [rbp+57h+ppv]
0x1800f0e97  mov     rax, [rcx]
0x1800f0e9a  mov     r8d, edi
0x1800f0e9d  lea     edx, [rdi+4]
0x1800f0ea0  mov     rax, [rax+18h]
0x1800f0ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0ea9  mov     ebx, eax
0x1800f0eab  jmp     short loc_1800F0EDA
0x1800f0ead  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0eb4  cmp     rcx, r12
0x1800f0eb7  jz      short loc_1800F0EDA
0x1800f0eb9  test    [rcx+1Ch], r15b
0x1800f0ebd  jz      short loc_1800F0EDA
0x1800f0ebf  cmp     [rcx+19h], r15b
0x1800f0ec3  jb      short loc_1800F0EDA
0x1800f0ec5  mov     edx, 10h
0x1800f0eca  mov     r9d, eax
0x1800f0ecd  mov     r8, r13
0x1800f0ed0  mov     rcx, [rcx+10h]
0x1800f0ed4  call    WPP_SF_d
0x1800f0ed9  nop
0x1800f0eda  lea     rcx, [rbp+57h+ppv]
0x1800f0ede  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800f0ee3  test    ebx, ebx
0x1800f0ee5  jnz     loc_1800F101F
0x1800f0eeb  mov     rcx, rsi; this
0x1800f0eee  call    ?VAD_AudiosrvServiceStart@CAudioSrv@@AEAAJXZ; CAudioSrv::VAD_AudiosrvServiceStart(void)
0x1800f0ef3  mov     ebx, eax
0x1800f0ef5  test    eax, eax
0x1800f0ef7  jnz     loc_1800F101F
0x1800f0efd  call    ?MME_ServiceStart@@YAJXZ; MME_ServiceStart(void)
0x1800f0f02  mov     ebx, eax
0x1800f0f04  test    eax, eax
0x1800f0f06  jns     short loc_1800F0F20
0x1800f0f08  test    cs:Microsoft_Windows_AudioEnableBits, r15b
0x1800f0f0f  jz      short loc_1800F0F20
0x1800f0f11  mov     r9d, eax
0x1800f0f14  lea     r8, aMme; "MME"
0x1800f0f1b  call    McTemplateU0zq_EtwEventWriteTransfer
0x1800f0f20  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x1800f0f28  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], 0
0x1800f0f30  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], 0
0x1800f0f38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0f3f  cmp     rcx, r12
0x1800f0f42  jz      short loc_1800F0F61
0x1800f0f44  test    [rcx+1Ch], r15b
0x1800f0f48  jz      short loc_1800F0F61
0x1800f0f4a  cmp     [rcx+19h], r15b
0x1800f0f4e  jb      short loc_1800F0F61
0x1800f0f50  mov     edx, 11h
0x1800f0f55  mov     r8, r13
0x1800f0f58  mov     rcx, [rcx+10h]
0x1800f0f5c  call    WPP_SF_
0x1800f0f61  xor     r9d, r9d; SecurityDescriptorSize
0x1800f0f64  lea     r8, [rbp+57h+EventAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x1800f0f68  mov     edx, edi; StringSDRevision
0x1800f0f6a  lea     rcx, aDA0x00100003S1; "D:(A;;0x00100003;;;S-1-5-80-2676549577-"...
0x1800f0f71  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f0f77  test    eax, eax
0x1800f0f79  jz      short loc_1800F0FCF
0x1800f0f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0f82  cmp     rcx, r12
0x1800f0f85  jz      short loc_1800F0FA4
0x1800f0f87  test    [rcx+1Ch], r15b
0x1800f0f8b  jz      short loc_1800F0FA4
0x1800f0f8d  cmp     [rcx+19h], r15b
0x1800f0f91  jb      short loc_1800F0FA4
0x1800f0f93  mov     edx, 12h
0x1800f0f98  mov     r8, r13
0x1800f0f9b  mov     rcx, [rcx+10h]
0x1800f0f9f  call    WPP_SF_
0x1800f0fa4  mov     r9d, 100002h; dwDesiredAccess
0x1800f0faa  mov     r8d, edi; dwFlags
0x1800f0fad  lea     rdx, aGlobalAudiosrv; "Global\\AudioSrv_CanAcceptMMCClient"
0x1800f0fb4  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800f0fb8  call    cs:__imp_CreateEventExW
0x1800f0fbe  mov     cs:?g_hCanAcceptMMCClientEvent@@3PEAXEA, rax; void * g_hCanAcceptMMCClientEvent
0x1800f0fc5  mov     rcx, [rbp+57h+EventAttributes.lpSecurityDescriptor]; hMem
0x1800f0fc9  call    cs:__imp_LocalFree
0x1800f0fcf  test    ebx, ebx
0x1800f0fd1  jns     short loc_1800F0FE7
0x1800f0fd3  mov     r8d, ebx; int
0x1800f0fd6  mov     edx, 276h; unsigned int
0x1800f0fdb  lea     rcx, aCaudiosrvIniti; "CAudioSrv::Initialize"
0x1800f0fe2  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x1800f0fe7  lea     rbx, ?UpdateRenderingEndpointsSpatialSettingsAsync@CPolicyConfig@@SAXXZ; CPolicyConfig::UpdateRenderingEndpointsSpatialSettingsAsync(void)
0x1800f0fee  cmp     cs:?m_pCallback@MyAtmosCheckCallback@@0P6AXXZEA, rbx; void (*MyAtmosCheckCallback::m_pCallback)(void)
0x1800f0ff5  jz      short loc_1800F1018
0x1800f0ff7  lea     rcx, ?s_atmosLock@CSpatialAudioTech@@1VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x1800f0ffe  call    cs:__imp_EnterCriticalSection
0x1800f1004  mov     cs:?m_pCallback@MyAtmosCheckCallback@@0P6AXXZEA, rbx; void (*MyAtmosCheckCallback::m_pCallback)(void)
0x1800f100b  lea     rcx, ?s_atmosLock@CSpatialAudioTech@@1VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x1800f1012  call    cs:__imp_LeaveCriticalSection
0x1800f1018  call    ?KsNotifications_ServiceStart@@YAJXZ; KsNotifications_ServiceStart(void)
0x1800f101d  mov     ebx, eax
0x1800f101f  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f1024  mov     rdi, [rax+8]
0x1800f1028  mov     eax, [rdi]
0x1800f102a  cmp     eax, r15d
0x1800f102d  jbe     short loc_1800F106D
0x1800f102f  mov     edx, 80h
0x1800f1034  mov     rcx, rdi
0x1800f1037  call    _tlgKeywordOn
0x1800f103c  test    al, al
0x1800f103e  jz      short loc_1800F106D
0x1800f1040  mov     [rbp+57h+var_A0], ebx
0x1800f1043  call    cs:__imp_GetCurrentProcessId
0x1800f1049  mov     dword ptr [rbp+57h+ppv], eax
0x1800f104c  lea     rax, [rbp+57h+var_A0]
0x1800f1050  mov     [rsp+0F0h+pvData], rax
0x1800f1055  lea     rax, [rbp+57h+ppv]
0x1800f1059  mov     [rsp+0F0h+pdwType], rax
0x1800f105e  lea     rdx, unk_1801A3144
0x1800f1065  mov     rcx, rdi
0x1800f1068  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f106d  mov     cs:?g_StreamVolumeChangeAsTelemetryCounter@@3HA, 0Ah; int g_StreamVolumeChangeAsTelemetryCounter
0x1800f1077  mov     eax, ebx
0x1800f1079  mov     rcx, [rbp+57h+var_30]
0x1800f107d  xor     rcx, rsp; StackCookie
0x1800f1080  call    __security_check_cookie
0x1800f1085  lea     r11, [rsp+0F0h+var_20]
0x1800f108d  mov     rbx, [r11+40h]
0x1800f1091  mov     rsi, [r11+48h]
0x1800f1095  mov     rsp, r11
0x1800f1098  pop     r15
0x1800f109a  pop     r13
0x1800f109c  pop     r12
0x1800f109e  pop     rdi
0x1800f109f  pop     rbp
0x1800f10a0  retn
```
