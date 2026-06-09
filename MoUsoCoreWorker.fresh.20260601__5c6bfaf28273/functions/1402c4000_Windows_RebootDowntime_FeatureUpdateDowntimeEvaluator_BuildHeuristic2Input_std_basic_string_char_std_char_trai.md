# Windows::RebootDowntime::FeatureUpdateDowntimeEvaluator::BuildHeuristic2Input(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1402c4000`
- end: `0x1402c4f43`
- name: `?BuildHeuristic2Input@FeatureUpdateDowntimeEvaluator@RebootDowntime@Windows@@QEAA?AV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@NU?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `3907`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1402c3abc`

## callees

- `0x14002cacc`
- `0x14003ff28`
- `0x1400413a8`
- `0x140043284`
- `0x140043814`
- `0x14004519c`
- `0x140045404`
- `0x1400c75e4`
- `0x1402b63c8`
- `0x1402b6460`
- `0x1402bd2fc`
- `0x1402c4000`
- `0x1402c5130`
- `0x1402c5258`
- `0x1402c54b0`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402c4068`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402c4068`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4d72`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4d82`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4d92`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4da2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4db2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4dc2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4dd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4de2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4df2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e02`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e12`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e22`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e32`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e42`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e52`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e62`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4d72`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4d82`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4d92`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4da2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4db2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4dc2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4dd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4de2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4df2`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e02`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e12`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e22`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e32`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e42`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e52`
- `OLEAUT32!__imp_SysFreeString` at `0x1402c4e62`

## string_xrefs

