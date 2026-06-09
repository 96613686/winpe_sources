# ServiceMain

- ea: `0x18002d530`
- end: `0x18002d958`
- name: `ServiceMain`
- size: `1064`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800065c0`
- `0x180006890`
- `0x18000beb4`
- `0x18000c920`
- `0x18000ce80`
- `0x18000d904`
- `0x180011030`
- `0x180011438`
- `0x180022b7c`
- `0x1800296a0`
- `0x18002d530`
- `0x18002da6c`
- `0x18002dd20`
- `0x18002f09c`
- `0x180034010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002d596`
- `ntdll!DbgPrint` at `0x18002d5ab`
- `ntdll!DbgPrint` at `0x18002d596`
- `ntdll!DbgPrint` at `0x18002d5ab`
- `ntdll!RtlDeregisterWait` at `0x18002d680`
- `ntdll!RtlDeregisterWait` at `0x18002d680`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002d800`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002d800`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d5f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d5f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d7b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d69e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d69e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d65b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d65b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d60d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d6ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d60d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d6ae`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002d71f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002d71f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d6ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d6ea`
- `USERENV!RegisterGPNotification` at `0x18002d6c9`
- `USERENV!RegisterGPNotification` at `0x18002d6c9`

## string_xrefs

- `0x18002d75f`: `WKSSVC failed with WsUpdateStatus %x\n`
- `0x18002d7e8`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\LanmanWorkstation`
- `0x18002d5a4`: `WKSSVC ServiceMain returned with %x\n`

## pseudocode

