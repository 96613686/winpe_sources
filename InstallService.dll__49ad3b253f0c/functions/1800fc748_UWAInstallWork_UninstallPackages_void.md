# UWAInstallWork::_UninstallPackages(void)

- ea: `0x1800fc748`
- end: `0x1800fcaff`
- name: `?_UninstallPackages@UWAInstallWork@@AEAAJXZ`
- size: `951`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ee3e8`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180022f00`
- `0x1800252e8`
- `0x18002f214`
- `0x1800594c4`
- `0x1800dc630`
- `0x1800dda60`
- `0x1800ecf8c`
- `0x1800fc748`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc9f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fca0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcaa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc9f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fca0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcaa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fca42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fca42`

## string_xrefs

- `0x1800fc7c3`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fc9c4`: `Failed to remove %s`
- `0x1800fca57`: `Successfully removed %s`
- `0x1800fc7a2`: `Attempting to remove %s`
- `0x1800fc7b6`: `UWAInstallWork::_UninstallPackages`
- `0x1800fca6b`: `UWAInstallWork::_UninstallPackages`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall UWAInstallWork::_UninstallPackages(UWAInstallWork *this)
{
  const unsigned __int16 *StringRawBuffer; // rax
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  HSTRING *v7; // rsi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, _QWORD, __int64); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ebx
  const char *v13; // rax
  const char *v14; // rbx
  const unsigned __int16 *v15; // rax
  int i; // eax
  int v17; // [rsp+20h] [rbp-C8h]
  __int64 v18; // [rsp+50h] [rbp-98h] BYREF
  __int64 v19; // [rsp+58h] [rbp-90h] BYREF
  __int64 v20; // [rsp+60h] [rbp-88h] BYREF
  __int64 v21; // [rsp+68h] [rbp-80h] BYREF
  int v22; // [rsp+70h] [rbp-78h]
  HSTRING v23; // [rsp+78h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-68h] BYREF
  __int64 v25; // [rsp+98h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0xF14u,
    "UWAInstallWork::_UninstallPackages",
    -1,
    L"Attempting to remove %s",
    (const char *)this + 304,
    StringRawBuffer);
  v20 = 0;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.Internal.PackageManagerInternal",
    0x3Eu,
    0x3Du);
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
         v25,
         &v20);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF16,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)v3,
      v17);
