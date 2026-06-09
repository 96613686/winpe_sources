# _GetHardwareCapabilitiesAndArchitecture(HSTRING__ * *,HSTRING__ * *)

- ea: `0x180185814`
- end: `0x180186fa1`
- name: `?_GetHardwareCapabilitiesAndArchitecture@@YAJPEAPEAUHSTRING__@@0@Z`
- size: `6029`
- prototype: `__int64 __fastcall(HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `54`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018260c`

## callees

- `0x180009ea0`
- `0x180010b74`
- `0x18001bd90`
- `0x18001bdf0`
- `0x18001bf24`
- `0x18001c144`
- `0x18001c964`
- `0x180035178`
- `0x180037200`
- `0x1800378d0`
- `0x1800453bc`
- `0x180045588`
- `0x18004f628`
- `0x180056d20`
- `0x18006cc00`
- `0x18006d98c`
- `0x18009a234`
- `0x1800c53b4`
- `0x1800cedcc`
- `0x18017de04`
- `0x18017dec0`
- `0x18017df7c`
- `0x18017e3b8`
- `0x18017ea40`
- `0x18017ec08`
- `0x18017eea8`
- `0x18017effc`
- `0x18017f3c0`
- `0x18017f4dc`
- `0x18017f630`
- `0x18017f74c`
- `0x18017f868`
- `0x18017f9bc`
- `0x18017fed0`
- `0x18017ff68`
- `0x180180000`
- `0x180180098`
- `0x1801801c0`
- `0x180180860`
- `0x18018095c`
- `0x180180b3c`
- `0x180180bdc`
- `0x18018123c`
- `0x18018170c`
- `0x1801817d4`
- `0x18018183c`
- `0x180181d48`
- `0x180182d2c`
- `0x180182fc8`
- `0x180185814`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180186918`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180186918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18018696f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186a32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186e80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18018696f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186a32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180186e80`

## string_xrefs

