# Windows::UXNotifications::RebootSystemWithUx(bool,bool,Monitor<std::pair<bool,bool>> &,std::shared_ptr<SystemInterface::Telemetry::CorrelationVector>,bool)

- ea: `0x1402a3ca0`
- end: `0x1402a554d`
- name: `?RebootSystemWithUx@UXNotifications@Windows@@UEAAI_N0AEAV?$Monitor@U?$pair@_N_N@std@@@@V?$shared_ptr@VCorrelationVector@Telemetry@SystemInterface@@@std@@0@Z`
- size: `6317`
- prototype: `__int64 __fastcall(int, int, int, int, void *, char)`
- caller_count: `0`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140021190`
- `0x140024de0`
- `0x1400288b0`
- `0x140029f9c`
- `0x14002b6ec`
- `0x14002f218`
- `0x14003c578`
- `0x140040184`
- `0x14004081c`
- `0x140041338`
- `0x1400413a8`
- `0x140043284`
- `0x1400447ac`
- `0x140044b18`
- `0x140045184`
- `0x140045404`
- `0x140057a20`
- `0x1400a6954`
- `0x1400aab3c`
- `0x1400e78cc`
- `0x1400eb300`
- `0x14012d7d8`
- `0x14012d864`
- `0x14018b170`
- `0x1401cf0f4`
- `0x1401cf43c`
- `0x1401cf6d0`
- `0x1401cf738`
- `0x1401d0ad0`
- `0x1401d0b48`
- `0x1401d3fb0`
- `0x140202bc8`
- `0x14024898c`
- `0x140268574`
- `0x140268890`
- `0x1402a3ca0`
- `0x1402aafd4`
- `0x140373ec0`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1402a4a8b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1402a4a8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1402a42e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1402a42e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402a42cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402a434f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402a42cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402a434f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a3e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a47a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a4c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a51c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a5279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a3e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a47a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a4c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a51c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402a5279`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1402a433d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1402a433d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1402a441a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1402a441a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1402a45a4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1402a4e96`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1402a45a4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1402a4e96`

## string_xrefs

