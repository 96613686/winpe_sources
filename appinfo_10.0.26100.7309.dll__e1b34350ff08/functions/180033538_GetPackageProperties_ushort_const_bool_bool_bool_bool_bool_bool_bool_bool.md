# GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x180033538`
- end: `0x180033a15`
- name: `?GetPackageProperties@@YAJPEBGPEA_N1111111@Z`
- size: `1245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *, bool *, bool *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `5`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027464`
- `0x180027d78`
- `0x1800286a4`
- `0x18002a1d8`
- `0x180032810`

## callees

- `0x180006510`
- `0x180007b30`
- `0x180007c78`
- `0x18000dd90`
- `0x18001847c`
- `0x180018530`
- `0x18001d474`
- `0x18002731c`
- `0x18002d548`
- `0x180033538`
- `0x180036054`
- `0x180039608`
- `0x180039828`
- `0x1800398a4`
- `0x180039df0`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003387a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003387a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003393c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003393c`
- `ntdll!RtlInitUnicodeString` at `0x1800337f2`
- `ntdll!RtlInitUnicodeString` at `0x1800337f2`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003382c`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003382c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800335de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800339e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800335de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800339e3`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003377d`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003377d`

## string_xrefs

- `0x1800335ba`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033676`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800336a6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800337aa`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033843`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800337e3`: `packageWriteRedirectionCompatibilityShim`

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
      (void *)0x1278,
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
      (void *)0x1288,
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
            (void *)0x128B,
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
          (void *)0x12B2,
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
                (void *)0x12BE,
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
0x180033538  push    rbp
0x18003353a  push    rbx
0x18003353b  push    rsi
0x18003353c  push    rdi
0x18003353d  push    r12
0x18003353f  push    r13
0x180033541  push    r14
0x180033543  push    r15
0x180033545  lea     rbp, [rsp-0E8h]
0x18003354d  sub     rsp, 1E8h
0x180033554  mov     rax, cs:__security_cookie
0x18003355b  xor     rax, rsp
0x18003355e  mov     [rbp+120h+var_50], rax
0x180033565  mov     rax, [rbp+120h+arg_30]
0x18003356c  mov     r15, r9
0x18003356f  mov     r12, [rbp+120h+arg_20]
0x180033576  mov     r14, r8
0x180033579  mov     r13, [rbp+120h+arg_28]
0x180033580  mov     rsi, rdx
0x180033583  mov     rdi, [rbp+120h+arg_38]
0x18003358a  and     [rsp+220h+var_1C8], 0
0x180033590  mov     [rbp+120h+var_130], rax
0x180033594  mov     rax, [rbp+120h+arg_40]
0x18003359b  mov     [rbp+120h+var_1A0], rcx
0x18003359f  lea     rcx, [rsp+220h+var_1C8]
0x1800335a4  mov     [rbp+120h+var_128], rax
0x1800335a8  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x1800335ad  mov     ebx, eax
0x1800335af  test    eax, eax
0x1800335b1  jns     short loc_1800335F1
0x1800335b3  mov     rcx, [rbp+128h]; this
0x1800335ba  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800335c1  mov     r9d, eax; char *
0x1800335c4  mov     edx, 1278h; void *
0x1800335c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335ce  mov     rcx, [rsp+220h+var_1C8]
0x1800335d3  and     [rsp+220h+var_1C8], 0
0x1800335d9  test    rcx, rcx
0x1800335dc  jz      short loc_1800335EA
0x1800335de  call    cs:__imp_SRCacheManager_Close
0x1800335e5  nop     dword ptr [rax+rax+00h]
0x1800335ea  mov     eax, ebx
0x1800335ec  jmp     loc_1800339F1
0x1800335f1  mov     dl, 1
0x1800335f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x1800335fa  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800335ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180033606  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x18003360b  mov     rdx, [rbp+120h+var_1A0]
0x18003360f  lea     r9, [rbp+120h+var_190]
0x180033613  neg     al
0x180033615  lea     rcx, [rsp+220h+var_1C8]
0x18003361a  xorps   xmm0, xmm0
0x18003361d  sbb     r8, r8
0x180033620  movdqa  [rbp+120h+var_190], xmm0
0x180033625  xor     eax, eax
0x180033627  movdqa  [rbp+120h+var_150], xmm0
0x18003362c  mov     [rbp+120h+var_180], rax
0x180033630  and     r8, 0FFFFFFFFFFFFFFE0h
0x180033634  mov     [rbp+120h+var_178], rax
0x180033638  add     r8, 23Ah
0x18003363f  mov     [rbp+120h+var_170], rax
0x180033643  mov     [rbp+120h+var_168], rax
0x180033647  mov     [rbp+120h+var_160], rax
0x18003364b  mov     [rbp+120h+var_158], rax
0x18003364f  mov     [rbp+120h+var_140], eax
0x180033652  mov     [rbp+120h+var_138], rax
0x180033656  mov     byte ptr [rsp+220h+var_1D0], al
0x18003365a  lea     rax, [rsp+220h+var_1D0]
0x18003365f  mov     qword ptr [rsp+220h+bIgnoreCase], rax; unsigned int
0x180033664  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180033669  mov     ebx, eax
0x18003366b  test    eax, eax
0x18003366d  jns     short loc_180033698
0x18003366f  mov     rcx, [rbp+128h]; this
0x180033676  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003367d  mov     r9d, eax; char *
0x180033680  mov     edx, 1288h; void *
0x180033685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003368a  lea     rcx, [rbp+120h+var_190]; this
0x18003368e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180033693  jmp     loc_1800335CE
0x180033698  cmp     byte ptr [rsp+220h+var_1D0], 0
0x18003369d  jnz     short loc_1800336C1
0x18003369f  mov     rcx, [rbp+128h]; this
0x1800336a6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800336ad  mov     r9d, 2; char *
0x1800336b3  mov     edx, 128Bh; void *
0x1800336b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800336bd  mov     ebx, eax
0x1800336bf  jmp     short loc_18003368A
0x1800336c1  mov     ecx, dword ptr [rbp+120h+var_178+4]
0x1800336c4  test    rsi, rsi
0x1800336c7  jz      short loc_1800336D2
0x1800336c9  mov     eax, ecx
0x1800336cb  shr     eax, 0Bh
0x1800336ce  and     al, 1
0x1800336d0  mov     [rsi], al
0x1800336d2  xor     esi, esi
0x1800336d4  test    r14, r14
0x1800336d7  jz      short loc_1800336E3
0x1800336d9  mov     eax, ecx
0x1800336db  shr     eax, 15h
0x1800336de  and     al, 1
0x1800336e0  mov     [r14], al
0x1800336e3  test    r15, r15
0x1800336e6  jz      short loc_1800336F2
0x1800336e8  mov     eax, ecx
0x1800336ea  shr     eax, 16h
0x1800336ed  and     al, 1
0x1800336ef  mov     [r15], al
0x1800336f2  mov     r14d, 44h ; 'D'
0x1800336f8  test    r12, r12
0x1800336fb  jz      loc_1800338AD
0x180033701  bt      ecx, 0Bh
0x180033705  jb      loc_1800338A8
0x18003370b  bt      ecx, 1Ah
0x18003370f  jb      loc_1800338A8
0x180033715  cmp     qword ptr [rbp+120h+var_150], rsi
0x180033719  jnz     loc_1800338A8
0x18003371f  call    IsQueryApplicationCapabilitiesPresent
0x180033724  test    al, al
0x180033726  jz      loc_1800338AD
0x18003372c  lea     rax, [rsp+220h+var_1C0]
0x180033731  mov     [rsp+220h+var_1C0], rsi
0x180033736  lea     rcx, [rsp+220h+var_1C0]
0x18003373b  mov     [rsp+220h+var_1B0], rax
0x180033740  mov     [rsp+220h+var_1B8], rsi
0x180033745  mov     [rsp+220h+var_1A8], esi
0x180033749  mov     [rsp+220h+var_1A4], 1
0x18003374e  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180033753  mov     rcx, [rbp+120h+var_1A0]
0x180033757  lea     r8, [rsp+220h+var_1A8]
0x18003375c  mov     [rsp+220h+var_1E0], rsi
0x180033761  lea     rdx, [rsp+220h+var_1C0]
0x180033766  mov     [rsp+220h+var_1E8], rsi
0x18003376b  xor     r9d, r9d
0x18003376e  mov     [rsp+220h+var_1F0], rsi
0x180033773  mov     [rsp+220h+var_1F8], rsi
0x180033778  mov     qword ptr [rsp+220h+bIgnoreCase], rsi; int
0x18003377d  call    cs:__imp_QueryApplicationCapabilities
0x180033784  nop     dword ptr [rax+rax+00h]
0x180033789  mov     ebx, eax
0x18003378b  cmp     [rsp+220h+var_1A4], sil
0x180033790  jz      short loc_18003379F
0x180033792  mov     rcx, [rsp+220h+var_1B0]
0x180033797  mov     edx, [rsp+220h+var_1A8]
0x18003379b  mov     [rcx+8], rdx
0x18003379f  test    ebx, ebx
0x1800337a1  jns     short loc_1800337E0
0x1800337a3  mov     rcx, [rbp+128h]; this
0x1800337aa  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800337b1  mov     r9d, ebx; char *
0x1800337b4  mov     edx, 12B2h; void *
0x1800337b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800337be  lea     rcx, [rsp+220h+var_1C0]
0x1800337c3  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x1800337c8  lea     rcx, [rbp+120h+var_190]; this
0x1800337cc  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800337d1  mov     rcx, [rsp+220h+var_1C8]
0x1800337d6  mov     [rsp+220h+var_1C8], rsi
0x1800337db  jmp     loc_1800335D9
0x1800337e0  xorps   xmm0, xmm0
0x1800337e3  lea     rdx, aPackagewritere; "packageWriteRedirectionCompatibilityShi"...
0x1800337ea  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x1800337ee  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x1800337f2  call    cs:__imp_RtlInitUnicodeString
0x1800337f9  nop     dword ptr [rax+rax+00h]
0x1800337fe  mov     r8, r14; Size
0x180033801  lea     rcx, [rbp+120h+pSid2]; void *
0x180033808  xor     edx, edx; Val
0x18003380a  call    memset_0
0x18003380f  mov     r8, r14; Size
0x180033812  lea     rcx, [rbp+120h+lpString1]; void *
0x180033816  xor     edx, edx; Val
0x180033818  call    memset_0
0x18003381d  lea     r8, [rbp+120h+pSid2]
0x180033824  lea     rdx, [rbp+120h+lpString1]
0x180033828  lea     rcx, [rbp+120h+DestinationString]
0x18003382c  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180033833  nop     dword ptr [rax+rax+00h]
0x180033838  test    eax, eax
0x18003383a  jns     short loc_18003385E
0x18003383c  mov     rcx, [rbp+128h]; this
0x180033843  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003384a  mov     r9d, eax; char *
0x18003384d  mov     edx, 12BEh; void *
0x180033852  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180033857  mov     ebx, eax
0x180033859  jmp     loc_1800337BE
0x18003385e  mov     ebx, esi
0x180033860  cmp     [rsp+220h+var_1B8], rsi
0x180033865  jbe     short loc_18003389C
0x180033867  mov     rax, rsi
0x18003386a  mov     rcx, [rsp+220h+var_1C0]
0x18003386f  lea     rdx, [rbp+120h+pSid2]; pSid2
0x180033876  mov     rcx, [rcx+rax*8]; pSid1
0x18003387a  call    cs:__imp_EqualSid
0x180033881  nop     dword ptr [rax+rax+00h]
0x180033886  test    eax, eax
0x180033888  jnz     short loc_180033897
0x18003388a  inc     ebx
0x18003388c  mov     eax, ebx
0x18003388e  cmp     rax, [rsp+220h+var_1B8]
0x180033893  jb      short loc_18003386A
0x180033895  jmp     short loc_18003389C
0x180033897  mov     byte ptr [r12], 1
0x18003389c  lea     rcx, [rsp+220h+var_1C0]
0x1800338a1  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x1800338a6  jmp     short loc_1800338AD
0x1800338a8  mov     byte ptr [r12], 1
0x1800338ad  test    r13, r13
0x1800338b0  jz      short loc_1800338BE
0x1800338b2  mov     eax, dword ptr [rbp+120h+var_170]
0x1800338b5  shr     eax, 0Fh
0x1800338b8  and     al, 1
0x1800338ba  mov     [r13+0], al
0x1800338be  mov     rbx, [rbp+120h+var_130]
0x1800338c2  test    rbx, rbx
0x1800338c5  jz      loc_180033959
0x1800338cb  mov     dl, 1
0x1800338cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x1800338d4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800338d9  xorps   xmm0, xmm0
0x1800338dc  lea     rcx, [rbp+120h+var_100]; void *
0x1800338e0  mov     r8, r14; Size
0x1800338e3  movdqa  xmmword ptr [rbp+120h+lpString1], xmm0
0x1800338e8  xor     edx, edx; Val
0x1800338ea  call    memset_0
0x1800338ef  mov     rdx, [rbp+120h+var_180]
0x1800338f3  lea     rax, [rsp+220h+var_1D0]
0x1800338f8  lea     r9, [rbp+120h+lpString1]
0x1800338fc  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x180033901  lea     rcx, [rsp+220h+var_1C8]
0x180033906  mov     [rbp+120h+var_B8], rsi
0x18003390a  mov     [rbp+120h+var_B0], rsi
0x18003390e  mov     byte ptr [rsp+220h+var_1D0], sil
0x180033913  call    ?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x180033918  test    eax, eax
0x18003391a  js      short loc_180033950
0x18003391c  cmp     byte ptr [rsp+220h+var_1D0], sil
0x180033921  jz      short loc_180033950
0x180033923  mov     rcx, [rbp+120h+lpString1+8]; lpString1
0x180033927  lea     r8, aMicrosoftwindo; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x18003392e  or      edx, 0FFFFFFFFh; cchCount1
0x180033931  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180033939  mov     r9d, edx; cchCount2
0x18003393c  call    cs:__imp_CompareStringOrdinal
0x180033943  nop     dword ptr [rax+rax+00h]
0x180033948  cmp     eax, 2
0x18003394b  setz    al
0x18003394e  mov     [rbx], al
0x180033950  lea     rcx, [rbp+120h+lpString1]; this
0x180033954  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x180033959  test    rdi, rdi
0x18003395c  jz      short loc_1800339A8
0x18003395e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180033965  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x18003396a  test    al, al
0x18003396c  jz      short loc_180033983
0x18003396e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180033975  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x18003397a  test    al, al
0x18003397c  jnz     short loc_180033999
0x18003397e  mov     al, sil
0x180033981  jmp     short loc_1800339A1
0x180033983  cmp     dword ptr [rbp+120h+var_170+4], 2
0x180033987  jz      short loc_1800339A5
0x180033989  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180033990  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180033995  test    al, al
0x180033997  jz      short loc_1800339A5
0x180033999  mov     eax, dword ptr [rbp+120h+var_170]
0x18003399c  shr     eax, 15h
0x18003399f  and     al, 1
0x1800339a1  mov     [rdi], al
0x1800339a3  jmp     short loc_1800339A8
0x1800339a5  mov     [rdi], sil
0x1800339a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA> `wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl(void)'::`2'::impl
0x1800339af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(void)
0x1800339b4  test    al, al
0x1800339b6  jz      short loc_1800339CB
0x1800339b8  mov     rcx, [rbp+120h+var_128]
0x1800339bc  test    rcx, rcx
0x1800339bf  jz      short loc_1800339CB
0x1800339c1  mov     eax, dword ptr [rbp+120h+var_178+4]
0x1800339c4  shr     eax, 1Ch
0x1800339c7  and     al, 1
0x1800339c9  mov     [rcx], al
0x1800339cb  lea     rcx, [rbp+120h+var_190]; this
0x1800339cf  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800339d4  mov     rcx, [rsp+220h+var_1C8]
0x1800339d9  mov     [rsp+220h+var_1C8], rsi
0x1800339de  test    rcx, rcx
0x1800339e1  jz      short loc_1800339EF
0x1800339e3  call    cs:__imp_SRCacheManager_Close
0x1800339ea  nop     dword ptr [rax+rax+00h]
0x1800339ef  xor     eax, eax
0x1800339f1  mov     rcx, [rbp+120h+var_50]
0x1800339f8  xor     rcx, rsp; StackCookie
  ... truncated ...
```
