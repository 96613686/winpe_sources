# CSecurityManager::GlobalInit(void)

- ea: `0x180038428`
- end: `0x1800385fa`
- name: `?GlobalInit@CSecurityManager@@SAHXZ`
- size: `466`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038358`

## callees

- `0x180038150`
- `0x180038428`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180038554`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180038554`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180038441`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003844e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180038441`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003844e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800384d2`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180038544`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800385ba`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800385eb`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800384d2`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180038544`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800385ba`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800385eb`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800384f9`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800384f9`

## pseudocode

```c
__int64 CSecurityManager::GlobalInit(void)
{
  BOOL fIgnoreHKCU; // eax
  HUSKEY v1; // rcx
  int v2; // eax
  int IsFeatureEnabledInternal; // ecx
  BOOL v5; // eax
  const unsigned int *v6; // [rsp+30h] [rbp-20h] BYREF
  HUSKEY v7; // [rsp+38h] [rbp-18h]
  BOOL v8; // [rsp+40h] [rbp-10h]
  __int64 v9; // [rsp+44h] [rbp-Ch]
  HUSKEY phNewUSKey; // [rsp+60h] [rbp+10h] BYREF

  InitializeCriticalSection(&CSecurityManager::s_csectZones);
  InitializeCriticalSection(&CSecurityManager::s_csectAList);
  CSecurityManager::s_fcsectZonesInit = 1;
  v6 = &CRegKey::`vftable';
  v7 = 0;
  v8 = g_bUseHKLMOnly;
  v9 = 1;
  if ( FCK::FEATURE_IGNORE_POLICIES_ZONEMAP_IF_ESC_ENABLED_KB918915 )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_3;
    dword_180159D98 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_IGNORE_POLICIES_ZONEMAP_IF_ESC_ENABLED_KB918915 = 0;
  }
  if ( dword_180159D98 && (unsigned int)IsInternetESCEnabledLocal() )
    goto LABEL_11;
LABEL_3:
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v6 + 2))(&v6);
  if ( !(_DWORD)v9 )
  {
LABEL_4:
    fIgnoreHKCU = v8;
    goto LABEL_5;
  }
  fIgnoreHKCU = v8;
  if ( !v8 )
  {
    if ( !SHRegOpenUSKeyW(
            L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\Domains\\",
            0x20019u,
            0,
            &phNewUSKey,
            1) )
      goto LABEL_6;
    goto LABEL_4;
  }
LABEL_5:
  if ( !SHRegOpenUSKeyW(
          L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\Domains\\",
          0x20019u,
          0,
          &phNewUSKey,
          fIgnoreHKCU) )
  {
LABEL_6:
    v1 = phNewUSKey;
    v2 = 1;
    v7 = phNewUSKey;
    goto LABEL_7;
  }
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v6 + 2))(&v6);
  if ( !(_DWORD)v9 )
    goto LABEL_18;
  v5 = v8;
  if ( !v8 )
  {
    if ( !SHRegOpenUSKeyW(L"ZoneMap\\Ranges\\", 0x20019u, 0, &phNewUSKey, 1) )
      goto LABEL_6;
LABEL_18:
    v5 = v8;
  }
  if ( !SHRegOpenUSKeyW(L"ZoneMap\\Ranges\\", 0x20019u, 0, &phNewUSKey, v5) )
    goto LABEL_6;
LABEL_11:
  v1 = v7;
  v2 = 0;
LABEL_7:
  CSecurityManager::s_fUsePoliciesZoneMap = v2;
  v6 = &CRegKey::`vftable';
  if ( v1 )
    SHRegCloseUSKey(v1);
  return 1;
}