- `0x1402a53cb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402a53e5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402a53ab`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402a53ff`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402a5419`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402a4afc`: `UsoSession: Reboot with blocking apps UX completed`
- `0x1402a54bd`: `Reboot with blocking apps could not complete due to UX process launch timeout`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall Windows::UXNotifications::RebootSystemWithUx(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        _QWORD *a5,
        char a6)
{
  __int64 v6; // r13
  _QWORD *v7; // r12
  _QWORD *System; // rax
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rbx
  char *v13; // rbx
  HANDLE *MostPreferredLoggedOnSessionTokenAndTryElevate; // rax
  _QWORD *v15; // rax
  __int64 (__fastcall *v16)(__int64, _OWORD *, __int128 *); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v18; // r9
  __int64 v19; // r11
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // r8
  volatile signed __int32 *v23; // rbx
  volatile signed __int32 *v24; // rbx
  _QWORD *v25; // rax
  _QWORD *v26; // rbx
  const wchar_t *v27; // r15
  const wchar_t *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  int v36; // esi
  WCHAR *v37; // rbx
  WCHAR *v38; // rax
  LPHANDLE v39; // rax
  struct _PROCESS_INFORMATION *v40; // rdx
  __int128 v41; // xmm7
  HANDLE v42; // xmm6_8
  DWORD LastError; // ebx
  struct _PROCESS_INFORMATION *v44; // rdx
  HANDLE Event; // rax
  wil *v46; // rcx
  const char *v47; // r9
  HANDLE v48; // rbx
  const char *v49; // r9
  __int64 v50; // rdx
  HANDLE v51; // rax
  const char *v52; // r9
  const char *v53; // r9
  signed __int64 v54; // rbx
  __int64 v55; // rax
  void *v56; // rcx
  HANDLE *v57; // rdx
  HANDLE *v58; // rcx
  const char *v59; // r9
  unsigned __int64 v60; // r13
  void (__fastcall *v61)(__int64, HANDLE *, __int128 *, __int64); // rbx
  __int64 v62; // rax
  __int16 *v63; // rax
  const char *v64; // r9
  __int64 v65; // r11
  __int64 v66; // rax
  volatile signed __int32 *v67; // rbx
  struct _PROCESS_INFORMATION *v68; // rdx
  __int64 v69; // rcx
  void (__fastcall ***v70)(_QWORD, __int64); // r8
  volatile signed __int32 *v71; // rbx
  volatile signed __int32 *v72; // rbx
  volatile signed __int32 *v73; // rbx
  volatile signed __int32 *v74; // rbx
  volatile signed __int32 *v75; // rbx
  void (__fastcall *v77)(__int64, HANDLE *, __int128 *, __int64); // rbx
  __int64 v78; // rax
  __int64 *v79; // rax
  const char *v80; // r9
  __int64 v81; // r11
  __int64 v82; // rax
  __int64 v83; // rsi
  volatile signed __int32 *v84; // rbx
  struct _PROCESS_INFORMATION *v85; // rdx
  __int64 v86; // rcx
  void (__fastcall ***v87)(_QWORD, __int64); // r8
  const char *v88; // r9
  __int64 v89; // rbx
  void (__fastcall *v90)(__int64, HANDLE *, __int128 *, __int64); // rsi
  __int64 v91; // rax
  _OWORD *v92; // rax
  __int64 v93; // rbx
  void (__fastcall *v94)(__int64, HANDLE *, __int128 *, __int64); // rdi
  __int64 v95; // rax
  struct _PROCESS_INFORMATION *v96; // rdx
  unsigned int v97; // ebx
  _QWORD *v98; // rax
  int v99; // esi
  char v100; // al
  __int64 v101; // rcx
  char v102; // bl
  __int64 v103; // rbx
  void (__fastcall *v104)(__int64, HANDLE *, __int128 *, __int64); // rsi
  __int64 v105; // rax
  __int64 v106; // rdx
  const wchar_t *v107; // r13
  __int64 v108; // rax
  void *v109; // rax
  __int64 v110; // rbx
  void (__fastcall *v111)(__int64, HANDLE *, __int128 *, __int64); // rdi
  __int64 v112; // rax
  signed __int64 v113; // rcx
  DWORD v114; // eax
  __int64 v115; // rbx
  void (__fastcall *v116)(__int64, HANDLE *, __int128 *, __int64); // rdi
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rbx
  void (__fastcall *v121)(__int64, __int128 *, __int128 *, __int64); // r13
  __int64 v122; // rax
  __int64 v123; // rcx
  void (__fastcall ***v124)(_QWORD, __int64); // r8
  struct _PROCESS_INFORMATION *v125; // rdx
  volatile signed __int32 *v126; // rbx
  volatile signed __int32 *v127; // rbx
  volatile signed __int32 *v128; // rbx
  volatile signed __int32 *v129; // rbx
  volatile signed __int32 *v130; // rbx
  unsigned int v131; // eax
  __int64 v132; // rsi
  void (__fastcall *v133)(__int64, HANDLE *, __int64, __int64); // rdi
  __int64 v134; // rbx
  __int64 v135; // rax
  __int64 v136; // rcx
  unsigned int v137; // eax
  __int64 v138; // rsi
  void (__fastcall *v139)(__int64, __int128 *, __int64, __int64); // rdi
  __int64 v140; // rbx
  __int64 v141; // rax
  unsigned int v142; // [rsp+20h] [rbp-2B8h]
  __int128 v143; // [rsp+40h] [rbp-298h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-288h] BYREF
  char v145; // [rsp+60h] [rbp-278h]
  HANDLE v146; // [rsp+68h] [rbp-270h] BYREF
  _BYTE v147[16]; // [rsp+70h] [rbp-268h] BYREF
  __int128 v148; // [rsp+80h] [rbp-258h] BYREF
  __int128 v149; // [rsp+90h] [rbp-248h] BYREF
  __int128 v150; // [rsp+A0h] [rbp-238h] BYREF
  __int128 v151; // [rsp+B0h] [rbp-228h]
  _QWORD v152[7]; // [rsp+C0h] [rbp-218h] BYREF
  _QWORD *v153; // [rsp+F8h] [rbp-1E0h]
  HANDLE hProcess[2]; // [rsp+100h] [rbp-1D8h] BYREF
  HANDLE v155; // [rsp+110h] [rbp-1C8h]
  _QWORD *v156; // [rsp+118h] [rbp-1C0h]
  HANDLE TargetHandle[3]; // [rsp+120h] [rbp-1B8h] BYREF
  __int128 v158; // [rsp+138h] [rbp-1A0h] BYREF
  __int128 v159; // [rsp+148h] [rbp-190h]
  __int128 v160; // [rsp+158h] [rbp-180h] BYREF
  __int128 v161; // [rsp+168h] [rbp-170h]
  _BYTE v162[32]; // [rsp+178h] [rbp-160h] BYREF
  _BYTE v163[32]; // [rsp+198h] [rbp-140h] BYREF
  _BYTE v164[32]; // [rsp+1B8h] [rbp-120h] BYREF
  DWORD ExitCode[2]; // [rsp+1D8h] [rbp-100h] BYREF
  HANDLE *lpHandles[2]; // [rsp+1E0h] [rbp-F8h] BYREF
  HANDLE *v167; // [rsp+1F0h] [rbp-E8h]
  __int128 v168; // [rsp+1F8h] [rbp-E0h] BYREF
  __int128 v169; // [rsp+208h] [rbp-D0h] BYREF
  __int128 v170; // [rsp+218h] [rbp-C0h] BYREF
  __int128 v171; // [rsp+228h] [rbp-B0h] BYREF
  __int64 v172[2]; // [rsp+238h] [rbp-A0h]
  __int128 v173; // [rsp+248h] [rbp-90h] BYREF
  _OWORD v174[2]; // [rsp+258h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v6 = a4;
  *(_QWORD *)&v148 = a4;
  v147[0] = a3;
  v145 = a2;
  *(_QWORD *)ExitCode = a4;
  v7 = a5;
  v156 = a5;
  LODWORD(hObject[0]) = 0;
  v168 = 0;
  System = (_QWORD *)SystemInterface::Providers::GetSystem(&v150);
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*System + 56LL))(*System, &v168);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v150 + 1);
  if ( *((_QWORD *)&v150 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v150 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v170 = 0;
  v10 = SystemInterface::Providers::GetSystem(&v169);
  v11 = *(_QWORD *)v10 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 4LL);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 80LL))(v11, &v170);
  v12 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
  if ( *((_QWORD *)&v169 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v173 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a5 + 32LL))(*a5, &v173);
  v13 = 0;
  v146 = 0;
  if ( a6 )
    MostPreferredLoggedOnSessionTokenAndTryElevate = (HANDLE *)Windows::CallerToken::GetMostPreferredLoggedOnSessionTokenAndTryElevate(hObject);
  else
    MostPreferredLoggedOnSessionTokenAndTryElevate = (HANDLE *)Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(hObject);
  if ( &v146 != MostPreferredLoggedOnSessionTokenAndTryElevate )
  {
    v13 = (char *)*MostPreferredLoggedOnSessionTokenAndTryElevate;
    v146 = *MostPreferredLoggedOnSessionTokenAndTryElevate;
    *MostPreferredLoggedOnSessionTokenAndTryElevate = 0;
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( ((unsigned __int64)(v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)v170 + 64LL))(v170, v6, 0);
LABEL_193:
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v13);
    v127 = (volatile signed __int32 *)*((_QWORD *)&v173 + 1);
    if ( *((_QWORD *)&v173 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v173 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v127)(v127);
        if ( _InterlockedExchangeAdd(v127 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v127 + 8LL))(v127);
      }
    }
    v128 = (volatile signed __int32 *)*((_QWORD *)&v170 + 1);
    if ( *((_QWORD *)&v170 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v128)(v128);
        if ( _InterlockedExchangeAdd(v128 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v128 + 8LL))(v128);
      }
    }
    v129 = (volatile signed __int32 *)*((_QWORD *)&v168 + 1);
    if ( *((_QWORD *)&v168 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v168 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v129)(v129);
        if ( _InterlockedExchangeAdd(v129 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v129 + 8LL))(v129);
      }
    }
    v130 = (volatile signed __int32 *)v7[1];
    if ( v130 && _InterlockedExchangeAdd(v130 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v130)(v130);
      if ( _InterlockedExchangeAdd(v130 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v130 + 8LL))(v130);
    }
    return 0;
  }
  *(_OWORD *)hProcess = 0;
  v155 = 0;
  try
  {
    v15 = (_QWORD *)SystemInterface::Service::GetSystem(&v149);
    v16 = *(__int64 (__fastcall **)(__int64, _OWORD *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v15 + 8LL))(
                                                                                   *v15,
                                                                                   &v143)
                                                                  + 48LL);
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"RebootSystemWithUx",
                                           &word_140475226,
                                           0);
    if ( traits_2_unsigned_short == &word_140475226
      || (v20 = ((char *)traits_2_unsigned_short - (char *)L"RebootSystemWithUx") >> 1, v20 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v18);
    }
    *(_QWORD *)&v150 = L"RebootSystemWithUx";
    *((_QWORD *)&v150 + 1) = v20;
    v21 = (_QWORD *)v16(v19, v174, &v150);
    if ( v21[3] > 7u )
      v21 = (_QWORD *)*v21;
    v171 = 0;
    *(_OWORD *)v172 = 0;
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    std::wstring::_Construct<1,wchar_t const *>(&v171, v21, v22);
    std::wstring::~wstring(v174);
    v23 = (volatile signed __int32 *)*((_QWORD *)&v143 + 1);
    if ( *((_QWORD *)&v143 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v143 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v24 = (volatile signed __int32 *)*((_QWORD *)&v149 + 1);
    if ( *((_QWORD *)&v149 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v149 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v25 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v173 + 16LL))(v173, v163);
    v26 = v25;
    if ( v25[3] > 7u )
      v26 = (_QWORD *)*v25;
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v172[0]) < 8 )
      std::_Xlen_string();
    std::wstring::wstring(v162, v172[0], L" /Reboot", 8);
    v27 = &psz;
    v28 = &psz;
    if ( v145 )
      v28 = L" /ForceOthers";
    v29 = -1;
    do
      ++v29;
    while ( v28[v29] );
    v30 = std::wstring::append(v162);
    v160 = 0;
    v161 = 0;
    v160 = *(_OWORD *)v30;
    v161 = *(_OWORD *)(v30 + 16);
    *(_WORD *)v30 = 0;
    *(_QWORD *)(v30 + 16) = 0;
    *(_QWORD *)(v30 + 24) = 7;
    if ( v147[0] )
      v27 = L" /ReduceDisruption";
    v31 = -1;
    do
      ++v31;
    while ( v27[v31] );
    v32 = std::wstring::append(&v160);
    v158 = 0;
    v159 = 0;
    v158 = *(_OWORD *)v32;
    v159 = *(_OWORD *)(v32 + 16);
    *(_WORD *)v32 = 0;
    *(_QWORD *)(v32 + 16) = 0;
    *(_QWORD *)(v32 + 24) = 7;
    v33 = std::wstring::append(&v158);
    v150 = 0;
    v151 = 0;
    v150 = *(_OWORD *)v33;
    v151 = *(_OWORD *)(v33 + 16);
    *(_WORD *)v33 = 0;
    *(_QWORD *)(v33 + 16) = 0;
    *(_QWORD *)(v33 + 24) = 7;
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v26 + v34) );
    v35 = std::wstring::append(&v150);
    v174[0] = *(_OWORD *)v35;
    v174[1] = *(_OWORD *)(v35 + 16);
    *(_WORD *)v35 = 0;
    *(_QWORD *)(v35 + 16) = 0;
    *(_QWORD *)(v35 + 24) = 7;
    v36 = 62;
    LODWORD(hObject[0]) = 62;
    std::wstring::~wstring(&v150);
    std::wstring::~wstring(&v158);
    std::wstring::~wstring(&v160);
    std::wstring::~wstring(v162);
    std::wstring::~wstring(v163);
    *(_QWORD *)&v149 = v164;
    v37 = (WCHAR *)std::wstring::wstring(v164, v174);
    v38 = (WCHAR *)std::wstring::wstring(v152, &v171);
    v39 = Windows::ProcessHelpers::CreateProcessAsUserToken(TargetHandle, &v146, v38, v37);
    if ( hProcess != v39 )
    {
      v41 = *(_OWORD *)v39;
      v42 = v39[2];
      *(_OWORD *)v39 = 0;
      v39[2] = 0;
      LastError = GetLastError();
      wil::details::CloseProcessInformation((wil::details *)hProcess, v44);
      SetLastError(LastError);
      *(_OWORD *)hProcess = v41;
      v155 = v42;
    }
    wil::details::CloseProcessInformation((wil::details *)TargetHandle, v40);
    std::wstring::~wstring(v174);
    std::wstring::~wstring(&v171);
    v169 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  }
  catch ( ... )
  {
    if ( (unsigned int)wil::ResultFromCaughtException(v46) == -2147024894 )
    {
      v138 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(&v168);
      v139 = *(void (__fastcall **)(__int64, __int128 *, __int64, __int64))(*(_QWORD *)v138 + 104LL);
      v140 = std::shared_ptr<Update>::shared_ptr<Update>(&v171, v156);
      v150 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                          TargetHandle,
                          L"MusNotificationUx not found");
      v139(v138, &v150, v140, 1);
      v141 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(&v170);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v141 + 64LL))(v141, *(_QWORD *)ExitCode, 0);
    }
    throw;
  }
  try
  {
    v48 = Event;
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CA0,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        v47);
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v169,
      v48);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x13C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
      v49);
    v36 = (int)hObject[0];
    v6 = *(_QWORD *)ExitCode;
    *(_QWORD *)&v148 = *(_QWORD *)ExitCode;
    v7 = v156;
  }
  v152[0] = off_1403D6BA0;
  v153 = v152;
  Monitor<std::pair<bool,bool>>::send_change(v6, v152);
  v150 = 0;
  *(_QWORD *)&v143 = v6;
  *((_QWORD *)&v143 + 1) = &v169;
  std::async__Windows::UXNotifications::RebootSystemWithUx_::_10_::_lambda_2___(&v150, v50, &v143);
  *(_QWORD *)&v171 = v6;
  BYTE8(v171) = 1;
  v149 = 0;
  v51 = OpenEventW(0x100002u, 0, L"Global\\USORebootCancel");
  try
  {
    if ( !v51 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CA0,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        v52);
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v149,
      v51);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x15F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
      v53);
    v36 = (int)hObject[0];
    *(_QWORD *)&v148 = *(_QWORD *)ExitCode;
    v7 = v156;
  }
  *(_OWORD *)lpHandles = 0;
  v167 = 0;
  LODWORD(v54) = 64;
  LODWORD(hObject[0]) = 64;
  if ( (_QWORD)v169 )
  {
    v55 = *(_QWORD *)v169;
    if ( *(_QWORD *)v169 )
    {
      LODWORD(hObject[0]) = 0;
      *(_QWORD *)ExitCode = v55;
      std::vector<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::_Emplace_reallocate<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
        lpHandles,
        0,
        ExitCode);
    }
  }
  if ( (_QWORD)v149 )
  {
    v56 = *(void **)v149;
    if ( *(_QWORD *)v149 )
    {
      v54 = lpHandles[1] - lpHandles[0];
      *(_QWORD *)ExitCode = *(_QWORD *)v149;
      if ( lpHandles[1] != v167 )
      {
        *lpHandles[1] = v56;
        v57 = ++lpHandles[1];
        goto LABEL_63;
      }
      std::vector<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::_Emplace_reallocate<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
        lpHandles,
        lpHandles[1],
        ExitCode);
    }
  }
  v57 = lpHandles[1];
LABEL_63:
  *(_QWORD *)ExitCode = v57 - lpHandles[0];
  if ( v57 == v167 )
  {
    std::vector<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::_Emplace_reallocate<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
      lpHandles,
      v57,
      hProcess);
    v58 = lpHandles[1];
  }
  else
  {
    *v57 = hProcess[0];
    v58 = ++lpHandles[1];
  }
  v60 = WaitForMultipleObjects(v58 - lpHandles[0], lpHandles[0], 0, 0x493E0u);
  if ( v60 >= lpHandles[1] - lpHandles[0] )
  {
    if ( (_DWORD)v60 == 258 )
    {
      v132 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(&v168);
      v133 = *(void (__fastcall **)(__int64, HANDLE *, __int64, __int64))(*(_QWORD *)v132 + 104LL);
      v134 = std::shared_ptr<Update>::shared_ptr<Update>(&v143, v7);
      *(_OWORD *)hObject = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                        TargetHandle,
                                        L"Reboot with blocking apps could not complete due to UX process launch timeout");
      v133(v132, hObject, v134, 1);
      v135 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(&v170);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v135 + 64LL))(v135, v148, 0);
    }
    else if ( (_DWORD)v60 == -1 )
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DD,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
        v59);
    }
    v136 = (unsigned __int16)v60 | 0x80070000;
    if ( (int)v60 <= 0 )
      v136 = (unsigned int)v60;
    v137 = wil::verify_hresult(v136);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
      (const char *)v137,
      v142);
  }
  if ( !(_QWORD)v149 || !*(_QWORD *)v149 || (_DWORD)v60 != (_DWORD)v54 )
  {
    if ( (_QWORD)v169 && *(_QWORD *)v169 && (_DWORD)v60 == LODWORD(hObject[0]) )
    {
      v77 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
      v143 = 0;
      v78 = v7[1];
      if ( v78 )
        _InterlockedAdd((volatile signed __int32 *)(v78 + 8), 1u);
      v143 = *(_OWORD *)v7;
      v79 = (__int64 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"USO worker canceled",
                         &qword_140475598,
                         0);
      if ( v79 == &qword_140475598 || (v82 = ((char *)v79 - (char *)L"USO worker canceled") >> 1, v82 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v80);
      hObject[0] = L"USO worker canceled";
      hObject[1] = (HANDLE)v82;
      v77(v81, hObject, &v143, 1);
      goto LABEL_115;
    }
    if ( (_DWORD)v60 != ExitCode[0] )
    {
LABEL_115:
      v83 = v148;
      goto LABEL_116;
    }
    ExitCode[0] = 0;
    if ( !GetExitCodeProcess(hProcess[0], ExitCode) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x187,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
        v88);
    if ( ExitCode[0] == 1073807364 || ExitCode[0] == -1073741510 )
    {
      v113 = --lpHandles[1] - lpHandles[0];
      if ( !v113 || !(_QWORD)v149 || !*(_QWORD *)v149 )
      {
        hObject[0] = (HANDLE)300;
        v152[0] = off_1403D6B70;
        v153 = v152;
        v83 = v148;
        Monitor<std::pair<bool,bool>>::wait_for(v148, v147, v152, hObject);
        if ( *(_BYTE *)Monitor<std::pair<bool,bool>>::get(v83, v147) )
        {
LABEL_116:
          std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(lpHandles);
          v84 = (volatile signed __int32 *)*((_QWORD *)&v149 + 1);
          if ( *((_QWORD *)&v149 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v149 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
              if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
            }
          }
          v152[0] = off_1403D6B40;
          v153 = v152;
          Monitor<std::pair<bool,bool>>::send_change(v83, v152);
          v86 = v150;
          if ( (_QWORD)v150 && _InterlockedExchangeAdd((volatile signed __int32 *)(v150 + 8), 0xFFFFFFFF) == 1 )
          {
            v87 = *(void (__fastcall ****)(_QWORD, __int64))(v86 + 200);
            if ( v87 )
              (**v87)(*(_QWORD *)(v86 + 200), v86);
            else
              (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
          }
          v126 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
          if ( *((_QWORD *)&v169 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v126)(v126);
              if ( _InterlockedExchangeAdd(v126 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v126 + 8LL))(v126);
            }
          }
          wil::details::CloseProcessInformation((wil::details *)hProcess, v85);
          v13 = (char *)v146;
          goto LABEL_193;
        }
        v120 = v168;
        v121 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
        v143 = 0;
        v122 = v7[1];
        if ( v122 )
          _InterlockedAdd((volatile signed __int32 *)(v122 + 8), 1u);
        v143 = *(_OWORD *)v7;
        v148 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                            TargetHandle,
                            L"MoNotificationUx exited, reboot timed out");
        v121(v120, &v148, &v143, 1);
        std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(lpHandles);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v149);
        v152[0] = off_1403D6B40;
        v153 = v152;
        Monitor<std::pair<bool,bool>>::send_change(v83, v152);
        v123 = v150;
        if ( (_QWORD)v150 && _InterlockedExchangeAdd((volatile signed __int32 *)(v150 + 8), 0xFFFFFFFF) == 1 )
        {
          v124 = *(void (__fastcall ****)(_QWORD, __int64))(v123 + 200);
          if ( v124 )
            (**v124)(*(_QWORD *)(v123 + 200), v123);
          else
            (**(void (__fastcall ***)(__int64, __int64))v123)(v123, 1);
        }
LABEL_183:
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v169);
        wil::details::CloseProcessInformation((wil::details *)hProcess, v125);
        if ( (char *)v146 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(v146);
        v97 = 2048;
        goto LABEL_186;
      }
      v114 = WaitForMultipleObjects(v113, lpHandles[0], 0, 0x493E0u);
      if ( v114 != (_DWORD)v54 )
      {
        if ( (_QWORD)v169 && *(_QWORD *)v169 && v114 == LODWORD(hObject[0]) )
        {
          v89 = v168;
          v90 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
          v143 = 0;
          v118 = v7[1];
          if ( v118 )
            _InterlockedAdd((volatile signed __int32 *)(v118 + 8), 1u);
          v143 = *(_OWORD *)v7;
          v92 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                            TargetHandle,
                            L"MoNotificationUx exited, USO worker canceled");
        }
        else
        {
          if ( v114 != 258 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x1A5,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
              (const char *)v114,
              v142);
          v89 = v168;
          v90 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
          v143 = 0;
          v119 = v7[1];
          if ( v119 )
            _InterlockedAdd((volatile signed __int32 *)(v119 + 8), 1u);
          v143 = *(_OWORD *)v7;
          v92 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                            TargetHandle,
                            L"MoNotificationUx exited, reboot was not canceled");
        }
        goto LABEL_132;
      }
      v115 = v168;
      v116 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
      v143 = 0;
      v117 = v7[1];
      if ( v117 )
        _InterlockedAdd((volatile signed __int32 *)(v117 + 8), 1u);
      v143 = *(_OWORD *)v7;
      *(_OWORD *)hObject = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                        TargetHandle,
                                        L"MoNotificationUx exited, reboot canceled due to blocking apps");
      v116(v115, hObject, &v143, 1);
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(lpHandles);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v149);
      v152[0] = off_1403D6B40;
      v153 = v152;
      Monitor<std::pair<bool,bool>>::send_change(v148, v152);
    }
    else
    {
      if ( (ExitCode[0] & 0x80000000) == 0 )
      {
        v89 = v168;
        v90 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
        v143 = 0;
        v91 = v7[1];
        if ( v91 )
          _InterlockedAdd((volatile signed __int32 *)(v91 + 8), 1u);
        v143 = *(_OWORD *)v7;
        v92 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                          TargetHandle,
                          L"UsoSession: Reboot with blocking apps UX completed");
LABEL_132:
        *(_OWORD *)hObject = *v92;
        v90(v89, hObject, &v143, 1);
        goto LABEL_115;
      }
      if ( ExitCode[0] == -2147023705 )
      {
        v93 = v168;
        v94 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
        v143 = 0;
        v95 = v7[1];
        if ( v95 )
          _InterlockedAdd((volatile signed __int32 *)(v95 + 8), 1u);
        v143 = *(_OWORD *)v7;
        *(_OWORD *)hObject = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                          TargetHandle,
                                          L"Reboot was canceled due to other users being logged in.");
        v94(v93, hObject, &v143, 1);
        std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(lpHandles);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v149);
        v152[0] = off_1403D6B40;
        v153 = v152;
        Monitor<std::pair<bool,bool>>::send_change(v148, v152);
        std::_Promise<int>::~_Promise<int>(&v150);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v169);
        wil::details::CloseProcessInformation((wil::details *)hProcess, v96);
        if ( (char *)v146 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(v146);
        v97 = 0x2000;
LABEL_186:
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v173);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v170);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v168);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v7);
        return v97;
      }
      v98 = (_QWORD *)SystemInterface::Service::GetSystem(&v143);
      v99 = v36 | 1;
      LODWORD(hObject[0]) = v99;
      v100 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v98 + 168LL))(*v98);
      v101 = ExitCode[0];
      if ( !v100 || (v102 = 1, ExitCode[0] != -2147024891) )
        v102 = 0;
      if ( (v99 & 1) != 0 )
      {
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v143);
        v101 = ExitCode[0];
      }
      if ( v102 )
      {
        v103 = v168;
        v104 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
        v143 = 0;
        v105 = v7[1];
        if ( v105 )
          _InterlockedAdd((volatile signed __int32 *)(v105 + 8), 1u);
        v106 = 75;
        v107 = L"Reboot from user context is not permitted on server SKU, try normal reboot";
LABEL_152:
        v143 = *(_OWORD *)v7;
        v109 = (void *)wil::basic_zstring_view<wchar_t>::length_n(v107, v106);
        hObject[0] = (HANDLE)v107;
        hObject[1] = v109;
        v104(v103, hObject, &v143, 1);
        v83 = v148;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v170 + 64LL))(v170, v148, 0);
        goto LABEL_116;
      }
      if ( (_DWORD)v101 == -2147023625 )
      {
        v103 = v168;
        v104 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
        v143 = 0;
        v108 = v7[1];
        if ( v108 )
          _InterlockedAdd((volatile signed __int32 *)(v108 + 8), 1u);
        v106 = 71;
        v107 = L"Reboot for active user failed due to machine locked, try normal reboot";
        goto LABEL_152;
      }
      if ( (_DWORD)v101 != -2145083109 )
      {
        v131 = wil::verify_hresult(v101);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D3,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\lib\\UXNotifications.cpp",
          (const char *)v131,
          v142);
      }
      v110 = v168;
      v111 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
      v143 = 0;
      v112 = v7[1];
      if ( v112 )
        _InterlockedAdd((volatile signed __int32 *)(v112 + 8), 1u);
      v143 = *(_OWORD *)v7;
      *(_OWORD *)hObject = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                        TargetHandle,
                                        L"Reboot was canceled due to blocking apps.");
      v111(v110, hObject, &v143, 1);
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(lpHandles);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v149);
      v152[0] = off_1403D6B40;
      v153 = v152;
      Monitor<std::pair<bool,bool>>::send_change(v148, v152);
    }
    std::_Promise<int>::~_Promise<int>(&v150);
    goto LABEL_183;
  }
  v61 = *(void (__fastcall **)(__int64, HANDLE *, __int128 *, __int64))(*(_QWORD *)v168 + 104LL);
  v143 = 0;
  v62 = v7[1];
  if ( v62 )
    _InterlockedAdd((volatile signed __int32 *)(v62 + 8), 1u);
  v143 = *(_OWORD *)v7;
  v63 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Reboot canceled due to blocking apps",
                     word_14047512A,
                     0);
  if ( v63 == word_14047512A || (v66 = ((char *)v63 - (char *)L"Reboot canceled due to blocking apps") >> 1, v66 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v64);
  hObject[0] = L"Reboot canceled due to blocking apps";
  hObject[1] = (HANDLE)v66;
  v61(v65, hObject, &v143, 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(lpHandles);
  v67 = (volatile signed __int32 *)*((_QWORD *)&v149 + 1);
  if ( *((_QWORD *)&v149 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v149 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
      if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
    }
  }
  v152[0] = off_1403D6B40;
  v153 = v152;
  Monitor<std::pair<bool,bool>>::send_change(v148, v152);
  v69 = v150;
  if ( (_QWORD)v150 && _InterlockedExchangeAdd((volatile signed __int32 *)(v150 + 8), 0xFFFFFFFF) == 1 )
  {
    v70 = *(void (__fastcall ****)(_QWORD, __int64))(v69 + 200);
    if ( v70 )
      (**v70)(*(_QWORD *)(v69 + 200), v69);
    else
      (**(void (__fastcall ***)(__int64, __int64))v69)(v69, 1);
  }
  v71 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
  if ( *((_QWORD *)&v169 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
      if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
    }
  }
  wil::details::CloseProcessInformation((wil::details *)hProcess, v68);
  if ( (char *)v146 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v146);
  v72 = (volatile signed __int32 *)*((_QWORD *)&v173 + 1);
  if ( *((_QWORD *)&v173 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v173 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
      if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
    }
  }
  v73 = (volatile signed __int32 *)*((_QWORD *)&v170 + 1);
  if ( *((_QWORD *)&v170 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
      if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
    }
  }
  v74 = (volatile signed __int32 *)*((_QWORD *)&v168 + 1);
  if ( *((_QWORD *)&v168 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v168 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
      if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
    }
  }
  v75 = (volatile signed __int32 *)v7[1];
  if ( v75 )
  {
    if ( _InterlockedExchangeAdd(v75 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
      if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
    }
  }
  return 2048;
}

```

