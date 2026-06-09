# CActivatedEventArgsBase::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180017108`
- end: `0x180017f0f`
- name: `?RuntimeClassInitialize@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `3591`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016298`

## callees

- `0x180001dc0`
- `0x18000e284`
- `0x18000ed10`
- `0x180016004`
- `0x180017108`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800171ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800172e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800173f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800174f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800175e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800176d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800177df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800178e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800179e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800171ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800172e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800173f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800174f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800175e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800176d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800177df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800178e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800179e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017aea`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::RuntimeClassInitialize(
        CActivatedEventArgsBase *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64))
{
  __int64 (__fastcall **v2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rax
  __int64 (__fastcall *v5)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rbx
  __int64 v6; // rax
  int v7; // eax
  int v8; // ebx
  __int64 *v9; // rcx
  __int64 *v11; // rbx
  __int64 v12; // rdi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 *v20; // rbx
  int v21; // r15d
  __int64 v22; // rdi
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  int v26; // eax
  __int64 (__fastcall ***v27)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 *v30; // rbx
  int v31; // r14d
  __int64 v32; // rdi
  HRESULT v33; // eax
  int v34; // edx
  unsigned int v35; // r8d
  int v36; // eax
  __int64 (__fastcall ***v37)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 *v40; // rbx
  __int64 v41; // rdi
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v46; // rcx
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64 *); // rdi
  int v48; // eax
  __int64 v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 *v51; // rbx
  __int64 v52; // rdi
  HRESULT v53; // eax
  int v54; // edx
  unsigned int v55; // r8d
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v57; // rcx
  __int64 (__fastcall *v58)(_QWORD, GUID *, __int64 *); // rdi
  int v59; // eax
  __int64 v60; // rcx
  __int64 (__fastcall ***v61)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 *v62; // rbx
  __int64 v63; // rdi
  HRESULT v64; // eax
  int v65; // edx
  unsigned int v66; // r8d
  int v67; // eax
  __int64 (__fastcall ***v68)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 *v71; // rbx
  __int64 v72; // rdi
  HRESULT v73; // eax
  int v74; // edx
  unsigned int v75; // r8d
  int v76; // eax
  __int64 (__fastcall ***v77)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 *v80; // rbx
  __int64 v81; // rdi
  HRESULT v82; // eax
  int v83; // edx
  unsigned int v84; // r8d
  int v85; // eax
  __int64 (__fastcall ***v86)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 *v89; // rbx
  __int64 v90; // rdi
  HRESULT v91; // eax
  int v92; // edx
  unsigned int v93; // r8d
  int v94; // eax
  __int64 (__fastcall ***v95)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 *v98; // rbx
  __int64 v99; // rdi
  HRESULT v100; // eax
  int v101; // edx
  unsigned int v102; // r8d
  int v103; // eax
  __int64 (__fastcall ***v104)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rbx
  __int64 v108; // rcx
  __int64 v109; // rbx
  __int64 v110; // rcx
  bool v111; // zf
  __int128 v112; // xmm0
  __int64 v113; // rcx
  __int64 (__fastcall ***v114)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v115; // rcx
  __int64 (__fastcall ***v116)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v117; // rcx
  __int64 (__fastcall ***v118)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v119; // rcx
  __int64 (__fastcall ***v120)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v121; // rcx
  __int64 (__fastcall ***v122)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v123; // rcx
  __int64 (__fastcall ***v124)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v125; // rcx
  __int64 (__fastcall ***v126)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v127; // rcx
  __int64 (__fastcall ***v128)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v129; // rcx
  __int64 (__fastcall ***v130)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v131; // rcx
  __int64 (__fastcall ***v132)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 *v133; // rcx
  int v134[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v135)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-D8h] BYREF
  __int64 v136; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v137)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v138; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v139)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v140; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v141; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v142; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v143)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v144)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v145)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v146; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v147)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-78h] BYREF
  __int64 v148; // [rsp+90h] [rbp-70h] BYREF
  char v149; // [rsp+98h] [rbp-68h] BYREF
  char v150; // [rsp+99h] [rbp-67h] BYREF
  _BYTE v151[6]; // [rsp+9Ah] [rbp-66h] BYREF
  __int64 (__fastcall ***v152)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-60h] BYREF
  __int64 v153; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v154)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-50h] BYREF
  __int64 v155; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v156)(_QWORD, GUID *, __int64 *); // [rsp+C0h] [rbp-40h] BYREF
  __int64 v157; // [rsp+C8h] [rbp-38h] BYREF
  int v158; // [rsp+D0h] [rbp-30h] BYREF
  int v159; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v160; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v161; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  __int128 v164; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = *a2;
  *(_QWORD *)v134 = 0;
  v5 = *v2;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(v134);
  v7 = v5((struct Windows::Foundation::Collections::IPropertySet *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v7,
      v134[0]);
LABEL_3:
    v9 = *(__int64 **)v134;
    if ( *(_QWORD *)v134 )
    {
      *(_QWORD *)v134 = 0;
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
    }
    return (unsigned int)v8;
  }
  v11 = *(__int64 **)v134;
  v135 = 0;
  v12 = **(_QWORD **)v134;
  string = 0;
  v13 = WindowsCreateStringReference(L"ActivationKind", 0xEu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v12 + 48))(v11, string, &v135);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v16,
      v134[0]);
LABEL_9:
    v17 = v135;
    if ( v135 )
    {
      v135 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v17)[2])(v17);
    }
    goto LABEL_3;
  }
  v136 = 0;
  v8 = (**v135)(v135, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v136);
  if ( v8 < 0 )
  {
    v18 = 201;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_14:
    v19 = v136;
    if ( v136 )
    {
      v136 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_9;
  }
  v158 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v136 + 96LL))(v136, &v158);
  if ( v8 < 0 )
  {
    v18 = 203;
    goto LABEL_13;
  }
  v20 = *(__int64 **)v134;
  v21 = v158;
  v137 = 0;
  v22 = **(_QWORD **)v134;
  string = 0;
  v23 = WindowsCreateStringReference(L"PreviousExecutionState", 0x16u, &hstringHeader, &string);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    __debugbreak();
  }
  v26 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v22 + 48))(v20, string, &v137);
  v8 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v26,
      v134[0]);
LABEL_21:
    v27 = v137;
    if ( v137 )
    {
      v137 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v27)[2])(v27);
    }
    goto LABEL_14;
  }
  v138 = 0;
  v8 = (**v137)(v137, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v138);
  if ( v8 < 0 )
  {
    v28 = 210;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_26:
    v29 = v138;
    if ( v138 )
    {
      v138 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    goto LABEL_21;
  }
  v159 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v138 + 96LL))(v138, &v159);
  if ( v8 < 0 )
  {
    v28 = 212;
    goto LABEL_25;
  }
  v30 = *(__int64 **)v134;
  v31 = v159;
  v160 = 0;
  v139 = 0;
  v32 = **(_QWORD **)v134;
  string = 0;
  v33 = WindowsCreateStringReference(L"UserContext", 0xBu, &hstringHeader, &string);
  if ( v33 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v33, v34, v35);
    __debugbreak();
  }
  v36 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v32 + 48))(v30, string, &v139);
  v8 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v36,
      v134[0]);
LABEL_33:
    v37 = v139;
    if ( v139 )
    {
      v139 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v37)[2])(v37);
    }
    goto LABEL_26;
  }
  v140 = 0;
  v8 = (**v139)(v139, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v140);
  if ( v8 < 0 )
  {
    v38 = 219;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_38:
    v39 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    goto LABEL_33;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v140 + 112LL))(v140, &v160);
  if ( v8 < 0 )
  {
    v38 = 220;
    goto LABEL_37;
  }
  v40 = *(__int64 **)v134;
  v143 = 0;
  v141 = 0;
  v41 = **(_QWORD **)v134;
  string = 0;
  v42 = WindowsCreateStringReference(L"SplashScreen", 0xCu, &hstringHeader, &string);
  if ( v42 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
    __debugbreak();
  }
  if ( (*(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(v41 + 48))(v40, string, &v143) >= 0 )
  {
    v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v143;
    v46 = v141;
    v47 = **v143;
    if ( v141 )
    {
      v141 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v48 = v47(v45, &GUID_ca4d975c_d4d6_43f0_97c0_0833c6391c24, &v141);
    v8 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v48,
        v134[0]);
LABEL_48:
      v49 = v141;
      if ( v141 )
      {
        v141 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v143;
      if ( v143 )
      {
        v143 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v50)[2])(v50);
      }
      goto LABEL_38;
    }
  }
  v51 = *(__int64 **)v134;
  v144 = 0;
  v142 = 0;
  v52 = **(_QWORD **)v134;
  string = 0;
  v53 = WindowsCreateStringReference(L"ActivationValueSetReference", 0x1Bu, &hstringHeader, &string);
  if ( v53 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v53, v54, v55);
    __debugbreak();
  }
  if ( (*(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(v52 + 48))(v51, string, &v144) >= 0 )
  {
    v56 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v144;
    v57 = v142;
    v58 = **v144;
    if ( v142 )
    {
      v142 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v59 = v58(v56, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v142);
    v8 = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v59,
        v134[0]);
LABEL_58:
      v60 = v142;
      if ( v142 )
      {
        v142 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      }
      v61 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v144;
      if ( v144 )
      {
        v144 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v61)[2])(v61);
      }
      goto LABEL_48;
    }
  }
  v62 = *(__int64 **)v134;
  v149 = 1;
  v145 = 0;
  v63 = **(_QWORD **)v134;
  string = 0;
  v64 = WindowsCreateStringReference(L"IsForeground", 0xCu, &hstringHeader, &string);
  if ( v64 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v64, v65, v66);
    __debugbreak();
  }
  v67 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v63 + 48))(v62, string, &v145);
  v8 = v67;
  if ( v67 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v67,
      v134[0]);
LABEL_65:
    v68 = v145;
    if ( v145 )
    {
      v145 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v68)[2])(v68);
    }
    goto LABEL_58;
  }
  v146 = 0;
  v8 = (**v145)(v145, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v146);
  if ( v8 < 0 )
  {
    v69 = 240;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v69,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_70:
    v70 = v146;
    if ( v146 )
    {
      v146 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    goto LABEL_65;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v146 + 144LL))(v146, &v149);
  if ( v8 < 0 )
  {
    v69 = 241;
    goto LABEL_69;
  }
  v71 = *(__int64 **)v134;
  v150 = 0;
  v147 = 0;
  v72 = **(_QWORD **)v134;
  string = 0;
  v73 = WindowsCreateStringReference(L"IsHolographic", 0xDu, &hstringHeader, &string);
  if ( v73 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v73, v74, v75);
    __debugbreak();
  }
  v76 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v72 + 48))(v71, string, &v147);
  v8 = v76;
  if ( v76 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v76,
      v134[0]);
LABEL_77:
    v77 = v147;
    if ( v147 )
    {
      v147 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v77)[2])(v77);
    }
    goto LABEL_70;
  }
  v148 = 0;
  v8 = (**v147)(v147, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v148);
  if ( v8 < 0 )
  {
    v78 = 247;
LABEL_81:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v78,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_82:
    v79 = v148;
    if ( v148 )
    {
      v148 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    goto LABEL_77;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v148 + 144LL))(v148, &v150);
  if ( v8 < 0 )
  {
    v78 = 248;
    goto LABEL_81;
  }
  v80 = *(__int64 **)v134;
  v151[0] = 0;
  v152 = 0;
  v81 = **(_QWORD **)v134;
  string = 0;
  v82 = WindowsCreateStringReference(L"IsInitialized", 0xDu, &hstringHeader, &string);
  if ( v82 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v82, v83, v84);
    __debugbreak();
  }
  v85 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v81 + 48))(v80, string, &v152);
  v8 = v85;
  if ( v85 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v85,
      v134[0]);
LABEL_89:
    v86 = v152;
    if ( v152 )
    {
      v152 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v86)[2])(v86);
    }
    goto LABEL_82;
  }
  v153 = 0;
  v8 = (**v152)(v152, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v153);
  if ( v8 < 0 )
  {
    v87 = 254;
LABEL_93:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v87,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_94:
    v88 = v153;
    if ( v153 )
    {
      v153 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    goto LABEL_89;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v153 + 144LL))(v153, v151);
  if ( v8 < 0 )
  {
    v87 = 255;
    goto LABEL_93;
  }
  v89 = *(__int64 **)v134;
  v161 = 0;
  v154 = 0;
  v90 = **(_QWORD **)v134;
  string = 0;
  v91 = WindowsCreateStringReference(L"AamActivationId", 0xFu, &hstringHeader, &string);
  if ( v91 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v91, v92, v93);
    JUMPOUT(0x180017F0ELL);
  }
  v94 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v90 + 48))(v89, string, &v154);
  v8 = v94;
  if ( v94 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v94,
      v134[0]);
LABEL_101:
    v95 = v154;
    if ( v154 )
    {
      v154 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v95)[2])(v95);
    }
    goto LABEL_94;
  }
  v155 = 0;
  v8 = (**v154)(v154, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v155);
  if ( v8 < 0 )
  {
    v96 = 261;
LABEL_105:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v96,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
LABEL_106:
    v97 = v155;
    if ( v155 )
    {
      v155 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    }
    goto LABEL_101;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v155 + 112LL))(v155, &v161);
  if ( v8 < 0 )
  {
    v96 = 262;
    goto LABEL_105;
  }
  v98 = *(__int64 **)v134;
  v156 = 0;
  v164 = 0;
  v99 = **(_QWORD **)v134;
  string = 0;
  v100 = WindowsCreateStringReference(L"AamActivityId", 0xDu, &hstringHeader, &string);
  if ( v100 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v100, v101, v102);
    __debugbreak();
  }
  v103 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v99 + 48))(v98, string, &v156);
  v8 = v103;
  if ( v103 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v103,
      v134[0]);
LABEL_113:
    v104 = v156;
    if ( v156 )
    {
      v156 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v104)[2])(v104);
    }
    goto LABEL_106;
  }
  v157 = 0;
  v8 = (**v156)(v156, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v157);
  if ( v8 < 0 )
  {
    v105 = 268;
    goto LABEL_117;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v157 + 160LL))(v157, &v164);
  if ( v8 < 0 )
  {
    v105 = 269;
LABEL_117:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v105,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v8,
      v134[0]);
    v106 = v157;
    if ( v157 )
    {
      v157 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
    }
    goto LABEL_113;
  }
  v107 = v141;
  *((_QWORD *)this + 13) = v160;
  *((_DWORD *)this + 19) = v31;
  *((_DWORD *)this + 18) = v21;
  if ( *((_QWORD *)this + 11) != v107 )
  {
    if ( v107 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 8LL))(v107);
    v108 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = v107;
    if ( v108 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
  }
  v109 = v142;
  if ( *((_QWORD *)this + 10) != v142 )
  {
    if ( v142 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 8LL))(v142);
    v110 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v109;
    if ( v110 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  }
  v111 = v151[0] == 0;
  v112 = v164;
  v113 = v157;
  *((_BYTE *)this + 102) = v149;
  *((_BYTE *)this + 112) = v150;
  *((_BYTE *)this + 101) = !v111;
  *((_QWORD *)this + 15) = v161;
  *((_OWORD *)this + 8) = v112;
  if ( v113 )
  {
    v157 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  }
  v114 = v156;
  if ( v156 )
  {
    v156 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v114)[2])(v114);
  }
  v115 = v155;
  if ( v155 )
  {
    v155 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
  }
  v116 = v154;
  if ( v154 )
  {
    v154 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v116)[2])(v116);
  }
  v117 = v153;
  if ( v153 )
  {
    v153 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
  }
  v118 = v152;
  if ( v152 )
  {
    v152 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v118)[2])(v118);
  }
  v119 = v148;
  if ( v148 )
  {
    v148 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
  }
  v120 = v147;
  if ( v147 )
  {
    v147 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v120)[2])(v120);
  }
  v121 = v146;
  if ( v146 )
  {
    v146 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
  }
  v122 = v145;
  if ( v145 )
  {
    v145 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v122)[2])(v122);
  }
  v123 = v142;
  if ( v142 )
  {
    v142 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
  }
  v124 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v144;
  if ( v144 )
  {
    v144 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v124)[2])(v124);
  }
  v125 = v141;
  if ( v141 )
  {
    v141 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
  }
  v126 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v143;
  if ( v143 )
  {
    v143 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v126)[2])(v126);
  }
  v127 = v140;
  if ( v140 )
  {
    v140 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
  }
  v128 = v139;
  if ( v139 )
  {
    v139 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v128)[2])(v128);
  }
  v129 = v138;
  if ( v138 )
  {
    v138 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
  }
  v130 = v137;
  if ( v137 )
  {
    v137 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v130)[2])(v130);
  }
  v131 = v136;
  if ( v136 )
  {
    v136 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
  }
  v132 = v135;
  if ( v135 )
  {
    v135 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v132)[2])(v132);
  }
  v133 = *(__int64 **)v134;
  if ( *(_QWORD *)v134 )
  {
    *(_QWORD *)v134 = 0;
    (*(void (__fastcall **)(__int64 *))(*v133 + 16))(v133);
  }
  return 0;
}

```

