# CloudSyncStateTelemetry::LogPrimaryState_(ushort const *,PrimaryStateReason,PrimarySyncState,PrimarySyncState,ulong,FolderEnumerationState const &,SyncItemStateData const &,__int64)

- ea: `0x18021a0b0`
- end: `0x18021b2a2`
- name: `?LogPrimaryState_@CloudSyncStateTelemetry@@QEBAXPEBGW4PrimaryStateReason@@W4PrimarySyncState@@2KAEBUFolderEnumerationState@@AEBUSyncItemStateData@@_J@Z`
- size: `4594`
- prototype: `void __high(const unsigned __int16 *, enum PrimaryStateReason, enum PrimarySyncState, enum PrimarySyncState, unsigned int, const struct FolderEnumerationState *, const struct SyncItemStateData *, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180219f18`
- `0x1802582e0`

## callees

- `0x18001aec0`
- `0x18001b390`
- `0x18001c14c`
- `0x18001c260`
- `0x18014c740`
- `0x18014d4e0`
- `0x180209f14`
- `0x18021a0b0`
- `0x180260fdc`
- `0x1803440d0`
- `0x1803a4cb0`
- `0x1803a513c`
- `0x1804206e8`
- `0x180518768`
- `0x18065a010`

## import_xrefs

- `ntdll!EtwEventSetInformation` at `0x18021a254`
- `ntdll!EtwEventSetInformation` at `0x18021a254`
- `ntdll!EtwEventRegister` at `0x18021a23b`
- `ntdll!EtwEventRegister` at `0x18021a23b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18021a283`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18021a283`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021a184`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021a184`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18021a140`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18021a140`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a2fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a56e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a8f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021aace`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a2fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a56e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021a8f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021aace`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021aefb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021aefb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021af71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b110`

## string_xrefs

