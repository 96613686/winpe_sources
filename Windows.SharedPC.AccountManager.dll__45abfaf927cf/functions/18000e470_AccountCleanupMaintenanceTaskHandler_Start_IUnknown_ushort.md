# AccountCleanupMaintenanceTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x18000e470`
- end: `0x18000e6e0`
- name: `?Start@AccountCleanupMaintenanceTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `624`
- prototype: `__int64 __fastcall(AccountCleanupMaintenanceTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x180005120`
- `0x180007228`
- `0x180008a18`
- `0x180008a38`
- `0x180009534`
- `0x18000d73c`
- `0x18000d904`
- `0x18000e470`
- `0x18000e6e8`
- `0x18000e808`
- `0x180026010`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e517`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e517`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000e4c2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000e4c2`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000e581`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000e581`

## string_xrefs

- `0x18000e492`: `AccountCleanupMaintenanceTaskStartingActivity`
- `0x18000e4da`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`
- `0x18000e52f`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`
- `0x18000e593`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`
- `0x18000e60c`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`
- `0x18000e66f`: `shellcommon\shell\sharedpc\accountmanager\lib\service\accountcleanupmaintenancetaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall AccountCleanupMaintenanceTaskHandler::Start(
        AccountCleanupMaintenanceTaskHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  SC_HANDLE v4; // rax
  const char *v5; // r9
  unsigned int v6; // ebx
  SC_HANDLE v8; // rax
  const char *v9; // r9
  unsigned int v10; // ebx
  const char *v11; // r9
  unsigned int LastError; // ebx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17[2]; // [rsp+20h] [rbp-1A8h] BYREF
  SC_HANDLE v18; // [rsp+28h] [rbp-1A0h] BYREF
  SC_HANDLE v19; // [rsp+30h] [rbp-198h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-190h] BYREF
  _QWORD v21[42]; // [rsp+60h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "AccountCleanupMaintenanceTaskStartingActivity",
    a3);
  v21[0] = &SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::`vftable';
  SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::StartActivity((SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity *)v21);
  v4 = OpenSCManagerW(0, 0, 1u);
  v18 = v4;
  if ( v4 )
  {
    v8 = OpenServiceW(v4, L"shpamsvc", 0x100u);
    v19 = v8;
    if ( v8 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(v8, 0x80u, &ServiceStatus) )
      {
        *(_QWORD *)v17 = 0;
        QueryInterface = a2->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, int *))QueryInterface)(
                a2,
                &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
                v17);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v17 + 32LL))(*(_QWORD *)v17, 0);
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x20,
              (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaintenancetaskhandler.cpp",
              (const char *)(unsigned int)v16,
              v17[0]);
          wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v21);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
          SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity((SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity *)v21);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F,
            (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaintenancetaskhandler.cpp",
            (const char *)(unsigned int)v14,
            v17[0]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
          SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity((SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity *)v21);
          return v15;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1B,
                      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaintenanc"
                                    "etaskhandler.cpp",
                      v11);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
        SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity((SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity *)v21);
        return LastError;
      }
    }
    else
    {
      v10 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x15,
              (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaintenancetaskhandler.cpp",
              v9);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
      SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity((SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity *)v21);
      return v10;
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x12,
           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\accountcleanupmaintenancetaskhandler.cpp",
           v5);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
    SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity((SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity *)v21);
    return v6;
  }
}

