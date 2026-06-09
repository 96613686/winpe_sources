# Mso::Experiment::ABConfigsCache::EcsConfigToRead(void)

- ea: `0x180035da0`
- end: `0x18003688e`
- name: `?EcsConfigToRead@ABConfigsCache@Experiment@Mso@@AEAA?AV?$Persistent@UEcsConfigResponseData@ABConfigsCache@Experiment@Mso@@@3@XZ`
- size: `2798`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036890`

## callees

- `0x18000e400`
- `0x1800124f0`
- `0x180012a50`
- `0x180012aa0`
- `0x180012ccc`
- `0x180013080`
- `0x180014ac8`
- `0x18001f428`
- `0x1800316f8`
- `0x180031adc`
- `0x180031ce8`
- `0x180031dc0`
- `0x180035750`
- `0x180035da0`
- `0x1800385f4`
- `0x180038f10`
- `0x1800390f4`
- `0x180069408`
- `0x18006cac0`
- `0x1800b525c`
- `0x1800b53d0`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180035fa3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180036006`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800360c1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800362b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003650c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003656d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003661e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003670d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180036758`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800367ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180035fa3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180036006`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800360c1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800362b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003650c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003656d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003661e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003670d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180036758`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800367ab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180035fff`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180036566`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800367a4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18003687a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180035fff`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180036566`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800367a4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18003687a`
- `api-ms-win-crt-time-l1-1-0!_difftime64` at `0x1800360f1`
- `api-ms-win-crt-time-l1-1-0!_difftime64` at `0x180036401`
- `api-ms-win-crt-time-l1-1-0!_difftime64` at `0x1800360f1`
- `api-ms-win-crt-time-l1-1-0!_difftime64` at `0x180036401`

## string_xrefs

