# WaaS::Device::FeatureEvaluator::EvaluateNPUFeatures(std::vector<WaaS::Device::NPUFeature,std::allocator<WaaS::Device::NPUFeature>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180051298`
- end: `0x180052005`
- name: `?EvaluateNPUFeatures@FeatureEvaluator@Device@WaaS@@AEAAJAEAV?$vector@VNPUFeature@Device@WaaS@@V?$allocator@VNPUFeature@Device@WaaS@@@std@@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@@Z`
- size: `3437`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800529d8`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18001e5a0`
- `0x180040ba0`
- `0x180046bf4`
- `0x180048498`
- `0x18004987c`
- `0x1800499b0`
- `0x180051298`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005138a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005138a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051400`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051b58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051fdd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051400`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051b58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051fdd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005136e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005136e`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180051359`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180051359`

## string_xrefs

- `0x180051380`: `DXCoreCreateAdapterFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WaaS::Device::FeatureEvaluator::EvaluateNPUFeatures(__int64 a1, __int64 *a2, _QWORD *a3)
{
  _QWORD *v5; // rdi
  _QWORD *v6; // rsi
  _QWORD *i; // rbx
  const wchar_t *v8; // rdx
  size_t v9; // r8
  const wchar_t *v10; // rcx
  HMODULE LibraryW; // rbx
  FARPROC ProcAddress; // rax
  int v13; // eax
  unsigned int v14; // edi
  _QWORD *v16; // rdx
  __int64 v17; // r14
  _QWORD *j; // rsi
  __int64 n; // rax
  __int64 v20; // rsi
  __int64 k; // rdi
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  bool v26; // zf
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdi
  __int64 v32; // r13
  _QWORD *v33; // rdx
  __int64 v34; // r8
  int v35; // esi
  _QWORD *v36; // rdx
  __int64 v37; // r8
  _QWORD *v38; // rdx
  __int64 v39; // r8
  _QWORD *v40; // rdx
  __int64 v41; // r8
  _QWORD *v42; // rdx
  __int64 v43; // r8
  _QWORD *v44; // rdx
  __int64 v45; // r8
  _QWORD *v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r14
  __int64 v49; // r14
  void (__fastcall ***v50)(_QWORD, _QWORD); // r14
  void (__fastcall ***m)(_QWORD, _QWORD); // rsi
  int v52; // [rsp+20h] [rbp-A9h]
  __int64 *v53; // [rsp+30h] [rbp-99h] BYREF
  __int64 v54; // [rsp+38h] [rbp-91h] BYREF
  int v55[2]; // [rsp+40h] [rbp-89h] BYREF
  __int128 v56; // [rsp+48h] [rbp-81h] BYREF
  _QWORD *v57; // [rsp+58h] [rbp-71h]
  _QWORD *v58; // [rsp+60h] [rbp-69h] BYREF
  int v59; // [rsp+68h] [rbp-61h]
  unsigned int v60; // [rsp+6Ch] [rbp-5Dh]
  _QWORD v61[2]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v62; // [rsp+80h] [rbp-49h] BYREF
  wchar_t String[8]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v64; // [rsp+A0h] [rbp-29h]
  wchar_t *S2[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v66; // [rsp+C0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v5 = (_QWORD *)a3[1];
  if ( v5 == (_QWORD *)*a3 )
    return 0;
  *(_OWORD *)S2 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S2, L"Device\\Detect\\Hardware\\NPU", 26);
  v6 = (_QWORD *)a3[1];
  for ( i = (_QWORD *)*a3; i != v6; i += 4 )
  {
    v8 = (const wchar_t *)S2;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      v8 = S2[0];
    v9 = i[2];
    v10 = i[3] <= 7u ? (const wchar_t *)i : (const wchar_t *)*i;
    if ( v9 == (_QWORD)v66 && (!v9 || !wmemcmp(v10, v8, v9)) )
      break;
  }
  std::wstring::~wstring(S2);
  if ( v5 == i || !IsApiSetImplemented("ext-ms-win-dxcore-l1-1-0") )
    return 0;
  LibraryW = LoadLibraryW(L"ext-ms-win-dxcore-l1-1-0");
  v61[1] = LibraryW;
  v54 = 0;
  ProcAddress = GetProcAddress(LibraryW, "DXCoreCreateAdapterFactory");
  if ( !ProcAddress )
  {
LABEL_208:
    if ( LibraryW )
      FreeLibrary(LibraryW);
    return 0;
  }
  v13 = ((__int64 (__fastcall *)(GUID *, __int64 *))ProcAddress)(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v54);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x245,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v13,
      v52);
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
LABEL_19:
    if ( LibraryW )
      FreeLibrary(LibraryW);
    return v14;
  }
  v56 = 0;
  v57 = 0;
  v58 = &DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(&v56, 0, &v58);
  v58 = &DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
  if ( *((_QWORD **)&v56 + 1) == v57 )
  {
    std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(&v56, *((_QWORD *)&v56 + 1), &v58);
    v16 = (_QWORD *)*((_QWORD *)&v56 + 1);
  }
  else
  {
    **((_QWORD **)&v56 + 1) = &DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
    v16 = (_QWORD *)(*((_QWORD *)&v56 + 1) + 8LL);
    *((_QWORD *)&v56 + 1) += 8LL;
  }
  v58 = &DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
  if ( v16 == v57 )
  {
    std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(&v56, v16, &v58);
    v17 = *((_QWORD *)&v56 + 1);
  }
  else
  {
    *v16 = &DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
    v17 = *((_QWORD *)&v56 + 1) + 8LL;
    *((_QWORD *)&v56 + 1) += 8LL;
  }
  for ( j = (_QWORD *)v56; ; ++j )
  {
    v58 = j;
    if ( j == (_QWORD *)v17 )
    {
LABEL_33:
      v20 = a2[1];
      for ( k = *a2; k != v20 && *(_BYTE *)(k + 264); k += 272 )
        ;
      if ( k != v20 )
      {
        v48 = k + 272;
        if ( k + 272 == v20 )
          goto LABEL_200;
        do
        {
          if ( *(_BYTE *)(v48 + 264) )
          {
            WaaS::Device::NPUFeature::operator=(k, v48);
            k += 272;
          }
          v48 += 272;
        }
        while ( v48 != v20 );
        if ( k != v20 )
        {
LABEL_200:
          v49 = a2[1];
          while ( v20 != v49 )
          {
            WaaS::Device::NPUFeature::operator=(k, v20);
            k += 272;
            v20 += 272;
          }
          v50 = (void (__fastcall ***)(_QWORD, _QWORD))a2[1];
          for ( m = (void (__fastcall ***)(_QWORD, _QWORD))k; m != v50; m += 34 )
            (**m)(m, 0);
          a2[1] = k;
        }
      }
      std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      goto LABEL_208;
    }
    *(_QWORD *)v55 = 0;
    for ( n = *a2; ; n += 272 )
    {
      if ( n == a2[1] )
        goto LABEL_33;
      if ( *(_BYTE *)(n + 264) != 1 )
        break;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)v54 + 24LL))(
            v54,
            1,
            *j,
            &GUID_526c7776_40e9_459b_b711_f32ad76dfc28);
    v14 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
        (const char *)(unsigned int)v22,
        (int)v55);
      if ( *(_QWORD *)v55 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
      std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      goto LABEL_19;
    }
    v60 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 32LL))(*(_QWORD *)v55);
    v23 = 0;
    v59 = 0;
    if ( v60 )
      break;
