# LoadCimEntry(ConfigurationVersion,OverlayLoadType,void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *,utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>> &,utl::vector<bool,utl::allocator<bool>> &)

- ea: `0x180081ffc`
- end: `0x180082e04`
- name: `?LoadCimEntry@@YAJW4ConfigurationVersion@@W4OverlayLoadType@@PEAXAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WAEAV?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@4@AEAV?$vector@_NV?$allocator@_N@utl@@@4@@Z`
- size: `3592`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, installer_update`

## callers

- `0x180082e0c`
- `0x180083190`

## callees

- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18007cb38`
- `0x18007df88`
- `0x18007dff4`
- `0x18007e020`
- `0x18007e064`
- `0x180080288`
- `0x180080360`
- `0x180080430`
- `0x180080694`
- `0x180080ae8`
- `0x180080b90`
- `0x180080c38`
- `0x180080eb4`
- `0x180081ffc`
- `0x18008348c`
- `0x1800835a8`
- `0x1800836ac`
- `0x180083d28`
- `0x180083e00`
- `0x180083fe0`
- `0x18008475c`
- `0x180097e20`

## string_xrefs

- `0x180082068`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800820b6`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800820eb`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082198`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082213`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082257`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008229e`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082322`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800823ce`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008241f`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082479`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082562`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008264b`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800826e1`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008271c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082779`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082898`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800828c5`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800828f2`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008292c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082999`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800829ee`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082ba8`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082bf2`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082c52`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082c7c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082d1a`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082d52`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082d9f`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082112`: `DirectoryPath`
- `0x1800820dd`: `!DirectoryPath`
- `0x180082447`: `CimEntry.AutoRelativePath.append(L"\\")`
- `0x1800823f6`: `CimEntry.AutoRelativePath.assign(DirectoryPath)`
- `0x18008249a`: `CimEntry.AutoRelativePath.append(CimKeyName)`
- `0x180082583`: `Version == ConfigurationVersion::V1`
- `0x180082d3b`: `SeenCimsImageCount > 0`
- `0x180082d73`: `SeenCimsImageCount == ImageNames.size()`

## pseudocode

