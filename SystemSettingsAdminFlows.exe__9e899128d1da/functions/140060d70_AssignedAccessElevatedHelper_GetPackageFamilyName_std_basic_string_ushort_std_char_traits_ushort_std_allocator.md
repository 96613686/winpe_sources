# AssignedAccessElevatedHelper::GetPackageFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140060d70`
- end: `0x140061051`
- name: `?GetPackageFamilyName@AssignedAccessElevatedHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006237c`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x14000d850`
- `0x14000f164`
- `0x140011b68`
- `0x140029eb8`
- `0x14002a2c0`
- `0x14003aed0`
- `0x140060d70`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140060f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140060f46`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140060dd7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140060e67`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140060dd7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140060e67`

## string_xrefs

- `0x140060fc1`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x140060fd6`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x140060feb`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x140061000`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x140061015`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x14006102a`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x14006103f`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall AssignedAccessElevatedHelper::GetPackageFamilyName(__int64 a1, __int64 a2, __int64 a3)
{
  int ActivationFactory; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD, __int64 **); // rbx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  PCWSTR StringRawBuffer; // rax
  int v24; // [rsp+20h] [rbp-59h]
  HSTRING string; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v27; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-31h] BYREF
  __int64 v29; // [rsp+50h] [rbp-29h] BYREF
  __int64 v30; // [rsp+58h] [rbp-21h] BYREF
  __int64 v31; // [rsp+60h] [rbp-19h] BYREF
  __int64 v32[2]; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF
  __int64 v34; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v30 = a1;
  v32[0] = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  ActivationFactory = RoGetActivationFactory(v34, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, v32);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v24);
  v29 = 0;
  v7 = v32[0];
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32[0] + 80LL);
  v29 = 0;
  v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v30);
  v10 = v8(v7, *(_QWORD *)(v9 + 24), &v29);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)v10,
      v24);
  v31 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  v11 = RoGetActivationFactory(v34, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v31);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)v11,
      v24);
  v28 = 0;
  v12 = v31;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 **))(*(_QWORD *)v31 + 240LL);
  v28 = 0;
  v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v30);
  v15 = v13(v12, v29, *(_QWORD *)(v14 + 24), &v28);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)v15,
      v24);
  v27 = 0;
  v16 = *v28;
  v27 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v16 + 72))(v28, &v27);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)v17,
      v24);
  v26 = 0;
  v18 = *v27;
  v26 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v18 + 72))(v27, &v26);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)v19,
      v24);
  string = 0;
  v20 = *v26;
  string = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v20 + 88))(v26, &string);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
      (const char *)(unsigned int)v21,
      v24);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(a1, (__int64)StringRawBuffer);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v26);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v27);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((__int64 *)&v28);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v31);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v32);
  return a1;
}

