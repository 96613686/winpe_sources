# SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog::DoWebAuth(ushort const *)

- ea: `0x1801ab77c`
- end: `0x1801abcf8`
- name: `?DoWebAuth@CorpDeviceEmailDialog@WorkplaceHandlers@SystemSettings@@AEAAJPEBG@Z`
- size: `1404`
- prototype: `int(SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801aa850`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001d624`
- `0x18002012c`
- `0x18004d124`
- `0x18004dee4`
- `0x18005019c`
- `0x1801a97d4`
- `0x1801aa0ec`
- `0x1801ab77c`
- `0x1801ad9f8`
- `0x1801adb10`
- `0x1801afdec`
- `0x1801afe88`
- `0x1801b0088`
- `0x180289010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801ab977`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801ab977`
- `USER32!GetForegroundWindow` at `0x1801ab7ff`
- `USER32!GetForegroundWindow` at `0x1801ab7ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abb67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abb7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abbd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abb67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abb7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abbd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801abc8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab9b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab9b9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801ab865`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801ab865`

## string_xrefs

- `0x1801ab838`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog::DoWebAuth(
        SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, struct Windows::Foundation::IUriRuntimeClassFactory **); // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, struct Windows::Foundation::IUriRuntimeClassFactory **); // rbx
  __int64 v14; // rax
  wchar_t *v15; // rsi
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, struct Windows::Foundation::IUriRuntimeClassFactory **); // rdi
  unsigned __int16 **v18; // r8
  int ResourceStringById; // eax
  SystemSettings::DataModel::CWebAuthHelper *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  struct Windows::Foundation::IUriRuntimeClassFactory *v23; // rdx
  const unsigned __int16 *v24; // r8
  int v26[2]; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, struct Windows::Foundation::IUriRuntimeClassFactory **); // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Foundation::IUriRuntimeClassFactory *v30; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v33[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h]
  _QWORD v37[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
  v37[0] = &CorpDeviceManagementSettingsTelemetry::WebAuth::`vftable';
  CorpDeviceManagementSettingsTelemetry::WebAuth::StartActivity((CorpDeviceManagementSettingsTelemetry::WebAuth *)v37);
  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
      (const char *)0x80070057LL,
      v26[0]);
LABEL_24:
    CorpDeviceManagementSettingsTelemetry::WebAuth::~WebAuth((CorpDeviceManagementSettingsTelemetry::WebAuth *)v37);
    return v4;
  }
  *((_QWORD *)this + 32) = GetForegroundWindow();
  v29 = 0;
  v30 = 0;
  memset(v33, 0, sizeof(v33));
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v5 = v36;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_c1d432ba_c824_4452_a7fd_512bc3bbe9a1, &v29);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26[0]);
LABEL_23:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    goto LABEL_24;
  }
  v28 = 0;
  string = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
  v8 = (*v29)[7];
  WindowsDeleteString(0);
  v28 = 0;
  v34 = *((_QWORD *)this + 43);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
  v10 = v8(v7, *(GUID **)(v9 + 24), (struct Windows::Foundation::IUriRuntimeClassFactory **)&v28);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 1002;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
      (const char *)(unsigned int)v10,
      v26[0]);
