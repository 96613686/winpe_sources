# _lambda_7d27f6f46df24ccd5c9b9152a52e12d6_::operator()

- ea: `0x18009ebf4`
- end: `0x18009f311`
- name: `_lambda_7d27f6f46df24ccd5c9b9152a52e12d6_::operator()`
- size: `1821`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800be740`

## callees

- `0x180009ea0`
- `0x18000c058`
- `0x1800101f4`
- `0x18001c414`
- `0x180024720`
- `0x180037200`
- `0x180042b9c`
- `0x1800453bc`
- `0x180045588`
- `0x180047e04`
- `0x18006cc00`
- `0x180084fa8`
- `0x18008fc28`
- `0x1800909b0`
- `0x18009ebf4`
- `0x1800abf3c`
- `0x1800ac030`
- `0x1800ad5e8`
- `0x1800b1a84`
- `0x1800c893c`
- `0x1800cd008`
- `0x180215010`

## import_xrefs

- `Wldp!__imp_?WldpIsAppApprovedByPolicy@@YAJPEBG_K@Z` at `0x18009f1b8`
- `Wldp!__imp_?WldpIsAppApprovedByPolicy@@YAJPEBG_K@Z` at `0x18009f1b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ec7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009efde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ec7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009efde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f1a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f24b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f1a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f24b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f273`
- `ext-ms-win-security-srp-l1-1-0!SrpDoesPolicyAllowAppExecution` at `0x18009f138`
- `ext-ms-win-security-srp-l1-1-0!SrpDoesPolicyAllowAppExecution` at `0x18009f138`

## string_xrefs

- `0x18009f117`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x18009f2c2`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x18009f10a`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetIsAppAllowedToInstallForUserAsync::<lambda_7d27f6f46df24ccd5c9b9152a52e12d6>::operator ()`
- `0x18009f2b5`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetIsAppAllowedToInstallForUserAsync::<lambda_7d27f6f46df24ccd5c9b9152a52e12d6>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall lambda_7d27f6f46df24ccd5c9b9152a52e12d6_::operator()(
        Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *a1,
        __int64 a2)
{
  __int64 v2; // r13
  struct Windows::System::IUser **v3; // r12
  char v4; // si
  AppId *v5; // rbx
  unsigned int StoreId; // eax
  struct Windows::System::IUser *v7; // rdi
  __int64 (__fastcall *v8)(struct Windows::System::IUser *, HSTRING *); // rbx
  unsigned int v9; // eax
  __int64 AppData; // rax
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *v11; // rdx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v12; // rbx
  int DoesPolicyAllowAppExecution; // r15d
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *v14; // rdx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int IsAppApprovedByPolicy; // eax
  const unsigned __int16 *v21; // rsi
  PCWSTR v22; // rdi
  PCWSTR v23; // rbx
  PCWSTR v24; // rax
  char v26; // [rsp+70h] [rbp-2D8h] BYREF
  _BYTE v27[7]; // [rsp+71h] [rbp-2D7h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *v28; // [rsp+78h] [rbp-2D0h] BYREF
  HSTRING string; // [rsp+80h] [rbp-2C8h] BYREF
  int v30; // [rsp+88h] [rbp-2C0h] BYREF
  HSTRING v31; // [rsp+90h] [rbp-2B8h] BYREF
  __int64 v32; // [rsp+98h] [rbp-2B0h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-2A8h] BYREF
  _BYTE v34[8]; // [rsp+A8h] [rbp-2A0h] BYREF
  _BYTE v35[8]; // [rsp+B0h] [rbp-298h] BYREF
  _BYTE v36[8]; // [rsp+B8h] [rbp-290h] BYREF
  _BYTE v37[8]; // [rsp+C0h] [rbp-288h] BYREF
  struct Windows::System::IUser **v38; // [rsp+C8h] [rbp-280h]
  __int64 v39; // [rsp+D0h] [rbp-278h]
  __int64 v40; // [rsp+D8h] [rbp-270h] BYREF
  __int128 v41; // [rsp+E0h] [rbp-268h]
  __int128 v42; // [rsp+F8h] [rbp-250h] BYREF
  __int128 v43; // [rsp+108h] [rbp-240h]
  __int128 v44; // [rsp+118h] [rbp-230h]
  const winrt::hresult_error *v45; // [rsp+128h] [rbp-220h] BYREF
  _QWORD v46[4]; // [rsp+130h] [rbp-218h] BYREF
  _QWORD v47[4]; // [rsp+150h] [rbp-1F8h] BYREF
  _QWORD v48[4]; // [rsp+170h] [rbp-1D8h] BYREF
  _QWORD v49[4]; // [rsp+190h] [rbp-1B8h] BYREF
  _BYTE v50[32]; // [rsp+1B0h] [rbp-198h] BYREF
  HSTRING v51; // [rsp+1D0h] [rbp-178h] BYREF
  char v52[144]; // [rsp+1F0h] [rbp-158h] BYREF
  char v53[144]; // [rsp+280h] [rbp-C8h] BYREF

  v2 = a2;
  v3 = (struct Windows::System::IUser **)a1;
  v38 = (struct Windows::System::IUser **)a1;
  v39 = a2;
  v4 = 1;
  v30 = 1;
  v32 = 0;
  if ( Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(a1) )
  {
    string = 0;
    LODWORD(v40) = 0;
    v41 = 0;
    v5 = v3[3];
    WindowsDeleteString(0);
    string = 0;
    StoreId = AppId::get_StoreId(v5, &string);
    try
    {
      winrt::check_hresult(&v28, StoreId, &v40);
      v31 = 0;
      LODWORD(v40) = 0;
      v41 = 0;
      v7 = *v3;
      v8 = *(__int64 (__fastcall **)(struct Windows::System::IUser *, HSTRING *))(*(_QWORD *)*v3 + 128LL);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v31);
      v9 = v8(v7, &v31);
      winrt::check_hresult(&v28, v9, &v40);
      LODWORD(v8) = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                      *v3,
                      v37);
      v40 = *(_QWORD *)GetCvString(v36, v3[4]);
      v46[0] = 0;
      v47[0] = 0;
      v48[0] = 0;
      v28 = (struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *)string;
      v49[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v35, &v28);
      winrt::param::hstring::hstring((winrt::param::hstring *)v50, L"StoreId");
      v51 = v31;
      *(_QWORD *)&v42 = *(_QWORD *)GetSidForIUser(v34, v3[2]);
      AppData = winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::GetAppData(
                  (_DWORD)v8,
                  (unsigned int)&v33,
                  (unsigned int)&v42,
                  (unsigned int)&v51,
                  (__int64)v50,
                  (__int64)v49,
                  (__int64)v48,
                  (__int64)v47,
                  (__int64)v46,
                  (__int64)&v40);
      winrt::Windows::Foundation::IUnknown::as<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(
        AppData,
        &v28);
      if ( v33 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v33);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v34);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v35);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v36);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v37);
      v11 = v28;
      v28 = 0;
      Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>::Attach(&v32, v11);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v28);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v31);
      WindowsDeleteString(string);
    }
    catch ( const winrt::hresult_error *v45 )
    {
      LODWORD(v28) = *((_DWORD *)v45 + 3);
      v4 = 1;
      DoesPolicyAllowAppExecution = (int)v28;
      v3 = v38;
      v2 = v39;
      goto LABEL_7;
    }
  }
  else
  {
    v28 = 0;
    v12 = *v3;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
    DoesPolicyAllowAppExecution = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::GetAppData(
                                    v12,
                                    v3[2],
                                    v3[3],
                                    v3[4],
                                    &v28);
    v14 = v28;
    v28 = 0;
    Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>::Attach(&v32, v14);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
LABEL_7:
    if ( DoesPolicyAllowAppExecution < 0 )
      goto LABEL_27;
  }
  v26 = 0;
  v15 = v32;
  DoesPolicyAllowAppExecution = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v32 + 224LL))(v32, &v26);
  if ( DoesPolicyAllowAppExecution < 0 )
    goto LABEL_27;
  if ( !v26 )
  {
    v27[0] = 0;
    DoesPolicyAllowAppExecution = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 232LL))(v15, v27);
    if ( DoesPolicyAllowAppExecution >= 0 && v27[0] )
    {
      v31 = 0;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 104LL);
      WindowsDeleteString(0);
      v31 = 0;
      DoesPolicyAllowAppExecution = v16(v15, &v31);
      if ( DoesPolicyAllowAppExecution >= 0 )
      {
        if ( !(unsigned __int8)IsSrpDoesPolicyAllowAppExecutionPresent() )
          goto LABEL_18;
        string = 0;
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        DoesPolicyAllowAppExecution = v17(v15, &string);
        if ( DoesPolicyAllowAppExecution >= 0 )
        {
          v42 = 0;
          v43 = 0;
          v44 = 0;
          *(_QWORD *)&v43 = WindowsGetStringRawBuffer(string, 0);
          *((_QWORD *)&v43 + 1) = WindowsGetStringRawBuffer(v31, 0);
          *((_QWORD *)&v42 + 1) = 1;
          TraceLoggingCorrelationVector::ToStringImpl(
            v3[4],
            _InterlockedExchangeAdd64((volatile signed __int64 *)v3[4] + 17, 0),
            v52);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
            0xAEAu,
            "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetIsAppAllowedToInstallF"
            "orUserAsync::<lambda_7d27f6f46df24ccd5c9b9152a52e12d6>::operator ()",
            -1,
            L"SrpDoesPolicyAllowAppExecution(%s, %s), CV = %hs",
            0,
            0,
            v43,
            v52);
          DoesPolicyAllowAppExecution = SrpDoesPolicyAllowAppExecution(&v42, &v30);
        }
        WindowsDeleteString(string);
        if ( DoesPolicyAllowAppExecution >= 0 )
        {
LABEL_18:
          if ( v30 == 1 )
          {
            string = 0;
            v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 64LL);
            WindowsDeleteString(0);
            string = 0;
            DoesPolicyAllowAppExecution = v18(v15, &string);
            if ( DoesPolicyAllowAppExecution >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              IsAppApprovedByPolicy = WldpIsAppApprovedByPolicy(StringRawBuffer, 0xFFFFFFFFFFFFFFFEuLL);
              if ( IsAppApprovedByPolicy >= 0 )
              {
                DoesPolicyAllowAppExecution = IsAppApprovedByPolicy;
              }
              else
              {
                v30 = 0;
                DoesPolicyAllowAppExecution = 0;
                if ( IsAppApprovedByPolicy != -790036478 )
                  DoesPolicyAllowAppExecution = IsAppApprovedByPolicy;
              }
            }
            WindowsDeleteString(string);
          }
        }
      }
      WindowsDeleteString(v31);
    }