```c
__int64 ServiceMain()
{
  unsigned int LastError; // ebx
  HANDLE EventW; // rax
  HANDLE v3; // rax
  unsigned int updated; // eax
  DWORD v5; // eax
  int PersistedStateLocation; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // [rsp+80h] [rbp+18h] BYREF

  WsInitState = 0;
  WsIsTerminationHandlerRunning = 0;
  WsWorkerCriticalSectionInitialized = 0;
  RegNotifyInfo = 0;
  dword_18004E540 = 0;
  xmmword_18004E548 = 0;
  if ( (unsigned int)WitnessInitialize() )
    WitnessTerminate();
  else
    WitnessClientEngineInitialized = 1;
  LastError = WsInitializeWorkstation();
  if ( LastError )
  {
    DbgPrint("WKSSVC failed to initialize workstation %x\n", (unsigned int)WsInitState);
LABEL_6:
    WsInitializeStatusError = LastError;
    DbgPrint("WKSSVC ServiceMain returned with %x\n", LastError);
    return WsTerminationNotify(0, 0);
  }
  LastError = WsAllocConfigName();
  if ( LastError )
    goto LABEL_6;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegPathToWatch, 0, 0x20019u, &ConfigHandle);
  if ( LastError )
    goto LABEL_6;
  ConfigHandleOpened = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  RegistryChangeEvent = EventW;
  if ( !EventW )
    goto LABEL_10;
  RegNotifyInfo = (__int64)EventW;
  *((_QWORD *)&xmmword_18004E548 + 1) = ConfigHandle;
  dword_18004E540 = -1;
  *(_QWORD *)&xmmword_18004E548 = 0;
  EnterCriticalSection(&WsWorkerCriticalSection);
  if ( !(unsigned int)WsReInitChangeNotify(&RegNotifyInfo) )
  {
    LastError = GetLastError();
    RtlDeregisterWait(TerminateWorkItem);
    TerminateWorkItem = 0;
    LeaveCriticalSection(&WsWorkerCriticalSection);
    goto LABEL_6;
  }
  LeaveCriticalSection(&WsWorkerCriticalSection);
  v3 = CreateEventW(0, 0, 0, 0);
  MachineGroupPolicyChangeEvent = v3;
  if ( !v3 )
    goto LABEL_10;
  if ( RegisterGPNotification(v3, 1) )
  {
    RegisteredForMachineGroupPolicyChangeNotifications = 1;
    if ( RegisterWaitForSingleObject(
           &MachineGroupPolicyChangeWaitObject,
           MachineGroupPolicyChangeEvent,
           WsOnMachineGroupPolicyChanged,
           0,
           0xFFFFFFFF,
           0) )
    {
      WaitingForMachineGroupPolicyChanges = 1;
      goto LABEL_19;
    }
LABEL_10:
    LastError = GetLastError();
    goto LABEL_6;
  }
  LastError = GetLastError();
  if ( LastError != 1 )
    goto LABEL_6;
  CloseHandle(MachineGroupPolicyChangeEvent);
  MachineGroupPolicyChangeEvent = 0;
LABEL_19:
  WsGlobalData.dwCurrentState = 4;
  WsGlobalData.dwControlsAccepted = 67;
  *(_QWORD *)&WsGlobalData.dwCheckPoint = 0;
  updated = WsUpdateStatus();
  LastError = updated;
  if ( updated )
  {
    WsInitializeStatusError = updated;
    DbgPrint("WKSSVC failed with WsUpdateStatus %x\n", updated);
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(_QWORD, _QWORD), _QWORD, int))(WsLmsvcsGlobalData + 192))(
         &TerminateWorkItem,
         L"LanmanWorkstation",
         hHandle,
         WsTerminationNotify,
         0,
         24);
  LastError = v5;
  if ( v5 )
  {
    SetLastError(v5);
    DbgPrint("WKSSVC/RegisterStopCallback failed. Error: %d\n", LastError);
    goto LABEL_6;
  }
  v9 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"LanmanWorkstation",
                             0,
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanWorkstation",
                             0,
                             WsData,
                             260,
                             &v9);
  if ( PersistedStateLocation < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 10;
    goto LABEL_28;
  }
  PersistedStateLocation = RtlStringCchPrintfW(&Path, 260, L"%ws\\%ws", WsData, L"ClientCertificateMappings");
  if ( PersistedStateLocation < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 11;
    goto LABEL_28;
  }
  PersistedStateLocation = WsQueryRegistrySubkeySecurityDescriptor(&pSecurityDescriptor, WsData);
  LastError = PersistedStateLocation;
  if ( PersistedStateLocation )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 12;
    goto LABEL_28;
  }
  PersistedStateLocation = WsRestoreCertificateMappings();
  LastError = PersistedStateLocation;
  if ( PersistedStateLocation )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_6;
    }
    v8 = 13;
LABEL_28:
    WPP_SF_d(v7[2], v8, WPP_31e0dc789b9f3c2c04382f436cbfec2a_Traceguids, (unsigned int)PersistedStateLocation);
    goto LABEL_6;
  }
  WsRestoreGlobalMappingsFromRegistry();
  return WJInitializeWorkplaceJoin();
}

```

## disassembly