## disassembly

```asm
0x180017108  mov     [rsp-8+arg_10], rbx
0x18001710d  push    rbp
0x18001710e  push    rsi
0x18001710f  push    rdi
0x180017110  push    r12
0x180017112  push    r13
0x180017114  push    r14
0x180017116  push    r15
0x180017118  lea     rbp, [rsp-20h]
0x18001711d  sub     rsp, 120h
0x180017124  mov     rax, cs:__security_cookie
0x18001712b  xor     rax, rsp
0x18001712e  mov     [rbp+50h+var_38], rax
0x180017132  mov     rax, [rdx]
0x180017135  mov     rsi, rcx
0x180017138  xor     r12d, r12d
0x18001713b  lea     rcx, [rsp+150h+var_130]
0x180017140  mov     rdi, rdx
0x180017143  mov     qword ptr [rsp+150h+var_130], r12; int
0x180017148  mov     rbx, [rax]
0x18001714b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180017150  mov     r8, rax
0x180017153  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001715a  mov     rax, rbx
0x18001715d  mov     rcx, rdi
0x180017160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017165  mov     ebx, eax
0x180017167  test    eax, eax
0x180017169  jns     short loc_1800171A5
0x18001716b  mov     rcx, [rbp+58h]; this
0x18001716f  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017176  mov     r9d, eax; char *
0x180017179  mov     edx, 0C3h; void *
0x18001717e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017183  mov     rcx, qword ptr [rsp+150h+var_130]
0x180017188  test    rcx, rcx
0x18001718b  jz      short loc_18001719E
0x18001718d  mov     qword ptr [rsp+150h+var_130], r12
0x180017192  mov     rax, [rcx]
0x180017195  mov     rax, [rax+10h]
0x180017199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719e  mov     eax, ebx
0x1800171a0  jmp     loc_180017E98
0x1800171a5  mov     rbx, qword ptr [rsp+150h+var_130]
0x1800171aa  lea     r9, [rbp+50h+string]; string
0x1800171ae  mov     [rsp+150h+var_128], r12
0x1800171b3  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x1800171b7  mov     edx, 0Eh; length
0x1800171bc  lea     rcx, aActivationkind; "ActivationKind"
0x1800171c3  mov     rdi, [rbx]
0x1800171c6  mov     [rbp+50h+string], r12
0x1800171ca  call    cs:__imp_WindowsCreateStringReference
0x1800171d0  test    eax, eax
0x1800171d2  js      loc_180017EC7
0x1800171d8  mov     rdx, [rbp+50h+string]
0x1800171dc  lea     r8, [rsp+150h+var_128]
0x1800171e1  mov     rax, [rdi+30h]
0x1800171e5  mov     rcx, rbx
0x1800171e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ed  mov     ebx, eax
0x1800171ef  test    eax, eax
0x1800171f1  jns     short loc_18001722F
0x1800171f3  mov     rcx, [rbp+58h]; this
0x1800171f7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800171fe  mov     r9d, eax; char *
0x180017201  mov     edx, 0C7h; void *
0x180017206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001720b  mov     rcx, [rsp+150h+var_128]
0x180017210  test    rcx, rcx
0x180017213  jz      loc_180017183
0x180017219  mov     [rsp+150h+var_128], r12
0x18001721e  mov     rax, [rcx]
0x180017221  mov     rax, [rax+10h]
0x180017225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001722a  jmp     loc_180017183
0x18001722f  mov     rcx, [rsp+150h+var_128]
0x180017234  lea     r13, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001723b  mov     [rsp+150h+var_120], r12
0x180017240  lea     r8, [rsp+150h+var_120]
0x180017245  mov     rdx, r13
0x180017248  mov     rax, [rcx]
0x18001724b  mov     rax, [rax]
0x18001724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017253  mov     ebx, eax
0x180017255  test    eax, eax
0x180017257  jns     short loc_180017291
0x180017259  mov     edx, 0C9h; void *
0x18001725e  mov     rcx, [rbp+58h]; this
0x180017262  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017269  mov     r9d, ebx; char *
0x18001726c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017271  mov     rcx, [rsp+150h+var_120]
0x180017276  test    rcx, rcx
0x180017279  jz      short loc_18001720B
0x18001727b  mov     [rsp+150h+var_120], r12
0x180017280  mov     rax, [rcx]
0x180017283  mov     rax, [rax+10h]
0x180017287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001728c  jmp     loc_18001720B
0x180017291  mov     rcx, [rsp+150h+var_120]
0x180017296  lea     rdx, [rbp+50h+var_80]
0x18001729a  mov     [rbp+50h+var_80], r12d
0x18001729e  mov     rax, [rcx]
0x1800172a1  mov     rax, [rax+60h]
0x1800172a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172aa  mov     ebx, eax
0x1800172ac  test    eax, eax
0x1800172ae  jns     short loc_1800172B7
0x1800172b0  mov     edx, 0CBh
0x1800172b5  jmp     short loc_18001725E
0x1800172b7  mov     rbx, qword ptr [rsp+150h+var_130]
0x1800172bc  lea     r9, [rbp+50h+string]; string
0x1800172c0  mov     r15d, [rbp+50h+var_80]
0x1800172c4  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x1800172c8  mov     [rsp+150h+var_118], r12
0x1800172cd  lea     rcx, aPreviousexecut; "PreviousExecutionState"
0x1800172d4  mov     edx, 16h; length
0x1800172d9  mov     rdi, [rbx]
0x1800172dc  mov     [rbp+50h+string], r12
0x1800172e0  call    cs:__imp_WindowsCreateStringReference
0x1800172e6  test    eax, eax
0x1800172e8  js      loc_180017ECF
0x1800172ee  mov     rdx, [rbp+50h+string]
0x1800172f2  lea     r8, [rsp+150h+var_118]
0x1800172f7  mov     rax, [rdi+30h]
0x1800172fb  mov     rcx, rbx
0x1800172fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017303  mov     ebx, eax
0x180017305  test    eax, eax
0x180017307  jns     short loc_180017345
0x180017309  mov     rcx, [rbp+58h]; this
0x18001730d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017314  mov     r9d, eax; char *
0x180017317  mov     edx, 0D0h; void *
0x18001731c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017321  mov     rcx, [rsp+150h+var_118]
0x180017326  test    rcx, rcx
0x180017329  jz      loc_180017271
0x18001732f  mov     [rsp+150h+var_118], r12
0x180017334  mov     rax, [rcx]
0x180017337  mov     rax, [rax+10h]
0x18001733b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017340  jmp     loc_180017271
0x180017345  mov     rcx, [rsp+150h+var_118]
0x18001734a  lea     r8, [rsp+150h+var_110]
0x18001734f  mov     [rsp+150h+var_110], r12
0x180017354  mov     rdx, r13
0x180017357  mov     rax, [rcx]
0x18001735a  mov     rax, [rax]
0x18001735d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017362  mov     ebx, eax
0x180017364  test    eax, eax
0x180017366  jns     short loc_18001739D
0x180017368  mov     edx, 0D2h; void *
0x18001736d  mov     rcx, [rbp+58h]; this
0x180017371  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017378  mov     r9d, ebx; char *
0x18001737b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017380  mov     rcx, [rsp+150h+var_110]
0x180017385  test    rcx, rcx
0x180017388  jz      short loc_180017321
0x18001738a  mov     [rsp+150h+var_110], r12
0x18001738f  mov     rax, [rcx]
0x180017392  mov     rax, [rax+10h]
0x180017396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001739b  jmp     short loc_180017321
0x18001739d  mov     rcx, [rsp+150h+var_110]
0x1800173a2  lea     rdx, [rbp+50h+var_7C]
0x1800173a6  mov     [rbp+50h+var_7C], r12d
0x1800173aa  mov     rax, [rcx]
0x1800173ad  mov     rax, [rax+60h]
0x1800173b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173b6  mov     ebx, eax
0x1800173b8  test    eax, eax
0x1800173ba  jns     short loc_1800173C3
0x1800173bc  mov     edx, 0D4h
0x1800173c1  jmp     short loc_18001736D
0x1800173c3  mov     rbx, qword ptr [rsp+150h+var_130]
0x1800173c8  lea     r9, [rbp+50h+string]; string
0x1800173cc  mov     r14d, [rbp+50h+var_7C]
0x1800173d0  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x1800173d4  mov     [rbp+50h+var_78], r12
0x1800173d8  lea     rcx, aUsercontext; "UserContext"
0x1800173df  mov     [rsp+150h+var_108], r12
0x1800173e4  mov     edx, 0Bh; length
0x1800173e9  mov     rdi, [rbx]
0x1800173ec  mov     [rbp+50h+string], r12
0x1800173f0  call    cs:__imp_WindowsCreateStringReference
0x1800173f6  test    eax, eax
0x1800173f8  js      loc_180017ED7
0x1800173fe  mov     rdx, [rbp+50h+string]
0x180017402  lea     r8, [rsp+150h+var_108]
0x180017407  mov     rax, [rdi+30h]
0x18001740b  mov     rcx, rbx
0x18001740e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017413  mov     ebx, eax
0x180017415  test    eax, eax
0x180017417  jns     short loc_180017455
0x180017419  mov     rcx, [rbp+58h]; this
0x18001741d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017424  mov     r9d, eax; char *
0x180017427  mov     edx, 0D9h; void *
0x18001742c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017431  mov     rcx, [rsp+150h+var_108]
0x180017436  test    rcx, rcx
0x180017439  jz      loc_180017380
0x18001743f  mov     [rsp+150h+var_108], r12
0x180017444  mov     rax, [rcx]
0x180017447  mov     rax, [rax+10h]
0x18001744b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017450  jmp     loc_180017380
0x180017455  mov     rcx, [rsp+150h+var_108]
0x18001745a  lea     r8, [rsp+150h+var_100]
0x18001745f  mov     [rsp+150h+var_100], r12
0x180017464  mov     rdx, r13
0x180017467  mov     rax, [rcx]
0x18001746a  mov     rax, [rax]
0x18001746d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017472  mov     ebx, eax
0x180017474  test    eax, eax
0x180017476  jns     short loc_1800174AD
0x180017478  mov     edx, 0DBh; void *
0x18001747d  mov     rcx, [rbp+58h]; this
0x180017481  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017488  mov     r9d, ebx; char *
0x18001748b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017490  mov     rcx, [rsp+150h+var_100]
0x180017495  test    rcx, rcx
0x180017498  jz      short loc_180017431
0x18001749a  mov     [rsp+150h+var_100], r12
0x18001749f  mov     rax, [rcx]
0x1800174a2  mov     rax, [rax+10h]
0x1800174a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ab  jmp     short loc_180017431
0x1800174ad  mov     rcx, [rsp+150h+var_100]
0x1800174b2  lea     rdx, [rbp+50h+var_78]
0x1800174b6  mov     rax, [rcx]
0x1800174b9  mov     rax, [rax+70h]
0x1800174bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c2  mov     ebx, eax
0x1800174c4  test    eax, eax
0x1800174c6  jns     short loc_1800174CF
0x1800174c8  mov     edx, 0DCh
0x1800174cd  jmp     short loc_18001747D
0x1800174cf  mov     rbx, qword ptr [rsp+150h+var_130]
0x1800174d4  lea     r9, [rbp+50h+string]; string
0x1800174d8  mov     [rsp+150h+var_E8], r12
0x1800174dd  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x1800174e1  mov     [rsp+150h+var_F8], r12
0x1800174e6  lea     rcx, aSplashscreen; "SplashScreen"
0x1800174ed  mov     edx, 0Ch; length
0x1800174f2  mov     rdi, [rbx]
0x1800174f5  mov     [rbp+50h+string], r12
0x1800174f9  call    cs:__imp_WindowsCreateStringReference
0x1800174ff  test    eax, eax
0x180017501  js      loc_180017EDF
0x180017507  mov     rdx, [rbp+50h+string]
0x18001750b  lea     r8, [rsp+150h+var_E8]
0x180017510  mov     rax, [rdi+30h]
0x180017514  mov     rcx, rbx
0x180017517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001751c  test    eax, eax
0x18001751e  js      loc_1800175BE
0x180017524  mov     rbx, [rsp+150h+var_E8]
0x180017529  mov     rcx, [rsp+150h+var_F8]
0x18001752e  mov     rax, [rbx]
0x180017531  mov     rdi, [rax]
0x180017534  test    rcx, rcx
0x180017537  jz      short loc_18001754A
0x180017539  mov     [rsp+150h+var_F8], r12
0x18001753e  mov     rdx, [rcx]
0x180017541  mov     rax, [rdx+10h]
0x180017545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001754a  lea     r8, [rsp+150h+var_F8]
0x18001754f  mov     rcx, rbx
0x180017552  lea     rdx, _GUID_ca4d975c_d4d6_43f0_97c0_0833c6391c24
0x180017559  mov     rax, rdi
0x18001755c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017561  mov     ebx, eax
0x180017563  test    eax, eax
0x180017565  jns     short loc_1800175BE
0x180017567  mov     rcx, [rbp+58h]; this
0x18001756b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180017572  mov     r9d, eax; char *
0x180017575  mov     edx, 0E2h; void *
0x18001757a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001757f  mov     rcx, [rsp+150h+var_F8]
0x180017584  test    rcx, rcx
0x180017587  jz      short loc_18001759A
0x180017589  mov     [rsp+150h+var_F8], r12
0x18001758e  mov     rax, [rcx]
0x180017591  mov     rax, [rax+10h]
0x180017595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001759a  mov     rcx, [rsp+150h+var_E8]
0x18001759f  test    rcx, rcx
0x1800175a2  jz      loc_180017490
0x1800175a8  mov     [rsp+150h+var_E8], r12
0x1800175ad  mov     rax, [rcx]
0x1800175b0  mov     rax, [rax+10h]
0x1800175b4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
