# Vml::VmServiceModule<CExec::Svc::Service>::main(int,ushort * *)

- ea: `0x140014ac0`
- end: `0x140014e26`
- name: `?main@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEAAHHPEAPEAG@Z`
- size: `870`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140014e84`

## callees

- `0x140001008`
- `0x140002310`
- `0x140002ecc`
- `0x140009490`
- `0x14000d65c`
- `0x14000d9f0`
- `0x14000e828`
- `0x140010cf4`
- `0x140013914`
- `0x140013f10`
- `0x140013f90`
- `0x140014ac0`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014be3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014af2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014af2`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140014b08`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140014b2f`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140014b08`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140014b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140014b40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140014b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140014b40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140014b95`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140014c5d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140014c5d`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x140014b5a`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x140014bb0`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x140014b5a`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x140014bb0`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140014b7c`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140014bd3`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140014b7c`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140014bd3`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140014d21`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140014d21`

## string_xrefs

- `0x140014d88`: `onecore\vm\common\vml\VmModules.h`
- `0x140014da1`: `onecore\vm\common\vml\VmModules.h`
- `0x140014dba`: `onecore\vm\common\vml\VmModules.h`
- `0x140014dd3`: `onecore\vm\common\vml\VmModules.h`
- `0x140014e01`: `onecore\vm\common\vml\VmModules.h`
- `0x140014e13`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
__int64 __fastcall Vml::VmServiceModule<CExec::Svc::Service>::main(__int64 a1, int a2, __int64 a3)
{
  HANDLE ProcessHeap; // rbx
  HANDLE CurrentProcess; // rax
  int ProcessMitigationPolicy; // eax
  const char *v8; // r9
  const char *v9; // r9
  HANDLE v10; // rax
  const char *v11; // r9
  const char *v12; // r9
  LPCGUID v13; // rbx
  const char *v14; // r9
  void *v15; // rax
  const char *v16; // r9
  const struct wil::FailureInfo *v18; // rdx
  char v19; // [rsp+20h] [rbp-108h]
  __int64 v20; // [rsp+20h] [rbp-108h]
  int v21; // [rsp+24h] [rbp-104h]
  _BYTE v22[160]; // [rsp+30h] [rbp-F8h] BYREF
  int HeapInformation; // [rsp+D0h] [rbp-58h] BYREF
  int v24; // [rsp+D4h] [rbp-54h] BYREF
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+D8h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-40h]
  __int64 v27; // [rsp+F0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v21 = 1;
  v19 = 0;
  ProcessHeap = GetProcessHeap();
  HeapSetInformation(ProcessHeap, HeapEnableTerminationOnCorruption, 0, 0);
  HeapInformation = 2;
  HeapSetInformation(ProcessHeap, HeapCompatibilityInformation, &HeapInformation, 4u);
  v24 = 0;
  CurrentProcess = GetCurrentProcess();
  ProcessMitigationPolicy = GetProcessMitigationPolicy(CurrentProcess, 3, &v24, 4, v19);
  try
  {
    if ( !ProcessMitigationPolicy )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x62D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v8);
    v24 |= 3u;
    if ( !(unsigned int)SetProcessMitigationPolicy(3, &v24, 4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x638,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v9);
    HeapInformation = 0;
    v10 = GetCurrentProcess();
    if ( !(unsigned int)GetProcessMitigationPolicy(v10, 6, &HeapInformation, 4, v20) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x647,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v11);
    HeapInformation |= 1u;
    if ( !(unsigned int)SetProcessMitigationPolicy(6, &HeapInformation, 4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x651,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v12);
    GetModuleHandleW(0);
    Vml::VmModuleBase::gm_ModuleBase = &g_Module;
    VmlDebugSetDefaultTraceFilter();
    _InterlockedExchange64(
      (volatile __int64 *)&g_TraceOutput,
      (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy);
    if ( wil::details::g_pfnLoggingCallback
      && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != VmlpTraceWilFailure )
    {
      memset_0(v22, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v22, v18);
    }
    wil::details::g_pfnLoggingCallback = (__int64)VmlpTraceWilFailure;
    v13 = ProviderId;
    if ( !ProviderId )
    {
      v13 = (LPCGUID)&g_CExecSvcEtwTrace;
      ProviderId = (LPCGUID)&g_CExecSvcEtwTrace;
    }
    Vml::VmpModuleInfo::Initalize();
    if ( !EventRegister(v13, VmlEtwTraceFilterCallback, 0, (PREGHANDLE)&v13[1].Data1) )
    {
      _InterlockedExchange64((volatile __int64 *)&g_TraceOutput, (__int64)VmlpEtwUnifiedTraceOutput);
      g_VmlEtwTrace = (struct _VML_ETW_TRACE *)v13;
      g_TraceEventEnabled = (unsigned __int8 (*)(unsigned __int16))VmlIsEtwTraceEnabled;
    }
    if ( (*(__int64 (__fastcall **)(__int64 *))(g_Module + 48))(&g_Module) )
    {
      v15 = (void *)(*(__int64 (__fastcall **)(__int64 *))(g_Module + 40))(&g_Module);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(v15);
    }
    if ( a2 <= 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB33,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v14);
    if ( (unsigned int)CExec::Svc::Service::ProcessCommandLine(retaddr, a2 - 1, (unsigned __int16 **const)(a3 + 8)) )
    {
      ServiceStartTable.lpServiceName = (LPWSTR)Vml::VmServiceModule<CExec::Svc::Service>::GetServiceName(&g_Module);
      ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)Vml::VmServiceModule<CExec::Svc::Service>::ServiceMain;
      v26 = 0;
      v27 = 0;
      if ( !StartServiceCtrlDispatcherW(&ServiceStartTable) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xB42,
          (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
          v16);
    }
  }
  catch ( ... )
  {
  }
  if ( qword_14003A3B8 )
    qword_14003A3B8();
  Vml::VmModule<CExec::Svc::Service>::Finalize();
  return 0;
}

```

