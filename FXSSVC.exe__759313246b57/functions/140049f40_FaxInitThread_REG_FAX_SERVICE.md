# FaxInitThread(_REG_FAX_SERVICE *)

- ea: `0x140049f40`
- end: `0x14004a8a4`
- name: `?FaxInitThread@@YAKPEAU_REG_FAX_SERVICE@@@Z`
- size: `2404`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140003b3c`
- `0x140003cd0`
- `0x140003e50`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14000bb38`
- `0x14000dd74`
- `0x140030038`
- `0x1400300f4`
- `0x14003417c`
- `0x140045da4`
- `0x1400483d4`
- `0x140049f40`
- `0x14004d270`
- `0x14004d358`
- `0x14004f428`
- `0x140050c6c`
- `0x140050e90`
- `0x140050f7c`
- `0x140051140`
- `0x1400602d4`
- `0x140060fac`
- `0x1400631cc`
- `0x140064674`
- `0x1400699d0`
- `0x1400749a0`
- `0x140074f18`
- `0x140081b74`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004a0af`
- `ADVAPI32!RegCloseKey` at `0x14004a1a5`
- `ADVAPI32!RegCloseKey` at `0x14004a0af`
- `ADVAPI32!RegCloseKey` at `0x14004a1a5`
- `KERNEL32!GetLastError` at `0x14004a003`
- `KERNEL32!GetLastError` at `0x14004a10c`
- `KERNEL32!GetLastError` at `0x14004a308`
- `KERNEL32!GetLastError` at `0x14004a3c9`
- `KERNEL32!GetLastError` at `0x14004a41f`
- `KERNEL32!GetLastError` at `0x14004a60e`
- `KERNEL32!GetLastError` at `0x14004a675`
- `KERNEL32!GetLastError` at `0x14004a6d0`
- `KERNEL32!GetLastError` at `0x14004a72e`
- `KERNEL32!GetLastError` at `0x14004a773`
- `KERNEL32!GetLastError` at `0x14004a7b8`
- `KERNEL32!GetLastError` at `0x14004a7fd`
- `KERNEL32!GetLastError` at `0x14004a003`
- `KERNEL32!GetLastError` at `0x14004a10c`
- `KERNEL32!GetLastError` at `0x14004a308`
- `KERNEL32!GetLastError` at `0x14004a3c9`
- `KERNEL32!GetLastError` at `0x14004a41f`
- `KERNEL32!GetLastError` at `0x14004a60e`
- `KERNEL32!GetLastError` at `0x14004a675`
- `KERNEL32!GetLastError` at `0x14004a6d0`
- `KERNEL32!GetLastError` at `0x14004a72e`
- `KERNEL32!GetLastError` at `0x14004a773`
- `KERNEL32!GetLastError` at `0x14004a7b8`
- `KERNEL32!GetLastError` at `0x14004a7fd`
- `KERNEL32!EnterCriticalSection` at `0x14004a541`
- `KERNEL32!EnterCriticalSection` at `0x14004a541`
- `KERNEL32!LeaveCriticalSection` at `0x14004a593`
- `KERNEL32!LeaveCriticalSection` at `0x14004a593`
- `KERNEL32!CreateEventW` at `0x14004a716`
- `KERNEL32!CreateEventW` at `0x14004a716`
- `KERNEL32!CreateWaitableTimerW` at `0x14004a6b8`
- `KERNEL32!CreateWaitableTimerW` at `0x14004a6b8`
- `USER32!SendMessageW` at `0x14004a863`
- `USER32!SendMessageW` at `0x14004a863`
- `USER32!FindWindowW` at `0x14004a842`
- `USER32!FindWindowW` at `0x14004a842`

## pseudocode

```c
__int64 __fastcall FaxInitThread(struct _REG_FAX_SERVICE *Parameter)
{
  CMapDeviceId *v2; // rcx
  CFaxAccountList *v3; // rdi
  HKEY v4; // rax
  HKEY v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // ebx
  CMapDeviceId *v8; // rcx
  HKEY v9; // rax
  HKEY v10; // rdi
  DWORD v11; // eax
  unsigned int v12; // ebx
  CMapDeviceId *v13; // rcx
  unsigned int v14; // eax
  DWORD updated; // ebx
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  DWORD v19; // r9d
  unsigned __int16 *v20; // rdx
  DWORD v21; // eax
  CMapDeviceId *v22; // rcx
  __int64 v23; // rdx
  struct _REG_FAX_SERVICE *v24; // rcx
  DWORD v25; // eax
  unsigned int v26; // edx
  DWORD v27; // eax
  CMapDeviceId *v28; // rcx
  DWORD v29; // eax
  struct _DEVICE_PROVIDER *v30; // rdx
  int v31; // r8d
  bool v32; // zf
  int v33; // eax
  DWORD_PTR *v34; // rbx
  DWORD_PTR *v35; // rcx
  COutboundRoutingGroupsMap *v36; // rcx
  COutboundRoutingGroupsMap *v37; // rcx
  CMapDeviceId *v38; // rcx
  __int64 v39; // rdx
  COutboundRulesMap *v40; // rcx
  COutboundRulesMap *v41; // rcx
  HWND WindowW; // rax
  char v44; // [rsp+20h] [rbp-40h]
  unsigned __int16 v45[14]; // [rsp+34h] [rbp-2Ch] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = g_pAccountList;
  if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v2 + 2), 56, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  v4 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax", 0, 0x20019u);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v3 + 4) = 1;
    EnumerateRegistryKeys((_DWORD)v4, (unsigned int)L"Accounts", 0, (unsigned int)RegEnumAccountsCB, 0);
    RegCloseKey(v5);
    goto LABEL_20;
  }
  LastError = GetLastError();
  v7 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Fax",
      LastError);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v8 == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_25;
    if ( (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 76, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v7);
LABEL_20:
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( v8 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v8 + 2), 81, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
LABEL_25:
  v9 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Accounts", 0, 0x20019u);
  v10 = v9;
  if ( v9 )
  {
    v14 = CFaxAccount::Load(g_pAccountDefaults, v9, 0);
    v12 = v14;
    if ( v14
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v14);
    }
    RegCloseKey(v10);
    goto LABEL_36;
  }
  v11 = GetLastError();
  v12 = v11;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Fax\\Accounts",
      v11);
