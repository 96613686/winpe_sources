# Common::Services::GetTopologicalOrdering(SC_HANDLE__ *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180072474`
- end: `0x1800728e2`
- name: `?GetTopologicalOrdering@Services@Common@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUSC_HANDLE__@@AEBV34@@Z`
- size: `1134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a96c0`

## callees

- `0x180012fc8`
- `0x1800225fc`
- `0x18004e2a0`
- `0x18004eac0`
- `0x180050e60`
- `0x180064a88`
- `0x180066780`
- `0x180071178`
- `0x180071510`
- `0x18007154c`
- `0x1800715c4`
- `0x1800718d0`
- `0x180072418`
- `0x180072474`
- `0x180072a70`
- `0x180072cb4`
- `0x180073fc4`
- `0x180074504`
- `0x1800aed10`
- `0x1800e2c4c`
- `0x1800f24d8`
- `0x1800f29c8`
- `0x180187e90`
- `0x180187fc4`
- `0x1801880bc`
- `0x18018822c`
- `0x180188324`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800725fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800725fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072725`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072714`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180072584`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180072584`
- `ADVAPI32!EnumDependentServicesW` at `0x1800725e7`
- `ADVAPI32!EnumDependentServicesW` at `0x180072653`
- `ADVAPI32!EnumDependentServicesW` at `0x1800725e7`
- `ADVAPI32!EnumDependentServicesW` at `0x180072653`

## string_xrefs

