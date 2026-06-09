# OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage(Windows::Internal::StateRepository::IPackage *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocation> &)

- ea: `0x1400095e4`
- end: `0x140009727`
- name: `?GetPackageLocationForPackage@CustomInstallExecution@Internal@DEH@OSIntegration@@KAXPEAUIPackage@StateRepository@2Windows@@AEAV?$ComPtr@UIPackageLocation@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009cd8`

## callees

- `0x1400033b0`
- `0x140007d78`
- `0x14000891c`
- `0x1400095e4`
- `0x1400098dc`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140009653`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140009653`

## string_xrefs

- `0x140009664`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400096af`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rbx
  __int64 v11; // [rsp+20h] [rbp-40h] BYREF
  __int64 v12; // [rsp+28h] [rbp-38h] BYREF
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v12 = 0;
  v15 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageLocation",
    0x31u,
    0x30u);
  v4 = v15;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v12);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea, &v12);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v11);
  v11 = 0;
  v6 = v12;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v11);
  v8 = v7(v6, a1, &v11);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = v11;
  if ( *a2 != v11 )
  {
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v13 = *a2;
    *a2 = v9;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v13);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v11);
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v12);
}

```

## disassembly

```asm
0x1400095e4  mov     [rsp-18h+arg_10], rbx
0x1400095e9  mov     [rsp-18h+arg_18], rsi
0x1400095ee  push    rbp
0x1400095ef  push    rdi
0x1400095f0  push    r14
0x1400095f2  mov     rbp, rsp
0x1400095f5  sub     rsp, 60h
0x1400095f9  mov     rax, cs:__security_cookie
0x140009600  xor     rax, rsp
0x140009603  mov     [rbp+var_8], rax
0x140009607  mov     rsi, rdx
0x14000960a  mov     r14, rcx
0x14000960d  mov     [rbp+var_38], 0
0x140009615  mov     [rbp+var_10], 0
0x14000961d  mov     r9d, 30h ; '0'; unsigned int
0x140009623  lea     r8d, [r9+1]; unsigned int
0x140009627  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x14000962e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140009632  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140009637  nop
0x140009638  mov     rbx, [rbp+var_10]
0x14000963c  lea     rcx, [rbp+var_38]
0x140009640  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009645  lea     r8, [rbp+var_38]
0x140009649  lea     rdx, _GUID_b8c8be3c_3a39_4e73_b4ba_c70d91d1b8ea
0x140009650  mov     rcx, rbx
0x140009653  call    cs:__imp_RoGetActivationFactory
0x140009659  mov     rcx, [rbp+18h]; this
0x14000965d  test    eax, eax
0x14000965f  jns     short loc_140009676
0x140009661  mov     r9d, eax; char *
0x140009664  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000966b  mov     edx, 1DAh; void *
0x140009670  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009676  mov     [rbp+var_40], 0
0x14000967e  mov     rdi, [rbp+var_38]
0x140009682  mov     rax, [rdi]
0x140009685  mov     rbx, [rax+60h]
0x140009689  lea     rcx, [rbp+var_40]
0x14000968d  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009692  lea     r8, [rbp+var_40]
0x140009696  mov     rdx, r14
0x140009699  mov     rcx, rdi
0x14000969c  mov     rax, rbx
0x14000969f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096a4  mov     rcx, [rbp+18h]; this
0x1400096a8  test    eax, eax
0x1400096aa  jns     short loc_1400096C1
0x1400096ac  mov     r9d, eax; char *
0x1400096af  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400096b6  mov     edx, 1DDh; void *
0x1400096bb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400096c1  mov     rbx, [rbp+var_40]
0x1400096c5  cmp     [rsi], rbx
0x1400096c8  jz      short loc_1400096F3
0x1400096ca  test    rbx, rbx
0x1400096cd  jz      short loc_1400096DF
0x1400096cf  mov     rax, [rbx]
0x1400096d2  mov     rcx, rbx
0x1400096d5  mov     rax, [rax+8]
0x1400096d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096de  nop
0x1400096df  mov     rax, [rsi]
0x1400096e2  mov     [rbp+var_30], rax
0x1400096e6  mov     [rsi], rbx
0x1400096e9  lea     rcx, [rbp+var_30]
0x1400096ed  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400096f2  nop
0x1400096f3  lea     rcx, [rbp+var_40]
0x1400096f7  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400096fc  nop
0x1400096fd  lea     rcx, [rbp+var_38]
0x140009701  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009706  mov     rcx, [rbp+var_8]
0x14000970a  xor     rcx, rsp; StackCookie
0x14000970d  call    __security_check_cookie
0x140009712  lea     r11, [rsp+60h+var_s0]
0x140009717  mov     rbx, [r11+30h]
0x14000971b  mov     rsi, [r11+38h]
0x14000971f  mov     rsp, r11
0x140009722  pop     r14
0x140009724  pop     rdi
0x140009725  pop     rbp
0x140009726  retn
```
