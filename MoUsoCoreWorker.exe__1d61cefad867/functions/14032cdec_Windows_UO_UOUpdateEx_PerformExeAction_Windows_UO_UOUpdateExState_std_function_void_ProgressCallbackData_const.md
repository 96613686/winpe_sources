# Windows::UO::UOUpdateEx::PerformExeAction(Windows::UO::UOUpdateExState,std::function<void (ProgressCallbackData)> const &)

- ea: `0x14032cdec`
- end: `0x14032e484`
- name: `?PerformExeAction@UOUpdateEx@UO@Windows@@AEAA?AU?$pair@JV?$optional@W4UOUpdateExState@UO@Windows@@@std@@@std@@W4UOUpdateExState@23@AEBV?$function@$$A6AXUProgressCallbackData@@@Z@5@@Z`
- size: `5784`
- prototype: `__int64 __fastcall(struct Update *, __int64, int, __int64)`
- caller_count: `3`
- callee_count: `46`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14032e930`
- `0x14032ea30`
- `0x14032eeb0`

## callees

- `0x140040964`
- `0x140041b3c`
- `0x14004296c`
- `0x140042d04`
- `0x1400430dc`
- `0x140043284`
- `0x140043354`
- `0x140043814`
- `0x1400447ac`
- `0x140045404`
- `0x140053618`
- `0x140059454`
- `0x140073568`
- `0x1400a3d80`
- `0x1400a52e4`
- `0x1400a6f74`
- `0x1400c679c`
- `0x1400c6ef0`
- `0x1400ced3c`
- `0x140150f10`
- `0x140160f98`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x1401a2fa8`
- `0x1401a7c40`
- `0x1403134ac`
- `0x1403277d4`
- `0x14032c6a4`
- `0x14032cdec`
- `0x14032e7f0`
- `0x14032f33c`
- `0x140330d3c`
- `0x140330e7c`
- `0x140331040`
- `0x14033124c`
- `0x140331870`
- `0x1403318f0`
- `0x140331974`
- `0x140331a50`
- `0x140331ba8`
- `0x1403321bc`
- `0x140378b3e`
- `0x140378fd8`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14032dbaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14032dbaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14032dc9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14032dc9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14032dc51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14032dc51`

## string_xrefs

- `0x14032e45c`: `create_directory`
- `0x14032d86e`: `%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe`
- `0x14032ce79`: `External Update {}:{} - ExecutionInfo is not populated`
- `0x14032d6b3`: `External Update {}:{} - Download executable is not populated`
- `0x14032d271`: `install`
- `0x14032de2b`: `External Update {}:{} - {} action failed with HRESULT: {}`
- `0x14032df7b`: `External Update {}:{} - {} action was canceled`
- `0x14032e02a`: `External Update {}:{} - {} action was removed`
- `0x14032e0fc`: `External Update {}:{} - {} action returned an unsupported restart reason: {}`
- `0x14032e28f`: `External Update {}:{} - {} action results missing for update`
- `0x14032e31d`: `External Update {}:{} - {} action executable failed without returning a result`
- `0x14032e3a7`: `Provider {} - Failed trust chain validation during Action {} attempt: {}`
- `0x14032d62b`: `External Update {}:{} - Executable path is not populated`
- `0x14032d7ef`: `External Update {}:{} - Executable path is not populated`
- `0x14032d48c`: `close-and-install`
- `0x14032d525`: `External Update {}:{} - AppClose has been approved for install`
- `0x14032d094`: `External Update {}:{} - app closure has not been approved`
- `0x14032d9cb`: `External Update {}:{} - Executable path does not exist: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::UO::UOUpdateEx::PerformExeAction(struct Update *a1, __int64 a2, int a3, __int64 a4)
{
  int v8; // edi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  bool v13; // zf
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  _QWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  _QWORD *v27; // rax
  char *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  wchar_t *v34; // r15
  _QWORD *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  _QWORD *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  wchar_t *v46; // rdx
  __int64 v47; // r8
  _QWORD *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rdx
  _QWORD *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // rbx
  __int128 *v79; // rax
  struct std::error_code *v80; // r8
  __int64 v81; // rdx
  bool v82; // bl
  const struct std::filesystem::path *v83; // r9
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  struct std::error_code *v90; // r8
  bool v91; // al
  const struct std::filesystem::path *v92; // r9
  const WCHAR *v93; // rcx
  unsigned __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rdx
  struct _Mtx_internal_imp_t *v97; // rax
  int v98; // r15d
  unsigned __int8 v99; // di
  _QWORD *v100; // r15
  __int128 *v101; // rcx
  __int128 *v102; // rcx
  struct _Mtx_internal_imp_t *v103; // rax
  _QWORD *v104; // rax
  __int64 v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // r8
  int v108; // edx
  int v109; // ebx
  int v110; // eax
  __int64 v111; // rdx
  __int64 v112; // rdx
  int v113; // eax
  int v114; // eax
  __int64 v115; // rdx
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rdx
  __int64 v119; // rdx
  __int64 v121; // rbx
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rdx
  __int64 v125; // rbx
  __int64 v126; // rax
  __int64 v127; // rdx
  __int64 v128; // rdx
  int v129; // ebx
  int v130; // eax
  __int64 v131; // rdx
  __int64 v132; // rdx
  __int64 v133; // rbx
  __int64 v134; // rax
  __int64 v135; // rdx
  __int64 v136; // rdx
  __int64 v137; // rax
  __int64 v138; // rdx
  __int64 v139; // rdx
  __int64 v140; // rax
  __int64 v141; // rdx
  __int128 v142; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v143; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v144; // [rsp+60h] [rbp-A0h]
  char Src[16]; // [rsp+70h] [rbp-90h] BYREF
  _Mtx_t v146[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v147[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v148; // [rsp+B0h] [rbp-50h]
  _QWORD v149[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v150; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v151; // [rsp+D8h] [rbp-28h] BYREF
  int v152; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v153; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v154; // [rsp+F8h] [rbp-8h]
  __int64 v155[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v156; // [rsp+118h] [rbp+18h]
  __int64 v157; // [rsp+120h] [rbp+20h]
  __int128 v158; // [rsp+128h] [rbp+28h] BYREF
  __int128 v159; // [rsp+138h] [rbp+38h]
  __int128 v160; // [rsp+148h] [rbp+48h] BYREF
  __int64 v161; // [rsp+158h] [rbp+58h]
  __int64 v162; // [rsp+160h] [rbp+60h]
  char v163; // [rsp+168h] [rbp+68h]
  __int128 v164; // [rsp+170h] [rbp+70h] BYREF
  __int64 v165; // [rsp+180h] [rbp+80h]
  unsigned __int64 v166; // [rsp+188h] [rbp+88h]
  __int128 v167; // [rsp+190h] [rbp+90h] BYREF
  __int128 v168; // [rsp+1A0h] [rbp+A0h]
  char v169; // [rsp+1B0h] [rbp+B0h]
  LPCWSTR lpFileName[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v171[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v172; // [rsp+200h] [rbp+100h]
  _QWORD v173[4]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD *v174; // [rsp+258h] [rbp+158h] BYREF
  __int64 v175; // [rsp+268h] [rbp+168h]
  unsigned __int64 v176; // [rsp+270h] [rbp+170h]
  _QWORD *v177; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v178; // [rsp+2B0h] [rbp+1B0h]
  unsigned __int64 v179; // [rsp+2B8h] [rbp+1B8h]
  _QWORD *v180; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v181; // [rsp+2F8h] [rbp+1F8h]
  unsigned __int64 v182; // [rsp+300h] [rbp+200h]
  char v183[40]; // [rsp+308h] [rbp+208h] BYREF
  _QWORD *v184; // [rsp+330h] [rbp+230h] BYREF
  __int64 v185; // [rsp+340h] [rbp+240h]
  unsigned __int64 v186; // [rsp+348h] [rbp+248h]
  char v187[40]; // [rsp+350h] [rbp+250h] BYREF
  _QWORD *v188; // [rsp+378h] [rbp+278h] BYREF
  __int64 v189; // [rsp+388h] [rbp+288h]
  unsigned __int64 v190; // [rsp+390h] [rbp+290h]
  _BYTE v191[432]; // [rsp+3C0h] [rbp+2C0h] BYREF
  char v192; // [rsp+570h] [rbp+470h]

  v8 = 0;
  (*(void (__fastcall **)(struct Update *, _BYTE *))(*(_QWORD *)a1 + 464LL))(a1, v191);
  if ( !v192 )
  {
    v9 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v147);
    v10 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
    *(_QWORD *)Src = L"External Update {}:{} - ExecutionInfo is not populated";
    *(_QWORD *)&Src[8] = 54;
    v142 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v142, v10, v9);
    std::wstring::~wstring(&v143, v11);
    std::wstring::~wstring(v147, v12);
    *(_DWORD *)a2 = -2145082593;
    *(_BYTE *)(a2 + 8) = 0;
LABEL_3:
    v13 = v192 == 0;
    goto LABEL_111;
  }
  UpdateExecutionInfo::UpdateExecutionInfo((UpdateExecutionInfo *)v173, (const struct UpdateExecutionInfo *)v191);
  v153 = 0;
  *(_QWORD *)&v154 = 0;
  *((_QWORD *)&v154 + 1) = 7;
  LOWORD(v153) = 0;
  v158 = 0;
  *(_QWORD *)&v159 = 0;
  *((_QWORD *)&v159 + 1) = 7;
  LOWORD(v158) = 0;
  *(_OWORD *)v155 = 0;
  v156 = 0;
  v157 = 7;
  LOWORD(v155[0]) = 0;
  if ( !a3 )
  {
    if ( v175 )
    {
      v65 = &v174;
      if ( v176 > 7 )
        v65 = v174;
      *(_QWORD *)Src = v65;
      *(_QWORD *)&Src[8] = v175;
      v142 = *(_OWORD *)Src;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v147, &v142);
      v66 = std::filesystem::operator/(&v167, (char *)a1 + 328, v147);
      std::wstring::wstring(&v143, v66);
      std::wstring::~wstring(&v153, v67);
      v153 = v143;
      v154 = v144;
      *(_QWORD *)&v144 = 0;
      *((_QWORD *)&v144 + 1) = 7;
      LOWORD(v143) = 0;
      std::wstring::~wstring(&v143, v68);
      std::wstring::~wstring(&v167, v69);
      std::wstring::~wstring(v147, v70);
      std::wstring::operator=(&v158);
      std::wstring::operator=(v155, L"download");
      goto LABEL_68;
    }
    v62 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v147);
    v63 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
    *(_QWORD *)Src = L"External Update {}:{} - Download executable is not populated";
    *(_QWORD *)&Src[8] = 60;
    v142 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v142, v63, v62);
    std::wstring::~wstring(&v143, v64);
    goto LABEL_62;
  }
  if ( a3 == 1 || a3 == 2 )
  {
    if ( Windows::UO::UOUpdateEx::HasDeployInfo(a1) )
    {
      v27 = v173;
      if ( v173[3] > 7u )
        v27 = (_QWORD *)v173[0];
      *(_QWORD *)Src = v27;
      *(_QWORD *)&Src[8] = v173[2];
      v142 = *(_OWORD *)Src;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v147, &v142);
      v28 = (char *)a1 + 328;
      v29 = std::filesystem::operator/(Src, (char *)a1 + 328, v147);
      std::wstring::wstring(&v143, v29);
      std::wstring::~wstring(&v153, v30);
      v153 = v143;
      v154 = v144;
      *(_QWORD *)&v144 = 0;
      *((_QWORD *)&v144 + 1) = 7;
      LOWORD(v143) = 0;
      std::wstring::~wstring(&v143, v31);
      std::wstring::~wstring(Src, v32);
      std::wstring::~wstring(v147, v33);
      v34 = L"deploy";
      goto LABEL_25;
    }
    if ( v178 )
    {
      v35 = &v177;
      if ( v179 > 7 )
        v35 = v177;
      *(_QWORD *)Src = v35;
      *(_QWORD *)&Src[8] = v178;
      v142 = *(_OWORD *)Src;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v147, &v142);
      v28 = (char *)a1 + 328;
      v36 = std::filesystem::operator/(Src, (char *)a1 + 328, v147);
      std::wstring::wstring(&v143, v36);
      std::wstring::~wstring(&v153, v37);
      v153 = v143;
      v154 = v144;
      *(_QWORD *)&v144 = 0;
      *((_QWORD *)&v144 + 1) = 7;
      LOWORD(v143) = 0;
      std::wstring::~wstring(&v143, v38);
      std::wstring::~wstring(Src, v39);
      std::wstring::~wstring(v147, v40);
      v34 = L"install";
LABEL_25:
      std::wstring::operator=(&v158);
      std::wstring::operator=(v155, v34);
      v8 = 0;
      v169 = 0;
      v172 = 0;
      v163 = 0;
      if ( Windows::UO::UOUpdateEx::HasDeployInfo(a1) )
      {
        if ( !v181 )
          goto LABEL_47;
        v42 = &v180;
        if ( v182 > 7 )
          v42 = v180;
        *(_QWORD *)Src = v42;
        *(_QWORD *)&Src[8] = v181;
        v142 = *(_OWORD *)Src;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v143, &v142);
        v43 = std::filesystem::operator/(v147, v28, &v143);
        std::optional<std::wstring>::operator=<std::filesystem::path,0>(&v167, v43);
        std::wstring::~wstring(v147, v44);
        std::wstring::~wstring(&v143, v45);
        if ( v172 )
        {
          std::wstring::operator=(v171);
        }
        else
        {
          std::wstring::wstring(v171, v183);
          v172 = 1;
        }
        v46 = L"close-and-deploy";
        if ( !v163 )
        {
          v47 = 16;
LABEL_46:
          v160 = 0;
          v161 = 0;
          v162 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v160, v46, v47);
          v163 = 1;
LABEL_47:
          if ( v169 && (_QWORD)v168 && v163 && UpdateDatabase::IsAppClosureApproved(*((UpdateDatabase **)a1 + 15), a1) )
          {
            v54 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v147);
            v55 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
            *(_QWORD *)Src = L"External Update {}:{} - AppClose has been approved for install";
            *(_QWORD *)&Src[8] = 62;
            v142 = *(_OWORD *)Src;
            SystemInterface::Log<std::wstring,std::wstring>(&v142, v55, v54);
            std::wstring::~wstring(&v143, v56);
            std::wstring::~wstring(v147, v57);
            if ( !v169 || (std::wstring::operator=(&v153), !v172) || (std::wstring::operator=(&v158), !v163) )
              std::_Throw_bad_optional_access();
            std::wstring::operator=(v155);
          }
          if ( v163 )
            std::wstring::~wstring(&v160, v41);
          if ( v172 )
            std::wstring::~wstring(v171, v41);
          if ( v169 )
            std::wstring::~wstring(&v167, v41);
          goto LABEL_68;
        }
      }
      else
      {
        if ( !v185 )
          goto LABEL_47;
        v48 = &v184;
        if ( v186 > 7 )
          v48 = v184;
        *(_QWORD *)Src = v48;
        *(_QWORD *)&Src[8] = v185;
        v142 = *(_OWORD *)Src;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v147, &v142);
        v49 = std::filesystem::operator/(Src, v28, v147);
        if ( v169 )
        {
          std::wstring::wstring(&v143, v49);
          std::wstring::~wstring(&v167, v50);
          v167 = v143;
          v168 = v144;
          *(_QWORD *)&v144 = 0;
          *((_QWORD *)&v144 + 1) = 7;
          LOWORD(v143) = 0;
          std::wstring::~wstring(&v143, v51);
        }
        else
        {
          std::wstring::wstring(&v167, v49);
          v169 = 1;
        }
        std::wstring::~wstring(Src, v52);
        std::wstring::~wstring(v147, v53);
        if ( v172 )
        {
          std::wstring::operator=(v171);
        }
        else
        {
          std::wstring::wstring(v171, v187);
          v172 = 1;
        }
        v46 = L"close-and-install";
        if ( !v163 )
        {
          v47 = 17;
          goto LABEL_46;
        }
      }
      std::wstring::operator=(&v160, v46);
      goto LABEL_47;
    }
    v58 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v147);
    v59 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
    *(_QWORD *)Src = L"External Update {}:{} - Executable path is not populated";
    *(_QWORD *)&Src[8] = 56;
    v142 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v142, v59, v58);
    std::wstring::~wstring(&v143, v60);