- `0x1402c47e3`: `NumComAV1`
- `0x1402c4ec8`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\FeatureUpdateDowntimeEvaluator.cpp`
- `0x1402c4f0d`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\FeatureUpdateDowntimeEvaluator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
_QWORD *__fastcall Windows::RebootDowntime::FeatureUpdateDowntimeEvaluator::BuildHeuristic2Input(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  HRESULT v6; // eax
  __int64 v7; // rax
  __int64 InputForKey; // rax
  __int64 v9; // rbx
  BSTR v10; // rcx
  __int64 v11; // rdx
  BSTR v12; // rcx
  __int64 v13; // rdx
  BSTR v14; // rcx
  __int64 v15; // rdx
  BSTR v16; // rcx
  __int64 v17; // rdx
  BSTR v18; // rcx
  __int64 v19; // rdx
  BSTR v20; // rcx
  __int64 v21; // rdx
  BSTR v22; // rcx
  __int64 v23; // rdx
  BSTR v24; // rcx
  __int64 v25; // rdx
  BSTR v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rbx
  float v39; // xmm0_4
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rbx
  float v44; // xmm0_4
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // ebx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rax
  int v52; // ebx
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rbx
  float v57; // xmm0_4
  __int64 v58; // rdx
  __int64 v59; // rdx
  int v60; // eax
  _QWORD *v61; // rax
  unsigned int i; // ebx
  double v63; // xmm6_8
  __int64 v64; // rdx
  __int64 v65; // r8
  int ppv; // [rsp+28h] [rbp-E0h]
  int v68; // [rsp+48h] [rbp-C0h] BYREF
  float v69; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v70; // [rsp+50h] [rbp-B8h] BYREF
  float v71[4]; // [rsp+58h] [rbp-B0h] BYREF
  BSTR v72; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+70h] [rbp-98h]
  __int64 v74; // [rsp+78h] [rbp-90h]
  _QWORD v75[2]; // [rsp+80h] [rbp-88h] BYREF
  char v76; // [rsp+90h] [rbp-78h]
  _OWORD v77[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v78; // [rsp+B8h] [rbp-50h]
  __int64 v79; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v80; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-28h]
  unsigned int v82; // [rsp+E8h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+F0h] [rbp-18h] BYREF
  BSTR v84; // [rsp+F8h] [rbp-10h] BYREF
  BSTR v85; // [rsp+100h] [rbp-8h] BYREF
  BSTR v86; // [rsp+108h] [rbp+0h] BYREF
  BSTR v87; // [rsp+110h] [rbp+8h] BYREF
  BSTR v88; // [rsp+118h] [rbp+10h] BYREF
  BSTR v89; // [rsp+120h] [rbp+18h] BYREF
  BSTR v90; // [rsp+128h] [rbp+20h] BYREF
  BSTR v91; // [rsp+130h] [rbp+28h] BYREF
  BSTR v92; // [rsp+138h] [rbp+30h] BYREF
  BSTR v93; // [rsp+140h] [rbp+38h] BYREF
  BSTR v94; // [rsp+148h] [rbp+40h] BYREF
  BSTR v95; // [rsp+150h] [rbp+48h] BYREF
  BSTR v96; // [rsp+158h] [rbp+50h] BYREF
  BSTR v97; // [rsp+160h] [rbp+58h] BYREF
  BSTR v98; // [rsp+168h] [rbp+60h] BYREF
  LPVOID v99; // [rsp+170h] [rbp+68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v78 = a2;
  LODWORD(v74) = 0;
  v99 = 0;
  v6 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v99);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\FeatureUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v80 = 0;
  v81 = 0;
  v7 = -1;
  do
    ++v7;
  while ( Windows::RebootDowntime::InputBuilder::rebootDowntimeSignalKey[v7] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::rebootDowntimeSignalKey;
  v73 = v7;
  InputForKey = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(InputForKey + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(InputForKey + 8) != 1 )
    std::_Throw_bad_variant_access();
  v9 = *(_QWORD *)InputForKey;
  v98 = 0;
  wil::make_bstr(&v98, L"NeoLCUpoV1");
  v69 = FLOAT_1_0;
  LODWORD(v70) = 0;
  LOBYTE(v68) = v9 == 1010;
  v10 = v98;
  *(_QWORD *)v71 = v98;
  v11 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v70,
      &v69);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 1010);
    *(_QWORD *)v11 = v10;
    *(_DWORD *)(v11 + 12) = 0;
    *(float *)(v11 + 16) = FLOAT_1_0;
    *(_DWORD *)(v11 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v97 = 0;
  wil::make_bstr(&v97, L"NeoLCUV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 1020;
  v12 = v97;
  *(_QWORD *)v71 = v97;
  v13 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 1020);
    *(_QWORD *)v13 = v12;
    *(_DWORD *)(v13 + 12) = 0;
    *(float *)(v13 + 16) = FLOAT_1_0;
    *(_DWORD *)(v13 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v96 = 0;
  wil::make_bstr(&v96, L"NeoWCOSV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 2010;
  v14 = v96;
  *(_QWORD *)v71 = v96;
  v15 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 2010);
    *(_QWORD *)v15 = v14;
    *(_DWORD *)(v15 + 12) = 0;
    *(float *)(v15 + 16) = FLOAT_1_0;
    *(_DWORD *)(v15 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v95 = 0;
  wil::make_bstr(&v95, L"NeoFUldsV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10010;
  v16 = v95;
  *(_QWORD *)v71 = v95;
  v17 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10010);
    *(_QWORD *)v17 = v16;
    *(_DWORD *)(v17 + 12) = 0;
    *(float *)(v17 + 16) = FLOAT_1_0;
    *(_DWORD *)(v17 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v94 = 0;
  wil::make_bstr(&v94, L"NeoFUoffV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10020;
  v18 = v94;
  *(_QWORD *)v71 = v94;
  v19 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10020);
    *(_QWORD *)v19 = v18;
    *(_DWORD *)(v19 + 12) = 0;
    *(float *)(v19 + 16) = FLOAT_1_0;
    *(_DWORD *)(v19 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v93 = 0;
  wil::make_bstr(&v93, L"NeoFUV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10030;
  v20 = v93;
  *(_QWORD *)v71 = v93;
  v21 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10030);
    *(_QWORD *)v21 = v20;
    *(_DWORD *)(v21 + 12) = 0;
    *(float *)(v21 + 16) = FLOAT_1_0;
    *(_DWORD *)(v21 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v92 = 0;
  wil::make_bstr(&v92, L"NeoFUssbV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10040;
  v22 = v92;
  *(_QWORD *)v71 = v92;
  v23 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10040);
    *(_QWORD *)v23 = v22;
    *(_DWORD *)(v23 + 12) = 0;
    *(float *)(v23 + 16) = FLOAT_1_0;
    *(_DWORD *)(v23 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v91 = 0;
  wil::make_bstr(&v91, L"NeoFUsfbV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10050;
  v24 = v91;
  *(_QWORD *)v71 = v91;
  v25 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10050);
    *(_QWORD *)v25 = v24;
    *(_DWORD *)(v25 + 12) = 0;
    *(float *)(v25 + 16) = FLOAT_1_0;
    *(_DWORD *)(v25 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v90 = 0;
  wil::make_bstr(&v90, L"NeoFUsosV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10060;
  v26 = v90;
  *(_QWORD *)v71 = v90;
  v27 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10060);
    *(_QWORD *)v27 = v26;
    *(_DWORD *)(v27 + 12) = 0;
    *(float *)(v27 + 16) = FLOAT_1_0;
    *(_DWORD *)(v27 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v28 = -1;
  do
    ++v28;
  while ( Windows::RebootDowntime::InputBuilder::didNumWin32ChangeKey[v28] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::didNumWin32ChangeKey;
  v73 = v28;
  v29 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v29 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v29 + 8) )
    std::_Throw_bad_variant_access();
  v30 = *(_DWORD *)v29;
  v89 = 0;
  wil::make_bstr(&v89, L"W32AChV1");
  LODWORD(v70) = 1065353216;
  v69 = 0.0;
  v71[0] = (float)v30;
  v72 = v89;
  v31 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      v71,
      &v69,
      &v70);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v89;
    *(float *)(v31 + 8) = (float)v30;
    *(_DWORD *)(v31 + 12) = 0;
    *(_QWORD *)(v31 + 16) = 1065353216;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v32 = -1;
  do
    ++v32;
  while ( Windows::RebootDowntime::InputBuilder::didTopAppsChangeVersionKey[v32] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::didTopAppsChangeVersionKey;
  v73 = v32;
  v33 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v33 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v33 + 8) )
    std::_Throw_bad_variant_access();
  v34 = *(_DWORD *)v33;
  v88 = 0;
  wil::make_bstr(&v88, L"OthAChV1");
  v71[0] = 1.0;
  LODWORD(v70) = 0;
  v69 = (float)v34;
  v72 = v88;
  v35 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v88;
    *(float *)(v35 + 8) = (float)v34;
    *(_DWORD *)(v35 + 12) = 0;
    *(_QWORD *)(v35 + 16) = 1065353216;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v36 = -1;
  do
    ++v36;
  while ( Windows::RebootDowntime::InputBuilder::numTopAppsKey[v36] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numTopAppsKey;
  v73 = v36;
  v37 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v37 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v37 + 8) != 1 )
    std::_Throw_bad_variant_access();
  v38 = *(_QWORD *)v37;
  v87 = 0;
  wil::make_bstr(&v87, L"NumComAV1");
  v71[0] = 5.0;
  LODWORD(v70) = 0;
  if ( v38 < 0 )
    v39 = (float)(v38 & 1 | (unsigned int)((unsigned __int64)v38 >> 1))
        + (float)(v38 & 1 | (unsigned int)((unsigned __int64)v38 >> 1));
  else
    v39 = (float)(int)v38;
  v69 = v39;
  v72 = v87;
  v40 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v87;
    *(float *)(v40 + 8) = v39;
    *(_DWORD *)(v40 + 12) = 0;
    *(_QWORD *)(v40 + 16) = 1084227584;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v41 = -1;
  do
    ++v41;
  while ( Windows::RebootDowntime::InputBuilder::numWin32AppsKey[v41] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numWin32AppsKey;
  v73 = v41;
  v42 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v42 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v42 + 8) != 1 )
    std::_Throw_bad_variant_access();
  v43 = *(_QWORD *)v42;
  v86 = 0;
  wil::make_bstr(&v86, L"NumW32AV1");
  v71[0] = 200.0;
  LODWORD(v70) = 0;
  if ( v43 < 0 )
    v44 = (float)(v43 & 1 | (unsigned int)((unsigned __int64)v43 >> 1))
        + (float)(v43 & 1 | (unsigned int)((unsigned __int64)v43 >> 1));
  else
    v44 = (float)(int)v43;
  v69 = v44;
  v72 = v86;
  v45 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v86;
    *(float *)(v45 + 8) = v44;
    *(_DWORD *)(v45 + 12) = 0;
    *(_QWORD *)(v45 + 16) = 1128792064;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v46 = -1;
  do
    ++v46;
  while ( Windows::RebootDowntime::InputBuilder::numInstalledFodKey[v46] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numInstalledFodKey;
  v73 = v46;
  v47 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v47 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v47 + 8) )
    std::_Throw_bad_variant_access();
  v48 = *(_DWORD *)v47;
  v85 = 0;
  wil::make_bstr(&v85, L"NumFODV1");
  v71[0] = 50.0;
  LODWORD(v70) = 0;
  v69 = (float)v48;
  v72 = v85;
  v49 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v85;
    *(float *)(v49 + 8) = (float)v48;
    *(_DWORD *)(v49 + 12) = 0;
    *(_QWORD *)(v49 + 16) = 1112014848;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v50 = -1;
  do
    ++v50;
  while ( Windows::RebootDowntime::InputBuilder::numUserProfilesKey[v50] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numUserProfilesKey;
  v73 = v50;
  v51 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v51 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v51 + 8) )
    std::_Throw_bad_variant_access();
  v52 = *(_DWORD *)v51;
  v84 = 0;
  wil::make_bstr(&v84, L"NumUsrPrV1");
  v71[0] = 10.0;
  LODWORD(v70) = 0;
  v69 = (float)v52;
  v72 = v84;
  v53 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v84;
    *(float *)(v53 + 8) = (float)v52;
    *(_DWORD *)(v53 + 12) = 0;
    *(_QWORD *)(v53 + 16) = 1092616192;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v54 = -1;
  do
    ++v54;
  while ( Windows::RebootDowntime::InputBuilder::fuSizeKey[v54] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::fuSizeKey;
  v73 = v54;
  v55 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v55 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v55 + 8) != 1 )
    std::_Throw_bad_variant_access();
  v56 = *(_QWORD *)v55;
  bstrString = 0;
  wil::make_bstr(&bstrString, L"SzFUV1");
  v71[0] = 8000000000.0;
  LODWORD(v70) = 0;
  if ( v56 < 0 )
    v57 = (float)(v56 & 1 | (unsigned int)((unsigned __int64)v56 >> 1))
        + (float)(v56 & 1 | (unsigned int)((unsigned __int64)v56 >> 1));
  else
    v57 = (float)(int)v56;
  v69 = v57;
  v72 = bstrString;
  v58 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
    v59 = *((_QWORD *)&v80 + 1);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = bstrString;
    *(float *)(v58 + 8) = v57;
    *(_DWORD *)(v58 + 12) = 0;
    *(_QWORD *)(v58 + 16) = 1341025064;
    v59 = *((_QWORD *)&v80 + 1) + 24LL;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v82 = 0;
  v79 = 0;
  if ( a3[3] > 0xFu )
    a3 = (_QWORD *)*a3;
  v60 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v99 + 40LL))(
          v99,
          0xAAAAAAAAAAAAAAABuLL * ((v59 - (__int64)v80) >> 3),
          v80,
          L"FU202409");
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\FeatureUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v60,
      (int)a3);
  v75[0] = &v79;
  v75[1] = &v82;
  v76 = 1;
  memset(a2, 0, 0x40u);
  *(_DWORD *)a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v61 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(56);
  *v61 = v61;
  v61[1] = v61;
  a2[1] = v61;
  a2[3] = 0;
  a2[4] = 0;
  a2[5] = 0;
  a2[6] = 7;
  a2[7] = 8;
  *(_DWORD *)a2 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,DecisionTable<SystemInterface::Providers::ConditionContext>>>>>>>::_Assign_grow(
    a2 + 3,
    16,
    a2[1]);
  LODWORD(v74) = 1;
  for ( i = 0; i < v82; ++i )
  {
    v63 = *(float *)(v79 + 16LL * i + 8);
    v64 = *(_QWORD *)(v79 + 16LL * i);
    memset(v77, 0, sizeof(v77));
    v65 = -1;
    do
      ++v65;
    while ( *(_WORD *)(v64 + 2 * v65) );
    std::wstring::_Construct<1,wchar_t const *>(v77, v64, v65);
    *(double *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Try_emplace<std::wstring,>(
                             a2,
                             &v72,
                             v77)
              + 48LL) = v63;
    std::wstring::~wstring(v77);
  }
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(v75);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v84 )
    SysFreeString(v84);
  if ( v85 )
    SysFreeString(v85);
  if ( v86 )
    SysFreeString(v86);
  if ( v87 )
    SysFreeString(v87);
  if ( v88 )
    SysFreeString(v88);
  if ( v89 )
    SysFreeString(v89);
  if ( v90 )
    SysFreeString(v90);
  if ( v91 )
    SysFreeString(v91);
  if ( v92 )
    SysFreeString(v92);
  if ( v93 )
    SysFreeString(v93);
  if ( v94 )
    SysFreeString(v94);
  if ( v95 )
    SysFreeString(v95);
  if ( v96 )
    SysFreeString(v96);
  if ( v97 )
    SysFreeString(v97);
  if ( v98 )
    SysFreeString(v98);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v80);
  if ( v99 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v99 + 16LL))(v99);
  return a2;
}

```

