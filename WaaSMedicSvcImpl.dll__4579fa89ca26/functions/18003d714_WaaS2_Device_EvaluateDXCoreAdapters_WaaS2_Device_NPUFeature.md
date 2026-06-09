# WaaS2::Device::EvaluateDXCoreAdapters_WaaS2::Device::NPUFeature_

- ea: `0x18003d714`
- end: `0x18003e039`
- name: `WaaS2::Device::EvaluateDXCoreAdapters_WaaS2::Device::NPUFeature_`
- size: `2341`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004ece0`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180005584`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000ea1c`
- `0x18000f860`
- `0x18001e5a0`
- `0x18002cbc4`
- `0x18003d714`
- `0x18003f7c4`
- `0x18003fd64`
- `0x180040ba0`
- `0x180040d30`
- `0x1800424f8`
- `0x180043cfc`
- `0x180044218`
- `0x180045c68`
- `0x180046544`
- `0x180046bf4`
- `0x180047300`
- `0x1800474e4`
- `0x1800481bc`
- `0x180048548`
- `0x180049514`
- `0x1800541c8`
- `0x18005fd14`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d793`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d793`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003e007`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003e007`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003d775`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003d775`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18003d75a`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18003d75a`

## string_xrefs

- `0x18003d789`: `DXCoreCreateAdapterFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall WaaS2::Device::EvaluateDXCoreAdapters_WaaS2::Device::NPUFeature_(
        __int64 a1,
        _QWORD *a2,
        __int64 ***a3,
        __int64 *a4)
{
  HMODULE LibraryA; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v10; // ebx
  int v11; // eax
  char v12; // r15
  _QWORD *v13; // rax
  __int64 *v14; // rbx
  __int64 **v15; // r13
  int v16; // eax
  unsigned int v17; // r14d
  unsigned int i; // esi
  __int64 (__fastcall *v19)(_QWORD, _QWORD, GUID *, struct IDXCoreAdapter **); // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 **v23; // rcx
  __int64 *j; // rax
  __int64 *v25; // rcx
  __int64 *v26; // rdx
  int v27; // eax
  __int64 *k; // rcx
  _QWORD *v29; // rax
  _QWORD *v30; // r15
  const wchar_t *v31; // rsi
  const wchar_t *v32; // rcx
  _QWORD *v33; // r13
  __int64 **v34; // r11
  __int64 *v35; // rcx
  __int64 *v36; // rdx
  __int64 *v37; // r12
  __int64 v38; // r8
  __int64 v39; // rbx
  __int64 v40; // r14
  __int64 v41; // rbx
  __int64 v42; // r14
  wchar_t *v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 *v46; // rbx
  __int64 **v47; // r13
  __int64 *v48; // rdx
  __int64 *v49; // rcx
  int v50; // eax
  __int64 **v51; // rcx
  __int64 *m; // rax
  __int64 *n; // rcx
  _QWORD *v54; // r13
  wchar_t *v55; // rsi
  wchar_t *ii; // rbx
  const wchar_t *v57; // rcx
  wchar_t *v58; // r15
  const wchar_t *v59; // r14
  const wchar_t *v60; // rcx
  wchar_t *v61; // r14
  WaaS2::Device::DXCoreFeatureBase *v62; // r14
  WaaS2::Device::DXCoreFeatureBase *v63; // rsi
  void *v64; // rcx
  _QWORD *v65; // rbx
  void *v66; // rcx
  int *v67; // [rsp+20h] [rbp-E0h]
  char v68[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct IDXCoreAdapter *v69; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v70; // [rsp+40h] [rbp-C0h] BYREF
  int v71[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v72; // [rsp+50h] [rbp-B0h]
  __int64 v73; // [rsp+58h] [rbp-A8h] BYREF
  void *v74[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v75; // [rsp+70h] [rbp-90h] BYREF
  __int64 v76; // [rsp+80h] [rbp-80h]
  _QWORD *v77; // [rsp+88h] [rbp-78h]
  _QWORD v78[3]; // [rsp+90h] [rbp-70h] BYREF
  char v79[16]; // [rsp+A8h] [rbp-58h] BYREF
  char v80[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v81; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v82; // [rsp+D8h] [rbp-28h]
  __int64 v83; // [rsp+E0h] [rbp-20h]
  _BYTE v84[480]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v72 = a4;
  v77 = a2;
  if ( !IsApiSetImplemented("ext-ms-win-dxcore-l1-1-0") )
    return 0;
  LibraryA = LoadLibraryA("ext-ms-win-dxcore-l1-1-0");
  v8 = LibraryA;
  v78[2] = LibraryA;
  if ( !LibraryA )
    return 0;
  ProcAddress = GetProcAddress(LibraryA, "DXCoreCreateAdapterFactory");
  if ( !ProcAddress )
  {
    v10 = 0;
    goto LABEL_148;
  }
  v73 = 0;
  v11 = ((__int64 (__fastcall *)(GUID *, __int64 *))ProcAddress)(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v73);
  v10 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xABA,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)(unsigned int)v11,
      (int)v67);
    if ( v73 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    goto LABEL_148;
  }
  v81 = 0;
  v82 = 0;
  v83 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v81, L"Hardware", 8);
  v12 = WaaS2::Device::URIContext::ContainsSegment(a1, &v81);
  std::wstring::~wstring(&v81);
  v75 = 0;
  v76 = 0;
  v74[0] = 0;
  v74[1] = 0;
  v13 = operator new(0x28u);
  *v13 = v13;
  v13[1] = v13;
  v13[2] = v13;
  *((_WORD *)v13 + 12) = 257;
  v74[0] = v13;
  v14 = **a3;
  v15 = (__int64 **)v72;
  while ( !*((_BYTE *)v14 + 25) )
  {
    *(_QWORD *)v71 = 0;
    v67 = v71;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, GUID *))(*(_QWORD *)v73 + 24LL))(
            v73,
            1,
            v14[4],
            &GUID_526c7776_40e9_459b_b711_f32ad76dfc28);
    if ( v16 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAC9,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)v16,
        (int)v71);
      goto LABEL_27;
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v71 + 32LL))(*(_QWORD *)v71);
    for ( i = 0; i < v17; ++i )
    {
      v69 = 0;
      v19 = *(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct IDXCoreAdapter **))(**(_QWORD **)v71 + 24LL);
      v69 = 0;
      v20 = v19(*(_QWORD *)v71, i, &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e, &v69);
      if ( v20 >= 0 )
      {
        if ( v12
          && (*(unsigned __int8 (__fastcall **)(struct IDXCoreAdapter *, __int64))(*(_QWORD *)v69 + 40LL))(v69, 11) )
        {
          v68[0] = 0;
          v21 = (*(__int64 (__fastcall **)(struct IDXCoreAdapter *, __int64, __int64, char *))(*(_QWORD *)v69 + 48LL))(
                  v69,
                  11,
                  1,
                  v68);
          if ( v21 >= 0 )
          {
            if ( !v68[0] )
              goto LABEL_24;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xAE0,
              (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
              (const char *)(unsigned int)v21,
              (int)v67);
          }
        }
        v70 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(struct IDXCoreAdapter *, _QWORD))(*(_QWORD *)v69 + 40LL))(v69, 0) )
        {
          v22 = (*(__int64 (__fastcall **)(struct IDXCoreAdapter *, _QWORD, __int64, _QWORD **))(*(_QWORD *)v69 + 48LL))(
                  v69,
                  0,
                  8,
                  &v70);
          if ( v22 >= 0 )
          {
            v25 = (__int64 *)(*v15)[1];
            v26 = *v15;
            while ( !*((_BYTE *)v25 + 25) )
            {
              if ( v25[4] < (__int64)v70 )
              {
                v25 = (__int64 *)v25[2];
              }
              else
              {
                v26 = v25;
                v25 = (__int64 *)*v25;
              }
            }
            if ( !*((_BYTE *)v26 + 25) && (__int64)v70 >= v26[4] && v26 != *v15 )
              goto LABEL_44;
            WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::DetectDXCoreAdapterHardwareIdParts((WaaS2::Device::DetectDXCoreAdapterHardwareIdParts *)v84);
            v27 = WaaS2::Device::DXCoreAdapterHardwareIdParts::Init(
                    (WaaS2::Device::DXCoreAdapterHardwareIdParts *)v84,
                    v69);
            if ( v27 >= 0 )
            {
              std::_Tree<std::_Tmap_traits<_LUID,WaaS2::Device::DXCoreAdapterHardwareIdParts,WaaS2::Device::LuidLess,std::allocator<std::pair<_LUID const,WaaS2::Device::DXCoreAdapterHardwareIdParts>>,0>>::emplace<_LUID &,WaaS2::Device::DXCoreAdapterHardwareIdParts>(
                v15,
                v79,
                &v70,
                v84);
              WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::~DetectDXCoreAdapterHardwareIdParts((WaaS2::Device::DetectDXCoreAdapterHardwareIdParts *)v84);
LABEL_44:
              if ( *(_BYTE *)(std::_Tree<std::_Tset_traits<_LUID,WaaS2::Device::LuidLess,std::allocator<_LUID>,0>>::insert<0,0>(
                                v74,
                                v80,
                                &v70)
                            + 8) )
              {
                if ( *((_QWORD *)&v75 + 1) == v76 )
                {
                  std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(&v75, *((_QWORD *)&v75 + 1), &v70);
                }
                else
                {
                  **((_QWORD **)&v75 + 1) = v70;
                  *((_QWORD *)&v75 + 1) += 8LL;
                }
              }
              goto LABEL_24;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xAF3,
              (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
              (const char *)(unsigned int)v27,
              (int)v67);
            WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::~DetectDXCoreAdapterHardwareIdParts((WaaS2::Device::DetectDXCoreAdapterHardwareIdParts *)v84);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xAEB,
              (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
              (const char *)(unsigned int)v22,
              (int)v67);
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAD3,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v20,
          (int)v67);
      }
LABEL_24:
      if ( v69 )
        (*(void (__fastcall **)(struct IDXCoreAdapter *))(*(_QWORD *)v69 + 16LL))(v69);
    }
