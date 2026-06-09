# ServiceStopCallback(void *,uchar)

- ea: `0x180010060`
- end: `0x18001018c`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `300`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x180009534`
- `0x18000d73c`
- `0x18000e808`
- `0x18000f7d0`
- `0x18000f838`
- `0x18000ff84`
- `0x180010060`
- `0x1800105b0`
- `0x180010708`
- `0x18001136c`
- `0x180026010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180010123`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180010123`

## string_xrefs

- `0x180010079`: `ServiceStopActivity`
- `0x1800100ef`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceStopCallback(void *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r8
  int v4; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  const char *v7; // r9
  int v8[84]; // [rsp+20h] [rbp-2B8h] BYREF
  struct tagComCallData v9[21]; // [rsp+170h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "ServiceStopActivity",
    a3);
  *(_QWORD *)&v9[0].dwDispid = &SharedPCAccountManagerTelemetry::ServiceStopActivity::`vftable';
  SharedPCAccountManagerTelemetry::ServiceStopActivity::StartActivity((SharedPCAccountManagerTelemetry::ServiceStopActivity *)v9);
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v8,
    "UnregisterObjectsActivity",
    v3);
  *(_QWORD *)v8 = &SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::`vftable';
  SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::StartActivity((SharedPCAccountManagerTelemetry::UnregisterObjectsActivity *)v8);
  try
  {
    v4 = qword_180036C08();
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
        (const char *)(unsigned int)v4,
        v8[0]);
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v8);
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    if ( !SetServiceStatus(g_serviceState, &ServiceStatus) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x88, v5, v6);
    ServiceState::Reset((ServiceState *)&g_serviceState);
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v9);
    SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::~UnregisterObjectsActivity((SharedPCAccountManagerTelemetry::UnregisterObjectsActivity *)v8);
    SharedPCAccountManagerTelemetry::ServiceStopActivity::~ServiceStopActivity(v9);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x8F,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x180010060  sub     rsp, 2D8h
0x180010067  mov     rax, cs:__security_cookie
0x18001006e  xor     rax, rsp
0x180010071  mov     [rsp+2D8h+var_18], rax
0x180010079  lea     rdx, aServicestopact; "ServiceStopActivity"
0x180010080  lea     rcx, [rsp+2D8h+var_168]
0x180010088  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001008d  lea     rax, ??_7ServiceStopActivity@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::ServiceStopActivity::`vftable'
0x180010094  mov     [rsp+2D8h+var_168], rax
0x18001009c  lea     rcx, [rsp+2D8h+var_168]; this
0x1800100a4  call    ?StartActivity@ServiceStopActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::ServiceStopActivity::StartActivity(void)
0x1800100a9  nop
0x1800100aa  lea     rdx, aUnregisterobje; "UnregisterObjectsActivity"
0x1800100b1  lea     rcx, [rsp+2D8h+var_2B8]
0x1800100b6  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800100bb  lea     rax, ??_7UnregisterObjectsActivity@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::`vftable'
0x1800100c2  mov     qword ptr [rsp+2D8h+var_2B8], rax; int
0x1800100c7  lea     rcx, [rsp+2D8h+var_2B8]; this
0x1800100cc  call    ?StartActivity@UnregisterObjectsActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::StartActivity(void)
0x1800100d1  nop
0x1800100d2  xor     ecx, ecx
0x1800100d4  mov     rax, cs:qword_180036C08
0x1800100db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e0  mov     rcx, [rsp+2D8h]; this
0x1800100e8  test    eax, eax
0x1800100ea  jns     short loc_180010100
0x1800100ec  mov     r9d, eax; char *
0x1800100ef  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800100f6  mov     edx, 83h; void *
0x1800100fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010100  lea     rcx, [rsp+2D8h+var_2B8]
0x180010105  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001010a  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x180010115  lea     rdx, ServiceStatus; lpServiceStatus
0x18001011c  mov     rcx, cs:?g_serviceState@@3VServiceState@@A; hServiceStatus
0x180010123  call    cs:__imp_SetServiceStatus
0x180010129  mov     rcx, [rsp+2D8h]; this
0x180010131  test    eax, eax
0x180010133  jnz     short loc_18001013F
0x180010135  mov     edx, 88h; void *
0x18001013a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001013f  lea     rcx, ?g_serviceState@@3VServiceState@@A; this
0x180010146  call    ?Reset@ServiceState@@QEAAXXZ; ServiceState::Reset(void)
0x18001014b  lea     rcx, [rsp+2D8h+var_168]
0x180010153  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010158  nop
0x180010159  lea     rcx, [rsp+2D8h+var_2B8]; this
0x18001015e  call    ??1UnregisterObjectsActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::~UnregisterObjectsActivity(void)
0x180010163  nop
0x180010164  lea     rcx, [rsp+2D8h+var_168]; this
0x18001016c  call    ??1ServiceStopActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::ServiceStopActivity::~ServiceStopActivity(void)
0x180010171  nop
0x180010172  jmp     short $+2
0x180010174  mov     rcx, [rsp+2D8h+var_18]
0x18001017c  xor     rcx, rsp; StackCookie
0x18001017f  call    __security_check_cookie
0x180010184  add     rsp, 2D8h
0x18001018b  retn
```
