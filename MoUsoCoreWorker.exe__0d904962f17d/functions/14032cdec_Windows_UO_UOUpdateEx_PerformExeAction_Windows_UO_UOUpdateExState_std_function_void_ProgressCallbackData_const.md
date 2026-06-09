# Windows::UO::UOUpdateEx::PerformExeAction(Windows::UO::UOUpdateExState,std::function<void (ProgressCallbackData)> const &)

- ea: `0x14032cdec`
- end: `0x14032e484`
- name: `?PerformExeAction@UOUpdateEx@UO@Windows@@AEAA?AU?$pair@JV?$optional@W4UOUpdateExState@UO@Windows@@@std@@@std@@W4UOUpdateExState@23@AEBV?$function@$$A6AXUProgressCallbackData@@@Z@5@@Z`
- size: `5784`
- prototype: `__int64 __fastcall(struct Update *)`
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
// Hidden C++ exception states: #wind=43
__int64 __fastcall Windows::UO::UOUpdateEx::PerformExeAction(struct Update *a1, __int64 a2, int a3, __int64 a4)
{
  int v8; // edi
  __int64 v9; // rbx
  __int64 v10; // rax
  bool v11; // zf
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // rax
  char *v17; // rbx
  __int64 v18; // rax
  wchar_t *v19; // r15
  _QWORD *v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rax
  wchar_t *v24; // rdx
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  _QWORD *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rbx
  __int128 *v40; // rax
  struct std::error_code *v41; // r8
  bool v42; // bl
  const struct std::filesystem::path *v43; // r9
  __int64 v44; // rbx
  __int64 v45; // rax
  struct std::error_code *v46; // r8
  bool v47; // al
  const struct std::filesystem::path *v48; // r9
  const WCHAR *v49; // rcx
  unsigned __int64 v50; // rax
  __int64 v51; // rax
  struct _Mtx_internal_imp_t *v52; // rax
  int v53; // r15d
  unsigned __int8 v54; // di
  _QWORD *v55; // r15
  __int128 *v56; // rcx
  __int128 *v57; // rcx
  struct _Mtx_internal_imp_t *v58; // rax
  _QWORD *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // r8
  int v62; // edx
  int v63; // ebx
  int v64; // eax
  int v65; // eax
  int v66; // eax
  __int64 v68; // rbx
  __int64 v69; // rax
  __int64 v70; // rbx
  __int64 v71; // rax
  int v72; // ebx
  int v73; // eax
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int128 v78; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v79; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v80; // [rsp+60h] [rbp-A0h]
  char Src[16]; // [rsp+70h] [rbp-90h] BYREF
  _Mtx_t v82[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v83[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v84; // [rsp+B0h] [rbp-50h]
  _QWORD v85[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v86; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v87; // [rsp+D8h] [rbp-28h] BYREF
  int v88; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v89; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v90; // [rsp+F8h] [rbp-8h]
  __int64 v91[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v92; // [rsp+118h] [rbp+18h]
  __int64 v93; // [rsp+120h] [rbp+20h]
  __int128 v94; // [rsp+128h] [rbp+28h] BYREF
  __int128 v95; // [rsp+138h] [rbp+38h]
  __int128 v96; // [rsp+148h] [rbp+48h] BYREF
  __int64 v97; // [rsp+158h] [rbp+58h]
  __int64 v98; // [rsp+160h] [rbp+60h]
  char v99; // [rsp+168h] [rbp+68h]
  __int128 v100; // [rsp+170h] [rbp+70h] BYREF
  __int64 v101; // [rsp+180h] [rbp+80h]
  unsigned __int64 v102; // [rsp+188h] [rbp+88h]
  __int128 v103; // [rsp+190h] [rbp+90h] BYREF
  __int128 v104; // [rsp+1A0h] [rbp+A0h]
  char v105; // [rsp+1B0h] [rbp+B0h]
  LPCWSTR lpFileName[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v107[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v108; // [rsp+200h] [rbp+100h]
  _QWORD v109[4]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD *v110; // [rsp+258h] [rbp+158h] BYREF
  __int64 v111; // [rsp+268h] [rbp+168h]
  unsigned __int64 v112; // [rsp+270h] [rbp+170h]
  _QWORD *v113; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v114; // [rsp+2B0h] [rbp+1B0h]
  unsigned __int64 v115; // [rsp+2B8h] [rbp+1B8h]
  _QWORD *v116; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v117; // [rsp+2F8h] [rbp+1F8h]
  unsigned __int64 v118; // [rsp+300h] [rbp+200h]
  char v119[40]; // [rsp+308h] [rbp+208h] BYREF
  _QWORD *v120; // [rsp+330h] [rbp+230h] BYREF
  __int64 v121; // [rsp+340h] [rbp+240h]
  unsigned __int64 v122; // [rsp+348h] [rbp+248h]
  char v123[40]; // [rsp+350h] [rbp+250h] BYREF
  _QWORD *v124; // [rsp+378h] [rbp+278h] BYREF
  __int64 v125; // [rsp+388h] [rbp+288h]
  unsigned __int64 v126; // [rsp+390h] [rbp+290h]
  _BYTE v127[432]; // [rsp+3C0h] [rbp+2C0h] BYREF
  char v128; // [rsp+570h] [rbp+470h]

  v8 = 0;
  (*(void (__fastcall **)(struct Update *, _BYTE *))(*(_QWORD *)a1 + 464LL))(a1, v127);
  if ( !v128 )
  {
    v9 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v83);
    v10 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
    *(_QWORD *)Src = L"External Update {}:{} - ExecutionInfo is not populated";
    *(_QWORD *)&Src[8] = 54;
    v78 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v78, v10, v9);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    *(_DWORD *)a2 = -2145082593;
    *(_BYTE *)(a2 + 8) = 0;
LABEL_3:
    v11 = v128 == 0;
    goto LABEL_110;
  }
  UpdateExecutionInfo::UpdateExecutionInfo((UpdateExecutionInfo *)v109, (const struct UpdateExecutionInfo *)v127);
  v89 = 0;
  *(_QWORD *)&v90 = 0;
  *((_QWORD *)&v90 + 1) = 7;
  LOWORD(v89) = 0;
  v94 = 0;
  *(_QWORD *)&v95 = 0;
  *((_QWORD *)&v95 + 1) = 7;
  LOWORD(v94) = 0;
  *(_OWORD *)v91 = 0;
  v92 = 0;
  v93 = 7;
  LOWORD(v91[0]) = 0;
  if ( !a3 )
  {
    if ( v111 )
    {
      v33 = &v110;
      if ( v112 > 7 )
        v33 = v110;
      *(_QWORD *)Src = v33;
      *(_QWORD *)&Src[8] = v111;
      v78 = *(_OWORD *)Src;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v83, &v78);
      v34 = std::filesystem::operator/(&v103, (char *)a1 + 328, v83);
      std::wstring::wstring(&v79, v34);
      std::wstring::~wstring(&v89);
      v89 = v79;
      v90 = v80;
      *(_QWORD *)&v80 = 0;
      *((_QWORD *)&v80 + 1) = 7;
      LOWORD(v79) = 0;
      std::wstring::~wstring(&v79);
      std::wstring::~wstring(&v103);
      std::wstring::~wstring(v83);
      std::wstring::operator=(&v94);
      std::wstring::operator=(v91, L"download");
      goto LABEL_67;
    }
    v31 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v83);
    v32 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
    *(_QWORD *)Src = L"External Update {}:{} - Download executable is not populated";
    *(_QWORD *)&Src[8] = 60;
    v78 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v78, v32, v31);
    std::wstring::~wstring(&v79);
    goto LABEL_61;
  }
  if ( a3 == 1 || a3 == 2 )
  {
    if ( Windows::UO::UOUpdateEx::HasDeployInfo(a1) )
    {
      v16 = v109;
      if ( v109[3] > 7u )
        v16 = (_QWORD *)v109[0];
      *(_QWORD *)Src = v16;
      *(_QWORD *)&Src[8] = v109[2];
      v78 = *(_OWORD *)Src;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v83, &v78);
      v17 = (char *)a1 + 328;
      v18 = std::filesystem::operator/(Src, (char *)a1 + 328, v83);
      std::wstring::wstring(&v79, v18);
      std::wstring::~wstring(&v89);
      v89 = v79;
      v90 = v80;
      *(_QWORD *)&v80 = 0;
      *((_QWORD *)&v80 + 1) = 7;
      LOWORD(v79) = 0;
      std::wstring::~wstring(&v79);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v83);
      v19 = L"deploy";
      goto LABEL_25;
    }
    if ( v114 )
    {
      v20 = &v113;
      if ( v115 > 7 )
        v20 = v113;
      *(_QWORD *)Src = v20;
      *(_QWORD *)&Src[8] = v114;
      v78 = *(_OWORD *)Src;
      std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v83, &v78);
      v17 = (char *)a1 + 328;
      v21 = std::filesystem::operator/(Src, (char *)a1 + 328, v83);
      std::wstring::wstring(&v79, v21);
      std::wstring::~wstring(&v89);
      v89 = v79;
      v90 = v80;
      *(_QWORD *)&v80 = 0;
      *((_QWORD *)&v80 + 1) = 7;
      LOWORD(v79) = 0;
      std::wstring::~wstring(&v79);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v83);
      v19 = L"install";