- `0x18021b14f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b161`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b176`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b188`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b19d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b1b2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b1c7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b1dc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b1ee`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b200`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b212`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b224`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b236`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b248`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b25a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b26c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b27e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b290`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18021b0fb`: `---- Enumeration(%s) Complete: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall CloudSyncStateTelemetry::LogPrimaryState_(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        struct SyncItemStateData *a8,
        __int64 a9)
{
  int v9; // esi
  struct SyncItemStateData *v10; // r15
  LPWSTR ExtensionW; // rax
  unsigned int v12; // r12d
  struct _tlgProvider_t *v13; // rbx
  wchar_t **v14; // r13
  const wchar_t *v15; // r14
  int v16; // esi
  __int64 v17; // rcx
  const WCHAR *v18; // rax
  rsize_t v19; // rbx
  _WORD *v20; // rax
  const char *v21; // r9
  _WORD *v22; // r15
  char v23; // al
  const QITAB *v24; // rbx
  const wchar_t *v25; // r8
  int v26; // r12d
  wchar_t *v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  unsigned int v32; // r12d
  wchar_t **v33; // rax
  const wchar_t *v34; // rbx
  __int64 v35; // rcx
  const wchar_t *v36; // rax
  rsize_t v37; // rdi
  char *v38; // rax
  const char *v39; // r9
  char *v40; // r13
  int v41; // r12d
  unsigned int v42; // r12d
  int v43; // esi
  __int64 v44; // rcx
  const WCHAR *v45; // rax
  rsize_t v46; // rbx
  _WORD *v47; // rax
  const char *v48; // r9
  _WORD *v49; // r14
  int v50; // r12d
  unsigned int v51; // r12d
  char v52; // al
  _QWORD *v53; // rbx
  const wchar_t *v54; // r8
  int v55; // r12d
  wchar_t *v56; // r9
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  int v60; // eax
  unsigned int v61; // r12d
  int v62; // r13d
  __int64 v63; // rcx
  const WCHAR *v64; // rax
  rsize_t v65; // rbx
  _WORD *v66; // rax
  const char *v67; // r9
  _WORD *v68; // rsi
  int v69; // r12d
  unsigned int v70; // r12d
  char v71; // al
  void **v72; // rbx
  const wchar_t *v73; // r8
  int v74; // r12d
  wchar_t *v75; // r9
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // rax
  int v79; // eax
  unsigned int v80; // r12d
  __int64 v81; // rcx
  const WCHAR *v82; // rax
  rsize_t v83; // rbx
  _WORD *v84; // rax
  const char *v85; // r9
  _WORD *v86; // rdi
  int v87; // r12d
  unsigned int v88; // r12d
  char v89; // al
  wchar_t **v90; // rbx
  int v91; // r13d
  const wchar_t *v92; // r8
  int v93; // r12d
  wchar_t *v94; // r9
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // rax
  int v98; // eax
  unsigned int v99; // r12d
  const WCHAR *v100; // rax
  __int64 v101; // rcx
  rsize_t v102; // r13
  _WORD *v103; // rax
  const char *v104; // r9
  _WORD *v105; // rbx
  int v106; // r12d
  unsigned int v107; // r12d
  char v108; // al
  _QWORD *v109; // r13
  unsigned int v110; // ecx
  const wchar_t *v111; // r8
  int v112; // r12d
  wchar_t *v113; // r9
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // rax
  int v117; // eax
  unsigned int v118; // r12d
  int v119; // ecx
  wchar_t **v120; // rax
  const wchar_t *v121; // rdx
  const char *v122; // r9
  int v123; // r12d
  unsigned int v124; // r12d
  wchar_t **v125; // rax
  const wchar_t *v126; // rdx
  const char *v127; // r9
  int v128; // r12d
  unsigned int v129; // r12d
  wchar_t **v130; // rax
  const wchar_t *v131; // rdx
  int v132; // r8d
  const char *v133; // r9
  unsigned int v134; // r12d
  const wchar_t *v135; // rax
  __int64 PrimaryStateReasonString; // rdi
  wchar_t **v137; // rcx
  const wchar_t *v138; // rdx
  const char *v139; // r9
  int v140; // ebx
  const unsigned __int16 *v141; // r8
  unsigned int v142; // edi
  wchar_t **v143; // rax
  const wchar_t *v144; // rdx
  const char *v145; // r9
  struct SyncItemStateData *v146; // rcx
  int v147; // eax
  const wchar_t *v148; // rdi
  const char *v149; // r9
  int v150; // [rsp+20h] [rbp-110h]
  _WORD *v151; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v152; // [rsp+B8h] [rbp-78h]
  struct SyncItemStateData *v153; // [rsp+C0h] [rbp-70h] BYREF
  int v154; // [rsp+C8h] [rbp-68h]
  const wchar_t *v155; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v156; // [rsp+D8h] [rbp-58h] BYREF
  unsigned int v157; // [rsp+E0h] [rbp-50h] BYREF
  int v158; // [rsp+E4h] [rbp-4Ch] BYREF
  int v159; // [rsp+E8h] [rbp-48h] BYREF
  LPVOID v160; // [rsp+F0h] [rbp-40h] BYREF
  _WORD *v161; // [rsp+F8h] [rbp-38h] BYREF
  _WORD *v162; // [rsp+100h] [rbp-30h] BYREF
  _WORD *v163; // [rsp+108h] [rbp-28h] BYREF
  _WORD *v164; // [rsp+110h] [rbp-20h] BYREF
  _WORD *v165; // [rsp+118h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+120h] [rbp-10h] BYREF
  LPVOID v167; // [rsp+128h] [rbp-8h] BYREF
  _WORD *v168; // [rsp+130h] [rbp+0h] BYREF
  char *v169; // [rsp+138h] [rbp+8h] BYREF
  _WORD *v170; // [rsp+140h] [rbp+10h] BYREF
  _WORD *v171; // [rsp+148h] [rbp+18h] BYREF
  _WORD *v172; // [rsp+150h] [rbp+20h] BYREF
  LPVOID v173; // [rsp+158h] [rbp+28h] BYREF
  LPVOID v174; // [rsp+160h] [rbp+30h] BYREF
  __int64 v175; // [rsp+168h] [rbp+38h] BYREF
  _DWORD *v176; // [rsp+170h] [rbp+40h]
  LPVOID v177; // [rsp+178h] [rbp+48h]
  const WCHAR *v178; // [rsp+180h] [rbp+50h]
  char *v179; // [rsp+188h] [rbp+58h]
  LPVOID Context; // [rsp+190h] [rbp+60h] BYREF
  _DWORD v181[2]; // [rsp+198h] [rbp+68h] BYREF
  int v182; // [rsp+1A0h] [rbp+70h]
  int v183; // [rsp+1A4h] [rbp+74h]
  int v184; // [rsp+1A8h] [rbp+78h]
  int v185; // [rsp+1ACh] [rbp+7Ch]
  WINBOOL fPending[2]; // [rsp+1B0h] [rbp+80h] BYREF
  __int128 v187; // [rsp+1B8h] [rbp+88h] BYREF
  __int64 v188; // [rsp+1D0h] [rbp+A0h] BYREF
  __int64 v189; // [rsp+1D8h] [rbp+A8h]
  _WORD *v190; // [rsp+1E0h] [rbp+B0h]
  __int64 v191; // [rsp+1E8h] [rbp+B8h]
  const wchar_t *v192; // [rsp+1F0h] [rbp+C0h]
  __int64 v193; // [rsp+1F8h] [rbp+C8h]
  wchar_t *v194; // [rsp+200h] [rbp+D0h]
  __int64 v195; // [rsp+208h] [rbp+D8h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+128h]

  v9 = a4;
  v154 = a4;
  LODWORD(v155) = a3;
  v178 = a2;
  v10 = a8;
  v153 = a8;
  v152 = a6;
  fPending[0] = 0;
  v181[0] = *(_DWORD *)a8;
  v181[1] = *((_DWORD *)a8 + 1);
  v182 = *((_DWORD *)a8 + 2);
  v183 = *((_DWORD *)a8 + 3);
  v184 = *((_DWORD *)a8 + 4);
  v185 = *((_DWORD *)a8 + 5);
  ExtensionW = PathFindExtensionW(a2);
  v156 = ExtensionW;
  if ( (v181[0] & 0x10) != 0 || !ExtensionW || !*ExtensionW )
    v156 = L"Folder";
  Context = 0;
  fPending[0] = 0;
  v12 = 2;
  if ( InitOnceBeginInitialize(&`CloudFileProvider::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
  {
    Context = &qword_180805E08;
    qword_180805E10 = 0;
    byte_180805E18 = 0;
    dword_180805E1C = 0;
    qword_180805E08 = &ShellEdpLogging::`vftable';
    qword_180805E20 = (struct _tlgProvider_t *)&`CloudFileProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_eaf6c2cdbe1fd0eabf0c712e7f531564_::_lambda_invoker_cdecl_);
    v13 = qword_180805E20;
    qword_180805E10 = (__int64)qword_180805E20;
    byte_180805E18 = 1;
    v187 = *(_OWORD *)(*((_QWORD *)qword_180805E20 + 1) - 16LL);
    if ( *((_QWORD *)qword_180805E20 + 4) )
      __fastfail(5u);
    *((_QWORD *)qword_180805E20 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    if ( !(unsigned int)EtwEventRegister(&v187, tlgEnableCallback, v13, (char *)v13 + 32) )
      EtwEventSetInformation(*((_QWORD *)v13 + 4), 2, *((_QWORD *)v13 + 1), **((unsigned __int16 **)v13 + 1));
    dword_180805E1C = 1;
    (*(void (__fastcall **)(void *))(qword_180805E08 + 8LL))(&qword_180805E08);
    InitOnceComplete(&`CloudFileProvider::Instance'::`2'::wrapper, 0, &qword_180805E08);
  }
  v176 = (_DWORD *)*((_QWORD *)Context + 1);
  v14 = (wchar_t **)&unk_1806D0AA0;
  v15 = L"???";
  if ( *v176 <= 5u )
  {
    v134 = (unsigned int)v155;
  }
  else
  {
    *(_QWORD *)&v187 = v181;
    DWORD2(v187) = 24;
    v16 = v185;
    v17 = 0x7FFFFFFF;
    v18 = &WindowName;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v17;
    }
    while ( v17 );
    v19 = 2 * (v18 - &WindowName);
    v20 = CoTaskMemAlloc(v19 + 2);
    v22 = v20;
    if ( v20 )
    {
      memcpy_s_0(v20, v19 + 2, &WindowName, v19);
      v22[v19 / 2] = 0;
    }
    v161 = v22;
    fPending[0] = 4;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v21);
    v23 = 1;
    v24 = (const QITAB *)&unk_180681400;
    do
    {
      if ( (v16 & (__int64)v24->piid) != 0 )
      {
        v25 = &WindowName;
        if ( !v23 )
          v25 = L", ";
        v151 = 0;
        v26 = v12 | 8;
        fPending[0] = v26;
        v27 = *(wchar_t **)&v24->dwOffset;
        if ( v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        else
        {
          v28 = 0;
        }
        v29 = -1;
        do
          ++v29;
        while ( v25[v29] );
        if ( v22 )
        {
          v30 = -1;
          do
            ++v30;
          while ( v22[v30] );
        }
        else
        {
          v30 = 0;
        }
        v188 = 0;
        v189 = 0;
        v190 = v22;
        v191 = v30;
        v192 = v25;
        v193 = v29;
        v194 = v27;
        v195 = v28;
        v31 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v151,
                &v188,
                4);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7B3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v31,
            v150);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v161,
          v151);
        v12 = v26 & 0xFFFFFFF7;
        v23 = 0;
        v22 = v161;
      }
      ++v24;
    }
    while ( v24 != &`CImageManager::QueryInterface'::`2'::qit );
    v32 = v12 & 0xFFFFFFFC | 1;
    v168 = v22;
    v33 = (wchar_t **)&unk_1806D0AA0;
    while ( v184 != *(_DWORD *)v33 )
    {
      v33 += 2;
      if ( v33 == off_1806D0BB0 )
      {
        v34 = L"???";
        goto LABEL_43;
      }
    }
    v34 = v33[1];
LABEL_43:
    if ( !v34 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v21);
    v35 = 0x7FFFFFFF;
    v36 = v34;
    do
    {
      if ( !*v36 )
        break;
      ++v36;
      --v35;
    }
    while ( v35 );
    v37 = 2 * (v36 - v34);
    v38 = (char *)CoTaskMemAlloc(v37 + 2);
    v40 = v38;
    v177 = v38;
    if ( v38 )
    {
      memcpy_s_0(v38, v37 + 2, v34, v37);
      *(_WORD *)&v40[v37] = 0;
    }
    v179 = v40;
    v41 = v32 | 0x40;
    fPending[0] = v41;
    if ( !v40 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v39);
    fPending[0] = v41 & 0xFFFFFFBF;
    v42 = v41 & 0xFFFFFF8F | 0x30;
    v169 = v40;
    v43 = v183;
    v44 = 0x7FFFFFFF;
    v45 = &WindowName;
    do
    {
      if ( !*v45 )
        break;
      ++v45;
      --v44;
    }
    while ( v44 );
    v46 = 2 * (v45 - &WindowName);
    v47 = CoTaskMemAlloc(v46 + 2);
    v49 = v47;
    if ( v47 )
    {
      memcpy_s_0(v47, v46 + 2, &WindowName, v46);
      v49[v46 / 2] = 0;
    }
    v162 = v49;
    v50 = v42 | 0x200;
    fPending[0] = v50;
    if ( !v49 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v48);
    fPending[0] = v50 & 0xFFFFFDFF;
    v51 = v50 & 0xFFFFFCFF | 0x100;
    v52 = 1;
    v53 = &unk_18065B110;
    do
    {
      if ( (v43 & *(_DWORD *)v53) != 0 )
      {
        v54 = &WindowName;
        if ( !v52 )
          v54 = L", ";
        v151 = 0;
        v55 = v51 | 0x400;
        fPending[0] = v55;
        v56 = (wchar_t *)v53[1];
        if ( v56 )
        {
          v57 = -1;
          do
            ++v57;
          while ( v56[v57] );
        }
        else
        {
          v57 = 0;
        }
        v58 = -1;
        do
          ++v58;
        while ( v54[v58] );
        if ( v49 )
        {
          v59 = -1;
          do
            ++v59;
          while ( v49[v59] );
        }
        else
        {
          v59 = 0;
        }
        v188 = 0;
        v189 = 0;
        v190 = v49;
        v191 = v59;
        v192 = v54;
        v193 = v58;
        v194 = v56;
        v195 = v57;
        v60 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v151,
                &v188,
                4);
        if ( v60 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7B3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v60,
            v150);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v162,
          v151);
        v51 = v55 & 0xFFFFFBFF;
        v52 = 0;
        v49 = v162;
      }
      v53 += 2;
    }
    while ( v53 != (_QWORD *)&unk_18065B150 );
    v61 = v51 & 0xFFFFFE7F | 0x80;
    v170 = v49;
    v62 = v182;
    v63 = 0x7FFFFFFF;
    v64 = &WindowName;
    do
    {
      if ( !*v64 )
        break;
      ++v64;
      --v63;
    }
    while ( v63 );
    v65 = 2 * (v64 - &WindowName);
    v66 = CoTaskMemAlloc(v65 + 2);
    v68 = v66;
    if ( v66 )
    {
      memcpy_s_0(v66, v65 + 2, &WindowName, v65);
      v68[v65 / 2] = 0;
    }
    v163 = v68;
    v69 = v61 | 0x2000;
    fPending[0] = v69;
    if ( !v68 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v67);
    fPending[0] = v69 & 0xFFFFDFFF;
    v70 = v69 & 0xFFFFCFFF | 0x1000;
    v71 = 1;
    v72 = (void **)&unk_18065B150;
    do
    {
      if ( (v62 & *(_DWORD *)v72) != 0 )
      {
        v73 = &WindowName;
        if ( !v71 )
          v73 = L", ";
        v151 = 0;
        v74 = v70 | 0x4000;
        fPending[0] = v74;
        v75 = (wchar_t *)v72[1];
        if ( v75 )
        {
          v76 = -1;
          do
            ++v76;
          while ( v75[v76] );
        }
        else
        {
          v76 = 0;
        }
        v77 = -1;
        do
          ++v77;
        while ( v73[v77] );
        if ( v68 )
        {
          v78 = -1;
          do
            ++v78;
          while ( v68[v78] );
        }
        else
        {
          v78 = 0;
        }
        v188 = 0;
        v189 = 0;
        v190 = v68;
        v191 = v78;
        v192 = v73;
        v193 = v77;
        v194 = v75;
        v195 = v76;
        v79 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v151,
                &v188,
                4);
        if ( v79 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7B3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v79,
            v150);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v163,
          v151);
        v70 = v74 & 0xFFFFBFFF;
        v71 = 0;
        v68 = v163;
      }
      v72 += 2;
    }
    while ( v72 != &CEnumFiles::`vftable'{for `IEnumFindDataEx'} );
    v80 = v70 & 0xFFFFE7FF | 0x800;
    v171 = v68;
    LODWORD(v151) = v181[0];
    v81 = 0x7FFFFFFF;
    v82 = &WindowName;
    do
    {
      if ( !*v82 )
        break;
      ++v82;
      --v81;
    }
    while ( v81 );
    v83 = 2 * (v82 - &WindowName);
    v84 = CoTaskMemAlloc(v83 + 2);
    v86 = v84;
    if ( v84 )
    {
      memcpy_s_0(v84, v83 + 2, &WindowName, v83);
      v86[v83 / 2] = 0;
    }
    v164 = v86;
    v87 = v80 | 0x20000;
    fPending[0] = v87;
    if ( !v86 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v85);
    fPending[0] = v87 & 0xFFFDFFFF;
    v88 = v87 & 0xFFFCFFFF | 0x10000;
    v89 = 1;
    v90 = (wchar_t **)&unk_18065B230;
    v91 = (int)v151;
    do
    {
      if ( (v91 & *(_DWORD *)v90) != 0 )
      {
        v92 = &WindowName;
        if ( !v89 )
          v92 = L", ";
        v151 = 0;
        v93 = v88 | 0x40000;
        fPending[0] = v93;
        v94 = v90[1];
        if ( v94 )
        {
          v95 = -1;
          do
            ++v95;
          while ( v94[v95] );
        }
        else
        {
          v95 = 0;
        }
        v96 = -1;
        do
          ++v96;
        while ( v92[v96] );
        if ( v86 )
        {
          v97 = -1;
          do
            ++v97;
          while ( v86[v97] );
        }
        else
        {
          v97 = 0;
        }
        v188 = 0;
        v189 = 0;
        v190 = v86;
        v191 = v97;
        v192 = v92;
        v193 = v96;
        v194 = v94;
        v195 = v95;
        v98 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v151,
                &v188,
                4);
        if ( v98 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7B3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v98,
            v150);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v164,
          v151);
        v88 = v93 & 0xFFFBFFFF;
        v89 = 0;
        v86 = v164;
      }
      v90 += 2;
    }
    while ( v90 != &off_18065B380 );
    v99 = v88 & 0xFFFE7FFF | 0x8000;
    v172 = v86;
    v157 = v152;
    v100 = &WindowName;
    v101 = 0x7FFFFFFF;
    do
    {
      if ( !*v100 )
        break;
      ++v100;
      --v101;
    }
    while ( v101 );
    v102 = 2 * (v100 - &WindowName);
    v103 = CoTaskMemAlloc(v102 + 2);
    v105 = v103;
    if ( v103 )
    {
      memcpy_s_0(v103, v102 + 2, &WindowName, v102);
      v105[v102 / 2] = 0;
    }
    v165 = v105;
    v106 = v99 | 0x200000;
    fPending[0] = v106;
    if ( !v105 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v104);
    fPending[0] = v106 & 0xFFDFFFFF;
    v107 = v106 & 0xFFCFFFFF | 0x100000;
    v108 = 1;
    v109 = &unk_18065B060;
    v110 = v152;
    do
    {
      if ( (v110 & *(_DWORD *)v109) != 0 )
      {
        v111 = &WindowName;
        if ( !v108 )
          v111 = L", ";
        v151 = 0;
        v112 = v107 | 0x400000;
        fPending[0] = v112;
        v113 = (wchar_t *)v109[1];
        if ( v113 )
        {
          v114 = -1;
          do
            ++v114;
          while ( v113[v114] );
        }
        else
        {
          v114 = 0;
        }
        v115 = -1;
        do
          ++v115;
        while ( v111[v115] );
        if ( v105 )
        {
          v116 = -1;
          do
            ++v116;
          while ( v105[v116] );
        }
        else
        {
          v116 = 0;
        }
        v188 = 0;
        v189 = 0;
        v190 = v105;
        v191 = v116;
        v192 = v111;
        v193 = v115;
        v194 = v113;
        v195 = v114;
        v117 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                 &v151,
                 &v188,
                 4);
        if ( v117 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7B3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v117,
            v150);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v165,
          v151);
        v107 = v112 & 0xFFBFFFFF;
        v108 = 0;
        v105 = v165;
        v110 = v152;
      }
      v109 += 2;
    }
    while ( v109 != (_QWORD *)&unk_18065B110 );
    v118 = v107 & 0xFFE7FFFF | 0x80000;
    v151 = v105;
    v119 = *(_DWORD *)(a7 + 4);
    v158 = v119;
    v14 = (wchar_t **)&unk_1806D0AA0;
    v120 = (wchar_t **)&unk_1806D0AA0;
    while ( v119 != *(_DWORD *)v120 )
    {
      v120 += 2;
      if ( v120 == off_1806D0BB0 )
      {
        v121 = L"???";
        goto LABEL_155;
      }
    }
    v121 = v120[1];
