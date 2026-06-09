# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetEnergyRecordsFromSrumRecordSet(std::vector<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow,std::allocator<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>> &,std::map<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::App_Usage,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,SystemSettings::BatteryUsageHandlers::App_Usage>>> *)

- ea: `0x1800403f8`
- end: `0x18004132a`
- name: `?GetEnergyRecordsFromSrumRecordSet@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJAEAV?$vector@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@V?$allocator@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@PEAV?$map@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UApp_Usage@23@UAppIdentityCompare@23@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@UApp_Usage@23@@std@@@std@@@5@@Z`
- size: `3890`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003f910`

## callees

- `0x1800028d0`
- `0x18000d4dc`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180025cf4`
- `0x180026444`
- `0x180029e10`
- `0x18002aab0`
- `0x18002b900`
- `0x1800312dc`
- `0x18003806c`
- `0x18003bb58`
- `0x18003d0cc`
- `0x18003d254`
- `0x18003d3d4`
- `0x18003dc48`
- `0x18003dc78`
- `0x18003dca8`
- `0x18003e1c4`
- `0x18003e220`
- `0x18003e27c`
- `0x18003e7a4`
- `0x1800403f8`
- `0x180044858`
- `0x18004702c`
- `0x1800470b8`
- `0x180047138`
- `0x1800472e8`
- `0x180047958`
- `0x180049480`
- `0x180049528`
- `0x1800512e0`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180040433`
- `msvcp_win!_Xtime_get_ticks` at `0x18004119a`
- `msvcp_win!_Xtime_get_ticks` at `0x180040433`
- `msvcp_win!_Xtime_get_ticks` at `0x18004119a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetEnergyRecordsFromSrumRecordSet(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v5; // rdi
  SystemSettings::BatteryUsageHandlers::ThrottlePolicyManager *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // r13
  __m128i si128; // xmm7
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 PackageFamilyNameFromPackageFullName; // rsi
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  unsigned __int64 *v18; // r8
  __int64 v19; // r8
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // rdx
  __int64 v22; // rdx
  double v23; // xmm1_8
  double v24; // xmm1_8
  __int64 v25; // rcx
  double v26; // xmm0_8
  __int64 v27; // rax
  double v28; // xmm0_8
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r15
  __int64 v31; // rcx
  double v32; // xmm0_8
  __int64 v33; // rax
  double v34; // xmm0_8
  unsigned __int64 v35; // rcx
  _QWORD *v36; // rax
  bool v37; // r14
  _QWORD *v38; // rax
  __int64 v39; // rsi
  __int64 v40; // r8
  SystemSettings::BatteryUsageHandlers::AppIdentity *v41; // rax
  __int64 v42; // rcx
  unsigned __int64 v43; // rax
  double v44; // xmm0_8
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  double v47; // xmm0_8
  unsigned __int64 v48; // rax
  double v49; // xmm0_8
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  double v52; // xmm0_8
  unsigned __int64 v53; // rax
  double v54; // xmm0_8
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // rdx
  double v57; // xmm0_8
  double *v58; // rsi
  unsigned __int64 v59; // rax
  double v60; // xmm0_8
  unsigned __int64 v61; // rcx
  unsigned __int64 v62; // rdx
  double v63; // xmm0_8
  __int64 v64; // rax
  __int64 v65; // rcx
  _OWORD *v66; // rdx
  unsigned __int64 v67; // rax
  double v68; // xmm0_8
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // rdx
  double v71; // xmm0_8
  __int64 v72; // rax
  unsigned __int64 v73; // rax
  double v74; // xmm0_8
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // rdx
  double v77; // xmm0_8
  __int64 *v79; // rax
  __m128d v80; // xmm2
  __int64 **v81; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  __m128d v84; // xmm2
  __m128d v85; // xmm2
  _QWORD *v86; // rdi
  _QWORD *k; // rbx
  _QWORD *v88; // rdi
  _QWORD *m; // rbx
  double v90; // xmm0_8
  int v91; // r14d
  int AggregatedTimeInMscFromTimeRanges; // r14d
  __int128 v93; // [rsp+20h] [rbp-2D8h] BYREF
  __int64 v94; // [rsp+30h] [rbp-2C8h]
  __int128 v95; // [rsp+38h] [rbp-2C0h] BYREF
  __int64 v96; // [rsp+48h] [rbp-2B0h]
  struct _SYSTEMTIME v97; // [rsp+50h] [rbp-2A8h] BYREF
  __int64 ticks; // [rsp+68h] [rbp-290h] BYREF
  float v99; // [rsp+70h] [rbp-288h] BYREF
  __int64 v100; // [rsp+78h] [rbp-280h]
  _BYTE v101[16]; // [rsp+B0h] [rbp-248h] BYREF
  float v102; // [rsp+C0h] [rbp-238h] BYREF
  __int64 v103; // [rsp+C8h] [rbp-230h]
  float v104; // [rsp+100h] [rbp-1F8h] BYREF
  _QWORD *v105; // [rsp+108h] [rbp-1F0h]
  float v106; // [rsp+140h] [rbp-1B8h] BYREF
  _QWORD *v107; // [rsp+148h] [rbp-1B0h]
  _BYTE v108[8]; // [rsp+180h] [rbp-178h] BYREF
  _BYTE v109[8]; // [rsp+188h] [rbp-170h] BYREF
  _BYTE v110[8]; // [rsp+190h] [rbp-168h] BYREF
  _BYTE v111[16]; // [rsp+198h] [rbp-160h] BYREF
  _BYTE v112[16]; // [rsp+1A8h] [rbp-150h] BYREF
  _BYTE v113[16]; // [rsp+1B8h] [rbp-140h] BYREF
  _BYTE v114[16]; // [rsp+1C8h] [rbp-130h] BYREF
  _BYTE v115[16]; // [rsp+1D8h] [rbp-120h] BYREF
  _BYTE v116[16]; // [rsp+1E8h] [rbp-110h] BYREF
  _BYTE v117[16]; // [rsp+1F8h] [rbp-100h] BYREF
  _BYTE v118[40]; // [rsp+208h] [rbp-F0h] BYREF
  __int128 v119; // [rsp+230h] [rbp-C8h] BYREF
  _BYTE v120[32]; // [rsp+240h] [rbp-B8h] BYREF
  int v121; // [rsp+260h] [rbp-98h]
  int v122; // [rsp+264h] [rbp-94h]
  _OWORD v123[2]; // [rsp+268h] [rbp-90h] BYREF
  _BYTE v124[32]; // [rsp+288h] [rbp-70h] BYREF

  ticks = _Xtime_get_ticks();
  v5 = 0;
  SystemSettings::BatteryUsageHandlers::ThrottlePolicyManager::LoadAppList(v6);
  SystemSettings::BatteryUsageHandlers::ThrottlePolicyManager::GetThrottleableApps(v7, &v97.wHour);
  std::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>(&v106);
  std::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>(&v104);
  v95 = 0;
  v96 = 0;
  v93 = 0;
  v94 = 0;
  std::_Tree<std::_Tmap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::App_Usage,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,SystemSettings::BatteryUsageHandlers::App_Usage>>,0>>::clear(a3);
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(&v102);
  std::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>>::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>>(&v99);
  v8 = *a2;
  v9 = a2[1];
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v8 != v9 )
  {
    v123[0] = 0;
    v123[1] = si128;
    LOWORD(v123[0]) = 0;
    if ( *(_DWORD *)(v8 + 32) == 1 )
    {
      v11 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                        &v102,
                        v108,
                        v8);
      if ( *v11 == v103 )
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8, v12, v13);
        PackageFamilyNameFromPackageFullName = SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(
                                                 v124,
                                                 v14);
        v16 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                          &v102,
                          (__int64)v111,
                          v8);
        std::wstring::operator=(*v16 + 48LL, PackageFamilyNameFromPackageFullName);
        std::wstring::_Tidy_deallocate(v124);
      }
      v17 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                        &v102,
                        (__int64)v112,
                        v8);
      std::wstring::operator=(v123, *v17 + 48LL);
    }
    else
    {
      std::wstring::operator=(v123, v8);
    }
    *(_QWORD *)&v97.wYear = 0;
    TimeFormatUtils::SystemTimeToTimestamp((TimeFormatUtils *)(v8 + 48), &v97, v18);
    if ( *(_DWORD *)(v8 + 44) )
    {
      v19 = (unsigned int)(10000 * *(_DWORD *)(v8 + 44));
      v20 = *(_QWORD *)&v97.wYear - v19;
      if ( (unsigned __int64)(*(_QWORD *)&v97.wYear - v19) <= *(_QWORD *)&qword_180079DE0 )
        v20 = *(_QWORD *)&qword_180079DE0;
      v21 = qword_180079DE8;
      if ( *(_QWORD *)&v97.wYear < qword_180079DE8 )
        v21 = *(_QWORD *)&v97.wYear;
      if ( v21 > v20 )
      {
        *(_QWORD *)&v119 = v20;
        *((_QWORD *)&v119 + 1) = v21;
        v22 = v21 - v20;
        if ( v22 < 0 )
          v23 = (double)(int)(v22 & 1 | ((unsigned __int64)v22 >> 1))
              + (double)(int)(v22 & 1 | ((unsigned __int64)v22 >> 1));
        else
          v23 = (double)(int)v22;
        v24 = v23 / (double)(int)v19;
        v25 = *(_QWORD *)(v8 + 64);
        if ( v25 < 0 )
        {
          v27 = *(_QWORD *)(v8 + 64) & 1LL | ((unsigned __int64)v25 >> 1);
          v26 = (double)(int)v27 + (double)(int)v27;
        }
        else
        {
          v26 = (double)(int)v25;
        }
        v28 = v26 * v24;
        v29 = 0;
        if ( v28 >= 9.223372036854776e18 )
        {
          v28 = v28 - 9.223372036854776e18;
          if ( v28 < 9.223372036854776e18 )
            v29 = 0x8000000000000000uLL;
        }
        v30 = v29 + (unsigned int)(int)v28;
        *(_QWORD *)(v8 + 64) = v30;
        v31 = *(_QWORD *)(v8 + 72);
        if ( v31 < 0 )
        {
          v33 = *(_QWORD *)(v8 + 72) & 1LL | ((unsigned __int64)v31 >> 1);
          v32 = (double)(int)v33 + (double)(int)v33;
        }
        else
        {
          v32 = (double)(int)v31;
        }
        v34 = v32 * v24;
        v35 = 0;
        if ( v34 >= 9.223372036854776e18 )
        {
          v34 = v34 - 9.223372036854776e18;
          if ( v34 < 9.223372036854776e18 )
            v35 = 0x8000000000000000uLL;
        }
        *(_QWORD *)(v8 + 72) = v35 + (unsigned int)(int)v34;
        std::wstring::wstring((__int64)v120, (__int64)v123, v19);
        v121 = *(_DWORD *)(v8 + 32);
        v122 = 0;
        v36 = (_QWORD *)std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::find(
                          &v97.wHour,
                          v109,
                          v120);
        v37 = *v36 == *(_QWORD *)&v97.wHour;
        v38 = (_QWORD *)std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::find(
                          &v99,
                          v110,
                          v120);
        if ( *v38 == v100 )
        {
          v39 = *(_QWORD *)std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                             &v99,
                             (__int64)v113,
                             (__int64)v120);
          v41 = SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(
                  (SystemSettings::BatteryUsageHandlers::AppIdentity *)v118,
                  (const struct SystemSettings::BatteryUsageHandlers::AppIdentity *)v120,
                  v40);
          if ( (int)SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::IsApp(v42, v41, v39 + 56) < 0 )
            *(_BYTE *)(*(_QWORD *)std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                                    &v99,
                                    (__int64)v114,
                                    (__int64)v120)
                     + 56LL) = 0;
        }
        if ( !*(_BYTE *)(*(_QWORD *)std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                                      &v99,
                                      (__int64)v115,
                                      (__int64)v120)
                       + 56LL)
          && v37 )
        {
          if ( (*(_BYTE *)(v8 + 36) & 2) != 0 && *(_QWORD *)(v8 + 72) )
          {
            v43 = 0;
            v44 = *(double *)&qword_180079E10;
            if ( *(double *)&qword_180079E10 >= 9.223372036854776e18 )
            {
              v44 = *(double *)&qword_180079E10 - 9.223372036854776e18;
              if ( *(double *)&qword_180079E10 - 9.223372036854776e18 < 9.223372036854776e18 )
                v43 = 0x8000000000000000uLL;
            }
            v45 = v43 + (unsigned int)(int)v44;
            v46 = v45 + *(_QWORD *)(v8 + 64);
            if ( v46 < v45 )
            {
              std::wstring::_Tidy_deallocate(v120);
              std::wstring::_Tidy_deallocate(v123);
              std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
              std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
              if ( (_QWORD)v93 )
              {
                std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
                v93 = 0;
                v94 = 0;
              }
              if ( (_QWORD)v95 )
                goto LABEL_118;
              goto LABEL_119;
            }
            if ( (v46 & 0x8000000000000000uLL) != 0LL )
              v47 = (double)(int)(v46 & 1 | (v46 >> 1)) + (double)(int)(v46 & 1 | (v46 >> 1));
            else
              v47 = (double)(int)v46;
            qword_180079E10 = *(_QWORD *)&v47;
            if ( *((_QWORD *)&v95 + 1) == v96 )
            {
              std::vector<EnergyEstimationRow>::_Emplace_reallocate<EnergyEstimationRow>(
                &v95,
                *((_QWORD *)&v95 + 1),
                &v119);
            }
            else
            {
              **((_OWORD **)&v95 + 1) = v119;
              *((_QWORD *)&v95 + 1) += 16LL;
            }
          }
          else
          {
            v48 = 0;
            v49 = *((double *)&xmmword_180079E00 + 1);
            if ( *((double *)&xmmword_180079E00 + 1) >= 9.223372036854776e18 )
            {
              v49 = *((double *)&xmmword_180079E00 + 1) - 9.223372036854776e18;
              if ( *((double *)&xmmword_180079E00 + 1) - 9.223372036854776e18 < 9.223372036854776e18 )
                v48 = 0x8000000000000000uLL;
            }
            v50 = v48 + (unsigned int)(int)v49;
            v51 = v50 + *(_QWORD *)(v8 + 64);
            if ( v51 < v50 )
            {
              std::wstring::_Tidy_deallocate(v120);
              std::wstring::_Tidy_deallocate(v123);
              std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
              std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
              if ( (_QWORD)v93 )
              {
                std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
                v93 = 0;
                v94 = 0;
              }
              if ( (_QWORD)v95 )
                goto LABEL_118;
              goto LABEL_119;
            }
            if ( (v51 & 0x8000000000000000uLL) != 0LL )
              v52 = (double)(int)(v51 & 1 | (v51 >> 1)) + (double)(int)(v51 & 1 | (v51 >> 1));
            else
              v52 = (double)(int)v51;
            *((double *)&xmmword_180079E00 + 1) = v52;
            if ( *((_QWORD *)&v93 + 1) == v94 )
            {
              std::vector<EnergyEstimationRow>::_Emplace_reallocate<EnergyEstimationRow>(
                &v93,
                *((_QWORD *)&v93 + 1),
                &v119);
            }
            else
            {
              **((_OWORD **)&v93 + 1) = v119;
              *((_QWORD *)&v93 + 1) += 16LL;
            }
          }
          v53 = 0;
          v54 = *(double *)&xmmword_180079E00;
          if ( *(double *)&xmmword_180079E00 >= 9.223372036854776e18 )
          {
            v54 = *(double *)&xmmword_180079E00 - 9.223372036854776e18;
            if ( *(double *)&xmmword_180079E00 - 9.223372036854776e18 < 9.223372036854776e18 )
              v53 = 0x8000000000000000uLL;
          }
          v55 = v53 + (unsigned int)(int)v54;
          v56 = v55 + *(_QWORD *)(v8 + 64);
          if ( v56 < v55 )
          {
            std::wstring::_Tidy_deallocate(v120);
            std::wstring::_Tidy_deallocate(v123);
            std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
            if ( (_QWORD)v93 )
            {
              std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
              v93 = 0;
              v94 = 0;
            }
            if ( (_QWORD)v95 )
              goto LABEL_118;
            goto LABEL_119;
          }
          if ( (v56 & 0x8000000000000000uLL) != 0LL )
            v57 = (double)(int)(v56 & 1 | (v56 >> 1)) + (double)(int)(v56 & 1 | (v56 >> 1));
          else
            v57 = (double)(int)v56;
          *(double *)&xmmword_180079E00 = v57;
LABEL_109:
          v5 += v30;
          std::wstring::_Tidy_deallocate(v120);
          goto LABEL_110;
        }
        v58 = *(double **)std::map<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::App_Usage,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,SystemSettings::BatteryUsageHandlers::App_Usage>>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                            a3,
                            (__int64)v116,
                            (__int64)v120);
        if ( (*(_BYTE *)(v8 + 36) & 2) != 0 && *(_QWORD *)(v8 + 72) )
        {
          v59 = 0;
          v60 = v58[11];
          if ( v60 >= 9.223372036854776e18 )
          {
            v60 = v60 - 9.223372036854776e18;
            if ( v60 < 9.223372036854776e18 )
              v59 = 0x8000000000000000uLL;
          }
          v61 = v59 + (unsigned int)(int)v60;
          v62 = v61 + *(_QWORD *)(v8 + 64);
          if ( v62 < v61 )
          {
            std::wstring::_Tidy_deallocate(v120);
            std::wstring::_Tidy_deallocate(v123);
            std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
            if ( (_QWORD)v93 )
            {
              std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
              v93 = 0;
              v94 = 0;
            }
            if ( (_QWORD)v95 )
              goto LABEL_118;
            goto LABEL_119;
          }
          if ( (v62 & 0x8000000000000000uLL) != 0LL )
            v63 = (double)(int)(v62 & 1 | (v62 >> 1)) + (double)(int)(v62 & 1 | (v62 >> 1));
          else
            v63 = (double)(int)v62;
          v58[11] = v63;
          v64 = std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                  &v106,
                  (__int64)v117,
                  (__int64)v120);
          v65 = *(_QWORD *)v64 + 56LL;
          v66 = *(_OWORD **)(*(_QWORD *)v64 + 64LL);
          if ( v66 == *(_OWORD **)(*(_QWORD *)v64 + 72LL) )
            goto LABEL_100;
