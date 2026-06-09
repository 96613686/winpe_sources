# CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180016798`
- end: `0x180017100`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `2408`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016040`

## callees

- `0x180001dc0`
- `0x18000e284`
- `0x18000ed10`
- `0x180016004`
- `0x180016798`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016aee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016b4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016d14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016f41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016aee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016b4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016d14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016f41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016921`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017046`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016921`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017046`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800168c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800168c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800168a1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800168a1`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::MarshalObjectToPropertySet(
        RTL_SRWLOCK *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64))
{
  __int64 (__fastcall **v2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rax
  __int64 (__fastcall *v5)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rbx
  __int64 v6; // rax
  int ActivationFactory; // ebx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  _QWORD *v10; // rcx
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  RTL_SRWLOCK *v15; // rbx
  __int64 Ptr_low; // rdx
  int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 *v20; // rcx
  _QWORD *v21; // rcx
  _QWORD *v22; // rdi
  __int64 v23; // r15
  __int64 v24; // r14
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 Ptr_high; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // rdi
  __int64 v32; // r15
  __int64 v33; // r14
  HRESULT v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  PVOID Ptr; // rdx
  __int64 v38; // rdx
  __int64 v39; // rcx
  _QWORD *v40; // rdi
  __int64 v41; // r15
  __int64 v42; // r14
  HRESULT v43; // eax
  int v44; // edx
  unsigned int v45; // r8d
  __int64 v46; // rdx
  PVOID v47; // rdi
  _QWORD *v48; // r14
  __int64 v49; // r15
  HRESULT v50; // eax
  int v51; // edx
  unsigned int v52; // r8d
  PVOID v53; // rdi
  _QWORD *v54; // r14
  __int64 v55; // r15
  HRESULT v56; // eax
  int v57; // edx
  unsigned int v58; // r8d
  __int64 v59; // rdx
  __int64 v60; // rcx
  _QWORD *v61; // rdi
  __int64 v62; // r15
  __int64 v63; // r14
  HRESULT v64; // eax
  int v65; // edx
  unsigned int v66; // r8d
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rcx
  _QWORD *v70; // rdi
  __int64 v71; // r15
  __int64 v72; // r14
  HRESULT v73; // eax
  int v74; // edx
  unsigned int v75; // r8d
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rcx
  _QWORD *v79; // rdi
  __int64 v80; // r15
  __int64 v81; // r14
  HRESULT v82; // eax
  int v83; // edx
  unsigned int v84; // r8d
  PVOID v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rcx
  _QWORD *v88; // rdi
  __int64 v89; // r15
  __int64 v90; // r14
  HRESULT v91; // eax
  int v92; // edx
  unsigned int v93; // r8d
  __int128 v94; // xmm0
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rcx
  _QWORD *v98; // rdi
  __int64 v99; // r14
  __int64 v100; // rsi
  HRESULT v101; // eax
  int v102; // edx
  unsigned int v103; // r8d
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rcx
  __int64 v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int64 *v112; // rcx
  _QWORD *v113; // rcx
  int v114; // [rsp+20h] [rbp-69h]
  _BYTE v115[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v116; // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v117; // [rsp+40h] [rbp-49h] BYREF
  __int64 v118; // [rsp+48h] [rbp-41h] BYREF
  __int64 v119; // [rsp+50h] [rbp-39h] BYREF
  __int64 v120; // [rsp+58h] [rbp-31h] BYREF
  __int64 v121; // [rsp+60h] [rbp-29h] BYREF
  __int64 v122; // [rsp+68h] [rbp-21h] BYREF
  __int64 v123; // [rsp+70h] [rbp-19h] BYREF
  __int64 v124; // [rsp+78h] [rbp-11h] BYREF
  __int64 v125; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = *a2;
  v117 = 0;
  v116 = 0;
  v5 = *v2;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(&v117);
  ActivationFactory = v5(
                        (struct Windows::Foundation::Collections::IPropertySet *)a2,
                        &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                        v6);
  if ( ActivationFactory < 0 )
  {
    v8 = 53;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v114);
    v9 = v116;
    if ( v116 )
    {
      v116 = 0;
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
    }
    v10 = v117;
    if ( v117 )
    {
      v117 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    }
    return (unsigned int)ActivationFactory;
  }
  string = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v116);
  if ( ActivationFactory < 0 )
  {
    v8 = 54;
    goto LABEL_3;
  }
  v15 = this + 18;
  AcquireSRWLockShared(this + 18);
  Ptr_low = LODWORD(this[9].Ptr);
  v118 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v116 + 88))(v116, Ptr_low, &v118);
  if ( v17 < 0 )
  {
    v18 = 60;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_14:
    v19 = v118;
    if ( v118 )
    {
      v118 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( v15 )
      ReleaseSRWLockShared(v15);
    v20 = v116;
    if ( v116 )
    {
      v116 = 0;
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    }
    v21 = v117;
    if ( v117 )
    {
      v117 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    return (unsigned int)v17;
  }
  v22 = v117;
  v23 = v118;
  v115[0] = 0;
  v24 = *v117;
  string = 0;
  v25 = WindowsCreateStringReference(L"ActivationKind", 0xEu, &hstringHeader, &string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v24 + 80))(v22, string, v23, v115);
  if ( v17 < 0 )
  {
    v18 = 62;
    goto LABEL_13;
  }
  Ptr_high = HIDWORD(this[9].Ptr);
  v119 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v116 + 88))(v116, Ptr_high, &v119);
  if ( v17 < 0 )
  {
    v29 = 66;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_29:
    v30 = v119;
    if ( v119 )
    {
      v119 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_14;
  }
  v31 = v117;
  v32 = v119;
  v33 = *v117;
  string = 0;
  v34 = WindowsCreateStringReference(L"PreviousExecutionState", 0x16u, &hstringHeader, &string);
  if ( v34 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v33 + 80))(v31, string, v32, v115);
  if ( v17 < 0 )
  {
    v29 = 67;
    goto LABEL_28;
  }
  Ptr = this[13].Ptr;
  v120 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, PVOID, __int64 *))(*v116 + 104))(v116, Ptr, &v120);
  if ( v17 < 0 )
  {
    v38 = 70;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_37:
    v39 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    goto LABEL_29;
  }
  v40 = v117;
  v41 = v120;
  v42 = *v117;
  string = 0;
  v43 = WindowsCreateStringReference(L"UserContext", 0xBu, &hstringHeader, &string);
  if ( v43 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v43, v44, v45);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v42 + 80))(v40, string, v41, v115);
  if ( v17 < 0 )
  {
    v38 = 71;
    goto LABEL_36;
  }
  v47 = this[11].Ptr;
  if ( v47 )
  {
    v48 = v117;
    v49 = *v117;
    string = 0;
    v50 = WindowsCreateStringReference(L"SplashScreen", 0xCu, &hstringHeader, &string);
    if ( v50 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v50, v51, v52);
      __debugbreak();
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, PVOID, _BYTE *))(v49 + 80))(v48, string, v47, v115);
    if ( v17 < 0 )
    {
      v38 = 75;
      goto LABEL_36;
    }
  }
  v53 = this[10].Ptr;
  if ( v53 )
  {
    v54 = v117;
    v55 = *v117;
    string = 0;
    v56 = WindowsCreateStringReference(L"ActivationValueSetReference", 0x1Bu, &hstringHeader, &string);
    if ( v56 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v56, v57, v58);
      __debugbreak();
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, PVOID, _BYTE *))(v55 + 80))(v54, string, v53, v115);
    if ( v17 < 0 )
    {
      v38 = 80;
      goto LABEL_36;
    }
  }
  LOBYTE(v46) = BYTE6(this[12].Ptr);
  v121 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v116 + 136))(v116, v46, &v121);
  if ( v17 < 0 )
  {
    v59 = 84;
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v59,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_53:
    v60 = v121;
    if ( v121 )
    {
      v121 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    goto LABEL_37;
  }
  v61 = v117;
  v62 = v121;
  v63 = *v117;
  string = 0;
  v64 = WindowsCreateStringReference(L"IsForeground", 0xCu, &hstringHeader, &string);
  if ( v64 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v64, v65, v66);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v63 + 80))(v61, string, v62, v115);
  if ( v17 < 0 )
  {
    v59 = 85;
    goto LABEL_52;
  }
  LOBYTE(v67) = this[14].Ptr;
  v122 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v116 + 136))(v116, v67, &v122);
  if ( v17 < 0 )
  {
    v68 = 88;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v68,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_61:
    v69 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    goto LABEL_53;
  }
  v70 = v117;
  v71 = v122;
  v72 = *v117;
  string = 0;
  v73 = WindowsCreateStringReference(L"IsHolographic", 0xDu, &hstringHeader, &string);
  if ( v73 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v73, v74, v75);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v72 + 80))(v70, string, v71, v115);
  if ( v17 < 0 )
  {
    v68 = 89;
    goto LABEL_60;
  }
  LOBYTE(v76) = BYTE5(this[12].Ptr);
  v123 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v116 + 136))(v116, v76, &v123);
  if ( v17 < 0 )
  {
    v77 = 92;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v77,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_69:
    v78 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    }
    goto LABEL_61;
  }
  v79 = v117;
  v80 = v123;
  v81 = *v117;
  string = 0;
  v82 = WindowsCreateStringReference(L"IsInitialized", 0xDu, &hstringHeader, &string);
  if ( v82 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v82, v83, v84);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v81 + 80))(v79, string, v80, v115);
  if ( v17 < 0 )
  {
    v77 = 93;
    goto LABEL_68;
  }
  v85 = this[15].Ptr;
  v124 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, PVOID, __int64 *))(*v116 + 104))(v116, v85, &v124);
  if ( v17 < 0 )
  {
    v86 = 96;
LABEL_76:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v86,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
LABEL_77:
    v87 = v124;
    if ( v124 )
    {
      v124 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    }
    goto LABEL_69;
  }
  v88 = v117;
  v89 = v124;
  v90 = *v117;
  string = 0;
  v91 = WindowsCreateStringReference(L"AamActivationId", 0xFu, &hstringHeader, &string);
  if ( v91 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v91, v92, v93);
    JUMPOUT(0x1800170FFLL);
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v90 + 80))(v88, string, v89, v115);
  if ( v17 < 0 )
  {
    v86 = 97;
    goto LABEL_76;
  }
  v94 = *(_OWORD *)&this[16].Ptr;
  v125 = 0;
  v95 = *v116;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v94;
  v17 = (*(__int64 (__fastcall **)(__int64 *, HSTRING_HEADER *, __int64 *))(v95 + 160))(v116, &hstringHeader, &v125);
  if ( v17 < 0 )
  {
    v96 = 100;
    goto LABEL_84;
  }
  v98 = v117;
  v99 = v125;
  v100 = *v117;
  string = 0;
  v101 = WindowsCreateStringReference(L"AamActivityId", 0xDu, &hstringHeader, &string);
  if ( v101 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v101, v102, v103);
    __debugbreak();
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v100 + 80))(v98, string, v99, v115);
  if ( v17 < 0 )
  {
    v96 = 101;
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v96,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v114);
    v97 = v125;
    if ( v125 )
    {
      v125 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    }
    goto LABEL_77;
  }
  v104 = v125;
  if ( v125 )
  {
    v125 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  }
  v105 = v124;
  if ( v124 )
  {
    v124 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
  }
  v106 = v123;
  if ( v123 )
  {
    v123 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
  }
  v107 = v122;
  if ( v122 )
  {
    v122 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
  }
  v108 = v121;
  if ( v121 )
  {
    v121 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
  }
  v109 = v120;
  if ( v120 )
  {
    v120 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  }
  v110 = v119;
  if ( v119 )
  {
    v119 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  }
  v111 = v118;
  if ( v118 )
  {
    v118 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
  }
  if ( v15 )
    ReleaseSRWLockShared(v15);
  v112 = v116;
  if ( v116 )
  {
    v116 = 0;
    (*(void (__fastcall **)(__int64 *))(*v112 + 16))(v112);
  }
  v113 = v117;
  if ( v117 )
  {
    v117 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v113 + 16LL))(v113);
  }
  return 0;
}

