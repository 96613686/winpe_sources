# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800cd634`
- end: `0x1800cde09`
- name: `?_StartBundleProductInstallWithOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EE1PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `2005`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800c3bb0`
- `0x1800c4c70`
- `0x1800c4ed0`
- `0x1800c5180`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18002ec2c`
- `0x180037200`
- `0x1800375c0`
- `0x18003f848`
- `0x180045588`
- `0x18004615c`
- `0x18008fc28`
- `0x1800ab6c4`
- `0x1800b7cb8`
- `0x1800c893c`
- `0x1800cd008`
- `0x1800cd04c`
- `0x1800cd634`
- `0x180105afc`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800cdbf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800cdbf7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800cdbca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800cdbca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd8f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdcdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cddc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd8f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdcdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cddc7`

## string_xrefs

- `0x1800cd780`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cd800`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cd8d8`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cdc6a`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8,
        char a9,
        __int64 a10,
        int (__fastcall ***a11)(_QWORD, GUID *, __int64 *),
        __int64 a12)
{
  __int64 v13; // r13
  RTL_SRWLOCK *v14; // r15
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  int (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  int v20; // eax
  unsigned int started; // ebx
  __int64 v22; // rdx
  int (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v33; // rcx
  bool ShouldUseInstallControl2; // al
  int InstallControl2; // ebx
  CorrelationVector *v37; // rcx
  PVOID Ptr; // rbx
  __int64 (__fastcall *v39)(PVOID, __int64, __int64, HSTRING); // rdi
  CorrelationVector *v40; // rcx
  int v41; // eax
  const char *v42; // r9
  int StartProductInstallOptions; // eax
  const char *v44; // r9
  int v45; // r12d
  int v46; // ebx
  int v47; // edi
  __int64 v48; // rsi
  HSTRING v49; // rax
  int v50; // [rsp+28h] [rbp-2F0h]
  int v51; // [rsp+20h] [rbp-2F8h]
  HSTRING v52; // [rsp+70h] [rbp-2A8h] BYREF
  HSTRING string; // [rsp+78h] [rbp-2A0h] BYREF
  __int64 v54; // [rsp+80h] [rbp-298h] BYREF
  HSTRING v55; // [rsp+88h] [rbp-290h] BYREF
  HSTRING v56; // [rsp+90h] [rbp-288h] BYREF
  __int64 v57; // [rsp+98h] [rbp-280h] BYREF
  int v58; // [rsp+A0h] [rbp-278h] BYREF
  int v59; // [rsp+A4h] [rbp-274h] BYREF
  int v60[2]; // [rsp+A8h] [rbp-270h]
  __int64 v61; // [rsp+B0h] [rbp-268h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-260h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-258h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-250h]
  PVOID v65; // [rsp+D0h] [rbp-248h] BYREF
  RTL_SRWLOCK *v66; // [rsp+D8h] [rbp-240h]
  int (__fastcall ***v67)(_QWORD, _QWORD, _QWORD); // [rsp+E0h] [rbp-238h]
  char v68[8]; // [rsp+E8h] [rbp-230h] BYREF
  char v69[8]; // [rsp+F0h] [rbp-228h] BYREF
  char v70[8]; // [rsp+F8h] [rbp-220h] BYREF
  char v71[8]; // [rsp+100h] [rbp-218h] BYREF
  char v72[8]; // [rsp+108h] [rbp-210h] BYREF
  char v73[8]; // [rsp+110h] [rbp-208h] BYREF
  char v74[8]; // [rsp+118h] [rbp-200h] BYREF
  __int64 v75; // [rsp+120h] [rbp-1F8h]
  __int64 v76; // [rsp+128h] [rbp-1F0h]
  __int64 v77; // [rsp+130h] [rbp-1E8h]
  __int64 v78; // [rsp+138h] [rbp-1E0h]
  const winrt::hresult_error *v79; // [rsp+140h] [rbp-1D8h] BYREF
  __int64 v80[4]; // [rsp+148h] [rbp-1D0h] BYREF
  __int64 v81[4]; // [rsp+168h] [rbp-1B0h] BYREF
  __int64 v82[4]; // [rsp+188h] [rbp-190h] BYREF
  __int64 v83[4]; // [rsp+1A8h] [rbp-170h] BYREF
  __int64 v84; // [rsp+1C8h] [rbp-150h] BYREF
  __int64 v85; // [rsp+1E8h] [rbp-130h] BYREF
  __int64 v86; // [rsp+208h] [rbp-110h] BYREF
  _BYTE v87[160]; // [rsp+230h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v64 = a4;
  v13 = a3;
  v14 = a1;
  v66 = a1;
  v78 = a2;
  v61 = a3;
  v62 = a4;
  v77 = a5;
  v76 = a6;
  *(_QWORD *)v60 = a7;
  v63 = a7;
  v15 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a11;
  v67 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a11;
  v75 = a12;
  v57 = 0;
  v59 = 0;
  v58 = 0;
  string = 0;
  CorrelationVector::GenerateIfMissingOrInvalid(v87, a10);
  if ( a11 )
  {
    v19 = (*a11)[6];
    WindowsDeleteString(string);
    string = 0;
    v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))v19)(a11, &string);
    started = v20;
    if ( v20 < 0 )
    {
      v22 = 5230;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v20,
        v51);
      goto LABEL_19;
    }
    v23 = (*a11)[14];
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v57);
    v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v23)(a11, &v57);
    started = v20;
    if ( v20 < 0 )
    {
      v22 = 5231;
      goto LABEL_6;
    }
    v54 = 0;
    v24 = **a11;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
    if ( v24(a11, &GUID_8a04c0d7_c94b_425e_95b4_bf27faeaee89, &v54) >= 0 )
    {
      v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v54 + 112LL))(v54, &v59);
      started = v25;
      if ( v25 < 0 )
      {
        v26 = 5236;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v25,
          v51);
LABEL_18:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
        goto LABEL_19;
      }
      v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v54 + 96LL))(v54, &v58);
      started = v25;
      if ( v25 < 0 )
      {
        v26 = 5237;
        goto LABEL_10;
      }
      v55 = 0;
      v52 = 0;
      v27 = v54;
      v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 160LL);
      WindowsDeleteString(0);
      v55 = 0;
      v29 = v28(v27, &v55);
      started = v29;
      if ( v29 < 0 )
      {
        v30 = 5242;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v29,
          v51);
        WindowsDeleteString(v52);
        v52 = 0;
        WindowsDeleteString(v55);
        v55 = 0;
        goto LABEL_18;
      }
      v31 = v54;
      v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 176LL);
      WindowsDeleteString(v52);
      v52 = 0;
      v29 = v32(v31, &v52);
      started = v29;
      if ( v29 < 0 )
      {
        v30 = 5243;
        goto LABEL_17;
      }
      if ( v55 || v52 )
      {
        ShouldUseInstallControl2 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(v33);
        try
        {
          if ( ShouldUseInstallControl2 )
          {
            try
            {
              InstallControl2 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                                  v14,
                                  &v65);
              v37 = CorrelationVector::Increment((CorrelationVector *)v87);
              v56 = CorrelationVector::hstring(v37);
              v80[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v73, &v56);
              v56 = v52;
              v81[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v72, &v56);
              v56 = v55;
              v82[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v71, &v56);
              v83[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v70, &v63);
              v56 = string;
              v84 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v69, &v56);
              v85 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v68, &v62);
              v86 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v74, &v61);
              winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::PostCampaignDataForInstall(
                InstallControl2,
                (unsigned int)&v86,
                (unsigned int)&v85,
                (unsigned int)&v84,
                (__int64)v83,
                (__int64)v82,
                (__int64)v81,
                (__int64)v80);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v74);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v68);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v69);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v70);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v71);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v72);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v73);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v65);
            }
            catch ( const winrt::hresult_error *v79 )
            {
              TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                0x148Cu,
                "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductIns"
                "tallWithOptionsAsync",
                "ex.code()",
                *((_DWORD *)v79 + 3),
                v50);
              v14 = v66;
              v13 = v61;
              v64 = v62;
              *(_QWORD *)v60 = v63;
              v15 = v67;
            }
          }
          else
          {
            AcquireSRWLockShared(v14 + 30);
            Ptr = v14[33].Ptr;
            v65 = Ptr;
            if ( Ptr )
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
            ReleaseSRWLockShared(v14 + 30);
            v39 = *(__int64 (__fastcall **)(PVOID, __int64, __int64, HSTRING))(*(_QWORD *)Ptr + 240LL);
            v40 = CorrelationVector::Increment((CorrelationVector *)v87);
            CorrelationVector::hstring(v40);
            v51 = v60[0];
            v41 = v39(Ptr, v13, a4, string);
            if ( v41 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x149C,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                (const char *)(unsigned int)v41,
                v51);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v65);
          }
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x149F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
            v42);
          v14 = v66;
          v13 = v61;
          v64 = v62;
          *(_QWORD *)v60 = v63;
          v15 = v67;
        }
      }
      WindowsDeleteString(v52);
      v52 = 0;
      WindowsDeleteString(v55);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  }
  try
  {
    LOBYTE(v51) = 0;
    LOBYTE(v17) = a8;
    LOBYTE(v18) = a8;
    LOBYTE(v16) = a9;
    StartProductInstallOptions = GetStartProductInstallOptions(v17, v16, 0, v18, v51, v15);
  }
  catch ( ... )
  {
    LODWORD(v52) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x14B2,
                     (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                     v44);
    CorrelationVector::~CorrelationVector((CorrelationVector *)v87);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v57);
    return (unsigned int)v52;
  }
  v45 = StartProductInstallOptions;
  v46 = v58;
  v47 = v59;
  v48 = v57;
  v49 = CorrelationVector::hstring((CorrelationVector *)v87);
  started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(
              v14,
              v78,
              v13,
              v64,
              v77,
              string,
              v76,
              *(_QWORD *)v60,
              v49,
              v48,
              v45,
              v47,
              v46,
              v75);
LABEL_19:
  CorrelationVector::~CorrelationVector((CorrelationVector *)v87);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v57);
  return started;
}

```

