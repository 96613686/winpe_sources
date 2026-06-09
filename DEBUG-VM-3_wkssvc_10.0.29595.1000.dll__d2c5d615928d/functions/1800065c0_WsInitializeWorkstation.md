# WsInitializeWorkstation

- ea: `0x1800065c0`
- end: `0x180006887`
- name: `WsInitializeWorkstation`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d530`

## callees

- `0x1800064b0`
- `0x1800065c0`
- `0x180006890`
- `0x1800068d0`
- `0x180006948`
- `0x180006c3c`
- `0x180006ca0`
- `0x180006e04`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000664e`
- `ntdll!DbgPrint` at `0x180006802`
- `ntdll!DbgPrint` at `0x18000664e`
- `ntdll!DbgPrint` at `0x180006802`
- `ntdll!RtlNtStatusToDosError` at `0x180006869`
- `ntdll!RtlNtStatusToDosError` at `0x180006869`
- `ntdll!RtlInitializeResource` at `0x18000668d`
- `ntdll!RtlInitializeResource` at `0x18000668d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006678`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006678`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800066a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800066a7`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800067e7`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800067e7`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000679f`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000679f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006779`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006779`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18000685d`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18000685d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006625`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006625`

## string_xrefs

- `0x180006668`: `WKSSVC failed with WsUpdateStatus %x\n`
- `0x180006641`: `WKSSVC failed with RegisterServiceCtrlHandler %x\n`
- `0x18000675b`: `WKSSVC failed with WsCreateApiStructures %x\n`

## pseudocode

