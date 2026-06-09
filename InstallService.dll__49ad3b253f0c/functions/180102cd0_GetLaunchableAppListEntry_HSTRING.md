# GetLaunchableAppListEntry(HSTRING__ *)

- ea: `0x180102cd0`
- end: `0x18010316d`
- name: `?GetLaunchableAppListEntry@@YA?AV?$ComPtr@UIAppListEntry@Core@ApplicationModel@Windows@@@WRL@Microsoft@@PEAUHSTRING__@@@Z`
- size: `1181`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d45a0`
- `0x1800ea910`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800252e8`
- `0x18002ec2c`
- `0x1800331d4`
- `0x180052268`
- `0x180091754`
- `0x180101dd4`
- `0x180101e88`
- `0x180102cd0`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010307f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010307f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010313a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010313a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180102e7a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180102edb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180102e7a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180102edb`

## string_xrefs

- `0x180102d4b`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102d8f`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102ddc`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102e2a`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102e8b`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102eec`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102f88`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102fd0`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103019`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103069`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103110`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x18010315b`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall GetLaunchableAppListEntry(_QWORD *a1, HSTRING a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, HSTRING, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rbx
  int ActivationFactory; // eax
  __int64 v14; // rbx
  int v15; // eax
  int i; // eax
  _QWORD *v17; // rsi
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, HSTRING, _QWORD *); // rbx
  int v28; // eax
  const char *StringRawBuffer; // rax
  int v31; // [rsp+20h] [rbp-79h]
  int v32; // [rsp+30h] [rbp-69h] BYREF
  HSTRING string; // [rsp+38h] [rbp-61h] BYREF
  __int64 v34; // [rsp+40h] [rbp-59h] BYREF
  __int64 v35; // [rsp+48h] [rbp-51h] BYREF
  __int64 v36; // [rsp+50h] [rbp-49h] BYREF
  __int64 v37; // [rsp+58h] [rbp-41h] BYREF
  __int64 v38; // [rsp+60h] [rbp-39h] BYREF
  int v39; // [rsp+68h] [rbp-31h]
  __int64 v40; // [rsp+70h] [rbp-29h] BYREF
  __int64 v41; // [rsp+78h] [rbp-21h] BYREF
  __int64 v42; // [rsp+80h] [rbp-19h] BYREF
  __int64 v43; // [rsp+88h] [rbp-11h] BYREF
  int v44; // [rsp+90h] [rbp-9h]
  _QWORD v45[2]; // [rsp+98h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v47; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v45[1] = a1;
  v39 = 1;
  v41 = 0;
  v47 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
         v47,
         &v41);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v4,
      v31);
  v38 = 0;
  v5 = v41;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 104LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
  v7 = v6(v5, &v38);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v7,
      v31);
  v40 = 0;
  v47 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
         v47,
         &v40);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v8,
      v31);
  v37 = 0;
  v9 = v40;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v40 + 288LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
  v11 = v10(v9, v38, a2, &v37);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v11,
      v31);
  v36 = 0;
  v47 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.AppDisplayInfo",
    0x28u,
    0x27u);
  v12 = v47;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_676532a9_b7d3_49b3_8fd2_8e9fdacb209f, &v36);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v31);
  v35 = 0;
  v47 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Core.AppListEntry",
    0x2Bu,
    0x2Au);
  v14 = v47;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
  v15 = RoGetActivationFactory(v14, &GUID_722f2b9b_5e83_40f7_a9d6_52e300a17805, &v35);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v15,
      v31);
  v43 = v37;
  v44 = 0;
  v45[0] = 0;
  Windows::Foundation::Collections::end<Windows::Internal::StateRepository::Application *>(&hstringHeader);
  for ( i = v44; ; i = ++v44 )
  {
    if ( i == *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] )
    {
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v45);
      StringRawBuffer = (const char *)WindowsGetStringRawBuffer(a2, 0);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
        (const char *)0x80004005LL,
        (int)"Failed to find AppListEntry for %ws",
        StringRawBuffer);
    }
    v17 = (_QWORD *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v43);
    v32 = 0;
    v18 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v17 + 528LL))(*v17, &v32);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
        (const char *)(unsigned int)v18,
        v31);
    if ( v32 != 1 )
      break;
  }
  v42 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v17 + 48LL))(*v17, &v42);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v19,
      v31);
  v34 = 0;
  v20 = v36;
  v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
  v22 = v21(v20, v42, &v34);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v22,
      v31);
  string = 0;
  v23 = *v17;
  v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*v17 + 232LL);
  WindowsDeleteString(0);
  string = 0;
  v25 = v24(v23, &string);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v25,
      v31);
  *a1 = 0;
  v39 = 1;
  v26 = v35;
  v27 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, _QWORD *))(*(_QWORD *)v35 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(a1);
  v28 = v27(v26, v34, string, a1);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v28,
      v31);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v45);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v41);
  return a1;
}

