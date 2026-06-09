# ServiceMainImpl(ushort const *,ServiceMainCallback *,ulong,ushort * *)

- ea: `0x1800212ac`
- end: `0x18002172d`
- name: `?ServiceMainImpl@@YAJPEBGPEAUServiceMainCallback@@KPEAPEAG@Z`
- size: `1153`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, struct ServiceMainCallback *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fe50`

## callees

- `0x1800026b0`
- `0x180010b64`
- `0x1800200cc`
- `0x180020f80`
- `0x1800212ac`
- `0x180021734`
- `0x180021764`
- `0x180023060`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213d1`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1800213c7`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1800213c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800216ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800216ae`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002148f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002148f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800215db`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800215db`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180021384`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002143e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180021563`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002161d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002166e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800216e6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180021384`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002143e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180021563`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002161d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002166e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800216e6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180021361`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180021361`

## string_xrefs

- `0x18002138a`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x1800213f1`: `onecoreuap\enduser\winstore\servicescommon\lib\commonsettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ServiceMainImpl(
        LPCWSTR lpServiceName,
        struct ServiceMainCallback *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  char v8; // al
  const char *v9; // r9
  signed int LastError; // eax
  signed int v11; // ebx
  DWORD v12; // esi
  const char *v13; // r9
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  const char *v19; // r9
  wil::details::in1diag3 *v20; // rcx
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  __int32 v23; // eax
  HRESULT v24; // eax
  DWORD v25; // ecx
  const char *v26; // r9
  DWORD v27; // ecx
  const char *v28; // r9
  const char *v29; // r9
  int lpdwindex; // [rsp+20h] [rbp-79h]
  DWORD dwindex; // [rsp+30h] [rbp-69h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-61h] BYREF
  void **Context; // [rsp+40h] [rbp-59h] BYREF
  __int64 v35; // [rsp+48h] [rbp-51h] BYREF
  int v36; // [rsp+50h] [rbp-49h]
  char v37; // [rsp+54h] [rbp-45h]
  char v38; // [rsp+55h] [rbp-44h]
  void *v39; // [rsp+58h] [rbp-41h]
  __int64 v40; // [rsp+60h] [rbp-39h]
  _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-31h] BYREF
  SERVICE_STATUS_HANDLE hServiceStatus; // [rsp+88h] [rbp-11h]
  struct ServiceMainCallback *v43; // [rsp+90h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v8 = (*(__int64 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  Context = &ProcessRefCount::`vftable';
  v35 = 0;
  v36 = 0;
  v37 = v8;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  hServiceStatus = 0;
  v43 = a2;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwControlsAccepted = 1;
  if ( (*(unsigned __int8 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 16LL))(a2) )
    ServiceStatus.dwControlsAccepted |= 0x1000u;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(lpServiceName, ServiceControlHandler, &Context);
  ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ++ServiceStatus.dwCheckPoint;
  ServiceStatus.dwWaitHint = 1000;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
      v9);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetImpl'::`2'::impl) )
  {
    dwindex = 1;
    if ( !(unsigned int)SetProcessMitigationPolicy(16, &dwindex) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\commonsettings.cpp",
          (const char *)(unsigned int)v11,
          lpdwindex);
        v12 = 1066;
LABEL_49:
        ServiceStatus.dwCurrentState = 1;
        ServiceStatus.dwServiceSpecificExitCode = v11;
        ServiceStatus.dwWin32ExitCode = v12;
        ++ServiceStatus.dwCheckPoint;
        ServiceStatus.dwWaitHint = 0;
        if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xC7,
            (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
            v29);
        goto LABEL_51;
      }
    }
  }
  if ( ShouldStoreComponentBeEnabled(lpServiceName) )
  {
    v11 = 0;
    (**(void (__fastcall ***)(struct ServiceMainCallback *, SERVICE_STATUS_HANDLE))a2)(a2, hServiceStatus);
    if ( (*(unsigned __int8 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 24LL))(a2) )
      v11 = CoInitializeEx(0, 0);
    v12 = 1066;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v11,
        lpdwindex);
