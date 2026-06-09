# WriteTdiKernelSummary

- ea: `0x180024b2c`
- end: `0x180025c0f`
- name: `WriteTdiKernelSummary`
- size: `4323`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027b90`

## callees

- `0x180005580`
- `0x180005c94`
- `0x18000a430`
- `0x18000d474`
- `0x18000e8ec`
- `0x18000e970`
- `0x18000fd70`
- `0x180010200`
- `0x180011740`
- `0x180015f50`
- `0x18001f2c4`
- `0x180024330`
- `0x180024b2c`
- `0x180025c18`
- `0x180025cf0`
- `0x180025dc4`
- `0x180026174`
- `0x1800261ac`
- `0x1800262a8`
- `0x18002687c`
- `0x180026930`
- `0x180026c30`
- `0x180027478`
- `0x180029d20`
- `0x18002eb20`
- `0x180034f00`
- `0x18003b454`
- `0x18003f270`
- `0x1800410f4`
- `0x180041624`
- `0x180042e24`
- `0x180043428`
- `0x18004c9cc`
- `0x180058590`
- `0x180064704`
- `0x180072254`
- `0x1800722d0`
- `0x1800810d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025331`
- `msvcrt!_wcsicmp` at `0x1800257ef`
- `msvcrt!_wcsicmp` at `0x180025331`
- `msvcrt!_wcsicmp` at `0x1800257ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024eea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024eea`

## string_xrefs

- `0x180024c2c`: `Services\%s\Linkage`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall WriteTdiKernelSummary(__int64 a1, __int64 a2, void ***a3, int a4, __int64 a5)
{
  void ***v5; // r14
  char v7; // di
  bool Boolean; // bl
  void **v9; // r8
  __int64 ValueMultiSz; // rax
  const unsigned __int8 *v11; // rbx
  const unsigned __int8 *v12; // r12
  __int64 v13; // r8
  unsigned __int64 i; // rdx
  __int64 v15; // r9
  const unsigned __int8 *v16; // rsi
  const unsigned __int8 *v17; // r13
  __int64 v18; // r8
  unsigned __int64 j; // rdx
  __int64 v20; // r8
  char v21; // r9
  __int64 v22; // r8
  unsigned __int64 k; // rdx
  char v24; // al
  __int64 v25; // rsi
  __int64 *v26; // r15
  __int64 *m; // r14
  __int64 v29; // rbx
  unsigned __int64 v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rsi
  __int64 v33; // rbx
  unsigned __int64 v34; // rdi
  char v35; // di
  int v36; // ebx
  int *v37; // rax
  __int64 v38; // rbx
  __int64 v39; // r8
  wchar_t *v40; // r15
  wchar_t *v41; // r9
  const wchar_t *v42; // rbx
  const unsigned __int8 *v43; // r14
  const unsigned __int8 *v44; // rsi
  const unsigned __int8 *v45; // rcx
  const unsigned __int8 *v46; // rdi
  const unsigned __int8 *v47; // rax
  const unsigned __int8 *v48; // rax
  bool v49; // zf
  const unsigned __int8 *v50; // rax
  __int64 v51; // rax
  const unsigned __int8 *v52; // rax
  const wchar_t *v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  const unsigned __int8 *v57; // rbx
  const unsigned __int8 *v58; // rax
  const unsigned __int8 *v59; // rax
  wchar_t **v60; // rax
  __int64 v61; // rcx
  const unsigned __int8 *v62; // rdx
  void **v63; // rcx
  __int64 v64; // rax
  const unsigned __int8 *v65; // rdx
  void **v66; // rax
  __int64 v67; // rcx
  const unsigned __int8 *v68; // rdx
  wchar_t **v69; // rax
  char *v70; // rdx
  wchar_t **v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  wchar_t **v74; // rcx
  char *v75; // rdx
  wchar_t **v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  wchar_t *v79; // rax
  wchar_t *v80; // r8
  const wchar_t *v81; // rdi
  const unsigned __int8 *v82; // rdx
  const unsigned __int8 *v83; // rsi
  const unsigned __int8 *v84; // rcx
  const unsigned __int8 *v85; // rbx
  const unsigned __int8 *v86; // rax
  const unsigned __int8 *v87; // rax
  const unsigned __int8 *v88; // rax
  const wchar_t *v89; // rdx
  __int64 v90; // r8
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rax
  unsigned __int64 v96; // rax
  __int64 v97; // r11
  _QWORD *v98; // rdi
  unsigned __int64 v99; // rbx
  unsigned __int64 v100; // rax
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // r11
  __int64 v104; // rax
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 v107; // r8
  __int64 v108; // r9
  _QWORD *v109; // r13
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // r9
  __int64 v115; // rdx
  __int64 v116; // r8
  int v117; // r10d
  int v118; // r11d
  __int64 v119; // rax
  void **v120; // rax
  __int64 v121; // rdx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v123; // [rsp+58h] [rbp-A8h] BYREF
  int v124; // [rsp+5Ch] [rbp-A4h]
  __int64 *v125; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  char *v127; // [rsp+78h] [rbp-88h]
  __int64 v128; // [rsp+90h] [rbp-70h]
  __int64 v129; // [rsp+98h] [rbp-68h]
  void ***v130; // [rsp+A0h] [rbp-60h]
  __int64 *v131; // [rsp+A8h] [rbp-58h]
  _QWORD v132[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v133[3]; // [rsp+C0h] [rbp-40h] BYREF
  char v134[8]; // [rsp+D8h] [rbp-28h] BYREF
  char v135[8]; // [rsp+E0h] [rbp-20h] BYREF
  char v136[8]; // [rsp+E8h] [rbp-18h] BYREF
  char v137[32]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *String1[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v139; // [rsp+120h] [rbp+20h]
  __int128 v140; // [rsp+128h] [rbp+28h] BYREF
  __int64 v141; // [rsp+138h] [rbp+38h]
  wchar_t *String2[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v143; // [rsp+150h] [rbp+50h]
  unsigned __int64 v144; // [rsp+158h] [rbp+58h]
  __int128 v145; // [rsp+160h] [rbp+60h] BYREF
  __int64 v146; // [rsp+170h] [rbp+70h]
  unsigned __int64 v147; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v148; // [rsp+180h] [rbp+80h]
  __int64 v149; // [rsp+188h] [rbp+88h]
  unsigned __int64 v150; // [rsp+190h] [rbp+90h] BYREF
  int *v151; // [rsp+198h] [rbp+98h]
  int *v152; // [rsp+1A0h] [rbp+A0h]
  void *v153[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned __int64 v154; // [rsp+1C0h] [rbp+C0h]
  void *v155[3]; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int64 v156; // [rsp+1E0h] [rbp+E0h]
  GUID v157; // [rsp+1E8h] [rbp+E8h] BYREF
  int v158; // [rsp+1F8h] [rbp+F8h]
  int v159; // [rsp+1FCh] [rbp+FCh]
  __int128 v160; // [rsp+200h] [rbp+100h] BYREF
  __int64 v161; // [rsp+210h] [rbp+110h]
  void *v162[3]; // [rsp+218h] [rbp+118h] BYREF
  unsigned __int64 v163; // [rsp+230h] [rbp+130h]
  void *v164[2]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v165; // [rsp+248h] [rbp+148h]
  unsigned __int64 v166; // [rsp+250h] [rbp+150h]
  WCHAR v167[264]; // [rsp+260h] [rbp+160h] BYREF

  v133[2] = -2;
  v124 = a4;
  v5 = a3;
  v130 = a3;
  v129 = a2;
  v128 = a5;
  v7 = 0;
  v140 = 0;
  v141 = 0;
  v145 = 0;
  v146 = 0;
  *(_OWORD *)String1 = 0;
  v139 = 0;
  NetSetup2::ActiveObject::GetProperty(a3, &v157, (__int128 *)&NETSETUPPKEY_ProtocolDriver_SkipLinkageKeyGeneration, 0);
  Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v157);
  std::vector<_NETSETUPPROPKEY>::_Tidy(&v160);
  if ( Boolean )
    goto LABEL_44;
  NetSetup2::ActiveObject::GetProperty(v5, &v157, &NETSETUPPKEY_Driver_BindName, 0);
  NetSetup2::Property::GetString(&v157, v155);
  std::vector<_NETSETUPPROPKEY>::_Tidy(&v160);
  v9 = v155;
  if ( v156 >= 8 )
    v9 = (void **)v155[0];
  swprintf_s<260>(v167, L"Services\\%s\\Linkage", v9);
  RegistryKey::CreateSubKey((HKEY *)(a1 + 24), (HKEY)&hKey, v167, 3u, 0, 0);
  if ( RegistryKey::ValueExists((RegistryKey *)&hKey, L"Export") )
  {
    ValueMultiSz = RegistryKey::GetValueMultiSz(&hKey, &Block, L"Export");
    std::vector<unsigned char>::operator=(&v140, ValueMultiSz);
    std::vector<_NETSETUPPROPKEY>::_Tidy(&Block);
    MultiSz::fix_null_terminator((MultiSz *)&v140);
  }
  if ( RegistryKey::ValueExists((RegistryKey *)&hKey, L"Bind") )
  {
    v94 = RegistryKey::GetValueMultiSz(&hKey, &Block, L"Bind");
    std::vector<unsigned char>::operator=(&v145, v94);
    std::vector<_NETSETUPPROPKEY>::_Tidy(&Block);
    MultiSz::fix_null_terminator((MultiSz *)&v145);
  }
  if ( RegistryKey::ValueExists((RegistryKey *)&hKey, L"Route") )
  {
    v95 = RegistryKey::GetValueMultiSz(&hKey, &Block, L"Route");
    std::vector<unsigned char>::operator=(String1, v95);
    std::vector<_NETSETUPPROPKEY>::_Tidy(&Block);
    MultiSz::fix_null_terminator((MultiSz *)String1);
  }
  v147 = 0;
  v148 = 0;
  v149 = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v11 = (const unsigned __int8 *)*((_QWORD *)&v140 + 1);
  v12 = (const unsigned __int8 *)v140;
  if ( (_QWORD)v140 == *((_QWORD *)&v140 + 1) || !*(_WORD *)v140 )
  {
    v15 = 0;
  }
  else
  {
    v13 = 0;
    for ( i = 0; i < (*((_QWORD *)&v140 + 1) - (_QWORD)v140) >> 1; ++i )
      v13 += *(_WORD *)(v140 + 2 * i) == 0;
    v15 = v13 - 1;
  }
  v16 = (const unsigned __int8 *)*((_QWORD *)&v145 + 1);
  v17 = (const unsigned __int8 *)v145;
  if ( (_QWORD)v145 == *((_QWORD *)&v145 + 1) || !*(_WORD *)v145 )
  {
    v20 = 0;
  }
  else
  {
    v18 = 0;
    for ( j = 0; j < (*((_QWORD *)&v145 + 1) - (_QWORD)v145) >> 1; ++j )
      v18 += *(_WORD *)(v145 + 2 * j) == 0;
    v20 = v18 - 1;
  }
  if ( v15 != v20 || (MultiSz::count((MultiSz *)String1), v96 = MultiSz::count((MultiSz *)&v140), v21 = 1, v96 != v97) )
    v21 = 0;
  if ( v12 == v11 || !*(_WORD *)v12 )
    goto LABEL_27;
  v22 = 0;
  for ( k = 0; k < (unsigned __int64)(v11 - v12) >> 1; ++k )
    v22 += *(_WORD *)&v12[2 * k] == 0;
  if ( v22 == 2 && (String1[0] == String1[1] || !*String1[0]) && (v17 == v16 || !*(_WORD *)v17) )
    v24 = 1;
  else
LABEL_27:
    v24 = 0;
  v25 = -1;
  if ( v21 || v24 )
  {
    if ( v24 )
      v11 = v12;
    *((_QWORD *)&v140 + 1) = v11;
    v26 = *(__int64 **)(a1 + 664);
    v131 = v26;
    for ( m = (__int64 *)*v26; ; m = (__int64 *)*m )
    {
      v125 = m;
      if ( m == v26 )
        break;
      v157 = (GUID)*((_OWORD *)m + 1);
      LOBYTE(v158) = *((_BYTE *)m + 32);
      std::vector<std::wstring>::vector<std::wstring>(&v160, m + 5);
      v29 = *((_QWORD *)&v160 + 1);
      if ( (unsigned __int8)std::operator==<wchar_t>(*((_QWORD *)&v160 + 1) - 32LL, v155) )
      {
        v30 = 7;
        v144 = 7;
        v31 = 0;
        v143 = 0;
        LOWORD(String2[0]) = 0;
        v166 = 7;
        v165 = 0;
        LOWORD(v164[0]) = 0;
        v32 = v160;
        v33 = ((v29 - (__int64)v160) >> 5) - 1;
        if ( v33 )
        {
          while ( 1 )
          {
            if ( v31 )
            {
              std::wstring::push_back(String2, 32, v30);
              v30 = v144;
              v31 = v143;
            }
            v69 = String2;
            if ( v30 >= 8 )
              v69 = (wchar_t **)String2[0];
            v70 = (char *)v69 + 2 * v31;
            v71 = String2;
            if ( v30 >= 8 )
              v71 = (wchar_t **)String2[0];
            if ( v70 )
              v72 = (v70 - (char *)v71) >> 1;
            else
              v72 = 0;
            std::wstring::insert(String2, v72, v30, 34);
            std::wstring::append(String2, 32 * v33 + v32 - 32, 0, -1);
            v74 = String2;
            if ( v144 >= 8 )
              v74 = (wchar_t **)String2[0];
            v75 = (char *)v74 + 2 * v143;
            v76 = String2;
            if ( v144 >= 8 )
              v76 = (wchar_t **)String2[0];
            if ( v75 )
              v77 = (v75 - (char *)v76) >> 1;
            else
              v77 = 0;
            std::wstring::insert(String2, v77, v73, 34);
            if ( v165 )
              std::wstring::push_back(v164, 95, v78);
            std::wstring::append(v164, 32 * v33-- + v32 - 32, 0, -1);
            if ( !v33 )
              break;
            v30 = v144;
            v31 = v143;
          }
          m = v125;
          v26 = v131;
        }
        std::wstring::wstring(v162, L"\\Device\\");
        std::wstring::append(v162, v164, 0, -1);
        v34 = v148;
        if ( (unsigned __int64)v162 >= v148 || v147 > (unsigned __int64)v162 )
        {
          if ( v148 == v149 )
          {
            std::vector<std::wstring>::_Reserve(&v147);
            v34 = v148;
          }
          *(_QWORD *)(v34 + 24) = 7;
          *(_QWORD *)(v34 + 16) = 0;
          *(_WORD *)v34 = 0;
          std::wstring::assign(v34, v162, 0, -1);
        }
        else
        {
          if ( v148 == v149 )
          {
            std::vector<std::wstring>::_Reserve(&v147);
            v34 = v148;
          }
          std::wstring::wstring(v34);
        }
        v148 = v34 + 32;
        v35 = v158;
        v36 = (_BYTE)v158 == 0 ? 2 : 0;
        v123 = v36;
        v37 = v151;
        if ( &v123 >= v151 || v150 > (unsigned __int64)&v123 )
        {
          if ( v151 == v152 )
          {
            std::vector<unsigned long>::_Reserve(&v150, 1);
            v37 = v151;
          }
          *v37 = v36;
        }
        else
        {
          v38 = (__int64)((__int64)&v123 - v150) >> 2;
          if ( v151 == v152 )
            std::vector<unsigned long>::_Reserve(&v150, 1);
          v37 = v151;
          *v151 = *(_DWORD *)(v150 + 4 * v38);
        }
        v151 = v37 + 1;
        if ( v35 )
        {
          std::wstring::wstring(v153, L"\\Device\\");
          std::wstring::append(v153, v155, 0, -1);
          if ( v165 )
            std::wstring::push_back(v153, 95, v39);
          std::wstring::append(v153, v164, 0, -1);
          v40 = String1[0];
          v41 = String1[1];
          if ( String1[0] == String1[1] || (v42 = String1[0], !*String1[0]) )
            v42 = (const wchar_t *)&MultiSz::emptyMultiSz;
          v43 = (const unsigned __int8 *)*((_QWORD *)&v140 + 1);
          if ( v12 == *((const unsigned __int8 **)&v140 + 1) || (v44 = v12, !*(_WORD *)v12) )
            v44 = &MultiSz::emptyMultiSz;
          v45 = (const unsigned __int8 *)*((_QWORD *)&v145 + 1);
          if ( v17 == *((const unsigned __int8 **)&v145 + 1) || (v46 = v17, !*(_WORD *)v17) )
            v46 = &MultiSz::emptyMultiSz;
          while ( 1 )
          {
            if ( v40 == v41 || (v47 = (const unsigned __int8 *)(v41 - 1), !*v40) )
              v47 = &MultiSz::emptyMultiSz;
            if ( v42 == (const wchar_t *)v47 )
              break;
            if ( v12 == v43 || (v48 = v43 - 2, !*(_WORD *)v12) )
              v48 = &MultiSz::emptyMultiSz;
            if ( v44 == v48 )
              break;
            if ( v17 == v45 || (v52 = v45 - 2, !*(_WORD *)v17) )
              v52 = &MultiSz::emptyMultiSz;
            if ( v46 == v52 )
              break;
            v53 = (const wchar_t *)String2;
            if ( v144 >= 8 )
              v53 = String2[0];
            if ( !_wcsicmp(v42, v53) )
            {
              v45 = (const unsigned __int8 *)*((_QWORD *)&v145 + 1);
              v41 = String1[1];
              break;
            }
            v54 = -1;
            do
              ++v54;
            while ( v42[v54] );
            v42 += v54 + 1;
            v55 = -1;
            do
              ++v55;
            while ( *(_WORD *)&v44[2 * v55] );
            v44 += 2 * v55 + 2;
            v56 = -1;
            do
              ++v56;
            while ( *(_WORD *)&v46[2 * v56] );
            v46 += 2 * v56 + 2;
            v45 = (const unsigned __int8 *)*((_QWORD *)&v145 + 1);
            v41 = String1[1];
          }
          v49 = v40 == v41;
          m = v125;
          v26 = v131;
          if ( v49 || (v50 = (const unsigned __int8 *)(v41 - 1), !*String1[0]) )
            v50 = &MultiSz::emptyMultiSz;
          if ( v42 != (const wchar_t *)v50 )
            goto LABEL_77;
          v57 = (const unsigned __int8 *)*((_QWORD *)&v140 + 1);
          if ( v12 == *((const unsigned __int8 **)&v140 + 1)
            || (v58 = (const unsigned __int8 *)(*((_QWORD *)&v140 + 1) - 2LL), !*(_WORD *)v12) )
          {
            v58 = &MultiSz::emptyMultiSz;
          }
          if ( v44 != v58 )
            goto LABEL_77;
          if ( v17 == v45 || (v59 = v45 - 2, !*(_WORD *)v17) )
            v59 = &MultiSz::emptyMultiSz;
          if ( v46 == v59 )
          {
            v60 = String2;
            if ( v144 >= 8 )
              v60 = (wchar_t **)String2[0];
            v61 = -1;
            do
              ++v61;
            while ( *((_WORD *)v60 + v61) );
            if ( String1[0] == v41 || (v62 = (const unsigned __int8 *)(v41 - 1), !*String1[0]) )
              v62 = &MultiSz::emptyMultiSz;
            v132[0] = v60;
            v132[1] = (char *)v60 + 2 * v61;
            MultiSz::insert(String1, v62, v132);
            v63 = v162;
            if ( v163 >= 8 )
              v63 = (void **)v162[0];
            v64 = -1;
            do
              ++v64;
            while ( *((_WORD *)v63 + v64) );
            if ( v17 == *((const unsigned __int8 **)&v145 + 1)
              || (v65 = (const unsigned __int8 *)(*((_QWORD *)&v145 + 1) - 2LL), !*(_WORD *)v17) )
            {
              v65 = &MultiSz::emptyMultiSz;
            }
            v133[0] = v63;
            v133[1] = (char *)v63 + 2 * v64;
            MultiSz::insert(&v145, v65, v133);
            v66 = v153;
            if ( v154 >= 8 )
              v66 = (void **)v153[0];
            v67 = -1;
            do
              ++v67;
            while ( *((_WORD *)v66 + v67) );
            if ( v12 == v57 || (v68 = v57 - 2, !*(_WORD *)v12) )
              v68 = &MultiSz::emptyMultiSz;
            Block = v66;
            v127 = (char *)v66 + 2 * v67;
            MultiSz::insert(&v140, v68, &Block);
          }
          else
          {
LABEL_77:
            v51 = std::wstring::wstring(v137);
            GetLinkageLists(
              v129,
              (_DWORD)v130,
              v124,
              v128,
              v51,
              (__int64)&v140,
              (__int64)&v145,
              (__int64)String1,
              (__int64)&v147);
          }
          if ( v154 >= 8 )
            operator delete(v153[0]);
        }
        else
        {
          v79 = String1[0];
          v80 = String1[1];
          if ( String1[0] == String1[1] || (v81 = String1[0], !*String1[0]) )
            v81 = (const wchar_t *)&MultiSz::emptyMultiSz;
          v82 = (const unsigned __int8 *)*((_QWORD *)&v145 + 1);
          if ( v17 == *((const unsigned __int8 **)&v145 + 1) || (v83 = v17, !*(_WORD *)v17) )
            v83 = &MultiSz::emptyMultiSz;
          v84 = (const unsigned __int8 *)*((_QWORD *)&v140 + 1);
          if ( v12 == *((const unsigned __int8 **)&v140 + 1) || (v85 = v12, !*(_WORD *)v12) )
            v85 = &MultiSz::emptyMultiSz;
          while ( 1 )
          {
            if ( v79 == v80 || (v49 = *v79 == 0, v86 = (const unsigned __int8 *)(v80 - 1), v49) )
              v86 = &MultiSz::emptyMultiSz;
            if ( v81 == (const wchar_t *)v86 )
              break;
            if ( v17 == v82 || (v87 = v82 - 2, !*(_WORD *)v17) )
              v87 = &MultiSz::emptyMultiSz;
            if ( v83 == v87 )
              break;
            if ( v12 == v84 || (v88 = v84 - 2, !*(_WORD *)v12) )
              v88 = &MultiSz::emptyMultiSz;
            if ( v85 == v88 )
              break;
            v89 = (const wchar_t *)String2;
            if ( v144 >= 8 )
              v89 = String2[0];
            if ( !_wcsicmp(v81, v89) )
            {
              MultiSz::erase(String1, v81, v90, 0);
              MultiSz::erase(&v145, v83, v105, v106);
              MultiSz::erase(&v140, v85, v107, v108);
              goto LABEL_80;
            }
            v91 = -1;
            do
              ++v91;
            while ( v81[v91] );
            v81 += v91 + 1;
            v92 = -1;
            do
              ++v92;
            while ( *(_WORD *)&v83[2 * v92] );
            v83 += 2 * v92 + 2;
            v93 = -1;
            do
              ++v93;
            while ( *(_WORD *)&v85[2 * v93] );
            v85 += 2 * v93 + 2;
            v79 = String1[0];
            v84 = (const unsigned __int8 *)*((_QWORD *)&v140 + 1);
            v82 = (const unsigned __int8 *)*((_QWORD *)&v145 + 1);
            v80 = String1[1];
          }
          v109 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            MultiSz::end(&v145, v134, v80, 0);
            MultiSz::end(&v140, v135, v110, v111);
            LOBYTE(v114) = v81 == *(const wchar_t **)MultiSz::end(String1, v136, v112, v113);
            WPP_SF_LLL(v109[2], v115, v116, v114, v117, v118);
          }
          v119 = std::wstring::wstring(v153);
          GetLinkageLists(
            v129,
            (_DWORD)v130,
            v124,
            v128,
            v119,
            (__int64)&v140,
            (__int64)&v145,
            (__int64)String1,
            (__int64)&v147);
        }
LABEL_80:
        v7 = 1;
        if ( v163 >= 8 )
          operator delete(v162[0]);
        v163 = 7;
        v162[2] = 0;
        LOWORD(v162[0]) = 0;
        if ( v166 >= 8 )
          operator delete(v164[0]);
        v166 = 7;
        v165 = 0;
        LOWORD(v164[0]) = 0;
        if ( v144 >= 8 )
          operator delete(String2[0]);
        std::vector<std::wstring>::_Tidy(&v160);
        v12 = (const unsigned __int8 *)v140;
        v17 = (const unsigned __int8 *)v145;
      }
      else
      {
        std::vector<std::wstring>::_Tidy(&v160);
      }
    }
    v25 = -1;
    v5 = v130;
  }
  else
  {
    v98 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v99 = MultiSz::count((MultiSz *)&v145);
      MultiSz::count((MultiSz *)&v140);
      v100 = MultiSz::count((MultiSz *)String1);
      WPP_SF_PPP(v98[2], v101, v102, v100, v103, v99);
    }
    v104 = std::wstring::wstring(v153);
    GetLinkageLists(
      v129,
      (_DWORD)v5,
      v124,
      v128,
      v104,
      (__int64)&v140,
      (__int64)&v145,
      (__int64)String1,
      (__int64)&v147);
    v7 = 1;
    v12 = (const unsigned __int8 *)v140;
  }
  if ( v12 == *((const unsigned __int8 **)&v140 + 1) || !*(_WORD *)v12 )
  {
    std::wstring::wstring(v153, L"\\Device\\");
    std::wstring::append(v153, v155, 0, -1);
    v120 = v153;
    if ( v154 >= 8 )
      v120 = (void **)v153[0];
    do
      ++v25;
    while ( *((_WORD *)v120 + v25) );
    Block = v120;
    v127 = (char *)v120 + 2 * v25;
    MultiSz::push_back(&v140, &Block);
    LOBYTE(v121) = 1;
    std::wstring::_Tidy(v153, v121, 0);
    goto LABEL_219;
  }
  if ( v7 )
  {
LABEL_219:
    RegistryKey::SetValue((RegistryKey *)&hKey, L"Export", (const struct MultiSz *)&v140);
    RegistryKey::SetValue((RegistryKey *)&hKey, L"Bind", (const struct MultiSz *)&v145);
    RegistryKey::SetValue((RegistryKey *)&hKey, L"Route", (const struct MultiSz *)String1);
  }
  v157 = *(GUID *)&NETSETUPPKEY_Driver_ResultingTdiBindings;
  v158 = 132;
  v159 = 0;
  v160 = 0;
  v161 = 0;
  NetSetup2::Aggregate::ResultingTdiBindings_Value::Serialize(&Block, &v147, &v150);
  NetSetup2::Property::SetRawData(&v157, 130, &Block);
  if ( Block )
    operator delete(Block);
  NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property>(v5, &v157);
  std::vector<_NETSETUPPROPKEY>::_Tidy(&v160);
  std::vector<NetSetupLoadedPlugin const *>::~vector<NetSetupLoadedPlugin const *>((__int64)&v150);
  std::vector<std::wstring>::_Tidy(&v147);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v156 >= 8 )
    operator delete(v155[0]);
  v156 = 7;
  v155[2] = 0;
  LOWORD(v155[0]) = 0;
LABEL_44:
  std::vector<_NETSETUPPROPKEY>::_Tidy(String1);
  std::vector<_NETSETUPPROPKEY>::_Tidy(&v145);
  return std::vector<_NETSETUPPROPKEY>::_Tidy(&v140);
}

```

