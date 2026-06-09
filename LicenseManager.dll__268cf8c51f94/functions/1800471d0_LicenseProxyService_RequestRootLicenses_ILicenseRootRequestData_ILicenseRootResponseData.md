# LicenseProxyService::RequestRootLicenses(ILicenseRootRequestData *,ILicenseRootResponseData * *)

- ea: `0x1800471d0`
- end: `0x18004875a`
- name: `?RequestRootLicenses@LicenseProxyService@@UEAAJPEAUILicenseRootRequestData@@PEAPEAUILicenseRootResponseData@@@Z`
- size: `5514`
- prototype: `__int64 __fastcall(LicenseProxyService *__hidden this, struct ILicenseRootRequestData *, struct ILicenseRootResponseData **)`
- caller_count: `0`
- callee_count: `51`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002b14`
- `0x180004738`
- `0x180006a48`
- `0x18000737c`
- `0x180012dc0`
- `0x180013b50`
- `0x1800174bc`
- `0x180017654`
- `0x1800192a0`
- `0x18001dad0`
- `0x18001f268`
- `0x180028b10`
- `0x18002aae8`
- `0x1800332f4`
- `0x180033c04`
- `0x180044174`
- `0x180046f88`
- `0x1800471d0`
- `0x180054a54`
- `0x1800593bc`
- `0x18005f5ac`
- `0x1800629dc`
- `0x180062a40`
- `0x18006ea5c`
- `0x18006eba8`
- `0x18006ffb8`
- `0x180073e24`
- `0x180073e90`
- `0x180075e60`
- `0x18008252b`
- `0x18008a400`
- `0x180097f40`
- `0x180098258`
- `0x1800982d4`
- `0x18009830c`
- `0x180098628`
- `0x180098894`
- `0x180098b54`
- `0x180098b9c`
- `0x180098c48`
- `0x180098ce4`
- `0x180098ecc`
- `0x180098fb8`
- `0x180099498`
- `0x1800996d0`
- `0x18009998c`
- `0x180099b4c`
- `0x18009a2a0`
- `0x18009a2fc`
- `0x18009a6a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004821e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004821e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004873f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004873f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180048132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004828c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180048132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004828c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004815c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800482bd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004815c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800482bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800482ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004833e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800482ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004833e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cb2`

## string_xrefs

- `0x1800477a1`: `LicenseProxyService::RequestRootLicenses`
- `0x1800478ce`: `LicenseProxyService::RequestRootLicenses`
- `0x180047994`: `LicenseProxyService::RequestRootLicenses`
- `0x180047a8d`: `LicenseProxyService::RequestRootLicenses`
- `0x180047d0c`: `LicenseProxyService::RequestRootLicenses`

## pseudocode

```c
// Hidden C++ exception states: #wind=39 #try_helpers=1
__int64 __fastcall LicenseProxyService::RequestRootLicenses(
        RTL_SRWLOCK *this,
        RTL_SRWLOCK *a2,
        struct ILicenseRootResponseData **a3)
{
  int v5; // eax
  int v6; // edi
  _QWORD *v7; // r14
  int v8; // eax
  unsigned int v9; // r15d
  _QWORD *v10; // r12
  __int64 size_of; // rax
  _QWORD *v12; // rax
  LPVOID v13; // rcx
  _QWORD **v14; // rcx
  _QWORD *v15; // rdx
  _QWORD *v16; // rbx
  const char *v17; // r9
  __int64 result; // rax
  int v19; // eax
  unsigned int i; // ebx
  __int64 v21; // rax
  int v22; // eax
  LPVOID v23; // rcx
  unsigned int j; // edi
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rbx
  PSRWLOCK v29; // rax
  RTL_SRWLOCK *v30; // r13
  int v31; // eax
  RTL_SRWLOCK *v32; // r12
  __int64 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  int v39; // ebx
  wchar_t *v40; // r15
  __int64 *v41; // rdi
  __int64 *k; // rbx
  const wchar_t *v43; // rcx
  __int64 v44; // rax
  size_t v45; // r8
  const wchar_t *v46; // rcx
  __int64 *v47; // rcx
  int v48; // eax
  int v49; // eax
  const wchar_t *v50; // rcx
  __int64 v51; // rbx
  int v52; // eax
  PVOID v53; // rcx
  __int64 v54; // rax
  const wchar_t *v55; // rcx
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  const wchar_t *v59; // rax
  int v60; // eax
  __int64 v61; // rax
  int v62; // eax
  int v63; // r12d
  _QWORD *v64; // rax
  _QWORD *v65; // rax
  PVOID Ptr; // rcx
  __int64 v67; // rax
  _QWORD *v68; // rbx
  void (__fastcall *v69)(_QWORD *, LPVOID *); // r15
  void *v70; // rdi
  const wchar_t *v71; // rcx
  int v72; // ecx
  int v73; // r8d
  int v74; // r9d
  const wchar_t *v75; // rax
  _QWORD *v76; // rdi
  _QWORD *m; // rbx
  _QWORD *v78; // rax
  PSRWLOCK v79; // rdi
  __int64 (__fastcall *v80)(PSRWLOCK, __int64 *); // rbx
  int v81; // eax
  PSRWLOCK v82; // rax
  RTL_SRWLOCK *v83; // r13
  PSRWLOCK v84; // r15
  char *v85; // rbx
  __int64 v86; // r8
  unsigned __int64 v87; // rdx
  const void *v88; // r9
  void **v89; // rdi
  __int64 v90; // rbx
  unsigned __int64 n; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  const char *v93; // r9
  __int64 v94; // rdx
  struct _TP_WORK *v95; // rax
  RTL_SRWLOCK *v96; // rdi
  RTL_SRWLOCK *v97; // r13
  RTL_SRWLOCK *v98; // r12
  char v99; // r15
  char *v100; // rbx
  struct _TP_WORK *v101; // rax
  const char *v102; // r9
  wil::details::in1diag3 *v103; // rcx
  int v104; // edi
  unsigned __int64 ii; // rbx
  __int64 v106; // rax
  int v107; // eax
  __int64 (__fastcall ***v108)(_QWORD, GUID *, struct ILicenseRootResponseData **); // rcx
  _QWORD **v109; // rcx
  _QWORD *v110; // rdx
  _QWORD *v111; // rbx
  RTL_SRWLOCK *v112; // rbx
  signed int LastError; // eax
  int v114; // edx
  unsigned int v115; // r8d
  signed int v116; // eax
  int v117; // edx
  unsigned int v118; // r8d
  int Format; // [rsp+20h] [rbp-2F8h]
  __int64 v120; // [rsp+38h] [rbp-2E0h]
  __int64 v121; // [rsp+40h] [rbp-2D8h] BYREF
  __int64 v122; // [rsp+48h] [rbp-2D0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-2C8h] BYREF
  int v124; // [rsp+58h] [rbp-2C0h] BYREF
  wchar_t *v125; // [rsp+60h] [rbp-2B8h] BYREF
  wchar_t *v126; // [rsp+68h] [rbp-2B0h] BYREF
  _QWORD *v127; // [rsp+70h] [rbp-2A8h] BYREF
  wchar_t *S2; // [rsp+78h] [rbp-2A0h] BYREF
  PSRWLOCK SRWLock; // [rsp+80h] [rbp-298h] BYREF
  PSRWLOCK v130; // [rsp+88h] [rbp-290h] BYREF
  struct _TP_WORK *v131; // [rsp+90h] [rbp-288h]
  LicenseProxyService::UserRootThreadParam *v132[2]; // [rsp+98h] [rbp-280h] BYREF
  LicenseProxyService::UserRootThreadParam *v133; // [rsp+A8h] [rbp-270h]
  __int128 v134; // [rsp+B0h] [rbp-268h] BYREF
  const wchar_t *v135; // [rsp+C0h] [rbp-258h] BYREF
  __int64 (__fastcall ***v136)(_QWORD, GUID *, struct ILicenseRootResponseData **); // [rsp+C8h] [rbp-250h] BYREF
  __int64 v137; // [rsp+D0h] [rbp-248h] BYREF
  __int128 v138; // [rsp+D8h] [rbp-240h] BYREF
  __int64 v139; // [rsp+E8h] [rbp-230h]
  RTL_SRWLOCK *v140; // [rsp+F0h] [rbp-228h]
  const wchar_t *v141; // [rsp+F8h] [rbp-220h] BYREF
  const wchar_t *v142; // [rsp+100h] [rbp-218h] BYREF
  PSRWLOCK v143; // [rsp+108h] [rbp-210h] BYREF
  void **v144; // [rsp+110h] [rbp-208h] BYREF
  PTP_WORK pwk; // [rsp+118h] [rbp-200h]
  _QWORD *v146; // [rsp+120h] [rbp-1F8h] BYREF
  unsigned int v147; // [rsp+128h] [rbp-1F0h]
  _QWORD *v148; // [rsp+130h] [rbp-1E8h] BYREF
  int v149; // [rsp+138h] [rbp-1E0h]
  PSRWLOCK *v150; // [rsp+140h] [rbp-1D8h] BYREF
  RTL_SRWLOCK *v151; // [rsp+148h] [rbp-1D0h]
  _QWORD v152[3]; // [rsp+150h] [rbp-1C8h] BYREF
  struct ILicenseRootResponseData **v153; // [rsp+168h] [rbp-1B0h]
  RTL_SRWLOCK *v154; // [rsp+170h] [rbp-1A8h]
  _BYTE v155[16]; // [rsp+178h] [rbp-1A0h] BYREF
  char v156[16]; // [rsp+188h] [rbp-190h] BYREF
  char v157[24]; // [rsp+198h] [rbp-180h] BYREF
  __int64 v158; // [rsp+1B0h] [rbp-168h] BYREF
  __int128 v159; // [rsp+1B8h] [rbp-160h] BYREF
  __int64 v160; // [rsp+1C8h] [rbp-150h]
  __int64 v161; // [rsp+1D0h] [rbp-148h]
  RTL_SRWLOCK *v162; // [rsp+1D8h] [rbp-140h]
  __int64 v163; // [rsp+1E0h] [rbp-138h] BYREF
  _BYTE v164[16]; // [rsp+1E8h] [rbp-130h] BYREF
  __int64 v165; // [rsp+1F8h] [rbp-120h] BYREF
  int v166; // [rsp+200h] [rbp-118h]
  char v167; // [rsp+204h] [rbp-114h]
  __int64 v168; // [rsp+210h] [rbp-108h] BYREF
  __int128 v169; // [rsp+218h] [rbp-100h] BYREF
  __int64 v170; // [rsp+228h] [rbp-F0h]
  __int64 v171; // [rsp+230h] [rbp-E8h]
  RTL_SRWLOCK *v172; // [rsp+238h] [rbp-E0h]
  __int64 v173; // [rsp+240h] [rbp-D8h] BYREF
  void *v174[2]; // [rsp+248h] [rbp-D0h] BYREF
  PVOID v175; // [rsp+258h] [rbp-C0h]
  unsigned __int64 v176; // [rsp+260h] [rbp-B8h]
  __int64 v177; // [rsp+268h] [rbp-B0h] BYREF
  __int128 v178; // [rsp+270h] [rbp-A8h] BYREF
  int v179; // [rsp+280h] [rbp-98h]
  _BYTE v180[32]; // [rsp+290h] [rbp-88h] BYREF
  _BYTE v181[32]; // [rsp+2B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v153 = a3;
  v130 = a2;
  v140 = this;
  v143 = this;
  v152[2] = this;
  v154 = this;
  *a3 = 0;
  LOBYTE(v121) = 1;
  v148 = 0;
  v149 = 0;
  HIDWORD(v121) = 0;
  v127 = 0;
  try
  {
    v5 = (*((__int64 (**)(void))a2->Ptr + 5))();
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x272,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v5,
        Format);
    v6 = HIDWORD(v121);
    v7 = v127;
    ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v148);
    v148 = v7;
    v149 = v6;
    v146 = 0;
    v147 = 0;
    HIDWORD(v121) = 0;
    v127 = 0;
    v8 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, char *, _QWORD **))a2->Ptr + 6))(a2, (char *)&v121 + 4, &v127);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v8,
        Format);
    v9 = HIDWORD(v121);
    v10 = v127;
    ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v146);
    v146 = v10;
    v147 = v9;
    v134 = 0;
    size_of = std::_Get_size_of_n<48>(1);
    v12 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    *v12 = v12;
    v12[1] = v12;
    *(_QWORD *)&v134 = v12;
    pv = 0;
    if ( (*((unsigned int (__fastcall **)(RTL_SRWLOCK *, LPVOID *))a2->Ptr + 7))(a2, &pv) == -2147467263 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &this[5]);
      LOBYTE(this[8].Ptr) = 1;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v13 = pv;
      if ( pv )
      {
        pv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v14 = (_QWORD **)v134;
      **(_QWORD **)(v134 + 8) = 0;
      v15 = *v14;
      if ( *v14 )
      {
        do
        {
          v16 = (_QWORD *)*v15;
          std::_List_node<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,void *>::_Freenode<std::allocator<std::_List_node<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,void *>>>(
            v14,
            v15);
          v15 = v16;
        }
        while ( v16 );
      }
      std::_Deallocate<16>(v134, 48);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v146);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v148);
      result = 2147500033LL;
    }
    else
    {
      HIDWORD(v121) = 0;
      v19 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)pv + 24LL))(pv, (char *)&v121 + 4);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x28C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v19,
          Format);
      for ( i = 0; i < HIDWORD(v121); ++i )
      {
        v122 = 0;
        v21 = *(_QWORD *)pv;
        v122 = 0;
        v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(v21 + 32))(pv, i, &v122);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x290,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v22,
            Format);
        std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
          v180,
          v122);
        std::list<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>::_Emplace<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>(
          &v134,
          v134,
          v180);
        ContentIdString::~ContentIdString((ContentIdString *)v180);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v122);
      }
      v23 = pv;
      if ( pv )
      {
        pv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      }
      std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>(v152);
      for ( j = 0; j < v9; ++j )
      {
        v126 = 0;
        v25 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, wchar_t **))v10[j])(
                v10[j],
                &GUID_dc44f1df_dc28_4036_8f9f_30978f2ed4db,
                &v126);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2A9,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v25,
            Format);
        v122 = 0;
        v26 = *(_QWORD *)v126;
        v122 = 0;
        v27 = (*(__int64 (__fastcall **)(wchar_t *, __int64 *))(v26 + 64))(v126, &v122);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2AC,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v27,
            Format);
        if ( v122 )
        {
          std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
            v180,
            v122);
          v28 = std::_Tree<std::_Tmap_traits<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>,std::less<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>,std::allocator<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>,0>>::_Find<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>(
                  v152,
                  v180);
          ContentIdString::~ContentIdString((ContentIdString *)v180);
          if ( v28 != v152[0] )
            Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v28 + 72, &v126);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v122);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v126);
      }
      v158 = 0;
      v159 = 0;
      v160 = 0;
      v161 = 7;
      LOWORD(v159) = 0;
      v162 = 0;
      v163 = 0;
      std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>(v164);
      v165 = 0;
      v166 = 1;
      v167 = 0;
      std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>(&v150);
      v29 = *(PSRWLOCK *)v152[0];
      SRWLock = *(PSRWLOCK *)v152[0];
      while ( !BYTE1(v29[3].Ptr) )
      {
        HIDWORD(v121) = 0;
        v30 = v29 + 8;
        v31 = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v29[8].Ptr + 152LL))(v29[8].Ptr, (char *)&v121 + 4);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C2,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v31,
            Format);
        if ( HIDWORD(v121) != 1 )
        {
          if ( HIDWORD(v121) == 2 )
          {
            v125 = 0;
            v60 = Microsoft::WRL::ComPtr<IStoredKeyDocument>::As<IStoredPassRootDocument>(v30, &v125);
            if ( v60 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2CE,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                (const char *)(unsigned int)v60,
                Format);
            v122 = 0;
            v61 = *(_QWORD *)v125;
            v122 = 0;
            v62 = (*(__int64 (__fastcall **)(wchar_t *, __int64 *))(v61 + 160))(v125, &v122);
            v63 = v62;
            if ( v62 < 0 )
            {
              (*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)v30->Ptr + 136LL))(v30->Ptr, (unsigned int)v62);
              v126 = 0;
              pv = 0;
              Ptr = v30->Ptr;
              v67 = *(_QWORD *)v30->Ptr;
              v126 = 0;
              (*(void (__fastcall **)(PVOID, wchar_t **))(v67 + 104))(Ptr, &v126);
              v68 = v30[1].Ptr;
              if ( v68 )
              {
                v69 = *(void (__fastcall **)(_QWORD *, LPVOID *))(*v68 + 104LL);
                v70 = pv;
                if ( pv )
                {
                  wil::last_error_context::last_error_context((wil::last_error_context *)v155);
                  CoTaskMemFree(v70);
                  wil::last_error_context::~last_error_context((wil::last_error_context *)v155);
                }
                pv = 0;
                v69(v68, &pv);
              }
              v71 = L"(empty)";
              if ( pv )
                v71 = (const wchar_t *)pv;
              LODWORD(v120) = v63;
              LogMessage(
                1u,
                "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                0x2E3u,
                "LicenseProxyService::RequestRootLicenses",
                (wchar_t *)L"Pass marked for removal because of lookup error: %s %s - 0x%08x",
                v71,
                v126,
                v120,
                v121);
              if ( (unsigned int)dword_1800F11D0 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x400000000000LL) )
              {
                v75 = L"(empty)";
                if ( pv )
                  v75 = (const wchar_t *)pv;
                v142 = v75;
                v141 = v126;
                v124 = v63;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  v72,
                  (unsigned int)word_1800D784A,
                  v73,
                  v74,
                  (__int64)&v124,
                  (__int64)&v141,
                  (__int64)&v142);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v126);
            }
            else
            {
              std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
                v181,
                v122);
              v64 = (_QWORD *)std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::_Try_emplace<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,>(
                                v164,
                                v156,
                                v181);
              Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(*v64 + 64LL, v30);
              ContentIdString::~ContentIdString((ContentIdString *)v181);
              std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
                v181,
                v122);
              v65 = (_QWORD *)std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::_Try_emplace<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,>(
                                v164,
                                v180,
                                v181);
              Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(*v65 + 72LL, &v30[1]);
              ContentIdString::~ContentIdString((ContentIdString *)v181);
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v122);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v125);
          }
          else if ( HIDWORD(v121) == 3 )
          {
            v125 = 0;
            v32 = v30 + 1;
            v33 = (__int64 *)v30[1].Ptr;
            if ( v33 )
            {
              v34 = *v33;
              v125 = 0;
              v35 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v34 + 104))(v33, &v125);
              if ( v35 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2F0,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                  (const char *)(unsigned int)v35,
                  Format);
            }
            v127 = 0;
            v36 = Microsoft::WRL::ComPtr<IStoredKeyDocument>::As<IStoredUserRootDocument>(v30, &v127);
            if ( v36 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2F4,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                (const char *)(unsigned int)v36,
                Format);
            S2 = 0;
            v37 = *v127;
            S2 = 0;
            v38 = (*(__int64 (__fastcall **)(_QWORD *, wchar_t **))(v37 + 160))(v127, &S2);
            v39 = v38;
            if ( v38 < 0 )
            {
              v52 = (*(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)v30->Ptr + 136LL))(
                      v30->Ptr,
                      (unsigned int)v38);
              if ( v52 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x30D,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                  (const char *)(unsigned int)v52,
                  Format);
              v135 = 0;
              v53 = v30->Ptr;
              v54 = *(_QWORD *)v30->Ptr;
              v135 = 0;
              (*(void (__fastcall **)(PVOID, const wchar_t **))(v54 + 104))(v53, &v135);
              v55 = L"(empty)";
              if ( v125 )
                v55 = v125;
              LODWORD(v120) = v39;
              LogMessage(
                1u,
                "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                0x312u,
                "LicenseProxyService::RequestRootLicenses",
                (wchar_t *)L"User marked for removal because of lookup error: %s %s - 0x%08x",
                v55,
                v135,
                v120);
              if ( (unsigned int)dword_1800F11D0 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x400000000000LL) )
              {
                v59 = L"(empty)";
                if ( v125 )
                  v59 = v125;
                v141 = v59;
                v142 = v135;
                v124 = v39;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  v56,
                  (unsigned int)&unk_1800D77F8,
                  v57,
                  v58,
                  (__int64)&v124,
                  (__int64)&v142,
                  (__int64)&v141);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v135);
            }
            else
            {
              v40 = S2;
              v41 = (__int64 *)v134;
              for ( k = *(__int64 **)v134; k != v41; k = (__int64 *)*k )
              {
                v43 = (const wchar_t *)(k + 2);
                v44 = -1;
                do
                  ++v44;
                while ( v40[v44] );
                v45 = k[4];
                if ( (unsigned __int64)k[5] > 7 )
                  v43 = *(const wchar_t **)v43;
                if ( v45 == v44 && (!v45 || !wmemcmp(v43, v40, v45)) )
                  break;
              }
              if ( k == (__int64 *)v134 )
              {
                v48 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)v30->Ptr + 136LL))(v30->Ptr, 2151649286LL);
                if ( v48 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x302,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                    (const char *)(unsigned int)v48,
                    Format);
                if ( v32->Ptr )
                {
                  v49 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)v32->Ptr + 160LL))(
                          v32->Ptr,
                          2151649286LL);
                  if ( v49 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x305,
                      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                      (const char *)(unsigned int)v49,
                      Format);
                }
                v50 = L"(empty)";
                if ( v125 )
                  v50 = v125;
                LogMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                  0x307u,
                  "LicenseProxyService::RequestRootLicenses",
                  (wchar_t *)L"User marked for removal: %s - %s",
                  v50,
                  S2);
              }
              else
              {
                v46 = L"(empty)";
                if ( v125 )
                  v46 = v125;
                LogMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                  0x2FDu,
                  "LicenseProxyService::RequestRootLicenses",
                  (wchar_t *)L"User signin state not changed: %s - %s",
                  v46,
                  S2);
                *(_QWORD *)k[1] = *k;
                v47 = (__int64 *)*k;
                v47[1] = k[1];
                --*((_QWORD *)&v134 + 1);
                std::_List_node<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,void *>::_Freenode<std::allocator<std::_List_node<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,void *>>>(
                  v47,
                  k);
              }
              std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
                v181,
                S2);
              v51 = *(_QWORD *)std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::_Try_emplace<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,>(
                                 &v150,
                                 v157,
                                 v181);
              Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v51 + 64, v30);
              Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v51 + 72, &v30[1]);
              ContentIdString::~ContentIdString((ContentIdString *)v181);
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&S2);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v127);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v125);
          }
          else
          {
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
              0x31Au,
              "LicenseProxyService::RequestRootLicenses",
              (wchar_t *)L"Assert (%s): %s");
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>>,std::_Iterator_base0>::operator++(&SRWLock);
        v29 = SRWLock;
      }
      v76 = (_QWORD *)v134;
      for ( m = *(_QWORD **)v134; m != v76; m = (_QWORD *)*m )
      {
        v78 = (_QWORD *)std::map<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::_Try_emplace<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const &,>(
                          &v150,
                          v180,
                          m + 2);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(*v78 + 64LL);
      }
      v137 = 0;
      v79 = v130;
      v80 = (__int64 (__fastcall *)(PSRWLOCK, __int64 *))*((_QWORD *)v130->Ptr + 3);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
      v81 = v80(v79, &v137);
      if ( v81 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x328,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v81,
          Format);
      *(_OWORD *)v132 = 0;
      v133 = 0;
      v130 = v151;
      if ( v151 )
      {
        if ( (unsigned __int64)v151 > 0x222222222222222LL )
          std::vector<LicenseProxyService::UserRootThreadParam>::_Xlength();
        std::vector<LicenseProxyService::UserRootThreadParam>::_Reallocate<0>(v132, &v130);
      }
      v82 = *v150;
      SRWLock = *v150;
      v83 = v140;
      while ( !BYTE1(v82[3].Ptr) )
      {
        v84 = v82 + 4;
        v168 = 0;
        v169 = 0;
        v170 = 0;
        v171 = 7;
        LOWORD(v169) = 0;
        v172 = 0;
        v173 = 0;
        *(_OWORD *)v174 = 0;
        v175 = 0;
        v176 = 7;
        LOWORD(v174[0]) = 0;
        v177 = 0;
        v178 = 0;
        v179 = 1;
        Microsoft::WRL::ComPtr<LicenseProxyService>::operator=(&v168, v83);
        v85 = (char *)v83[6].Ptr;
        Nexus::InitializeIfNecessary(v85);
        std::wstring::operator=(&v169, v85 + 24);
        v172 = v83 + 9;
        Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v173, &v137);
        if ( v174 != (void **)v84 )
        {
          v87 = (unsigned __int64)v84[2].Ptr;
          if ( v84[3].Ptr <= (PVOID)7 )
            v88 = v84;
          else
            v88 = v84->Ptr;
          if ( v87 > v176 )
          {
            std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::_Reallocate_for<_lambda_ce2acf73edcc71272405ec96db31d1c5_,unsigned short const *>(
              v174,
              v87,
              v86,
              v88);
          }
          else
          {
            v89 = v174;
            if ( v176 > 7 )
              v89 = (void **)v174[0];
            v175 = v84[2].Ptr;
            v90 = 2 * v87;
            memmove_0(v89, v88, 2 * v87);
            *(_WORD *)((char *)v89 + v90) = 0;
          }
        }
        Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v177, &v84[4]);
        Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v178, &v84[5]);
        if ( v132[1] == v133 )
        {
          std::vector<LicenseProxyService::UserRootThreadParam>::_Emplace_reallocate<LicenseProxyService::UserRootThreadParam>(
            v132,
            v132[1],
            &v168);
        }
        else
        {
          LicenseProxyService::UserRootThreadParam::UserRootThreadParam(v132[1], &v168);
          v132[1] = (LicenseProxyService::UserRootThreadParam *)((char *)v132[1] + 120);
        }
        LicenseProxyService::UserRootThreadParam::~UserRootThreadParam((LicenseProxyService::UserRootThreadParam *)&v168);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>>,std::_Iterator_base0>::operator++(&SRWLock);
        v82 = SRWLock;
      }
      v138 = 0;
      v139 = 0;
      std::vector<Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>>::reserve(
        &v138,
        0xEEEEEEEEEEEEEEEFuLL * ((v132[1] - v132[0]) >> 3));
      for ( n = 0; n < 0xEEEEEEEEEEEEEEEFuLL * ((v132[1] - v132[0]) >> 3); ++n )
      {
        ThreadpoolWork = CreateThreadpoolWork(LicenseProxyService::RequestUserRootLicense, (char *)v132[0] + 120 * n, 0);
        v130 = (PSRWLOCK)&Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::`vftable';
        v131 = ThreadpoolWork;
        if ( !ThreadpoolWork )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x33D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            v93);
        SubmitThreadpoolWork(ThreadpoolWork);
        v94 = *((_QWORD *)&v138 + 1);
        if ( *((_QWORD *)&v138 + 1) == v139 )
        {
          std::vector<Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>>(
            &v138,
            *((_QWORD *)&v138 + 1),
            &v130);
          v95 = v131;
        }
        else
        {
          **((_QWORD **)&v138 + 1) = &Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::`vftable';
          *(_QWORD *)(v94 + 8) = v131;
          v95 = 0;
          v131 = 0;
          *((_QWORD *)&v138 + 1) += 16LL;
        }
        v130 = (PSRWLOCK)&Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::`vftable';
        if ( v95 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::InternalClose(&v130) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v114, v115);
            goto LABEL_168;
          }
          v131 = 0;
        }
      }
      v96 = v140;
      v97 = v140 + 5;
      Microsoft::WRL::Wrappers::SRWLock::LockShared(&v130, &v140[5]);
      v98 = v96 + 8;
      v99 = (char)v96[8].Ptr;
      LOBYTE(v121) = v99;
      if ( v130 )
        ReleaseSRWLockShared(v130);
      Microsoft::WRL::ComPtr<LicenseProxyService>::operator=(&v158, v96);
      v100 = (char *)v96[6].Ptr;
      Nexus::InitializeIfNecessary(v100);
      std::wstring::operator=(&v159, v100 + 24);
      v162 = v96 + 9;
      Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v163, &v137);
      v167 = v99;
      v101 = CreateThreadpoolWork(LicenseProxyService::RequestSubscriptionRootLicenses, &v158, 0);
      v144 = &Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::`vftable';
      pwk = v101;
      v103 = retaddr;
      if ( !v101 )
