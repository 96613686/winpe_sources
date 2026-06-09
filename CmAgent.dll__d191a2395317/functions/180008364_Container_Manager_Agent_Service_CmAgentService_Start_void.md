# Container::Manager::Agent::Service::CmAgentService::Start(void)

- ea: `0x180008364`
- end: `0x180008640`
- name: `?Start@CmAgentService@Service@Agent@Manager@Container@@QEAAJXZ`
- size: `732`
- prototype: `__int64 __fastcall(RPC_BINDING_VECTOR *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009a60`

## callees

- `0x180002c48`
- `0x1800045e4`
- `0x180007b2c`
- `0x180007b4c`
- `0x180008364`
- `0x18000a768`
- `0x1800171d8`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000854f`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000854f`
- `RPCRT4!RpcServerRegisterIf3` at `0x180008506`
- `RPCRT4!RpcServerRegisterIf3` at `0x180008506`
- `RPCRT4!RpcEpRegisterW` at `0x180008531`
- `RPCRT4!RpcEpRegisterW` at `0x180008531`
- `RPCRT4!RpcServerInqBindings` at `0x1800084b5`
- `RPCRT4!RpcServerInqBindings` at `0x1800084b5`
- `RPCRT4!RpcBindingVectorFree` at `0x180008586`
- `RPCRT4!RpcBindingVectorFree` at `0x1800085c6`
- `RPCRT4!RpcBindingVectorFree` at `0x180008586`
- `RPCRT4!RpcBindingVectorFree` at `0x1800085c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800083b4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008610`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800083b4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008610`
- `SYSNTFY!SysNotifyStartServer` at `0x18000845d`
- `SYSNTFY!SysNotifyStartServer` at `0x18000845d`

## string_xrefs

- `0x1800083cd`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x1800083f2`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x180008567`: `onecore\base\gendrv\silos\clem\rpc\common\rpcutilities.cpp`
- `0x18000848d`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180008471`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180008456`: `CmAgent`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Service::CmAgentService::Start(RPC_BINDING_VECTOR *this)
{
  Container::Manager::Agent::Core *v1; // rcx
  const char *v2; // r9
  __int64 v3; // rdx
  int v5; // ebx
  __int64 v6; // rdx
  Container::Manager::Agent::Core::Details::FirstBootExperienceManager *v7; // rbx
  int started; // eax
  int v9; // eax
  unsigned int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  RPC_BINDING_VECTOR *v15; // rdi
  RPC_BINDING_VECTOR *v16; // rsi
  DWORD LastError; // eax
  DWORD v18; // ebx
  unsigned int v19; // [rsp+20h] [rbp-59h]
  int v20; // [rsp+40h] [rbp-39h] BYREF
  unsigned int (*v21)(void *, struct _SN_ONCREATESESSION_PARAMS *); // [rsp+48h] [rbp-31h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+E0h] [rbp+67h] BYREF
  RPC_BINDING_VECTOR *v24; // [rsp+E8h] [rbp+6Fh] BYREF

  BindingVector = this;
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 5000;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    v3 = 153;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
             v2);
  }
  v5 = Container::Manager::Agent::Core::Initialize(v1);
  if ( v5 < 0 )
  {
    v6 = 157;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
      (const char *)(unsigned int)v5,
      v19);
    return (unsigned int)v5;
  }
  v7 = qword_18004B978;
  byte_18004B1B8 = 1;
  if ( qword_18004B978 )
  {
    memset_0(&v20, 0, 0x80u);
    v20 = 1;
    v21 = Container::Manager::Agent::Core::Details::FirstBootExperienceManager::OnCreateSession;
    v19 = (_DWORD)v7 + 8;
    started = SysNotifyStartServer("CmAgent", 128, &v20, v7);
    if ( started < 0 )
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x99,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
             (const char *)(unsigned int)started,
             v19);
      v5 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F2,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)(unsigned int)v9,
          v19);
        v6 = 160;
        goto LABEL_6;
      }
    }
  }
  BindingVector = 0;
  v10 = RpcServerInqBindings(&BindingVector);
  if ( v10 )
  {
    v11 = v10;
    v12 = 187;
  }
  else
  {
    v19 = 1234;
    v13 = RpcServerRegisterIf3(IfSpec, 0, 0, 17);
    if ( v13 )
    {
      v11 = v13;
      v12 = 197;
    }
    else
    {
      v14 = RpcEpRegisterW(IfSpec, BindingVector, 0, 0);
      if ( !v14 )
      {
        v15 = (RPC_BINDING_VECTOR *)qword_18004B1C8;
        v16 = BindingVector;
        if ( qword_18004B1C8 )
        {
          LastError = GetLastError();
          v24 = v15;
          v18 = LastError;
          RpcBindingVectorFree(&v24);
          SetLastError(v18);
        }
        qword_18004B1C8 = (__int64)v16;
        goto LABEL_24;
      }
      RpcServerUnregisterIfEx(IfSpec, 0, 0);
      v11 = v14;
      v12 = 211;
    }
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v12,
         (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\rpcutilities.cpp",
         (const char *)v11,
         v19);
  if ( BindingVector )
  {
    v24 = BindingVector;
    RpcBindingVectorFree(&v24);
  }
  if ( v5 < 0 )
  {
    v6 = 165;
    goto LABEL_6;
  }
LABEL_24:
  byte_18004B1D0 = 1;
  ServiceStatus.dwControlsAccepted = 1;
  ServiceStatus.dwCurrentState = 4;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    v3 = 173;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
             v2);
  }
  return 0;
}

```

