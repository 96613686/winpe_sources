# CTnoCfgMgr::RefreshRegistrySettings(HKEY__ *,bool)

- ea: `0x1800245ac`
- end: `0x1800251b0`
- name: `?RefreshRegistrySettings@CTnoCfgMgr@@IEAAJPEAUHKEY__@@_N@Z`
- size: `3076`
- prototype: `__int64 __fastcall(CTnoCfgMgr *__hidden this, HKEY, bool)`
- caller_count: `4`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021370`
- `0x180021f90`
- `0x1800265b0`
- `0x180027bfc`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18000cf48`
- `0x180015264`
- `0x1800183a0`
- `0x18001844c`
- `0x1800205f8`
- `0x1800206d0`
- `0x180020a38`
- `0x18002118c`
- `0x180021310`
- `0x180022488`
- `0x180022ea0`
- `0x1800245ac`
- `0x180025f38`
- `0x18002606c`
- `0x180026354`
- `0x180026724`
- `0x180028518`
- `0x180028558`
- `0x1800288f4`
- `0x1800289d0`
- `0x180028d7c`
- `0x180028fa0`
- `0x1800290ac`
- `0x1800291b8`
- `0x1800292dc`
- `0x180144876`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800246d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800246d3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024974`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024b10`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024974`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024b10`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CTnoCfgMgr::RefreshRegistrySettings(CTnoCfgMgr *this, HKEY a2)
{
  unsigned int v3; // edi
  struct ITnoLoggingMgr *v4; // rax
  char v5; // cl
  char *v6; // r14
  CTnoCfgMgr *v7; // rcx
  HKEY v8; // rbx
  unsigned int i; // ebx
  const struct cfg_mgr_reg_defaults_tag near *const *v10; // r14
  unsigned int v11; // r15d
  char v12; // di
  int ServiceModeSettingType; // edi
  __int64 v15; // rax
  const struct cfg_mgr_reg_defaults_tag near *const *v16; // r13
  const size_t *v17; // rax
  const WCHAR *v18; // r14
  const WCHAR *v19; // r15
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  HKEY v23; // rcx
  LSTATUS ValueW; // eax
  LSTATUS v25; // ebx
  CHostedCacheMsgEncoding *v26; // rcx
  LSTATUS v27; // eax
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r11
  const WCHAR *v31; // r8
  unsigned int v32; // eax
  struct ITnoLoggingMgr *v33; // rdi
  _QWORD *v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // r11
  bool v37; // zf
  unsigned int v38; // edx
  unsigned int v39; // eax
  unsigned int v40; // r11d
  _QWORD *v41; // rbx
  int v42; // r11d
  int v43; // eax
  unsigned int v44; // edi
  _QWORD *v45; // rbx
  unsigned int v46; // eax
  int v47; // eax
  const size_t *v48; // rdx
  __int64 v49; // r8
  int v50; // edx
  _QWORD *v51; // r11
  char *v52; // r14
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // r8d
  DWORD pcbData; // [rsp+40h] [rbp-418h] BYREF
  unsigned int v57; // [rsp+44h] [rbp-414h]
  const unsigned __int16 *v58; // [rsp+48h] [rbp-410h]
  int v59; // [rsp+50h] [rbp-408h] BYREF
  DWORD pdwType; // [rsp+54h] [rbp-404h] BYREF
  int v61; // [rsp+58h] [rbp-400h]
  int v62; // [rsp+5Ch] [rbp-3FCh]
  int v63; // [rsp+60h] [rbp-3F8h]
  HKEY phkResult; // [rsp+68h] [rbp-3F0h] BYREF
  HKEY v65; // [rsp+70h] [rbp-3E8h] BYREF
  struct ITnoLoggingMgr *v66; // [rsp+78h] [rbp-3E0h]
  char *v67; // [rsp+80h] [rbp-3D8h]
  const struct cfg_mgr_reg_defaults_tag near *const *v68; // [rsp+88h] [rbp-3D0h]
  char *v69; // [rsp+90h] [rbp-3C8h]
  __int64 v70; // [rsp+98h] [rbp-3C0h]
  __int64 v71; // [rsp+A0h] [rbp-3B8h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-3B0h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-3A8h] BYREF
  const size_t *v74; // [rsp+B8h] [rbp-3A0h]
  __int64 v75; // [rsp+C0h] [rbp-398h] BYREF
  _BYTE v76[24]; // [rsp+C8h] [rbp-390h] BYREF
  char v77; // [rsp+E0h] [rbp-378h] BYREF
  int v78; // [rsp+F0h] [rbp-368h] BYREF
  __int16 v79[8]; // [rsp+F8h] [rbp-360h] BYREF
  __int64 v80; // [rsp+108h] [rbp-350h]
  __int64 v81; // [rsp+110h] [rbp-348h]
  __int16 v82[8]; // [rsp+118h] [rbp-340h] BYREF
  __int64 v83; // [rsp+128h] [rbp-330h]
  __int64 v84; // [rsp+130h] [rbp-328h]
  unsigned int v85; // [rsp+138h] [rbp-320h]
  unsigned __int64 v86; // [rsp+140h] [rbp-318h]
  _WORD v87[8]; // [rsp+148h] [rbp-310h] BYREF
  __int64 v88; // [rsp+158h] [rbp-300h]
  __int64 v89; // [rsp+160h] [rbp-2F8h]
  __int64 v90; // [rsp+168h] [rbp-2F0h]
  int v91; // [rsp+170h] [rbp-2E8h]
  char v92[8]; // [rsp+180h] [rbp-2D8h] BYREF
  char v93[136]; // [rsp+188h] [rbp-2D0h] BYREF
  char pvData[528]; // [rsp+210h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 74, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
  }
  v3 = 0;
  v62 = 0;
  pdwType = 0;
  v4 = 0;
  phkResult = 0;
  v65 = 0;
  v59 = 1;
  if ( *((_DWORD *)this + 16) == 3 )
    v4 = (struct ITnoLoggingMgr *)ITnoLoggingMgr::s_spLoggingMgr;
  v66 = v4;
  InCritSec::InCritSec((InCritSec *)v76, this, 1);
  v70 = *((_QWORD *)this + 40);
  v5 = *((_BYTE *)this + 336);
  v67 = (char *)this + (-(__int64)(v5 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 360;
  v6 = (char *)this + 360;
  if ( !v5 )
    v6 = (char *)this + 344;
  v69 = v6;
  std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::clear(v6);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\PeerDist", 0, 0x20119u, &phkResult) )
  {
    phkResult = 0;
  }
  else
  {
    v8 = phkResult;
    AutoRegKey::Close((AutoRegKey *)&v65);
    v65 = v8;
  }
  for ( i = 0; ; ++i )
  {
    v57 = i;
    if ( i >= 2 )
      break;
    if ( !i )
    {
      v11 = 183;
      v61 = 183;
      v10 = &c_Cfg_Mgr_Reg_Settings;
      v68 = &c_Cfg_Mgr_Reg_Settings;
      ServiceModeSettingType = CTnoCfgMgr::GetServiceModeSettingType(v7, phkResult, (enum _CFGMGR_SETTING_TYPE *)&v59);
      v62 = ServiceModeSettingType;
      if ( ServiceModeSettingType < 0 )
      {
        InCritSec::~InCritSec((InCritSec *)v76);
        AutoRegKey::Close((AutoRegKey *)&v65);
        return (unsigned int)ServiceModeSettingType;
      }
      v12 = 0;
LABEL_20:
      v15 = 0;
LABEL_21:
      v63 = v15;
      if ( (unsigned int)v15 >= v11 )
      {
        v3 = v62;
        continue;
      }
      v16 = &v10[10 * v15];
      memset_0(pvData, 0, 0x208u);
      pcbData = 0;
      v78 = 0;
      v81 = 7;
      v80 = 0;
      v79[0] = 0;
      v84 = 7;
      v83 = 0;
      v82[0] = 0;
      v85 = 0;
      v86 = 0;
      v89 = 7;
      v88 = 0;
      v87[0] = 0;
      v90 = 0;
      v17 = &dword_1801747C4;
      v18 = (const WCHAR *)&dword_1801747C4;
      if ( *((_QWORD *)v16 + 1) )
        v18 = (const WCHAR *)*((_QWORD *)v16 + 1);
      v19 = (const WCHAR *)&dword_1801747C4;
      if ( *((_QWORD *)v16 + 2) )
        v19 = (const WCHAR *)*((_QWORD *)v16 + 2);
      if ( *((_QWORD *)v16 + 6) )
        v17 = (const size_t *)*((_QWORD *)v16 + 6);
      v74 = v17;
      if ( !*(_DWORD *)v16 )
        goto LABEL_166;
      v78 = *(_DWORD *)v16;
      if ( *v18 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v18[v20] );
      }
      std::wstring::assign(v79);
      if ( *v19 )
      {
        v21 = -1;
        do
          ++v21;
        while ( v19[v21] );
      }
      v58 = L"UNKNOWN";
      std::wstring::assign(v82);
      v85 = *((_DWORD *)v16 + 6);
      v22 = 0;
      v91 = 0;
      if ( !*v18 || !*v19 || i )
      {
        v26 = WPP_GLOBAL_Control;
        goto LABEL_73;
      }
      if ( !phkResult || (unsigned __int8)CTnoCfgMgr::IsServiceModeValue(phkResult, *(unsigned int *)v16) && v59 != 2 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            77,
            (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
            (unsigned int)L"Software\\Policies\\Microsoft\\PeerDist",
            144);
          v26 = WPP_GLOBAL_Control;
          v22 = 0;
        }
        goto LABEL_61;
      }
      pcbData = 520;
      ValueW = RegGetValueW(v23, v18, v19, 0x1000FFFFu, &pdwType, pvData, &pcbData);
      v25 = ValueW;
      v22 = 0;
      if ( ValueW )
      {
        if ( ValueW != 2 && ValueW != 1168 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_DSSS(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              76,
              0,
              ValueW,
              (__int64)v19,
              (__int64)L"Software\\Policies\\Microsoft\\PeerDist",
              (__int64)v18);
            goto LABEL_48;
          }
LABEL_55:
          if ( v25 )
          {
LABEL_61:
            if ( v70 == v22 || (unsigned __int8)CTnoCfgMgr::IsServiceModeValue(v26, *(unsigned int *)v16) && v59 != 1 )
              goto LABEL_73;
            pcbData = 520;
            v27 = RegGetValueW(*((HKEY *)this + 40), v18, v19, 0x1000FFFFu, &pdwType, pvData, &pcbData);
            v22 = 0;
            if ( v27 )
            {
              if ( v27 != 2 && v27 != 1168 )
              {
                v26 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  WPP_SF_DSSS(
                    *((_QWORD *)WPP_GLOBAL_Control + 12),
                    79,
                    (unsigned int)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
                    v27,
                    (__int64)v19,
                    (__int64)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
                    (__int64)v18);
                  goto LABEL_71;
                }
LABEL_73:
                if ( *((_DWORD *)v16 + 6) == 1 || *((_DWORD *)v16 + 6) == 2 )
                {
                  v48 = (const size_t *)pvData;
                  if ( !v12 )
                    v48 = v74;
                  if ( *(_WORD *)v48 != (_WORD)v22 )
                  {
                    v49 = -1;
                    do
                      ++v49;
                    while ( *((_WORD *)v48 + v49) );
                  }
                  std::wstring::assign(v87);
                  if ( v12
                    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
                  {
                    WPP_SF_SSSS(
                      *((_QWORD *)WPP_GLOBAL_Control + 12),
                      v50,
                      v22,
                      (_DWORD)v19,
                      (__int64)pvData,
                      (__int64)v58,
                      (__int64)v18);
                  }
                  v33 = v66;
                  if ( !v66 )
                    goto LABEL_165;
                  std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::find(
                    v67,
                    &v75,
                    &v78);
                  if ( v75 == *v51 )
                    goto LABEL_165;
                  v47 = std::wstring::compare(v75 + 128, v87);
                }
                else
                {
                  if ( *((_DWORD *)v16 + 6) != 3 )
                  {
                    if ( *((_DWORD *)v16 + 6) != 4 )
                    {
                      if ( *((_DWORD *)v16 + 6) == 11 )
                      {
                        v28 = *((_QWORD *)v16 + 8);
                        v29 = *((_QWORD *)v16 + 9);
                        v22 = *(_QWORD *)pvData;
                        v30 = *(_QWORD *)pvData;
                        if ( !v12 )
                          v30 = *((_QWORD *)v16 + 5);
                        if ( *((_DWORD *)v16 + 7) )
                        {
                          if ( (__int64)v29 < (__int64)v30 )
                            v30 = *((_QWORD *)v16 + 9);
                          if ( (__int64)v30 < (__int64)v28 )
                            v30 = *((_QWORD *)v16 + 8);
                        }
                        else
                        {
                          if ( v29 < v30 )
                            v30 = *((_QWORD *)v16 + 9);
                          if ( v30 < v28 )
                            v30 = *((_QWORD *)v16 + 8);
                        }
                        v86 = v30;
                        if ( v12
                          && v26 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)v26 + 27) & 0x200) != 0
                          && *((_BYTE *)v26 + 105) >= 3u )
                        {
                          WPP_SF_SISS(
                            *((_QWORD *)v26 + 12),
                            v28,
                            *(_DWORD *)pvData,
                            (_DWORD)v19,
                            pvData[0],
                            (__int64)v58,
                            (__int64)v18);
                        }
                        v33 = v66;
                        if ( v66 )
                        {
                          v34 = v67;
                          std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::find(
                            v67,
                            &v71,
                            &v78);
                          if ( v71 != *v34 )
                          {
                            v37 = *(_QWORD *)(v71 + 120) == v36;
                            goto LABEL_163;
                          }
                        }
                      }
LABEL_165:
                      v52 = v69;
                      std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::erase(
                        v69,
                        v16,
                        v22);
                      v53 = std::pair<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag>::pair<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag>(
                              v92,
                              v16,
                              &v78);
                      v54 = std::_Tree_buy<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>::_Buynode<std::pair<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag>>(
                              v52,
                              v53);
                      std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::_Insert_nohint<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag> &,std::_Tree_node<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>,void *> *>(
                        (_DWORD)v52,
                        (unsigned int)&v77,
                        v55,
                        v54 + 32,
                        v54);
                      CTnoCfgMgr::cfgmgr_reg_entry_tag::~cfgmgr_reg_entry_tag((CTnoCfgMgr::cfgmgr_reg_entry_tag *)v93);
                      i = v57;
                      v12 = 0;
LABEL_166:
                      CTnoCfgMgr::cfgmgr_reg_entry_tag::~cfgmgr_reg_entry_tag((CTnoCfgMgr::cfgmgr_reg_entry_tag *)&v78);
                      v15 = (unsigned int)(v63 + 1);
                      v10 = v68;
                      v11 = v61;
                      goto LABEL_21;
                    }
                    v38 = *((_DWORD *)v16 + 14);
                    v39 = *((_DWORD *)v16 + 15);
                    v22 = *(_QWORD *)pvData;
                    v40 = *(_DWORD *)pvData;
                    if ( !v12 )
                      v40 = *((_DWORD *)v16 + 8);
                    if ( *((_DWORD *)v16 + 7) )
                    {
                      if ( (int)v39 < (int)v40 )
                        v40 = *((_DWORD *)v16 + 15);
                      if ( (int)v40 < (int)v38 )
                        v40 = *((_DWORD *)v16 + 14);
                    }
                    else
                    {
                      if ( v39 < v40 )
                        v40 = *((_DWORD *)v16 + 15);
                      if ( v40 < v38 )
                        v40 = *((_DWORD *)v16 + 14);
                    }
                    LODWORD(v86) = v40;
                    if ( v12
                      && v26 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)v26 + 27) & 0x200) != 0
                      && *((_BYTE *)v26 + 105) >= 3u )
                    {
                      WPP_SF_SDSS(
                        *((_QWORD *)v26 + 12),
                        v38,
                        *(_DWORD *)pvData,
                        (_DWORD)v19,
                        pvData[0],
                        (__int64)v58,
                        (__int64)v18);
                    }
                    v33 = v66;
                    if ( !v66 )
                      goto LABEL_165;
                    v41 = v67;
                    std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::find(
                      v67,
                      &v72,
                      &v78);
                    if ( v72 == *v41 )
                      goto LABEL_165;
                    v37 = *(_DWORD *)(v72 + 120) == v42;
LABEL_163:
                    if ( v37 )
                      goto LABEL_165;
                    goto LABEL_164;
                  }
                  if ( v12 )
                  {
                    if ( v26 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)v26 + 27) & 0x200) != 0
                      && *((_BYTE *)v26 + 105) >= 3u )
                    {
                      WPP_SF_SS(
                        *((_QWORD *)v26 + 12),
                        84,
                        (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
                        (_DWORD)v58,
                        (__int64)v18);
                    }
                    v43 = CTnoCfgMgr::SetBinaryEntry(
                            v26,
                            (struct CTnoCfgMgr::cfgmgr_reg_entry_tag *)&v78,
                            pvData,
                            pcbData);
                    v44 = v43;
                    v62 = v43;
                    if ( v43 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 12),
                          85,
                          WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
                          (unsigned int)v43);
                      }
                      CTnoCfgMgr::cfgmgr_reg_entry_tag::~cfgmgr_reg_entry_tag((CTnoCfgMgr::cfgmgr_reg_entry_tag *)&v78);
                      InCritSec::~InCritSec((InCritSec *)v76);
                      AutoRegKey::Close((AutoRegKey *)&v65);
                      return v44;
                    }
                  }
                  v33 = v66;
                  if ( !v66 )
                    goto LABEL_165;
                  v45 = v67;
                  std::_Tree<std::_Tmap_traits<enum cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<enum cfg_mgr_reg_ids_tag>,std::allocator<std::pair<enum cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::find(
                    v67,
                    &v73,
                    &v78);
                  if ( v73 == *v45 )
                    goto LABEL_165;
                  v35 = *(_QWORD *)(v73 + 160);
                  if ( !v35 )
                  {
                    v37 = v90 == 0;
                    goto LABEL_163;
                  }
                  if ( !v90 || (v46 = *(_DWORD *)(v90 + 24), *(_DWORD *)(v35 + 24) != v46) )
                  {
LABEL_164:
                    CTnoCfgMgr::SendCfgChangeToEventLog(
                      (CTnoCfgMgr *)v35,
                      v33,
                      (const struct CTnoCfgMgr::cfgmgr_reg_entry_tag *)&v78);
                    goto LABEL_165;
                  }
                  v47 = memcmp_0(*(const void **)(v35 + 16), *(const void **)(v90 + 16), v46);
                }
                v37 = v47 == 0;
                goto LABEL_163;
              }
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 105) < 4u )
              {
                goto LABEL_73;
              }
              WPP_SF_SSS(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                78,
                (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
                (_DWORD)v19,
                (__int64)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
                (__int64)v18);
LABEL_71:
              v26 = WPP_GLOBAL_Control;
              goto LABEL_72;
            }
            v31 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist";
            v58 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist";
            v91 = 1;
            v26 = WPP_GLOBAL_Control;
          }
          else
          {
            LODWORD(v31) = (_DWORD)v58;
          }
          v32 = *((_DWORD *)v16 + 6);
          if ( v32 == pdwType )
          {
            v12 = 1;
          }
          else if ( v26 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)v26 + 27) & 0x200) != 0
                 && *((_BYTE *)v26 + 105) )
          {
            WPP_SF_SSSDD(
              *((_QWORD *)v26 + 12),
              pdwType,
              (_DWORD)v31,
              (_DWORD)v31,
              (__int64)v18,
              (__int64)v19,
              v32,
              pdwType);
            goto LABEL_71;
          }