LABEL_99:
          *v66 = v119;
          *(_QWORD *)(v65 + 8) += 16LL;
        }
        else
        {
          v67 = 0;
          v68 = v58[10];
          if ( v68 >= 9.223372036854776e18 )
          {
            v68 = v68 - 9.223372036854776e18;
            if ( v68 < 9.223372036854776e18 )
              v67 = 0x8000000000000000uLL;
          }
          v69 = v67 + (unsigned int)(int)v68;
          v70 = v69 + *(_QWORD *)(v8 + 64);
          if ( v70 < v69 )
          {
            std::wstring::_Tidy_deallocate(v120);
            std::wstring::_Tidy_deallocate(v123);
            std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
            if ( (_QWORD)v93 )
            {
              std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
              v93 = 0;
              v94 = 0;
            }
            if ( (_QWORD)v95 )
            {
LABEL_118:
              std::_Deallocate<16>((void *)v95, (struct std::nothrow_t *)((v96 - v95) & 0xFFFFFFFFFFFFFFF0uLL));
              v95 = 0;
              v96 = 0;
            }
LABEL_119:
            std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>((__int64)&v104);
            std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>((__int64)&v106);
            std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>((void **)&v97.wHour);
            return 2147942487LL;
          }
          if ( (v70 & 0x8000000000000000uLL) != 0LL )
            v71 = (double)(int)(v70 & 1 | (v70 >> 1)) + (double)(int)(v70 & 1 | (v70 >> 1));
          else
            v71 = (double)(int)v70;
          v58[10] = v71;
          v72 = std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                  &v104,
                  (__int64)v101,
                  (__int64)v120);
          v65 = *(_QWORD *)v72 + 56LL;
          v66 = *(_OWORD **)(*(_QWORD *)v72 + 64LL);
          if ( v66 != *(_OWORD **)(*(_QWORD *)v72 + 72LL) )
            goto LABEL_99;
