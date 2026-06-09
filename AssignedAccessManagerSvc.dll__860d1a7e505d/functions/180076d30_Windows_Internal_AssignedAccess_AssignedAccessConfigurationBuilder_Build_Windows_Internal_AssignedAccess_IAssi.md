# Windows::Internal::AssignedAccess::AssignedAccessConfigurationBuilder::Build(Windows::Internal::AssignedAccess::IAssignedAccessConfiguration * *)

- ea: `0x180076d30`
- end: `0x180077f22`
- name: `?Build@AssignedAccessConfigurationBuilder@AssignedAccess@Internal@Windows@@UEAAJPEAPEAUIAssignedAccessConfiguration@234@@Z`
- size: `4594`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigurationBuilder *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration **)`
- caller_count: `0`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006640`
- `0x180008d89`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010590`
- `0x180010c98`
- `0x180013fac`
- `0x180014a5c`
- `0x180014b00`
- `0x18001f2b0`
- `0x1800200e4`
- `0x180022d00`
- `0x1800262e0`
- `0x1800271e4`
- `0x1800272d0`
- `0x1800272e0`
- `0x180028f14`
- `0x18002901c`
- `0x18002bc2c`
- `0x18002bd18`
- `0x18002be50`
- `0x18002c5a4`
- `0x18003185c`
- `0x180037454`
- `0x18003a810`
- `0x180074650`
- `0x180076308`
- `0x1800765c8`
- `0x180076750`
- `0x180076988`
- `0x180076b78`
- `0x180076d30`
- `0x1800781fc`
- `0x1800784d8`
- `0x18007a58c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180076f88`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007726c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180076f88`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007726c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077c41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077c41`

## string_xrefs

- `0x180076ea1`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180076f0e`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180076fac`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077070`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x1800771e1`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077290`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077371`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077406`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x1800774a6`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077530`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x1800775c1`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077668`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077706`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x1800777b2`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x18007784f`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x1800778d0`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x18007796e`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077a15`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077ace`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077bb3`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077cc9`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077df5`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x180077e60`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfigurationbuilder.cpp`
- `0x18007734d`: `A profile ID used by one or more configs is not found: %ws`
- `0x180076d62`: `BuildAssignedAccessConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigurationBuilder::Build(
        Windows::Internal::AssignedAccess::AssignedAccessConfigurationBuilder *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration **a2)
{
  int v4; // edi
  _QWORD *v5; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  HRESULT v9; // ebx
  _QWORD *v10; // rax
  bool v11; // bl
  _QWORD *v12; // rax
  unsigned __int64 v13; // r15
  int v14; // r12d
  __int64 **v15; // rsi
  int v16; // eax
  unsigned int v17; // ebx
  HRESULT v18; // ebx
  __int64 v19; // rbx
  __int64 *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // edi
  int v26; // eax
  unsigned int v27; // edi
  int v28; // edi
  int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // edi
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int Instance; // eax
  unsigned int v37; // ebx
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // ebx
  Windows::Internal::AssignedAccess *v41; // rdi
  __int64 (__fastcall *v42)(Windows::Internal::AssignedAccess *, HSTRING *); // rbx
  int v43; // eax
  unsigned int v44; // ebx
  PCWSTR StringRawBuffer; // rdi
  _QWORD *v46; // rax
  bool v47; // bl
  __int64 v48; // rcx
  int v49; // eax
  unsigned int v50; // ebx
  int v51; // eax
  unsigned int v52; // ebx
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **v53; // [rsp+20h] [rbp-308h] BYREF
  Windows::Internal::AssignedAccess *v54; // [rsp+28h] [rbp-300h] BYREF
  __int64 v55; // [rsp+30h] [rbp-2F8h] BYREF
  HSTRING v56; // [rsp+38h] [rbp-2F0h] BYREF
  int v57; // [rsp+40h] [rbp-2E8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-2E0h] BYREF
  int v59; // [rsp+50h] [rbp-2D8h] BYREF
  _BYTE v60[24]; // [rsp+58h] [rbp-2D0h] BYREF
  _BYTE v61[8]; // [rsp+70h] [rbp-2B8h] BYREF
  int v62; // [rsp+78h] [rbp-2B0h]
  _BYTE v63[16]; // [rsp+90h] [rbp-298h] BYREF
  int v64; // [rsp+A0h] [rbp-288h] BYREF
  _QWORD v65[2]; // [rsp+A8h] [rbp-280h] BYREF
  _BYTE v66[24]; // [rsp+B8h] [rbp-270h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-258h]
  __int64 v68; // [rsp+D8h] [rbp-250h]
  PCWSTR v69; // [rsp+E0h] [rbp-248h] BYREF
  __int64 v70; // [rsp+E8h] [rbp-240h] BYREF
  int v71; // [rsp+F0h] [rbp-238h]
  _BYTE v72[8]; // [rsp+100h] [rbp-228h] BYREF
  __int64 v73; // [rsp+108h] [rbp-220h]
  __int64 v74; // [rsp+140h] [rbp-1E8h] BYREF
  HSTRING *v75; // [rsp+148h] [rbp-1E0h] BYREF
  LPOLESTR lpsz; // [rsp+150h] [rbp-1D8h] BYREF
  char v77; // [rsp+158h] [rbp-1D0h]
  IID Buf1; // [rsp+160h] [rbp-1C8h] BYREF
  __int64 *v79; // [rsp+170h] [rbp-1B8h] BYREF
  LPOLESTR v80; // [rsp+178h] [rbp-1B0h] BYREF
  char v81; // [rsp+180h] [rbp-1A8h]
  IID rclsid; // [rsp+190h] [rbp-198h] BYREF
  _QWORD v83[42]; // [rsp+1A0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v83,
    "BuildAssignedAccessConfiguration");
  v83[0] = &AssignedAccessTelemetry::BuildAssignedAccessConfiguration::`vftable';
  AssignedAccessTelemetry::BuildAssignedAccessConfiguration::StartActivity((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
  v65[0] = 0;
  v65[1] = 0;
  std::list<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>>::_Alloc_sentinel_and_proxy(v65);
  std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(v66);
  v67 = 7;
  v68 = 8;
  v64 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v66,
    16,
    v65[0]);
  wil::get_range_nothrow<Windows::Internal::AssignedAccess::AssignedAccessProfile *>(v61, *((_QWORD *)this + 2));
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::begin(
    v61,
    &v70);
  v4 = v62;
  while ( **(int **)(v70 + 16) >= 0 && v71 != v4 )
  {
    v5 = (_QWORD *)wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *>>::vector_iterator_nothrow::operator*(&v70);
    Buf1 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, IID *))(*(_QWORD *)*v5 + 56LL))(*v5, &Buf1);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v6,
        (int)v53);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v7;
    }
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)0x80070057LL,
        (int)v53);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return 2147942487LL;
    }
    v56 = 0;
    v75 = &v56;
    lpsz = 0;
    v77 = 1;
    v9 = StringFromCLSID(&Buf1, &lpsz);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v75);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v9,
        (int)v53);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return (unsigned int)v9;
    }
    std::wstring::wstring(&v79, v56);
    v10 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                      &v64,
                      &v69,
                      &v79);
    v11 = *v10 != v65[0];
    std::wstring::_Tidy_deallocate(&v79);
    if ( v11 )
    {
      wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
        v83,
        "Duplicated profile ID is found: %ws",
        v56);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)0x80070057LL,
        (int)v53);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return 2147942487LL;
    }
    std::wstring::wstring(&v79, v56);
    v12 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::_Try_emplace<std::wstring,>(
                      (float *)&v64,
                      (__int64)&rclsid,
                      (__int64)&v79);
    wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(
      *v12 + 48LL,
      *v5);
    std::wstring::_Tidy_deallocate(&v79);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>>::vector_iterator_nothrow::operator+=(&v70);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
  v13 = 0;
  std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(v60);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v72);
  wil::get_range_nothrow<Windows::Internal::AssignedAccess::AssignedAccessProfile *>(v61, *((_QWORD *)this + 3));
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::begin(
    v61,
    &Buf1);
  v14 = v62;
  while ( **(int **)(*(_QWORD *)&Buf1.Data1 + 16LL) >= 0 && *(_DWORD *)Buf1.Data4 != v14 )
  {
    v15 = (__int64 **)wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *>>::vector_iterator_nothrow::operator*(&Buf1);
    rclsid = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, IID *))(**v15 + 64))(*v15, &rclsid);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v16,
        (int)v53);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v17;
    }
    v55 = 0;
    v79 = &v55;
    v80 = 0;
    v81 = 1;
    v18 = StringFromCLSID(&rclsid, &v80);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v79);
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v18,
        (int)v53);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return (unsigned int)v18;
    }
    std::wstring::wstring(&v79, v55);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
      &v64,
      &v74,
      &v79);
    std::wstring::_Tidy_deallocate(&v79);
    v19 = v74;
    if ( v74 == v65[0] )
    {
      wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
        v83,
        "A profile ID used by one or more configs is not found: %ws",
        v55);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)0x80070057LL,
        (int)v53);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return 2147942487LL;
    }
    v54 = 0;
    v20 = *v15;
    v21 = **v15;
    v54 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, Windows::Internal::AssignedAccess **))(v21 + 48))(v20, &v54);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v22,
        (int)v53);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v23;
    }
    v59 = 0;
    v24 = (*(__int64 (__fastcall **)(Windows::Internal::AssignedAccess *, int *))(*(_QWORD *)v54 + 80LL))(v54, &v59);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v24,
        (int)v53);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v25;
    }
    if ( v59 == -1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)0x8000FFFFLL,
        (int)v53);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return 2147549183LL;
    }
    if ( v59 == 1 )
      ++v13;
    if ( v13 > 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)0x80070057LL,
        (int)v53);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return 2147942487LL;
    }
    if ( v59 == 300 )
    {
      LOBYTE(v53) = 0;
      v26 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo ***))(**(_QWORD **)(v19 + 48) + 72LL))(
              *(_QWORD *)(v19 + 48),
              &v53);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)(unsigned int)v26,
          (int)v53);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return v27;
      }
      BYTE1(v53) = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(v19 + 48) + 88LL))(
              *(_QWORD *)(v19 + 48),
              (char *)&v53 + 1);
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)(unsigned int)v28,
          (int)v53);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return (unsigned int)v28;
      }
      if ( (_WORD)v53 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x67,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)0x80070057LL,
          (int)v53);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return 2147942487LL;
      }
      *(_WORD *)((char *)&v53 + 1) = 0;
      v29 = (*(__int64 (__fastcall **)(__int64 *, char *))(**v15 + 96))(*v15, (char *)&v53 + 2);
      v31 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)(unsigned int)v29,
          (int)v53);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return v31;
      }
      LOBYTE(v30) = BYTE2(v53);
      v32 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v19 + 48) + 224LL))(*(_QWORD *)(v19 + 48), v30);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)(unsigned int)v32,
          (int)v53);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return v33;
      }
    }
    v57 = 0;
    v34 = (*(__int64 (__fastcall **)(__int64 *, int *))(**v15 + 80))(*v15, &v57);
    v35 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v34,
        (int)v53);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v35;
    }
    v56 = 0;
    Instance = Windows::Internal::AssignedAccess::AssignedAccessUserInfo_CreateInstance(
                 v54,
                 *(struct Windows::Internal::AssignedAccess::IAssignedAccessAccount **)(v19 + 48),
                 (struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *)&v57,
                 (const enum Windows::Internal::AssignedAccess::ConfigSource *)&v56,
                 v53);
    v37 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)Instance,
        (int)v53);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v56);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v37;
    }
    v38 = *((_QWORD *)this + 11);
    if ( v38 )
    {
      string = v56;
      v39 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 16LL))(v38, &string);
      v40 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x77,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)(unsigned int)v39,
          (int)v53);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v56);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return v40;
      }
    }
    if ( v59 != 1 && v59 != 300 && v59 != 200 )
    {
      string = 0;
      v41 = v54;
      v42 = *(__int64 (__fastcall **)(Windows::Internal::AssignedAccess *, HSTRING *))(*(_QWORD *)v54 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v43 = v42(v41, &string);
      v44 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)(unsigned int)v43,
          (int)v53);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v56);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return v44;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v69 = StringRawBuffer;
      std::wstring::wstring(&v79, StringRawBuffer);
      v46 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                        v72,
                        &v70,
                        &v79);
      v47 = *v46 != v73;
      std::wstring::_Tidy_deallocate(&v79);
      if ( v47 )
      {
        wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
          v83,
          "Duplicated account is found: %ws",
          StringRawBuffer);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
          (const char *)0x80070057LL,
          (int)v53);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v56);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
        std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
        AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
        return 2147942487LL;
      }
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<unsigned short const * const &>(
        v72,
        &v75,
        &v69);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    }
    std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>::emplace_back<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> const &>(
      v60,
      &v56);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v56);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v54);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>>::vector_iterator_nothrow::operator+=(&Buf1);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v63);
  v48 = *((_QWORD *)this + 19);
  if ( v48
    && (v49 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v48 + 16LL))(v48, v60), v50 = v49, v49 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
      (const char *)(unsigned int)v49,
      (int)v53);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
    std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
    std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
    AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
    return v50;
  }
  else
  {
    v51 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessConfiguration,Windows::Internal::AssignedAccess::IAssignedAccessConfiguration,std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>> &>(
            a2,
            v60);
    v52 = v51;
    if ( v51 >= 0 )
    {
      wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v83);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfigurationbuilder.cpp",
        (const char *)(unsigned int)v51,
        (int)v53);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v72);
      std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(v60);
      std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(&v64);
      AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration((AssignedAccessTelemetry::BuildAssignedAccessConfiguration *)v83);
      return v52;
    }
  }
}

