# Windows::Policy::RefreshWaaSOutOfDate(void)

- ea: `0x180062620`
- end: `0x18006365e`
- name: `?RefreshWaaSOutOfDate@Policy@Windows@@AEAAXXZ`
- size: `4158`
- prototype: `void __fastcall(Windows::Policy *__hidden this)`
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800600b0`
- `0x180060190`
- `0x180061920`
- `0x180062510`
- `0x1800625f0`

## callees

- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x18001fab0`
- `0x1800209fc`
- `0x18002107c`
- `0x180023a58`
- `0x18003a1f0`
- `0x180045bd4`
- `0x18005ac34`
- `0x18005ecd0`
- `0x180060778`
- `0x1800608fc`
- `0x180062620`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800626e9`
- `msvcp_win!_Xtime_get_ticks` at `0x1800628bf`
- `msvcp_win!_Xtime_get_ticks` at `0x180062b4d`
- `msvcp_win!_Xtime_get_ticks` at `0x180062b88`
- `msvcp_win!_Xtime_get_ticks` at `0x18006309f`
- `msvcp_win!_Xtime_get_ticks` at `0x1800630d3`
- `msvcp_win!_Xtime_get_ticks` at `0x18006359f`
- `msvcp_win!_Xtime_get_ticks` at `0x1800626e9`
- `msvcp_win!_Xtime_get_ticks` at `0x1800628bf`
- `msvcp_win!_Xtime_get_ticks` at `0x180062b4d`
- `msvcp_win!_Xtime_get_ticks` at `0x180062b88`
- `msvcp_win!_Xtime_get_ticks` at `0x18006309f`
- `msvcp_win!_Xtime_get_ticks` at `0x1800630d3`
- `msvcp_win!_Xtime_get_ticks` at `0x18006359f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006271a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006271a`

## string_xrefs

- `0x1800635f6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\policy.cpp`
- `0x18006360a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\policy.cpp`
- `0x18006361e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\policy.cpp`
- `0x18006364b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\policy.cpp`
- `0x1800629df`: `Override out of date value for quality update based on WaaS because it is a managed device.`
- `0x180062df4`: ` hours out of date for quality update`
- `0x180062c5a`: `Quality updates are deferred for `
- `0x18006332b`: ` hours out of date for feature update`
- `0x18006319b`: `Feature updates are deferred for `
- `0x180062fb5`: `Override out of date value for feature update based on WaaS because it is a managed device.`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall Windows::Policy::RefreshWaaSOutOfDate(Windows::Policy *this)
{
  char v2; // di
  const char *v3; // r9
  char v4; // bl
  __int64 v5; // rbx
  HRESULT v6; // r15d
  _QWORD **System; // rax
  char v8; // r12
  volatile signed __int32 *v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  __int64 ticks; // rax
  __int64 v15; // rbx
  int v16; // eax
  _QWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  void (__fastcall *v20)(__int64, __int128 *, __int64); // r15
  volatile signed __int32 *v21; // rbx
  volatile signed __int32 *v22; // rbx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // r13
  int v27; // r15d
  char v28; // al
  __int64 v29; // rcx
  _QWORD *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  void (__fastcall *v33)(__int64, __int128 *, __int64); // r13
  __int64 v34; // rax
  void *v35; // rax
  __int64 v36; // rax
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  _QWORD *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rbx
  void (__fastcall *v42)(__int64, __int128 *, __int64); // r15
  __int64 v43; // r8
  void *v44; // rcx
  __int64 v45; // rax
  volatile signed __int32 *v46; // rbx
  volatile signed __int32 *v47; // rbx
  _QWORD *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rbx
  void (__fastcall *v51)(__int64, __int128 *, __int64); // r15
  volatile signed __int32 *v52; // rbx
  volatile signed __int32 *v53; // rbx
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rbx
  __int64 v57; // r13
  int v58; // r15d
  char v59; // cl
  __int64 v60; // rax
  _QWORD *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rbx
  void (__fastcall *v64)(__int64, __int128 *, __int64); // r12
  __int64 v65; // r8
  void *v66; // rcx
  __int64 v67; // rax
  volatile signed __int32 *v68; // rbx
  volatile signed __int32 *v69; // rbx
  _QWORD *v70; // rax
  __int64 v71; // rax
  __int64 v72; // rbx
  void (__fastcall *v73)(__int64, __int128 *, __int64); // r15
  __int64 v74; // r8
  void *v75; // rcx
  __int64 v76; // rax
  volatile signed __int32 *v77; // rbx
  volatile signed __int32 *v78; // rbx
  int v79; // eax
  _QWORD *v80; // rax
  _QWORD *v81; // rax
  char v82; // bl
  int v83; // eax
  _QWORD *v84; // rax
  _QWORD *v85; // rax
  char v86; // bl
  int v87; // eax
  int ppv; // [rsp+20h] [rbp-168h]
  int v89; // [rsp+40h] [rbp-148h] BYREF
  int v90; // [rsp+44h] [rbp-144h] BYREF
  int v91; // [rsp+48h] [rbp-140h] BYREF
  char v92[8]; // [rsp+50h] [rbp-138h] BYREF
  volatile signed __int32 *v93; // [rsp+58h] [rbp-130h]
  char v94[8]; // [rsp+60h] [rbp-128h] BYREF
  volatile signed __int32 *v95; // [rsp+68h] [rbp-120h]
  LPVOID v96; // [rsp+70h] [rbp-118h] BYREF
  __int64 v97; // [rsp+78h] [rbp-110h] BYREF
  int v98; // [rsp+80h] [rbp-108h]
  __int64 v99; // [rsp+88h] [rbp-100h] BYREF
  _DWORD v100[8]; // [rsp+90h] [rbp-F8h] BYREF
  char v101; // [rsp+B0h] [rbp-D8h]
  char v102; // [rsp+B8h] [rbp-D0h]
  int v103; // [rsp+C0h] [rbp-C8h] BYREF
  char v104; // [rsp+C4h] [rbp-C4h]
  __int64 v105; // [rsp+C8h] [rbp-C0h] BYREF
  __int128 v106; // [rsp+D0h] [rbp-B8h] BYREF
  __int128 v107; // [rsp+E0h] [rbp-A8h]
  __int64 v108; // [rsp+F0h] [rbp-98h] BYREF
  int v109; // [rsp+F8h] [rbp-90h]
  __int64 v110; // [rsp+100h] [rbp-88h] BYREF
  int v111; // [rsp+108h] [rbp-80h]
  _BYTE v112[32]; // [rsp+110h] [rbp-78h] BYREF
  _BYTE v113[32]; // [rsp+130h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v2 = 0;
  v98 = 0;
  try
  {
    Windows::GetPolicy();
    if ( !v102 )
      goto LABEL_6;
    if ( v101 != 2 )
      std::_Throw_bad_variant_access();
    if ( v100[0] == 1 )
      v4 = 1;
    else
LABEL_6:
      v4 = 0;
    if ( v102 && v101 != -1 && v101 && (unsigned __int64)(v101 - 1LL) >= 2 )
      std::wstring::_Tidy_deallocate(v100);
    if ( !v4 )
    {
      v5 = *((_QWORD *)this + 5) + 864000000000LL;
      if ( _Xtime_get_ticks() >= v5 )
      {
        v96 = 0;
        v6 = CoCreateInstance(
               &GUID_098ef871_fa9f_46af_8958_c083515d7c9c,
               0,
               1u,
               &GUID_28f36eb8_3990_460a_bda9_3f06f8514de9,
               &v96);
        if ( v6 != -2147221164
          || (System = (_QWORD **)SystemInterface::Service::GetSystem(v92),
              v2 = 1,
              v98 = 1,
              v8 = 1,
              !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**System + 128LL))(*System, **System)) )
        {
          v8 = 0;
        }
        if ( (v2 & 1) != 0 )
        {
          v9 = v93;
          if ( v93 )
          {
            if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
              if ( !_InterlockedDecrement(v9 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
            }
          }
        }
        if ( v8 )
        {
          if ( v96 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
          return;
        }
        if ( v6 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C0,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\policy.cpp",
            (const char *)(unsigned int)v6,
            ppv);
        v97 = 0;
        v90 = 0;
        v89 = 0;
        v108 = 0;
        v109 = 0;
        v10 = (_QWORD *)SystemInterface::Service::GetSystem(v94);
        v11 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v10 + 48LL))(*v10, v92);
        (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v11 + 64LL))(*v11, &v103);
        v12 = v93;
        if ( v93 )
        {
          if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
        v13 = v95;
        if ( v95 )
        {
          if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
        if ( v104 )
        {
          v90 = 1;
          v89 = 0;
          ticks = _Xtime_get_ticks();
          v15 = (ticks - 36000000000LL * v103) % 10000000
              + 10000000 * ((ticks - 36000000000LL * v103) / 10000000 + 0x2B6109100LL);
          v97 = v15;
        }
        else
        {
          v16 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int *))(*(_QWORD *)v96 + 88LL))(
                  v96,
                  &v97,
                  &v108,
                  &v90);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2DC,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\policy.cpp",
              (const char *)(unsigned int)v16,
              (int)&v89);
          if ( v16 == 1 )
          {
LABEL_51:
            v99 = 0;
            v90 = 0;
            v89 = 0;
            v110 = 0;
            v111 = 0;
            v23 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int *))(*(_QWORD *)v96 + 88LL))(
                    v96,
                    &v99,
                    &v110,
                    &v90);
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x309,
                (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\policy.cpp",
                (const char *)(unsigned int)v23,
                (int)&v89);
            if ( v23 != 1 )
            {
              if ( (_DWORD)v110 == 9 )
              {
                v48 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
                v49 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v48 + 96LL))(*v48, v94);
                v50 = *(_QWORD *)v49;
                v51 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v49 + 112LL);
                v106 = 0;
                v107 = 0u;
                std::wstring::_Construct<1,unsigned short const *>(
                  &v106,
                  L"Override out of date value for feature update based on WaaS because it is a managed device.",
                  91);
                v51(v50, &v106, 1);
                std::wstring::_Tidy_deallocate(&v106);
                v52 = v95;
                if ( v95 )
                {
                  if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
                    if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
                  }
                }
                v53 = v93;
                if ( v93 )
                {
                  if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
                    if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
                  }
                }
                if ( !*((_BYTE *)this + 12) )
                  *((_BYTE *)this + 12) = 1;
                *((_DWORD *)this + 2) = 0;
                *((_BYTE *)this + 32) = 0;
              }
              else if ( v90 )
              {
                v54 = v99;
                v55 = (_Xtime_get_ticks() - v54 + 116444736000000000LL) / 36000000000LL;
                if ( !*((_BYTE *)this + 12) )
                  *((_BYTE *)this + 12) = 1;
                *((_DWORD *)this + 2) = v55;
                *((_BYTE *)this + 32) = HIDWORD(v108) == 3;
                v56 = v99;
                v57 = _Xtime_get_ticks();
                Windows::GetEnterprisePolicy(v100, 9);
                if ( v102 )
                {
                  if ( v101 != 2 )
                    std::_Throw_bad_variant_access();
                  v58 = 24 * v100[0];
                  v59 = *((_BYTE *)this + 12);
                  if ( v59 && v58 < *((_DWORD *)this + 2) )
                  {
                    v60 = (36000000000LL * (3234576LL - v58) - v56 + v57) / 36000000000LL;
                  }
                  else
                  {
                    LODWORD(v60) = 0;
                    if ( !v59 )
                      *((_BYTE *)this + 12) = 1;
                  }
                  *((_DWORD *)this + 2) = v60;
                  v61 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
                  v62 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v61 + 96LL))(*v61, v94);
                  v63 = *(_QWORD *)v62;
                  v64 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v62 + 112LL);
                  v65 = std::to_wstring(v112, (unsigned int)v58);
                  v66 = (void *)std::operator+<unsigned short>(v113, L"Feature updates are deferred for ", v65);
                  v67 = std::wstring::_Append<unsigned short>(v66);
                  v106 = 0;
                  v107 = 0u;
                  v106 = *(_OWORD *)v67;
                  v107 = *(_OWORD *)(v67 + 16);
                  *(_QWORD *)(v67 + 16) = 0;
                  *(_QWORD *)(v67 + 24) = 7;
                  *(_WORD *)v67 = 0;
                  v64(v63, &v106, 1);
                  std::wstring::_Tidy_deallocate(&v106);
                  std::wstring::_Tidy_deallocate(v113);
                  std::wstring::_Tidy_deallocate(v112);
                  v68 = v95;
                  if ( v95 )
                  {
                    if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
                      if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
                    }
                  }
                  v69 = v93;
                  if ( v93 )
                  {
                    if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
                      if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
                    }
                  }
                }
                v70 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
                v71 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v70 + 96LL))(*v70, v94);
                if ( !*((_BYTE *)this + 12) )
                  std::_Throw_bad_optional_access();
                v72 = *(_QWORD *)v71;
                v73 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v71 + 112LL);
                v74 = std::to_wstring(v112, *((unsigned int *)this + 2));
                v75 = (void *)std::operator+<unsigned short>(v113, L"Device is ", v74);
                v76 = std::wstring::_Append<unsigned short>(v75);
                v106 = 0;
                v107 = 0u;
                v106 = *(_OWORD *)v76;
                v107 = *(_OWORD *)(v76 + 16);
                *(_QWORD *)(v76 + 16) = 0;
                *(_QWORD *)(v76 + 24) = 7;
                *(_WORD *)v76 = 0;
                v73(v72, &v106, 1);
                std::wstring::_Tidy_deallocate(&v106);
                std::wstring::_Tidy_deallocate(v113);
                std::wstring::_Tidy_deallocate(v112);
                v77 = v95;
                if ( v95 )
                {
                  if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
                    if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
                  }
                }
                v78 = v93;
                if ( v93 )
                {
                  if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
                    if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
                  }
                }
                if ( v102 && v101 != -1 && v101 && (unsigned __int64)(v101 - 1LL) >= 2 )
                  std::wstring::_Tidy_deallocate(v100);
              }
            }
            v105 = 0;
            v91 = 0;
            v79 = (*(__int64 (__fastcall **)(LPVOID, int *, int *, __int64 *))(*(_QWORD *)v96 + 80LL))(
                    v96,
                    &v89,
                    &v91,
                    &v105);
            if ( v79 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x32E,
                (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\policy.cpp",
                (const char *)(unsigned int)v79,
                1);
            if ( v79 == 1 )
            {
              v89 = 0;
              v91 = 876000;
            }
            v80 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
            v81 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v80 + 48LL))(*v80, v94);
            v82 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v81 + 136LL))(*v81);
            std::shared_ptr<SystemInterface::Service::System>::~shared_ptr<SystemInterface::Service::System>(v94);
            std::shared_ptr<SystemInterface::Service::System>::~shared_ptr<SystemInterface::Service::System>(v92);
            if ( v82 )
            {
              v83 = 0;
            }
            else
            {
              v84 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
              v85 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v84 + 48LL))(*v84, v94);
              v86 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v85 + 128LL))(*v85);
              std::shared_ptr<SystemInterface::Service::System>::~shared_ptr<SystemInterface::Service::System>(v94);
              std::shared_ptr<SystemInterface::Service::System>::~shared_ptr<SystemInterface::Service::System>(v92);
              if ( !v86 )
              {
                v87 = v91;
                if ( v89 )
                  v87 = -v91;
                *((_DWORD *)this + 6) = 24 * v87;
                if ( !*((_BYTE *)this + 28) )
                  *((_BYTE *)this + 28) = 1;
                goto LABEL_144;
              }
              v83 = 120;
            }
            if ( !*((_BYTE *)this + 28) )
              *((_BYTE *)this + 28) = 1;
            *((_DWORD *)this + 6) = v83;
LABEL_144:
            *((_QWORD *)this + 5) = _Xtime_get_ticks();
            if ( v96 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
            return;
          }
          v15 = v97;
        }
        if ( (_DWORD)v108 == 9 )
        {
          v17 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
          v18 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v17 + 96LL))(*v17, v94);
          v19 = *(_QWORD *)v18;
          v20 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v18 + 112LL);
          v106 = 0;
          v107 = 0u;
          std::wstring::_Construct<1,unsigned short const *>(
            &v106,
            L"Override out of date value for quality update based on WaaS because it is a managed device.",
            91);
          v20(v19, &v106, 1);
          std::wstring::_Tidy_deallocate(&v106);
          v21 = v95;
          if ( v95 )
          {
            if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
              if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
            }
          }
          v22 = v93;
          if ( v93 )
          {
            if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          if ( !*((_BYTE *)this + 20) )
            *((_BYTE *)this + 20) = 1;
          *((_DWORD *)this + 4) = 0;
          *((_BYTE *)this + 33) = 0;
        }
        else if ( v90 )
        {
          v24 = (_Xtime_get_ticks() - v15 + 116444736000000000LL) / 36000000000LL;
          if ( !*((_BYTE *)this + 20) )
            *((_BYTE *)this + 20) = 1;
          *((_DWORD *)this + 4) = v24;
          *((_BYTE *)this + 33) = HIDWORD(v108) == 3;
          v25 = v97;
          v26 = _Xtime_get_ticks();
          Windows::GetEnterprisePolicy(v100, 7);
          if ( v102 )
          {
            if ( v101 != 2 )
              std::_Throw_bad_variant_access();
            v27 = 24 * v100[0];
            v28 = *((_BYTE *)this + 20);
            if ( v28 && v27 < *((_DWORD *)this + 4) )
            {
              v29 = (v26 + 36000000000LL * (3234576LL - v27) - v25) / 36000000000LL;
            }
            else
            {
              LODWORD(v29) = 0;
              if ( !v28 )
                *((_BYTE *)this + 20) = 1;
            }
            *((_DWORD *)this + 4) = v29;
            v30 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
            v31 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v30 + 96LL))(*v30, v94);
            v32 = *(_QWORD *)v31;
            v33 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v31 + 112LL);
            v34 = std::to_wstring(v113, (unsigned int)v27);
            v35 = (void *)std::operator+<unsigned short>(v112, L"Quality updates are deferred for ", v34);
            v36 = std::wstring::_Append<unsigned short>(v35);
            v106 = 0;
            v107 = 0u;
            v106 = *(_OWORD *)v36;
            v107 = *(_OWORD *)(v36 + 16);
            *(_QWORD *)(v36 + 16) = 0;
            *(_QWORD *)(v36 + 24) = 7;
            *(_WORD *)v36 = 0;
            v33(v32, &v106, 1);
            std::wstring::_Tidy_deallocate(&v106);
            std::wstring::_Tidy_deallocate(v112);
            std::wstring::_Tidy_deallocate(v113);
            v37 = v95;
            if ( v95 )
            {
              if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
                if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
              }
            }
            v38 = v93;
            if ( v93 )
            {
              if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
                if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
              }
            }
          }
          v39 = (_QWORD *)SystemInterface::Service::GetSystem(v92);
          v40 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v39 + 96LL))(*v39, v94);
          if ( !*((_BYTE *)this + 20) )
            std::_Throw_bad_optional_access();
          v41 = *(_QWORD *)v40;
          v42 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v40 + 112LL);
          v43 = std::to_wstring(v112, *((unsigned int *)this + 4));
          v44 = (void *)std::operator+<unsigned short>(v113, L"Device is ", v43);
          v45 = std::wstring::_Append<unsigned short>(v44);
          v106 = 0;
          v107 = 0u;
          v106 = *(_OWORD *)v45;
          v107 = *(_OWORD *)(v45 + 16);
          *(_QWORD *)(v45 + 16) = 0;
          *(_QWORD *)(v45 + 24) = 7;
          *(_WORD *)v45 = 0;
          v42(v41, &v106, 1);
          std::wstring::_Tidy_deallocate(&v106);
          std::wstring::_Tidy_deallocate(v113);
          std::wstring::_Tidy_deallocate(v112);
          v46 = v95;
          if ( v95 )
          {
            if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
              if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
            }
          }
          v47 = v93;
          if ( v93 )
          {
            if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
              if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
            }
          }
          if ( v102 && v101 != -1 && v101 && (unsigned __int64)(v101 - 1LL) >= 2 )
            std::wstring::_Tidy_deallocate(v100);
        }
        goto LABEL_51;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\policy.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x180062620  mov     r11, rsp
0x180062623  mov     [r11+10h], rbx
0x180062627  mov     [r11+18h], rsi
0x18006262b  push    rdi
0x18006262c  push    r12
0x18006262e  push    r13
0x180062630  push    r14
0x180062632  push    r15
0x180062634  sub     rsp, 160h
0x18006263b  mov     rax, cs:__security_cookie
0x180062642  xor     rax, rsp
0x180062645  mov     [rsp+188h+var_38], rax
0x18006264d  mov     rsi, rcx
0x180062650  xor     r13d, r13d
0x180062653  mov     edi, r13d
0x180062656  mov     [r11-108h], r13d
0x18006265d  lea     edx, [r13+0Eh]
0x180062661  lea     rcx, [r11-0F8h]
0x180062668  call    ?GetPolicy@Windows@@YA?AV?$optional@V?$variant@_NIHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@W4tagUpdatePolicy@@@Z; Windows::GetPolicy(tagUpdatePolicy)
0x18006266d  nop
0x18006266e  mov     cl, [rsp+188h+var_D0]
0x180062675  mov     al, [rsp+188h+var_D8]
0x18006267c  test    cl, cl
0x18006267e  jz      short loc_18006269B
0x180062680  cmp     al, 2
0x180062682  jnz     loc_1800635ED
0x180062688  lea     r14d, [r13+1]
0x18006268c  cmp     [rsp+188h+var_F8], r14d
0x180062694  jnz     short loc_1800626A1
0x180062696  mov     bl, r14b
0x180062699  jmp     short loc_1800626A4
0x18006269b  mov     r14d, 1
0x1800626a1  mov     bl, r13b
0x1800626a4  test    cl, cl
0x1800626a6  jz      short loc_1800626D0
0x1800626a8  movsx   rax, al
0x1800626ac  add     rax, r14
0x1800626af  jz      short loc_1800626D0
0x1800626b1  sub     rax, 1
0x1800626b5  jz      short loc_1800626D0
0x1800626b7  sub     rax, 1
0x1800626bb  jz      short loc_1800626D0
0x1800626bd  cmp     rax, 1
0x1800626c1  jz      short loc_1800626D0
0x1800626c3  lea     rcx, [rsp+188h+var_F8]
0x1800626cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800626d0  test    bl, bl
0x1800626d2  jnz     loc_1800635C0
0x1800626d8  mov     rbx, [rsi+28h]
0x1800626dc  mov     rcx, 0C92A69C000h
0x1800626e6  add     rbx, rcx
0x1800626e9  call    cs:__imp__Xtime_get_ticks
0x1800626ef  cmp     rax, rbx
0x1800626f2  jl      loc_1800635C0
0x1800626f8  mov     [rsp+188h+var_118], r13
0x1800626fd  lea     rax, [rsp+188h+var_118]
0x180062702  mov     [rsp+188h+ppv], rax; int
0x180062707  lea     r9, _GUID_28f36eb8_3990_460a_bda9_3f06f8514de9; riid
0x18006270e  mov     r8d, r14d; dwClsContext
0x180062711  xor     edx, edx; pUnkOuter
0x180062713  lea     rcx, _GUID_098ef871_fa9f_46af_8958_c083515d7c9c; rclsid
0x18006271a  call    cs:__imp_CoCreateInstance
0x180062720  mov     r15d, eax
0x180062723  cmp     eax, 80040154h
0x180062728  jnz     short loc_180062759
0x18006272a  lea     rcx, [rsp+188h+var_138]
0x18006272f  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180062734  nop
0x180062735  mov     edi, r14d
0x180062738  mov     [rsp+188h+var_108], r14d
0x180062740  mov     rcx, [rax]
0x180062743  mov     rdx, [rcx]
0x180062746  mov     rax, [rdx+80h]
0x18006274d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062752  test    al, al
0x180062754  mov     r12b, r14b
0x180062757  jnz     short loc_18006275C
0x180062759  mov     r12b, r13b
0x18006275c  test    r14b, dil
0x18006275f  jz      short loc_1800627A3
0x180062761  mov     rbx, [rsp+188h+var_130]
0x180062766  test    rbx, rbx
0x180062769  jz      short loc_1800627A3
0x18006276b  or      edi, 0FFFFFFFFh
0x18006276e  mov     eax, edi
0x180062770  lock xadd [rbx+8], eax
0x180062775  add     eax, edi
0x180062777  jnz     short loc_1800627A6
0x180062779  mov     rax, [rbx]
0x18006277c  mov     rcx, rbx
0x18006277f  mov     rax, [rax]
0x180062782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062787  mov     eax, edi
0x180062789  lock xadd [rbx+0Ch], eax
0x18006278e  add     eax, edi
0x180062790  jnz     short loc_1800627A6
0x180062792  mov     rax, [rbx]
0x180062795  mov     rcx, rbx
0x180062798  mov     rax, [rax+8]
0x18006279c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627a1  jmp     short loc_1800627A6
0x1800627a3  or      edi, 0FFFFFFFFh
0x1800627a6  test    r12b, r12b
0x1800627a9  jz      short loc_1800627C7
0x1800627ab  mov     rcx, [rsp+188h+var_118]
0x1800627b0  test    rcx, rcx
0x1800627b3  jz      short loc_1800627C2
0x1800627b5  mov     rax, [rcx]
0x1800627b8  mov     rax, [rax+10h]
0x1800627bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627c1  nop
0x1800627c2  jmp     loc_1800635C0
0x1800627c7  mov     rcx, [rsp+188h]; this
0x1800627cf  test    r15d, r15d
0x1800627d2  js      loc_1800635F3
0x1800627d8  mov     [rsp+188h+var_110], r13
0x1800627dd  mov     [rsp+188h+var_144], r13d
0x1800627e2  mov     [rsp+188h+var_148], r13d
0x1800627e7  xor     eax, eax
0x1800627e9  mov     [rsp+188h+var_98], rax
0x1800627f1  mov     [rsp+188h+var_90], eax
0x1800627f8  lea     rcx, [rsp+188h+var_128]
0x1800627fd  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180062802  nop
0x180062803  mov     rcx, [rax]
0x180062806  mov     rax, [rcx]
0x180062809  lea     rdx, [rsp+188h+var_138]
0x18006280e  mov     rax, [rax+30h]
0x180062812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062817  nop
0x180062818  mov     rcx, [rax]
0x18006281b  mov     rax, [rcx]
0x18006281e  lea     rdx, [rsp+188h+var_C8]
0x180062826  mov     rax, [rax+40h]
0x18006282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006282f  nop
0x180062830  mov     rbx, [rsp+188h+var_130]
0x180062835  test    rbx, rbx
0x180062838  jz      short loc_18006286E
0x18006283a  mov     eax, edi
0x18006283c  lock xadd [rbx+8], eax
0x180062841  add     eax, edi
0x180062843  jnz     short loc_18006286E
0x180062845  mov     rax, [rbx]
0x180062848  mov     rcx, rbx
0x18006284b  mov     rax, [rax]
0x18006284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062853  mov     eax, edi
0x180062855  lock xadd [rbx+0Ch], eax
0x18006285a  add     eax, edi
0x18006285c  jnz     short loc_18006286E
0x18006285e  mov     rax, [rbx]
0x180062861  mov     rcx, rbx
0x180062864  mov     rax, [rax+8]
0x180062868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006286d  nop
0x18006286e  mov     rbx, [rsp+188h+var_120]
0x180062873  test    rbx, rbx
0x180062876  jz      short loc_1800628AB
0x180062878  mov     eax, edi
0x18006287a  lock xadd [rbx+8], eax
0x18006287f  add     eax, edi
0x180062881  jnz     short loc_1800628AB
0x180062883  mov     rax, [rbx]
0x180062886  mov     rcx, rbx
0x180062889  mov     rax, [rax]
0x18006288c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062891  mov     eax, edi
0x180062893  lock xadd [rbx+0Ch], eax
0x180062898  add     eax, edi
0x18006289a  jnz     short loc_1800628AB
0x18006289c  mov     rax, [rbx]
0x18006289f  mov     rcx, rbx
0x1800628a2  mov     rax, [rax+8]
0x1800628a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628ab  cmp     [rsp+188h+var_C4], r13b
0x1800628b3  jz      short loc_180062927
0x1800628b5  mov     [rsp+188h+var_144], r14d
0x1800628ba  mov     [rsp+188h+var_148], r13d
0x1800628bf  call    cs:__imp__Xtime_get_ticks
0x1800628c5  mov     rcx, rax
0x1800628c8  movsxd  rax, [rsp+188h+var_C8]
0x1800628d0  mov     r15, 861C46800h
0x1800628da  imul    rax, r15
0x1800628de  sub     rcx, rax
0x1800628e1  mov     rax, 0D6BF94D5E57A42BDh
0x1800628eb  imul    rcx
0x1800628ee  add     rdx, rcx
0x1800628f1  sar     rdx, 17h
0x1800628f5  mov     rax, rdx
0x1800628f8  shr     rax, 3Fh
0x1800628fc  add     rdx, rax
0x1800628ff  imul    rax, rdx, 989680h
0x180062906  sub     rcx, rax
0x180062909  mov     rax, 2B6109100h
0x180062913  add     rax, rdx
0x180062916  imul    rbx, rax, 989680h
0x18006291d  add     rbx, rcx
0x180062920  mov     [rsp+188h+var_110], rbx
0x180062925  jmp     short loc_180062986
0x180062927  mov     rcx, [rsp+188h+var_118]
0x18006292c  mov     rax, [rcx]
0x18006292f  mov     [rsp+188h+var_158], r14d
0x180062934  mov     [rsp+188h+var_160], r14d
0x180062939  lea     rdx, [rsp+188h+var_148]
0x18006293e  mov     [rsp+188h+ppv], rdx; int
0x180062943  lea     r9, [rsp+188h+var_144]
0x180062948  lea     r8, [rsp+188h+var_98]
0x180062950  lea     rdx, [rsp+188h+var_110]
0x180062955  mov     rax, [rax+58h]
0x180062959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006295e  mov     rcx, [rsp+188h]; this
0x180062966  test    eax, eax
0x180062968  js      loc_180063607
0x18006296e  cmp     eax, r14d
0x180062971  jz      loc_180062AA8
0x180062977  mov     r15, 861C46800h
0x180062981  mov     rbx, [rsp+188h+var_110]
0x180062986  cmp     dword ptr [rsp+188h+var_98], 9
0x18006298e  jnz     loc_180062B37
0x180062994  lea     rcx, [rsp+188h+var_138]
0x180062999  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18006299e  nop
0x18006299f  mov     rcx, [rax]
0x1800629a2  mov     rax, [rcx]
0x1800629a5  lea     rdx, [rsp+188h+var_128]
0x1800629aa  mov     rax, [rax+60h]
0x1800629ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629b3  nop
0x1800629b4  mov     rbx, [rax]
0x1800629b7  mov     rax, [rbx]
0x1800629ba  mov     r15, [rax+70h]
0x1800629be  xorps   xmm0, xmm0
0x1800629c1  movups  [rsp+188h+var_B8], xmm0
0x1800629c9  mov     qword ptr [rsp+188h+var_A8], r13
0x1800629d1  mov     qword ptr [rsp+188h+var_A8+8], r13
0x1800629d9  mov     r8d, 5Bh ; '['
0x1800629df  lea     rdx, aOverrideOutOfD_0; "Override out of date value for quality "...
0x1800629e6  lea     rcx, [rsp+188h+var_B8]
0x1800629ee  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800629f3  nop
0x1800629f4  mov     r8d, r14d
0x1800629f7  lea     rdx, [rsp+188h+var_B8]
0x1800629ff  mov     rcx, rbx
0x180062a02  mov     rax, r15
0x180062a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a0a  nop
0x180062a0b  lea     rcx, [rsp+188h+var_B8]
0x180062a13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062a18  nop
0x180062a19  mov     rbx, [rsp+188h+var_120]
0x180062a1e  test    rbx, rbx
0x180062a21  jz      short loc_180062A57
0x180062a23  mov     eax, edi
0x180062a25  lock xadd [rbx+8], eax
0x180062a2a  add     eax, edi
0x180062a2c  jnz     short loc_180062A57
0x180062a2e  mov     rax, [rbx]
0x180062a31  mov     rcx, rbx
0x180062a34  mov     rax, [rax]
0x180062a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a3c  mov     eax, edi
0x180062a3e  lock xadd [rbx+0Ch], eax
0x180062a43  add     eax, edi
0x180062a45  jnz     short loc_180062A57
0x180062a47  mov     rax, [rbx]
0x180062a4a  mov     rcx, rbx
0x180062a4d  mov     rax, [rax+8]
0x180062a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a56  nop
0x180062a57  mov     rbx, [rsp+188h+var_130]
0x180062a5c  test    rbx, rbx
0x180062a5f  jz      short loc_180062A94
0x180062a61  mov     eax, edi
0x180062a63  lock xadd [rbx+8], eax
0x180062a68  add     eax, edi
0x180062a6a  jnz     short loc_180062A94
0x180062a6c  mov     rax, [rbx]
0x180062a6f  mov     rcx, rbx
0x180062a72  mov     rax, [rax]
0x180062a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a7a  mov     eax, edi
0x180062a7c  lock xadd [rbx+0Ch], eax
0x180062a81  add     eax, edi
0x180062a83  jnz     short loc_180062A94
0x180062a85  mov     rax, [rbx]
0x180062a88  mov     rcx, rbx
0x180062a8b  mov     rax, [rax+8]
0x180062a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a94  mov     eax, r13d
0x180062a97  cmp     [rsi+14h], r13b
0x180062a9b  jnz     short loc_180062AA1
0x180062a9d  mov     [rsi+14h], r14b
0x180062aa1  mov     [rsi+10h], eax
0x180062aa4  mov     [rsi+21h], r13b
0x180062aa8  mov     r12d, 315B10h
0x180062aae  mov     r15, 19DB1DED53E8000h
0x180062ab8  mov     r13, 861C46800h
0x180062ac2  xor     ebx, ebx
0x180062ac4  mov     [rsp+188h+var_100], rbx
  ... truncated ...
```