## disassembly

```asm
0x180024b2c  push    rbp
0x180024b2e  push    rbx
0x180024b2f  push    rsi
0x180024b30  push    rdi
0x180024b31  push    r12
0x180024b33  push    r13
0x180024b35  push    r14
0x180024b37  push    r15
0x180024b39  lea     rbp, [rsp-388h]
0x180024b41  sub     rsp, 488h
0x180024b48  mov     [rbp+3C0h+var_3F0], 0FFFFFFFFFFFFFFFEh
0x180024b50  mov     rax, cs:__security_cookie
0x180024b57  xor     rax, rsp
0x180024b5a  mov     [rbp+3C0h+var_50], rax
0x180024b61  mov     [rsp+4C0h+var_464], r9d
0x180024b66  mov     r14, r8
0x180024b69  mov     [rbp+3C0h+var_420], r8
0x180024b6d  mov     [rbp+3C0h+var_428], rdx
0x180024b71  mov     r15, rcx
0x180024b74  mov     rax, [rbp+3C0h+arg_20]
0x180024b7b  mov     [rbp+3C0h+var_430], rax
0x180024b7f  xor     edi, edi
0x180024b81  xorps   xmm0, xmm0
0x180024b84  movdqu  [rbp+3C0h+var_398], xmm0
0x180024b89  mov     [rbp+3C0h+var_388], rdi
0x180024b8d  movdqu  [rbp+3C0h+var_360], xmm0
0x180024b92  mov     [rbp+3C0h+var_350], rdi
0x180024b96  movdqu  xmmword ptr [rbp+3C0h+String1], xmm0
0x180024b9b  mov     [rbp+3C0h+var_3A0], rdi
0x180024b9f  xor     r9d, r9d
0x180024ba2  lea     r8, NETSETUPPKEY_ProtocolDriver_SkipLinkageKeyGeneration; unsigned int
0x180024ba9  lea     rdx, [rbp+3C0h+var_2D8]; struct _NETSETUPPROPKEY *
0x180024bb0  mov     rcx, r14; this
0x180024bb3  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x180024bb8  nop
0x180024bb9  lea     rcx, [rbp+3C0h+var_2D8]; this
0x180024bc0  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x180024bc5  mov     bl, al
0x180024bc7  lea     rcx, [rbp+3C0h+var_2C0]
0x180024bce  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024bd3  test    bl, bl
0x180024bd5  jnz     loc_180024F18
0x180024bdb  xor     r9d, r9d
0x180024bde  lea     r8, NETSETUPPKEY_Driver_BindName; unsigned int
0x180024be5  lea     rdx, [rbp+3C0h+var_2D8]; struct _NETSETUPPROPKEY *
0x180024bec  mov     rcx, r14; this
0x180024bef  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x180024bf4  nop
0x180024bf5  lea     rdx, [rbp+3C0h+var_2F8]
0x180024bfc  lea     rcx, [rbp+3C0h+var_2D8]
0x180024c03  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x180024c08  nop
0x180024c09  lea     rcx, [rbp+3C0h+var_2C0]
0x180024c10  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024c15  lea     r8, [rbp+3C0h+var_2F8]
0x180024c1c  cmp     [rbp+3C0h+var_2E0], 8
0x180024c24  cmovnb  r8, [rbp+3C0h+var_2F8]
0x180024c2c  lea     rdx, aServicesSLinka; "Services\\%s\\Linkage"
0x180024c33  lea     rcx, [rbp+3C0h+var_260]
0x180024c3a  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@_WPEB_WZZ; swprintf_s<260>(wchar_t (&)[260],wchar_t const *,...)
0x180024c3f  lea     rcx, [r15+18h]
0x180024c43  mov     [rsp+4C0h+var_498], rdi
0x180024c48  mov     [rsp+4C0h+var_4A0], rdi
0x180024c4d  lea     r9d, [rdi+3]
0x180024c51  lea     r8, [rbp+3C0h+var_260]
0x180024c58  lea     rdx, [rsp+4C0h+hKey]
0x180024c5d  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180024c62  nop
0x180024c63  lea     rdx, aExport; "Export"
0x180024c6a  lea     rcx, [rsp+4C0h+hKey]; this
0x180024c6f  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180024c74  test    al, al
0x180024c76  jz      short loc_180024CAF
0x180024c78  lea     r8, aExport; "Export"
0x180024c7f  lea     rdx, [rsp+4C0h+Block]
0x180024c84  lea     rcx, [rsp+4C0h+hKey]
0x180024c89  call    ?GetValueMultiSz@RegistryKey@@QEBA?AVMultiSz@@PEB_W@Z; RegistryKey::GetValueMultiSz(wchar_t const *)
0x180024c8e  nop
0x180024c8f  mov     rdx, rax
0x180024c92  lea     rcx, [rbp+3C0h+var_398]
0x180024c96  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180024c9b  nop
0x180024c9c  lea     rcx, [rsp+4C0h+Block]
0x180024ca1  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024ca6  lea     rcx, [rbp+3C0h+var_398]; this
0x180024caa  call    ?fix_null_terminator@MultiSz@@QEAAXXZ; MultiSz::fix_null_terminator(void)
0x180024caf  lea     rdx, aBind; "Bind"
0x180024cb6  lea     rcx, [rsp+4C0h+hKey]; this
0x180024cbb  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180024cc0  test    al, al
0x180024cc2  jnz     loc_1800258CE
0x180024cc8  lea     rdx, aRoute; "Route"
0x180024ccf  lea     rcx, [rsp+4C0h+hKey]; this
0x180024cd4  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180024cd9  test    al, al
0x180024cdb  jnz     loc_18002590A
0x180024ce1  mov     [rbp+3C0h+var_348], rdi
0x180024ce5  mov     [rbp+3C0h+var_340], rdi
0x180024cec  mov     [rbp+3C0h+var_338], rdi
0x180024cf3  mov     [rbp+3C0h+var_330], rdi
0x180024cfa  mov     [rbp+3C0h+var_328], rdi
0x180024d01  mov     [rbp+3C0h+var_320], rdi
0x180024d08  mov     r12, qword ptr [rbp+3C0h+var_398]
0x180024d0c  mov     rbx, qword ptr [rbp+3C0h+var_398+8]
0x180024d10  cmp     r12, rbx
0x180024d13  jz      loc_180025946
0x180024d19  cmp     [r12], di
0x180024d1e  jz      loc_180025946
0x180024d24  mov     rcx, rbx
0x180024d27  sub     rcx, r12
0x180024d2a  shr     rcx, 1
0x180024d2d  mov     r8, rdi
0x180024d30  mov     rdx, rdi
0x180024d33  jz      short loc_180024D4B
0x180024d35  mov     rax, rdi
0x180024d38  cmp     [r12+rdx*2], di
0x180024d3d  setz    al
0x180024d40  add     r8, rax
0x180024d43  inc     rdx
0x180024d46  cmp     rdx, rcx
0x180024d49  jb      short loc_180024D35
0x180024d4b  lea     r9, [r8-1]
0x180024d4f  mov     r13, qword ptr [rbp+3C0h+var_360]
0x180024d53  mov     rsi, qword ptr [rbp+3C0h+var_360+8]
0x180024d57  cmp     r13, rsi
0x180024d5a  jz      loc_18002594E
0x180024d60  cmp     [r13+0], di
0x180024d65  jz      loc_18002594E
0x180024d6b  mov     rcx, rsi
0x180024d6e  sub     rcx, r13
0x180024d71  shr     rcx, 1
0x180024d74  mov     r8, rdi
0x180024d77  mov     rdx, rdi
0x180024d7a  jz      short loc_180024D93
0x180024d7c  mov     rax, rdi
0x180024d7f  cmp     [r13+rdx*2+0], di
0x180024d85  setz    al
0x180024d88  add     r8, rax
0x180024d8b  inc     rdx
0x180024d8e  cmp     rdx, rcx
0x180024d91  jb      short loc_180024D7C
0x180024d93  dec     r8
0x180024d96  cmp     r9, r8
0x180024d99  jz      loc_180025956
0x180024d9f  mov     r9b, dil
0x180024da2  cmp     r12, rbx
0x180024da5  jz      short loc_180024DDF
0x180024da7  cmp     [r12], di
0x180024dac  jz      short loc_180024DDF
0x180024dae  mov     rcx, rbx
0x180024db1  sub     rcx, r12
0x180024db4  shr     rcx, 1
0x180024db7  mov     r8, rdi
0x180024dba  mov     rdx, rdi
0x180024dbd  jz      short loc_180024DD5
0x180024dbf  mov     rax, rdi
0x180024dc2  cmp     [r12+rdx*2], di
0x180024dc7  setz    al
0x180024dca  add     r8, rax
0x180024dcd  inc     rdx
0x180024dd0  cmp     rdx, rcx
0x180024dd3  jb      short loc_180024DBF
0x180024dd5  cmp     r8, 2
0x180024dd9  jz      loc_1800258A4
0x180024ddf  mov     al, dil
0x180024de2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024de6  test    r9b, r9b
0x180024de9  jz      loc_18002597C
0x180024def  xor     esi, esi
0x180024df1  test    al, al
0x180024df3  cmovnz  rbx, r12
0x180024df7  mov     qword ptr [rbp+3C0h+var_398+8], rbx
0x180024dfb  mov     r15, [r15+298h]
0x180024e02  mov     [rbp+3C0h+var_418], r15
0x180024e06  mov     r14, [r15]
0x180024e09  mov     [rsp+4C0h+var_460], r14
0x180024e0e  cmp     r14, r15
0x180024e11  jnz     loc_180024F58
0x180024e17  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024e1b  mov     r14, [rbp+3C0h+var_420]
0x180024e1f  xor     ebx, ebx
0x180024e21  cmp     r12, qword ptr [rbp+3C0h+var_398+8]
0x180024e25  jz      loc_180025B4F
0x180024e2b  cmp     [r12], bx
0x180024e30  jz      loc_180025B4F
0x180024e36  test    dil, dil
0x180024e39  jnz     loc_180025BCA
0x180024e3f  movups  xmm0, cs:NETSETUPPKEY_Driver_ResultingTdiBindings
0x180024e46  movups  [rbp+3C0h+var_2D8], xmm0
0x180024e4d  mov     eax, cs:dword_18009A398
0x180024e53  mov     [rbp+3C0h+var_2C8], eax
0x180024e59  mov     [rbp+3C0h+var_2C4], ebx
0x180024e5f  xorps   xmm0, xmm0
0x180024e62  movdqu  [rbp+3C0h+var_2C0], xmm0
0x180024e6a  mov     [rbp+3C0h+var_2B0], rbx
0x180024e71  lea     r8, [rbp+3C0h+var_330]
0x180024e78  lea     rdx, [rbp+3C0h+var_348]
0x180024e7c  lea     rcx, [rsp+4C0h+Block]
0x180024e81  call    ?Serialize@ResultingTdiBindings_Value@Aggregate@NetSetup2@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEBV?$vector@KV?$allocator@K@std@@@5@@Z; NetSetup2::Aggregate::ResultingTdiBindings_Value::Serialize(std::vector<std::wstring> const &,std::vector<ulong> const &)
0x180024e86  nop
0x180024e87  lea     r8, [rsp+4C0h+Block]
0x180024e8c  mov     edx, 82h
0x180024e91  lea     rcx, [rbp+3C0h+var_2D8]
0x180024e98  call    ?SetRawData@Property@NetSetup2@@QEAAXK$$QEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NetSetup2::Property::SetRawData(ulong,std::vector<uchar> &&)
0x180024e9d  nop
0x180024e9e  mov     rcx, [rsp+4C0h+Block]; Block
0x180024ea3  test    rcx, rcx
0x180024ea6  jz      short loc_180024EAD
0x180024ea8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024ead  lea     rdx, [rbp+3C0h+var_2D8]
0x180024eb4  mov     rcx, r14
0x180024eb7  call    ??$SetPropertyUniversal@VProperty@NetSetup2@@@ActiveObject@NetSetup2@@AEAAX$$QEAVProperty@1@@Z; NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property>(NetSetup2::Property &&)
0x180024ebc  nop
0x180024ebd  lea     rcx, [rbp+3C0h+var_2C0]
0x180024ec4  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024ec9  nop
0x180024eca  lea     rcx, [rbp+3C0h+var_330]
0x180024ed1  call    ??1?$vector@PEBVNetSetupLoadedPlugin@@V?$allocator@PEBVNetSetupLoadedPlugin@@@std@@@std@@QEAA@XZ; std::vector<NetSetupLoadedPlugin const *>::~vector<NetSetupLoadedPlugin const *>(void)
0x180024ed6  lea     rcx, [rbp+3C0h+var_348]
0x180024eda  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180024edf  nop
0x180024ee0  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180024ee5  test    rcx, rcx
0x180024ee8  jz      short loc_180024EF1
0x180024eea  call    cs:__imp_RegCloseKey
0x180024ef0  nop
0x180024ef1  cmp     [rbp+3C0h+var_2E0], 8
0x180024ef9  jnb     loc_1800255D1
0x180024eff  mov     [rbp+3C0h+var_2E0], 7
0x180024f0a  mov     [rbp+3C0h+var_2E8], rbx
0x180024f11  mov     word ptr [rbp+3C0h+var_2F8], bx
0x180024f18  lea     rcx, [rbp+3C0h+String1]
0x180024f1c  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024f21  nop
0x180024f22  lea     rcx, [rbp+3C0h+var_360]
0x180024f26  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024f2b  nop
0x180024f2c  lea     rcx, [rbp+3C0h+var_398]
0x180024f30  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180024f35  mov     rcx, [rbp+3C0h+var_50]
0x180024f3c  xor     rcx, rsp; StackCookie
0x180024f3f  call    __security_check_cookie
0x180024f44  add     rsp, 488h
0x180024f4b  pop     r15
0x180024f4d  pop     r14
0x180024f4f  pop     r13
0x180024f51  pop     r12
0x180024f53  pop     rdi
0x180024f54  pop     rsi
0x180024f55  pop     rbx
0x180024f56  pop     rbp
0x180024f57  retn
0x180024f58  movups  xmm0, xmmword ptr [r14+10h]
0x180024f5d  movdqu  [rbp+3C0h+var_2D8], xmm0
0x180024f65  mov     al, [r14+20h]
0x180024f69  mov     byte ptr [rbp+3C0h+var_2C8], al
0x180024f6f  lea     rdx, [r14+28h]
0x180024f73  lea     rcx, [rbp+3C0h+var_2C0]
0x180024f7a  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180024f7f  nop
0x180024f80  mov     rbx, qword ptr [rbp+3C0h+var_2C0+8]
0x180024f87  lea     rcx, [rbx-20h]
0x180024f8b  lea     rdx, [rbp+3C0h+var_2F8]
0x180024f92  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x180024f97  test    al, al
0x180024f99  jnz     short loc_180024FAF
0x180024f9b  lea     rcx, [rbp+3C0h+var_2C0]
0x180024fa2  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180024fa7  mov     r14, [r14]
0x180024faa  jmp     loc_180024E09
0x180024faf  mov     edx, 7
0x180024fb4  mov     r8d, edx
0x180024fb7  mov     [rbp+3C0h+var_368], rdx
0x180024fbb  mov     rcx, rsi
0x180024fbe  mov     [rbp+3C0h+var_370], rcx
0x180024fc2  mov     word ptr [rbp+3C0h+String2], si
0x180024fc6  mov     [rbp+3C0h+var_270], rdx
0x180024fcd  mov     [rbp+3C0h+var_278], rsi
0x180024fd4  mov     word ptr [rbp+3C0h+var_288], si
0x180024fdb  mov     rsi, qword ptr [rbp+3C0h+var_2C0]
0x180024fe2  sub     rbx, rsi
0x180024fe5  sar     rbx, 5
0x180024fe9  sub     rbx, 1
0x180024fed  jnz     loc_18002562A
0x180024ff3  lea     rdx, aDevice_1; "\\Device\\"
0x180024ffa  lea     rcx, [rbp+3C0h+var_2A8]
0x180025001  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180025006  nop
0x180025007  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002500b  mov     r9, rsi
0x18002500e  xor     r8d, r8d
0x180025011  lea     rdx, [rbp+3C0h+var_288]
0x180025018  lea     rcx, [rbp+3C0h+var_2A8]
0x18002501f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180025024  lea     rax, [rbp+3C0h+var_2A8]
0x18002502b  mov     rdi, [rbp+3C0h+var_340]
0x180025032  cmp     rax, rdi
0x180025035  jb      loc_180025584
0x18002503b  cmp     rdi, [rbp+3C0h+var_338]
0x180025042  jz      loc_180025A3E
  ... truncated ...
```
