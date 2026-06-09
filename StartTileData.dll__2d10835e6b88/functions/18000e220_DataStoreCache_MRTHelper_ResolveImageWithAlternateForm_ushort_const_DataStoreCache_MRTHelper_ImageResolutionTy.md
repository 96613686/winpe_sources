# DataStoreCache::MRTHelper::ResolveImageWithAlternateForm(ushort const *,DataStoreCache::MRTHelper::ImageResolutionType,IResourceMap *,IResourceContext *,DEVICE_SCALE_FACTOR,ushort,ushort,RESOURCE_CONTRAST const *,ushort const *,ushort const *,RESOURCE_CONTRAST *,ushort * *,ushort * *,ushort * *)

- ea: `0x18000e220`
- end: `0x18000eb32`
- name: `?ResolveImageWithAlternateForm@MRTHelper@DataStoreCache@@KAJPEBGW4ImageResolutionType@12@PEAUIResourceMap@@PEAUIResourceContext@@W4DEVICE_SCALE_FACTOR@@GGPEBW4RESOURCE_CONTRAST@@00PEAW47@PEAPEAG77@Z`
- size: `2322`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d258`

## callees

- `0x18000ccec`
- `0x18000ce08`
- `0x18000ce94`
- `0x18000e220`
- `0x18000f4c4`
- `0x18001aca4`
- `0x18002f1fc`
- `0x1800a5310`
- `0x1800a8e20`
- `0x1800a8e40`
- `0x1800f0854`
- `0x180114378`
- `0x18011951c`
- `0x18011c5fc`
- `0x180128594`
- `0x180159390`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e3fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e593`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e60a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e939`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e593`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e60a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e939`

## string_xrefs

- `0x18000e5d5`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000e64f`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000e68b`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000e8cb`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000e8f3`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000ea54`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000eaac`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreCache::MRTHelper::ResolveImageWithAlternateForm(
        const WCHAR *a1,
        int a2,
        struct IResourceMap *a3,
        struct IResourceContext *a4,
        unsigned int a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        _DWORD *a8,
        __int64 a9,
        LPVOID a10,
        _DWORD *a11,
        unsigned __int16 **a12,
        unsigned __int16 **a13,
        LPVOID *a14)
{
  _DWORD *v18; // r15
  unsigned __int16 **v19; // r14
  __int64 v20; // rdx
  unsigned int NamedResourceWithPathNormalization; // ebx
  __int64 v22; // r8
  int v23; // eax
  void *v24; // rbx
  char v25; // bl
  int v26; // eax
  int v27; // r12d
  __int64 v28; // rdx
  struct INamedResource *v29; // rcx
  struct INamedResource *v30; // rcx
  struct INamedResource *v32; // rcx
  int v33; // eax
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rax
  struct IResourceCandidate *v36; // rcx
  struct IResourceCandidate *v37; // rcx
  int v38; // eax
  struct IResourceCandidate *v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // r8
  int v42; // eax
  struct INamedResource *v43; // rcx
  struct IResourceCandidate *v44; // rcx
  struct IResourceCandidate *v45; // rcx
  struct INamedResource *v46; // rcx
  int ContrastFromCandidate; // eax
  struct INamedResource *v48; // rdi
  __int64 (__fastcall *v49)(struct INamedResource *, struct IResourceContext *, struct IResourceCandidate **); // rbx
  unsigned __int16 *v50; // rcx
  struct IResourceCandidate *v51; // rdx
  struct IResourceCandidate *v52; // rdx
  struct INamedResource *v53; // rcx
  struct IResourceCandidate *v54; // rdi
  __int64 (__fastcall *v55)(struct IResourceCandidate *, LPVOID *); // rbx
  int ThemeFromCandidate; // eax
  __int64 v57; // rdx
  int v58; // esi
  unsigned __int64 v59; // r9
  unsigned int v60; // eax
  int v61; // edx
  __int64 v62; // r9
  struct IResourceCandidate *v63; // rcx
  __int64 v64; // rdx
  LPVOID v65; // rax
  int v66; // [rsp+20h] [rbp-61h]
  int v67; // [rsp+20h] [rbp-61h]
  unsigned __int16 *v68; // [rsp+30h] [rbp-51h] BYREF
  struct IResourceCandidate *v69; // [rsp+38h] [rbp-49h] BYREF
  struct INamedResource *v70; // [rsp+40h] [rbp-41h] BYREF
  struct IResourceCandidate *v71; // [rsp+48h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-31h] BYREF
  struct IResourceCandidate *v73; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int16 *v74; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 *v75; // [rsp+68h] [rbp-19h] BYREF
  _DWORD *v76; // [rsp+70h] [rbp-11h] BYREF
  int v77; // [rsp+78h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v18 = a11;
  if ( a11 )
    *a11 = 0;
  v19 = a12;
  if ( a12 )
    *a12 = 0;
  if ( a13 )
    *a13 = 0;
  *a14 = 0;
  if ( !a10 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
      (const char *)0x80070057LL,
      v66);
  v70 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  NamedResourceWithPathNormalization = DataStoreCache::MRTHelper::GetNamedResourceWithPathNormalization(a1, a3, &v70);
  if ( (NamedResourceWithPathNormalization & 0x80000000) != 0 )
  {
    v29 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(struct INamedResource *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    return NamedResourceWithPathNormalization;
  }
  if ( a8 )
  {
    v23 = (*(__int64 (__fastcall **)(struct IResourceContext *, _QWORD))(*(_QWORD *)a4 + 128LL))(a4, (unsigned int)*a8);
    NamedResourceWithPathNormalization = v23;
    if ( v23 < 0 )
    {
      v28 = 605;
LABEL_110:
      v59 = (unsigned int)v23;
LABEL_112:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)v59,
        v66);
LABEL_130:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      return NamedResourceWithPathNormalization;
    }
  }
  if ( a9 )
    (*(void (__fastcall **)(struct IResourceContext *, const wchar_t *, __int64))(*(_QWORD *)a4 + 144LL))(
      a4,
      L"Theme",
      a9);
  v22 = *(_QWORD *)a4;
  if ( a2 == 1 )
  {
    v23 = (*(__int64 (__fastcall **)(struct IResourceContext *, _QWORD))(v22 + 112))(a4, a7);
    NamedResourceWithPathNormalization = v23;
    if ( v23 < 0 )
    {
      v28 = 617;
      goto LABEL_110;
    }
  }
  else
  {
    v40 = ShellMRTHelper::Common::ScaleFactorToResourceScale(a5, v20, v22);
    v42 = (*(__int64 (__fastcall **)(struct IResourceContext *, _QWORD))(v41 + 120))(a4, v40);
    NamedResourceWithPathNormalization = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26D,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v42,
        v66);
      v43 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(struct INamedResource *))(*(_QWORD *)v43 + 16LL))(v43);
      }
      return NamedResourceWithPathNormalization;
    }
  }
  NamedResourceWithPathNormalization = (*(__int64 (__fastcall **)(struct IResourceContext *, LPVOID))(*(_QWORD *)a4 + 136LL))(
                                         a4,
                                         a10);
  if ( (NamedResourceWithPathNormalization & 0x80000000) != 0 )
  {
    v59 = NamedResourceWithPathNormalization;
    v28 = 625;
    goto LABEL_112;
  }
  v76 = a8;
  v77 = a2;
  LODWORD(a11) = 0;
  pv = 0;
  v69 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  v68 = 0;
  v24 = pv;
  if ( pv )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&a12);
    CoTaskMemFree(v24);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&a12);
  }
  v25 = 0;
  pv = 0;
  LODWORD(a12) = DataStoreCache::MRTHelper::ResolveResourceCandidate(
                   a4,
                   v70,
                   (enum RESOURCE_CONTRAST *)&a11,
                   (unsigned __int16 **)&pv,
                   &v68,
                   &v69);
  if ( (int)a12 >= 0 && (v68 || a2 != 1) && ((_DWORD)a11 || a8 && !*a8) )
  {
    v25 = 1;
    if ( v68 && a9 && pv )
    {
      v26 = _o__wcsicmp(a9);
      v27 = (int)a11;
      v25 = v26 == 0;
      goto LABEL_39;
    }
    goto LABEL_38;
  }
  if ( (unsigned int)DataStoreCache::MRTHelper::TranslateMrtAlternateFormToUtmAlternateForm(a10) != 2 )
  {
LABEL_38:
    v27 = (int)a11;
    goto LABEL_39;
  }
  v38 = (*(__int64 (__fastcall **)(struct IResourceContext *, const wchar_t *))(*(_QWORD *)a4 + 136LL))(a4, L"unplated");
  NamedResourceWithPathNormalization = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
      (const char *)(unsigned int)v38,
      v67);
    v39 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    if ( v68 )
      CoTaskMemFree(v68);
    if ( pv )
      CoTaskMemFree(pv);
    v30 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(struct INamedResource *))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return NamedResourceWithPathNormalization;
  }
  LODWORD(a10) = 0;
  v75 = 0;
  v74 = 0;
  v73 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v74,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v75,
    0);
  v60 = DataStoreCache::MRTHelper::ResolveResourceCandidate(a4, v70, (enum RESOURCE_CONTRAST *)&a10, &v75, &v74, &v73);
  v27 = (int)a10;
  v25 = lambda_ae4f2981c61335f045e7ad8bf2b7e77c_::operator()(&v76, v60, (unsigned int)a10, v74);
  if ( v25 || !v68 && v62 )
  {
    LODWORD(a12) = v61;
    v63 = v73;
    v73 = 0;
    a10 = v69;
    v69 = v63;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a10);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pv,
      &v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v68,
      &v74);
  }
  else
  {
    v27 = (int)a11;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v74);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v75);
LABEL_39:
  LODWORD(a10) = 0;
  v71 = 0;
  if ( !v25 )
  {
    if ( a2 == 1
      && (ContrastFromCandidate = (*(__int64 (__fastcall **)(struct IResourceContext *, _QWORD))(*(_QWORD *)a4 + 112LL))(
                                    a4,
                                    a6),
          NamedResourceWithPathNormalization = ContrastFromCandidate,
          ContrastFromCandidate < 0) )
    {
      v64 = 717;
    }
    else
    {
      ContrastFromCandidate = (*(__int64 (__fastcall **)(struct IResourceContext *, const wchar_t *))(*(_QWORD *)a4 + 168LL))(
                                a4,
                                L"AlternateForm");
      NamedResourceWithPathNormalization = ContrastFromCandidate;
      if ( ContrastFromCandidate < 0 )
      {
        v64 = 719;
      }
      else
      {
        v48 = v70;
        v49 = *(__int64 (__fastcall **)(struct INamedResource *, struct IResourceContext *, struct IResourceCandidate **))(*(_QWORD *)v70 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
        NamedResourceWithPathNormalization = v49(v48, a4, &v71);
        if ( (NamedResourceWithPathNormalization & 0x80000000) != 0 )
        {
          v50 = v68;
          if ( (int)a12 < 0 || a2 == 1 && !v68 )
          {
            v51 = v71;
            if ( v71 )
            {
              v71 = 0;
              (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v51 + 16LL))(v51);
              v50 = v68;
            }
            v52 = v69;
            if ( v69 )
            {
              v69 = 0;
              (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v52 + 16LL))(v52);
              v50 = v68;
            }
            if ( v50 )
              CoTaskMemFree(v50);
            if ( pv )
              CoTaskMemFree(pv);
            v53 = v70;
            if ( v70 )
            {
              v70 = 0;
              (*(void (__fastcall **)(struct INamedResource *))(*(_QWORD *)v53 + 16LL))(v53);
            }
            return NamedResourceWithPathNormalization;
          }
          goto LABEL_40;
        }
        ContrastFromCandidate = DataStoreCache::MRTHelper::GetContrastFromCandidate(v71, (enum RESOURCE_CONTRAST *)&a10);
        NamedResourceWithPathNormalization = ContrastFromCandidate;
        if ( ContrastFromCandidate >= 0 )
        {
          v58 = (int)a10;
          if ( v68 && (int)a12 >= 0 && (v27 || !(_DWORD)a10) )
            goto LABEL_40;
          a10 = 0;
          v54 = v71;
          v55 = *(__int64 (__fastcall **)(struct IResourceCandidate *, LPVOID *))(*(_QWORD *)v71 + 32LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &a10,
            0);
          ThemeFromCandidate = v55(v54, &a10);
          NamedResourceWithPathNormalization = ThemeFromCandidate;
          if ( ThemeFromCandidate >= 0 )
          {
            if ( v18 )
              *v18 = v58;
            if ( !v19
              || (ThemeFromCandidate = DataStoreCache::MRTHelper::GetThemeFromCandidate(v71, v19),
                  NamedResourceWithPathNormalization = ThemeFromCandidate,
                  ThemeFromCandidate >= 0) )
            {
              v65 = a10;
              a10 = 0;
              *a14 = v65;
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&a10);
              goto LABEL_48;
            }
            v57 = 776;
          }
          else
          {
            v57 = 767;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v57,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
            (const char *)(unsigned int)ThemeFromCandidate,
            v67);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&a10);
LABEL_129:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v68);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
          goto LABEL_130;
        }
        v64 = 724;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v64,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
      (const char *)(unsigned int)ContrastFromCandidate,
      v67);
    goto LABEL_129;
  }
LABEL_40:
  a10 = 0;
  v33 = (*(__int64 (__fastcall **)(struct IResourceCandidate *, LPVOID *))(*(_QWORD *)v69 + 32LL))(v69, &a10);
  NamedResourceWithPathNormalization = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
      (const char *)(unsigned int)v33,
      v67);
    if ( a10 )
      CoTaskMemFree(a10);
    v44 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v45 + 16LL))(v45);
    }
    if ( v68 )
      CoTaskMemFree(v68);
    if ( pv )
      CoTaskMemFree(pv);
    v46 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(struct INamedResource *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    return NamedResourceWithPathNormalization;
  }
  if ( v18 )
    *v18 = v27;
  if ( v19 )
  {
    v34 = (unsigned __int16 *)pv;
    pv = 0;
    *v19 = v34;
  }
  if ( a13 )
  {
    v35 = v68;
    v68 = 0;
    *a13 = v35;
  }
  *a14 = a10;
LABEL_48:
  v36 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)v37 + 16LL))(v37);
  }
  if ( v68 )
    CoTaskMemFree(v68);
  if ( pv )
    CoTaskMemFree(pv);
  v32 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(struct INamedResource *))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e220  push    rbp
0x18000e222  push    rbx
0x18000e223  push    rsi
0x18000e224  push    rdi
0x18000e225  push    r12
0x18000e227  push    r13
0x18000e229  push    r14
0x18000e22b  push    r15
0x18000e22d  lea     rbp, [rsp-7]
0x18000e232  sub     rsp, 88h
0x18000e239  mov     rsi, r9
0x18000e23c  mov     rbx, r8
0x18000e23f  mov     r13d, edx
0x18000e242  mov     rdi, rcx
0x18000e245  mov     r15, [rbp+3Fh+arg_50]
0x18000e24c  xor     r12d, r12d
0x18000e24f  test    r15, r15
0x18000e252  jz      short loc_18000E257
0x18000e254  mov     [r15], r12d
0x18000e257  mov     r14, [rbp+3Fh+arg_58]
0x18000e25e  test    r14, r14
0x18000e261  jz      short loc_18000E266
0x18000e263  mov     [r14], r12
0x18000e266  mov     rax, [rbp+3Fh+arg_60]
0x18000e26d  test    rax, rax
0x18000e270  jz      short loc_18000E275
0x18000e272  mov     [rax], r12
0x18000e275  mov     rax, [rbp+3Fh+arg_68]
0x18000e27c  mov     [rax], r12
0x18000e27f  mov     rcx, [rbp+47h]; this
0x18000e283  cmp     [rbp+3Fh+arg_48], r12
0x18000e28a  jz      loc_18000E8C5
0x18000e290  mov     [rbp+3Fh+var_80], r12
0x18000e294  lea     rcx, [rbp+3Fh+var_80]
0x18000e298  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000e29d  lea     r8, [rbp+3Fh+var_80]; struct INamedResource **
0x18000e2a1  mov     rdx, rbx; struct IResourceMap *
0x18000e2a4  mov     rcx, rdi; pszMore
0x18000e2a7  call    ?GetNamedResourceWithPathNormalization@MRTHelper@DataStoreCache@@KAJPEBGPEAUIResourceMap@@PEAPEAUINamedResource@@@Z; DataStoreCache::MRTHelper::GetNamedResourceWithPathNormalization(ushort const *,IResourceMap *,INamedResource * *)
0x18000e2ac  mov     ebx, eax
0x18000e2ae  test    eax, eax
0x18000e2b0  js      loc_18000E440
0x18000e2b6  mov     rdi, [rbp+3Fh+arg_38]
0x18000e2bd  test    rdi, rdi
0x18000e2c0  jnz     loc_18000E418
0x18000e2c6  mov     r12, [rbp+3Fh+arg_40]
0x18000e2cd  test    r12, r12
0x18000e2d0  jz      short loc_18000E2EE
0x18000e2d2  mov     rax, [rsi]
0x18000e2d5  mov     r8, r12
0x18000e2d8  lea     rdx, aTheme; "Theme"
0x18000e2df  mov     rcx, rsi
0x18000e2e2  mov     rax, [rax+90h]
0x18000e2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ee  mov     r8, [rsi]
0x18000e2f1  cmp     r13d, 1
0x18000e2f5  jnz     loc_18000E628
0x18000e2fb  movzx   edx, [rbp+3Fh+arg_30]
0x18000e2ff  mov     rcx, rsi
0x18000e302  mov     rax, [r8+70h]
0x18000e306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e30b  mov     ebx, eax
0x18000e30d  test    eax, eax
0x18000e30f  js      loc_18000E8DD
0x18000e315  mov     rax, [rsi]
0x18000e318  mov     rdx, [rbp+3Fh+arg_48]
0x18000e31f  mov     rcx, rsi
0x18000e322  mov     rax, [rax+88h]
0x18000e329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e32e  mov     ebx, eax
0x18000e330  xor     eax, eax
0x18000e332  test    ebx, ebx
0x18000e334  js      loc_18000E8E7
0x18000e33a  mov     [rbp+3Fh+var_50], rdi
0x18000e33e  mov     [rbp+3Fh+var_48], r13d
0x18000e342  mov     dword ptr [rbp+3Fh+arg_50], eax
0x18000e348  mov     [rbp+3Fh+pv], rax
0x18000e34c  mov     [rbp+3Fh+var_90], rax
0x18000e350  mov     [rbp+3Fh+var_88], rax
0x18000e354  lea     rcx, [rbp+3Fh+var_88]
0x18000e358  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000e35d  mov     rbx, [rbp+3Fh+var_90]
0x18000e361  test    rbx, rbx
0x18000e364  jnz     loc_18000E904
0x18000e36a  mov     [rbp+3Fh+var_90], 0
0x18000e372  mov     rbx, [rbp+3Fh+pv]
0x18000e376  test    rbx, rbx
0x18000e379  jnz     loc_18000E92A
0x18000e37f  xor     ebx, ebx
0x18000e381  mov     [rbp+3Fh+pv], rbx
0x18000e385  lea     rax, [rbp+3Fh+var_88]
0x18000e389  mov     [rsp+0C0h+var_98], rax; struct IResourceCandidate **
0x18000e38e  lea     rax, [rbp+3Fh+var_90]
0x18000e392  mov     [rsp+0C0h+var_A0], rax; int
0x18000e397  lea     r9, [rbp+3Fh+pv]; unsigned __int16 **
0x18000e39b  lea     r8, [rbp+3Fh+arg_50]; enum RESOURCE_CONTRAST *
0x18000e3a2  mov     rdx, [rbp+3Fh+var_80]; struct INamedResource *
0x18000e3a6  mov     rcx, rsi; struct IResourceContext *
0x18000e3a9  call    ?ResolveResourceCandidate@MRTHelper@DataStoreCache@@KAJPEAUIResourceContext@@PEAUINamedResource@@PEAW4RESOURCE_CONTRAST@@PEAPEAG3PEAPEAUIResourceCandidate@@@Z; DataStoreCache::MRTHelper::ResolveResourceCandidate(IResourceContext *,INamedResource *,RESOURCE_CONTRAST *,ushort * *,ushort * *,IResourceCandidate * *)
0x18000e3ae  mov     dword ptr [rbp+3Fh+arg_58], eax
0x18000e3b4  test    eax, eax
0x18000e3b6  js      loc_18000E4BE
0x18000e3bc  mov     rdx, [rbp+3Fh+var_90]
0x18000e3c0  test    rdx, rdx
0x18000e3c3  jz      loc_18000E950
0x18000e3c9  cmp     dword ptr [rbp+3Fh+arg_50], ebx
0x18000e3cf  jz      loc_18000E4B1
0x18000e3d5  mov     bl, 1
0x18000e3d7  xor     edi, edi
0x18000e3d9  test    rdx, rdx
0x18000e3dc  jz      loc_18000E4D5
0x18000e3e2  test    r12, r12
0x18000e3e5  jz      loc_18000E4D5
0x18000e3eb  mov     rdx, [rbp+3Fh+pv]
0x18000e3ef  test    rdx, rdx
0x18000e3f2  jz      loc_18000E4D5
0x18000e3f8  mov     rcx, r12
0x18000e3fb  call    cs:__imp__o__wcsicmp
0x18000e401  mov     r12d, dword ptr [rbp+3Fh+arg_50]
0x18000e408  test    eax, eax
0x18000e40a  jz      loc_18000E4DC
0x18000e410  mov     bl, dil
0x18000e413  jmp     loc_18000E4DC
0x18000e418  mov     rax, [rsi]
0x18000e41b  mov     edx, [rdi]
0x18000e41d  mov     rcx, rsi
0x18000e420  mov     rax, [rax+80h]
0x18000e427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e42c  mov     ebx, eax
0x18000e42e  test    eax, eax
0x18000e430  jns     loc_18000E2C6
0x18000e436  mov     edx, 25Dh
0x18000e43b  jmp     loc_18000E8E2
0x18000e440  mov     rcx, [rbp+3Fh+var_80]
0x18000e444  test    rcx, rcx
0x18000e447  jz      short loc_18000E45A
0x18000e449  mov     [rbp+3Fh+var_80], r12
0x18000e44d  mov     rdx, [rcx]
0x18000e450  mov     rax, [rdx+10h]
0x18000e454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e459  nop
0x18000e45a  jmp     short loc_18000E476
0x18000e45c  mov     rcx, [rbp+3Fh+var_80]
0x18000e460  test    rcx, rcx
0x18000e463  jz      short loc_18000E476
0x18000e465  mov     [rbp+3Fh+var_80], rdi
0x18000e469  mov     rax, [rcx]
0x18000e46c  mov     rax, [rax+10h]
0x18000e470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e475  nop
0x18000e476  mov     eax, ebx
0x18000e478  jmp     short loc_18000E49D
0x18000e47a  call    cs:__imp_CoTaskMemFree
0x18000e480  nop
0x18000e481  mov     rcx, [rbp+3Fh+var_80]
0x18000e485  test    rcx, rcx
0x18000e488  jz      short loc_18000E49B
0x18000e48a  mov     [rbp+3Fh+var_80], rdi
0x18000e48e  mov     rax, [rcx]
0x18000e491  mov     rax, [rax+10h]
0x18000e495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e49a  nop
0x18000e49b  xor     eax, eax
0x18000e49d  add     rsp, 88h
0x18000e4a4  pop     r15
0x18000e4a6  pop     r14
0x18000e4a8  pop     r13
0x18000e4aa  pop     r12
0x18000e4ac  pop     rdi
0x18000e4ad  pop     rsi
0x18000e4ae  pop     rbx
0x18000e4af  pop     rbp
0x18000e4b0  retn
0x18000e4b1  test    rdi, rdi
0x18000e4b4  jz      short loc_18000E4BE
0x18000e4b6  cmp     [rdi], ebx
0x18000e4b8  jz      loc_18000E3D5
0x18000e4be  xor     edi, edi
0x18000e4c0  mov     rcx, [rbp+3Fh+arg_48]
0x18000e4c7  call    ?TranslateMrtAlternateFormToUtmAlternateForm@MRTHelper@DataStoreCache@@KA?AW4TileImageResourceAlternateForm@UnifiedTile@Shell@WindowsInternal@@PEBG@Z; DataStoreCache::MRTHelper::TranslateMrtAlternateFormToUtmAlternateForm(ushort const *)
0x18000e4cc  cmp     eax, 2
0x18000e4cf  jz      loc_18000E5AB
0x18000e4d5  mov     r12d, dword ptr [rbp+3Fh+arg_50]
0x18000e4dc  mov     dword ptr [rbp+3Fh+arg_48], edi
0x18000e4e2  mov     [rbp+3Fh+var_78], rdi
0x18000e4e6  test    bl, bl
0x18000e4e8  jz      loc_18000E721
0x18000e4ee  mov     [rbp+3Fh+arg_48], rdi
0x18000e4f5  mov     rcx, [rbp+3Fh+var_88]
0x18000e4f9  mov     rax, [rcx]
0x18000e4fc  lea     rdx, [rbp+3Fh+arg_48]
0x18000e503  mov     rax, [rax+20h]
0x18000e507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50c  mov     ebx, eax
0x18000e50e  test    eax, eax
0x18000e510  js      loc_18000E684
0x18000e516  test    r15, r15
0x18000e519  jz      short loc_18000E51E
0x18000e51b  mov     [r15], r12d
0x18000e51e  test    r14, r14
0x18000e521  jz      short loc_18000E52E
0x18000e523  mov     rax, [rbp+3Fh+pv]
0x18000e527  mov     [rbp+3Fh+pv], rdi
0x18000e52b  mov     [r14], rax
0x18000e52e  mov     rcx, [rbp+3Fh+arg_60]
0x18000e535  test    rcx, rcx
0x18000e538  jz      short loc_18000E545
0x18000e53a  mov     rax, [rbp+3Fh+var_90]
0x18000e53e  mov     [rbp+3Fh+var_90], rdi
0x18000e542  mov     [rcx], rax
0x18000e545  mov     rax, [rbp+3Fh+arg_48]
0x18000e54c  mov     rcx, [rbp+3Fh+arg_68]
0x18000e553  mov     [rcx], rax
0x18000e556  mov     rcx, [rbp+3Fh+var_78]
0x18000e55a  test    rcx, rcx
0x18000e55d  jz      short loc_18000E570
0x18000e55f  mov     [rbp+3Fh+var_78], rdi
0x18000e563  mov     rax, [rcx]
0x18000e566  mov     rax, [rax+10h]
0x18000e56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e56f  nop
0x18000e570  mov     rcx, [rbp+3Fh+var_88]
0x18000e574  test    rcx, rcx
0x18000e577  jz      short loc_18000E58A
0x18000e579  mov     [rbp+3Fh+var_88], rdi
0x18000e57d  mov     rax, [rcx]
0x18000e580  mov     rax, [rax+10h]
0x18000e584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e589  nop
0x18000e58a  mov     rcx, [rbp+3Fh+var_90]; pv
0x18000e58e  test    rcx, rcx
0x18000e591  jz      short loc_18000E599
0x18000e593  call    cs:__imp_CoTaskMemFree
0x18000e599  mov     rcx, [rbp+3Fh+pv]; pv
0x18000e59d  test    rcx, rcx
0x18000e5a0  jz      loc_18000E481
0x18000e5a6  jmp     loc_18000E47A
0x18000e5ab  mov     rax, [rsi]
0x18000e5ae  lea     rdx, aUnplated; "unplated"
0x18000e5b5  mov     rcx, rsi
0x18000e5b8  mov     rax, [rax+88h]
0x18000e5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5c4  mov     ebx, eax
0x18000e5c6  test    eax, eax
0x18000e5c8  jns     loc_18000E95F
0x18000e5ce  mov     rcx, [rbp+47h]; this
0x18000e5d2  mov     r9d, eax; char *
0x18000e5d5  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x18000e5dc  mov     edx, 2A9h; void *
0x18000e5e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5e6  nop
0x18000e5e7  mov     rcx, [rbp+3Fh+var_88]
0x18000e5eb  test    rcx, rcx
0x18000e5ee  jz      short loc_18000E601
0x18000e5f0  mov     [rbp+3Fh+var_88], rdi
0x18000e5f4  mov     rax, [rcx]
0x18000e5f7  mov     rax, [rax+10h]
0x18000e5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e600  nop
0x18000e601  mov     rcx, [rbp+3Fh+var_90]; pv
0x18000e605  test    rcx, rcx
0x18000e608  jz      short loc_18000E610
0x18000e60a  call    cs:__imp_CoTaskMemFree
0x18000e610  mov     rcx, [rbp+3Fh+pv]; pv
0x18000e614  test    rcx, rcx
0x18000e617  jz      loc_18000E45C
0x18000e61d  call    cs:__imp_CoTaskMemFree
0x18000e623  jmp     loc_18000E45C
0x18000e628  mov     ecx, [rbp+3Fh+arg_20]
0x18000e62b  call    ?ScaleFactorToResourceScale@Common@ShellMRTHelper@@YA?AW4RESOURCE_SCALE@@W4DEVICE_SCALE_FACTOR@@@Z; ShellMRTHelper::Common::ScaleFactorToResourceScale(DEVICE_SCALE_FACTOR)
0x18000e630  mov     edx, eax
0x18000e632  mov     rcx, rsi
0x18000e635  mov     rax, [r8+78h]
0x18000e639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e63e  mov     ebx, eax
0x18000e640  test    eax, eax
0x18000e642  jns     loc_18000E315
0x18000e648  mov     rcx, [rbp+47h]; this
0x18000e64c  mov     r9d, eax; char *
0x18000e64f  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x18000e656  mov     edx, 26Dh; void *
0x18000e65b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e660  nop
0x18000e661  mov     rcx, [rbp+3Fh+var_80]
0x18000e665  test    rcx, rcx
0x18000e668  jz      short loc_18000E67F
0x18000e66a  mov     [rbp+3Fh+var_80], 0
0x18000e672  mov     rax, [rcx]
0x18000e675  mov     rax, [rax+10h]
0x18000e679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e67e  nop
0x18000e67f  jmp     loc_18000E476
0x18000e684  mov     rcx, [rbp+47h]; this
0x18000e688  mov     r9d, ebx; char *
0x18000e68b  lea     r8, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x18000e692  mov     edx, 2E9h; void *
0x18000e697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e69c  mov     rcx, [rbp+3Fh+arg_48]; pv
0x18000e6a3  test    rcx, rcx
0x18000e6a6  jz      short loc_18000E6AF
  ... truncated ...
```
