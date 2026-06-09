# ModernDeployment::Autopilot::Core::AttestationConfiguration::MergeConfigurations(ModernDeployment::Autopilot::Core::IAttestationConfiguration *,ModernDeployment::Autopilot::Core::IAttestationConfiguration *)

- ea: `0x180109bd4`
- end: `0x18010b015`
- name: `?MergeConfigurations@AttestationConfiguration@Core@Autopilot@ModernDeployment@@SAJPEAUIAttestationConfiguration@234@0@Z`
- size: `5185`
- prototype: `__int64 __fastcall(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180117e0c`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x1800801fc`
- `0x1800cfeb4`
- `0x180107860`
- `0x180109bd4`
- `0x1801fa010`

## string_xrefs

- `0x180109c2e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109c59`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109ca1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109ce9`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109d21`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109d71`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109db1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109df7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109e47`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109e87`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109ed5`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109f1c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109f8e`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x180109fed`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a05d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a0d2`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a14d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a1e1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a273`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a30d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a3fb`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a4a5`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a54f`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a611`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a6bb`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a765`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a84c`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a8f0`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010a995`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010aa63`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010ab0d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010abb7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010ac87`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010ad4d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010ae06`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010af39`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010afcf`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AttestationConfiguration::MergeConfigurations(
        struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *a1,
        struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *a2)
{
  int v5; // eax
  unsigned int v6; // esi
  int v7; // eax
  unsigned int v8; // esi
  int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  unsigned int v12; // esi
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  unsigned int v18; // esi
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // edi
  __int64 (__fastcall *v25)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, __int64 **); // rdi
  int v26; // eax
  unsigned int v27; // edi
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // edi
  __int64 (__fastcall **v31)(_QWORD, GUID *, __int64 **); // rax
  int v32; // eax
  unsigned int v33; // edi
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // edi
  int v37; // eax
  unsigned int v38; // edi
  __int64 v39; // rax
  int v40; // eax
  unsigned int v41; // edi
  int v42; // eax
  unsigned int v43; // edi
  __int64 v44; // rax
  int v45; // eax
  unsigned int v46; // edi
  __int64 v47; // rax
  int v48; // edi
  int v49; // eax
  unsigned int v50; // edi
  int v51; // eax
  unsigned int v52; // edi
  int v53; // eax
  unsigned int v54; // edi
  int v55; // eax
  unsigned int v56; // edi
  int v57; // eax
  unsigned int v58; // edi
  int v59; // eax
  unsigned int v60; // edi
  __int64 v61; // rdx
  unsigned int v62; // esi
  unsigned int v63; // r14d
  int v64; // eax
  unsigned int v65; // edi
  int v66; // eax
  unsigned int v67; // edi
  int v68; // eax
  unsigned int v69; // edi
  int v70; // eax
  unsigned int v71; // edi
  int v72; // eax
  unsigned int v73; // edi
  int v74; // eax
  unsigned int v75; // edi
  int v76; // eax
  unsigned int v77; // edi
  int v78; // eax
  unsigned int v79; // edi
  int v80; // eax
  unsigned int v81; // edi
  int v82; // eax
  unsigned int v83; // ebx
  int v84; // [rsp+20h] [rbp-D8h]
  _QWORD v85[2]; // [rsp+30h] [rbp-C8h] BYREF
  _DWORD v86[4]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 *v87; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v88[8]; // [rsp+58h] [rbp-A0h] BYREF
  __int64 *v89; // [rsp+60h] [rbp-98h] BYREF
  __int64 *v90; // [rsp+68h] [rbp-90h] BYREF
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 **); // [rsp+70h] [rbp-88h] BYREF
  __int64 *v92; // [rsp+78h] [rbp-80h] BYREF
  __int64 v93; // [rsp+80h] [rbp-78h] BYREF
  __int64 v94; // [rsp+88h] [rbp-70h] BYREF
  __int64 *v95; // [rsp+90h] [rbp-68h] BYREF
  _BYTE v96[4]; // [rsp+98h] [rbp-60h] BYREF
  unsigned int v97; // [rsp+9Ch] [rbp-5Ch] BYREF
  unsigned int v98; // [rsp+A0h] [rbp-58h] BYREF
  unsigned int v99; // [rsp+A4h] [rbp-54h] BYREF
  unsigned int v100; // [rsp+A8h] [rbp-50h] BYREF
  unsigned int v101; // [rsp+ACh] [rbp-4Ch] BYREF
  unsigned int v102; // [rsp+B0h] [rbp-48h] BYREF
  int v103; // [rsp+B4h] [rbp-44h] BYREF
  int v104; // [rsp+B8h] [rbp-40h] BYREF
  __int64 v105; // [rsp+BCh] [rbp-3Ch] BYREF
  unsigned int v106; // [rsp+C4h] [rbp-34h] BYREF
  unsigned int v107; // [rsp+C8h] [rbp-30h] BYREF
  unsigned int v108; // [rsp+CCh] [rbp-2Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    if ( a1 )
    {
      if ( a2 )
      {
        v104 = 0;
        v5 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, int *))(*(_QWORD *)a1 + 64LL))(
               a1,
               &v104);
        v6 = v5;
        if ( v5 >= 0 )
        {
          v103 = 0;
          v7 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, int *))(*(_QWORD *)a2 + 64LL))(
                 a2,
                 &v103);
          v8 = v7;
          if ( v7 >= 0 )
          {
            if ( v104 == v103 )
            {
              v105 = 0;
              v9 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, char *))(*(_QWORD *)a1 + 48LL))(
                     a1,
                     (char *)&v105 + 4);
              v10 = v9;
              if ( v9 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, __int64 *))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        &v105);
                v12 = v11;
                if ( v11 >= 0 )
                {
                  v13 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, _QWORD))(*(_QWORD *)a2 + 56LL))(
                          a2,
                          HIDWORD(v105) | (unsigned int)v105);
                  v14 = v13;
                  if ( v13 >= 0 )
                  {
                    v102 = 0;
                    v106 = 0;
                    v15 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, unsigned int *))(*(_QWORD *)a1 + 80LL))(
                            a1,
                            &v102);
                    v16 = v15;
                    if ( v15 >= 0 )
                    {
                      v17 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, unsigned int *))(*(_QWORD *)a2 + 80LL))(
                              a2,
                              &v106);
                      v18 = v17;
                      if ( v17 >= 0 )
                      {
                        v19 = v106;
                        if ( v102 > v106 )
                          v19 = v102;
                        v20 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, __int64))(*(_QWORD *)a2 + 88LL))(
                                a2,
                                v19);
                        v21 = v20;
                        if ( v20 >= 0 )
                        {
                          v87 = 0;
                          v22 = *(_QWORD *)a1;
                          v89 = 0;
                          v23 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, __int64 **))(v22 + 96))(
                                  a1,
                                  &v89);
                          v24 = v23;
                          if ( v23 >= 0 )
                          {
                            v25 = *(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, __int64 **))(*(_QWORD *)a2 + 96LL);
                            v87 = 0;
                            v26 = v25(a2, &v87);
                            v27 = v26;
                            if ( v26 >= 0 )
                            {
                              v91 = 0;
                              v28 = *v89;
                              v91 = 0;
                              v29 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)))(v28 + 72))(
                                      v89,
                                      &v91);
                              v30 = v29;
                              if ( v29 >= 0 )
                              {
                                v92 = 0;
                                v31 = *v91;
                                v92 = 0;
                                v32 = (*v31)(v91, &GUID_a34fe5b1_df9f_55c5_9ec9_09dd9170a8ce, &v92);
                                v33 = v32;
                                if ( v32 >= 0 )
                                {
                                  v90 = 0;
                                  v34 = *v92;
                                  v90 = 0;
                                  v35 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v34 + 48))(v92, &v90);
                                  v36 = v35;
                                  if ( v35 >= 0 )
                                  {
                                    v88[0] = 0;
                                    v37 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v90 + 56))(v90, v88);
                                    v38 = v37;
                                    if ( v37 >= 0 )
                                    {
                                      while ( v88[0] )
                                      {
                                        v95 = 0;
                                        v39 = *v90;
                                        v95 = 0;
                                        v40 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v39 + 48))(v90, &v95);
                                        v41 = v40;
                                        if ( v40 < 0 )
                                        {
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            (void *)0x66,
                                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attes"
                                                          "tation\\attestationconfiguration.cpp",
                                            (const char *)(unsigned int)v40,
                                            v84);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                          return v41;
                                        }
                                        v100 = 0;
                                        v42 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v95 + 48))(
                                                v95,
                                                &v100);
                                        v43 = v42;
                                        if ( v42 < 0 )
                                        {
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            (void *)0x6A,
                                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attes"
                                                          "tation\\attestationconfiguration.cpp",
                                            (const char *)(unsigned int)v42,
                                            v84);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                          return v43;
                                        }
                                        v93 = 0;
                                        v44 = *v95;
                                        v93 = 0;
                                        v45 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v44 + 56))(v95, &v93);
                                        v46 = v45;
                                        if ( v45 < 0 )
                                        {
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            (void *)0x6D,
                                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attes"
                                                          "tation\\attestationconfiguration.cpp",
                                            (const char *)(unsigned int)v45,
                                            v84);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                          return v46;
                                        }
                                        v94 = 0;
                                        v47 = *v87;
                                        v94 = 0;
                                        v48 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v47 + 48))(
                                                v87,
                                                v100,
                                                &v94);
                                        if ( v48 < 0 )
                                        {
                                          if ( v48 != -2147483637 )
                                          {
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return (unsigned int)v48;
                                          }
                                          v99 = 0;
                                          v98 = 0;
                                          v97 = 0;
                                          v70 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v93 + 64LL))(
                                                  v93,
                                                  &v99);
                                          v71 = v70;
                                          if ( v70 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x92,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v70,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v71;
                                          }
                                          v72 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v93 + 80LL))(
                                                  v93,
                                                  &v98);
                                          v73 = v72;
                                          if ( v72 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x93,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v72,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v73;
                                          }
                                          v74 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v93 + 96LL))(
                                                  v93,
                                                  &v97);
                                          v75 = v74;
                                          if ( v74 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x94,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v74,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v75;
                                          }
                                          v85[0] = 0;
                                          v86[0] = v100;
                                          v86[1] = v99;
                                          v86[2] = v98;
                                          v86[3] = v97;
                                          v76 = ModernDeployment::Autopilot::Core::BuildAttestationPhaseRetrySettings(
                                                  v86,
                                                  v85);
                                          v77 = v76;
                                          if ( v76 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0xA1,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v76,
                                              v84);
                                            wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationPhaseRetrySettings,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationPhaseRetrySettings,wil::err_returncode_policy>(v85);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v77;
                                          }
                                          v96[0] = 0;
                                          v78 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _BYTE *))(*v87 + 80))(
                                                  v87,
                                                  v100,
                                                  v85[0],
                                                  v96);
                                          v79 = v78;
                                          if ( v78 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0xA4,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v78,
                                              v84);
                                            wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationPhaseRetrySettings,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationPhaseRetrySettings,wil::err_returncode_policy>(v85);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v79;
                                          }
                                          wil::com_ptr_t<ModernDeployment::Autopilot::Core::AttestationPhaseRetrySettings,wil::err_returncode_policy>::~com_ptr_t<ModernDeployment::Autopilot::Core::AttestationPhaseRetrySettings,wil::err_returncode_policy>(v85);
                                        }
                                        else
                                        {
                                          v97 = 0;
                                          v98 = 0;
                                          v99 = 0;
                                          v49 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v93 + 64LL))(
                                                  v93,
                                                  &v97);
                                          v50 = v49;
                                          if ( v49 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x79,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v49,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v50;
                                          }
                                          v51 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v93 + 80LL))(
                                                  v93,
                                                  &v98);
                                          v52 = v51;
                                          if ( v51 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x7A,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v51,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v52;
                                          }
                                          v53 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v93 + 96LL))(
                                                  v93,
                                                  &v99);
                                          v54 = v53;
                                          if ( v53 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x7B,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v53,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v54;
                                          }
                                          v107 = 0;
                                          v108 = 0;
                                          v101 = 0;
                                          v55 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v94 + 64LL))(
                                                  v94,
                                                  &v107);
                                          v56 = v55;
                                          if ( v55 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x80,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v55,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v56;
                                          }
                                          v57 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v94 + 80LL))(
                                                  v94,
                                                  &v108);
                                          v58 = v57;
                                          if ( v57 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x81,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v57,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v58;
                                          }
                                          v59 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v94 + 96LL))(
                                                  v94,
                                                  &v101);
                                          v60 = v59;
                                          if ( v59 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x82,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v59,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v60;
                                          }
                                          v61 = v107;
                                          if ( v97 > v107 )
                                            v61 = v97;
                                          v62 = v108;
                                          if ( v98 > v108 )
                                            v62 = v98;
                                          v63 = v101;
                                          if ( v99 > v101 )
                                            v63 = v99;
                                          v64 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 72LL))(
                                                  v94,
                                                  v61);
                                          v65 = v64;
                                          if ( v64 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x88,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v64,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v65;
                                          }
                                          v66 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v94 + 88LL))(
                                                  v94,
                                                  v62);
                                          v67 = v66;
                                          if ( v66 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x89,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v66,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v67;
                                          }
                                          v68 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v94 + 104LL))(
                                                  v94,
                                                  v63);
                                          v69 = v68;
                                          if ( v68 < 0 )
                                          {
                                            wil::details::in1diag3::Return_Hr(
                                              retaddr,
                                              (void *)0x8A,
                                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\att"
                                                            "estation\\attestationconfiguration.cpp",
                                              (const char *)(unsigned int)v68,
                                              v84);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                            return v69;
                                          }
                                        }
                                        v80 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v90 + 64))(v90, v88);
                                        v81 = v80;
                                        if ( v80 < 0 )
                                        {
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            (void *)0xAC,
                                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attes"
                                                          "tation\\attestationconfiguration.cpp",
                                            (const char *)(unsigned int)v80,
                                            v84);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                          return v81;
                                        }
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v94);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v93);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v95);
                                      }
                                      v82 = (*(__int64 (__fastcall **)(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, __int64 *))(*(_QWORD *)a2 + 104LL))(
                                              a2,
                                              v87);
                                      v83 = v82;
                                      if ( v82 >= 0 )
                                      {
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                        return 0;
                                      }
                                      else
                                      {
                                        wil::details::in1diag3::Return_Hr(
                                          retaddr,
                                          (void *)0xAF,
                                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attesta"
                                                        "tion\\attestationconfiguration.cpp",
                                          (const char *)(unsigned int)v82,
                                          v84);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                        return v83;
                                      }
                                    }
                                    else
                                    {
                                      wil::details::in1diag3::Return_Hr(
                                        retaddr,
                                        (void *)0x61,
                                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestati"
                                                      "on\\attestationconfiguration.cpp",
                                        (const char *)(unsigned int)v37,
                                        v84);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                      return v38;
                                    }
                                  }
                                  else
                                  {
                                    wil::details::in1diag3::Return_Hr(
                                      retaddr,
                                      (void *)0x5E,
                                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation"
                                                    "\\attestationconfiguration.cpp",
                                      (const char *)(unsigned int)v35,
                                      v84);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v90);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                    return v36;
                                  }
                                }
                                else
                                {
                                  wil::details::in1diag3::Return_Hr(
                                    retaddr,
                                    (void *)0x5B,
                                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\"
                                                  "attestationconfiguration.cpp",
                                    (const char *)(unsigned int)v32,
                                    v84);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v92);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                  return v33;
                                }
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0x55,
                                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\at"
                                                "testationconfiguration.cpp",
                                  (const char *)(unsigned int)v29,
                                  v84);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v91);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                                return v30;
                              }
                            }
                            else
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0x50,
                                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\atte"
                                              "stationconfiguration.cpp",
                                (const char *)(unsigned int)v26,
                                v84);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                              return v27;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x4F,
                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attest"
                                            "ationconfiguration.cpp",
                              (const char *)(unsigned int)v23,
                              v84);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v89);
                            return v24;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x4A,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestat"
                                          "ionconfiguration.cpp",
                            (const char *)(unsigned int)v20,
                            v84);
                          return v21;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x49,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestatio"
                                        "nconfiguration.cpp",
                          (const char *)(unsigned int)v17,
                          v84);
                        return v18;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x48,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationc"
                                      "onfiguration.cpp",
                        (const char *)(unsigned int)v15,
                        v84);
                      return v16;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x43,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
                      (const char *)(unsigned int)v13,
                      v84);
                    return v14;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x40,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
                    (const char *)(unsigned int)v11,
                    v84);
                  return v12;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3F,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
                  (const char *)(unsigned int)v9,
                  v84);
                return v10;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3B,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
                (const char *)0x80070057LL,
                v84);
              return 2147942487LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x39,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
              (const char *)(unsigned int)v7,
              v84);
            return v8;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x36,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
            (const char *)(unsigned int)v5,
            v84);
          return v6;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
          (const char *)0x80004003LL,
          v84);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
        (const char *)0x80004003LL,
        v84);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\attestation\\attestationconfiguration.cpp",
      (const char *)0x80004001LL,
      v84);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180109bd4  mov     [rsp+arg_10], rbx
0x180109bd9  mov     [rsp+arg_18], rsi
0x180109bde  push    rdi
0x180109bdf  push    r14
0x180109be1  push    r15
0x180109be3  sub     rsp, 0E0h
0x180109bea  mov     rax, cs:__security_cookie
0x180109bf1  xor     rax, rsp
0x180109bf4  mov     [rsp+0F8h+var_28], rax
0x180109bfc  mov     rbx, rdx
0x180109bff  mov     rdi, rcx
0x180109c02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180109c09  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180109c0e  xor     r15d, r15d
0x180109c11  test    al, al
0x180109c13  jz      loc_18010AFBF
0x180109c19  test    rdi, rdi
0x180109c1c  jnz     short loc_180109C44
0x180109c1e  mov     rcx, [rsp+0F8h]; this
0x180109c26  mov     ebx, 80004003h
0x180109c2b  mov     r9d, ebx; char *
0x180109c2e  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109c35  lea     edx, [rdi+31h]; void *
0x180109c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c3d  mov     eax, ebx
0x180109c3f  jmp     loc_18010AFEB
0x180109c44  test    rbx, rbx
0x180109c47  jnz     short loc_180109C71
0x180109c49  mov     rcx, [rsp+0F8h]; this
0x180109c51  mov     ebx, 80004003h
0x180109c56  mov     r9d, ebx; char *
0x180109c59  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109c60  mov     edx, 32h ; '2'; void *
0x180109c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c6a  mov     eax, ebx
0x180109c6c  jmp     loc_18010AFEB
0x180109c71  mov     [rsp+0F8h+var_40], r15d
0x180109c79  mov     rax, [rdi]
0x180109c7c  lea     rdx, [rsp+0F8h+var_40]
0x180109c84  mov     rcx, rdi
0x180109c87  mov     rax, [rax+40h]
0x180109c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c90  mov     esi, eax
0x180109c92  test    eax, eax
0x180109c94  jns     short loc_180109CB9
0x180109c96  mov     rcx, [rsp+0F8h]; this
0x180109c9e  mov     r9d, eax; char *
0x180109ca1  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109ca8  mov     edx, 36h ; '6'; void *
0x180109cad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109cb2  mov     eax, esi
0x180109cb4  jmp     loc_18010AFEB
0x180109cb9  mov     [rsp+0F8h+var_44], r15d
0x180109cc1  mov     rax, [rbx]
0x180109cc4  lea     rdx, [rsp+0F8h+var_44]
0x180109ccc  mov     rcx, rbx
0x180109ccf  mov     rax, [rax+40h]
0x180109cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cd8  mov     esi, eax
0x180109cda  test    eax, eax
0x180109cdc  jns     short loc_180109D01
0x180109cde  mov     rcx, [rsp+0F8h]; this
0x180109ce6  mov     r9d, eax; char *
0x180109ce9  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109cf0  mov     edx, 39h ; '9'; void *
0x180109cf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109cfa  mov     eax, esi
0x180109cfc  jmp     loc_18010AFEB
0x180109d01  mov     eax, [rsp+0F8h+var_44]
0x180109d08  cmp     [rsp+0F8h+var_40], eax
0x180109d0f  jz      short loc_180109D39
0x180109d11  mov     rcx, [rsp+0F8h]; this
0x180109d19  mov     ebx, 80070057h
0x180109d1e  mov     r9d, ebx; char *
0x180109d21  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109d28  mov     edx, 3Bh ; ';'; void *
0x180109d2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109d32  mov     eax, ebx
0x180109d34  jmp     loc_18010AFEB
0x180109d39  mov     dword ptr [rsp+0F8h+var_3C+4], r15d
0x180109d41  mov     dword ptr [rsp+0F8h+var_3C], r15d
0x180109d49  mov     rax, [rdi]
0x180109d4c  lea     rdx, [rsp+0F8h+var_3C+4]
0x180109d54  mov     rcx, rdi
0x180109d57  mov     rax, [rax+30h]
0x180109d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d60  mov     esi, eax
0x180109d62  test    eax, eax
0x180109d64  jns     short loc_180109D89
0x180109d66  mov     rcx, [rsp+0F8h]; this
0x180109d6e  mov     r9d, eax; char *
0x180109d71  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109d78  mov     edx, 3Fh ; '?'; void *
0x180109d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109d82  mov     eax, esi
0x180109d84  jmp     loc_18010AFEB
0x180109d89  mov     rax, [rbx]
0x180109d8c  lea     rdx, [rsp+0F8h+var_3C]
0x180109d94  mov     rcx, rbx
0x180109d97  mov     rax, [rax+30h]
0x180109d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109da0  mov     esi, eax
0x180109da2  test    eax, eax
0x180109da4  jns     short loc_180109DC9
0x180109da6  mov     rcx, [rsp+0F8h]; this
0x180109dae  mov     r9d, eax; char *
0x180109db1  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109db8  mov     edx, 40h ; '@'; void *
0x180109dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109dc2  mov     eax, esi
0x180109dc4  jmp     loc_18010AFEB
0x180109dc9  mov     rax, [rbx]
0x180109dcc  mov     edx, dword ptr [rsp+0F8h+var_3C]
0x180109dd3  or      edx, dword ptr [rsp+0F8h+var_3C+4]
0x180109dda  mov     rcx, rbx
0x180109ddd  mov     rax, [rax+38h]
0x180109de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109de6  mov     esi, eax
0x180109de8  test    eax, eax
0x180109dea  jns     short loc_180109E0F
0x180109dec  mov     rcx, [rsp+0F8h]; this
0x180109df4  mov     r9d, eax; char *
0x180109df7  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109dfe  mov     edx, 43h ; 'C'; void *
0x180109e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109e08  mov     eax, esi
0x180109e0a  jmp     loc_18010AFEB
0x180109e0f  mov     [rsp+0F8h+var_48], r15d
0x180109e17  mov     [rsp+0F8h+var_34], r15d
0x180109e1f  mov     rax, [rdi]
0x180109e22  lea     rdx, [rsp+0F8h+var_48]
0x180109e2a  mov     rcx, rdi
0x180109e2d  mov     rax, [rax+50h]
0x180109e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109e36  mov     esi, eax
0x180109e38  test    eax, eax
0x180109e3a  jns     short loc_180109E5F
0x180109e3c  mov     rcx, [rsp+0F8h]; this
0x180109e44  mov     r9d, eax; char *
0x180109e47  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109e4e  mov     edx, 48h ; 'H'; void *
0x180109e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109e58  mov     eax, esi
0x180109e5a  jmp     loc_18010AFEB
0x180109e5f  mov     rax, [rbx]
0x180109e62  lea     rdx, [rsp+0F8h+var_34]
0x180109e6a  mov     rcx, rbx
0x180109e6d  mov     rax, [rax+50h]
0x180109e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109e76  mov     esi, eax
0x180109e78  test    eax, eax
0x180109e7a  jns     short loc_180109E9F
0x180109e7c  mov     rcx, [rsp+0F8h]; this
0x180109e84  mov     r9d, eax; char *
0x180109e87  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109e8e  mov     edx, 49h ; 'I'; void *
0x180109e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109e98  mov     eax, esi
0x180109e9a  jmp     loc_18010AFEB
0x180109e9f  mov     rax, [rbx]
0x180109ea2  mov     edx, [rsp+0F8h+var_34]
0x180109ea9  cmp     [rsp+0F8h+var_48], edx
0x180109eb0  cmova   edx, [rsp+0F8h+var_48]
0x180109eb8  mov     rcx, rbx
0x180109ebb  mov     rax, [rax+58h]
0x180109ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109ec4  mov     esi, eax
0x180109ec6  test    eax, eax
0x180109ec8  jns     short loc_180109EED
0x180109eca  mov     rcx, [rsp+0F8h]; this
0x180109ed2  mov     r9d, eax; char *
0x180109ed5  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109edc  mov     edx, 4Ah ; 'J'; void *
0x180109ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ee6  mov     eax, esi
0x180109ee8  jmp     loc_18010AFEB
0x180109eed  mov     [rsp+0F8h+var_A8], r15
0x180109ef2  mov     rax, [rdi]
0x180109ef5  mov     [rsp+0F8h+var_98], r15
0x180109efa  lea     rdx, [rsp+0F8h+var_98]
0x180109eff  mov     rcx, rdi
0x180109f02  mov     rax, [rax+60h]
0x180109f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f0b  mov     edi, eax
0x180109f0d  test    eax, eax
0x180109f0f  jns     short loc_180109F4A
0x180109f11  mov     rcx, [rsp+0F8h]; this
0x180109f19  mov     r9d, eax; char *
0x180109f1c  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109f23  mov     edx, 4Fh ; 'O'; void *
0x180109f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109f2d  nop
0x180109f2e  lea     rcx, [rsp+0F8h+var_A8]
0x180109f33  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180109f38  nop
0x180109f39  lea     rcx, [rsp+0F8h+var_98]
0x180109f3e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180109f43  mov     eax, edi
0x180109f45  jmp     loc_18010AFEB
0x180109f4a  mov     rax, [rbx]
0x180109f4d  mov     rdi, [rax+60h]
0x180109f51  mov     rcx, [rsp+0F8h+var_A8]
0x180109f56  mov     [rsp+0F8h+var_A8], r15
0x180109f5b  test    rcx, rcx
0x180109f5e  jz      short loc_180109F6D
0x180109f60  mov     rdx, [rcx]
0x180109f63  mov     rax, [rdx+10h]
0x180109f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f6c  nop
0x180109f6d  lea     rdx, [rsp+0F8h+var_A8]
0x180109f72  mov     rcx, rbx
0x180109f75  mov     rax, rdi
0x180109f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f7d  mov     edi, eax
0x180109f7f  test    eax, eax
0x180109f81  jns     short loc_180109FBC
0x180109f83  mov     rcx, [rsp+0F8h]; this
0x180109f8b  mov     r9d, eax; char *
0x180109f8e  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109f95  mov     edx, 50h ; 'P'; void *
0x180109f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109f9f  nop
0x180109fa0  lea     rcx, [rsp+0F8h+var_A8]
0x180109fa5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180109faa  nop
0x180109fab  lea     rcx, [rsp+0F8h+var_98]
0x180109fb0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180109fb5  mov     eax, edi
0x180109fb7  jmp     loc_18010AFEB
0x180109fbc  mov     [rsp+0F8h+var_88], r15
0x180109fc1  mov     rcx, [rsp+0F8h+var_98]
0x180109fc6  mov     rax, [rcx]
0x180109fc9  mov     [rsp+0F8h+var_88], r15
0x180109fce  lea     rdx, [rsp+0F8h+var_88]
0x180109fd3  mov     rax, [rax+48h]
0x180109fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109fdc  mov     edi, eax
0x180109fde  test    eax, eax
0x180109fe0  jns     short loc_18010A026
0x180109fe2  mov     rcx, [rsp+0F8h]; this
0x180109fea  mov     r9d, eax; char *
0x180109fed  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x180109ff4  mov     edx, 55h ; 'U'; void *
0x180109ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ffe  nop
0x180109fff  lea     rcx, [rsp+0F8h+var_88]
0x18010a004  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a009  nop
0x18010a00a  lea     rcx, [rsp+0F8h+var_A8]
0x18010a00f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a014  nop
0x18010a015  lea     rcx, [rsp+0F8h+var_98]
0x18010a01a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a01f  mov     eax, edi
0x18010a021  jmp     loc_18010AFEB
0x18010a026  mov     [rsp+0F8h+var_80], r15
0x18010a02b  mov     rcx, [rsp+0F8h+var_88]
0x18010a030  mov     rax, [rcx]
0x18010a033  mov     [rsp+0F8h+var_80], r15
0x18010a038  lea     r8, [rsp+0F8h+var_80]
0x18010a03d  lea     rdx, _GUID_a34fe5b1_df9f_55c5_9ec9_09dd9170a8ce
0x18010a044  mov     rax, [rax]
0x18010a047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a04c  mov     edi, eax
0x18010a04e  test    eax, eax
0x18010a050  jns     short loc_18010A0A1
0x18010a052  mov     rcx, [rsp+0F8h]; this
0x18010a05a  mov     r9d, eax; char *
0x18010a05d  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010a064  mov     edx, 5Bh ; '['; void *
0x18010a069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a06e  nop
0x18010a06f  lea     rcx, [rsp+0F8h+var_80]
0x18010a074  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a079  nop
0x18010a07a  lea     rcx, [rsp+0F8h+var_88]
0x18010a07f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a084  nop
0x18010a085  lea     rcx, [rsp+0F8h+var_A8]
0x18010a08a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a08f  nop
0x18010a090  lea     rcx, [rsp+0F8h+var_98]
0x18010a095  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010a09a  mov     eax, edi
0x18010a09c  jmp     loc_18010AFEB
0x18010a0a1  mov     [rsp+0F8h+var_90], r15
0x18010a0a6  mov     rcx, [rsp+0F8h+var_80]
0x18010a0ab  mov     rax, [rcx]
0x18010a0ae  mov     [rsp+0F8h+var_90], r15
0x18010a0b3  lea     rdx, [rsp+0F8h+var_90]
0x18010a0b8  mov     rax, [rax+30h]
0x18010a0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a0c1  mov     edi, eax
0x18010a0c3  test    eax, eax
0x18010a0c5  jns     short loc_18010A121
0x18010a0c7  mov     rcx, [rsp+0F8h]; this
0x18010a0cf  mov     r9d, eax; char *
0x18010a0d2  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010a0d9  mov     edx, 5Eh ; '^'; void *
0x18010a0de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
