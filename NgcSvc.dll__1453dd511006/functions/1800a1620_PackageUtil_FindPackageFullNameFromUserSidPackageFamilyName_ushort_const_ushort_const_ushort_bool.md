# PackageUtil::FindPackageFullNameFromUserSidPackageFamilyName(ushort const *,ushort const *,ushort * *,bool *)

- ea: `0x1800a1620`
- end: `0x1800a1daa`
- name: `?FindPackageFullNameFromUserSidPackageFamilyName@PackageUtil@@QEAAJPEBG0PEAPEAGPEA_N@Z`
- size: `1930`
- prototype: `__int64 __fastcall(PackageUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009abe4`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x1800988a0`
- `0x1800a0ca4`
- `0x1800a0dc4`
- `0x1800a1620`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1b98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1b98`

## string_xrefs

- `0x1800a1675`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a16a9`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a16f2`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a175e`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a17ce`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a184c`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a18f9`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1997`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1a39`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1af5`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1bdd`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall PackageUtil::FindPackageFullNameFromUserSidPackageFamilyName(
        PackageUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        bool *a5)
{
  bool *v7; // r14
  int v8; // eax
  char v9; // r8
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // rdi
  int v26; // eax
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  char *StringRawBuffer; // rax
  const char *v45; // r9
  unsigned __int16 *v46; // rbx
  __int64 v47; // rcx
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v52; // rcx
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  int v58; // [rsp+20h] [rbp-60h]
  __int64 v59; // [rsp+30h] [rbp-50h] BYREF
  __int64 v60; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v61)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  HSTRING v62; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v63; // [rsp+50h] [rbp-30h] BYREF
  __int64 v64; // [rsp+58h] [rbp-28h] BYREF
  __int64 v65; // [rsp+60h] [rbp-20h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  HSTRING v67; // [rsp+70h] [rbp-10h] BYREF
  __int64 v68; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  const WCHAR *v70; // [rsp+B8h] [rbp+38h] BYREF
  const WCHAR *v71; // [rsp+C0h] [rbp+40h] BYREF
  int v72; // [rsp+C8h] [rbp+48h] BYREF

  v71 = a3;
  v70 = a2;
  *a4 = 0;
  v7 = a5;
  *a5 = 0;
  v72 = 0;
  v67 = 0;
  v8 = Windows::Internal::String::Initialize<unsigned short const *>(&v67, &v71, (char)a3);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v8,
      v58);
LABEL_76:
    Windows::Internal::String::~String((Windows::Internal::String *)&v67);
    return v10;
  }
  v62 = 0;
  v11 = Windows::Internal::String::Initialize<unsigned short const *>(&v62, &v70, v9);
  v10 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v11,
      v58);
