# _lambda_6e2f007c37fc2c249cdaece063b7a5d6_::operator()

- ea: `0x180037254`
- end: `0x180037bb1`
- name: `_lambda_6e2f007c37fc2c249cdaece063b7a5d6_::operator()`
- size: `2397`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800406e0`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18001094c`
- `0x180037254`
- `0x18003aea0`
- `0x18003eca8`
- `0x180041ad4`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18003767a`
- `SHCORE!IUnknown_QueryService` at `0x18003767a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800372b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800372b8`

## string_xrefs

- `0x1800374c5`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003755b`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800377c8`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037881`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037933`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037abd`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037ad2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037ae7`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037afb`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b10`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b25`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b3a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b4e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b62`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b76`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b8a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037b9e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall lambda_6e2f007c37fc2c249cdaece063b7a5d6_::operator()(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, __int64 *, GUID *, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  RetailDemoUserAgent *v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  struct IApplicationView *v19; // rdi
  int (__fastcall *v20)(struct IApplicationView *, GUID *, __int64 *); // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  RetailDemoUserAgent *v24; // rcx
  __int64 v25; // r8
  LPVOID v26; // rdi
  int (__fastcall *v27)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  int v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  struct IApplicationView *v58; // rdi
  int (__fastcall *v59)(struct IApplicationView *, GUID *, __int64 *); // rbx
  __int64 v60; // rdi
  void (__fastcall *v61)(__int64, HWND *); // rbx
  HWND v62; // rdi
  __int64 (__fastcall *v63)(HWND, IUnknown **); // rbx
  __int64 v64; // rdx
  __int64 v65; // r8
  int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  HRESULT v69; // eax
  int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r8
  int v73; // eax
  LPVOID v74; // rdi
  int (__fastcall *v75)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  __int64 v76; // rdx
  __int64 v77; // r8
  HWND v78; // rdi
  __int64 (__fastcall *v79)(HWND, __int64, GUID *, __int64 *); // rbx
  int v80; // eax
  unsigned int v81; // ebx
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 v100; // rdx
  __int64 v101; // r8
  int v102; // eax
  __int64 v103; // rcx
  unsigned int v104; // ebx
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // rdx
  __int64 v108; // r8
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // rdx
  __int64 v112; // r8
  __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // rdx
  __int64 v116; // r8
  __int64 v117; // rdx
  __int64 v118; // r8
  __int64 v119; // rdx
  __int64 v120; // r8
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // rdx
  __int64 v124; // r8
  int v125; // eax
  __int64 v126; // rdx
  __int64 v127; // r8
  unsigned int v128; // ebx
  __int64 v129; // rdx
  __int64 v130; // r8
  __int64 v131; // rdx
  __int64 v132; // r8
  __int64 v133; // rdx
  __int64 v134; // r8
  __int64 v135; // rdx
  __int64 v136; // r8
  __int64 v137; // rdx
  __int64 v138; // r8
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // rdx
  __int64 v142; // r8
  __int64 v143; // rdx
  __int64 v144; // r8
  __int64 v145; // rdx
  __int64 v146; // r8
  __int64 v147; // rdx
  __int64 v148; // r8
  int v149; // eax
  int v150; // eax
  __int64 v151; // rdx
  __int64 v152; // r8
  __int64 v153; // rdx
  __int64 v154; // r8
  __int64 v155; // rdx
  __int64 v156; // r8
  __int64 v157; // rdx
  __int64 v158; // r8
  __int64 v159; // rdx
  __int64 v160; // r8
  __int64 v161; // rdx
  __int64 v162; // r8
  int ppv; // [rsp+20h] [rbp-B8h]
  int ppva; // [rsp+20h] [rbp-B8h]
  LPVOID v165; // [rsp+30h] [rbp-A8h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-A0h] BYREF
  struct IApplicationView *v167; // [rsp+40h] [rbp-98h] BYREF
  __int64 v168; // [rsp+48h] [rbp-90h] BYREF
  __int64 v169; // [rsp+50h] [rbp-88h] BYREF
  __int64 v170; // [rsp+58h] [rbp-80h] BYREF
  __int64 v171; // [rsp+60h] [rbp-78h] BYREF
  __int64 v172; // [rsp+68h] [rbp-70h] BYREF
  IUnknown *punk; // [rsp+70h] [rbp-68h] BYREF
  __int64 v174; // [rsp+78h] [rbp-60h] BYREF
  int v175[4]; // [rsp+80h] [rbp-58h] BYREF
  __int128 v176; // [rsp+90h] [rbp-48h]
  __int128 v177; // [rsp+A0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v179; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v180; // [rsp+F0h] [rbp+18h] BYREF
  HWND v181; // [rsp+F8h] [rbp+20h] BYREF

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8));
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v165 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v3, v4);
  v5 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v165);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  v170 = 0;
  v8 = v165;
  v9 = *(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, __int64 *))(*(_QWORD *)v165 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v6, v7);
  v10 = v9(v8, qword_18005DED8, &GUID_53b23e1b_25e2_4886_9fb6_744b8f15571c, &v170);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x295,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v10,
      ppva);
  *(_OWORD *)v175 = 0;
  v176 = 0;
  v177 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v170 + 24LL))(
          v170,
          *(_QWORD *)(a1 + 16),
          *(_QWORD *)(a1 + 24),
          *(_QWORD *)(a1 + 16));
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v11,
      (int)v175);
  v167 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v12, v13);
  v15 = RetailDemoUserAgent::WaitOnViewForAumid(v14, *(const unsigned __int16 **)(a1 + 16), &v167);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v15,
      (int)v175);
  v169 = 0;
  v168 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8));
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v16,
      (int)v175);
  v19 = v167;
  v20 = **(int (__fastcall ***)(struct IApplicationView *, GUID *, __int64 *))v167;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v17, v18);
  if ( v20(v19, &GUID_f3527610_c76d_4316_ac8e_28651acf3df3, &v169) < 0 )
  {
    v58 = v167;
    v59 = **(int (__fastcall ***)(struct IApplicationView *, GUID *, __int64 *))v167;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v21, v22);
    if ( v59(v58, &GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b, &v168) >= 0 )
    {
      v181 = 0;
      v60 = v168;
      v61 = *(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v168 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v181, v23, v25);
      v61(v60, &v181);
      ppvOut = 0;
      punk = 0;
      v62 = v181;
      v63 = *(__int64 (__fastcall **)(HWND, IUnknown **))(*(_QWORD *)v181 + 232LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v64, v65);
      v66 = v63(v62, &punk);
      if ( v66 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2CD,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v66,
          (int)v175);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v67, v68);
      v69 = IUnknown_QueryService(
              punk,
              (const GUID *const)&SID_FullScreenManager,
              &GUID_f0093591_bfa3_471f_b9f0_f17f8a979c6d,
              &ppvOut);
      if ( v69 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2CE,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v69,
          (int)v175);
      v179 = 0;
      v70 = (*(__int64 (__fastcall **)(void *, HWND, int *))(*(_QWORD *)ppvOut + 64LL))(ppvOut, v181, &v179);
      if ( v70 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D1,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v70,
          (int)v175);
      if ( *(_QWORD *)(a1 + 40) )
      {
        if ( v179 )
        {
          v73 = (*(__int64 (__fastcall **)(void *, HWND, _QWORD))(*(_QWORD *)ppvOut + 56LL))(ppvOut, v181, 0);
          if ( v73 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2D9,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)(unsigned int)v73,
              (int)v175);
        }
        v172 = 0;
        LODWORD(v180) = 0;
        v74 = v165;
        v75 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v165 + 24LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v172, v71, v72);
        if ( v75(v74, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &v172) < 0
          || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v172 + 24LL))(v172, &v180) < 0
          || (_DWORD)v180 != 1 )
        {
          v171 = 0;
          v78 = v181;
          v79 = *(__int64 (__fastcall **)(HWND, __int64, GUID *, __int64 *))(*(_QWORD *)v181 + 24LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v171, v76, v77);
          v80 = v79(v78, 5, &GUID_c6636ec2_eba1_4e6d_a995_8fa14b8b2891, &v171);
          v81 = v80;
          if ( v80 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E4,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)(unsigned int)v80,
              (int)v175);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v171, v82, v83);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v172, v84, v85);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v86, v87);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v88, v89);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v181, v90, v91);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v92, v93);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v94, v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v96, v97);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v98, v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v100, v101);
            return v81;
          }
          v174 = 0;
          v102 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v171 + 32LL))(v171, &v174);
          v104 = v102;
          if ( v102 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E7,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)(unsigned int)v102,
              (int)v175);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v171, v105, v106);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v172, v107, v108);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v109, v110);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v111, v112);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v181, v113, v114);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v115, v116);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v117, v118);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v119, v120);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v121, v122);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v123, v124);
            return v104;
          }
          v125 = RetailDemoUserAgent::MoveApplication(v103, &v174, *(_QWORD *)(a1 + 40), 1);
          v128 = v125;
          if ( v125 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E8,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)(unsigned int)v125,
              (int)v175);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v171, v129, v130);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v172, v131, v132);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v133, v134);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v135, v136);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v181, v137, v138);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v139, v140);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v141, v142);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v143, v144);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v145, v146);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v147, v148);
            return v128;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v171, v126, v127);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v172, v76, v77);
      }
      if ( *(_BYTE *)(a1 + 32) )
      {
        v149 = (*(__int64 (__fastcall **)(void *, HWND, int *))(*(_QWORD *)ppvOut + 64LL))(ppvOut, v181, &v179);
        if ( v149 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2EE,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
            (const char *)(unsigned int)v149,
            (int)v175);
        if ( !v179 )
        {
          v150 = (*(__int64 (__fastcall **)(void *, HWND, __int64))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v181, 2);
          if ( v150 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2F1,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)(unsigned int)v150,
              (int)v175);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v71, v72);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v151, v152);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v181, v153, v154);
    }
  }
  else
  {
    v181 = 0;
    (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v169 + 24LL))(v169, &v181);
    if ( *(_QWORD *)(a1 + 40) )
    {
      v180 = 0;
      v179 = 0;
      v26 = v165;
      v27 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v165 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v180, v23, v25);
      if ( v27(v26, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &v180) < 0
        || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v180 + 24LL))(v180, &v179) < 0
        || v179 != 1 )
      {
        v31 = RetailDemoUserAgent::MoveApplication(v28, &v181, *(_QWORD *)(a1 + 40), 1);
        v32 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B8,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
            (const char *)(unsigned int)v31,
            (int)v175);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v180, v33, v34);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v35, v36);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v37, v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v39, v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v41, v42);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v43, v44);
          return v32;
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v180, v29, v30);
    }
    if ( *(_BYTE *)(a1 + 32) )
    {
      v46 = RetailDemoUserAgent::EnterFullscreenForHwnd(v24, &v181);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BD,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v46,
          (int)v175);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v48, v49);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v50, v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v52, v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v54, v55);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v56, v57);
        return v47;
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168, v23, v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169, v155, v156);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v167, v157, v158);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170, v159, v160);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v165, v161, v162);
  return **(unsigned int **)(a1 + 48);
}

