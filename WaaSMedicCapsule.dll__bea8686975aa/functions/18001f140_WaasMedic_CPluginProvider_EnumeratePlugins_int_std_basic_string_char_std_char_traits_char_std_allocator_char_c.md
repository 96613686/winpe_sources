# WaasMedic::CPluginProvider::EnumeratePlugins(int *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,PluginNameAndOrder * *)

- ea: `0x18001f140`
- end: `0x18001fb6e`
- name: `?EnumeratePlugins@CPluginProvider@WaasMedic@@UEAAJPEAHAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAUPluginNameAndOrder@@@Z`
- size: `2606`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003c18`
- `0x1800040b8`
- `0x180009a54`
- `0x18000b9dc`
- `0x18001ead8`
- `0x18001efa0`
- `0x18001f140`
- `0x180020540`
- `0x180020e68`
- `0x180024fc4`
- `0x1800251a8`
- `0x18002543c`
- `0x18002de0c`
- `0x18002e2d0`
- `0x18004b0b0`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f238`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f716`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f238`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f716`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001f35a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001f838`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001f35a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001f838`

## string_xrefs

- `0x18001f41f`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f482`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f4e5`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f548`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f8f7`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f95a`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f9bd`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001fa20`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18001f630`: `Create instance of plugin %s failed. hr = 0x%08x`
- `0x18001fb06`: `Create instance of plugin %s failed. hr = 0x%08x`
- `0x18001f372`: `Conversion of plugin order failed.  Defaulting to 0.  %s`
- `0x18001f850`: `Conversion of plugin order failed.  Defaulting to 0.  %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::CPluginProvider::EnumeratePlugins(__int64 a1, int *a2, __int64 a3, _QWORD *a4)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdx
  bool v8; // r8
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  bool v11; // r8
  _DWORD *v12; // r15
  unsigned __int64 v13; // r12
  __int64 v14; // rdi
  int v15; // eax
  int v16; // eax
  CJsonHelper *v17; // rax
  void *v18; // rdx
  CJsonHelper *v19; // rdi
  int v20; // eax
  int Value__lambda_142bbb5a18063f8f3b48ec9338a7e8dc; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // eax
  void *v25; // rdx
  void *v26; // rdx
  void *v27; // rdx
  void *v28; // rdx
  void *v29; // rdx
  void *v30; // rdx
  void *v31; // rdx
  void *v32; // rdx
  void *v33; // rdx
  void *v34; // rdx
  void *v35; // rdx
  void *v36; // rdx
  void *v37; // rdx
  void *v38; // rdx
  void *v39; // rdx
  void *v40; // rdx
  void *v41; // rdx
  void *v42; // rdx
  void *v43; // rdx
  void *v44; // rdx
  void *v45; // rdx
  void *v46; // rdx
  void *v47; // rdx
  char *v49; // r15
  int v50; // r12d
  int v51; // eax
  char *v52; // r13
  int v53; // eax
  int v54; // eax
  CJsonHelper *v55; // rax
  void *v56; // rdx
  CJsonHelper *v57; // rdi
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  unsigned int v62; // eax
  void *v63; // rdx
  void *v64; // rdx
  void *v65; // rdx
  void *v66; // rdx
  void *v67; // rdx
  void *v68; // rdx
  void *v69; // rdx
  void *v70; // rdx
  void *v71; // rdx
  void *v72; // rdx
  void *v73; // rdx
  void *v74; // rdx
  void *v75; // rdx
  void *v76; // rdx
  void *v77; // rdx
  void *v78; // rdx
  void *v79; // rdx
  void *v80; // rdx
  void *v81; // rdx
  void *v82; // rdx
  void *v83; // rdx
  void *v84; // rdx
  void *v85; // rdx
  WaasMedic *v86; // [rsp+20h] [rbp-49h] BYREF
  WaasMedic *v87; // [rsp+28h] [rbp-41h] BYREF
  WaasMedic *v88; // [rsp+30h] [rbp-39h] BYREF
  WaasMedic **v89; // [rsp+38h] [rbp-31h] BYREF
  const unsigned __int16 ***v90; // [rsp+40h] [rbp-29h] BYREF
  __int64 v91; // [rsp+48h] [rbp-21h] BYREF
  __int64 v92; // [rsp+50h] [rbp-19h]
  CJsonHelper *v93; // [rsp+60h] [rbp-9h]
  WaasMedic **v94; // [rsp+68h] [rbp-1h]
  WaasMedic **v95; // [rsp+70h] [rbp+7h]
  wchar_t **p_String; // [rsp+78h] [rbp+Fh]
  WaasMedic **v97; // [rsp+80h] [rbp+17h]
  char v98; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  wchar_t *String; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v101; // [rsp+E0h] [rbp+77h]

  v101 = a3;
  if ( !a2 || !a4 )
    return 2147500035LL;
  v6 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginContainment_56454451>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginContainment_56454451>::GetImpl'::`2'::impl) )
  {
    WaasMedic::CPluginProvider::GetEffectiveRemediationPlugins(&v91);
    v9 = (v92 - v91) >> 4;
    *a2 = v9;
    v12 = WaasMedic::SafeAlloc((WaasMedic *)(516LL * (int)v9), v10, v11);
    *a4 = v12;
    if ( v12 )
    {
      v13 = 0;
      v14 = v91;
      if ( (v92 - v91) >> 4 )
      {
        while ( 1 )
        {
          v88 = 0;
          v87 = 0;
          v86 = 0;
          String = 0;
          v94 = &v87;
          v95 = &v86;
          p_String = &String;
          v97 = &v88;
          v98 = 1;
          _o_wcscpy_s(&v12[129 * v13], 255, *(_QWORD *)(v14 + 16 * v13));
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, WaasMedic **))(v14 + 16 * v13 + 8))(
                  *(_QWORD *)(v14 + 16 * v13),
                  v101,
                  &v88);
          v6 = v15;
          if ( v15 < 0 )
            break;
          v16 = (*(__int64 (__fastcall **)(WaasMedic *, WaasMedic **))(*(_QWORD *)v88 + 80LL))(v88, &v87);
          v6 = v16;
          if ( v16 < 0 )
          {
            LogLevelW(2u, L"Unable to get default settings for %s. hr = 0x%08x", &v12[129 * v13], (unsigned int)v16);
            WaasMedic::SafeFree(v87, v42);
            WaasMedic::SafeFree(v86, v43);
            WaasMedic::SafeFree((WaasMedic *)String, v44);
            if ( v88 )
              (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
            goto LABEL_42;
          }
          v17 = (CJsonHelper *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
          v19 = v17;
          if ( v17 )
          {
            *(_QWORD *)v17 = 0;
            *((_QWORD *)v17 + 1) = 0;
            *((_QWORD *)v17 + 2) = 0;
            *((_QWORD *)v17 + 3) = 0;
            *((_QWORD *)v17 + 4) = 0;
          }
          else
          {
            v19 = 0;
          }
          v93 = v19;
          if ( !v19 )
          {
            WaasMedic::SafeFree(v87, v18);
            WaasMedic::SafeFree(v86, v40);
            WaasMedic::SafeFree((WaasMedic *)String, v41);
            if ( v88 )
              (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
            goto LABEL_36;
          }
          v20 = CJsonHelper::Init(v19, (const unsigned __int16 *)v87);
          v6 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9F,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
              (const char *)(unsigned int)v20,
              (int)v86);
            CJsonHelper::~CJsonHelper(v19);
            operator delete(v19, (const struct std::nothrow_t *)0x28);
            WaasMedic::SafeFree(v87, v37);
            WaasMedic::SafeFree(v86, v38);
            WaasMedic::SafeFree((WaasMedic *)String, v39);
            if ( v88 )
              (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
            goto LABEL_42;
          }
          v89 = &v86;
          v86 = 0;
          v90 = (const unsigned __int16 ***)&v89;
          Value__lambda_142bbb5a18063f8f3b48ec9338a7e8dc = CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___(
                                                             (__int64 *)v19,
                                                             (HSTRING)L"ORDER",
                                                             (const unsigned __int16 ***)&v90);
          v6 = Value__lambda_142bbb5a18063f8f3b48ec9338a7e8dc;
          if ( Value__lambda_142bbb5a18063f8f3b48ec9338a7e8dc < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA0,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
              (const char *)(unsigned int)Value__lambda_142bbb5a18063f8f3b48ec9338a7e8dc,
              (int)v86);
            CJsonHelper::~CJsonHelper(v19);
            operator delete(v19, (const struct std::nothrow_t *)0x28);
            WaasMedic::SafeFree(v87, v34);
            WaasMedic::SafeFree(v86, v35);
            WaasMedic::SafeFree((WaasMedic *)String, v36);
            if ( v88 )
              (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
            goto LABEL_42;
          }
          v22 = CJsonHelper::Init(v19, (const unsigned __int16 *)v86);
          v6 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA2,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
              (const char *)(unsigned int)v22,
              (int)v86);
            CJsonHelper::~CJsonHelper(v19);
            operator delete(v19, (const struct std::nothrow_t *)0x28);
            WaasMedic::SafeFree(v87, v31);
            WaasMedic::SafeFree(v86, v32);
            WaasMedic::SafeFree((WaasMedic *)String, v33);
            if ( v88 )
              (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
            goto LABEL_42;
          }
          v90 = (const unsigned __int16 ***)&String;
          String = 0;
          v89 = (WaasMedic **)&v90;
          v23 = CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___(
                  (__int64 *)v19,
                  (HSTRING)L"VALUE",
                  (const unsigned __int16 ***)&v89);
          v6 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA3,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
              (const char *)(unsigned int)v23,
              (int)v86);
            CJsonHelper::~CJsonHelper(v19);
            operator delete(v19, (const struct std::nothrow_t *)0x28);
            WaasMedic::SafeFree(v87, v28);
            WaasMedic::SafeFree(v86, v29);
            WaasMedic::SafeFree((WaasMedic *)String, v30);
            if ( v88 )
              (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
            goto LABEL_42;
          }
          v24 = wcstoul(String, 0, 10);
          v12[129 * v13 + 128] = v24;
          if ( !v24 )
            LogLevelW(3u, L"Conversion of plugin order failed.  Defaulting to 0.  %s", String);
          CJsonHelper::~CJsonHelper(v19);
          operator delete(v19, (const struct std::nothrow_t *)0x28);
          WaasMedic::SafeFree(v87, v25);
          WaasMedic::SafeFree(v86, v26);
          WaasMedic::SafeFree((WaasMedic *)String, v27);
          if ( v88 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
          ++v13;
          v14 = v91;
          if ( v13 >= (v92 - v91) >> 4 )
            goto LABEL_21;
        }
        LogLevelW(2u, L"Create instance of plugin %s failed. hr = 0x%08x", &v12[129 * v13], (unsigned int)v15);
        WaasMedic::SafeFree(v87, v45);
        WaasMedic::SafeFree(v86, v46);
        WaasMedic::SafeFree((WaasMedic *)String, v47);
        if ( v88 )
          (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v88 + 16LL))(v88);
      }
      else
      {
LABEL_21:
        std::_Sort_unchecked<PluginNameAndOrder *,bool (*)(PluginNameAndOrder const &,PluginNameAndOrder const &)>(
          v12,
          &v12[129 * *a2],
          0x80FE03F80FE03F81uLL * ((516LL * *a2) >> 2),
          WaasMedic::CPluginProvider::ComparePlugins);
      }
    }
    else
    {
LABEL_36:
      v6 = -2147024882;
    }
