# ServiceBeginAcquireLicenseImpl(void *,ushort const *,int,unsigned __int64)

- ea: `0x180045750`
- end: `0x18004637f`
- name: `?ServiceBeginAcquireLicenseImpl@@YAJPEAXPEBGH_K@Z`
- size: `3119`
- prototype: `int(void *, const unsigned __int16 *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045740`

## callees

- `0x18000b14c`
- `0x18000cca0`
- `0x18000f07c`
- `0x1800104c8`
- `0x180011960`
- `0x1800119e0`
- `0x180013b50`
- `0x180017740`
- `0x1800397ac`
- `0x180045750`
- `0x1800593bc`
- `0x18006eba8`
- `0x180075e60`
- `0x180076300`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045f1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004627a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004630c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004634a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004627a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004630c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004634a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046364`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045f82`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045f82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045a85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045a85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180045cf0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180045aa1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180045d09`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180045aa1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180045d09`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800458d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800458d5`
- `ntdll!EtwEventWriteTransfer` at `0x180045a1a`
- `ntdll!EtwEventWriteTransfer` at `0x180045a1a`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180045794`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180045794`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x180045c2c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x180045c2c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045ada`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045d3f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045ef6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045ada`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045d3f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045ef6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004606d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004606d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180045c67`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180045c67`

## string_xrefs

- `0x180045885`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180046196`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180046223`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180046234`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18004586c`: `ServiceBeginAcquireLicenseImpl PsmKey:%s, IsSystemUsage:%d`
- `0x180045878`: `ServiceBeginAcquireLicenseImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ServiceBeginAcquireLicenseImpl(void *a1, const unsigned __int16 *a2, int a3, __int64 a4)
{
  const char *v8; // r9
  const struct std::nothrow_t *v9; // rdx
  void *v10; // rcx
  __int64 v11; // rcx
  __int64 result; // rax
  void **v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  char v16; // bl
  bool v17; // di
  HANDLE CurrentThread; // rax
  int v19; // eax
  __int64 EffectiveToken; // rdi
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  int ImpersonationTokenForContext; // eax
  const char *v24; // r9
  char v25; // bl
  bool v26; // di
  HANDLE v27; // rax
  int v28; // eax
  __int64 v29; // rdi
  int v30; // eax
  wil::details::in1diag3 *v31; // rcx
  __int64 TokenSID; // rbx
  const char *v33; // r9
  int v34; // ebx
  __int64 v35; // rcx
  bool v36; // di
  __int64 v37; // rcx
  const char *v38; // r9
  __int64 v39; // rcx
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rcx
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rcx
  __int64 v44; // rcx
  signed int LastError; // eax
  int v46; // edx
  unsigned int v47; // r8d
  signed int v48; // eax
  int v49; // edx
  unsigned int v50; // r8d
  signed int v51; // eax
  int v52; // edx
  unsigned int v53; // r8d
  signed int v54; // eax
  int v55; // edx
  unsigned int v56; // r8d
  signed int v57; // eax
  int v58; // edx
  unsigned int v59; // r8d
  signed int v60; // eax
  int v61; // edx
  unsigned int v62; // r8d
  signed int v63; // eax
  int v64; // edx
  unsigned int v65; // r8d
  signed int v66; // eax
  int v67; // edx
  unsigned int v68; // r8d
  signed int v69; // eax
  int v70; // edx
  unsigned int v71; // r8d
  signed int v72; // eax
  int v73; // edx
  unsigned int v74; // r8d
  signed int v75; // eax
  int v76; // edx
  unsigned int v77; // r8d
  signed int v78; // eax
  int v79; // edx
  unsigned int v80; // r8d
  int ReturnLength; // [rsp+20h] [rbp-178h]
  int ReturnLengtha; // [rsp+20h] [rbp-178h]
  PHANDLE phNewToken; // [rsp+28h] [rbp-170h]
  int TokenInformation; // [rsp+50h] [rbp-148h] BYREF
  DWORD v85[2]; // [rsp+58h] [rbp-140h] BYREF
  void **v86; // [rsp+60h] [rbp-138h] BYREF
  HANDLE hExistingToken; // [rsp+68h] [rbp-130h] BYREF
  void **v88; // [rsp+70h] [rbp-128h] BYREF
  HANDLE Token; // [rsp+78h] [rbp-120h] BYREF
  RTL_SRWLOCK *TickCount64; // [rsp+80h] [rbp-118h] BYREF
  __int64 v91; // [rsp+88h] [rbp-110h]
  void **v92; // [rsp+90h] [rbp-108h] BYREF
  __int64 v93; // [rsp+98h] [rbp-100h]
  void **v94; // [rsp+A0h] [rbp-F8h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp-F0h] BYREF
  __int64 v96; // [rsp+B0h] [rbp-E8h] BYREF
  void *v97[2]; // [rsp+B8h] [rbp-E0h] BYREF
  __int64 v98; // [rsp+C8h] [rbp-D0h]
  unsigned __int64 v99; // [rsp+D0h] [rbp-C8h]
  void *v100[2]; // [rsp+D8h] [rbp-C0h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-B0h]
  unsigned __int64 v102; // [rsp+F0h] [rbp-A8h]
  void *v103; // [rsp+100h] [rbp-98h] BYREF
  int v104; // [rsp+108h] [rbp-90h]
  int v105; // [rsp+10Ch] [rbp-8Ch]
  __int16 *v106; // [rsp+110h] [rbp-88h]
  int v107; // [rsp+118h] [rbp-80h]
  int v108; // [rsp+11Ch] [rbp-7Ch]
  void **v109; // [rsp+120h] [rbp-78h]
  int v110; // [rsp+128h] [rbp-70h]
  int v111; // [rsp+12Ch] [rbp-6Ch]
  int *p_TokenInformation; // [rsp+130h] [rbp-68h]
  __int64 v113; // [rsp+138h] [rbp-60h]
  RTL_SRWLOCK **p_TickCount64; // [rsp+140h] [rbp-58h]
  __int64 v115; // [rsp+148h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v96 = 0;
  GetProcessReference(&v96);
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8FB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)0x80004003LL,
        ReturnLength);
    GetPackageFullNameFromPsmKey(v97);
    if ( (unsigned __int8)SkipForAppCompat(v97) )
    {
      if ( v99 <= 7 )
      {
LABEL_10:
        v98 = 0;
        v99 = 7;
        LOWORD(v97[0]) = 0;
        v11 = v96;
        if ( v96 )
        {
          v96 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        return 0;
      }
      v9 = (const struct std::nothrow_t *)(2 * v99 + 2);
      if ( (unsigned __int64)v9 < 0x1000 )
      {
        v10 = v97[0];
        goto LABEL_9;
      }
      v10 = (void *)*((_QWORD *)v97[0] - 1);
      if ( (unsigned __int64)((char *)v97[0] - (char *)v10 - 8) <= 0x1F )
      {
        v9 = (const struct std::nothrow_t *)(2 * v99 + 41);
LABEL_9:
        operator delete(v10, v9);
        goto LABEL_10;
      }
LABEL_105:
      __fastfail(5u);
    }
    HIDWORD(phNewToken) = HIDWORD(a2);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x900u,
      "ServiceBeginAcquireLicenseImpl",
      (wchar_t *)L"ServiceBeginAcquireLicenseImpl PsmKey:%s, IsSystemUsage:%d");
    if ( (unsigned int)dword_1800F11D0 > 5
      && (qword_1800F11E0 & 0x200000000000LL) != 0
      && (qword_1800F11E8 & 0x200000000000LL) == qword_1800F11E8 )
    {
      TickCount64 = (RTL_SRWLOCK *)GetTickCount64();
      TokenInformation = a3;
      v13 = v97;
      if ( v99 > 7 )
        v13 = (void **)v97[0];
      p_TickCount64 = &TickCount64;
      v115 = 8;
      p_TokenInformation = &TokenInformation;
      v113 = 4;
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)v13 + v14) );
        v15 = 2 * v14 + 2;
      }
      else
      {
        v13 = (void **)&LocaleName;
        v15 = 2;
      }
      v109 = v13;
      v110 = v15;
      v111 = 0;
      v86 = (void **)0x50B000000LL;
      hExistingToken = (HANDLE)0x200000000000LL;
      v103 = off_1800F11D8;
      v104 = *(unsigned __int16 *)off_1800F11D8;
      v105 = 2;
      v106 = word_1800D73E2;
      v107 = 79;
      v108 = 1;
      v85[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      phNewToken = &v103;
      ReturnLengtha = 5;
      EtwEventWriteTransfer(qword_1800F11F0, &v86, 0, 0);
    }
    v88 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Token = 0;
    v92 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    v93 = 0;
    if ( a4 )
    {
      TickCount64 = (RTL_SRWLOCK *)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      v91 = 0;
      v16 = 0;
      LOBYTE(v100[0]) = 0;
      v100[1] = a1;
      v17 = 0;
      v94 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
      {
        TokenInformation = 0;
        v85[0] = 4;
        if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, v85) )
          v17 = TokenInformation == 2;
      }
      v94 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( TokenHandle )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v94) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v46, v47);
          __debugbreak();
        }
        TokenHandle = 0;
      }
      if ( !v17 )
      {
        v19 = _RpcImpersonateClient(a1);
        if ( v19 >= 1 )
          v19 |= 0x80010000;
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1BE,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
            (const char *)(unsigned int)v19,
            ReturnLengtha);
        v16 = 1;
        LOBYTE(v100[0]) = 1;
      }
      EffectiveToken = GetEffectiveToken(&v94);
      if ( v91 )
      {
        if ( !((unsigned __int8 (__fastcall *)(RTL_SRWLOCK **))TickCount64->Ptr)(&TickCount64) )
        {
          v48 = GetLastError();
          if ( v48 > 0 )
            v48 = (unsigned __int16)v48 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v48, v49, v50);
          __debugbreak();
        }
        v91 = 0;
      }
      v91 = *(_QWORD *)(EffectiveToken + 8);
      *(_QWORD *)(EffectiveToken + 8) = 0;
      v94 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( TokenHandle )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v94) )
        {
          v51 = GetLastError();
          if ( v51 > 0 )
            v51 = (unsigned __int16)v51 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v51, v52, v53);
          goto LABEL_122;
        }
        TokenHandle = 0;
      }
      if ( !v16 )
        goto LABEL_46;
      v21 = _RpcRevertToSelfEx(a1);
      if ( v21 >= 1 )
        v21 |= 0x80010000;
      v22 = retaddr;
      if ( v21 >= 0 )
      {
LABEL_46:
        v86 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        hExistingToken = 0;
        ImpersonationTokenForContext = UMgrGetImpersonationTokenForContext(v91, a4, &hExistingToken);
        if ( ImpersonationTokenForContext < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x914,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)ImpersonationTokenForContext,
            ReturnLengtha);
        if ( !DuplicateTokenEx(hExistingToken, 0x2000Eu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x916,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            v24);
        v86 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        if ( hExistingToken )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v86) )
          {
            v54 = GetLastError();
            if ( v54 > 0 )
              v54 = (unsigned __int16)v54 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v54, v55, v56);
            goto LABEL_128;
          }
          hExistingToken = 0;
        }
        TickCount64 = (RTL_SRWLOCK *)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        if ( !v91
          || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&TickCount64) )
        {
          goto LABEL_75;
        }
