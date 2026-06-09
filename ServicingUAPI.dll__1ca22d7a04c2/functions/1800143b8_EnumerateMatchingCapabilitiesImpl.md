# EnumerateMatchingCapabilitiesImpl

- ea: `0x1800143b8`
- end: `0x180015644`
- name: `EnumerateMatchingCapabilitiesImpl`
- size: `4748`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180013c64`
- `0x18001416c`

## callees

- `0x1800031d0`
- `0x180006198`
- `0x1800062b8`
- `0x18000693e`
- `0x180006a58`
- `0x180008a90`
- `0x18000aedc`
- `0x18000c468`
- `0x18000f5cc`
- `0x18000f614`
- `0x18000f874`
- `0x180010a18`
- `0x180010cd0`
- `0x1800126d4`
- `0x18001284c`
- `0x180012944`
- `0x180012a70`
- `0x1800130a0`
- `0x1800132dc`
- `0x1800134f4`
- `0x1800137b8`
- `0x180013860`
- `0x1800143b8`
- `0x180015684`
- `0x180015b10`
- `0x180016070`
- `0x18001631c`
- `0x180016558`
- `0x180016578`
- `0x180049274`
- `0x18004d970`
- `0x1800ebb74`
- `0x1801a03d8`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014551`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001493b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015409`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001493b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015409`

## string_xrefs