LABEL_155:
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v160,
      v121,
      -1);
    v123 = v118 | 0x2000000;
    fPending[0] = v123;
    if ( !v160 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v122);
    fPending[0] = v123 & 0xFDFFFFFF;
    v124 = v123 & 0xFC7FFFFF | 0x1800000;
    v173 = v160;
    v159 = a5;
    v125 = (wchar_t **)&unk_1806D0AA0;
    while ( a5 != *(_DWORD *)v125 )
    {
      v125 += 2;
      if ( v125 == off_1806D0BB0 )
      {
        v126 = L"???";
        goto LABEL_161;
      }
    }
    v126 = v125[1];
LABEL_161:
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v167,
      v126,
      -1);
    v128 = v124 | 0x10000000;
    fPending[0] = v128;
    if ( !v167 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v127);
    fPending[0] = v128 & 0xEFFFFFFF;
    v129 = v128 & 0xE3FFFFFF | 0xC000000;
    v174 = v167;
    LODWORD(Context) = v154;
    v130 = (wchar_t **)&unk_1806D0AA0;
    while ( v154 != *(_DWORD *)v130 )
    {
      v130 += 2;
      if ( v130 == off_1806D0BB0 )
      {
        v131 = L"???";
        goto LABEL_167;
      }
    }
    v131 = v130[1];
