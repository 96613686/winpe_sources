# NgcKspServer::NgcUserIdKey::EventWriteSignHash(void * const,bool,ulong,long)

- ea: `0x180078a9c`
- end: `0x180079848`
- name: `?EventWriteSignHash@NgcUserIdKey@NgcKspServer@@AEAAXQEAX_NKJ@Z`
- size: `3500`
- prototype: `void(NgcKspServer::NgcUserIdKey *__hidden this, void *const, bool, unsigned int, int)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800762a0`
- `0x18007e170`

## callees

- `0x1800015f0`
- `0x18000782c`
- `0x180010990`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x18002d740`
- `0x18002dc0c`
- `0x18002eee8`
- `0x18002fb30`
- `0x1800320a0`
- `0x1800323d0`
- `0x180038764`
- `0x18004566c`
- `0x180045d60`
- `0x180047228`
- `0x18004d9c8`
- `0x1800517f0`
- `0x18005b484`
- `0x18005caa0`
- `0x18005cee0`
- `0x18005dd44`
- `0x180078a9c`
- `0x18007ea48`
- `0x18007ec00`
- `0x18008f3b4`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180078c9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180078c9d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180078cd7`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180078cd7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180078d18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180078d18`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180078ce9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180078ce9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078b0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078b0f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078bd3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078c0e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078c58`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078d02`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180079053`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078bd3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078c0e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078c58`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078d02`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180079053`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180078dfa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180078e3a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180078ee1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180078dfa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180078e3a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180078ee1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800790fd`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800790fd`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x1800791b5`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x1800791b5`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180078f01`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180078f01`
- `ntdll!NtQueryInformationProcess` at `0x180078dba`
- `ntdll!NtQueryInformationProcess` at `0x180078dba`

## string_xrefs

- `0x180079349`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x180078fc4`: `dllhost`
- `0x180079325`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall NgcKspServer::NgcUserIdKey::EventWriteSignHash(
        NgcKspServer::NgcUserIdKey *this,
        void *const a2,
        char a3,
        int a4,
        int a5)
{
  NgcKspServer::NgcUserIdKey *v6; // r14
  struct NgcKspServer::PinCacheManager *v7; // rax
  char v8; // r13
  const WCHAR *v9; // rdi
  unsigned __int16 v10; // r12
  const char *v11; // r9
  char *v12; // r15
  HANDLE v13; // rax
  char *v14; // rbx
  HANDLE v15; // rax
  unsigned int v16; // r8d
  const char *v17; // r9
  const WCHAR *v18; // rbx
  LPWSTR *v19; // rax
  LPWSTR v20; // rcx
  unsigned __int64 v21; // r13
  char *v22; // rdi
  __int64 last_trivial_2; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  HANDLE v27; // rax
  unsigned int v28; // r8d
  const char *v29; // r9
  _WORD *v30; // r13
  __int64 v31; // r14
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  unsigned __int16 v36; // r14
  wil *v37; // rcx
  enum NgcUserAccountType *v38; // r8
  int v39; // eax
  int v40; // r15d
  int NgcEnabledModifiers; // eax
  int v42; // ebx
  unsigned __int64 v43; // rbx
  __int16 v44; // ax
  _QWORD *v45; // rax
  NgcKspServer::NgcUserIdKey *v46; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  const char *v52; // r9
  int ReturnLength; // [rsp+20h] [rbp-F28h]
  unsigned __int16 v54; // [rsp+134h] [rbp-E14h] BYREF
  int pNumArgs; // [rsp+138h] [rbp-E10h] BYREF
  void *DuplicateTokenHandle; // [rsp+140h] [rbp-E08h] BYREF
  char v57; // [rsp+148h] [rbp-E00h]
  char v58; // [rsp+149h] [rbp-DFFh]
  char v59; // [rsp+14Ah] [rbp-DFEh]
  char v60; // [rsp+14Bh] [rbp-DFDh]
  char v61; // [rsp+14Ch] [rbp-DFCh]
  char v62; // [rsp+14Dh] [rbp-DFBh]
  char v63; // [rsp+14Eh] [rbp-DFAh]
  char v64; // [rsp+14Fh] [rbp-DF9h]
  char *v65; // [rsp+150h] [rbp-DF8h] BYREF
  DWORD dwSize; // [rsp+158h] [rbp-DF0h] BYREF
  int v67; // [rsp+15Ch] [rbp-DECh] BYREF
  int v68; // [rsp+160h] [rbp-DE8h]
  int v69; // [rsp+164h] [rbp-DE4h] BYREF
  int v70; // [rsp+168h] [rbp-DE0h]
  void *TokenHandle; // [rsp+170h] [rbp-DD8h] BYREF
  const WCHAR *v72; // [rsp+178h] [rbp-DD0h] BYREF
  NgcKspServer::NgcUserIdKey *v73; // [rsp+180h] [rbp-DC8h] BYREF
  unsigned __int64 v74; // [rsp+188h] [rbp-DC0h] BYREF
  DWORD v75; // [rsp+190h] [rbp-DB8h] BYREF
  LPVOID lpBuffer; // [rsp+198h] [rbp-DB0h] BYREF
  unsigned __int64 v77; // [rsp+1A0h] [rbp-DA8h] BYREF
  struct _FILETIME v78; // [rsp+1A8h] [rbp-DA0h]
  NgcKspServer::NgcUserIdKey *v79; // [rsp+1B0h] [rbp-D98h]
  __int64 v80; // [rsp+1B8h] [rbp-D90h]
  unsigned __int64 v81; // [rsp+1C0h] [rbp-D88h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1C8h] [rbp-D80h] BYREF
  HLOCAL hMem; // [rsp+1D0h] [rbp-D78h]
  _QWORD v84[2]; // [rsp+1D8h] [rbp-D70h] BYREF
  _QWORD *v85; // [rsp+1E8h] [rbp-D60h] BYREF
  _QWORD *v86; // [rsp+1F0h] [rbp-D58h] BYREF
  _QWORD *v87; // [rsp+1F8h] [rbp-D50h] BYREF
  unsigned __int64 v88; // [rsp+200h] [rbp-D48h] BYREF
  unsigned __int64 v89; // [rsp+208h] [rbp-D40h] BYREF
  __int64 v90; // [rsp+210h] [rbp-D38h] BYREF
  __int128 v91; // [rsp+218h] [rbp-D30h] BYREF
  __int64 v92; // [rsp+228h] [rbp-D20h]
  __int128 v93; // [rsp+230h] [rbp-D18h] BYREF
  __int64 v94; // [rsp+240h] [rbp-D08h]
  const WCHAR *v95; // [rsp+248h] [rbp-D00h]
  __int16 v96; // [rsp+250h] [rbp-CF8h]
  _BYTE v97[60]; // [rsp+260h] [rbp-CE8h] BYREF
  DWORD dwProcessId; // [rsp+29Ch] [rbp-CACh]
  _OWORD ProcessInformation[3]; // [rsp+2A0h] [rbp-CA8h] BYREF
  _BYTE v100[112]; // [rsp+2D0h] [rbp-C78h] BYREF
  unsigned __int16 v101; // [rsp+340h] [rbp-C08h]
  LPCVOID v102; // [rsp+348h] [rbp-C00h]
  _BYTE Buffer[32]; // [rsp+720h] [rbp-828h] BYREF
  LPCVOID lpBaseAddress; // [rsp+740h] [rbp-808h]
  __int128 v105; // [rsp+EF0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F48h] [rbp+0h]

  v6 = this;
  v79 = this;
  v73 = this;
  v67 = 0;
  pNumArgs = 0;
  v7 = NgcKspServer::PinCacheManager::Instance();
  v8 = 1;
  ++*((_QWORD *)v7 + 9);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v78 = SystemTimeAsFileTime;
  v81 = *((_QWORD *)v6 + 74);
  v77 = v81;
  v80 = *((_QWORD *)NgcKspServer::PinCacheManager::Instance() + 8);
  v70 = *((_DWORD *)NgcKspServer::PinCacheManager::Instance() + 20);
  v69 = v70;
  lpBuffer = 0;
  hMem = 0;
  v9 = 0;
  v72 = 0;
  v10 = 0;
  v54 = 0;
  v75 = 0;
  v68 = 0;
  try
  {
    NgcUtils::RpcCallerInfo::RpcCallerInfo((NgcUtils::RpcCallerInfo *)v97, a2);
    v12 = (char *)OpenProcess(0x410u, 0, dwProcessId);
    v65 = v12;
    if ( ((unsigned __int64)(v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator(
        (NgcUtils::RpcCallerImpersonator *)&DuplicateTokenHandle,
        a2);
      v13 = OpenProcess(0x410u, 0, dwProcessId);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v65,
        v13);
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&DuplicateTokenHandle);
      v12 = v65;
    }
    if ( ((unsigned __int64)(v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v14 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
      v74 = (unsigned __int64)v14;
      TokenHandle = 0;
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandle,
          0);
        if ( OpenProcessToken(v14, 0xEu, &TokenHandle) )
        {
          DuplicateTokenHandle = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &DuplicateTokenHandle,
            0);
          if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle)
            && ImpersonateLoggedOnUser(DuplicateTokenHandle) )
          {
            v15 = OpenProcess(0x410u, 0, dwProcessId);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &v65,
              v15);
            RevertToSelf();
            v12 = v65;
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
        }
      }
      if ( ((unsigned __int64)(v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v65,
          v14);
        v74 = 0;
        v12 = v65;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v74);
    }
    memset(ProcessInformation, 0, sizeof(ProcessInformation));
    if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_33;
    if ( NtQueryInformationProcess(v12, ProcessBasicInformation, ProcessInformation, 0x30u, 0) < 0 )
      goto LABEL_33;
    memset_0(Buffer, 0, 0x7D0u);
    if ( !ReadProcessMemory(v12, *((LPCVOID *)&ProcessInformation[0] + 1), Buffer, 0x7D0u, 0) )
      goto LABEL_33;
    memset_0(v100, 0, 0x450u);
    if ( !ReadProcessMemory(v12, lpBaseAddress, v100, 0x450u, 0) )
      goto LABEL_33;
    v10 = v101 >> 1;
    v54 = v101 >> 1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &DuplicateTokenHandle,
      0,
      v101 >> 1,
      v11);
    pNumArgs = 2;
    if ( !DuplicateTokenHandle )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v16, v17);
    v67 = 1;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpBuffer,
      &DuplicateTokenHandle);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&DuplicateTokenHandle);
    v18 = (const WCHAR *)lpBuffer;
    if ( ReadProcessMemory(v12, v102, lpBuffer, v101, 0)
      && (pNumArgs = 0, v19 = CommandLineToArgvW(v18, &pNumArgs), (hMem = v19) != 0) )
    {
      v20 = *v19;
      DuplicateTokenHandle = v20;
      v84[0] = v20;
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      v84[1] = v21;
      if ( !v21
        || (v22 = (char *)&v20[v21],
            last_trivial_2 = _std_find_last_trivial_2(v20, v22, 92),
            (char *)last_trivial_2 == v22) )
      {
        v24 = -1;
      }
      else
      {
        v24 = (last_trivial_2 - (__int64)DuplicateTokenHandle) >> 1;
      }
      TokenHandle = (void *)(v24 + 1);
      v74 = (unsigned __int16)(v24 + 1);
      v9 = &v18[v74];
      v72 = v9;
      v10 -= v74;
      v54 = v10;
      v25 = std::basic_string_view<unsigned short>::find(v84, L"svchost");
      v26 = std::basic_string_view<unsigned short>::find(v84, L"dllhost");
      if ( v25 == -1 && v26 == -1 && pNumArgs > 1 )
      {
        if ( v21 < (unsigned __int64)TokenHandle )
          std::basic_string_view<unsigned short>::_Xran();
        v9 = (const WCHAR *)((char *)DuplicateTokenHandle + 2 * (_QWORD)TokenHandle);
        v72 = v9;
        v10 = v21 - v74;
        v54 = v21 - v74;
      }
    }
    else
    {
LABEL_33:
      if ( ((unsigned __int64)(v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v27 = OpenProcess(0x1000u, 0, dwProcessId);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v65,
          v27);
        v12 = v65;
      }
      dwSize = 1024;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &DuplicateTokenHandle,
        0,
        0x400u,
        v11);
      pNumArgs = v67 | 8;
      if ( !DuplicateTokenHandle )
        wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v28, v29);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &lpBuffer,
        &DuplicateTokenHandle);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&DuplicateTokenHandle);
      if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v9 = 0;
        v72 = 0;
        goto LABEL_49;
      }
      v30 = lpBuffer;
      if ( !QueryFullProcessImageNameW(v12, 0, (LPWSTR)lpBuffer, &dwSize) )
      {
LABEL_47:
        GetProcessInformation(v12, 7, &v75);
        v8 = 1;
LABEL_49:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v65);
        NgcUtils::RpcCallerInfo::~RpcCallerInfo((NgcUtils::RpcCallerInfo *)v97);
        goto LABEL_84;
      }
      ULongToUShort(dwSize, &v54);
      LOWORD(v31) = -1;
      v32 = -1;
      do
        ++v32;
      while ( v30[v32] );
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 == -1 )
          v33 = -1;
        v34 = (__int64)&v30[v33 + 1];
        v35 = _std_find_last_trivial_2(v30, v34, 92);
        if ( v35 != v34 )
          v31 = (v35 - (__int64)v30) >> 1;
      }
      v36 = v31 + 1;
      v9 = &v30[v36];
      v72 = v9;
      v10 = v54 - v36;
      v54 -= v36;
    }
    v6 = v79;
    goto LABEL_47;
  }
  catch ( ... )
  {
    v70 = wil::ResultFromCaughtException(v37);
    if ( v70 != 1765 )
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x148D,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        v52);
    v8 = 1;
    v10 = v54;
    v68 = v70;
    v9 = v72;
    v6 = v73;
    v81 = v77;
    v70 = v69;
  }
