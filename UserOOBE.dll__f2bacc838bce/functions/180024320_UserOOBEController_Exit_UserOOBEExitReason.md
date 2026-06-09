# UserOOBEController::Exit(UserOOBEExitReason)

- ea: `0x180024320`
- end: `0x180024829`
- name: `?Exit@UserOOBEController@@UEAAJW4UserOOBEExitReason@@@Z`
- size: `1289`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007134`
- `0x18000e270`
- `0x180015434`
- `0x1800218b8`
- `0x180021c8c`
- `0x180024320`
- `0x1800268e0`
- `0x1800279b8`
- `0x180027c60`
- `0x180027fb0`
- `0x180028974`
- `0x180028e74`
- `0x180028f50`
- `0x180029260`
- `0x180029890`
- `0x180029b68`
- `0x180047bd0`
- `0x180047e1c`
- `0x1800488e0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180024709`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180024709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002455d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002455d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002454a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002454a`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180024730`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180024730`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024434`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002450a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024434`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002450a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024463`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024536`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024463`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024536`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002446f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002446f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024542`

## string_xrefs

- `0x18002438e`: `Removing monitor task failed [hr=0x%08X]`
- `0x1800243a6`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800245e2`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180024662`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180024697`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800246df`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180024752`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800247b8`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800247e2`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800246cc`: `Reschedule delete rdx content failed [hr=0x%08X]`
- `0x18002452f`: `SetupFinalTasks`
- `0x180024411`: `System\Setup\Status\ChildCompletion`
- `0x1800244e3`: `System\Setup\Status\ChildCompletion`

## pseudocode

```c
__int64 __fastcall UserOOBEController::Exit(UserOOBEController *a1, unsigned int a2)
{
  bool v4; // r14
  int v5; // eax
  int updated; // ebx
  __int64 v7; // rdx
  DWORD v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rdx
  LSTATUS v12; // ebx
  HKEY v13; // rdx
  HKEY v14; // rcx
  const unsigned __int16 *v15; // r8
  signed int LastError; // eax
  bool v17; // sf
  signed int v18; // eax
  LSTATUS v19; // ebx
  HKEY v20; // rdx
  HKEY v21; // rcx
  const unsigned __int16 *v22; // r8
  signed int v23; // eax
  bool v24; // sf
  signed int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  unsigned int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-30h]
  int dwOptionsa; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  int Data; // [rsp+90h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF

  UnattendLogW(0, L"UserOOBEController::Exit() started [%d]", a2);
  v4 = (a2 & 0xFFFFFFFD) == 0;
  if ( a2 == 4 )
    v4 = 1;
  if ( a2 == 3 )
    OOBE::Health::details::OOBEHealthTracker::HandleEvent<27,bool>();
  if ( *((_BYTE *)a1 + 16) )
  {
    v5 = UserOOBEController::s_RemoveUserOOBEMonitorTask(a2 == 1);
    updated = v5;
    if ( v5 < 0 )
    {
      UnattendLogW(1, L"Removing monitor task failed [hr=0x%08X]", (unsigned int)v5);
      v7 = 171;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)updated,
        dwOptions);
      return (unsigned int)updated;
    }
  }
  if ( v4 && *((_BYTE *)a1 + 16) )
  {
    OOBE::Health::details::OOBEHealthTracker::HandleEvent<1,bool>();
    updated = OrchestrateBootCommand(v10, v9);
    if ( updated < 0 )
    {
      v11 = 501;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)updated,
        dwOptions);
      UnattendLogW(1, L"Preparing reboot failed [hr=0x%08X]", (unsigned int)updated);
      v7 = 177;
      goto LABEL_8;
    }
    Data = 0;
    hKey = 0;
    dwDisposition = 0;
    v12 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\Setup\\Status\\ChildCompletion",
            0,
            (LPWSTR)&Class,
            0,
            0x20006u,
            0,
            &hKey,
            &dwDisposition);
    if ( !v12 )
    {
      v12 = RegSetValueExW(hKey, L"oobeldr.exe", 0, 4u, (const BYTE *)&Data, 4u);
      RegCloseKey(hKey);
    }
    SetLastError(v12);
    if ( v12 )
    {
      LastError = GetLastError();
      v17 = LastError < 0;
      if ( LastError > 0 )
        v17 = 1;
      if ( !v17 )
      {
        updated = -2147467259;
        goto LABEL_40;
      }
      v18 = GetLastError();
      updated = v18;
      if ( v18 > 0 )
        updated = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      updated = OrchestrateUpdateImageState(v14, v13, v15);
    }
    if ( updated >= 0 )
    {
      Data = 0;
      hKey = 0;
      dwDisposition = 0;
      v19 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\Setup\\Status\\ChildCompletion",
              0,
              (LPWSTR)&Class,
              0,
              0x20006u,
              0,
              &hKey,
              &dwDisposition);
      if ( !v19 )
      {
        v19 = RegSetValueExW(hKey, L"SetupFinalTasks", 0, 4u, (const BYTE *)&Data, 4u);
        RegCloseKey(hKey);
      }
      SetLastError(v19);
      if ( v19 )
      {
        v23 = GetLastError();
        v24 = v23 < 0;
        if ( v23 > 0 )
          v24 = 1;
        if ( !v24 )
        {
          updated = -2147467259;
          goto LABEL_38;
        }
        v25 = GetLastError();
        updated = v25;
        if ( v25 > 0 )
          updated = (unsigned __int16)v25 | 0x80070000;
      }
      else
      {
        updated = OrchestrateUpdateImageState(v21, v20, v22);
      }
      if ( updated >= 0 )
        goto LABEL_33;
