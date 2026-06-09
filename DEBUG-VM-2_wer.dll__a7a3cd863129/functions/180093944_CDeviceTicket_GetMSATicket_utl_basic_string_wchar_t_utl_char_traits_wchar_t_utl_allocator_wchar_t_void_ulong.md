# CDeviceTicket::GetMSATicket(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *,ulong)

- ea: `0x180093944`
- end: `0x1800944c0`
- name: `?GetMSATicket@CDeviceTicket@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAXK@Z`
- size: `2940`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008f0fc`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000c390`
- `0x180019b50`
- `0x18001fe24`
- `0x1800269c4`
- `0x18002e390`
- `0x18002f570`
- `0x1800303dc`
- `0x180043fac`
- `0x180049530`
- `0x18004a8e0`
- `0x18004c824`
- `0x180050db0`
- `0x180093944`
- `0x1800944c8`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800939c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093e23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093f25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800942e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800939c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093e23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093f25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800942e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180093c41`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180093c41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093ea5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093ea5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180093f02`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180093f02`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009448e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009448e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800939d2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800939d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093ace`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009427a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009427a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093b6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093b6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009443e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009443e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094466`

## string_xrefs

- `0x180093b18`: `https://watson.telemetry.microsoft.com`
- `0x180093a09`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180093a28`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CDeviceTicket::GetMSATicket(__int64 a1, void *a2)
{
  DWORD v4; // ebx
  HRESULT v5; // esi
  void *v6; // rdi
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HRESULT ActivationFactory; // eax
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  HANDLE Event; // rbx
  DWORD LastError; // eax
  HANDLE v15; // rax
  void **v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r14
  __int64 (__fastcall *v19)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64 *); // r14
  int v22; // r14d
  char v23; // bl
  ULONGLONG v24; // rax
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  const char *v28; // rax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // r14
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, __int64 *); // r14
  __int64 v33; // r14
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64 *); // rbx
  __int64 v35; // r14
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  ULONGLONG v38; // r14
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+48h] [rbp-B8h] BYREF
  int v42; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD dwindex[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v45; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  ULONGLONG TickCount64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-50h] BYREF
  void **v56; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE pHandles; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v58; // [rsp+C8h] [rbp-38h] BYREF
  HRESULT v59; // [rsp+D0h] [rbp-30h]
  __int128 v60; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v61; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v62; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  __int64 v64; // [rsp+128h] [rbp+28h]
  char v65[32]; // [rsp+130h] [rbp+30h] BYREF
  __int128 *v66; // [rsp+150h] [rbp+50h]
  __int64 v67; // [rsp+158h] [rbp+58h]
  ULONGLONG *p_TickCount64; // [rsp+160h] [rbp+60h]
  __int64 v69; // [rsp+168h] [rbp+68h]
  DWORD *v70; // [rsp+170h] [rbp+70h]
  __int64 v71; // [rsp+178h] [rbp+78h]

  if ( !a1 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, 2147942487LL);
    return v4;
  }
  TickCount64 = GetTickCount64();
  v5 = CoInitializeEx(0, 0);
  v59 = v5;
  pHandles = 0;
  v56 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  string = 0;
  v46 = 0;
  v45 = 0;
  v64 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
    0x42u,
    0x41u);
  v62 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v61,
    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
    0x46u,
    0x45u);
  v55 = 0;
  v54 = 0;
  v50 = 0;
  v6 = 0;
  v58 = 0;
  v44 = 0;
  v40 = 0;
  v53 = 0;
  v52 = 0;
  v49 = 0;
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147417850 )
  {
    v4 = v5;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 11;
    v9 = (unsigned int)v5;
    goto LABEL_10;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v55);
  ActivationFactory = RoGetActivationFactory(v62, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v55);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 12;
    goto LABEL_15;
  }
  WindowsDeleteString(string);
  string = 0;
  ActivationFactory = WindowsCreateString(L"https://watson.telemetry.microsoft.com", 0x26u, &string);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 13;
    goto LABEL_15;
  }
  WindowsDeleteString(v46);
  v46 = 0;
  ActivationFactory = WindowsCreateString(L"MBI_SSL", 7u, &v46);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 14;
    goto LABEL_15;
  }
  v11 = v55;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v54);
  ActivationFactory = v12(v11, string, v46, &v54);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 15;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v50);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>(
                        v64,
                        &v50);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 16;
    goto LABEL_15;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
  {
    LastError = GetLastError();
    v4 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_132;
  }
  v15 = pHandles;
  if ( Event != pHandles )
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v56);
    v15 = Event;
    pHandles = Event;
  }
  v58 = v15;
  v16 = (void **)Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(
                   dwindex,
                   &v58);
  v6 = *v16;
  *v16 = 0;
  v58 = v6;
  v17 = *(_QWORD *)dwindex;
  if ( *(_QWORD *)dwindex )
  {
    *(_QWORD *)dwindex = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( !v6 )
  {
    v4 = -2147024882;
    goto LABEL_132;
  }
  v60 = xmmword_1800C1C60;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v50 + 72LL))(v50, &v60);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 17;
    goto LABEL_15;
  }
  v18 = v50;
  v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v50 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v44);
  ActivationFactory = v19(v18, v54, &v44);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 18;
    goto LABEL_15;
  }
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), void *))(*v44)[6])(
                        v44,
                        v6);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 19;
    goto LABEL_15;
  }
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  v21 = **v44;
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v40);
  ActivationFactory = v21(v20, &GUID_00000036_0000_0000_c000_000000000046, &v40);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 20;
    goto LABEL_15;
  }
  dwindex[0] = 0;
  v22 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v24 = GetTickCount64();
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
      v24 - TickCount64);
  }
  while ( CoWaitForMultipleHandles(0x18u, 0x64u, 1u, &pHandles, dwindex) == -2147417835 )
  {
    if ( !v23 )
    {
      if ( (unsigned int)++v22 > 0x1E )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 72LL))(v40);
        v23 = 1;
      }
      if ( a2 && !WaitForSingleObject(a2, 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 72LL))(v40);
        v23 = 1;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v27 = GetTickCount64() - TickCount64;
    v28 = "true";
    if ( !v23 )
      v28 = "false";
    WPP_SF_is(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, v27, (__int64)v28);
  }
  v41 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v41);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 25;
    goto LABEL_15;
  }
  v4 = v41;
  if ( v41 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)v41);
      v4 = v41;
    }
    goto LABEL_132;
  }
  v48 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 56LL))(v40, &v48);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 27;
    goto LABEL_15;
  }
  if ( v48 != 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, v48);
    v4 = -2147467260;
    goto LABEL_132;
  }
  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  v30 = (*v44)[8];
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v53);
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v30)(
                        v29,
                        &v53);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 29;
    goto LABEL_15;
  }
  v31 = v53;
  if ( !v53 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(v53 + 30),
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
LABEL_131:
    v4 = -2147467261;
    goto LABEL_132;
  }
  v42 = 0;
  v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v52);
  ActivationFactory = v32(v31, &v52);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 31;
    goto LABEL_15;
  }
  v33 = v52;
  v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v49);
  ActivationFactory = v34(v33, 0, &v49);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 32;
    goto LABEL_15;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v42);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 33;
    goto LABEL_15;
  }
  v4 = v42;
  if ( v42 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)v42);
      v4 = v42;
    }
    goto LABEL_132;
  }
  v35 = v49;
  v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v49 + 48LL);
  WindowsDeleteString(v45);
  v45 = 0;
  ActivationFactory = v36(v35, &v45);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 35;
LABEL_15:
    v9 = (unsigned int)ActivationFactory;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, v9);
    goto LABEL_132;
  }
  if ( !v45 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)ActivationFactory);
    goto LABEL_131;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v45, 0);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a1,
                           StringRawBuffer) )
  {
    v4 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 36;
    v9 = 2147942414LL;
    goto LABEL_10;
  }
  v4 = 0;
LABEL_132:
  v38 = GetTickCount64() - TickCount64;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_SSdi(*((_QWORD *)WPP_GLOBAL_Control + 2));
  if ( (unsigned int)dword_1800D8000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 0x400000000000LL) )
  {
    dwindex[0] = v4;
    TickCount64 = v38;
    *(_QWORD *)&v60 = 0x1000000;
    v70 = dwindex;
    v71 = 4;
    p_TickCount64 = &TickCount64;
    v69 = 8;
    v66 = &v60;
    v67 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800D8000, byte_1800C86CD, 0, 0, 5, v65);
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL))(v40);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v44);
  if ( v6 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v55);
  v62 = 0;
  v64 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(v46);
  v46 = 0;
  WindowsDeleteString(string);
  string = 0;
  v56 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v56);
  if ( v5 >= 0 )
    CoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x180093944  mov     [rsp-8+arg_10], rbx
0x180093949  push    rbp
0x18009394a  push    rsi
0x18009394b  push    rdi
0x18009394c  push    r12
0x18009394e  push    r13
0x180093950  push    r14
0x180093952  push    r15
0x180093954  lea     rbp, [rsp-90h]
0x18009395c  sub     rsp, 190h
0x180093963  mov     rax, cs:__security_cookie
0x18009396a  xor     rax, rsp
0x18009396d  mov     [rbp+0C0h+var_40], rax
0x180093974  mov     r12, rdx
0x180093977  mov     r13, rcx
0x18009397a  xor     r14d, r14d
0x18009397d  test    rcx, rcx
0x180093980  jnz     short loc_1800939C4
0x180093982  lea     r15, WPP_GLOBAL_Control
0x180093989  mov     ebx, 80070057h
0x18009398e  mov     rcx, cs:WPP_GLOBAL_Control
0x180093995  cmp     rcx, r15
0x180093998  jz      loc_180094494
0x18009399e  test    byte ptr [rcx+1Ch], 1
0x1800939a2  jz      loc_180094494
0x1800939a8  lea     edx, [r13+0Ah]
0x1800939ac  mov     r9d, ebx
0x1800939af  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x1800939b6  mov     rcx, [rcx+10h]
0x1800939ba  call    WPP_SF_d
0x1800939bf  jmp     loc_180094494
0x1800939c4  call    cs:__imp_GetTickCount64
0x1800939ca  mov     [rbp+0C0h+var_130], rax
0x1800939ce  xor     edx, edx; dwCoInit
0x1800939d0  xor     ecx, ecx; pvReserved
0x1800939d2  call    cs:__imp_CoInitializeEx
0x1800939d8  mov     esi, eax
0x1800939da  mov     [rbp+0C0h+var_F0], eax
0x1800939dd  mov     [rbp+0C0h+pHandles], r14
0x1800939e1  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800939e8  mov     [rbp+0C0h+var_108], rax
0x1800939ec  mov     [rsp+1C0h+string], r14
0x1800939f1  mov     [rsp+1C0h+var_158], r14
0x1800939f6  mov     [rsp+1C0h+var_160], r14
0x1800939fb  mov     [rbp+0C0h+var_98], r14
0x1800939ff  mov     r9d, 41h ; 'A'; unsigned int
0x180093a05  lea     r8d, [r9+1]; unsigned int
0x180093a09  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QB_WB; "Windows.Internal.Security.WebAuthentica"...
0x180093a10  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x180093a14  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180093a19  nop
0x180093a1a  mov     [rbp+0C0h+var_B8], r14
0x180093a1e  mov     r9d, 45h ; 'E'; unsigned int
0x180093a24  lea     r8d, [r9+1]; unsigned int
0x180093a28  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QB_WB; "Windows.Security.Authentication.OnlineI"...
0x180093a2f  lea     rcx, [rbp+0C0h+var_D0]; hstringHeader
0x180093a33  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180093a38  nop
0x180093a39  mov     [rbp+0C0h+var_110], r14
0x180093a3d  mov     [rbp+0C0h+var_118], r14
0x180093a41  mov     [rbp+0C0h+var_138], r14
0x180093a45  mov     rdi, r14
0x180093a48  mov     [rbp+0C0h+var_F8], r14
0x180093a4c  mov     [rsp+1C0h+var_168], r14
0x180093a51  mov     [rsp+1C0h+var_180], r14
0x180093a56  mov     [rbp+0C0h+var_120], r14
0x180093a5a  mov     [rbp+0C0h+var_128], r14
0x180093a5e  mov     [rbp+0C0h+var_140], r14
0x180093a62  mov     ecx, 80000000h
0x180093a67  lea     eax, [rsi+rcx]
0x180093a6a  lea     r15, WPP_GLOBAL_Control
0x180093a71  test    ecx, eax
0x180093a73  jnz     short loc_180093AB6
0x180093a75  cmp     esi, 80010106h
0x180093a7b  jz      short loc_180093AB6
0x180093a7d  mov     ebx, esi
0x180093a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180093a86  cmp     rcx, r15
0x180093a89  jz      loc_1800942E6
0x180093a8f  test    byte ptr [rcx+1Ch], 1
0x180093a93  jz      loc_1800942E6
0x180093a99  mov     edx, 0Bh
0x180093a9e  mov     r9d, esi
0x180093aa1  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180093aa8  mov     rcx, [rcx+10h]
0x180093aac  call    WPP_SF_d
0x180093ab1  jmp     loc_1800942E6
0x180093ab6  lea     rcx, [rbp+0C0h+var_110]
0x180093aba  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093abf  lea     r8, [rbp+0C0h+var_110]
0x180093ac3  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180093aca  mov     rcx, [rbp+0C0h+var_B8]
0x180093ace  call    cs:__imp_RoGetActivationFactory
0x180093ad4  mov     ebx, eax
0x180093ad6  test    eax, eax
0x180093ad8  jns     short loc_180093AFE
0x180093ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ae1  cmp     rcx, r15
0x180093ae4  jz      loc_1800942E6
0x180093aea  test    byte ptr [rcx+1Ch], 1
0x180093aee  jz      loc_1800942E6
0x180093af4  mov     edx, 0Ch
0x180093af9  mov     r9d, eax
0x180093afc  jmp     short loc_180093AA1
0x180093afe  mov     rcx, [rsp+1C0h+string]; string
0x180093b03  call    cs:__imp_WindowsDeleteString
0x180093b09  mov     [rsp+1C0h+string], r14
0x180093b0e  lea     r8, [rsp+1C0h+string]; string
0x180093b13  mov     edx, 26h ; '&'; length
0x180093b18  lea     rcx, sourceString; "https://watson.telemetry.microsoft.com"
0x180093b1f  call    cs:__imp_WindowsCreateString
0x180093b25  mov     ebx, eax
0x180093b27  test    eax, eax
0x180093b29  jns     short loc_180093B4C
0x180093b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180093b32  cmp     rcx, r15
0x180093b35  jz      loc_1800942E6
0x180093b3b  test    byte ptr [rcx+1Ch], 1
0x180093b3f  jz      loc_1800942E6
0x180093b45  mov     edx, 0Dh
0x180093b4a  jmp     short loc_180093AF9
0x180093b4c  mov     rcx, [rsp+1C0h+var_158]; string
0x180093b51  call    cs:__imp_WindowsDeleteString
0x180093b57  mov     [rsp+1C0h+var_158], r14
0x180093b5c  lea     r8, [rsp+1C0h+var_158]; string
0x180093b61  mov     edx, 7; length
0x180093b66  lea     rcx, aMbiSsl; "MBI_SSL"
0x180093b6d  call    cs:__imp_WindowsCreateString
0x180093b73  mov     ebx, eax
0x180093b75  test    eax, eax
0x180093b77  jns     short loc_180093B9D
0x180093b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180093b80  cmp     rcx, r15
0x180093b83  jz      loc_1800942E6
0x180093b89  test    byte ptr [rcx+1Ch], 1
0x180093b8d  jz      loc_1800942E6
0x180093b93  mov     edx, 0Eh
0x180093b98  jmp     loc_180093AF9
0x180093b9d  mov     r14, [rbp+0C0h+var_110]
0x180093ba1  mov     rax, [r14]
0x180093ba4  mov     rbx, [rax+30h]
0x180093ba8  lea     rcx, [rbp+0C0h+var_118]
0x180093bac  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093bb1  lea     r9, [rbp+0C0h+var_118]
0x180093bb5  mov     r8, [rsp+1C0h+var_158]
0x180093bba  mov     rdx, [rsp+1C0h+string]
0x180093bbf  mov     rcx, r14
0x180093bc2  mov     rax, rbx
0x180093bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093bca  mov     ebx, eax
0x180093bcc  test    eax, eax
0x180093bce  jns     short loc_180093BF4
0x180093bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180093bd7  cmp     rcx, r15
0x180093bda  jz      loc_1800942E6
0x180093be0  test    byte ptr [rcx+1Ch], 1
0x180093be4  jz      loc_1800942E6
0x180093bea  mov     edx, 0Fh
0x180093bef  jmp     loc_180093AF9
0x180093bf4  lea     rcx, [rbp+0C0h+var_138]
0x180093bf8  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093bfd  lea     rdx, [rbp+0C0h+var_138]
0x180093c01  mov     rcx, [rbp+0C0h+var_98]
0x180093c05  call    ??$ActivateInstance@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAuthenticationManager@WebAuthentication@Security@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>(HSTRING__ *,Windows::Internal::Security::WebAuthentication::IAuthenticationManager * *)
0x180093c0a  mov     ebx, eax
0x180093c0c  test    eax, eax
0x180093c0e  jns     short loc_180093C34
0x180093c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180093c17  cmp     rcx, r15
0x180093c1a  jz      loc_1800942E6
0x180093c20  test    byte ptr [rcx+1Ch], 1
0x180093c24  jz      loc_1800942E6
0x180093c2a  mov     edx, 10h
0x180093c2f  jmp     loc_180093AF9
0x180093c34  mov     r9d, 1F0003h; dwDesiredAccess
0x180093c3a  xor     r8d, r8d; dwFlags
0x180093c3d  xor     edx, edx; lpName
0x180093c3f  xor     ecx, ecx; lpEventAttributes
0x180093c41  call    cs:__imp_CreateEventExW
0x180093c47  mov     rbx, rax
0x180093c4a  test    rax, rax
0x180093c4d  jnz     short loc_180093C63
0x180093c4f  call    cs:__imp_GetLastError
0x180093c55  mov     ecx, eax; unsigned int
0x180093c57  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180093c5c  mov     ebx, eax
0x180093c5e  jmp     loc_1800942E6
0x180093c63  mov     rax, [rbp+0C0h+pHandles]
0x180093c67  cmp     rbx, rax
0x180093c6a  jz      short loc_180093C7C
0x180093c6c  lea     rcx, [rbp+0C0h+var_108]
0x180093c70  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180093c75  mov     rax, rbx
0x180093c78  mov     [rbp+0C0h+pHandles], rbx
0x180093c7c  mov     [rbp+0C0h+var_F8], rax
0x180093c80  lea     rdx, [rbp+0C0h+var_F8]
0x180093c84  lea     rcx, [rsp+1C0h+dwindex]
0x180093c89  call    ??$Make@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@PEAX@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@@12@$$QEAPEAX@Z; Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(void * &&)
0x180093c8e  mov     rdi, [rax]
0x180093c91  mov     qword ptr [rax], 0
0x180093c98  mov     [rbp+0C0h+var_F8], rdi
0x180093c9c  mov     rcx, qword ptr [rsp+1C0h+dwindex]
0x180093ca1  test    rcx, rcx
0x180093ca4  jz      short loc_180093CBC
0x180093ca6  mov     qword ptr [rsp+1C0h+dwindex], 0
0x180093caf  mov     rax, [rcx]
0x180093cb2  mov     rax, [rax+10h]
0x180093cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cbb  nop
0x180093cbc  test    rdi, rdi
0x180093cbf  jnz     short loc_180093CCB
0x180093cc1  mov     ebx, 8007000Eh
0x180093cc6  jmp     loc_1800942E6
0x180093ccb  mov     rcx, [rbp+0C0h+var_138]
0x180093ccf  movups  xmm0, cs:xmmword_1800C1C60
0x180093cd6  movdqu  [rbp+0C0h+var_E0], xmm0
0x180093cdb  mov     rax, [rcx]
0x180093cde  lea     rdx, [rbp+0C0h+var_E0]
0x180093ce2  mov     rax, [rax+48h]
0x180093ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ceb  mov     ebx, eax
0x180093ced  test    eax, eax
0x180093cef  jns     short loc_180093D15
0x180093cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180093cf8  cmp     rcx, r15
0x180093cfb  jz      loc_1800942E6
0x180093d01  test    byte ptr [rcx+1Ch], 1
0x180093d05  jz      loc_1800942E6
0x180093d0b  mov     edx, 11h
0x180093d10  jmp     loc_180093AF9
0x180093d15  mov     r14, [rbp+0C0h+var_138]
0x180093d19  mov     rax, [r14]
0x180093d1c  mov     rbx, [rax+38h]
0x180093d20  lea     rcx, [rsp+1C0h+var_168]
0x180093d25  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093d2a  lea     r8, [rsp+1C0h+var_168]
0x180093d2f  mov     rdx, [rbp+0C0h+var_118]
0x180093d33  mov     rcx, r14
0x180093d36  mov     rax, rbx
0x180093d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d3e  mov     ebx, eax
0x180093d40  test    eax, eax
0x180093d42  jns     short loc_180093D68
0x180093d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d4b  cmp     rcx, r15
0x180093d4e  jz      loc_1800942E6
0x180093d54  test    byte ptr [rcx+1Ch], 1
0x180093d58  jz      loc_1800942E6
0x180093d5e  mov     edx, 12h
0x180093d63  jmp     loc_180093AF9
0x180093d68  mov     rcx, [rsp+1C0h+var_168]
0x180093d6d  mov     rax, [rcx]
0x180093d70  mov     rdx, rdi
0x180093d73  mov     rax, [rax+30h]
0x180093d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d7c  mov     ebx, eax
0x180093d7e  test    eax, eax
0x180093d80  jns     short loc_180093DA6
0x180093d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d89  cmp     rcx, r15
0x180093d8c  jz      loc_1800942E6
0x180093d92  test    byte ptr [rcx+1Ch], 1
0x180093d96  jz      loc_1800942E6
0x180093d9c  mov     edx, 13h
0x180093da1  jmp     loc_180093AF9
0x180093da6  mov     rbx, [rsp+1C0h+var_168]
0x180093dab  mov     rax, [rbx]
0x180093dae  mov     r14, [rax]
0x180093db1  lea     rcx, [rsp+1C0h+var_180]
0x180093db6  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093dbb  lea     r8, [rsp+1C0h+var_180]
0x180093dc0  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180093dc7  mov     rcx, rbx
0x180093dca  mov     rax, r14
0x180093dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093dd2  mov     ebx, eax
0x180093dd4  test    eax, eax
0x180093dd6  jns     short loc_180093DFC
0x180093dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ddf  cmp     rcx, r15
0x180093de2  jz      loc_1800942E6
0x180093de8  test    byte ptr [rcx+1Ch], 1
0x180093dec  jz      loc_1800942E6
0x180093df2  mov     edx, 14h
0x180093df7  jmp     loc_180093AF9
0x180093dfc  mov     [rsp+1C0h+dwindex], 0
0x180093e04  xor     r14d, r14d
0x180093e07  xor     bl, bl
0x180093e09  mov     rax, cs:WPP_GLOBAL_Control
0x180093e10  cmp     rax, r15
0x180093e13  jz      loc_180093EE7
0x180093e19  test    byte ptr [rax+1Ch], 4
0x180093e1d  jz      loc_180093EE7
0x180093e23  call    cs:__imp_GetTickCount64
0x180093e29  sub     rax, [rbp+0C0h+var_130]
0x180093e2d  lea     edx, [r14+15h]
0x180093e31  mov     r9, rax
0x180093e34  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180093e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e42  mov     rcx, [rcx+10h]
  ... truncated ...
```
