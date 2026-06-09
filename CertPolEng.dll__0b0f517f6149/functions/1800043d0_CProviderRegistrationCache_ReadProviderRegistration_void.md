# CProviderRegistrationCache::ReadProviderRegistration(void)

- ea: `0x1800043d0`
- end: `0x180004d98`
- name: `?ReadProviderRegistration@CProviderRegistrationCache@@AEAAKXZ`
- size: `2504`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003fb0`

## callees

- `0x180003e60`
- `0x1800043d0`
- `0x180004da0`
- `0x1800064e0`
- `0x180007d20`
- `0x180007da0`
- `0x180009310`
- `0x18000c344`
- `0x18000c65c`
- `0x18000ddf0`
- `0x18000e8d6`
- `0x180013de8`
- `0x180014510`
- `0x180016ec0`
- `0x180016f18`
- `0x180017004`
- `0x1800173cc`
- `0x18001a342`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004565`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004794`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004565`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000457a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000473d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000457a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000473d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800044d2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000472d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800044d2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000472d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000475f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000475f`
- `CRYPT32!CertOpenStore` at `0x18000451a`
- `CRYPT32!CertOpenStore` at `0x18000451a`
- `CRYPT32!CertControlStore` at `0x1800045b2`
- `CRYPT32!CertControlStore` at `0x1800045b2`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180004820`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180004820`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000465e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800046df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000465e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800046df`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004897`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004897`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004952`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004952`
- `ntdll!NtClose` at `0x18000474c`
- `ntdll!NtClose` at `0x18000474c`
- `ntdll!NtOpenThreadToken` at `0x1800044a5`
- `ntdll!NtOpenThreadToken` at `0x1800044a5`
- `ntdll!RtlReleaseResource` at `0x180004d6d`
- `ntdll!RtlReleaseResource` at `0x180004d6d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000443e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000443e`
- `ntdll!RtlGUIDFromString` at `0x180004a50`
- `ntdll!RtlGUIDFromString` at `0x180004a50`
- `ntdll!RtlNtStatusToDosError` at `0x1800044b8`
- `ntdll!RtlNtStatusToDosError` at `0x180004a58`
- `ntdll!RtlNtStatusToDosError` at `0x1800044b8`
- `ntdll!RtlNtStatusToDosError` at `0x180004a58`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800046b2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800046b2`

## string_xrefs

- `0x180004448`: `CProviderRegistrationCache::ReadProviderRegistration`
- `0x180004712`: `CProviderRegistrationCache::ReadProviderRegistration`
- `0x180004590`: `CreateEvent`
- `0x1800047c3`: `CreateEvent`
- `0x18000483e`: `CreateEvent`
- `0x180004ce9`: `CreateCertChainEngine`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::ReadProviderRegistration(CProviderRegistrationCache *this)
{
  WCHAR *v2; // rdi
  int v3; // r12d
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  HCERTSTORE v7; // rax
  DWORD v8; // eax
  __int64 v9; // rcx
  HANDLE EventW; // rax
  DWORD v11; // eax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  int IsDeviceJoined; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  HKEY *v18; // r14
  unsigned int v19; // eax
  __int64 v20; // rcx
  HKEY *v21; // rbx
  const WCHAR *v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // rcx
  void *v25; // rcx
  DWORD v26; // ebx
  __int64 v27; // r9
  HANDLE v28; // rax
  DWORD v29; // eax
  int v30; // ecx
  CProviderEntry *v31; // rbx
  unsigned int v32; // eax
  __int64 v33; // rcx
  DWORD v34; // ecx
  unsigned __int64 v35; // rax
  DWORD v36; // esi
  unsigned int v37; // eax
  __int64 v38; // rcx
  WCHAR v39; // dx
  __int64 v40; // r8
  __int64 v41; // rax
  ULONG v42; // eax
  WCHAR *v43; // rcx
  __int64 v44; // rax
  NTSTATUS v45; // eax
  CProviderEntry *v46; // rax
  CProviderEntry *v47; // rax
  unsigned int v48; // esi
  unsigned int v49; // r14d
  unsigned int i; // ebx
  __int64 v51; // rax
  unsigned __int64 v52; // rax
  HLOCAL v53; // rax
  unsigned int j; // r8d
  unsigned int CertChainEngine; // eax
  __int64 v56; // rcx
  DWORD LastError; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen; // [rsp+7Ch] [rbp-84h] BYREF
  CProviderEntry *v64; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING GuidString; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME v67; // [rsp+A0h] [rbp-60h] BYREF
  char *v68; // [rsp+A8h] [rbp-58h]
  char v69; // [rsp+B0h] [rbp-50h]
  const char *v70; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v71; // [rsp+C0h] [rbp-40h]
  DWORD *v72; // [rsp+D0h] [rbp-30h]
  GUID Guid; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v74; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v75; // [rsp+100h] [rbp+0h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  _OWORD v77[2]; // [rsp+120h] [rbp+20h]
  _BYTE v78[528]; // [rsp+140h] [rbp+40h] BYREF

  LastError = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueLen = 0;
  ftLastWriteTime = 0;
  v2 = 0;
  v3 = 0;
  TokenHandle = 0;
  memset_0(v78, 0, 0x208u);
  v68 = (char *)this + 16;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 16), 1u);
  v69 = 1;
  v70 = "CProviderRegistrationCache::ReadProviderRegistration";
  v71 = 0;
  v72 = &LastError;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v5, Func_Start, "CProviderRegistrationCache::ReadProviderRegistration");
  if ( !*((_DWORD *)this + 2) )
  {
    LastError = 5023;
    goto LABEL_36;
  }
  v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( v6 >= 0 )
  {
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      goto LABEL_36;
    }
    v3 = 1;
  }
  else
  {
    if ( v6 != -1073741700 )
    {
      LastError = RtlNtStatusToDosError(v6);
      goto LABEL_36;
    }
    TokenHandle = 0;
  }
  CProviderRegistrationCache::ShutDown(this, 0);
  v7 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x2C000u, L"My");
  *((_QWORD *)this + 41) = v7;
  if ( !v7 )
  {
    v8 = GetLastError();
    LastError = v8;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0zq_EtwEventWriteTransfer(v9, CertOpenStoreFailed, L"My", v8);
    goto LABEL_36;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 42) = EventW;
  if ( !EventW )
  {
    v11 = GetLastError();
    LastError = v11;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_36;
LABEL_18:
    McTemplateU0sq_EtwEventWriteTransfer(v12, v4, "CreateEvent", v11);
    goto LABEL_36;
  }
  if ( !CertControlStore(*((HCERTSTORE *)this + 41), 0, 2u, (char *)this + 336) )
  {
    v13 = GetLastError();
    LastError = v13;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v14, v4, "CertControlStore", v13);
    goto LABEL_36;
  }
  IsDeviceJoined = DsrIsDeviceJoinedEx((char *)this + 344);
  if ( IsDeviceJoined < 0 )
  {
    LastError = 1353;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    {
      McTemplateU0sq_EtwEventWriteTransfer(v16, v4, "DsrIsDeviceJoined", (unsigned int)IsDeviceJoined);
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v17, v4, "DsrIsDeviceJoined(mapped)", LastError);
    }
    goto LABEL_36;
  }
  v18 = (HKEY *)((char *)this + 112);
  v19 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\IdentityStore\\Providers",
          0,
          0x20019u,
          (PHKEY)this + 14);
  LastError = v19;
  if ( v19 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v20, FailedToOpenProvRoot, v19);
    *v18 = 0;
    goto LABEL_36;
  }
  LastError = GetPersistedRegistryLocationW(
                L"IDStoreLoadParameters",
                L"Software\\Microsoft\\IdentityStore\\LoadParameters",
                v78,
                520,
                0);
  v21 = (HKEY *)((char *)this + 120);
  v22 = (const WCHAR *)v78;
  if ( LastError )
    v22 = L"Software\\Microsoft\\IdentityStore\\LoadParameters";
  v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v22, 0, 0x20019u, (PHKEY)this + 15);
  LastError = v23;
  if ( v23 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v24, FailedToOpenProvRoot, v23);
    *v21 = 0;
    goto LABEL_36;
  }
  v28 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 16) = v28;
  if ( !v28 )
  {
    v29 = GetLastError();
    LastError = v29;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    {
      cchName = v29;
      *(_QWORD *)&v75 = "CreateEvent";
      *((_QWORD *)&v75 + 1) = 12;
      *(_QWORD *)&v76 = &cchName;
      *((_QWORD *)&v76 + 1) = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        v30,
        (unsigned int)FunctionName_Returned_Error,
        (unsigned int)"CreateEvent",
        3,
        (__int64)&v74);
    }
    goto LABEL_36;
  }
  v11 = RegNotifyChangeKeyValue(*v21, 1, 0x10000005u, v28, 1);
  LastError = v11;
  if ( v11 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_36;
    goto LABEL_18;
  }
  v31 = 0;
  v32 = RegQueryInfoKeyW(*v18, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, &cbMaxValueLen, 0, &ftLastWriteTime);
  LastError = v32;
  if ( v32 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v33, FailedToQueryProvRoot, v32);
    goto LABEL_36;
  }
  v34 = cbMaxSubKeyLen + 1;
  if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
  {
    cbMaxSubKeyLen = -1;
    goto LABEL_121;
  }
  ++cbMaxSubKeyLen;
  v35 = 2LL * v34;
  if ( v35 > 0xFFFFFFFF )
    goto LABEL_121;
  v2 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v35);
  if ( !v2 )
  {
    LastError = 14;
    goto LABEL_36;
  }
  v36 = 0;
  while ( v36 < cSubKeys )
  {
    cchName = cbMaxSubKeyLen;
    v67 = 0;
    Guid = 0;
    v37 = RegEnumKeyExW(*v18, v36, v2, &cchName, 0, 0, 0, &v67);
    LastError = v37;
    if ( v37 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 4) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(v38, FailedToQueryProvRootSubKey, v36, v37);
      goto LABEL_80;
    }
    v39 = *v2;
    v40 = 36;
    if ( *v2 == 123 )
      v40 = 38;
    v41 = -1;
    do
      ++v41;
    while ( v2[v41] );
    if ( v41 == v40 )
    {
      v43 = v2;
      v74 = *(_OWORD *)L"{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}";
      v75 = *(_OWORD *)L"X-XXXX-XXXX-XXXX-XXXXXXXXXXXX}";
      v76 = *(_OWORD *)L"XXX-XXXX-XXXXXXXXXXXX}";
      v77[0] = *(_OWORD *)L"-XXXXXXXXXXXX}";
      *(_OWORD *)((char *)v77 + 14) = *(_OWORD *)L"XXXXXX}";
      *(_DWORD *)(&GuidString.MaximumLength + 1) = 0;
      GuidString.MaximumLength = 78;
      if ( v39 != 123 )
      {
        memcpy_0((char *)&v74 + 2, v2, 2 * v40);
        v43 = (WCHAR *)&v74;
      }
      v44 = -1;
      do
        ++v44;
      while ( v43[v44] );
      GuidString.Length = 2 * v44;
      GuidString.Buffer = v43;
      v45 = RtlGUIDFromString(&GuidString, &Guid);
      v42 = RtlNtStatusToDosError(v45);
      LastError = v42;
      if ( v42 )
        goto LABEL_78;
      v46 = (CProviderEntry *)operator new(0x868u);
      v64 = v46;
      if ( v46 )
        v31 = CProviderEntry::CProviderEntry(v46);
      v64 = v31;
      if ( !v31 )
      {
        LastError = 14;
        goto LABEL_36;
      }
      if ( CProviderEntry::ReadInfoFromRegistry(v31, *v18, *((HKEY *)this + 15), v2, &Guid) >= 0 )
      {
        if ( !(unsigned int)CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::Add(
                              (char *)this + 144,
                              v31) )
        {
          LastError = 14;
LABEL_91:
          (**(void (__fastcall ***)(CProviderEntry *, __int64))v31)(v31, 1);
          goto LABEL_36;
        }
        v31 = 0;
      }
      if ( v31 )
        (**(void (__fastcall ***)(CProviderEntry *, __int64))v31)(v31, 1);
      v31 = 0;
      ++v36;
    }
    else
    {
      v42 = 87;
      LastError = 87;
LABEL_78:
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0zq_EtwEventWriteTransfer(v38, InvalidProvGuid, v2, v42);
LABEL_80:
      LastError = 0;
      ++v36;
    }
  }
  v47 = (CProviderEntry *)operator new(0x868u);
  v64 = v47;
  if ( v47 )
    v31 = CProviderEntry::CProviderEntry(v47);
  v64 = v31;
  if ( !v31 )
  {
    LastError = 14;
    goto LABEL_36;
  }
  if ( CProviderEntry::ReadInfoFromRegistry(v31, 0, 0, 0, &Uuid2) >= 0 )
  {
    if ( !(unsigned int)CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::Add((char *)this + 144, v31) )
    {
      LastError = 14;
      goto LABEL_91;
    }
    *((_QWORD *)this + 40) = *((_QWORD *)v31 + 263);
    v31 = 0;
  }
  if ( v31 )
    (**(void (__fastcall ***)(CProviderEntry *, __int64))v31)(v31, 1);
  v48 = 0;
  if ( *((_DWORD *)this + 38) )
  {
    do
    {
      v49 = v48 + 1;
      for ( i = v48 + 1; i < *((_DWORD *)this + 38); ++i )
      {
        if ( (unsigned int)CProviderEntry::IssuerMatch(
                             *(CProviderEntry **)(*((_QWORD *)this + 18) + 8LL * v48),
                             *(struct _SecPkgContext_IssuerListInfoEx **)(*(_QWORD *)(*((_QWORD *)this + 18) + 8LL * i)
                                                                        + 2120LL)) )
        {
          *((_DWORD *)this + 87) = 1;
          break;
        }
      }
      if ( *((_DWORD *)this + 87) )
        break;
      ++v48;
    }
    while ( v49 < *((_DWORD *)this + 38) );
  }
  v51 = *((unsigned int *)this + 38);
  *((_DWORD *)this + 44) = v51;
  if ( !(_DWORD)v51 )
    goto LABEL_116;
  v52 = 8 * v51;
  if ( v52 > 0xFFFFFFFF )
  {
LABEL_121:
    LastError = 111;
    goto LABEL_36;
  }
  v53 = LocalAlloc(0x40u, (unsigned int)v52);
  *((_QWORD *)this + 21) = v53;
  if ( !v53 )
  {
    *((_DWORD *)this + 44) = 0;
    LastError = 14;
    goto LABEL_36;
  }
  for ( j = 0; j < *((_DWORD *)this + 44); ++j )
    *(_QWORD *)(8LL * j + *((_QWORD *)this + 21)) = *(_QWORD *)(*(_QWORD *)(8LL * j + *((_QWORD *)this + 18)) + 2112LL);
LABEL_116:
  CertChainEngine = CProviderRegistrationCache::CreateCertChainEngine(this);
  LastError = CertChainEngine;
  if ( CertChainEngine && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v56, v4, "CreateCertChainEngine", CertChainEngine);
LABEL_36:
  v25 = TokenHandle;
  if ( TokenHandle )
  {
    if ( v3 )
    {
      if ( !SetThreadToken(0, TokenHandle) && !LastError )
        LastError = GetLastError();
      v25 = TokenHandle;
    }
    NtClose(v25);
    TokenHandle = 0;
  }
  if ( v2 )
    LocalFree(v2);
  if ( LastError )
    CProviderRegistrationCache::ShutDown(this, 0);
  v26 = LastError;
  if ( (int)LastError > 0 )
    v27 = (unsigned __int16)LastError | 0x80070000;
  else
    v27 = LastError;
  cchName = v27;
  if ( (int)v27 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v25, v4, "CProviderRegistrationCache::ReadProviderRegistration", v27);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>(&v70, &cchName);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v25, Func_Exit, "CProviderRegistrationCache::ReadProviderRegistration");
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
  return v26;
}

```

