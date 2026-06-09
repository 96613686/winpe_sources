# EvaluateFeatureRequest

- ea: `0x18001fb24`
- end: `0x180020645`
- name: `EvaluateFeatureRequest`
- size: `2849`
- prototype: `void __fastcall(HMODULE, __int64, char, __int64, __int64, __int64 *, __int64 *, wchar_t *, __int64 *, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002095c`

## callees

- `0x1800031d0`
- `0x180009750`
- `0x18000aedc`
- `0x18000c468`
- `0x18000f614`
- `0x18000f874`
- `0x180012218`
- `0x1800126b8`
- `0x1800126d4`
- `0x180016558`
- `0x18001b0a4`
- `0x18001c1d0`
- `0x18001cb10`
- `0x18001d3dc`
- `0x18001d650`
- `0x18001dc34`
- `0x18001e434`
- `0x18001fb24`
- `0x180023390`
- `0x18002bc54`
- `0x18002c0d0`
- `0x18002dfe0`
- `0x18002e3a4`
- `0x18002e510`
- `0x18002fee4`
- `0x18004e028`
- `0x18004e0d4`
- `0x180070f18`
- `0x1801b31e0`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001fbbb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180020402`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002042b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001fbbb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180020402`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002042b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002050b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002050b`

## string_xrefs

- `0x18001fbb4`: `GetRootPath`
- `0x18001fda0`: `\Windows\ImageUpdate\CompDBs`
- `0x1800203a4`: `Failed to acquire privileges`
- `0x18001fc0d`: `Failed to determine DATA partition root path`
- `0x18001ffdf`: `ActionList.xml`
- `0x18001fc5d`: `\SystemData\Temp`
- `0x180020421`: `StageUpdateWithActionList`
- `0x1800203f4`: `CommitUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EvaluateFeatureRequest(
        HMODULE a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 *a7,
        wchar_t *a8,
        __int64 *a9,
        __int64 *a10,
        _DWORD *a11)
{
  __int64 *v11; // r13
  FARPROC ProcAddress; // rax
  const char *v13; // r9
  void (__fastcall *v14)(_QWORD, _QWORD, _QWORD); // rdi
  int v15; // eax
  int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // rax
  const wchar_t *v20; // rax
  __int64 v21; // rcx
  int TemporaryFileName; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 *v27; // rbx
  __int64 i; // rdi
  __int64 v29; // rax
  const int near *const *v30; // rcx
  int v31; // r8d
  __int64 v32; // rdx
  __int64 *v33; // rbx
  __int64 v34; // rdi
  __int64 v35; // rax
  const int near *const *v36; // rcx
  int v37; // r8d
  __int64 v38; // rdx
  wchar_t *v39; // rbx
  const char *v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  int v45; // edx
  int v46; // eax
  char v47; // di
  wchar_t *v48; // r12
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r9
  _QWORD *v52; // rdx
  _QWORD *v53; // r8
  __int64 v54; // r10
  __int64 v55; // r9
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // r8
  void (__fastcall ***v62)(_QWORD, __int64, __int64, __int64); // rcx
  void (__fastcall ***v63)(_QWORD, __int64, __int64, __int64); // rdi
  __int64 v64; // rcx
  __int64 v65; // r8
  int wnf_subscription; // eax
  wil::details::in1diag3 *v67; // rcx
  _DWORD *v68; // rax
  int v69; // eax
  int v70; // esi
  __int64 v71; // rdx
  HMODULE v72; // r15
  FARPROC v73; // rsi
  const char *v74; // r9
  const char *v75; // r9
  FARPROC v76; // r10
  int v77; // eax
  int v78; // eax
  int *v79; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+60h] [rbp-A0h]
  const wchar_t *v82; // [rsp+68h] [rbp-98h] BYREF
  __int64 v83; // [rsp+70h] [rbp-90h]
  int v84[2]; // [rsp+78h] [rbp-88h] BYREF
  int v85[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v86; // [rsp+88h] [rbp-78h]
  _DWORD *v87; // [rsp+90h] [rbp-70h]
  const int near *const *v88; // [rsp+98h] [rbp-68h] BYREF
  __int64 v89; // [rsp+A0h] [rbp-60h]
  int v90; // [rsp+A8h] [rbp-58h]
  int v91; // [rsp+ACh] [rbp-54h]
  HMODULE hModule; // [rsp+B8h] [rbp-48h]
  __int64 v93; // [rsp+C0h] [rbp-40h]
  _BYTE v94[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v95[8]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v96[13]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v97; // [rsp+158h] [rbp+58h]
  __int64 v98; // [rsp+160h] [rbp+60h] BYREF
  void **v99; // [rsp+170h] [rbp+70h] BYREF
  int v100; // [rsp+178h] [rbp+78h]
  __int64 v101; // [rsp+180h] [rbp+80h]
  __int64 v102; // [rsp+188h] [rbp+88h]
  int v103; // [rsp+190h] [rbp+90h]
  __int64 v104; // [rsp+198h] [rbp+98h]
  __int64 v105; // [rsp+1A0h] [rbp+A0h]
  int v106; // [rsp+1A8h] [rbp+A8h]
  __int128 v107; // [rsp+1B0h] [rbp+B0h]
  int v108; // [rsp+1C0h] [rbp+C0h]
  __int64 v109; // [rsp+1C8h] [rbp+C8h]
  _BYTE v110[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v111; // [rsp+1D4h] [rbp+D4h] BYREF
  __int128 v112; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v113; // [rsp+1E8h] [rbp+E8h]
  wchar_t *v114; // [rsp+1F0h] [rbp+F0h] BYREF
  char v115; // [rsp+1F8h] [rbp+F8h]
  _OWORD v116[2]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v117; // [rsp+220h] [rbp+120h] BYREF
  __m128i si128; // [rsp+230h] [rbp+130h]
  unsigned __int16 v119[16]; // [rsp+240h] [rbp+140h] BYREF
  _WORD v120[2048]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+12A8h] [rbp+11A8h]

  v93 = -2;
  *(_QWORD *)v84 = a4;
  hModule = a1;
  v11 = a10;
  v114 = a8;
  v98 = a2;
  v87 = a11;
  ProcAddress = GetProcAddress(a1, "GetRootPath");
  v14 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x382,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      v13);
  v15 = ((__int64 (__fastcall *)(const wchar_t *, _WORD *, __int64))ProcAddress)(L"DATA", v120, 2048);
  v16 = v15;
  if ( v15 < 0 )
  {
    v111 = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to determine DATA partition root path");
      *(_QWORD *)v85 = &v111;
      v79 = v85;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v17,
        3,
        ": {}");
    }
  }
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x388,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)(unsigned int)v16,
      (int)v79);
  *(_QWORD *)v85 = L"\\SystemData\\Temp";
  v86 = 16;
  v82 = v120;
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( v120[v19] );
  v83 = v19;
  v20 = (const wchar_t *)CreatePath(&v88, &v82, v85);
  v21 = *((_QWORD *)v20 + 2);
  if ( *((_QWORD *)v20 + 3) > 7u )
    v20 = *(const wchar_t **)v20;
  v82 = v20;
  v83 = v21;
  TemporaryFileName = GetTemporaryFileName(&v82, a7);
  if ( TemporaryFileName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38C,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      (const char *)(unsigned int)TemporaryFileName,
      (int)v79);
  std::wstring::~wstring(&v88);
  v117 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v117) = 0;
  v116[0] = 0;
  v116[1] = si128;
  LOWORD(v116[0]) = 0;
  v14(L"MAINOS", v120, 2048);
  v82 = L"\\Windows";
  v83 = 8;
  *(_QWORD *)v85 = v120;
  v23 = -1;
  do
    ++v23;
  while ( v120[v23] );
  v86 = v23;
  v24 = CreatePath(&v88, v85, &v82);
  std::wstring::operator=(&v117, v24);
  std::wstring::~wstring(&v88);
  v82 = L"\\Windows\\ImageUpdate\\CompDBs";
  v83 = 28;
  *(_QWORD *)v85 = v120;
  do
    ++v18;
  while ( v120[v18] );
  v86 = v18;
  v25 = CreatePath(&v88, v85, &v82);
  std::wstring::operator=(v116, v25);
  std::wstring::~wstring(&v88);
  v112 = 0;
  v113 = 0;
  v26 = *(_QWORD *)v84;
  std::vector<FeatureDescriptor>::reserve(&v112, *(_QWORD *)(a5 + 8) + *(_QWORD *)(*(_QWORD *)v84 + 8LL));
  v27 = *(__int64 **)v26;
  for ( i = *(_QWORD *)v26 + 8LL * *(_QWORD *)(v26 + 8); v27 != (__int64 *)i; ++v27 )
  {
    v29 = *v27;
    v89 = 0;
    v91 = 0;
    v30 = *(const int near *const **)v29;
    v88 = *(const int near *const **)v29;
    v31 = *(_DWORD *)(v29 + 20);
    v90 = v31;
    v32 = *((_QWORD *)&v112 + 1);
    if ( *((_QWORD *)&v112 + 1) == v113 )
    {
      std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(
        &v112,
        *((_QWORD *)&v112 + 1),
        &v88);
    }
    else
    {
      **((_QWORD **)&v112 + 1) = v30;
      *(_QWORD *)(v32 + 8) = 0;
      *(_DWORD *)(v32 + 16) = v31;
      *(_DWORD *)(v32 + 20) = 0;
      *((_QWORD *)&v112 + 1) += 24LL;
    }
  }
  v33 = *(__int64 **)a5;
  v34 = *(_QWORD *)a5 + 8LL * *(_QWORD *)(a5 + 8);
  while ( v33 != (__int64 *)v34 )
  {
    v35 = *v33;
    v89 = 0;
    v90 = 0;
    v36 = *(const int near *const **)v35;
    v88 = *(const int near *const **)v35;
    v37 = *(_DWORD *)(v35 + 20);
    v91 = v37;
    v38 = *((_QWORD *)&v112 + 1);
    if ( *((_QWORD *)&v112 + 1) == v113 )
    {
      std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(
        &v112,
        *((_QWORD *)&v112 + 1),
        &v88);
    }
    else
    {
      **((_QWORD **)&v112 + 1) = v36;
      *(_QWORD *)(v38 + 8) = 0;
      *(_DWORD *)(v38 + 16) = 0;
      *(_DWORD *)(v38 + 20) = v37;
      *((_QWORD *)&v112 + 1) += 24LL;
    }
    ++v33;
  }
  *(_QWORD *)v85 = 0;
  v99 = &SessionData::`vftable';
  v101 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v100 = 18;
  v102 = v112;
  v103 = -1431655765 * ((__int64)(*((_QWORD *)&v112 + 1) - v112) >> 3);
  v39 = SessionDataToJson((const struct SessionData *)&v99);
  *(_QWORD *)v85 = v39;
  if ( !v39 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
      v40);
  to_wstring(v119, v98 + 8);
  v41 = a7[2];
  v42 = (__int64)a7;
  if ( (unsigned __int64)a7[3] > 7 )
    v42 = *a7;
  v82 = (const wchar_t *)v42;
  v83 = v41;
  DestroyDirectory(&v82);
  v82 = L"ActionList.xml";
  v83 = 14;
  if ( (unsigned __int64)a7[3] <= 7 )
    v43 = (__int64)a7;
  else
    v43 = *a7;
  v88 = (const int near *const *)v43;
  v89 = a7[2];
  v44 = CreatePath(v94, &v88, &v82);
  std::wstring::operator=(a10, v44);
  std::wstring::~wstring(v94);
  v46 = a3 & 4;
  v81 = v46;
  if ( *(_QWORD *)(v98 + 176) || v46 || (*(_BYTE *)(v98 + 160) & 3) != 0 )
  {
    if ( *a9 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      goto LABEL_102;
    }
    v47 = 1;
    v48 = v114;
    CallFacilitator(
      v98,
      2,
      (__int64)&v99,
      (__int64)v39,
      v119,
      (wchar_t *)a7,
      (__int64)&v117,
      (const wchar_t *)v116,
      a10,
      v114,
      (__int64)a9,
      v87);
  }
  else
  {
    LOBYTE(v45) = *(_QWORD *)(*(_QWORD *)v84 + 8LL) == 0;
    v110[0] = 0;
    if ( *a9 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      __debugbreak();
    }
    v47 = 0;
    CallUSO(v98, v45, (_DWORD)v39, (_DWORD)a7, (__int64)a10, (__int64)a9, (__int64)v110, (__int64)v87);
    v48 = v114;
    if ( v110[0] && a6 != (__int64 *)-56LL )
      *((_DWORD *)a6 + 14) = 2;
  }
  v49 = *a9;
  v50 = *(_QWORD *)(*a9 + 64);
  v51 = v50 + 168LL * *(unsigned int *)(*a9 + 72);
  if ( v50 != v51 )
  {
    do
    {
      v52 = *(_QWORD **)(v50 + 112);
      v53 = &v52[23 * *(unsigned int *)(v50 + 120)];
      if ( v52 != v53 )
      {
        v54 = *a6;
        do
        {
          v54 += *v52;
          *a6 = v54;
          v52 += 23;
        }
        while ( v52 != v53 );
      }
      v50 += 168;
    }
    while ( v50 != v51 );
    v49 = *a9;
  }
  v55 = *a6;
  v56 = *(_QWORD *)(v49 + 88);
  v57 = v56 + 168LL * *(unsigned int *)(v49 + 96);
  if ( v56 != v57 )
  {
    v58 = a6[2];
    do
    {
      v58 += *(_QWORD *)(v56 + 8);
      a6[2] = v58;
      if ( !v55 )
        *a6 += *(_QWORD *)(v56 + 8);
      v56 += 168;
    }
    while ( v56 != v57 );
  }
  v59 = a6[2];
  a6[1] += v59 + *a6;
  v60 = *(_QWORD *)(*a9 + 104);
  v61 = v60 + 56LL * *(unsigned int *)(*a9 + 112);
  while ( v60 != v61 )
  {
    v59 -= *(_QWORD *)(v60 + 32);
    a6[2] = v59;
    v60 += 56;
  }
  if ( v47 )
  {
    if ( !v81 )
    {
      v62 = (void (__fastcall ***)(_QWORD, __int64, __int64, __int64))*a9;
      if ( *(_DWORD *)(*a9 + 72) )
      {
        if ( v62 )
        {
          (**v62)(v62, v60, v61, v55);
          *a9 = 0;
        }
        CallFacilitator(
          v98,
          0,
          (__int64)&v99,
          (__int64)v39,
          v119,
          (wchar_t *)a7,
          (__int64)&v117,
          (const wchar_t *)v116,
          a10,
          v48,
          (__int64)a9,
          v87);
      }
    }
    v63 = 0;
    v87 = 0;
    if ( (*(_BYTE *)(v98 + 160) & 1) != 0 || !InMobile() || InUpdateOS() )
      goto LABEL_67;
    PublishOperationProgress(v98, 1, 0, 0);
    v96[0] = off_1801BE0B0;
    v96[1] = &v98;
    v97 = v96;
    *(_QWORD *)v84 = 0;
    wnf_subscription = wil::details::make_wnf_subscription_state<IUProgressData>(v64, v95, v65, v84);
    v67 = retaddr;
    if ( wnf_subscription >= 0 )
    {
      v63 = *(void (__fastcall ****)(_QWORD, __int64, __int64, __int64))v84;
      v87 = *(_DWORD **)v84;
      if ( v97 )
        (*(void (__fastcall **)(_QWORD *))(*v97 + 24LL))(v97);
LABEL_67:
      v68 = (_DWORD *)*a9;
      if ( *(_DWORD *)(*a9 + 128) || v68[36] || v68[24] || v68[28] )
      {
        if ( v81 )
        {
          if ( (*(_BYTE *)(v98 + 160) & 1) == 0 && a6 != (__int64 *)-56LL )
            *((_DWORD *)a6 + 14) = 2;
        }
        else
        {
          v114 = 0;
          v115 = 0;
          v88 = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
          v89 = 3;
          v69 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v114, &v88);
          v70 = v69;
          if ( v69 < 0 )
          {
            v111 = v69;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed to acquire privileges");
              *(_QWORD *)v84 = &v111;
              v79 = v84;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v71,
                3,
                ": {}");
            }
          }
          if ( v70 < 0 )
            wil::details::in1diag3::_Throw_NtStatus(
              retaddr,
              (void *)0x443,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
              (const char *)(unsigned int)v70,
              (int)v79);
          v72 = hModule;
          v73 = GetProcAddress(hModule, "CommitUpdate");
          if ( !v73 )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x449,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
              v74);
          v76 = GetProcAddress(v72, "StageUpdateWithActionList");
          if ( !v76 )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x44E,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
              v75);
          if ( *((_QWORD *)v48 + 3) > 7u )
            v48 = *(wchar_t **)v48;
          if ( (unsigned __int64)a10[3] > 7 )
            v11 = (__int64 *)*a10;
          v77 = ((__int64 (__fastcall *)(_QWORD, __int64 *, wchar_t *, _QWORD))v76)(
                  (*(_DWORD *)(v98 + 160) & 4) != 0 ? 64 : 16,
                  v11,
                  v48,
                  0);
          if ( v77 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x45D,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
              (const char *)(unsigned int)v77,
              0);
          v78 = ((__int64 (__fastcall *)(__int64))v73)(1);
          if ( v78 == -2147021886 )
          {
            if ( a6 != (__int64 *)-56LL )
              *((_DWORD *)a6 + 14) = 2;
            v78 = 0;
          }
          if ( v78 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x468,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\modify_onecore.cpp",
              (const char *)(unsigned int)v78,
              0);
          RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v114);
        }
      }
      if ( v63 )
        (**v63)(v63, 1, v61, v55);
      goto LABEL_94;
    }
LABEL_102:
    wil::details::in1diag3::Throw_Hr(
      v67,
      (void *)0x43C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)wnf_subscription,
      (int)v79);
  }
LABEL_94:
  std::wstring::~wstring(v119);
  CoTaskMemFree(v39);
  std::vector<FeatureDescriptor>::~vector<FeatureDescriptor>(&v112);
  std::wstring::~wstring(v116);
  std::wstring::~wstring(&v117);
}

```

