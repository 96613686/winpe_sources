# MpWatchDog::Wd1dsManager::Initialize(void)

- ea: `0x1400ae494`
- end: `0x1400af54a`
- name: `?Initialize@Wd1dsManager@MpWatchDog@@AEAAXXZ`
- size: `4278`
- prototype: `void __fastcall(MpWatchDog::Wd1dsManager *__hidden this)`
- caller_count: `1`
- callee_count: `53`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400ad630`

## callees

- `0x14000bf54`
- `0x140013394`
- `0x140014ac8`
- `0x140015528`
- `0x140017990`
- `0x14003a0f4`
- `0x14003a130`
- `0x14003a360`
- `0x14003a3c0`
- `0x14003a430`
- `0x14003a5c0`
- `0x14003c78c`
- `0x140049330`
- `0x14005a270`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007e088`
- `0x14007e14c`
- `0x14007f0f4`
- `0x1400820b4`
- `0x1400833d4`
- `0x140084a18`
- `0x140084a8c`
- `0x140084bb4`
- `0x140085d38`
- `0x140085d94`
- `0x1400876a0`
- `0x14008d1fc`
- `0x14008e9a8`
- `0x14009d8e0`
- `0x1400a3370`
- `0x1400a5128`
- `0x1400a54b0`
- `0x1400a5974`
- `0x1400a70b4`
- `0x1400a84a8`
- `0x1400a8ae0`
- `0x1400a94f0`
- `0x1400aa2b0`
- `0x1400aa334`
- `0x1400aaab8`
- `0x1400ab430`
- `0x1400adfac`
- `0x1400ae02c`
- `0x1400ae164`
- `0x1400ae494`
- `0x1400af85c`
- `0x1400b17b0`
- `0x1400e6ab0`
- `0x1401044d8`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x1400ae549`
- `KERNEL32!DeleteFileA` at `0x1400ae549`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400af1e0`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400af1e0`
- `KERNEL32!AcquireSRWLockShared` at `0x1400ae566`
- `KERNEL32!AcquireSRWLockShared` at `0x1400aed3b`
- `KERNEL32!AcquireSRWLockShared` at `0x1400ae566`
- `KERNEL32!AcquireSRWLockShared` at `0x1400aed3b`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400ae58f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400aedc0`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400ae58f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400aedc0`

## string_xrefs

- `0x1400ae89b`: `DefenderCommon`
- `0x1400af07a`: `eventCollectorUri`
- `0x1400af01a`: `cacheMemorySizeLimitInBytes`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
void __fastcall MpWatchDog::Wd1dsManager::Initialize(MpWatchDog::Wd1dsManager *this)
{
  struct I1dsListenerEvents *v1; // r13
  RTL_SRWLOCK *v2; // rdi
  int ProductAppDataPath; // eax
  int v4; // eax
  int v5; // edx
  const wchar_t *v6; // r8
  unsigned int v7; // eax
  wchar_t **v8; // rdx
  int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  int v11; // r13d
  __m128i si128; // xmm6
  wchar_t *v13; // rax
  struct I1dsListenerEvents *v14; // r15
  __int64 *v15; // rdi
  int v16; // r12d
  unsigned __int64 v17; // r8
  _OWORD *v18; // rdx
  _QWORD *v19; // rax
  unsigned __int64 v20; // rdi
  MpWatchDog::Wd1dsManager *v21; // rbx
  int v22; // eax
  wchar_t *v23; // rdx
  unsigned __int64 v24; // r8
  _OWORD *v25; // rdx
  __int128 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r12
  _QWORD *v29; // rax
  wchar_t *v30; // rdx
  unsigned __int64 v31; // r8
  struct EventFrequencyMonitor *v32; // rdx
  unsigned int v33; // r8d
  const wchar_t *v34; // r9
  __int64 v35; // r12
  wchar_t *v36; // rbx
  unsigned __int64 v37; // rdi
  const wchar_t *v38; // rcx
  int v39; // eax
  int v40; // edi
  __int64 v41; // rdi
  const char *v42; // rdx
  size_t v43; // r8
  char *v44; // rdx
  size_t v45; // r8
  MpWatchDog *v46; // rcx
  void **v47; // r8
  void **MiscConfigString; // rax
  const struct std::nothrow_t *v49; // rdx
  MpWatchDog::Wd1dsManager *v50; // rdi
  const struct std::nothrow_t *v51; // rdx
  __int64 v52; // r8
  void **v53; // rcx
  size_t v54; // rdi
  void **v55; // r9
  void *v56; // r13
  __int128 *v57; // rdx
  void **v58; // rdx
  size_t v59; // r8
  char v60; // di
  __int128 *v61; // r13
  MpWatchDog *v62; // rcx
  __m128i *v63; // rbx
  unsigned int v64; // edi
  __int64 DebugEventSource; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  unsigned int v69; // edi
  __int64 v70; // rax
  __int64 v71; // rax
  MpWatchDog *v72; // rcx
  char IsCoreSvcInDevMode; // di
  __int64 v74; // rax
  struct I1dsListenerEvents *v75; // r13
  CommonUtil *v76; // rcx
  unsigned int v77; // edi
  unsigned int v78; // r12d
  unsigned __int64 SystemTimeAsUlong64; // rax
  unsigned __int64 v80; // r8
  unsigned __int64 v81; // r8
  int v82; // eax
  HANDLE *v83; // rdi
  int TimerQueueTimer; // eax
  const struct std::nothrow_t *v85; // rdx
  __int64 v86; // rbx
  __int64 v87; // rax
  __int64 v88; // [rsp+0h] [rbp-2B8h] BYREF
  void *v89; // [rsp+28h] [rbp-290h]
  unsigned int v90; // [rsp+30h] [rbp-288h]
  char v91; // [rsp+34h] [rbp-284h]
  struct I1dsListenerEvents *v92; // [rsp+38h] [rbp-280h]
  wchar_t *v93; // [rsp+40h] [rbp-278h] BYREF
  void *v94[2]; // [rsp+48h] [rbp-270h] BYREF
  __int128 v95; // [rsp+58h] [rbp-260h]
  MpWatchDog::Wd1dsManager *v96; // [rsp+68h] [rbp-250h]
  unsigned int v97; // [rsp+70h] [rbp-248h] BYREF
  int v98; // [rsp+74h] [rbp-244h] BYREF
  int v99; // [rsp+78h] [rbp-240h] BYREF
  unsigned int v100; // [rsp+7Ch] [rbp-23Ch] BYREF
  int pExceptionObject; // [rsp+80h] [rbp-238h] BYREF
  MpWatchDog::Wd1dsManager *v102; // [rsp+88h] [rbp-230h]
  PSRWLOCK SRWLock; // [rsp+90h] [rbp-228h]
  MpWatchDog::WdConfigManager *v104; // [rsp+98h] [rbp-220h]
  _OWORD v105[5]; // [rsp+A0h] [rbp-218h] BYREF
  const std::exception *v106; // [rsp+F8h] [rbp-1C0h] BYREF
  wchar_t *Context[2]; // [rsp+100h] [rbp-1B8h] BYREF
  __int128 v108; // [rsp+110h] [rbp-1A8h] BYREF
  __m128i v109; // [rsp+120h] [rbp-198h]
  void *Src[2]; // [rsp+130h] [rbp-188h] BYREF
  size_t Size; // [rsp+140h] [rbp-178h]
  unsigned __int64 v112; // [rsp+148h] [rbp-170h]
  wchar_t *String[2]; // [rsp+150h] [rbp-168h] BYREF
  __int128 v114; // [rsp+160h] [rbp-158h]
  LPCSTR lpFileName[2]; // [rsp+170h] [rbp-148h] BYREF
  _OWORD v116[4]; // [rsp+180h] [rbp-138h] BYREF
  unsigned int v117[3]; // [rsp+1C0h] [rbp-F8h] BYREF
  int v118; // [rsp+1CCh] [rbp-ECh]
  wchar_t **v119[4]; // [rsp+1D0h] [rbp-E8h] BYREF
  __int64 v120; // [rsp+1F0h] [rbp-C8h]
  unsigned int v121; // [rsp+1F8h] [rbp-C0h]
  wchar_t *String1[5]; // [rsp+200h] [rbp-B8h] BYREF
  char v123[56]; // [rsp+228h] [rbp-90h] BYREF
  __m128i v124; // [rsp+260h] [rbp-58h] BYREF
  __int64 v125; // [rsp+270h] [rbp-48h] BYREF

  v1 = this;
  v92 = this;
  v102 = this;
  v96 = this;
  v2 = (RTL_SRWLOCK *)MpWatchDog::gMpWdConfigManager;
  v104 = MpWatchDog::gMpWdConfigManager;
  v93 = 0;
  ProductAppDataPath = MpWatchDog::WdConfigManager::GetProductAppDataPath(MpWatchDog::gMpWdConfigManager, &v93);
  if ( ProductAppDataPath < 0 || !v93 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        28,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)ProductAppDataPath);
    pExceptionObject = -2147467259;
    throw (long *)&pExceptionObject;
  }
  lpFileName[0] = 0;
  v4 = CommonUtil::NewSprintfA((CommonUtil *)lpFileName, (char **)"%ls\\Scans\\%hs", (const char *)v93, "MdCoreSvc.db");
  if ( v4 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v4, v5);
  DeleteFileA(lpFileName[0]);
  SRWLock = v2 + 106;
  v94[0] = &v2[106];
  AcquireSRWLockShared(v2 + 106);
  LOBYTE(v94[1]) = 1;
  MpWatchDog::OnedsConfigs::OnedsConfigs(
    (MpWatchDog::OnedsConfigs *)v117,
    (const struct MpWatchDog::OnedsConfigs *)&v2[84]);
  ReleaseSRWLockShared(v2 + 106);
  v7 = v117[0];
  if ( v117[0] )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids, v117[0]);
      v7 = v117[0];
    }
    v97 = v7;
    throw (long *)&v97;
  }
  if ( v119[2] )
  {
    String[0] = 0;
    v8 = (wchar_t **)v119;
    if ( v119[3] > (wchar_t **)7 )
      v8 = v119[0];
    v9 = CommonUtil::HrDuplicateStringW((CommonUtil *)String, v8, v6);
    v11 = v9;
    if ( v9 >= 0 )
    {
      Context[0] = 0;
      v13 = wcstok(String[0], L"|", Context);
      v14 = v92;
      v15 = (__int64 *)((char *)v92 + 360);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        *(_QWORD *)&v105[0] = v13;
        v16 = (int)v13;
        if ( !v13 )
          break;
        v15 = (__int64 *)((char *)v14 + 360);
        v94[0] = (char *)v14 + 360;
        v108 = 0;
        v109 = 0;
        v17 = -1;
        do
          ++v17;
        while ( v13[v17] );
        std::wstring::_Construct<1,wchar_t const *>(&v108, v13, v17);
        v18 = (_OWORD *)*((_QWORD *)v14 + 46);
        if ( v18 == *((_OWORD **)v14 + 47) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)v14 + 360, v18, &v108);
        }
        else
        {
          *v18 = v108;
          v18[1] = v109;
          v109 = si128;
          LOWORD(v108) = 0;
          *((_QWORD *)v14 + 46) += 32LL;
        }
        std::wstring::_Tidy_deallocate(&v108);
        if ( v11 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_Sd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              31,
              (unsigned int)&WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
              v16,
              v11);
          break;
        }
        v13 = wcstok(0, L"|", Context);
      }
      std::_Sort_unchecked<std::wstring *,MpWatchDog::StringCompare>(
        *v15,
        *((_QWORD *)v96 + 46),
        (*((_QWORD *)v96 + 46) - *v15) >> 5,
        v91);
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          30,
          &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
          (unsigned int)v9);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    if ( String[0] )
      operator delete(String[0], v10);
    v1 = v92;
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  memset(&v105[1], 0, 0x40u);
  *(_QWORD *)&v105[2] = 0;
  v19 = operator new(0x70u);
  *v19 = v19;
  v19[1] = v19;
  *((_QWORD *)&v105[1] + 1) = v19;
  *((_QWORD *)&v105[2] + 1) = 0;
  v105[3] = 0;
  *(_QWORD *)&v105[4] = 7;
  *((_QWORD *)&v105[4] + 1) = 8;
  LODWORD(v105[1]) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>>>::_Assign_grow(
    (char *)&v105[2] + 8,
    16,
    v19);
  v20 = 0;
  v21 = v96;
  do
  {
    v22 = wcsicmp(L"DefenderCommon", off_140199680[v20]);
    v23 = off_140199680[v20];
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    v108 = 0;
    v109 = 0;
    if ( v22 )
    {
      std::wstring::_Construct<1,wchar_t const *>(&v108, v23, v24);
      v26 = &v108;
      if ( v109.m128i_i64[1] > 7uLL )
        v26 = (__int128 *)v108;
      v27 = std::_Hash_array_representation<wchar_t>(v26, v109.m128i_i64[0]);
      v28 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
              (_QWORD *)v1 + 48,
              v94,
              (__int64)&v108,
              v27)[1];
      if ( !v28 )
        v28 = *((_QWORD *)v1 + 49);
      std::wstring::_Tidy_deallocate(&v108);
      if ( v28 == *((_QWORD *)v21 + 49) )
      {
        memset(v116, 0, sizeof(v116));
        LODWORD(v116[0]) = 0;
        *((_QWORD *)&v116[0] + 1) = 0;
        *(_QWORD *)&v116[1] = 0;
        v29 = operator new(0x30u);
        *v29 = v29;
        v29[1] = v29;
        *((_QWORD *)&v116[0] + 1) = v29;
        *((_QWORD *)&v116[1] + 1) = 0;
        v116[2] = 0;
        *(_QWORD *)&v116[3] = 7;
        *((_QWORD *)&v116[3] + 1) = 8;
        LODWORD(v116[0]) = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>>>::_Assign_grow(
          (char *)&v116[1] + 8,
          16,
          v29);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<wchar_t const * const &>(
          v116,
          (__int64)Context,
          (const void **)&(&off_140199688)[v20]);
        v30 = off_140199680[v20];
        v108 = 0;
        v109 = 0;
        v31 = -1;
        do
          ++v31;
        while ( v30[v31] );
        std::wstring::_Construct<1,wchar_t const *>(&v108, v30, v31);
        std::_Hash<std::_Umap_traits<std::wstring,std::unordered_set<std::wstring>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unordered_set<std::wstring>>>,0>>::emplace<std::wstring,std::unordered_set<std::wstring> &>(
          (float *)v1 + 96,
          (__int64)String,
          &v108,
          (__int64)v116);
        std::wstring::_Tidy_deallocate(&v108);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wchar_t const * const,CommonUtil::AutoRefWrapper<CommonUtil::CCmdOptionsLookupMap::CSimpleMapItem>>>>>>>::_Tidy((char *)&v116[1] + 8);
        std::list<std::wstring>::~list<std::wstring>((char *)v116 + 8);
      }
      else
      {
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<wchar_t const * const &>(
          (_QWORD *)(v28 + 48),
          (__int64)v105,
          (const void **)&(&off_140199688)[v20]);
      }
    }
    else
    {
      std::wstring::_Construct<1,wchar_t const *>(&v108, v23, v24);
      v25 = (_OWORD *)*((_QWORD *)v1 + 57);
      if ( v25 == *((_OWORD **)v1 + 58) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)v1 + 448, v25, &v108);
      }
      else
      {
        *v25 = v108;
        v25[1] = v109;
        v109 = si128;
        LOWORD(v108) = 0;
        *((_QWORD *)v1 + 57) += 32LL;
      }
      std::wstring::_Tidy_deallocate(&v108);
    }
    v20 += 3LL;
  }
  while ( v20 < 327 );
  std::_Sort_unchecked<std::wstring *,MpWatchDog::StringCompare>(
    *((_QWORD *)v1 + 56),
    *((_QWORD *)v96 + 57),
    (__int64)(*((_QWORD *)v96 + 57) - *((_QWORD *)v1 + 56)) >> 5,
    v91);
  v35 = 14;
  v36 = v93;
  if ( String1[2] )
  {
    v35 = 0;
    v37 = 0;
    while ( 1 )
    {
      v38 = (const wchar_t *)String1;
      if ( String1[3] > (wchar_t *)7 )
        v38 = String1[0];
      if ( !wcsicmp(v38, (&off_140198830)[v37]) )
        break;
      ++v35;
      v37 += 3LL;
      if ( v37 >= 45 )
      {
        v86 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v87 = std::wstring::c_str(String1);
          WPP_SF_S(*(_QWORD *)(v86 + 16), 32, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids, v87);
        }
        v98 = -2089418750;
        throw (long *)&v98;
      }
    }
  }
  v39 = Wd1dsListenerInitialize(v1, v32, v33, v34);
  v40 = v39;
  if ( v39 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        33,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)v39);
    v99 = v40;
    throw (long *)&v99;
  }
  v41 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  Context[0] = (wchar_t *)v41;
  if ( dword_1401E7700 > *(_DWORD *)(v41 + 4) )
  {
    Init_thread_header(&dword_1401E7700);
    if ( dword_1401E7700 == -1 )
    {
      atexit(MpWatchDog::Wd1dsManager::Initialize_::_2_::_dynamic_atexit_destructor_for__OneDsLoggerParams__);
      Init_thread_footer(&dword_1401E7700);
    }
  }
  if ( dword_1401E7704 > *(_DWORD *)(v41 + 4) )
  {
    Init_thread_header(&dword_1401E7704);
    if ( dword_1401E7704 == -1 )
    {
      atexit(MpWatchDog::Wd1dsManager::Initialize_::_2_::_dynamic_atexit_destructor_for__oneDsDebugEventListener__);
      Init_thread_footer(&dword_1401E7704);
    }
  }
  v42 = "bb3a785178f443fda931098a5a9a306b-869d072b-93ec-4304-bf5e-a4dad92ca10c-6941";
  if ( qword_140198840[3 * v35] )
    v42 = (const char *)qword_140198840[3 * v35];
  v108 = 0;
  v109 = 0u;
  v43 = -1;
  do
    ++v43;
  while ( v42[v43] );
  std::string::_Construct<1,char const *>(&v108, v42, v43);
  v44 = (&off_140198838)[3 * v35];
  *(_OWORD *)Src = 0;
  Size = 0;
  v112 = 0;
  v45 = -1;
  do
    ++v45;
  while ( v44[v45] );
  std::string::_Construct<1,char const *>(Src, v44, v45);
  if ( MpWatchDog::MpIsCoreSvcInDevMode(v46) )
  {
    v47 = Src;
    if ( v112 > 0xF )
      v47 = (void **)Src[0];
    MiscConfigString = (void **)MpWatchDog::GetMiscConfigString(v94, L"MdCoreSvc_1dsEndpointUrl", v47);
    v50 = (MpWatchDog::Wd1dsManager *)*MiscConfigString;
    *MiscConfigString = 0;
    v96 = v50;
    if ( v94[0] )
      operator delete(v94[0], v49);
    std::string::operator=(Src);
    if ( v50 )
      operator delete(v50, v51);
  }
  AcquireSRWLockShared(SRWLock);
  v53 = (void **)((char *)v104 + 776);
  if ( (void **)((char *)v104 + 776) != Src )
  {
    v54 = Size;
    v55 = Src;
    if ( v112 > 0xF )
      v55 = (void **)Src[0];
    if ( Size > *((_QWORD *)v104 + 100) )
    {
      _mm_lfence();
      std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(v53, Size, v52, v55);
    }
    else
    {
      v56 = (char *)v104 + 776;
      if ( *((_QWORD *)v104 + 100) > 0xFu )
        v56 = *v53;
      *((_QWORD *)v104 + 99) = Size;
      memmove(v56, v55, v54);
      *((_BYTE *)v56 + v54) = 0;
    }
  }
  ReleaseSRWLockShared(SRWLock);
  v104 = (MpWatchDog::WdConfigManager *)String;
  *(_OWORD *)String = 0;
  v114 = 0u;
  v57 = &v108;
  if ( v109.m128i_i64[1] > 0xFuLL )
    v57 = (__int128 *)v108;
  std::string::_Construct<2,char const *>((__int64)String, v57, v109.m128i_u64[0]);
  v58 = Src;
  if ( v112 > 0xF )
    v58 = (void **)Src[0];
  *(_OWORD *)v94 = 0;
  v95 = 0u;
  v59 = -1;
  do
    ++v59;
  while ( *((_BYTE *)v58 + v59) );
  std::string::_Construct<1,char const *>(v94, v58, v59);
  v60 = 0;
  if ( v118 != dword_1401D98D0 )
  {
    dword_1401D98D0 = v118;
    v60 = 1;
  }
  v61 = &xmmword_1401D98D8;
  if ( (unsigned __int8)std::operator!=<char>(v94, &xmmword_1401D98D8) )
  {
    std::string::_Tidy_deallocate(&xmmword_1401D98D8);
    xmmword_1401D98D8 = *(_OWORD *)v94;
    xmmword_1401D98E8 = v95;
    *(_QWORD *)&v95 = 0;
    *((_QWORD *)&v95 + 1) = 15;
    LOBYTE(v94[0]) = 0;
    v60 = 1;
  }
  if ( (unsigned __int8)std::operator!=<char>(String, &xmmword_1401D98F8) )
  {
    std::string::_Tidy_deallocate(&xmmword_1401D98F8);
    xmmword_1401D98F8 = *(_OWORD *)String;
    xmmword_1401D9908 = v114;
    *(_QWORD *)&v114 = 0;
    *((_QWORD *)&v114 + 1) = 15;
    LOBYTE(String[0]) = 0;
    v60 = 1;
  }
  std::string::_Tidy_deallocate(v94);
  std::string::_Tidy_deallocate(String);
  if ( v60 || !MpWatchDog::Wd1dsManager::g_pOneDsLogger )
  {
    MpWatchDog::Wd1dsManager::LogManagerTeardown();
    v124 = _mm_load_si128((const __m128i *)&_xmm);
    v63 = &v124;
    do
    {
      v64 = v63->m128i_i32[0];
      DebugEventSource = Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::GetDebugEventSource();
      (*(void (__fastcall **)(__int64, _QWORD, _UNKNOWN ***))(*(_QWORD *)DebugEventSource + 24LL))(
        DebugEventSource,
        v64,
        &off_1401D9440);
      v66 = Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::GetDebugEventSource();
      (*(void (__fastcall **)(__int64, _QWORD, _UNKNOWN ***))(*(_QWORD *)v66 + 16LL))(v66, v64, &off_1401D9440);
      v63 = (__m128i *)((char *)v63 + 4);
    }
    while ( v63 != (__m128i *)&v125 );
    try
    {
      v36 = v93;
      if ( dword_1401E76F0 > *((_DWORD *)Context[0] + 1) )
      {
        Init_thread_header(&dword_1401E76F0);
        if ( dword_1401E76F0 == -1 )
        {
          qword_1401E76F8 = Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::GetLogConfiguration();
          Init_thread_footer(&dword_1401E76F0);
        }
      }
      v67 = Microsoft::Applications::Events::ILogConfiguration::operator[](qword_1401E76F8, "tpm");
      v68 = Microsoft::Applications::Events::Variant::operator[](v67, "maxRetryCount");
      *(_QWORD *)(v68 + 8) = 2;
      *(_DWORD *)(v68 + 88) = 1;
      v69 = dword_1401D98D0 << 20;
      v70 = Microsoft::Applications::Events::ILogConfiguration::operator[](
              qword_1401E76F8,
              "cacheMemorySizeLimitInBytes");
      *(_QWORD *)(v70 + 8) = v69;
      *(_DWORD *)(v70 + 88) = 1;
      v104 = (MpWatchDog::WdConfigManager *)v94;
      *(_OWORD *)v94 = 0;
      v95 = 0u;
      if ( *((_QWORD *)&xmmword_1401D98E8 + 1) > 0xFu )
        v61 = (__int128 *)xmmword_1401D98D8;
      std::string::_Construct<2,char const *>((__int64)v94, v61, xmmword_1401D98E8);
      v71 = Microsoft::Applications::Events::ILogConfiguration::operator[](qword_1401E76F8, "eventCollectorUri");
      Microsoft::Applications::Events::Variant::operator=(v71, v94);
      IsCoreSvcInDevMode = MpWatchDog::MpIsCoreSvcInDevMode(v72);
      v74 = Microsoft::Applications::Events::ILogConfiguration::operator[](qword_1401E76F8, "enableTrace");
      *(_BYTE *)(v74 + 8) = IsCoreSvcInDevMode;
      *(_DWORD *)(v74 + 88) = 5;
      MpWatchDog::Wd1dsManager::g_pOneDsLogger = (struct Microsoft::Applications::Events::ILogger *)Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::Initialize(&xmmword_1401D98F8, qword_1401E76F8);
    }
    catch ( const std::exception *v106 )
    {
      CommonUtil::HrFromStdException(v106, (const struct std::exception *)&v88);
    }
    catch ( ... )
    {
      v90 = -2147467259;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids, v90);
      v100 = v90;
      throw (long *)&v100;
    }
  }
  v75 = v92;
  if ( v121 )
  {
    v77 = MpWatchDog::MpIsCoreSvcInDevMode(v62) != 0 ? 10000 : 120000;
    v78 = v77;
    if ( v120 )
    {
      SystemTimeAsUlong64 = CommonUtil::UtilGetSystemTimeAsUlong64(v76);
      v80 = v120 + 36000000000LL * v121;
      if ( SystemTimeAsUlong64 < v80 )
      {
        v81 = v80 - SystemTimeAsUlong64;
        if ( v81 >= 0x271000000000LL )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              35,
              &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
              2147942934LL);
        }
        else if ( (unsigned int)(v81 / 0x2710) > v77 )
        {
          v78 = v81 / 0x2710;
        }
      }
    }
    v82 = 3600000 * v121;
    v90 = 3600000 * v121;
    v83 = (HANDLE *)((char *)v92 + 312);
    if ( *((_QWORD *)v92 + 39) )
    {
      DeleteTimerQueueTimer(0, *v83, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *v83 = 0;
      v82 = v90;
    }
    LODWORD(v89) = 0;
    TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                        (struct I1dsListenerEvents *)((char *)v75 + 312),
                        (void **)v78,
                        v82,
                        (unsigned int)MpWatchDog::Wd1dsManager::HeartbeatTimerCallback,
                        (void (*)(void *, unsigned __int8))v75,
                        v89,
                        v90);
    if ( TimerQueueTimer < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        36,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)TimerQueueTimer);
    }
  }
  MpWatchDog::Wd1dsManager::m_bReset1DSMonitorCallbackStatus = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 37, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids);
  std::string::_Tidy_deallocate(Src);
  std::string::_Tidy_deallocate(&v108);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wchar_t const * const,CommonUtil::AutoRefWrapper<CommonUtil::CCmdOptionsLookupMap::CSimpleMapItem>>>>>>>::_Tidy((char *)&v105[2] + 8);
  __1__list_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__unordered_set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2__std__V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__unordered_set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2__std___2__std__QEAA_XZ((char *)&v105[1] + 8);
  std::string::_Tidy_deallocate(v123);
  std::wstring::_Tidy_deallocate(String1);
  std::wstring::_Tidy_deallocate(v119);
  if ( lpFileName[0] )
    operator delete((void *)lpFileName[0], v85);
  if ( v36 )
    operator delete(v36, v85);
}

```

