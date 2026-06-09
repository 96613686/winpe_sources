# Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGlobalProfile(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::ConfigSource,_GUID,bool)

- ea: `0x1800665dc`
- end: `0x1800667b7`
- name: `?SerializeGlobalProfile@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@W4ConfigSource@234@U_GUID@@_N@Z`
- size: `475`
- prototype: `void __high(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, enum Windows::Internal::AssignedAccess::ConfigSource, struct _GUID, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800655ec`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180020050`
- `0x180022d00`
- `0x18002b190`
- `0x180037454`
- `0x1800575cc`
- `0x180063b68`
- `0x180064314`
- `0x1800665dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066623`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066623`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800666ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066760`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800666ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066760`

## string_xrefs

- `0x1800666df`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x180066771`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x180066634`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180066695`: `GlobalProfileConfigSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGlobalProfile(
        __int64 a1,
        __int64 a2,
        int a3,
        const IID *a4,
        unsigned __int8 a5)
{
  HRESULT v7; // eax
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  int lpData; // [rsp+20h] [rbp-51h]
  unsigned int lpDataa; // [rsp+20h] [rbp-51h]
  unsigned int lpDatab; // [rsp+20h] [rbp-51h]
  BYTE Data[8]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v17; // [rsp+38h] [rbp-39h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-31h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-21h]
  _BYTE v21[32]; // [rsp+60h] [rbp-11h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v17 = 0;
  v18 = &v17;
  lpsz = 0;
  LOBYTE(hKey) = 1;
  v7 = StringFromCLSID(a4, &lpsz);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v7,
      lpData);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
  std::wstring::wstring(v21, v17);
  std::wstring::wstring(&v18, L"GlobalProfileId");
  Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a2, &v18, v21);
  std::wstring::_Tidy_deallocate(&v18);
  std::wstring::_Tidy_deallocate(v21);
  *(_DWORD *)Data = a3;
  std::wstring::wstring(v21, L"GlobalProfileConfigSource");
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  v9 = RegSetValueExW(*(HKEY *)(a2 + 16), v8, 0, 4u, Data, 4u);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v9,
      lpDataa);
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::wstring(v21, L"GlobalProfileExclusions");
  Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(a2, &v18, v21);
  std::wstring::_Tidy_deallocate(v21);
  *(_DWORD *)Data = a5;
  std::wstring::wstring(v22, L"DeviceOwners");
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  v11 = RegSetValueExW(hKey, v10, 0, 4u, Data, 4u);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v11,
      lpDatab);
  std::wstring::_Tidy_deallocate(v22);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)&v18);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
}

