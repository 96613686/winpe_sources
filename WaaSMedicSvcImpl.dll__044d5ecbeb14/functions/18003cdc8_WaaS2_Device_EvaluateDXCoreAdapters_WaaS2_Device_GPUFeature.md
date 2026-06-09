# WaaS2::Device::EvaluateDXCoreAdapters_WaaS2::Device::GPUFeature_

- ea: `0x18003cdc8`
- end: `0x18003d70e`
- name: `WaaS2::Device::EvaluateDXCoreAdapters_WaaS2::Device::GPUFeature_`
- size: `2374`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004e1a0`

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
- `0x18003cdc8`
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

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003d6dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003d6dc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003ce29`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003ce29`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18003ce0e`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18003ce0e`

## string_xrefs

- `0x18003ce3d`: `DXCoreCreateAdapterFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall WaaS2::Device::EvaluateDXCoreAdapters_WaaS2::Device::GPUFeature_(
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
    goto LABEL_149;
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
    goto LABEL_149;
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
      goto LABEL_28;
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
        if ( (*(unsigned __int8 (__fastcall **)(struct IDXCoreAdapter *, __int64 *))(*(_QWORD *)v69 + 32LL))(
               v69,
               DXCORE_ADAPTER_ATTRIBUTE_D3D12_GRAPHICS) )
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
                goto LABEL_25;
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
                goto LABEL_45;
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
LABEL_45:
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
                goto LABEL_25;
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
LABEL_25:
      if ( v69 )
        (*(void (__fastcall **)(struct IDXCoreAdapter *))(*(_QWORD *)v69 + 16LL))(v69);
    }
LABEL_28:
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
    goto LABEL_98;
  v31 = (const wchar_t *)(v30 + 65);
  do
  {
    if ( *((_QWORD *)v31 + 3) <= 7u )
      v32 = v31;
    else
      v32 = *(const wchar_t **)v31;
    if ( *((_QWORD *)v31 + 2) == 1 && !wmemcmp(v32, L"1", 1u) )
      goto LABEL_96;
    *(_QWORD *)v71 = *((_QWORD *)&v75 + 1);
    v33 = (_QWORD *)v75;
    if ( (_QWORD)v75 == *((_QWORD *)&v75 + 1) )
      goto LABEL_96;
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
        goto LABEL_81;
      v37 = v36 + 5;
      if ( (unsigned __int8)WaaS2::Device::DXCoreAdapterHardwareIdParts::MeetsCriteria<WaaS2::Device::NPUFeature>(
                              v36 + 5,
                              v30) )
        break;
LABEL_80:
      v34 = (__int64 **)v72;
LABEL_81:
      if ( ++v33 == *(_QWORD **)v71 )
        goto LABEL_96;
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
          goto LABEL_80;
      }
    }
    v41 = v30[72];
    v42 = v30[73];
    while ( v41 != v42 )
    {
      if ( (unsigned __int8)WaaS2::Device::DXCoreAdapterHardwareIdParts::MeetsCriteria<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>(
                              v37,
                              v41) )
        goto LABEL_80;
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
LABEL_96:
    v30 += 75;
    v31 += 300;
  }
  while ( v30 != v70 );
  v29 = (_QWORD *)v78[0];
LABEL_98:
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
      v50 = WaaS2::Device::DXCoreAdapterHardwareIdParts::LogDebugInfo(v48 + 5, v48, L"GPU");
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
LABEL_149:
  FreeLibrary(v8);
  return v10;
}

