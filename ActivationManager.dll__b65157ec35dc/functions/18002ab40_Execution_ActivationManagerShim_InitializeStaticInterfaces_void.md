# Execution::ActivationManagerShim::InitializeStaticInterfaces(void)

- ea: `0x18002ab40`
- end: `0x18002b120`
- name: `?InitializeStaticInterfaces@ActivationManagerShim@Execution@@CAJXZ`
- size: `1504`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a9c4`
- `0x18002aa00`

## callees

- `0x18000b5c0`
- `0x18002ab40`
- `0x18005b33c`
- `0x18005b37c`
- `0x180061700`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ac43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ad0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002add1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b0e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b0f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ac43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ad0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002add1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b0e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b0f9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002b03c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002b05f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002b03c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002b05f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002abcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002abcd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002ab77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002ab77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aff4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aff4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b079`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002afaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002afaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 Execution::ActivationManagerShim::InitializeStaticInterfaces(void)
{
  const char *v0; // r9
  HRESULT v1; // eax
  unsigned int v2; // ebx
  __int64 (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rcx
  HKEY v4; // rcx
  LPVOID v5; // rcx
  LPVOID v6; // rbx
  __int64 (__fastcall *v7)(LPVOID, GUID *, GUID *, HKEY *); // rdi
  HKEY v8; // rcx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  HKEY v11; // rcx
  LPVOID v12; // rcx
  LPVOID v13; // rbx
  __int64 (__fastcall *v14)(LPVOID, SID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rcx
  HKEY v18; // rcx
  LPVOID v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v22; // rcx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  HKEY v25; // rcx
  LPVOID v26; // rcx
  struct IApplicationInstanceManager *v28; // rcx
  struct IApplicationInstanceManager *v29; // rbx
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  HKEY v31; // rcx
  LPVOID v32; // rcx
  UserContextHelpers *v33; // rsi
  char *v34; // rax
  bool *v35; // rdi
  LSTATUS v36; // eax
  unsigned int v37; // ebx
  bool v38; // zf
  UserContextHelpers *v39; // rcx
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  int ppvb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+40h] BYREF
  LPVOID v46; // [rsp+80h] [rbp+48h] BYREF
  struct _RTL_CRITICAL_SECTION *v47; // [rsp+88h] [rbp+50h]

  EnterCriticalSection(&Execution::ActivationManagerShim::_sStaticsLock);
  v47 = &Execution::ActivationManagerShim::_sStaticsLock;
  if ( !Execution::ActivationManagerShim::s_activationCounter
    && !QueryPerformanceFrequency(&Execution::ActivationManagerShim::s_qpcFrequency) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      v0);
  }
  if ( !Execution::ActivationManagerShim::s_applicationInstanceManager
    || !Execution::ActivationManagerShim::s_hamViewHacks )
  {
    v46 = 0;
    phkResult = 0;
    v44 = 0;
    v1 = CoCreateInstance(&CLSID_ShellServiceHost, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v46);
    v2 = v1;
    if ( v1 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v1,
        ppv);
      v3 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
      if ( v44 )
      {
        v44 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v3)[2])(v3);
      }
      v4 = phkResult;
      if ( phkResult )
      {
        phkResult = 0;
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v4 + 16LL))(v4);
      }
      v5 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
      }