```asm
0x18002d530  push    rbx
0x18002d532  push    rbp
0x18002d533  push    rsi
0x18002d534  push    rdi
0x18002d535  sub     rsp, 48h
0x18002d539  xor     edi, edi
0x18002d53b  xorps   xmm0, xmm0
0x18002d53e  mov     cs:WsInitState, edi
0x18002d544  mov     cs:WsIsTerminationHandlerRunning, edi
0x18002d54a  mov     cs:WsWorkerCriticalSectionInitialized, edi
0x18002d550  mov     cs:RegNotifyInfo, rdi
0x18002d557  mov     cs:dword_18004E540, edi
0x18002d55d  movdqu  cs:xmmword_18004E548, xmm0
0x18002d565  call    WitnessInitialize
0x18002d56a  lea     esi, [rdi+1]
0x18002d56d  test    eax, eax
0x18002d56f  jz      short loc_18002D578
0x18002d571  call    WitnessTerminate
0x18002d576  jmp     short loc_18002D57E
0x18002d578  mov     cs:WitnessClientEngineInitialized, esi
0x18002d57e  call    WsInitializeWorkstation
0x18002d583  mov     ebx, eax
0x18002d585  test    eax, eax
0x18002d587  jz      short loc_18002D5C3
0x18002d589  mov     edx, cs:WsInitState
0x18002d58f  lea     rcx, aWkssvcFailedTo_0; "WKSSVC failed to initialize workstation"...
0x18002d596  call    cs:__imp_DbgPrint
0x18002d59c  mov     edx, ebx
0x18002d59e  mov     cs:WsInitializeStatusError, ebx
0x18002d5a4  lea     rcx, aWkssvcServicem; "WKSSVC ServiceMain returned with %x\n"
0x18002d5ab  call    cs:__imp_DbgPrint
0x18002d5b1  xor     edx, edx
0x18002d5b3  xor     ecx, ecx
0x18002d5b5  call    WsTerminationNotify
0x18002d5ba  add     rsp, 48h
0x18002d5be  pop     rdi
0x18002d5bf  pop     rsi
0x18002d5c0  pop     rbp
0x18002d5c1  pop     rbx
0x18002d5c2  retn
0x18002d5c3  call    WsAllocConfigName
0x18002d5c8  mov     ebx, eax
0x18002d5ca  test    eax, eax
0x18002d5cc  jnz     short loc_18002D59C
0x18002d5ce  mov     rdx, cs:RegPathToWatch; lpSubKey
0x18002d5d5  lea     rax, ConfigHandle
0x18002d5dc  mov     r9d, 20019h; samDesired
0x18002d5e2  mov     [rsp+68h+phkResult], rax; phkResult
0x18002d5e7  xor     r8d, r8d; ulOptions
0x18002d5ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d5f1  call    cs:__imp_RegOpenKeyExW
0x18002d5f7  mov     ebx, eax
0x18002d5f9  test    eax, eax
0x18002d5fb  jnz     short loc_18002D59C
0x18002d5fd  xor     r9d, r9d; lpName
0x18002d600  mov     cs:ConfigHandleOpened, esi
0x18002d606  xor     r8d, r8d; bInitialState
0x18002d609  xor     edx, edx; bManualReset
0x18002d60b  xor     ecx, ecx; lpEventAttributes
0x18002d60d  call    cs:__imp_CreateEventW
0x18002d613  mov     cs:RegistryChangeEvent, rax
0x18002d61a  test    rax, rax
0x18002d61d  jnz     short loc_18002D62C
0x18002d61f  call    cs:__imp_GetLastError
0x18002d625  mov     ebx, eax
0x18002d627  jmp     loc_18002D59C
0x18002d62c  mov     cs:RegNotifyInfo, rax
0x18002d633  lea     rbp, WsWorkerCriticalSection
0x18002d63a  mov     rax, cs:ConfigHandle
0x18002d641  or      ebx, 0FFFFFFFFh
0x18002d644  mov     rcx, rbp; lpCriticalSection
0x18002d647  mov     qword ptr cs:xmmword_18004E548+8, rax
0x18002d64e  mov     cs:dword_18004E540, ebx
0x18002d654  mov     qword ptr cs:xmmword_18004E548, rdi
0x18002d65b  call    cs:__imp_EnterCriticalSection
0x18002d661  lea     rcx, RegNotifyInfo; pvContext
0x18002d668  call    WsReInitChangeNotify
0x18002d66d  test    eax, eax
0x18002d66f  jnz     short loc_18002D69B
0x18002d671  call    cs:__imp_GetLastError
0x18002d677  mov     rcx, cs:TerminateWorkItem; hWaitHandle
0x18002d67e  mov     ebx, eax
0x18002d680  call    cs:__imp_RtlDeregisterWait
0x18002d686  mov     rcx, rbp; lpCriticalSection
0x18002d689  mov     cs:TerminateWorkItem, rdi
0x18002d690  call    cs:__imp_LeaveCriticalSection
0x18002d696  jmp     loc_18002D59C
0x18002d69b  mov     rcx, rbp; lpCriticalSection
0x18002d69e  call    cs:__imp_LeaveCriticalSection
0x18002d6a4  xor     r9d, r9d; lpName
0x18002d6a7  xor     r8d, r8d; bInitialState
0x18002d6aa  xor     edx, edx; bManualReset
0x18002d6ac  xor     ecx, ecx; lpEventAttributes
0x18002d6ae  call    cs:__imp_CreateEventW
0x18002d6b4  mov     cs:MachineGroupPolicyChangeEvent, rax
0x18002d6bb  test    rax, rax
0x18002d6be  jz      loc_18002D61F
0x18002d6c4  mov     edx, esi; bMachine
0x18002d6c6  mov     rcx, rax; hEvent
0x18002d6c9  call    cs:__imp_RegisterGPNotification
0x18002d6cf  test    eax, eax
0x18002d6d1  jnz     short loc_18002D6F9
0x18002d6d3  call    cs:__imp_GetLastError
0x18002d6d9  mov     ebx, eax
0x18002d6db  cmp     eax, esi
0x18002d6dd  jnz     loc_18002D59C
0x18002d6e3  mov     rcx, cs:MachineGroupPolicyChangeEvent; hObject
0x18002d6ea  call    cs:__imp_CloseHandle
0x18002d6f0  mov     cs:MachineGroupPolicyChangeEvent, rdi
0x18002d6f7  jmp     short loc_18002D733
0x18002d6f9  mov     rdx, cs:MachineGroupPolicyChangeEvent; hObject
0x18002d700  lea     r8, WsOnMachineGroupPolicyChanged; Callback
0x18002d707  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18002d70b  lea     rcx, MachineGroupPolicyChangeWaitObject; phNewWaitObject
0x18002d712  xor     r9d, r9d; Context
0x18002d715  mov     dword ptr [rsp+68h+phkResult], ebx; dwMilliseconds
0x18002d719  mov     cs:RegisteredForMachineGroupPolicyChangeNotifications, esi
0x18002d71f  call    cs:__imp_RegisterWaitForSingleObject
0x18002d725  test    eax, eax
0x18002d727  jz      loc_18002D61F
0x18002d72d  mov     cs:WaitingForMachineGroupPolicyChanges, esi
0x18002d733  mov     cs:WsGlobalData.dwCurrentState, 4
0x18002d73d  mov     cs:WsGlobalData.dwControlsAccepted, 43h ; 'C'
0x18002d747  mov     qword ptr cs:WsGlobalData.dwCheckPoint, rdi
0x18002d74e  call    WsUpdateStatus
0x18002d753  mov     ebx, eax
0x18002d755  test    eax, eax
0x18002d757  jz      short loc_18002D76D
0x18002d759  mov     cs:WsInitializeStatusError, eax
0x18002d75f  lea     rcx, aWkssvcFailedWi_4; "WKSSVC failed with WsUpdateStatus %x\n"
0x18002d766  mov     edx, eax
0x18002d768  jmp     loc_18002D596
0x18002d76d  mov     rax, cs:WsLmsvcsGlobalData
0x18002d774  lea     r9, WsTerminationNotify
0x18002d77b  mov     r8, cs:hHandle
0x18002d782  lea     rdx, aLanmanworkstat; "LanmanWorkstation"
0x18002d789  mov     [rsp+68h+dwFlags], 18h
0x18002d791  lea     rcx, TerminateWorkItem
0x18002d798  mov     [rsp+68h+phkResult], rdi
0x18002d79d  mov     rax, [rax+0C0h]
0x18002d7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7a9  mov     ebx, eax
0x18002d7ab  test    eax, eax
0x18002d7ad  jz      short loc_18002D7C5
0x18002d7af  mov     ecx, eax; dwErrCode
0x18002d7b1  call    cs:__imp_SetLastError
0x18002d7b7  mov     edx, ebx
0x18002d7b9  lea     rcx, aWkssvcRegister; "WKSSVC/RegisterStopCallback failed. Err"...
0x18002d7c0  jmp     loc_18002D596
0x18002d7c5  lea     rax, [rsp+68h+arg_10]
0x18002d7cd  mov     [rsp+68h+arg_10], edi
0x18002d7d4  mov     [rsp+68h+var_38], rax
0x18002d7d9  lea     rbp, WsData
0x18002d7e0  mov     [rsp+68h+dwFlags], 104h
0x18002d7e8  lea     r8, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18002d7ef  xor     r9d, r9d
0x18002d7f2  mov     [rsp+68h+phkResult], rbp
0x18002d7f7  xor     edx, edx
0x18002d7f9  lea     rcx, aLanmanworkstat; "LanmanWorkstation"
0x18002d800  call    cs:__imp_RtlGetPersistedStateLocation
0x18002d806  test    eax, eax
0x18002d808  jns     short loc_18002D852
0x18002d80a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002d811  lea     rdx, WPP_GLOBAL_Control
0x18002d818  cmp     rcx, rdx
0x18002d81b  jz      loc_18002D59C
0x18002d821  test    [rcx+1Ch], sil
0x18002d825  jz      loc_18002D59C
0x18002d82b  cmp     [rcx+19h], sil
0x18002d82f  jb      loc_18002D59C
0x18002d835  mov     edx, 0Ah
0x18002d83a  mov     rcx, [rcx+10h]
0x18002d83e  lea     r8, WPP_31e0dc789b9f3c2c04382f436cbfec2a_Traceguids
0x18002d845  mov     r9d, eax
0x18002d848  call    WPP_SF_d
0x18002d84d  jmp     loc_18002D59C
0x18002d852  lea     rax, aClientcertific; "ClientCertificateMappings"
0x18002d859  mov     r9, rbp
0x18002d85c  lea     r8, aWsWs_1; "%ws\\%ws"
0x18002d863  mov     [rsp+68h+phkResult], rax
0x18002d868  mov     edx, 104h
0x18002d86d  lea     rcx, Path
0x18002d874  call    RtlStringCchPrintfW
0x18002d879  test    eax, eax
0x18002d87b  jns     short loc_18002D8AF
0x18002d87d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002d884  lea     rdx, WPP_GLOBAL_Control
0x18002d88b  cmp     rcx, rdx
0x18002d88e  jz      loc_18002D59C
0x18002d894  test    [rcx+1Ch], sil
0x18002d898  jz      loc_18002D59C
0x18002d89e  cmp     [rcx+19h], sil
0x18002d8a2  jb      loc_18002D59C
0x18002d8a8  mov     edx, 0Bh
0x18002d8ad  jmp     short loc_18002D83A
0x18002d8af  mov     rdx, rbp
0x18002d8b2  lea     rcx, pSecurityDescriptor
0x18002d8b9  call    WsQueryRegistrySubkeySecurityDescriptor
0x18002d8be  mov     ebx, eax
0x18002d8c0  test    eax, eax
0x18002d8c2  jz      short loc_18002D90C
0x18002d8c4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002d8cb  lea     rdx, WPP_GLOBAL_Control
0x18002d8d2  cmp     rcx, rdx
0x18002d8d5  jz      loc_18002D59C
0x18002d8db  test    [rcx+1Ch], sil
0x18002d8df  jz      loc_18002D59C
0x18002d8e5  cmp     [rcx+19h], sil
0x18002d8e9  jb      loc_18002D59C
0x18002d8ef  mov     edx, 0Ch
0x18002d8f4  mov     rcx, [rcx+10h]
0x18002d8f8  lea     r8, WPP_31e0dc789b9f3c2c04382f436cbfec2a_Traceguids
0x18002d8ff  mov     r9d, eax
0x18002d902  call    WPP_SF_d
0x18002d907  jmp     loc_18002D59C
0x18002d90c  call    WsRestoreCertificateMappings
0x18002d911  mov     ebx, eax
0x18002d913  test    eax, eax
0x18002d915  jz      short loc_18002D949
0x18002d917  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002d91e  lea     rdx, WPP_GLOBAL_Control
0x18002d925  cmp     rcx, rdx
0x18002d928  jz      loc_18002D59C
0x18002d92e  test    [rcx+1Ch], sil
0x18002d932  jz      loc_18002D59C
0x18002d938  cmp     [rcx+19h], sil
0x18002d93c  jb      loc_18002D59C
0x18002d942  mov     edx, 0Dh
0x18002d947  jmp     short loc_18002D8F4
0x18002d949  call    WsRestoreGlobalMappingsFromRegistry
0x18002d94e  call    WJInitializeWorkplaceJoin
0x18002d953  jmp     loc_18002D5BA
```