```

## disassembly

```asm
0x180037254  mov     [rsp+arg_0], rcx
0x180037259  push    rbx
0x18003725a  push    rsi
0x18003725b  push    rdi
0x18003725c  push    r14
0x18003725e  sub     rsp, 0B8h
0x180037265  mov     rsi, rcx
0x180037268  mov     rcx, [rcx+8]
0x18003726c  mov     rax, [rcx]
0x18003726f  mov     rax, [rax+18h]
0x180037273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037278  mov     rcx, [rsp+0D8h]; this
0x180037280  xor     r14d, r14d
0x180037283  test    eax, eax
0x180037285  js      loc_180037ABA
0x18003728b  mov     [rsp+0D8h+var_A8], r14
0x180037290  lea     rcx, [rsp+0D8h+var_A8]
0x180037295  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003729a  lea     rax, [rsp+0D8h+var_A8]
0x18003729f  mov     qword ptr [rsp+0D8h+ppv], rax; int
0x1800372a4  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x1800372ab  xor     edx, edx; pUnkOuter
0x1800372ad  lea     r8d, [rdx+4]; dwClsContext
0x1800372b1  lea     rcx, CLSID_ImmersiveShell; rclsid
0x1800372b8  call    cs:__imp_CoCreateInstance
0x1800372be  mov     rcx, [rsp+0D8h]; this
0x1800372c6  test    eax, eax
0x1800372c8  js      loc_180037ACF
0x1800372ce  mov     [rsp+0D8h+var_80], r14
0x1800372d3  mov     rdi, [rsp+0D8h+var_A8]
0x1800372d8  mov     rax, [rdi]
0x1800372db  mov     rbx, [rax+18h]
0x1800372df  lea     rcx, [rsp+0D8h+var_80]
0x1800372e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800372e9  lea     r9, [rsp+0D8h+var_80]
0x1800372ee  lea     r8, _GUID_53b23e1b_25e2_4886_9fb6_744b8f15571c
0x1800372f5  lea     rdx, qword_18005DED8
0x1800372fc  mov     rcx, rdi
0x1800372ff  mov     rax, rbx
0x180037302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037307  mov     rcx, [rsp+0D8h]; this
0x18003730f  test    eax, eax
0x180037311  js      loc_180037AE4
0x180037317  xorps   xmm0, xmm0
0x18003731a  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x180037322  movups  [rsp+0D8h+var_48], xmm0
0x18003732a  movups  [rsp+0D8h+var_38], xmm0
0x180037332  mov     rcx, [rsp+0D8h+var_80]
0x180037337  mov     rdx, [rsi+10h]
0x18003733b  mov     rax, [rcx]
0x18003733e  lea     r8, [rsp+0D8h+var_58]
0x180037346  mov     qword ptr [rsp+0D8h+ppv], r8; int
0x18003734b  mov     r9, rdx
0x18003734e  mov     r8, [rsi+18h]
0x180037352  mov     rax, [rax+18h]
0x180037356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003735b  mov     rcx, [rsp+0D8h]; this
0x180037363  test    eax, eax
0x180037365  js      loc_180037AF8
0x18003736b  mov     [rsp+0D8h+var_98], r14
0x180037370  lea     rcx, [rsp+0D8h+var_98]
0x180037375  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003737a  lea     r8, [rsp+0D8h+var_98]; struct IApplicationView **
0x18003737f  mov     rdx, [rsi+10h]; unsigned __int16 *
0x180037383  call    ?WaitOnViewForAumid@RetailDemoUserAgent@@AEAAJPEBGPEAPEAUIApplicationView@@@Z; RetailDemoUserAgent::WaitOnViewForAumid(ushort const *,IApplicationView * *)
0x180037388  mov     rcx, [rsp+0D8h]; this
0x180037390  test    eax, eax
0x180037392  js      loc_180037B0D
0x180037398  mov     [rsp+0D8h+var_88], r14
0x18003739d  mov     [rsp+0D8h+var_90], r14
0x1800373a2  mov     rcx, [rsi+8]
0x1800373a6  mov     rax, [rcx]
0x1800373a9  mov     rax, [rax+18h]
0x1800373ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373b2  mov     rcx, [rsp+0D8h]; this
0x1800373ba  test    eax, eax
0x1800373bc  js      loc_180037B22
0x1800373c2  mov     rdi, [rsp+0D8h+var_98]
0x1800373c7  mov     rax, [rdi]
0x1800373ca  mov     rbx, [rax]
0x1800373cd  lea     rcx, [rsp+0D8h+var_88]
0x1800373d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800373d7  lea     r8, [rsp+0D8h+var_88]
0x1800373dc  lea     rdx, _GUID_f3527610_c76d_4316_ac8e_28651acf3df3
0x1800373e3  mov     rcx, rdi
0x1800373e6  mov     rax, rbx
0x1800373e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373ee  test    eax, eax
0x1800373f0  js      loc_1800375AA
0x1800373f6  mov     [rsp+0D8h+arg_18], r14
0x1800373fe  mov     rcx, [rsp+0D8h+var_88]
0x180037403  mov     rax, [rcx]
0x180037406  lea     rdx, [rsp+0D8h+arg_18]
0x18003740e  mov     rax, [rax+18h]
0x180037412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037417  cmp     [rsi+28h], r14
0x18003741b  jz      loc_18003752F
0x180037421  mov     [rsp+0D8h+arg_10], r14
0x180037429  mov     [rsp+0D8h+arg_8], r14d
0x180037431  mov     rdi, [rsp+0D8h+var_A8]
0x180037436  mov     rax, [rdi]
0x180037439  mov     rbx, [rax+18h]
0x18003743d  lea     rcx, [rsp+0D8h+arg_10]
0x180037445  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003744a  lea     r9, [rsp+0D8h+arg_10]
0x180037452  lea     r8, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x180037459  lea     rdx, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x180037460  mov     rcx, rdi
0x180037463  mov     rax, rbx
0x180037466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003746b  test    eax, eax
0x18003746d  js      short loc_18003749D
0x18003746f  mov     rcx, [rsp+0D8h+arg_10]
0x180037477  mov     rax, [rcx]
0x18003747a  lea     rdx, [rsp+0D8h+arg_8]
0x180037482  mov     rax, [rax+18h]
0x180037486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003748b  test    eax, eax
0x18003748d  js      short loc_18003749D
0x18003748f  cmp     [rsp+0D8h+arg_8], 1
0x180037497  jz      loc_180037522
0x18003749d  mov     r9d, 1
0x1800374a3  mov     r8, [rsi+28h]
0x1800374a7  lea     rdx, [rsp+0D8h+arg_18]
0x1800374af  call    ?MoveApplication@RetailDemoUserAgent@@AEAAJAEAPEAUHWND__@@PEAUtagRECT@@W4LaunchOptionsUA@@@Z; RetailDemoUserAgent::MoveApplication(HWND__ * &,tagRECT *,LaunchOptionsUA)
0x1800374b4  mov     ebx, eax
0x1800374b6  test    eax, eax
0x1800374b8  jns     short loc_180037522
0x1800374ba  mov     rcx, [rsp+0D8h]; this
0x1800374c2  mov     r9d, eax; char *
0x1800374c5  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800374cc  mov     edx, 2B8h; void *
0x1800374d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800374d6  nop
0x1800374d7  lea     rcx, [rsp+0D8h+arg_10]
0x1800374df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800374e4  nop
0x1800374e5  lea     rcx, [rsp+0D8h+var_90]
0x1800374ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800374ef  nop
0x1800374f0  lea     rcx, [rsp+0D8h+var_88]
0x1800374f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800374fa  nop
0x1800374fb  lea     rcx, [rsp+0D8h+var_98]
0x180037500  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037505  nop
0x180037506  lea     rcx, [rsp+0D8h+var_80]
0x18003750b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037510  nop
0x180037511  lea     rcx, [rsp+0D8h+var_A8]
0x180037516  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003751b  mov     eax, ebx
0x18003751d  jmp     loc_180037AAD
0x180037522  lea     rcx, [rsp+0D8h+arg_10]
0x18003752a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003752f  cmp     [rsi+20h], r14b
0x180037533  jz      loc_180037A66
0x180037539  lea     rdx, [rsp+0D8h+arg_18]; HWND *
0x180037541  call    ?EnterFullscreenForHwnd@RetailDemoUserAgent@@AEAAJAEAPEAUHWND__@@@Z; RetailDemoUserAgent::EnterFullscreenForHwnd(HWND__ * &)
0x180037546  mov     ebx, eax
0x180037548  test    eax, eax
0x18003754a  jns     loc_180037A66
0x180037550  mov     rcx, [rsp+0D8h]; this
0x180037558  mov     r9d, eax; char *
0x18003755b  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037562  mov     edx, 2BDh; void *
0x180037567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003756c  nop
0x18003756d  lea     rcx, [rsp+0D8h+var_90]
0x180037572  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037577  nop
0x180037578  lea     rcx, [rsp+0D8h+var_88]
0x18003757d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037582  nop
0x180037583  lea     rcx, [rsp+0D8h+var_98]
0x180037588  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003758d  nop
0x18003758e  lea     rcx, [rsp+0D8h+var_80]
0x180037593  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037598  nop
0x180037599  lea     rcx, [rsp+0D8h+var_A8]
0x18003759e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800375a3  mov     eax, ebx
0x1800375a5  jmp     loc_180037AAD
0x1800375aa  mov     rdi, [rsp+0D8h+var_98]
0x1800375af  mov     rax, [rdi]
0x1800375b2  mov     rbx, [rax]
0x1800375b5  lea     rcx, [rsp+0D8h+var_90]
0x1800375ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800375bf  lea     r8, [rsp+0D8h+var_90]
0x1800375c4  lea     rdx, _GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b
0x1800375cb  mov     rcx, rdi
0x1800375ce  mov     rax, rbx
0x1800375d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375d6  test    eax, eax
0x1800375d8  js      loc_180037A66
0x1800375de  mov     [rsp+0D8h+arg_18], r14
0x1800375e6  mov     rdi, [rsp+0D8h+var_90]
0x1800375eb  mov     rax, [rdi]
0x1800375ee  mov     rbx, [rax+18h]
0x1800375f2  lea     rcx, [rsp+0D8h+arg_18]
0x1800375fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800375ff  lea     rdx, [rsp+0D8h+arg_18]
0x180037607  mov     rcx, rdi
0x18003760a  mov     rax, rbx
0x18003760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037612  mov     [rsp+0D8h+ppvOut], r14
0x180037617  mov     [rsp+0D8h+punk], r14
0x18003761c  mov     rdi, [rsp+0D8h+arg_18]
0x180037624  mov     rax, [rdi]
0x180037627  mov     rbx, [rax+0E8h]
0x18003762e  lea     rcx, [rsp+0D8h+punk]
0x180037633  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037638  lea     rdx, [rsp+0D8h+punk]
0x18003763d  mov     rcx, rdi
0x180037640  mov     rax, rbx
0x180037643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037648  mov     rcx, [rsp+0D8h]; this
0x180037650  test    eax, eax
0x180037652  js      loc_180037B37
0x180037658  lea     rcx, [rsp+0D8h+ppvOut]
0x18003765d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037662  lea     r9, [rsp+0D8h+ppvOut]; ppvOut
0x180037667  lea     r8, _GUID_f0093591_bfa3_471f_b9f0_f17f8a979c6d; riid
0x18003766e  lea     rdx, SID_FullScreenManager; guidService
0x180037675  mov     rcx, [rsp+0D8h+punk]; punk
0x18003767a  call    cs:__imp_IUnknown_QueryService
0x180037680  mov     rcx, [rsp+0D8h]; this
0x180037688  test    eax, eax
0x18003768a  js      loc_180037B4B
0x180037690  mov     [rsp+0D8h+arg_8], r14d
0x180037698  mov     rcx, [rsp+0D8h+ppvOut]
0x18003769d  mov     rax, [rcx]
0x1800376a0  lea     r8, [rsp+0D8h+arg_8]
0x1800376a8  mov     rdx, [rsp+0D8h+arg_18]
0x1800376b0  mov     rax, [rax+40h]
0x1800376b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376b9  mov     rcx, [rsp+0D8h]; this
0x1800376c1  test    eax, eax
0x1800376c3  js      loc_180037B5F
0x1800376c9  cmp     [rsi+28h], r14
0x1800376cd  jz      loc_1800379D1
0x1800376d3  cmp     [rsp+0D8h+arg_8], r14d
0x1800376db  jz      short loc_180037709
0x1800376dd  mov     rcx, [rsp+0D8h+ppvOut]
0x1800376e2  mov     rax, [rcx]
0x1800376e5  xor     r8d, r8d
0x1800376e8  mov     rdx, [rsp+0D8h+arg_18]
0x1800376f0  mov     rax, [rax+38h]
0x1800376f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376f9  mov     rcx, [rsp+0D8h]; this
0x180037701  test    eax, eax
0x180037703  js      loc_180037B73
0x180037709  mov     [rsp+0D8h+var_70], r14
0x18003770e  mov     dword ptr [rsp+0D8h+arg_10], r14d
0x180037716  mov     rdi, [rsp+0D8h+var_A8]
0x18003771b  mov     rax, [rdi]
0x18003771e  mov     rbx, [rax+18h]
0x180037722  lea     rcx, [rsp+0D8h+var_70]
0x180037727  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003772c  lea     r9, [rsp+0D8h+var_70]
0x180037731  lea     r8, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x180037738  lea     rdx, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x18003773f  mov     rcx, rdi
0x180037742  mov     rax, rbx
0x180037745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003774a  test    eax, eax
0x18003774c  js      short loc_180037779
0x18003774e  mov     rcx, [rsp+0D8h+var_70]
0x180037753  mov     rax, [rcx]
0x180037756  lea     rdx, [rsp+0D8h+arg_10]
0x18003775e  mov     rax, [rax+18h]
0x180037762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037767  test    eax, eax
0x180037769  js      short loc_180037779
0x18003776b  cmp     dword ptr [rsp+0D8h+arg_10], 1
0x180037773  jz      loc_1800379C7
0x180037779  mov     [rsp+0D8h+var_78], r14
0x18003777e  mov     rdi, [rsp+0D8h+arg_18]
0x180037786  mov     rax, [rdi]
0x180037789  mov     rbx, [rax+18h]
0x18003778d  lea     rcx, [rsp+0D8h+var_78]
0x180037792  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037797  lea     r9, [rsp+0D8h+var_78]
0x18003779c  lea     r8, _GUID_c6636ec2_eba1_4e6d_a995_8fa14b8b2891
0x1800377a3  mov     edx, 5
0x1800377a8  mov     rcx, rdi
0x1800377ab  mov     rax, rbx
0x1800377ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377b3  mov     ebx, eax
0x1800377b5  test    eax, eax
0x1800377b7  jns     loc_180037851
0x1800377bd  mov     rcx, [rsp+0D8h]; this
0x1800377c5  mov     r9d, eax; char *
0x1800377c8  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800377cf  mov     edx, 2E4h; void *
0x1800377d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800377d9  nop
0x1800377da  lea     rcx, [rsp+0D8h+var_78]
0x1800377df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
