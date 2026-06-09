# Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeProfile(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessProfile *)

- ea: `0x180066a5c`
- end: `0x180066ba3`
- name: `?SerializeProfile@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@PEAUIAssignedAccessProfile@234@@Z`
- size: `327`
- prototype: `void(Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *__hidden this, struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800655ec`
- `0x180065a30`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x180020050`
- `0x180022d00`
- `0x180037454`
- `0x1800575cc`
- `0x1800630e0`
- `0x180064314`
- `0x180066a5c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066ae2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066ae2`

## string_xrefs

- `0x180066aac`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180066af3`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180066b5d`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeProfile(
        Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *this,
        struct Windows::Internal::AssignedAccess::RegistryKeyBroker *a2,
        struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *a3)
{
  int v5; // eax
  HRESULT v6; // eax
  struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *v7; // r8
  int v8; // eax
  int v9; // [rsp+20h] [rbp-19h]
  __int64 v10; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-1h] BYREF
  struct Windows::Internal::AssignedAccess::RegistryKeyBroker *v12; // [rsp+50h] [rbp+17h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp+1Fh] BYREF
  char v14; // [rsp+60h] [rbp+27h]
  IID rclsid; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  rclsid = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, IID *))(*(_QWORD *)a3 + 56LL))(
         a3,
         &rclsid);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v5,
      v9);
  v10 = 0;
  v12 = (struct Windows::Internal::AssignedAccess::RegistryKeyBroker *)&v10;
  lpsz = 0;
  v14 = 1;
  v6 = StringFromCLSID(&rclsid, &lpsz);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v6,
      v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
  std::wstring::wstring(&v12, v10);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(a2, v11, &v12);
  std::wstring::_Tidy_deallocate(&v12);
  v12 = a2;
  lpsz = (LPOLESTR)&v10;
  v14 = 1;
  v8 = Windows::Internal::AssignedAccess::Details::Serialize((Windows::Internal::AssignedAccess::Details *)v11, a3, v7);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v8,
      v9);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v11);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x180066a5c  mov     [rsp-8+arg_0], rbx
0x180066a61  mov     [rsp-8+arg_18], rdi
0x180066a66  push    rbp
0x180066a67  lea     rbp, [rsp-57h]
0x180066a6c  sub     rsp, 90h
0x180066a73  mov     rax, cs:__security_cookie
0x180066a7a  xor     rax, rsp
0x180066a7d  mov     [rbp+57h+var_10], rax
0x180066a81  mov     rbx, r8
0x180066a84  mov     rdi, rdx
0x180066a87  xorps   xmm0, xmm0
0x180066a8a  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180066a8e  mov     rax, [r8]
0x180066a91  lea     rdx, [rbp+57h+rclsid]
0x180066a95  mov     rcx, r8
0x180066a98  mov     rax, [rax+38h]
0x180066a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066aa1  mov     rcx, [rbp+5Fh]; this
0x180066aa5  test    eax, eax
0x180066aa7  jns     short loc_180066ABE
0x180066aa9  mov     r9d, eax; char *
0x180066aac  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180066ab3  mov     edx, 1BCh; void *
0x180066ab8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066abe  mov     [rbp+57h+var_60], 0
0x180066ac6  lea     rax, [rbp+57h+var_60]
0x180066aca  mov     [rbp+57h+var_40], rax
0x180066ace  mov     [rbp+57h+lpsz], 0
0x180066ad6  mov     [rbp+57h+var_30], 1
0x180066ada  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180066ade  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180066ae2  call    cs:__imp_StringFromCLSID
0x180066ae8  mov     rcx, [rbp+5Fh]; this
0x180066aec  test    eax, eax
0x180066aee  jns     short loc_180066B05
0x180066af0  mov     r9d, eax; char *
0x180066af3  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180066afa  mov     edx, 1BEh; void *
0x180066aff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066b05  lea     rcx, [rbp+57h+var_40]
0x180066b09  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180066b0e  mov     rdx, [rbp+57h+var_60]
0x180066b12  lea     rcx, [rbp+57h+var_40]
0x180066b16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066b1b  nop
0x180066b1c  lea     r8, [rbp+57h+var_40]
0x180066b20  lea     rdx, [rbp+57h+var_58]
0x180066b24  mov     rcx, rdi
0x180066b27  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(std::wstring const &,ulong,ulong)
0x180066b2c  nop
0x180066b2d  lea     rcx, [rbp+57h+var_40]
0x180066b31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066b36  mov     [rbp+57h+var_40], rdi
0x180066b3a  lea     rax, [rbp+57h+var_60]
0x180066b3e  mov     [rbp+57h+lpsz], rax
0x180066b42  mov     [rbp+57h+var_30], 1
0x180066b46  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x180066b49  lea     rcx, [rbp+57h+var_58]; this
0x180066b4d  call    ?Serialize@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@234@PEAUIAssignedAccessProfile@234@@Z; Windows::Internal::AssignedAccess::Details::Serialize(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessProfile *)
0x180066b52  mov     rcx, [rbp+5Fh]; this
0x180066b56  test    eax, eax
0x180066b58  jns     short loc_180066B6F
0x180066b5a  mov     r9d, eax; char *
0x180066b5d  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180066b64  mov     edx, 1C6h; void *
0x180066b69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066b6f  lea     rcx, [rbp+57h+var_58]; this
0x180066b73  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180066b78  nop
0x180066b79  lea     rcx, [rbp+57h+var_60]
0x180066b7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180066b82  mov     rcx, [rbp+57h+var_10]
0x180066b86  xor     rcx, rsp; StackCookie
0x180066b89  call    __security_check_cookie
0x180066b8e  lea     r11, [rsp+90h+var_s0]
0x180066b96  mov     rbx, [r11+10h]
0x180066b9a  mov     rdi, [r11+28h]
0x180066b9e  mov     rsp, r11
0x180066ba1  pop     rbp
0x180066ba2  retn
```