```

## disassembly

```asm
0x180076d30  mov     [rsp+arg_10], rbx
0x180076d35  mov     [rsp+arg_18], rsi
0x180076d3a  push    rdi
0x180076d3b  push    r12
0x180076d3d  push    r13
0x180076d3f  push    r14
0x180076d41  push    r15
0x180076d43  sub     rsp, 300h
0x180076d4a  mov     rax, cs:__security_cookie
0x180076d51  xor     rax, rsp
0x180076d54  mov     [rsp+328h+var_38], rax
0x180076d5c  mov     r13, rdx
0x180076d5f  mov     r14, rcx
0x180076d62  lea     rdx, aBuildassigneda; "BuildAssignedAccessConfiguration"
0x180076d69  lea     rcx, [rsp+328h+var_188]
0x180076d71  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180076d76  lea     rax, ??_7BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::BuildAssignedAccessConfiguration::`vftable'
0x180076d7d  mov     [rsp+328h+var_188], rax
0x180076d85  lea     rcx, [rsp+328h+var_188]; this
0x180076d8d  call    ?StartActivity@BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::StartActivity(void)
0x180076d92  nop
0x180076d93  mov     [rsp+328h+var_288], 0
0x180076d9e  mov     [rsp+328h+var_280], 0
0x180076daa  mov     [rsp+328h+var_278], 0
0x180076db6  lea     rcx, [rsp+328h+var_280]
0x180076dbe  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>>::_Alloc_sentinel_and_proxy(void)
0x180076dc3  nop
0x180076dc4  lea     rcx, [rsp+328h+var_270]
0x180076dcc  call    ??0?$vector@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@V?$allocator@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@@2@@std@@QEAA@XZ; std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(void)
0x180076dd1  nop
0x180076dd2  mov     [rsp+328h+var_258], 7
0x180076dde  mov     [rsp+328h+var_250], 8
0x180076dea  mov     [rsp+328h+var_288], 3F800000h
0x180076df5  mov     r8, [rsp+328h+var_280]
0x180076dfd  mov     r15d, 10h
0x180076e03  mov     edx, r15d
0x180076e06  lea     rcx, [rsp+328h+var_270]
0x180076e0e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180076e13  nop
0x180076e14  mov     rdx, [r14+10h]
0x180076e18  lea     rcx, [rsp+328h+var_2B8]
0x180076e1d  call    ??$get_range_nothrow@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::get_range_nothrow<Windows::Internal::AssignedAccess::AssignedAccessProfile *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *> *,long *)
0x180076e22  nop
0x180076e23  lea     rdx, [rsp+328h+var_240]
0x180076e2b  lea     rcx, [rsp+328h+var_2B8]
0x180076e30  call    ?begin@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAA?AVvector_iterator_nothrow@12@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::begin(void)
0x180076e35  mov     edi, [rsp+328h+var_2B0]
0x180076e39  mov     rax, [rsp+328h+var_240]
0x180076e41  mov     rcx, [rax+10h]
0x180076e45  cmp     dword ptr [rcx], 0
0x180076e48  jl      loc_180077127
0x180076e4e  cmp     [rsp+328h+var_238], edi
0x180076e55  jz      loc_180077127
0x180076e5b  lea     rcx, [rsp+328h+var_240]
0x180076e63  call    ??Dvector_iterator_nothrow@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEBAAEBV?$ComPtr@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *>>::vector_iterator_nothrow::operator*(void)
0x180076e68  mov     rsi, rax
0x180076e6b  xorps   xmm0, xmm0
0x180076e6e  movups  [rsp+328h+Buf1], xmm0
0x180076e76  mov     r8, [rax]
0x180076e79  mov     rcx, [r8]
0x180076e7c  mov     rax, [rcx+38h]
0x180076e80  lea     rdx, [rsp+328h+Buf1]
0x180076e88  mov     rcx, r8
0x180076e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e90  mov     ebx, eax
0x180076e92  test    eax, eax
0x180076e94  jns     short loc_180076EE3
0x180076e96  mov     rcx, [rsp+328h]; this
0x180076e9e  mov     r9d, eax; char *
0x180076ea1  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180076ea8  mov     edx, 2Fh ; '/'; void *
0x180076ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076eb2  nop
0x180076eb3  lea     rcx, [rsp+328h+var_298]
0x180076ebb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180076ec0  nop
0x180076ec1  lea     rcx, [rsp+328h+var_288]
0x180076ec9  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(void)
0x180076ece  nop
0x180076ecf  lea     rcx, [rsp+328h+var_188]; this
0x180076ed7  call    ??1BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration(void)
0x180076edc  mov     eax, ebx
0x180076ede  jmp     loc_180077EF4
0x180076ee3  mov     r8, r15; Size
0x180076ee6  lea     rdx, GUID_NULL; Buf2
0x180076eed  lea     rcx, [rsp+328h+Buf1]; Buf1
0x180076ef5  call    memcmp_0
0x180076efa  test    eax, eax
0x180076efc  jnz     short loc_180076F4E
0x180076efe  mov     rcx, [rsp+328h]; this
0x180076f06  mov     ebx, 80070057h
0x180076f0b  mov     r9d, ebx; char *
0x180076f0e  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180076f15  lea     edx, [rax+31h]; void *
0x180076f18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076f1d  nop
0x180076f1e  lea     rcx, [rsp+328h+var_298]
0x180076f26  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180076f2b  nop
0x180076f2c  lea     rcx, [rsp+328h+var_288]
0x180076f34  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(void)
0x180076f39  nop
0x180076f3a  lea     rcx, [rsp+328h+var_188]; this
0x180076f42  call    ??1BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration(void)
0x180076f47  mov     eax, ebx
0x180076f49  jmp     loc_180077EF4
0x180076f4e  mov     [rsp+328h+var_2F0], 0
0x180076f57  lea     rax, [rsp+328h+var_2F0]
0x180076f5c  mov     [rsp+328h+var_1E0], rax
0x180076f64  mov     [rsp+328h+lpsz], 0
0x180076f70  mov     [rsp+328h+var_1D0], 1
0x180076f78  lea     rdx, [rsp+328h+lpsz]; lplpsz
0x180076f80  lea     rcx, [rsp+328h+Buf1]; rclsid
0x180076f88  call    cs:__imp_StringFromCLSID
0x180076f8e  mov     ebx, eax
0x180076f90  lea     rcx, [rsp+328h+var_1E0]
0x180076f98  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180076f9d  test    ebx, ebx
0x180076f9f  jns     short loc_180076FF9
0x180076fa1  mov     rcx, [rsp+328h]; this
0x180076fa9  mov     r9d, ebx; char *
0x180076fac  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180076fb3  mov     edx, 33h ; '3'; void *
0x180076fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076fbd  nop
0x180076fbe  lea     rcx, [rsp+328h+var_2F0]
0x180076fc3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180076fc8  nop
0x180076fc9  lea     rcx, [rsp+328h+var_298]
0x180076fd1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180076fd6  nop
0x180076fd7  lea     rcx, [rsp+328h+var_288]
0x180076fdf  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(void)
0x180076fe4  nop
0x180076fe5  lea     rcx, [rsp+328h+var_188]; this
0x180076fed  call    ??1BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration(void)
0x180076ff2  mov     eax, ebx
0x180076ff4  jmp     loc_180077EF4
0x180076ff9  mov     rdx, [rsp+328h+var_2F0]
0x180076ffe  lea     rcx, [rsp+328h+var_1B8]
0x180077006  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007700b  lea     r8, [rsp+328h+var_1B8]
0x180077013  lea     rdx, [rsp+328h+var_248]
0x18007701b  lea     rcx, [rsp+328h+var_288]
0x180077023  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180077028  mov     rcx, [rsp+328h+var_280]
0x180077030  cmp     [rax], rcx
0x180077033  setnz   bl
0x180077036  lea     rcx, [rsp+328h+var_1B8]
0x18007703e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077043  test    bl, bl
0x180077045  jz      short loc_1800770BD
0x180077047  mov     r8, [rsp+328h+var_2F0]
0x18007704c  lea     rdx, aDuplicatedProf; "Duplicated profile ID is found: %ws"
0x180077053  lea     rcx, [rsp+328h+var_188]
0x18007705b  call    ?SetMessage@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXPEBDZZ; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(char const *,...)
0x180077060  mov     rcx, [rsp+328h]; this
0x180077068  mov     ebx, 80070057h
0x18007706d  mov     r9d, ebx; char *
0x180077070  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180077077  mov     edx, 39h ; '9'; void *
0x18007707c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077081  nop
0x180077082  lea     rcx, [rsp+328h+var_2F0]
0x180077087  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007708c  nop
0x18007708d  lea     rcx, [rsp+328h+var_298]
0x180077095  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007709a  nop
0x18007709b  lea     rcx, [rsp+328h+var_288]
0x1800770a3  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(void)
0x1800770a8  nop
0x1800770a9  lea     rcx, [rsp+328h+var_188]; this
0x1800770b1  call    ??1BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration(void)
0x1800770b6  mov     eax, ebx
0x1800770b8  jmp     loc_180077EF4
0x1800770bd  mov     rdx, [rsp+328h+var_2F0]
0x1800770c2  lea     rcx, [rsp+328h+var_1B8]
0x1800770ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800770cf  nop
0x1800770d0  lea     r8, [rsp+328h+var_1B8]
0x1800770d8  lea     rdx, [rsp+328h+rclsid]
0x1800770e0  lea     rcx, [rsp+328h+var_288]
0x1800770e8  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800770ed  mov     rcx, [rax]
0x1800770f0  add     rcx, 30h ; '0'
0x1800770f4  mov     rdx, [rsi]
0x1800770f7  call    ??4?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x1800770fc  nop
0x1800770fd  lea     rcx, [rsp+328h+var_1B8]
0x180077105  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007710a  nop
0x18007710b  lea     rcx, [rsp+328h+var_2F0]
0x180077110  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180077115  lea     rcx, [rsp+328h+var_240]
0x18007711d  call    ??Yvector_iterator_nothrow@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAAEAV012@H@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>>::vector_iterator_nothrow::operator+=(int)
0x180077122  jmp     loc_180076E39
0x180077127  lea     rcx, [rsp+328h+var_298]
0x18007712f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077134  xor     r15d, r15d
0x180077137  lea     rcx, [rsp+328h+var_2D0]
0x18007713c  call    ??0?$vector@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@V?$allocator@V?$function@$$A6AJPEAVMDMPolicyOperation@AssignedAccess@Internal@Windows@@@Z@std@@@2@@std@@QEAA@XZ; std::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>::vector<std::function<long (Windows::Internal::AssignedAccess::MDMPolicyOperation *)>>(void)
0x180077141  nop
0x180077142  lea     rcx, [rsp+328h+var_228]
0x18007714a  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18007714f  nop
0x180077150  mov     rdx, [r14+18h]
0x180077154  lea     rcx, [rsp+328h+var_2B8]
0x180077159  call    ??$get_range_nothrow@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::get_range_nothrow<Windows::Internal::AssignedAccess::AssignedAccessProfile *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *> *,long *)
0x18007715e  nop
0x18007715f  lea     rdx, [rsp+328h+Buf1]
0x180077167  lea     rcx, [rsp+328h+var_2B8]
0x18007716c  call    ?begin@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAA?AVvector_iterator_nothrow@12@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::begin(void)
0x180077171  mov     r12d, [rsp+328h+var_2B0]
0x180077176  mov     rax, qword ptr [rsp+328h+Buf1]
0x18007717e  mov     rcx, [rax+10h]
0x180077182  cmp     dword ptr [rcx], 0
0x180077185  jl      loc_180077DBA
0x18007718b  cmp     dword ptr [rsp+328h+Buf1+8], r12d
0x180077193  jz      loc_180077DBA
0x180077199  lea     rcx, [rsp+328h+Buf1]
0x1800771a1  call    ??Dvector_iterator_nothrow@?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEBAAEBV?$ComPtr@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *>>::vector_iterator_nothrow::operator*(void)
0x1800771a6  mov     rsi, rax
0x1800771a9  xorps   xmm0, xmm0
0x1800771ac  movups  xmmword ptr [rsp+328h+rclsid.Data1], xmm0
0x1800771b4  mov     r8, [rax]
0x1800771b7  mov     rcx, [r8]
0x1800771ba  mov     rax, [rcx+40h]
0x1800771be  lea     rdx, [rsp+328h+rclsid]
0x1800771c6  mov     rcx, r8
0x1800771c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771ce  mov     ebx, eax
0x1800771d0  xor     edi, edi
0x1800771d2  test    eax, eax
0x1800771d4  jns     short loc_18007723A
0x1800771d6  mov     rcx, [rsp+328h]; this
0x1800771de  mov     r9d, eax; char *
0x1800771e1  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800771e8  lea     edx, [rdi+45h]; void *
0x1800771eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771f0  nop
0x1800771f1  lea     rcx, [rsp+328h+var_298]
0x1800771f9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800771fe  nop
0x1800771ff  lea     rcx, [rsp+328h+var_228]
0x180077207  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18007720c  nop
0x18007720d  lea     rcx, [rsp+328h+var_2D0]
0x180077212  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(void)
0x180077217  nop
0x180077218  lea     rcx, [rsp+328h+var_288]
0x180077220  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(void)
0x180077225  nop
0x180077226  lea     rcx, [rsp+328h+var_188]; this
0x18007722e  call    ??1BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration(void)
0x180077233  mov     eax, ebx
0x180077235  jmp     loc_180077EF4
0x18007723a  mov     [rsp+328h+var_2F8], rdi
0x18007723f  lea     rax, [rsp+328h+var_2F8]
0x180077244  mov     [rsp+328h+var_1B8], rax
0x18007724c  mov     [rsp+328h+var_1B0], rdi
0x180077254  mov     [rsp+328h+var_1A8], 1
0x18007725c  lea     rdx, [rsp+328h+var_1B0]; lplpsz
0x180077264  lea     rcx, [rsp+328h+rclsid]; rclsid
0x18007726c  call    cs:__imp_StringFromCLSID
0x180077272  mov     ebx, eax
0x180077274  lea     rcx, [rsp+328h+var_1B8]
0x18007727c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180077281  test    ebx, ebx
0x180077283  jns     short loc_1800772F6
0x180077285  mov     rcx, [rsp+328h]; this
0x18007728d  mov     r9d, ebx; char *
0x180077290  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180077297  mov     edx, 47h ; 'G'; void *
0x18007729c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800772a1  nop
0x1800772a2  lea     rcx, [rsp+328h+var_2F8]
0x1800772a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800772ac  nop
0x1800772ad  lea     rcx, [rsp+328h+var_298]
0x1800772b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800772ba  nop
0x1800772bb  lea     rcx, [rsp+328h+var_228]
0x1800772c3  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800772c8  nop
0x1800772c9  lea     rcx, [rsp+328h+var_2D0]
0x1800772ce  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Tidy(void)
0x1800772d3  nop
0x1800772d4  lea     rcx, [rsp+328h+var_288]
0x1800772dc  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAssignedAccessProfile@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessProfile,wil::err_exception_policy>>>,0>>(void)
0x1800772e1  nop
0x1800772e2  lea     rcx, [rsp+328h+var_188]; this
0x1800772ea  call    ??1BuildAssignedAccessConfiguration@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::BuildAssignedAccessConfiguration::~BuildAssignedAccessConfiguration(void)
0x1800772ef  mov     eax, ebx
0x1800772f1  jmp     loc_180077EF4
0x1800772f6  mov     rdx, [rsp+328h+var_2F8]
0x1800772fb  lea     rcx, [rsp+328h+var_1B8]
0x180077303  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180077308  lea     r8, [rsp+328h+var_1B8]
0x180077310  lea     rdx, [rsp+328h+var_1E8]
  ... truncated ...
```
