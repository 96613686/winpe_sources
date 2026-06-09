# _ModernDeployment::Autopilot::Core::AutopilotUtilities::GetQrCodeImageAsync_::_3_::_lambda_1_::operator()

- ea: `0x1800991f8`
- end: `0x180099da7`
- name: `_ModernDeployment::Autopilot::Core::AutopilotUtilities::GetQrCodeImageAsync_::_3_::_lambda_1_::operator()`
- size: `2991`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009be30`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x1800853a0`
- `0x1800889a0`
- `0x180095b70`
- `0x1800991f8`
- `0x18009bef4`
- `0x1800a0084`
- `0x180134e6c`
- `0x1801360c4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180099381`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180099381`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009951a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180099ac6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009951a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180099ac6`

## string_xrefs

- `0x180099360`: `Windows.Storage.Streams.InMemoryRandomAccessStream`
- `0x180099a9b`: `Windows.Storage.Streams.RandomAccessStreamReference`
- `0x1800994f2`: `Windows.Storage.Streams.DataWriter`
- `0x180099274`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x1800992cb`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099318`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099398`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009940b`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099489`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099531`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x1800995c4`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009964e`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x1800996e3`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009977f`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099813`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x1800998b2`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009995d`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099a03`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099ae1`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099baa`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x180099c63`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`

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
  v4 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(a1 + 8, (__int64)v58);
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
0x1800991f8  mov     [rsp+arg_10], rbx
0x1800991fd  push    rdi
0x1800991fe  push    r14
0x180099200  push    r15
0x180099202  sub     rsp, 0D0h
0x180099209  mov     rax, cs:__security_cookie
0x180099210  xor     rax, rsp
0x180099213  mov     [rsp+0E8h+var_20], rax
0x18009921b  mov     r14, rdx
0x18009921e  mov     rbx, rcx
0x180099221  xor     edx, edx
0x180099223  mov     rcx, r14
0x180099226  call    ?Set@?$CMarshaledInterfaceResult@UIRandomAccessStreamReference@Streams@Storage@Windows@@@Internal@Windows@@QEAAJPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStreamReference>::Set(Windows::Storage::Streams::IRandomAccessStreamReference *)
0x18009922b  xorps   xmm0, xmm0
0x18009922e  movups  [rsp+0E8h+var_60], xmm0
0x180099236  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18009923e  movdqu  [rsp+0E8h+var_50], xmm1
0x180099247  xor     r15d, r15d
0x18009924a  mov     byte ptr [rsp+0E8h+var_60], r15b
0x180099252  lea     rcx, [rbx+8]
0x180099256  lea     rdx, [rsp+0E8h+var_60]
0x18009925e  call    ?UnicodeToUtf8@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(std::wstring const &,std::string &)
0x180099263  mov     ebx, eax
0x180099265  test    eax, eax
0x180099267  jns     short loc_18009929A
0x180099269  mov     rcx, [rsp+0E8h]; this
0x180099271  mov     r9d, eax; char *
0x180099274  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009927b  mov     edx, 0BBh; void *
0x180099280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099285  nop
0x180099286  lea     rcx, [rsp+0E8h+var_60]
0x18009928e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099293  mov     eax, ebx
0x180099295  jmp     loc_180099D81
0x18009929a  xorps   xmm0, xmm0
0x18009929d  movdqu  [rsp+0E8h+var_90], xmm0
0x1800992a3  mov     [rsp+0E8h+var_80], r15
0x1800992a8  lea     r8, [rsp+0E8h+var_90]
0x1800992ad  lea     rcx, [rsp+0E8h+var_60]
0x1800992b5  call    ?GenerateQrCodeAsPng@NayukiEncoder@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ErrorCorrectionMode@1234@AEAV?$vector@EV?$allocator@E@std@@@6@@Z; ModernDeployment::Autopilot::Core::NayukiEncoder::GenerateQrCodeAsPng(std::string const &,ModernDeployment::Autopilot::Core::NayukiEncoder::ErrorCorrectionMode,std::vector<uchar> &)
0x1800992ba  mov     ebx, eax
0x1800992bc  test    eax, eax
0x1800992be  jns     short loc_1800992FC
0x1800992c0  mov     rcx, [rsp+0E8h]; this
0x1800992c8  mov     r9d, eax; char *
0x1800992cb  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800992d2  mov     edx, 0BFh; void *
0x1800992d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800992dc  nop
0x1800992dd  lea     rcx, [rsp+0E8h+var_90]
0x1800992e2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800992e7  nop
0x1800992e8  lea     rcx, [rsp+0E8h+var_60]
0x1800992f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800992f5  mov     eax, ebx
0x1800992f7  jmp     loc_180099D81
0x1800992fc  mov     rbx, qword ptr [rsp+0E8h+var_90+8]
0x180099301  cmp     qword ptr [rsp+0E8h+var_90], rbx
0x180099306  jnz     short loc_180099349
0x180099308  mov     rcx, [rsp+0E8h]; this
0x180099310  mov     ebx, 80004005h
0x180099315  mov     r9d, ebx; char *
0x180099318  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009931f  mov     edx, 0C0h; void *
0x180099324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099329  nop
0x18009932a  lea     rcx, [rsp+0E8h+var_90]
0x18009932f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180099334  nop
0x180099335  lea     rcx, [rsp+0E8h+var_60]
0x18009933d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099342  mov     eax, ebx
0x180099344  jmp     loc_180099D81
0x180099349  mov     [rsp+0E8h+var_C0], r15
0x18009934e  mov     [rsp+0E8h+var_28], r15
0x180099356  mov     r9d, 32h ; '2'; unsigned int
0x18009935c  lea     r8d, [r9+1]; unsigned int
0x180099360  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_InMemoryRandomAccessStream@@3QBGB; "Windows.Storage.Streams.InMemoryRandomA"...
0x180099367  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18009936f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099374  lea     rdx, [rsp+0E8h+var_C0]
0x180099379  mov     rcx, [rsp+0E8h+var_28]
0x180099381  call    cs:__imp_RoActivateInstance
0x180099387  mov     edi, eax
0x180099389  test    eax, eax
0x18009938b  jns     short loc_1800993D4
0x18009938d  mov     rcx, [rsp+0E8h]; this
0x180099395  mov     r9d, eax; char *
0x180099398  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009939f  mov     edx, 0C5h; void *
0x1800993a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800993a9  nop
0x1800993aa  lea     rcx, [rsp+0E8h+var_C0]
0x1800993af  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800993b4  nop
0x1800993b5  lea     rcx, [rsp+0E8h+var_90]
0x1800993ba  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800993bf  nop
0x1800993c0  lea     rcx, [rsp+0E8h+var_60]
0x1800993c8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800993cd  mov     eax, edi
0x1800993cf  jmp     loc_180099D81
0x1800993d4  mov     qword ptr [rsp+0E8h+var_C8], r15
0x1800993d9  mov     rcx, [rsp+0E8h+var_C0]
0x1800993de  mov     rax, [rcx]
0x1800993e1  mov     qword ptr [rsp+0E8h+var_C8], r15; int
0x1800993e6  lea     r8, [rsp+0E8h+var_C8]
0x1800993eb  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800993f2  mov     rax, [rax]
0x1800993f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800993fa  mov     edi, eax
0x1800993fc  test    eax, eax
0x1800993fe  jns     short loc_180099452
0x180099400  mov     rcx, [rsp+0E8h]; this
0x180099408  mov     r9d, eax; char *
0x18009940b  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x180099412  mov     edx, 0C8h; void *
0x180099417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009941c  nop
0x18009941d  lea     rcx, [rsp+0E8h+var_C8]
0x180099422  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099427  nop
0x180099428  lea     rcx, [rsp+0E8h+var_C0]
0x18009942d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099432  nop
0x180099433  lea     rcx, [rsp+0E8h+var_90]
0x180099438  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009943d  nop
0x18009943e  lea     rcx, [rsp+0E8h+var_60]
0x180099446  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009944b  mov     eax, edi
0x18009944d  jmp     loc_180099D81
0x180099452  mov     [rsp+0E8h+var_B0], r15
0x180099457  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x18009945c  mov     rax, [rcx]
0x18009945f  mov     [rsp+0E8h+var_B0], r15
0x180099464  lea     r8, [rsp+0E8h+var_B0]
0x180099469  lea     rdx, _GUID_905a0fe6_bc53_11df_8c49_001e4fc686da
0x180099470  mov     rax, [rax]
0x180099473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099478  mov     edi, eax
0x18009947a  test    eax, eax
0x18009947c  jns     short loc_1800994DB
0x18009947e  mov     rcx, [rsp+0E8h]; this
0x180099486  mov     r9d, eax; char *
0x180099489  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x180099490  mov     edx, 0CBh; void *
0x180099495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009949a  nop
0x18009949b  lea     rcx, [rsp+0E8h+var_B0]
0x1800994a0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800994a5  nop
0x1800994a6  lea     rcx, [rsp+0E8h+var_C8]
0x1800994ab  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800994b0  nop
0x1800994b1  lea     rcx, [rsp+0E8h+var_C0]
0x1800994b6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800994bb  nop
0x1800994bc  lea     rcx, [rsp+0E8h+var_90]
0x1800994c1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800994c6  nop
0x1800994c7  lea     rcx, [rsp+0E8h+var_60]
0x1800994cf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800994d4  mov     eax, edi
0x1800994d6  jmp     loc_180099D81
0x1800994db  mov     [rsp+0E8h+var_A8], r15
0x1800994e0  mov     [rsp+0E8h+var_28], r15
0x1800994e8  mov     r9d, 22h ; '"'; unsigned int
0x1800994ee  lea     r8d, [r9+1]; unsigned int
0x1800994f2  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x1800994f9  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x180099501  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099506  lea     r8, [rsp+0E8h+var_A8]
0x18009950b  lea     rdx, _GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f
0x180099512  mov     rcx, [rsp+0E8h+var_28]
0x18009951a  call    cs:__imp_RoGetActivationFactory
0x180099520  mov     edi, eax
0x180099522  test    eax, eax
0x180099524  jns     short loc_18009958E
0x180099526  mov     rcx, [rsp+0E8h]; this
0x18009952e  mov     r9d, eax; char *
0x180099531  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x180099538  mov     edx, 0D0h; void *
0x18009953d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099542  nop
0x180099543  lea     rcx, [rsp+0E8h+var_A8]
0x180099548  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009954d  nop
0x18009954e  lea     rcx, [rsp+0E8h+var_B0]
0x180099553  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099558  nop
0x180099559  lea     rcx, [rsp+0E8h+var_C8]
0x18009955e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099563  nop
0x180099564  lea     rcx, [rsp+0E8h+var_C0]
0x180099569  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009956e  nop
0x18009956f  lea     rcx, [rsp+0E8h+var_90]
0x180099574  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180099579  nop
0x18009957a  lea     rcx, [rsp+0E8h+var_60]
0x180099582  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099587  mov     eax, edi
0x180099589  jmp     loc_180099D81
0x18009958e  mov     [rsp+0E8h+var_B8], r15
0x180099593  mov     rcx, [rsp+0E8h+var_A8]
0x180099598  mov     rax, [rcx]
0x18009959b  mov     [rsp+0E8h+var_B8], r15
0x1800995a0  lea     r8, [rsp+0E8h+var_B8]
0x1800995a5  mov     rdx, [rsp+0E8h+var_B0]
0x1800995aa  mov     rax, [rax+30h]
0x1800995ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800995b3  mov     edi, eax
0x1800995b5  test    eax, eax
0x1800995b7  jns     short loc_18009962C
0x1800995b9  mov     rcx, [rsp+0E8h]; this
0x1800995c1  mov     r9d, eax; char *
0x1800995c4  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800995cb  mov     edx, 0D3h; void *
0x1800995d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800995d5  nop
0x1800995d6  lea     rcx, [rsp+0E8h+var_B8]
0x1800995db  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800995e0  nop
0x1800995e1  lea     rcx, [rsp+0E8h+var_A8]
0x1800995e6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800995eb  nop
0x1800995ec  lea     rcx, [rsp+0E8h+var_B0]
0x1800995f1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800995f6  nop
0x1800995f7  lea     rcx, [rsp+0E8h+var_C8]
0x1800995fc  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099601  nop
0x180099602  lea     rcx, [rsp+0E8h+var_C0]
0x180099607  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009960c  nop
0x18009960d  lea     rcx, [rsp+0E8h+var_90]
0x180099612  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180099617  nop
0x180099618  lea     rcx, [rsp+0E8h+var_60]
0x180099620  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099625  mov     eax, edi
0x180099627  jmp     loc_180099D81
0x18009962c  mov     rax, rbx
0x18009962f  sub     rax, qword ptr [rsp+0E8h+var_90]
0x180099634  mov     edi, 0FFFFFFFFh
0x180099639  cmp     rax, rdi
0x18009963c  jbe     short loc_1800996B6
0x18009963e  mov     rcx, [rsp+0E8h]; this
0x180099646  mov     ebx, 80004005h
0x18009964b  mov     r9d, ebx; char *
0x18009964e  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x180099655  mov     edx, 0D5h; void *
0x18009965a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009965f  nop
0x180099660  lea     rcx, [rsp+0E8h+var_B8]
0x180099665  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009966a  nop
0x18009966b  lea     rcx, [rsp+0E8h+var_A8]
0x180099670  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099675  nop
0x180099676  lea     rcx, [rsp+0E8h+var_B0]
0x18009967b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099680  nop
0x180099681  lea     rcx, [rsp+0E8h+var_C8]
0x180099686  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009968b  nop
0x18009968c  lea     rcx, [rsp+0E8h+var_C0]
0x180099691  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180099696  nop
0x180099697  lea     rcx, [rsp+0E8h+var_90]
0x18009969c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800996a1  nop
0x1800996a2  lea     rcx, [rsp+0E8h+var_60]
0x1800996aa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800996af  mov     eax, ebx
0x1800996b1  jmp     loc_180099D81
0x1800996b6  mov     rcx, [rsp+0E8h+var_B8]
0x1800996bb  mov     rax, [rcx]
0x1800996be  sub     ebx, dword ptr [rsp+0E8h+var_90]
0x1800996c2  mov     r8, qword ptr [rsp+0E8h+var_90]
0x1800996c7  mov     edx, ebx
0x1800996c9  mov     rax, [rax+60h]
0x1800996cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996d2  mov     ebx, eax
0x1800996d4  test    eax, eax
0x1800996d6  jns     short loc_18009974B
0x1800996d8  mov     rcx, [rsp+0E8h]; this
0x1800996e0  mov     r9d, eax; char *
0x1800996e3  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800996ea  mov     edx, 0D9h; void *
0x1800996ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800996f4  nop
0x1800996f5  lea     rcx, [rsp+0E8h+var_B8]
0x1800996fa  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800996ff  nop
0x180099700  lea     rcx, [rsp+0E8h+var_A8]
0x180099705  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18009970a  nop
  ... truncated ...
```