- `0x180014aa2`: `Failed to get install state`
- `0x180014e5a`: `Failed to get install size`
- `0x180014fc4`: `Failed to get install timestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
char __fastcall EnumerateMatchingCapabilitiesImpl(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        int *a10)
{
  _DWORD *v13; // rdi
  char v14; // al
  char v15; // r14
  wchar_t *v16; // r8
  _WORD *v17; // rcx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  size_t v20; // rdx
  _WORD *v21; // rdi
  __int64 v22; // rbx
  size_t v23; // rbx
  size_t v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  wil::details::in1diag3 *v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // ebx
  char v32; // r12
  __int64 v33; // rsi
  __int64 v34; // r14
  __int64 v35; // rbx
  _OWORD *v36; // r15
  int v37; // eax
  int v38; // edi
  __int64 v39; // rdx
  int v40; // eax
  int v41; // edi
  __int64 v42; // rdx
  void *v43; // rcx
  void *v44; // rdi
  _QWORD *v45; // rdx
  void *v46; // rcx
  void *v47; // rcx
  const char *v48; // r9
  int v49; // eax
  int v50; // edi
  __int64 v51; // rdx
  _DWORD *v52; // rdi
  int v53; // esi
  int v54; // r14d
  __int64 v55; // rax
  int v56; // ecx
  int v57; // ecx
  void *v58; // rcx
  int v59; // ecx
  void *v60; // rcx
  int v61; // edi
  int v62; // esi
  const char *v63; // r9
  _DWORD *v64; // rax
  _QWORD *v65; // rcx
  LPVOID v66; // rax
  __int64 v67; // rsi
  _QWORD *v68; // rdx
  void *v69; // rdi
  void *v70; // rcx
  int v71; // eax
  wchar_t **v72; // r8
  int v73; // edi
  __int64 v74; // rdx
  int v75; // eax
  char v76; // di
  int v77; // eax
  int v78; // edi
  __int64 v79; // rdx
  int v80; // eax
  int v81; // edi
  __int64 v82; // rdx
  int v83; // eax
  int v84; // edi
  __int64 v85; // rdx
  int v86; // eax
  int v87; // edi
  __int64 v88; // rdx
  wchar_t *v89; // rcx
  int v90; // eax
  _QWORD *v91; // rcx
  __int64 v92; // r14
  void *v93; // rdi
  Windows::COM *v94; // rcx
  int v95; // eax
  Windows::COM *v96; // rcx
  int v97; // eax
  _QWORD **v98; // rdi
  _QWORD **v99; // r12
  void *v100; // rsi
  wchar_t **v101; // r8
  int v102; // ecx
  int v103; // ecx
  int v104; // eax
  _QWORD *v105; // rcx
  _QWORD *v106; // rdx
  void *v107; // rcx
  unsigned int v108; // eax
  unsigned int v109; // eax
  int *v110; // [rsp+20h] [rbp-E0h]
  int v111; // [rsp+20h] [rbp-E0h]
  char v112; // [rsp+50h] [rbp-B0h]
  char v113; // [rsp+51h] [rbp-AFh]
  int v114[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v115; // [rsp+60h] [rbp-A0h]
  char v116; // [rsp+61h] [rbp-9Fh]
  void *v117; // [rsp+68h] [rbp-98h] BYREF
  __int64 v118; // [rsp+70h] [rbp-90h]
  __int64 v119; // [rsp+78h] [rbp-88h]
  __int64 v120; // [rsp+80h] [rbp-80h]
  _DWORD *v121; // [rsp+88h] [rbp-78h]
  __int64 v122; // [rsp+90h] [rbp-70h]
  __int64 v123; // [rsp+98h] [rbp-68h]
  __int64 v124; // [rsp+A0h] [rbp-60h]
  _BYTE v125[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v126[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v127[16]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v128; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID v129; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v130; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v131; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v132; // [rsp+100h] [rbp+0h]
  __int128 v133; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *v134; // [rsp+118h] [rbp+18h]
  wchar_t *Buffer; // [rsp+120h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+128h] [rbp+28h] BYREF
  int v137; // [rsp+130h] [rbp+30h] BYREF
  __int64 v138; // [rsp+138h] [rbp+38h] BYREF
  int v139; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v140; // [rsp+148h] [rbp+48h]
  __int128 v141; // [rsp+150h] [rbp+50h] BYREF
  _WORD *v142; // [rsp+160h] [rbp+60h]
  int v143; // [rsp+168h] [rbp+68h] BYREF
  int v144; // [rsp+16Ch] [rbp+6Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v123 = -2;
  v122 = a4;
  v118 = a6;
  v120 = a7;
  v119 = a8;
  v13 = a9;
  v121 = a9;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a5 == 8 )
  {
    v14 = 1;
    v112 = 1;
    goto LABEL_7;
  }
  v14 = 0;
  v112 = 0;
  if ( (a5 & 0x40) == 0 )
  {
LABEL_7:
    v113 = 0;
    v15 = v14;
    if ( v14 )
      goto LABEL_12;
    goto LABEL_8;
  }
  v113 = 1;
  v112 = 0;
  v15 = 0;
LABEL_8:
  if ( (a2 & 1) != 0 )
  {
    v116 = 1;
    goto LABEL_13;
  }
LABEL_12:
  v116 = 0;
  if ( !v14 )
  {
LABEL_13:
    v115 = 1;
    if ( (a2 & 2) != 0 )
      goto LABEL_15;
  }
  v115 = 0;
LABEL_15:
  v140 = 0;
  v133 = 0;
  v134 = 0;
  v131 = 0;
  v132 = 0;
  v16 = 0;
  Buffer = 0;
  v130 = 0;
  if ( !a4 )
    goto LABEL_43;
  v17 = *(_WORD **)a4;
  if ( *(_QWORD *)a4 && *v17 )
  {
    v141 = 0;
    v142 = 0;
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    *(_QWORD *)&v141 = 2 * v18;
    *((_QWORD *)&v141 + 1) = 2 * v18 + 2;
    v142 = v17;
    SplitFeatureName(
      (unsigned int)&v141,
      (unsigned int)&v133,
      (unsigned int)&Buffer,
      (unsigned int)&v131,
      (__int64)&v130);
    v16 = Buffer;
    goto LABEL_43;
  }
  v19 = *(const wchar_t **)(a4 + 8);
  if ( v19 && *v19 )
  {
    if ( !wcschr(v19, 0x7Eu) )
    {
      v16 = *(wchar_t **)(a4 + 8);
      goto LABEL_43;
    }
    v20 = 0;
    *(_QWORD *)&v133 = 0;
    v21 = *(_WORD **)(a4 + 8);
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( v21[v22] );
      v23 = 2 * v22;
    }
    else
    {
      v23 = 0;
      v21 = 0;
    }
    v24 = v23 + 2;
    if ( v23 + 2 < v23 )
    {
      v26 = -1073741675;
    }
    else
    {
      v15 = v112;
      v25 = *((_QWORD *)&v133 + 1);
      if ( *((_QWORD *)&v133 + 1) < v24 )
      {
        v26 = RtlReallocateLUnicodeString(v24, v23 + 2, &v133);
        if ( v26 < 0 )
        {
LABEL_39:
          v27 = retaddr;
          if ( v26 < 0 )
            goto LABEL_243;
          v28 = ShredStringIdIntoAttributes(v134, 0x7Eu, (const wchar_t **)&Buffer, 0, 0, (const wchar_t **)&v130, 0);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
              (const char *)(unsigned int)v28,
              v111);
          v16 = Buffer;
          v13 = v121;
          goto LABEL_43;
        }
        v25 = *((_QWORD *)&v133 + 1);
        v20 = v133;
      }
      if ( v23 )
      {
        if ( v23 > v25 - v20 )
          goto LABEL_245;
        memcpy_0(&v134[v20 >> 1], v21, v23);
        v20 = v23 + v133;
        *(_QWORD *)&v133 = v23 + v133;
      }
      v134[v20 >> 1] = 0;
      v26 = 0;
    }
    v112 = v15;
    goto LABEL_39;
  }
LABEL_43:
  if ( v140 )
  {
LABEL_245:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  LODWORD(v110) = 0;
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, wchar_t *))(*(_QWORD *)a1 + 144LL))(a1, a5, v16, v130);
  if ( v30 < 0 )
  {
    if ( v13 )
      *v13 = 2;
    if ( a10 )
      *a10 = v30;
    if ( (a3 & 1) == 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
        LogAdapter::Logger::Log<>(v29, 3, "Failed enumerating capabilities");
      v108 = EnsureNTSTATUS<long>((unsigned int)v30);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x150,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
        (const char *)v108,
        0);
    }
    if ( v132 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine();
      v131 = 0;
      v132 = 0;
    }
    if ( v134 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine();
      v133 = 0;
      v134 = 0;
    }
    if ( v140 )
      (*(void (__fastcall **)(_QWORD *))(*v140 + 16LL))(v140);
    return 0;
  }
  v32 = 0;
  if ( v132 )
  {
    anonymous_namespace_::OurRtlFreeStringRoutine();
    v131 = 0;
    v132 = 0;
  }
  if ( v134 )
    anonymous_namespace_::OurRtlFreeStringRoutine();
  v139 = 0;
  v138 = 0;
LABEL_62:
  v33 = v119;
LABEL_63:
  v34 = v118;
  while ( 1 )
  {
    if ( v138 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_243:
      wil::details::in1diag3::_Throw_NtStatus(
        v27,
        (void *)0x12C,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
        (const char *)(unsigned int)v26,
        (int)v110);
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD *, __int64, __int64 *, int *))(*v140 + 24LL))(v140, 1, &v138, &v139)
      || !v139 )
    {
      break;
    }
    v35 = v138;
    v124 = v138;
    v138 = 0;
    v117 = 0;
    v36 = operator new(0x28u);
    *(_QWORD *)v114 = v36;
    *v36 = 0;
    v36[1] = 0;
    *((_QWORD *)v36 + 4) = 0;
    v117 = v36;
    v129 = 0;
    pv = 0;
    v144 = 0;
    v143 = 0;
    v110 = &v144;
    v37 = (*(__int64 (__fastcall **)(__int64, _OWORD *, LPVOID *, LPVOID *))(*(_QWORD *)v35 + 112LL))(
            v35,
            v36,
            &v129,
            &pv);
    v38 = v37;
    if ( v37 < 0 )
    {
      LODWORD(v128) = v37;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get capability");
        *(_QWORD *)v114 = &v128;
        v110 = v114;
        LOBYTE(v39) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v39,
          3,
          ": {}");
      }
    }
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
        (const char *)(unsigned int)v38,
        (int)v110);
    JoinFeatureName(v36, v129);
    v40 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v35 + 32LL))(v35, 35, (__int64)v36 + 8);
    v41 = v40;
    if ( v40 < 0 )
    {
      LODWORD(v128) = v40;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get capability identity");
        *(_QWORD *)v114 = &v128;
        v110 = v114;
        LOBYTE(v42) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v42,
          3,
          ": {}");
      }
    }
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
        (const char *)(unsigned int)v41,
        (int)v110);
    v43 = pv;
    v44 = 0;
    if ( pv )
    {
      pv = 0;
      CoTaskMemFree(v43);
    }
    if ( v112 )
    {
      v32 = 1;
      v45 = *(_QWORD **)(v33 + 8);
      if ( v45 == *(_QWORD **)(v33 + 16) )
      {
        std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>(
          v33,
          v45,
          &v117);
        v44 = v117;
      }
      else
      {
        v117 = 0;
        *v45 = v36;
        *(_QWORD *)(v33 + 8) += 8LL;
      }
      *(_QWORD *)v114 = v36;
      std::_Tree<std::_Tset_traits<FeatureId const *,ptrFeatureIdCompare,std::allocator<FeatureId const *>,0>>::emplace<FeatureId *>(
        v34,
        v125,
        v114);
      v46 = v129;
      if ( v129 )
      {
        v129 = 0;
        CoTaskMemFree(v46);
      }
      if ( v44 )
      {
        Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v44);
        operator delete(v44);
      }
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    else
    {
      *(_QWORD *)v114 = v36;
      if ( !std::_Tree<std::_Tset_traits<FeatureId const *,ptrFeatureIdCompare,std::allocator<FeatureId const *>,0>>::count(
              v120,
              v114) )
      {
        v137 = -16;
        pv = 0;
        if ( !Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResultInfo,3,&void CloseWithFreeFeatureResultInfo(FeatureResultInfo)>>::Allocate<>(&pv) )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x190,
            (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
            v48);
        if ( !v113 )
        {
          v49 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 152LL))(v35, &v137);
          v50 = v49;
          if ( v49 < 0 )
          {
            LODWORD(v128) = v49;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get install state");
              *(_QWORD *)v114 = &v128;
              v110 = v114;
              LOBYTE(v51) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v51,
                3,
                ": {}");
            }
          }
          if ( v50 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x199,
              (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
              (const char *)(unsigned int)v50,
              (int)v110);
        }
        v52 = pv;
        if ( v137 == 5 || (unsigned int)(v137 - 7) < 2 )
        {
          v53 = 64;
          v54 = 4;
        }
        else
        {
          v53 = 0;
          v54 = 0;
        }
        *(_QWORD *)v114 = v36;
        v55 = std::_Tree<std::_Tset_traits<FeatureId const *,ptrFeatureIdCompare,std::allocator<FeatureId const *>,0>>::count(
                v118,
                v114);
        v56 = v53 | 1;
        if ( !v55 )
          v56 = v53;
        v52[1] = v56;
        *v52 = v54;
        *((_QWORD *)v36 + 2) = v52;
        if ( !v122 )
        {
LABEL_121:
          if ( v115 )
          {
            if ( v137 == 5 )
            {
              v62 = 0;
              v61 = 1;
            }
            else
            {
              if ( v137 != 6 )
                goto LABEL_128;
              v61 = 0;
              v62 = 4;
            }
            pv = 0;
            if ( !Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResultInfo,3,&void CloseWithFreeFeatureResultInfo(FeatureResultInfo)>>::Allocate<>(&pv) )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x1E8,
                (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                v63);
            v64 = pv;
            *(_DWORD *)pv = v62;
            v64[1] = v61;
            *((_QWORD *)v36 + 3) = v64;
          }
LABEL_128:
          v133 = 0;
          v134 = 0;
          if ( v129 && *(_WORD *)v129 )
          {
            v128 = 0;
            v65 = operator new(0x18u);
            *(_QWORD *)v114 = v65;
            *(_OWORD *)v65 = 0;
            v65[2] = 0;
            v128 = v65;
            *v65 = 0;
            *((_DWORD *)v65 + 2) = 2;
            *((_DWORD *)v65 + 3) = 2;
            v66 = v129;
            v129 = 0;
            v65[2] = v66;
            if ( *((wchar_t **)&v133 + 1) == v134 )
            {
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                &v133,
                *((_QWORD *)&v133 + 1),
                &v128);
            }
            else
            {
              v128 = 0;
              **((_QWORD **)&v133 + 1) = v65;
              *((_QWORD *)&v133 + 1) += 8LL;
            }
            Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
          }
          v67 = *((_QWORD *)v36 + 2);
          if ( v116 )
          {
            v71 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 136LL))(v35, v67 + 24);
            v73 = v71;
            if ( v71 < 0 )
            {
              LODWORD(v128) = v71;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get download size");
                *(_QWORD *)v114 = &v128;
                v110 = v114;
                LOBYTE(v74) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v74,
                  3,
                  ": {}");
              }
            }
            if ( v73 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x20F,
                (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                (const char *)(unsigned int)v73,
                (int)v110);
            v75 = 0;
            v130 = 0;
            v76 = v113;
            if ( !v113 )
            {
              v77 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 144LL))(v35, v67 + 32);
              v78 = v77;
              if ( v77 < 0 )
              {
                LODWORD(v128) = v77;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get install size");
                  *(_QWORD *)v114 = &v128;
                  v110 = v114;
                  LOBYTE(v79) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v79,
                    3,
                    ": {}");
                }
              }
              if ( v78 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x217,
                  (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                  (const char *)(unsigned int)v78,
                  (int)v110);
              v80 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v35 + 32LL))(v35, 2, v67 + 16);
              v81 = v80;
              if ( v80 < 0 )
              {
                LODWORD(v128) = v80;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get display name");
                  *(_QWORD *)v114 = &v128;
                  v110 = v114;
                  LOBYTE(v82) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v82,
                    3,
                    ": {}");
                }
              }
              if ( v81 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x21B,
                  (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                  (const char *)(unsigned int)v81,
                  (int)v110);
              v83 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v35 + 32LL))(v35, 3, v67 + 8);
              v84 = v83;
              if ( v83 < 0 )
              {
                LODWORD(v128) = v83;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get description");
                  *(_QWORD *)v114 = &v128;
                  v110 = v114;
                  LOBYTE(v85) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v85,
                    3,
                    ": {}");
                }
              }
              if ( v84 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x21F,
                  (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                  (const char *)(unsigned int)v84,
                  (int)v110);
              Buffer = 0;
              v86 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v35 + 32LL))(v35, 17, &Buffer);
              v87 = v86;
              if ( v86 < 0 )
              {
                LODWORD(v128) = v86;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get install timestamp");
                  *(_QWORD *)v114 = &v128;
                  v110 = v114;
                  LOBYTE(v88) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v88,
                    3,
                    ": {}");
                }
              }
              if ( v87 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x224,
                  (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                  (const char *)(unsigned int)v87,
                  (int)v110);
              v89 = Buffer;
              if ( Buffer )
              {
                if ( *Buffer )
                {
                  v90 = swscanf_s(Buffer, L"%08x%08x", (char *)&v130 + 4, &v130, v110, &v143);
                  v89 = Buffer;
                  if ( v90 == -1 )
                    v130 = 0;
                }
              }
              if ( v89 )
              {
                CoTaskMemFree(v89);
                Buffer = 0;
              }
              GetCustomInformationProperties(v35, &v133);
              v75 = (int)v130;
              v76 = 0;
            }
            if ( (*(_BYTE *)v67 & 4) != 0 && (v75 || HIDWORD(v130)) )
            {
              v128 = 0;
              v91 = operator new(0x18u);
              *(_QWORD *)v114 = v91;
              *(_OWORD *)v91 = 0;
              v91[2] = 0;
              v128 = v91;
              *v91 = 0;
              *((_DWORD *)v91 + 2) = 3;
              *((_DWORD *)v91 + 3) = 3;
              v91[2] = v130;
              if ( *((wchar_t **)&v133 + 1) == v134 )
              {
                std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                  &v133,
                  *((_QWORD *)&v133 + 1),
                  &v128);
              }
              else
              {
                v128 = 0;
                **((_QWORD **)&v133 + 1) = v91;
                *((_QWORD *)&v133 + 1) += 8LL;
              }
              Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
            }
            if ( (_QWORD)v133 != *((_QWORD *)&v133 + 1) )
              DisownResults<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,FeatureProperties>(
                &v133,
                v67 + 40);
            if ( !v76 )
            {
              v131 = 0;
              v132 = 0;
              GetDependencies(v35, &v131);
              if ( (_QWORD)v131 != *((_QWORD *)&v131 + 1) )
                DisownResults<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>,FeatureDependencies>(
                  &v131,
                  *((_QWORD *)v36 + 2) + 56LL);
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>>>(&v131);
              v131 = 0;
              v132 = 0;
              GetDependencies(v35, &v131);
              if ( (_QWORD)v131 != *((_QWORD *)&v131 + 1) )
                DisownResults<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>,FeatureDependencies>(
                  &v131,
                  *((_QWORD *)v36 + 2) + 56LL);
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>>>(&v131);
            }
            v92 = *((_QWORD *)v36 + 3);
            v93 = 0;
            if ( v92 )
            {
              *(_QWORD *)(v92 + 24) = *(_QWORD *)(v67 + 24);
              *(_QWORD *)(v92 + 32) = *(_QWORD *)(v67 + 32);
              v94 = *(Windows::COM **)(v67 + 16);
              if ( v94 )
              {
                if ( *(_WORD *)v94 )
                {
                  v95 = Windows::COM::CopyOut(v94, (const wchar_t *)(v67 + 16), v72);
                  if ( v95 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x26D,
                      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                      (const char *)(unsigned int)v95,
                      (int)v110);
                }
              }
              v96 = *(Windows::COM **)(v67 + 8);
              if ( v96 )
              {
                if ( *(_WORD *)v96 )
                {
                  v97 = Windows::COM::CopyOut(v96, (const wchar_t *)(v67 + 8), v72);
                  if ( v97 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x272,
                      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                      (const char *)(unsigned int)v97,
                      (int)v110);
                }
              }
              v131 = 0;
              v132 = 0;
              v98 = *(_QWORD ***)(v67 + 40);
              v99 = &v98[*(_QWORD *)(v67 + 48)];
              while ( v98 != v99 )
              {
                if ( *((_DWORD *)*v98 + 3) != 3 )
                {
                  v128 = 0;
                  v100 = operator new(0x18u);
                  *(_QWORD *)v114 = v100;
                  *(_OWORD *)v100 = 0;
                  *((_QWORD *)v100 + 2) = 0;
                  v128 = v100;
                  *(_QWORD *)v100 = **v98;
                  *((_DWORD *)v100 + 2) = *((_DWORD *)*v98 + 2);
                  v102 = *((_DWORD *)*v98 + 3);
                  *((_DWORD *)v100 + 3) = v102;
                  v103 = v102 - 1;
                  if ( v103 )
                  {
                    if ( v103 != 1 )
                    {
                      v109 = EnsureNTSTATUS<long>(2147549183LL);
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x294,
                        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                        (const char *)v109,
                        (int)v110);
                    }
                    v104 = Windows::COM::CopyOut((Windows::COM *)(*v98)[2], (const wchar_t *)v100 + 8, v101);
                    if ( v104 < 0 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x291,
                        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_desktop.cpp",
                        (const char *)(unsigned int)v104,
                        (int)v110);
                  }
                  else
                  {
                    *((_QWORD *)v100 + 2) = (*v98)[2];
                  }
                  if ( *((_QWORD *)&v131 + 1) == v132 )
                  {
                    std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                      &v131,
                      *((_QWORD *)&v131 + 1),
                      &v128);
                  }
                  else
                  {
                    v128 = 0;
                    **((_QWORD **)&v131 + 1) = v100;
                    *((_QWORD *)&v131 + 1) += 8LL;
                  }
                  Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
                }
                ++v98;
              }
              v93 = 0;
              if ( (*(_BYTE *)v92 & 4) != 0 && v130 )
              {
                v128 = 0;
                v105 = operator new(0x18u);
                *(_QWORD *)v114 = v105;
                *(_OWORD *)v105 = 0;
                v105[2] = 0;
                v128 = v105;
                *v105 = 0;
                *((_DWORD *)v105 + 2) = 3;
                *((_DWORD *)v105 + 3) = 3;
                v105[2] = v130;
                if ( *((_QWORD *)&v131 + 1) == v132 )
                {
                  std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                    &v131,
                    *((_QWORD *)&v131 + 1),
                    &v128);
                }
                else
                {
                  v128 = 0;
                  **((_QWORD **)&v131 + 1) = v105;
                  *((_QWORD *)&v131 + 1) += 8LL;
                }
                Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
              }
              if ( (_QWORD)v131 != *((_QWORD *)&v131 + 1) )
                DisownResults<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,FeatureProperties>(
                  &v131,
                  v92 + 40);
              if ( !v113 )
              {
                v141 = 0;
                v142 = 0;
                GetDependencies(v35, &v141);
                if ( (_QWORD)v141 != *((_QWORD *)&v141 + 1) )
                  DisownResults<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>,FeatureDependencies>(
                    &v141,
                    v92 + 56);
                std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureDependency,4,&void CloseWithFreeFeatureDependency(FeatureDependency)>>>(&v141);
              }
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v131);
            }
            v32 = 1;
            v33 = v119;
            v106 = *(_QWORD **)(v119 + 8);
            if ( v106 == *(_QWORD **)(v119 + 16) )
            {
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>(
                v119,
                v106,
                &v117);
              v93 = v117;
            }
            else
            {
              v117 = 0;
              *v106 = v36;
              *(_QWORD *)(v33 + 8) += 8LL;
            }
            *(_QWORD *)v114 = v36;
            std::_Tree<std::_Tset_traits<FeatureId const *,ptrFeatureIdCompare,std::allocator<FeatureId const *>,0>>::emplace<FeatureId *>(
              v120,
              v127,
              v114);
            std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v133);
            v107 = v129;
            if ( v129 )
            {
              v129 = 0;
              CoTaskMemFree(v107);
            }
            if ( v93 )
            {
              Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v93);
              operator delete(v93);
            }
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          else
          {
            if ( (_QWORD)v133 != *((_QWORD *)&v133 + 1) )
              DisownResults<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,FeatureProperties>(
                &v133,
                v67 + 40);
            v32 = 1;
            v33 = v119;
            v68 = *(_QWORD **)(v119 + 8);
            if ( v68 == *(_QWORD **)(v119 + 16) )
            {
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>(
                v119,
                v68,
                &v117);
              v69 = v117;
            }
            else
            {
              v69 = 0;
              v117 = 0;
              *v68 = v36;
              *(_QWORD *)(v33 + 8) += 8LL;
            }
            *(_QWORD *)v114 = v36;
            std::_Tree<std::_Tset_traits<FeatureId const *,ptrFeatureIdCompare,std::allocator<FeatureId const *>,0>>::emplace<FeatureId *>(
              v120,
              v126,
              v114);
            std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v133);
            v70 = v129;
            if ( v129 )
            {
              v129 = 0;
              CoTaskMemFree(v70);
            }
            if ( v69 )
            {
              Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v69);
              operator delete(v69);
            }
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          goto LABEL_63;
        }
        v57 = *(_DWORD *)(v122 + 20);
        if ( !v57 || (v57 & v52[1]) == v57 )
        {
          v59 = *(_DWORD *)(v122 + 16);
          if ( !v59 || (v59 & *v52) == v59 )
            goto LABEL_121;
          v60 = v129;
          if ( v129 )
          {
            v129 = 0;
            CoTaskMemFree(v60);
          }
          Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v36);
          operator delete(v36);
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        else
        {
          v58 = v129;
          if ( v129 )
          {
            v129 = 0;
            CoTaskMemFree(v58);
          }
          Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v36);
          operator delete(v36);
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        goto LABEL_62;
      }
      v47 = v129;
      if ( v129 )
      {
        v129 = 0;
        CoTaskMemFree(v47);
      }
      Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v36);
      operator delete(v36);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
  }
  if ( v121 )
    *v121 = 1;
  if ( v138 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 16LL))(v138);
    v138 = 0;
  }
  if ( v140 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v140 + 16LL))(v140, *v140);
  return v32;
}

```

