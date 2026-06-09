# _GetPackageDetailsFromSinglePackage(Windows::Internal::StateRepository::IPackage *,NotificationMetadata *)

- ea: `0x180103b28`
- end: `0x180103f57`
- name: `?_GetPackageDetailsFromSinglePackage@@YAJPEAUIPackage@StateRepository@Internal@Windows@@PEAUNotificationMetadata@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IPackage *, struct NotificationMetadata *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180103174`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c108`
- `0x18001c414`
- `0x18001c844`
- `0x18001c964`
- `0x1800252e8`
- `0x18002c310`
- `0x18002ec2c`
- `0x180045e74`
- `0x180103b28`
- `0x180103f60`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103d7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103d7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103cbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103d1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103cbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103d1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103ea4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180103ba1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180103ba1`

## string_xrefs

- `0x180103bb6`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103c00`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103c53`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103c9a`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103d58`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103da2`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103df4`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103e33`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103edf`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180103d4b`: `_GetPackageDetailsFromSinglePackage`
- `0x180103de8`: `_GetPackageDetailsFromSinglePackage`
- `0x180103ed2`: `_GetPackageDetailsFromSinglePackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall _GetPackageDetailsFromSinglePackage(
        struct Windows::Internal::StateRepository::IPackage *a1,
        HSTRING *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, struct Windows::Internal::StateRepository::IPackage *, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 (__fastcall *v12)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *); // rbx
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rdi
  int v18; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rdi
  int v21; // eax
  int v22; // eax
  PCWSTR v24; // rbx
  PCWSTR v25; // rax
  int v26; // [rsp+20h] [rbp-B8h]
  int v27; // [rsp+20h] [rbp-B8h]
  int v28; // [rsp+20h] [rbp-B8h]
  int v29; // [rsp+28h] [rbp-B0h]
  HSTRING string; // [rsp+50h] [rbp-88h] BYREF
  HSTRING v31; // [rsp+58h] [rbp-80h] BYREF
  __int64 v32; // [rsp+60h] [rbp-78h] BYREF
  __int64 v33; // [rsp+68h] [rbp-70h] BYREF
  HSTRING v34; // [rsp+70h] [rbp-68h] BYREF
  HSTRING v35; // [rsp+78h] [rbp-60h] BYREF
  HSTRING_HEADER v36; // [rsp+80h] [rbp-58h] BYREF
  __int64 v37; // [rsp+98h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v32 = 0;
  v33 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v36,
    L"Windows.Internal.StateRepository.PackageResourceResolver",
    0x39u,
    0x38u);
  v4 = v37;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_cb4720b3_052a_4478_b348_29a7cf0d828e, &v33);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26);
  v6 = v33;
  v7 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IPackage *, __int64 *))(*(_QWORD *)v33 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  v8 = v7(v6, a1, &v32);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v8,
      v26);
  v31 = 0;
  string = 0;
  v9 = v32;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
  WindowsDeleteString(0);
  v31 = 0;
  v11 = v10(v9, &v31);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v11,
      v26);
  v12 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *))(*(_QWORD *)a1 + 112LL);
  WindowsDeleteString(string);
  string = 0;
  v13 = v12(a1, &string);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v13,
      v26);
  if ( !v31 )
    goto LABEL_17;
  StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
  std::wstring::wstring(&v36, StringRawBuffer);
  v15 = std::wstring::find(&v36, L"_");
  if ( v15 <= *(_QWORD *)&v36.Reserved.Reserved2[16] )
  {
    std::wstring::_Tidy_deallocate(&v36);
LABEL_17:
    v24 = WindowsGetStringRawBuffer(string, 0);
    v25 = WindowsGetStringRawBuffer(v31, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      0x15Du,
      "_GetPackageDetailsFromSinglePackage",
      -1,
      L"Toast notification generation, displayName resolved from appx resourceResolver: %s, PackageFullName: %s. Invalid d"
       "isplayName, defaulting to catalog information.",
      0,
      0,
      v25,
      v24);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v31);
    v31 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
    return 0;
  }
  std::wstring::_Tidy_deallocate(&v36);
  WindowsGetStringRawBuffer(string, 0);
  WindowsGetStringRawBuffer(v31, 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
    0x154u,
    "_GetPackageDetailsFromSinglePackage",
    -1,
    L"Toast notification generation, displayName resolved from appx resourceResolver: %s, PackageFullName: %s",
    0,
    0);
  v16 = v32;
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
  WindowsDeleteString(a2[8]);
  a2[8] = 0;
  v18 = v17(v16, a2 + 8);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v18,
      v27);
  v19 = v32;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 72LL);
  WindowsDeleteString(a2[9]);
  a2[9] = 0;
  v21 = v20(v19, a2 + 9);
  TraceHR(
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
    0x157u,
    "_GetPackageDetailsFromSinglePackage",
    "resourceResolver->GetLogoLocalized(pData->logoUrl.GetAddressOf())",
    v21,
    v29);
  v34 = *(HSTRING *)_GetSingleAumidFromPackage(&v35, a1);
  v22 = Microsoft::WRL::Wrappers::HString::Set(a2 + 10, &v34);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
      (const char *)(unsigned int)v22,
      v28);
  WindowsDeleteString(v35);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v31);
  v31 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  return 0;
}

