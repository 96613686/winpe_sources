# SystemSettings::WorkAccess::MDMHTMLReportSetting::s_DeviceManagementWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18003a340`
- end: `0x18003a880`
- name: `?s_DeviceManagementWorker@MDMHTMLReportSetting@WorkAccess@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1344`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c970`
- `0x18001197c`
- `0x180019dfc`
- `0x180020da0`
- `0x180020dd4`
- `0x1800211a0`
- `0x180023164`
- `0x1800236d8`
- `0x180023a64`
- `0x1800291ec`
- `0x180029234`
- `0x180029708`
- `0x18002a260`
- `0x18002a2dc`
- `0x180030bd8`
- `0x18003a340`
- `0x180043030`
- `0x1800433e8`
- `0x180052010`

## import_xrefs

- `MdmDiagnostics!__imp_?CreateMdmEnterpriseDiagnosticHTMLReport@@YAJPEBG@Z` at `0x18003a51b`
- `MdmDiagnostics!__imp_?CreateMdmEnterpriseDiagnosticHTMLReport@@YAJPEBG@Z` at `0x18003a51b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a6d5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a6d5`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003a3e7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003a417`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003a3e7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18003a417`

## string_xrefs

- `0x18003a580`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall SystemSettings::WorkAccess::MDMHTMLReportSetting::s_DeviceManagementWorker(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WORK Work)
{
  char v4; // bl
  SystemSettings::WorkAccess *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  const WCHAR *v9; // rax
  _BYTE *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, _QWORD, PWSTR *); // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, PWSTR, _QWORD *); // rbx
  char v18; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v19; // [rsp+28h] [rbp-D8h] BYREF
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v26; // [rsp+68h] [rbp-98h]
  _BYTE v27[32]; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-58h]
  _BYTE v30[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[32]; // [rsp+F0h] [rbp-10h] BYREF

  WorkAccessTelemetry::ClickOnCreateReport();
  v22 = 0;
  std::wstring::wstring(v27, L"Documents\\MDMDiagnostics\\MDMDiagReport.html");
  std::wstring::wstring(v30, L"%PUBLIC%\\Documents\\MDMDiagnostics");
  v4 = *(_BYTE *)(Context[11] + 24LL);
  v18 = 0;
  v25[1] = &v18;
  v26 = 1;
  if ( SystemSettings::WorkAccess::IsDesktopSKU(v5) )
  {
LABEL_6:
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    if ( (int)SystemSettings::WorkAccess::GetDiagnosticsFolderPath(v9, (__int64)&v22) >= 0 )
    {
      LODWORD(v19) = CreateMdmEnterpriseDiagnosticHTMLReport(v22);
      WorkAccessTelemetry::HtmlReport<long &>(&v19);
      v19 = 0;
      v10 = v27;
      if ( !v4 )
        v10 = v30;
      v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
      if ( (int)wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                  v11,
                  &v19) >= 0 )
      {
        v23 = 0;
        v29 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Foundation.Uri",
          0x17u,
          0x16u);
        if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                    v29,
                    &v23) < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
          LODWORD(v19) = v18 != 0 ? 2 : 0;
          v21 = &v19;
          SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
            &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
            &v21);
          goto LABEL_21;
        }
        ppszPath = 0;
        v12 = v23;
        v13 = *(int (__fastcall **)(__int64, _QWORD, PWSTR *))(*(_QWORD *)v23 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
        v21 = v19;
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &v21);
        if ( v13(v12, *(_QWORD *)(v14 + 24), &ppszPath) < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
          LODWORD(v19) = v18 != 0 ? 2 : 0;
          v21 = &v19;
          SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
            &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
            &v21);
          goto LABEL_21;
        }
        v24 = 0;
        v29 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Launcher",
          0x18u,
          0x17u);
        v15 = v29;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        if ( (int)RoGetActivationFactory(v15, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v24) < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
          LODWORD(v19) = v18 != 0 ? 2 : 0;
          v21 = &v19;
          SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
            &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
            &v21);
          goto LABEL_21;
        }
        v25[0] = 0;
        v16 = v24;
        v17 = *(int (__fastcall **)(__int64, PWSTR, _QWORD *))(*(_QWORD *)v24 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
        if ( v17(v16, ppszPath, v25) < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
          LODWORD(v19) = v18 != 0 ? 2 : 0;
          v21 = &v19;
          SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
            &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
            &v21);
          goto LABEL_21;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      }
      v18 = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    }
    LODWORD(v19) = v18 != 0 ? 2 : 0;
    v21 = &v19;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
      &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
      &v21);
    goto LABEL_21;
  }
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  if ( SHGetKnownFolderPath(&FOLDERID_Documents, 0, 0, &ppszPath) >= 0
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszPath,
          0),
        SHGetKnownFolderPath(&FOLDERID_Documents, 0x4400u, 0, &ppszPath) >= 0) )
  {
    std::wstring::wstring(&hstringHeader, ppszPath);
    v6 = std::operator+<unsigned short>(v31, &hstringHeader, L"\\MDMDiagnostics");
    v7 = std::operator+<unsigned short>(v32, v6, L"\\MDMDiagReport.html");
    std::wstring::operator=(v27, v7);
    std::wstring::_Tidy_deallocate(v32);
    std::wstring::_Tidy_deallocate(v31);
    v8 = std::operator+<unsigned short>(v31, &hstringHeader, L"\\MDMDiagnostics");
    std::wstring::operator=(v30, v8);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    goto LABEL_6;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  LODWORD(v19) = v18 != 0 ? 2 : 0;
  v25[0] = &v19;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
    &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
    v25);
LABEL_21:
  std::wstring::_Tidy_deallocate(v30);
  std::wstring::_Tidy_deallocate(v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
}

```