## disassembly

```asm
0x1800143b8  mov     rax, rsp
0x1800143bb  push    rbp
0x1800143bc  push    rsi
0x1800143bd  push    rdi
0x1800143be  push    r12
0x1800143c0  push    r13
0x1800143c2  push    r14
0x1800143c4  push    r15
0x1800143c6  lea     rbp, [rsp-80h]
0x1800143cb  sub     rsp, 180h
0x1800143d2  mov     [rbp+0B0h+var_118], 0FFFFFFFFFFFFFFFEh
0x1800143da  mov     [rax+10h], rbx
0x1800143de  mov     rax, cs:__security_cookie
0x1800143e5  xor     rax, rsp
0x1800143e8  mov     [rbp+0B0h+var_40], rax
0x1800143ec  mov     rbx, r9
0x1800143ef  mov     [rbp+0B0h+var_120], rbx
0x1800143f3  mov     r13d, r8d
0x1800143f6  mov     r12, rcx
0x1800143f9  mov     rax, [rbp+0B0h+arg_28]
0x180014400  mov     [rsp+1B0h+var_140], rax
0x180014405  mov     rax, [rbp+0B0h+arg_30]
0x18001440c  mov     [rbp+0B0h+var_130], rax
0x180014410  mov     rax, [rbp+0B0h+arg_38]
0x180014417  mov     [rsp+1B0h+var_138], rax
0x18001441c  mov     rdi, [rbp+0B0h+arg_40]
0x180014423  mov     [rbp+0B0h+var_128], rdi
0x180014427  mov     rsi, [rbp+0B0h+arg_48]
0x18001442e  xor     r9d, r9d
0x180014431  test    rdi, rdi
0x180014434  jz      short loc_180014439
0x180014436  mov     [rdi], r9d
0x180014439  test    rsi, rsi
0x18001443c  jz      short loc_180014441
0x18001443e  mov     [rsi], r9d
0x180014441  mov     r15d, [rbp+0B0h+arg_20]
0x180014448  cmp     r15d, 8
0x18001444c  jnz     short loc_18001446C
0x18001444e  mov     al, 1
0x180014450  mov     [rsp+1B0h+var_160], al
0x180014454  mov     [rsp+1B0h+var_15F], r9b
0x180014459  mov     r14b, al
0x18001445c  test    al, al
0x18001445e  jnz     short loc_180014487
0x180014460  test    dl, 1
0x180014463  jz      short loc_180014487
0x180014465  mov     [rsp+1B0h+var_14F], 1
0x18001446a  jmp     short loc_180014490
0x18001446c  mov     al, r9b
0x18001446f  mov     [rsp+1B0h+var_160], al
0x180014473  test    r15b, 40h
0x180014477  jz      short loc_180014454
0x180014479  mov     [rsp+1B0h+var_15F], 1
0x18001447e  mov     [rsp+1B0h+var_160], al
0x180014482  mov     r14b, r9b
0x180014485  jmp     short loc_180014460
0x180014487  mov     [rsp+1B0h+var_14F], r9b
0x18001448c  test    al, al
0x18001448e  jnz     short loc_18001449A
0x180014490  test    dl, 2
0x180014493  mov     [rsp+1B0h+var_150], 1
0x180014498  jnz     short loc_18001449F
0x18001449a  mov     [rsp+1B0h+var_150], r9b
0x18001449f  mov     [rbp+0B0h+var_68], r9
0x1800144a3  xorps   xmm0, xmm0
0x1800144a6  xor     eax, eax
0x1800144a8  movups  [rbp+0B0h+var_A8], xmm0
0x1800144ac  mov     [rbp+0B0h+var_98], rax
0x1800144b0  movups  [rbp+0B0h+var_C0], xmm0
0x1800144b4  mov     [rbp+0B0h+var_B0], rax
0x1800144b8  mov     r8, r9
0x1800144bb  mov     [rbp+0B0h+Buffer], r9
0x1800144bf  mov     [rbp+0B0h+var_C8], r9
0x1800144c3  test    rbx, rbx
0x1800144c6  jz      loc_180014670
0x1800144cc  mov     rcx, [rbx]
0x1800144cf  test    rcx, rcx
0x1800144d2  jz      short loc_180014535
0x1800144d4  cmp     r9w, [rcx]
0x1800144d8  jz      short loc_180014535
0x1800144da  movups  [rbp+0B0h+var_60], xmm0
0x1800144de  mov     [rbp+0B0h+var_50], rax
0x1800144e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800144e6  inc     rax
0x1800144e9  cmp     [rcx+rax*2], r9w
0x1800144ee  jnz     short loc_1800144E6
0x1800144f0  add     rax, rax
0x1800144f3  mov     qword ptr [rbp+0B0h+var_60], rax
0x1800144f7  add     rax, 2
0x1800144fb  mov     qword ptr [rbp+0B0h+var_60+8], rax
0x1800144ff  movups  xmm0, [rbp+0B0h+var_60]
0x180014503  movups  [rbp+0B0h+var_60], xmm0
0x180014507  mov     [rbp+0B0h+var_50], rcx
0x18001450b  lea     rax, [rbp+0B0h+var_C8]
0x18001450f  mov     [rsp+1B0h+var_190], rax
0x180014514  lea     r9, [rbp+0B0h+var_C0]
0x180014518  lea     r8, [rbp+0B0h+Buffer]
0x18001451c  lea     rdx, [rbp+0B0h+var_A8]
0x180014520  lea     rcx, [rbp+0B0h+var_60]
0x180014524  call    SplitFeatureName
0x180014529  mov     r8, [rbp+0B0h+Buffer]
0x18001452d  xor     r9d, r9d
0x180014530  jmp     loc_180014670
0x180014535  mov     rcx, [rbx+8]; Str
0x180014539  test    rcx, rcx
0x18001453c  jz      loc_180014670
0x180014542  cmp     r9w, [rcx]
0x180014546  jz      loc_180014670
0x18001454c  mov     edx, 7Eh ; '~'; Ch
0x180014551  call    cs:__imp_wcschr
0x180014558  nop     dword ptr [rax+rax+00h]
0x18001455d  xor     r9d, r9d
0x180014560  test    rax, rax
0x180014563  jz      loc_18001466C
0x180014569  mov     edx, r9d
0x18001456c  mov     qword ptr [rbp+0B0h+var_A8], rdx
0x180014570  mov     rdi, [rbx+8]
0x180014574  test    rdi, rdi
0x180014577  jz      short loc_18001458C
0x180014579  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001457d  inc     rbx
0x180014580  cmp     [rdi+rbx*2], r9w
0x180014585  jnz     short loc_18001457D
0x180014587  add     rbx, rbx
0x18001458a  jmp     short loc_180014592
0x18001458c  mov     rbx, r9
0x18001458f  mov     rdi, r9
0x180014592  lea     rcx, [rbx+2]
0x180014596  cmp     rcx, rbx
0x180014599  jb      short loc_18001460F
0x18001459b  mov     r14b, [rsp+1B0h+var_160]
0x1800145a0  mov     [rsp+1B0h+var_160], r14b
0x1800145a5  mov     rax, qword ptr [rbp+0B0h+var_A8+8]
0x1800145a9  cmp     rax, rcx
0x1800145ac  jnb     short loc_1800145C9
0x1800145ae  lea     r8, [rbp+0B0h+var_A8]
0x1800145b2  mov     rdx, rcx
0x1800145b5  call    RtlReallocateLUnicodeString
0x1800145ba  xor     r9d, r9d
0x1800145bd  test    eax, eax
0x1800145bf  js      short loc_180014619
0x1800145c1  mov     rax, qword ptr [rbp+0B0h+var_A8+8]
0x1800145c5  mov     rdx, qword ptr [rbp+0B0h+var_A8]
0x1800145c9  test    rbx, rbx
0x1800145cc  jz      short loc_1800145FE
0x1800145ce  sub     rax, rdx
0x1800145d1  cmp     rbx, rax
0x1800145d4  ja      loc_1800154F4
0x1800145da  shr     rdx, 1
0x1800145dd  mov     rax, [rbp+0B0h+var_98]
0x1800145e1  lea     rcx, [rax+rdx*2]; void *
0x1800145e5  mov     r8, rbx; Size
0x1800145e8  mov     rdx, rdi; Src
0x1800145eb  call    memcpy_0
0x1800145f0  mov     rdx, qword ptr [rbp+0B0h+var_A8]
0x1800145f4  add     rdx, rbx
0x1800145f7  mov     qword ptr [rbp+0B0h+var_A8], rdx
0x1800145fb  xor     r9d, r9d
0x1800145fe  mov     rcx, [rbp+0B0h+var_98]
0x180014602  shr     rdx, 1
0x180014605  mov     [rcx+rdx*2], r9w
0x18001460a  mov     eax, r9d
0x18001460d  jmp     short loc_180014614
0x18001460f  mov     eax, 0C0000095h
0x180014614  mov     [rsp+1B0h+var_160], r14b
0x180014619  mov     rcx, [rbp+0B8h]
0x180014620  test    eax, eax
0x180014622  js      loc_1800154CA
0x180014628  mov     edx, 7Eh ; '~'; wchar_t
0x18001462d  mov     [rsp+1B0h+var_180], r9; wchar_t **
0x180014632  lea     rax, [rbp+0B0h+var_C8]
0x180014636  mov     [rsp+1B0h+var_188], rax; wchar_t **
0x18001463b  mov     [rsp+1B0h+var_190], r9; int
0x180014640  xor     r9d, r9d; wchar_t **
0x180014643  lea     r8, [rbp+0B0h+Buffer]; wchar_t **
0x180014647  mov     rcx, [rbp+0B0h+var_98]; wchar_t *
0x18001464b  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x180014650  mov     rcx, [rbp+0B8h]; this
0x180014657  xor     r9d, r9d
0x18001465a  test    eax, eax
0x18001465c  js      loc_1800154DF
0x180014662  mov     r8, [rbp+0B0h+Buffer]
0x180014666  mov     rdi, [rbp+0B0h+var_128]
0x18001466a  jmp     short loc_180014670
0x18001466c  mov     r8, [rbx+8]
0x180014670  cmp     [rbp+0B0h+var_68], r9
0x180014674  jnz     loc_1800154F4
0x18001467a  mov     rax, [r12]
0x18001467e  lea     rcx, [rbp+0B0h+var_68]
0x180014682  mov     [rsp+1B0h+var_178], rcx
0x180014687  mov     dword ptr [rsp+1B0h+var_180], r9d
0x18001468c  mov     dword ptr [rsp+1B0h+var_188], r9d
0x180014691  mov     [rsp+1B0h+var_190], r9; int
0x180014696  mov     r9, [rbp+0B0h+var_C8]
0x18001469a  mov     edx, r15d
0x18001469d  mov     rcx, r12
0x1800146a0  mov     rax, [rax+90h]
0x1800146a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146ac  mov     ebx, eax
0x1800146ae  test    eax, eax
0x1800146b0  jns     loc_180014748
0x1800146b6  test    rdi, rdi
0x1800146b9  jz      short loc_1800146C1
0x1800146bb  mov     dword ptr [rdi], 2
0x1800146c1  test    rsi, rsi
0x1800146c4  jz      short loc_1800146C8
0x1800146c6  mov     [rsi], ebx
0x1800146c8  test    r13b, 1
0x1800146cc  jz      loc_1800154FF
0x1800146d2  mov     rcx, [rbp+0B0h+var_B0]
0x1800146d6  test    rcx, rcx
0x1800146d9  jz      short loc_1800146ED
0x1800146db  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800146e0  xorps   xmm0, xmm0
0x1800146e3  xor     eax, eax
0x1800146e5  movups  [rbp+0B0h+var_C0], xmm0
0x1800146e9  mov     [rbp+0B0h+var_B0], rax
0x1800146ed  mov     rcx, [rbp+0B0h+var_98]
0x1800146f1  test    rcx, rcx
0x1800146f4  jz      short loc_180014708
0x1800146f6  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800146fb  xorps   xmm0, xmm0
0x1800146fe  xor     eax, eax
0x180014700  movups  [rbp+0B0h+var_A8], xmm0
0x180014704  mov     [rbp+0B0h+var_98], rax
0x180014708  mov     rcx, [rbp+0B0h+var_68]
0x18001470c  test    rcx, rcx
0x18001470f  jz      short loc_18001471E
0x180014711  mov     rax, [rcx]
0x180014714  mov     rax, [rax+10h]
0x180014718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001471d  nop
0x18001471e  xor     al, al
0x180014720  mov     rcx, [rbp+0B0h+var_40]
0x180014724  xor     rcx, rsp; StackCookie
0x180014727  call    __security_check_cookie
0x18001472c  mov     rbx, [rsp+1B0h+arg_8]
0x180014734  add     rsp, 180h
0x18001473b  pop     r15
0x18001473d  pop     r14
0x18001473f  pop     r13
0x180014741  pop     r12
0x180014743  pop     rdi
0x180014744  pop     rsi
0x180014745  pop     rbp
0x180014746  retn
0x180014748  xor     r12b, r12b
0x18001474b  mov     rcx, [rbp+0B0h+var_B0]
0x18001474f  test    rcx, rcx
0x180014752  jz      short loc_180014766
0x180014754  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180014759  xorps   xmm0, xmm0
0x18001475c  xor     eax, eax
0x18001475e  movups  [rbp+0B0h+var_C0], xmm0
0x180014762  mov     [rbp+0B0h+var_B0], rax
0x180014766  mov     rcx, [rbp+0B0h+var_98]
0x18001476a  cmp     rcx, 1
0x18001476e  jb      short loc_180014776
0x180014770  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180014775  nop
0x180014776  mov     [rbp+0B0h+var_70], 0
0x18001477d  mov     [rbp+0B0h+var_78], 0
0x180014785  mov     r13d, 3
0x18001478b  mov     rsi, [rsp+1B0h+var_138]
0x180014790  mov     r14, [rsp+1B0h+var_140]
0x180014795  cmp     [rbp+0B0h+var_78], 0
0x18001479a  jnz     loc_1800154BF
0x1800147a0  mov     rcx, [rbp+0B0h+var_68]
0x1800147a4  mov     rax, [rcx]
0x1800147a7  lea     r9, [rbp+0B0h+var_70]
0x1800147ab  lea     r8, [rbp+0B0h+var_78]
0x1800147af  mov     edx, 1
0x1800147b4  mov     rax, [rax+18h]
0x1800147b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147bd  test    eax, eax
0x1800147bf  jnz     loc_18001544B
0x1800147c5  cmp     [rbp+0B0h+var_70], eax
0x1800147c8  jbe     loc_18001544B
0x1800147ce  mov     rbx, [rbp+0B0h+var_78]
0x1800147d2  mov     [rbp+0B0h+var_110], rbx
0x1800147d6  mov     [rbp+0B0h+var_78], 0
0x1800147de  mov     [rsp+1B0h+var_148], 0
0x1800147e7  lea     ecx, [rax+28h]; Size
0x1800147ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800147ef  mov     r15, rax
0x1800147f2  mov     qword ptr [rsp+1B0h+var_158], rax
0x1800147f7  xorps   xmm0, xmm0
0x1800147fa  xor     eax, eax
0x1800147fc  movups  xmmword ptr [r15], xmm0
0x180014800  movups  xmmword ptr [r15+10h], xmm0
0x180014805  mov     [r15+20h], rax
0x180014809  mov     [rsp+1B0h+var_148], r15
0x18001480e  mov     [rbp+0B0h+var_D0], rax
0x180014812  mov     [rbp+0B0h+pv], rax
0x180014816  mov     [rbp+0B0h+var_44], eax
0x180014819  mov     [rbp+0B0h+var_48], eax
0x18001481c  mov     rax, [rbx]
0x18001481f  lea     rcx, [rbp+0B0h+var_48]
0x180014823  mov     [rsp+1B0h+var_188], rcx
0x180014828  lea     rcx, [rbp+0B0h+var_44]
  ... truncated ...
```
