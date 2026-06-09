# ConvertDeploymentOptionsToAddPackageOptions

- ea: `0x18001fdbc`
- end: `0x180020bd5`
- name: `ConvertDeploymentOptionsToAddPackageOptions`
- size: `3609`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180021650`

## callees

- `0x18000d3dc`
- `0x18001fdbc`
- `0x180024558`
- `0x1800295bc`
- `0x180070010`

## string_xrefs

- `0x18001fe08`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ff65`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001ffbe`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020024`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002007a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800200d3`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002012d`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020182`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002020f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800202bb`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002035f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002048c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002052e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800205ce`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002066e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020734`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800207f2`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800209ae`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020a68`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020b22`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

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
0x18001fdbc  push    rbp
0x18001fdbe  push    rbx
0x18001fdbf  push    rsi
0x18001fdc0  push    rdi
0x18001fdc1  push    r12
0x18001fdc3  push    r13
0x18001fdc5  push    r14
0x18001fdc7  push    r15
0x18001fdc9  mov     rbp, rsp
0x18001fdcc  sub     rsp, 58h
0x18001fdd0  mov     r12b, r9b
0x18001fdd3  mov     edi, r8d
0x18001fdd6  mov     r15, rdx
0x18001fdd9  mov     r14, rcx
0x18001fddc  mov     rbx, [rbp+arg_20]
0x18001fde0  mov     rax, [rbx]
0x18001fde3  mov     edx, r8d
0x18001fde6  shr     edx, 1
0x18001fde8  and     dl, 1
0x18001fdeb  mov     rcx, rbx
0x18001fdee  mov     rax, [rax+88h]
0x18001fdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdfa  mov     esi, eax
0x18001fdfc  xor     r13d, r13d
0x18001fdff  test    eax, eax
0x18001fe01  jns     short loc_18001FE22
0x18001fe03  mov     edx, 65Ah; void *
0x18001fe08  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fe0f  mov     r9d, esi; char *
0x18001fe12  mov     rcx, [rbp+40h]; this
0x18001fe16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe1b  mov     eax, esi
0x18001fe1d  jmp     loc_180020995
0x18001fe22  mov     rax, [rbx]
0x18001fe25  mov     dl, dil
0x18001fe28  and     dl, 1
0x18001fe2b  mov     rcx, rbx
0x18001fe2e  mov     rax, [rax+98h]
0x18001fe35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe3a  mov     esi, eax
0x18001fe3c  test    eax, eax
0x18001fe3e  jns     short loc_18001FE47
0x18001fe40  mov     edx, 65Bh
0x18001fe45  jmp     short loc_18001FE08
0x18001fe47  mov     rax, [rbx]
0x18001fe4a  mov     edx, edi
0x18001fe4c  shr     edx, 6
0x18001fe4f  and     dl, 1
0x18001fe52  mov     rcx, rbx
0x18001fe55  mov     rax, [rax+0A8h]
0x18001fe5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe61  mov     esi, eax
0x18001fe63  test    eax, eax
0x18001fe65  jns     short loc_18001FE6E
0x18001fe67  mov     edx, 65Ch
0x18001fe6c  jmp     short loc_18001FE08
0x18001fe6e  mov     rax, [rbx]
0x18001fe71  mov     edx, edi
0x18001fe73  shr     edx, 12h
0x18001fe76  and     dl, 1
0x18001fe79  mov     rcx, rbx
0x18001fe7c  mov     rax, [rax+0B8h]
0x18001fe83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe88  mov     esi, eax
0x18001fe8a  test    eax, eax
0x18001fe8c  jns     short loc_18001FE98
0x18001fe8e  mov     edx, 65Dh
0x18001fe93  jmp     loc_18001FE08
0x18001fe98  mov     rax, [rbx]
0x18001fe9b  mov     edx, edi
0x18001fe9d  shr     edx, 5
0x18001fea0  and     dl, 1
0x18001fea3  mov     rcx, rbx
0x18001fea6  mov     rax, [rax+0C8h]
0x18001fead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feb2  mov     esi, eax
0x18001feb4  test    eax, eax
0x18001feb6  jns     short loc_18001FEC2
0x18001feb8  mov     edx, 65Eh
0x18001febd  jmp     loc_18001FE08
0x18001fec2  mov     rax, [rbx]
0x18001fec5  mov     edx, edi
0x18001fec7  shr     edx, 8
0x18001feca  and     dl, 1
0x18001fecd  mov     rcx, rbx
0x18001fed0  mov     rax, [rax+0D8h]
0x18001fed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fedc  mov     esi, eax
0x18001fede  test    eax, eax
0x18001fee0  jns     short loc_18001FEEC
0x18001fee2  mov     edx, 65Fh
0x18001fee7  jmp     loc_18001FE08
0x18001feec  mov     rax, [rbx]
0x18001feef  mov     edx, edi
0x18001fef1  shr     edx, 15h
0x18001fef4  and     dl, 1
0x18001fef7  mov     rcx, rbx
0x18001fefa  mov     rax, [rax+0E8h]
0x18001ff01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff06  mov     esi, eax
0x18001ff08  test    eax, eax
0x18001ff0a  jns     short loc_18001FF16
0x18001ff0c  mov     edx, 660h
0x18001ff11  jmp     loc_18001FE08
0x18001ff16  mov     rax, [rbx]
0x18001ff19  mov     dl, r12b
0x18001ff1c  mov     rcx, rbx
0x18001ff1f  mov     rax, [rax+118h]
0x18001ff26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff2b  mov     esi, eax
0x18001ff2d  test    eax, eax
0x18001ff2f  jns     short loc_18001FF3B
0x18001ff31  mov     edx, 661h
0x18001ff36  jmp     loc_18001FE08
0x18001ff3b  mov     [rbp+arg_20], r13
0x18001ff3f  mov     rax, [rbx]
0x18001ff42  lea     r8, [rbp+arg_20]
0x18001ff46  lea     rdx, _GUID_4236972c_2b83_4776_9aa3_565e11029a41
0x18001ff4d  mov     rcx, rbx
0x18001ff50  mov     rax, [rax]
0x18001ff53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff58  mov     esi, eax
0x18001ff5a  test    eax, eax
0x18001ff5c  jns     short loc_18001FF96
0x18001ff5e  mov     rcx, [rbp+40h]; this
0x18001ff62  mov     r9d, eax; char *
0x18001ff65  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001ff6c  mov     edx, 665h; void *
0x18001ff71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff76  nop
0x18001ff77  mov     rcx, [rbp+arg_20]
0x18001ff7b  test    rcx, rcx
0x18001ff7e  jz      short loc_18001FF91
0x18001ff80  mov     [rbp+arg_20], r13
0x18001ff84  mov     rax, [rcx]
0x18001ff87  mov     rax, [rax+10h]
0x18001ff8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff90  nop
0x18001ff91  jmp     loc_18001FE1B
0x18001ff96  mov     rcx, [rbp+arg_20]
0x18001ff9a  mov     rax, [rcx]
0x18001ff9d  mov     edx, edi
0x18001ff9f  shr     edx, 4
0x18001ffa2  mov     r12b, 1
0x18001ffa5  and     dl, r12b
0x18001ffa8  mov     rax, [rax+58h]
0x18001ffac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffb1  mov     esi, eax
0x18001ffb3  test    eax, eax
0x18001ffb5  jns     short loc_18001FFEF
0x18001ffb7  mov     rcx, [rbp+40h]; this
0x18001ffbb  mov     r9d, eax; char *
0x18001ffbe  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001ffc5  mov     edx, 666h; void *
0x18001ffca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffcf  nop
0x18001ffd0  mov     rcx, [rbp+arg_20]
0x18001ffd4  test    rcx, rcx
0x18001ffd7  jz      short loc_18001FFEA
0x18001ffd9  mov     [rbp+arg_20], r13
0x18001ffdd  mov     rax, [rcx]
0x18001ffe0  mov     rax, [rax+10h]
0x18001ffe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffe9  nop
0x18001ffea  jmp     loc_18001FE1B
0x18001ffef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass> `wil::Feature<__WilFeatureTraits_Feature_SignatureValidationBypass>::GetImpl(void)'::`2'::impl
0x18001fff6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass>::__private_IsEnabled(void)
0x18001fffb  test    al, al
0x18001fffd  jnz     short loc_180020055
0x18001ffff  mov     rcx, [rbp+arg_20]
0x180020003  mov     rax, [rcx]
0x180020006  mov     edx, edi
0x180020008  shr     edx, 0Fh
0x18002000b  and     dl, r12b
0x18002000e  mov     rax, [rax+68h]
0x180020012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020017  mov     esi, eax
0x180020019  test    eax, eax
0x18002001b  jns     short loc_180020055
0x18002001d  mov     rcx, [rbp+40h]; this
0x180020021  mov     r9d, eax; char *
0x180020024  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002002b  mov     edx, 66Eh; void *
0x180020030  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020035  nop
0x180020036  mov     rcx, [rbp+arg_20]
0x18002003a  test    rcx, rcx
0x18002003d  jz      short loc_180020050
0x18002003f  mov     [rbp+arg_20], r13
0x180020043  mov     rax, [rcx]
0x180020046  mov     rax, [rax+10h]
0x18002004a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002004f  nop
0x180020050  jmp     loc_18001FE1B
0x180020055  mov     rcx, [rbp+arg_20]
0x180020059  mov     rax, [rcx]
0x18002005c  mov     edx, edi
0x18002005e  shr     edx, 19h
0x180020061  and     dl, r12b
0x180020064  mov     rax, [rax+78h]
0x180020068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002006d  mov     esi, eax
0x18002006f  test    eax, eax
0x180020071  jns     short loc_1800200AB
0x180020073  mov     rcx, [rbp+40h]; this
0x180020077  mov     r9d, eax; char *
0x18002007a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020081  mov     edx, 671h; void *
0x180020086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002008b  nop
0x18002008c  mov     rcx, [rbp+arg_20]
0x180020090  test    rcx, rcx
0x180020093  jz      short loc_1800200A6
0x180020095  mov     [rbp+arg_20], r13
0x180020099  mov     rax, [rcx]
0x18002009c  mov     rax, [rax+10h]
0x1800200a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200a5  nop
0x1800200a6  jmp     loc_18001FE1B
0x1800200ab  mov     rcx, [rbp+arg_20]
0x1800200af  mov     rax, [rcx]
0x1800200b2  mov     edx, edi
0x1800200b4  shr     edx, 1Ah
0x1800200b7  and     dl, r12b
0x1800200ba  mov     rax, [rax+88h]
0x1800200c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200c6  mov     esi, eax
0x1800200c8  test    eax, eax
0x1800200ca  jns     short loc_180020104
0x1800200cc  mov     rcx, [rbp+40h]; this
0x1800200d0  mov     r9d, eax; char *
0x1800200d3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800200da  mov     edx, 672h; void *
0x1800200df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200e4  nop
0x1800200e5  mov     rcx, [rbp+arg_20]
0x1800200e9  test    rcx, rcx
0x1800200ec  jz      short loc_1800200FF
0x1800200ee  mov     [rbp+arg_20], r13
0x1800200f2  mov     rax, [rcx]
0x1800200f5  mov     rax, [rax+10h]
0x1800200f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200fe  nop
0x1800200ff  jmp     loc_18001FE1B
0x180020104  mov     rcx, [rbp+arg_20]
0x180020108  mov     rax, [rcx]
0x18002010b  shr     edi, 1Bh
0x18002010e  and     dil, r12b
0x180020111  mov     dl, dil
0x180020114  mov     rax, [rax+98h]
0x18002011b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020120  mov     edi, eax
0x180020122  test    eax, eax
0x180020124  jns     short loc_180020160
0x180020126  mov     rcx, [rbp+40h]; this
0x18002012a  mov     r9d, eax; char *
0x18002012d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020134  mov     edx, 673h; void *
0x180020139  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002013e  nop
0x18002013f  mov     rcx, [rbp+arg_20]
0x180020143  test    rcx, rcx
0x180020146  jz      short loc_180020159
0x180020148  mov     [rbp+arg_20], r13
0x18002014c  mov     rax, [rcx]
0x18002014f  mov     rax, [rax+10h]
0x180020153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020158  nop
0x180020159  mov     eax, edi
0x18002015b  jmp     loc_180020995
0x180020160  mov     [rbp+var_38], r13
0x180020164  mov     [rbp+arg_10], r13b
0x180020168  mov     [rbp+var_30], r13
0x18002016c  lea     rcx, [rbp+var_30]
0x180020170  call    ?Make@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@SAJPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>::Make(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x180020175  mov     edi, eax
0x180020177  test    eax, eax
0x180020179  jns     short loc_1800201E7
0x18002017b  mov     rcx, [rbp+40h]; this
0x18002017f  mov     r9d, eax; char *
0x180020182  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020189  mov     edx, 67Ah; void *
0x18002018e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020193  nop
0x180020194  mov     rcx, [rbp+var_30]
0x180020198  test    rcx, rcx
0x18002019b  jz      short loc_1800201AE
0x18002019d  mov     [rbp+var_30], r13
0x1800201a1  mov     rax, [rcx]
0x1800201a4  mov     rax, [rax+10h]
0x1800201a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201ad  nop
0x1800201ae  mov     rcx, [rbp+var_38]
0x1800201b2  test    rcx, rcx
0x1800201b5  jz      short loc_1800201C8
0x1800201b7  mov     [rbp+var_38], r13
0x1800201bb  mov     rax, [rcx]
0x1800201be  mov     rax, [rax+10h]
0x1800201c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201c7  nop
  ... truncated ...
```
