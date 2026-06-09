# InstallServiceTaskHelpers::CreateAppInUseForceRestartTaskIfNecessary(void)

- ea: `0x180100808`
- end: `0x18010144f`
- name: `?CreateAppInUseForceRestartTaskIfNecessary@InstallServiceTaskHelpers@@YAXXZ`
- size: `3143`
- prototype: `void __fastcall(InstallServiceTaskHelpers *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800613ac`
- `0x1800eae04`
- `0x180101504`
- `0x180168484`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800127c8`
- `0x18002ec2c`
- `0x1800370f4`
- `0x18003e0c4`
- `0x180051798`
- `0x180063648`
- `0x1801005c8`
- `0x180100808`
- `0x180215010`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180100a64`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180100a64`
- `msvcp_win!_Xtime_get_ticks` at `0x18010086f`
- `msvcp_win!_Xtime_get_ticks` at `0x18010086f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180100928`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180100928`

## string_xrefs

- `0x180100a2d`: `Microsoft\Windows\InstallService`
- `0x180100ba8`: `\n<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n  <RegistrationInfo>\n    <Version>1.0</Version>\n    <URI>\\Microsoft\\Windows\\InstallService\\SmartRetryByPolicy</URI>\n    <SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;GRGX;;;SU)</SecurityDescriptor>\n  </RegistrationInfo>\n  <Triggers>\n  </Triggers>\n  <Principals>\n    <Principal id="LocalSystem">\n      <UserId>S-1-5-18</UserId>\n      <RunLevel>HighestAvailable</RunLevel>\n    </Principal>\n  </Principals>\n  `
- `0x18010093d`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x1801009f3`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100a4e`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100ab6`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100aff`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100b37`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100b8f`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100bca`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100c22`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100c67`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100cb2`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100cf0`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100d40`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100d92`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100dd1`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100e2e`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100e70`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100ed1`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100f23`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100f5c`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100fb9`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180100ffb`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x18010105c`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180101090`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x1801010ed`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x18010112f`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180101195`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x1801011e7`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180101244`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180101286`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x180101383`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x1801013bc`: `onecoreuap\enduser\winstore\installservice\lib\taskhelpers.cpp`
- `0x18010139e`: `Successfully created SmartRetryCSP task.`
- `0x1801013af`: `InstallServiceTaskHelpers::CreateAppInUseForceRestartTaskIfNecessary`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall InstallServiceTaskHelpers::CreateAppInUseForceRestartTaskIfNecessary(InstallServiceTaskHelpers *this)
{
  __int64 ForceAppRestartPolicy; // rax
  __m128i v2; // xmm6
  __m128i v3; // xmm8
  __int64 ticks; // rax
  int v5; // esi
  __int8 v6; // r15
  HRESULT v7; // eax
  int v8; // eax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, const wchar_t *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, _QWORD, __int64 *); // rbx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, __int64 *); // rbx
  int v30; // eax
  int v31; // esi
  int v32; // esi
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, _QWORD); // rbx
  int v35; // eax
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v37)(_QWORD, GUID *, __int64 *); // rdi
  int v38; // eax
  int v39; // eax
  __int64 v40; // rbx
  __int64 (__fastcall *v41)(__int64, _QWORD); // rdi
  __int64 v42; // rax
  _QWORD *v43; // rax
  int v44; // eax
  int v45; // eax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, __int64, _QWORD); // rbx
  int v48; // eax
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v50)(_QWORD, GUID *, __int64 *); // rdi
  int v51; // eax
  int v52; // eax
  __int64 v53; // rbx
  __int64 (__fastcall *v54)(__int64, _QWORD); // rdi
  __int64 v55; // rax
  _QWORD *v56; // rax
  int v57; // eax
  int v58; // eax
  __int64 v59; // rdi
  __int64 (__fastcall *v60)(__int64, __int64, __int64 *); // rbx
  int v61; // eax
  int v62; // eax
  __int64 (__fastcall ***v63)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v64)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v65; // rax
  _QWORD *bstr; // rax
  int v67; // eax
  int v68; // eax
  __int64 *v69; // rcx
  __int64 v70; // rdi
  __int64 (__fastcall *v71)(__int64, __int64, _QWORD); // rbx
  int v72; // eax
  __int64 (__fastcall ***v73)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v74)(_QWORD, GUID *, __int64 *); // rdi
  int v75; // eax
  __int64 v76; // rbx
  __int64 (__fastcall *v77)(__int64, _QWORD); // rdi
  __int64 v78; // rax
  _QWORD *v79; // rax
  int v80; // eax
  int v81; // eax
  __int64 v82; // rdi
  __int64 (__fastcall *v83)(__int64, const wchar_t *, __int64, __int64); // rbx
  int v84; // eax
  const char *v85; // r9
  int ppv; // [rsp+20h] [rbp-1B8h]
  __int64 v87; // [rsp+50h] [rbp-188h] BYREF
  __int64 (__fastcall ***v88)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-180h] BYREF
  __int64 v89; // [rsp+60h] [rbp-178h] BYREF
  __int64 v90; // [rsp+68h] [rbp-170h] BYREF
  char v91[8]; // [rsp+70h] [rbp-168h] BYREF
  LPVOID v92; // [rsp+78h] [rbp-160h] BYREF
  __int64 v93; // [rsp+80h] [rbp-158h] BYREF
  __int64 v94; // [rsp+88h] [rbp-150h] BYREF
  __int64 v95; // [rsp+90h] [rbp-148h] BYREF
  __m128i v96; // [rsp+98h] [rbp-140h]
  __m128i v97; // [rsp+A8h] [rbp-130h]
  int v98[4]; // [rsp+C0h] [rbp-118h] BYREF
  __int64 v99; // [rsp+D0h] [rbp-108h]
  __int128 v100; // [rsp+E0h] [rbp-F8h] BYREF
  __int64 v101; // [rsp+F0h] [rbp-E8h]
  int v102[4]; // [rsp+100h] [rbp-D8h] BYREF
  __int64 v103; // [rsp+110h] [rbp-C8h]
  wchar_t Buffer[8]; // [rsp+120h] [rbp-B8h] BYREF
  __int64 v105; // [rsp+130h] [rbp-A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  ForceAppRestartPolicy = GetForceAppRestartPolicy(Buffer);
  v2 = *(__m128i *)ForceAppRestartPolicy;
  v96 = *(__m128i *)ForceAppRestartPolicy;
  v3 = *(__m128i *)(ForceAppRestartPolicy + 16);
  v97 = v3;
  if ( !(unsigned __int8)*(_DWORD *)(ForceAppRestartPolicy + 24) )
    return;
  ticks = _Xtime_get_ticks();
  if ( v96.m128i_i64[0] >= ticks )
  {
    v6 = v96.m128i_i8[12];
    v5 = v96.m128i_i32[2];
  }
  else
  {
    v5 = _mm_cvtsi128_si32(_mm_srli_si128(v2, 8));
    if ( !v5 )
      return;
    v6 = _mm_cvtsi128_si32(_mm_srli_si128(v2, 12));
    if ( v6 )
      v96.m128i_i64[0] += 36000000000LL * (24 * ((ticks - v96.m128i_i64[0]) / 36000000000LL / 24) + 24);
  }
  v92 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v92);
  v7 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v92);
  try
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    *(_OWORD *)v102 = 0;
    v103 = 0;
    *(_OWORD *)v98 = 0;
    v99 = 0;
    v100 = 0;
    v101 = 0;
    *(_OWORD *)Buffer = 0;
    v105 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, __int128 *, int *))(*(_QWORD *)v92 + 80LL))(
           v92,
           Buffer,
           &v100,
           v98);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v8,
        (int)v102);
    v93 = 0;
    v9 = v92;
    v10 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v92 + 56LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v93);
    v11 = v10(v9, L"Microsoft\\Windows\\InstallService", &v93);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v11,
        (int)v102);
    v89 = 0;
    if ( (unsigned __int8)RtlIsStateSeparationEnabled(retaddr) )
    {
      v87 = 0;
      v12 = v93;
      v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v93 + 104LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
      v14 = v13(v12, L"SmartRetryCSP", &v87);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v14,
          (int)v102);
      v15 = v87;
      v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v87 + 152LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v89);
      v17 = v16(v15, &v89);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v17,
          (int)v102);
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 88LL))(v87, 0xFFFFFFFFLL);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v18,
          (int)v102);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
    }
    else
    {
      v19 = v92;
      v20 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v92 + 72LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v89);
      v21 = v20(v19, 0, &v89);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v21,
          (int)v102);
      v22 = (*(__int64 (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v89 + 160LL))(
              v89,
              L"\n"
               "<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\n"
               "  <RegistrationInfo>\n"
               "    <Version>1.0</Version>\n"
               "    <URI>\\\\Microsoft\\\\Windows\\\\InstallService\\\\SmartRetryByPolicy</URI>\n"
               "    <SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;GRGX;;;SU)</SecurityDescriptor>\n"
               "  </RegistrationInfo>\n"
               "  <Triggers>\n"
               "  </Triggers>\n"
               "  <Principals>\n"
               "    <Principal id=\"LocalSystem\">\n"
               "      <UserId>S-1-5-18</UserId>\n"
               "      <RunLevel>HighestAvailable</RunLevel>\n"
               "    </Principal>\n"
               "  </Principals>\n"
               "  <Settings>\n"
               "    <MultipleInstancesPolicy>Queue</MultipleInstancesPolicy>\n"
               "    <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
               "    <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
               "    <AllowHardTerminate>true</AllowHardTerminate>\n"
               "    <RunOnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable>\n"
               "    <AllowStartOnDemand>true</AllowStartOnDemand>\n"
               "    <Enabled>true</Enabled>\n"
               "    <Hidden>false</Hidden>\n"
               "    <DisallowStartOnRemoteAppSession>true</DisallowStartOnRemoteAppSession>\n"
               "    <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
               "    <WakeToRun>false</WakeToRun>\n"
               "    <ExecutionTimeLimit>PT1H</ExecutionTimeLimit>\n"
               "    <Priority>7</Priority>\n"
               "  </Settings>\n"
               "  <Actions Context=\"LocalSystem\">\n"
               "    <Exec>\n"
               "      <Command>%windir%\\\\system32\\\\rundll32.exe</Command>\n"
               "      <Arguments>%windir%\\\\system32\\\\InstallServiceTasks.dll,ForceAppInUseRestart</Arguments>\n"
               "    </Exec>\n"
               "  </Actions>\n"
               "</Task>\n");
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v22,
          (int)v102);
    }
    v94 = 0;
    v23 = v89;
    v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 88LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v94);
    v25 = v24(v23, &v94);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v25,
        (int)v102);
    if ( v6 )
      v26 = 0xFFFF;
    else
      v26 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 176LL))(v94, v26);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v27,
        (int)v102);
    v90 = 0;
    v28 = v89;
    v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 72LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v90);
    v30 = v29(v28, &v90);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v30,
        (int)v102);
    if ( v5 )
    {
      v31 = v5 - 1;
      if ( !v31 )
      {
        v87 = 0;
        v59 = v90;
        v60 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v90 + 80LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
        v61 = v60(v59, 2, &v87);
        if ( v61 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v61,
            (int)v102);
        v88 = 0;
        v62 = Microsoft::WRL::ComPtr<ITrigger>::As<IDailyTrigger>(&v87, &v88);
        if ( v62 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v62,
            (int)v102);
        v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
        v64 = (*v88)[15];
        v65 = time_point_iso8601::time_point_iso8601(Buffer);
        bstr = (_QWORD *)wil::make_bstr(v91, v65);
        v67 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v64)(v63, *bstr);
        if ( v67 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDF,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v67,
            (int)v102);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v91);
        v68 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v88)[19])(
                v88,
                0xFFFFFFFFLL);
        if ( v68 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE0,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v68,
            (int)v102);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v88);
        v69 = &v87;
        goto LABEL_78;
      }
      v32 = v31 - 1;
      if ( v32 )
      {
        if ( v32 != 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)0x8007000DLL,
            (int)v102);
        v88 = 0;
        v33 = v90;
        v34 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v90 + 80LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v88);
        v35 = v34(v33, 4, &v88);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v35,
            (int)v102);
        v87 = 0;
        v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
        v37 = **v88;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
        v38 = v37(v36, &GUID_97c45ef1_6b02_4a1a_9c0e_1ebfba1500ac, &v87);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF5,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v38,
            (int)v102);
        v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 168LL))(
                v87,
                (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v3, 4)));
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF6,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v39,
            (int)v102);
        v40 = v87;
        v41 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 120LL);
        v42 = time_point_iso8601::time_point_iso8601(Buffer);
        v43 = (_QWORD *)wil::make_bstr(v91, v42);
        v44 = v41(v40, *v43);
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF7,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v44,
            (int)v102);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v91);
        v45 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 152LL))(v87, 0xFFFFFFFFLL);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF8,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v45,
            (int)v102);
      }
      else
      {
        v88 = 0;
        v46 = v90;
        v47 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v90 + 80LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v88);
        v48 = v47(v46, 3, &v88);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE7,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v48,
            (int)v102);
        v87 = 0;
        v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
        v50 = **v88;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
        v51 = v50(v49, &GUID_5038fc98_82ff_436d_8728_a512a57c9dc1, &v87);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE9,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v51,
            (int)v102);
        v52 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 168LL))(
                v87,
                (unsigned int)_mm_cvtsi128_si32(v3));
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEA,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v52,
            (int)v102);
        v53 = v87;
        v54 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 120LL);
        v55 = time_point_iso8601::time_point_iso8601(Buffer);
        v56 = (_QWORD *)wil::make_bstr(v91, v55);
        v57 = v54(v53, *v56);
        if ( v57 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEB,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v57,
            (int)v102);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v91);
        v58 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 152LL))(v87, 0xFFFFFFFFLL);
        if ( v58 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xEC,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
            (const char *)(unsigned int)v58,
            (int)v102);
      }
    }
    else
    {
      v88 = 0;
      v70 = v90;
      v71 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v90 + 80LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v88);
      v72 = v71(v70, 1, &v88);
      if ( v72 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v72,
          (int)v102);
      v87 = 0;
      v73 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
      v74 = **v88;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
      v75 = v74(v73, &GUID_b45747e0_eba7_4276_9f29_85c5bb300006, &v87);
      if ( v75 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v75,
          (int)v102);
      v76 = v87;
      v77 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 120LL);
      v78 = time_point_iso8601::time_point_iso8601(Buffer);
      v79 = (_QWORD *)wil::make_bstr(v91, v78);
      v80 = v77(v76, *v79);
      if ( v80 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v80,
          (int)v102);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v91);
      v81 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 152LL))(v87, 0xFFFFFFFFLL);
      if ( v81 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
          (const char *)(unsigned int)v81,
          (int)v102);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
    v69 = (__int64 *)&v88;
LABEL_78:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v69);
    v95 = 0;
    v82 = v93;
    v83 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64))(*(_QWORD *)v93 + 136LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v95);
    *(_OWORD *)Buffer = 0;
    v105 = 0;
    v100 = 0;
    v101 = 0;
    *(_OWORD *)v98 = 0;
    v99 = 0;
    v84 = v83(v82, L"SmartRetryCSP", v89, 6);
    if ( v84 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
        (const char *)(unsigned int)v84,
        (int)v98);
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
      0x103u,
      "InstallServiceTaskHelpers::CreateAppInUseForceRestartTaskIfNecessary",
      -1,
      L"Successfully created SmartRetryCSP task.",
      0,
      0);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v92);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\taskhelpers.cpp",
      v85);
  }
}

```

