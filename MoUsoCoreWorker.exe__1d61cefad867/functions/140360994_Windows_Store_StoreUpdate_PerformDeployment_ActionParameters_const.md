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
  __int64 v21; // r8
  const wchar_t *v22; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  void *v26; // rbx
  int v27; // ecx
  HANDLE v28; // rax
  __int64 *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  volatile signed __int32 *v32; // rbx
  volatile signed __int32 *v33; // rbx
  struct SystemInterface::Telemetry::CorrelationVector *v34; // rbx
  volatile signed __int32 *v35; // rbx
  __int64 v36; // rbx
  bool v37; // zf
  _QWORD *v38; // rbx
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rax
  unsigned int v47; // edx
  const void *v48; // r12
  __int64 v49; // rbx
  volatile signed __int32 *v50; // r13
  __int64 v51; // r12
  volatile signed __int32 *v52; // rbx
  __int64 v53; // rdx
  int v54; // eax
  HANDLE v55; // rax
  int v56; // eax
  HANDLE v57; // rax
  __int64 v58; // rbx
  _QWORD *System; // rax
  __int64 (__fastcall *v60)(__int64, _QWORD *, __int64 *); // r12
  const wchar_t *traits_2_unsigned_short; // rax
  const char *v62; // r9
  __int64 v63; // r11
  __int64 v64; // rax
  volatile signed __int32 *v65; // r12
  volatile signed __int32 *v66; // r12
  __int64 v67; // r8
  _BYTE *v68; // r12
  char *v69; // rax
  _BYTE *v70; // r13
  _BYTE *v71; // rcx
  _BYTE *v72; // rdx
  char v73; // al
  _BYTE *v74; // rax
  __int64 v75; // rax
  int v76; // eax
  int v77; // eax
  __int64 v78; // rcx
  double v79; // xmm0_8
  __int64 v80; // rax
  unsigned __int64 v81; // r14
  __int64 v82; // rax
  unsigned __int64 v83; // rax
  const wchar_t *v84; // r9
  __int64 v85; // r15
  volatile signed __int32 *v86; // rbx
  __int64 v87; // rax
  unsigned int v88; // r12d
  char v89; // bl
  __int64 v90; // rcx
  double v91; // xmm0_8
  __int64 v92; // rax
  unsigned __int64 v93; // r12
  __int64 v94; // rax
  unsigned __int64 v95; // rsi
  struct SystemInterface::Telemetry::CorrelationVector *v96; // rbx
  __int64 *v97; // rbx
  __int64 v98; // rcx
  unsigned int v99; // r13d
  int v100; // r12d
  int v101; // eax
  __int64 *v102; // rax
  __int64 v103; // rax
  const OLECHAR *v104; // rdx
  __int64 v105; // r8
  const wchar_t *v106; // rax
  _QWORD *v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // rdx
  void *v110; // rbx
  int v111; // ecx
  HANDLE v112; // rax
  __int64 v113; // rax
  __int64 v114; // rbx
  struct SystemInterface::Telemetry::CorrelationVector *v115; // rbx
  volatile signed __int32 *v116; // rbx
  volatile signed __int32 *v117; // rbx
  struct SystemInterface::Telemetry::CorrelationVector *v118; // rbx
  int v119; // esi
  __int64 v120; // rax
  double v121; // xmm0_8
  __int64 v122; // rax
  unsigned __int64 v123; // r12
  __int64 v124; // rax
  unsigned __int64 v125; // rsi
  struct SystemInterface::Telemetry::CorrelationVector *v126; // rbx
  __int64 v127; // rcx
  double v128; // xmm0_8
  __int64 v129; // rax
  unsigned __int64 v130; // r12
  __int64 v131; // rax
  unsigned __int64 v132; // r15
  struct SystemInterface::Telemetry::CorrelationVector *v133; // rbx
  unsigned int v134; // ebx
  __int64 v135; // rax
  double v136; // xmm0_8
  __int64 v137; // rax
  unsigned __int64 v138; // r14
  __int64 v139; // rax
  unsigned __int64 v140; // rsi
  struct SystemInterface::Telemetry::CorrelationVector *v141; // rdi
  __int64 v142; // rax
  int v143; // eax
  __int64 v144; // rcx
  char v145; // [rsp+40h] [rbp-368h]
  char v146; // [rsp+40h] [rbp-368h]
  LPVOID v147; // [rsp+48h] [rbp-360h] BYREF
  __int64 v148; // [rsp+50h] [rbp-358h] BYREF
  struct Windows::Store::StoreUpdate *v149; // [rsp+58h] [rbp-350h] BYREF
  __int64 v150; // [rsp+60h] [rbp-348h]
  struct SystemInterface::Telemetry::CorrelationVector **v151; // [rsp+68h] [rbp-340h] BYREF
  int *v152; // [rsp+70h] [rbp-338h] BYREF
  void *Source[2]; // [rsp+78h] [rbp-330h] BYREF
  const wchar_t *v154; // [rsp+90h] [rbp-318h] BYREF
  __int64 v155; // [rsp+98h] [rbp-310h]
  unsigned int v156; // [rsp+A0h] [rbp-308h]
  _BYTE *v157; // [rsp+A8h] [rbp-300h] BYREF
  char *v158; // [rsp+B0h] [rbp-2F8h]
  __int64 v159; // [rsp+B8h] [rbp-2F0h] BYREF
  __int128 v160; // [rsp+C0h] [rbp-2E8h] BYREF
  __int128 v161; // [rsp+D0h] [rbp-2D8h] BYREF
  __int128 v162; // [rsp+E0h] [rbp-2C8h]
  __int128 v163; // [rsp+F0h] [rbp-2B8h] BYREF
  __int64 v164; // [rsp+100h] [rbp-2A8h]
  __int128 v165; // [rsp+110h] [rbp-298h] BYREF
  __int128 v166; // [rsp+120h] [rbp-288h]
  __int64 v167; // [rsp+130h] [rbp-278h]
  _QWORD v168[2]; // [rsp+140h] [rbp-268h] BYREF
  _QWORD v169[2]; // [rsp+150h] [rbp-258h] BYREF
  struct SystemInterface::Telemetry::CorrelationVector **v170; // [rsp+160h] [rbp-248h] BYREF
  volatile signed __int32 *v171; // [rsp+168h] [rbp-240h]
  int *v172; // [rsp+170h] [rbp-238h] BYREF
  volatile signed __int32 *v173; // [rsp+178h] [rbp-230h]
  _QWORD v174[5]; // [rsp+180h] [rbp-228h] BYREF
  winrt::hresult_error *v175; // [rsp+1A8h] [rbp-200h] BYREF
  volatile signed __int32 *v176; // [rsp+1B0h] [rbp-1F8h] BYREF
  __int64 v177; // [rsp+1D0h] [rbp-1D8h] BYREF
  __int64 v178; // [rsp+1D8h] [rbp-1D0h] BYREF
  __int64 v179; // [rsp+1E0h] [rbp-1C8h] BYREF
  __int128 v180; // [rsp+1E8h] [rbp-1C0h] BYREF
  LPVOID lpMem; // [rsp+1F8h] [rbp-1B0h] BYREF
  _OWORD v182[21]; // [rsp+200h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v151 = a3;
  v152 = a2;
  v4 = a1;
  v172 = a2;
  v168[0] = a3;
  *(_QWORD *)&v165 = a1;
  v149 = a1;
  v169[0] = a1;
  v147 = a1;
  v5 = a2;
  v150 = (__int64)a2;
  v170 = a3;
  v6 = 0;
  v156 = 0;
  LODWORD(v158) = 0;
  memset(v182, 0, sizeof(v182));
  DWORD2(v182[0]) = 0;
  BYTE12(v182[0]) = 0;
  BYTE8(v182[4]) = 0;
  LODWORD(v182[3]) = 0;
  *((_QWORD *)&v182[3] + 1) = "Deploy";
  *(_QWORD *)&v182[4] = 0;
  LODWORD(v182[5]) = 0;
  v182[15] = 0;
  memset((char *)&v182[5] + 8, 0, 0x98u);
  try
  {
    LODWORD(v182[16]) = 1;
    *((_QWORD *)&v182[16] + 1) = 0;
    *(_QWORD *)&v182[17] = (char *)v182 + 8;
    *((_QWORD *)&v182[17] + 1) = 0;
    *(_QWORD *)&v182[18] = 0;
    *((_QWORD *)&v182[18] + 1) = v182;
    *(_QWORD *)&v182[19] = 0;
    DWORD2(v182[19]) = 0;
    *(_QWORD *)&v182[20] = &v182[3];
    *(_QWORD *)&v182[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
    *((_QWORD *)&v182[20] + 1) = 0;
    Windows::Store::Telemetry::StoreProvider::Deploy::StartActivity(
      (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
      *a3,
      v4);
    winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager((winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)&v179);
    if ( !v179 )
    {
      v8 = *a3;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v182,
        2147500035LL);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
        v8,
        L"Completed",
        L"null pointer");
      *v5 = -2147467261;
      *((_BYTE *)v5 + 4) = 1;
      if ( v179 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
      *(_QWORD *)&v182[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v182);
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v182);
      return v5;
    }
    v11 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x14, v7);
    memcpy_s((void *const)(v11 + 7), 0x28u, L"MoUpdateOrchestrator", 0x28u);
    *(_QWORD *)&v163 = v11;
    *(_QWORD *)&v161 = v11;
    winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(
      (winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)&v148,
      (const struct winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)&v179,
      (const struct winrt::param::hstring *)&v161);
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
    if ( !v148 )
    {
      v14 = *v151;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v182,
        2147500035LL);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
        v14,
        L"Completed",
        L"null pointer");
      *v152 = -2147467261;
      *((_BYTE *)v5 + 4) = 1;
      if ( v148 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
      if ( v179 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
LABEL_14:
      *(_QWORD *)&v182[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v182);
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v182);
      return v5;
    }
    v180 = 0;
    winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
      &v179,
      &v178);
    if ( v178 )
    {
      v15 = 0;
      winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::end(
        &v178,
        Source);
      while ( v15 != LODWORD(Source[1]) )
      {
        v177 = 0;
        v16 = v6 | 4;
        LODWORD(v158) = v16;
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v178 + 48LL))(v178, v15, &v177);
        if ( v17 < 0 )
          winrt::throw_hresult((unsigned int)v17);
        v6 = v16 & 0xFFFFFFF9 | 2;
        v156 = v6;
        LODWORD(v158) = v6;
        if ( v177 )
        {
          v18 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
                             &v177,
                             &lpMem);
          v161 = 0;
          v162 = 0;
          v19 = *v18;
          if ( v19 )
          {
            v20 = *(const OLECHAR **)(v19 + 16);
            v21 = *(unsigned int *)(v19 + 4);
          }
          else
          {
            v20 = &psz;
            v21 = 0;
          }
          std::wstring::_Construct<1,wchar_t const *>(&v161, v20, v21);
          v22 = (const wchar_t *)&v161;
          if ( *((_QWORD *)&v162 + 1) > 7u )
            v22 = (const wchar_t *)v161;
          v23 = (_QWORD *)((char *)v4 + 144);
          v24 = *((_QWORD *)v4 + 20);
          if ( *((_QWORD *)v4 + 21) > 7u )
            v23 = (_QWORD *)*v23;
          v154 = v22;
          v155 = v162;
          *(_QWORD *)&v160 = v23;
          *((_QWORD *)&v160 + 1) = v24;
          v145 = Strings::iequals(&v160, &v154);
          std::wstring::~wstring(&v161, v25);
          v26 = lpMem;
          if ( lpMem )
          {
            v27 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
            if ( v27 )
            {
              if ( v27 < 0 )
                abort();
            }
            else
            {
              v28 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v28, 0, v26);
            }
            lpMem = 0;
          }
          if ( v145 )
          {
            v29 = (__int64 *)std::make_shared<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem &>(
                               &v154,
                               &v177);
            v30 = *v29;
            v31 = v29[1];
            *v29 = 0;
            v29[1] = 0;
            *(_QWORD *)&v180 = v30;
            v32 = (volatile signed __int32 *)*((_QWORD *)&v180 + 1);
            *((_QWORD *)&v180 + 1) = v31;
            if ( v32 )
            {
              if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
                if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
              }
            }
            v33 = (volatile signed __int32 *)v155;
            if ( v155 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v155 + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
                if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
              }
            }
            if ( v177 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v177);
            break;
          }
        }
        else
        {
          *(_QWORD *)&v163 = L"PerformDeployment Encountered null AppInstallItem - first";
          *((_QWORD *)&v163 + 1) = 57;
          SystemInterface::Log<>(&v163);
        }
        if ( v177 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v177);
        ++v15;
      }
      v5 = (int *)v150;
    }
    else
    {
      v154 = L"PerformDeployment Encountered null VectorView - first";
      v155 = 53;
      SystemInterface::Log<>(&v154);
    }
    if ( !(_QWORD)v180 )
    {
      v34 = *v151;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v182,
        0);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
        v34,
        L"Completed",
        L"removed");
      *((_DWORD *)v4 + 34) = 1;
      *v152 = 0;
      *((_BYTE *)v5 + 4) = 1;
      if ( v178 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
      v35 = (volatile signed __int32 *)*((_QWORD *)&v180 + 1);
      if ( *((_QWORD *)&v180 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v180 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
          if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
        }
      }
      if ( v148 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
      if ( v179 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
      goto LABEL_14;
    }
    v154 = (const wchar_t *)v4;
    v155 = 1;
    *(_QWORD *)&v163 = (char *)v4 + 208;
    v36 = *((_QWORD *)v4 + 26);
    if ( (unsigned int)mtx_do_lock(v36, 0) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v36 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v36 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    **((_BYTE **)v4 + 40) = 1;
    v37 = (*(_DWORD *)(v36 + 76))-- == 1;
    if ( v37 )
    {
      *(_DWORD *)(v36 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v36 + 16));
    }
    v38 = (_QWORD *)v180;
    v39 = *((_QWORD *)v4 + 41);
    v40 = 0;
    v41 = 0;
    if ( v39 )
    {
      v40 = *((_QWORD *)v4 + 40);
      _InterlockedAdd((volatile signed __int32 *)(v39 + 12), 1u);
      v41 = v39;
    }
    v42 = *((_QWORD *)v4 + 27);
    v43 = 0;
    v44 = 0;
    if ( v42 )
    {
      v43 = *((_QWORD *)v4 + 26);
      _InterlockedAdd((volatile signed __int32 *)(v42 + 12), 1u);
      v44 = v42;
    }
    v174[0] = v4;
    v174[1] = v40;
    v174[2] = v41;
    v160 = 0;
    v174[3] = v43;
    v174[4] = v44;
    *(_OWORD *)Source = 0;
    winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem_winrt::Windows::Foundation::IInspectable_::TypedEventHandler_winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem_winrt::Windows::Foundation::IInspectable___Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_2___(
      &v177,
      v174);
    lpMem = 0;
    v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(*(_QWORD *)*v38 + 128LL))(*v38, v177, &lpMem);
    if ( v45 < 0 )
      winrt::throw_hresult((unsigned int)v45);
    if ( v177 )
      winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v177);
    try
    {
      *(_QWORD *)&v166 = &v180;
      *((_QWORD *)&v166 + 1) = &lpMem;
      LOBYTE(v167) = 1;
      v46 = (*(__int64 (__fastcall **)(struct SystemInterface::Telemetry::CorrelationVector *, _QWORD *))(*(_QWORD *)*v151 + 16LL))(
              *v151,
              v174);
      v48 = (const void *)v46;
      if ( *(_QWORD *)(v46 + 24) > 7u )
        v48 = *(const void **)v46;
      v49 = *(unsigned int *)(v46 + 16);
      if ( (_DWORD)v49 )
      {
        v50 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v49, v47);
        memcpy_s((void *const)(v50 + 7), 2 * v49, v48, 2 * v49);
      }
      else
      {
        v50 = 0;
      }
      *(_QWORD *)&v160 = v50;
      *(_QWORD *)&v161 = v50;
      LODWORD(v157) = 0;
      LODWORD(v177) = 0;
      Source[0] = (char *)v4 + 144;
      if ( *((_QWORD *)v4 + 21) > 7u )
        Source[0] = *((void **)v4 + 18);
      v51 = *((unsigned int *)v4 + 40);
      if ( (_DWORD)v51 )
      {
        v52 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v51, v47);
        memcpy_s((void *const)(v52 + 7), 2 * v51, Source[0], 2 * v51);
      }
      else
      {
        v52 = 0;
      }
      Source[0] = (void *)v52;
      v176 = v52;
      winrt::impl::consume_WindowsUdk_ApplicationModel_Store_Preview_InstallControl_IAppInstallManager3<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager>::ResumeUpdates(
        (unsigned int)&v148,
        (unsigned int)&v176,
        (unsigned int)&v177,
        (unsigned int)&v157,
        (__int64)&v161);
      if ( v52 )
      {
        v54 = _InterlockedDecrement(v52 + 6);
        if ( v54 )
        {
          if ( v54 < 0 )
            abort();
        }
        else
        {
          v55 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v55, 0, (LPVOID)v52);
        }
      }
      if ( v50 )
      {
        v56 = _InterlockedDecrement(v50 + 6);
        if ( v56 )
        {
          if ( v56 < 0 )
            abort();
        }
        else
        {
          v57 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v57, 0, (LPVOID)v50);
        }
      }
      std::wstring::~wstring(v174, v53);
    }
    catch ( winrt::hresult_error *v175 )
    {
      winrt::hresult_error::to_abi(v175, &v177);
      v134 = v177;
      if ( (_DWORD)v177 == -2147467259 )
      {
        v156 = (unsigned int)v158;
        v152 = v172;
        v151 = (struct SystemInterface::Telemetry::CorrelationVector **)v168[0];
        v4 = (struct Windows::Store::StoreUpdate *)v165;
        goto LABEL_105;
      }
      v135 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
               v180,
               &v151);
      v136 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v135);
      v137 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
               v180,
               &v152);
      v138 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v137);
      v139 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
               v180,
               Source);
      v140 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v139);
      v141 = *v170;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v182,
        v134);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
        v141,
        L"Completed",
        L"failed resume",
        v140,
        v138,
        v136);
      if ( Source[0] )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
      if ( v152 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v152);
      if ( v151 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v151);
      v142 = v150;
      *(_DWORD *)v150 = v134;
      *(_BYTE *)(v142 + 4) = 1;
      (*(void (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)v180 + 136LL))(*(_QWORD *)v180, lpMem);
      wil::details::lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___::_lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___(&v154);
      if ( v178 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
      if ( v148 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
      if ( v179 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
      *(_QWORD *)&v182[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v182);
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v182);
      return (int *)v150;
    }
LABEL_105:
    v165 = 0;
    v58 = *(_QWORD *)v163;
    *(_QWORD *)&v165 = v58;
    BYTE8(v165) = 0;
    if ( (unsigned int)mtx_do_lock(v58, 0) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v58 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v58 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v165) = 1;
    while ( !*((_BYTE *)v4 + 296) )
    {
      System = (_QWORD *)SystemInterface::Service::GetSystem(&v170);
      v60 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, int **))(*(_QWORD *)*System + 40LL))(
                                                                                    *System,
                                                                                    &v172)
                                                                   + 56LL);
      LODWORD(v177) = 30;
      traits_2_unsigned_short = (const wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                                   L"StoreUpdateProgressTimeoutInMinutes",
                                                   L"failed resume",
                                                   0);
      if ( traits_2_unsigned_short == L"failed resume"
        || (v64 = traits_2_unsigned_short - L"StoreUpdateProgressTimeoutInMinutes", v64 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v62);
      }
      v168[0] = L"StoreUpdateProgressTimeoutInMinutes";
      v168[1] = v64;
      LODWORD(v157) = v60(v63, v168, &v177);
      v65 = v173;
      if ( v173 )
      {
        if ( _InterlockedExchangeAdd(v173 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
          if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
        }
      }
      v66 = v171;
      if ( v171 )
      {
        if ( _InterlockedExchangeAdd(v171 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
          if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
        }
      }
      v67 = std::_To_absolute_time<int,std::ratio<60,1>>(&v160, &v157);
      *(_QWORD *)&v163 = v67;
      v68 = (char *)v149 + 297;
      v69 = (char *)v147 + 304;
      v158 = (char *)v147 + 304;
      v70 = (char *)v147 + 304;
      while ( 1 )
      {
        v71 = v68;
        v72 = v70;
        if ( *((_BYTE *)v4 + 296)
          || (v68 = (char *)v4 + 297, v71 = (char *)v4 + 297, v72 = v69, *((_BYTE *)v4 + 297) == 1)
          || (v70 = (char *)v4 + 304, v72 = (char *)v4 + 304, *((_BYTE *)v4 + 304))
          || (v157 = (char *)v4 + 312, *((_BYTE *)v4 + 312)) )
        {
          v74 = (char *)v147 + 312;
          v157 = (char *)v147 + 312;
          v68 = v71;
          v70 = v72;
          goto LABEL_134;
        }
        if ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                             (char *)v4 + 224,
                             &v165,
                             v67) == 1 )
          break;
        v67 = v163;
        v69 = v158;
      }
      if ( *((_BYTE *)v4 + 296) || *v68 == 1 || *v70 || (v73 = 0, *v157) )
        v73 = 1;
      if ( !v73 )
      {
        LODWORD(Source[0]) = 1;
        BYTE4(Source[0]) = 1;
        *(void **)((char *)v4 + 300) = Source[0];
        *(_QWORD *)&v163 = L"Deploy timeout";
        *((_QWORD *)&v163 + 1) = 14;
        LOBYTE(v164) = 1;
        v161 = v163;
        *(_QWORD *)&v162 = v164;
        Windows::Store::StoreUpdate::LogAppInstallCurrentStatus(v4, v180, &v161);
        v68 = (char *)v149 + 297;
        v70 = v158;
      }
      v74 = v157;
