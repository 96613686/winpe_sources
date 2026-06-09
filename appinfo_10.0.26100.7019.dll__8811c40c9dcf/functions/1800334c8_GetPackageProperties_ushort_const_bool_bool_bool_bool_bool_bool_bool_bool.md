# GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x1800334c8`
- end: `0x180033963`
- name: `?GetPackageProperties@@YAJPEBGPEA_N1111111@Z`
- size: `1179`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *, bool *, bool *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `5`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028aa4`
- `0x180029474`
- `0x180029ce4`
- `0x18002b828`
- `0x1800327a0`

## callees

- `0x180006510`
- `0x180007b30`
- `0x180007c78`
- `0x18000d8e0`
- `0x18000de50`
- `0x1800181cc`
- `0x180018280`
- `0x18001d098`
- `0x18002895c`
- `0x18002eb68`
- `0x1800334c8`
- `0x180035f20`
- `0x180038f68`
- `0x1800391c4`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800337f2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800337f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800338b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800338b2`
- `ntdll!RtlInitUnicodeString` at `0x18003376a`
- `ntdll!RtlInitUnicodeString` at `0x18003376a`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800337a4`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800337a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003356e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180033931`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003356e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180033931`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1800336f5`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1800336f5`

## string_xrefs

- `0x18003354a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800335f0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033620`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033722`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800337bb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003375b`: `packageWriteRedirectionCompatibilityShim`

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
  int v19; // eax
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rax
  bool *v26; // rbx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-98h]
  __int64 *v37; // [rsp+70h] [rbp-90h]
  unsigned int v38; // [rsp+78h] [rbp-88h] BYREF
  char v39; // [rsp+7Ch] [rbp-84h]
  const unsigned __int16 *v40; // [rsp+80h] [rbp-80h]
  bool *v41; // [rsp+88h] [rbp-78h]
  bool *v42; // [rsp+90h] [rbp-70h]
  __int128 v43; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+F8h] [rbp-8h]
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  LPCWCH lpString1[2]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v55[72]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v56; // [rsp+168h] [rbp+68h]
  __int64 v57; // [rsp+170h] [rbp+70h]
  _BYTE pSid2[80]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v34 = 0;
  v41 = a7;
  v40 = a1;
  v42 = a9;
  v12 = StateRepository::Cache::Manager_NoThrow::Open(&v34);
  v14 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C5,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
LABEL_3:
    v17 = v34;
    v34 = 0;
LABEL_4:
    if ( v17 )
      SRCacheManager_Close(v17, v15, v16);
    return v14;
  }
  LOBYTE(v13) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
    v13);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v51 = 0;
  v52 = 0;
  LOBYTE(v33) = 0;
  v43 = 0;
  v50 = 0;
  v19 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v34,
          v40,
          538,
          (__int64)&v43,
          (bool *)&v33);
  v14 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D4,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v19,
      bIgnoreCasea);
LABEL_9:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
    goto LABEL_3;
  }
  if ( !(_BYTE)v33 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x11D7,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)2,
            bIgnoreCasea);
    goto LABEL_9;
  }
  v21 = HIDWORD(v45);
  if ( a2 )
    *a2 = (v45 & 0x80000000000LL) != 0;
  if ( a3 )
    *a3 = (v21 & 0x200000) != 0;
  if ( a4 )
    *a4 = (v21 & 0x400000) != 0;
  if ( a5 )
  {
    if ( (v21 & 0x800) != 0 || (v21 & 0x4000000) != 0 || (_QWORD)v50 )
    {
      *a5 = 1;
    }
    else if ( (unsigned __int8)IsQueryApplicationCapabilitiesPresent() )
    {
      v35 = 0;
      v37 = &v35;
      v36 = 0;
      v38 = 0;
      v39 = 1;
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v35);
      v22 = QueryApplicationCapabilities(v40, &v35, &v38, 0);
      v14 = v22;
      if ( v39 )
        v37[1] = v38;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11FE,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v22,
          0);
LABEL_27:
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v35);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
        v17 = v34;
        v34 = 0;
        goto LABEL_4;
      }
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
      memset_0(pSid2, 0, 0x44u);
      memset_0(lpString1, 0, 0x44u);
      v23 = RtlDeriveCapabilitySidsFromName(&DestinationString, lpString1, pSid2);
      if ( v23 < 0 )
      {
        v14 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x120A,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)(unsigned int)v23,
                0);
        goto LABEL_27;
      }
      v24 = 0;
      if ( v36 )
      {
        v25 = 0;
        while ( !EqualSid(*(PSID *)(v35 + 8 * v25), pSid2) )
        {
          v25 = ++v24;
          if ( v24 >= v36 )
            goto LABEL_36;
        }
        *a5 = 1;
      }
LABEL_36:
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v35);
    }
  }
  if ( a6 )
    *a6 = (v46 & 0x8000) != 0;
  v26 = v41;
  if ( v41 )
  {
    LOBYTE(v20) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
      v20);
    *(_OWORD *)lpString1 = 0;
    memset_0(v55, 0, 0x44u);
    v56 = 0;
    v57 = 0;
    LOBYTE(v33) = 0;
    if ( (int)StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(&v34, v44, v27, lpString1, &v33) >= 0
      && (_BYTE)v33 )
    {
      *v26 = CompareStringOrdinal(lpString1[1], -1, L"MicrosoftWindows.Client.AIX_cw5n1h2txyewy", -1, 1) == 2;
    }
    StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)lpString1);
  }
  if ( a8 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
      *a8 = (v46 & 0x200000) != 0;
    else
      *a8 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl'::`2'::impl)
    && v42 )
  {
    *v42 = (v45 & 0x1000000000000000LL) != 0;
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v43);
  v30 = v34;
  v34 = 0;
  if ( v30 )
    SRCacheManager_Close(v30, v28, v29);
  return 0;
}