LABEL_38:
      v11 = 503;
      goto LABEL_41;
    }
LABEL_40:
    v11 = 502;
    goto LABEL_41;
  }
LABEL_33:
  if ( a2 == 3 )
  {
    if ( *((_BYTE *)a1 + 16) )
    {
      v26 = UserOOBEController::s_PrepareForAuditModeOnReboot();
      updated = v26;
      if ( v26 < 0 )
      {
        UnattendLogW(1, L"Preparing audit mode failed [hr=0x%08X]", (unsigned int)v26);
        v7 = 182;
        goto LABEL_8;
      }
    }
  }
  else if ( a2 == 4 )
  {
    if ( *((_BYTE *)a1 + 16) )
    {
      v27 = UserOOBEController::s_PrepareForBootWinREOnReboot();
      updated = v27;
      if ( v27 < 0 )
      {
        UnattendLogW(1, L"Preparing WinRE boot failed [hr=0x%08X]", (unsigned int)v27);
        v7 = 187;
        goto LABEL_8;
      }
    }
  }
  v28 = UserOOBEController::s_ProcessUserRegKeys(a2);
  v29 = v28;
  if ( v28 < 0 )
  {
    UnattendLogW(1, L"Processing user reg keys failed [hr=0x%08X]", (unsigned int)v28);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v29,
      dwOptions);
  }
  v30 = UserOOBEController::s_DisableDefaultAccount();
  v31 = v30;
  if ( v30 < 0 )
  {
    UnattendLogW(1, L"Disabling default account failed [hr=0x%08X]", (unsigned int)v30);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v31,
      dwOptions);
  }
  if ( a2 == 1 && *((_BYTE *)a1 + 16) )
  {
    v32 = UserOOBEController::s_ScheduleRemoveRDXContent();
    v33 = v32;
    if ( v32 < 0 )
    {
      UnattendLogW(1, L"Reschedule delete rdx content failed [hr=0x%08X]", (unsigned int)v32);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)v33,
        dwOptions);
    }
    UserOOBEController::s_CleanupMachineRegValues();
    goto LABEL_55;
  }
  UserOOBEController::s_CleanupMachineRegValues();
  if ( (a2 & 0xFFFFFFFD) != 0 )
  {
LABEL_55:
    SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"RecoveryOOBEEnabled");
    goto LABEL_56;
  }
  v36 = SHRegSetBOOL(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
          L"RecoveryOOBEEnabled",
          1);
  v37 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x340,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v36,
      dwOptions);
    UnattendLogW(1, L"Enabling recovery OOBE failed [hr=0x%08X]", v37);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v37,
      dwOptionsa);
  }
