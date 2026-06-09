# Windows::Management::Setup::ConnectionMonitor::OnHeartbeatTimer(void)

- ea: `0x180102564`
- end: `0x180102ef5`
- name: `?OnHeartbeatTimer@ConnectionMonitor@Setup@Management@Windows@@AEAAJXZ`
- size: `2449`
- prototype: `__int64 __fastcall(Windows::Management::Setup::ConnectionMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180102310`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007748c`
- `0x18007755c`
- `0x18007ff90`
- `0x1800839bc`
- `0x18008b1ac`
- `0x18008c244`
- `0x1800953b4`
- `0x1800fba84`
- `0x18010006c`
- `0x18010024c`
- `0x180101cb4`
- `0x180102564`
- `0x180103034`
- `0x18010326c`
- `0x1801032d0`
- `0x1801035bc`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180102699`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180102699`
- `msvcp_win!_Mtx_unlock` at `0x18010271e`
- `msvcp_win!_Mtx_unlock` at `0x18010276d`
- `msvcp_win!_Mtx_unlock` at `0x180102e90`
- `msvcp_win!_Mtx_unlock` at `0x180102eab`
- `msvcp_win!_Mtx_unlock` at `0x18010271e`
- `msvcp_win!_Mtx_unlock` at `0x18010276d`
- `msvcp_win!_Mtx_unlock` at `0x180102e90`
- `msvcp_win!_Mtx_unlock` at `0x180102eab`

## string_xrefs

- `0x180102709`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180102899`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x1801029b9`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180102ae2`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180102db4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180102e54`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180102e7b`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\connectionmonitor.cpp`
- `0x180102b3e`: `Agent heartbeat tracking reset`
- `0x180102b53`: `Agent heartbeat launch succeeded`
- `0x180102a16`: `Agent heartbeat consecutive failed count: %u`
- `0x180102ce2`: `Agent heartbeat consecutive failed count: %u`
- `0x180102a2d`: `Agent heartbeat failed`
- `0x180102cf6`: `Agent heartbeat succeeded after previous failures`
- `0x180102c09`: `Agent heartbeat tracking not reset`
- `0x180102c1b`: `Agent heartbeat launch failed`

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
    v4 = (const unsigned __int16 *)&stru_180228C20;
  if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
              (HKEY)&stru_180228C20,
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
0x180102564  mov     [rsp+arg_8], rbx
0x180102569  mov     [rsp+arg_10], rsi
0x18010256e  push    rdi
0x18010256f  push    r12
0x180102571  push    r13
0x180102573  push    r14
0x180102575  push    r15
0x180102577  sub     rsp, 160h
0x18010257e  mov     rax, cs:__security_cookie
0x180102585  xor     rax, rsp
0x180102588  mov     [rsp+188h+var_38], rax
0x180102590  mov     rbx, rcx
0x180102593  lea     rdx, aOnheartbeattim; "OnHeartbeatTimer"
0x18010259a  lea     rcx, [rsp+188h+var_130]
0x18010259f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801025a4  nop
0x1801025a5  mov     rcx, [rbx+120h]
0x1801025ac  mov     rax, [rcx]
0x1801025af  lea     rdx, [rsp+188h+var_108]
0x1801025b7  mov     rax, [rax+0B8h]
0x1801025be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801025c3  mov     rdi, rax
0x1801025c6  mov     rdx, [rbx+120h]
0x1801025cd  mov     rcx, [rdx]
0x1801025d0  mov     rax, [rcx+0B0h]
0x1801025d7  mov     rcx, rdx
0x1801025da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801025df  lea     r9, [rsp+188h+var_130]
0x1801025e4  mov     r8, rdi
0x1801025e7  mov     rdx, rax
0x1801025ea  lea     rcx, [rsp+188h+var_B8]; this
0x1801025f2  call    ??0ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@PEAUIProvisioningSessionLogger@123@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger(Windows::Management::Setup::IProvisioningSessionLogger *,_GUID const &,std::wstring const &)
0x1801025f7  nop
0x1801025f8  lea     rcx, [rsp+188h+var_130]
0x1801025fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102602  lea     r13, [rbx+0D0h]
0x180102609  mov     [rsp+188h+var_138], r13
0x18010260e  mov     rcx, r13; this
0x180102611  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180102616  nop
0x180102617  mov     r14d, 8103B006h
0x18010261d  mov     [rsp+188h+var_144], r14d
0x180102622  mov     [rsp+188h+var_148], r14d
0x180102627  mov     edi, [rbx+8]
0x18010262a  mov     [rsp+188h+var_140], 0
0x180102632  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x180102637  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x18010263e  lea     rcx, stru_180228C20; HKEY
0x180102645  test    al, al
0x180102647  cmovnz  rdx, rcx; unsigned __int16 *
0x18010264b  lea     r9, [rsp+188h+var_140]; unsigned int *
0x180102650  lea     r8, aDppheartbeatma; "DppHeartbeatMaxFailures"
0x180102657  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18010265c  test    eax, eax
0x18010265e  cmovns  edi, [rsp+188h+var_140]
0x180102663  mov     [rsp+188h+var_140], edi
0x180102667  cmp     qword ptr [rbx+0B8h], 0
0x18010266f  jnz     short loc_180102679
0x180102671  mov     esi, r14d
0x180102674  jmp     loc_180102788
0x180102679  lea     rdx, aCallingHeartbe; "Calling heartbeat callback"
0x180102680  lea     rcx, [rsp+188h+var_B0]
0x180102688  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18010268d  mov     rcx, [rbx+0B8h]
0x180102694  test    rcx, rcx
0x180102697  jnz     short loc_18010269F
0x180102699  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18010269f  mov     rax, [rcx]
0x1801026a2  lea     r8, [rsp+188h+var_148]
0x1801026a7  lea     rdx, [rsp+188h+var_144]
0x1801026ac  mov     rax, [rax+10h]
0x1801026b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801026b5  mov     esi, eax
0x1801026b7  test    eax, eax
0x1801026b9  js      loc_180102788
0x1801026bf  cmp     [rsp+188h+var_148], r14d
0x1801026c4  jnz     loc_180102788
0x1801026ca  cmp     [rsp+188h+var_144], r14d
0x1801026cf  jnz     loc_180102788
0x1801026d5  lea     rdx, aNeitherHeartbe; "Neither heartbeat callbacks are still r"...
0x1801026dc  lea     rcx, [rsp+188h+var_B0]
0x1801026e4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801026e9  mov     rcx, rbx; this
0x1801026ec  call    ?StopHeartbeatTimer@ConnectionMonitor@Setup@Management@Windows@@QEAAJXZ; Windows::Management::Setup::ConnectionMonitor::StopHeartbeatTimer(void)
0x1801026f1  mov     edi, eax
0x1801026f3  mov     [rsp+188h+var_B8], eax
0x1801026fa  test    eax, eax
0x1801026fc  jns     short loc_180102739
0x1801026fe  mov     rcx, [rsp+188h]; this
0x180102706  mov     r9d, eax; char *
0x180102709  lea     r8, aOnecoreuapAdmi_119; "onecoreuap\\admin\\moderndeployment\\au"...
0x180102710  mov     edx, 85h; void *
0x180102715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010271a  nop
0x18010271b  mov     rcx, r13; _Mtx_t
0x18010271e  call    cs:__imp__Mtx_unlock
0x180102724  nop
0x180102725  lea     rcx, [rsp+188h+var_B8]; this
0x18010272d  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180102732  mov     eax, edi
0x180102734  jmp     loc_180102EC7
0x180102739  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180102740  jz      short loc_18010276A
0x180102742  mov     eax, [rbx+12Ch]
0x180102748  mov     [rsp+188h+var_158], eax
0x18010274c  mov     eax, [rbx+128h]
0x180102752  mov     [rsp+188h+var_160], eax
0x180102756  mov     [rsp+188h+var_168], esi
0x18010275a  mov     r9d, [rsp+188h+var_148]
0x18010275f  mov     r8d, [rsp+188h+var_144]
0x180102764  call    McTemplateU0dddqq_EventWriteTransfer
0x180102769  nop
0x18010276a  mov     rcx, r13; _Mtx_t
0x18010276d  call    cs:__imp__Mtx_unlock
0x180102773  nop
0x180102774  lea     rcx, [rsp+188h+var_B8]; this
0x18010277c  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180102781  xor     eax, eax
0x180102783  jmp     loc_180102EC7
0x180102788  mov     eax, [rbx+128h]
0x18010278e  cmp     [rsp+188h+var_144], 0
0x180102793  jge     loc_1801028B6
0x180102799  inc     eax
0x18010279b  mov     [rbx+128h], eax
0x1801027a1  mov     rcx, [rbx+120h]
0x1801027a8  mov     rax, [rcx]
0x1801027ab  mov     rax, [rax+0B0h]
0x1801027b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801027b7  mov     rdi, rax
0x1801027ba  mov     rcx, [rax]
0x1801027bd  mov     r12, [rcx+28h]
0x1801027c1  mov     r14d, [rsp+188h+var_144]
0x1801027c6  mov     r8d, [rbx+12Ch]
0x1801027cd  lea     rdx, aDisplayHeartbe_0; "Display heartbeat consecutive failed co"...
0x1801027d4  lea     rcx, [rsp+188h+var_D8]
0x1801027dc  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x1801027e1  mov     r15, rax
0x1801027e4  lea     rdx, aDisplayHeartbe; "Display heartbeat failed"
0x1801027eb  lea     rcx, [rsp+188h+var_130]
0x1801027f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801027f5  nop
0x1801027f6  mov     r8, [rbx+120h]
0x1801027fd  mov     rcx, [r8]
0x180102800  mov     rax, [rcx+0B8h]
0x180102807  lea     rdx, [rsp+188h+var_108]
0x18010280f  mov     rcx, r8
0x180102812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102817  xor     r8d, r8d
0x18010281a  mov     rdx, rax
0x18010281d  lea     rcx, [rsp+188h+var_F8]
0x180102825  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x18010282a  nop
0x18010282b  mov     [rsp+188h+var_168], r14d; int
0x180102830  mov     r9, r15
0x180102833  lea     r8, [rsp+188h+var_130]
0x180102838  mov     rdx, rax
0x18010283b  mov     rcx, rdi
0x18010283e  mov     rax, r12
0x180102841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102846  nop
0x180102847  lea     rcx, [rsp+188h+var_F8]
0x18010284f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102854  nop
0x180102855  lea     rcx, [rsp+188h+var_130]
0x18010285a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010285f  nop
0x180102860  lea     rcx, [rsp+188h+var_D8]
0x180102868  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010286d  mov     eax, [rsp+188h+var_140]
0x180102871  cmp     [rbx+128h], eax
0x180102877  jbe     loc_1801029D1
0x18010287d  mov     edx, 1
0x180102882  mov     rcx, rbx
0x180102885  call    ?UpdateConnectionState@ConnectionMonitor@Setup@Management@Windows@@AEAAJW4DeploymentSessionConnectionChange@234@@Z; Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(Windows::Management::Setup::DeploymentSessionConnectionChange)
0x18010288a  mov     rcx, [rsp+188h]; this
0x180102892  test    eax, eax
0x180102894  jns     short loc_1801028AA
0x180102896  mov     r9d, eax; char *
0x180102899  lea     r8, aOnecoreuapAdmi_119; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801028a0  mov     edx, 98h; void *
0x1801028a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801028aa  mov     byte ptr [rbx+130h], 1
0x1801028b1  jmp     loc_1801029D1
0x1801028b6  test    eax, eax
0x1801028b8  jz      loc_180102994
0x1801028be  mov     rcx, [rbx+120h]
0x1801028c5  mov     rax, [rcx]
0x1801028c8  mov     rax, [rax+0B0h]
0x1801028cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801028d4  mov     rdi, rax
0x1801028d7  mov     rcx, [rax]
0x1801028da  mov     r12, [rcx+10h]
0x1801028de  mov     r14d, [rsp+188h+var_148]
0x1801028e3  mov     r8d, [rbx+128h]
0x1801028ea  lea     rdx, aDisplayHeartbe_0; "Display heartbeat consecutive failed co"...
0x1801028f1  lea     rcx, [rsp+188h+var_F8]
0x1801028f9  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x1801028fe  mov     r15, rax
0x180102901  lea     rdx, aDisplayHeartbe_1; "Display heartbeat succeeded after previ"...
0x180102908  lea     rcx, [rsp+188h+var_130]
0x18010290d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180102912  nop
0x180102913  mov     r8, [rbx+120h]
0x18010291a  mov     rcx, [r8]
0x18010291d  mov     rax, [rcx+0B8h]
0x180102924  lea     rdx, [rsp+188h+var_108]
0x18010292c  mov     rcx, r8
0x18010292f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102934  xor     r8d, r8d
0x180102937  mov     rdx, rax
0x18010293a  lea     rcx, [rsp+188h+var_D8]
0x180102942  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180102947  nop
0x180102948  mov     [rsp+188h+var_168], r14d; int
0x18010294d  mov     r9, r15
0x180102950  lea     r8, [rsp+188h+var_130]
0x180102955  mov     rdx, rax
0x180102958  mov     rcx, rdi
0x18010295b  mov     rax, r12
0x18010295e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102963  nop
0x180102964  lea     rcx, [rsp+188h+var_D8]
0x18010296c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102971  nop
0x180102972  lea     rcx, [rsp+188h+var_130]
0x180102977  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010297c  nop
0x18010297d  lea     rcx, [rsp+188h+var_F8]
0x180102985  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010298a  mov     dword ptr [rbx+128h], 0
0x180102994  cmp     byte ptr [rbx+130h], 0
0x18010299b  jz      short loc_1801029D1
0x18010299d  mov     edx, 2
0x1801029a2  mov     rcx, rbx
0x1801029a5  call    ?UpdateConnectionState@ConnectionMonitor@Setup@Management@Windows@@AEAAJW4DeploymentSessionConnectionChange@234@@Z; Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(Windows::Management::Setup::DeploymentSessionConnectionChange)
0x1801029aa  mov     rcx, [rsp+188h]; this
0x1801029b2  test    eax, eax
0x1801029b4  jns     short loc_1801029CA
0x1801029b6  mov     r9d, eax; char *
0x1801029b9  lea     r8, aOnecoreuapAdmi_119; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801029c0  mov     edx, 0ABh; void *
0x1801029c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801029ca  mov     byte ptr [rbx+130h], 0
0x1801029d1  mov     eax, [rbx+12Ch]
0x1801029d7  cmp     [rsp+188h+var_148], 0
0x1801029dc  jge     loc_180102CAE
0x1801029e2  inc     eax
0x1801029e4  mov     [rbx+12Ch], eax
0x1801029ea  mov     rcx, [rbx+120h]
0x1801029f1  mov     rax, [rcx]
0x1801029f4  mov     rax, [rax+0B0h]
0x1801029fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102a00  mov     rdi, rax
0x180102a03  mov     rcx, [rax]
0x180102a06  mov     r12, [rcx+28h]
0x180102a0a  mov     r14d, [rsp+188h+var_148]
0x180102a0f  mov     r8d, [rbx+12Ch]
0x180102a16  lea     rdx, aAgentHeartbeat_3; "Agent heartbeat consecutive failed coun"...
0x180102a1d  lea     rcx, [rsp+188h+var_F8]
0x180102a25  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180102a2a  mov     r15, rax
0x180102a2d  lea     rdx, aAgentHeartbeat; "Agent heartbeat failed"
0x180102a34  lea     rcx, [rsp+188h+var_130]
0x180102a39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180102a3e  nop
0x180102a3f  mov     r8, [rbx+120h]
0x180102a46  mov     rcx, [r8]
0x180102a49  mov     rax, [rcx+0B8h]
0x180102a50  lea     rdx, [rsp+188h+var_108]
0x180102a58  mov     rcx, r8
0x180102a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102a60  xor     r8d, r8d
0x180102a63  mov     rdx, rax
0x180102a66  lea     rcx, [rsp+188h+var_D8]
0x180102a6e  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180102a73  nop
0x180102a74  mov     [rsp+188h+var_168], r14d; int
0x180102a79  mov     r9, r15
0x180102a7c  lea     r8, [rsp+188h+var_130]
0x180102a81  mov     rdx, rax
0x180102a84  mov     rcx, rdi
0x180102a87  mov     rax, r12
0x180102a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102a8f  nop
0x180102a90  lea     rcx, [rsp+188h+var_D8]
0x180102a98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102a9d  nop
0x180102a9e  lea     rcx, [rsp+188h+var_130]
0x180102aa3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102aa8  nop
0x180102aa9  lea     rcx, [rsp+188h+var_F8]
0x180102ab1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180102ab6  mov     eax, [rsp+188h+var_140]
0x180102aba  cmp     [rbx+12Ch], eax
0x180102ac0  jbe     loc_180102DCC
0x180102ac6  mov     edx, 3
0x180102acb  mov     rcx, rbx
0x180102ace  call    ?UpdateConnectionState@ConnectionMonitor@Setup@Management@Windows@@AEAAJW4DeploymentSessionConnectionChange@234@@Z; Windows::Management::Setup::ConnectionMonitor::UpdateConnectionState(Windows::Management::Setup::DeploymentSessionConnectionChange)
0x180102ad3  mov     rcx, [rsp+188h]; this
0x180102adb  test    eax, eax
  ... truncated ...
```