LABEL_42:
    std::vector<WaasMedic::tagPluginRegistrationInfo>::~vector<WaasMedic::tagPluginRegistrationInfo>(&v91);
    return v6;
  }
  *a2 = 15;
  v49 = (char *)WaasMedic::SafeAlloc((WaasMedic *)0x1E3C, v7, v8);
  *a4 = v49;
  if ( v49 )
  {
    v50 = 0;
    v51 = *a2;
    if ( *a2 <= 0 )
    {
LABEL_62:
      std::_Sort_unchecked<PluginNameAndOrder *,bool (*)(PluginNameAndOrder const &,PluginNameAndOrder const &)>(
        v49,
        &v49[516 * v51],
        0x80FE03F80FE03F81uLL * ((516LL * v51) >> 2),
        WaasMedic::CPluginProvider::ComparePlugins);
    }
    else
    {
      while ( 1 )
      {
        v87 = 0;
        v88 = 0;
        v86 = 0;
        String = 0;
        v94 = &v88;
        v95 = &v86;
        p_String = &String;
        v97 = &v87;
        v98 = 1;
        v52 = &v49[516 * v50];
        _o_wcscpy_s(v52, 255, (&off_180065310)[2 * v50]);
        v53 = ((__int64 (__fastcall *)(wchar_t *, __int64, WaasMedic **))*(&funcs_18001F72D + 2 * v50))(
                (&off_180065310)[2 * v50],
                v101,
                &v87);
        v6 = v53;
        if ( v53 < 0 )
          break;
        v54 = (*(__int64 (__fastcall **)(WaasMedic *, WaasMedic **))(*(_QWORD *)v87 + 80LL))(v87, &v88);
        v6 = v54;
        if ( v54 < 0 )
        {
          LogLevelW(2u, L"Unable to get default settings for %s. hr = 0x%08x", v52, (unsigned int)v54);
          WaasMedic::SafeFree(v88, v80);
          WaasMedic::SafeFree(v86, v81);
          WaasMedic::SafeFree((WaasMedic *)String, v82);
          if ( v87 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
          return v6;
        }
        v55 = (CJsonHelper *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
        v57 = v55;
        if ( v55 )
        {
          *(_QWORD *)v55 = 0;
          *((_QWORD *)v55 + 1) = 0;
          *((_QWORD *)v55 + 2) = 0;
          *((_QWORD *)v55 + 3) = 0;
          *((_QWORD *)v55 + 4) = 0;
        }
        else
        {
          v57 = 0;
        }
        v93 = v57;
        if ( !v57 )
        {
          WaasMedic::SafeFree(v88, v56);
          WaasMedic::SafeFree(v86, v78);
          WaasMedic::SafeFree((WaasMedic *)String, v79);
          if ( v87 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
          return 2147942414LL;
        }
        v58 = CJsonHelper::Init(v57, (const unsigned __int16 *)v88);
        v6 = v58;
        if ( v58 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
            (const char *)(unsigned int)v58,
            (int)v86);
          CJsonHelper::~CJsonHelper(v57);
          operator delete(v57, (const struct std::nothrow_t *)0x28);
          WaasMedic::SafeFree(v88, v75);
          WaasMedic::SafeFree(v86, v76);
          WaasMedic::SafeFree((WaasMedic *)String, v77);
          if ( v87 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
          return v6;
        }
        v90 = (const unsigned __int16 ***)&v86;
        v86 = 0;
        v89 = (WaasMedic **)&v90;
        v59 = CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___(
                (__int64 *)v57,
                (HSTRING)L"ORDER",
                (const unsigned __int16 ***)&v89);
        v6 = v59;
        if ( v59 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDF,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
            (const char *)(unsigned int)v59,
            (int)v86);
          CJsonHelper::~CJsonHelper(v57);
          operator delete(v57, (const struct std::nothrow_t *)0x28);
          WaasMedic::SafeFree(v88, v72);
          WaasMedic::SafeFree(v86, v73);
          WaasMedic::SafeFree((WaasMedic *)String, v74);
          if ( v87 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
          return v6;
        }
        v60 = CJsonHelper::Init(v57, (const unsigned __int16 *)v86);
        v6 = v60;
        if ( v60 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE1,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
            (const char *)(unsigned int)v60,
            (int)v86);
          CJsonHelper::~CJsonHelper(v57);
          operator delete(v57, (const struct std::nothrow_t *)0x28);
          WaasMedic::SafeFree(v88, v69);
          WaasMedic::SafeFree(v86, v70);
          WaasMedic::SafeFree((WaasMedic *)String, v71);
          if ( v87 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
          return v6;
        }
        v90 = (const unsigned __int16 ***)&String;
        String = 0;
        v89 = (WaasMedic **)&v90;
        v61 = CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___(
                (__int64 *)v57,
                (HSTRING)L"VALUE",
                (const unsigned __int16 ***)&v89);
        v6 = v61;
        if ( v61 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE2,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
            (const char *)(unsigned int)v61,
            (int)v86);
          CJsonHelper::~CJsonHelper(v57);
          operator delete(v57, (const struct std::nothrow_t *)0x28);
          WaasMedic::SafeFree(v88, v66);
          WaasMedic::SafeFree(v86, v67);
          WaasMedic::SafeFree((WaasMedic *)String, v68);
          if ( v87 )
            (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
          return v6;
        }
        v62 = wcstoul(String, 0, 10);
        *((_DWORD *)v52 + 128) = v62;
        if ( !v62 )
          LogLevelW(3u, L"Conversion of plugin order failed.  Defaulting to 0.  %s", String);
        CJsonHelper::~CJsonHelper(v57);
        operator delete(v57, (const struct std::nothrow_t *)0x28);
        WaasMedic::SafeFree(v88, v63);
        WaasMedic::SafeFree(v86, v64);
        WaasMedic::SafeFree((WaasMedic *)String, v65);
        if ( v87 )
          (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
        ++v50;
        v51 = *a2;
        if ( v50 >= *a2 )
          goto LABEL_62;
      }
      LogLevelW(2u, L"Create instance of plugin %s failed. hr = 0x%08x", v52, (unsigned int)v53);
      WaasMedic::SafeFree(v88, v83);
      WaasMedic::SafeFree(v86, v84);
      WaasMedic::SafeFree((WaasMedic *)String, v85);
      if ( v87 )
        (*(void (__fastcall **)(WaasMedic *))(*(_QWORD *)v87 + 16LL))(v87);
    }
    return v6;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001f140  mov     [rsp-8+arg_0], rbx
0x18001f145  mov     [rsp-8+arg_10], r8
0x18001f14a  push    rbp
0x18001f14b  push    rsi
0x18001f14c  push    rdi
0x18001f14d  push    r12
0x18001f14f  push    r13
0x18001f151  push    r14
0x18001f153  push    r15
0x18001f155  lea     rbp, [rsp-27h]
0x18001f15a  sub     rsp, 90h
0x18001f161  mov     rdi, r9
0x18001f164  mov     r14, rdx
0x18001f167  xor     r13d, r13d
0x18001f16a  test    rdx, rdx
0x18001f16d  jz      loc_18001FB4E
0x18001f173  test    r9, r9
0x18001f176  jz      loc_18001FB4E
0x18001f17c  mov     ebx, r13d
0x18001f17f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginContainment_56454451@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginContainment_56454451@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginContainment_56454451> `wil::Feature<__WilFeatureTraits_Feature_PluginContainment_56454451>::GetImpl(void)'::`2'::impl
0x18001f186  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginContainment_56454451@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginContainment_56454451>::__private_IsEnabled(void)
0x18001f18b  test    al, al
0x18001f18d  jz      loc_18001F683
0x18001f193  lea     rcx, [rbp+57h+var_78]
0x18001f197  call    ?GetEffectiveRemediationPlugins@CPluginProvider@WaasMedic@@SA?AV?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@XZ; WaasMedic::CPluginProvider::GetEffectiveRemediationPlugins(void)
0x18001f19c  nop
0x18001f19d  mov     rax, [rbp+57h+var_70]
0x18001f1a1  sub     rax, [rbp+57h+var_78]
0x18001f1a5  sar     rax, 4
0x18001f1a9  mov     [r14], eax
0x18001f1ac  cdqe
0x18001f1ae  imul    rcx, rax, 204h; this
0x18001f1b5  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x18001f1ba  mov     r15, rax
0x18001f1bd  mov     [rdi], rax
0x18001f1c0  test    rax, rax
0x18001f1c3  jz      loc_18001F5D5
0x18001f1c9  mov     r12d, r13d
0x18001f1cc  mov     rax, [rbp+57h+var_70]
0x18001f1d0  mov     rdi, [rbp+57h+var_78]
0x18001f1d4  sub     rax, rdi
0x18001f1d7  sar     rax, 4
0x18001f1db  test    rax, rax
0x18001f1de  jz      loc_18001F3E2
0x18001f1e4  lea     esi, [r13+28h]
0x18001f1e8  mov     rbx, r12
0x18001f1eb  add     rbx, rbx
0x18001f1ee  mov     [rbp+57h+var_90], r13
0x18001f1f2  mov     [rbp+57h+var_98], r13
0x18001f1f6  mov     [rbp+57h+var_A0], r13
0x18001f1fa  mov     [rbp+57h+String], r13
0x18001f1fe  lea     rax, [rbp+57h+var_98]
0x18001f202  mov     [rbp+57h+var_58], rax
0x18001f206  lea     rax, [rbp+57h+var_A0]
0x18001f20a  mov     [rbp+57h+var_50], rax
0x18001f20e  lea     rax, [rbp+57h+String]
0x18001f212  mov     [rbp+57h+var_48], rax
0x18001f216  lea     rax, [rbp+57h+var_90]
0x18001f21a  mov     [rbp+57h+var_40], rax
0x18001f21e  mov     [rbp+57h+var_38], 1
0x18001f222  imul    r13, r12, 204h
0x18001f229  add     r13, r15
0x18001f22c  mov     r8, [rdi+rbx*8]
0x18001f230  mov     edx, 0FFh
0x18001f235  mov     rcx, r13
0x18001f238  call    cs:__imp__o_wcscpy_s
0x18001f23e  lea     r8, [rbp+57h+var_90]
0x18001f242  mov     rdx, [rbp+57h+arg_10]
0x18001f246  mov     rcx, [rdi+rbx*8]
0x18001f24a  mov     rax, [rdi+rbx*8+8]
0x18001f24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f254  mov     ebx, eax
0x18001f256  test    eax, eax
0x18001f258  js      loc_18001F62A
0x18001f25e  mov     rcx, [rbp+57h+var_90]
0x18001f262  mov     rax, [rcx]
0x18001f265  lea     rdx, [rbp+57h+var_98]
0x18001f269  mov     rax, [rax+50h]
0x18001f26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f272  mov     ebx, eax
0x18001f274  test    eax, eax
0x18001f276  js      loc_18001F5DF
0x18001f27c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f283  mov     rcx, rsi; unsigned __int64
0x18001f286  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f28b  mov     rdi, rax
0x18001f28e  xor     ebx, ebx
0x18001f290  test    rax, rax
0x18001f293  jz      short loc_18001F2AA
0x18001f295  mov     [rax], rbx
0x18001f298  mov     [rax+8], rbx
0x18001f29c  mov     [rax+10h], rbx
0x18001f2a0  mov     [rax+18h], rbx
0x18001f2a4  mov     [rax+20h], rbx
0x18001f2a8  jmp     short loc_18001F2AD
0x18001f2aa  mov     rdi, rbx
0x18001f2ad  mov     [rbp+57h+var_60], rdi
0x18001f2b1  test    rdi, rdi
0x18001f2b4  jz      loc_18001F5A4
0x18001f2ba  mov     rdx, [rbp+57h+var_98]; unsigned __int16 *
0x18001f2be  mov     rcx, rdi; this
0x18001f2c1  call    ?Init@CJsonHelper@@QEAAJPEBG@Z; CJsonHelper::Init(ushort const *)
0x18001f2c6  mov     ebx, eax
0x18001f2c8  test    eax, eax
0x18001f2ca  js      loc_18001F541
0x18001f2d0  lea     rax, [rbp+57h+var_A0]
0x18001f2d4  mov     [rbp+57h+var_88], rax
0x18001f2d8  mov     [rbp+57h+var_A0], 0
0x18001f2e0  lea     rax, [rbp+57h+var_88]
0x18001f2e4  mov     [rbp+57h+var_80], rax
0x18001f2e8  lea     r8, [rbp+57h+var_80]
0x18001f2ec  lea     rdx, aOrder; "ORDER"
0x18001f2f3  mov     rcx, rdi
0x18001f2f6  call    CJsonHelper___GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___
0x18001f2fb  mov     ebx, eax
0x18001f2fd  test    eax, eax
0x18001f2ff  js      loc_18001F4DE
0x18001f305  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18001f309  mov     rcx, rdi; this
0x18001f30c  call    ?Init@CJsonHelper@@QEAAJPEBG@Z; CJsonHelper::Init(ushort const *)
0x18001f311  mov     ebx, eax
0x18001f313  test    eax, eax
0x18001f315  js      loc_18001F47B
0x18001f31b  lea     rax, [rbp+57h+String]
0x18001f31f  mov     [rbp+57h+var_80], rax
0x18001f323  mov     [rbp+57h+String], 0
0x18001f32b  lea     rax, [rbp+57h+var_80]
0x18001f32f  mov     [rbp+57h+var_88], rax
0x18001f333  lea     r8, [rbp+57h+var_88]
0x18001f337  lea     rdx, aValue; "VALUE"
0x18001f33e  mov     rcx, rdi
0x18001f341  call    CJsonHelper___GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___
0x18001f346  mov     ebx, eax
0x18001f348  test    eax, eax
0x18001f34a  js      loc_18001F418
0x18001f350  xor     edx, edx; EndPtr
0x18001f352  lea     r8d, [rdx+0Ah]; Radix
0x18001f356  mov     rcx, [rbp+57h+String]; String
0x18001f35a  call    cs:__imp_wcstoul
0x18001f360  mov     [r13+200h], eax
0x18001f367  xor     r13d, r13d
0x18001f36a  test    eax, eax
0x18001f36c  jnz     short loc_18001F382
0x18001f36e  mov     r8, [rbp+57h+String]
0x18001f372  lea     rdx, aConversionOfPl; "Conversion of plugin order failed.  Def"...
0x18001f379  lea     ecx, [rax+3]; unsigned __int8
0x18001f37c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001f381  nop
0x18001f382  mov     rcx, rdi; this
0x18001f385  call    ??1CJsonHelper@@QEAA@XZ; CJsonHelper::~CJsonHelper(void)
0x18001f38a  mov     rdx, rsi; struct std::nothrow_t *
0x18001f38d  mov     rcx, rdi; void *
0x18001f390  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f395  nop
0x18001f396  mov     rcx, [rbp+57h+var_98]; this
0x18001f39a  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f39f  mov     rcx, [rbp+57h+var_A0]; this
0x18001f3a3  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f3a8  mov     rcx, [rbp+57h+String]; this
0x18001f3ac  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f3b1  mov     rcx, [rbp+57h+var_90]
0x18001f3b5  test    rcx, rcx
0x18001f3b8  jz      short loc_18001F3C7
0x18001f3ba  mov     rax, [rcx]
0x18001f3bd  mov     rax, [rax+10h]
0x18001f3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3c6  nop
0x18001f3c7  inc     r12
0x18001f3ca  mov     rax, [rbp+57h+var_70]
0x18001f3ce  mov     rdi, [rbp+57h+var_78]
0x18001f3d2  sub     rax, rdi
0x18001f3d5  sar     rax, 4
0x18001f3d9  cmp     r12, rax
0x18001f3dc  jb      loc_18001F1E8
0x18001f3e2  movsxd  rax, dword ptr [r14]
0x18001f3e5  imul    rdx, rax, 204h
0x18001f3ec  mov     r8, rdx
0x18001f3ef  sar     r8, 2
0x18001f3f3  mov     rax, 80FE03F80FE03F81h
0x18001f3fd  imul    r8, rax
0x18001f401  add     rdx, r15
0x18001f404  lea     r9, ?ComparePlugins@CPluginProvider@WaasMedic@@CA_NAEBUPluginNameAndOrder@@0@Z; WaasMedic::CPluginProvider::ComparePlugins(PluginNameAndOrder const &,PluginNameAndOrder const &)
0x18001f40b  mov     rcx, r15
0x18001f40e  call    ??$_Sort_unchecked@PEAUPluginNameAndOrder@@P6A_NAEBU1@0@Z@std@@YAXPEAUPluginNameAndOrder@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PluginNameAndOrder *,bool (*)(PluginNameAndOrder const &,PluginNameAndOrder const &)>(PluginNameAndOrder *,PluginNameAndOrder *,__int64,bool (*)(PluginNameAndOrder const &,PluginNameAndOrder const &))
0x18001f413  jmp     loc_18001F673
0x18001f418  mov     rcx, [rbp+5Fh]; this
0x18001f41c  mov     r9d, eax; char *
0x18001f41f  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x18001f426  mov     edx, 0A3h; void *
0x18001f42b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f430  nop
0x18001f431  mov     rcx, rdi; this
0x18001f434  call    ??1CJsonHelper@@QEAA@XZ; CJsonHelper::~CJsonHelper(void)
0x18001f439  mov     rdx, rsi; struct std::nothrow_t *
0x18001f43c  mov     rcx, rdi; void *
0x18001f43f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f444  nop
0x18001f445  mov     rcx, [rbp+57h+var_98]; this
0x18001f449  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f44e  mov     rcx, [rbp+57h+var_A0]; this
0x18001f452  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f457  mov     rcx, [rbp+57h+String]; this
0x18001f45b  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f460  mov     rcx, [rbp+57h+var_90]
0x18001f464  test    rcx, rcx
0x18001f467  jz      short loc_18001F476
0x18001f469  mov     rax, [rcx]
0x18001f46c  mov     rax, [rax+10h]
0x18001f470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f475  nop
0x18001f476  jmp     loc_18001F673
0x18001f47b  mov     rcx, [rbp+5Fh]; this
0x18001f47f  mov     r9d, eax; char *
0x18001f482  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x18001f489  mov     edx, 0A2h; void *
0x18001f48e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f493  nop
0x18001f494  mov     rcx, rdi; this
0x18001f497  call    ??1CJsonHelper@@QEAA@XZ; CJsonHelper::~CJsonHelper(void)
0x18001f49c  mov     rdx, rsi; struct std::nothrow_t *
0x18001f49f  mov     rcx, rdi; void *
0x18001f4a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f4a7  nop
0x18001f4a8  mov     rcx, [rbp+57h+var_98]; this
0x18001f4ac  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f4b1  mov     rcx, [rbp+57h+var_A0]; this
0x18001f4b5  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f4ba  mov     rcx, [rbp+57h+String]; this
0x18001f4be  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f4c3  mov     rcx, [rbp+57h+var_90]
0x18001f4c7  test    rcx, rcx
0x18001f4ca  jz      short loc_18001F4D9
0x18001f4cc  mov     rax, [rcx]
0x18001f4cf  mov     rax, [rax+10h]
0x18001f4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4d8  nop
0x18001f4d9  jmp     loc_18001F673
0x18001f4de  mov     rcx, [rbp+5Fh]; this
0x18001f4e2  mov     r9d, eax; char *
0x18001f4e5  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x18001f4ec  mov     edx, 0A0h; void *
0x18001f4f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4f6  nop
0x18001f4f7  mov     rcx, rdi; this
0x18001f4fa  call    ??1CJsonHelper@@QEAA@XZ; CJsonHelper::~CJsonHelper(void)
0x18001f4ff  mov     rdx, rsi; struct std::nothrow_t *
0x18001f502  mov     rcx, rdi; void *
0x18001f505  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f50a  nop
0x18001f50b  mov     rcx, [rbp+57h+var_98]; this
0x18001f50f  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f514  mov     rcx, [rbp+57h+var_A0]; this
0x18001f518  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f51d  mov     rcx, [rbp+57h+String]; this
0x18001f521  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f526  mov     rcx, [rbp+57h+var_90]
0x18001f52a  test    rcx, rcx
0x18001f52d  jz      short loc_18001F53C
0x18001f52f  mov     rax, [rcx]
0x18001f532  mov     rax, [rax+10h]
0x18001f536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f53b  nop
0x18001f53c  jmp     loc_18001F673
0x18001f541  mov     rcx, [rbp+5Fh]; this
0x18001f545  mov     r9d, eax; char *
0x18001f548  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x18001f54f  mov     edx, 9Fh; void *
0x18001f554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f559  nop
0x18001f55a  mov     rcx, rdi; this
0x18001f55d  call    ??1CJsonHelper@@QEAA@XZ; CJsonHelper::~CJsonHelper(void)
0x18001f562  mov     rdx, rsi; struct std::nothrow_t *
0x18001f565  mov     rcx, rdi; void *
0x18001f568  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f56d  nop
0x18001f56e  mov     rcx, [rbp+57h+var_98]; this
0x18001f572  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f577  mov     rcx, [rbp+57h+var_A0]; this
0x18001f57b  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f580  mov     rcx, [rbp+57h+String]; this
0x18001f584  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f589  mov     rcx, [rbp+57h+var_90]
0x18001f58d  test    rcx, rcx
0x18001f590  jz      short loc_18001F59F
0x18001f592  mov     rax, [rcx]
0x18001f595  mov     rax, [rax+10h]
0x18001f599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59e  nop
0x18001f59f  jmp     loc_18001F673
0x18001f5a4  mov     rcx, [rbp+57h+var_98]; this
0x18001f5a8  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f5ad  mov     rcx, [rbp+57h+var_A0]; this
0x18001f5b1  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f5b6  mov     rcx, [rbp+57h+String]; this
0x18001f5ba  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18001f5bf  mov     rcx, [rbp+57h+var_90]
0x18001f5c3  test    rcx, rcx
0x18001f5c6  jz      short loc_18001F5D5
0x18001f5c8  mov     rax, [rcx]
0x18001f5cb  mov     rax, [rax+10h]
  ... truncated ...
```