LABEL_42:
      LeaveCriticalSection(&Execution::ActivationManagerShim::_sStaticsLock);
      return v2;
    }
    v6 = v46;
    v7 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, HKEY *))(*(_QWORD *)v46 + 24LL);
    v8 = phkResult;
    if ( phkResult )
    {
      phkResult = 0;
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v7(v6, &IID_IApplicationInstanceManager, &GUID_62a9407f_345a_4300_8cdd_4847dee60f48, &phkResult);
    v2 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v9,
        ppv);
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
      if ( v44 )
      {
        v44 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
      }
      v11 = phkResult;
      if ( phkResult )
      {
        phkResult = 0;
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
      }
      goto LABEL_42;
    }
    v13 = v46;
    v14 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v46 + 24LL);
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
    if ( v44 )
    {
      v44 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
    }
    v16 = v14(
            v13,
            &SID_ProcessLifetimeManagerControl,
            &GUID_69c083b1_7f6f_490d_9d77_c0219a95b25d,
            (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v44);
    v2 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v16,
        ppv);
      v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
      if ( v44 )
      {
        v44 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v17)[2])(v17);
      }
      v18 = phkResult;
      if ( phkResult )
      {
        phkResult = 0;
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
      }
      goto LABEL_42;
    }
    v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
    v21 = **v44;
    v22 = Execution::ActivationManagerShim::s_hamViewHacks;
    if ( Execution::ActivationManagerShim::s_hamViewHacks )
    {
      Execution::ActivationManagerShim::s_hamViewHacks = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v21(v20, &GUID_8bd9f82e_f77e_4a64_9965_8ec5b9c45b81, &Execution::ActivationManagerShim::s_hamViewHacks);
    v2 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v23,
        ppv);
      v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
      if ( v44 )
      {
        v44 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
      }
      v25 = phkResult;
      if ( phkResult )
      {
        phkResult = 0;
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
      }
      goto LABEL_42;
    }
    v28 = Execution::ActivationManagerShim::s_applicationInstanceManager;
    v29 = (struct IApplicationInstanceManager *)phkResult;
    if ( Execution::ActivationManagerShim::s_applicationInstanceManager != (struct IApplicationInstanceManager *)phkResult )
    {
      if ( phkResult )
      {
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 8LL))(phkResult);
        v28 = Execution::ActivationManagerShim::s_applicationInstanceManager;
      }
      Execution::ActivationManagerShim::s_applicationInstanceManager = v29;
      if ( v28 )
        (*(void (__fastcall **)(struct IApplicationInstanceManager *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
    if ( v44 )
    {
      v44 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
    }
    v31 = phkResult;
    if ( phkResult )
    {
      phkResult = 0;
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
    }
  }
  if ( Execution::ActivationManagerShim::s_userContextHelper )
    goto LABEL_72;
  v33 = 0;
  v34 = (char *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = (bool *)v34;
  if ( !v34 )
  {
    v37 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
      (const char *)0x8007000ELL,
      ppv);
    goto LABEL_68;
  }
  *(_OWORD *)(v34 + 4) = 0;
  *(_OWORD *)(v34 + 20) = 0;
  *(_OWORD *)(v34 + 36) = 0;
  *(_OWORD *)(v34 + 52) = 0;
  *((_DWORD *)v34 + 17) = 0;
  phkResult = 0;
  v36 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Policies\\AppRestrictions\\Resource\\AllowApps",
          0,
          0x20019u,
          &phkResult);
  v37 = v36;
  if ( v36 > 0 )
    v37 = (unsigned __int16)v36 | 0x80070000;
  if ( (int)(v37 + 0x80000000) < 0 )
  {
    v38 = v37 == -2147024894;
  }
  else
  {
    v38 = v37 == -2147024894;
    if ( v37 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)v37,
        ppva);
      if ( phkResult )
        RegCloseKey(phkResult);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)v37,
        ppvb);
      operator delete(v35, (const struct std::nothrow_t *)0x48);
      goto LABEL_68;
    }
  }
  *v35 = !v38;
  LODWORD(v44) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v44, 0);
  UserContextHelpers::s_IsRunningOnIOT = (unsigned int)((_DWORD)v44 - 7) <= 1;
  LODWORD(v44) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v44, 0);
  UserContextHelpers::s_IsRunningOnPolaris = (_DWORD)v44 == 15;
  if ( phkResult )
    RegCloseKey(phkResult);
  v33 = (UserContextHelpers *)v35;
  v37 = 0;
LABEL_68:
  v39 = Execution::ActivationManagerShim::s_userContextHelper;
  Execution::ActivationManagerShim::s_userContextHelper = v33;
  if ( v39 )
    operator delete(v39, (const struct std::nothrow_t *)0x48);
  if ( (v37 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)v37,
      ppva);
    LeaveCriticalSection(&Execution::ActivationManagerShim::_sStaticsLock);
    return v37;
  }
LABEL_72:
  LeaveCriticalSection(&Execution::ActivationManagerShim::_sStaticsLock);
  return 0;
}

