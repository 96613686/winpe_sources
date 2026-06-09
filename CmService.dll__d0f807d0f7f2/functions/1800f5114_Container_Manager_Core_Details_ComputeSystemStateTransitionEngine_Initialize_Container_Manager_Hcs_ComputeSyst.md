# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Initialize(Container::Manager::Hcs::ComputeSystem *,Container::Manager::Hcs::ComputeSystemConfiguration,Container::Manager::Core::Details::SiloSettings,void (*)(Container::Manager::Core::Details::ComputeSystemState const &,long,void *),void (*)(Container::Manager::Core::Details::ComputeSystemState const &,long,void *),void *)

- ea: `0x1800f5114`
- end: `0x1800f5f9f`
- name: `?Initialize@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@QEAAJPEAVComputeSystem@Hcs@45@UComputeSystemConfiguration@745@USiloSettings@2345@P6AXAEBUComputeSystemState@2345@JPEAX@Z54@Z`
- size: `3723`
- prototype: `int __high(struct Container::Manager::Hcs::ComputeSystem *, struct Container::Manager::Hcs::ComputeSystemConfiguration, struct Container::Manager::Core::Details::SiloSettings, void (__high *)(const struct Container::Manager::Core::Details::ComputeSystemState *, int, void *), void (__high *)(const struct Container::Manager::Core::Details::ComputeSystemState *, int, void *), void *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a24bc`
- `0x1800f0078`

## callees