- `0x18007253c`: `onecore\admin\appmodel\common\servicehelpers.cpp`
- `0x18007274a`: `onecore\admin\appmodel\common\servicehelpers.cpp`
- `0x180072769`: `onecore\admin\appmodel\common\servicehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 *__fastcall Common::Services::GetTopologicalOrdering(__int64 *a1, SC_HANDLE a2, WCHAR **a3)
{
  __int64 *v4; // r12
  unsigned __int64 v5; // r13
  int v6; // eax
  WCHAR *v7; // rsi
  __int64 *v8; // rdi
  SC_HANDLE v9; // r12
  const WCHAR *v10; // rdx
  SC_HANDLE v11; // rbx
  SC_HANDLE v12; // r15
  __int64 v13; // rbx
  __int64 v14; // rax
  signed int LastError; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  WCHAR *v18; // r9
  DWORD *v19; // rax
  bool v20; // si
  unsigned __int64 v21; // rbx
  WCHAR *v22; // rcx
  WCHAR *v23; // r9
  _QWORD *v24; // rcx
  LPDWORD pcbBytesNeeded; // [rsp+20h] [rbp-E0h]
  int pcbBytesNeededa; // [rsp+20h] [rbp-E0h]
  DWORD ServicesReturned; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbBufSize; // [rsp+34h] [rbp-CCh] BYREF
  SC_HANDLE hSCManager; // [rsp+38h] [rbp-C8h] BYREF
  SC_HANDLE hService; // [rsp+40h] [rbp-C0h] BYREF
  void *v32[2]; // [rsp+48h] [rbp-B8h] BYREF
  SC_HANDLE v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v34; // [rsp+60h] [rbp-A0h]
  __int64 *v35; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  _BYTE v39[24]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  _BYTE v42[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v43[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v44[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v45[64]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v46[32]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  hSCManager = a2;
  v4 = a1;
  v35 = a1;
  v34 = a1;
  v5 = 0;
  v37 = 0;
  v38 = 0;
  std::list<std::pair<std::wstring const,std::unique_ptr<OSIntegration::DEH::Internal::PackagedServiceExtensionHelper>>>::_Alloc_sentinel_and_proxy(&v37);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(v39);
  v40 = 7;
  v41 = 8;
  v36 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<OSIntegration::DEH::RegistryCompatibility::EntryPathAndPackageNamePair>>,std::_Iterator_base0>>>::_Assign_grow(
    v39,
    16,
    v37);
  ServicesReturned = 0;
  __0___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__0A__std___std__IEAA_AEBV___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__1_AEBV__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___1__Z(
    v45,
    &ServicesReturned);
  v32[0] = 0;
  v32[1] = 0;
  v6 = Common::ImpersonationContext::Impersonate(v32, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\admin\\appmodel\\common\\servicehelpers.cpp",
      (const char *)(unsigned int)v6,
      (int)pcbBytesNeeded);
  v7 = *a3;
  v8 = (__int64 *)a3[1];
  v34 = v8;
  if ( v7 != (WCHAR *)v8 )
  {
    v9 = hSCManager;
    do
    {
      hService = 0;
      if ( *((_QWORD *)v7 + 3) <= 7u )
        v10 = v7;
      else
        v10 = *(const WCHAR **)v7;
      v33 = OpenServiceW(v9, v10, 8u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>>::operator=(
        &hService,
        &v33);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v33);
      v11 = hService;
      if ( hService )
      {
        cbBufSize = 0;
        ServicesReturned = 0;
        if ( !EnumDependentServicesW(hService, 3u, 0, 0, &cbBufSize, &ServicesReturned) && GetLastError() == 234 )
        {
          wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hSCManager, cbBufSize);
          v12 = hSCManager;
          if ( hSCManager
            && EnumDependentServicesW(
                 v11,
                 3u,
                 (LPENUM_SERVICE_STATUSW)hSCManager,
                 cbBufSize,
                 &cbBufSize,
                 &ServicesReturned) )
          {
            if ( ServicesReturned )
            {
              do
              {
                v13 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::set<std::wstring>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::set<std::wstring>>>,0>>::_Try_emplace<std::wstring const &,>(
                                   v45,
                                   v43,
                                   v7);
                std::wstring::wstring(v46, *((_QWORD *)v12 + 6 * v5));
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                  v13 + 48,
                  v44,
                  v46);
                std::wstring::_Tidy_deallocate(v46);
                std::wstring::wstring(v46, *((_QWORD *)v12 + 6 * v5));
                v14 = std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring,>(
                        &v36,
                        v42,
                        v46);
                ++*(_DWORD *)(*(_QWORD *)v14 + 48LL);
                std::wstring::_Tidy_deallocate(v46);
                ++v5;
              }
              while ( v5 < ServicesReturned );
              v8 = v34;
            }
            v5 = 0;
          }
          hSCManager = 0;
          if ( v12 )
            LocalFree(v12);
        }
      }
      else
      {
        LastError = GetLastError();
        v16 = LastError;
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecore\\admin\\appmodel\\common\\servicehelpers.cpp",
          (const char *)v16,
          (int)pcbBytesNeeded);
        if ( (v16 & 0x80000000) != 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5E,
            (unsigned int)"onecore\\admin\\appmodel\\common\\servicehelpers.cpp",
            (const char *)v16,
            pcbBytesNeededa);
        if ( (byte_18024560B & 2) != 0 )
        {
          if ( *((_QWORD *)v7 + 3) <= 7u )
            v18 = v7;
          else
            v18 = *(WCHAR **)v7;
          McTemplateU0dz_EventWriteTransfer(
            &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
            SLMServiceOpenFailed,
            v16,
            v18);
        }
        if ( *((_QWORD *)v7 + 3) <= 7u )
          v19 = (DWORD *)v7;
        else
          v19 = *(DWORD **)v7;
        pcbBytesNeeded = v19;
        details::appxLog<long,unsigned short const *>(v16, v17, SLMServiceOpenFailed, v16);
      }
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hService);
      v7 += 16;
    }
    while ( v7 != (WCHAR *)v8 );
    v4 = v35;
  }
  v20 = v38 == 0;
  v21 = 0;
  v22 = *a3;
  v23 = a3[1];
  if ( ((char *)v23 - (char *)*a3) >> 5 )
  {
    do
    {
      v24 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OSIntegration::DEH::Internal::PackagedServiceExtensionHelper>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OSIntegration::DEH::Internal::PackagedServiceExtensionHelper>>>,0>>::find(
                        &v36,
                        &v35,
                        &v22[16 * v21]);
      if ( *v24 == v37 )
        *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring const &,>(
                                 &v36,
                                 v42,
                                 &(*a3)[16 * v21])
                  + 48LL) = 0;
      ++v21;
      v22 = *a3;
      v23 = a3[1];
    }
    while ( v21 < ((char *)v23 - (char *)*a3) >> 5 );
  }
  if ( v20 )
    std::vector<std::wstring>::vector<std::wstring>(v4, a3);
  else
    Common::Services::GetTopologicalOrderingHelper(v4, v45, &v36, ((char *)v23 - (char *)v22) >> 5, pcbBytesNeeded);
  if ( LODWORD(v32[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v32);
  __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2__std___2__0A__std___std__QEAA_XZ(v45);
  std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::~_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>(&v36);
  return v4;
}

```

