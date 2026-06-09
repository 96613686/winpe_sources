# AssignedAccessAdminHelperImpl::GetPackageFamilyName(ushort const *,ushort const *)

- ea: `0x140062cc4`
- end: `0x140062f6d`
- name: `?GetPackageFamilyName@AssignedAccessAdminHelperImpl@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140063ca8`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x14000d850`
- `0x14000f164`
- `0x140011b68`
- `0x14002a2c0`
- `0x14003aed0`
- `0x140062cc4`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140062ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140062ef9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140062d27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140062dcd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140062d27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140062dcd`

## string_xrefs

- `0x140062d38`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062d89`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062dde`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062e36`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062e6f`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062ea8`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062ee1`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall AssignedAccessAdminHelperImpl::GetPackageFamilyName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, __int64 **); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  PCWSTR StringRawBuffer; // rax
  int v23; // [rsp+20h] [rbp-59h]
  HSTRING string; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v25; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v26; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v27; // [rsp+48h] [rbp-31h] BYREF
  __int64 v28; // [rsp+50h] [rbp-29h] BYREF
  __int64 v29; // [rsp+58h] [rbp-21h] BYREF
  __int64 v30; // [rsp+60h] [rbp-19h] BYREF
  __int64 v31; // [rsp+68h] [rbp-11h] BYREF
  __int64 v32; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  __int64 v34; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v32 = a3;
  v31 = a4;
  v30 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  ActivationFactory = RoGetActivationFactory(v34, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v30);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v23);
  v28 = 0;
  v6 = v30;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 80LL);
  v28 = 0;
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v32);
  v9 = v7(v6, *(_QWORD *)(v8 + 24), &v28);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v9,
      v23);
  v29 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  v10 = RoGetActivationFactory(v34, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v29);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v27 = 0;
  v11 = v29;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 **))(*(_QWORD *)v29 + 240LL);
  v27 = 0;
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
  v14 = v12(v11, v28, *(_QWORD *)(v13 + 24), &v27);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v14,
      v23);
  v26 = 0;
  v15 = *v27;
  v26 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v15 + 72))(v27, &v26);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v16,
      v23);
  v25 = 0;
  v17 = *v26;
  v25 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v17 + 72))(v26, &v25);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v18,
      v23);
  string = 0;
  v19 = *v25;
  string = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v19 + 88))(v25, &string);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x149,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v20,
      v23);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(a2, (__int64)StringRawBuffer);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v25);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v26);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v27);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v28);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v30);
  return a2;
}

