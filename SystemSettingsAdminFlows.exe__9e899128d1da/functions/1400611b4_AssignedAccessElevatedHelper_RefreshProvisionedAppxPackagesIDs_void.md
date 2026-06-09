# AssignedAccessElevatedHelper::RefreshProvisionedAppxPackagesIDs(void)

- ea: `0x1400611b4`
- end: `0x140061700`
- name: `?RefreshProvisionedAppxPackagesIDs@AssignedAccessElevatedHelper@@SAJXZ`
- size: `1356`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x14000c3c8`
- `0x14000d850`
- `0x14000ed38`
- `0x140011b68`
- `0x14001a2a0`
- `0x140029eb8`
- `0x14002a2c0`
- `0x14002a304`
- `0x14002a3e8`
- `0x14002c070`
- `0x14003aed0`
- `0x140044f18`
- `0x140047aa8`
- `0x14005eaf0`
- `0x14005ffc0`
- `0x1400611b4`
- `0x140062608`
- `0x14007d010`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x140061564`
- `KERNEL32!RegCreateKeyExW` at `0x140061564`
- `KERNEL32!RegSetValueExW` at `0x1400615b6`
- `KERNEL32!RegSetValueExW` at `0x1400615b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400612c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400612c4`
- `DismApi!DismCloseSession` at `0x14006163d`
- `DismApi!DismCloseSession` at `0x14006163d`
- `DismApi!DismInitialize` at `0x1400611ec`
- `DismApi!DismInitialize` at `0x1400611ec`
- `DismApi!DismOpenSession` at `0x14006121b`
- `DismApi!DismOpenSession` at `0x14006121b`
- `DismApi!_DismGetProvisionedAppxPackages` at `0x140061260`
- `DismApi!_DismGetProvisionedAppxPackages` at `0x140061260`

## string_xrefs

