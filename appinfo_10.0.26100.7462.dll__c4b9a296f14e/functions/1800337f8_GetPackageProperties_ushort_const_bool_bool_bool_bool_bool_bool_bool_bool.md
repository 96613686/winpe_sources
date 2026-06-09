# GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x1800337f8`
- end: `0x180033cd5`
- name: `?GetPackageProperties@@YAJPEBGPEA_N1111111@Z`
- size: `1245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *, bool *, bool *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `5`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027534`
- `0x180027c34`
- `0x180028604`
- `0x18002a2a8`
- `0x180032ad0`

## callees

- `0x180006510`
- `0x180007b30`
- `0x180007c78`
- `0x18000dd90`
- `0x18001847c`
- `0x180018530`
- `0x18001d474`
- `0x1800273ec`
- `0x18002d618`
- `0x1800337f8`
- `0x18003639c`
- `0x180039984`
- `0x180039ba4`
- `0x180039c20`
- `0x18003a170`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180033b3a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180033b3a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033bfc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033bfc`
- `ntdll!RtlInitUnicodeString` at `0x180033ab2`
- `ntdll!RtlInitUnicodeString` at `0x180033ab2`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180033aec`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180033aec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003389e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180033ca3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003389e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180033ca3`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180033a3d`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180033a3d`

## string_xrefs

- `0x18003387a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033936`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033966`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033a6a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033b03`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033aa3`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
__int64 __fastcall GetPackageProperties(
        const unsigned __int16 *a1,
        bool *a2,
        bool *a3,
        bool *a4,
        bool *a5,
        bool *a6,
        bool *a7,
        bool *a8,
        bool *a9)
{
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  char IsEnabled; // al
  int v20; // eax
  __int64 v21; // rdx
  int v22; // ecx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  bool *v27; // rbx
  __int64 v28; // r8
  bool v29; // al
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned int v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-98h]
  __int64 *v39; // [rsp+70h] [rbp-90h]
  unsigned int v40; // [rsp+78h] [rbp-88h] BYREF
  char v41; // [rsp+7Ch] [rbp-84h]
  const unsigned __int16 *v42; // [rsp+80h] [rbp-80h]
  __int128 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  __int64 v49; // [rsp+C8h] [rbp-38h]
  __int128 v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  bool *v53; // [rsp+F0h] [rbp-10h]
  bool *v54; // [rsp+F8h] [rbp-8h]
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  LPCWCH lpString1[2]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v57[72]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v58; // [rsp+168h] [rbp+68h]
  __int64 v59; // [rsp+170h] [rbp+70h]
  _BYTE pSid2[80]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v36 = 0;
  v53 = a7;
  v42 = a1;
  v54 = a9;
  v12 = StateRepository::Cache::Manager_NoThrow::Open(&v36);
  v14 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12AF,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
LABEL_3:
    v17 = v36;
    v36 = 0;
LABEL_4:
    if ( v17 )
      SRCacheManager_Close(v17, v15, v16);
    return v14;
  }
  LOBYTE(v13) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
    v13);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl);
  v43 = 0;
  v50 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v51 = 0;
  v52 = 0;
  LOBYTE(v35) = 0;
  v20 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v36,
          v42,
          (-(__int64)(IsEnabled != 0) & 0xFFFFFFFFFFFFFFE0uLL) + 570,
          (__int64)&v43,
          (bool *)&v35);
  v14 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12BF,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v20,
      bIgnoreCasea);
LABEL_9:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
    goto LABEL_3;
  }
  if ( !(_BYTE)v35 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x12C2,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)2,
            bIgnoreCasea);
    goto LABEL_9;
  }
  v22 = HIDWORD(v45);
  if ( a2 )
    *a2 = (v45 & 0x80000000000LL) != 0;
  if ( a3 )
    *a3 = (v22 & 0x200000) != 0;
  if ( a4 )
    *a4 = (v22 & 0x400000) != 0;
  if ( a5 )
  {
    if ( (v22 & 0x800) != 0 || (v22 & 0x4000000) != 0 || (_QWORD)v50 )
    {
      *a5 = 1;
    }
    else if ( (unsigned __int8)IsQueryApplicationCapabilitiesPresent() )
    {
      v37 = 0;
      v39 = &v37;
      v38 = 0;
      v40 = 0;
      v41 = 1;
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v37);
      v23 = QueryApplicationCapabilities(v42, &v37, &v40, 0);
      v14 = v23;
      if ( v41 )
        v39[1] = v40;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12E9,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v23,
          0);
