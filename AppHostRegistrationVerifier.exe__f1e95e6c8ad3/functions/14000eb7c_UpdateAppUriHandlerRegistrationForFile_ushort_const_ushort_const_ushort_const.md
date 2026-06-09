# UpdateAppUriHandlerRegistrationForFile(ushort const *,ushort const *,ushort const *)

- ea: `0x14000eb7c`
- end: `0x14000ed96`
- name: `?UpdateAppUriHandlerRegistrationForFile@@YAXPEBG00@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008150`

## callees

- `0x140002210`
- `0x14000834c`
- `0x1400099c4`
- `0x14000a13c`
- `0x14000a41c`
- `0x14000a544`
- `0x14000bc30`
- `0x14000bef8`
- `0x14000ced4`
- `0x14000cf8c`
- `0x14000d49c`
- `0x14000e0ec`
- `0x14000e348`
- `0x14000eb28`
- `0x14000eb7c`
- `0x14000f3b8`
- `0x14000fc20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ecdf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ecdf`

## pseudocode

```c
void __fastcall UpdateAppUriHandlerRegistrationForFile(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HSTRING Reserved1; // rbx
  HSTRING_HEADER *v6; // rax
  PHKEY RegKeyForPackageAndHost; // rax
  HSTRING_HEADER *v8; // rax
  unsigned int v9; // r8d
  HSTRING_HEADER *v10; // rax
  unsigned int v11; // eax
  int v12; // r8d
  int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v16; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Data::Json::IJsonObject *v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+68h] [rbp-98h]
  HSTRING_HEADER v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER v24; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v25[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  hKey = (HKEY)a2;
  *(_QWORD *)Data = a3;
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "VerifyFromFile");
  v25[0] = &HostNameVerifierProvider::VerifyFromFile::`vftable';
  HostNameVerifierProvider::VerifyFromFile::StartActivity((HostNameVerifierProvider::VerifyFromFile *)v25, a3, a2);
  v16 = 0;
  phkResult[1] = (HKEY)&v16;
  v21 = 1;
  Reserved1 = (HSTRING)Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v22, (const WCHAR **)&hKey)[1].Reserved.Reserved1;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v24, (const WCHAR **)Data);
  RegKeyForPackageAndHost = GetRegKeyForPackageAndHost(phkResult, (HSTRING)v6[1].Reserved.Reserved1, Reserved1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
    &v16,
    RegKeyForPackageAndHost);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  GetAppUriHandlerJsonFromFile(&v19);
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v22, (const WCHAR **)Data);
  GetAppUriHandlerRegistrationEntryFromJson(&v18, v19, (HSTRING)v8[1].Reserved.Reserved1);
  v23 = 0;
  if ( !v18 )
  {
    if ( v16 )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x1CD, v9, (const char *)0x80070490LL, lpData);
LABEL_8:
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x1D2, v9, (const char *)0x8000FFFFLL, lpData);
  }
  if ( !v16 )
    goto LABEL_8;
  UpdateRegistryForAppUriHandlerPackage(v18, v16);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v24, (const WCHAR **)Data);
  GetSystemApplicationDataKeyForPackage(&hKey, (HSTRING)v10[1].Reserved.Reserved1);
  *(_DWORD *)Data = 0;
  v11 = RegSetValueExW(hKey, L"ForceValidation", 0, 4u, Data, 4u);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x2BD, v12, (const char *)v11, lpDataa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease((__int64 *)&v18);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease((__int64 *)&v19);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
  HostNameVerifierProvider::VerifyFromFile::~VerifyFromFile((HostNameVerifierProvider::VerifyFromFile *)v25);
}