LABEL_27:
    if ( v30 == 1 )
      goto LABEL_29;
    goto LABEL_28;
  }
  v30 = 0;
  DoesPolicyAllowAppExecution = 0;
LABEL_28:
  v4 = 0;
LABEL_29:
  *(_BYTE *)(v2 + 16) = v4;
  TraceLoggingCorrelationVector::ToStringImpl(
    v3[4],
    _InterlockedExchangeAdd64((volatile signed __int64 *)v3[4] + 17, 0),
    v53);
  v21 = L"true";
  if ( !v30 )
    v21 = L"false";
  v22 = WindowsGetStringRawBuffer(*((HSTRING *)v3[3] + 10), 0);
  v23 = WindowsGetStringRawBuffer(*((HSTRING *)v3[3] + 9), 0);
  v24 = WindowsGetStringRawBuffer(*((HSTRING *)v3[3] + 8), 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0xB1Au,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetIsAppAllowedToInstallForUserAs"
    "ync::<lambda_7d27f6f46df24ccd5c9b9152a52e12d6>::operator ()",
    DoesPolicyAllowAppExecution,
    L"result: productId = %s, skuId = %s, catalogId = %s, CV = %hs, allowed = %s",
    0,
    0,
    v24,
    v23,
    v22,
    v53,
    v21);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  return (unsigned int)DoesPolicyAllowAppExecution;
}

