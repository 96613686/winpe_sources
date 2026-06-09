# _lambda_25f85fa8dc0afc9a4b936628c59fdf50_::operator()

- ea: `0x18001338c`
- end: `0x18001371f`
- name: `_lambda_25f85fa8dc0afc9a4b936628c59fdf50_::operator()`
- size: `915`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033780`

## callees

- `0x180002958`
- `0x180011bd0`
- `0x18001326c`
- `0x18001338c`
- `0x180013728`
- `0x180027a4c`
- `0x180037710`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800473d8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001364c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001364c`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001351b`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001351b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800136a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800136a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800133be`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800133be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800135b4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800135b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001359e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001359e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180013499`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180013499`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800135dc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800135dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180013443`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180013443`

## string_xrefs

- `0x1800133df`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180013458`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800134a5`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180013527`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800135e8`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180013658`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800133ee`: `AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()`
- `0x180013467`: `AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()`
- `0x1800134b4`: `AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()`
- `0x180013536`: `AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()`
- `0x1800135f7`: `AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()`
- `0x180013667`: `AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()`
- `0x1800133fa`: `ResultFromWin32HandleMaybenull(CreateEventEx(nullptr, nullptr, 0, EVENT_MODIFY_STATE | SYNCHRONIZE), m_usersToProcessEvent.GetAddressOf())`
- `0x180013473`: `RegisterWaitForSingleObject(&waitHandle, m_usersToProcessEvent.Get(), &StaticProcessUserTaskCallback, this, INFINITE, WT_EXECUTEDEFAULT)`
- `0x1800134c0`: `Windows::Foundation::Initialize(WINRT_INIT_MULTITHREADED)`
- `0x180013542`: `CoInitializeSecurity(reinterpret_cast<PSECURITY_DESCRIPTOR>(const_cast<GUID*>(&appIdAppReadiness)), -1, nullptr, nullptr, RPC_C_AUTHN_LEVEL_PKT, RPC_C_IMP_LEVEL_IDENTIFY, nullptr, EOAC_NO_CUSTOM_MARSHAL | EOAC_DYNAMIC_CLOAKING | EOAC_DISABLE_AAA | EOAC_APPID, nullptr)`
- `0x180013673`: `ComDisconnectableObjectManager::Initialize()`

## pseudocode

