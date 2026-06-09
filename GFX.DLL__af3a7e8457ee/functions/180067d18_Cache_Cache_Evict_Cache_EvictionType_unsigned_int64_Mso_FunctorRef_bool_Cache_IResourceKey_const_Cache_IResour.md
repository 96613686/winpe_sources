# Cache::Cache::Evict(Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)

- ea: `0x180067d18`
- end: `0x18006891c`
- name: `?Evict@Cache@1@QEAA_KW4EvictionType@1@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z`
- size: `3076`
- prototype: `__int64 __fastcall(Cache::Cache *this, int)`
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x1800fce10`

## callees

- `0x180003cc4`
- `0x180004640`
- `0x1800088e0`
- `0x1800089b0`
- `0x18000d7fc`
- `0x18000edd0`
- `0x180056ee0`
- `0x1800573f0`
- `0x180067254`
- `0x1800673a0`
- `0x180067750`
- `0x180067d18`
- `0x180068920`
- `0x180068a10`
- `0x18007aa30`
- `0x180110df8`
- `0x180110f28`
- `0x1801145ec`
- `0x180117294`
- `0x18013e550`
- `0x18014670c`
- `0x18015011c`
- `0x180154e38`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180068274`
- `KERNEL32!GetCurrentThreadId` at `0x180068274`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800683c0`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800683c0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180067f07`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180067f07`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180067f72`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180067f72`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006819f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800681d0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006819f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800681d0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180067f52`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180067f52`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800683ac`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800683ac`

## string_xrefs

- `0x180068289`: `threadID`
- `0x1800682d5`: `cacheType`
- `0x18006842c`: `cacheType`
- `0x180068588`: `cacheType`
- `0x1800687f1`: `cacheType`
- `0x1800685c2`: `Gfx::Cache::Evict status : object is in use and cannot be evict candidate`
- `0x180068466`: `Gfx::Cache::Evict status : object is unreferenced so is a candidate for eviction`
- `0x180068397`: `Gfx::Cache::Evict - Cannot access cache manager`
- `0x18006830f`: `Gfx::Cache::Evict (begin)`
- `0x180068832`: `Gfx::Cache::Evict (end)`
- `0x1800686ce`: `oldCacheSizeBytes`
- `0x180068645`: `newCacheSizeBytes`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Cache::Cache::Evict(Cache::Cache *this, unsigned int a2, __int64 a3, __int64 a4)
{
  void **v4; // rsi
  __int64 v7; // r12
  bool v8; // bl
  __m128i si128; // xmm6
  struct Cache::CacheManager *v10; // r14
  __int64 v11; // r9
  const char *v12; // rax
  _QWORD *v13; // rcx
  void *v14; // rcx
  bool v15; // al
  unsigned __int64 v16; // rax
  char v18; // r10
  unsigned __int64 v19; // rax
  const char *v20; // rax
  const char *v21; // r14
  const struct Mso::IRefCounted *v22; // rdx
  __int64 v23; // rax
  int v24; // ecx
  const char *v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rbx
  unsigned __int128 v28; // kr10_16
  __int64 v29; // rax
  int v30; // edx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rax
  __int64 v35; // rax
  __int16 v36; // r10
  int v37; // edx
  int v38; // r8d
  int v39; // r9d
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // r8d
  int v44; // edx
  int v45; // r9d
  int v46; // edx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  bool v50; // [rsp+60h] [rbp-2C8h]
  const char *v51; // [rsp+68h] [rbp-2C0h] BYREF
  void *Block; // [rsp+70h] [rbp-2B8h] BYREF
  void *v53; // [rsp+78h] [rbp-2B0h]
  __int64 v54; // [rsp+80h] [rbp-2A8h] BYREF
  const char *CachedResourceStateForObject; // [rsp+88h] [rbp-2A0h] BYREF
  unsigned __int128 v56; // [rsp+90h] [rbp-298h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-288h]
  __int64 v58; // [rsp+A8h] [rbp-280h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-278h]
  const char *v60; // [rsp+B8h] [rbp-270h] BYREF
  const char *v61; // [rsp+C0h] [rbp-268h]
  __int64 v62; // [rsp+C8h] [rbp-260h]
  struct Cache::CacheManager *v63; // [rsp+D0h] [rbp-258h]
  unsigned __int64 TotalCacheSize; // [rsp+D8h] [rbp-250h]
  int v65; // [rsp+E0h] [rbp-248h] BYREF
  __int64 v66; // [rsp+E8h] [rbp-240h]
  const char *v67; // [rsp+F0h] [rbp-238h]
  char v68[24]; // [rsp+F8h] [rbp-230h] BYREF
  void **v69; // [rsp+110h] [rbp-218h] BYREF
  const char *v70; // [rsp+118h] [rbp-210h]
  __int64 v71; // [rsp+120h] [rbp-208h]
  __int16 v72; // [rsp+128h] [rbp-200h]
  __int128 v73; // [rsp+130h] [rbp-1F8h] BYREF
  __m128i v74; // [rsp+140h] [rbp-1E8h]
  void **v75; // [rsp+150h] [rbp-1D8h] BYREF
  const char *v76; // [rsp+158h] [rbp-1D0h]
  __int64 v77; // [rsp+160h] [rbp-1C8h]
  __int16 v78; // [rsp+168h] [rbp-1C0h]
  __int128 v79; // [rsp+170h] [rbp-1B8h] BYREF
  __m128i v80; // [rsp+180h] [rbp-1A8h]
  void **v81; // [rsp+190h] [rbp-198h] BYREF
  const char *v82; // [rsp+198h] [rbp-190h]
  const char *v83; // [rsp+1A0h] [rbp-188h]
  _BYTE v84[40]; // [rsp+1A8h] [rbp-180h] BYREF
  void **v85; // [rsp+1D0h] [rbp-158h] BYREF
  const char *v86; // [rsp+1D8h] [rbp-150h]
  __int64 v87; // [rsp+1E0h] [rbp-148h]
  __int16 v88; // [rsp+1E8h] [rbp-140h]
  __int128 v89; // [rsp+1F0h] [rbp-138h] BYREF
  __m128i v90; // [rsp+200h] [rbp-128h]
  _QWORD v91[3]; // [rsp+210h] [rbp-118h] BYREF
  __int16 v92; // [rsp+228h] [rbp-100h]
  _OWORD v93[2]; // [rsp+230h] [rbp-F8h] BYREF
  _QWORD v94[3]; // [rsp+250h] [rbp-D8h] BYREF
  __int16 v95; // [rsp+268h] [rbp-C0h]
  _OWORD v96[2]; // [rsp+270h] [rbp-B8h] BYREF
  _QWORD v97[3]; // [rsp+290h] [rbp-98h] BYREF
  __int16 v98; // [rsp+2A8h] [rbp-80h]
  _OWORD v99[2]; // [rsp+2B0h] [rbp-78h] BYREF

  v4 = (void **)a4;
  v62 = a4;
  v59 = a3;
  v7 = 0;
  if ( byte_18051EEC8 < 0 )
  {
    v8 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18051EEC8);
    v50 = v8;
    a3 = v59;
  }
  else
  {
    v8 = byte_18051EEC8 != 0;
    v50 = byte_18051EEC8 != 0;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v8 )
  {
    v75 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v76 = "evictionGoalBytes";
    v77 = a3;
    v78 = 4;
    v79 = 0;
    v80 = si128;
    LOWORD(v79) = 0;
    v69 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v70 = "evictType";
    v71 = sub_180004640(a2);
    v72 = 4;
    v73 = 0;
    v74 = si128;
    LOWORD(v73) = 0;
    v81 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v82 = "threadID";
    LODWORD(v83) = GetCurrentThreadId();
    WORD2(v83) = 4;
    *(_OWORD *)v84 = 0;
    *(__m128i *)&v84[16] = si128;
    *(_WORD *)v84 = 0;
    v29 = sub_18000D7FC(*((unsigned int *)this + 28));
    v85 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v86 = "cacheType";
    v87 = v29;
    v88 = 4;
    v89 = 0;
    v90 = si128;
    LOWORD(v89) = 0;
    v51 = "Gfx::Cache::Evict (begin)";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      v31,
      v30,
      v32,
      v33,
      (__int64)&v51,
      (__int64)&v85,
      (__int64)&v81,
      (__int64)&v69,
      (__int64)&v75);
    std::wstring::~wstring(&v89);
    std::wstring::~wstring(v84);
    std::wstring::~wstring(&v73);
    std::wstring::~wstring(&v79);
  }
  if ( a2 == 2 )
  {
    if ( !v4 )
    {
      CrashWithRecovery(0x23518716u, 0);
      __debugbreak();
    }
  }
  else if ( a2 == 3 )
  {
    CrashWithRecovery(0x23518715u, 0);
    goto LABEL_44;
  }
  v10 = Cache::CacheManager::PInternalInstance();
  v63 = v10;
  if ( v10 )
  {
    v60 = (const char *)*((_QWORD *)this + 5);
    TotalCacheSize = Cache::Cache::GetTotalCacheSize(this);
    v54 = 0;
    v58 = 0;
    std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>(&Block);
    v4 = (void **)((char *)this + 32);
    if ( a2 == 4 )
    {
      v56 = 0;
      v18 = 0;
      v57 = 0;
      v19 = *((_QWORD *)this + 5);
      v51 = (const char *)v19;
      if ( v19 )
      {
        if ( v19 > 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("vector too long");
        std::vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,unsigned int>>::_Reallocate<0>(&v56, &v51);
        v18 = 0;
      }
      v20 = *(const char **)*v4;
      v51 = v20;
      while ( v20[25] == v18 )
      {
        v61 = v20 + 32;
        v21 = v20 + 48;
        v22 = (const struct Mso::IRefCounted *)*((_QWORD *)v20 + 6);
        if ( v22 )
        {
          CachedResourceStateForObject = (const char *)Cache::Cache::GetCachedResourceStateForObject(this, v22);
          if ( (**(unsigned int (__fastcall ***)(const char *))CachedResourceStateForObject)(CachedResourceStateForObject) == 1 )
          {
            if ( v8 )
            {
              v34 = *(_QWORD *)v21;
              v69 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
              v70 = "objectPtr";
              v71 = v34;
              v72 = 4;
              v73 = 0;
              v74 = si128;
              LOWORD(v73) = 0;
              v35 = sub_18000D7FC(*((unsigned int *)this + 28));
              v75 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
              v76 = "cacheType";
              v77 = v35;
              v78 = 4;
              v79 = 0;
              v80 = si128;
              LOWORD(v79) = v36;
              CachedResourceStateForObject = "Gfx::Cache::Evict status : object is unreferenced so is a candidate for eviction";
              Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>>(
                (unsigned int)"cacheType",
                v37,
                v38,
                v39,
                (__int64)&CachedResourceStateForObject,
                (__int64)&v75,
                (__int64)&v69);
              std::wstring::~wstring(&v79);
              std::wstring::~wstring(&v73);
            }
            v23 = *(_QWORD *)v21;
            v24 = *((_DWORD *)v21 + 2);
            v65 = v24;
            v66 = v23;
            v25 = v61;
            v67 = v61;
            v26 = *((_QWORD *)&v56 + 1);
            if ( *((_QWORD *)&v56 + 1) == v57 )
            {
LABEL_44:
              std::vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,unsigned int>>::_Emplace_reallocate<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,unsigned int>>(
                &v56,
                v26,
                &v65);
            }
            else
            {
              **((_DWORD **)&v56 + 1) = v24;
              *(_QWORD *)(v26 + 8) = v23;
              *(_QWORD *)(v26 + 16) = v25;
              *((_QWORD *)&v56 + 1) += 24LL;
            }
          }
          else
          {
            if ( v8 )
            {
              v40 = (**(__int64 (__fastcall ***)(const char *))CachedResourceStateForObject)(CachedResourceStateForObject);
              v81 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
              v82 = "refCount";
              LODWORD(v83) = v40;
              WORD2(v83) = 4;
              *(_OWORD *)v84 = 0;
              *(__m128i *)&v84[16] = si128;
              *(_WORD *)v84 = 0;
              v41 = *(_QWORD *)v21;
              v69 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
              v70 = "objectPtr";
              v71 = v41;
              v72 = 4;
              v73 = 0;
              v74 = si128;
              LOWORD(v73) = 0;
              v42 = sub_18000D7FC(*((unsigned int *)this + 28));
              v75 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
              v76 = "cacheType";
              v77 = v42;
              v78 = 4;
              v79 = 0;
              v80 = si128;
              LOWORD(v79) = v43;
              CachedResourceStateForObject = "Gfx::Cache::Evict status : object is in use and cannot be evict candidate";
              Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>>(
                (unsigned int)"cacheType",
                v44,
                v43,
                v45,
                (__int64)&CachedResourceStateForObject,
                (__int64)&v75,
                (__int64)&v69,
                (__int64)&v81);
              std::wstring::~wstring(&v79);
              std::wstring::~wstring(&v73);
              std::wstring::~wstring(v84);
            }
            v27 = *(_QWORD *)std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(
                               &Block,
                               v68,
                               v61);
            Mso::TCntPtr<Mso::IRefCounted>::operator=((void *)(v27 + 48));
            *(_DWORD *)(v27 + 56) = *((_DWORD *)v21 + 2);
            v8 = v50;
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>>,std::_Iterator_base0>::operator++(&v51);
        v20 = v51;
        v10 = v63;
      }
      LOBYTE(v11) = v50;
      sub_1801145EC(
        v56,
        *((_QWORD *)&v56 + 1),
        0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v56 + 1) - v56) >> 3),
        v11);
      v28 = v56;
      v51 = (const char *)*((_QWORD *)&v56 + 1);
      while ( (_QWORD)v28 != *((_QWORD *)&v28 + 1) )
      {
        Cache::Cache::EvictOrAddToMap(this, a2, v59, v62, (__int64)v10, (__int64)&Block, (__int64)&v54, (__int64)&v58);
        v7 = v54;
        v28 = __PAIR128__((unsigned __int64)v51, (__int64)v28 + 24);
      }
      std::vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,unsigned int>>::~vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,unsigned int>>(&v56);
      v8 = v50;
    }
    else
    {
      v12 = *(const char **)*v4;
      v51 = v12;
      while ( !v12[25] )
      {
        if ( *((_QWORD *)v12 + 6) )
        {
          Cache::Cache::EvictOrAddToMap(this, a2, v59, v62, (__int64)v10, (__int64)&Block, (__int64)&v54, (__int64)&v58);
          v7 = v54;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>>,std::_Iterator_base0>::operator++(&v51);
        v12 = v51;
      }
    }
    if ( v4 != &Block )
    {
      v13 = *v4;
      *v4 = Block;
      Block = v13;
      v14 = v4[1];
      v4[1] = v53;
      v53 = v14;
    }
    if ( byte_18051EEE0 < 0 )
      v15 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051EEE0);
    else
      v15 = byte_18051EEE0 != 0;
    if ( v15 )
      *((_QWORD *)this + 18) -= v7;
    std::_Tree_val<std::_Tree_simple_types<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>,void *>>>(
      &Block,
      &Block,
      *((_QWORD *)Block + 1));
    free(Block);
    v16 = Cache::Cache::GetTotalCacheSize(this);
    if ( v8 )
    {
      v97[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v97[1] = "newCacheSizeBytes";
      v97[2] = v16;
      v98 = 4;
      v99[0] = 0;
      v99[1] = si128;
      LOWORD(v99[0]) = 0;
      v94[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v94[1] = "newItemCount";
      v94[2] = *((_QWORD *)this + 5);
      v95 = 4;
      v96[0] = 0;
      v96[1] = si128;
      LOWORD(v96[0]) = 0;
      v91[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v91[1] = "oldCacheSizeBytes";
      v91[2] = TotalCacheSize;
      v92 = 4;
      v93[0] = 0;
      v93[1] = si128;
      LOWORD(v93[0]) = 0;
      v81 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v82 = "oldItemCount";
      v83 = v60;
      *(_WORD *)v84 = 4;
      *(_OWORD *)&v84[8] = 0;
      *(__m128i *)&v84[24] = si128;
      *(_WORD *)&v84[8] = 0;
      v85 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v86 = "reclaimedBytes";
      v87 = v7;
      v88 = 4;
      v89 = 0;
      v90 = si128;
      LOWORD(v89) = 0;
      v69 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v70 = "evictCount";
      v71 = v58;
      v72 = 4;
      v73 = 0;
      v74 = si128;
      LOWORD(v73) = 0;
      v75 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v76 = "cacheType";
      v77 = sub_18000D7FC(*((unsigned int *)this + 28));
      v78 = 4;
      v79 = 0;
      v80 = si128;
      LOWORD(v79) = 0;
      v60 = "Gfx::Cache::Evict (end)";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
        v47,
        v46,
        v48,
        v49,
        (__int64)&v60,
        (__int64)&v75,
        (__int64)&v69,
        (__int64)&v85,
        (__int64)&v81,
        (__int64)v91,
        (__int64)v94,
        (__int64)v97);
      std::wstring::~wstring(&v79);
      std::wstring::~wstring(&v73);
      std::wstring::~wstring(&v89);
      std::wstring::~wstring(&v84[8]);
      std::wstring::~wstring(v93);
      std::wstring::~wstring(v96);
      std::wstring::~wstring(v99);
    }
    return v7;
  }
  else
  {
    Mso::Logging::MsoSendTraceTag(592545556, 48, 10, L"Gfx::Cache::Evict - Cannot access cache manager");
    return 0;
  }
}

```