```

## disassembly

```asm
0x1800665dc  push    rbp
0x1800665de  push    rbx
0x1800665df  push    rdi
0x1800665e0  lea     rbp, [rsp-3Fh]
0x1800665e5  sub     rsp, 0B0h
0x1800665ec  mov     rax, cs:__security_cookie
0x1800665f3  xor     rax, rsp
0x1800665f6  mov     [rbp+4Fh+var_20], rax
0x1800665fa  mov     edi, r8d
0x1800665fd  mov     rbx, rdx
0x180066600  mov     [rbp+4Fh+var_88], 0
0x180066608  lea     rax, [rbp+4Fh+var_88]
0x18006660c  mov     [rbp+4Fh+var_80], rax
0x180066610  mov     [rbp+4Fh+lpsz], 0
0x180066618  mov     byte ptr [rbp+4Fh+hKey], 1
0x18006661c  lea     rdx, [rbp+4Fh+lpsz]; lplpsz
0x180066620  mov     rcx, r9; rclsid
0x180066623  call    cs:__imp_StringFromCLSID
0x180066629  mov     rcx, [rbp+57h]; this
0x18006662d  test    eax, eax
0x18006662f  jns     short loc_180066646
0x180066631  mov     r9d, eax; char *
0x180066634  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006663b  mov     edx, 239h; void *
0x180066640  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066646  lea     rcx, [rbp+4Fh+var_80]
0x18006664a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006664f  mov     rdx, [rbp+4Fh+var_88]
0x180066653  lea     rcx, [rbp+4Fh+var_60]
0x180066657  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006665c  nop
0x18006665d  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x180066664  lea     rcx, [rbp+4Fh+var_80]
0x180066668  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006666d  nop
0x18006666e  lea     r8, [rbp+4Fh+var_60]
0x180066672  lea     rdx, [rbp+4Fh+var_80]
0x180066676  mov     rcx, rbx
0x180066679  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18006667e  nop
0x18006667f  lea     rcx, [rbp+4Fh+var_80]
0x180066683  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066688  nop
0x180066689  lea     rcx, [rbp+4Fh+var_60]
0x18006668d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066692  mov     dword ptr [rbp+4Fh+Data], edi
0x180066695  lea     rdx, aGlobalprofilec; "GlobalProfileConfigSource"
0x18006669c  lea     rcx, [rbp+4Fh+var_60]
0x1800666a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800666a5  nop
0x1800666a6  lea     rcx, [rbp+4Fh+var_60]
0x1800666aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800666af  mov     rdx, rax; lpValueName
0x1800666b2  mov     edi, 4
0x1800666b7  mov     [rsp+0C0h+cbData], edi; cbData
0x1800666bb  lea     rax, [rbp+4Fh+Data]
0x1800666bf  mov     [rsp+0C0h+lpData], rax; unsigned int
0x1800666c4  mov     r9d, edi; dwType
0x1800666c7  xor     r8d, r8d; Reserved
0x1800666ca  mov     rcx, [rbx+10h]; hKey
0x1800666ce  call    cs:__imp_RegSetValueExW
0x1800666d4  mov     rcx, [rbp+57h]; this
0x1800666d8  test    eax, eax
0x1800666da  jz      short loc_1800666F1
0x1800666dc  mov     r9d, eax; char *
0x1800666df  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x1800666e6  mov     edx, 0CDh; void *
0x1800666eb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800666f1  lea     rcx, [rbp+4Fh+var_60]
0x1800666f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800666fa  lea     rdx, aGlobalprofilee; "GlobalProfileExclusions"
0x180066701  lea     rcx, [rbp+4Fh+var_60]
0x180066705  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006670a  nop
0x18006670b  lea     r8, [rbp+4Fh+var_60]
0x18006670f  lea     rdx, [rbp+4Fh+var_80]
0x180066713  mov     rcx, rbx
0x180066716  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(std::wstring const &,ulong,ulong)
0x18006671b  nop
0x18006671c  lea     rcx, [rbp+4Fh+var_60]
0x180066720  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066725  movzx   eax, [rbp+4Fh+arg_20]
0x180066729  mov     dword ptr [rbp+4Fh+Data], eax
0x18006672c  lea     rdx, aDeviceowners; "DeviceOwners"
0x180066733  lea     rcx, [rbp+4Fh+var_40]
0x180066737  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006673c  nop
0x18006673d  lea     rcx, [rbp+4Fh+var_40]
0x180066741  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180066746  mov     rdx, rax; lpValueName
0x180066749  mov     [rsp+0C0h+cbData], edi; cbData
0x18006674d  lea     rax, [rbp+4Fh+Data]
0x180066751  mov     [rsp+0C0h+lpData], rax; unsigned int
0x180066756  mov     r9d, edi; dwType
0x180066759  xor     r8d, r8d; Reserved
0x18006675c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180066760  call    cs:__imp_RegSetValueExW
0x180066766  mov     rcx, [rbp+57h]; this
0x18006676a  test    eax, eax
0x18006676c  jz      short loc_180066783
0x18006676e  mov     r9d, eax; char *
0x180066771  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x180066778  mov     edx, 0CDh; void *
0x18006677d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180066783  lea     rcx, [rbp+4Fh+var_40]
0x180066787  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006678c  nop
0x18006678d  lea     rcx, [rbp+4Fh+var_80]; this
0x180066791  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180066796  nop
0x180066797  lea     rcx, [rbp+4Fh+var_88]
0x18006679b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800667a0  mov     rcx, [rbp+4Fh+var_20]
0x1800667a4  xor     rcx, rsp; StackCookie
0x1800667a7  call    __security_check_cookie
0x1800667ac  add     rsp, 0B0h
0x1800667b3  pop     rdi
0x1800667b4  pop     rbx
0x1800667b5  pop     rbp
0x1800667b6  retn
```