```

## disassembly

```asm
0x18002ab40  push    rbp
0x18002ab42  push    rbx
0x18002ab43  push    rsi
0x18002ab44  push    rdi
0x18002ab45  push    r14
0x18002ab47  push    r15
0x18002ab49  mov     rbp, rsp
0x18002ab4c  sub     rsp, 38h
0x18002ab50  lea     r15, ?_sStaticsLock@ActivationManagerShim@Execution@@0Vcritical_section@wil@@A; wil::critical_section Execution::ActivationManagerShim::_sStaticsLock
0x18002ab57  mov     rcx, r15; lpCriticalSection
0x18002ab5a  call    cs:__imp_EnterCriticalSection
0x18002ab60  mov     [rbp+arg_18], r15
0x18002ab64  mov     rax, cs:?s_activationCounter@ActivationManagerShim@Execution@@0_JC; __int64 volatile Execution::ActivationManagerShim::s_activationCounter
0x18002ab6b  test    rax, rax
0x18002ab6e  jnz     short loc_18002AB89
0x18002ab70  lea     rcx, ?s_qpcFrequency@ActivationManagerShim@Execution@@0T_LARGE_INTEGER@@A; lpFrequency
0x18002ab77  call    cs:__imp_QueryPerformanceFrequency
0x18002ab7d  mov     rcx, [rbp+30h]; this
0x18002ab81  test    eax, eax
0x18002ab83  jz      loc_18002B10E
0x18002ab89  xor     r14d, r14d
0x18002ab8c  cmp     cs:?s_applicationInstanceManager@ActivationManagerShim@Execution@@0V?$ComPtr@UIApplicationInstanceManager@@@WRL@Microsoft@@A, r14; Microsoft::WRL::ComPtr<IApplicationInstanceManager> Execution::ActivationManagerShim::s_applicationInstanceManager
0x18002ab93  jz      short loc_18002ABA2
0x18002ab95  cmp     cs:?s_hamViewHacks@ActivationManagerShim@Execution@@0V?$ComPtr@UIHamHacksForViewActivation@Execution@@@WRL@Microsoft@@A, r14; Microsoft::WRL::ComPtr<Execution::IHamHacksForViewActivation> Execution::ActivationManagerShim::s_hamViewHacks
0x18002ab9c  jnz     loc_18002AF40
0x18002aba2  mov     [rbp+arg_10], r14
0x18002aba6  mov     [rbp+phkResult], r14
0x18002abaa  mov     [rbp+arg_0], r14
0x18002abae  lea     rax, [rbp+arg_10]
0x18002abb2  mov     qword ptr [rsp+38h+ppv], rax; int
0x18002abb7  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18002abbe  xor     edx, edx; pUnkOuter
0x18002abc0  mov     r8d, 4; dwClsContext
0x18002abc6  lea     rcx, CLSID_ShellServiceHost; rclsid
0x18002abcd  call    cs:__imp_CoCreateInstance
0x18002abd3  mov     ebx, eax
0x18002abd5  test    eax, eax
0x18002abd7  jns     short loc_18002AC58
0x18002abd9  mov     rcx, [rbp+30h]; this
0x18002abdd  mov     r9d, eax; char *
0x18002abe0  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002abe7  mov     edx, 8Fh; void *
0x18002abec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002abf1  nop
0x18002abf2  mov     rcx, [rbp+arg_0]
0x18002abf6  test    rcx, rcx
0x18002abf9  jz      short loc_18002AC0C
0x18002abfb  mov     [rbp+arg_0], r14
0x18002abff  mov     rax, [rcx]
0x18002ac02  mov     rax, [rax+10h]
0x18002ac06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac0b  nop
0x18002ac0c  mov     rcx, [rbp+phkResult]
0x18002ac10  test    rcx, rcx
0x18002ac13  jz      short loc_18002AC26
0x18002ac15  mov     [rbp+phkResult], r14
0x18002ac19  mov     rax, [rcx]
0x18002ac1c  mov     rax, [rax+10h]
0x18002ac20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac25  nop
0x18002ac26  mov     rcx, [rbp+arg_10]
0x18002ac2a  test    rcx, rcx
0x18002ac2d  jz      short loc_18002AC40
0x18002ac2f  mov     [rbp+arg_10], r14
0x18002ac33  mov     rax, [rcx]
0x18002ac36  mov     rax, [rax+10h]
0x18002ac3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac3f  nop
0x18002ac40  mov     rcx, r15; lpCriticalSection
0x18002ac43  call    cs:__imp_LeaveCriticalSection
0x18002ac49  mov     eax, ebx
0x18002ac4b  add     rsp, 38h
0x18002ac4f  pop     r15
0x18002ac51  pop     r14
0x18002ac53  pop     rdi
0x18002ac54  pop     rsi
0x18002ac55  pop     rbx
0x18002ac56  pop     rbp
0x18002ac57  retn
0x18002ac58  mov     rbx, [rbp+arg_10]
0x18002ac5c  mov     rax, [rbx]
0x18002ac5f  mov     rdi, [rax+18h]
0x18002ac63  mov     rcx, [rbp+phkResult]
0x18002ac67  test    rcx, rcx
0x18002ac6a  jz      short loc_18002AC7D
0x18002ac6c  mov     [rbp+phkResult], r14
0x18002ac70  mov     rdx, [rcx]
0x18002ac73  mov     rax, [rdx+10h]
0x18002ac77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac7c  nop
0x18002ac7d  lea     r9, [rbp+phkResult]
0x18002ac81  lea     r8, _GUID_62a9407f_345a_4300_8cdd_4847dee60f48
0x18002ac88  lea     rdx, IID_IApplicationInstanceManager
0x18002ac8f  mov     rcx, rbx
0x18002ac92  mov     rax, rdi
0x18002ac95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac9a  mov     ebx, eax
0x18002ac9c  test    eax, eax
0x18002ac9e  jns     short loc_18002AD1F
0x18002aca0  mov     rcx, [rbp+30h]; this
0x18002aca4  mov     r9d, eax; char *
0x18002aca7  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002acae  mov     edx, 90h; void *
0x18002acb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acb8  nop
0x18002acb9  mov     rcx, [rbp+arg_0]
0x18002acbd  test    rcx, rcx
0x18002acc0  jz      short loc_18002ACD3
0x18002acc2  mov     [rbp+arg_0], r14
0x18002acc6  mov     rax, [rcx]
0x18002acc9  mov     rax, [rax+10h]
0x18002accd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acd2  nop
0x18002acd3  mov     rcx, [rbp+phkResult]
0x18002acd7  test    rcx, rcx
0x18002acda  jz      short loc_18002ACED
0x18002acdc  mov     [rbp+phkResult], r14
0x18002ace0  mov     rax, [rcx]
0x18002ace3  mov     rax, [rax+10h]
0x18002ace7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acec  nop
0x18002aced  mov     rcx, [rbp+arg_10]
0x18002acf1  test    rcx, rcx
0x18002acf4  jz      short loc_18002AD07
0x18002acf6  mov     [rbp+arg_10], r14
0x18002acfa  mov     rax, [rcx]
0x18002acfd  mov     rax, [rax+10h]
0x18002ad01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad06  nop
0x18002ad07  mov     rcx, r15; lpCriticalSection
0x18002ad0a  call    cs:__imp_LeaveCriticalSection
0x18002ad10  mov     eax, ebx
0x18002ad12  add     rsp, 38h
0x18002ad16  pop     r15
0x18002ad18  pop     r14
0x18002ad1a  pop     rdi
0x18002ad1b  pop     rsi
0x18002ad1c  pop     rbx
0x18002ad1d  pop     rbp
0x18002ad1e  retn
0x18002ad1f  mov     rbx, [rbp+arg_10]
0x18002ad23  mov     rax, [rbx]
0x18002ad26  mov     rdi, [rax+18h]
0x18002ad2a  mov     rcx, [rbp+arg_0]
0x18002ad2e  test    rcx, rcx
0x18002ad31  jz      short loc_18002AD44
0x18002ad33  mov     [rbp+arg_0], r14
0x18002ad37  mov     rdx, [rcx]
0x18002ad3a  mov     rax, [rdx+10h]
0x18002ad3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad43  nop
0x18002ad44  lea     r9, [rbp+arg_0]
0x18002ad48  lea     r8, _GUID_69c083b1_7f6f_490d_9d77_c0219a95b25d
0x18002ad4f  lea     rdx, SID_ProcessLifetimeManagerControl
0x18002ad56  mov     rcx, rbx
0x18002ad59  mov     rax, rdi
0x18002ad5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad61  mov     ebx, eax
0x18002ad63  test    eax, eax
0x18002ad65  jns     short loc_18002ADE6
0x18002ad67  mov     rcx, [rbp+30h]; this
0x18002ad6b  mov     r9d, eax; char *
0x18002ad6e  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002ad75  mov     edx, 91h; void *
0x18002ad7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ad7f  nop
0x18002ad80  mov     rcx, [rbp+arg_0]
0x18002ad84  test    rcx, rcx
0x18002ad87  jz      short loc_18002AD9A
0x18002ad89  mov     [rbp+arg_0], r14
0x18002ad8d  mov     rax, [rcx]
0x18002ad90  mov     rax, [rax+10h]
0x18002ad94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad99  nop
0x18002ad9a  mov     rcx, [rbp+phkResult]
0x18002ad9e  test    rcx, rcx
0x18002ada1  jz      short loc_18002ADB4
0x18002ada3  mov     [rbp+phkResult], r14
0x18002ada7  mov     rax, [rcx]
0x18002adaa  mov     rax, [rax+10h]
0x18002adae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb3  nop
0x18002adb4  mov     rcx, [rbp+arg_10]
0x18002adb8  test    rcx, rcx
0x18002adbb  jz      short loc_18002ADCE
0x18002adbd  mov     [rbp+arg_10], r14
0x18002adc1  mov     rax, [rcx]
0x18002adc4  mov     rax, [rax+10h]
0x18002adc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adcd  nop
0x18002adce  mov     rcx, r15; lpCriticalSection
0x18002add1  call    cs:__imp_LeaveCriticalSection
0x18002add7  mov     eax, ebx
0x18002add9  add     rsp, 38h
0x18002addd  pop     r15
0x18002addf  pop     r14
0x18002ade1  pop     rdi
0x18002ade2  pop     rsi
0x18002ade3  pop     rbx
0x18002ade4  pop     rbp
0x18002ade5  retn
0x18002ade6  mov     rbx, [rbp+arg_0]
0x18002adea  mov     rax, [rbx]
0x18002aded  mov     rdi, [rax]
0x18002adf0  mov     rcx, cs:?s_hamViewHacks@ActivationManagerShim@Execution@@0V?$ComPtr@UIHamHacksForViewActivation@Execution@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Execution::IHamHacksForViewActivation> Execution::ActivationManagerShim::s_hamViewHacks
0x18002adf7  test    rcx, rcx
0x18002adfa  jz      short loc_18002AE10
0x18002adfc  mov     cs:?s_hamViewHacks@ActivationManagerShim@Execution@@0V?$ComPtr@UIHamHacksForViewActivation@Execution@@@WRL@Microsoft@@A, r14; Microsoft::WRL::ComPtr<Execution::IHamHacksForViewActivation> Execution::ActivationManagerShim::s_hamViewHacks
0x18002ae03  mov     rdx, [rcx]
0x18002ae06  mov     rax, [rdx+10h]
0x18002ae0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae0f  nop
0x18002ae10  lea     r8, ?s_hamViewHacks@ActivationManagerShim@Execution@@0V?$ComPtr@UIHamHacksForViewActivation@Execution@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Execution::IHamHacksForViewActivation> Execution::ActivationManagerShim::s_hamViewHacks
0x18002ae17  lea     rdx, _GUID_8bd9f82e_f77e_4a64_9965_8ec5b9c45b81
0x18002ae1e  mov     rcx, rbx
0x18002ae21  mov     rax, rdi
0x18002ae24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae29  mov     ebx, eax
0x18002ae2b  test    eax, eax
0x18002ae2d  jns     short loc_18002AEAE
0x18002ae2f  mov     rcx, [rbp+30h]; this
0x18002ae33  mov     r9d, eax; char *
0x18002ae36  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002ae3d  mov     edx, 92h; void *
0x18002ae42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ae47  nop
0x18002ae48  mov     rcx, [rbp+arg_0]
0x18002ae4c  test    rcx, rcx
0x18002ae4f  jz      short loc_18002AE62
0x18002ae51  mov     [rbp+arg_0], r14
0x18002ae55  mov     rax, [rcx]
0x18002ae58  mov     rax, [rax+10h]
0x18002ae5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae61  nop
0x18002ae62  mov     rcx, [rbp+phkResult]
0x18002ae66  test    rcx, rcx
0x18002ae69  jz      short loc_18002AE7C
0x18002ae6b  mov     [rbp+phkResult], r14
0x18002ae6f  mov     rax, [rcx]
0x18002ae72  mov     rax, [rax+10h]
0x18002ae76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae7b  nop
0x18002ae7c  mov     rcx, [rbp+arg_10]
0x18002ae80  test    rcx, rcx
0x18002ae83  jz      short loc_18002AE96
0x18002ae85  mov     [rbp+arg_10], r14
0x18002ae89  mov     rax, [rcx]
0x18002ae8c  mov     rax, [rax+10h]
0x18002ae90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae95  nop
0x18002ae96  mov     rcx, r15; lpCriticalSection
0x18002ae99  call    cs:__imp_LeaveCriticalSection
0x18002ae9f  mov     eax, ebx
0x18002aea1  add     rsp, 38h
0x18002aea5  pop     r15
0x18002aea7  pop     r14
0x18002aea9  pop     rdi
0x18002aeaa  pop     rsi
0x18002aeab  pop     rbx
0x18002aeac  pop     rbp
0x18002aead  retn
0x18002aeae  mov     rcx, cs:?s_applicationInstanceManager@ActivationManagerShim@Execution@@0V?$ComPtr@UIApplicationInstanceManager@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IApplicationInstanceManager> Execution::ActivationManagerShim::s_applicationInstanceManager
0x18002aeb5  mov     rbx, [rbp+phkResult]
0x18002aeb9  cmp     rcx, rbx
0x18002aebc  jz      short loc_18002AEF2
0x18002aebe  test    rbx, rbx
0x18002aec1  jz      short loc_18002AED9
0x18002aec3  mov     rax, [rbx]
0x18002aec6  mov     rcx, rbx
0x18002aec9  mov     rax, [rax+8]
0x18002aecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed2  mov     rcx, cs:?s_applicationInstanceManager@ActivationManagerShim@Execution@@0V?$ComPtr@UIApplicationInstanceManager@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IApplicationInstanceManager> Execution::ActivationManagerShim::s_applicationInstanceManager
0x18002aed9  mov     cs:?s_applicationInstanceManager@ActivationManagerShim@Execution@@0V?$ComPtr@UIApplicationInstanceManager@@@WRL@Microsoft@@A, rbx; Microsoft::WRL::ComPtr<IApplicationInstanceManager> Execution::ActivationManagerShim::s_applicationInstanceManager
0x18002aee0  test    rcx, rcx
0x18002aee3  jz      short loc_18002AEF2
0x18002aee5  mov     rax, [rcx]
0x18002aee8  mov     rax, [rax+10h]
0x18002aeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aef1  nop
0x18002aef2  mov     rcx, [rbp+arg_0]
0x18002aef6  test    rcx, rcx
0x18002aef9  jz      short loc_18002AF0C
0x18002aefb  mov     [rbp+arg_0], r14
0x18002aeff  mov     rax, [rcx]
0x18002af02  mov     rax, [rax+10h]
0x18002af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af0b  nop
0x18002af0c  mov     rcx, [rbp+phkResult]
0x18002af10  test    rcx, rcx
0x18002af13  jz      short loc_18002AF26
0x18002af15  mov     [rbp+phkResult], r14
0x18002af19  mov     rax, [rcx]
0x18002af1c  mov     rax, [rax+10h]
0x18002af20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af25  nop
0x18002af26  mov     rcx, [rbp+arg_10]
0x18002af2a  test    rcx, rcx
0x18002af2d  jz      short loc_18002AF40
0x18002af2f  mov     [rbp+arg_10], r14
0x18002af33  mov     rax, [rcx]
  ... truncated ...
```
