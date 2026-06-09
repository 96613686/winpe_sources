# EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(void)

- ea: `0x18007f5a0`
- end: `0x18007f73f`
- name: `?ServiceInitialization@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007f748`

## callees

- `0x18000bd50`
- `0x180067a34`
- `0x180067a54`
- `0x18007748c`
- `0x18007c9c8`
- `0x18007df1c`
- `0x18007e5cc`
- `0x18007ee74`
- `0x18007f5a0`
- `0x18007fa88`
- `0x18007fecc`
- `0x1800803ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007f61b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007f61b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007f5af`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18007f5af`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007f731`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18007f731`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18007f658`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18007f658`
- `dmenterprisediagnostics!SetupAutoLog` at `0x18007f5f5`
- `dmenterprisediagnostics!SetupAutoLog` at `0x18007f5f5`
- `dmenterprisediagnostics!StartAutoLog` at `0x18007f602`
- `dmenterprisediagnostics!StartAutoLog` at `0x18007f602`

## string_xrefs

- `0x18007f5c7`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f632`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f66c`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f6f2`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(
        EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *this)
{
  int v1; // eax
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v2; // rcx
  unsigned int v3; // r8d
  unsigned int LastError; // ebx
  EnterpriseDeviceManagement::Service::AutoPilot *v5; // rcx
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v6; // rcx
  const char *v7; // r9
  unsigned int EnrollmentServerShutdownDelay; // eax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *v12; // rax
  int v13; // eax
  unsigned int v14; // r8d
  EnterpriseDeviceManagement::Service::AutoPilot *v15; // rcx
  int v17; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v19; // [rsp+38h] [rbp+10h] BYREF

  v1 = RoInitialize(1);
  LastError = v1;
  if ( v1 >= 0 )
  {
    EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(v2, 2u, v3);
    SetupAutoLog(L"Autopilot", 0, 1);
    StartAutoLog(L"Autopilot");
    LOBYTE(v5) = 1;
    EnterpriseDeviceManagement::Service::AutoPilot::PerformProcMonProfileIfAvailable(v5);
    qword_18029E3E8 = CreateEventW(0, 1, 0, 0);
    if ( !qword_18029E3E8 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1A5,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
                    v7);
LABEL_18:
      RoUninitialize();
      return LastError;
    }
    EnrollmentServerShutdownDelay = EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::GetEnrollmentServerShutdownDelay(v6);
    v9 = CoRegisterServerShutdownDelay(qword_18029E3E8, EnrollmentServerShutdownDelay);
    LastError = v9;
    if ( v9 >= 0 )
    {
      v12 = (EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)operator new(
                                                                                         0x20u,
                                                                                         (const struct std::nothrow_t *)&std::nothrow);
      if ( v12 )
        v12 = (EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::ManagementServiceModule(v12);
      v19 = 0;
      wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(
        &qword_18029E3E0,
        v12);
      wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(
        &v19,
        0);
      if ( !qword_18029E3E0 )
      {
        LastError = -2147024882;
        v11 = 2147942414LL;
        v10 = 431;
        goto LABEL_8;
      }
      v13 = EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::RegisterContextObjects(qword_18029E3E0);
      LastError = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
          (const char *)(unsigned int)v13,
          v17);
        v11 = LastError;
        v10 = 433;
        goto LABEL_8;
      }
      EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(retaddr, 4u, v14);
      v9 = EnterpriseDeviceManagement::Service::AutoPilot::SetGlobalComSettings(v15);
      LastError = v9;
      if ( v9 >= 0 )
      {
        LastError = 0;
        goto LABEL_18;
      }
      v10 = 437;
    }
    else
    {
      v10 = 427;
    }
    v11 = (unsigned int)v9;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
      (const char *)v11,
      v17);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x197,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
    (const char *)(unsigned int)v1,
    v17);
  return LastError;
}