LABEL_84:
  v69 = 0;
  NgcUtils::GetUserAccountType(*((NgcUtils **)v6 + 4), &v69, v38);
  v93 = 0;
  v94 = 0;
  v39 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int128 *))(**((_QWORD **)v6 + 44) + 248LL))(
          *((_QWORD *)v6 + 44),
          (__int64)v6 + 56,
          10,
          &v93);
  LODWORD(v73) = 0;
  if ( v39 >= 0 )
    LODWORD(v73) = *(_DWORD *)v93;
  v91 = 0;
  v92 = 0;
  v40 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64, __int128 *))(**((_QWORD **)v6 + 44) + 248LL))(
         *((_QWORD *)v6 + 44),
         (__int64)v6 + 56,
         11,
         &v91) >= 0 )
    v40 = *(_DWORD *)v91;
  pNumArgs = 0;
  NgcEnabledModifiers = NgcUtils::GetNgcEnabledModifiers(&pNumArgs);
  v42 = NgcEnabledModifiers;
  if ( NgcEnabledModifiers >= 0 )
  {
    v42 = 0;
  }
  else
  {
    v8 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
      (const char *)(unsigned int)NgcEnabledModifiers,
      ReturnLength);
  }
  if ( v42 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14B5,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
      (const char *)(unsigned int)v42,
      ReturnLength);
  if ( (unsigned int)dword_180122038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180122038, 0x800000000000LL) )
  {
    v43 = (*(_QWORD *)&v78 - v81) / 0x2710;
    v77 = (*(_QWORD *)&v78 - v80) / 0x2710uLL;
    v57 = v8;
    LODWORD(v80) = 0;
    LODWORD(v81) = 0;
    v58 = 0;
    v78.dwLowDateTime = v75;
    if ( v10 > 0x7FFFuLL )
      v44 = -2;
    else
      v44 = 2 * v10;
    v95 = v9;
    v96 = v44;
    v59 = *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 91);
    v60 = *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 90);
    v61 = *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 89);
    v62 = *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 88);
    LODWORD(v79) = *((_DWORD *)NgcKspServer::PinCacheManager::Instance() + 21);
    LODWORD(v74) = *((_DWORD *)v6 + 129);
    v63 = *((_BYTE *)v6 + 512);
    v64 = *((_BYTE *)v6 + 264);
    LOBYTE(v54) = a3;
    LODWORD(TokenHandle) = a5;
    LODWORD(DuplicateTokenHandle) = a4;
    v45 = (_QWORD *)((char *)v6 + 536);
    if ( *((_QWORD *)v6 + 70) > 7u )
      v45 = (_QWORD *)*v45;
    v85 = v45;
    LODWORD(v72) = v40;
    LODWORD(v65) = (_DWORD)v73;
    v46 = (NgcKspServer::NgcUserIdKey *)((char *)v6 + 136);
    if ( *((_QWORD *)v6 + 20) > 7u )
      v46 = *(NgcKspServer::NgcUserIdKey **)v46;
    v73 = v46;
    v47 = (_QWORD *)((char *)v6 + 104);
    if ( *((_QWORD *)v6 + 16) > 7u )
      v47 = (_QWORD *)*v47;
    v86 = v47;
    v48 = (_QWORD *)((char *)v6 + 72);
    if ( *((_QWORD *)v6 + 12) > 7u )
      v48 = (_QWORD *)*v48;
    v87 = v48;
    LOWORD(dwSize) = NgcKspServer::NgcUserIdKey::GetKeyType(v6);
    LOWORD(v67) = v69;
    v88 = v43;
    v89 = v77;
    v90 = *((_QWORD *)NgcKspServer::PinCacheManager::Instance() + 9);
    LOWORD(pNumArgs) = v70;
    v105 = *((_OWORD *)NgcKspServer::PinCacheManager::Instance() + 3);
    v77 = (unsigned __int64)&v105;
    v84[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v49,
      (__int64)word_1801022C2,
      v50,
      v51,
      (__int64)v84,
      (__int64)&v77,
      (__int64)&pNumArgs,
      (__int64)&v90,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v67,
      (__int64)&dwSize,
      &v87,
      &v86,
      &v73,
      (__int64)&v65,
      (__int64)&v72,
      &v85);
  }
  std::vector<unsigned char>::_Tidy(&v91);
  std::vector<unsigned char>::_Tidy(&v93);
  if ( hMem )
    LocalFree(hMem);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpBuffer);
}