LABEL_128:
        v57 = GetLastError();
        if ( v57 > 0 )
          v57 = (unsigned __int16)v57 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v57, v58, v59);
        __debugbreak();
      }
LABEL_122:
      wil::details::in1diag3::Throw_Hr(
        v22,
        (void *)0x1C4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
        (const char *)(unsigned int)v21,
        ReturnLengtha);
    }
    v25 = 0;
    LOBYTE(v100[0]) = 0;
    v100[1] = a1;
    v26 = 0;
    v86 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    hExistingToken = 0;
    v27 = GetCurrentThread();
    if ( OpenThreadToken(v27, 0x20008u, 1, &hExistingToken) )
    {
      TokenInformation = 0;
      v85[0] = 4;
      if ( GetTokenInformation(hExistingToken, TokenType, &TokenInformation, 4u, v85) )
        v26 = TokenInformation == 2;
    }
    v86 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( hExistingToken )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v86) )
      {
        v60 = GetLastError();
        if ( v60 > 0 )
          v60 = (unsigned __int16)v60 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v60, v61, v62);
        __debugbreak();
      }
      hExistingToken = 0;
    }
    if ( !v26 )
    {
      v28 = _RpcImpersonateClient(a1);
      if ( v28 >= 1 )
        v28 |= 0x80010000;
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          (const char *)(unsigned int)v28,
          ReturnLengtha);
      v25 = 1;
      LOBYTE(v100[0]) = 1;
    }
    v29 = GetEffectiveToken(&v86);
    if ( Token )
    {
      if ( !((unsigned __int8 (__fastcall *)(void ***))*v88)(&v88) )
      {
        v63 = GetLastError();
        if ( v63 > 0 )
          v63 = (unsigned __int16)v63 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v63, v64, v65);
        __debugbreak();
      }
      Token = 0;
    }
    Token = *(HANDLE *)(v29 + 8);
    *(_QWORD *)(v29 + 8) = 0;
    v86 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( hExistingToken )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v86) )
      {
        v66 = GetLastError();
        if ( v66 > 0 )
          v66 = (unsigned __int16)v66 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v66, v67, v68);
        goto LABEL_141;
      }
      hExistingToken = 0;
    }
    if ( !v25 )
      goto LABEL_75;
    v30 = _RpcRevertToSelfEx(a1);
    if ( v30 >= 1 )
      v30 |= 0x80010000;
    v31 = retaddr;
    if ( v30 >= 0 )
    {
LABEL_75:
      TokenSID = GetTokenSID(&v86, &v88);
      if ( v93 )
      {
        if ( !((unsigned __int8 (__fastcall *)(void ***))*v92)(&v92) )
        {
          v69 = GetLastError();
          if ( v69 > 0 )
            v69 = (unsigned __int16)v69 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v69, v70, v71);
          __debugbreak();
        }
        v93 = 0;
      }
      v93 = *(_QWORD *)(TokenSID + 8);
      *(_QWORD *)(TokenSID + 8) = 0;
      v86 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      if ( hExistingToken
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v86) )
      {
        v72 = GetLastError();
        if ( v72 > 0 )
          v72 = (unsigned __int16)v72 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v72, v73, v74);
        __debugbreak();
      }
      TokenInformation = 0;
      v85[0] = 4;
      if ( !GetTokenInformation(Token, TokenSessionId, &TokenInformation, 4u, v85) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
          v33);
      v34 = TokenInformation;
      AcquireSRWLockExclusive(&PendingRequestsLock);
      TickCount64 = &PendingRequestsLock;
      LODWORD(phNewToken) = v34;
      v36 = *(_QWORD *)PendingRequestManager::FindExisting(v35, v85, v97, a2, v93, phNewToken, a3) == 0;
      v37 = *(_QWORD *)v85;
      if ( *(_QWORD *)v85 )
      {
        *(_QWORD *)v85 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      if ( v36 )
      {
        if ( !SetThreadToken(0, Token) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x221,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
            v38);
        *(_OWORD *)v100 = 0;
        v101 = 0;
        v102 = 7;
        LOWORD(v100[0]) = 0;
        PendingRequestManager::AddRequest((int)retaddr, (int)v85, (int)v97, (int)a2, 0, v93, v34, a3, (__int64)v100, 0);
        v39 = *(_QWORD *)v85;
        if ( *(_QWORD *)v85 )
        {
          *(_QWORD *)v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        }
        if ( v102 > 7 )
        {
          v40 = (const struct std::nothrow_t *)(2 * v102 + 2);
          if ( (unsigned __int64)v40 < 0x1000 )
          {
            v41 = v100[0];
          }
          else
          {
            v41 = (void *)*((_QWORD *)v100[0] - 1);
            if ( (unsigned __int64)((char *)v100[0] - (char *)v41 - 8) > 0x1F )
              __fastfail(5u);
            v40 = (const struct std::nothrow_t *)(2 * v102 + 41);
          }
          operator delete(v41, v40);
        }
        RevertToSelf();
      }
      ReleaseSRWLockExclusive(&PendingRequestsLock);
      v92 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      if ( v93 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v92) )
        {
          v75 = GetLastError();
          if ( v75 > 0 )
            v75 = (unsigned __int16)v75 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v75, v76, v77);
          goto LABEL_153;
        }
        v93 = 0;
      }
      v88 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( !Token )
      {
LABEL_101:
        if ( v99 > 7 )
        {
          v42 = (const struct std::nothrow_t *)(2 * v99 + 2);
          if ( (unsigned __int64)v42 < 0x1000 )
          {
            v43 = v97[0];
          }
          else
          {
            v43 = (void *)*((_QWORD *)v97[0] - 1);
            if ( (unsigned __int64)((char *)v97[0] - (char *)v43 - 8) > 0x1F )
              goto LABEL_105;
            v42 = (const struct std::nothrow_t *)(2 * v99 + 41);
          }
          operator delete(v43, v42);
        }
        v98 = 0;
        v99 = 7;
        LOWORD(v97[0]) = 0;
        v44 = v96;
        if ( v96 )
        {
          v96 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        return 0;
      }
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v88) )
      {
        Token = 0;
        goto LABEL_101;
      }