LABEL_27:
    if ( *(_QWORD *)v71 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v71 + 16LL))(*(_QWORD *)v71);
    v23 = (__int64 **)v14[2];
    if ( *((_BYTE *)v23 + 25) )
    {
      for ( j = (__int64 *)v14[1]; !*((_BYTE *)j + 25) && v14 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v14 = j;
      v14 = j;
    }
    else
    {
      v14 = (__int64 *)v14[2];
      for ( k = *v23; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v14 = k;
    }
  }
  v78[0] = 0;
  v78[1] = 0;
  v29 = operator new(0x40u);
  *v29 = v29;
  v29[1] = v29;
  v29[2] = v29;
  *((_WORD *)v29 + 12) = 257;
  v78[0] = v29;
  v30 = (_QWORD *)*v77;
  v70 = (_QWORD *)v77[1];
  if ( v30 == v70 )
    goto LABEL_97;
  v31 = (const wchar_t *)(v30 + 65);
  do
  {
    if ( *((_QWORD *)v31 + 3) <= 7u )
      v32 = v31;
    else
      v32 = *(const wchar_t **)v31;
    if ( *((_QWORD *)v31 + 2) == 1 && !wmemcmp(v32, L"1", 1u) )
      goto LABEL_95;
    *(_QWORD *)v71 = *((_QWORD *)&v75 + 1);
    v33 = (_QWORD *)v75;
    if ( (_QWORD)v75 == *((_QWORD *)&v75 + 1) )
      goto LABEL_95;
    v34 = (__int64 **)v72;
    while ( 1 )
    {
      v35 = (__int64 *)(*v34)[1];
      v36 = *v34;
      while ( !*((_BYTE *)v35 + 25) )
      {
        if ( v35[4] < *v33 )
        {
          v35 = (__int64 *)v35[2];
        }
        else
        {
          v36 = v35;
          v35 = (__int64 *)*v35;
        }
      }
      if ( *((_BYTE *)v36 + 25) )
      {
        v36 = *v34;
      }
      else if ( *v33 < v36[4] )
      {
        v36 = *v34;
      }
      if ( v36 == *v34 )
        goto LABEL_80;
      v37 = v36 + 5;
      if ( (unsigned __int8)WaaS2::Device::DXCoreAdapterHardwareIdParts::MeetsCriteria<WaaS2::Device::NPUFeature>(
                              v36 + 5,
                              v30) )
        break;
LABEL_79:
      v34 = (__int64 **)v72;
LABEL_80:
      if ( ++v33 == *(_QWORD **)v71 )
        goto LABEL_95;
    }
    v39 = v30[69];
    v40 = v30[70];
    if ( v39 != v40 )
    {
      while ( !(unsigned __int8)WaaS2::Device::DXCoreAdapterHardwareIdParts::MeetsCriteria<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>(
                                  v37,
                                  v39) )
      {
        v39 += 480;
        if ( v39 == v40 )
          goto LABEL_79;
      }
    }
    v41 = v30[72];
    v42 = v30[73];
    while ( v41 != v42 )
    {
      if ( (unsigned __int8)WaaS2::Device::DXCoreAdapterHardwareIdParts::MeetsCriteria<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>(
                              v37,
                              v41) )
        goto LABEL_79;
      v41 += 480;
    }
    if ( *((_QWORD *)v31 + 3) )
    {
      if ( *((_QWORD *)v31 + 3) <= 7u )
        v43 = (wchar_t *)v31;
      else
        v43 = *(wchar_t **)v31;
      *((_QWORD *)v31 + 2) = 1;
      *v43 = ::a1[0];
      v43[1] = 0;
    }
    else
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v31, 1, v38, L"1");
    }
    v44 = std::map<_LUID,std::vector<std::wstring>,WaaS2::Device::LuidLess,std::allocator<std::pair<_LUID const,std::vector<std::wstring>>>>::operator[](
            v78,
            v33);
    v45 = *(_QWORD *)(v44 + 8);
    if ( v45 == *(_QWORD *)(v44 + 16) )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v44, v45, v30 + 61);
    }
    else
    {
      std::wstring::wstring(v45, v30 + 61);
      *(_QWORD *)(v44 + 8) += 32LL;
    }