LABEL_167:
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      v131,
      -1);
    fPending[0] = v129 | 0x80000000;
    if ( !pv )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v133);
    *(_QWORD *)fPending = pv;
    v134 = (unsigned int)v155;
    if ( (_DWORD)v155 )
    {
      switch ( (_DWORD)v155 )
      {
        case 1:
          v135 = L"Extrinsic Store ";
          break;
        case 2:
          v135 = L"SyncEngine ";
          break;
        case 3:
          v135 = L"Folder Enumerated ";
          break;
        case 4:
          v135 = L"Calculated ";
          break;
        default:
          v135 = L"???";
          break;
      }
    }
    else
    {
      v135 = L"Indexer ";
    }
    v155 = v135;
    v175 = a9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperPtrSize>(
      (_DWORD)v176,
      (unsigned int)&unk_180764856,
      v132,
      (_DWORD)v133,
      (__int64)&v175,
      (__int64)&v156,
      (__int64)&v155,
      (__int64)fPending,
      (__int64)&Context,
      (__int64)&v174,
      (__int64)&v159,
      (__int64)&v173,
      (__int64)&v158,
      (__int64)&v151,
      (__int64)&v157,
      (__int64)&v172,
      (__int64)&v171,
      (__int64)&v170,
      (__int64)&v169,
      (__int64)&v168,
      (__int64)&v187);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v167 )
      CoTaskMemFree(v167);
    if ( v160 )
      CoTaskMemFree(v160);
    if ( v105 )
      CoTaskMemFree(v105);
    if ( v86 )
      CoTaskMemFree(v86);
    if ( v68 )
      CoTaskMemFree(v68);
    if ( v49 )
      CoTaskMemFree(v49);
    CoTaskMemFree(v177);
    if ( v22 )
      CoTaskMemFree(v22);
    v9 = v154;
    v15 = L"???";
    v10 = v153;
  }
  PrimaryStateReasonString = GetPrimaryStateReasonString(v134);
  v137 = (wchar_t **)&unk_1806D0AA0;
  while ( v9 != *(_DWORD *)v137 )
  {
    v137 += 2;
    if ( v137 == off_1806D0BB0 )
    {
      v138 = L"???";
      goto LABEL_202;
    }
  }
  v138 = v137[1];