## disassembly

```asm
0x1800cd634  mov     r11, rsp
0x1800cd637  push    rbx
0x1800cd638  push    rsi
0x1800cd639  push    rdi
0x1800cd63a  push    r12
0x1800cd63c  push    r13
0x1800cd63e  push    r14
0x1800cd640  push    r15
0x1800cd642  sub     rsp, 2E0h
0x1800cd649  mov     rax, cs:__security_cookie
0x1800cd650  xor     rax, rsp
0x1800cd653  mov     [rsp+318h+var_48], rax
0x1800cd65b  mov     r12, r9
0x1800cd65e  mov     [r11-250h], r9
0x1800cd665  mov     r13, r8
0x1800cd668  mov     r15, rcx
0x1800cd66b  mov     [rsp+318h+var_240], rcx
0x1800cd673  mov     [rsp+318h+var_1E0], rdx
0x1800cd67b  mov     [r11-268h], r8
0x1800cd682  mov     [r11-260h], r9
0x1800cd689  mov     rax, [rsp+318h+arg_20]
0x1800cd691  mov     [rsp+318h+var_1E8], rax
0x1800cd699  mov     rax, [rsp+318h+arg_28]
0x1800cd6a1  mov     [rsp+318h+var_1F0], rax
0x1800cd6a9  mov     rdi, [rsp+318h+arg_30]
0x1800cd6b1  mov     [r11-270h], rdi
0x1800cd6b8  mov     [r11-258h], rdi
0x1800cd6bf  mov     rdx, [rsp+318h+arg_48]
0x1800cd6c7  mov     rsi, [rsp+318h+arg_50]
0x1800cd6cf  mov     [rsp+318h+var_238], rsi
0x1800cd6d7  mov     rax, [rsp+318h+arg_58]
0x1800cd6df  mov     [rsp+318h+var_1F8], rax
0x1800cd6e7  xor     r14d, r14d
0x1800cd6ea  mov     [r11-280h], r14
0x1800cd6f1  mov     [r11-274h], r14d
0x1800cd6f8  mov     [r11-278h], r14d
0x1800cd6ff  mov     [rsp+318h+string], r14
0x1800cd704  lea     rcx, [r11-0E8h]
0x1800cd70b  call    ?GenerateIfMissingOrInvalid@CorrelationVector@@SA?AV1@PEAUHSTRING__@@@Z; CorrelationVector::GenerateIfMissingOrInvalid(HSTRING__ *)
0x1800cd710  nop
0x1800cd711  test    rsi, rsi
0x1800cd714  jz      loc_1800CDCF4
0x1800cd71a  mov     rax, [rsi]
0x1800cd71d  mov     rbx, [rax+30h]
0x1800cd721  mov     rcx, [rsp+318h+string]; string
0x1800cd726  call    cs:__imp_WindowsDeleteString
0x1800cd72c  mov     [rsp+318h+string], r14
0x1800cd731  lea     rdx, [rsp+318h+string]
0x1800cd736  mov     rcx, rsi
0x1800cd739  mov     rax, rbx
0x1800cd73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd741  mov     ebx, eax
0x1800cd743  test    eax, eax
0x1800cd745  jns     short loc_1800CD74E
0x1800cd747  mov     edx, 146Eh
0x1800cd74c  jmp     short loc_1800CD780
0x1800cd74e  mov     rax, [rsi]
0x1800cd751  mov     rbx, [rax+70h]
0x1800cd755  lea     rcx, [rsp+318h+var_280]
0x1800cd75d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd762  lea     rdx, [rsp+318h+var_280]
0x1800cd76a  mov     rcx, rsi
0x1800cd76d  mov     rax, rbx
0x1800cd770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd775  mov     ebx, eax
0x1800cd777  test    eax, eax
0x1800cd779  jns     short loc_1800CD79C
0x1800cd77b  mov     edx, 146Fh; void *
0x1800cd780  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800cd787  mov     r9d, eax; char *
0x1800cd78a  mov     rcx, [rsp+318h]; this
0x1800cd792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd797  jmp     loc_1800CD921
0x1800cd79c  mov     [rsp+318h+var_298], r14
0x1800cd7a4  mov     rax, [rsi]
0x1800cd7a7  mov     rbx, [rax]
0x1800cd7aa  lea     rcx, [rsp+318h+var_298]
0x1800cd7b2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd7b7  lea     r8, [rsp+318h+var_298]
0x1800cd7bf  lea     rdx, _GUID_8a04c0d7_c94b_425e_95b4_bf27faeaee89
0x1800cd7c6  mov     rcx, rsi
0x1800cd7c9  mov     rax, rbx
0x1800cd7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd7d1  test    eax, eax
0x1800cd7d3  js      loc_1800CDCE6
0x1800cd7d9  mov     rcx, [rsp+318h+var_298]
0x1800cd7e1  mov     rax, [rcx]
0x1800cd7e4  lea     rdx, [rsp+318h+var_274]
0x1800cd7ec  mov     rax, [rax+70h]
0x1800cd7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd7f5  mov     ebx, eax
0x1800cd7f7  test    eax, eax
0x1800cd7f9  jns     short loc_1800CD81C
0x1800cd7fb  mov     edx, 1474h; void *
0x1800cd800  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800cd807  mov     r9d, eax; char *
0x1800cd80a  mov     rcx, [rsp+318h]; this
0x1800cd812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd817  jmp     loc_1800CD913
0x1800cd81c  mov     rcx, [rsp+318h+var_298]
0x1800cd824  mov     rax, [rcx]
0x1800cd827  lea     rdx, [rsp+318h+var_278]
0x1800cd82f  mov     rax, [rax+60h]
0x1800cd833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd838  mov     ebx, eax
0x1800cd83a  test    eax, eax
0x1800cd83c  jns     short loc_1800CD845
0x1800cd83e  mov     edx, 1475h
0x1800cd843  jmp     short loc_1800CD800
0x1800cd845  mov     [rsp+318h+var_290], r14
0x1800cd84d  mov     [rsp+318h+var_2A8], r14
0x1800cd852  mov     rdi, [rsp+318h+var_298]
0x1800cd85a  mov     rax, [rdi]
0x1800cd85d  mov     rbx, [rax+0A0h]
0x1800cd864  xor     ecx, ecx; string
0x1800cd866  call    cs:__imp_WindowsDeleteString
0x1800cd86c  mov     [rsp+318h+var_290], r14
0x1800cd874  lea     rdx, [rsp+318h+var_290]
0x1800cd87c  mov     rcx, rdi
0x1800cd87f  mov     rax, rbx
0x1800cd882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd887  mov     ebx, eax
0x1800cd889  test    eax, eax
0x1800cd88b  jns     short loc_1800CD894
0x1800cd88d  mov     edx, 147Ah
0x1800cd892  jmp     short loc_1800CD8D5
0x1800cd894  mov     rdi, [rsp+318h+var_298]
0x1800cd89c  mov     rax, [rdi]
0x1800cd89f  mov     rbx, [rax+0B0h]
0x1800cd8a6  mov     rcx, [rsp+318h+var_2A8]; string
0x1800cd8ab  call    cs:__imp_WindowsDeleteString
0x1800cd8b1  mov     [rsp+318h+var_2A8], r14
0x1800cd8b6  lea     rdx, [rsp+318h+var_2A8]
0x1800cd8bb  mov     rcx, rdi
0x1800cd8be  mov     rax, rbx
0x1800cd8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8c6  mov     ebx, eax
0x1800cd8c8  test    eax, eax
0x1800cd8ca  jns     loc_1800CD953
0x1800cd8d0  mov     edx, 147Bh; void *
0x1800cd8d5  mov     r9d, eax; char *
0x1800cd8d8  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800cd8df  mov     rcx, [rsp+318h]; this
0x1800cd8e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd8ec  nop
0x1800cd8ed  mov     rcx, [rsp+318h+var_2A8]; string
0x1800cd8f2  call    cs:__imp_WindowsDeleteString
0x1800cd8f8  mov     [rsp+318h+var_2A8], r14
0x1800cd8fd  mov     rcx, [rsp+318h+var_290]; string
0x1800cd905  call    cs:__imp_WindowsDeleteString
0x1800cd90b  mov     [rsp+318h+var_290], r14
0x1800cd913  lea     rcx, [rsp+318h+var_298]
0x1800cd91b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd920  nop
0x1800cd921  lea     rcx, [rsp+318h+var_E8]; this
0x1800cd929  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x1800cd92e  nop
0x1800cd92f  mov     rcx, [rsp+318h+string]; string
0x1800cd934  call    cs:__imp_WindowsDeleteString
0x1800cd93a  mov     [rsp+318h+string], r14
0x1800cd93f  lea     rcx, [rsp+318h+var_280]
0x1800cd947  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd94c  mov     eax, ebx
0x1800cd94e  jmp     loc_1800CDDE6
0x1800cd953  cmp     [rsp+318h+var_290], r14
0x1800cd95b  jnz     short loc_1800CD968
0x1800cd95d  cmp     [rsp+318h+var_2A8], r14
0x1800cd962  jz      loc_1800CDCC7
0x1800cd968  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x1800cd96d  test    al, al
0x1800cd96f  jz      loc_1800CDBC0
0x1800cd975  lea     rdx, [rsp+318h+var_248]
0x1800cd97d  mov     rcx, r15
0x1800cd980  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800cd985  mov     rbx, rax
0x1800cd988  lea     rcx, [rsp+318h+var_E8]; this
0x1800cd990  call    ?Increment@CorrelationVector@@QEAAAEAV1@XZ; CorrelationVector::Increment(void)
0x1800cd995  mov     rcx, rax; this
0x1800cd998  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x1800cd99d  mov     [rsp+318h+var_288], rax
0x1800cd9a5  lea     rdx, [rsp+318h+var_288]
0x1800cd9ad  lea     rcx, [rsp+318h+var_208]
0x1800cd9b5  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cd9ba  nop
0x1800cd9bb  mov     rax, [rax]
0x1800cd9be  mov     [rsp+318h+var_1D0], rax
0x1800cd9c6  mov     rax, [rsp+318h+var_2A8]
0x1800cd9cb  mov     [rsp+318h+var_288], rax
0x1800cd9d3  lea     rdx, [rsp+318h+var_288]
0x1800cd9db  lea     rcx, [rsp+318h+var_210]
0x1800cd9e3  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cd9e8  nop
0x1800cd9e9  mov     rax, [rax]
0x1800cd9ec  mov     [rsp+318h+var_1B0], rax
0x1800cd9f4  mov     rax, [rsp+318h+var_290]
0x1800cd9fc  mov     [rsp+318h+var_288], rax
0x1800cda04  lea     rdx, [rsp+318h+var_288]
0x1800cda0c  lea     rcx, [rsp+318h+var_218]
0x1800cda14  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cda19  nop
0x1800cda1a  mov     rax, [rax]
0x1800cda1d  mov     [rsp+318h+var_190], rax
0x1800cda25  lea     rdx, [rsp+318h+var_258]
0x1800cda2d  lea     rcx, [rsp+318h+var_220]
0x1800cda35  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cda3a  nop
0x1800cda3b  mov     rax, [rax]
0x1800cda3e  mov     [rsp+318h+var_170], rax
0x1800cda46  mov     rax, [rsp+318h+string]
0x1800cda4b  mov     [rsp+318h+var_288], rax
0x1800cda53  lea     rdx, [rsp+318h+var_288]
0x1800cda5b  lea     rcx, [rsp+318h+var_228]
0x1800cda63  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cda68  nop
0x1800cda69  mov     rax, [rax]
0x1800cda6c  mov     [rsp+318h+var_150], rax
0x1800cda74  lea     rdx, [rsp+318h+var_260]
0x1800cda7c  lea     rcx, [rsp+318h+var_230]
0x1800cda84  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cda89  nop
0x1800cda8a  mov     rax, [rax]
0x1800cda8d  mov     [rsp+318h+var_130], rax
0x1800cda95  lea     rdx, [rsp+318h+var_268]
0x1800cda9d  lea     rcx, [rsp+318h+var_200]
0x1800cdaa5  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800cdaaa  nop
0x1800cdaab  mov     rax, [rax]
0x1800cdaae  mov     [rsp+318h+var_110], rax
0x1800cdab6  lea     rax, [rsp+318h+var_1D0]
0x1800cdabe  mov     [rsp+318h+var_2E0], rax
0x1800cdac3  lea     rax, [rsp+318h+var_1B0]
0x1800cdacb  mov     [rsp+318h+var_2E8], rax
0x1800cdad0  lea     rax, [rsp+318h+var_190]
0x1800cdad8  mov     [rsp+318h+var_2F0], rax
0x1800cdadd  lea     rax, [rsp+318h+var_170]
0x1800cdae5  mov     qword ptr [rsp+318h+var_2F8], rax
0x1800cdaea  lea     r9, [rsp+318h+var_150]
0x1800cdaf2  lea     r8, [rsp+318h+var_130]
0x1800cdafa  lea     rdx, [rsp+318h+var_110]
0x1800cdb02  mov     rcx, rbx
0x1800cdb05  call    ?PostCampaignDataForInstall@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@000000@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::PostCampaignDataForInstall(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800cdb0a  nop
0x1800cdb0b  lea     rcx, [rsp+318h+var_200]
0x1800cdb13  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb18  nop
0x1800cdb19  lea     rcx, [rsp+318h+var_230]
0x1800cdb21  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb26  nop
0x1800cdb27  lea     rcx, [rsp+318h+var_228]
0x1800cdb2f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb34  nop
0x1800cdb35  lea     rcx, [rsp+318h+var_220]
0x1800cdb3d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb42  nop
0x1800cdb43  lea     rcx, [rsp+318h+var_218]
0x1800cdb4b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb50  nop
0x1800cdb51  lea     rcx, [rsp+318h+var_210]
0x1800cdb59  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb5e  nop
0x1800cdb5f  lea     rcx, [rsp+318h+var_208]
0x1800cdb67  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800cdb6c  nop
0x1800cdb6d  lea     rcx, [rsp+318h+var_248]; void *
0x1800cdb75  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800cdb7a  nop
0x1800cdb7b  jmp     loc_1800CDC8A
0x1800cdb80  xor     r14d, r14d
0x1800cdb83  mov     r15, [rsp+318h+var_240]
0x1800cdb8b  mov     r13, [rsp+318h+var_268]
0x1800cdb93  mov     rax, [rsp+318h+var_260]
0x1800cdb9b  mov     [rsp+318h+var_250], rax
0x1800cdba3  mov     rax, [rsp+318h+var_258]
0x1800cdbab  mov     qword ptr [rsp+318h+var_270], rax
0x1800cdbb3  mov     rsi, [rsp+318h+var_238]
0x1800cdbbb  jmp     loc_1800CDC8A
0x1800cdbc0  lea     rdi, [r15+0F0h]
0x1800cdbc7  mov     rcx, rdi; SRWLock
0x1800cdbca  call    cs:__imp_AcquireSRWLockShared
0x1800cdbd0  mov     rbx, [r15+108h]
0x1800cdbd7  mov     [rsp+318h+var_248], rbx
0x1800cdbdf  test    rbx, rbx
0x1800cdbe2  jz      short loc_1800CDBF4
0x1800cdbe4  mov     rax, [rbx]
0x1800cdbe7  mov     rcx, rbx
0x1800cdbea  mov     rax, [rax+8]
0x1800cdbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdbf3  nop
0x1800cdbf4  mov     rcx, rdi; SRWLock
0x1800cdbf7  call    cs:__imp_ReleaseSRWLockShared
0x1800cdbfd  mov     rax, [rbx]
0x1800cdc00  mov     rdi, [rax+0F0h]
0x1800cdc07  lea     rcx, [rsp+318h+var_E8]; this
0x1800cdc0f  call    ?Increment@CorrelationVector@@QEAAAEAV1@XZ; CorrelationVector::Increment(void)
0x1800cdc14  mov     rcx, rax; this
0x1800cdc17  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x1800cdc1c  mov     rcx, [rsp+318h+var_2A8]
0x1800cdc21  mov     rdx, [rsp+318h+var_290]
0x1800cdc29  mov     [rsp+318h+var_2E0], rax
0x1800cdc2e  mov     [rsp+318h+var_2E8], rcx
  ... truncated ...
```
