# ServiceMainInternal

- ea: `0x18000dda4`
- end: `0x18000e134`
- name: `ServiceMainInternal`
- size: `912`
- prototype: `__int64 __fastcall(int, LPCWSTR *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000dd70`

## callees

- `0x180006a4c`
- `0x180009cb8`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000c398`
- `0x18000c7dc`
- `0x18000cfe4`
- `0x18000d0e8`
- `0x18000dc5c`
- `0x18000dda4`
- `0x18000e62c`
- `0x18000e760`
- `0x18000e850`
- `0x18004d204`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000e07e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000e07e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000de78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000de78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000df63`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000df63`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000de1e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000de1e`
- `combase!__imp_CoGetSharedServiceId` at `0x18000df10`
- `combase!__imp_CoGetSharedServiceId` at `0x18000df10`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000dfcf`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000e065`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000dfcf`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000e065`

## string_xrefs

- `0x18000ddcd`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000de34`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000de8e`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000dee1`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000df23`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000df7b`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000e01a`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`
- `0x18000e045`: `onecoreuap\base\embedded\sys\lockdown\runtime\dllsrv\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall ServiceMainInternal(int a1, LPCWSTR *a2)
{
  unsigned int updated; // ebx
  __int64 v4; // rdx
  const char *v6; // r9
  HANDLE EventW; // rax
  const char *v8; // r9
  HANDLE v9; // rbx
  int LastError; // eax
  unsigned int v11; // eax
  int SharedServiceId; // eax
  HRESULT v13; // edi
  __int64 v14; // rdx
  Windows::Internal::AssignedAccess::MdmTaskWorker *v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 v19; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  HANDLE WaitHandle; // [rsp+40h] [rbp-30h] BYREF
  Windows::Internal::AssignedAccess::MdmTaskWorker *v23; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-20h] BYREF
  char v25; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  LPVOID v27; // [rsp+A8h] [rbp+38h] BYREF

  if ( !a1 )
  {
    updated = -2147024809;
    v4 = 329;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
      (const char *)updated,
      ppv);
    return updated;
  }
  if ( !qword_1800CF4F0 )
  {
    updated = -2147418113;
    v4 = 330;
    goto LABEL_3;
  }
  *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwServiceType = 16;
  hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceControlHandler, 0);
  if ( !hServiceStatus )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x151,
             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
             v6);
  updated = UpdateServiceStatus(2, 0, 30000);
  if ( (updated & 0x80000000) != 0 )
  {
    v4 = 339;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v9 = EventW;
  v24[0] = EventW;
  if ( !EventW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x157,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
                  v8);
LABEL_15:
    updated = LastError;
LABEL_31:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
    UpdateServiceStatus(1, 31, 0);
    return updated;
  }
  WaitHandle = 0;
  v11 = (*(__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, __int64 (__fastcall *)()))(qword_1800CF4F0 + 192))(
          &WaitHandle,
          *a2,
          EventW,
          StopService);
  if ( v11 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x167,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
                  (const char *)v11,
                  0);
    goto LABEL_15;
  }
  v24[1] = &WaitHandle;
  v25 = 1;
  SharedServiceId = CoGetSharedServiceId((char *)module + 16);
  v13 = SharedServiceId;
  if ( SharedServiceId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
      (const char *)(unsigned int)SharedServiceId,
      0);
LABEL_30:
    UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    updated = v13;
    goto LABEL_31;
  }
  v27 = 0;
  wil::com_ptr_t<IContextCallback,wil::err_returncode_policy>::reset(&v27);
  v13 = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &v27);
  if ( v13 < 0 )
  {
    v14 = 372;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
      (const char *)(unsigned int)v13,
      ppva);