## disassembly

```asm
0x1800043d0  push    rbp
0x1800043d2  push    rbx
0x1800043d3  push    rsi
0x1800043d4  push    rdi
0x1800043d5  push    r12
0x1800043d7  push    r13
0x1800043d9  push    r14
0x1800043db  push    r15
0x1800043dd  lea     rbp, [rsp-268h]
0x1800043e5  sub     rsp, 368h
0x1800043ec  mov     rax, cs:__security_cookie
0x1800043f3  xor     rax, rsp
0x1800043f6  mov     [rbp+2A0h+var_50], rax
0x1800043fd  mov     r13, rcx
0x180004400  xor     ebx, ebx
0x180004402  mov     [rsp+3A0h+var_340], ebx
0x180004406  mov     [rsp+3A0h+cSubKeys], ebx
0x18000440a  mov     [rsp+3A0h+cbMaxSubKeyLen], ebx
0x18000440e  mov     [rsp+3A0h+cbMaxValueLen], ebx
0x180004412  mov     qword ptr [rbp+2A0h+ftLastWriteTime.dwLowDateTime], rbx
0x180004416  mov     edi, ebx
0x180004418  mov     r12d, ebx
0x18000441b  mov     [rsp+3A0h+TokenHandle], rbx
0x180004420  xor     edx, edx; Val
0x180004422  mov     r8d, 208h; Size
0x180004428  lea     rcx, [rbp+2A0h+var_260]; void *
0x18000442c  call    memset_0
0x180004431  lea     r15, [r13+10h]
0x180004435  mov     [rbp+2A0h+var_2F8], r15
0x180004439  mov     dl, 1; Wait
0x18000443b  mov     rcx, r15; Resource
0x18000443e  call    cs:__imp_RtlAcquireResourceExclusive
0x180004444  mov     [rbp+2A0h+var_2F0], 1
0x180004448  lea     rsi, aCproviderregis_12; "CProviderRegistrationCache::ReadProvide"...
0x18000444f  mov     [rbp+2A0h+var_2E8], rsi
0x180004453  xorps   xmm0, xmm0
0x180004456  movdqu  [rbp+2A0h+var_2E0], xmm0
0x18000445b  lea     rax, [rsp+3A0h+var_340]
0x180004460  mov     [rbp+2A0h+var_2D0], rax
0x180004464  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18000446b  jz      short loc_18000447D
0x18000446d  mov     r8, rsi
0x180004470  lea     rdx, Func_Start
0x180004477  call    McTemplateU0s_EtwEventWriteTransfer
0x18000447c  nop
0x18000447d  cmp     dword ptr [r13+8], 0
0x180004482  jnz     short loc_180004491
0x180004484  mov     [rsp+3A0h+var_340], 139Fh
0x18000448c  jmp     loc_180004719
0x180004491  lea     r9, [rsp+3A0h+TokenHandle]; TokenHandle
0x180004496  mov     r8b, 1; OpenAsSelf
0x180004499  mov     edx, 0Ch; DesiredAccess
0x18000449e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800044a5  call    cs:__imp_NtOpenThreadToken
0x1800044ab  test    eax, eax
0x1800044ad  jns     short loc_1800044CE
0x1800044af  cmp     eax, 0C000007Ch
0x1800044b4  jz      short loc_1800044C7
0x1800044b6  mov     ecx, eax; Status
0x1800044b8  call    cs:__imp_RtlNtStatusToDosError
0x1800044be  mov     [rsp+3A0h+var_340], eax
0x1800044c2  jmp     loc_180004719
0x1800044c7  mov     [rsp+3A0h+TokenHandle], rbx
0x1800044cc  jmp     short loc_1800044F1
0x1800044ce  xor     edx, edx; Token
0x1800044d0  xor     ecx, ecx; Thread
0x1800044d2  call    cs:__imp_SetThreadToken
0x1800044d8  test    eax, eax
0x1800044da  jnz     short loc_1800044EB
0x1800044dc  call    cs:__imp_GetLastError
0x1800044e2  mov     [rsp+3A0h+var_340], eax
0x1800044e6  jmp     loc_180004719
0x1800044eb  mov     r12d, 1
0x1800044f1  xor     edx, edx; int
0x1800044f3  mov     rcx, r13; this
0x1800044f6  call    ?ShutDown@CProviderRegistrationCache@@QEAAKH@Z; CProviderRegistrationCache::ShutDown(int)
0x1800044fb  lea     rbx, aMy; "My"
0x180004502  mov     [rsp+3A0h+pvPara], rbx; pvPara
0x180004507  mov     r9d, 2C000h; dwFlags
0x18000450d  xor     r8d, r8d; hCryptProv
0x180004510  mov     edx, 10001h; dwEncodingType
0x180004515  mov     ecx, 0Ah; lpszStoreProvider
0x18000451a  call    cs:__imp_CertOpenStore
0x180004520  mov     [r13+148h], rax
0x180004527  test    rax, rax
0x18000452a  jnz     short loc_180004558
0x18000452c  call    cs:__imp_GetLastError
0x180004532  mov     [rsp+3A0h+var_340], eax
0x180004536  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000453d  jz      short loc_180004551
0x18000453f  mov     r9d, eax
0x180004542  mov     r8, rbx
0x180004545  lea     rdx, CertOpenStoreFailed
0x18000454c  call    McTemplateU0zq_EtwEventWriteTransfer
0x180004551  xor     ebx, ebx
0x180004553  jmp     loc_180004719
0x180004558  xor     r9d, r9d; lpName
0x18000455b  xor     r8d, r8d; bInitialState
0x18000455e  mov     edx, 1; bManualReset
0x180004563  xor     ecx, ecx; lpEventAttributes
0x180004565  call    cs:__imp_CreateEventW
0x18000456b  lea     r9, [r13+150h]; pvCtrlPara
0x180004572  mov     [r9], rax
0x180004575  test    rax, rax
0x180004578  jnz     short loc_1800045A3
0x18000457a  call    cs:__imp_GetLastError
0x180004580  mov     [rsp+3A0h+var_340], eax
0x180004584  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000458b  jz      short loc_180004551
0x18000458d  mov     r9d, eax
0x180004590  lea     r8, aCreateevent; "CreateEvent"
0x180004597  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000459c  xor     ebx, ebx
0x18000459e  jmp     loc_180004719
0x1800045a3  xor     edx, edx; dwFlags
0x1800045a5  mov     r8d, 2; dwCtrlType
0x1800045ab  mov     rcx, [r13+148h]; hCertStore
0x1800045b2  call    cs:__imp_CertControlStore
0x1800045b8  test    eax, eax
0x1800045ba  jnz     short loc_1800045E5
0x1800045bc  call    cs:__imp_GetLastError
0x1800045c2  mov     [rsp+3A0h+var_340], eax
0x1800045c6  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800045cd  jz      short loc_180004551
0x1800045cf  mov     r9d, eax
0x1800045d2  lea     r8, aCertcontrolsto; "CertControlStore"
0x1800045d9  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800045de  xor     ebx, ebx
0x1800045e0  jmp     loc_180004719
0x1800045e5  lea     rcx, [r13+158h]
0x1800045ec  call    DsrIsDeviceJoinedEx
0x1800045f1  test    eax, eax
0x1800045f3  jns     short loc_18000463E
0x1800045f5  mov     [rsp+3A0h+var_340], 549h
0x1800045fd  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004604  jz      loc_180004551
0x18000460a  mov     r9d, eax
0x18000460d  lea     r8, aDsrisdevicejoi_1; "DsrIsDeviceJoined"
0x180004614  call    McTemplateU0sq_EtwEventWriteTransfer
0x180004619  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004620  jz      loc_180004551
0x180004626  mov     r9d, [rsp+3A0h+var_340]
0x18000462b  lea     r8, aDsrisdevicejoi_0; "DsrIsDeviceJoined(mapped)"
0x180004632  call    McTemplateU0sq_EtwEventWriteTransfer
0x180004637  xor     ebx, ebx
0x180004639  jmp     loc_180004719
0x18000463e  lea     r14, [r13+70h]
0x180004642  mov     [rsp+3A0h+pvPara], r14; phkResult
0x180004647  mov     r9d, 20019h; samDesired
0x18000464d  xor     r8d, r8d; ulOptions
0x180004650  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityStore\\Pro"...
0x180004657  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000465e  call    cs:__imp_RegOpenKeyExW
0x180004664  mov     [rsp+3A0h+var_340], eax
0x180004668  test    eax, eax
0x18000466a  jz      short loc_18000468E
0x18000466c  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004673  jz      short loc_180004684
0x180004675  mov     r8d, eax
0x180004678  lea     rdx, FailedToOpenProvRoot
0x18000467f  call    McTemplateU0q_EtwEventWriteTransfer
0x180004684  xor     ebx, ebx
0x180004686  mov     [r14], rbx
0x180004689  jmp     loc_180004719
0x18000468e  mov     [rsp+3A0h+pvPara], 0
0x180004697  mov     r9d, 208h
0x18000469d  lea     r8, [rbp+2A0h+var_260]
0x1800046a1  lea     rsi, aSoftwareMicros_1; "Software\\Microsoft\\IdentityStore\\Loa"...
0x1800046a8  mov     rdx, rsi
0x1800046ab  lea     rcx, aIdstoreloadpar; "IDStoreLoadParameters"
0x1800046b2  call    cs:__imp_GetPersistedRegistryLocationW
0x1800046b8  mov     [rsp+3A0h+var_340], eax
0x1800046bc  lea     rbx, [r13+78h]
0x1800046c0  lea     rdx, [rbp+2A0h+var_260]
0x1800046c4  test    eax, eax
0x1800046c6  cmovnz  rdx, rsi; lpSubKey
0x1800046ca  mov     [rsp+3A0h+pvPara], rbx; phkResult
0x1800046cf  mov     r9d, 20019h; samDesired
0x1800046d5  xor     r8d, r8d; ulOptions
0x1800046d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800046df  call    cs:__imp_RegOpenKeyExW
0x1800046e5  mov     [rsp+3A0h+var_340], eax
0x1800046e9  test    eax, eax
0x1800046eb  jz      loc_18000478A
0x1800046f1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800046f8  jz      short loc_180004709
0x1800046fa  mov     r8d, eax
0x1800046fd  lea     rdx, FailedToOpenProvRoot
0x180004704  call    McTemplateU0q_EtwEventWriteTransfer
0x180004709  mov     qword ptr [rbx], 0
0x180004710  xor     ebx, ebx
0x180004712  lea     rsi, aCproviderregis_12; "CProviderRegistrationCache::ReadProvide"...
0x180004719  mov     rcx, [rsp+3A0h+TokenHandle]
0x18000471e  test    rcx, rcx
0x180004721  jz      short loc_180004757
0x180004723  test    r12d, r12d
0x180004726  jz      short loc_18000474C
0x180004728  mov     rdx, rcx; Token
0x18000472b  xor     ecx, ecx; Thread
0x18000472d  call    cs:__imp_SetThreadToken
0x180004733  test    eax, eax
0x180004735  jnz     short loc_180004747
0x180004737  cmp     [rsp+3A0h+var_340], eax
0x18000473b  jnz     short loc_180004747
0x18000473d  call    cs:__imp_GetLastError
0x180004743  mov     [rsp+3A0h+var_340], eax
0x180004747  mov     rcx, [rsp+3A0h+TokenHandle]; Handle
0x18000474c  call    cs:__imp_NtClose
0x180004752  mov     [rsp+3A0h+TokenHandle], rbx
0x180004757  test    rdi, rdi
0x18000475a  jz      short loc_180004765
0x18000475c  mov     rcx, rdi; hMem
0x18000475f  call    cs:__imp_LocalFree
0x180004765  cmp     [rsp+3A0h+var_340], 0
0x18000476a  jz      short loc_180004776
0x18000476c  xor     edx, edx; int
0x18000476e  mov     rcx, r13; this
0x180004771  call    ?ShutDown@CProviderRegistrationCache@@QEAAKH@Z; CProviderRegistrationCache::ShutDown(int)
0x180004776  mov     ebx, [rsp+3A0h+var_340]
0x18000477a  test    ebx, ebx
0x18000477c  jg      loc_180004D1D
0x180004782  mov     r9d, ebx
0x180004785  jmp     loc_180004D28
0x18000478a  xor     r9d, r9d; lpName
0x18000478d  xor     r8d, r8d; bInitialState
0x180004790  xor     edx, edx; bManualReset
0x180004792  xor     ecx, ecx; lpEventAttributes
0x180004794  call    cs:__imp_CreateEventW
0x18000479a  mov     [r13+80h], rax
0x1800047a1  test    rax, rax
0x1800047a4  jnz     short loc_180004807
0x1800047a6  call    cs:__imp_GetLastError
0x1800047ac  mov     [rsp+3A0h+var_340], eax
0x1800047b0  xor     ebx, ebx
0x1800047b2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800047b9  jz      loc_180004712
0x1800047bf  mov     [rsp+3A0h+cchName], eax
0x1800047c3  lea     r8, aCreateevent; "CreateEvent"
0x1800047ca  mov     qword ptr [rbp+2A0h+var_2A0], r8
0x1800047ce  mov     qword ptr [rbp+2A0h+var_2A0+8], 0Ch
0x1800047d6  lea     rax, [rsp+3A0h+cchName]
0x1800047db  mov     qword ptr [rbp+2A0h+var_290], rax
0x1800047df  mov     qword ptr [rbp+2A0h+var_290+8], 4
0x1800047e7  lea     rax, [rbp+2A0h+var_2B0]
0x1800047eb  mov     [rsp+3A0h+pvPara], rax
0x1800047f0  mov     r9d, 3
0x1800047f6  lea     rdx, FunctionName_Returned_Error
0x1800047fd  call    McGenEventWrite_EtwEventWriteTransfer
0x180004802  jmp     loc_180004712
0x180004807  mov     dword ptr [rsp+3A0h+pvPara], 1; fAsynchronous
0x18000480f  mov     r9, rax; hEvent
0x180004812  mov     edx, 1; bWatchSubtree
0x180004817  mov     r8d, 10000005h; dwNotifyFilter
0x18000481d  mov     rcx, [rbx]; hKey
0x180004820  call    cs:__imp_RegNotifyChangeKeyValue
0x180004826  mov     [rsp+3A0h+var_340], eax
0x18000482a  test    eax, eax
0x18000482c  jz      short loc_18000484F
0x18000482e  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004835  jz      loc_180004710
0x18000483b  mov     r9d, eax
0x18000483e  lea     r8, aCreateevent; "CreateEvent"
0x180004845  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000484a  jmp     loc_180004710
0x18000484f  lea     rax, [rbp+2A0h+ftLastWriteTime]
0x180004853  mov     [rsp+3A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004858  xor     ebx, ebx
0x18000485a  mov     [rsp+3A0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18000485f  lea     rax, [rsp+3A0h+cbMaxValueLen]
0x180004864  mov     [rsp+3A0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180004869  mov     [rsp+3A0h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18000486e  mov     [rsp+3A0h+lpcValues], rbx; lpcValues
0x180004873  mov     [rsp+3A0h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180004878  lea     rax, [rsp+3A0h+cbMaxSubKeyLen]
0x18000487d  mov     [rsp+3A0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180004882  lea     rax, [rsp+3A0h+cSubKeys]
0x180004887  mov     [rsp+3A0h+pvPara], rax; lpcSubKeys
0x18000488c  xor     r9d, r9d; lpReserved
0x18000488f  xor     r8d, r8d; lpcchClass
0x180004892  xor     edx, edx; lpClass
0x180004894  mov     rcx, [r14]; hKey
0x180004897  call    cs:__imp_RegQueryInfoKeyW
0x18000489d  mov     [rsp+3A0h+var_340], eax
0x1800048a1  test    eax, eax
0x1800048a3  jz      short loc_1800048C6
0x1800048a5  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800048ac  jz      loc_180004712
0x1800048b2  mov     r8d, eax
0x1800048b5  lea     rdx, FailedToQueryProvRoot
0x1800048bc  call    McTemplateU0q_EtwEventWriteTransfer
0x1800048c1  jmp     loc_180004712
0x1800048c6  mov     eax, [rsp+3A0h+cbMaxSubKeyLen]
0x1800048ca  lea     ecx, [rax+1]
0x1800048cd  cmp     ecx, eax
0x1800048cf  jb      loc_180004D07
0x1800048d5  mov     [rsp+3A0h+cbMaxSubKeyLen], ecx
0x1800048d9  mov     eax, ecx
0x1800048db  add     rax, rax
0x1800048de  mov     ecx, 0FFFFFFFFh
0x1800048e3  cmp     rax, rcx
  ... truncated ...
```