```

## disassembly

```asm
0x180016798  mov     [rsp-8+arg_10], rbx
0x18001679d  mov     [rsp-8+arg_18], rsi
0x1800167a2  push    rbp
0x1800167a3  push    rdi
0x1800167a4  push    r12
0x1800167a6  push    r14
0x1800167a8  push    r15
0x1800167aa  lea     rbp, [rsp-37h]
0x1800167af  sub     rsp, 0C0h
0x1800167b6  mov     rax, cs:__security_cookie
0x1800167bd  xor     rax, rsp
0x1800167c0  mov     [rbp+57h+var_30], rax
0x1800167c4  mov     rax, [rdx]
0x1800167c7  mov     rsi, rcx
0x1800167ca  xor     r12d, r12d
0x1800167cd  lea     rcx, [rbp+57h+var_A0]
0x1800167d1  mov     rdi, rdx
0x1800167d4  mov     [rbp+57h+var_A0], r12
0x1800167d8  mov     [rbp+57h+var_A8], r12
0x1800167dc  mov     rbx, [rax]
0x1800167df  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800167e4  mov     r8, rax
0x1800167e7  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800167ee  mov     rax, rbx
0x1800167f1  mov     rcx, rdi
0x1800167f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f9  mov     ebx, eax
0x1800167fb  test    eax, eax
0x1800167fd  jns     short loc_180016850
0x1800167ff  lea     edx, [r12+35h]; void *
0x180016804  mov     rcx, [rbp+5Fh]; this
0x180016808  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18001680f  mov     r9d, ebx; char *
0x180016812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016817  mov     rcx, [rbp+57h+var_A8]
0x18001681b  test    rcx, rcx
0x18001681e  jz      short loc_180016830
0x180016820  mov     [rbp+57h+var_A8], r12
0x180016824  mov     rax, [rcx]
0x180016827  mov     rax, [rax+10h]
0x18001682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016830  mov     rcx, [rbp+57h+var_A0]
0x180016834  test    rcx, rcx
0x180016837  jz      short loc_180016849
0x180016839  mov     [rbp+57h+var_A0], r12
0x18001683d  mov     rax, [rcx]
0x180016840  mov     rax, [rax+10h]
0x180016844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016849  mov     eax, ebx
0x18001684b  jmp     loc_180017080
0x180016850  lea     r9, [rbp+57h+string]; string
0x180016854  mov     [rbp+57h+string], r12
0x180016858  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001685c  mov     edx, 20h ; ' '; length
0x180016861  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180016868  call    cs:__imp_WindowsCreateStringReference
0x18001686e  test    eax, eax
0x180016870  js      loc_1800170B0
0x180016876  mov     rcx, [rbp+57h+var_A8]
0x18001687a  mov     rbx, [rbp+57h+string]
0x18001687e  test    rcx, rcx
0x180016881  jz      short loc_180016893
0x180016883  mov     [rbp+57h+var_A8], r12
0x180016887  mov     rax, [rcx]
0x18001688a  mov     rax, [rax+10h]
0x18001688e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016893  lea     r8, [rbp+57h+var_A8]
0x180016897  mov     rcx, rbx
0x18001689a  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800168a1  call    cs:__imp_RoGetActivationFactory
0x1800168a7  mov     ebx, eax
0x1800168a9  test    eax, eax
0x1800168ab  jns     short loc_1800168B7
0x1800168ad  mov     edx, 36h ; '6'
0x1800168b2  jmp     loc_180016804
0x1800168b7  lea     rbx, [rsi+90h]
0x1800168be  mov     rcx, rbx; SRWLock
0x1800168c1  call    cs:__imp_AcquireSRWLockShared
0x1800168c7  mov     rcx, [rbp+57h+var_A8]
0x1800168cb  lea     r8, [rbp+57h+var_98]
0x1800168cf  mov     edx, [rsi+48h]
0x1800168d2  mov     [rbp+57h+var_98], r12
0x1800168d6  mov     rax, [rcx]
0x1800168d9  mov     rax, [rax+58h]
0x1800168dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e2  mov     edi, eax
0x1800168e4  test    eax, eax
0x1800168e6  jns     short loc_180016960
0x1800168e8  mov     edx, 3Ch ; '<'; void *
0x1800168ed  mov     rcx, [rbp+5Fh]; this
0x1800168f1  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800168f8  mov     r9d, edi; char *
0x1800168fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016900  mov     rcx, [rbp+57h+var_98]
0x180016904  test    rcx, rcx
0x180016907  jz      short loc_180016919
0x180016909  mov     [rbp+57h+var_98], r12
0x18001690d  mov     rax, [rcx]
0x180016910  mov     rax, [rax+10h]
0x180016914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016919  test    rbx, rbx
0x18001691c  jz      short loc_180016927
0x18001691e  mov     rcx, rbx; SRWLock
0x180016921  call    cs:__imp_ReleaseSRWLockShared
0x180016927  mov     rcx, [rbp+57h+var_A8]
0x18001692b  test    rcx, rcx
0x18001692e  jz      short loc_180016940
0x180016930  mov     [rbp+57h+var_A8], r12
0x180016934  mov     rax, [rcx]
0x180016937  mov     rax, [rax+10h]
0x18001693b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016940  mov     rcx, [rbp+57h+var_A0]
0x180016944  test    rcx, rcx
0x180016947  jz      short loc_180016959
0x180016949  mov     [rbp+57h+var_A0], r12
0x18001694d  mov     rax, [rcx]
0x180016950  mov     rax, [rax+10h]
0x180016954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016959  mov     eax, edi
0x18001695b  jmp     loc_180017080
0x180016960  mov     rdi, [rbp+57h+var_A0]
0x180016964  lea     r9, [rbp+57h+string]; string
0x180016968  mov     r15, [rbp+57h+var_98]
0x18001696c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016970  mov     [rbp+57h+var_B0], r12b
0x180016974  lea     rcx, aActivationkind; "ActivationKind"
0x18001697b  mov     edx, 0Eh; length
0x180016980  mov     r14, [rdi]
0x180016983  mov     [rbp+57h+string], r12
0x180016987  call    cs:__imp_WindowsCreateStringReference
0x18001698d  test    eax, eax
0x18001698f  js      loc_1800170B8
0x180016995  mov     rdx, [rbp+57h+string]
0x180016999  lea     r9, [rbp+57h+var_B0]
0x18001699d  mov     rax, [r14+50h]
0x1800169a1  mov     r8, r15
0x1800169a4  mov     rcx, rdi
0x1800169a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ac  mov     edi, eax
0x1800169ae  test    eax, eax
0x1800169b0  jns     short loc_1800169BC
0x1800169b2  mov     edx, 3Eh ; '>'
0x1800169b7  jmp     loc_1800168ED
0x1800169bc  mov     rcx, [rbp+57h+var_A8]
0x1800169c0  lea     r8, [rbp+57h+var_90]
0x1800169c4  mov     edx, [rsi+4Ch]
0x1800169c7  mov     [rbp+57h+var_90], r12
0x1800169cb  mov     rax, [rcx]
0x1800169ce  mov     rax, [rax+58h]
0x1800169d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d7  mov     edi, eax
0x1800169d9  test    eax, eax
0x1800169db  jns     short loc_180016A17
0x1800169dd  mov     edx, 42h ; 'B'; void *
0x1800169e2  mov     rcx, [rbp+5Fh]; this
0x1800169e6  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800169ed  mov     r9d, edi; char *
0x1800169f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800169f5  mov     rcx, [rbp+57h+var_90]
0x1800169f9  test    rcx, rcx
0x1800169fc  jz      loc_180016900
0x180016a02  mov     [rbp+57h+var_90], r12
0x180016a06  mov     rax, [rcx]
0x180016a09  mov     rax, [rax+10h]
0x180016a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a12  jmp     loc_180016900
0x180016a17  mov     rdi, [rbp+57h+var_A0]
0x180016a1b  lea     r9, [rbp+57h+string]; string
0x180016a1f  mov     r15, [rbp+57h+var_90]
0x180016a23  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016a27  mov     edx, 16h; length
0x180016a2c  lea     rcx, aPreviousexecut; "PreviousExecutionState"
0x180016a33  mov     r14, [rdi]
0x180016a36  mov     [rbp+57h+string], r12
0x180016a3a  call    cs:__imp_WindowsCreateStringReference
0x180016a40  test    eax, eax
0x180016a42  js      loc_1800170C0
0x180016a48  mov     rdx, [rbp+57h+string]
0x180016a4c  lea     r9, [rbp+57h+var_B0]
0x180016a50  mov     rax, [r14+50h]
0x180016a54  mov     r8, r15
0x180016a57  mov     rcx, rdi
0x180016a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a5f  mov     edi, eax
0x180016a61  test    eax, eax
0x180016a63  jns     short loc_180016A6F
0x180016a65  mov     edx, 43h ; 'C'
0x180016a6a  jmp     loc_1800169E2
0x180016a6f  mov     rcx, [rbp+57h+var_A8]
0x180016a73  lea     r8, [rbp+57h+var_88]
0x180016a77  mov     rdx, [rsi+68h]
0x180016a7b  mov     [rbp+57h+var_88], r12
0x180016a7f  mov     rax, [rcx]
0x180016a82  mov     rax, [rax+68h]
0x180016a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a8b  mov     edi, eax
0x180016a8d  test    eax, eax
0x180016a8f  jns     short loc_180016ACB
0x180016a91  mov     edx, 46h ; 'F'; void *
0x180016a96  mov     rcx, [rbp+5Fh]; this
0x180016a9a  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180016aa1  mov     r9d, edi; char *
0x180016aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016aa9  mov     rcx, [rbp+57h+var_88]
0x180016aad  test    rcx, rcx
0x180016ab0  jz      loc_1800169F5
0x180016ab6  mov     [rbp+57h+var_88], r12
0x180016aba  mov     rax, [rcx]
0x180016abd  mov     rax, [rax+10h]
0x180016ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ac6  jmp     loc_1800169F5
0x180016acb  mov     rdi, [rbp+57h+var_A0]
0x180016acf  lea     r9, [rbp+57h+string]; string
0x180016ad3  mov     r15, [rbp+57h+var_88]
0x180016ad7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016adb  mov     edx, 0Bh; length
0x180016ae0  lea     rcx, aUsercontext; "UserContext"
0x180016ae7  mov     r14, [rdi]
0x180016aea  mov     [rbp+57h+string], r12
0x180016aee  call    cs:__imp_WindowsCreateStringReference
0x180016af4  test    eax, eax
0x180016af6  js      loc_1800170C8
0x180016afc  mov     rdx, [rbp+57h+string]
0x180016b00  lea     r9, [rbp+57h+var_B0]
0x180016b04  mov     rax, [r14+50h]
0x180016b08  mov     r8, r15
0x180016b0b  mov     rcx, rdi
0x180016b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b13  mov     edi, eax
0x180016b15  test    eax, eax
0x180016b17  jns     short loc_180016B23
0x180016b19  mov     edx, 47h ; 'G'
0x180016b1e  jmp     loc_180016A96
0x180016b23  mov     rdi, [rsi+58h]
0x180016b27  test    rdi, rdi
0x180016b2a  jz      short loc_180016B80
0x180016b2c  mov     r14, [rbp+57h+var_A0]
0x180016b30  lea     r9, [rbp+57h+string]; string
0x180016b34  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016b38  mov     edx, 0Ch; length
0x180016b3d  lea     rcx, aSplashscreen; "SplashScreen"
0x180016b44  mov     r15, [r14]
0x180016b47  mov     [rbp+57h+string], r12
0x180016b4b  call    cs:__imp_WindowsCreateStringReference
0x180016b51  test    eax, eax
0x180016b53  js      loc_1800170D0
0x180016b59  mov     rdx, [rbp+57h+string]
0x180016b5d  lea     r9, [rbp+57h+var_B0]
0x180016b61  mov     rax, [r15+50h]
0x180016b65  mov     r8, rdi
0x180016b68  mov     rcx, r14
0x180016b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b70  mov     edi, eax
0x180016b72  test    eax, eax
0x180016b74  jns     short loc_180016B80
0x180016b76  mov     edx, 4Bh ; 'K'
0x180016b7b  jmp     loc_180016A96
0x180016b80  mov     rdi, [rsi+50h]
0x180016b84  test    rdi, rdi
0x180016b87  jz      short loc_180016BDD
0x180016b89  mov     r14, [rbp+57h+var_A0]
0x180016b8d  lea     r9, [rbp+57h+string]; string
0x180016b91  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016b95  mov     edx, 1Bh; length
0x180016b9a  lea     rcx, aActivationvalu; "ActivationValueSetReference"
0x180016ba1  mov     r15, [r14]
0x180016ba4  mov     [rbp+57h+string], r12
0x180016ba8  call    cs:__imp_WindowsCreateStringReference
0x180016bae  test    eax, eax
0x180016bb0  js      loc_1800170D8
0x180016bb6  mov     rdx, [rbp+57h+string]
0x180016bba  lea     r9, [rbp+57h+var_B0]
0x180016bbe  mov     rax, [r15+50h]
0x180016bc2  mov     r8, rdi
0x180016bc5  mov     rcx, r14
0x180016bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bcd  mov     edi, eax
0x180016bcf  test    eax, eax
0x180016bd1  jns     short loc_180016BDD
0x180016bd3  mov     edx, 50h ; 'P'
0x180016bd8  jmp     loc_180016A96
0x180016bdd  mov     rcx, [rbp+57h+var_A8]
0x180016be1  lea     r8, [rbp+57h+var_80]
0x180016be5  mov     dl, [rsi+66h]
0x180016be8  mov     [rbp+57h+var_80], r12
0x180016bec  mov     rax, [rcx]
0x180016bef  mov     rax, [rax+88h]
0x180016bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bfb  mov     edi, eax
0x180016bfd  test    eax, eax
0x180016bff  jns     short loc_180016C3B
0x180016c01  mov     edx, 54h ; 'T'; void *
0x180016c06  mov     rcx, [rbp+5Fh]; this
0x180016c0a  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180016c11  mov     r9d, edi; char *
0x180016c14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c19  mov     rcx, [rbp+57h+var_80]
0x180016c1d  test    rcx, rcx
0x180016c20  jz      loc_180016AA9
0x180016c26  mov     [rbp+57h+var_80], r12
  ... truncated ...
```