LABEL_36:
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12
    && v13 != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v13 + 28) & 4) != 0
    && *((_BYTE *)v13 + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)v13 + 2), 77, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v12);
  }
  updated = InitializeServerQuota();
  if ( updated )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 78;
LABEL_47:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, updated);
LABEL_48:
    v45[0] = 0;
    v18 = StringCchPrintfW(v45, 0xCu, L"%ld", updated);
    v19 = -1073709780;
LABEL_49:
    v20 = v45;
    if ( v18 < 0 )
      LOBYTE(v20) = 0;
    FaxLog(1u, 1u, 1u, v19, (char)v20);
    goto LABEL_160;
  }
  v21 = InitializeServerSecurity();
  updated = v21;
  if ( v21 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_160;
    }
    v23 = 79;
    goto LABEL_57;
  }
  if ( !(unsigned int)LoadDeviceProviders(Parameter) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    }
  }
  if ( !(unsigned int)InitializeJobManager(v24) )
  {
    updated = 31;
    goto LABEL_160;
  }
  if ( !(unsigned int)InitializeRouting(Parameter) )
  {
    v21 = GetLastError();
    updated = v21;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_160;
    }
    v23 = 81;
LABEL_57:
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v21);
    goto LABEL_160;
  }
  v25 = TapiInitialize(Parameter);
  updated = v25;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v25);
    }
    v45[0] = 0;
    v18 = StringCchPrintfW(v45, 0xCu, L"%ld", updated);
    v19 = -1073709779;
    goto LABEL_49;
  }
  if ( !(unsigned int)InitializeDeviceProvidersConfiguration()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v27 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v27);
  }
  g_dwDeviceCount += CreateVirtualDevices(Parameter, v26);
  if ( !(unsigned int)InitializeDeviceProviders() )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_87;
    }
    v29 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v29);
  }
  v28 = WPP_GLOBAL_Control;
