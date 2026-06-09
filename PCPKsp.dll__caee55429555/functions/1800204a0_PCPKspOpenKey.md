# PCPKspOpenKey

- ea: `0x1800204a0`
- end: `0x1800210b4`
- name: `PCPKspOpenKey`
- size: `3092`
- prototype: `__int64 __fastcall(PCPStorageProvider *, PCPStorageProviderKey **, const wchar_t *, int, unsigned int)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800113f0`
- `0x1800133c4`
- `0x1800159f0`
- `0x18001b860`
- `0x18001c308`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001edb0`
- `0x18001f190`
- `0x18001f1cc`
- `0x18001f2f0`
- `0x1800204a0`
- `0x1800210bc`
- `0x1800212f0`
- `0x180021b7c`
- `0x18003a868`
- `0x18003a8b0`
- `0x18003bad0`
- `0x18004d528`
- `0x180058464`
- `0x180061b6c`
- `0x18006a9c4`
- `0x1800764d0`
- `0x1800769bc`
- `0x18007704c`
- `0x18007c794`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020fbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ff4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020fbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ff4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002062c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002062c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800209a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800209a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020e9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020e9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020537`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020537`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180020edd`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180020edd`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180020eb0`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180020eb0`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180020f34`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180021062`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180020f34`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180021062`

## string_xrefs

- `0x1800204f5`: `PCPKspOpenKey`
- `0x1800207f4`: `PCPKspOpenKey`
- `0x180020543`: `PCPKspOpenKey`
- `0x180020697`: `Found container name, opening container`
- `0x180020a52`: `Container name not found. Attempting to load key directly`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PCPKspOpenKey(
        PCPStorageProvider *a1,
        PCPStorageProviderKey **a2,
        const wchar_t *a3,
        int a4,
        unsigned int a5)
{
  int v9; // r12d
  int v10; // eax
  unsigned int v11; // ebx
  TpmObject *v12; // rbx
  unsigned int v13; // eax
  int ContainerNameFromKeyName; // eax
  int v15; // esi
  PCPStorageProviderKey *v16; // rax
  PCPStorageProviderKey *v17; // rax
  PCPStorageProviderKey *v18; // rbx
  const char *v19; // r9
  __int64 result; // rax
  int v21; // eax
  int v22; // edi
  unsigned __int8 v23; // r14
  WINBOOL v24; // r15d
  int v25; // r12d
  RTL_SRWLOCK *v26; // rbx
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // ebx
  __int64 unique; // rax
  int v31; // eax
  unsigned int v32; // ebx
  HANDLE CurrentProcess; // rax
  BOOL v34; // r12d
  int v35; // eax
  int v36; // eax
  unsigned int v37; // ebx
  const struct wil::FailureInfo *v38; // rdx
  int v39; // [rsp+20h] [rbp-4E8h]
  int v40; // [rsp+20h] [rbp-4E8h]
  char *v41; // [rsp+28h] [rbp-4E0h]
  PCPStorageProvider *v42; // [rsp+30h] [rbp-4D8h] BYREF
  int v43; // [rsp+38h] [rbp-4D0h] BYREF
  WINBOOL Wow64Process; // [rsp+40h] [rbp-4C8h] BYREF
  PCPStorageProviderKey *v45; // [rsp+48h] [rbp-4C0h] BYREF
  PVOID OldValue; // [rsp+58h] [rbp-4B0h] BYREF
  unsigned __int8 v47[8]; // [rsp+60h] [rbp-4A8h]
  PCPStorageProviderKey **v48; // [rsp+68h] [rbp-4A0h] BYREF
  _QWORD v49[7]; // [rsp+70h] [rbp-498h] BYREF
  DWORD TickCount; // [rsp+A8h] [rbp-460h]
  char v51; // [rsp+ACh] [rbp-45Ch]
  _BYTE v52[160]; // [rsp+C0h] [rbp-448h] BYREF
  _QWORD v53[34]; // [rsp+160h] [rbp-3A8h] BYREF
  __int64 v54; // [rsp+270h] [rbp-298h]
  unsigned __int64 v55; // [rsp+278h] [rbp-290h]
  unsigned __int16 v56[264]; // [rsp+2B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+0h]

  v48 = a2;
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v53);
  v53[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  try
  {
    KspDebugProvider::KspDebugActivity::StartActivity((KspDebugProvider::KspDebugActivity *)v53, "PCPKspOpenKey");
    v43 = 0;
    v42 = a1;
    v45 = 0;
    v56[0] = 0;
    memset_0(&v56[1], 0, 0x206u);
    v49[0] = L"PCPKspOpenKey";
    v49[1] = &v42;
    v49[2] = a2;
    v49[3] = 0;
    v49[4] = &v43;
    v49[5] = &a5;
    v49[6] = a3;
    TickCount = GetTickCount();
    v51 = 2;
    if ( !a1 )
    {
      v43 = -2146893786;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090026LL,
        v39);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 2148073510LL;
    }
    if ( !*((_DWORD *)v42 + 2) )
    {
      v43 = -2146893771;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090035LL,
        v39);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 2148073525LL;
    }
    if ( !a2 || !a3 || !*a3 )
    {
      v43 = -2146893785;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090027LL,
        v39);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 2148073511LL;
    }
    KspDebugProvider::TraceLoggingInfo("KeyName = %ls", a3);
    if ( a4 )
    {
      v43 = -2146893783;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090029LL,
        v39);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 2148073513LL;
    }
    if ( (a5 & 0xEFFFFF9F) != 0 )
    {
      v43 = -2146893815;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E1,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090009LL,
        v39);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 2148073481LL;
    }
    v9 = a5 & 0x10000000;
    v10 = PCPStorageProvider::ValidateObject(v42);
    v11 = v10;
    v43 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E5,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v10,
        v39);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return v11;
    }
    v12 = v42;
    if ( (*((_DWORD *)v42 + 3) & 1) == 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v42 + 16));
      v12 = v42;
    }
    if ( !wcscmp_0(a3, L"MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF-004E-4E2F-8A4D-0BF633DCB074") )
    {
      *a2 = (PCPStorageProviderKey *)4294967281LL;
      TpmObject::UnLockProvider(v12);
      KspLoggingProvider::LogOpenKeyFailure(v42, 0, 0, 0, 0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 0;
    }
    v13 = a5 >> 5;
    LOBYTE(v13) = (a5 & 0x20) != 0;
    *(_DWORD *)v47 = v13;
    ContainerNameFromKeyName = PCPStorageProvider::GetContainerNameFromKeyName(v12, a3, v13, 0, v56);
    v15 = ContainerNameFromKeyName;
    if ( ContainerNameFromKeyName == -2146893807 )
    {
      KspDebugProvider::TraceLoggingInfo("Container name not found. Attempting to load key directly");
      unique = wil::make_unique_nothrow<PCPStorageProviderKey,>(&OldValue);
      wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::operator=(&v45, unique);
      wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&OldValue, 0);
      v18 = v45;
      if ( !v45 )
      {
        v43 = -2147024888;
        TpmObject::UnLockProvider(v42);
        KspLoggingProvider::LogOpenKeyFailure(v42, v15, 0, 0, 0);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
        wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
        return 2147942408LL;
      }
      v22 = PCPStorageProviderKey::InitializeLoadFromContainer(v45, v42, a3, 1u);
      v23 = *((_BYTE *)v18 + 700);
      Wow64Process = *((_DWORD *)v18 + 176);
      if ( v22 == -2147024894 )
      {
        v15 = PCPStorageProvider::GetContainerNameFromKeyName(v42, a3, v47[0], 1, v56);
        if ( v15 == -2144795634 )
          KspLoggingProvider::TpmKspWrongParent();
        if ( v9 && v15 == -2144795634 )
        {
          v43 = -2144795634;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x215,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x8029040ELL,
            (int)"The key exists for a previous SRK.",
            v41);
          TpmObject::UnLockProvider(v42);
          KspLoggingProvider::LogOpenKeyFailure(v42, -2144795634, -2147024894, v23, Wow64Process);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
          wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
          return 2150171662LL;
        }
      }
      if ( v23 && v22 != -2147024894 )
      {
        v24 = Wow64Process;
LABEL_20:
        if ( v22 < 0 )
        {
          v36 = SecurityStatusFromHResult(v22);
          v37 = v36;
          v43 = v36;
          if ( v36 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x256,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v36,
              v40);
          TpmObject::UnLockProvider(v42);
          KspLoggingProvider::LogOpenKeyFailure(v42, v15, v22, v23, v24);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
          wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
          return v37;
        }
        else
        {
          *((_QWORD *)v18 + 6) = v42;
          *((_BYTE *)v18 + 652) = v47[0];
          *((_BYTE *)v18 + 736) |= *((_BYTE *)v42 + 92) | ((a5 & 0x40) != 0);
          *v48 = v18;
          v25 = v43;
          if ( v55 )
          {
            v26 = (RTL_SRWLOCK *)(((v55 + 8) & ((unsigned __int128)-(__int128)v55 >> 64)) + 256);
            AcquireSRWLockExclusive(v26);
            v48 = 0;
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v48);
          }
          else
          {
            OldValue = 0;
            v26 = 0;
          }
          v27 = v54;
          v28 = *(_DWORD *)(v54 + 248);
          if ( v28 < 1 )
          {
            memset_0(v52, 0, 0x98u);
            wil::details::WilFailFast((wil::details *)v52, v38);
          }
          if ( *(int *)(v54 + 72) >= 0 )
            *(_DWORD *)(v54 + 72) = v25;
          *(_DWORD *)(v27 + 248) = v28 - 1;
          if ( v26 )
            ReleaseSRWLockExclusive(v26);
          KspDebugProvider::KspDebugActivity::Stop((KspDebugProvider::KspDebugActivity *)v53, "PCPKspOpenKey");
          v29 = v43;
          TpmObject::UnLockProvider(v42);
          if ( v15 < 0 )
            KspLoggingProvider::LogOpenKeyFailure(v42, v15, v22, v23, v24);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
          return v29;
        }
      }
      v43 = -2146893802;
      LODWORD(v41) = v22;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x21C,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090016LL,
        (int)"Load unsuccessful or missing key. hr = 0x%X",
        v41);
      TpmObject::UnLockProvider(v42);
      if ( v15 < 0 || v22 < 0 || !v23 )
        KspLoggingProvider::LogOpenKeyFailure(v42, v15, v22, v23, Wow64Process);
LABEL_48:
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
      return 2148073494LL;
    }
    if ( ContainerNameFromKeyName >= 0 )
    {
      KspDebugProvider::TraceLoggingInfo("Found container name, opening container");
      v16 = (PCPStorageProviderKey *)operator new(0x318u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v16 || (v17 = PCPStorageProviderKey::PCPStorageProviderKey(v16), v18 = v17, (v45 = v17) == 0) )
      {
        v43 = -2147024888;
        TpmObject::UnLockProvider(v42);
        KspLoggingProvider::LogOpenKeyFailure(v42, v15, 0, 0, 0);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
        return 2147942408LL;
      }
      v21 = PCPStorageProviderKey::InitializeLoadFromContainer(v17, v42, v56, 1u);
      v22 = v21;
      v23 = *((_BYTE *)v18 + 700);
      v24 = *((_DWORD *)v18 + 176);
      if ( v23 && v21 != -2147024894 )
        goto LABEL_20;
      Wow64Process = 0;
      CurrentProcess = GetCurrentProcess();
      IsWow64Process(CurrentProcess, &Wow64Process);
      if ( Wow64Process )
      {
        KspDebugProvider::TraceLoggingInfo("Disabling Redirection for Wow64");
        OldValue = 0;
        v34 = Wow64DisableWow64FsRedirection(&OldValue);
        v35 = PCPStorageProviderKey::InitializeLoadFromContainer(v18, v42, v56, 1u);
        v22 = v35;
        v23 = *((_BYTE *)v18 + 700);
        v24 = *((_DWORD *)v18 + 176);
        if ( v23 && v35 != -2147024894 )
        {
          if ( v34 )
            Wow64RevertWow64FsRedirection(OldValue);
          goto LABEL_20;
        }
        KspDebugProvider::TraceLoggingError("Load unsuccessful or missing key. hr = 0x%X", v35);
        v43 = -2146893802;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24B,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)0x80090016LL,
          v40);
        if ( v34 )
          Wow64RevertWow64FsRedirection(OldValue);
        TpmObject::UnLockProvider(v42);
        if ( v22 >= 0 && v23 )
          goto LABEL_48;
      }
      else
      {
        KspDebugProvider::TraceLoggingError("Load unsuccessful or missing key. hr = 0x%X", v22);
        v43 = -2146893802;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x251,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)0x80090016LL,
          v40);
        TpmObject::UnLockProvider(v42);
        if ( v22 >= 0 && v23 )
          goto LABEL_48;
      }
      KspLoggingProvider::LogOpenKeyFailure(v42, v15, v22, v23, v24);
      goto LABEL_48;
    }
    v31 = SecurityStatusFromHResult(ContainerNameFromKeyName);
    v32 = v31;
    v43 = v31;
    if ( v31 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v31,
        v40);
    TpmObject::UnLockProvider(v42);
    KspLoggingProvider::LogOpenKeyFailure(v42, v15, 0, 0, 0);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
    wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(&v45, 0);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v53);
    result = v32;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x281,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x1800204a0  push    rbx
0x1800204a2  push    rsi
0x1800204a3  push    rdi
0x1800204a4  push    r12
0x1800204a6  push    r13
0x1800204a8  push    r14
0x1800204aa  push    r15
0x1800204ac  sub     rsp, 4D0h
0x1800204b3  mov     rax, cs:__security_cookie
0x1800204ba  xor     rax, rsp
0x1800204bd  mov     [rsp+508h+var_48], rax
0x1800204c5  mov     edi, r9d
0x1800204c8  mov     r15, r8
0x1800204cb  mov     rsi, rdx
0x1800204ce  mov     [rsp+508h+var_4A0], rdx
0x1800204d3  mov     rbx, rcx
0x1800204d6  xor     r13d, r13d
0x1800204d9  lea     rcx, [rsp+508h+var_3A8]
0x1800204e1  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800204e6  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x1800204ed  mov     [rsp+508h+var_3A8], rax
0x1800204f5  lea     rdx, aPcpkspopenkey; "PCPKspOpenKey"
0x1800204fc  lea     rcx, [rsp+508h+var_3A8]; this
0x180020504  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x180020509  nop
0x18002050a  mov     [rsp+508h+var_4D0], r13d
0x18002050f  mov     [rsp+508h+var_4D8], rbx
0x180020514  mov     [rsp+508h+var_4C0], r13
0x180020519  mov     [rsp+508h+var_258], r13w
0x180020522  xor     edx, edx; Val
0x180020524  mov     r8d, 206h; Size
0x18002052a  lea     rcx, [rsp+508h+var_258+2]; void *
0x180020532  call    memset_0
0x180020537  call    cs:__imp_GetTickCount
0x18002053e  nop     dword ptr [rax+rax+00h]
0x180020543  lea     rcx, aPcpkspopenkey_0; "PCPKspOpenKey"
0x18002054a  mov     [rsp+508h+var_498], rcx
0x18002054f  lea     rcx, [rsp+508h+var_4D8]
0x180020554  mov     [rsp+508h+var_490], rcx
0x180020559  mov     [rsp+508h+var_488], rsi
0x180020561  mov     [rsp+508h+var_480], r13
0x180020569  lea     rcx, [rsp+508h+var_4D0]
0x18002056e  mov     [rsp+508h+var_478], rcx
0x180020576  lea     rcx, [rsp+508h+arg_20]
0x18002057e  mov     [rsp+508h+var_470], rcx
0x180020586  mov     [rsp+508h+var_468], r15
0x18002058e  mov     [rsp+508h+var_460], eax
0x180020595  mov     [rsp+508h+var_45C], 2
0x18002059d  test    rbx, rbx
0x1800205a0  jz      loc_180020935
0x1800205a6  mov     rax, [rsp+508h+var_4D8]
0x1800205ab  cmp     [rax+8], r13d
0x1800205af  jz      loc_180020C22
0x1800205b5  test    rsi, rsi
0x1800205b8  jz      loc_1800209CD
0x1800205be  test    r15, r15
0x1800205c1  jz      loc_1800209CD
0x1800205c7  cmp     [r15], r13w
0x1800205cb  jz      loc_1800209CD
0x1800205d1  mov     rdx, r15
0x1800205d4  lea     rcx, aKeynameLs; "KeyName = %ls"
0x1800205db  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x1800205e0  test    edi, edi
0x1800205e2  jnz     loc_180020C88
0x1800205e8  mov     r12d, [rsp+508h+arg_20]
0x1800205f0  test    r12d, 0EFFFFF9Fh
0x1800205f7  jnz     loc_180020896
0x1800205fd  and     r12d, 10000000h
0x180020604  mov     rcx, [rsp+508h+var_4D8]; this
0x180020609  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x18002060e  mov     ebx, eax
0x180020610  mov     [rsp+508h+var_4D0], eax
0x180020614  test    eax, eax
0x180020616  js      loc_180020845
0x18002061c  mov     rbx, [rsp+508h+var_4D8]
0x180020621  mov     eax, [rbx+0Ch]
0x180020624  test    al, 1
0x180020626  jnz     short loc_18002063D
0x180020628  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002062c  call    cs:__imp_EnterCriticalSection
0x180020633  nop     dword ptr [rax+rax+00h]
0x180020638  mov     rbx, [rsp+508h+var_4D8]
0x18002063d  lea     rdx, aMicrosoftPcpKs; "MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF"...
0x180020644  mov     rcx, r15; String1
0x180020647  call    wcscmp_0
0x18002064c  test    eax, eax
0x18002064e  jz      loc_1800208F0
0x180020654  mov     eax, [rsp+508h+arg_20]
0x18002065b  shr     eax, 5
0x18002065e  and     al, 1
0x180020660  mov     dword ptr [rsp+508h+var_4A8], eax
0x180020664  lea     rcx, [rsp+508h+var_258]
0x18002066c  mov     [rsp+508h+var_4E8], rcx; int
0x180020671  xor     r9d, r9d; bool
0x180020674  mov     r8b, al; unsigned __int8
0x180020677  mov     rdx, r15; unsigned __int16 *
0x18002067a  mov     rcx, rbx; this
0x18002067d  call    ?GetContainerNameFromKeyName@PCPStorageProvider@@QEAAJPEBGE_NPEAG@Z; PCPStorageProvider::GetContainerNameFromKeyName(ushort const *,uchar,bool,ushort *)
0x180020682  mov     esi, eax
0x180020684  cmp     eax, 80090011h
0x180020689  jz      loc_180020A52
0x18002068f  test    eax, eax
0x180020691  js      loc_180020E1C
0x180020697  lea     rcx, aFoundContainer; "Found container name, opening container"
0x18002069e  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x1800206a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800206aa  mov     ecx, 318h; unsigned __int64
0x1800206af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800206b4  test    rax, rax
0x1800206b7  jz      short loc_1800206CE
0x1800206b9  mov     rcx, rax; this
0x1800206bc  call    ??0PCPStorageProviderKey@@QEAA@XZ; PCPStorageProviderKey::PCPStorageProviderKey(void)
0x1800206c1  mov     rbx, rax
0x1800206c4  mov     [rsp+508h+var_4C0], rax
0x1800206c9  test    rax, rax
0x1800206cc  jnz     short loc_180020716
0x1800206ce  mov     ebx, 80070008h
0x1800206d3  mov     [rsp+508h+var_4D0], ebx
0x1800206d7  mov     rcx, [rsp+508h+var_4D8]; this
0x1800206dc  call    ?UnLockProvider@TpmObject@@QEAAXXZ; TpmObject::UnLockProvider(void)
0x1800206e1  mov     dword ptr [rsp+508h+var_4E8], r13d; unsigned int
0x1800206e6  xor     r9d, r9d; unsigned __int8
0x1800206e9  xor     r8d, r8d; int
0x1800206ec  mov     edx, esi; int
0x1800206ee  mov     rcx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x1800206f3  call    ?LogOpenKeyFailure@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@JJEI@Z; KspLoggingProvider::LogOpenKeyFailure(PCPStorageProvider *,long,long,uchar,uint)
0x1800206f8  lea     rcx, [rsp+508h+var_498]; this
0x1800206fd  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180020702  lea     rcx, [rsp+508h+var_3A8]; this
0x18002070a  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18002070f  mov     eax, ebx
0x180020711  jmp     loc_180020A2E
0x180020716  mov     r9b, 1; unsigned __int8
0x180020719  lea     r8, [rsp+508h+var_258]; unsigned __int16 *
0x180020721  mov     rdx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x180020726  mov     rcx, rbx; this
0x180020729  call    ?InitializeLoadFromContainer@PCPStorageProviderKey@@QEAAJPEAVPCPStorageProvider@@PEBGE@Z; PCPStorageProviderKey::InitializeLoadFromContainer(PCPStorageProvider *,ushort const *,uchar)
0x18002072e  mov     edi, eax
0x180020730  mov     r14b, [rbx+2BCh]
0x180020737  mov     r15d, [rbx+2C0h]
0x18002073e  mov     r13d, 80070002h
0x180020744  test    r14b, r14b
0x180020747  jz      loc_180020E94
0x18002074d  cmp     eax, r13d
0x180020750  jz      loc_180020E94
0x180020756  test    edi, edi
0x180020758  js      loc_180020F45
0x18002075e  mov     rax, [rsp+508h+var_4D8]
0x180020763  mov     [rbx+30h], rax
0x180020767  mov     eax, dword ptr [rsp+508h+var_4A8]
0x18002076b  mov     [rbx+28Ch], al
0x180020771  mov     ecx, [rsp+508h+arg_20]
0x180020778  shr     ecx, 6
0x18002077b  and     cl, 1
0x18002077e  mov     rax, [rsp+508h+var_4D8]
0x180020783  or      cl, [rax+5Ch]
0x180020786  or      [rbx+2E0h], cl
0x18002078c  mov     rax, [rsp+508h+var_4A0]
0x180020791  mov     [rax], rbx
0x180020794  mov     r12d, [rsp+508h+var_4D0]
0x180020799  mov     rcx, [rsp+508h+var_290]
0x1800207a1  test    rcx, rcx
0x1800207a4  jnz     loc_18002098F
0x1800207aa  lea     rax, [rsp+508h+OldValue]
0x1800207af  mov     [rax], rcx
0x1800207b2  mov     rcx, [rsp+508h+OldValue]; SRWLock
0x1800207b7  test    rcx, rcx
0x1800207ba  jnz     loc_180020FBD
0x1800207c0  xor     ebx, ebx
0x1800207c2  mov     rcx, [rsp+508h+var_298]
0x1800207ca  mov     eax, [rcx+0F8h]
0x1800207d0  cmp     eax, 1
0x1800207d3  jl      loc_180020FCE
0x1800207d9  cmp     dword ptr [rcx+48h], 0
0x1800207dd  jl      short loc_1800207E3
0x1800207df  mov     [rcx+48h], r12d
0x1800207e3  dec     eax
0x1800207e5  mov     [rcx+0F8h], eax
0x1800207eb  test    rbx, rbx
0x1800207ee  jnz     loc_180020FF1
0x1800207f4  lea     rdx, aPcpkspopenkey; "PCPKspOpenKey"
0x1800207fb  lea     rcx, [rsp+508h+var_3A8]; this
0x180020803  call    ?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::Stop(char const *)
0x180020808  mov     ebx, [rsp+508h+var_4D0]
0x18002080c  mov     rcx, [rsp+508h+var_4D8]; this
0x180020811  call    ?UnLockProvider@TpmObject@@QEAAXXZ; TpmObject::UnLockProvider(void)
0x180020816  test    esi, esi
0x180020818  js      loc_180021005
0x18002081e  test    r14b, r14b
0x180020821  jz      loc_180021005
0x180020827  lea     rcx, [rsp+508h+var_498]; this
0x18002082c  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180020831  lea     rcx, [rsp+508h+var_3A8]; this
0x180020839  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18002083e  mov     eax, ebx
0x180020840  jmp     loc_180020A2E
0x180020845  mov     rcx, [rsp+508h]; this
0x18002084d  mov     r9d, ebx; char *
0x180020850  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180020857  mov     edx, 1E5h; void *
0x18002085c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020861  mov     dword ptr [rsp+508h+var_4E8], r13d; unsigned int
0x180020866  xor     r9d, r9d; unsigned __int8
0x180020869  xor     r8d, r8d; int
0x18002086c  xor     edx, edx; int
0x18002086e  mov     rcx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x180020873  call    ?LogOpenKeyFailure@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@JJEI@Z; KspLoggingProvider::LogOpenKeyFailure(PCPStorageProvider *,long,long,uchar,uint)
0x180020878  lea     rcx, [rsp+508h+var_498]; this
0x18002087d  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180020882  lea     rcx, [rsp+508h+var_3A8]; this
0x18002088a  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18002088f  mov     eax, ebx
0x180020891  jmp     loc_180020A2E
0x180020896  mov     ebx, 80090009h
0x18002089b  mov     [rsp+508h+var_4D0], ebx
0x18002089f  mov     rcx, [rsp+508h]; this
0x1800208a7  mov     r9d, ebx; char *
0x1800208aa  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800208b1  mov     edx, 1E1h; void *
0x1800208b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208bb  mov     dword ptr [rsp+508h+var_4E8], r13d; unsigned int
0x1800208c0  xor     r9d, r9d; unsigned __int8
0x1800208c3  xor     r8d, r8d; int
0x1800208c6  xor     edx, edx; int
0x1800208c8  mov     rcx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x1800208cd  call    ?LogOpenKeyFailure@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@JJEI@Z; KspLoggingProvider::LogOpenKeyFailure(PCPStorageProvider *,long,long,uchar,uint)
0x1800208d2  lea     rcx, [rsp+508h+var_498]; this
0x1800208d7  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x1800208dc  lea     rcx, [rsp+508h+var_3A8]; this
0x1800208e4  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x1800208e9  mov     eax, ebx
0x1800208eb  jmp     loc_180020A2E
0x1800208f0  mov     eax, 0FFFFFFF1h
0x1800208f5  mov     [rsi], rax
0x1800208f8  mov     rcx, rbx; this
0x1800208fb  call    ?UnLockProvider@TpmObject@@QEAAXXZ; TpmObject::UnLockProvider(void)
0x180020900  mov     dword ptr [rsp+508h+var_4E8], r13d; unsigned int
0x180020905  xor     r9d, r9d; unsigned __int8
0x180020908  xor     r8d, r8d; int
0x18002090b  xor     edx, edx; int
0x18002090d  mov     rcx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x180020912  call    ?LogOpenKeyFailure@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@JJEI@Z; KspLoggingProvider::LogOpenKeyFailure(PCPStorageProvider *,long,long,uchar,uint)
0x180020917  lea     rcx, [rsp+508h+var_498]; this
0x18002091c  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180020921  lea     rcx, [rsp+508h+var_3A8]; this
0x180020929  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18002092e  xor     eax, eax
0x180020930  jmp     loc_180020A2E
0x180020935  mov     ebx, 80090026h
0x18002093a  mov     [rsp+508h+var_4D0], ebx
0x18002093e  mov     rcx, [rsp+508h]; this
0x180020946  mov     r9d, ebx; char *
0x180020949  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180020950  mov     edx, 1D1h; void *
0x180020955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002095a  mov     dword ptr [rsp+508h+var_4E8], r13d; unsigned int
0x18002095f  xor     r9d, r9d; unsigned __int8
0x180020962  xor     r8d, r8d; int
0x180020965  xor     edx, edx; int
0x180020967  mov     rcx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x18002096c  call    ?LogOpenKeyFailure@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@JJEI@Z; KspLoggingProvider::LogOpenKeyFailure(PCPStorageProvider *,long,long,uchar,uint)
0x180020971  lea     rcx, [rsp+508h+var_498]; this
0x180020976  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18002097b  lea     rcx, [rsp+508h+var_3A8]; this
0x180020983  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180020988  mov     eax, ebx
0x18002098a  jmp     loc_180020A2E
0x18002098f  lea     rax, [rcx+8]
0x180020993  neg     rcx
0x180020996  sbb     rbx, rbx
0x180020999  and     rbx, rax
0x18002099c  add     rbx, 100h
0x1800209a3  mov     rcx, rbx; SRWLock
0x1800209a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800209ad  nop     dword ptr [rax+rax+00h]
0x1800209b2  lea     rax, [rsp+508h+var_4A0]
0x1800209b7  mov     qword ptr [rax], 0
0x1800209be  lea     rcx, [rsp+508h+var_4A0]
0x1800209c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800209c8  jmp     loc_1800207C2
0x1800209cd  mov     ebx, 80090027h
0x1800209d2  mov     [rsp+508h+var_4D0], ebx
0x1800209d6  mov     rcx, [rsp+508h]; this
0x1800209de  mov     r9d, ebx; char *
0x1800209e1  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800209e8  mov     edx, 1D8h; void *
0x1800209ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209f2  mov     dword ptr [rsp+508h+var_4E8], r13d; unsigned int
0x1800209f7  xor     r9d, r9d; unsigned __int8
0x1800209fa  xor     r8d, r8d; int
0x1800209fd  xor     edx, edx; int
0x1800209ff  mov     rcx, [rsp+508h+var_4D8]; struct PCPStorageProvider *
0x180020a04  call    ?LogOpenKeyFailure@KspLoggingProvider@@SAXPEAVPCPStorageProvider@@JJEI@Z; KspLoggingProvider::LogOpenKeyFailure(PCPStorageProvider *,long,long,uchar,uint)
0x180020a09  lea     rcx, [rsp+508h+var_498]; this
0x180020a0e  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180020a13  xor     edx, edx
0x180020a15  lea     rcx, [rsp+508h+var_4C0]
0x180020a1a  call    ?reset@?$unique_ptr@VPCPStorageProviderKey@@U?$default_delete@VPCPStorageProviderKey@@@wistd@@@wistd@@QEAAXPEAVPCPStorageProviderKey@@@Z; wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(PCPStorageProviderKey *)
0x180020a1f  lea     rcx, [rsp+508h+var_3A8]; this
0x180020a27  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
  ... truncated ...
```