```c
DWORD WsInitializeWorkstation()
{
  __int64 LastError; // rbx
  __int64 v1; // rdx
  const CHAR *v2; // rcx
  DWORD result; // eax
  unsigned int updated; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int ApiStructures; // eax
  RPC_STATUS v9; // ebx
  RPC_STATUS v10; // edi
  ULONG v11; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  WsGlobalData.dwServiceType = 48;
  *(_QWORD *)&WsGlobalData.dwCurrentState = 2;
  WsGlobalData.dwCheckPoint = 1;
  WsGlobalData.dwWaitHint = 90000;
  *(_QWORD *)&WsGlobalData.dwWin32ExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"LanmanWorkstation", WkstaControlHandlerEx, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    v1 = LastError;
    v2 = "WKSSVC failed with RegisterServiceCtrlHandler %x\n";
LABEL_3:
    WsInitializeStatusError = LastError;
    DbgPrint(v2, v1);
    return LastError;
  }
  updated = WsUpdateStatus();
  LODWORD(LastError) = updated;
  if ( updated )
  {
    v1 = updated;
    v2 = "WKSSVC failed with WsUpdateStatus %x\n";
    goto LABEL_3;
  }
  InitializeCriticalSection(&WsWorkerCriticalSection);
  WsWorkerCriticalSectionInitialized = 1;
  RtlInitializeResource(&WsInfo);
  WsInitState |= 0x80u;
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
    goto LABEL_7;
  WsInitState |= 1u;
  v5 = WsInitializeLsa();
  LODWORD(LastError) = v5;
  if ( v5 )
  {
    v1 = v5;
    v2 = "WKSSVC failed with WsInitializeLsa %x\n";
    goto LABEL_3;
  }
  WsInitState |= 0x20u;
  v6 = WsInitializeRedirector();
  LODWORD(LastError) = v6;
  if ( v6 )
  {
    v1 = v6;
    v2 = "WKSSVC failed with WsInitializeRedirector %x\n";
    goto LABEL_3;
  }
  WsInitState |= 2u;
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  v7 = WsAddDomains();
  LODWORD(LastError) = v7;
  if ( v7 )
  {
    v1 = v7;
    v2 = "WKSSVC failed with WsAddDomains %x\n";
    goto LABEL_3;
  }
  ++WsGlobalData.dwCheckPoint;
  WsUpdateStatus();
  ApiStructures = WsCreateApiStructures();
  LODWORD(LastError) = ApiStructures;
  if ( ApiStructures )
  {
    v1 = ApiStructures;
    v2 = "WKSSVC failed with WsCreateApiStructures %x\n";
    goto LABEL_3;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:NSG:NSD:(A;;0x12019B;;;AN)(A;;0x12019B;;;WD)(A;;0x1F01FF;;;SY)(A;;0x1F01FF;;;NS)S:(ML;;NW;;;LW)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v9 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0xAu, (RPC_WSTR)L"\\PIPE\\wkssvc", SecurityDescriptor);
    LocalFree(SecurityDescriptor);
    v10 = 0;
    if ( v9 != 1740 )
      v10 = v9;
    if ( v10 || (v10 = RpcServerRegisterIfEx(qword_180036060, 0, 0, 0x91u, 0x4D2u, WsRpcSecurityCallback_Old)) != 0 )
    {
      WsInitializeStatusError = v10;
      DbgPrint("WKSSVC failed with StartRpcServer %x\n", v10);
      return v10;
    }
    else
    {
      WsInitState |= 8u;
      if ( !(unsigned int)StartDfscRpc() )
        WsInitState |= 0x100u;
      v11 = WsInitializeDfs();
      LODWORD(LastError) = v11;
      if ( v11 )
      {
        v1 = v11;
        v2 = "WKSSVC failed with WsInitializeDfs %x\n";
        goto LABEL_3;
      }
      WsInitState |= 0x40u;
      I_ScSetServiceBitsW(hServiceStatus, 1, 1, 1, 0);
      return 0;
    }
  }
  else
  {
LABEL_7:
    result = GetLastError();
    WsInitializeStatusError = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800065c0  mov     rax, rsp
0x1800065c3  mov     [rax+10h], rbx
0x1800065c7  mov     [rax+18h], rdi
0x1800065cb  mov     [rax+8], rcx
0x1800065cf  push    r14
0x1800065d1  sub     rsp, 30h
0x1800065d5  mov     qword ptr [rax+8], 0
0x1800065dd  mov     cs:WsGlobalData.dwServiceType, 30h ; '0'
0x1800065e7  mov     qword ptr cs:WsGlobalData.dwCurrentState, 2
0x1800065f2  mov     r14d, 1
0x1800065f8  mov     cs:WsGlobalData.dwCheckPoint, r14d
0x1800065ff  mov     cs:WsGlobalData.dwWaitHint, 15F90h
0x180006609  mov     qword ptr cs:WsGlobalData.dwWin32ExitCode, 0
0x180006614  xor     r8d, r8d; lpContext
0x180006617  lea     rdx, WkstaControlHandlerEx; lpHandlerProc
0x18000661e  lea     rcx, aLanmanworkstat; "LanmanWorkstation"
0x180006625  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000662b  mov     cs:hServiceStatus, rax
0x180006632  test    rax, rax
0x180006635  jnz     short loc_18000665B
0x180006637  call    cs:__imp_GetLastError
0x18000663d  mov     ebx, eax
0x18000663f  mov     edx, eax
0x180006641  lea     rcx, aWkssvcFailedWi; "WKSSVC failed with RegisterServiceCtrlH"...
0x180006648  mov     cs:WsInitializeStatusError, ebx
0x18000664e  call    cs:__imp_DbgPrint
0x180006654  mov     eax, ebx
0x180006656  jmp     loc_180006876
0x18000665b  call    WsUpdateStatus
0x180006660  mov     ebx, eax
0x180006662  test    eax, eax
0x180006664  jz      short loc_180006671
0x180006666  mov     edx, eax
0x180006668  lea     rcx, aWkssvcFailedWi_4; "WKSSVC failed with WsUpdateStatus %x\n"
0x18000666f  jmp     short loc_180006648
0x180006671  lea     rcx, WsWorkerCriticalSection; lpCriticalSection
0x180006678  call    cs:__imp_InitializeCriticalSection
0x18000667e  nop
0x18000667f  mov     cs:WsWorkerCriticalSectionInitialized, r14d
0x180006686  lea     rcx, WsInfo; Resource
0x18000668d  call    cs:__imp_RtlInitializeResource
0x180006693  nop
0x180006694  bts     cs:WsInitState, 7
0x18000669c  xor     r9d, r9d; lpName
0x18000669f  xor     r8d, r8d; bInitialState
0x1800066a2  mov     edx, r14d; bManualReset
0x1800066a5  xor     ecx, ecx; lpEventAttributes
0x1800066a7  call    cs:__imp_CreateEventW
0x1800066ad  mov     cs:hHandle, rax
0x1800066b4  test    rax, rax
0x1800066b7  jnz     short loc_1800066CA
0x1800066b9  call    cs:__imp_GetLastError
0x1800066bf  mov     cs:WsInitializeStatusError, eax
0x1800066c5  jmp     loc_180006876
0x1800066ca  or      cs:WsInitState, r14d
0x1800066d1  call    WsInitializeLsa
0x1800066d6  mov     ebx, eax
0x1800066d8  test    eax, eax
0x1800066da  jz      short loc_1800066EA
0x1800066dc  mov     edx, eax
0x1800066de  lea     rcx, aWkssvcFailedWi_2; "WKSSVC failed with WsInitializeLsa %x\n"
0x1800066e5  jmp     loc_180006648
0x1800066ea  or      cs:WsInitState, 20h
0x1800066f1  call    WsInitializeRedirector
0x1800066f6  mov     ebx, eax
0x1800066f8  test    eax, eax
0x1800066fa  jz      short loc_18000670A
0x1800066fc  mov     edx, eax
0x1800066fe  lea     rcx, aWkssvcFailedWi_1; "WKSSVC failed with WsInitializeRedirect"...
0x180006705  jmp     loc_180006648
0x18000670a  or      cs:WsInitState, 2
0x180006711  add     cs:WsGlobalData.dwCheckPoint, r14d
0x180006718  call    WsUpdateStatus
0x18000671d  add     cs:WsGlobalData.dwCheckPoint, r14d
0x180006724  call    WsUpdateStatus
0x180006729  call    WsAddDomains
0x18000672e  mov     ebx, eax
0x180006730  test    eax, eax
0x180006732  jz      short loc_180006742
0x180006734  mov     edx, eax
0x180006736  lea     rcx, aWkssvcFailedWi_3; "WKSSVC failed with WsAddDomains %x\n"
0x18000673d  jmp     loc_180006648
0x180006742  add     cs:WsGlobalData.dwCheckPoint, r14d
0x180006749  call    WsUpdateStatus
0x18000674e  call    WsCreateApiStructures
0x180006753  mov     ebx, eax
0x180006755  test    eax, eax
0x180006757  jz      short loc_180006767
0x180006759  mov     edx, eax
0x18000675b  lea     rcx, aWkssvcFailedWi_6; "WKSSVC failed with WsCreateApiStructure"...
0x180006762  jmp     loc_180006648
0x180006767  xor     r9d, r9d; SecurityDescriptorSize
0x18000676a  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x18000676f  mov     edx, r14d; StringSDRevision
0x180006772  lea     rcx, StringSecurityDescriptor; "O:NSG:NSD:(A;;0x12019B;;;AN)(A;;0x12019"...
0x180006779  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000677f  test    eax, eax
0x180006781  jz      loc_1800066B9
0x180006787  mov     r9, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x18000678c  lea     r8, Endpoint; "\\PIPE\\wkssvc"
0x180006793  mov     edx, 0Ah; MaxCalls
0x180006798  lea     rcx, Protseq; "ncacn_np"
0x18000679f  call    cs:__imp_RpcServerUseProtseqEpW
0x1800067a5  mov     ebx, eax
0x1800067a7  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x1800067ac  call    cs:__imp_LocalFree
0x1800067b2  xor     edi, edi
0x1800067b4  cmp     ebx, 6CCh
0x1800067ba  cmovnz  edi, ebx
0x1800067bd  test    edi, edi
0x1800067bf  jnz     short loc_1800067F3
0x1800067c1  lea     rax, WsRpcSecurityCallback_Old
0x1800067c8  mov     [rsp+38h+IfCallback], rax; IfCallback
0x1800067cd  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x1800067d5  mov     r9d, 91h; Flags
0x1800067db  xor     r8d, r8d; MgrEpv
0x1800067de  xor     edx, edx; MgrTypeUuid
0x1800067e0  lea     rcx, qword_180036060; IfSpec
0x1800067e7  call    cs:__imp_RpcServerRegisterIfEx
0x1800067ed  mov     edi, eax
0x1800067ef  test    eax, eax
0x1800067f1  jz      short loc_18000680C
0x1800067f3  mov     cs:WsInitializeStatusError, edi
0x1800067f9  mov     edx, edi
0x1800067fb  lea     rcx, aWkssvcFailedWi_0; "WKSSVC failed with StartRpcServer %x\n"
0x180006802  call    cs:__imp_DbgPrint
0x180006808  mov     eax, edi
0x18000680a  jmp     short loc_180006876
0x18000680c  or      cs:WsInitState, 8
0x180006813  call    StartDfscRpc
0x180006818  test    eax, eax
0x18000681a  jnz     short loc_180006824
0x18000681c  bts     cs:WsInitState, 8
0x180006824  call    WsInitializeDfs
0x180006829  mov     ebx, eax
0x18000682b  test    eax, eax
0x18000682d  jz      short loc_18000683D
0x18000682f  mov     edx, eax
0x180006831  lea     rcx, aWkssvcFailedWi_5; "WKSSVC failed with WsInitializeDfs %x\n"
0x180006838  jmp     loc_180006648
0x18000683d  or      cs:WsInitState, 40h
0x180006844  mov     qword ptr [rsp+38h+MaxCalls], 0
0x18000684d  mov     r9d, r14d
0x180006850  mov     r8d, r14d
0x180006853  mov     edx, r14d
0x180006856  mov     rcx, cs:hServiceStatus
0x18000685d  call    cs:__imp_I_ScSetServiceBitsW
0x180006863  xor     eax, eax
0x180006865  jmp     short loc_180006876
0x180006867  mov     ecx, eax; Status
0x180006869  call    cs:__imp_RtlNtStatusToDosError
0x18000686f  jmp     short loc_180006876
0x180006871  mov     eax, 8
0x180006876  mov     rbx, [rsp+38h+arg_8]
0x18000687b  mov     rdi, [rsp+38h+arg_10]
0x180006880  add     rsp, 30h
0x180006884  pop     r14
0x180006886  retn
```