- `0x18003625d`: `ConfigContextData`
- `0x1800365e8`: `ConfigContextData`
- `0x180036810`: `ConfigContextData`
- `0x180035ed0`: `Microsoft.Office.Experimentation.Configs.FirstSessionPersistentStore`
- `0x180036134`: `Microsoft.Office.Experimentation.Configs.FirstSessionPersistentStore`
- `0x180035e77`: `Microsoft.Office.Experimentation.Configs.FirstSessionUpgradeCandidatePersistentStore`
- `0x180036446`: `Microsoft.Office.Experimentation.Configs.FirstSessionUpgradeCandidatePersistentStore`
- `0x180035e63`: `Microsoft.Office.Experimentation.Configs.ApplicationUpgradeCandidatePersistentStore`
- `0x180036646`: `Microsoft.Office.Experimentation.Configs.ApplicationUpgradeCandidatePersistentStore`
- `0x1800367c4`: `ApplicationUpgradeCandidateCacheUsed`
- `0x180036210`: `FirstSessionCacheUsed`
- `0x180036306`: `FirstSessionCacheUsed`
- `0x180035e29`: `LoadingFirstSessionCache`
- `0x18003659b`: `FirstSessionUpgradeCandidateCacheUsed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::Experiment::ABConfigsCache::EcsConfigToRead(__int64 a1, __int64 a2)
{
  struct Mso::Telemetry::IActivityParenter *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  void *v7; // rcx
  __m128i v8; // xmm6
  void *v9; // rcx
  __time64_t v10; // rcx
  void *v11; // rcx
  __time64_t v12; // r12
  __time64_t v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  __int64 *v19; // rcx
  volatile signed __int32 *v20; // rdi
  __int64 v22; // rax
  __int64 v23; // rax
  void *v24; // rcx
  __m128i si128; // xmm6
  void *v26; // rcx
  __int64 v27; // rax
  char *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  void *v31; // rcx
  __m128i v32; // xmm6
  void *v33; // rcx
  void *v34; // rcx
  char *v35; // rdx
  __int64 v36; // [rsp+40h] [rbp-C8h] BYREF
  __time64_t Time1; // [rsp+48h] [rbp-C0h]
  char v38[8]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v39; // [rsp+60h] [rbp-A8h] BYREF
  __time64_t Time2_8[2]; // [rsp+70h] [rbp-98h]
  __int128 v41; // [rsp+80h] [rbp-88h] BYREF
  __int128 v42; // [rsp+90h] [rbp-78h]
  __int128 v43; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v44; // [rsp+B0h] [rbp-58h]
  void *v45[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v46; // [rsp+D0h] [rbp-38h]
  void *Block[2]; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v48; // [rsp+F0h] [rbp-18h]
  __int128 v49; // [rsp+100h] [rbp-8h] BYREF
  __m128i v50; // [rsp+110h] [rbp+8h]
  __int128 v51; // [rsp+120h] [rbp+18h] BYREF
  __m128i v52; // [rsp+130h] [rbp+28h]
  void *v53[2]; // [rsp+140h] [rbp+38h] BYREF
  __m128i v54; // [rsp+150h] [rbp+48h]
  __int128 v55; // [rsp+160h] [rbp+58h] BYREF
  __m128i v56; // [rsp+170h] [rbp+68h]
  __int128 Src; // [rsp+180h] [rbp+78h] BYREF
  __int128 v58; // [rsp+190h] [rbp+88h]
  _BYTE v59[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v60; // [rsp+1C8h] [rbp+C0h]
  char v61; // [rsp+1D0h] [rbp+C8h]
  __m128i v62; // [rsp+1D8h] [rbp+D0h] BYREF
  _OWORD v63[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  _OWORD v64[2]; // [rsp+208h] [rbp+100h] BYREF
  char v65[8]; // [rsp+228h] [rbp+120h] BYREF
  _BYTE v66[424]; // [rsp+230h] [rbp+128h] BYREF

  if ( !Mso::AB::Plat::Win32 )
    CrashWithRecovery(0x1E3C3840u, 0);
  if ( !((unsigned __int8 (__fastcall *)(void ***))(*Mso::AB::Plat::Win32)[3])(Mso::AB::Plat::Win32) )
    goto LABEL_37;
  v36 = 0x64000201010101LL;
  *(_QWORD *)&v39 = &off_1805BCED0;
  *((_QWORD *)&v39 + 1) = "LoadingFirstSessionCache";
  v4 = Mso::Telemetry::Activity::UseThreadCurrentParenter();
  Mso::Telemetry::Activity::Activity(v38, &v39, v4, 256, &v36);
  Mso::Experiment::ABConfigsCache::IsUpgradeCandidateCacheValid(
    a1,
    &v39,
    L"Microsoft.Office.Experimentation.Configs.ApplicationUpgradeCandidatePersistentStore");
  Mso::Experiment::ABConfigsCache::IsUpgradeCandidateCacheValid(
    a1,
    &v36,
    L"Microsoft.Office.Experimentation.Configs.FirstSessionUpgradeCandidatePersistentStore");
  if ( (_BYTE)v36 || (_BYTE)v39 )
  {
    *(_BYTE *)(a1 + 1032) = 1;
    if ( _difftime64(Time1, *((__time64_t *)&v39 + 1)) > 0.0 )
    {
      memset(v64, 0, sizeof(v64));
      std::wstring::_Construct<1,wchar_t *>(v64, L".", 1);
      v22 = std::wstring::insert(v64);
      *(_OWORD *)v53 = 0;
      v54 = 0;
      *(_OWORD *)v53 = *(_OWORD *)v22;
      v54 = *(__m128i *)(v22 + 16);
      *(_WORD *)v22 = 0;
      *(_QWORD *)(v22 + 16) = 0;
      *(_QWORD *)(v22 + 24) = 7;
      v23 = std::wstring::append(v53);
      v51 = 0;
      v52 = 0;
      v51 = *(_OWORD *)v23;
      v52 = *(__m128i *)(v23 + 16);
      *(_WORD *)v23 = 0;
      *(_QWORD *)(v23 + 16) = 0;
      *(_QWORD *)(v23 + 24) = 7;
      Mso::GetVersionedRegistryStore(&v39, &v51);
      if ( v52.m128i_i64[1] > 7uLL )
      {
        v24 = (void *)v51;
        if ( (unsigned __int64)(2 * v52.m128i_i64[1] + 2) >= 0x1000 )
        {
          v24 = *(void **)(v51 - 8);
          if ( (unsigned __int64)(v51 - (_QWORD)v24 - 8) > 0x1F )
LABEL_47:
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v24);
      }
      *(_QWORD *)&v51 = 19937;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v52 = si128;
      if ( v54.m128i_i64[1] > 7uLL )
      {
        v26 = v53[0];
        if ( (unsigned __int64)(2 * v54.m128i_i64[1] + 2) >= 0x1000 )
        {
          v26 = (void *)*((_QWORD *)v53[0] - 1);
          if ( (unsigned __int64)((char *)v53[0] - (char *)v26 - 8) > 0x1F )
            goto LABEL_47;
        }
        free(v26);
      }
      v53[0] = (void *)19937;
      v54 = si128;
      std::wstring::~wstring(v64);
      Mso::Telemetry::CreateResult((unsigned int)v65, 1, (unsigned int)"FirstSessionUpgradeCandidateCacheUsed", 0, 0);
      Mso::Telemetry::Activity::SetResult(
        (Mso::Telemetry::Activity *)v38,
        1,
        (const struct Office::System::Result *)v65);
      Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v66);
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v41, L"ConfigContextData", 17);
      Mso::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>(
        a2,
        &v41,
        &v39);
      v27 = *((_QWORD *)&v42 + 1);
      if ( *((_QWORD *)&v42 + 1) <= 7u )
      {
LABEL_52:
        v19 = (__int64 *)&v39;
        goto LABEL_31;
      }
      v28 = (char *)v41;
LABEL_68:
      v35 = v28;
      if ( (unsigned __int64)(2 * v27 + 2) >= 0x1000 )
      {
        v28 = (char *)*((_QWORD *)v28 - 1);
        if ( (unsigned __int64)(v35 - v28 - 8) > 0x1F )
          goto LABEL_70;
      }
      free(v28);
      goto LABEL_52;
    }
    *(_OWORD *)v45 = 0;
    v46 = 0;
    std::wstring::_Construct<1,wchar_t *>(v45, L".", 1);
    v29 = std::wstring::insert(v45);
    v43 = 0;
    v44 = 0;
    v43 = *(_OWORD *)v29;
    v44 = *(__m128i *)(v29 + 16);
    *(_WORD *)v29 = 0;
    *(_QWORD *)(v29 + 16) = 0;
    *(_QWORD *)(v29 + 24) = 7;
    v30 = std::wstring::append(&v43);
    v55 = 0;
    v56 = 0;
    v55 = *(_OWORD *)v30;
    v56 = *(__m128i *)(v30 + 16);
    *(_WORD *)v30 = 0;
    *(_QWORD *)(v30 + 16) = 0;
    *(_QWORD *)(v30 + 24) = 7;
    Mso::GetVersionedRegistryStore(&v39, &v55);
    if ( v56.m128i_i64[1] > 7uLL )
    {
      v31 = (void *)v55;
      if ( (unsigned __int64)(2 * v56.m128i_i64[1] + 2) >= 0x1000 )
      {
        v31 = *(void **)(v55 - 8);
        if ( (unsigned __int64)(v55 - (_QWORD)v31 - 8) > 0x1F )
          goto LABEL_64;
      }
      free(v31);
    }
    *(_QWORD *)&v55 = 19937;
    v32 = _mm_load_si128((const __m128i *)&_xmm);
    v56 = v32;
    if ( v44.m128i_i64[1] <= 7uLL )
      goto LABEL_61;
    v33 = (void *)v43;
    if ( (unsigned __int64)(2 * v44.m128i_i64[1] + 2) < 0x1000
      || (v33 = *(void **)(v43 - 8), (unsigned __int64)(v43 - (_QWORD)v33 - 8) <= 0x1F) )
    {
      free(v33);
LABEL_61:
      *(_QWORD *)&v43 = 19937;
      v44 = v32;
      if ( *((_QWORD *)&v46 + 1) > 7u )
      {
        v34 = v45[0];
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v46 + 1) + 2) >= 0x1000 )
        {
          v34 = (void *)*((_QWORD *)v45[0] - 1);
          if ( (unsigned __int64)((char *)v45[0] - (char *)v34 - 8) > 0x1F )
            goto LABEL_64;
        }
        free(v34);
      }
      Mso::Telemetry::CreateResult((unsigned int)v65, 1, (unsigned int)"ApplicationUpgradeCandidateCacheUsed", 0, 0);
      Mso::Telemetry::Activity::SetResult(
        (Mso::Telemetry::Activity *)v38,
        1,
        (const struct Office::System::Result *)v65);
      Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v66);
      *(_OWORD *)v45 = 0;
      v46 = 0;
      std::wstring::_Construct<1,wchar_t *>(v45, L"ConfigContextData", 17);
      Mso::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>(
        a2,
        v45,
        &v39);
      v27 = *((_QWORD *)&v46 + 1);
      if ( *((_QWORD *)&v46 + 1) <= 7u )
        goto LABEL_52;
      v28 = (char *)v45[0];
      goto LABEL_68;
    }
LABEL_64:
    _invoke_watson(0, 0, 0, 0, 0);
  }
  memset(v63, 0, sizeof(v63));
  std::wstring::_Construct<1,wchar_t *>(v63, L".", 1);
  v5 = std::wstring::insert(v63);
  *(_OWORD *)Block = 0;
  v48 = 0;
  *(_OWORD *)Block = *(_OWORD *)v5;
  v48 = *(__m128i *)(v5 + 16);
  *(_WORD *)v5 = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 7;
  v6 = std::wstring::append(Block);
  v39 = 0;
  *(_OWORD *)Time2_8 = 0;
  v39 = *(_OWORD *)v6;
  *(_OWORD *)Time2_8 = *(_OWORD *)(v6 + 16);
  *(_WORD *)v6 = 0;
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  Mso::GetRegistryStoreFromContext(&v36, qword_1806BB348, &v39);
  if ( Time2_8[1] > 7uLL )
  {
    v7 = (void *)v39;
    if ( (unsigned __int64)(2 * Time2_8[1] + 2) >= 0x1000 )
    {
      v7 = *(void **)(v39 - 8);
      if ( (unsigned __int64)(v39 - (_QWORD)v7 - 8) > 0x1F )
LABEL_12:
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v7);
  }
  *(_QWORD *)&v39 = 19937;
  v8 = _mm_load_si128((const __m128i *)&_xmm);
  *(__m128i *)Time2_8 = v8;
  if ( v48.m128i_i64[1] > 7uLL )
  {
    v9 = Block[0];
    if ( (unsigned __int64)(2 * v48.m128i_i64[1] + 2) >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
        goto LABEL_12;
    }
    free(v9);
  }
  Block[0] = (void *)19937;
  v48 = v8;
  std::wstring::~wstring(v63);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v43, L"Expires", 7);
  std::wstring::wstring(v59, &v43);
  v60 = 0;
  v61 = 1;
  v62 = 0;
  v10 = Time1;
  if ( Time1 )
    _InterlockedAdd((volatile signed __int32 *)(Time1 + 8), 1u);
  v62.m128i_i64[0] = v36;
  v62.m128i_i64[1] = v10;
  if ( v44.m128i_i64[1] > 7uLL )
  {
    v11 = (void *)v43;
    if ( (unsigned __int64)(2 * v44.m128i_i64[1] + 2) >= 0x1000 )
    {
      v11 = *(void **)(v43 - 8);
      if ( (unsigned __int64)(v43 - (_QWORD)v11 - 8) > 0x1F )
        goto LABEL_70;
    }
    free(v11);
  }
  v12 = Mso::Persistent<__int64>::operator __int64(v59);
  if ( !v12 || (v13 = Mso::Persistent<__int64>::operator __int64(a1 + 696), _difftime64(v12, v13) <= 0.0) )
  {
    Mso::Telemetry::CreateResult((unsigned int)v65, 0, (unsigned int)"FirstSessionCacheUsed", 0, 0);
    Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v38, 0, (const struct Office::System::Result *)v65);
    Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v66);
    v20 = (volatile signed __int32 *)v62.m128i_i64[1];
    if ( v62.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v62.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v62 = _mm_load_si128((const __m128i *)&_xmm);
    std::wstring::~wstring(v59);
    std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(&v36);
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v38);
LABEL_37:
    Mso::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>(
      a2,
      a1 + 760);
    return a2;
  }
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v41, L".", 1);
  v14 = std::wstring::insert(&v41);
  Src = 0;
  v58 = 0;
  Src = *(_OWORD *)v14;
  v58 = *(_OWORD *)(v14 + 16);
  *(_WORD *)v14 = 0;
  *(_QWORD *)(v14 + 16) = 0;
  *(_QWORD *)(v14 + 24) = 7;
  v15 = std::wstring::append(&Src);
  v49 = 0;
  v50 = 0;
  v49 = *(_OWORD *)v15;
  v50 = *(__m128i *)(v15 + 16);
  *(_WORD *)v15 = 0;
  *(_QWORD *)(v15 + 16) = 0;
  *(_QWORD *)(v15 + 24) = 7;
  Mso::GetVersionedRegistryStore(&v39, &v49);
  if ( v50.m128i_i64[1] > 7uLL )
    std::wstring::_Deallocate_for_capacity(v16, v49);
  *(_QWORD *)&v49 = 19937;
  v50 = v8;
  std::wstring::~wstring(&Src);
  if ( *((_QWORD *)&v42 + 1) > 7u )
    std::wstring::_Deallocate_for_capacity(v17, v41);
  Mso::Telemetry::CreateResult((unsigned int)v65, 1, (unsigned int)"FirstSessionCacheUsed", 0, 0);
  Mso::Telemetry::Activity::SetResult((Mso::Telemetry::Activity *)v38, 1, (const struct Office::System::Result *)v65);
  Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v66);
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v41, L"ConfigContextData", 17);
  Mso::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>(
    a2,
    &v41,
    &v39);
  if ( *((_QWORD *)&v42 + 1) <= 7u )
    goto LABEL_30;
  v18 = (void *)v41;
  if ( (unsigned __int64)(2LL * *((_QWORD *)&v42 + 1) + 2) >= 0x1000 )
  {
    v18 = *(void **)(v41 - 8);
    if ( (unsigned __int64)(v41 - (_QWORD)v18 - 8) > 0x1F )
LABEL_70:
      _invoke_watson(0, 0, 0, 0, 0);
  }
  free(v18);
LABEL_30:
  std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(&v39);
  std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(&v62);
  std::wstring::~wstring(v59);
  v19 = &v36;
LABEL_31:
  std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v19);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v38);
  return a2;
}

```