## disassembly

```asm
0x1402c4000  mov     rax, rsp
0x1402c4003  mov     [rax+20h], rbx
0x1402c4007  push    rbp
0x1402c4008  push    rsi
0x1402c4009  push    rdi
0x1402c400a  push    r14
0x1402c400c  push    r15
0x1402c400e  lea     rbp, [rax-0C8h]
0x1402c4015  sub     rsp, 1A0h
0x1402c401c  movaps  xmmword ptr [rax-38h], xmm6
0x1402c4020  movaps  xmmword ptr [rax-48h], xmm7
0x1402c4024  mov     rax, cs:__security_cookie
0x1402c402b  xor     rax, rsp
0x1402c402e  mov     [rbp+0C0h+var_50], rax
0x1402c4032  mov     r14, r8
0x1402c4035  mov     rsi, rdx
0x1402c4038  mov     rdi, rcx
0x1402c403b  mov     [rbp+0C0h+var_110], rdx
0x1402c403f  xor     r15d, r15d
0x1402c4042  mov     dword ptr [rsp+1C0h+var_150], r15d
0x1402c4047  mov     [rbp+0C0h+var_58], r15
0x1402c404b  lea     rax, [rbp+0C0h+var_58]
0x1402c404f  mov     [rsp+1C0h+ppv], rax; int
0x1402c4054  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1402c405b  xor     edx, edx; pUnkOuter
0x1402c405d  lea     r8d, [r15+4]; dwClsContext
0x1402c4061  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1402c4068  call    cs:__imp_CoCreateInstance
0x1402c406e  mov     rcx, [rbp+0C8h]; this
0x1402c4075  test    eax, eax
0x1402c4077  js      loc_1402C4EC5
0x1402c407d  xorps   xmm1, xmm1
0x1402c4080  movdqu  [rbp+0C0h+var_F8], xmm1
0x1402c4085  mov     [rbp+0C0h+var_E8], r15
0x1402c4089  mov     rdx, cs:?rebootDowntimeSignalKey@InputBuilder@RebootDowntime@Windows@@2QEB_WEB; wchar_t const * const Windows::RebootDowntime::InputBuilder::rebootDowntimeSignalKey
0x1402c4090  or      rax, 0FFFFFFFFFFFFFFFFh
0x1402c4094  inc     rax
0x1402c4097  cmp     [rdx+rax*2], r15w
0x1402c409c  jnz     short loc_1402C4094
0x1402c409e  mov     [rsp+1C0h+var_160], rdx
0x1402c40a3  mov     [rsp+1C0h+var_158], rax
0x1402c40a8  lea     r8, [rsp+1C0h+var_160]
0x1402c40ad  lea     rdx, [rsp+1C0h+var_148]
0x1402c40b2  mov     rcx, [rdi+8]
0x1402c40b6  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1402c40bb  cmp     [rax+10h], r15b
0x1402c40bf  jz      loc_1402C4EDA
0x1402c40c5  cmp     byte ptr [rax+8], 1
0x1402c40c9  jnz     loc_1402C4EBF
0x1402c40cf  mov     rbx, [rax]
0x1402c40d2  mov     [rbp+0C0h+var_60], r15
0x1402c40d6  lea     rdx, aNeolcupov1; "NeoLCUpoV1"
0x1402c40dd  lea     rcx, [rbp+0C0h+var_60]
0x1402c40e1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c40e6  nop
0x1402c40e7  movss   xmm6, cs:__real@3f800000
0x1402c40ef  movss   [rsp+1C0h+var_17C], xmm6
0x1402c40f5  xorps   xmm7, xmm7
0x1402c40f8  movss   dword ptr [rsp+1C0h+var_178], xmm7
0x1402c40fe  cmp     rbx, 3F2h
0x1402c4105  setz    al
0x1402c4108  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c410c  mov     rcx, [rbp+0C0h+var_60]
0x1402c4110  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c4115  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c4119  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c411d  jz      short loc_1402C4147
0x1402c411f  movzx   eax, al
0x1402c4122  movd    xmm0, eax
0x1402c4126  cvtdq2ps xmm0, xmm0
0x1402c4129  movss   dword ptr [rdx+8], xmm0
0x1402c412e  mov     [rdx], rcx
0x1402c4131  movss   dword ptr [rdx+0Ch], xmm7
0x1402c4136  movss   dword ptr [rdx+10h], xmm6
0x1402c413b  xor     eax, eax
0x1402c413d  mov     [rdx+14h], eax
0x1402c4140  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c4145  jmp     short loc_1402C416E
0x1402c4147  lea     rax, [rsp+1C0h+var_17C]
0x1402c414c  mov     [rsp+1C0h+var_198], rax
0x1402c4151  lea     rax, [rsp+1C0h+var_178]
0x1402c4156  mov     [rsp+1C0h+ppv], rax
0x1402c415b  lea     r9, [rsp+1C0h+var_180]
0x1402c4160  lea     r8, [rsp+1C0h+var_170]
0x1402c4165  lea     rcx, [rbp+0C0h+var_F8]
0x1402c4169  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c416e  mov     [rbp+0C0h+var_68], r15
0x1402c4172  lea     rdx, aNeolcuv1; "NeoLCUV1"
0x1402c4179  lea     rcx, [rbp+0C0h+var_68]
0x1402c417d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c4182  nop
0x1402c4183  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c4189  movss   [rsp+1C0h+var_17C], xmm7
0x1402c418f  cmp     rbx, 3FCh
0x1402c4196  setz    al
0x1402c4199  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c419d  mov     rcx, [rbp+0C0h+var_68]
0x1402c41a1  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c41a6  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c41aa  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c41ae  jz      short loc_1402C41D8
0x1402c41b0  movzx   eax, al
0x1402c41b3  movd    xmm0, eax
0x1402c41b7  cvtdq2ps xmm0, xmm0
0x1402c41ba  movss   dword ptr [rdx+8], xmm0
0x1402c41bf  mov     [rdx], rcx
0x1402c41c2  movss   dword ptr [rdx+0Ch], xmm7
0x1402c41c7  movss   dword ptr [rdx+10h], xmm6
0x1402c41cc  xor     eax, eax
0x1402c41ce  mov     [rdx+14h], eax
0x1402c41d1  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c41d6  jmp     short loc_1402C41FF
0x1402c41d8  lea     rax, [rsp+1C0h+var_178]
0x1402c41dd  mov     [rsp+1C0h+var_198], rax
0x1402c41e2  lea     rax, [rsp+1C0h+var_17C]
0x1402c41e7  mov     [rsp+1C0h+ppv], rax
0x1402c41ec  lea     r9, [rsp+1C0h+var_180]
0x1402c41f1  lea     r8, [rsp+1C0h+var_170]
0x1402c41f6  lea     rcx, [rbp+0C0h+var_F8]
0x1402c41fa  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c41ff  mov     [rbp+0C0h+var_70], r15
0x1402c4203  lea     rdx, aNeowcosv1; "NeoWCOSV1"
0x1402c420a  lea     rcx, [rbp+0C0h+var_70]
0x1402c420e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c4213  nop
0x1402c4214  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c421a  movss   [rsp+1C0h+var_17C], xmm7
0x1402c4220  cmp     rbx, 7DAh
0x1402c4227  setz    al
0x1402c422a  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c422e  mov     rcx, [rbp+0C0h+var_70]
0x1402c4232  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c4237  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c423b  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c423f  jz      short loc_1402C4269
0x1402c4241  movzx   eax, al
0x1402c4244  movd    xmm0, eax
0x1402c4248  cvtdq2ps xmm0, xmm0
0x1402c424b  movss   dword ptr [rdx+8], xmm0
0x1402c4250  mov     [rdx], rcx
0x1402c4253  movss   dword ptr [rdx+0Ch], xmm7
0x1402c4258  movss   dword ptr [rdx+10h], xmm6
0x1402c425d  xor     eax, eax
0x1402c425f  mov     [rdx+14h], eax
0x1402c4262  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c4267  jmp     short loc_1402C4290
0x1402c4269  lea     rax, [rsp+1C0h+var_178]
0x1402c426e  mov     [rsp+1C0h+var_198], rax
0x1402c4273  lea     rax, [rsp+1C0h+var_17C]
0x1402c4278  mov     [rsp+1C0h+ppv], rax
0x1402c427d  lea     r9, [rsp+1C0h+var_180]
0x1402c4282  lea     r8, [rsp+1C0h+var_170]
0x1402c4287  lea     rcx, [rbp+0C0h+var_F8]
0x1402c428b  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c4290  mov     [rbp+0C0h+var_78], r15
0x1402c4294  lea     rdx, aNeofuldsv1; "NeoFUldsV1"
0x1402c429b  lea     rcx, [rbp+0C0h+var_78]
0x1402c429f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c42a4  nop
0x1402c42a5  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c42ab  movss   [rsp+1C0h+var_17C], xmm7
0x1402c42b1  cmp     rbx, 271Ah
0x1402c42b8  setz    al
0x1402c42bb  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c42bf  mov     rcx, [rbp+0C0h+var_78]
0x1402c42c3  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c42c8  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c42cc  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c42d0  jz      short loc_1402C42FA
0x1402c42d2  movzx   eax, al
0x1402c42d5  movd    xmm0, eax
0x1402c42d9  cvtdq2ps xmm0, xmm0
0x1402c42dc  movss   dword ptr [rdx+8], xmm0
0x1402c42e1  mov     [rdx], rcx
0x1402c42e4  movss   dword ptr [rdx+0Ch], xmm7
0x1402c42e9  movss   dword ptr [rdx+10h], xmm6
0x1402c42ee  xor     eax, eax
0x1402c42f0  mov     [rdx+14h], eax
0x1402c42f3  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c42f8  jmp     short loc_1402C4321
0x1402c42fa  lea     rax, [rsp+1C0h+var_178]
0x1402c42ff  mov     [rsp+1C0h+var_198], rax
0x1402c4304  lea     rax, [rsp+1C0h+var_17C]
0x1402c4309  mov     [rsp+1C0h+ppv], rax
0x1402c430e  lea     r9, [rsp+1C0h+var_180]
0x1402c4313  lea     r8, [rsp+1C0h+var_170]
0x1402c4318  lea     rcx, [rbp+0C0h+var_F8]
0x1402c431c  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c4321  mov     [rbp+0C0h+var_80], r15
0x1402c4325  lea     rdx, aNeofuoffv1; "NeoFUoffV1"
0x1402c432c  lea     rcx, [rbp+0C0h+var_80]
0x1402c4330  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c4335  nop
0x1402c4336  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c433c  movss   [rsp+1C0h+var_17C], xmm7
0x1402c4342  cmp     rbx, 2724h
0x1402c4349  setz    al
0x1402c434c  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c4350  mov     rcx, [rbp+0C0h+var_80]
0x1402c4354  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c4359  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c435d  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c4361  jz      short loc_1402C438B
0x1402c4363  movzx   eax, al
0x1402c4366  movd    xmm0, eax
0x1402c436a  cvtdq2ps xmm0, xmm0
0x1402c436d  movss   dword ptr [rdx+8], xmm0
0x1402c4372  mov     [rdx], rcx
0x1402c4375  movss   dword ptr [rdx+0Ch], xmm7
0x1402c437a  movss   dword ptr [rdx+10h], xmm6
0x1402c437f  xor     eax, eax
0x1402c4381  mov     [rdx+14h], eax
0x1402c4384  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c4389  jmp     short loc_1402C43B2
0x1402c438b  lea     rax, [rsp+1C0h+var_178]
0x1402c4390  mov     [rsp+1C0h+var_198], rax
0x1402c4395  lea     rax, [rsp+1C0h+var_17C]
0x1402c439a  mov     [rsp+1C0h+ppv], rax
0x1402c439f  lea     r9, [rsp+1C0h+var_180]
0x1402c43a4  lea     r8, [rsp+1C0h+var_170]
0x1402c43a9  lea     rcx, [rbp+0C0h+var_F8]
0x1402c43ad  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c43b2  mov     [rbp+0C0h+var_88], r15
0x1402c43b6  lea     rdx, aNeofuv1; "NeoFUV1"
0x1402c43bd  lea     rcx, [rbp+0C0h+var_88]
0x1402c43c1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c43c6  nop
0x1402c43c7  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c43cd  movss   [rsp+1C0h+var_17C], xmm7
0x1402c43d3  cmp     rbx, 272Eh
0x1402c43da  setz    al
0x1402c43dd  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c43e1  mov     rcx, [rbp+0C0h+var_88]
0x1402c43e5  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c43ea  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c43ee  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c43f2  jz      short loc_1402C441C
0x1402c43f4  movzx   eax, al
0x1402c43f7  movd    xmm0, eax
0x1402c43fb  cvtdq2ps xmm0, xmm0
0x1402c43fe  movss   dword ptr [rdx+8], xmm0
0x1402c4403  mov     [rdx], rcx
0x1402c4406  movss   dword ptr [rdx+0Ch], xmm7
0x1402c440b  movss   dword ptr [rdx+10h], xmm6
0x1402c4410  xor     eax, eax
0x1402c4412  mov     [rdx+14h], eax
0x1402c4415  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c441a  jmp     short loc_1402C4443
0x1402c441c  lea     rax, [rsp+1C0h+var_178]
0x1402c4421  mov     [rsp+1C0h+var_198], rax
0x1402c4426  lea     rax, [rsp+1C0h+var_17C]
0x1402c442b  mov     [rsp+1C0h+ppv], rax
0x1402c4430  lea     r9, [rsp+1C0h+var_180]
0x1402c4435  lea     r8, [rsp+1C0h+var_170]
0x1402c443a  lea     rcx, [rbp+0C0h+var_F8]
0x1402c443e  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c4443  mov     [rbp+0C0h+var_90], r15
0x1402c4447  lea     rdx, aNeofussbv1; "NeoFUssbV1"
0x1402c444e  lea     rcx, [rbp+0C0h+var_90]
0x1402c4452  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c4457  nop
0x1402c4458  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c445e  movss   [rsp+1C0h+var_17C], xmm7
0x1402c4464  cmp     rbx, 2738h
0x1402c446b  setz    al
0x1402c446e  mov     byte ptr [rsp+1C0h+var_180], al
0x1402c4472  mov     rcx, [rbp+0C0h+var_90]
0x1402c4476  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1402c447b  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1402c447f  cmp     rdx, [rbp+0C0h+var_E8]
0x1402c4483  jz      short loc_1402C44AD
0x1402c4485  movzx   eax, al
0x1402c4488  movd    xmm0, eax
0x1402c448c  cvtdq2ps xmm0, xmm0
0x1402c448f  movss   dword ptr [rdx+8], xmm0
0x1402c4494  mov     [rdx], rcx
0x1402c4497  movss   dword ptr [rdx+0Ch], xmm7
0x1402c449c  movss   dword ptr [rdx+10h], xmm6
0x1402c44a1  xor     eax, eax
0x1402c44a3  mov     [rdx+14h], eax
0x1402c44a6  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1402c44ab  jmp     short loc_1402C44D4
0x1402c44ad  lea     rax, [rsp+1C0h+var_178]
0x1402c44b2  mov     [rsp+1C0h+var_198], rax
0x1402c44b7  lea     rax, [rsp+1C0h+var_17C]
0x1402c44bc  mov     [rsp+1C0h+ppv], rax
0x1402c44c1  lea     r9, [rsp+1C0h+var_180]
0x1402c44c6  lea     r8, [rsp+1C0h+var_170]
0x1402c44cb  lea     rcx, [rbp+0C0h+var_F8]
0x1402c44cf  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1402c44d4  mov     [rbp+0C0h+var_98], r15
0x1402c44d8  lea     rdx, aNeofusfbv1; "NeoFUsfbV1"
0x1402c44df  lea     rcx, [rbp+0C0h+var_98]
0x1402c44e3  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402c44e8  nop
0x1402c44e9  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1402c44ef  movss   [rsp+1C0h+var_17C], xmm7
0x1402c44f5  cmp     rbx, 2742h
0x1402c44fc  setz    al
0x1402c44ff  mov     byte ptr [rsp+1C0h+var_180], al
  ... truncated ...
```