LABEL_168:
        wil::details::in1diag3::_Throw_GetLastError(
          v103,
          (void *)0x34E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          v102);
      SubmitThreadpoolWork(v101);
      MakeCom<LicenseProxyService::LicenseResponse,>(&v136);
      v104 = 0;
      for ( ii = 0; ii < (__int64)(*((_QWORD *)&v138 + 1) - v138) >> 4; ++ii )
      {
        WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(v138 + 16 * ii + 8), 0);
        v106 = 120 * ii;
        if ( *((int *)v132[0] + 30 * ii + 28) < 0 )
          v104 = *(_DWORD *)((char *)v132[0] + v106 + 112);
        else
          LicenseProxyService::MergeResponses(&v136, (char *)v132[0] + v106 + 104);
      }
      WaitForThreadpoolWorkCallbacks(pwk, 0);
      if ( v166 < 0 )
        v104 = v166;
      else
        LicenseProxyService::MergeResponses(&v136, &v165);
      v107 = (**v136)(v136, &GUID_19bc68d4_8e48_41d6_966e_c4fd915f8143, v153);
      if ( v107 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x36F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v107,
          Format);
      v108 = v136;
      if ( v136 )
      {
        v136 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ILicenseRootResponseData **)))(*v108)[2])(v108);
      }
      v144 = &Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::`vftable';
      if ( pwk )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>::InternalClose(&v144) )
        {
          v116 = GetLastError();
          if ( v116 > 0 )
            v116 = (unsigned __int16)v116 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v116, v117, v118);
          JUMPOUT(0x180048758LL);
        }
        pwk = 0;
      }
      if ( (_QWORD)v138 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<ThreadpoolWorkTraits>>>(
          v138,
          *((_QWORD *)&v138 + 1));
        std::_Deallocate<16>(v138, (v139 - v138) & 0xFFFFFFFFFFFFFFF0uLL);
        v138 = 0;
        v139 = 0;
      }
      if ( v132[0] )
      {
        std::_Destroy_range<std::allocator<LicenseProxyService::UserRootThreadParam>>(v132[0]);
        std::_Deallocate<16>(v132[0], 8 * ((v133 - v132[0]) >> 3));
        *(_OWORD *)v132 = 0;
        v133 = 0;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
      std::_Tree<std::_Tmap_traits<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>,std::less<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>,std::allocator<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>,std::less<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>,std::allocator<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>,0>>(&v150);
      LicenseProxyService::SubscriptionsRootThreadParam::~SubscriptionsRootThreadParam((LicenseProxyService::SubscriptionsRootThreadParam *)&v158);
      std::_Tree<std::_Tmap_traits<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>,std::less<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>,std::allocator<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>,std::less<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>,std::allocator<std::pair<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>,0>>(v152);
      v109 = (_QWORD **)v134;
      **(_QWORD **)(v134 + 8) = 0;
      v110 = *v109;
      if ( *v109 )
      {
        do
        {
          v111 = (_QWORD *)*v110;
          std::_List_node<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,void *>::_Freenode<std::allocator<std::_List_node<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>,void *>>>(
            v109,
            v110);
          v110 = v111;
        }
        while ( v111 );
      }
      std::_Deallocate<16>(v134, 48);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v146);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v148);
      v112 = v140;
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v143, v97);
      if ( v104 == -2147467263 || (HIDWORD(v112[8].Ptr) = v104, v104 >= 0) && !v99 )
        LOBYTE(v98->Ptr) = 1;
      if ( v143 )
        ReleaseSRWLockExclusive(v143);
      result = (unsigned int)v104;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x38A,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800471d0  push    rbx
0x1800471d2  push    rsi
0x1800471d3  push    rdi
0x1800471d4  push    r12
0x1800471d6  push    r13
0x1800471d8  push    r14
0x1800471da  push    r15
0x1800471dc  sub     rsp, 2E0h
0x1800471e3  mov     rax, cs:__security_cookie
0x1800471ea  xor     rax, rsp
0x1800471ed  mov     [rsp+318h+var_48], rax
0x1800471f5  mov     [rsp+318h+var_1B0], r8
0x1800471fd  mov     rbx, rdx
0x180047200  mov     [rsp+318h+var_290], rdx
0x180047208  mov     r13, rcx
0x18004720b  mov     [rsp+318h+var_228], rcx
0x180047213  mov     [rsp+318h+var_210], rcx
0x18004721b  mov     [rsp+318h+var_1B8], rcx
0x180047223  mov     [rsp+318h+var_1A8], rcx
0x18004722b  xor     esi, esi
0x18004722d  mov     [r8], rsi
0x180047230  mov     [rsp+318h+var_2D8], 1
0x180047235  mov     [rsp+318h+var_1E8], rsi
0x18004723d  mov     [rsp+318h+var_1E0], esi
0x180047244  mov     [rsp+318h+var_2D4], esi
0x180047248  mov     [rsp+318h+var_2A8], rsi
0x18004724d  mov     rax, [rdx]
0x180047250  lea     r8, [rsp+318h+var_2A8]
0x180047255  lea     rdx, [rsp+318h+var_2D4]
0x18004725a  mov     rcx, rbx
0x18004725d  mov     rax, [rax+28h]
0x180047261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047266  mov     rcx, [rsp+318h]; this
0x18004726e  test    eax, eax
0x180047270  js      loc_1800485C4
0x180047276  mov     edi, [rsp+318h+var_2D4]
0x18004727a  mov     r14, [rsp+318h+var_2A8]
0x18004727f  lea     rcx, [rsp+318h+var_1E8]
0x180047287  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x18004728c  mov     [rsp+318h+var_1E8], r14
0x180047294  mov     [rsp+318h+var_1E0], edi
0x18004729b  mov     [rsp+318h+var_1F8], rsi
0x1800472a3  mov     [rsp+318h+var_1F0], esi
0x1800472aa  mov     [rsp+318h+var_2D4], esi
0x1800472ae  mov     [rsp+318h+var_2A8], rsi
0x1800472b3  mov     rax, [rbx]
0x1800472b6  lea     r8, [rsp+318h+var_2A8]
0x1800472bb  lea     rdx, [rsp+318h+var_2D4]
0x1800472c0  mov     rcx, rbx
0x1800472c3  mov     rax, [rax+30h]
0x1800472c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472cc  mov     rcx, [rsp+318h]; this
0x1800472d4  test    eax, eax
0x1800472d6  js      loc_1800485D9
0x1800472dc  mov     r15d, [rsp+318h+var_2D4]
0x1800472e1  mov     r12, [rsp+318h+var_2A8]
0x1800472e6  lea     rcx, [rsp+318h+var_1F8]
0x1800472ee  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x1800472f3  mov     [rsp+318h+var_1F8], r12
0x1800472fb  mov     [rsp+318h+var_1F0], r15d
0x180047303  xorps   xmm0, xmm0
0x180047306  movdqu  [rsp+318h+var_268], xmm0
0x18004730f  mov     ecx, 1
0x180047314  call    ??$_Get_size_of_n@$0DA@@std@@YA_K_K@Z; std::_Get_size_of_n<48>(unsigned __int64)
0x180047319  mov     rcx, rax
0x18004731c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180047321  mov     [rax], rax
0x180047324  mov     [rax+8], rax
0x180047328  mov     qword ptr [rsp+318h+var_268], rax
0x180047330  mov     [rsp+318h+pv], rsi
0x180047335  mov     rax, [rbx]
0x180047338  lea     rdx, [rsp+318h+pv]
0x18004733d  mov     rcx, rbx
0x180047340  mov     rax, [rax+38h]
0x180047344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047349  cmp     eax, 80004001h
0x18004734e  jnz     loc_1800473FA
0x180047354  lea     rdx, [r13+28h]
0x180047358  lea     rcx, [rsp+318h+SRWLock]
0x180047360  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180047365  mov     byte ptr [r13+40h], 1
0x18004736a  mov     rcx, [rsp+318h+SRWLock]; SRWLock
0x180047372  test    rcx, rcx
0x180047375  jz      short loc_18004737E
0x180047377  call    cs:__imp_ReleaseSRWLockExclusive
0x18004737d  nop
0x18004737e  mov     rcx, [rsp+318h+pv]
0x180047383  test    rcx, rcx
0x180047386  jz      short loc_18004739A
0x180047388  mov     [rsp+318h+pv], rsi
0x18004738d  mov     rax, [rcx]
0x180047390  mov     rax, [rax+10h]
0x180047394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047399  nop
0x18004739a  mov     rcx, qword ptr [rsp+318h+var_268]
0x1800473a2  mov     rax, [rcx+8]
0x1800473a6  mov     [rax], rsi
0x1800473a9  mov     rdx, [rcx]
0x1800473ac  test    rdx, rdx
0x1800473af  jz      short loc_1800473C1
0x1800473b1  mov     rbx, [rdx]
0x1800473b4  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,void *>::_Freenode<std::allocator<std::_List_node<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,void *>>>(std::allocator<std::_List_node<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,void *>> &,std::_List_node<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,void *> *)
0x1800473b9  mov     rdx, rbx
0x1800473bc  test    rbx, rbx
0x1800473bf  jnz     short loc_1800473B1
0x1800473c1  mov     edx, 30h ; '0'
0x1800473c6  mov     rcx, qword ptr [rsp+318h+var_268]
0x1800473ce  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800473d3  nop
0x1800473d4  lea     rcx, [rsp+318h+var_1F8]
0x1800473dc  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x1800473e1  nop
0x1800473e2  lea     rcx, [rsp+318h+var_1E8]
0x1800473ea  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x1800473ef  nop
0x1800473f0  mov     eax, 80004001h
0x1800473f5  jmp     loc_1800485A1
0x1800473fa  mov     [rsp+318h+var_2D4], esi
0x1800473fe  mov     rcx, [rsp+318h+pv]
0x180047403  mov     rax, [rcx]
0x180047406  lea     rdx, [rsp+318h+var_2D4]
0x18004740b  mov     rax, [rax+18h]
0x18004740f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047414  mov     rcx, [rsp+318h]; this
0x18004741c  test    eax, eax
0x18004741e  js      loc_1800485EE
0x180047424  mov     ebx, esi
0x180047426  cmp     ebx, [rsp+318h+var_2D4]
0x18004742a  jnb     loc_1800474B2
0x180047430  mov     [rsp+318h+var_2D0], rsi
0x180047435  mov     rcx, [rsp+318h+pv]
0x18004743a  mov     rax, [rcx]
0x18004743d  mov     [rsp+318h+var_2D0], rsi
0x180047442  lea     r8, [rsp+318h+var_2D0]
0x180047447  mov     edx, ebx
0x180047449  mov     rax, [rax+20h]
0x18004744d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047452  mov     rcx, [rsp+318h]; this
0x18004745a  test    eax, eax
0x18004745c  js      loc_180048603
0x180047462  mov     rdx, [rsp+318h+var_2D0]
0x180047467  lea     rcx, [rsp+318h+var_88]
0x18004746f  call    ??0?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>(ushort const * const)
0x180047474  nop
0x180047475  lea     r8, [rsp+318h+var_88]
0x18004747d  mov     rdx, qword ptr [rsp+318h+var_268]
0x180047485  lea     rcx, [rsp+318h+var_268]
0x18004748d  call    ??$_Emplace@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@?$list@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@1@@Z; std::list<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>>::_Emplace<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>>(std::_List_node<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,void *> * const,std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> &&)
0x180047492  nop
0x180047493  lea     rcx, [rsp+318h+var_88]; this
0x18004749b  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800474a0  nop
0x1800474a1  lea     rcx, [rsp+318h+var_2D0]
0x1800474a6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800474ab  inc     ebx
0x1800474ad  jmp     loc_180047426
0x1800474b2  mov     rcx, [rsp+318h+pv]
0x1800474b7  test    rcx, rcx
0x1800474ba  jz      short loc_1800474CE
0x1800474bc  mov     [rsp+318h+pv], rsi
0x1800474c1  mov     rax, [rcx]
0x1800474c4  mov     rax, [rax+10h]
0x1800474c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474cd  nop
0x1800474ce  lea     rcx, [rsp+318h+var_1C8]
0x1800474d6  call    ??0?$map@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@U?$less@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>(void)
0x1800474db  nop
0x1800474dc  mov     ebx, esi
0x1800474de  cmp     ebx, edi
0x1800474e0  jnb     loc_1800475B9
0x1800474e6  mov     [rsp+318h+var_2B0], rsi
0x1800474eb  mov     eax, ebx
0x1800474ed  mov     rcx, [r14+rax*8]
0x1800474f1  mov     rax, [rcx]
0x1800474f4  lea     r8, [rsp+318h+var_2B0]
0x1800474f9  lea     rdx, _GUID_450650a1_f019_4d2e_a24a_7346b7cf9b21
0x180047500  mov     rax, [rax]
0x180047503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047508  mov     rcx, [rsp+318h]; this
0x180047510  test    eax, eax
0x180047512  js      loc_180048618
0x180047518  mov     [rsp+318h+var_2D0], rsi
0x18004751d  mov     rcx, [rsp+318h+var_2B0]
0x180047522  mov     rax, [rcx]
0x180047525  mov     [rsp+318h+var_2D0], rsi
0x18004752a  lea     rdx, [rsp+318h+var_2D0]
0x18004752f  mov     rax, [rax+40h]
0x180047533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047538  mov     rcx, [rsp+318h]; this
0x180047540  test    eax, eax
0x180047542  js      loc_18004862D
0x180047548  mov     rdx, [rsp+318h+var_2D0]
0x18004754d  test    rdx, rdx
0x180047550  jz      short loc_18004759D
0x180047552  lea     rcx, [rsp+318h+var_88]
0x18004755a  call    ??0?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>(ushort const * const)
0x18004755f  nop
0x180047560  lea     r8, [rsp+318h+var_88]
0x180047568  lea     rdx, [rsp+318h+var_1A0]
0x180047570  lea     rcx, [rsp+318h+var_1C8]
0x180047578  call    ??$_Try_emplace@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@$$V@?$map@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@U?$less@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@1@@Z; std::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::_Try_emplace<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,>(std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> &&)
0x18004757d  mov     rcx, [rax]
0x180047580  add     rcx, 40h ; '@'
0x180047584  lea     rdx, [rsp+318h+var_2B0]
0x180047589  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x18004758e  nop
0x18004758f  lea     rcx, [rsp+318h+var_88]; this
0x180047597  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18004759c  nop
0x18004759d  lea     rcx, [rsp+318h+var_2D0]
0x1800475a2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800475a7  nop
0x1800475a8  lea     rcx, [rsp+318h+var_2B0]
0x1800475ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800475b2  inc     ebx
0x1800475b4  jmp     loc_1800474DE
0x1800475b9  mov     edi, esi
0x1800475bb  cmp     edi, r15d
0x1800475be  jnb     loc_180047697
0x1800475c4  mov     [rsp+318h+var_2B0], rsi
0x1800475c9  mov     eax, edi
0x1800475cb  mov     rcx, [r12+rax*8]
0x1800475cf  mov     rax, [rcx]
0x1800475d2  lea     r8, [rsp+318h+var_2B0]
0x1800475d7  lea     rdx, _GUID_dc44f1df_dc28_4036_8f9f_30978f2ed4db
0x1800475de  mov     rax, [rax]
0x1800475e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475e6  mov     rcx, [rsp+318h]; this
0x1800475ee  test    eax, eax
0x1800475f0  js      loc_180048642
0x1800475f6  mov     [rsp+318h+var_2D0], rsi
0x1800475fb  mov     rcx, [rsp+318h+var_2B0]
0x180047600  mov     rax, [rcx]
0x180047603  mov     [rsp+318h+var_2D0], rsi
0x180047608  lea     rdx, [rsp+318h+var_2D0]
0x18004760d  mov     rax, [rax+40h]
0x180047611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047616  mov     rcx, [rsp+318h]; this
0x18004761e  test    eax, eax
0x180047620  js      loc_180048657
0x180047626  mov     rdx, [rsp+318h+var_2D0]
0x18004762b  test    rdx, rdx
0x18004762e  jz      short loc_18004767B
0x180047630  lea     rcx, [rsp+318h+var_88]
0x180047638  call    ??0?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>(ushort const * const)
0x18004763d  lea     rdx, [rsp+318h+var_88]
0x180047645  lea     rcx, [rsp+318h+var_1C8]
0x18004764d  call    ??$_Find@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@U?$less@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@PEAX@1@AEBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>,std::less<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> const,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>>,0>>::_Find<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>>(std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> const &)
0x180047652  mov     rbx, rax
0x180047655  lea     rcx, [rsp+318h+var_88]; this
0x18004765d  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180047662  cmp     rbx, [rsp+318h+var_1C8]
0x18004766a  jz      short loc_18004767B
0x18004766c  lea     rcx, [rbx+48h]
0x180047670  lea     rdx, [rsp+318h+var_2B0]
0x180047675  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x18004767a  nop
0x18004767b  lea     rcx, [rsp+318h+var_2D0]
0x180047680  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180047685  nop
0x180047686  lea     rcx, [rsp+318h+var_2B0]
0x18004768b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180047690  inc     edi
0x180047692  jmp     loc_1800475BB
0x180047697  mov     [rsp+318h+var_168], rsi
0x18004769f  xorps   xmm0, xmm0
0x1800476a2  movups  [rsp+318h+var_160], xmm0
0x1800476aa  mov     [rsp+318h+var_150], rsi
0x1800476b2  mov     r12d, 7
0x1800476b8  mov     [rsp+318h+var_148], r12
0x1800476c0  mov     word ptr [rsp+318h+var_160], si
0x1800476c8  mov     [rsp+318h+var_140], rsi
0x1800476d0  mov     [rsp+318h+var_138], rsi
0x1800476d8  lea     rcx, [rsp+318h+var_130]
0x1800476e0  call    ??0?$map@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@U?$less@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>(void)
0x1800476e5  mov     [rsp+318h+var_120], rsi
0x1800476ed  mov     [rsp+318h+var_118], 1
0x1800476f8  mov     [rsp+318h+var_114], sil
0x180047700  lea     rcx, [rsp+318h+var_1D8]
0x180047708  call    ??0?$map@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@U?$less@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@U?$pair@V?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@V?$ComPtr@UIStoredLeaseDocument@@@23@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>::map<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>,std::pair<Microsoft::WRL::ComPtr<IStoredKeyDocument>,Microsoft::WRL::ComPtr<IStoredLeaseDocument>>>(void)
0x18004770d  nop
0x18004770e  mov     rax, [rsp+318h+var_1C8]
0x180047716  mov     rax, [rax]
0x180047719  mov     [rsp+318h+SRWLock], rax
0x180047721  lea     r14, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180047728  cmp     [rax+19h], sil
0x18004772c  jnz     loc_180047DED
0x180047732  mov     [rsp+318h+var_2D4], esi
0x180047736  lea     r13, [rax+40h]
0x18004773a  mov     rcx, [r13+0]
0x18004773e  mov     rax, [rcx]
0x180047741  lea     rdx, [rsp+318h+var_2D4]
0x180047746  mov     rax, [rax+98h]
0x18004774d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047752  mov     rcx, [rsp+318h]; this
0x18004775a  test    eax, eax
0x18004775c  js      loc_18004866C
0x180047762  mov     ecx, [rsp+318h+var_2D4]
0x180047766  sub     ecx, 1
0x180047769  jz      loc_180047DD3
  ... truncated ...
```
