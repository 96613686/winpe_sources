# ConvertDeploymentOptionsToAddPackageOptions

- ea: `0x18001e7e4`
- end: `0x18001f5fc`
- name: `ConvertDeploymentOptionsToAddPackageOptions`
- size: `3608`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001ffb0`

## callees

- `0x18000cfe8`
- `0x18001e7e4`
- `0x180022ca8`
- `0x18002752c`
- `0x18006a010`

## string_xrefs

- `0x18001e830`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001e98d`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001e9e6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ea4c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001eaa2`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001eafb`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001eb55`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ebaa`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ec37`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ece3`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ed87`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001eeb4`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ef56`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001eff6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f096`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f15c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f21a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f3d5`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f48f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f549`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall ConvertDeploymentOptionsToAddPackageOptions(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        __int64 a5)
{
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // esi
  __int64 v13; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // edi
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  _QWORD *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // eax
  _QWORD *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // eax
  _QWORD *v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  int v56; // eax
  __int64 v57; // rax
  __int64 v58; // rdx
  int v59; // eax
  int v60; // eax
  __int64 v61; // rcx
  int v62; // eax
  unsigned int v63; // ebx
  _QWORD *v64; // rcx
  _QWORD *v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  _QWORD *v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  _QWORD *v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  _QWORD *v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  int v84; // eax
  _QWORD *v85; // rcx
  _QWORD *v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  int v90; // eax
  _QWORD *v91; // rcx
  _QWORD *v92; // rcx
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  int v96; // eax
  __int64 v97; // rax
  __int64 v98; // rdx
  int v99; // eax
  int v100; // eax
  __int64 v101; // rcx
  _QWORD *v102; // rcx
  _QWORD *v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  _QWORD *v108; // rcx
  _QWORD *v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int64 v112; // rcx
  __int64 v113; // rcx
  _QWORD *v114; // rcx
  _QWORD *v115; // rcx
  __int64 v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // rcx
  __int64 v119; // rcx
  _QWORD *v120; // rcx
  _QWORD *v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  __int64 v124; // rcx
  __int64 v125; // [rsp+20h] [rbp-38h] BYREF
  __int64 v126; // [rsp+28h] [rbp-30h] BYREF
  _QWORD *v127; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v128; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v129[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  char v131; // [rsp+B0h] [rbp+58h] BYREF

  v9 = a5;
  v10 = a3 >> 1;
  LOBYTE(v10) = (a3 & 2) != 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 136LL))(a5, v10);
  if ( v12 < 0 )
  {
    v13 = 1626;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v12,
      v125);
    return (unsigned int)v12;
  }
  LOBYTE(v11) = a3 & 1;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 152LL))(v9, v11);
  if ( v12 < 0 )
  {
    v13 = 1627;
    goto LABEL_3;
  }
  v15 = a3 >> 6;
  LOBYTE(v15) = (a3 & 0x40) != 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 168LL))(v9, v15);
  if ( v12 < 0 )
  {
    v13 = 1628;
    goto LABEL_3;
  }
  v16 = a3 >> 18;
  LOBYTE(v16) = (a3 & 0x40000) != 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 184LL))(v9, v16);
  if ( v12 < 0 )
  {
    v13 = 1629;
    goto LABEL_3;
  }
  v17 = a3 >> 5;
  LOBYTE(v17) = (a3 & 0x20) != 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 200LL))(v9, v17);
  if ( v12 < 0 )
  {
    v13 = 1630;
    goto LABEL_3;
  }
  v18 = a3 >> 8;
  LOBYTE(v18) = BYTE1(a3) & 1;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 216LL))(v9, v18);
  if ( v12 < 0 )
  {
    v13 = 1631;
    goto LABEL_3;
  }
  v19 = a3 >> 21;
  LOBYTE(v19) = (a3 & 0x200000) != 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 232LL))(v9, v19);
  if ( v12 < 0 )
  {
    v13 = 1632;
    goto LABEL_3;
  }
  LOBYTE(v20) = a4;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 280LL))(v9, v20);
  if ( v12 < 0 )
  {
    v13 = 1633;
    goto LABEL_3;
  }
  a5 = 0;
  v21 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
          v9,
          &GUID_4236972c_2b83_4776_9aa3_565e11029a41,
          &a5);
  v12 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x665,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v21,
      v125);
    v22 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return (unsigned int)v12;
  }
  v23 = a3 >> 4;
  LOBYTE(v23) = (a3 & 0x10) != 0;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 88LL))(a5, v23);
  v12 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x666,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v24,
      v125);
    v25 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return (unsigned int)v12;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SignatureValidationBypass>::GetImpl'::`2'::impl) )
  {
    v26 = a3 >> 15;
    LOBYTE(v26) = (a3 & 0x8000) != 0;
    v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 104LL))(a5, v26);
    v12 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66E,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v27,
        v125);
      v28 = a5;
      if ( a5 )
      {
        a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      return (unsigned int)v12;
    }
  }
  v29 = (*(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)a5 + 120LL))(a5, (a3 & 0x2000000) != 0);
  v12 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x671,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v29,
      v125);
    v30 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return (unsigned int)v12;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)a5 + 136LL))(a5, (a3 & 0x4000000) != 0);
  v12 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x672,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v31,
      v125);
    v33 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return (unsigned int)v12;
  }
  LOBYTE(v32) = (a3 & 0x8000000) != 0;
  v34 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 152LL))(a5, v32);
  v35 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x673,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v34,
      v125);
    v36 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return v35;
  }
  v125 = 0;
  v131 = 0;
  v126 = 0;
  v37 = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>::Make(&v126);
  v35 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67A,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v37,
      v125);
    v38 = v126;
    if ( v126 )
    {
      v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v35;
  }
  v127 = 0;
  v41 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v9 + 48LL))(v9, &v127);
  v35 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67D,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v41,
      v125);
    v42 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
    }
    v43 = v126;
    if ( v126 )
    {
      v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    return v35;
  }
  if ( a1 )
  {
    v46 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 48LL))(a1, &v125);
    v35 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x680,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v46,
        v125);
      v47 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
      }
      v48 = v126;
      if ( v126 )
      {
        v126 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v49 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      v50 = a5;
      if ( a5 )
      {
        a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      return v35;
    }
    v51 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v125 + 56LL))(v125, &v131);
    v35 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x681,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v51,
        v125);
      v52 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v52 + 16LL))(v52);
      }
      v53 = v126;
      if ( v126 )
      {
        v126 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      v54 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v55 = a5;
      if ( a5 )
      {
        a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      return v35;
    }
    while ( v131 )
    {
      v129[0] = 0;
      v56 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v125 + 48LL))(v125, v129);
      v35 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x686,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v56,
          v125);
        v79 = v129[0];
        if ( v129[0] )
        {
          v129[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        }
        v80 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v80 + 16LL))(v80);
        }
        v81 = v126;
        if ( v126 )
        {
          v126 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        }
        v82 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
        }
        v83 = a5;
        if ( a5 )
        {
          a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        }
        return v35;
      }
      v57 = *v127;
      v58 = v129[0];
      v129[0] = 0;
      v59 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v57 + 104))(v127, v58);
      v35 = v59;
      if ( v59 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x688,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v59,
          v125);
        v74 = v129[0];
        if ( v129[0] )
        {
          v129[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        }
        v75 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v75 + 16LL))(v75);
        }
        v76 = v126;
        if ( v126 )
        {
          v126 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        }
        v77 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        }
        v78 = a5;
        if ( a5 )
        {
          a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        }
        return v35;
      }
      v60 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v125 + 64LL))(v125, &v131);
      v35 = v60;
      if ( v60 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x689,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v60,
          v125);
        v69 = v129[0];
        if ( v129[0] )
        {
          v129[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        }
        v70 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v70 + 16LL))(v70);
        }
        v71 = v126;
        if ( v126 )
        {
          v126 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
        }
        v72 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        }
        v73 = a5;
        if ( a5 )
        {
          a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
        }
        return v35;
      }
      v61 = v129[0];
      if ( v129[0] )
      {
        v129[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      }
    }
  }
  v128 = 0;
  v62 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v9 + 80LL))(v9, &v128);
  v63 = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68E,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v62,
      v125);
    v64 = v128;
    if ( v128 )
    {
      v128 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
    }
    v65 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v65 + 16LL))(v65);
    }
    v66 = v126;
    if ( v126 )
    {
      v126 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = a5;
    if ( a5 )
    {
      a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    return v63;
  }
  if ( a2 )
  {
    v84 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v125);
    v63 = v84;
    if ( v84 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x691,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v84,
        v125);
      v85 = v128;
      if ( v128 )
      {
        v128 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v85 + 16LL))(v85);
      }
      v86 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v86 + 16LL))(v86);
      }
      v87 = v126;
      if ( v126 )
      {
        v126 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      }
      v88 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      v89 = a5;
      if ( a5 )
      {
        a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      }
      return v63;
    }
    v90 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v125 + 56LL))(v125, &v131);
    v63 = v90;
    if ( v90 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x692,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v90,
        v125);
      v91 = v128;
      if ( v128 )
      {
        v128 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v91 + 16LL))(v91);
      }
      v92 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v92 + 16LL))(v92);
      }
      v93 = v126;
      if ( v126 )
      {
        v126 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
      }
      v94 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      v95 = a5;
      if ( a5 )
      {
        a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      }
      return v63;
    }
    while ( v131 )
    {
      v129[0] = 0;
      v96 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v125 + 48LL))(v125, v129);
      v63 = v96;
      if ( v96 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x697,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v96,
          v125);
        v119 = v129[0];
        if ( v129[0] )
        {
          v129[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
        }
        v120 = v128;
        if ( v128 )
        {
          v128 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v120 + 16LL))(v120);
        }
        v121 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v121 + 16LL))(v121);
        }
        v122 = v126;
        if ( v126 )
        {
          v126 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
        }
        v123 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        }
        v124 = a5;
        if ( a5 )
        {
          a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
        }
        return v63;
      }
      v97 = *v128;
      v98 = v129[0];
      v129[0] = 0;
      v99 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v97 + 104))(v128, v98);
      v63 = v99;
      if ( v99 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x699,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v99,
          v125);
        v113 = v129[0];
        if ( v129[0] )
        {
          v129[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
        }
        v114 = v128;
        if ( v128 )
        {
          v128 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v114 + 16LL))(v114);
        }
        v115 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v115 + 16LL))(v115);
        }
        v116 = v126;
        if ( v126 )
        {
          v126 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
        }
        v117 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
        }
        v118 = a5;
        if ( a5 )
        {
          a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
        }
        return v63;
      }
      v100 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v125 + 64LL))(v125, &v131);
      v63 = v100;
      if ( v100 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69A,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v100,
          v125);
        v107 = v129[0];
        if ( v129[0] )
        {
          v129[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        }
        v108 = v128;
        if ( v128 )
        {
          v128 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v108 + 16LL))(v108);
        }
        v109 = v127;
        if ( v127 )
        {
          v127 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v109 + 16LL))(v109);
        }
        v110 = v126;
        if ( v126 )
        {
          v126 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        }
        v111 = v125;
        if ( v125 )
        {
          v125 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
        }
        v112 = a5;
        if ( a5 )
        {
          a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
        }
        return v63;
      }
      v101 = v129[0];
      if ( v129[0] )
      {
        v129[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
      }
    }
  }
  v102 = v128;
  if ( v128 )
  {
    v128 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v102 + 16LL))(v102);
  }
  v103 = v127;
  if ( v127 )
  {
    v127 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v103 + 16LL))(v103);
  }
  v104 = v126;
  if ( v126 )
  {
    v126 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  }
  v105 = v125;
  if ( v125 )
  {
    v125 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
  }
  v106 = a5;
  if ( a5 )
  {
    a5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e7e4  push    rbp
0x18001e7e6  push    rbx
0x18001e7e7  push    rsi
0x18001e7e8  push    rdi
0x18001e7e9  push    r12
0x18001e7eb  push    r13
0x18001e7ed  push    r14
0x18001e7ef  push    r15
0x18001e7f1  mov     rbp, rsp
0x18001e7f4  sub     rsp, 58h
0x18001e7f8  mov     r12b, r9b
0x18001e7fb  mov     edi, r8d
0x18001e7fe  mov     r15, rdx
0x18001e801  mov     r14, rcx
0x18001e804  mov     rbx, [rbp+arg_20]
0x18001e808  mov     rax, [rbx]
0x18001e80b  mov     edx, r8d
0x18001e80e  shr     edx, 1
0x18001e810  and     dl, 1
0x18001e813  mov     rcx, rbx
0x18001e816  mov     rax, [rax+88h]
0x18001e81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e822  mov     esi, eax
0x18001e824  xor     r13d, r13d
0x18001e827  test    eax, eax
0x18001e829  jns     short loc_18001E84A
0x18001e82b  mov     edx, 65Ah; void *
0x18001e830  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e837  mov     r9d, esi; char *
0x18001e83a  mov     rcx, [rbp+40h]; this
0x18001e83e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e843  mov     eax, esi
0x18001e845  jmp     loc_18001F3BD
0x18001e84a  mov     rax, [rbx]
0x18001e84d  mov     dl, dil
0x18001e850  and     dl, 1
0x18001e853  mov     rcx, rbx
0x18001e856  mov     rax, [rax+98h]
0x18001e85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e862  mov     esi, eax
0x18001e864  test    eax, eax
0x18001e866  jns     short loc_18001E86F
0x18001e868  mov     edx, 65Bh
0x18001e86d  jmp     short loc_18001E830
0x18001e86f  mov     rax, [rbx]
0x18001e872  mov     edx, edi
0x18001e874  shr     edx, 6
0x18001e877  and     dl, 1
0x18001e87a  mov     rcx, rbx
0x18001e87d  mov     rax, [rax+0A8h]
0x18001e884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e889  mov     esi, eax
0x18001e88b  test    eax, eax
0x18001e88d  jns     short loc_18001E896
0x18001e88f  mov     edx, 65Ch
0x18001e894  jmp     short loc_18001E830
0x18001e896  mov     rax, [rbx]
0x18001e899  mov     edx, edi
0x18001e89b  shr     edx, 12h
0x18001e89e  and     dl, 1
0x18001e8a1  mov     rcx, rbx
0x18001e8a4  mov     rax, [rax+0B8h]
0x18001e8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8b0  mov     esi, eax
0x18001e8b2  test    eax, eax
0x18001e8b4  jns     short loc_18001E8C0
0x18001e8b6  mov     edx, 65Dh
0x18001e8bb  jmp     loc_18001E830
0x18001e8c0  mov     rax, [rbx]
0x18001e8c3  mov     edx, edi
0x18001e8c5  shr     edx, 5
0x18001e8c8  and     dl, 1
0x18001e8cb  mov     rcx, rbx
0x18001e8ce  mov     rax, [rax+0C8h]
0x18001e8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8da  mov     esi, eax
0x18001e8dc  test    eax, eax
0x18001e8de  jns     short loc_18001E8EA
0x18001e8e0  mov     edx, 65Eh
0x18001e8e5  jmp     loc_18001E830
0x18001e8ea  mov     rax, [rbx]
0x18001e8ed  mov     edx, edi
0x18001e8ef  shr     edx, 8
0x18001e8f2  and     dl, 1
0x18001e8f5  mov     rcx, rbx
0x18001e8f8  mov     rax, [rax+0D8h]
0x18001e8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e904  mov     esi, eax
0x18001e906  test    eax, eax
0x18001e908  jns     short loc_18001E914
0x18001e90a  mov     edx, 65Fh
0x18001e90f  jmp     loc_18001E830
0x18001e914  mov     rax, [rbx]
0x18001e917  mov     edx, edi
0x18001e919  shr     edx, 15h
0x18001e91c  and     dl, 1
0x18001e91f  mov     rcx, rbx
0x18001e922  mov     rax, [rax+0E8h]
0x18001e929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e92e  mov     esi, eax
0x18001e930  test    eax, eax
0x18001e932  jns     short loc_18001E93E
0x18001e934  mov     edx, 660h
0x18001e939  jmp     loc_18001E830
0x18001e93e  mov     rax, [rbx]
0x18001e941  mov     dl, r12b
0x18001e944  mov     rcx, rbx
0x18001e947  mov     rax, [rax+118h]
0x18001e94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e953  mov     esi, eax
0x18001e955  test    eax, eax
0x18001e957  jns     short loc_18001E963
0x18001e959  mov     edx, 661h
0x18001e95e  jmp     loc_18001E830
0x18001e963  mov     [rbp+arg_20], r13
0x18001e967  mov     rax, [rbx]
0x18001e96a  lea     r8, [rbp+arg_20]
0x18001e96e  lea     rdx, _GUID_4236972c_2b83_4776_9aa3_565e11029a41
0x18001e975  mov     rcx, rbx
0x18001e978  mov     rax, [rax]
0x18001e97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e980  mov     esi, eax
0x18001e982  test    eax, eax
0x18001e984  jns     short loc_18001E9BE
0x18001e986  mov     rcx, [rbp+40h]; this
0x18001e98a  mov     r9d, eax; char *
0x18001e98d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e994  mov     edx, 665h; void *
0x18001e999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e99e  nop
0x18001e99f  mov     rcx, [rbp+arg_20]
0x18001e9a3  test    rcx, rcx
0x18001e9a6  jz      short loc_18001E9B9
0x18001e9a8  mov     [rbp+arg_20], r13
0x18001e9ac  mov     rax, [rcx]
0x18001e9af  mov     rax, [rax+10h]
0x18001e9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9b8  nop
0x18001e9b9  jmp     loc_18001E843
0x18001e9be  mov     rcx, [rbp+arg_20]
0x18001e9c2  mov     rax, [rcx]
0x18001e9c5  mov     edx, edi
0x18001e9c7  shr     edx, 4
0x18001e9ca  mov     r12b, 1
0x18001e9cd  and     dl, r12b
0x18001e9d0  mov     rax, [rax+58h]
0x18001e9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9d9  mov     esi, eax
0x18001e9db  test    eax, eax
0x18001e9dd  jns     short loc_18001EA17
0x18001e9df  mov     rcx, [rbp+40h]; this
0x18001e9e3  mov     r9d, eax; char *
0x18001e9e6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e9ed  mov     edx, 666h; void *
0x18001e9f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9f7  nop
0x18001e9f8  mov     rcx, [rbp+arg_20]
0x18001e9fc  test    rcx, rcx
0x18001e9ff  jz      short loc_18001EA12
0x18001ea01  mov     [rbp+arg_20], r13
0x18001ea05  mov     rax, [rcx]
0x18001ea08  mov     rax, [rax+10h]
0x18001ea0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea11  nop
0x18001ea12  jmp     loc_18001E843
0x18001ea17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass> `wil::Feature<__WilFeatureTraits_Feature_SignatureValidationBypass>::GetImpl(void)'::`2'::impl
0x18001ea1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass>::__private_IsEnabled(void)
0x18001ea23  test    al, al
0x18001ea25  jnz     short loc_18001EA7D
0x18001ea27  mov     rcx, [rbp+arg_20]
0x18001ea2b  mov     rax, [rcx]
0x18001ea2e  mov     edx, edi
0x18001ea30  shr     edx, 0Fh
0x18001ea33  and     dl, r12b
0x18001ea36  mov     rax, [rax+68h]
0x18001ea3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea3f  mov     esi, eax
0x18001ea41  test    eax, eax
0x18001ea43  jns     short loc_18001EA7D
0x18001ea45  mov     rcx, [rbp+40h]; this
0x18001ea49  mov     r9d, eax; char *
0x18001ea4c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001ea53  mov     edx, 66Eh; void *
0x18001ea58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea5d  nop
0x18001ea5e  mov     rcx, [rbp+arg_20]
0x18001ea62  test    rcx, rcx
0x18001ea65  jz      short loc_18001EA78
0x18001ea67  mov     [rbp+arg_20], r13
0x18001ea6b  mov     rax, [rcx]
0x18001ea6e  mov     rax, [rax+10h]
0x18001ea72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea77  nop
0x18001ea78  jmp     loc_18001E843
0x18001ea7d  mov     rcx, [rbp+arg_20]
0x18001ea81  mov     rax, [rcx]
0x18001ea84  mov     edx, edi
0x18001ea86  shr     edx, 19h
0x18001ea89  and     dl, r12b
0x18001ea8c  mov     rax, [rax+78h]
0x18001ea90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea95  mov     esi, eax
0x18001ea97  test    eax, eax
0x18001ea99  jns     short loc_18001EAD3
0x18001ea9b  mov     rcx, [rbp+40h]; this
0x18001ea9f  mov     r9d, eax; char *
0x18001eaa2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001eaa9  mov     edx, 671h; void *
0x18001eaae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eab3  nop
0x18001eab4  mov     rcx, [rbp+arg_20]
0x18001eab8  test    rcx, rcx
0x18001eabb  jz      short loc_18001EACE
0x18001eabd  mov     [rbp+arg_20], r13
0x18001eac1  mov     rax, [rcx]
0x18001eac4  mov     rax, [rax+10h]
0x18001eac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eacd  nop
0x18001eace  jmp     loc_18001E843
0x18001ead3  mov     rcx, [rbp+arg_20]
0x18001ead7  mov     rax, [rcx]
0x18001eada  mov     edx, edi
0x18001eadc  shr     edx, 1Ah
0x18001eadf  and     dl, r12b
0x18001eae2  mov     rax, [rax+88h]
0x18001eae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaee  mov     esi, eax
0x18001eaf0  test    eax, eax
0x18001eaf2  jns     short loc_18001EB2C
0x18001eaf4  mov     rcx, [rbp+40h]; this
0x18001eaf8  mov     r9d, eax; char *
0x18001eafb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001eb02  mov     edx, 672h; void *
0x18001eb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb0c  nop
0x18001eb0d  mov     rcx, [rbp+arg_20]
0x18001eb11  test    rcx, rcx
0x18001eb14  jz      short loc_18001EB27
0x18001eb16  mov     [rbp+arg_20], r13
0x18001eb1a  mov     rax, [rcx]
0x18001eb1d  mov     rax, [rax+10h]
0x18001eb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb26  nop
0x18001eb27  jmp     loc_18001E843
0x18001eb2c  mov     rcx, [rbp+arg_20]
0x18001eb30  mov     rax, [rcx]
0x18001eb33  shr     edi, 1Bh
0x18001eb36  and     dil, r12b
0x18001eb39  mov     dl, dil
0x18001eb3c  mov     rax, [rax+98h]
0x18001eb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb48  mov     edi, eax
0x18001eb4a  test    eax, eax
0x18001eb4c  jns     short loc_18001EB88
0x18001eb4e  mov     rcx, [rbp+40h]; this
0x18001eb52  mov     r9d, eax; char *
0x18001eb55  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001eb5c  mov     edx, 673h; void *
0x18001eb61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb66  nop
0x18001eb67  mov     rcx, [rbp+arg_20]
0x18001eb6b  test    rcx, rcx
0x18001eb6e  jz      short loc_18001EB81
0x18001eb70  mov     [rbp+arg_20], r13
0x18001eb74  mov     rax, [rcx]
0x18001eb77  mov     rax, [rax+10h]
0x18001eb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb80  nop
0x18001eb81  mov     eax, edi
0x18001eb83  jmp     loc_18001F3BD
0x18001eb88  mov     [rbp+var_38], r13
0x18001eb8c  mov     [rbp+arg_10], r13b
0x18001eb90  mov     [rbp+var_30], r13
0x18001eb94  lea     rcx, [rbp+var_30]
0x18001eb98  call    ?Make@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@SAJPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>::Make(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18001eb9d  mov     edi, eax
0x18001eb9f  test    eax, eax
0x18001eba1  jns     short loc_18001EC0F
0x18001eba3  mov     rcx, [rbp+40h]; this
0x18001eba7  mov     r9d, eax; char *
0x18001ebaa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001ebb1  mov     edx, 67Ah; void *
0x18001ebb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ebbb  nop
0x18001ebbc  mov     rcx, [rbp+var_30]
0x18001ebc0  test    rcx, rcx
0x18001ebc3  jz      short loc_18001EBD6
0x18001ebc5  mov     [rbp+var_30], r13
0x18001ebc9  mov     rax, [rcx]
0x18001ebcc  mov     rax, [rax+10h]
0x18001ebd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebd5  nop
0x18001ebd6  mov     rcx, [rbp+var_38]
0x18001ebda  test    rcx, rcx
0x18001ebdd  jz      short loc_18001EBF0
0x18001ebdf  mov     [rbp+var_38], r13
0x18001ebe3  mov     rax, [rcx]
0x18001ebe6  mov     rax, [rax+10h]
0x18001ebea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebef  nop
  ... truncated ...
```