LABEL_25:
      std::wstring::operator=(&v94);
      std::wstring::operator=(v91, v19);
      v8 = 0;
      v105 = 0;
      v108 = 0;
      v99 = 0;
      if ( Windows::UO::UOUpdateEx::HasDeployInfo(a1) )
      {
        if ( !v117 )
          goto LABEL_46;
        v22 = &v116;
        if ( v118 > 7 )
          v22 = v116;
        *(_QWORD *)Src = v22;
        *(_QWORD *)&Src[8] = v117;
        v78 = *(_OWORD *)Src;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v79, &v78);
        v23 = std::filesystem::operator/(v83, v17, &v79);
        std::optional<std::wstring>::operator=<std::filesystem::path,0>(&v103, v23);
        std::wstring::~wstring(v83);
        std::wstring::~wstring(&v79);
        if ( v108 )
        {
          std::wstring::operator=(v107);
        }
        else
        {
          std::wstring::wstring(v107, v119);
          v108 = 1;
        }
        v24 = L"close-and-deploy";
        if ( !v99 )
        {
LABEL_45:
          v96 = 0;
          v97 = 0;
          v98 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v96, v24);
          v99 = 1;
LABEL_46:
          if ( v105 && (_QWORD)v104 && v99 && UpdateDatabase::IsAppClosureApproved(*((UpdateDatabase **)a1 + 15), a1) )
          {
            v27 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v83);
            v28 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
            *(_QWORD *)Src = L"External Update {}:{} - AppClose has been approved for install";
            *(_QWORD *)&Src[8] = 62;
            v78 = *(_OWORD *)Src;
            SystemInterface::Log<std::wstring,std::wstring>(&v78, v28, v27);
            std::wstring::~wstring(&v79);
            std::wstring::~wstring(v83);
            if ( !v105 || (std::wstring::operator=(&v89), !v108) || (std::wstring::operator=(&v94), !v99) )
              std::_Throw_bad_optional_access();
            std::wstring::operator=(v91);
          }
          if ( v99 )
            std::wstring::~wstring(&v96);
          if ( v108 )
            std::wstring::~wstring(v107);
          if ( v105 )
            std::wstring::~wstring(&v103);
          goto LABEL_67;
        }
      }
      else
      {
        if ( !v121 )
          goto LABEL_46;
        v25 = &v120;
        if ( v122 > 7 )
          v25 = v120;
        *(_QWORD *)Src = v25;
        *(_QWORD *)&Src[8] = v121;
        v78 = *(_OWORD *)Src;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v83, &v78);
        v26 = std::filesystem::operator/(Src, v17, v83);
        if ( v105 )
        {
          std::wstring::wstring(&v79, v26);
          std::wstring::~wstring(&v103);
          v103 = v79;
          v104 = v80;
          *(_QWORD *)&v80 = 0;
          *((_QWORD *)&v80 + 1) = 7;
          LOWORD(v79) = 0;
          std::wstring::~wstring(&v79);
        }
        else
        {
          std::wstring::wstring(&v103, v26);
          v105 = 1;
        }
        std::wstring::~wstring(Src);
        std::wstring::~wstring(v83);
        if ( v108 )
        {
          std::wstring::operator=(v107);
        }
        else
        {
          std::wstring::wstring(v107, v123);
          v108 = 1;
        }
        v24 = L"close-and-install";
        if ( !v99 )
          goto LABEL_45;
      }
      std::wstring::operator=(&v96, v24);
      goto LABEL_46;
    }
    v29 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v83);
    v30 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
    *(_QWORD *)Src = L"External Update {}:{} - Executable path is not populated";
    *(_QWORD *)&Src[8] = 56;
    v78 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v78, v30, v29);
    std::wstring::~wstring(&v79);