## disassembly

```asm
0x1400ae494  mov     rax, rsp
0x1400ae497  mov     [rax+10h], rbx
0x1400ae49b  mov     [rax+18h], rsi
0x1400ae49f  push    rdi
0x1400ae4a0  push    r12
0x1400ae4a2  push    r13
0x1400ae4a4  push    r14
0x1400ae4a6  push    r15
0x1400ae4a8  sub     rsp, 290h
0x1400ae4af  movaps  xmmword ptr [rax-38h], xmm6
0x1400ae4b3  mov     rax, cs:__security_cookie
0x1400ae4ba  xor     rax, rsp
0x1400ae4bd  mov     [rsp+2B8h+var_48], rax
0x1400ae4c5  mov     r13, rcx
0x1400ae4c8  mov     [rsp+2B8h+var_280], rcx
0x1400ae4cd  mov     [rsp+2B8h+var_230], rcx
0x1400ae4d5  mov     [rsp+2B8h+var_250], rcx
0x1400ae4da  xor     esi, esi
0x1400ae4dc  mov     rdi, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400ae4e3  mov     [rsp+2B8h+var_220], rdi
0x1400ae4eb  mov     [rsp+2B8h+var_278], rsi
0x1400ae4f0  lea     rdx, [rsp+2B8h+var_278]; wchar_t **
0x1400ae4f5  mov     rcx, rdi; this
0x1400ae4f8  call    ?GetProductAppDataPath@WdConfigManager@MpWatchDog@@QEAAJPEAPEA_W@Z; MpWatchDog::WdConfigManager::GetProductAppDataPath(wchar_t * *)
0x1400ae4fd  test    eax, eax
0x1400ae4ff  js      loc_1400AF319
0x1400ae505  mov     rbx, [rsp+2B8h+var_278]
0x1400ae50a  test    rbx, rbx
0x1400ae50d  jz      loc_1400AF319
0x1400ae513  mov     [rsp+2B8h+lpFileName], rsi
0x1400ae51b  lea     r9, aMdcoresvcDb; "MdCoreSvc.db"
0x1400ae522  mov     r8, rbx; char *
0x1400ae525  lea     rdx, aLsScansHs; "%ls\\Scans\\%hs"
0x1400ae52c  lea     rcx, [rsp+2B8h+lpFileName]; this
0x1400ae534  call    ?NewSprintfA@CommonUtil@@YAJPEAPEADPEBDZZ; CommonUtil::NewSprintfA(char * *,char const *,...)
0x1400ae539  test    eax, eax
0x1400ae53b  js      loc_1400AF36F
0x1400ae541  mov     rcx, [rsp+2B8h+lpFileName]; lpFileName
0x1400ae549  call    cs:__imp_DeleteFileA
0x1400ae54f  lea     r15, [rdi+350h]
0x1400ae556  mov     [rsp+2B8h+SRWLock], r15
0x1400ae55e  mov     [rsp+2B8h+var_270], r15
0x1400ae563  mov     rcx, r15; SRWLock
0x1400ae566  call    cs:__imp_AcquireSRWLockShared
0x1400ae56c  mov     r14d, 1
0x1400ae572  mov     byte ptr [rsp+2B8h+var_270+8], r14b
0x1400ae577  lea     rdx, [rdi+2A0h]; struct MpWatchDog::OnedsConfigs *
0x1400ae57e  lea     rcx, [rsp+2B8h+var_F8]; this
0x1400ae586  call    ??0OnedsConfigs@MpWatchDog@@QEAA@AEBU01@@Z; MpWatchDog::OnedsConfigs::OnedsConfigs(MpWatchDog::OnedsConfigs const &)
0x1400ae58b  nop
0x1400ae58c  mov     rcx, r15; SRWLock
0x1400ae58f  call    cs:__imp_ReleaseSRWLockShared
0x1400ae595  nop
0x1400ae596  mov     eax, [rsp+2B8h+var_F8]
0x1400ae59d  test    eax, eax
0x1400ae59f  jnz     loc_1400AF377
0x1400ae5a5  cmp     [rsp+2B8h+var_D8], rsi
0x1400ae5ad  jz      loc_1400AE92D
0x1400ae5b3  mov     [rsp+2B8h+String], rsi
0x1400ae5bb  lea     rdx, [rsp+2B8h+var_E8]
0x1400ae5c3  cmp     [rsp+2B8h+var_D0], 7
0x1400ae5cc  cmova   rdx, [rsp+2B8h+var_E8]; wchar_t **
0x1400ae5d5  lea     rcx, [rsp+2B8h+String]; this
0x1400ae5dd  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x1400ae5e2  mov     r13d, eax
0x1400ae5e5  test    eax, eax
0x1400ae5e7  jns     short loc_1400AE627
0x1400ae5e9  lea     r15, WPP_GLOBAL_Control
0x1400ae5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae5f7  cmp     rcx, r15
0x1400ae5fa  jz      short loc_1400AE61A
0x1400ae5fc  test    byte ptr [rcx+1Ch], 2
0x1400ae600  jz      short loc_1400AE61A
0x1400ae602  mov     edx, 1Eh
0x1400ae607  mov     r9d, eax
0x1400ae60a  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400ae611  mov     rcx, [rcx+10h]
0x1400ae615  call    WPP_SF_d
0x1400ae61a  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ae622  jmp     loc_1400AE7EC
0x1400ae627  mov     [rsp+2B8h+Context], rsi
0x1400ae62f  lea     r8, [rsp+2B8h+Context]; Context
0x1400ae637  lea     rdx, asc_140196108; "|"
0x1400ae63e  mov     rcx, [rsp+2B8h+String]; String
0x1400ae646  call    wcstok
0x1400ae64b  mov     r15, [rsp+2B8h+var_280]
0x1400ae650  lea     rdi, [r15+168h]
0x1400ae657  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ae65f  mov     [rsp+2B8h+var_218], rax
0x1400ae667  mov     r12, rax
0x1400ae66a  test    rax, rax
0x1400ae66d  jz      loc_1400AE7C1
0x1400ae673  lea     rdi, [r15+168h]
0x1400ae67a  mov     [rsp+2B8h+var_270], rdi
0x1400ae67f  xorps   xmm0, xmm0
0x1400ae682  movups  [rsp+2B8h+var_1A8], xmm0
0x1400ae68a  xorps   xmm1, xmm1
0x1400ae68d  movdqu  [rsp+2B8h+var_198], xmm1
0x1400ae696  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400ae69a  inc     r8
0x1400ae69d  cmp     [r12+r8*2], si
0x1400ae6a2  jnz     short loc_1400AE69A
0x1400ae6a4  mov     rdx, r12
0x1400ae6a7  lea     rcx, [rsp+2B8h+var_1A8]
0x1400ae6af  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400ae6b4  nop
0x1400ae6b5  mov     rdx, [rdi+8]
0x1400ae6b9  cmp     rdx, [rdi+10h]
0x1400ae6bd  jz      short loc_1400AE6EE
0x1400ae6bf  movups  xmm0, [rsp+2B8h+var_1A8]
0x1400ae6c7  movups  xmmword ptr [rdx], xmm0
0x1400ae6ca  movups  xmm1, [rsp+2B8h+var_198]
0x1400ae6d2  movups  xmmword ptr [rdx+10h], xmm1
0x1400ae6d6  movdqu  [rsp+2B8h+var_198], xmm6
0x1400ae6df  mov     word ptr [rsp+2B8h+var_1A8], si
0x1400ae6e7  add     qword ptr [rdi+8], 20h ; ' '
0x1400ae6ec  jmp     short loc_1400AE6FF
0x1400ae6ee  lea     r8, [rsp+2B8h+var_1A8]
0x1400ae6f6  mov     rcx, rdi
0x1400ae6f9  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1400ae6fe  nop
0x1400ae6ff  lea     rcx, [rsp+2B8h+var_1A8]
0x1400ae707  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ae70c  nop
0x1400ae70d  jmp     short loc_1400AE73C
0x1400ae70f  xor     esi, esi
0x1400ae711  lea     r14d, [rsi+1]
0x1400ae715  mov     r13d, [rsp+2B8h+var_288]
0x1400ae71a  mov     r12, [rsp+2B8h+var_218]
0x1400ae722  mov     rdi, [rsp+2B8h+var_270]
0x1400ae727  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ae72f  mov     r15, [rsp+2B8h+var_230]
0x1400ae737  mov     [rsp+2B8h+var_280], r15
0x1400ae73c  test    r13d, r13d
0x1400ae73f  js      short loc_1400AE789
0x1400ae741  lea     r8, [rsp+2B8h+Context]; Context
0x1400ae749  lea     rdx, asc_140196108; "|"
0x1400ae750  xor     ecx, ecx; String
0x1400ae752  call    wcstok
0x1400ae757  jmp     loc_1400AE65F
0x1400ae75c  xor     esi, esi
0x1400ae75e  lea     r14d, [rsi+1]
0x1400ae762  mov     r13d, [rsp+2B8h+var_288]
0x1400ae767  mov     r12, [rsp+2B8h+var_218]
0x1400ae76f  mov     rdi, [rsp+2B8h+var_270]
0x1400ae774  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ae77c  mov     r15, [rsp+2B8h+var_230]
0x1400ae784  mov     [rsp+2B8h+var_280], r15
0x1400ae789  lea     r15, WPP_GLOBAL_Control
0x1400ae790  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae797  cmp     rcx, r15
0x1400ae79a  jz      short loc_1400AE7C8
0x1400ae79c  test    byte ptr [rcx+1Ch], 2
0x1400ae7a0  jz      short loc_1400AE7C8
0x1400ae7a2  mov     edx, 1Fh
0x1400ae7a7  mov     dword ptr [rsp+2B8h+var_298], r13d
0x1400ae7ac  mov     r9, r12
0x1400ae7af  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400ae7b6  mov     rcx, [rcx+10h]
0x1400ae7ba  call    WPP_SF_Sd
0x1400ae7bf  jmp     short loc_1400AE7C8
0x1400ae7c1  lea     r15, WPP_GLOBAL_Control
0x1400ae7c8  mov     rdx, [rsp+2B8h+var_250]
0x1400ae7cd  mov     rdx, [rdx+170h]
0x1400ae7d4  mov     r8, rdx
0x1400ae7d7  sub     r8, [rdi]
0x1400ae7da  sar     r8, 5
0x1400ae7de  mov     r9b, [rsp+2B8h+var_284]
0x1400ae7e3  mov     rcx, [rdi]
0x1400ae7e6  call    ??$_Sort_unchecked@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UStringCompare@MpWatchDog@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0_JUStringCompare@MpWatchDog@@@Z; std::_Sort_unchecked<std::wstring *,MpWatchDog::StringCompare>(std::wstring *,std::wstring *,__int64,MpWatchDog::StringCompare)
0x1400ae7eb  nop
0x1400ae7ec  mov     rcx, [rsp+2B8h+String]; void *
0x1400ae7f4  test    rcx, rcx
0x1400ae7f7  jz      short loc_1400AE7FE
0x1400ae7f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400ae7fe  mov     r13, [rsp+2B8h+var_280]
0x1400ae803  xor     edx, edx; Val
0x1400ae805  lea     r8d, [rdx+40h]; Size
0x1400ae809  lea     rcx, [rsp+2B8h+var_208]; void *
0x1400ae811  call    memset
0x1400ae816  mov     [rsp+2B8h+var_1F8], rsi
0x1400ae81e  mov     ecx, 70h ; 'p'; Size
0x1400ae823  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400ae828  mov     [rax], rax
0x1400ae82b  mov     [rax+8], rax
0x1400ae82f  mov     [rsp+2B8h+var_200], rax
0x1400ae837  mov     [rsp+2B8h+var_1F0], rsi
0x1400ae83f  xorps   xmm0, xmm0
0x1400ae842  movdqa  [rsp+2B8h+var_1E8], xmm0
0x1400ae84b  mov     [rsp+2B8h+var_1D8], 7
0x1400ae857  mov     [rsp+2B8h+var_1D0], 8
0x1400ae863  mov     [rsp+2B8h+var_208], 3F800000h
0x1400ae86e  mov     r8, rax
0x1400ae871  mov     edx, 10h
0x1400ae876  lea     rcx, [rsp+2B8h+var_1F0]
0x1400ae87e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>)
0x1400ae883  nop
0x1400ae884  mov     rdi, rsi
0x1400ae887  lea     r12, cs:140000000h
0x1400ae88e  mov     rbx, [rsp+2B8h+var_250]
0x1400ae893  mov     rdx, [rdi+r12+199680h]; String2
0x1400ae89b  lea     rcx, aDefendercommon; "DefenderCommon"
0x1400ae8a2  call    _wcsicmp
0x1400ae8a7  mov     rdx, [rdi+r12+199680h]
0x1400ae8af  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400ae8b3  inc     r8
0x1400ae8b6  cmp     [rdx+r8*2], si
0x1400ae8bb  jnz     short loc_1400AE8B3
0x1400ae8bd  xorps   xmm0, xmm0
0x1400ae8c0  xorps   xmm1, xmm1
0x1400ae8c3  lea     rcx, [rsp+2B8h+var_1A8]
0x1400ae8cb  movups  [rsp+2B8h+var_1A8], xmm0
0x1400ae8d3  movdqu  [rsp+2B8h+var_198], xmm1
0x1400ae8dc  test    eax, eax
0x1400ae8de  jnz     loc_1400AE964
0x1400ae8e4  lea     r12, [r13+1C0h]
0x1400ae8eb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400ae8f0  nop
0x1400ae8f1  mov     rdx, [r12+8]
0x1400ae8f6  cmp     rdx, [r12+10h]
0x1400ae8fb  jz      short loc_1400AE941
0x1400ae8fd  movups  xmm0, [rsp+2B8h+var_1A8]
0x1400ae905  movups  xmmword ptr [rdx], xmm0
0x1400ae908  movups  xmm1, [rsp+2B8h+var_198]
0x1400ae910  movups  xmmword ptr [rdx+10h], xmm1
0x1400ae914  movdqu  [rsp+2B8h+var_198], xmm6
0x1400ae91d  mov     word ptr [rsp+2B8h+var_1A8], si
0x1400ae925  add     qword ptr [r12+8], 20h ; ' '
0x1400ae92b  jmp     short loc_1400AE952
0x1400ae92d  lea     r15, WPP_GLOBAL_Control
0x1400ae934  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ae93c  jmp     loc_1400AE803
0x1400ae941  lea     r8, [rsp+2B8h+var_1A8]
0x1400ae949  mov     rcx, r12
0x1400ae94c  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1400ae951  nop
0x1400ae952  lea     rcx, [rsp+2B8h+var_1A8]
0x1400ae95a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ae95f  jmp     loc_1400AEB3E
0x1400ae964  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400ae969  lea     rcx, [rsp+2B8h+var_1A8]
0x1400ae971  cmp     qword ptr [rsp+2B8h+var_198+8], 7
0x1400ae97a  cmova   rcx, qword ptr [rsp+2B8h+var_1A8]
0x1400ae983  mov     rdx, qword ptr [rsp+2B8h+var_198]
0x1400ae98b  call    ??$_Hash_array_representation@_W@std@@YA_KQEB_W_K@Z; std::_Hash_array_representation<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400ae990  mov     r9, rax
0x1400ae993  lea     r8, [rsp+2B8h+var_1A8]
0x1400ae99b  lea     rdx, [rsp+2B8h+var_270]
0x1400ae9a0  lea     rcx, [r13+180h]
0x1400ae9a7  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1400ae9ac  mov     r12, [rax+8]
0x1400ae9b0  test    r12, r12
0x1400ae9b3  jnz     short loc_1400AE9BC
0x1400ae9b5  mov     r12, [r13+188h]
0x1400ae9bc  lea     rcx, [rsp+2B8h+var_1A8]
0x1400ae9c4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ae9c9  cmp     r12, [rbx+188h]
0x1400ae9d0  jnz     loc_1400AEB1B
0x1400ae9d6  xor     edx, edx; Val
0x1400ae9d8  lea     r8d, [rdx+40h]; Size
0x1400ae9dc  lea     rcx, [rsp+2B8h+var_138]; void *
0x1400ae9e4  call    memset
0x1400ae9e9  mov     [rsp+2B8h+var_138], 0
0x1400ae9f4  mov     [rsp+2B8h+var_130], rsi
0x1400ae9fc  mov     [rsp+2B8h+var_128], rsi
0x1400aea04  mov     ecx, 30h ; '0'; Size
0x1400aea09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400aea0e  mov     [rax], rax
0x1400aea11  mov     [rax+8], rax
0x1400aea15  mov     [rsp+2B8h+var_130], rax
0x1400aea1d  mov     [rsp+2B8h+var_120], rsi
0x1400aea25  xorps   xmm0, xmm0
0x1400aea28  movdqa  [rsp+2B8h+var_118], xmm0
0x1400aea31  mov     [rsp+2B8h+var_108], 7
0x1400aea3d  mov     [rsp+2B8h+var_100], 8
0x1400aea49  mov     [rsp+2B8h+var_138], 3F800000h
0x1400aea54  mov     r8, rax
0x1400aea57  mov     edx, 10h
0x1400aea5c  lea     rcx, [rsp+2B8h+var_120]
0x1400aea64  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::string>>,std::_Iterator_base0>)
0x1400aea69  nop
0x1400aea6a  lea     r12, cs:140000000h
0x1400aea71  lea     r8, rva off_140199688[r12]; "EngineRing" ...
0x1400aea79  add     r8, rdi
0x1400aea7c  lea     rdx, [rsp+2B8h+Context]
0x1400aea84  lea     rcx, [rsp+2B8h+var_138]
0x1400aea8c  call    ??$emplace@AEBQEB_W@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBQEB_W@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<wchar_t const * const &>(wchar_t const * const &)
0x1400aea91  mov     rdx, [rdi+r12+199680h]
0x1400aea99  xorps   xmm0, xmm0
0x1400aea9c  movups  [rsp+2B8h+var_1A8], xmm0
0x1400aeaa4  xorps   xmm1, xmm1
0x1400aeaa7  movdqu  [rsp+2B8h+var_198], xmm1
0x1400aeab0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400aeab4  inc     r8
0x1400aeab7  cmp     [rdx+r8*2], si
0x1400aeabc  jnz     short loc_1400AEAB4
0x1400aeabe  lea     rcx, [rsp+2B8h+var_1A8]
0x1400aeac6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400aeacb  nop
0x1400aeacc  lea     r9, [rsp+2B8h+var_138]
  ... truncated ...
```
