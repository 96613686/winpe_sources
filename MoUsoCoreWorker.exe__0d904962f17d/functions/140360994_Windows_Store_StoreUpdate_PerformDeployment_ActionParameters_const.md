# Windows::Store::StoreUpdate::PerformDeployment(ActionParameters const &)

- ea: `0x140360994`
- end: `0x140362607`
- name: `?PerformDeployment@StoreUpdate@Store@Windows@@AEAA?AV?$optional@J@std@@AEBUActionParameters@@@Z`
- size: `7283`
- prototype: `__int64 __fastcall(struct Windows::Store::StoreUpdate *)`
- caller_count: `1`
- callee_count: `45`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1403603a0`

## callees

- `0x140024de0`
- `0x140040184`
- `0x140041174`
- `0x140041224`
- `0x140041318`
- `0x140043284`
- `0x140045404`
- `0x140057a20`
- `0x1400a4c60`
- `0x1400a5368`
- `0x1400a8280`
- `0x1400b22e4`
- `0x14012a810`
- `0x14012d864`
- `0x14013e2d4`
- `0x14013ee6c`
- `0x14013ef78`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x1402da2c0`
- `0x140357f60`
- `0x140358418`
- `0x14035a83c`
- `0x14035b8c8`
- `0x14035c9e8`
- `0x14035d100`
- `0x14035d374`
- `0x14035de5c`
- `0x14035e788`
- `0x14035ea44`
- `0x14035f0b0`
- `0x140360938`
- `0x140360994`
- `0x140362610`
- `0x1403626cc`
- `0x140362728`
- `0x14036283c`
- `0x140362ef4`
- `0x1403634a0`
- `0x140378932`
- `0x14037893e`
- `0x140378e10`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14036118c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14036197a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140361a78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14036118c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14036197a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140361a78`

## string_xrefs

- `0x1403625e6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140360b59`: `Completed`
- `0x140360c6c`: `Completed`
- `0x140360fc5`: `Completed`
- `0x140361bb2`: `Completed`
- `0x140361f89`: `Completed`
- `0x140362146`: `Completed`
- `0x1403622b9`: `Completed`
- `0x14036243d`: `Completed`
- `0x140360bdb`: `MoUpdateOrchestrator`
- `0x1403610f4`: `PerformDeployment Encountered null AppInstallItem - first`
- `0x140360fbe`: `removed`
- `0x140361f82`: `removed`
- `0x140361543`: `StoreUpdateProgressTimeoutInMinutes`
- `0x140361814`: `StoreUpdateProgressTimeoutInMinutes`
- `0x140361eea`: `PerformDeployment Encountered null AppInstallItem - second`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
int *__fastcall Windows::Store::StoreUpdate::PerformDeployment(
        struct Windows::Store::StoreUpdate *a1,
        int *a2,
        struct SystemInterface::Telemetry::CorrelationVector **a3)
{
  struct Windows::Store::StoreUpdate *v4; // r15
  int *v5; // r13
  unsigned int v6; // r12d
  unsigned int v7; // edx
  struct SystemInterface::Telemetry::CorrelationVector *v8; // rbx
  const char *v9; // r9
  int *result; // rax
  volatile signed __int32 *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  struct SystemInterface::Telemetry::CorrelationVector *v14; // rbx
  unsigned int v15; // r13d
  int v16; // r12d
  int v17; // eax
  __int64 *v18; // rax
  __int64 v19; // rax
  const OLECHAR *v20; // rdx
  const wchar_t *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  void *v24; // rbx
  int v25; // ecx
  HANDLE v26; // rax
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31; // rbx
  struct SystemInterface::Telemetry::CorrelationVector *v32; // rbx
  volatile signed __int32 *v33; // rbx
  __int64 v34; // rbx
  bool v35; // zf
  _QWORD *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rax
  unsigned int v45; // edx
  const void *v46; // r12
  __int64 v47; // rbx
  volatile signed __int32 *v48; // r13
  __int64 v49; // r12
  volatile signed __int32 *v50; // rbx
  int v51; // eax
  HANDLE v52; // rax
  int v53; // eax
  HANDLE v54; // rax
  __int64 v55; // rbx
  _QWORD *System; // rax
  __int64 (__fastcall *v57)(__int64, _QWORD *, __int64 *); // r12
  const wchar_t *traits_2_unsigned_short; // rax
  const char *v59; // r9
  __int64 v60; // r11
  __int64 v61; // rax
  volatile signed __int32 *v62; // r12
  volatile signed __int32 *v63; // r12
  __int64 v64; // r8
  _BYTE *v65; // r12
  char *v66; // rax
  _BYTE *v67; // r13
  _BYTE *v68; // rcx
  _BYTE *v69; // rdx
  char v70; // al
  _BYTE *v71; // rax
  __int64 v72; // rax
  int v73; // eax
  int v74; // eax
  __int64 v75; // rcx
  double v76; // xmm0_8
  __int64 v77; // rax
  unsigned __int64 v78; // r14
  __int64 v79; // rax
  unsigned __int64 v80; // rax
  const wchar_t *v81; // r9
  __int64 v82; // r15
  volatile signed __int32 *v83; // rbx
  __int64 v84; // rax
  unsigned int v85; // r12d
  char v86; // bl
  __int64 v87; // rcx
  double v88; // xmm0_8
  __int64 v89; // rax
  unsigned __int64 v90; // r12
  __int64 v91; // rax
  unsigned __int64 v92; // rsi
  struct SystemInterface::Telemetry::CorrelationVector *v93; // rbx
  __int64 *v94; // rbx
  __int64 v95; // rcx
  unsigned int v96; // r13d
  int v97; // r12d
  int v98; // eax
  __int64 *v99; // rax
  __int64 v100; // rax
  const OLECHAR *v101; // rdx
  const wchar_t *v102; // rax
  _QWORD *v103; // rcx
  __int64 v104; // rdx
  void *v105; // rbx
  int v106; // ecx
  HANDLE v107; // rax
  __int64 v108; // rax
  __int64 v109; // rbx
  struct SystemInterface::Telemetry::CorrelationVector *v110; // rbx
  volatile signed __int32 *v111; // rbx
  volatile signed __int32 *v112; // rbx
  struct SystemInterface::Telemetry::CorrelationVector *v113; // rbx
  int v114; // esi
  __int64 v115; // rax
  double v116; // xmm0_8
  __int64 v117; // rax
  unsigned __int64 v118; // r12
  __int64 v119; // rax
  unsigned __int64 v120; // rsi
  struct SystemInterface::Telemetry::CorrelationVector *v121; // rbx
  __int64 v122; // rcx
  double v123; // xmm0_8
  __int64 v124; // rax
  unsigned __int64 v125; // r12
  __int64 v126; // rax
  unsigned __int64 v127; // r15
  struct SystemInterface::Telemetry::CorrelationVector *v128; // rbx
  unsigned int v129; // ebx
  __int64 v130; // rax
  double v131; // xmm0_8
  __int64 v132; // rax
  unsigned __int64 v133; // r14
  __int64 v134; // rax
  unsigned __int64 v135; // rsi
  struct SystemInterface::Telemetry::CorrelationVector *v136; // rdi
  __int64 v137; // rax
  int v138; // eax
  __int64 v139; // rcx
  char v140; // [rsp+40h] [rbp-368h]
  char v141; // [rsp+40h] [rbp-368h]
  LPVOID v142; // [rsp+48h] [rbp-360h] BYREF
  __int64 v143; // [rsp+50h] [rbp-358h] BYREF
  struct Windows::Store::StoreUpdate *v144; // [rsp+58h] [rbp-350h] BYREF
  __int64 v145; // [rsp+60h] [rbp-348h]
  struct SystemInterface::Telemetry::CorrelationVector **v146; // [rsp+68h] [rbp-340h] BYREF
  int *v147; // [rsp+70h] [rbp-338h] BYREF
  void *Source[2]; // [rsp+78h] [rbp-330h] BYREF
  const wchar_t *v149; // [rsp+90h] [rbp-318h] BYREF
  __int64 v150; // [rsp+98h] [rbp-310h]
  unsigned int v151; // [rsp+A0h] [rbp-308h]
  _BYTE *v152; // [rsp+A8h] [rbp-300h] BYREF
  char *v153; // [rsp+B0h] [rbp-2F8h]
  __int64 v154; // [rsp+B8h] [rbp-2F0h] BYREF
  __int128 v155; // [rsp+C0h] [rbp-2E8h] BYREF
  __int128 v156; // [rsp+D0h] [rbp-2D8h] BYREF
  __int128 v157; // [rsp+E0h] [rbp-2C8h]
  __int128 v158; // [rsp+F0h] [rbp-2B8h] BYREF
  __int64 v159; // [rsp+100h] [rbp-2A8h]
  __int128 v160; // [rsp+110h] [rbp-298h] BYREF
  __int128 v161; // [rsp+120h] [rbp-288h]
  __int64 v162; // [rsp+130h] [rbp-278h]
  _QWORD v163[2]; // [rsp+140h] [rbp-268h] BYREF
  _QWORD v164[2]; // [rsp+150h] [rbp-258h] BYREF
  struct SystemInterface::Telemetry::CorrelationVector **v165; // [rsp+160h] [rbp-248h] BYREF
  volatile signed __int32 *v166; // [rsp+168h] [rbp-240h]
  int *v167; // [rsp+170h] [rbp-238h] BYREF
  volatile signed __int32 *v168; // [rsp+178h] [rbp-230h]
  _QWORD v169[5]; // [rsp+180h] [rbp-228h] BYREF
  winrt::hresult_error *v170; // [rsp+1A8h] [rbp-200h] BYREF
  volatile signed __int32 *v171; // [rsp+1B0h] [rbp-1F8h] BYREF
  __int64 v172; // [rsp+1D0h] [rbp-1D8h] BYREF
  __int64 v173; // [rsp+1D8h] [rbp-1D0h] BYREF
  __int64 v174; // [rsp+1E0h] [rbp-1C8h] BYREF
  __int128 v175; // [rsp+1E8h] [rbp-1C0h] BYREF
  LPVOID lpMem; // [rsp+1F8h] [rbp-1B0h] BYREF
  _OWORD v177[21]; // [rsp+200h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v146 = a3;
  v147 = a2;
  v4 = a1;
  v167 = a2;
  v163[0] = a3;
  *(_QWORD *)&v160 = a1;
  v144 = a1;
  v164[0] = a1;
  v142 = a1;
  v5 = a2;
  v145 = (__int64)a2;
  v165 = a3;
  v6 = 0;
  v151 = 0;
  LODWORD(v153) = 0;
  memset(v177, 0, sizeof(v177));
  DWORD2(v177[0]) = 0;
  BYTE12(v177[0]) = 0;
  BYTE8(v177[4]) = 0;
  LODWORD(v177[3]) = 0;
  *((_QWORD *)&v177[3] + 1) = "Deploy";
  *(_QWORD *)&v177[4] = 0;
  LODWORD(v177[5]) = 0;
  v177[15] = 0;
  memset((char *)&v177[5] + 8, 0, 0x98u);
  try
  {
    LODWORD(v177[16]) = 1;
    *((_QWORD *)&v177[16] + 1) = 0;
    *(_QWORD *)&v177[17] = (char *)v177 + 8;
    *((_QWORD *)&v177[17] + 1) = 0;
    *(_QWORD *)&v177[18] = 0;
    *((_QWORD *)&v177[18] + 1) = v177;
    *(_QWORD *)&v177[19] = 0;
    DWORD2(v177[19]) = 0;
    *(_QWORD *)&v177[20] = &v177[3];
    *(_QWORD *)&v177[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
    *((_QWORD *)&v177[20] + 1) = 0;
    Windows::Store::Telemetry::StoreProvider::Deploy::StartActivity(
      (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
      *a3,
      v4);
    winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager((winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)&v174);
    if ( !v174 )
    {
      v8 = *a3;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v177,
        2147500035LL);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
        v8,
        L"Completed",
        L"null pointer");
      *v5 = -2147467261;
      *((_BYTE *)v5 + 4) = 1;
      if ( v174 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
      *(_QWORD *)&v177[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v177);
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v177);
      return v5;
    }
    v11 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x14, v7);
    memcpy_s((void *const)(v11 + 7), 0x28u, L"MoUpdateOrchestrator", 0x28u);
    *(_QWORD *)&v158 = v11;
    *(_QWORD *)&v156 = v11;
    winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(
      (winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)&v143,
      (const struct winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)&v174,
      (const struct winrt::param::hstring *)&v156);
    if ( v11 )
    {
      v12 = _InterlockedDecrement(v11 + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
      }
    }
    if ( !v143 )
    {
      v14 = *v146;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v177,
        2147500035LL);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
        v14,
        L"Completed",
        L"null pointer");
      *v147 = -2147467261;
      *((_BYTE *)v5 + 4) = 1;
      if ( v143 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
      if ( v174 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
LABEL_14:
      *(_QWORD *)&v177[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v177);
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v177);
      return v5;
    }
    v175 = 0;
    winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
      &v174,
      &v173);
    if ( v173 )
    {
      v15 = 0;
      winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::end(
        &v173,
        Source);
      while ( v15 != LODWORD(Source[1]) )
      {
        v172 = 0;
        v16 = v6 | 4;
        LODWORD(v153) = v16;
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v173 + 48LL))(v173, v15, &v172);
        if ( v17 < 0 )
          winrt::throw_hresult((unsigned int)v17);
        v6 = v16 & 0xFFFFFFF9 | 2;
        v151 = v6;
        LODWORD(v153) = v6;
        if ( v172 )
        {
          v18 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
                             &v172,
                             &lpMem);
          v156 = 0;
          v157 = 0;
          v19 = *v18;
          if ( v19 )
            v20 = *(const OLECHAR **)(v19 + 16);
          else
            v20 = &psz;
          std::wstring::_Construct<1,wchar_t const *>(&v156, v20);
          v21 = (const wchar_t *)&v156;
          if ( *((_QWORD *)&v157 + 1) > 7u )
            v21 = (const wchar_t *)v156;
          v22 = (_QWORD *)((char *)v4 + 144);
          v23 = *((_QWORD *)v4 + 20);
          if ( *((_QWORD *)v4 + 21) > 7u )
            v22 = (_QWORD *)*v22;
          v149 = v21;
          v150 = v157;
          *(_QWORD *)&v155 = v22;
          *((_QWORD *)&v155 + 1) = v23;
          v140 = Strings::iequals(&v155, &v149);
          std::wstring::~wstring(&v156);
          v24 = lpMem;
          if ( lpMem )
          {
            v25 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
            if ( v25 )
            {
              if ( v25 < 0 )
                abort();
            }
            else
            {
              v26 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v26, 0, v24);
            }
            lpMem = 0;
          }
          if ( v140 )
          {
            v27 = (__int64 *)std::make_shared<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem &>(
                               &v149,
                               &v172);
            v28 = *v27;
            v29 = v27[1];
            *v27 = 0;
            v27[1] = 0;
            *(_QWORD *)&v175 = v28;
            v30 = (volatile signed __int32 *)*((_QWORD *)&v175 + 1);
            *((_QWORD *)&v175 + 1) = v29;
            if ( v30 )
            {
              if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
                if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
              }
            }
            v31 = (volatile signed __int32 *)v150;
            if ( v150 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v150 + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
                if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
              }
            }
            if ( v172 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v172);
            break;
          }
        }
        else
        {
          *(_QWORD *)&v158 = L"PerformDeployment Encountered null AppInstallItem - first";
          *((_QWORD *)&v158 + 1) = 57;
          SystemInterface::Log<>(&v158);
        }
        if ( v172 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v172);
        ++v15;
      }
      v5 = (int *)v145;
    }
    else
    {
      v149 = L"PerformDeployment Encountered null VectorView - first";
      v150 = 53;
      SystemInterface::Log<>(&v149);
    }
    if ( !(_QWORD)v175 )
    {
      v32 = *v146;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v177,
        0);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
        v32,
        L"Completed",
        L"removed");
      *((_DWORD *)v4 + 34) = 1;
      *v147 = 0;
      *((_BYTE *)v5 + 4) = 1;
      if ( v173 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
      v33 = (volatile signed __int32 *)*((_QWORD *)&v175 + 1);
      if ( *((_QWORD *)&v175 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v175 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        }
      }
      if ( v143 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
      if ( v174 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
      goto LABEL_14;
    }
    v149 = (const wchar_t *)v4;
    v150 = 1;
    *(_QWORD *)&v158 = (char *)v4 + 208;
    v34 = *((_QWORD *)v4 + 26);
    if ( (unsigned int)mtx_do_lock(v34, 0) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v34 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v34 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    **((_BYTE **)v4 + 40) = 1;
    v35 = (*(_DWORD *)(v34 + 76))-- == 1;
    if ( v35 )
    {
      *(_DWORD *)(v34 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v34 + 16));
    }
    v36 = (_QWORD *)v175;
    v37 = *((_QWORD *)v4 + 41);
    v38 = 0;
    v39 = 0;
    if ( v37 )
    {
      v38 = *((_QWORD *)v4 + 40);
      _InterlockedAdd((volatile signed __int32 *)(v37 + 12), 1u);
      v39 = v37;
    }
    v40 = *((_QWORD *)v4 + 27);
    v41 = 0;
    v42 = 0;
    if ( v40 )
    {
      v41 = *((_QWORD *)v4 + 26);
      _InterlockedAdd((volatile signed __int32 *)(v40 + 12), 1u);
      v42 = v40;
    }
    v169[0] = v4;
    v169[1] = v38;
    v169[2] = v39;
    v155 = 0;
    v169[3] = v41;
    v169[4] = v42;
    *(_OWORD *)Source = 0;
    winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem_winrt::Windows::Foundation::IInspectable_::TypedEventHandler_winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem_winrt::Windows::Foundation::IInspectable___Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_2___(
      &v172,
      v169);
    lpMem = 0;
    v43 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(*(_QWORD *)*v36 + 128LL))(*v36, v172, &lpMem);
    if ( v43 < 0 )
      winrt::throw_hresult((unsigned int)v43);
    if ( v172 )
      winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v172);
    try
    {
      *(_QWORD *)&v161 = &v175;
      *((_QWORD *)&v161 + 1) = &lpMem;
      LOBYTE(v162) = 1;
      v44 = (*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _QWORD *))(*(_QWORD *)*v146 + 16LL))(
              *v146,
              v169);
      v46 = (const void *)v44;
      if ( *(_QWORD *)(v44 + 24) > 7u )
        v46 = *(const void **)v44;
      v47 = *(unsigned int *)(v44 + 16);
      if ( (_DWORD)v47 )
      {
        v48 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v47, v45);
        memcpy_s((void *const)(v48 + 7), 2 * v47, v46, 2 * v47);
      }
      else
      {
        v48 = 0;
      }
      *(_QWORD *)&v155 = v48;
      *(_QWORD *)&v156 = v48;
      LODWORD(v152) = 0;
      LODWORD(v172) = 0;
      Source[0] = (char *)v4 + 144;
      if ( *((_QWORD *)v4 + 21) > 7u )
        Source[0] = *((void **)v4 + 18);
      v49 = *((unsigned int *)v4 + 40);
      if ( (_DWORD)v49 )
      {
        v50 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v49, v45);
        memcpy_s((void *const)(v50 + 7), 2 * v49, Source[0], 2 * v49);
      }
      else
      {
        v50 = 0;
      }
      Source[0] = (void *)v50;
      v171 = v50;
      winrt::impl::consume_WindowsUdk_ApplicationModel_Store_Preview_InstallControl_IAppInstallManager3<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager>::ResumeUpdates(
        (unsigned int)&v143,
        (unsigned int)&v171,
        (unsigned int)&v172,
        (unsigned int)&v152,
        (__int64)&v156);
      if ( v50 )
      {
        v51 = _InterlockedDecrement(v50 + 6);
        if ( v51 )
        {
          if ( v51 < 0 )
            abort();
        }
        else
        {
          v52 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v52, 0, (LPVOID)v50);
        }
      }
      if ( v48 )
      {
        v53 = _InterlockedDecrement(v48 + 6);
        if ( v53 )
        {
          if ( v53 < 0 )
            abort();
        }
        else
        {
          v54 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v54, 0, (LPVOID)v48);
        }
      }
      std::wstring::~wstring(v169);
    }
    catch ( winrt::hresult_error *v170 )
    {
      winrt::hresult_error::to_abi(v170, &v172);
      v129 = v172;
      if ( (_DWORD)v172 == -2147467259 )
      {
        v151 = (unsigned int)v153;
        v147 = v167;
        v146 = (struct SystemInterface::Telemetry::CorrelationVector **)v163[0];
        v4 = (struct Windows::Store::StoreUpdate *)v160;
        goto LABEL_105;
      }
      v130 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
               v175,
               &v146);
      v131 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v130);
      v132 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
               v175,
               &v147);
      v133 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v132);
      v134 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
               v175,
               Source);
      v135 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v134);
      v136 = *v165;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v177,
        v129);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
        v136,
        L"Completed",
        L"failed resume",
        v135,
        v133,
        v131);
      if ( Source[0] )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
      if ( v147 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
      if ( v146 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v146);
      v137 = v145;
      *(_DWORD *)v145 = v129;
      *(_BYTE *)(v137 + 4) = 1;
      (*(void (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)v175 + 136LL))(*(_QWORD *)v175, lpMem);
      wil::details::lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___::_lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___(&v149);
      if ( v173 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v175);
      if ( v143 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
      if ( v174 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
      *(_QWORD *)&v177[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v177);
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v177);
      return (int *)v145;
    }
LABEL_105:
    v160 = 0;
    v55 = *(_QWORD *)v158;
    *(_QWORD *)&v160 = v55;
    BYTE8(v160) = 0;
    if ( (unsigned int)mtx_do_lock(v55, 0) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v55 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v55 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v160) = 1;
    while ( !*((_BYTE *)v4 + 296) )
    {
      System = (_QWORD *)SystemInterface::Service::GetSystem(&v165);
      v57 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, int **))(*(_QWORD *)*System + 40LL))(
                                                                                    *System,
                                                                                    &v167)
                                                                   + 56LL);
      LODWORD(v172) = 30;
      traits_2_unsigned_short = (const wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                                   L"StoreUpdateProgressTimeoutInMinutes",
                                                   L"failed resume",
                                                   0);
      if ( traits_2_unsigned_short == L"failed resume"
        || (v61 = traits_2_unsigned_short - L"StoreUpdateProgressTimeoutInMinutes", v61 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v59);
      }
      v163[0] = L"StoreUpdateProgressTimeoutInMinutes";
      v163[1] = v61;
      LODWORD(v152) = v57(v60, v163, &v172);
      v62 = v168;
      if ( v168 )
      {
        if ( _InterlockedExchangeAdd(v168 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
          if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
        }
      }
      v63 = v166;
      if ( v166 )
      {
        if ( _InterlockedExchangeAdd(v166 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
          if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
        }
      }
      v64 = std::_To_absolute_time<int,std::ratio<60,1>>(&v155, &v152);
      *(_QWORD *)&v158 = v64;
      v65 = (char *)v144 + 297;
      v66 = (char *)v142 + 304;
      v153 = (char *)v142 + 304;
      v67 = (char *)v142 + 304;
      while ( 1 )
      {
        v68 = v65;
        v69 = v67;
        if ( *((_BYTE *)v4 + 296)
          || (v65 = (char *)v4 + 297, v68 = (char *)v4 + 297, v69 = v66, *((_BYTE *)v4 + 297) == 1)
          || (v67 = (char *)v4 + 304, v69 = (char *)v4 + 304, *((_BYTE *)v4 + 304))
          || (v152 = (char *)v4 + 312, *((_BYTE *)v4 + 312)) )
        {
          v71 = (char *)v142 + 312;
          v152 = (char *)v142 + 312;
          v65 = v68;
          v67 = v69;
          goto LABEL_134;
        }
        if ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                             (char *)v4 + 224,
                             &v160,
                             v64) == 1 )
          break;
        v64 = v158;
        v66 = v153;
      }
      if ( *((_BYTE *)v4 + 296) || *v65 == 1 || *v67 || (v70 = 0, *v152) )
        v70 = 1;
      if ( !v70 )
      {
        LODWORD(Source[0]) = 1;
        BYTE4(Source[0]) = 1;
        *(void **)((char *)v4 + 300) = Source[0];
        *(_QWORD *)&v158 = L"Deploy timeout";
        *((_QWORD *)&v158 + 1) = 14;
        LOBYTE(v159) = 1;
        v156 = v158;
        *(_QWORD *)&v157 = v159;
        Windows::Store::StoreUpdate::LogAppInstallCurrentStatus(v4, v175, &v156);
        v65 = (char *)v144 + 297;
        v67 = v153;
      }
      v71 = v152;
LABEL_134:
      *v65 = 0;
      if ( *v67 || *v71 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_StoreLoopFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_StoreLoopFixes>::GetImpl'::`2'::impl) )
        {
          v72 = **(_QWORD **)v175;
          if ( *v152 )
          {
            v73 = (*(__int64 (**)(void))(v72 + 96))();
            if ( v73 < 0 )
              winrt::throw_hresult((unsigned int)v73);
          }
          else
          {
            v74 = (*(__int64 (**)(void))(v72 + 88))();
            if ( v74 < 0 )
              winrt::throw_hresult((unsigned int)v74);
          }
        }
        v75 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                v175,
                Source);
        v76 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v75);
        v77 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                v175,
                &v144);
        v78 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v77);
        v79 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                v175,
                &v142);
        v80 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v79);
        v81 = L"aborted";
        if ( *(_BYTE *)(v164[0] + 312LL) )
          v81 = L"paused";
        Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
          (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
          *v146,
          L"Aborted",
          v81,
          v80,
          v78,
          v76);
        if ( v142 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v142);
        if ( v144 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v144);
        if ( Source[0] )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
        v82 = v145;
        *(_BYTE *)(v145 + 4) = 0;
        v35 = (*(_DWORD *)(v55 + 76))-- == 1;
        if ( v35 )
        {
          *(_DWORD *)(v55 + 72) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)(v55 + 16));
        }
        (*(void (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)v161 + 136LL))(
          **(_QWORD **)v161,
          **((_QWORD **)&v161 + 1));
        wil::details::lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___::_lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___(&v149);
        if ( v173 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
        v83 = (volatile signed __int32 *)*((_QWORD *)&v175 + 1);
        if ( *((_QWORD *)&v175 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v175 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
            if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
          }
        }
        if ( v143 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
        if ( v174 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
        goto LABEL_276;
      }
    }
    v35 = (*(_DWORD *)(v55 + 76))-- == 1;
    if ( v35 )
    {
      *(_DWORD *)(v55 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v55 + 16));
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)v161 + 136LL))(**(_QWORD **)v161, **((_QWORD **)&v161 + 1));
    wil::details::lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___::_lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___(&v149);
    if ( *((_BYTE *)v4 + 296) )
    {
      v84 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v175,
              &v142);
      v85 = v151 | 1;
      LODWORD(v153) = v151 | 1;
      if ( *(int *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::ErrorCode(
                     v84,
                     &v172) >= 0 )
      {
        v86 = 1;
        goto LABEL_170;
      }
    }
    else
    {
      v85 = v151;
    }
    v86 = 0;
