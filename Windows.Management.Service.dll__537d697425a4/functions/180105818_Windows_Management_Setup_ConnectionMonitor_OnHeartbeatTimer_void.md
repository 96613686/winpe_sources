# Windows::Management::Setup::ConnectionMonitor::OnHeartbeatTimer(void)

- ea: `0x180105818`
- end: `0x1801061c7`
- name: `?OnHeartbeatTimer@ConnectionMonitor@Setup@Management@Windows@@AEAAJXZ`
- size: `2479`
- prototype: `__int64 __fastcall(Windows::Management::Setup::ConnectionMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801055b0`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077d0c`
- `0x180077de0`
- `0x180080984`
- `0x180084574`
- `0x18008c0f0`
- `0x18008d290`
- `0x1800966b8`
- `0x1800feb74`
- `0x1801031ec`
- `0x1801033d4`
- `0x180104f08`
- `0x180105818`
- `0x180106310`
- `0x180106558`
- `0x1801065c8`
- `0x1801068bc`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18010594d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18010594d`
- `msvcp_win!_Mtx_unlock` at `0x1801059d8`
- `msvcp_win!_Mtx_unlock` at `0x180105a2d`
- `msvcp_win!_Mtx_unlock` at `0x180106156`
- `msvcp_win!_Mtx_unlock` at `0x180106177`
- `msvcp_win!_Mtx_unlock` at `0x1801059d8`
- `msvcp_win!_Mtx_unlock` at `0x180105a2d`
- `msvcp_win!_Mtx_unlock` at `0x180106156`
- `msvcp_win!_Mtx_unlock` at `0x180106177`

## string_xrefs