## disassembly

```asm
0x180100808  mov     rax, rsp
0x18010080b  push    rbx
0x18010080c  push    rsi
0x18010080d  push    rdi
0x18010080e  push    r12
0x180100810  push    r14
0x180100812  push    r15
0x180100814  sub     rsp, 1A8h
0x18010081b  movaps  xmmword ptr [rax-48h], xmm6
0x18010081f  movaps  xmmword ptr [rax-58h], xmm7
0x180100823  movaps  xmmword ptr [rax-68h], xmm8
0x180100828  mov     rax, cs:__security_cookie
0x18010082f  xor     rax, rsp
0x180100832  mov     [rsp+1D8h+var_78], rax
0x18010083a  lea     rcx, [rsp+1D8h+Buffer]
0x180100842  call    ?GetForceAppRestartPolicy@@YA?AUForceAppRestartValues@@XZ; GetForceAppRestartPolicy(void)
0x180100847  movups  xmm6, xmmword ptr [rax]
0x18010084a  movups  [rsp+1D8h+var_140], xmm6
0x180100852  movups  xmm8, xmmword ptr [rax+10h]
0x180100857  movups  [rsp+1D8h+var_130], xmm8
0x180100860  mov     eax, [rax+18h]
0x180100863  xor     r12d, r12d
0x180100866  test    al, al
0x180100868  jnz     short loc_18010086F
0x18010086a  jmp     loc_18010141B
0x18010086f  call    cs:__imp__Xtime_get_ticks
0x180100875  mov     rcx, qword ptr [rsp+1D8h+var_140]
0x18010087d  cmp     rcx, rax
0x180100880  jge     short loc_1801008EC
0x180100882  movdqa  xmm0, xmm6
0x180100886  psrldq  xmm0, 8
0x18010088b  movd    esi, xmm0
0x18010088f  test    esi, esi
0x180100891  jnz     short loc_180100898
0x180100893  jmp     loc_18010141B
0x180100898  psrldq  xmm6, 0Ch
0x18010089d  movd    r15d, xmm6
0x1801008a2  test    r15b, r15b
0x1801008a5  jz      short loc_1801008FB
0x1801008a7  sub     rax, rcx
0x1801008aa  cqo
0x1801008ac  mov     r9, 861C46800h
0x1801008b6  idiv    r9
0x1801008b9  mov     r8, rax
0x1801008bc  mov     eax, 2AAAAAABh
0x1801008c1  imul    r8d
0x1801008c4  sar     edx, 2
0x1801008c7  mov     eax, edx
0x1801008c9  shr     eax, 1Fh
0x1801008cc  add     edx, eax
0x1801008ce  lea     eax, [rdx+rdx*2]
0x1801008d1  lea     eax, ds:18h[rax*8]
0x1801008d8  movsxd  rdx, eax
0x1801008db  imul    rdx, r9
0x1801008df  add     rcx, rdx
0x1801008e2  mov     qword ptr [rsp+1D8h+var_140], rcx
0x1801008ea  jmp     short loc_1801008FB
0x1801008ec  mov     r15b, byte ptr [rsp+1D8h+var_140+0Ch]
0x1801008f4  mov     esi, dword ptr [rsp+1D8h+var_140+8]
0x1801008fb  mov     [rsp+1D8h+var_160], r12
0x180100900  lea     rcx, [rsp+1D8h+var_160]
0x180100905  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18010090a  lea     rax, [rsp+1D8h+var_160]
0x18010090f  mov     [rsp+1D8h+ppv], rax; int
0x180100914  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18010091b  xor     edx, edx; pUnkOuter
0x18010091d  lea     r8d, [rdx+1]; dwClsContext
0x180100921  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180100928  call    cs:__imp_CoCreateInstance
0x18010092e  mov     rcx, [rsp+1D8h]; this
0x180100936  test    eax, eax
0x180100938  jns     short loc_18010094E
0x18010093a  mov     r9d, eax; char *
0x18010093d  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100944  mov     edx, 0ABh; void *
0x180100949  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010094e  mov     rcx, [rsp+1D8h+var_160]
0x180100953  xorps   xmm7, xmm7
0x180100956  xor     eax, eax
0x180100958  movq    xmm6, rax
0x18010095d  xorps   xmm5, xmm5
0x180100960  movq    xmm4, rax
0x180100965  xorps   xmm3, xmm3
0x180100968  movq    xmm2, rax
0x18010096d  xorps   xmm1, xmm1
0x180100970  movaps  xmmword ptr [rsp+1D8h+var_D8], xmm7
0x180100978  movsd   [rsp+1D8h+var_C8], xmm6
0x180100981  movaps  xmmword ptr [rsp+1D8h+var_118], xmm5
0x180100989  movsd   [rsp+1D8h+var_108], xmm4
0x180100992  movaps  [rsp+1D8h+var_F8], xmm3
0x18010099a  movsd   [rsp+1D8h+var_E8], xmm2
0x1801009a3  movaps  xmmword ptr [rsp+1D8h+Buffer], xmm1
0x1801009ab  mov     [rsp+1D8h+var_A8], rax
0x1801009b3  mov     rax, [rcx]
0x1801009b6  lea     rdx, [rsp+1D8h+var_D8]
0x1801009be  mov     [rsp+1D8h+ppv], rdx; int
0x1801009c3  lea     r9, [rsp+1D8h+var_118]
0x1801009cb  lea     r8, [rsp+1D8h+var_F8]
0x1801009d3  lea     rdx, [rsp+1D8h+Buffer]
0x1801009db  mov     rax, [rax+50h]
0x1801009df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801009e4  mov     rcx, [rsp+1D8h]; this
0x1801009ec  test    eax, eax
0x1801009ee  jns     short loc_180100A04
0x1801009f0  mov     r9d, eax; char *
0x1801009f3  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x1801009fa  mov     edx, 0ACh; void *
0x1801009ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100a04  mov     [rsp+1D8h+var_158], r12
0x180100a0c  mov     rdi, [rsp+1D8h+var_160]
0x180100a11  mov     rax, [rdi]
0x180100a14  mov     rbx, [rax+38h]
0x180100a18  lea     rcx, [rsp+1D8h+var_158]
0x180100a20  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100a25  lea     r8, [rsp+1D8h+var_158]
0x180100a2d  lea     rdx, aMicrosoftWindo_1; "Microsoft\\Windows\\InstallService"
0x180100a34  mov     rcx, rdi
0x180100a37  mov     rax, rbx
0x180100a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100a3f  mov     rcx, [rsp+1D8h]; this
0x180100a47  test    eax, eax
0x180100a49  jns     short loc_180100A5F
0x180100a4b  mov     r9d, eax; char *
0x180100a4e  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100a55  mov     edx, 0AEh; void *
0x180100a5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100a5f  mov     [rsp+1D8h+var_178], r12
0x180100a64  call    cs:__imp_RtlIsStateSeparationEnabled
0x180100a6a  test    al, al
0x180100a6c  jz      loc_180100B58
0x180100a72  mov     [rsp+1D8h+var_188], r12
0x180100a77  mov     rdi, [rsp+1D8h+var_158]
0x180100a7f  mov     rax, [rdi]
0x180100a82  mov     rbx, [rax+68h]
0x180100a86  lea     rcx, [rsp+1D8h+var_188]
0x180100a8b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100a90  lea     r8, [rsp+1D8h+var_188]
0x180100a95  lea     rdx, aSmartretrycsp; "SmartRetryCSP"
0x180100a9c  mov     rcx, rdi
0x180100a9f  mov     rax, rbx
0x180100aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100aa7  mov     rcx, [rsp+1D8h]; this
0x180100aaf  test    eax, eax
0x180100ab1  jns     short loc_180100AC7
0x180100ab3  mov     r9d, eax; char *
0x180100ab6  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100abd  mov     edx, 0B8h; void *
0x180100ac2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100ac7  mov     rdi, [rsp+1D8h+var_188]
0x180100acc  mov     rax, [rdi]
0x180100acf  mov     rbx, [rax+98h]
0x180100ad6  lea     rcx, [rsp+1D8h+var_178]
0x180100adb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100ae0  lea     rdx, [rsp+1D8h+var_178]
0x180100ae5  mov     rcx, rdi
0x180100ae8  mov     rax, rbx
0x180100aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100af0  mov     rcx, [rsp+1D8h]; this
0x180100af8  test    eax, eax
0x180100afa  jns     short loc_180100B10
0x180100afc  mov     r9d, eax; char *
0x180100aff  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100b06  mov     edx, 0B9h; void *
0x180100b0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100b10  mov     rcx, [rsp+1D8h+var_188]
0x180100b15  mov     rax, [rcx]
0x180100b18  or      r14d, 0FFFFFFFFh
0x180100b1c  mov     edx, r14d
0x180100b1f  mov     rax, [rax+58h]
0x180100b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100b28  mov     rcx, [rsp+1D8h]; this
0x180100b30  test    eax, eax
0x180100b32  jns     short loc_180100B49
0x180100b34  mov     r9d, eax; char *
0x180100b37  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100b3e  mov     edx, 0BAh; void *
0x180100b43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100b49  lea     rcx, [rsp+1D8h+var_188]
0x180100b4e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100b53  jmp     loc_180100BDF
0x180100b58  mov     rdi, [rsp+1D8h+var_160]
0x180100b5d  mov     rax, [rdi]
0x180100b60  mov     rbx, [rax+48h]
0x180100b64  lea     rcx, [rsp+1D8h+var_178]
0x180100b69  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100b6e  lea     r8, [rsp+1D8h+var_178]
0x180100b73  xor     edx, edx
0x180100b75  mov     rcx, rdi
0x180100b78  mov     rax, rbx
0x180100b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100b80  mov     rcx, [rsp+1D8h]; this
0x180100b88  test    eax, eax
0x180100b8a  jns     short loc_180100BA0
0x180100b8c  mov     r9d, eax; char *
0x180100b8f  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100b96  mov     edx, 0BEh; void *
0x180100b9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100ba0  mov     rcx, [rsp+1D8h+var_178]
0x180100ba5  mov     rax, [rcx]
0x180100ba8  lea     rdx, aTaskXmlnsHttpS; "\n<Task xmlns=\"http://schemas.microsof"...
0x180100baf  mov     rax, [rax+0A0h]
0x180100bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100bbb  mov     rcx, [rsp+1D8h]; this
0x180100bc3  test    eax, eax
0x180100bc5  jns     short loc_180100BDB
0x180100bc7  mov     r9d, eax; char *
0x180100bca  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100bd1  mov     edx, 0BFh; void *
0x180100bd6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100bdb  or      r14d, 0FFFFFFFFh
0x180100bdf  mov     [rsp+1D8h+var_150], r12
0x180100be7  mov     rdi, [rsp+1D8h+var_178]
0x180100bec  mov     rax, [rdi]
0x180100bef  mov     rbx, [rax+58h]
0x180100bf3  lea     rcx, [rsp+1D8h+var_150]
0x180100bfb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100c00  lea     rdx, [rsp+1D8h+var_150]
0x180100c08  mov     rcx, rdi
0x180100c0b  mov     rax, rbx
0x180100c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100c13  mov     rcx, [rsp+1D8h]; this
0x180100c1b  test    eax, eax
0x180100c1d  jns     short loc_180100C33
0x180100c1f  mov     r9d, eax; char *
0x180100c22  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100c29  mov     edx, 0C4h; void *
0x180100c2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100c33  test    r15b, r15b
0x180100c36  jz      short loc_180100C3E
0x180100c38  movzx   edx, r14w
0x180100c3c  jmp     short loc_180100C41
0x180100c3e  mov     edx, r12d
0x180100c41  mov     rcx, [rsp+1D8h+var_150]
0x180100c49  mov     rax, [rcx]
0x180100c4c  mov     rax, [rax+0B0h]
0x180100c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100c58  mov     rcx, [rsp+1D8h]; this
0x180100c60  test    eax, eax
0x180100c62  jns     short loc_180100C78
0x180100c64  mov     r9d, eax; char *
0x180100c67  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100c6e  mov     edx, 0C6h; void *
0x180100c73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100c78  mov     [rsp+1D8h+var_170], r12
0x180100c7d  mov     rdi, [rsp+1D8h+var_178]
0x180100c82  mov     rax, [rdi]
0x180100c85  mov     rbx, [rax+48h]
0x180100c89  lea     rcx, [rsp+1D8h+var_170]
0x180100c8e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100c93  lea     rdx, [rsp+1D8h+var_170]
0x180100c98  mov     rcx, rdi
0x180100c9b  mov     rax, rbx
0x180100c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100ca3  mov     rcx, [rsp+1D8h]; this
0x180100cab  test    eax, eax
0x180100cad  jns     short loc_180100CC3
0x180100caf  mov     r9d, eax; char *
0x180100cb2  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100cb9  mov     edx, 0CAh; void *
0x180100cbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100cc3  test    esi, esi
0x180100cc5  jz      loc_180101156
0x180100ccb  sub     esi, 1
0x180100cce  jz      loc_18010101D
0x180100cd4  sub     esi, 1
0x180100cd7  jz      loc_180100E92
0x180100cdd  cmp     esi, 1
0x180100ce0  jz      short loc_180100D01
0x180100ce2  mov     rcx, [rsp+1D8h]; this
0x180100cea  mov     r9d, 8007000Dh; char *
0x180100cf0  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100cf7  mov     edx, 0FDh; void *
0x180100cfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100d01  mov     [rsp+1D8h+var_180], r12
0x180100d06  mov     rdi, [rsp+1D8h+var_170]
0x180100d0b  mov     rax, [rdi]
0x180100d0e  mov     rbx, [rax+50h]
0x180100d12  lea     rcx, [rsp+1D8h+var_180]
0x180100d17  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100d1c  lea     r8, [rsp+1D8h+var_180]
0x180100d21  mov     edx, 4
0x180100d26  mov     rcx, rdi
0x180100d29  mov     rax, rbx
0x180100d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100d31  mov     rcx, [rsp+1D8h]; this
0x180100d39  test    eax, eax
0x180100d3b  jns     short loc_180100D51
0x180100d3d  mov     r9d, eax; char *
0x180100d40  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180100d47  mov     edx, 0F3h; void *
0x180100d4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100d51  mov     [rsp+1D8h+var_188], r12
0x180100d56  mov     rbx, [rsp+1D8h+var_180]
0x180100d5b  mov     rax, [rbx]
0x180100d5e  mov     rdi, [rax]
0x180100d61  lea     rcx, [rsp+1D8h+var_188]
0x180100d66  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180100d6b  lea     r8, [rsp+1D8h+var_188]
0x180100d70  lea     rdx, _GUID_97c45ef1_6b02_4a1a_9c0e_1ebfba1500ac
0x180100d77  mov     rcx, rbx
  ... truncated ...
```