```c
__int64 __fastcall LoadCimEntry(int a1, unsigned int a2, void *a3, _QWORD *a4, __int64 a5, __int64 *a6, __int64 *a7)
{
  int v7; // r13d
  const char *v9; // rax
  const wchar_t *v10; // rdx
  signed int RegistrySZ; // ebx
  const wchar_t *v12; // r8
  void *v13; // r14
  int RegistryDWORD; // eax
  int v15; // edx
  const wchar_t *v16; // r8
  unsigned __int64 v17; // r15
  __m128i *v18; // rdx
  __int64 v19; // r8
  unsigned __int64 v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // r15
  __int64 v23; // rax
  __int64 v24; // r12
  __int64 v25; // rdi
  int v26; // edx
  int v27; // r8d
  const char *v28; // rax
  int v29; // edx
  int v30; // r8d
  bool *v31; // rcx
  __int64 v32; // r15
  const wchar_t *v33; // r8
  unsigned int *v34; // rsi
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rbx
  __int64 *v38; // rdx
  __int64 v39; // rax
  unsigned __int64 v40; // rsi
  unsigned __int64 v41; // rdi
  unsigned __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  const wchar_t *v46; // r8
  unsigned __int64 v47; // rax
  int v48; // ecx
  const wchar_t **v49; // rbx
  const wchar_t **v50; // rsi
  __int64 v51; // r8
  const char *v52; // rax
  __int64 v53; // r15
  __int64 v54; // r8
  const char *v55; // rax
  __int64 v56; // r12
  const wchar_t *v57; // rdx
  int v58; // edi
  const wchar_t *v59; // r8
  void *v60; // rdi
  const wchar_t *v61; // r8
  int v62; // r13d
  unsigned int *v63; // rdx
  __int64 v64; // r13
  int v65; // edx
  int v66; // r8d
  __int64 v67; // rax
  int v68; // edx
  char v69; // al
  const char *v70; // rax
  bool v71[8]; // [rsp+30h] [rbp-D0h] BYREF
  const char *v72; // [rsp+38h] [rbp-C8h] BYREF
  const char *v73; // [rsp+40h] [rbp-C0h]
  __int64 v74; // [rsp+48h] [rbp-B8h]
  const char *v75; // [rsp+50h] [rbp-B0h]
  void *v76; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v77; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v78; // [rsp+64h] [rbp-9Ch] BYREF
  int v79; // [rsp+68h] [rbp-98h]
  unsigned int v80[2]; // [rsp+70h] [rbp-90h] BYREF
  int v81; // [rsp+78h] [rbp-88h]
  unsigned int *v82; // [rsp+80h] [rbp-80h]
  void *v83; // [rsp+88h] [rbp-78h] BYREF
  __int64 v84; // [rsp+90h] [rbp-70h]
  __int64 v85; // [rsp+98h] [rbp-68h]
  _QWORD v86[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v87[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v88[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v89[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v90[4]; // [rsp+120h] [rbp+20h] BYREF
  int v91; // [rsp+140h] [rbp+40h] BYREF
  __m128i si128; // [rsp+148h] [rbp+48h] BYREF
  __int64 v93; // [rsp+158h] [rbp+58h]
  const char *v94; // [rsp+160h] [rbp+60h]
  int v95[4]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v96; // [rsp+178h] [rbp+78h]
  const char *v97; // [rsp+180h] [rbp+80h]
  __int64 *v98; // [rsp+188h] [rbp+88h] BYREF
  __int64 *v99; // [rsp+190h] [rbp+90h]
  __int64 v100; // [rsp+198h] [rbp+98h] BYREF
  const char *v101; // [rsp+1A0h] [rbp+A0h]

  v7 = 0;
  v81 = a1;
  v76 = a4;
  v80[0] = a2;
  v91 = 0;
  if ( a2 == 1 )
  {
    if ( !a5 )
    {
      v100 = 749;
      v98 = (__int64 *)"onecore\\base\\servicing\\overlayutil\\read.cpp";
      v99 = (__int64 *)"LoadCimEntry";
      v9 = "DirectoryPath";
      goto LABEL_8;
    }
  }
  else
  {
    if ( a2 != 2 )
    {
      v100 = 756;
      v98 = (__int64 *)"onecore\\base\\servicing\\overlayutil\\read.cpp";
      v101 = 0;
      v99 = (__int64 *)"LoadCimEntry";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v91,
               &v98,
               3221225659LL);
    }
    if ( a5 )
    {
      v100 = 753;
      v98 = (__int64 *)"onecore\\base\\servicing\\overlayutil\\read.cpp";
      v99 = (__int64 *)"LoadCimEntry";
      v9 = "!DirectoryPath";
LABEL_8:
      v101 = v9;
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v91,
               &v98);
    }
  }
  v10 = (const wchar_t *)*a4;
  v71[0] = 0;
  v83 = 0;
  RegistrySZ = OuOpenKey(a3, v10, &v83);
  if ( RegistrySZ < 0 )
    goto LABEL_142;
  v13 = v83;
  v77 = 0;
  RegistryDWORD = OuGetRegistryDWORD(v83, L"Index", v12, &v77, 0);
  if ( RegistryDWORD < 0 )
  {
LABEL_11:
    RegistrySZ = RegistryDWORD;
    goto LABEL_142;
  }
  v17 = v77;
  v77 = v17;
  if ( (_DWORD)v17 == -1 )
  {
    v96 = 778;
    *(_QWORD *)v95 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v18 = (__m128i *)v95;
    *(_QWORD *)&v95[2] = "LoadCimEntry";
    v97 = "CimIndex < 0xffffffffUL";
LABEL_14:
    v19 = 3221225659LL;
LABEL_15:
    RegistryDWORD = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                      &v91,
                      v18,
                      v19);
    goto LABEL_11;
  }
  v20 = v17;
  if ( 0xF0F0F0F0F0F0F0F1uLL * ((a6[1] - *a6) >> 3) <= v17 )
  {
    v21 = (unsigned int)(v17 + 1);
    v22 = v21;
    if ( !(unsigned __int8)utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Resize<,0>(
                             a6,
                             v21) )
    {
      v93 = 782;
      si128.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\overlayutil\\read.cpp";
      v18 = &si128;
      v19 = 3221225495LL;
      si128.m128i_i64[1] = (__int64)"LoadCimEntry";
      v94 = "CimEntries.resize(CimIndex + 1)";
      goto LABEL_15;
    }
    if ( !(unsigned __int8)utl::vector<bool,utl::allocator<bool>>::_Resize<,0>(a7, v22) )
    {
      v86[2] = 783;
      v86[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v18 = (__m128i *)v86;
      v19 = 3221225495LL;
      v86[1] = "LoadCimEntry";
      v86[3] = "SeenCimIndexes.resize(CimIndex + 1)";
      goto LABEL_15;
    }
    LODWORD(v17) = v77;
  }
  v23 = *a7;
  if ( *(_BYTE *)(v20 + *a7) )
  {
    v87[2] = 787;
    v87[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v18 = (__m128i *)v87;
    v87[1] = "LoadCimEntry";
    v87[3] = "SeenCimIndexes[CimIndex]";
    goto LABEL_14;
  }
  v24 = *a6;
  v85 = *a6;
  *(_BYTE *)(v20 + v23) = 1;
  v79 = 0;
  if ( v81 == 1 )
  {
    v78 = 0;
    RegistryDWORD = OuGetRegistryDWORD(v13, L"Projection", v16, &v78, v71);
    if ( RegistryDWORD < 0 )
      goto LABEL_11;
    if ( v78 )
    {
      if ( (_DWORD)v17 )
      {
        v88[2] = 809;
        v88[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v18 = (__m128i *)v88;
        v88[1] = "LoadCimEntry";
        v88[3] = "CimIndex == 0";
        goto LABEL_14;
      }
      LOBYTE(v7) = 1;
      v79 = v7;
    }
  }
  if ( !(_DWORD)v17 && !(_BYTE)v7 )
  {
    v78 = 0;
    RegistryDWORD = OuGetAndValidateRegistryEnum<enum OverlayImageFlags>((int)v13, v15, (int)v16, (int)&v78, v71);
    if ( RegistryDWORD < 0 )
      goto LABEL_11;
    if ( !v71[0] )
    {
      LOBYTE(v7) = (v78 & 1) != 0;
      v79 = (unsigned __int8)v7;
    }
  }
  v25 = 136 * v20;
  v84 = 136 * v20;
  if ( a5 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v25 + v24 + 56,
                             a5) )
    {
      v89[2] = 833;
      v89[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v18 = (__m128i *)v89;
      v19 = 3221225495LL;
      v89[1] = "LoadCimEntry";
      v89[3] = "CimEntry.AutoRelativePath.assign(DirectoryPath)";
      goto LABEL_15;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v25 + v24 + 56,
                             L"\\",
                             1) )
    {
      v90[2] = 834;
      v90[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v18 = (__m128i *)v90;
      v19 = 3221225495LL;
      v90[1] = "LoadCimEntry";
      v90[3] = "CimEntry.AutoRelativePath.append(L\"\\\\\")";
      goto LABEL_15;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v25 + v24 + 56,
                             *(_QWORD *)v76,
                             (__int64)(*((_QWORD *)v76 + 1) - *(_QWORD *)v76) >> 1) )
    {
      v74 = 835;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v73 = "LoadCimEntry";
      v28 = "CimEntry.AutoRelativePath.append(CimKeyName)";
LABEL_42:
      v19 = 3221225495LL;
LABEL_43:
      v75 = v28;
      v18 = (__m128i *)&v72;
      goto LABEL_15;
    }
  }
  else
  {
    v98 = &v100;
    v99 = &v100;
    LOWORD(v100) = 0;
    RegistrySZ = OuGetRegistrySZ((_DWORD)v13, v15, (_DWORD)v16, (unsigned int)&v98, (__int64)v71);
    if ( RegistrySZ < 0 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v98);
      goto LABEL_142;
    }
    if ( !v71[0] )
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v25 + v24 + 56, &v98);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v98);
  }
  RegistryDWORD = OuGetAndValidateRegistryEnum<enum OverlayCimType>((int)v13, v26, v27, (int)v25 + (int)v24 + 4, v71);
  if ( RegistryDWORD < 0 )
    goto LABEL_11;
  if ( v71[0] )
  {
    if ( v81 != 1 )
    {
      v74 = 865;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v73 = "LoadCimEntry";
      v28 = "Version == ConfigurationVersion::V1";
LABEL_53:
      v19 = 3221225659LL;
      goto LABEL_43;
    }
    *(_DWORD *)(v25 + v24 + 4) = 1;
  }
  v31 = v71;
  v32 = v25 + v24;
  if ( v80[0] == 2 )
    v31 = 0;
  RegistryDWORD = OuGetAndValidateRegistryEnum<enum OverlayCimHashAlgId>(
                    (int)v13,
                    v29,
                    v30,
                    (int)v25 + (int)v24 + 8,
                    v31);
  if ( RegistryDWORD < 0 )
    goto LABEL_11;
  if ( *(_DWORD *)(v32 + 8) )
  {
    v34 = (unsigned int *)(v25 + v24 + 28);
    v82 = v34;
    RegistryDWORD = OuGetRegistryDWORD(v13, L"HashSourceSize", v33, v34, 0);
    if ( RegistryDWORD < 0 )
      goto LABEL_11;
    v37 = v25 + v24;
    if ( v80[0] == 2 )
    {
      v38 = (__int64 *)v76;
      v39 = *(_QWORD *)(v37 + 112);
      v40 = *(_QWORD *)(v37 + 120) - v39;
      v41 = (unsigned __int64)((__int64)(*((_QWORD *)v76 + 1) - *(_QWORD *)v76) >> 1) >> 1;
      if ( v41 > v40 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                 v37 + 112,
                                 (unsigned __int64)((__int64)(*((_QWORD *)v76 + 1) - *(_QWORD *)v76) >> 1) >> 1) )
        {
          v74 = 896;
          v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v73 = "LoadCimEntry";
          v28 = "CimEntry.AutoHash.resize(CimKeyName.size() / 2)";
          goto LABEL_42;
        }
        memset(*(void **)(v37 + 120), 0, v41 - v40);
        v38 = (__int64 *)v76;
        v42 = v41 + *(_QWORD *)(v37 + 112);
      }
      else
      {
        v42 = v39 + v41;
      }
      *(_QWORD *)(v37 + 120) = v42;
      v43 = *(_QWORD *)(v37 + 120) - *(_QWORD *)(v37 + 112);
      v96 = *(_QWORD *)(v37 + 112);
      v44 = *v38;
      *(_QWORD *)&v95[2] = v43;
      v45 = v38[1];
      v93 = v44;
      *(_QWORD *)v95 = 0;
      si128.m128i_i64[0] = 2 * ((v45 - v44) >> 1);
      si128.m128i_i64[1] = si128.m128i_i64[0];
      if ( !(unsigned __int8)Windows::StringUtil::TryParseBase16StringToPreAllocatedBlob<_LUNICODE_STRING>(&si128, v95) )
      {
        v74 = 903;
        v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v73 = "LoadCimEntry";
        v28 = "Windows::StringUtil::TryParseBase16StringToPreAllocatedBlob( Windows::StringUtil::AsLUnicodeFromChars(CimK"
              "eyName.size(), CimKeyName.data()), &HashBlob)";
        goto LABEL_53;
      }
      if ( *(_QWORD *)(v37 + 120) - *(_QWORD *)(v37 + 112) != *(_QWORD *)v95 )
      {
        v74 = 906;
        v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v73 = "LoadCimEntry";
        v28 = "CimEntry.AutoHash.size() == HashBlob.Length";
        goto LABEL_53;
      }
      v25 = v84;
      v34 = v82;
    }
    else
    {
      RegistryDWORD = OuGetRegistryBinary(v13, v35, v36, v37 + 112);
      if ( RegistryDWORD < 0 )
        goto LABEL_11;
    }
    v47 = *(_QWORD *)(v37 + 120) - *(_QWORD *)(v37 + 112);
    if ( v47 >= 0xFFFFFFFF )
    {
      v74 = 918;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v73 = "LoadCimEntry";
      v28 = "CimEntry.AutoHash.size() < 0xffffffffUL";
      goto LABEL_53;
    }
    *(_DWORD *)(v25 + v24 + 24) = v47;
    RegistryDWORD = OuGetRegistryDWORD(v13, L"HashSourceSize", v46, v34, 0);
    if ( RegistryDWORD < 0 )
      goto LABEL_11;
    v48 = *(_DWORD *)(v32 + 8);
    if ( v48 )
    {
      if ( (unsigned int)(v48 - 1) <= 1 && *(_QWORD *)(v37 + 112) )
      {
        if ( (unsigned int)(v48 - 1) <= 1 && *(_DWORD *)(v25 + v24 + 24) == 32 )
        {
          if ( (unsigned int)(v48 - 1) <= 1 && *v34 < 0x1000 )
            goto LABEL_82;
LABEL_88:
          v74 = 930;
          v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v73 = "LoadCimEntry";
          v28 = "ValidateHashSourceSize(CimEntry.Data.HashAlgId, CimEntry.Data.HashSourceSize)";
          goto LABEL_53;
        }
        goto LABEL_89;
      }
    }
    else if ( !*(_QWORD *)(v37 + 112) )
    {
      if ( !*(_DWORD *)(v25 + v24 + 24) )
      {
        if ( !*v34 )
          goto LABEL_82;
        goto LABEL_88;
      }
LABEL_89:
      v74 = 929;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v73 = "LoadCimEntry";
      v28 = "ValidateHashSize(CimEntry.Data.HashAlgId, CimEntry.Data.HashSize)";
      goto LABEL_53;
    }
    v74 = 928;
    v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v73 = "LoadCimEntry";
    v28 = "ValidateHash(CimEntry.Data.HashAlgId, CimEntry.AutoHash.data())";
    goto LABEL_53;
  }
LABEL_82:
  if ( *(_DWORD *)(v25 + v24 + 4) == 2 )
  {
    v93 = -1;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    RegistrySZ = OuEnumerateSubKeys(v13, &si128);
    if ( RegistrySZ < 0 )
    {
LABEL_84:
      utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
      goto LABEL_142;
    }
    v50 = (const wchar_t **)si128.m128i_i64[1];
    v49 = (const wchar_t **)si128.m128i_i64[0];
    if ( si128.m128i_i64[0] == si128.m128i_i64[1] )
    {
      v74 = 940;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v51 = 3221225659LL;
      v73 = "LoadCimEntry";
      v52 = "ImageNames.empty()";
LABEL_93:
      v75 = v52;
      RegistrySZ = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                     &v91,
                     &v72,
                     v51);
      goto LABEL_84;
    }
    v53 = (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 5;
    v82 = (unsigned int *)(v25 + v24 + 88);
    if ( !(unsigned __int8)utl::vector<AutoOverlayImageConfiguration,utl::allocator<AutoOverlayImageConfiguration>>::_Resize<,0>(
                             v82,
                             v53) )
    {
      v74 = 942;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v51 = 3221225495LL;
      v73 = "LoadCimEntry";
      v52 = "CimEntry.AutoImages.resize(ImageNames.size())";
      goto LABEL_93;
    }
    v96 = -1;
    *(__m128i *)v95 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    if ( !(unsigned __int8)utl::vector<bool,utl::allocator<bool>>::_Resize<,0>(v95, ((char *)v50 - (char *)v49) >> 5) )
    {
      v74 = 946;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v54 = 3221225495LL;
      v73 = "LoadCimEntry";
      v55 = "SeenCimImageIndexes.resize(ImageNames.size())";
      goto LABEL_98;
    }
    v56 = 0;
    while ( v49 != v50 )
    {
      v57 = *v49;
      v76 = 0;
      v58 = OuOpenKey(v13, v57, &v76);
      if ( v58 < 0 )
        goto LABEL_131;
      v60 = v76;
      v80[0] = 0;
      v62 = OuGetRegistryDWORD(v76, L"Index", v59, v80, 0);
      if ( v62 < 0 )
      {
        AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v76);
        utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(v95);
        utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
        RegistrySZ = v62;
        goto LABEL_142;
      }
      v63 = v82;
      v64 = v80[0];
      if ( v80[0] >= 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v84 + v85 + 96) - *(_QWORD *)v82) >> 4) )
      {
        v74 = 965;
        v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v73 = "LoadCimEntry";
        v70 = "ImageIndex < CimEntry.AutoImages.size()";
        goto LABEL_129;
      }
      if ( v81 == 1 )
      {
        v80[0] = 0;
        v78 = OuGetRegistryDWORD(v60, L"Projection", v61, v80, v71);
        if ( (v78 & 0x80000000) != 0 )
        {
          AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v76);
          utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(v95);
          utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
          RegistrySZ = v78;
          goto LABEL_142;
        }
        if ( v80[0] )
        {
          if ( v77 )
          {
            v74 = 981;
            v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
            v73 = "LoadCimEntry";
            v70 = "CimIndex == 0";
            goto LABEL_129;
          }
          LOBYTE(v65) = 1;
          v79 = v65;
        }
        v63 = v82;
      }
      v66 = v95[0];
      if ( *(_BYTE *)(*(_QWORD *)v95 + v64) )
      {
        v74 = 987;
        v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v73 = "LoadCimEntry";
        v70 = "SeenCimImageIndexes[ImageIndex]";
        goto LABEL_129;
      }
      v67 = *(_QWORD *)v63;
      *(_BYTE *)(*(_QWORD *)v95 + v64) = 1;
      *(_QWORD *)v80 = 48 * v64 + v67;
      v58 = OuGetAndValidateRegistryEnum<enum OverlayImageFlags>((int)v60, (int)v63, v66, v80[0], v71);
      if ( v58 < 0 )
      {
LABEL_131:
        AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v76);
        utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(v95);
        utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
        RegistrySZ = v58;
        goto LABEL_142;
      }
      if ( !v71[0] )
      {
        if ( (**(_BYTE **)v80 & 1) != 0 )
        {
          v69 = 1;
          LOBYTE(v68) = 1;
          v79 = v68;
        }
        else
        {
          v69 = 0;
        }
        if ( v56 || v77 )
        {
          if ( v69 )
          {
            v74 = 1014;
LABEL_121:
            v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
            v73 = "LoadCimEntry";
            v70 = "IsProjectionImage";
LABEL_129:
            v75 = v70;
            RegistrySZ = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                           &v91,
                           &v72,
                           3221225659LL);
            AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v76);
            goto LABEL_99;
          }
        }
        else if ( !v69 )
        {
          v74 = 1010;
          goto LABEL_121;
        }
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(
        *(_QWORD *)v80 + 16LL,
        v49);
      ++v56;
      AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v76);
      v49 += 4;
    }
    if ( !v56 )
    {
      v74 = 1023;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v73 = "LoadCimEntry";
      v55 = "SeenCimsImageCount > 0";
LABEL_134:
      v54 = 3221225659LL;
LABEL_98:
      v75 = v55;
      RegistrySZ = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                     &v91,
                     &v72,
                     v54);
LABEL_99:
      utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(v95);
      goto LABEL_84;
    }
    if ( v56 != v53 )
    {
      v74 = 1024;
      v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v73 = "LoadCimEntry";
      v55 = "SeenCimsImageCount == ImageNames.size()";
      goto LABEL_134;
    }
    utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(v95);
    utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
    LOBYTE(v7) = v79;
  }
  if ( !v77 && !(_BYTE)v7 )
  {
    v74 = 1028;
    v72 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v73 = "LoadCimEntry";
    v28 = "(CimIndex == 0) && !ProjectionCimOrImageFound";
    goto LABEL_53;
  }
  RegistrySZ = 0;
LABEL_142:
  AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v83);
  return (unsigned int)RegistrySZ;
}

```

