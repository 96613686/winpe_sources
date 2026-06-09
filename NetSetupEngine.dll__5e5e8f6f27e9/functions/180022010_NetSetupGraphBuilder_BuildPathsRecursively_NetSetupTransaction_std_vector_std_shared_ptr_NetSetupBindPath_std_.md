# NetSetupGraphBuilder::BuildPathsRecursively(NetSetupTransaction &,std::vector<std::shared_ptr<NetSetupBindPath>,std::allocator<std::shared_ptr<NetSetupBindPath>>> &,NetSetupBindNode &,NetSetupBindNode const &,std::vector<NetSetupBindNode *,std::allocator<NetSetupBindNode *>> &,std::vector<NetSetupBindPath const *,std::allocator<NetSetupBindPath const *>> &,ushort,ulong *)

- ea: `0x180022010`
- end: `0x18002370e`
- name: `?BuildPathsRecursively@NetSetupGraphBuilder@@AEAAXAEAVNetSetupTransaction@@AEAV?$vector@V?$shared_ptr@VNetSetupBindPath@@@std@@V?$allocator@V?$shared_ptr@VNetSetupBindPath@@@std@@@2@@std@@AEAVNetSetupBindNode@@AEBV5@AEAV?$vector@PEAVNetSetupBindNode@@V?$allocator@PEAVNetSetupBindNode@@@std@@@4@AEAV?$vector@PEBVNetSetupBindPath@@V?$allocator@PEBVNetSetupBindPath@@@std@@@4@GPEAK@Z`
- size: `5886`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021c2c`
- `0x180022010`

## callees

- `0x180005660`
- `0x180005c94`
- `0x180006eb0`
- `0x180007b00`
- `0x180007eb0`
- `0x1800086b0`
- `0x18000a430`
- `0x1800217b8`
- `0x180021888`
- `0x180021f08`
- `0x180022010`
- `0x180023714`
- `0x1800237b0`
- `0x180023910`
- `0x180023d24`
- `0x180023da8`
- `0x180024330`
- `0x180029d20`
- `0x18002e4f0`
- `0x180039b88`
- `0x18005097c`
- `0x1800646b8`
- `0x180064704`
- `0x1800647e0`
- `0x180065035`
- `0x18006c3a4`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180022356`
- `msvcrt!swprintf_s` at `0x180022f06`
- `msvcrt!swprintf_s` at `0x180022356`
- `msvcrt!swprintf_s` at `0x180022f06`
- `msvcrt!wcscat_s` at `0x180022392`
- `msvcrt!wcscat_s` at `0x180022f60`
- `msvcrt!wcscat_s` at `0x180022f90`
- `msvcrt!wcscat_s` at `0x180022392`
- `msvcrt!wcscat_s` at `0x180022f60`
- `msvcrt!wcscat_s` at `0x180022f90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800223d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002328a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800223d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002328a`

## string_xrefs