## disassembly

```asm
0x180067d18  mov     rax, rsp
0x180067d1b  push    rbx
0x180067d1c  push    rsi
0x180067d1d  push    rdi
0x180067d1e  push    r12
0x180067d20  push    r13
0x180067d22  push    r14
0x180067d24  push    r15
0x180067d26  sub     rsp, 2F0h
0x180067d2d  movaps  xmmword ptr [rax-48h], xmm6
0x180067d31  mov     rax, cs:__security_cookie
0x180067d38  xor     rax, rsp
0x180067d3b  mov     [rsp+328h+var_58], rax
0x180067d43  mov     rsi, r9
0x180067d46  mov     [rsp+328h+var_260], r9
0x180067d4e  mov     [rsp+328h+var_278], r8
0x180067d56  mov     r15d, edx
0x180067d59  mov     rdi, rcx
0x180067d5c  mov     al, cs:byte_18051EEC8
0x180067d62  xor     r12d, r12d
0x180067d65  test    al, al
0x180067d67  js      loc_180067F4B
0x180067d6d  setnz   bl
0x180067d70  mov     [rsp+328h+var_2C8], bl
0x180067d74  mov     r13d, 4
0x180067d7a  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180067d82  test    bl, bl
0x180067d84  jnz     loc_1800681D7
0x180067d8a  cmp     r15d, 2
0x180067d8e  jz      loc_1800681C0
0x180067d94  cmp     r15d, 3
0x180067d98  jz      loc_180068198
0x180067d9e  call    ?PInternalInstance@CacheManager@Cache@@SAPEAV12@XZ; Cache::CacheManager::PInternalInstance(void)
0x180067da3  mov     r14, rax
0x180067da6  mov     [rsp+328h+var_258], rax
0x180067dae  test    rax, rax
0x180067db1  jz      loc_180068397
0x180067db7  mov     rax, [rdi+28h]
0x180067dbb  mov     [rsp+328h+var_270], rax
0x180067dc3  mov     rcx, rdi; this
0x180067dc6  call    ?GetTotalCacheSize@Cache@1@QEBA_KXZ; Cache::Cache::GetTotalCacheSize(void)
0x180067dcb  mov     [rsp+328h+var_250], rax
0x180067dd3  mov     [rsp+328h+var_2A8], r12
0x180067ddb  xor     eax, eax
0x180067ddd  mov     [rsp+328h+var_280], rax
0x180067de5  lea     rcx, [rsp+328h+Block]
0x180067dea  call    ??0?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@QEAA@XZ; std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>(void)
0x180067def  lea     rsi, [rdi+20h]
0x180067df3  cmp     r15d, r13d
0x180067df6  jz      loc_180067F7D
0x180067dfc  mov     rax, [rsi]
0x180067dff  mov     rax, [rax]
0x180067e02  mov     [rsp+328h+var_2C0], rax
0x180067e07  xor     ecx, ecx
0x180067e09  cmp     [rax+19h], cl
0x180067e0c  jnz     loc_180067EA0
0x180067e12  lea     rdx, [rax+20h]
0x180067e16  mov     r8, [rdx+10h]
0x180067e1a  test    r8, r8
0x180067e1d  jz      short loc_180067E7B
0x180067e1f  lea     rax, [rsp+328h+var_280]
0x180067e27  mov     [rsp+328h+var_2D8], rax; __int64
0x180067e2c  lea     rax, [rsp+328h+var_2A8]
0x180067e34  mov     [rsp+328h+var_2E0], rax; __int64
0x180067e39  lea     rax, [rsp+328h+Block]
0x180067e3e  mov     [rsp+328h+var_2E8], rax; __int64
0x180067e43  mov     [rsp+328h+var_2F0], r14; __int64
0x180067e48  mov     rax, [rsp+328h+var_260]
0x180067e50  mov     [rsp+328h+var_2F8], rax; __int64
0x180067e55  mov     rax, [rsp+328h+var_278]
0x180067e5d  mov     [rsp+328h+var_300], rax; __int64
0x180067e62  mov     [rsp+328h+var_308], r15d; int
0x180067e67  mov     r9d, [rdx+18h]
0x180067e6b  mov     rcx, rdi; this
0x180067e6e  call    ?EvictOrAddToMap@Cache@1@AEAAXAEBVKeyHolder@1@AEAUIRefCounted@Mso@@IW4EvictionType@1@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@4@AEAVCacheManager@1@AEAV?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEA_K7@Z; Cache::Cache::EvictOrAddToMap(Cache::KeyHolder const &,Mso::IRefCounted &,uint,Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *,Cache::CacheManager &,std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair> &,unsigned __int64 &,unsigned __int64 &)
0x180067e73  mov     r12, [rsp+328h+var_2A8]
0x180067e7b  lea     rcx, [rsp+328h+var_2C0]
0x180067e80  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@URasterizerCache@Gfx@@U?$default_delete@URasterizerCache@Gfx@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>>,std::_Iterator_base0>::operator++(void)
0x180067e85  mov     rax, [rsp+328h+var_2C0]
0x180067e8a  jmp     loc_180067E07
0x180067e8f  lea     rcx, [rsp+328h+var_298]
0x180067e97  call    ??1?$vector@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@V?$allocator@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint>>::~vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint>>(void)
0x180067e9c  mov     bl, [rsp+328h+var_2C8]
0x180067ea0  lea     rax, [rsp+328h+Block]
0x180067ea5  cmp     rsi, rax
0x180067ea8  jz      short loc_180067ECC
0x180067eaa  mov     rcx, [rsi]
0x180067ead  mov     rax, [rsp+328h+Block]
0x180067eb2  mov     [rsi], rax
0x180067eb5  mov     [rsp+328h+Block], rcx
0x180067eba  mov     rcx, [rsi+8]
0x180067ebe  mov     rax, [rsp+328h+var_2B0]
0x180067ec3  mov     [rsi+8], rax
0x180067ec7  mov     [rsp+328h+var_2B0], rcx
0x180067ecc  mov     al, cs:byte_18051EEE0
0x180067ed2  xor     esi, esi
0x180067ed4  test    al, al
0x180067ed6  js      loc_180067F6B
0x180067edc  setnz   al
0x180067edf  test    al, al
0x180067ee1  jz      short loc_180067EEA
0x180067ee3  sub     [rdi+90h], r12
0x180067eea  mov     r8, [rsp+328h+Block]
0x180067eef  mov     r8, [r8+8]
0x180067ef3  lea     rdx, [rsp+328h+Block]
0x180067ef8  lea     rcx, [rsp+328h+Block]
0x180067efd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>,void *>>>(std::allocator<std::_Tree_node<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>,void *>> &,std::_Tree_node<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>,void *> *)
0x180067f02  mov     rcx, [rsp+328h+Block]; Block
0x180067f07  call    cs:__imp_free
0x180067f0d  mov     rcx, rdi; this
0x180067f10  call    ?GetTotalCacheSize@Cache@1@QEBA_KXZ; Cache::Cache::GetTotalCacheSize(void)
0x180067f15  test    bl, bl
0x180067f17  jnz     loc_180068636
0x180067f1d  mov     rax, r12
0x180067f20  mov     rcx, [rsp+328h+var_58]
0x180067f28  xor     rcx, rsp; StackCookie
0x180067f2b  call    __security_check_cookie
0x180067f30  movaps  xmm6, [rsp+328h+var_48]
0x180067f38  add     rsp, 2F0h
0x180067f3f  pop     r15
0x180067f41  pop     r14
0x180067f43  pop     r13
0x180067f45  pop     r12
0x180067f47  pop     rdi
0x180067f48  pop     rsi
0x180067f49  pop     rbx
0x180067f4a  retn
0x180067f4b  lea     rcx, byte_18051EEC8
0x180067f52  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x180067f58  mov     bl, al
0x180067f5a  mov     [rsp+328h+var_2C8], al
0x180067f5e  mov     r8, [rsp+328h+var_278]
0x180067f66  jmp     loc_180067D74
0x180067f6b  lea     rcx, byte_18051EEE0
0x180067f72  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180067f78  jmp     loc_180067EDF
0x180067f7d  xorps   xmm0, xmm0
0x180067f80  movdqu  [rsp+328h+var_298], xmm0
0x180067f89  xor     r10d, r10d
0x180067f8c  mov     [rsp+328h+var_288], r10
0x180067f94  mov     rax, [rsi+8]
0x180067f98  mov     [rsp+328h+var_2C0], rax
0x180067f9d  test    rax, rax
0x180067fa0  jz      short loc_180067FCA
0x180067fa2  mov     rcx, 0AAAAAAAAAAAAAAAh
0x180067fac  cmp     rax, rcx
0x180067faf  ja      loc_1800683B9
0x180067fb5  lea     rdx, [rsp+328h+var_2C0]
0x180067fba  lea     rcx, [rsp+328h+var_298]
0x180067fc2  call    ??$_Reallocate@$0A@@?$vector@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@V?$allocator@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint>>::_Reallocate<0>(unsigned __int64 &)
0x180067fc7  xor     r10d, r10d
0x180067fca  mov     rax, [rsi]
0x180067fcd  mov     rax, [rax]
0x180067fd0  mov     [rsp+328h+var_2C0], rax
0x180067fd5  cmp     [rax+19h], r10b
0x180067fd9  jnz     loc_1800680D9
0x180067fdf  add     rax, 20h ; ' '
0x180067fe3  mov     [rsp+328h+var_268], rax
0x180067feb  lea     r14, [rax+10h]
0x180067fef  mov     rdx, [r14]; struct Mso::IRefCounted *
0x180067ff2  test    rdx, rdx
0x180067ff5  jz      loc_18006807C
0x180067ffb  mov     rcx, rdi; this
0x180067ffe  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x180068003  mov     rdx, rax
0x180068006  mov     [rsp+328h+var_2A0], rax
0x18006800e  mov     rcx, [rax]
0x180068011  mov     rax, [rcx]
0x180068014  mov     rcx, rdx
0x180068017  call    cs:__guard_dispatch_icall_fptr
0x18006801d  cmp     eax, 1
0x180068020  jnz     short loc_180068098
0x180068022  xor     r10d, r10d
0x180068025  test    bl, bl
0x180068027  jnz     loc_1800683C6
0x18006802d  mov     rax, [r14]
0x180068030  mov     ecx, [r14+8]
0x180068034  mov     [rsp+328h+var_248], ecx
0x18006803b  mov     [rsp+328h+var_240], rax
0x180068043  mov     r8, [rsp+328h+var_268]
0x18006804b  mov     [rsp+328h+var_238], r8
0x180068053  mov     rdx, qword ptr [rsp+328h+var_298+8]
0x18006805b  cmp     rdx, [rsp+328h+var_288]
0x180068063  jz      loc_1800681A6
0x180068069  mov     [rdx], ecx
0x18006806b  mov     [rdx+8], rax
0x18006806f  mov     [rdx+10h], r8
0x180068073  add     qword ptr [rsp+328h+var_298+8], 18h
0x18006807c  lea     rcx, [rsp+328h+var_2C0]
0x180068081  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIFactory@ARC@@V?$unique_ptr@URasterizerCache@Gfx@@U?$default_delete@URasterizerCache@Gfx@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ARC::IFactory * const,std::unique_ptr<Gfx::RasterizerCache>>>>,std::_Iterator_base0>::operator++(void)
0x180068086  mov     rax, [rsp+328h+var_2C0]
0x18006808b  mov     r14, [rsp+328h+var_258]
0x180068093  jmp     loc_180067FD5
0x180068098  test    bl, bl
0x18006809a  jnz     loc_1800684C3
0x1800680a0  mov     r8, [rsp+328h+var_268]
0x1800680a8  lea     rdx, [rsp+328h+var_230]
0x1800680b0  lea     rcx, [rsp+328h+Block]
0x1800680b5  call    ??$_Try_emplace@AEBVKeyHolder@Cache@@$$V@?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@_N@1@AEBVKeyHolder@Cache@@@Z; std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(Cache::KeyHolder const &)
0x1800680ba  mov     rbx, [rax]
0x1800680bd  mov     rdx, r14
0x1800680c0  lea     rcx, [rbx+30h]
0x1800680c4  call    ??4?$TCntPtr@UIRefCounted@Mso@@@Mso@@QEAAAEAV01@AEBV01@@Z; Mso::TCntPtr<Mso::IRefCounted>::operator=(Mso::TCntPtr<Mso::IRefCounted> const &)
0x1800680c9  mov     eax, [r14+8]
0x1800680cd  mov     [rbx+38h], eax
0x1800680d0  mov     bl, [rsp+328h+var_2C8]
0x1800680d4  xor     r10d, r10d
0x1800680d7  jmp     short loc_18006807C
0x1800680d9  mov     rdx, qword ptr [rsp+328h+var_298+8]
0x1800680e1  mov     r8, rdx
0x1800680e4  mov     rcx, qword ptr [rsp+328h+var_298]
0x1800680ec  sub     r8, rcx
0x1800680ef  sar     r8, 3
0x1800680f3  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800680fd  imul    r8, rax
0x180068101  mov     r9b, [rsp+328h+var_2C8]
0x180068106  call    sub_1801145EC
0x18006810b  nop
0x18006810c  mov     rbx, qword ptr [rsp+328h+var_298]
0x180068114  mov     rax, qword ptr [rsp+328h+var_298+8]
0x18006811c  mov     [rsp+328h+var_2C0], rax
0x180068121  cmp     rbx, rax
0x180068124  jz      loc_180067E8F
0x18006812a  lea     rax, [rsp+328h+var_280]
0x180068132  mov     [rsp+328h+var_2D8], rax; __int64
0x180068137  lea     rax, [rsp+328h+var_2A8]
0x18006813f  mov     [rsp+328h+var_2E0], rax; __int64
0x180068144  lea     rax, [rsp+328h+Block]
0x180068149  mov     [rsp+328h+var_2E8], rax; __int64
0x18006814e  mov     [rsp+328h+var_2F0], r14; __int64
0x180068153  mov     rax, [rsp+328h+var_260]
0x18006815b  mov     [rsp+328h+var_2F8], rax; __int64
0x180068160  mov     rax, [rsp+328h+var_278]
0x180068168  mov     [rsp+328h+var_300], rax; __int64
0x18006816d  mov     [rsp+328h+var_308], r15d; int
0x180068172  mov     r9d, [rbx]
0x180068175  mov     r8, [rbx+8]
0x180068179  mov     rdx, [rbx+10h]
0x18006817d  mov     rcx, rdi; this
0x180068180  call    ?EvictOrAddToMap@Cache@1@AEAAXAEBVKeyHolder@1@AEAUIRefCounted@Mso@@IW4EvictionType@1@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@4@AEAVCacheManager@1@AEAV?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEA_K7@Z; Cache::Cache::EvictOrAddToMap(Cache::KeyHolder const &,Mso::IRefCounted &,uint,Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *,Cache::CacheManager &,std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair> &,unsigned __int64 &,unsigned __int64 &)
0x180068185  add     rbx, 18h
0x180068189  mov     r12, [rsp+328h+var_2A8]
0x180068191  mov     rax, [rsp+328h+var_2C0]
0x180068196  jmp     short loc_180068121
0x180068198  xor     edx, edx
0x18006819a  mov     ecx, 23518715h
0x18006819f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800681a5  nop
0x1800681a6  lea     r8, [rsp+328h+var_248]
0x1800681ae  lea     rcx, [rsp+328h+var_298]
0x1800681b6  call    ??$_Emplace_reallocate@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@@?$vector@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@V?$allocator@V?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@std@@@2@@std@@AEAAPEAV?$tuple@PEBVKeyHolder@Cache@@PEAUIRefCounted@Mso@@I@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint>>::_Emplace_reallocate<std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint>>(std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint> * const,std::tuple<Cache::KeyHolder const *,Mso::IRefCounted *,uint> &&)
0x1800681bb  jmp     loc_1800680D4
0x1800681c0  test    rsi, rsi
0x1800681c3  jnz     loc_180067D9E
0x1800681c9  xor     edx, edx
0x1800681cb  mov     ecx, 23518716h
0x1800681d0  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800681d6  int     3; Trap to Debugger
0x1800681d7  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x1800681de  mov     [rsp+328h+var_1D8], rax
0x1800681e6  lea     rax, aEvictiongoalby; "evictionGoalBytes"
0x1800681ed  mov     [rsp+328h+var_1D0], rax
0x1800681f5  mov     [rsp+328h+var_1C8], r8
0x1800681fd  mov     [rsp+328h+var_1C0], r13w
0x180068206  xorps   xmm0, xmm0
0x180068209  movups  [rsp+328h+var_1B8], xmm0
0x180068211  movdqa  [rsp+328h+var_1A8], xmm6
0x18006821a  mov     word ptr [rsp+328h+var_1B8], r12w
0x180068223  mov     ecx, r15d
0x180068226  call    sub_180004640
0x18006822b  lea     r14, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180068232  mov     [rsp+328h+var_218], r14
0x18006823a  lea     rcx, aEvicttype; "evictType"
0x180068241  mov     [rsp+328h+var_210], rcx
0x180068249  mov     [rsp+328h+var_208], rax
0x180068251  mov     [rsp+328h+var_200], r13w
0x18006825a  movups  [rsp+328h+var_1F8], xmm0
0x180068262  movdqa  [rsp+328h+var_1E8], xmm6
0x18006826b  mov     word ptr [rsp+328h+var_1F8], r12w
0x180068274  call    cs:__imp_GetCurrentThreadId
0x18006827a  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180068281  mov     [rsp+328h+var_198], rcx
0x180068289  lea     rcx, aThreadid; "threadID"
0x180068290  mov     [rsp+328h+var_190], rcx
0x180068298  mov     dword ptr [rsp+328h+var_188], eax
0x18006829f  mov     word ptr [rsp+328h+var_188+4], r13w
0x1800682a8  xorps   xmm0, xmm0
0x1800682ab  movups  [rsp+328h+var_180], xmm0
0x1800682b3  movdqu  [rsp+328h+var_170], xmm6
0x1800682bc  mov     word ptr [rsp+328h+var_180], r12w
0x1800682c5  mov     ecx, [rdi+70h]
0x1800682c8  call    sub_18000D7FC
0x1800682cd  mov     [rsp+328h+var_158], r14
0x1800682d5  lea     r14, aCachetype; "cacheType"
0x1800682dc  mov     [rsp+328h+var_150], r14
0x1800682e4  mov     [rsp+328h+var_148], rax
0x1800682ec  mov     [rsp+328h+var_140], r13w
0x1800682f5  movups  [rsp+328h+var_138], xmm0
0x1800682fd  movdqa  [rsp+328h+var_128], xmm6
0x180068306  mov     word ptr [rsp+328h+var_138], r12w
  ... truncated ...
```
