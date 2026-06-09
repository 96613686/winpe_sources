# AppReadiness::Groups::OnDemandSyncGroup::RuntimeClassInitialize(AppReadiness::User *)

- ea: `0x1800277ac`
- end: `0x180027a46`
- name: `?RuntimeClassInitialize@OnDemandSyncGroup@Groups@AppReadiness@@QEAAJPEAVUser@3@@Z`
- size: `666`
- prototype: `__int64 __fastcall(AppReadiness::Groups::OnDemandSyncGroup *__hidden this, struct AppReadiness::User *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049e38`

## callees

- `0x180002958`
- `0x180003ea4`
- `0x180006b54`
- `0x18000e4a0`
- `0x1800203d8`
- `0x1800276e0`
- `0x180027780`
- `0x1800277ac`
- `0x180028814`
- `0x18003e210`
- `0x180049310`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002790d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027973`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800279d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002790d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027973`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800279d9`

## string_xrefs

- `0x18002780f`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180027868`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800278b8`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18002791e`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180027984`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800279ea`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppReadiness::Groups::OnDemandSyncGroup::RuntimeClassInitialize(
        AppReadiness::Groups::OnDemandSyncGroup *this,
        struct AppReadiness::User *a2)
{
  int v2; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rbx
  int v14; // eax
  int v16; // [rsp+20h] [rbp-50h]
  __int128 v17; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = (int)a2;
  std::wstring::wstring((__int64)&hstringHeader, (__int64)L"ART:OnDemandSyncGroup");
  v17 = 0;
  v4 = AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize(this, v2, (int)&hstringHeader, (int)&v17, 4);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v4,
      v16);
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&hstringHeader);
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.Internal.PackageManagerInternal",
    0x3Eu,
    0x3Du);
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
         v19,
         (_QWORD *)this + 45);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v5,
      v16);
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         v19,
         (__int64)this + 368);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageLocation",
    0x31u,
    0x30u);
  v7 = v19;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 376);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea, (char *)this + 376);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v16);
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageUserStatus",
    0x33u,
    0x32u);
  v9 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 384);
  v10 = RoGetActivationFactory(v9, &GUID_872735ff_f1f0_423d_b086_2d822dd4b9d7, (char *)this + 384);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v10,
      v16);
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageIdentity",
    0x31u,
    0x30u);
  v11 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 392);
  v12 = RoGetActivationFactory(v11, &GUID_84485035_7d09_4684_8440_e8eb94f59919, (char *)this + 392);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v12,
      v16);
  v13 = *((_QWORD *)this + 1);
  v14 = (*(__int64 (__fastcall **)(char *))(v13 + 144))((char *)this + 8);
  (*(void (__fastcall **)(char *, _QWORD))(v13 + 128))((char *)this + 8, v14 | 0x500000u);
  return 0;
}