- `0x1801868b1`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x18018698a`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180186a4d`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180186aed`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180186c47`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180186ca5`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180186cdd`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180186e97`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=49
__int64 __fastcall _GetHardwareCapabilitiesAndArchitecture(HSTRING *a1, HSTRING *a2)
{
  char v2; // r14
  const char *v3; // r9
  size_t size_of; // rax
  _QWORD *v5; // rbx
  struct _SYSTEM_INFO *v6; // rdi
  _QWORD *v7; // rax
  __int64 v8; // rcx
  unsigned int i; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  const char *v12; // r9
  unsigned int v13; // eax
  __int64 v14; // rcx
  const char *v15; // r9
  unsigned int v16; // eax
  __int64 v17; // rcx
  const char *v18; // r9
  unsigned int v19; // eax
  __int64 v20; // rcx
  const char *v21; // r9
  __int64 AllAsync; // rax
  bool v23; // al
  __int64 v24; // rcx
  const char *v25; // r9
  __int64 v26; // rax
  bool v27; // al
  const char *v28; // r9
  __int64 v29; // rax
  bool v30; // al
  __int64 v31; // rcx
  const char *v32; // r9
  __m128i *v33; // rdi
  __m128i v34; // xmm6
  const char *v35; // r9
  __m128i *j; // rbx
  __int64 v37; // rax
  bool v38; // al
  __int8 IsHostCardEmulationSupported; // bl
  __int64 v40; // rcx
  const char *v41; // r9
  __int64 v42; // rax
  bool v43; // al
  __int64 v44; // rcx
  const char *v45; // r9
  __int8 v46; // bl
  unsigned int v47; // eax
  __int64 (__fastcall *v48)(const struct winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics *); // rcx
  unsigned int v49; // eax
  __int64 *v50; // rbx
  unsigned int v51; // eax
  enum AsyncStatus v52; // edx
  __int64 v53; // rcx
  unsigned int v54; // eax
  const char *v55; // r9
  __int8 v56; // al
  const char *v57; // r9
  __int8 v58; // al
  const char *v59; // r9
  __int8 v60; // al
  const char *v61; // r9
  const char *v62; // r9
  __m128i *v63; // r11
  __m128i *k; // r10
  __m128i **v65; // r10
  __m128i v66; // xmm0
  __int64 v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rdx
  HRESULT v70; // eax
  __int64 v71; // r8
  unsigned int v72; // edi
  _QWORD **v73; // rdx
  _QWORD *v74; // rcx
  _QWORD *v75; // rbx
  HRESULT v76; // eax
  _QWORD **v77; // rdx
  _QWORD *v78; // rcx
  _QWORD *v79; // rbx
  HRESULT v80; // eax
  _QWORD **v81; // rdx
  _QWORD *v82; // rcx
  _QWORD *v83; // rbx
  HRESULT v84; // eax
  _QWORD **v85; // rdx
  _QWORD *v86; // rcx
  _QWORD *v87; // rbx
  HRESULT v88; // eax
  _QWORD **v89; // rdx
  _QWORD *v90; // rcx
  _QWORD *v91; // rbx
  HRESULT v92; // eax
  _QWORD **v93; // rdx
  _QWORD *v94; // rcx
  _QWORD *v95; // rbx
  unsigned int v96; // eax
  const char *v97; // r9
  __int64 *v98; // rdi
  __int64 *m; // rbx
  __int64 v100; // r15
  char v101; // r12
  __int64 v102; // r8
  const unsigned __int16 *v103; // rdx
  __int64 v104; // r8
  const WCHAR *v105; // rcx
  HRESULT v106; // eax
  _QWORD **v107; // rdx
  _QWORD *v108; // rcx
  _QWORD *v109; // rbx
  _QWORD **v110; // rcx
  _QWORD *v111; // rcx
  _QWORD *v112; // rbx
  int v114; // [rsp+20h] [rbp-1F8h]
  const char *v115; // [rsp+28h] [rbp-1F0h]
  __m128i v116; // [rsp+30h] [rbp-1E8h] BYREF
  char v117[8]; // [rsp+40h] [rbp-1D8h] BYREF
  __int64 (__fastcall *v118)(const struct winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics *); // [rsp+48h] [rbp-1D0h] BYREF
  __int64 v119; // [rsp+50h] [rbp-1C8h] BYREF
  __int128 v120; // [rsp+58h] [rbp-1C0h] BYREF
  wchar_t *v121; // [rsp+68h] [rbp-1B0h] BYREF
  char v122; // [rsp+70h] [rbp-1A8h]
  int v123; // [rsp+71h] [rbp-1A7h]
  __int16 v124; // [rsp+75h] [rbp-1A3h]
  char v125; // [rsp+77h] [rbp-1A1h]
  int v126; // [rsp+78h] [rbp-1A0h] BYREF
  __int64 v127; // [rsp+80h] [rbp-198h] BYREF
  char v128; // [rsp+88h] [rbp-190h]
  wchar_t *v129; // [rsp+90h] [rbp-188h] BYREF
  __int128 v130; // [rsp+98h] [rbp-180h]
  HSTRING *string; // [rsp+B0h] [rbp-168h]
  __int64 v132; // [rsp+B8h] [rbp-160h] BYREF
  __int128 v133; // [rsp+C0h] [rbp-158h] BYREF
  HSTRING *v134; // [rsp+D0h] [rbp-148h]
  _QWORD v135[2]; // [rsp+D8h] [rbp-140h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+E8h] [rbp-130h] BYREF
  PCNZWCH sourceString[2]; // [rsp+118h] [rbp-100h] BYREF
  UINT32 length; // [rsp+128h] [rbp-F0h]
  unsigned __int64 v139; // [rsp+130h] [rbp-E8h]
  _OWORD v140[8]; // [rsp+140h] [rbp-D8h] BYREF
  int v141; // [rsp+1C0h] [rbp-58h]
  int v142; // [rsp+1C4h] [rbp-54h]
  char v143; // [rsp+1C8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  try
  {
    v134 = a1;
    string = a2;
    v132 = 0;
    v116.m128i_i64[0] = (__int64)&qword_1802E6038;
    v2 = 1;
    _InterlockedAdd64(&qword_1802E6038, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics> )
    {
      _lambda_19170038424925556a014a2097a441dc_::operator()(
        a1,
        &v119,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics>);
      _InterlockedDecrement64(&qword_1802E6038);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E6038);
      v118 = _lambda_26af1ca49efede7d23bd76b4f0091e5d_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics>::call<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Gaming::Input::Gamepad> (*)(winrt::Windows::Gaming::Input::IGamepadStatics const &)>(
        a1,
        &v119,
        &v118);
    }
    winrt::Windows::Foundation::IUnknown::operator=(&v132, &v119);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v119);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v3);
    v2 = 1;
  }
  v135[0] = L"x86";
  v135[1] = L"x64";
  v133 = 0;
  size_of = std::_Get_size_of_n<40>(1);
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)&v133 = v5;
  v6 = (struct _SYSTEM_INFO *)v135;
  do
  {
    std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Emplace_hint<unsigned short const * const &>(
      &v133,
      v5,
      v6);
    v6 = (struct _SYSTEM_INFO *)((char *)v6 + 8);
  }
  while ( v6 != &SystemInfo );
  v140[0] = _mm_load_si128((const __m128i *)&_xmm);
  v140[1] = _mm_load_si128((const __m128i *)&_xmm);
  v140[2] = _mm_load_si128((const __m128i *)&_xmm);
  v140[3] = _mm_load_si128((const __m128i *)&_xmm);
  v140[4] = _mm_load_si128((const __m128i *)&_xmm);
  v140[5] = _mm_load_si128((const __m128i *)&_xmm);
  v140[6] = _mm_load_si128((const __m128i *)&_xmm);
  v140[7] = _mm_load_si128((const __m128i *)&_xmm);
  v141 = 33;
  v142 = 34;
  v116.m128i_i64[0] = (__int64)v140;
  v116.m128i_i64[1] = (__int64)&v143;
  winrt::param::async_iterable<enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>::async_iterable<enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>(
    &v127,
    &v116);
  v120 = 0;
  v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
  *v7 = v7;
  v7[1] = v7;
  *(_QWORD *)&v120 = v7;
  try
  {
    v121 = (wchar_t *)&v127;
    v116.m128i_i64[0] = (__int64)&qword_1802E5248;
    _InterlockedAdd64(&qword_1802E5248, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics> )
    {
      _lambda_8851844acf8991df0c80ab7dd7d65589_::operator()(
        &v121,
        &v119,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics>);
      _InterlockedDecrement64(&qword_1802E5248);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E5248);
      winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics>::call<_lambda_8851844acf8991df0c80ab7dd7d65589_ &>(
        v8,
        &v119,
        &v121);
    }
    winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>>>((winrt *)&v118);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v119);
    for ( i = 0; i < 0x23; ++i )
    {
      if ( off_180228050[i] )
      {
        v126 = 0;
        v117[0] = 0;
        LODWORD(v129) = 0;
        v130 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(const struct winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics *), _QWORD, int *, char *))(*(_QWORD *)v118 + 64LL))(
                v118,
                i,
                &v126,
                v117);
        winrt::check_hresult(&v119, v10, &v129);
        if ( v117[0] )
        {
          v116.m128i_i64[0] = (__int64)off_180228050[i];
          v116.m128i_i8[8] = 1;
          *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
          *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
          v116.m128i_i8[15] = 0;
          std::list<ShortCode>::push_back(&v120, &v116);
        }
        else
        {
          v121 = off_180228050[i];
          v122 = 0;
          v123 = 0;
          v124 = 0;
          v125 = 0;
          std::list<ShortCode>::push_back(&v120, &v121);
        }
      }
    }
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v118);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v12);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)&qword_1802E60B8;
    _InterlockedAdd64(&qword_1802E60B8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Devices::Input::TouchCapabilities>(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory>,
        &v121);
      _InterlockedDecrement64(&qword_1802E60B8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E60B8);
      v118 = _lambda_a15ff3c6ef6754699948ab76a1ac847f_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Devices::Input::TouchCapabilities (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v11,
        &v121,
        &v118);
    }
    v126 = 0;
    LODWORD(v129) = 0;
    v130 = 0;
    v13 = (*(__int64 (__fastcall **)(wchar_t *, int *))(*(_QWORD *)v121 + 48LL))(v121, &v126);
    winrt::check_hresult(&v119, v13, &v129);
    v116.m128i_i64[0] = (__int64)L"tch";
    v116.m128i_i8[8] = v126 > 0;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v15);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)&qword_1802E60F8;
    _InterlockedAdd64(&qword_1802E60F8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Devices::Input::KeyboardCapabilities>(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory>,
        &v121);
      _InterlockedDecrement64(&qword_1802E60F8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E60F8);
      v118 = _lambda_4fc70953ad3a90d3b7ef637294af038f_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Devices::Input::KeyboardCapabilities (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v14,
        &v121,
        &v118);
    }
    v126 = 0;
    LODWORD(v129) = 0;
    v130 = 0;
    v16 = (*(__int64 (__fastcall **)(wchar_t *, int *))(*(_QWORD *)v121 + 48LL))(v121, &v126);
    winrt::check_hresult(&v119, v16, &v129);
    v116.m128i_i64[0] = (__int64)L"kbd";
    v116.m128i_i8[8] = v126 > 0;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v18);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)&qword_1802E60D8;
    _InterlockedAdd64(&qword_1802E60D8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Devices::Input::MouseCapabilities>(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory>,
        &v121);
      _InterlockedDecrement64(&qword_1802E60D8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E60D8);
      v118 = _lambda_a210ed02b6ad0116de4a668d69060f7b_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Devices::Input::MouseCapabilities (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v17,
        &v121,
        &v118);
    }
    v126 = 0;
    LODWORD(v129) = 0;
    v130 = 0;
    v19 = (*(__int64 (__fastcall **)(wchar_t *, int *))(*(_QWORD *)v121 + 48LL))(v121, &v126);
    winrt::check_hresult(&v119, v19, &v129);
    v116.m128i_i64[0] = (__int64)L"mse";
    v116.m128i_i8[8] = v126 > 0;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v21);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)&qword_1802E5FD8;
    _InterlockedAdd64(&qword_1802E5FD8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Media::Devices::MediaDevice,winrt::Windows::Media::Devices::IMediaDeviceStatics> )
    {
      _lambda_8fc7733a43d4c174b2c26f38b4c99ece_::operator()(
        v20,
        &v121,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Media::Devices::MediaDevice,winrt::Windows::Media::Devices::IMediaDeviceStatics>);
      _InterlockedDecrement64(&qword_1802E5FD8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E5FD8);
      v118 = _lambda_8fc7733a43d4c174b2c26f38b4c99ece_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Media::Devices::MediaDevice,winrt::Windows::Media::Devices::IMediaDeviceStatics>::call<winrt::hstring (*)(winrt::Windows::Media::Devices::IMediaDeviceStatics const &)>(
        v20,
        &v121,
        &v118);
    }
    v129 = v121;
    AllAsync = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync((const struct winrt::param::hstring *)&v126);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
      AllAsync,
      &v119);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v126);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v121);
    v23 = 0;
    if ( v119 )
      v23 = (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(&v119) != 0;
    v116.m128i_i64[0] = (__int64)L"cmr";
    v116.m128i_i8[8] = v23;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v119);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v25);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)&qword_1802E5FD8;
    _InterlockedAdd64(&qword_1802E5FD8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Media::Devices::MediaDevice,winrt::Windows::Media::Devices::IMediaDeviceStatics> )
    {
      _lambda_8d01896b91b8d406742a81118915306f_::operator()(
        v24,
        &v121,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Media::Devices::MediaDevice,winrt::Windows::Media::Devices::IMediaDeviceStatics>);
      _InterlockedDecrement64(&qword_1802E5FD8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E5FD8);
      v118 = _lambda_8d01896b91b8d406742a81118915306f_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Media::Devices::MediaDevice,winrt::Windows::Media::Devices::IMediaDeviceStatics>::call<winrt::hstring (*)(winrt::Windows::Media::Devices::IMediaDeviceStatics const &)>(
        v24,
        &v121,
        &v118);
    }
    v129 = v121;
    v26 = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync((const struct winrt::param::hstring *)&v126);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
      v26,
      &v119);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v126);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v121);
    v27 = 0;
    if ( v119 )
      v27 = (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(&v119) != 0;
    v116.m128i_i64[0] = (__int64)L"mic";
    v116.m128i_i8[8] = v27;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v119);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v28);
    v2 = 1;
  }
  try
  {
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)&v129,
      L"System.Devices.InterfaceClassGuid:=\"{4d1e55b2-f16f-11cf-88cb-001111000030}\" AND (System.DeviceInterface.Hid.Usag"
       "ePage:=1 AND System.DeviceInterface.Hid.UsageId:=15)");
    v29 = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync((const struct winrt::param::hstring *)&v118);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
      v29,
      &v121);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v118);
    v30 = 0;
    if ( v121 )
      v30 = (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(&v121) != 0;
    v116.m128i_i64[0] = (__int64)L"mct";
    v116.m128i_i8[8] = v30;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v32);
    v2 = 1;
  }
  try
  {
    v33 = (__m128i *)v120;
    for ( j = *(__m128i **)v120; j != v33; j = (__m128i *)j->m128i_i64[0] )
    {
      v34 = j[1];
      v116 = v34;
      if ( !wcscmp_0((const wchar_t *)v34.m128i_i64[0], L"nfc") )
      {
        if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v34, 8)) )
          goto LABEL_188;
        std::list<ShortCode>::remove_if<_lambda_dfb9b301e8d2d4d97ddbf3b6fd011b21_>(&v120, &v116);
        break;
      }
    }
    v116.m128i_i64[0] = (__int64)&qword_1802E5F98;
    _InterlockedAdd64(&qword_1802E5F98, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::Proximity::ProximityDevice,winrt::Windows::Networking::Proximity::IProximityDeviceStatics> )
    {
      _lambda_8d01896b91b8d406742a81118915306f_::operator()(
        v31,
        &v121,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::Proximity::ProximityDevice,winrt::Windows::Networking::Proximity::IProximityDeviceStatics>);
      _InterlockedDecrement64(&qword_1802E5F98);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E5F98);
      v118 = _lambda_8d01896b91b8d406742a81118915306f_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Networking::Proximity::ProximityDevice,winrt::Windows::Networking::Proximity::IProximityDeviceStatics>::call<winrt::hstring (*)(winrt::Windows::Networking::Proximity::IProximityDeviceStatics const &)>(
        v31,
        &v121,
        &v118);
    }
    v129 = v121;
    v37 = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync((const struct winrt::param::hstring *)&v126);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
      v37,
      &v119);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v126);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v121);
    v38 = 0;
    if ( v119 )
      v38 = (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(&v119) != 0;
    v116.m128i_i64[0] = (__int64)L"nfc";
    v116.m128i_i8[8] = v38;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v119);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v35);
    v2 = 1;
  }
LABEL_188:
  try
  {
    IsHostCardEmulationSupported = 0;
    if ( (unsigned __int8)winrt::impl::call_factory_cast<bool (*)(winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics3 const &),winrt::Windows::Devices::SmartCards::SmartCardEmulator,winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics3,_lambda_333adc0011d7a9ef262af6106a35e036_>() )
    {
      v116.m128i_i64[0] = (__int64)&qword_1802E6058;
      _InterlockedAdd64(&qword_1802E6058, 1u);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::SmartCards::SmartCardEmulator,winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics> )
      {
        _lambda_8d01896b91b8d406742a81118915306f_::operator()(
          v40,
          &v119,
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::SmartCards::SmartCardEmulator,winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics>);
        _InterlockedDecrement64(&qword_1802E6058);
      }
      else
      {
        _InterlockedDecrement64(&qword_1802E6058);
        v118 = _lambda_8d01896b91b8d406742a81118915306f_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Windows::Devices::SmartCards::SmartCardEmulator,winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::SmartCards::SmartCardEmulator> (*)(winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics const &)>(
          v40,
          &v119,
          &v118);
      }
      winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::SmartCards::SmartCardEmulator>>((winrt *)&v121);
      if ( v121 )
        IsHostCardEmulationSupported = winrt::impl::consume_Windows_Devices_SmartCards_ISmartCardEmulator2<winrt::Windows::Devices::SmartCards::SmartCardEmulator>::IsHostCardEmulationSupported(&v121);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v119);
    }
    v116.m128i_i64[0] = (__int64)L"hce";
    v116.m128i_i8[8] = IsHostCardEmulationSupported;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v41);
    v2 = 1;
  }
  try
  {
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)&v129,
      L"System.Devices.InterfaceClassGuid:=\"{92383b0e-f90e-4ac9-8d44-8c2d0d0ebda2}\" AND System.Devices.InterfaceEnabled:"
       "=System.StructuredQueryType.Boolean#True");
    v42 = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync((const struct winrt::param::hstring *)&v118);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
      v42,
      &v121);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v118);
    v43 = 0;
    if ( v121 )
      v43 = (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(&v121) != 0;
    v116.m128i_i64[0] = (__int64)L"ble";
    v116.m128i_i8[8] = v43;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v45);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)&qword_1802E5FB8;
    _InterlockedAdd64(&qword_1802E5FB8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::NetworkOperators::MobileBroadbandModem,winrt::Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics> )
    {
      _lambda_8fc7733a43d4c174b2c26f38b4c99ece_::operator()(
        v44,
        &v121,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::NetworkOperators::MobileBroadbandModem,winrt::Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>);
      _InterlockedDecrement64(&qword_1802E5FB8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1802E5FB8);
      v118 = _lambda_8fc7733a43d4c174b2c26f38b4c99ece_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Networking::NetworkOperators::MobileBroadbandModem,winrt::Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>::call<winrt::Windows::Networking::NetworkOperators::MobileBroadbandModem (*)(winrt::Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics const &)>(
        v44,
        &v121,
        &v118);
    }
    v46 = 0;
    if ( v121 )
    {
      v118 = 0;
      LODWORD(v129) = 0;
      v130 = 0;
      v47 = (*(__int64 (__fastcall **)(wchar_t *, __int64 (__fastcall **)(const struct winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics *)))(*(_QWORD *)v121 + 48LL))(
              v121,
              &v118);
      winrt::check_hresult(&v119, v47, &v129);
      v48 = v118;
      v116.m128i_i64[0] = (__int64)v118;
      if ( v118 )
      {
        v118 = 0;
        LODWORD(v129) = 0;
        v130 = 0;
        v49 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(const struct winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics *), __int64 (__fastcall **)(const struct winrt::Windows::Devices::SmartCards::ISmartCardEmulatorStatics *)))(*(_QWORD *)v48 + 72LL))(
                v48,
                &v118);
        winrt::check_hresult(&v119, v49, &v129);
        if ( v118 )
        {
          v50 = (__int64 *)winrt::impl::consume_Windows_Networking_NetworkOperators_IMobileBroadbandNetwork2<winrt::Windows::Networking::NetworkOperators::MobileBroadbandNetwork>::GetVoiceCallSupportAsync(
                             &v118,
                             &v126);
          v51 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>>::Status(v50);
          if ( !v51 )
            v51 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(v50);
          winrt::impl::check_status_canceled((winrt::impl *)v51, v52);
          v117[0] = 0;
          v53 = *v50;
          LODWORD(v129) = 0;
          v130 = 0;
          v54 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v53 + 64LL))(v53, v117);
          winrt::check_hresult(&v119, v54, &v129);
          v46 = v117[0];
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v126);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v118);
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v116);
    }
    v116.m128i_i64[0] = (__int64)L"tel";
    v116.m128i_i8[8] = v46;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v121);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v55);
    v2 = 1;
  }
  try
  {
    v56 = winrt::impl::call_factory_cast<bool (*)(winrt::Windows::Graphics::Holographic::IHolographicSpaceStatics2 const &),winrt::Windows::Graphics::Holographic::HolographicSpace,winrt::Windows::Graphics::Holographic::IHolographicSpaceStatics2,_lambda_a5638fed9de7800f644714612c145a04_>();
    v116.m128i_i64[0] = (__int64)L"hss";
    v116.m128i_i8[8] = v56;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v57);
    v2 = 1;
  }
  try
  {
    v58 = winrt::impl::call_factory_cast<bool (*)(winrt::Windows::Graphics::Holographic::IHolographicSpaceStatics3 const &),winrt::Windows::Graphics::Holographic::HolographicSpace,winrt::Windows::Graphics::Holographic::IHolographicSpaceStatics3,_lambda_a87a940b8595473fd3cc80b50249a339_>();
    v116.m128i_i64[0] = (__int64)L"mrc";
    v116.m128i_i8[8] = v58;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v59);
    v2 = 1;
  }
  try
  {
    v60 = winrt::impl::call_factory_cast<bool (*)(winrt::Windows::Graphics::Holographic::IHolographicSpaceStatics2 const &),winrt::Windows::Graphics::Holographic::HolographicSpace,winrt::Windows::Graphics::Holographic::IHolographicSpaceStatics2,_lambda_34d38c005ff02db4dd737b4723088a2f_>();
    v116.m128i_i64[0] = (__int64)L"hsa";
    v116.m128i_i8[8] = v60;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v61);
    v2 = 1;
  }
  try
  {
    v116.m128i_i64[0] = (__int64)L"hdc";
    v116.m128i_i8[8] = 0;
    *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
    v116.m128i_i8[15] = 0;
    std::list<ShortCode>::push_back(&v120, &v116);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x247,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      v62);
    v2 = 1;
  }
  v116.m128i_i64[0] = (__int64)L"xbo";
  v116.m128i_i8[8] = 0;
  *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
  *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
  v116.m128i_i8[15] = 0;
  std::list<ShortCode>::push_back(&v120, &v116);
  v116.m128i_i64[0] = (__int64)L"xbs";
  v116.m128i_i8[8] = 0;
  *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
  *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
  v116.m128i_i8[15] = 0;
  std::list<ShortCode>::push_back(&v120, &v116);
  v116.m128i_i64[0] = (__int64)L"xbx";
  v116.m128i_i8[8] = 0;
  *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
  *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
  v116.m128i_i8[15] = 0;
  std::list<ShortCode>::push_back(&v120, &v116);
  v116.m128i_i64[0] = (__int64)L"xbd";
  v116.m128i_i8[8] = 0;
  *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
  *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
  v116.m128i_i8[15] = 0;
  std::list<ShortCode>::push_back(&v120, &v116);
  v63 = (__m128i *)v120;
  for ( k = *(__m128i **)v120; ; k = *v65 )
  {
    if ( k == v63 )
    {
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetSystemInfo(&SystemInfo);
      if ( SystemInfo.wProcessorArchitecture == 5 )
      {
        v116.m128i_i64[0] = (__int64)L"arm";
        v116.m128i_i8[8] = 1;
        *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
        *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
        v116.m128i_i8[15] = 0;
        std::list<ShortCode>::push_back(&v120, &v116);
        v76 = WindowsCreateString(L"arm", 3u, string);
        v72 = v76;
        if ( v76 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x266,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
            (const char *)(unsigned int)v76,
            v114);
          v77 = (_QWORD **)v120;
          **(_QWORD **)(v120 + 8) = 0;
          v78 = *v77;
          if ( *v77 )
          {
            do
            {
              v79 = (_QWORD *)*v78;
              std::_Deallocate<16>(v78, (struct std::nothrow_t *)0x20);
              v78 = v79;
            }
            while ( v79 );
          }
          goto LABEL_100;
        }
      }
      else if ( SystemInfo.wProcessorArchitecture == 9 )
      {
        v116.m128i_i64[0] = (__int64)L"x64";
        v116.m128i_i8[8] = 1;
        *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
        *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
        v116.m128i_i8[15] = 0;
        std::list<ShortCode>::push_back(&v120, &v116);
        v80 = WindowsCreateString(L"x64", 3u, string);
        v72 = v80;
        if ( v80 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26C,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
            (const char *)(unsigned int)v80,
            v114);
          v81 = (_QWORD **)v120;
          **(_QWORD **)(v120 + 8) = 0;
          v82 = *v81;
          if ( *v81 )
          {
            do
            {
              v83 = (_QWORD *)*v82;
              std::_Deallocate<16>(v82, (struct std::nothrow_t *)0x20);
              v82 = v83;
            }
            while ( v83 );
          }
          goto LABEL_100;
        }
      }
      else if ( SystemInfo.wProcessorArchitecture )
      {
        if ( SystemInfo.wProcessorArchitecture == 12 )
        {
          v116.m128i_i64[0] = (__int64)L"x86";
          v116.m128i_i8[8] = 1;
          *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
          *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
          v116.m128i_i8[15] = 0;
          std::list<ShortCode>::push_back(&v120, &v116);
          v116.m128i_i64[0] = (__int64)L"arm64";
          v116.m128i_i8[8] = 1;
          *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
          *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
          v116.m128i_i8[15] = 0;
          std::list<ShortCode>::push_back(&v120, &v116);
          v116.m128i_i64[0] = (__int64)L"x86a64";
          v116.m128i_i8[8] = 1;
          *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
          *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
          v116.m128i_i8[15] = 0;
          std::list<ShortCode>::push_back(&v120, &v116);
          v116.m128i_i64[0] = (__int64)L"arm";
          v116.m128i_i8[8] = 1;
          *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
          *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
          v116.m128i_i8[15] = 0;
          std::list<ShortCode>::push_back(&v120, &v116);
          v116.m128i_i64[0] = (__int64)L"x64";
          v116.m128i_i8[8] = 1;
          *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
          *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
          v116.m128i_i8[15] = 0;
          std::list<ShortCode>::push_back(&v120, &v116);
          v88 = WindowsCreateString(L"arm,arm64,x64,x86,x86a64", 0x18u, string);
          v72 = v88;
          if ( v88 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x27E,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
              (const char *)(unsigned int)v88,
              v114);
            v89 = (_QWORD **)v120;
            **(_QWORD **)(v120 + 8) = 0;
            v90 = *v89;
            if ( *v89 )
            {
              do
              {
                v91 = (_QWORD *)*v90;
                std::_Deallocate<16>(v90, (struct std::nothrow_t *)0x20);
                v90 = v91;
              }
              while ( v91 );
            }
            goto LABEL_100;
          }
        }
        else
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x283,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
            (const char *)0x80070032LL,
            (int)"No supported achitecture was detected, assuming x86",
            v115);
          v92 = WindowsCreateString(L"x86", 3u, string);
          v72 = v92;
          if ( v92 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x285,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
              (const char *)(unsigned int)v92,
              v114);
            v93 = (_QWORD **)v120;
            **(_QWORD **)(v120 + 8) = 0;
            v94 = *v93;
            if ( *v93 )
            {
              do
              {
                v95 = (_QWORD *)*v94;
                std::_Deallocate<16>(v94, (struct std::nothrow_t *)0x20);
                v94 = v95;
              }
              while ( v95 );
            }
            goto LABEL_100;
          }
        }
      }
      else
      {
        v116.m128i_i64[0] = (__int64)L"x86";
        v116.m128i_i8[8] = 1;
        *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
        *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
        v116.m128i_i8[15] = 0;
        std::list<ShortCode>::push_back(&v120, &v116);
        v84 = WindowsCreateString(L"x86", 3u, string);
        v72 = v84;
        if ( v84 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x272,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
            (const char *)(unsigned int)v84,
            v114);
          v85 = (_QWORD **)v120;
          **(_QWORD **)(v120 + 8) = 0;
          v86 = *v85;
          if ( *v85 )
          {
            do
            {
              v87 = (_QWORD *)*v86;
              std::_Deallocate<16>(v86, (struct std::nothrow_t *)0x20);
              v86 = v87;
            }
            while ( v87 );
          }
          goto LABEL_100;
        }
      }
      goto LABEL_121;
    }
    v66 = k[1];
    v116 = v66;
    *(double *)v66.m128i_i64 = std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Find_lower_bound<unsigned short const *>(
                                 &v133,
                                 &v129,
                                 &v116);
    v67 = *((_QWORD *)&v130 + 1);
    if ( *(_BYTE *)(*((_QWORD *)&v130 + 1) + 25LL) || v66.m128i_i64[0] < *(_QWORD *)(*((_QWORD *)&v130 + 1) + 32LL) )
    {
      v68 = v133;
      v67 = v133;
    }
    else
    {
      v68 = v133;
    }
    if ( v67 != v68 && (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v66, 8)) )
      break;
  }
  v69 = -1;
  do
    ++v69;
  while ( *(_WORD *)(v66.m128i_i64[0] + 2 * v69) );
  v70 = WindowsCreateString((PCNZWCH)v66.m128i_i64[0], v69, string);
  v72 = v70;
  if ( v70 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)v70,
      v114);
    v73 = (_QWORD **)v120;
    **(_QWORD **)(v120 + 8) = 0;
    v74 = *v73;
    if ( *v73 )
    {
      do
      {
        v75 = (_QWORD *)*v74;
        std::_Deallocate<16>(v74, (struct std::nothrow_t *)0x20);
        v74 = v75;
      }
      while ( v75 );
    }
LABEL_100:
    std::_Deallocate<16>((void *)v120, (struct std::nothrow_t *)0x20);
    if ( !v128 )
      v127 = 0;
    goto LABEL_145;
  }
LABEL_121:
  if ( v132 )
  {
    v116.m128i_i64[0] = (__int64)L"xgp";
    v126 = 0;
    LODWORD(v129) = 0;
    v130 = 0;
    v96 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v132 + 56LL))(v132, &v126);
    try
    {
      winrt::check_hresult(&v119, v96, &v129);
      v116.m128i_i8[8] = v126 != 0;
      *(__int32 *)((char *)&v116.m128i_i32[2] + 1) = 0;
      *(__int16 *)((char *)&v116.m128i_i16[6] + 1) = 0;
      v116.m128i_i8[15] = 0;
      std::list<ShortCode>::push_back(&v120, &v116);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
        v97);
      v2 = 1;
    }
  }
  LOBYTE(v71) = 0;
  std::_List_val<std::_List_simple_types<ShortCode>>::_Sort<std::less<void>>(v120, *((_QWORD *)&v120 + 1), v71);
  std::wstring::wstring(sourceString);
  v98 = (__int64 *)v120;
  for ( m = *(__int64 **)v120; m != v98; m = (__int64 *)*m )
  {
    v100 = m[2];
    v101 = *((_BYTE *)m + 24);
    if ( !v2 )
      std::wstring::_Append<unsigned short>(sourceString);
    v2 = 0;
    v102 = -1;
    do
      ++v102;
    while ( *(_WORD *)(v100 + 2 * v102) );
    std::wstring::_Append<unsigned short>(sourceString);
    v103 = L"1";
    if ( !v101 )
      v103 = L"0";
    v104 = -1;
    do
      ++v104;
    while ( v103[v104] );
    std::wstring::_Append<unsigned short>(sourceString);
  }
  v105 = (const WCHAR *)sourceString;
  if ( v139 > 7 )
    v105 = sourceString[0];
  v106 = WindowsCreateString(v105, length, v134);
  v72 = v106;
  if ( v106 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)v106,
      v114);
    std::wstring::_Tidy_deallocate(sourceString);
    v107 = (_QWORD **)v120;
    **(_QWORD **)(v120 + 8) = 0;
    v108 = *v107;
    if ( *v107 )
    {
      do
      {
        v109 = (_QWORD *)*v108;
        std::_Deallocate<16>(v108, (struct std::nothrow_t *)0x20);
        v108 = v109;
      }
      while ( v109 );
    }
    goto LABEL_100;
  }
  std::wstring::_Tidy_deallocate(sourceString);
  v110 = (_QWORD **)v120;
  **(_QWORD **)(v120 + 8) = 0;
  v111 = *v110;
  if ( v111 )
  {
    do
    {
      v112 = (_QWORD *)*v111;
      std::_Deallocate<16>(v111, (struct std::nothrow_t *)0x20);
      v111 = v112;
    }
    while ( v112 );
  }
  std::_Deallocate<16>((void *)v120, (struct std::nothrow_t *)0x20);
  if ( !v128 )
    v127 = 0;
  v72 = 0;
LABEL_145:
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v127);
  std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::~_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>(&v133);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v132);
  return v72;
}

```