LABEL_22:
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v28);
    v28 = 0;
    goto LABEL_23;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
  v13 = (*v29)[7];
  WindowsDeleteString(string);
  string = 0;
  v34 = *((_QWORD *)this + 33);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
  v10 = v13(v12, *(GUID **)(v14 + 24), (struct Windows::Foundation::IUriRuntimeClassFactory **)&string);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 1003;
    goto LABEL_7;
  }
  v15 = wcsrchr(a2, 0x3Fu);
  WindowsGetStringRawBuffer(string, 0);
  WindowsGetStringRawBuffer(string, 0);
  v26[0] = (unsigned int)WindowsGetStringRawBuffer(v28, 0);
  v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          v33,
          L"%ws%wcappru=%ws&login_hint=%ws&username=%ws",
          a2,
          v15 != 0 ? 38 : 63);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 1011;
    goto LABEL_7;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
  v17 = **v29;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  v10 = v17(v16, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v30);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 1013;
    goto LABEL_7;
  }
  v31 = 0;
  v32 = 2;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Workplace_CorpDeviceRegistration_WebAuthTitle",
                         (const unsigned __int16 *)&hstringHeader,
                         v18);
  v4 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v21 = 1019;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
      (const char *)(unsigned int)ResourceStringById,
      v26[0]);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
    WindowsDeleteString(v31);
    v31 = 0;
    goto LABEL_22;
  }
  SystemSettings::DataModel::CWebAuthHelper::AddUrlToIntranetZone(v20, v30, v33[0]);
  *(_QWORD *)v26 = *((_QWORD *)this + 43);
  ResourceStringById = SystemSettings::DataModel::CWebAuthHelper::DoWebAuthRequest(
                         &v31,
                         *((_QWORD *)this + 32),
                         v30,
                         v33[0]);
  v4 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v21 = 1031;
    goto LABEL_21;
  }
  v22 = v32;
  *((_DWORD *)this + 62) = v32;
  if ( v22 )
  {
    *((_DWORD *)this + 132) = HIDWORD(v32);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v28);
    v28 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    CorpDeviceManagementSettingsTelemetry::WebAuth::~WebAuth((CorpDeviceManagementSettingsTelemetry::WebAuth *)v37);
    return 2147500037LL;
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 400);
    *((_QWORD *)this + 51) = -1;
    *((_QWORD *)this + 52) = -1;
    ResourceStringById = SystemSettings::DataModel::CWebAuthHelper::GetResponseTokenValue(
                           (SystemSettings::DataModel::CWebAuthHelper *)&v31,
                           v23,
                           v24,
                           (unsigned __int16 **)this + 50);
    v4 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v21 = 1037;
      goto LABEL_21;
    }
    wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v37);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v28);
    v28 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    CorpDeviceManagementSettingsTelemetry::WebAuth::~WebAuth((CorpDeviceManagementSettingsTelemetry::WebAuth *)v37);
    return 0;
  }
}