LABEL_109:
    if ( *(_QWORD *)v55 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
  }
  while ( 1 )
  {
    v53 = 0;
    *(_OWORD *)S2 = 0;
    LODWORD(v66) = 0;
    v61[0] = 0;
    v24 = **(_QWORD **)v55;
    v53 = 0;
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 **))(v24 + 24))(
            *(_QWORD *)v55,
            v23,
            &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
            &v53);
    v14 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x263,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
        (const char *)(unsigned int)v25,
        (int)v55);
      if ( v53 )
        (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
      if ( *(_QWORD *)v55 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
      std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      goto LABEL_19;
    }
    v26 = (*(unsigned __int8 (__fastcall **)(__int64 *, __int64))(*v53 + 40))(v53, 14) == 0;
    v27 = *v53;
    if ( !v26 )
      break;
    if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64))(v27 + 40))(v53, 3) )
    {
      v62 = 0;
      v29 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int128 *))(*v53 + 48))(v53, 3, 16, &v62);
      v14 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
          (const char *)(unsigned int)v29,
          (int)v55);
        if ( v53 )
          (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
        if ( *(_QWORD *)v55 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
        std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        goto LABEL_19;
      }
      S2[0] = (wchar_t *)v62;
      LODWORD(v66) = HIDWORD(v62);
      LODWORD(S2[1]) = DWORD2(v62);
      goto LABEL_49;
    }