- `0x180004bf4`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x180016658`
- `0x180023b68`
- `0x180023bec`
- `0x1800262e4`
- `0x18002e2b4`
- `0x180061a7c`
- `0x180066670`
- `0x180080880`
- `0x180080980`
- `0x180080b98`
- `0x18008d0d8`
- `0x18008d534`
- `0x180099858`
- `0x1800f5114`
- `0x1801011d8`
- `0x180101b20`
- `0x180101c1c`
- `0x180125ad4`
- `0x180125bb0`
- `0x180125c2c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f5593`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f5593`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5711`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5830`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5a3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5711`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5830`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f522a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f52a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f52c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5352`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f552e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f554c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f55f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f56e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f574b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f586a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f58a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5a1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5a74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5ab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5b60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5ca9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5cc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f522a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f52a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f52c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5352`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f552e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f554c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f55f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f56e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f574b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f586a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f58a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5a1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5a74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5ab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5b60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5ca9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5cc7`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Initialize(
        void *a1,
        __int64 a2,
        Container::Manager::Hcs::ComputeSystemConfiguration *a3,
        _BYTE *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v10; // eax
  unsigned int LastError; // ebx
  unsigned int v12; // r8d
  const char *v13; // r9
  _BYTE *v14; // rcx
  bool v15; // zf
  int v17; // eax
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  int v22; // eax
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  _QWORD *v29; // rax
  _QWORD *v30; // rdi
  int v31; // eax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  _QWORD *v38; // rax
  _QWORD *v39; // r13
  int v40; // eax
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  unsigned int v45; // r8d
  const char *v46; // r9
  _QWORD *v47; // rax
  _QWORD *v48; // r12
  int v49; // eax
  unsigned int v50; // r8d
  const char *v51; // r9
  unsigned int v52; // r8d
  const char *v53; // r9
  unsigned int v54; // r8d
  const char *v55; // r9
  const char *v56; // r9
  struct _TP_TIMER *v57; // rbx
  unsigned int v58; // r8d
  const char *v59; // r9
  unsigned int v60; // r8d
  const char *v61; // r9
  unsigned int v62; // r8d
  const char *v63; // r9
  __int64 v64; // rax
  int v65; // eax
  unsigned int v66; // esi
  unsigned int v67; // r8d
  const char *v68; // r9
  unsigned int v69; // r8d
  const char *v70; // r9
  unsigned int v71; // r8d
  const char *v72; // r9
  _BYTE *v73; // rcx
  bool v74; // zf
  int JobObject; // eax
  unsigned int v76; // r8d
  const char *v77; // r9
  unsigned int v78; // r8d
  const char *v79; // r9
  unsigned int v80; // r8d
  const char *v81; // r9
  _QWORD *v82; // rbx
  unsigned int v83; // r8d
  const char *v84; // r9
  unsigned int v85; // r8d
  const char *v86; // r9
  unsigned int v87; // r8d
  const char *v88; // r9
  unsigned int v89; // r8d
  const char *v90; // r9
  unsigned int v91; // r8d
  const char *v92; // r9
  unsigned int v93; // r8d
  const char *v94; // r9
  _BYTE *v95; // rcx
  bool v96; // zf
  unsigned int v97; // r8d
  const char *v98; // r9
  unsigned int v99; // r8d
  const char *v100; // r9
  unsigned int v101; // r8d
  const char *v102; // r9
  unsigned int v103; // r8d
  const char *v104; // r9
  unsigned int v105; // r8d
  const char *v106; // r9
  unsigned int v107; // r8d
  const char *v108; // r9
  int v109; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v111; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v112; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v113; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v114; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v115; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v116; // [rsp+60h] [rbp-A0h] BYREF
  PVOID pv; // [rsp+68h] [rbp-98h]
  PTP_TIMER pti; // [rsp+70h] [rbp-90h] BYREF
  __int64 v119; // [rsp+78h] [rbp-88h]
  __int64 v120; // [rsp+80h] [rbp-80h] BYREF
  __int16 v121; // [rsp+88h] [rbp-78h]
  char v122; // [rsp+8Ah] [rbp-76h]
  int v123; // [rsp+90h] [rbp-70h]
  __int128 v124; // [rsp+98h] [rbp-68h] BYREF
  __int128 v125; // [rsp+A8h] [rbp-58h]
  _BYTE v126[88]; // [rsp+B8h] [rbp-48h] BYREF
  char v127; // [rsp+110h] [rbp+10h]
  HANDLE v128; // [rsp+118h] [rbp+18h]
  _BYTE v129[208]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v119 = a2;
  pv = a1;
  hObject = 0;
  v10 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &hObject,
          1);
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v10,
      v109);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
LABEL_4:
    Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
    if ( a4[128] )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
    v14 = a4 + 8;
    v15 = a4[32] == 0;
LABEL_7:
    if ( !v15 )
      utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(v14);
    return LastError;
  }
  v111 = 0;
  v17 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &v111,
          0);
  LastError = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v17,
      v109);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    goto LABEL_4;
  }
  v112 = 0;
  v22 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &v112,
          0);
  LastError = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v22,
      v109);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    goto LABEL_4;
  }
  v29 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v30 = v29;
  if ( !v29 )
  {
    v113 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)0x8007000ELL,
      v109);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v103, v104);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v105, v106);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v107, v108);
    goto LABEL_129;
  }
  *v29 = 0;
  v29[1] = 0;
  v29[2] = 0;
  v113 = v29;
  v31 = Container::Manager::Hcs::ComputeSystem::WatchForExit(a2, v29);
  LastError = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v31,
      v109);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
    goto LABEL_4;
  }
  v38 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v39 = v38;
  if ( !v38 )
  {
    v114 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)0x8007000ELL,
      v109);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v97, v98);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v99, v100);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v101, v102);
LABEL_129:
    Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
    if ( a4[128] )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
    v95 = a4 + 8;
    v96 = a4[32] == 0;
    goto LABEL_132;
  }
  *v38 = 0;
  v38[1] = 0;
  v38[2] = 0;
  v114 = v38;
  v40 = Container::Manager::Hcs::ComputeSystem::WatchForCrash(a2, v38);
  LastError = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v40,
      v109);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v42);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v45, v46);
    goto LABEL_4;
  }
  v47 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v48 = v47;
  if ( !v47 )
  {
    v115 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)0x8007000ELL,
      v109);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v115, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v89, v90);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v91, v92);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v93, v94);
    Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
    if ( a4[128] )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
    v95 = a4 + 8;
    v96 = a4[32] == 0;
LABEL_132:
    if ( !v96 )
      utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(v95);
    return 2147942414LL;
  }
  *v47 = 0;
  v47[1] = 0;
  v47[2] = 0;
  v115 = v47;
  v49 = Container::Manager::Hcs::ComputeSystem::WatchForCrashDumpCollectionCompletion(a2, v47);
  LastError = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v49,
      v109);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v115, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v50, v51);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v52, v53);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v54, v55);
LABEL_50:
    Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
    if ( a4[128] )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
    v14 = a4 + 8;
    v15 = a4[32] == 0;
    goto LABEL_7;
  }
  pti = CreateThreadpoolTimer(
          Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::OnComputeSystemTerminateTimer,
          pv,
          0);
  v57 = pti;
  if ( !pti )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCD,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
                  v56);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v115, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v58, v59);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v60, v61);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v62, v63);
    goto LABEL_50;
  }
  v121 = 0;
  v120 = 0;
  v124 = 0;
  v125 = 0;
  v122 = 0;
  v123 = 0;
  LOBYTE(v124) = 0;
  BYTE8(v125) = 0;
  memset_0(v126, 0, 0x60u);
  v126[0] = 0;
  v127 = 0;
  v128 = 0;
  v64 = Container::Manager::Core::Details::SiloSettings::SiloSettings(v129, a4);
  v65 = Container::Manager::Core::Details::Silo::Initialize(&v120, *((_QWORD *)a3 + 32), v64);
  v66 = v65;
  if ( v65 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v65,
      v109);
    if ( (char *)v128 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v128);
    if ( v127 )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)v126);
    if ( BYTE8(v125) )
      utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(&v124);
    CloseThreadpoolTimer(v57);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v115, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v67, v68);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v69, v70);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v71, v72);
    Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
    if ( a4[128] )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
    v73 = a4 + 8;
    v74 = a4[32] == 0;
LABEL_77:
    if ( !v74 )
      utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(v73);
    return v66;
  }
  v116 = 0;
  JobObject = Container::Manager::Core::Details::Silo::GetJobObject(&v120, 6, &v116);
  v66 = JobObject;
  if ( JobObject < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)JobObject,
      v109);
    if ( (char *)v116 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v116);
    Container::Manager::Core::Details::Silo::~Silo((Container::Manager::Core::Details::Silo *)&v120);
    CloseThreadpoolTimer(v57);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v115, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
    if ( v112 && !CloseHandle(v112) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v76, v77);
    if ( v111 && !CloseHandle(v111) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v78, v79);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v80, v81);
    Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
    if ( a4[128] )
      Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
    v73 = a4 + 8;
    v74 = a4[32] == 0;
    goto LABEL_77;
  }
  v82 = pv;
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    (char *)pv + 104,
    &hObject);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    v82 + 14,
    &v111);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    v82 + 15,
    &v112);
  v82[20] = v119;
  Container::Manager::Hcs::ComputeSystemConfiguration::operator=(v82 + 21, a3);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    v82 + 180,
    &v116);
  v113 = 0;
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v82 + 181, v30);
  v114 = 0;
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v82 + 182, v39);
  v115 = 0;
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v82 + 184, v48);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(
    v82 + 185,
    &pti);
  v82[188] = a5;
  v82[189] = a6;
  v82[190] = a7;
  Container::Manager::Core::Details::Silo::operator=(v82 + 191, &v120);
  Csl::AsyncOperation<void>::SetCompletionCallback(
    v82[181],
    Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::OnComputeSystemExited,
    v82);
  Csl::AsyncOperation<void>::SetCompletionCallback(
    v82[182],
    Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::OnComputeSystemCrashed,
    v82);
  Csl::AsyncOperation<void>::SetCompletionCallback(
    v82[184],
    Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::OnComputeSystemCrashDumpCollected,
    v82);
  if ( (char *)v116 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v116);
  Container::Manager::Core::Details::Silo::~Silo((Container::Manager::Core::Details::Silo *)&v120);
  if ( pti )
    CloseThreadpoolTimer(pti);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v115, 0);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v114, 0);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v113, 0);
  if ( v112 && !CloseHandle(v112) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v83, v84);
  if ( v111 && !CloseHandle(v111) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v85, v86);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v87, v88);
  Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(a3);
  if ( a4[128] )
    Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(a4 + 40));
  if ( a4[32] )
    utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(a4 + 8);
  return 0;
}

```