```

## disassembly

```asm
0x1801ab77c  mov     [rsp-8+arg_10], rbx
0x1801ab781  mov     [rsp-8+arg_18], rsi
0x1801ab786  push    rbp
0x1801ab787  push    rdi
0x1801ab788  push    r12
0x1801ab78a  push    r14
0x1801ab78c  push    r15
0x1801ab78e  lea     rbp, [rsp-110h]
0x1801ab796  sub     rsp, 210h
0x1801ab79d  mov     rax, cs:__security_cookie
0x1801ab7a4  xor     rax, rsp
0x1801ab7a7  mov     [rbp+130h+var_30], rax
0x1801ab7ae  mov     r15, rdx
0x1801ab7b1  mov     r14, rcx
0x1801ab7b4  lea     rcx, [rbp+130h+var_180]; struct wil::details::IFailureCallback *
0x1801ab7b8  call    ??0?$ActivityBase@VCorpDeviceManagementSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801ab7bd  lea     rax, ??_7WebAuth@CorpDeviceManagementSettingsTelemetry@@6B@; const CorpDeviceManagementSettingsTelemetry::WebAuth::`vftable'
0x1801ab7c4  mov     [rbp+130h+var_180], rax
0x1801ab7c8  lea     rcx, [rbp+130h+var_180]; this
0x1801ab7cc  call    ?StartActivity@WebAuth@CorpDeviceManagementSettingsTelemetry@@QEAAXXZ; CorpDeviceManagementSettingsTelemetry::WebAuth::StartActivity(void)
0x1801ab7d1  nop
0x1801ab7d2  xor     r12d, r12d
0x1801ab7d5  test    r15, r15
0x1801ab7d8  jnz     short loc_1801AB7FF
0x1801ab7da  mov     rcx, [rbp+138h]; this
0x1801ab7e1  mov     ebx, 80070057h
0x1801ab7e6  mov     r9d, ebx; char *
0x1801ab7e9  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ab7f0  mov     edx, 3E1h; void *
0x1801ab7f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ab7fa  jmp     loc_1801ABBAF
0x1801ab7ff  call    cs:__imp_GetForegroundWindow
0x1801ab806  nop     dword ptr [rax+rax+00h]
0x1801ab80b  mov     [r14+100h], rax
0x1801ab812  mov     [rsp+230h+var_1E0], r12
0x1801ab817  mov     [rsp+230h+var_1D8], r12
0x1801ab81c  mov     [rsp+230h+var_1C0], r12
0x1801ab821  mov     [rsp+230h+var_1B8], r12
0x1801ab826  mov     [rbp+130h+var_1B0], r12
0x1801ab82a  mov     [rbp+130h+var_188], r12
0x1801ab82e  mov     r9d, 16h; unsigned int
0x1801ab834  lea     r8d, [r9+1]; unsigned int
0x1801ab838  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1801ab83f  lea     rcx, [rbp+130h+hstringHeader]; hstringHeader
0x1801ab843  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801ab848  mov     rbx, [rbp+130h+var_188]
0x1801ab84c  lea     rcx, [rsp+230h+var_1E0]
0x1801ab851  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ab856  lea     r8, [rsp+230h+var_1E0]
0x1801ab85b  lea     rdx, _GUID_c1d432ba_c824_4452_a7fd_512bc3bbe9a1
0x1801ab862  mov     rcx, rbx
0x1801ab865  call    cs:__imp_RoGetActivationFactory
0x1801ab86c  nop     dword ptr [rax+rax+00h]
0x1801ab871  mov     ebx, eax
0x1801ab873  test    eax, eax
0x1801ab875  jns     short loc_1801AB897
0x1801ab877  mov     rcx, [rbp+138h]; this
0x1801ab87e  mov     r9d, eax; char *
0x1801ab881  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ab888  mov     edx, 3E6h; void *
0x1801ab88d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ab892  jmp     loc_1801ABB8E
0x1801ab897  mov     [rsp+230h+var_1E8], r12
0x1801ab89c  mov     [rsp+230h+string], r12
0x1801ab8a1  mov     rdi, [rsp+230h+var_1E0]
0x1801ab8a6  mov     rax, [rdi]
0x1801ab8a9  mov     rbx, [rax+38h]
0x1801ab8ad  xor     ecx, ecx; string
0x1801ab8af  call    cs:__imp_WindowsDeleteString
0x1801ab8b6  nop     dword ptr [rax+rax+00h]
0x1801ab8bb  mov     [rsp+230h+var_1E8], r12
0x1801ab8c0  mov     rdx, [r14+158h]
0x1801ab8c7  mov     [rbp+130h+var_1A8], rdx
0x1801ab8cb  lea     rdx, [rbp+130h+var_1A8]
0x1801ab8cf  lea     rcx, [rbp+130h+hstringHeader]
0x1801ab8d3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ab8d8  nop
0x1801ab8d9  lea     r8, [rsp+230h+var_1E8]
0x1801ab8de  mov     rdx, [rax+18h]
0x1801ab8e2  mov     rcx, rdi
0x1801ab8e5  mov     rax, rbx
0x1801ab8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab8ed  mov     ebx, eax
0x1801ab8ef  test    eax, eax
0x1801ab8f1  jns     short loc_1801AB913
0x1801ab8f3  mov     edx, 3EAh; void *
0x1801ab8f8  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ab8ff  mov     r9d, eax; char *
0x1801ab902  mov     rcx, [rbp+138h]; this
0x1801ab909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ab90e  jmp     loc_1801ABB62
0x1801ab913  mov     rdi, [rsp+230h+var_1E0]
0x1801ab918  mov     rax, [rdi]
0x1801ab91b  mov     rbx, [rax+38h]
0x1801ab91f  mov     rcx, [rsp+230h+string]; string
0x1801ab924  call    cs:__imp_WindowsDeleteString
0x1801ab92b  nop     dword ptr [rax+rax+00h]
0x1801ab930  mov     [rsp+230h+string], r12
0x1801ab935  mov     rdx, [r14+108h]
0x1801ab93c  mov     [rbp+130h+var_1A8], rdx
0x1801ab940  lea     rdx, [rbp+130h+var_1A8]
0x1801ab944  lea     rcx, [rbp+130h+hstringHeader]
0x1801ab948  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ab94d  nop
0x1801ab94e  lea     r8, [rsp+230h+string]
0x1801ab953  mov     rdx, [rax+18h]
0x1801ab957  mov     rcx, rdi
0x1801ab95a  mov     rax, rbx
0x1801ab95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab962  mov     ebx, eax
0x1801ab964  test    eax, eax
0x1801ab966  jns     short loc_1801AB96F
0x1801ab968  mov     edx, 3EBh
0x1801ab96d  jmp     short loc_1801AB8F8
0x1801ab96f  mov     edx, 3Fh ; '?'; Ch
0x1801ab974  mov     rcx, r15; Str
0x1801ab977  call    cs:__imp_wcsrchr
0x1801ab97e  nop     dword ptr [rax+rax+00h]
0x1801ab983  mov     rsi, rax
0x1801ab986  xor     edx, edx; length
0x1801ab988  mov     rcx, [rsp+230h+string]; string
0x1801ab98d  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ab994  nop     dword ptr [rax+rax+00h]
0x1801ab999  mov     rdi, rax
0x1801ab99c  xor     edx, edx; length
0x1801ab99e  mov     rcx, [rsp+230h+string]; string
0x1801ab9a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ab9aa  nop     dword ptr [rax+rax+00h]
0x1801ab9af  mov     rbx, rax
0x1801ab9b2  xor     edx, edx; length
0x1801ab9b4  mov     rcx, [rsp+230h+var_1E8]; string
0x1801ab9b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ab9c0  nop     dword ptr [rax+rax+00h]
0x1801ab9c5  neg     rsi
0x1801ab9c8  sbb     r9d, r9d
0x1801ab9cb  and     r9d, 0FFFFFFE7h
0x1801ab9cf  add     r9d, 3Fh ; '?'
0x1801ab9d3  mov     [rsp+230h+var_200], rdi
0x1801ab9d8  mov     [rsp+230h+var_208], rbx
0x1801ab9dd  mov     qword ptr [rsp+230h+var_210], rax
0x1801ab9e2  mov     r8, r15
0x1801ab9e5  lea     rdx, aWsWcappruWsLog; "%ws%wcappru=%ws&login_hint=%ws&username"...
0x1801ab9ec  lea     rcx, [rsp+230h+var_1C0]
0x1801ab9f1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801ab9f6  mov     ebx, eax
0x1801ab9f8  test    eax, eax
0x1801ab9fa  jns     short loc_1801ABA06
0x1801ab9fc  mov     edx, 3F3h
0x1801aba01  jmp     loc_1801AB8F8
0x1801aba06  mov     rbx, [rsp+230h+var_1E0]
0x1801aba0b  mov     rax, [rbx]
0x1801aba0e  mov     rdi, [rax]
0x1801aba11  lea     rcx, [rsp+230h+var_1D8]
0x1801aba16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801aba1b  lea     r8, [rsp+230h+var_1D8]
0x1801aba20  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1801aba27  mov     rcx, rbx
0x1801aba2a  mov     rax, rdi
0x1801aba2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aba32  mov     ebx, eax
0x1801aba34  test    eax, eax
0x1801aba36  jns     short loc_1801ABA42
0x1801aba38  mov     edx, 3F5h
0x1801aba3d  jmp     loc_1801AB8F8
0x1801aba42  mov     [rsp+230h+var_1D0], r12
0x1801aba47  mov     [rsp+230h+var_1C8], 2
0x1801aba50  mov     qword ptr [rbp+130h+hstringHeader.Reserved], r12
0x1801aba54  mov     qword ptr [rbp+130h+hstringHeader.Reserved+8], r12
0x1801aba58  mov     qword ptr [rbp+130h+hstringHeader.Reserved+10h], r12
0x1801aba5c  lea     rcx, [rbp+130h+hstringHeader]
0x1801aba60  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801aba65  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801aba69  mov     qword ptr [rbp+130h+hstringHeader.Reserved+8], rdi
0x1801aba6d  mov     qword ptr [rbp+130h+hstringHeader.Reserved+10h], rdi
0x1801aba71  lea     rdx, [rbp+130h+hstringHeader]; unsigned __int16 *
0x1801aba75  lea     rcx, aSystemsettings_1322; "SystemSettings_Workplace_CorpDeviceRegi"...
0x1801aba7c  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x1801aba81  mov     ebx, eax
0x1801aba83  test    eax, eax
0x1801aba85  jns     short loc_1801ABA91
0x1801aba87  mov     edx, 3FBh
0x1801aba8c  jmp     loc_1801ABB2B
0x1801aba91  mov     r8, [rsp+230h+var_1C0]; unsigned __int16 *
0x1801aba96  mov     rdx, [rsp+230h+var_1D8]; struct Windows::Foundation::IUriRuntimeClassFactory *
0x1801aba9b  call    ?AddUrlToIntranetZone@CWebAuthHelper@DataModel@SystemSettings@@QEAAJPEAUIUriRuntimeClassFactory@Foundation@Windows@@PEBG@Z; SystemSettings::DataModel::CWebAuthHelper::AddUrlToIntranetZone(Windows::Foundation::IUriRuntimeClassFactory *,ushort const *)
0x1801abaa0  mov     dword ptr [rsp+230h+var_200], 0Ch
0x1801abaa8  mov     rax, qword ptr [rbp+130h+hstringHeader.Reserved]
0x1801abaac  mov     [rsp+230h+var_208], rax
0x1801abab1  mov     rax, [r14+158h]
0x1801abab8  mov     qword ptr [rsp+230h+var_210], rax; int
0x1801ababd  mov     r9, [rsp+230h+var_1C0]
0x1801abac2  mov     r8, [rsp+230h+var_1D8]
0x1801abac7  mov     rdx, [r14+100h]
0x1801abace  lea     rcx, [rsp+230h+var_1D0]
0x1801abad3  call    ?DoWebAuthRequest@CWebAuthHelper@DataModel@SystemSettings@@QEAAJPEAUHWND__@@PEAUIUriRuntimeClassFactory@Foundation@Windows@@PEBG22W4WebAuthenticationOptions@Web@Authentication@Security@7@_N@Z; SystemSettings::DataModel::CWebAuthHelper::DoWebAuthRequest(HWND__ *,Windows::Foundation::IUriRuntimeClassFactory *,ushort const *,ushort const *,ushort const *,Windows::Security::Authentication::Web::WebAuthenticationOptions,bool)
0x1801abad8  mov     ebx, eax
0x1801abada  test    eax, eax
0x1801abadc  jns     short loc_1801ABAE5
0x1801abade  mov     edx, 407h
0x1801abae3  jmp     short loc_1801ABB2B
0x1801abae5  mov     eax, dword ptr [rsp+230h+var_1C8]
0x1801abae9  mov     [r14+0F8h], eax
0x1801abaf0  test    eax, eax
0x1801abaf2  jnz     loc_1801ABC46
0x1801abaf8  lea     rbx, [r14+190h]
0x1801abaff  mov     rcx, rbx
0x1801abb02  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb07  mov     [rbx+8], rdi
0x1801abb0b  mov     [rbx+10h], rdi
0x1801abb0f  mov     r9, rbx; unsigned __int16 **
0x1801abb12  lea     rcx, [rsp+230h+var_1D0]; this
0x1801abb17  call    ?GetResponseTokenValue@CWebAuthHelper@DataModel@SystemSettings@@QEAAJPEAUIUriRuntimeClassFactory@Foundation@Windows@@PEBGPEAPEAG@Z; SystemSettings::DataModel::CWebAuthHelper::GetResponseTokenValue(Windows::Foundation::IUriRuntimeClassFactory *,ushort const *,ushort * *)
0x1801abb1c  mov     ebx, eax
0x1801abb1e  test    eax, eax
0x1801abb20  jns     loc_1801ABBBF
0x1801abb26  mov     edx, 40Dh; void *
0x1801abb2b  mov     rcx, [rbp+138h]; this
0x1801abb32  mov     r9d, eax; char *
0x1801abb35  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801abb3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801abb41  nop
0x1801abb42  lea     rcx, [rbp+130h+hstringHeader]
0x1801abb46  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb4b  nop
0x1801abb4c  mov     rcx, [rsp+230h+var_1D0]; string
0x1801abb51  call    cs:__imp_WindowsDeleteString
0x1801abb58  nop     dword ptr [rax+rax+00h]
0x1801abb5d  mov     [rsp+230h+var_1D0], r12
0x1801abb62  mov     rcx, [rsp+230h+string]; string
0x1801abb67  call    cs:__imp_WindowsDeleteString
0x1801abb6e  nop     dword ptr [rax+rax+00h]
0x1801abb73  mov     [rsp+230h+string], r12
0x1801abb78  mov     rcx, [rsp+230h+var_1E8]; string
0x1801abb7d  call    cs:__imp_WindowsDeleteString
0x1801abb84  nop     dword ptr [rax+rax+00h]
0x1801abb89  mov     [rsp+230h+var_1E8], r12
0x1801abb8e  lea     rcx, [rsp+230h+var_1C0]
0x1801abb93  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb98  nop
0x1801abb99  lea     rcx, [rsp+230h+var_1D8]
0x1801abb9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801abba3  nop
0x1801abba4  lea     rcx, [rsp+230h+var_1E0]
0x1801abba9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801abbae  nop
0x1801abbaf  lea     rcx, [rbp+130h+var_180]; this
0x1801abbb3  call    ??1WebAuth@CorpDeviceManagementSettingsTelemetry@@QEAA@XZ; CorpDeviceManagementSettingsTelemetry::WebAuth::~WebAuth(void)
0x1801abbb8  mov     eax, ebx
0x1801abbba  jmp     loc_1801ABCCC
0x1801abbbf  lea     rcx, [rbp+130h+var_180]
0x1801abbc3  call    ?Stop@?$ActivityBase@VCorpDeviceManagementSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CorpDeviceManagementSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1801abbc8  nop
0x1801abbc9  lea     rcx, [rbp+130h+hstringHeader]
0x1801abbcd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abbd2  nop
0x1801abbd3  mov     rcx, [rsp+230h+var_1D0]; string
0x1801abbd8  call    cs:__imp_WindowsDeleteString
0x1801abbdf  nop     dword ptr [rax+rax+00h]
0x1801abbe4  mov     [rsp+230h+var_1D0], r12
0x1801abbe9  mov     rcx, [rsp+230h+string]; string
0x1801abbee  call    cs:__imp_WindowsDeleteString
0x1801abbf5  nop     dword ptr [rax+rax+00h]
0x1801abbfa  mov     [rsp+230h+string], r12
0x1801abbff  mov     rcx, [rsp+230h+var_1E8]; string
0x1801abc04  call    cs:__imp_WindowsDeleteString
0x1801abc0b  nop     dword ptr [rax+rax+00h]
0x1801abc10  mov     [rsp+230h+var_1E8], r12
0x1801abc15  lea     rcx, [rsp+230h+var_1C0]
0x1801abc1a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abc1f  nop
0x1801abc20  lea     rcx, [rsp+230h+var_1D8]
0x1801abc25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801abc2a  nop
0x1801abc2b  lea     rcx, [rsp+230h+var_1E0]
0x1801abc30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801abc35  nop
0x1801abc36  lea     rcx, [rbp+130h+var_180]; this
0x1801abc3a  call    ??1WebAuth@CorpDeviceManagementSettingsTelemetry@@QEAA@XZ; CorpDeviceManagementSettingsTelemetry::WebAuth::~WebAuth(void)
0x1801abc3f  xor     eax, eax
0x1801abc41  jmp     loc_1801ABCCC
0x1801abc46  mov     eax, dword ptr [rsp+230h+var_1C8+4]
0x1801abc4a  mov     [r14+210h], eax
0x1801abc51  lea     rcx, [rbp+130h+hstringHeader]
0x1801abc55  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abc5a  nop
0x1801abc5b  mov     rcx, [rsp+230h+var_1D0]; string
0x1801abc60  call    cs:__imp_WindowsDeleteString
0x1801abc67  nop     dword ptr [rax+rax+00h]
0x1801abc6c  mov     [rsp+230h+var_1D0], r12
0x1801abc71  mov     rcx, [rsp+230h+string]; string
0x1801abc76  call    cs:__imp_WindowsDeleteString
0x1801abc7d  nop     dword ptr [rax+rax+00h]
0x1801abc82  mov     [rsp+230h+string], r12
0x1801abc87  mov     rcx, [rsp+230h+var_1E8]; string
0x1801abc8c  call    cs:__imp_WindowsDeleteString
0x1801abc93  nop     dword ptr [rax+rax+00h]
0x1801abc98  mov     [rsp+230h+var_1E8], r12
0x1801abc9d  lea     rcx, [rsp+230h+var_1C0]
0x1801abca2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abca7  nop
  ... truncated ...
```
