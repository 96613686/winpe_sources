# Container::Manager::Service::CmsService::Start(void)

- ea: `0x180024704`
- end: `0x180024952`
- name: `?Start@CmsService@Service@Manager@Container@@QEAAJXZ`
- size: `590`
- prototype: `__int64 __fastcall(Container::Manager::Service::CmsService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180026440`

## callees

- `0x18000da68`
- `0x18000da88`
- `0x180024704`
- `0x1800260f0`
- `0x1800426d0`
- `0x180046320`
- `0x180191188`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800247c5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800247c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024829`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024838`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024858`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024867`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024829`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024838`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024858`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024867`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180024786`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180024786`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180024804`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180024804`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180024911`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180024911`

## string_xrefs

- `0x18002473a`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x180024792`: `onecore\base\gendrv\silos\clem\service\service.cpp`
- `0x1800247bb`: `cmservice`

## pseudocode

```c
__int64 __fastcall Container::Manager::Service::CmsService::Start(Container::Manager::Service::CmsService *this)
{
  Container::Manager::Core *v1; // rcx
  int updated; // edi
  __int64 v3; // rdx
  int v5; // edi
  SC_HANDLE v6; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rsi
  Container::Manager::Core *v9; // rcx
  SC_HANDLE v10; // rbp
  const char *v11; // r9
  const char *v12; // r9
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Container::Manager::Service::CmsService *Info; // [rsp+50h] [rbp+8h] BYREF

  Info = this;
  ServiceStatus.dwServiceType = 32;
  updated = Container::Manager::Service::CmsService::UpdateServiceStatus(this, 2u, 0x1388u, 0);
  if ( updated < 0 )
  {
    v3 = 218;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
      (const char *)(unsigned int)updated,
      v16);
    return (unsigned int)updated;
  }
  updated = Container::Manager::Core::Initialize(v1);
  if ( updated < 0 )
  {
    v3 = 222;
    goto LABEL_3;
  }
  byte_18021E4B4 = 1;
  v5 = *((_DWORD *)Container::Manager::Core::g_policyManager + 28);
  dword_18021E4B0 = v5;
  v6 = OpenSCManagerW(0, 0, 1u);
  v8 = v6;
  if ( v6 )
  {
    v10 = OpenServiceW(v6, L"cmservice", 2u);
    if ( v10 )
    {
      LODWORD(Info) = v5 + 30000;
      if ( ChangeServiceConfig2W(v10, 7u, &Info) )
      {
        CloseServiceHandle(v10);
        CloseServiceHandle(v8);
        goto LABEL_16;
      }
      updated = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6E,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                  v12);
      CloseServiceHandle(v10);
    }
    else
    {
      updated = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x66,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                  v11);
    }
    CloseServiceHandle(v8);
  }
  else
  {
    updated = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x5F,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                v7);
  }
  if ( updated < 0 )
  {
    v3 = 227;
    goto LABEL_3;
  }