## disassembly

```asm
0x140014ac0  push    rbx
0x140014ac2  push    rsi
0x140014ac3  push    r14
0x140014ac5  push    r15
0x140014ac7  sub     rsp, 108h
0x140014ace  mov     rax, cs:__security_cookie
0x140014ad5  xor     rax, rsp
0x140014ad8  mov     [rsp+128h+var_30], rax
0x140014ae0  mov     r14, r8
0x140014ae3  mov     esi, edx
0x140014ae5  mov     [rsp+128h+var_104], 1
0x140014aed  mov     [rsp+128h+var_108], 0
0x140014af2  call    cs:__imp_GetProcessHeap
0x140014af8  mov     rbx, rax
0x140014afb  xor     r9d, r9d; HeapInformationLength
0x140014afe  xor     r8d, r8d; HeapInformation
0x140014b01  lea     edx, [r9+1]; HeapInformationClass
0x140014b05  mov     rcx, rax; HeapHandle
0x140014b08  call    cs:__imp_HeapSetInformation
0x140014b0e  mov     [rsp+128h+HeapInformation], 2
0x140014b19  mov     r15d, 4
0x140014b1f  mov     r9d, r15d; HeapInformationLength
0x140014b22  lea     r8, [rsp+128h+HeapInformation]; HeapInformation
0x140014b2a  xor     edx, edx; HeapInformationClass
0x140014b2c  mov     rcx, rbx; HeapHandle
0x140014b2f  call    cs:__imp_HeapSetInformation
0x140014b35  mov     [rsp+128h+var_54], 0
0x140014b40  call    cs:__imp_GetCurrentProcess
0x140014b46  mov     rcx, rax
0x140014b49  mov     r9d, r15d
0x140014b4c  lea     r8, [rsp+128h+var_54]
0x140014b54  lea     ebx, [r15-1]
0x140014b58  mov     edx, ebx
0x140014b5a  call    cs:__imp_GetProcessMitigationPolicy
0x140014b60  test    eax, eax
0x140014b62  jz      loc_140014D80
0x140014b68  or      [rsp+128h+var_54], ebx
0x140014b6f  mov     r8, r15
0x140014b72  lea     rdx, [rsp+128h+var_54]
0x140014b7a  mov     ecx, ebx
0x140014b7c  call    cs:__imp_SetProcessMitigationPolicy
0x140014b82  test    eax, eax
0x140014b84  jz      loc_140014D99
0x140014b8a  mov     [rsp+128h+HeapInformation], 0
0x140014b95  call    cs:__imp_GetCurrentProcess
0x140014b9b  mov     rcx, rax
0x140014b9e  mov     r9, r15
0x140014ba1  lea     r8, [rsp+128h+HeapInformation]
0x140014ba9  mov     ebx, 6
0x140014bae  mov     edx, ebx
0x140014bb0  call    cs:__imp_GetProcessMitigationPolicy
0x140014bb6  test    eax, eax
0x140014bb8  jz      loc_140014DB2
0x140014bbe  or      [rsp+128h+HeapInformation], 1
0x140014bc6  mov     r8, r15
0x140014bc9  lea     rdx, [rsp+128h+HeapInformation]
0x140014bd1  mov     ecx, ebx
0x140014bd3  call    cs:__imp_SetProcessMitigationPolicy
0x140014bd9  test    eax, eax
0x140014bdb  jz      loc_140014DCB
0x140014be1  xor     ecx, ecx; lpModuleName
0x140014be3  call    cs:__imp_GetModuleHandleW
0x140014be9  lea     r15, ?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140014bf0  mov     cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA, r15; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x140014bf7  call    ?VmlDebugSetDefaultTraceFilter@@YAXXZ; VmlDebugSetDefaultTraceFilter(void)
0x140014bfc  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x140014c03  xchg    rax, cs:?g_TraceOutput@@3R6AXGPEBG@ZEA; void (*g_TraceOutput)(ushort,ushort const *)
0x140014c0a  mov     rcx, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140014c11  lea     rax, ?VmlpTraceWilFailure@@YAXAEBUFailureInfo@wil@@@Z; VmlpTraceWilFailure(wil::FailureInfo const &)
0x140014c18  test    rcx, rcx
0x140014c1b  jz      short loc_140014C26
0x140014c1d  cmp     rcx, rax
0x140014c20  jnz     loc_140014DE4
0x140014c26  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rax
0x140014c2d  mov     rbx, cs:ProviderId
0x140014c34  test    rbx, rbx
0x140014c37  jnz     short loc_140014C47
0x140014c39  lea     rbx, ?g_CExecSvcEtwTrace@@3U_VML_ETW_TRACE@@A; _VML_ETW_TRACE g_CExecSvcEtwTrace
0x140014c40  mov     cs:ProviderId, rbx
0x140014c47  call    ?Initalize@VmpModuleInfo@Vml@@SAXXZ; Vml::VmpModuleInfo::Initalize(void)
0x140014c4c  lea     r9, [rbx+10h]; RegHandle
0x140014c50  xor     r8d, r8d; CallbackContext
0x140014c53  lea     rdx, ?VmlEtwTraceFilterCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; EnableCallback
0x140014c5a  mov     rcx, rbx; ProviderId
0x140014c5d  call    cs:__imp_EventRegister
0x140014c63  test    eax, eax
0x140014c65  jnz     short loc_140014C8A
0x140014c67  lea     rax, ?VmlpEtwUnifiedTraceOutput@@YAXGPEBG@Z; VmlpEtwUnifiedTraceOutput(ushort,ushort const *)
0x140014c6e  xchg    rax, cs:?g_TraceOutput@@3R6AXGPEBG@ZEA; void (*g_TraceOutput)(ushort,ushort const *)
0x140014c75  mov     cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA, rbx; _VML_ETW_TRACE * g_VmlEtwTrace
0x140014c7c  lea     rax, ?VmlIsEtwTraceEnabled@@YAEG@Z; VmlIsEtwTraceEnabled(ushort)
0x140014c83  mov     cs:?g_TraceEventEnabled@@3P6AEG@ZEA, rax; uchar (*g_TraceEventEnabled)(ushort)
0x140014c8a  mov     rax, cs:?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140014c91  mov     rcx, r15
0x140014c94  mov     rax, [rax+30h]
0x140014c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c9d  test    rax, rax
0x140014ca0  jz      short loc_140014CBD
0x140014ca2  mov     rax, cs:?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140014ca9  mov     rcx, r15
0x140014cac  mov     rax, [rax+28h]
0x140014cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014cb5  mov     rcx, rax; CallbackContext
0x140014cb8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140014cbd  mov     rcx, [rsp+128h]; this
0x140014cc5  test    esi, esi
0x140014cc7  jle     loc_140014E01
0x140014ccd  mov     [rsp+128h+var_108], 1
0x140014cd2  lea     r8, [r14+8]; unsigned __int16 **
0x140014cd6  lea     edx, [rsi-1]; int
0x140014cd9  call    ?ProcessCommandLine@Service@Svc@CExec@@QEAAHHQEAPEAG@Z; CExec::Svc::Service::ProcessCommandLine(int,ushort * * const)
0x140014cde  test    eax, eax
0x140014ce0  jz      short loc_140014D37
0x140014ce2  mov     rcx, r15
0x140014ce5  call    ?GetServiceName@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<CExec::Svc::Service>::GetServiceName(void)
0x140014cea  mov     [rsp+128h+ServiceStartTable.lpServiceName], rax
0x140014cf2  lea     rax, ?ServiceMain@?$VmServiceModule@VService@Svc@CExec@@@Vml@@CAXKPEAPEAG@Z; Vml::VmServiceModule<CExec::Svc::Service>::ServiceMain(ulong,ushort * *)
0x140014cf9  mov     [rsp+128h+ServiceStartTable.lpServiceProc], rax
0x140014d01  mov     [rsp+128h+var_40], 0
0x140014d0d  mov     [rsp+128h+var_38], 0
0x140014d19  lea     rcx, [rsp+128h+ServiceStartTable]; lpServiceStartTable
0x140014d21  call    cs:__imp_StartServiceCtrlDispatcherW
0x140014d27  mov     rcx, [rsp+128h]; this
0x140014d2f  test    eax, eax
0x140014d31  jz      loc_140014E13
0x140014d37  mov     [rsp+128h+var_104], 0
0x140014d3f  jmp     short loc_140014D48
0x140014d41  cmp     [rsp+128h+var_108], 0
0x140014d46  jz      short loc_140014D5E
0x140014d48  mov     rax, cs:qword_14003A3B8
0x140014d4f  test    rax, rax
0x140014d52  jz      short loc_140014D59
0x140014d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d59  call    ?Finalize@?$VmModule@VService@Svc@CExec@@@Vml@@QEAAXXZ; Vml::VmModule<CExec::Svc::Service>::Finalize(void)
0x140014d5e  mov     eax, [rsp+128h+var_104]
0x140014d62  mov     rcx, [rsp+128h+var_30]
0x140014d6a  xor     rcx, rsp; StackCookie
0x140014d6d  call    __security_check_cookie
0x140014d72  add     rsp, 108h
0x140014d79  pop     r15
0x140014d7b  pop     r14
0x140014d7d  pop     rsi
0x140014d7e  pop     rbx
0x140014d7f  retn
0x140014d80  mov     rcx, [rsp+128h]; this
0x140014d88  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014d8f  mov     edx, 62Dh; void *
0x140014d94  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140014d99  mov     rcx, [rsp+128h]; this
0x140014da1  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014da8  mov     edx, 638h; void *
0x140014dad  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140014db2  mov     rcx, [rsp+128h]; this
0x140014dba  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014dc1  mov     edx, 647h; void *
0x140014dc6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140014dcb  mov     rcx, [rsp+128h]; this
0x140014dd3  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014dda  mov     edx, 651h; void *
0x140014ddf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140014de4  xor     edx, edx; Val
0x140014de6  mov     r8d, 98h; Size
0x140014dec  lea     rcx, [rsp+128h+var_F8]; void *
0x140014df1  call    memset_0
0x140014df6  lea     rcx, [rsp+128h+var_F8]; this
0x140014dfb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140014e01  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014e08  mov     edx, 0B33h; void *
0x140014e0d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140014e13  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140014e1a  mov     edx, 0B42h; void *
0x140014e1f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