LABEL_202:
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v153,
    v138,
    -1);
  fPending[0] = 4;
  if ( !v153 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xFF8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v139);
  v140 = 3;
  StateLog(L"State(%s) %s : %s", v153, PrimaryStateReasonString, v178);
  if ( v153 )
    CoTaskMemFree(v153);
  v142 = v152;
  if ( a5 != 16 || v152 )
  {
    v143 = (wchar_t **)&unk_1806D0AA0;
    while ( a5 != *(_DWORD *)v143 )
    {
      v143 += 2;
      if ( v143 == off_1806D0BB0 )
      {
        v144 = L"???";
        goto LABEL_212;
      }
    }
    v144 = v143[1];
LABEL_212:
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v153,
      v144,
      -1);
    fPending[0] = 35;
    if ( !v153 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v145);
    v140 = 27;
    StateLog(L"---- Indexer(%s) Status: %08X", v153, v142);
    if ( v153 )
      CoTaskMemFree(v153);
  }
  v146 = (struct SyncItemStateData *)a7;
  v147 = *(_DWORD *)(a7 + 4);
  if ( v147 != 16 || *(_BYTE *)(a7 + 3) )
  {
    v148 = L"yes";
    if ( !*(_BYTE *)(a7 + 3) )
      v148 = L"no";
    while ( v147 != *(_DWORD *)v14 )
    {
      v14 += 2;
      if ( v14 == off_1806D0BB0 )
        goto LABEL_223;
    }
    v15 = v14[1];
LABEL_223:
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v153,
      v15,
      -1);
    fPending[0] = v140 | 0x100;
    if ( !v153 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v149);
    StateLog(L"---- Enumeration(%s) Complete: %s", v153, v148);
    v146 = v153;
    if ( v153 )
      CoTaskMemFree(v153);
  }
  if ( *((_DWORD *)v10 + 4) != 16 )
    LogSyncItemStateData((const unsigned __int16 *)v146, v10, v141);
}