LABEL_134:
      *v68 = 0;
      if ( *v70 || *v74 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_StoreLoopFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_StoreLoopFixes>::GetImpl'::`2'::impl) )
        {
          v75 = **(_QWORD **)v180;
          if ( *v157 )
          {
            v76 = (*(__int64 (**)(void))(v75 + 96))();
            if ( v76 < 0 )
              winrt::throw_hresult((unsigned int)v76);
          }
          else
          {
            v77 = (*(__int64 (**)(void))(v75 + 88))();
            if ( v77 < 0 )
              winrt::throw_hresult((unsigned int)v77);
          }
        }
        v78 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                v180,
                Source);
        v79 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v78);
        v80 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                v180,
                &v149);
        v81 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v80);
        v82 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                v180,
                &v147);
        v83 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v82);
        v84 = L"aborted";
        if ( *(_BYTE *)(v169[0] + 312LL) )
          v84 = L"paused";
        Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
          (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
          *v151,
          L"Aborted",
          v84,
          v83,
          v81,
          v79);
        if ( v147 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
        if ( v149 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v149);
        if ( Source[0] )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
        v85 = v150;
        *(_BYTE *)(v150 + 4) = 0;
        v37 = (*(_DWORD *)(v58 + 76))-- == 1;
        if ( v37 )
        {
          *(_DWORD *)(v58 + 72) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)(v58 + 16));
        }
        (*(void (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)v166 + 136LL))(
          **(_QWORD **)v166,
          **((_QWORD **)&v166 + 1));
        wil::details::lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___::_lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___(&v154);
        if ( v178 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
        v86 = (volatile signed __int32 *)*((_QWORD *)&v180 + 1);
        if ( *((_QWORD *)&v180 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v180 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
            if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
          }
        }
        if ( v148 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
        if ( v179 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
        goto LABEL_276;
      }
    }
    v37 = (*(_DWORD *)(v58 + 76))-- == 1;
    if ( v37 )
    {
      *(_DWORD *)(v58 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v58 + 16));
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)v166 + 136LL))(**(_QWORD **)v166, **((_QWORD **)&v166 + 1));
    wil::details::lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___::_lambda_call__Windows::Store::StoreUpdate::PerformDeployment_::_30_::_lambda_1___(&v154);
    if ( *((_BYTE *)v4 + 296) )
    {
      v87 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v180,
              &v147);
      v88 = v156 | 1;
      LODWORD(v158) = v156 | 1;
      if ( *(int *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::ErrorCode(
                     v87,
                     &v177) >= 0 )
      {
        v89 = 1;
        goto LABEL_170;
      }
    }
    else
    {
      v88 = v156;
    }
    v89 = 0;