LABEL_29:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v27);
    goto LABEL_30;
  }
  ppva = 5;
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *))(*(_QWORD *)v27 + 24LL))(
          v27,
          RegisterActivationFactoryCallback,
          0,
          &IID_IContextCallback);
  if ( v13 < 0 )
  {
    v14 = 378;
    goto LABEL_20;
  }
  v13 = CoRegisterServerShutdownDelay(v9, 10000);
  if ( v13 < 0 )
  {
    v14 = 380;
    goto LABEL_20;
  }
  v15 = (Windows::Internal::AssignedAccess::MdmTaskWorker *)operator new(0x28u);
  *(_QWORD *)v15 = 0;
  *((_QWORD *)v15 + 1) = 0;
  *((_QWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 3) = 0;
  *((_QWORD *)v15 + 4) = 0;
  v23 = v15;
  v16 = Windows::Internal::AssignedAccess::MdmTaskWorker::Restart(v15);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
      (const char *)(unsigned int)v16,
      5);
  v17 = UpdateServiceStatus(4, 0, 0);
  v13 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\dllsrv\\servicemain.cpp",
      (const char *)(unsigned int)v17,
      ppva);
    std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>::~unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>(&v23);
    CoRegisterServerShutdownDelay(0, 0);
    goto LABEL_29;
  }
  v18 = qword_1800CF8F0;
  qword_1800CF8F0 = (__int64)v27;
  if ( v27 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hEvent,
    v9);
  v24[0] = 0;
  ::WaitHandle = WaitHandle;
  std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>::operator=<std::default_delete<Windows::Internal::AssignedAccess::MdmTaskWorker>,0>(
    v19,
    &v23);
  std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>::~unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>(&v23);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v27);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return 0;
}