LABEL_105:
    if ( v53 )
      (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    v23 = (unsigned int)(v59 + 1);
    v59 = v23;
    if ( (unsigned int)v23 >= v60 )
    {
      j = v58;
      goto LABEL_109;
    }
  }
  v28 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, wchar_t **))(v27 + 48))(v53, 14, 20, S2);
  v14 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v28,
      (int)v55);
    if ( v53 )
      (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    if ( *(_QWORD *)v55 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
    std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    goto LABEL_19;
  }
LABEL_49:
  if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64))(*v53 + 40))(v53, 1) )
  {
    v30 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD *))(*v53 + 48))(v53, 1, 8, v61);
    v14 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x279,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
        (const char *)(unsigned int)v30,
        (int)v55);
      if ( v53 )
        (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
      if ( *(_QWORD *)v55 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
      std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      goto LABEL_19;
    }
  }
  v31 = *a2;
  v32 = a2[1];
  if ( *a2 == v32 )
    goto LABEL_105;
  while ( 1 )
  {
    if ( *(_BYTE *)(v31 + 264) )
      goto LABEL_102;
    if ( !*(_QWORD *)(v31 + 24) )
      goto LABEL_60;
    LODWORD(v62) = 0;
    v33 = (_QWORD *)(v31 + 8);
    if ( *(_QWORD *)(v31 + 32) > 7u )
      v33 = (_QWORD *)*v33;
    *(_OWORD *)String = 0;
    v64 = 0;
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    std::wstring::_Construct<1,unsigned short const *>(String, v33);
    v35 = WaaS::Device::ConvertToUInt32(String);
    std::wstring::~wstring(String);
    if ( v35 < 0 )
      break;
    if ( LODWORD(S2[0]) == (_DWORD)v62 )
    {
LABEL_60:
      if ( !*(_QWORD *)(v31 + 56) )
        goto LABEL_73;
      LODWORD(v62) = 0;
      v36 = (_QWORD *)(v31 + 40);
      if ( *(_QWORD *)(v31 + 64) > 7u )
        v36 = (_QWORD *)*v36;
      *(_OWORD *)String = 0;
      v64 = 0;
      v37 = -1;
      do
        ++v37;
      while ( *((_WORD *)v36 + v37) );
      std::wstring::_Construct<1,unsigned short const *>(String, v36);
      v35 = WaaS::Device::ConvertToUInt32(String);
      std::wstring::~wstring(String);
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x291,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
          (const char *)(unsigned int)v35,
          (int)v55);
        if ( v53 )
          (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
        if ( *(_QWORD *)v55 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
        std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        goto LABEL_127;
      }
      if ( HIDWORD(S2[0]) == (_DWORD)v62 )
      {
LABEL_73:
        if ( !*(_QWORD *)(v31 + 88) )
          goto LABEL_80;
        LODWORD(v62) = 0;
        v38 = (_QWORD *)(v31 + 72);
        if ( *(_QWORD *)(v31 + 96) > 7u )
          v38 = (_QWORD *)*v38;
        *(_OWORD *)String = 0;
        v64 = 0;
        v39 = -1;
        do
          ++v39;
        while ( *((_WORD *)v38 + v39) );
        std::wstring::_Construct<1,unsigned short const *>(String, v38);
        v35 = WaaS::Device::ConvertToUInt32(String);
        std::wstring::~wstring(String);
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29B,
            (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
            (const char *)(unsigned int)v35,
            (int)v55);
          if ( v53 )
            (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
          if ( *(_QWORD *)v55 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
          std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
          if ( v54 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
          goto LABEL_127;
        }
        if ( LODWORD(S2[1]) == (_DWORD)v62 )
        {
LABEL_80:
          if ( !*(_QWORD *)(v31 + 120) )
            goto LABEL_87;
          LODWORD(v62) = 0;
          v40 = (_QWORD *)(v31 + 104);
          if ( *(_QWORD *)(v31 + 128) > 7u )
            v40 = (_QWORD *)*v40;
          *(_OWORD *)String = 0;
          v64 = 0;
          v41 = -1;
          do
            ++v41;
          while ( *((_WORD *)v40 + v41) );
          std::wstring::_Construct<1,unsigned short const *>(String, v40);
          v35 = WaaS::Device::ConvertToUInt32(String);
          std::wstring::~wstring(String);
          if ( v35 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2A5,
              (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
              (const char *)(unsigned int)v35,
              (int)v55);
            if ( v53 )
              (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
            if ( *(_QWORD *)v55 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
            std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
            if ( v54 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            goto LABEL_127;
          }
          if ( HIDWORD(S2[1]) == (_DWORD)v62 )
          {
LABEL_87:
            if ( !*(_QWORD *)(v31 + 152) )
              goto LABEL_94;
            LODWORD(v62) = 0;
            v42 = (_QWORD *)(v31 + 136);
            if ( *(_QWORD *)(v31 + 160) > 7u )
              v42 = (_QWORD *)*v42;
            *(_OWORD *)String = 0;
            v64 = 0;
            v43 = -1;
            do
              ++v43;
            while ( *((_WORD *)v42 + v43) );
            std::wstring::_Construct<1,unsigned short const *>(String, v42);
            v35 = WaaS::Device::ConvertToUInt32(String);
            std::wstring::~wstring(String);
            if ( v35 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2AF,
                (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
                (const char *)(unsigned int)v35,
                (int)v55);
              if ( v53 )
                (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
              if ( *(_QWORD *)v55 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
              std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
              if ( v54 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
              goto LABEL_127;
            }
            if ( (_DWORD)v66 == (_DWORD)v62 )
            {
LABEL_94:
              if ( !*(_QWORD *)(v31 + 216) )
                goto LABEL_95;
              *(_QWORD *)&v62 = 0;
              v44 = (_QWORD *)(v31 + 200);
              if ( *(_QWORD *)(v31 + 224) > 7u )
                v44 = (_QWORD *)*v44;
              *(_OWORD *)String = 0;
              v64 = 0;
              v45 = -1;
              do
                ++v45;
              while ( *((_WORD *)v44 + v45) );
              std::wstring::_Construct<1,unsigned short const *>(String, v44);
              v35 = WaaS::Device::ConvertToUInt64(String);
              std::wstring::~wstring(String);
              if ( v35 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B9,
                  (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
                  (const char *)(unsigned int)v35,
                  (int)v55);
                if ( v53 )
                  (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
                if ( *(_QWORD *)v55 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
                std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
                if ( v54 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                goto LABEL_127;
              }
              if ( v61[0] >= (unsigned __int64)v62 )
              {
LABEL_95:
                if ( !*(_QWORD *)(v31 + 248) )
                  goto LABEL_104;
                *(_QWORD *)&v62 = 0;
                v46 = (_QWORD *)(v31 + 232);
                if ( *(_QWORD *)(v31 + 256) > 7u )
                  v46 = (_QWORD *)*v46;
                *(_OWORD *)String = 0;
                v64 = 0;
                v47 = -1;
                do
                  ++v47;
                while ( *((_WORD *)v46 + v47) );
                std::wstring::_Construct<1,unsigned short const *>(String, v46);
                v35 = WaaS::Device::ConvertToUInt64(String);
                std::wstring::~wstring(String);
                if ( v35 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2C3,
                    (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
                    (const char *)(unsigned int)v35,
                    (int)v55);
                  if ( v53 )
                    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
                  if ( *(_QWORD *)v55 )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
                  std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
                  if ( v54 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                  goto LABEL_127;
                }
                if ( v61[0] <= (unsigned __int64)v62 )
                {
LABEL_104:
                  *(_BYTE *)(v31 + 264) = 1;
                  goto LABEL_105;
                }
              }
            }
          }
        }
      }
    }
LABEL_102:
    v31 += 272;
    if ( v31 == v32 )
      goto LABEL_105;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x287,
    (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
    (const char *)(unsigned int)v35,
    (int)v55);
  if ( v53 )
    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
  if ( *(_QWORD *)v55 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
  std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(&v56);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
LABEL_127:
  if ( LibraryW )
    FreeLibrary(LibraryW);
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x180051298  push    rbp
0x18005129a  push    rbx
0x18005129b  push    rsi
0x18005129c  push    rdi
0x18005129d  push    r12
0x18005129f  push    r13
0x1800512a1  push    r14
0x1800512a3  push    r15
0x1800512a5  lea     rbp, [rsp-1Fh]
0x1800512aa  sub     rsp, 0E8h
0x1800512b1  mov     rax, cs:__security_cookie
0x1800512b8  xor     rax, rsp
0x1800512bb  mov     [rbp+57h+var_50], rax
0x1800512bf  mov     rbx, r8
0x1800512c2  mov     r15, rdx
0x1800512c5  xor     r12d, r12d
0x1800512c8  mov     rdi, [r8+8]
0x1800512cc  cmp     rdi, [r8]
0x1800512cf  jz      loc_180051FE3
0x1800512d5  xorps   xmm0, xmm0
0x1800512d8  movups  xmmword ptr [rbp+57h+S2], xmm0
0x1800512dc  xorps   xmm1, xmm1
0x1800512df  movdqu  [rbp+57h+var_60], xmm1
0x1800512e4  lea     r8d, [r12+1Ah]
0x1800512e9  lea     rdx, aDeviceDetectHa; "Device\\Detect\\Hardware\\NPU"
0x1800512f0  lea     rcx, [rbp+57h+S2]
0x1800512f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800512f9  mov     rsi, [rbx+8]
0x1800512fd  mov     rbx, [rbx]
0x180051300  jmp     short loc_18005133B
0x180051302  lea     rdx, [rbp+57h+S2]
0x180051306  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18005130b  cmova   rdx, [rbp+57h+S2]; S2
0x180051310  mov     r8, [rbx+10h]; N
0x180051314  cmp     qword ptr [rbx+18h], 7
0x180051319  jbe     short loc_180051320
0x18005131b  mov     rcx, [rbx]
0x18005131e  jmp     short loc_180051323
0x180051320  mov     rcx, rbx; S1
0x180051323  cmp     r8, qword ptr [rbp+57h+var_60]
0x180051327  jnz     short loc_180051337
0x180051329  test    r8, r8
0x18005132c  jz      short loc_180051340
0x18005132e  call    wmemcmp
0x180051333  test    eax, eax
0x180051335  jz      short loc_180051340
0x180051337  add     rbx, 20h ; ' '
0x18005133b  cmp     rbx, rsi
0x18005133e  jnz     short loc_180051302
0x180051340  lea     rcx, [rbp+57h+S2]; void *
0x180051344  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051349  cmp     rdi, rbx
0x18005134c  jz      loc_180051FE3
0x180051352  lea     rcx, Contract; "ext-ms-win-dxcore-l1-1-0"
0x180051359  call    cs:__imp_IsApiSetImplemented
0x18005135f  test    eax, eax
0x180051361  jz      loc_180051FE3
0x180051367  lea     rcx, aExtMsWinDxcore; "ext-ms-win-dxcore-l1-1-0"
0x18005136e  call    cs:__imp_LoadLibraryW
0x180051374  mov     rbx, rax
0x180051377  mov     [rbp+57h+var_A8], rax
0x18005137b  mov     [rsp+120h+var_E8], r12
0x180051380  lea     rdx, aDxcorecreatead; "DXCoreCreateAdapterFactory"
0x180051387  mov     rcx, rax; hModule
0x18005138a  call    cs:__imp_GetProcAddress
0x180051390  test    rax, rax
0x180051393  jnz     short loc_1800513B1
0x180051395  mov     rcx, [rsp+120h+var_E8]
0x18005139a  test    rcx, rcx
0x18005139d  jz      short loc_1800513AC
0x18005139f  mov     rax, [rcx]
0x1800513a2  mov     rax, [rax+10h]
0x1800513a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513ab  nop
0x1800513ac  jmp     loc_180051FD5
0x1800513b1  lea     rdx, [rsp+120h+var_E8]
0x1800513b6  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x1800513bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513c2  mov     edi, eax
0x1800513c4  test    eax, eax
0x1800513c6  jns     short loc_18005140D
0x1800513c8  mov     rcx, [rbp+5Fh]; this
0x1800513cc  mov     r9d, eax; char *
0x1800513cf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x1800513d6  mov     edx, 245h; void *
0x1800513db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800513e0  nop
0x1800513e1  mov     rcx, [rsp+120h+var_E8]
0x1800513e6  test    rcx, rcx
0x1800513e9  jz      short loc_1800513F8
0x1800513eb  mov     rax, [rcx]
0x1800513ee  mov     rax, [rax+10h]
0x1800513f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513f7  nop
0x1800513f8  test    rbx, rbx
0x1800513fb  jz      short loc_180051406
0x1800513fd  mov     rcx, rbx; hLibModule
0x180051400  call    cs:__imp_FreeLibrary
0x180051406  mov     eax, edi
0x180051408  jmp     loc_180051FE5
0x18005140d  xorps   xmm0, xmm0
0x180051410  movdqu  [rsp+120h+var_D8], xmm0
0x180051416  mov     [rbp+57h+var_C8], r12
0x18005141a  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x180051421  mov     [rbp+57h+var_C0], rax
0x180051425  lea     r8, [rbp+57h+var_C0]
0x180051429  xor     edx, edx
0x18005142b  lea     rcx, [rsp+120h+var_D8]
0x180051430  call    ??$_Emplace_reallocate@AEBU_LUID@@@?$vector@U_LUID@@V?$allocator@U_LUID@@@std@@@std@@AEAAPEAU_LUID@@QEAU2@AEBU2@@Z; std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(_LUID * const,_LUID const &)
0x180051435  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x18005143c  mov     [rbp+57h+var_C0], rax
0x180051440  mov     rdx, qword ptr [rbp+57h+var_D8+8]
0x180051444  cmp     rdx, [rbp+57h+var_C8]
0x180051448  jz      short loc_18005145B
0x18005144a  mov     [rdx], rax
0x18005144d  mov     rdx, qword ptr [rbp+57h+var_D8+8]
0x180051451  add     rdx, 8
0x180051455  mov     qword ptr [rbp+57h+var_D8+8], rdx
0x180051459  jmp     short loc_18005146D
0x18005145b  lea     r8, [rbp+57h+var_C0]
0x18005145f  lea     rcx, [rsp+120h+var_D8]
0x180051464  call    ??$_Emplace_reallocate@AEBU_LUID@@@?$vector@U_LUID@@V?$allocator@U_LUID@@@std@@@std@@AEAAPEAU_LUID@@QEAU2@AEBU2@@Z; std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(_LUID * const,_LUID const &)
0x180051469  mov     rdx, qword ptr [rbp+57h+var_D8+8]
0x18005146d  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x180051474  mov     [rbp+57h+var_C0], rax
0x180051478  cmp     rdx, [rbp+57h+var_C8]
0x18005147c  jz      short loc_18005148F
0x18005147e  mov     [rdx], rax
0x180051481  mov     r14, qword ptr [rbp+57h+var_D8+8]
0x180051485  add     r14, 8
0x180051489  mov     qword ptr [rbp+57h+var_D8+8], r14
0x18005148d  jmp     short loc_1800514A1
0x18005148f  lea     r8, [rbp+57h+var_C0]
0x180051493  lea     rcx, [rsp+120h+var_D8]
0x180051498  call    ??$_Emplace_reallocate@AEBU_LUID@@@?$vector@U_LUID@@V?$allocator@U_LUID@@@std@@@std@@AEAAPEAU_LUID@@QEAU2@AEBU2@@Z; std::vector<_LUID>::_Emplace_reallocate<_LUID const &>(_LUID * const,_LUID const &)
0x18005149d  mov     r14, qword ptr [rbp+57h+var_D8+8]
0x1800514a1  mov     rsi, qword ptr [rsp+120h+var_D8]
0x1800514a6  mov     r13d, 110h
0x1800514ac  jmp     loc_180051A67
0x1800514b1  mov     qword ptr [rsp+120h+var_E0], r12
0x1800514b6  mov     rax, [r15]
0x1800514b9  jmp     short loc_1800514C7
0x1800514bb  cmp     byte ptr [rax+108h], 1
0x1800514c2  jnz     short loc_1800514D9
0x1800514c4  add     rax, r13
0x1800514c7  cmp     rax, [r15+8]
0x1800514cb  jnz     short loc_1800514BB
0x1800514cd  mov     rsi, [r15+8]
0x1800514d1  mov     rdi, [r15]
0x1800514d4  jmp     loc_180051F35
0x1800514d9  mov     rcx, [rsp+120h+var_E8]
0x1800514de  mov     rax, [rcx]
0x1800514e1  lea     rdx, [rsp+120h+var_E0]
0x1800514e6  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800514eb  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x1800514f2  mov     r8, [rsi]
0x1800514f5  mov     edx, 1
0x1800514fa  mov     rax, [rax+18h]
0x1800514fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051503  mov     edi, eax
0x180051505  test    eax, eax
0x180051507  js      loc_180051ED2
0x18005150d  mov     rcx, qword ptr [rsp+120h+var_E0]
0x180051512  mov     rax, [rcx]
0x180051515  mov     rax, [rax+20h]
0x180051519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005151e  mov     [rbp+57h+var_B4], eax
0x180051521  mov     edx, r12d
0x180051524  mov     [rbp+57h+var_B8], edx
0x180051527  test    eax, eax
0x180051529  jz      loc_180051A4C
0x18005152f  mov     [rsp+120h+var_F0], r12
0x180051534  xorps   xmm0, xmm0
0x180051537  xor     eax, eax
0x180051539  movups  xmmword ptr [rbp+57h+S2], xmm0
0x18005153d  mov     dword ptr [rbp+57h+var_60], eax
0x180051540  mov     [rbp+57h+var_B0], r12
0x180051544  mov     rcx, qword ptr [rsp+120h+var_E0]
0x180051549  mov     rax, [rcx]
0x18005154c  mov     [rsp+120h+var_F0], r12
0x180051551  lea     r9, [rsp+120h+var_F0]
0x180051556  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18005155d  mov     rax, [rax+18h]
0x180051561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051566  mov     edi, eax
0x180051568  test    eax, eax
0x18005156a  js      loc_180051E64
0x180051570  mov     rcx, [rsp+120h+var_F0]
0x180051575  mov     rax, [rcx]
0x180051578  mov     edi, 0Eh
0x18005157d  mov     edx, edi
0x18005157f  mov     rax, [rax+28h]
0x180051583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051588  mov     rcx, [rsp+120h+var_F0]
0x18005158d  test    al, al
0x18005158f  mov     rax, [rcx]
0x180051592  jz      loc_180051623
0x180051598  lea     r9, [rbp+57h+S2]
0x18005159c  lea     r8d, [rdi+6]
0x1800515a0  mov     edx, edi
0x1800515a2  mov     rax, [rax+30h]
0x1800515a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515ab  mov     edi, eax
0x1800515ad  test    eax, eax
0x1800515af  jns     loc_18005167F
0x1800515b5  mov     rcx, [rbp+5Fh]; this
0x1800515b9  mov     r9d, eax; char *
0x1800515bc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x1800515c3  mov     edx, 267h; void *
0x1800515c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800515cd  nop
0x1800515ce  mov     rcx, [rsp+120h+var_F0]
0x1800515d3  test    rcx, rcx
0x1800515d6  jz      short loc_1800515E5
0x1800515d8  mov     rax, [rcx]
0x1800515db  mov     rax, [rax+10h]
0x1800515df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515e4  nop
0x1800515e5  mov     rcx, qword ptr [rsp+120h+var_E0]
0x1800515ea  test    rcx, rcx
0x1800515ed  jz      short loc_1800515FC
0x1800515ef  mov     rax, [rcx]
0x1800515f2  mov     rax, [rax+10h]
0x1800515f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515fb  nop
0x1800515fc  lea     rcx, [rsp+120h+var_D8]
0x180051601  call    ??1?$vector@PEBVCPUHardwareIdParts@Device@WaaS2@@V?$allocator@PEBVCPUHardwareIdParts@Device@WaaS2@@@std@@@std@@QEAA@XZ; std::vector<WaaS2::Device::CPUHardwareIdParts const *>::~vector<WaaS2::Device::CPUHardwareIdParts const *>(void)
0x180051606  nop
0x180051607  mov     rcx, [rsp+120h+var_E8]
0x18005160c  test    rcx, rcx
0x18005160f  jz      short loc_18005161E
0x180051611  mov     rax, [rcx]
0x180051614  mov     rax, [rax+10h]
0x180051618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005161d  nop
0x18005161e  jmp     loc_1800513F8
0x180051623  mov     edi, 3
0x180051628  mov     edx, edi
0x18005162a  mov     rax, [rax+28h]
0x18005162e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051633  test    al, al
0x180051635  jz      loc_180051A1A
0x18005163b  xorps   xmm0, xmm0
0x18005163e  movups  [rbp+57h+var_A0], xmm0
0x180051642  mov     rcx, [rsp+120h+var_F0]
0x180051647  mov     rax, [rcx]
0x18005164a  lea     r9, [rbp+57h+var_A0]
0x18005164e  lea     r8d, [rdi+0Dh]
0x180051652  mov     edx, edi
0x180051654  mov     rax, [rax+30h]
0x180051658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005165d  mov     edi, eax
0x18005165f  test    eax, eax
0x180051661  js      loc_180051DF6
0x180051667  mov     eax, dword ptr [rbp+57h+var_A0]
0x18005166a  mov     dword ptr [rbp+57h+S2], eax
0x18005166d  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x180051670  mov     dword ptr [rbp+57h+S2+4], eax
0x180051673  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x180051676  mov     dword ptr [rbp+57h+S2+8], eax
0x180051679  mov     eax, dword ptr [rbp+57h+var_A0+0Ch]
0x18005167c  mov     dword ptr [rbp+57h+var_60], eax
0x18005167f  mov     rcx, [rsp+120h+var_F0]
0x180051684  mov     rax, [rcx]
0x180051687  mov     edx, 1
0x18005168c  mov     rax, [rax+28h]
0x180051690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051695  test    al, al
0x180051697  jz      short loc_1800516C1
0x180051699  mov     rcx, [rsp+120h+var_F0]
0x18005169e  mov     rax, [rcx]
0x1800516a1  lea     r9, [rbp+57h+var_B0]
0x1800516a5  mov     edx, 1
0x1800516aa  lea     r8d, [rdx+7]
0x1800516ae  mov     rax, [rax+30h]
0x1800516b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516b7  mov     edi, eax
0x1800516b9  test    eax, eax
0x1800516bb  js      loc_180051A79
0x1800516c1  mov     rdi, [r15]
0x1800516c4  mov     r13, [r15+8]
0x1800516c8  cmp     rdi, r13
0x1800516cb  jz      loc_180051A0C
0x1800516d1  xor     eax, eax
0x1800516d3  cmp     [rdi+108h], al
0x1800516d9  jz      short loc_1800516E3
0x1800516db  mov     r12b, 1
0x1800516de  jmp     loc_1800519F7
0x1800516e3  cmp     [rdi+18h], rax
0x1800516e7  jz      short loc_18005174F
0x1800516e9  mov     dword ptr [rbp+57h+var_A0], eax
0x1800516ec  lea     rdx, [rdi+8]
0x1800516f0  cmp     qword ptr [rdi+20h], 7
0x1800516f5  jbe     short loc_1800516FA
0x1800516f7  mov     rdx, [rdx]
0x1800516fa  xorps   xmm0, xmm0
0x1800516fd  movups  xmmword ptr [rbp+57h+String], xmm0
0x180051701  xorps   xmm1, xmm1
0x180051704  movdqu  [rbp+57h+var_80], xmm1
0x180051709  or      r8, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
