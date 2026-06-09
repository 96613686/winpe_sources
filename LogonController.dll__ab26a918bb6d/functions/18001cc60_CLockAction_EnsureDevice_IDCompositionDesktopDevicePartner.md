# CLockAction::_EnsureDevice(IDCompositionDesktopDevicePartner * *)

- ea: `0x18001cc60`
- end: `0x18001d33c`
- name: `?_EnsureDevice@CLockAction@@AEAAJPEAPEAUIDCompositionDesktopDevicePartner@@@Z`
- size: `1756`
- prototype: `__int64 __fastcall(CLockAction *__hidden this, struct IDCompositionDesktopDevicePartner **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001def0`

## callees

- `0x180017dec`
- `0x18001cc60`
- `0x18001d344`
- `0x18001d850`
- `0x18001da28`
- `0x18001db70`
- `0x18001ed6c`
- `0x18005b3e4`
- `0x18005d488`
- `0x18006c000`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001d0bf`
- `KERNEL32!LoadLibraryExW` at `0x18001d0bf`
- `KERNEL32!FreeLibrary` at `0x18001d2fe`
- `KERNEL32!FreeLibrary` at `0x18001d2fe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cfcc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d096`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d0f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d199`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d209`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d243`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d298`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cfcc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d096`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d0f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d199`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d209`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d243`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001d298`
- `KERNEL32!GetProcAddress` at `0x18001cea2`
- `KERNEL32!GetProcAddress` at `0x18001cea2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ce35`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ce35`
- `KERNEL32!SetLastError` at `0x18001d2e7`
- `KERNEL32!SetLastError` at `0x18001d306`
- `KERNEL32!SetLastError` at `0x18001d2e7`
- `KERNEL32!SetLastError` at `0x18001d306`
- `KERNEL32!GetLastError` at `0x18001d2d4`
- `KERNEL32!GetLastError` at `0x18001d2f3`
- `KERNEL32!GetLastError` at `0x18001d2d4`
- `KERNEL32!GetLastError` at `0x18001d2f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cdcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cdcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d2df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d2df`

## string_xrefs

- `0x18001d0b8`: `dcomp.dll`
- `0x18001ce98`: `DCompositionCreateDevice2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLockAction::_EnsureDevice(RTL_SRWLOCK *this, struct IDCompositionDesktopDevicePartner **a2)
{
  __int128 v4; // xmm6
  LSTATUS Value; // eax
  bool v6; // sf
  RTL_SRWLOCK *v7; // rsi
  RTL_SRWLOCK *v8; // r14
  CLockAction *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  HMODULE v12; // rbx
  __int64 v13; // rdi
  FARPROC ProcAddress; // rbx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  HKEY v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, RTL_SRWLOCK *); // rdi
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v27; // rcx
  HMODULE Library; // r14
  HMODULE Ptr; // r12
  HKEY v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  DWORD LastError; // edi
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD Type[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-B0h] BYREF
  void **v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+68h] [rbp-98h] BYREF
  char v45; // [rsp+6Ch] [rbp-94h]
  int v46; // [rsp+90h] [rbp-70h] BYREF
  const char *v47; // [rsp+98h] [rbp-68h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  char v49; // [rsp+A8h] [rbp-58h]
  int v50; // [rsp+B0h] [rbp-50h]
  __int128 v51; // [rsp+B8h] [rbp-48h]
  __int128 v52; // [rsp+C8h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-18h]
  __int128 v55; // [rsp+F8h] [rbp-8h]
  __int128 v56; // [rsp+108h] [rbp+8h]
  __int128 v57; // [rsp+118h] [rbp+18h]
  __int128 v58; // [rsp+128h] [rbp+28h]
  __int128 v59; // [rsp+138h] [rbp+38h]
  __int64 v60; // [rsp+148h] [rbp+48h]
  __int128 v61; // [rsp+150h] [rbp+50h]
  int v62; // [rsp+160h] [rbp+60h]
  __int64 v63; // [rsp+168h] [rbp+68h]
  int *v64; // [rsp+170h] [rbp+70h]
  __int64 v65; // [rsp+178h] [rbp+78h]
  char v66[48]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v43 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v44 = 0;
  v45 = 0;
  v49 = 0;
  v46 = 0;
  v47 = "CLockAction__EnsureDevice_Activity";
  v48 = 0;
  v50 = 0;
  v61 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v62 = 1;
  v63 = 0;
  v64 = &v44;
  v65 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v66,
    (struct wil::details::IFailureCallback *)&v43,
    (struct wil::CallContextInfo *)&v46,
    0);
  v43 = &LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::`vftable';
  v4 = 0;
  *(_OWORD *)Data = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TelemetryCorrelation",
         0,
         0x20019u,
         &hKey) < 0 )
    goto LABEL_28;
  Type[0] = 3;
  cbData[0] = 16;
  Value = RegQueryValueExW(hKey, L"FirstRunCorrelationID", 0, Type, Data, cbData);
  v6 = Value < 0;
  if ( Value > 0 )
    v6 = 1;
  if ( v6 )
    *(_OWORD *)Data = 0;
  else
LABEL_28:
    v4 = *(_OWORD *)Data;
  if ( hKey )
    RegCloseKey(hKey);
  *(_OWORD *)Data = v4;
  if ( memcmp_0(Data, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v43,
      Data);
  LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::StartActivity((LogonControllerTelemetry::CLockAction__EnsureDevice_Activity *)&v43);
  *a2 = 0;
  v7 = this + 48;
  AcquireSRWLockExclusive(this + 48);
  if ( this[57].Ptr )
    goto LABEL_11;
  Library = LoadLibraryExW(L"dcomp.dll", 0, 0x800u);
  Ptr = (HMODULE)this[57].Ptr;
  if ( Ptr )
  {
    LastError = GetLastError();
    FreeLibrary(Ptr);
    SetLastError(LastError);
  }
  this[57].Ptr = Library;
  if ( Library )
  {
LABEL_11:
    v8 = this + 49;
    if ( this[49].Ptr )
      goto LABEL_24;
    *(_QWORD *)Type = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
    v10 = CLockAction::_InitializeDCompDeviceSupport(v9, (struct IDXGIDevice1 **)Type);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x560,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v10,
        phkResult);
      v35 = *(_QWORD *)Type;
      if ( *(_QWORD *)Type )
      {
        *(_QWORD *)Type = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      if ( this != (RTL_SRWLOCK *)-384LL )
        ReleaseSRWLockExclusive(this + 48);
      LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity((LogonControllerTelemetry::CLockAction__EnsureDevice_Activity *)&v43);
      return v11;
    }
    *(_QWORD *)cbData = 0;
    v12 = (HMODULE)this[57].Ptr;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
    v13 = *(_QWORD *)Type;
    ProcAddress = GetProcAddress(v12, "DCompositionCreateDevice2");
    if ( ProcAddress )
    {
      hKey = 0;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
      v15 = ((__int64 (__fastcall *)(__int64, GUID *, HKEY *))ProcAddress)(
              v13,
              &GUID_5f4633fe_1e08_4cb8_8c75_ce24333f5602,
              &hKey);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x545,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)v15,
          phkResult);
        v30 = hKey;
        if ( hKey )
        {
          hKey = 0;
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)v30 + 16LL))(v30);
        }
      }
      else
      {
        v17 = (**(__int64 (__fastcall ***)(HKEY, GUID *, DWORD *))hKey)(
                hKey,
                &GUID_c37ea93a_e7aa_450d_b16f_9746cb0407f3,
                cbData);
        v16 = v17;
        if ( v17 >= 0 )
        {
          v18 = hKey;
          if ( hKey )
          {
            hKey = 0;
            (*(void (__fastcall **)(HKEY))(*(_QWORD *)v18 + 16LL))(v18);
          }
          v19 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))cbData;
          if ( !*(_QWORD *)cbData )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x565,
              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
              (const char *)0x8007000ELL,
              phkResult);
            v26 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))cbData;
            if ( *(_QWORD *)cbData )
            {
              *(_QWORD *)cbData = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
            }
            v27 = *(_QWORD *)Type;
            if ( *(_QWORD *)Type )
            {
              *(_QWORD *)Type = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
            if ( v7 )
              ReleaseSRWLockExclusive(v7);
            LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity((LogonControllerTelemetry::CLockAction__EnsureDevice_Activity *)&v43);
            return 2147942414LL;
          }
          v20 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, RTL_SRWLOCK *))cbData;
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v8);
          v21 = v20(v19, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, v8);
          v16 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x567,
              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
              (const char *)(unsigned int)v21,
              phkResult);
            v33 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))cbData;
            if ( *(_QWORD *)cbData )
            {
              *(_QWORD *)cbData = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
            }
            v34 = *(_QWORD *)Type;
            if ( *(_QWORD *)Type )
            {
              *(_QWORD *)Type = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            }
            if ( v7 )
              ReleaseSRWLockExclusive(v7);
            goto LABEL_60;
          }
          v22 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))cbData;
          if ( *(_QWORD *)cbData )
          {
            *(_QWORD *)cbData = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v22)[2])(v22);
          }
          v23 = *(_QWORD *)Type;
          if ( *(_QWORD *)Type )
          {
            *(_QWORD *)Type = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
LABEL_24:
          v24 = (**(__int64 (__fastcall ***)(PVOID, GUID *, struct IDCompositionDesktopDevicePartner **))v8->Ptr)(
                  v8->Ptr,
                  &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0,
                  a2);
          v16 = v24;
          if ( v24 >= 0 )
          {
            wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v43, 0);
            if ( v7 )
              ReleaseSRWLockExclusive(v7);
            LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity((LogonControllerTelemetry::CLockAction__EnsureDevice_Activity *)&v43);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56A,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
            (const char *)(unsigned int)v24,
            phkResult);
          if ( v7 )
            ReleaseSRWLockExclusive(v7);
LABEL_60:
          LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity((LogonControllerTelemetry::CLockAction__EnsureDevice_Activity *)&v43);
          return v16;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x546,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)v17,
          phkResult);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
      }
    }
    else
    {
      v16 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x542,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)0x80004005LL,
        phkResult);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x564,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
      (const char *)v16,
      phkResulta);
    v31 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))cbData;
    if ( *(_QWORD *)cbData )
    {
      *(_QWORD *)cbData = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v31)[2])(v31);
    }
    v32 = *(_QWORD *)Type;
    if ( *(_QWORD *)Type )
    {
      *(_QWORD *)Type = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    goto LABEL_60;
  }
  if ( this != (RTL_SRWLOCK *)-384LL )
    ReleaseSRWLockExclusive(this + 48);
  LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity((LogonControllerTelemetry::CLockAction__EnsureDevice_Activity *)&v43);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18001cc60  mov     [rsp-8+arg_10], rbx
0x18001cc65  push    rbp
0x18001cc66  push    rsi
0x18001cc67  push    rdi
0x18001cc68  push    r12
0x18001cc6a  push    r13
0x18001cc6c  push    r14
0x18001cc6e  push    r15
0x18001cc70  lea     rbp, [rsp-0D0h]
0x18001cc78  sub     rsp, 1D0h
0x18001cc7f  movaps  [rsp+200h+var_40], xmm6
0x18001cc87  mov     rax, cs:__security_cookie
0x18001cc8e  xor     rax, rsp
0x18001cc91  mov     [rbp+100h+var_50], rax
0x18001cc98  mov     r15, rdx
0x18001cc9b  mov     rbx, rcx
0x18001cc9e  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18001cca5  mov     [rsp+200h+var_1A0], rax
0x18001ccaa  xor     r13d, r13d
0x18001ccad  mov     [rsp+200h+var_198], r13d
0x18001ccb2  mov     [rsp+200h+var_194], r13b
0x18001ccb7  mov     [rbp+100h+var_158], r13b
0x18001ccbb  mov     [rbp+100h+var_170], r13d
0x18001ccbf  lea     rax, aClockactionEns_0; "CLockAction__EnsureDevice_Activity"
0x18001ccc6  mov     [rbp+100h+var_168], rax
0x18001ccca  mov     [rbp+100h+var_160], r13
0x18001ccce  mov     [rbp+100h+var_150], r13d
0x18001ccd2  xorps   xmm0, xmm0
0x18001ccd5  movdqa  [rbp+100h+var_B0], xmm0
0x18001ccda  xorps   xmm1, xmm1
0x18001ccdd  xor     eax, eax
0x18001ccdf  movups  [rbp+100h+var_148], xmm1
0x18001cce3  movups  [rbp+100h+var_138], xmm1
0x18001cce7  movups  [rbp+100h+var_128], xmm1
0x18001cceb  movups  [rbp+100h+var_118], xmm1
0x18001ccef  movups  [rbp+100h+var_108], xmm1
0x18001ccf3  movups  [rbp+100h+var_F8], xmm1
0x18001ccf7  movups  [rbp+100h+var_E8], xmm1
0x18001ccfb  movups  [rbp+100h+var_D8], xmm1
0x18001ccff  movups  [rbp+100h+var_C8], xmm1
0x18001cd03  mov     [rbp+100h+var_B8], rax
0x18001cd07  mov     [rbp+100h+var_A0], 1
0x18001cd0e  mov     [rbp+100h+var_98], rax
0x18001cd12  lea     rax, [rsp+200h+var_198]
0x18001cd17  mov     [rbp+100h+var_90], rax
0x18001cd1b  mov     [rbp+100h+var_88], r13
0x18001cd1f  xor     r9d, r9d; bool
0x18001cd22  lea     r8, [rbp+100h+var_170]; struct wil::CallContextInfo *
0x18001cd26  lea     rdx, [rsp+200h+var_1A0]; struct wil::details::IFailureCallback *
0x18001cd2b  lea     rcx, [rbp+100h+var_80]; this
0x18001cd32  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18001cd37  nop
0x18001cd38  lea     rax, ??_7CLockAction__EnsureDevice_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::`vftable'
0x18001cd3f  mov     [rsp+200h+var_1A0], rax
0x18001cd44  xorps   xmm6, xmm6
0x18001cd47  movdqa  xmmword ptr [rsp+200h+Data], xmm6
0x18001cd4d  mov     [rsp+200h+hKey], r13
0x18001cd52  mov     rsi, [rsp+200h+hKey]
0x18001cd57  test    rsi, rsi
0x18001cd5a  jnz     loc_18001D2D4
0x18001cd60  mov     [rsp+200h+hKey], r13
0x18001cd65  lea     rax, [rsp+200h+hKey]
0x18001cd6a  mov     [rsp+200h+phkResult], rax; phkResult
0x18001cd6f  mov     r9d, 20019h; samDesired
0x18001cd75  xor     r8d, r8d; ulOptions
0x18001cd78  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001cd7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cd86  call    cs:__imp_RegOpenKeyExW
0x18001cd8c  test    eax, eax
0x18001cd8e  js      loc_18001D030
0x18001cd94  mov     [rsp+200h+Type], 3
0x18001cd9c  mov     [rsp+200h+cbData], 10h
0x18001cda4  lea     rax, [rsp+200h+cbData]
0x18001cda9  mov     [rsp+200h+lpcbData], rax; lpcbData
0x18001cdae  lea     rax, [rsp+200h+Data]
0x18001cdb3  mov     [rsp+200h+phkResult], rax; int
0x18001cdb8  lea     r9, [rsp+200h+Type]; lpType
0x18001cdbd  xor     r8d, r8d; lpReserved
0x18001cdc0  lea     rdx, aFirstruncorrel; "FirstRunCorrelationID"
0x18001cdc7  mov     rcx, [rsp+200h+hKey]; hKey
0x18001cdcc  call    cs:__imp_RegQueryValueExW
0x18001cdd2  test    eax, eax
0x18001cdd4  jle     short loc_18001CDE0
0x18001cdd6  movzx   eax, ax
0x18001cdd9  or      eax, 80070000h
0x18001cdde  test    eax, eax
0x18001cde0  jns     loc_18001D030
0x18001cde6  movaps  xmmword ptr [rsp+200h+Data], xmm6
0x18001cdeb  mov     rcx, [rsp+200h+hKey]; hKey
0x18001cdf0  test    rcx, rcx
0x18001cdf3  jnz     loc_18001D024
0x18001cdf9  movdqa  xmmword ptr [rsp+200h+Data], xmm6
0x18001cdff  mov     r8d, 10h; Size
0x18001ce05  lea     rdx, GUID_NULL; Buf2
0x18001ce0c  lea     rcx, [rsp+200h+Data]; Buf1
0x18001ce11  call    memcmp_0
0x18001ce16  test    eax, eax
0x18001ce18  jnz     loc_18001D010
0x18001ce1e  lea     rcx, [rsp+200h+var_1A0]; this
0x18001ce23  call    ?StartActivity@CLockAction__EnsureDevice_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::StartActivity(void)
0x18001ce28  mov     [r15], r13
0x18001ce2b  lea     rsi, [rbx+180h]
0x18001ce32  mov     rcx, rsi; SRWLock
0x18001ce35  call    cs:__imp_AcquireSRWLockExclusive
0x18001ce3b  cmp     qword ptr [rbx+1C8h], 0
0x18001ce43  jz      loc_18001D0B0
0x18001ce49  lea     r14, [rbx+188h]
0x18001ce50  cmp     qword ptr [r14], 0
0x18001ce54  jnz     loc_18001CF96
0x18001ce5a  mov     qword ptr [rsp+200h+Type], r13
0x18001ce5f  lea     rcx, [rsp+200h+Type]
0x18001ce64  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001ce69  lea     rdx, [rsp+200h+Type]; struct IDXGIDevice1 **
0x18001ce6e  call    ?_InitializeDCompDeviceSupport@CLockAction@@AEAAJPEAPEAUIDXGIDevice1@@@Z; CLockAction::_InitializeDCompDeviceSupport(IDXGIDevice1 * *)
0x18001ce73  mov     edi, eax
0x18001ce75  test    eax, eax
0x18001ce77  js      loc_18001D25A
0x18001ce7d  mov     qword ptr [rsp+200h+cbData], r13
0x18001ce82  mov     rbx, [rbx+1C8h]
0x18001ce89  lea     rcx, [rsp+200h+cbData]
0x18001ce8e  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001ce93  mov     rdi, qword ptr [rsp+200h+Type]
0x18001ce98  lea     rdx, aDcompositioncr; "DCompositionCreateDevice2"
0x18001ce9f  mov     rcx, rbx; hModule
0x18001cea2  call    cs:__imp_GetProcAddress
0x18001cea8  mov     rbx, rax
0x18001ceab  test    rax, rax
0x18001ceae  jz      loc_18001D2AF
0x18001ceb4  mov     [rsp+200h+hKey], r13
0x18001ceb9  lea     rcx, [rsp+200h+hKey]
0x18001cebe  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001cec3  lea     r8, [rsp+200h+hKey]
0x18001cec8  lea     rdx, _GUID_5f4633fe_1e08_4cb8_8c75_ce24333f5602
0x18001cecf  mov     rcx, rdi
0x18001ced2  mov     rax, rbx
0x18001ced5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceda  mov     ebx, eax
0x18001cedc  test    eax, eax
0x18001cede  js      loc_18001D10A
0x18001cee4  mov     rcx, [rsp+200h+hKey]
0x18001cee9  mov     rax, [rcx]
0x18001ceec  lea     r8, [rsp+200h+cbData]
0x18001cef1  lea     rdx, _GUID_c37ea93a_e7aa_450d_b16f_9746cb0407f3
0x18001cef8  mov     rax, [rax]
0x18001cefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf00  mov     ebx, eax
0x18001cf02  test    eax, eax
0x18001cf04  js      loc_18001D312
0x18001cf0a  mov     rcx, [rsp+200h+hKey]
0x18001cf0f  test    rcx, rcx
0x18001cf12  jz      short loc_18001CF25
0x18001cf14  mov     [rsp+200h+hKey], r13
0x18001cf19  mov     rax, [rcx]
0x18001cf1c  mov     rax, [rax+10h]
0x18001cf20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf25  mov     rbx, qword ptr [rsp+200h+cbData]
0x18001cf2a  test    rbx, rbx
0x18001cf2d  jz      loc_18001D03A
0x18001cf33  mov     rax, [rbx]
0x18001cf36  mov     rdi, [rax]
0x18001cf39  mov     rcx, r14
0x18001cf3c  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001cf41  mov     r8, r14
0x18001cf44  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x18001cf4b  mov     rcx, rbx
0x18001cf4e  mov     rax, rdi
0x18001cf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf56  mov     ebx, eax
0x18001cf58  test    eax, eax
0x18001cf5a  js      loc_18001D1B0
0x18001cf60  mov     rcx, qword ptr [rsp+200h+cbData]
0x18001cf65  test    rcx, rcx
0x18001cf68  jz      short loc_18001CF7B
0x18001cf6a  mov     qword ptr [rsp+200h+cbData], r13
0x18001cf6f  mov     rax, [rcx]
0x18001cf72  mov     rax, [rax+10h]
0x18001cf76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf7b  mov     rcx, qword ptr [rsp+200h+Type]
0x18001cf80  test    rcx, rcx
0x18001cf83  jz      short loc_18001CF96
0x18001cf85  mov     qword ptr [rsp+200h+Type], r13
0x18001cf8a  mov     rax, [rcx]
0x18001cf8d  mov     rax, [rax+10h]
0x18001cf91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf96  mov     rcx, [r14]
0x18001cf99  mov     rax, [rcx]
0x18001cf9c  mov     r8, r15
0x18001cf9f  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x18001cfa6  mov     rax, [rax]
0x18001cfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfae  mov     ebx, eax
0x18001cfb0  test    eax, eax
0x18001cfb2  js      loc_18001D220
0x18001cfb8  xor     edx, edx
0x18001cfba  lea     rcx, [rsp+200h+var_1A0]
0x18001cfbf  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001cfc4  test    rsi, rsi
0x18001cfc7  jz      short loc_18001CFD2
0x18001cfc9  mov     rcx, rsi; SRWLock
0x18001cfcc  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cfd2  lea     rcx, [rsp+200h+var_1A0]; this
0x18001cfd7  call    ??1CLockAction__EnsureDevice_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity(void)
0x18001cfdc  xor     eax, eax
0x18001cfde  mov     rcx, [rbp+100h+var_50]
0x18001cfe5  xor     rcx, rsp; StackCookie
0x18001cfe8  call    __security_check_cookie
0x18001cfed  mov     rbx, [rsp+200h+arg_10]
0x18001cff5  movaps  xmm6, [rsp+200h+var_40]
0x18001cffd  add     rsp, 1D0h
0x18001d004  pop     r15
0x18001d006  pop     r14
0x18001d008  pop     r13
0x18001d00a  pop     r12
0x18001d00c  pop     rdi
0x18001d00d  pop     rsi
0x18001d00e  pop     rbp
0x18001d00f  retn
0x18001d010  lea     rdx, [rsp+200h+Data]
0x18001d015  lea     rcx, [rsp+200h+var_1A0]
0x18001d01a  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18001d01f  jmp     loc_18001CE1E
0x18001d024  call    cs:__imp_RegCloseKey
0x18001d02a  nop
0x18001d02b  jmp     loc_18001CDF9
0x18001d030  movaps  xmm6, xmmword ptr [rsp+200h+Data]
0x18001d035  jmp     loc_18001CDEB
0x18001d03a  mov     rcx, [rbp+108h]; this
0x18001d041  mov     r9d, 8007000Eh; char *
0x18001d047  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001d04e  mov     edx, 565h; void *
0x18001d053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d058  mov     rcx, qword ptr [rsp+200h+cbData]
0x18001d05d  test    rcx, rcx
0x18001d060  jz      short loc_18001D073
0x18001d062  mov     qword ptr [rsp+200h+cbData], r13
0x18001d067  mov     rax, [rcx]
0x18001d06a  mov     rax, [rax+10h]
0x18001d06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d073  mov     rcx, qword ptr [rsp+200h+Type]
0x18001d078  test    rcx, rcx
0x18001d07b  jz      short loc_18001D08E
0x18001d07d  mov     qword ptr [rsp+200h+Type], r13
0x18001d082  mov     rax, [rcx]
0x18001d085  mov     rax, [rax+10h]
0x18001d089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d08e  test    rsi, rsi
0x18001d091  jz      short loc_18001D09C
0x18001d093  mov     rcx, rsi; SRWLock
0x18001d096  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d09c  lea     rcx, [rsp+200h+var_1A0]; this
0x18001d0a1  call    ??1CLockAction__EnsureDevice_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity(void)
0x18001d0a6  mov     eax, 8007000Eh
0x18001d0ab  jmp     loc_18001CFDE
0x18001d0b0  xor     edx, edx; hFile
0x18001d0b2  mov     r8d, 800h; dwFlags
0x18001d0b8  lea     rcx, aDcompDll; "dcomp.dll"
0x18001d0bf  call    cs:__imp_LoadLibraryExW
0x18001d0c5  mov     r14, rax
0x18001d0c8  mov     r12, [rbx+1C8h]
0x18001d0cf  test    r12, r12
0x18001d0d2  jnz     loc_18001D2F3
0x18001d0d8  mov     [rbx+1C8h], r14
0x18001d0df  test    r14, r14
0x18001d0e2  jnz     loc_18001CE49
0x18001d0e8  test    rsi, rsi
0x18001d0eb  jz      short loc_18001D0F6
0x18001d0ed  mov     rcx, rsi; SRWLock
0x18001d0f0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d0f6  lea     rcx, [rsp+200h+var_1A0]; this
0x18001d0fb  call    ??1CLockAction__EnsureDevice_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CLockAction__EnsureDevice_Activity::~CLockAction__EnsureDevice_Activity(void)
0x18001d100  mov     eax, 80004001h
0x18001d105  jmp     loc_18001CFDE
0x18001d10a  mov     rcx, [rbp+108h]; this
0x18001d111  mov     r9d, eax; char *
0x18001d114  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001d11b  mov     edx, 545h; void *
0x18001d120  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d125  mov     rcx, [rsp+200h+hKey]
0x18001d12a  test    rcx, rcx
0x18001d12d  jz      short loc_18001D140
0x18001d12f  mov     [rsp+200h+hKey], r13
0x18001d134  mov     rax, [rcx]
0x18001d137  mov     rax, [rax+10h]
0x18001d13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d140  mov     rcx, [rbp+108h]; this
0x18001d147  mov     r9d, ebx; char *
0x18001d14a  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001d151  mov     edx, 564h; void *
0x18001d156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d15b  mov     rcx, qword ptr [rsp+200h+cbData]
0x18001d160  test    rcx, rcx
0x18001d163  jz      short loc_18001D176
0x18001d165  mov     qword ptr [rsp+200h+cbData], r13
0x18001d16a  mov     rax, [rcx]
0x18001d16d  mov     rax, [rax+10h]
0x18001d171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d176  mov     rcx, qword ptr [rsp+200h+Type]
0x18001d17b  test    rcx, rcx
0x18001d17e  jz      short loc_18001D191
0x18001d180  mov     qword ptr [rsp+200h+Type], r13
  ... truncated ...
```