```

## disassembly

```asm
0x18007f5a0  mov     [rsp+arg_0], rcx
0x18007f5a5  push    rbx; int
0x18007f5a6  sub     rsp, 20h
0x18007f5aa  mov     ecx, 1
0x18007f5af  call    cs:__imp_RoInitialize
0x18007f5b5  mov     ebx, eax
0x18007f5b7  mov     dword ptr [rsp+28h+arg_0], eax
0x18007f5bb  test    eax, eax
0x18007f5bd  jns     short loc_18007F5DE
0x18007f5bf  mov     rcx, [rsp+28h]; this
0x18007f5c4  mov     r9d, eax; char *
0x18007f5c7  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f5ce  mov     edx, 197h; void *
0x18007f5d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f5d8  nop
0x18007f5d9  jmp     loc_18007F737
0x18007f5de  mov     edx, 2; unsigned int
0x18007f5e3  call    ?UpdateServiceStatus@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAXKK@Z; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(ulong,ulong)
0x18007f5e8  xor     edx, edx
0x18007f5ea  lea     r8d, [rdx+1]
0x18007f5ee  lea     rcx, aAutopilot; "Autopilot"
0x18007f5f5  call    cs:__imp_?SetupAutoLog@@YAJPEBG0H@Z; SetupAutoLog(ushort const *,ushort const *,int)
0x18007f5fb  lea     rcx, aAutopilot; "Autopilot"
0x18007f602  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x18007f608  mov     cl, 1; this
0x18007f60a  call    ?PerformProcMonProfileIfAvailable@AutoPilot@Service@EnterpriseDeviceManagement@@YAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::PerformProcMonProfileIfAvailable(bool)
0x18007f60f  xor     r9d, r9d; lpName
0x18007f612  xor     r8d, r8d; bInitialState
0x18007f615  lea     edx, [r9+1]; bManualReset
0x18007f619  xor     ecx, ecx; lpEventAttributes
0x18007f61b  call    cs:__imp_CreateEventW
0x18007f621  mov     cs:qword_18029E3E8, rax
0x18007f628  test    rax, rax
0x18007f62b  jnz     short loc_18007F64A
0x18007f62d  mov     rcx, [rsp+28h]; this
0x18007f632  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f639  mov     edx, 1A5h; void *
0x18007f63e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007f643  mov     ebx, eax
0x18007f645  jmp     loc_18007F731
0x18007f64a  call    ?GetEnrollmentServerShutdownDelay@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAKXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::GetEnrollmentServerShutdownDelay(void)
0x18007f64f  mov     edx, eax
0x18007f651  mov     rcx, cs:qword_18029E3E8
0x18007f658  call    cs:__imp_CoRegisterServerShutdownDelay
0x18007f65e  mov     ebx, eax
0x18007f660  test    eax, eax
0x18007f662  jns     short loc_18007F682
0x18007f664  mov     edx, 1ABh; void *
0x18007f669  mov     r9d, eax; char *
0x18007f66c  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f673  mov     rcx, [rsp+28h]; this
0x18007f678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f67d  jmp     loc_18007F731
0x18007f682  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007f689  mov     ecx, 20h ; ' '; unsigned __int64
0x18007f68e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007f693  test    rax, rax
0x18007f696  jz      short loc_18007F6A0
0x18007f698  mov     rcx, rax; this
0x18007f69b  call    ??0ManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@QEAA@XZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::ManagementServiceModule(void)
0x18007f6a0  mov     [rsp+28h+arg_8], 0
0x18007f6a9  mov     rdx, rax
0x18007f6ac  lea     rcx, qword_18029E3E0
0x18007f6b3  call    ?reset@?$unique_ptr@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@U?$default_delete@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@wistd@@@wistd@@QEAAXPEAVManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)
0x18007f6b8  xor     edx, edx
0x18007f6ba  lea     rcx, [rsp+28h+arg_8]
0x18007f6bf  call    ?reset@?$unique_ptr@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@U?$default_delete@VManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@wistd@@@wistd@@QEAAXPEAVManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; wistd::unique_ptr<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule,wistd::default_delete<EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule>>::reset(EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule *)
0x18007f6c4  mov     rcx, cs:qword_18029E3E0; this
0x18007f6cb  test    rcx, rcx
0x18007f6ce  jnz     short loc_18007F6DF
0x18007f6d0  mov     ebx, 8007000Eh
0x18007f6d5  mov     r9d, ebx
0x18007f6d8  mov     edx, 1AFh
0x18007f6dd  jmp     short loc_18007F66C
0x18007f6df  call    ?RegisterContextObjects@ManagementServiceModule@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementServiceModule::RegisterContextObjects(void)
0x18007f6e4  mov     ebx, eax
0x18007f6e6  mov     rcx, [rsp+28h]; this
0x18007f6eb  test    eax, eax
0x18007f6ed  jns     short loc_18007F710
0x18007f6ef  mov     r9d, eax; char *
0x18007f6f2  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f6f9  mov     edx, 0F7h; void *
0x18007f6fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f703  mov     r9d, ebx
0x18007f706  mov     edx, 1B1h
0x18007f70b  jmp     loc_18007F66C
0x18007f710  mov     edx, 4; unsigned int
0x18007f715  call    ?UpdateServiceStatus@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAXKK@Z; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::UpdateServiceStatus(ulong,ulong)
0x18007f71a  call    ?SetGlobalComSettings@AutoPilot@Service@EnterpriseDeviceManagement@@YAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::SetGlobalComSettings(void)
0x18007f71f  mov     ebx, eax
0x18007f721  test    eax, eax
0x18007f723  jns     short loc_18007F72F
0x18007f725  mov     edx, 1B5h
0x18007f72a  jmp     loc_18007F669
0x18007f72f  xor     ebx, ebx
0x18007f731  call    cs:__imp_RoUninitialize
0x18007f737  mov     eax, ebx
0x18007f739  add     rsp, 20h
0x18007f73d  pop     rbx
0x18007f73e  retn
```