LABEL_27:
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v37);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
        v17 = v36;
        v36 = 0;
        goto LABEL_4;
      }
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
      memset_0(pSid2, 0, 0x44u);
      memset_0(lpString1, 0, 0x44u);
      v24 = RtlDeriveCapabilitySidsFromName(&DestinationString, lpString1, pSid2);
      if ( v24 < 0 )
      {
        v14 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x12F5,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)(unsigned int)v24,
                0);
        goto LABEL_27;
      }
      v25 = 0;
      if ( v38 )
      {
        v26 = 0;
        while ( !EqualSid(*(PSID *)(v37 + 8 * v26), pSid2) )
        {
          v26 = ++v25;
          if ( v25 >= v38 )
            goto LABEL_36;
        }
        *a5 = 1;
      }
LABEL_36:
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v37);
    }
  }
  if ( a6 )
    *a6 = (v46 & 0x8000) != 0;
  v27 = v53;
  if ( v53 )
  {
    LOBYTE(v21) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
      v21);
    *(_OWORD *)lpString1 = 0;
    memset_0(v57, 0, 0x44u);
    v58 = 0;
    v59 = 0;
    LOBYTE(v35) = 0;
    if ( (int)StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(&v36, v44, v28, lpString1, &v35) >= 0
      && (_BYTE)v35 )
    {
      *v27 = CompareStringOrdinal(lpString1[1], -1, L"MicrosoftWindows.Client.AIX_cw5n1h2txyewy", -1, 1) == 2;
    }
    StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)lpString1);
  }
  if ( a8 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
      {
        v29 = 0;
LABEL_52:
        *a8 = v29;
        goto LABEL_54;
      }
LABEL_51:
      v29 = (v46 & 0x200000) != 0;
      goto LABEL_52;
    }
    if ( HIDWORD(v46) != 2
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
    {
      goto LABEL_51;
    }
    *a8 = 0;
  }
LABEL_54:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl'::`2'::impl)
    && v54 )
  {
    *v54 = (v45 & 0x1000000000000000LL) != 0;
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
  v32 = v36;
  v36 = 0;
  if ( v32 )
    SRCacheManager_Close(v32, v30, v31);
  return 0;
}