```c
unsigned int __fastcall lambda_25f85fa8dc0afc9a4b936628c59fdf50_::operator()(PHANDLE *a1)
{
  PHANDLE v1; // rbx
  HANDLE Event; // rax
  int Error; // edx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // edx
  HRESULT v8; // edx
  AppReadiness::Service *v9; // rcx
  __int64 v10; // rax
  PHANDLE v11; // rbx
  HRESULT v12; // eax
  HSTRING v13; // rdi
  int ActivationFactory; // edx
  HRESULT Instance; // edx
  RTL_SRWLOCK *v16; // rbx
  PHANDLE v17; // r10
  void **v18; // r8
  void *v19; // r9
  unsigned int result; // eax
  HSTRING_HEADER pExceptionObject; // [rsp+50h] [rbp+7h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF

  v1 = *a1;
  Event = CreateEventExW(0, 0, 0, 0x100002u);
  v1[33] = Event;
  if ( Event )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  if ( Error < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      Error,
      "ResultFromWin32HandleMaybenull(CreateEventEx(nullptr, nullptr, 0, EVENT_MODIFY_STATE | SYNCHRONIZE), m_usersToProc"
      "essEvent.GetAddressOf())",
      "AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      101);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  if ( !RegisterWaitForSingleObject(a1[1], (*a1)[33], AppReadiness::StaticProcessUserTaskCallback, *a1, 0xFFFFFFFF, 0) )
  {
    v6 = ResultFromKnownLastError();
    v5 = (unsigned int)v6;
    if ( v6 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v6,
        "RegisterWaitForSingleObject(&waitHandle, m_usersToProcessEvent.Get(), &StaticProcessUserTaskCallback, this, INFI"
        "NITE, WT_EXECUTEDEFAULT)",
        "AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()",
        "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
        102);
      throw (Windows::HResultException *)&pExceptionObject;
    }
  }
  v7 = RoInitialize(1, v5);
  if ( v7 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v7,
      "Windows::Foundation::Initialize(WINRT_INIT_MULTITHREADED)",
      "AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      103);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v8 = CoInitializeSecurity(qword_1800824B8, -1, 0, 0, 4u, 2u, 0, 0x3048u, 0);
  if ( v8 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v8,
      "CoInitializeSecurity(reinterpret_cast<PSECURITY_DESCRIPTOR>(const_cast<GUID*>(&appIdAppReadiness)), -1, nullptr, n"
      "ullptr, RPC_C_AUTHN_LEVEL_PKT, RPC_C_IMP_LEVEL_IDENTIFY, nullptr, EOAC_NO_CUSTOM_MARSHAL | EOAC_DYNAMIC_CLOAKING |"
      " EOAC_DISABLE_AAA | EOAC_APPID, nullptr)",
      "AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      113);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  AppReadiness::Service::SetGlobalComOptions(v9);
  v10 = Microsoft::WRL::Details::OutOfProcModuleBase<AppReadiness::AppReadinessModule>::Create();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v11 = *a1;
  string = 0;
  v12 = WindowsCreateStringReference(
          L"Windows.Networking.Connectivity.NetworkInformation",
          0x32u,
          &pExceptionObject,
          &string);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  v13 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11 + 30);
  ActivationFactory = RoGetActivationFactory(v13, &GUID_5074f851_950d_4165_9c15_365619481eea, v11 + 30);
  if ( ActivationFactory < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      ActivationFactory,
      "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_Networking_Connectivity_NetworkInf"
      "ormation).Get(), &m_networkInfo)",
      "AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      121);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Windows::Internal::ComDisconnectableObjectManager::s_spContextCallback);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               &Windows::Internal::ComDisconnectableObjectManager::s_spContextCallback);
  if ( Instance < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      Instance,
      "ComDisconnectableObjectManager::Initialize()",
      "AppReadiness::Service::OnServiceStart::<lambda_25f85fa8dc0afc9a4b936628c59fdf50>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      122);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v16 = (RTL_SRWLOCK *)(*a1 + 19);
  AcquireSRWLockExclusive(v16);
  v17 = *a1;
  v18 = a1[1];
  v19 = *v18;
  *v18 = (*a1)[31];
  v17[31] = v19;
  if ( v16 )
    ReleaseSRWLockExclusive(v16);
  *((_DWORD *)*a1 + 5) = 4353;
  AppReadiness::ServiceHandle::SetStatus((AppReadiness::ServiceHandle *)*a1, 4u, 0, (unsigned int)v19, 0, 0);
  result = AppReadiness::System::GetMaxNonProgressIdlePulseCount();
  *((_DWORD *)*a1 + 70) = result;
  return result;
}

```

## disassembly