```

## disassembly

```asm
0x1800334c8  push    rbp
0x1800334ca  push    rbx
0x1800334cb  push    rsi
0x1800334cc  push    rdi
0x1800334cd  push    r12
0x1800334cf  push    r13
0x1800334d1  push    r14
0x1800334d3  push    r15
0x1800334d5  lea     rbp, [rsp-0E8h]
0x1800334dd  sub     rsp, 1E8h
0x1800334e4  mov     rax, cs:__security_cookie
0x1800334eb  xor     rax, rsp
0x1800334ee  mov     [rbp+120h+var_50], rax
0x1800334f5  mov     rax, [rbp+120h+arg_30]
0x1800334fc  mov     r14, r9
0x1800334ff  mov     r15, [rbp+120h+arg_20]
0x180033506  mov     rsi, r8
0x180033509  mov     r13, [rbp+120h+arg_28]
0x180033510  mov     rdi, rdx
0x180033513  mov     r12, [rbp+120h+arg_38]
0x18003351a  and     [rsp+220h+var_1C8], 0
0x180033520  mov     [rbp+120h+var_198], rax
0x180033524  mov     rax, [rbp+120h+arg_40]
0x18003352b  mov     [rbp+120h+var_1A0], rcx
0x18003352f  lea     rcx, [rsp+220h+var_1C8]
0x180033534  mov     [rbp+120h+var_190], rax
0x180033538  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x18003353d  mov     ebx, eax
0x18003353f  test    eax, eax
0x180033541  jns     short loc_180033581
0x180033543  mov     rcx, [rbp+128h]; this
0x18003354a  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033551  mov     r9d, eax; char *
0x180033554  mov     edx, 11C5h; void *
0x180033559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003355e  mov     rcx, [rsp+220h+var_1C8]
0x180033563  and     [rsp+220h+var_1C8], 0
0x180033569  test    rcx, rcx
0x18003356c  jz      short loc_18003357A
0x18003356e  call    cs:__imp_SRCacheManager_Close
0x180033575  nop     dword ptr [rax+rax+00h]
0x18003357a  mov     eax, ebx
0x18003357c  jmp     loc_18003393F
0x180033581  mov     dl, 1
0x180033583  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x18003358a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003358f  mov     rdx, [rbp+120h+var_1A0]
0x180033593  lea     r9, [rbp+120h+var_180]
0x180033597  xor     eax, eax
0x180033599  lea     rcx, [rsp+220h+var_1C8]
0x18003359e  xorps   xmm0, xmm0
0x1800335a1  mov     [rbp+120h+var_170], rax
0x1800335a5  mov     [rbp+120h+var_168], rax
0x1800335a9  mov     r8d, 21Ah
0x1800335af  mov     [rbp+120h+var_160], rax
0x1800335b3  mov     [rbp+120h+var_158], rax
0x1800335b7  mov     [rbp+120h+var_150], rax
0x1800335bb  mov     [rbp+120h+var_148], rax
0x1800335bf  mov     [rbp+120h+var_130], eax
0x1800335c2  mov     [rbp+120h+var_128], rax
0x1800335c6  mov     byte ptr [rsp+220h+var_1D0], al
0x1800335ca  lea     rax, [rsp+220h+var_1D0]
0x1800335cf  mov     qword ptr [rsp+220h+bIgnoreCase], rax; unsigned int
0x1800335d4  movdqa  [rbp+120h+var_180], xmm0
0x1800335d9  movdqa  [rbp+120h+var_140], xmm0
0x1800335de  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1800335e3  mov     ebx, eax
0x1800335e5  test    eax, eax
0x1800335e7  jns     short loc_180033612
0x1800335e9  mov     rcx, [rbp+128h]; this
0x1800335f0  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800335f7  mov     r9d, eax; char *
0x1800335fa  mov     edx, 11D4h; void *
0x1800335ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033604  lea     rcx, [rbp+120h+var_180]; this
0x180033608  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003360d  jmp     loc_18003355E
0x180033612  cmp     byte ptr [rsp+220h+var_1D0], 0
0x180033617  jnz     short loc_18003363B
0x180033619  mov     rcx, [rbp+128h]; this
0x180033620  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033627  mov     r9d, 2; char *
0x18003362d  mov     edx, 11D7h; void *
0x180033632  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033637  mov     ebx, eax
0x180033639  jmp     short loc_180033604
0x18003363b  mov     ecx, dword ptr [rbp+120h+var_168+4]
0x18003363e  test    rdi, rdi
0x180033641  jz      short loc_18003364C
0x180033643  mov     eax, ecx
0x180033645  shr     eax, 0Bh
0x180033648  and     al, 1
0x18003364a  mov     [rdi], al
0x18003364c  xor     edi, edi
0x18003364e  test    rsi, rsi
0x180033651  jz      short loc_18003365C
0x180033653  mov     eax, ecx
0x180033655  shr     eax, 15h
0x180033658  and     al, 1
0x18003365a  mov     [rsi], al
0x18003365c  test    r14, r14
0x18003365f  jz      short loc_18003366B
0x180033661  mov     eax, ecx
0x180033663  shr     eax, 16h
0x180033666  and     al, 1
0x180033668  mov     [r14], al
0x18003366b  mov     esi, 44h ; 'D'
0x180033670  test    r15, r15
0x180033673  jz      loc_180033823
0x180033679  bt      ecx, 0Bh
0x18003367d  jb      loc_18003381F
0x180033683  bt      ecx, 1Ah
0x180033687  jb      loc_18003381F
0x18003368d  cmp     qword ptr [rbp+120h+var_140], rdi
0x180033691  jnz     loc_18003381F
0x180033697  call    IsQueryApplicationCapabilitiesPresent
0x18003369c  test    al, al
0x18003369e  jz      loc_180033823
0x1800336a4  lea     rax, [rsp+220h+var_1C0]
0x1800336a9  mov     [rsp+220h+var_1C0], rdi
0x1800336ae  lea     rcx, [rsp+220h+var_1C0]
0x1800336b3  mov     [rsp+220h+var_1B0], rax
0x1800336b8  mov     [rsp+220h+var_1B8], rdi
0x1800336bd  mov     [rsp+220h+var_1A8], edi
0x1800336c1  mov     [rsp+220h+var_1A4], 1
0x1800336c6  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x1800336cb  mov     rcx, [rbp+120h+var_1A0]
0x1800336cf  lea     r8, [rsp+220h+var_1A8]
0x1800336d4  mov     [rsp+220h+var_1E0], rdi
0x1800336d9  lea     rdx, [rsp+220h+var_1C0]
0x1800336de  mov     [rsp+220h+var_1E8], rdi
0x1800336e3  xor     r9d, r9d
0x1800336e6  mov     [rsp+220h+var_1F0], rdi
0x1800336eb  mov     [rsp+220h+var_1F8], rdi
0x1800336f0  mov     qword ptr [rsp+220h+bIgnoreCase], rdi; int
0x1800336f5  call    cs:__imp_QueryApplicationCapabilities
0x1800336fc  nop     dword ptr [rax+rax+00h]
0x180033701  mov     ebx, eax
0x180033703  cmp     [rsp+220h+var_1A4], dil
0x180033708  jz      short loc_180033717
0x18003370a  mov     rcx, [rsp+220h+var_1B0]
0x18003370f  mov     edx, [rsp+220h+var_1A8]
0x180033713  mov     [rcx+8], rdx
0x180033717  test    ebx, ebx
0x180033719  jns     short loc_180033758
0x18003371b  mov     rcx, [rbp+128h]; this
0x180033722  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033729  mov     r9d, ebx; char *
0x18003372c  mov     edx, 11FEh; void *
0x180033731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033736  lea     rcx, [rsp+220h+var_1C0]
0x18003373b  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x180033740  lea     rcx, [rbp+120h+var_180]; this
0x180033744  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180033749  mov     rcx, [rsp+220h+var_1C8]
0x18003374e  mov     [rsp+220h+var_1C8], rdi
0x180033753  jmp     loc_180033569
0x180033758  xorps   xmm0, xmm0
0x18003375b  lea     rdx, aPackagewritere; "packageWriteRedirectionCompatibilityShi"...
0x180033762  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x180033766  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x18003376a  call    cs:__imp_RtlInitUnicodeString
0x180033771  nop     dword ptr [rax+rax+00h]
0x180033776  mov     r8, rsi; Size
0x180033779  lea     rcx, [rbp+120h+pSid2]; void *
0x180033780  xor     edx, edx; Val
0x180033782  call    memset_0
0x180033787  mov     r8, rsi; Size
0x18003378a  lea     rcx, [rbp+120h+lpString1]; void *
0x18003378e  xor     edx, edx; Val
0x180033790  call    memset_0
0x180033795  lea     r8, [rbp+120h+pSid2]
0x18003379c  lea     rdx, [rbp+120h+lpString1]
0x1800337a0  lea     rcx, [rbp+120h+DestinationString]
0x1800337a4  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800337ab  nop     dword ptr [rax+rax+00h]
0x1800337b0  test    eax, eax
0x1800337b2  jns     short loc_1800337D6
0x1800337b4  mov     rcx, [rbp+128h]; this
0x1800337bb  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800337c2  mov     r9d, eax; char *
0x1800337c5  mov     edx, 120Ah; void *
0x1800337ca  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800337cf  mov     ebx, eax
0x1800337d1  jmp     loc_180033736
0x1800337d6  mov     ebx, edi
0x1800337d8  cmp     [rsp+220h+var_1B8], rdi
0x1800337dd  jbe     short loc_180033813
0x1800337df  mov     rax, rdi
0x1800337e2  mov     rcx, [rsp+220h+var_1C0]
0x1800337e7  lea     rdx, [rbp+120h+pSid2]; pSid2
0x1800337ee  mov     rcx, [rcx+rax*8]; pSid1
0x1800337f2  call    cs:__imp_EqualSid
0x1800337f9  nop     dword ptr [rax+rax+00h]
0x1800337fe  test    eax, eax
0x180033800  jnz     short loc_18003380F
0x180033802  inc     ebx
0x180033804  mov     eax, ebx
0x180033806  cmp     rax, [rsp+220h+var_1B8]
0x18003380b  jb      short loc_1800337E2
0x18003380d  jmp     short loc_180033813
0x18003380f  mov     byte ptr [r15], 1
0x180033813  lea     rcx, [rsp+220h+var_1C0]
0x180033818  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x18003381d  jmp     short loc_180033823
0x18003381f  mov     byte ptr [r15], 1
0x180033823  test    r13, r13
0x180033826  jz      short loc_180033834
0x180033828  mov     eax, dword ptr [rbp+120h+var_160]
0x18003382b  shr     eax, 0Fh
0x18003382e  and     al, 1
0x180033830  mov     [r13+0], al
0x180033834  mov     rbx, [rbp+120h+var_198]
0x180033838  test    rbx, rbx
0x18003383b  jz      loc_1800338CF
0x180033841  mov     dl, 1
0x180033843  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x18003384a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003384f  xorps   xmm0, xmm0
0x180033852  lea     rcx, [rbp+120h+var_100]; void *
0x180033856  mov     r8, rsi; Size
0x180033859  movdqa  xmmword ptr [rbp+120h+lpString1], xmm0
0x18003385e  xor     edx, edx; Val
0x180033860  call    memset_0
0x180033865  mov     rdx, [rbp+120h+var_170]
0x180033869  lea     rax, [rsp+220h+var_1D0]
0x18003386e  lea     r9, [rbp+120h+lpString1]
0x180033872  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x180033877  lea     rcx, [rsp+220h+var_1C8]
0x18003387c  mov     [rbp+120h+var_B8], rdi
0x180033880  mov     [rbp+120h+var_B0], rdi
0x180033884  mov     byte ptr [rsp+220h+var_1D0], dil
0x180033889  call    ?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x18003388e  test    eax, eax
0x180033890  js      short loc_1800338C6
0x180033892  cmp     byte ptr [rsp+220h+var_1D0], dil
0x180033897  jz      short loc_1800338C6
0x180033899  mov     rcx, [rbp+120h+lpString1+8]; lpString1
0x18003389d  lea     r8, aMicrosoftwindo; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x1800338a4  or      edx, 0FFFFFFFFh; cchCount1
0x1800338a7  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x1800338af  mov     r9d, edx; cchCount2
0x1800338b2  call    cs:__imp_CompareStringOrdinal
0x1800338b9  nop     dword ptr [rax+rax+00h]
0x1800338be  cmp     eax, 2
0x1800338c1  setz    al
0x1800338c4  mov     [rbx], al
0x1800338c6  lea     rcx, [rbp+120h+lpString1]; this
0x1800338ca  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800338cf  test    r12, r12
0x1800338d2  jz      short loc_1800338F6
0x1800338d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x1800338db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x1800338e0  test    al, al
0x1800338e2  jz      short loc_1800338F2
0x1800338e4  mov     eax, dword ptr [rbp+120h+var_160]
0x1800338e7  shr     eax, 15h
0x1800338ea  and     al, 1
0x1800338ec  mov     [r12], al
0x1800338f0  jmp     short loc_1800338F6
0x1800338f2  mov     [r12], dil
0x1800338f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA> `wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl(void)'::`2'::impl
0x1800338fd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(void)
0x180033902  test    al, al
0x180033904  jz      short loc_180033919
0x180033906  mov     rcx, [rbp+120h+var_190]
0x18003390a  test    rcx, rcx
0x18003390d  jz      short loc_180033919
0x18003390f  mov     eax, dword ptr [rbp+120h+var_168+4]
0x180033912  shr     eax, 1Ch
0x180033915  and     al, 1
0x180033917  mov     [rcx], al
0x180033919  lea     rcx, [rbp+120h+var_180]; this
0x18003391d  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180033922  mov     rcx, [rsp+220h+var_1C8]
0x180033927  mov     [rsp+220h+var_1C8], rdi
0x18003392c  test    rcx, rcx
0x18003392f  jz      short loc_18003393D
0x180033931  call    cs:__imp_SRCacheManager_Close
0x180033938  nop     dword ptr [rax+rax+00h]
0x18003393d  xor     eax, eax
0x18003393f  mov     rcx, [rbp+120h+var_50]
0x180033946  xor     rcx, rsp; StackCookie
0x180033949  call    __security_check_cookie
0x18003394e  add     rsp, 1E8h
0x180033955  pop     r15
0x180033957  pop     r14
0x180033959  pop     r13
0x18003395b  pop     r12
0x18003395d  pop     rdi
0x18003395e  pop     rsi
0x18003395f  pop     rbx
0x180033960  pop     rbp
0x180033961  retn
```