```

## disassembly

```asm
0x1800277ac  mov     [rsp-18h+arg_10], rbx
0x1800277b1  push    rbp
0x1800277b2  push    rsi
0x1800277b3  push    rdi
0x1800277b4  mov     rbp, rsp
0x1800277b7  sub     rsp, 70h
0x1800277bb  mov     rax, cs:__security_cookie
0x1800277c2  xor     rax, rsp
0x1800277c5  mov     [rbp+var_10], rax
0x1800277c9  mov     rbx, rdx
0x1800277cc  mov     rsi, rcx
0x1800277cf  lea     rdx, String1; "ART:OnDemandSyncGroup"
0x1800277d6  lea     rcx, [rbp+hstringHeader]
0x1800277da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800277df  nop
0x1800277e0  xorps   xmm0, xmm0
0x1800277e3  movdqu  [rbp+var_40], xmm0
0x1800277e8  mov     [rsp+70h+var_50], 4; int
0x1800277f0  lea     r9, [rbp+var_40]
0x1800277f4  lea     r8, [rbp+hstringHeader]
0x1800277f8  mov     rdx, rbx
0x1800277fb  mov     rcx, rsi
0x1800277fe  call    ?RuntimeClassInitialize@BaseTaskGroup@Impl@AppReadiness@@IEAAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$weak_ptr@VPackageInfo@AppReadiness@@@6@W4TaskPriority@3@@Z; AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize(AppReadiness::User *,std::wstring const &,std::weak_ptr<AppReadiness::PackageInfo> const &,AppReadiness::TaskPriority)
0x180027803  nop
0x180027804  mov     rcx, [rbp+18h]; this
0x180027808  test    eax, eax
0x18002780a  jns     short loc_180027821
0x18002780c  mov     r9d, eax; char *
0x18002780f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180027816  mov     edx, 21h ; '!'; void *
0x18002781b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027821  lea     rcx, [rbp+hstringHeader]
0x180027825  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18002782a  mov     [rbp+var_18], 0
0x180027832  mov     r9d, 3Dh ; '='; unsigned int
0x180027838  lea     r8d, [r9+1]; unsigned int
0x18002783c  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x180027843  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180027847  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002784c  nop
0x18002784d  lea     rdx, [rsi+168h]
0x180027854  mov     rcx, [rbp+var_18]
0x180027858  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x18002785d  mov     rcx, [rbp+18h]; this
0x180027861  test    eax, eax
0x180027863  jns     short loc_18002787A
0x180027865  mov     r9d, eax; char *
0x180027868  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002786f  mov     edx, 22h ; '"'; void *
0x180027874  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002787a  mov     [rbp+var_18], 0
0x180027882  mov     r9d, 28h ; '('; unsigned int
0x180027888  lea     r8d, [r9+1]; unsigned int
0x18002788c  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180027893  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180027897  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002789c  nop
0x18002789d  lea     rdx, [rsi+170h]
0x1800278a4  mov     rcx, [rbp+var_18]
0x1800278a8  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800278ad  mov     rcx, [rbp+18h]; this
0x1800278b1  test    eax, eax
0x1800278b3  jns     short loc_1800278CA
0x1800278b5  mov     r9d, eax; char *
0x1800278b8  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800278bf  mov     edx, 23h ; '#'; void *
0x1800278c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800278ca  lea     rdi, [rsi+178h]
0x1800278d1  mov     [rbp+var_18], 0
0x1800278d9  mov     r9d, 30h ; '0'; unsigned int
0x1800278df  lea     r8d, [r9+1]; unsigned int
0x1800278e3  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800278ea  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800278ee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800278f3  nop
0x1800278f4  mov     rbx, [rbp+var_18]
0x1800278f8  mov     rcx, rdi
0x1800278fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027900  mov     r8, rdi
0x180027903  lea     rdx, _GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea
0x18002790a  mov     rcx, rbx
0x18002790d  call    cs:__imp_RoGetActivationFactory
0x180027913  mov     rcx, [rbp+18h]; this
0x180027917  test    eax, eax
0x180027919  jns     short loc_180027930
0x18002791b  mov     r9d, eax; char *
0x18002791e  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180027925  mov     edx, 24h ; '$'; void *
0x18002792a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027930  lea     rdi, [rsi+180h]
0x180027937  mov     [rbp+var_18], 0
0x18002793f  mov     r9d, 32h ; '2'; unsigned int
0x180027945  lea     r8d, [r9+1]; unsigned int
0x180027949  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUserStatus@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180027950  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180027954  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027959  nop
0x18002795a  mov     rbx, [rbp+var_18]
0x18002795e  mov     rcx, rdi
0x180027961  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027966  mov     r8, rdi
0x180027969  lea     rdx, _GUID_872735ff_f1f0_423d_b086_2d822dd4b9d7
0x180027970  mov     rcx, rbx
0x180027973  call    cs:__imp_RoGetActivationFactory
0x180027979  mov     rcx, [rbp+18h]; this
0x18002797d  test    eax, eax
0x18002797f  jns     short loc_180027996
0x180027981  mov     r9d, eax; char *
0x180027984  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002798b  mov     edx, 25h ; '%'; void *
0x180027990  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027996  lea     rdi, [rsi+188h]
0x18002799d  mov     [rbp+var_18], 0
0x1800279a5  mov     r9d, 30h ; '0'; unsigned int
0x1800279ab  lea     r8d, [r9+1]; unsigned int
0x1800279af  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageIdentity@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800279b6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800279ba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800279bf  nop
0x1800279c0  mov     rbx, [rbp+var_18]
0x1800279c4  mov     rcx, rdi
0x1800279c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800279cc  mov     r8, rdi
0x1800279cf  lea     rdx, _GUID_84485035_7d09_4684_8440_e8eb94f59919
0x1800279d6  mov     rcx, rbx
0x1800279d9  call    cs:__imp_RoGetActivationFactory
0x1800279df  mov     rcx, [rbp+18h]; this
0x1800279e3  test    eax, eax
0x1800279e5  jns     short loc_1800279FC
0x1800279e7  mov     r9d, eax; char *
0x1800279ea  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800279f1  mov     edx, 26h ; '&'; void *
0x1800279f6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800279fc  lea     rdi, [rsi+8]
0x180027a00  mov     rbx, [rdi]
0x180027a03  mov     rcx, rdi
0x180027a06  mov     rax, [rbx+90h]
0x180027a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a12  or      eax, 500000h
0x180027a17  mov     edx, eax
0x180027a19  mov     rcx, rdi
0x180027a1c  mov     rax, [rbx+80h]
0x180027a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a28  xor     eax, eax
0x180027a2a  mov     rcx, [rbp+var_10]
0x180027a2e  xor     rcx, rsp; StackCookie
0x180027a31  call    __security_check_cookie
0x180027a36  mov     rbx, [rsp+70h+arg_10]
0x180027a3e  add     rsp, 70h
0x180027a42  pop     rdi
0x180027a43  pop     rsi
0x180027a44  pop     rbp
0x180027a45  retn
```