LABEL_87:
  v30 = g_DeviceProvidersListHead;
  v31 = 0;
  if ( g_DeviceProvidersListHead == (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead )
    goto LABEL_94;
  do
  {
    v32 = *((_DWORD *)v30 + 4) == 0;
    v33 = v31 + 1;
    v30 = *(struct _DEVICE_PROVIDER **)v30;
    if ( !v32 )
      v33 = v31;
    v31 = v33;
  }
  while ( v30 != (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead );
  if ( !v33 )
  {
LABEL_94:
    if ( v28 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 && *((_BYTE *)v28 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v28 + 2), 85, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    FaxLog(1u, 2u, 0, 0x80007D27, v44);
    v28 = WPP_GLOBAL_Control;
  }
  if ( !g_dwDeviceCount )
  {
    if ( v28 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 && *((_BYTE *)v28 + 25) >= 3u )
      WPP_SF_(*((_QWORD *)v28 + 2), 86, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    FaxLog(1u, 2u, 0, 0x80007D1A, v44);
  }
  UpdateManualAnswerDevice();
  updated = UpdateDevicesFlags();
  if ( updated )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 87;
    goto LABEL_47;
  }
  EnterCriticalSection(&g_CsLine);
  v34 = (DWORD_PTR *)g_TapiLinesListHead;
  if ( g_TapiLinesListHead && (DWORD_PTR *)g_TapiLinesListHead != &g_TapiLinesListHead )
  {
    do
    {
      v35 = v34;
      v34 = (DWORD_PTR *)*v34;
      UpdateVirtualDeviceSendAndReceiveStatus(
        (struct _LINE_INFO *)v35,
        *((_DWORD *)v35 + 19) & 2,
        *((_DWORD *)v35 + 19) & 1);
    }
    while ( v34 != &g_TapiLinesListHead );
  }
  LeaveCriticalSection(&g_CsLine);
  UpdateReceiveEnabledDevicesCount();
  updated = COutboundRoutingGroupsMap::Load(v36);
  if ( updated )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_117;
    }
    v39 = 88;
LABEL_116:
    WPP_SF_d(*((_QWORD *)v38 + 2), v39, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, updated);
LABEL_117:
    v45[0] = 0;
    v18 = StringCchPrintfW(v45, 0xCu, L"%ld", updated);
    v19 = -1073709759;
    goto LABEL_49;
  }
  if ( !(unsigned int)COutboundRoutingGroupsMap::UpdateAllDevicesGroup(v37) )
  {
    updated = GetLastError();
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_117;
    }
    v39 = 89;
    goto LABEL_116;
  }
  updated = COutboundRulesMap::Load(v40);
  if ( updated )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_117;
    }
    v39 = 90;
    goto LABEL_116;
  }
  if ( !(unsigned int)COutboundRulesMap::CreateDefaultRule(v41) )
  {
    updated = GetLastError();
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_117;
    }
    v39 = 91;
    goto LABEL_116;
  }
  g_hQueueTimer = CreateWaitableTimerW(0, 0, 0);
  if ( !g_hQueueTimer )
  {
    updated = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 92;
    goto LABEL_47;
  }
  g_hJobQueueEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hJobQueueEvent )
  {
    updated = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 93;
    goto LABEL_47;
  }
  if ( !(unsigned int)CreateStatusThreads() )
  {
    updated = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 94;
    goto LABEL_47;
  }
  if ( !(unsigned int)CreateTapiThread() )
  {
    updated = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 95;
    goto LABEL_47;
  }
  if ( !(unsigned int)CreateJobQueueThread() )
  {
    updated = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 96;
    goto LABEL_47;
  }
  WindowW = FindWindowW(L"SystemTray_Main", 0);
  if ( WindowW )
    SendMessageW(WindowW, 0x64u, 0, 1);
LABEL_160:
  if ( Parameter )
    FreeFaxRegistry(Parameter);
  return updated;
}