- `0x180022343`: `Control\NetworkSetup2\BindPaths\%ws`
- `0x180022eb9`: `Protocols`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall NetSetupGraphBuilder::BuildPathsRecursively(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7,
        __int16 a8,
        int *a9)
{
  __int64 v9; // r12
  _QWORD *v10; // r13
  _QWORD *v11; // rbx
  _QWORD *v12; // r10
  _QWORD *v13; // r11
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  bool v17; // al
  int *v18; // r15
  __int64 v19; // rax
  HKEY v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // rbx
  unsigned __int64 v23; // rax
  __int64 *v24; // rdx
  __int64 v25; // rcx
  volatile signed __int32 *v26; // rbx
  __int64 v27; // r13
  __int64 v28; // rax
  __int64 v29; // rcx
  _DWORD *v30; // r9
  int v31; // r8d
  __int16 v32; // cx
  int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // r9
  unsigned __int64 v36; // rcx
  int v37; // ecx
  HKEY *v38; // r15
  int v39; // ecx
  _QWORD *v40; // rax
  HKEY *v41; // rbx
  int v42; // ecx
  HKEY v43; // rax
  HKEY v44; // rsi
  HKEY v45; // rbx
  unsigned __int64 v46; // rax
  __int64 v47; // rsi
  __int64 v48; // r14
  _QWORD *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 result; // rax
  _QWORD *v53; // r15
  __int64 i; // rax
  __int64 j; // rcx
  __int64 v56; // rbx
  __int64 v57; // rdi
  __int64 *v58; // r12
  __int64 k; // rax
  __int64 m; // rcx
  _WORD *v61; // r9
  unsigned __int64 v62; // rbx
  unsigned __int64 v63; // rdi
  unsigned __int64 v64; // rdx
  _WORD *v65; // r8
  int v66; // edx
  _WORD *v67; // r9
  unsigned __int64 v68; // r10
  unsigned __int64 v69; // r11
  unsigned __int64 v70; // rdx
  _WORD *v71; // r8
  int v72; // edx
  __int64 v73; // rbx
  _QWORD *v74; // rdx
  __int64 *v75; // r14
  __int64 *v76; // r15
  HKEY v77; // r13
  __int64 v78; // r12
  HKEY v79; // r15
  HKEY v80; // rdi
  _QWORD *v81; // r12
  int *v82; // r14
  HKEY kk; // rbx
  __int64 n; // rax
  __int64 v85; // rbx
  __int64 v86; // rdi
  __int64 v87; // rbx
  __int64 v88; // rdi
  __int64 v89; // rax
  __int64 jj; // rcx
  _WORD *v91; // r9
  unsigned __int64 v92; // rbx
  unsigned __int64 v93; // rdi
  unsigned __int64 v94; // rdx
  _WORD *v95; // r8
  int v96; // edx
  __int64 ii; // rcx
  _WORD *v98; // r9
  unsigned __int64 v99; // rbx
  unsigned __int64 v100; // rdi
  unsigned __int64 v101; // rdx
  _WORD *v102; // r8
  int v103; // edx
  bool v104; // zf
  __int64 *v105; // rbx
  __int64 *v106; // rsi
  __int64 v107; // rcx
  unsigned __int64 v108; // rax
  __int64 *v109; // rdx
  __int64 v110; // rcx
  _DWORD *v111; // rcx
  int v112; // eax
  _DWORD *v113; // rcx
  int v114; // eax
  _DWORD *v115; // rcx
  int v116; // eax
  _DWORD *v117; // rcx
  int v118; // eax
  _DWORD *v119; // rdx
  _DWORD *v120; // rdx
  _DWORD *v121; // rdx
  _DWORD *v122; // rdx
  char *v123; // rbx
  char *v124; // rdi
  unsigned __int64 v125; // rax
  unsigned __int64 v126; // rax
  unsigned __int64 v127; // rax
  unsigned __int64 v128; // rax
  _QWORD *v129; // rax
  _QWORD *v130; // rbx
  __int64 v131; // rdx
  const wchar_t *v132; // rdi
  _QWORD *v133; // rax
  __int64 v134; // rdx
  __int64 v135; // rdx
  __int64 v136; // rax
  __int64 v137; // rdx
  __int64 v138; // rbx
  __int64 v139; // rsi
  __int64 v140; // r8
  __int64 v141; // rdi
  __int64 v142; // r8
  _QWORD *v143; // r10
  __int16 v144; // di
  unsigned __int64 v145; // r13
  unsigned __int64 v146; // rbx
  unsigned __int64 v147; // rdx
  int v148; // r8d
  __int128 v149; // xmm6
  HKEY v150; // rdi
  int v151; // ecx
  __int64 v152; // rax
  __int64 v153; // rbx
  unsigned __int64 v154; // rbx
  _DWORD *v155; // r8
  signed __int64 v156; // rbx
  _DWORD *v157; // r8
  signed __int64 v158; // rbx
  _DWORD *v159; // r8
  signed __int64 v160; // rbx
  _DWORD *v161; // r8
  signed __int64 v162; // rbx
  unsigned __int64 v163; // r14
  _QWORD *v165; // [rsp+58h] [rbp-A8h]
  void *Block[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v169; // [rsp+98h] [rbp-68h]
  __int64 v170; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v171; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v172; // [rsp+B0h] [rbp-50h]
  int *v173; // [rsp+B8h] [rbp-48h]
  __int64 v174; // [rsp+C0h] [rbp-40h]
  __int128 v175; // [rsp+C8h] [rbp-38h] BYREF
  int v176; // [rsp+D8h] [rbp-28h]
  int v177; // [rsp+DCh] [rbp-24h]
  _BYTE v178[24]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v179; // [rsp+F8h] [rbp-8h]
  HKEY hKey; // [rsp+100h] [rbp+0h] BYREF
  void *v181[2]; // [rsp+108h] [rbp+8h] BYREF
  _DWORD *v182; // [rsp+118h] [rbp+18h]
  void *v183[2]; // [rsp+120h] [rbp+20h] BYREF
  HKEY v184; // [rsp+130h] [rbp+30h]
  int v185; // [rsp+138h] [rbp+38h] BYREF
  HKEY v186; // [rsp+140h] [rbp+40h] BYREF
  __int128 v187; // [rsp+148h] [rbp+48h] BYREF
  int v188; // [rsp+158h] [rbp+58h]
  int v189; // [rsp+15Ch] [rbp+5Ch]
  _BYTE v190[24]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v191; // [rsp+178h] [rbp+78h] BYREF
  int v192; // [rsp+188h] [rbp+88h]
  int v193; // [rsp+18Ch] [rbp+8Ch]
  _BYTE v194[24]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v195; // [rsp+1A8h] [rbp+A8h] BYREF
  int v196; // [rsp+1B8h] [rbp+B8h]
  int v197; // [rsp+1BCh] [rbp+BCh]
  _BYTE v198[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t Buffer[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v179 = -2;
  v9 = a4;
  v10 = a3;
  v172 = a3;
  v11 = a1;
  v174 = a5;
  v12 = a6;
  v13 = a7;
  v170 = a4;
  v14 = a6[1];
  if ( (unsigned __int64)&v170 < v14 && *a6 <= (unsigned __int64)&v170 )
  {
    v153 = ((__int64)&v170 - *a6) >> 3;
    if ( v14 == a6[2] )
    {
      std::vector<NetSetupLoadedPlugin const *>::_Reserve(a6);
      v12 = a6;
      v13 = a7;
    }
    *(_QWORD *)v12[1] = *(_QWORD *)(*v12 + 8 * v153);
    v11 = a1;
  }
  else
  {
    if ( v14 == a6[2] )
    {
      std::vector<NetSetupLoadedPlugin const *>::_Reserve(a6);
      v12 = a6;
      v13 = a7;
    }
    *(_QWORD *)v12[1] = v9;
  }
  v15 = v12[1] + 8LL;
  v12[1] = v15;
  v16 = v15;
  v185 = 0;
  v17 = *(_BYTE *)(v9 + 193) && *(_BYTE *)(v9 + 212) && *(_WORD *)(v9 + 222) < 0x119u;
  v18 = &v185;
  if ( !v17 )
    v18 = a9;
  v173 = v18;
  if ( (unsigned __int64)((v16 - *v12) >> 3) >= 2 )
  {
    v19 = v13[1];
    if ( *v13 == v19 )
      v20 = 0;
    else
      v20 = *(HKEY *)(v19 - 8);
    hKey = v20;
    v22 = std::make_shared<NetSetupBindPath,std::vector<NetSetupBindNode *> &,NetSetupBindPath const * &>(
            Block,
            (__int64)v12,
            (__int64 *)&hKey);
    v23 = v10[1];
    if ( (unsigned __int64)v22 < v23 && *v10 <= (unsigned __int64)v22 )
    {
      v154 = (unsigned __int64)v22 - *v10;
      if ( v23 == v10[2] )
        std::vector<std::shared_ptr<NetSetupBindPath>>::_Reserve(v10);
      std::_Wrap_alloc<std::allocator<std::shared_ptr<NetSetupBindPath>>>::construct<std::shared_ptr<NetSetupBindPath>,std::shared_ptr<NetSetupBindPath>>(
        v21,
        (__int64 *)v10[1],
        (__int64 *)(*v10 + (v154 & 0xFFFFFFFFFFFFFFF0uLL)));
    }
    else
    {
      if ( v23 == v10[2] )
        std::vector<std::shared_ptr<NetSetupBindPath>>::_Reserve(v10);
      v24 = (__int64 *)v10[1];
      *v24 = 0;
      v24[1] = 0;
      if ( v24 != v22 )
      {
        v24[1] = v22[1];
        v22[1] = 0;
        v25 = *v24;
        *v24 = *v22;
        *v22 = v25;
      }
    }
    v10[1] += 16LL;
    v26 = (volatile signed __int32 *)Block[1];
    if ( Block[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    v27 = *(_QWORD *)(v10[1] - 16LL);
    *(_OWORD *)(v27 + 32) = 0;
    v28 = *a6;
    v29 = a6[1];
    while ( v28 != v29 )
    {
      v30 = *(_DWORD **)v28;
      v31 = *(_DWORD *)(*(_QWORD *)v28 + 4LL) ^ *(_DWORD *)(v27 + 36);
      *(_DWORD *)(v27 + 32) = v31;
      *(_DWORD *)(v27 + 36) = *(_DWORD *)(v27 + 40) ^ v30[2];
      *(_DWORD *)(v27 + 40) = *(_DWORD *)(v27 + 44) ^ v30[3];
      *(_DWORD *)(v27 + 44) = v30[4] ^ v31;
      v28 += 8;
    }
    *(_BYTE *)(v27 + 40) = *(_BYTE *)(v27 + 40) & 0x1F | 0xC0;
    v32 = a8;
    if ( (unsigned __int64)((__int64)(a6[1] - *a6) >> 3) <= 2 )
      v32 = 0;
    *(_WORD *)(v27 + 112) = v32;
    *(_BYTE *)(v27 + 114) = *(_BYTE *)(v9 + 195);
    v33 = ++*v18;
    v34 = **(_QWORD **)(v27 + 56);
    v35 = (unsigned int)++*(_DWORD *)(v34 + 224);
    if ( *(_BYTE *)(v34 + 193) && *(_BYTE *)(v34 + 212) && *(_WORD *)(v34 + 222) < 0x119u )
    {
      if ( (unsigned int)v35 > 0x7F )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_71e95b2648723d8386fcbc850d2d5df3_Traceguids, v35, 127);
        HResultException::HResultException((HResultException *)Buffer, -2147024809);
        throw (HResultException *)Buffer;
      }
      v36 = *(_QWORD *)(v34 + 216);
      if ( ((v36 >> 24) & 0xFFFFFF) > 0xFFFF )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_71e95b2648723d8386fcbc850d2d5df3_Traceguids,
            (v36 >> 24) & 0xFFFFFF,
            0xFFFF);
        HResultException::HResultException((HResultException *)Buffer, -2147024809);
        throw (HResultException *)Buffer;
      }
      v37 = v33 & 0x7F | (((unsigned __int16)(v36 >> 24) | (HIWORD(v36) << 16)) << 7);
    }
    else
    {
      if ( (unsigned int)v35 > 0x7FFFFF )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_71e95b2648723d8386fcbc850d2d5df3_Traceguids,
            v35,
            0x7FFFFF);
        HResultException::HResultException((HResultException *)Buffer, -2147024809);
        throw (HResultException *)Buffer;
      }
      v37 = v33 - 1937768448;
    }
    *(_DWORD *)(v27 + 116) = v37;
    *(_BYTE *)(v27 + 48) = *(_BYTE *)(v9 + 192);
    v38 = (HKEY *)(v27 + 160);
    if ( *(_QWORD *)(v27 + 160) )
      goto LABEL_184;
    v39 = *(_DWORD *)(v27 + 120);
    if ( v39 )
    {
      if ( v39 == 1 )
      {
        v129 = (_QWORD *)StringFromGuid(&v175, *(_QWORD *)(v27 + 80) + 24LL);
        v130 = v129;
        if ( v129[3] >= 8u )
          v130 = (_QWORD *)*v129;
        v131 = *(_QWORD *)(v27 + 80);
        v132 = L"Filters";
        if ( *(_DWORD *)(v131 + 20) != 3 )
          v132 = L"Protocols";
        v133 = (_QWORD *)StringFromGuid(Block, v131 + 4);
        if ( v133[3] >= 8u )
          v133 = (_QWORD *)*v133;
        swprintf_s(Buffer, 0x104u, L"Networking\\NetAdapters\\%ws\\Bindings\\%ws\\%ws", v133, v132, v130);
        LOBYTE(v134) = 1;
        std::wstring::_Tidy(Block, v134, 0);
        LOBYTE(v135) = 1;
        std::wstring::_Tidy(&v175, v135, 0);
        if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v27 + 88) - *(_QWORD *)(v27 + 80)) >> 2) > 2 )
        {
          wcscat_s(Buffer, 0x104u, L"-");
          v136 = StringFromGuid(&v175, *(_QWORD *)(v27 + 80) + 44LL);
          if ( *(_QWORD *)(v136 + 24) >= 8u )
            v136 = *(_QWORD *)v136;
          wcscat_s(Buffer, 0x104u, (const wchar_t *)v136);
          LOBYTE(v137) = 1;
          std::wstring::_Tidy(&v175, v137, 0);
        }
      }
    }
    else
    {
      v40 = (_QWORD *)StringFromGuid(Block, v27 + 32);
      if ( v40[3] >= 8u )
        v40 = (_QWORD *)*v40;
      swprintf_s(Buffer, 0x104u, L"Control\\NetworkSetup2\\BindPaths\\%ws", v40);
      if ( v169 >= 8 )
        operator delete(Block[0]);
    }
    v41 = 0;
    v42 = *(_DWORD *)(v27 + 120);
    if ( v42 )
    {
      if ( v42 == 1 )
        v41 = (HKEY *)(a2 + 6);
    }
    else
    {
      v41 = (HKEY *)(a2 + 3);
      wcscat_s(Buffer, 0x104u, L"\\Properties");
    }
    v43 = RegistryKey::TryOpenSubKey(v41, (HKEY)&hKey, Buffer, 0xEu, 0);
    v44 = *(HKEY *)v43;
    *(_QWORD *)v43 = 0;
    v45 = v44;
    v186 = v44;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v44 )
    {
      v149 = *(_OWORD *)(v27 + 32);
      v150 = (HKEY)operator new(0x58u);
      hKey = v150;
      if ( v150 )
      {
        v151 = *(_DWORD *)(v27 + 120);
        v152 = *a2;
        if ( *a2 )
          v152 = *(_QWORD *)(v152 + 8);
        *(_QWORD *)v150 = &NetSetupPropertyBag::`vftable';
        v45 = 0;
        *((_QWORD *)v150 + 1) = v44;
        *((_DWORD *)v150 + 4) = 2;
        *(_OWORD *)(v150 + 5) = v149;
        *((_DWORD *)v150 + 9) = v151;
        *((_QWORD *)v150 + 5) = v152;
        *((_QWORD *)v150 + 6) = 0;
        *((_DWORD *)v150 + 14) = 0;
        *((_QWORD *)v150 + 8) = 0;
        *((_QWORD *)v150 + 9) = 0;
        *((_QWORD *)v150 + 10) = 0;
        v44 = 0;
      }
      else
      {
        v150 = 0;
      }
      if ( v150 != *v38 )
      {
        std::unique_ptr<NetSetupPropertyBag>::_Delete(v27 + 160);
        *v38 = v150;
      }
      if ( v45 && v44 )
        RegCloseKey(v44);
    }
    if ( *v38 )
    {
LABEL_184:
      *(_OWORD *)v181 = 0;
      v182 = 0;
      std::vector<_NETSETUPPROPKEY>::_Reallocate(v181, 4);
      v111 = v181[1];
      if ( &NETSETUPPKEY_Binding_EnabledByController >= v181[1]
        || (v155 = v181[0], v181[0] > &NETSETUPPKEY_Binding_EnabledByController) )
      {
        if ( v181[1] == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v111 = v181[1];
        }
        *(_OWORD *)v111 = NETSETUPPKEY_Binding_EnabledByController;
        v112 = 80;
      }
      else
      {
        v156 = ((char *)&NETSETUPPKEY_Binding_EnabledByController - (char *)v181[0]) / 20;
        if ( v181[1] == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v111 = v181[1];
          v155 = v181[0];
        }
        *(_OWORD *)v111 = *(_OWORD *)&v155[5 * v156];
        v112 = v155[5 * v156 + 4];
      }
      v111[4] = v112;
      v113 = (char *)v181[1] + 20;
      v181[1] = v113;
      if ( &NETSETUPPKEY_Binding_EnabledByBindRules >= (__int128 *)v113
        || (v157 = v181[0], v181[0] > &NETSETUPPKEY_Binding_EnabledByBindRules) )
      {
        if ( v113 == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v113 = v181[1];
        }
        *(_OWORD *)v113 = NETSETUPPKEY_Binding_EnabledByBindRules;
        v114 = 84;
      }
      else
      {
        v158 = ((char *)&NETSETUPPKEY_Binding_EnabledByBindRules - (char *)v181[0]) / 20;
        if ( v113 == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v113 = v181[1];
          v157 = v181[0];
        }
        *(_OWORD *)v113 = *(_OWORD *)&v157[5 * v158];
        v114 = v157[5 * v158 + 4];
      }
      v113[4] = v114;
      v115 = (char *)v181[1] + 20;
      v181[1] = v115;
      if ( &NETSETUPPKEY_Binding_EnabledByUserPersisted >= (__int128 *)v115
        || (v159 = v181[0], v181[0] > &NETSETUPPKEY_Binding_EnabledByUserPersisted) )
      {
        if ( v115 == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v115 = v181[1];
        }
        *(_OWORD *)v115 = NETSETUPPKEY_Binding_EnabledByUserPersisted;
        v116 = 82;
      }
      else
      {
        v160 = ((char *)&NETSETUPPKEY_Binding_EnabledByUserPersisted - (char *)v181[0]) / 20;
        if ( v115 == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v115 = v181[1];
          v159 = v181[0];
        }
        *(_OWORD *)v115 = *(_OWORD *)&v159[5 * v160];
        v116 = v159[5 * v160 + 4];
      }
      v115[4] = v116;
      v117 = (char *)v181[1] + 20;
      v181[1] = v117;
      if ( &NETSETUPPKEY_Binding_UserOrderHintPersisted >= (__int128 *)v117
        || (v161 = v181[0], v181[0] > &NETSETUPPKEY_Binding_UserOrderHintPersisted) )
      {
        if ( v117 == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v117 = v181[1];
        }
        *(_OWORD *)v117 = NETSETUPPKEY_Binding_UserOrderHintPersisted;
        v118 = 90;
      }
      else
      {
        v162 = ((char *)&NETSETUPPKEY_Binding_UserOrderHintPersisted - (char *)v181[0]) / 20;
        if ( v117 == v182 )
        {
          std::vector<_NETSETUPPROPKEY>::_Reserve(v181, 1);
          v117 = v181[1];
          v161 = v181[0];
        }
        *(_OWORD *)v117 = *(_OWORD *)&v161[5 * v162];
        v118 = v161[5 * v162 + 4];
      }
      v117[4] = v118;
      v181[1] = (char *)v181[1] + 20;
      *(_OWORD *)v183 = 0;
      v184 = 0;
      (*(void (__fastcall **)(HKEY, _QWORD *, void **, void **))(*(_QWORD *)*v38 + 8LL))(*v38, a2, v181, v183);
      v119 = v183[0];
      *(_OWORD *)Block = NETSETUPPKEY_Binding_EnabledByController;
      if ( v183[0] == v183[1] )
        goto LABEL_349;
      do
      {
        if ( v119[4] == 80 )
        {
          v125 = *(_QWORD *)v119 - (unsigned __int64)Block[0];
          if ( *(void **)v119 == Block[0] )
            v125 = *((_QWORD *)v119 + 1) - (unsigned __int64)Block[1];
          if ( !v125 )
            break;
        }
        v119 += 12;
      }
      while ( v119 != v183[1] );
      if ( v119 == v183[1] )
      {
LABEL_349:
        HResultException::HResultException((HResultException *)Buffer, -2147024664);
        throw (HResultException *)Buffer;
      }
      v195 = *(_OWORD *)v119;
      v196 = v119[4];
      v197 = v119[5];
      std::vector<unsigned char>::vector<unsigned char>(v198, v119 + 6);
      v120 = v183[0];
      *(_OWORD *)Block = NETSETUPPKEY_Binding_EnabledByBindRules;
      if ( v183[0] == v183[1] )
        goto LABEL_350;
      do
      {
        if ( v120[4] == 84 )
        {
          v126 = *(_QWORD *)v120 - (unsigned __int64)Block[0];
          if ( *(void **)v120 == Block[0] )
            v126 = *((_QWORD *)v120 + 1) - (unsigned __int64)Block[1];
          if ( !v126 )
            break;
        }
        v120 += 12;
      }
      while ( v120 != v183[1] );
      if ( v120 == v183[1] )
      {
LABEL_350:
        HResultException::HResultException((HResultException *)Buffer, -2147024664);
        throw (HResultException *)Buffer;
      }
      v191 = *(_OWORD *)v120;
      v192 = v120[4];
      v193 = v120[5];
      std::vector<unsigned char>::vector<unsigned char>(v194, v120 + 6);
      v121 = v183[0];
      *(_OWORD *)Block = NETSETUPPKEY_Binding_EnabledByUserPersisted;
      if ( v183[0] == v183[1] )
        goto LABEL_351;
      do
      {
        if ( v121[4] == 82 )
        {
          v127 = *(_QWORD *)v121 - (unsigned __int64)Block[0];
          if ( *(void **)v121 == Block[0] )
            v127 = *((_QWORD *)v121 + 1) - (unsigned __int64)Block[1];
          if ( !v127 )
            break;
        }
        v121 += 12;
      }
      while ( v121 != v183[1] );
      if ( v121 == v183[1] )
      {
LABEL_351:
        HResultException::HResultException((HResultException *)Buffer, -2147024664);
        throw (HResultException *)Buffer;
      }
      v187 = *(_OWORD *)v121;
      v188 = v121[4];
      v189 = v121[5];
      std::vector<unsigned char>::vector<unsigned char>(v190, v121 + 6);
      v122 = v183[0];
      *(_OWORD *)Block = NETSETUPPKEY_Binding_UserOrderHintPersisted;
      if ( v183[0] == v183[1] )
        goto LABEL_352;
      do
      {
        if ( v122[4] == 90 )
        {
          v128 = *(_QWORD *)v122 - (unsigned __int64)Block[0];
          if ( *(void **)v122 == Block[0] )
            v128 = *((_QWORD *)v122 + 1) - (unsigned __int64)Block[1];
          if ( !v128 )
            break;
        }
        v122 += 12;
      }
      while ( v122 != v183[1] );
      if ( v122 == v183[1] )
      {
LABEL_352:
        HResultException::HResultException((HResultException *)Buffer, -2147024664);
        throw (HResultException *)Buffer;
      }
      v175 = *(_OWORD *)v122;
      v176 = v122[4];
      v177 = v122[5];
      std::vector<unsigned char>::vector<unsigned char>(v178, v122 + 6);
      if ( v197 )
        *(_DWORD *)(v27 + 132) = !NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v195) + 1;
      if ( v193 )
        *(_DWORD *)(v27 + 128) = !NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v191) + 1;
      if ( v189 )
        *(_DWORD *)(v27 + 136) = !NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v187) + 1;
      if ( v177 )
        *(_DWORD *)(v27 + 140) = NetSetup2::Property::GetUint32((NetSetup2::Property *)&v175);
      std::vector<_NETSETUPPROPKEY>::_Tidy(v178);
      std::vector<_NETSETUPPROPKEY>::_Tidy(v190);
      std::vector<_NETSETUPPROPKEY>::_Tidy(v194);
      std::vector<_NETSETUPPROPKEY>::_Tidy(v198);
      v123 = (char *)v183[0];
      if ( v183[0] )
      {
        v124 = (char *)v183[1];
        if ( v183[0] != v183[1] )
        {
          do
          {
            std::vector<_NETSETUPPROPKEY>::_Tidy(v123 + 24);
            v123 += 48;
          }
          while ( v123 != v124 );
          v123 = (char *)v183[0];
        }
        operator delete(v123);
        *(_OWORD *)v183 = 0;
        v184 = 0;
      }
      if ( v181[0] )
        operator delete(v181[0]);
    }
    *(_BYTE *)(v9 + 200) = 1;
    v171 = v27;
    v13 = a7;
    v46 = a7[1];
    if ( (unsigned __int64)&v171 >= v46 || *a7 > (unsigned __int64)&v171 )
    {
      if ( v46 == a7[2] )
      {
        std::vector<NetSetupLoadedPlugin const *>::_Reserve(a7);
        v13 = a7;
      }
      *(_QWORD *)v13[1] = v27;
    }
    else
    {
      v73 = ((__int64)&v171 - *a7) >> 3;
      if ( v46 == a7[2] )
      {
        std::vector<NetSetupLoadedPlugin const *>::_Reserve(a7);
        v13 = a7;
      }
      *(_QWORD *)v13[1] = *(_QWORD *)(*v13 + 8 * v73);
    }
    v12 = a6;
    v11 = a1;
    LODWORD(v10) = (_DWORD)v172;
    v13[1] += 8LL;
  }
  if ( !*(_BYTE *)(v9 + 194) )
  {
    v47 = v11[6];
    v48 = v11[7];
    while ( v47 != v48 )
    {
      v53 = *(_QWORD **)v47;
      for ( i = *(_QWORD *)(*(_QWORD *)v47 + 120LL); i != v53[16]; i += 32 )
      {
        for ( j = *(_QWORD *)(v9 + 24); j != *(_QWORD *)(v9 + 32); j += 32 )
        {
          if ( *(_QWORD *)(i + 24) < 8u )
            v67 = (_WORD *)i;
          else
            v67 = *(_WORD **)i;
          v68 = *(_QWORD *)(i + 16);
          v69 = *(_QWORD *)(j + 16);
          v70 = v69;
          if ( v69 >= v68 )
            v70 = *(_QWORD *)(i + 16);
          if ( *(_QWORD *)(j + 24) < 8u )
            v71 = (_WORD *)j;
          else
            v71 = *(_WORD **)j;
          if ( v70 )
          {
            while ( v70 )
            {
              if ( *v71 != *v67 )
              {
                v72 = -1;
                if ( *v71 >= *v67 )
                  v72 = 1;
                goto LABEL_105;
              }
              ++v71;
              ++v67;
              --v70;
            }
          }
          if ( v69 < v68 )
            v72 = -1;
          else
            v72 = v69 != v68;
LABEL_105:
          if ( !v72 )
            goto LABEL_91;
        }
      }
      v56 = *(_QWORD *)(v9 + 96);
      v57 = *(_QWORD *)(v9 + 104);
      v58 = v53 + 6;
      while ( v56 != v57 )
      {
        v58 = v53 + 6;
        if ( (unsigned __int8)IsInRange(v53 + 6, v56) )
        {
          v9 = a4;
          goto LABEL_91;
        }
        v56 += 32;
      }
      for ( k = *v58; ; k += 32 )
      {
        v9 = a4;
        if ( k == v53[7] )
          break;
        for ( m = *(_QWORD *)(a4 + 24); m != *(_QWORD *)(a4 + 32); m += 32 )
        {
          if ( *(_QWORD *)(k + 24) < 8u )
            v61 = (_WORD *)k;
          else
            v61 = *(_WORD **)k;
          v62 = *(_QWORD *)(k + 16);
          v63 = *(_QWORD *)(m + 16);
          v64 = v63;
          if ( v63 >= v62 )
            v64 = *(_QWORD *)(k + 16);
          if ( *(_QWORD *)(m + 24) < 8u )
            v65 = (_WORD *)m;
          else
            v65 = *(_WORD **)m;
          if ( v64 )
          {
            while ( v64 )
            {
              if ( *v65 != *v61 )
              {
                v66 = -1;
                if ( *v65 >= *v61 )
                  v66 = 1;
                goto LABEL_88;
              }
              ++v65;
              ++v61;
              --v64;
            }
          }
          if ( v63 < v62 )
            v66 = -1;
          else
            v66 = v63 != v62;
LABEL_88:
          if ( !v66 )
          {
            NetSetupGraphBuilder::BuildPathsRecursively(
              (_DWORD)a1,
              (_DWORD)a2,
              (_DWORD)v10,
              *(_QWORD *)v47,
              v174,
              (__int64)a6,
              (__int64)a7,
              0,
              (__int64)v173);
            goto LABEL_91;
          }
        }
      }
LABEL_91:
      v47 += 8;
      v13 = a7;
    }
    v11 = a1;
    v12 = a6;
  }
  v49 = (_QWORD *)*v12;
  v50 = v12[1] - *v12;
  if ( v50 == 8 )
  {
    if ( !*(_BYTE *)(v9 + 193) )
      goto LABEL_59;
  }
  else if ( v50 != 16 || !*(_BYTE *)(v9 + 194) || *(_BYTE *)(v9 + 195) )
  {
    goto LABEL_59;
  }
  v74 = (_QWORD *)*v49;
  v165 = (_QWORD *)*v49;
  *(_OWORD *)v183 = 0;
  hKey = 0;
  v184 = 0;
  v75 = (__int64 *)v11[3];
  v76 = (__int64 *)v11[4];
  v77 = 0;
  while ( v75 != v76 )
  {
    v78 = *v75;
    if ( v12[1] - *v12 != 16 || *(_BYTE *)(v78 + 195) && *(_DWORD *)(v78 + 196) != 1 )
    {
      for ( n = *(_QWORD *)(v78 + 120); n != *(_QWORD *)(v78 + 128); n += 32 )
      {
        for ( ii = v74[3]; ii != v74[4]; ii += 32 )
        {
          if ( *(_QWORD *)(n + 24) < 8u )
            v98 = (_WORD *)n;
          else
            v98 = *(_WORD **)n;
          v99 = *(_QWORD *)(n + 16);
          v100 = *(_QWORD *)(ii + 16);
          v101 = v100;
          if ( v100 >= v99 )
            v101 = *(_QWORD *)(n + 16);
          if ( *(_QWORD *)(ii + 24) < 8u )
            v102 = (_WORD *)ii;
          else
            v102 = *(_WORD **)ii;
          if ( v101 )
          {
            while ( v101 )
            {
              if ( *v102 != *v98 )
              {
                v103 = -1;
                if ( *v102 >= *v98 )
                  v103 = 1;
                goto LABEL_168;
              }
              ++v102;
              ++v98;
              --v101;
            }
          }
          if ( v100 < v99 )
            v103 = -1;
          else
            v103 = v100 != v99;
LABEL_168:
          v104 = v103 == 0;
          v74 = v165;
          if ( v104 )
            goto LABEL_124;
        }
      }
      v85 = v74[12];
      v86 = v74[13];
      while ( v85 != v86 )
      {
        if ( (unsigned __int8)IsInRange(v78 + 48, v85) )
          goto LABEL_286;
        v85 += 32;
      }
      v87 = *(_QWORD *)(v78 + 144);
      v88 = *(_QWORD *)(v78 + 152);
      while ( v87 != v88 )
      {
        if ( (unsigned __int8)IsInRange(v165 + 6, v87) )
        {
          v74 = v165;
          goto LABEL_124;
        }
        v87 += 32;
      }
      v89 = *(_QWORD *)(v78 + 48);
      v74 = v165;
      while ( v89 != *(_QWORD *)(v78 + 56) )
      {
        for ( jj = v74[3]; jj != v74[4]; jj += 32 )
        {
          if ( *(_QWORD *)(v89 + 24) < 8u )
            v91 = (_WORD *)v89;
          else
            v91 = *(_WORD **)v89;
          v92 = *(_QWORD *)(v89 + 16);
          v93 = *(_QWORD *)(jj + 16);
          v94 = v93;
          if ( v93 >= v92 )
            v94 = *(_QWORD *)(v89 + 16);
          if ( *(_QWORD *)(jj + 24) < 8u )
            v95 = (_WORD *)jj;
          else
            v95 = *(_WORD **)jj;
          if ( v94 )
          {
            while ( v94 )
            {
              if ( *v95 != *v91 )
              {
                v96 = -1;
                if ( *v95 >= *v91 )
                  v96 = 1;
                goto LABEL_153;
              }
              ++v95;
              ++v91;
              --v94;
            }
          }
          if ( v93 < v92 )
            v96 = -1;
          else
            v96 = v93 != v92;
LABEL_153:
          if ( !v96 )
            goto LABEL_274;
          v74 = v165;
        }
        v89 += 32;
      }
      v138 = *(_QWORD *)(v78 + 72);
      v139 = *(_QWORD *)(v78 + 80);
LABEL_265:
      if ( v138 != v139 )
      {
        v140 = v74[6];
        v141 = v74[7];
        while ( 1 )
        {
          if ( v140 == v141 )
          {
            v138 += 32;
            v74 = v165;
            goto LABEL_265;
          }
          if ( (unsigned __int8)std::operator==<wchar_t>(v140, v138) )
            break;
          v140 = v142 + 32;
        }
LABEL_274:
        v143 = a6;
        v144 = a8;
        if ( a6[1] - *a6 == 8 && !*(_BYTE *)(v78 + 195) )
          v144 = ++a8;
        LODWORD(v186) = 0;
        if ( v77 == hKey && !(0xAAAAAAAAAAAAAAABuLL * (((char *)hKey - (char *)v77) >> 3)) )
        {
          v145 = 0xAAAAAAAAAAAAAAABuLL * (((char *)v77 - (char *)v183[0]) >> 3);
          if ( v145 == 0xAAAAAAAAAAAAAAALL )
            std::_Xlength_error("vector<T> too long");
          v146 = 0xAAAAAAAAAAAAAAABuLL * (((char *)hKey - (char *)v183[0]) >> 3);
          v147 = 0;
          if ( 0xAAAAAAAAAAAAAAALL - (v146 >> 1) >= v146 )
            v147 = v146 + (v146 >> 1);
          if ( v147 < v145 + 1 )
            v147 = v145 + 1;
          std::vector<std::vector<std::shared_ptr<NetSetupBindPath>>>::_Reallocate(v183, v147);
          hKey = v184;
          v77 = (HKEY)v183[1];
          v143 = a6;
        }
        v148 = (int)v77;
        *(_QWORD *)v77 = 0;
        *((_QWORD *)v77 + 1) = 0;
        *((_QWORD *)v77 + 2) = 0;
        v77 += 6;
        v183[1] = v77;
        NetSetupGraphBuilder::BuildPathsRecursively(
          (_DWORD)a1,
          (_DWORD)a2,
          v148,
          v78,
          v174,
          (__int64)v143,
          (__int64)a7,
          v144,
          (__int64)&v186);
LABEL_286:
        v74 = v165;
        ++v75;
        v12 = a6;
        continue;
      }
    }
LABEL_124:
    ++v75;
    v12 = a6;
  }
  v79 = (HKEY)v183[0];
  std::_Sort_std::vector_std::shared_ptr_NetSetupBindPath__std::allocator_std::shared_ptr_NetSetupBindPath__________int64__lambda_9f7126193d6d472f59b0c286d2d650bd___(
    v183[0],
    v77,
    0xAAAAAAAAAAAAAAABuLL * (((char *)v77 - (char *)v183[0]) >> 3),
    0);
  v80 = v79;
  v81 = v172;
  v82 = v173;
  while ( v80 != v77 )
  {
    v105 = *(__int64 **)v80;
    v106 = (__int64 *)*((_QWORD *)v80 + 1);
    while ( v105 != v106 )
    {
      v107 = *v105;
      *(_DWORD *)(*v105 + 116) += *v82;
      v108 = v81[1];
      if ( (unsigned __int64)v105 < v108 && *v81 <= (unsigned __int64)v105 )
      {
        v163 = (unsigned __int64)v105 - *v81;
        if ( v108 == v81[2] )
          std::vector<std::shared_ptr<NetSetupBindPath>>::_Reserve(v81);
        std::_Wrap_alloc<std::allocator<std::shared_ptr<NetSetupBindPath>>>::construct<std::shared_ptr<NetSetupBindPath>,std::shared_ptr<NetSetupBindPath>>(
          v107,
          (__int64 *)v81[1],
          (__int64 *)(*v81 + (v163 & 0xFFFFFFFFFFFFFFF0uLL)));
        v82 = v173;
      }
      else
      {
        if ( v108 == v81[2] )
          std::vector<std::shared_ptr<NetSetupBindPath>>::_Reserve(v81);
        v109 = (__int64 *)v81[1];
        *v109 = 0;
        v109[1] = 0;
        if ( v109 != v105 )
        {
          v109[1] = v105[1];
          v105[1] = 0;
          v110 = *v109;
          *v109 = *v105;
          *v105 = v110;
        }
      }
      v81[1] += 16LL;
      v105 += 2;
    }
    *v82 += (__int64)(*((_QWORD *)v80 + 1) - *(_QWORD *)v80) >> 4;
    v80 += 6;
  }
  if ( v79 )
  {
    for ( kk = v79; kk != v77; kk += 6 )
      std::vector<std::shared_ptr<NetSetupBindPath>>::_Tidy(kk);
    operator delete(v79);
  }
  v13 = a7;
  v12 = a6;
LABEL_59:
  v51 = v12[1];
  if ( *v12 != v51 )
    v12[1] = v51 - 8;
  result = v13[1];
  if ( *v13 != result )
  {
    result -= 8;
    v13[1] = result;
  }
  return result;
}

```

## disassembly

```asm
0x180022010  push    rbp
0x180022012  push    rbx
0x180022013  push    rsi
0x180022014  push    rdi
0x180022015  push    r12
0x180022017  push    r13
0x180022019  push    r14
0x18002201b  push    r15
0x18002201d  lea     rbp, [rsp-318h]
0x180022025  sub     rsp, 418h
0x18002202c  mov     [rbp+350h+var_358], 0FFFFFFFFFFFFFFFEh
0x180022034  movaps  [rsp+450h+var_50], xmm6
0x18002203c  mov     rax, cs:__security_cookie
0x180022043  xor     rax, rsp
0x180022046  mov     [rbp+350h+var_60], rax
0x18002204d  mov     r12, r9
0x180022050  mov     [rsp+450h+var_3F8], r9
0x180022055  mov     r13, r8
0x180022058  mov     [rbp+350h+var_3A0], r8
0x18002205c  mov     [rsp+450h+var_3E8], rdx
0x180022061  mov     rbx, rcx
0x180022064  mov     [rsp+450h+var_3E0], rcx
0x180022069  mov     rsi, [rbp+350h+arg_40]
0x180022070  mov     rax, [rbp+350h+arg_20]
0x180022077  mov     [rbp+350h+var_390], rax
0x18002207b  mov     r10, [rbp+350h+arg_28]
0x180022082  mov     [rsp+450h+var_400], r10
0x180022087  mov     r11, [rbp+350h+arg_30]
0x18002208e  mov     [rsp+450h+var_3F0], r11
0x180022093  mov     [rbp+350h+var_3B0], r9
0x180022097  mov     rax, [r10+8]
0x18002209b  lea     rcx, [rbp+350h+var_3B0]
0x18002209f  cmp     rcx, rax
0x1800220a2  jnb     short loc_1800220B1
0x1800220a4  lea     rcx, [rbp+350h+var_3B0]
0x1800220a8  cmp     [r10], rcx
0x1800220ab  jbe     loc_1800232D7
0x1800220b1  cmp     rax, [r10+10h]
0x1800220b5  jz      loc_18002271E
0x1800220bb  mov     rax, [r10+8]
0x1800220bf  mov     [rax], r12
0x1800220c2  mov     rcx, [r10+8]
0x1800220c6  lea     rax, [rcx+8]
0x1800220ca  mov     [r10+8], rax
0x1800220ce  add     rcx, 8
0x1800220d2  mov     [rbp+350h+var_318], 0
0x1800220d9  cmp     byte ptr [r12+0C1h], 0
0x1800220e2  jz      loc_180022704
0x1800220e8  cmp     byte ptr [r12+0D4h], 0
0x1800220f1  jz      loc_180022704
0x1800220f7  mov     edi, 119h
0x1800220fc  cmp     [r12+0DEh], di
0x180022105  jnb     loc_180022709
0x18002210b  mov     al, 1
0x18002210d  lea     r15, [rbp+350h+var_318]
0x180022111  test    al, al
0x180022113  cmovz   r15, rsi
0x180022117  mov     [rbp+350h+var_398], r15
0x18002211b  sub     rcx, [r10]
0x18002211e  sar     rcx, 3
0x180022122  cmp     rcx, 2
0x180022126  jb      loc_18002243B
0x18002212c  mov     rax, [r11+8]
0x180022130  xor     esi, esi
0x180022132  cmp     [r11], rax
0x180022135  jz      loc_1800226D0
0x18002213b  mov     rax, [rax-8]
0x18002213f  mov     [rbp+350h+hKey], rax
0x180022143  lea     r8, [rbp+350h+hKey]
0x180022147  mov     rdx, r10
0x18002214a  lea     rcx, [rbp+350h+Block]
0x18002214e  call    ??$make_shared@VNetSetupBindPath@@AEAV?$vector@PEAVNetSetupBindNode@@V?$allocator@PEAVNetSetupBindNode@@@std@@@std@@AEAPEBV1@@std@@YA?AV?$shared_ptr@VNetSetupBindPath@@@0@AEAV?$vector@PEAVNetSetupBindNode@@V?$allocator@PEAVNetSetupBindNode@@@std@@@0@AEAPEBVNetSetupBindPath@@@Z; std::make_shared<NetSetupBindPath,std::vector<NetSetupBindNode *> &,NetSetupBindPath const * &>(std::vector<NetSetupBindNode *> &,NetSetupBindPath const * &)
0x180022153  mov     rbx, rax
0x180022156  mov     rax, [r13+8]
0x18002215a  cmp     rbx, rax
0x18002215d  jnb     short loc_180022169
0x18002215f  cmp     [r13+0], rbx
0x180022163  jbe     loc_180023312
0x180022169  cmp     rax, [r13+10h]
0x18002216d  jz      loc_1800226F7
0x180022173  mov     rdx, [r13+8]
0x180022177  mov     [rdx], rsi
0x18002217a  mov     [rdx+8], rsi
0x18002217e  cmp     rdx, rbx
0x180022181  jz      short loc_18002219B
0x180022183  mov     rax, [rbx+8]
0x180022187  mov     [rdx+8], rax
0x18002218b  mov     [rbx+8], rsi
0x18002218f  mov     rcx, [rdx]
0x180022192  mov     rax, [rbx]
0x180022195  mov     [rdx], rax
0x180022198  mov     [rbx], rcx
0x18002219b  add     qword ptr [r13+8], 10h
0x1800221a0  mov     rbx, [rbp+350h+Block+8]
0x1800221a4  test    rbx, rbx
0x1800221a7  jz      short loc_1800221E5
0x1800221a9  mov     eax, 0FFFFFFFFh
0x1800221ae  lock xadd [rbx+8], eax
0x1800221b3  cmp     eax, 1
0x1800221b6  jnz     short loc_1800221E5
0x1800221b8  mov     rax, [rbx]
0x1800221bb  mov     rcx, rbx
0x1800221be  mov     rax, [rax]
0x1800221c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221c6  mov     eax, 0FFFFFFFFh
0x1800221cb  lock xadd [rbx+0Ch], eax
0x1800221d0  cmp     eax, 1
0x1800221d3  jnz     short loc_1800221E5
0x1800221d5  mov     rax, [rbx]
0x1800221d8  mov     rcx, rbx
0x1800221db  mov     rax, [rax+8]
0x1800221df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221e4  nop
0x1800221e5  mov     rax, [r13+8]
0x1800221e9  mov     r13, [rax-10h]
0x1800221ed  xorps   xmm0, xmm0
0x1800221f0  movups  xmmword ptr [r13+20h], xmm0
0x1800221f5  mov     r8, [rsp+450h+var_400]
0x1800221fa  mov     rax, [r8]
0x1800221fd  mov     rcx, [r8+8]
0x180022201  cmp     rax, rcx
0x180022204  jz      short loc_18002223B
0x180022206  mov     r9, [rax]
0x180022209  mov     r8d, [r13+24h]
0x18002220d  xor     r8d, [r9+4]
0x180022211  mov     [r13+20h], r8d
0x180022215  mov     edx, [r9+8]
0x180022219  xor     edx, [r13+28h]
0x18002221d  mov     [r13+24h], edx
0x180022221  mov     edx, [r9+0Ch]
0x180022225  xor     edx, [r13+2Ch]
0x180022229  mov     [r13+28h], edx
0x18002222d  xor     r8d, [r9+10h]
0x180022231  mov     [r13+2Ch], r8d
0x180022235  add     rax, 8
0x180022239  jmp     short loc_180022201
0x18002223b  movzx   eax, byte ptr [r13+28h]
0x180022240  and     al, 1Fh
0x180022242  or      al, 0C0h
0x180022244  mov     [r13+28h], al
0x180022248  mov     rax, [rsp+450h+var_400]
0x18002224d  mov     rdx, [rax+8]
0x180022251  sub     rdx, [rax]
0x180022254  sar     rdx, 3
0x180022258  movzx   ecx, [rbp+350h+arg_38]
0x18002225f  cmp     rdx, 2
0x180022263  cmovbe  cx, si
0x180022267  mov     [r13+70h], cx
0x18002226c  movzx   eax, byte ptr [r12+0C3h]
0x180022275  mov     [r13+72h], al
0x180022279  inc     dword ptr [r15]
0x18002227c  mov     edx, [r15]
0x18002227f  mov     rax, [r13+38h]
0x180022283  mov     rcx, [rax]
0x180022286  inc     dword ptr [rcx+0E0h]
0x18002228c  mov     r9d, [rcx+0E0h]
0x180022293  cmp     byte ptr [rcx+0C1h], 0
0x18002229a  jz      loc_180022735
0x1800222a0  cmp     byte ptr [rcx+0D4h], 0
0x1800222a7  jz      loc_180022735
0x1800222ad  cmp     [rcx+0DEh], di
0x1800222b4  jnb     loc_180022735
0x1800222ba  cmp     r9d, 7Fh
0x1800222be  ja      loc_18002333D
0x1800222c4  mov     rcx, [rcx+0D8h]
0x1800222cb  mov     r8, rcx
0x1800222ce  shr     r8, 18h
0x1800222d2  mov     rax, r8
0x1800222d5  and     eax, 0FFFFFFh
0x1800222da  cmp     rax, 0FFFFh
0x1800222e0  ja      loc_180023398
0x1800222e6  shr     rcx, 30h
0x1800222ea  shl     ecx, 10h
0x1800222ed  movzx   eax, r8w
0x1800222f1  or      ecx, eax
0x1800222f3  shl     ecx, 7
0x1800222f6  and     edx, 7Fh
0x1800222f9  or      ecx, edx
0x1800222fb  mov     [r13+74h], ecx
0x1800222ff  movzx   eax, byte ptr [r12+0C0h]
0x180022308  mov     [r13+30h], al
0x18002230c  lea     r15, [r13+0A0h]
0x180022313  cmp     qword ptr [r15], 0
0x180022317  jnz     loc_180022A41
0x18002231d  mov     ecx, [r13+78h]
0x180022321  test    ecx, ecx
0x180022323  jnz     loc_180022E8E
0x180022329  lea     rdx, [r13+20h]
0x18002232d  lea     rcx, [rbp+350h+Block]
0x180022331  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180022336  cmp     qword ptr [rax+18h], 8
0x18002233b  jb      short loc_180022340
0x18002233d  mov     rax, [rax]
0x180022340  mov     r9, rax
0x180022343  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\BindPaths\\%ws"
0x18002234a  mov     edx, 104h; BufferCount
0x18002234f  lea     rcx, [rbp+350h+Buffer]; Buffer
0x180022356  call    cs:__imp_swprintf_s
0x18002235c  cmp     [rbp+350h+var_3B8], 8
0x180022361  jnb     loc_180022710
0x180022367  mov     rbx, rsi
0x18002236a  mov     ecx, [r13+78h]
0x18002236e  test    ecx, ecx
0x180022370  jnz     loc_18002318D
0x180022376  mov     rbx, [rsp+450h+var_3E8]
0x18002237b  add     rbx, 18h
0x18002237f  lea     r8, aProperties; "\\Properties"
0x180022386  mov     edx, 104h; SizeInWords
0x18002238b  lea     rcx, [rbp+350h+Buffer]; Destination
0x180022392  call    cs:__imp_wcscat_s
0x180022398  mov     [rsp+450h+var_430], rsi
0x18002239d  mov     r9d, 0Eh
0x1800223a3  lea     r8, [rbp+350h+Buffer]
0x1800223aa  lea     rdx, [rbp+350h+hKey]
0x1800223ae  mov     rcx, rbx
0x1800223b1  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x1800223b6  mov     rsi, [rax]
0x1800223b9  mov     qword ptr [rax], 0
0x1800223c0  mov     rbx, rsi
0x1800223c3  mov     [rbp+350h+var_310], rbx
0x1800223c7  mov     rcx, [rbp+350h+hKey]; hKey
0x1800223cb  test    rcx, rcx
0x1800223ce  jz      short loc_1800223D7
0x1800223d0  call    cs:__imp_RegCloseKey
0x1800223d6  nop
0x1800223d7  test    rsi, rsi
0x1800223da  jnz     loc_1800231FC
0x1800223e0  xor     esi, esi
0x1800223e2  cmp     [r15], rsi
0x1800223e5  jnz     loc_180022A41
0x1800223eb  mov     byte ptr [r12+0C8h], 1
0x1800223f4  mov     [rbp+350h+var_3A8], r13
0x1800223f8  mov     r11, [rsp+450h+var_3F0]
0x1800223fd  mov     rax, [r11+8]
0x180022401  lea     rcx, [rbp+350h+var_3A8]
0x180022405  cmp     rcx, rax
0x180022408  jb      loc_180022692
0x18002240e  cmp     rax, [r11+10h]
0x180022412  jnz     short loc_180022421
0x180022414  mov     rcx, r11
0x180022417  call    ?_Reserve@?$vector@PEBVNetSetupLoadedPlugin@@V?$allocator@PEBVNetSetupLoadedPlugin@@@std@@@std@@IEAAX_K@Z; std::vector<NetSetupLoadedPlugin const *>::_Reserve(unsigned __int64)
0x18002241c  mov     r11, [rsp+450h+var_3F0]
0x180022421  mov     rax, [r11+8]
0x180022425  mov     [rax], r13
0x180022428  mov     r10, [rsp+450h+var_400]
0x18002242d  mov     rbx, [rsp+450h+var_3E0]
0x180022432  mov     r13, [rbp+350h+var_3A0]
0x180022436  add     qword ptr [r11+8], 8
0x18002243b  cmp     byte ptr [r12+0C2h], 0
0x180022444  jnz     short loc_18002245F
0x180022446  mov     rsi, [rbx+30h]
0x18002244a  mov     r14, [rbx+38h]
0x18002244e  xchg    ax, ax
0x180022450  cmp     rsi, r14
0x180022453  jnz     short loc_1800224CA
0x180022455  mov     rbx, [rsp+450h+var_3E0]
0x18002245a  mov     r10, [rsp+450h+var_400]
0x18002245f  mov     rcx, [r10]
0x180022462  mov     rax, [r10+8]
0x180022466  sub     rax, rcx
0x180022469  cmp     rax, 8
0x18002246d  jz      loc_18002274D
0x180022473  cmp     rax, 10h
0x180022477  jz      loc_1800226D8
0x18002247d  mov     rax, [r10+8]
0x180022481  cmp     [r10], rax
0x180022484  jz      short loc_18002248E
0x180022486  add     rax, 0FFFFFFFFFFFFFFF8h
0x18002248a  mov     [r10+8], rax
0x18002248e  mov     rax, [r11+8]
0x180022492  cmp     [r11], rax
0x180022495  jz      short loc_18002249F
0x180022497  add     rax, 0FFFFFFFFFFFFFFF8h
0x18002249b  mov     [r11+8], rax
0x18002249f  mov     rcx, [rbp+350h+var_60]
0x1800224a6  xor     rcx, rsp; StackCookie
0x1800224a9  call    __security_check_cookie
0x1800224ae  movaps  xmm6, [rsp+450h+var_50]
0x1800224b6  add     rsp, 418h
0x1800224bd  pop     r15
0x1800224bf  pop     r14
0x1800224c1  pop     r13
0x1800224c3  pop     r12
0x1800224c5  pop     rdi
0x1800224c6  pop     rsi
0x1800224c7  pop     rbx
0x1800224c8  pop     rbp
0x1800224c9  retn
0x1800224ca  mov     r15, [rsi]
0x1800224cd  mov     rax, [r15+78h]
0x1800224d1  cmp     rax, [r15+80h]
0x1800224d8  jz      short loc_1800224F0
0x1800224da  mov     rcx, [r12+18h]
0x1800224df  cmp     rcx, [r12+20h]
0x1800224e4  jnz     loc_18002261B
0x1800224ea  add     rax, 20h ; ' '
0x1800224ee  jmp     short loc_1800224D1
0x1800224f0  mov     rbx, [r12+60h]
0x1800224f5  mov     rdi, [r12+68h]
0x1800224fa  lea     r12, [r15+30h]
  ... truncated ...
```