LABEL_16:
  updated = Container::Manager::Core::Start(v9);
  if ( updated < 0 )
  {
    v3 = 229;
    goto LABEL_3;
  }
  updated = Container::Manager::Rpc::Server::Start(
              (Container::Manager::Rpc::Server *)&off_18021E4D8,
              qword_18021E4C8,
              v13);
  if ( updated < 0 )
  {
    v3 = 234;
    goto LABEL_3;
  }
  byte_18021E4E8 = 1;
  updated = Container::Manager::Rpc::Server::Start(
              (Container::Manager::Rpc::Server *)&off_18021E4F0,
              qword_18021E4D0,
              v14);
  if ( updated < 0 )
  {
    v3 = 240;
    goto LABEL_3;
  }
  byte_18021E500 = 1;
  ServiceStatus.dwControlsAccepted = 257;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwCurrentState = 4;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    updated = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x139,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                v15);
    if ( updated < 0 )
    {
      v3 = 244;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024704  mov     [rsp+Info], rcx
0x180024709  push    rbx
0x18002470a  push    rbp
0x18002470b  push    rsi
0x18002470c  push    rdi
0x18002470d  sub     rsp, 28h
0x180024711  xor     r9d, r9d; unsigned int
0x180024714  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18002471e  mov     r8d, 1388h; unsigned int
0x180024724  lea     ebp, [r9+2]
0x180024728  mov     edx, ebp; unsigned int
0x18002472a  call    ?UpdateServiceStatus@CmsService@Service@Manager@Container@@AEAAJKKK@Z; Container::Manager::Service::CmsService::UpdateServiceStatus(ulong,ulong,ulong)
0x18002472f  mov     edi, eax
0x180024731  test    eax, eax
0x180024733  jns     short loc_180024755
0x180024735  mov     edx, 0DAh; void *
0x18002473a  lea     r8, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180024741  mov     rcx, [rsp+48h]; this
0x180024746  mov     r9d, edi; char *
0x180024749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002474e  mov     eax, edi
0x180024750  jmp     loc_180024948
0x180024755  call    ?Initialize@Core@Manager@Container@@YAJXZ; Container::Manager::Core::Initialize(void)
0x18002475a  mov     edi, eax
0x18002475c  test    eax, eax
0x18002475e  jns     short loc_180024767
0x180024760  mov     edx, 0DEh
0x180024765  jmp     short loc_18002473A
0x180024767  mov     rax, cs:?g_policyManager@Core@Manager@Container@@3V?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@A; utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> Container::Manager::Core::g_policyManager
0x18002476e  xor     edx, edx; lpDatabaseName
0x180024770  mov     cs:byte_18021E4B4, 1
0x180024777  xor     ecx, ecx; lpMachineName
0x180024779  mov     edi, [rax+70h]
0x18002477c  lea     r8d, [rdx+1]; dwDesiredAccess
0x180024780  mov     cs:dword_18021E4B0, edi
0x180024786  call    cs:__imp_OpenSCManagerW
0x18002478d  nop     dword ptr [rax+rax+00h]
0x180024792  lea     rbx, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180024799  mov     rsi, rax
0x18002479c  test    rax, rax
0x18002479f  jnz     short loc_1800247B8
0x1800247a1  mov     rcx, [rsp+48h]; this
0x1800247a6  lea     edx, [rax+5Fh]; void *
0x1800247a9  mov     r8, rbx; unsigned int
0x1800247ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800247b1  mov     edi, eax
0x1800247b3  jmp     loc_180024844
0x1800247b8  mov     r8d, ebp; dwDesiredAccess
0x1800247bb  lea     rdx, ServiceName; "cmservice"
0x1800247c2  mov     rcx, rsi; hSCManager
0x1800247c5  call    cs:__imp_OpenServiceW
0x1800247cc  nop     dword ptr [rax+rax+00h]
0x1800247d1  mov     rbp, rax
0x1800247d4  test    rax, rax
0x1800247d7  jnz     short loc_1800247ED
0x1800247d9  mov     rcx, [rsp+48h]; this
0x1800247de  lea     edx, [rax+66h]; void *
0x1800247e1  mov     r8, rbx; unsigned int
0x1800247e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800247e9  mov     edi, eax
0x1800247eb  jmp     short loc_180024835
0x1800247ed  lea     eax, [rdi+7530h]
0x1800247f3  mov     edx, 7; dwInfoLevel
0x1800247f8  lea     r8, [rsp+48h+Info]; lpInfo
0x1800247fd  mov     dword ptr [rsp+48h+Info], eax
0x180024801  mov     rcx, rbp; hService
0x180024804  call    cs:__imp_ChangeServiceConfig2W
0x18002480b  nop     dword ptr [rax+rax+00h]
0x180024810  test    eax, eax
0x180024812  jnz     short loc_180024855
0x180024814  mov     rcx, [rsp+48h]; this
0x180024819  lea     edx, [rax+6Eh]; void *
0x18002481c  mov     r8, rbx; unsigned int
0x18002481f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024824  mov     rcx, rbp; hSCObject
0x180024827  mov     edi, eax
0x180024829  call    cs:__imp_CloseServiceHandle
0x180024830  nop     dword ptr [rax+rax+00h]
0x180024835  mov     rcx, rsi; hSCObject
0x180024838  call    cs:__imp_CloseServiceHandle
0x18002483f  nop     dword ptr [rax+rax+00h]
0x180024844  test    edi, edi
0x180024846  jns     short loc_180024873
0x180024848  mov     r8, rbx
0x18002484b  mov     edx, 0E3h
0x180024850  jmp     loc_180024741
0x180024855  mov     rcx, rbp; hSCObject
0x180024858  call    cs:__imp_CloseServiceHandle
0x18002485f  nop     dword ptr [rax+rax+00h]
0x180024864  mov     rcx, rsi; hSCObject
0x180024867  call    cs:__imp_CloseServiceHandle
0x18002486e  nop     dword ptr [rax+rax+00h]
0x180024873  call    ?Start@Core@Manager@Container@@YAJXZ; Container::Manager::Core::Start(void)
0x180024878  mov     edi, eax
0x18002487a  test    eax, eax
0x18002487c  jns     short loc_18002488B
0x18002487e  mov     r8, rbx
0x180024881  mov     edx, 0E5h
0x180024886  jmp     loc_180024741
0x18002488b  mov     rdx, cs:qword_18021E4C8; void *
0x180024892  lea     rcx, off_18021E4D8; this
0x180024899  call    ?Start@Server@Rpc@Manager@Container@@QEAAJPEAXI@Z; Container::Manager::Rpc::Server::Start(void *,uint)
0x18002489e  mov     edi, eax
0x1800248a0  test    eax, eax
0x1800248a2  jns     short loc_1800248B1
0x1800248a4  mov     r8, rbx
0x1800248a7  mov     edx, 0EAh
0x1800248ac  jmp     loc_180024741
0x1800248b1  mov     rdx, cs:qword_18021E4D0; void *
0x1800248b8  lea     rcx, off_18021E4F0; this
0x1800248bf  mov     cs:byte_18021E4E8, 1
0x1800248c6  call    ?Start@Server@Rpc@Manager@Container@@QEAAJPEAXI@Z; Container::Manager::Rpc::Server::Start(void *,uint)
0x1800248cb  mov     edi, eax
0x1800248cd  test    eax, eax
0x1800248cf  jns     short loc_1800248DE
0x1800248d1  mov     r8, rbx
0x1800248d4  mov     edx, 0F0h
0x1800248d9  jmp     loc_180024741
0x1800248de  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800248e5  lea     rdx, ServiceStatus; lpServiceStatus
0x1800248ec  mov     cs:byte_18021E500, 1
0x1800248f3  mov     cs:ServiceStatus.dwControlsAccepted, 101h
0x1800248fd  mov     cs:ServiceStatus.dwCheckPoint, 0
0x180024907  mov     cs:ServiceStatus.dwCurrentState, 4
0x180024911  call    cs:__imp_SetServiceStatus
0x180024918  nop     dword ptr [rax+rax+00h]
0x18002491d  test    eax, eax
0x18002491f  jnz     short loc_180024946
0x180024921  mov     rcx, [rsp+48h]; this
0x180024926  mov     r8, rbx; unsigned int
0x180024929  mov     edx, 139h; void *
0x18002492e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024933  mov     edi, eax
0x180024935  test    eax, eax
0x180024937  jns     short loc_180024946
0x180024939  mov     r8, rbx
0x18002493c  mov     edx, 0F4h
0x180024941  jmp     loc_180024741
0x180024946  xor     eax, eax
0x180024948  add     rsp, 28h
0x18002494c  pop     rdi
0x18002494d  pop     rsi
0x18002494e  pop     rbp
0x18002494f  pop     rbx
0x180024950  retn
```