```

## disassembly

```asm
0x140049f40  mov     [rsp-28h+arg_8], rbx
0x140049f45  mov     [rsp-28h+arg_10], rsi
0x140049f4a  push    rbp
0x140049f4b  push    rdi
0x140049f4c  push    r12
0x140049f4e  push    r13
0x140049f50  push    r15
0x140049f52  mov     rbp, rsp
0x140049f55  sub     rsp, 60h
0x140049f59  mov     rax, cs:__security_cookie
0x140049f60  xor     rax, rsp
0x140049f63  mov     [rbp+var_10], rax
0x140049f67  mov     rsi, rcx
0x140049f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140049f71  lea     r13, WPP_GLOBAL_Control
0x140049f78  mov     r15b, 4
0x140049f7b  cmp     rcx, r13
0x140049f7e  jz      short loc_140049FA8
0x140049f80  test    [rcx+1Ch], r15b
0x140049f84  jz      short loc_140049FA8
0x140049f86  cmp     byte ptr [rcx+19h], 5
0x140049f8a  jb      short loc_140049FA8
0x140049f8c  mov     rcx, [rcx+10h]
0x140049f90  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140049f97  mov     edx, 4Bh ; 'K'
0x140049f9c  call    WPP_SF_
0x140049fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140049fa8  mov     rdi, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x140049faf  cmp     rcx, r13
0x140049fb2  jz      short loc_140049FD5
0x140049fb4  test    [rcx+1Ch], r15b
0x140049fb8  jz      short loc_140049FD5
0x140049fba  cmp     byte ptr [rcx+19h], 5
0x140049fbe  jb      short loc_140049FD5
0x140049fc0  mov     rcx, [rcx+10h]
0x140049fc4  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x140049fcb  mov     edx, 38h ; '8'
0x140049fd0  call    WPP_SF_
0x140049fd5  mov     r9d, 20019h
0x140049fdb  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x140049fe2  xor     r8d, r8d
0x140049fe5  mov     rcx, 0FFFFFFFF80000002h
0x140049fec  call    OpenRegistryKey
0x140049ff1  mov     rbx, rax
0x140049ff4  mov     r12d, 2
0x140049ffa  test    rax, rax
0x140049ffd  jnz     loc_14004A083
0x14004a003  call    cs:__imp_GetLastError
0x14004a00a  nop     dword ptr [rax+rax+00h]
0x14004a00f  mov     ebx, eax
0x14004a011  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a018  cmp     rcx, r13
0x14004a01b  jz      short loc_14004A050
0x14004a01d  test    [rcx+1Ch], r15b
0x14004a021  jz      short loc_14004A050
0x14004a023  cmp     [rcx+19h], r12b
0x14004a027  jb      short loc_14004A050
0x14004a029  mov     rcx, [rcx+10h]
0x14004a02d  lea     edx, [r12+37h]
0x14004a032  lea     r9, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14004a039  mov     dword ptr [rsp+60h+var_40], eax
0x14004a03d  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004a044  call    WPP_SF_Sd
0x14004a049  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a050  test    ebx, ebx
0x14004a052  jz      short loc_14004A0C2
0x14004a054  cmp     rcx, r13
0x14004a057  jz      loc_14004A0E8
0x14004a05d  test    [rcx+1Ch], r15b
0x14004a061  jz      short loc_14004A0C2
0x14004a063  cmp     [rcx+19h], r12b
0x14004a067  jb      short loc_14004A0C2
0x14004a069  mov     rcx, [rcx+10h]
0x14004a06d  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004a074  mov     edx, 4Ch ; 'L'
0x14004a079  mov     r9d, ebx
0x14004a07c  call    WPP_SF_d
0x14004a081  jmp     short loc_14004A0BB
0x14004a083  lea     r9, RegEnumAccountsCB
0x14004a08a  mov     dword ptr [rdi+10h], 1
0x14004a091  xor     r8d, r8d
0x14004a094  mov     qword ptr [rsp+60h+var_40], 0
0x14004a09d  lea     rdx, aAccounts; "Accounts"
0x14004a0a4  mov     rcx, rbx
0x14004a0a7  call    EnumerateRegistryKeys
0x14004a0ac  mov     rcx, rbx; hKey
0x14004a0af  call    cs:__imp_RegCloseKey
0x14004a0b6  nop     dword ptr [rax+rax+00h]
0x14004a0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a0c2  cmp     rcx, r13
0x14004a0c5  jz      short loc_14004A0E8
0x14004a0c7  test    [rcx+1Ch], r15b
0x14004a0cb  jz      short loc_14004A0E8
0x14004a0cd  cmp     byte ptr [rcx+19h], 5
0x14004a0d1  jb      short loc_14004A0E8
0x14004a0d3  mov     rcx, [rcx+10h]
0x14004a0d7  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004a0de  mov     edx, 51h ; 'Q'
0x14004a0e3  call    WPP_SF_
0x14004a0e8  mov     r9d, 20019h
0x14004a0ee  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Fax\\Accounts"
0x14004a0f5  xor     r8d, r8d
0x14004a0f8  mov     rcx, 0FFFFFFFF80000002h
0x14004a0ff  call    OpenRegistryKey
0x14004a104  mov     rdi, rax
0x14004a107  test    rax, rax
0x14004a10a  jnz     short loc_14004A15A
0x14004a10c  call    cs:__imp_GetLastError
0x14004a113  nop     dword ptr [rax+rax+00h]
0x14004a118  mov     ebx, eax
0x14004a11a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a121  cmp     rcx, r13
0x14004a124  jz      loc_14004A1B8
0x14004a12a  test    [rcx+1Ch], r15b
0x14004a12e  jz      loc_14004A1B8
0x14004a134  cmp     [rcx+19h], r12b
0x14004a138  jb      short loc_14004A1B8
0x14004a13a  mov     rcx, [rcx+10h]
0x14004a13e  lea     edx, [rdi+52h]
0x14004a141  lea     r9, aSoftwareMicros_10; "Software\\Microsoft\\Fax\\Accounts"
0x14004a148  mov     dword ptr [rsp+60h+var_40], eax
0x14004a14c  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004a153  call    WPP_SF_Sd
0x14004a158  jmp     short loc_14004A1B1
0x14004a15a  mov     rcx, cs:?g_pAccountDefaults@@3PEAVCFaxAccount@@EA; this
0x14004a161  xor     r8d, r8d; void *
0x14004a164  mov     rdx, rdi; HKEY
0x14004a167  call    ?Load@CFaxAccount@@QEAAKPEAUHKEY__@@PEAX@Z; CFaxAccount::Load(HKEY__ *,void *)
0x14004a16c  mov     ebx, eax
0x14004a16e  test    eax, eax
0x14004a170  jz      short loc_14004A1A2
0x14004a172  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a179  cmp     rcx, r13
0x14004a17c  jz      short loc_14004A1A2
0x14004a17e  test    [rcx+1Ch], r15b
0x14004a182  jz      short loc_14004A1A2
0x14004a184  cmp     [rcx+19h], r12b
0x14004a188  jb      short loc_14004A1A2
0x14004a18a  mov     rcx, [rcx+10h]
0x14004a18e  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004a195  mov     edx, 53h ; 'S'
0x14004a19a  mov     r9d, eax
0x14004a19d  call    WPP_SF_d
0x14004a1a2  mov     rcx, rdi; hKey
0x14004a1a5  call    cs:__imp_RegCloseKey
0x14004a1ac  nop     dword ptr [rax+rax+00h]
0x14004a1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a1b8  test    ebx, ebx
0x14004a1ba  jz      short loc_14004A1EA
0x14004a1bc  cmp     rcx, r13
0x14004a1bf  jz      short loc_14004A1EA
0x14004a1c1  test    [rcx+1Ch], r15b
0x14004a1c5  jz      short loc_14004A1EA
0x14004a1c7  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004a1ce  cmp     [rcx+19h], r12b
0x14004a1d2  jb      short loc_14004A1F1
0x14004a1d4  mov     rcx, [rcx+10h]
0x14004a1d8  mov     edx, 4Dh ; 'M'
0x14004a1dd  mov     r9d, ebx
0x14004a1e0  mov     r8, rdi
0x14004a1e3  call    WPP_SF_d
0x14004a1e8  jmp     short loc_14004A1F1
0x14004a1ea  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004a1f1  call    ?InitializeServerQuota@@YAKXZ; InitializeServerQuota(void)
0x14004a1f6  mov     ebx, eax
0x14004a1f8  test    eax, eax
0x14004a1fa  jz      short loc_14004A270
0x14004a1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a203  cmp     rcx, r13
0x14004a206  jz      short loc_14004A228
0x14004a208  test    [rcx+1Ch], r15b
0x14004a20c  jz      short loc_14004A228
0x14004a20e  cmp     [rcx+19h], r12b
0x14004a212  jb      short loc_14004A228
0x14004a214  mov     edx, 4Eh ; 'N'
0x14004a219  mov     rcx, [rcx+10h]
0x14004a21d  mov     r9d, ebx
0x14004a220  mov     r8, rdi
0x14004a223  call    WPP_SF_d
0x14004a228  xor     eax, eax
0x14004a22a  mov     [rbp+var_30], ebx
0x14004a22d  mov     r9d, ebx
0x14004a230  mov     [rbp+var_2C], ax
0x14004a234  lea     r8, aLd; "%ld"
0x14004a23b  lea     rcx, [rbp+var_2C]; unsigned __int16 *
0x14004a23f  lea     edx, [rax+0Ch]; unsigned __int64
0x14004a242  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004a247  mov     r9d, 0C0007D2Ch
0x14004a24d  xor     ecx, ecx
0x14004a24f  lea     rdx, [rbp+var_2C]
0x14004a253  test    eax, eax
0x14004a255  cmovs   rdx, rcx
0x14004a259  mov     qword ptr [rsp+60h+var_40], rdx
0x14004a25e  lea     edx, [rcx+1]
0x14004a261  mov     ecx, edx
0x14004a263  mov     r8d, edx
0x14004a266  call    FaxLog
0x14004a26b  jmp     loc_14004A86F
0x14004a270  call    ?InitializeServerSecurity@@YAKXZ; InitializeServerSecurity(void)
0x14004a275  mov     ebx, eax
0x14004a277  test    eax, eax
0x14004a279  jz      short loc_14004A2B8
0x14004a27b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a282  cmp     rcx, r13
0x14004a285  jz      loc_14004A86F
0x14004a28b  test    [rcx+1Ch], r15b
0x14004a28f  jz      loc_14004A86F
0x14004a295  cmp     [rcx+19h], r12b
0x14004a299  jb      loc_14004A86F
0x14004a29f  mov     edx, 4Fh ; 'O'
0x14004a2a4  mov     rcx, [rcx+10h]
0x14004a2a8  mov     r9d, eax
0x14004a2ab  mov     r8, rdi
0x14004a2ae  call    WPP_SF_d
0x14004a2b3  jmp     loc_14004A86F
0x14004a2b8  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x14004a2bb  call    ?LoadDeviceProviders@@YAHPEAU_REG_FAX_SERVICE@@@Z; LoadDeviceProviders(_REG_FAX_SERVICE *)
0x14004a2c0  test    eax, eax
0x14004a2c2  jnz     short loc_14004A2EB
0x14004a2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a2cb  cmp     rcx, r13
0x14004a2ce  jz      short loc_14004A2EB
0x14004a2d0  test    [rcx+1Ch], r15b
0x14004a2d4  jz      short loc_14004A2EB
0x14004a2d6  cmp     [rcx+19h], r12b
0x14004a2da  jb      short loc_14004A2EB
0x14004a2dc  mov     rcx, [rcx+10h]
0x14004a2e0  lea     edx, [rax+50h]
0x14004a2e3  mov     r8, rdi
0x14004a2e6  call    WPP_SF_
0x14004a2eb  call    ?InitializeJobManager@@YAHPEAU_REG_FAX_SERVICE@@@Z; InitializeJobManager(_REG_FAX_SERVICE *)
0x14004a2f0  test    eax, eax
0x14004a2f2  jnz     short loc_14004A2FC
0x14004a2f4  lea     ebx, [rax+1Fh]
0x14004a2f7  jmp     loc_14004A86F
0x14004a2fc  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x14004a2ff  call    ?InitializeRouting@@YAHPEAU_REG_FAX_SERVICE@@@Z; InitializeRouting(_REG_FAX_SERVICE *)
0x14004a304  test    eax, eax
0x14004a306  jnz     short loc_14004A344
0x14004a308  call    cs:__imp_GetLastError
0x14004a30f  nop     dword ptr [rax+rax+00h]
0x14004a314  mov     ebx, eax
0x14004a316  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a31d  cmp     rcx, r13
0x14004a320  jz      loc_14004A86F
0x14004a326  test    [rcx+1Ch], r15b
0x14004a32a  jz      loc_14004A86F
0x14004a330  cmp     [rcx+19h], r12b
0x14004a334  jb      loc_14004A86F
0x14004a33a  mov     edx, 51h ; 'Q'
0x14004a33f  jmp     loc_14004A2A4
0x14004a344  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x14004a347  call    ?TapiInitialize@@YAKPEAU_REG_FAX_SERVICE@@@Z; TapiInitialize(_REG_FAX_SERVICE *)
0x14004a34c  mov     ebx, eax
0x14004a34e  test    eax, eax
0x14004a350  jz      short loc_14004A3A8
0x14004a352  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a359  cmp     rcx, r13
0x14004a35c  jz      short loc_14004A37E
0x14004a35e  test    [rcx+1Ch], r15b
0x14004a362  jz      short loc_14004A37E
0x14004a364  cmp     [rcx+19h], r12b
0x14004a368  jb      short loc_14004A37E
0x14004a36a  mov     rcx, [rcx+10h]
0x14004a36e  mov     edx, 52h ; 'R'
0x14004a373  mov     r9d, eax
0x14004a376  mov     r8, rdi
0x14004a379  call    WPP_SF_d
0x14004a37e  xor     eax, eax
0x14004a380  mov     [rbp+var_30], ebx
0x14004a383  mov     r9d, ebx
0x14004a386  mov     [rbp+var_2C], ax
0x14004a38a  lea     r8, aLd; "%ld"
0x14004a391  lea     rcx, [rbp+var_2C]; unsigned __int16 *
0x14004a395  lea     edx, [rax+0Ch]; unsigned __int64
0x14004a398  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004a39d  mov     r9d, 0C0007D2Dh
0x14004a3a3  jmp     loc_14004A24D
0x14004a3a8  call    ?InitializeDeviceProvidersConfiguration@@YAHXZ; InitializeDeviceProvidersConfiguration(void)
0x14004a3ad  test    eax, eax
0x14004a3af  jnz     short loc_14004A3F0
0x14004a3b1  mov     rax, cs:WPP_GLOBAL_Control
0x14004a3b8  cmp     rax, r13
0x14004a3bb  jz      short loc_14004A3F0
0x14004a3bd  test    [rax+1Ch], r15b
0x14004a3c1  jz      short loc_14004A3F0
0x14004a3c3  cmp     [rax+19h], r12b
0x14004a3c7  jb      short loc_14004A3F0
0x14004a3c9  call    cs:__imp_GetLastError
0x14004a3d0  nop     dword ptr [rax+rax+00h]
0x14004a3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3dc  mov     edx, 53h ; 'S'
0x14004a3e1  mov     r9d, eax
0x14004a3e4  mov     r8, rdi
0x14004a3e7  mov     rcx, [rcx+10h]
0x14004a3eb  call    WPP_SF_d
0x14004a3f0  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x14004a3f3  call    ?CreateVirtualDevices@@YAKPEAU_REG_FAX_SERVICE@@K@Z; CreateVirtualDevices(_REG_FAX_SERVICE *,ulong)
0x14004a3f8  add     cs:?g_dwDeviceCount@@3KA, eax; ulong g_dwDeviceCount
0x14004a3fe  call    ?InitializeDeviceProviders@@YAHXZ; InitializeDeviceProviders(void)
  ... truncated ...
```
