# SystemSettings::WorkAccess::MDMExportSetting::s_DeviceManagementWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800297d0`
- end: `0x180029d74`
- name: `?s_DeviceManagementWorker@MDMExportSetting@WorkAccess@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1444`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c970`
- `0x18001197c`
- `0x180020d48`
- `0x180020da0`
- `0x180020dd4`
- `0x180020f50`
- `0x180022168`
- `0x1800222b0`
- `0x180022478`
- `0x180023164`
- `0x1800236d8`
- `0x180023a64`
- `0x1800249a0`
- `0x1800291ec`
- `0x180029234`
- `0x180029708`
- `0x1800297d0`
- `0x180043030`
- `0x1800433e8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029c92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029c92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d19`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029aa7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029c08`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029aa7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029c08`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180029865`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180029895`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180029865`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180029895`

## string_xrefs

- `0x180029bdb`: `Windows.Storage.AccessCache.StorageApplicationPermissions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::WorkAccess::MDMExportSetting::s_DeviceManagementWorker(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WORK Work)
{
  SystemSettings::WorkAccess *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  const unsigned __int16 *v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, __int64, __int64, PWSTR *); // rdi
  __int64 v12; // rbx
  const WCHAR *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  __int64 v17; // rax
  __int64 v18; // rbx
  int v19; // eax
  int (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v22; // rbx
  PWSTR v23; // rdi
  int (__fastcall *v24)(PWSTR, void (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  void (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v27; // rbx
  void (__fastcall *v28)(__int64, __int64, _QWORD, __int64, HSTRING *); // rdi
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  int (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h]
  _BYTE v41[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v43[32]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v44[4]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v45[32]; // [rsp+120h] [rbp+20h] BYREF

  WorkAccessTelemetry::ClickOnExportLogs();
  v38 = 0;
  v37 = 0;
  std::wstring::wstring(v43, L"Documents\\MDMDiagnostics");
  std::wstring::wstring(v42, L"Documents\\MDMDiagnostics\\MDMDiagReport.cab");
  std::wstring::wstring(v41, L"Documents\\MDMDiagnostics\\MDMDiagReport.zip");
  if ( !SystemSettings::WorkAccess::IsDesktopSKU(v3) )
  {
    ppszPath = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPath,
      0);
    if ( SHGetKnownFolderPath(&FOLDERID_Documents, 0, 0, &ppszPath) < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPath,
        0);
      if ( SHGetKnownFolderPath(&FOLDERID_Documents, 0x4400u, 0, &ppszPath) < 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
        goto LABEL_24;
      }
    }
    std::wstring::wstring(&hstringHeader, ppszPath);
    v4 = std::operator+<unsigned short>(v45, &hstringHeader, L"\\MDMDiagnostics");
    std::wstring::operator=(v43, v4);
    std::wstring::_Tidy_deallocate(v45);
    v5 = std::operator+<unsigned short>(v44, &hstringHeader, L"\\MDMDiagnostics");
    v6 = std::operator+<unsigned short>(v45, v5, L"\\MDMDiagReport.cab");
    std::wstring::operator=(v42, v6);
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  }
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  if ( (int)SystemSettings::WorkAccess::GetDiagnosticsFolderPath(v7) >= 0 )
  {
    v32 = 0;
    v9 = (_QWORD *)Windows::Internal::StringReference::StringReference(v44, (const unsigned __int16 (*)[56])v8);
    if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Enrollment::IReflectedEnrollment>>(
                *v9,
                &v32) >= 0 )
    {
      ppszPath = 0;
      v10 = v32;
      v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, PWSTR *))(*(_QWORD *)v32 + 312LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
      v31 = v38;
      v12 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, &v31) + 24);
      v40 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"DeviceEnrollment;DeviceProvisioning;Autopilot",
        0x2Eu,
        0x2Du);
      LODWORD(string) = v11(v10, v40, v12, &ppszPath);
      WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        ppszPath,
        0xFFFFFFFFLL);
      WorkAccessTelemetry::XmlReport<long &>(&string);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  }
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  if ( (int)SystemSettings::WorkAccess::GetDiagnosticsFolderPath(v13) >= 0 )
  {
    string = 0;
    ppszPath = 0;
    v31 = 0;
    v36 = 0;
    v35 = 0;
    v34 = 0;
    v33 = 0;
    v40 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.StorageFile",
      0x1Cu,
      0x1Bu);
    v14 = v40;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    if ( (int)RoGetActivationFactory(v14, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v34) < 0 )
      goto LABEL_12;
    v15 = v34;
    v16 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v32 = v37;
    v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, &v32);
    if ( v16(v15, *(_QWORD *)(v17 + 24), &v35) < 0 )
      goto LABEL_12;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v18 = v35;
    v19 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *>(v35);
    if ( v19 >= 0 )
      v19 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v18 + 64LL))(
              v18,
              &v33);
    if ( v19 < 0
      || (v20 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33,
          v21 = **v33,
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36),
          v21(v20, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v36) < 0) )
    {
LABEL_12:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
      WindowsDeleteString(string);
      string = 0;
    }
    else
    {
      v40 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Storage.AccessCache.StorageApplicationPermissions",
        0x3Au,
        0x39u);
      v22 = v40;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
      if ( (int)RoGetActivationFactory(v22, &GUID_4391dfaa_d033_48f9_8060_3ec847d2e3f1, &ppszPath) >= 0 )
      {
        v23 = ppszPath;
        v24 = *(int (__fastcall **)(PWSTR, void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)ppszPath + 56LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        if ( v24(v23, &v31) >= 0 )
        {
          v32 = 0;
          v25 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
          v26 = **v31;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          v26(v25, &GUID_da481ea0_ed8d_4731_a1db_e44ee2204093, &v32);
          v27 = v32;
          if ( v32 )
          {
            v28 = *(void (__fastcall **)(__int64, __int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
            WindowsDeleteString(string);
            string = 0;
            v28(v27, v36, 0, 1, &string);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppszPath);
      WindowsDeleteString(string);
    }
  }
LABEL_24:
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v42);
  std::wstring::_Tidy_deallocate(v43);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
}

```

## disassembly

```asm
0x1800297d0  push    rbp
0x1800297d2  push    rbx
0x1800297d3  push    rsi
0x1800297d4  push    rdi
0x1800297d5  push    r14
0x1800297d7  lea     rbp, [rsp-50h]
0x1800297dc  sub     rsp, 150h
0x1800297e3  mov     rax, cs:__security_cookie
0x1800297ea  xor     rax, rsp
0x1800297ed  mov     [rbp+70h+var_30], rax
0x1800297f1  call    ?ClickOnExportLogs@WorkAccessTelemetry@@SAXXZ; WorkAccessTelemetry::ClickOnExportLogs(void)
0x1800297f6  xor     r14d, r14d
0x1800297f9  mov     [rsp+170h+var_F8], r14
0x1800297fe  mov     [rsp+170h+var_100], r14
0x180029803  lea     rdx, aDocumentsMdmdi; "Documents\\MDMDiagnostics"
0x18002980a  lea     rcx, [rbp+70h+var_90]
0x18002980e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029813  nop
0x180029814  lea     rdx, aDocumentsMdmdi_1; "Documents\\MDMDiagnostics\\MDMDiagRepor"...
0x18002981b  lea     rcx, [rbp+70h+var_B0]
0x18002981f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029824  nop
0x180029825  lea     rdx, aDocumentsMdmdi_2; "Documents\\MDMDiagnostics\\MDMDiagRepor"...
0x18002982c  lea     rcx, [rbp+70h+var_D0]
0x180029830  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029835  nop
0x180029836  call    ?IsDesktopSKU@WorkAccess@SystemSettings@@YA_NXZ; SystemSettings::WorkAccess::IsDesktopSKU(void)
0x18002983b  test    al, al
0x18002983d  jnz     loc_180029948
0x180029843  mov     [rsp+170h+ppszPath], r14
0x180029848  xor     edx, edx
0x18002984a  lea     rcx, [rsp+170h+ppszPath]
0x18002984f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180029854  lea     r9, [rsp+170h+ppszPath]; ppszPath
0x180029859  xor     r8d, r8d; hToken
0x18002985c  xor     edx, edx; dwFlags
0x18002985e  lea     rcx, FOLDERID_Documents; rfid
0x180029865  call    cs:__imp_SHGetKnownFolderPath
0x18002986c  nop     dword ptr [rax+rax+00h]
0x180029871  test    eax, eax
0x180029873  jns     short loc_1800298B4
0x180029875  xor     edx, edx
0x180029877  lea     rcx, [rsp+170h+ppszPath]
0x18002987c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180029881  lea     r9, [rsp+170h+ppszPath]; ppszPath
0x180029886  xor     r8d, r8d; hToken
0x180029889  mov     edx, 4400h; dwFlags
0x18002988e  lea     rcx, FOLDERID_Documents; rfid
0x180029895  call    cs:__imp_SHGetKnownFolderPath
0x18002989c  nop     dword ptr [rax+rax+00h]
0x1800298a1  test    eax, eax
0x1800298a3  jns     short loc_1800298B4
0x1800298a5  lea     rcx, [rsp+170h+ppszPath]
0x1800298aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800298af  jmp     loc_180029D26
0x1800298b4  mov     rdx, [rsp+170h+ppszPath]
0x1800298b9  lea     rcx, [rbp+70h+hstringHeader]
0x1800298bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800298c2  nop
0x1800298c3  lea     r8, aMdmdiagnostics_0; "\\MDMDiagnostics"
0x1800298ca  lea     rdx, [rbp+70h+hstringHeader]
0x1800298ce  lea     rcx, [rbp+70h+var_50]
0x1800298d2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800298d7  mov     rdx, rax
0x1800298da  lea     rcx, [rbp+70h+var_90]
0x1800298de  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800298e3  lea     rcx, [rbp+70h+var_50]
0x1800298e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298ec  lea     r8, aMdmdiagnostics_0; "\\MDMDiagnostics"
0x1800298f3  lea     rdx, [rbp+70h+hstringHeader]
0x1800298f7  lea     rcx, [rbp+70h+var_70]
0x1800298fb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180029900  nop
0x180029901  lea     r8, aMdmdiagreportC; "\\MDMDiagReport.cab"
0x180029908  mov     rdx, rax
0x18002990b  lea     rcx, [rbp+70h+var_50]
0x18002990f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180029914  mov     rdx, rax
0x180029917  lea     rcx, [rbp+70h+var_B0]
0x18002991b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029920  lea     rcx, [rbp+70h+var_50]
0x180029924  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029929  nop
0x18002992a  lea     rcx, [rbp+70h+var_70]
0x18002992e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029933  nop
0x180029934  lea     rcx, [rbp+70h+hstringHeader]
0x180029938  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002993d  nop
0x18002993e  lea     rcx, [rsp+170h+ppszPath]
0x180029943  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029948  lea     rcx, [rbp+70h+var_D0]
0x18002994c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029951  mov     rcx, rax; pszMore
0x180029954  lea     rdx, [rsp+170h+var_F8]
0x180029959  call    ?GetDiagnosticsFolderPath@WorkAccess@SystemSettings@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; SystemSettings::WorkAccess::GetDiagnosticsFolderPath(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002995e  test    eax, eax
0x180029960  js      loc_180029A2B
0x180029966  mov     [rsp+170h+var_128], r14
0x18002996b  lea     rcx, [rbp+70h+var_70]; string
0x18002996f  call    ??$?0$0DI@@StringReference@Internal@Windows@@QEAA@AEAY0DI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[56])
0x180029974  lea     rdx, [rsp+170h+var_128]
0x180029979  mov     rcx, [rax]
0x18002997c  call    ??$ActivateInstance@V?$ComPtr@UIReflectedEnrollment@Enrollment@EnterpriseDeviceManagement@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIReflectedEnrollment@Enrollment@EnterpriseDeviceManagement@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Enrollment::IReflectedEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Enrollment::IReflectedEnrollment>>)
0x180029981  test    eax, eax
0x180029983  js      loc_180029A21
0x180029989  mov     [rsp+170h+ppszPath], r14
0x18002998e  mov     rsi, [rsp+170h+var_128]
0x180029993  mov     rax, [rsi]
0x180029996  mov     rdi, [rax+138h]
0x18002999d  lea     rcx, [rsp+170h+ppszPath]
0x1800299a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800299a7  mov     rax, [rsp+170h+var_F8]
0x1800299ac  mov     [rsp+170h+var_130], rax
0x1800299b1  lea     rdx, [rsp+170h+var_130]
0x1800299b6  lea     rcx, [rbp+70h+var_70]
0x1800299ba  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800299bf  nop
0x1800299c0  mov     rbx, [rax+18h]
0x1800299c4  mov     [rbp+70h+var_D8], r14
0x1800299c8  mov     r9d, 2Dh ; '-'; unsigned int
0x1800299ce  lea     r8d, [r9+1]; unsigned int
0x1800299d2  lea     rdx, aDeviceenrollme; "DeviceEnrollment;DeviceProvisioning;Aut"...
0x1800299d9  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x1800299dd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800299e2  nop
0x1800299e3  lea     r9, [rsp+170h+ppszPath]
0x1800299e8  mov     r8, rbx
0x1800299eb  mov     rdx, [rbp+70h+var_D8]
0x1800299ef  mov     rcx, rsi
0x1800299f2  mov     rax, rdi
0x1800299f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299fa  mov     dword ptr [rsp+170h+string], eax
0x1800299fe  or      edx, 0FFFFFFFFh
0x180029a01  mov     rcx, [rsp+170h+ppszPath]
0x180029a06  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180029a0b  lea     rcx, [rsp+170h+string]
0x180029a10  call    ??$XmlReport@AEAJ@WorkAccessTelemetry@@SAXAEAJ@Z; WorkAccessTelemetry::XmlReport<long &>(long &)
0x180029a15  nop
0x180029a16  lea     rcx, [rsp+170h+ppszPath]
0x180029a1b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a20  nop
0x180029a21  lea     rcx, [rsp+170h+var_128]
0x180029a26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a2b  lea     rcx, [rbp+70h+var_D0]
0x180029a2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029a34  mov     rcx, rax; pszMore
0x180029a37  lea     rdx, [rsp+170h+var_100]
0x180029a3c  call    ?GetDiagnosticsFolderPath@WorkAccess@SystemSettings@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; SystemSettings::WorkAccess::GetDiagnosticsFolderPath(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180029a41  test    eax, eax
0x180029a43  js      loc_180029D26
0x180029a49  mov     [rsp+170h+string], r14
0x180029a4e  mov     [rsp+170h+ppszPath], r14
0x180029a53  mov     [rsp+170h+var_130], r14
0x180029a58  mov     [rsp+170h+var_108], r14
0x180029a5d  mov     [rsp+170h+var_110], r14
0x180029a62  mov     [rsp+170h+var_118], r14
0x180029a67  mov     [rsp+170h+var_120], r14
0x180029a6c  mov     [rbp+70h+var_D8], r14
0x180029a70  mov     r9d, 1Bh; unsigned int
0x180029a76  lea     r8d, [r9+1]; unsigned int
0x180029a7a  lea     rdx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x180029a81  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x180029a85  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029a8a  mov     rbx, [rbp+70h+var_D8]
0x180029a8e  lea     rcx, [rsp+170h+var_118]
0x180029a93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029a98  lea     r8, [rsp+170h+var_118]
0x180029a9d  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x180029aa4  mov     rcx, rbx
0x180029aa7  call    cs:__imp_RoGetActivationFactory
0x180029aae  nop     dword ptr [rax+rax+00h]
0x180029ab3  test    eax, eax
0x180029ab5  jns     short loc_180029B14
0x180029ab7  lea     rcx, [rsp+170h+var_120]
0x180029abc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029ac1  nop
0x180029ac2  lea     rcx, [rsp+170h+var_118]
0x180029ac7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029acc  nop
0x180029acd  lea     rcx, [rsp+170h+var_110]
0x180029ad2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029ad7  nop
0x180029ad8  lea     rcx, [rsp+170h+var_108]
0x180029add  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029ae2  nop
0x180029ae3  lea     rcx, [rsp+170h+var_130]
0x180029ae8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029aed  nop
0x180029aee  lea     rcx, [rsp+170h+ppszPath]
0x180029af3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029af8  nop
0x180029af9  mov     rcx, [rsp+170h+string]; string
0x180029afe  call    cs:__imp_WindowsDeleteString
0x180029b05  nop     dword ptr [rax+rax+00h]
0x180029b0a  mov     [rsp+170h+string], r14
0x180029b0f  jmp     loc_180029D26
0x180029b14  mov     rdi, [rsp+170h+var_118]
0x180029b19  mov     rax, [rdi]
0x180029b1c  mov     rbx, [rax+30h]
0x180029b20  lea     rcx, [rsp+170h+var_110]
0x180029b25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029b2a  mov     rdx, [rsp+170h+var_100]
0x180029b2f  mov     [rsp+170h+var_128], rdx
0x180029b34  lea     rdx, [rsp+170h+var_128]
0x180029b39  lea     rcx, [rbp+70h+var_70]
0x180029b3d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180029b42  nop
0x180029b43  lea     r8, [rsp+170h+var_110]
0x180029b48  mov     rdx, [rax+18h]
0x180029b4c  mov     rcx, rdi
0x180029b4f  mov     rax, rbx
0x180029b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b57  nop
0x180029b58  test    eax, eax
0x180029b5a  js      loc_180029AB7
0x180029b60  lea     rcx, [rsp+170h+var_120]
0x180029b65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029b6a  mov     rbx, [rsp+170h+var_110]
0x180029b6f  mov     rcx, rbx
0x180029b72  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180029b77  test    eax, eax
0x180029b79  js      short loc_180029B90
0x180029b7b  mov     rax, [rbx]
0x180029b7e  lea     rdx, [rsp+170h+var_120]
0x180029b83  mov     rcx, rbx
0x180029b86  mov     rax, [rax+40h]
0x180029b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b8f  nop
0x180029b90  test    eax, eax
0x180029b92  js      loc_180029AB7
0x180029b98  mov     rbx, [rsp+170h+var_120]
0x180029b9d  mov     rax, [rbx]
0x180029ba0  mov     rdi, [rax]
0x180029ba3  lea     rcx, [rsp+170h+var_108]
0x180029ba8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029bad  lea     r8, [rsp+170h+var_108]
0x180029bb2  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180029bb9  mov     rcx, rbx
0x180029bbc  mov     rax, rdi
0x180029bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bc4  nop
0x180029bc5  test    eax, eax
0x180029bc7  js      loc_180029AB7
0x180029bcd  mov     [rbp+70h+var_D8], r14
0x180029bd1  mov     r9d, 39h ; '9'; unsigned int
0x180029bd7  lea     r8d, [r9+1]; unsigned int
0x180029bdb  lea     rdx, ?RuntimeClass_Windows_Storage_AccessCache_StorageApplicationPermissions@@3QBGB; "Windows.Storage.AccessCache.StorageAppl"...
0x180029be2  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x180029be6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029beb  mov     rbx, [rbp+70h+var_D8]
0x180029bef  lea     rcx, [rsp+170h+ppszPath]
0x180029bf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029bf9  lea     r8, [rsp+170h+ppszPath]
0x180029bfe  lea     rdx, _GUID_4391dfaa_d033_48f9_8060_3ec847d2e3f1
0x180029c05  mov     rcx, rbx
0x180029c08  call    cs:__imp_RoGetActivationFactory
0x180029c0f  nop     dword ptr [rax+rax+00h]
0x180029c14  test    eax, eax
0x180029c16  js      loc_180029CD2
0x180029c1c  mov     rdi, [rsp+170h+ppszPath]
0x180029c21  mov     rax, [rdi]
0x180029c24  mov     rbx, [rax+38h]
0x180029c28  lea     rcx, [rsp+170h+var_130]
0x180029c2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029c32  lea     rdx, [rsp+170h+var_130]
0x180029c37  mov     rcx, rdi
0x180029c3a  mov     rax, rbx
0x180029c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c42  test    eax, eax
0x180029c44  js      loc_180029CD2
0x180029c4a  mov     [rsp+170h+var_128], r14
0x180029c4f  mov     rbx, [rsp+170h+var_130]
0x180029c54  mov     rax, [rbx]
0x180029c57  mov     rdi, [rax]
0x180029c5a  lea     rcx, [rsp+170h+var_128]
0x180029c5f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029c64  lea     r8, [rsp+170h+var_128]
0x180029c69  lea     rdx, _GUID_da481ea0_ed8d_4731_a1db_e44ee2204093
0x180029c70  mov     rcx, rbx
0x180029c73  mov     rax, rdi
0x180029c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c7b  nop
0x180029c7c  mov     rbx, [rsp+170h+var_128]
0x180029c81  test    rbx, rbx
0x180029c84  jz      short loc_180029CC7
0x180029c86  mov     rax, [rbx]
0x180029c89  mov     rdi, [rax+30h]
0x180029c8d  mov     rcx, [rsp+170h+string]; string
0x180029c92  call    cs:__imp_WindowsDeleteString
0x180029c99  nop     dword ptr [rax+rax+00h]
0x180029c9e  mov     [rsp+170h+string], r14
0x180029ca3  lea     rax, [rsp+170h+string]
0x180029ca8  mov     [rsp+170h+var_150], rax
0x180029cad  mov     r9d, 1
0x180029cb3  xor     r8d, r8d
0x180029cb6  mov     rdx, [rsp+170h+var_108]
0x180029cbb  mov     rcx, rbx
0x180029cbe  mov     rax, rdi
0x180029cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