LABEL_62:
    std::wstring::~wstring(v147, v61);
    *(_DWORD *)a2 = -2145082593;
    goto LABEL_9;
  }
  if ( a3 != 3 )
  {
    *(_DWORD *)a2 = -2147418113;
LABEL_9:
    *(_BYTE *)(a2 + 8) = 0;
LABEL_10:
    std::wstring::~wstring(v155, v14);
    std::wstring::~wstring(&v158, v15);
    std::wstring::~wstring(&v153, v16);
    UpdateExecutionInfo::~UpdateExecutionInfo((UpdateExecutionInfo *)v173);
    goto LABEL_3;
  }
  if ( v189 )
  {
    v17 = &v188;
    if ( v190 > 7 )
      v17 = v188;
    *(_QWORD *)Src = v17;
    *(_QWORD *)&Src[8] = v189;
    v142 = *(_OWORD *)Src;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v147, &v142);
    v18 = std::filesystem::operator/(Src, (char *)a1 + 328, v147);
    std::wstring::wstring(&v143, v18);
    std::wstring::~wstring(&v153, v19);
    v153 = v143;
    v154 = v144;
    *(_QWORD *)&v144 = 0;
    *((_QWORD *)&v144 + 1) = 7;
    LOWORD(v143) = 0;
    std::wstring::~wstring(&v143, v20);
    std::wstring::~wstring(Src, v21);
    std::wstring::~wstring(v147, v22);
    std::wstring::operator=(&v158);
  }
  std::wstring::operator=(v155, L"close-and-restart");
  if ( !UpdateDatabase::IsAppClosureApproved(*((UpdateDatabase **)a1 + 15), a1) )
  {
    v23 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v147);
    v24 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
    *(_QWORD *)Src = L"External Update {}:{} - app closure has not been approved";
    *(_QWORD *)&Src[8] = 57;
    v142 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v142, v24, v23);
    std::wstring::~wstring(&v143, v25);
    std::wstring::~wstring(v147, v26);
    *(_DWORD *)a2 = -2145082827;
    goto LABEL_9;
  }
