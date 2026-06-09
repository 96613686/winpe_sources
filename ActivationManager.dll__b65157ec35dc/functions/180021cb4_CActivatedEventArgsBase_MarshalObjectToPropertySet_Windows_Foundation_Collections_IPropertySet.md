# CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180021cb4`
- end: `0x1800228fe`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `3146`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800217f8`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180021cb4`
- `0x180031540`
- `0x18003b4a0`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021e9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022266`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002259c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021e9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022266`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002259c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021da6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021da6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021d51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021e51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021f51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002205c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800222ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800223dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022521`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021d51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021e51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021f51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002205c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800222ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800223dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021d3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800223c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002250b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021d3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800223c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002250b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021d73`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021d73`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CActivatedEventArgsBase::MarshalObjectToPropertySet(
        RTL_SRWLOCK *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **))
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  HSTRING v9; // rbx
  unsigned int Ptr; // edi
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  int v13; // eax
  __int64 *v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rsi
  HRESULT v17; // eax
  int v18; // eax
  unsigned int Ptr_high; // edi
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  __int64 *v23; // rbx
  __int64 v24; // rdi
  __int64 v25; // rsi
  HRESULT v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, PVOID, __int64 *); // rbx
  int v30; // eax
  __int64 *v31; // rbx
  __int64 v32; // rdi
  __int64 v33; // rsi
  HRESULT v34; // eax
  int v35; // eax
  PVOID v36; // rsi
  __int64 *v37; // rdi
  __int64 (__fastcall *v38)(__int64 *, HSTRING, PVOID, _BYTE *); // rbx
  int v39; // eax
  PVOID v40; // rsi
  __int64 *v41; // rdi
  __int64 (__fastcall *v42)(__int64 *, HSTRING, PVOID, _BYTE *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, __int64, __int64 *); // rbx
  __int64 v46; // rdx
  int v47; // eax
  __int64 *v48; // rbx
  __int64 v49; // rdi
  __int64 v50; // rsi
  HRESULT v51; // eax
  int v52; // eax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, __int64, __int64 *); // rbx
  __int64 v55; // rdx
  int v56; // eax
  __int64 *v57; // rbx
  __int64 v58; // rdi
  __int64 v59; // rsi
  HRESULT v60; // eax
  int v61; // eax
  __int64 v62; // rdi
  __int64 (__fastcall *v63)(__int64, __int64, __int64 *); // rbx
  __int64 v64; // rdx
  int v65; // eax
  __int64 *v66; // rbx
  __int64 v67; // rdi
  __int64 v68; // rsi
  HRESULT v69; // eax
  int v70; // eax
  __int64 v71; // rdi
  __int64 (__fastcall *v72)(__int64, PVOID, __int64 *); // rbx
  int v73; // eax
  __int64 *v74; // rsi
  __int64 (__fastcall *v75)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v76; // rbx
  int v77; // eax
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, HSTRING_HEADER *, __int64 *); // rbx
  int v80; // eax
  __int64 *v81; // rsi
  __int64 (__fastcall *v82)(__int64 *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v83; // rbx
  int v84; // eax
  int v86; // [rsp+20h] [rbp-69h]
  _BYTE v87[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v88; // [rsp+38h] [rbp-51h] BYREF
  __int64 v89; // [rsp+40h] [rbp-49h] BYREF
  __int64 v90; // [rsp+48h] [rbp-41h] BYREF
  RTL_SRWLOCK *v91; // [rsp+50h] [rbp-39h] BYREF
  __int64 v92; // [rsp+58h] [rbp-31h] BYREF
  __int64 *v93; // [rsp+60h] [rbp-29h] BYREF
  __int64 v94; // [rsp+68h] [rbp-21h] BYREF
  __int64 v95; // [rsp+70h] [rbp-19h] BYREF
  __int64 v96; // [rsp+78h] [rbp-11h] BYREF
  __int64 v97; // [rsp+80h] [rbp-9h] BYREF
  __int64 v98; // [rsp+88h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v93 = 0;
  v95 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v93);
  ActivationFactory = v4(
                        (struct Windows::Foundation::Collections::IPropertySet *)a2,
                        &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                        &v93);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 53;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v86);
LABEL_64:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v93);
    return v6;
  }
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v9 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v95);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 54;
    goto LABEL_7;
  }
  AcquireSRWLockShared(this + 18);
  v91 = this + 18;
  v88 = 0;
  Ptr = (unsigned int)this[9].Ptr;
  v11 = v95;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v95 + 88LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
  v13 = v12(v11, Ptr, &v88);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v13,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v87[0] = 0;
  v14 = v93;
  v15 = *v93;
  v16 = v88;
  string = 0;
  v17 = WindowsCreateStringReference(L"ActivationKind", 0xEu, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    RaiseException(v17, 1u, 0, 0);
    __debugbreak();
  }
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v15 + 80))(v14, string, v16, v87);
  v6 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v18,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    if ( this != (RTL_SRWLOCK *)-144LL )
      ReleaseSRWLockShared(this + 18);
    goto LABEL_64;
  }
  v89 = 0;
  Ptr_high = HIDWORD(this[9].Ptr);
  v20 = v95;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v95 + 88LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
  v22 = v21(v20, Ptr_high, &v89);
  v6 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v22,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v23 = v93;
  v24 = *v93;
  v25 = v89;
  string = 0;
  v26 = WindowsCreateStringReference(L"PreviousExecutionState", 0x16u, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    RaiseException(v26, 1u, 0, 0);
    __debugbreak();
  }
  v27 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v24 + 80))(v23, string, v25, v87);
  v6 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v27,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v90 = 0;
  v28 = v95;
  v29 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v95 + 104LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
  v30 = v29(v28, this[13].Ptr, &v90);
  v6 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v30,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v31 = v93;
  v32 = *v93;
  v33 = v90;
  string = 0;
  v34 = WindowsCreateStringReference(L"UserContext", 0xBu, &hstringHeader, &string);
  if ( v34 < 0 )
  {
    RaiseException(v34, 1u, 0, 0);
    __debugbreak();
  }
  v35 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v32 + 80))(v31, string, v33, v87);
  v6 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v35,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v36 = this[11].Ptr;
  if ( v36 )
  {
    v37 = v93;
    v38 = *(__int64 (__fastcall **)(__int64 *, HSTRING, PVOID, _BYTE *))(*v93 + 80);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SplashScreen", 0xDu, 0xCu);
    v39 = v38(v37, string, v36, v87);
    v6 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v39,
        v86);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
      CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
      goto LABEL_64;
    }
  }
  v40 = this[10].Ptr;
  if ( v40 )
  {
    v41 = v93;
    v42 = *(__int64 (__fastcall **)(__int64 *, HSTRING, PVOID, _BYTE *))(*v93 + 80);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"ActivationValueSetReference",
      0x1Cu,
      0x1Bu);
    v43 = v42(v41, string, v40, v87);
    v6 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v43,
        v86);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
      CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
      goto LABEL_64;
    }
  }
  v92 = 0;
  v44 = v95;
  v45 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v95 + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
  LOBYTE(v46) = BYTE6(this[12].Ptr);
  v47 = v45(v44, v46, &v92);
  v6 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v47,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    if ( this != (RTL_SRWLOCK *)-144LL )
      ReleaseSRWLockShared(this + 18);
    goto LABEL_64;
  }
  v48 = v93;
  v49 = *v93;
  v50 = v92;
  string = 0;
  v51 = WindowsCreateStringReference(L"IsForeground", 0xCu, &hstringHeader, &string);
  if ( v51 < 0 )
  {
    RaiseException(v51, 1u, 0, 0);
    __debugbreak();
  }
  v52 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v49 + 80))(v48, string, v50, v87);
  v6 = v52;
  if ( v52 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v52,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v94 = 0;
  v53 = v95;
  v54 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v95 + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
  LOBYTE(v55) = this[14].Ptr;
  v56 = v54(v53, v55, &v94);
  v6 = v56;
  if ( v56 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v56,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v57 = v93;
  v58 = *v93;
  v59 = v94;
  string = 0;
  v60 = WindowsCreateStringReference(L"IsHolographic", 0xDu, &hstringHeader, &string);
  if ( v60 < 0 )
  {
    RaiseException(v60, 1u, 0, 0);
    __debugbreak();
  }
  v61 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v58 + 80))(v57, string, v59, v87);
  v6 = v61;
  if ( v61 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v61,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v96 = 0;
  v62 = v95;
  v63 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v95 + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
  LOBYTE(v64) = BYTE5(this[12].Ptr);
  v65 = v63(v62, v64, &v96);
  v6 = v65;
  if ( v65 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v65,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v66 = v93;
  v67 = *v93;
  v68 = v96;
  string = 0;
  v69 = WindowsCreateStringReference(L"IsInitialized", 0xDu, &hstringHeader, &string);
  if ( v69 < 0 )
  {
    RaiseException(v69, 1u, 0, 0);
    __debugbreak();
  }
  v70 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(v67 + 80))(v66, string, v68, v87);
  v6 = v70;
  if ( v70 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v70,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    if ( this != (RTL_SRWLOCK *)-144LL )
      ReleaseSRWLockShared(this + 18);
    goto LABEL_64;
  }
  v97 = 0;
  v71 = v95;
  v72 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v95 + 104LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
  v73 = v72(v71, this[15].Ptr, &v97);
  v6 = v73;
  if ( v73 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v73,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v74 = v93;
  v75 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v93 + 80);
  v76 = v97;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivationId", 0x10u, 0xFu);
  v77 = v75(v74, string, v76, v87);
  v6 = v77;
  if ( v77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v77,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v98 = 0;
  v78 = v95;
  v79 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v95 + 160LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&this[16].Ptr;
  v80 = v79(v78, &hstringHeader, &v98);
  v6 = v80;
  if ( v80 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v80,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  v81 = v93;
  v82 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v93 + 80);
  v83 = v98;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivityId", 0xEu, 0xDu);
  v84 = v82(v81, string, v83, v87);
  v6 = v84;
  if ( v84 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v84,
      v86);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
    CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
    goto LABEL_64;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v94);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v90);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
  CAutoSRWSharedLock::~CAutoSRWSharedLock((CAutoSRWSharedLock *)&v91);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v93);
  return 0;
}

```