LABEL_170:
    if ( (v88 & 1) != 0 )
    {
      v88 &= ~1u;
      if ( v147 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
    }
    if ( v89 )
    {
      v90 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v180,
              Source);
      v91 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v90);
      v92 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v180,
              &v149);
      v93 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v92);
      v94 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
              v180,
              &v147);
      v95 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v94);
      v96 = *v151;
      wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v182,
        0);
      Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
        (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
        v96,
        L"Completed",
        L"succeeded",
        v95,
        v93,
        v91);
      if ( v147 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
      if ( v149 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v149);
      if ( Source[0] )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
      *((_DWORD *)v4 + 34) = 1;
      *v152 = 0;
      v85 = v150;
      *(_BYTE *)(v150 + 4) = 1;
      if ( v178 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
      if ( v148 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
      if ( v179 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
    }
    else
    {
      v160 = 0;
      v97 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
                         &v179,
                         &v147);
      if ( &v178 != v97 )
      {
        if ( v178 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
        v98 = *v97;
        *v97 = 0;
        v178 = v98;
      }
      if ( v147 )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
      if ( v178 )
      {
        v99 = 0;
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::end(
          &v178,
          &v165);
        while ( v99 != DWORD2(v165) )
        {
          v177 = 0;
          v100 = v88 | 0x10;
          LODWORD(v158) = v100;
          v101 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v178 + 48LL))(v178, v99, &v177);
          if ( v101 < 0 )
            winrt::throw_hresult((unsigned int)v101);
          v88 = v100 & 0xFFFFFFE7 | 8;
          if ( v177 )
          {
            v102 = (__int64 *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DownloadInfo(
                                &v177,
                                &v147);
            v161 = 0;
            v162 = 0;
            v103 = *v102;
            if ( v103 )
            {
              v104 = *(const OLECHAR **)(v103 + 16);
              v105 = *(unsigned int *)(v103 + 4);
            }
            else
            {
              v104 = &psz;
              v105 = 0;
            }
            std::wstring::_Construct<1,wchar_t const *>(&v161, v104, v105);
            v106 = (const wchar_t *)&v161;
            if ( *((_QWORD *)&v162 + 1) > 7u )
              v106 = (const wchar_t *)v161;
            v107 = (_QWORD *)((char *)v4 + 144);
            v108 = *((_QWORD *)v4 + 20);
            if ( *((_QWORD *)v4 + 21) > 7u )
              v107 = (_QWORD *)*v107;
            v154 = v106;
            v155 = v162;
            v169[0] = v107;
            v169[1] = v108;
            v146 = Strings::iequals(v169, &v154);
            std::wstring::~wstring(&v161, v109);
            v110 = v147;
            if ( v147 )
            {
              v111 = _InterlockedDecrement((volatile signed __int32 *)v147 + 6);
              if ( v111 )
              {
                if ( v111 < 0 )
                  abort();
              }
              else
              {
                v112 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v112, 0, v110);
              }
              v147 = 0;
            }
            if ( v146 )
            {
              v113 = std::make_shared<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem &>(
                       &v154,
                       &v177);
              std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v160, v113);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v154);
              if ( v177 )
                winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v177);
              break;
            }
          }
          else
          {
            *(_QWORD *)&v163 = L"PerformDeployment Encountered null AppInstallItem - second";
            *((_QWORD *)&v163 + 1) = 58;
            SystemInterface::Log<>(&v163);
          }
          if ( v177 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v177);
          ++v99;
        }
      }
      else
      {
        v154 = L"PerformDeployment Encountered null VectorView - second";
        v155 = 54;
        SystemInterface::Log<>(&v154);
      }
      v114 = v160;
      if ( (_QWORD)v160 )
      {
        *(_QWORD *)&v166 = L"StoreProvider Deploy action failed";
        *((_QWORD *)&v166 + 1) = 34;
        LOBYTE(v167) = 1;
        v161 = v166;
        *(_QWORD *)&v162 = v167;
        Windows::Store::StoreUpdate::LogAppInstallCurrentStatus(v4, v160, &v161);
        winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
          v114,
          &v159);
        if ( v159 )
        {
          v119 = *(_DWORD *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::ErrorCode(
                              &v159,
                              &v177);
          if ( *((_BYTE *)v4 + 296) && v119 >= 0 )
          {
            v120 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v114,
                     Source);
            v121 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v120);
            v122 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v114,
                     &v149);
            v123 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v122);
            v124 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v114,
                     &v147);
            v125 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v124);
            v126 = *v151;
            wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
              v182,
              0);
            Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
              (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
              v126,
              L"Completed",
              L"succeeded post refresh",
              v125,
              v123,
              v121);
            if ( v147 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
            if ( v149 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v149);
            if ( Source[0] )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
            *((_DWORD *)v4 + 34) = 1;
            *v152 = 0;
            v85 = v150;
            *(_BYTE *)(v150 + 4) = 1;
            if ( v159 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v159);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v160);
            if ( v178 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
            if ( v148 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
            if ( v179 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
          }
          else
          {
            v127 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v114,
                     Source);
            v128 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(v127);
            v129 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v114,
                     &v149);
            v130 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::DownloadSizeInBytes(v129);
            v131 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdate<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::Description(
                     v114,
                     &v147);
            v132 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::BytesDownloaded(v131);
            v133 = *v151;
            wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
              v182,
              (unsigned int)v119);
            Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
              (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
              v133,
              L"Completed",
              L"failed",
              v132,
              v130,
              v128);
            if ( v147 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v147);
            if ( v149 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v149);
            if ( Source[0] )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Source);
            *v152 = v119;
            v85 = v150;
            *(_BYTE *)(v150 + 4) = 1;
            if ( v159 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v159);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v160);
            if ( v178 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
            if ( v148 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
            if ( v179 )
              winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
          }
        }
        else
        {
          v118 = *v151;
          wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
            v182,
            2147500035LL);
          Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
            (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
            v118,
            L"Completed",
            L"null pointer");
          *v152 = -2147467261;
          v85 = v150;
          *(_BYTE *)(v150 + 4) = 1;
          if ( v159 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v159);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v160);
          if ( v178 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
          if ( v148 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
          if ( v179 )
            winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
        }
      }
      else
      {
        v115 = *v151;
        wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
          v182,
          0);
        Windows::Store::Telemetry::StoreProvider::Deploy::Stop(
          (Windows::Store::Telemetry::StoreProvider::Deploy *)v182,
          v115,
          L"Completed",
          L"removed");
        *((_DWORD *)v4 + 34) = 1;
        *v152 = 0;
        v85 = v150;
        *(_BYTE *)(v150 + 4) = 1;
        v116 = (volatile signed __int32 *)*((_QWORD *)&v160 + 1);
        if ( *((_QWORD *)&v160 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v160 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v116)(v116);
            if ( _InterlockedExchangeAdd(v116 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v116 + 8LL))(v116);
          }
        }
        if ( v178 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v178);
        v117 = (volatile signed __int32 *)*((_QWORD *)&v180 + 1);
        if ( *((_QWORD *)&v180 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v180 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v117)(v117);
            if ( _InterlockedExchangeAdd(v117 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v117 + 8LL))(v117);
          }
        }
        if ( v148 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v148);
        if ( v179 )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(&v179);
      }
    }
LABEL_276:
    *(_QWORD *)&v182[0] = &Windows::Store::Telemetry::StoreProvider::Deploy::`vftable';
    wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v182);
    wil::ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Store::Telemetry::StoreProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v182);
    result = (int *)v85;
  }
  catch ( ... )
  {
    v143 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x23D,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\StoreProvider\\StoreUpdate.cpp",
             v9);
    v144 = v150;
    *(_DWORD *)v150 = v143;
    *(_BYTE *)(v144 + 4) = 1;
    return (int *)v150;
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