## disassembly

```asm
0x1800f5114  push    rbp
0x1800f5116  push    rbx
0x1800f5117  push    rsi
0x1800f5118  push    rdi
0x1800f5119  push    r12
0x1800f511b  push    r13
0x1800f511d  push    r14
0x1800f511f  push    r15
0x1800f5121  lea     rbp, [rsp-0B8h]
0x1800f5129  sub     rsp, 1B8h
0x1800f5130  xor     r12d, r12d
0x1800f5133  mov     [rsp+1F0h+var_178], rdx
0x1800f5138  mov     r14, r9
0x1800f513b  mov     [rsp+1F0h+pv], rcx
0x1800f5140  mov     rsi, rdx
0x1800f5143  mov     [rsp+1F0h+hObject], r12
0x1800f5148  xor     r9d, r9d
0x1800f514b  lea     rcx, [rsp+1F0h+hObject]
0x1800f5150  lea     edx, [r12+1]
0x1800f5155  mov     r15, r8
0x1800f5158  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800f515d  mov     ebx, eax
0x1800f515f  test    eax, eax
0x1800f5161  jns     short loc_1800F51C9
0x1800f5163  mov     rcx, [rbp+0F8h]; this
0x1800f516a  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f5171  mov     r9d, eax; char *
0x1800f5174  mov     edx, 0A3h; void *
0x1800f5179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f517e  mov     rcx, [rsp+1F0h+hObject]; hObject
0x1800f5183  test    rcx, rcx
0x1800f5186  jz      short loc_1800F519C
0x1800f5188  call    cs:__imp_CloseHandle
0x1800f518f  nop     dword ptr [rax+rax+00h]
0x1800f5194  test    eax, eax
0x1800f5196  jz      loc_1800F5D95
0x1800f519c  mov     rcx, r15; this
0x1800f519f  call    ??1ComputeSystemConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(void)
0x1800f51a4  lea     rcx, [r14+28h]; this
0x1800f51a8  cmp     [rcx+58h], r12b
0x1800f51ac  jz      short loc_1800F51B3
0x1800f51ae  call    ??1BindingSettings@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BindingSettings::~BindingSettings(void)
0x1800f51b3  lea     rcx, [r14+8]
0x1800f51b7  cmp     [rcx+18h], r12b
0x1800f51bb  jz      short loc_1800F51C2
0x1800f51bd  call    ??1?$vector@UWcifsInstanceSettings@Details@Core@Manager@Container@@V?$allocator@UWcifsInstanceSettings@Details@Core@Manager@Container@@@utl@@@utl@@QEAA@XZ; utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(void)
0x1800f51c2  mov     eax, ebx
0x1800f51c4  jmp     loc_1800F5D02
0x1800f51c9  xor     r9d, r9d
0x1800f51cc  mov     [rsp+1F0h+var_1B8], r12
0x1800f51d1  xor     edx, edx
0x1800f51d3  lea     rcx, [rsp+1F0h+var_1B8]
0x1800f51d8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800f51dd  mov     ebx, eax
0x1800f51df  test    eax, eax
0x1800f51e1  jns     short loc_1800F5243
0x1800f51e3  mov     rcx, [rbp+0F8h]; this
0x1800f51ea  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f51f1  mov     r9d, eax; char *
0x1800f51f4  mov     edx, 0A7h; void *
0x1800f51f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f51fe  mov     rcx, [rsp+1F0h+var_1B8]; hObject
0x1800f5203  test    rcx, rcx
0x1800f5206  jz      short loc_1800F521C
0x1800f5208  call    cs:__imp_CloseHandle
0x1800f520f  nop     dword ptr [rax+rax+00h]
0x1800f5214  test    eax, eax
0x1800f5216  jz      loc_1800F5DA7
0x1800f521c  mov     rcx, [rsp+1F0h+hObject]; hObject
0x1800f5221  test    rcx, rcx
0x1800f5224  jz      loc_1800F519C
0x1800f522a  call    cs:__imp_CloseHandle
0x1800f5231  nop     dword ptr [rax+rax+00h]
0x1800f5236  test    eax, eax
0x1800f5238  jz      loc_1800F5D29
0x1800f523e  jmp     loc_1800F519C
0x1800f5243  xor     r9d, r9d
0x1800f5246  mov     [rsp+1F0h+var_1B0], r12
0x1800f524b  xor     edx, edx
0x1800f524d  lea     rcx, [rsp+1F0h+var_1B0]
0x1800f5252  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800f5257  mov     ebx, eax
0x1800f5259  test    eax, eax
0x1800f525b  jns     short loc_1800F52DB
0x1800f525d  mov     rcx, [rbp+0F8h]; this
0x1800f5264  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f526b  mov     r9d, eax; char *
0x1800f526e  mov     edx, 0ACh; void *
0x1800f5273  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5278  mov     rcx, [rsp+1F0h+var_1B0]; hObject
0x1800f527d  test    rcx, rcx
0x1800f5280  jz      short loc_1800F5296
0x1800f5282  call    cs:__imp_CloseHandle
0x1800f5289  nop     dword ptr [rax+rax+00h]
0x1800f528e  test    eax, eax
0x1800f5290  jz      loc_1800F5DB9
0x1800f5296  mov     rcx, [rsp+1F0h+var_1B8]; hObject
0x1800f529b  test    rcx, rcx
0x1800f529e  jz      short loc_1800F52B4
0x1800f52a0  call    cs:__imp_CloseHandle
0x1800f52a7  nop     dword ptr [rax+rax+00h]
0x1800f52ac  test    eax, eax
0x1800f52ae  jz      loc_1800F5DCB
0x1800f52b4  mov     rcx, [rsp+1F0h+hObject]; hObject
0x1800f52b9  test    rcx, rcx
0x1800f52bc  jz      loc_1800F519C
0x1800f52c2  call    cs:__imp_CloseHandle
0x1800f52c9  nop     dword ptr [rax+rax+00h]
0x1800f52ce  test    eax, eax
0x1800f52d0  jz      loc_1800F5D3B
0x1800f52d6  jmp     loc_1800F519C
0x1800f52db  mov     r13d, 18h
0x1800f52e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f52e8  mov     ecx, r13d; unsigned __int64
0x1800f52eb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f52f0  mov     rdi, rax
0x1800f52f3  test    rax, rax
0x1800f52f6  jz      loc_1800F5C52
0x1800f52fc  mov     rdx, rax
0x1800f52ff  mov     [rax], r12
0x1800f5302  mov     rcx, rsi
0x1800f5305  mov     [rax+8], r12
0x1800f5309  mov     [rax+10h], r12
0x1800f530d  mov     [rsp+1F0h+var_1A8], rax
0x1800f5312  call    ?WatchForExit@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::WatchForExit(Csl::AsyncOperation<void> &)
0x1800f5317  mov     ebx, eax
0x1800f5319  test    eax, eax
0x1800f531b  jns     loc_1800F53AB
0x1800f5321  mov     rcx, [rbp+0F8h]; this
0x1800f5328  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f532f  mov     r9d, eax; char *
0x1800f5332  mov     edx, 0B4h; void *
0x1800f5337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f533c  xor     edx, edx
0x1800f533e  lea     rcx, [rsp+1F0h+var_1A8]
0x1800f5343  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f5348  mov     rcx, [rsp+1F0h+var_1B0]; hObject
0x1800f534d  test    rcx, rcx
0x1800f5350  jz      short loc_1800F5366
0x1800f5352  call    cs:__imp_CloseHandle
0x1800f5359  nop     dword ptr [rax+rax+00h]
0x1800f535e  test    eax, eax
0x1800f5360  jz      loc_1800F5DDD
0x1800f5366  mov     rcx, [rsp+1F0h+var_1B8]; hObject
0x1800f536b  test    rcx, rcx
0x1800f536e  jz      short loc_1800F5384
0x1800f5370  call    cs:__imp_CloseHandle
0x1800f5377  nop     dword ptr [rax+rax+00h]
0x1800f537c  test    eax, eax
0x1800f537e  jz      loc_1800F5DEF
0x1800f5384  mov     rcx, [rsp+1F0h+hObject]; hObject
0x1800f5389  test    rcx, rcx
0x1800f538c  jz      loc_1800F519C
0x1800f5392  call    cs:__imp_CloseHandle
0x1800f5399  nop     dword ptr [rax+rax+00h]
0x1800f539e  test    eax, eax
0x1800f53a0  jz      loc_1800F5D4D
0x1800f53a6  jmp     loc_1800F519C
0x1800f53ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f53b2  mov     rcx, r13; unsigned __int64
0x1800f53b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f53ba  mov     r13, rax
0x1800f53bd  test    rax, rax
0x1800f53c0  jz      loc_1800F5BB4
0x1800f53c6  mov     rdx, rax
0x1800f53c9  mov     [rax], r12
0x1800f53cc  mov     rcx, rsi
0x1800f53cf  mov     [rax+8], r12
0x1800f53d3  mov     [rax+10h], r12
0x1800f53d7  mov     [rsp+1F0h+var_1A0], rax
0x1800f53dc  call    ?WatchForCrash@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::WatchForCrash(Csl::AsyncOperation<void> &)
0x1800f53e1  mov     ebx, eax
0x1800f53e3  test    eax, eax
0x1800f53e5  jns     loc_1800F5481
0x1800f53eb  mov     rcx, [rbp+0F8h]; this
0x1800f53f2  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f53f9  mov     r9d, eax; char *
0x1800f53fc  mov     edx, 0BCh; void *
0x1800f5401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5406  xor     edx, edx
0x1800f5408  lea     rcx, [rsp+1F0h+var_1A0]
0x1800f540d  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f5412  xor     edx, edx
0x1800f5414  lea     rcx, [rsp+1F0h+var_1A8]
0x1800f5419  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f541e  mov     rcx, [rsp+1F0h+var_1B0]; hObject
0x1800f5423  test    rcx, rcx
0x1800f5426  jz      short loc_1800F543C
0x1800f5428  call    cs:__imp_CloseHandle
0x1800f542f  nop     dword ptr [rax+rax+00h]
0x1800f5434  test    eax, eax
0x1800f5436  jz      loc_1800F5E01
0x1800f543c  mov     rcx, [rsp+1F0h+var_1B8]; hObject
0x1800f5441  test    rcx, rcx
0x1800f5444  jz      short loc_1800F545A
0x1800f5446  call    cs:__imp_CloseHandle
0x1800f544d  nop     dword ptr [rax+rax+00h]
0x1800f5452  test    eax, eax
0x1800f5454  jz      loc_1800F5E13
0x1800f545a  mov     rcx, [rsp+1F0h+hObject]; hObject
0x1800f545f  test    rcx, rcx
0x1800f5462  jz      loc_1800F519C
0x1800f5468  call    cs:__imp_CloseHandle
0x1800f546f  nop     dword ptr [rax+rax+00h]
0x1800f5474  test    eax, eax
0x1800f5476  jz      loc_1800F5D5F
0x1800f547c  jmp     loc_1800F519C
0x1800f5481  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f5488  mov     ecx, 18h; unsigned __int64
0x1800f548d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f5492  xor     ebx, ebx
0x1800f5494  mov     r12, rax
0x1800f5497  test    rax, rax
0x1800f549a  jz      loc_1800F5AF1
0x1800f54a0  mov     rdx, rax
0x1800f54a3  mov     [rax], rbx
0x1800f54a6  mov     rcx, rsi
0x1800f54a9  mov     [rax+8], rbx
0x1800f54ad  mov     [rax+10h], rbx
0x1800f54b1  mov     [rsp+1F0h+var_198], rax
0x1800f54b6  call    ?WatchForCrashDumpCollectionCompletion@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::WatchForCrashDumpCollectionCompletion(Csl::AsyncOperation<void> &)
0x1800f54bb  xor     esi, esi
0x1800f54bd  mov     ebx, eax
0x1800f54bf  test    eax, eax
0x1800f54c1  jns     loc_1800F5584
0x1800f54c7  mov     rcx, [rbp+0F8h]; this
0x1800f54ce  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f54d5  mov     r9d, eax; char *
0x1800f54d8  mov     edx, 0C5h; void *
0x1800f54dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f54e2  xor     edx, edx
0x1800f54e4  lea     rcx, [rsp+1F0h+var_198]
0x1800f54e9  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f54ee  xor     edx, edx
0x1800f54f0  lea     rcx, [rsp+1F0h+var_1A0]
0x1800f54f5  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f54fa  xor     edx, edx
0x1800f54fc  lea     rcx, [rsp+1F0h+var_1A8]
0x1800f5501  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f5506  mov     rcx, [rsp+1F0h+var_1B0]; hObject
0x1800f550b  test    rcx, rcx
0x1800f550e  jz      short loc_1800F5524
0x1800f5510  call    cs:__imp_CloseHandle
0x1800f5517  nop     dword ptr [rax+rax+00h]
0x1800f551c  test    eax, eax
0x1800f551e  jz      loc_1800F5E25
0x1800f5524  mov     rcx, [rsp+1F0h+var_1B8]; hObject
0x1800f5529  test    rcx, rcx
0x1800f552c  jz      short loc_1800F5542
0x1800f552e  call    cs:__imp_CloseHandle
0x1800f5535  nop     dword ptr [rax+rax+00h]
0x1800f553a  test    eax, eax
0x1800f553c  jz      loc_1800F5E37
0x1800f5542  mov     rcx, [rsp+1F0h+hObject]; hObject
0x1800f5547  test    rcx, rcx
0x1800f554a  jz      short loc_1800F5560
0x1800f554c  call    cs:__imp_CloseHandle
0x1800f5553  nop     dword ptr [rax+rax+00h]
0x1800f5558  test    eax, eax
0x1800f555a  jz      loc_1800F5E49
0x1800f5560  mov     rcx, r15; this
0x1800f5563  call    ??1ComputeSystemConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(void)
0x1800f5568  lea     rcx, [r14+28h]; this
0x1800f556c  cmp     [rcx+58h], sil
0x1800f5570  jz      short loc_1800F5577
0x1800f5572  call    ??1BindingSettings@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BindingSettings::~BindingSettings(void)
0x1800f5577  lea     rcx, [r14+8]
0x1800f557b  cmp     [rcx+18h], sil
0x1800f557f  jmp     loc_1800F51BB
0x1800f5584  mov     rdx, [rsp+1F0h+pv]; pv
0x1800f5589  lea     rcx, ?OnComputeSystemTerminateTimer@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800f5590  xor     r8d, r8d; pcbe
0x1800f5593  call    cs:__imp_CreateThreadpoolTimer
0x1800f559a  nop     dword ptr [rax+rax+00h]
0x1800f559f  mov     [rsp+1F0h+pti], rax
0x1800f55a4  mov     rbx, rax
0x1800f55a7  test    rax, rax
0x1800f55aa  jnz     loc_1800F5651
0x1800f55b0  mov     rcx, [rbp+0F8h]; this
0x1800f55b7  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f55be  mov     edx, 0CDh; void *
0x1800f55c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f55c8  xor     edx, edx
0x1800f55ca  lea     rcx, [rsp+1F0h+var_198]
0x1800f55cf  mov     ebx, eax
0x1800f55d1  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f55d6  xor     edx, edx
0x1800f55d8  lea     rcx, [rsp+1F0h+var_1A0]
0x1800f55dd  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f55e2  xor     edx, edx
0x1800f55e4  lea     rcx, [rsp+1F0h+var_1A8]
0x1800f55e9  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f55ee  mov     rcx, [rsp+1F0h+var_1B0]; hObject
0x1800f55f3  test    rcx, rcx
0x1800f55f6  jz      short loc_1800F560C
0x1800f55f8  call    cs:__imp_CloseHandle
0x1800f55ff  nop     dword ptr [rax+rax+00h]
0x1800f5604  test    eax, eax
0x1800f5606  jz      loc_1800F5E5B
0x1800f560c  mov     rcx, [rsp+1F0h+var_1B8]; hObject
  ... truncated ...
```