```

## disassembly

```asm
0x18000dda4  mov     [rsp-18h+arg_8], rbx
0x18000dda9  push    rbp
0x18000ddaa  push    rsi
0x18000ddab  push    rdi
0x18000ddac  mov     rbp, rsp
0x18000ddaf  sub     rsp, 70h
0x18000ddb3  mov     rdi, rdx
0x18000ddb6  xor     esi, esi
0x18000ddb8  test    ecx, ecx
0x18000ddba  jnz     short loc_18000DDE0
0x18000ddbc  mov     ebx, 80070057h
0x18000ddc1  mov     edx, 149h; void *
0x18000ddc6  mov     rcx, [rbp+18h]; this
0x18000ddca  mov     r9d, ebx; char *
0x18000ddcd  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000ddd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddd9  mov     eax, ebx
0x18000dddb  jmp     loc_18000E124
0x18000dde0  cmp     cs:qword_1800CF4F0, rsi
0x18000dde7  jnz     short loc_18000DDF5
0x18000dde9  mov     ebx, 8000FFFFh
0x18000ddee  mov     edx, 14Ah
0x18000ddf3  jmp     short loc_18000DDC6
0x18000ddf5  xorps   xmm0, xmm0
0x18000ddf8  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x18000de00  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x18000de07  mov     cs:ServiceStatus.dwServiceType, 10h
0x18000de11  xor     r8d, r8d; lpContext
0x18000de14  lea     rdx, ServiceControlHandler; lpHandlerProc
0x18000de1b  mov     rcx, [rdi]; lpServiceName
0x18000de1e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000de24  mov     cs:hServiceStatus, rax
0x18000de2b  test    rax, rax
0x18000de2e  jnz     short loc_18000DE4A
0x18000de30  mov     rcx, [rbp+18h]; this
0x18000de34  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000de3b  mov     edx, 151h; void *
0x18000de40  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de45  jmp     loc_18000E124
0x18000de4a  xor     edx, edx
0x18000de4c  lea     ecx, [rdx+2]
0x18000de4f  mov     r8d, 7530h
0x18000de55  call    UpdateServiceStatus
0x18000de5a  mov     ebx, eax
0x18000de5c  test    eax, eax
0x18000de5e  jns     short loc_18000DE6A
0x18000de60  mov     edx, 153h
0x18000de65  jmp     loc_18000DDC6
0x18000de6a  mov     [rbp+arg_1], 1
0x18000de6e  xor     r9d, r9d; lpName
0x18000de71  xor     r8d, r8d; bInitialState
0x18000de74  xor     edx, edx; bManualReset
0x18000de76  xor     ecx, ecx; lpEventAttributes
0x18000de78  call    cs:__imp_CreateEventW
0x18000de7e  mov     rbx, rax
0x18000de81  mov     [rbp+var_20], rax
0x18000de85  test    rax, rax
0x18000de88  jnz     short loc_18000DEA1
0x18000de8a  mov     rcx, [rbp+18h]; this
0x18000de8e  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000de95  mov     edx, 157h; void *
0x18000de9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de9f  jmp     short loc_18000DEF2
0x18000dea1  mov     [rbp+WaitHandle], rsi
0x18000dea5  mov     rax, cs:qword_1800CF4F0
0x18000deac  mov     dword ptr [rsp+70h+var_48], 8
0x18000deb4  mov     [rsp+70h+ppv], rsi; int
0x18000deb9  lea     r9, StopService
0x18000dec0  mov     r8, rbx
0x18000dec3  mov     rdx, [rdi]
0x18000dec6  lea     rcx, [rbp+WaitHandle]
0x18000deca  mov     rax, [rax+0C0h]
0x18000ded1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded6  test    eax, eax
0x18000ded8  jz      short loc_18000DEF9
0x18000deda  mov     rcx, [rbp+18h]; this
0x18000dede  mov     r9d, eax; char *
0x18000dee1  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000dee8  mov     edx, 167h; void *
0x18000deed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000def2  mov     ebx, eax
0x18000def4  jmp     loc_18000E086
0x18000def9  lea     rax, [rbp+WaitHandle]
0x18000defd  mov     [rbp+var_18], rax
0x18000df01  mov     [rbp+var_10], 1
0x18000df05  mov     rcx, cs:?module@@3AEAVServiceModule@@EA; ServiceModule & module
0x18000df0c  add     rcx, 10h
0x18000df10  call    cs:__imp_CoGetSharedServiceId
0x18000df16  mov     edi, eax
0x18000df18  test    eax, eax
0x18000df1a  jns     short loc_18000DF39
0x18000df1c  mov     rcx, [rbp+18h]; this
0x18000df20  mov     r9d, eax; char *
0x18000df23  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000df2a  mov     edx, 16Ah; void *
0x18000df2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df34  jmp     loc_18000E076
0x18000df39  mov     [rbp+arg_18], rsi
0x18000df3d  lea     rcx, [rbp+arg_18]
0x18000df41  call    ?reset@?$com_ptr_t@UIContextCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IContextCallback,wil::err_returncode_policy>::reset(void)
0x18000df46  lea     rax, [rbp+arg_18]
0x18000df4a  mov     [rsp+70h+ppv], rax; int
0x18000df4f  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000df56  xor     edx, edx; pUnkOuter
0x18000df58  lea     r8d, [rdx+1]; dwClsContext
0x18000df5c  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000df63  call    cs:__imp_CoCreateInstance
0x18000df69  mov     edi, eax
0x18000df6b  test    eax, eax
0x18000df6d  jns     short loc_18000DF8C
0x18000df6f  mov     edx, 174h; void *
0x18000df74  mov     rcx, [rbp+18h]; this
0x18000df78  mov     r9d, edi; char *
0x18000df7b  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000df82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df87  jmp     loc_18000E06C
0x18000df8c  mov     rcx, [rbp+arg_18]
0x18000df90  mov     rax, [rcx]
0x18000df93  mov     [rsp+70h+var_48], rsi
0x18000df98  mov     dword ptr [rsp+70h+ppv], 5; int
0x18000dfa0  lea     r9, IID_IContextCallback
0x18000dfa7  xor     r8d, r8d
0x18000dfaa  lea     rdx, ?RegisterActivationFactoryCallback@@YAJPEAUtagComCallData@@@Z; RegisterActivationFactoryCallback(tagComCallData *)
0x18000dfb1  mov     rax, [rax+18h]
0x18000dfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfba  mov     edi, eax
0x18000dfbc  test    eax, eax
0x18000dfbe  jns     short loc_18000DFC7
0x18000dfc0  mov     edx, 17Ah
0x18000dfc5  jmp     short loc_18000DF74
0x18000dfc7  mov     edx, 2710h
0x18000dfcc  mov     rcx, rbx
0x18000dfcf  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000dfd5  mov     edi, eax
0x18000dfd7  test    eax, eax
0x18000dfd9  jns     short loc_18000DFE2
0x18000dfdb  mov     edx, 17Ch
0x18000dfe0  jmp     short loc_18000DF74
0x18000dfe2  mov     [rbp+arg_11], 1
0x18000dfe6  mov     ecx, 28h ; '('; Size
0x18000dfeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dff0  mov     [rax], rsi
0x18000dff3  mov     [rax+8], rsi
0x18000dff7  mov     [rax+10h], rsi
0x18000dffb  mov     [rax+18h], rsi
0x18000dfff  mov     [rax+20h], rsi
0x18000e003  mov     [rbp+var_28], rax
0x18000e007  mov     rcx, rax; this
0x18000e00a  call    ?Restart@MdmTaskWorker@AssignedAccess@Internal@Windows@@QEAAJXZ; Windows::Internal::AssignedAccess::MdmTaskWorker::Restart(void)
0x18000e00f  mov     rcx, [rbp+18h]; this
0x18000e013  test    eax, eax
0x18000e015  jns     short loc_18000E02B
0x18000e017  mov     r9d, eax; char *
0x18000e01a  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000e021  mov     edx, 180h; void *
0x18000e026  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e02b  xor     r8d, r8d
0x18000e02e  xor     edx, edx
0x18000e030  lea     ecx, [rdx+4]
0x18000e033  call    UpdateServiceStatus
0x18000e038  mov     edi, eax
0x18000e03a  test    eax, eax
0x18000e03c  jns     short loc_18000E0A4
0x18000e03e  mov     rcx, [rbp+18h]; this
0x18000e042  mov     r9d, eax; char *
0x18000e045  lea     r8, aOnecoreuapBase_88; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18000e04c  mov     edx, 182h; void *
0x18000e051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e056  nop
0x18000e057  lea     rcx, [rbp+var_28]
0x18000e05b  call    ??1?$unique_ptr@VMdmTaskWorker@AssignedAccess@Internal@Windows@@U?$default_delete@VMdmTaskWorker@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>::~unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>(void)
0x18000e060  nop
0x18000e061  xor     edx, edx
0x18000e063  xor     ecx, ecx
0x18000e065  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000e06b  nop
0x18000e06c  lea     rcx, [rbp+arg_18]
0x18000e070  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18000e075  nop
0x18000e076  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000e07a  mov     rcx, [rbp+WaitHandle]; WaitHandle
0x18000e07e  call    cs:__imp_UnregisterWaitEx
0x18000e084  mov     ebx, edi
0x18000e086  lea     rcx, [rbp+var_20]
0x18000e08a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e08f  nop
0x18000e090  xor     r8d, r8d
0x18000e093  lea     edx, [r8+1Fh]
0x18000e097  lea     ecx, [rdx-1Eh]
0x18000e09a  call    UpdateServiceStatus
0x18000e09f  jmp     loc_18000DDD9
0x18000e0a4  mov     rcx, [rbp+arg_18]
0x18000e0a8  mov     rdi, cs:qword_1800CF8F0
0x18000e0af  mov     cs:qword_1800CF8F0, rcx
0x18000e0b6  test    rcx, rcx
0x18000e0b9  jz      short loc_18000E0C7
0x18000e0bb  mov     rax, [rcx]
0x18000e0be  mov     rax, [rax+8]
0x18000e0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c7  test    rdi, rdi
0x18000e0ca  jz      short loc_18000E0DC
0x18000e0cc  mov     rax, [rdi]
0x18000e0cf  mov     rcx, rdi
0x18000e0d2  mov     rax, [rax+10h]
0x18000e0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0db  nop
0x18000e0dc  mov     rdx, rbx
0x18000e0df  lea     rcx, hEvent
0x18000e0e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e0eb  mov     [rbp+var_20], rsi
0x18000e0ef  mov     rax, [rbp+WaitHandle]
0x18000e0f3  mov     cs:WaitHandle, rax
0x18000e0fa  lea     rdx, [rbp+var_28]
0x18000e0fe  call    ??$?4U?$default_delete@VMdmTaskWorker@AssignedAccess@Internal@Windows@@@std@@$0A@@?$unique_ptr@VMdmTaskWorker@AssignedAccess@Internal@Windows@@U?$default_delete@VMdmTaskWorker@AssignedAccess@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>::operator=<std::default_delete<Windows::Internal::AssignedAccess::MdmTaskWorker>,0>(std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker> &&)
0x18000e103  nop
0x18000e104  lea     rcx, [rbp+var_28]
0x18000e108  call    ??1?$unique_ptr@VMdmTaskWorker@AssignedAccess@Internal@Windows@@U?$default_delete@VMdmTaskWorker@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>::~unique_ptr<Windows::Internal::AssignedAccess::MdmTaskWorker>(void)
0x18000e10d  nop
0x18000e10e  lea     rcx, [rbp+arg_18]
0x18000e112  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18000e117  nop
0x18000e118  lea     rcx, [rbp+var_20]
0x18000e11c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e121  nop
0x18000e122  xor     eax, eax
0x18000e124  mov     rbx, [rsp+70h+arg_8]
0x18000e12c  add     rsp, 70h
0x18000e130  pop     rdi
0x18000e131  pop     rsi
0x18000e132  pop     rbp
0x18000e133  retn
```