```

## disassembly

```asm
0x18003cdc8  mov     [rsp-8+arg_10], rbx
0x18003cdcd  push    rbp
0x18003cdce  push    rsi
0x18003cdcf  push    rdi
0x18003cdd0  push    r12
0x18003cdd2  push    r13
0x18003cdd4  push    r14
0x18003cdd6  push    r15
0x18003cdd8  lea     rbp, [rsp-1E0h]
0x18003cde0  sub     rsp, 2E0h
0x18003cde7  mov     rax, cs:__security_cookie
0x18003cdee  xor     rax, rsp
0x18003cdf1  mov     [rbp+210h+var_40], rax
0x18003cdf8  mov     [rsp+310h+var_2C0], r9
0x18003cdfd  mov     rsi, r8
0x18003ce00  mov     [rbp+210h+var_288], rdx
0x18003ce04  mov     r14, rcx
0x18003ce07  lea     rcx, Contract; "ext-ms-win-dxcore-l1-1-0"
0x18003ce0e  call    cs:__imp_IsApiSetImplemented
0x18003ce14  xor     r15d, r15d
0x18003ce17  test    eax, eax
0x18003ce19  jnz     short loc_18003CE22
0x18003ce1b  xor     eax, eax
0x18003ce1d  jmp     loc_18003D6E4
0x18003ce22  lea     rcx, Contract; "ext-ms-win-dxcore-l1-1-0"
0x18003ce29  call    cs:__imp_LoadLibraryA
0x18003ce2f  mov     rdi, rax
0x18003ce32  mov     [rbp+210h+var_270], rax
0x18003ce36  test    rax, rax
0x18003ce39  jnz     short loc_18003CE3D
0x18003ce3b  jmp     short loc_18003CE1B
0x18003ce3d  lea     rdx, aDxcorecreatead; "DXCoreCreateAdapterFactory"
0x18003ce44  mov     rcx, rdi; hModule
0x18003ce47  call    cs:__imp_GetProcAddress
0x18003ce4d  test    rax, rax
0x18003ce50  jnz     short loc_18003CE5A
0x18003ce52  mov     ebx, r15d
0x18003ce55  jmp     loc_18003D6D9
0x18003ce5a  mov     [rsp+310h+var_2B8], r15
0x18003ce5f  lea     rdx, [rsp+310h+var_2B8]
0x18003ce64  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18003ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce70  mov     ebx, eax
0x18003ce72  test    eax, eax
0x18003ce74  jns     short loc_18003CEAE
0x18003ce76  mov     rcx, [rbp+218h]; this
0x18003ce7d  mov     r9d, eax; char *
0x18003ce80  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003ce87  mov     edx, 0ABAh; void *
0x18003ce8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ce91  nop
0x18003ce92  mov     rcx, [rsp+310h+var_2B8]
0x18003ce97  test    rcx, rcx
0x18003ce9a  jz      short loc_18003CEA9
0x18003ce9c  mov     rax, [rcx]
0x18003ce9f  mov     rax, [rax+10h]
0x18003cea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cea8  nop
0x18003cea9  jmp     loc_18003D6D9
0x18003ceae  xorps   xmm0, xmm0
0x18003ceb1  movups  [rbp+210h+var_248], xmm0
0x18003ceb5  mov     [rbp+210h+var_238], r15
0x18003ceb9  mov     [rbp+210h+var_230], r15
0x18003cebd  mov     r8d, 8
0x18003cec3  lea     rdx, aHardware; "Hardware"
0x18003ceca  lea     rcx, [rbp+210h+var_248]
0x18003cece  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003ced3  lea     rdx, [rbp+210h+var_248]
0x18003ced7  mov     rcx, r14
0x18003ceda  call    ?ContainsSegment@URIContext@Device@WaaS2@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaaS2::Device::URIContext::ContainsSegment(std::wstring const &)
0x18003cedf  mov     r15b, al
0x18003cee2  lea     rcx, [rbp+210h+var_248]; void *
0x18003cee6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ceeb  xorps   xmm0, xmm0
0x18003ceee  movdqu  [rsp+310h+var_2A0], xmm0
0x18003cef4  xor     r14d, r14d
0x18003cef7  mov     [rbp+210h+var_290], r14
0x18003cefb  mov     [rsp+310h+var_2B0], r14
0x18003cf00  mov     [rsp+310h+var_2A8], r14
0x18003cf05  lea     ecx, [r14+28h]; Size
0x18003cf09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cf0e  mov     [rax], rax
0x18003cf11  mov     [rax+8], rax
0x18003cf15  mov     [rax+10h], rax
0x18003cf19  mov     word ptr [rax+18h], 101h
0x18003cf1f  mov     [rsp+310h+var_2B0], rax
0x18003cf24  mov     rbx, [rsi]
0x18003cf27  mov     rbx, [rbx]
0x18003cf2a  lea     r12, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003cf31  mov     r13, [rsp+310h+var_2C0]
0x18003cf36  cmp     [rbx+19h], r14b
0x18003cf3a  jnz     loc_18003D277
0x18003cf40  mov     qword ptr [rsp+310h+var_2C8], r14
0x18003cf45  mov     rcx, [rsp+310h+var_2B8]
0x18003cf4a  mov     rax, [rcx]
0x18003cf4d  lea     rdx, [rsp+310h+var_2C8]
0x18003cf52  mov     qword ptr [rsp+310h+var_2F0], rdx; int
0x18003cf57  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18003cf5e  mov     r8, [rbx+20h]
0x18003cf62  mov     edx, 1
0x18003cf67  mov     rax, [rax+18h]
0x18003cf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf70  mov     rcx, [rbp+218h]; this
0x18003cf77  test    eax, eax
0x18003cf79  jns     short loc_18003CF91
0x18003cf7b  mov     r9d, eax; char *
0x18003cf7e  mov     r8, r12; unsigned int
0x18003cf81  mov     edx, 0AC9h; void *
0x18003cf86  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003cf8b  nop
0x18003cf8c  jmp     loc_18003D104
0x18003cf91  mov     rcx, qword ptr [rsp+310h+var_2C8]
0x18003cf96  mov     rax, [rcx]
0x18003cf99  mov     rax, [rax+20h]
0x18003cf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfa2  mov     r14d, eax
0x18003cfa5  xor     esi, esi
0x18003cfa7  test    eax, eax
0x18003cfa9  jz      loc_18003D101
0x18003cfaf  mov     [rsp+310h+var_2D8], 0
0x18003cfb8  mov     rcx, qword ptr [rsp+310h+var_2C8]
0x18003cfbd  mov     rdx, [rcx]
0x18003cfc0  mov     rax, [rdx+18h]
0x18003cfc4  mov     [rsp+310h+var_2D8], 0
0x18003cfcd  lea     r9, [rsp+310h+var_2D8]
0x18003cfd2  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18003cfd9  mov     edx, esi
0x18003cfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfe0  mov     rcx, [rbp+218h]; this
0x18003cfe7  test    eax, eax
0x18003cfe9  jns     short loc_18003D001
0x18003cfeb  mov     r9d, eax; char *
0x18003cfee  mov     r8, r12; unsigned int
0x18003cff1  mov     edx, 0AD3h; void *
0x18003cff6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003cffb  nop
0x18003cffc  jmp     loc_18003D0DF
0x18003d001  mov     rcx, [rsp+310h+var_2D8]
0x18003d006  mov     rax, [rcx]
0x18003d009  lea     rdx, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GRAPHICS
0x18003d010  mov     rax, [rax+20h]
0x18003d014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d019  test    al, al
0x18003d01b  jnz     short loc_18003D022
0x18003d01d  jmp     loc_18003D0DF
0x18003d022  test    r15b, r15b
0x18003d025  jz      short loc_18003D084
0x18003d027  mov     rcx, [rsp+310h+var_2D8]
0x18003d02c  mov     rax, [rcx]
0x18003d02f  mov     edx, 0Bh
0x18003d034  mov     rax, [rax+28h]
0x18003d038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d03d  test    al, al
0x18003d03f  jz      short loc_18003D084
0x18003d041  mov     [rsp+310h+var_2E0], 0
0x18003d046  mov     rcx, [rsp+310h+var_2D8]
0x18003d04b  mov     rax, [rcx]
0x18003d04e  lea     r9, [rsp+310h+var_2E0]
0x18003d053  mov     edx, 0Bh
0x18003d058  lea     r8d, [rdx-0Ah]
0x18003d05c  mov     rax, [rax+30h]
0x18003d060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d065  mov     rcx, [rbp+218h]; this
0x18003d06c  test    eax, eax
0x18003d06e  jns     loc_18003D132
0x18003d074  mov     r9d, eax; char *
0x18003d077  mov     r8, r12; unsigned int
0x18003d07a  mov     edx, 0AE0h; void *
0x18003d07f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d084  mov     [rsp+310h+var_2D0], 0
0x18003d08d  mov     rcx, [rsp+310h+var_2D8]
0x18003d092  mov     rax, [rcx]
0x18003d095  xor     edx, edx
0x18003d097  mov     rax, [rax+28h]
0x18003d09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0a0  test    al, al
0x18003d0a2  jz      short loc_18003D0DF
0x18003d0a4  mov     rcx, [rsp+310h+var_2D8]
0x18003d0a9  mov     rax, [rcx]
0x18003d0ac  lea     r9, [rsp+310h+var_2D0]
0x18003d0b1  xor     edx, edx
0x18003d0b3  lea     r8d, [rdx+8]
0x18003d0b7  mov     rax, [rax+30h]
0x18003d0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0c0  mov     rcx, [rbp+218h]; this
0x18003d0c7  xor     r10d, r10d
0x18003d0ca  test    eax, eax
0x18003d0cc  jns     short loc_18003D13F
0x18003d0ce  mov     r9d, eax; char *
0x18003d0d1  mov     r8, r12; unsigned int
0x18003d0d4  mov     edx, 0AEBh; void *
0x18003d0d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d0de  nop
0x18003d0df  mov     rcx, [rsp+310h+var_2D8]
0x18003d0e4  test    rcx, rcx
0x18003d0e7  jz      short loc_18003D0F6
0x18003d0e9  mov     rax, [rcx]
0x18003d0ec  mov     rax, [rax+10h]
0x18003d0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0f5  nop
0x18003d0f6  inc     esi
0x18003d0f8  cmp     esi, r14d
0x18003d0fb  jb      loc_18003CFAF
0x18003d101  xor     r14d, r14d
0x18003d104  mov     rcx, qword ptr [rsp+310h+var_2C8]
0x18003d109  test    rcx, rcx
0x18003d10c  jz      short loc_18003D11B
0x18003d10e  mov     rax, [rcx]
0x18003d111  mov     rax, [rax+10h]
0x18003d115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d11a  nop
0x18003d11b  mov     rcx, [rbx+10h]
0x18003d11f  cmp     [rcx+19h], r14b
0x18003d123  jz      loc_18003D253
0x18003d129  mov     rax, [rbx+8]
0x18003d12d  jmp     loc_18003D245
0x18003d132  cmp     [rsp+310h+var_2E0], 0
0x18003d137  jnz     loc_18003D084
0x18003d13d  jmp     short loc_18003D0DF
0x18003d13f  mov     r9, [r13+0]
0x18003d143  mov     rcx, [r9+8]
0x18003d147  mov     rdx, r9
0x18003d14a  mov     rax, [rsp+310h+var_2D0]
0x18003d14f  mov     r8d, dword ptr [rsp+310h+var_2D0+4]
0x18003d154  jmp     short loc_18003D16F
0x18003d156  cmp     [rcx+24h], r8d
0x18003d15a  jl      short loc_18003D16B
0x18003d15c  jnz     short loc_18003D163
0x18003d15e  cmp     [rcx+20h], eax
0x18003d161  jb      short loc_18003D16B
0x18003d163  mov     rdx, rcx
0x18003d166  mov     rcx, [rcx]
0x18003d169  jmp     short loc_18003D16F
0x18003d16b  mov     rcx, [rcx+10h]
0x18003d16f  cmp     [rcx+19h], r10b
0x18003d173  jz      short loc_18003D156
0x18003d175  cmp     [rdx+19h], r10b
0x18003d179  jnz     short loc_18003D18D
0x18003d17b  cmp     r8d, [rdx+24h]
0x18003d17f  jl      short loc_18003D18D
0x18003d181  jnz     short loc_18003D188
0x18003d183  cmp     eax, [rdx+20h]
0x18003d186  jb      short loc_18003D18D
0x18003d188  cmp     rdx, r9
0x18003d18b  jnz     short loc_18003D1EF
0x18003d18d  lea     rcx, [rbp+210h+var_220]; this
0x18003d191  call    ??0DetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::DetectDXCoreAdapterHardwareIdParts(void)
0x18003d196  nop
0x18003d197  mov     rdx, [rsp+310h+var_2D8]; struct IDXCoreAdapter *
0x18003d19c  lea     rcx, [rbp+210h+var_220]; this
0x18003d1a0  call    ?Init@DXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAAJPEAUIDXCoreAdapter@@@Z; WaaS2::Device::DXCoreAdapterHardwareIdParts::Init(IDXCoreAdapter *)
0x18003d1a5  mov     rcx, [rbp+218h]; this
0x18003d1ac  test    eax, eax
0x18003d1ae  jns     short loc_18003D1D0
0x18003d1b0  mov     r9d, eax; char *
0x18003d1b3  mov     r8, r12; unsigned int
0x18003d1b6  mov     edx, 0AF3h; void *
0x18003d1bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d1c0  nop
0x18003d1c1  lea     rcx, [rbp+210h+var_220]; this
0x18003d1c5  call    ??1DetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::~DetectDXCoreAdapterHardwareIdParts(void)
0x18003d1ca  nop
0x18003d1cb  jmp     loc_18003D0DF
0x18003d1d0  lea     r9, [rbp+210h+var_220]
0x18003d1d4  lea     r8, [rsp+310h+var_2D0]
0x18003d1d9  lea     rdx, [rbp+210h+var_268]
0x18003d1dd  mov     rcx, r13
0x18003d1e0  call    ??$emplace@AEAU_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@@?$_Tree@V?$_Tmap_traits@U_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@ULuidLess@34@V?$allocator@U?$pair@$$CBU_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_LUID@@VDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@@std@@@std@@_N@1@AEAU_LUID@@$$QEAVDXCoreAdapterHardwareIdParts@Device@WaaS2@@@Z; std::_Tree<std::_Tmap_traits<_LUID,WaaS2::Device::DXCoreAdapterHardwareIdParts,WaaS2::Device::LuidLess,std::allocator<std::pair<_LUID const,WaaS2::Device::DXCoreAdapterHardwareIdParts>>,0>>::emplace<_LUID &,WaaS2::Device::DXCoreAdapterHardwareIdParts>(_LUID &,WaaS2::Device::DXCoreAdapterHardwareIdParts &&)
0x18003d1e5  nop
0x18003d1e6  lea     rcx, [rbp+210h+var_220]; this
0x18003d1ea  call    ??1DetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DetectDXCoreAdapterHardwareIdParts::~DetectDXCoreAdapterHardwareIdParts(void)
0x18003d1ef  lea     r8, [rsp+310h+var_2D0]
0x18003d1f4  lea     rdx, [rbp+210h+var_258]
0x18003d1f8  lea     rcx, [rsp+310h+var_2B0]
0x18003d1fd  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_LUID@@ULuidLess@Device@WaaS2@@V?$allocator@U_LUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_LUID@@@std@@@std@@@std@@_N@1@AEBU_LUID@@@Z; std::_Tree<std::_Tset_traits<_LUID,WaaS2::Device::LuidLess,std::allocator<_LUID>,0>>::insert<0,0>(_LUID const &)
0x18003d202  cmp     byte ptr [rax+8], 0
0x18003d206  jz      short loc_18003D233
0x18003d208  mov     rdx, qword ptr [rsp+310h+var_2A0+8]
0x18003d20d  cmp     rdx, [rbp+210h+var_290]
0x18003d211  jz      short loc_18003D223
0x18003d213  mov     rax, [rsp+310h+var_2D0]
0x18003d218  mov     [rdx], rax
0x18003d21b  add     qword ptr [rsp+310h+var_2A0+8], 8
0x18003d221  jmp     short loc_18003D233
0x18003d223  lea     r8, [rsp+310h+var_2D0]
0x18003d228  lea     rcx, [rsp+310h+var_2A0]
0x18003d22d  call    ??$_Emplace_reallocate@AEBU_LUID@@@?$vector@U_LUID@@V?$allocator@U_LUID@@@std@@@std@@AEAAPEAU_LUID@@QEAU2@AEBU2@@Z; std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(_LUID * const,_LUID const &)
0x18003d232  nop
0x18003d233  jmp     loc_18003D0DF
0x18003d238  cmp     rbx, [rax+10h]
0x18003d23c  jnz     short loc_18003D24B
0x18003d23e  mov     rbx, rax
0x18003d241  mov     rax, [rax+8]
0x18003d245  cmp     [rax+19h], r14b
0x18003d249  jz      short loc_18003D238
0x18003d24b  mov     rbx, rax
0x18003d24e  jmp     loc_18003CF36
0x18003d253  mov     rbx, rcx
0x18003d256  mov     rcx, [rcx]
0x18003d259  cmp     [rcx+19h], r14b
  ... truncated ...
```