## disassembly

```asm
0x180185814  mov     rax, rsp
0x180185817  mov     [rax+18h], rbx
0x18018581b  mov     [rax+20h], rsi
0x18018581f  push    rdi
0x180185820  push    r12
0x180185822  push    r13
0x180185824  push    r14
0x180185826  push    r15
0x180185828  sub     rsp, 1F0h
0x18018582f  movaps  xmmword ptr [rax-38h], xmm6
0x180185833  mov     rax, cs:__security_cookie
0x18018583a  xor     rax, rsp
0x18018583d  mov     [rsp+218h+var_48], rax
0x180185845  mov     [rsp+218h+var_148], rcx
0x18018584d  mov     [rsp+218h+string], rdx
0x180185855  xor     esi, esi
0x180185857  mov     [rsp+218h+var_160], rsi
0x18018585f  lea     rax, qword_1802E6038
0x180185866  mov     qword ptr [rsp+218h+var_1E8], rax
0x18018586b  lea     r14d, [rsi+1]
0x18018586f  lock add cs:qword_1802E6038, r14
0x180185877  cmp     cs:??$factory_cache_entry_v@UGamepad@Input@Gaming@Windows@winrt@@UIGamepadStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UGamepad@Input@Gaming@Windows@winrt@@UIGamepadStatics@2345@@12@A, rsi; factory_cache_entry<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics>::winrt::factory_cache_entry<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics>
0x18018587e  jz      short loc_18018589C
0x180185880  lea     r8, ??$factory_cache_entry_v@UGamepad@Input@Gaming@Windows@winrt@@UIGamepadStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UGamepad@Input@Gaming@Windows@winrt@@UIGamepadStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics>::winrt::factory_cache_entry<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Gaming::Input::Gamepad,winrt::Windows::Gaming::Input::IGamepadStatics>
0x180185887  lea     rdx, [rsp+218h+var_1C8]
0x18018588c  call    ??R_lambda_19170038424925556a014a2097a441dc_@@QEBA@AEBUIGamepadStatics@Input@Gaming@Windows@winrt@@@Z; _lambda_19170038424925556a014a2097a441dc_::operator()(winrt::Windows::Gaming::Input::IGamepadStatics const &)
0x180185891  nop
0x180185892  lock dec cs:qword_1802E6038
0x18018589a  jmp     short loc_1801858BF
0x18018589c  lock dec cs:qword_1802E6038
0x1801858a4  lea     rax, ?_lambda_invoker_cdecl_@_lambda_26af1ca49efede7d23bd76b4f0091e5d_@@CA@AEBUIGlobalizationPreferencesStatics@UserProfile@System@Windows@winrt@@@Z; _lambda_26af1ca49efede7d23bd76b4f0091e5d_::_lambda_invoker_cdecl_(winrt::Windows::System::UserProfile::IGlobalizationPreferencesStatics const &)
0x1801858ab  mov     [rsp+218h+var_1D0], rax
0x1801858b0  lea     r8, [rsp+218h+var_1D0]
0x1801858b5  lea     rdx, [rsp+218h+var_1C8]
0x1801858ba  call    ??$call@P6A?AU?$IVectorView@UGamepad@Input@Gaming@Windows@winrt@@@Collections@Foundation@Windows@winrt@@AEBUIGamepadStatics@Input@Gaming@45@@Z@?$factory_cache_entry@UGamepad@Input@Gaming@Windows@winrt@@UIGamepadStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IVectorView@UGamepad@Input@Gaming@Windows@winrt@@@Collections@Foundation@Windows@2@AEBUIGamepadStatics@Input@Gaming@62@@Z@Z
0x1801858bf  lea     rdx, [rsp+218h+var_1C8]
0x1801858c4  lea     rcx, [rsp+218h+var_160]
0x1801858cc  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1801858d1  lea     rcx, [rsp+218h+var_1C8]; void *
0x1801858d6  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801858db  nop
0x1801858dc  jmp     short loc_1801858E4
0x1801858de  xor     esi, esi
0x1801858e0  lea     r14d, [rsi+1]
0x1801858e4  lea     r15, aX86_0; "x86"
0x1801858eb  mov     [rsp+218h+var_140], r15
0x1801858f3  lea     r12, aX64; "x64"
0x1801858fa  mov     [rsp+218h+var_138], r12
0x180185902  xorps   xmm0, xmm0
0x180185905  movdqu  [rsp+218h+var_158], xmm0
0x18018590e  mov     rcx, r14
0x180185911  call    ??$_Get_size_of_n@$0CI@@std@@YA_K_K@Z; std::_Get_size_of_n<40>(unsigned __int64)
0x180185916  mov     rcx, rax
0x180185919  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18018591e  mov     rbx, rax
0x180185921  mov     [rax], rax
0x180185924  mov     [rax+8], rax
0x180185928  mov     [rax+10h], rax
0x18018592c  mov     word ptr [rax+18h], 101h
0x180185932  mov     qword ptr [rsp+218h+var_158], rax
0x18018593a  lea     rdi, [rsp+218h+var_140]
0x180185942  mov     r8, rdi
0x180185945  mov     rdx, rbx
0x180185948  lea     rcx, [rsp+218h+var_158]
0x180185950  call    ??$_Emplace_hint@AEBQEBG@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@PEBGPEAX@1@QEAU21@AEBQEBG@Z; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Emplace_hint<ushort const * const &>(std::_Tree_node<ushort const *,void *> * const,ushort const * const &)
0x180185955  add     rdi, 8
0x180185959  lea     rax, [rsp+218h+SystemInfo]
0x180185961  cmp     rdi, rax
0x180185964  jnz     short loc_180185942
0x180185966  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x18018596e  movdqa  [rsp+218h+var_D8], xmm0
0x180185977  movdqa  xmm1, cs:__xmm@00000007000000060000000500000004
0x18018597f  movdqa  [rsp+218h+var_C8], xmm1
0x180185988  movdqa  xmm0, cs:__xmm@0000000b0000000a0000000900000008
0x180185990  movdqa  [rsp+218h+var_B8], xmm0
0x180185999  movdqa  xmm1, cs:__xmm@0000000f0000000e0000000d0000000c
0x1801859a1  movdqa  [rsp+218h+var_A8], xmm1
0x1801859aa  movdqa  xmm0, cs:__xmm@00000013000000120000001100000010
0x1801859b2  movdqa  [rsp+218h+var_98], xmm0
0x1801859bb  movdqa  xmm1, cs:__xmm@00000017000000160000001500000014
0x1801859c3  movdqa  [rsp+218h+var_88], xmm1
0x1801859cc  movdqa  xmm0, cs:__xmm@0000001b0000001a0000001900000018
0x1801859d4  movdqa  [rsp+218h+var_78], xmm0
0x1801859dd  movdqa  xmm1, cs:__xmm@0000001f0000001e0000001d0000001c
0x1801859e5  movdqa  [rsp+218h+var_68], xmm1
0x1801859ee  mov     [rsp+218h+var_58], 21h ; '!'
0x1801859f9  mov     [rsp+218h+var_54], 22h ; '"'
0x180185a04  lea     rax, [rsp+218h+var_D8]
0x180185a0c  mov     qword ptr [rsp+218h+var_1E8], rax
0x180185a11  lea     rax, [rsp+218h+var_50]
0x180185a19  mov     qword ptr [rsp+218h+var_1E8+8], rax
0x180185a1e  lea     rdx, [rsp+218h+var_1E8]
0x180185a23  lea     rcx, [rsp+218h+var_198]
0x180185a2b  call    ??0?$async_iterable@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@param@winrt@@QEAA@V?$initializer_list@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@std@@@Z; winrt::param::async_iterable<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>::async_iterable<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>(std::initializer_list<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>)
0x180185a30  nop
0x180185a31  xorps   xmm0, xmm0
0x180185a34  movdqu  [rsp+218h+var_1C0], xmm0
0x180185a3a  mov     ecx, 20h ; ' '
0x180185a3f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180185a44  mov     [rax], rax
0x180185a47  mov     [rax+8], rax
0x180185a4b  mov     qword ptr [rsp+218h+var_1C0], rax
0x180185a50  lea     rax, [rsp+218h+var_198]
0x180185a58  mov     [rsp+218h+var_1B0], rax
0x180185a5d  lea     rax, qword_1802E5248
0x180185a64  mov     qword ptr [rsp+218h+var_1E8], rax
0x180185a69  lock add cs:qword_1802E5248, r14
0x180185a71  cmp     cs:??$factory_cache_entry_v@UStoreConfiguration@Preview@Store@ApplicationModel@Windows@winrt@@UIStoreConfigurationStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UStoreConfiguration@Preview@Store@ApplicationModel@Windows@winrt@@UIStoreConfigurationStatics@23456@@12@A, rsi; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics>
0x180185a78  jz      short loc_180185A9B
0x180185a7a  lea     r8, ??$factory_cache_entry_v@UStoreConfiguration@Preview@Store@ApplicationModel@Windows@winrt@@UIStoreConfigurationStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UStoreConfiguration@Preview@Store@ApplicationModel@Windows@winrt@@UIStoreConfigurationStatics@23456@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::StoreConfiguration,winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics>
0x180185a81  lea     rdx, [rsp+218h+var_1C8]
0x180185a86  lea     rcx, [rsp+218h+var_1B0]
0x180185a8b  call    ??R_lambda_8851844acf8991df0c80ab7dd7d65589_@@QEBA@AEBUIStoreConfigurationStatics@Preview@Store@ApplicationModel@Windows@winrt@@@Z; _lambda_8851844acf8991df0c80ab7dd7d65589_::operator()(winrt::Windows::ApplicationModel::Store::Preview::IStoreConfigurationStatics const &)
0x180185a90  nop
0x180185a91  lock dec cs:qword_1802E5248
0x180185a99  jmp     short loc_180185AB3
0x180185a9b  lock dec cs:qword_1802E5248
0x180185aa3  lea     r8, [rsp+218h+var_1B0]
0x180185aa8  lea     rdx, [rsp+218h+var_1C8]
0x180185aad  call    ??$call@AEAV_lambda_8851844acf8991df0c80ab7dd7d65589_@@@?$factory_cache_entry@UStoreConfiguration@Preview@Store@ApplicationModel@Windows@winrt@@UIStoreConfigurationStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_8851844acf8991df0c80ab7dd7d65589_@@@Z
0x180185ab2  nop
0x180185ab3  lea     rdx, [rsp+218h+var_1C8]
0x180185ab8  lea     rcx, [rsp+218h+var_1D0]; this
0x180185abd  call    ??$wait_get@U?$IAsyncOperation@U?$IVectorView@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@U?$IVectorView@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@1@@Z
0x180185ac2  nop
0x180185ac3  lea     rcx, [rsp+218h+var_1C8]; void *
0x180185ac8  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180185acd  mov     ebx, esi
0x180185acf  cmp     ebx, 23h ; '#'
0x180185ad2  jnb     loc_180185B9A
0x180185ad8  mov     edi, ebx
0x180185ada  lea     r13, off_180228050; "x86"
0x180185ae1  cmp     [r13+rdi*8+0], rsi
0x180185ae6  jz      loc_180185B92
0x180185aec  mov     [rsp+218h+var_1A0], esi
0x180185af0  mov     [rsp+218h+var_1D8], sil
0x180185af5  mov     rcx, [rsp+218h+var_1D0]
0x180185afa  mov     dword ptr [rsp+218h+var_188], esi
0x180185b01  xorps   xmm0, xmm0
0x180185b04  movdqu  [rsp+218h+var_180], xmm0
0x180185b0d  mov     rax, [rcx]
0x180185b10  lea     r9, [rsp+218h+var_1D8]
0x180185b15  lea     r8, [rsp+218h+var_1A0]
0x180185b1a  mov     edx, ebx
0x180185b1c  mov     rax, [rax+40h]
0x180185b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185b25  lea     r8, [rsp+218h+var_188]
0x180185b2d  mov     edx, eax
0x180185b2f  lea     rcx, [rsp+218h+var_1C8]
0x180185b34  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180185b39  mov     rax, [r13+rdi*8+0]
0x180185b3e  lea     rcx, [rsp+218h+var_1C0]
0x180185b43  cmp     [rsp+218h+var_1D8], sil
0x180185b48  jz      short loc_180185B6F
0x180185b4a  mov     qword ptr [rsp+218h+var_1E8], rax
0x180185b4f  mov     byte ptr [rsp+218h+var_1E8+8], r14b
0x180185b54  xor     eax, eax
0x180185b56  mov     dword ptr [rsp+218h+var_1E8+9], eax
0x180185b5a  mov     word ptr [rsp+218h+var_1E8+0Dh], ax
0x180185b5f  mov     byte ptr [rsp+218h+var_1E8+0Fh], al
0x180185b63  lea     rdx, [rsp+218h+var_1E8]
0x180185b68  call    ?push_back@?$list@UShortCode@@V?$allocator@UShortCode@@@std@@@std@@QEAAX$$QEAUShortCode@@@Z; std::list<ShortCode>::push_back(ShortCode &&)
0x180185b6d  jmp     short loc_180185B92
0x180185b6f  mov     [rsp+218h+var_1B0], rax
0x180185b74  mov     [rsp+218h+var_1A8], sil
0x180185b79  xor     eax, eax
0x180185b7b  mov     [rsp+218h+var_1A7], eax
0x180185b7f  mov     [rsp+218h+var_1A3], ax
0x180185b84  mov     [rsp+218h+var_1A1], al
0x180185b88  lea     rdx, [rsp+218h+var_1B0]
0x180185b8d  call    ?push_back@?$list@UShortCode@@V?$allocator@UShortCode@@@std@@@std@@QEAAX$$QEAUShortCode@@@Z; std::list<ShortCode>::push_back(ShortCode &&)
0x180185b92  add     ebx, r14d
0x180185b95  jmp     loc_180185ACF
0x180185b9a  lea     rcx, [rsp+218h+var_1D0]; void *
0x180185b9f  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180185ba4  nop
0x180185ba5  jmp     short loc_180185BBB
0x180185ba7  xor     esi, esi
0x180185ba9  lea     r14d, [rsi+1]
0x180185bad  lea     r15, aX86_0; "x86"
0x180185bb4  lea     r12, aX64; "x64"
0x180185bbb  lea     rax, qword_1802E60B8
0x180185bc2  mov     qword ptr [rsp+218h+var_1E8], rax
0x180185bc7  lock add cs:qword_1802E60B8, r14
0x180185bcf  cmp     cs:??$factory_cache_entry_v@UTouchCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UTouchCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rsi; factory_cache_entry<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory>
0x180185bd6  jz      short loc_180185BF4
0x180185bd8  lea     rdx, [rsp+218h+var_1B0]
0x180185bdd  lea     rcx, ??$factory_cache_entry_v@UTouchCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UTouchCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::TouchCapabilities,winrt::Windows::Foundation::IActivationFactory>
0x180185be4  call    ??$ActivateInstance@UTouchCapabilities@Input@Devices@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUTouchCapabilities@Input@Devices@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Devices::Input::TouchCapabilities>(void)
0x180185be9  nop
0x180185bea  lock dec cs:qword_1802E60B8
0x180185bf2  jmp     short loc_180185C18
0x180185bf4  lock dec cs:qword_1802E60B8
0x180185bfc  lea     rax, ?_lambda_invoker_cdecl_@_lambda_a15ff3c6ef6754699948ab76a1ac847f_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_a15ff3c6ef6754699948ab76a1ac847f_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180185c03  mov     [rsp+218h+var_1D0], rax
0x180185c08  lea     r8, [rsp+218h+var_1D0]
0x180185c0d  lea     rdx, [rsp+218h+var_1B0]
0x180185c12  call    ??$call@P6A?AUTouchCapabilities@Input@Devices@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UTouchCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUTouchCapabilities@Input@Devices@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180185c17  nop
0x180185c18  mov     [rsp+218h+var_1A0], esi
0x180185c1c  mov     rcx, [rsp+218h+var_1B0]
0x180185c21  mov     dword ptr [rsp+218h+var_188], esi
0x180185c28  xorps   xmm0, xmm0
0x180185c2b  movdqu  [rsp+218h+var_180], xmm0
0x180185c34  mov     rax, [rcx]
0x180185c37  lea     rdx, [rsp+218h+var_1A0]
0x180185c3c  mov     rax, [rax+30h]
0x180185c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185c45  lea     r8, [rsp+218h+var_188]
0x180185c4d  mov     edx, eax
0x180185c4f  lea     rcx, [rsp+218h+var_1C8]
0x180185c54  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180185c59  cmp     [rsp+218h+var_1A0], esi
0x180185c5d  setnle  al
0x180185c60  lea     rcx, aTch; "tch"
0x180185c67  mov     qword ptr [rsp+218h+var_1E8], rcx
0x180185c6c  mov     byte ptr [rsp+218h+var_1E8+8], al
0x180185c70  xor     eax, eax
0x180185c72  mov     dword ptr [rsp+218h+var_1E8+9], eax
0x180185c76  mov     word ptr [rsp+218h+var_1E8+0Dh], ax
0x180185c7b  mov     byte ptr [rsp+218h+var_1E8+0Fh], al
0x180185c7f  lea     rdx, [rsp+218h+var_1E8]
0x180185c84  lea     rcx, [rsp+218h+var_1C0]
0x180185c89  call    ?push_back@?$list@UShortCode@@V?$allocator@UShortCode@@@std@@@std@@QEAAX$$QEAUShortCode@@@Z; std::list<ShortCode>::push_back(ShortCode &&)
0x180185c8e  nop
0x180185c8f  lea     rcx, [rsp+218h+var_1B0]; void *
0x180185c94  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180185c99  nop
0x180185c9a  jmp     short loc_180185CB0
0x180185c9c  xor     esi, esi
0x180185c9e  lea     r14d, [rsi+1]
0x180185ca2  lea     r15, aX86_0; "x86"
0x180185ca9  lea     r12, aX64; "x64"
0x180185cb0  lea     rax, qword_1802E60F8
0x180185cb7  mov     qword ptr [rsp+218h+var_1E8], rax
0x180185cbc  lock add cs:qword_1802E60F8, r14
0x180185cc4  cmp     cs:??$factory_cache_entry_v@UKeyboardCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UKeyboardCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rsi; factory_cache_entry<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory>
0x180185ccb  jz      short loc_180185CE9
0x180185ccd  lea     rdx, [rsp+218h+var_1B0]
0x180185cd2  lea     rcx, ??$factory_cache_entry_v@UKeyboardCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UKeyboardCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::KeyboardCapabilities,winrt::Windows::Foundation::IActivationFactory>
0x180185cd9  call    ??$ActivateInstance@UKeyboardCapabilities@Input@Devices@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUKeyboardCapabilities@Input@Devices@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Devices::Input::KeyboardCapabilities>(void)
0x180185cde  nop
0x180185cdf  lock dec cs:qword_1802E60F8
0x180185ce7  jmp     short loc_180185D0D
0x180185ce9  lock dec cs:qword_1802E60F8
0x180185cf1  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4fc70953ad3a90d3b7ef637294af038f_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_4fc70953ad3a90d3b7ef637294af038f_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180185cf8  mov     [rsp+218h+var_1D0], rax
0x180185cfd  lea     r8, [rsp+218h+var_1D0]
0x180185d02  lea     rdx, [rsp+218h+var_1B0]
0x180185d07  call    ??$call@P6A?AUKeyboardCapabilities@Input@Devices@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UKeyboardCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUKeyboardCapabilities@Input@Devices@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180185d0c  nop
0x180185d0d  mov     [rsp+218h+var_1A0], esi
0x180185d11  mov     rcx, [rsp+218h+var_1B0]
0x180185d16  mov     dword ptr [rsp+218h+var_188], esi
0x180185d1d  xorps   xmm0, xmm0
0x180185d20  movdqu  [rsp+218h+var_180], xmm0
0x180185d29  mov     rax, [rcx]
0x180185d2c  lea     rdx, [rsp+218h+var_1A0]
0x180185d31  mov     rax, [rax+30h]
0x180185d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185d3a  lea     r8, [rsp+218h+var_188]
0x180185d42  mov     edx, eax
0x180185d44  lea     rcx, [rsp+218h+var_1C8]
0x180185d49  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180185d4e  cmp     [rsp+218h+var_1A0], esi
0x180185d52  setnle  al
0x180185d55  lea     rcx, aKbd; "kbd"
0x180185d5c  mov     qword ptr [rsp+218h+var_1E8], rcx
0x180185d61  mov     byte ptr [rsp+218h+var_1E8+8], al
0x180185d65  xor     eax, eax
0x180185d67  mov     dword ptr [rsp+218h+var_1E8+9], eax
0x180185d6b  mov     word ptr [rsp+218h+var_1E8+0Dh], ax
0x180185d70  mov     byte ptr [rsp+218h+var_1E8+0Fh], al
0x180185d74  lea     rdx, [rsp+218h+var_1E8]
0x180185d79  lea     rcx, [rsp+218h+var_1C0]
0x180185d7e  call    ?push_back@?$list@UShortCode@@V?$allocator@UShortCode@@@std@@@std@@QEAAX$$QEAUShortCode@@@Z; std::list<ShortCode>::push_back(ShortCode &&)
0x180185d83  nop
0x180185d84  lea     rcx, [rsp+218h+var_1B0]; void *
0x180185d89  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180185d8e  nop
0x180185d8f  jmp     short loc_180185DA5
0x180185d91  xor     esi, esi
0x180185d93  lea     r14d, [rsi+1]
0x180185d97  lea     r15, aX86_0; "x86"
0x180185d9e  lea     r12, aX64; "x64"
0x180185da5  lea     rax, qword_1802E60D8
0x180185dac  mov     qword ptr [rsp+218h+var_1E8], rax
0x180185db1  lock add cs:qword_1802E60D8, r14
0x180185db9  cmp     cs:??$factory_cache_entry_v@UMouseCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UMouseCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rsi; factory_cache_entry<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory>
0x180185dc0  jz      short loc_180185DDE
0x180185dc2  lea     rdx, [rsp+218h+var_1B0]
0x180185dc7  lea     rcx, ??$factory_cache_entry_v@UMouseCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UMouseCapabilities@Input@Devices@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Input::MouseCapabilities,winrt::Windows::Foundation::IActivationFactory>
0x180185dce  call    ??$ActivateInstance@UMouseCapabilities@Input@Devices@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUMouseCapabilities@Input@Devices@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Devices::Input::MouseCapabilities>(void)
0x180185dd3  nop
0x180185dd4  lock dec cs:qword_1802E60D8
0x180185ddc  jmp     short loc_180185E02
0x180185dde  lock dec cs:qword_1802E60D8
0x180185de6  lea     rax, ?_lambda_invoker_cdecl_@_lambda_a210ed02b6ad0116de4a668d69060f7b_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_a210ed02b6ad0116de4a668d69060f7b_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180185ded  mov     [rsp+218h+var_1D0], rax
0x180185df2  lea     r8, [rsp+218h+var_1D0]
  ... truncated ...
```
