# _ModernDeployment::Autopilot::Core::AutopilotUtilities::GetQrCodeImageAsync_::_3_::_lambda_1_::operator()

- ea: `0x18009a5e8`
- end: `0x18009b1a9`
- name: `_ModernDeployment::Autopilot::Core::AutopilotUtilities::GetQrCodeImageAsync_::_3_::_lambda_1_::operator()`
- size: `3009`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009d2d0`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x180086044`
- `0x180089850`
- `0x180096e98`
- `0x18009a5e8`
- `0x18009d394`
- `0x1800a1600`
- `0x180138d20`
- `0x18013a018`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18009a771`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18009a771`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009a910`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009aec2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009a910`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009aec2`

## string_xrefs

- `0x18009a750`: `Windows.Storage.Streams.InMemoryRandomAccessStream`
- `0x18009ae97`: `Windows.Storage.Streams.RandomAccessStreamReference`
- `0x18009a8e8`: `Windows.Storage.Streams.DataWriter`
- `0x18009a664`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a6bb`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a708`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a78e`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a801`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a87f`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a92d`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009a9c0`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009aa4a`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009aadf`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009ab7b`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009ac0f`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009acae`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009ad59`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009adff`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009aee3`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009afac`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009b065`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AutopilotUtilities::GetQrCodeImageAsync_::_3_::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2)
{
  int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  __int64 (__fastcall **v13)(_QWORD, GUID *, int *); // rax
  int v14; // eax
  unsigned int v15; // edi
  __int64 (__fastcall **v16)(_QWORD, GUID *, __int64 *); // rax
  int v17; // eax
  unsigned int v18; // edi
  int ActivationFactory; // eax
  unsigned int v20; // edi
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // ebx
  int v37; // eax
  unsigned int v38; // ebx
  int v39; // eax
  unsigned int v40; // ebx
  __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  unsigned int v45; // ebx
  int v46[2]; // [rsp+20h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, int *); // [rsp+28h] [rbp-C0h] BYREF
  __int64 *v48; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+38h] [rbp-B0h] BYREF
  __int64 *v50; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+50h] [rbp-98h] BYREF
  __int128 v53; // [rsp+58h] [rbp-90h] BYREF
  __int64 v54; // [rsp+68h] [rbp-80h]
  int v55; // [rsp+70h] [rbp-78h] BYREF
  __int64 v56; // [rsp+78h] [rbp-70h] BYREF
  __int64 *v57; // [rsp+80h] [rbp-68h] BYREF
  _OWORD v58[2]; // [rsp+88h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStreamReference>::Set(a2, 0);
  v58[0] = 0;
  v58[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v58[0]) = 0;
  v4 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(a1 + 8, v58);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v53 = 0;
    v54 = 0;
    v8 = ModernDeployment::Autopilot::Core::NayukiEncoder::GenerateQrCodeAsPng(v58, v5, &v53);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v10 = *((_QWORD *)&v53 + 1);
      if ( (_QWORD)v53 == *((_QWORD *)&v53 + 1) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
          (const char *)0x80004005LL,
          v46[0]);
        std::vector<unsigned char>::_Tidy(&v53);
        std::string::_Tidy_deallocate(v58);
        return 2147500037LL;
      }
      else
      {
        v47 = 0;
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Storage.Streams.InMemoryRandomAccessStream",
          0x33u,
          0x32u);
        v11 = RoActivateInstance(v60, &v47);
        v12 = v11;
        if ( v11 >= 0 )
        {
          *(_QWORD *)v46 = 0;
          v13 = *v47;
          *(_QWORD *)v46 = 0;
          v14 = (*v13)(v47, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, v46);
          v15 = v14;
          if ( v14 >= 0 )
          {
            v49 = 0;
            v16 = **(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v46;
            v49 = 0;
            v17 = (*v16)(*(_QWORD *)v46, &GUID_905a0fe6_bc53_11df_8c49_001e4fc686da, &v49);
            v18 = v17;
            if ( v17 >= 0 )
            {
              v50 = 0;
              v60 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.Storage.Streams.DataWriter",
                0x23u,
                0x22u);
              ActivationFactory = RoGetActivationFactory(v60, &GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f, &v50);
              v20 = ActivationFactory;
              if ( ActivationFactory >= 0 )
              {
                v48 = 0;
                v21 = *v50;
                v48 = 0;
                v22 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v21 + 48))(v50, v49, &v48);
                v23 = v22;
                if ( v22 >= 0 )
                {
                  if ( (unsigned __int64)(v10 - v53) <= 0xFFFFFFFF )
                  {
                    v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v48 + 96))(
                            v48,
                            (unsigned int)(v10 - v53),
                            v53);
                    v25 = v24;
                    if ( v24 >= 0 )
                    {
                      v51 = 0;
                      v26 = *v48;
                      v51 = 0;
                      v27 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v26 + 232))(v48, &v51);
                      v29 = v27;
                      if ( v27 >= 0 )
                      {
                        v30 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<unsigned int> *>(
                                v51,
                                v28,
                                0xFFFFFFFFLL,
                                0);
                        v31 = v30;
                        if ( v30 >= 0 )
                        {
                          v55 = 0;
                          v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 64LL))(v51, &v55);
                          v33 = v32;
                          if ( v32 >= 0 )
                          {
                            v52 = 0;
                            v34 = *v48;
                            v52 = 0;
                            v35 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v34 + 256))(v48, &v52);
                            v36 = v35;
                            if ( v35 >= 0 )
                            {
                              v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v46 + 88LL))(
                                      *(_QWORD *)v46,
                                      0);
                              v38 = v37;
                              if ( v37 >= 0 )
                              {
                                v57 = 0;
                                v60 = 0;
                                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                  &hstringHeader,
                                  L"Windows.Storage.Streams.RandomAccessStreamReference",
                                  0x34u,
                                  0x33u);
                                v39 = RoGetActivationFactory(v60, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &v57);
                                v40 = v39;
                                if ( v39 >= 0 )
                                {
                                  v56 = 0;
                                  v41 = *v57;
                                  v56 = 0;
                                  v42 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v41 + 64))(
                                          v57,
                                          *(_QWORD *)v46,
                                          &v56);
                                  v43 = v42;
                                  if ( v42 >= 0 )
                                  {
                                    v44 = Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStreamReference>::Set(
                                            a2,
                                            v56);
                                    v45 = v44;
                                    if ( v44 >= 0 )
                                    {
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v52);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                                      std::vector<unsigned char>::_Tidy(&v53);
                                      std::string::_Tidy_deallocate(v58);
                                      return 0;
                                    }
                                    else
                                    {
                                      wil::details::in1diag3::Return_Hr(
                                        retaddr,
                                        (void *)0xF1,
                                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilot"
                                                      "utilities\\autopilotutilities.cpp",
                                        (const char *)(unsigned int)v44,
                                        v46[0]);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v52);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                                      std::vector<unsigned char>::_Tidy(&v53);
                                      std::string::_Tidy_deallocate(v58);
                                      return v45;
                                    }
                                  }
                                  else
                                  {
                                    wil::details::in1diag3::Return_Hr(
                                      retaddr,
                                      (void *)0xEF,
                                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotut"
                                                    "ilities\\autopilotutilities.cpp",
                                      (const char *)(unsigned int)v42,
                                      v46[0]);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v52);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                                    std::vector<unsigned char>::_Tidy(&v53);
                                    std::string::_Tidy_deallocate(v58);
                                    return v43;
                                  }
                                }
                                else
                                {
                                  wil::details::in1diag3::Return_Hr(
                                    retaddr,
                                    (void *)0xEC,
                                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutil"
                                                  "ities\\autopilotutilities.cpp",
                                    (const char *)(unsigned int)v39,
                                    v46[0]);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v52);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                                  std::vector<unsigned char>::_Tidy(&v53);
                                  std::string::_Tidy_deallocate(v58);
                                  return v40;
                                }
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0xE9,
                                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilit"
                                                "ies\\autopilotutilities.cpp",
                                  (const char *)(unsigned int)v37,
                                  v46[0]);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v52);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                                std::vector<unsigned char>::_Tidy(&v53);
                                std::string::_Tidy_deallocate(v58);
                                return v38;
                              }
                            }
                            else
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0xE7,
                                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilitie"
                                              "s\\autopilotutilities.cpp",
                                (const char *)(unsigned int)v35,
                                v46[0]);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v52);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                              std::vector<unsigned char>::_Tidy(&v53);
                              std::string::_Tidy_deallocate(v58);
                              return v36;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0xE0,
                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\"
                                            "autopilotutilities.cpp",
                              (const char *)(unsigned int)v32,
                              v46[0]);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                            std::vector<unsigned char>::_Tidy(&v53);
                            std::string::_Tidy_deallocate(v58);
                            return v33;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xDD,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\a"
                                          "utopilotutilities.cpp",
                            (const char *)(unsigned int)v30,
                            v46[0]);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                          std::vector<unsigned char>::_Tidy(&v53);
                          std::string::_Tidy_deallocate(v58);
                          return v31;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xDC,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\aut"
                                        "opilotutilities.cpp",
                          (const char *)(unsigned int)v27,
                          v46[0]);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v51);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                        std::vector<unsigned char>::_Tidy(&v53);
                        std::string::_Tidy_deallocate(v58);
                        return v29;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xD9,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autop"
                                      "ilotutilities.cpp",
                        (const char *)(unsigned int)v24,
                        v46[0]);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                      std::vector<unsigned char>::_Tidy(&v53);
                      std::string::_Tidy_deallocate(v58);
                      return v25;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xD5,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
                      (const char *)0x80004005LL,
                      v46[0]);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                    std::vector<unsigned char>::_Tidy(&v53);
                    std::string::_Tidy_deallocate(v58);
                    return 2147500037LL;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xD3,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
                    (const char *)(unsigned int)v22,
                    v46[0]);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v48);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                  std::vector<unsigned char>::_Tidy(&v53);
                  std::string::_Tidy_deallocate(v58);
                  return v23;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD0,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
                  (const char *)(unsigned int)ActivationFactory,
                  v46[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v50);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
                std::vector<unsigned char>::_Tidy(&v53);
                std::string::_Tidy_deallocate(v58);
                return v20;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
                (const char *)(unsigned int)v17,
                v46[0]);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v49);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
              std::vector<unsigned char>::_Tidy(&v53);
              std::string::_Tidy_deallocate(v58);
              return v18;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC8,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
              (const char *)(unsigned int)v14,
              v46[0]);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v46);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
            std::vector<unsigned char>::_Tidy(&v53);
            std::string::_Tidy_deallocate(v58);
            return v15;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC5,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
            (const char *)(unsigned int)v11,
            v46[0]);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v47);
          std::vector<unsigned char>::_Tidy(&v53);
          std::string::_Tidy_deallocate(v58);
          return v12;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
        (const char *)(unsigned int)v8,
        v46[0]);
      std::vector<unsigned char>::_Tidy(&v53);
      std::string::_Tidy_deallocate(v58);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
      (const char *)(unsigned int)v4,
      v46[0]);
    std::string::_Tidy_deallocate(v58);
    return v6;
  }
}