LABEL_75:
    Windows::Internal::String::~String((Windows::Internal::String *)&v62);
    goto LABEL_76;
  }
  v60 = 0;
  v59 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING, __int64 *))(**(_QWORD **)this + 160LL))(
          *(_QWORD *)this,
          v62,
          v67,
          &v60);
  v10 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v12,
      v58);
    v13 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_75;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 48LL))(v60, &v59);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v14,
      v58);
    v15 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_75;
  }
  LOBYTE(a5) = 1;
  v17 = (*(__int64 (__fastcall **)(__int64, bool **))(*(_QWORD *)v59 + 56LL))(v59, &a5);
  v10 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v17,
      v58);
    v18 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_75;
  }
  v63 = 0;
  if ( (_BYTE)a5 )
  {
    v61 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v59 + 48LL))(
            v59,
            &v61);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)(unsigned int)v20,
        v58);
      v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
      v22 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      goto LABEL_75;
    }
    v65 = 0;
    v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
    v25 = **v61;
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
    v26 = v25(v24, &GUID_65aed1ae_b95b_450c_882b_6255187f397e, &v65);
    v10 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)(unsigned int)v26,
        v58);
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
      v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
      v28 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      goto LABEL_75;
    }
    v30 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v65 + 48LL))(v65, &v72);
    v10 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)(unsigned int)v30,
        v58);
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
      v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v31)[2])(v31);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
      v32 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v33 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      goto LABEL_75;
    }
    v64 = 0;
    v34 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v61)[6])(v61, &v64);
    v10 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)(unsigned int)v34,
        v58);
      v35 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
      v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
      v37 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      goto LABEL_75;
    }
    string = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 96LL))(v64, &string);
    v10 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)(unsigned int)v39,
        v58);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      v40 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
      v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v41)[2])(v41);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
      v42 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      goto LABEL_75;
    }
    StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v68,
      StringRawBuffer,
      0xFFFFFFFFFFFFFFFFuLL,
      v45);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v63,
      &v68);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v68);
    v46 = v63;
    if ( !v63 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)0x8007000ELL,
        v58);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      v47 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
      v48 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v48)[2])(v48);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
      v49 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      v50 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      goto LABEL_75;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    v52 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(&v65);
    v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[2])(v53);
    }
    v63 = 0;
    *a4 = v46;
    *v7 = v72 == 4;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
    v54 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v62);
    Windows::Internal::String::~String((Windows::Internal::String *)&v67);
    return 0;
  }
  else
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v63);
    v56 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v62);
    Windows::Internal::String::~String((Windows::Internal::String *)&v67);
    return 2150040148LL;
  }
}