LABEL_5:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
    return v4;
  }
  v19 = 0;
  v5 = StringHelpers::Split(*((HSTRING *)this + 12));
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF19,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)v5,
      v17);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
    goto LABEL_5;
  }
  v18 = v19;
  v21 = v19;
  v22 = 0;
  v23 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
    &v18,
    &hstringHeader);
  for ( i = v22; i != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; i = ++v22 )
  {
    v7 = (HSTRING *)wil::vector_range<Windows::Foundation::Collections::IVectorView<HSTRING__ *>,wil::err_exception_policy>::vector_iterator::operator*(&v21);
    v18 = 0;
    v8 = v20;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, __int64))(*(_QWORD *)v20 + 104LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
    v10 = v9(v8, *v7, 0, 3);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        (const char *)(unsigned int)v10,
        (int)&v18);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
      WindowsDeleteString(*(HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
      WindowsDeleteString(v23);
      v23 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
      return v11;
    }
    v12 = Windows::Management::Deployment::WaitForDeploymentOperation(0xFFFFFFFF, (__int64)&v18);
    v13 = (const char *)WindowsGetStringRawBuffer(*v7, 0);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xF20,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        (const char *)(unsigned int)v12,
        (int)"Failed to remove %s",
        v13);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
      WindowsDeleteString(*(HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
      WindowsDeleteString(v23);
      v23 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
      return (unsigned int)v12;
    }
    v14 = v13;
    v15 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0xF21u,
      "UWAInstallWork::_UninstallPackages",
      -1,
      L"Successfully removed %s",
      (const char *)this + 304,
      v15,
      v14);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
  }
  WindowsDeleteString(*(HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  WindowsDeleteString(v23);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x1800fc748  push    rbx
0x1800fc74a  push    rsi
0x1800fc74b  push    rdi
0x1800fc74c  push    r13
0x1800fc74e  push    r14
0x1800fc750  push    r15
0x1800fc752  sub     rsp, 0B8h
0x1800fc759  mov     rax, cs:__security_cookie
0x1800fc760  xor     rax, rsp
0x1800fc763  mov     [rsp+0E8h+var_48], rax
0x1800fc76b  mov     r14, rcx
0x1800fc76e  xor     edx, edx; length
0x1800fc770  mov     rcx, [rcx+60h]; string
0x1800fc774  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc77a  mov     rbx, rax
0x1800fc77d  xor     edx, edx; length
0x1800fc77f  mov     rcx, [r14+1D8h]; string
0x1800fc786  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc78c  lea     r15, [r14+130h]
0x1800fc793  mov     [rsp+0E8h+var_A8], rbx
0x1800fc798  mov     [rsp+0E8h+var_B0], rax; unsigned __int16 *
0x1800fc79d  mov     [rsp+0E8h+var_B8], r15; char *
0x1800fc7a2  lea     rax, aAttemptingToRe_0; "Attempting to remove %s"
0x1800fc7a9  mov     [rsp+0E8h+var_C0], rax; unsigned __int16 *
0x1800fc7ae  mov     dword ptr [rsp+0E8h+var_C8], 0FFFFFFFFh; int
0x1800fc7b6  lea     r9, aUwainstallwork_6; "UWAInstallWork::_UninstallPackages"
0x1800fc7bd  mov     r8d, 0F14h; unsigned int
0x1800fc7c3  lea     r13, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc7ca  mov     rdx, r13; char *
0x1800fc7cd  mov     ecx, 3; unsigned int
0x1800fc7d2  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800fc7d7  mov     [rsp+0E8h+var_88], 0
0x1800fc7e0  mov     [rsp+0E8h+var_50], 0
0x1800fc7ec  mov     r9d, 3Dh ; '='; unsigned int
0x1800fc7f2  lea     r8d, [r9+1]; unsigned int
0x1800fc7f6  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x1800fc7fd  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800fc805  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800fc80a  lea     rdx, [rsp+0E8h+var_88]
0x1800fc80f  mov     rcx, [rsp+0E8h+var_50]
0x1800fc817  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x1800fc81c  mov     ebx, eax
0x1800fc81e  test    eax, eax
0x1800fc820  jns     short loc_1800FC83C
0x1800fc822  mov     rcx, [rsp+0E8h]; this
0x1800fc82a  mov     r9d, eax; char *
0x1800fc82d  mov     r8, r13; unsigned int
0x1800fc830  mov     edx, 0F16h; void *
0x1800fc835  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc83a  jmp     short loc_1800FC87D
0x1800fc83c  mov     [rsp+0E8h+var_90], 0
0x1800fc845  lea     r8, [rsp+0E8h+var_90]
0x1800fc84a  mov     rcx, [r14+60h]; string
0x1800fc84e  call    ?Split@StringHelpers@@SAJPEAUHSTRING__@@GPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; StringHelpers::Split(HSTRING__ *,ushort,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)
0x1800fc853  mov     ebx, eax
0x1800fc855  test    eax, eax
0x1800fc857  jns     short loc_1800FC88E
0x1800fc859  mov     rcx, [rsp+0E8h]; this
0x1800fc861  mov     r9d, eax; char *
0x1800fc864  mov     r8, r13; unsigned int
0x1800fc867  mov     edx, 0F19h; void *
0x1800fc86c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc871  nop
0x1800fc872  lea     rcx, [rsp+0E8h+var_90]
0x1800fc877  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc87c  nop
0x1800fc87d  lea     rcx, [rsp+0E8h+var_88]
0x1800fc882  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc887  mov     eax, ebx
0x1800fc889  jmp     loc_1800FCADE
0x1800fc88e  mov     rax, [rsp+0E8h+var_90]
0x1800fc893  mov     [rsp+0E8h+var_98], rax
0x1800fc898  mov     [rsp+0E8h+var_80], rax
0x1800fc89d  mov     [rsp+0E8h+var_78], 0
0x1800fc8a5  mov     [rsp+0E8h+var_70], 0
0x1800fc8ae  lea     rdx, [rsp+0E8h+hstringHeader]
0x1800fc8b6  lea     rcx, [rsp+0E8h+var_98]
0x1800fc8bb  call    ?end@?$vector_range@U?$IVectorView@PEAVToastNotification@Notifications@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(void)
0x1800fc8c0  nop
0x1800fc8c1  mov     eax, [rsp+0E8h+var_78]
0x1800fc8c5  cmp     eax, dword ptr [rsp+0E8h+hstringHeader.Reserved+8]
0x1800fc8cc  jz      loc_1800FCA9F
0x1800fc8d2  lea     rcx, [rsp+0E8h+var_80]
0x1800fc8d7  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBVHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@2@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<HSTRING__ *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x1800fc8dc  mov     rsi, rax
0x1800fc8df  mov     [rsp+0E8h+var_98], 0
0x1800fc8e8  mov     rdi, [rsp+0E8h+var_88]
0x1800fc8ed  mov     rdx, [rdi]
0x1800fc8f0  mov     rbx, [rdx+68h]
0x1800fc8f4  lea     rcx, [rsp+0E8h+var_98]
0x1800fc8f9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc8fe  lea     rax, [rsp+0E8h+var_98]
0x1800fc903  mov     [rsp+0E8h+var_C8], rax; __int64
0x1800fc908  mov     r9d, 3
0x1800fc90e  xor     r8d, r8d
0x1800fc911  mov     rdx, [rsi]
0x1800fc914  mov     rcx, rdi
0x1800fc917  mov     rax, rbx
0x1800fc91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc91f  mov     ebx, eax
0x1800fc921  test    eax, eax
0x1800fc923  jns     short loc_1800FC993
0x1800fc925  mov     rcx, [rsp+0E8h]; this
0x1800fc92d  mov     r9d, eax; char *
0x1800fc930  mov     r8, r13; unsigned int
0x1800fc933  mov     edx, 0F1Fh; void *
0x1800fc938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc93d  nop
0x1800fc93e  lea     rcx, [rsp+0E8h+var_98]
0x1800fc943  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc948  nop
0x1800fc949  mov     rcx, qword ptr [rsp+0E8h+hstringHeader.Reserved+10h]; string
0x1800fc951  call    cs:__imp_WindowsDeleteString
0x1800fc957  mov     qword ptr [rsp+0E8h+hstringHeader.Reserved+10h], 0
0x1800fc963  mov     rcx, [rsp+0E8h+var_70]; string
0x1800fc968  call    cs:__imp_WindowsDeleteString
0x1800fc96e  mov     [rsp+0E8h+var_70], 0
0x1800fc977  lea     rcx, [rsp+0E8h+var_90]
0x1800fc97c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc981  nop
0x1800fc982  lea     rcx, [rsp+0E8h+var_88]
0x1800fc987  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc98c  mov     eax, ebx
0x1800fc98e  jmp     loc_1800FCADE
0x1800fc993  xor     r9d, r9d
0x1800fc996  xor     r8d, r8d
0x1800fc999  mov     rdx, [rsp+0E8h+var_98]
0x1800fc99e  or      ecx, 0FFFFFFFFh; dwMilliseconds
0x1800fc9a1  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x1800fc9a6  mov     ebx, eax
0x1800fc9a8  mov     rcx, [rsi]; string
0x1800fc9ab  xor     edx, edx; length
0x1800fc9ad  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc9b3  test    ebx, ebx
0x1800fc9b5  jns     short loc_1800FCA36
0x1800fc9b7  mov     rcx, [rsp+0E8h]; this
0x1800fc9bf  mov     [rsp+0E8h+var_C0], rax; char *
0x1800fc9c4  lea     rax, aFailedToRemove; "Failed to remove %s"
0x1800fc9cb  mov     [rsp+0E8h+var_C8], rax; int
0x1800fc9d0  mov     r9d, ebx; char *
0x1800fc9d3  mov     r8, r13; unsigned int
0x1800fc9d6  mov     edx, 0F20h; void *
0x1800fc9db  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fc9e0  nop
0x1800fc9e1  lea     rcx, [rsp+0E8h+var_98]
0x1800fc9e6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc9eb  nop
0x1800fc9ec  mov     rcx, qword ptr [rsp+0E8h+hstringHeader.Reserved+10h]; string
0x1800fc9f4  call    cs:__imp_WindowsDeleteString
0x1800fc9fa  mov     qword ptr [rsp+0E8h+hstringHeader.Reserved+10h], 0
0x1800fca06  mov     rcx, [rsp+0E8h+var_70]; string
0x1800fca0b  call    cs:__imp_WindowsDeleteString
0x1800fca11  mov     [rsp+0E8h+var_70], 0
0x1800fca1a  lea     rcx, [rsp+0E8h+var_90]
0x1800fca1f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fca24  nop
0x1800fca25  lea     rcx, [rsp+0E8h+var_88]
0x1800fca2a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fca2f  mov     eax, ebx
0x1800fca31  jmp     loc_1800FCADE
0x1800fca36  mov     rbx, rax
0x1800fca39  xor     edx, edx; length
0x1800fca3b  mov     rcx, [r14+1D8h]; string
0x1800fca42  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fca48  mov     [rsp+0E8h+var_A8], rbx
0x1800fca4d  mov     [rsp+0E8h+var_B0], rax; unsigned __int16 *
0x1800fca52  mov     [rsp+0E8h+var_B8], r15; char *
0x1800fca57  lea     rax, aSuccessfullyRe; "Successfully removed %s"
0x1800fca5e  mov     [rsp+0E8h+var_C0], rax; unsigned __int16 *
0x1800fca63  mov     dword ptr [rsp+0E8h+var_C8], 0FFFFFFFFh; int
0x1800fca6b  lea     r9, aUwainstallwork_6; "UWAInstallWork::_UninstallPackages"
0x1800fca72  mov     r8d, 0F21h; unsigned int
0x1800fca78  mov     rdx, r13; char *
0x1800fca7b  mov     ecx, 3; unsigned int
0x1800fca80  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800fca85  nop
0x1800fca86  lea     rcx, [rsp+0E8h+var_98]
0x1800fca8b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fca90  mov     eax, [rsp+0E8h+var_78]
0x1800fca94  inc     eax
0x1800fca96  mov     [rsp+0E8h+var_78], eax
0x1800fca9a  jmp     loc_1800FC8C5
0x1800fca9f  mov     rcx, qword ptr [rsp+0E8h+hstringHeader.Reserved+10h]; string
0x1800fcaa7  call    cs:__imp_WindowsDeleteString
0x1800fcaad  mov     qword ptr [rsp+0E8h+hstringHeader.Reserved+10h], 0
0x1800fcab9  mov     rcx, [rsp+0E8h+var_70]; string
0x1800fcabe  call    cs:__imp_WindowsDeleteString
0x1800fcac4  nop
0x1800fcac5  jmp     short $+2
0x1800fcac7  lea     rcx, [rsp+0E8h+var_90]
0x1800fcacc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fcad1  nop
0x1800fcad2  lea     rcx, [rsp+0E8h+var_88]
0x1800fcad7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fcadc  xor     eax, eax
0x1800fcade  mov     rcx, [rsp+0E8h+var_48]
0x1800fcae6  xor     rcx, rsp; StackCookie
0x1800fcae9  call    __security_check_cookie
0x1800fcaee  add     rsp, 0B8h
0x1800fcaf5  pop     r15
0x1800fcaf7  pop     r14
0x1800fcaf9  pop     r13
0x1800fcafb  pop     rdi
0x1800fcafc  pop     rsi
0x1800fcafd  pop     rbx
0x1800fcafe  retn
```