## disassembly

```asm
0x18003a340  mov     [rsp-8+arg_0], rbx
0x18003a345  mov     [rsp-8+arg_8], rdi
0x18003a34a  push    rbp
0x18003a34b  lea     rbp, [rsp-20h]
0x18003a350  sub     rsp, 120h
0x18003a357  mov     rax, cs:__security_cookie
0x18003a35e  xor     rax, rsp
0x18003a361  mov     [rbp+20h+var_10], rax
0x18003a365  mov     rbx, rdx
0x18003a368  call    ?ClickOnCreateReport@WorkAccessTelemetry@@SAXXZ; WorkAccessTelemetry::ClickOnCreateReport(void)
0x18003a36d  mov     [rsp+120h+var_E0], 0
0x18003a376  lea     rdx, aDocumentsMdmdi_0; "Documents\\MDMDiagnostics\\MDMDiagRepor"...
0x18003a37d  lea     rcx, [rsp+120h+var_B0]
0x18003a382  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a387  nop
0x18003a388  lea     rdx, Src; "%PUBLIC%\\Documents\\MDMDiagnostics"
0x18003a38f  lea     rcx, [rbp+20h+var_70]
0x18003a393  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a398  nop
0x18003a399  mov     rax, [rbx+58h]
0x18003a39d  mov     bl, [rax+18h]
0x18003a3a0  mov     [rsp+120h+var_100], 0
0x18003a3a5  lea     rax, [rsp+120h+var_100]
0x18003a3aa  mov     [rsp+120h+var_C0], rax
0x18003a3af  mov     [rsp+120h+var_B8], 1
0x18003a3b4  call    ?IsDesktopSKU@WorkAccess@SystemSettings@@YA_NXZ; SystemSettings::WorkAccess::IsDesktopSKU(void)
0x18003a3b9  test    al, al
0x18003a3bb  jnz     loc_18003A4F7
0x18003a3c1  mov     [rsp+120h+ppszPath], 0
0x18003a3ca  xor     edx, edx
0x18003a3cc  lea     rcx, [rsp+120h+ppszPath]
0x18003a3d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003a3d6  lea     r9, [rsp+120h+ppszPath]; ppszPath
0x18003a3db  xor     r8d, r8d; hToken
0x18003a3de  xor     edx, edx; dwFlags
0x18003a3e0  lea     rcx, FOLDERID_Documents; rfid
0x18003a3e7  call    cs:__imp_SHGetKnownFolderPath
0x18003a3ee  nop     dword ptr [rax+rax+00h]
0x18003a3f3  test    eax, eax
0x18003a3f5  jns     short loc_18003A462
0x18003a3f7  xor     edx, edx
0x18003a3f9  lea     rcx, [rsp+120h+ppszPath]
0x18003a3fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003a403  lea     r9, [rsp+120h+ppszPath]; ppszPath
0x18003a408  xor     r8d, r8d; hToken
0x18003a40b  mov     edx, 4400h; dwFlags
0x18003a410  lea     rcx, FOLDERID_Documents; rfid
0x18003a417  call    cs:__imp_SHGetKnownFolderPath
0x18003a41e  nop     dword ptr [rax+rax+00h]
0x18003a423  test    eax, eax
0x18003a425  jns     short loc_18003A462
0x18003a427  lea     rcx, [rsp+120h+ppszPath]
0x18003a42c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a431  nop
0x18003a432  mov     al, [rsp+120h+var_100]
0x18003a436  neg     al
0x18003a438  sbb     ecx, ecx
0x18003a43a  and     ecx, 2
0x18003a43d  mov     dword ptr [rsp+120h+var_F8], ecx
0x18003a441  lea     rax, [rsp+120h+var_F8]
0x18003a446  mov     [rsp+120h+var_C8], rax
0x18003a44b  lea     rdx, [rsp+120h+var_C8]
0x18003a450  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x18003a457  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x18003a45c  nop
0x18003a45d  jmp     loc_18003A83F
0x18003a462  mov     rdx, [rsp+120h+ppszPath]
0x18003a467  lea     rcx, [rbp+20h+hstringHeader]
0x18003a46b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a470  nop
0x18003a471  lea     r8, aMdmdiagnostics_0; "\\MDMDiagnostics"
0x18003a478  lea     rdx, [rbp+20h+hstringHeader]
0x18003a47c  lea     rcx, [rbp+20h+var_50]
0x18003a480  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003a485  nop
0x18003a486  lea     r8, aMdmdiagreportH; "\\MDMDiagReport.html"
0x18003a48d  mov     rdx, rax
0x18003a490  lea     rcx, [rbp+20h+var_30]
0x18003a494  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003a499  mov     rdx, rax
0x18003a49c  lea     rcx, [rsp+120h+var_B0]
0x18003a4a1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003a4a6  lea     rcx, [rbp+20h+var_30]
0x18003a4aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a4af  nop
0x18003a4b0  lea     rcx, [rbp+20h+var_50]
0x18003a4b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a4b9  lea     r8, aMdmdiagnostics_0; "\\MDMDiagnostics"
0x18003a4c0  lea     rdx, [rbp+20h+hstringHeader]
0x18003a4c4  lea     rcx, [rbp+20h+var_50]
0x18003a4c8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003a4cd  mov     rdx, rax
0x18003a4d0  lea     rcx, [rbp+20h+var_70]
0x18003a4d4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003a4d9  lea     rcx, [rbp+20h+var_50]
0x18003a4dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a4e2  nop
0x18003a4e3  lea     rcx, [rbp+20h+hstringHeader]
0x18003a4e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a4ec  nop
0x18003a4ed  lea     rcx, [rsp+120h+ppszPath]
0x18003a4f2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a4f7  lea     rcx, [rsp+120h+var_B0]
0x18003a4fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003a501  mov     rcx, rax; pszMore
0x18003a504  lea     rdx, [rsp+120h+var_E0]
0x18003a509  call    ?GetDiagnosticsFolderPath@WorkAccess@SystemSettings@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; SystemSettings::WorkAccess::GetDiagnosticsFolderPath(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003a50e  test    eax, eax
0x18003a510  js      loc_18003A814
0x18003a516  mov     rcx, [rsp+120h+var_E0]
0x18003a51b  call    cs:__imp_?CreateMdmEnterpriseDiagnosticHTMLReport@@YAJPEBG@Z; CreateMdmEnterpriseDiagnosticHTMLReport(ushort const *)
0x18003a522  nop     dword ptr [rax+rax+00h]
0x18003a527  mov     dword ptr [rsp+120h+var_F8], eax
0x18003a52b  lea     rcx, [rsp+120h+var_F8]
0x18003a530  call    ??$HtmlReport@AEAJ@WorkAccessTelemetry@@SAXAEAJ@Z; WorkAccessTelemetry::HtmlReport<long &>(long &)
0x18003a535  mov     [rsp+120h+var_F8], 0
0x18003a53e  test    bl, bl
0x18003a540  lea     rcx, [rsp+120h+var_B0]
0x18003a545  jnz     short loc_18003A54B
0x18003a547  lea     rcx, [rbp+20h+var_70]
0x18003a54b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003a550  lea     rdx, [rsp+120h+var_F8]
0x18003a555  mov     rcx, rax
0x18003a558  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003a55d  test    eax, eax
0x18003a55f  js      loc_18003A804
0x18003a565  mov     [rsp+120h+var_D8], 0
0x18003a56e  mov     [rbp+20h+var_78], 0
0x18003a576  mov     r9d, 16h; unsigned int
0x18003a57c  lea     r8d, [r9+1]; unsigned int
0x18003a580  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18003a587  lea     rcx, [rbp+20h+hstringHeader]; hstringHeader
0x18003a58b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a590  lea     rdx, [rsp+120h+var_D8]
0x18003a595  mov     rcx, [rbp+20h+var_78]
0x18003a599  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18003a59e  test    eax, eax
0x18003a5a0  jns     short loc_18003A5E8
0x18003a5a2  lea     rcx, [rsp+120h+var_D8]
0x18003a5a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a5ac  nop
0x18003a5ad  lea     rcx, [rsp+120h+var_F8]
0x18003a5b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a5b7  nop
0x18003a5b8  mov     al, [rsp+120h+var_100]
0x18003a5bc  neg     al
0x18003a5be  sbb     ecx, ecx
0x18003a5c0  and     ecx, 2
0x18003a5c3  mov     dword ptr [rsp+120h+var_F8], ecx
0x18003a5c7  lea     rax, [rsp+120h+var_F8]
0x18003a5cc  mov     [rsp+120h+var_E8], rax
0x18003a5d1  lea     rdx, [rsp+120h+var_E8]
0x18003a5d6  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x18003a5dd  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x18003a5e2  nop
0x18003a5e3  jmp     loc_18003A83F
0x18003a5e8  mov     [rsp+120h+ppszPath], 0
0x18003a5f1  mov     rdi, [rsp+120h+var_D8]
0x18003a5f6  mov     rax, [rdi]
0x18003a5f9  mov     rbx, [rax+30h]
0x18003a5fd  lea     rcx, [rsp+120h+ppszPath]
0x18003a602  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a607  mov     rdx, [rsp+120h+var_F8]
0x18003a60c  mov     [rsp+120h+var_E8], rdx
0x18003a611  lea     rdx, [rsp+120h+var_E8]
0x18003a616  lea     rcx, [rbp+20h+var_50]
0x18003a61a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003a61f  nop
0x18003a620  lea     r8, [rsp+120h+ppszPath]
0x18003a625  mov     rdx, [rax+18h]
0x18003a629  mov     rcx, rdi
0x18003a62c  mov     rax, rbx
0x18003a62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a634  nop
0x18003a635  shr     eax, 1Fh
0x18003a638  test    al, al
0x18003a63a  jz      short loc_18003A68D
0x18003a63c  lea     rcx, [rsp+120h+ppszPath]
0x18003a641  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a646  nop
0x18003a647  lea     rcx, [rsp+120h+var_D8]
0x18003a64c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a651  nop
0x18003a652  lea     rcx, [rsp+120h+var_F8]
0x18003a657  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a65c  nop
0x18003a65d  mov     al, [rsp+120h+var_100]
0x18003a661  neg     al
0x18003a663  sbb     ecx, ecx
0x18003a665  and     ecx, 2
0x18003a668  mov     dword ptr [rsp+120h+var_F8], ecx
0x18003a66c  lea     rax, [rsp+120h+var_F8]
0x18003a671  mov     [rsp+120h+var_E8], rax
0x18003a676  lea     rdx, [rsp+120h+var_E8]
0x18003a67b  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x18003a682  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x18003a687  nop
0x18003a688  jmp     loc_18003A83F
0x18003a68d  mov     [rsp+120h+var_D0], 0
0x18003a696  mov     [rbp+20h+var_78], 0
0x18003a69e  mov     r9d, 17h; unsigned int
0x18003a6a4  lea     r8d, [r9+1]; unsigned int
0x18003a6a8  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18003a6af  lea     rcx, [rbp+20h+hstringHeader]; hstringHeader
0x18003a6b3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a6b8  mov     rbx, [rbp+20h+var_78]
0x18003a6bc  lea     rcx, [rsp+120h+var_D0]
0x18003a6c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a6c6  lea     r8, [rsp+120h+var_D0]
0x18003a6cb  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x18003a6d2  mov     rcx, rbx
0x18003a6d5  call    cs:__imp_RoGetActivationFactory
0x18003a6dc  nop     dword ptr [rax+rax+00h]
0x18003a6e1  test    eax, eax
0x18003a6e3  jns     short loc_18003A741
0x18003a6e5  lea     rcx, [rsp+120h+var_D0]
0x18003a6ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a6ef  nop
0x18003a6f0  lea     rcx, [rsp+120h+ppszPath]
0x18003a6f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a6fa  nop
0x18003a6fb  lea     rcx, [rsp+120h+var_D8]
0x18003a700  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a705  nop
0x18003a706  lea     rcx, [rsp+120h+var_F8]
0x18003a70b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a710  nop
0x18003a711  mov     al, [rsp+120h+var_100]
0x18003a715  neg     al
0x18003a717  sbb     ecx, ecx
0x18003a719  and     ecx, 2
0x18003a71c  mov     dword ptr [rsp+120h+var_F8], ecx
0x18003a720  lea     rax, [rsp+120h+var_F8]
0x18003a725  mov     [rsp+120h+var_E8], rax
0x18003a72a  lea     rdx, [rsp+120h+var_E8]
0x18003a72f  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x18003a736  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x18003a73b  nop
0x18003a73c  jmp     loc_18003A83F
0x18003a741  mov     [rsp+120h+var_C8], 0
0x18003a74a  mov     rdi, [rsp+120h+var_D0]
0x18003a74f  mov     rax, [rdi]
0x18003a752  mov     rbx, [rax+40h]
0x18003a756  lea     rcx, [rsp+120h+var_C8]
0x18003a75b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a760  lea     r8, [rsp+120h+var_C8]
0x18003a765  mov     rdx, [rsp+120h+ppszPath]
0x18003a76a  mov     rcx, rdi
0x18003a76d  mov     rax, rbx
0x18003a770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a775  nop
0x18003a776  lea     rcx, [rsp+120h+var_C8]
0x18003a77b  test    eax, eax
0x18003a77d  jns     short loc_18003A7DE
0x18003a77f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a784  nop
0x18003a785  lea     rcx, [rsp+120h+var_D0]
0x18003a78a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a78f  nop
0x18003a790  lea     rcx, [rsp+120h+ppszPath]
0x18003a795  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a79a  nop
0x18003a79b  lea     rcx, [rsp+120h+var_D8]
0x18003a7a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a7a5  nop
0x18003a7a6  lea     rcx, [rsp+120h+var_F8]
0x18003a7ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a7b0  nop
0x18003a7b1  mov     al, [rsp+120h+var_100]
0x18003a7b5  neg     al
0x18003a7b7  sbb     ecx, ecx
0x18003a7b9  and     ecx, 2
0x18003a7bc  mov     dword ptr [rsp+120h+var_F8], ecx
0x18003a7c0  lea     rax, [rsp+120h+var_F8]
0x18003a7c5  mov     [rsp+120h+var_E8], rax
0x18003a7ca  lea     rdx, [rsp+120h+var_E8]
0x18003a7cf  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x18003a7d6  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x18003a7db  nop
0x18003a7dc  jmp     short loc_18003A83F
0x18003a7de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a7e3  nop
0x18003a7e4  lea     rcx, [rsp+120h+var_D0]
0x18003a7e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a7ee  nop
0x18003a7ef  lea     rcx, [rsp+120h+ppszPath]
0x18003a7f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a7f9  nop
0x18003a7fa  lea     rcx, [rsp+120h+var_D8]
0x18003a7ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a804  mov     [rsp+120h+var_100], 1
0x18003a809  lea     rcx, [rsp+120h+var_F8]
0x18003a80e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a813  nop
0x18003a814  mov     al, [rsp+120h+var_100]
0x18003a818  neg     al
0x18003a81a  sbb     ecx, ecx
0x18003a81c  and     ecx, 2
0x18003a81f  mov     dword ptr [rsp+120h+var_F8], ecx
0x18003a823  lea     rax, [rsp+120h+var_F8]
  ... truncated ...
```