- `0x1400614e9`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x1400614fe`: `ProvisionedAppxPackagesIDs`
- `0x140061671`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x140061685`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x14006169a`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x1400616af`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x1400616c4`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x1400616d9`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`
- `0x1400616ed`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesselevatedhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 AssignedAccessElevatedHelper::RefreshProvisionedAppxPackagesIDs(void)
{
  int v0; // r15d
  int v1; // eax
  int v2; // eax
  unsigned int v3; // ebx
  int ProvisionedAppxPackages; // eax
  __int64 v5; // r12
  int ActivationFactory; // eax
  unsigned int i; // r14d
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // edi
  int v16; // esi
  const WCHAR *v17; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  const WCHAR *v20; // rax
  DWORD v21; // r8d
  const BYTE *v22; // r10
  unsigned int v23; // eax
  const char *v24; // r9
  __int64 result; // rax
  int dwOptions; // [rsp+20h] [rbp-188h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-188h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-188h]
  unsigned int v29; // [rsp+50h] [rbp-158h] BYREF
  unsigned int v30; // [rsp+54h] [rbp-154h] BYREF
  __int64 v31; // [rsp+58h] [rbp-150h] BYREF
  __int64 v32; // [rsp+60h] [rbp-148h] BYREF
  __int128 v33; // [rsp+68h] [rbp-140h] BYREF
  __int64 v34; // [rsp+78h] [rbp-130h]
  HKEY hKey; // [rsp+80h] [rbp-128h] BYREF
  __int64 v36; // [rsp+88h] [rbp-120h] BYREF
  __int64 v37; // [rsp+90h] [rbp-118h] BYREF
  unsigned int v38; // [rsp+98h] [rbp-110h]
  char v39; // [rsp+9Ch] [rbp-10Ch]
  __int64 v40; // [rsp+A0h] [rbp-108h] BYREF
  int v41; // [rsp+A8h] [rbp-100h] BYREF
  int *v42; // [rsp+B0h] [rbp-F8h]
  int v43; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-E8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-E0h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-C8h]
  _BYTE v47[32]; // [rsp+E8h] [rbp-C0h] BYREF
  _BYTE v48[32]; // [rsp+108h] [rbp-A0h] BYREF
  _BYTE v49[32]; // [rsp+128h] [rbp-80h] BYREF
  _BYTE v50[32]; // [rsp+148h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v0 = 0;
  v29 = 0;
  v1 = DismInitialize(2, 0, 0);
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
        (const char *)(unsigned int)v1,
        dwOptions);
    v30 = -1073479676;
    v2 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v30);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
        (const char *)(unsigned int)v2,
        dwOptions);
    v3 = v30;
    v38 = v30;
    v39 = 1;
    v29 = 0;
    v37 = 0;
    ProvisionedAppxPackages = _DismGetProvisionedAppxPackages(v30, &v37, &v29);
    if ( ProvisionedAppxPackages < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
        (const char *)(unsigned int)ProvisionedAppxPackages,
        dwOptions);
    v5 = v37;
    v36 = 0;
    v46 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Package",
      0x29u,
      0x28u);
    ActivationFactory = RoGetActivationFactory(v46, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v36);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
        (const char *)(unsigned int)ActivationFactory,
        dwOptions);
    v33 = 0;
    v34 = 0;
    for ( i = 0; i < v29; ++i )
    {
      v8 = 68LL * i;
      std::wstring::wstring(v48, *(_QWORD *)(v8 + v5 + 8));
      std::wstring::wstring(v47, *(_QWORD *)(v8 + v5 + 16));
      v9 = std::operator+<unsigned short>(&v40, v48);
      std::operator+<unsigned short>(&hstringHeader, v9, v47);
      std::wstring::_Tidy_deallocate(&v40);
      v32 = 0;
      v10 = v36;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v36 + 392LL);
      v32 = 0;
      v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
      v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v40, &v31);
      v13 = v11(v10, *(_QWORD *)(v12 + 24), 17, &v32);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10D,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
          (const char *)(unsigned int)v13,
          dwOptions);
      v40 = v32;
      v42 = &v43;
      v43 = 0;
      v44 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 56LL))(v32, &v41);
      *v42 = v14;
      wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::get_at_current(
        &v40,
        0);
      v15 = 0;
      v16 = v41;
      while ( *v42 >= 0 && v15 != v16 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL))(v44, &v31);
        if ( *((_QWORD *)&v33 + 1) == v34 )
        {
          std::vector<__int64>::_Emplace_reallocate<__int64 &>(&v33, *((_QWORD *)&v33 + 1), &v31);
        }
        else
        {
          **((_QWORD **)&v33 + 1) = v31;
          *((_QWORD *)&v33 + 1) += 8LL;
        }
        wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::get_at_current(
          &v40,
          (unsigned int)++v15);
      }
      v0 |= 3u;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v32);
      std::wstring::_Tidy_deallocate(&hstringHeader);
      std::wstring::_Tidy_deallocate(v47);
      std::wstring::_Tidy_deallocate(v48);
    }
    std::wstring::wstring(v50, L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration");
    std::wstring::wstring(v49, L"ProvisionedAppxPackagesIDs");
    hKey = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 0, 0, 0x20006u, 0, phkResult, 0);
    if ( Key )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x11A,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
        (const char *)Key,
        dwOptionsa);
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
    v23 = RegSetValueExW(hKey, v20, 0, 3u, v22, v21);
    if ( v23 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x11D,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
        (const char *)v23,
        dwOptionsb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v49);
    std::wstring::_Tidy_deallocate(v50);
    if ( (_QWORD)v33 )
    {
      std::_Deallocate<16>(v33, (v34 - v33) & 0xFFFFFFFFFFFFFFF8uLL);
      v33 = 0;
      v34 = 0;
    }
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>(&v37);
    DismCloseSession(v3);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x121,
                           (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesselevatedhelper.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x1400611b4  push    rbx
0x1400611b6  push    rsi
0x1400611b7  push    rdi
0x1400611b8  push    r12
0x1400611ba  push    r13
0x1400611bc  push    r14
0x1400611be  push    r15
0x1400611c0  sub     rsp, 170h
0x1400611c7  mov     rax, cs:__security_cookie
0x1400611ce  xor     rax, rsp
0x1400611d1  mov     [rsp+1A8h+var_40], rax
0x1400611d9  xor     r13d, r13d
0x1400611dc  mov     r15d, r13d
0x1400611df  mov     [rsp+1A8h+var_158], r13d
0x1400611e4  xor     r8d, r8d
0x1400611e7  xor     edx, edx
0x1400611e9  lea     ecx, [rdx+2]
0x1400611ec  call    cs:__imp_DismInitialize
0x1400611f2  mov     rcx, [rsp+1A8h]; this
0x1400611fa  test    eax, eax
0x1400611fc  js      loc_14006166E
0x140061202  mov     [rsp+1A8h+var_154], 0C0040004h
0x14006120a  lea     r9, [rsp+1A8h+var_154]
0x14006120f  xor     r8d, r8d
0x140061212  xor     edx, edx
0x140061214  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x14006121b  call    cs:__imp_DismOpenSession
0x140061221  mov     rcx, [rsp+1A8h]; this
0x140061229  test    eax, eax
0x14006122b  js      loc_140061682
0x140061231  mov     ebx, [rsp+1A8h+var_154]
0x140061235  mov     [rsp+1A8h+var_110], ebx
0x14006123c  mov     [rsp+1A8h+var_10C], 1
0x140061244  mov     [rsp+1A8h+var_158], r13d
0x140061249  mov     [rsp+1A8h+var_118], r13
0x140061251  lea     r8, [rsp+1A8h+var_158]
0x140061256  lea     rdx, [rsp+1A8h+var_118]
0x14006125e  mov     ecx, ebx
0x140061260  call    cs:__imp__DismGetProvisionedAppxPackages
0x140061266  mov     rcx, [rsp+1A8h]; this
0x14006126e  test    eax, eax
0x140061270  js      loc_140061697
0x140061276  mov     r12, [rsp+1A8h+var_118]
0x14006127e  mov     [rsp+1A8h+var_120], r13
0x140061286  mov     [rsp+1A8h+var_C8], r13
0x14006128e  mov     r9d, 28h ; '('; unsigned int
0x140061294  lea     r8d, [r9+1]; unsigned int
0x140061298  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x14006129f  lea     rcx, [rsp+1A8h+hstringHeader]; hstringHeader
0x1400612a7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400612ac  nop
0x1400612ad  lea     r8, [rsp+1A8h+var_120]
0x1400612b5  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1400612bc  mov     rcx, [rsp+1A8h+var_C8]
0x1400612c4  call    cs:__imp_RoGetActivationFactory
0x1400612ca  mov     rcx, [rsp+1A8h]; this
0x1400612d2  test    eax, eax
0x1400612d4  js      loc_1400616AC
0x1400612da  xorps   xmm0, xmm0
0x1400612dd  movdqu  [rsp+1A8h+var_140], xmm0
0x1400612e3  mov     [rsp+1A8h+var_130], r13
0x1400612e8  mov     r14d, r13d
0x1400612eb  cmp     r14d, [rsp+1A8h+var_158]
0x1400612f0  jnb     loc_1400614E9
0x1400612f6  mov     eax, r14d
0x1400612f9  imul    rdi, rax, 44h ; 'D'
0x1400612fd  mov     rdx, [rdi+r12+8]
0x140061302  lea     rcx, [rsp+1A8h+var_A0]
0x14006130a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006130f  nop
0x140061310  mov     rdx, [rdi+r12+10h]
0x140061315  lea     rcx, [rsp+1A8h+var_C0]
0x14006131d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140061322  nop
0x140061323  lea     rdx, [rsp+1A8h+var_A0]
0x14006132b  lea     rcx, [rsp+1A8h+var_108]
0x140061333  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x140061338  nop
0x140061339  lea     r8, [rsp+1A8h+var_C0]
0x140061341  mov     rdx, rax
0x140061344  lea     rcx, [rsp+1A8h+hstringHeader]
0x14006134c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140061351  nop
0x140061352  lea     rcx, [rsp+1A8h+var_108]
0x14006135a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006135f  mov     [rsp+1A8h+var_148], r13
0x140061364  mov     rsi, [rsp+1A8h+var_120]
0x14006136c  mov     rax, [rsi]
0x14006136f  mov     rdi, [rax+188h]
0x140061376  mov     [rsp+1A8h+var_148], r13
0x14006137b  lea     rcx, [rsp+1A8h+hstringHeader]
0x140061383  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140061388  mov     [rsp+1A8h+var_150], rax
0x14006138d  lea     rdx, [rsp+1A8h+var_150]
0x140061392  lea     rcx, [rsp+1A8h+var_108]
0x14006139a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14006139f  nop
0x1400613a0  lea     r9, [rsp+1A8h+var_148]
0x1400613a5  mov     r8d, 11h
0x1400613ab  mov     rdx, [rax+18h]
0x1400613af  mov     rcx, rsi
0x1400613b2  mov     rax, rdi
0x1400613b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400613ba  mov     rcx, [rsp+1A8h]; this
0x1400613c2  test    eax, eax
0x1400613c4  js      loc_1400616C1
0x1400613ca  mov     rcx, [rsp+1A8h+var_148]
0x1400613cf  mov     [rsp+1A8h+var_108], rcx
0x1400613d7  lea     rax, [rsp+1A8h+var_F0]
0x1400613df  mov     [rsp+1A8h+var_F8], rax
0x1400613e7  mov     [rsp+1A8h+var_F0], r13d
0x1400613ef  mov     [rsp+1A8h+var_E8], r13
0x1400613f7  mov     rax, [rcx]
0x1400613fa  lea     rdx, [rsp+1A8h+var_100]
0x140061402  mov     rax, [rax+38h]
0x140061406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006140b  mov     rcx, [rsp+1A8h+var_F8]
0x140061413  mov     [rcx], eax
0x140061415  xor     edx, edx
0x140061417  lea     rcx, [rsp+1A8h+var_108]
0x14006141f  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::get_at_current(uint)
0x140061424  mov     edi, r13d
0x140061427  mov     esi, [rsp+1A8h+var_100]
0x14006142e  mov     rax, [rsp+1A8h+var_F8]
0x140061436  cmp     [rax], r13d
0x140061439  jl      short loc_14006149B
0x14006143b  cmp     edi, esi
0x14006143d  jz      short loc_14006149B
0x14006143f  mov     [rsp+1A8h+var_150], r13
0x140061444  mov     rcx, [rsp+1A8h+var_E8]
0x14006144c  mov     rax, [rcx]
0x14006144f  lea     rdx, [rsp+1A8h+var_150]
0x140061454  mov     rax, [rax+30h]
0x140061458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006145d  mov     rdx, qword ptr [rsp+1A8h+var_140+8]
0x140061462  cmp     rdx, [rsp+1A8h+var_130]
0x140061467  jz      short loc_140061479
0x140061469  mov     rax, [rsp+1A8h+var_150]
0x14006146e  mov     [rdx], rax
0x140061471  add     qword ptr [rsp+1A8h+var_140+8], 8
0x140061477  jmp     short loc_140061488
0x140061479  lea     r8, [rsp+1A8h+var_150]
0x14006147e  lea     rcx, [rsp+1A8h+var_140]
0x140061483  call    ??$_Emplace_reallocate@AEA_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEA_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 &>(__int64 * const,__int64 &)
0x140061488  inc     edi
0x14006148a  mov     edx, edi
0x14006148c  lea     rcx, [rsp+1A8h+var_108]
0x140061494  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::get_at_current(uint)
0x140061499  jmp     short loc_14006142E
0x14006149b  or      r15d, 3
0x14006149f  lea     rcx, [rsp+1A8h+var_E8]
0x1400614a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400614ac  nop
0x1400614ad  lea     rcx, [rsp+1A8h+var_148]
0x1400614b2  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1400614b7  nop
0x1400614b8  lea     rcx, [rsp+1A8h+hstringHeader]
0x1400614c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400614c5  nop
0x1400614c6  lea     rcx, [rsp+1A8h+var_C0]
0x1400614ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400614d3  nop
0x1400614d4  lea     rcx, [rsp+1A8h+var_A0]
0x1400614dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400614e1  inc     r14d
0x1400614e4  jmp     loc_1400612EB
0x1400614e9  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x1400614f0  lea     rcx, [rsp+1A8h+var_60]
0x1400614f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400614fd  nop
0x1400614fe  lea     rdx, aProvisionedapp; "ProvisionedAppxPackagesIDs"
0x140061505  lea     rcx, [rsp+1A8h+var_80]
0x14006150d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140061512  nop
0x140061513  mov     [rsp+1A8h+hKey], r13
0x14006151b  lea     rcx, [rsp+1A8h+hKey]
0x140061523  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140061528  mov     r8, rax
0x14006152b  lea     rcx, [rsp+1A8h+var_60]
0x140061533  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140061538  mov     rdx, rax; lpSubKey
0x14006153b  mov     [rsp+1A8h+lpdwDisposition], r13; lpdwDisposition
0x140061540  mov     [rsp+1A8h+phkResult], r8; phkResult
0x140061545  mov     [rsp+1A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14006154a  mov     [rsp+1A8h+samDesired], 20006h; samDesired
0x140061552  mov     [rsp+1A8h+dwOptions], r13d; unsigned int
0x140061557  xor     r9d, r9d; lpClass
0x14006155a  xor     r8d, r8d; Reserved
0x14006155d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140061564  call    cs:__imp_RegCreateKeyExW
0x14006156a  mov     rcx, [rsp+1A8h]; this
0x140061572  test    eax, eax
0x140061574  jnz     loc_1400616D6
0x14006157a  mov     r10, qword ptr [rsp+1A8h+var_140]
0x14006157f  mov     r8, qword ptr [rsp+1A8h+var_140+8]
0x140061584  sub     r8, r10
0x140061587  and     r8d, 0FFFFFFF8h
0x14006158b  lea     rcx, [rsp+1A8h+var_80]
0x140061593  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140061598  mov     rdx, rax; lpValueName
0x14006159b  mov     [rsp+1A8h+samDesired], r8d; cbData
0x1400615a0  mov     qword ptr [rsp+1A8h+dwOptions], r10; unsigned int
0x1400615a5  mov     r9d, 3; dwType
0x1400615ab  xor     r8d, r8d; Reserved
0x1400615ae  mov     rcx, [rsp+1A8h+hKey]; hKey
0x1400615b6  call    cs:__imp_RegSetValueExW
0x1400615bc  mov     rcx, [rsp+1A8h]; this
0x1400615c4  test    eax, eax
0x1400615c6  jnz     loc_1400616EA
0x1400615cc  lea     rcx, [rsp+1A8h+hKey]
0x1400615d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400615d9  nop
0x1400615da  lea     rcx, [rsp+1A8h+var_80]
0x1400615e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400615e7  nop
0x1400615e8  lea     rcx, [rsp+1A8h+var_60]
0x1400615f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400615f5  nop
0x1400615f6  mov     rcx, qword ptr [rsp+1A8h+var_140]
0x1400615fb  test    rcx, rcx
0x1400615fe  jz      short loc_14006161F
0x140061600  mov     rdx, [rsp+1A8h+var_130]
0x140061605  sub     rdx, rcx
0x140061608  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14006160c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140061611  xorps   xmm0, xmm0
0x140061614  movdqu  [rsp+1A8h+var_140], xmm0
0x14006161a  mov     [rsp+1A8h+var_130], r13
0x14006161f  lea     rcx, [rsp+1A8h+var_120]
0x140061627  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14006162c  nop
0x14006162d  lea     rcx, [rsp+1A8h+var_118]
0x140061635  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismAppxPackage@@P6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismAppxPackage *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismAppxPackage *,_DismAppxPackage *,0,std::nullptr_t>>(void)
0x14006163a  nop
0x14006163b  mov     ecx, ebx
0x14006163d  call    cs:__imp_DismCloseSession
0x140061643  xor     eax, eax
0x140061645  jmp     short loc_14006164B
0x140061647  mov     eax, [rsp+1A8h+var_158]
0x14006164b  mov     rcx, [rsp+1A8h+var_40]
0x140061653  xor     rcx, rsp; StackCookie
0x140061656  call    __security_check_cookie
0x14006165b  add     rsp, 170h
0x140061662  pop     r15
0x140061664  pop     r14
0x140061666  pop     r13
0x140061668  pop     r12
0x14006166a  pop     rdi
0x14006166b  pop     rsi
0x14006166c  pop     rbx
0x14006166d  retn
0x14006166e  mov     r9d, eax; char *
0x140061671  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x140061678  mov     edx, 0F1h; void *
0x14006167d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140061682  mov     r9d, eax; char *
0x140061685  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006168c  mov     edx, 0F3h; void *
0x140061691  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140061697  mov     r9d, eax; char *
0x14006169a  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400616a1  mov     edx, 0FCh; void *
0x1400616a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400616ac  mov     r9d, eax; char *
0x1400616af  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400616b6  mov     edx, 100h; void *
0x1400616bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400616c1  mov     r9d, eax; char *
0x1400616c4  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400616cb  mov     edx, 10Dh; void *
0x1400616d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400616d6  mov     r9d, eax; char *
0x1400616d9  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400616e0  mov     edx, 11Ah; void *
0x1400616e5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1400616ea  mov     r9d, eax; char *
0x1400616ed  lea     r8, aPcshellShellSy_28; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400616f4  mov     edx, 11Dh; void *
0x1400616f9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
