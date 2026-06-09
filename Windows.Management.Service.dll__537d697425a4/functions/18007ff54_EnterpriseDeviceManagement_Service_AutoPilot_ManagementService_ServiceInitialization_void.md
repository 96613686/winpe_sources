# EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(void)

- ea: `0x18007ff54`
- end: `0x180080118`
- name: `?ServiceInitialization@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ`
- size: `452`
- prototype: `int(EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180080120`

## callees

- `0x18000be20`
- `0x180067e34`
- `0x180067e54`
- `0x180077d0c`
- `0x18007d28c`
- `0x18007e87c`
- `0x18007ef6c`
- `0x18007f814`
- `0x18007ff54`
- `0x180080468`
- `0x1800808b4`
- `0x180080dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ffe1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ffe1`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007ff63`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007ff63`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180080103`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180080103`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180080024`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180080024`
- `dmenterprisediagnostics!SetupAutoLog` at `0x18007ffaf`
- `dmenterprisediagnostics!SetupAutoLog` at `0x18007ffaf`
- `dmenterprisediagnostics!StartAutoLog` at `0x18007ffc2`
- `dmenterprisediagnostics!StartAutoLog` at `0x18007ffc2`

## string_xrefs

- `0x18007ff81`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007fffe`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18008003e`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x1800800c4`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(
        EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *this)
{
  int v1; // eax
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v2; // rcx
  unsigned int v3; // r8d
  unsigned int LastError; // ebx
  EnterpriseDeviceManagement::Service::AutoPilot *v5; // rcx
  bool v6; // dl
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v7; // rcx
  const char *v8; // r9
  unsigned int EnrollmentServerShutdownDelay; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *v13; // rax
  int v14; // eax
  unsigned int v15; // r8d
  EnterpriseDeviceManagement::Service::AutoPilot *v16; // rcx
  int v18; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v20; // [rsp+38h] [rbp+10h] BYREF

  v1 = RoInitialize(1);
  LastError = v1;
  if ( v1 >= 0 )
  {
    EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(v2, 2u, v3);
    SetupAutoLog(L"Autopilot", 0, 1);
    StartAutoLog(L"Autopilot");
    LOBYTE(v5) = 1;
    EnterpriseDeviceManagement::Service::AutoPilot::PerformProcMonProfileIfAvailable(v5, v6);
    qword_1802A34E8 = CreateEventW(0, 1, 0, 0);
    if ( !qword_1802A34E8 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1A5,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
                    v8);
LABEL_18:
      RoUninitialize();
      return LastError;
    }
    EnrollmentServerShutdownDelay = EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::GetEnrollmentServerShutdownDelay(v7);
    v10 = CoRegisterServerShutdownDelay(qword_1802A34E8, EnrollmentServerShutdownDelay);
    LastError = v10;
    if ( v10 >= 0 )
    {
      v13 = (EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)operator new(
                                                                                         0x20u,
                                                                                         (const struct std::nothrow_t *)&std::nothrow);
      if ( v13 )
        v13 = (EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::ManagementServiceModule(v13);
      v20 = 0;
      wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(
        &qword_1802A34E0,
        v13);
      wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(
        &v20,
        0);
      if ( !qword_1802A34E0 )
      {
        LastError = -2147024882;
        v12 = 2147942414LL;
        v11 = 431;
        goto LABEL_8;
      }
      v14 = EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::RegisterContextObjects(qword_1802A34E0);
      LastError = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
          (const char *)(unsigned int)v14,
          v18);
        v12 = LastError;
        v11 = 433;
        goto LABEL_8;
      }
      EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(retaddr, 4u, v15);
      v10 = EnterpriseDeviceManagement::Service::AutoPilot::SetGlobalComSettings(v16);
      LastError = v10;
      if ( v10 >= 0 )
      {
        LastError = 0;
        goto LABEL_18;
      }
      v11 = 437;
    }
    else
    {
      v11 = 427;
    }
    v12 = (unsigned int)v10;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
      (const char *)v12,
      v18);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x197,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
    (const char *)(unsigned int)v1,
    v18);
  return LastError;
}

```

## disassembly