LABEL_47:
      (**(void (__fastcall ***)(struct ServiceMainCallback *, _QWORD))a2)(a2, 0);
      if ( v11 >= 0 )
        v12 = 0;
      goto LABEL_49;
    }
    v14 = ProcessRefCount::Initialize(&Context);
    v11 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v14,
        lpdwindex);
      goto LABEL_45;
    }
    v15 = (*(__int64 (__fastcall **)(struct ServiceMainCallback *, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(
            a2,
            a3,
            a4);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v15,
        lpdwindex);
LABEL_44:
      LOBYTE(v16) = v38;
      (*(void (__fastcall **)(struct ServiceMainCallback *, __int64))(*(_QWORD *)a2 + 40LL))(a2, v16);
LABEL_45:
      if ( (*(unsigned __int8 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 24LL))(a2) )
        CoUninitialize();
      goto LABEL_47;
    }
    v17 = (*(__int64 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 48LL))(a2);
    v11 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v17,
        lpdwindex);
LABEL_40:
      LOBYTE(v18) = v38;
      (*(void (__fastcall **)(struct ServiceMainCallback *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v18);
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwServiceSpecificExitCode = v11;
      v27 = 1066;
      if ( v11 >= 0 )
        v27 = 0;
      ServiceStatus.dwWin32ExitCode = v27;
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwWaitHint = 1100;
      if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xC7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
          v28);
      goto LABEL_44;
    }
    ServiceStatus.dwCurrentState = 4;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    ++ServiceStatus.dwCheckPoint;
    ServiceStatus.dwWaitHint = 0;
    if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
      v11 = 0;
    else
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xC7,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
              v19);
    v20 = retaddr;
    if ( v11 >= 0 )
    {
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        v23 = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                      + 24LL))(Microsoft::WRL::Details::ModuleBase::module_);
      else
        v23 = 0;
      _InterlockedExchange((volatile __int32 *)&v35 + 1, v23);
      dwindex = 0;
      pHandles = v39;
      v24 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      v20 = retaddr;
      if ( v24 >= 0 )
        goto LABEL_36;
      v21 = (unsigned int)v24;
      v22 = 98;
    }
    else
    {
      v21 = (unsigned int)v11;
      v22 = 299;
    }
    wil::details::in1diag3::_Log_Hr(
      v20,
      (void *)v22,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
      (const char *)v21,
      lpdwindex);
LABEL_36:
    ServiceStatus.dwCurrentState = 3;
    ServiceStatus.dwServiceSpecificExitCode = v11;
    v25 = 1066;
    if ( v11 >= 0 )
      v25 = 0;
    ServiceStatus.dwWin32ExitCode = v25;
    ++ServiceStatus.dwCheckPoint;
    ServiceStatus.dwWaitHint = 1500;
    if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        v26);
    goto LABEL_40;
  }
  ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwServiceSpecificExitCode = -2147467259;
  ServiceStatus.dwWin32ExitCode = 1066;
  ++ServiceStatus.dwCheckPoint;
  ServiceStatus.dwWaitHint = 0;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
      v13);
  v11 = -2147467259;
LABEL_51:
  ProcessRefCount::~ProcessRefCount((ProcessRefCount *)&Context);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800212ac  push    rbp