## disassembly

```asm
0x1402a3ca0  mov     rax, rsp
0x1402a3ca3  push    rbx
0x1402a3ca4  push    rsi
0x1402a3ca5  push    rdi
0x1402a3ca6  push    r12
0x1402a3ca8  push    r13
0x1402a3caa  push    r14
0x1402a3cac  push    r15
0x1402a3cae  sub     rsp, 2A0h
0x1402a3cb5  movaps  xmmword ptr [rax-48h], xmm6
0x1402a3cb9  movaps  xmmword ptr [rax-58h], xmm7
0x1402a3cbd  mov     rax, cs:__security_cookie
0x1402a3cc4  xor     rax, rsp
0x1402a3cc7  mov     [rsp+2D8h+var_60], rax
0x1402a3ccf  mov     r13, r9
0x1402a3cd2  mov     qword ptr [rsp+2D8h+var_258], r9
0x1402a3cda  mov     [rsp+2D8h+var_268], r8b
0x1402a3cdf  mov     [rsp+2D8h+var_278], dl
0x1402a3ce3  mov     qword ptr [rsp+2D8h+ExitCode], r9
0x1402a3ceb  mov     r12, [rsp+2D8h+arg_20]
0x1402a3cf3  mov     [rsp+2D8h+var_1C0], r12
0x1402a3cfb  xor     r14d, r14d
0x1402a3cfe  mov     dword ptr [rsp+2D8h+hObject], r14d
0x1402a3d03  xorps   xmm0, xmm0
0x1402a3d06  movups  [rsp+2D8h+var_E0], xmm0
0x1402a3d0e  lea     rcx, [rsp+2D8h+var_238]
0x1402a3d16  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402a3d1b  nop
0x1402a3d1c  mov     rcx, [rax]
0x1402a3d1f  mov     rax, [rcx]
0x1402a3d22  lea     rdx, [rsp+2D8h+var_E0]
0x1402a3d2a  mov     rax, [rax+38h]
0x1402a3d2e  call    _guard_dispatch_icall
0x1402a3d33  nop
0x1402a3d34  mov     rbx, qword ptr [rsp+2D8h+var_238+8]
0x1402a3d3c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1402a3d40  test    rbx, rbx
0x1402a3d43  jz      short loc_1402A3D78
0x1402a3d45  mov     eax, edi
0x1402a3d47  lock xadd [rbx+8], eax
0x1402a3d4c  add     eax, edi
0x1402a3d4e  jnz     short loc_1402A3D78
0x1402a3d50  mov     rax, [rbx]
0x1402a3d53  mov     rcx, rbx
0x1402a3d56  mov     rax, [rax]
0x1402a3d59  call    _guard_dispatch_icall
0x1402a3d5e  mov     eax, edi
0x1402a3d60  lock xadd [rbx+0Ch], eax
0x1402a3d65  add     eax, edi
0x1402a3d67  jnz     short loc_1402A3D78
0x1402a3d69  mov     rax, [rbx]
0x1402a3d6c  mov     rcx, rbx
0x1402a3d6f  mov     rax, [rax+8]
0x1402a3d73  call    _guard_dispatch_icall
0x1402a3d78  xorps   xmm0, xmm0
0x1402a3d7b  movups  [rsp+2D8h+var_C0], xmm0
0x1402a3d83  lea     rcx, [rsp+2D8h+var_D0]
0x1402a3d8b  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402a3d90  nop
0x1402a3d91  mov     rdx, [rax]
0x1402a3d94  mov     rax, [rdx+8]
0x1402a3d98  movsxd  rcx, dword ptr [rax+4]
0x1402a3d9c  add     rdx, 8
0x1402a3da0  add     rcx, rdx
0x1402a3da3  mov     rax, [rcx]
0x1402a3da6  lea     rdx, [rsp+2D8h+var_C0]
0x1402a3dae  mov     rax, [rax+50h]
0x1402a3db2  call    _guard_dispatch_icall
0x1402a3db7  nop
0x1402a3db8  mov     rbx, qword ptr [rsp+2D8h+var_D0+8]
0x1402a3dc0  test    rbx, rbx
0x1402a3dc3  jz      short loc_1402A3DF8
0x1402a3dc5  mov     eax, edi
0x1402a3dc7  lock xadd [rbx+8], eax
0x1402a3dcc  add     eax, edi
0x1402a3dce  jnz     short loc_1402A3DF8
0x1402a3dd0  mov     rax, [rbx]
0x1402a3dd3  mov     rcx, rbx
0x1402a3dd6  mov     rax, [rax]
0x1402a3dd9  call    _guard_dispatch_icall
0x1402a3dde  mov     eax, edi
0x1402a3de0  lock xadd [rbx+0Ch], eax
0x1402a3de5  add     eax, edi
0x1402a3de7  jnz     short loc_1402A3DF8
0x1402a3de9  mov     rax, [rbx]
0x1402a3dec  mov     rcx, rbx
0x1402a3def  mov     rax, [rax+8]
0x1402a3df3  call    _guard_dispatch_icall
0x1402a3df8  xorps   xmm0, xmm0
0x1402a3dfb  movups  [rsp+2D8h+var_90], xmm0
0x1402a3e03  mov     rcx, [r12]
0x1402a3e07  mov     rax, [rcx]
0x1402a3e0a  lea     rdx, [rsp+2D8h+var_90]
0x1402a3e12  mov     rax, [rax+20h]
0x1402a3e16  call    _guard_dispatch_icall
0x1402a3e1b  nop
0x1402a3e1c  mov     rbx, r14
0x1402a3e1f  mov     [rsp+2D8h+var_270], rbx
0x1402a3e24  lea     rcx, [rsp+2D8h+hObject]
0x1402a3e29  cmp     [rsp+2D8h+arg_28], r14b
0x1402a3e31  jz      short loc_1402A3E3A
0x1402a3e33  call    ?GetMostPreferredLoggedOnSessionTokenAndTryElevate@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionTokenAndTryElevate(void)
0x1402a3e38  jmp     short loc_1402A3E3F
0x1402a3e3a  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x1402a3e3f  lea     rcx, [rsp+2D8h+var_270]
0x1402a3e44  cmp     rcx, rax
0x1402a3e47  jz      short loc_1402A3E54
0x1402a3e49  mov     rbx, [rax]
0x1402a3e4c  mov     [rsp+2D8h+var_270], rbx
0x1402a3e51  mov     [rax], r14
0x1402a3e54  mov     rcx, [rsp+2D8h+hObject]; hObject
0x1402a3e59  lea     rax, [rcx-1]
0x1402a3e5d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402a3e61  ja      short loc_1402A3E69
0x1402a3e63  call    cs:__imp_CloseHandle
0x1402a3e69  lea     rax, [rbx+1]
0x1402a3e6d  test    rax, 0FFFFFFFFFFFFFFFEh
0x1402a3e73  jnz     short loc_1402A3E94
0x1402a3e75  mov     rcx, qword ptr [rsp+2D8h+var_C0]
0x1402a3e7d  mov     rax, [rcx]
0x1402a3e80  xor     r8d, r8d
0x1402a3e83  mov     rdx, r13
0x1402a3e86  mov     rax, [rax+40h]
0x1402a3e8a  call    _guard_dispatch_icall
0x1402a3e8f  jmp     loc_1402A526C
0x1402a3e94  xorps   xmm0, xmm0
0x1402a3e97  xor     eax, eax
0x1402a3e99  movups  xmmword ptr [rsp+2D8h+hProcess], xmm0
0x1402a3ea1  mov     [rsp+2D8h+var_1C8], rax
0x1402a3ea9  lea     rcx, [rsp+2D8h+var_248]
0x1402a3eb1  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1402a3eb6  nop
0x1402a3eb7  mov     rcx, [rax]
0x1402a3eba  mov     rax, [rcx]
0x1402a3ebd  lea     rdx, [rsp+2D8h+var_298]
0x1402a3ec2  mov     rax, [rax+8]
0x1402a3ec6  call    _guard_dispatch_icall
0x1402a3ecb  nop
0x1402a3ecc  mov     r11, [rax]
0x1402a3ecf  mov     rax, [r11]
0x1402a3ed2  mov     rbx, [rax+30h]
0x1402a3ed6  xor     r8d, r8d
0x1402a3ed9  lea     rsi, word_140475226
0x1402a3ee0  mov     rdx, rsi
0x1402a3ee3  lea     r15, aRebootsystemwi; "RebootSystemWithUx"
0x1402a3eea  mov     rcx, r15
0x1402a3eed  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1402a3ef2  cmp     rax, rsi
0x1402a3ef5  jz      loc_1402A53A3
0x1402a3efb  sub     rax, r15
0x1402a3efe  sar     rax, 1
0x1402a3f01  cmp     rax, rdi
0x1402a3f04  jz      loc_1402A53A3
0x1402a3f0a  mov     qword ptr [rsp+2D8h+var_238], r15
0x1402a3f12  mov     qword ptr [rsp+2D8h+var_238+8], rax
0x1402a3f1a  lea     r8, [rsp+2D8h+var_238]
0x1402a3f22  lea     rdx, [rsp+2D8h+var_80]
0x1402a3f2a  mov     rcx, r11
0x1402a3f2d  mov     rax, rbx
0x1402a3f30  call    _guard_dispatch_icall
0x1402a3f35  nop
0x1402a3f36  cmp     qword ptr [rax+18h], 7
0x1402a3f3b  jbe     short loc_1402A3F40
0x1402a3f3d  mov     rax, [rax]
0x1402a3f40  xorps   xmm0, xmm0
0x1402a3f43  movups  [rsp+2D8h+var_B0], xmm0
0x1402a3f4b  xorps   xmm1, xmm1
0x1402a3f4e  movdqu  xmmword ptr [rsp+2D8h+var_A0], xmm1
0x1402a3f57  mov     r8, rdi
0x1402a3f5a  inc     r8
0x1402a3f5d  cmp     [rax+r8*2], r14w
0x1402a3f62  jnz     short loc_1402A3F5A
0x1402a3f64  mov     rdx, rax
0x1402a3f67  lea     rcx, [rsp+2D8h+var_B0]
0x1402a3f6f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a3f74  nop
0x1402a3f75  lea     rcx, [rsp+2D8h+var_80]
0x1402a3f7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402a3f82  nop
0x1402a3f83  mov     rbx, qword ptr [rsp+2D8h+var_298+8]
0x1402a3f88  test    rbx, rbx
0x1402a3f8b  jz      short loc_1402A3FC1
0x1402a3f8d  mov     eax, edi
0x1402a3f8f  lock xadd [rbx+8], eax
0x1402a3f94  add     eax, edi
0x1402a3f96  jnz     short loc_1402A3FC1
0x1402a3f98  mov     rax, [rbx]
0x1402a3f9b  mov     rcx, rbx
0x1402a3f9e  mov     rax, [rax]
0x1402a3fa1  call    _guard_dispatch_icall
0x1402a3fa6  mov     eax, edi
0x1402a3fa8  lock xadd [rbx+0Ch], eax
0x1402a3fad  add     eax, edi
0x1402a3faf  jnz     short loc_1402A3FC1
0x1402a3fb1  mov     rax, [rbx]
0x1402a3fb4  mov     rcx, rbx
0x1402a3fb7  mov     rax, [rax+8]
0x1402a3fbb  call    _guard_dispatch_icall
0x1402a3fc0  nop
0x1402a3fc1  mov     rbx, qword ptr [rsp+2D8h+var_248+8]
0x1402a3fc9  test    rbx, rbx
0x1402a3fcc  jz      short loc_1402A4001
0x1402a3fce  mov     eax, edi
0x1402a3fd0  lock xadd [rbx+8], eax
0x1402a3fd5  add     eax, edi
0x1402a3fd7  jnz     short loc_1402A4001
0x1402a3fd9  mov     rax, [rbx]
0x1402a3fdc  mov     rcx, rbx
0x1402a3fdf  mov     rax, [rax]
0x1402a3fe2  call    _guard_dispatch_icall
0x1402a3fe7  mov     eax, edi
0x1402a3fe9  lock xadd [rbx+0Ch], eax
0x1402a3fee  add     eax, edi
0x1402a3ff0  jnz     short loc_1402A4001
0x1402a3ff2  mov     rax, [rbx]
0x1402a3ff5  mov     rcx, rbx
0x1402a3ff8  mov     rax, [rax+8]
0x1402a3ffc  call    _guard_dispatch_icall
0x1402a4001  mov     rcx, qword ptr [rsp+2D8h+var_90]
0x1402a4009  mov     rax, [rcx]
0x1402a400c  lea     rdx, [rsp+2D8h+var_140]
0x1402a4014  mov     rax, [rax+10h]
0x1402a4018  call    _guard_dispatch_icall
0x1402a401d  mov     rbx, rax
0x1402a4020  cmp     qword ptr [rax+18h], 7
0x1402a4025  jbe     short loc_1402A402A
0x1402a4027  mov     rbx, [rax]
0x1402a402a  mov     rax, 7FFFFFFFFFFFFFFEh
0x1402a4034  mov     rcx, [rsp+2D8h+var_A0]
0x1402a403c  sub     rax, rcx
0x1402a403f  cmp     rax, 8
0x1402a4043  jb      loc_1402A53BD
0x1402a4049  lea     r9, [rsp+2D8h+var_B0]
0x1402a4051  cmp     [rsp+2D8h+var_A0+8], 7
0x1402a405a  cmova   r9, qword ptr [rsp+2D8h+var_B0]
0x1402a4063  mov     [rsp+2D8h+var_2A8], 8; __int64
0x1402a406c  lea     rax, aReboot; " /Reboot"
0x1402a4073  mov     [rsp+2D8h+Src], rax; Src
0x1402a4078  mov     [rsp+2D8h+var_2B8], rcx; __int64
0x1402a407d  lea     rcx, [rsp+2D8h+var_160]; void *
0x1402a4085  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1402a408a  mov     esi, 2
0x1402a408f  lea     rax, aForceothers; " /ForceOthers"
0x1402a4096  lea     r15, psz
0x1402a409d  mov     rdx, r15
0x1402a40a0  cmp     [rsp+2D8h+var_278], r14b
0x1402a40a5  cmovnz  rdx, rax
0x1402a40a9  mov     r8, rdi
0x1402a40ac  inc     r8
0x1402a40af  cmp     [rdx+r8*2], r14w
0x1402a40b4  jnz     short loc_1402A40AC
0x1402a40b6  lea     rcx, [rsp+2D8h+var_160]; Src
0x1402a40be  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402a40c3  xorps   xmm0, xmm0
0x1402a40c6  movups  [rsp+2D8h+var_180], xmm0
0x1402a40ce  xorps   xmm1, xmm1
0x1402a40d1  movdqu  [rsp+2D8h+var_170], xmm1
0x1402a40da  movups  xmm0, xmmword ptr [rax]
0x1402a40dd  movups  [rsp+2D8h+var_180], xmm0
0x1402a40e5  movups  xmm1, xmmword ptr [rax+10h]
0x1402a40e9  movups  [rsp+2D8h+var_170], xmm1
0x1402a40f1  mov     [rax], r14w
0x1402a40f5  mov     [rax+10h], r14
0x1402a40f9  mov     qword ptr [rax+18h], 7
0x1402a4101  or      esi, 4
0x1402a4104  lea     rax, aReducedisrupti; " /ReduceDisruption"
0x1402a410b  cmp     [rsp+2D8h+var_268], r14b
0x1402a4110  cmovnz  r15, rax
0x1402a4114  mov     r8, rdi
0x1402a4117  inc     r8
0x1402a411a  cmp     [r15+r8*2], r14w
0x1402a411f  jnz     short loc_1402A4117
0x1402a4121  mov     rdx, r15
0x1402a4124  lea     rcx, [rsp+2D8h+var_180]; Src
0x1402a412c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402a4131  xorps   xmm0, xmm0
0x1402a4134  movups  [rsp+2D8h+var_1A0], xmm0
0x1402a413c  xorps   xmm1, xmm1
0x1402a413f  movdqu  [rsp+2D8h+var_190], xmm1
0x1402a4148  movups  xmm0, xmmword ptr [rax]
0x1402a414b  movups  [rsp+2D8h+var_1A0], xmm0
0x1402a4153  movups  xmm1, xmmword ptr [rax+10h]
0x1402a4157  movups  [rsp+2D8h+var_190], xmm1
0x1402a415f  mov     [rax], r14w
0x1402a4163  mov     [rax+10h], r14
0x1402a4167  mov     r15d, 7
0x1402a416d  mov     [rax+18h], r15
0x1402a4171  or      esi, 8
0x1402a4174  lea     r8d, [r15-2]
0x1402a4178  lea     rdx, aCv; " /CV "
0x1402a417f  lea     rcx, [rsp+2D8h+var_1A0]; Src
0x1402a4187  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402a418c  xorps   xmm0, xmm0
0x1402a418f  movups  [rsp+2D8h+var_238], xmm0
0x1402a4197  xorps   xmm1, xmm1
0x1402a419a  movdqu  [rsp+2D8h+var_228], xmm1
0x1402a41a3  movups  xmm0, xmmword ptr [rax]
0x1402a41a6  movups  [rsp+2D8h+var_238], xmm0
0x1402a41ae  movups  xmm1, xmmword ptr [rax+10h]
0x1402a41b2  movups  [rsp+2D8h+var_228], xmm1
  ... truncated ...
```