## disassembly

```asm
0x180072474  mov     [rsp-8+arg_18], rbx
0x180072479  push    rbp
0x18007247a  push    rsi
0x18007247b  push    rdi
0x18007247c  push    r12
0x18007247e  push    r13
0x180072480  push    r14
0x180072482  push    r15
0x180072484  lea     rbp, [rsp-60h]
0x180072489  sub     rsp, 160h
0x180072490  mov     rax, cs:__security_cookie
0x180072497  xor     rax, rsp
0x18007249a  mov     [rbp+90h+var_40], rax
0x18007249e  mov     r14, r8
0x1800724a1  mov     [rsp+190h+hSCManager], rdx
0x1800724a6  mov     r12, rcx
0x1800724a9  mov     [rsp+190h+var_128], rcx
0x1800724ae  mov     [rsp+190h+var_130], rcx
0x1800724b3  xor     r13d, r13d
0x1800724b6  mov     [rsp+190h+var_120], r13d
0x1800724bb  mov     [rsp+190h+var_118], r13
0x1800724c0  mov     [rbp+90h+var_110], r13
0x1800724c4  lea     rcx, [rsp+190h+var_118]
0x1800724c9  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@U?$default_delete@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@U?$default_delete@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@@std@@@2@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,std::unique_ptr<OSIntegration::DEH::Internal::PackagedServiceExtensionHelper>>>::_Alloc_sentinel_and_proxy(void)
0x1800724ce  nop
0x1800724cf  lea     rcx, [rbp+90h+var_108]
0x1800724d3  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>> &&)
0x1800724d8  nop
0x1800724d9  mov     [rbp+90h+var_F0], 7
0x1800724e1  mov     [rbp+90h+var_E8], 8
0x1800724e9  mov     [rsp+190h+var_120], 3F800000h
0x1800724f1  mov     r8, [rsp+190h+var_118]
0x1800724f6  lea     edx, [r13+10h]
0x1800724fa  lea     rcx, [rbp+90h+var_108]
0x1800724fe  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UEntryPathAndPackageNamePair@RegistryCompatibility@DEH@OSIntegration@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UEntryPathAndPackageNamePair@RegistryCompatibility@DEH@OSIntegration@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<OSIntegration::DEH::RegistryCompatibility::EntryPathAndPackageNamePair>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<OSIntegration::DEH::RegistryCompatibility::EntryPathAndPackageNamePair>>,std::_Iterator_base0>)
0x180072503  nop
0x180072504  mov     [rsp+190h+ServicesReturned], r13d
0x180072509  lea     rdx, [rsp+190h+ServicesReturned]
0x18007250e  lea     rcx, [rbp+90h+var_A0]
0x180072512  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@1@@Z
0x180072517  nop
0x180072518  mov     [rsp+190h+var_148], r13
0x18007251d  mov     [rsp+190h+var_140], r13
0x180072522  xor     edx, edx; void *
0x180072524  lea     rcx, [rsp+190h+var_148]; this
0x180072529  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x18007252e  mov     rcx, [rbp+98h]; this
0x180072535  test    eax, eax
0x180072537  jns     short loc_18007254D
0x180072539  mov     r9d, eax; char *
0x18007253c  lea     r8, aOnecoreAdminAp_23; "onecore\\admin\\appmodel\\common\\servi"...
0x180072543  lea     edx, [r13+52h]; void *
0x180072547  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007254d  mov     rsi, [r14]
0x180072550  mov     rdi, [r14+8]
0x180072554  mov     [rsp+190h+var_130], rdi
0x180072559  cmp     rsi, rdi
0x18007255c  jz      loc_1800727EA
0x180072562  mov     r12, [rsp+190h+hSCManager]
0x180072567  mov     [rsp+190h+hService], r13
0x18007256c  cmp     qword ptr [rsi+18h], 7
0x180072571  jbe     short loc_180072578
0x180072573  mov     rdx, [rsi]
0x180072576  jmp     short loc_18007257B
0x180072578  mov     rdx, rsi; lpServiceName
0x18007257b  mov     r8d, 8; dwDesiredAccess
0x180072581  mov     rcx, r12; hSCManager
0x180072584  call    cs:__imp_OpenServiceW
0x18007258b  nop     dword ptr [rax+rax+00h]
0x180072590  mov     [rsp+190h+var_138], rax
0x180072595  lea     rdx, [rsp+190h+var_138]
0x18007259a  lea     rcx, [rsp+190h+hService]
0x18007259f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &&)
0x1800725a4  lea     rcx, [rsp+190h+var_138]
0x1800725a9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800725ae  mov     rbx, [rsp+190h+hService]
0x1800725b3  test    rbx, rbx
0x1800725b6  jz      loc_180072725
0x1800725bc  mov     [rsp+190h+cbBufSize], r13d
0x1800725c1  mov     [rsp+190h+ServicesReturned], r13d
0x1800725c6  lea     rax, [rsp+190h+ServicesReturned]
0x1800725cb  mov     [rsp+190h+lpServicesReturned], rax; lpServicesReturned
0x1800725d0  lea     rax, [rsp+190h+cbBufSize]
0x1800725d5  mov     [rsp+190h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800725da  xor     r9d, r9d; cbBufSize
0x1800725dd  xor     r8d, r8d; lpServices
0x1800725e0  lea     edx, [r9+3]; dwServiceState
0x1800725e4  mov     rcx, rbx; hService
0x1800725e7  call    cs:__imp_EnumDependentServicesW
0x1800725ee  nop     dword ptr [rax+rax+00h]
0x1800725f3  test    eax, eax
0x1800725f5  jnz     loc_1800727CE
0x1800725fb  call    cs:__imp_GetLastError
0x180072602  nop     dword ptr [rax+rax+00h]
0x180072607  cmp     eax, 0EAh
0x18007260c  jnz     loc_1800727CE
0x180072612  mov     edx, [rsp+190h+cbBufSize]
0x180072616  lea     rcx, [rsp+190h+hSCManager]
0x18007261b  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180072620  nop
0x180072621  mov     r15, [rsp+190h+hSCManager]
0x180072626  test    r15, r15
0x180072629  jz      loc_180072703
0x18007262f  lea     rax, [rsp+190h+ServicesReturned]
0x180072634  mov     [rsp+190h+lpServicesReturned], rax; lpServicesReturned
0x180072639  lea     rax, [rsp+190h+cbBufSize]
0x18007263e  mov     [rsp+190h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180072643  mov     r9d, [rsp+190h+cbBufSize]; cbBufSize
0x180072648  mov     r8, r15; lpServices
0x18007264b  mov     edx, 3; dwServiceState
0x180072650  mov     rcx, rbx; hService
0x180072653  call    cs:__imp_EnumDependentServicesW
0x18007265a  nop     dword ptr [rax+rax+00h]
0x18007265f  test    eax, eax
0x180072661  jz      loc_180072703
0x180072667  cmp     [rsp+190h+ServicesReturned], 0
0x18007266c  jbe     loc_180072700
0x180072672  mov     r8, rsi
0x180072675  lea     rdx, [rbp+90h+var_C8]
0x180072679  lea     rcx, [rbp+90h+var_A0]
0x18007267d  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z
0x180072682  mov     rbx, [rax]
0x180072685  lea     rdi, ds:0[r13*2]
0x18007268d  add     rdi, r13
0x180072690  add     rdi, rdi
0x180072693  mov     rdx, [r15+rdi*8]
0x180072697  lea     rcx, [rbp+90h+var_60]
0x18007269b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800726a0  nop
0x1800726a1  lea     r8, [rbp+90h+var_60]
0x1800726a5  lea     rdx, [rbp+90h+var_B8]
0x1800726a9  lea     rcx, [rbx+30h]
0x1800726ad  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x1800726b2  nop
0x1800726b3  lea     rcx, [rbp+90h+var_60]
0x1800726b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800726bc  mov     rdx, [r15+rdi*8]
0x1800726c0  lea     rcx, [rbp+90h+var_60]
0x1800726c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800726c9  nop
0x1800726ca  lea     r8, [rbp+90h+var_60]
0x1800726ce  lea     rdx, [rbp+90h+var_D8]
0x1800726d2  lea     rcx, [rsp+190h+var_120]
0x1800726d7  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800726dc  mov     rcx, [rax]
0x1800726df  inc     dword ptr [rcx+30h]
0x1800726e2  lea     rcx, [rbp+90h+var_60]
0x1800726e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800726eb  inc     r13
0x1800726ee  mov     eax, [rsp+190h+ServicesReturned]
0x1800726f2  cmp     r13, rax
0x1800726f5  jb      loc_180072672
0x1800726fb  mov     rdi, [rsp+190h+var_130]
0x180072700  xor     r13d, r13d
0x180072703  mov     [rsp+190h+hSCManager], r13
0x180072708  test    r15, r15
0x18007270b  jz      loc_1800727CE
0x180072711  mov     rcx, r15; hMem
0x180072714  call    cs:__imp_LocalFree
0x18007271b  nop     dword ptr [rax+rax+00h]
0x180072720  jmp     loc_1800727CE
0x180072725  call    cs:__imp_GetLastError
0x18007272c  nop     dword ptr [rax+rax+00h]
0x180072731  mov     ebx, eax
0x180072733  test    eax, eax
0x180072735  jle     short loc_180072740
0x180072737  movzx   ebx, ax
0x18007273a  or      ebx, 80070000h
0x180072740  mov     rcx, [rbp+98h]; this
0x180072747  mov     r9d, ebx; char *
0x18007274a  lea     r8, aOnecoreAdminAp_23; "onecore\\admin\\appmodel\\common\\servi"...
0x180072751  mov     edx, 5Dh ; ']'; void *
0x180072756  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007275b  mov     rcx, [rbp+98h]; this
0x180072762  test    ebx, ebx
0x180072764  jns     short loc_18007277A
0x180072766  mov     r9d, ebx; char *
0x180072769  lea     r8, aOnecoreAdminAp_23; "onecore\\admin\\appmodel\\common\\servi"...
0x180072770  mov     edx, 5Eh ; '^'; void *
0x180072775  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007277a  test    cs:byte_18024560B, 2
0x180072781  jz      short loc_1800727A8
0x180072783  cmp     qword ptr [rsi+18h], 7
0x180072788  jbe     short loc_18007278F
0x18007278a  mov     r9, [rsi]
0x18007278d  jmp     short loc_180072792
0x18007278f  mov     r9, rsi
0x180072792  mov     r8d, ebx
0x180072795  lea     rdx, SLMServiceOpenFailed
0x18007279c  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x1800727a3  call    McTemplateU0dz_EventWriteTransfer
0x1800727a8  cmp     qword ptr [rsi+18h], 7
0x1800727ad  jbe     short loc_1800727B4
0x1800727af  mov     rax, [rsi]
0x1800727b2  jmp     short loc_1800727B7
0x1800727b4  mov     rax, rsi
0x1800727b7  mov     [rsp+190h+pcbBytesNeeded], rax
0x1800727bc  mov     r9d, ebx
0x1800727bf  lea     r8, SLMServiceOpenFailed
0x1800727c6  mov     ecx, ebx
0x1800727c8  call    ??$appxLog@JPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG@Z; details::appxLog<long,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *)
0x1800727cd  nop
0x1800727ce  lea     rcx, [rsp+190h+hService]
0x1800727d3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800727d8  add     rsi, 20h ; ' '
0x1800727dc  cmp     rsi, rdi
0x1800727df  jnz     loc_180072567
0x1800727e5  mov     r12, [rsp+190h+var_128]
0x1800727ea  cmp     [rbp+90h+var_110], r13
0x1800727ee  setz    sil
0x1800727f2  mov     rbx, r13
0x1800727f5  mov     rcx, [r14]
0x1800727f8  mov     r9, [r14+8]
0x1800727fc  mov     rax, r9
0x1800727ff  sub     rax, rcx
0x180072802  sar     rax, 5
0x180072806  test    rax, rax
0x180072809  jz      short loc_180072866
0x18007280b  mov     rdi, rbx
0x18007280e  shl     rdi, 5
0x180072812  lea     r8, [rdi+rcx]
0x180072816  lea     rdx, [rsp+190h+var_128]
0x18007281b  lea     rcx, [rsp+190h+var_120]
0x180072820  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@U?$default_delete@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@U?$default_delete@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@U?$default_delete@VPackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OSIntegration::DEH::Internal::PackagedServiceExtensionHelper>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OSIntegration::DEH::Internal::PackagedServiceExtensionHelper>>>,0>>::find(std::wstring const &)
0x180072825  mov     rcx, rax
0x180072828  mov     rax, [rsp+190h+var_118]
0x18007282d  cmp     [rcx], rax
0x180072830  jnz     short loc_18007284D
0x180072832  mov     r8, [r14]
0x180072835  add     r8, rdi
0x180072838  lea     rdx, [rbp+90h+var_D8]
0x18007283c  lea     rcx, [rsp+190h+var_120]
0x180072841  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180072846  mov     rcx, [rax]
0x180072849  mov     [rcx+30h], r13d
0x18007284d  inc     rbx
0x180072850  mov     rcx, [r14]
0x180072853  mov     r9, [r14+8]
0x180072857  mov     rax, r9
0x18007285a  sub     rax, rcx
0x18007285d  sar     rax, 5
0x180072861  cmp     rbx, rax
0x180072864  jb      short loc_18007280B
0x180072866  test    sil, sil
0x180072869  jnz     short loc_180072885
0x18007286b  sub     r9, rcx
0x18007286e  sar     r9, 5
0x180072872  lea     r8, [rsp+190h+var_120]
0x180072877  lea     rdx, [rbp+90h+var_A0]
0x18007287b  mov     rcx, r12
0x18007287e  call    ?GetTopologicalOrderingHelper@Services@Common@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@4@AEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@4@_K@Z; Common::Services::GetTopologicalOrderingHelper(std::unordered_map<std::wstring,std::set<std::wstring>> const &,std::unordered_map<std::wstring,int> &,unsigned __int64)
0x180072883  jmp     short loc_180072891
0x180072885  mov     rdx, r14
0x180072888  mov     rcx, r12
0x18007288b  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180072890  nop
0x180072891  cmp     dword ptr [rsp+190h+var_148], r13d
0x180072896  jz      short loc_1800728A3
0x180072898  lea     rcx, [rsp+190h+var_148]; this
0x18007289d  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800728a2  nop
0x1800728a3  lea     rcx, [rbp+90h+var_A0]
0x1800728a7  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x1800728ac  nop
0x1800728ad  lea     rcx, [rsp+190h+var_120]
0x1800728b2  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::~_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>(void)
0x1800728b7  mov     rax, r12
0x1800728ba  mov     rcx, [rbp+90h+var_40]
0x1800728be  xor     rcx, rsp; StackCookie
0x1800728c1  call    __security_check_cookie
0x1800728c6  mov     rbx, [rsp+190h+arg_18]
0x1800728ce  add     rsp, 160h
0x1800728d5  pop     r15
0x1800728d7  pop     r14
0x1800728d9  pop     r13
0x1800728db  pop     r12
0x1800728dd  pop     rdi
0x1800728de  pop     rsi
0x1800728df  pop     rbp
0x1800728e0  retn
```
