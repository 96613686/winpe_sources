# ServiceMain

- ea: `0x18000ed30`
- end: `0x18000edb4`
- name: `ServiceMain`
- size: `132`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800071b0`
- `0x18000c570`
- `0x18000df30`

## string_xrefs

- `0x18000ed43`: `McpManagementService`
- `0x18000ed51`: `ServiceMain`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 ServiceMain()
{
  __int128 v1; // [rsp+20h] [rbp-48h] BYREF
  _DWORD v2[8]; // [rsp+30h] [rbp-38h]
  __int64 v3; // [rsp+50h] [rbp-18h]

  McpManagementTelemetry::WriteDbgTraceInfo("ServiceMain", L"Starting %s", L"McpManagementService");
  v2[0] = 16;
  v3 = 0;
  *(_OWORD *)&v2[3] = 0;
  v2[3] = 0;
  v1 = 0;
  *(_QWORD *)&v2[1] = 4;
  Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(&v1);
  return Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(&v1);
}

```

## disassembly

```asm
0x18000ed30  sub     rsp, 68h
0x18000ed34  mov     rax, cs:__security_cookie
0x18000ed3b  xor     rax, rsp
0x18000ed3e  mov     [rsp+68h+var_10], rax
0x18000ed43  lea     r8, ServiceName; "McpManagementService"
0x18000ed4a  lea     rdx, aStartingS; "Starting %s"
0x18000ed51  lea     rcx, aServicemain_0; "ServiceMain"
0x18000ed58  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ed5d  xorps   xmm1, xmm1
0x18000ed60  lea     rcx, [rsp+68h+var_48]
0x18000ed65  movups  xmmword ptr [rsp+68h+var_38], xmm1
0x18000ed6a  xor     eax, eax
0x18000ed6c  mov     [rsp+68h+var_38], 10h
0x18000ed74  xorps   xmm0, xmm0
0x18000ed77  mov     [rsp+68h+var_18], rax
0x18000ed7c  movups  xmmword ptr [rsp+68h+var_38+0Ch], xmm1
0x18000ed81  mov     [rsp+68h+var_38+0Ch], eax
0x18000ed85  movdqu  [rsp+68h+var_48], xmm0
0x18000ed8b  mov     [rsp+68h+var_38+4], 4
0x18000ed93  call    ?RunServiceMain@?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAAJE@Z; Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(uchar)
0x18000ed98  lea     rcx, [rsp+68h+var_48]
0x18000ed9d  call    ??1?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAA@XZ; Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(void)
0x18000eda2  mov     rcx, [rsp+68h+var_10]
0x18000eda7  xor     rcx, rsp; StackCookie
0x18000edaa  call    __security_check_cookie
0x18000edaf  add     rsp, 68h
0x18000edb3  retn
```