LABEL_100:
          std::vector<EnergyEstimationRow>::_Emplace_reallocate<EnergyEstimationRow>(v65, v66, &v119);
        }
        v73 = 0;
        v74 = v58[9];
        if ( v74 >= 9.223372036854776e18 )
        {
          v74 = v74 - 9.223372036854776e18;
          if ( v74 < 9.223372036854776e18 )
            v73 = 0x8000000000000000uLL;
        }
        v75 = v73 + (unsigned int)(int)v74;
        v76 = v75 + *(_QWORD *)(v8 + 64);
        if ( v76 < v75 )
        {
          std::wstring::_Tidy_deallocate(v120);
          std::wstring::_Tidy_deallocate(v123);
          std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
          if ( (_QWORD)v93 )
          {
            std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
            v93 = 0;
            v94 = 0;
          }
          if ( (_QWORD)v95 )
            goto LABEL_118;
          goto LABEL_119;
        }
        if ( (v76 & 0x8000000000000000uLL) != 0LL )
          v77 = (double)(int)(v76 & 1 | (v76 >> 1)) + (double)(int)(v76 & 1 | (v76 >> 1));
        else
          v77 = (double)(int)v76;
        v58[9] = v77;
        goto LABEL_109;
      }
    }
LABEL_110:
    std::wstring::_Tidy_deallocate(v123);
    v8 += 80;
  }
  v79 = *(__int64 **)*a3;
  while ( !*((_BYTE *)v79 + 25) )
  {
    if ( v5 )
    {
      v80 = 0;
      if ( v5 < 0 )
        v80.m128d_f64[0] = (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1))
                         + (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1));
      else
        v80.m128d_f64[0] = (double)(int)v5;
      *((double *)v79 + 11) = *((double *)v79 + 11) / v80.m128d_f64[0] * *(double *)&_xmm;
      *(__m128d *)(v79 + 9) = _mm_mul_pd(_mm_div_pd(*(__m128d *)(v79 + 9), _mm_unpacklo_pd(v80, v80)), (__m128d)_xmm);
    }
    *(_OWORD *)(v79 + 9) = *(_OWORD *)(v79 + 9);
    *(_OWORD *)(v79 + 11) = *(_OWORD *)(v79 + 11);
    v81 = (__int64 **)v79[2];
    if ( *((_BYTE *)v81 + 25) )
    {
      for ( i = (__int64 *)v79[1]; !*((_BYTE *)i + 25) && v79 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v79 = i;
      v79 = i;
    }
    else
    {
      v79 = (__int64 *)v79[2];
      for ( j = *v81; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v79 = j;
    }
  }
  v84 = 0;
  if ( v5 < 0 )
    v84.m128d_f64[0] = (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1))
                     + (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1));
  else
    v84.m128d_f64[0] = (double)(int)v5;
  v85 = _mm_unpacklo_pd(v84, v84);
  *(__int128 *)((char *)&xmmword_180079E00 + 8) = (__int128)_mm_mul_pd(
                                                              _mm_div_pd(
                                                                *(__m128d *)((char *)&xmmword_180079E00 + 8),
                                                                v85),
                                                              (__m128d)_xmm);
  *(double *)&xmmword_180079E00 = *(double *)&xmmword_180079E00 / v85.m128d_f64[0] * *(double *)&_xmm;
  SystemSettings::BatteryUsageHandlers::mergeTimeRanges(&v95);
  SystemSettings::BatteryUsageHandlers::mergeTimeRanges(&v93);
  HIDWORD(qword_180079E18) = SystemSettings::BatteryUsageHandlers::getAggregatedTimeInMscFromTimeRanges(&v95);
  LODWORD(qword_180079E18) = SystemSettings::BatteryUsageHandlers::getAggregatedTimeInMscFromTimeRanges(&v93);
  v86 = v107;
  for ( k = (_QWORD *)*v107; k != v86; k = (_QWORD *)*k )
  {
    SystemSettings::BatteryUsageHandlers::mergeTimeRanges(k + 7);
    AggregatedTimeInMscFromTimeRanges = SystemSettings::BatteryUsageHandlers::getAggregatedTimeInMscFromTimeRanges(k + 7);
    *(_DWORD *)(*(_QWORD *)std::map<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::App_Usage,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,SystemSettings::BatteryUsageHandlers::App_Usage>>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                             a3,
                             (__int64)v101,
                             (__int64)(k + 2))
              + 100LL) = AggregatedTimeInMscFromTimeRanges;
  }
  v88 = v105;
  for ( m = (_QWORD *)*v105; m != v88; m = (_QWORD *)*m )
  {
    SystemSettings::BatteryUsageHandlers::mergeTimeRanges(m + 7);
    v91 = SystemSettings::BatteryUsageHandlers::getAggregatedTimeInMscFromTimeRanges(m + 7);
    *(_DWORD *)(*(_QWORD *)std::map<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::App_Usage,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,SystemSettings::BatteryUsageHandlers::App_Usage>>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(
                             a3,
                             (__int64)v101,
                             (__int64)(m + 2))
              + 96LL) = v91;
  }
  v90 = (double)(int)(_Xtime_get_ticks() - ticks) / 10000000.0;
  ticks = a3[1];
  *(double *)&v97.wYear = v90;
  UsageGraphTelemetry::GetEnergyRecordsFromSrumRecordSetStats<double,unsigned __int64 &,unsigned __int64 &,unsigned __int64>(
    &v97,
    &qword_180079DE0,
    &qword_180079DE8,
    &ticks);
  std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>((__int64)&v99);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((__int64)&v102);
  if ( (_QWORD)v93 )
  {
    std::_Deallocate<16>((void *)v93, (struct std::nothrow_t *)((v94 - v93) & 0xFFFFFFFFFFFFFFF0uLL));
    v93 = 0;
    v94 = 0;
  }
  if ( (_QWORD)v95 )
  {
    std::_Deallocate<16>((void *)v95, (struct std::nothrow_t *)((v96 - v95) & 0xFFFFFFFFFFFFFFF0uLL));
    v95 = 0;
    v96 = 0;
  }
  std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>((__int64)&v104);
  std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>,0>>((__int64)&v106);
  std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>((void **)&v97.wHour);
  return 0;
}

