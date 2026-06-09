# ModernDeployment::Autopilot::Core::AttestationConfiguration::MergeConfigurations(ModernDeployment::Autopilot::Core::IAttestationConfiguration *,ModernDeployment::Autopilot::Core::IAttestationConfiguration *)

- ea: `0x18010d068`
- end: `0x18010e4a9`
- name: `?MergeConfigurations@AttestationConfiguration@Core@Autopilot@ModernDeployment@@SAJPEAUIAttestationConfiguration@234@0@Z`
- size: `5185`
- prototype: `__int64 __fastcall(struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *, struct ModernDeployment::Autopilot::Core::IAttestationConfiguration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18011b610`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x180080c10`
- `0x1800d2334`
- `0x18010ac60`
- `0x18010d068`
- `0x180200010`

## string_xrefs

- `0x18010d0c2`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d0ed`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d135`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d17d`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d1b5`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d205`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d245`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d28b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d2db`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d31b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d369`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d3b0`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d422`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d481`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d4f1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d566`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d5e1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d675`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d707`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d7a1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d88f`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d939`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010d9e3`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010daa5`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010db4f`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010dbf9`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010dce0`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010dd84`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010de29`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010def7`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010dfa1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010e04b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010e11b`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010e1e1`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010e29a`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010e3cd`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`
- `0x18010e463`: `onecoreuap\admin\moderndeployment\autopilot\service\attestation\attestationconfiguration.cpp`

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
0x18010d068  mov     [rsp+arg_10], rbx
0x18010d06d  mov     [rsp+arg_18], rsi
0x18010d072  push    rdi
0x18010d073  push    r14
0x18010d075  push    r15
0x18010d077  sub     rsp, 0E0h
0x18010d07e  mov     rax, cs:__security_cookie
0x18010d085  xor     rax, rsp
0x18010d088  mov     [rsp+0F8h+var_28], rax
0x18010d090  mov     rbx, rdx
0x18010d093  mov     rdi, rcx
0x18010d096  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18010d09d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010d0a2  xor     r15d, r15d
0x18010d0a5  test    al, al
0x18010d0a7  jz      loc_18010E453
0x18010d0ad  test    rdi, rdi
0x18010d0b0  jnz     short loc_18010D0D8
0x18010d0b2  mov     rcx, [rsp+0F8h]; this
0x18010d0ba  mov     ebx, 80004003h
0x18010d0bf  mov     r9d, ebx; char *
0x18010d0c2  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d0c9  lea     edx, [rdi+31h]; void *
0x18010d0cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d0d1  mov     eax, ebx
0x18010d0d3  jmp     loc_18010E47F
0x18010d0d8  test    rbx, rbx
0x18010d0db  jnz     short loc_18010D105
0x18010d0dd  mov     rcx, [rsp+0F8h]; this
0x18010d0e5  mov     ebx, 80004003h
0x18010d0ea  mov     r9d, ebx; char *
0x18010d0ed  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d0f4  mov     edx, 32h ; '2'; void *
0x18010d0f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d0fe  mov     eax, ebx
0x18010d100  jmp     loc_18010E47F
0x18010d105  mov     [rsp+0F8h+var_40], r15d
0x18010d10d  mov     rax, [rdi]
0x18010d110  lea     rdx, [rsp+0F8h+var_40]
0x18010d118  mov     rcx, rdi
0x18010d11b  mov     rax, [rax+40h]
0x18010d11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d124  mov     esi, eax
0x18010d126  test    eax, eax
0x18010d128  jns     short loc_18010D14D
0x18010d12a  mov     rcx, [rsp+0F8h]; this
0x18010d132  mov     r9d, eax; char *
0x18010d135  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d13c  mov     edx, 36h ; '6'; void *
0x18010d141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d146  mov     eax, esi
0x18010d148  jmp     loc_18010E47F
0x18010d14d  mov     [rsp+0F8h+var_44], r15d
0x18010d155  mov     rax, [rbx]
0x18010d158  lea     rdx, [rsp+0F8h+var_44]
0x18010d160  mov     rcx, rbx
0x18010d163  mov     rax, [rax+40h]
0x18010d167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d16c  mov     esi, eax
0x18010d16e  test    eax, eax
0x18010d170  jns     short loc_18010D195
0x18010d172  mov     rcx, [rsp+0F8h]; this
0x18010d17a  mov     r9d, eax; char *
0x18010d17d  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d184  mov     edx, 39h ; '9'; void *
0x18010d189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d18e  mov     eax, esi
0x18010d190  jmp     loc_18010E47F
0x18010d195  mov     eax, [rsp+0F8h+var_44]
0x18010d19c  cmp     [rsp+0F8h+var_40], eax
0x18010d1a3  jz      short loc_18010D1CD
0x18010d1a5  mov     rcx, [rsp+0F8h]; this
0x18010d1ad  mov     ebx, 80070057h
0x18010d1b2  mov     r9d, ebx; char *
0x18010d1b5  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d1bc  mov     edx, 3Bh ; ';'; void *
0x18010d1c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d1c6  mov     eax, ebx
0x18010d1c8  jmp     loc_18010E47F
0x18010d1cd  mov     dword ptr [rsp+0F8h+var_3C+4], r15d
0x18010d1d5  mov     dword ptr [rsp+0F8h+var_3C], r15d
0x18010d1dd  mov     rax, [rdi]
0x18010d1e0  lea     rdx, [rsp+0F8h+var_3C+4]
0x18010d1e8  mov     rcx, rdi
0x18010d1eb  mov     rax, [rax+30h]
0x18010d1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d1f4  mov     esi, eax
0x18010d1f6  test    eax, eax
0x18010d1f8  jns     short loc_18010D21D
0x18010d1fa  mov     rcx, [rsp+0F8h]; this
0x18010d202  mov     r9d, eax; char *
0x18010d205  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d20c  mov     edx, 3Fh ; '?'; void *
0x18010d211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d216  mov     eax, esi
0x18010d218  jmp     loc_18010E47F
0x18010d21d  mov     rax, [rbx]
0x18010d220  lea     rdx, [rsp+0F8h+var_3C]
0x18010d228  mov     rcx, rbx
0x18010d22b  mov     rax, [rax+30h]
0x18010d22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d234  mov     esi, eax
0x18010d236  test    eax, eax
0x18010d238  jns     short loc_18010D25D
0x18010d23a  mov     rcx, [rsp+0F8h]; this
0x18010d242  mov     r9d, eax; char *
0x18010d245  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d24c  mov     edx, 40h ; '@'; void *
0x18010d251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d256  mov     eax, esi
0x18010d258  jmp     loc_18010E47F
0x18010d25d  mov     rax, [rbx]
0x18010d260  mov     edx, dword ptr [rsp+0F8h+var_3C]
0x18010d267  or      edx, dword ptr [rsp+0F8h+var_3C+4]
0x18010d26e  mov     rcx, rbx
0x18010d271  mov     rax, [rax+38h]
0x18010d275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d27a  mov     esi, eax
0x18010d27c  test    eax, eax
0x18010d27e  jns     short loc_18010D2A3
0x18010d280  mov     rcx, [rsp+0F8h]; this
0x18010d288  mov     r9d, eax; char *
0x18010d28b  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d292  mov     edx, 43h ; 'C'; void *
0x18010d297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d29c  mov     eax, esi
0x18010d29e  jmp     loc_18010E47F
0x18010d2a3  mov     [rsp+0F8h+var_48], r15d
0x18010d2ab  mov     [rsp+0F8h+var_34], r15d
0x18010d2b3  mov     rax, [rdi]
0x18010d2b6  lea     rdx, [rsp+0F8h+var_48]
0x18010d2be  mov     rcx, rdi
0x18010d2c1  mov     rax, [rax+50h]
0x18010d2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d2ca  mov     esi, eax
0x18010d2cc  test    eax, eax
0x18010d2ce  jns     short loc_18010D2F3
0x18010d2d0  mov     rcx, [rsp+0F8h]; this
0x18010d2d8  mov     r9d, eax; char *
0x18010d2db  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d2e2  mov     edx, 48h ; 'H'; void *
0x18010d2e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d2ec  mov     eax, esi
0x18010d2ee  jmp     loc_18010E47F
0x18010d2f3  mov     rax, [rbx]
0x18010d2f6  lea     rdx, [rsp+0F8h+var_34]
0x18010d2fe  mov     rcx, rbx
0x18010d301  mov     rax, [rax+50h]
0x18010d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d30a  mov     esi, eax
0x18010d30c  test    eax, eax
0x18010d30e  jns     short loc_18010D333
0x18010d310  mov     rcx, [rsp+0F8h]; this
0x18010d318  mov     r9d, eax; char *
0x18010d31b  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d322  mov     edx, 49h ; 'I'; void *
0x18010d327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d32c  mov     eax, esi
0x18010d32e  jmp     loc_18010E47F
0x18010d333  mov     rax, [rbx]
0x18010d336  mov     edx, [rsp+0F8h+var_34]
0x18010d33d  cmp     [rsp+0F8h+var_48], edx
0x18010d344  cmova   edx, [rsp+0F8h+var_48]
0x18010d34c  mov     rcx, rbx
0x18010d34f  mov     rax, [rax+58h]
0x18010d353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d358  mov     esi, eax
0x18010d35a  test    eax, eax
0x18010d35c  jns     short loc_18010D381
0x18010d35e  mov     rcx, [rsp+0F8h]; this
0x18010d366  mov     r9d, eax; char *
0x18010d369  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d370  mov     edx, 4Ah ; 'J'; void *
0x18010d375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d37a  mov     eax, esi
0x18010d37c  jmp     loc_18010E47F
0x18010d381  mov     [rsp+0F8h+var_A8], r15
0x18010d386  mov     rax, [rdi]
0x18010d389  mov     [rsp+0F8h+var_98], r15
0x18010d38e  lea     rdx, [rsp+0F8h+var_98]
0x18010d393  mov     rcx, rdi
0x18010d396  mov     rax, [rax+60h]
0x18010d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d39f  mov     edi, eax
0x18010d3a1  test    eax, eax
0x18010d3a3  jns     short loc_18010D3DE
0x18010d3a5  mov     rcx, [rsp+0F8h]; this
0x18010d3ad  mov     r9d, eax; char *
0x18010d3b0  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d3b7  mov     edx, 4Fh ; 'O'; void *
0x18010d3bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d3c1  nop
0x18010d3c2  lea     rcx, [rsp+0F8h+var_A8]
0x18010d3c7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d3cc  nop
0x18010d3cd  lea     rcx, [rsp+0F8h+var_98]
0x18010d3d2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d3d7  mov     eax, edi
0x18010d3d9  jmp     loc_18010E47F
0x18010d3de  mov     rax, [rbx]
0x18010d3e1  mov     rdi, [rax+60h]
0x18010d3e5  mov     rcx, [rsp+0F8h+var_A8]
0x18010d3ea  mov     [rsp+0F8h+var_A8], r15
0x18010d3ef  test    rcx, rcx
0x18010d3f2  jz      short loc_18010D401
0x18010d3f4  mov     rdx, [rcx]
0x18010d3f7  mov     rax, [rdx+10h]
0x18010d3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d400  nop
0x18010d401  lea     rdx, [rsp+0F8h+var_A8]
0x18010d406  mov     rcx, rbx
0x18010d409  mov     rax, rdi
0x18010d40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d411  mov     edi, eax
0x18010d413  test    eax, eax
0x18010d415  jns     short loc_18010D450
0x18010d417  mov     rcx, [rsp+0F8h]; this
0x18010d41f  mov     r9d, eax; char *
0x18010d422  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d429  mov     edx, 50h ; 'P'; void *
0x18010d42e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d433  nop
0x18010d434  lea     rcx, [rsp+0F8h+var_A8]
0x18010d439  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d43e  nop
0x18010d43f  lea     rcx, [rsp+0F8h+var_98]
0x18010d444  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d449  mov     eax, edi
0x18010d44b  jmp     loc_18010E47F
0x18010d450  mov     [rsp+0F8h+var_88], r15
0x18010d455  mov     rcx, [rsp+0F8h+var_98]
0x18010d45a  mov     rax, [rcx]
0x18010d45d  mov     [rsp+0F8h+var_88], r15
0x18010d462  lea     rdx, [rsp+0F8h+var_88]
0x18010d467  mov     rax, [rax+48h]
0x18010d46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d470  mov     edi, eax
0x18010d472  test    eax, eax
0x18010d474  jns     short loc_18010D4BA
0x18010d476  mov     rcx, [rsp+0F8h]; this
0x18010d47e  mov     r9d, eax; char *
0x18010d481  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d488  mov     edx, 55h ; 'U'; void *
0x18010d48d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d492  nop
0x18010d493  lea     rcx, [rsp+0F8h+var_88]
0x18010d498  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d49d  nop
0x18010d49e  lea     rcx, [rsp+0F8h+var_A8]
0x18010d4a3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d4a8  nop
0x18010d4a9  lea     rcx, [rsp+0F8h+var_98]
0x18010d4ae  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d4b3  mov     eax, edi
0x18010d4b5  jmp     loc_18010E47F
0x18010d4ba  mov     [rsp+0F8h+var_80], r15
0x18010d4bf  mov     rcx, [rsp+0F8h+var_88]
0x18010d4c4  mov     rax, [rcx]
0x18010d4c7  mov     [rsp+0F8h+var_80], r15
0x18010d4cc  lea     r8, [rsp+0F8h+var_80]
0x18010d4d1  lea     rdx, _GUID_a34fe5b1_df9f_55c5_9ec9_09dd9170a8ce
0x18010d4d8  mov     rax, [rax]
0x18010d4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d4e0  mov     edi, eax
0x18010d4e2  test    eax, eax
0x18010d4e4  jns     short loc_18010D535
0x18010d4e6  mov     rcx, [rsp+0F8h]; this
0x18010d4ee  mov     r9d, eax; char *
0x18010d4f1  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d4f8  mov     edx, 5Bh ; '['; void *
0x18010d4fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d502  nop
0x18010d503  lea     rcx, [rsp+0F8h+var_80]
0x18010d508  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d50d  nop
0x18010d50e  lea     rcx, [rsp+0F8h+var_88]
0x18010d513  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d518  nop
0x18010d519  lea     rcx, [rsp+0F8h+var_A8]
0x18010d51e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d523  nop
0x18010d524  lea     rcx, [rsp+0F8h+var_98]
0x18010d529  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18010d52e  mov     eax, edi
0x18010d530  jmp     loc_18010E47F
0x18010d535  mov     [rsp+0F8h+var_90], r15
0x18010d53a  mov     rcx, [rsp+0F8h+var_80]
0x18010d53f  mov     rax, [rcx]
0x18010d542  mov     [rsp+0F8h+var_90], r15
0x18010d547  lea     rdx, [rsp+0F8h+var_90]
0x18010d54c  mov     rax, [rax+30h]
0x18010d550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d555  mov     edi, eax
0x18010d557  test    eax, eax
0x18010d559  jns     short loc_18010D5B5
0x18010d55b  mov     rcx, [rsp+0F8h]; this
0x18010d563  mov     r9d, eax; char *
0x18010d566  lea     r8, aOnecoreuapAdmi_138; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010d56d  mov     edx, 5Eh ; '^'; void *
0x18010d572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