LABEL_153:
      v78 = GetLastError();
      if ( v78 > 0 )
        v78 = (unsigned __int16)v78 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v78, v79, v80);
      JUMPOUT(0x18004637DLL);
    }
LABEL_141:
    wil::details::in1diag3::Throw_Hr(
      v31,
      (void *)0x1C4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
      (const char *)(unsigned int)v30,
      ReturnLengtha);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x92C,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180045750  push    rbx
0x180045752  push    rsi
0x180045753  push    rdi
0x180045754  push    r12
0x180045756  push    r13
0x180045758  push    r14
0x18004575a  push    r15
0x18004575c  sub     rsp, 160h
0x180045763  mov     rax, cs:__security_cookie
0x18004576a  xor     rax, rsp
0x18004576d  mov     [rsp+198h+var_40], rax
0x180045775  mov     r15, r9
0x180045778  mov     r12d, r8d
0x18004577b  mov     r14, rdx
0x18004577e  mov     rsi, rcx
0x180045781  xor     r13d, r13d
0x180045784  mov     [rsp+198h+var_E8], r13
0x18004578c  lea     rcx, [rsp+198h+var_E8]
0x180045794  call    cs:__imp_GetProcessReference
0x18004579a  nop
0x18004579b  mov     rcx, [rsp+198h]; this
0x1800457a3  test    r14, r14
0x1800457a6  jz      loc_180046190
0x1800457ac  mov     rdx, r14
0x1800457af  lea     rcx, [rsp+198h+var_E0]
0x1800457b7  call    ?GetPackageFullNameFromPsmKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetPackageFullNameFromPsmKey(ushort const *)
0x1800457bc  nop
0x1800457bd  lea     rcx, [rsp+198h+var_E0]
0x1800457c5  call    ?SkipForAppCompat@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SkipForAppCompat(std::wstring const &)
0x1800457ca  test    al, al
0x1800457cc  jz      loc_180045862
0x1800457d2  mov     rdx, [rsp+198h+var_C8]
0x1800457da  cmp     rdx, 7
0x1800457de  jbe     short loc_18004581C
0x1800457e0  mov     rax, [rsp+198h+var_E0]
0x1800457e8  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x1800457f0  cmp     rdx, 1000h
0x1800457f7  jb      short loc_180045814
0x1800457f9  mov     rcx, [rax-8]
0x1800457fd  sub     rax, rcx
0x180045800  sub     rax, 8
0x180045804  cmp     rax, 1Fh
0x180045808  ja      loc_180046117
0x18004580e  add     rdx, 27h ; '''
0x180045812  jmp     short loc_180045817
0x180045814  mov     rcx, rax; void *
0x180045817  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004581c  mov     [rsp+198h+var_D0], r13
0x180045824  mov     [rsp+198h+var_C8], 7
0x180045830  mov     word ptr [rsp+198h+var_E0], r13w
0x180045839  mov     rcx, [rsp+198h+var_E8]
0x180045841  test    rcx, rcx
0x180045844  jz      short loc_18004585B
0x180045846  mov     [rsp+198h+var_E8], r13
0x18004584e  mov     rax, [rcx]
0x180045851  mov     rax, [rax+10h]
0x180045855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004585a  nop
0x18004585b  xor     eax, eax
0x18004585d  jmp     loc_18004616D
0x180045862  mov     [rsp+198h+var_168], r12d
0x180045867  mov     [rsp+198h+phNewToken], r14
0x18004586c  lea     rax, aServicebeginac_0; "ServiceBeginAcquireLicenseImpl PsmKey:%"...
0x180045873  mov     [rsp+198h+ReturnLength], rax; Format
0x180045878  lea     r9, aServicebeginac_1; "ServiceBeginAcquireLicenseImpl"
0x18004587f  mov     r8d, 900h; unsigned int
0x180045885  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18004588c  mov     ecx, 3; unsigned int
0x180045891  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180045896  mov     eax, cs:dword_1800F11D0
0x18004589c  cmp     eax, 5
0x18004589f  jbe     loc_180045A20
0x1800458a5  mov     rcx, cs:qword_1800F11E8
0x1800458ac  mov     rax, cs:qword_1800F11E0
0x1800458b3  mov     rbx, 200000000000h
0x1800458bd  test    rbx, rax
0x1800458c0  jz      loc_180045A20
0x1800458c6  mov     rax, rcx
0x1800458c9  and     rax, rbx
0x1800458cc  cmp     rax, rcx
0x1800458cf  jnz     loc_180045A20
0x1800458d5  call    cs:__imp_GetTickCount64
0x1800458db  mov     [rsp+198h+var_118], rax
0x1800458e3  mov     [rsp+198h+TokenInformation], r12d
0x1800458e8  lea     rcx, [rsp+198h+var_E0]
0x1800458f0  cmp     [rsp+198h+var_C8], 7
0x1800458f9  cmova   rcx, [rsp+198h+var_E0]
0x180045902  lea     rax, [rsp+198h+var_118]
0x18004590a  mov     [rsp+198h+var_58], rax
0x180045912  mov     [rsp+198h+var_50], 8
0x18004591e  lea     rax, [rsp+198h+TokenInformation]
0x180045923  mov     [rsp+198h+var_68], rax
0x18004592b  mov     [rsp+198h+var_60], 4
0x180045937  test    rcx, rcx
0x18004593a  jz      short loc_180045957
0x18004593c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180045943  lea     rax, [rax+1]
0x180045947  cmp     word ptr [rcx+rax*2], 0
0x18004594c  jnz     short loc_180045943
0x18004594e  lea     eax, ds:2[rax*2]
0x180045955  jmp     short loc_180045963
0x180045957  lea     rcx, LocaleName
0x18004595e  mov     eax, 2
0x180045963  mov     [rsp+198h+var_78], rcx
0x18004596b  mov     [rsp+198h+var_70], eax
0x180045972  mov     [rsp+198h+var_6C], r13d
0x18004597a  mov     dword ptr [rsp+198h+var_138], 0B000000h
0x180045982  movzx   eax, cs:word_1800D73D8
0x180045989  mov     dword ptr [rsp+198h+var_138+4], eax
0x18004598d  mov     [rsp+198h+hExistingToken], rbx
0x180045992  mov     rax, cs:off_1800F11D8
0x180045999  mov     [rsp+198h+var_98], rax
0x1800459a1  movzx   eax, word ptr [rax]
0x1800459a4  mov     [rsp+198h+var_90], eax
0x1800459ab  mov     [rsp+198h+var_8C], 2
0x1800459b6  lea     rax, word_1800D73E2
0x1800459bd  mov     [rsp+198h+var_88], rax
0x1800459c5  mov     [rsp+198h+var_80], 4Fh ; 'O'
0x1800459d0  mov     [rsp+198h+var_7C], 1
0x1800459db  lea     rax, _TraceLoggingMetadataEnd
0x1800459e2  lea     rcx, _TraceLoggingMetadata
0x1800459e9  sub     eax, ecx
0x1800459eb  mov     [rsp+198h+var_140], eax
0x1800459ef  mov     eax, [rsp+198h+var_140]
0x1800459f3  lea     rax, [rsp+198h+var_98]
0x1800459fb  mov     [rsp+198h+phNewToken], rax
0x180045a00  mov     dword ptr [rsp+198h+ReturnLength], 5
0x180045a08  xor     r9d, r9d
0x180045a0b  xor     r8d, r8d
0x180045a0e  lea     rdx, [rsp+198h+var_138]
0x180045a13  mov     rcx, cs:qword_1800F11F0
0x180045a1a  call    cs:__imp_EtwEventWriteTransfer
0x180045a20  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180045a27  mov     [rsp+198h+var_128], rax
0x180045a2c  mov     [rsp+198h+Token], r13
0x180045a31  lea     rcx, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180045a38  mov     [rsp+198h+var_108], rcx
0x180045a40  mov     [rsp+198h+var_100], r13
0x180045a48  test    r15, r15
0x180045a4b  jz      loc_180045CD2
0x180045a51  mov     [rsp+198h+var_118], rax
0x180045a59  mov     [rsp+198h+var_110], r13
0x180045a61  xor     bl, bl
0x180045a63  mov     byte ptr [rsp+198h+var_C0], bl
0x180045a6a  mov     [rsp+198h+var_C0+8], rsi
0x180045a72  xor     dil, dil
0x180045a75  mov     [rsp+198h+var_F8], rax
0x180045a7d  mov     [rsp+198h+TokenHandle], r13
0x180045a85  call    cs:__imp_GetCurrentThread
0x180045a8b  lea     r9, [rsp+198h+TokenHandle]; TokenHandle
0x180045a93  mov     edx, 20008h; DesiredAccess
0x180045a98  mov     r8d, 1; OpenAsSelf
0x180045a9e  mov     rcx, rax; ThreadHandle
0x180045aa1  call    cs:__imp_OpenThreadToken
0x180045aa7  test    eax, eax
0x180045aa9  jz      short loc_180045AED
0x180045aab  mov     [rsp+198h+TokenInformation], r13d
0x180045ab0  mov     [rsp+198h+var_140], 4
0x180045ab8  lea     rax, [rsp+198h+var_140]
0x180045abd  mov     [rsp+198h+ReturnLength], rax; int
0x180045ac2  mov     r9d, 4; TokenInformationLength
0x180045ac8  lea     r8, [rsp+198h+TokenInformation]; TokenInformation
0x180045acd  mov     edx, 8; TokenInformationClass
0x180045ad2  mov     rcx, [rsp+198h+TokenHandle]; TokenHandle
0x180045ada  call    cs:__imp_GetTokenInformation
0x180045ae0  test    eax, eax
0x180045ae2  jz      short loc_180045AED
0x180045ae4  cmp     [rsp+198h+TokenInformation], 2
0x180045ae9  setz    dil
0x180045aed  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180045af4  mov     [rsp+198h+var_F8], rax
0x180045afc  cmp     [rsp+198h+TokenHandle], 0
0x180045b05  jz      short loc_180045B24
0x180045b07  lea     rcx, [rsp+198h+var_F8]
0x180045b0f  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180045b14  test    al, al
0x180045b16  jz      loc_1800461A8
0x180045b1c  mov     [rsp+198h+TokenHandle], r13
0x180045b24  test    dil, dil
0x180045b27  jnz     short loc_180045B5B
0x180045b29  mov     rcx, rsi
0x180045b2c  mov     rax, cs:?_RpcImpersonateClient@@3P6AJPEAX@ZEA; long (*_RpcImpersonateClient)(void *)
0x180045b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b38  cmp     eax, 1
0x180045b3b  jl      short loc_180045B42
0x180045b3d  or      eax, 80010000h
0x180045b42  mov     rcx, [rsp+198h]; this
0x180045b4a  test    eax, eax
0x180045b4c  js      loc_1800461C2
0x180045b52  mov     bl, 1
0x180045b54  mov     byte ptr [rsp+198h+var_C0], bl
0x180045b5b  lea     rcx, [rsp+198h+var_F8]
0x180045b63  call    ?GetEffectiveToken@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; GetEffectiveToken(void)
0x180045b68  mov     rdi, rax
0x180045b6b  cmp     [rsp+198h+var_110], 0
0x180045b74  jz      short loc_180045B9E
0x180045b76  mov     rcx, [rsp+198h+var_118]
0x180045b7e  mov     rax, [rcx]
0x180045b81  lea     rcx, [rsp+198h+var_118]
0x180045b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b8e  test    al, al
0x180045b90  jz      loc_1800461D7
0x180045b96  mov     [rsp+198h+var_110], r13
0x180045b9e  mov     rax, [rdi+8]
0x180045ba2  mov     [rsp+198h+var_110], rax
0x180045baa  mov     [rdi+8], r13
0x180045bae  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180045bb5  mov     [rsp+198h+var_F8], rdi
0x180045bbd  cmp     [rsp+198h+TokenHandle], 0
0x180045bc6  jz      short loc_180045BE5
0x180045bc8  lea     rcx, [rsp+198h+var_F8]
0x180045bd0  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180045bd5  test    al, al
0x180045bd7  jz      loc_1800461F1
0x180045bdd  mov     [rsp+198h+TokenHandle], r13
0x180045be5  test    bl, bl
0x180045be7  jz      short loc_180045C12
0x180045be9  mov     rcx, rsi
0x180045bec  mov     rax, cs:?_RpcRevertToSelfEx@@3P6AJPEAX@ZEA; long (*_RpcRevertToSelfEx)(void *)
0x180045bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bf8  cmp     eax, 1
0x180045bfb  jl      short loc_180045C02
0x180045bfd  or      eax, 80010000h
0x180045c02  mov     rcx, [rsp+198h]
0x180045c0a  test    eax, eax
0x180045c0c  js      loc_18004620B
0x180045c12  mov     [rsp+198h+var_138], rdi
0x180045c17  mov     [rsp+198h+hExistingToken], r13
0x180045c1c  lea     r8, [rsp+198h+hExistingToken]
0x180045c21  mov     rdx, r15
0x180045c24  mov     rcx, [rsp+198h+var_110]
0x180045c2c  call    cs:__imp_UMgrGetImpersonationTokenForContext
0x180045c32  mov     rcx, [rsp+198h]; this
0x180045c3a  test    eax, eax
0x180045c3c  js      loc_180046220
0x180045c42  lea     rax, [rsp+198h+Token]
0x180045c47  mov     [rsp+198h+phNewToken], rax; phNewToken
0x180045c4c  mov     dword ptr [rsp+198h+ReturnLength], 2; TokenType
0x180045c54  mov     r9d, 2; ImpersonationLevel
0x180045c5a  xor     r8d, r8d; lpTokenAttributes
0x180045c5d  mov     edx, 2000Eh; dwDesiredAccess
0x180045c62  mov     rcx, [rsp+198h+hExistingToken]; hExistingToken
0x180045c67  call    cs:__imp_DuplicateTokenEx
0x180045c6d  mov     rcx, [rsp+198h]; this
0x180045c75  test    eax, eax
0x180045c77  jz      loc_180046234
0x180045c7d  mov     [rsp+198h+var_138], rdi
0x180045c82  cmp     [rsp+198h+hExistingToken], 0
0x180045c88  jz      short loc_180045CA1
0x180045c8a  lea     rcx, [rsp+198h+var_138]
0x180045c8f  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180045c94  test    al, al
0x180045c96  jz      loc_180046246
0x180045c9c  mov     [rsp+198h+hExistingToken], r13
0x180045ca1  mov     [rsp+198h+var_118], rdi
0x180045ca9  cmp     [rsp+198h+var_110], 0
0x180045cb2  jz      loc_180045E48
0x180045cb8  lea     rcx, [rsp+198h+var_118]
0x180045cc0  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180045cc5  test    al, al
0x180045cc7  jz      loc_180046260
0x180045ccd  jmp     loc_180045E48
0x180045cd2  xor     bl, bl
0x180045cd4  mov     byte ptr [rsp+198h+var_C0], bl
0x180045cdb  mov     [rsp+198h+var_C0+8], rsi
0x180045ce3  xor     dil, dil
0x180045ce6  mov     [rsp+198h+var_138], rax
0x180045ceb  mov     [rsp+198h+hExistingToken], r13
0x180045cf0  call    cs:__imp_GetCurrentThread
0x180045cf6  lea     r9, [rsp+198h+hExistingToken]; TokenHandle
0x180045cfb  mov     edx, 20008h; DesiredAccess
0x180045d00  mov     r8d, 1; OpenAsSelf
0x180045d06  mov     rcx, rax; ThreadHandle
0x180045d09  call    cs:__imp_OpenThreadToken
0x180045d0f  test    eax, eax
0x180045d11  jz      short loc_180045D52
0x180045d13  mov     [rsp+198h+TokenInformation], r13d
0x180045d18  mov     [rsp+198h+var_140], 4
0x180045d20  lea     rax, [rsp+198h+var_140]
0x180045d25  mov     [rsp+198h+ReturnLength], rax; int
0x180045d2a  mov     r9d, 4; TokenInformationLength
0x180045d30  lea     r8, [rsp+198h+TokenInformation]; TokenInformation
0x180045d35  mov     edx, 8; TokenInformationClass
0x180045d3a  mov     rcx, [rsp+198h+hExistingToken]; TokenHandle
0x180045d3f  call    cs:__imp_GetTokenInformation
0x180045d45  test    eax, eax
0x180045d47  jz      short loc_180045D52
0x180045d49  cmp     [rsp+198h+TokenInformation], 2
0x180045d4e  setz    dil
0x180045d52  lea     r15, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180045d59  mov     [rsp+198h+var_138], r15
0x180045d5e  cmp     [rsp+198h+hExistingToken], 0
0x180045d64  jz      short loc_180045D7D
0x180045d66  lea     rcx, [rsp+198h+var_138]
0x180045d6b  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180045d70  test    al, al
0x180045d72  jz      loc_18004627A
0x180045d78  mov     [rsp+198h+hExistingToken], r13
0x180045d7d  test    dil, dil
0x180045d80  jnz     short loc_180045DB4
  ... truncated ...
```
