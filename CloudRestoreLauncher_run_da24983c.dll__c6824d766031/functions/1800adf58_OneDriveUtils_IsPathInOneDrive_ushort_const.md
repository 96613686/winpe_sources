# OneDriveUtils::IsPathInOneDrive(ushort const *)

- ea: `0x1800adf58`
- end: `0x1800ae043`
- name: `?IsPathInOneDrive@OneDriveUtils@@YA_NPEBG@Z`
- size: `235`
- prototype: `bool __fastcall(OneDriveUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a96f0`
- `0x1800ab0ec`
- `0x1800bca00`

## callees

- `0x18001649c`
- `0x18001666c`
- `0x18001cfa4`
- `0x18001da4c`
- `0x1800adf58`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800adfea`
- `KERNEL32!CompareStringOrdinal` at `0x1800adfea`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800adf79`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800adf79`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall OneDriveUtils::IsPathInOneDrive(const WCHAR *this, const unsigned __int16 *a2)
{
  HRESULT v2; // eax
  void *v3; // rdi
  __int64 (__fastcall *v4)(void *, const PROPERTYKEY *, LPCWCH *); // rbx
  int v5; // eax
  bool v6; // bl
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWCH lpString1; // [rsp+48h] [rbp+10h] BYREF
  void *ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  v2 = SHCreateItemFromParsingName(this, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
      (const char *)(unsigned int)v2,
      bIgnoreCase);
  lpString1 = 0;
  v3 = ppv;
  v4 = *(__int64 (__fastcall **)(void *, const PROPERTYKEY *, LPCWCH *))(*(_QWORD *)ppv + 136LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpString1,
    0);
  v5 = v4(v3, &PKEY_StorageProviderId, &lpString1);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  v6 = CompareStringOrdinal(lpString1, -1, L"OneDrive", -1, 1) == 2;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString1);
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&ppv);
  return v6;
}

```

## disassembly

```asm
0x1800adf58  mov     [rsp+arg_0], rbx
0x1800adf5d  push    rdi
0x1800adf5e  sub     rsp, 30h
0x1800adf62  mov     [rsp+38h+ppv], 0
0x1800adf6b  lea     r9, [rsp+38h+ppv]; ppv
0x1800adf70  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800adf77  xor     edx, edx; pbc
0x1800adf79  call    cs:__imp_SHCreateItemFromParsingName
0x1800adf7f  mov     rcx, [rsp+38h]; this
0x1800adf84  test    eax, eax
0x1800adf86  js      loc_1800AE02E
0x1800adf8c  mov     [rsp+38h+lpString1], 0
0x1800adf95  mov     rdi, [rsp+38h+ppv]
0x1800adf9a  mov     rax, [rdi]
0x1800adf9d  mov     rbx, [rax+88h]
0x1800adfa4  xor     edx, edx
0x1800adfa6  lea     rcx, [rsp+38h+lpString1]
0x1800adfab  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800adfb0  lea     r8, [rsp+38h+lpString1]
0x1800adfb5  lea     rdx, PKEY_StorageProviderId
0x1800adfbc  mov     rcx, rdi
0x1800adfbf  mov     rax, rbx
0x1800adfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adfc7  mov     rcx, [rsp+38h]; this
0x1800adfcc  test    eax, eax
0x1800adfce  js      short loc_1800AE019
0x1800adfd0  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800adfd8  or      edx, 0FFFFFFFFh; cchCount1
0x1800adfdb  mov     r9d, edx; cchCount2
0x1800adfde  lea     r8, aOnedrive; "OneDrive"
0x1800adfe5  mov     rcx, [rsp+38h+lpString1]; lpString1
0x1800adfea  call    cs:__imp_CompareStringOrdinal
0x1800adff0  nop
0x1800adff1  cmp     eax, 2
0x1800adff4  setz    bl
0x1800adff7  lea     rcx, [rsp+38h+lpString1]
0x1800adffc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ae001  nop
0x1800ae002  lea     rcx, [rsp+38h+ppv]
0x1800ae007  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ae00c  mov     al, bl
0x1800ae00e  mov     rbx, [rsp+38h+arg_0]
0x1800ae013  add     rsp, 30h
0x1800ae017  pop     rdi
0x1800ae018  retn
0x1800ae019  mov     r9d, eax; char *
0x1800ae01c  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ae023  mov     edx, 0B5h; void *
0x1800ae028  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae02e  mov     r9d, eax; char *
0x1800ae031  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ae038  mov     edx, 0B3h; void *
0x1800ae03d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