```

## disassembly

```asm
0x180038428  mov     [rsp-8+arg_8], rdi
0x18003842d  mov     [rsp-8+arg_10], r14
0x180038432  push    rbp
0x180038433  mov     rbp, rsp
0x180038436  sub     rsp, 50h
0x18003843a  lea     rcx, ?s_csectZones@CSecurityManager@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038441  call    cs:__imp_InitializeCriticalSection
0x180038447  lea     rcx, ?s_csectAList@CSecurityManager@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003844e  call    cs:__imp_InitializeCriticalSection
0x180038454  mov     rcx, cs:?FEATURE_IGNORE_POLICIES_ZONEMAP_IF_ESC_ENABLED_KB918915@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_IGNORE_POLICIES_ZONEMAP_IF_ESC_ENABLED_KB918915
0x18003845b  lea     r14, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180038462  mov     eax, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x180038468  mov     edi, 1
0x18003846d  mov     cs:?s_fcsectZonesInit@CSecurityManager@@0HA, edi; int CSecurityManager::s_fcsectZonesInit
0x180038473  mov     [rbp+var_20], r14
0x180038477  mov     [rbp+var_18], 0
0x18003847f  mov     [rbp+var_10], eax
0x180038482  mov     [rbp+var_C], rdi
0x180038486  test    rcx, rcx
0x180038489  jnz     loc_180038554
0x18003848f  mov     eax, cs:dword_180159D98
0x180038495  test    eax, eax
0x180038497  jnz     short loc_180038511
0x180038499  mov     rax, [rbp+var_20]
0x18003849d  lea     rcx, [rbp+var_20]
0x1800384a1  mov     [rbp+phNewUSKey], 0
0x1800384a9  mov     rax, [rax+10h]
0x1800384ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384b2  cmp     dword ptr [rbp+var_C], 0
0x1800384b6  jnz     short loc_180038526
0x1800384b8  mov     eax, [rbp+var_10]
0x1800384bb  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x1800384bf  mov     [rsp+50h+fIgnoreHKCU], eax; fIgnoreHKCU
0x1800384c3  xor     r8d, r8d; hRelativeUSKey
0x1800384c6  lea     rcx, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Windows"...
0x1800384cd  mov     edx, 20019h; samDesired
0x1800384d2  call    cs:__imp_SHRegOpenUSKeyW
0x1800384d8  test    eax, eax
0x1800384da  jnz     loc_180038581
0x1800384e0  mov     rcx, [rbp+phNewUSKey]; hUSKey
0x1800384e4  mov     eax, edi
0x1800384e6  mov     [rbp+var_18], rcx
0x1800384ea  mov     cs:?s_fUsePoliciesZoneMap@CSecurityManager@@0HA, eax; int CSecurityManager::s_fUsePoliciesZoneMap
0x1800384f0  mov     [rbp+var_20], r14
0x1800384f4  test    rcx, rcx
0x1800384f7  jz      short loc_1800384FF
0x1800384f9  call    cs:__imp_SHRegCloseUSKey
0x1800384ff  mov     r14, [rsp+50h+arg_10]
0x180038504  mov     eax, edi
0x180038506  mov     rdi, [rsp+50h+arg_8]
0x18003850b  add     rsp, 50h
0x18003850f  pop     rbp
0x180038510  retn
0x180038511  call    IsInternetESCEnabledLocal
0x180038516  test    eax, eax
0x180038518  jz      loc_180038499
0x18003851e  mov     rcx, [rbp+var_18]
0x180038522  xor     eax, eax
0x180038524  jmp     short loc_1800384EA
0x180038526  mov     eax, [rbp+var_10]
0x180038529  test    eax, eax
0x18003852b  jnz     short loc_1800384BB
0x18003852d  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x180038531  mov     [rsp+50h+fIgnoreHKCU], edi; fIgnoreHKCU
0x180038535  xor     r8d, r8d; hRelativeUSKey
0x180038538  lea     rcx, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Windows"...
0x18003853f  mov     edx, 20019h; samDesired
0x180038544  call    cs:__imp_SHRegOpenUSKeyW
0x18003854a  test    eax, eax
0x18003854c  jnz     loc_1800384B8
0x180038552  jmp     short loc_1800384E0
0x180038554  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x18003855a  mov     ecx, eax
0x18003855c  test    eax, eax
0x18003855e  js      loc_180038499
0x180038564  xor     eax, eax
0x180038566  test    ecx, ecx
0x180038568  setz    al
0x18003856b  mov     cs:dword_180159D98, eax
0x180038571  mov     cs:?FEATURE_IGNORE_POLICIES_ZONEMAP_IF_ESC_ENABLED_KB918915@FCK@@3VCFeatureControlKey@@A, 0; CFeatureControlKey FCK::FEATURE_IGNORE_POLICIES_ZONEMAP_IF_ESC_ENABLED_KB918915
0x18003857c  jmp     loc_18003848F
0x180038581  mov     rax, [rbp+var_20]
0x180038585  lea     rcx, [rbp+var_20]
0x180038589  mov     [rbp+phNewUSKey], 0
0x180038591  mov     rax, [rax+10h]
0x180038595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003859a  cmp     dword ptr [rbp+var_C], 0
0x18003859e  jnz     short loc_1800385CD
0x1800385a0  mov     eax, [rbp+var_10]
0x1800385a3  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x1800385a7  mov     [rsp+50h+fIgnoreHKCU], eax; fIgnoreHKCU
0x1800385ab  xor     r8d, r8d; hRelativeUSKey
0x1800385ae  lea     rcx, ?SZPOLICIESZONEMAPRANGES@@3QBGB; "ZoneMap\\Ranges\\"
0x1800385b5  mov     edx, 20019h; samDesired
0x1800385ba  call    cs:__imp_SHRegOpenUSKeyW
0x1800385c0  test    eax, eax
0x1800385c2  jz      loc_1800384E0
0x1800385c8  jmp     loc_18003851E
0x1800385cd  mov     eax, [rbp+var_10]
0x1800385d0  test    eax, eax
0x1800385d2  jnz     short loc_1800385A3
0x1800385d4  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x1800385d8  mov     [rsp+50h+fIgnoreHKCU], edi; fIgnoreHKCU
0x1800385dc  xor     r8d, r8d; hRelativeUSKey
0x1800385df  lea     rcx, ?SZPOLICIESZONEMAPRANGES@@3QBGB; "ZoneMap\\Ranges\\"
0x1800385e6  mov     edx, 20019h; samDesired
0x1800385eb  call    cs:__imp_SHRegOpenUSKeyW
0x1800385f1  test    eax, eax
0x1800385f3  jnz     short loc_1800385A0
0x1800385f5  jmp     loc_1800384E0
```