```

## disassembly

```asm
0x18009ebf4  mov     [rsp+arg_10], rbx
0x18009ebf9  mov     [rsp+arg_18], rsi
0x18009ebfe  push    rdi
0x18009ebff  push    r12
0x18009ec01  push    r13
0x18009ec03  push    r14
0x18009ec05  push    r15
0x18009ec07  sub     rsp, 320h
0x18009ec0e  mov     rax, cs:__security_cookie
0x18009ec15  xor     rax, rsp
0x18009ec18  mov     [rsp+348h+var_38], rax
0x18009ec20  mov     r13, rdx
0x18009ec23  mov     r12, rcx
0x18009ec26  mov     [rsp+348h+var_280], rcx
0x18009ec2e  mov     [rsp+348h+var_278], rdx
0x18009ec36  mov     esi, 1
0x18009ec3b  mov     [rsp+348h+var_2C0], esi
0x18009ec42  xor     r14d, r14d
0x18009ec45  mov     [rsp+348h+var_2B0], r14
0x18009ec4d  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x18009ec52  test    al, al
0x18009ec54  jz      loc_18009EEF3
0x18009ec5a  mov     [rsp+348h+string], r14
0x18009ec62  mov     dword ptr [rsp+348h+var_270], r14d
0x18009ec6a  xorps   xmm0, xmm0
0x18009ec6d  movdqu  [rsp+348h+var_268], xmm0
0x18009ec76  mov     rbx, [r12+18h]
0x18009ec7b  xor     ecx, ecx; string
0x18009ec7d  call    cs:__imp_WindowsDeleteString
0x18009ec83  mov     [rsp+348h+string], r14
0x18009ec8b  lea     rdx, [rsp+348h+string]; HSTRING *
0x18009ec93  mov     rcx, rbx; this
0x18009ec96  call    ?get_StoreId@AppId@@QEBAJPEAPEAUHSTRING__@@@Z; AppId::get_StoreId(HSTRING__ * *)
0x18009ec9b  lea     r8, [rsp+348h+var_270]
0x18009eca3  mov     edx, eax
0x18009eca5  lea     rcx, [rsp+348h+var_2D0]
0x18009ecaa  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18009ecaf  mov     [rsp+348h+var_2B8], r14
0x18009ecb7  mov     dword ptr [rsp+348h+var_270], r14d
0x18009ecbf  xorps   xmm0, xmm0
0x18009ecc2  movdqu  [rsp+348h+var_268], xmm0
0x18009eccb  mov     rdi, [r12]
0x18009eccf  mov     rax, [rdi]
0x18009ecd2  mov     rbx, [rax+80h]
0x18009ecd9  lea     rcx, [rsp+348h+var_2B8]
0x18009ece1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18009ece6  lea     rdx, [rsp+348h+var_2B8]
0x18009ecee  mov     rcx, rdi
0x18009ecf1  mov     rax, rbx
0x18009ecf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecf9  lea     r8, [rsp+348h+var_270]
0x18009ed01  mov     edx, eax
0x18009ed03  lea     rcx, [rsp+348h+var_2D0]
0x18009ed08  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18009ed0d  lea     rdx, [rsp+348h+var_288]
0x18009ed15  mov     rcx, [r12]
0x18009ed19  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x18009ed1e  mov     rbx, rax
0x18009ed21  mov     rdx, [r12+20h]
0x18009ed26  lea     rcx, [rsp+348h+var_290]
0x18009ed2e  call    ?GetCvString@@YA?AUhstring@winrt@@PEAVTraceLoggingCorrelationVector@@@Z; GetCvString(TraceLoggingCorrelationVector *)
0x18009ed33  nop
0x18009ed34  mov     rcx, [rax]
0x18009ed37  mov     [rsp+348h+var_270], rcx
0x18009ed3f  mov     [rsp+348h+var_218], r14
0x18009ed47  mov     [rsp+348h+var_1F8], r14
0x18009ed4f  mov     [rsp+348h+var_1D8], r14
0x18009ed57  mov     rax, [rsp+348h+string]
0x18009ed5f  mov     [rsp+348h+var_2D0], rax
0x18009ed64  lea     rdx, [rsp+348h+var_2D0]
0x18009ed69  lea     rcx, [rsp+348h+var_298]
0x18009ed71  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x18009ed76  nop
0x18009ed77  mov     rax, [rax]
0x18009ed7a  mov     [rsp+348h+var_1B8], rax
0x18009ed82  lea     rdx, aStoreid_0; "StoreId"
0x18009ed89  lea     rcx, [rsp+348h+var_198]; this
0x18009ed91  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18009ed96  mov     rax, [rsp+348h+var_2B8]
0x18009ed9e  mov     [rsp+348h+var_178], rax
0x18009eda6  mov     rdx, [r12+10h]
0x18009edab  lea     rcx, [rsp+348h+var_2A0]
0x18009edb3  call    ?GetSidForIUser@@YA?AUhstring@winrt@@PEAUIUser@System@Windows@@@Z; GetSidForIUser(Windows::System::IUser *)
0x18009edb8  nop
0x18009edb9  mov     rax, [rax]
0x18009edbc  mov     qword ptr [rsp+348h+var_250], rax
0x18009edc4  lea     rax, [rsp+348h+var_270]
0x18009edcc  mov     qword ptr [rsp+348h+var_308+8], rax
0x18009edd1  lea     rax, [rsp+348h+var_218]
0x18009edd9  mov     qword ptr [rsp+348h+var_308], rax
0x18009edde  lea     rax, [rsp+348h+var_1F8]
0x18009ede6  mov     [rsp+348h+var_310], rax
0x18009edeb  lea     rax, [rsp+348h+var_1D8]
0x18009edf3  mov     [rsp+348h+var_318], rax
0x18009edf8  lea     rax, [rsp+348h+var_1B8]
0x18009ee00  mov     [rsp+348h+var_320], rax
0x18009ee05  lea     rax, [rsp+348h+var_198]
0x18009ee0d  mov     [rsp+348h+var_328], rax
0x18009ee12  lea     r9, [rsp+348h+var_178]
0x18009ee1a  lea     r8, [rsp+348h+var_250]
0x18009ee22  lea     rdx, [rsp+348h+var_2A8]
0x18009ee2a  mov     rcx, rbx
0x18009ee2d  call    ?GetAppData@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0000000@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::GetAppData(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x18009ee32  nop
0x18009ee33  lea     rdx, [rsp+348h+var_2D0]
0x18009ee38  mov     rcx, rax
0x18009ee3b  call    ??$as@UIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18009ee40  nop
0x18009ee41  cmp     [rsp+348h+var_2A8], r14
0x18009ee49  jz      short loc_18009EE59
0x18009ee4b  lea     rcx, [rsp+348h+var_2A8]
0x18009ee53  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18009ee58  nop
0x18009ee59  lea     rcx, [rsp+348h+var_2A0]
0x18009ee61  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18009ee66  nop
0x18009ee67  lea     rcx, [rsp+348h+var_298]
0x18009ee6f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18009ee74  nop
0x18009ee75  lea     rcx, [rsp+348h+var_290]
0x18009ee7d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18009ee82  nop
0x18009ee83  lea     rcx, [rsp+348h+var_288]; void *
0x18009ee8b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18009ee90  mov     rdx, [rsp+348h+var_2D0]
0x18009ee95  mov     [rsp+348h+var_2D0], r14
0x18009ee9a  lea     rcx, [rsp+348h+var_2B0]
0x18009eea2  call    ?Attach@?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@QEAAXPEAVInstallItem@Internal@WindowsUpdate@@@Z; Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>::Attach(WindowsUpdate::Internal::InstallItem *)
0x18009eea7  lea     rcx, [rsp+348h+var_2D0]; void *
0x18009eeac  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18009eeb1  nop
0x18009eeb2  lea     rcx, [rsp+348h+var_2B8]
0x18009eeba  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18009eebf  nop
0x18009eec0  mov     rcx, [rsp+348h+string]; string
0x18009eec8  call    cs:__imp_WindowsDeleteString
0x18009eece  nop
0x18009eecf  jmp     loc_18009EF55
0x18009eed4  mov     esi, 1
0x18009eed9  xor     r14d, r14d
0x18009eedc  mov     r15d, dword ptr [rsp+348h+var_2D0]
0x18009eee1  mov     r12, [rsp+348h+var_280]
0x18009eee9  mov     r13, [rsp+348h+var_278]
0x18009eef1  jmp     short loc_18009EF4C
0x18009eef3  mov     [rsp+348h+var_2D0], r14
0x18009eef8  mov     rbx, [r12]
0x18009eefc  lea     rcx, [rsp+348h+var_2D0]
0x18009ef01  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18009ef06  lea     rax, [rsp+348h+var_2D0]
0x18009ef0b  mov     [rsp+348h+var_328], rax; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData **
0x18009ef10  mov     r9, [r12+20h]; struct TraceLoggingCorrelationVector *
0x18009ef15  mov     r8, [r12+18h]; struct AppId *
0x18009ef1a  mov     rdx, [r12+10h]; struct Windows::System::IUser *
0x18009ef1f  mov     rcx, rbx; this
0x18009ef22  call    ?GetAppData@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIUser@System@6@PEAVAppId@@PEAVTraceLoggingCorrelationVector@@PEAPEAVAppData@Internal@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::GetAppData(Windows::System::IUser *,AppId *,TraceLoggingCorrelationVector *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData * *)
0x18009ef27  mov     r15d, eax
0x18009ef2a  mov     rdx, [rsp+348h+var_2D0]
0x18009ef2f  mov     [rsp+348h+var_2D0], r14
0x18009ef34  lea     rcx, [rsp+348h+var_2B0]
0x18009ef3c  call    ?Attach@?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@QEAAXPEAVInstallItem@Internal@WindowsUpdate@@@Z; Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>::Attach(WindowsUpdate::Internal::InstallItem *)
0x18009ef41  nop
0x18009ef42  lea     rcx, [rsp+348h+var_2D0]
0x18009ef47  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18009ef4c  test    r15d, r15d
0x18009ef4f  js      loc_18009F1F8
0x18009ef55  mov     [rsp+348h+var_2D8], r14b
0x18009ef5a  mov     rdi, [rsp+348h+var_2B0]
0x18009ef62  mov     rax, [rdi]
0x18009ef65  lea     rdx, [rsp+348h+var_2D8]
0x18009ef6a  mov     rcx, rdi
0x18009ef6d  mov     rax, [rax+0E0h]
0x18009ef74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ef79  mov     r15d, eax
0x18009ef7c  test    eax, eax
0x18009ef7e  js      loc_18009F1F8
0x18009ef84  cmp     [rsp+348h+var_2D8], r14b
0x18009ef89  jz      short loc_18009EF9B
0x18009ef8b  mov     [rsp+348h+var_2C0], r14d
0x18009ef93  mov     r15d, r14d
0x18009ef96  jmp     loc_18009F201
0x18009ef9b  mov     [rsp+348h+var_2D7], r14b
0x18009efa0  mov     rax, [rdi]
0x18009efa3  lea     rdx, [rsp+348h+var_2D7]
0x18009efa8  mov     rcx, rdi
0x18009efab  mov     rax, [rax+0E8h]
0x18009efb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009efb7  mov     r15d, eax
0x18009efba  test    eax, eax
0x18009efbc  js      loc_18009F1F8
0x18009efc2  cmp     [rsp+348h+var_2D7], r14b
0x18009efc7  jz      loc_18009F1F8
0x18009efcd  mov     [rsp+348h+var_2B8], r14
0x18009efd5  mov     rax, [rdi]
0x18009efd8  mov     rbx, [rax+68h]
0x18009efdc  xor     ecx, ecx; string
0x18009efde  call    cs:__imp_WindowsDeleteString
0x18009efe4  mov     [rsp+348h+var_2B8], r14
0x18009efec  lea     rdx, [rsp+348h+var_2B8]
0x18009eff4  mov     rcx, rdi
0x18009eff7  mov     rax, rbx
0x18009effa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009efff  mov     r15d, eax
0x18009f002  test    eax, eax
0x18009f004  js      loc_18009F1EA
0x18009f00a  call    IsSrpDoesPolicyAllowAppExecutionPresent
0x18009f00f  test    al, al
0x18009f011  jz      loc_18009F158
0x18009f017  mov     [rsp+348h+string], r14
0x18009f01f  mov     rax, [rdi]
0x18009f022  mov     rbx, [rax+38h]
0x18009f026  xor     ecx, ecx; string
0x18009f028  call    cs:__imp_WindowsDeleteString
0x18009f02e  mov     [rsp+348h+string], r14
0x18009f036  lea     rdx, [rsp+348h+string]
0x18009f03e  mov     rcx, rdi
0x18009f041  mov     rax, rbx
0x18009f044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f049  mov     r15d, eax
0x18009f04c  test    eax, eax
0x18009f04e  js      loc_18009F141
0x18009f054  xorps   xmm0, xmm0
0x18009f057  movups  [rsp+348h+var_250], xmm0
0x18009f05f  movups  [rsp+348h+var_240], xmm0
0x18009f067  movups  [rsp+348h+var_230], xmm0
0x18009f06f  xor     edx, edx; length
0x18009f071  mov     rcx, [rsp+348h+string]; string
0x18009f079  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f07f  mov     qword ptr [rsp+348h+var_240], rax
0x18009f087  xor     edx, edx; length
0x18009f089  mov     rcx, [rsp+348h+var_2B8]; string
0x18009f091  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f097  mov     qword ptr [rsp+348h+var_240+8], rax
0x18009f09f  mov     qword ptr [rsp+348h+var_250+8], rsi
0x18009f0a7  mov     rcx, [r12+20h]; this
0x18009f0ac  mov     rdx, r14
0x18009f0af  lock xadd [rcx+88h], rdx; unsigned __int64
0x18009f0b8  lea     r8, [rsp+348h+var_158]; char *
0x18009f0c0  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18009f0c5  lea     rax, [rsp+348h+var_158]
0x18009f0cd  mov     [rsp+348h+var_2F8], rax
0x18009f0d2  mov     rax, qword ptr [rsp+348h+var_240+8]
0x18009f0da  mov     qword ptr [rsp+348h+var_308+8], rax
0x18009f0df  mov     rax, qword ptr [rsp+348h+var_240]
0x18009f0e7  mov     qword ptr [rsp+348h+var_308], rax
0x18009f0ec  mov     [rsp+348h+var_310], r14; unsigned __int16 *
0x18009f0f1  mov     [rsp+348h+var_318], r14; char *
0x18009f0f6  lea     rax, aSrpdoespolicya_1; "SrpDoesPolicyAllowAppExecution(%s, %s),"...
0x18009f0fd  mov     [rsp+348h+var_320], rax; unsigned __int16 *
0x18009f102  mov     dword ptr [rsp+348h+var_328], 0FFFFFFFFh; int
0x18009f10a  lea     r9, aWindowsApplica_129; "Windows::ApplicationModel::Store::Previ"...
0x18009f111  mov     r8d, 0AEAh; unsigned int
0x18009f117  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x18009f11e  mov     ecx, 3; unsigned int
0x18009f123  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18009f128  lea     rdx, [rsp+348h+var_2C0]
0x18009f130  lea     rcx, [rsp+348h+var_250]
0x18009f138  call    cs:__imp_SrpDoesPolicyAllowAppExecution
0x18009f13e  mov     r15d, eax
0x18009f141  mov     rcx, [rsp+348h+string]; string
0x18009f149  call    cs:__imp_WindowsDeleteString
0x18009f14f  test    r15d, r15d
0x18009f152  js      loc_18009F1EA
0x18009f158  cmp     [rsp+348h+var_2C0], esi
0x18009f15f  jnz     loc_18009F1EA
0x18009f165  mov     [rsp+348h+string], r14
0x18009f16d  mov     rax, [rdi]
0x18009f170  mov     rbx, [rax+40h]
0x18009f174  xor     ecx, ecx; string
0x18009f176  call    cs:__imp_WindowsDeleteString
0x18009f17c  mov     [rsp+348h+string], r14
0x18009f184  lea     rdx, [rsp+348h+string]
0x18009f18c  mov     rcx, rdi
0x18009f18f  mov     rax, rbx
0x18009f192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f197  mov     r15d, eax
0x18009f19a  test    eax, eax
0x18009f19c  js      short loc_18009F1DB
0x18009f19e  xor     edx, edx; length
0x18009f1a0  mov     rcx, [rsp+348h+string]; string
0x18009f1a8  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f1ae  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18009f1b5  mov     rcx, rax
0x18009f1b8  call    cs:__imp_?WldpIsAppApprovedByPolicy@@YAJPEBG_K@Z; WldpIsAppApprovedByPolicy(ushort const *,unsigned __int64)
0x18009f1be  test    eax, eax
0x18009f1c0  jns     short loc_18009F1D8
0x18009f1c2  mov     [rsp+348h+var_2C0], r14d
0x18009f1ca  mov     r15d, r14d
0x18009f1cd  cmp     eax, 0D0E90002h
0x18009f1d2  cmovnz  r15d, eax
0x18009f1d6  jmp     short loc_18009F1DB
0x18009f1d8  mov     r15d, eax
0x18009f1db  mov     rcx, [rsp+348h+string]; string
0x18009f1e3  call    cs:__imp_WindowsDeleteString
0x18009f1e9  nop
0x18009f1ea  mov     rcx, [rsp+348h+var_2B8]; string
0x18009f1f2  call    cs:__imp_WindowsDeleteString
0x18009f1f8  cmp     [rsp+348h+var_2C0], esi
0x18009f1ff  jz      short loc_18009F204
0x18009f201  mov     sil, r14b
0x18009f204  mov     [r13+10h], sil
  ... truncated ...
```