LABEL_61:
    std::wstring::~wstring(v83);
    *(_DWORD *)a2 = -2145082593;
    goto LABEL_9;
  }
  if ( a3 != 3 )
  {
    *(_DWORD *)a2 = -2147418113;
LABEL_9:
    *(_BYTE *)(a2 + 8) = 0;
LABEL_10:
    std::wstring::~wstring(v91);
    std::wstring::~wstring(&v94);
    std::wstring::~wstring(&v89);
    UpdateExecutionInfo::~UpdateExecutionInfo((UpdateExecutionInfo *)v109);
    goto LABEL_3;
  }
  if ( v125 )
  {
    v12 = &v124;
    if ( v126 > 7 )
      v12 = v124;
    *(_QWORD *)Src = v12;
    *(_QWORD *)&Src[8] = v125;
    v78 = *(_OWORD *)Src;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v83, &v78);
    v13 = std::filesystem::operator/(Src, (char *)a1 + 328, v83);
    std::wstring::wstring(&v79, v13);
    std::wstring::~wstring(&v89);
    v89 = v79;
    v90 = v80;
    *(_QWORD *)&v80 = 0;
    *((_QWORD *)&v80 + 1) = 7;
    LOWORD(v79) = 0;
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v83);
    std::wstring::operator=(&v94);
  }
  std::wstring::operator=(v91, L"close-and-restart");
  if ( !UpdateDatabase::IsAppClosureApproved(*((UpdateDatabase **)a1 + 15), a1) )
  {
    v14 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v83);
    v15 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
    *(_QWORD *)Src = L"External Update {}:{} - app closure has not been approved";
    *(_QWORD *)&Src[8] = 57;
    v78 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v78, v15, v14);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    *(_DWORD *)a2 = -2145082827;
    goto LABEL_9;
  }