```

## disassembly

```asm
0x180102cd0  mov     [rsp-8+arg_10], rbx
0x180102cd5  mov     [rsp-8+arg_18], rsi
0x180102cda  push    rbp
0x180102cdb  push    rdi
0x180102cdc  push    r12
0x180102cde  push    r14
0x180102ce0  push    r15
0x180102ce2  lea     rbp, [rsp-37h]
0x180102ce7  sub     rsp, 0D0h
0x180102cee  mov     rax, cs:__security_cookie
0x180102cf5  xor     rax, rsp
0x180102cf8  mov     [rbp+57h+var_28], rax
0x180102cfc  mov     r15, rdx
0x180102cff  mov     r14, rcx
0x180102d02  mov     [rbp+57h+var_50], rcx
0x180102d06  mov     [rbp+57h+var_88], 1
0x180102d0d  xor     r12d, r12d
0x180102d10  mov     [rbp+57h+var_78], r12
0x180102d14  mov     [rbp+57h+var_30], r12
0x180102d18  lea     r9d, [r12+25h]; unsigned int
0x180102d1d  lea     r8d, [r12+26h]; unsigned int
0x180102d22  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x180102d29  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180102d2d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180102d32  nop
0x180102d33  lea     rdx, [rbp+57h+var_78]
0x180102d37  mov     rcx, [rbp+57h+var_30]
0x180102d3b  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x180102d40  mov     rcx, [rbp+5Fh]; this
0x180102d44  test    eax, eax
0x180102d46  jns     short loc_180102D5D
0x180102d48  mov     r9d, eax; char *
0x180102d4b  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102d52  mov     edx, 195h; void *
0x180102d57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102d5d  mov     [rbp+57h+var_90], r12
0x180102d61  mov     rdi, [rbp+57h+var_78]
0x180102d65  mov     rax, [rdi]
0x180102d68  mov     rbx, [rax+68h]
0x180102d6c  lea     rcx, [rbp+57h+var_90]
0x180102d70  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102d75  lea     rdx, [rbp+57h+var_90]
0x180102d79  mov     rcx, rdi
0x180102d7c  mov     rax, rbx
0x180102d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102d84  mov     rcx, [rbp+5Fh]; this
0x180102d88  test    eax, eax
0x180102d8a  jns     short loc_180102DA1
0x180102d8c  mov     r9d, eax; char *
0x180102d8f  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102d96  mov     edx, 198h; void *
0x180102d9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102da1  mov     [rbp+57h+var_80], r12
0x180102da5  mov     [rbp+57h+var_30], r12
0x180102da9  mov     r9d, 2Ch ; ','; unsigned int
0x180102daf  lea     r8d, [r9+1]; unsigned int
0x180102db3  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180102dba  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180102dbe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180102dc3  nop
0x180102dc4  lea     rdx, [rbp+57h+var_80]
0x180102dc8  mov     rcx, [rbp+57h+var_30]
0x180102dcc  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x180102dd1  mov     rcx, [rbp+5Fh]; this
0x180102dd5  test    eax, eax
0x180102dd7  jns     short loc_180102DEE
0x180102dd9  mov     r9d, eax; char *
0x180102ddc  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102de3  mov     edx, 19Bh; void *
0x180102de8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102dee  mov     [rbp+57h+var_98], r12
0x180102df2  mov     rdi, [rbp+57h+var_80]
0x180102df6  mov     rax, [rdi]
0x180102df9  mov     rbx, [rax+120h]
0x180102e00  lea     rcx, [rbp+57h+var_98]
0x180102e04  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102e09  lea     r9, [rbp+57h+var_98]
0x180102e0d  mov     r8, r15
0x180102e10  mov     rdx, [rbp+57h+var_90]
0x180102e14  mov     rcx, rdi
0x180102e17  mov     rax, rbx
0x180102e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102e1f  mov     rcx, [rbp+5Fh]; this
0x180102e23  test    eax, eax
0x180102e25  jns     short loc_180102E3C
0x180102e27  mov     r9d, eax; char *
0x180102e2a  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102e31  mov     edx, 19Eh; void *
0x180102e36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102e3c  mov     [rbp+57h+var_A0], r12
0x180102e40  mov     [rbp+57h+var_30], r12
0x180102e44  mov     r9d, 27h ; '''; unsigned int
0x180102e4a  lea     r8d, [r9+1]; unsigned int
0x180102e4e  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppDisplayInfo@@3QBGB; "Windows.ApplicationModel.AppDisplayInfo"
0x180102e55  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180102e59  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180102e5e  nop
0x180102e5f  mov     rbx, [rbp+57h+var_30]
0x180102e63  lea     rcx, [rbp+57h+var_A0]
0x180102e67  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102e6c  lea     r8, [rbp+57h+var_A0]
0x180102e70  lea     rdx, _GUID_676532a9_b7d3_49b3_8fd2_8e9fdacb209f
0x180102e77  mov     rcx, rbx
0x180102e7a  call    cs:__imp_RoGetActivationFactory
0x180102e80  mov     rcx, [rbp+5Fh]; this
0x180102e84  test    eax, eax
0x180102e86  jns     short loc_180102E9D
0x180102e88  mov     r9d, eax; char *
0x180102e8b  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102e92  mov     edx, 1A1h; void *
0x180102e97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102e9d  mov     [rbp+57h+var_A8], r12
0x180102ea1  mov     [rbp+57h+var_30], r12
0x180102ea5  mov     r9d, 2Ah ; '*'; unsigned int
0x180102eab  lea     r8d, [r9+1]; unsigned int
0x180102eaf  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_AppListEntry@@3QBGB; "Windows.ApplicationModel.Core.AppListEn"...
0x180102eb6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180102eba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180102ebf  nop
0x180102ec0  mov     rbx, [rbp+57h+var_30]
0x180102ec4  lea     rcx, [rbp+57h+var_A8]
0x180102ec8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102ecd  lea     r8, [rbp+57h+var_A8]
0x180102ed1  lea     rdx, _GUID_722f2b9b_5e83_40f7_a9d6_52e300a17805
0x180102ed8  mov     rcx, rbx
0x180102edb  call    cs:__imp_RoGetActivationFactory
0x180102ee1  mov     rcx, [rbp+5Fh]; this
0x180102ee5  test    eax, eax
0x180102ee7  jns     short loc_180102EFE
0x180102ee9  mov     r9d, eax; char *
0x180102eec  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102ef3  mov     edx, 1A4h; void *
0x180102ef8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102efe  mov     rdx, [rbp+57h+var_98]
0x180102f02  mov     [rbp+57h+var_68], rdx
0x180102f06  mov     [rbp+57h+var_60], r12d
0x180102f0a  mov     [rbp+57h+var_58], r12
0x180102f0e  lea     rcx, [rbp+57h+hstringHeader]
0x180102f12  call    ??$end@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@YA?AVvector_iterator@?$vector_range@U?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEAU?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@012@@Z; Windows::Foundation::Collections::end<Windows::Internal::StateRepository::Application *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *> *)
0x180102f17  nop
0x180102f18  mov     eax, [rbp+57h+var_60]
0x180102f1b  cmp     eax, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x180102f1e  jz      loc_180103122
0x180102f24  lea     rcx, [rbp+57h+var_68]
0x180102f28  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x180102f2d  mov     rsi, rax
0x180102f30  mov     [rbp+57h+var_C0], r12d
0x180102f34  mov     rcx, [rax]
0x180102f37  mov     rax, [rcx]
0x180102f3a  lea     rdx, [rbp+57h+var_C0]
0x180102f3e  mov     rax, [rax+210h]
0x180102f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102f4a  mov     rcx, [rbp+5Fh]; this
0x180102f4e  test    eax, eax
0x180102f50  js      loc_18010310D
0x180102f56  cmp     [rbp+57h+var_C0], 1
0x180102f5a  jnz     short loc_180102F66
0x180102f5c  mov     eax, [rbp+57h+var_60]
0x180102f5f  inc     eax
0x180102f61  mov     [rbp+57h+var_60], eax
0x180102f64  jmp     short loc_180102F1B
0x180102f66  mov     [rbp+57h+var_70], r12
0x180102f6a  mov     rcx, [rsi]
0x180102f6d  mov     rax, [rcx]
0x180102f70  lea     rdx, [rbp+57h+var_70]
0x180102f74  mov     rax, [rax+30h]
0x180102f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102f7d  mov     rcx, [rbp+5Fh]; this
0x180102f81  test    eax, eax
0x180102f83  jns     short loc_180102F9A
0x180102f85  mov     r9d, eax; char *
0x180102f88  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102f8f  mov     edx, 1B0h; void *
0x180102f94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102f9a  mov     [rbp+57h+var_B0], r12
0x180102f9e  mov     rdi, [rbp+57h+var_A0]
0x180102fa2  mov     rax, [rdi]
0x180102fa5  mov     rbx, [rax+30h]
0x180102fa9  lea     rcx, [rbp+57h+var_B0]
0x180102fad  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102fb2  lea     r8, [rbp+57h+var_B0]
0x180102fb6  mov     rdx, [rbp+57h+var_70]
0x180102fba  mov     rcx, rdi
0x180102fbd  mov     rax, rbx
0x180102fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102fc5  mov     rcx, [rbp+5Fh]; this
0x180102fc9  test    eax, eax
0x180102fcb  jns     short loc_180102FE2
0x180102fcd  mov     r9d, eax; char *
0x180102fd0  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102fd7  mov     edx, 1B3h; void *
0x180102fdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180102fe2  mov     [rbp+57h+string], r12
0x180102fe6  mov     rdi, [rsi]
0x180102fe9  mov     rax, [rdi]
0x180102fec  mov     rbx, [rax+0E8h]
0x180102ff3  xor     ecx, ecx; string
0x180102ff5  call    cs:__imp_WindowsDeleteString
0x180102ffb  mov     [rbp+57h+string], r12
0x180102fff  lea     rdx, [rbp+57h+string]
0x180103003  mov     rcx, rdi
0x180103006  mov     rax, rbx
0x180103009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010300e  mov     rcx, [rbp+5Fh]; this
0x180103012  test    eax, eax
0x180103014  jns     short loc_18010302B
0x180103016  mov     r9d, eax; char *
0x180103019  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103020  mov     edx, 1B6h; void *
0x180103025  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010302b  mov     [r14], r12
0x18010302e  mov     [rbp+57h+var_88], 1
0x180103035  mov     rdi, [rbp+57h+var_A8]
0x180103039  mov     rax, [rdi]
0x18010303c  mov     rbx, [rax+30h]
0x180103040  mov     rcx, r14
0x180103043  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103048  mov     r9, r14
0x18010304b  mov     r8, [rbp+57h+string]
0x18010304f  mov     rdx, [rbp+57h+var_B0]
0x180103053  mov     rcx, rdi
0x180103056  mov     rax, rbx
0x180103059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010305e  mov     rcx, [rbp+5Fh]; this
0x180103062  test    eax, eax
0x180103064  jns     short loc_18010307B
0x180103066  mov     r9d, eax; char *
0x180103069  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103070  mov     edx, 1B9h; void *
0x180103075  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010307b  mov     rcx, [rbp+57h+string]; string
0x18010307f  call    cs:__imp_WindowsDeleteString
0x180103085  mov     [rbp+57h+string], r12
0x180103089  lea     rcx, [rbp+57h+var_B0]
0x18010308d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103092  nop
0x180103093  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x180103097  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18010309c  nop
0x18010309d  lea     rcx, [rbp+57h+var_58]
0x1801030a1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030a6  nop
0x1801030a7  lea     rcx, [rbp+57h+var_A8]
0x1801030ab  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030b0  nop
0x1801030b1  lea     rcx, [rbp+57h+var_A0]
0x1801030b5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030ba  nop
0x1801030bb  lea     rcx, [rbp+57h+var_98]
0x1801030bf  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030c4  nop
0x1801030c5  lea     rcx, [rbp+57h+var_80]
0x1801030c9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030ce  nop
0x1801030cf  lea     rcx, [rbp+57h+var_90]
0x1801030d3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030d8  nop
0x1801030d9  lea     rcx, [rbp+57h+var_78]
0x1801030dd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801030e2  mov     rax, r14
0x1801030e5  mov     rcx, [rbp+57h+var_28]
0x1801030e9  xor     rcx, rsp; StackCookie
0x1801030ec  call    __security_check_cookie
0x1801030f1  lea     r11, [rsp+0F0h+var_20]
0x1801030f9  mov     rbx, [r11+40h]
0x1801030fd  mov     rsi, [r11+48h]
0x180103101  mov     rsp, r11
0x180103104  pop     r15
0x180103106  pop     r14
0x180103108  pop     r12
0x18010310a  pop     rdi
0x18010310b  pop     rbp
0x18010310c  retn
0x18010310d  mov     r9d, eax; char *
0x180103110  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103117  mov     edx, 1A9h; void *
0x18010311c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103122  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x180103126  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18010312b  nop
0x18010312c  lea     rcx, [rbp+57h+var_58]
0x180103130  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103135  xor     edx, edx; length
0x180103137  mov     rcx, r15; string
0x18010313a  call    cs:__imp_WindowsGetStringRawBuffer
0x180103140  mov     rcx, [rbp+5Fh]; this
0x180103144  mov     [rsp+0F0h+var_C8], rax; char *
0x180103149  lea     rax, aFailedToFindAp; "Failed to find AppListEntry for %ws"
0x180103150  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180103155  mov     r9d, 80004005h; char *
0x18010315b  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103162  mov     edx, 1BCh; void *
0x180103167  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