```asm
0x18007ff54  mov     [rsp+arg_0], rcx
0x18007ff59  push    rbx; int
0x18007ff5a  sub     rsp, 20h
0x18007ff5e  mov     ecx, 1
0x18007ff63  call    cs:__imp_RoInitialize
0x18007ff6a  nop     dword ptr [rax+rax+00h]
0x18007ff6f  mov     ebx, eax
0x18007ff71  mov     dword ptr [rsp+28h+arg_0], eax
0x18007ff75  test    eax, eax
0x18007ff77  jns     short loc_18007FF98
0x18007ff79  mov     rcx, [rsp+28h]; this
0x18007ff7e  mov     r9d, eax; char *
0x18007ff81  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007ff88  mov     edx, 197h; void *
0x18007ff8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ff92  nop
0x18007ff93  jmp     loc_18008010F
0x18007ff98  mov     edx, 2; unsigned int
0x18007ff9d  call    ?UpdateServiceStatus@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAXKK@Z; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(ulong,ulong)
0x18007ffa2  xor     edx, edx
0x18007ffa4  lea     r8d, [rdx+1]
0x18007ffa8  lea     rcx, aAutopilot; "Autopilot"
0x18007ffaf  call    cs:__imp_?SetupAutoLog@@YAJPEBG0H@Z; SetupAutoLog(ushort const *,ushort const *,int)
0x18007ffb6  nop     dword ptr [rax+rax+00h]
0x18007ffbb  lea     rcx, aAutopilot; "Autopilot"
0x18007ffc2  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x18007ffc9  nop     dword ptr [rax+rax+00h]
0x18007ffce  mov     cl, 1; this
0x18007ffd0  call    ?PerformProcMonProfileIfAvailable@AutoPilot@Service@EnterpriseDeviceManagement@@YAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::PerformProcMonProfileIfAvailable(bool)
0x18007ffd5  xor     r9d, r9d; lpName
0x18007ffd8  xor     r8d, r8d; bInitialState
0x18007ffdb  lea     edx, [r9+1]; bManualReset
0x18007ffdf  xor     ecx, ecx; lpEventAttributes
0x18007ffe1  call    cs:__imp_CreateEventW
0x18007ffe8  nop     dword ptr [rax+rax+00h]
0x18007ffed  mov     cs:qword_1802A34E8, rax
0x18007fff4  test    rax, rax
0x18007fff7  jnz     short loc_180080016
0x18007fff9  mov     rcx, [rsp+28h]; this
0x18007fffe  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x180080005  mov     edx, 1A5h; void *
0x18008000a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008000f  mov     ebx, eax
0x180080011  jmp     loc_180080103
0x180080016  call    ?GetEnrollmentServerShutdownDelay@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAKXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::GetEnrollmentServerShutdownDelay(void)
0x18008001b  mov     edx, eax
0x18008001d  mov     rcx, cs:qword_1802A34E8
0x180080024  call    cs:__imp_CoRegisterServerShutdownDelay
0x18008002b  nop     dword ptr [rax+rax+00h]
0x180080030  mov     ebx, eax
0x180080032  test    eax, eax
0x180080034  jns     short loc_180080054
0x180080036  mov     edx, 1ABh; void *
0x18008003b  mov     r9d, eax; char *
0x18008003e  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x180080045  mov     rcx, [rsp+28h]; this
0x18008004a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008004f  jmp     loc_180080103
0x180080054  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008005b  mov     ecx, 20h ; ' '; unsigned __int64
0x180080060  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180080065  test    rax, rax
0x180080068  jz      short loc_180080072
0x18008006a  mov     rcx, rax; this
0x18008006d  call    ??0ManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@QEAA@XZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::ManagementServiceModule(void)
0x180080072  mov     [rsp+28h+arg_8], 0
0x18008007b  mov     rdx, rax
0x18008007e  lea     rcx, qword_1802A34E0
0x180080085  call    ?reset@?$unique_ptr@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@U?$default_delete@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@wistd@@@wistd@@QEAAXPEAVManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)
0x18008008a  xor     edx, edx
0x18008008c  lea     rcx, [rsp+28h+arg_8]
0x180080091  call    ?reset@?$unique_ptr@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@U?$default_delete@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@wistd@@@wistd@@QEAAXPEAVManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)
0x180080096  mov     rcx, cs:qword_1802A34E0; this
0x18008009d  test    rcx, rcx
0x1800800a0  jnz     short loc_1800800B1
0x1800800a2  mov     ebx, 8007000Eh
0x1800800a7  mov     r9d, ebx
0x1800800aa  mov     edx, 1AFh
0x1800800af  jmp     short loc_18008003E
0x1800800b1  call    ?RegisterContextObjects@ManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::RegisterContextObjects(void)
0x1800800b6  mov     ebx, eax
0x1800800b8  mov     rcx, [rsp+28h]; this
0x1800800bd  test    eax, eax
0x1800800bf  jns     short loc_1800800E2
0x1800800c1  mov     r9d, eax; char *
0x1800800c4  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800800cb  mov     edx, 0F7h; void *
0x1800800d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800800d5  mov     r9d, ebx
0x1800800d8  mov     edx, 1B1h
0x1800800dd  jmp     loc_18008003E
0x1800800e2  mov     edx, 4; unsigned int
0x1800800e7  call    ?UpdateServiceStatus@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAXKK@Z; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(ulong,ulong)
0x1800800ec  call    ?SetGlobalComSettings@AutoPilot@Service@EnterpriseDeviceManagement@@YAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::SetGlobalComSettings(void)
0x1800800f1  mov     ebx, eax
0x1800800f3  test    eax, eax
0x1800800f5  jns     short loc_180080101
0x1800800f7  mov     edx, 1B5h
0x1800800fc  jmp     loc_18008003B
0x180080101  xor     ebx, ebx
0x180080103  call    cs:__imp_RoUninitialize
0x18008010a  nop     dword ptr [rax+rax+00h]
0x18008010f  mov     eax, ebx
0x180080111  add     rsp, 20h
0x180080115  pop     rbx
0x180080116  retn
```