LABEL_56:
  if ( v4 || a2 - 3 <= 1 )
  {
    v38 = UserOOBEController::Restart(a1);
    updated = v38;
    if ( v38 < 0 )
    {
      UnattendLogW(1, L"Restarting failed [hr=0x%08X]", (unsigned int)v38);
      v7 = 204;
      goto LABEL_8;
    }
  }
  else if ( UserOOBEController::s_HasProvisioned() )
  {
    v34 = RegFlushKey(HKEY_LOCAL_MACHINE);
    v35 = v34;
    if ( v34 )
    {
      UnattendLogW(1, L"Flushing LOCAL MACHINE hive failed [%d]", v34);
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)v35,
        dwOptions);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024320  mov     [rsp-38h+arg_18], rbx
0x180024325  push    rbp
0x180024326  push    rsi
0x180024327  push    rdi
0x180024328  push    r12
0x18002432a  push    r13
0x18002432c  push    r14
0x18002432e  push    r15
0x180024330  mov     rbp, rsp
0x180024333  sub     rsp, 50h
0x180024337  mov     edi, edx
0x180024339  mov     rsi, rcx
0x18002433c  mov     r8d, edx
0x18002433f  xor     ecx, ecx
0x180024341  lea     rdx, aUseroobecontro_1; "UserOOBEController::Exit() started [%d]"
0x180024348  call    UnattendLogW
0x18002434d  test    edi, 0FFFFFFFDh
0x180024353  mov     r12d, 1
0x180024359  setz    al
0x18002435c  cmp     edi, 4
0x18002435f  movzx   r14d, al
0x180024363  cmovz   r14d, r12d
0x180024367  cmp     edi, 3
0x18002436a  jnz     short loc_180024371
0x18002436c  call    ??$HandleEvent@$0BL@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<27,bool>(bool)
0x180024371  xor     r15d, r15d
0x180024374  cmp     [rsi+10h], r15b
0x180024378  jz      short loc_1800243BC
0x18002437a  cmp     edi, r12d
0x18002437d  setz    cl; bool
0x180024380  call    ?s_RemoveUserOOBEMonitorTask@UserOOBEController@@CAJ_N@Z; UserOOBEController::s_RemoveUserOOBEMonitorTask(bool)
0x180024385  mov     ebx, eax
0x180024387  test    eax, eax
0x180024389  jns     short loc_1800243BC
0x18002438b  mov     r8d, eax
0x18002438e  lea     rdx, aRemovingMonito; "Removing monitor task failed [hr=0x%08X"...
0x180024395  mov     ecx, r12d
0x180024398  call    UnattendLogW
0x18002439d  mov     edx, 0ABh; void *
0x1800243a2  mov     rcx, [rbp+38h]; this
0x1800243a6  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800243ad  mov     r9d, ebx; char *
0x1800243b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800243b5  mov     eax, ebx
0x1800243b7  jmp     loc_180024768
0x1800243bc  mov     r13, 0FFFFFFFF80000002h
0x1800243c3  test    r14b, r14b
0x1800243c6  jz      loc_18002458E
0x1800243cc  cmp     [rsi+10h], r15b
0x1800243d0  jz      loc_18002458E
0x1800243d6  call    ??$HandleEvent@$00_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<1,bool>(bool)
0x1800243db  call    OrchestrateBootCommand
0x1800243e0  mov     ebx, eax
0x1800243e2  test    eax, eax
0x1800243e4  jns     short loc_1800243F0
0x1800243e6  mov     edx, 1F5h
0x1800243eb  jmp     loc_1800245DE
0x1800243f0  lea     rax, [rbp+dwDisposition]
0x1800243f4  mov     [rbp+Data], r15d
0x1800243f8  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800243fd  lea     r9, Class; lpClass
0x180024404  lea     rax, [rbp+hKey]
0x180024408  mov     [rbp+hKey], r15
0x18002440c  mov     [rsp+50h+phkResult], rax; phkResult
0x180024411  lea     rdx, aSystemSetupSta_1; "System\\Setup\\Status\\ChildCompletion"
0x180024418  mov     [rsp+50h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002441d  xor     r8d, r8d; Reserved
0x180024420  mov     [rsp+50h+samDesired], 20006h; samDesired
0x180024428  mov     rcx, r13; hKey
0x18002442b  mov     [rsp+50h+dwOptions], r15d; dwOptions
0x180024430  mov     [rbp+dwDisposition], r15d
0x180024434  call    cs:__imp_RegCreateKeyExW
0x18002443a  mov     ebx, eax
0x18002443c  test    eax, eax
0x18002443e  jnz     short loc_180024475
0x180024440  mov     rcx, [rbp+hKey]; hKey
0x180024444  lea     rax, [rbp+Data]
0x180024448  mov     [rsp+50h+samDesired], 4; cbData
0x180024450  lea     r9d, [rbx+4]; dwType
0x180024454  xor     r8d, r8d; Reserved
0x180024457  mov     qword ptr [rsp+50h+dwOptions], rax; int
0x18002445c  lea     rdx, aOobeldrExe; "oobeldr.exe"
0x180024463  call    cs:__imp_RegSetValueExW
0x180024469  mov     rcx, [rbp+hKey]; hKey
0x18002446d  mov     ebx, eax
0x18002446f  call    cs:__imp_RegCloseKey
0x180024475  mov     ecx, ebx; dwErrCode
0x180024477  call    cs:__imp_SetLastError
0x18002447d  mov     r13d, 80070000h
0x180024483  test    ebx, ebx
0x180024485  jnz     short loc_180024490
0x180024487  call    ?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z; OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)
0x18002448c  mov     ebx, eax
0x18002448e  jmp     short loc_1800244BA
0x180024490  call    cs:__imp_GetLastError
0x180024496  test    eax, eax
0x180024498  jle     short loc_1800244A2
0x18002449a  movzx   eax, ax
0x18002449d  or      eax, r13d
0x1800244a0  test    eax, eax
0x1800244a2  jns     loc_1800245D4
0x1800244a8  call    cs:__imp_GetLastError
0x1800244ae  mov     ebx, eax
0x1800244b0  test    eax, eax
0x1800244b2  jle     short loc_1800244BA
0x1800244b4  movzx   ebx, ax
0x1800244b7  or      ebx, r13d
0x1800244ba  test    ebx, ebx
0x1800244bc  js      loc_1800245D9
0x1800244c2  lea     rax, [rbp+dwDisposition]
0x1800244c6  mov     [rbp+Data], r15d
0x1800244ca  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800244cf  lea     r9, Class; lpClass
0x1800244d6  lea     rax, [rbp+hKey]
0x1800244da  mov     [rbp+hKey], r15
0x1800244de  mov     [rsp+50h+phkResult], rax; phkResult
0x1800244e3  lea     rdx, aSystemSetupSta_1; "System\\Setup\\Status\\ChildCompletion"
0x1800244ea  mov     [rsp+50h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800244ef  xor     r8d, r8d; Reserved
0x1800244f2  mov     [rsp+50h+samDesired], 20006h; samDesired
0x1800244fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024501  mov     [rsp+50h+dwOptions], r15d; dwOptions
0x180024506  mov     [rbp+dwDisposition], r15d
0x18002450a  call    cs:__imp_RegCreateKeyExW
0x180024510  mov     ebx, eax
0x180024512  test    eax, eax
0x180024514  jnz     short loc_180024548
0x180024516  mov     rcx, [rbp+hKey]; hKey
0x18002451a  lea     r9d, [rax+4]; dwType
0x18002451e  lea     rax, [rbp+Data]
0x180024522  mov     [rsp+50h+samDesired], r9d; cbData
0x180024527  xor     r8d, r8d; Reserved
0x18002452a  mov     qword ptr [rsp+50h+dwOptions], rax; int
0x18002452f  lea     rdx, aSetupfinaltask; "SetupFinalTasks"
0x180024536  call    cs:__imp_RegSetValueExW
0x18002453c  mov     rcx, [rbp+hKey]; hKey
0x180024540  mov     ebx, eax
0x180024542  call    cs:__imp_RegCloseKey
0x180024548  mov     ecx, ebx; dwErrCode
0x18002454a  call    cs:__imp_SetLastError
0x180024550  test    ebx, ebx
0x180024552  jnz     short loc_18002455D
0x180024554  call    ?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z; OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)
0x180024559  mov     ebx, eax
0x18002455b  jmp     short loc_180024583
0x18002455d  call    cs:__imp_GetLastError
0x180024563  test    eax, eax
0x180024565  jle     short loc_18002456F
0x180024567  movzx   eax, ax
0x18002456a  or      eax, r13d
0x18002456d  test    eax, eax
0x18002456f  jns     short loc_1800245C8
0x180024571  call    cs:__imp_GetLastError
0x180024577  mov     ebx, eax
0x180024579  test    eax, eax
0x18002457b  jle     short loc_180024583
0x18002457d  movzx   ebx, ax
0x180024580  or      ebx, r13d
0x180024583  test    ebx, ebx
0x180024585  js      short loc_1800245CD
0x180024587  mov     r13, 0FFFFFFFF80000002h
0x18002458e  cmp     edi, 3
0x180024591  jnz     short loc_18002460D
0x180024593  cmp     [rsi+10h], r15b
0x180024597  jz      loc_18002463F
0x18002459d  call    ?s_PrepareForAuditModeOnReboot@UserOOBEController@@CAJXZ; UserOOBEController::s_PrepareForAuditModeOnReboot(void)
0x1800245a2  mov     ebx, eax
0x1800245a4  test    eax, eax
0x1800245a6  jns     loc_18002463F
0x1800245ac  mov     r8d, eax
0x1800245af  lea     rdx, aPreparingAudit; "Preparing audit mode failed [hr=0x%08X]"
0x1800245b6  mov     ecx, r12d
0x1800245b9  call    UnattendLogW
0x1800245be  mov     edx, 0B6h
0x1800245c3  jmp     loc_1800243A2
0x1800245c8  mov     ebx, 80004005h
0x1800245cd  mov     edx, 1F7h
0x1800245d2  jmp     short loc_1800245DE
0x1800245d4  mov     ebx, 80004005h
0x1800245d9  mov     edx, 1F6h; void *
0x1800245de  mov     rcx, [rbp+38h]; this
0x1800245e2  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800245e9  mov     r9d, ebx; char *
0x1800245ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800245f1  mov     r8d, ebx
0x1800245f4  lea     rdx, aPreparingReboo; "Preparing reboot failed [hr=0x%08X]"
0x1800245fb  mov     ecx, r12d
0x1800245fe  call    UnattendLogW
0x180024603  mov     edx, 0B1h
0x180024608  jmp     loc_1800243A2
0x18002460d  cmp     edi, 4
0x180024610  jnz     short loc_18002463F
0x180024612  cmp     [rsi+10h], r15b
0x180024616  jz      short loc_18002463F
0x180024618  call    ?s_PrepareForBootWinREOnReboot@UserOOBEController@@CAJXZ; UserOOBEController::s_PrepareForBootWinREOnReboot(void)
0x18002461d  mov     ebx, eax
0x18002461f  test    eax, eax
0x180024621  jns     short loc_18002463F
0x180024623  mov     r8d, eax
0x180024626  lea     rdx, aPreparingWinre; "Preparing WinRE boot failed [hr=0x%08X]"
0x18002462d  mov     ecx, r12d
0x180024630  call    UnattendLogW
0x180024635  mov     edx, 0BBh
0x18002463a  jmp     loc_1800243A2
0x18002463f  mov     ecx, edi
0x180024641  call    ?s_ProcessUserRegKeys@UserOOBEController@@CAJW4UserOOBEExitReason@@@Z; UserOOBEController::s_ProcessUserRegKeys(UserOOBEExitReason)
0x180024646  mov     ebx, eax
0x180024648  test    eax, eax
0x18002464a  jns     short loc_180024676
0x18002464c  mov     r8d, eax
0x18002464f  lea     rdx, aProcessingUser; "Processing user reg keys failed [hr=0x%"...
0x180024656  mov     ecx, r12d
0x180024659  call    UnattendLogW
0x18002465e  mov     rcx, [rbp+38h]; this
0x180024662  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180024669  mov     r9d, ebx; char *
0x18002466c  mov     edx, 0BFh; void *
0x180024671  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024676  call    ?s_DisableDefaultAccount@UserOOBEController@@CAJXZ; UserOOBEController::s_DisableDefaultAccount(void)
0x18002467b  mov     ebx, eax
0x18002467d  test    eax, eax
0x18002467f  jns     short loc_1800246AB
0x180024681  mov     r8d, eax
0x180024684  lea     rdx, aDisablingDefau; "Disabling default account failed [hr=0x"...
0x18002468b  mov     ecx, r12d
0x18002468e  call    UnattendLogW
0x180024693  mov     rcx, [rbp+38h]; this
0x180024697  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002469e  mov     r9d, ebx; char *
0x1800246a1  mov     edx, 0C0h; void *
0x1800246a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800246ab  cmp     edi, r12d
0x1800246ae  jnz     loc_180024780
0x1800246b4  cmp     [rsi+10h], r15b
0x1800246b8  jz      loc_180024780
0x1800246be  call    ?s_ScheduleRemoveRDXContent@UserOOBEController@@CAJXZ; UserOOBEController::s_ScheduleRemoveRDXContent(void)
0x1800246c3  mov     ebx, eax
0x1800246c5  test    eax, eax
0x1800246c7  jns     short loc_1800246F3
0x1800246c9  mov     r8d, eax
0x1800246cc  lea     rdx, aRescheduleDele; "Reschedule delete rdx content failed [h"...
0x1800246d3  mov     ecx, r12d
0x1800246d6  call    UnattendLogW
0x1800246db  mov     rcx, [rbp+38h]; this
0x1800246df  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800246e6  mov     r9d, ebx; char *
0x1800246e9  mov     edx, 0C4h; void *
0x1800246ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800246f3  call    ?s_CleanupMachineRegValues@UserOOBEController@@CAXXZ; UserOOBEController::s_CleanupMachineRegValues(void)
0x1800246f8  lea     r8, aRecoveryoobeen; "RecoveryOOBEEnabled"
0x1800246ff  mov     rcx, r13; hkey
0x180024702  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180024709  call    cs:__imp_SHDeleteValueW
0x18002470f  test    r14b, r14b
0x180024712  jnz     loc_1800247FB
0x180024718  lea     eax, [rdi-3]
0x18002471b  cmp     eax, r12d
0x18002471e  jbe     loc_1800247FB
0x180024724  call    ?s_HasProvisioned@UserOOBEController@@CA_NXZ; UserOOBEController::s_HasProvisioned(void)
0x180024729  test    al, al
0x18002472b  jz      short loc_180024766
0x18002472d  mov     rcx, r13; hKey
0x180024730  call    cs:__imp_RegFlushKey
0x180024736  mov     ebx, eax
0x180024738  test    eax, eax
0x18002473a  jz      short loc_180024766
0x18002473c  mov     r8d, eax
0x18002473f  lea     rdx, aFlushingLocalM; "Flushing LOCAL MACHINE hive failed [%d]"
0x180024746  mov     ecx, r12d
0x180024749  call    UnattendLogW
0x18002474e  mov     rcx, [rbp+38h]; this
0x180024752  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180024759  mov     r9d, ebx; char *
0x18002475c  mov     edx, 0D1h; void *
0x180024761  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180024766  xor     eax, eax
0x180024768  mov     rbx, [rsp+50h+arg_18]
0x180024770  add     rsp, 50h
0x180024774  pop     r15
0x180024776  pop     r14
0x180024778  pop     r13
0x18002477a  pop     r12
0x18002477c  pop     rdi
0x18002477d  pop     rsi
0x18002477e  pop     rbp
0x18002477f  retn
0x180024780  call    ?s_CleanupMachineRegValues@UserOOBEController@@CAXXZ; UserOOBEController::s_CleanupMachineRegValues(void)
0x180024785  test    edi, 0FFFFFFFDh
0x18002478b  jnz     loc_1800246F8
0x180024791  mov     r9d, r12d; int
0x180024794  lea     r8, aRecoveryoobeen; "RecoveryOOBEEnabled"
0x18002479b  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800247a2  mov     rcx, r13; HKEY
0x1800247a5  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800247aa  mov     ebx, eax
0x1800247ac  test    eax, eax
0x1800247ae  jns     loc_18002470F
0x1800247b4  mov     rcx, [rbp+38h]; this
0x1800247b8  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800247bf  mov     r9d, eax; char *
  ... truncated ...
```
