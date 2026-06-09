# Windows::ApplicationModel::Store::Preview::InstallControl::GetDiscInstallFulfillmentData(Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass> const &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Uri *>> const &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> const &)

- ea: `0x1800ad674`
- end: `0x1800adceb`
- name: `?GetDiscInstallFulfillmentData@InstallControl@Preview@Store@ApplicationModel@Windows@@YA?AV?$ComPtr@UIFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@AEBV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@78@AEBV?$ComPtr@U?$IIterable@PEAVUri@Foundation@Windows@@@Collections@Foundation@Windows@@@78@AEBV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@78@@Z`
- size: `1655`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a230c`
- `0x1800a7078`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001ecfc`
- `0x1800252e8`
- `0x18002ec2c`
- `0x18008abbc`
- `0x1800ad674`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ada0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adaf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adbdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adcac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ada0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adaf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adbdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800adcac`

## string_xrefs

- `0x1800adb88`: `FulfillmentPluginId`
- `0x1800ad6c6`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad72d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad777`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad7b2`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad81e`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad866`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad899`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad905`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad94d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad97d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ad9e9`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ada31`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800ada64`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adad0`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adb18`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adb4b`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adbb7`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adbff`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adc32`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adc64`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800adc96`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::ApplicationModel::Store::Preview::InstallControl::GetDiscInstallFulfillmentData(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, __int64 *); // rbx
  int v38; // eax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rbx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, __int64 *); // rbx
  int v45; // eax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, HSTRING *); // rbx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  __int64 v54; // [rsp+28h] [rbp-58h] BYREF
  __int64 v55; // [rsp+30h] [rbp-50h] BYREF
  int v56; // [rsp+38h] [rbp-48h]
  _QWORD v57[2]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v59; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v57[1] = a1;
  v56 = 0;
  v55 = 0;
  v7 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         a4,
         &v55);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18BE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
  v54 = 0;
  v8 = v55;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProductId", 0xAu, 9u);
  v10 = v9(v8, v59, &v54);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18C1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
  string = 0;
  v11 = v54;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(v11, &string);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18C3,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v13,
      (int)string);
  *a1 = 0;
  v56 = 1;
  v57[0] = string;
  v14 = Microsoft::WRL::Details::MakeAndInitialize<WindowsUpdate::Internal::FulfillmentDataInfo,WindowsUpdate::Internal::IFulfillmentDataInfo,HSTRING__ *>(
          a1,
          v57);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18C6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v14,
      (int)string);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v15 = v55;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProductTitle", 0xDu, 0xCu);
  v17 = v16(v15, v59, &v54);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18C9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v17,
      (int)string);
  v18 = v54;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v20 = v19(v18, &string);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18CA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v20,
      (int)string);
  v21 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*a1 + 128LL))(*a1, string);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18CB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v21,
      (int)string);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v22 = v55;
  v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PackageFamilyName", 0x12u, 0x11u);
  v24 = v23(v22, v59, &v54);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18CE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v24,
      (int)string);
  v25 = v54;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v27 = v26(v25, &string);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18CF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v27,
      (int)string);
  v28 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*a1 + 96LL))(*a1, string);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v28,
      (int)string);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v29 = v55;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"CategoryId", 0xBu, 0xAu);
  v31 = v30(v29, v59, &v54);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D3,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v31,
      (int)string);
  v32 = v54;
  v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v34 = v33(v32, &string);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v34,
      (int)string);
  v35 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*a1 + 176LL))(*a1, string);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D5,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v35,
      (int)string);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v36 = v55;
  v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Market", 7u, 6u);
  v38 = v37(v36, v59, &v54);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v38,
      (int)string);
  v39 = v54;
  v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v41 = v40(v39, &string);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18D9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v41,
      (int)string);
  v42 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*a1 + 304LL))(*a1, string);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18DA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v42,
      (int)string);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v43 = v55;
  v44 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"FulfillmentPluginId", 0x14u, 0x13u);
  v45 = v44(v43, v59, &v54);
  if ( v45 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18DD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v45,
      (int)string);
  v46 = v54;
  v47 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v48 = v47(v46, &string);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18DE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v48,
      (int)string);
  v49 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*a1 + 336LL))(*a1, string);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18DF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v49,
      (int)string);
  v50 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 272LL))(*a1, *a2);
  if ( v50 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18E1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v50,
      (int)string);
  v51 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 288LL))(*a1, *a3);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18E2,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v51,
      (int)string);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
  return a1;
}

