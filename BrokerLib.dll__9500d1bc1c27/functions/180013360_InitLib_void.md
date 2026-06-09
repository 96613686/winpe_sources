# InitLib(void)

- ea: `0x180013360`
- end: `0x1800133da`
- name: `?InitLib@@YAKXZ`
- size: `122`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800114fc`

## callees

- `0x180011874`
- `0x180011e14`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800133cd`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800133cd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800133b3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800133b3`

## pseudocode

```c
__int64 InitLib(void)
{
  qword_180028950 = 1;
  qword_180028948 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_BrokerCommon;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  CreateWellKnownSid(WinNullSid, 0, &BLP_TRACELOGGING_INVALID_SID, 0);
  RtlRunOnceExecuteOnce(&BrpRpcContextHelperInitializeOnceToken, BrpRpcContextHelperInitializeOnceFunction, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180013360  sub     rsp, 28h
0x180013364  xor     ecx, ecx
0x180013366  mov     cs:qword_180028950, 1
0x180013371  lea     rax, WPP_ThisDir_CTLGUID_BrokerCommon
0x180013378  mov     cs:qword_180028948, rcx
0x18001337f  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180013386  lea     rax, WPP_MAIN_CB
0x18001338d  mov     cs:WPP_GLOBAL_Control, rax
0x180013394  mov     cs:WPP_MAIN_CB, rcx
0x18001339b  call    WppInitUm
0x1800133a0  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800133a5  xor     r9d, r9d; cbSid
0x1800133a8  lea     r8, BLP_TRACELOGGING_INVALID_SID; pSid
0x1800133af  xor     edx, edx; DomainSid
0x1800133b1  xor     ecx, ecx; WellKnownSidType
0x1800133b3  call    cs:__imp_CreateWellKnownSid
0x1800133b9  xor     r9d, r9d
0x1800133bc  lea     rdx, ?BrpRpcContextHelperInitializeOnceFunction@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; BrpRpcContextHelperInitializeOnceFunction(_RTL_RUN_ONCE *,void *,void * *)
0x1800133c3  xor     r8d, r8d
0x1800133c6  lea     rcx, ?BrpRpcContextHelperInitializeOnceToken@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE BrpRpcContextHelperInitializeOnceToken
0x1800133cd  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800133d3  xor     eax, eax
0x1800133d5  add     rsp, 28h
0x1800133d9  retn
```