```

## disassembly

```asm
0x180078a9c  mov     [rsp+arg_18], r9d
0x180078aa1  mov     [rsp+arg_10], r8b
0x180078aa6  push    rbx
0x180078aa7  push    rsi
0x180078aa8  push    rdi
0x180078aa9  push    r12
0x180078aab  push    r13
0x180078aad  push    r14
0x180078aaf  push    r15
0x180078ab1  sub     rsp, 0F10h
0x180078ab8  mov     rax, cs:__security_cookie
0x180078abf  xor     rax, rsp
0x180078ac2  mov     [rsp+0F48h+var_48], rax
0x180078aca  mov     rbx, rdx
0x180078acd  mov     r14, rcx
0x180078ad0  mov     [rsp+0F48h+var_D98], rcx
0x180078ad8  mov     [rsp+0F48h+var_DC8], rcx
0x180078ae0  xor     esi, esi
0x180078ae2  mov     eax, esi
0x180078ae4  mov     [rsp+0F48h+var_DEC], eax
0x180078aeb  mov     [rsp+0F48h+pNumArgs], eax
0x180078af2  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180078af7  lea     r13d, [rsi+1]
0x180078afb  add     [rax+48h], r13
0x180078aff  mov     qword ptr [rsp+0F48h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180078b07  lea     rcx, [rsp+0F48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180078b0f  call    cs:__imp_GetSystemTimeAsFileTime
0x180078b15  mov     eax, [rsp+0F48h+SystemTimeAsFileTime.dwHighDateTime]
0x180078b1c  mov     dword ptr [rsp+0F48h+var_DA0+4], eax
0x180078b23  mov     eax, [rsp+0F48h+SystemTimeAsFileTime.dwLowDateTime]
0x180078b2a  mov     dword ptr [rsp+0F48h+var_DA0], eax
0x180078b31  mov     rax, [r14+250h]
0x180078b38  mov     [rsp+0F48h+var_D88], rax
0x180078b40  mov     [rsp+0F48h+var_DA8], rax
0x180078b48  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180078b4d  mov     ecx, [rax+44h]
0x180078b50  mov     dword ptr [rsp+0F48h+var_D90+4], ecx
0x180078b57  mov     eax, [rax+40h]
0x180078b5a  mov     dword ptr [rsp+0F48h+var_D90], eax
0x180078b61  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180078b66  mov     eax, [rax+50h]
0x180078b69  mov     [rsp+0F48h+var_DE0], eax
0x180078b70  mov     [rsp+0F48h+var_DE4], eax
0x180078b77  mov     [rsp+0F48h+lpBuffer], rsi
0x180078b7f  mov     [rsp+0F48h+hMem], rsi
0x180078b87  mov     edi, esi
0x180078b89  mov     [rsp+0F48h+var_DD0], rsi
0x180078b91  movzx   r12d, si
0x180078b95  mov     [rsp+0F48h+var_E14], si
0x180078b9d  mov     [rsp+0F48h+var_E18], r13b
0x180078ba5  mov     [rsp+0F48h+var_DB8], esi
0x180078bac  mov     [rsp+0F48h+var_DE8], esi
0x180078bb3  mov     rdx, rbx; void *
0x180078bb6  lea     rcx, [rsp+0F48h+var_CE8]; this
0x180078bbe  call    ??0RpcCallerInfo@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerInfo::RpcCallerInfo(void * const)
0x180078bc3  nop
0x180078bc4  mov     r8d, [rsp+0F48h+dwProcessId]; dwProcessId
0x180078bcc  xor     edx, edx; bInheritHandle
0x180078bce  mov     ecx, 410h; dwDesiredAccess
0x180078bd3  call    cs:__imp_OpenProcess
0x180078bd9  mov     r15, rax
0x180078bdc  mov     [rsp+0F48h+var_DF8], rax
0x180078be4  inc     rax
0x180078be7  test    rax, 0FFFFFFFFFFFFFFFEh
0x180078bed  jnz     short loc_180078C39
0x180078bef  mov     rdx, rbx; void *
0x180078bf2  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]; this
0x180078bfa  call    ??0RpcCallerImpersonator@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator(void * const)
0x180078bff  mov     r8d, [rsp+0F48h+dwProcessId]; dwProcessId
0x180078c07  xor     edx, edx; bInheritHandle
0x180078c09  mov     ecx, 410h; dwDesiredAccess
0x180078c0e  call    cs:__imp_OpenProcess
0x180078c14  mov     rdx, rax
0x180078c17  lea     rcx, [rsp+0F48h+var_DF8]
0x180078c1f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180078c24  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]; this
0x180078c2c  call    ??1RpcCallerImpersonator@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator(void)
0x180078c31  mov     r15, [rsp+0F48h+var_DF8]
0x180078c39  lea     rax, [r15+1]
0x180078c3d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180078c43  jnz     loc_180078D79
0x180078c49  mov     r8d, [rsp+0F48h+dwProcessId]; dwProcessId
0x180078c51  xor     edx, edx; bInheritHandle
0x180078c53  mov     ecx, 1000h; dwDesiredAccess
0x180078c58  call    cs:__imp_OpenProcess
0x180078c5e  mov     rbx, rax
0x180078c61  mov     [rsp+0F48h+var_DC0], rax
0x180078c69  mov     [rsp+0F48h+TokenHandle], rsi
0x180078c71  dec     rax
0x180078c74  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180078c78  ja      loc_180078D33
0x180078c7e  xor     edx, edx
0x180078c80  lea     rcx, [rsp+0F48h+TokenHandle]
0x180078c88  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180078c8d  lea     r8, [rsp+0F48h+TokenHandle]; TokenHandle
0x180078c95  mov     edx, 0Eh; DesiredAccess
0x180078c9a  mov     rcx, rbx; ProcessHandle
0x180078c9d  call    cs:__imp_OpenProcessToken
0x180078ca3  test    eax, eax
0x180078ca5  jz      loc_180078D33
0x180078cab  mov     [rsp+0F48h+DuplicateTokenHandle], rsi
0x180078cb3  xor     edx, edx
0x180078cb5  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]
0x180078cbd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180078cc2  lea     r8, [rsp+0F48h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180078cca  mov     edx, 2; ImpersonationLevel
0x180078ccf  mov     rcx, [rsp+0F48h+TokenHandle]; ExistingTokenHandle
0x180078cd7  call    cs:__imp_DuplicateToken
0x180078cdd  test    eax, eax
0x180078cdf  jz      short loc_180078D26
0x180078ce1  mov     rcx, [rsp+0F48h+DuplicateTokenHandle]; hToken
0x180078ce9  call    cs:__imp_ImpersonateLoggedOnUser
0x180078cef  test    eax, eax
0x180078cf1  jz      short loc_180078D26
0x180078cf3  mov     r8d, [rsp+0F48h+dwProcessId]; dwProcessId
0x180078cfb  xor     edx, edx; bInheritHandle
0x180078cfd  mov     ecx, 410h; dwDesiredAccess
0x180078d02  call    cs:__imp_OpenProcess
0x180078d08  mov     rdx, rax
0x180078d0b  lea     rcx, [rsp+0F48h+var_DF8]
0x180078d13  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180078d18  call    cs:__imp_RevertToSelf
0x180078d1e  mov     r15, [rsp+0F48h+var_DF8]
0x180078d26  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]
0x180078d2e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180078d33  lea     rax, [r15+1]
0x180078d37  test    rax, 0FFFFFFFFFFFFFFFEh
0x180078d3d  jnz     short loc_180078D5F
0x180078d3f  mov     rdx, rbx
0x180078d42  lea     rcx, [rsp+0F48h+var_DF8]
0x180078d4a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180078d4f  mov     [rsp+0F48h+var_DC0], rsi
0x180078d57  mov     r15, [rsp+0F48h+var_DF8]
0x180078d5f  lea     rcx, [rsp+0F48h+TokenHandle]
0x180078d67  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180078d6c  lea     rcx, [rsp+0F48h+var_DC0]
0x180078d74  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180078d79  xorps   xmm0, xmm0
0x180078d7c  movups  [rsp+0F48h+ProcessInformation], xmm0
0x180078d84  movups  [rsp+0F48h+var_C98], xmm0
0x180078d8c  movups  [rsp+0F48h+var_C88], xmm0
0x180078d94  lea     rax, [r15-1]
0x180078d98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180078d9c  ja      loc_180079038
0x180078da2  mov     [rsp+0F48h+ReturnLength], rsi; ReturnLength
0x180078da7  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180078dad  lea     r8, [rsp+0F48h+ProcessInformation]; ProcessInformation
0x180078db5  xor     edx, edx; ProcessInformationClass
0x180078db7  mov     rcx, r15; ProcessHandle
0x180078dba  call    cs:__imp_NtQueryInformationProcess
0x180078dc0  test    eax, eax
0x180078dc2  js      loc_180079038
0x180078dc8  mov     ebx, 7D0h
0x180078dcd  mov     r8d, ebx; Size
0x180078dd0  xor     edx, edx; Val
0x180078dd2  lea     rcx, [rsp+0F48h+Buffer]; void *
0x180078dda  call    memset_0
0x180078ddf  mov     [rsp+0F48h+ReturnLength], rsi; lpNumberOfBytesRead
0x180078de4  mov     r9d, ebx; nSize
0x180078de7  lea     r8, [rsp+0F48h+Buffer]; lpBuffer
0x180078def  mov     rdx, qword ptr [rsp+0F48h+ProcessInformation+8]; lpBaseAddress
0x180078df7  mov     rcx, r15; hProcess
0x180078dfa  call    cs:__imp_ReadProcessMemory
0x180078e00  test    eax, eax
0x180078e02  jz      loc_180079038
0x180078e08  mov     ebx, 450h
0x180078e0d  mov     r8d, ebx; Size
0x180078e10  xor     edx, edx; Val
0x180078e12  lea     rcx, [rsp+0F48h+var_C78]; void *
0x180078e1a  call    memset_0
0x180078e1f  mov     [rsp+0F48h+ReturnLength], rsi; lpNumberOfBytesRead
0x180078e24  mov     r9d, ebx; nSize
0x180078e27  lea     r8, [rsp+0F48h+var_C78]; lpBuffer
0x180078e2f  mov     rdx, [rsp+0F48h+lpBaseAddress]; lpBaseAddress
0x180078e37  mov     rcx, r15; hProcess
0x180078e3a  call    cs:__imp_ReadProcessMemory
0x180078e40  test    eax, eax
0x180078e42  jz      loc_180079038
0x180078e48  movzx   eax, [rsp+0F48h+var_C08]
0x180078e50  shr     ax, 1
0x180078e53  movzx   r12d, ax
0x180078e57  mov     [rsp+0F48h+var_E14], r12w
0x180078e60  mov     r8d, r12d
0x180078e63  xor     edx, edx
0x180078e65  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]
0x180078e6d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180078e72  mov     [rsp+0F48h+pNumArgs], 2
0x180078e7d  mov     rcx, [rsp+0F48h]; this
0x180078e85  cmp     [rsp+0F48h+DuplicateTokenHandle], rsi
0x180078e8d  jz      loc_18007982B
0x180078e93  mov     [rsp+0F48h+var_DEC], r13d
0x180078e9b  lea     rdx, [rsp+0F48h+DuplicateTokenHandle]
0x180078ea3  lea     rcx, [rsp+0F48h+lpBuffer]
0x180078eab  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180078eb0  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]; void *
0x180078eb8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180078ebd  movzx   r9d, [rsp+0F48h+var_C08]; nSize
0x180078ec6  mov     [rsp+0F48h+ReturnLength], rsi; lpNumberOfBytesRead
0x180078ecb  mov     rbx, [rsp+0F48h+lpBuffer]
0x180078ed3  mov     r8, rbx; lpBuffer
0x180078ed6  mov     rdx, [rsp+0F48h+var_C00]; lpBaseAddress
0x180078ede  mov     rcx, r15; hProcess
0x180078ee1  call    cs:__imp_ReadProcessMemory
0x180078ee7  test    eax, eax
0x180078ee9  jz      loc_180079038
0x180078eef  mov     [rsp+0F48h+pNumArgs], esi
0x180078ef6  lea     rdx, [rsp+0F48h+pNumArgs]; pNumArgs
0x180078efe  mov     rcx, rbx; lpCmdLine
0x180078f01  call    cs:__imp_CommandLineToArgvW
0x180078f07  mov     [rsp+0F48h+hMem], rax
0x180078f0f  test    rax, rax
0x180078f12  jz      loc_180079038
0x180078f18  mov     rcx, [rax]
0x180078f1b  mov     [rsp+0F48h+DuplicateTokenHandle], rcx
0x180078f23  mov     [rsp+0F48h+var_D70], rcx
0x180078f2b  or      r14, 0FFFFFFFFFFFFFFFFh
0x180078f2f  mov     r13, r14
0x180078f32  inc     r13
0x180078f35  cmp     [rcx+r13*2], si
0x180078f3a  jnz     short loc_180078F32
0x180078f3c  mov     [rsp+0F48h+var_D68], r13
0x180078f44  test    r13, r13
0x180078f47  jz      short loc_180078F7B
0x180078f49  lea     rax, [r13-1]
0x180078f4d  cmp     rax, r14
0x180078f50  cmovnb  rax, r14
0x180078f54  inc     rax
0x180078f57  lea     rdi, [rcx+rax*2]
0x180078f5b  mov     r8d, 5Ch ; '\'
0x180078f61  mov     rdx, rdi
0x180078f64  call    __std_find_last_trivial_2
0x180078f69  cmp     rax, rdi
0x180078f6c  jz      short loc_180078F7B
0x180078f6e  sub     rax, [rsp+0F48h+DuplicateTokenHandle]
0x180078f76  sar     rax, 1
0x180078f79  jmp     short loc_180078F7E
0x180078f7b  mov     rax, r14
0x180078f7e  inc     rax
0x180078f81  mov     [rsp+0F48h+TokenHandle], rax
0x180078f89  movzx   eax, ax
0x180078f8c  mov     [rsp+0F48h+var_DC0], rax
0x180078f94  lea     rdi, [rbx+rax*2]
0x180078f98  mov     [rsp+0F48h+var_DD0], rdi
0x180078fa0  sub     r12w, ax
0x180078fa4  mov     [rsp+0F48h+var_E14], r12w
0x180078fad  lea     rdx, aSvchost; "svchost"
0x180078fb4  lea     rcx, [rsp+0F48h+var_D70]
0x180078fbc  call    ?find@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA_KQEBG_K@Z; std::basic_string_view<ushort>::find(ushort const * const,unsigned __int64)
0x180078fc1  mov     rbx, rax
0x180078fc4  lea     rdx, aDllhost; "dllhost"
0x180078fcb  lea     rcx, [rsp+0F48h+var_D70]
0x180078fd3  call    ?find@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA_KQEBG_K@Z; std::basic_string_view<ushort>::find(ushort const * const,unsigned __int64)
0x180078fd8  cmp     rbx, r14
0x180078fdb  jnz     short loc_18007902B
0x180078fdd  cmp     rax, r14
0x180078fe0  jnz     short loc_18007902B
0x180078fe2  mov     eax, 1
0x180078fe7  cmp     [rsp+0F48h+pNumArgs], eax
0x180078fee  jle     short loc_18007902B
0x180078ff0  mov     rcx, [rsp+0F48h+TokenHandle]
0x180078ff8  cmp     r13, rcx
0x180078ffb  jb      loc_180079836
0x180079001  mov     rax, [rsp+0F48h+DuplicateTokenHandle]
0x180079009  lea     rdi, [rax+rcx*2]
0x18007900d  mov     [rsp+0F48h+var_DD0], rdi
0x180079015  sub     r13w, word ptr [rsp+0F48h+var_DC0]
0x18007901e  movzx   r12d, r13w
0x180079022  mov     [rsp+0F48h+var_E14], r13w
0x18007902b  mov     [rsp+0F48h+var_E18], sil
0x180079033  jmp     loc_180079198
0x180079038  lea     rax, [r15+1]
0x18007903c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180079042  jnz     short loc_180079071
0x180079044  mov     r8d, [rsp+0F48h+dwProcessId]; dwProcessId
0x18007904c  xor     edx, edx; bInheritHandle
0x18007904e  mov     ecx, 1000h; dwDesiredAccess
0x180079053  call    cs:__imp_OpenProcess
0x180079059  mov     rdx, rax
0x18007905c  lea     rcx, [rsp+0F48h+var_DF8]
0x180079064  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180079069  mov     r15, [rsp+0F48h+var_DF8]
0x180079071  mov     r8d, 400h
0x180079077  mov     [rsp+0F48h+dwSize], r8d
0x18007907f  xor     edx, edx
0x180079081  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]
0x180079089  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18007908e  mov     eax, [rsp+0F48h+var_DEC]
0x180079095  or      eax, 8
0x180079098  mov     [rsp+0F48h+pNumArgs], eax
0x18007909f  mov     rcx, [rsp+0F48h]; this
0x1800790a7  cmp     [rsp+0F48h+DuplicateTokenHandle], rsi
0x1800790af  jz      loc_18007983C
0x1800790b5  lea     rdx, [rsp+0F48h+DuplicateTokenHandle]
0x1800790bd  lea     rcx, [rsp+0F48h+lpBuffer]
0x1800790c5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800790ca  lea     rcx, [rsp+0F48h+DuplicateTokenHandle]; void *
0x1800790d2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800790d7  lea     rax, [r15-1]
0x1800790db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800790df  ja      loc_1800791C3
  ... truncated ...
```