LABEL_170:
    if ( (v85 & 1) != 0 )
    {
      v85 &= ~1u;
      if ( v142 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v142);
    }
    if ( v86 )
    {
      v87 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v175,
              Source);
      v88 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v87);
      v89 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v175,
              &v144);
      v90 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v89);
      v91 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v175,
              &v142);
      v92 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v91);
      v93 = *v146;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v177,
        0);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
        v93,
        L"Completed",
        L"succeeded",
        v92,
        v90,
        v88);
      if ( v142 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v142);
      if ( v144 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v144);
      if ( Source[0] )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
      *((_DWORD *)v4 + 34) = 1;
      *v147 = 0;
      v82 = v145;
      *(_BYTE *)(v145 + 4) = 1;
      if ( v173 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v175);
      if ( v143 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
      if ( v174 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
    }
    else
    {
      v155 = 0;
      v94 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
                         &v174,
                         &v142);
      if ( &v173 != v94 )
      {
        if ( v173 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
        v95 = *v94;
        *v94 = 0;
        v173 = v95;
      }
      if ( v142 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v142);
      if ( v173 )
      {
        v96 = 0;
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::end(
          &v173,
          &v160);
        while ( v96 != DWORD2(v160) )
        {
          v172 = 0;
          v97 = v85 | 0x10;
          LODWORD(v153) = v97;
          v98 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v173 + 48LL))(v173, v96, &v172);
          if ( v98 < 0 )
            winrt::throw_hresult((unsigned int)v98);
          v85 = v97 & 0xFFFFFFE7 | 8;
          if ( v172 )
          {
            v99 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
                               &v172,
                               &v142);
            v156 = 0;
            v157 = 0;
            v100 = *v99;
            if ( v100 )
              v101 = *(const OLECHAR **)(v100 + 16);
            else
              v101 = &psz;
            std::wstring::_Construct<1,wchar_t const *>(&v156, v101);
            v102 = (const wchar_t *)&v156;
            if ( *((_QWORD *)&v157 + 1) > 7u )
              v102 = (const wchar_t *)v156;
            v103 = (_QWORD *)((char *)v4 + 144);
            v104 = *((_QWORD *)v4 + 20);
            if ( *((_QWORD *)v4 + 21) > 7u )
              v103 = (_QWORD *)*v103;
            v149 = v102;
            v150 = v157;
            v164[0] = v103;
            v164[1] = v104;
            v141 = Strings::iequals(v164, &v149);
            std::wstring::~wstring(&v156);
            v105 = v142;
            if ( v142 )
            {
              v106 = _InterlockedDecrement((volatile signed __int32 *)v142 + 6);
              if ( v106 )
              {
                if ( v106 < 0 )
                  abort();
              }
              else
              {
                v107 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v107, 0, v105);
              }
              v142 = 0;
            }
            if ( v141 )
            {
              v108 = std::make_shared<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem &>(
                       &v149,
                       &v172);
              std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v155, v108);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v149);
              if ( v172 )
                winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v172);
              break;
            }
          }
          else
          {
            *(_QWORD *)&v158 = L"PerformDeployment Encountered null AppInstallItem - second";
            *((_QWORD *)&v158 + 1) = 58;
            SystemInterface::Log<>(&v158);
          }
          if ( v172 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v172);
          ++v96;
        }
      }
      else
      {
        v149 = L"PerformDeployment Encountered null VectorView - second";
        v150 = 54;
        SystemInterface::Log<>(&v149);
      }
      v109 = v155;
      if ( (_QWORD)v155 )
      {
        *(_QWORD *)&v161 = L"StoreProvider Deploy action failed";
        *((_QWORD *)&v161 + 1) = 34;
        LOBYTE(v162) = 1;
        v156 = v161;
        *(_QWORD *)&v157 = v162;
        Windows::Store::StoreUpdate::LogAppInstallCurrentStatus(v4, v155, &v156);
        winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
          v109,
          &v154);
        if ( v154 )
        {
          v114 = *(_DWORD *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::ErrorCode(
                              &v154,
                              &v172);
          if ( *((_BYTE *)v4 + 296) && v114 >= 0 )
          {
            v115 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v109,
                     Source);
            v116 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v115);
            v117 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v109,
                     &v144);
            v118 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v117);
            v119 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v109,
                     &v142);
            v120 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v119);
            v121 = *v146;
            wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
              v177,
              0);
            Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
              (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
              v121,
              L"Completed",
              L"succeeded post refresh",
              v120,
              v118,
              v116);
            if ( v142 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v142);
            if ( v144 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v144);
            if ( Source[0] )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
            *((_DWORD *)v4 + 34) = 1;
            *v147 = 0;
            v82 = v145;
            *(_BYTE *)(v145 + 4) = 1;
            if ( v154 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v154);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v155);
            if ( v173 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v175);
            if ( v143 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
            if ( v174 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
          }
          else
          {
            v122 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v109,
                     Source);
            v123 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v122);
            v124 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v109,
                     &v144);
            v125 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v124);
            v126 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v109,
                     &v142);
            v127 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v126);
            v128 = *v146;
            wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
              v177,
              (unsigned int)v114);
            Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
              (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
              v128,
              L"Completed",
              L"failed",
              v127,
              v125,
              v123);
            if ( v142 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v142);
            if ( v144 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v144);
            if ( Source[0] )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
            *v147 = v114;
            v82 = v145;
            *(_BYTE *)(v145 + 4) = 1;
            if ( v154 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v154);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v155);
            if ( v173 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v175);
            if ( v143 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
            if ( v174 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
          }
        }
        else
        {
          v113 = *v146;
          wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
            v177,
            2147500035LL);
          Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
            (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
            v113,
            L"Completed",
            L"null pointer");
          *v147 = -2147467261;
          v82 = v145;
          *(_BYTE *)(v145 + 4) = 1;
          if ( v154 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v154);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v155);
          if ( v173 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v175);
          if ( v143 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
          if ( v174 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
        }
      }
      else
      {
        v110 = *v146;
        wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
          v177,
          0);
        Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
          (Windows::Store::Telemetry::StoreProvider::Deploy *)v177,
          v110,
          L"Completed",
          L"removed");
        *((_DWORD *)v4 + 34) = 1;
        *v147 = 0;
        v82 = v145;
        *(_BYTE *)(v145 + 4) = 1;
        v111 = (volatile signed __int32 *)*((_QWORD *)&v155 + 1);
        if ( *((_QWORD *)&v155 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v155 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v111)(v111);
            if ( _InterlockedExchangeAdd(v111 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v111 + 8LL))(v111);
          }
        }
        if ( v173 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v173);
        v112 = (volatile signed __int32 *)*((_QWORD *)&v175 + 1);
        if ( *((_QWORD *)&v175 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v175 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v112)(v112);
            if ( _InterlockedExchangeAdd(v112 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v112 + 8LL))(v112);
          }
        }
        if ( v143 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v143);
        if ( v174 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v174);
      }
    }
