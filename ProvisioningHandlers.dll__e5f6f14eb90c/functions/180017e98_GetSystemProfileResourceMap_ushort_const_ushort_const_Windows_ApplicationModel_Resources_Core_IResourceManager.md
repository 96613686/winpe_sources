# GetSystemProfileResourceMap(ushort const *,ushort const *,Windows::ApplicationModel::Resources::Core::IResourceManager * *,Windows::ApplicationModel::Resources::Core::IResourceMap * *)

- ea: `0x180017e98`
- end: `0x1800180e2`
- name: `?GetSystemProfileResourceMap@@YAJPEBG0PEAPEAUIResourceManager@Core@Resources@ApplicationModel@Windows@@PEAPEAUIResourceMap@2345@@Z`
- size: `586`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IResourceManager **, struct Windows::ApplicationModel::Resources::Core::IResourceMap **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015448`

## callees

- `0x1800067fc`
- `0x18000b46c`
- `0x1800136cc`
- `0x180017e98`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017f19`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017f19`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetSystemProfileResourceMap(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IResourceManager **a3,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap **a4)
{
  __int64 v4; // rbx
  int ActivationFactory; // ebx
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, const wchar_t **); // rbx
  __int64 v17; // rax
  unsigned __int16 *v18; // rax
  const wchar_t *v20; // [rsp+20h] [rbp-29h] BYREF
  __int64 v21; // [rsp+28h] [rbp-21h] BYREF
  __int64 v22; // [rsp+30h] [rbp-19h] BYREF
  __int64 v23; // [rsp+38h] [rbp-11h] BYREF
  __int64 v24; // [rsp+40h] [rbp-9h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-1h] BYREF
  const wchar_t *v26; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v28; // [rsp+70h] [rbp+27h]
  _BYTE v29[32]; // [rsp+78h] [rbp+2Fh] BYREF

  v26 = L"Resources";
  v20 = L"Windows.UI.SettingsHandlers-nt";
  v25 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Resources.Core.ResourceManager",
    0x38u,
    0x37u);
  v4 = v28;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)&v25);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7, &v25);
  if ( ActivationFactory < 0 )
    goto LABEL_13;
  v24 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
  v7 = **v25;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v24);
  ActivationFactory = v7(v6, &GUID_4a8eac58_b652_459d_8de1_239471e8b22b, &v24);
  if ( ActivationFactory >= 0 )
  {
    v23 = 0;
    v8 = v24;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v23);
    ActivationFactory = v9(v8, &v23);
    if ( ActivationFactory >= 0 )
    {
      v22 = 0;
      v10 = v23;
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 56LL);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v22);
      ActivationFactory = v11(v10, &v22);
      if ( ActivationFactory >= 0 )
      {
        v21 = 0;
        v12 = v22;
        v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 48LL);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v21);
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v29, &v20);
        ActivationFactory = v13(v12, *(_QWORD *)(v14 + 24), &v21);
        if ( ActivationFactory >= 0 )
        {
          v20 = 0;
          v15 = v21;
          v16 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t **))(*(_QWORD *)v21 + 72LL);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)&v20);
          v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v29, &v26);
          ActivationFactory = v16(v15, *(_QWORD *)(v17 + 24), &v20);
          if ( ActivationFactory >= 0 )
          {
            v18 = (unsigned __int16 *)v20;
            v20 = 0;
            SystemSettings::DataModel::Details::s_handlersResourceMap = v18;
          }
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)&v20);
        }
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v21);
      }
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v22);
    }
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v23);
  }
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v24);
  if ( ActivationFactory < 0 )
LABEL_13:
    SystemSettings::DataModel::Details::s_handlersResourceMap = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)&v25);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180017e98  mov     [rsp-8+arg_0], rbx
0x180017e9d  mov     [rsp-8+arg_8], rdi
0x180017ea2  push    rbp
0x180017ea3  lea     rbp, [rsp-57h]
0x180017ea8  sub     rsp, 0A0h
0x180017eaf  mov     rax, cs:__security_cookie
0x180017eb6  xor     rax, rsp
0x180017eb9  mov     [rbp+57h+var_8], rax
0x180017ebd  lea     rax, aResources; "Resources"
0x180017ec4  mov     [rbp+57h+var_50], rax
0x180017ec8  lea     rax, aWindowsUiSetti; "Windows.UI.SettingsHandlers-nt"
0x180017ecf  mov     [rbp+57h+var_80], rax
0x180017ed3  mov     [rbp+57h+var_58], 0
0x180017edb  mov     [rbp+57h+var_30], 0
0x180017ee3  mov     r9d, 37h ; '7'; unsigned int
0x180017ee9  lea     r8d, [r9+1]; unsigned int
0x180017eed  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Resources_Core_ResourceManager@@3QBGB; "Windows.ApplicationModel.Resources.Core"...
0x180017ef4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180017ef8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017efd  nop
0x180017efe  mov     rbx, [rbp+57h+var_30]
0x180017f02  lea     rcx, [rbp+57h+var_58]
0x180017f06  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180017f0b  lea     r8, [rbp+57h+var_58]
0x180017f0f  lea     rdx, _GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7
0x180017f16  mov     rcx, rbx
0x180017f19  call    cs:__imp_RoGetActivationFactory
0x180017f20  nop     dword ptr [rax+rax+00h]
0x180017f25  mov     ebx, eax
0x180017f27  test    eax, eax
0x180017f29  js      loc_1800180A2
0x180017f2f  mov     [rbp+57h+var_60], 0
0x180017f37  mov     rbx, [rbp+57h+var_58]
0x180017f3b  mov     rax, [rbx]
0x180017f3e  mov     rdi, [rax]
0x180017f41  lea     rcx, [rbp+57h+var_60]
0x180017f45  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180017f4a  lea     r8, [rbp+57h+var_60]
0x180017f4e  lea     rdx, _GUID_4a8eac58_b652_459d_8de1_239471e8b22b
0x180017f55  mov     rcx, rbx
0x180017f58  mov     rax, rdi
0x180017f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f60  mov     ebx, eax
0x180017f62  test    eax, eax
0x180017f64  js      loc_180018095
0x180017f6a  mov     [rbp+57h+var_68], 0
0x180017f72  mov     rdi, [rbp+57h+var_60]
0x180017f76  mov     rax, [rdi]
0x180017f79  mov     rbx, [rax+30h]
0x180017f7d  lea     rcx, [rbp+57h+var_68]
0x180017f81  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180017f86  lea     rdx, [rbp+57h+var_68]
0x180017f8a  mov     rcx, rdi
0x180017f8d  mov     rax, rbx
0x180017f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f95  mov     ebx, eax
0x180017f97  test    eax, eax
0x180017f99  js      loc_18001808B
0x180017f9f  mov     [rbp+57h+var_70], 0
0x180017fa7  mov     rdi, [rbp+57h+var_68]
0x180017fab  mov     rax, [rdi]
0x180017fae  mov     rbx, [rax+38h]
0x180017fb2  lea     rcx, [rbp+57h+var_70]
0x180017fb6  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180017fbb  lea     rdx, [rbp+57h+var_70]
0x180017fbf  mov     rcx, rdi
0x180017fc2  mov     rax, rbx
0x180017fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fca  mov     ebx, eax
0x180017fcc  test    eax, eax
0x180017fce  js      loc_180018081
0x180017fd4  mov     [rbp+57h+var_78], 0
0x180017fdc  mov     rdi, [rbp+57h+var_70]
0x180017fe0  mov     rax, [rdi]
0x180017fe3  mov     rbx, [rax+30h]
0x180017fe7  lea     rcx, [rbp+57h+var_78]
0x180017feb  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180017ff0  lea     rdx, [rbp+57h+var_80]
0x180017ff4  lea     rcx, [rbp+57h+var_28]
0x180017ff8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017ffd  nop
0x180017ffe  lea     r8, [rbp+57h+var_78]
0x180018002  mov     rdx, [rax+18h]
0x180018006  mov     rcx, rdi
0x180018009  mov     rax, rbx
0x18001800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018011  mov     ebx, eax
0x180018013  test    eax, eax
0x180018015  js      short loc_180018077
0x180018017  mov     [rbp+57h+var_80], 0
0x18001801f  mov     rdi, [rbp+57h+var_78]
0x180018023  mov     rax, [rdi]
0x180018026  mov     rbx, [rax+48h]
0x18001802a  lea     rcx, [rbp+57h+var_80]
0x18001802e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180018033  lea     rdx, [rbp+57h+var_50]
0x180018037  lea     rcx, [rbp+57h+var_28]
0x18001803b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180018040  nop
0x180018041  lea     r8, [rbp+57h+var_80]
0x180018045  mov     rdx, [rax+18h]
0x180018049  mov     rcx, rdi
0x18001804c  mov     rax, rbx
0x18001804f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018054  mov     ebx, eax
0x180018056  test    eax, eax
0x180018058  js      short loc_18001806D
0x18001805a  mov     rax, [rbp+57h+var_80]
0x18001805e  mov     [rbp+57h+var_80], 0
0x180018066  mov     cs:?s_handlersResourceMap@Details@DataModel@SystemSettings@@3PEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@EA, rax; Windows::ApplicationModel::Resources::Core::IResourceMap * SystemSettings::DataModel::Details::s_handlersResourceMap
0x18001806d  lea     rcx, [rbp+57h+var_80]
0x180018071  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180018076  nop
0x180018077  lea     rcx, [rbp+57h+var_78]
0x18001807b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180018080  nop
0x180018081  lea     rcx, [rbp+57h+var_70]
0x180018085  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001808a  nop
0x18001808b  lea     rcx, [rbp+57h+var_68]
0x18001808f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180018094  nop
0x180018095  lea     rcx, [rbp+57h+var_60]
0x180018099  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001809e  test    ebx, ebx
0x1800180a0  jns     short loc_1800180AD
0x1800180a2  mov     cs:?s_handlersResourceMap@Details@DataModel@SystemSettings@@3PEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@EA, 0; Windows::ApplicationModel::Resources::Core::IResourceMap * SystemSettings::DataModel::Details::s_handlersResourceMap
0x1800180ad  mov     [rbp+57h+var_30], 0
0x1800180b5  lea     rcx, [rbp+57h+var_58]
0x1800180b9  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800180be  mov     eax, ebx
0x1800180c0  mov     rcx, [rbp+57h+var_8]
0x1800180c4  xor     rcx, rsp; StackCookie
0x1800180c7  call    __security_check_cookie
0x1800180cc  lea     r11, [rsp+0A0h+var_s0]
0x1800180d4  mov     rbx, [r11+10h]
0x1800180d8  mov     rdi, [r11+18h]
0x1800180dc  mov     rsp, r11
0x1800180df  pop     rbp
0x1800180e0  retn
```