## disassembly

```asm
0x180021cb4  mov     [rsp-8+arg_10], rbx
0x180021cb9  mov     [rsp-8+arg_18], rsi
0x180021cbe  push    rbp
0x180021cbf  push    rdi
0x180021cc0  push    r12
0x180021cc2  push    r14
0x180021cc4  push    r15
0x180021cc6  lea     rbp, [rsp-37h]
0x180021ccb  sub     rsp, 0C0h
0x180021cd2  mov     rax, cs:__security_cookie
0x180021cd9  xor     rax, rsp
0x180021cdc  mov     [rbp+57h+var_30], rax
0x180021ce0  mov     rdi, rdx
0x180021ce3  mov     r15, rcx
0x180021ce6  xor     r12d, r12d
0x180021ce9  mov     [rbp+57h+var_80], r12
0x180021ced  mov     [rbp+57h+var_70], r12
0x180021cf1  mov     rax, [rdx]
0x180021cf4  mov     rbx, [rax]
0x180021cf7  lea     rcx, [rbp+57h+var_80]
0x180021cfb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021d00  lea     r8, [rbp+57h+var_80]
0x180021d04  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180021d0b  mov     rcx, rdi
0x180021d0e  mov     rax, rbx
0x180021d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d16  mov     ebx, eax
0x180021d18  test    eax, eax
0x180021d1a  jns     short loc_180021D23
0x180021d1c  lea     edx, [r12+35h]
0x180021d21  jmp     short loc_180021D84
0x180021d23  mov     [rbp+57h+string], r12
0x180021d27  lea     r9, [rbp+57h+string]; string
0x180021d2b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021d2f  mov     edx, 20h ; ' '; length
0x180021d34  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180021d3b  call    cs:__imp_WindowsCreateStringReference
0x180021d41  test    eax, eax
0x180021d43  jns     short loc_180021D58
0x180021d45  xor     r9d, r9d; lpArguments
0x180021d48  xor     r8d, r8d; nNumberOfArguments
0x180021d4b  lea     edx, [r9+1]; dwExceptionFlags
0x180021d4f  mov     ecx, eax; dwExceptionCode
0x180021d51  call    cs:__imp_RaiseException
0x180021d57  int     3; Trap to Debugger
0x180021d58  mov     rbx, [rbp+57h+string]
0x180021d5c  lea     rcx, [rbp+57h+var_70]
0x180021d60  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021d65  lea     r8, [rbp+57h+var_70]
0x180021d69  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180021d70  mov     rcx, rbx
0x180021d73  call    cs:__imp_RoGetActivationFactory
0x180021d79  mov     ebx, eax
0x180021d7b  test    eax, eax
0x180021d7d  jns     short loc_180021D9C
0x180021d7f  mov     edx, 36h ; '6'; void *
0x180021d84  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021d8b  mov     r9d, eax; char *
0x180021d8e  mov     rcx, [rbp+5Fh]; this
0x180021d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d97  jmp     loc_180022859
0x180021d9c  lea     r14, [r15+90h]
0x180021da3  mov     rcx, r14; SRWLock
0x180021da6  call    cs:__imp_AcquireSRWLockShared
0x180021dac  mov     [rbp+57h+var_90], r14
0x180021db0  mov     [rbp+57h+var_A8], r12
0x180021db4  mov     edi, [r15+48h]
0x180021db8  mov     rsi, [rbp+57h+var_70]
0x180021dbc  mov     rax, [rsi]
0x180021dbf  mov     rbx, [rax+58h]
0x180021dc3  lea     rcx, [rbp+57h+var_A8]
0x180021dc7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021dcc  lea     r8, [rbp+57h+var_A8]
0x180021dd0  mov     edx, edi
0x180021dd2  mov     rcx, rsi
0x180021dd5  mov     rax, rbx
0x180021dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ddd  mov     ebx, eax
0x180021ddf  test    eax, eax
0x180021de1  jns     short loc_180021E14
0x180021de3  mov     rcx, [rbp+5Fh]; this
0x180021de7  mov     r9d, eax; char *
0x180021dea  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021df1  mov     edx, 3Ch ; '<'; void *
0x180021df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021dfb  lea     rcx, [rbp+57h+var_A8]
0x180021dff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021e04  nop
0x180021e05  lea     rcx, [rbp+57h+var_90]; this
0x180021e09  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x180021e0e  nop
0x180021e0f  jmp     loc_180022859
0x180021e14  mov     [rbp+57h+var_B0], r12b
0x180021e18  mov     rbx, [rbp+57h+var_80]
0x180021e1c  mov     rdi, [rbx]
0x180021e1f  mov     rsi, [rbp+57h+var_A8]
0x180021e23  mov     [rbp+57h+string], r12
0x180021e27  lea     r9, [rbp+57h+string]; string
0x180021e2b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021e2f  mov     edx, 0Eh; length
0x180021e34  lea     rcx, aActivationkind; "ActivationKind"
0x180021e3b  call    cs:__imp_WindowsCreateStringReference
0x180021e41  test    eax, eax
0x180021e43  jns     short loc_180021E58
0x180021e45  xor     r9d, r9d; lpArguments
0x180021e48  xor     r8d, r8d; nNumberOfArguments
0x180021e4b  lea     edx, [r9+1]; dwExceptionFlags
0x180021e4f  mov     ecx, eax; dwExceptionCode
0x180021e51  call    cs:__imp_RaiseException
0x180021e57  int     3; Trap to Debugger
0x180021e58  lea     r9, [rbp+57h+var_B0]
0x180021e5c  mov     r8, rsi
0x180021e5f  mov     rdx, [rbp+57h+string]
0x180021e63  mov     rcx, rbx
0x180021e66  mov     rax, [rdi+50h]
0x180021e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e6f  mov     ebx, eax
0x180021e71  test    eax, eax
0x180021e73  jns     short loc_180021EAB
0x180021e75  mov     rcx, [rbp+5Fh]; this
0x180021e79  mov     r9d, eax; char *
0x180021e7c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021e83  mov     edx, 3Eh ; '>'; void *
0x180021e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e8d  lea     rcx, [rbp+57h+var_A8]
0x180021e91  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021e96  nop
0x180021e97  test    r14, r14
0x180021e9a  jz      short loc_180021EA6
0x180021e9c  mov     rcx, r14; SRWLock
0x180021e9f  call    cs:__imp_ReleaseSRWLockShared
0x180021ea5  nop
0x180021ea6  jmp     loc_180022859
0x180021eab  mov     [rbp+57h+var_A0], r12
0x180021eaf  mov     edi, [r15+4Ch]
0x180021eb3  mov     rsi, [rbp+57h+var_70]
0x180021eb7  mov     rax, [rsi]
0x180021eba  mov     rbx, [rax+58h]
0x180021ebe  lea     rcx, [rbp+57h+var_A0]
0x180021ec2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021ec7  lea     r8, [rbp+57h+var_A0]
0x180021ecb  mov     edx, edi
0x180021ecd  mov     rcx, rsi
0x180021ed0  mov     rax, rbx
0x180021ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ed8  mov     ebx, eax
0x180021eda  test    eax, eax
0x180021edc  jns     short loc_180021F18
0x180021ede  mov     rcx, [rbp+5Fh]; this
0x180021ee2  mov     r9d, eax; char *
0x180021ee5  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021eec  mov     edx, 42h ; 'B'; void *
0x180021ef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ef6  lea     rcx, [rbp+57h+var_A0]
0x180021efa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021eff  lea     rcx, [rbp+57h+var_A8]
0x180021f03  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021f08  nop
0x180021f09  lea     rcx, [rbp+57h+var_90]; this
0x180021f0d  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x180021f12  nop
0x180021f13  jmp     loc_180022859
0x180021f18  mov     rbx, [rbp+57h+var_80]
0x180021f1c  mov     rdi, [rbx]
0x180021f1f  mov     rsi, [rbp+57h+var_A0]
0x180021f23  mov     [rbp+57h+string], r12
0x180021f27  lea     r9, [rbp+57h+string]; string
0x180021f2b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021f2f  mov     edx, 16h; length
0x180021f34  lea     rcx, aPreviousexecut; "PreviousExecutionState"
0x180021f3b  call    cs:__imp_WindowsCreateStringReference
0x180021f41  test    eax, eax
0x180021f43  jns     short loc_180021F58
0x180021f45  xor     r9d, r9d; lpArguments
0x180021f48  xor     r8d, r8d; nNumberOfArguments
0x180021f4b  lea     edx, [r9+1]; dwExceptionFlags
0x180021f4f  mov     ecx, eax; dwExceptionCode
0x180021f51  call    cs:__imp_RaiseException
0x180021f57  int     3; Trap to Debugger
0x180021f58  lea     r9, [rbp+57h+var_B0]
0x180021f5c  mov     r8, rsi
0x180021f5f  mov     rdx, [rbp+57h+string]
0x180021f63  mov     rcx, rbx
0x180021f66  mov     rax, [rdi+50h]
0x180021f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f6f  mov     ebx, eax
0x180021f71  test    eax, eax
0x180021f73  jns     short loc_180021FAF
0x180021f75  mov     rcx, [rbp+5Fh]; this
0x180021f79  mov     r9d, eax; char *
0x180021f7c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021f83  mov     edx, 43h ; 'C'; void *
0x180021f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f8d  lea     rcx, [rbp+57h+var_A0]
0x180021f91  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021f96  lea     rcx, [rbp+57h+var_A8]
0x180021f9a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021f9f  nop
0x180021fa0  lea     rcx, [rbp+57h+var_90]; this
0x180021fa4  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x180021fa9  nop
0x180021faa  jmp     loc_180022859
0x180021faf  mov     [rbp+57h+var_98], r12
0x180021fb3  mov     rdi, [rbp+57h+var_70]
0x180021fb7  mov     rax, [rdi]
0x180021fba  mov     rbx, [rax+68h]
0x180021fbe  lea     rcx, [rbp+57h+var_98]
0x180021fc2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021fc7  lea     r8, [rbp+57h+var_98]
0x180021fcb  mov     rdx, [r15+68h]
0x180021fcf  mov     rcx, rdi
0x180021fd2  mov     rax, rbx
0x180021fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fda  mov     ebx, eax
0x180021fdc  test    eax, eax
0x180021fde  jns     short loc_180022023
0x180021fe0  mov     rcx, [rbp+5Fh]; this
0x180021fe4  mov     r9d, eax; char *
0x180021fe7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021fee  mov     edx, 46h ; 'F'; void *
0x180021ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ff8  lea     rcx, [rbp+57h+var_98]
0x180021ffc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022001  lea     rcx, [rbp+57h+var_A0]
0x180022005  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002200a  lea     rcx, [rbp+57h+var_A8]
0x18002200e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022013  nop
0x180022014  lea     rcx, [rbp+57h+var_90]; this
0x180022018  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x18002201d  nop
0x18002201e  jmp     loc_180022859
0x180022023  mov     rbx, [rbp+57h+var_80]
0x180022027  mov     rdi, [rbx]
0x18002202a  mov     rsi, [rbp+57h+var_98]
0x18002202e  mov     [rbp+57h+string], r12
0x180022032  lea     r9, [rbp+57h+string]; string
0x180022036  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002203a  mov     edx, 0Bh; length
0x18002203f  lea     rcx, aUsercontext; "UserContext"
0x180022046  call    cs:__imp_WindowsCreateStringReference
0x18002204c  test    eax, eax
0x18002204e  jns     short loc_180022063
0x180022050  xor     r9d, r9d; lpArguments
0x180022053  xor     r8d, r8d; nNumberOfArguments
0x180022056  lea     edx, [r9+1]; dwExceptionFlags
0x18002205a  mov     ecx, eax; dwExceptionCode
0x18002205c  call    cs:__imp_RaiseException
0x180022062  int     3; Trap to Debugger
0x180022063  lea     r9, [rbp+57h+var_B0]
0x180022067  mov     r8, rsi
0x18002206a  mov     rdx, [rbp+57h+string]
0x18002206e  mov     rcx, rbx
0x180022071  mov     rax, [rdi+50h]
0x180022075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002207a  mov     ebx, eax
0x18002207c  test    eax, eax
0x18002207e  jns     short loc_1800220C3
0x180022080  mov     rcx, [rbp+5Fh]; this
0x180022084  mov     r9d, eax; char *
0x180022087  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18002208e  mov     edx, 47h ; 'G'; void *
0x180022093  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022098  lea     rcx, [rbp+57h+var_98]
0x18002209c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800220a1  lea     rcx, [rbp+57h+var_A0]
0x1800220a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800220aa  lea     rcx, [rbp+57h+var_A8]
0x1800220ae  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800220b3  nop
0x1800220b4  lea     rcx, [rbp+57h+var_90]; this
0x1800220b8  call    ??1CAutoSRWSharedLock@@QEAA@XZ; CAutoSRWSharedLock::~CAutoSRWSharedLock(void)
0x1800220bd  nop
0x1800220be  jmp     loc_180022859
0x1800220c3  mov     rsi, [r15+58h]
0x1800220c7  test    rsi, rsi
0x1800220ca  jz      loc_180022158
0x1800220d0  mov     rdi, [rbp+57h+var_80]
0x1800220d4  mov     rax, [rdi]
0x1800220d7  mov     rbx, [rax+50h]
0x1800220db  mov     [rbp+57h+string], r12
0x1800220df  mov     r9d, 0Ch; unsigned int
0x1800220e5  lea     r8d, [r9+1]; unsigned int
0x1800220e9  lea     rdx, aSplashscreen; "SplashScreen"
0x1800220f0  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800220f4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800220f9  lea     r9, [rbp+57h+var_B0]
0x1800220fd  mov     r8, rsi
0x180022100  mov     rdx, [rbp+57h+string]
0x180022104  mov     rcx, rdi
0x180022107  mov     rax, rbx
0x18002210a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002210f  mov     ebx, eax
0x180022111  test    eax, eax
0x180022113  jns     short loc_180022158
0x180022115  mov     rcx, [rbp+5Fh]; this
0x180022119  mov     r9d, eax; char *
0x18002211c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180022123  mov     edx, 4Bh ; 'K'; void *
0x180022128  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