```

## disassembly

```asm
0x1800ad674  push    rbp
0x1800ad676  push    rbx
0x1800ad677  push    rsi
0x1800ad678  push    rdi
0x1800ad679  push    r12
0x1800ad67b  push    r14
0x1800ad67d  push    r15
0x1800ad67f  mov     rbp, rsp
0x1800ad682  sub     rsp, 80h
0x1800ad689  mov     rax, cs:__security_cookie
0x1800ad690  xor     rax, rsp
0x1800ad693  mov     [rbp+var_10], rax
0x1800ad697  mov     r15, r8
0x1800ad69a  mov     r14, rdx
0x1800ad69d  mov     rsi, rcx
0x1800ad6a0  mov     [rbp+var_38], rcx
0x1800ad6a4  xor     r12d, r12d
0x1800ad6a7  mov     [rbp+var_48], r12d
0x1800ad6ab  mov     [rbp+var_50], r12
0x1800ad6af  lea     rdx, [rbp+var_50]
0x1800ad6b3  mov     rcx, r9
0x1800ad6b6  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800ad6bb  mov     rcx, [rbp+38h]; this
0x1800ad6bf  test    eax, eax
0x1800ad6c1  jns     short loc_1800AD6D8
0x1800ad6c3  mov     r9d, eax; char *
0x1800ad6c6  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad6cd  mov     edx, 18BEh; void *
0x1800ad6d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad6d8  mov     [rbp+var_58], r12
0x1800ad6dc  mov     rdi, [rbp+var_50]
0x1800ad6e0  mov     rax, [rdi]
0x1800ad6e3  mov     rbx, [rax+30h]
0x1800ad6e7  lea     rcx, [rbp+var_58]
0x1800ad6eb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad6f0  mov     [rbp+var_18], r12
0x1800ad6f4  mov     r9d, 9; unsigned int
0x1800ad6fa  lea     r8d, [r9+1]; unsigned int
0x1800ad6fe  lea     rdx, aProductid_0; "ProductId"
0x1800ad705  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800ad709  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ad70e  nop
0x1800ad70f  lea     r8, [rbp+var_58]
0x1800ad713  mov     rdx, [rbp+var_18]
0x1800ad717  mov     rcx, rdi
0x1800ad71a  mov     rax, rbx
0x1800ad71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad722  mov     rcx, [rbp+38h]; this
0x1800ad726  test    eax, eax
0x1800ad728  jns     short loc_1800AD73F
0x1800ad72a  mov     r9d, eax; char *
0x1800ad72d  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad734  mov     edx, 18C1h; void *
0x1800ad739  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad73f  mov     [rbp+string], r12
0x1800ad743  mov     rdi, [rbp+var_58]
0x1800ad747  mov     rax, [rdi]
0x1800ad74a  mov     rbx, [rax+98h]
0x1800ad751  xor     ecx, ecx; string
0x1800ad753  call    cs:__imp_WindowsDeleteString
0x1800ad759  mov     [rbp+string], r12
0x1800ad75d  lea     rdx, [rbp+string]
0x1800ad761  mov     rcx, rdi
0x1800ad764  mov     rax, rbx
0x1800ad767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad76c  mov     rcx, [rbp+38h]; this
0x1800ad770  test    eax, eax
0x1800ad772  jns     short loc_1800AD789
0x1800ad774  mov     r9d, eax; char *
0x1800ad777  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad77e  mov     edx, 18C3h; void *
0x1800ad783  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad789  mov     [rsi], r12
0x1800ad78c  mov     [rbp+var_48], 1
0x1800ad793  mov     rax, [rbp+string]
0x1800ad797  mov     [rbp+var_40], rax
0x1800ad79b  lea     rdx, [rbp+var_40]
0x1800ad79f  mov     rcx, rsi
0x1800ad7a2  call    ??$MakeAndInitialize@VFulfillmentDataInfo@Internal@WindowsUpdate@@UIFulfillmentDataInfo@23@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsUpdate::Internal::FulfillmentDataInfo,WindowsUpdate::Internal::IFulfillmentDataInfo,HSTRING__ *>(WindowsUpdate::Internal::IFulfillmentDataInfo * *,HSTRING__ * &&)
0x1800ad7a7  mov     rcx, [rbp+38h]; this
0x1800ad7ab  test    eax, eax
0x1800ad7ad  jns     short loc_1800AD7C4
0x1800ad7af  mov     r9d, eax; char *
0x1800ad7b2  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad7b9  mov     edx, 18C6h; void *
0x1800ad7be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad7c4  lea     rcx, [rbp+var_58]
0x1800ad7c8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad7cd  mov     rdi, [rbp+var_50]
0x1800ad7d1  mov     rax, [rdi]
0x1800ad7d4  mov     rbx, [rax+30h]
0x1800ad7d8  lea     rcx, [rbp+var_58]
0x1800ad7dc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad7e1  mov     [rbp+var_18], r12
0x1800ad7e5  mov     r9d, 0Ch; unsigned int
0x1800ad7eb  lea     r8d, [r9+1]; unsigned int
0x1800ad7ef  lea     rdx, aProducttitle; "ProductTitle"
0x1800ad7f6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800ad7fa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ad7ff  nop
0x1800ad800  lea     r8, [rbp+var_58]
0x1800ad804  mov     rdx, [rbp+var_18]
0x1800ad808  mov     rcx, rdi
0x1800ad80b  mov     rax, rbx
0x1800ad80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad813  mov     rcx, [rbp+38h]; this
0x1800ad817  test    eax, eax
0x1800ad819  jns     short loc_1800AD830
0x1800ad81b  mov     r9d, eax; char *
0x1800ad81e  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad825  mov     edx, 18C9h; void *
0x1800ad82a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad830  mov     rdi, [rbp+var_58]
0x1800ad834  mov     rax, [rdi]
0x1800ad837  mov     rbx, [rax+98h]
0x1800ad83e  mov     rcx, [rbp+string]; string
0x1800ad842  call    cs:__imp_WindowsDeleteString
0x1800ad848  mov     [rbp+string], r12
0x1800ad84c  lea     rdx, [rbp+string]
0x1800ad850  mov     rcx, rdi
0x1800ad853  mov     rax, rbx
0x1800ad856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad85b  mov     rcx, [rbp+38h]; this
0x1800ad85f  test    eax, eax
0x1800ad861  jns     short loc_1800AD878
0x1800ad863  mov     r9d, eax; char *
0x1800ad866  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad86d  mov     edx, 18CAh; void *
0x1800ad872  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad878  mov     rcx, [rsi]
0x1800ad87b  mov     rax, [rcx]
0x1800ad87e  mov     rdx, [rbp+string]
0x1800ad882  mov     rax, [rax+80h]
0x1800ad889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad88e  mov     rcx, [rbp+38h]; this
0x1800ad892  test    eax, eax
0x1800ad894  jns     short loc_1800AD8AB
0x1800ad896  mov     r9d, eax; char *
0x1800ad899  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad8a0  mov     edx, 18CBh; void *
0x1800ad8a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad8ab  lea     rcx, [rbp+var_58]
0x1800ad8af  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad8b4  mov     rdi, [rbp+var_50]
0x1800ad8b8  mov     rax, [rdi]
0x1800ad8bb  mov     rbx, [rax+30h]
0x1800ad8bf  lea     rcx, [rbp+var_58]
0x1800ad8c3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad8c8  mov     [rbp+var_18], r12
0x1800ad8cc  mov     r9d, 11h; unsigned int
0x1800ad8d2  lea     r8d, [r9+1]; unsigned int
0x1800ad8d6  lea     rdx, aPackagefamilyn_3; "PackageFamilyName"
0x1800ad8dd  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800ad8e1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ad8e6  nop
0x1800ad8e7  lea     r8, [rbp+var_58]
0x1800ad8eb  mov     rdx, [rbp+var_18]
0x1800ad8ef  mov     rcx, rdi
0x1800ad8f2  mov     rax, rbx
0x1800ad8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad8fa  mov     rcx, [rbp+38h]; this
0x1800ad8fe  test    eax, eax
0x1800ad900  jns     short loc_1800AD917
0x1800ad902  mov     r9d, eax; char *
0x1800ad905  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad90c  mov     edx, 18CEh; void *
0x1800ad911  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad917  mov     rdi, [rbp+var_58]
0x1800ad91b  mov     rax, [rdi]
0x1800ad91e  mov     rbx, [rax+98h]
0x1800ad925  mov     rcx, [rbp+string]; string
0x1800ad929  call    cs:__imp_WindowsDeleteString
0x1800ad92f  mov     [rbp+string], r12
0x1800ad933  lea     rdx, [rbp+string]
0x1800ad937  mov     rcx, rdi
0x1800ad93a  mov     rax, rbx
0x1800ad93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad942  mov     rcx, [rbp+38h]; this
0x1800ad946  test    eax, eax
0x1800ad948  jns     short loc_1800AD95F
0x1800ad94a  mov     r9d, eax; char *
0x1800ad94d  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad954  mov     edx, 18CFh; void *
0x1800ad959  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad95f  mov     rcx, [rsi]
0x1800ad962  mov     rax, [rcx]
0x1800ad965  mov     rdx, [rbp+string]
0x1800ad969  mov     rax, [rax+60h]
0x1800ad96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad972  mov     rcx, [rbp+38h]; this
0x1800ad976  test    eax, eax
0x1800ad978  jns     short loc_1800AD98F
0x1800ad97a  mov     r9d, eax; char *
0x1800ad97d  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad984  mov     edx, 18D0h; void *
0x1800ad989  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad98f  lea     rcx, [rbp+var_58]
0x1800ad993  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad998  mov     rdi, [rbp+var_50]
0x1800ad99c  mov     rax, [rdi]
0x1800ad99f  mov     rbx, [rax+30h]
0x1800ad9a3  lea     rcx, [rbp+var_58]
0x1800ad9a7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ad9ac  mov     [rbp+var_18], r12
0x1800ad9b0  mov     r9d, 0Ah; unsigned int
0x1800ad9b6  lea     r8d, [r9+1]; unsigned int
0x1800ad9ba  lea     rdx, aCategoryid; "CategoryId"
0x1800ad9c1  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800ad9c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ad9ca  nop
0x1800ad9cb  lea     r8, [rbp+var_58]
0x1800ad9cf  mov     rdx, [rbp+var_18]
0x1800ad9d3  mov     rcx, rdi
0x1800ad9d6  mov     rax, rbx
0x1800ad9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad9de  mov     rcx, [rbp+38h]; this
0x1800ad9e2  test    eax, eax
0x1800ad9e4  jns     short loc_1800AD9FB
0x1800ad9e6  mov     r9d, eax; char *
0x1800ad9e9  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ad9f0  mov     edx, 18D3h; void *
0x1800ad9f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad9fb  mov     rdi, [rbp+var_58]
0x1800ad9ff  mov     rax, [rdi]
0x1800ada02  mov     rbx, [rax+98h]
0x1800ada09  mov     rcx, [rbp+string]; string
0x1800ada0d  call    cs:__imp_WindowsDeleteString
0x1800ada13  mov     [rbp+string], r12
0x1800ada17  lea     rdx, [rbp+string]
0x1800ada1b  mov     rcx, rdi
0x1800ada1e  mov     rax, rbx
0x1800ada21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ada26  mov     rcx, [rbp+38h]; this
0x1800ada2a  test    eax, eax
0x1800ada2c  jns     short loc_1800ADA43
0x1800ada2e  mov     r9d, eax; char *
0x1800ada31  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ada38  mov     edx, 18D4h; void *
0x1800ada3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ada43  mov     rcx, [rsi]
0x1800ada46  mov     rax, [rcx]
0x1800ada49  mov     rdx, [rbp+string]
0x1800ada4d  mov     rax, [rax+0B0h]
0x1800ada54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ada59  mov     rcx, [rbp+38h]; this
0x1800ada5d  test    eax, eax
0x1800ada5f  jns     short loc_1800ADA76
0x1800ada61  mov     r9d, eax; char *
0x1800ada64  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ada6b  mov     edx, 18D5h; void *
0x1800ada70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ada76  lea     rcx, [rbp+var_58]
0x1800ada7a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ada7f  mov     rdi, [rbp+var_50]
0x1800ada83  mov     rax, [rdi]
0x1800ada86  mov     rbx, [rax+30h]
0x1800ada8a  lea     rcx, [rbp+var_58]
0x1800ada8e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ada93  mov     [rbp+var_18], r12
0x1800ada97  mov     r9d, 6; unsigned int
0x1800ada9d  lea     r8d, [r9+1]; unsigned int
0x1800adaa1  lea     rdx, aMarket; "Market"
0x1800adaa8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800adaac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800adab1  nop
0x1800adab2  lea     r8, [rbp+var_58]
0x1800adab6  mov     rdx, [rbp+var_18]
0x1800adaba  mov     rcx, rdi
0x1800adabd  mov     rax, rbx
0x1800adac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adac5  mov     rcx, [rbp+38h]; this
0x1800adac9  test    eax, eax
0x1800adacb  jns     short loc_1800ADAE2
0x1800adacd  mov     r9d, eax; char *
0x1800adad0  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800adad7  mov     edx, 18D8h; void *
0x1800adadc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adae2  mov     rdi, [rbp+var_58]
0x1800adae6  mov     rax, [rdi]
0x1800adae9  mov     rbx, [rax+98h]
0x1800adaf0  mov     rcx, [rbp+string]; string
0x1800adaf4  call    cs:__imp_WindowsDeleteString
0x1800adafa  mov     [rbp+string], r12
0x1800adafe  lea     rdx, [rbp+string]
0x1800adb02  mov     rcx, rdi
0x1800adb05  mov     rax, rbx
0x1800adb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb0d  mov     rcx, [rbp+38h]; this
0x1800adb11  test    eax, eax
0x1800adb13  jns     short loc_1800ADB2A
0x1800adb15  mov     r9d, eax; char *
0x1800adb18  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800adb1f  mov     edx, 18D9h; void *
0x1800adb24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adb2a  mov     rcx, [rsi]
0x1800adb2d  mov     rax, [rcx]
0x1800adb30  mov     rdx, [rbp+string]
0x1800adb34  mov     rax, [rax+130h]
0x1800adb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb40  mov     rcx, [rbp+38h]; this
  ... truncated ...
```
