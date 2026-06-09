# OSIntegration::DEH::Internal::SRStatics::Initialize(void)

- ea: `0x140009758`
- end: `0x1400098c3`
- name: `?Initialize@SRStatics@Internal@DEH@OSIntegration@@SAXXZ`
- size: `363`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a8a8`
- `0x14000aa08`

## callees

- `0x1400033b0`
- `0x140007d78`
- `0x14000891c`
- `0x140009758`
- `0x1400098dc`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400097be`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140009887`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400097be`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140009887`

## string_xrefs

- `0x140009853`: `Windows.Internal.StateRepository.CustomInstallWork`
- `0x1400097d0`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009824`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009899`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
void OSIntegration::DEH::Internal::SRStatics::Initialize(void)
{
  __int64 v0; // rbx
  __int64 v1; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall *v3)(__int64, __int64 *); // rdi
  int v4; // eax
  __int64 v5; // rbx
  int v6; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v0 = OSIntegration::DEH::Internal::SRStatics::s_userStatics;
  if ( !OSIntegration::DEH::Internal::SRStatics::s_userStatics )
  {
    v8 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.User",
      0x26u,
      0x25u);
    v1 = v8;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&OSIntegration::DEH::Internal::SRStatics::s_userStatics);
    ActivationFactory = RoGetActivationFactory(
                          v1,
                          &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720,
                          &OSIntegration::DEH::Internal::SRStatics::s_userStatics);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)hstringHeader.Reserved.Reserved1);
    v0 = OSIntegration::DEH::Internal::SRStatics::s_userStatics;
  }
  if ( !OSIntegration::DEH::Internal::SRStatics::s_perMachineUser )
  {
    v3 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v0 + 112LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&OSIntegration::DEH::Internal::SRStatics::s_perMachineUser);
    v4 = v3(v0, &OSIntegration::DEH::Internal::SRStatics::s_perMachineUser);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v4,
        (int)hstringHeader.Reserved.Reserved1);
  }
  if ( !OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics )
  {
    v8 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.CustomInstallWork",
      0x33u,
      0x32u);
    v5 = v8;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics);
    v6 = RoGetActivationFactory(
           v5,
           &GUID_5fd8fae3_eb98_4879_8199_cfc7f0d6834b,
           &OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v6,
        (int)hstringHeader.Reserved.Reserved1);
  }
}

```

## disassembly

```asm
0x140009758  mov     [rsp+arg_0], rbx
0x14000975d  push    rdi
0x14000975e  sub     rsp, 50h
0x140009762  mov     rax, cs:__security_cookie
0x140009769  xor     rax, rsp
0x14000976c  mov     [rsp+58h+var_18], rax
0x140009771  mov     rbx, cs:?s_userStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics> OSIntegration::DEH::Internal::SRStatics::s_userStatics
0x140009778  test    rbx, rbx
0x14000977b  jnz     short loc_1400097E9
0x14000977d  mov     [rsp+58h+var_20], rbx
0x140009782  lea     r9d, [rbx+25h]; unsigned int
0x140009786  lea     r8d, [rbx+26h]; unsigned int
0x14000978a  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x140009791  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x140009796  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000979b  nop
0x14000979c  mov     rbx, [rsp+58h+var_20]
0x1400097a1  lea     rcx, ?s_userStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics> OSIntegration::DEH::Internal::SRStatics::s_userStatics
0x1400097a8  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400097ad  lea     r8, ?s_userStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics> OSIntegration::DEH::Internal::SRStatics::s_userStatics
0x1400097b4  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x1400097bb  mov     rcx, rbx
0x1400097be  call    cs:__imp_RoGetActivationFactory
0x1400097c4  mov     rcx, [rsp+58h]; this
0x1400097c9  test    eax, eax
0x1400097cb  jns     short loc_1400097E2
0x1400097cd  mov     r9d, eax; char *
0x1400097d0  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400097d7  mov     edx, 2Eh ; '.'; void *
0x1400097dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400097e2  mov     rbx, cs:?s_userStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics> OSIntegration::DEH::Internal::SRStatics::s_userStatics
0x1400097e9  cmp     cs:?s_perMachineUser@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> OSIntegration::DEH::Internal::SRStatics::s_perMachineUser
0x1400097f1  jnz     short loc_140009836
0x1400097f3  mov     rax, [rbx]
0x1400097f6  mov     rdi, [rax+70h]
0x1400097fa  lea     rcx, ?s_perMachineUser@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> OSIntegration::DEH::Internal::SRStatics::s_perMachineUser
0x140009801  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009806  lea     rdx, ?s_perMachineUser@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> OSIntegration::DEH::Internal::SRStatics::s_perMachineUser
0x14000980d  mov     rcx, rbx
0x140009810  mov     rax, rdi
0x140009813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009818  mov     rcx, [rsp+58h]; this
0x14000981d  test    eax, eax
0x14000981f  jns     short loc_140009836
0x140009821  mov     r9d, eax; char *
0x140009824  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000982b  mov     edx, 33h ; '3'; void *
0x140009830  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009836  cmp     cs:?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x14000983e  jnz     short loc_1400098AB
0x140009840  mov     [rsp+58h+var_20], 0
0x140009849  mov     r9d, 32h ; '2'; unsigned int
0x14000984f  lea     r8d, [r9+1]; unsigned int
0x140009853  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_CustomInstallWork@@3QBGB; "Windows.Internal.StateRepository.Custom"...
0x14000985a  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x14000985f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140009864  nop
0x140009865  mov     rbx, [rsp+58h+var_20]
0x14000986a  lea     rcx, ?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x140009871  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009876  lea     r8, ?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x14000987d  lea     rdx, _GUID_5fd8fae3_eb98_4879_8199_cfc7f0d6834b
0x140009884  mov     rcx, rbx
0x140009887  call    cs:__imp_RoGetActivationFactory
0x14000988d  mov     rcx, [rsp+58h]; this
0x140009892  test    eax, eax
0x140009894  jns     short loc_1400098AB
0x140009896  mov     r9d, eax; char *
0x140009899  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400098a0  mov     edx, 3Ah ; ':'; void *
0x1400098a5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400098ab  mov     rcx, [rsp+58h+var_18]
0x1400098b0  xor     rcx, rsp; StackCookie
0x1400098b3  call    __security_check_cookie
0x1400098b8  mov     rbx, [rsp+58h+arg_0]
0x1400098bd  add     rsp, 50h
0x1400098c1  pop     rdi
0x1400098c2  retn
```