```

## disassembly

```asm
0x1800403f8  mov     rax, rsp
0x1800403fb  mov     [rax+8], rbx
0x1800403ff  mov     [rax+20h], rsi
0x180040403  push    rdi
0x180040404  push    r12
0x180040406  push    r13
0x180040408  push    r14
0x18004040a  push    r15
0x18004040c  sub     rsp, 2D0h
0x180040413  movaps  xmmword ptr [rax-38h], xmm6
0x180040417  movaps  xmmword ptr [rax-48h], xmm7
0x18004041b  mov     rax, cs:__security_cookie
0x180040422  xor     rax, rsp
0x180040425  mov     [rsp+2F8h+var_50], rax
0x18004042d  mov     r12, r8
0x180040430  mov     rsi, rdx
0x180040433  call    cs:__imp__Xtime_get_ticks
0x180040439  mov     [rsp+2F8h+var_290], rax
0x18004043e  xor     r14d, r14d
0x180040441  mov     edi, r14d
0x180040444  call    ?LoadAppList@ThrottlePolicyManager@BatteryUsageHandlers@SystemSettings@@QEAAXXZ; SystemSettings::BatteryUsageHandlers::ThrottlePolicyManager::LoadAppList(void)
0x180040449  lea     rdx, [rsp+2F8h+var_2A8.wHour]
0x18004044e  call    ?GetThrottleableApps@ThrottlePolicyManager@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@XZ; SystemSettings::BatteryUsageHandlers::ThrottlePolicyManager::GetThrottleableApps(void)
0x180040453  nop
0x180040454  lea     rcx, [rsp+2F8h+var_1B8]
0x18004045c  call    ??0?$unordered_map@UAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@UAppIdentityHash@23@UAppIdentityEquals@23@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@5@@std@@QEAA@XZ; std::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>(void)
0x180040461  nop
0x180040462  lea     rcx, [rsp+2F8h+var_1F8]
0x18004046a  call    ??0?$unordered_map@UAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@UAppIdentityHash@23@UAppIdentityEquals@23@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@5@@std@@QEAA@XZ; std::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>(void)
0x18004046f  nop
0x180040470  xorps   xmm0, xmm0
0x180040473  movdqu  [rsp+2F8h+var_2C0], xmm0
0x180040479  mov     [rsp+2F8h+var_2B0], r14
0x18004047e  movdqu  [rsp+2F8h+var_2D8], xmm0
0x180040484  mov     [rsp+2F8h+var_2C8], r14
0x180040489  mov     rcx, r12
0x18004048c  call    ?clear@?$_Tree@V?$_Tmap_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UApp_Usage@23@UAppIdentityCompare@23@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@UApp_Usage@23@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::App_Usage,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,SystemSettings::BatteryUsageHandlers::App_Usage>>,0>>::clear(void)
0x180040491  lea     rcx, [rsp+2F8h+var_238]
0x180040499  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x18004049e  nop
0x18004049f  lea     rcx, [rsp+2F8h+var_288]
0x1800404a4  call    ??0?$unordered_map@UAppIdentity@BatteryUsageHandlers@SystemSettings@@_NUAppIdentityHash@23@UAppIdentityEquals@23@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@std@@@std@@QEAA@XZ; std::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>>::unordered_map<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>>(void)
0x1800404a9  nop
0x1800404aa  mov     rbx, [rsi]
0x1800404ad  mov     r13, [rsi+8]
0x1800404b1  mov     r14, 8000000000000000h
0x1800404bb  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x1800404c3  movsd   xmm6, cs:__real@43e0000000000000
0x1800404cb  cmp     rbx, r13
0x1800404ce  jz      loc_18004101B
0x1800404d4  xorps   xmm0, xmm0
0x1800404d7  movups  [rsp+2F8h+var_90], xmm0
0x1800404df  movdqu  [rsp+2F8h+var_80], xmm7
0x1800404e8  xor     esi, esi
0x1800404ea  mov     word ptr [rsp+2F8h+var_90], si
0x1800404f2  cmp     dword ptr [rbx+20h], 1
0x1800404f6  jnz     loc_1800405A1
0x1800404fc  mov     r8, rbx
0x1800404ff  lea     rdx, [rsp+2F8h+var_178]
0x180040507  lea     rcx, [rsp+2F8h+var_238]
0x18004050f  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180040514  mov     rcx, [rsp+2F8h+var_230]
0x18004051c  cmp     [rax], rcx
0x18004051f  jnz     short loc_180040573
0x180040521  mov     rcx, rbx
0x180040524  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040529  mov     rdx, rax
0x18004052c  lea     rcx, [rsp+2F8h+var_70]
0x180040534  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x180040539  mov     rsi, rax
0x18004053c  mov     r8, rbx
0x18004053f  lea     rdx, [rsp+2F8h+var_160]
0x180040547  lea     rcx, [rsp+2F8h+var_238]
0x18004054f  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180040554  mov     rcx, [rax]
0x180040557  add     rcx, 30h ; '0'
0x18004055b  mov     rdx, rsi
0x18004055e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180040563  nop
0x180040564  lea     rcx, [rsp+2F8h+var_70]
0x18004056c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040571  xor     esi, esi
0x180040573  mov     r8, rbx
0x180040576  lea     rdx, [rsp+2F8h+var_150]
0x18004057e  lea     rcx, [rsp+2F8h+var_238]
0x180040586  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18004058b  mov     rdx, [rax]
0x18004058e  add     rdx, 30h ; '0'
0x180040592  lea     rcx, [rsp+2F8h+var_90]
0x18004059a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004059f  jmp     short loc_1800405B1
0x1800405a1  mov     rdx, rbx
0x1800405a4  lea     rcx, [rsp+2F8h+var_90]
0x1800405ac  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800405b1  mov     qword ptr [rsp+2F8h+var_2A8.wYear], rsi
0x1800405b6  lea     rcx, [rbx+30h]; this
0x1800405ba  lea     rdx, [rsp+2F8h+var_2A8]; struct _SYSTEMTIME *
0x1800405bf  call    ?SystemTimeToTimestamp@TimeFormatUtils@@YAHPEAU_SYSTEMTIME@@PEA_K@Z; TimeFormatUtils::SystemTimeToTimestamp(_SYSTEMTIME *,unsigned __int64 *)
0x1800405c4  cmp     [rbx+2Ch], esi
0x1800405c7  jnz     short loc_1800405CE
0x1800405c9  jmp     loc_180040E97
0x1800405ce  imul    r8d, [rbx+2Ch], 2710h
0x1800405d6  mov     rcx, qword ptr [rsp+2F8h+var_2A8.wYear]
0x1800405db  mov     r9, rcx
0x1800405de  sub     r9, r8
0x1800405e1  cmp     r9, cs:qword_180079DE0
0x1800405e8  cmovbe  r9, cs:qword_180079DE0
0x1800405f0  mov     rdx, cs:qword_180079DE8
0x1800405f7  cmp     rcx, rdx
0x1800405fa  cmovb   rdx, rcx
0x1800405fe  cmp     rdx, r9
0x180040601  jbe     short loc_1800405C9
0x180040603  mov     qword ptr [rsp+2F8h+var_C8], r9
0x18004060b  mov     qword ptr [rsp+2F8h+var_C8+8], rdx
0x180040613  sub     rdx, r9
0x180040616  xorps   xmm1, xmm1
0x180040619  js      short loc_180040622
0x18004061b  cvtsi2sd xmm1, rdx
0x180040620  jmp     short loc_180040637
0x180040622  mov     rax, rdx
0x180040625  shr     rax, 1
0x180040628  and     edx, 1
0x18004062b  or      rax, rdx
0x18004062e  cvtsi2sd xmm1, rax
0x180040633  addsd   xmm1, xmm1
0x180040637  xorps   xmm0, xmm0
0x18004063a  test    r8, r8
0x18004063d  js      short loc_180040646
0x18004063f  cvtsi2sd xmm0, r8
0x180040644  jmp     short loc_18004065C
0x180040646  mov     rax, r8
0x180040649  shr     rax, 1
0x18004064c  and     r8d, 1
0x180040650  or      rax, r8
0x180040653  cvtsi2sd xmm0, rax
0x180040658  addsd   xmm0, xmm0
0x18004065c  divsd   xmm1, xmm0
0x180040660  mov     rcx, [rbx+40h]
0x180040664  xorps   xmm0, xmm0
0x180040667  test    rcx, rcx
0x18004066a  js      short loc_180040673
0x18004066c  cvtsi2sd xmm0, rcx
0x180040671  jmp     short loc_180040688
0x180040673  mov     rax, rcx
0x180040676  shr     rax, 1
0x180040679  and     ecx, 1
0x18004067c  or      rax, rcx
0x18004067f  cvtsi2sd xmm0, rax
0x180040684  addsd   xmm0, xmm0
0x180040688  mulsd   xmm0, xmm1
0x18004068c  xor     eax, eax
0x18004068e  comisd  xmm0, xmm6
0x180040692  jb      short loc_1800406A1
0x180040694  subsd   xmm0, xmm6
0x180040698  comisd  xmm0, xmm6
0x18004069c  jnb     short loc_1800406A1
0x18004069e  mov     rax, r14
0x1800406a1  cvttsd2si r15, xmm0
0x1800406a6  add     r15, rax
0x1800406a9  mov     [rbx+40h], r15
0x1800406ad  mov     rcx, [rbx+48h]
0x1800406b1  xorps   xmm0, xmm0
0x1800406b4  test    rcx, rcx
0x1800406b7  js      short loc_1800406C0
0x1800406b9  cvtsi2sd xmm0, rcx
0x1800406be  jmp     short loc_1800406D5
0x1800406c0  mov     rax, rcx
0x1800406c3  shr     rax, 1
0x1800406c6  and     ecx, 1
0x1800406c9  or      rax, rcx
0x1800406cc  cvtsi2sd xmm0, rax
0x1800406d1  addsd   xmm0, xmm0
0x1800406d5  mulsd   xmm0, xmm1
0x1800406d9  xor     ecx, ecx
0x1800406db  comisd  xmm0, xmm6
0x1800406df  jb      short loc_1800406EE
0x1800406e1  subsd   xmm0, xmm6
0x1800406e5  comisd  xmm0, xmm6
0x1800406e9  jnb     short loc_1800406EE
0x1800406eb  mov     rcx, r14
0x1800406ee  cvttsd2si rax, xmm0
0x1800406f3  add     rax, rcx
0x1800406f6  mov     [rbx+48h], rax
0x1800406fa  lea     rdx, [rsp+2F8h+var_90]
0x180040702  lea     rcx, [rsp+2F8h+var_B8]
0x18004070a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004070f  mov     eax, [rbx+20h]
0x180040712  mov     [rsp+2F8h+var_98], eax
0x180040719  xor     eax, eax
0x18004071b  mov     [rsp+2F8h+var_94], eax
0x180040722  lea     r8, [rsp+2F8h+var_B8]
0x18004072a  lea     rdx, [rsp+2F8h+var_170]
0x180040732  lea     rcx, [rsp+2F8h+var_2A8.wHour]
0x180040737  call    ?find@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@2@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::find(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x18004073c  mov     rcx, qword ptr [rsp+2F8h+var_2A8.wHour]
0x180040741  cmp     [rax], rcx
0x180040744  setz    r14b
0x180040748  lea     r8, [rsp+2F8h+var_B8]
0x180040750  lea     rdx, [rsp+2F8h+var_168]
0x180040758  lea     rcx, [rsp+2F8h+var_288]
0x18004075d  call    ?find@?$_Hash@V?$_Umap_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@_NV?$_Uhash_compare@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityHash@23@UAppIdentityEquals@23@@std@@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@std@@@std@@@2@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::find(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x180040762  mov     rcx, [rsp+2F8h+var_280]
0x180040767  cmp     [rax], rcx
0x18004076a  jnz     short loc_1800407D1
0x18004076c  lea     r8, [rsp+2F8h+var_B8]
0x180040774  lea     rdx, [rsp+2F8h+var_140]
0x18004077c  lea     rcx, [rsp+2F8h+var_288]
0x180040781  call    ??$_Try_emplace@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@$$V@?$_Hash@V?$_Umap_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@_NV?$_Uhash_compare@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityHash@23@UAppIdentityEquals@23@@std@@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@PEAX@std@@_N@1@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x180040786  mov     rsi, [rax]
0x180040789  lea     rdx, [rsp+2F8h+var_B8]; struct SystemSettings::BatteryUsageHandlers::AppIdentity *
0x180040791  lea     rcx, [rsp+2F8h+var_F0]; this
0x180040799  call    ??0AppIdentity@BatteryUsageHandlers@SystemSettings@@QEAA@AEBU012@@Z; SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x18004079e  lea     r8, [rsi+38h]
0x1800407a2  mov     rdx, rax
0x1800407a5  call    ?IsApp@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJUAppIdentity@23@PEA_N@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::IsApp(SystemSettings::BatteryUsageHandlers::AppIdentity,bool *)
0x1800407aa  xor     esi, esi
0x1800407ac  test    eax, eax
0x1800407ae  jns     short loc_1800407D1
0x1800407b0  lea     r8, [rsp+2F8h+var_B8]
0x1800407b8  lea     rdx, [rsp+2F8h+var_130]
0x1800407c0  lea     rcx, [rsp+2F8h+var_288]
0x1800407c5  call    ??$_Try_emplace@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@$$V@?$_Hash@V?$_Umap_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@_NV?$_Uhash_compare@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityHash@23@UAppIdentityEquals@23@@std@@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@PEAX@std@@_N@1@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x1800407ca  mov     rax, [rax]
0x1800407cd  mov     [rax+38h], sil
0x1800407d1  lea     r8, [rsp+2F8h+var_B8]
0x1800407d9  lea     rdx, [rsp+2F8h+var_120]
0x1800407e1  lea     rcx, [rsp+2F8h+var_288]
0x1800407e6  call    ??$_Try_emplace@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@$$V@?$_Hash@V?$_Umap_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@_NV?$_Uhash_compare@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityHash@23@UAppIdentityEquals@23@@std@@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@PEAX@std@@_N@1@AEBUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::_Try_emplace<SystemSettings::BatteryUsageHandlers::AppIdentity const &,>(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x1800407eb  mov     rax, [rax]
0x1800407ee  cmp     [rax+38h], sil
0x1800407f2  jnz     loc_180040BDA
0x1800407f8  test    r14b, r14b
0x1800407fb  jz      loc_180040BDA
0x180040801  test    byte ptr [rbx+24h], 2
0x180040805  jz      loc_18004096D
0x18004080b  cmp     [rbx+48h], rsi
0x18004080f  jz      loc_18004096D
0x180040815  xor     eax, eax
0x180040817  movsd   xmm0, cs:qword_180079E10
0x18004081f  mov     r14, 8000000000000000h
0x180040829  comisd  xmm0, xmm6
0x18004082d  jb      short loc_18004083C
0x18004082f  subsd   xmm0, xmm6
0x180040833  comisd  xmm0, xmm6
0x180040837  jnb     short loc_18004083C
0x180040839  mov     rax, r14
0x18004083c  cvttsd2si rcx, xmm0
0x180040841  add     rcx, rax
0x180040844  mov     rdx, [rbx+40h]
0x180040848  add     rdx, rcx
0x18004084b  cmp     rdx, rcx
0x18004084e  jb      short loc_1800408B6
0x180040850  xorps   xmm0, xmm0
0x180040853  test    rdx, rdx
0x180040856  js      short loc_18004085F
0x180040858  cvtsi2sd xmm0, rdx
0x18004085d  jmp     short loc_180040874
0x18004085f  mov     rax, rdx
0x180040862  shr     rax, 1
0x180040865  and     edx, 1
0x180040868  or      rax, rdx
0x18004086b  cvtsi2sd xmm0, rax
0x180040870  addsd   xmm0, xmm0
0x180040874  movsd   cs:qword_180079E10, xmm0
0x18004087c  mov     rdx, qword ptr [rsp+2F8h+var_2C0+8]
0x180040881  cmp     rdx, [rsp+2F8h+var_2B0]
0x180040886  jz      short loc_18004089F
0x180040888  movups  xmm0, [rsp+2F8h+var_C8]
0x180040890  movdqu  xmmword ptr [rdx], xmm0
0x180040894  add     qword ptr [rsp+2F8h+var_2C0+8], 10h
0x18004089a  jmp     loc_180040A0A
0x18004089f  lea     r8, [rsp+2F8h+var_C8]
0x1800408a7  lea     rcx, [rsp+2F8h+var_2C0]
0x1800408ac  call    ??$_Emplace_reallocate@UEnergyEstimationRow@@@?$vector@UEnergyEstimationRow@@V?$allocator@UEnergyEstimationRow@@@std@@@std@@AEAAPEAUEnergyEstimationRow@@QEAU2@$$QEAU2@@Z; std::vector<EnergyEstimationRow>::_Emplace_reallocate<EnergyEstimationRow>(EnergyEstimationRow * const,EnergyEstimationRow &&)
0x1800408b1  jmp     loc_180040A0A
0x1800408b6  lea     rcx, [rsp+2F8h+var_B8]
0x1800408be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800408c3  nop
0x1800408c4  lea     rcx, [rsp+2F8h+var_90]
0x1800408cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800408d1  nop
0x1800408d2  lea     rcx, [rsp+2F8h+var_288]
0x1800408d7  call    ??1?$_Hash@V?$_Umap_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@_NV?$_Uhash_compare@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityHash@23@UAppIdentityEquals@23@@std@@V?$allocator@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@_N@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>::~_Hash<std::_Umap_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,bool,std::_Uhash_compare<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityHash,SystemSettings::BatteryUsageHandlers::AppIdentityEquals>,std::allocator<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,bool>>,0>>(void)
0x1800408dc  nop
0x1800408dd  lea     rcx, [rsp+2F8h+var_238]
0x1800408e5  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800408ea  nop
0x1800408eb  mov     rcx, qword ptr [rsp+2F8h+var_2D8]
0x1800408f0  test    rcx, rcx
0x1800408f3  jz      short loc_180040914
0x1800408f5  mov     rdx, [rsp+2F8h+var_2C8]
0x1800408fa  sub     rdx, rcx
0x1800408fd  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180040901  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040906  xorps   xmm0, xmm0
0x180040909  movdqu  [rsp+2F8h+var_2D8], xmm0
0x18004090f  mov     [rsp+2F8h+var_2C8], rsi
0x180040914  mov     rcx, qword ptr [rsp+2F8h+var_2C0]
0x180040919  test    rcx, rcx
0x18004091c  jz      short loc_18004093D
  ... truncated ...
```
