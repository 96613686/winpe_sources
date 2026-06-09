# StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)

- ea: `0x18003037c`
- end: `0x180030aa9`
- name: `?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z`
- size: `1837`
- prototype: `__int64 __fastcall(__int64, unsigned int, const WCHAR *, int *)`
- caller_count: `8`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031660`
- `0x180032088`
- `0x18003253c`
- `0x180033118`
- `0x1800334b8`
- `0x18003376c`
- `0x180033b78`
- `0x180037720`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180012ce0`
- `0x180019db4`
- `0x18001b3b0`
- `0x18002ab90`
- `0x18002fd64`
- `0x18002fe70`
- `0x1800301c4`
- `0x18003037c`
- `0x180030ab0`
- `0x180031cec`
- `0x180037720`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800304f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003053e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003059c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030641`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030728`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030781`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800307dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003093c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030959`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800309b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030a3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030a68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800304f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003053e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003059c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030641`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030728`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030781`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800307dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003093c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030959`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800309b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030a3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030a68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800307be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800307be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003068a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800306c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030823`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030869`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003068a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800306c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030823`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030869`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030496`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800305dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030496`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800305dc`

## string_xrefs

- `0x1800303c6`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x1800304d4`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030522`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030581`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18003061a`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030701`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18003075a`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x1800308d2`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030920`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030999`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030a1e`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StorageService::GetStoragePolicySettings(__int64 a1, unsigned int a2, const WCHAR *a3, int *a4)
{
  __int64 v6; // rdi
  unsigned int StoragePolicySettings; // ebx
  __int64 v8; // rdx
  __int64 result; // rax
  HKEY v10; // rbx
  int v11; // eax
  int v12; // r15d
  int v13; // eax
  int v14; // eax
  LSTATUS ValueW; // eax
  __int64 v16; // rcx
  bool v17; // sf
  int StoragePolicyDefaultValue; // eax
  __int64 v19; // rcx
  int v20; // r13d
  int v21; // eax
  __int64 v22; // rcx
  LSTATUS v23; // eax
  __int64 v24; // rcx
  bool v25; // sf
  int v26; // eax
  __int64 v27; // rcx
  int v28; // r14d
  int v29; // eax
  int v30; // eax
  StorageService *v31; // rcx
  bool v32; // bl
  __int64 v33; // rcx
  int v34; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  bool v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int pvData; // [rsp+70h] [rbp-90h] BYREF
  DWORD v45; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Value[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v6 = (int)a2;
  if ( !a4 )
  {
    StoragePolicySettings = -2147024809;
    v8 = 39;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)StoragePolicySettings,
      pdwType);
    return StoragePolicySettings;
  }
  if ( a2 >= 0xC )
  {
    StoragePolicySettings = -2147418113;
    v8 = 40;
    goto LABEL_3;
  }
  if ( BYTE4(qword_18008E530[3 * (int)a2 + 1]) )
  {
    if ( a2 == 4 )
      return GetSpaceFreed(a4);
    else
      return StorageService::GetStoragePolicyDefaultValue(a1, a2, a4);
  }
  v38[0] = 0;
  v40 = 0;
  result = Util::GetMDMPolicyIsConfiguredAndValue(a2, v38, &v40);
  if ( (int)result >= 0 && v38[0] )
  {
    *a4 = v40;
    return result;
  }
  hKey = 0;
  v45 = 4;
  Microsoft::WRL::Wrappers::CriticalSection::Lock(qword_1800C11A8, &lpCriticalSection);
  v10 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)Data);
    RegCloseKey(v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)Data);
  }
  hKey = 0;
  v11 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"StoragePolicy", &hKey);
  StoragePolicySettings = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v11,
      pdwType);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
LABEL_90:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return StoragePolicySettings;
  }
  if ( !BYTE4(qword_18008E530[3 * v6]) && a3 )
  {
    StoragePolicySettings = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x80070057LL,
      pdwType);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    goto LABEL_90;
  }
  v12 = 1;
  v13 = StringCchPrintfW(Value, 0x104u, L"%02d", (unsigned int)(1 << v6));
  StoragePolicySettings = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v13,
      pdwType);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    goto LABEL_90;
  }
  if ( (_DWORD)v6 == 1 || (_DWORD)v6 == 7 )
  {
    hkey = 0;
    v14 = OpenStorageRegKey(HKEY_LOCAL_MACHINE, (wchar_t *)&word_180092AF0, &hkey);
    StoragePolicySettings = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v14,
        pdwType);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_90;
    }
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(hkey, 0, L"StorageSenseVersion", 0x18u, 0, &pvData, &pcbData) >= 0 && pvData >= 2 )
    {
      ValueW = RegGetValueW(hKey, a3, Value, 0x18u, 0, a4, &v45);
      v17 = ValueW < 0;
      if ( ValueW > 0 )
        v17 = 1;
      if ( v17 )
      {
        v40 = 0;
        StoragePolicyDefaultValue = StorageService::GetStoragePolicyDefaultValue(v16, (unsigned int)v6, &v40);
        StoragePolicySettings = StoragePolicyDefaultValue;
        if ( StoragePolicyDefaultValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
            (const char *)(unsigned int)StoragePolicyDefaultValue,
            pdwTypea);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          if ( lpCriticalSection )
          {
            LeaveCriticalSection(lpCriticalSection);
            lpCriticalSection = 0;
          }
          goto LABEL_90;
        }
        v20 = v40;
        v21 = StorageService::SetStoragePolicySettings(v19, v6, a3, v40);
        StoragePolicySettings = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x62,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
            (const char *)(unsigned int)v21,
            pdwTypea);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          if ( lpCriticalSection )
          {
            LeaveCriticalSection(lpCriticalSection);
            lpCriticalSection = 0;
          }
          goto LABEL_90;
        }
        *a4 = v20;
        *(_DWORD *)Data = 1;
        RegSetValueExW(hKey, L"CloudfilePolicyConsent", 0, 4u, Data, 4u);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      StoragePolicySettings = 0;
      goto LABEL_90;
    }
    v40 = 0;
    *(_DWORD *)Data = 4;
    if ( RegGetValueW(hKey, 0, L"CloudfilePolicyConsent", 0x18u, 0, &v40, (LPDWORD)Data) || !v40 )
    {
      StoragePolicySettings = StorageService::GetStoragePolicyDefaultValue(v22, (unsigned int)v6, a4);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_90;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  v23 = RegGetValueW(hKey, a3, Value, 0x18u, 0, a4, &v45);
  v25 = v23 < 0;
  if ( v23 > 0 )
    v25 = 1;
  if ( v25 )
  {
    if ( a3 )
    {
      StoragePolicySettings = SvcGetStoragePolicySettings();
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_90;
    }
    v40 = 0;
    v26 = StorageService::GetStoragePolicyDefaultValue(v24, (unsigned int)v6, &v40);
    StoragePolicySettings = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v26,
        pdwTypeb);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_90;
    }
    v28 = v40;
    v29 = StorageService::SetStoragePolicySettings(v27, v6, 0, v40);
    StoragePolicySettings = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v29,
        pdwTypeb);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_90;
    }
    *a4 = v28;
  }
  else if ( (_DWORD)v6 == 2 )
  {
    v38[0] = 0;
    v30 = IsCleanMgrPresent(v38);
    StoragePolicySettings = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v30,
        pdwTypeb);
      if ( lpCriticalSection )
      {
        LeaveCriticalSection(lpCriticalSection);
        lpCriticalSection = 0;
      }
      goto LABEL_90;
    }
    if ( v38[0] )
    {
      *(_WORD *)v38 = 0;
      v32 = 0;
      if ( (int)StorageService::SilentCleanupTaskGetEnabledState(v31, (__int16 *)v38) >= 0 )
        v32 = *(_WORD *)v38 == 0xFFFF;
      if ( !*a4 || !v32 )
        v12 = 0;
      *a4 = v12;
      v34 = StorageService::SetStoragePolicySettings(v33, 2, 0, v12);
      StoragePolicySettings = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
          (const char *)(unsigned int)v34,
          pdwTypeb);
        if ( lpCriticalSection )
        {
          LeaveCriticalSection(lpCriticalSection);
          lpCriticalSection = 0;
        }
        goto LABEL_90;
      }
    }
  }
  if ( lpCriticalSection )
  {
    LeaveCriticalSection(lpCriticalSection);
    lpCriticalSection = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18003037c  mov     [rsp-8+arg_0], rbx
0x180030381  push    rbp
0x180030382  push    rsi
0x180030383  push    rdi
0x180030384  push    r12
0x180030386  push    r13
0x180030388  push    r14
0x18003038a  push    r15
0x18003038c  lea     rbp, [rsp-1A0h]
0x180030394  sub     rsp, 2A0h
0x18003039b  mov     rax, cs:__security_cookie
0x1800303a2  xor     rax, rsp
0x1800303a5  mov     [rbp+1D0h+var_40], rax
0x1800303ac  mov     rsi, r9
0x1800303af  mov     r12, r8
0x1800303b2  movsxd  rdi, edx
0x1800303b5  xor     r13d, r13d
0x1800303b8  test    r9, r9
0x1800303bb  jnz     short loc_1800303E1
0x1800303bd  mov     ebx, 80070057h
0x1800303c2  lea     edx, [r9+27h]; void *
0x1800303c6  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800303cd  mov     r9d, ebx; char *
0x1800303d0  mov     rcx, [rbp+1D8h]; this
0x1800303d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800303dc  jmp     loc_180030A7D
0x1800303e1  cmp     edi, 0Ch
0x1800303e4  jb      short loc_1800303F2
0x1800303e6  mov     ebx, 8000FFFFh
0x1800303eb  mov     edx, 28h ; '('
0x1800303f0  jmp     short loc_1800303C6
0x1800303f2  lea     r15, [rdi+rdi*2]
0x1800303f6  lea     rax, qword_18008E530
0x1800303fd  cmp     [rax+r15*8+0Ch], r13b
0x180030402  jz      short loc_18003042B
0x180030404  mov     r14d, 4
0x18003040a  cmp     edi, r14d
0x18003040d  jnz     short loc_18003041C
0x18003040f  mov     rcx, rsi
0x180030412  call    GetSpaceFreed
0x180030417  jmp     loc_180030A7F
0x18003041c  mov     r8, rsi
0x18003041f  mov     edx, edi
0x180030421  call    ?GetStoragePolicyDefaultValue@StorageService@@QEAAJW4_STORAGE_POLICY@@PEAK@Z; StorageService::GetStoragePolicyDefaultValue(_STORAGE_POLICY,ulong *)
0x180030426  jmp     loc_180030A7F
0x18003042b  mov     [rsp+2D0h+var_290], r13b
0x180030430  mov     [rsp+2D0h+var_280], r13d
0x180030435  lea     r8, [rsp+2D0h+var_280]
0x18003043a  lea     rdx, [rsp+2D0h+var_290]
0x18003043f  mov     ecx, edi
0x180030441  call    Util__GetMDMPolicyIsConfiguredAndValue
0x180030446  test    eax, eax
0x180030448  js      short loc_18003045C
0x18003044a  cmp     [rsp+2D0h+var_290], r13b
0x18003044f  jz      short loc_18003045C
0x180030451  mov     ecx, [rsp+2D0h+var_280]
0x180030455  mov     [rsi], ecx
0x180030457  jmp     loc_180030A7F
0x18003045c  mov     [rsp+2D0h+hKey], r13
0x180030461  mov     r14d, 4
0x180030467  mov     [rsp+2D0h+var_25C], r14d
0x18003046c  lea     rdx, [rsp+2D0h+lpCriticalSection]
0x180030471  lea     rcx, qword_1800C11A8
0x180030478  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x18003047d  nop
0x18003047e  mov     rbx, [rsp+2D0h+hKey]
0x180030483  test    rbx, rbx
0x180030486  jz      short loc_1800304A7
0x180030488  lea     rcx, [rsp+2D0h+Data]; this
0x18003048d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030492  nop
0x180030493  mov     rcx, rbx; hKey
0x180030496  call    cs:__imp_RegCloseKey
0x18003049c  nop
0x18003049d  lea     rcx, [rsp+2D0h+Data]; this
0x1800304a2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800304a7  mov     [rsp+2D0h+hKey], r13
0x1800304ac  lea     r8, [rsp+2D0h+hKey]; phkResult
0x1800304b1  lea     rdx, aStoragepolicy; "StoragePolicy"
0x1800304b8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800304bf  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x1800304c4  mov     ebx, eax
0x1800304c6  test    eax, eax
0x1800304c8  jns     short loc_180030500
0x1800304ca  mov     rcx, [rbp+1D8h]; this
0x1800304d1  mov     r9d, eax; char *
0x1800304d4  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800304db  mov     edx, 48h ; 'H'; void *
0x1800304e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304e5  nop
0x1800304e6  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x1800304eb  test    rcx, rcx
0x1800304ee  jz      short loc_1800304FB
0x1800304f0  call    cs:__imp_LeaveCriticalSection
0x1800304f6  mov     [rsp+2D0h+lpCriticalSection], r13
0x1800304fb  jmp     loc_180030A73
0x180030500  lea     rax, qword_18008E530
0x180030507  cmp     [rax+r15*8+4], r13b
0x18003050c  jnz     short loc_18003054E
0x18003050e  test    r12, r12
0x180030511  jz      short loc_18003054E
0x180030513  mov     rcx, [rbp+1D8h]; this
0x18003051a  mov     ebx, 80070057h
0x18003051f  mov     r9d, ebx; char *
0x180030522  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030529  mov     edx, 4Dh ; 'M'; void *
0x18003052e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030533  nop
0x180030534  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x180030539  test    rcx, rcx
0x18003053c  jz      short loc_180030549
0x18003053e  call    cs:__imp_LeaveCriticalSection
0x180030544  mov     [rsp+2D0h+lpCriticalSection], r13
0x180030549  jmp     loc_180030A73
0x18003054e  mov     ecx, edi
0x180030550  mov     r15d, 1
0x180030556  mov     r9d, r15d
0x180030559  shl     r9d, cl
0x18003055c  lea     r8, a02d; "%02d"
0x180030563  mov     edx, 104h; unsigned __int64
0x180030568  lea     rcx, [rbp+1D0h+Value]; unsigned __int16 *
0x18003056c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030571  mov     ebx, eax
0x180030573  test    eax, eax
0x180030575  jns     short loc_1800305AC
0x180030577  mov     rcx, [rbp+1D8h]; this
0x18003057e  mov     r9d, eax; char *
0x180030581  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030588  lea     edx, [r15+4Eh]; void *
0x18003058c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030591  nop
0x180030592  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x180030597  test    rcx, rcx
0x18003059a  jz      short loc_1800305A7
0x18003059c  call    cs:__imp_LeaveCriticalSection
0x1800305a2  mov     [rsp+2D0h+lpCriticalSection], r13
0x1800305a7  jmp     loc_180030A73
0x1800305ac  mov     ebx, 18h
0x1800305b1  cmp     edi, r15d
0x1800305b4  jz      short loc_1800305BF
0x1800305b6  cmp     edi, 7
0x1800305b9  jnz     loc_180030846
0x1800305bf  mov     [rsp+2D0h+hkey], r13
0x1800305c4  mov     rbx, [rsp+2D0h+hkey]
0x1800305c9  test    rbx, rbx
0x1800305cc  jz      short loc_1800305ED
0x1800305ce  lea     rcx, [rsp+2D0h+Data]; this
0x1800305d3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800305d8  nop
0x1800305d9  mov     rcx, rbx; hKey
0x1800305dc  call    cs:__imp_RegCloseKey
0x1800305e2  nop
0x1800305e3  lea     rcx, [rsp+2D0h+Data]; this
0x1800305e8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800305ed  mov     [rsp+2D0h+hkey], r13
0x1800305f2  lea     r8, [rsp+2D0h+hkey]; phkResult
0x1800305f7  lea     rdx, word_180092AF0; wchar_t *
0x1800305fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030605  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18003060a  mov     ebx, eax
0x18003060c  test    eax, eax
0x18003060e  jns     short loc_180030651
0x180030610  mov     rcx, [rbp+1D8h]; this
0x180030617  mov     r9d, eax; char *
0x18003061a  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030621  mov     edx, 57h ; 'W'; void *
0x180030626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003062b  nop
0x18003062c  lea     rcx, [rsp+2D0h+hkey]
0x180030631  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030636  nop
0x180030637  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x18003063c  test    rcx, rcx
0x18003063f  jz      short loc_18003064C
0x180030641  call    cs:__imp_LeaveCriticalSection
0x180030647  mov     [rsp+2D0h+lpCriticalSection], r13
0x18003064c  jmp     loc_180030A73
0x180030651  mov     [rsp+2D0h+var_260], r13d
0x180030656  mov     [rsp+2D0h+var_258], r14d
0x18003065b  lea     rax, [rsp+2D0h+var_258]
0x180030660  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180030665  lea     rax, [rsp+2D0h+var_260]
0x18003066a  mov     [rsp+2D0h+pvData], rax; pvData
0x18003066f  mov     [rsp+2D0h+pdwType], r13; pdwType
0x180030674  mov     ebx, 18h
0x180030679  mov     r9d, ebx; dwFlags
0x18003067c  lea     r8, aStoragesenseve; "StorageSenseVersion"
0x180030683  xor     edx, edx; lpSubKey
0x180030685  mov     rcx, [rsp+2D0h+hkey]; hkey
0x18003068a  call    cs:__imp_RegGetValueW
0x180030690  test    eax, eax
0x180030692  js      loc_1800307EF
0x180030698  cmp     [rsp+2D0h+var_260], 2
0x18003069d  jb      loc_1800307EF
0x1800306a3  lea     rax, [rsp+2D0h+var_25C]
0x1800306a8  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800306ad  mov     [rsp+2D0h+pvData], rsi; pvData
0x1800306b2  mov     [rsp+2D0h+pdwType], r13; int
0x1800306b7  mov     r9d, ebx; dwFlags
0x1800306ba  lea     r8, [rbp+1D0h+Value]; lpValue
0x1800306be  mov     rdx, r12; lpSubKey
0x1800306c1  mov     rcx, [rsp+2D0h+hKey]; hkey
0x1800306c6  call    cs:__imp_RegGetValueW
0x1800306cc  test    eax, eax
0x1800306ce  jle     short loc_1800306DA
0x1800306d0  movzx   eax, ax
0x1800306d3  or      eax, 80070000h
0x1800306d8  test    eax, eax
0x1800306da  jns     loc_1800307C7
0x1800306e0  mov     [rsp+2D0h+var_280], r13d
0x1800306e5  lea     r8, [rsp+2D0h+var_280]
0x1800306ea  mov     edx, edi
0x1800306ec  call    ?GetStoragePolicyDefaultValue@StorageService@@QEAAJW4_STORAGE_POLICY@@PEAK@Z; StorageService::GetStoragePolicyDefaultValue(_STORAGE_POLICY,ulong *)
0x1800306f1  mov     ebx, eax
0x1800306f3  test    eax, eax
0x1800306f5  jns     short loc_180030738
0x1800306f7  mov     rcx, [rbp+1D8h]; this
0x1800306fe  mov     r9d, eax; char *
0x180030701  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030708  mov     edx, 60h ; '`'; void *
0x18003070d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030712  nop
0x180030713  lea     rcx, [rsp+2D0h+hkey]
0x180030718  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003071d  nop
0x18003071e  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x180030723  test    rcx, rcx
0x180030726  jz      short loc_180030733
0x180030728  call    cs:__imp_LeaveCriticalSection
0x18003072e  mov     [rsp+2D0h+lpCriticalSection], r13
0x180030733  jmp     loc_180030A73
0x180030738  mov     r13d, [rsp+2D0h+var_280]
0x18003073d  mov     r9d, r13d
0x180030740  mov     r8, r12
0x180030743  mov     edx, edi
0x180030745  call    ?SetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGK@Z; StorageService::SetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong)
0x18003074a  mov     ebx, eax
0x18003074c  test    eax, eax
0x18003074e  jns     short loc_180030795
0x180030750  mov     rcx, [rbp+1D8h]; this
0x180030757  mov     r9d, eax; char *
0x18003075a  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030761  mov     edx, 62h ; 'b'; void *
0x180030766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003076b  nop
0x18003076c  lea     rcx, [rsp+2D0h+hkey]
0x180030771  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030776  nop
0x180030777  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x18003077c  test    rcx, rcx
0x18003077f  jz      short loc_180030790
0x180030781  call    cs:__imp_LeaveCriticalSection
0x180030787  mov     [rsp+2D0h+lpCriticalSection], 0
0x180030790  jmp     loc_180030A73
0x180030795  mov     [rsi], r13d
0x180030798  mov     dword ptr [rsp+2D0h+Data], r15d
0x18003079d  mov     dword ptr [rsp+2D0h+pvData], r14d; cbData
0x1800307a2  lea     rax, [rsp+2D0h+Data]
0x1800307a7  mov     [rsp+2D0h+pdwType], rax; lpData
0x1800307ac  mov     r9d, r14d; dwType
0x1800307af  xor     r8d, r8d; Reserved
0x1800307b2  lea     rdx, aCloudfilepolic; "CloudfilePolicyConsent"
0x1800307b9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800307be  call    cs:__imp_RegSetValueExW
0x1800307c4  xor     r13d, r13d
0x1800307c7  lea     rcx, [rsp+2D0h+hkey]
0x1800307cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800307d1  nop
0x1800307d2  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x1800307d7  test    rcx, rcx
0x1800307da  jz      short loc_1800307E7
0x1800307dc  call    cs:__imp_LeaveCriticalSection
0x1800307e2  mov     [rsp+2D0h+lpCriticalSection], r13
0x1800307e7  mov     ebx, r13d
0x1800307ea  jmp     loc_180030A73
0x1800307ef  mov     [rsp+2D0h+var_280], r13d
0x1800307f4  mov     dword ptr [rsp+2D0h+Data], r14d
0x1800307f9  lea     rax, [rsp+2D0h+Data]
0x1800307fe  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180030803  lea     rax, [rsp+2D0h+var_280]
0x180030808  mov     [rsp+2D0h+pvData], rax; pvData
0x18003080d  mov     [rsp+2D0h+pdwType], r13; pdwType
0x180030812  mov     r9d, ebx; dwFlags
0x180030815  lea     r8, aCloudfilepolic; "CloudfilePolicyConsent"
0x18003081c  xor     edx, edx; lpSubKey
0x18003081e  mov     rcx, [rsp+2D0h+hKey]; hkey
0x180030823  call    cs:__imp_RegGetValueW
0x180030829  test    eax, eax
0x18003082b  jnz     loc_180030A47
0x180030831  cmp     [rsp+2D0h+var_280], r13d
0x180030836  jz      loc_180030A47
0x18003083c  lea     rcx, [rsp+2D0h+hkey]
0x180030841  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030846  lea     rax, [rsp+2D0h+var_25C]
0x18003084b  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180030850  mov     [rsp+2D0h+pvData], rsi; pvData
0x180030855  mov     [rsp+2D0h+pdwType], r13; int
0x18003085a  mov     r9d, ebx; dwFlags
0x18003085d  lea     r8, [rbp+1D0h+Value]; lpValue
0x180030861  mov     rdx, r12; lpSubKey
  ... truncated ...
```