LABEL_95:
    v30 += 75;
    v31 += 300;
  }
  while ( v30 != v70 );
  v29 = (_QWORD *)v78[0];
LABEL_97:
  v46 = (__int64 *)*v29;
  v47 = (__int64 **)v72;
  while ( !*((_BYTE *)v46 + 25) )
  {
    v48 = *v47;
    v49 = (__int64 *)(*v47)[1];
    while ( !*((_BYTE *)v49 + 25) )
    {
      if ( v49[4] < v46[4] )
      {
        v49 = (__int64 *)v49[2];
      }
      else
      {
        v48 = v49;
        v49 = (__int64 *)*v49;
      }
    }
    if ( !*((_BYTE *)v48 + 25) && v46[4] >= v48[4] && v48 != *v47 )
    {
      v50 = WaaS2::Device::DXCoreAdapterHardwareIdParts::LogDebugInfo(v48 + 5, v48, L"NPU");
      if ( v50 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB27,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v50,
          (int)v67);
    }
    v51 = (__int64 **)v46[2];
    if ( *((_BYTE *)v51 + 25) )
    {
      for ( m = (__int64 *)v46[1]; !*((_BYTE *)m + 25) && v46 == (__int64 *)m[2]; m = (__int64 *)m[1] )
        v46 = m;
      v46 = m;
    }
    else
    {
      v46 = (__int64 *)v46[2];
      for ( n = *v51; !*((_BYTE *)n + 25); n = (__int64 *)*n )
        v46 = n;
    }
  }
  v54 = v77;
  v55 = (wchar_t *)v77[1];
  for ( ii = (wchar_t *)*v77; ii != v55; ii += 300 )
  {
    v57 = ii + 260;
    if ( *((_QWORD *)ii + 68) > 7u )
      v57 = *(const wchar_t **)v57;
    if ( *((_QWORD *)ii + 67) != 1 || wmemcmp(v57, L"1", 1u) )
      break;
  }
  if ( ii != v55 )
  {
    v58 = ii + 300;
    if ( ii + 300 != v55 )
    {
      v59 = ii + 560;
      do
      {
        if ( *((_QWORD *)v59 + 3) <= 7u )
          v60 = v59;
        else
          v60 = *(const wchar_t **)v59;
        if ( *((_QWORD *)v59 + 2) == 1 && !wmemcmp(v60, L"1", 1u) )
        {
          WaaS2::Device::DXCoreFeatureBase::operator=(ii, v58);
          ii += 300;
        }
        v58 += 300;
        v59 += 300;
      }
      while ( v58 != v55 );
    }
    if ( ii != v55 )
    {
      v61 = (wchar_t *)v54[1];
      while ( v55 != v61 )
      {
        WaaS2::Device::DXCoreFeatureBase::operator=(ii, v55);
        ii += 300;
        v55 += 300;
      }
      v62 = (WaaS2::Device::DXCoreFeatureBase *)v54[1];
      v63 = (WaaS2::Device::DXCoreFeatureBase *)ii;
      if ( ii != (wchar_t *)v62 )
      {
        do
        {
          WaaS2::Device::DXCoreFeatureBase::~DXCoreFeatureBase(v63);
          v63 = (WaaS2::Device::DXCoreFeatureBase *)((char *)v63 + 600);
        }
        while ( v63 != v62 );
      }
      v54[1] = ii;
    }
  }
  std::_Tree<std::_Tmap_traits<_LUID,std::vector<std::wstring>,WaaS2::Device::LuidLess,std::allocator<std::pair<_LUID const,std::vector<std::wstring>>>,0>>::~_Tree<std::_Tmap_traits<_LUID,std::vector<std::wstring>,WaaS2::Device::LuidLess,std::allocator<std::pair<_LUID const,std::vector<std::wstring>>>,0>>(v78);
  v64 = v74[0];
  v65 = (_QWORD *)*((_QWORD *)v74[0] + 1);
  if ( !*((_BYTE *)v65 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<_GUID const *>>::_Erase_tree<std::allocator<std::_Tree_node<_GUID const *,void *>>>(
        v74,
        v74,
        v65[2]);
      v66 = v65;
      v65 = (_QWORD *)*v65;
      operator delete(v66, (const struct std::nothrow_t *)0x28);
    }
    while ( !*((_BYTE *)v65 + 25) );
    v64 = v74[0];
  }
  operator delete(v64, (const struct std::nothrow_t *)0x28);
  std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v75);
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  v10 = 0;
LABEL_148:
  FreeLibrary(v8);
  return v10;
}