LABEL_68:
  v71 = *(_QWORD *)a1;
  if ( !(_QWORD)v154 )
  {
    v72 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(v71 + 24))(a1, v147);
    v73 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
    *(_QWORD *)Src = L"External Update {}:{} - Executable path is not populated";
    *(_QWORD *)&Src[8] = 56;
    v142 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v142, v73, v72);
    std::wstring::~wstring(&v143, v74);
    goto LABEL_62;
  }
  v164 = 0;
  v165 = 0;
  v166 = 7;
  LOWORD(v164) = 0;
  if ( (*(unsigned int (__fastcall **)(struct Update *))(v71 + 416))(a1) == 3 )
  {
    std::wstring::operator=(&v164);
    v76 = wil::ExpandEnvironmentStringsW<std::wstring,256>(
            &v143,
            L"%SystemRoot%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe");
    if ( &v153 != (__int128 *)v76 )
    {
      std::wstring::~wstring(&v153, v75);
      v153 = *(_OWORD *)v76;
      v154 = *(_OWORD *)(v76 + 16);
      *(_QWORD *)(v76 + 16) = 0;
      *(_QWORD *)(v76 + 24) = 7;
      *(_WORD *)v76 = 0;
    }
    std::wstring::~wstring(&v143, v75);
    *(_QWORD *)Src = L"-NoLogo -NoProfile -NonInteractive -ExecutionPolicy Bypass -File \"{}\" {}";
    *(_QWORD *)&Src[8] = 72;
    v142 = *(_OWORD *)Src;
    v78 = std::format<std::wstring const &,std::wstring const &>(&v143);
    if ( &v158 != (__int128 *)v78 )
    {
      std::wstring::~wstring(&v158, v77);
      v158 = *(_OWORD *)v78;
      v159 = *(_OWORD *)(v78 + 16);
      *(_QWORD *)(v78 + 16) = 0;
      *(_QWORD *)(v78 + 24) = 7;
      *(_WORD *)v78 = 0;
    }
    std::wstring::~wstring(&v143, v77);
  }
  v79 = &v153;
  if ( *((_QWORD *)&v154 + 1) > 7u )
    v79 = (__int128 *)v153;
  *(_QWORD *)Src = v79;
  *(_QWORD *)&Src[8] = v154;
  v142 = *(_OWORD *)Src;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v143, &v142);
  *(_QWORD *)Src = 0;
  *(_QWORD *)&Src[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v82 = std::filesystem::exists((std::filesystem *)&v143, (const struct std::filesystem::path *)Src, v80);
  if ( *(_DWORD *)Src )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", Src, (const struct std::error_code *)&v143, v83);
  std::wstring::~wstring(&v143, v81);
  if ( !v82 )
  {
    v84 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v147);
    v85 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v143);
    *(_QWORD *)Src = L"External Update {}:{} - Executable path does not exist: {}";
    *(_QWORD *)&Src[8] = 58;
    v142 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v142, v85, v84, &v153);
    std::wstring::~wstring(&v143, v86);
    std::wstring::~wstring(v147, v87);
    *(_DWORD *)a2 = -2145082592;
    *(_BYTE *)(a2 + 8) = 0;
    std::wstring::~wstring(&v164, v88);
    goto LABEL_10;
  }
  *(_QWORD *)Src = L"State";
  *(_QWORD *)&Src[8] = 5;
  v142 = *(_OWORD *)Src;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v143, &v142);
  std::filesystem::operator/(lpFileName, (char *)a1 + 328, &v143);
  std::wstring::~wstring(&v143, v89);
  *(_QWORD *)Src = 0;
  *(_QWORD *)&Src[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v91 = std::filesystem::exists((std::filesystem *)lpFileName, (const struct std::filesystem::path *)Src, v90);
  if ( *(_DWORD *)Src )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", Src, (const struct std::error_code *)lpFileName, v92);
  if ( !v91 )
  {
    v93 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v93 = lpFileName[0];
    v94 = (unsigned __int64)_std_fs_create_directory(v93) >> 32;
    if ( (_DWORD)v94 )
      std::filesystem::_Throw_fs_error("create_directory", (unsigned int)v94, lpFileName);
  }
  *(_QWORD *)&Src[8] = 1;
  *(_QWORD *)Src = a1;
  v149[0] = (char *)a1 + 128;
  if ( (unsigned int)mtx_do_lock((char *)a1 + 128, 0) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)a1 + 51) == 0x7FFFFFFF )
  {
    *((_DWORD *)a1 + 51) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v146[0] = (_Mtx_t)(*(_QWORD *)std::chrono::steady_clock::now(v146) / 1000LL);
  *(_QWORD *)&v167 = L"{:016X}:Action:{}";
  *((_QWORD *)&v167 + 1) = 17;
  v142 = v167;
  v95 = std::format<__int64 &,std::wstring &>(&v143);
  std::optional<std::wstring>::operator=<std::wstring,0>((char *)a1 + 208, v95);
  std::wstring::~wstring(&v143, v96);
  v13 = (*((_DWORD *)a1 + 51))-- == 1;
  if ( v13 )
  {
    *((_DWORD *)a1 + 50) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 18);
  }
  v150 = 0;
  *(_QWORD *)&v143 = a1;
  *((_QWORD *)&v143 + 1) = &v150;
  *(_QWORD *)&v144 = a4;
  *((_QWORD *)&v144 + 1) = v155;
  v97 = (struct _Mtx_internal_imp_t *)operator new(0x20u);
  *(_OWORD *)v97 = v143;
  *((_OWORD *)v97 + 1) = v144;
  v146[0] = v97;
  v151 = o__beginthreadex_0(
           0,
           0,
           std::thread::_Invoke_std::tuple__Windows::UO::UOUpdateEx::PerformExeAction_::_2_::_lambda_2____0_,
           v97,
           0);
  if ( !v151 )
  {
LABEL_152:
    v152 = v8;
    std::_Throw_Cpp_error(6);
  }
  v147[0] = &v150;
  v147[1] = &v151;
  v148 = 1;
  *((_QWORD *)&v142 + 1) = 1;
  v8 = (_DWORD)a1 + 320;
  *(_QWORD *)&v142 = (char *)a1 + 320;
  AcquireSRWLockShared((PSRWLOCK)a1 + 40);
  v149[0] = &v143;
  std::wstring::wstring(&v143, (char *)a1 + 328);
  (***((void (__fastcall ****)(_QWORD, _Mtx_t *))a1 + 39))(*((_QWORD *)a1 + 39), v146);
  v98 = Windows::UO::VerifyProviderTrust(v146, &v143);
  LODWORD(v149[0]) = v98;
  ReleaseSRWLockShared((PSRWLOCK)a1 + 40);
  if ( v98 < 0 )
  {
    v140 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
    *(_QWORD *)&v142 = L"Provider {} - Failed trust chain validation during Action {} attempt: {}";
    *((_QWORD *)&v142 + 1) = 72;
    SystemInterface::Log<std::wstring,std::wstring &,long &>(&v142, v140, v155, v149);
    std::wstring::~wstring(&v160, v141);
    *(_DWORD *)a2 = v98;
    *(_BYTE *)(a2 + 8) = 0;
    v150 = 1;
    v114 = v152;
    if ( v152 )
    {
      std::thread::join((std::thread *)&v151);
      v114 = v152;
    }
  }
  else
  {
    if ( !*((_BYTE *)a1 + 308) || (v99 = 1, *((_DWORD *)a1 + 76) != 1) )
      v99 = 0;
    v100 = (_QWORD *)Windows::UO::UOUpdateEx::CreateActionEnvironmentBlock(a1, &v143);
    v101 = &v164;
    if ( v166 > 7 )
      v101 = (__int128 *)v164;
    *(_QWORD *)&v142 = v101;
    *((_QWORD *)&v142 + 1) = v165;
    v102 = &v158;
    if ( *((_QWORD *)&v159 + 1) > 7u )
      v102 = (__int128 *)v158;
    *(_QWORD *)&v167 = v102;
    *((_QWORD *)&v167 + 1) = v159;
    v103 = (struct _Mtx_internal_imp_t *)&v153;
    if ( *((_QWORD *)&v154 + 1) > 7u )
      v103 = (struct _Mtx_internal_imp_t *)v153;
    v146[0] = v103;
    v146[1] = (_Mtx_t)v154;
    v104 = (_QWORD *)(*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
    v105 = v104[2];
    if ( v104[3] > 7u )
      v104 = (_QWORD *)*v104;
    v149[0] = v104;
    v149[1] = v105;
    v8 = Windows::UO::ExecuteBinary_0(v149, v146, &v167, (__int64)&v142, v100, (int)&v152, v99);
    std::wstring::~wstring(&v160, v106);
    std::vector<wchar_t>::_Tidy(&v143);
    v150 = 1;
    std::lock_guard<std::mutex>::lock_guard<std::mutex>(v146, (char *)a1 + 128);
    if ( *((_BYTE *)a1 + 296) )
    {
      v107 = *((unsigned int *)a1 + 68);
      v108 = *((_DWORD *)a1 + 69);
      v8 = *((_DWORD *)a1 + 70);
      LODWORD(v149[0]) = v8;
      switch ( (_DWORD)v107 )
      {
        case 2:
          v109 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v143);
          v110 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
          *(_QWORD *)&v142 = L"External Update {}:{} - {} action failed with HRESULT: {}";
          *((_QWORD *)&v142 + 1) = 57;
          SystemInterface::Log<std::wstring,std::wstring,std::wstring const &,int>(
            (unsigned int)&v142,
            v110,
            v109,
            (unsigned int)v155,
            (__int64)v149);
          std::wstring::~wstring(&v160, v111);
          std::wstring::~wstring(&v143, v112);
          v113 = -2147467259;
          if ( v8 < 0 )
            v113 = v8;
          *(_DWORD *)a2 = v113;
          *(_BYTE *)(a2 + 8) = 0;
          Mtx_unlock(v146[0]);
          v150 = 1;
          v114 = v152;
          if ( v152 )
          {
            std::thread::join((std::thread *)&v151);
            v114 = v152;
          }
          break;
        case 3:
          v121 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v143);
          v122 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
          *(_QWORD *)&v142 = L"External Update {}:{} - {} action was canceled";
          *((_QWORD *)&v142 + 1) = 46;
          SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v142, v122, v121, v155);
          std::wstring::~wstring(&v160, v123);
          std::wstring::~wstring(&v143, v124);
          *(_DWORD *)a2 = -2147467260;
          *(_BYTE *)(a2 + 8) = 0;
          Mtx_unlock(v146[0]);
          v150 = 1;
          v114 = v152;
          if ( v152 )
          {
            std::thread::join((std::thread *)&v151);
            v114 = v152;
          }
          break;
        case 4:
          v125 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v143);
          v126 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
          *(_QWORD *)&v142 = L"External Update {}:{} - {} action was removed";
          *((_QWORD *)&v142 + 1) = 45;
          SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v142, v126, v125, v155);
          std::wstring::~wstring(&v160, v127);
          std::wstring::~wstring(&v143, v128);
          *(_DWORD *)a2 = 0;
          *(_DWORD *)(a2 + 4) = 5;
          *(_BYTE *)(a2 + 8) = 1;
          Mtx_unlock(v146[0]);
          v150 = 1;
          v114 = v152;
          if ( v152 )
          {
            std::thread::join((std::thread *)&v151);
            v114 = v152;
          }
          break;
        default:
          if ( v108 )
          {
            switch ( v108 )
            {
              case 1:
                Windows::UO::UOUpdateEx::HandleRestartReasonSystem(a1, (__int64)v155);
                Mtx_unlock(v146[0]);
                v150 = 1;
                v114 = v152;
                if ( v152 )
                {
                  std::thread::join((std::thread *)&v151);
                  v114 = v152;
                }
                break;
              case 2:
                Windows::UO::UOUpdateEx::HandleRestartReasonAppClose(a1);
                Mtx_unlock(v146[0]);
                v150 = 1;
                v114 = v152;
                if ( v152 )
                {
                  std::thread::join((std::thread *)&v151);
                  v114 = v152;
                }
                break;
              case 3:
                Windows::UO::UOUpdateEx::HandleRestartReasonAppRestart(a1, a2, v107, v155);
                Mtx_unlock(v146[0]);
                v150 = 1;
                v114 = v152;
                if ( v152 )
                {
                  std::thread::join((std::thread *)&v151);
                  v114 = v152;
                }
                break;
              default:
                LODWORD(v149[0]) = v108;
                v129 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v143);
                v130 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
                *(_QWORD *)&v142 = L"External Update {}:{} - {} action returned an unsupported restart reason: {}";
                *((_QWORD *)&v142 + 1) = 76;
                SystemInterface::Log<std::wstring,std::wstring,std::wstring const &,int>(
                  (unsigned int)&v142,
                  v130,
                  v129,
                  (unsigned int)v155,
                  (__int64)v149);
                std::wstring::~wstring(&v160, v131);
                std::wstring::~wstring(&v143, v132);
                *(_DWORD *)a2 = -2145082590;
                *(_BYTE *)(a2 + 8) = 0;
                Mtx_unlock(v146[0]);
                v150 = 1;
                v114 = v152;
                if ( v152 )
                {
                  std::thread::join((std::thread *)&v151);
                  v114 = v152;
                }
                break;
            }
          }
          else
          {
            Windows::UO::UOUpdateEx::HandleRestartReasonNone(a1, a2, v107, v155);
            Mtx_unlock(v146[0]);
            v150 = 1;
            v114 = v152;
            if ( v152 )
            {
              std::thread::join((std::thread *)&v151);
              v114 = v152;
            }
          }
          break;
      }
    }
    else
    {
      v133 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v143);
      if ( v8 < 0 )
      {
        v137 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
        *(_QWORD *)&v142 = L"External Update {}:{} - {} action executable failed without returning a result";
        *((_QWORD *)&v142 + 1) = 78;
        SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v142, v137, v133, v155);
        std::wstring::~wstring(&v160, v138);
        std::wstring::~wstring(&v143, v139);
        *(_DWORD *)a2 = v8;
        *(_BYTE *)(a2 + 8) = 0;
        Mtx_unlock(v146[0]);
        v150 = 1;
        v114 = v152;
        if ( v152 )
        {
          std::thread::join((std::thread *)&v151);
          v114 = v152;
        }
      }
      else
      {
        v134 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v160);
        *(_QWORD *)&v142 = L"External Update {}:{} - {} action results missing for update";
        *((_QWORD *)&v142 + 1) = 60;
        SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v142, v134, v133, v155);
        std::wstring::~wstring(&v160, v135);
        std::wstring::~wstring(&v143, v136);
        *(_DWORD *)a2 = -2145082597;
        *(_BYTE *)(a2 + 8) = 0;
        Mtx_unlock(v146[0]);
        v150 = 1;
        v114 = v152;
        if ( v152 )
        {
          std::thread::join((std::thread *)&v151);
          v114 = v152;
        }
      }
    }
  }
  if ( v114 )
  {
    o_terminate_0();
    goto LABEL_152;
  }
  wil::details::lambda_call__Windows::UO::UOUpdateEx::PerformExeAction_::_2_::_lambda_1___::_lambda_call__Windows::UO::UOUpdateEx::PerformExeAction_::_2_::_lambda_1___(Src);
  std::wstring::~wstring(lpFileName, v115);
  std::wstring::~wstring(&v164, v116);
  std::wstring::~wstring(v155, v117);
  std::wstring::~wstring(&v158, v118);
  std::wstring::~wstring(&v153, v119);
  UpdateExecutionInfo::~UpdateExecutionInfo((UpdateExecutionInfo *)v173);
  v13 = v192 == 0;