- `0x1801059c3`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180105b5f`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180105c7f`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180105da8`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x18010607a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x18010611a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180106141`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180105e19`: `Agent heartbeat launch succeeded`
- `0x180105e04`: `Agent heartbeat tracking reset`
- `0x180105ee1`: `Agent heartbeat launch failed`
- `0x180105ecf`: `Agent heartbeat tracking not reset`
- `0x180105cf3`: `Agent heartbeat failed`
- `0x180105cdc`: `Agent heartbeat consecutive failed count: %u`
- `0x180105fa8`: `Agent heartbeat consecutive failed count: %u`
- `0x180105fbc`: `Agent heartbeat succeeded after previous failures`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall Windows::Management::Setup::ConnectionMonitor::OnHeartbeatTimer(
        Windows::Management::Setup::ConnectionMonitor *this)
{
  unsigned int v2; // edi
  bool v3; // al
  const unsigned __int16 *v4; // rdx
  int v5; // edx
  int v6; // ecx
  int v7; // esi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  unsigned int v12; // edi
  int v14; // eax
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, __int64, _BYTE *, __int64); // r12
  int v17; // r14d
  __int64 v18; // r15
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, __int64, _BYTE *, __int64); // r12
  int v24; // r14d
  __int64 v25; // r15
  __int64 v26; // rax
  __int64 v27; // rax
  int updated; // eax
  int v29; // eax
  __int64 v30; // rdi
  void (__fastcall *v31)(__int64, __int64, _BYTE *, __int64); // r12
  int v32; // r14d
  __int64 v33; // r15
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // eax
  int v37; // r15d
  __int64 v38; // rdx
  __int64 v39; // rdi
  void (__fastcall *v40)(__int64, __int64, _BYTE *, _BYTE *); // r14
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdi
  void (__fastcall *v44)(__int64, __int64, _BYTE *, _BYTE *); // r14
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdi
  void (__fastcall *v48)(__int64, __int64, _BYTE *, __int64); // r12
  int v49; // r14d
  __int64 v50; // r15
  __int64 v51; // rax
  __int64 v52; // rax
  int v53; // eax
  int v54; // eax
  int v55; // [rsp+20h] [rbp-168h]
  int v56; // [rsp+40h] [rbp-148h] BYREF
  int v57; // [rsp+44h] [rbp-144h] BYREF
  unsigned int v58; // [rsp+48h] [rbp-140h] BYREF
  char *v59; // [rsp+50h] [rbp-138h]
  _BYTE v60[40]; // [rsp+58h] [rbp-130h] BYREF
  struct _GUID v61; // [rsp+80h] [rbp-108h] BYREF
  _BYTE v62[32]; // [rsp+90h] [rbp-F8h] BYREF
  _BYTE v63[32]; // [rsp+B0h] [rbp-D8h] BYREF
  int v64; // [rsp+D0h] [rbp-B8h] BYREF
  _BYTE v65[120]; // [rsp+D8h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  std::wstring::wstring(v60, L"OnHeartbeatTimer");
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(*((_QWORD *)this + 36), &v61);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 176LL))(*((_QWORD *)this + 36));
  Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v64);
  std::wstring::_Tidy_deallocate(v60);
  v59 = (char *)this + 208;
  std::_Mutex_base::lock((Windows::Management::Setup::ConnectionMonitor *)((char *)this + 208));
  v57 = -2130464762;
  v56 = -2130464762;
  v2 = *((_DWORD *)this + 2);
  v58 = 0;
  v3 = ZTPIsStateSeparationEnabled();
  v4 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
  if ( v3 )
    v4 = (const unsigned __int16 *)&stru_18022EC60;
  if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
              (HKEY)&stru_18022EC60,
              v4,
              L"DppHeartbeatMaxFailures",
              &v58) >= 0 )
    v2 = v58;
  v58 = v2;
  if ( *((_QWORD *)this + 23) )
  {
    std::wstring::assign(v65, L"Calling heartbeat callback");
    v8 = *((_QWORD *)this + 23);
    if ( !v8 )
      std::_Xbad_function_call();
    v7 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v8 + 16LL))(v8, &v57, &v56);
    if ( v7 >= 0 && v56 == -2130464762 && v57 == -2130464762 )
    {
      std::wstring::assign(v65, L"Neither heartbeat callbacks are still registered; stopping heartbeat");
      v9 = Windows::Management::Setup::ConnectionMonitor::StopHeartbeatTimer(this);
      v12 = v9;
      v64 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
          (const char *)(unsigned int)v9,
          v55);
        _Mtx_unlock((Windows::Management::Setup::ConnectionMonitor *)((char *)this + 208));
        Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v64);
        return v12;
      }
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0dddqq_EventWriteTransfer(v11, v10, v57, v56, v7, *((_DWORD *)this + 74), *((_DWORD *)this + 75));
      goto LABEL_50;
    }
  }
  else
  {
    v7 = -2130464762;
  }
  v14 = *((_DWORD *)this + 74);
  if ( v57 >= 0 )
  {
    if ( v14 )
    {
      v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 176LL))(*((_QWORD *)this + 36));
      v23 = *(void (__fastcall **)(__int64, __int64, _BYTE *, __int64))(*(_QWORD *)v22 + 16LL);
      v24 = v56;
      v25 = wil::str_printf<std::wstring>(
              v62,
              L"Display heartbeat consecutive failed count: %u",
              *((unsigned int *)this + 74));
      std::wstring::wstring(v60, L"Display heartbeat succeeded after previous failures");
      v26 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(
              *((_QWORD *)this + 36),
              &v61);
      v27 = Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v63, v26, 0);
      v55 = v24;
      v23(v22, v27, v60, v25);
      std::wstring::_Tidy_deallocate(v63);
      std::wstring::_Tidy_deallocate(v60);
      std::wstring::_Tidy_deallocate(v62);
      *((_DWORD *)this + 74) = 0;
    }
    if ( *((_BYTE *)this + 304) )
    {
      updated = Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(this, 2);
      v6 = (int)retaddr;
      if ( updated < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
          (const char *)(unsigned int)updated,
          v55);
      *((_BYTE *)this + 304) = 0;
    }
  }
  else
  {
    *((_DWORD *)this + 74) = v14 + 1;
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 176LL))(*((_QWORD *)this + 36));
    v16 = *(void (__fastcall **)(__int64, __int64, _BYTE *, __int64))(*(_QWORD *)v15 + 40LL);
    v17 = v57;
    v18 = wil::str_printf<std::wstring>(
            v63,
            L"Display heartbeat consecutive failed count: %u",
            *((unsigned int *)this + 75));
    std::wstring::wstring(v60, L"Display heartbeat failed");
    v19 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(
            *((_QWORD *)this + 36),
            &v61);
    v20 = Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v62, v19, 0);
    v55 = v17;
    v16(v15, v20, v60, v18);
    std::wstring::_Tidy_deallocate(v62);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v63);
    if ( *((_DWORD *)this + 74) > v58 )
    {
      v21 = Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(this, 1);
      v6 = (int)retaddr;
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
          (const char *)(unsigned int)v21,
          v17);
      *((_BYTE *)this + 304) = 1;
    }
  }
  v29 = *((_DWORD *)this + 75);
  if ( v56 >= 0 )
  {
    if ( v29 )
    {
      v47 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 176LL))(*((_QWORD *)this + 36));
      v48 = *(void (__fastcall **)(__int64, __int64, _BYTE *, __int64))(*(_QWORD *)v47 + 16LL);
      v49 = v56;
      v50 = wil::str_printf<std::wstring>(
              v60,
              L"Agent heartbeat consecutive failed count: %u",
              *((unsigned int *)this + 75));
      std::wstring::wstring(v62, L"Agent heartbeat succeeded after previous failures");
      v51 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(
              *((_QWORD *)this + 36),
              &v61);
      v52 = Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v63, v51, 0);
      v55 = v49;
      v48(v47, v52, v62, v50);
      std::wstring::_Tidy_deallocate(v63);
      std::wstring::_Tidy_deallocate(v62);
      std::wstring::_Tidy_deallocate(v60);
      *((_DWORD *)this + 75) = 0;
    }
    if ( *((_BYTE *)this + 305) )
    {
      v53 = Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(this, 4);
      v6 = (int)retaddr;
      if ( v53 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
          (const char *)(unsigned int)v53,
          v55);
      *((_BYTE *)this + 305) = 0;
    }
  }
  else
  {
    *((_DWORD *)this + 75) = v29 + 1;
    v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 176LL))(*((_QWORD *)this + 36));
    v31 = *(void (__fastcall **)(__int64, __int64, _BYTE *, __int64))(*(_QWORD *)v30 + 40LL);
    v32 = v56;
    v33 = wil::str_printf<std::wstring>(
            v62,
            L"Agent heartbeat consecutive failed count: %u",
            *((unsigned int *)this + 75));
    std::wstring::wstring(v60, L"Agent heartbeat failed");
    v34 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(
            *((_QWORD *)this + 36),
            &v61);
    v35 = Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v63, v34, 0);
    v55 = v32;
    v31(v30, v35, v60, v33);
    std::wstring::_Tidy_deallocate(v63);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v62);
    if ( *((_DWORD *)this + 75) > v58 )
    {
      v36 = Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(this, 3);
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
          (const char *)(unsigned int)v36,
          v32);
      *((_BYTE *)this + 305) = 1;
      v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 168LL))(*((_QWORD *)this + 36));
      v38 = *((_QWORD *)this + 36);
      if ( v37 < 0 )
      {
        v43 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v38 + 176LL))(*((_QWORD *)this + 36), v38);
        v44 = *(void (__fastcall **)(__int64, __int64, _BYTE *, _BYTE *))(*(_QWORD *)v43 + 24LL);
        std::wstring::wstring(v60, L"Agent heartbeat tracking not reset");
        std::wstring::wstring(v62, L"Agent heartbeat launch failed");
        v45 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(
                *((_QWORD *)this + 36),
                &v61);
        v46 = Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v63, v45, 0);
        v55 = v37;
        v44(v43, v46, v62, v60);
        std::wstring::_Tidy_deallocate(v63);
        std::wstring::_Tidy_deallocate(v62);
        std::wstring::_Tidy_deallocate(v60);
      }
      else
      {
        v39 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v38 + 176LL))(*((_QWORD *)this + 36));
        v40 = *(void (__fastcall **)(__int64, __int64, _BYTE *, _BYTE *))(*(_QWORD *)v39 + 16LL);
        std::wstring::wstring(v62, L"Agent heartbeat tracking reset");
        std::wstring::wstring(v60, L"Agent heartbeat launch succeeded");
        v41 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 36) + 184LL))(
                *((_QWORD *)this + 36),
                &v61);
        v42 = Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v63, v41, 0);
        v55 = v37;
        v40(v39, v42, v60, v62);
        std::wstring::_Tidy_deallocate(v63);
        std::wstring::_Tidy_deallocate(v60);
        std::wstring::_Tidy_deallocate(v62);
        *((_DWORD *)this + 75) = 0;
      }
    }
  }
  if ( (v7 < 0 || v57 < 0 || v56 < 0) && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    McTemplateU0dddqq_EventWriteTransfer(v6, v5, v57, v56, v7, *((_DWORD *)this + 74), *((_DWORD *)this + 75));
  v61 = *(struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 36) + 184LL))(
                           *((_QWORD *)this + 36),
                           v60);
  v54 = Windows::Management::Setup::ConnectionMonitor::SetNextHeartbeatInterval(this, &v61);
  if ( v54 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
      (const char *)(unsigned int)v54,
      v55);
  v64 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\connectionmonitor.cpp",
      (const char *)(unsigned int)v7,
      v55);
    _Mtx_unlock((Windows::Management::Setup::ConnectionMonitor *)((char *)this + 208));
    Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v64);
    return (unsigned int)v7;
  }
LABEL_50:
  _Mtx_unlock((Windows::Management::Setup::ConnectionMonitor *)((char *)this + 208));
  Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v64);
  return 0;
}

```