```

## disassembly

```asm
0x140062cc4  push    rbp
0x140062cc6  push    rbx
0x140062cc7  push    rsi
0x140062cc8  push    rdi
0x140062cc9  push    r14
0x140062ccb  lea     rbp, [rsp-37h]
0x140062cd0  sub     rsp, 0B0h
0x140062cd7  mov     rax, cs:__security_cookie
0x140062cde  xor     rax, rsp
0x140062ce1  mov     [rbp+57h+var_30], rax
0x140062ce5  mov     rsi, rdx
0x140062ce8  mov     [rbp+57h+var_68], rdx
0x140062cec  mov     [rbp+57h+var_58], r8
0x140062cf0  mov     [rbp+57h+var_68], r9
0x140062cf4  xor     r14d, r14d
0x140062cf7  mov     [rbp+57h+var_70], r14
0x140062cfb  mov     [rbp+57h+var_38], r14
0x140062cff  lea     r9d, [r14+25h]; unsigned int
0x140062d03  lea     r8d, [r14+26h]; unsigned int
0x140062d07  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x140062d0e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140062d12  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140062d17  nop
0x140062d18  lea     r8, [rbp+57h+var_70]
0x140062d1c  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x140062d23  mov     rcx, [rbp+57h+var_38]
0x140062d27  call    cs:__imp_RoGetActivationFactory
0x140062d2d  mov     rcx, [rbp+5Fh]; this
0x140062d31  test    eax, eax
0x140062d33  jns     short loc_140062D4A
0x140062d35  mov     r9d, eax; char *
0x140062d38  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062d3f  mov     edx, 13Dh; void *
0x140062d44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062d4a  mov     [rbp+57h+var_80], r14
0x140062d4e  mov     rdi, [rbp+57h+var_70]
0x140062d52  mov     rax, [rdi]
0x140062d55  mov     rbx, [rax+50h]
0x140062d59  mov     [rbp+57h+var_80], r14
0x140062d5d  lea     rdx, [rbp+57h+var_58]
0x140062d61  lea     rcx, [rbp+57h+hstringHeader]
0x140062d65  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140062d6a  nop
0x140062d6b  lea     r8, [rbp+57h+var_80]
0x140062d6f  mov     rdx, [rax+18h]
0x140062d73  mov     rcx, rdi
0x140062d76  mov     rax, rbx
0x140062d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062d7e  mov     rcx, [rbp+5Fh]; this
0x140062d82  test    eax, eax
0x140062d84  jns     short loc_140062D9B
0x140062d86  mov     r9d, eax; char *
0x140062d89  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062d90  mov     edx, 13Fh; void *
0x140062d95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062d9b  mov     [rbp+57h+var_78], r14
0x140062d9f  mov     [rbp+57h+var_38], r14
0x140062da3  mov     r9d, 2Ch ; ','; unsigned int
0x140062da9  lea     r8d, [r9+1]; unsigned int
0x140062dad  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x140062db4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140062db8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140062dbd  nop
0x140062dbe  lea     r8, [rbp+57h+var_78]
0x140062dc2  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x140062dc9  mov     rcx, [rbp+57h+var_38]
0x140062dcd  call    cs:__imp_RoGetActivationFactory
0x140062dd3  mov     rcx, [rbp+5Fh]; this
0x140062dd7  test    eax, eax
0x140062dd9  jns     short loc_140062DF0
0x140062ddb  mov     r9d, eax; char *
0x140062dde  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062de5  mov     edx, 141h; void *
0x140062dea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062df0  mov     [rbp+57h+var_88], r14
0x140062df4  mov     rdi, [rbp+57h+var_78]
0x140062df8  mov     rax, [rdi]
0x140062dfb  mov     rbx, [rax+0F0h]
0x140062e02  mov     [rbp+57h+var_88], r14
0x140062e06  lea     rdx, [rbp+57h+var_68]
0x140062e0a  lea     rcx, [rbp+57h+hstringHeader]
0x140062e0e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140062e13  nop
0x140062e14  lea     r9, [rbp+57h+var_88]
0x140062e18  mov     r8, [rax+18h]
0x140062e1c  mov     rdx, [rbp+57h+var_80]
0x140062e20  mov     rcx, rdi
0x140062e23  mov     rax, rbx
0x140062e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062e2b  mov     rcx, [rbp+5Fh]; this
0x140062e2f  test    eax, eax
0x140062e31  jns     short loc_140062E48
0x140062e33  mov     r9d, eax; char *
0x140062e36  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062e3d  mov     edx, 143h; void *
0x140062e42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062e48  mov     [rbp+57h+var_90], r14
0x140062e4c  mov     rcx, [rbp+57h+var_88]
0x140062e50  mov     rax, [rcx]
0x140062e53  mov     [rbp+57h+var_90], r14
0x140062e57  lea     rdx, [rbp+57h+var_90]
0x140062e5b  mov     rax, [rax+48h]
0x140062e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062e64  mov     rcx, [rbp+5Fh]; this
0x140062e68  test    eax, eax
0x140062e6a  jns     short loc_140062E81
0x140062e6c  mov     r9d, eax; char *
0x140062e6f  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062e76  mov     edx, 145h; void *
0x140062e7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062e81  mov     [rbp+57h+var_98], r14
0x140062e85  mov     rcx, [rbp+57h+var_90]
0x140062e89  mov     rax, [rcx]
0x140062e8c  mov     [rbp+57h+var_98], r14
0x140062e90  lea     rdx, [rbp+57h+var_98]
0x140062e94  mov     rax, [rax+48h]
0x140062e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062e9d  mov     rcx, [rbp+5Fh]; this
0x140062ea1  test    eax, eax
0x140062ea3  jns     short loc_140062EBA
0x140062ea5  mov     r9d, eax; char *
0x140062ea8  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062eaf  mov     edx, 147h; void *
0x140062eb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062eba  mov     [rbp+57h+string], r14
0x140062ebe  mov     rcx, [rbp+57h+var_98]
0x140062ec2  mov     rax, [rcx]
0x140062ec5  mov     [rbp+57h+string], r14
0x140062ec9  lea     rdx, [rbp+57h+string]
0x140062ecd  mov     rax, [rax+58h]
0x140062ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062ed6  mov     rcx, [rbp+5Fh]; this
0x140062eda  test    eax, eax
0x140062edc  jns     short loc_140062EF3
0x140062ede  mov     r9d, eax; char *
0x140062ee1  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062ee8  mov     edx, 149h; void *
0x140062eed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062ef3  xor     edx, edx; length
0x140062ef5  mov     rcx, [rbp+57h+string]; string
0x140062ef9  call    cs:__imp_WindowsGetStringRawBuffer
0x140062eff  mov     rdx, rax
0x140062f02  mov     rcx, rsi
0x140062f05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140062f0a  nop
0x140062f0b  lea     rcx, [rbp+57h+string]; this
0x140062f0f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140062f14  nop
0x140062f15  lea     rcx, [rbp+57h+var_98]
0x140062f19  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140062f1e  nop
0x140062f1f  lea     rcx, [rbp+57h+var_90]
0x140062f23  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140062f28  nop
0x140062f29  lea     rcx, [rbp+57h+var_88]
0x140062f2d  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140062f32  nop
0x140062f33  lea     rcx, [rbp+57h+var_78]
0x140062f37  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140062f3c  nop
0x140062f3d  lea     rcx, [rbp+57h+var_80]
0x140062f41  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140062f46  nop
0x140062f47  lea     rcx, [rbp+57h+var_70]
0x140062f4b  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140062f50  mov     rax, rsi
0x140062f53  mov     rcx, [rbp+57h+var_30]
0x140062f57  xor     rcx, rsp; StackCookie
0x140062f5a  call    __security_check_cookie
0x140062f5f  add     rsp, 0B0h
0x140062f66  pop     r14
0x140062f68  pop     rdi
0x140062f69  pop     rsi
0x140062f6a  pop     rbx
0x140062f6b  pop     rbp
0x140062f6c  retn
```