LABEL_111:
  if ( !v13 )
    UpdateExecutionInfo::~UpdateExecutionInfo((UpdateExecutionInfo *)v191);
  return a2;
}

```

## disassembly

```asm
0x14032cdec  mov     [rsp-8+arg_18], rbx
0x14032cdf1  push    rbp
0x14032cdf2  push    rsi
0x14032cdf3  push    rdi
0x14032cdf4  push    r12
0x14032cdf6  push    r13
0x14032cdf8  push    r14
0x14032cdfa  push    r15
0x14032cdfc  lea     rbp, [rsp-490h]
0x14032ce04  sub     rsp, 590h
0x14032ce0b  mov     rax, cs:__security_cookie
0x14032ce12  xor     rax, rsp
0x14032ce15  mov     [rbp+4C0h+var_40], rax
0x14032ce1c  mov     r13, r9
0x14032ce1f  mov     r12d, r8d
0x14032ce22  mov     r14, rdx
0x14032ce25  mov     rsi, rcx
0x14032ce28  xor     edi, edi
0x14032ce2a  mov     rax, [rcx]
0x14032ce2d  lea     rdx, [rbp+4C0h+var_200]
0x14032ce34  mov     rax, [rax+1D0h]
0x14032ce3b  call    _guard_dispatch_icall
0x14032ce40  nop
0x14032ce41  cmp     [rbp+4C0h+var_50], dil
0x14032ce48  jnz     loc_14032CED5
0x14032ce4e  mov     rax, [rsi]
0x14032ce51  lea     rdx, [rbp+4C0h+var_520]
0x14032ce55  mov     rcx, rsi
0x14032ce58  mov     rax, [rax+18h]
0x14032ce5c  call    _guard_dispatch_icall
0x14032ce61  mov     rbx, rax
0x14032ce64  mov     rax, [rsi]
0x14032ce67  lea     rdx, [rsp+5C0h+var_570]
0x14032ce6c  mov     rcx, rsi
0x14032ce6f  mov     rax, [rax+8]
0x14032ce73  call    _guard_dispatch_icall
0x14032ce78  nop
0x14032ce79  lea     rcx, aExternalUpdate_16; "External Update {}:{} - ExecutionInfo i"...
0x14032ce80  mov     qword ptr [rsp+5C0h+Src], rcx
0x14032ce85  mov     qword ptr [rsp+5C0h+Src+8], 36h ; '6'
0x14032ce8e  movaps  xmm0, xmmword ptr [rsp+5C0h+Src]
0x14032ce93  movdqa  [rsp+5C0h+var_580], xmm0
0x14032ce99  mov     r8, rbx
0x14032ce9c  mov     rdx, rax
0x14032ce9f  lea     rcx, [rsp+5C0h+var_580]
0x14032cea4  call    ??$Log@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1@Z; SystemInterface::Log<std::wstring,std::wstring>(std::wstring_view,std::wstring &&,std::wstring &&)
0x14032cea9  nop
0x14032ceaa  lea     rcx, [rsp+5C0h+var_570]
0x14032ceaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032ceb4  nop
0x14032ceb5  lea     rcx, [rbp+4C0h+var_520]
0x14032ceb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032cebe  mov     dword ptr [r14], 8024A31Fh
0x14032cec5  mov     [r14+8], dil
0x14032cec9  cmp     [rbp+4C0h+var_50], dil
0x14032ced0  jmp     loc_14032DF0B
0x14032ced5  lea     rdx, [rbp+4C0h+var_200]; struct UpdateExecutionInfo *
0x14032cedc  lea     rcx, [rbp+4C0h+var_3B0]; this
0x14032cee3  call    ??0UpdateExecutionInfo@@QEAA@AEBU0@@Z; UpdateExecutionInfo::UpdateExecutionInfo(UpdateExecutionInfo const &)
0x14032cee8  nop
0x14032cee9  xorps   xmm0, xmm0
0x14032ceec  movups  [rbp+4C0h+var_4D8], xmm0
0x14032cef0  mov     qword ptr [rbp+4C0h+var_4C8], rdi
0x14032cef4  mov     r15d, 7
0x14032cefa  mov     qword ptr [rbp+4C0h+var_4C8+8], r15
0x14032cefe  mov     word ptr [rbp+4C0h+var_4D8], di
0x14032cf02  movups  [rbp+4C0h+var_498], xmm0
0x14032cf06  mov     qword ptr [rbp+4C0h+var_488], rdi
0x14032cf0a  mov     qword ptr [rbp+4C0h+var_488+8], r15
0x14032cf0e  mov     word ptr [rbp+4C0h+var_498], di
0x14032cf12  movups  xmmword ptr [rbp+4C0h+var_4B8], xmm0
0x14032cf16  mov     [rbp+4C0h+var_4A8], rdi
0x14032cf1a  mov     [rbp+4C0h+var_4A0], r15
0x14032cf1e  mov     word ptr [rbp+4C0h+var_4B8], di
0x14032cf22  mov     ecx, r12d
0x14032cf25  test    r12d, r12d
0x14032cf28  jz      loc_14032D67C
0x14032cf2e  sub     ecx, 1
0x14032cf31  jz      loc_14032D0E5
0x14032cf37  sub     ecx, 1
0x14032cf3a  jz      loc_14032D0E5
0x14032cf40  cmp     ecx, 1
0x14032cf43  jz      short loc_14032CF7F
0x14032cf45  mov     dword ptr [r14], 8000FFFFh
0x14032cf4c  mov     [r14+8], dil
0x14032cf50  lea     rcx, [rbp+4C0h+var_4B8]
0x14032cf54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032cf59  nop
0x14032cf5a  lea     rcx, [rbp+4C0h+var_498]
0x14032cf5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032cf63  nop
0x14032cf64  lea     rcx, [rbp+4C0h+var_4D8]
0x14032cf68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032cf6d  nop
0x14032cf6e  lea     rcx, [rbp+4C0h+var_3B0]; this
0x14032cf75  call    ??1UpdateExecutionInfo@@QEAA@XZ; UpdateExecutionInfo::~UpdateExecutionInfo(void)
0x14032cf7a  jmp     loc_14032CEC9
0x14032cf7f  mov     rcx, [rbp+4C0h+var_238]
0x14032cf86  test    rcx, rcx
0x14032cf89  jz      loc_14032D045
0x14032cf8f  lea     rax, [rbp+4C0h+var_248]
0x14032cf96  cmp     [rbp+4C0h+var_230], r15
0x14032cf9d  cmova   rax, [rbp+4C0h+var_248]
0x14032cfa5  mov     qword ptr [rsp+5C0h+Src], rax
0x14032cfaa  mov     qword ptr [rsp+5C0h+Src+8], rcx
0x14032cfaf  movaps  xmm0, xmmword ptr [rsp+5C0h+Src]
0x14032cfb4  movdqa  [rsp+5C0h+var_580], xmm0
0x14032cfba  lea     rdx, [rsp+5C0h+var_580]
0x14032cfbf  lea     rcx, [rbp+4C0h+var_520]
0x14032cfc3  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14032cfc8  nop
0x14032cfc9  lea     rdx, [rsi+148h]; void *
0x14032cfd0  lea     r8, [rbp+4C0h+var_520]; void *
0x14032cfd4  lea     rcx, [rsp+5C0h+Src]; Src
0x14032cfd9  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14032cfde  nop
0x14032cfdf  mov     rdx, rax
0x14032cfe2  lea     rcx, [rsp+5C0h+var_570]
0x14032cfe7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14032cfec  lea     rcx, [rbp+4C0h+var_4D8]
0x14032cff0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032cff5  movups  xmm0, [rsp+5C0h+var_570]
0x14032cffa  movups  [rbp+4C0h+var_4D8], xmm0
0x14032cffe  movups  xmm1, [rsp+5C0h+var_560]
0x14032d003  movups  [rbp+4C0h+var_4C8], xmm1
0x14032d007  mov     qword ptr [rsp+5C0h+var_560], rdi
0x14032d00c  mov     qword ptr [rsp+5C0h+var_560+8], r15
0x14032d011  mov     word ptr [rsp+5C0h+var_570], di
0x14032d016  lea     rcx, [rsp+5C0h+var_570]
0x14032d01b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d020  nop
0x14032d021  lea     rcx, [rsp+5C0h+Src]
0x14032d026  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d02b  nop
0x14032d02c  lea     rcx, [rbp+4C0h+var_520]
0x14032d030  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d035  lea     rdx, [rbp+4C0h+var_228]
0x14032d03c  lea     rcx, [rbp+4C0h+var_498]; void *
0x14032d040  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14032d045  lea     rdx, aCloseAndRestar; "close-and-restart"
0x14032d04c  lea     rcx, [rbp+4C0h+var_4B8]; void *
0x14032d050  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14032d055  mov     rdx, rsi; struct Update *
0x14032d058  mov     rcx, [rsi+78h]; this
0x14032d05c  call    ?IsAppClosureApproved@UpdateDatabase@@QEBA_NAEBVUpdate@@@Z; UpdateDatabase::IsAppClosureApproved(Update const &)
0x14032d061  test    al, al
0x14032d063  jnz     loc_14032D7BE
0x14032d069  mov     rax, [rsi]
0x14032d06c  lea     rdx, [rbp+4C0h+var_520]
0x14032d070  mov     rcx, rsi
0x14032d073  mov     rax, [rax+18h]
0x14032d077  call    _guard_dispatch_icall
0x14032d07c  mov     rbx, rax
0x14032d07f  mov     rax, [rsi]
0x14032d082  lea     rdx, [rsp+5C0h+var_570]
0x14032d087  mov     rcx, rsi
0x14032d08a  mov     rax, [rax+8]
0x14032d08e  call    _guard_dispatch_icall
0x14032d093  nop
0x14032d094  lea     rcx, aExternalUpdate_20; "External Update {}:{} - app closure has"...
0x14032d09b  mov     qword ptr [rsp+5C0h+Src], rcx
0x14032d0a0  mov     qword ptr [rsp+5C0h+Src+8], 39h ; '9'
0x14032d0a9  movaps  xmm0, xmmword ptr [rsp+5C0h+Src]
0x14032d0ae  movdqa  [rsp+5C0h+var_580], xmm0
0x14032d0b4  mov     r8, rbx
0x14032d0b7  mov     rdx, rax
0x14032d0ba  lea     rcx, [rsp+5C0h+var_580]
0x14032d0bf  call    ??$Log@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@1@Z; SystemInterface::Log<std::wstring,std::wstring>(std::wstring_view,std::wstring &&,std::wstring &&)
0x14032d0c4  nop
0x14032d0c5  lea     rcx, [rsp+5C0h+var_570]
0x14032d0ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d0cf  nop
0x14032d0d0  lea     rcx, [rbp+4C0h+var_520]
0x14032d0d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d0d9  mov     dword ptr [r14], 8024A235h
0x14032d0e0  jmp     loc_14032CF4C
0x14032d0e5  mov     rcx, rsi; this
0x14032d0e8  call    ?HasDeployInfo@UOUpdateEx@UO@Windows@@AEBA_NXZ; Windows::UO::UOUpdateEx::HasDeployInfo(void)
0x14032d0ed  test    al, al
0x14032d0ef  jz      loc_14032D1B8
0x14032d0f5  lea     rax, [rbp+4C0h+var_3B0]
0x14032d0fc  cmp     [rbp+4C0h+var_398], r15
0x14032d103  cmova   rax, [rbp+4C0h+var_3B0]
0x14032d10b  mov     qword ptr [rsp+5C0h+Src], rax
0x14032d110  mov     rax, [rbp+4C0h+var_3A0]
0x14032d117  mov     qword ptr [rsp+5C0h+Src+8], rax
0x14032d11c  movaps  xmm0, xmmword ptr [rsp+5C0h+Src]
0x14032d121  movdqa  [rsp+5C0h+var_580], xmm0
0x14032d127  lea     rdx, [rsp+5C0h+var_580]
0x14032d12c  lea     rcx, [rbp+4C0h+var_520]
0x14032d130  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14032d135  nop
0x14032d136  lea     rbx, [rsi+148h]
0x14032d13d  lea     r8, [rbp+4C0h+var_520]; void *
0x14032d141  mov     rdx, rbx; void *
0x14032d144  lea     rcx, [rsp+5C0h+Src]; Src
0x14032d149  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14032d14e  nop
0x14032d14f  mov     rdx, rax
0x14032d152  lea     rcx, [rsp+5C0h+var_570]
0x14032d157  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14032d15c  lea     rcx, [rbp+4C0h+var_4D8]
0x14032d160  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d165  movups  xmm0, [rsp+5C0h+var_570]
0x14032d16a  movups  [rbp+4C0h+var_4D8], xmm0
0x14032d16e  movups  xmm1, [rsp+5C0h+var_560]
0x14032d173  movups  [rbp+4C0h+var_4C8], xmm1
0x14032d177  mov     qword ptr [rsp+5C0h+var_560], rdi
0x14032d17c  mov     qword ptr [rsp+5C0h+var_560+8], r15
0x14032d181  mov     word ptr [rsp+5C0h+var_570], di
0x14032d186  lea     rcx, [rsp+5C0h+var_570]
0x14032d18b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d190  nop
0x14032d191  lea     rcx, [rsp+5C0h+Src]
0x14032d196  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d19b  nop
0x14032d19c  lea     rcx, [rbp+4C0h+var_520]
0x14032d1a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d1a5  lea     r15, aDeploy; "deploy"
0x14032d1ac  lea     rdx, [rbp+4C0h+var_390]
0x14032d1b3  jmp     loc_14032D27F
0x14032d1b8  mov     rcx, [rbp+4C0h+var_310]
0x14032d1bf  test    rcx, rcx
0x14032d1c2  jz      loc_14032D600
0x14032d1c8  lea     rax, [rbp+4C0h+var_320]
0x14032d1cf  cmp     [rbp+4C0h+var_308], r15
0x14032d1d6  cmova   rax, [rbp+4C0h+var_320]
0x14032d1de  mov     qword ptr [rsp+5C0h+Src], rax
0x14032d1e3  mov     qword ptr [rsp+5C0h+Src+8], rcx
0x14032d1e8  movaps  xmm0, xmmword ptr [rsp+5C0h+Src]
0x14032d1ed  movdqa  [rsp+5C0h+var_580], xmm0
0x14032d1f3  lea     rdx, [rsp+5C0h+var_580]
0x14032d1f8  lea     rcx, [rbp+4C0h+var_520]
0x14032d1fc  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14032d201  nop
0x14032d202  lea     rbx, [rsi+148h]
0x14032d209  lea     r8, [rbp+4C0h+var_520]; void *
0x14032d20d  mov     rdx, rbx; void *
0x14032d210  lea     rcx, [rsp+5C0h+Src]; Src
0x14032d215  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14032d21a  nop
0x14032d21b  mov     rdx, rax
0x14032d21e  lea     rcx, [rsp+5C0h+var_570]
0x14032d223  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14032d228  lea     rcx, [rbp+4C0h+var_4D8]
0x14032d22c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d231  movups  xmm0, [rsp+5C0h+var_570]
0x14032d236  movups  [rbp+4C0h+var_4D8], xmm0
0x14032d23a  movups  xmm1, [rsp+5C0h+var_560]
0x14032d23f  movups  [rbp+4C0h+var_4C8], xmm1
0x14032d243  mov     qword ptr [rsp+5C0h+var_560], rdi
0x14032d248  mov     qword ptr [rsp+5C0h+var_560+8], r15
0x14032d24d  mov     word ptr [rsp+5C0h+var_570], di
0x14032d252  lea     rcx, [rsp+5C0h+var_570]
0x14032d257  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d25c  nop
0x14032d25d  lea     rcx, [rsp+5C0h+Src]
0x14032d262  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d267  nop
0x14032d268  lea     rcx, [rbp+4C0h+var_520]
0x14032d26c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032d271  lea     r15, aInstall_0; "install"
0x14032d278  lea     rdx, [rbp+4C0h+var_300]
0x14032d27f  lea     rcx, [rbp+4C0h+var_498]; void *
0x14032d283  lea     rdi, [rbp+4C0h+var_4B8]
0x14032d287  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14032d28c  mov     rdx, r15; Src
0x14032d28f  mov     rcx, rdi; void *
0x14032d292  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14032d297  xor     edi, edi
0x14032d299  mov     [rbp+4C0h+var_410], dil
0x14032d2a0  mov     [rbp+4C0h+var_3C0], dil
0x14032d2a7  mov     [rbp+4C0h+var_458], dil
0x14032d2ab  mov     rcx, rsi; this
0x14032d2ae  call    ?HasDeployInfo@UOUpdateEx@UO@Windows@@AEBA_NXZ; Windows::UO::UOUpdateEx::HasDeployInfo(void)
0x14032d2b3  lea     r15d, [rdi+7]
0x14032d2b7  test    al, al
0x14032d2b9  jz      loc_14032D38A
0x14032d2bf  mov     rcx, [rbp+4C0h+var_2C8]
0x14032d2c6  test    rcx, rcx
0x14032d2c9  jz      loc_14032D4C2
0x14032d2cf  lea     rax, [rbp+4C0h+var_2D8]
0x14032d2d6  cmp     [rbp+4C0h+var_2C0], r15
0x14032d2dd  cmova   rax, [rbp+4C0h+var_2D8]
0x14032d2e5  mov     qword ptr [rsp+5C0h+Src], rax
0x14032d2ea  mov     qword ptr [rsp+5C0h+Src+8], rcx
0x14032d2ef  movaps  xmm0, xmmword ptr [rsp+5C0h+Src]
0x14032d2f4  movdqa  [rsp+5C0h+var_580], xmm0
0x14032d2fa  lea     rdx, [rsp+5C0h+var_580]
0x14032d2ff  lea     rcx, [rsp+5C0h+var_570]
0x14032d304  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14032d309  nop
0x14032d30a  lea     r8, [rsp+5C0h+var_570]; void *
0x14032d30f  mov     rdx, rbx; void *
0x14032d312  lea     rcx, [rbp+4C0h+var_520]; Src
0x14032d316  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14032d31b  nop
0x14032d31c  mov     rdx, rax
0x14032d31f  lea     rcx, [rbp+4C0h+var_430]
0x14032d326  call    ??$?4Vpath@filesystem@std@@$0A@@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAAAEAV01@$$QEAVpath@filesystem@1@@Z; std::optional<std::wstring>::operator=<std::filesystem::path,0>(std::filesystem::path &&)
  ... truncated ...
```