```

## disassembly

```asm
0x1800337f8  push    rbp
0x1800337fa  push    rbx
0x1800337fb  push    rsi
0x1800337fc  push    rdi
0x1800337fd  push    r12
0x1800337ff  push    r13
0x180033801  push    r14
0x180033803  push    r15
0x180033805  lea     rbp, [rsp-0E8h]
0x18003380d  sub     rsp, 1E8h
0x180033814  mov     rax, cs:__security_cookie
0x18003381b  xor     rax, rsp
0x18003381e  mov     [rbp+120h+var_50], rax
0x180033825  mov     rax, [rbp+120h+arg_30]
0x18003382c  mov     r15, r9
0x18003382f  mov     r12, [rbp+120h+arg_20]
0x180033836  mov     r14, r8
0x180033839  mov     r13, [rbp+120h+arg_28]
0x180033840  mov     rsi, rdx
0x180033843  mov     rdi, [rbp+120h+arg_38]
0x18003384a  and     [rsp+220h+var_1C8], 0
0x180033850  mov     [rbp+120h+var_130], rax
0x180033854  mov     rax, [rbp+120h+arg_40]
0x18003385b  mov     [rbp+120h+var_1A0], rcx
0x18003385f  lea     rcx, [rsp+220h+var_1C8]
0x180033864  mov     [rbp+120h+var_128], rax
0x180033868  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x18003386d  mov     ebx, eax
0x18003386f  test    eax, eax
0x180033871  jns     short loc_1800338B1
0x180033873  mov     rcx, [rbp+128h]; this
0x18003387a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180033881  mov     r9d, eax; char *
0x180033884  mov     edx, 12AFh; void *
0x180033889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003388e  mov     rcx, [rsp+220h+var_1C8]
0x180033893  and     [rsp+220h+var_1C8], 0
0x180033899  test    rcx, rcx
0x18003389c  jz      short loc_1800338AA
0x18003389e  call    cs:__imp_SRCacheManager_Close
0x1800338a5  nop     dword ptr [rax+rax+00h]
0x1800338aa  mov     eax, ebx
0x1800338ac  jmp     loc_180033CB1
0x1800338b1  mov     dl, 1
0x1800338b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x1800338ba  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800338bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x1800338c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x1800338cb  mov     rdx, [rbp+120h+var_1A0]
0x1800338cf  lea     r9, [rbp+120h+var_190]
0x1800338d3  neg     al
0x1800338d5  lea     rcx, [rsp+220h+var_1C8]
0x1800338da  xorps   xmm0, xmm0
0x1800338dd  sbb     r8, r8
0x1800338e0  movdqa  [rbp+120h+var_190], xmm0
0x1800338e5  xor     eax, eax
0x1800338e7  movdqa  [rbp+120h+var_150], xmm0
0x1800338ec  mov     [rbp+120h+var_180], rax
0x1800338f0  and     r8, 0FFFFFFFFFFFFFFE0h
0x1800338f4  mov     [rbp+120h+var_178], rax
0x1800338f8  add     r8, 23Ah
0x1800338ff  mov     [rbp+120h+var_170], rax
0x180033903  mov     [rbp+120h+var_168], rax
0x180033907  mov     [rbp+120h+var_160], rax
0x18003390b  mov     [rbp+120h+var_158], rax
0x18003390f  mov     [rbp+120h+var_140], eax
0x180033912  mov     [rbp+120h+var_138], rax
0x180033916  mov     byte ptr [rsp+220h+var_1D0], al
0x18003391a  lea     rax, [rsp+220h+var_1D0]
0x18003391f  mov     qword ptr [rsp+220h+bIgnoreCase], rax; unsigned int
0x180033924  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180033929  mov     ebx, eax
0x18003392b  test    eax, eax
0x18003392d  jns     short loc_180033958
0x18003392f  mov     rcx, [rbp+128h]; this
0x180033936  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003393d  mov     r9d, eax; char *
0x180033940  mov     edx, 12BFh; void *
0x180033945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003394a  lea     rcx, [rbp+120h+var_190]; this
0x18003394e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180033953  jmp     loc_18003388E
0x180033958  cmp     byte ptr [rsp+220h+var_1D0], 0
0x18003395d  jnz     short loc_180033981
0x18003395f  mov     rcx, [rbp+128h]; this
0x180033966  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003396d  mov     r9d, 2; char *
0x180033973  mov     edx, 12C2h; void *
0x180033978  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003397d  mov     ebx, eax
0x18003397f  jmp     short loc_18003394A
0x180033981  mov     ecx, dword ptr [rbp+120h+var_178+4]
0x180033984  test    rsi, rsi
0x180033987  jz      short loc_180033992
0x180033989  mov     eax, ecx
0x18003398b  shr     eax, 0Bh
0x18003398e  and     al, 1
0x180033990  mov     [rsi], al
0x180033992  xor     esi, esi
0x180033994  test    r14, r14
0x180033997  jz      short loc_1800339A3
0x180033999  mov     eax, ecx
0x18003399b  shr     eax, 15h
0x18003399e  and     al, 1
0x1800339a0  mov     [r14], al
0x1800339a3  test    r15, r15
0x1800339a6  jz      short loc_1800339B2
0x1800339a8  mov     eax, ecx
0x1800339aa  shr     eax, 16h
0x1800339ad  and     al, 1
0x1800339af  mov     [r15], al
0x1800339b2  mov     r14d, 44h ; 'D'
0x1800339b8  test    r12, r12
0x1800339bb  jz      loc_180033B6D
0x1800339c1  bt      ecx, 0Bh
0x1800339c5  jb      loc_180033B68
0x1800339cb  bt      ecx, 1Ah
0x1800339cf  jb      loc_180033B68
0x1800339d5  cmp     qword ptr [rbp+120h+var_150], rsi
0x1800339d9  jnz     loc_180033B68
0x1800339df  call    IsQueryApplicationCapabilitiesPresent
0x1800339e4  test    al, al
0x1800339e6  jz      loc_180033B6D
0x1800339ec  lea     rax, [rsp+220h+var_1C0]
0x1800339f1  mov     [rsp+220h+var_1C0], rsi
0x1800339f6  lea     rcx, [rsp+220h+var_1C0]
0x1800339fb  mov     [rsp+220h+var_1B0], rax
0x180033a00  mov     [rsp+220h+var_1B8], rsi
0x180033a05  mov     [rsp+220h+var_1A8], esi
0x180033a09  mov     [rsp+220h+var_1A4], 1
0x180033a0e  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180033a13  mov     rcx, [rbp+120h+var_1A0]
0x180033a17  lea     r8, [rsp+220h+var_1A8]
0x180033a1c  mov     [rsp+220h+var_1E0], rsi
0x180033a21  lea     rdx, [rsp+220h+var_1C0]
0x180033a26  mov     [rsp+220h+var_1E8], rsi
0x180033a2b  xor     r9d, r9d
0x180033a2e  mov     [rsp+220h+var_1F0], rsi
0x180033a33  mov     [rsp+220h+var_1F8], rsi
0x180033a38  mov     qword ptr [rsp+220h+bIgnoreCase], rsi; int
0x180033a3d  call    cs:__imp_QueryApplicationCapabilities
0x180033a44  nop     dword ptr [rax+rax+00h]
0x180033a49  mov     ebx, eax
0x180033a4b  cmp     [rsp+220h+var_1A4], sil
0x180033a50  jz      short loc_180033A5F
0x180033a52  mov     rcx, [rsp+220h+var_1B0]
0x180033a57  mov     edx, [rsp+220h+var_1A8]
0x180033a5b  mov     [rcx+8], rdx
0x180033a5f  test    ebx, ebx
0x180033a61  jns     short loc_180033AA0
0x180033a63  mov     rcx, [rbp+128h]; this
0x180033a6a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180033a71  mov     r9d, ebx; char *
0x180033a74  mov     edx, 12E9h; void *
0x180033a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a7e  lea     rcx, [rsp+220h+var_1C0]
0x180033a83  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180033a88  lea     rcx, [rbp+120h+var_190]; this
0x180033a8c  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180033a91  mov     rcx, [rsp+220h+var_1C8]
0x180033a96  mov     [rsp+220h+var_1C8], rsi
0x180033a9b  jmp     loc_180033899
0x180033aa0  xorps   xmm0, xmm0
0x180033aa3  lea     rdx, aPackagewritere; "packageWriteRedirectionCompatibilityShi"...
0x180033aaa  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x180033aae  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x180033ab2  call    cs:__imp_RtlInitUnicodeString
0x180033ab9  nop     dword ptr [rax+rax+00h]
0x180033abe  mov     r8, r14; Size
0x180033ac1  lea     rcx, [rbp+120h+pSid2]; void *
0x180033ac8  xor     edx, edx; Val
0x180033aca  call    memset_0
0x180033acf  mov     r8, r14; Size
0x180033ad2  lea     rcx, [rbp+120h+lpString1]; void *
0x180033ad6  xor     edx, edx; Val
0x180033ad8  call    memset_0
0x180033add  lea     r8, [rbp+120h+pSid2]
0x180033ae4  lea     rdx, [rbp+120h+lpString1]
0x180033ae8  lea     rcx, [rbp+120h+DestinationString]
0x180033aec  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180033af3  nop     dword ptr [rax+rax+00h]
0x180033af8  test    eax, eax
0x180033afa  jns     short loc_180033B1E
0x180033afc  mov     rcx, [rbp+128h]; this
0x180033b03  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180033b0a  mov     r9d, eax; char *
0x180033b0d  mov     edx, 12F5h; void *
0x180033b12  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180033b17  mov     ebx, eax
0x180033b19  jmp     loc_180033A7E
0x180033b1e  mov     ebx, esi
0x180033b20  cmp     [rsp+220h+var_1B8], rsi
0x180033b25  jbe     short loc_180033B5C
0x180033b27  mov     rax, rsi
0x180033b2a  mov     rcx, [rsp+220h+var_1C0]
0x180033b2f  lea     rdx, [rbp+120h+pSid2]; pSid2
0x180033b36  mov     rcx, [rcx+rax*8]; pSid1
0x180033b3a  call    cs:__imp_EqualSid
0x180033b41  nop     dword ptr [rax+rax+00h]
0x180033b46  test    eax, eax
0x180033b48  jnz     short loc_180033B57
0x180033b4a  inc     ebx
0x180033b4c  mov     eax, ebx
0x180033b4e  cmp     rax, [rsp+220h+var_1B8]
0x180033b53  jb      short loc_180033B2A
0x180033b55  jmp     short loc_180033B5C
0x180033b57  mov     byte ptr [r12], 1
0x180033b5c  lea     rcx, [rsp+220h+var_1C0]
0x180033b61  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180033b66  jmp     short loc_180033B6D
0x180033b68  mov     byte ptr [r12], 1
0x180033b6d  test    r13, r13
0x180033b70  jz      short loc_180033B7E
0x180033b72  mov     eax, dword ptr [rbp+120h+var_170]
0x180033b75  shr     eax, 0Fh
0x180033b78  and     al, 1
0x180033b7a  mov     [r13+0], al
0x180033b7e  mov     rbx, [rbp+120h+var_130]
0x180033b82  test    rbx, rbx
0x180033b85  jz      loc_180033C19
0x180033b8b  mov     dl, 1
0x180033b8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x180033b94  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180033b99  xorps   xmm0, xmm0
0x180033b9c  lea     rcx, [rbp+120h+var_100]; void *
0x180033ba0  mov     r8, r14; Size
0x180033ba3  movdqa  xmmword ptr [rbp+120h+lpString1], xmm0
0x180033ba8  xor     edx, edx; Val
0x180033baa  call    memset_0
0x180033baf  mov     rdx, [rbp+120h+var_180]
0x180033bb3  lea     rax, [rsp+220h+var_1D0]
0x180033bb8  lea     r9, [rbp+120h+lpString1]
0x180033bbc  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x180033bc1  lea     rcx, [rsp+220h+var_1C8]
0x180033bc6  mov     [rbp+120h+var_B8], rsi
0x180033bca  mov     [rbp+120h+var_B0], rsi
0x180033bce  mov     byte ptr [rsp+220h+var_1D0], sil
0x180033bd3  call    ?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x180033bd8  test    eax, eax
0x180033bda  js      short loc_180033C10
0x180033bdc  cmp     byte ptr [rsp+220h+var_1D0], sil
0x180033be1  jz      short loc_180033C10
0x180033be3  mov     rcx, [rbp+120h+lpString1+8]; lpString1
0x180033be7  lea     r8, aMicrosoftwindo; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x180033bee  or      edx, 0FFFFFFFFh; cchCount1
0x180033bf1  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180033bf9  mov     r9d, edx; cchCount2
0x180033bfc  call    cs:__imp_CompareStringOrdinal
0x180033c03  nop     dword ptr [rax+rax+00h]
0x180033c08  cmp     eax, 2
0x180033c0b  setz    al
0x180033c0e  mov     [rbx], al
0x180033c10  lea     rcx, [rbp+120h+lpString1]; this
0x180033c14  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x180033c19  test    rdi, rdi
0x180033c1c  jz      short loc_180033C68
0x180033c1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180033c25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x180033c2a  test    al, al
0x180033c2c  jz      short loc_180033C43
0x180033c2e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180033c35  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180033c3a  test    al, al
0x180033c3c  jnz     short loc_180033C59
0x180033c3e  mov     al, sil
0x180033c41  jmp     short loc_180033C61
0x180033c43  cmp     dword ptr [rbp+120h+var_170+4], 2
0x180033c47  jz      short loc_180033C65
0x180033c49  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180033c50  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180033c55  test    al, al
0x180033c57  jz      short loc_180033C65
0x180033c59  mov     eax, dword ptr [rbp+120h+var_170]
0x180033c5c  shr     eax, 15h
0x180033c5f  and     al, 1
0x180033c61  mov     [rdi], al
0x180033c63  jmp     short loc_180033C68
0x180033c65  mov     [rdi], sil
0x180033c68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA> `wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl(void)'::`2'::impl
0x180033c6f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(void)
0x180033c74  test    al, al
0x180033c76  jz      short loc_180033C8B
0x180033c78  mov     rcx, [rbp+120h+var_128]
0x180033c7c  test    rcx, rcx
0x180033c7f  jz      short loc_180033C8B
0x180033c81  mov     eax, dword ptr [rbp+120h+var_178+4]
0x180033c84  shr     eax, 1Ch
0x180033c87  and     al, 1
0x180033c89  mov     [rcx], al
0x180033c8b  lea     rcx, [rbp+120h+var_190]; this
0x180033c8f  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180033c94  mov     rcx, [rsp+220h+var_1C8]
0x180033c99  mov     [rsp+220h+var_1C8], rsi
0x180033c9e  test    rcx, rcx
0x180033ca1  jz      short loc_180033CAF
0x180033ca3  call    cs:__imp_SRCacheManager_Close
0x180033caa  nop     dword ptr [rax+rax+00h]
0x180033caf  xor     eax, eax
0x180033cb1  mov     rcx, [rbp+120h+var_50]
0x180033cb8  xor     rcx, rsp; StackCookie
  ... truncated ...
```