```

## disassembly

```asm
0x18009a5e8  mov     [rsp+arg_10], rbx
0x18009a5ed  push    rdi
0x18009a5ee  push    r14
0x18009a5f0  push    r15
0x18009a5f2  sub     rsp, 0D0h
0x18009a5f9  mov     rax, cs:__security_cookie
0x18009a600  xor     rax, rsp
0x18009a603  mov     [rsp+0E8h+var_20], rax
0x18009a60b  mov     r14, rdx
0x18009a60e  mov     rbx, rcx
0x18009a611  xor     edx, edx
0x18009a613  mov     rcx, r14
0x18009a616  call    ?Set@?$CMarshaledInterfaceResult@UIRandomAccessStreamReference@Streams@Storage@Windows@@@Internal@Windows@@QEAAJPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStreamReference>::Set(Windows::Storage::Streams::IRandomAccessStreamReference *)
0x18009a61b  xorps   xmm0, xmm0
0x18009a61e  movups  [rsp+0E8h+var_60], xmm0
0x18009a626  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18009a62e  movdqu  [rsp+0E8h+var_50], xmm1
0x18009a637  xor     r15d, r15d
0x18009a63a  mov     byte ptr [rsp+0E8h+var_60], r15b
0x18009a642  lea     rcx, [rbx+8]
0x18009a646  lea     rdx, [rsp+0E8h+var_60]
0x18009a64e  call    ?UnicodeToUtf8@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(std::wstring const &,std::string &)
0x18009a653  mov     ebx, eax
0x18009a655  test    eax, eax
0x18009a657  jns     short loc_18009A68A
0x18009a659  mov     rcx, [rsp+0E8h]; this
0x18009a661  mov     r9d, eax; char *
0x18009a664  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a66b  mov     edx, 0BBh; void *
0x18009a670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a675  nop
0x18009a676  lea     rcx, [rsp+0E8h+var_60]
0x18009a67e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a683  mov     eax, ebx
0x18009a685  jmp     loc_18009B183
0x18009a68a  xorps   xmm0, xmm0
0x18009a68d  movdqu  [rsp+0E8h+var_90], xmm0
0x18009a693  mov     [rsp+0E8h+var_80], r15
0x18009a698  lea     r8, [rsp+0E8h+var_90]
0x18009a69d  lea     rcx, [rsp+0E8h+var_60]
0x18009a6a5  call    ?GenerateQrCodeAsPng@NayukiEncoder@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ErrorCorrectionMode@1234@AEAV?$vector@EV?$allocator@E@std@@@6@@Z; ModernDeployment::Autopilot::Core::NayukiEncoder::GenerateQrCodeAsPng(std::string const &,ModernDeployment::Autopilot::Core::NayukiEncoder::ErrorCorrectionMode,std::vector<uchar> &)
0x18009a6aa  mov     ebx, eax
0x18009a6ac  test    eax, eax
0x18009a6ae  jns     short loc_18009A6EC
0x18009a6b0  mov     rcx, [rsp+0E8h]; this
0x18009a6b8  mov     r9d, eax; char *
0x18009a6bb  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a6c2  mov     edx, 0BFh; void *
0x18009a6c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a6cc  nop
0x18009a6cd  lea     rcx, [rsp+0E8h+var_90]
0x18009a6d2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009a6d7  nop
0x18009a6d8  lea     rcx, [rsp+0E8h+var_60]
0x18009a6e0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a6e5  mov     eax, ebx
0x18009a6e7  jmp     loc_18009B183
0x18009a6ec  mov     rbx, qword ptr [rsp+0E8h+var_90+8]
0x18009a6f1  cmp     qword ptr [rsp+0E8h+var_90], rbx
0x18009a6f6  jnz     short loc_18009A739
0x18009a6f8  mov     rcx, [rsp+0E8h]; this
0x18009a700  mov     ebx, 80004005h
0x18009a705  mov     r9d, ebx; char *
0x18009a708  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a70f  mov     edx, 0C0h; void *
0x18009a714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a719  nop
0x18009a71a  lea     rcx, [rsp+0E8h+var_90]
0x18009a71f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009a724  nop
0x18009a725  lea     rcx, [rsp+0E8h+var_60]
0x18009a72d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a732  mov     eax, ebx
0x18009a734  jmp     loc_18009B183
0x18009a739  mov     [rsp+0E8h+var_C0], r15
0x18009a73e  mov     [rsp+0E8h+var_28], r15
0x18009a746  mov     r9d, 32h ; '2'; unsigned int
0x18009a74c  lea     r8d, [r9+1]; unsigned int
0x18009a750  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_InMemoryRandomAccessStream@@3QBGB; "Windows.Storage.Streams.InMemoryRandomA"...
0x18009a757  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18009a75f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009a764  lea     rdx, [rsp+0E8h+var_C0]
0x18009a769  mov     rcx, [rsp+0E8h+var_28]
0x18009a771  call    cs:__imp_RoActivateInstance
0x18009a778  nop     dword ptr [rax+rax+00h]
0x18009a77d  mov     edi, eax
0x18009a77f  test    eax, eax
0x18009a781  jns     short loc_18009A7CA
0x18009a783  mov     rcx, [rsp+0E8h]; this
0x18009a78b  mov     r9d, eax; char *
0x18009a78e  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a795  mov     edx, 0C5h; void *
0x18009a79a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a79f  nop
0x18009a7a0  lea     rcx, [rsp+0E8h+var_C0]
0x18009a7a5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a7aa  nop
0x18009a7ab  lea     rcx, [rsp+0E8h+var_90]
0x18009a7b0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009a7b5  nop
0x18009a7b6  lea     rcx, [rsp+0E8h+var_60]
0x18009a7be  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a7c3  mov     eax, edi
0x18009a7c5  jmp     loc_18009B183
0x18009a7ca  mov     qword ptr [rsp+0E8h+var_C8], r15
0x18009a7cf  mov     rcx, [rsp+0E8h+var_C0]
0x18009a7d4  mov     rax, [rcx]
0x18009a7d7  mov     qword ptr [rsp+0E8h+var_C8], r15; int
0x18009a7dc  lea     r8, [rsp+0E8h+var_C8]
0x18009a7e1  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18009a7e8  mov     rax, [rax]
0x18009a7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a7f0  mov     edi, eax
0x18009a7f2  test    eax, eax
0x18009a7f4  jns     short loc_18009A848
0x18009a7f6  mov     rcx, [rsp+0E8h]; this
0x18009a7fe  mov     r9d, eax; char *
0x18009a801  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a808  mov     edx, 0C8h; void *
0x18009a80d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a812  nop
0x18009a813  lea     rcx, [rsp+0E8h+var_C8]
0x18009a818  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a81d  nop
0x18009a81e  lea     rcx, [rsp+0E8h+var_C0]
0x18009a823  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a828  nop
0x18009a829  lea     rcx, [rsp+0E8h+var_90]
0x18009a82e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009a833  nop
0x18009a834  lea     rcx, [rsp+0E8h+var_60]
0x18009a83c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a841  mov     eax, edi
0x18009a843  jmp     loc_18009B183
0x18009a848  mov     [rsp+0E8h+var_B0], r15
0x18009a84d  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x18009a852  mov     rax, [rcx]
0x18009a855  mov     [rsp+0E8h+var_B0], r15
0x18009a85a  lea     r8, [rsp+0E8h+var_B0]
0x18009a85f  lea     rdx, _GUID_905a0fe6_bc53_11df_8c49_001e4fc686da
0x18009a866  mov     rax, [rax]
0x18009a869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a86e  mov     edi, eax
0x18009a870  test    eax, eax
0x18009a872  jns     short loc_18009A8D1
0x18009a874  mov     rcx, [rsp+0E8h]; this
0x18009a87c  mov     r9d, eax; char *
0x18009a87f  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a886  mov     edx, 0CBh; void *
0x18009a88b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a890  nop
0x18009a891  lea     rcx, [rsp+0E8h+var_B0]
0x18009a896  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a89b  nop
0x18009a89c  lea     rcx, [rsp+0E8h+var_C8]
0x18009a8a1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a8a6  nop
0x18009a8a7  lea     rcx, [rsp+0E8h+var_C0]
0x18009a8ac  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a8b1  nop
0x18009a8b2  lea     rcx, [rsp+0E8h+var_90]
0x18009a8b7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009a8bc  nop
0x18009a8bd  lea     rcx, [rsp+0E8h+var_60]
0x18009a8c5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a8ca  mov     eax, edi
0x18009a8cc  jmp     loc_18009B183
0x18009a8d1  mov     [rsp+0E8h+var_A8], r15
0x18009a8d6  mov     [rsp+0E8h+var_28], r15
0x18009a8de  mov     r9d, 22h ; '"'; unsigned int
0x18009a8e4  lea     r8d, [r9+1]; unsigned int
0x18009a8e8  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x18009a8ef  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18009a8f7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009a8fc  lea     r8, [rsp+0E8h+var_A8]
0x18009a901  lea     rdx, _GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f
0x18009a908  mov     rcx, [rsp+0E8h+var_28]
0x18009a910  call    cs:__imp_RoGetActivationFactory
0x18009a917  nop     dword ptr [rax+rax+00h]
0x18009a91c  mov     edi, eax
0x18009a91e  test    eax, eax
0x18009a920  jns     short loc_18009A98A
0x18009a922  mov     rcx, [rsp+0E8h]; this
0x18009a92a  mov     r9d, eax; char *
0x18009a92d  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a934  mov     edx, 0D0h; void *
0x18009a939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a93e  nop
0x18009a93f  lea     rcx, [rsp+0E8h+var_A8]
0x18009a944  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a949  nop
0x18009a94a  lea     rcx, [rsp+0E8h+var_B0]
0x18009a94f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a954  nop
0x18009a955  lea     rcx, [rsp+0E8h+var_C8]
0x18009a95a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a95f  nop
0x18009a960  lea     rcx, [rsp+0E8h+var_C0]
0x18009a965  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a96a  nop
0x18009a96b  lea     rcx, [rsp+0E8h+var_90]
0x18009a970  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009a975  nop
0x18009a976  lea     rcx, [rsp+0E8h+var_60]
0x18009a97e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009a983  mov     eax, edi
0x18009a985  jmp     loc_18009B183
0x18009a98a  mov     [rsp+0E8h+var_B8], r15
0x18009a98f  mov     rcx, [rsp+0E8h+var_A8]
0x18009a994  mov     rax, [rcx]
0x18009a997  mov     [rsp+0E8h+var_B8], r15
0x18009a99c  lea     r8, [rsp+0E8h+var_B8]
0x18009a9a1  mov     rdx, [rsp+0E8h+var_B0]
0x18009a9a6  mov     rax, [rax+30h]
0x18009a9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a9af  mov     edi, eax
0x18009a9b1  test    eax, eax
0x18009a9b3  jns     short loc_18009AA28
0x18009a9b5  mov     rcx, [rsp+0E8h]; this
0x18009a9bd  mov     r9d, eax; char *
0x18009a9c0  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009a9c7  mov     edx, 0D3h; void *
0x18009a9cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a9d1  nop
0x18009a9d2  lea     rcx, [rsp+0E8h+var_B8]
0x18009a9d7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a9dc  nop
0x18009a9dd  lea     rcx, [rsp+0E8h+var_A8]
0x18009a9e2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a9e7  nop
0x18009a9e8  lea     rcx, [rsp+0E8h+var_B0]
0x18009a9ed  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a9f2  nop
0x18009a9f3  lea     rcx, [rsp+0E8h+var_C8]
0x18009a9f8  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009a9fd  nop
0x18009a9fe  lea     rcx, [rsp+0E8h+var_C0]
0x18009aa03  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aa08  nop
0x18009aa09  lea     rcx, [rsp+0E8h+var_90]
0x18009aa0e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009aa13  nop
0x18009aa14  lea     rcx, [rsp+0E8h+var_60]
0x18009aa1c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009aa21  mov     eax, edi
0x18009aa23  jmp     loc_18009B183
0x18009aa28  mov     rax, rbx
0x18009aa2b  sub     rax, qword ptr [rsp+0E8h+var_90]
0x18009aa30  mov     edi, 0FFFFFFFFh
0x18009aa35  cmp     rax, rdi
0x18009aa38  jbe     short loc_18009AAB2
0x18009aa3a  mov     rcx, [rsp+0E8h]; this
0x18009aa42  mov     ebx, 80004005h
0x18009aa47  mov     r9d, ebx; char *
0x18009aa4a  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009aa51  mov     edx, 0D5h; void *
0x18009aa56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009aa5b  nop
0x18009aa5c  lea     rcx, [rsp+0E8h+var_B8]
0x18009aa61  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aa66  nop
0x18009aa67  lea     rcx, [rsp+0E8h+var_A8]
0x18009aa6c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aa71  nop
0x18009aa72  lea     rcx, [rsp+0E8h+var_B0]
0x18009aa77  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aa7c  nop
0x18009aa7d  lea     rcx, [rsp+0E8h+var_C8]
0x18009aa82  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aa87  nop
0x18009aa88  lea     rcx, [rsp+0E8h+var_C0]
0x18009aa8d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aa92  nop
0x18009aa93  lea     rcx, [rsp+0E8h+var_90]
0x18009aa98  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009aa9d  nop
0x18009aa9e  lea     rcx, [rsp+0E8h+var_60]
0x18009aaa6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009aaab  mov     eax, ebx
0x18009aaad  jmp     loc_18009B183
0x18009aab2  mov     rcx, [rsp+0E8h+var_B8]
0x18009aab7  mov     rax, [rcx]
0x18009aaba  sub     ebx, dword ptr [rsp+0E8h+var_90]
0x18009aabe  mov     r8, qword ptr [rsp+0E8h+var_90]
0x18009aac3  mov     edx, ebx
0x18009aac5  mov     rax, [rax+60h]
0x18009aac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aace  mov     ebx, eax
0x18009aad0  test    eax, eax
0x18009aad2  jns     short loc_18009AB47
0x18009aad4  mov     rcx, [rsp+0E8h]; this
0x18009aadc  mov     r9d, eax; char *
0x18009aadf  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009aae6  mov     edx, 0D9h; void *
0x18009aaeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009aaf0  nop
0x18009aaf1  lea     rcx, [rsp+0E8h+var_B8]
0x18009aaf6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009aafb  nop
0x18009aafc  lea     rcx, [rsp+0E8h+var_A8]
  ... truncated ...
```