0x1800212ae  push    rbx
0x1800212af  push    rsi
0x1800212b0  push    rdi
0x1800212b1  push    r12
0x1800212b3  push    r13
0x1800212b5  push    r14
0x1800212b7  push    r15
0x1800212b9  lea     rbp, [rsp-1Fh]
0x1800212be  sub     rsp, 0B8h
0x1800212c5  mov     rax, cs:__security_cookie
0x1800212cc  xor     rax, rsp
0x1800212cf  mov     [rbp+57h+var_50], rax
0x1800212d3  mov     r15, r9
0x1800212d6  mov     r14d, r8d
0x1800212d9  mov     rdi, rdx
0x1800212dc  mov     rsi, rcx
0x1800212df  mov     rax, [rdx]
0x1800212e2  mov     rcx, rdx
0x1800212e5  mov     rax, [rax+8]
0x1800212e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ee  lea     rcx, ??_7ProcessRefCount@@6B@; const ProcessRefCount::`vftable'
0x1800212f5  mov     [rbp+57h+Context], rcx
0x1800212f9  xor     r12d, r12d
0x1800212fc  mov     [rbp+57h+var_A8], r12
0x180021300  mov     [rbp+57h+var_A0], r12d
0x180021304  mov     [rbp+57h+var_9C], al
0x180021307  mov     [rbp+57h+var_9B], r12b
0x18002130b  mov     [rbp+57h+var_98], r12
0x18002130f  mov     [rbp+57h+var_90], r12
0x180021313  mov     [rbp+57h+hServiceStatus], r12
0x180021317  mov     [rbp+57h+var_60], rdi
0x18002131b  mov     [rbp+57h+ServiceStatus.dwServiceType], 20h ; ' '
0x180021322  lea     r13d, [r12+2]
0x180021327  mov     [rbp+57h+ServiceStatus.dwCurrentState], r13d
0x18002132b  lea     ebx, [r12+1]
0x180021330  mov     [rbp+57h+ServiceStatus.dwControlsAccepted], ebx
0x180021333  mov     rax, [rdi]
0x180021336  mov     rcx, rdi
0x180021339  mov     rax, [rax+10h]
0x18002133d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021342  test    al, al
0x180021344  jz      short loc_18002134B
0x180021346  bts     [rbp+57h+ServiceStatus.dwControlsAccepted], 0Ch
0x18002134b  mov     qword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], r12
0x18002134f  mov     qword ptr [rbp+57h+ServiceStatus.dwCheckPoint], r12
0x180021353  lea     r8, [rbp+57h+Context]; lpContext
0x180021357  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18002135e  mov     rcx, rsi; lpServiceName
0x180021361  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180021367  mov     [rbp+57h+hServiceStatus], rax
0x18002136b  mov     [rbp+57h+ServiceStatus.dwCurrentState], r13d
0x18002136f  mov     qword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], r12
0x180021373  add     [rbp+57h+ServiceStatus.dwCheckPoint], ebx
0x180021376  mov     [rbp+57h+ServiceStatus.dwWaitHint], 3E8h
0x18002137d  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180021381  mov     rcx, rax; hServiceStatus
0x180021384  call    cs:__imp_SetServiceStatus
0x18002138a  lea     r13, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\services"...
0x180021391  test    eax, eax
0x180021393  jnz     short loc_1800213A6
0x180021395  mov     rcx, [rbp+5Fh]; this
0x180021399  mov     r8, r13; unsigned int
0x18002139c  mov     edx, 0C7h; void *
0x1800213a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800213a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy> `wil::Feature<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetImpl(void)'::`2'::impl
0x1800213ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::__private_IsEnabled(void)
0x1800213b2  test    al, al
0x1800213b4  jz      short loc_180021411
0x1800213b6  mov     [rbp+57h+dwindex], ebx
0x1800213b9  mov     r8d, 4
0x1800213bf  lea     rdx, [rbp+57h+dwindex]
0x1800213c3  lea     ecx, [r8+0Ch]
0x1800213c7  call    cs:__imp_SetProcessMitigationPolicy
0x1800213cd  test    eax, eax
0x1800213cf  jnz     short loc_180021411
0x1800213d1  call    cs:__imp_GetLastError
0x1800213d7  mov     ebx, eax
0x1800213d9  test    eax, eax
0x1800213db  jle     short loc_1800213E6
0x1800213dd  movzx   ebx, ax
0x1800213e0  or      ebx, 80070000h
0x1800213e6  mov     rcx, [rbp+5Fh]; this
0x1800213ea  test    ebx, ebx
0x1800213ec  jns     short loc_18002140C
0x1800213ee  mov     r9d, ebx; char *
0x1800213f1  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x1800213f8  mov     edx, 46h ; 'F'; void *
0x1800213fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021402  mov     esi, 42Ah
0x180021407  jmp     loc_1800216CA
0x18002140c  mov     ebx, 1
0x180021411  mov     rcx, rsi; unsigned __int16 *
0x180021414  call    ?ShouldStoreComponentBeEnabled@@YA_NPEBG@Z; ShouldStoreComponentBeEnabled(ushort const *)
0x180021419  test    al, al
0x18002141b  jnz     short loc_180021463
0x18002141d  mov     [rbp+57h+ServiceStatus.dwCurrentState], ebx
0x180021420  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], 80004005h
0x180021427  mov     esi, 42Ah
0x18002142c  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], esi
0x18002142f  add     [rbp+57h+ServiceStatus.dwCheckPoint], ebx
0x180021432  mov     [rbp+57h+ServiceStatus.dwWaitHint], r12d
0x180021436  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18002143a  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x18002143e  call    cs:__imp_SetServiceStatus
0x180021444  test    eax, eax
0x180021446  jnz     short loc_180021459
0x180021448  mov     rcx, [rbp+5Fh]; this
0x18002144c  mov     r8, r13; unsigned int
0x18002144f  mov     edx, 0C7h; void *
0x180021454  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021459  mov     ebx, 80004005h
0x18002145e  jmp     loc_180021702
0x180021463  mov     ebx, r12d
0x180021466  mov     rax, [rdi]
0x180021469  mov     rdx, [rbp+57h+hServiceStatus]
0x18002146d  mov     rcx, rdi
0x180021470  mov     rax, [rax]
0x180021473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021478  mov     rax, [rdi]
0x18002147b  mov     rcx, rdi
0x18002147e  mov     rax, [rax+18h]
0x180021482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021487  test    al, al
0x180021489  jz      short loc_180021497
0x18002148b  xor     edx, edx; dwCoInit
0x18002148d  xor     ecx, ecx; pvReserved
0x18002148f  call    cs:__imp_CoInitializeEx
0x180021495  mov     ebx, eax
0x180021497  mov     rcx, [rbp+5Fh]; this
0x18002149b  mov     esi, 42Ah
0x1800214a0  test    ebx, ebx
0x1800214a2  jns     short loc_1800214B9
0x1800214a4  mov     r9d, ebx; char *
0x1800214a7  mov     r8, r13; unsigned int
0x1800214aa  mov     edx, 11Eh; void *
0x1800214af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800214b4  jmp     loc_1800216B4
0x1800214b9  lea     rcx, [rbp+57h+Context]; pv
0x1800214bd  call    ?Initialize@ProcessRefCount@@QEAAJXZ; ProcessRefCount::Initialize(void)
0x1800214c2  mov     ebx, eax
0x1800214c4  mov     rcx, [rbp+5Fh]; this
0x1800214c8  test    eax, eax
0x1800214ca  jns     short loc_1800214E1
0x1800214cc  mov     r9d, eax; char *
0x1800214cf  mov     r8, r13; unsigned int
0x1800214d2  mov     edx, 121h; void *
0x1800214d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800214dc  jmp     loc_18002169B
0x1800214e1  mov     rax, [rdi]
0x1800214e4  mov     r8, r15
0x1800214e7  mov     edx, r14d
0x1800214ea  mov     rcx, rdi
0x1800214ed  mov     rax, [rax+20h]
0x1800214f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214f6  mov     ebx, eax
0x1800214f8  mov     rcx, [rbp+5Fh]; this
0x1800214fc  test    eax, eax
0x1800214fe  jns     short loc_180021515
0x180021500  mov     r9d, eax; char *
0x180021503  mov     r8, r13; unsigned int
0x180021506  mov     edx, 124h; void *
0x18002150b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021510  jmp     loc_180021689
0x180021515  mov     rax, [rdi]
0x180021518  mov     rcx, rdi
0x18002151b  mov     rax, [rax+30h]
0x18002151f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021524  mov     ebx, eax
0x180021526  mov     rcx, [rbp+5Fh]; this
0x18002152a  mov     r14d, 3
0x180021530  test    eax, eax
0x180021532  jns     short loc_180021549
0x180021534  mov     r9d, eax; char *
0x180021537  mov     r8, r13; unsigned int
0x18002153a  mov     edx, 127h; void *
0x18002153f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021544  jmp     loc_180021638
0x180021549  mov     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x180021550  mov     qword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], r12
0x180021554  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x180021557  mov     [rbp+57h+ServiceStatus.dwWaitHint], r12d
0x18002155b  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18002155f  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x180021563  call    cs:__imp_SetServiceStatus
0x180021569  test    eax, eax
0x18002156b  jnz     short loc_180021582
0x18002156d  mov     rcx, [rbp+5Fh]; this
0x180021571  mov     r8, r13; unsigned int
0x180021574  mov     edx, 0C7h; void *
0x180021579  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002157e  mov     ebx, eax
0x180021580  jmp     short loc_180021585
0x180021582  mov     ebx, r12d
0x180021585  mov     rcx, [rbp+5Fh]
0x180021589  test    ebx, ebx
0x18002158b  jns     short loc_180021597
0x18002158d  mov     r9d, ebx
0x180021590  mov     edx, 12Bh
0x180021595  jmp     short loc_1800215F1
0x180021597  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002159e  test    rcx, rcx
0x1800215a1  jnz     short loc_1800215A8
0x1800215a3  mov     eax, r12d
0x1800215a6  jmp     short loc_1800215B4
0x1800215a8  mov     rax, [rcx]
0x1800215ab  mov     rax, [rax+18h]
0x1800215af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215b4  xchg    eax, dword ptr [rbp+57h+var_A8+4]
0x1800215b7  mov     [rbp+57h+dwindex], r12d
0x1800215bb  mov     rax, [rbp+57h+var_98]
0x1800215bf  mov     [rbp+57h+pHandles], rax
0x1800215c3  lea     rax, [rbp+57h+dwindex]
0x1800215c7  mov     qword ptr [rsp+0F0h+lpdwindex], rax; int
0x1800215cc  lea     r9, [rbp+57h+pHandles]; pHandles
0x1800215d0  mov     r8d, 1; cHandles
0x1800215d6  or      edx, 0FFFFFFFFh; dwTimeout
0x1800215d9  xor     ecx, ecx; dwFlags
0x1800215db  call    cs:__imp_CoWaitForMultipleHandles
0x1800215e1  mov     rcx, [rbp+5Fh]; this
0x1800215e5  test    eax, eax
0x1800215e7  jns     short loc_1800215F9
0x1800215e9  mov     r9d, eax; char *
0x1800215ec  mov     edx, 62h ; 'b'; void *
0x1800215f1  mov     r8, r13; unsigned int
0x1800215f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800215f9  mov     [rbp+57h+ServiceStatus.dwCurrentState], r14d
0x1800215fd  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], ebx
0x180021600  mov     ecx, esi
0x180021602  test    ebx, ebx
0x180021604  cmovns  ecx, r12d
0x180021608  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], ecx
0x18002160b  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x18002160e  mov     [rbp+57h+ServiceStatus.dwWaitHint], 5DCh
0x180021615  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180021619  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x18002161d  call    cs:__imp_SetServiceStatus
0x180021623  test    eax, eax
0x180021625  jnz     short loc_180021638
0x180021627  mov     rcx, [rbp+5Fh]; this
0x18002162b  mov     r8, r13; unsigned int
0x18002162e  mov     edx, 0C7h; void *
0x180021633  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021638  mov     rax, [rdi]
0x18002163b  mov     dl, [rbp+57h+var_9B]
0x18002163e  mov     rcx, rdi
0x180021641  mov     rax, [rax+48h]
0x180021645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002164a  mov     [rbp+57h+ServiceStatus.dwCurrentState], r14d
0x18002164e  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], ebx
0x180021651  mov     ecx, esi
0x180021653  test    ebx, ebx
0x180021655  cmovns  ecx, r12d
0x180021659  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], ecx
0x18002165c  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x18002165f  mov     [rbp+57h+ServiceStatus.dwWaitHint], 44Ch
0x180021666  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18002166a  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x18002166e  call    cs:__imp_SetServiceStatus
0x180021674  test    eax, eax
0x180021676  jnz     short loc_180021689
0x180021678  mov     rcx, [rbp+5Fh]; this
0x18002167c  mov     r8, r13; unsigned int
0x18002167f  mov     edx, 0C7h; void *
0x180021684  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021689  mov     rax, [rdi]
0x18002168c  mov     dl, [rbp+57h+var_9B]
0x18002168f  mov     rcx, rdi
0x180021692  mov     rax, [rax+28h]
0x180021696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002169b  mov     rax, [rdi]
0x18002169e  mov     rcx, rdi
0x1800216a1  mov     rax, [rax+18h]
0x1800216a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216aa  test    al, al
0x1800216ac  jz      short loc_1800216B4
0x1800216ae  call    cs:__imp_CoUninitialize
0x1800216b4  mov     rax, [rdi]
0x1800216b7  xor     edx, edx
0x1800216b9  mov     rcx, rdi
0x1800216bc  mov     rax, [rax]
0x1800216bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216c4  test    ebx, ebx
0x1800216c6  cmovns  esi, r12d
0x1800216ca  mov     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x1800216d1  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], ebx
0x1800216d4  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], esi
0x1800216d7  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x1800216da  mov     [rbp+57h+ServiceStatus.dwWaitHint], r12d
0x1800216de  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1800216e2  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x1800216e6  call    cs:__imp_SetServiceStatus
0x1800216ec  test    eax, eax
0x1800216ee  jnz     short loc_180021702
0x1800216f0  mov     r8, r13; unsigned int
0x1800216f3  mov     edx, 0C7h; void *
0x1800216f8  mov     rcx, [rbp+5Fh]; this
0x1800216fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021701  nop
0x180021702  lea     rcx, [rbp+57h+Context]; this
  ... truncated ...
```