```

## disassembly

```asm
0x18021a0b0  mov     [rsp-8+arg_0], rbx
0x18021a0b5  push    rbp
0x18021a0b6  push    rsi
0x18021a0b7  push    rdi
0x18021a0b8  push    r12
0x18021a0ba  push    r13
0x18021a0bc  push    r14
0x18021a0be  push    r15
0x18021a0c0  lea     rbp, [rsp-0F0h]
0x18021a0c8  sub     rsp, 220h
0x18021a0cf  mov     rax, cs:__security_cookie
0x18021a0d6  xor     rax, rsp
0x18021a0d9  mov     [rbp+120h+var_40], rax
0x18021a0e0  mov     esi, r9d
0x18021a0e3  mov     [rbp+120h+var_188], r9d
0x18021a0e7  mov     dword ptr [rbp+120h+var_180], r8d
0x18021a0eb  mov     [rbp+120h+var_D0], rdx
0x18021a0ef  mov     r15, [rbp+120h+arg_38]
0x18021a0f6  mov     [rbp+120h+var_190], r15
0x18021a0fa  mov     eax, [rbp+120h+arg_28]
0x18021a100  mov     [rbp+120h+var_198], eax
0x18021a103  xor     r13d, r13d
0x18021a106  mov     [rbp+120h+fPending], r13d
0x18021a10d  mov     [rbp+120h+fPending], r13d
0x18021a114  mov     ebx, [r15]
0x18021a117  mov     [rbp+120h+var_B8], ebx
0x18021a11a  mov     eax, [r15+4]
0x18021a11e  mov     [rbp+120h+var_B4], eax
0x18021a121  mov     eax, [r15+8]
0x18021a125  mov     [rbp+120h+var_B0], eax
0x18021a128  mov     eax, [r15+0Ch]
0x18021a12c  mov     [rbp+120h+var_AC], eax
0x18021a12f  mov     eax, [r15+10h]
0x18021a133  mov     [rbp+120h+var_A8], eax
0x18021a136  mov     eax, [r15+14h]
0x18021a13a  mov     [rbp+120h+var_A4], eax
0x18021a13d  mov     rcx, rdx; pszPath
0x18021a140  call    cs:__imp_PathFindExtensionW
0x18021a146  mov     [rbp+120h+var_178], rax
0x18021a14a  test    bl, 10h
0x18021a14d  jnz     short loc_18021A15A
0x18021a14f  test    rax, rax
0x18021a152  jz      short loc_18021A15A
0x18021a154  cmp     [rax], r13w
0x18021a158  jnz     short loc_18021A165
0x18021a15a  lea     rax, aFolder; "Folder"
0x18021a161  mov     [rbp+120h+var_178], rax
0x18021a165  mov     [rbp+120h+Context], r13
0x18021a169  mov     [rbp+120h+fPending], r13d
0x18021a170  lea     r9, [rbp+120h+Context]; lpContext
0x18021a174  lea     r8, [rbp+120h+fPending]; fPending
0x18021a17b  xor     edx, edx; dwFlags
0x18021a17d  lea     rcx, ?wrapper@?1??Instance@CloudFileProvider@@KAPEAV2@XZ@4V?$static_lazy@VCloudFileProvider@@@details@wil@@A; lpInitOnce
0x18021a184  call    cs:__imp_InitOnceBeginInitialize
0x18021a18a  mov     r12d, 2
0x18021a190  test    eax, eax
0x18021a192  jz      loc_18021A289
0x18021a198  cmp     [rbp+120h+fPending], r13d
0x18021a19f  jz      loc_18021A289
0x18021a1a5  lea     r14, qword_180805E08
0x18021a1ac  mov     [rbp+120h+Context], r14
0x18021a1b0  mov     cs:qword_180805E10, r13
0x18021a1b7  mov     cs:byte_180805E18, r13b
0x18021a1be  mov     cs:dword_180805E1C, r13d
0x18021a1c5  lea     rax, ??_7ShellEdpLogging@@6B@; const ShellEdpLogging::`vftable'
0x18021a1cc  mov     cs:qword_180805E08, rax
0x18021a1d3  lea     rax, ?__hInner@?1???0StaticHandle@CloudFileProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CloudFileProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18021a1da  mov     cs:qword_180805E20, rax
0x18021a1e1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_eaf6c2cdbe1fd0eabf0c712e7f531564_@@CA@XZ; void (__cdecl *)()
0x18021a1e8  call    atexit
0x18021a1ed  mov     rbx, cs:qword_180805E20
0x18021a1f4  mov     cs:qword_180805E10, rbx
0x18021a1fb  mov     cs:byte_180805E18, 1
0x18021a202  mov     rax, [rbx+8]
0x18021a206  movups  xmm0, xmmword ptr [rax-10h]
0x18021a20a  movups  [rbp+120h+var_98], xmm0
0x18021a211  cmp     [rbx+20h], r13
0x18021a215  jz      short loc_18021A21E
0x18021a217  mov     ecx, 5
0x18021a21c  int     29h; Win8: RtlFailFast(ecx)
0x18021a21e  mov     [rbx+28h], r13
0x18021a222  mov     [rbx+30h], r13
0x18021a226  lea     r9, [rbx+20h]
0x18021a22a  mov     r8, rbx
0x18021a22d  lea     rdx, _tlgEnableCallback
0x18021a234  lea     rcx, [rbp+120h+var_98]
0x18021a23b  call    cs:__imp_EtwEventRegister
0x18021a241  test    eax, eax
0x18021a243  jnz     short loc_18021A25A
0x18021a245  mov     r8, [rbx+8]
0x18021a249  movzx   r9d, word ptr [r8]
0x18021a24d  mov     edx, r12d
0x18021a250  mov     rcx, [rbx+20h]
0x18021a254  call    cs:__imp_EtwEventSetInformation
0x18021a25a  mov     cs:dword_180805E1C, 1
0x18021a264  mov     rax, cs:qword_180805E08
0x18021a26b  mov     rcx, r14
0x18021a26e  mov     rax, [rax+8]
0x18021a272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021a277  mov     r8, r14; lpContext
0x18021a27a  xor     edx, edx; dwFlags
0x18021a27c  lea     rcx, ?wrapper@?1??Instance@CloudFileProvider@@KAPEAV2@XZ@4V?$static_lazy@VCloudFileProvider@@@details@wil@@A; lpInitOnce
0x18021a283  call    cs:__imp_InitOnceComplete
0x18021a289  mov     rax, [rbp+120h+Context]
0x18021a28d  mov     rax, [rax+8]
0x18021a291  mov     [rbp+120h+var_E0], rax
0x18021a295  mov     eax, [rax]
0x18021a297  lea     r13, unk_1806D0AA0
0x18021a29e  lea     r14, asc_180736030; "???"
0x18021a2a5  cmp     eax, 5
0x18021a2a8  jbe     loc_18021AF87
0x18021a2ae  lea     rax, [rbp+120h+var_B8]
0x18021a2b2  mov     qword ptr [rbp+120h+var_98], rax
0x18021a2b9  mov     dword ptr [rbp+120h+var_98+8], 18h
0x18021a2c3  mov     esi, [rbp+120h+var_A4]
0x18021a2c6  mov     r14d, 7FFFFFFFh
0x18021a2cc  mov     ecx, r14d
0x18021a2cf  lea     rdx, WindowName
0x18021a2d6  mov     rax, rdx
0x18021a2d9  nop     dword ptr [rax+00000000h]
0x18021a2e0  cmp     word ptr [rax], 0
0x18021a2e4  jz      short loc_18021A2F0
0x18021a2e6  add     rax, 2
0x18021a2ea  sub     rcx, 1
0x18021a2ee  jnz     short loc_18021A2E0
0x18021a2f0  sub     rax, rdx
0x18021a2f3  sar     rax, 1
0x18021a2f6  lea     rbx, [rax+rax]
0x18021a2fa  lea     rcx, [rbx+2]; cb
0x18021a2fe  call    cs:__imp_CoTaskMemAlloc
0x18021a304  mov     r15, rax
0x18021a307  test    rax, rax
0x18021a30a  jz      short loc_18021A32C
0x18021a30c  mov     r9, rbx; SourceSize
0x18021a30f  lea     r8, WindowName; Source
0x18021a316  lea     rdx, [rbx+2]; DestinationSize
0x18021a31a  mov     rcx, rax; Destination
0x18021a31d  call    memcpy_s_0
0x18021a322  xor     r10d, r10d
0x18021a325  mov     [rbx+r15], r10w
0x18021a32a  jmp     short loc_18021A32F
0x18021a32c  xor     r10d, r10d
0x18021a32f  mov     [rbp+120h+var_158], r15
0x18021a333  mov     [rbp+120h+fPending], 4
0x18021a33d  mov     rcx, [rbp+128h]; this
0x18021a344  test    r15, r15
0x18021a347  jz      loc_18021B27E
0x18021a34d  mov     al, 1
0x18021a34f  lea     rbx, unk_180681400
0x18021a356  lea     rcx, asc_1806EF4D4; ", "
0x18021a35d  lea     rdi, ?qit@?1??QueryInterface@CImageManager@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CImageManager::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x18021a364  test    [rbx], esi
0x18021a366  jz      loc_18021A46B
0x18021a36c  lea     r8, WindowName
0x18021a373  test    al, al
0x18021a375  cmovz   r8, rcx
0x18021a379  mov     [rbp+120h+var_1A0], r10
0x18021a37d  or      r12d, 8
0x18021a381  mov     [rbp+120h+fPending], r12d
0x18021a388  mov     r9, [rbx+8]
0x18021a38c  test    r9, r9
0x18021a38f  jz      short loc_18021A3AD
0x18021a391  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18021a398  nop     dword ptr [rax+rax+00000000h]
0x18021a3a0  inc     rcx
0x18021a3a3  cmp     word ptr [r9+rcx*2], 0
0x18021a3a9  jnz     short loc_18021A3A0
0x18021a3ab  jmp     short loc_18021A3B0
0x18021a3ad  mov     rcx, r10
0x18021a3b0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18021a3b7  nop     word ptr [rax+rax+00000000h]
0x18021a3c0  inc     rdx
0x18021a3c3  cmp     word ptr [r8+rdx*2], 0
0x18021a3c9  jnz     short loc_18021A3C0
0x18021a3cb  test    r15, r15
0x18021a3ce  jz      short loc_18021A3ED
0x18021a3d0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18021a3d7  nop     word ptr [rax+rax+00000000h]
0x18021a3e0  inc     rax
0x18021a3e3  cmp     word ptr [r15+rax*2], 0
0x18021a3e9  jnz     short loc_18021A3E0
0x18021a3eb  jmp     short loc_18021A3F0
0x18021a3ed  mov     rax, r10
0x18021a3f0  mov     [rbp+120h+var_80], r10
0x18021a3f7  mov     [rbp+120h+var_78], r10
0x18021a3fe  mov     [rbp+120h+var_70], r15
0x18021a405  mov     [rbp+120h+var_68], rax
0x18021a40c  mov     [rbp+120h+var_60], r8
0x18021a413  mov     [rbp+120h+var_58], rdx
0x18021a41a  mov     [rbp+120h+var_50], r9
0x18021a421  mov     [rbp+120h+var_48], rcx
0x18021a428  mov     r8d, 4
0x18021a42e  lea     rdx, [rbp+120h+var_80]
0x18021a435  lea     rcx, [rbp+120h+var_1A0]
0x18021a439  call    ??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z; wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)
0x18021a43e  mov     rcx, [rbp+128h]; this
0x18021a445  test    eax, eax
0x18021a447  js      loc_18021B173
0x18021a44d  mov     rdx, [rbp+120h+var_1A0]
0x18021a451  lea     rcx, [rbp+120h+var_158]
0x18021a455  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18021a45a  and     r12d, 0FFFFFFF7h
0x18021a45e  xor     al, al
0x18021a460  mov     r15, [rbp+120h+var_158]
0x18021a464  lea     rcx, asc_1806EF4D4; ", "
0x18021a46b  add     rbx, 10h
0x18021a46f  cmp     rbx, rdi
0x18021a472  jz      short loc_18021A47C
0x18021a474  xor     r10d, r10d
0x18021a477  jmp     loc_18021A364
0x18021a47c  and     r12d, 0FFFFFFFDh
0x18021a480  or      r12d, 1
0x18021a484  mov     [rbp+120h+var_120], r15
0x18021a488  mov     ecx, [rbp+120h+var_A8]
0x18021a48b  mov     rax, r13
0x18021a48e  lea     rdx, off_1806D0BB0; "Windows.System.AppInitiatedDownload"
0x18021a495  cmp     ecx, [rax]
0x18021a497  jz      short loc_18021A4AB
0x18021a499  add     rax, 10h
0x18021a49d  cmp     rax, rdx
0x18021a4a0  jnz     short loc_18021A495
0x18021a4a2  lea     rbx, asc_180736030; "???"
0x18021a4a9  jmp     short loc_18021A4AF
0x18021a4ab  mov     rbx, [rax+8]
0x18021a4af  mov     rcx, [rbp+128h]; this
0x18021a4b6  test    rbx, rbx
0x18021a4b9  jz      loc_18021B188
0x18021a4bf  mov     rcx, r14
0x18021a4c2  mov     rax, rbx
0x18021a4c5  cmp     word ptr [rax], 0
0x18021a4c9  jz      short loc_18021A4D5
0x18021a4cb  add     rax, 2
0x18021a4cf  sub     rcx, 1
0x18021a4d3  jnz     short loc_18021A4C5
0x18021a4d5  sub     rax, rbx
0x18021a4d8  sar     rax, 1
0x18021a4db  lea     rdi, [rax+rax]
0x18021a4df  lea     rcx, [rdi+2]; cb
0x18021a4e3  call    cs:__imp_CoTaskMemAlloc
0x18021a4e9  mov     r13, rax
0x18021a4ec  mov     [rbp+120h+var_D8], rax
0x18021a4f0  test    rax, rax
0x18021a4f3  jz      short loc_18021A50E
0x18021a4f5  mov     r9, rdi; SourceSize
0x18021a4f8  mov     r8, rbx; Source
0x18021a4fb  lea     rdx, [rdi+2]; DestinationSize
0x18021a4ff  mov     rcx, rax; Destination
0x18021a502  call    memcpy_s_0
0x18021a507  xor     ecx, ecx
0x18021a509  mov     [rdi+r13], cx
0x18021a50e  mov     [rbp+120h+var_C8], r13
0x18021a512  or      r12d, 40h
0x18021a516  mov     [rbp+120h+fPending], r12d
0x18021a51d  mov     rcx, [rbp+128h]; this
0x18021a524  test    r13, r13
0x18021a527  jz      loc_18021B26C
0x18021a52d  and     r12d, 0FFFFFFBFh
0x18021a531  mov     [rbp+120h+fPending], r12d
0x18021a538  or      r12d, 30h
0x18021a53c  mov     [rbp+120h+var_118], r13
0x18021a540  mov     esi, [rbp+120h+var_AC]
0x18021a543  mov     rcx, r14
0x18021a546  lea     r13, WindowName
0x18021a54d  mov     rax, r13
0x18021a550  cmp     word ptr [rax], 0
0x18021a554  jz      short loc_18021A560
0x18021a556  add     rax, 2
0x18021a55a  sub     rcx, 1
0x18021a55e  jnz     short loc_18021A550
0x18021a560  sub     rax, r13
0x18021a563  sar     rax, 1
0x18021a566  lea     rbx, [rax+rax]
0x18021a56a  lea     rcx, [rbx+2]; cb
0x18021a56e  call    cs:__imp_CoTaskMemAlloc
0x18021a574  mov     r14, rax
0x18021a577  test    rax, rax
0x18021a57a  jz      short loc_18021A598
0x18021a57c  mov     r9, rbx; SourceSize
0x18021a57f  mov     r8, r13; Source
0x18021a582  lea     rdx, [rbx+2]; DestinationSize
0x18021a586  mov     rcx, rax; Destination
0x18021a589  call    memcpy_s_0
0x18021a58e  xor     r10d, r10d
0x18021a591  mov     [rbx+r14], r10w
0x18021a596  jmp     short loc_18021A59B
0x18021a598  xor     r10d, r10d
0x18021a59b  mov     [rbp+120h+var_150], r14
0x18021a59f  bts     r12d, 9
0x18021a5a4  mov     [rbp+120h+fPending], r12d
0x18021a5ab  mov     rcx, [rbp+128h]; this
0x18021a5b2  test    r14, r14
0x18021a5b5  jz      loc_18021B25A
0x18021a5bb  btr     r12d, 9
0x18021a5c0  mov     [rbp+120h+fPending], r12d
0x18021a5c7  bts     r12d, 8
0x18021a5cc  mov     al, 1
0x18021a5ce  lea     rbx, unk_18065B110
0x18021a5d5  lea     rdi, unk_18065B150
0x18021a5dc  nop     dword ptr [rax+00h]
0x18021a5e0  test    [rbx], esi
  ... truncated ...
```