```

## disassembly

```asm
0x140060d70  push    rbp
0x140060d72  push    rbx
0x140060d73  push    rsi
0x140060d74  push    rdi
0x140060d75  push    r12
0x140060d77  push    r14
0x140060d79  push    r15
0x140060d7b  lea     rbp, [rsp-27h]
0x140060d80  sub     rsp, 0A0h
0x140060d87  mov     rax, cs:__security_cookie
0x140060d8e  xor     rax, rsp
0x140060d91  mov     [rbp+57h+var_38], rax
0x140060d95  mov     r15, r8
0x140060d98  mov     r14, rdx
0x140060d9b  mov     rsi, rcx
0x140060d9e  mov     [rbp+57h+var_78], rcx
0x140060da2  xor     r12d, r12d
0x140060da5  mov     [rbp+57h+var_68], r12
0x140060da9  mov     [rbp+57h+var_40], r12
0x140060dad  lea     r9d, [r12+25h]; unsigned int
0x140060db2  lea     r8d, [r12+26h]; unsigned int
0x140060db7  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x140060dbe  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140060dc2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140060dc7  nop
0x140060dc8  lea     r8, [rbp+57h+var_68]
0x140060dcc  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x140060dd3  mov     rcx, [rbp+57h+var_40]
0x140060dd7  call    cs:__imp_RoGetActivationFactory
0x140060ddd  mov     rcx, [rbp+5Fh]; this
0x140060de1  test    eax, eax
0x140060de3  js      loc_140060FD3
0x140060de9  mov     [rbp+57h+var_80], r12
0x140060ded  mov     rdi, [rbp+57h+var_68]
0x140060df1  mov     rax, [rdi]
0x140060df4  mov     rbx, [rax+50h]
0x140060df8  mov     [rbp+57h+var_80], r12
0x140060dfc  mov     rcx, r14
0x140060dff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140060e04  mov     [rbp+57h+var_78], rax
0x140060e08  lea     rdx, [rbp+57h+var_78]
0x140060e0c  lea     rcx, [rbp+57h+hstringHeader]
0x140060e10  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140060e15  nop
0x140060e16  lea     r8, [rbp+57h+var_80]
0x140060e1a  mov     rdx, [rax+18h]
0x140060e1e  mov     rcx, rdi
0x140060e21  mov     rax, rbx
0x140060e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060e29  mov     rcx, [rbp+5Fh]; this
0x140060e2d  test    eax, eax
0x140060e2f  js      loc_140060FE8
0x140060e35  mov     [rbp+57h+var_70], r12
0x140060e39  mov     [rbp+57h+var_40], r12
0x140060e3d  lea     r9d, [r12+2Ch]; unsigned int
0x140060e42  lea     r8d, [r12+2Dh]; unsigned int
0x140060e47  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x140060e4e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140060e52  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140060e57  nop
0x140060e58  lea     r8, [rbp+57h+var_70]
0x140060e5c  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x140060e63  mov     rcx, [rbp+57h+var_40]
0x140060e67  call    cs:__imp_RoGetActivationFactory
0x140060e6d  mov     rcx, [rbp+5Fh]; this
0x140060e71  test    eax, eax
0x140060e73  js      loc_140060FFD
0x140060e79  mov     [rbp+57h+var_88], r12
0x140060e7d  mov     rdi, [rbp+57h+var_70]
0x140060e81  mov     rax, [rdi]
0x140060e84  mov     rbx, [rax+0F0h]
0x140060e8b  mov     [rbp+57h+var_88], r12
0x140060e8f  mov     rcx, r15
0x140060e92  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140060e97  mov     [rbp+57h+var_78], rax
0x140060e9b  lea     rdx, [rbp+57h+var_78]
0x140060e9f  lea     rcx, [rbp+57h+hstringHeader]
0x140060ea3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140060ea8  nop
0x140060ea9  lea     r9, [rbp+57h+var_88]
0x140060ead  mov     r8, [rax+18h]
0x140060eb1  mov     rdx, [rbp+57h+var_80]
0x140060eb5  mov     rcx, rdi
0x140060eb8  mov     rax, rbx
0x140060ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060ec0  mov     rcx, [rbp+5Fh]; this
0x140060ec4  test    eax, eax
0x140060ec6  js      loc_140061012
0x140060ecc  mov     [rbp+57h+var_90], r12
0x140060ed0  mov     rcx, [rbp+57h+var_88]
0x140060ed4  mov     rax, [rcx]
0x140060ed7  mov     [rbp+57h+var_90], r12
0x140060edb  lea     rdx, [rbp+57h+var_90]
0x140060edf  mov     rax, [rax+48h]
0x140060ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060ee8  mov     rcx, [rbp+5Fh]; this
0x140060eec  test    eax, eax
0x140060eee  js      loc_140061027
0x140060ef4  mov     [rbp+57h+var_98], r12
0x140060ef8  mov     rcx, [rbp+57h+var_90]
0x140060efc  mov     rax, [rcx]
0x140060eff  mov     [rbp+57h+var_98], r12
0x140060f03  lea     rdx, [rbp+57h+var_98]
0x140060f07  mov     rax, [rax+48h]
0x140060f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060f10  mov     rcx, [rbp+5Fh]; this
0x140060f14  test    eax, eax
0x140060f16  js      loc_14006103C
0x140060f1c  mov     [rbp+57h+string], r12
0x140060f20  mov     rcx, [rbp+57h+var_98]
0x140060f24  mov     rax, [rcx]
0x140060f27  mov     [rbp+57h+string], r12
0x140060f2b  lea     rdx, [rbp+57h+string]
0x140060f2f  mov     rax, [rax+58h]
0x140060f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060f38  mov     rcx, [rbp+5Fh]; this
0x140060f3c  test    eax, eax
0x140060f3e  js      short loc_140060FBE
0x140060f40  xor     edx, edx; length
0x140060f42  mov     rcx, [rbp+57h+string]; string
0x140060f46  call    cs:__imp_WindowsGetStringRawBuffer
0x140060f4c  mov     rdx, rax
0x140060f4f  mov     rcx, rsi
0x140060f52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140060f57  nop
0x140060f58  lea     rcx, [rbp+57h+string]; this
0x140060f5c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140060f61  nop
0x140060f62  lea     rcx, [rbp+57h+var_98]
0x140060f66  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140060f6b  nop
0x140060f6c  lea     rcx, [rbp+57h+var_90]
0x140060f70  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140060f75  nop
0x140060f76  lea     rcx, [rbp+57h+var_88]
0x140060f7a  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140060f7f  nop
0x140060f80  lea     rcx, [rbp+57h+var_70]
0x140060f84  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140060f89  nop
0x140060f8a  lea     rcx, [rbp+57h+var_80]
0x140060f8e  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140060f93  nop
0x140060f94  lea     rcx, [rbp+57h+var_68]
0x140060f98  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140060f9d  mov     rax, rsi
0x140060fa0  mov     rcx, [rbp+57h+var_38]
0x140060fa4  xor     rcx, rsp; StackCookie
0x140060fa7  call    __security_check_cookie
0x140060fac  add     rsp, 0A0h
0x140060fb3  pop     r15
0x140060fb5  pop     r14
0x140060fb7  pop     r12
0x140060fb9  pop     rdi
0x140060fba  pop     rsi
0x140060fbb  pop     rbx
0x140060fbc  pop     rbp
0x140060fbd  retn
0x140060fbe  mov     r9d, eax; char *
0x140060fc1  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140060fc8  mov     edx, 0BDh; void *
0x140060fcd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140060fd3  mov     r9d, eax; char *
0x140060fd6  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140060fdd  mov     edx, 0B1h; void *
0x140060fe2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140060fe8  mov     r9d, eax; char *
0x140060feb  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140060ff2  mov     edx, 0B3h; void *
0x140060ff7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140060ffd  mov     r9d, eax; char *
0x140061000  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140061007  mov     edx, 0B5h; void *
0x14006100c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140061012  mov     r9d, eax; char *
0x140061015  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006101c  mov     edx, 0B7h; void *
0x140061021  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140061027  mov     r9d, eax; char *
0x14006102a  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140061031  mov     edx, 0B9h; void *
0x140061036  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006103c  mov     r9d, eax; char *
0x14006103f  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140061046  mov     edx, 0BBh; void *
0x14006104b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