## disassembly

```asm
0x18001fb24  push    rbp
0x18001fb26  push    rsi
0x18001fb27  push    rdi
0x18001fb28  push    r12
0x18001fb2a  push    r13
0x18001fb2c  push    r14
0x18001fb2e  push    r15
0x18001fb30  lea     rbp, [rsp-1170h]
0x18001fb38  mov     eax, 1270h
0x18001fb3d  call    _alloca_probe
0x18001fb42  sub     rsp, rax
0x18001fb45  mov     [rbp+11A0h+var_11E0], 0FFFFFFFFFFFFFFFEh
0x18001fb4d  mov     [rsp+12A0h+arg_10], rbx
0x18001fb55  mov     rax, cs:__security_cookie
0x18001fb5c  xor     rax, rsp
0x18001fb5f  mov     [rbp+11A0h+var_40], rax
0x18001fb66  mov     qword ptr [rsp+12A0h+var_1228], r9
0x18001fb6b  mov     [rsp+12A0h+var_1240], r8d
0x18001fb70  mov     [rbp+11A0h+hModule], rcx
0x18001fb74  mov     r13, [rbp+11A0h+arg_48]
0x18001fb7b  mov     rax, [rbp+11A0h+arg_38]
0x18001fb82  mov     [rbp+11A0h+var_10B0], rax
0x18001fb89  mov     r14, [rbp+11A0h+arg_28]
0x18001fb90  mov     r15, [rbp+11A0h+arg_40]
0x18001fb97  mov     rsi, [rbp+11A0h+arg_30]
0x18001fb9e  mov     [rbp+11A0h+var_1140], rdx
0x18001fba2  mov     r12, [rbp+11A0h+arg_20]
0x18001fba9  mov     rax, [rbp+11A0h+arg_50]
0x18001fbb0  mov     [rbp+11A0h+var_1210], rax
0x18001fbb4  lea     rdx, aGetrootpath; "GetRootPath"
0x18001fbbb  call    cs:__imp_GetProcAddress
0x18001fbc2  nop     dword ptr [rax+rax+00h]
0x18001fbc7  mov     rdi, rax
0x18001fbca  mov     rcx, [rbp+11A8h]; this
0x18001fbd1  test    rax, rax
0x18001fbd4  jz      loc_18002057E
0x18001fbda  mov     r8d, 800h
0x18001fbe0  lea     rdx, [rbp+11A0h+var_1040]
0x18001fbe7  lea     rcx, aData; "DATA"
0x18001fbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbf3  mov     ebx, eax
0x18001fbf5  xor     edx, edx
0x18001fbf7  test    eax, eax
0x18001fbf9  jns     short loc_18001FC4E
0x18001fbfb  mov     [rbp+11A0h+var_10CC], eax
0x18001fc01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001fc08  test    rcx, rcx
0x18001fc0b  jz      short loc_18001FC4E
0x18001fc0d  lea     r9, aFailedToDeterm_1; "Failed to determine DATA partition root"...
0x18001fc14  lea     r8d, [rdx+3]
0x18001fc18  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001fc1d  lea     rax, [rbp+11A0h+var_10CC]
0x18001fc24  mov     qword ptr [rbp+11A0h+var_1220], rax
0x18001fc28  lea     rax, [rbp+11A0h+var_1220]
0x18001fc2c  mov     qword ptr [rsp+12A0h+var_1280], rax; int
0x18001fc31  lea     r9, asc_1801CAFB4; ": {}"
0x18001fc38  mov     r8d, 3
0x18001fc3e  mov     dl, 1
0x18001fc40  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001fc47  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001fc4c  xor     edx, edx
0x18001fc4e  mov     rcx, [rbp+11A8h]; this
0x18001fc55  test    ebx, ebx
0x18001fc57  js      loc_180020590
0x18001fc5d  lea     rax, aSystemdataTemp; "\\SystemData\\Temp"
0x18001fc64  mov     qword ptr [rbp+11A0h+var_1220], rax
0x18001fc68  mov     [rbp+11A0h+var_1218], 10h
0x18001fc70  lea     rax, [rbp+11A0h+var_1040]
0x18001fc77  mov     [rsp+12A0h+var_1238], rax
0x18001fc7c  lea     rcx, [rbp+11A0h+var_1040]
0x18001fc83  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001fc87  mov     rax, rbx
0x18001fc8a  inc     rax
0x18001fc8d  cmp     [rcx+rax*2], dx
0x18001fc91  jnz     short loc_18001FC8A
0x18001fc93  mov     [rsp+12A0h+var_1230], rax
0x18001fc98  lea     r8, [rbp+11A0h+var_1220]
0x18001fc9c  lea     rdx, [rsp+12A0h+var_1238]
0x18001fca1  lea     rcx, [rbp+11A0h+var_1208]
0x18001fca5  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18001fcaa  nop
0x18001fcab  mov     rcx, [rax+10h]
0x18001fcaf  cmp     qword ptr [rax+18h], 7
0x18001fcb4  jbe     short loc_18001FCB9
0x18001fcb6  mov     rax, [rax]
0x18001fcb9  mov     [rsp+12A0h+var_1238], rax
0x18001fcbe  mov     [rsp+12A0h+var_1230], rcx
0x18001fcc3  mov     rdx, rsi
0x18001fcc6  lea     rcx, [rsp+12A0h+var_1238]
0x18001fccb  call    ?GetTemporaryFileName@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetTemporaryFileName(wil::basic_zstring_view<wchar_t> const &,std::wstring *)
0x18001fcd0  mov     rcx, [rbp+11A8h]; this
0x18001fcd7  test    eax, eax
0x18001fcd9  js      loc_1800205A5
0x18001fcdf  lea     rcx, [rbp+11A0h+var_1208]; void *
0x18001fce3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fce8  xorps   xmm0, xmm0
0x18001fceb  movups  [rbp+11A0h+var_1080], xmm0
0x18001fcf2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001fcfa  movdqu  [rbp+11A0h+var_1070], xmm1
0x18001fd02  xor     ecx, ecx
0x18001fd04  mov     word ptr [rbp+11A0h+var_1080], cx
0x18001fd0b  movups  [rbp+11A0h+var_10A0], xmm0
0x18001fd12  movdqu  [rbp+11A0h+var_1090], xmm1
0x18001fd1a  mov     word ptr [rbp+11A0h+var_10A0], cx
0x18001fd21  mov     r8d, 800h
0x18001fd27  lea     rdx, [rbp+11A0h+var_1040]
0x18001fd2e  lea     rcx, aMainos_1; "MAINOS"
0x18001fd35  mov     rax, rdi
0x18001fd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd3d  lea     rax, aWindows; "\\Windows"
0x18001fd44  mov     [rsp+12A0h+var_1238], rax
0x18001fd49  mov     [rsp+12A0h+var_1230], 8
0x18001fd52  lea     rax, [rbp+11A0h+var_1040]
0x18001fd59  mov     qword ptr [rbp+11A0h+var_1220], rax
0x18001fd5d  lea     rcx, [rbp+11A0h+var_1040]
0x18001fd64  mov     rax, rbx
0x18001fd67  xor     edi, edi
0x18001fd69  inc     rax
0x18001fd6c  cmp     [rcx+rax*2], di
0x18001fd70  jnz     short loc_18001FD69
0x18001fd72  mov     [rbp+11A0h+var_1218], rax
0x18001fd76  lea     r8, [rsp+12A0h+var_1238]
0x18001fd7b  lea     rdx, [rbp+11A0h+var_1220]
0x18001fd7f  lea     rcx, [rbp+11A0h+var_1208]
0x18001fd83  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18001fd88  mov     rdx, rax
0x18001fd8b  lea     rcx, [rbp+11A0h+var_1080]
0x18001fd92  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fd97  lea     rcx, [rbp+11A0h+var_1208]; void *
0x18001fd9b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fda0  lea     rax, aWindowsImageup; "\\Windows\\ImageUpdate\\CompDBs"
0x18001fda7  mov     [rsp+12A0h+var_1238], rax
0x18001fdac  mov     [rsp+12A0h+var_1230], 1Ch
0x18001fdb5  lea     rax, [rbp+11A0h+var_1040]
0x18001fdbc  mov     qword ptr [rbp+11A0h+var_1220], rax
0x18001fdc0  lea     rax, [rbp+11A0h+var_1040]
0x18001fdc7  inc     rbx
0x18001fdca  cmp     [rax+rbx*2], di
0x18001fdce  jnz     short loc_18001FDC7
0x18001fdd0  mov     [rbp+11A0h+var_1218], rbx
0x18001fdd4  lea     r8, [rsp+12A0h+var_1238]
0x18001fdd9  lea     rdx, [rbp+11A0h+var_1220]
0x18001fddd  lea     rcx, [rbp+11A0h+var_1208]
0x18001fde1  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18001fde6  mov     rdx, rax
0x18001fde9  lea     rcx, [rbp+11A0h+var_10A0]
0x18001fdf0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fdf5  lea     rcx, [rbp+11A0h+var_1208]; void *
0x18001fdf9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fdfe  xorps   xmm0, xmm0
0x18001fe01  movdqu  [rbp+11A0h+var_10C8], xmm0
0x18001fe09  mov     [rbp+11A0h+var_10B8], rdi
0x18001fe10  mov     rdi, qword ptr [rsp+12A0h+var_1228]
0x18001fe15  mov     rdx, [rdi+8]
0x18001fe19  add     rdx, [r12+8]
0x18001fe1e  lea     rcx, [rbp+11A0h+var_10C8]
0x18001fe25  call    ?reserve@?$vector@UFeatureDescriptor@@V?$allocator@UFeatureDescriptor@@@std@@@std@@QEAAX_K@Z; std::vector<FeatureDescriptor>::reserve(unsigned __int64)
0x18001fe2a  mov     rbx, [rdi]
0x18001fe2d  mov     rax, [rdi+8]
0x18001fe31  lea     rdi, [rbx+rax*8]
0x18001fe35  cmp     rbx, rdi
0x18001fe38  jz      short loc_18001FE9C
0x18001fe3a  xor     r9d, r9d
0x18001fe3d  mov     rax, [rbx]
0x18001fe40  mov     [rbp+11A0h+var_1200], r9
0x18001fe44  mov     [rbp+11A0h+var_11F4], r9d
0x18001fe48  mov     rcx, [rax]
0x18001fe4b  mov     [rbp+11A0h+var_1208], rcx
0x18001fe4f  mov     r8d, [rax+14h]
0x18001fe53  mov     [rbp+11A0h+var_11F8], r8d
0x18001fe57  mov     rdx, qword ptr [rbp+11A0h+var_10C8+8]
0x18001fe5e  cmp     rdx, [rbp+11A0h+var_10B8]
0x18001fe65  jz      short loc_18001FE80
0x18001fe67  mov     [rdx], rcx
0x18001fe6a  mov     [rdx+8], r9
0x18001fe6e  mov     [rdx+10h], r8d
0x18001fe72  mov     [rdx+14h], r9d
0x18001fe76  add     qword ptr [rbp+11A0h+var_10C8+8], 18h
0x18001fe7e  jmp     short loc_18001FE93
0x18001fe80  lea     r8, [rbp+11A0h+var_1208]
0x18001fe84  lea     rcx, [rbp+11A0h+var_10C8]
0x18001fe8b  call    ??$_Emplace_reallocate@UCustomInfoPair@ActionList@@@?$vector@UCustomInfoPair@ActionList@@V?$allocator@UCustomInfoPair@ActionList@@@std@@@std@@AEAAPEAUCustomInfoPair@ActionList@@QEAU23@$$QEAU23@@Z; std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(ActionList::CustomInfoPair * const,ActionList::CustomInfoPair &&)
0x18001fe90  xor     r9d, r9d
0x18001fe93  add     rbx, 8
0x18001fe97  cmp     rbx, rdi
0x18001fe9a  jnz     short loc_18001FE3D
0x18001fe9c  mov     rbx, [r12]
0x18001fea0  mov     rax, [r12+8]
0x18001fea5  lea     rdi, [rbx+rax*8]
0x18001fea9  xor     r12d, r12d
0x18001feac  cmp     rbx, rdi
0x18001feaf  jz      short loc_18001FF0A
0x18001feb1  mov     rax, [rbx]
0x18001feb4  mov     [rbp+11A0h+var_1200], r12
0x18001feb8  mov     [rbp+11A0h+var_11F8], r12d
0x18001febc  mov     rcx, [rax]
0x18001febf  mov     [rbp+11A0h+var_1208], rcx
0x18001fec3  mov     r8d, [rax+14h]
0x18001fec7  mov     [rbp+11A0h+var_11F4], r8d
0x18001fecb  mov     rdx, qword ptr [rbp+11A0h+var_10C8+8]
0x18001fed2  cmp     rdx, [rbp+11A0h+var_10B8]
0x18001fed9  jz      short loc_18001FEF4
0x18001fedb  mov     [rdx], rcx
0x18001fede  mov     [rdx+8], r12
0x18001fee2  mov     [rdx+10h], r12d
0x18001fee6  mov     [rdx+14h], r8d
0x18001feea  add     qword ptr [rbp+11A0h+var_10C8+8], 18h
0x18001fef2  jmp     short loc_18001FF04
0x18001fef4  lea     r8, [rbp+11A0h+var_1208]
0x18001fef8  lea     rcx, [rbp+11A0h+var_10C8]
0x18001feff  call    ??$_Emplace_reallocate@UCustomInfoPair@ActionList@@@?$vector@UCustomInfoPair@ActionList@@V?$allocator@UCustomInfoPair@ActionList@@@std@@@std@@AEAAPEAUCustomInfoPair@ActionList@@QEAU23@$$QEAU23@@Z; std::vector<ActionList::CustomInfoPair>::_Emplace_reallocate<ActionList::CustomInfoPair>(ActionList::CustomInfoPair * const,ActionList::CustomInfoPair &&)
0x18001ff04  add     rbx, 8
0x18001ff08  jmp     short loc_18001FEAC
0x18001ff0a  mov     qword ptr [rbp+11A0h+var_1220], r12
0x18001ff0e  lea     rax, ??_7SessionData@@6B@; const SessionData::`vftable'
0x18001ff15  mov     [rbp+11A0h+var_1130], rax
0x18001ff19  mov     [rbp+11A0h+var_1120], r12
0x18001ff20  mov     [rbp+11A0h+var_1108], r12
0x18001ff27  mov     [rbp+11A0h+var_1100], r12
0x18001ff2e  mov     [rbp+11A0h+var_10F8], r12d
0x18001ff35  xorps   xmm0, xmm0
0x18001ff38  movdqa  [rbp+11A0h+var_10F0], xmm0
0x18001ff40  mov     [rbp+11A0h+var_10E0], r12d
0x18001ff47  mov     [rbp+11A0h+var_10D8], r12
0x18001ff4e  mov     [rbp+11A0h+var_1128], 12h
0x18001ff55  mov     rax, qword ptr [rbp+11A0h+var_10C8]
0x18001ff5c  mov     [rbp+11A0h+var_1118], rax
0x18001ff63  mov     rcx, qword ptr [rbp+11A0h+var_10C8+8]
0x18001ff6a  sub     rcx, rax
0x18001ff6d  sar     rcx, 3
0x18001ff71  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001ff7b  imul    rcx, rax
0x18001ff7f  mov     [rbp+11A0h+var_1110], ecx
0x18001ff85  lea     rcx, [rbp+11A0h+var_1130]; struct SessionData *
0x18001ff89  call    ?SessionDataToJson@@YAPEA_WAEBUSessionData@@@Z; SessionDataToJson(SessionData const &)
0x18001ff8e  mov     rbx, rax
0x18001ff91  mov     qword ptr [rbp+11A0h+var_1220], rax
0x18001ff95  mov     rcx, [rbp+11A8h]; this
0x18001ff9c  test    rax, rax
0x18001ff9f  jz      loc_1800205BA
0x18001ffa5  mov     rdx, [rbp+11A0h+var_1140]
0x18001ffa9  add     rdx, 8
0x18001ffad  lea     rcx, [rbp+11A0h+var_1060]
0x18001ffb4  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBD@Z; to_wstring(char const * const)
0x18001ffb9  nop
0x18001ffba  mov     rcx, [rsi+10h]
0x18001ffbe  mov     rax, rsi
0x18001ffc1  cmp     qword ptr [rsi+18h], 7
0x18001ffc6  jbe     short loc_18001FFCB
0x18001ffc8  mov     rax, [rsi]
0x18001ffcb  mov     [rsp+12A0h+var_1238], rax
0x18001ffd0  mov     [rsp+12A0h+var_1230], rcx
0x18001ffd5  lea     rcx, [rsp+12A0h+var_1238]
0x18001ffda  call    ?DestroyDirectory@@YAXAEBV?$basic_zstring_view@_W@wil@@@Z; DestroyDirectory(wil::basic_zstring_view<wchar_t> const &)
0x18001ffdf  lea     rax, aActionlistXml; "ActionList.xml"
0x18001ffe6  mov     [rsp+12A0h+var_1238], rax
0x18001ffeb  mov     [rsp+12A0h+var_1230], 0Eh
0x18001fff4  cmp     qword ptr [rsi+18h], 7
0x18001fff9  jbe     short loc_180020000
0x18001fffb  mov     rax, [rsi]
0x18001fffe  jmp     short loc_180020003
0x180020000  mov     rax, rsi
0x180020003  mov     [rbp+11A0h+var_1208], rax
0x180020007  mov     rax, [rsi+10h]
0x18002000b  mov     [rbp+11A0h+var_1200], rax
0x18002000f  lea     r8, [rsp+12A0h+var_1238]
0x180020014  lea     rdx, [rbp+11A0h+var_1208]
0x180020018  lea     rcx, [rbp+11A0h+var_11D8]
0x18002001c  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180020021  mov     rdx, rax
0x180020024  mov     rcx, r13
0x180020027  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002002c  lea     rcx, [rbp+11A0h+var_11D8]; void *
0x180020030  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020035  mov     eax, [rsp+12A0h+var_1240]
0x180020039  and     eax, 4
0x18002003c  mov     [rsp+12A0h+var_1240], eax
0x180020040  mov     rcx, [rbp+11A0h+var_1140]
0x180020044  cmp     [rcx+0B0h], r12
0x18002004b  ja      short loc_1800200C4
0x18002004d  test    eax, eax
0x18002004f  jnz     short loc_1800200C4
0x180020051  test    byte ptr [rcx+0A0h], 3
0x180020058  jnz     short loc_1800200C4
0x18002005a  mov     r9, qword ptr [rsp+12A0h+var_1228]
0x18002005f  cmp     [r9+8], r12
0x180020063  setz    dl
0x180020066  mov     [rbp+11A0h+var_10D0], r12b
0x18002006d  cmp     [r15], r12
0x180020070  jnz     loc_1800205CC
0x180020076  mov     dil, r12b
0x180020079  mov     rax, [rbp+11A0h+var_1210]
0x18002007d  mov     [rsp+12A0h+var_1268], rax
0x180020082  lea     rax, [rbp+11A0h+var_10D0]
0x180020089  mov     [rsp+12A0h+var_1270], rax
0x18002008e  mov     [rsp+12A0h+var_1278], r15
0x180020093  mov     qword ptr [rsp+12A0h+var_1280], r13
0x180020098  mov     r9, rsi
0x18002009b  mov     r8, rbx
0x18002009e  call    CallUSO
  ... truncated ...
```