## disassembly

```asm
0x180105818  mov     [rsp+arg_8], rbx
0x18010581d  mov     [rsp+arg_10], rsi
0x180105822  push    rdi
0x180105823  push    r12
0x180105825  push    r13
0x180105827  push    r14
0x180105829  push    r15
0x18010582b  sub     rsp, 160h
0x180105832  mov     rax, cs:__security_cookie
0x180105839  xor     rax, rsp
0x18010583c  mov     [rsp+188h+var_38], rax
0x180105844  mov     rbx, rcx
0x180105847  lea     rdx, aOnheartbeattim; "OnHeartbeatTimer"
0x18010584e  lea     rcx, [rsp+188h+var_130]
0x180105853  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180105858  nop
0x180105859  mov     rcx, [rbx+120h]
0x180105860  mov     rax, [rcx]
0x180105863  lea     rdx, [rsp+188h+var_108]
0x18010586b  mov     rax, [rax+0B8h]
0x180105872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105877  mov     rdi, rax
0x18010587a  mov     rdx, [rbx+120h]
0x180105881  mov     rcx, [rdx]
0x180105884  mov     rax, [rcx+0B0h]
0x18010588b  mov     rcx, rdx
0x18010588e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105893  lea     r9, [rsp+188h+var_130]
0x180105898  mov     r8, rdi
0x18010589b  mov     rdx, rax
0x18010589e  lea     rcx, [rsp+188h+var_B8]; this
0x1801058a6  call    ??0ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@PEAUIProvisioningSessionLogger@123@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger(Windows::Management::Setup::IProvisioningSessionLogger *,_GUID const &,std::wstring const &)
0x1801058ab  nop
0x1801058ac  lea     rcx, [rsp+188h+var_130]
0x1801058b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801058b6  lea     r13, [rbx+0D0h]
0x1801058bd  mov     [rsp+188h+var_138], r13
0x1801058c2  mov     rcx, r13; this
0x1801058c5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801058ca  nop
0x1801058cb  mov     r14d, 8103B006h
0x1801058d1  mov     [rsp+188h+var_144], r14d
0x1801058d6  mov     [rsp+188h+var_148], r14d
0x1801058db  mov     edi, [rbx+8]
0x1801058de  mov     [rsp+188h+var_140], 0
0x1801058e6  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1801058eb  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1801058f2  lea     rcx, stru_18022EC60; HKEY
0x1801058f9  test    al, al
0x1801058fb  cmovnz  rdx, rcx; unsigned __int16 *
0x1801058ff  lea     r9, [rsp+188h+var_140]; unsigned int *
0x180105904  lea     r8, aDppheartbeatma; "DppHeartbeatMaxFailures"
0x18010590b  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x180105910  test    eax, eax
0x180105912  cmovns  edi, [rsp+188h+var_140]
0x180105917  mov     [rsp+188h+var_140], edi
0x18010591b  cmp     qword ptr [rbx+0B8h], 0
0x180105923  jnz     short loc_18010592D
0x180105925  mov     esi, r14d
0x180105928  jmp     loc_180105A4E
0x18010592d  lea     rdx, aCallingHeartbe; "Calling heartbeat callback"
0x180105934  lea     rcx, [rsp+188h+var_B0]
0x18010593c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180105941  mov     rcx, [rbx+0B8h]
0x180105948  test    rcx, rcx
0x18010594b  jnz     short loc_180105959
0x18010594d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180105954  nop     dword ptr [rax+rax+00h]
0x180105959  mov     rax, [rcx]
0x18010595c  lea     r8, [rsp+188h+var_148]
0x180105961  lea     rdx, [rsp+188h+var_144]
0x180105966  mov     rax, [rax+10h]
0x18010596a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010596f  mov     esi, eax
0x180105971  test    eax, eax
0x180105973  js      loc_180105A4E
0x180105979  cmp     [rsp+188h+var_148], r14d
0x18010597e  jnz     loc_180105A4E
0x180105984  cmp     [rsp+188h+var_144], r14d
0x180105989  jnz     loc_180105A4E
0x18010598f  lea     rdx, aNeitherHeartbe; "Neither heartbeat callbacks are still r"...
0x180105996  lea     rcx, [rsp+188h+var_B0]
0x18010599e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801059a3  mov     rcx, rbx; this
0x1801059a6  call    ?StopHeartbeatTimer@ConnectionMonitor@Setup@Management@Windows@@QEAAJXZ; Windows::Management::Setup::ConnectionMonitor::StopHeartbeatTimer(void)
0x1801059ab  mov     edi, eax
0x1801059ad  mov     [rsp+188h+var_B8], eax
0x1801059b4  test    eax, eax
0x1801059b6  jns     short loc_1801059F9
0x1801059b8  mov     rcx, [rsp+188h]; this
0x1801059c0  mov     r9d, eax; char *
0x1801059c3  lea     r8, aOnecoreuapAdmi_119; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801059ca  mov     edx, 85h; void *
0x1801059cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801059d4  nop
0x1801059d5  mov     rcx, r13; _Mtx_t
0x1801059d8  call    cs:__imp__Mtx_unlock
0x1801059df  nop     dword ptr [rax+rax+00h]
0x1801059e4  nop
0x1801059e5  lea     rcx, [rsp+188h+var_B8]; this
0x1801059ed  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1801059f2  mov     eax, edi
0x1801059f4  jmp     loc_180106199
0x1801059f9  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180105a00  jz      short loc_180105A2A
0x180105a02  mov     eax, [rbx+12Ch]
0x180105a08  mov     [rsp+188h+var_158], eax
0x180105a0c  mov     eax, [rbx+128h]
0x180105a12  mov     [rsp+188h+var_160], eax
0x180105a16  mov     [rsp+188h+var_168], esi
0x180105a1a  mov     r9d, [rsp+188h+var_148]
0x180105a1f  mov     r8d, [rsp+188h+var_144]
0x180105a24  call    McTemplateU0dddqq_EventWriteTransfer
0x180105a29  nop
0x180105a2a  mov     rcx, r13; _Mtx_t
0x180105a2d  call    cs:__imp__Mtx_unlock
0x180105a34  nop     dword ptr [rax+rax+00h]
0x180105a39  nop
0x180105a3a  lea     rcx, [rsp+188h+var_B8]; this
0x180105a42  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180105a47  xor     eax, eax
0x180105a49  jmp     loc_180106199
0x180105a4e  mov     eax, [rbx+128h]
0x180105a54  cmp     [rsp+188h+var_144], 0
0x180105a59  jge     loc_180105B7C
0x180105a5f  inc     eax
0x180105a61  mov     [rbx+128h], eax
0x180105a67  mov     rcx, [rbx+120h]
0x180105a6e  mov     rax, [rcx]
0x180105a71  mov     rax, [rax+0B0h]
0x180105a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105a7d  mov     rdi, rax
0x180105a80  mov     rcx, [rax]
0x180105a83  mov     r12, [rcx+28h]
0x180105a87  mov     r14d, [rsp+188h+var_144]
0x180105a8c  mov     r8d, [rbx+12Ch]
0x180105a93  lea     rdx, aDisplayHeartbe_0; "Display heartbeat consecutive failed co"...
0x180105a9a  lea     rcx, [rsp+188h+var_D8]
0x180105aa2  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180105aa7  mov     r15, rax
0x180105aaa  lea     rdx, aDisplayHeartbe; "Display heartbeat failed"
0x180105ab1  lea     rcx, [rsp+188h+var_130]
0x180105ab6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180105abb  nop
0x180105abc  mov     r8, [rbx+120h]
0x180105ac3  mov     rcx, [r8]
0x180105ac6  mov     rax, [rcx+0B8h]
0x180105acd  lea     rdx, [rsp+188h+var_108]
0x180105ad5  mov     rcx, r8
0x180105ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105add  xor     r8d, r8d
0x180105ae0  mov     rdx, rax
0x180105ae3  lea     rcx, [rsp+188h+var_F8]
0x180105aeb  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180105af0  nop
0x180105af1  mov     [rsp+188h+var_168], r14d; int
0x180105af6  mov     r9, r15
0x180105af9  lea     r8, [rsp+188h+var_130]
0x180105afe  mov     rdx, rax
0x180105b01  mov     rcx, rdi
0x180105b04  mov     rax, r12
0x180105b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105b0c  nop
0x180105b0d  lea     rcx, [rsp+188h+var_F8]
0x180105b15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105b1a  nop
0x180105b1b  lea     rcx, [rsp+188h+var_130]
0x180105b20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105b25  nop
0x180105b26  lea     rcx, [rsp+188h+var_D8]
0x180105b2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105b33  mov     eax, [rsp+188h+var_140]
0x180105b37  cmp     [rbx+128h], eax
0x180105b3d  jbe     loc_180105C97
0x180105b43  mov     edx, 1
0x180105b48  mov     rcx, rbx
0x180105b4b  call    ?UpdateConnectionState@ConnectionMonitor@Setup@Management@Windows@@AEAAJW4DeploymentSessionConnectionChange@234@@Z; Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(Windows::Management::Setup::DeploymentSessionConnectionChange)
0x180105b50  mov     rcx, [rsp+188h]; this
0x180105b58  test    eax, eax
0x180105b5a  jns     short loc_180105B70
0x180105b5c  mov     r9d, eax; char *
0x180105b5f  lea     r8, aOnecoreuapAdmi_119; "onecoreuap\\admin\\moderndeployment\\au"...
0x180105b66  mov     edx, 98h; void *
0x180105b6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180105b70  mov     byte ptr [rbx+130h], 1
0x180105b77  jmp     loc_180105C97
0x180105b7c  test    eax, eax
0x180105b7e  jz      loc_180105C5A
0x180105b84  mov     rcx, [rbx+120h]
0x180105b8b  mov     rax, [rcx]
0x180105b8e  mov     rax, [rax+0B0h]
0x180105b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105b9a  mov     rdi, rax
0x180105b9d  mov     rcx, [rax]
0x180105ba0  mov     r12, [rcx+10h]
0x180105ba4  mov     r14d, [rsp+188h+var_148]
0x180105ba9  mov     r8d, [rbx+128h]
0x180105bb0  lea     rdx, aDisplayHeartbe_0; "Display heartbeat consecutive failed co"...
0x180105bb7  lea     rcx, [rsp+188h+var_F8]
0x180105bbf  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180105bc4  mov     r15, rax
0x180105bc7  lea     rdx, aDisplayHeartbe_1; "Display heartbeat succeeded after previ"...
0x180105bce  lea     rcx, [rsp+188h+var_130]
0x180105bd3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180105bd8  nop
0x180105bd9  mov     r8, [rbx+120h]
0x180105be0  mov     rcx, [r8]
0x180105be3  mov     rax, [rcx+0B8h]
0x180105bea  lea     rdx, [rsp+188h+var_108]
0x180105bf2  mov     rcx, r8
0x180105bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105bfa  xor     r8d, r8d
0x180105bfd  mov     rdx, rax
0x180105c00  lea     rcx, [rsp+188h+var_D8]
0x180105c08  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180105c0d  nop
0x180105c0e  mov     [rsp+188h+var_168], r14d; int
0x180105c13  mov     r9, r15
0x180105c16  lea     r8, [rsp+188h+var_130]
0x180105c1b  mov     rdx, rax
0x180105c1e  mov     rcx, rdi
0x180105c21  mov     rax, r12
0x180105c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105c29  nop
0x180105c2a  lea     rcx, [rsp+188h+var_D8]
0x180105c32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105c37  nop
0x180105c38  lea     rcx, [rsp+188h+var_130]
0x180105c3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105c42  nop
0x180105c43  lea     rcx, [rsp+188h+var_F8]
0x180105c4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105c50  mov     dword ptr [rbx+128h], 0
0x180105c5a  cmp     byte ptr [rbx+130h], 0
0x180105c61  jz      short loc_180105C97
0x180105c63  mov     edx, 2
0x180105c68  mov     rcx, rbx
0x180105c6b  call    ?UpdateConnectionState@ConnectionMonitor@Setup@Management@Windows@@AEAAJW4DeploymentSessionConnectionChange@234@@Z; Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(Windows::Management::Setup::DeploymentSessionConnectionChange)
0x180105c70  mov     rcx, [rsp+188h]; this
0x180105c78  test    eax, eax
0x180105c7a  jns     short loc_180105C90
0x180105c7c  mov     r9d, eax; char *
0x180105c7f  lea     r8, aOnecoreuapAdmi_119; "onecoreuap\\admin\\moderndeployment\\au"...
0x180105c86  mov     edx, 0ABh; void *
0x180105c8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180105c90  mov     byte ptr [rbx+130h], 0
0x180105c97  mov     eax, [rbx+12Ch]
0x180105c9d  cmp     [rsp+188h+var_148], 0
0x180105ca2  jge     loc_180105F74
0x180105ca8  inc     eax
0x180105caa  mov     [rbx+12Ch], eax
0x180105cb0  mov     rcx, [rbx+120h]
0x180105cb7  mov     rax, [rcx]
0x180105cba  mov     rax, [rax+0B0h]
0x180105cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105cc6  mov     rdi, rax
0x180105cc9  mov     rcx, [rax]
0x180105ccc  mov     r12, [rcx+28h]
0x180105cd0  mov     r14d, [rsp+188h+var_148]
0x180105cd5  mov     r8d, [rbx+12Ch]
0x180105cdc  lea     rdx, aAgentHeartbeat_3; "Agent heartbeat consecutive failed coun"...
0x180105ce3  lea     rcx, [rsp+188h+var_F8]
0x180105ceb  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180105cf0  mov     r15, rax
0x180105cf3  lea     rdx, aAgentHeartbeat; "Agent heartbeat failed"
0x180105cfa  lea     rcx, [rsp+188h+var_130]
0x180105cff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180105d04  nop
0x180105d05  mov     r8, [rbx+120h]
0x180105d0c  mov     rcx, [r8]
0x180105d0f  mov     rax, [rcx+0B8h]
0x180105d16  lea     rdx, [rsp+188h+var_108]
0x180105d1e  mov     rcx, r8
0x180105d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105d26  xor     r8d, r8d
0x180105d29  mov     rdx, rax
0x180105d2c  lea     rcx, [rsp+188h+var_D8]
0x180105d34  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180105d39  nop
0x180105d3a  mov     [rsp+188h+var_168], r14d; int
0x180105d3f  mov     r9, r15
0x180105d42  lea     r8, [rsp+188h+var_130]
0x180105d47  mov     rdx, rax
0x180105d4a  mov     rcx, rdi
0x180105d4d  mov     rax, r12
0x180105d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105d55  nop
0x180105d56  lea     rcx, [rsp+188h+var_D8]
0x180105d5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105d63  nop
0x180105d64  lea     rcx, [rsp+188h+var_130]
0x180105d69  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105d6e  nop
0x180105d6f  lea     rcx, [rsp+188h+var_F8]
0x180105d77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105d7c  mov     eax, [rsp+188h+var_140]
0x180105d80  cmp     [rbx+12Ch], eax
0x180105d86  jbe     loc_180106092
0x180105d8c  mov     edx, 3
0x180105d91  mov     rcx, rbx
  ... truncated ...
```