```

## disassembly

```asm
0x14000eb7c  mov     [rsp-8+arg_18], rbx
0x14000eb81  push    rbp
0x14000eb82  push    rsi
0x14000eb83  push    rdi
0x14000eb84  lea     rbp, [rsp-110h]
0x14000eb8c  sub     rsp, 210h
0x14000eb93  mov     rax, cs:__security_cookie
0x14000eb9a  xor     rax, rsp
0x14000eb9d  mov     [rbp+120h+var_20], rax
0x14000eba4  mov     rdi, r8
0x14000eba7  mov     rbx, rdx
0x14000ebaa  mov     rsi, rcx
0x14000ebad  mov     [rsp+220h+hKey], rdx
0x14000ebb2  mov     qword ptr [rsp+220h+Data], r8
0x14000ebb7  lea     rdx, aVerifyfromfile; "VerifyFromFile"
0x14000ebbe  lea     rcx, [rbp+120h+var_170]
0x14000ebc2  call    ??0?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000ebc7  lea     rax, ??_7VerifyFromFile@HostNameVerifierProvider@@6B@; const HostNameVerifierProvider::VerifyFromFile::`vftable'
0x14000ebce  mov     [rbp+120h+var_170], rax
0x14000ebd2  mov     r8, rbx; unsigned __int16 *
0x14000ebd5  mov     rdx, rdi; unsigned __int16 *
0x14000ebd8  lea     rcx, [rbp+120h+var_170]; this
0x14000ebdc  call    ?StartActivity@VerifyFromFile@HostNameVerifierProvider@@QEAAXPEBG0@Z; HostNameVerifierProvider::VerifyFromFile::StartActivity(ushort const *,ushort const *)
0x14000ebe1  nop
0x14000ebe2  xor     edi, edi
0x14000ebe4  mov     [rsp+220h+var_1E8], rdi
0x14000ebe9  lea     rax, [rsp+220h+var_1E8]
0x14000ebee  mov     [rsp+220h+var_1C0], rax
0x14000ebf3  mov     [rsp+220h+var_1B8], 1
0x14000ebf8  lea     rdx, [rsp+220h+hKey]
0x14000ebfd  lea     rcx, [rsp+220h+var_1B0]
0x14000ec02  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000ec07  nop
0x14000ec08  mov     rbx, [rax+18h]
0x14000ec0c  lea     rdx, [rsp+220h+Data]
0x14000ec11  lea     rcx, [rbp+120h+var_190]
0x14000ec15  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000ec1a  nop
0x14000ec1b  mov     r8, rbx
0x14000ec1e  mov     rdx, [rax+18h]
0x14000ec22  lea     rcx, [rsp+220h+phkResult]; phkResult
0x14000ec27  call    ?GetRegKeyForPackageAndHost@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@0@Z; GetRegKeyForPackageAndHost(HSTRING__ *,HSTRING__ *)
0x14000ec2c  mov     rdx, rax
0x14000ec2f  lea     rcx, [rsp+220h+var_1E8]
0x14000ec34  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x14000ec39  lea     rcx, [rsp+220h+phkResult]
0x14000ec3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000ec43  nop
0x14000ec44  mov     rdx, rsi
0x14000ec47  lea     rcx, [rsp+220h+var_1D0]
0x14000ec4c  call    ?GetAppUriHandlerJsonFromFile@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z; GetAppUriHandlerJsonFromFile(ushort const *)
0x14000ec51  nop
0x14000ec52  lea     rdx, [rsp+220h+Data]
0x14000ec57  lea     rcx, [rsp+220h+var_1B0]
0x14000ec5c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000ec61  nop
0x14000ec62  mov     r8, [rax+18h]
0x14000ec66  mov     rdx, [rsp+220h+var_1D0]
0x14000ec6b  lea     rcx, [rsp+220h+var_1D8]
0x14000ec70  call    ?GetAppUriHandlerRegistrationEntryFromJson@@YA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAUIJsonArray@Json@Data@Windows@@PEAUHSTRING__@@@Z; GetAppUriHandlerRegistrationEntryFromJson(Windows::Data::Json::IJsonArray *,HSTRING__ *)
0x14000ec75  nop
0x14000ec76  mov     [rbp+120h+var_198], rdi
0x14000ec7a  mov     rcx, [rsp+220h+var_1D8]; struct Windows::Data::Json::IJsonObject *
0x14000ec7f  test    rcx, rcx
0x14000ec82  jz      loc_14000ED5F
0x14000ec88  mov     rdx, [rsp+220h+var_1E8]; HKEY
0x14000ec8d  test    rdx, rdx
0x14000ec90  jz      loc_14000ED7E
0x14000ec96  call    ?UpdateRegistryForAppUriHandlerPackage@@YAXPEAUIJsonObject@Json@Data@Windows@@PEAUHKEY__@@@Z; UpdateRegistryForAppUriHandlerPackage(Windows::Data::Json::IJsonObject *,HKEY__ *)
0x14000ec9b  lea     rdx, [rsp+220h+Data]
0x14000eca0  lea     rcx, [rbp+120h+var_190]
0x14000eca4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000eca9  nop
0x14000ecaa  mov     rdx, [rax+18h]; string
0x14000ecae  lea     rcx, [rsp+220h+hKey]; phkResult
0x14000ecb3  call    ?GetSystemApplicationDataKeyForPackage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@@Z; GetSystemApplicationDataKeyForPackage(HSTRING__ *)
0x14000ecb8  nop
0x14000ecb9  mov     dword ptr [rsp+220h+Data], edi
0x14000ecbd  lea     r9d, [rdi+4]; dwType
0x14000ecc1  mov     [rsp+220h+cbData], r9d; cbData
0x14000ecc6  lea     rax, [rsp+220h+Data]
0x14000eccb  mov     [rsp+220h+lpData], rax; unsigned int
0x14000ecd0  xor     r8d, r8d; Reserved
0x14000ecd3  lea     rdx, aForcevalidatio; "ForceValidation"
0x14000ecda  mov     rcx, [rsp+220h+hKey]; hKey
0x14000ecdf  call    cs:__imp_RegSetValueExW
0x14000ece5  mov     rcx, [rbp+128h]; this
0x14000ecec  test    eax, eax
0x14000ecee  jz      short loc_14000ECFE
0x14000ecf0  mov     r9d, eax; char *
0x14000ecf3  mov     edx, 2BDh; void *
0x14000ecf8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000ecfe  lea     rcx, [rsp+220h+hKey]
0x14000ed03  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000ed08  nop
0x14000ed09  lea     rcx, [rbp+120h+var_170]
0x14000ed0d  call    ?Stop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000ed12  nop
0x14000ed13  lea     rcx, [rsp+220h+var_1D8]
0x14000ed18  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ed1d  nop
0x14000ed1e  lea     rcx, [rsp+220h+var_1D0]
0x14000ed23  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ed28  nop
0x14000ed29  lea     rcx, [rsp+220h+var_1E8]
0x14000ed2e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000ed33  nop
0x14000ed34  lea     rcx, [rbp+120h+var_170]; this
0x14000ed38  call    ??1VerifyFromFile@HostNameVerifierProvider@@QEAA@XZ; HostNameVerifierProvider::VerifyFromFile::~VerifyFromFile(void)
0x14000ed3d  mov     rcx, [rbp+120h+var_20]
0x14000ed44  xor     rcx, rsp; StackCookie
0x14000ed47  call    __security_check_cookie
0x14000ed4c  mov     rbx, [rsp+220h+arg_18]
0x14000ed54  add     rsp, 210h
0x14000ed5b  pop     rdi
0x14000ed5c  pop     rsi
0x14000ed5d  pop     rbp
0x14000ed5e  retn
0x14000ed5f  cmp     [rsp+220h+var_1E8], rdi
0x14000ed64  jz      short loc_14000ED7E
0x14000ed66  mov     rcx, [rbp+128h]; this
0x14000ed6d  mov     edx, 1CDh; void *
0x14000ed72  mov     r9d, 80070490h; char *
0x14000ed78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ed7e  mov     rcx, [rbp+128h]; this
0x14000ed85  mov     edx, 1D2h; void *
0x14000ed8a  mov     r9d, 8000FFFFh; char *
0x14000ed90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