## disassembly

```asm
0x180008364  mov     [rsp-8+arg_10], rbx
0x180008369  mov     [rsp-8+BindingVector], rcx
0x18000836e  push    rbp
0x18000836f  push    rsi
0x180008370  push    rdi
0x180008371  lea     rbp, [rsp-47h]
0x180008376  sub     rsp, 0C0h
0x18000837d  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180008384  lea     rdx, ServiceStatus; lpServiceStatus
0x18000838b  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180008395  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x1800083a0  mov     cs:ServiceStatus.dwCheckPoint, 0
0x1800083aa  mov     cs:ServiceStatus.dwWaitHint, 1388h
0x1800083b4  call    cs:__imp_SetServiceStatus
0x1800083bb  nop     dword ptr [rax+rax+00h]
0x1800083c0  test    eax, eax
0x1800083c2  jnz     short loc_1800083DE
0x1800083c4  mov     edx, 99h; void *
0x1800083c9  mov     rcx, [rbp+5Fh]; this
0x1800083cd  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800083d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800083d9  jmp     loc_18000862C
0x1800083de  call    ?Initialize@Core@Agent@Manager@Container@@YAJXZ; Container::Manager::Agent::Core::Initialize(void)
0x1800083e3  mov     ebx, eax
0x1800083e5  test    eax, eax
0x1800083e7  jns     short loc_180008408
0x1800083e9  mov     edx, 9Dh; void *
0x1800083ee  mov     rcx, [rbp+5Fh]; this
0x1800083f2  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800083f9  mov     r9d, ebx; char *
0x1800083fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008401  mov     eax, ebx
0x180008403  jmp     loc_18000862C
0x180008408  mov     rbx, cs:qword_18004B978
0x18000840f  mov     cs:byte_18004B1B8, 1
0x180008416  test    rbx, rbx
0x180008419  jz      loc_1800084A9
0x18000841f  mov     edi, 80h
0x180008424  lea     rcx, [rbp+57h+var_90]; void *
0x180008428  mov     r8d, edi; Size
0x18000842b  xor     edx, edx; Val
0x18000842d  call    memset_0
0x180008432  lea     rax, ?OnCreateSession@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@CAKPEAXPEAU_SN_ONCREATESESSION_PARAMS@@@Z; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::OnCreateSession(void *,_SN_ONCREATESESSION_PARAMS *)
0x180008439  mov     [rbp+57h+var_90], 1
0x180008440  mov     [rbp+57h+var_88], rax
0x180008444  lea     r8, [rbp+57h+var_90]
0x180008448  lea     rax, [rbx+8]
0x18000844c  mov     r9, rbx
0x18000844f  mov     edx, edi
0x180008451  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180008456  lea     rcx, aCmagent_0; "CmAgent"
0x18000845d  call    cs:__imp_SysNotifyStartServer
0x180008464  nop     dword ptr [rax+rax+00h]
0x180008469  test    eax, eax
0x18000846b  jns     short loc_1800084A9
0x18000846d  mov     rcx, [rbp+5Fh]; this
0x180008471  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180008478  mov     r9d, eax; char *
0x18000847b  lea     edx, [rdi+19h]; void *
0x18000847e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180008483  mov     ebx, eax
0x180008485  test    eax, eax
0x180008487  jns     short loc_1800084A9
0x180008489  mov     rcx, [rbp+5Fh]; this
0x18000848d  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180008494  mov     r9d, eax; char *
0x180008497  mov     edx, 1F2h; void *
0x18000849c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084a1  lea     edx, [rdi+20h]
0x1800084a4  jmp     loc_1800083EE
0x1800084a9  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x1800084ad  mov     [rbp+57h+BindingVector], 0
0x1800084b5  call    cs:__imp_RpcServerInqBindings
0x1800084bc  nop     dword ptr [rax+rax+00h]
0x1800084c1  test    eax, eax
0x1800084c3  jz      short loc_1800084D2
0x1800084c5  mov     r9d, eax
0x1800084c8  mov     edx, 0BBh
0x1800084cd  jmp     loc_180008563
0x1800084d2  mov     rcx, cs:IfSpec
0x1800084d9  mov     r9d, 11h
0x1800084df  mov     [rsp+0D0h+var_98], 0
0x1800084e8  xor     r8d, r8d
0x1800084eb  mov     [rsp+0D0h+var_A0], 0
0x1800084f4  xor     edx, edx
0x1800084f6  mov     [rsp+0D0h+var_A8], 0
0x1800084fe  mov     [rsp+0D0h+var_B0], 4D2h; unsigned int
0x180008506  call    cs:__imp_RpcServerRegisterIf3
0x18000850d  nop     dword ptr [rax+rax+00h]
0x180008512  test    eax, eax
0x180008514  jz      short loc_180008520
0x180008516  mov     r9d, eax
0x180008519  mov     edx, 0C5h
0x18000851e  jmp     short loc_180008563
0x180008520  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x180008524  xor     r9d, r9d; Annotation
0x180008527  mov     rcx, cs:IfSpec; IfSpec
0x18000852e  xor     r8d, r8d; UuidVector
0x180008531  call    cs:__imp_RpcEpRegisterW
0x180008538  nop     dword ptr [rax+rax+00h]
0x18000853d  mov     ebx, eax
0x18000853f  test    eax, eax
0x180008541  jz      short loc_1800085A0
0x180008543  mov     rcx, cs:IfSpec; IfSpec
0x18000854a  xor     r8d, r8d; RundownContextHandles
0x18000854d  xor     edx, edx; MgrTypeUuid
0x18000854f  call    cs:__imp_RpcServerUnregisterIfEx
0x180008556  nop     dword ptr [rax+rax+00h]
0x18000855b  mov     r9d, ebx; char *
0x18000855e  mov     edx, 0D3h; void *
0x180008563  mov     rcx, [rbp+5Fh]; this
0x180008567  lea     r8, aOnecoreBaseGen_9; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000856e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008573  mov     ebx, eax
0x180008575  mov     rax, [rbp+57h+BindingVector]
0x180008579  test    rax, rax
0x18000857c  jz      short loc_180008592
0x18000857e  lea     rcx, [rbp+57h+arg_8]; BindingVector
0x180008582  mov     [rbp+57h+arg_8], rax
0x180008586  call    cs:__imp_RpcBindingVectorFree
0x18000858d  nop     dword ptr [rax+rax+00h]
0x180008592  test    ebx, ebx
0x180008594  jns     short loc_1800085E7
0x180008596  mov     edx, 0A5h
0x18000859b  jmp     loc_1800083EE
0x1800085a0  mov     rdi, cs:qword_18004B1C8
0x1800085a7  mov     rsi, [rbp+57h+BindingVector]
0x1800085ab  test    rdi, rdi
0x1800085ae  jz      short loc_1800085E0
0x1800085b0  call    cs:__imp_GetLastError
0x1800085b7  nop     dword ptr [rax+rax+00h]
0x1800085bc  lea     rcx, [rbp+57h+arg_8]; BindingVector
0x1800085c0  mov     [rbp+57h+arg_8], rdi
0x1800085c4  mov     ebx, eax
0x1800085c6  call    cs:__imp_RpcBindingVectorFree
0x1800085cd  nop     dword ptr [rax+rax+00h]
0x1800085d2  mov     ecx, ebx; dwErrCode
0x1800085d4  call    cs:__imp_SetLastError
0x1800085db  nop     dword ptr [rax+rax+00h]
0x1800085e0  mov     cs:qword_18004B1C8, rsi
0x1800085e7  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800085ee  lea     rdx, ServiceStatus; lpServiceStatus
0x1800085f5  mov     cs:byte_18004B1D0, 1
0x1800085fc  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x180008606  mov     cs:ServiceStatus.dwCurrentState, 4
0x180008610  call    cs:__imp_SetServiceStatus
0x180008617  nop     dword ptr [rax+rax+00h]
0x18000861c  test    eax, eax
0x18000861e  jnz     short loc_18000862A
0x180008620  mov     edx, 0ADh
0x180008625  jmp     loc_1800083C9
0x18000862a  xor     eax, eax
0x18000862c  mov     rbx, [rsp+0D0h+arg_10]
0x180008634  add     rsp, 0C0h
0x18000863b  pop     rdi
0x18000863c  pop     rsi
0x18000863d  pop     rbp
0x18000863e  retn
```