LABEL_72:
          v22 = 0;
          goto LABEL_73;
        }
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 105) < 4u )
        {
          goto LABEL_55;
        }
        WPP_SF_SSS(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          75,
          (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
          (_DWORD)v19,
          (__int64)L"Software\\Policies\\Microsoft\\PeerDist",
          (__int64)v18);
LABEL_48:
        v22 = 0;
      }
      else
      {
        v58 = L"Software\\Policies\\Microsoft\\PeerDist";
        v91 = 2;
      }
      v26 = WPP_GLOBAL_Control;
      goto LABEL_55;
    }
    v10 = (const struct cfg_mgr_reg_defaults_tag near *const *)*((_QWORD *)this + 16);
    v68 = v10;
    if ( v10 )
    {
      v11 = *((_DWORD *)this + 28);
      v61 = v11;
      v12 = 0;
      goto LABEL_20;
    }
  }
  *((_BYTE *)this + 336) = *((_BYTE *)this + 336) == 0;
  InCritSec::~InCritSec((InCritSec *)v76);
  CTnoCfgMgr::SetPortValues(this);
  CTnoCfgMgr::SendServiceModeToTelemetry(this);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 87, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids);
  }
  AutoRegKey::Close((AutoRegKey *)&v65);
  return v3;
}

