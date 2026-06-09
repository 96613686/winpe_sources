# StartEndpointMapper

- ea: `0x180006758`
- end: `0x180006a08`
- name: `StartEndpointMapper`
- size: `688`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800081a4`

## callees

- `0x18000662c`
- `0x180006758`
- `0x180008b80`
- `0x180008df0`
- `0x1800094f4`
- `0x18000a8b4`
- `0x18000a980`

## import_xrefs

- `RPCRT4!I_RpcSystemFunction001` at `0x180006868`
- `RPCRT4!I_RpcSystemFunction001` at `0x180006868`
- `RPCRT4!RpcServerRegisterIf2` at `0x18000692e`
- `RPCRT4!RpcServerRegisterIf2` at `0x18000692e`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800068b3`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800068f1`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800068b3`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800068f1`
- `RPCRT4!I_RpcServerSetAddressChangeFn` at `0x180006973`
- `RPCRT4!I_RpcServerSetAddressChangeFn` at `0x180006973`
- `RPCRT4!I_RpcServerRegisterForwardFunction` at `0x180006943`
- `RPCRT4!I_RpcServerRegisterForwardFunction` at `0x180006943`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180006834`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000684e`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180006834`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000684e`
- `RPCRT4!I_RpcGetPortAllocationData` at `0x180006966`
- `RPCRT4!I_RpcGetPortAllocationData` at `0x180006966`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800069d4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800069d4`
- `ntdll!NtDeleteWnfStateData` at `0x180006791`
- `ntdll!NtDeleteWnfStateData` at `0x180006791`
- `ntdll!WinSqmIsOptedIn` at `0x180006979`
- `ntdll!WinSqmIsOptedIn` at `0x180006979`
- `ntdll!NtQuerySystemInformation` at `0x1800067c0`
- `ntdll!NtQuerySystemInformation` at `0x1800067c0`
- `ntdll!RtlInitializeCriticalSection` at `0x1800067e3`
- `ntdll!RtlInitializeCriticalSection` at `0x1800067e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006996`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006996`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006959`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006959`

## pseudocode

```c
NTSTATUS StartEndpointMapper()
{
  NTSTATUS result; // eax
  struct _ACL *Sd; // rbx
  BOOL v2; // esi
  HANDLE ProcessHeap; // rax
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // [rsp+48h] [rbp-60h] BYREF
  _BYTE SystemInformation[64]; // [rsp+50h] [rbp-58h] BYREF

  v6 = 0;
  result = NtDeleteWnfStateData(&WNF_RPCF_FWMAN_RUNNING, 0);
  if ( result >= 0 )
  {
    memset_0(SystemInformation, 0, sizeof(SystemInformation));
    result = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
    if ( result >= 0 )
    {
      gNumberOfProcessors = SystemInformation[56];
      result = RtlInitializeCriticalSection(&UuidCritSec);
      if ( result >= 0 )
      {
        DealWithDeviceEvent();
        hEpMapperHeap = GetProcessHeap();
        if ( hEpMapperHeap )
        {
          Sd = CreateSd();
          if ( Sd )
          {
            v2 = RpcServerRegisterAuthInfoW(0, 9u, 0, 0) != 0;
            if ( RpcServerRegisterAuthInfoW(0, 0x10u, 0, 0) )
              v2 = 1;
            I_RpcSystemFunction001(4);
            result = RpcServerRegisterIf3(&unk_18000C890, 0, 0, 0, 1234, 4096, 0, Sd);
            if ( !result )
            {
              result = RpcServerRegisterIf3(&unk_18000CC70, 0, 0, 0, 1234, 204800, LocalEpmpSecurityCallback, Sd);
              if ( !result
                && (v2
                 || (result = RpcServerRegisterIf2(
                                &unk_18000D7E0,
                                0,
                                0,
                                0,
                                0x4D2u,
                                0x1000u,
                                (RPC_IF_CALLBACK_FN *)DebugServerSecurityCallback)) == 0) )
              {
                if ( !I_RpcServerRegisterForwardFunction(GetForwardEp) )
                {
                  InitializeCriticalSectionAndSpinCount(&PortLock, 0x80000000);
                  I_RpcGetPortAllocationData(&PortData);
                }
                I_RpcServerSetAddressChangeFn(UpdateAddresses);
                if ( (unsigned int)WinSqmIsOptedIn() )
                  SqmUploadMachineConfig();
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, Sd);
                v4 = RtlSubscribeWnfStateChangeNotification(
                       &v6,
                       WNF_SCM_SERVICE_CONTROL_MANAGER_STATE,
                       0,
                       EpmpWnfScmStateChangeCallback,
                       0,
                       0,
                       0,
                       0);
                if ( v4 < 0 )
                  MicrosoftTelemetryAssertTriggeredArgs(v5, (unsigned int)v4);
                return 0;
              }
            }
          }
          else
          {
            return 14;
          }
        }
        else
        {
          return GetLastError();
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006758  mov     [rsp+arg_0], rbx
0x18000675d  push    rsi
0x18000675e  sub     rsp, 0A0h
0x180006765  mov     rax, cs:__security_cookie
0x18000676c  xor     rax, rsp
0x18000676f  mov     [rsp+0A8h+var_18], rax
0x180006777  xor     edx, edx
0x180006779  mov     [rsp+0A8h+var_68], 0
0x180006781  lea     rcx, WNF_RPCF_FWMAN_RUNNING
0x180006788  mov     [rsp+0A8h+var_60], 0
0x180006791  call    cs:__imp_NtDeleteWnfStateData
0x180006797  test    eax, eax
0x180006799  js      loc_1800069E7
0x18000679f  mov     ebx, 40h ; '@'
0x1800067a4  lea     rcx, [rsp+0A8h+SystemInformation]; void *
0x1800067a9  mov     r8d, ebx; Size
0x1800067ac  xor     edx, edx; Val
0x1800067ae  call    memset_0
0x1800067b3  xor     r9d, r9d; ReturnLength
0x1800067b6  lea     rdx, [rsp+0A8h+SystemInformation]; SystemInformation
0x1800067bb  mov     r8d, ebx; SystemInformationLength
0x1800067be  xor     ecx, ecx; SystemInformationClass
0x1800067c0  call    cs:__imp_NtQuerySystemInformation
0x1800067c6  test    eax, eax
0x1800067c8  js      loc_1800069E7
0x1800067ce  movsx   eax, [rsp+0A8h+var_20]
0x1800067d6  lea     rcx, UuidCritSec; CriticalSection
0x1800067dd  mov     cs:?gNumberOfProcessors@@3IA, eax; uint gNumberOfProcessors
0x1800067e3  call    cs:__imp_RtlInitializeCriticalSection
0x1800067e9  test    eax, eax
0x1800067eb  js      loc_1800069E7
0x1800067f1  call    DealWithDeviceEvent
0x1800067f6  call    cs:__imp_GetProcessHeap
0x1800067fc  mov     cs:hEpMapperHeap, rax
0x180006803  test    rax, rax
0x180006806  jnz     short loc_180006813
0x180006808  call    cs:__imp_GetLastError
0x18000680e  jmp     loc_1800069E7
0x180006813  call    CreateSd
0x180006818  mov     rbx, rax
0x18000681b  test    rax, rax
0x18000681e  jnz     short loc_180006828
0x180006820  lea     eax, [rbx+0Eh]
0x180006823  jmp     loc_1800069E7
0x180006828  xor     r9d, r9d; Arg
0x18000682b  xor     r8d, r8d; GetKeyFn
0x18000682e  xor     ecx, ecx; ServerPrincName
0x180006830  lea     edx, [r9+9]; AuthnSvc
0x180006834  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18000683a  xor     esi, esi
0x18000683c  test    eax, eax
0x18000683e  setnz   sil
0x180006842  xor     r9d, r9d; Arg
0x180006845  xor     r8d, r8d; GetKeyFn
0x180006848  xor     ecx, ecx; ServerPrincName
0x18000684a  lea     edx, [r9+10h]; AuthnSvc
0x18000684e  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180006854  mov     ecx, 1
0x180006859  lea     r8, [rsp+0A8h+var_68]
0x18000685e  test    eax, eax
0x180006860  cmovnz  esi, ecx
0x180006863  xor     edx, edx
0x180006865  lea     ecx, [rdx+4]
0x180006868  call    cs:__imp_I_RpcSystemFunction001
0x18000686e  xor     r8d, r8d
0x180006871  mov     [rsp+0A8h+var_70], rbx
0x180006876  xor     edx, edx
0x180006878  lea     rcx, unk_18000C890
0x18000687f  cmp     [rsp+0A8h+var_68], edx
0x180006883  jz      short loc_180006897
0x180006885  lea     rax, RemoteEpmpServerSecurityCallback
0x18000688c  mov     [rsp+0A8h+IfCallbackFn], rax
0x180006891  lea     r9d, [r8+10h]
0x180006895  jmp     short loc_1800068A3
0x180006897  mov     [rsp+0A8h+IfCallbackFn], 0
0x1800068a0  xor     r9d, r9d
0x1800068a3  mov     [rsp+0A8h+MaxRpcSize], 1000h
0x1800068ab  mov     [rsp+0A8h+MaxCalls], 4D2h
0x1800068b3  call    cs:__imp_RpcServerRegisterIf3
0x1800068b9  test    eax, eax
0x1800068bb  jnz     loc_1800069E7
0x1800068c1  mov     [rsp+0A8h+var_70], rbx
0x1800068c6  lea     rax, LocalEpmpSecurityCallback
0x1800068cd  mov     [rsp+0A8h+IfCallbackFn], rax
0x1800068d2  lea     rcx, unk_18000CC70
0x1800068d9  mov     [rsp+0A8h+MaxRpcSize], 32000h
0x1800068e1  xor     r9d, r9d
0x1800068e4  xor     r8d, r8d
0x1800068e7  mov     [rsp+0A8h+MaxCalls], 4D2h
0x1800068ef  xor     edx, edx
0x1800068f1  call    cs:__imp_RpcServerRegisterIf3
0x1800068f7  test    eax, eax
0x1800068f9  jnz     loc_1800069E7
0x1800068ff  test    esi, esi
0x180006901  jnz     short loc_18000693C
0x180006903  lea     rax, DebugServerSecurityCallback
0x18000690a  xor     r9d, r9d; Flags
0x18000690d  mov     [rsp+0A8h+IfCallbackFn], rax; IfCallbackFn
0x180006912  lea     rcx, unk_18000D7E0; IfSpec
0x180006919  mov     [rsp+0A8h+MaxRpcSize], 1000h; MaxRpcSize
0x180006921  xor     r8d, r8d; MgrEpv
0x180006924  xor     edx, edx; MgrTypeUuid
0x180006926  mov     [rsp+0A8h+MaxCalls], 4D2h; MaxCalls
0x18000692e  call    cs:__imp_RpcServerRegisterIf2
0x180006934  test    eax, eax
0x180006936  jnz     loc_1800069E7
0x18000693c  lea     rcx, GetForwardEp; pForwardFunction
0x180006943  call    cs:__imp_I_RpcServerRegisterForwardFunction
0x180006949  test    eax, eax
0x18000694b  jnz     short loc_18000696C
0x18000694d  mov     edx, 80000000h; dwSpinCount
0x180006952  lea     rcx, PortLock; lpCriticalSection
0x180006959  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000695f  lea     rcx, PortData
0x180006966  call    cs:__imp_I_RpcGetPortAllocationData
0x18000696c  lea     rcx, UpdateAddresses; pAddressChangeFn
0x180006973  call    cs:__imp_I_RpcServerSetAddressChangeFn
0x180006979  call    cs:__imp_WinSqmIsOptedIn
0x18000697f  test    eax, eax
0x180006981  jz      short loc_180006988
0x180006983  call    SqmUploadMachineConfig
0x180006988  call    cs:__imp_GetProcessHeap
0x18000698e  mov     r8, rbx; lpMem
0x180006991  xor     edx, edx; dwFlags
0x180006993  mov     rcx, rax; hHeap
0x180006996  call    cs:__imp_HeapFree
0x18000699c  mov     rdx, cs:WNF_SCM_SERVICE_CONTROL_MANAGER_STATE
0x1800069a3  lea     r9, EpmpWnfScmStateChangeCallback
0x1800069aa  mov     dword ptr [rsp+0A8h+var_70], 0
0x1800069b2  lea     rcx, [rsp+0A8h+var_60]
0x1800069b7  mov     dword ptr [rsp+0A8h+IfCallbackFn], 0
0x1800069bf  xor     r8d, r8d
0x1800069c2  mov     qword ptr [rsp+0A8h+MaxRpcSize], 0
0x1800069cb  mov     qword ptr [rsp+0A8h+MaxCalls], 0
0x1800069d4  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800069da  test    eax, eax
0x1800069dc  jns     short loc_1800069E5
0x1800069de  mov     edx, eax
0x1800069e0  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800069e5  xor     eax, eax
0x1800069e7  mov     rcx, [rsp+0A8h+var_18]
0x1800069ef  xor     rcx, rsp; StackCookie
0x1800069f2  call    __security_check_cookie
0x1800069f7  mov     rbx, [rsp+0A8h+arg_0]
0x1800069ff  add     rsp, 0A0h
0x180006a06  pop     rsi
0x180006a07  retn
```