```asm
0x18001338c  push    rbp
0x18001338e  push    rbx
0x18001338f  push    rsi
0x180013390  push    rdi
0x180013391  lea     rbp, [rsp-3Fh]
0x180013396  sub     rsp, 88h
0x18001339d  mov     rax, cs:__security_cookie
0x1800133a4  xor     rax, rsp
0x1800133a7  mov     [rbp+57h+var_28], rax
0x1800133ab  mov     rbx, [rcx]
0x1800133ae  mov     rsi, rcx
0x1800133b1  xor     ecx, ecx; lpEventAttributes
0x1800133b3  mov     r9d, 100002h; dwDesiredAccess
0x1800133b9  xor     r8d, r8d; dwFlags
0x1800133bc  xor     edx, edx; lpName
0x1800133be  call    cs:__imp_CreateEventExW
0x1800133c4  mov     [rbx+108h], rax
0x1800133cb  test    rax, rax
0x1800133ce  jnz     short loc_1800133D9
0x1800133d0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800133d5  mov     edx, eax
0x1800133d7  jmp     short loc_1800133DB
0x1800133d9  xor     edx, edx; int
0x1800133db  test    edx, edx
0x1800133dd  jns     short loc_18001341B
0x1800133df  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800133e6  mov     [rsp+0A0h+dwFlags], 65h ; 'e'; int
0x1800133ee  lea     r9, aAppreadinessSe_12; "AppReadiness::Service::OnServiceStart::"...
0x1800133f5  mov     qword ptr [rsp+0A0h+dwMilliseconds], rax; char *
0x1800133fa  lea     r8, aResultfromwin3_7; "ResultFromWin32HandleMaybenull(CreateEv"...
0x180013401  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180013405  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18001340a  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013411  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013415  call    _CxxThrowException_0
0x18001341b  mov     rdx, [rsi]
0x18001341e  lea     r8, AppReadiness__StaticProcessUserTaskCallback; Callback
0x180013425  mov     rcx, [rsi+8]; phNewWaitObject
0x180013429  mov     r9, rdx; Context
0x18001342c  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x180013434  mov     [rsp+0A0h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18001343c  mov     rdx, [rdx+108h]; hObject
0x180013443  call    cs:__imp_RegisterWaitForSingleObject
0x180013449  test    eax, eax
0x18001344b  jnz     short loc_180013494
0x18001344d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180013452  mov     edx, eax; int
0x180013454  test    eax, eax
0x180013456  jns     short loc_180013494
0x180013458  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001345f  mov     [rsp+0A0h+dwFlags], 66h ; 'f'; int
0x180013467  lea     r9, aAppreadinessSe_12; "AppReadiness::Service::OnServiceStart::"...
0x18001346e  mov     qword ptr [rsp+0A0h+dwMilliseconds], rax; char *
0x180013473  lea     r8, aRegisterwaitfo; "RegisterWaitForSingleObject(&waitHandle"...
0x18001347a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001347e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013483  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001348a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001348e  call    _CxxThrowException_0
0x180013494  mov     ecx, 1
0x180013499  call    cs:__imp_RoInitialize
0x18001349f  mov     edx, eax; int
0x1800134a1  test    eax, eax
0x1800134a3  jns     short loc_1800134E1
0x1800134a5  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800134ac  mov     [rsp+0A0h+dwFlags], 67h ; 'g'; int
0x1800134b4  lea     r9, aAppreadinessSe_12; "AppReadiness::Service::OnServiceStart::"...
0x1800134bb  mov     qword ptr [rsp+0A0h+dwMilliseconds], rax; char *
0x1800134c0  lea     r8, aWindowsFoundat_10; "Windows::Foundation::Initialize(WINRT_I"...
0x1800134c7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800134cb  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800134d0  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800134d7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800134db  call    _CxxThrowException_0
0x1800134e1  mov     [rsp+0A0h+pReserved3], 0; pReserved3
0x1800134ea  lea     rcx, qword_1800824B8; pSecDesc
0x1800134f1  mov     [rsp+0A0h+dwCapabilities], 3048h; dwCapabilities
0x1800134f9  xor     r9d, r9d; pReserved1
0x1800134fc  mov     [rsp+0A0h+pAuthList], 0; pAuthList
0x180013505  xor     r8d, r8d; asAuthSvc
0x180013508  mov     [rsp+0A0h+dwFlags], 2; dwImpLevel
0x180013510  or      edx, 0FFFFFFFFh; cAuthSvc
0x180013513  mov     [rsp+0A0h+dwMilliseconds], 4; dwAuthnLevel
0x18001351b  call    cs:__imp_CoInitializeSecurity
0x180013521  mov     edx, eax; int
0x180013523  test    eax, eax
0x180013525  jns     short loc_180013563
0x180013527  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001352e  mov     [rsp+0A0h+dwFlags], 71h ; 'q'; int
0x180013536  lea     r9, aAppreadinessSe_12; "AppReadiness::Service::OnServiceStart::"...
0x18001353d  mov     qword ptr [rsp+0A0h+dwMilliseconds], rax; char *
0x180013542  lea     r8, aCoinitializese; "CoInitializeSecurity(reinterpret_cast<P"...
0x180013549  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001354d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013552  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013559  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001355d  call    _CxxThrowException_0
0x180013563  call    ?SetGlobalComOptions@Service@AppReadiness@@IEAAXXZ; AppReadiness::Service::SetGlobalComOptions(void)
0x180013568  call    ?Create@?$OutOfProcModuleBase@VAppReadinessModule@AppReadiness@@@Details@WRL@Microsoft@@SAAEAVAppReadinessModule@AppReadiness@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<AppReadiness::AppReadinessModule>::Create(void)
0x18001356d  mov     rdx, rax
0x180013570  mov     rcx, [rax]
0x180013573  mov     rax, [rcx+8]
0x180013577  mov     rcx, rdx
0x18001357a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001357f  mov     rbx, [rsi]
0x180013582  lea     r9, [rbp+57h+string]; string
0x180013586  lea     r8, [rbp+57h+pExceptionObject]; hstringHeader
0x18001358a  mov     [rbp+57h+string], 0
0x180013592  mov     edx, 32h ; '2'; length
0x180013597  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x18001359e  call    cs:__imp_WindowsCreateStringReference
0x1800135a4  test    eax, eax
0x1800135a6  jns     short loc_1800135BB
0x1800135a8  xor     r9d, r9d; lpArguments
0x1800135ab  xor     r8d, r8d; nNumberOfArguments
0x1800135ae  mov     ecx, eax; dwExceptionCode
0x1800135b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800135b4  call    cs:__imp_RaiseException
0x1800135ba  int     3; Trap to Debugger
0x1800135bb  mov     rdi, [rbp+57h+string]
0x1800135bf  lea     rcx, [rbx+0F0h]
0x1800135c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800135cb  lea     r8, [rbx+0F0h]
0x1800135d2  mov     rcx, rdi
0x1800135d5  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x1800135dc  call    cs:__imp_RoGetActivationFactory
0x1800135e2  mov     edx, eax; int
0x1800135e4  test    eax, eax
0x1800135e6  jns     short loc_180013624
0x1800135e8  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800135ef  mov     [rsp+0A0h+dwFlags], 79h ; 'y'; int
0x1800135f7  lea     r9, aAppreadinessSe_12; "AppReadiness::Service::OnServiceStart::"...
0x1800135fe  mov     qword ptr [rsp+0A0h+dwMilliseconds], rax; char *
0x180013603  lea     r8, aWindowsFoundat_9; "Windows::Foundation::GetActivationFacto"...
0x18001360a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001360e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013613  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001361a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001361e  call    _CxxThrowException_0
0x180013624  lea     rbx, ?s_spContextCallback@ComDisconnectableObjectManager@Internal@Windows@@0V?$ComPtr@UIContextCallback@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IContextCallback> Windows::Internal::ComDisconnectableObjectManager::s_spContextCallback
0x18001362b  mov     rcx, rbx
0x18001362e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013633  xor     edx, edx; pUnkOuter
0x180013635  mov     qword ptr [rsp+0A0h+dwMilliseconds], rbx; ppv
0x18001363a  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180013641  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180013648  lea     r8d, [rdx+1]; dwClsContext
0x18001364c  call    cs:__imp_CoCreateInstance
0x180013652  mov     edx, eax; int
0x180013654  test    eax, eax
0x180013656  jns     short loc_180013694
0x180013658  lea     rax, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001365f  mov     [rsp+0A0h+dwFlags], 7Ah ; 'z'; int
0x180013667  lea     r9, aAppreadinessSe_12; "AppReadiness::Service::OnServiceStart::"...
0x18001366e  mov     qword ptr [rsp+0A0h+dwMilliseconds], rax; char *
0x180013673  lea     r8, aComdisconnecta; "ComDisconnectableObjectManager::Initial"...
0x18001367a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001367e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013683  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001368a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001368e  call    _CxxThrowException_0
0x180013694  mov     rbx, [rsi]
0x180013697  add     rbx, 98h
0x18001369e  mov     rcx, rbx; SRWLock
0x1800136a1  call    cs:__imp_AcquireSRWLockExclusive
0x1800136a7  mov     r10, [rsi]
0x1800136aa  mov     r8, [rsi+8]
0x1800136ae  mov     rax, [r10+0F8h]
0x1800136b5  mov     r9, [r8]
0x1800136b8  mov     [r8], rax
0x1800136bb  mov     [r10+0F8h], r9
0x1800136c2  test    rbx, rbx
0x1800136c5  jz      short loc_1800136D0
0x1800136c7  mov     rcx, rbx; SRWLock
0x1800136ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1800136d0  mov     rax, [rsi]
0x1800136d3  xor     r8d, r8d; unsigned int
0x1800136d6  mov     [rsp+0A0h+dwFlags], 0; unsigned int
0x1800136de  mov     [rsp+0A0h+dwMilliseconds], 0; unsigned int
0x1800136e6  mov     dword ptr [rax+14h], 1101h
0x1800136ed  lea     edx, [r8+4]; unsigned int
0x1800136f1  mov     rcx, [rsi]; this
0x1800136f4  call    ?SetStatus@ServiceHandle@AppReadiness@@QEAA_NKKKKK@Z; AppReadiness::ServiceHandle::SetStatus(ulong,ulong,ulong,ulong,ulong)
0x1800136f9  call    ?GetMaxNonProgressIdlePulseCount@System@AppReadiness@@SAKXZ; AppReadiness::System::GetMaxNonProgressIdlePulseCount(void)
0x1800136fe  mov     rcx, [rsi]
0x180013701  mov     [rcx+118h], eax
0x180013707  mov     rcx, [rbp+57h+var_28]
0x18001370b  xor     rcx, rsp; StackCookie
0x18001370e  call    __security_check_cookie
0x180013713  add     rsp, 88h
0x18001371a  pop     rdi
0x18001371b  pop     rsi
0x18001371c  pop     rbx
0x18001371d  pop     rbp
0x18001371e  retn
```