```

## disassembly

```asm
0x1800245ac  mov     [rsp+arg_8], rbx
0x1800245b1  mov     [rsp+arg_10], rsi
0x1800245b6  push    rdi
0x1800245b7  push    r12
0x1800245b9  push    r13
0x1800245bb  push    r14
0x1800245bd  push    r15
0x1800245bf  sub     rsp, 430h
0x1800245c6  mov     rax, cs:__security_cookie
0x1800245cd  xor     rax, rsp
0x1800245d0  mov     [rsp+458h+var_38], rax
0x1800245d8  mov     rsi, rcx
0x1800245db  lea     rbx, WPP_GLOBAL_Control
0x1800245e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245e9  mov     r12d, 200h
0x1800245ef  cmp     rcx, rbx
0x1800245f2  jz      short loc_180024615
0x1800245f4  test    [rcx+6Ch], r12d
0x1800245f8  jz      short loc_180024615
0x1800245fa  cmp     byte ptr [rcx+69h], 4
0x1800245fe  jb      short loc_180024615
0x180024600  mov     edx, 4Ah ; 'J'
0x180024605  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x18002460c  mov     rcx, [rcx+60h]
0x180024610  call    WPP_SF_
0x180024615  xor     r15d, r15d
0x180024618  mov     edi, r15d
0x18002461b  mov     [rsp+458h+var_3FC], r15d
0x180024620  mov     [rsp+458h+pdwType], r15d
0x180024625  mov     eax, r15d
0x180024628  mov     [rsp+458h+var_3F0], r15
0x18002462d  mov     [rsp+458h+var_3E8], r15
0x180024632  mov     [rsp+458h+var_408], 1
0x18002463a  cmp     dword ptr [rsi+40h], 3
0x18002463e  cmovz   rax, cs:?s_spLoggingMgr@ITnoLoggingMgr@@0V?$auto_ptr@VITnoLoggingMgr@@@std@@A; std::auto_ptr<ITnoLoggingMgr> ITnoLoggingMgr::s_spLoggingMgr
0x180024646  mov     [rsp+458h+var_3E0], rax
0x18002464b  mov     r8b, 1; bool
0x18002464e  mov     rdx, rsi; struct CritSec *
0x180024651  lea     rcx, [rsp+458h+var_390]; this
0x180024659  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18002465e  nop
0x18002465f  mov     rax, [rsi+140h]
0x180024666  mov     [rsp+458h+var_3C0], rax
0x18002466e  mov     cl, [rsi+150h]
0x180024674  mov     al, cl
0x180024676  neg     al
0x180024678  sbb     rax, rax
0x18002467b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002467f  add     rax, 168h
0x180024685  add     rax, rsi
0x180024688  mov     [rsp+458h+var_3D8], rax
0x180024690  test    cl, cl
0x180024692  lea     r14, [rsi+168h]
0x180024699  jnz     short loc_1800246A2
0x18002469b  lea     r14, [rsi+158h]
0x1800246a2  mov     [rsp+458h+var_3C8], r14
0x1800246aa  mov     rcx, r14
0x1800246ad  call    ?clear@?$_Tree@V?$_Tmap_traits@W4cfg_mgr_reg_ids_tag@@Ucfgmgr_reg_entry_tag@CTnoCfgMgr@@U?$less@W4cfg_mgr_reg_ids_tag@@@std@@V?$allocator@U?$pair@$$CBW4cfg_mgr_reg_ids_tag@@Ucfgmgr_reg_entry_tag@CTnoCfgMgr@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<cfg_mgr_reg_ids_tag,CTnoCfgMgr::cfgmgr_reg_entry_tag,std::less<cfg_mgr_reg_ids_tag>,std::allocator<std::pair<cfg_mgr_reg_ids_tag const,CTnoCfgMgr::cfgmgr_reg_entry_tag>>,0>>::clear(void)
0x1800246b2  lea     rax, [rsp+458h+var_3F0]
0x1800246b7  mov     [rsp+458h+phkResult], rax; phkResult
0x1800246bc  mov     r9d, 20119h; samDesired
0x1800246c2  xor     r8d, r8d; ulOptions
0x1800246c5  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"
0x1800246cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800246d3  call    cs:__imp_RegOpenKeyExW
0x1800246d9  test    eax, eax
0x1800246db  jnz     short loc_1800246F3
0x1800246dd  mov     rbx, [rsp+458h+var_3F0]
0x1800246e2  lea     rcx, [rsp+458h+var_3E8]; this
0x1800246e7  call    ?Close@AutoRegKey@@QEAAXXZ; AutoRegKey::Close(void)
0x1800246ec  mov     [rsp+458h+var_3E8], rbx
0x1800246f1  jmp     short loc_1800246F8
0x1800246f3  mov     [rsp+458h+var_3F0], r15
0x1800246f8  mov     ebx, r15d
0x1800246fb  mov     [rsp+458h+var_414], ebx
0x1800246ff  cmp     ebx, 2
0x180024702  jnb     loc_180025108
0x180024708  mov     eax, ebx
0x18002470a  test    ebx, ebx
0x18002470c  jz      short loc_180024753
0x18002470e  cmp     eax, 1
0x180024711  jz      short loc_18002472A
0x180024713  mov     r15d, 0B7h
0x180024719  lea     r14, ?c_Cfg_Mgr_Reg_Settings@@3QBUcfg_mgr_reg_defaults_tag@@B; cfg_mgr_reg_defaults_tag const near * const c_Cfg_Mgr_Reg_Settings
0x180024720  mov     [rsp+458h+var_3D0], r14
0x180024728  jmp     short loc_180024746
0x18002472a  mov     r14, [rsi+80h]
0x180024731  mov     [rsp+458h+var_3D0], r14
0x180024739  test    r14, r14
0x18002473c  jz      loc_180025101
0x180024742  mov     r15d, [rsi+70h]
0x180024746  mov     [rsp+458h+var_400], r15d
0x18002474b  xor     edi, edi
0x18002474d  test    ebx, ebx
0x18002474f  jnz     short loc_1800247A7
0x180024751  jmp     short loc_18002476D
0x180024753  mov     r15d, 0B7h
0x180024759  mov     [rsp+458h+var_400], r15d
0x18002475e  lea     r14, ?c_Cfg_Mgr_Reg_Settings@@3QBUcfg_mgr_reg_defaults_tag@@B; cfg_mgr_reg_defaults_tag const near * const c_Cfg_Mgr_Reg_Settings
0x180024765  mov     [rsp+458h+var_3D0], r14
0x18002476d  lea     r8, [rsp+458h+var_408]; enum _CFGMGR_SETTING_TYPE *
0x180024772  mov     rdx, [rsp+458h+var_3F0]; HKEY
0x180024777  call    ?GetServiceModeSettingType@CTnoCfgMgr@@IEAAJPEAUHKEY__@@PEAW4_CFGMGR_SETTING_TYPE@@@Z; CTnoCfgMgr::GetServiceModeSettingType(HKEY__ *,_CFGMGR_SETTING_TYPE *)
0x18002477c  mov     edi, eax
0x18002477e  mov     [rsp+458h+var_3FC], eax
0x180024782  test    eax, eax
0x180024784  jns     short loc_1800247A5
0x180024786  lea     rcx, [rsp+458h+var_390]; this
0x18002478e  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180024793  nop
0x180024794  lea     rcx, [rsp+458h+var_3E8]; this
0x180024799  call    ?Close@AutoRegKey@@QEAAXXZ; AutoRegKey::Close(void)
0x18002479e  mov     eax, edi
0x1800247a0  jmp     loc_180025183
0x1800247a5  xor     edi, edi
0x1800247a7  mov     eax, edi
0x1800247a9  mov     [rsp+458h+var_3F8], eax
0x1800247ad  cmp     eax, r15d
0x1800247b0  jnb     loc_1800250FA
0x1800247b6  lea     r13, [rax+rax*4]
0x1800247ba  shl     r13, 4
0x1800247be  add     r13, r14
0x1800247c1  xor     edx, edx; Val
0x1800247c3  mov     r8d, 208h; Size
0x1800247c9  lea     rcx, [rsp+458h+var_248]; void *
0x1800247d1  call    memset_0
0x1800247d6  mov     [rsp+458h+var_418], edi
0x1800247da  mov     [rsp+458h+var_368], edi
0x1800247e1  mov     ecx, 7
0x1800247e6  mov     [rsp+458h+var_348], rcx
0x1800247ee  mov     [rsp+458h+var_350], rdi
0x1800247f6  mov     [rsp+458h+var_360], di
0x1800247fe  mov     [rsp+458h+var_328], rcx
0x180024806  mov     [rsp+458h+var_330], rdi
0x18002480e  mov     [rsp+458h+var_340], di
0x180024816  mov     [rsp+458h+var_320], edi
0x18002481d  mov     [rsp+458h+var_318], rdi
0x180024825  mov     [rsp+458h+var_2F8], rcx
0x18002482d  mov     [rsp+458h+var_300], rdi
0x180024835  mov     [rsp+458h+var_310], di
0x18002483d  mov     [rsp+458h+var_2F0], rdi
0x180024845  lea     rax, dword_1801747C4
0x18002484c  mov     r14, rax
0x18002484f  cmp     [r13+8], rdi
0x180024853  cmovnz  r14, [r13+8]
0x180024858  mov     r15, rax
0x18002485b  cmp     [r13+10h], rdi
0x18002485f  cmovnz  r15, [r13+10h]
0x180024864  cmp     [r13+30h], rdi
0x180024868  cmovnz  rax, [r13+30h]
0x18002486d  mov     [rsp+458h+var_3A0], rax
0x180024875  mov     eax, [r13+0]
0x180024879  test    eax, eax
0x18002487b  jnz     short loc_180024882
0x18002487d  jmp     loc_1800250D5
0x180024882  mov     [rsp+458h+var_368], eax
0x180024889  cmp     [r14], di
0x18002488d  jnz     short loc_180024894
0x18002488f  mov     r8, rdi
0x180024892  jmp     short loc_1800248A2
0x180024894  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024898  inc     r8
0x18002489b  cmp     [r14+r8*2], di
0x1800248a0  jnz     short loc_180024898
0x1800248a2  mov     rdx, r14
0x1800248a5  lea     rcx, [rsp+458h+var_360]; void *
0x1800248ad  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800248b2  cmp     [r15], di
0x1800248b6  jnz     short loc_1800248BD
0x1800248b8  mov     r8, rdi
0x1800248bb  jmp     short loc_1800248CB
0x1800248bd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800248c1  inc     r8
0x1800248c4  cmp     [r15+r8*2], di
0x1800248c9  jnz     short loc_1800248C1
0x1800248cb  lea     rax, aUnknown_1; "UNKNOWN"
0x1800248d2  mov     [rsp+458h+var_410], rax
0x1800248d7  mov     rdx, r15
0x1800248da  lea     rcx, [rsp+458h+var_340]; void *
0x1800248e2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800248e7  mov     eax, [r13+18h]
0x1800248eb  mov     [rsp+458h+var_320], eax
0x1800248f2  xor     r8d, r8d
0x1800248f5  mov     [rsp+458h+var_2E8], r8d
0x1800248fd  cmp     r8w, [r14]
0x180024901  jz      loc_180024CD1
0x180024907  cmp     r8w, [r15]
0x18002490b  jz      loc_180024CD1
0x180024911  test    ebx, ebx
0x180024913  jnz     loc_180024CD1
0x180024919  mov     rcx, [rsp+458h+var_3F0]
0x18002491e  test    rcx, rcx
0x180024921  jz      loc_180024A5B
0x180024927  mov     edx, [r13+0]
0x18002492b  call    ?IsServiceModeValue@CTnoCfgMgr@@IEAA_NW4cfg_mgr_reg_ids_tag@@@Z; CTnoCfgMgr::IsServiceModeValue(cfg_mgr_reg_ids_tag)
0x180024930  test    al, al
0x180024932  jz      short loc_18002493F
0x180024934  cmp     [rsp+458h+var_408], 2
0x180024939  jnz     loc_180024A5B
0x18002493f  mov     [rsp+458h+var_418], 208h
0x180024947  lea     rax, [rsp+458h+var_418]
0x18002494c  mov     [rsp+458h+pcbData], rax; pcbData
0x180024951  lea     rax, [rsp+458h+var_248]
0x180024959  mov     [rsp+458h+pvData], rax; pvData
0x18002495e  lea     rax, [rsp+458h+pdwType]
0x180024963  mov     [rsp+458h+phkResult], rax; pdwType
0x180024968  mov     r9d, 1000FFFFh; dwFlags
0x18002496e  mov     r8, r15; lpValue
0x180024971  mov     rdx, r14; lpSubKey
0x180024974  call    cs:__imp_RegGetValueW
0x18002497a  mov     ebx, eax
0x18002497c  xor     r8d, r8d
0x18002497f  test    eax, eax
0x180024981  jz      loc_180024A33
0x180024987  cmp     eax, 2
0x18002498a  jz      short loc_1800249E9
0x18002498c  cmp     eax, 490h
0x180024991  jz      short loc_1800249E9
0x180024993  mov     rcx, cs:WPP_GLOBAL_Control
0x18002499a  lea     rax, WPP_GLOBAL_Control
0x1800249a1  cmp     rcx, rax
0x1800249a4  jz      loc_180024A51
0x1800249aa  test    [rcx+6Ch], r12d
0x1800249ae  jz      loc_180024A51
0x1800249b4  cmp     byte ptr [rcx+69h], 1
0x1800249b8  jb      loc_180024A51
0x1800249be  lea     edx, [r8+4Ch]
0x1800249c2  mov     [rsp+458h+pcbData], r14
0x1800249c7  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"
0x1800249ce  mov     [rsp+458h+pvData], rax
0x1800249d3  mov     [rsp+458h+phkResult], r15
0x1800249d8  mov     r9d, ebx
0x1800249db  mov     rcx, [rcx+60h]
0x1800249df  call    WPP_SF_DSSS
0x1800249e4  xor     r8d, r8d
0x1800249e7  jmp     short loc_180024A4A
0x1800249e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249f0  lea     rax, WPP_GLOBAL_Control
0x1800249f7  cmp     rcx, rax
0x1800249fa  jz      short loc_180024A51
0x1800249fc  test    [rcx+6Ch], r12d
0x180024a00  jz      short loc_180024A51
0x180024a02  cmp     byte ptr [rcx+69h], 4
0x180024a06  jb      short loc_180024A51
0x180024a08  mov     edx, 4Bh ; 'K'
0x180024a0d  mov     [rsp+458h+pvData], r14
0x180024a12  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"
0x180024a19  mov     [rsp+458h+phkResult], rax
0x180024a1e  mov     r9, r15
0x180024a21  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180024a28  mov     rcx, [rcx+60h]
0x180024a2c  call    WPP_SF_SSS
0x180024a31  jmp     short loc_1800249E4
0x180024a33  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"
0x180024a3a  mov     [rsp+458h+var_410], rax
0x180024a3f  mov     [rsp+458h+var_2E8], 2
0x180024a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a51  test    ebx, ebx
0x180024a53  jz      loc_180024C6A
0x180024a59  jmp     short loc_180024AAE
0x180024a5b  mov     r9d, 490h
0x180024a61  mov     ebx, r9d
0x180024a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a6b  lea     rax, WPP_GLOBAL_Control
0x180024a72  cmp     rcx, rax
0x180024a75  jz      short loc_180024AAE
0x180024a77  test    [rcx+6Ch], r12d
0x180024a7b  jz      short loc_180024AAE
0x180024a7d  cmp     byte ptr [rcx+69h], 1
0x180024a81  jb      short loc_180024AAE
0x180024a83  mov     edx, 4Dh ; 'M'
0x180024a88  mov     dword ptr [rsp+458h+phkResult], r9d
0x180024a8d  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"
0x180024a94  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180024a9b  mov     rcx, [rcx+60h]
0x180024a9f  call    WPP_SF_Sd
0x180024aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180024aab  xor     r8d, r8d
0x180024aae  cmp     [rsp+458h+var_3C0], r8
0x180024ab6  jz      loc_180024C66
0x180024abc  mov     edx, [r13+0]
0x180024ac0  call    ?IsServiceModeValue@CTnoCfgMgr@@IEAA_NW4cfg_mgr_reg_ids_tag@@@Z; CTnoCfgMgr::IsServiceModeValue(cfg_mgr_reg_ids_tag)
0x180024ac5  test    al, al
0x180024ac7  jz      short loc_180024AD4
0x180024ac9  cmp     [rsp+458h+var_408], 1
0x180024ace  jnz     loc_180024C66
0x180024ad4  mov     [rsp+458h+var_418], 208h
0x180024adc  lea     rax, [rsp+458h+var_418]
0x180024ae1  mov     [rsp+458h+pcbData], rax; pcbData
0x180024ae6  lea     rax, [rsp+458h+var_248]
0x180024aee  mov     [rsp+458h+pvData], rax; pvData
0x180024af3  lea     rax, [rsp+458h+pdwType]
0x180024af8  mov     [rsp+458h+phkResult], rax; pdwType
0x180024afd  mov     r9d, 1000FFFFh; dwFlags
0x180024b03  mov     r8, r15; lpValue
0x180024b06  mov     rdx, r14; lpSubKey
0x180024b09  mov     rcx, [rsi+140h]; hkey
0x180024b10  call    cs:__imp_RegGetValueW
0x180024b16  xor     r8d, r8d
0x180024b19  test    eax, eax
  ... truncated ...
```