```

## disassembly

```asm
0x1800a1620  mov     [rsp-28h+arg_0], rbx
0x1800a1625  mov     [rsp-28h+arg_10], r8
0x1800a162a  mov     [rsp-28h+arg_8], rdx
0x1800a162f  push    rbp
0x1800a1630  push    rsi
0x1800a1631  push    rdi
0x1800a1632  push    r14
0x1800a1634  push    r15
0x1800a1636  mov     rbp, rsp
0x1800a1639  sub     rsp, 80h
0x1800a1640  mov     rsi, r9
0x1800a1643  mov     rdi, rcx
0x1800a1646  xor     r15d, r15d
0x1800a1649  mov     [r9], r15
0x1800a164c  mov     r14, [rbp+arg_20]
0x1800a1650  mov     [r14], r15b
0x1800a1653  mov     [rbp+arg_18], r15d
0x1800a1657  mov     [rbp+var_10], r15
0x1800a165b  lea     rdx, [rbp+arg_10]
0x1800a165f  lea     rcx, [rbp+var_10]
0x1800a1663  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800a1668  mov     ebx, eax
0x1800a166a  test    eax, eax
0x1800a166c  jns     short loc_1800A168B
0x1800a166e  mov     rcx, [rbp+28h]; this
0x1800a1672  mov     r9d, eax; char *
0x1800a1675  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a167c  mov     edx, 0E9h; void *
0x1800a1681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1686  jmp     loc_1800A1C7F
0x1800a168b  mov     [rbp+var_38], r15
0x1800a168f  lea     rdx, [rbp+arg_8]
0x1800a1693  lea     rcx, [rbp+var_38]
0x1800a1697  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800a169c  mov     ebx, eax
0x1800a169e  test    eax, eax
0x1800a16a0  jns     short loc_1800A16BF
0x1800a16a2  mov     rcx, [rbp+28h]; this
0x1800a16a6  mov     r9d, eax; char *
0x1800a16a9  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a16b0  mov     edx, 0ECh; void *
0x1800a16b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a16ba  jmp     loc_1800A1C75
0x1800a16bf  mov     [rbp+var_48], r15
0x1800a16c3  mov     [rbp+var_50], r15
0x1800a16c7  mov     rcx, [rdi]
0x1800a16ca  mov     rax, [rcx]
0x1800a16cd  lea     r9, [rbp+var_48]
0x1800a16d1  mov     r8, [rbp+var_10]
0x1800a16d5  mov     rdx, [rbp+var_38]
0x1800a16d9  mov     rax, [rax+0A0h]
0x1800a16e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a16e5  mov     ebx, eax
0x1800a16e7  test    eax, eax
0x1800a16e9  jns     short loc_1800A173D
0x1800a16eb  mov     rcx, [rbp+28h]; this
0x1800a16ef  mov     r9d, eax; char *
0x1800a16f2  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a16f9  mov     edx, 0F4h; void *
0x1800a16fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1703  nop
0x1800a1704  mov     rcx, [rbp+var_50]
0x1800a1708  test    rcx, rcx
0x1800a170b  jz      short loc_1800A171E
0x1800a170d  mov     [rbp+var_50], r15
0x1800a1711  mov     rax, [rcx]
0x1800a1714  mov     rax, [rax+10h]
0x1800a1718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a171d  nop
0x1800a171e  mov     rcx, [rbp+var_48]
0x1800a1722  test    rcx, rcx
0x1800a1725  jz      short loc_1800A1738
0x1800a1727  mov     [rbp+var_48], r15
0x1800a172b  mov     rax, [rcx]
0x1800a172e  mov     rax, [rax+10h]
0x1800a1732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1737  nop
0x1800a1738  jmp     loc_1800A1C75
0x1800a173d  mov     rcx, [rbp+var_48]
0x1800a1741  mov     rax, [rcx]
0x1800a1744  lea     rdx, [rbp+var_50]
0x1800a1748  mov     rax, [rax+30h]
0x1800a174c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1751  mov     ebx, eax
0x1800a1753  test    eax, eax
0x1800a1755  jns     short loc_1800A17A9
0x1800a1757  mov     rcx, [rbp+28h]; this
0x1800a175b  mov     r9d, eax; char *
0x1800a175e  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1765  mov     edx, 0F6h; void *
0x1800a176a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a176f  nop
0x1800a1770  mov     rcx, [rbp+var_50]
0x1800a1774  test    rcx, rcx
0x1800a1777  jz      short loc_1800A178A
0x1800a1779  mov     [rbp+var_50], r15
0x1800a177d  mov     rax, [rcx]
0x1800a1780  mov     rax, [rax+10h]
0x1800a1784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1789  nop
0x1800a178a  mov     rcx, [rbp+var_48]
0x1800a178e  test    rcx, rcx
0x1800a1791  jz      short loc_1800A17A4
0x1800a1793  mov     [rbp+var_48], r15
0x1800a1797  mov     rax, [rcx]
0x1800a179a  mov     rax, [rax+10h]
0x1800a179e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a17a3  nop
0x1800a17a4  jmp     loc_1800A1C75
0x1800a17a9  mov     byte ptr [rbp+arg_20], 1
0x1800a17ad  mov     rcx, [rbp+var_50]
0x1800a17b1  mov     rax, [rcx]
0x1800a17b4  lea     rdx, [rbp+arg_20]
0x1800a17b8  mov     rax, [rax+38h]
0x1800a17bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a17c1  mov     ebx, eax
0x1800a17c3  test    eax, eax
0x1800a17c5  jns     short loc_1800A1819
0x1800a17c7  mov     rcx, [rbp+28h]; this
0x1800a17cb  mov     r9d, eax; char *
0x1800a17ce  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a17d5  mov     edx, 0FAh; void *
0x1800a17da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a17df  nop
0x1800a17e0  mov     rcx, [rbp+var_50]
0x1800a17e4  test    rcx, rcx
0x1800a17e7  jz      short loc_1800A17FA
0x1800a17e9  mov     [rbp+var_50], r15
0x1800a17ed  mov     rax, [rcx]
0x1800a17f0  mov     rax, [rax+10h]
0x1800a17f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a17f9  nop
0x1800a17fa  mov     rcx, [rbp+var_48]
0x1800a17fe  test    rcx, rcx
0x1800a1801  jz      short loc_1800A1814
0x1800a1803  mov     [rbp+var_48], r15
0x1800a1807  mov     rax, [rcx]
0x1800a180a  mov     rax, [rax+10h]
0x1800a180e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1813  nop
0x1800a1814  jmp     loc_1800A1C75
0x1800a1819  mov     [rbp+var_30], r15
0x1800a181d  cmp     byte ptr [rbp+arg_20], r15b
0x1800a1821  jz      loc_1800A1D3D
0x1800a1827  mov     [rbp+var_40], r15
0x1800a182b  mov     rcx, [rbp+var_50]
0x1800a182f  mov     rax, [rcx]
0x1800a1832  lea     rdx, [rbp+var_40]
0x1800a1836  mov     rax, [rax+30h]
0x1800a183a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a183f  mov     ebx, eax
0x1800a1841  test    eax, eax
0x1800a1843  jns     short loc_1800A18BB
0x1800a1845  mov     rcx, [rbp+28h]; this
0x1800a1849  mov     r9d, eax; char *
0x1800a184c  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1853  mov     edx, 100h; void *
0x1800a1858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a185d  nop
0x1800a185e  mov     rcx, [rbp+var_40]
0x1800a1862  test    rcx, rcx
0x1800a1865  jz      short loc_1800A1878
0x1800a1867  mov     [rbp+var_40], r15
0x1800a186b  mov     rax, [rcx]
0x1800a186e  mov     rax, [rax+10h]
0x1800a1872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1877  nop
0x1800a1878  lea     rcx, [rbp+var_30]; void *
0x1800a187c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a1881  nop
0x1800a1882  mov     rcx, [rbp+var_50]
0x1800a1886  test    rcx, rcx
0x1800a1889  jz      short loc_1800A189C
0x1800a188b  mov     [rbp+var_50], r15
0x1800a188f  mov     rax, [rcx]
0x1800a1892  mov     rax, [rax+10h]
0x1800a1896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a189b  nop
0x1800a189c  mov     rcx, [rbp+var_48]
0x1800a18a0  test    rcx, rcx
0x1800a18a3  jz      short loc_1800A18B6
0x1800a18a5  mov     [rbp+var_48], r15
0x1800a18a9  mov     rax, [rcx]
0x1800a18ac  mov     rax, [rax+10h]
0x1800a18b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18b5  nop
0x1800a18b6  jmp     loc_1800A1C75
0x1800a18bb  mov     [rbp+var_20], r15
0x1800a18bf  mov     rbx, [rbp+var_40]
0x1800a18c3  mov     rax, [rbx]
0x1800a18c6  mov     rdi, [rax]
0x1800a18c9  lea     rcx, [rbp+var_20]
0x1800a18cd  call    ?InternalRelease@?$ComPtr@UIPackage4@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(void)
0x1800a18d2  lea     r8, [rbp+var_20]
0x1800a18d6  lea     rdx, _GUID_65aed1ae_b95b_450c_882b_6255187f397e
0x1800a18dd  mov     rcx, rbx
0x1800a18e0  mov     rax, rdi
0x1800a18e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18e8  mov     ebx, eax
0x1800a18ea  test    eax, eax
0x1800a18ec  jns     loc_1800A1972
0x1800a18f2  mov     rcx, [rbp+28h]; this
0x1800a18f6  mov     r9d, eax; char *
0x1800a18f9  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1900  mov     edx, 103h; void *
0x1800a1905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a190a  nop
0x1800a190b  lea     rcx, [rbp+var_20]
0x1800a190f  call    ?InternalRelease@?$ComPtr@UIPackage4@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(void)
0x1800a1914  nop
0x1800a1915  mov     rcx, [rbp+var_40]
0x1800a1919  test    rcx, rcx
0x1800a191c  jz      short loc_1800A192F
0x1800a191e  mov     [rbp+var_40], r15
0x1800a1922  mov     rax, [rcx]
0x1800a1925  mov     rax, [rax+10h]
0x1800a1929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a192e  nop
0x1800a192f  lea     rcx, [rbp+var_30]; void *
0x1800a1933  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a1938  nop
0x1800a1939  mov     rcx, [rbp+var_50]
0x1800a193d  test    rcx, rcx
0x1800a1940  jz      short loc_1800A1953
0x1800a1942  mov     [rbp+var_50], r15
0x1800a1946  mov     rax, [rcx]
0x1800a1949  mov     rax, [rax+10h]
0x1800a194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1952  nop
0x1800a1953  mov     rcx, [rbp+var_48]
0x1800a1957  test    rcx, rcx
0x1800a195a  jz      short loc_1800A196D
0x1800a195c  mov     [rbp+var_48], r15
0x1800a1960  mov     rax, [rcx]
0x1800a1963  mov     rax, [rax+10h]
0x1800a1967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a196c  nop
0x1800a196d  jmp     loc_1800A1C75
0x1800a1972  mov     rcx, [rbp+var_20]
0x1800a1976  mov     rax, [rcx]
0x1800a1979  lea     rdx, [rbp+arg_18]
0x1800a197d  mov     rax, [rax+30h]
0x1800a1981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1986  mov     ebx, eax
0x1800a1988  test    eax, eax
0x1800a198a  jns     loc_1800A1A10
0x1800a1990  mov     rcx, [rbp+28h]; this
0x1800a1994  mov     r9d, eax; char *
0x1800a1997  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a199e  mov     edx, 104h; void *
0x1800a19a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a19a8  nop
0x1800a19a9  lea     rcx, [rbp+var_20]
0x1800a19ad  call    ?InternalRelease@?$ComPtr@UIPackage4@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage4>::InternalRelease(void)
0x1800a19b2  nop
0x1800a19b3  mov     rcx, [rbp+var_40]
0x1800a19b7  test    rcx, rcx
0x1800a19ba  jz      short loc_1800A19CD
0x1800a19bc  mov     [rbp+var_40], r15
0x1800a19c0  mov     rax, [rcx]
0x1800a19c3  mov     rax, [rax+10h]
0x1800a19c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a19cc  nop
0x1800a19cd  lea     rcx, [rbp+var_30]; void *
0x1800a19d1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a19d6  nop
0x1800a19d7  mov     rcx, [rbp+var_50]
0x1800a19db  test    rcx, rcx
0x1800a19de  jz      short loc_1800A19F1
0x1800a19e0  mov     [rbp+var_50], r15
0x1800a19e4  mov     rax, [rcx]
0x1800a19e7  mov     rax, [rax+10h]
0x1800a19eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a19f0  nop
0x1800a19f1  mov     rcx, [rbp+var_48]
0x1800a19f5  test    rcx, rcx
0x1800a19f8  jz      short loc_1800A1A0B
0x1800a19fa  mov     [rbp+var_48], r15
0x1800a19fe  mov     rax, [rcx]
0x1800a1a01  mov     rax, [rax+10h]
0x1800a1a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a0a  nop
0x1800a1a0b  jmp     loc_1800A1C75
0x1800a1a10  mov     [rbp+var_28], r15
0x1800a1a14  mov     rcx, [rbp+var_40]
0x1800a1a18  mov     rax, [rcx]
0x1800a1a1b  lea     rdx, [rbp+var_28]
0x1800a1a1f  mov     rax, [rax+30h]
0x1800a1a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a28  mov     ebx, eax
0x1800a1a2a  test    eax, eax
0x1800a1a2c  jns     loc_1800A1ACC
0x1800a1a32  mov     rcx, [rbp+28h]; this
0x1800a1a36  mov     r9d, eax; char *
0x1800a1a39  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1a40  mov     edx, 107h; void *
0x1800a1a45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1a4a  nop
0x1800a1a4b  mov     rcx, [rbp+var_28]
0x1800a1a4f  test    rcx, rcx
  ... truncated ...
```