## disassembly

```asm
0x180035da0  mov     rax, rsp
0x180035da3  mov     [rax+18h], rbx
0x180035da7  push    rbp
0x180035da8  push    rsi
0x180035da9  push    rdi
0x180035daa  push    r12
0x180035dac  push    r13
0x180035dae  push    r14
0x180035db0  push    r15
0x180035db2  lea     rbp, [rax-328h]
0x180035db9  sub     rsp, 3F0h
0x180035dc0  movaps  xmmword ptr [rax-48h], xmm6
0x180035dc4  mov     rax, cs:__security_cookie
0x180035dcb  xor     rax, rsp
0x180035dce  mov     [rbp+320h+var_50], rax
0x180035dd5  mov     r15, rdx
0x180035dd8  mov     rbx, rcx
0x180035ddb  mov     rcx, cs:?Win32@Plat@AB@Mso@@3U?$Scope_t@_N@23@B; Mso::AB::Scope_t<bool> const Mso::AB::Plat::Win32
0x180035de2  xor     r13d, r13d
0x180035de5  test    rcx, rcx
0x180035de8  jz      loc_180036881
0x180035dee  mov     rax, [rcx]
0x180035df1  mov     rax, [rax+18h]
0x180035df5  call    cs:__guard_dispatch_icall_fptr
0x180035dfb  test    al, al
0x180035dfd  jz      loc_1800363AF
0x180035e03  lea     r12d, [r13+1]
0x180035e07  mov     word ptr [rsp+420h+var_3E8], 101h
0x180035e0e  mov     dword ptr [rsp+420h+var_3E8+2], 20101h
0x180035e16  mov     word ptr [rsp+420h+var_3E8+6], 64h ; 'd'
0x180035e1d  lea     rax, off_1805BCED0
0x180035e24  mov     qword ptr [rsp+420h+var_3D0+8], rax
0x180035e29  lea     rax, aLoadingfirstse; "LoadingFirstSessionCache"
0x180035e30  mov     [rsp+420h+Time2], rax
0x180035e35  mov     word ptr [rsp+420h+var_3F0], 100h
0x180035e3c  call    ?UseThreadCurrentParenter@Activity@Telemetry@Mso@@SAAEAUIActivityParenter@23@XZ; Mso::Telemetry::Activity::UseThreadCurrentParenter(void)
0x180035e41  lea     rcx, [rsp+420h+var_3E8]
0x180035e46  mov     [rsp+420h+Reserved], rcx
0x180035e4b  movzx   r9d, word ptr [rsp+420h+var_3F0]
0x180035e51  mov     r8, rax
0x180035e54  lea     rdx, [rsp+420h+var_3D0+8]
0x180035e59  lea     rcx, [rsp+420h+var_3D8]
0x180035e5e  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::IActivityParenter const &,Mso::Telemetry::ActivityAggregation,Mso::Telemetry::EventFlags const &)
0x180035e63  lea     r8, aMicrosoftOffic_63; "Microsoft.Office.Experimentation.Config"...
0x180035e6a  lea     rdx, [rsp+420h+var_3D0+8]
0x180035e6f  mov     rcx, rbx
0x180035e72  call    ?IsUpgradeCandidateCacheValid@ABConfigsCache@Experiment@Mso@@AEAA?AU?$pair@_N_J@std@@PEB_W@Z; Mso::Experiment::ABConfigsCache::IsUpgradeCandidateCacheValid(wchar_t const *)
0x180035e77  lea     r8, aMicrosoftOffic_127; "Microsoft.Office.Experimentation.Config"...
0x180035e7e  lea     rdx, [rsp+420h+var_3E8]
0x180035e83  mov     rcx, rbx
0x180035e86  call    ?IsUpgradeCandidateCacheValid@ABConfigsCache@Experiment@Mso@@AEAA?AU?$pair@_N_J@std@@PEB_W@Z; Mso::Experiment::ABConfigsCache::IsUpgradeCandidateCacheValid(wchar_t const *)
0x180035e8b  cmp     byte ptr [rsp+420h+var_3E8], r13b
0x180035e90  jnz     loc_1800363F0
0x180035e96  cmp     byte ptr [rsp+420h+var_3D0+8], r13b
0x180035e9b  jnz     loc_1800363F0
0x180035ea1  xorps   xmm0, xmm0
0x180035ea4  movups  [rbp+320h+var_240], xmm0
0x180035eab  xorps   xmm1, xmm1
0x180035eae  movdqu  [rbp+320h+var_230], xmm1
0x180035eb6  mov     r8d, r12d
0x180035eb9  lea     rdx, S; "."
0x180035ec0  lea     rcx, [rbp+320h+var_240]
0x180035ec7  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180035ecc  lea     r9d, [r13+44h]
0x180035ed0  lea     r8, aMicrosoftOffic; "Microsoft.Office.Experimentation.Config"...
0x180035ed7  lea     rcx, [rbp+320h+var_240]; Src
0x180035ede  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x180035ee3  xorps   xmm0, xmm0
0x180035ee6  movups  xmmword ptr [rbp+320h+Block], xmm0
0x180035eea  xorps   xmm1, xmm1
0x180035eed  movdqu  [rbp+320h+var_338], xmm1
0x180035ef2  movups  xmm0, xmmword ptr [rax]
0x180035ef5  movups  xmmword ptr [rbp+320h+Block], xmm0
0x180035ef9  movups  xmm1, xmmword ptr [rax+10h]
0x180035efd  movups  [rbp+320h+var_338], xmm1
0x180035f01  mov     [rax], r13w
0x180035f05  mov     [rax+10h], r13
0x180035f09  lea     edi, [r13+7]
0x180035f0d  mov     [rax+18h], rdi
0x180035f11  mov     rdx, rbx
0x180035f14  cmp     [rbx+18h], rdi
0x180035f18  jbe     short loc_180035F1D
0x180035f1a  mov     rdx, [rbx]
0x180035f1d  mov     r8, [rbx+10h]
0x180035f21  lea     rcx, [rbp+320h+Block]; Src
0x180035f25  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180035f2a  xorps   xmm0, xmm0
0x180035f2d  movups  [rsp+420h+var_3D0+8], xmm0
0x180035f32  xorps   xmm1, xmm1
0x180035f35  movdqu  xmmword ptr [rsp+420h+Time2+8], xmm1
0x180035f3b  movups  xmm0, xmmword ptr [rax]
0x180035f3e  movups  [rsp+420h+var_3D0+8], xmm0
0x180035f43  movups  xmm1, xmmword ptr [rax+10h]
0x180035f47  movups  xmmword ptr [rsp+420h+Time2+8], xmm1
0x180035f4c  mov     [rax], r13w
0x180035f50  mov     [rax+10h], r13
0x180035f54  mov     [rax+18h], rdi
0x180035f58  lea     r8, [rsp+420h+var_3D0+8]
0x180035f5d  mov     rdx, cs:qword_1806BB348
0x180035f64  lea     rcx, [rsp+420h+var_3E8]
0x180035f69  call    ?GetRegistryStoreFromContext@Mso@@YA?AV?$shared_ptr@VIPersistentStore@Mso@@@std@@AEBUIConfigContext@Experiment@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Mso::GetRegistryStoreFromContext(Mso::Experiment::IConfigContext const &,std::wstring const &)
0x180035f6e  mov     esi, 1000h
0x180035f73  mov     rax, qword ptr [rsp+420h+var_3B0]
0x180035f78  cmp     rax, rdi
0x180035f7b  jbe     short loc_180035FA9
0x180035f7d  mov     rcx, qword ptr [rsp+420h+var_3D0+8]
0x180035f82  mov     rdx, rcx
0x180035f85  lea     rax, ds:2[rax*2]
0x180035f8d  cmp     rax, rsi
0x180035f90  jb      short loc_180035FA3
0x180035f92  mov     rcx, [rcx-8]; Block
0x180035f96  sub     rdx, rcx
0x180035f99  lea     rax, [rdx-8]
0x180035f9d  cmp     rax, 1Fh
0x180035fa1  ja      short loc_180035FF0
0x180035fa3  call    cs:__imp_free
0x180035fa9  mov     r14d, 4DE1h
0x180035faf  mov     qword ptr [rsp+420h+var_3D0+8], r14
0x180035fb4  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x180035fbc  movdqu  xmmword ptr [rsp+420h+Time2+8], xmm6
0x180035fc2  mov     rax, qword ptr [rbp+320h+var_338+8]
0x180035fc6  cmp     rax, rdi
0x180035fc9  jbe     short loc_18003600C
0x180035fcb  mov     rcx, [rbp+320h+Block]; Block
0x180035fcf  mov     rdx, rcx
0x180035fd2  lea     rax, ds:2[rax*2]
0x180035fda  cmp     rax, rsi
0x180035fdd  jb      short loc_180036006
0x180035fdf  mov     rcx, [rcx-8]
0x180035fe3  sub     rdx, rcx
0x180035fe6  lea     rax, [rdx-8]
0x180035fea  cmp     rax, 1Fh
0x180035fee  jbe     short loc_180036006
0x180035ff0  mov     [rsp+420h+Reserved], r13; Reserved
0x180035ff5  xor     r9d, r9d; LineNo
0x180035ff8  xor     r8d, r8d; FileName
0x180035ffb  xor     edx, edx; FunctionName
0x180035ffd  xor     ecx, ecx; Expression
0x180035fff  call    cs:__imp__invoke_watson
0x180036006  call    cs:__imp_free
0x18003600c  mov     [rbp+320h+Block], r14
0x180036010  movdqu  [rbp+320h+var_338], xmm6
0x180036015  lea     rcx, [rbp+320h+var_240]; void *
0x18003601c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036021  xorps   xmm0, xmm0
0x180036024  movups  [rbp+320h+var_388], xmm0
0x180036028  xorps   xmm1, xmm1
0x18003602b  movdqu  [rbp+320h+var_378], xmm1
0x180036030  mov     r8, rdi
0x180036033  lea     rdx, aExpires; "Expires"
0x18003603a  lea     rcx, [rbp+320h+var_388]
0x18003603e  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180036043  nop
0x180036044  lea     rdx, [rbp+320h+var_388]
0x180036048  lea     rcx, [rbp+320h+var_280]
0x18003604f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180036054  mov     [rbp+320h+var_260], r13
0x18003605b  mov     [rbp+320h+var_258], r12b
0x180036062  xorps   xmm0, xmm0
0x180036065  movdqa  [rbp+320h+var_250], xmm0
0x18003606d  mov     rcx, [rsp+420h+Time1]
0x180036072  test    rcx, rcx
0x180036075  jz      short loc_18003607C
0x180036077  lock add [rcx+8], r12d
0x18003607c  mov     rax, [rsp+420h+var_3E8]
0x180036081  mov     qword ptr [rbp+320h+var_250], rax
0x180036088  mov     qword ptr [rbp+320h+var_250+8], rcx
0x18003608f  mov     rax, qword ptr [rbp+320h+var_378+8]
0x180036093  cmp     rax, rdi
0x180036096  jbe     short loc_1800360C7
0x180036098  mov     rcx, qword ptr [rbp+320h+var_388]
0x18003609c  mov     rdx, rcx
0x18003609f  lea     rax, ds:2[rax*2]
0x1800360a7  cmp     rax, rsi
0x1800360aa  jb      short loc_1800360C1
0x1800360ac  mov     rcx, [rcx-8]; Block
0x1800360b0  sub     rdx, rcx
0x1800360b3  lea     rax, [rdx-8]
0x1800360b7  cmp     rax, 1Fh
0x1800360bb  ja      loc_18003686B
0x1800360c1  call    cs:__imp_free
0x1800360c7  lea     rcx, [rbp+320h+var_280]
0x1800360ce  call    ??B?$Persistent@_J@Mso@@QEBA_JXZ; Mso::Persistent<__int64>::operator __int64(void)
0x1800360d3  mov     r12, rax
0x1800360d6  test    rax, rax
0x1800360d9  jz      loc_1800362F4
0x1800360df  lea     rcx, [rbx+2B8h]
0x1800360e6  call    ??B?$Persistent@_J@Mso@@QEBA_JXZ; Mso::Persistent<__int64>::operator __int64(void)
0x1800360eb  mov     rdx, rax; Time2
0x1800360ee  mov     rcx, r12; Time1
0x1800360f1  call    cs:__imp__difftime64
0x1800360f7  comisd  xmm0, cs:__real@0000000000000000
0x1800360ff  jbe     loc_1800362F4
0x180036105  xorps   xmm0, xmm0
0x180036108  movups  xmmword ptr [rsp+420h+var_3B0+8], xmm0
0x18003610d  xorps   xmm1, xmm1
0x180036110  movdqu  [rbp+320h+var_398], xmm1
0x180036115  mov     r12d, 1
0x18003611b  mov     r8d, r12d
0x18003611e  lea     rdx, S; "."
0x180036125  lea     rcx, [rsp+420h+var_3B0+8]
0x18003612a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18003612f  lea     r9d, [r12+43h]
0x180036134  lea     r8, aMicrosoftOffic; "Microsoft.Office.Experimentation.Config"...
0x18003613b  lea     rcx, [rsp+420h+var_3B0+8]; Src
0x180036140  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x180036145  xorps   xmm0, xmm0
0x180036148  movups  [rbp+320h+Src], xmm0
0x18003614c  xorps   xmm1, xmm1
0x18003614f  movdqu  [rbp+320h+var_298], xmm1
0x180036157  movups  xmm0, xmmword ptr [rax]
0x18003615a  movups  [rbp+320h+Src], xmm0
0x18003615e  movups  xmm1, xmmword ptr [rax+10h]
0x180036162  movups  [rbp+320h+var_298], xmm1
0x180036169  mov     [rax], r13w
0x18003616d  mov     [rax+10h], r13
0x180036171  mov     [rax+18h], rdi
0x180036175  mov     r8, [rbx+10h]
0x180036179  cmp     [rbx+18h], rdi
0x18003617d  jbe     short loc_180036182
0x18003617f  mov     rbx, [rbx]
0x180036182  mov     rdx, rbx
0x180036185  lea     rcx, [rbp+320h+Src]; Src
0x180036189  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18003618e  xorps   xmm0, xmm0
0x180036191  movups  [rbp+320h+var_328], xmm0
0x180036195  xorps   xmm1, xmm1
0x180036198  movdqu  [rbp+320h+var_318], xmm1
0x18003619d  movups  xmm0, xmmword ptr [rax]
0x1800361a0  movups  [rbp+320h+var_328], xmm0
0x1800361a4  movups  xmm1, xmmword ptr [rax+10h]
0x1800361a8  movups  [rbp+320h+var_318], xmm1
0x1800361ac  mov     [rax], r13w
0x1800361b0  mov     [rax+10h], r13
0x1800361b4  mov     [rax+18h], rdi
0x1800361b8  lea     rdx, [rbp+320h+var_328]
0x1800361bc  lea     rcx, [rsp+420h+var_3D0+8]
0x1800361c1  call    ?GetVersionedRegistryStore@Mso@@YA?AV?$shared_ptr@VIPersistentStore@Mso@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Mso::GetVersionedRegistryStore(std::wstring const &)
0x1800361c6  mov     r8, qword ptr [rbp+320h+var_318+8]
0x1800361ca  cmp     r8, rdi
0x1800361cd  jbe     short loc_1800361D8
0x1800361cf  mov     rdx, qword ptr [rbp+320h+var_328]
0x1800361d3  call    ?_Deallocate_for_capacity@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAXAEAV?$allocator@_W@2@QEA_W_K@Z; std::wstring::_Deallocate_for_capacity(std::allocator<wchar_t> &,wchar_t * const,unsigned __int64)
0x1800361d8  mov     qword ptr [rbp+320h+var_328], r14
0x1800361dc  movdqu  [rbp+320h+var_318], xmm6
0x1800361e1  lea     rcx, [rbp+320h+Src]; void *
0x1800361e5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800361ea  mov     r8, qword ptr [rbp+320h+var_398+8]
0x1800361ee  cmp     r8, rdi
0x1800361f1  jbe     short loc_1800361FE
0x1800361f3  mov     rdx, qword ptr [rsp+420h+var_3B0+8]
0x1800361f8  call    ?_Deallocate_for_capacity@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAXAEAV?$allocator@_W@2@QEA_W_K@Z; std::wstring::_Deallocate_for_capacity(std::allocator<wchar_t> &,wchar_t * const,unsigned __int64)
0x1800361fd  nop
0x1800361fe  mov     byte ptr [rsp+420h+var_3F0+1], r13b
0x180036203  movzx   eax, word ptr [rsp+420h+var_3F0]
0x180036208  mov     word ptr [rsp+420h+Reserved], ax
0x18003620d  xor     r9d, r9d
0x180036210  lea     r8, aFirstsessionca; "FirstSessionCacheUsed"
0x180036217  mov     edx, r12d
0x18003621a  lea     rcx, [rbp+320h+var_200]
0x180036221  call    ?CreateResult@Telemetry@Mso@@YA?AVResult@System@Office@@HPEBDIV?$optional@_N@std@@@Z; Mso::Telemetry::CreateResult(int,char const *,uint,std::optional<bool>)
0x180036226  nop
0x180036227  lea     r8, [rbp+320h+var_200]; struct Office::System::Result *
0x18003622e  mov     dl, r12b; bool
0x180036231  lea     rcx, [rsp+420h+var_3D8]; this
0x180036236  call    ?SetResult@Activity@Telemetry@Mso@@QEAAX_NAEBVResult@System@Office@@@Z; Mso::Telemetry::Activity::SetResult(bool,Office::System::Result const &)
0x18003623b  lea     rcx, [rbp+320h+var_1F8]; this
0x180036242  call    ??1Fields@Result@System@Office@@QEAA@XZ; Office::System::Result::Fields::~Fields(void)
0x180036247  xorps   xmm0, xmm0
0x18003624a  movups  xmmword ptr [rsp+420h+var_3B0+8], xmm0
0x18003624f  xorps   xmm1, xmm1
0x180036252  movdqu  [rbp+320h+var_398], xmm1
0x180036257  mov     r8d, 11h
0x18003625d  lea     rdx, aConfigcontextd; "ConfigContextData"
0x180036264  lea     rcx, [rsp+420h+var_3B0+8]
0x180036269  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18003626e  lea     r8, [rsp+420h+var_3D0+8]
0x180036273  lea     rdx, [rsp+420h+var_3B0+8]
0x180036278  mov     rcx, r15
0x18003627b  call    ??0?$Persistent@UEcsConfigResponseData@ABConfigsCache@Experiment@Mso@@@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@VIPersistentStore@Mso@@@3@@Z; Mso::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>::Persistent<Mso::Experiment::ABConfigsCache::EcsConfigResponseData>(std::wstring const &,std::shared_ptr<Mso::IPersistentStore> const &)
0x180036280  mov     rax, qword ptr [rbp+320h+var_398+8]
0x180036284  cmp     rax, rdi
0x180036287  jbe     short loc_1800362B9
0x180036289  mov     rcx, qword ptr [rsp+420h+var_3B0+8]
0x18003628e  mov     rdx, rcx
0x180036291  lea     rax, ds:2[rax*2]
0x180036299  cmp     rax, rsi
0x18003629c  jb      short loc_1800362B3
0x18003629e  mov     rcx, [rcx-8]; Block
0x1800362a2  sub     rdx, rcx
0x1800362a5  lea     rax, [rdx-8]
0x1800362a9  cmp     rax, 1Fh
0x1800362ad  ja      loc_18003686B
0x1800362b3  call    cs:__imp_free
0x1800362b9  lea     rcx, [rsp+420h+var_3D0+8]; void *
0x1800362be  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800362c3  lea     rcx, [rbp+320h+var_250]; void *
0x1800362ca  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800362cf  lea     rcx, [rbp+320h+var_280]; void *
0x1800362d6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