```

## disassembly

```asm
0x18003d714  mov     [rsp-8+arg_10], rbx
0x18003d719  push    rbp
0x18003d71a  push    rsi
0x18003d71b  push    rdi
0x18003d71c  push    r12
0x18003d71e  push    r13
0x18003d720  push    r14
0x18003d722  push    r15
0x18003d724  lea     rbp, [rsp-1E0h]
0x18003d72c  sub     rsp, 2E0h
0x18003d733  mov     rax, cs:__security_cookie
0x18003d73a  xor     rax, rsp
0x18003d73d  mov     [rbp+210h+var_40], rax
0x18003d744  mov     [rsp+310h+var_2C0], r9
0x18003d749  mov     rsi, r8
0x18003d74c  mov     [rbp+210h+var_288], rdx
0x18003d750  mov     r14, rcx
0x18003d753  lea     rcx, Contract; "ext-ms-win-dxcore-l1-1-0"
0x18003d75a  call    cs:__imp_IsApiSetImplemented
0x18003d760  xor     r15d, r15d
0x18003d763  test    eax, eax
0x18003d765  jnz     short loc_18003D76E
0x18003d767  xor     eax, eax
0x18003d769  jmp     loc_18003E00F
0x18003d76e  lea     rcx, Contract; "ext-ms-win-dxcore-l1-1-0"
0x18003d775  call    cs:__imp_LoadLibraryA
0x18003d77b  mov     rdi, rax
0x18003d77e  mov     [rbp+210h+var_270], rax
0x18003d782  test    rax, rax
0x18003d785  jnz     short loc_18003D789
0x18003d787  jmp     short loc_18003D767
0x18003d789  lea     rdx, aDxcorecreatead; "DXCoreCreateAdapterFactory"
0x18003d790  mov     rcx, rdi; hModule
0x18003d793  call    cs:__imp_GetProcAddress
0x18003d799  test    rax, rax
0x18003d79c  jnz     short loc_18003D7A6
0x18003d79e  mov     ebx, r15d
0x18003d7a1  jmp     loc_18003E004
0x18003d7a6  mov     [rsp+310h+var_2B8], r15
0x18003d7ab  lea     rdx, [rsp+310h+var_2B8]
0x18003d7b0  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18003d7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7bc  mov     ebx, eax
0x18003d7be  test    eax, eax
0x18003d7c0  jns     short loc_18003D7FA
0x18003d7c2  mov     rcx, [rbp+218h]; this
0x18003d7c9  mov     r9d, eax; char *
0x18003d7cc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003d7d3  mov     edx, 0ABAh; void *
0x18003d7d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d7dd  nop
0x18003d7de  mov     rcx, [rsp+310h+var_2B8]
0x18003d7e3  test    rcx, rcx
0x18003d7e6  jz      short loc_18003D7F5
0x18003d7e8  mov     rax, [rcx]
0x18003d7eb  mov     rax, [rax+10h]
0x18003d7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7f4  nop
0x18003d7f5  jmp     loc_18003E004
0x18003d7fa  xorps   xmm0, xmm0
0x18003d7fd  movups  [rbp+210h+var_248], xmm0
0x18003d801  mov     [rbp+210h+var_238], r15
0x18003d805  mov     [rbp+210h+var_230], r15
0x18003d809  mov     r8d, 8
0x18003d80f  lea     rdx, aHardware; "Hardware"
0x18003d816  lea     rcx, [rbp+210h+var_248]
0x18003d81a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003d81f  lea     rdx, [rbp+210h+var_248]
0x18003d823  mov     rcx, r14
0x18003d826  call    ?ContainsSegment@URIContext@Device@WaaS2@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaaS2::Device::URIContext::ContainsSegment(std::wstring const &)
0x18003d82b  mov     r15b, al
0x18003d82e  lea     rcx, [rbp+210h+var_248]; void *
0x18003d832  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d837  xorps   xmm0, xmm0
0x18003d83a  movdqu  [rsp+310h+var_2A0], xmm0
0x18003d840  xor     r14d, r14d
0x18003d843  mov     [rbp+210h+var_290], r14
0x18003d847  mov     [rsp+310h+var_2B0], r14
0x18003d84c  mov     [rsp+310h+var_2A8], r14
0x18003d851  lea     ecx, [r14+28h]; Size
0x18003d855  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d85a  mov     [rax], rax
0x18003d85d  mov     [rax+8], rax
0x18003d861  mov     [rax+10h], rax
0x18003d865  mov     word ptr [rax+18h], 101h
0x18003d86b  mov     [rsp+310h+var_2B0], rax
0x18003d870  mov     rbx, [rsi]
0x18003d873  mov     rbx, [rbx]
0x18003d876  lea     r12, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003d87d  mov     r13, [rsp+310h+var_2C0]
0x18003d882  cmp     [rbx+19h], r14b
0x18003d886  jnz     loc_18003DBA2
0x18003d88c  mov     qword ptr [rsp+310h+var_2C8], r14
0x18003d891  mov     rcx, [rsp+310h+var_2B8]
0x18003d896  mov     rax, [rcx]
0x18003d899  lea     rdx, [rsp+310h+var_2C8]
0x18003d89e  mov     qword ptr [rsp+310h+var_2F0], rdx; int
0x18003d8a3  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18003d8aa  mov     r8, [rbx+20h]
0x18003d8ae  mov     edx, 1
0x18003d8b3  mov     rax, [rax+18h]
0x18003d8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8bc  mov     rcx, [rbp+218h]; this
0x18003d8c3  test    eax, eax
0x18003d8c5  jns     short loc_18003D8DD
0x18003d8c7  mov     r9d, eax; char *
0x18003d8ca  mov     r8, r12; unsigned int
0x18003d8cd  mov     edx, 0AC9h; void *
0x18003d8d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d8d7  nop
0x18003d8d8  jmp     loc_18003DA2F
0x18003d8dd  mov     rcx, qword ptr [rsp+310h+var_2C8]
0x18003d8e2  mov     rax, [rcx]
0x18003d8e5  mov     rax, [rax+20h]
0x18003d8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8ee  mov     r14d, eax
0x18003d8f1  xor     esi, esi
0x18003d8f3  test    eax, eax
0x18003d8f5  jz      loc_18003DA2C
0x18003d8fb  mov     [rsp+310h+var_2D8], 0
0x18003d904  mov     rcx, qword ptr [rsp+310h+var_2C8]
0x18003d909  mov     rdx, [rcx]
0x18003d90c  mov     rax, [rdx+18h]
0x18003d910  mov     [rsp+310h+var_2D8], 0
0x18003d919  lea     r9, [rsp+310h+var_2D8]
0x18003d91e  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18003d925  mov     edx, esi
0x18003d927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d92c  mov     rcx, [rbp+218h]; this
0x18003d933  test    eax, eax
0x18003d935  jns     short loc_18003D94D
0x18003d937  mov     r9d, eax; char *
0x18003d93a  mov     r8, r12; unsigned int
0x18003d93d  mov     edx, 0AD3h; void *
0x18003d942  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d947  nop
0x18003d948  jmp     loc_18003DA0A
0x18003d94d  test    r15b, r15b
0x18003d950  jz      short loc_18003D9AF
0x18003d952  mov     rcx, [rsp+310h+var_2D8]
0x18003d957  mov     rax, [rcx]
0x18003d95a  mov     edx, 0Bh
0x18003d95f  mov     rax, [rax+28h]
0x18003d963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d968  test    al, al
0x18003d96a  jz      short loc_18003D9AF
0x18003d96c  mov     [rsp+310h+var_2E0], 0
0x18003d971  mov     rcx, [rsp+310h+var_2D8]
0x18003d976  mov     rax, [rcx]
0x18003d979  lea     r9, [rsp+310h+var_2E0]
0x18003d97e  mov     edx, 0Bh
0x18003d983  lea     r8d, [rdx-0Ah]
0x18003d987  mov     rax, [rax+30h]
0x18003d98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d990  mov     rcx, [rbp+218h]; this
0x18003d997  test    eax, eax
0x18003d999  jns     loc_18003DA5D
0x18003d99f  mov     r9d, eax; char *
0x18003d9a2  mov     r8, r12; unsigned int
0x18003d9a5  mov     edx, 0AE0h; void *
0x18003d9aa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d9af  mov     [rsp+310h+var_2D0], 0
0x18003d9b8  mov     rcx, [rsp+310h+var_2D8]
0x18003d9bd  mov     rax, [rcx]
0x18003d9c0  xor     edx, edx
0x18003d9c2  mov     rax, [rax+28h]
0x18003d9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9cb  test    al, al
0x18003d9cd  jz      short loc_18003DA0A
0x18003d9cf  mov     rcx, [rsp+310h+var_2D8]
0x18003d9d4  mov     rax, [rcx]
0x18003d9d7  lea     r9, [rsp+310h+var_2D0]
0x18003d9dc  xor     edx, edx
0x18003d9de  lea     r8d, [rdx+8]
0x18003d9e2  mov     rax, [rax+30h]
0x18003d9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9eb  mov     rcx, [rbp+218h]; this
0x18003d9f2  xor     r10d, r10d
0x18003d9f5  test    eax, eax
0x18003d9f7  jns     short loc_18003DA6A
0x18003d9f9  mov     r9d, eax; char *
0x18003d9fc  mov     r8, r12; unsigned int
0x18003d9ff  mov     edx, 0AEBh; void *
0x18003da04  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003da09  nop
0x18003da0a  mov     rcx, [rsp+310h+var_2D8]
0x18003da0f  test    rcx, rcx
0x18003da12  jz      short loc_18003DA21
0x18003da14  mov     rax, [rcx]
0x18003da17  mov     rax, [rax+10h]
0x18003da1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da20  nop
0x18003da21  inc     esi
0x18003da23  cmp     esi, r14d
0x18003da26  jb      loc_18003D8FB
0x18003da2c  xor     r14d, r14d
0x18003da2f  mov     rcx, qword ptr [rsp+310h+var_2C8]
0x18003da34  test    rcx, rcx
0x18003da37  jz      short loc_18003DA46
0x18003da39  mov     rax, [rcx]
0x18003da3c  mov     rax, [rax+10h]
0x18003da40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da45  nop
0x18003da46  mov     rcx, [rbx+10h]
0x18003da4a  cmp     [rcx+19h], r14b
0x18003da4e  jz      loc_18003DB7E
0x18003da54  mov     rax, [rbx+8]
0x18003da58  jmp     loc_18003DB70
0x18003da5d  cmp     [rsp+310h+var_2E0], 0
0x18003da62  jnz     loc_18003D9AF
0x18003da68  jmp     short loc_18003DA0A
0x18003da6a  mov     r9, [r13+0]
0x18003da6e  mov     rcx, [r9+8]
0x18003da72  mov     rdx, r9
0x18003da75  mov     rax, [rsp+310h+var_2D0]
0x18003da7a  mov     r8d, dword ptr [rsp+310h+var_2D0+4]
0x18003da7f  jmp     short loc_18003DA9A
0x18003da81  cmp     [rcx+24h], r8d
0x18003da85  jl      short loc_18003DA96
0x18003da87  jnz     short loc_18003DA8E
0x18003da89  cmp     [rcx+20h], eax
0x18003da8c  jb      short loc_18003DA96
0x18003da8e  mov     rdx, rcx
0x18003da91  mov     rcx, [rcx]
0x18003da94  jmp     short loc_18003DA9A
0x18003da96  mov     rcx, [rcx+10h]
0x18003da9a  cmp     [rcx+19h], r10b
0x18003da9e  jz      short loc_18003DA81
0x18003daa0  cmp     [rdx+19h], r10b
0x18003daa4  jnz     short loc_18003DAB8
0x18003daa6  cmp     r8d, [rdx+24h]
0x18003daaa  jl      short loc_18003DAB8
0x18003daac  jnz     short loc_18003DAB3
0x18003daae  cmp     eax, [rdx+20h]
0x18003dab1  jb      short loc_18003DAB8
0x18003dab3  cmp     rdx, r9
0x18003dab6  jnz     short loc_18003DB1A
0x18003dab8  lea     rcx, [rbp+210h+var_220]; this
0x18003dabc  call    ??0DetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::DetectDXCoreAdapterHardwareIdParts(void)
0x18003dac1  nop
0x18003dac2  mov     rdx, [rsp+310h+var_2D8]; struct IDXCoreAdapter *
0x18003dac7  lea     rcx, [rbp+210h+var_220]; this
0x18003dacb  call    ?Init@DXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAAJPEAUIDXCoreAdapter@@@Z; WaaS2::Device::DXCoreAdapterHardwareIdParts::Init(IDXCoreAdapter *)
0x18003dad0  mov     rcx, [rbp+218h]; this
0x18003dad7  test    eax, eax
0x18003dad9  jns     short loc_18003DAFB
0x18003dadb  mov     r9d, eax; char *
0x18003dade  mov     r8, r12; unsigned int
0x18003dae1  mov     edx, 0AF3h; void *
0x18003dae6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003daeb  nop
0x18003daec  lea     rcx, [rbp+210h+var_220]; this
0x18003daf0  call    ??1DetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::~DetectDXCoreAdapterHardwareIdParts(void)
0x18003daf5  nop
0x18003daf6  jmp     loc_18003DA0A
0x18003dafb  lea     r9, [rbp+210h+var_220]
0x18003daff  lea     r8, [rsp+310h+var_2D0]
0x18003db04  lea     rdx, [rbp+210h+var_268]
0x18003db08  mov     rcx, r13
0x18003db0b  call    ??$emplace@AEAU_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@@?$_Tree@V?$_Tmap_traits@U_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@ULuidLess@34@V?$allocator@U?$pair@$$CBU_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@@std@@@std@@_N@1@AEAU_LUID@@$$QEAVDXCoreAdapterHardwareIdParts@Device@WaaS2@@@Z; std::_Tree<std::_Tmap_traits<_LUID,WaaS2::Device::DXCoreAdapterHardwareIdParts,WaaS2::Device::LuidLess,std::allocator<std::pair<_LUID const,WaaS2::Device::DXCoreAdapterHardwareIdParts>>,0>>::emplace<_LUID &,WaaS2::Device::DXCoreAdapterHardwareIdParts>(_LUID &,WaaS2::Device::DXCoreAdapterHardwareIdParts &&)
0x18003db10  nop
0x18003db11  lea     rcx, [rbp+210h+var_220]; this
0x18003db15  call    ??1DetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::~DetectDXCoreAdapterHardwareIdParts(void)
0x18003db1a  lea     r8, [rsp+310h+var_2D0]
0x18003db1f  lea     rdx, [rbp+210h+var_258]
0x18003db23  lea     rcx, [rsp+310h+var_2B0]
0x18003db28  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_LUID@@ULuidLess@Device@WaaS2@@V?$allocator@U_LUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_LUID@@@std@@@std@@@std@@_N@1@AEBU_LUID@@@Z; std::_Tree<std::_Tset_traits<_LUID,WaaS2::Device::LuidLess,std::allocator<_LUID>,0>>::insert<0,0>(_LUID const &)
0x18003db2d  cmp     byte ptr [rax+8], 0
0x18003db31  jz      short loc_18003DB5E
0x18003db33  mov     rdx, qword ptr [rsp+310h+var_2A0+8]
0x18003db38  cmp     rdx, [rbp+210h+var_290]
0x18003db3c  jz      short loc_18003DB4E
0x18003db3e  mov     rax, [rsp+310h+var_2D0]
0x18003db43  mov     [rdx], rax
0x18003db46  add     qword ptr [rsp+310h+var_2A0+8], 8
0x18003db4c  jmp     short loc_18003DB5E
0x18003db4e  lea     r8, [rsp+310h+var_2D0]
0x18003db53  lea     rcx, [rsp+310h+var_2A0]
0x18003db58  call    ??$_Emplace_reallocate@AEBU_LUID@@@?$vector@U_LUID@@V?$allocator@U_LUID@@@std@@@std@@AEAAPEAU_LUID@@QEAU2@AEBU2@@Z; std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(_LUID * const,_LUID const &)
0x18003db5d  nop
0x18003db5e  jmp     loc_18003DA0A
0x18003db63  cmp     rbx, [rax+10h]
0x18003db67  jnz     short loc_18003DB76
0x18003db69  mov     rbx, rax
0x18003db6c  mov     rax, [rax+8]
0x18003db70  cmp     [rax+19h], r14b
0x18003db74  jz      short loc_18003DB63
0x18003db76  mov     rbx, rax
0x18003db79  jmp     loc_18003D882
0x18003db7e  mov     rbx, rcx
0x18003db81  mov     rcx, [rcx]
0x18003db84  cmp     [rcx+19h], r14b
0x18003db88  jnz     loc_18003D882
0x18003db8e  mov     rbx, rcx
0x18003db91  mov     rax, [rcx]
0x18003db94  mov     rcx, rax
0x18003db97  cmp     [rax+19h], r14b
0x18003db9b  jz      short loc_18003DB8E
0x18003db9d  jmp     loc_18003D882
0x18003dba2  mov     [rbp+210h+var_280], r14
  ... truncated ...
```