```

## disassembly

```asm
0x180103b28  mov     r11, rsp
0x180103b2b  mov     [r11+18h], rbx
0x180103b2f  push    rsi
0x180103b30  push    rdi
0x180103b31  push    r12
0x180103b33  push    r14
0x180103b35  push    r15
0x180103b37  sub     rsp, 0B0h
0x180103b3e  mov     rax, cs:__security_cookie
0x180103b45  xor     rax, rsp
0x180103b48  mov     [rsp+0D8h+var_38], rax
0x180103b50  mov     r15, rdx
0x180103b53  mov     r14, rcx
0x180103b56  xor     r12d, r12d
0x180103b59  mov     [r11-78h], r12
0x180103b5d  mov     [r11-70h], r12
0x180103b61  mov     [r11-40h], r12
0x180103b65  lea     r9d, [r12+38h]; unsigned int
0x180103b6a  lea     r8d, [r12+39h]; unsigned int
0x180103b6f  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180103b76  lea     rcx, [r11-58h]; hstringHeader
0x180103b7a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180103b7f  nop
0x180103b80  mov     rbx, [rsp+0D8h+var_40]
0x180103b88  lea     rcx, [rsp+0D8h+var_70]
0x180103b8d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103b92  lea     r8, [rsp+0D8h+var_70]
0x180103b97  lea     rdx, _GUID_cb4720b3_052a_4478_b348_29a7cf0d828e
0x180103b9e  mov     rcx, rbx
0x180103ba1  call    cs:__imp_RoGetActivationFactory
0x180103ba7  mov     rcx, [rsp+0D8h]; this
0x180103baf  test    eax, eax
0x180103bb1  jns     short loc_180103BC8
0x180103bb3  mov     r9d, eax; char *
0x180103bb6  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103bbd  mov     edx, 14Ah; void *
0x180103bc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103bc8  mov     rdi, [rsp+0D8h+var_70]
0x180103bcd  mov     rax, [rdi]
0x180103bd0  mov     rbx, [rax+30h]
0x180103bd4  lea     rcx, [rsp+0D8h+var_78]
0x180103bd9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103bde  lea     r8, [rsp+0D8h+var_78]
0x180103be3  mov     rdx, r14
0x180103be6  mov     rcx, rdi
0x180103be9  mov     rax, rbx
0x180103bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103bf1  mov     rcx, [rsp+0D8h]; this
0x180103bf9  test    eax, eax
0x180103bfb  jns     short loc_180103C11
0x180103bfd  mov     r9d, eax; char *
0x180103c00  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103c07  mov     edx, 14Bh; void *
0x180103c0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103c11  mov     [rsp+0D8h+var_80], r12
0x180103c16  mov     [rsp+0D8h+string], r12
0x180103c1b  mov     rdi, [rsp+0D8h+var_78]
0x180103c20  mov     rax, [rdi]
0x180103c23  mov     rbx, [rax+30h]
0x180103c27  xor     ecx, ecx; string
0x180103c29  call    cs:__imp_WindowsDeleteString
0x180103c2f  mov     [rsp+0D8h+var_80], r12
0x180103c34  lea     rdx, [rsp+0D8h+var_80]
0x180103c39  mov     rcx, rdi
0x180103c3c  mov     rax, rbx
0x180103c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103c44  mov     rcx, [rsp+0D8h]; this
0x180103c4c  test    eax, eax
0x180103c4e  jns     short loc_180103C64
0x180103c50  mov     r9d, eax; char *
0x180103c53  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103c5a  mov     edx, 150h; void *
0x180103c5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103c64  mov     rax, [r14]
0x180103c67  mov     rbx, [rax+70h]
0x180103c6b  mov     rcx, [rsp+0D8h+string]; string
0x180103c70  call    cs:__imp_WindowsDeleteString
0x180103c76  mov     [rsp+0D8h+string], r12
0x180103c7b  lea     rdx, [rsp+0D8h+string]
0x180103c80  mov     rcx, r14
0x180103c83  mov     rax, rbx
0x180103c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103c8b  mov     rcx, [rsp+0D8h]; this
0x180103c93  test    eax, eax
0x180103c95  jns     short loc_180103CAB
0x180103c97  mov     r9d, eax; char *
0x180103c9a  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103ca1  mov     edx, 151h; void *
0x180103ca6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103cab  mov     rcx, [rsp+0D8h+var_80]; string
0x180103cb0  test    rcx, rcx
0x180103cb3  jz      loc_180103E8D
0x180103cb9  xor     edx, edx; length
0x180103cbb  call    cs:__imp_WindowsGetStringRawBuffer
0x180103cc1  mov     rdx, rax
0x180103cc4  lea     rcx, [rsp+0D8h+var_58]
0x180103ccc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180103cd1  lea     rdx, asc_18026CA70; "_"
0x180103cd8  lea     rcx, [rsp+0D8h+var_58]
0x180103ce0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180103ce5  lea     rcx, [rsp+0D8h+var_58]
0x180103ced  cmp     rax, [rsp+0D8h+var_48]
0x180103cf5  ja      short loc_180103D01
0x180103cf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180103cfc  jmp     loc_180103E8D
0x180103d01  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180103d06  xor     edx, edx; length
0x180103d08  mov     rcx, [rsp+0D8h+string]; string
0x180103d0d  call    cs:__imp_WindowsGetStringRawBuffer
0x180103d13  mov     rbx, rax
0x180103d16  xor     edx, edx; length
0x180103d18  mov     rcx, [rsp+0D8h+var_80]; string
0x180103d1d  call    cs:__imp_WindowsGetStringRawBuffer
0x180103d23  mov     [rsp+0D8h+var_90], rbx
0x180103d28  mov     [rsp+0D8h+var_98], rax
0x180103d2d  mov     [rsp+0D8h+var_A0], r12; unsigned __int16 *
0x180103d32  mov     [rsp+0D8h+var_A8], r12; char *
0x180103d37  lea     rax, aToastNotificat_1; "Toast notification generation, displayN"...
0x180103d3e  mov     [rsp+0D8h+var_B0], rax; int
0x180103d43  mov     [rsp+0D8h+var_B8], 0FFFFFFFFh; int
0x180103d4b  lea     r9, aGetpackagedeta_0; "_GetPackageDetailsFromSinglePackage"
0x180103d52  mov     r8d, 154h; unsigned int
0x180103d58  lea     rdx, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103d5f  mov     ecx, 3; unsigned int
0x180103d64  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180103d69  mov     rsi, [rsp+0D8h+var_78]
0x180103d6e  mov     rax, [rsi]
0x180103d71  mov     rdi, [rax+30h]
0x180103d75  lea     rbx, [r15+40h]
0x180103d79  mov     rcx, [rbx]; string
0x180103d7c  call    cs:__imp_WindowsDeleteString
0x180103d82  mov     [rbx], r12
0x180103d85  mov     rdx, rbx
0x180103d88  mov     rcx, rsi
0x180103d8b  mov     rax, rdi
0x180103d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103d93  mov     rcx, [rsp+0D8h]; this
0x180103d9b  test    eax, eax
0x180103d9d  jns     short loc_180103DB3
0x180103d9f  mov     r9d, eax; char *
0x180103da2  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103da9  mov     edx, 155h; void *
0x180103dae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103db3  mov     rsi, [rsp+0D8h+var_78]
0x180103db8  mov     rax, [rsi]
0x180103dbb  mov     rdi, [rax+48h]
0x180103dbf  lea     rbx, [r15+48h]
0x180103dc3  mov     rcx, [rbx]; string
0x180103dc6  call    cs:__imp_WindowsDeleteString
0x180103dcc  mov     [rbx], r12
0x180103dcf  mov     rdx, rbx
0x180103dd2  mov     rcx, rsi
0x180103dd5  mov     rax, rdi
0x180103dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103ddd  mov     [rsp+0D8h+var_B8], eax; int
0x180103de1  lea     r9, aResourceresolv; "resourceResolver->GetLogoLocalized(pDat"...
0x180103de8  lea     r8, aGetpackagedeta_0; "_GetPackageDetailsFromSinglePackage"
0x180103def  mov     edx, 157h; unsigned int
0x180103df4  lea     rcx, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103dfb  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180103e00  mov     rdx, r14
0x180103e03  lea     rcx, [rsp+0D8h+var_60]
0x180103e08  call    ?_GetSingleAumidFromPackage@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIPackage@StateRepository@Internal@Windows@@@Z; _GetSingleAumidFromPackage(Windows::Internal::StateRepository::IPackage *)
0x180103e0d  nop
0x180103e0e  mov     rax, [rax]
0x180103e11  mov     [rsp+0D8h+var_68], rax
0x180103e16  lea     rcx, [r15+50h]; newString
0x180103e1a  lea     rdx, [rsp+0D8h+var_68]; HSTRING *
0x180103e1f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180103e24  mov     rcx, [rsp+0D8h]; this
0x180103e2c  test    eax, eax
0x180103e2e  jns     short loc_180103E45
0x180103e30  mov     r9d, eax; char *
0x180103e33  lea     r8, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103e3a  mov     edx, 158h; void *
0x180103e3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103e45  mov     rcx, [rsp+0D8h+var_60]; string
0x180103e4a  call    cs:__imp_WindowsDeleteString
0x180103e50  nop
0x180103e51  mov     rcx, [rsp+0D8h+string]; string
0x180103e56  call    cs:__imp_WindowsDeleteString
0x180103e5c  mov     [rsp+0D8h+string], r12
0x180103e61  mov     rcx, [rsp+0D8h+var_80]; string
0x180103e66  call    cs:__imp_WindowsDeleteString
0x180103e6c  mov     [rsp+0D8h+var_80], r12
0x180103e71  lea     rcx, [rsp+0D8h+var_70]
0x180103e76  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103e7b  nop
0x180103e7c  lea     rcx, [rsp+0D8h+var_78]
0x180103e81  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103e86  xor     eax, eax
0x180103e88  jmp     loc_180103F2E
0x180103e8d  xor     edx, edx; length
0x180103e8f  mov     rcx, [rsp+0D8h+string]; string
0x180103e94  call    cs:__imp_WindowsGetStringRawBuffer
0x180103e9a  mov     rbx, rax
0x180103e9d  xor     edx, edx; length
0x180103e9f  mov     rcx, [rsp+0D8h+var_80]; string
0x180103ea4  call    cs:__imp_WindowsGetStringRawBuffer
0x180103eaa  mov     [rsp+0D8h+var_90], rbx
0x180103eaf  mov     [rsp+0D8h+var_98], rax
0x180103eb4  mov     [rsp+0D8h+var_A0], r12; unsigned __int16 *
0x180103eb9  mov     [rsp+0D8h+var_A8], r12; char *
0x180103ebe  lea     rax, aToastNotificat; "Toast notification generation, displayN"...
0x180103ec5  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x180103eca  mov     [rsp+0D8h+var_B8], 0FFFFFFFFh; int
0x180103ed2  lea     r9, aGetpackagedeta_0; "_GetPackageDetailsFromSinglePackage"
0x180103ed9  mov     r8d, 15Dh; unsigned int
0x180103edf  lea     rdx, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180103ee6  mov     ecx, 3; unsigned int
0x180103eeb  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180103ef0  nop
0x180103ef1  mov     rcx, [rsp+0D8h+string]; string
0x180103ef6  call    cs:__imp_WindowsDeleteString
0x180103efc  mov     [rsp+0D8h+string], r12
0x180103f01  mov     rcx, [rsp+0D8h+var_80]; string
0x180103f06  call    cs:__imp_WindowsDeleteString
0x180103f0c  mov     [rsp+0D8h+var_80], r12
0x180103f11  lea     rcx, [rsp+0D8h+var_70]
0x180103f16  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103f1b  nop
0x180103f1c  lea     rcx, [rsp+0D8h+var_78]
0x180103f21  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180103f26  xor     eax, eax
0x180103f28  jmp     short loc_180103F2E
0x180103f2a  mov     eax, dword ptr [rsp+0D8h+string]
0x180103f2e  mov     rcx, [rsp+0D8h+var_38]
0x180103f36  xor     rcx, rsp; StackCookie
0x180103f39  call    __security_check_cookie
0x180103f3e  mov     rbx, [rsp+0D8h+arg_10]
0x180103f46  add     rsp, 0B0h
0x180103f4d  pop     r15
0x180103f4f  pop     r14
0x180103f51  pop     r12
0x180103f53  pop     rdi
0x180103f54  pop     rsi
0x180103f55  retn
```