## disassembly

```asm
0x180081ffc  mov     [rsp-8+arg_0], rbx
0x180082001  push    rbp
0x180082002  push    rsi
0x180082003  push    rdi
0x180082004  push    r12
0x180082006  push    r13
0x180082008  push    r14
0x18008200a  push    r15
0x18008200c  lea     rbp, [rsp-0B0h]
0x180082014  sub     rsp, 1B0h
0x18008201b  mov     rax, cs:__security_cookie
0x180082022  xor     rax, rsp
0x180082025  mov     [rbp+0E0h+var_38], rax
0x18008202c  mov     r12, [rbp+0E0h+arg_30]
0x180082033  xor     r13d, r13d
0x180082036  mov     rdi, [rbp+0E0h+arg_28]
0x18008203d  mov     r10, r8
0x180082040  mov     rsi, [rbp+0E0h+arg_20]
0x180082047  mov     [rsp+1E0h+var_168], ecx
0x18008204b  mov     ecx, edx
0x18008204d  mov     [rsp+1E0h+var_188], r9
0x180082052  mov     [rsp+1E0h+var_170], edx
0x180082056  mov     [rbp+0E0h+var_A0], r13d
0x18008205a  sub     ecx, 1
0x18008205d  jz      loc_1800820E6
0x180082063  cmp     ecx, 1
0x180082066  jz      short loc_1800820B1
0x180082068  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008206f  mov     [rbp+0E0h+var_48], 2F4h
0x18008207a  mov     [rbp+0E0h+var_58], rax
0x180082081  lea     rdx, [rbp+0E0h+var_58]
0x180082088  lea     rax, aLoadcimentry; "LoadCimEntry"
0x18008208f  mov     [rbp+0E0h+var_40], r13
0x180082096  mov     r8d, 0C00000BBh
0x18008209c  mov     [rbp+0E0h+var_50], rax
0x1800820a3  lea     rcx, [rbp+0E0h+var_A0]
0x1800820a7  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800820ac  jmp     loc_180082DD9
0x1800820b1  test    rsi, rsi
0x1800820b4  jz      short loc_180082135
0x1800820b6  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800820bd  mov     [rbp+0E0h+var_48], 2F1h
0x1800820c8  mov     [rbp+0E0h+var_58], rax
0x1800820cf  lea     rax, aLoadcimentry; "LoadCimEntry"
0x1800820d6  mov     [rbp+0E0h+var_50], rax
0x1800820dd  lea     rax, aDirectorypath; "!DirectoryPath"
0x1800820e4  jmp     short loc_180082119
0x1800820e6  test    rsi, rsi
0x1800820e9  jnz     short loc_180082135
0x1800820eb  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800820f2  mov     [rbp+0E0h+var_48], 2EDh
0x1800820fd  mov     [rbp+0E0h+var_58], rax
0x180082104  lea     rax, aLoadcimentry; "LoadCimEntry"
0x18008210b  mov     [rbp+0E0h+var_50], rax
0x180082112  lea     rax, aDirectorypath_0; "DirectoryPath"
0x180082119  lea     rdx, [rbp+0E0h+var_58]
0x180082120  mov     [rbp+0E0h+var_40], rax
0x180082127  lea     rcx, [rbp+0E0h+var_A0]
0x18008212b  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180082130  jmp     loc_180082DD9
0x180082135  mov     rdx, [r9]; wchar_t *
0x180082138  lea     r8, [rbp+0E0h+var_158]; void **
0x18008213c  mov     rcx, r10; void *
0x18008213f  mov     [rsp+1E0h+var_1B0], r13b
0x180082144  mov     [rbp+0E0h+var_158], r13
0x180082148  call    ?OuOpenKey@@YAJPEAXPEB_WPEAPEAX@Z; OuOpenKey(void *,wchar_t const *,void * *)
0x18008214d  mov     ebx, eax
0x18008214f  test    eax, eax
0x180082151  js      loc_180082DCE
0x180082157  mov     r14, [rbp+0E0h+var_158]
0x18008215b  lea     r9, [rsp+1E0h+var_180]; unsigned int *
0x180082160  mov     rcx, r14; void *
0x180082163  mov     [rsp+1E0h+var_180], r13d
0x180082168  lea     rdx, aIndex; "Index"
0x18008216f  mov     [rsp+1E0h+var_1C0], r13; bool *
0x180082174  call    ?OuGetRegistryDWORD@@YAJPEAXPEB_W1PEAKPEA_N@Z; OuGetRegistryDWORD(void *,wchar_t const *,wchar_t const *,ulong *,bool *)
0x180082179  test    eax, eax
0x18008217b  jns     short loc_180082184
0x18008217d  mov     ebx, eax
0x18008217f  jmp     loc_180082DCE
0x180082184  mov     r15d, [rsp+1E0h+var_180]
0x180082189  mov     eax, 0FFFFFFFFh
0x18008218e  mov     [rsp+1E0h+var_180], r15d
0x180082193  cmp     r15d, eax
0x180082196  jb      short loc_1800821D9
0x180082198  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008219f  mov     [rbp+0E0h+var_68], 30Ah
0x1800821a7  mov     qword ptr [rbp+0E0h+var_78], rax
0x1800821ab  lea     rdx, [rbp+0E0h+var_78]
0x1800821af  lea     rax, aLoadcimentry; "LoadCimEntry"
0x1800821b6  mov     qword ptr [rbp+0E0h+var_78+8], rax
0x1800821ba  lea     rax, aCimindex0xffff; "CimIndex < 0xffffffffUL"
0x1800821c1  mov     [rbp+0E0h+var_60], rax
0x1800821c8  mov     r8d, 0C00000BBh
0x1800821ce  lea     rcx, [rbp+0E0h+var_A0]
0x1800821d2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800821d7  jmp     short loc_18008217D
0x1800821d9  mov     rax, [rdi+8]
0x1800821dd  mov     rcx, 0F0F0F0F0F0F0F0F1h
0x1800821e7  sub     rax, [rdi]
0x1800821ea  mov     rbx, r15
0x1800821ed  sar     rax, 3
0x1800821f1  imul    rax, rcx
0x1800821f5  cmp     rax, r15
0x1800821f8  ja      loc_180082294
0x1800821fe  lea     eax, [r15+1]
0x180082202  mov     rcx, rdi
0x180082205  mov     edx, eax
0x180082207  mov     r15d, eax
0x18008220a  call    ??$_Resize@$$V$0A@@?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Resize<,0>(unsigned __int64)
0x18008220f  test    al, al
0x180082211  jnz     short loc_180082248
0x180082213  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008221a  mov     [rbp+0E0h+var_88], 30Eh
0x180082222  mov     qword ptr [rbp+0E0h+var_98], rax
0x180082226  lea     rdx, [rbp+0E0h+var_98]
0x18008222a  lea     rax, aLoadcimentry; "LoadCimEntry"
0x180082231  mov     r8d, 0C0000017h
0x180082237  mov     qword ptr [rbp+0E0h+var_98+8], rax
0x18008223b  lea     rax, aCimentriesResi; "CimEntries.resize(CimIndex + 1)"
0x180082242  mov     [rbp+0E0h+var_80], rax
0x180082246  jmp     short loc_1800821CE
0x180082248  mov     rdx, r15
0x18008224b  mov     rcx, r12
0x18008224e  call    ??$_Resize@$$V$0A@@?$vector@_NV?$allocator@_N@utl@@@utl@@AEAA_N_K@Z; utl::vector<bool,utl::allocator<bool>>::_Resize<,0>(unsigned __int64)
0x180082253  test    al, al
0x180082255  jnz     short loc_18008228F
0x180082257  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008225e  mov     [rbp+0E0h+var_130], 30Fh
0x180082266  mov     [rbp+0E0h+var_140], rax
0x18008226a  lea     rdx, [rbp+0E0h+var_140]
0x18008226e  lea     rax, aLoadcimentry; "LoadCimEntry"
0x180082275  mov     r8d, 0C0000017h
0x18008227b  mov     [rbp+0E0h+var_138], rax
0x18008227f  lea     rax, aSeencimindexes; "SeenCimIndexes.resize(CimIndex + 1)"
0x180082286  mov     [rbp+0E0h+var_128], rax
0x18008228a  jmp     loc_1800821CE
0x18008228f  mov     r15d, [rsp+1E0h+var_180]
0x180082294  mov     rax, [r12]
0x180082298  cmp     [rbx+rax], r13b
0x18008229c  jz      short loc_1800822D0
0x18008229e  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800822a5  mov     [rbp+0E0h+var_110], 313h
0x1800822ad  mov     [rbp+0E0h+var_120], rax
0x1800822b1  lea     rdx, [rbp+0E0h+var_120]
0x1800822b5  lea     rax, aLoadcimentry; "LoadCimEntry"
0x1800822bc  mov     [rbp+0E0h+var_118], rax
0x1800822c0  lea     rax, aSeencimindexes_1; "SeenCimIndexes[CimIndex]"
0x1800822c7  mov     [rbp+0E0h+var_108], rax
0x1800822cb  jmp     loc_1800821C8
0x1800822d0  mov     r12, [rdi]
0x1800822d3  mov     edi, 1
0x1800822d8  mov     [rbp+0E0h+var_148], r12
0x1800822dc  mov     [rbx+rax], dil
0x1800822e0  mov     [rsp+1E0h+var_178], r13d
0x1800822e5  cmp     [rsp+1E0h+var_168], edi
0x1800822e9  jnz     short loc_18008235C
0x1800822eb  lea     rax, [rsp+1E0h+var_1B0]
0x1800822f0  mov     [rsp+1E0h+var_17C], r13d
0x1800822f5  lea     r9, [rsp+1E0h+var_17C]; unsigned int *
0x1800822fa  mov     [rsp+1E0h+var_1C0], rax; bool *
0x1800822ff  lea     rdx, aProjection; "Projection"
0x180082306  mov     rcx, r14; void *
0x180082309  call    ?OuGetRegistryDWORD@@YAJPEAXPEB_W1PEAKPEA_N@Z; OuGetRegistryDWORD(void *,wchar_t const *,wchar_t const *,ulong *,bool *)
0x18008230e  test    eax, eax
0x180082310  js      loc_18008217D
0x180082316  cmp     [rsp+1E0h+var_17C], r13d
0x18008231b  jz      short loc_18008235C
0x18008231d  test    r15d, r15d
0x180082320  jz      short loc_180082354
0x180082322  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082329  mov     [rbp+0E0h+var_F0], 329h
0x180082331  mov     [rbp+0E0h+var_100], rax
0x180082335  lea     rdx, [rbp+0E0h+var_100]
0x180082339  lea     rax, aLoadcimentry; "LoadCimEntry"
0x180082340  mov     [rbp+0E0h+var_F8], rax
0x180082344  lea     rax, aCimindex0; "CimIndex == 0"
0x18008234b  mov     [rbp+0E0h+var_E8], rax
0x18008234f  jmp     loc_1800821C8
0x180082354  mov     r13b, dil
0x180082357  mov     [rsp+1E0h+var_178], r13d
0x18008235c  test    r15d, r15d
0x18008235f  jnz     short loc_1800823A3
0x180082361  test    r13b, r13b
0x180082364  jnz     short loc_1800823A3
0x180082366  lea     rax, [rsp+1E0h+var_1B0]
0x18008236b  mov     [rsp+1E0h+var_17C], r15d
0x180082370  lea     r9, [rsp+1E0h+var_17C]; int
0x180082375  mov     [rsp+1E0h+var_1C0], rax; bool *
0x18008237a  mov     rcx, r14; int
0x18008237d  call    ??$OuGetAndValidateRegistryEnum@W4OverlayImageFlags@@@@YAJPEAXPEB_W1PEAW4OverlayImageFlags@@PEA_N@Z; OuGetAndValidateRegistryEnum<OverlayImageFlags>(void *,wchar_t const *,wchar_t const *,OverlayImageFlags *,bool *)
0x180082382  test    eax, eax
0x180082384  js      loc_18008217D
0x18008238a  cmp     [rsp+1E0h+var_1B0], r13b
0x18008238f  jnz     short loc_1800823A3
0x180082391  test    byte ptr [rsp+1E0h+var_17C], dil
0x180082396  movzx   r13d, r13b
0x18008239a  cmovnz  r13d, edi
0x18008239e  mov     [rsp+1E0h+var_178], r13d
0x1800823a3  imul    rdi, rbx, 88h
0x1800823aa  mov     [rbp+0E0h+var_150], rdi
0x1800823ae  test    rsi, rsi
0x1800823b1  jz      loc_1800824B6
0x1800823b7  lea     rbx, [r12+38h]
0x1800823bc  mov     rdx, rsi
0x1800823bf  add     rbx, rdi
0x1800823c2  mov     rcx, rbx
0x1800823c5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800823ca  test    al, al
0x1800823cc  jnz     short loc_180082406
0x1800823ce  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800823d5  mov     [rbp+0E0h+var_D0], 341h
0x1800823dd  mov     [rbp+0E0h+var_E0], rax
0x1800823e1  lea     rdx, [rbp+0E0h+var_E0]
0x1800823e5  lea     rax, aLoadcimentry; "LoadCimEntry"
0x1800823ec  mov     r8d, 0C0000017h
0x1800823f2  mov     [rbp+0E0h+var_D8], rax
0x1800823f6  lea     rax, aCimentryAutore_0; "CimEntry.AutoRelativePath.assign(Direct"...
0x1800823fd  mov     [rbp+0E0h+var_C8], rax
0x180082401  jmp     loc_1800821CE
0x180082406  mov     r8d, 1
0x18008240c  lea     rdx, asc_1800AE8E8; "\\"
0x180082413  mov     rcx, rbx
0x180082416  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18008241b  test    al, al
0x18008241d  jnz     short loc_180082457
0x18008241f  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082426  mov     [rbp+0E0h+var_B0], 342h
0x18008242e  mov     [rbp+0E0h+var_C0], rax
0x180082432  lea     rdx, [rbp+0E0h+var_C0]
0x180082436  lea     rax, aLoadcimentry; "LoadCimEntry"
0x18008243d  mov     r8d, 0C0000017h
0x180082443  mov     [rbp+0E0h+var_B8], rax
0x180082447  lea     rax, aCimentryAutore; "CimEntry.AutoRelativePath.append(L\"\\"...
0x18008244e  mov     [rbp+0E0h+var_A8], rax
0x180082452  jmp     loc_1800821CE
0x180082457  mov     rax, [rsp+1E0h+var_188]
0x18008245c  mov     rcx, rbx
0x18008245f  mov     r8, [rax+8]
0x180082463  sub     r8, [rax]
0x180082466  mov     rdx, [rax]
0x180082469  sar     r8, 1
0x18008246c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180082471  test    al, al
0x180082473  jnz     loc_180082532
0x180082479  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082480  mov     [rsp+1E0h+var_198], 343h
0x180082489  mov     [rsp+1E0h+var_1A8], rax
0x18008248e  lea     rax, aLoadcimentry; "LoadCimEntry"
0x180082495  mov     [rsp+1E0h+var_1A0], rax
0x18008249a  lea     rax, aCimentryAutore_1; "CimEntry.AutoRelativePath.append(CimKey"...
0x1800824a1  mov     r8d, 0C0000017h
0x1800824a7  mov     [rsp+1E0h+var_190], rax
0x1800824ac  lea     rdx, [rsp+1E0h+var_1A8]
0x1800824b1  jmp     loc_1800821CE
0x1800824b6  lea     rax, [rbp+0E0h+var_48]
0x1800824bd  mov     rcx, r14
0x1800824c0  mov     [rbp+0E0h+var_58], rax
0x1800824c7  lea     r9, [rbp+0E0h+var_58]
0x1800824ce  lea     rax, [rbp+0E0h+var_48]
0x1800824d5  mov     [rbp+0E0h+var_50], rax
0x1800824dc  xor     eax, eax
0x1800824de  mov     word ptr [rbp+0E0h+var_48], ax
0x1800824e5  lea     rax, [rsp+1E0h+var_1B0]
0x1800824ea  mov     [rsp+1E0h+var_1C0], rax
0x1800824ef  call    ?OuGetRegistrySZ@@YAJPEAXPEB_W1PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_N@Z; OuGetRegistrySZ(void *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool *)
0x1800824f4  mov     ebx, eax
0x1800824f6  test    eax, eax
0x1800824f8  jns     short loc_18008250B
0x1800824fa  lea     rcx, [rbp+0E0h+var_58]
0x180082501  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082506  jmp     loc_180082DCE
0x18008250b  cmp     [rsp+1E0h+var_1B0], 0
0x180082510  jnz     short loc_180082526
0x180082512  lea     rcx, [r12+38h]
0x180082517  add     rcx, rdi
0x18008251a  lea     rdx, [rbp+0E0h+var_58]
0x180082521  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180082526  lea     rcx, [rbp+0E0h+var_58]
0x18008252d  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082532  lea     rax, [rsp+1E0h+var_1B0]
0x180082537  mov     rcx, r14; int
0x18008253a  lea     r15, [rdi+r12]
0x18008253e  mov     [rsp+1E0h+var_1C0], rax; bool *
0x180082543  lea     r9, [r15+4]; int
0x180082547  call    ??$OuGetAndValidateRegistryEnum@W4OverlayCimType@@@@YAJPEAXPEB_W1PEAW4OverlayCimType@@PEA_N@Z; OuGetAndValidateRegistryEnum<OverlayCimType>(void *,wchar_t const *,wchar_t const *,OverlayCimType *,bool *)
0x18008254c  test    eax, eax
0x18008254e  js      loc_18008217D
0x180082554  cmp     [rsp+1E0h+var_1B0], 0
0x180082559  jz      short loc_18008259D
0x18008255b  cmp     [rsp+1E0h+var_168], 1
0x180082560  jz      short loc_180082595
0x180082562  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082569  mov     [rsp+1E0h+var_198], 361h
0x180082572  mov     [rsp+1E0h+var_1A8], rax
0x180082577  lea     rax, aLoadcimentry; "LoadCimEntry"
0x18008257e  mov     [rsp+1E0h+var_1A0], rax
0x180082583  lea     rax, aVersionConfigu; "Version == ConfigurationVersion::V1"
0x18008258a  mov     r8d, 0C00000BBh
0x180082590  jmp     loc_1800824A7
  ... truncated ...
```