```

## disassembly

```asm
0x18000e470  mov     [rsp+arg_0], rbx
0x18000e475  push    rdi
0x18000e476  sub     rsp, 1C0h
0x18000e47d  mov     rax, cs:__security_cookie
0x18000e484  xor     rax, rsp
0x18000e487  mov     [rsp+1C8h+var_18], rax
0x18000e48f  mov     rdi, rdx
0x18000e492  lea     rdx, aAccountcleanup; "AccountCleanupMaintenanceTaskStartingAc"...
0x18000e499  lea     rcx, [rsp+1C8h+var_168]
0x18000e49e  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e4a3  lea     rax, ??_7AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::`vftable'
0x18000e4aa  mov     [rsp+1C8h+var_168], rax
0x18000e4af  lea     rcx, [rsp+1C8h+var_168]; this
0x18000e4b4  call    ?StartActivity@AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::StartActivity(void)
0x18000e4b9  nop
0x18000e4ba  xor     edx, edx; lpDatabaseName
0x18000e4bc  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000e4c0  xor     ecx, ecx; lpMachineName
0x18000e4c2  call    cs:__imp_OpenSCManagerW
0x18000e4c8  mov     [rsp+1C8h+var_1A0], rax
0x18000e4cd  test    rax, rax
0x18000e4d0  jnz     short loc_18000E507
0x18000e4d2  mov     rcx, [rsp+1C8h]; this
0x18000e4da  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000e4e1  lea     edx, [rax+12h]; void *
0x18000e4e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e4e9  mov     ebx, eax
0x18000e4eb  lea     rcx, [rsp+1C8h+var_1A0]
0x18000e4f0  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e4f5  nop
0x18000e4f6  lea     rcx, [rsp+1C8h+var_168]; this
0x18000e4fb  call    ??1AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity(void)
0x18000e500  mov     eax, ebx
0x18000e502  jmp     loc_18000E6BE
0x18000e507  mov     r8d, 100h; dwDesiredAccess
0x18000e50d  lea     rdx, ServiceName; "shpamsvc"
0x18000e514  mov     rcx, rax; hSCManager
0x18000e517  call    cs:__imp_OpenServiceW
0x18000e51d  mov     [rsp+1C8h+var_198], rax
0x18000e522  test    rax, rax
0x18000e525  jnz     short loc_18000E567
0x18000e527  mov     rcx, [rsp+1C8h]; this
0x18000e52f  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000e536  lea     edx, [rax+15h]; void *
0x18000e539  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e53e  mov     ebx, eax
0x18000e540  lea     rcx, [rsp+1C8h+var_198]
0x18000e545  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e54a  nop
0x18000e54b  lea     rcx, [rsp+1C8h+var_1A0]
0x18000e550  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e555  nop
0x18000e556  lea     rcx, [rsp+1C8h+var_168]; this
0x18000e55b  call    ??1AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity(void)
0x18000e560  mov     eax, ebx
0x18000e562  jmp     loc_18000E6BE
0x18000e567  xorps   xmm0, xmm0
0x18000e56a  movups  xmmword ptr [rsp+1C8h+ServiceStatus.dwServiceType], xmm0
0x18000e56f  movups  xmmword ptr [rsp+1C8h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000e574  lea     r8, [rsp+1C8h+ServiceStatus]; lpServiceStatus
0x18000e579  mov     edx, 80h; dwControl
0x18000e57e  mov     rcx, rax; hService
0x18000e581  call    cs:__imp_ControlService
0x18000e587  test    eax, eax
0x18000e589  jnz     short loc_18000E5CB
0x18000e58b  mov     rcx, [rsp+1C8h]; this
0x18000e593  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000e59a  lea     edx, [rax+1Bh]; void *
0x18000e59d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e5a2  mov     ebx, eax
0x18000e5a4  lea     rcx, [rsp+1C8h+var_198]
0x18000e5a9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e5ae  nop
0x18000e5af  lea     rcx, [rsp+1C8h+var_1A0]
0x18000e5b4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e5b9  nop
0x18000e5ba  lea     rcx, [rsp+1C8h+var_168]; this
0x18000e5bf  call    ??1AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity(void)
0x18000e5c4  mov     eax, ebx
0x18000e5c6  jmp     loc_18000E6BE
0x18000e5cb  mov     qword ptr [rsp+1C8h+var_1A8], 0; int
0x18000e5d4  mov     rax, [rdi]
0x18000e5d7  mov     rbx, [rax]
0x18000e5da  lea     rcx, [rsp+1C8h+var_1A8]
0x18000e5df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e5e4  lea     r8, [rsp+1C8h+var_1A8]
0x18000e5e9  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000e5f0  mov     rcx, rdi
0x18000e5f3  mov     rax, rbx
0x18000e5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5fb  mov     ebx, eax
0x18000e5fd  test    eax, eax
0x18000e5ff  jns     short loc_18000E64D
0x18000e601  mov     rcx, [rsp+1C8h]; this
0x18000e609  mov     r9d, eax; char *
0x18000e60c  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000e613  mov     edx, 1Fh; void *
0x18000e618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e61d  nop
0x18000e61e  lea     rcx, [rsp+1C8h+var_1A8]
0x18000e623  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e628  nop
0x18000e629  lea     rcx, [rsp+1C8h+var_198]
0x18000e62e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e633  nop
0x18000e634  lea     rcx, [rsp+1C8h+var_1A0]
0x18000e639  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e63e  nop
0x18000e63f  lea     rcx, [rsp+1C8h+var_168]; this
0x18000e644  call    ??1AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity(void)
0x18000e649  mov     eax, ebx
0x18000e64b  jmp     short loc_18000E6BE
0x18000e64d  mov     rcx, qword ptr [rsp+1C8h+var_1A8]
0x18000e652  mov     rax, [rcx]
0x18000e655  xor     edx, edx
0x18000e657  mov     rax, [rax+20h]
0x18000e65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e660  mov     rcx, [rsp+1C8h]; this
0x18000e668  test    eax, eax
0x18000e66a  jns     short loc_18000E680
0x18000e66c  mov     r9d, eax; char *
0x18000e66f  lea     r8, aShellcommonShe_16; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000e676  mov     edx, 20h ; ' '; void *
0x18000e67b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e680  lea     rcx, [rsp+1C8h+var_168]
0x18000e685  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e68a  nop
0x18000e68b  lea     rcx, [rsp+1C8h+var_1A8]
0x18000e690  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e695  nop
0x18000e696  lea     rcx, [rsp+1C8h+var_198]
0x18000e69b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e6a0  nop
0x18000e6a1  lea     rcx, [rsp+1C8h+var_1A0]
0x18000e6a6  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000e6ab  nop
0x18000e6ac  lea     rcx, [rsp+1C8h+var_168]; this
0x18000e6b1  call    ??1AccountCleanupMaintenanceTaskStartingActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::AccountCleanupMaintenanceTaskStartingActivity::~AccountCleanupMaintenanceTaskStartingActivity(void)
0x18000e6b6  xor     eax, eax
0x18000e6b8  jmp     short loc_18000E6BE
0x18000e6ba  mov     eax, [rsp+1C8h+var_1A8]
0x18000e6be  mov     rcx, [rsp+1C8h+var_18]
0x18000e6c6  xor     rcx, rsp; StackCookie
0x18000e6c9  call    __security_check_cookie
0x18000e6ce  mov     rbx, [rsp+1C8h+arg_0]
0x18000e6d6  add     rsp, 1C0h
0x18000e6dd  pop     rdi
0x18000e6de  retn
```