LABEL_67:
  v35 = *(_QWORD *)a1;
  if ( !(_QWORD)v90 )
  {
    v36 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(v35 + 24))(a1, v83);
    v37 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
    *(_QWORD *)Src = L"External Update {}:{} - Executable path is not populated";
    *(_QWORD *)&Src[8] = 56;
    v78 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring>(&v78, v37, v36);
    std::wstring::~wstring(&v79);
    goto LABEL_61;
  }
  v100 = 0;
  v101 = 0;
  v102 = 7;
  LOWORD(v100) = 0;
  if ( (*(unsigned int (__fastcall **)(struct Update *))(v35 + 416))(a1) == 3 )
  {
    std::wstring::operator=(&v100);
    v38 = wil::ExpandEnvironmentStringsW<std::wstring,256>(
            &v79,
            L"%SystemRoot%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe");
    if ( &v89 != (__int128 *)v38 )
    {
      std::wstring::~wstring(&v89);
      v89 = *(_OWORD *)v38;
      v90 = *(_OWORD *)(v38 + 16);
      *(_QWORD *)(v38 + 16) = 0;
      *(_QWORD *)(v38 + 24) = 7;
      *(_WORD *)v38 = 0;
    }
    std::wstring::~wstring(&v79);
    *(_QWORD *)Src = L"-NoLogo -NoProfile -NonInteractive -ExecutionPolicy Bypass -File \"{}\" {}";
    *(_QWORD *)&Src[8] = 72;
    v78 = *(_OWORD *)Src;
    v39 = std::format<std::wstring const &,std::wstring const &>(&v79);
    if ( &v94 != (__int128 *)v39 )
    {
      std::wstring::~wstring(&v94);
      v94 = *(_OWORD *)v39;
      v95 = *(_OWORD *)(v39 + 16);
      *(_QWORD *)(v39 + 16) = 0;
      *(_QWORD *)(v39 + 24) = 7;
      *(_WORD *)v39 = 0;
    }
    std::wstring::~wstring(&v79);
  }
  v40 = &v89;
  if ( *((_QWORD *)&v90 + 1) > 7u )
    v40 = (__int128 *)v89;
  *(_QWORD *)Src = v40;
  *(_QWORD *)&Src[8] = v90;
  v78 = *(_OWORD *)Src;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v79, &v78);
  *(_QWORD *)Src = 0;
  *(_QWORD *)&Src[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v42 = std::filesystem::exists((std::filesystem *)&v79, (const struct std::filesystem::path *)Src, v41);
  if ( *(_DWORD *)Src )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", Src, (const struct std::error_code *)&v79, v43);
  std::wstring::~wstring(&v79);
  if ( !v42 )
  {
    v44 = (*(__int64 (__fastcall **)(struct Update *, _QWORD *))(*(_QWORD *)a1 + 24LL))(a1, v83);
    v45 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v79);
    *(_QWORD *)Src = L"External Update {}:{} - Executable path does not exist: {}";
    *(_QWORD *)&Src[8] = 58;
    v78 = *(_OWORD *)Src;
    SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v78, v45, v44, &v89);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    *(_DWORD *)a2 = -2145082592;
    *(_BYTE *)(a2 + 8) = 0;
    std::wstring::~wstring(&v100);
    goto LABEL_10;
  }
  *(_QWORD *)Src = L"State";
  *(_QWORD *)&Src[8] = 5;
  v78 = *(_OWORD *)Src;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v79, &v78);
  std::filesystem::operator/(lpFileName, (char *)a1 + 328, &v79);
  std::wstring::~wstring(&v79);
  *(_QWORD *)Src = 0;
  *(_QWORD *)&Src[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v47 = std::filesystem::exists((std::filesystem *)lpFileName, (const struct std::filesystem::path *)Src, v46);
  if ( *(_DWORD *)Src )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", Src, (const struct std::error_code *)lpFileName, v48);
  if ( !v47 )
  {
    v49 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v49 = lpFileName[0];
    v50 = (unsigned __int64)_std_fs_create_directory(v49) >> 32;
    if ( (_DWORD)v50 )
      std::filesystem::_Throw_fs_error("create_directory", (unsigned int)v50, lpFileName);
  }
  *(_QWORD *)&Src[8] = 1;
  *(_QWORD *)Src = a1;
  v85[0] = (char *)a1 + 128;
  if ( (unsigned int)mtx_do_lock((char *)a1 + 128, 0) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)a1 + 51) == 0x7FFFFFFF )
  {
    *((_DWORD *)a1 + 51) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v82[0] = (_Mtx_t)(*(_QWORD *)std::chrono::steady_clock::now(v82) / 1000LL);
  *(_QWORD *)&v103 = L"{:016X}:Action:{}";
  *((_QWORD *)&v103 + 1) = 17;
  v78 = v103;
  v51 = std::format<__int64 &,std::wstring &>(&v79);
  std::optional<std::wstring>::operator=<std::wstring,0>((char *)a1 + 208, v51);
  std::wstring::~wstring(&v79);
  v11 = (*((_DWORD *)a1 + 51))-- == 1;
  if ( v11 )
  {
    *((_DWORD *)a1 + 50) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 18);
  }
  v86 = 0;
  *(_QWORD *)&v79 = a1;
  *((_QWORD *)&v79 + 1) = &v86;
  *(_QWORD *)&v80 = a4;
  *((_QWORD *)&v80 + 1) = v91;
  v52 = (struct _Mtx_internal_imp_t *)operator new(0x20u);
  *(_OWORD *)v52 = v79;
  *((_OWORD *)v52 + 1) = v80;
  v82[0] = v52;
  v87 = o__beginthreadex_0(
          0,
          0,
          std::thread::_Invoke_std::tuple__Windows::UO::UOUpdateEx::PerformExeAction_::_2_::_lambda_2____0_,
          v52,
          0);
  if ( !v87 )
  {
LABEL_151:
    v88 = v8;
    std::_Throw_Cpp_error(6);
  }
  v83[0] = &v86;
  v83[1] = &v87;
  v84 = 1;
  *((_QWORD *)&v78 + 1) = 1;
  v8 = (_DWORD)a1 + 320;
  *(_QWORD *)&v78 = (char *)a1 + 320;
  AcquireSRWLockShared((PSRWLOCK)a1 + 40);
  v85[0] = &v79;
  std::wstring::wstring(&v79, (char *)a1 + 328);
  (***((void (__fastcall ****)(_QWORD, _Mtx_t *))a1 + 39))(*((_QWORD *)a1 + 39), v82);
  v53 = Windows::UO::VerifyProviderTrust(v82, &v79);
  LODWORD(v85[0]) = v53;
  ReleaseSRWLockShared((PSRWLOCK)a1 + 40);
  if ( v53 < 0 )
  {
    v77 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
    *(_QWORD *)&v78 = L"Provider {} - Failed trust chain validation during Action {} attempt: {}";
    *((_QWORD *)&v78 + 1) = 72;
    SystemInterface::Log<std::wstring,std::wstring &,long &>(&v78, v77, v91, v85);
    std::wstring::~wstring(&v96);
    *(_DWORD *)a2 = v53;
    *(_BYTE *)(a2 + 8) = 0;
    v86 = 1;
    v66 = v88;
    if ( v88 )
    {
      std::thread::join((std::thread *)&v87);
      v66 = v88;
    }
  }
  else
  {
    if ( !*((_BYTE *)a1 + 308) || (v54 = 1, *((_DWORD *)a1 + 76) != 1) )
      v54 = 0;
    v55 = (_QWORD *)Windows::UO::UOUpdateEx::CreateActionEnvironmentBlock(a1, &v79);
    v56 = &v100;
    if ( v102 > 7 )
      v56 = (__int128 *)v100;
    *(_QWORD *)&v78 = v56;
    *((_QWORD *)&v78 + 1) = v101;
    v57 = &v94;
    if ( *((_QWORD *)&v95 + 1) > 7u )
      v57 = (__int128 *)v94;
    *(_QWORD *)&v103 = v57;
    *((_QWORD *)&v103 + 1) = v95;
    v58 = (struct _Mtx_internal_imp_t *)&v89;
    if ( *((_QWORD *)&v90 + 1) > 7u )
      v58 = (struct _Mtx_internal_imp_t *)v89;
    v82[0] = v58;
    v82[1] = (_Mtx_t)v90;
    v59 = (_QWORD *)(*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
    v60 = v59[2];
    if ( v59[3] > 7u )
      v59 = (_QWORD *)*v59;
    v85[0] = v59;
    v85[1] = v60;
    v8 = Windows::UO::ExecuteBinary_0(v85, v82, &v103, (__int64)&v78, v55, (int)&v88, v54);
    std::wstring::~wstring(&v96);
    std::vector<wchar_t>::_Tidy(&v79);
    v86 = 1;
    std::lock_guard<std::mutex>::lock_guard<std::mutex>(v82, (char *)a1 + 128);
    if ( *((_BYTE *)a1 + 296) )
    {
      v61 = *((unsigned int *)a1 + 68);
      v62 = *((_DWORD *)a1 + 69);
      v8 = *((_DWORD *)a1 + 70);
      LODWORD(v85[0]) = v8;
      switch ( (_DWORD)v61 )
      {
        case 2:
          v63 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v79);
          v64 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
          *(_QWORD *)&v78 = L"External Update {}:{} - {} action failed with HRESULT: {}";
          *((_QWORD *)&v78 + 1) = 57;
          SystemInterface::Log<std::wstring,std::wstring,std::wstring const &,int>(
            (unsigned int)&v78,
            v64,
            v63,
            (unsigned int)v91,
            (__int64)v85);
          std::wstring::~wstring(&v96);
          std::wstring::~wstring(&v79);
          v65 = -2147467259;
          if ( v8 < 0 )
            v65 = v8;
          *(_DWORD *)a2 = v65;
          *(_BYTE *)(a2 + 8) = 0;
          Mtx_unlock(v82[0]);
          v86 = 1;
          v66 = v88;
          if ( v88 )
          {
            std::thread::join((std::thread *)&v87);
            v66 = v88;
          }
          break;
        case 3:
          v68 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v79);
          v69 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
          *(_QWORD *)&v78 = L"External Update {}:{} - {} action was canceled";
          *((_QWORD *)&v78 + 1) = 46;
          SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v78, v69, v68, v91);
          std::wstring::~wstring(&v96);
          std::wstring::~wstring(&v79);
          *(_DWORD *)a2 = -2147467260;
          *(_BYTE *)(a2 + 8) = 0;
          Mtx_unlock(v82[0]);
          v86 = 1;
          v66 = v88;
          if ( v88 )
          {
            std::thread::join((std::thread *)&v87);
            v66 = v88;
          }
          break;
        case 4:
          v70 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v79);
          v71 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
          *(_QWORD *)&v78 = L"External Update {}:{} - {} action was removed";
          *((_QWORD *)&v78 + 1) = 45;
          SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v78, v71, v70, v91);
          std::wstring::~wstring(&v96);
          std::wstring::~wstring(&v79);
          *(_DWORD *)a2 = 0;
          *(_DWORD *)(a2 + 4) = 5;
          *(_BYTE *)(a2 + 8) = 1;
          Mtx_unlock(v82[0]);
          v86 = 1;
          v66 = v88;
          if ( v88 )
          {
            std::thread::join((std::thread *)&v87);
            v66 = v88;
          }
          break;
        default:
          if ( v62 )
          {
            switch ( v62 )
            {
              case 1:
                Windows::UO::UOUpdateEx::HandleRestartReasonSystem(a1, (__int64)v91);
                Mtx_unlock(v82[0]);
                v86 = 1;
                v66 = v88;
                if ( v88 )
                {
                  std::thread::join((std::thread *)&v87);
                  v66 = v88;
                }
                break;
              case 2:
                Windows::UO::UOUpdateEx::HandleRestartReasonAppClose(a1);
                Mtx_unlock(v82[0]);
                v86 = 1;
                v66 = v88;
                if ( v88 )
                {
                  std::thread::join((std::thread *)&v87);
                  v66 = v88;
                }
                break;
              case 3:
                Windows::UO::UOUpdateEx::HandleRestartReasonAppRestart(a1, a2, v61, v91);
                Mtx_unlock(v82[0]);
                v86 = 1;
                v66 = v88;
                if ( v88 )
                {
                  std::thread::join((std::thread *)&v87);
                  v66 = v88;
                }
                break;
              default:
                LODWORD(v85[0]) = v62;
                v72 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v79);
                v73 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
                *(_QWORD *)&v78 = L"External Update {}:{} - {} action returned an unsupported restart reason: {}";
                *((_QWORD *)&v78 + 1) = 76;
                SystemInterface::Log<std::wstring,std::wstring,std::wstring const &,int>(
                  (unsigned int)&v78,
                  v73,
                  v72,
                  (unsigned int)v91,
                  (__int64)v85);
                std::wstring::~wstring(&v96);
                std::wstring::~wstring(&v79);
                *(_DWORD *)a2 = -2145082590;
                *(_BYTE *)(a2 + 8) = 0;
                Mtx_unlock(v82[0]);
                v86 = 1;
                v66 = v88;
                if ( v88 )
                {
                  std::thread::join((std::thread *)&v87);
                  v66 = v88;
                }
                break;
            }
          }
          else
          {
            Windows::UO::UOUpdateEx::HandleRestartReasonNone(a1, a2, v61, v91);
            Mtx_unlock(v82[0]);
            v86 = 1;
            v66 = v88;
            if ( v88 )
            {
              std::thread::join((std::thread *)&v87);
              v66 = v88;
            }
          }
          break;
      }
    }
    else
    {
      v74 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v79);
      if ( v8 < 0 )
      {
        v76 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
        *(_QWORD *)&v78 = L"External Update {}:{} - {} action executable failed without returning a result";
        *((_QWORD *)&v78 + 1) = 78;
        SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v78, v76, v74, v91);
        std::wstring::~wstring(&v96);
        std::wstring::~wstring(&v79);
        *(_DWORD *)a2 = v8;
        *(_BYTE *)(a2 + 8) = 0;
        Mtx_unlock(v82[0]);
        v86 = 1;
        v66 = v88;
        if ( v88 )
        {
          std::thread::join((std::thread *)&v87);
          v66 = v88;
        }
      }
      else
      {
        v75 = (*(__int64 (__fastcall **)(struct Update *, __int128 *))(*(_QWORD *)a1 + 8LL))(a1, &v96);
        *(_QWORD *)&v78 = L"External Update {}:{} - {} action results missing for update";
        *((_QWORD *)&v78 + 1) = 60;
        SystemInterface::Log<std::wstring,std::wstring,std::wstring &>(&v78, v75, v74, v91);
        std::wstring::~wstring(&v96);
        std::wstring::~wstring(&v79);
        *(_DWORD *)a2 = -2145082597;
        *(_BYTE *)(a2 + 8) = 0;
        Mtx_unlock(v82[0]);
        v86 = 1;
        v66 = v88;
        if ( v88 )
        {
          std::thread::join((std::thread *)&v87);
          v66 = v88;
        }
      }
    }
  }
  if ( v66 )
  {
    o_terminate_0();
    goto LABEL_151;
  }
  wil::details::lambda_call__Windows::UO::UOUpdateEx::PerformExeAction_::_2_::_lambda_1___::_lambda_call__Windows::UO::UOUpdateEx::PerformExeAction_::_2_::_lambda_1___(Src);
  std::wstring::~wstring(lpFileName);
  std::wstring::~wstring(&v100);
  std::wstring::~wstring(v91);
  std::wstring::~wstring(&v94);
  std::wstring::~wstring(&v89);
  UpdateExecutionInfo::~UpdateExecutionInfo((UpdateExecutionInfo *)v109);
  v11 = v128 == 0;
LABEL_110:
  if ( !v11 )
    UpdateExecutionInfo::~UpdateExecutionInfo((UpdateExecutionInfo *)v127);
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