LABEL_276:
    *(_QWORD *)&v177[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
    wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v177);
    wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v177);
    result = (int *)v82;
  }
  catch ( ... )
  {
    v138 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x23D,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\StoreProvider\\StoreUpdate.cpp",
             v9);
    v139 = v145;
    *(_DWORD *)v145 = v138;
    *(_BYTE *)(v139 + 4) = 1;
    return (int *)v145;
  }
  return result;
}

```

## disassembly

```asm
0x140360994  mov     rax, rsp
0x140360997  push    rbx
0x140360998  push    rsi
0x140360999  push    rdi
0x14036099a  push    r12
0x14036099c  push    r13
0x14036099e  push    r14
0x1403609a0  push    r15
0x1403609a2  sub     rsp, 370h
0x1403609a9  movaps  xmmword ptr [rax-48h], xmm6
0x1403609ad  mov     rax, cs:__security_cookie
0x1403609b4  xor     rax, rsp
0x1403609b7  mov     [rsp+3A8h+var_58], rax
0x1403609bf  mov     rbx, r8
0x1403609c2  mov     [rsp+3A8h+var_340], rbx
0x1403609c7  mov     [rsp+3A8h+var_338], rdx
0x1403609cc  mov     r15, rcx
0x1403609cf  mov     [rsp+3A8h+var_238], rdx
0x1403609d7  mov     [rsp+3A8h+var_268], rbx
0x1403609df  mov     qword ptr [rsp+3A8h+var_298], rcx
0x1403609e7  mov     [rsp+3A8h+var_350], rcx
0x1403609ec  mov     [rsp+3A8h+var_258], rcx
0x1403609f4  mov     [rsp+3A8h+var_360], rcx
0x1403609f9  mov     r13, rdx
0x1403609fc  mov     [rsp+3A8h+var_348], rdx
0x140360a01  mov     [rsp+3A8h+var_248], rbx
0x140360a09  xor     edi, edi
0x140360a0b  mov     r12d, edi
0x140360a0e  mov     [rsp+3A8h+var_308], edi
0x140360a15  mov     dword ptr [rsp+3A8h+var_2F8], edi
0x140360a1c  xor     edx, edx; Val
0x140360a1e  mov     r8d, 150h; Size
0x140360a24  lea     rcx, [rsp+3A8h+var_1A8]; void *
0x140360a2c  call    memset
0x140360a31  nop
0x140360a32  mov     [rsp+3A8h+var_1A0], edi
0x140360a39  mov     [rsp+3A8h+var_19C], dil
0x140360a41  mov     [rsp+3A8h+var_160], dil
0x140360a49  mov     [rsp+3A8h+var_178], edi
0x140360a50  lea     rax, aDeploy_0; "Deploy"
0x140360a57  mov     [rsp+3A8h+var_170], rax
0x140360a5f  mov     [rsp+3A8h+var_168], rdi
0x140360a67  mov     [rsp+3A8h+var_158], edi
0x140360a6e  xorps   xmm0, xmm0
0x140360a71  movdqa  [rsp+3A8h+var_B8], xmm0
0x140360a7a  xor     edx, edx; Val
0x140360a7c  mov     r8d, 98h; Size
0x140360a82  lea     rcx, [rsp+3A8h+var_150]; void *
0x140360a8a  call    memset
0x140360a8f  lea     r14d, [rdi+1]
0x140360a93  mov     [rsp+3A8h+var_A8], r14d
0x140360a9b  xor     eax, eax
0x140360a9d  mov     [rsp+3A8h+var_A0], rax
0x140360aa5  lea     rax, [rsp+3A8h+var_1A0]
0x140360aad  mov     [rsp+3A8h+var_98], rax
0x140360ab5  mov     [rsp+3A8h+var_90], rdi
0x140360abd  mov     [rsp+3A8h+var_88], rdi
0x140360ac5  lea     rax, [rsp+3A8h+var_1A8]
0x140360acd  mov     [rsp+3A8h+var_80], rax
0x140360ad5  mov     [rsp+3A8h+var_78], rdi
0x140360add  mov     [rsp+3A8h+var_70], edi
0x140360ae4  lea     rax, [rsp+3A8h+var_178]
0x140360aec  mov     [rsp+3A8h+var_68], rax
0x140360af4  lea     rax, ??_7Deploy@StoreProvider@Telemetry@Store@Windows@@6B@; const Windows::Store::Telemetry::StoreProvider::Deploy::`vftable'
0x140360afb  mov     [rsp+3A8h+var_1A8], rax
0x140360b03  mov     [rsp+3A8h+var_60], rdi
0x140360b0b  mov     r8, r15; struct Windows::Store::StoreUpdate *
0x140360b0e  mov     rdx, [rbx]; struct SystemInterface::Telemetry::CorrelationVector *
0x140360b11  lea     rcx, [rsp+3A8h+var_1A8]; this
0x140360b19  call    ?StartActivity@Deploy@StoreProvider@Telemetry@Store@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@PEAVStoreUpdate@45@@Z; Windows::Store::Telemetry::StoreProvider::Deploy::StartActivity(SystemInterface::Telemetry::CorrelationVector &,Windows::Store::StoreUpdate *)
0x140360b1e  nop
0x140360b1f  lea     rcx, [rsp+3A8h+var_1C8]; this
0x140360b27  call    ??0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ; winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(void)
0x140360b2c  nop
0x140360b2d  cmp     [rsp+3A8h+var_1C8], rdi
0x140360b35  jnz     loc_140360BC2
0x140360b3b  mov     rbx, [rbx]
0x140360b3e  mov     esi, 80004003h
0x140360b43  mov     edx, esi
0x140360b45  lea     rcx, [rsp+3A8h+var_1A8]
0x140360b4d  call    ?SetStopResult@?$ActivityBase@VStoreProvider@Telemetry@Store@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140360b52  lea     r9, aNullPointer; "null pointer"
0x140360b59  lea     r8, aCompleted; "Completed"
0x140360b60  mov     rdx, rbx; struct SystemInterface::Telemetry::CorrelationVector *
0x140360b63  lea     rcx, [rsp+3A8h+var_1A8]; this
0x140360b6b  call    ?Stop@Deploy@StoreProvider@Telemetry@Store@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@PEB_W1@Z; Windows::Store::Telemetry::StoreProvider::Deploy::Stop(SystemInterface::Telemetry::CorrelationVector &,wchar_t const *,wchar_t const *)
0x140360b70  mov     rax, r13
0x140360b73  mov     [rax], esi
0x140360b75  mov     [r13+4], r14b
0x140360b79  cmp     [rsp+3A8h+var_1C8], rdi
0x140360b81  jz      short loc_140360B91
0x140360b83  lea     rcx, [rsp+3A8h+var_1C8]
0x140360b8b  call    ?unconditional_release_ref@?$com_ptr@UIGlobalInterfaceTable@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(void)
0x140360b90  nop
0x140360b91  lea     rax, ??_7Deploy@StoreProvider@Telemetry@Store@Windows@@6B@; const Windows::Store::Telemetry::StoreProvider::Deploy::`vftable'
0x140360b98  mov     [rsp+3A8h+var_1A8], rax
0x140360ba0  lea     rcx, [rsp+3A8h+var_1A8]
0x140360ba8  call    ?Destroy@?$ActivityBase@VStoreProvider@Telemetry@Store@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140360bad  lea     rcx, [rsp+3A8h+var_1A8]
0x140360bb5  call    ??1?$ActivityBase@VStoreProvider@Telemetry@Store@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x140360bba  mov     rax, r13
0x140360bbd  jmp     loc_140362543
0x140360bc2  mov     ecx, 14h; this
0x140360bc7  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x140360bcc  mov     rbx, rax
0x140360bcf  lea     rcx, [rax+1Ch]; Destination
0x140360bd3  mov     edx, 28h ; '('; DestinationSize
0x140360bd8  mov     r9d, edx; SourceSize
0x140360bdb  lea     r8, Source; "MoUpdateOrchestrator"
0x140360be2  call    memcpy_s
0x140360be7  mov     qword ptr [rsp+3A8h+var_2B8], rbx
0x140360bef  mov     qword ptr [rsp+3A8h+var_2D8], rbx
0x140360bf7  lea     r8, [rsp+3A8h+var_2D8]; struct winrt::param::hstring *
0x140360bff  lea     rdx, [rsp+3A8h+var_1C8]; struct winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *
0x140360c07  lea     rcx, [rsp+3A8h+var_358]; this
0x140360c0c  call    ??0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@QEAA@AEBU01234Windows@6@AEBUhstring@param@6@@Z; winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager const &,winrt::param::hstring const &)
0x140360c11  nop
0x140360c12  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140360c16  test    rbx, rbx
0x140360c19  jz      short loc_140360C3E
0x140360c1b  mov     eax, esi
0x140360c1d  lock xadd [rbx+18h], eax
0x140360c22  sub     eax, 1
0x140360c25  jnz     loc_140360D79
0x140360c2b  nop
0x140360c2c  call    WINRT_IMPL_GetProcessHeap
0x140360c31  mov     rcx, rax; hHeap
0x140360c34  mov     r8, rbx; lpMem
0x140360c37  xor     edx, edx; dwFlags
0x140360c39  call    WINRT_IMPL_HeapFree
0x140360c3e  cmp     [rsp+3A8h+var_358], rdi
0x140360c43  jnz     loc_140360CE9
0x140360c49  mov     rcx, [rsp+3A8h+var_340]
0x140360c4e  mov     rbx, [rcx]
0x140360c51  mov     esi, 80004003h
0x140360c56  mov     edx, esi
0x140360c58  lea     rcx, [rsp+3A8h+var_1A8]
0x140360c60  call    ?SetStopResult@?$ActivityBase@VStoreProvider@Telemetry@Store@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140360c65  lea     r9, aNullPointer; "null pointer"
0x140360c6c  lea     r8, aCompleted; "Completed"
0x140360c73  mov     rdx, rbx; struct SystemInterface::Telemetry::CorrelationVector *
0x140360c76  lea     rcx, [rsp+3A8h+var_1A8]; this
0x140360c7e  call    ?Stop@Deploy@StoreProvider@Telemetry@Store@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@PEB_W1@Z; Windows::Store::Telemetry::StoreProvider::Deploy::Stop(SystemInterface::Telemetry::CorrelationVector &,wchar_t const *,wchar_t const *)
0x140360c83  mov     rax, [rsp+3A8h+var_338]
0x140360c88  mov     [rax], esi
0x140360c8a  mov     [r13+4], r14b
0x140360c8e  cmp     [rsp+3A8h+var_358], rdi
0x140360c93  jz      short loc_140360CA0
0x140360c95  lea     rcx, [rsp+3A8h+var_358]
0x140360c9a  call    ?unconditional_release_ref@?$com_ptr@UIGlobalInterfaceTable@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(void)
0x140360c9f  nop
0x140360ca0  cmp     [rsp+3A8h+var_1C8], rdi
0x140360ca8  jz      short loc_140360CB8
0x140360caa  lea     rcx, [rsp+3A8h+var_1C8]
0x140360cb2  call    ?unconditional_release_ref@?$com_ptr@UIGlobalInterfaceTable@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(void)
0x140360cb7  nop
0x140360cb8  lea     rax, ??_7Deploy@StoreProvider@Telemetry@Store@Windows@@6B@; const Windows::Store::Telemetry::StoreProvider::Deploy::`vftable'
0x140360cbf  mov     [rsp+3A8h+var_1A8], rax
0x140360cc7  lea     rcx, [rsp+3A8h+var_1A8]
0x140360ccf  call    ?Destroy@?$ActivityBase@VStoreProvider@Telemetry@Store@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140360cd4  lea     rcx, [rsp+3A8h+var_1A8]
0x140360cdc  call    ??1?$ActivityBase@VStoreProvider@Telemetry@Store@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x140360ce1  mov     rax, r13
0x140360ce4  jmp     loc_140362543
0x140360ce9  xorps   xmm1, xmm1
0x140360cec  movdqu  [rsp+3A8h+var_1C0], xmm1
0x140360cf5  lea     rdx, [rsp+3A8h+var_1D0]
0x140360cfd  lea     rcx, [rsp+3A8h+var_1C8]
0x140360d05  call    ?DownloadInfo@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo@UIWindowsSoftwareUpdateExecutionInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(void)
0x140360d0a  nop
0x140360d0b  cmp     [rsp+3A8h+var_1D0], rdi
0x140360d13  jz      loc_14036113C
0x140360d19  mov     r13d, edi
0x140360d1c  lea     rdx, [rsp+3A8h+Source]
0x140360d21  lea     rcx, [rsp+3A8h+var_1D0]
0x140360d29  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@U?$IVectorView@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::end(void)
0x140360d2e  cmp     r13d, dword ptr [rsp+3A8h+Source+8]
0x140360d36  jz      loc_140360F94
0x140360d3c  mov     [rsp+3A8h+var_1D8], rdi
0x140360d44  or      r12d, 4
0x140360d48  mov     dword ptr [rsp+3A8h+var_2F8], r12d
0x140360d50  mov     rcx, [rsp+3A8h+var_1D0]
0x140360d58  mov     rax, [rcx]
0x140360d5b  lea     r8, [rsp+3A8h+var_1D8]
0x140360d63  mov     edx, r13d
0x140360d66  mov     rax, [rax+30h]
0x140360d6a  call    _guard_dispatch_icall
0x140360d6f  test    eax, eax
0x140360d71  js      loc_14036256E
0x140360d77  jmp     short loc_140360D86
0x140360d79  test    eax, eax
0x140360d7b  js      loc_140362576
0x140360d81  jmp     loc_140360C3E
0x140360d86  and     r12d, 0FFFFFFFBh
0x140360d8a  or      r12d, 2
0x140360d8e  mov     [rsp+3A8h+var_308], r12d
0x140360d96  mov     dword ptr [rsp+3A8h+var_2F8], r12d
0x140360d9e  cmp     [rsp+3A8h+var_1D8], rdi
0x140360da6  jz      loc_1403610F4
0x140360dac  lea     rdx, [rsp+3A8h+lpMem]
0x140360db4  lea     rcx, [rsp+3A8h+var_1D8]
0x140360dbc  call    ?DownloadInfo@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo@UIWindowsSoftwareUpdateExecutionInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(void)
0x140360dc1  nop
0x140360dc2  xorps   xmm0, xmm0
0x140360dc5  movups  [rsp+3A8h+var_2D8], xmm0
0x140360dcd  xorps   xmm1, xmm1
0x140360dd0  movdqu  [rsp+3A8h+var_2C8], xmm1
0x140360dd9  mov     rax, [rax]
0x140360ddc  test    rax, rax
0x140360ddf  jz      short loc_140360DEB
0x140360de1  mov     rdx, [rax+10h]
0x140360de5  mov     r8d, [rax+4]
0x140360de9  jmp     short loc_140360DF5
0x140360deb  lea     rdx, psz
0x140360df2  mov     r8, rdi
0x140360df5  lea     rcx, [rsp+3A8h+var_2D8]
0x140360dfd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140360e02  lea     rax, [rsp+3A8h+var_2D8]
0x140360e0a  cmp     qword ptr [rsp+3A8h+var_2C8+8], 7
0x140360e13  cmova   rax, qword ptr [rsp+3A8h+var_2D8]
0x140360e1c  lea     rcx, [r15+90h]
0x140360e23  mov     rdx, [r15+0A0h]
0x140360e2a  cmp     qword ptr [r15+0A8h], 7
0x140360e32  jbe     short loc_140360E37
0x140360e34  mov     rcx, [rcx]
0x140360e37  mov     qword ptr [rsp+3A8h+var_318], rax
0x140360e3f  mov     rax, qword ptr [rsp+3A8h+var_2C8]
0x140360e47  mov     qword ptr [rsp+3A8h+var_318+8], rax
0x140360e4f  mov     qword ptr [rsp+3A8h+var_2E8], rcx
0x140360e57  mov     qword ptr [rsp+3A8h+var_2E8+8], rdx
0x140360e5f  lea     rdx, [rsp+3A8h+var_318]
0x140360e67  lea     rcx, [rsp+3A8h+var_2E8]
0x140360e6f  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x140360e74  mov     [rsp+3A8h+var_368], al
0x140360e78  lea     rcx, [rsp+3A8h+var_2D8]
0x140360e80  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140360e85  nop
0x140360e86  mov     rbx, [rsp+3A8h+lpMem]
0x140360e8e  test    rbx, rbx
0x140360e91  jz      short loc_140360EBE
0x140360e93  mov     ecx, esi
0x140360e95  lock xadd [rbx+18h], ecx
0x140360e9a  sub     ecx, 1
0x140360e9d  jnz     loc_1403610E7
0x140360ea3  nop
0x140360ea4  call    WINRT_IMPL_GetProcessHeap
0x140360ea9  mov     rcx, rax; hHeap
0x140360eac  mov     r8, rbx; lpMem
0x140360eaf  xor     edx, edx; dwFlags
0x140360eb1  call    WINRT_IMPL_HeapFree
0x140360eb6  mov     [rsp+3A8h+lpMem], rdi
0x140360ebe  cmp     [rsp+3A8h+var_368], dil
0x140360ec3  jz      loc_14036111D
0x140360ec9  lea     rdx, [rsp+3A8h+var_1D8]
0x140360ed1  lea     rcx, [rsp+3A8h+var_318]
0x140360ed9  call    ??$make_shared@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEAU1234567@@std@@YA?AV?$shared_ptr@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@0@AEAUAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@Z; std::make_shared<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem &>(winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem &)
0x140360ede  mov     rcx, [rax]
0x140360ee1  mov     rdx, [rax+8]
0x140360ee5  mov     [rax], rdi
0x140360ee8  mov     [rax+8], rdi
0x140360eec  mov     qword ptr [rsp+3A8h+var_1C0], rcx
0x140360ef4  mov     rbx, qword ptr [rsp+3A8h+var_1C0+8]
0x140360efc  mov     qword ptr [rsp+3A8h+var_1C0+8], rdx
0x140360f04  test    rbx, rbx
0x140360f07  jz      short loc_140360F3C
0x140360f09  mov     eax, esi
0x140360f0b  lock xadd [rbx+8], eax
0x140360f10  add     eax, esi
0x140360f12  jnz     short loc_140360F3C
0x140360f14  mov     rax, [rbx]
0x140360f17  mov     rcx, rbx
0x140360f1a  mov     rax, [rax]
0x140360f1d  call    _guard_dispatch_icall
0x140360f22  mov     eax, esi
0x140360f24  lock xadd [rbx+0Ch], eax
0x140360f29  add     eax, esi
0x140360f2b  jnz     short loc_140360F3C
0x140360f2d  mov     rax, [rbx]
0x140360f30  mov     rcx, rbx
0x140360f33  mov     rax, [rax+8]
0x140360f37  call    _guard_dispatch_icall
0x140360f3c  mov     rbx, qword ptr [rsp+3A8h+var_318+8]
0x140360f44  test    rbx, rbx
0x140360f47  jz      short loc_140360F7D
0x140360f49  mov     eax, esi
0x140360f4b  lock xadd [rbx+8], eax
0x140360f50  add     eax, esi
0x140360f52  jnz     short loc_140360F7D
0x140360f54  mov     rax, [rbx]
0x140360f57  mov     rcx, rbx
0x140360f5a  mov     rax, [rax]
0x140360f5d  call    _guard_dispatch_icall
0x140360f62  mov     eax, esi
0x140360f64  lock xadd [rbx+0Ch], eax
0x140360f69  add     eax, esi
0x140360f6b  jnz     short loc_140360F7D
0x140360f6d  mov     rax, [rbx]
0x140360f70  mov     rcx, rbx
0x140360f73  mov     rax, [rax+8]
0x140360f77  call    _guard_dispatch_icall
  ... truncated ...
```
